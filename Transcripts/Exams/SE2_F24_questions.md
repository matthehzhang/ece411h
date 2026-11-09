---
course: ECE 411H
kind: past-exam
source: Exam Preparation Materials/ECE_411H_Exam_2_questions+histogram_F24.pdf
source_pages: 3
author: Prof. Ed Yu
unit: exam2
topics: [semester-exam-2, low-pass-filter, acceptor-doping, fermi-level, fermi-distribution, pn-junction, series-rlc-resonance, maximum-power-transfer, impedance-matching, rc-low-pass, cutoff-frequency, bode-plot, sallen-key, second-order-low-pass, butterworth-filter, score-histogram]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
---

# ECE 411H Semester Exam 2 — Fall 2024 (questions + score histogram)

**Summary.** The Fall 2024 Semester Exam 2 (13 November 2024, 70 minutes, 4 problems × 25 points). Problem 1: four short conceptual questions (series-RLC element for low-pass, why acceptors move $E_F$ toward the valence band, Fermi-function explanation of diode exponential I–V, which series-RLC single-element outputs can exceed $|H| = 1$). Problem 2: AC maximum power transfer from a source ($\mathbf{V}_s$, $R_s$) to a load ($R'$, shunt $C$, series $L$, $R$) — average power with $C = R' = 0$, then the $C$ and $R'$ that maximize power. Problem 3: RC low-pass with source resistance — filter type, cutoff frequency for two $R_s$ values, Bode plots. Problem 4: Sallen-Key (unity-gain) second-order low-pass — factored transfer function, filter type, Bode plots, and the $C_1/C_2$ ratio for a Butterworth response. Page 3: score histogram (mean 75.1, median 78.25, N = 36). Companion: `SE2_F24_short_answers.md`.

## Page 1

SEMESTER EXAM 2 — ECE 411H — 13 November 2024

PLEASE ATTEMPT ALL PROBLEMS AND SHOW ALL WORK!
WRITE ALL EXAM SOLUTIONS IN THE SPACES PROVIDED ON THE EXAM ANSWER SHEETS. YOU MAY USE THE BACK OF EACH PAGE FOR SCRATCH, BUT ONLY THE FRONT SIDES WILL BE SCANNED AND GRADED.

The exam questions, answer sheets, and a calculator are allowed; no other materials should be consulted during the exam. No communication with any other student is allowed during the exam. You will have 70 minutes from the start of the exam to complete the exam, followed by ~5 minutes to scan and upload your exam answer sheets to Gradescope.

NOTES: Unless otherwise stated, you may assume all numerical quantities given in the exam problems are known to 3 significant figures, and calculate your answers accordingly. You must show all of your work to receive credit. If you need to make an assumption to answer a question, state it explicitly.

ONLY THE FRONT SIDE OF EACH SHEET WILL BE GRADED.

### Problem 1 [25 points total]

Answer the questions below. Each should require a few sentences or relatively small amount of math at most. You may also include a sketch/picture if necessary.

(a) [6 points] In a series RLC filter circuit, across which single component (R, L, or C) should the output terminals be positioned in order to create a low-pass filter? Explain your answer.

(b) [6 points] Explain why the introduction of acceptor atoms into a semiconductor crystal, e.g., B (3 valence electrons) into Si (4 valence electrons), causes the Fermi level to move closer to the valence-band edge energy of the semiconductor.

(c) [6 points] Explain, in terms of the mathematical form of the Fermi distribution function, why current in a pn junction diode increases exponentially with increasing voltage.

(d) [7 points] Consider a series RLC filter circuit with output terminals positioned across a single component (R, L, or C). For which types of filter circuits constructed in this manner can the maximum magnitude of the transfer function be greater than 1? Explain your answer.

### Problem 2 [25 points total]

Consider Circuit SE2-2 at right. The input signal $\mathbf{V}_s$ is a sinusoidal signal with amplitude $V_s$ and angular frequency $\omega$.

**Figure: Circuit SE2-2.** Left to right along the top rail: voltage source $\mathbf{V}_s$ (+ on top) at the far left, then series resistor $R_s$, then an open-circle node (the source/load boundary), then series resistor $R'$, then a node from which capacitor $C$ hangs down (shunt) to the bottom rail, then series inductor $L$, then resistor $R$ hanging down (shunt) to the bottom rail at the far right. The bottom rail is continuous back to the source − terminal (with an open-circle node at the boundary). Brackets under the circuit label the left portion ($\mathbf{V}_s$, $R_s$) "source" and the right portion ($R'$, $C$, $L$, $R$) "load".

(a) Suppose $C = 0$ and $R' = 0$. Calculate the average power transferred to the load circuit as a function of (as needed) $R_s$, $L$, $R$, $V_s$, and $\omega$.

(b) Now suppose $C > 0$ and $R' > 0$. Calculate the values of $C$ and $R'$ that maximize average power transfer to the load circuit. Your answers should be functions of (as needed) $R_s$, $L$, $R$, and $\omega$.

## Page 2

### Problem 3 [25 points total]

Consider Circuits SE2-3 at right. The input voltage is $\mathbf{V}_s$, and the output voltage is $\mathbf{V}_o$.

**Figure: Circuit SE2-3.** Source $\mathbf{V}_s(\omega)$ (+ on top) at left. Top rail: series resistor $R_s$, open-circle node, series resistor $R$, then a node from which capacitor $C$ hangs down (shunt) to the bottom rail. Open output terminals at the right across $C$: upper +, lower −, labeled $\mathbf{V}_o(\omega)$. Bottom rail returns to the source (with an open-circle node).

