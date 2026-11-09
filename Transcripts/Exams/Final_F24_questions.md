---
course: ECE 411H
kind: past-exam
source: Exam Preparation Materials/ECE_411H_Final_questions+handout+histogram_F24.pdf
source_pages: 5
author: Prof. Ed Yu
unit: final
topics: [final-exam, series-rlc-filter-terminals, high-pass-filter, band-reject-filter, resonant-frequency, analysis-method-choice, fourier-transform, band-gap, intrinsic-carriers, rc-high-pass, rl-low-pass, bode-plot, average-power, apparent-power, power-factor, cutoff-frequency, active-band-pass, bandwidth, laplace-transform, rc-ladder, non-oscillatory, laplace-handout, transform-pairs, score-histogram]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
---

# ECE 411H Final Exam — Fall 2024 (questions + Laplace handout + score histogram)

**Summary.** The Fall 2024 final (16 December 2024, 115 minutes, 4 problems × 25 points, Laplace handout appended). Problem 1: five 5-point short questions on a series R–C–L string with terminals a, b, c, d (which pair gives high-pass, which band-reject, resonant frequency for given values, which analysis method for $5e^{-10t}\cos\omega t$ switched at $t = 0$, Si vs Ge hole concentration). Problem 2: two parallel branches ($C$–$R_1$ and $L$–$R_2$) across one source — $\mathbf{H}_1$, $\mathbf{H}_2$ with Bode plots, average powers, component values for $\omega_c = 10^4$ rad/s, and apparent power / power factor at $\omega_c$. Problem 3: inverting active band-pass ($R_1$, shunt $R_2$, $C_1$, feedback $C_2 \parallel R_3$) — transfer function, Bode plots with $0°$–$360°$ phase, bandwidth by linear approximation vs exact. Problem 4: RC ladder ($R_1$, $C_1$, $R_2$, $C_2$) driven by $5(1 - e^{-10t})u(t)$ via Laplace; prove no oscillation for any positive $R_1$, $R_2$. Page 4: Laplace handout. Page 5: histogram (mean 75.0, median 74.6, N = 32). Companion: `Final_F24_short_answers.md`.

## Page 1

FINAL EXAM — ECE 411H — 16 December 2024

PLEASE ATTEMPT ALL PROBLEMS AND SHOW ALL WORK!
WRITE ALL EXAM SOLUTIONS IN THE SPACES PROVIDED ON THE EXAM ANSWER SHEETS. YOU MAY USE THE BACK OF EACH PAGE FOR SCRATCH, BUT ONLY THE FRONT SIDES WILL BE SCANNED AND GRADED.

The exam questions and appended Laplace transform handout, answer sheets, and a calculator are allowed; no other materials should be consulted during the exam. No communication with any other student is allowed during the exam. You will have 115 minutes from the start of the exam to complete the exam, followed by ~5 minutes to scan and upload your exam answer sheets to Gradescope.

NOTES: Unless otherwise stated, you may assume all numerical quantities given in the exam problems are known to 3 significant figures, and calculate your answers accordingly. Decimal values for answers can be given to 3 significant figures. You must show all of your work to receive credit. If you need to make an assumption to answer a question, state it explicitly.

ONLY THE FRONT SIDE OF EACH SHEET WILL BE GRADED.

### Problem 1 [25 points total]

Answer the questions below. Each should require a few sentences or relatively small amount of math at most. You may also include a sketch/picture if necessary.

**Figure: Circuit FE-1abcd.** Source $v_s(t)$ (+ on top) on the left. The top wire runs to the top node, which is brought out to an open terminal labeled $a$ (top right). From that node a vertical string runs down the right side: resistor $R$ (between terminals $a$ and $b$), then capacitor $C$ (between $b$ and $c$), then inductor $L$ (between $c$ and $d$), to the bottom node which is brought out as terminal $d$ (bottom right) and returns along the bottom wire to the source −. Terminals $a$, $b$, $c$, $d$ are open circles on the right, from top to bottom. (Series R–C–L loop with taps at every node.)

(a) [5 points] Consider Circuit FE-1abcd shown at right. Which two terminals should be selected as the output terminals for a high-pass filter? Explain.

(b) [5 points] Consider Circuit FE-1abcd shown at right. Which two terminals should be selected as the output terminals for a band-reject filter? Explain.

(c) [5 points] Consider Circuit FE-1abcd shown at right. If $R = 1\,\text{k}\Omega$, $C = 2\,\mu$F, and $L = 0.8$ mH, what is the resonant frequency of the circuit? Your answer should be a numerical value with appropriate units.

