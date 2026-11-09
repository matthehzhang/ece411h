---
course: ECE 411H
date: 2026-10-26
instructor: Prof. Ed Yu
topic: Series-RLC bandpass (magnitude/phase, resonance, cutoff frequencies, bandwidth), quality factor Q, Bode plots of the bandpass by constituent factors, start of the series-RLC highpass (output across L; phase quadrant correction; M(ω0)=Q)
reading: Ulaby/Maharbiz/Furse 3e §9-4-1 (named on the board for Q); no other section named
source: Recordings/2026-10-26-active-filters (transcript + 33 distinct tablet pages from 144 page-final frames; folder name is a misnomer, there is no op-amp content); page descriptions in Recordings/2026-10-26-active-filters/frames/pages_described.md
tags: [ece411, lecture, filters, bandpass, highpass, resonance, quality-factor, bode-plot, transfer-function, exam2]
source_quality:
  - "Audio 81 min, Deepgram Nova-3, 1121 utterances, mean confidence 0.96; 78 words < 0.55 and 12 utterances < 0.7 (lowest 1:17:42, 0:31:47, 0:10:12); spoken math is transcribed as words, signs and subscripts are the ASR's guess"
  - "Student questions are off-mic and fragmentary; reconstructions are marked (?)"
  - "Board: tablet handwriting, 33 distinct pages; p12-p26 are mostly scroll-backs with no new ink; 1 blurry frame (f_0019, 0:06:33) superseded by a sharp later state"
  - "Every board formula re-derived with python3/sympy; 2 acknowledged board errors, 2 unacknowledged discrepancies, 3 speech slips (see Board-error audit)"
---

# 2026-10-26: RLC Bandpass Cutoffs, Quality Factor, Bode Plots, RLC Highpass

> [!warning] No active-filter (op-amp) content in this lecture
> The recording folder is named `active-filters`, but the lecture is entirely **passive series-RLC filters**: the bandpass from 10/21 is finished, and the highpass is started (output across $L$). There is no ideal op-amp, no $-Z_f/Z_{in}$, no non-inverting stage and no Sallen-Key. It ends with "We'll pick up with this on Wednesday" [1:20:40], so op-amp filters must come from the Wed 10/28 lecture or later. Do not cite this note for P4's op-amp branch.

## Summary

