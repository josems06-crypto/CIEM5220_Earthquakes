4) Perform a dynamic time history analysis with one set of input accelerations derived in question (1) along the principal directions. You are free to choose any set of triaxial motions (from the list provided) as well as the directions in which you apply the motions in the horizontal plane. Please report the following:
a) Substantiate your choice as to directions in which you apply the horizontal components of the ground excitation. You are not asked to perform multiple seismic analysis here but simply to explain your choice.

A computational routine was developed to construct the Elastic Response Spectra (ERS) for each principal direction of the unscaled ground motions. The algorithm applies a peak ground acceleration (PGA) scaling factor in accordance with the target design spectrum, defined by a structural damping ratio of 4.2%. The time-domain signals were converted into the frequency domain using numerical integration, yielding the Spectral Acceleration ($SA$) as a function of the natural period ($T_n$). This allows for a direct comparison between the energy demands of the earthquakes and the resonant frequencies of the structure.

The response spectra of the 5 scaled acceleration signals along principal directions are derived in ERS.ipynb. From which we can observe that the response spectra is almost identical for Horizontal 1 and Horizontal 2, and all 5 sets show a peak between a natural period of roughly 0.3~0.5 [s]. 


After conducting modal analysis of our selected structure in RFEM6, we get natural frequencies for the first 20 modes, and their corresponding modal effective modal masses: 
| Mode No. | Eigenvalue $\lambda$ [1/s2] | Angular Frequency $\omega$ [rad/s] | Natural Frequency f [Hz] | Natural Period T [s] |
| :---: | :---: | :---: | :---: | :---: |
| 1 | 48.197 | 6.942 | 1.105 | 0.905 |
| 2 | 517.409 | 22.747 | 3.620 | 0.276 |
| 3 | 581.827 | 24.121 | 3.839 | 0.260 |
| 4 | 645.010 | 25.397 | 4.042 | 0.247 |
| 5 | 856.589 | 29.268 | 4.658 | 0.215 |
| 6 | 859.694 | 29.321 | 4.667 | 0.214 |
| 7 | 867.821 | 29.459 | 4.689 | 0.213 |
| 8 | 867.896 | 29.460 | 4.689 | 0.213 |
| 9 | 880.249 | 29.669 | 4.722 | 0.212 |
| 10 | 1109.195 | 33.305 | 5.301 | 0.189 |
| 11 | 1970.273 | 44.388 | 7.065 | 0.142 |
| 12 | 2009.466 | 44.827 | 7.134 | 0.140 |
| 13 | 2076.892 | 45.573 | 7.253 | 0.138 |
| 14 | 2840.611 | 53.297 | 8.483 | 0.118 |
| 15 | 3992.454 | 63.186 | 10.056 | 0.099 |
| 16 | 4368.107 | 66.092 | 10.519 | 0.095 |
| 17 | 4612.659 | 67.917 | 10.809 | 0.093 |
| 18 | 4902.118 | 70.015 | 11.143 | 0.090 |
| 19 | 9470.390 | 97.316 | 15.488 | 0.065 |
| 20 | 10404.063 | 102.000 | 16.234 | 0.062 |
| Mode No. | Modal Mass Mi [kg] | meX | meY | meZ | me$\Phi$X | me$\Phi$Y | me$\Phi$Z |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 1 | 6127.3 | 5.2 | 24702.8 | 0.5 | 91571.35 | 4.31 | 27776.07 |
| 2 | 7458.7 | 2155.6 | 6932.2 | 12.8 | 17729.81 | 6452.21 | 90448.72 |
| 3 | 12136.6 | 30157.8 | 603.3 | 95.6 | 78.72 | 99799.11 | 5690.78 |
| 4 | 4496.0 | 306.8 | 2225.4 | 0.6 | 201922.25 | 1629.54 | 7648.73 |
| 5 | 1524.5 | 0.3 | 96.9 | 0.0 | 3536.69 | 1.97 | 1.30 |
| 6 | 538.5 | 0.8 | 18.2 | 0.1 | 4.37 | 5.80 | 168.07 |
| 7 | 771.4 | 0.0 | 0.0 | 0.0 | 0.01 | 0.00 | 0.00 |
| 8 | 769.4 | 0.0 | 0.0 | 0.0 | 0.09 | 0.01 | 0.00 |
| 9 | 575.0 | 3.9 | 39.4 | 0.4 | 816.20 | 39.42 | 1367.01 |
| 10 | 2506.2 | 0.0 | 1463.0 | 3.4 | 26009.69 | 40.26 | 265.18 |
| 11 | 434.2 | 0.3 | 557.3 | 48.1 | 37897.00 | 687.61 | 91.16 |
| 12 | 430.0 | 0.5 | 73.8 | 80.6 | 5123.96 | 499.46 | 6.66 |
| 13 | 2596.8 | 11.5 | 0.0 | 9348.7 | 1056.77 | 9903.99 | 4.38 |
| 14 | 1842.8 | 358.9 | 0.1 | 62.9 | 35.20 | 34636.90 | 13.05 |
| 15 | 1630.3 | 34.2 | 0.0 | 303.4 | 24.49 | 512.92 | 0.15 |
| 16 | 4829.9 | 264.1 | 488.9 | 1.3 | 16358.26 | 21451.75 | 2334.22 |
| 17 | 7304.4 | 2853.2 | 333.8 | 10.2 | 20169.66 | 241885.02 | 584.93 |
| 18 | 5318.4 | 524.4 | 785.8 | 5.3 | 65369.74 | 44201.63 | 9962.05 |
| 19 | 1212.7 | 192.0 | 0.0 | 473.0 | 37.61 | 9900.42 | 30.22 |
| 20 | 727.7 | 0.6 | 1.0 | 777.0 | 106.22 | 159.24 | 30.60 |
| $\Sigma$ | 63230.8 | 36870.1 | 38321.9 | 11223.7 | 487848.09 | 471811.56 | 146423.28 |
| $\Sigma$M | | 40234.6 | 40234.6 | 40234.6 | 601259.56 | 689900.75 | 157708.06 |
| % | | 91.64 | 95.25 | 27.90 | 81.14 | 68.39 | 92.84 |

