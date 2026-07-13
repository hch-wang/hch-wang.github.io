---
layout: distill
title: Compound Burgers-KdV Solitons
description: Refraction, reflection, and fusion in a coupled shallow-water model.
img: assets/img/posts/20251015/waterfall_plot_combined.png
importance: 1
category: Mathematical Physics
---

# Burgers-swept KdV Equation: Soliton and Bore Interaction in Shallow Water

[Paper Link](https://arxiv.org/abs/2505.17026)


We consider a coupled PDE system between the Burgers equation and the KdV equation to model the interactions
between ‘bore’-like structures and wave-like solitons in shallow water. Two derivations of the resulting Burgers–swept KdV system are presented, based on Lie group symmetry and reduced variational principles. Exact
compound soliton solutions are obtained, and numerical simulations show that the Burgers and KdV momenta
tend toward a balance at which the coupled system reduces to the integrable Gardner equation. The numerical
simulations also reveal rich nonlinear solution behaviours that include refraction, reflection, and soliton fusion,
before the balance is finally achieved.


$\mathrm{Burgers}: \quad u_t+3 u u_x \quad=-v \partial_x\left(3 v^2+\gamma v_{x x}\right)$, 

$\mathrm{KdV}: \quad v_t+6 v v_x+\gamma v_{x x x}=-\partial_x(u v)$.

Or equivalently,

Gardner: $\quad v_t+6 v v_x+\frac{3}{2} v^2 v_x+\gamma v_{x x x}=-\partial_x(v m)$,

Lie Transport: $\quad m_t+\left(m \partial_x+\partial_x m\right) u=0, \quad$ with $\quad m:=u-\frac{1}{2} v^2$,


## Soliton Emergence 

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/posts/20251015/1_compound_soliton_emerge.gif" alt="Compound soliton emerging from coupled Burgers-KdV dynamics" title="Compound soliton emergence" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/posts/20251015/2_gaussian_split.gif" alt="Gaussian initial condition splitting into soliton-like structures" title="Gaussian splitting into solitons" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/posts/20251015/3_three_B_KdV_soliton.gif" alt="Three-soliton evolution in the coupled Burgers-KdV system" title="Three-soliton evolution" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

## Soliton and Bore interaction

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/posts/20251015/4_refraction_1.gif" alt="First refraction example in a soliton-bore interaction" title="Soliton refraction example one" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/posts/20251015/5_refraction_2.gif" alt="Second refraction example in a soliton-bore interaction" title="Soliton refraction example two" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/posts/20251015/6_reflection.gif" alt="Reflection in a soliton-bore interaction" title="Soliton reflection" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

## Soliton Fusion

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/posts/20251015/7_soliton_fusion_1.gif" alt="First example of soliton fusion" title="Soliton fusion example one" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

<div class="row">
  <div class="col-sm mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/posts/20251015/8_soliton_fusion_2.gif" alt="Second example of soliton fusion" title="Soliton fusion example two" class="img-fluid rounded z-depth-1" %}
  </div>
</div>

