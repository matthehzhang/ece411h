---
course: ECE 411H
date: 2026-10-19
instructor: Prof. Ed Yu
topic: Transfer functions (four types; voltage gain H(ω) = M e^{jφ}), filter terminology (M0, ωc, B, S_G, ω0), RC low-pass and high-pass worked example, decibel scale, Bode-plot definition, dB additivity of factors, first standard factor (1 + jω/ωz)^N
reading: Ulaby/Maharbiz/Furse 3e §9-1 (transfer functions), §9-3 (Bode plots)
source: Recordings/2026-10-19-passive-filters-and-bode-plots (75.6 min transcript + 24 distinct tablet pages from 84 page-final frames; descriptions in frames/pages_described.md)
tags: [ece411, lecture, transfer-function, filters, lowpass, highpass, resonance, decibel, bode-plot, exam2]
source_quality:
  - "Speech: Deepgram Nova-3, 76 min, 1038 utterances, mean confidence 0.96; 75 words < 0.55 (0.8 %); 7 utterances < 0.7 (0:38:36, 1:10:01, 0:16:53 student, 0:24:15, 0:25:09, 0:09:31, 0:29:10). None of them carries math that is not also on the board."
  - "Board: tablet pages that scroll continuously; 24 distinct pages, 60 of 84 page-final frames are scroll/extension states. One blurry frame (f_0023, 0:12:00) is superseded by f_0026."
  - "Frames end at 1:14:24. The phase of the first standard factor, φ = N tan⁻¹(ω/ωz), is speech-only (1:14:25)."
  - "Spoken math is ASR text. Fixes: 'quarter frequency' = corner frequency; '03/2002 h' = 302/302H; 'three dot 08:02' = EER 3.802; '(five?) omega' = φ(ω); 'DL over r' = jωL/R (?)."
  - "Student questions are off-mic and partly garbled (0:15:52, 0:28:25). There are no audio dropouts: every gap of 12 s or more is a single long utterance."
  - "No board arithmetic or algebra error. There is one self-corrected board slip (0:47:04)."
---

# 2026-10-19: Transfer Functions, Filter Terms, RC Filters, Decibels, Bode Plot Intro

## Summary

- **Define and compute a voltage-gain transfer function.** $\tilde H(\omega)=\tilde V_{out}/\tilde V_{in}$, written as $M(\omega)e^{j\phi(\omega)}$ with $M=|\tilde H|$ and $\phi=\tan^{-1}(\mathrm{Im}/\mathrm{Re})$. The $\tan^{-1}$ must be taken **in the correct quadrant**, not restricted to $\pm\pi/2$. Also know the other three ratios: $\tilde H_I=\tilde I_{out}/\tilde I_{in}$, transfer impedance $\tilde H_Z=\tilde V_{out}/\tilde I_{in}$, and transfer admittance $\tilde H_Y=\tilde I_{out}/\tilde V_{in}$.
- **State the five filter quantities exactly as he defines them:**
  - gain factor $M_0$ is the maximum **non-resonant** passband gain;
  - corner (cutoff) frequency $\omega_c$ is where $M=M_0/\sqrt2$, which is the half-power point;
  - bandwidth $B$ is the width of the passband and is defined for low-pass and band-pass filters only;
  - roll-off rate $S_G$ is the rate at which $M$ falls outside the passband ($|S_G|$ large is ideal);
  - resonant frequency $\omega_0$ is where the **input impedance is purely real**.
- **Explain why $1/\sqrt2$:** half power is "the least arbitrary" criterion, and $P\propto V^2$, so $V$ falls to $1/\sqrt2$. In dB that is −3 dB.
- **Derive the RC filter both ways with voltage division.** Clear nested fractions by multiplying by $j\omega C/j\omega C$, then read off magnitude and phase:
  - Output across C (low-pass): $\tilde H_c=\frac{1}{1+j\omega RC}$, $M_c=\frac{1}{\sqrt{1+\omega^2R^2C^2}}$, $\phi_c=-\tan^{-1}\omega RC$.
  - Output across R (high-pass): $\tilde H_R=\frac{j\omega RC}{1+j\omega RC}$, $M_R=\frac{\omega RC}{\sqrt{1+\omega^2R^2C^2}}$, $\phi_R=\frac\pi2-\tan^{-1}\omega RC$.
  - Both have **$\omega_c=1/RC=1/\tau$**. The phase at $\omega_c$ is $-\pi/4$ (low-pass) and $+\pi/4$ (high-pass).
- **Sketch $M$ and $\phi$ with labelled limits.** Work out the $\omega\to0$ and $\omega\to\infty$ limits, then mark $1$, $1/\sqrt2$, $\omega_c$, $\pm\pi/4$ and the $\pm\pi/2$ or 0 asymptotes, with dotted guide lines.
- **Know the dB rules:** power uses $10\log_{10}$ and voltage or current uses **$20\log_{10}$** ("a factor of 20 in front, not a factor of 10"). A 10× power change is 10 dB, 100× is 20 dB, and 2× is about 3 dB. In this course "log" means $\log_{10}$.
- **Know what a Bode plot is in this course.** Magnitude is plotted log-log ($M$ in dB vs. $\log\omega$). Phase is plotted linear-log. **"Strictly", the Bode plot is the straight-line (linear) approximation version**, following Ulaby.
- **Use dB additivity.** $\tilde H=\tilde N(j\omega)/\tilde D(j\omega)$ (polynomials in $j\omega$), so $M[\mathrm{dB}]=20\log|\tilde N|-20\log|\tilde D|$. Factor contributions add (numerator) or subtract (denominator). The first factor: $(1+j\omega/\omega_z)^N$ gives $20N\log|1+j\omega/\omega_z|$ and phase $N\tan^{-1}(\omega/\omega_z)$.
- **Resonance example (series R–C with the output across L):** $\tilde H(\omega_0)=\tilde Z_L/R$ and $M(\omega_0)=\omega_0L/R$, which grows without bound as $R\to0$.

> [!warning] Scope
> **This lecture does not give the straight-line Bode rules (slopes, corner breakpoints, phase ramps) for any factor.** He stopped after writing the magnitude and phase of $(1+j\omega/\omega_z)^N$ and deferred the sketches to Wed 10/21. All plots drawn today are on **linear** axes. The factor table under "Added context" below is textbook material and must be checked against the 10/21 lecture.

