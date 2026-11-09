---
course: ECE 411H
kind: past-exam
source: Exam Preparation Materials/ECE_411H_Final_questions+handout+histogram_F23.pdf
source_pages: 4
author: Prof. Ed Yu
unit: final
topics: [final-exam, series-rlc-damping, overdamped, laplace-vs-fourier, complex-phase-quadrant, cascaded-active-filter, bode-slope, band-reject-filter, parallel-lc, transfer-function, cutoff-frequency, rlc-transient, initial-conditions, step-response, inverting-op-amp, laplace-transform, laplace-handout, transform-pairs, score-histogram]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
---

# ECE 411H Final Exam — Fall 2023 (questions + Laplace handout + score histogram)

**Summary.** The Fall 2023 final (09 December 2023, 115 minutes, 4 problems × 25 points, Laplace handout appended). Problem 1: four short questions (raise R for overdamping; Laplace vs Fourier vs time-domain for a windowed $t + \cos\omega t$ input; phase quadrant of $a + jb$; 4th-order cascade of an inverting RC low-pass stage and its −80 dB/decade roll-off). Problem 2: parallel-LC series element with shunt R — band-reject filter, factored transfer function, two corner frequencies. Problem 3: second-order RLC transient (R_1, shunt L, R_2, C) with a step from 1 V to 5 V — initial conditions, $v_C(t)$, $i(t)$. Problem 4: inverting op-amp with $C_1$–$R_1$ input and $R_2 \parallel C_2$ feedback driven by $5(1 - e^{-10t})u(t)$ — find $v_{out}(t)$ and check $v_{out}(0)$, $v_{out}(\infty)$. Page 3 is the Laplace handout (transcribed row by row). Page 4: histogram (mean 71.4, median 73, N = 67). Companion: `Final_F23_short_answers.md`.

## Page 1

FINAL EXAM — ECE 411H — 09 December 2023

PLEASE ATTEMPT ALL PROBLEMS AND SHOW ALL WORK!
WRITE ALL EXAM SOLUTIONS IN THE SPACES PROVIDED ON THE EXAM ANSWER SHEETS. YOU MAY USE THE BACK OF EACH PAGE FOR SCRATCH, BUT ONLY THE FRONT SIDES WILL BE SCANNED AND GRADED.

The exam questions and appended Laplace transform handout, answer sheets, and a calculator are allowed; no other materials should be consulted during the exam. No communication with any other student is allowed during the exam. You will have 115 minutes from the start of the exam to complete the exam, followed by ~5 minutes to scan and upload your exam answer sheets to Gradescope.

NOTES: Unless otherwise stated, you may assume all numerical quantities given in the exam problems are known to 3 significant figures, and calculate your answers accordingly. Decimal values for answers can be given to 3 significant figures. You must show all of your work to receive credit. If you need to make an assumption to answer a question, state it explicitly.

ONLY THE FRONT SIDE OF EACH SHEET WILL BE GRADED.

### Problem 1 [25 points total]

Answer the questions below. Each should require a few sentences or relatively small amount of math at most. You may also include a sketch/picture if necessary.

**Figure: Circuit FE-1ab.** Single series loop. Voltage source $v_s(t)$ (+ on top) on the left side; along the top: resistor $R$, then inductor $L$ (coil), then capacitor $C$ at the top-right corner (drawn vertically on the right side); the right side returns down and the bottom wire returns to the source −. Series RLC with no output marked.

(a) [6 points] Suppose a series RLC circuit, such as Circuit FE-1ab at right, has underdamped response. To achieve overdamped response, would you want to increase or decrease $R$ (keeping the rest of the circuit unchanged)? Explain.

(b) [6 points] Consider an RLC series circuit with a single independent source $v_s(t)$, such as Circuit FE-1ab shown at right. If $v_s(t) = (t + \cos\omega t)[u(t - 5) - u(t - 10)]$, would it be most efficient to solve for the current in the circuit using differential equations in the time domain, Laplace transforms, or Fourier techniques? Explain.

(c) [6 points] Consider a complex number $z = a + jb$, where $a$ and $b$ are real numbers. Keeping in mind the defined range of the mathematical function $\tan^{-1} x$, what is the phase of $z$, in degrees, for (i) $a > 0$ and $b > 0$, and (ii) $a < 0$ and $b < 0$?

