# Q1

## Governing Equations for the Layered Soil System

The layered soil is modeled as a one-dimensional shear beam subjected to vertically propagating SH waves. The horizontal displacement in each layer is denoted by $u_i(z,t)$, where $z$ is the depth coordinate measured downward from the ground surface. For the three soil layers, neglecting damping, the equations of motion are

$$
\rho_i \frac{\partial^2 u_i}{\partial t^2} - G_i \frac{\partial^2 u_i}{\partial z^2} = 0,
\qquad i = 1,2,3,
$$

or equivalently

$$
\frac{\partial^2 u_i}{\partial t^2} - c_i^2 \frac{\partial^2 u_i}{\partial z^2} = 0,
\qquad
c_i = \sqrt{\frac{G_i}{\rho_i}},
$$

where $G_i$ is the shear modulus, $\rho_i$ is the mass density, and $c_i$ is the SH-wave velocity of layer $i$.

Let the layer thicknesses be $H_1$, $H_2$, and $H_3$, so that the interfaces are located at

$$
z = H_1, \qquad z = H_1 + H_2,
$$

and the bedrock is located at

$$
z = H = H_1 + H_2 + H_3.
$$

![Layered soil profile used for the Q1 formulation](images/q1_layered_soil_profile.png)

*Figure 1. Schematic three-layer soil column used in the SH-wave formulation, with a free surface at the top and a prescribed kinematic input motion at the bedrock. The drawing is not to scale.*

## Boundary and Interface Conditions

At the free ground surface, the shear stress must vanish. Since $\tau = G\,\partial u / \partial z$, this gives

$$
\tau_1(0,t) = G_1 \frac{\partial u_1}{\partial z}(0,t) = 0
\quad \Rightarrow \quad
\frac{\partial u_1}{\partial z}(0,t) = 0.
$$

At each interface, both displacement and shear stress must be continuous. Therefore, at $z = H_1$,

$$
u_1(H_1,t) = u_2(H_1,t),
$$

$$
G_1 \frac{\partial u_1}{\partial z}(H_1,t) =
G_2 \frac{\partial u_2}{\partial z}(H_1,t),
$$

and at $z = H_1 + H_2$,

$$
u_2(H_1 + H_2,t) = u_3(H_1 + H_2,t),
$$

$$
G_2 \frac{\partial u_2}{\partial z}(H_1 + H_2,t) =
G_3 \frac{\partial u_3}{\partial z}(H_1 + H_2,t).
$$

At the bedrock level, the input motion is prescribed. If the bedrock displacement is $u_g(t)$, the kinematic boundary condition is

$$
u_3(H,t) = u_g(t).
$$

If the input is instead given as a bedrock acceleration $a_g(t)$, then

$$
\ddot{u}_g(t) = a_g(t),
$$

and the same boundary condition can be written in terms of the corresponding displacement history.

## Frequency-Domain Form

To derive the harmonic response, assume

$$
u_i(z,t) = U_i(z)e^{i\omega t}.
$$

Substitution into the equations of motion gives, for each layer,

$$
U_i''(z) + \left(\frac{\omega}{c_i}\right)^2 U_i(z) = 0,
\qquad i = 1,2,3.
$$

The corresponding general solutions are

$$
U_i(z) = A_i \sin\left(\frac{\omega z}{c_i}\right)
+ B_i \cos\left(\frac{\omega z}{c_i}\right),
\qquad i = 1,2,3.
$$

The boundary and interface conditions in the frequency domain become

$$
\begin{aligned}
U_1'(0) &= 0, \\
U_1(H_1) &= U_2(H_1), \\
G_1 U_1'(H_1) &= G_2 U_2'(H_1), \\
U_2(H_1 + H_2) &= U_3(H_1 + H_2), \\
G_2 U_2'(H_1 + H_2) &= G_3 U_3'(H_1 + H_2), \\
U_3(H) &= U_g.
\end{aligned}
$$

The bedrock excitation is prescribed as a harmonic acceleration

$$
a_g(t) = a_0 e^{i\omega t}.
$$

Since

