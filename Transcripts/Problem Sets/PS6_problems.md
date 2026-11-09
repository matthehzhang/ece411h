---
course: ECE 411H
kind: problem-set
source: Problem Sets/ECE_411H_PS6_F26.pdf
source_pages: 2
author: Prof. Ed Yu
unit: exam2
topics: [maximum-power-transfer, thevenin-equivalent, load-impedance, conjugate-matching, bridge-circuit, density-of-states, fermi-distribution, hole-concentration, electron-concentration, intrinsic-concentration, band-gap, effective-mass, pn-junction, ideal-diode-equation, diffusion, dimensional-analysis, diffusion-length]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; text layer via pdftotext -layout where present
---

# Problem Set 6 — ECE 411H: Circuit Theory (Honors), Fall 2026

**Summary**
Six problems. Problems 1–2 are textbook maximum-power-transfer problems (8.51 and 8.54): find the Thevenin equivalent seen by $\mathbf{Z}_L$, set $\mathbf{Z}_L = \mathbf{Z}_{Th}^*$, and compute the maximum power. Problems 3–6 are instructor-written semiconductor-physics problems that build on recitation: derive the valence-band hole concentration $p$ from the density of states and Fermi function (Boltzmann approximation), find the intrinsic concentration $n_i$ for Si at 300 K, derive the simplified ideal diode equation $J(V) = (A_1 n_{p0} + A_2 p_{n0})(e^{qV/k_BT}-1)$ from band-edge shifts, and use dimensional analysis to pin down $A_1, A_2$ in terms of $q$, $D$, $\tau$, and diffusion length $L = \sqrt{D\tau}$. Exam-2-unit material: max power transfer (circuits) and the diode/semiconductor physics thread.

Due date: We 10/21/2026. Due online (Canvas) by start of class on due date.

## Page 1

Header: DUE DATE: We 10/21/2026. DUE ONLINE (CANVAS) BY START OF CLASS ON DUE DATE.
Title line: Problem Set 6 — ECE 411H: Circuit Theory (Honors) — Fall 2026.

### 1. Maximum power transfer 1.

**8.51** For the circuit in Fig. P8.51, choose the load impedance $\mathbf{Z}_L$ so that the power dissipated in it is a maximum. How much power will that be?

**Figure P8.51: Circuit for Problem 8.51.** Phasor-domain circuit. Left: independent voltage source $20\angle 0^\circ$ V (circle, + on top, − on bottom), its − terminal on the bottom rail. From the source + terminal, a $4\ \Omega$ resistor in series along the top wire to a middle node. From the middle node, an inductor $j2\ \Omega$ goes vertically down to the bottom rail (shunt branch). From the middle node the top wire continues to the right through a capacitor $-j4\ \Omega$ (series) to the load $\mathbf{Z}_L$ (blue box), whose other end returns to the bottom rail. Topology: source → $4\ \Omega$ → node; node to ground via $j2\ \Omega$; node → $-j4\ \Omega$ → $\mathbf{Z}_L$ → ground.

### 2. Maximum power transfer 2.

**8.54** For the circuit in Fig. P8.54, choose the load impedance $\mathbf{Z}_L$ so that the power dissipated in it is a maximum. How much power will that be?

**Figure P8.54: Circuit for Problem 8.54.** A diamond-shaped bridge with four nodes: top, left, right, bottom. Upper-left edge (left node to top node): capacitor $-j2$ k$\Omega$. Upper-right edge (top node to right node): resistor $4$ k$\Omega$. Lower-left edge (left node to bottom node): resistor $8$ k$\Omega$. Lower-right edge (right node to bottom node): capacitor $-j6$ k$\Omega$. Across the horizontal diagonal (between the left node and the right node) is an independent current source $2\angle 0^\circ$ mA (circle with arrow pointing to the RIGHT, i.e., current flows from the left node into the right node through the source). The load $\mathbf{Z}_L$ (blue box) is connected across the vertical diagonal: a wire from the top node goes right and down along an outer rail to $\mathbf{Z}_L$, and from $\mathbf{Z}_L$ down and left back to the bottom node. So $\mathbf{Z}_L$ is between the top and bottom nodes of the bridge.

