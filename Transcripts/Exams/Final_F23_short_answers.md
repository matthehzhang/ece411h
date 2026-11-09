---
course: ECE 411H
kind: past-exam
source: Exam Preparation Materials/ECE_411H_FE_short-answers_F23.pdf
source_pages: 4
author: Prof. Ed Yu
unit: final
topics: [final-exam, short-answers, overdamped, laplace-vs-fourier, complex-phase-quadrant, cascaded-active-filter, band-reject-filter, parallel-lc, transfer-function, cutoff-frequency, rlc-transient, initial-conditions, step-response, inverting-op-amp, laplace-transform, laplace-handout]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
---

# ECE 411H Final Exam — Fall 2023 — Short Answers

**Summary.** Instructor's answer key for the Fall 2023 final: the question sheet with typed bold answers and pasted handwritten results, followed by the Laplace handout on page 4. Key results: increase $R$ ($R > 2\sqrt{L/C}$); Laplace; $\tan^{-1}(b/a)$ and $180° + \tan^{-1}(b/a)$; 4th-order low-pass at $-80$ dB/decade; band-reject $\mathbf{H} = (1 - \omega^2LC)/(1 + j\omega L/R - \omega^2LC)$ with cutoffs 618 and 1618 rad/s; $i_L(0) = 0.1$ A, $v_C(0) = 0$, $v_C(t) = 8e^{-200t}\sin 100t$ V, $i(t) = 0.5 - [0.32\cos100t + 0.16\sin100t]e^{-200t}$ A; $v_{out}(t) = [1.2136e^{-100t}\cos(50t - 60.95°) - 0.5896e^{-10t}]u(t)$ V with $v_{out}(0) = v_{out}(\infty) = 0$. Question text identical to `Final_F23_questions.md`.

## Page 1

FINAL EXAM SHORT ANSWERS — ECE 411H — 09 December 2023 (header and rules block identical to the question sheet).

### Problem 1 [25 points total]

**Figure: Circuit FE-1ab.** Series loop: $v_s(t)$ (+ top) at left; top wire: $R$, then $L$, then $C$ (vertical, at the right side); bottom wire back to the source.

(a) [6 points] Suppose a series RLC circuit, such as Circuit FE-1ab at right, has underdamped response. To achieve overdamped response, would you want to increase or decrease $R$ (keeping the rest of the circuit unchanged)? Explain.
**Answer:** Increase R. R>2sqrt(L/C) for overdamping, or increasing R increases power dissipation so signals are damped more quickly.

(b) [6 points] Consider an RLC series circuit with a single independent source $v_s(t)$, such as Circuit FE-1ab shown at right. If $v_s(t) = (t + \cos\omega t)[u(t - 5) - u(t - 10)]$, would it be most efficient to solve for the current in the circuit using differential equations in the time domain, Laplace transforms, or Fourier techniques? Explain.
**Answer:** Laplace transform, to accommodate initial conditions and avoid solving challenging differential equation.

(c) [6 points] Consider a complex number $z = a + jb$, where $a$ and $b$ are real numbers. Keeping in mind the defined range of the mathematical function $\tan^{-1} x$, what is the phase of $z$, in degrees, for (i) $a > 0$ and $b > 0$, and (ii) $a < 0$ and $b < 0$?
**Answer:** (i) $\tan^{-1}(b/a)$. (ii) $180° + \tan^{-1}(b/a)$

**Figure: Circuit FE-1d.** Inverting op-amp stage: $v_{in}$ → series resistor → − input (top pin); + input (bottom pin) grounded; feedback resistor ∥ capacitor from output to − input; $v_{out}$ at the output. Components unlabeled.

(d) [7 points] Consider a 4th-order cascaded active filter circuit consisting of 4 of the subcircuits Circuit FE-1d, shown at right, connected in series with each other, i.e., the output of one subcircuit is connect to the input of the next. (i) What type of filter is the 4th order circuit? (ii) What is the slope of the Bode magnitude plot (in the linear approximation) for the 4th order circuit outside the filter passband?
**Answer:** (i) low-pass filter. (ii) -80 dB/decade.

## Page 2

### Problem 2 [25 points total]

Consider Circuit FE-2 shown below right. All numerical values given in this problem are exact.

**Figure: Circuit FE-2.** $\mathbf{V}_s$ → series ($L \parallel C$) on the top rail → node; shunt $R$ to the bottom rail; $\mathbf{V}_{out}$ across $R$ (+ top, − bottom).

(a) What type of filter is this? Explain.
**Answer:** Band-reject filter

