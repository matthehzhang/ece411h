---
course: ECE 411H
kind: problem-set
source: Problem Sets/ECE_411H_PS8_F26.pdf
source_pages: 1
author: Prof. Ed Yu
unit: exam2
topics: [series-rlc, bandpass-filter, quality-factor, bandwidth, half-power-frequencies, active-filter, op-amp-filter, inverting-amplifier, lowpass, highpass, bandpass, standard-form, bode-plot, corner-frequency, cascaded-filters, roll-off, impulse-function, delta-function, sifting-property]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; text layer via pdftotext -layout where present
---

# Problem Set 8 — ECE 411H: Circuit Theory (Honors), Fall 2026

**Summary**
Six problems: series RLC bandpass parameters ($\omega_0$, $Q$, $B$, $\omega_{c1}$, $\omega_{c2}$) and whether $Q$ can be doubled at fixed $\omega_0$ and $R$ (9.26); two active op-amp filters requiring $\mathbf{H}(\omega)$ in standard form, spectral plots, filter type and max gain (9.38 with RC feedback on the inverting input and 9.39 with a two-stage RC network feeding a buffer); active lowpass design with gain 4, corner 1 kHz, −60 dB/decade (9.42); an analytical Bode-plot problem m9.2 for an inverting op-amp with $R_1 \parallel C_1$ at the input and $R_2 \parallel C_2$ in feedback, including $f$-domain form, Bode plots, and asymptotes/corner frequencies read from the plot; and three delta-function integrals (12.2). Exam-2 material (active filters, Bode plots) plus the start of the impulse/Laplace unit.

Due date: Mo 11/09/2026. Due online (Canvas) by start of class on due date.

## Page 1

Header: DUE DATE: Mo 11/09/2026. DUE ONLINE (CANVAS) BY START OF CLASS ON DUE DATE.
Title line: Problem Set 8 — ECE 411H: Circuit Theory (Honors) — Fall 2026.

### 1. Passive filter circuit parameters.

**9.26** The element values of a series RLC bandpass filter are $R = 5\ \Omega$, $L = 20$ mH, and $C = 0.5\ \mu$F.

*(a) Determine $\omega_0$, $Q$, $B$, $\omega_{c_1}$, and $\omega_{c_2}$. (The asterisk marks a problem with an answer in the back of the textbook.)

(b) Is it possible to double the magnitude of $Q$ by changing the values of $L$ and/or $C$ while keeping $\omega_0$ and $R$ unchanged? If yes, propose such values, and if no, why not?

### 2. Active filters 1.

**9.38** For the op-amp circuit of Fig. P9.38:

(a) Obtain an expression for $\mathbf{H}(\omega) = \mathbf{V}_o/\mathbf{V}_s$ in standard form.

(b) Generate spectral plots for the magnitude and phase of $\mathbf{H}(\omega)$, given that $R_1 = 99$ k$\Omega$, $R_2 = 1$ k$\Omega$, and $C = 0.1\ \mu$F.

(c) What type of filter is it? What is its maximum gain?

**Figure P9.38: Circuit for Problem 9.38.** Op amp (triangle, − input on top, + input on bottom, output to the right). Independent voltage source $\mathbf{V}_s$ (circle, + on top, − on bottom) with its − terminal on the bottom wire, which is grounded (ground symbol below the source). The + terminal of $\mathbf{V}_s$ connects directly to the non-inverting (+) input of the op amp. The inverting (−) input node connects (via a wire running left) down through resistor $R_2$ to the bottom (ground) wire. Feedback from the op-amp output to the inverting (−) input consists of two parallel elements: capacitor $C$ (outer/upper loop) and resistor $R_1$ (inner loop, just below $C$). The output is taken between the op-amp output terminal (upper open circle, +) and the bottom wire (lower open circle, −), labeled $\mathbf{V}_o$. Topology: non-inverting amplifier with source on the + input; $R_2$ from − input to ground; $R_1 \parallel C$ from output to − input.

### 3. Active filters 2.

**9.39** For the op-amp circuit of Fig. P9.39:

*(a) Obtain an expression for $\mathbf{H}(\omega) = \mathbf{V}_o/\mathbf{V}_i$ in standard form.

(b) Generate spectral plots for the magnitude and phase of $\mathbf{H}(\omega)$, given that $R_1 = R_2 = 100\ \Omega$, $C_1 = 10\ \mu$F, and $C_2 = 0.4\ \mu$F.

(c) What type of filter is it? What is its maximum gain?