(d) [5 points] Consider Circuit FE-1abcd shown at right, with
$$v_s(t) = \begin{cases} 5 & t < 0 \\ 5\,e^{-10t}\cos(\omega t) & t \ge 0 \end{cases}.$$
The output terminals for the circuit are $b$ and $c$. Would the most efficient way to solve this problem be to use phasors, Laplace transforms, Fourier series, Fourier transforms, or time-domain analysis? Explain.

(e) [5 points] Consider two different semiconductor materials, silicon and germanium, both of which have no dopants or defects, at room temperature. Silicon has an energy band gap of 1.12 eV, and germanium an energy band gap of 0.67 eV. Which semiconductor would you expect to have a higher concentration of holes in the valence band? Explain.

## Page 2

### Problem 2 [25 points total]

Consider Circuit FE-2 shown at right.

**Figure: Circuit FE-2.** Source $\mathbf{V}_s(\omega)$ (+ on top) on the left, feeding a top rail and a bottom rail. Two parallel branches hang between the rails. Left branch: capacitor $C$ (upper) in series with resistor $R_1$ (lower) to the bottom rail; the voltage across $R_1$ is marked $\mathbf{V}_1(\omega)$ with open terminals (+ at the $C$–$R_1$ junction, − at the bottom). Right branch: inductor $L$ (upper) in series with resistor $R_2$ (lower); the voltage across $R_2$ is marked $\mathbf{V}_2(\omega)$ (+ at the $L$–$R_2$ junction, − at the bottom). Both branches share the bottom rail back to the source −.

(a) Calculate the transfer function $\mathbf{H}_1(\omega) \equiv \mathbf{V}_1(\omega)/\mathbf{V}_s(\omega)$. Your result should be in terms of (as needed) $R_1$, $R_2$, $C$, $L$, and $\omega$. Then construct the Bode magnitude and phase plots for the transfer function $\mathbf{H}_1$, using linear approximations as done in class. Be sure to label the key values on the vertical and horizontal axes of each plot, and any nonzero slopes in the Bode magnitude plot.

(b) Calculate the transfer function $\mathbf{H}_2(\omega) \equiv \mathbf{V}_2(\omega)/\mathbf{V}_s(\omega)$. Your result should be in terms of (as needed) $R_1$, $R_2$, $C$, $L$, and $\omega$. Then construct the Bode magnitude and phase plots for the transfer function $\mathbf{H}_2$, using linear approximations as done in class. Be sure to label the key values on the vertical and horizontal axes of each plot, and any nonzero slopes in the Bode magnitude plot.

(c) Calculate the average power dissipated by (i) the resistor $R_1$ and (ii) the resistor $R_2$ as functions of (as needed) $R_1$, $R_2$, $C$, $L$, $|\mathbf{V}_s(\omega)|$, and $\omega$.

(d) Suppose $R_1 = R_2 = 8\,\Omega$. For what values of $C$ and $L$ will the cutoff angular frequencies of $\mathbf{H}_1$ and $\mathbf{H}_2$ both be $10^4$ rad/s? You should give your answers as numerical values with appropriate units.

(e) Assume the cutoff angular frequencies of $\mathbf{H}_1$ and $\mathbf{H}_2$ are both equal to $\omega_c$, and that Circuit FE-2 is operating at $\omega = \omega_c$. Without assuming specific numerical values for any parameters in Circuit FE-2, calculate (i) the apparent power $P_s$ for the voltage source $\mathbf{V}_s(\omega)$, (ii) the average power $P_1$ dissipated by $R_1$, (iii) the average power $P_2$ dissipated by $R_2$, and (iv) the power factor $(P_1 + P_2)/P_s$, all when the circuit operates at $\omega_c$. Your results should be expressed in terms of (as needed) $|\mathbf{V}_s(\omega_c)|$, $R_1$, and $R_2$. (The words "apparent" and "average" are underlined in the original.)

### Problem 3 [25 points total]

Consider Circuit FE-3 shown at right. Assume the op-amp always behaves according to the ideal op-amp model.

**Figure: Circuit FE-3.** Source $\mathbf{V}_s(\omega)$ (+ on top, − grounded) at left. Series resistor $R_1$ from the source + to node X. From node X: resistor $R_2$ down to ground (shunt); capacitor $C_1$ in series to the op-amp inverting (−) input (top pin); and capacitor $C_2$ up and across to the op-amp output node (outer feedback path, drawn across the top). Resistor $R_3$ connects the op-amp − input to the output (inner feedback). The non-inverting (+) input (bottom pin) is grounded. Output $\mathbf{V}_o(\omega)$ at the op-amp output (open terminal, right).