---

## Content

### 0. Announcements [0:00:03–0:01:16]
- PS6 is due Wed 10/21, 9:00 AM Central, on Canvas.
- **PS7 is posted Wed 10/21 and due Mon 11/02. It covers "transfer functions, Bode plots, and filter circuits."**
- Office hours are Mon 10/19, 10:30–11:55 AM and 3:00–4:30 PM, both in EER 3.802. There are none Wed 10/21 because of travel. Class still meets Wednesday: "pick up with this on Wednesday" [1:15:23].

### 1. Framing [0:01:21–0:02:43]
Filter circuits "exhibit some engineered and useful response as a function of frequency": some frequencies pass "with very little attenuation", others "are strongly attenuated." He gives two ways to quantify this: algebraically (transfer functions, first) and graphically (Bode plots, later). Board title: **"Transfer Functions. Reading: Ulaby et al, Sec. 9-1."**

### 2. Transfer function: definition and the four types [0:02:46–0:07:41]
**Figure (f_0008):** a box labelled "linear circuit". The input port is on the left: $\tilde I_{in}$ flows into the + terminal, and $\tilde V_{in}$ is + on top. The output port is on the right: $\tilde I_{out}$ flows out of the + terminal, and $\tilde V_{out}$ is + on top.

Board: **"transfer function = ratio of output to input."** With two inputs and two outputs there are four ratios (f_0014, f_0018):

| Name (board) | Definition |
|---|---|
| voltage-gain transfer function **(most common)** | $\tilde H(\omega)=\tilde V_{out}(\omega)/\tilde V_{in}(\omega)$ |
| current-gain transfer function | $\tilde H_I(\omega)=\tilde I_{out}(\omega)/\tilde I_{in}(\omega)$ |
| transfer impedance | $\tilde H_Z(\omega)=\tilde V_{out}(\omega)/\tilde I_{in}(\omega)$ |
| transfer admittance | $\tilde H_Y(\omega)=\tilde I_{out}(\omega)/\tilde V_{in}(\omega)$ |

The impedance and admittance names follow from the units: V/I has units of impedance, and "the usual symbol for admittance is Y" [0:07:07]. "For our purposes, we will look primarily at the voltage gain transfer function." The under-tilde on $\tilde H$ is "to remind us that this is, in general, going to be a complex quantity" [0:04:49].

### 3. Magnitude–phase form [0:07:42–0:10:18]
Board (f_0021): "We will consider primarily the voltage gain, $\tilde H(\omega)$. Then"
$$\tilde H(\omega)=M(\omega)e^{j\phi(\omega)},\qquad M(\omega)=|\tilde H(\omega)|,\qquad \phi(\omega)=\tan^{-1}\!\left(\frac{\mathrm{Im}(\tilde H(\omega))}{\mathrm{Re}(\tilde H(\omega))}\right)$$
- While working, "very often you're working with rectangular expressions." For the final result, magnitude and phase "more directly reflect the kind of functionality that we want to get from a filter circuit" [0:08:26–0:08:58].
- **Phase quadrant** [0:09:52]: the inverse tangent "has the actual correct phase of the transfer function... rather than being restricted to being between minus pi over two and pi over two." He said "we'll talk about that nuance in more detail" later.

> [!warning] Board vs speech
> The board formula, read literally, is the principal-value arctangent. He said aloud that it means the full-quadrant angle. Follow the speech: a negative real part needs ±π added.

### 4. Generic low-pass response and filter terminology [0:10:18–0:22:36]
**Figure (f_0026 → f_0097 → f_0104), "low pass".** Both axes are linear: vertical $M(\omega)$, horizontal $\omega$.
- The blue curve is flat at $M_0$, rolls off smoothly, and tails toward 0.
- A dashed horizontal line runs at $M_0/\sqrt2$ from the vertical axis to the curve, and a dashed vertical line drops from there to the $\omega$ axis at **$\omega_c$**.
- A double-headed arrow **$B$** spans from $\omega=0$ to $\omega_c$.
- An arrow points at the falling part of the curve near $\omega_c$, labelled **"slope" $=S_G$**.
- Added in **red** at 0:23–0:24: a narrow dash-dot spike rising well above $M_0$ just inside the passband edge, with a red dashed vertical line to the axis labelled **$\omega_0$**, just left of $\omega_c$.

Board definitions, verbatim (f_0042, f_0074, f_0113):
- **gain factor, $M_0$:** "maximum ("peak") non-resonant gain in filter's pass band." [0:12:11]
- **corner (or "cutoff") frequency, $\omega_c$:** "frequency at the edge(s) of the passband at which $M(\omega)=\frac{1}{\sqrt2}M_0$. Since power $\propto vi\sim v^2$, power at $\omega_c$ is half its peak value." [0:14:11]
  - "Edge(s)": a low-pass filter's lower passband edge is 0, so only the upper edge is specified. "If we have a bandpass filter, then we have a lower and upper" [0:15:30].
- **bandwidth, $B$:** "for low pass and bandpass filters, $B$ is the width, in frequency, of the passband." [0:19:09] For a high-pass filter "it doesn't really make sense... the upper limit is infinite, so the bandwidth will always be infinite" [0:19:40].
- **rolloff rate, $S_G$:** "rate at which $M(\omega)$ decreases with frequency outside the passband. For an "ideal" filter, $|S_G|$ is very large." [0:21:06] Ideally the response would "drop abruptly to zero", which is not achievable, so "as steep as we can practically make it" [0:22:03].

**Why $1/\sqrt2$** (student question, [0:15:52–0:18:12]): "There is some arbitrariness to it, but there is a well-founded justification." Half the peak power is "the least arbitrary criterion" ("if we said a third or three quarters... it wouldn't be as natural"). In a linear circuit $V\propto I$, so $P\propto V^2$ or $I^2$, and half power means $V$ or $I$ at $1/\sqrt2$. "That's why it's defined... with one over root two, since the transfer functions are for voltage or current, not for power."

> [!check] Verified
> $(1/\sqrt2)^2=0.5$, and $20\log_{10}(1/\sqrt2)=-3.0103$ dB (python).

