---
course: ECE 411H
kind: problem-set-solution
source: Problem Sets/ECE_411H_PS6_solns_F26.pdf
source_pages: 7
author: Prof. Ed Yu / TA (pp. 1–2 are publisher solutions, © 2016 National Technology and Science Press; pp. 3–7 handwritten by instructor)
unit: exam2
topics: [maximum-power-transfer, thevenin-equivalent, open-circuit-voltage, mesh-analysis, bridge-circuit, conjugate-matching, density-of-states, fermi-distribution, boltzmann-approximation, hole-concentration, intrinsic-concentration, effective-density-of-states, band-gap, pn-junction, quasi-fermi-level, ideal-diode-equation, dimensional-analysis, diffusion-length]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; text layer via pdftotext -layout where present
---

# ECE 411H: Problem Set 6 Solutions

**Summary**
Problems 8.51 and 8.54 (typeset): Thevenin impedance by source deactivation, $\mathbf{V}_{oc}$ by voltage division or mesh analysis, $\mathbf{Z}_L = \mathbf{Z}_s^*$, $P_{av}(\max) = |\mathbf{V}_s|^2/(8R_L)$, giving 12.5 W ($\mathbf{Z}_L = 0.8 + j2.4\ \Omega$) and 1.41 mW ($\mathbf{Z}_L = 3.3 + j2.4$ k$\Omega$). Problems 3–6 (handwritten): derive $p = 2(m_v^* k_B T/2\pi\hbar^2)^{3/2}e^{-(E_F - E_v)/k_BT}$ by substitution $u = E_v - E$ and the Boltzmann approximation; set $n = p$ to get $E_c - E_F = \tfrac12 E_g - \tfrac34 k_B T\ln(m_v^*/m_c^*) = 0.5673$ eV for Si and $n_i \approx 9.47\times 10^9$ cm$^{-3}$; use quasi-Fermi-level shift $eV$ to show $n_p = n_{p0}e^{eV/k_BT}$, $p_n = p_{n0}e^{eV/k_BT}$, hence $J(V) = (A_1 n_{p0} + A_2 p_{n0})(e^{eV/k_BT} - 1)$; dimensional analysis gives $[A] = $ C·m/s, $[D] = $ m$^2$/s, $L = \sqrt{D\tau}$, $A_1 = eD_n/L_n$, $A_2 = eD_p/L_p$. Exam-2 relevance: maximum power transfer procedure, and the diode-equation physics thread.

## Page 1

**ECE 411H: Problem Set 6 Solutions**

**Problem 8.51** For the circuit in Fig. P8.51, choose the load impedance $\mathbf{Z}_L$ so that the power dissipated in it is a maximum. How much power will that be?

**Figure P8.51: Circuit for Problem 8.51.** Source $20\angle 0^\circ$ V (+ top) on the left; $4\ \Omega$ in series on the top wire to a node; from the node, $j2\ \Omega$ inductor shunt to the bottom rail; top wire continues through $-j4\ \Omega$ capacitor to $\mathbf{Z}_L$ (blue box), which returns to the bottom rail.

**Solution:** The Thévenin impedance of the circuit connected to $\mathbf{Z}_L$ can be found by deactivating the voltage source and then calculating $\mathbf{Z}_{Th}$.

$$\mathbf{Z}_s = \mathbf{Z}_{Th} = -j4 + 4 \parallel j2$$
$$= -j4 + \frac{8j}{4 + j2} = (0.8 - j2.4)\ \Omega.$$

For maximum power transfer,
$$\mathbf{Z}_L = \mathbf{Z}_s^* = (0.8 + j2.4)\ \Omega,$$

To determine $\mathbf{V}_s$ of the equivalent source circuit, we calculate $\mathbf{V}_{oc}$ with $\mathbf{Z}_L$ removed:
$$\mathbf{V}_s = \mathbf{V}_{oc} = \frac{20\times j2}{4 + j2} = \frac{j40}{4 + j2} = 8.94 e^{j63.43^\circ}\ \text{V}.$$

Amount of power transferred is:
$$P_{av}(\max) = \frac18\frac{|\mathbf{V}_s|^2}{R_L} = \frac18\frac{(8.94)^2}{0.8} = 12.5\ \text{W}.$$

Footer: All rights reserved. Do not reproduce or distribute. © 2016 National Technology and Science Press

## Page 2