(a) Calculate the transfer function $\mathbf{H}(\omega) \equiv \mathbf{V}_o(\omega)/\mathbf{V}_s(\omega)$ as a function of (as needed) $R_1$, $R_2$, $R_3$, $C_1$, $C_2$, and $\omega$. What type of filter is Circuit FE-3?

(b) Construct the Bode magnitude and phase plots for the transfer function $\mathbf{H}$, using linear approximations as done in class. Be sure to label the key values on the vertical and horizontal axes of each plot expressed in terms of (as needed) $R_1$, $R_2$, $R_3$, $C_1$, and $C_2$, and the numerical values of any nonzero slopes in the Bode magnitude plot. For the Bode phase plot, all phase angles $\phi(\omega)$ should satisfy $0° \le \phi(\omega) < 360°$.

(c) Assume $R_1 = 2.5\,\Omega$, $R_2 = 0.1\,\Omega$, $R_3 = 10\,\Omega$, $C_1 = C_2 = 1$ mF. Using the same linear approximations used to construct Bode plots, calculate the bandwidth of this filter, giving your result as a numerical value with appropriate units.

(d) As you did in part (c), assume $R_1 = 2.5\,\Omega$, $R_2 = 0.1\,\Omega$, $R_3 = 10\,\Omega$, $C_1 = C_2 = 1$ mF. Without using the linear approximations used to construct Bode plots, calculate the bandwidth of this filter directly from the transfer function, giving your result as a numerical value with appropriate units. Explain why this result differs from the one you obtained in part (c).

## Page 3

### Problem 4 [25 points total]

Consider Circuit FE-4 shown at right The input signal is given by
$$v_s(t) = 5(1 - e^{-10t})\,u(t)\ \text{V}, \quad \text{with}\quad u(t) = \begin{cases} 1 & t \ge 0 \\ 0 & t < 0 \end{cases}.$$

**Figure: Circuit FE-4.** Two-section RC ladder. Source $v_s(t)$ (+ on top) at left. Top rail: series resistor $R_1$ to node A; from node A capacitor $C_1$ hangs down (shunt) to the bottom rail; series resistor $R_2$ from node A to node B; from node B capacitor $C_2$ hangs down (shunt) to the bottom rail. Open output terminals at the right across $C_2$: upper +, lower −, labeled $v_{out}(t)$. Bottom rail returns to the source −.

(a) Calculate the Laplace transform of $v_s(t)$.

(b) Assume $R_1 = 2\,\text{k}\Omega$, $R_2 = 5\,\text{k}\Omega$, $C_1 = 1\,\mu$F, and $C_2 = 2\,\mu$F. Use the Laplace transform technique to calculate $v_{out}(t)$.

(c) Your result for $v_{out}(t)$ in part (b) should not exhibit any oscillatory behavior. Show mathematically that with $C_1 = 1\,\mu$F and $C_2 = 2\,\mu$F, there is no combination of positive values of $R_1$ and $R_2$ for which oscillatory behavior will be observed in $v_{out}(t)$.

(Rest of page 3 blank.)

## Page 4

**Laplace transform handout** ("ECE 411H: Laplace Transforms — Fall 2024"). Identical in content to the Fall 2023 and Fall 2025 handouts.

**Layout.** The handout is a single landscape page (printed rotated 90° in the PDF, so it appears sideways in the portrait file). Header, top centre: "ECE 411H: Laplace Transforms"; top right: "Fall 2024". Left half: the "Laplace Transform Pairs" table (16 numbered rows plus "a" variants) on a light-green panel. Right half, upper: "Table 12-1: Properties of the Laplace transform ($f(t) = 0$ for $t < 0^-$)". Right half, lower: "Table 12-3: Transform pairs for four types of poles." All three tables are reproduced from Ulaby/Maharbiz/Furse *Circuit Analysis and Design*, Chapter 12. Red double-headed arrows (↔) separate $f(t)$ and $\mathbf{F}(\mathbf{s})$ in each row.

**Caption above the pairs table:** "Examples of Laplace transform pairs for $T \ge 0$. Note that multiplication by $u(t)$ guarantees that $f(t) = 0$ for $t < 0^-$."

**Laplace Transform Pairs** — columns: No. | $f(t)$ | $\mathbf{F}(\mathbf{s}) = \mathcal{L}[f(t)]$

