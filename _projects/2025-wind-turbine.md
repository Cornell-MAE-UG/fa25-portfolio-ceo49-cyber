---
layout: project
title: Wind Turbine (MAE 4272)
description: Optimized wind turbine blades for a low reynolds number
technologies: [Fusion 360, MATLAB, 3D-Printing]
image: /assets/images/wind-turbine.jpg
---

In this project, we were asked to design wind turbine blades that fit a fixed hub connection geometry. The blades were optimized for performance at a constant RPM and wind speeds following a Weibull distribution with parameters c = 5 and k = 5. While significant research exists on optimizing large-scale wind turbines, small-scale systems still lack blades tailored for low-speed operation, motivating this design effort.

The first major design decision was selecting a target RPM. Based on laboratory observations and the probability distribution of wind speeds, we chose a target RPM of 800, as this speed was expected to occur most frequently across the relevant wind conditions. We then selected the NACA 4412 airfoil due to its simple geometry and strong performance at low Reynolds numbers. After researching common wind turbine blade design approaches, we implemented equations from blade element theory.

<img src="{{ '/assets/images/bet.png' | relative_url }}" width="600">

We developed a MATLAB script that used these equations along with the target RPM, airfoil parameters, and other constant values to generate the optimal chord and pitch distributions. After validating the structural integrity of the design using analysis methods developed in Lab 5, the blades were modeled in Fusion 360 and prepared for manufacturing.

<img src="{{ '/assets/images/geometry.png' | relative_url }}" width="600">

With the blades fabricated, we tested their performance to determine whether the optimization was successful. Testing was conducted in the Big Blue Wind Tunnel by systematically increasing the fan frequency and collecting power curves at each wind speed. At each condition, torque was applied using a torque brake as the turbine slowed from free speed to stall, while data were collected on applied torque, rotational speed, and power output. This process was repeated for each wind speed.

<img src="{{ '/assets/images/power_curve.png' | relative_url }}" width="600">

The resulting RPM versus power curves were analyzed in MATLAB and interpolated at the target RPM to produce a relationship between power and wind velocity. The final step involved integrating this power–velocity curve multiplied by the Weibull distribution across the valid operating range to estimate the expected power output. Although the design did not achieve the power levels originally predicted, it outperformed the turbines tested in class, operated near the intended optimal RPM, and satisfied all design constraints.

<img src="{{ '/assets/images/weibull-overlay.png' | relative_url }}" width="600">

My primary contribution to this project focused on testing and data analysis. I developed the testing protocols and processed the experimental data to compute the expected power output.












