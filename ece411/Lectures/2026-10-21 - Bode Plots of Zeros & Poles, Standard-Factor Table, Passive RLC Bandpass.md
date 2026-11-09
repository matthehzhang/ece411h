---
course: ECE 411H
date: 2026-10-21
instructor: Prof. Ed Yu
topic: Straight-line Bode magnitude and phase plots for a simple zero and a simple pole; definitions of zero and pole (with order); the table of standard factors (constant, zero/pole at origin, simple zero/pole, quadratic zero/pole) and their Bode plots; adding factor plots; passive vs active filters; series RLC bandpass (output across R) transfer function
reading: Ulaby/Maharbiz/Furse 3e §9-4, §9-5 (passive filters, named on the board). The Bode-plot reading was not restated this lecture.
source: Recordings/2026-10-21-passive-filters-and-bode-plots-cont (78.7-min transcript + 29 distinct tablet pages from 107 page-final frames; page-by-page descriptions in frames/pages_described.md)
tags: [ece411, lecture, transfer-function, bode-plot, poles-zeros, decibels, passive-filter, bandpass, rlc, exam2]
source_quality:
  - "Speech: Deepgram Nova-3, 78.7 min, 9015 words, mean confidence 0.97. 47 words < 0.55 and 12 utterances < 0.7, all filler words (lowest: [1:07:08] 'we', [0:51:54] 'what'). Spoken math is the ASR's guess. Every number here was re-derived with python/sympy."
  - "Frames: tablet ink at 1280 px. 29 distinct pages from 107 page-final / 330 scene-change frames. 81 of them are scroll or extension states of the same page."
  - "One blurry frame, f_0131 [0:37:16]. It is superseded by f_0134/f_0154, so no content is lost."
  - "Frames end at 1:17:16. The final conjugate-multiplied H(ω) [1:17:16–1:17:46] is speech-only."
  - "No audio gaps. The recording runs 0:00:00–1:18:43."
---

# 2026-10-21: Bode Plots of Zeros & Poles, the Standard-Factor Table, Passive RLC Bandpass

## Summary

- **Draw a Bode magnitude plot the way he does it.** Put $M(\omega)$ in dB on the vertical axis and $\omega$ on a log axis. For each factor, take the $\omega\to0$ limit below the corner and the $\omega\to\infty$ limit above it, so the plot is two straight lines meeting at the corner. A simple zero gives 0 dB, then $+20N$ dB/decade. A simple pole gives 0 dB, then $-20N$ dB/decade.
- **Draw a Bode phase plot the way he does it.** Hold the low-frequency value up to $0.1\,\omega_c$ and the high-frequency value from $10\,\omega_c$. Join them with a straight line on the log axis, which passes through the exact midpoint at $\omega_c$ ($\pm45°N$ for a simple factor). A step at $\omega_c$ is "a little too lousy of an approximation."
- **Know the 7-row factor table cold** (in the table below). Constant $K$: $20\log|K|$, and 0° or $\pm180°$. $(j\omega)^{\pm N}$: $\pm20N$ dB/decade through 0 dB at $\omega=1$, phase $\pm90°N$. $(1+j\omega/\omega_c)^{\pm N}$: $\pm20N$ dB/decade, phase $\pm90°N$. Quadratic $[1+j2\xi\omega/\omega_c+(j\omega/\omega_c)^2]^{\pm N}$: $\pm40N$ dB/decade, phase $\pm180°N$.
- **Add the factor plots to get the plot of $H(\omega)$.** Since $H=A_1A_2\cdots A_n$, $\log|H|=\sum\log|A_i|$. Slopes of the straight segments add, constants shift the level, and phases add because they sit in exponents.
- **Name a factor as a zero or a pole, with its order.** $\omega_z$ is a *zero of order $N$* because at $\omega=j\omega_z$ the numerator (and $H$) is 0. $\omega_p$ is a *pole of order $N$* because at $\omega=j\omega_p$ the denominator is 0 and $H\to\infty$.
- **Recognize which circuit produces which factor.**
  - A current into series $R$–$L$ gives $IR(1+j\omega L/R)$: a simple zero at $R/L$.
  - An RC voltage divider with the output across $C$ gives $1/(1+j\omega RC)$: a simple pole at $1/RC$.
  - $j\omega L$ gives a zero at the origin, and $1/j\omega C$ a pole at the origin.
  - Series RLC gives a quadratic factor.
- **Derive the transfer function of the series RLC bandpass with output across $R$.** Voltage division gives $H=\dfrac{R}{R+j\omega L+1/j\omega C}=\dfrac{j\omega RC}{1-\omega^2LC+j\omega RC}$: a zero at the origin (times a constant) and a quadratic pole. Explain the bandpass behaviour from the impedances. At low $\omega$, $Z_C$ is large. At high $\omega$, $Z_L$ is large. In between, $Z_L$ and $Z_C$ cancel and all of $V_s$ appears across $R$.
- **Passive vs active:** passive filters contain only R, L, C plus the input source. Active filters contain op amps, transistors or other gain devices.
- **"Bode plot" in this course means the straight-line approximation** (the Ulaby usage), not the exact computed curve.

---

## Content

### 0. Announcements [0:00:03–0:00:57]
- PS6 was due today (9:00 AM). **PS7 is released, due Mon 11/02/2026 at 9:00 AM, "on transfer functions, Bode plots, and filter circuits."**
- No office hours after class today because of travel. Monday's extra office hours replaced them.

### 1. Recap: transfer functions are rational in $j\omega$ [0:01:03–0:02:55]
Board "From last time:" (f_0008):
$$H(\omega)=\frac{N(\omega)}{D(\omega)}=M(\omega)e^{j\phi(\omega)},\qquad N,D\ \text{polynomial functions of }(j\omega)$$
$$\Rightarrow M(\omega)=\left|\frac{N(\omega)}{D(\omega)}\right|,\qquad M(\omega)[\mathrm{dB}]=20\log|N(\omega)|-20\log|D(\omega)|$$
- Why rational: impedances are $R$, $1/j\omega C$ and $j\omega L$. Combining them and dividing out common factors "will typically give you polynomials in frequency." [0:01:44–0:02:14]
- Taking the log turns the ratio into a **difference of logs**, which is "a hint as to why Bode plots... are particularly useful." [0:02:24–0:02:49]