From which we can see that the x-axis is governed by mode 3 and the y-axis by mode 1, according to the dominant modal mass contribution compared to the other modes. Mode 3, governing for the x-axis has a fundamental period of 0.26[s] and an effective modal mass of 30157.8[kg]. Mode 1, governing for the y-axis has a fundamental period of 0.905[s] and an effective modal mass of 24702.8[kg]. 

We set these two fundamental periods into the derived response spectra. 
![ERS_Q4_1.png](ERS_Q4_1.png)
![ERS_Q4_2.png](ERS_Q4_2.png)

The selection of the critical ground motion was dictated by the spectral demands at these specific periods. An analysis of the generated response spectra revealed that the structural period of the Y-axis ($0.905 \text{ s}$) falls within the long-period, low-acceleration region for all five earthquake sets. Consequently, the critical loading scenario is governed entirely by the X-axis.

Set 3 was selected because its horizontal components exhibit maximum spectral acceleration of 1.916[g] precisely at the $0.260 \text{ s}$ mark. To induce the most severe internal forces, the strongest horizontal component of Set 3 (Horizontal 1) was aligned with the structure's X-axis, forcing the stiffest lateral resisting system to absorb the peak inertial energy. The orthogonal, slightly weaker component (Horizontal 2) was applied simultaneously to the Y-axis.


b) Determine the maximum displacements and stresses as well as their critical locations and explain why the chosen locations are considered critical.

The time history analysis was conducted with the two horizontal excitations inputted accordingly into the corresponding x and y axes in an accelerogram. Implementing the linear modal analysis rather than linear implicit Neumark to save computational time. The time step was 0.01[s] with split saved time steps of 10. 

