---
course: ECE 411H
kind: past-exam
source: Exam Preparation Materials/ECE_411H_FE_short-answers_F25.pdf
source_pages: 4
author: Prof. Ed Yu
unit: final
topics: [final-exam, short-answers, low-pass-filter, band-pass-peak, rc-step-response, maximum-power-transfer, pn-junction, forward-bias, third-order-ladder-filter, loaded-filter, sallen-key, second-order-low-pass, bode-plot, input-impedance, laplace-transform, damped-cosine, laplace-handout]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
---

# ECE 411H Final Exam — Fall 2025 — Short Answers

**Summary.** Instructor's answer key for the Fall 2025 final: question sheet with typed bold answers and pasted handwritten results; page 4 is the Laplace handout. Key results: low-pass; peak $|H| = 1$ at $\omega = 1/\sqrt{LC}$; 1.833 ms; $R_1 = 0$; carrier-energy explanation of the diode exponential. Ladder: $\mathbf{H}|_{R_L\to\infty} = 1/[1 + j\omega R_s(C_1+C_2) - \omega^2LC_2 - j\omega^3R_sLC_1C_2]$; finite $R_L$: $\mathbf{H} = (j\omega L/R_s)/[(1 - \omega^2LC_1 + j\omega L/R_s)(1 - \omega^2LC_2 + j\omega L/R_L) - 1]$. Sallen-Key: $\mathbf{H} = 1/[1 + j\omega(R_1+R_2)C_2 - \omega^2R_1R_2C_1C_2]$, corner 1000 rad/s, $-40$ dB/decade, $\mathbf{Z}_{in} = [1 + j\omega(R_1+R_2)C_2 - \omega^2R_1R_2C_1C_2]/[j\omega C_2(1 + j\omega R_2C_1)]$. $V_s(s) = 4(s+5)/[(s+5)^2 + 10^4]$; $v_o(t) = [0.10775e^{-100t} - 199.74te^{-100t} + 2.102e^{-5t}\sin(100t - 2.94°)]u(t)$ V; $v_o$ continuous at $t = 0$. Question text identical to `Final_F25_questions.md`.

## Page 1

FINAL EXAM — ECE 411H — 12 December 2025 (header and rules block identical to the question sheet).

### Problem 1 [25 points total]

**Figure: Circuit FE-1abc.** $v_s(t)$ at left; terminal $a$ at the top node; $R$ down to terminal $b$; from $b$ two parallel branches: $C$ + switch 1 (left) and $L$ + switch 2 (right), both to the bottom node, terminal $c$.

(a) [5 points] Consider Circuit FE-1abc shown at right. If switch 1 is open and switch 2 is closed, and the output terminals are taken to be terminals $a$ and $b$, what type of filter is this? Explain.
**Answer:** Low-pass filter

(b) [5 points] Consider Circuit FE-1abc shown at right. Both switches are closed and the output terminals are taken to be terminals $b$ and $c$. What is the maximum value of the transfer function magnitude, and at what frequency does this maximum value occur? Your results should be expressed in terms of (as needed) $R$, $L$, and $C$.
**Answer:** $1$, at $\omega = 1/\sqrt{LC}$

(c) [5 points] Consider Circuit FE-1abc shown at right. Switch 1 is closed, and switch 2 is open. Assume $R = 200\,\Omega$, $C = 10\,\mu$F, $L = 5$ mH, and $v_s(t) = 5u(t)$ V where $u(t)$ is the unit step function. At what time (give a numerical value) is the voltage between terminals $b$ and $c$ equal to 3 V? Be sure to show your work.
**Answer:** 1.833 ms

**Figure: Circuit FE-1d.** $\mathbf{V}_s(\omega)$ → $R_1$ (source) | node with shunt $C$ → $R_2$ → $L$ to the bottom rail (load); brackets "source" and "load".

(d) [5 points] Consider Circuit FE-1d shown at right, with $R_2 = 100\,\Omega$, $C = 20\,\mu$F, $L = 2$ mH, and $\omega = 5000$ rad/s. What value of $R_1$ maximizes power transfer from the source to the load? Explain your answer.
**Answer:** $R_1 = 0$