### 2. Simple zero: setup and a circuit that produces it [0:02:56–0:09:04]
**Board** (f_0012/f_0031):
$$\text{Suppose } N(\omega)=\left(1+j\frac{\omega}{\omega_z}\right)^N,\ D(\omega)=1$$
$$M(\omega)[\mathrm{dB}]=20N\log\left|1+j\frac{\omega}{\omega_z}\right|,\qquad \phi(\omega)=N\tan^{-1}\frac{\omega}{\omega_z}$$

> [!warning] Board corrected live: the magnitude line was first written "$20N\log|+j\omega/\omega_z|$" with no 1. At 0:07:02 he says "sorry, this is a one in here", and the 1 is on the board from f_0031 (0:09:04).

**Circuit (f_0019/f_0020)** [0:03:49–0:05:15]. The left side is "..." (the rest of the circuit). A current $I$ (arrow pointing right) enters the top wire. Between the + and − output terminals hangs a vertical branch with $R$ on top and $L$ below, in series. $V_o$ is across the terminals, + on top.
$$V_o=I(R+j\omega L)=IR\left(1+j\omega\frac{L}{R}\right)$$
This is the simple-zero form with $N=1$, multiplied by the constant $R$ (and by $I$). Implied, not written: $\omega_z=R/L$ (sympy ✓).

**How to get $N>1$** (student question, 0:07:34). He drew in green a second $R$–$L$ branch hanging off the output terminals (f_0031). "To get the higher exponents, typically, you have to have something that has multiple stages... It's not exactly like this... where there's something in between." Filter orders come later. [0:07:45–0:08:52]

> [!note] Added context: two RL branches connected directly load each other, so $H$ is not simply the square. The "something in between" is a buffer (e.g. an op-amp follower), which makes the stage transfer functions multiply exactly. This becomes the active-filter story.

### 3. Simple zero: actual magnitude curve [0:05:51–0:11:44]
**Axes (f_0046, f_0078 left):** "magnitude:". The vertical axis is $M(\omega)$[dB], with ticks 0, **3N** (green), 10N, 20N. The horizontal axis is $\omega$ on a log scale, with ticks $0.1\omega_z$, $\omega_z$, $10\omega_z$. "The magnitude is on a log scale because it's in dB. The frequency... we also want to have on a log scale." [0:06:20–0:06:47]

Key points he computes:
- $\omega\to0$: $\log|1|=0$, so the curve starts at **0 dB**. (He says "the magnitude goes to zero", meaning 0 dB, i.e. $|H|=1$.) [0:09:26]
- $\omega=\omega_z$: $20N\log|1+j|=20N\log2^{1/2}=10N\log2\approx10N(0.3)\approx\mathbf{3N}$ **dB** (green dot). [0:09:43–0:10:36]
- $\omega\gg\omega_z$: the imaginary part dominates, so $M\approx20N\log|\omega/\omega_z|$, which grows without bound. [0:10:59–0:11:44]

The green curve starts at 0, rises slowly through $(\omega_z,3N)$, then curves upward. It is labelled "$\approx20N\log|\omega/\omega_z|$".

> [!check] Verified (python): $20\log_{10}\sqrt2=3.0103$ dB and $\log_{10}2=0.30103$. Board correct.

### 4. Simple zero: Bode magnitude plot [0:13:00–0:17:30]
**Idea** [0:13:21–0:15:13]: "we construct a plot that has just linear approximations... for the magnitude in each of the key regions of behavior." There are two regions:
- $\omega<\omega_z$: use the $\omega\to0$ limit, which is 0 dB.
- $\omega>\omega_z$: use the $\omega\to\infty$ limit, $20N\log|\omega/\omega_z|$. This is "a straight line on this log log scale."

The trade: you can sketch it "very quickly... at the price of a little bit of loss in accuracy." [0:14:22–0:14:26]

**Figure (f_0078 right, "Bode magnitude plot:", drawn after a "≈" sign).** Axes $M(\omega)$[dB] with ticks 0, 10N, 20N, and $\omega$ with ticks $0.1\omega_z$, $\omega_z$, $10\omega_z$. In green: a horizontal segment at **0 dB up to $\omega_z$**, then a straight line rising from $(\omega_z,0)$ through **$(10\omega_z,20N)$**. The line is labelled "$=20N\log|\omega/\omega_z|$".

Why this form: "drawing it in this form makes it very easy to combine the Bode plots for different factors." [0:17:14]

### 5. Simple zero: actual phase and Bode phase plot [0:17:35–0:25:30]
**Actual phase (f_0075 left, "phase:")** [0:17:35–0:20:08]:
- $\omega\to0$: $\tan^{-1}0=0$.
- $\omega\to\infty$: $\tan^{-1}(\text{large})\to90°$, times $N$.
- $\omega=\omega_z$: $N\tan^{-1}1=$ **45°N**, the halfway point.

Axes: $\phi(\omega)$ with ticks 0°, 45°N and 90°N, plus a dashed line at 90°N. The horizontal axis is log $\omega$ with ticks $0.1\omega_z$, $\omega_z$, $10\omega_z$. The green S-curve runs through the dot $(\omega_z,45°N)$ and approaches 90°N.

**Bode phase plot (f_0075 right)** [0:20:13–0:23:32]. The vertical axis is linear and the frequency axis is log.
- **Why not reuse the magnitude rule:** that would give 0° up to $\omega_z$ and then "a discontinuous jump to 90 degrees times n... that's a little too lousy of an approximation." It doesn't represent the shape of the green curve. [0:21:06–0:21:55]
- **His rule:** use the low-frequency limit only when $\omega$ is *much* lower than $\omega_z$, and "the criterion that we will use for much lower is that omega has to be less than point one times [$\omega_z$]." Use the high-frequency limit only above $10\omega_z$. In between, use a straight line, which "has the advantage of going through the correct point at omega z." [0:22:05–0:23:21]

**Figure:** green 0° up to $0.1\omega_z$, then a straight line through the dot $(\omega_z,45°N)$ to $(10\omega_z,90°N)$, then flat at 90°N on the dashed line.

> [!check] Verified (python, N = 1): the exact magnitude is 0.043 dB at $0.1\omega_z$ and 20.043 dB at $10\omega_z$. The largest magnitude error is 3.01 dB at the corner. The exact phase is 5.71° at $0.1\omega_z$ and 84.29° at $10\omega_z$. The largest phase error of the straight line is **5.71°**, at the two ends of the ramp. These error numbers are mine, not his.