### 5. Non-resonant gain and the resonant frequency [0:22:36–0:30:05]
**Why "non-resonant"** [0:22:46–0:24:49]. A second-order filter with an L and a C can show "a localized peak" near the passband edge, at the frequency where "the impedances of the inductor and the capacitor cancel each other out." The response there can be "very large." Because it occupies a narrow range, it is **not** $M_0$: "It's really this value [the flat passband level] that we care about, not this localized peak." Other applications do care about the peak shape.

**Board definition (f_0126):** "**resonant frequency, $\omega_0$:** Frequency at which the input impedance is purely real; often corresponds to an extremum of $\tilde H(\omega)$." [0:25:02]

**Example circuit (f_0161/f_0184).** The input port $\tilde V_{in}$ is on the left. **$R$ then $C$ run in series along the top wire** to a node. **$L$ goes from that node to the bottom (common) wire.** The output $\tilde V_{out}$ is taken across $L$ on the right.
$$\tilde H(\omega)=\frac{\tilde Z_L}{R+\tilde Z_C+\tilde Z_L}\quad\text{(voltage division)}$$
At $\omega_0$, $\tilde Z_C+\tilde Z_L=0$, so
$$\tilde H(\omega_0)=\frac{\tilde Z_L}{R},\qquad M(\omega_0)=\left|\frac{\tilde Z_L}{R}\right|=\frac{\omega_0L}{R}$$
"If you imagine that R, the resistance, is very small, the transfer function at that frequency can be very large... if R goes to zero, the transfer function will go to infinity. But that will only happen if you're right around the resonant frequency." [0:27:33–0:27:58]


> [!check] Verified (sympy/numpy)
> $\mathrm{Im}\,\tilde Z_{in}=0\Rightarrow\omega_0=1/\sqrt{LC}$, and $\tilde H(\omega_0)=j\sqrt{L/C}/R$, so $M(\omega_0)=\sqrt{L/C}/R=\omega_0L/R$.

> [!note] Added context (not from the lecture)
> "Often corresponds to an extremum" is approximate. For this L-output circuit with $L=C=1$ and $R=0.1$ ($Q=10$), $\max|H|=10.013$ at $\omega=1.0025\,\omega_0$, while $|H(\omega_0)|=10$. The peak sits slightly above $\omega_0$ and approaches it as $Q$ grows. On an exam, define $\omega_0$ by $\mathrm{Im}\,Z_{in}=0$, as he does, not by the peak of $|H|$.

### 6. Worked example: RC filter circuit [0:30:11–0:54:49]
**Circuit (f_0185, f_0190).** Board title: "**Example: RC filter circuit**".
- $\tilde V_s$ (+ on top) is on the left edge.
- The top wire runs to a node. **$C$** runs down from that node to a middle node, then **$R$** runs down from the middle node to the bottom wire, which returns to the source.
- Output terminals (open circles) sit at the top, middle and bottom nodes.
- $\tilde V_c$ is across C (+ at top) and $\tilde V_R$ is across R (+ at the middle node).
- Impedances: $\tilde Z_C=\frac1{j\omega C}$, $\tilde Z_R=R$.

"It's not really interesting to take the output terminals to be across both of these things together because that voltage is just always the input" [0:45:01].

#### 6a. Output across C [0:31:54–0:38:09]
Board (f_0190, f_0199, f_0209). The green factors are his "multiply by one" steps.
$$\tilde V_c=\frac{\tilde Z_C}{\tilde Z_R+\tilde Z_C}\tilde V_s=\frac{\frac1{j\omega C}}{R+\frac1{j\omega C}}\tilde V_s\left(\frac{j\omega C}{j\omega C}\right)=\frac{1}{1+j\omega RC}\tilde V_s$$
"We have fractions in the numerator, fractions in the denominator, so it's a little bit cumbersome... we'll multiply by $j\omega C$ over $j\omega C$" [0:33:24].

"**voltage-gain transfer function:**"
$$\tilde H_c(\omega)=\frac{\tilde V_c}{\tilde V_s}=\frac{1}{1+j\omega RC}\left(\frac{1-j\omega RC}{1-j\omega RC}\right)=\frac{1-j\omega RC}{1+\omega^2R^2C^2}\equiv M_c(\omega)e^{j\phi_c(\omega)}$$
The subscript $c$ marks the output taken across the capacitor. Multiplying by the conjugate gives "the strictly speaking rectangular form" [0:34:55].
$$\Rightarrow M_c(\omega)=|\tilde H_c(\omega)|=\frac{1}{\sqrt{1+\omega^2R^2C^2}},\qquad \phi_c(\omega)=-\tan^{-1}(\omega RC)$$
- **Magnitude:** "it's actually easiest to calculate it from this form [$1/(1+j\omega RC)$]... the magnitude of the fraction is just the magnitude of the numerator divided by the magnitude of the denominator" [0:36:16].
- **Phase, two routes:** (i) from the rationalized form, $\tan^{-1}(\mathrm{Im}/\mathrm{Re})$, pulling the minus sign of the imaginary part outside the arctangent [0:37:03]; (ii) from $1/(1+j\omega RC)$, "the phase of the transfer function itself is just the negative of the phase of the denominator" [0:37:31].

#### 6b. Low-pass sketches [0:38:18–0:40:04]
**Figure (f_0211 → f_0331), linear axes.**
- **$M_c(\omega)$:** vertical ticks 1, $1/\sqrt2$ and 0; horizontal axis $\omega$. The curve starts flat at 1 and passes through $(\omega_c,1/\sqrt2)$, marked by dotted guide lines to both axes. It then decays toward 0.
- **$\phi_c(\omega)$:** the $\omega$ axis is drawn at the top ($\phi=0$). The curve starts at 0 and falls monotonically. A dotted line from the $-\pi/4$ tick meets the curve at $\omega_c$, which is labelled above the axis. The curve approaches a dashed asymptote at $-\pi/2$.
- Limits as he states them: $\omega\to0$ gives $M\to1$ and $\phi\to\tan^{-1}0=0$. $\omega\to\infty$ gives $M\to0$, and "the inverse tangent of infinity, which in radians is pi over two... goes to minus pi over two" [0:39:23].

