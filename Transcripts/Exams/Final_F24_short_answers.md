---
course: ECE 411H
kind: past-exam
source: Exam Preparation Materials/ECE_411H_FE_short-answers_F24.pdf
source_pages: 5
author: Prof. Ed Yu
unit: final
topics: [final-exam, short-answers, high-pass-filter, band-reject-filter, resonant-frequency, fourier-transform, band-gap, rc-high-pass, rl-low-pass, bode-plot, average-power, apparent-power, power-factor, cutoff-frequency, active-band-pass, bandwidth, laplace-transform, rc-ladder, laplace-handout]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
---

# ECE 411H Final Exam — Fall 2024 — Short Answers

**Summary.** Instructor's answer key for the Fall 2024 final: question sheet with typed bold answers and pasted handwritten results; page 5 is the Laplace handout. Key results: high-pass across c,d; band-reject across b,d; $\omega_0 = 25{,}000$ rad/s (3979 Hz); Fourier transform; germanium. $\mathbf{H}_1 = j\omega R_1C/(1 + j\omega R_1C)$ (high-pass, $\omega_0 = 1/R_1C$), $\mathbf{H}_2 = 1/(1 + j\omega L/R_2)$ (low-pass, $\omega_1 = R_2/L$); $P_1$, $P_2$ formulas; $C = 12.5\,\mu$F, $L = 0.8$ mH; at $\omega_c$: $P_s = \frac{|V_s|^2}{2\sqrt2}\sqrt{R_1^{-2} + R_2^{-2}}$, $P_1 = |V_s|^2/4R_1$, $P_2 = |V_s|^2/4R_2$, pf $= \frac{1}{\sqrt2}(R_1^{-1}+R_2^{-1})/\sqrt{R_1^{-2}+R_2^{-2}}$. Active band-pass $\mathbf{H} = -j\omega R_3C_1/[1 + R_1/R_2 + j\omega R_1(C_1+C_2) - \omega^2R_1R_3C_1C_2]$, bandwidth 721 rad/s (linear approx.) vs 200.3 rad/s (exact). $V_s(s) = 5/s - 5/(s+10)$; $v_{out}(t) = [0.9453e^{-68.34t} - 7.138\times10^{-3}e^{-731.66t} - 5.938e^{-10t} + 5]$ V. Question text identical to `Final_F24_questions.md`.

## Page 1

FINAL EXAM — ECE 411H — 16 December 2024 (header and rules block identical to the question sheet).

### Problem 1 [25 points total]

**Figure: Circuit FE-1abcd.** $v_s(t)$ at left; right-side vertical string with open terminals $a$ (top), $R$, $b$, $C$, $c$, $L$, $d$ (bottom).

(a) [5 points] Consider Circuit FE-1abcd shown at right. Which two terminals should be selected as the output terminals for a high-pass filter? Explain.
**Answer:** c,d

(b) [5 points] Consider Circuit FE-1abcd shown at right. Which two terminals should be selected as the output terminals for a band-reject filter? Explain.
**Answer:** b,d

(c) [5 points] Consider Circuit FE-1abcd shown at right. If $R = 1\,\text{k}\Omega$, $C = 2\,\mu$F, and $L = 0.8$ mH, what is the resonant frequency of the circuit? Your answer should be a numerical value with appropriate units.
**Answer:** 25,000 rad/s (or 3979 Hz)

(d) [5 points] Consider Circuit FE-1abcd shown at right, with $v_s(t) = 5$ for $t < 0$, $5e^{-10t}\cos(\omega t)$ for $t \ge 0$. The output terminals for the circuit are $b$ and $c$. Would the most efficient way to solve this problem be to use phasors, Laplace transforms, Fourier series, Fourier transforms, or time-domain analysis? Explain.
**Answer:** Fourier transform

(e) [5 points] Consider two different semiconductor materials, silicon and germanium, both of which have no dopants or defects, at room temperature. Silicon has an energy band gap of 1.12 eV, and germanium an energy band gap of 0.67 eV. Which semiconductor would you expect to have a higher concentration of holes in the valence band? Explain.
**Answer:** Germanium

