---
layout: cv
permalink: /cv/
title: cv
nav: true
navorder: 1
years: [2022,2021]
cv_pdf: Hanchun_Wang_CV.pdf
---

[//]: # ([pdf]&#40;../assets/pdf/Hanchun_Wang_CV.pdf&#41;)

<div class="publications">

{% for y in page.years %}
<h2 class="year">{{y}}</h2>
{% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>