(a) What type of filter circuit is this? Explain your answer.

(b) Suppose $R_s$ can range from $100\,\Omega$ to $1000\,\Omega$, with $R = 10\,\text{k}\Omega$ and $C = 0.1\,\mu$F. Calculate the cutoff frequency (or frequencies) $\omega_c$, i.e., the frequency (or frequencies) at which $|H(\omega)| \equiv |\mathbf{V}_o/\mathbf{V}_s| = 1/\sqrt{2}$, for (i) $R_s = 100\,\Omega$ and (ii) $R_s = 1000\,\Omega$.

(c) Now suppose $R_s = 0\,\Omega$, $R = 10\,\text{k}\Omega$, and $C = 0.1\,\mu$F. Construct the Bode magnitude and phase plots for this circuit, using linear approximations for low and high frequencies as done in class. For the phase plot, all angles should be plotted in the range $-180° \le \phi \le 180°$. Be sure to label the key values on the vertical and horizontal axes of each plot, and any nonzero slopes in the Bode magnitude plot.

### Problem 4 [25 points total]

Consider Circuit SE2-4 shown below. Assume that the op amp in the circuit always behaves in accordance with the ideal op-amp model.

**Figure: Circuit SE2-4** (Sallen-Key unity-gain low-pass). Source $\mathbf{V}_s(\omega)$ (+ on top, − grounded) at the lower left. From the source +: series resistor $R_1$ to node A; series resistor $R_2$ from node A to node B; node B connects to the op-amp non-inverting (+) input (the + input is drawn on the upper side of the triangle). Capacitor $C_1$ connects node A to the op-amp output node (feedback, drawn across the top). Capacitor $C_2$ connects node B to ground (drawn at the bottom). The op-amp inverting (−) input is tied directly to the output (voltage follower). Output $\mathbf{V}_o(\omega)$ is the op-amp output node (open terminal at right).

(a) Calculate the transfer function $H(\omega) \equiv \mathbf{V}_o/\mathbf{V}_s$ for this circuit. Express your final answer as a product of factors that are each one of the following (as needed): constant, zero@origin, pole@origin, simple zero, simple pole, quadratic zero, or quadratic pole. Your result should be expressed in terms of $R_1$, $R_2$, $C_1$, $C_2$, and $\omega$.

(b) What type of filter is Circuit SE2-4? Explain why it works this way, in terms of the component impedances as functions of frequency.

(c) Construct the Bode magnitude and phase plots for this circuit, using linear approximations for low and high frequencies as done in class. For the phase plot, all angles should be plotted in the range $-180° \le \phi \le 180°$. Be sure to label the key values on the vertical and horizontal axes of each plot, and any nonzero slopes in the Bode magnitude plot.

(d) A "Butterworth filter" is a filter designed to have a very flat response across the filter pass band. For Circuit SE2-4, such a filter would have a transfer function magnitude $M(\omega)$ of the form $M(\omega) = 1\big/\sqrt{1 + (\omega/\omega_p)^4}$. Assuming $R_1 = R_2$, calculate the ratio $C_1/C_2$ that would be required to obtain a transfer function corresponding to a Butterworth filter.

## Page 3

**Figure: score histogram.** Title "ECE 411H Semester Exam 2 scores - Fall 2024". Bar chart; x-axis "Semester Exam 2 score", tick labels every 2 from 0 to 100; y-axis "Frequency" 0 to 6. Printed statistics:

- Mean = 75.1, Median = 78.25, Standard Deviation = 13.8
- P1 = 18.2/25, P2 = 15.7/25, P3 = 23.3/25, P4 = 17.8/25
- Range = 29-98, Number = 36

Bar heights (score bin : count); unlisted bins are 0:

| score | 30 | 52 | 54 | 60 | 64 | 66 | 68 | 74 | 78 | 80 | 82 | 86 | 88 | 94 | 98 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| count | 1 | 1 | 2 | 1 | 2 | 1 | 2 | 3 | 5 | 5 | 4 | 2 | 4 | 2 | 1 |

(Counts sum to 36.) Mode at 78–80 (5 each); one outlier at 30. Note P2 (the power-transfer problem) had the lowest average, 15.7/25; P3 (RC low-pass) the highest, 23.3/25.

## Index terms

Semester Exam 2, Fall 2024, Problem 1, Problem 2, Problem 3, Problem 4, series RLC, low-pass output across C, acceptor atoms, boron, Fermi level, valence band edge, Fermi distribution function, pn junction, exponential current, transfer function magnitude greater than 1, resonance, Circuit SE2-2, source and load, R_s, R', C, L, R, average power transfer, maximum power transfer, impedance matching, conjugate matching, Circuit SE2-3, RC low-pass, source resistance, cutoff frequency, 1/sqrt(2), R = 10 kohm, C = 0.1 uF, R_s = 100 ohm, R_s = 1000 ohm, Bode magnitude plot, Bode phase plot, -180 to 180 degrees, Circuit SE2-4, Sallen-Key, ideal op-amp model, voltage follower, second-order low-pass, quadratic pole, factored transfer function, zero@origin, pole@origin, simple zero, simple pole, Butterworth filter, M(omega) = 1/sqrt(1 + (omega/omega_p)^4), C1/C2 ratio, score histogram, mean 75.1, median 78.25, standard deviation 13.8, N = 36
