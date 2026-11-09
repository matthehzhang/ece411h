---
course: ECE 411H
kind: problem-set
source: Problem Sets/ECE_411H_PS5_F26.pdf
source_pages: 2
author: Prof. Ed Yu
unit: exam2
topics: [average-value, rms-value, periodic-signals, complex-power, conservation-of-complex-power, op-amp, ac-power, load-resistor, inductor-esr, triangular-waveform, switch-mode-power-supply, conduction-loss]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; text layer via pdftotext -layout where present
---

# Problem Set 5 — ECE 411H: Circuit Theory (Honors), Fall 2026

**Summary**
Five problems on ac power. Problems 1–4 are textbook problems (Ulaby/Maharbiz/Furse numbering 8.16, 8.20, 8.27, 8.38): average/rms of periodic waveforms, complex power per element with conservation check, complex power S of an RL load fed by a current source through a two-port network, and ac power delivered to an RL load driven by an inverting op-amp with RC feedback. Problem 5 is an application problem written by the instructor on conduction loss in an inductor's equivalent series resistance (ESR) with a triangular (dc + ripple) current, as in a switch-mode power supply. All of this is Exam-2 material (Chapter 8 ac power: rms, average power, complex power, conservation).

Due date: Mo 10/05/2026. Due online (Canvas) by start of class on due date.

## Page 1

Header: DUE DATE: Mo 10/05/2026. DUE ONLINE (CANVAS) BY START OF CLASS ON DUE DATE.
Title line: Problem Set 5 — ECE 411H: Circuit Theory (Honors) — Fall 2026.

### 1. Average and rms values of periodic signals.

**8.16** Determine the average and rms values of the following periodic waveforms:

(a) $v(t) = |12\cos(\omega t + \theta)|$ V

(b) $v(t) = 4 + 6\cos(2\pi f t + \phi)$ V

(c) $v(t) = 2\cos\omega t - 4\sin(\omega t + 30^\circ)$ V

(d) $v(t) = 9\cos\omega t\,\sin(\omega t + 30^\circ)$ V

### 2. Calculation of complex power 1.

**8.20** In the circuit shown in Fig. P8.20, $v(t) = 40\cos(10^5 t)$ V, $R_1 = 100\ \Omega$, $R_2 = 500\ \Omega$, $C = 0.1\ \mu$F, and $L = 0.5$ mH. Determine the complex power for each passive element, and verify that conservation of energy is satisfied.

**Figure P8.20: Circuit for Problem 8.20.** An independent voltage source $v(t)$ (circle, + at top, − at bottom) is on the left, its bottom terminal on the bottom rail. From the top of the source a wire runs right through resistor $R_1$ (in series, on the top wire) to a top node. From that top node two branches go down to the bottom rail: (i) a capacitor $C$ (middle branch, vertical), and (ii) a series combination of resistor $R_2$ (upper) and inductor $L$ (lower) (right branch, vertical). The bottom rail connects the source −, the capacitor's bottom, and the inductor's bottom. So: source → $R_1$ → node; node to ground via $C$ in parallel with ($R_2$ + $L$).

### 3. Calculation of complex power 2.

**8.27** Determine $\mathbf{S}$ for the RL load in the circuit of Fig. P8.27, given that $\mathbf{I}_s = 4\angle 0^\circ$ A, $R_1 = 10\ \Omega$, $R_2 = 5\ \Omega$, $\mathbf{Z}_C = -j20\ \Omega$, $R = 10\ \Omega$, and $\mathbf{Z}_L = j20\ \Omega$.

**Figure P8.27: Circuit for Problem 8.27.** Three vertical branches in parallel between a top rail and a bottom rail, from left to right: a capacitor labeled $\mathbf{Z}_C$, a resistor $R_1$, and an independent current source $\mathbf{I}_s$ (circle with arrow pointing UP, i.e., current injected into the top rail). From the right end of the top rail a series resistor $R_2$ leads to terminal $a$ (open circle). The bottom rail extends to terminal $b$ (open circle, lower right). Between $a$ and $b$ is the "Load" (shaded box): a resistor $R$ (top) in series with an inductor $\mathbf{Z}_L$ (bottom), i.e., the RL load hangs from $a$ down to $b$.

### 4. Ac power delivered to load resistor.