**Figure: Circuit FE-1d.** Inverting op-amp stage. Input $v_{in}$ (open terminal at left, referenced to ground) → series resistor → op-amp inverting (−) input (top pin). Non-inverting (+) input (bottom pin) grounded. Feedback from the output back to the − input: a resistor (upper branch) in parallel with a capacitor (lower branch). Output $v_{out}$ at the op-amp output (open terminal at right, referenced to ground). Components are unlabeled in this figure.

(d) [7 points] Consider a 4th-order cascaded active filter circuit consisting of 4 of the subcircuits Circuit FE-1d, shown at right, connected in series with each other, i.e., the output of one subcircuit is connect to the input of the next. (i) What type of filter is the 4th order circuit? (ii) What is the slope of the Bode magnitude plot (in the linear approximation) for the 4th order circuit outside the filter passband?

## Page 2

### Problem 2 [25 points total]

Consider Circuit FE-2 shown below right. All numerical values given in this problem are exact.

**Figure: Circuit FE-2.** Source $\mathbf{V}_s$ (+ on top) on the left. On the top rail between the source + and the output node sits a parallel combination: inductor $L$ (upper branch) in parallel with capacitor $C$ (lower branch), i.e., a series-connected $L \parallel C$ tank. From the output node a resistor $R$ hangs down (shunt) to the bottom rail. Open output terminals at the right across $R$: upper +, lower −, labeled $\mathbf{V}_{out}$. Bottom rail returns to the source −.

(a) What type of filter is this? Explain.

(b) Calculate the transfer function $\mathbf{H}(\omega) = \mathbf{V}_{out}/\mathbf{V}_s$ in terms of $R$, $L$, and $C$. Your answer should be in an algebraic form that makes it very straightforward to identify the factors corresponding to any zeros or poles that are present.

(c) Suppose $L = 10$ mH, $R = 10\,\Omega$, and $C = 100\,\mu$F. Calculate the numerical value(s) of the corner, i.e., cutoff, frequency (or frequencies, if more than one exists).

### Problem 3 [25 points total]

Consider Circuit FE-3 shown at right. $R_1 = 10\,\Omega$, $R_2 = 40\,\Omega$, $C = 100\,\mu$F, and $L = 40$ mH. The input signal is given by
$$v_s(t) = \begin{cases} 5u(t)\ \text{V} & t \ge 0 \\ 1\ \text{V} & t < 0 \end{cases}.$$
All numerical values given in this problem are exact.

**Figure: Circuit FE-3.** Source $v_s(t)$ (+ on top) on the left. Top rail: resistor $R_1$ with current $i(t)$ marked by an arrow pointing right (toward the middle node); at the middle node an inductor $L$ hangs down (shunt) to the bottom rail with current $i_L(t)$ marked by a downward arrow; then resistor $R_2$ continues on the top rail to the right node, from which capacitor $C$ hangs down to the bottom rail with $v_C(t)$ marked across it (+ top, − bottom). Bottom rail returns to the source −.

(a) Calculate the initial conditions, i.e., values at $t = 0$, for $i_L(t)$ and $v_C(t)$.

(b) Solve for $v_C(t)$ for $t \ge 0$.

(c) Solve for $i(t)$ for $t \ge 0$.

### Problem 4 [25 points total]

Consider Circuit FE-4 shown at right. All the numerical values given in this problem are exact, and the op amp can be considered ideal and is always in its linear region of behavior. $R_1 = 1\,\text{k}\Omega$, $R_2 = 1\,\text{k}\Omega$, $C_1 = 10\,\mu$F, and $C_2 = 8\,\mu$F. The input signal is given by $v_{in}(t) = 5(1 - e^{-10t})u(t)$ V, with
$$u(t) = \begin{cases} 1 & t \ge 0 \\ 0 & t < 0 \end{cases}.$$

