# Q3

## Structural Model Used for the Pushover Analysis

The nonlinear static pushover analysis was carried out on the three-dimensional frame model shown in Figure 1. The nonlinearity was introduced by assigning plastic hinges to the moment-resisting frame members and by defining hinge behaviour at the bases of the bottom columns. In this way, the model is able to capture the progressive formation of plastic mechanisms as the lateral load is increased.

![Structural model used for the pushover analysis](images/Pushover_structure_image.png)

*Figure 1. RFEM model adopted for the pushover analysis.*

## Elastic Response Spectrum

The pushover demand was defined in RFEM using the horizontal elastic response spectrum of EN 1998-1. According to the assignment setup, the following spectrum properties were used:

- Spectrum type: Type 2
- Ground type: D
- Soil factor: $S = 1.80$
- Lower limit of constant spectral acceleration branch: $T_B = 0.10\ \mathrm{s}$
- Upper limit of constant spectral acceleration branch: $T_C = 0.30\ \mathrm{s}$
- Displacement-controlled branch limit: $T_D = 1.20\ \mathrm{s}$
- Structural damping ratio: $\xi = 5\%$
- Damping correction factor: $\eta = 1.0$
- Behaviour factor for elastic spectrum: $q = 1.0$
- Importance factor: $\gamma_I = 1.4$

The assignment defines the design ground acceleration as

$$
a_{gR} = \,(0.35 + 0.0C)\,g
$$

Using the student-ID digits adopted in the current project files,

$$
(A,B,C,D,E,F,G) = (6,6,1,1,2,5,7),
$$

and therefore $C = 1$, so

$$
PGA = \gamma_I\,(0.35 + 0.01)\,g = 0.504\,g
$$


## Modal Basis and Choice of Analysis Direction

Before running the nonlinear static analysis, a modal analysis was performed in RFEM6. The first 20 modes were extracted. From the modal mass table, one mode clearly governs each horizontal translational direction:

| Mode | lambda [1/s^2] | omega [rad/s] | f [Hz] | T [s] | meX [kg] | meY [kg] | fmeX [-] | fmeY [-] | Governing direction |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | --- |
| 1 | 282.938 | 16.821 | 2.677 | 0.374 | 82.0 | 13119.2 | 0.004 | 0.645 | global y |
| 7 | 3588.673 | 59.906 | 9.534 | 0.105 | 15936.9 | 39.4 | 0.784 | 0.002 | global x |

Thus, mode 1 is the governing translational mode in the global $y$ direction, while mode 7 is the governing translational mode in the global $x$ direction. 

The cumulative translational modal mass captured by the first 20 modes is:
- $\Sigma f_{meX} = 0.841$, corresponding to $84.13\%$ of the total mass in the global $x$ direction.
- $\Sigma f_{meY} = 0.933$, corresponding to $93.26\%$ of the total mass in the global $y$ direction.
- $\Sigma f_{meZ} = 0.151$, corresponding to $15.08\%$ of the total mass in the global $z$ direction.


The pushover analysis is performed in the global $y$ direction using the first mode as the load pattern. This choice is justified because mode 1 dominates the translational response in $y$, with an effective modal mass of $13119.2\ \mathrm{kg}$ and a modal mass participation factor of $0.645$. In addition, this mode has the largest relevant horizontal period, namely

$$
T_1 = 0.374\ \mathrm{s}
$$

which indicates that the structure is more flexible in the $y$ direction than in the $x$ direction. Therefore, the $y$ direction is expected to govern the lateral displacement demand and is the most appropriate direction for the pushover assessment.

## Analysis Setup

The nonlinear static analysis is therefore defined as follows:

- Lateral loading direction: global $y$ direction.
- Load pattern: first mode shape.
- Governing mode properties: $\omega_1 = 16.821\ \mathrm{rad/s}$, $f_1 = 2.677\ \mathrm{Hz}$, $T_1 = 0.374\ \mathrm{s}$.
- Effective modal mass in $y$: $m_{eY,1} = 13119.2\ \mathrm{kg}$.
- Effective modal mass ratio in $y$: $f_{meY,1} = 0.645$.
- Solution procedure: Newton-Raphson iteration.
- Termination criterion: analysis continued until structural collapse or numerical non-convergence.

This setup ensures that the pushover curve is generated in the direction that is dynamically most representative for the structure and that the applied lateral forces are consistent with the dominant deformation pattern obtained from modal analysis.

## Capacity-Spectrum Assessment

In the pushover procedure, the MDOF structure is converted into an equivalent SDOF system and the nonlinear capacity curve is expressed in ADRS form, that is, spectral acceleration versus spectral displacement. The demand is represented by the EN 1998-1 elastic spectrum. Following the procedure used in the course notes, the displacement demand is not taken from the horizontal plateau of the bilinear capacity curve. Instead, the yield point of the bilinearized spectrum is first identified and the initial elastic branch is extended from the origin. The demand is then read from the point where this elastic branch corresponds to the elastic spectrum.

For the present case, the selected lateral load pattern is modal and acts in the global $y$ direction, using the first mode shape. This is consistent with the modal analysis, since mode 1 is the governing translational mode in $y$ and carries the largest relevant effective mass in that direction.

![Pushover demand spectrum and capacity spectrum](images/part2_q3_design_adrs.png)

