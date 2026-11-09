---
course: ECE 411H
kind: past-exam
source: Exam Preparation Materials/ECE_411H_SE2_short-answers_F23.pdf
source_pages: 3
author: Prof. Ed Yu
unit: exam2
topics: [semester-exam-2, short-answers, quality-factor, n-type-doping, fermi-distribution, pn-junction, band-pass-filter, high-pass-filter, band-reject-filter, transfer-function, bode-plot, inverting-op-amp-filter, parallel-lc, bandwidth]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
---

# ECE 411H Semester Exam 2 — Fall 2023 — Short Answers

**Summary.** Instructor's answer key for the Fall 2023 Semester Exam 2. The document is the exam question sheet with the final answers inserted after each part: typed bold text for the conceptual/numeric answers, and pasted handwritten (pen on ruled paper) snippets for the transfer functions and Bode sketches. No intermediate work is shown. Covers: Q vs R, As for n-type, Fermi-function argument, output across R for band-pass; Z = 0.1 H inductor, series LC notch with $LC = 2.5\times10^{-7}\ \text{s}^2$; inverting op-amp filter $\mathbf{H} = -L_fC_s(j\omega)^2/[(1+j\omega R_sC_s)(1+j\omega L_f/R_f)]$ with Bode plots; parallel-LC band-pass $\mathbf{H} = j\omega L/[R(1 + j\omega L/R + (j\omega\sqrt{LC})^2)]$ with $\omega_p = 5000$ rad/s. Question text is identical to `SE2_F23_questions.md`; it is reproduced here so each answer sits next to its prompt.

## Page 1

SEMESTER EXAM 2 SHORT ANSWERS — ECE 411H — Fall 2023

(Same header/rules block as the question sheet: PLEASE ATTEMPT ALL PROBLEMS AND SHOW ALL WORK! ... 70 minutes ... ONLY THE FRONT SIDE OF EACH SHEET WILL BE GRADED.)

### Problem 1 [25 points total]

(a) [6 points] Recall that the quality factor $Q$ of a filter is given by $Q = 2\pi\left(W_{stored}/W_{dissipated}\right)\big|_{\omega=\omega_0}$. Based on this definition of $Q$, does a very small value of $R$ in an RLC series filter circuit lead to a high or low value for $Q$? Explain.
**Answer (typed, bold):** High value of Q. R dissipates power so small R reduces the denominator in Q.

(b) [6 points] To create an n-type semiconductor from a crystal of pure Si, would you replace some of the Si atoms with B (boron, 3 valence electrons/atom) or As (arsenic, 5 valence electrons/atom)? Explain your answer.
**Answer:** As, since extra valence electron compared to Si will occupy a state in the conduction band.

(c) [6 points] Explain, in terms of the Fermi distribution function and its dependence on energy, why the current in a pn junction diode increases exponentially with voltage $V$, for $V > 0$.
**Answer:** Fermi distribution function decreases exponentially with increasing energy. Increasing V>0 lowers barrier for carriers to traverse the pn junction by qV, and therefore exponentially increases the concentration of carriers with sufficient energy to cross the pn junction and contribute to current flow.

(d) [7 points] In a series RLC filter circuit, across which single component ($R$, $L$, or $C$) should the output terminals be connected to create a band pass filter? Explain your answer.
**Answer:** R. By voltage division, most of the input voltage will be across C at low frequencies, and across L at high frequencies, so voltage across R will be maximum at intermediate frequencies leading to formation of pass band.

### Problem 2 [25 points total]

Consider Circuit SE2-2 shown at right. All numerical values given in this problem are exact.

**Figure: Circuit SE2-2.** Same as in the question sheet: $\mathbf{V}_s$ (+ top) → series $R = 100\,\Omega$ on top rail → shunt box $\mathbf{Z}$ to bottom rail; $\mathbf{V}_{out}$ (+ top, − bottom) across $\mathbf{Z}$ at open terminals on the right.

(a) Suppose for this part of the problem that the circuit element $\mathbf{Z}$ in Circuit SE2-2 consists of a single component, i.e., a resistor, a capacitor, or an inductor. For the circuit to function as a high-pass filter with corner frequency $\omega_c = 1000$ rad/s, what type of component should $\mathbf{Z}$ be (resistor, capacitor, or inductor), and what should its value be?

## Page 2

(Problem 2(a) continued) ... or inductor), and what should its value be?
**Answer:** Inductor, 0.1 H.

