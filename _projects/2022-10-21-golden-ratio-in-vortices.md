---
layout: distill
title: Golden Ratio and Vortices
description: How vortex dynamics reveal bifurcations at golden-ratio thresholds.
img: assets/img/posts/20221021/front.png
importance: 1
category: research
---
## Summary

<a id="download code" href="https://raw.githubusercontent.com/hch-wang/hch-wang.github.io/refs/heads/master/assets/html/goldenHydro_web.html"> Download Code</a>
[Notebook](/assets/html/goldenHydro_web.html)

[Preview Version](http://www.math.toronto.edu/khesin/papers/goldenhydroTMIN.pdf)
[Published Version](https://link.springer.com/article/10.1007/s00283-021-10099-1)

[Prof. Boris Khesin](http://www.math.toronto.edu/khesin/)

In this two-point-vortex system on the half-plane, $$W$$ is a dimensionless parameter, and
$$W=\phi, 1, \frac{1}{\phi}$$ are three bifurcation values, where $$\phi$$ is the golden ratio.

Two mechanisms act on each point vortex:

1. translation along the boundary of the half-plane;
2. rotation around the other vortex.

These two mechanisms compete and lead to different types of the trajectories.

### Vortex Pair
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221021/pos1.png" alt="Phase portrait for a same-sign vortex pair" title="Phase portrait for a vortex pair" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Two vortices with the same sign form a vortex pair. Leapfrogging motions appear when $$W<1$$, and cusp motion appears at $$W=1/\phi$$.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221021/0.193.gif" alt="Leapfrogging vortex-pair motion at W equals 0.193" title="Vortex pair at W = 0.193" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221021/0.618.gif" alt="Cusp vortex-pair motion at W equals 0.618" title="Vortex pair at W = 0.618" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


### Vortex Dipole
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221021/neg1.png" alt="Phase portrait for an opposite-sign vortex dipole" title="Phase portrait for a vortex dipole" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    A vortex dipole consists of two vortices with equal magnitude and opposite sign. Cusp motion appears at $$W=\phi$$, and the dipole escapes from the boundary when $$W<1$$.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221021/1.618.gif" alt="Cusp vortex-dipole motion at W equals 1.618" title="Vortex dipole at W = 1.618" class="img-fluid rounded z-depth-1" %}
    </div>
</div>



## Introduction

A single point vortex on the half-plane can be represented by a vortex dipole symmetric about the boundary $$(y=0)$$ in the full plane. Thus, an $$N$$-point-vortex system in the half-plane is equivalent to a $$2N$$-point-vortex system in the full plane consisting of the original vortices and their images.

The Green's function on the half-plane $$\mathbb{R}_+^2$$ is

$$
G_{\mathbb{R}^2_+}\left( {z,z'} \right) =  - \frac{1}{2\pi}\log ||z - z'||+\frac{1}{2\pi}\log ||z - z'^*||
$$

and the Hamiltonian is

$$
H=\frac{1}{4 \pi} \log \left(\left(2 y_1\right)^{\Gamma_1^2}\left(2 y_2\right)^{\Gamma_2^2}\left(\frac{\left(x_1-x_2\right)^2+\left(y_1+y_2\right)^2}{\left(x_1-x_2\right)^2+\left(y_1-y_2\right)^2}\right)^{\Gamma_1 \Gamma_2}\right)
$$

The first term represents the interaction between different vortices with their images; and the second term represents the interaction between a vortex and its image.

For the two-point-vortex system on the half-plane, the equations of motion are

$$

\dot{x}_1=\frac{\Gamma_1}{4 \pi} \frac{1}{y_1}+\frac{\Gamma_2}{4 \pi}\left(\frac{2\left(y_1+y_2\right)}{\left(x_1-x_2\right)^2+\left(y_1+y_2\right)^2}-\frac{2\left(y_1-y_2\right)}{\left(x_1-x_2\right)^2+\left(y_1-y_2\right)^2}\right)

$$

and

$$
\dot{y}_1=\frac{-\Gamma_2}{4 \pi}\left(\frac{2\left(x_1-x_2\right)}{\left(x_1-x_2\right)^2+\left(y_1+y_2\right)^2}-\frac{2\left(x_1-x_2\right)}{\left(x_1-x_2\right)^2+\left(y_1-y_2\right)^2}\right)
$$

To study vortex bifurcations we normalize their strengths by setting $$\Gamma_1=\Gamma_2=1$$ for a vortex pair and $$\Gamma_1=-\Gamma_2=1$$ for a dipole. Furthermore, introduce the following dimensionless parameter

$$W:=(P / \Gamma)^2 \exp \left(-4 \pi \mathcal{H} / \Gamma^2\right)$$

measuring the vortex interaction where $$\Gamma:=\Gamma_1=\pm \Gamma_2$$.
As we will see below, the increase of $$W$$ corresponds to the weakening of the interaction between the point vortices.

## More GIF
### Vortex Pair
When two point vortices have same strength, we have the following four scenarios.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221021/0.193.gif" alt="Leapfrogging vortex-pair motion at W equals 0.193" title="Vortex pair at W = 0.193" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221021/0.618.gif" alt="Cusp vortex-pair motion at W equals 0.618" title="Vortex pair at W = 0.618" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221021/0.906.gif" alt="Vortex-pair motion at W equals 0.906" title="Vortex pair at W = 0.906" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221021/1.041.gif" alt="Vortex-pair motion at W equals 1.041" title="Vortex pair at W = 1.041" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

### Vortex Dipole
When two point vortices have opposite strength $$\Gamma_1=-\Gamma_2$$, we have the following four scenarios.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221021/0.911.gif" alt="Vortex-dipole motion at W equals 0.911" title="Vortex dipole at W = 0.911" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221021/1.345.gif" alt="Vortex-dipole motion at W equals 1.345" title="Vortex dipole at W = 1.345" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221021/1.542.gif" alt="Vortex-dipole motion at W equals 1.542" title="Vortex dipole at W = 1.542" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221021/1.618.gif" alt="Cusp vortex-dipole motion at W equals 1.618" title="Vortex dipole at W = 1.618" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221021/1.932.gif" alt="Vortex-dipole motion at W equals 1.932" title="Vortex dipole at W = 1.932" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
