---
layout: page
title: Dual gelations to synthesize core-shell hydrogel particles
description: making core-shell hydrogel particles for applications in oral drug delivery
img: assets/img/particle.png
importance: 1
category: work
related_publications: Attia2023-bc
---
This project, the first in my PhD, focused on figuring out a clever way to engineer core-shell hydrogel drug carrier particles. Core-shell particles are extremely useful in oral drug delivery. They can unlock sustained and delayed release profiles, which is important for instestinal and colonic targeting applications. They can also formulate fixed dosage combination (FDC) products, structuring different active ingredients in the core and the shell. Despite these useful applications, conventional methods for engineering core-shell carriers for pharmaceutical applications are limited, relying on organic solvents, high processing temperatures, and are often unable to structure drugs in the shell (see below). 
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/core_shell.PNG" title="table" class="img-fluid rounded z-depth-1 mx-auto d-block" %}
    </div>
</div>
<div class="caption">
    Digital microscopy image of a core-shell hydrogel particle.
</div>



<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/particle.png" title="Particle" class="img-fluid rounded z-depth-1 mx-auto d-block" %}
    </div>
</div>
<div class="caption">
    Digital microscopy image of a core-shell hydrogel particle.
</div>

You can also put regular text between your rows of images.
Say you wanted to write a little bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, *bled* for your project, and then... you reveal its glory in the next row of images.


<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>


The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

{% raw %}
```html
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
```
{% endraw %}