**Problem 8.54** For the circuit in Fig. P8.54, choose the load impedance $\mathbf{Z}_L$ so that the power dissipated in it is a maximum. How much power will that be?

**Figure P8.54: Circuit for Problem 8.54.** Diamond bridge: upper-left $-j2$ k$\Omega$, upper-right $4$ k$\Omega$, lower-left $8$ k$\Omega$, lower-right $-j6$ k$\Omega$; current source $2\angle 0^\circ$ mA across the horizontal diagonal with arrow pointing right (left node to right node); $\mathbf{Z}_L$ (blue box) connected between the top node and bottom node via the outer right rail.

**Solution:** To determine the equivalent source voltage $\mathbf{V}_s$, we remove $\mathbf{Z}_L$ and calculate $\mathbf{V}_{oc}$.

**Figure:** The bridge redrawn with $\mathbf{Z}_L$ removed. Two mesh currents are marked in blue: $\mathbf{I}_1$ (clockwise arrow) in the upper triangle formed by $-j2$ k$\Omega$, $4$ k$\Omega$, and the current source; $\mathbf{I}_2$ (clockwise arrow) in the lower triangle formed by the current source, $-j6$ k$\Omega$, and $8$ k$\Omega$. The open-circuit terminals are on the right: open circles labeled + (upper, connected to the top node) and − (lower, connected to the bottom node), with $\mathbf{V}_{oc}$ between them.

For the outer loop of the diamond:
$$-j2\text{k}\,\mathbf{I}_1 + 4\text{k}\,\mathbf{I}_1 - j6\text{k}\,\mathbf{I}_2 + 8\text{k}\,\mathbf{I}_2 = 0$$

Also,
$$\mathbf{I}_2 - \mathbf{I}_1 = 2\times 10^{-3}\ \text{A}.$$

Solution gives
$$\mathbf{I}_1 = (-1.37 + j0.076)\ \text{mA},\qquad \mathbf{I}_2 = (0.63 + j0.076)\ \text{mA}$$
$$\mathbf{V}_s = \mathbf{V}_{oc} = 4\mathbf{I}_1 - j6\mathbf{I}_2 = 6.1\angle{-145.3^\circ}\ \text{V}.$$

To determine $\mathbf{Z}_s$, we suppress the source and simplify the circuit. The result is
$$\mathbf{Z}_s = (4 - j6)\parallel(8 - j2)\ \text{k}\Omega$$
$$= \frac{(4 - j6)(8 - j2)}{4 - j6 + 8 - j2} = \frac{20 - j56}{12 - j8} = (3.3 - j2.4)\ \text{k}\Omega.$$

For maximum power transfer,
$$\mathbf{Z}_L = \mathbf{Z}_s^* = (3.3 + j2.4)\ \text{k}\Omega,$$
and
$$P_{av}(\max) = \frac18\frac{|\mathbf{V}_s|^2}{R_L} = \frac18\times\frac{(6.1)^2}{3.3\times 10^3} = 1.41\ \text{mW}.$$

Footer: All rights reserved. Do not reproduce or distribute. © 2016 National Technology and Science Press

## Page 3

(Handwritten, ruled paper, black ink.)

**3.**
$$p = \int_{-\infty}^{E_v} g_v(E)[1 - f(E)]\,dE\ ;\quad g_v(E) = \frac{\sqrt2}{\pi^2}\left(\frac{m_v^*}{\hbar^2}\right)^{3/2}(E_v - E)^{1/2}$$
$$= \frac{\sqrt2}{\pi^2}\left(\frac{m_v^*}{\hbar^2}\right)^{3/2}\int_{-\infty}^{E_v}(E_v - E)^{1/2}\left[1 - \frac{1}{e^{(E - E_F)/k_BT} + 1}\right]dE\ ;\quad\text{let } u = E_v - E,\ du = -dE$$
$$= \frac{\sqrt2}{\pi^2}\left(\frac{m_v^*}{\hbar^2}\right)^{3/2}\int_0^\infty u^{1/2}\left[1 - \frac{1}{e^{(E_v - E_F)/k_BT}\,e^{-u/k_BT} + 1}\right]du$$

Since we take $(E_F - E_v)\gg k_BT$, we can perform a Taylor series expansion of $f(E)$: $\frac{1}{1 + x}\approx 1 - x$ for $x \ll 1$