**Terminology** (student question, 0:23:39). Is a "Bode plot" the machine-computed curve? "The way that we're using the Bode plot terminology here is the way it is used in the Ulaby textbook... Bode plots refer specifically to these linearly approximated versions." Elsewhere, the exact curves are also called Bode plots. Either way, magnitude is plotted in dB against log $\omega$, and phase on a linear axis against log $\omega$. [0:24:00–0:25:25]

### 6. Definition: zero of order N [0:25:33–0:28:52]
**Board (f_0091):** "$\omega_z$ is called a **zero** of $H(\omega)$, of order $N$ (since $\omega=j\omega_z\Rightarrow N(\omega)=H(\omega)=0$)."
- At $\omega=j\omega_z$: $1+j(j\omega_z)/\omega_z=1-1=0$. "Order $N$ because $N$ is the exponent of that factor." [0:26:01–0:26:53]
- **Why the $j$** [0:27:21–0:28:46]: time-domain responses are sums of exponentials $e^{st}$. Decay is a real $s$. "Oscillatory behavior, which is what we have when we're talking about real frequencies, correspond[s] to imaginary values of s." The full treatment comes with Laplace transforms.

> [!note] Added context: with $s=j\omega$, the condition $\omega=j\omega_z$ is $s=-\omega_z$. The zero sits on the negative real axis of the s-plane. The same holds for the pole: $s=-\omega_p$. This is the link to the Laplace lectures.

### 7. Simple pole: setup and an RC circuit that produces it [0:28:55–0:32:52]
**Board (f_0097):**
$$\text{Now suppose } D(\omega)=\left(1+j\frac{\omega}{\omega_p}\right)^N,\ N(\omega)=1$$
$$\Rightarrow M(\omega)[\mathrm{dB}]=-20N\log\left|1+j\frac{\omega}{\omega_p}\right|,\qquad \phi(\omega)=-N\tan^{-1}\frac{\omega}{\omega_p}$$
These are the negatives of the zero results, because the factor is "what we had previously to the minus one". The log and the phase each pick up a minus sign. [0:30:19–0:30:42]

**Circuit (f_0097).** $V_s$ (+ on top) is on the left, $R$ sits on the top wire, and $C$ is a shunt to the bottom wire. $V_o$ is across $C$. You get this factor from voltage division whenever the series combination has "a real term and an imaginary term", for example R in series with L or C. [0:30:58–0:31:43]
$$V_o=\frac{V_s}{1+j\omega RC}$$
Implied: $\omega_p=1/RC$ (sympy ✓). Since these are the zero plots "reflected through the horizontal axis," you should be able to predict them. [0:32:40–0:33:02]

### 8. Simple pole: magnitude and Bode magnitude plot [0:33:05–0:36:25]
**Actual (f_0130 left, "magnitude:").** The 0 dB axis is drawn at the top, with $\omega$ ticks $0.1\omega_p$, $\omega_p$, $10\omega_p$ along it. Vertical ticks are $-3N$, $-10N$, $-20N$. At $\omega_p$ the value is $-20N\log\sqrt2=$ **$-3N$ dB** (dot). The curve approaches 0 at low $\omega$ and falls as $\approx-20N\log|\omega/\omega_p|$ at high $\omega$.

> [!warning] Board and speech error (minor). The label on the actual pole curve reads "$\approx-20\log|\omega/\omega_p|$", without the $N$. The speech at 0:34:30 drops it too. **Correct: $\approx-20N\log|\omega/\omega_p|$**, as on the Bode plot beside it. Separately, at 0:34:25 he says "at high frequencies, it's going to increase". It *decreases*, and the board curve goes down.

**Bode magnitude (f_0130 right).** 0 dB up to $\omega_p$, then a straight line down through about $(10\omega_p,-20N)$, labelled "$=-20N\log|\omega/\omega_p|$". Vertical ticks are $-10N$ and $-20N$. [0:34:47–0:36:19]

> [!warning] Speech imprecision [0:36:04]: "linear with a slope... equal to minus 20 n times the log of omega over omega p." That expression is the *line*. The *slope* is $-20N$ dB/decade, which he states correctly at 0:50:05 and 0:54:11.

### 9. Simple pole: phase, Bode phase, and the pole definition [0:36:25–0:41:57]
- Limits: $0$ as $\omega\to0$, $-90°N$ as $\omega\to\infty$, and $-45°N$ at $\omega_p$. [0:36:41–0:37:12]
- **Actual (f_0134 left).** 0° axis at the top, ticks $-45°N$ and $-90°N$ (dashed). The curve passes through the dot $(\omega_p,-45°N)$.
- **Bode phase (f_0134 right).** 0° up to $0.1\omega_p$, a straight line through $(\omega_p,-45°N)$ to $(10\omega_p,-90°N)$, then flat. "Linear interpolation between these." [0:39:15–0:39:52]
- **Board (f_0154):** "$\omega_p$ is called a **pole** of $H(\omega)$, of order $N$ (since $\omega=j\omega_p\Rightarrow D(\omega)=0,\ H(\omega)\to\infty$)." A pole is "a point at which the transfer function goes to infinity in this particular way." [0:40:09–0:41:24]
- Student check [0:41:35]: to get dB, "take the log and multiply by 20". He answered: "That's right."

> [!note] Added context: $20\log_{10}$ applies to voltage and current ratios, which is every $H$ in this course. $10\log_{10}$ is for power ratios.

### 10. General form: $H$ as a product of standard factors [0:41:57–0:43:34]
**Board (f_0160, f_0166):** "In general, $H(\omega)$ can be written in the form $H(\omega)=A_1(\omega)A_2(\omega)\cdots A_n(\omega)$ where each $A_i(\omega)$ is one of the following:"
"For any linear circuit, there will be a limited number of types of factors." [0:42:08]

### 11. The standard-factor table [0:43:34–1:06:11]
The board table (f_0170 → f_0286) has three columns: "$A_i(\omega)$ | Bode magnitude plot | Bode phase plot". Every curve is green. Dashed horizontal lines mark the asymptotic phase.

