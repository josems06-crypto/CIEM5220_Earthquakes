5) Perform the response spectrum method of analysis (RSA) using the design spectra provided in Eurocode (EN1998-1) and report the following results:

a) Plot the first five eigenmodes of the system together with their correspondent eigenfrequencies. Derive the modal participation mass for each of the five modes (in each direction). What do you observe as to the (potential) contribution of the different modes to the final response of the system?

A modal analysis was performed based on the existing finite element model of the structure. As requested, the amount of modes captured was limited to five, each including the corresponding natural frequency and modal participation mass per mode and per direction. From it, the following eigenmodes were obtained for the first five modes:

### First Mode

![Mode 1 modal shape](Mode1.png)

Figure 1. First eigenmode of the structure, with $f_1 = 4.771\,\mathrm{Hz}$ and normalized displacement magnitude shown by the color contour.

### Second Mode

![Mode 2 modal shape](Mode2.png)

Figure 2. Second eigenmode of the structure, with $f_2 = 12.080\,\mathrm{Hz}$ and normalized displacement magnitude shown by the color contour.

### Third Mode

![Mode 3 modal shape](Mode3.png)

Figure 3. Third eigenmode of the structure, with $f_3 = 12.106\,\mathrm{Hz}$ and normalized displacement magnitude shown by the color contour.

### Fourth Mode

![Mode 4 modal shape](Mode4.png)

Figure 4. Fourth eigenmode of the structure, with $f_4 = 15.103\,\mathrm{Hz}$ and normalized displacement magnitude shown by the color contour.

### Fifth Mode

![Mode 5 modal shape](Mode5.png)

Figure 5. Fifth eigenmode of the structure, with $f_5 = 15.977\,\mathrm{Hz}$ and normalized displacement magnitude shown by the color contour.

The obtained eigenmodes of the structure have the following characteristics: 

| Mode No. | Eigenvalue $\lambda$ [1/s2] | Angular Frequency $\omega$ [rad/s] | Natural Frequency f [Hz] | Natural Period T [s] |
| :---: | :---: | :---: | :---: | :---: |
| 1 | 898.775 | 29.980 | 4.771 | 0.210 |
| 2 | 5761.336 | 75.903 | 12.080 | 0.083 |
| 3 | 5785.167 | 76.060 | 12.106 | 0.083 |
| 4 | 9005,584 | 94.898 | 15.103 | 0.066 |
| 5 | 10077.998 | 100.389 | 15.977 | 0.063 |

Based on the modal analysis, the modal participation mass for each of the five modes per direction was obtained:

<table>
	<thead>
		<tr>
			<th rowspan="2">Mode No.</th>
			<th rowspan="2">Modal Mass Mi [kg]</th>
			<th colspan="3">Effective Modal Mass - Translational Direction [kg]</th>
			<th colspan="3">Effective Modal Mass - Rotational Direction [kg]</th>
			<th colspan="3">Factor for Effective Modal Mass - Translational Direction</th>
			<th colspan="3">Factor for Effective Modal Mass - Rotational Direction</th>
		</tr>
		<tr>
			<th>meX</th>
			<th>meY</th>
			<th>meZ</th>
			<th>meφX</th>
			<th>meφY</th>
			<th>meφZ</th>
			<th>fmeX</th>
			<th>fmeY</th>
			<th>fmeZ</th>
			<th>fmeφX</th>
			<th>fmeφY</th>
			<th>fmeφZ</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>1</td>
			<td>1092.0</td>
			<td>2.6</td>
			<td>3278.3</td>
			<td>0.4</td>
			<td>1793.40</td>
			<td>1.40</td>
			<td>4355.65</td>
			<td>0.000</td>
			<td>0.606</td>
			<td>0.000</td>
			<td>0.103</td>
			<td>0.000</td>
			<td>0.190</td>
		</tr>
		<tr>
			<td>2</td>
			<td>117.8</td>
			<td>5.5</td>
			<td>100.7</td>
			<td>0.4</td>
			<td>25.93</td>
			<td>2.49</td>
			<td>1169.13</td>
			<td>0.001</td>
			<td>0.019</td>
			<td>0.000</td>
			<td>0.001</td>
			<td>0.000</td>
			<td>0.051</td>
		</tr>
		<tr>
			<td>3</td>
			<td>109.6</td>
			<td>0.0</td>
			<td>0.1</td>
			<td>0.0</td>
			<td>0.02</td>
			<td>0.00</td>
			<td>1.09</td>
			<td>0.000</td>
			<td>0.000</td>
			<td>0.000</td>
			<td>0.000</td>
			<td>0.000</td>
			<td>0.000</td>
		</tr>
		<tr>
			<td>4</td>
			<td>1194.3</td>
			<td>2672.1</td>
			<td>374.3</td>
			<td>147.7</td>
			<td>15.63</td>
			<td>1012.51</td>
			<td>3208.44</td>
			<td>0.494</td>
			<td>0.069</td>
			<td>0.027</td>
			<td>0.001</td>
			<td>0.034</td>
			<td>0.140</td>
		</tr>
		<tr>
			<td>5</td>
			<td>1285.6</td>
			<td>1172.3</td>
			<td>730.6</td>
			<td>60.1</td>
			<td>146.86</td>
			<td>456.40</td>
			<td>8854.09</td>
			<td>0.217</td>
			<td>0.135</td>
			<td>0.011</td>
			<td>0.008</td>
			<td>0.015</td>
			<td>0.387</td>
		</tr>
		<tr>
			<td>Σ</td>
			<td>3799.4</td>
			<td>3852.6</td>
			<td>4484.0</td>
			<td>208.6</td>
			<td>1981.84</td>
			<td>1472.82</td>
			<td>17588.41</td>
			<td>0.712</td>
			<td>0.829</td>
			<td>0.039</td>
			<td>0.114</td>
			<td>0.049</td>
			<td>0.768</td>
		</tr>
		<tr>
			<td>ΣM</td>
			<td></td>
			<td>5408.2</td>
			<td>5408.2</td>
			<td>5408.2</td>
			<td>17412.78</td>
			<td>29768.39</td>
			<td>22898.75</td>
			<td></td>
			<td></td>
			<td></td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td>%</td>
			<td></td>
			<td>71.24</td>
			<td>82.91</td>
			<td>3.86</td>
			<td>11.38</td>
			<td>4.95</td>
			<td>76.81</td>
			<td></td>
			<td></td>
			<td></td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
	</tbody>