## Page 2

### Problem 2 [25 points total]

Consider Circuit FE-2 shown at right.

**Figure: Circuit FE-2.** $\mathbf{V}_s(\omega)$ feeding two parallel branches: $C$ over $R_1$ (with $\mathbf{V}_1(\omega)$ across $R_1$) and $L$ over $R_2$ (with $\mathbf{V}_2(\omega)$ across $R_2$).

(a) Calculate the transfer function $\mathbf{H}_1(\omega) \equiv \mathbf{V}_1(\omega)/\mathbf{V}_s(\omega)$ ... Then construct the Bode magnitude and phase plots for $\mathbf{H}_1$ ...
**Answer (handwritten):**
$$\mathbf{H}_1(\omega) = \frac{\mathbf{V}_1}{\mathbf{V}_s} = \frac{j\omega R_1 C}{1 + j\omega R_1 C}$$
"Bode plots:" with boxed $\omega_0 = \dfrac{1}{R_1 C}$.
- **Figure: Bode magnitude plot for $\mathbf{H}_1$.** $M(\omega)\,[\text{dB}]$ vs $\omega$; "0" on the vertical axis. Corner labeled "$\omega_0 = 1/R_1C$". Curve rises at slope labeled "20dB/decade" up to 0 dB at $\omega_0$, then flat at 0 dB.
- **Figure: Bode phase plot for $\mathbf{H}_1$.** $\phi(\omega)$ vs $\omega$; vertical marks $90°$, $0°$; horizontal ticks $0.1\omega_0$, $\omega_0$, $10\omega_0$ with dashed verticals at $0.1\omega_0$ and $10\omega_0$. Flat at $90°$ to $0.1\omega_0$, straight line down to $0°$ at $10\omega_0$, flat after.

(b) Calculate the transfer function $\mathbf{H}_2(\omega) \equiv \mathbf{V}_2(\omega)/\mathbf{V}_s(\omega)$ ... Then construct the Bode magnitude and phase plots for $\mathbf{H}_2$ ...
**Answer (handwritten):**
$$\mathbf{H}_2(\omega) = \frac{\mathbf{V}_2}{\mathbf{V}_s} = \frac{1}{1 + j\omega L/R_2}$$
"Bode plots:" with boxed $\omega_1 = \dfrac{R_2}{L}$.
- **Figure: Bode magnitude plot for $\mathbf{H}_2$.** Flat at 0 dB up to the corner labeled "$\omega_1 = R_2/L$", then down at slope labeled "$-20$dB/decade".
- **Figure: Bode phase plot for $\mathbf{H}_2$.** Vertical marks $0°$, $-90°$ (dashed line at $-90°$); horizontal ticks $0.1\omega_1$, $\omega_1$, $10\omega_1$ with dashed verticals. Flat at $0°$ to $0.1\omega_1$, straight line down to $-90°$ at $10\omega_1$, flat after.

(c) Calculate the average power dissipated by (i) the resistor $R_1$ and (ii) the resistor $R_2$ as functions of (as needed) $R_1$, $R_2$, $C$, $L$, $|\mathbf{V}_s(\omega)|$, and $\omega$.
**Answer (handwritten):**
$$P_1 = \frac{1}{2}\,\frac{(\omega R_1 C)^2}{1 + (\omega R_1 C)^2}\,\frac{|\mathbf{V}_s(\omega)|^2}{R_1},\qquad P_2 = \frac{1}{2}\,\frac{1}{1 + (\omega L/R_2)^2}\,\frac{|\mathbf{V}_s(\omega)|^2}{R_2}$$

(d) Suppose $R_1 = R_2 = 8\,\Omega$. For what values of $C$ and $L$ will the cutoff angular frequencies of $\mathbf{H}_1$ and $\mathbf{H}_2$ both be $10^4$ rad/s? You should give your answers as numerical values with appropriate units.
**Answer (typed):** $C = 12.5\,\mu$F, $L = 0.8$ mH