| $A_i(\omega)$ (his name) | Corner, ticks drawn | Bode magnitude | Bode phase | Circuit origin he gives | t |
|---|---|---|---|---|---|
| constant $K$ | none | flat at $20\log\lvert K\rvert$ (drawn above 0, i.e. $\lvert K\rvert>1$) | flat **0° if $K>0$**, flat **±180° if $K<0$** | "the voltage scale or something like that" | 0:44:21 |
| zero @ origin $(j\omega)^N$ | no natural scale, ticks **1, 10, 100** | line through $(1,\,0)$ and $(10,\,20N)$: **+20N dB/decade** | flat **+90°N** | multiplying by $j\omega L$ | 0:46:06 |
| pole @ origin $\dfrac{1}{(j\omega)^N}$ | ticks 1, 10, 100 | line through $(1,0)$, $(10,-20N)$: **−20N dB/decade** | flat **−90°N** | multiplying by $1/j\omega C$ | 0:48:45 |
| simple zero @ $\omega_z$: $\left(1+j\frac{\omega}{\omega_z}\right)^N$ | $0.1\omega_z,\ \omega_z,\ 10\omega_z$ | 0 dB to $\omega_z$, then **+20N dB/decade** (20N at $10\omega_z$) | 0° to $0.1\omega_z$, ramp (45°N at $\omega_z$), **90°N** from $10\omega_z$ | current into series R–L | 0:51:05 |
| simple pole @ $\omega_p$: $\dfrac{1}{\left(1+j\frac{\omega}{\omega_p}\right)^N}$ | $0.1\omega_p,\ \omega_p,\ 10\omega_p$ | 0 dB to $\omega_p$, then **−20N dB/decade** | 0° to $0.1\omega_p$, ramp, **−90°N** from $10\omega_p$ | RC divider, output across C | 0:53:03 |
| quadratic zero @ $\omega_z$: $\left[1+j2\xi\frac{\omega}{\omega_z}+\left(\frac{j\omega}{\omega_z}\right)^2\right]^N$ | $0.1\omega_z,\ \omega_z,\ 10\omega_z$ | 0 dB to $\omega_z$, then **+40N dB/decade** (40N at $10\omega_z$) | 0° to $0.1\omega_z$, ramp, **180°N** from $10\omega_z$ | current into series R–L–C | 0:55:23 |
| quadratic pole @ $\omega_p$: $\dfrac{1}{\left[1+j2\xi\frac{\omega}{\omega_p}+\left(\frac{j\omega}{\omega_p}\right)^2\right]^N}$ | $0.1\omega_p,\ \omega_p,\ 10\omega_p$ | 0 dB to $\omega_p$, then **−40N dB/decade** | 0° to $0.1\omega_p$, ramp, **−180°N** from $10\omega_p$ | $V_s$ → series R, L → shunt C, output across C | 1:02:21 |

Row details:

**Constant $K$** [0:44:21–0:46:04]. "20 times the log of that constant". The board has $|K|$. Phase "zero if k is greater than zero, and... plus or minus a 180 degrees if k is less than zero."

**Zero at origin** [0:46:06–0:48:39]. "For a zero at the origin, there's no natural frequency scale for it. So we'll just say a frequency of one, 10, a 100." At $\omega=1$ the value is 0 dB, and at $\omega=10$ it is $20N$. The line continues below 0 dB for $\omega<1$. **Definition:** "a decade is a factor of 10 change... the slope here is 20 n decibels per decade." The phase of $j$ is 90°, so $(j)^N$ gives $90°N$.

**Pole at origin** [0:48:45–0:50:44]. The mirror image: through $(1,0)$ and $(10,-20N)$, slope $-20N$ dB/decade. "We have a j in the denominator, which has a phase of minus 90 degrees," so the total is $-90°N$.

**Simple zero / simple pole** [0:50:48–0:55:03]. These are the same plots as sections 4–9, redrawn compactly. Corner ticks are $\omega_c$ and $10\omega_c$ on the magnitude plot and $0.1\omega_c$, $\omega_c$, $10\omega_c$ on the phase plot. The slope label is "20N dB/decade" or "−20N dB/decade". (The speech says "minus nine degrees times n" at 0:54:30, a slip for $-90°N$. The board is correct.)

**Quadratic zero** [0:55:13–1:02:12]:
- $\xi$ is the lowercase Greek **xi**, "just the coefficient of the linear term... typically related to the resistance." Capital Xi is three horizontal bars. [0:56:04–0:56:56]
- **Circuit (f_0198).** The current source $I$ (arrow up) feeds a series R–L–C branch between the output terminals. You get three terms, "a real term and two imaginary terms": $R+j\omega L+\frac1{j\omega C}$. "If you multiply through by j omega c, then you'll end up getting something that looks like this." [0:57:08–0:58:00]
- Limits: as $\omega\to0$ the factor tends to 1, which is 0 dB. As $\omega\to\infty$ "it's this omega squared term that will dominate... $(\omega/\omega_z)^{2N}$... two n times 20, which is 40 n." [0:58:38–0:59:28] So the slope is **+40N dB/decade** above $\omega_z$: "it's steeper... than if we had the simple zero." [1:00:26–1:00:38]
- Phase: 0 at low $\omega$. At high $\omega$, "$j$ to the two n... 90 degrees times two n, which is a 180 degrees times n." The Bode phase is 0 below $0.1\omega_z$, $180°N$ above $10\omega_z$, with a straight line in between. [1:01:02–1:02:07]
- **Figure (f_0201).** Magnitude ticks are 0 and 40N, with $\omega_z$ and $10\omega_z$. The line passes through about $(10\omega_z, 40N)$. Phase ticks are 0° and 180°N (dashed), with $0.1\omega_z$, $\omega_z$, $10\omega_z$.

**Quadratic pole** [1:02:21–1:06:11]:
- **Circuit (f_0286).** A voltage source, then $R$ and $L$ in series on the top wire, then $C$ as a shunt across the output terminals. You get this factor from voltage division when the series combination has "three terms, each with a different power of omega." [1:03:04–1:03:53]
- The plots are the negatives of the quadratic zero: **−40N dB/decade** above $\omega_p$, and phase from 0° to **−180°N** (ramp from $0.1\omega_p$ to $10\omega_p$). [1:03:56–1:06:09]
- **Figure (f_0286).** The 0 dB axis is at the top, with $\omega_p$ and $10\omega_p$. The line runs down through a dot at $10\omega_p$, labelled "−40N dB/decade". The phase axis is at the top at 0°, with a dashed line at −180°N.

> [!warning] Board error: on the quadratic-pole magnitude plot (f_0286), the lower vertical tick is labelled **"40N" with no minus sign** (confirmed on a zoomed crop). The speech at 1:04:37 also says "the scale here is gonna be 40 n". **Correct: $-40N$ dB.** The slope label "−40N dB/decade" and the spoken "minus 40 n dB per decade" [1:05:03] are correct.