$$
a_g(t) = \ddot{u}_g(t) = -\omega^2 U_g e^{i\omega t},
$$

the bedrock displacement amplitude is

$$
U_g = -\frac{a_0}{\omega^2},
$$

so the bottom boundary condition becomes

$$
U_3(H) = -\frac{a_0}{\omega^2}.
$$

This set of equations, together with the six boundary and interface conditions, fully defines the one-dimensional SH-wave propagation problem in the three-layer soil column.

# Q2

## Natural Frequencies and Modes of Vibration

Using the frequency-domain solutions from Q1 together with the six boundary and interface conditions, the unknown integration constants can be collected into the vector

$$
\mathbf{C} = [C_1,\; C_2,\; C_3,\; C_4,\; C_5,\; C_6]^T.
$$

This leads to the homogeneous algebraic system

$$
\mathbf{A}(\omega)\mathbf{C} = \mathbf{0}.
$$

For a non-trivial mode shape, the constant vector $\mathbf{C}$ must be different from zero. Therefore, the natural frequencies are obtained from the frequency equation

$$
\det\bigl(\mathbf{A}(\omega)\bigr) = 0.
$$

The symbolic coefficient matrix is constructed directly from the six equations using `sympy.linear_eq_to_matrix`, after which the roots of $\det(\mathbf{A})$ are found numerically by scanning in frequency and refining each sign change with bisection.

The soil properties used here are the assignment values corresponding to the student-number digits,

$$
H_1 = 8\ \text{m}, \qquad H_2 = 65\ \text{m}, \qquad H_3 = 43\ \text{m},
$$

with

$$
G_1 = 150\ \text{MPa}, \qquad
G_2 = 110\ \text{MPa}, \qquad
G_3 = 120\ \text{MPa},
$$

and

$$
\rho_1 = 1650\ \text{kg/m}^3, \qquad
\rho_2 = 1850\ \text{kg/m}^3, \qquad
\rho_3 = 1900\ \text{kg/m}^3.
$$

The first 10 natural frequencies obtained from the notebook are listed below.

| Mode | $\omega_n$ [rad/s] | $f_n$ [Hz] |
| --- | ---: | ---: |
| 1 | 3.41964 | 0.54425 |
| 2 | 10.07663 | 1.60374 |
| 3 | 16.80455 | 2.67453 |
| 4 | 23.64545 | 3.76329 |
| 5 | 30.29954 | 4.82232 |
| 6 | 37.13594 | 5.91037 |
| 7 | 43.95543 | 6.99572 |
| 8 | 50.65300 | 8.06167 |
| 9 | 57.56232 | 9.16133 |
| 10 | 64.31951 | 10.23677 |

For each natural frequency, the corresponding mode shape is obtained by substituting $\omega = \omega_n$ back into the homogeneous system and solving for the constant vector $\mathbf{C}$ up to an arbitrary scaling factor. In the notebook, one constant is fixed to set the amplitude level, and each plotted mode is then normalized by its maximum absolute displacement.

![First 10 natural modes of the layered soil system](images/q2_first_10_modes.png)

*Figure 2. First 10 normalized natural mode shapes of the three-layer soil column. The dashed horizontal lines mark the interfaces between layers 1 and 2, and between layers 2 and 3.*

The first mode is a smooth global deformation of the full soil column. With increasing mode number, more zero crossings appear and the curvature becomes more oscillatory, especially in the deeper layers. The discontinuity in material properties at the interfaces changes the local wavelength of the mode shapes, which is why the slope and curvature visibly change from one layer to another.

## Effect of Soil Damping

In the present modal analysis, soil damping is neglected. If damping is included, the shear modulus becomes complex,

$$
G_i^{*}(\omega) = G_i + i\omega\eta_i.
$$

Then the eigenvalue problem is no longer purely real. The main consequences are:

- The natural frequencies become complex-valued. For light damping, the real part represents the damped oscillation frequency and is usually slightly lower than the undamped frequency.
- The imaginary part of the eigenvalue introduces exponential decay in time, so the free vibrations are no longer sustained standing waves.
- The mode shapes become complex-valued, which means that they describe not only amplitude variation with depth but also phase variation.
- In the frequency response, damping reduces the resonance amplitudes and broadens the peaks, while the sharp phase jumps of the undamped case become smooth transitions.

