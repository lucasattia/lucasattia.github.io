---
layout: page
title: how can we control drug nanoparticle crystallinity? 
description: understanding drug nanoparticle structure using molecular simulations
img: assets/img/md.png
importance: 2
category: work
related_publications: Attia2024-qn
---

This paper was the second in my PhD, and was a really exciting foray into using molecular dynamics simulations to understand material systems. A previous PhD student had observed that when we make drug nanoparticles using the technology my group has developed, the 'crystallinity' (or percentage of the nanoparticle that is crystalline vs. amorphous, see the image below) was extremely difficult to control. 

{% include figure.html path="assets/img/crystallinity.png" title="Crystallinty" class="img-fluid rounded z-depth-1 mx-auto d-block" %}


Crystallinity is crucial to drug formulation because it impacts how quickly a drug dissolves, which directly affects its bioavailability—the extent to which the active drug is absorbed and becomes available in the body. So, the lack of control we observed experimentally posed a challenge that we wanted to understand and ultimately mitigate. Since we were looking at molecular-scale interactions, I turned to molecular dynamics simulations (using GROMACS) to understand what interactions governed this behavior. We modeled our system by building a nanocrystal surface of our drug, then treating that surface with different ratios of excipients.

{% include figure.html path="assets/img/simulate.png" title="simulation" class="img-fluid rounded z-depth-1 mx-auto d-block" %}

We looked at how the structure of the nanocrystal responded to these different treatments to understand the molecular-level driver of crystallinity in these nanoparticles. One of my favorite parts of this project is the crystallinity metric we defined to quantify the degree of crystallinity in the simulation. This was a challenging task, and no one has really established a good way to do this. We decided to base the metric from the [RMSD](https://www.compchems.com/what-is-the-rmsd-and-how-to-compute-it-with-gromacs/)- which basically describes the amount of deviation of the atoms in the nanoparticle from their original lattice positions. We time-average the RMSD (since it can vary quite rapidly during the simulation), and normalize the value for any given simulation against the minimum deviation (RMSD for a simulation with no excipients), and the maximum deviation (the spacing between molecules in the lattice). This is summarized in the equation below. \
$$
\Gamma_{\text{effective}}= \frac{\frac{a}{2} - \langle \text{RMSD} \rangle}{\frac{a}{2} - \langle \text{RMSD}_{0} \rangle}
$$\
We discovered that two phenomena drive the crystallinity result of the surface. First, we find that the surfactant and polymer excipients we use experimentally compete at the interface, since both are surface active. However, since the surfactant is more surface active, it can outcompete the polymer, even at low concentrations, and 'protect' the surface from de-stabilizing polymer interactions. Additionally, the surfactant and polymer can themselves complex (a [well-studied phenomena in soft materials](https://pubs.acs.org/doi/pdf/10.1021/la00022a026?casa_token=kONkmMNElfcAAAAA:Yj3PE_TvPQXbxuhaA8STo8VxnfCAplcXX3S5bkmY6juMhgh7LOix7kS9x4aWR7PNMEDSEpahSETJLg)), which de-localizes the polymer from the drug surface, and prevents it from disrupting the crystal structure and amorphizing the surface. 

