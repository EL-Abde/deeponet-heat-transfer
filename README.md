# deeponet-heat-transfer
DeepONet surrogate model for 2D steady-state heat conduction in heterogeneous materials with localized heat sources.

## Physical Problem

We consider **steady-state heat conduction in a heterogeneous 2D material with localized heat sources**.

The governing equation is:

$$
\nabla\cdot\left(\kappa(x,y)\nabla\theta(x,y)\right)+Q(x,y)=0
$$

with:

* Spatially varying conductivity $\kappa(x,y)$
* Heat-source field $Q(x,y)$
* Hot left boundary: $\theta(0,y)=1$
* Cold right boundary: $\theta(1,y)=0$
* Adiabatic top and bottom boundaries

The objective is to train a **DeepONet** to learn the operator:

$$
\boxed{(\kappa(x,y),Q(x,y))\longrightarrow\theta(x,y)}
$$

This provides a fast surrogate for predicting the temperature field from new material and heat-source configurations.