**8.38** Determine the amount of power delivered to $R_L$ in the circuit of Fig. P8.38, given that $v_{in}(t) = 0.5\cos 2000t$ V, $R_1 = 1$ k$\Omega$, $R_2 = 10$ k$\Omega$, $C = 0.1\ \mu$F, $R_L = 1$ k$\Omega$, and $L = 0.2$ H.

**Figure P8.38: Op-amp circuit for Problem 8.38.** Independent voltage source $v_{in}(t)$ (circle, + on top, − on bottom) with its − terminal grounded (ground symbol). Its + terminal connects through resistor $R_1$ to the inverting (−) input of an op amp (triangle, − input on top, + input on bottom, output to the right). The non-inverting (+) input is tied to ground. Feedback from the op-amp output back to the inverting input consists of two parallel elements: a resistor $R_2$ (upper feedback path) and a capacitor $C$ (lower feedback path, between $R_2$ and the op amp). The op-amp output node is labeled $v_{out}$ (open circle terminal to the right). From the output node a current $\mathbf{I}_L$ (arrow pointing down) flows through a load consisting of resistor $R_L$ (upper) in series with inductor $L$ (lower) to ground. Three ground symbols: under the source, under the + input, and under $L$.

### 5. Application – inductor losses

One common source of loss in filters, transformers, or other circuits with discrete inductors is the loss due to the resistance of the wires winding around the inductor core. Consider a triangular waveform $i(t)$ as shown in Figure 1(a), as might be used in a switched-mode power supply. The waveform consists of a constant baseline $I$ and a superimposed triangular ripple with amplitude $rI$.

**Figure 1. (a) Periodic triangular waveform $i(t)$ for Problem 5. (b) Equivalent circuit for an inductor with equivalent series resistance $R_{ESR}$.**
- (a) Axes: vertical axis $i(t)$, horizontal axis $t$. A dashed horizontal line at level $I$ (labeled $I$ on the left axis). The red waveform is a symmetric triangle wave centered on the dashed line: it rises linearly from $I$ to a peak of $I + rI$, falls linearly through $I$ to a trough of $I - rI$, and repeats; about 2.5 cycles are drawn starting at $t = 0$ at level $I$ with positive slope. A bracket at the right marks the peak-to-baseline height as $rI$ (from the dashed line up to a peak). A horizontal bracket at the bottom between two consecutive troughs is labeled $T$ (the period). The triangle has equal rise and fall times (50% duty, symmetric).
- (b) Two-terminal equivalent circuit: open-circle terminal on the left, series resistor $R_{ESR}$, series inductor $L$, open-circle terminal on the right.

(a) Consider a generic resistor $R$ with current $i(t)$ as shown in Figure 1(a) flowing through it. What is the (i) instantaneous power and (ii) average power dissipated in the resistor? Your answers should be in terms of $R$, $I$, and $r$.

(b) Now suppose $i(t)$ as shown in Figure 1(a) flows through the inductor equivalent circuit shown in Figure 1(b). What is the average power dissipated in the resistor $R_{ESR}$? Your answer should be in terms of $R_{ESR}$, $I$, and $r$.

## Page 2

Header: DUE DATE: Mo 10/05/2026. DUE ONLINE (CANVAS) BY START OF CLASS ON DUE DATE.

(c) In switch-mode power supplies, $r$ is generally inversely proportional to $L$. Assuming that the current $i(t)$ in Figure 1(a) is flowing through the inductor equivalent circuit shown in Figure 1(b) and that $r$ is exactly inversely proportional to $L$, by what factor does the average conduction-related loss in the inductor equivalent circuit change if $L$ is increased by a factor of 2? Assume that for the original value of the inductor, $r = 0.2$, and that $R_{ESR}$ increases by 40% when $L$ is doubled.

(Rest of page 2 is blank.)

## Index terms

Problem Set 5, PS5, problem 1, problem 2, problem 3, problem 4, problem 5, 8.16, 8.20, 8.27, 8.38, average value, rms value, periodic waveform, rectified cosine, dc offset, phasor addition, product of sinusoids, complex power, S, conservation of energy, conservation of complex power, Figure P8.20, Figure P8.27, Figure P8.38, RL load, current source, Thevenin, op amp, inverting amplifier, RC feedback, power delivered to load, R_L, inductor losses, equivalent series resistance, R_ESR, triangular waveform, ripple, rI, baseline current I, period T, instantaneous power, average power, switch-mode power supply, conduction loss, r inversely proportional to L, L doubled, 40% increase in R_ESR, r = 0.2
