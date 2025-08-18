---
layout: page
title: fastsolv
description: developing accurate cheminformatics models for solubility prediction 
img: assets/img/fastsolv.PNG
importance: 3
category: work
related_publications: attia2024organic
---

Most of my thesis is motivated by poor aqueous solubility of hydrophobic drugs. However, organic solubility is also a crucial property, particularly for synethic/process chemistry and formulation processing. Measuring solubility accurately is extremely challenging, and experimental variability is high. 
Despite its importance, solubility is notoriously difficult to predict. There has been an enormous amount of work in making a good predictor for aqueous solubility (due to its relevance in drug function), and some tools have been quite successful. However, organic solubility has been comparatively neglected. We sought to create an accurate and accessible tool for the community to use. 

 We used standard deep learning cheminformatics models ([chemprop](https://github.com/chemprop/chemprop) and [fastprop](https://github.com/JacksonBurns/fastprop)), and trained them on large datasets in the litetature. 
 One cool training technique; we trained on the solubility loss and the loss of the gradient of solubility with respect to temperature (see equation below). This is a very general approach called [Sobolev training](https://arxiv.org/abs/1706.04859), which can be adapted for any DL problem where you care about the accuracy of the gradient of your target value with respect to an input (temperature, pH, concentration, etc). 

 $$
\mathcal{L}(\hat S, S)
= \frac{1}{n} \sum_{i=1}^n
\left[
\left( \log S_i - \log \hat{S}_i \right)^2
+ \alpha \left(
\frac{d\, \log S_i}{d T_i}
-
\frac{d\, \log \hat{S}_i}{d T_i}
\right)^2
\right].
$$

The combination of this training approach, great model architectures, and compiled literature datasets gave us state-of-the-art performance. We rigorously show that our models achieve average accuracy that approaches the limit of experimental variability, the noise floor of the measurements themselves. Excitingly, our model (fastsolv) is quickly being adopted in industry, most notably by [Rowan Scientific](https://rowansci.com/tools/solubility) ([docs here](https://docs.rowansci.com/science/workflows/solubility)). We’ve also released an [open-source deployment of FastSolv](http://fastsolv.mit.edu/), making it accessible to the broader community for both research and practical applications. 
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/fastsolv.PNG" title="Solubility prediction" class="img-fluid rounded z-depth-1 mx-auto d-block" %}
    </div>
</div>
<div class="caption">
    Deployed model GUI
</div>

This project started as a class project in an [MIT ML course](https://computing.mit.edu/cross-cutting/common-ground-for-computing-education/common-ground-subjects/c01-c51-modeling-machine-learning/), so it's been awesome to see it develop into a useful tool for the community. 