(b) Calculate the transfer function $\mathbf{H}(\omega) = \mathbf{V}_{out}/\mathbf{V}_s$ in terms of $R$, $L$, and $C$. Your answer should be in an algebraic form that makes it very straightforward to identify the factors corresponding to any zeros or poles that are present.
**Answer (handwritten):**
$$\mathbf{H}(\omega) = \frac{\mathbf{V}_{out}}{\mathbf{V}_s} = \frac{1 - \omega^2 LC}{1 + j\omega\frac{L}{R} - \omega^2 LC} = \frac{1 + (j\omega/\omega_0)^2}{1 + j\omega\frac{L}{R} + (j\omega/\omega_0)^2},\qquad \omega_0 = \frac{1}{\sqrt{LC}}$$

(c) Suppose $L = 10$ mH, $R = 10\,\Omega$, and $C = 100\,\mu$F. Calculate the numerical value(s) of the corner, i.e., cutoff, frequency (or frequencies, if more than one exists).
**Answer:** 618 rad/s, 1618 rad/s

### Problem 3 [25 points total]

Consider Circuit FE-3 shown at right. $R_1 = 10\,\Omega$, $R_2 = 40\,\Omega$, $C = 100\,\mu$F, and $L = 40$ mH. The input signal is given by
$$v_s(t) = \begin{cases} 5u(t)\ \text{V} & t \ge 0 \\ 1\ \text{V} & t < 0 \end{cases}.$$
All numerical values given in this problem are exact.

**Figure: Circuit FE-3.** $v_s(t)$ → $R_1$ (current $i(t)$ →) → middle node (shunt $L$, current $i_L(t)$ ↓) → $R_2$ → right node (shunt $C$, $v_C(t)$ + top).

(a) Calculate the initial conditions, i.e., values at $t = 0$, for $i_L(t)$ and $v_C(t)$.
**Answer:** $i_L(0) = 0.1$ A, $v_C(0) = 0$ V.

(b) Solve for $v_C(t)$ for $t \ge 0$.
**Answer (handwritten):** $v_C(t) = 8e^{-200t}\sin 100t$ V

(c) Solve for $i(t)$ for $t \ge 0$.
**Answer (handwritten, boxed):** $i(t) = 0.5 - \left[0.32\cos 100t + 0.16\sin 100t\right]e^{-200t}$ A

### Problem 4 [25 points total]

Consider Circuit FE-4 shown at right. All the numerical values given in this problem are exact, and the op amp can be considered ideal and is always in its linear region of behavior. $R_1 = 1\,\text{k}\Omega$, $R_2 = 1\,\text{k}\Omega$, $C_1 = 10\,\mu$F, and $C_2 = 8\,\mu$F. The input signal is given by $v_{in}(t) = 5(1 - e^{-10t})u(t)$ V, with
$$u(t) = \begin{cases} 1 & t \ge 0 \\ 0 & t < 0 \end{cases}.$$

**Figure: Circuit FE-4.** $v_{in}(t)$ → $C_1$ → $R_1$ → op-amp − input (top pin); + input grounded; $R_2 \parallel C_2$ feedback from output to − input; $v_{out}(t)$ from output to ground.

## Page 3

(a) Using an analysis technique of your choice, calculate $v_{out}(t)$.
**Answer (handwritten, boxed, pasted over the question line):**
$$v_{out}(t) = \left[1.2136\,e^{-100t}\cos(50t - 60.95°) - 0.5896\,e^{-10t}\right]u(t)\ \text{V}$$

(b) As a quick check of the correctness of your solution, you can compute $v_{out}(0)$ and $v_{out}(\infty)$ using the expression you obtained in part (a). What values should you obtain for $v_{out}(0)$ and $v_{out}(\infty)$? Explain your answers.
**Answer (handwritten):** $v_{out}(0) = 0$ and $v_{out}(\infty) = 0$.

(Rest of page 3 blank.)

## Page 4

**Laplace transform handout** ("ECE 411H: Laplace Transforms — Fall 2023"), appended to the answer key exactly as on the question sheet.

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

## Index terms

Final Exam, Fall 2023, short answers, answer key, Problem 1, Problem 2, Problem 3, Problem 4, Circuit FE-1ab, overdamped, increase R, R > 2 sqrt(L/C), Laplace transform, initial conditions, complex phase, tan^-1(b/a), 180 + tan^-1(b/a), Circuit FE-1d, 4th-order low-pass, -80 dB/decade, Circuit FE-2, band-reject, H(omega) = (1 - omega^2 LC)/(1 + j omega L/R - omega^2 LC), quadratic zero, quadratic pole, omega_0 = 1/sqrt(LC), 618 rad/s, 1618 rad/s, Circuit FE-3, i_L(0) = 0.1 A, v_C(0) = 0 V, v_C(t) = 8 e^-200t sin 100t, i(t) = 0.5 - (0.32 cos 100t + 0.16 sin 100t) e^-200t, underdamped, Circuit FE-4, inverting op amp, v_out(t) = 1.2136 e^-100t cos(50t - 60.95 deg) - 0.5896 e^-10t, v_out(0) = 0, v_out(infinity) = 0, Laplace handout, Laplace transform pairs, Table 12-1, Table 12-3
