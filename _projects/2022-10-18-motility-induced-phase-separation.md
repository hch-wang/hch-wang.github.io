---
layout: page
title: Motility Induced Phase Separation
description: How do particles aggregate without any attracting force?
img: assets/img/posts/20221018/detail.png
importance: 2
category: work
mathjax: yes
---
    
    ---
    layout: post
    read_time: true
    show_date: true
    title:  Motility Induced Phase Separation
    date:   2022-10-18 13:32:20 -0000
    description: Motility Induced Phase Separation in Active Brownian Particle System.
    img: posts/20221018/detail.png
    tags: [Stochastic Process, Scientific Computation]
    author: Hanchun Wang
    category: project
    github:  
    mathjax: yes
    ---

## Summary
In this [Active Brownian Particle](https://en.wikipedia.org/wiki/Active_Brownian_particle) system, 
particles will aggregate without any attracting force inbetween.

**Vidoes of my results in Motility Induced Phase Separation:**

MIPS cluster formation [YouTube](https://youtu.be/Mi5pbJ8jI4s) <br>
MIPS cluster merging [YouTube](https://youtube.com/shorts/JxTgIvu2Sv8?feature=share) <br>
MIPS cluster dissolution [YouTube](https://youtube.com/shorts/m9tW2ULBz_s?feature=share) <br>

**Voronoi tessellation of a MIPS cluster:**
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221018/fig2.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Voronoi tessellation
</div>

**Adjacency graph of a MIPS cluster:**
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221018/fig3.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Adjacency matrix
</div>


## Introduction
From [cytoskeletal filaments](https://en.wikipedia.org/wiki/Stromatolite) and bacterial aggregation to 
the [birds’ flock](https://en.wikipedia.org/wiki/Flocking_(behavior)) and fish school, biological agents consume energy from the environment to sustain different
kinds of activities. The activity provides agents the capacity to have steady states
away from the equilibrium. This capacity against the 
[maximum entropy](https://en.wikipedia.org/wiki/Principle_of_maximum_entropy#:~:text=The%20principle%20of%20maximum%20entropy,proposition%20that%20expresses%20testable%20information).) is the key
to understanding the mystery of why biological creatures can live for decades.

One of the minimal models to study active matter is the active Brownian particles
model (ABP model). In the ABP model, particles are colloidal spheres. Particles
are governed by [Langevin’s equation](https://en.wikipedia.org/wiki/Langevin_equation) that particles can self-propel themselves by absorbing
and converting energy from the environment. This is one of the simplest
forms of activity, however, previous research has shown that simple activeness is
enough to achieve steady non-equilibrium states in the system. Particles will aggregate
into clusters without any presence of attracting mechanisms and this phenomenon
is called motility-induced phase separation (MIPS).

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221018/overprocess.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Process of the formation of cluster
</div>




## Dynamics
The over-damped Langevin's dynamics is given as

<p style="text-align:center">
$$
\left\{\begin{split}
\boldsymbol{\dot r_i} &= \frac{1}{\gamma }\boldsymbol{F_i} + {v_p}\boldsymbol{\hat n_i} + \sqrt {2D} {\eta _i}\\
{\dot \theta }_i &= \sqrt {2{D_R}} {\xi _i}
\end{split}\right.
$$
</p>

Where $F_i=-{\nabla _r}\sum_j {V_j}\left( r_i \right) $ is the total force given by all the particles to the particle 
$i$. $\vec{\hat n}$ is the self-propelling direction of the particle. $D$ is the transitional diffusion constant, $D_R$ 
is the rotational diffusion constant. $\xi, \eta \sim \mathcal{N}(0,1)$ are independent stochastic variables under the 
multidimensional Gaussian white noise.

The potential is 
<p style="text-align:center">
$$
V(r)=4\varepsilon\left[\left(\frac{\sigma}{r}\right)^{12}-\left(\frac{\sigma}{r}\right)^6+\frac{1}{4}\right] 
\Theta\left(\sigma_*-|r|\right)
$$
</p>

The under-damped dynamics is given as
<p style="text-align:center">
$$
\left\{\begin{aligned}
\boldsymbol{\ddot r_i} &=-\gamma_T \boldsymbol{\dot{r}_i}
+\boldsymbol{F_i}
+\gamma_T v_p \boldsymbol{\hat{n}_i}
+\sqrt{2 D_T} \gamma_T \eta_i \\
\ddot{\theta}_i &=-\gamma_R \dot{\theta}_i+\sqrt{2 D_R} \gamma_R \xi_i
\end{aligned}\right.
$$
</p>

## Voronoi Tessellation

The local density in the system can be studied by the [Voronoi Tessellation](https://en.wikipedia.org/wiki/Voronoi_diagram)

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221018/voidistri2.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Bimodal distribution of particles' density
</div>
