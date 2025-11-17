# Introduction
approaches for modelling forest fires, first we have the "propagation models" that aim to predict the position of the front flame.
- [[cellular automata wildfire models]].
- [[envelop wildfire model]].
- [[semi-empirical wildfire models]]
The other class is the "complete physical models" that aim to describe as faithfully as possible the combustion of vegetation
- Physical Models.


## Objective
- Relate complete physical models to two dimensional reaction diffusion models.
- The main idea is that a certain length scale:
  $$L$$
- $L$ (distance from the fire front, size of a developed fire), the height of the vegetation $\delta$ is such that the ratio $$\delta/L = \epsilon $$
- is small parameter, so the vegetation could be consider as as boundary layer

## model assumptions
- the forest at the [[mesoscopic scale]] can be considered as porous medium (porosity $\Phi$), called ==vegetal phase== is composed of 2 phases: 
	- <mark style="background: #D2B3FFA6;">p-phase:</mark> trunks, branches, twigs, leaves, ... consider itself as a porous medium constituted of solid components $s$, liquid component (water) $l$ and a flammable gas denoted by $F$.
	- <mark style="background: #D2B3FFA6;">f-phase:</mark> gaseous phase, containing steam (denoted $v$ with density $\rho_{g_p}$), air and gases.
	- mass fraction: of the gaseous $i$ is denoted by $Y_{ig_p}$

---
# model equations

## p-phase equations
the balance of energy equation is:
$$
(1-\Phi) \rho_p C_p^p \frac{\partial T_p}{\partial t} = \nabla \cdot (\lambda_p \nabla T_p - \mathbf{Q}_{pr}) + R_{cp} + \chi(T_f - T_p)
$$
- $\Phi:$ is the porosity of the p-phase.
- $\rho_p$: is the density of the p-phase.
- 