### 3. Hole concentration from density of states.

In recitation section you learned about the density of states function and how to calculate the electron concentration, $n$, in the conduction band from the density of states and Fermi distribution function. Similarly, the hole concentration, $p$, in the valence band is given by

$$p = \int_{-\infty}^{E_v} g_v(E)\,[1 - f(E)]\,dE\,,$$

where

$$g_v(E) = \frac{\sqrt{2}}{\pi^2}\left(\frac{m_v^*}{\hbar^2}\right)^{3/2}(E_v - E)^{1/2}\,,$$

$$f(E) = \frac{1}{e^{(E - E_F)/k_B T} + 1}\,.$$

Show that, for $(E_F - E_v) \gg k_B T$,

$$p \approx 2\left(\frac{m_v^* k_B T}{2\pi\hbar^2}\right)^{3/2} e^{-(E_F - E_v)/k_B T}\,.$$

### 4. Intrinsic concentration.

Recall the expression for $p$ from problem 3, and the expression for $n$ from recitation, i.e.,

$$n \approx 2\left(\frac{m_c^* k_B T}{2\pi\hbar^2}\right)^{3/2} e^{-(E_c - E_F)/k_B T}\,.$$

(a) Obtain an expression for the value of $E_c - E_F$ (in eV) for which $n = p$. Your result should be in terms of $E_g$, $k_B$, $T$, $m_c^*$, and $m_v^*$. $E_g$ is energy band gap, with $E_g \equiv E_c - E_v$.

(b) For Si at $T = 300$ K, take $E_g = 1.12$ eV, $m_c^* = 1.18\,m_e$, $m_v^* = 0.81\,m_e$, and $m_e = 9.11\times 10^{-31}$ kg. Calculate, at $T = 300$ K, the value of $n$ and $p$ when they are equal to each other. This value is called the intrinsic concentration $n_i$, and $n_i$ is one of the important factors limiting the temperature at which devices can operate: at high temperatures, $n_i$ can approach typical dopant concentrations and the ability to control electronic properties and current flow via doping is degraded or lost.

### 5. Simplified ideal diode equation.

In a pn junction diode, current flow occurs when a positive voltage $V$ is applied to the p-type terminal relative to the n-type terminal. In a simple model, we can calculate the current density $J$ (current per unit area) in the pn junction diode by calculating $n_p$, the concentration of electrons on the p-side of the junction with voltage $V$ applied, and $p_n$, the concentration of holes on the n-side of the junction with $V$ applied. The current is then given approximately by $J(V) = A_1(n_p - n_{p0}) + A_2(p_n - p_{n0})$, where $A_1$ and $A_2$ are constants that depend on the details of carrier motion in the pn junction, $n_{p0} = n_p(V{=}0)$, and $p_n = p_n(V{=}0)$ [sic — as printed; evidently meant $p_{n0} = p_n(V{=}0)$]. Show that $J(V)$ is then given by

$$J(V) = \left(A_1 n_{p0} + A_2 p_{n0}\right)\left(e^{qV/k_B T} - 1\right)\,,$$

where $q$ is the electron's charge magnitude.

*Hint:* Recall from class how the band-edge energies in the pn junction change with $V$, noting that for $V \neq 0$, $n$ on the p-side of the junction is determined by $E_F$ on the n-side of the junction, and $p$ on the n-side of the junction is determined by $E_F$ on the p-side of the junction.

[Problem Set 6 continues with Problem 6 on the next page]

## Page 2

Header: DUE DATE: We 10/21/2026. DUE ONLINE (CANVAS) BY START OF CLASS ON DUE DATE.

### 6. Dimensional analysis and ideal diode equation.