| No. | $f(t)$ | $\mathbf{F}(\mathbf{s}) = \mathcal{L}[f(t)]$ |
|---|---|---|
| 1 | $\delta(t)$ | $1$ |
| 1a | $\delta(t - T)$ | $e^{-T\mathbf{s}}$ |
| 2 | $1$ or $u(t)$ | $\dfrac{1}{\mathbf{s}}$ |
| 2a | $u(t - T)$ | $\dfrac{e^{-T\mathbf{s}}}{\mathbf{s}}$ |
| 3 | $e^{-at}\,u(t)$ | $\dfrac{1}{\mathbf{s} + a}$ |
| 3a | $e^{-a(t-T)}\,u(t - T)$ | $\dfrac{e^{-T\mathbf{s}}}{\mathbf{s} + a}$ |
| 4 | $t\,u(t)$ | $\dfrac{1}{\mathbf{s}^2}$ |
| 4a | $(t - T)\,u(t - T)$ | $\dfrac{e^{-T\mathbf{s}}}{\mathbf{s}^2}$ |
| 5 | $t^2\,u(t)$ | $\dfrac{2}{\mathbf{s}^3}$ |
| 6 | $t e^{-at}\,u(t)$ | $\dfrac{1}{(\mathbf{s} + a)^2}$ |
| 7 | $t^2 e^{-at}\,u(t)$ | $\dfrac{2}{(\mathbf{s} + a)^3}$ |
| 8 | $t^{n-1} e^{-at}\,u(t)$ | $\dfrac{(n-1)!}{(\mathbf{s} + a)^n}$ |
| 9 | $\sin\omega t\,u(t)$ | $\dfrac{\omega}{\mathbf{s}^2 + \omega^2}$ |
| 10 | $\sin(\omega t + \theta)\,u(t)$ | $\dfrac{\mathbf{s}\sin\theta + \omega\cos\theta}{\mathbf{s}^2 + \omega^2}$ |
| 11 | $\cos\omega t\,u(t)$ | $\dfrac{\mathbf{s}}{\mathbf{s}^2 + \omega^2}$ |
| 12 | $\cos(\omega t + \theta)\,u(t)$ | $\dfrac{\mathbf{s}\cos\theta - \omega\sin\theta}{\mathbf{s}^2 + \omega^2}$ |
| 13 | $e^{-at}\sin\omega t\,u(t)$ | $\dfrac{\omega}{(\mathbf{s} + a)^2 + \omega^2}$ |
| 14 | $e^{-at}\cos\omega t\,u(t)$ | $\dfrac{\mathbf{s} + a}{(\mathbf{s} + a)^2 + \omega^2}$ |
| 15 | $2e^{-at}\cos(bt - \theta)\,u(t)$ | $\dfrac{e^{j\theta}}{\mathbf{s} + a + jb} + \dfrac{e^{-j\theta}}{\mathbf{s} + a - jb}$ |
| 16 | $\dfrac{2t^{n-1}}{(n-1)!}\,e^{-at}\cos(bt - \theta)\,u(t)$ | $\dfrac{e^{j\theta}}{(\mathbf{s} + a + jb)^n} + \dfrac{e^{-j\theta}}{(\mathbf{s} + a - jb)^n}$ |

Note under the table: $(n-1)! = (n-1)(n-2)\ldots 1$.

**Table 12-1: Properties of the Laplace transform ($f(t) = 0$ for $t < 0^-$).** Columns: Property | $f(t)$ | $\mathbf{F}(\mathbf{s}) = \mathcal{L}[f(t)]$