(e) [5 points] Explain, in terms of the behavior of electrons and holes in a semiconductor's conduction band and valence band, respectively, why current increases exponentially with increasing voltage across a forward-biased pn junction diode.
**Answer:** At forward bias, more electrons on the n-side have enough energy to surmount the built-in pn junction barrier and move to the p-side, and more holes on the p-side have enough energy to surmount the barrier and move to the n-side, resulting in forward-bias current flow. The concentration of carriers on each side with sufficient energy to surmount the barrier increases exponentially with voltage because the Fermi distribution function well above the Fermi level, and 1-f(E) well below the Fermi level, depend approximately exponentially on voltage/kT.

## Page 2

### Problem 2 [25 points total]

Consider Circuit FE-2 shown at right.

**Figure: Circuit FE-2.** $\mathbf{V}_s(\omega)$ → $R_s$ → node 1 (shunt $C_1$) → $L$ → node 2 (shunt $C_2$, shunt $R_L$); $\mathbf{V}_o(\omega)$ across $R_L$.

(a) What type of filter is this? Explain your reasoning in terms of the limiting behavior of the circuit's components at low and high frequency.
**Answer:** Low-pass filter

(b) Assume, for just part (b) of the problem, that $R_L \to \infty$. Calculate the transfer function $\mathbf{H}(\omega) \equiv \mathbf{V}_o(\omega)/\mathbf{V}_s(\omega)$ in this limit. ...
**Answer (handwritten):**
$$\mathbf{H}(\omega) = \frac{1}{1 + j\omega R_s(C_1 + C_2) - \omega^2 L C_2 - j\omega^3 R_s L C_1 C_2}$$

(c) Now assume that $R_L$ is finite and nonzero. Calculate the transfer function $\mathbf{H}(\omega) \equiv \mathbf{V}_o(\omega)/\mathbf{V}_s(\omega)$ in terms of (as needed) $R_s$, $R_L$, $C_1$, $C_2$, $L$, and $\omega$. ...
**Answer (handwritten):**
$$\mathbf{H}(\omega) = \frac{j\omega L/R_s}{\left(1 - \omega^2 L C_1 + j\omega\dfrac{L}{R_s}\right)\left(1 - \omega^2 L C_2 + j\omega\dfrac{L}{R_L}\right) - 1}$$

(d) Show that your expression for $\mathbf{H}(\omega)$ from part (c) yields the correct result for $\omega \to 0$.
**Answer:** (none printed.)

### Problem 3 [25 points total]

Consider Circuit FE-3 shown at right. Assume the op-amp always behaves according to the ideal op-amp model.

**Figure: Circuit FE-3.** Sallen-Key: $\mathbf{I}_s(\omega)$ → $R_1$ → node A → $R_2$ → node B → op-amp + input (top pin); $C_1$ from node A to the output; $C_2$ from node B to ground; − input (bottom pin) tied to the output; $\mathbf{V}_o(\omega)$ at the output.

(a) What type of filter is this? Explain your reasoning in terms of the limiting behavior of the circuit's components at low and high frequency.
**Answer:** Low-pass filter

(b) Calculate the transfer function $\mathbf{H}(\omega) \equiv \mathbf{V}_o(\omega)/\mathbf{V}_s(\omega)$ as a function of (as needed) $R_1$, $R_2$, $C_1$, $C_2$, and $\omega$. Your result should contain only factors corresponding to constants and simple or quadratic zeroes or poles.
**Answer (handwritten):**
$$\mathbf{H}(\omega) = \frac{1}{1 + j\omega(R_1 + R_2)C_2 - \omega^2 R_1 R_2 C_1 C_2}$$

(c) For part (c) of this problem only, assume $R_1 = R_2 = 1000\,\Omega$, and $C_1 = C_2 = 1\,\mu$F. Construct the Bode magnitude and phase plots for the transfer function $\mathbf{H}(\omega)$. ... all phase angles $\phi(\omega)$ should satisfy $-180° \le \phi(\omega) < 180°$.

## Page 3

(Problem 3(c) continued.)
**Answer (handwritten Bode sketch):**
- **Figure: Bode magnitude plot.** $M(\omega)\,[\text{dB}]$ vs $\omega$; "0dB" on the vertical axis. Corner labeled "1000 rad/s". Flat at 0 dB up to 1000 rad/s, then down at slope labeled "$-40$dB/decade". ($\omega_p = 1/\sqrt{R_1R_2C_1C_2} = 1/(10^3\cdot10^{-6}) = 10^3$ rad/s.)
- **Figure: Bode phase plot.** $\phi(\omega)$ vs $\omega$ (rad/s); vertical marks $180°$ (top), $0°$, $-180°$ (dashed line at $-180°$); horizontal ticks labeled $100$, $1000$, $10000$. Flat at $0°$ to 100 rad/s, straight line down through $-90°$ at 1000 rad/s to $-180°$ at 10000 rad/s, flat after.