In this problem, you will see how analysis of the units of different quantities allows you to determine the full form of the expression for the current-voltage relationship in an ideal pn junction diode. This approach is known as dimensional analysis, and is a very powerful technique for analyzing and understanding a wide range of physical systems.

(a) The expression for current density $J(V)$ in Problem 5 includes two constants, $A_1$ and $A_2$. What are the units of those constants (in standard mks units)?

(b) The primary mechanism for carrier motion and current flow in an ideal pn junction diode is diffusion of holes on the n-side of the junction, and of electrons on the p-side of the junction, in the direction away from the junction. Electron and hole diffusion are described by two physical parameters each: the diffusion constant, $D_n$ (for electrons) or $D_p$ (for holes), and the diffusion lifetime, $\tau_n$ (for electrons) or $\tau_p$ (for holes). Diffusion occurs due to spatial variations in the concentration of electrons or holes, and the diffusion current $J_{diff,n(p)}$ for electrons (holes) is given by

$$J_{diff,n(p)} = -q_{n(p)}\, D_{n(p)}\, \nabla n(p)\,,$$

where $q_{n(p)}$ is the charge of an electron (hole). Obviously, the units of $\tau_n$ and $\tau_p$ are seconds. What are the units of $D_n$ and $D_p$ (in standard mks units)?

(c) $A_1$ and $A_2$ must be rational functions of $q_{n(p)}$, $D_n$, $D_p$, $\tau_n$ and $\tau_p$, and powers of these quantities (including fractional powers, e.g., square roots). Given the units for $q_{n(p)}$, $D_n$, $D_p$, $\tau_n$ and $\tau_p$, and the units for $A_1$ and $A_2$, and assuming any arbitrary numerical constants of proportionality have magnitude 1, how is $A_1$ related to $q_{n(p)}$, $D_n$ and $\tau_n$, and how is $A_2$ related to $q_{n(p)}$, $D_p$ and $\tau_p$?

(d) Another parameter used to describe the motion of electrons and holes by diffusion is the diffusion length, $L_p$ or $L_n$. The diffusion lengths have units of meters. Based on the units of each quantity, and again assuming any arbitrary numerical constants of proportionality have magnitude 1, express $L_n$ in terms of $D_n$ and $\tau_n$, and $L_p$ in terms of $D_p$ and $\tau_p$.

(e) Finally, express $A_1$ in terms of $q_n$, $D_n$ and $L_n$, and $A_2$ in terms of $q_p$, $D_p$ and $L_p$. These expressions combined with the equation for $J(V)$ in problem 5 constitute the standard form of the ideal diode equation, which describes the current-voltage relationship for an ideal pn junction diode.

(Rest of page 2 is blank.)

## Index terms

Problem Set 6, PS6, problem 1, problem 2, problem 3, problem 4, problem 5, problem 6, 8.51, 8.54, maximum power transfer, load impedance Z_L, Thevenin equivalent, Thevenin impedance, conjugate match, Z_L = Z_Th*, maximum power, Figure P8.51, Figure P8.54, bridge circuit, current source 2 mA, 20 V source, 4 ohm, j2 ohm, -j4 ohm, -j2 kohm, 4 kohm, 8 kohm, -j6 kohm, density of states, g_v(E), Fermi distribution, f(E), hole concentration p, electron concentration n, valence band, conduction band, E_v, E_c, E_F, Fermi level, Boltzmann approximation, effective mass m_v*, m_c*, effective density of states, intrinsic concentration n_i, band gap E_g, Si at 300 K, 1.12 eV, 1.18 m_e, 0.81 m_e, 9.11e-31 kg, pn junction, ideal diode equation, current density J(V), n_p, p_n, n_p0, p_n0, A_1, A_2, e^{qV/kT} - 1, band-edge energies, quasi-Fermi level, dimensional analysis, mks units, diffusion constant D_n, D_p, diffusion lifetime tau_n, tau_p, diffusion current, J_diff = -q D grad n, diffusion length L_n, L_p, L = sqrt(D tau), A_1 = q D_n / L_n, standard form of ideal diode equation