The maximum displacement resulting from the time history analysis are as follows: 
| Description | Value | Unit | Notes |
| :--- | :--- | :--- | :--- |
| Maximum displacement in X-direction | -22.42 | mm | Member No. 100, x: 3.170 m |
| Maximum displacement in Y-direction | -83.00 | mm | Member No. 269, x: 1.150 m |
| Maximum displacement in Z-direction | 6.13 | mm | Member No. 218, x: 3.886 m |
| Maximum vectorial displacement | 85.25 | mm | Member No. 100, x: 3.170 m |
| Maximum rotation about X-axis | 36.88 | mrad | Member No. 476, x: 0.000 m |
| Maximum rotation about Y-axis | 2.81 | mrad | Member No. 5, x: 0.000 m |
| Maximum rotation about Z-axis | -14.28 | mrad | Member No. 267, x: 1.429 m |

The maximum deformation for both X and Y were observed at the roof members. This makes sense because structural deflections compound upward. The free end of the global cantilever experiences the summation of the inter-story drifts from all lower levels, resulting in maximum absolute displacement at the highest elevation.

Although the structure was subjected to extreme spectral acceleration along its X-axis ($T_x = 0.260 \text{ s}$) and relatively low acceleration along its Y-axis ($T_y = 0.905 \text{ s}$), the recorded displacement in the Y-direction was approximately four times larger than in the X-direction. 

The relationship between Spectral Acceleration ($SA$) and Spectral Displacement ($SD$) is strictly period-dependent, defined by the formula:

$$SD = SA \cdot \frac{T^2}{4\pi^2}$$

This mathematical relationship demonstrates that displacement demand grows exponentially with the structural period. Calculating the displacement multipliers for both axes yields: 

X-Axis: $\frac{0.260^2}{4\pi^2} \approx 0.0017$

Y-Axis: $\frac{0.905^2}{4\pi^2} \approx 0.0207$

The fundamental flexibility of the Y-axis gives it a theoretical displacement sensitivity roughly 12 times greater than the X-axis. Therefore, even though the Y-axis was subjected to a significantly lower inertial force, its lack of stiffness allowed it to undergo massive physical deformations. The X-axis acted as a rigid block—attracting massive base shear and stress but resisting deformation—while the Y-axis acted as a flexible rod, shedding stress but experiencing extreme drift.

On the other hand, the maximum internal forces are summarized as follows : 
| Description | Value | Unit | Notes |
| :--- | :--- | :--- | :--- |
| Max. axial force N | 466.51 | kN | Member No. 4, Location: 0.0m |
| Min. axial force N | -444.91 | kN | Member No. 4, Location: 0.0m |
| Max. shear force Vy | 32.12 | kN | Member No. 4, Location: 0.0m |
| Min. shear force Vy | -30.00 | kN | Member No. 6, Location: 2.470m |
| Max. shear force Vz | 4.08 | kN | Member No. 4, Location: 0.0m |
| Min. shear force Vz | -3.25 | kN | Member No. 6, Location: 2.470m |
| Max. torsional moment Mt | 0.10 | kNm | Member No. 4, Location: 0.0m |
| Min. torsional moment Mt | -0.09 | kN | Member No. 6, Location: 2.470m |
| Max. bending moment My | 10.87 | kNm | Member No. 4, Location: 0.0m |
| Min. bending moment My | -10.16 | kNm | Member No. 6, Location: 2.470m |
| Max. bending moment Mz | 17.20 | kNm | Member No. 4, Location: 0.0m |
| Min. bending moment Mz | -16.71 | kNm | Member No. 6, Location: 2.470m |

The time history analysis reveals that the critical internal forces (maximum bending moments, shear forces, and axial loads) are heavily concentrated at the base of the lowest-story columns. Under global lateral excitation, the multi-story frame behaves macroscopically as a vertical cantilever. The inertial forces generated by the mass of each floor level accumulate downwards through the load path. Consequently, the base columns must resist the maximum global base shear. Furthermore, the lateral sway of the upper stories generates a massive global overturning moment. As the building oscillates, the exterior columns parallel to the direction of motion experience alternating cycles of extreme axial compression and tension, coupled with maximum bending stress. This combined stress state makes the foundation-level boundary elements the most critical components for seismic capacity.

c) Conclude as to the seismic capacity of the structure.

To determine the final seismic capacity of the structure, the maximum dynamic demands (internal forces and global displacements) obtained from the time history analysis must be evaluated against the mechanical resistance of the frame. The structure is composed of HEB 240 cross-sections utilizing S355 structural steel.

