---
course: ECE 411H
kind: past-exam
source: Exam Preparation Materials/ECE_411H_Exam_2_questions+histogram_F23.pdf
source_pages: 3
author: Prof. Ed Yu
unit: exam2
topics: [semester-exam-2, quality-factor, n-type-doping, fermi-distribution, pn-junction, band-pass-filter, high-pass-filter, band-reject-filter, transfer-function, bode-plot, inverting-op-amp-filter, parallel-lc, bandwidth, score-histogram]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
---

# ECE 411H Semester Exam 2 — Fall 2023 (questions + score histogram)

**Summary.** The Fall 2023 Semester Exam 2 (08 November 2023, 70 minutes, 4 problems × 25 points). Problem 1 is four short-answer conceptual questions (Q of a series RLC, n-type doping B vs As, Fermi-function explanation of diode exponential I–V, which series-RLC element gives a band-pass output). Problem 2 is a design problem on a 100 Ω series resistor with an unknown shunt element Z (high-pass with ω_c = 1000 rad/s, then band-reject with a series LC notch at 2000 rad/s). Problem 3 is an inverting op-amp filter with R_s–C_s input and R_f ∥ L_f feedback: transfer function in factored form, Bode magnitude and phase plots with slopes, and the ω → ∞ limit. Problem 4 is a series-R / parallel-LC band-pass filter: transfer function, Bode plots, filter type, and effect of R on bandwidth. Page 3 is the score histogram (mean 77.2, median 80, N = 66). Companion file: `SE2_F23_short_answers.md`.

## Page 1

SEMESTER EXAM 2 — ECE 411H — 08 November 2023

PLEASE ATTEMPT ALL PROBLEMS AND SHOW ALL WORK!
WRITE ALL EXAM SOLUTIONS IN THE SPACES PROVIDED ON THE EXAM ANSWER SHEETS. YOU MAY USE THE BACK OF EACH PAGE FOR SCRATCH, BUT ONLY THE FRONT SIDES WILL BE SCANNED AND GRADED.

The exam questions, answer sheets, and a calculator are allowed; no other materials should be consulted during the exam. No communication with any other student is allowed during the exam. You will have 70 minutes from the start of the exam to complete the exam, followed by ~5 minutes to scan and upload your exam answer sheets to Gradescope.

NOTES: Unless otherwise stated, you may assume all numerical quantities given in the exam problems are known to 3 significant figures, and calculate your answers accordingly. You must show all of your work to receive credit. If you need to make an assumption to answer a question, state it explicitly.

ONLY THE FRONT SIDE OF EACH SHEET WILL BE GRADED.

### Problem 1 [25 points total]

Answer the questions below. Each should require a few sentences or relatively small amount of math at most. You may also include a sketch/picture if necessary.

(a) [6 points] Recall that the quality factor $Q$ of a filter is given by $Q = 2\pi\left(W_{stored}/W_{dissipated}\right)\big|_{\omega=\omega_0}$. Based on this definition of $Q$, does a very small value of $R$ in an RLC series filter circuit lead to a high or low value for $Q$? Explain.

(b) [6 points] To create an n-type semiconductor from a crystal of pure Si, would you replace some of the Si atoms with B (boron, 3 valence electrons/atom) or As (arsenic, 5 valence electrons/atom)? Explain your answer.

(c) [6 points] Explain, in terms of the Fermi distribution function and its dependence on energy, why the current in a pn junction diode increases exponentially with voltage $V$, for $V > 0$.

(d) [7 points] In a series RLC filter circuit, across which single component ($R$, $L$, or $C$) should the output terminals be connected to create a band pass filter? Explain your answer.

### Problem 2 [25 points total]

Consider Circuit SE2-2 shown at right. All numerical values given in this problem are exact.

**Figure: Circuit SE2-2.** Voltage source $\mathbf{V}_s$ (+ terminal on top) on the left. From the + terminal, a series resistor labeled $R = 100\,\Omega$ runs along the top rail to a top node. From that top node a rectangular box labeled $\mathbf{Z}$ (unknown element) runs vertically down to the bottom rail. The bottom rail returns to the − terminal of $\mathbf{V}_s$. Open output terminals at the far right are connected across $\mathbf{Z}$: upper terminal marked +, lower terminal marked −, labeled $\mathbf{V}_{out}$. (Voltage-divider topology: series $R$, shunt $\mathbf{Z}$, output across $\mathbf{Z}$.)

(a) Suppose for this part of the problem that the circuit element $\mathbf{Z}$ in Circuit SE2-2 consists of a single component, i.e., a resistor, a capacitor, or an inductor. For the circuit to function as a high-pass filter with corner frequency $\omega_c = 1000$ rad/s, what type of component should $\mathbf{Z}$ be (resistor, capacitor, or inductor), and what should its value be?

(b) Now suppose that $\mathbf{Z}$ consists of 2 individual components connected in series with each other. For the circuit to function as a band-reject filter, what should those components be (choose two from resistor, capacitor, and inductor). Explain your answer.

(c) For the two components you chose in part (b), compute numerical values of the components that will yield $\mathbf{V}_{out} = 0$ at $\omega = 2000$ rad/s. Are there other component values for which $\mathbf{V}_{out} = 0$ as well? Explain why or why not.

## Page 2

### Problem 3 [25 points total]

Consider Circuit SE2-3 shown at right. All the numerical values given in this problem are exact, and the op amp is always in its linear region of behavior.

