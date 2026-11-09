---
course: ECE 411H
kind: past-exam
source: Exam Preparation Materials/ECE_411H_SE2_short-answers_F24.pdf
source_pages: 3
author: Prof. Ed Yu
unit: exam2
topics: [semester-exam-2, short-answers, low-pass-filter, acceptor-doping, fermi-level, pn-junction, maximum-power-transfer, impedance-matching, rc-low-pass, cutoff-frequency, bode-plot, sallen-key, second-order-low-pass, butterworth-filter]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
---

# ECE 411H Semester Exam 2 — Fall 2024 — Short Answers

**Summary.** Instructor's answer key for the Fall 2024 Semester Exam 2: question sheet with typed bold answers and pasted handwritten snippets. Key results: output across C for low-pass; acceptors create holes so $E_F$ moves toward the VB; low-pass (across C) or high-pass (across L) can exceed $|H|=1$; $P_{load} = \tfrac12 V_s^2 R/[(R_s+R)^2 + \omega^2L^2]$ and the matching values $C = L/(\omega^2L^2 + R^2)$, $R' = R_s - R/[(1-\omega^2LC)^2 + (\omega RC)^2]$; RC low-pass cutoffs 990.1 and 909.1 rad/s, $\omega_p = 1/RC = 10^3$ rad/s; Sallen-Key $\mathbf{H} = 1/[1 + j\omega(R_1+R_2)C_2 - \omega^2R_1C_1R_2C_2]$, $\omega_p = 1/\sqrt{R_1C_1R_2C_2}$, Butterworth needs $C_1/C_2 = 2$. Question text identical to `SE2_F24_questions.md`.

## Page 1

SEMESTER EXAM 2 — ECE 411H — 13 November 2024 (header and rules identical to the question sheet; note this answer-key copy keeps the plain "SEMESTER EXAM 2" header rather than "SHORT ANSWERS").

### Problem 1 [25 points total]

(a) [6 points] In a series RLC filter circuit, across which single component (R, L, or C) should the output terminals be positioned in order to create a low-pass filter? Explain your answer.
**Answer:** Across capacitor

(b) [6 points] Explain why the introduction of acceptor atoms into a semiconductor crystal, e.g., B (3 valence electrons) into Si (4 valence electrons), causes the Fermi level to move closer to the valence-band edge energy of the semiconductor.
**Answer:** Acceptor removes electrons from/creates holes in the valence band; probably [sic — "probability"] of finding empty states in the valence band increases, so Fermi level must move closer to valence band.

(c) [6 points] Explain, in terms of the mathematical form of the Fermi distribution function, why current in a pn junction diode increases exponentially with increasing voltage.
**Answer:** Energy barrier for carriers to diffuse across junction decreases with positive V, so from form of f(E) one can show that current increases exponentially.

(d) [7 points] Consider a series RLC filter circuit with output terminals positioned across a single component (R, L, or C). For which types of filter circuits constructed in this manner can the maximum magnitude of the transfer function be greater than 1? Explain your answer.
**Answer:** Low-pass (output terminals across C) or high-pass (output terminals across L).

### Problem 2 [25 points total]

Consider Circuit SE2-2 at right. The input signal $\mathbf{V}_s$ is a sinusoidal signal with amplitude $V_s$ and angular frequency $\omega$.

**Figure: Circuit SE2-2.** As in the question sheet: $\mathbf{V}_s$ → $R_s$ (source) | $R'$ → shunt $C$ → series $L$ → shunt $R$ (load); brackets "source" and "load".

(a) Suppose $C = 0$ and $R' = 0$. Calculate the average power transferred to the load circuit as a function of (as needed) $R_s$, $L$, $R$, $V_s$, and $\omega$.
**Answer (handwritten):**
$$P_{load} = \tfrac{1}{2} V_s^{2} R \Big/ \left[(R_s + R)^2 + \omega^2 L^2\right]$$

(b) Now suppose $C > 0$ and $R' > 0$. Calculate the values of $C$ and $R'$ that maximize average power transfer to the load circuit. Your answers should be functions of (as needed) $R_s$, $L$, $R$, and $\omega$.
**Answer (handwritten, two boxed expressions):**
$$C = \frac{L}{\omega^2 L^2 + R^2}$$
$$R' = R_s - \frac{R}{(1 - \omega^2 LC)^2 + (\omega R C)^2}$$

## Page 2

### Problem 3 [25 points total]

Consider Circuits SE2-3 at right. The input voltage is $\mathbf{V}_s$, and the output voltage is $\mathbf{V}_o$.

**Figure: Circuit SE2-3.** As in the question sheet: $\mathbf{V}_s(\omega)$ → $R_s$ → $R$ → shunt $C$; $\mathbf{V}_o(\omega)$ across $C$.

(a) What type of filter circuit is this? Explain your answer.
**Answer:** Low-pass filter.

(b) Suppose $R_s$ can range from $100\,\Omega$ to $1000\,\Omega$, with $R = 10\,\text{k}\Omega$ and $C = 0.1\,\mu$F. Calculate the cutoff frequency (or frequencies) $\omega_c$, i.e., the frequency (or frequencies) at which $|H(\omega)| \equiv |\mathbf{V}_o/\mathbf{V}_s| = 1/\sqrt{2}$, for (i) $R_s = 100\,\Omega$ and (ii) $R_s = 1000\,\Omega$.
**Answer (handwritten):**
- (i) $R_s = 100\,\Omega$: $\omega_c = 1/\big((10{,}100)(10^{-7})\big) = 990.1$ rad/s
- (ii) $R_s = 1000\,\Omega$: $\omega_c = 1/\big((11{,}000)(10^{-7})\big) = 909.1$ rad/s