</table>

As it can be observed from the previous results, the total modal participation mass of the five modes is below the prescribed minimum of 90% of the total mass, this holds for all directions. This means that if performed with this amount of modes, the analysis could not be concluded to be accurate enough to represent the real behavior of the structure due to seismic loading. Further on, the modal participation mass of some modes in certain directions can be observed to be almost negligible. To ensure the analysis is performed within the requirements as well as in an efficient manner, it will be ensured that a right amount of modes are chosen so that the total modal participation mass reaches 90% of the total mass, and modes which can be neglected will not be taken into account for the calculation. 

b) Determine the maximum displacements and stresses at the critical sections. Please substantiate your choice as to the modal combination rules used for: i) the structural modes; and ii) the different directions of the seismic input motion. Are the critical cross-sections the same as the ones found in Question 4 above?

The maximum displacements located at their corresponding critical cross-sections which follow from the Response Spectra Analysis are the following: 

### Serviceability Limit State (SLS) – Deflection and Rotation Summary

The global displacement and rotation analysis highlights that the most significant structural movement occurs as lateral drift/deflection along the Y-axis. Below is the detailed breakdown written in standard phrasing:

#### Global Displacements

* **Maximum Displacement in the X-Direction (Longitudinal):** The peak longitudinal movement reaches **6.5 mm**. This occurs on **Member No. 28** at a distance of **2.470 m**.

![Maximum X-displacement](MaxDisplacement1.png)

* **Maximum Displacement in the Y-Direction (Lateral):** The largest movement in the entire structure occurs along the Y-axis, reaching **34.2 mm**. This peak deflection is located on **Member No. 27** at a distance of **2.470 m**.

![Maximum Y-displacement](MaxDisplacement2.png)

* **Maximum Displacement in the Z-Direction (Vertical):** Vertical deflection remains very low, peaking at **3.7 mm**. This is located on **Member No. 218** at a distance of **3.886 m**.

![Maximum Z-displacement](MaxDisplacement3.png)

* **Maximum Vectorial (Total) Displacement:** When combining the X, Y, and Z translational vectors, the absolute maximum total displacement is **34.8 mm**. This governing value occurs on **Member No. 28** at a distance of **2.470 m** (driven heavily by the large Y-direction movement at this structural node).

![Maximum vectorial displacement](MaxDisplacement4.png)

---

#### Global Rotations

* **Maximum Rotation about the X-Axis:** The highest rotational deformation occurs about the X-axis, measuring **22.5 mrad**. This peak twist is located at the start of **Member No. 476** (at **0.000 m**).

![Maximum X-rotation](MaxRotation1.png)

* **Maximum Rotation about the Y-Axis:** Torsional rotation about the vertical Y-axis reaches a maximum of **2.0 mrad**, located on **Member No. 5** at a distance of **0.000 m**.

![Maximum Y-rotation](MaxRotation2.png)

* **Maximum Rotation about the Z-Axis:** Torsional rotation about the vertical Z-axis reaches a maximum of **6.4 mrad**, located on **Member No. 462** at a distance of **1.125 m**.

![Maximum Z-rotation](MaxRotation3.png)

The maximum stresses located at their corresponding critical cross-sections which follow from the Response Spectra Analysis are the following: 

### Ultimate Limit State (ULS) STR/GEO - Seismic Analysis Summary

The structural checks under seismic loading condition RC1 show that all examined members remain well within their material capacity limits. Below is the detailed breakdown for each critical check:

#### 1. Member 129 (Total Axial/Normal Stress)
* **Location:** 3.514 meters
* **Stress Point:** 1
* **Stress Type:** Total Normal Stress ($\sigma_{x,tot}$)
* **Existing Stress:** 155.792 N/mm²
* **Limit Stress:** 350.000 N/mm²
* **Status:** Safe. The stress ratio ($\eta$) is **0.445**, utilizing 44.5% of the total capacity.