**Figure: Circuit SE2-3.** Inverting op-amp filter. Source $\mathbf{V}_s$ (+ on top, − terminal grounded) on the left. From the source + terminal: series resistor $R_s$, then series capacitor $C_s$, into the inverting (−) input of the op amp. The non-inverting (+) input is connected to ground. Op amp supplies labeled $+V_{cc}$ (top) and $-V_{cc}$ (bottom). The feedback network from the op-amp output back to the − input consists of two parallel branches: resistor $R_f$ (upper branch) and inductor $L_f$ (lower branch), i.e., $R_f \parallel L_f$. The output $\mathbf{V}_{out}$ is taken between the op-amp output node (+, open terminal at right) and ground (−).

(a) Calculate the transfer function $\mathbf{H}(\omega) = \mathbf{V}_{out}/\mathbf{V}_s$ in terms of $R_s$, $C_s$, $R_f$, $L_f$, and $\omega$. Your answer should be in an algebraic form that makes it very straightforward to identify the factors corresponding to any zeros or poles that are present.

(b) Suppose $R_s = 100\,\Omega$, $C_s = 1\,\mu$F, $R_f = 1\,\text{k}\Omega$, and $L_f = 10\,\text{mH}$. Construct the Bode magnitude and phase plots for this circuit, using linear approximations as done in class. Be sure to label the key values on the vertical and horizontal axes of each plot, and any nonzero slopes in BOTH the Bode magnitude plot and the Bode phase plot.

(c) What is the value, in terms of (as needed) $R_s$, $C_s$, $R_f$, and $L_f$, of $M(\omega) = |\mathbf{H}(\omega)|$ as $\omega \to \infty$? Does this result make sense to you? Explain why or why not.

### Problem 4 [25 points total]

Consider Circuit SE2-4 shown at right. All numerical values given in this problem are exact.

**Figure: Circuit SE2-4.** Source $\mathbf{V}_s$ (+ on top) at left. Series resistor $R$ on the top rail from the source + terminal to a top node. From the top node, two shunt branches in parallel run down to the bottom rail: a capacitor $C$ (left branch) and an inductor $L$ (right branch). The bottom rail returns to the source − terminal. Open output terminals at the far right across the parallel $L \parallel C$: upper marked +, lower marked −, labeled $\mathbf{V}_{out}$. (Series $R$, shunt parallel $LC$ tank, output across the tank.)

(a) Calculate the transfer function $\mathbf{H}(\omega) = \mathbf{V}_{out}/\mathbf{V}_s$ in terms of $R$, $L$, $C$, and $\omega$.

(b) Suppose $R = 100\,\Omega$, $C = 40\,\mu$F, and $L = 1\,\text{mH}$. Construct the Bode magnitude and phase plots for this circuit, using linear approximations as done in class. Be sure to label the key values on the vertical and horizontal axes of each plot, and any nonzero slopes in the Bode magnitude plot.

(c) What type of filter is this? Explain why it works this way, in terms of the component impedances as functions of frequency.

(d) Suppose $R$ increases from $100\,\Omega$ to $1000\,\Omega$. Would the bandwidth of the filter increase or decrease? Explain your answer.

## Page 3

**Figure: score histogram.** Title "ECE 411H Semester Exam 2 scores - Fall 2023". Vertical bar chart; x-axis "Semester Exam 2 score" with tick labels every 2 points from 0 to 100; y-axis "Frequency" from 0 to 7 (ticks every 1). Printed statistics inside the plot:

- Mean = 77.2, Median = 80, Standard Deviation = 15.1
- P1 = 20.3/25, P2 = 19.5/25, P3 = 18.2/25, P4 = 18.9/25
- Range = 24-100, Number = 66

Bar heights (score bin : count), read from the chart; all unlisted bins are 0:

| score | 24 | 46 | 52 | 54 | 58 | 60 | 62 | 64 | 66 | 68 | 70 | 72 | 76 | 78 | 80 | 82 | 84 | 86 | 88 | 90 | 92 | 94 | 96 | 98 | 100 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| count | 1 | 1 | 1 | 4 | 1 | 1 | 1 | 3 | 2 | 2 | 5 | 4 | 1 | 2 | 6 | 3 | 3 | 2 | 5 | 5 | 2 | 5 | 4 | 1 | 1 |

(Counts sum to 66, matching the printed Number.) Tallest bar: 80 (6). Distribution is bimodal-ish with clusters at 70–72 and 80–96; one outlier at 24.

## Index terms

Semester Exam 2, Fall 2023, Problem 1, Problem 2, Problem 3, Problem 4, quality factor, Q, W_stored, W_dissipated, series RLC, n-type semiconductor, boron, arsenic, valence electrons, Fermi distribution function, pn junction diode, exponential I-V, band pass filter, output across R, Circuit SE2-2, R = 100 ohm, unknown element Z, high-pass filter, corner frequency 1000 rad/s, band-reject filter, series LC, notch at 2000 rad/s, LC product, Circuit SE2-3, inverting op amp, R_s, C_s, R_f, L_f, R_f parallel L_f, transfer function, zeros and poles, factored form, Bode magnitude plot, Bode phase plot, phase slope, M(omega) as omega to infinity, R_f/R_s, Circuit SE2-4, series R, parallel LC, L parallel C, quadratic pole, resonant frequency, 5000 rad/s, bandwidth vs R, score histogram, mean 77.2, median 80, standard deviation 15.1, N = 66
