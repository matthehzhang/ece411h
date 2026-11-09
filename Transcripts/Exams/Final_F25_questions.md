---
course: ECE 411H
kind: past-exam
source: Exam Preparation Materials/ECE_411H_Final_questions+handout+histogram_F25.pdf
source_pages: 5
author: Prof. Ed Yu
unit: final
topics: [final-exam, switched-rlc-filter, low-pass-filter, band-pass-peak, rc-step-response, maximum-power-transfer, pn-junction, forward-bias, third-order-ladder-filter, loaded-filter, transfer-function-limits, sallen-key, second-order-low-pass, bode-plot, input-impedance, laplace-transform, damped-cosine, laplace-handout, transform-pairs, score-histogram]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
---

# ECE 411H Final Exam — Fall 2025 (questions + Laplace handout + score histogram)

**Summary.** The Fall 2025 final (12 December 2025, 115 minutes, 4 problems × 25 points, Laplace handout appended) — the most recent final and the closest model for F26. Problem 1: five 5-point short questions on a switchable R–(C ∥ L) circuit with terminals a, b, c (filter type with one switch open; peak of $|H|$ with both closed; time for the RC step to reach 3 V; $R_1$ for max power transfer to a C–R_2–L load; physical explanation of exponential diode current). Problem 2: third-order ladder ($R_s$, shunt $C_1$, series $L$, shunt $C_2$, load $R_L$) — filter type, $\mathbf{H}$ with $R_L \to \infty$, $\mathbf{H}$ with finite $R_L$, $\omega \to 0$ check. Problem 3: Sallen-Key low-pass — filter type, factored $\mathbf{H}$, numeric Bode plots, input impedance $\mathbf{Z}_{in}$, limiting checks. Problem 4: same Sallen-Key driven by $4e^{-5t}\cos(100t)u(t)$ — Laplace transform of the input, $v_o(t)$ for all $t$, boundary condition at $t = 0$. Page 4: Laplace handout. Page 5: histogram (mean 77.1, median 75, N = 17). Companion: `Final_F25_short_answers.md`.

## Page 1

FINAL EXAM — ECE 411H — 12 December 2025

PLEASE ATTEMPT ALL PROBLEMS AND SHOW ALL WORK!
WRITE ALL EXAM SOLUTIONS IN THE SPACES PROVIDED ON THE EXAM ANSWER SHEETS. YOU MAY USE THE BACK OF EACH PAGE FOR SCRATCH, BUT ONLY THE FRONT SIDES WILL BE SCANNED AND GRADED.

The exam questions and appended Laplace transform handout, answer sheets, and a calculator are allowed; no other materials should be consulted during the exam. No communication with any other student is allowed during the exam. You will have 115 minutes from the start of the exam to complete the exam, followed by ~5 minutes to scan and upload your exam answer sheets to Gradescope.

NOTES: Unless otherwise stated, you may assume all numerical quantities given in the exam problems are known to 3 significant figures, and calculate your answers accordingly. Decimal values for answers can be given to 3 significant figures. You must show all of your work to receive credit. If you need to make an assumption to answer a question, state it explicitly.

ONLY THE FRONT SIDE OF EACH SHEET WILL BE GRADED.

### Problem 1 [25 points total]

Answer the questions below. Each should require a few sentences or relatively small amount of math at most. You may also include a sketch/picture if necessary.

**Figure: Circuit FE-1abc.** Source $v_s(t)$ (+ on top) on the left. The top wire runs to the top-right node, brought out as open terminal $a$. From that node, resistor $R$ runs down to a node brought out as terminal $b$. Below node $b$ the path splits into two parallel vertical branches: the left branch is capacitor $C$ in series with "switch 1" (a single-pole switch drawn open, below $C$); the right branch is inductor $L$ in series with "switch 2" (drawn open, below $L$). Both switches close onto the bottom node, which is brought out as terminal $c$ and returns along the bottom wire to the source −. (So terminals: $a$ = source +/top of $R$; $b$ = bottom of $R$ / top of the $C$ and $L$ branches; $c$ = bottom rail.)

(a) [5 points] Consider Circuit FE-1abc shown at right. If switch 1 is open and switch 2 is closed, and the output terminals are taken to be terminals $a$ and $b$, what type of filter is this? Explain.

(b) [5 points] Consider Circuit FE-1abc shown at right. Both switches are closed and the output terminals are taken to be terminals $b$ and $c$. What is the maximum value of the transfer function magnitude, and at what frequency does this maximum value occur? Your results should be expressed in terms of (as needed) $R$, $L$, and $C$.

(c) [5 points] Consider Circuit FE-1abc shown at right. Switch 1 is closed, and switch 2 is open. Assume $R = 200\,\Omega$, $C = 10\,\mu$F, $L = 5$ mH, and $v_s(t) = 5u(t)$ V where $u(t)$ is the unit step function. At what time (give a numerical value) is the voltage between terminals $b$ and $c$ equal to 3 V? Be sure to show your work.