$$p = \frac{\sqrt2}{\pi^2}\left(\frac{m_v^*}{\hbar^2}\right)^{3/2}\int_0^\infty u^{1/2}\left[1 - \left(1 - e^{-(E_F - E_v)/k_BT}e^{-u/k_BT}\right)\right]du$$
$$= \frac{\sqrt2}{\pi^2}\left(\frac{m_v^*}{\hbar^2}\right)^{3/2}e^{-(E_F - E_v)/k_BT}\underbrace{\int_0^\infty u^{1/2}e^{-u/k_BT}\,du}_{=\ \frac{\sqrt\pi}{2}(k_BT)^{3/2}\ \text{(from recitation)}}$$

$$\Rightarrow\boxed{p = 2\left(\frac{m_v^* k_BT}{2\pi\hbar^2}\right)^{3/2}e^{-(E_F - E_v)/k_BT}}\quad\checkmark$$

(Rest of page blank.)

## Page 4

(Handwritten.)

**4. a)** We are given that:
$$n = 2\left(\frac{m_c^* k_BT}{2\pi\hbar^2}\right)^{3/2}e^{-(E_c - E_F)/k_BT}$$
$$p = 2\left(\frac{m_v^* k_BT}{2\pi\hbar^2}\right)^{3/2}e^{-(E_F - E_v)/k_BT}$$

$n = p \Rightarrow (m_c^*)^{3/2}e^{-(E_c - E_F)/k_BT} = (m_v^*)^{3/2}e^{-(E_F - E_v)/k_BT}$ ; multiply by $e^{-(E_c - E_F)/k_BT}$ (a small scribble/cross-out precedes the word "multiply")

$$e^{-2(E_c - E_F)/k_BT} = \left(\frac{m_v^*}{m_c^*}\right)^{3/2}e^{-(E_c - E_v)/k_BT}\ ;\quad\text{take } \ln\text{ of both sides}$$
$$\frac{-2}{k_BT}(E_c - E_F) = -\left(\frac{E_c - E_v}{k_BT}\right) + \frac32\ln\left(\frac{m_v^*}{m_c^*}\right)$$
$$\Rightarrow\boxed{(E_c - E_F) = \frac12 E_g - \frac34 k_BT\ln\left(\frac{m_v^*}{m_c^*}\right)}$$

**b)** For Si at $T = 300$K: $E_g = 1.12$ eV, $m_c^* = 1.18\,m_e$, $m_v^* = 0.81\,m_e$, $m_e = 9.11\times 10^{-31}$ kg.
$$E_c - E_F = \frac12(1.12) - \frac34(8.617\times 10^{-5}\ \text{eV/K})(300\text{K})\ln\left(\frac{0.81}{1.18}\right) = 0.5673\ \text{eV}$$

Then
$$n = n_i = 2\left(\frac{1.18(9.11\times 10^{-31})(1.381\times 10^{-23})(300)}{2\pi(1.055\times 10^{-34})^2}\right)^{3/2}e^{-(0.5673)/(8.617\times 10^{-5})(300)}$$
$$= 9.473\times 10^{15}\ \text{m}^{-3} = \boxed{9.473\times 10^9\ \text{cm}^{-3} = n}$$

$$p = n_i = 2\left(\frac{0.81(9.11\times 10^{-31})(1.381\times 10^{-23})(300)}{2\pi(1.055\times 10^{-34})^2}\right)^{3/2}e^{-(1.12 - 0.5673)/(8.617\times 10^{-5})(300)}$$
$$= 9.477\times 10^{15}\ \text{m}^{-3} = \boxed{9.477\times 10^9\ \text{cm}^{-3} = p}$$

Thus, we see that indeed $n = p$ with
$$n = p = n_i \approx 9.47\times 10^9\ \text{cm}^{-3}.$$

(Rest of page blank.)

## Page 5

(Handwritten.)

**5.** In class, we saw that for a voltage $V$ applied to the p-side of a pn junction (with the n-side grounded), the band-edge energy diagram is:

