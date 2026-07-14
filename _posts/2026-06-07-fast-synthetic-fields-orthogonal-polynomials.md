---
layout: distill
title: Fast Synthetic Fields with Orthogonal Polynomials
description: Sampling smooth random fields and binary masks with controllable topology, using tensor products of orthogonal polynomials.
date: 2026-06-07
tags: polynomials sampling topology
categories: notes
giscus_comments: false
related_posts: false
authors:
  - name: Hanchun Wang
    url: "https://hch-wang.github.io/"
    affiliations:
      name: DAMTP, University of Cambridge
toc:
  - name: Why sample smooth fields?
  - name: Four polynomial bases
  - name: From fields to masks
  - name: How to use
_styles: >
  .fig-toggle {
    border: 1px solid var(--global-divider-color, #e6e6e6);
    border-radius: 8px;
    margin: 0.5rem 0 1.5rem;
    padding: 0 1rem;
  }
  .fig-toggle > summary {
    cursor: pointer;
    padding: 0.6rem 0;
    font-weight: 600;
    list-style: none;
  }
  .fig-toggle > summary::-webkit-details-marker { display: none; }
  .fig-toggle > summary::before { content: "▸  "; color: var(--global-theme-color, #b509ac); }
  .fig-toggle[open] > summary::before { content: "▾  "; }
  .fig-toggle[open] { padding-bottom: 0.8rem; }
---

## Why sample smooth fields?

We want a cheap, reproducible supply of smooth random fields on a grid — and, by thresholding, binary masks with controllable topology. Our use case: synthetic perturbations for training a topology-aware segmentation model (see the [demo]({{ '/projects/' | relative_url }})). Orthogonal polynomials make this easy.

## Four polynomial bases

Build a 2D field by tensoring two 1D bases, $f(x, y) = \sum_{ij} c_{ij}\, P_i(x)\, P_j(y)$, with random, seeded coefficients. Each basis gives a different texture — a few samples each, expand for more:

**Legendre**

{% include figure.liquid path="assets/img/posts/fast-syn/legendre_few.png" class="img-fluid rounded z-depth-1" alt="Legendre random-coefficient fields" %}

<details class="fig-toggle">
<summary>More Legendre examples</summary>
{% include figure.liquid path="assets/img/posts/fast-syn/legendre_more.png" class="img-fluid rounded z-depth-1" alt="More Legendre fields" %}
</details>

**Chebyshev**

{% include figure.liquid path="assets/img/posts/fast-syn/chebyshev_few.png" class="img-fluid rounded z-depth-1" alt="Chebyshev random-coefficient fields" %}

<details class="fig-toggle">
<summary>More Chebyshev examples</summary>
{% include figure.liquid path="assets/img/posts/fast-syn/chebyshev_more.png" class="img-fluid rounded z-depth-1" alt="More Chebyshev fields" %}
</details>

**Hermite** (probabilist's, $He_n$)

{% include figure.liquid path="assets/img/posts/fast-syn/hermite_few.png" class="img-fluid rounded z-depth-1" alt="Probabilist Hermite random-coefficient fields" %}

<details class="fig-toggle">
<summary>More Hermite examples</summary>
{% include figure.liquid path="assets/img/posts/fast-syn/hermite_more.png" class="img-fluid rounded z-depth-1" alt="More probabilist Hermite fields" %}
</details>

**Physicist's Hermite** ($H_n$)

{% include figure.liquid path="assets/img/posts/fast-syn/hermite_phys_few.png" class="img-fluid rounded z-depth-1" alt="Physicist Hermite random-coefficient fields" %}

<details class="fig-toggle">
<summary>More physicist's Hermite examples</summary>
{% include figure.liquid path="assets/img/posts/fast-syn/hermite_phys_more.png" class="img-fluid rounded z-depth-1" alt="More physicist Hermite fields" %}
</details>

A fresh $300 \times 300$ field takes about **14 ms** (≈ 70 per second) on a laptop, so a large batch is cheap.

## From fields to masks

Threshold a field to get a binary mask. Raising the order folds the level set more, adding more connected components and holes.

{% include figure.liquid path="assets/img/posts/fast-syn/binary_masks.png" class="img-fluid rounded z-depth-1" alt="Binary masks from thresholded Chebyshev fields" caption="Binary masks from thresholded Chebyshev fields (order 6); raising the order adds components and holes." %}

## How to use

```python
import numpy as np
from polysynth import Legendre, TensorPolynomial, random_coefficients

x = np.linspace(-1, 1, 300)
X, Y = np.meshgrid(x, x)

f = TensorPolynomial(Legendre(), random_coefficients((6, 6), normalize="l1", seed=0))
Z = f(X, Y)                                # smooth random field
mask = f.mask(X, Y, threshold=0.5)         # binary topology perturbation
```

Swap `Legendre()` for `Chebyshev()`, `Hermite()`, or `PhysicistsHermite()` to change the texture; raise the order for more topology.