(b) Now suppose that $\mathbf{Z}$ consists of 2 individual components connected in series with each other. For the circuit to function as a band-reject filter, what should those components be (choose two from resistor, capacitor, and inductor). Explain your answer.
**Answer:** Capacitor and inductor. Most of the input voltage will be across C at low frequencies, and across L at high frequencies, leading to a minimum in transfer function at intermediate frequencies.

(c) For the two components you chose in part (b), compute numerical values of the components that will yield $\mathbf{V}_{out} = 0$ at $\omega = 2000$ rad/s. Are there other component values for which $\mathbf{V}_{out} = 0$ as well? Explain why or why not.
**Answer:** Any combination of L and C with $LC = 2.5\times10^{-7}\ \text{s}^2$, e.g., C = 2.5 uF, L = 0.1 H.

### Problem 3 [25 points total]

Consider Circuit SE2-3 shown at right. All the numerical values given in this problem are exact, and the op amp is always in its linear region of behavior.

**Figure: Circuit SE2-3.** Same as question sheet: $\mathbf{V}_s$ (− grounded) → $R_s$ → $C_s$ → op-amp inverting input; + input grounded; feedback $R_f \parallel L_f$ from output to − input; $\pm V_{cc}$ supplies; $\mathbf{V}_{out}$ from output to ground.

(a) Calculate the transfer function $\mathbf{H}(\omega) = \mathbf{V}_{out}/\mathbf{V}_s$ in terms of $R_s$, $C_s$, $R_f$, $L_f$, and $\omega$. Your answer should be in an algebraic form that makes it very straightforward to identify the factors corresponding to any zeros or poles that are present.
**Answer (handwritten):**
$$\mathbf{H}(\omega) = \frac{-L_f C_s (j\omega)^2}{(1 + j\omega R_s C_s)(1 + j\omega L_f/R_f)}$$

(b) Suppose $R_s = 100\,\Omega$, $C_s = 1\,\mu$F, $R_f = 1\,\text{k}\Omega$, and $L_f = 10\,\text{mH}$. Construct the Bode magnitude and phase plots for this circuit, using linear approximations as done in class. Be sure to label the key values on the vertical and horizontal axes of each plot, and any nonzero slopes in BOTH the Bode magnitude plot and the Bode phase plot.
**Answer (handwritten Bode sketch):**
- **Figure: Bode magnitude plot.** Axes $M(\omega)\,[\text{dB}]$ vs $\omega$ (log). A dashed horizontal reference line at 20 dB (labeled "20dB" on the vertical axis). Curve: rises from the lower left with slope labeled "40dB/dec" up to the corner at $\omega = 10^4$ (marked on the horizontal axis), then continues rising with slope labeled "20dB/dec" up to the corner at $\omega = 10^5$, where it flattens at 20 dB for all higher $\omega$. (Corners: $1/(R_sC_s) = 10^4$ rad/s and $R_f/L_f = 10^5$ rad/s; high-frequency gain $R_f/R_s = 10 \Rightarrow 20$ dB.)
- **Figure: Bode phase plot.** Axes $\phi(\omega)$ vs $\omega$ with tick labels $10^3$, $10^4$, $10^5$, $10^6$ along the top of the horizontal axis; vertical axis marked $-90°$ and $-180°$. Dashed vertical lines at each decade tick. Curve: flat at $0°$ up to $10^3$; from $10^3$ to $10^4$ falls with slope labeled "$-45°$/dec"; from $10^4$ to $10^5$ falls with slope labeled "$-90°$/dec" (passing through $-90°$ at about $10^{4.5}$); from $10^5$ to $10^6$ falls with slope labeled "$-45°$/dec" (arrow pointing to that segment), reaching $-180°$ at $10^6$ and flat thereafter. (Two simple poles with corners a decade apart: their $\pm$decade phase ramps overlap between $10^4$ and $10^5$.)

(c) What is the value, in terms of (as needed) $R_s$, $C_s$, $R_f$, and $L_f$, of $M(\omega) = |\mathbf{H}(\omega)|$ as $\omega \to \infty$? Does this result make sense to you? Explain why or why not.
**Answer:** $M = R_f/R_s$. This makes sense because at high frequencies C is short, L is open and circuit looks like an inverting amplifier, which has gain of magnitude $R_f/R_s$.

## Page 3