Therefore, including soil damping does not radically change the qualitative modal pattern for small damping, but it does introduce decay, a slight downward shift of the natural frequencies, and depth-dependent phase lag in the mode shapes.

# Q3

## Frequency Response Functions of the Layered Soil System

For the forced-response problem, the same layer-wise equations and the same general solutions from Q1 are used. The only change is the bedrock boundary condition, which is now prescribed by the seismic input motion.

Assume a harmonic bedrock acceleration

$$
a_g(t) = a_0 e^{i\omega t}.
$$

Because acceleration and displacement are related through

$$
a(t) = \ddot{u}(t) = -\omega^2 U e^{i\omega t},
$$

the corresponding bedrock displacement amplitude is

$$
U_g = -\frac{a_0}{\omega^2}.
$$

Therefore, the bottom boundary condition becomes

$$
U_3(H) = -\frac{a_0}{\omega^2}.
$$

The forced system can again be written in matrix form,

$$
\mathbf{A}(\omega)\mathbf{C} = \mathbf{b}(\omega),
$$

where the coefficient matrix $\mathbf{A}(\omega)$ is the same as in the free-vibration problem, while the right-hand side changes because of the prescribed bedrock motion.

The displacement frequency response function is defined as

$$
H(z,\omega) = \frac{U(z)}{U_g}.
$$

Substituting the bedrock displacement amplitude gives

$$
H(z,\omega) = -\frac{\omega^2 U(z)}{a_0}.
$$

Hence, in this harmonic formulation, the same complex ratio also represents the acceleration FRF,

$$
H(z,\omega) = \frac{a(z)}{a_g}.
$$

In the notebook, the FRFs are evaluated at:

- the top of layer 1, i.e. the ground surface, $z = 0$
- the top of layer 3, i.e. the interface between layers 2 and 3, $z = H_1 + H_2$

![Amplitude and phase of the FRF at the surface and at the top of layer 3](images/q3_frf_amplitude_phase.png)

*Figure 3. Amplitude and phase of the normalized FRF at the top of layer 1 (surface) and at the top of layer 3. The dashed red lines mark the natural frequencies found in Q2.*

## Comparison Between the Two Locations

At the surface, the FRF amplitude is generally larger. This is expected because the upward-propagating wave passes through the full soil column and is further amplified by reflection at the free surface. The surface therefore shows the strongest resonance peaks.

At the top of layer 3, the response is closer to the imposed bedrock motion and does not yet include the full amplification produced by the upper two layers. As a result, the amplitude is usually smaller than at the surface. In addition, the FRF at the top of layer 3 exhibits deeper minima between resonances. These minima are anti-resonances caused by partial cancellation between upward and downward traveling wave components at that depth.

The resonance peaks in both curves occur close to the natural frequencies derived in Q2, which confirms the consistency between the modal analysis and the forced-response analysis.

## Physical Meaning of the Phase

The phase of $H(z,\omega)$ gives the phase difference between the local soil response at depth $z$ and the harmonic bedrock input motion. In other words, it indicates whether the response is in phase with the input or lags by part of a cycle.

For the undamped model used here, the FRF is essentially real-valued apart from numerical roundoff. Therefore, the phase is mostly either

$$
0^\circ \quad \text{or} \quad 180^\circ,
$$

which means:

- $0^\circ$: the local response is in phase with the bedrock input
- $180^\circ$: the local response is out of phase with the bedrock input

The abrupt jumps between these two values occur when the response changes sign, which typically happens across resonances or anti-resonances. At the top of layer 3 these phase flips occur more frequently because that location shows stronger local cancellations. At the surface the phase changes are more regular and closely tied to the global resonant behavior of the full soil column.

If damping were included, the FRF would become genuinely complex-valued, the resonant peaks would become finite and broader, and the phase jumps would no longer be abrupt. Instead, they would become smooth transitions through the resonant regions.
