---
layout: distill
title: A soliton of Burgers' equation?
description: A soliton of Burgers' equation?
img: assets/img/posts/20251015/waterfall_plot_combined.png
importance: 1
category: work
---

# import all gifs from assets/img/posts/20251015/

<div class="row">
  {% assign gif_files = site.static_files | where: "path", "contains", "assets/img/posts/20251015/" %}
  {% for file in gif_files %}
    {% if file.extname == ".gif" %}
      <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path=file.path title="example image" class="img-fluid rounded z-depth-1" %}
      </div>
    {% endif %}
  {% endfor %}
</div>