#### 6c. Corner frequency and phase at the corner [0:40:04–0:42:02]
Board (f_0219):
$$\frac{1}{\sqrt{1+\omega_c^2R^2C^2}}=\frac1{\sqrt2}\;\Rightarrow\;\omega_c=\frac{1}{RC},\qquad \phi_c(\omega_c)=-\tan^{-1}(1)=-\frac\pi4$$
"This is equal to one over root two... because the maximum value is one" [0:40:20]. "This requires that $\omega_c RC$ is equal to one" [0:40:53].

#### 6d. Notes and intuition, low-pass [0:42:02–0:44:41]
Board (f_0264/f_0331):
- "**Note: 1)** $\omega_c=1/\tau$ where $\tau=RC$ is the RC time constant of the circuit."
- "**2)** Output signal $\tilde V_c(\omega)$ acts as a **low-pass filter**."

His two explanations (spoken):
- **Impedance:** "at low frequencies... the impedance of the capacitor is high. And so we should expect to have a large value of the voltage across the capacitor" [0:43:05].
- **Time constant:** "the time scale for the voltage of the capacitor to respond is basically R times C." At frequencies below $1/RC$ "the voltage across the capacitor is able to respond in time... if the voltage is changing very rapidly, then there's no time for the capacitor to respond... and so $V_C$ will be low" [0:43:24–0:44:10].

#### 6e. Output across R [0:44:48–0:49:31]
Board (f_0350, f_0353, f_0359, f_0366):
$$\tilde V_R=\frac{\tilde Z_R}{\tilde Z_R+\tilde Z_C}\tilde V_s=\frac{R}{R+\frac1{j\omega C}}\tilde V_s\left(\frac{j\omega C}{j\omega C}\right)=\frac{j\omega RC}{1+j\omega RC}\tilde V_s$$

> [!warning] Self-corrected board slip [0:47:04]
> He first wrote "$\equiv M_R(\omega)e^{j\phi_R(\omega)}$" right after the $\tilde V_R$ expression, which still contains the factor $\tilde V_s$. He crossed it out ("Or, actually, this is not quite there yet") and rewrote it under $\tilde H_R=\tilde V_R/\tilde V_s$. Lesson: divide by the input before you call anything $Me^{j\phi}$.

$$\tilde H_R(\omega)=\frac{\tilde V_R}{\tilde V_s}=\frac{j\omega RC}{1+j\omega RC}\equiv M_R(\omega)e^{j\phi_R(\omega)}$$
$$\Rightarrow M_R(\omega)=\frac{\omega RC}{\sqrt{1+\omega^2R^2C^2}},\qquad \phi_R(\omega)=\frac\pi2-\tan^{-1}(\omega RC)$$
- Magnitude is |numerator| / |denominator|. The numerator's magnitude is $\omega RC$ [0:48:24].
- Phase is the phase of the numerator minus the phase of the denominator. "So the phase of the numerator is what, in radians? Right. Pi over two" [0:49:04].

> [!warning] Speech slip [0:48:52]
> He said "the magnitude of the numerator minus the magnitude of the..." and corrected himself aloud: "Or sorry. The phase of the numerator minus the phase of the denominator." The board is correct.

#### 6f. High-pass sketches, corner and notes [0:49:34–0:54:42]
**Figure (f_0369 → f_0379), linear axes.**
- **$M_R(\omega)$:** vertical ticks 1 (dashed horizontal asymptote) and $1/\sqrt2$. The curve starts **at the origin** ($M_R\to0$ as $\omega\to0$), rises concave-down through $(\omega_c,1/\sqrt2)$ with dotted guides, and approaches the dashed line at 1.
- **$\phi_R(\omega)$:** vertical ticks $\pi/2$ (dashed asymptote), $\pi/4$ and 0. The curve starts at $\pi/2$ at $\omega=0$, passes through $(\omega_c,\pi/4)$ with dotted guides, and decays to 0.
- Limits: $\omega\to0$ gives $\phi=\pi/2-0=\pi/2$. $\omega\to\infty$ gives $\phi=\pi/2-\pi/2=0$ [0:50:37].

Board:
$$\frac{\omega_cRC}{\sqrt{1+\omega_c^2R^2C^2}}=\frac1{\sqrt2}\;\Rightarrow\;\omega_c=\frac1{RC},\qquad\phi_R(\omega_c)=\frac\pi2-\tan^{-1}(1)=\frac\pi4$$
"If $\omega_c$ is equal to one over RC, we'll have one in the numerator... and the square root of two in the denominator" [0:51:50].
- "**Note: 1)** Again $\omega_c=1/\tau$ with $\tau=RC$."
- "**2)** Output signal $\tilde V_R(\omega)$ acts as a **high-pass filter**." The reason: "at high frequencies, the impedance of the capacitor goes to zero... so all the voltage drop will be across the resistor" [0:53:58].

> [!check] Verified (sympy + numpy)
> $Z_C/(R+Z_C)=1/(1+j\omega RC)$ and $R/(R+Z_C)=j\omega RC/(1+j\omega RC)$ hold exactly. Both $\omega_c$ equations give $1/RC$.
>
> | $\omega RC$ | $M_c$ | $\phi_c$ | $M_R$ | $\phi_R$ |
> |---|---|---|---|---|
> | 0.1 | 0.9950 | −5.71° | 0.0995 | 84.29° |
> | 1 | 0.7071 | −45.00° | 0.7071 | 45.00° |
> | 10 | 0.0995 | −84.29° | 0.9950 | 5.71° |
>
> **No board error in the example.**

### 7. Bode plots: definition [0:54:43–0:57:36]
Board (f_0408): "**Bode Plots. Reading: Ulaby et al, Sec. 9-3.**"

Motivation: plotting magnitude and phase is useful, and there is "a very systematic way of doing this that, in particular, allows one to combine many different components." From the plots for "subparts of the circuit, we can easily construct what happens for the circuit as a whole" [0:55:03].

Board (f_0409): "**Bode plots are log-log plots of $M(\omega)$ vs. $\omega$, and linear-log plots of $\phi(\omega)$ vs. $\omega$.**" "Both axes on log scales" for magnitude. For phase, "the vertical axis is on a linear scale... the frequency, the horizontal axis, is on a log scale" [0:56:51–0:57:29].

