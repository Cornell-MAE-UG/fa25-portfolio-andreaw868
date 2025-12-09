---
layout: project
title: Torque Wrench Design
description: I designed a torque wrench for my materials of engineering class, in order to meet several requirements, including sensitivity and safety factors against yield, crack propagation, and fatigue stress.
technologies: [MATLAB, SolidWorks, ANSYS]
image: /assets/images/torque_wrench.jpg
---

<div style="clear: both;"></div>

For this project, I learned how to perform finite element analysis on a design in ANSYS. The design process began with a simple, rectangular prism geometry fixed at one end. Using hand calculations, I calculated deflection at the free end, strain at a specified location (representing where a strain gauge would be located) and the max bending stress in the torque wrench. I created a simple MATLAB script to take material properties (E, K_IC, yield strength, fatigue strength, Poisson's ratio) and geometric properties of the beam as inputs, and outputted safety factors against yield, crack propagation, fatigue, and the strain sensitivity at the strain gauge.

After modifying some parameters to better understand how this affected the resulting safety factors and identifying which areas needed improvement, I designed my own torque wrench. The CAD was done in SolidWorks. The baseline design did not have enough strain sensitivity, so I added a narrower neck region in the handle to reduce the moment of inertia in this region, thus increasing the measured strain. Additionally, I created smoother curves and added fillets to reduce stress concentrations. 

To validate my design, I used ANSYS to identify the maximum stress in the torque wrench and the strain at the strain gauge location. I then used this maximum stress value (which was larger than the stress computed using hand calculations/beam theory) in my computation of safety factors, which satisfied all requirements.

See the design and analysis in the following pdf: 
<iframe
    src="{{ '/assets/MAE3270_FinalHW_Part2.pdf' | relative_url }}"
    style="width:100%; height:900px; border:none;"
></iframe>