> [!check] Verified (sympy):
> - Series RLC driven by a current: $Z\cdot j\omega C=1+j\omega RC-\omega^2LC=1+j2\xi\frac{\omega}{\omega_0}+\left(\frac{j\omega}{\omega_0}\right)^2$ with $\omega_0=\frac{1}{\sqrt{LC}}$ and $\xi=\frac R2\sqrt{\frac CL}$. So $V=\frac{I}{j\omega C}[\text{quadratic}]$: a quadratic zero together with a pole at the origin and a constant $1/C$.
> - RLC with the output across $C$: $V_o/V_s=\dfrac{1}{1-\omega^2LC+j\omega RC}$, a pure quadratic pole with the same $\omega_0$ and $\xi$.
> - $20\log(10^2)=40$ dB per decade ✓.

> [!note] Added context: the quadratic straight lines ignore $\xi$, and so did he.
> - At $\omega=\omega_c$ the quadratic factor equals exactly $j2\xi$. Its phase is exactly $90°$ per order, for any $\xi$, so his ramp's midpoint ($\pm90°N$ at $\omega_c$, not labelled on the board) is exact.
> - Its magnitude there is $20N\log(2\xi)$ dB, not 0. It matches the asymptote only at $\xi=0.5$. At $\xi=0.1$ it is −13.98 dB, a dip for a zero or a +13.98 dB peak for a pole. At $\xi=1$ it is +6.02 dB.
> - For small $\xi$, the real phase change is also much sharper than the two-decade ramp.
> - Quote $\xi$ (or $Q$) whenever a resonant peak matters. Next lecture's Q/bandwidth material lives here.

### 12. Why the table is useful: Bode plots add [1:06:18–1:09:33]
He scrolled back up to $H=A_1\cdots A_n$ (f_0258/f_0269):
- **Magnitude:** "the log of this product here will just be the sum of the logs of the individual factors." Adding a constant "you just increase the level." Adding straight lines gives a straight line, and "the slope is just the sum of the slopes of the individual lines." [1:06:35–1:07:48]
- **Phase:** "the phases always appear in exponents... the phases just add up." [1:07:52–1:08:36]
- **Board (f_0302):** "Bode plots for each factor $A_i(\omega)$ in $H(\omega)$ can be added to each other to obtain the Bode plots for $H(\omega)$." [1:08:42–1:09:20]

**No combined multi-factor example was worked in this lecture.**

### 13. Passive vs active filter circuits [1:09:33–1:12:21]
**Board (f_0304, f_0313):** "**Passive Filter Circuits**. Reading: Ulaby et al, Secs. 9-4, 9-5."
- "**Passive** filters are filter circuits that contain only passive elements (R, L, C) plus input signals." The drive "could be represented as a source of some sort", but "you get the filter functionality only from passive components." [1:10:17–1:11:41]
- "**Active** filters contain op amps, transistors, or other active devices", which he describes as "devices that can give you gain." In this course that means op amps. "We'll see... why it's useful to have that." [1:10:40–1:12:18]

### 14. Example: series RLC bandpass filter, output across R [1:12:25–1:18:24]
**Board heading (f_0315):** "Example: band pass filter."

**Circuit (f_0316).** $V_s$ (circle, + on top) is on the left. The top wire carries $L$, then $C$, in series to a node that continues to the + output terminal. $R$ is the shunt from that node to the bottom wire. $V_R$ is across $R$ (+ top, − bottom). This is "a simple RLC series circuit... the output voltage is taken across the resistor." [1:12:44–1:13:18]

**Qualitative argument (say this on a P1)** [1:13:28–1:14:18]:
- **Low $\omega$:** "the impedance of the capacitor will be very high, much higher than the impedance of the resistor. So the output voltage will be very low."
- **High $\omega$:** "the impedance of the inductor will be very high", so the output is low again.
- **In between:** "there will be some frequency where the impedance of the inductor and the capacitor will cancel each other out... essentially all of the input signal appearing across the resistor."

**Derivation (f_0321, f_0330)** [1:14:27–1:16:18]:
$$V_R=\frac{Z_R}{Z_R+Z_L+Z_C}V_s=\frac{R}{R+j\omega L+\frac{1}{j\omega C}}V_s$$
$$\Rightarrow H(\omega)=\frac{V_R}{V_s}=\frac{R}{R+j\omega L+\frac{1}{j\omega C}}\left(\frac{j\omega C}{j\omega C}\right)=\frac{j\omega RC}{1-\omega^2LC+j\omega RC}$$
Reading the factors: "we're gonna get a quadratic pole due to this factor in the denominator, and we're going to get a zero at the origin, right, plus some constant." [1:16:08–1:16:18]

**Rectangular form** [1:16:31–1:17:46]. Multiply by the conjugate of the denominator over itself (green on f_0330). The result is **speech-only**, because the frames end at 1:17:16:
$$H(\omega)=\frac{j\omega RC}{1-\omega^2LC+j\omega RC}\cdot\frac{1-\omega^2LC-j\omega RC}{1-\omega^2LC-j\omega RC}=\frac{\omega^2R^2C^2+j\omega RC\,(1-\omega^2LC)}{(1-\omega^2LC)^2+\omega^2R^2C^2}$$
"in the denominator, we're just gonna get the magnitude squared of the denominator, which is the real part squared plus the imaginary part squared." Either form can be used. [1:17:16–1:17:56]

> [!check] Verified (sympy): both forms are identical to $R/(R+j\omega L+1/j\omega C)$. At $\omega=1/\sqrt{LC}$, $H=1$ (0 dB, 0°), which is mine and not stated.

> [!warning] Related to **PS8 9.26** (series RLC bandpass parameters). This lecture derived only the general symbolic $H(\omega)$; it did not work the graded problem. The tutor must not use this section as a walkthrough or check for 9.26's numbers.