**The course definition (spoken, [0:56:11–0:56:40]):** "The way the Bode plot terminology is used in Ulaby, and therefore the way that we will use it here, a version of those plots where we make kind of **linear approximations** to what the plots look like over specific ranges of frequency will be what we **strictly refer to as the Bode plot**. And by making those linear approximations, it makes it very easy to combine kind of the Bode plots for different subparts of the circuit."

Board (f_0419): "Very useful for visualizing and thinking about circuit frequency response."

### 8. The decibel scale [0:57:36–1:07:07]
Board (f_0419, f_0430, f_0438), heading "**The decibel (dB) scale:**":
- "Recall that decibels (dB) quantify the **ratio** of power $P$ to a reference value $P_0$. Often $P_0=1$ W or 1 mW. Define power gain $G$:"
$$G=P/P_0\;\Rightarrow\;\boxed{G\,[\mathrm{dB}]=10\log_{10}\frac{P}{P_0}}$$
- "Each 10X change in $P$ changes $G$[dB] by 10 dB." Spoken: "a change in the power by a factor of a 100 is 20 decibels" [1:02:04].
- "Since $\log_{10}2\approx0.30$, a 2X change in $P$ changes $G$[dB] by ~3 dB." Spoken: "doubling or halving" [1:03:47].
- 1 mW is the dBm reference [1:00:34].
- Spoken link to filters [1:04:05]: "if we have a, say, lowpass filter, then at the cutoff frequency, the transfer function... it's reduced by three dB compared to its maximum value."

Board (f_0447, f_0460): "Also, since power $\propto\tilde V\tilde I^*$ and, for linear circuits, $\tilde V\propto\tilde I$, we also have"
$$G\,[\mathrm{dB}]=10\log_{10}\!\left(\frac{P}{P_0}\right)=10\log_{10}\!\left(\left|\frac{\tilde V^2}{\tilde V_0^2}\right|\right)=20\log_{10}\!\left(\frac{|\tilde V|}{|\tilde V_0|}\right)=20\log_{10}\!\left(\frac{|\tilde I|}{|\tilde I_0|}\right)$$
"If we're talking about ratios of voltage or current, then it's a factor of 20 in front, not a factor of 10, and that's because the power goes as the voltage squared" [1:06:51].

> [!check] Verified
> $\log_{10}2=0.30103$, $10\log_{10}2=3.0103$ dB, $10\log_{10}100=20$ dB, and $20\log_{10}2=6.0206$ dB (python).

> [!note] Added context (not from the lecture)
> $10\log(P/P_0)=20\log(|V|/|V_0|)$ holds only if $V$ and $V_0$ appear across the same (resistive) impedance. He did not state this. For a transfer function, $M[\mathrm{dB}]\equiv20\log_{10}|\tilde H|$ is simply the definition, whatever the impedances.

### 9. General form of $\tilde H(\omega)$ and dB additivity [1:07:09–1:12:59]
Board (f_0466, f_0475):
$$\text{"In general, }\tilde H(\omega)\text{ will be of the form" }\quad\tilde H(\omega)=\frac{\tilde N(\omega)}{\tilde D(\omega)}\equiv M(\omega)e^{j\phi(\omega)},$$
"where $\tilde N(\omega)$, $\tilde D(\omega)$ are polynomial functions of $(j\omega)$."
- He writes the numerator as a capital N "with serifs... to emphasize this as a capital letter," which distinguishes it from the exponent $N$ used next [1:08:14].
- **Why polynomials in $j\omega$** [1:08:45–1:10:33]: element relations go through impedances, and these "always have $j$ and $\omega$ together", as in $1/j\omega C$ and $j\omega L$. Sums of such terms are linear in $1/j\omega$ and $j\omega$. Solving for an output means dividing by a polynomial, and that gives a rational function. "We'll see later when we talk about Laplace transforms why having $j\omega$ turns out to be a natural combination."

$$\Rightarrow M(\omega)=\left|\frac{\tilde N(\omega)}{\tilde D(\omega)}\right|,\qquad M(\omega)[\mathrm{dB}]=20\log_{10}|\tilde N(\omega)|-20\log_{10}|\tilde D(\omega)|$$
"If we can figure out what are the typical factors that will go into the numerator or into the denominator... then, basically, by adding or subtracting them, we can get the magnitude on the dB scale of the transfer function as a whole... that will be a large part of what makes the Bode plots particularly useful" [1:11:51–1:12:41].

### 10. First standard factor (preview) [1:13:00–1:15:38]
Board (f_0480): "Suppose $\tilde N(\omega)=(1+j\omega/\omega_z)^N$, $\tilde D(\omega)=1$."
$$M(\omega)[\mathrm{dB}]=20N\log|1+j\omega/\omega_z|$$
$$\phi(\omega)=N\tan^{-1}(\omega/\omega_z)\quad\text{(spoken at 1:14:25; frames end at 1:14:24)}$$
- "We're always gonna be working with log base tens here. So when I write log... we're gonna always assume that that is log base 10 even though we're not gonna write the 10 subscript explicitly anymore" [1:14:01].
- Next time: "sketch out what these two functions look like on the appropriate log-log or linear-log scales" [1:14:35].
- **Thought question for Wednesday** [1:14:48–1:15:13]: "To make it simpler, let's assume N is one. How would you get a combination like this in some expression for, say, a voltage or a current in a circuit?"

> [!check] Verified (N = 1)
> At $\omega=\omega_z$: $20\log|1+j|=3.010$ dB and $\phi=45^\circ$. At $10\omega_z$: 20.04 dB and $84.29^\circ$. At $100\omega_z$: 40.00 dB and $89.43^\circ$.

