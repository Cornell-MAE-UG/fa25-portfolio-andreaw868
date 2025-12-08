---
layout: project
title: Heat Exchanger Lab
description: Analysis of a Real-Life Thermodynamic System
technologies: [Hand Calcs - Control Volume Analysis]
image: /assets/images/heat_exchanger.jpg
permalink: /projects/heat-exchanger-lab/
---

<br style="clear: both;" />
For this lab, I analyzed a heat exchanger, applying the concepts that I learned in ENGRD2210 (Thermodynamics). Using a control volume analysis, I performed hand calculations to compare the performance of the heat exchanger under two different setups: counter-flow and parallel.

Description of device: A heat exchanger is a thermodynamic device that transfers heat between two fluids at different temperatures flowing through separate channels to prevent mixing. Heat exchangers have a wide range of applications, including in HVAC systems to heat/cool buildings, cooling automotives, and in the Rankine cycle.

The schematics for both setups are illustrated below:
![Schematics for setups]({{ "/assets/images/heat_exchanger_schematic.jpg" | relative_url }}){: .inline-image-l}

<br style="clear: both;" />

I then performed a control volume analysis on both setups to calculate the specific heat transfer rate i.e. the heat transfer rate normalized by the mass transfer rate. In order to simplify the energy balance equation, I made the following assumptions:
1) Steady-state operation. This means that the energy balance equation equals zero. Aside from the very start when the water begins to flow and the very end when water stops flowing, the heat exchanger has input that matches its output.
2) Change in kinetic and potential energy is negligible, meaning the corresponding terms (velocity and height terms) equal zero. Although the water is piped in at a height above the table, the actual flow through the heat exchanger is flat. 
3) No work is done by the heat exchanger. This means that the W dot term equals 0. This assumes no friction as the fluid moves through the heat exchanger, which is not true in real life, but since the distance that the fluid travels through the heat exchanger is relatively small, the work done by friction can be neglected.
4) The heat exchanger is adiabatic. This means that the Q dot term equals 0. 
5) The mass flow rate of the cold fluid equals that of the hot fluid, and mass flow rate in equals mass flow rate out. It would have been nice to measure the actual flowrates in the lab, but both fluids were pumped using the same diameter pipe, same pump, and roughly the same pipe setup (i.e. pipe draping up and down over the bucket, with no kinks); additionally, both fluids appeared to stop flowing at the same time. Therefore, we believe this assumption is roughly valid. This means that the m dot i and m dot e terms can be combined.
6) Since liquid water is being analyzed, approximate h(T,p) as h_f(T), since the enthalpy of liquid water does not depend strongly on pressure. 

<p style="text-align:center;">
  <img src="{{ '/assets/images/heat_exchanger_calcs.jpg' | relative_url }}" style="max-width:100%; height:auto;">
</p>

For the counter-flow setup, the specific heat transfer rate was 72.98 kJ/kg, versus the parallel setup, which had a specific heat transfer rate of 47.04 kJ/kg. This was consistent with my intuition; for a parallel setup, the temperature difference between the two fluids decreases as both fluids flow side-by-side through the heat exchanger, leading to less heat transfer overall. 