*Figure 3. ADRS representation of the EC8 demand spectrum and the pushover capacity spectrum in the governing $y$ direction. The orange dotted line is the extension of the elastic branch used to read $S_{de}$, while the short horizontal green segment indicates the beginning of the bilinear post-yield plateau.*

From the exported bilinear capacity spectrum, the yield point is

$$
S_{dy}=79.9\ \mathrm{mm}, \qquad S_{ay}=27.17\ \mathrm{m/s^2}.
$$

This yields an equivalent period

$$
T^\ast = 2\pi\sqrt{\frac{S_{dy}}{S_{ay}}}=0.341\ \mathrm{s}.
$$

Since

$$
T^\ast > T_C = 0.30\ \mathrm{s},
$$

the structure falls in the long-period range. Therefore, according to the ADRS procedure, the equal-displacement rule applies and the target displacement is taken directly from the elastic-spectrum point associated with the extended elastic branch:

$$
S_{de}=57.6\ \mathrm{mm}, \qquad S_d = S_{de}=57.6\ \mathrm{mm}.
$$

The usable displacement capacity of the actual pushover curve is

$$
d_u^\ast = 178.6\ \mathrm{mm}.
$$

Hence,

$$
S_d < d_u^\ast,
$$

which shows that the displacement demand remains well below the available displacement capacity. For the design spectrum defined by

$$
a_g = 0.504\,g,
$$

the structure satisfies the displacement-based seismic demand of the pushover check.

By scaling the design spectrum incrementally, the limiting acceleration at which the target displacement reaches the capacity is found to be approximately

$$
a_{g,\mathrm{fail}} \approx 1.56\,g.
$$

Therefore, the structure remains safe for the assignment design acceleration and would only reach its displacement capacity at a substantially larger seismic demand level.

![Scaled ADRS demand up to failure](images/part2_q3_failure_scaling.png)

*Figure 4. Iterative scaling of the demand spectrum up to the limiting acceleration. The orange dotted line is extended up to the contact point with the scaled demand spectrum, and the orange marker indicates the last safe point where the target displacement reaches the displacement capacity. The short horizontal green segment shows the start of the bilinear plateau after yield.*

Figure 4 confirms the failure-search procedure. The design demand spectrum for $a_g=0.504\,g$ remains far below the displacement limit, whereas the scaled spectrum associated with

$$
a_{g,\mathrm{fail}} \approx 1.56\,g
$$

reaches the capacity at the contact point defined by the extension of the elastic branch,

$$
S_d \approx d_u^\ast = 178.6\ \mathrm{mm}.
$$

This provides the requested limiting acceleration for the chosen modal pushover pattern in the global $y$ direction.



## Comparison of lateral-load patterns and applicability of pushover analysis

In accordance with EN 1998-1, Section 4.3.3.4.2.2, both uniform and modal lateral-load distributions were considered in each principal horizontal direction. The uniform pattern was defined using lateral forces proportional to the masses, independently of elevation. The modal pattern was based on the dominant translational mode in the direction under consideration.

In the $Y$-direction, Mode 1 is the dominant translational mode. It has a natural period of

$$
T_1 = 0.374\ \text{s}
$$

and an effective modal-mass ratio of

$$
f_{\mathrm{meY},1} = 64.5\%.
$$

The modal pushover pattern in the $Y$-direction was therefore based on Mode 1.

Nevertheless, the response in the $Y$-direction is not completely dominated by this mode. Mode 4 contributes an additional $22.2\%$ of the effective translational mass in the $Y$-direction. Modes 1 and 4 together account for

$$
64.5\% + 22.2\% = 86.7\%
$$

of the total effective mass in the $Y$-direction. Including Mode 9 increases the cumulative effective modal-mass ratio to approximately

$$
64.5\% + 22.2\% + 4.7\% = 91.4\%.
$$

Furthermore, Mode 4 has a rotational effective modal-mass ratio about the vertical $Z$-axis of approximately

$$
f_{\mathrm{m}\varphi Z,4} = 47.8\%,
$$

indicating coupled translational and torsional behaviour.

Based on these modal characteristics, an additional lateral-load pattern may be relevant in the $Y$-direction. Although Mode 1 is the dominant mode, it accounts for only $64.5\%$ of the effective translational mass, while Mode 4 makes a substantial additional contribution and exhibits significant torsional participation. Therefore, a higher-mode pattern based on Mode 4, a multimodal pattern combining Modes 1 and 4, or an adaptive pushover distribution could provide additional information regarding the sensitivity of the structural response to the assumed lateral-load distribution.

Conventional pushover analysis is most applicable when the structural response is dominated by a principal translational mode, with limited contribution from translation in the orthogonal horizontal direction and from torsional deformation. For Mode 1, the effective modal-mass ratio in the orthogonal $X$-direction is only

$$
f_{\mathrm{meX},1} = 0.4\%,
$$

while the rotational effective modal-mass ratio about the vertical $Z$-axis is approximately

$$
f_{\mathrm{m}\varphi Z,1} = 17.7\%.
$$

The very small contribution in the orthogonal $X$-direction indicates that Mode 1 is predominantly translational in the $Y$-direction. Although some torsional coupling is present, the response remains primarily governed by $Y$-translation. Consequently, pushover analysis is considered an appropriate method for estimating the global seismic capacity of the structure in the $Y$-direction. However, the contribution of Mode 4 and its significant torsional component should be considered when interpreting the results.