(e) Assume the cutoff angular frequencies of $\mathbf{H}_1$ and $\mathbf{H}_2$ are both equal to $\omega_c$, and that Circuit FE-2 is operating at $\omega = \omega_c$. ... calculate (i) the apparent power $P_s$ for the voltage source $\mathbf{V}_s(\omega)$, (ii) the average power $P_1$ dissipated by $R_1$, (iii) the average power $P_2$ dissipated by $R_2$, and (iv) the power factor $(P_1 + P_2)/P_s$ ...
**Answer (handwritten):**
$$P_s = \frac{1}{2\sqrt{2}}\,|\mathbf{V}_s|^2\sqrt{\left(\tfrac{1}{R_1}\right)^2 + \left(\tfrac{1}{R_2}\right)^2},\qquad P_1 = \frac{|\mathbf{V}_s|^2}{4R_1},\qquad P_2 = \frac{|\mathbf{V}_s|^2}{4R_2}$$
**power factor =** (typed label, handwritten expression)
$$\text{pf} = \frac{1}{\sqrt{2}}\left(\frac{1}{R_1} + \frac{1}{R_2}\right)\Bigg/\sqrt{\left(\frac{1}{R_1}\right)^2 + \left(\frac{1}{R_2}\right)^2}$$

## Page 3

### Problem 3 [25 points total]

Consider Circuit FE-3 shown at right. Assume the op-amp always behaves according to the ideal op-amp model.

**Figure: Circuit FE-3.** $\mathbf{V}_s(\omega)$ → $R_1$ → node X; $R_2$ from X to ground; $C_1$ from X to the op-amp − input (top pin); $C_2$ from X across the top to the output; $R_3$ from the − input to the output; + input (bottom pin) grounded; $\mathbf{V}_o(\omega)$ at the output.

(a) Calculate the transfer function $\mathbf{H}(\omega) \equiv \mathbf{V}_o(\omega)/\mathbf{V}_s(\omega)$ as a function of (as needed) $R_1$, $R_2$, $R_3$, $C_1$, $C_2$, and $\omega$. What type of filter is Circuit FE-3?
**Answer:** Band pass filter.
**Answer (handwritten):**
$$\mathbf{H}(\omega) = \frac{\mathbf{V}_o}{\mathbf{V}_s} = \frac{-j\omega R_3 C_1}{1 + \dfrac{R_1}{R_2} + j\omega R_1(C_1 + C_2) - \omega^2 R_1 R_3 C_1 C_2}$$

(b) Construct the Bode magnitude and phase plots for the transfer function $\mathbf{H}$ ... For the Bode phase plot, all phase angles $\phi(\omega)$ should satisfy $0° \le \phi(\omega) < 360°$.
**Answer (handwritten):** boxed
$$\omega_0 = \sqrt{\frac{R_1 + R_2}{R_1 R_2 R_3 C_1 C_2}}$$
- **Figure: Bode magnitude plot.** $M(\omega)\,[\text{dB}]$ vs $\omega$. Inverted V peaking at $\omega_0$ (marked on the horizontal axis) at a level labeled on the vertical axis as "$20\log\!\left(\dfrac{R_3 C_1}{R_1(C_1 + C_2)}\right)$" with a dashed horizontal guide. Rising segment labeled "20dB/decade", falling segment labeled "$-20$dB/decade".
- **Figure: Bode phase plot.** $\phi(\omega)$ vs $\omega$; vertical marks $270°$, $180°$, $90°$ (dashed guide at $90°$); horizontal ticks $0.1\omega_0$, $\omega_0$, $10\omega_0$ with dashed verticals at $0.1\omega_0$ and $10\omega_0$. Flat at $270°$ to $0.1\omega_0$, straight line down through $180°$ at $\omega_0$ to $90°$ at $10\omega_0$, flat at $90°$ after.
(Faint bleed-through of handwriting from the reverse side is visible behind this sketch; it is not part of the answer.)

(c) Assume $R_1 = 2.5\,\Omega$, $R_2 = 0.1\,\Omega$, $R_3 = 10\,\Omega$, $C_1 = C_2 = 1$ mF. Using the same linear approximations used to construct Bode plots, calculate the bandwidth of this filter, giving your result as a numerical value with appropriate units.
**Answer:** 721 rad/s

