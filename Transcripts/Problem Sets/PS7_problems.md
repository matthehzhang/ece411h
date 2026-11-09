---
course: ECE 411H
kind: problem-set
source: Problem Sets/ECE_411H_PS7_F26.pdf
source_pages: 2
author: Prof. Ed Yu
unit: exam2
topics: [resonance, resonant-frequency, rlc-circuit, transfer-function, bode-plot, straight-line-approximation, standard-form, passive-filter, lowpass, highpass, cutoff-frequency, decoupling-capacitor, parasitic-inductance, esr, esl, pcb-parasitics]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; text layer via pdftotext -layout where present
---

# Problem Set 7 — ECE 411H: Circuit Theory (Honors), Fall 2026

**Summary**
Seven problems on frequency response (Chapter 9). Problems 1–6 are textbook problems (9.2, 9.6, 9.18, 9.20, 9.31, 9.34): resonant frequency of a C-in-series-with-(L‖R) circuit, transfer function and the purely-real frequency for a C–L1–L2–R ladder, six Bode-plot transfer functions (two with second-order/quadratic factors), and two passive filters (an RC–CR two-stage filter and a C–(L‖R) highpass) requiring standard form, spectral plots, cutoff frequency, and asymptotic slopes. Problem 7 is an instructor application problem on decoupling capacitors: writing $v_o = f_1(\omega)V_i + f_2(\omega)i_L(\omega)$ with PCB trace parasitics $L_p$, $R_p$, with and without $C_d$, the conditions on $f_1, f_2$, Bode plots of each, the effect of increasing $C_d$, and the ESR/ESL model of a real capacitor (impedance, Bode plots, range of ideal behavior). Core Exam-2 material: Bode plots, standard form, corner frequencies, filters.

Due date: Mo 11/02/2026. Due online (Canvas) by start of class on due date.

## Page 1

Header: DUE DATE: Mo 11/02/2026. DUE ONLINE (CANVAS) BY START OF CLASS ON DUE DATE.
Title line: Problem Set 7 — ECE 411H: Circuit Theory (Honors) — Fall 2026.

### 1. Resonant frequency of RLC circuit.

**9.2** Determine the resonant frequency of the circuit shown in Fig. P9.2, given that $R = 100\ \Omega$, $L = 5$ mH, and $C = 1\ \mu$F.

**Figure P9.2: Circuit for Problem 9.2.** Two-terminal network. Two open-circle input terminals on the left (upper and lower). From the upper terminal, a capacitor $C$ in series along the top wire to a node. From that node, two parallel branches go down to the bottom wire: an inductor $L$ (left branch) and a resistor $R$ (right branch). The bottom wire returns to the lower input terminal. Topology: $C$ in series with the parallel combination ($L \parallel R$).

### 2. RLC circuit transfer function.

**9.6** For the circuit shown in Fig. P9.6, determine (a) the transfer function $\mathbf{H} = \mathbf{V}_o/\mathbf{V}_i$ and (b) the frequency $\omega_0$ at which $\mathbf{H}$ is purely real.

**Figure P9.6: Circuit for Problem 9.6.** Two-port ladder. Input port on the left: terminals marked + (top) and − (bottom) with $\mathbf{V}_i$. Top wire from the + input: capacitor $C$ (series), then a node; from that node an inductor $L_1$ goes down (shunt) to the bottom wire; the top wire continues through inductor $L_2$ (series) to the output node; from the output node a resistor $R$ goes down (shunt) to the bottom wire. Output port on the right: + (top) and − (bottom) with $\mathbf{V}_o$ across $R$. Bottom wire is common. Topology: series $C$, shunt $L_1$, series $L_2$, shunt $R$ (output taken across $R$).

### 3. Bode plots 1.

**9.18** Generate Bode magnitude and phase plots (straight-line approximations) for the following voltage transfer functions.

(a) $\mathbf{H}(\omega) = \dfrac{30(10 + j\omega)}{(200 + j2\omega)(1000 + j2\omega)}$

(b) $\mathbf{H}(\omega) = \dfrac{j100\omega}{(100 + j5\omega)(100 + j\omega)^2}$

(c) $\mathbf{H}(\omega) = \dfrac{(200 + j2\omega)}{(50 + j5\omega)(1000 + j\omega)}$

