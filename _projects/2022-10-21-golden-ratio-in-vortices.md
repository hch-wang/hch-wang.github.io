---
layout: distill
title: Golden Ratio and Vortices
description: Golden Ratio appears in vortices?
img: assets/img/posts/20221021/front.png
importance: 1
category: work
---
    
    ---
    layout: post
    read_time: true
    show_date: true
    title: "Golden Ratio in Vortices"
    date: 2022-10-21
    img: posts/20221021/point_vortex.jpg
    tags: [Hydrodynamics, Dynamical System, Scientific Computation]
    author: Hanchun Wang
    description: "point vortex on the half plane"
    ---
    
## Summary

<a id="download code" href="https://raw.githubusercontent.com/hch-wang/hch-wang.github.io/refs/heads/master/assets/html/goldenHydro_web.html"> Download Code</a>
[Code](assets/html/goldenHydro_web.html)

[Preview Version](http://www.math.toronto.edu/khesin/papers/goldenhydroTMIN.pdf)
[Published Version](https://link.springer.com/article/10.1007/s00283-021-10099-1)

[Prof. Boris Khesin](http://www.math.toronto.edu/khesin/)

In this two point vortices system on the half plane, we show that $$W$$ is a non-dimensional parameter, 
and $$W=\phi, 1, \frac{1}{\phi}$$ are three bifurcation values in this system. Where $$\phi$$ is the Golden Ratio.

There are two mechanisms applied on a point vortex. 
1. Move along the boundary of the half plane
2. rotate on the other vortex

These two mechanisms compete and lead to different types of the trajectories.

### Vortex Pair
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221021/pos1.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Two point vortices same strength is a vortex pair. Leapfrogging motions appear when $$W<1$$, and cusp motion appear at $$W=1/\phi$$. 
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221021/0.193.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221021/0.618.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


### Vortex Dipole
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221021/neg1.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    A vortex dipole are two point vortices with same strength but negative sign. Cusp motion appear at $$W=\phi$$, and the vortex dipole will escape from the boundary when $$W<1$$. 
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221021/1.618.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>



## Introduction

A single point vortex on the halfplane can be regarded as a vortex dipole that symmetric on the boundary $$(y=0)$$ in the full plane. Thus an $$N$$ point vortex system in the halfplane is equivalent to a $$2N$$ point vortex system in the full plane which are $$N$$ point vortices and their $$N$$ images.

The Green's function on the half-plane $$\mathbb{R}_+^2$$ is

$$
G_{\mathbb{R}^2_+}\left( {z,z'} \right) =  - \frac{1}{2\pi}\log ||z - z'||+\frac{1}{2\pi}\log ||z - z'^*||
$$

and the Hamiltonian is

$$
H=\frac{1}{4 \pi} \log \left(\left(2 y_1\right)^{\Gamma_1^2}\left(2 y_2\right)^{\Gamma_2^2}\left(\frac{\left(x_1-x_2\right)^2+\left(y_1+y_2\right)^2}{\left(x_1-x_2\right)^2+\left(y_1-y_2\right)^2}\right)^{\Gamma_1 \Gamma_2}\right)
$$

The first term represents the interaction between different vortices with their images; and the second term represents the interaction between a vortex and its image.

For the two point vortices system on the half plane, the Hamiltonian is
The motion of equations are

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
        {% include figure.liquid path="assets/img/posts/20221021/0.193.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221021/0.618.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221021/0.906.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221021/1.041.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

### Vortex Dipole
When two point vortices have opposite strength $$\Gamma_1=-\Gamma_2$$, we have the following four scenarios.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221021/0.911.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221021/1.345.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221021/1.542.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221021/1.618.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221021/1.932.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