> [!note] Added context (standard form, not done in lecture): $H=(RC)\cdot(j\omega)\cdot\dfrac{1}{1+j2\xi\frac{\omega}{\omega_0}+\left(\frac{j\omega}{\omega_0}\right)^2}$ with $\omega_0=1/\sqrt{LC}$ and $\xi=\frac R2\sqrt{C/L}$. In his table that is a constant $K=RC$, a zero at the origin and a quadratic pole at $\omega_0$. Asymptotically: +20 dB/decade below $\omega_0$ and −20 dB/decade above it. The other outputs of the same series loop give the other filter types (not covered this lecture; sympy-checked): across $C$, $\frac{1}{1-\omega^2LC+j\omega RC}$ is **lowpass**; across $L$, $\frac{-\omega^2LC}{1-\omega^2LC+j\omega RC}$ is **highpass**; across $L$+$C$, $\frac{1-\omega^2LC}{1-\omega^2LC+j\omega RC}$ is **bandstop**.

**Preview** [1:17:57–1:18:24]: next time (Monday 10/26), "the magnitude and phase of this transfer function," which introduces **bandwidth and quality factor** "for filter circuits specifically and for frequency dependent circuits more generally." **Resonance, Q and bandwidth (series or parallel) were not covered in this lecture.**

---

## Ed Yu's conventions & notation

| Item | His convention (this lecture) |
|---|---|
| Transfer function | $\underset{\sim}{H}(\omega)=\underset{\sim}{N}(\omega)/\underset{\sim}{D}(\omega)=M(\omega)e^{j\phi(\omega)}$, with an under-tilde on $H$, $N$, $D$, $A_i$, $V$, $I$, $Z$. The argument is $\omega$, not $j\omega$ or $s$. |
| Magnitude in dB | Written "$M(\omega)[\mathrm{dB}]$" $=20\log|\cdot|$ ($\log=\log_{10}$). The axis label is "$M(\omega)$[dB]". |
| Phase | $\phi(\omega)$, in **degrees**, written "$N\tan^{-1}\frac{\omega}{\omega_z}$". |
| Order | Capital **$N$** is the exponent and appears on every axis value: $20N$, $3N$, $45°N$, $40N$ dB/decade. (The same letter is also used for the numerator polynomial $N(\omega)$.) |
| Corner names | $\omega_z$ for a zero and $\omega_p$ for a pole, for simple and quadratic factors alike. Row names: "simple zero @ $\omega_z$", "quadratic pole @ $\omega_p$", "zero @ origin", "pole @ origin", "constant $K$". |
| Standard forms | $\left(1+j\frac{\omega}{\omega_c}\right)^{\pm N}$, $(j\omega)^{\pm N}$, $\left[1+j2\xi\frac{\omega}{\omega_c}+\left(\frac{j\omega}{\omega_c}\right)^2\right]^{\pm N}$. The damping symbol is lowercase **$\xi$** (xi), not $\zeta$. |
| Frequency ticks | **$0.1\omega_c,\ \omega_c,\ 10\omega_c$**, one decade apart. Origin factors have no natural scale, so the ticks are **1, 10, 100**. |
| Magnitude values labelled | 0, 10N, 20N (and 3N on the *actual* curve). The pole versions are negative. Quadratics use 40N. |
| Phase values labelled | 0°, 45°N, 90°N, or 0°, 180°N, with a **dashed** horizontal line at the asymptotic phase. |
| Slope label | Written **next to the line** with an arrow: "20N dB/decade", "−40N dB/decade". On the first plots he labels the line by its equation instead: "$=20N\log|\omega/\omega_z|$". |
| Plot layout | The actual curve on the left, a "$\approx$" sign, then the "Bode magnitude plot:" / "Bode phase plot:" on the right. The curves are green. The dots mark the exact points at $\omega_c$ and $10\omega_c$. |
| Pole plots | Drawn with the 0 dB (or 0°) axis at the **top** and the curve going down. |
| "Bode plot" | Means **only the straight-line approximation**, per Ulaby. |
| "Decade" | "A factor of 10 change". Slopes are given "per decade". |
| Circuit for a factor | He gives a minimal circuit for each factor: current into R–L for a zero, an RC divider for a pole, RLC for a quadratic. |

---

## Intuition & explanations he gives

- **Why Bode plots work:** a log turns products into sums, so "the difference of the logs of the numerator and the denominator" means factor plots simply add. [0:02:24–0:02:49, 1:06:35–1:08:36]
- **Why straight lines for magnitude:** in each "key region of behavior", replace the function by its limiting behaviour. This trades "a little bit of loss in accuracy" for something "we can sketch out very quickly." [0:13:40–0:14:26]
- **Why the phase uses a ramp from $0.1\omega_c$ to $10\omega_c$, not a step:** a step at $\omega_c$ "doesn't really sufficiently correctly represent the shape" of the actual curve. The ramp "has the advantage of going through the correct point at omega z." [0:21:40–0:23:21]
- **Why the corner value is 3N dB:** $|1+j|=\sqrt2$, and $20\log\sqrt2=10\log2\approx3$ dB. [0:09:57–0:10:24]
- **Why a pole is a mirror image of a zero:** the factor is "what we had previously to the minus one", so the log and the phase change sign. The plots are "reflected through the horizontal axis." [0:30:35, 0:32:54]
- **Why "zero" and "pole":** at $\omega=j\omega_c$ the factor vanishes, so $H=0$ for a zero and $H\to\infty$ for a pole. The $j$ appears because real oscillation corresponds to imaginary $s$ in $e^{st}$, previewing Laplace. [0:26:01–0:28:46, 0:40:32]
- **Why quadratics are steeper:** "it's this omega squared term that will dominate," which doubles both the dB slope (40N) and the phase swing (180°N). [0:59:01–1:01:30]
- **Where each factor comes from physically:** $j\omega L$ gives a zero at the origin and $1/j\omega C$ a pole at the origin. R in series with L or C, in a divider denominator, gives a simple pole. R+L+C gives "three terms, each with a different power of omega", which is a quadratic. Higher orders need "multiple stages... where there's something in between." [0:07:50–0:08:52, 0:30:58, 0:46:31, 0:49:09, 1:03:19]
- **Why the series RLC across R is a bandpass:** the impedances argument in section 14. $Z_C$ dominates at low $\omega$, $Z_L$ at high $\omega$, and they cancel in between, leaving all of $V_s$ across $R$. [1:13:28–1:14:18]
- **What "passive" means:** the filtering comes "only from passive components". An active filter adds devices "that can give you gain." [1:10:26–1:12:18]

---

## Emphasis & exam intel

