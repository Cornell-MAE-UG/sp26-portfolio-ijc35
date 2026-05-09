---
layout: project
title: Torque Wrench Analysis Using ANSYS 
description: Mechanics of Materials Final Torque Wrench Project
technologies: [MATLAB, Inventor, ANSYS]
image: /assets/images/normalstress.png
---

Designed a non-ratcheting, 3/8 inch drive instrumented torque wrench rated for 600 in-lbf. Torque was transduced using strain gauges bonded to the outer surfaces of the wrench at high strain locations. 

Learned how to use ANSYS via an FEM analysis of a provided ”baseline” design, used hand calculations to iterate the dimensions and material to meet all requirements, built a CAD model of the design, and then imported the CAD model to ANSYS. Once in ANSYS I performed the stress analysis, to ensure the design met the requirements and determined the torque wrench sensitivity.

___________________________________________________________________________________________________________________________

Project Design Requirements: 

- Attain at least 1.0 mV/V output at the rated torque of 600 in-lbf.
- Safety factor of Xo = 4 for yield or brittle failure
- Safety factor of XK = 2 for crack growth from an assumed crack of depth 0.04 inches
- Fatigue stress safety factor of XS = 1.5

Chosen Material: Al 7075 - T6
- Young's modulus = 11e6 psi
- Poisson's ratio = 0.33

Design improvements
- Lighter: 
	- Made of Aluminum rather than steel
	- Shorter by 2.5 inches


<!-- CAD Dimensions -->
<figure class="inline-image-l">
  <img src="{{ '/assets/images/drawing.png' | relative_url }}" alt="CAD drawing of torque wrench">
  <figcaption>CAD Dimensions of Torque Wrench</figcaption>
</figure>

<!-- Loads and Boundary Conditions -->
<figure class="inline-image-l">
  <img src="{{ '/assets/images/boundaryconditions.png' | relative_url }}" alt="Loads and boundary conditions applied to torque wrench">
  <figcaption>Loads and Boundary Conditions Applied</figcaption>
</figure>

<!-- Normal Strain Contours -->
<figure class="inline-image-l">
  <img src="{{ '/assets/images/normalstress.png' | relative_url }}" alt="Normal strain contours in strain gauge direction">
  <figcaption>
    Normal Strain Contours (in the Strain Gauge Direction) from FEM
  </figcaption>
</figure>

<!-- Maximum Principal Stress -->
<figure class="inline-image-l">
  <img src="{{ '/assets/images/maxprinc.png' | relative_url }}" alt="Maximum principal stress contour plot">
  <figcaption>Contour Plot of Maximum Principal Stress from FEM</figcaption>
</figure>

<!-- Maximum Normal Stress -->
<figure class="inline-image-l">
  <img src="{{ '/assets/images/maxnormalstress.png' | relative_url }}" alt="Maximum normal stress contour plot">
  <figcaption>Maximum Normal Stress</figcaption>
</figure>

<!-- Load Point Deflection -->
<figure class="inline-image-l">
  <img src="{{ '/assets/images/deflectiontw.png' | relative_url }}" alt="Load point deflection of torque wrench">
  <figcaption>Load Point Deflection</figcaption>
</figure>

<!-- Strain Gauge Results -->
<figure class="inline-image-l">
  <img src="{{ '/assets/images/tensionstraing.png' | relative_url }}" alt="tensile strain gauge">
  <figcaption>Strains at Strain Gauge Locations</figcaption>
</figure>

<!-- Text Results -->
<p>
  <strong>Calculated Torque Wrench Sensitivity:</strong> 1.107 mV/V
</p>

<p>
  <strong>Strain Gauge Selection:</strong><br>
  OMEGA Precision Linear Strain Gauge (7.6 × 5.8 mm)<br>
  Product Number: SGD-2/350-LY11
</p>