> [!note] Added context: the standard factor list and straight-line rules (Ulaby §9-3, not yet given in lecture)
> The textbook's straight-line rules, listed so the tutor can check them against his 10/21 lecture. $\omega_c$ below is the factor's own corner ($\omega_z$ on his board for a numerator factor).
>
> | Factor | Magnitude asymptote (dB) | Phase straight line |
> |---|---|---|
> | $K$ | flat at $20\log\lvert K\rvert$ | $0$ (or $\pm180^\circ$ if $K<0$) |
> | $(j\omega)^{\pm N}$ | line of slope $\pm20N$ dB/decade through 0 dB at $\omega=1$ rad/s | constant $\pm90N^\circ$ |
> | $(1+j\omega/\omega_c)^{\pm N}$ | 0 dB below $\omega_c$, then $\pm20N$ dB/decade above | 0 below $0.1\omega_c$, a ramp of $\pm45N^\circ$/decade to $\pm90N^\circ$ at $10\omega_c$ |
> | $[1+j2\xi\omega/\omega_c-(\omega/\omega_c)^2]^{\pm N}$ | 0 dB below $\omega_c$, then $\pm40N$ dB/decade above | 0 below $0.1\omega_c$, a ramp of $\pm90N^\circ$/decade to $\pm180N^\circ$ at $10\omega_c$ |
>
> Largest errors of the straight lines for a simple zero or pole: 3.01 dB at the corner and 5.71° at $0.1\omega_c$ and $10\omega_c$ (python). **Do not treat this table as his convention until the 10/21 lecture confirms it,** especially whether he labels phase in degrees or radians. Today he used radians throughout.

---

## Ed Yu's conventions & notation