**Figure (band diagram, hand sketch):** Horizontal position axis, p-region on the left (labeled "p"), n-region on the right (labeled "n"). Two solid curves: the upper is $E_c$ (conduction band edge) and the lower is $E_v$ (valence band edge); both are flat and high on the p-side, step smoothly DOWN through the junction region, and are flat and lower on the n-side ($E_c$ labeled at the right end of the upper curve, $E_v$ at the right end of the lower curve). Two dashed horizontal lines mark the quasi-Fermi levels: $E_{F,p}$ (labeled at the far left) is the lower dashed line, lying slightly below the p-side $E_c$ region and extending to the right; $E_{F,n}$ (labeled at the right, just under $E_c$ on the n side) is the upper dashed line, lying just below the n-side $E_c$. A double-headed vertical arrow between the two dashed lines is labeled $eV$ (the separation $E_{F,n} - E_{F,p} = eV$). An arrow from below pointing up at the p-side region is labeled "electron conc. here $= n_p$"; an arrow pointing to the n-side valence band edge is labeled "hole conc. here $= p_n$".

$$n_p = 2\left(\frac{m_c^* k_BT}{2\pi\hbar^2}\right)^{3/2}e^{-(E_c - E_{F,n})/k_BT}$$
$$\Rightarrow\quad = 2\left(\frac{m_c^* k_BT}{2\pi\hbar^2}\right)^{3/2}e^{-(E_c - E_{F,p})/k_BT}\,e^{(E_{F,n} - E_{F,p})/k_BT}$$
$$= 2\left(\frac{m_c^* k_BT}{2\pi\hbar^2}\right)^{3/2}e^{-(E_c - E_{F,p})/k_BT}\,e^{eV/k_BT}$$
$$= n_{p0}\,e^{eV/k_BT}$$
$$p_n = 2\left(\frac{m_v^* k_BT}{2\pi\hbar^2}\right)^{3/2}e^{-(E_{F,p} - E_v)/k_BT}$$
$$= 2\left(\frac{m_v^* k_BT}{2\pi\hbar^2}\right)^{3/2}e^{-(E_{F,n} - E_v)/k_BT}\,e^{(E_{F,n} - E_{F,p})/k_BT}$$
$$= p_{n0}\,e^{eV/k_BT}$$

Then,
$$J(V) = A_1(n_p - n_{p0}) + A_2(p_n - p_{n0})$$
$$= A_1 n_{p0}\left(e^{eV/k_BT} - 1\right) + A_2 p_{n0}\left(e^{eV/k_BT} - 1\right)$$
(a stray small "0" mark appears below this line)
$$\Rightarrow\boxed{J(V) = \left(A_1 n_{p0} + A_2 p_{n0}\right)\left(e^{eV/k_BT} - 1\right)}\quad\checkmark$$

(Rest of page blank.)

## Page 6

(Handwritten.)

**6. a)** $J(V)$ has units of $[\text{A/m}^2] = [\text{C/s}\cdot\text{m}^2]$
$n_{p0}, p_{n0}$ have units of $[\text{m}^{-3}]$
$$\Rightarrow [\text{C/s}\cdot\text{m}^2] = [A_1, A_2][\text{m}^{-3}]\ \Rightarrow\ \boxed{[A_1, A_2] = [\text{C}\cdot\text{m/s}]}$$

**b)** From the problem statement, we have
$$J_{diff,n(p)} = -q_{n(p)}D_{n(p)}\vec\nabla n(p)$$
In terms of units, this becomes
$$[\text{C/s}\cdot\text{m}^2] = [\text{C}][D_{n(p)}]\left[\tfrac1{\text{m}}\right][\text{m}^{-3}]$$
$$\Rightarrow\boxed{[D_{n(p)}] = [\text{m}^2/\text{s}]}$$

**c)** We need to combine $q$, $D_{n(p)}$ and $\tau_{n(p)}$ to obtain an expression for $A_{1(2)}$ that has the correct units, C·m/s.
Among these quantities, [C] must come from $q_{n(p)}$.
To obtain [m], the only possibility is $\sqrt{D_{n(p)}\tau_{n(p)}}$.
To obtain [s], the only possibility is $\tau_{n(p)}$.
Thus, to obtain [C·m/s] for $A_{1(2)}$, we must (a scribbled-out word) have
$$A_{1(2)} = (\text{constant})\cdot q_{n(p)}\sqrt{D_{n(p)}\tau_{n(p)}}\big/\tau_{n(p)} = (\text{constant})\cdot q_{n(p)}\sqrt{D_{n(p)}/\tau_{n(p)}}$$
$$\Rightarrow\boxed{A_1 = \pm q_n\sqrt{D_n/\tau_n}\ ,\quad A_2 = \pm q_p\sqrt{D_p/\tau_p}}$$