**Figure: Circuit FE-1d.** Source $\mathbf{V}_s(\omega)$ (+ on top) at left. Top rail: series resistor $R_1$ to a node; from that node capacitor $C$ hangs down (shunt) to the bottom rail; series resistor $R_2$ continues to the right, then inductor $L$ runs down the right side to the bottom rail. Brackets beneath label the left part ($\mathbf{V}_s$, $R_1$) "source" and the right part ($C$, $R_2$, $L$) "load".

(d) [5 points] Consider Circuit FE-1d shown at right, with $R_2 = 100\,\Omega$, $C = 20\,\mu$F, $L = 2$ mH, and $\omega = 5000$ rad/s. What value of $R_1$ maximizes power transfer from the source to the load? Explain your answer.

(e) [5 points] Explain, in terms of the behavior of electrons and holes in a semiconductor's conduction band and valence band, respectively, why current increases exponentially with increasing voltage across a forward-biased pn junction diode.

## Page 2

### Problem 2 [25 points total]

Consider Circuit FE-2 shown at right.

**Figure: Circuit FE-2.** Third-order LC ladder. Source $\mathbf{V}_s(\omega)$ (+ on top) at left. Top rail: series resistor $R_s$ to node 1; from node 1 capacitor $C_1$ hangs down (shunt) to the bottom rail; series inductor $L$ from node 1 to node 2; from node 2 capacitor $C_2$ hangs down (shunt); further right, resistor $R_L$ hangs down (shunt) from the same top node. Open output terminals at the far right across $R_L$: upper +, lower −, labeled $\mathbf{V}_o(\omega)$. Bottom rail returns to the source −.

(a) What type of filter is this? Explain your reasoning in terms of the limiting behavior of the circuit's components at low and high frequency.

(b) Assume, for just part (b) of the problem, that $R_L \to \infty$. Calculate the transfer function $\mathbf{H}(\omega) \equiv \mathbf{V}_o(\omega)/\mathbf{V}_s(\omega)$ in this limit. Your result should be in terms of (as needed) $R_s$, $C_1$, $C_2$, $L$, and $\omega$. You do not need to express $\mathbf{H}(\omega)$ in terms of solely simple or quadratic zeroes or poles, and constants, but your answer should be in the form of a rational function of $\omega$ in resonably [sic] simplified form.

(c) Now assume that $R_L$ is finite and nonzero. Calculate the transfer function $\mathbf{H}(\omega) \equiv \mathbf{V}_o(\omega)/\mathbf{V}_s(\omega)$ in terms of (as needed) $R_s$, $R_L$, $C_1$, $C_2$, $L$, and $\omega$. You do not need to express $\mathbf{H}(\omega)$ in terms of solely simple or quadratic zeroes or poles, and constants, but your answer should be in the form of a rational function of $\omega$ in reasonably simplified form.

(d) Show that your expression for $\mathbf{H}(\omega)$ from part (c) yields the correct result for $\omega \to 0$.

### Problem 3 [25 points total]

Consider Circuit FE-3 shown at right. Assume the op-amp always behaves according to the ideal op-amp model.

**Figure: Circuit FE-3** (Sallen-Key unity-gain low-pass). Source $\mathbf{V}_s(\omega)$ (+ on top, − grounded) at lower left, with the source current $\mathbf{I}_s(\omega)$ marked by an arrow pointing right out of the source + terminal into $R_1$. Series resistor $R_1$ to node A; series resistor $R_2$ from node A to node B; node B connects to the op-amp non-inverting (+) input (top pin). Capacitor $C_1$ from node A up and across to the op-amp output node (feedback). Capacitor $C_2$ from node B down to ground. The inverting (−) input (bottom pin) is tied to the output. Output $\mathbf{V}_o(\omega)$ at the op-amp output (open terminal, right).

(a) What type of filter is this? Explain your reasoning in terms of the limiting behavior of the circuit's components at low and high frequency.

(b) Calculate the transfer function $\mathbf{H}(\omega) \equiv \mathbf{V}_o(\omega)/\mathbf{V}_s(\omega)$ as a function of (as needed) $R_1$, $R_2$, $C_1$, $C_2$, and $\omega$. Your result should contain only factors corresponding to constants and simple or quadratic zeroes or poles.

(c) For part (c) of this problem only, assume $R_1 = R_2 = 1000\,\Omega$, and $C_1 = C_2 = 1\,\mu$F. Construct the Bode magnitude and phase plots for the transfer function $\mathbf{H}(\omega)$. Be sure to label the key numerical values on the vertical and horizontal axes of each plot, and the numerical values of any nonzero slopes in the Bode magnitude plot. For the Bode phase plot, all phase angles $\phi(\omega)$ should satisfy $-180° \le \phi(\omega) < 180°$.

(d) Now assume again that $R_1$, $R_2$, $C_1$, $C_2$, and $\omega$ can each take on any positive value. We can define an input impedance for this circuit, $\mathbf{Z}_{in}$, to be $\mathbf{Z}_{in} = \mathbf{V}_s/\mathbf{I}_s$. Calculate $\mathbf{Z}_{in}$ as a function of (as needed) $R_1$, $R_2$, $C_1$, $C_2$, and $\omega$.