(c) Now suppose $R_s = 0\,\Omega$, $R = 10\,\text{k}\Omega$, and $C = 0.1\,\mu$F. Construct the Bode magnitude and phase plots for this circuit, using linear approximations for low and high frequencies as done in class. For the phase plot, all angles should be plotted in the range $-180° \le \phi \le 180°$. Be sure to label the key values on the vertical and horizontal axes of each plot, and any nonzero slopes in the Bode magnitude plot.
**Answer (handwritten Bode sketch):**
- **Figure: Bode magnitude plot.** $M(\omega)$ vs $\omega$; flat at 0 dB from the left up to the corner labeled "$\omega_p = 10^3$ rad/s", then a straight line down with slope labeled "$-20$dB/decade".
- **Figure: Bode phase plot.** $\phi(\omega)$ vs $\omega$; horizontal ticks labeled $10^2$, $10^3$, $10^4$ rad/s; vertical marks $0°$ and $-90°$ (dashed line at $-90°$). Curve: $0°$ flat up to $10^2$, straight line down to $-90°$ at $10^4$ (passing $-45°$ at $10^3$), flat at $-90°$ after.
- Handwritten to the right: $\omega_p = \dfrac{1}{RC} = 10^3$ rad/s.

### Problem 4 [25 points total]

Consider Circuit SE2-4 shown below. Assume that the op amp in the circuit always behaves in accordance with the ideal op-amp model.

**Figure: Circuit SE2-4.** Sallen-Key unity-gain low-pass, as in the question sheet: $\mathbf{V}_s(\omega)$ → $R_1$ → node A → $R_2$ → node B → op-amp + input; $C_1$ from node A to op-amp output; $C_2$ from node B to ground; − input tied to output; $\mathbf{V}_o(\omega)$ at the output.

(a) Calculate the transfer function $H(\omega) \equiv \mathbf{V}_o/\mathbf{V}_s$ for this circuit. Express your final answer as a product of factors that are each one of the following (as needed): constant, zero@origin, pole@origin, simple zero, simple pole, quadratic zero, or quadratic pole. Your result should be expressed in terms of $R_1$, $R_2$, $C_1$, $C_2$, and $\omega$.
**Answer (handwritten, inserted between the lines of the question):**
$$\mathbf{H}(\omega) = \frac{1}{1 + j\omega(R_1 + R_2)C_2 - \omega^2 R_1 C_1 R_2 C_2}$$

(b) What type of filter is Circuit SE2-4? Explain why it works this way, in terms of the component impedances as functions of frequency.
**Answer:** Low-pass filter, due to limiting behavior of capacitors at low and high frequencies.

(c) Construct the Bode magnitude and phase plots for this circuit, using linear approximations for low and high frequencies as done in class. For the phase plot, all angles should be plotted in the range $-180° \le \phi \le 180°$. Be sure to label the key values on the vertical and horizontal axes of each plot, and any nonzero slopes in the Bode magnitude plot.

## Page 3

(Problem 4(c) continued.)
**Answer (handwritten Bode sketch, labeled "Bode plots:"):**
- **Figure: Bode magnitude plot.** $M(\omega)\,[\text{dB}]$ vs $\omega$; "0dB" on the vertical axis; flat at 0 dB up to the corner $\omega_p$ (marked on the horizontal axis), then a straight line down with slope labeled "$-40$dB/decade".
- **Figure: Bode phase plot.** $\phi(\omega)$ vs $\omega$; vertical marks $0°$, $-90°$, $-180°$ (dashed line at $-180°$); horizontal ticks $0.1\omega_p$, $\omega_p$, $10\omega_p$. Curve: $0°$ flat up to $0.1\omega_p$, straight line down through $-90°$ at $\omega_p$ to $-180°$ at $10\omega_p$, flat thereafter.
- Handwritten to the right: $\omega_p = \dfrac{1}{\sqrt{R_1 C_1 R_2 C_2}}$.

(d) A "Butterworth filter" is a filter designed to have a very flat response across the filter pass band. For Circuit SE2-4, such a filter would have a transfer function magnitude $M(\omega)$ of the form $M(\omega) = 1\big/\sqrt{1 + (\omega/\omega_p)^4}$. Assuming $R_1 = R_2$, calculate the ratio $C_1/C_2$ that would be required to obtain a transfer function corresponding to a Butterworth filter.
**Answer:** $C_1/C_2 = 2$.

## Index terms

Semester Exam 2, Fall 2024, short answers, answer key, Problem 1, Problem 2, Problem 3, Problem 4, low-pass across capacitor, acceptor, holes, valence band, Fermi level, barrier lowering, f(E), exponential current, transfer function greater than 1, low-pass across C, high-pass across L, Circuit SE2-2, source and load, average power, P = (1/2) V_s^2 R / ((R_s + R)^2 + omega^2 L^2), maximum power transfer, C = L/(omega^2 L^2 + R^2), R' = R_s - R/((1 - omega^2 LC)^2 + (omega R C)^2), Circuit SE2-3, RC low-pass, omega_c = 990.1 rad/s, omega_c = 909.1 rad/s, omega_p = 1/RC = 10^3 rad/s, -20 dB/decade, phase 0 to -90, Circuit SE2-4, Sallen-Key, H(omega) = 1/(1 + j omega (R1+R2) C2 - omega^2 R1 C1 R2 C2), quadratic pole, omega_p = 1/sqrt(R1 C1 R2 C2), -40 dB/decade, phase 0 to -180, Butterworth, C1/C2 = 2