**Figure P9.39: Circuit for Problems 9.39 and 9.40.** Independent voltage source $\mathbf{V}_s$ (circle, + top, − bottom), − terminal on the bottom wire. From the + terminal: resistor $R_1$ (series) to a middle node; from the middle node, resistor $R_2$ (series) continues to a second node which connects to the non-inverting (+) input of the op amp. Also from the middle node (between $R_1$ and $R_2$), a capacitor $C_1$ goes UP to a wire that runs across the top and connects to the op-amp output (so $C_1$ connects the $R_1$–$R_2$ junction to the output node). From the second node (between $R_2$ and the + input), a capacitor $C_2$ goes down (shunt) to the bottom wire. The op amp's inverting (−) input is connected directly to the output (unity-gain follower/buffer). Output $\mathbf{V}_o$ is taken between the op-amp output (upper open circle, +) and the bottom wire (lower open circle, −). Topology: Sallen–Key style two-stage RC with $C_1$ feedback to the output and a voltage follower.

### 4. Active filter design 1.

**9.42** Design an active lowpass filter with a gain of 4, a corner frequency of 1 kHz, and a gain roll-off rate of −60 dB/decade.

### 5. Bode plot analysis.

Solve the problem below analytically.

**m9.2 Bode Plots:** For the circuit in Fig. m9.2:

(a) Determine the voltage transfer function $\mathbf{H}(\omega)$ of the filter circuit. Write your finished result in standard form for creating a Bode plot.

(b) Substitute $\omega = 2\pi f$ to express the voltage transfer function in terms of oscillation frequency $f$ in Hz.

(c) Generate Bode magnitude and phase plots for $\mathbf{H}(f)$ using oscillation frequency $f$ as the independent variable. Use the following component values: $R_1 = 3.3$ k$\Omega$, $R_2 = 10$ k$\Omega$, $C_1 = 0.01\ \mu$F, and $C_2 = 0.1\ \mu$F.

**Figure m9.2 Circuit for Problem m9.2.** Independent ac voltage source $v_s$ (circle with sine symbol, + top, − bottom), − terminal grounded (ground symbol). From the + terminal of $v_s$, a parallel combination of resistor $R_1$ (upper branch) and capacitor $C_1$ (lower branch) connects in series to the inverting (−) input of the op amp. The non-inverting (+) input is grounded (ground symbol). Feedback from the op-amp output to the inverting input is a parallel combination of resistor $R_2$ (upper branch) and capacitor $C_2$ (lower branch). Output node is labeled $v_{out}$ (open circle to the right). Topology: inverting amplifier with $Z_{in} = R_1 \parallel C_1$ and $Z_f = R_2 \parallel C_2$.

(d) Determine the following filter circuit properties by inspecting the Bode plot:

  (1) Low-frequency asymptotes for magnitude and phase

  (2) High-frequency asymptotes for magnitude and phase

  (3) Corner frequencies (this filter circuit has two such frequencies)

### 6. Simple integrals.

**12.2** Evaluate each of the following integrals:

(a) $G_1 = \displaystyle\int_{-\infty}^{\infty} (3t^3 - 4t^2 + 3)\,[\delta(t) + 2\delta(t-2)]\,dt$.

(b) $G_2 = \displaystyle\int_{-4}^{4} 2(e^{-3t} + 1)\,[\delta(t) - 2\delta(t-2)]\,dt$.

(c) $G_3 = \displaystyle\int_{-12}^{16} 4[t\sin(2\pi t) - 1]\,[\delta(t-1) + \delta(t-6)]\,dt$.

## Index terms

Problem Set 8, PS8, problem 1, problem 2, problem 3, problem 4, problem 5, problem 6, 9.26, 9.38, 9.39, 9.42, m9.2, 12.2, series RLC bandpass filter, resonant frequency omega_0, quality factor Q, bandwidth B, half-power frequencies omega_c1, omega_c2, R = 5 ohm, L = 20 mH, C = 0.5 uF, double Q, active filter, op amp, non-inverting amplifier, R1 = 99 kohm, R2 = 1 kohm, C = 0.1 uF, Figure P9.38, Figure P9.39, Figure m9.2, voltage follower, buffer, Sallen-Key, R1 = R2 = 100 ohm, C1 = 10 uF, C2 = 0.4 uF, filter type, maximum gain, standard form, spectral plots, active lowpass design, gain of 4, corner frequency 1 kHz, -60 dB/decade, cascaded stages, inverting amplifier, R1 parallel C1, R2 parallel C2, R1 = 3.3 kohm, R2 = 10 kohm, C1 = 0.01 uF, C2 = 0.1 uF, omega = 2 pi f, Bode plot in Hz, low-frequency asymptote, high-frequency asymptote, corner frequencies, two corner frequencies, impulse function, delta function, sifting property, G_1, G_2, G_3, integration limits