| Property | $f(t)$ | $\mathbf{F}(\mathbf{s}) = \mathcal{L}[f(t)]$ |
|---|---|---|
| 1. Multiplication by constant | $K\,f(t)$ | $K\,\mathbf{F}(\mathbf{s})$ |
| 2. Linearity | $K_1 f_1(t) + K_2 f_2(t)$ | $K_1\mathbf{F}_1(\mathbf{s}) + K_2\mathbf{F}_2(\mathbf{s})$ |
| 3. Time scaling | $f(at),\ a > 0$ | $\dfrac{1}{a}\,\mathbf{F}\!\left(\dfrac{\mathbf{s}}{a}\right)$ |
| 4. Time shift | $f(t - T)\,u(t - T)$ | $e^{-T\mathbf{s}}\,\mathbf{F}(\mathbf{s}),\ T \ge 0$ |
| 5. Frequency shift | $e^{-at}\,f(t)$ | $\mathbf{F}(\mathbf{s} + a)$ |
| 6. Time 1st derivative | $f' = \dfrac{df}{dt}$ | $\mathbf{s}\,\mathbf{F}(\mathbf{s}) - f(0^-)$ |
| 7. Time 2nd derivative | $f'' = \dfrac{d^2 f}{dt^2}$ | $\mathbf{s}^2\mathbf{F}(\mathbf{s}) - \mathbf{s}f(0^-) - f'(0^-)$ |
| 8. Time integral | $\displaystyle\int_{0^-}^{t} f(\tau)\,d\tau$ | $\dfrac{1}{\mathbf{s}}\,\mathbf{F}(\mathbf{s})$ |
| 9. Frequency derivative | $t\,f(t)$ | $-\dfrac{d}{d\mathbf{s}}\,\mathbf{F}(\mathbf{s})$ |
| 10. Frequency integral | $\dfrac{f(t)}{t}$ | $\displaystyle\int_{\mathbf{s}}^{\infty} \mathbf{F}(\mathbf{s}')\,d\mathbf{s}'$ |

**Table 12-3: Transform pairs for four types of poles.** Columns: Pole | $\mathbf{F}(\mathbf{s})$ | $f(t)$

| Pole | $\mathbf{F}(\mathbf{s})$ | $f(t)$ |
|---|---|---|
| 1. Distinct real | $\dfrac{A}{\mathbf{s} + a}$ | $A e^{-at}\,u(t)$ |
| 2. Repeated real | $\dfrac{A}{(\mathbf{s} + a)^n}$ | $A\,\dfrac{t^{n-1}}{(n-1)!}\,e^{-at}\,u(t)$ |
| 3. Distinct complex | $\left[\dfrac{A e^{j\theta}}{\mathbf{s} + a + jb} + \dfrac{A e^{-j\theta}}{\mathbf{s} + a - jb}\right]$ | $2A e^{-at}\cos(bt - \theta)\,u(t)$ |
| 4. Repeated complex | $\left[\dfrac{A e^{j\theta}}{(\mathbf{s} + a + jb)^n} + \dfrac{A e^{-j\theta}}{(\mathbf{s} + a - jb)^n}\right]$ | $\dfrac{2A t^{n-1}}{(n-1)!}\,e^{-at}\cos(bt - \theta)\,u(t)$ |

## Page 5

**Figure: score histogram.** Title "ECE 411H Final Exam scores - Fall 2024". Bar chart; x-axis "Final Exam score", tick labels every 4 from 0 to 100 (2-point bins); y-axis "Frequency" 0 to 4.5 (ticks every 0.5). Printed statistics:

- Mean = 75.0, Median = 74.6, Standard Deviation = 9.1
- P1 = 23.1/25, P2 = 16.7/25, P3 = 15.1/25, P4 = 20.0/25
- Range = 54-91.75, Number = 32

Bar heights (score bin : count); unlisted bins are 0:

| score | 54 | 62 | 64 | 68 | 70 | 72 | 74 | 76 | 78 | 80 | 82 | 84 | 86 | 88 | 92 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| count | 1 | 2 | 2 | 1 | 3 | 4 | 3 | 1 | 2 | 3 | 1 | 2 | 2 | 4 | 1 |

(Counts sum to 32.) Modes at 72 and 88 (4 each). Problem 3 (active band-pass, bandwidth exact vs approximate) had the lowest average (15.1/25); Problem 1 the highest (23.1/25).

## Index terms

Final Exam, Fall 2024, Problem 1, Problem 2, Problem 3, Problem 4, Circuit FE-1abcd, terminals a b c d, series R C L, high-pass terminals, band-reject terminals, resonant frequency, R = 1 kohm, C = 2 uF, L = 0.8 mH, 25000 rad/s, analysis method choice, phasors, Laplace, Fourier series, Fourier transform, time domain, 5 e^-10t cos(omega t), silicon 1.12 eV, germanium 0.67 eV, hole concentration, Circuit FE-2, parallel branches, C series R1, L series R2, H1, H2, RC high-pass, RL low-pass, Bode plots, average power P1 P2, cutoff 10^4 rad/s, R1 = R2 = 8 ohm, apparent power P_s, power factor, Circuit FE-3, active band-pass, R1, R2, R3, C1, C2, phase 0 to 360, bandwidth linear approximation, bandwidth exact, R1 = 2.5 ohm, R2 = 0.1 ohm, R3 = 10 ohm, C = 1 mF, Circuit FE-4, RC ladder, R1 = 2 kohm, R2 = 5 kohm, C1 = 1 uF, C2 = 2 uF, v_s = 5(1 - e^-10t)u(t), Laplace transform of input, v_out(t), no oscillation, real poles, Laplace handout, Laplace transform pairs, Table 12-1, Table 12-3, score histogram, mean 75.0, median 74.6, standard deviation 9.1, N = 32