1. Cross-Section and Material Properties

According to standard European profiles, the HEB 240 section and S355 steel possess the following characteristic properties:

Yield Strength ($f_y$): $355 \text{ MPa} \: (\text{N/mm}^2)$

Cross-Sectional Area ($A$): $10,600 \text{ mm}^2$

Plastic Section Modulus (Strong Axis, $W_{pl,y}$): $1,053 \times 10^3 \text{ mm}^3$

Plastic Section Modulus (Weak Axis, $W_{pl,z}$): $498.4 \times 10^3 \text{ mm}^3$

Partial Safety Factor ($\gamma_{M0}$): $1.0$ (for cross-section resistance)

2. Ultimate Limit State (ULS) – Strength Capacity Check

The most critical column (Member No. 4 at the base, $x = 0.0 \text{ m}$) experienced the absolute maximum combined stress state during the earthquake. The peak demands ($E_d$) are extracted from the envelope of the time history analysis:

Max Axial Force ($N_{Ed}$): $466.51 \text{ kN}$

Max Bending Moment ($M_{y,Ed}$): $10.87 \text{ kNm}$

Max Bending Moment ($M_{z,Ed}$): $17.20 \text{ kNm}$

The plastic design capacities ($R_d$) of the HEB 240 section are calculated as follows:

Axial Capacity ($N_{pl,Rd}$):$$N_{pl,Rd} = \frac{A \cdot f_y}{\gamma_{M0}} = \frac{10,600 \text{ mm}^2 \cdot 355 \text{ N/mm}^2}{1.0} = 3,763 \text{ kN}$$Strong-Axis Bending Capacity ($M_{pl,y,Rd}$):$$M_{pl,y,Rd} = \frac{W_{pl,y} \cdot f_y}{\gamma_{M0}} = \frac{1,053 \times 10^3 \text{ mm}^3 \cdot 355 \text{ N/mm}^2}{1.0 \times 10^6} = 373.8 \text{ kNm}$$Weak-Axis Bending Capacity ($M_{pl,z,Rd}$):$$M_{pl,z,Rd} = \frac{W_{pl,z} \cdot f_y}{\gamma_{M0}} = \frac{498.4 \times 10^3 \text{ mm}^3 \cdot 355 \text{ N/mm}^2}{1.0 \times 10^6} = 176.9 \text{ kNm}$$

Applying a conservative linear interaction formula for combined axial and bi-axial bending stress:
$$\text{Unity Check} = \frac{N_{Ed}}{N_{pl,Rd}} + \frac{M_{y,Ed}}{M_{pl,y,Rd}} + \frac{M_{z,Ed}}{M_{pl,z,Rd}}$$

$$\text{Unity Check} = 0.124 + 0.029 + 0.097 = \mathbf{0.250} \le 1.0$$

The maximum utilization ratio of the most critical member is only 25.0%. The steel cross-sections are massively oversized for the applied seismic forces and will remain completely elastic without yielding.

3. Global Deformation Capacity Check

Seismic capacity is also governed by lateral stiffness to prevent structural instability (P-Delta effects) and severe damage. The total height of the structure is H = 14.0 [m].The maximum absolute deformation occurred at the roof level in the flexible Y-direction:Max Global Displacement ($\Delta_{max}$): 83 [mm]

The global drift ratio ($\theta$) is calculated as:$$\theta = \frac{\Delta_{max}}{H} = \frac{83.0 \text{ mm}}{14,000 \text{ mm}} = 0.00593 \text{ rad} \approx \mathbf{0.59\%}$$A global drift ratio of 0.59%is well within standard acceptable limits for the ultimate limit state of steel frames under seismic loading (which typically allow drifts between 1.0% and 1.5% to ensure life safety and prevent collapse).

The dynamic time history analysis proves that the structure has sufficient seismic capacity. The substantial cross-sectional area of the HEB 240 columns ensures that internal stresses remain at roughly 25% of the S355 steel's yield threshold, while the overall frame stiffness restricts global deformations to a safe 0.59% drift ratio. Therefore, the building will comfortably survive the assigned bi-directional seismic event with no structural damage.