| Item | His convention (this lecture) |
|---|---|
| Transfer function symbol | $\tilde H(\omega)$ with the **under-tilde** (complex). The argument is $\omega$ (rad/s), not $s$ or $f$. A subscript names the output element ($\tilde H_c$, $\tilde H_R$) or the ratio type ($\tilde H_I$, $\tilde H_Z$, $\tilde H_Y$). |
| Default ratio | **Voltage gain** $\tilde V_{out}/\tilde V_{in}$ unless stated otherwise. |
| Polar form | $\tilde H=M(\omega)e^{j\phi(\omega)}$, written with "$\equiv$" at the end of the algebra. $M$ and $\phi$ take the same subscript as $\tilde H$. |
| Phase | $\phi=\tan^{-1}(\mathrm{Im}/\mathrm{Re})$ **in the correct quadrant**. The phase of a fraction is the phase of the numerator minus the phase of the denominator. **Radians in this lecture** ($\pm\pi/4$, $\pm\pi/2$). |
| Algebra moves | "Multiply by one" in **green**: $j\omega C/j\omega C$ to clear nested fractions, and the conjugate $(1-j\omega RC)/(1-j\omega RC)$ to rationalize. Get the magnitude from the unrationalized form as $\lvert N\rvert/\lvert D\rvert$. |
| Symbols | $M_0$ gain factor; $\omega_c$ corner/cutoff; $B$ bandwidth; $S_G$ roll-off rate; $\omega_0$ resonant (drawn in red); $\tau=RC$; $\omega_z$ corner of a numerator factor; $\tilde N,\tilde D$ numerator and denominator (serifed N, distinct from the exponent $N$). |
| dB notation | $G\,[\mathrm{dB}]=10\log_{10}(P/P_0)$, boxed. $M(\omega)[\mathrm{dB}]=20\log|\cdot|$, with the unit in square brackets after the quantity. **"log" means $\log_{10}$** from 1:14 onward. |
| Plot axes | Bode magnitude: **log-log** ($M$ in dB vs. $\log\omega$). Bode phase: **linear-log**. "Bode plot" **strictly = the straight-line approximation** (Ulaby's usage). Today's sketches were on linear axes and are explicitly *not* Bode plots. |
| Plot labelling | Label the axes ($M_c(\omega)$, $\phi_c(\omega)$, $\omega$). Put tick values on the vertical axis (1, $1/\sqrt2$, 0; $-\pi/4$, $-\pi/2$; $\pi/2$, $\pi/4$, 0) and **$\omega_c$ on the horizontal axis**. Draw **dotted guide lines** from both axes to the curve at $\omega_c$, and **dashed lines for asymptotes**. For a negative phase the $\omega$ axis is drawn at the top ($\phi=0$) with the curve below it. |
| Definitions written as | Underlined term, colon, one-sentence definition, as on the board ("gain factor, $M_0$: ..."). |
| Readings | Ulaby et al. §9-1 (transfer functions), §9-3 (Bode plots). |

### His Bode-plot procedure as established in this lecture
1. Find $\tilde H(\omega)=\tilde V_{out}/\tilde V_{in}$ by impedances and voltage division. Clear nested fractions by multiplying by one.
2. Write $\tilde H$ as $\tilde N(\omega)/\tilde D(\omega)$, polynomials in $j\omega$, and break them into standard factors. Only $(1+j\omega/\omega_z)^N$ has been introduced so far.
3. Magnitude in dB: $M[\mathrm{dB}]=20\log|\tilde N|-20\log|\tilde D|$, so each factor's dB curve adds (numerator) or subtracts (denominator). Use 20, not 10, for voltage ratios.
4. Phase: add the phases of the numerator factors and subtract those of the denominator factors, in the correct quadrant. For example, $j\omega$ contributes $+\pi/2$ and $(1+j\omega/\omega_z)^N$ contributes $N\tan^{-1}(\omega/\omega_z)$.
5. Plot magnitude as dB vs. $\log\omega$ and phase linearly vs. $\log\omega$.
6. Replace each factor's curve by straight-line approximations over frequency ranges, which is what he "strictly" calls the Bode plot, and sum them. **The specific slopes and breakpoints were deferred to 10/21.**
7. Label key values on both axes, as in his sketches: $M_0$ and the corner ($M_0/\sqrt2$, i.e. −3 dB) on the vertical axis, $\omega_c$ on the horizontal axis, the phase at $\omega_c$ ($\pm\pi/4$ for first order), and the asymptotes (0, $\pm\pi/2$).
8. Sanity-check against the exact function: at a first-order corner the true curve is 3 dB below the asymptote and the phase is ±45°.

---

## Intuition & explanations he gives

- **Why magnitude and phase rather than rectangular form:** "The magnitude and the phase more directly reflect the kind of functionality that we want to get from a filter circuit." [0:08:49]
- **Why $1/\sqrt2$:** "In some sense, the least arbitrary criterion for that is to say power has dropped to half its peak value... if we said a third or three quarters... it wouldn't be as natural." Then $P\propto V^2$ gives $V/\sqrt2$, "since the transfer functions are for voltage or current, not for power." [0:17:06–0:18:12]
- **Why bandwidth is not defined for a high-pass filter:** "the upper limit is infinite, so the bandwidth will always be infinite." [0:19:40]
- **Why $M_0$ excludes the resonant peak:** the peak "occurs only in a narrow range of frequencies," so "for filter circuits, usually, we're concerned with what is the more typical response across the passband." [0:24:16–0:24:43]
- **Where resonant peaks come from:** "a frequency at which the impedances of the inductor and the capacitor cancel each other out"; then $H(\omega_0)=Z_L/R$, which blows up as $R\to0$. [0:23:47, 0:27:26–0:27:50]
- **Why the RC circuit across C is low-pass (impedance):** at low $\omega$, $|Z_C|$ is high, so most of the voltage sits across C. [0:43:05]
- **Why it is low-pass (time constant):** "The time scale for the voltage of the capacitor to respond is basically RC." Slow inputs let C follow; fast inputs leave "no time for the capacitor to respond." This is why $\omega_c=1/\tau$. [0:43:24–0:44:10]
- **Why across R is high-pass:** "at high frequencies, the impedance of the capacitor goes to zero... so all the voltage drop will be across the resistor." [0:53:58]
- **Why log scales and dB:** dB is "the natural way of quantifying... quantities in terms of logs, which means that you're thinking really in terms of multiples by which quantities change rather than... additive changes." [0:58:31–0:59:01]
- **Why Bode plots combine easily:** "Since you're plotting things on a log scale for the magnitude, you can add or subtract different contributions very easily, corresponding to different factors." [1:12:29–1:12:44]
- **Why transfer functions are rational in $j\omega$:** impedances "always have $j$ and $\omega$ together"; solving for an output divides by a polynomial. [1:09:00–1:10:33]

---

## Emphasis & exam intel

1. **Bode plot = straight-line version** [0:56:11]: "the way the Bode plot terminology is used in Ulaby, and therefore the way that we will use it here, a version of those plots where we make kind of linear approximations... will be what we strictly refer to as the Bode plot." This is consistent with past exams asking for Bode plots "using linear approximations as done in class."
2. **20 vs 10** [1:06:51]: "If we're talking about ratios of voltage or current, then it's a factor of 20 in front, not a factor of 10."
3. **−3 dB at cutoff** [1:04:13]: "at the cutoff frequency, the transfer function... it's reduced by three dB compared to its maximum value."
4. **dB additivity is the point of Bode plots** [1:12:32]: "you can add or subtract different contributions very easily, corresponding to different factors."
5. **Correct-quadrant phase** [0:09:52]: the arctangent must give "the actual correct phase... rather than being restricted to being between minus pi over two and pi over two."
6. **$M_0$ is non-resonant** [0:24:22]: "It's really this value that we care about, not this localized peak."
7. **Resonance definition** (board, [0:25:02]): "Frequency at which the input impedance is purely real; often corresponds to an extremum of $\tilde H(\omega)$." Note that he defines it by the input impedance, not by the peak of $H$.
8. **log = log10** [1:14:01]: "When I write log... we're gonna always assume that that is log base 10."
9. **PS7 scope** [0:00:30]: "transfer functions, Bode plots, and filter circuits, basically the topics that we're discussing right now."
10. **Thought question** [1:14:55]: how would $(1+j\omega/\omega_z)$ arise in a circuit expression? This is a likely P1-style "explain" prompt. (Answer, mine: e.g. an impedance $R+j\omega L=R(1+j\omega L/R)$, so $\omega_z=R/L$, or an admittance $1/R+j\omega C$ with $\omega_z=1/RC$.)

---

## Student questions

| t | Question (reconstructed) | His answer |
|---|---|---|
| 0:15:52 | Is there a physical reason for $1/\sqrt2$? Does it relate to RMS, or is it just mathematically convenient? | "There is some arbitrariness... but a well-founded justification." He asked the class; a student said "power". Half power is the least arbitrary criterion, and $P\propto V^2$ gives $1/\sqrt2$ in voltage or current. |
| 0:28:25 | If $H(\omega_0)=j\omega L/R$ (ASR "DL over r" (?)), it isn't purely real, so how is $\omega_0$ "where it's real"? | Resonance is defined by the **input impedance** seen from the input terminals being real: $Z_{in}=R+1/j\omega C+j\omega L$. $H$ itself need not be real; its magnitude at $\omega_0$ is $\omega_0L/R$. |
| 1:10:41 | (Possible Zoom question; nothing audible.) | "I thought I heard something... if there are questions on Zoom... type in the chat or you can just speak up." |

---

## Exam relevance

The TA hint "Bode plots in your sleep" and the past-exam demand for linear-approximation Bode plots with key values on both axes make this lecture the foundation. It does **not** contain the slope rules (see the Scope warning). Semiconductor physics does not appear.

- **P1 (four conceptual short answers on filter concepts), high.** Ready-made answers:
  - why the cutoff is at $M_0/\sqrt2$ (half power, −3 dB);
  - why bandwidth is undefined for a high-pass filter;
  - why $M_0$ is the "non-resonant" gain;
  - the resonant-frequency definition ($Z_{in}$ purely real) versus the peak of $|H|$;
  - why the RC output across C is low-pass and across R is high-pass (impedance limits plus the time-constant argument);
  - why voltage dB uses 20 rather than 10;
  - why Bode plots use log axes (factor contributions add);
  - why $\tilde H$ is a rational function of $j\omega$.
- **P2 (passive filter design or analysis), high.** First-order RC: $\omega_c=1/RC$, so a design specifies the $RC$ product. You choose the output node (C gives low-pass, R gives high-pass). Expect "design for $f_c$" ($\omega_c=2\pi f_c$) and "find the phase at $\omega_c$" ($\mp45^\circ$).
- **P3 (filter transfer function, cutoff and Bode plots), highest.** The full pipeline: voltage division, multiply by one, $\tilde H$, $M$ and $\phi$, $\omega\to0,\infty$ limits, $\omega_c$ from $M=M_0/\sqrt2$, phase at $\omega_c$, then Bode on log axes with straight-line approximations and labelled values.
- **P4 (op-amp or RLC filter: factored standard form, type, Bode, design ratio), medium.** You need $\tilde H=\tilde N/\tilde D$ in $j\omega$ and the first standard factor $(1+j\omega/\omega_z)^N$. The resonance example (series R–C with the output across L, $M(\omega_0)=\omega_0L/R$) previews the RLC filter. Op-amp filters are not covered here.

> [!note] Graded-work check
> No PS8 problem (9.26, 9.38, 9.39, 9.42, m9.2, 12.2a–c) and no Lab 5 item (active inverting LP, Sallen-Key) was worked in this lecture. The RC low-pass/high-pass derivation is the generic textbook example and is safe for tutoring. The series-RLC resonance aside is conceptual only; no band-pass parameters were computed.

**Likely question variants:**
1. A given RC (or RL) divider: find $\tilde H$, $M$, $\phi$, $\omega_c$ and the phase at $\omega_c$, name the filter type, and sketch it.
2. Convert a gain to dB or back: a voltage ratio of 2 is 6.02 dB, a power ratio of 2 is 3.01 dB, and a voltage ratio of 0.1 is −20 dB.
3. Explain resonance in a series RLC; find $\omega_0$ and $M(\omega_0)$; explain why $M_0$ excludes the peak.
4. Write a given $\tilde H$ as $\tilde N/\tilde D$ in standard factors and state the dB contribution and phase of each factor.

---

## Common mistakes / traps

- **Principal-value arctangent.** With a negative real part, $\tan^{-1}(\mathrm{Im}/\mathrm{Re})$ is off by $\pi$. He warned about this at 0:09:52.
- **Writing $Me^{j\phi}$ before dividing by $\tilde V_{in}$.** He made this slip himself at 0:47:04.
- **Forgetting the $+\pi/2$ of a $j\omega$ numerator.** For the high-pass, $\phi_R=\pi/2-\tan^{-1}\omega RC$, not $-\tan^{-1}\omega RC$.
- **Using $10\log$ for a voltage or current ratio.** $|H|=1/\sqrt2$ is −3 dB with $20\log$; $10\log$ gives −1.5 dB, which is wrong.
- **Defining bandwidth for a high-pass filter.** It is infinite or undefined.
- **Taking a resonant spike as $M_0$.** $M_0$ is the non-resonant passband level.
- **Defining $\omega_0$ as the peak of $|H|$.** His definition is $\mathrm{Im}\,Z_{in}=0$. The peak can sit slightly away from it.
- **Calling a linear-axis sketch a Bode plot.** A Bode plot has a log $\omega$ axis, magnitude in dB, and straight-line segments.
- **Mixing degrees and radians.** Today's phases were in radians ($\pi/4$). If you switch to degrees, convert ($-\pi/4=-45^\circ$).
- **"log" means $\log_{10}$, not ln.**

---

## Self-check

1. For the RC circuit with the output across R, derive $\tilde H_R$, $M_R$, $\phi_R$, $\omega_c$ and $\phi_R(\omega_c)$. Name the filter type.
> [!question]- Answer
> By voltage division with $\times\, j\omega C/j\omega C$: $\tilde H_R=\dfrac{j\omega RC}{1+j\omega RC}$, $M_R=\dfrac{\omega RC}{\sqrt{1+\omega^2R^2C^2}}$, $\phi_R=\dfrac\pi2-\tan^{-1}(\omega RC)$. Setting $M_R=1/\sqrt2$ gives $\omega_c=1/RC$ and $\phi_R(\omega_c)=\pi/2-\pi/4=\pi/4$. It is a **high-pass** filter ($M_R:0\to1$). Verified with sympy.

2. $R=2$ kΩ and $C=50$ nF, output across C. Find $\omega_c$, $f_c$, and $M_c$ (absolute and dB) and $\phi_c$ at $\omega=10\,\omega_c$.
> [!question]- Answer
> $\omega_c=1/RC=1/(2\times10^3\cdot50\times10^{-9})=1.00\times10^4$ rad/s, so $f_c=\omega_c/2\pi=1.59$ kHz. At $\omega RC=10$: $M_c=1/\sqrt{101}=0.0995$, which is −20.0 dB, and $\phi_c=-\tan^{-1}10=-84.3^\circ$ $(-1.47$ rad$)$. Verified with numpy.

3. Why is the cutoff defined at $M_0/\sqrt2$, and what is that in dB? What dB change corresponds to a voltage ratio of 2, and to a power ratio of 2?
> [!question]- Answer
> At $M_0/\sqrt2$ the output power is half its peak, because $P\propto V^2$. He calls this the least arbitrary criterion. $20\log_{10}(1/\sqrt2)=-3.01$ dB. A voltage ratio of 2 is $20\log_{10}2=6.02$ dB; a power ratio of 2 is $10\log_{10}2=3.01$ dB.

4. In his resonance example (series $R$, then $C$, with the output across $L$), take $R=10\ \Omega$, $L=10$ mH, $C=1\ \mu$F. Find $\omega_0$, $\tilde Z_{in}(\omega_0)$ and $M(\omega_0)$. Is $\tilde H(\omega_0)$ real?
> [!question]- Answer
> $\omega_0=1/\sqrt{LC}=1/\sqrt{10^{-8}}=1.00\times10^4$ rad/s. $\tilde Z_{in}(\omega_0)=R=10\ \Omega$ (purely real; that is the definition). $\tilde H(\omega_0)=\tilde Z_L/R=j\omega_0L/R=j10$, so $M(\omega_0)=10.0$. $\tilde H$ is **not** real; it is purely imaginary (phase $+90^\circ$). Verified with numpy.

5. For $\tilde N(\omega)=(1+j\omega/\omega_z)$ ($N=1$), compute $M$[dB] and $\phi$ at $\omega=\omega_z$ and $\omega=10\,\omega_z$, and give one circuit expression that contains such a factor.
> [!question]- Answer
> At $\omega_z$: $20\log\sqrt2=3.01$ dB and $\phi=45^\circ$ ($\pi/4$). At $10\omega_z$: $20\log\sqrt{101}=20.04$ dB and $\phi=84.3^\circ$. An example is the impedance of R in series with L: $R+j\omega L=R(1+j\omega/\omega_z)$ with $\omega_z=R/L$. (His thought question at 1:14:55; the circuit example is mine.) Verified with numpy.