1. **Straight lines are the definition here** [0:24:14]: "Bode plots refer specifically to these linearly approximated versions" (Ulaby). Past exams demand Bode plots "using linear approximations as done in class". This lecture is that construction.
2. **The phase ramp rule** [0:22:23, 0:22:50]: the "criterion... for much lower is that omega has to be less than point one times" $\omega_c$, and "sufficiently far, we define as being greater than 10" $\omega_c$.
3. **A phase step is wrong** [0:21:40]: "that's a little too lousy of an approximation."
4. **Label the key values** (every one of his plots does): corner ticks $0.1\omega_c$, $\omega_c$, $10\omega_c$; dB values ($20N$, $40N$); phase values ($45°N$, $90°N$, $180°N$); and a slope label in dB/decade next to every non-zero slope.
5. **Origin factors** [0:46:57]: "there's no natural frequency scale... we'll just say a frequency of one, 10, a 100."
6. **"Decade"** [0:47:45–0:48:02]: "a decade is a factor of 10 change"; "20 n decibels per decade."
7. **Additivity** [1:07:36, 1:08:13]: "the slope is just the sum of the slopes", and "the phases just add up." Expect a multi-factor P3/P4 that is built this way.
8. **Every circuit $H$ factors into the table** [0:42:08]: "for any linear circuit, there will be a limited number of types of factors."
9. **The bandpass impedance argument** [1:13:28–1:14:13] is a ready P1 answer: why a series RLC with the output across R passes a band.
10. **Factor-reading habit** [1:16:08]: on any $H$, immediately name the factors ("a quadratic pole... a zero at the origin... plus some constant").
11. **PS7 coverage** [0:00:27]: "transfer functions, Bode plots, and filter circuits... basically, the material that we are covering now."
12. **Coming next** [1:18:04]: magnitude and phase of the RLC bandpass, then bandwidth and quality factor.

---

## Student questions

| t | Question (reconstructed) | His answer |
|---|---|---|
| 0:07:34 | In the R–L example, where does the exponent $N$ come from? | Here $N=1$. Higher $N$ needs multiple stages "where there's something in between". He drew a green second R–L stage and said "not exactly like this". Filter orders come later. |
| 0:11:51 | In $V_o=IR(1+j\omega L/R)$, what role does $I$ play? Is it an arbitrary current source? | It is whatever current the rest of the circuit supplies, or simply a current source. "This is just an example of how you get this kind of factor, not... the only kind of circuit." |
| 0:23:39 | Aren't Bode plots machine-generated by sampling frequencies? These look hand-made. | Terminology differs. In Ulaby, and so in this course, "Bode plot" means the straight-line version. Elsewhere the exact computed curves are also called Bode plots. Either way: dB vs log $\omega$, and linear phase vs log $\omega$. |
| 0:41:35 | To get a transfer function in decibels, take the log and multiply by 20? | "Yeah. That's right." |
| 0:56:04 | What is that letter? | Lowercase Greek xi ($\xi$), the coefficient of the linear term, typically related to resistance. Capital Xi is three horizontal bars. |
| 0:00:57, 1:18:28 | (Calls for questions) | None asked. |

---

## Exam relevance

**P3 (filter transfer function + cutoff + Bode plots): primary.** This lecture is the whole construction method.
- Write $H$ in standard factors.
- Read each corner $\omega_c$ and order $N$.
- Draw each factor's asymptotes using the table: magnitude breaks at $\omega_c$, phase ramps from $0.1\omega_c$ to $10\omega_c$.
- Sum the factors.
- Label the corner frequencies, decade ticks, dB levels, phase levels, and every non-zero slope in dB/decade.

The simple-pole facts give the cutoff: $-3$ dB at $\omega_p$ for $N=1$. The RC divider gives $\omega_p=1/RC$.

**P4 (op-amp or RLC filter: $H(\omega)$ in factored standard form, filter type, Bode plots, design ratio): high.**
- The factor table is the "standard form" vocabulary: $K$, $(j\omega)^{\pm N}$, $(1+j\omega/\omega_c)^{\pm N}$, and the quadratic with $\xi$.
- The bandpass example shows how to factor an RLC $H$: a zero at the origin, a constant, and a quadratic pole.
- Know that $j\omega L$ and $1/j\omega C$ create origin factors, which is how an op-amp impedance ratio $-Z_f/Z_i$ produces them (Added context).
- The type of a sign-inverting (op-amp) $H$ shows up as a $K<0$ row: ±180° on the phase plot.

**P1 (conceptual short answers): medium.** Likely stems:
1. Why does a series RLC with the output across R act as a bandpass? Use the impedance limits.
2. Why is the corner 3 dB?
3. Why does the phase plot use a two-decade ramp?
4. What is a zero or a pole of order $N$?
5. Why can Bode plots of factors be added?
6. Passive vs active filter.

Semiconductor physics: **not** in this lecture.

**P2 (passive filter design / max power transfer): low to medium.** It gives the first-order design relations implied on the board, $\omega_p=1/RC$ (RC lowpass) and $\omega_z=R/L$, and the definition of a passive filter. Design and Q/bandwidth come in the next lectures. Max power transfer is not here.

---

## Common mistakes / traps

1. **Dropping $N$ or the minus sign on axis labels.** He did both on the board ($-20\log$ without $N$; "40N" for $-40N$). On an exam, every label on a pole plot is negative and carries $N$.
2. **A phase step at $\omega_c$.** The magnitude breaks at $\omega_c$, but the phase ramps from $0.1\omega_c$ to $10\omega_c$, and the midpoint ($\pm45°N$, or $\pm90°N$ for a quadratic) falls at $\omega_c$.
3. **Quadratic ≠ two simple factors in the labels.** It is ±40N dB/decade and ±180°N, and the asymptotes ignore $\xi$. A double *simple* pole $(1+j\omega/\omega_p)^{-2}$ has the same asymptotes but no resonant peak. (Exact at $\omega_p$: −6.02 dB, versus $20\log(2\xi)$ for a quadratic.)
4. **Origin factors have no corner.** $(j\omega)^N$ passes 0 dB at $\omega=1$ rad/s. Combined with a constant, $K\,j\omega$ crosses 0 dB at $\omega=1/|K|$ (Added context). Do not draw a flat segment for it.
5. **Not in "1 +" form.** $(j\omega+a)$ must be rewritten as $a(1+j\omega/a)$, and $a$ moves into $K$. Otherwise the 0 dB low-frequency asymptote is wrong (Added context, implied by his standard forms).
6. **Negative $K$:** the magnitude uses $|K|$, and the phase shifts by ±180°. Do not take the log of a negative number.
7. **"Magnitude goes to zero"** in his speech means 0 dB ($|H|=1$), not $|H|=0$.
8. **$20\log$, not $10\log$,** for voltage and current transfer functions.
9. **A log axis has no $\omega=0$.** Start the plot a decade or more below the lowest corner.
10. **The slope versus the line equation:** "−20N log|ω/ω_p|" is the line. Its slope is −20N dB/decade. Label the slope.
11. **Series RLC output element sets the type** (Added context): R gives bandpass, C lowpass, L highpass, and L+C bandstop. Mixing them up flips P1/P4 answers.