(d) As you did in part (c), assume $R_1 = 2.5\,\Omega$, $R_2 = 0.1\,\Omega$, $R_3 = 10\,\Omega$, $C_1 = C_2 = 1$ mF. Without using the linear approximations used to construct Bode plots, calculate the bandwidth of this filter directly from the transfer function, giving your result as a numerical value with appropriate units. Explain why this result differs from the one you obtained in part (c).
**Answer:** 200.3 rad/s

### Problem 4 [25 points total]

Consider Circuit FE-4 shown at right The input signal is given by $v_s(t) = 5(1 - e^{-10t})u(t)$ V, with $u(t) = 1$ for $t \ge 0$, $0$ for $t < 0$.

**Figure: Circuit FE-4.** RC ladder: $v_s(t)$ → $R_1$ → node A (shunt $C_1$) → $R_2$ → node B (shunt $C_2$); $v_{out}(t)$ across $C_2$.

(a) Calculate the Laplace transform of $v_s(t)$.
**Answer (handwritten):**
$$V_s(s) = \frac{5}{s} - \frac{5}{s + 10}$$

## Page 4

(b) Assume $R_1 = 2\,\text{k}\Omega$, $R_2 = 5\,\text{k}\Omega$, $C_1 = 1\,\mu$F, and $C_2 = 2\,\mu$F. Use the Laplace transform technique to calculate $v_{out}(t)$.
**Answer (handwritten, boxed, pasted over the question line):**
$$v_{out}(t) = \left[(0.9453)e^{-68.34t} - (7.138\times10^{-3})e^{-731.66t} - (5.938)e^{-10t} + 5\right]\ \text{V}$$

(c) Your result for $v_{out}(t)$ in part (b) should not exhibit any oscillatory behavior. Show mathematically that with $C_1 = 1\,\mu$F and $C_2 = 2\,\mu$F, there is no combination of positive values of $R_1$ and $R_2$ for which oscillatory behavior will be observed in $v_{out}(t)$.
**Answer:** (none printed — derivation left to the student; the key gives no short answer for this part.)

(Rest of page 4 blank.)

## Page 5

**Laplace transform handout** ("ECE 411H: Laplace Transforms — Fall 2024"), appended to the answer key.

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

## Index terms

Final Exam, Fall 2024, short answers, answer key, Problem 1, Problem 2, Problem 3, Problem 4, Circuit FE-1abcd, high-pass c d, band-reject b d, resonant frequency 25000 rad/s, 3979 Hz, Fourier transform, germanium, Circuit FE-2, H1 = j omega R1 C/(1 + j omega R1 C), omega_0 = 1/(R1 C), RC high-pass, H2 = 1/(1 + j omega L/R2), omega_1 = R2/L, RL low-pass, 20 dB/decade, -20 dB/decade, P1 = (1/2)(omega R1 C)^2/(1 + (omega R1 C)^2) |Vs|^2/R1, P2 = (1/2) 1/(1 + (omega L/R2)^2) |Vs|^2/R2, C = 12.5 uF, L = 0.8 mH, apparent power P_s, P1 = |Vs|^2/4R1, P2 = |Vs|^2/4R2, power factor, Circuit FE-3, active band-pass, H = -j omega R3 C1/(1 + R1/R2 + j omega R1 (C1 + C2) - omega^2 R1 R3 C1 C2), omega_0 = sqrt((R1 + R2)/(R1 R2 R3 C1 C2)), peak 20 log(R3 C1/(R1 (C1 + C2))), phase 270 to 90, bandwidth 721 rad/s, bandwidth 200.3 rad/s, Circuit FE-4, RC ladder, V_s(s) = 5/s - 5/(s + 10), v_out(t) = 0.9453 e^-68.34t - 7.138e-3 e^-731.66t - 5.938 e^-10t + 5, no oscillation, Laplace handout, Laplace transform pairs, Table 12-1, Table 12-3