### Problem 4 [25 points total]

Consider Circuit SE2-4 shown at right. All numerical values given in this problem are exact.

**Figure: Circuit SE2-4.** Same as question sheet: $\mathbf{V}_s$ → series $R$ → shunt $C \parallel L$ → $\mathbf{V}_{out}$ across the tank (+ top, − bottom).

(a) Calculate the transfer function $\mathbf{H}(\omega) = \mathbf{V}_{out}/\mathbf{V}_s$ in terms of $R$, $L$, $C$, and $\omega$.
**Answer (handwritten):**
$$\mathbf{H}(\omega) = \frac{j\omega L}{R\left(1 + j\omega\frac{L}{R} + \left(j\omega\sqrt{LC}\right)^2\right)}$$

(b) Suppose $R = 100\,\Omega$, $C = 40\,\mu$F, and $L = 1\,\text{mH}$. Construct the Bode magnitude and phase plots for this circuit, using linear approximations as done in class. Be sure to label the key values on the vertical and horizontal axes of each plot, and any nonzero slopes in the Bode magnitude plot.
**Answer (handwritten Bode sketch):**
- **Figure: Bode magnitude plot.** Axes $M(\omega)\,[\text{dB}]$ vs $\omega$; "0dB" marked on the vertical axis at the level of the horizontal axis. Curve is an inverted V: rises at slope labeled "20dB/dec" to a peak touching 0 dB at $\omega_p$ (marked on the horizontal axis), then falls at slope labeled "$-20$dB/dec".
- **Figure: Bode phase plot.** Axes $\phi(\omega)$ vs $\omega$, vertical ticks $90°$, $0°$, $-90°$; horizontal ticks $0.1\omega_p$, $\omega_p$, $10\omega_p$. Curve: flat at $+90°$ up to $0.1\omega_p$, straight line down through $0°$ at $\omega_p$ to $-90°$ at $10\omega_p$, flat at $-90°$ thereafter.
- Handwritten calculation below the plots:
$$\omega_p = \frac{1}{\sqrt{LC}} = \frac{1}{\sqrt{(10^{-3})(4\times10^{-5})}} = \frac{1}{2\times10^{-4}} = \tfrac{1}{2}\times10^{4} = 5000\ \text{rad/s}.$$

(c) What type of filter is this? Explain why it works this way, in terms of the component impedances as functions of frequency.
**Answer:** Band pass filter. L becomes short at low frequency, C becomes short at high frequency, so transfer function is 0 in those limits. At quadratic pole frequency, H = 1.

(d) Suppose $R$ increases from $100\,\Omega$ to $1000\,\Omega$. Would the bandwidth of the filter increase or decrease? Explain your answer.
**Answer (typed):** As R increases, bandwidth decreases.
**Answer (handwritten, two lines below):** "As R increases, bandwidth decreases" [boxed] "because $\mathbf{Z}_{L\parallel C} \to \infty$ as $\omega \to \omega_p$, and larger R means $|\mathbf{H}(\omega)| = 1/\sqrt{2}$ for a larger value of $\mathbf{Z}_{L\parallel C}$, or smaller deviation in $\omega$."

## Index terms

Semester Exam 2, Fall 2023, short answers, answer key, Problem 1, Problem 2, Problem 3, Problem 4, quality factor, Q, W_stored, W_dissipated, high Q small R, n-type, arsenic, conduction band, Fermi distribution, barrier lowering qV, exponential current, band pass, output across R, voltage division, Circuit SE2-2, inductor 0.1 H, high-pass, band-reject, series LC, LC = 2.5e-7, C = 2.5 uF, L = 0.1 H, Circuit SE2-3, inverting op amp filter, H(omega) = -L_f C_s (j omega)^2 / ((1 + j omega R_s C_s)(1 + j omega L_f/R_f)), Bode magnitude, 40 dB/dec, 20 dB/dec, corner 10^4, corner 10^5, 20 dB, Bode phase, -45 deg/dec, -90 deg/dec, -180 deg, M = R_f/R_s, inverting amplifier limit, Circuit SE2-4, parallel LC, H(omega) = j omega L / (R(1 + j omega L/R + (j omega sqrt(LC))^2)), omega_p = 1/sqrt(LC), 5000 rad/s, band pass, 0 dB peak, +20 dB/dec, -20 dB/dec, phase 90 to -90, bandwidth decreases with R, Z_L||C