---

## Self-check

**Q1.** Bode plots for $H(\omega)=\dfrac{1}{(1+j\omega/100)^2}$ (ω in rad/s). Give the straight-line magnitude at $\omega=1000$ and the straight-line phase at 10, 100 and 1000 rad/s. What is the exact magnitude at 100 rad/s?
> [!question]- Answer
> This is a **simple pole of order N = 2** at $\omega_p=100$, not a quadratic.
> - Magnitude: 0 dB up to 100, then **−40 dB/decade**, so **−40 dB at 1000**.
> - Phase: 0° for $\omega\le10$, a ramp through **−90° at 100**, and **−180° for $\omega\ge1000$**.
> - Exact at 100: $|1/(1+j)^2|=1/2$, which is **−6.02 dB** (= $-3N$ with $N=2$).
> - (python: exact −0.09 dB / −11.4° at 10, −40.09 dB / −168.6° at 1000.)

**Q2.** Write $H(\omega)=\dfrac{j\omega RC}{1-\omega^2LC+j\omega RC}$ (the series RLC with output across R) as a product of his standard factors, and name each one. Do it symbolically only.
> [!question]- Answer
> $H=\underbrace{RC}_{\text{constant }K}\cdot\underbrace{(j\omega)}_{\text{zero @ origin}}\cdot\underbrace{\dfrac{1}{1+j2\xi\frac{\omega}{\omega_0}+\left(\frac{j\omega}{\omega_0}\right)^2}}_{\text{quadratic pole @ }\omega_0}$ with $\omega_0=1/\sqrt{LC}$ and $2\xi/\omega_0=RC$, so $\xi=\frac R2\sqrt{C/L}$ (sympy ✓). The asymptotes are +20 dB/decade below $\omega_0$ and −20 dB/decade above. The phase goes from +90° to −90°. This matches his reading "a quadratic pole... a zero at the origin... plus some constant."

**Q3.** Sketch the straight-line Bode plots of $H(\omega)=\dfrac{10\,j\omega}{1+j\omega/1000}$. Give the magnitude at $\omega=1,\ 10,\ 1000,\ 10^4$, the phase at $\omega\le100$, at $1000$ and at $\ge10^4$, and the filter type.
> [!question]- Answer
> The factors are $K=10$ (+20 dB flat), a zero at the origin (+20 dB/decade through 0 dB at ω = 1), and a simple pole at 1000 (−20 dB/decade above 1000).
> - Magnitude sum: 20 dB at 1, 40 dB at 10, 80 dB at 1000, then **flat at 80 dB** above 1000 (the slopes cancel).
> - Phase: +90° (origin zero) plus the pole ramp. That is **+90° for ω ≤ 100**, **+45° at 1000**, and **0° for ω ≥ 10⁴**.
> - Type: **highpass**.
> - (python exact: 76.99 dB and 45.0° at 1000. 79.96 dB and 5.7° at 10⁴.)

**Q4.** In one or two sentences each: (a) why is the Bode magnitude of a simple zero 3N dB *below the true curve* at $\omega_z$, and (b) why does he refuse to draw the phase as a step at $\omega_z$?
> [!question]- Answer
> (a) The Bode plot uses 0 dB, the $\omega\to0$ limit, all the way up to $\omega_z$. The true value there is $20N\log|1+j|=20N\log\sqrt2\approx3N$ dB.
> (b) A step "is a little too lousy of an approximation". The true phase changes gradually over about two decades. So he holds the limits only below $0.1\omega_z$ and above $10\omega_z$ and joins them with a straight line, which passes through the exact $45°N$ at $\omega_z$. Its worst error is 5.7° per order.

**Q5.** Why does a series RLC driven by $V_s$, with the output taken across R, behave as a bandpass filter? Use his argument, no algebra.
> [!question]- Answer
> - At low frequency, $|Z_C|=1/\omega C$ is huge compared with $R$, so almost all of $V_s$ drops across C and $V_R\approx0$.
> - At high frequency, $|Z_L|=\omega L$ is huge, so again $V_R\approx0$.
> - At one intermediate frequency, $j\omega L$ and $1/j\omega C$ cancel, so the whole of $V_s$ appears across R.
> - So a band around that frequency passes and both ends are rejected. (That frequency is $1/\sqrt{LC}$, Added context.)

> [!summary] Board-error audit
> - **Board errors (2):**
>   - The actual simple-pole magnitude label reads "$\approx-20\log|\omega/\omega_p|$", missing $N$ (f_0130, 0:34:30). The speech omits it too.
>   - The quadratic-pole magnitude tick reads "40N" instead of **−40N** (f_0286, 1:04:37). The speech omits the minus too.
> - **Board corrected live (1):** "$20N\log|+j\omega/\omega_z|$" became "$20N\log|1+j\omega/\omega_z|$" (0:07:02).
> - **Speech slips (board correct):**
>   - "at high frequencies, it's going to increase" for the pole magnitude, which decreases (0:34:25).
>   - The line equation called the "slope" (0:36:04).
>   - "point one times z" for $0.1\omega_z$ (0:22:23).
>   - "minus nine degrees times n" for −90°N (0:54:30).
>   - "omega p", corrected to $\omega_z$ (0:58:28).
>   - "minus minus n" (0:30:01).
> - **ASR artifacts:**
>   - "voltage source I" = $V_s$ (0:31:22).
>   - "decimal units" = decibel (0:41:49).
>   - "the foreign jω" = the form $j\omega$ (0:46:20).
>   - "c" = $\xi$ (0:56:22).
>   - "one to the end" = $1^N$ (1:01:02).
>   - "quality and factor" = quality factor, and "filter surface" = filter circuits (1:18:11).
> - **Verified:** every algebraic result and number on the board was re-derived with python/sympy and is correct apart from the two label errors above.