![Maximum axial stress](MaxStress1.png)

#### 2. Member 470 (Total Shear Stress)
* **Location:** 1.000 meter
* **Stress Point:** 11
* **Stress Type:** Total Shear Stress ($\tau_{tot}$)
* **Existing Stress:** -20.264 N/mm²
* **Limit Stress:** 202.073 N/mm²
* **Status:** Safe. The stress ratio ($\eta$) is **0.100**, utilizing 10.0% of the shear capacity.

![Maximum shear stress](MaxStress2.png)

#### 3. Member 129 (Equivalent von Mises Stress)
* **Location:** 3.514 meters
* **Stress Point:** 1
* **Stress Type:** Equivalent von Mises Stress ($\sigma_{eqv, von Mises}$)
* **Existing Stress:** 155.792 N/mm²
* **Limit Stress:** 350.000 N/mm²
* **Status:** Safe. The stress ratio ($\eta$) is **0.445**, utilizing 44.5% of the allowable limit.

![Maximum equivalent stress](MaxStress1.png)



The modal combination rule used for the structural modes is chosen to be a Complete Quadratic Combination (CQC) by using equivalent linear combination. This choice was made based on the fact that some of the eigenmodes show to be very close to each other (see for example mode 2 and mode 3). When the eigenfrequencies of those certain modes differ by less than 10%, their modal responses are statistically dependent and can couple; the simple SRSS rule would unsafely ignore this interaction, whereas CQC correctly accounts for it via cross-modal correlation coefficients. For the different directions of the seismic input, it was chosen to make use of the Scaled Sum, with a factor of 100% / 30%, as it is the most realistic combination as well as a conservative approach, wihtout being as overly conservative as the absolute sum is, recommended by EN 1998-1. 

c) How did you choose the upper limit of modes to be considered in the final response of the system? Are the results sensitive to this choice and why? Please substantiate your answer.

As stated above, the amount of modes chosen previously (5 modes) was not sufficient for the total participation mass to be 90% of the modal mass. Therefore, more modes need to be taken into account. Additionally, the scope for directions of the seismic input motion is limited, and only the translational motion in the x- and y-direction will be taken into account. This choice is made based on the fact that the derived Empirical Response Spectra in Questions 1 and 2 show that the magnitude of the soil accelerations in the horizontal principal directions is much greater than for the vertical one. Next to it, the rotational directions are also not accounted for for simplicity. 

To ensure the total modal mass participation reached the prescribed minimum, the first 102 modes of the structure were selected. This gave a total modal participation mass which was 91.16% of the total mass in the x-direction and 92.43% in the y-direction. This was the minimum amount of modes to fulfill this requirement. Even though a lot of the selected modes have a very small modal participation mass, modes which had a modal participation mass smaller than 0.3% of the total mass in both x- and y-direction were neglected, following the regulations of EN 1998-1. This meant that only 21 out of the 102 modes were relevant for the calculation, making the analysis much more efficient. 

Based on this, we can conclude that the current results are very sensitive to the chosen modes, as if we had continued with the initial 5 modes, we would have reached a total modal mass participation of 71.24% and 82.91% respectively. This would have resulted in smaller displacements and stresses as a result of the seismic loading, possibly leading to underdesigning the structure. Even though these differences would have been clear and the structure wouldn't fulfill the requirements, the difference is not drastic and it could still give a realistic estimate of how the structure could behave. 


d) Conclude as to the seismic capacity of the structure

Seismic capacity is governed by lateral stiffness to prevent structural instability (P-Delta effects) and severe damage. The total height of the structure is H = 5.035 [m]. The maximum absolute deformation occurred at the roof level: Maximum Global Displacement ($\Delta_{max}$): 34.8 [mm]

The global drift ratio Global Drift Ratio is calculated as:$$Global Drift Ratio = \frac{\Delta_{max}}{H} = \frac{34.8 \text{ mm}}{5035 \text{ mm}} = 0.00691 \text{ rad} \approx \mathbf{0.69\%}$$A global drift ratio of 0.69% is beyond the standard acceptable limits for the ultimate limit state of steel frames under seismic loading (0.5% assuming it is a structure without brittle non-structural components). If we were to assume it to have ductile or isolated components the acceptable limit would move around 0.75% to 1%, meaning the strucutre would fulfill. Based on the characteristics of the structure, we are assuming components are ductile but not isolated, therefore the structure is on the limit and may need to be slightly redesigned. 

The Response Spectra analysis proves that the seismic capacity of the structure is slightly lower than the stated limit. On the one hand, the stresses in the membres in the substantial cross-sectional area of the HEB 240 columns ensures that internal stresses remain at roughly 44.5% of the S355 steel's yield threshold. On the other hand, the overall frame stiffness restricts global deformations to a 0.69% drift ratio, which is on the limit is we assume ductile behaviour of the components. Therefore, the building needs to be redesigned, including some isolated components for it to fulfill against seismic loading.  