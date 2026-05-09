---
layout: project
title: Massage Gun Dissection
description: Dissection and System Dynamics Analysis of Massage Gun
technologies: [System Dynamics, MATLAB]
image: /assets/images/halfbody.png
---

Dissected and analyzed a multi-function massage gun with three different mechanical heads.

We first created a block diagram for the system. The input is the voltage provided to the motor, and the output is the position of the end of the massage gun. The output we are focusing on is clearly shown below.
<!-- output -->
<figure class="inline-image-l">
  <img src="{{ '/assets/images/inputgun.png' | relative_url }}" alt="Input image">
  <figcaption>The red arrow denotes the output of the system, the linear position of the ball</figcaption>
</figure>

Once we knew the system input and output, the next step was filling in the steps in-between to map out the full process. 

<!-- block diagram -->
<figure class="inline-image-l">
  <img src="{{ '/assets/images/blockdiagram.png' | relative_url }}" alt="Input image">
  <figcaption>Block Diagram of System</figcaption>
</figure>

After creating the Block Diagram, we found the transfer function. 
### Transfer Functions

$$
G(s) = \frac{X(s)}{F(s)} = \frac{1}{m s^2 + b s + k}
$$

$$
G_m(s) = \frac{F(s)}{U(s)} = \frac{k_m}{\tau s + 1}
$$

The overall system is:
$$
X(s) = G(s)G_m(s)U(s) = \frac{k_m}{(\tau s + 1)(m s^2 + b s + k)}\, U(s)
$$
## Parameter Estimation

Next, we focused on identifying the unknown system parameters. The massage gun packaging provided several important motor specifications:

- **Rated voltage:** $V = 7.4\ \text{V}$
- **Motor power:** $P = 25\ \text{W}$
- **Rotation speed:** $\omega = 1800\ \text{rpm}$

The relationship between motor power and torque is given by:
$$
P = \tau \omega
$$

The motor torque is therefore:
$$
\tau = \frac{P}{\omega} = \frac{25}{188.5} = 0.133\ \text{N·m}
$$

The top section of the massage gun was removed and using calipers the peak-to-peak displacement of the output ball was measured to be $5\ \text{mm}$. This corresponds to a radius of:
$$
r = \frac{5}{2} = 2.5\ \text{mm} = 0.0025\ \text{m}
$$

Assuming an efficiency of $\eta = 0.9$, the force generated at the output is estimated as:
$$
F = \frac{\eta \tau}{r} = \frac{0.9 \times 0.133}{0.0025} = 47.88\ \text{N}
$$

The motor force constant is then approximated by:
$$
k_m = \frac{F}{V} = \frac{47.88}{7.4} = 6.47\ \text{N/V}
$$

These values are only rough approximations of the system. We are unable to calculate the real efficiency value, and are unsure if the parameters on the box can be applied to all massage gun settings. The only variables unknown are m, b, and k, which we found using a MATLAB script.

