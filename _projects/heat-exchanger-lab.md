---
layout: project
title: Heat Exchanger Lab
description: Analysis of a Real-Life Thermodynamic System
technologies: [Hand Calcs - Control Volume Analysis]
image: /assets/images/heat_exchanger.jpg
---

<br style="clear: both;" />
For this lab, I analyzed a heat exchanger, applying the concepts that I learned in ENGRD2210 (Thermodynamics). Using a control volume analysis, I performed hand calculations to compare the performance of the heat exchanger under two different setups: counter-flow and parallel.

Description of device: A heat exchanger is a thermodynamic device that transfers heat between two fluids at different temperatures flowing through separate channels to prevent mixing. Heat exchangers have a wide range of applications, including in HVAC systems to heat/cool buildings, cooling automotives, and in the Rankine cycle.

The schematics for both setups are illustrated below:
![Schematics for setups]({{ "/assets/images/heat_exchanger_schematic.jpg" | relative_url }}){: .inline-image-l}

<br style="clear: both;" />

I then performed a control volume analysis on both setups to calculate the specific heat transfer rate.
<p style="text-align:center;">
  <img src="{{ '/assets/images/heat_exchanger_calcs.jpg' | relative_url }}" style="max-width:100%; height:auto;">
</p>

For the counter-flow setup, the specific heat transfer rate was 72.98 kJ/kg, versus the parallel setup, which had a specific heat transfer rate of 47.04 kJ/kg. This was consistent with my intuition; for a parallel setup, the temperature difference between the two fluids decreases as both fluids flow side-by-side through the heat exchanger, leading to less heat transfer overall. 