(d) Now assume again that $R_1$, $R_2$, $C_1$, $C_2$, and $\omega$ can each take on any positive value. We can define an input impedance for this circuit, $\mathbf{Z}_{in}$, to be $\mathbf{Z}_{in} = \mathbf{V}_s/\mathbf{I}_s$. Calculate $\mathbf{Z}_{in}$ as a function of (as needed) $R_1$, $R_2$, $C_1$, $C_2$, and $\omega$.
**Answer (handwritten):**
$$\mathbf{Z}_{in} = \frac{1 + j\omega(R_1 + R_2)C_2 - \omega^2 R_1 R_2 C_1 C_2}{j\omega C_2\left(1 + j\omega R_2 C_1\right)}$$

(e) Demonstrate that your result for part (d) is correct for $\omega \to 0$ and $\omega \to \infty$.
**Answer:** (none printed.)

### Problem 4 [25 points total]

Consider Circuit FE-4 shown at right The input signal is given by $v_s(t) = 4e^{-5t}\cos(100t)\,u(t)$ V, with $u(t) = 1$ for $t \ge 0$, $0$ for $t < 0$.

**Figure: Circuit FE-4.** Same Sallen-Key as FE-3, time domain, op-amp drawn with − on the top pin (tied to the output) and + on the bottom pin (node B); $C_1$ from node A to the output; $C_2$ from node B to ground; $v_o(t)$ at the output.

(a) Determine the Laplace transform, $V_s(s)$, of $v_s(t)$. Explain how you arrived at your result.
**Answer (handwritten):**
$$V_s(s) = \frac{4(s + 5)}{(s + 5)^2 + \omega^2} = \frac{4(s + 5)}{(s + 5)^2 + 10^4}$$

(b) Assume $R_1 = R_2 = 1000\,\Omega$, and $C_1 = C_2 = 10\,\mu$F. Use the Laplace transform technique to calculate $v_o(t)$ for all values of $t$.
**Answer (typed, bold):**
$v_o(t) = 0$ for $t \le 0$
$$v_o(t) = \left[0.10775\,e^{-100t} - 199.74\,t\,e^{-100t} + 2.102\,e^{-5t}\sin(100t - 2.94°)\right]u(t)\ \text{V for } t \ge 0$$

(c) Show that your result for $v_o(t)$ in part (b) satisfies the correct boundary condition for $v_o(t)$ at $t = 0$.
**Answer:** $v_o(t)$ must be continuous at $t = 0$.

(Rest of page 3 blank.)

## Page 4

**Laplace transform handout** ("ECE 411H: Laplace Transforms — Fall 2025"), appended to the answer key.

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

## Index terms

Final Exam, Fall 2025, short answers, answer key, Problem 1, Problem 2, Problem 3, Problem 4, Circuit FE-1abc, low-pass filter, maximum |H| = 1 at omega = 1/sqrt(LC), RC step response, 1.833 ms, Circuit FE-1d, R1 = 0, maximum power transfer, forward-biased pn junction, Fermi distribution, 1 - f(E), exponential in voltage/kT, Circuit FE-2, third-order ladder, low-pass, H = 1/(1 + j omega R_s (C1 + C2) - omega^2 L C2 - j omega^3 R_s L C1 C2), H = (j omega L/R_s)/((1 - omega^2 L C1 + j omega L/R_s)(1 - omega^2 L C2 + j omega L/R_L) - 1), Circuit FE-3, Sallen-Key, H = 1/(1 + j omega (R1 + R2) C2 - omega^2 R1 R2 C1 C2), corner 1000 rad/s, -40 dB/decade, phase 0 to -180, Z_in = (1 + j omega (R1 + R2) C2 - omega^2 R1 R2 C1 C2)/(j omega C2 (1 + j omega R2 C1)), Circuit FE-4, V_s(s) = 4(s + 5)/((s + 5)^2 + 10^4), damped cosine, repeated pole, v_o(t) = 0.10775 e^-100t - 199.74 t e^-100t + 2.102 e^-5t sin(100t - 2.94 deg), continuity at t = 0, Laplace handout, Laplace transform pairs, Table 12-1, Table 12-3