### 4. Bode plots 2.

**9.20** Generate Bode magnitude and phase plots (straight-line approximations) for the following voltage transfer functions.

(a) $\mathbf{H}(\omega) = \dfrac{j5\times 10^3\,\omega\,(20 + j2\omega)}{(2500 - \omega^2 + j20\omega)}$

(b) $\mathbf{H}(\omega) = \dfrac{512(1 + j\omega)(4 + j40\omega)}{(256 - \omega^2 + j32\omega)^2}$

(c) $\mathbf{H}(\omega) = \dfrac{j(10 + j\omega)\times 10^8}{(20 + j\omega)^2(500 + j\omega)(1000 + j\omega)}$

### 5. Passive filters 1.

**9.31** For the circuit shown in Fig. P9.31:

(a) Obtain an expression for $\mathbf{H}(\omega) = \mathbf{V}_o/\mathbf{V}_i$ in standard form.

(b) Generate spectral plots for the magnitude and phase of $\mathbf{H}(\omega)$, given that $R_1 = 1\ \Omega$, $R_2 = 2\ \Omega$, $C_1 = 1\ \mu$F, and $C_2 = 2\ \mu$F.

(c) Determine the cutoff frequency $\omega_c$ and the slope of the magnitude (in dB) when $\omega/\omega_c \ll 1$ and when $\omega/\omega_c \gg 1$.

**Figure P9.31: Circuit for Problem 9.31.** Two-port ladder. Input port on the left (+ top, − bottom, $\mathbf{V}_i$). Top wire: resistor $R_1$ (series), then a node; from that node a capacitor $C_1$ goes down (shunt) to the bottom wire; the top wire continues through capacitor $C_2$ (series) to the output node; from the output node a resistor $R_2$ goes down (shunt) to the bottom wire. Output port on the right (+ top, − bottom, $\mathbf{V}_o$ across $R_2$). Bottom wire common. Topology: series $R_1$, shunt $C_1$, series $C_2$, shunt $R_2$.

### 6. Passive filters 2.

**9.34** For the circuit shown in Fig. P9.34:

(a) Obtain an expression for $\mathbf{H}(\omega) = \mathbf{V}_o/\mathbf{V}_i$ in standard form.

(b) Generate spectral plots for the magnitude and phase of $\mathbf{H}(\omega)$, given that $R = 10\ \Omega$, $L = 1$ mH, and $C = 10\ \mu$F.

(c) Determine the cutoff frequency $\omega_c$ and the slope of the magnitude (in dB) when $\omega/\omega_c \ll 1$.

**Figure P9.34: Circuit for Problem 9.34.** Two-port. Input port on the left (+ top, − bottom, $\mathbf{V}_i$). Top wire: capacitor $C$ (series), then the output node. From the output node two shunt branches go down to the bottom wire: inductor $L$ (left) and resistor $R$ (right), in parallel. Output port on the right (+ top, − bottom, $\mathbf{V}_o$ across $L \parallel R$). Bottom wire common. Topology: series $C$, shunt ($L \parallel R$).

(see next page for problem 7)

## Page 2

Header: DUE DATE: Mo 11/02/2026. DUE ONLINE (CANVAS) BY START OF CLASS ON DUE DATE.

### 7. (Decoupling capacitors — application)

ICs (especially digital logic ICs that switch output states quickly) often include a line in the datasheet recommending that a decoupling capacitor be placed connecting the power and ground pins. Let's consider why this capacitor is used and when it is useful.

Note that, generally speaking, any PCB trace has some parasitic trace inductance that increases with length (and other parameters that we will ignore). PCB traces also have some parasitic resistance and capacitance, but we will ignore these here.

**Figure 7.1. Circuit with decoupling capacitor $C_d$ used for parts (a)–(d).** (Hand-drawn, black ink with red annotation.) Left: an independent voltage source $V_i$ (circle with + on top, − on bottom), − terminal on the bottom wire. From the + terminal the top wire passes through an inductor $L_p$ then a resistor $R_p$ in series; these two elements are enclosed in a red box labeled "Board Parasitics" (red handwriting). After $R_p$ the top wire reaches a node labeled $v_o$. From the $v_o$ node a capacitor $C_d$ goes down (shunt) to the bottom wire. The top wire continues right to an independent current source $i_L(t)$ (circle with arrow pointing DOWN, i.e., the load draws current $i_L(t)$ from the $v_o$ node down to the bottom wire). Bottom wire common to the source −, $C_d$, and the current source. Topology: $V_i$ → $L_p$ → $R_p$ → node $v_o$; at $v_o$, shunt $C_d$ and shunt load current sink $i_L(t)$.

