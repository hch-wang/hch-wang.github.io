---
layout: page
title: Motility-Induced Phase Separation
description: How self-propelled particles aggregate without attractive forces.
img: assets/img/posts/20221018/detail.png
importance: 2
category: research
mathjax: yes
---
## Summary
This project studies how [active Brownian particles](https://en.wikipedia.org/wiki/Active_Brownian_particle)
aggregate even when no attractive interaction is present.

**Videos of my results in Motility Induced Phase Separation:**

MIPS cluster formation [YouTube](https://youtu.be/Mi5pbJ8jI4s) <br>
MIPS cluster merging [YouTube](https://youtube.com/shorts/JxTgIvu2Sv8?feature=share) <br>
MIPS cluster dissolution [YouTube](https://youtube.com/shorts/m9tW2ULBz_s?feature=share) <br>

**Voronoi tessellation of a MIPS cluster:**
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221018/fig2.png" alt="Voronoi tessellation of a motility-induced phase separation cluster" title="Voronoi tessellation of a MIPS cluster" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Voronoi tessellation of a dense MIPS cluster.
</div>

**Adjacency graph of a MIPS cluster:**
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221018/fig3.png" alt="Adjacency graph derived from a MIPS cluster" title="Adjacency graph of a MIPS cluster" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Adjacency graph derived from the same particle configuration.
</div>


## Introduction
From [cytoskeletal filaments](https://en.wikipedia.org/wiki/Cytoskeleton) and bacterial colonies to
[bird flocks](https://en.wikipedia.org/wiki/Flocking_(behavior)) and fish schools, many biological systems consume
energy from their surroundings to sustain organized motion. That continual energy input allows them to maintain
non-equilibrium steady states rather than relaxing immediately toward equilibrium.

One of the minimal models to study active matter is the active Brownian particles
model (ABP model). In the ABP model, particles are colloidal spheres. Particles
are governed by [Langevin’s equation](https://en.wikipedia.org/wiki/Langevin_equation) that particles can self-propel themselves by absorbing
and converting energy from the environment. This is one of the simplest
forms of activity; nevertheless, even this minimal ingredient is enough to produce rich non-equilibrium behavior.
Particles can aggregate into clusters without any attractive mechanism, a phenomenon known as
motility-induced phase separation (MIPS).

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/posts/20221018/overprocess.png" alt="Stages in the formation of a MIPS cluster" title="Cluster formation in MIPS" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Successive stages in the formation of a particle cluster.
</div>




## Dynamics
The overdamped Langevin dynamics are given by

<p style="text-align:center">
$$
\left\{\begin{split}
\boldsymbol{\dot r_i} &= \frac{1}{\gamma }\boldsymbol{F_i} + {v_p}\boldsymbol{\hat n_i} + \sqrt {2D} {\eta _i}\\
{\dot \theta }_i &= \sqrt {2{D_R}} {\xi _i}
\end{split}\right.
$$
</p>

Here, $F_i=-{\nabla _r}\sum_j {V_j}\left( r_i \right)$ is the total force acting on particle
$i$. $\vec{\hat n}$ is its self-propulsion direction, $D$ is the translational diffusion constant, and $D_R$
is the rotational diffusion constant. The random variables $\xi, \eta \sim \mathcal{N}(0,1)$ represent independent
Gaussian white noise terms.

The potential is 
<p style="text-align:center">
$$
V(r)=4\varepsilon\left[\left(\frac{\sigma}{r}\right)^{12}-\left(\frac{\sigma}{r}\right)^6+\frac{1}{4}\right] 
\Theta\left(\sigma_*-|r|\right)
$$
</p>

The underdamped dynamics are given by
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
        {% include figure.liquid path="assets/img/posts/20221018/voidistri2.png" alt="Bimodal density distribution in a MIPS system" title="Bimodal density distribution" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Bimodal particle-density distribution associated with phase separation.
</div>