- **Get $H(\omega)$ of a series RLC by voltage division with impedances, then clear the nested fraction** (multiply by $j\omega C/j\omega C$). Both circuits share the denominator $1-\omega^2LC+j\omega RC$. The output across $R$ gives the bandpass $\dfrac{j\omega RC}{1-\omega^2LC+j\omega RC}$; the output across $L$ gives the highpass $\dfrac{-\omega^2LC}{1-\omega^2LC+j\omega RC}$.
- **Name the filter type from limits before any algebra:** the impedance limits ($Z_L=j\omega L\to0$ or $\infty$, $Z_C\to\infty$ or $0$) in a voltage divider, then $M(0)$, $M(\infty)$, $M(\omega_0)$.
- **Resonance:** $\omega_0=1/\sqrt{LC}$ is where $Z_L$ and $Z_C$ cancel and the input impedance is purely real.
- **Magnitude** = |num| / |den|. **Phase:** use the rationalized form (real denominator) or "phase of num − phase of den" **with a quadrant check**. When $\mathrm{Re}(\text{den})<0$, add $180^\circ$ to the calculator's $\tan^{-1}$.
- **Bandpass cutoffs** from $M=1/\sqrt2$: solve a quadratic, keep the 2 positive roots of 4, and label $\omega_{c1}<\omega_{c2}$. $\omega_{c1,2}=\sqrt{(R/2L)^2+1/LC}\mp R/2L$, **$B=R/L$**.
- **Quality factor:** $Q=2\pi\,W_{stor}/W_{diss}$ at $\omega_0$. For the series RLC, $Q=\omega_0L/R=\omega_0/B=\frac1R\sqrt{L/C}$. **High Q ⟺ narrow bandwidth**, and low loss means high Q.
- **Bode by factors:** split $H$ into a constant ($RC$), a zero at the origin ($j\omega$) and a quadratic pole ($1/(1+j\omega RC-\omega^2LC)$, $\omega_p=\omega_0$). Draw each factor, then **add the slopes and add the phases**. Quadratic pole: 0 dB then −40 dB/dec from $\omega_0$; phase $0\to-180^\circ$ in a straight line from $0.1\omega_0$ to $10\omega_0$. Bandpass result: +20 dB/dec up to the peak at $\omega_0$, then −20 dB/dec; phase $+90^\circ\to0\to-90^\circ$.
- **Highpass:** $M(\omega_0)=Q$. Sketch it for $Q<1$ (no peak), $Q>1$ (modest peak) and $Q\gg1$ (sharp tall peak); $M\to1$ at high $\omega$. Phase $180^\circ\to90^\circ\to0^\circ$.
- **Two flags before using his combined Bode plot as a template:** the axis-label errors (fixed in lecture), and the vertex placed at 0 dB, which a literal asymptote sum puts at $-20\log Q$ dB. See the [Board-error audit](#board-error-audit).

---

## Content

### 0. Announcements [0:00:03–0:01:02]
Typed on the board (f_0002):
- **PS7** due **9:00 AM Central, Mon 11/02/2026**.
- **PS8** posted Wed 10/28, due **Mon 11/9/2026**. "Problem Set 8 will cover primarily passive and active filter circuits."
- **Semester Exam 2: in class, Wed 11/11/2026.** "A detailed announcement on the exam will be posted later this week." Spoken: "that'll be the last exam before the final" [0:00:40].

### 1. Recap: series-RLC bandpass, magnitude and phase [0:01:06–0:05:13]
> [!warning] = PS8 9.26 (likely): graded work; the tutor must not use this as a walkthrough or check

Board heading (f_0002): **"From last time - band pass RLC filter."**

**Circuit (f_0010):** source $\tilde V_s$ on the left edge, + on top. The top wire runs left to right: $L$, then $C$, to a node. $R$ goes from that node down to the bottom return wire, and the node also continues to the + output terminal. Output $\tilde V_R$ is across $R$ (+ top, − bottom). It is a single series loop with the output across the resistor.

**Transfer function** (derived on 10/21 by voltage division, rewritten here):
$$\tilde H(\omega)=\frac{j\omega RC}{1-\omega^2LC+j\omega RC}=\frac{\omega^2R^2C^2+j\omega RC(1-\omega^2LC)}{(1-\omega^2LC)^2+\omega^2R^2C^2}$$
The second form comes from multiplying by the complex conjugate of the denominator.

**Magnitude** [0:02:23] from the first form, |numerator| over |denominator|:
$$M(\omega)=|\tilde H(\omega)|=\frac{\omega RC}{\sqrt{(1-\omega^2LC)^2+\omega^2R^2C^2}}$$
**Phase** [0:03:16] from the rationalized form. Its denominator is real, so $\phi=\tan^{-1}(\text{Im}/\text{Re})$, and one factor of $\omega RC$ cancels:
$$\phi(\omega)=\tan^{-1}\!\left(\frac{1-\omega^2LC}{\omega RC}\right)$$
He adds [0:04:42]: "if you had tried to calculate the phase from... taking the phase of the numerator minus the phase of the denominator, it would actually be a little bit trickier... later on today, we'll see an example." (That example is the highpass quadrant correction in §6.)

> [!check] Verified (python3, 2000 random R, L, C, ω): both forms equal $R/(R+j\omega L+1/j\omega C)$, and the board's $M$ and $\phi$ match $|H|$ and $\angle H$ to machine precision. The rationalized-form $\tan^{-1}$ is always in the correct quadrant because the rationalized real part $\omega^2R^2C^2>0$.

### 2. Resonant frequency and limit sketches [0:05:13–0:13:40]
Resonance recap [0:05:29]: the resonant frequency is where "the Thevenin equivalent impedance between the input terminals... [has] the imaginary parts all canceled out... purely real". Here that is $\omega L=1/(\omega C)$:
$$\boxed{\omega_0=\frac{1}{\sqrt{LC}}}\qquad\text{since }\omega_0L=\frac{1}{\omega_0C}\Rightarrow \tilde Z_L\text{ and }\tilde Z_C\text{ cancel out for }\omega=\omega_0.$$

"Not make the Bode plots yet, but do a slightly better sketch" [0:07:33]. He asks the class for the limits:

| | $\omega\to0$ | $\omega=\omega_0$ | $\omega\to\infty$ |
|---|---|---|---|
| $M$ | 0 ("because of the omega in the numerator") | **1** (the $1-\omega^2LC$ term vanishes, leaving $\omega RC/\omega RC$) | 0 |
| $\phi$ | $+90^\circ$ ($\tan^{-1}(+\infty)$) | $0^\circ$ ($\tan^{-1}0$) | $-90^\circ$ ($\tan^{-1}(-\infty)$) |

**Sketches (f_0040 / f_0421), linear axes:**
- *Magnitude:* a green bell from 0 up to a peak of 1 at $\omega_0$ and back toward 0. Dashed horizontals sit at 1 and at $1/\sqrt2$. The $1/\sqrt2$ line meets the curve at $\omega_{c1}$ (left of $\omega_0$) and $\omega_{c2}$ (right), with dashed drops to the axis. The double arrow between them is labelled **$B$**.
- *Phase:* starts at $+90^\circ$, falls through $0$ at $\omega_0$ and approaches $-90^\circ$ (dashed asymptotes at $\pm90^\circ$).

"Clearly, [this] is a bandpass filter" [0:12:07]. There are two cutoff (corner) frequencies, where $M=1/\sqrt2$, called $\omega_{c1}$ and $\omega_{c2}$, and "the difference between them is the bandwidth $B$" [0:12:41].

### 3. Cutoff frequencies and bandwidth [0:13:40–0:23:10]
(PS8 9.26 warning above applies.)

Set $M(\omega_{c1})=M(\omega_{c2})=1/\sqrt2$, with $\omega_{ci}$, $i=1,2$:
$$\frac{\omega_{ci}RC}{\sqrt{(1-\omega_{ci}^2LC)^2+\omega_{ci}^2R^2C^2}}=\frac{1}{\sqrt2}$$
Divide the numerator and denominator by $\omega_{ci}RC$ [0:14:19]:
$$\frac{1}{\sqrt{\left(\dfrac{1-\omega_{ci}^2LC}{\omega_{ci}RC}\right)^2+1}}=\frac{1}{\sqrt2}\;\Rightarrow\;\left(\frac{1-\omega_{ci}^2LC}{\omega_{ci}RC}\right)^2=1\;\Rightarrow\;1-\omega_{ci}^2LC=\pm\,\omega_{ci}RC$$
Rearrange into a quadratic [0:17:00]:
$$LC\,\omega_{ci}^2\pm RC\,\omega_{ci}-1=0$$
Apply the quadratic formula [0:17:31]:
$$\omega_{ci}=\frac{1}{2LC}\left[\mp RC\pm\sqrt{(RC)^2+4LC}\right]=\mp\frac{R}{2L}\pm\sqrt{\left(\frac{R}{2L}\right)^2+\frac{1}{LC}}$$
**Four candidate roots** ("two options for the sign here and two options for the sign here, and they're independent" [0:18:43]). The cutoffs must be positive, so take **+ on the square root** with either sign on $R/2L$, and label $\omega_{c1}<\omega_{c2}$ "because that's how we label them in the plot" [0:19:59]:
$$\omega_{c1}=\sqrt{\left(\frac{R}{2L}\right)^2+\frac{1}{LC}}-\frac{R}{2L},\qquad \omega_{c2}=\sqrt{\left(\frac{R}{2L}\right)^2+\frac{1}{LC}}+\frac{R}{2L}$$
**Bandwidth** [0:21:13]: the square root cancels in the difference:
$$B=\omega_{c2}-\omega_{c1}=\frac{R}{L}$$
- Small $R$ gives a narrow $B$, "very selective in picking out a particular range of frequencies". Large $R$ gives a wide band [0:21:41–0:22:12].
- Only the resistor dissipates power. Low dissipation goes with narrow bandwidth, "and it turns out that that correlation is true under quite general circumstances", which leads to $Q$ [0:22:13–0:23:17].

> [!check] Verified (python3 + sympy): $|H(\omega_{c1})|=|H(\omega_{c2})|=1/\sqrt2$, $B=R/L$, and the step $\sqrt{(RC)^2+4LC}/(2LC)=\sqrt{(R/2L)^2+1/LC}$ holds. **No board error.**

> [!note] Added context (mine, not his)
> - $\omega_{c1}\,\omega_{c2}=\omega_0^2$: $\omega_0$ is the **geometric** mean of the cutoffs, not the arithmetic mean, so it is not centred on a linear axis. (Verified.)
> - $\angle H=+45^\circ$ at $\omega_{c1}$ and $-45^\circ$ at $\omega_{c2}$. (Verified.)
> - $B$ comes out in rad/s because the $\omega$'s are in rad/s. Divide by $2\pi$ if a problem wants Hz.

### 4. Quality factor $Q$ [0:23:10–0:34:11]
Board (f_0094, f_0116):
> **quality factor, Q:** Q quantifies the degree of frequency selectivity of a circuit and is related to the ratio of stored to dissipated energy:
$$Q=2\pi\left(\frac{W_{stor}}{W_{diss}}\right)\Bigg|_{\omega=\omega_0}$$
> $W_{stor}$ = maximum energy stored for $\omega=\omega_0$; $W_{diss}$ = energy dissipated during one period $T=2\pi/\omega_0$.

- Q "applies actually to any resonant circuit... and particularly to the resonant part of the circuit" [0:23:24]. Energy is stored in $L$ and $C$ and dissipated in $R$ [0:24:31].
- He did not derive it ("it's in the book") [0:31:22]. **Board:** "One can show (Ulaby et al, Sec. 9-4-1) for the RLC series circuit that"
$$\boxed{Q=\omega_0\frac{L}{R}=\frac{\omega_0}{B}}$$
- **Board:** "high quality factor Q $\Longleftrightarrow$ narrow bandwidth B in general." The "key... part of this relationship is the quality factor being inversely proportional to the bandwidth... very generally true of resonant systems" [0:32:47].
- Application [0:33:44]: in communications you "pick out a range of frequencies", and high-Q (low-loss) resonant structures are how you do it.
- In §6 [1:12:17] he adds the equivalent form $Q=\dfrac1R\sqrt{\dfrac{L}{C}}$.

> [!check] Verified: $\omega_0L/R=\omega_0/(R/L)=\frac1R\sqrt{L/C}$ (python, random values). **No board error.**

### 5. Bode plots of the bandpass by constituent factors [0:34:11–0:58:48]
(PS8 9.26 warning above applies.)

**Factorization (f_0145)** [0:34:47]:
$$\tilde H(\omega)=\frac{j\omega RC}{1-\omega^2LC+j\omega RC}=\underbrace{(RC)}_{\tilde A_1}\;\underbrace{(j\omega)}_{\tilde A_2}\;\underbrace{\left(\frac{1}{1+j\omega RC-\omega^2LC}\right)}_{\tilde A_3}$$
A blue annotation maps $-\omega^2LC$ to $\left(\dfrac{j\omega}{\omega_p}\right)^2$. That gives "**$\tilde H(\omega)$ has a zero @ origin and a quadratic pole at $\omega_p=\dfrac{1}{\sqrt{LC}}=\omega_0$.**" [0:36:15–0:37:08]

**Why adding works** (board, f_0159): "To obtain the Bode plot for $\tilde H(\omega)$, construct plots for $\tilde A_i(\omega)$ and combine by adding. This works because $M(\omega)$ is plotted on a log scale, and $\phi(\omega)$ appears in an exponent." Spoken [0:38:25–0:39:09]: "the log of a product is the sum of the logs", and "when we multiply the phase factors together, then that corresponds to adding the phases together."

**Factor plots.** Every panel has $M(\omega)$ [dB] on the left and $\phi(\omega)$ on the right against a log-$\omega$ axis.

| Factor | Magnitude [dB] | Phase | His reasoning |
|---|---|---|---|
| $\tilde A_1=RC$ (constant) | Horizontal line, drawn **below** 0 dB | $0^\circ$ flat | "typical values... one kilo-ohm... one microfarad... that's gonna be less than one" [0:39:50]. $RC>0$, so the phase is 0. |
| $\tilde A_2=j\omega$ (zero at origin) | Straight line, **+20 dB/decade**, crossing 0 dB at $\omega=1$ | $+90^\circ$ flat | "no inherent frequency scale... at a frequency of one... the log... gives us zero" [0:41:26]. "for every factor of 10 change in the frequency, we get a 20 dB change" [0:42:13]. Phase $=\angle j$. |
| $\tilde A_3$ (quadratic pole at $\omega_0$) | 0 dB for $\omega<\omega_0$, then **−40 dB/decade** | $0^\circ$ below $0.1\omega_0$, a straight line through $-90^\circ$ at $\omega_0$, $-180^\circ$ above $10\omega_0$ | As $\omega\to0$, $A_3\to1$ (0 dB). As $\omega\to\infty$, $A_3\to1/(-\omega^2LC)$, which falls 100× per decade = −40 dB/dec [0:45:32–0:46:19]. At $\omega_0$, $A_3=1/(j\omega_0RC)$, so $-90^\circ$. $\angle(-1)$ "we can take to be minus 180 degrees" [0:47:44–0:48:44]. |

> [!note] Added context
> $1\ \text{k}\Omega\times1\ \mu\text{F}=10^{-3}$ s, so $20\log_{10}(RC)=-60$ dB (python). He drew the level without a number, and the dB value depends on the unit of $RC$, as he hedged: "in the appropriate units".

**Combining: magnitude** [0:50:14–0:53:10] (f_0360 → f_0466):
- **Below $\omega_0$:** flat (A1) + flat (A3) + up 20 (A2) = **+20 dB/decade**.
- **Above $\omega_0$:** flat + up 20 − 40 = **−20 dB/decade** ("again, we just add the slopes").
- **Level:** "Remember we saw way back here at omega naught, the magnitude of the transfer function is one... zero dB" [0:51:28–0:51:41]. He scrolled back to the p04 sketch and anchored the vertex at (ω0, 0 dB).
- **Drawn plot:** a triangle with its apex at (ω0, 0 dB), a +20 dB/decade left leg and a −20 dB/decade right leg. "This also shows that the functionality we have is a bandpass filter... with the maximum at $\omega=\omega_0$" [0:53:14].

> [!warning] Vertex level: [board differs] from a literal sum of the factor asymptotes (not acknowledged)
> If you add the three factor asymptotes as drawn, the vertex at $\omega_0$ sits at $20\log_{10}(\omega_0RC)$. Since $\omega_0RC=R\sqrt{C/L}=1/Q$ (sympy), that is **$-20\log_{10}Q$ dB**. It equals 0 dB **only when $Q=1$**. For $Q=10$ the asymptotes meet at −20 dB, while the true curve reaches 0 dB at $\omega_0$ (the quadratic-pole resonance lifts it by $20\log Q$). His 0 dB vertex comes from the exact $|H(\omega_0)|=1$, not from the asymptote sum. A student asked exactly this [0:53:35], and he answered that it was a "shortcut" and that the overall scale factor "gives you a magnitude of one at the resonant frequency... that's sort of what we did anyway" [0:53:58–0:54:38]. That holds for the exact curve, not for the asymptotes.
> **Exam handling:** compute the vertex as the asymptote sum $20\log|K|+\dots$ evaluated at $\omega_0$. If the true value differs (resonant peak), mark it separately as $|H(\omega_0)|$ and say which number is which. Check the graders' convention against the posted PS8 solutions once released.

**Combining: phase** [0:54:49–0:56:33]. Axis ticks $0.1\omega_0$, $\omega_0$, $10\omega_0$; levels $+90^\circ$, $0$, $-90^\circ$.
- $\omega<0.1\omega_0$: $0+90+0=+90^\circ$
- $\omega=\omega_0$: $0+90-90=0^\circ$
- $\omega>10\omega_0$: $0+90-180=-90^\circ$
- Drawn: flat at $+90^\circ$, a straight line from $(0.1\omega_0,90^\circ)$ through $(\omega_0,0)$ to $(10\omega_0,-90^\circ)$, then flat.

> [!warning] Board error, acknowledged: the third tick was first written as "$\omega_0$" (f_0384; spoken "point one omega naught, omega naught, and omega naught" [0:55:07]). A student flagged it at [0:57:24]; corrected to **$10\,\omega_0$** ("You're right. Thank you." [0:57:40]).

**Comparison with the early sketch** [0:56:40–0:57:17]: the Bode plots are "very consistent" with the p04 sketches, "but the Bode plots kind of make linear approximations to the different ranges of behavior." ("This is the disadvantage of working on a tablet rather than on the board": no side-by-side view.)

**Why $\omega_p=\omega_0$ is no coincidence** [0:58:10]: "that pole is what gives you the peak... it ends up being a quadratic pole because it's second order. Right? You have the RLC."

> [!check] Verified: $\angle A_3(\omega_0)=-90^\circ$ and $\angle H(\omega_0)=0$ exactly; $\angle H=\pm45^\circ$ at the cutoffs, consistent with the straight-line phase.

> [!note] Added context (standard form, mine): since $RC=1/(Q\omega_0)$,
> $$\tilde H=\frac{\dfrac{1}{Q}\dfrac{j\omega}{\omega_0}}{1+\dfrac1Q\dfrac{j\omega}{\omega_0}+\left(\dfrac{j\omega}{\omega_0}\right)^2}$$
> This form shows the constant directly: the numerator asymptote is $1/Q$ at $\omega_0$, which is where the $-20\log Q$ vertex comes from.

### 6. Example: series-RLC highpass (output across $L$) [0:58:48–1:20:43]
Board title (f_0467): **"Example: high-pass filter"**. "We will have time to start this but not to finish it, today" [0:58:51].

**Circuit (f_0467):** $\tilde V_s$ on the left (+ top). The top wire carries $R$, then $C$, to a node. $L$ goes from the node to the bottom wire, and the node continues to the + output. Output $\tilde V_L$ is across $L$ (+ top). This is "the same circuit that we had before, except that we've exchanged the resistor and the inductor" [0:59:42].

**Filter type by limits** (board) [1:00:02]: "$\tilde Z_L=j\omega L\to0$ as $\omega\to0$, and $\tilde Z_L\to\infty$ as $\omega\to\infty$, so this circuit should make sense intuitively as a high-pass filter." Spoken: by voltage division, $v_L$ is small at low frequency and large at high frequency.

**Resonance** (board): "Circuit has a resonant frequency $\omega_0=1/\sqrt{LC}$ since $\omega_0L=1/(\omega_0C)\Rightarrow\tilde Z_L+\tilde Z_C$ cancel out at $\omega=\omega_0$." [1:01:23–1:02:25]

**Transfer function** (f_0478, f_0482) [1:02:51–1:05:02]:
$$\tilde V_L=\frac{\tilde Z_L}{\tilde Z_R+\tilde Z_C+\tilde Z_L}\tilde V_s=\frac{j\omega L}{R+\frac{1}{j\omega C}+j\omega L}\tilde V_s$$
$$\tilde H(\omega)=\frac{\tilde V_L}{\tilde V_s}=\frac{j\omega L}{R+\frac1{j\omega C}+j\omega L}\left(\frac{j\omega C}{j\omega C}\right)=\frac{-\omega^2LC}{1-\omega^2LC+j\omega RC}$$
(He multiplied by $j\omega C/j\omega C$ "to get rid of this fraction that we have in the denominator". The denominator is "as we had before".)

**Magnitude** [1:05:29]:
$$M(\omega)=\frac{\omega^2LC}{\sqrt{(1-\omega^2LC)^2+\omega^2R^2C^2}}$$

**Phase, the quadrant trap** [1:06:20–1:11:46]. "Here, it's a little bit tricky. There are two different expressions that we're gonna have to use." Phase = phase(num) − phase(den).
- Numerator $-\omega^2LC$: phase $180^\circ$ ("we have the minus one here").
- Denominator, $\omega<\omega_0$: Re $>0$, Im $>0$, so the **1st quadrant**. The calculator $\tan^{-1}$ is correct.
- Denominator, $\omega>\omega_0$: Re $<0$, Im $>0$, so the **2nd quadrant**. "If you were to... use your calculator... it'll give you an angle in the fourth quadrant... in reality, it should be up here in the second quadrant... add a 180 degrees." The $+180^\circ$ from the numerator and this $+180^\circ$ cancel [1:09:09–1:10:44].
- **Board sketch:** complex plane with "$\phi_{denom}$, $\omega>\omega_0$" in the upper-left (2nd) quadrant and "$\phi_{denom}$, $\omega<\omega_0$" in the upper-right (1st).
$$\phi(\omega)=\begin{cases}180^\circ-\tan^{-1}\!\left(\dfrac{\omega RC}{1-\omega^2LC}\right) & \omega<\omega_0\\[6pt]-\tan^{-1}\!\left(\dfrac{\omega RC}{1-\omega^2LC}\right) & \omega>\omega_0\end{cases}$$
- General rule [1:11:17]: "since the inverse tangent is typically defined as a function that... has a range of minus 90 degrees to plus 90 degrees, then if the actual correct phase is not within that range, then you're gonna have to add or subtract a 180 degrees to get the right phase."

> [!check] Verified (python3): the piecewise $\phi$ matches $\angle H$ for all $\omega$ (max error $3\times10^{-14}$ deg). **No board error.** Example (mine, normalized $x=\omega/\omega_0=2$, $Q=1$): the denominator is $-3+j2$; the calculator gives $\tan^{-1}(2/-3)=-33.69^\circ$ but the true angle is $146.31^\circ$. So $\phi=180-146.31=+33.69^\circ$. The naive $180-(-33.69)=213.69^\circ$ is wrong.

**$Q$ and the value at resonance** [1:11:51–1:13:51]:
$$Q=\omega_0\frac{L}{R}=\frac{1}{R}\sqrt{\frac{L}{C}},\qquad M(\omega_0)=\frac{\omega_0^2LC}{\omega_0RC}=\omega_0\frac{L}{R}=Q$$
"The magnitude of the transfer function at the resonant frequency... is equal to $\omega_0L/R$... that's actually equal to $Q$."

**Magnitude sketch versus $Q$** (f_0560/f_0564) [1:13:52–1:18:12]: linear $M$ against $\omega$, with a dashed line at $M=1$ and a dashed vertical at $\omega_0$. All three curves start at 0 ($\omega^2$ in the numerator) and approach **1** at high $\omega$ (both $\omega^2LC$ terms dominate).
- **Red, "low $Q<1$"** (large R): monotonic rise, passing $M=Q<1$ at $\omega_0$, then approaching 1 from below.
- **Green, "moderate $Q>1$":** a modest peak just above 1 near $\omega_0$, then settling to 1.
- **Blue, "high $Q\gg1$"** (very small R): "a sharp and quite high peak" at about $\omega_0$, then decaying to 1.

> [!warning] Board error, acknowledged: the axis is labelled "**$M(\omega)$[dB]**" and he said "we're plotting the magnitude... in dB" [1:13:52], but the ticks are linear (0 and 1). When a student asked about approaching "zero decibels", he said "Oh, sorry. **This is not decibels.** This is just..." [1:19:56]. The "[dB]" label was never erased (still in f_0567). **Read it as linear $M$.**

> [!note] Added context (mine, verified with python): the HP magnitude has a peak only if $Q>1/\sqrt2\approx0.707$. The peak is at $\omega/\omega_0=1/\sqrt{1-1/(2Q^2)}$ (slightly **above** $\omega_0$) with value $Q/\sqrt{1-1/(4Q^2)}$. So the monotone "low $Q<1$" curve is exact only for $Q\le0.707$. For $Q=0.9$, $M$ overshoots to 1.082 at $1.62\,\omega_0$, even though $M(\omega_0)=0.9<1$. For $Q=10$ the peak is $10.01$ at $1.0025\,\omega_0$, so "peak at $\omega_0$, height $Q$" is accurate for high Q.

**Phase sketch** [1:18:13–1:19:19] (f_0567): levels $180^\circ$, $90^\circ$, $0^\circ$. The curve starts at $180^\circ$, passes $90^\circ$ at $\omega_0$ (tick label cut off in the frame; spoken "This is omega naught") and approaches $0^\circ$. "It doesn't have that sort of special behavior near the resonant frequency."

**Closing Q&A** [1:19:28–1:20:43]: the magnitude "can actually approach [1] from either side" as $\omega\to\infty$. A small R gives a resonant gain that is "arbitrarily high but finite. But then as you make it higher, it'll be more narrow... that's sort of the characteristic behavior of resonant systems generally." Class ended "slightly long"; the HP Bode plots continue Wednesday.

> [!note] Added context (his next step, not done in this lecture): in Bode form,
> $$\tilde H_{HP}=\frac{(j\omega/\omega_0)^2}{1+\frac1Q\frac{j\omega}{\omega_0}+\left(\frac{j\omega}{\omega_0}\right)^2}$$
> That is a double zero at the origin (+40 dB/dec) times a quadratic pole at $\omega_0$ (−40 dB/dec). The asymptotes are +40 dB/dec up to 0 dB at $\omega_0$, then flat at 0 dB; the true value at $\omega_0$ is $20\log Q$ dB. The asymptotic phase is $180^\circ$, then a straight line from $0.1\omega_0$ to $10\omega_0$ down to $0^\circ$. Verify against the 10/28 lecture.

---

## Ed Yu's conventions & notation

| Item | His convention (this lecture) |
|---|---|
| Phasors, impedances, $H$ | **Under-tilde**: $\underset{\sim}{H}(\omega)$, $\underset{\sim}{V}_s$, $\underset{\sim}{Z}_L$, and the factors $\underset{\sim}{A}_i(\omega)$. (Written $\tilde X$ in this note.) |
| Magnitude / phase names | $M(\omega)=\lvert\tilde H(\omega)\rvert$ and $\phi(\omega)$ |
| Resonance | $\omega_0=1/\sqrt{LC}$, defined as where the input (Thevenin) impedance is purely real. Pole frequency $\omega_p$, here $=\omega_0$. |
| Cutoffs | $\omega_{c1}<\omega_{c2}$, generic $\omega_{ci}$; defined by $M=1/\sqrt2$ (on a peak-normalized response with max 1). Also called "corner or cutoff frequencies". |
| Bandwidth | $B=\omega_{c2}-\omega_{c1}$, in rad/s |
| Quality factor | $Q=2\pi\,(W_{stor}/W_{diss})\rvert_{\omega_0}$; $W_{stor}$ = **maximum** stored energy at $\omega_0$; $W_{diss}$ = energy dissipated in one period $T=2\pi/\omega_0$ |
| Bode magnitude | $M(\omega)$ [dB] $=20\log_{10}M$ against $\omega$ on a log axis; slopes in "dB/decade"; the vertical axis is drawn at "some small value of $\omega$", **not** $\omega=0$ |
| Bode phase (quadratic) | Straight line over **two decades**: ticks $0.1\omega_0$, $\omega_0$, $10\omega_0$; flat outside |
| Factor names | "constant factor", "zero at the origin", "quadratic pole", labelled $A_1, A_2, A_3$ under braces |
| Standard quadratic form | Writes the $-\omega^2LC$ term as $(j\omega/\omega_p)^2$ to read off $\omega_p$ |
| $\angle(-1)$ | Picks $\pm180^\circ$ for continuity: $-180^\circ$ for $A_3$ at high $\omega$, $+180^\circ$ for the HP numerator |
| $\tan^{-1}$ | Principal range $(-90^\circ,90^\circ)$; add or subtract $180^\circ$ when Re < 0 |
| Order of work | Circuit → $H$ by voltage division → clear fractions → limits and value at $\omega_0$ → **linear "sketch"** → $M$, $\phi$ formulas → cutoffs/B/Q → **Bode by factors** → compare with the sketch |
| Ink colours | Green for curves, blue for annotations, red/green/blue for the three Q cases |

---

## Intuition & explanations he gives

- **Which form to use for the phase:** use the rationalized form "because the denominator here is real... we don't have to worry about that" [0:03:52]. Phase of numerator minus phase of denominator "would actually be a little bit trickier" [0:04:42] (quadrant issue, shown at 1:09).
- **Resonance definition:** "the frequency at which the input impedance... the Thevenin equivalent impedance between the input terminals... [is] purely real" [0:05:29–0:06:05]; for the series RLC, "the impedance of the inductor and the impedance of the capacitor will cancel each other out" [0:07:05].
- **Sketch before Bode:** "not make the Bode plots yet, but do a slightly better sketch of the magnitude and the phase" [0:07:31], from the limits $\omega\to0$, $\omega_0$, $\omega\to\infty$.
- **Bandwidth and R:** "if the resistance is small, the bandwidth is very narrow... very selective... If the resistance is large... it'll pick out a wide range of frequencies" [0:21:41–0:22:12].
- **Loss and selectivity:** "only the resistor is going to be dissipating power... if it dissipates very little power, then perhaps in some way that corresponds to having a very narrow bandwidth... that correlation is true under quite general circumstances" [0:22:20–0:23:09].
- **Real impedance is not the same as no stored energy:** "the impedance is real, but that does not mean that there's no energy that is stored... the energy is gonna go back and forth between the inductor and the capacitor" [0:27:02–0:27:18].
- **How to build a high-Q filter:** "if you wanna have a very fine frequency filter, what you want is to make the loss as low as possible... the loss is associated with the resistance" [0:28:04–0:28:13].
- **Q needs both L and C:** with only one storage element, "it'll always be something that's exponentially decaying... you won't be able to get a structure where you can have energy stored that's just kind of oscillating back and forth... you have to have something that has this kind of resonant behavior" [0:28:41–0:29:58].
- **Q is inversely proportional to B in general:** "very generally true of resonant systems... high quality factor... related in a quite fundamental way to having a narrow bandwidth" [0:32:47–0:33:37].
- **Why Bode factors add:** "the log of a product is the sum of the logs" (magnitude); "the phase appears in an exponent in each factor... multiply the phase factors together... corresponds to adding the phases" [0:38:25–0:39:09].
- **Zero at the origin:** "there's no inherent frequency scale to that", so it crosses 0 dB at $\omega=1$ [0:41:26].
- **Why −40 dB/decade:** "it's omega squared... decrease by a factor of 100... If it decreased by a factor of 10... that would be 20 dB per decade" [0:46:01–0:46:19].
- **Combining lines:** "when we add lines... we can just add the slopes" [0:51:13].
- **Bode is approximate:** "the Bode plots kind of make linear approximations to the different ranges of behavior" [0:57:08].
- **The pole gives the peak:** "that pole is what gives you the peak... it ends up being a quadratic pole because it's a second order" [0:58:10].
- **Highpass by inspection:** $Z_L\to0$ at low $\omega$ means a small $v_L$ "by voltage division", and $Z_L\to\infty$ at high $\omega$ means a large output [1:00:06–1:00:52].
- **The HP resonant gain equals Q:** a large R gives $Q<1$; "you can always make it sufficiently small that the quality factor is greater than one"; a very small R gives "a sharp and quite high peak" [1:15:48–1:17:47]. The gain is "arbitrarily high but finite... as you make it higher, it'll be more narrow" [1:20:21].

---

## Emphasis & exam intel

1. **PS8 scope** [0:00:31] (board item 2): "the eighth problem set will be mostly on passive and active filter circuits." Due Mon 11/9, two days before SE2.
2. **SE2 logistics** [0:00:40]: "in about two and a half weeks... the second semester exam... That'll be on November 11... the last exam before the final... I'll post more detailed information... later this week."
3. **Exam algebra is vetted** [0:16:03–0:16:38]: "before we actually give the exam, we work through the problems... to make sure that... they're doable in the time for the exam... it won't be kind of arbitrarily complicated."
4. **Bode axis on exams** [0:43:24]: "if you're drawing this on a problem set or an exam... and you have omega on a log scale, you can draw it... pretty much like it's been drawn here... that vertical axis is not going through omega equal to zero."
5. **Quadrant rule** [1:11:17]: "since the inverse tangent is typically defined as a function that has a range of minus 90 degrees to plus 90 degrees... you're gonna have to add or subtract a 180 degrees to get the right phase... this is a circumstance where you actually have to do that."
6. **The key relationship** [0:32:47]: "the quality factor being inversely proportional to the bandwidth... very generally true of resonant systems."
7. **Bode method statement** (board, f_0159): "construct plots for $A_i(\omega)$ and combine by adding. This works because $M(\omega)$ is plotted on a log scale, and $\phi(\omega)$ appears in an exponent." This is a ready-made P1 justification.
8. **Four roots, keep two** [0:18:43–0:19:59]: discard the negative cutoffs and label $\omega_{c1}<\omega_{c2}$.
9. **Corrections he accepted in class** [0:57:40, 1:19:56]: $10\omega_0$ tick; "This is not decibels."
10. **Reading named:** Ulaby et al. §9-4-1 (Q of the series RLC).

---

## Student questions

| t | Question (reconstructed) | His answer |
|---|---|---|
| 0:15:41 | Will most transfer functions simplify this conveniently? | "It'll depend on the circuit." Exam problems are worked through beforehand so they are doable in the time, and "won't be kind of arbitrarily complicated." |
| 0:26:36 | At resonance the impedance is purely real, so is the stored energy zero? (?) | No. A real impedance doesn't mean no stored energy; energy sloshes between L and C. Low R means little dissipation, which means high Q. A follow-up confirms: overall Z is real, the internal reactances still store energy, and they cancel. |
| 0:28:32 | Does resonance make sense without both L and C? | No. First-order circuits only decay exponentially, so there is no Q for a lone C, RC or RL. Resonance can come from parasitics or a larger system. |
| 0:30:10 | (Follow-up from a student with "real life" Q experience, garbled (?)) | Q applies to anything with resonant behavior. If a C or RC alone seemed to have a Q, the resonance came from elsewhere (parasitics or the surrounding system). |
| 0:42:41 | On a log-ω axis ω never reaches 0, so where should the line stop near the vertical axis? | The vertical axis is drawn at "some presumably small frequency", not ω = 0. Draw it as shown on problem sets and exams. |
| 0:53:35 | The constant term doesn't change the slopes but moves the magnitude up and down, so how do you place it if you only add factor plots? | He "took a little shortcut" and used $\lvert H(\omega_0)\rvert=1$ from earlier. Otherwise you would "plug in numerical values... or by some other method deduce... the overall scale factor". (See the vertex warning in §5: the asymptote sum gives $-20\log Q$, not 0 dB.) |
| 0:57:24 | The third phase tick should be $10\omega_0$. | "You're right. Thank you." Corrected. |
| 0:57:58 | Is it a coincidence that $\omega_0=1/\sqrt{LC}$ equals the pole frequency? | No. The quadratic pole gives the peak, and it is quadratic because the RLC is second order. "There are fundamental reasons." |
| 1:19:28 | The HP magnitude approaches 1; is that approaching 0 dB from below? | It "can actually approach from either side." Then: "This is not decibels" (label correction). |
| 1:20:10 | So a small R gives an arbitrarily high transfer voltage? | "Arbitrarily high but finite," and narrower as it gets higher; that is characteristic of resonant systems. |

---

## Exam relevance

**P3 (filter transfer function + cutoff + Bode plots): HIGH. This lecture is the P3 method end to end for a passive RLC.** Voltage-division $H$ → clear fractions → $M$, $\phi$ (quadrant-safe) → $M=1/\sqrt2$ cutoffs → factorization into constant / zero at origin / quadratic pole → factor Bode plots → add. The TA's "Bode plots in your sleep" applies to every row of the §5 factor table. Practise drawing the factor rows and the sum until you can do them without thinking, and label slopes, ticks ($0.1\omega_0$, $\omega_0$, $10\omega_0$) and levels.

**P4 (active or RLC filter: H in factored standard form, filter type, Bode, design ratio): HIGH for the RLC branch, NONE for the op-amp branch.** The RLC branch covers the factored form $(RC)(j\omega)\big/(1+j\omega RC-\omega^2LC)$, the filter type from limits, and $Q$ or $B=R/L$ as the "design ratio". The op-amp branch is not in this recording.

**P1 (four conceptual short answers): MEDIUM–HIGH for the filter-concept half.** Ready stems:
- *Define Q and relate it to bandwidth / selectivity.* $Q=2\pi W_{stor}/W_{diss}$ at $\omega_0$; high Q ⟺ narrow B; low loss means high Q.
- *Why can't an RC or RL circuit have a Q / resonance?* Only one storage element, so there is no oscillatory exchange and only exponential decay.
- *At resonance $Z_{in}$ is real; is stored energy zero?* No, it oscillates between L and C.
- *Why do Bode factors add?* $\log$ of a product = sum of logs; phases add in the exponent.
- *Why is this circuit a highpass/bandpass?* Impedance limits in the voltage divider.
- *Why must you correct $\tan^{-1}$ by $180^\circ$?* Principal range $\pm90^\circ$; Re < 0 means the 2nd or 3rd quadrant.
- Semiconductor-physics half: **nothing in this lecture.**

**P2 (passive filter design or max power transfer): MEDIUM.** Design relations: $\omega_0=1/\sqrt{LC}$, $B=R/L$, $Q=\omega_0L/R=\frac1R\sqrt{L/C}$. Given a centre frequency and bandwidth you can pick R, L, C. Max power transfer: not covered.

**Likely question variants this lecture prepares you for:**
1. A series RLC with the output across R, L or C: find $H$, name the filter, find $\omega_0$ and $M(\omega_0)$.
2. A bandpass: derive $\omega_{c1}$, $\omega_{c2}$, $B$, $Q$; sketch linear $M$ and $\phi$ with $B$ marked.
3. A Bode magnitude and phase from a factored $H$ with a constant, a zero at the origin and a quadratic pole (labelled slopes, 0.1/1/10 ticks).
4. A highpass phase at $\omega>\omega_0$, testing the $180^\circ$ quadrant correction.
5. Sketch the HP $M$ for $Q<1$, $Q>1$, $Q\gg1$ and state $M(\omega_0)=Q$.
6. Conceptual: Q definition, Q–B inverse relation, why only R dissipates.

---

## Common mistakes / traps

1. **Calculator $\tan^{-1}$ in the wrong quadrant.** When Re(den) < 0 (e.g. $1-\omega^2LC<0$ above $\omega_0$), add $180^\circ$ to the denominator angle. Equivalently, use the rationalized form when its real part is positive (as for the bandpass). Example: HP at $\omega=2\omega_0$, $Q=1$ gives $+33.7^\circ$, not $213.7^\circ$ or $-146.3^\circ$.
2. **Keeping the wrong cutoff roots.** There are 4 sign combinations; keep $+\sqrt{\cdot}$ with $\mp R/2L$, check that both are positive, and label $\omega_{c1}<\omega_{c2}$.
3. **Assuming $\omega_0$ is the arithmetic midpoint of the cutoffs.** It is the geometric mean: $\omega_{c1}\omega_{c2}=\omega_0^2$ (added context).
4. **Quadratic pole slope:** $-40$, not $-20$ dB/decade. Its phase spans **two decades** ($0.1\omega_0\to10\omega_0$) and a total of $-180^\circ$, passing $-90^\circ$ at $\omega_0$.
5. **The vertex level of a combined Bode plot.** Adding the asymptotes gives $20\log(\omega_0RC)=-20\log Q$ dB at $\omega_0$ for this bandpass, not 0 dB unless $Q=1$. Label which number you mean.
6. **dB vs linear axes.** His HP sketch is linear despite the "[dB]" label. On an exam, never mix "1" and "0" ticks with a dB label: 1 is 0 dB, and $M\to0$ is $-\infty$ dB.
7. **"Low Q < 1 means no peak."** For the HP (and LP) second-order response, peaking starts at $Q>1/\sqrt2$, not at $Q>1$ (added context).
8. **Drawing the Bode vertical axis as $\omega=0$.** On a log axis it is some small $\omega$.
9. **The sign of $\angle(-1)$.** Choose $+180^\circ$ or $-180^\circ$ so the phase curve is continuous with the other factors (he used $-180^\circ$ for $A_3$ and $+180^\circ$ for the HP numerator).
10. **"Resistance of the inductor"** (his slip, 1:03:25): it is the impedance $j\omega L$; keep the language exact in P1 answers.
11. **Citing this lecture for op-amp filters.** It has none.

---

## Self-check

1. For the lecture's series-RLC bandpass (output across $R$), give $M$ and $\phi$ at $\omega_0$, $\omega_{c1}$ and $\omega_{c2}$, and state $B$ and $Q$ symbolically.
> [!question]- Answer
> $M(\omega_0)=1$, $\phi(\omega_0)=0^\circ$; $M(\omega_{c1})=M(\omega_{c2})=1/\sqrt2$, with $\phi(\omega_{c1})=+45^\circ$ and $\phi(\omega_{c2})=-45^\circ$. $B=R/L$; $Q=\omega_0L/R=\omega_0/B=\frac1R\sqrt{L/C}$. (All verified with python3 over 2000 random R, L, C.)

2. Series-RLC highpass (output across $L$), normalized $x=\omega/\omega_0=2$ and $Q=1$, so $H=\dfrac{-x^2}{1-x^2+jx/Q}$. Find $|H|$ and $\angle H$, and say what a careless calculator answer would be.
> [!question]- Answer
> Denominator $=-3+j2$, $|{\rm den}|=\sqrt{13}$, so $|H|=4/\sqrt{13}=1.109$. The calculator gives $\tan^{-1}(2/-3)=-33.69^\circ$, but the denominator is in the 2nd quadrant: $146.31^\circ$. $\angle H=180^\circ-146.31^\circ=\mathbf{+33.69^\circ}$, which matches his $\omega>\omega_0$ branch $-\tan^{-1}\!\big(2/(-3)\big)$. Careless: $180-(-33.69)=213.69^\circ$. (Verified with python3. Note $|H|>1$ here: for $Q=1$ the HP response peaks above 1, at $\sqrt2\,\omega_0$ with height $1.155$.)

3. For the bandpass $H=(RC)(j\omega)\big/(1+j\omega RC-\omega^2LC)$, where do the straight-line magnitude asymptotes meet, in terms of $Q$, and what is the true $|H|$ there?
> [!question]- Answer
> They meet at $\omega_0$ at the level $20\log_{10}(\omega_0RC)$. Since $\omega_0RC=R\sqrt{C/L}=1/Q$, the level is $-20\log_{10}Q$ dB. The true value is $|H(\omega_0)|=1$ (0 dB). They coincide only for $Q=1$. Example: $Q=10$ gives asymptotes meeting at −20 dB and the true curve at 0 dB. (Verified with sympy. His board drew the vertex at 0 dB.)

4. (P1 style.) Define the quality factor and explain why a series RC circuit has no meaningful Q, while a series RLC at resonance has a large Q when R is small, even though its input impedance is purely real there.
> [!question]- Answer
> $Q=2\pi\,W_{stor,max}/W_{diss\,per\,cycle}$ at $\omega_0$. An RC (or RL) has one storage element, so its natural response only decays exponentially, with no oscillatory energy exchange and no resonance. In the RLC at $\omega_0$, $Z_L$ and $Z_C$ cancel in the *sum*, but each still stores energy, which oscillates between L and C. Only R dissipates, so a small R makes $W_{diss}$ small and Q large. For the series RLC, $Q=\omega_0L/R=\omega_0/B$, so a high Q means a narrow bandwidth.

5. Why may Bode plots of the factors simply be added, and what is the combined slope of the bandpass above $\omega_0$?
> [!question]- Answer
> The magnitude is plotted as $20\log_{10}|\cdot|$, and the log of a product is the sum of the logs. Each factor's phase sits in an exponent, $|A_i|e^{j\phi_i}$, so multiplying the factors adds the phases. Above $\omega_0$: constant (0) + zero at origin (+20) + quadratic pole (−40) = **−20 dB/decade**. Below $\omega_0$ it is +20 dB/decade.

---

## Board-error audit

> [!summary] Board-error audit
> Every formula on the board was re-derived with python3/sympy: the bandpass $H$, $M$, $\phi$, $\omega_0$, $\omega_{c1,2}$, $B$, $Q$; the factorization; the HP $H$, $M$, piecewise $\phi$ and $M(\omega_0)=Q$. **All correct.** Issues:
> 1. **Phase tick "$\omega_0$" instead of $10\omega_0$** (0:55:07): caught by a student, corrected at 0:57:40.
> 2. **HP magnitude axis labelled "[dB]" with linear ticks** (1:13:52): acknowledged verbally at 1:19:56 ("This is not decibels"); the label was never erased.
> 4. **HP "low $Q<1$" curve drawn monotone** (1:16:23): it is monotone only for $Q\le1/\sqrt2$. Minor. [board differs]
> 5. **Speech slips:** "quadratic zero" for the pole (0:46:52); "90 degrees at omega naught" for $A_3$, which is $-90^\circ$ (0:49:16); "series resistance" and "resistance of the inductor" for impedance (1:03:14–1:03:25).
> 6. **ASR only:** "plus (or?) l c" = $+4LC$ (0:17:56); "You'll be at all" = Ulaby et al.; "omega nod/dot", "w zero b zero" = $\omega_0$.
>
> **Audio gaps:** none beyond the low-confidence spans in QUALITY.md. All are fillers ("if", "as", "I...") with no lost math. Student questions are off-mic and partly garbled (0:26:39, 0:30:10, 0:42:41, 1:19:28).