**Figure: Circuit FE-4.** Inverting op-amp. Source $v_{in}(t)$ (+ on top, − grounded) at lower left. From the source +: series capacitor $C_1$ (drawn vertically, then the wire turns), then series resistor $R_1$, into the op-amp inverting (−) input (top pin). Non-inverting (+) input (bottom pin) grounded. Feedback from the op-amp output back to the − input: resistor $R_2$ (upper branch, drawn across the top) in parallel with capacitor $C_2$ (lower branch). Output $v_{out}(t)$ between the op-amp output (+, open terminal) and ground (−, ground symbol).

(a) Using an analysis technique of your choice, calculate $v_{out}(t)$.

(b) As a quick check of the correctness of your solution, you can compute $v_{out}(0)$ and $v_{out}(\infty)$ using the expression you obtained in part (a). What values should you obtain for $v_{out}(0)$ and $v_{out}(\infty)$? Explain your answers.

## Page 3

**Laplace transform handout** ("ECE 411H: Laplace Transforms — Fall 2023").

**Layout.** The handout is a single landscape page (printed rotated 90° in the PDF, so it appears sideways in the portrait file). Header, top centre: "ECE 411H: Laplace Transforms"; top right: "Fall 2023". Left half: the "Laplace Transform Pairs" table (16 numbered rows plus "a" variants) on a light-green panel. Right half, upper: "Table 12-1: Properties of the Laplace transform ($f(t) = 0$ for $t < 0^-$)". Right half, lower: "Table 12-3: Transform pairs for four types of poles." All three tables are reproduced from Ulaby/Maharbiz/Furse *Circuit Analysis and Design*, Chapter 12. Red double-headed arrows (↔) separate $f(t)$ and $\mathbf{F}(\mathbf{s})$ in each row.

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

## Page 4

**Figure: score histogram.** Title "ECE 411H Final Exam scores - Fall 2023". Bar chart; x-axis "Final Exam score", tick labels every 4 from 0 to 100 (bars in 2-point bins); y-axis "Frequency" 0 to 14 (ticks every 2). Printed statistics:

- Mean = 71.4, Median = 73, Standard Deviation = 11.7
- P1 = 20.9/25, P2 = 17.4/25, P3 = 16.2/25, P4 = 16.6/25
- Range = 45-95, Number = 67

Bar heights (score bin : count); unlisted bins are 0:

| score | 46 | 48 | 50 | 52 | 54 | 58 | 60 | 62 | 66 | 68 | 70 | 72 | 74 | 76 | 80 | 82 | 84 | 86 | 88 | 90 | 96 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| count | 1 | 4 | 1 | 1 | 1 | 2 | 2 | 2 | 6 | 2 | 5 | 2 | 13 | 5 | 5 | 1 | 8 | 1 | 2 | 2 | 1 |

(Counts sum to 67.) Strong mode at 74 (13), secondary at 84 (8). Problem 3 (RLC transient) had the lowest average (16.2/25).

## Index terms

Final Exam, Fall 2023, Problem 1, Problem 2, Problem 3, Problem 4, Circuit FE-1ab, series RLC, underdamped, overdamped, increase R, R > 2 sqrt(L/C), windowed input, u(t-5) - u(t-10), Laplace transform vs Fourier vs time domain, complex number phase, tan^-1, quadrant, a < 0 b < 0, 180 degrees, Circuit FE-1d, inverting RC low-pass, cascaded 4th-order, -80 dB/decade, Circuit FE-2, series L parallel C, shunt R, band-reject, notch, transfer function, zeros and poles, corner frequencies, L = 10 mH, R = 10 ohm, C = 100 uF, Circuit FE-3, R1 = 10 ohm, R2 = 40 ohm, C = 100 uF, L = 40 mH, step 1 V to 5 V, initial conditions, i_L(0), v_C(0), v_C(t), i(t), second-order transient, Circuit FE-4, inverting op amp, C1 = 10 uF, R1 = 1 kohm, R2 = 1 kohm, C2 = 8 uF, v_in = 5(1 - e^-10t)u(t), v_out(t), v_out(0), v_out(infinity), Laplace transform handout, Laplace transform pairs, Table 12-1, Table 12-3, time shift, frequency shift, time derivative, time integral, distinct real pole, repeated real pole, distinct complex pole, repeated complex pole, score histogram, mean 71.4, median 73, standard deviation 11.7, N = 67