**Figure 7.2. A more complete model for the decoupling capacitor shown in Figure 7.1, to be used in part (e).** (Hand-drawn.) Left red box labeled "Ideal": a single capacitor symbol labeled $C$. A double arrow "⇒" points to the right red box labeled "Model": a series chain of resistor $R_{ESR}$, inductor $L_{ESL}$, and capacitor $C$ (left to right), i.e., the real capacitor is modeled as $R_{ESR}$ + $L_{ESL}$ + $C$ in series.

(a) Write the following expressions for $v_o$ using phasors and in the form
$$v_o = f_1(\omega)V_i + f_2(\omega)\,i_L(\omega)\,.$$
Assume that $V_i$ doesn't vary with time and that $i_L$ does vary with time.

  i. Write the expression for $v_o$ when there is no decoupling capacitor $C_d$.

  ii. Write the expression for $v_o$ when there is a decoupling capacitor $C_d$.

(b) Good decoupling capacitors ensure that $v_o = V_i$ over a wide range of values for $i_L$. What are the mathematical conditions or inequalities that must be satisfied by $f_1(\omega)$ and $f_2(\omega)$ to ensure that $v_o = V_i$ when the decoupling capacitor is present?

(c) On a single set of axes, draw the magnitude Bode plots for $f_1(\omega)$ and $f_2(\omega)$ when $C_d$ is included. Over what frequencies does the decoupling capacitor work as intended?

(d) How does increasing $C_d$ affect the range of frequencies for which the decoupling capacitor works as intended?

(e) Physically large capacitors have equivalent series resistances and inductances (ESR and ESL, respectively) that affect the model that should be used when analyzing a circuit with a large capacitor.

  i. What is the impedance of an ideal capacitor with capacitance $C$?

  ii. Draw the magnitude Bode plot for an ideal capacitor.

  iii. What is the impedance of a capacitor with nonzero ESL and ESR, as shown in Figure 7.2?

  iv. Draw the magnitude Bode plot for a capacitor including $R_{ESR}$ and $L_{ESL}$.

  v. Over what range of frequencies does a capacitor with nonzero $R_{ESR}$ and $L_{ESL}$ behave most similarly to an ideal capacitor?

  vi. Given that $R_{ESR}$ and $L_{ESL}$ generally increase with capacitor value and size, how does the range of frequencies for which a capacitor exhibits ideal behavior (or close to it) change as the capacitor value and size increase?

## Index terms

Problem Set 7, PS7, problem 1, problem 2, problem 3, problem 4, problem 5, problem 6, problem 7, 9.2, 9.6, 9.18, 9.20, 9.31, 9.34, resonant frequency, omega_0, RLC circuit, C in series with L parallel R, transfer function H = V_o/V_i, purely real H, Figure P9.2, Figure P9.6, Figure P9.31, Figure P9.34, Bode magnitude plot, Bode phase plot, straight-line approximation, standard form, corner frequency, quadratic factor, second-order factor, 2500 - omega^2 + j20 omega, 256 - omega^2 + j32 omega, passive filter, two-stage RC filter, highpass filter, cutoff frequency omega_c, slope in dB, dB/decade, spectral plots, R1 = 1 ohm, R2 = 2 ohm, C1 = 1 uF, C2 = 2 uF, R = 10 ohm, L = 1 mH, C = 10 uF, R = 100 ohm, L = 5 mH, C = 1 uF, decoupling capacitor C_d, bypass capacitor, PCB trace inductance, parasitic inductance L_p, parasitic resistance R_p, board parasitics, Figure 7.1, Figure 7.2, f_1(omega), f_2(omega), v_o = f_1 V_i + f_2 i_L, superposition, load current i_L(t), ESR, ESL, R_ESR, L_ESL, capacitor model, self-resonant frequency, impedance of ideal capacitor 1/(j omega C), ideal capacitor Bode plot
