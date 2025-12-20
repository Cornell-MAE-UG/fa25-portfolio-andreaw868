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

I then performed a control volume analysis on both setups (specifically around the cold water flow) to calculate the specific heat transfer rate, i.e. the heat transfer rate normalized by the mass transfer rate. In order to simplify the energy balance equation, I made the following assumptions:

1. **Steady-state operation.** This means that the energy balance equation equals zero. Aside from the very start when the water begins to flow and the very end when water stops flowing, the heat exchanger has input that matches its output.

2. **Change in kinetic and potential energy is negligible,** meaning the corresponding terms (velocity and height terms) equal zero. Although the water is piped in at a height above the table, the actual flow through the heat exchanger is flat.

3. **No work is done by the heat exchanger.** This means that the Ẇ term equals 0. This assumes no friction as the fluid moves through the heat exchanger, which is not true in real life, but since the distance that the fluid travels through the heat exchanger is relatively small, the work done by friction can be neglected.

4. **The heat exchanger is adiabatic.** This means that the Q̇ term equals 0.

5. **Mass flow rate of the cold fluid equals that of the hot fluid, and mass flow rate in equals mass flow rate out.** It would have been nice to measure the actual flowrates in the lab, but both fluids were pumped using the same diameter pipe, same pump, and roughly the same pipe setup (i.e., pipe draping up and down over the bucket, with no kinks); additionally, both fluids appeared to stop flowing at the same time. Therefore, we believe this assumption is roughly valid. This means that the ṁ_i and ṁ_e terms can be combined.

6. **Since liquid water is being analyzed, approximate h(T,p) as h_f(T),** since the enthalpy of liquid water does not depend strongly on pressure.


<p style="text-align:center;">
  <img src="{{ '/assets/images/heat_exchanger_calcs.jpg' | relative_url }}" style="max-width:100%; height:auto;">
</p>

The important values are summarized below:
- **Counter-flow setup:**
  - **`h_1,cf`** = 102.375 kJ/kg (specific enthalpy of exiting cold water)
  - **`h_2,cf`** = 29.40 kJ/kg (specific enthalpy of entering cold water)
  - **`Q̇_cf/ṁ_c`** = -78.56 kW/kg (specific heat transfer rate)

- **Parallel-flow setup:**
  - **`h_1,p`** = 21.824 kJ/kg (specific enthalpy of entering cold water)
  - **`h_2,p`** = 68.866 kJ/kg (specific enthalpy of exiting cold water)
  - **`Q̇_p/ṁ_c`** = -48.86 kW/kg (specific heat transfer rate)

For the counter-flow setup, the specific heat transfer rate was **72.98 kW/kg**, versus the parallel setup, which had a specific heat transfer rate of **47.04 kW/kg**. This was consistent with my intuition; for a parallel setup, the temperature difference between the two fluids decreases as both fluids flow side-by-side through the heat exchanger, leading to less heat transfer overall. 

To verify these values, I also performed a similar control volume analysis on the hot water flow, for both setups. If the heat exchanger is indeed adiabatic, I expect the Qdot value for the hot water flow to be equal and opposite to that of the cold water flow; physically this means that all heat lost by the hot water is transferred to the cold water. In reality, I expect these values to differ slightly because some heat lost by the hot water will be lost to the surroundings. 

<p style="text-align:center;">
  <img src="{{ '/assets/images/heat_exchanger_calcs2.jpg' | relative_url }}" style="max-width:100%; height:auto;">
</p>

The important values are summarized below:
- **Counter-flow setup:**
  - **`h_3,cf`** = 178.01 kJ/kg (specific enthalpy of entering hot water)
  - **`h_4,cf`** = 99.446 kJ/kg (specific enthalpy of exiting hot water)
  - **`Q̇_cf/ṁ_h`** = -78.56 kW/kg (specific heat transfer rate)

- **Parallel-flow setup:**
  - **`h_3,p`** = 148.77 kJ/kg (specific enthalpy of entering hot water)
  - **`h_4,p`** = 99.914 kJ/kg (specific enthalpy of exiting hot water)
  - **`Q̇_cf/ṁ_h`** = -48.86 kW/kg (specific heat transfer rate)

As expected, the magnitude of the heat transfer rate leaving the hot water exceeds that entering the cold water, indicating heat loss to the surroundings. To quantify this heat loss, I subtracted the magnitudes of both heat transfer rates: `(Q̇_loss / ṁ) = |Q̇_hot / ṁ_hot| - |Q̇_cold / ṁ_cold|.` This resulted in Q̇_loss/ṁ values of **5.58 kW/kg** (counter-flow) and **1.82 kW/kg** (parallel). Then, I compared the rate of heat loss to the surroundings to the heat transfer rate leaving the hot water to obtain heat loss percentages of **7.1%** (counter-flow) and **3.7%** (parallel). 

Counter-flow setups are more effective in terms of the heat gained by the cold water, as calculated earlier; this is because they maintain a larger temperature gradient throughout operation -- the hot water stays hotter for longer and the cold water stays colder for longer. However, they are less thermodynamically efficient i.e. they have a higher heat loss percentage for the same reason. Heat loss to surroundings is driven by convection, which is described by the following equation: `Q_loss = hA(T_fluid-T_amb)`. In counter-flow setups, the fluid and wall temperatures remain higher over a larger portion of the exchanger length, which increases the average temperature difference between the fluid and the surroundings. As a result, more heat is lost to the environment compared to parallel-flow setups, where the temperature difference decreases more rapidly along the length. 

After revisiting my analysis, I also wanted to double check assumption 6. This assumption is typically used for water that is close to saturation, but the water used in this lab was clearly well within the compressed/supercooled liquid water regime, so using Q = mc_p(T_f-T_i) would have been easier and more accurate. Using `Q̇/ṁ = c_p(T-f-T_i)`, I recalculated the specific heat transfer rates for both setups with c_p = 4.18 kJ/(kg K)

Sources used: Table A-2. Properties of Saturated Water (Liquid–Vapor): Temperature Table. From Fundamentals of Engineering Thermodynamics, Moran et al.