(e) Demonstrate that your result for part (d) is correct for $\omega \to 0$ and $\omega \to \infty$.

## Page 3

### Problem 4 [25 points total]

Consider Circuit FE-4 shown at right The input signal is given by
$$v_s(t) = 4e^{-5t}\cos(100t)\,u(t)\ \text{V}, \quad \text{with}\quad u(t) = \begin{cases} 1 & t \ge 0 \\ 0 & t < 0 \end{cases}.$$

**Figure: Circuit FE-4.** Same Sallen-Key topology as FE-3 but in the time domain, with the op-amp drawn with its pins swapped: source $v_s(t)$ (+ on top, − grounded) → $R_1$ → node A → $R_2$ → node B → op-amp non-inverting (+) input, which is the BOTTOM pin in this drawing; $C_1$ from node A up and across to the op-amp output node; $C_2$ from node B down to ground; the inverting (−) input (TOP pin) is tied to the output; output $v_o(t)$ at the op-amp output (open terminal, right).

(a) Determine the Laplace transform, $V_s(s)$, of $v_s(t)$. Explain how you arrived at your result.

(b) Assume $R_1 = R_2 = 1000\,\Omega$, and $C_1 = C_2 = 10\,\mu$F. Use the Laplace transform technique to calculate $v_o(t)$ for all values of $t$.

(c) Show that your result for $v_o(t)$ in part (b) satisfies the correct boundary condition for $v_o(t)$ at $t = 0$.

(Rest of page 3 blank.)

## Page 4

**Laplace transform handout** ("ECE 411H: Laplace Transforms — Fall 2025"). Identical in content to the Fall 2023 and Fall 2024 handouts.

**Layout.** The handout is a single landscape page (printed rotated 90° in the PDF, so it appears sideways in the portrait file). Header, top centre: "ECE 411H: Laplace Transforms"; top right: "Fall 2025". Left half: the "Laplace Transform Pairs" table (16 numbered rows plus "a" variants) on a light-green panel. Right half, upper: "Table 12-1: Properties of the Laplace transform ($f(t) = 0$ for $t < 0^-$)". Right half, lower: "Table 12-3: Transform pairs for four types of poles." All three tables are reproduced from Ulaby/Maharbiz/Furse *Circuit Analysis and Design*, Chapter 12. Red double-headed arrows (↔) separate $f(t)$ and $\mathbf{F}(\mathbf{s})$ in each row.

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

**Figure: score histogram.** Title "ECE 411H Final Exam scores - Fall 2025". Bar chart; x-axis "Final Exam score", tick labels every 4 from 0 to 100 (2-point bins); y-axis "Frequency" 0 to 3.5 (ticks every 0.5). Printed statistics:

- Mean = 77.1, Median = 75, Standard Deviation = 10.1
- P1 = 17.1/25, P2 = 22.0/25, P3 = 21.1/25, P4 = 16.8/25
- Range = 58-94, Number = 17

Bar heights (score bin : count); unlisted bins are 0:

| score | 58 | 66 | 70 | 74 | 76 | 78 | 84 | 86 | 88 | 90 | 92 | 94 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| count | 1 | 2 | 1 | 3 | 2 | 2 | 1 | 1 | 1 | 1 | 1 | 1 |

(Counts sum to 17.) Mode at 74 (3). Problem 1 (short answers, 17.1/25) and Problem 4 (Laplace with damped cosine, 16.8/25) were the lowest-scoring parts; Problem 2 (ladder filter) the highest (22.0/25).

## Index terms

Final Exam, Fall 2025, Problem 1, Problem 2, Problem 3, Problem 4, Circuit FE-1abc, switch 1, switch 2, terminals a b c, R, C parallel L, low-pass, band-pass maximum, omega = 1/sqrt(LC), RC step response, time to reach 3 V, R = 200 ohm, C = 10 uF, L = 5 mH, 5u(t), Circuit FE-1d, source and load, R1 for maximum power transfer, R2 = 100 ohm, C = 20 uF, L = 2 mH, omega = 5000 rad/s, forward-biased pn junction, electrons and holes, exponential current, Circuit FE-2, third-order ladder, R_s, C1, L, C2, R_L, low-pass, H with R_L infinite, H with finite R_L, rational function, omega to 0 check, Circuit FE-3, Sallen-Key, ideal op-amp, factored transfer function, quadratic pole, R1 = R2 = 1000 ohm, C1 = C2 = 1 uF, Bode plots, -40 dB/decade, input impedance Z_in = V_s/I_s, limits omega to 0 and infinity, Circuit FE-4, v_s = 4 e^-5t cos(100t) u(t), Laplace transform damped cosine, R1 = R2 = 1000 ohm, C1 = C2 = 10 uF, v_o(t), boundary condition at t = 0, continuity, Laplace handout, Laplace transform pairs, Table 12-1, Table 12-3, score histogram, mean 77.1, median 75, standard deviation 10.1, N = 17