**d)** We saw in part (c) that the only way to obtain a quantity with units of [m] is (a scribbled-out word) $\sqrt{D_{n(p)}\tau_{n(p)}}$, so
$$\boxed{L_n = \sqrt{D_n\tau_n}\ ,\quad L_p = \sqrt{D_p\tau_p}}$$

**e)**
$$A_{1(2)} = \pm q_{n(p)}\sqrt{D_{n(p)}/\tau_{n(p)}} = \pm q_{n(p)}D_{n(p)}\big/\sqrt{D_{n(p)}\tau_{n(p)}}$$
$$= \pm q_{n(p)}D_{n(p)}/L_{n(p)}$$
$$\Rightarrow\boxed{A_1 = \pm q_n\frac{D_n}{L_n}\ ,\quad A_2 = \pm q_p\frac{D_p}{L_p}}$$

## Page 7

(Handwritten.)

Finally, (not necessary for full credit), we need to determine the signs of $A_1$ and $A_2$. In the band-edge energy diagram for problem 5, electrons are injected from the n to p side of the junction and diffuse to the left. Holes are injected from the p to the n side of the junction and diffuse to the right. In both cases, the corresponding electric current flows from left to right (for $V > 0$), and we want $A_1, A_2 > 0$.
Thus, taking $e$ = electron charge magnitude $= |q_{n(p)}|$, we have
$$A_1 = e\frac{D_n}{L_n},\quad A_2 = e\frac{D_p}{L_p}$$
$$\Rightarrow J(V) = e\left(\frac{D_n}{L_n}n_{p0} + \frac{D_p}{L_p}p_{n0}\right)\left(e^{eV/k_BT} - 1\right)$$

This is in fact one of the standard forms for the ideal diode equation, which describes the current-voltage relationship for high-quality pn junction diodes.
We have "derived" this result using simply the basic ideas about carrier concentrations from class, plus dimensional analysis, in problems 5 and 6.

(Rest of page blank.)

## Index terms

Problem Set 6 solutions, PS6, problem 8.51, problem 8.54, problem 3, problem 4, problem 5, problem 6, maximum power transfer, Thevenin impedance Z_Th, Z_s, deactivate source, 4 parallel j2, Z_s = 0.8 - j2.4, Z_L = Z_s* = 0.8 + j2.4, V_oc, voltage divider, V_s = 8.94 e^{j63.43}, P_av(max) = |V_s|^2/(8 R_L), 12.5 W, bridge circuit, mesh currents I_1, I_2, outer loop KVL, I_2 - I_1 = 2 mA, I_1 = -1.37 + j0.076 mA, I_2 = 0.63 + j0.076 mA, V_oc = 4 I_1 - j6 I_2, 6.1 angle -145.3, Z_s = (4 - j6) parallel (8 - j2), 3.3 - j2.4 kohm, Z_L = 3.3 + j2.4 kohm, 1.41 mW, hole concentration, density of states g_v(E), Fermi function, substitution u = E_v - E, Boltzmann approximation, 1/(1+x) ~ 1 - x, Gamma integral sqrt(pi)/2 (k_B T)^{3/2}, effective density of states, p = 2(m_v* k_B T / 2 pi hbar^2)^{3/2} exp, n = p, E_c - E_F = E_g/2 - (3/4) k_B T ln(m_v*/m_c*), 0.5673 eV, intrinsic concentration n_i, 9.47e9 cm^-3, 9.473e15 m^-3, 9.477e15 m^-3, k_B = 8.617e-5 eV/K, k_B = 1.381e-23 J/K, hbar = 1.055e-34, Si, band diagram, quasi-Fermi levels E_F,n, E_F,p, eV separation, n_p = n_p0 exp(eV/kT), p_n = p_n0 exp(eV/kT), ideal diode equation, J(V) = (A_1 n_p0 + A_2 p_n0)(exp(eV/kT) - 1), dimensional analysis, units C m/s, A/m^2, diffusion constant m^2/s, diffusion current, diffusion lifetime tau, diffusion length L = sqrt(D tau), A_1 = q sqrt(D_n/tau_n), A_1 = e D_n / L_n, A_2 = e D_p / L_p, sign of A_1 A_2, electron injection, hole injection, Shockley equation
