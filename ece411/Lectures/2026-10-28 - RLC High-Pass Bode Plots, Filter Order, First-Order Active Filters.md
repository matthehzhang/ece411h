---
course: ECE 411H
date: 2026-10-28
instructor: Prof. Ed Yu
topic: Factor-by-factor Bode plots of the series-RLC high-pass (output across L); limitation of straight-line Bode plots near resonance; filter order; passive vs active filters; active first-order low-pass and high-pass (inverting op amp, H = −Zf/Zs)
reading: Ulaby/Maharbiz/Furse 3e §9-6, §9-7 (active filters; board says "Ulaby et al., Secs. 9-6, 9-7"). The first half continues the passive-filter material from the previous lectures; no section was named for it today.
source: Recordings/2026-10-28-active-filters-cont (transcript + 28 distinct tablet pages from 96 page-final frames; 1 page black)
tags: [ece411, lecture, filters, bode-plot, filter-order, active-filter, op-amp, exam2]
source_quality:
  - "Speech: Deepgram Nova-3, 79 min audio, 9156 words, mean utterance confidence 0.96. 78 words < 0.55 (0.9 %). 9 utterances < 0.7, all filler ('and', 'so', 'that', 'back')."
  - "Spoken math is transcribed as words, and ASR symbols, subscripts and signs are guesses. Every equation here comes from the board and was cross-checked with speech and sympy."
  - "Board: tablet, 28 distinct pages (71 of 96 page-final frames are scroll/extension states). The handwriting renders 180 as '188' and −90 as '−98'; speech confirms 180/−90."
  - "Screen share dropped 1:08:40–1:09:12, so page 27 (f_0587) is a black frame. Speech gaps at 1:07:58–1:08:55 and 1:09:03–1:09:22."
  - "Frames end at 1:16:48 (f_0619). The active-HP phase curve drawn 1:16:48–1:17:22 is reconstructed from speech only."
  - "Audio ends mid-sentence at 1:18:46 ('Oh, so the final, it will be'). A remark about the final exam is lost."
  - "Student questions are off-mic and fragmentary. Reconstructions are marked (?)."
---

# 2026-10-28: RLC High-Pass Bode Plots, Filter Order, First-Order Active Filters

## Summary

- **Factor-by-factor Bode plot of a second-order RLC filter.** Write $H$ as a constant × $(j\omega)^n$ × a quadratic pole. Draw the magnitude (dB) and phase of each factor, then add the slopes and the phases. For the series-RLC high-pass $H=\dfrac{-\omega^2LC}{1+j\omega RC-\omega^2LC}$ the result is **+40 dB/dec below $\omega_0$, 0 dB above**, with phase **180° → 90° (at $\omega_0$) → 0°**.
- **Settle the ±180° ambiguity of a quadratic pole by evaluating at $\omega=\omega_0$.** There the factor equals $1/(j\omega_0RC)$, which is −90°, so the pole goes 0° → −90° → **−180°**.
- **Know the limitation.** Straight-line Bode plots do not depend on Q. The true $|H|$ near $\omega_0$ can peak sharply for high Q (low R). *(Added context, verified: for this HP, $|H(\omega_0)|=Q$.)*
- **Filter order (his definition):** "the absolute value of the highest power of ω in the dominant behavior of $H(\omega)$ when ω is in the filter stop band." A series RLC with output across R is first order in each stopband (±20 dB/dec). Output across L gives second order (+40 dB/dec). Each +1 in order adds ±20 dB/dec.
- **Active vs passive:** active filters "contain components that can generate power and therefore gain, e.g., op amps." They give passband gain and a load-independent output, and they can be cascaded without the signal shrinking.
- **Inverting op-amp filter recipe:** lump the input branch into $Z_s$ and the feedback branch into $Z_f$. KCL at the virtual-ground node gives $H=-Z_f/Z_s$. Factor this into a constant × simple zero/pole and draw the Bode plots directly.
- **Active first-order LP** ($R_s$ in, $R_f\|C_f$ feedback): $H=-\dfrac{R_f}{R_s}\dfrac{1}{1+j\omega R_fC_f}$. Passband $20\log(R_f/R_s)$, $\omega_0=1/(R_fC_f)$, −20 dB/dec, phase 180° → 90°. **$\omega_0$ does not depend on $R_s$, and $V_{out}$ does not depend on $R_L$.** *(This is the Lab 5 topology and is graded; see the warning in §7.)*
- **Active first-order HP** ($R_s+C_s$ in series at the input, $R_f$ feedback): $H=\dfrac{-j\omega R_fC_s}{1+j\omega R_sC_s}$, $\omega_0=1/(R_sC_s)$. It rises at +20 dB/dec to a passband of $20\log(R_f/R_s)$, with phase −90° → −180°.
- **Board error (0:26–0:30):** adding a "+20 dB/dec then flat" factor to the RLC high-pass does **not** produce a bandpass. Every factor's slope persists above its own corner, so the result is a steeper high-pass (+60/+20/0).
- **Scope intel:** PS8 problems 1–5 are Exam 2 material, and problem 6 (transform math) is not. The next lecture covers **cascaded filter stages**, which is how you get higher order.

---

## Content

### 0. Announcements [0:00:03–0:01:49]
Board text is from f_0003 (a Zoom dialog covers the page-final frame).
- Office hours **today 1:00–2:30 PM** instead of 10:30–11:55 AM, still in EER 3.802.
- **PS8 was posted this morning, due Mon 11/9/2026.** It "covers primarily passive and active filter circuits." In speech: "Except for the sixth problem ... which has to do with some of the mathematics associated with transforms. So **the first five problems on that problem set will be on material that'll be included on the upcoming exam**." [0:00:44–0:01:05]
- PS7 is due 9:00 AM Central, Mon 11/02/2026.
- **Semester Exam 2: in person, in class, Wed 11/11/2026.** A detailed announcement will follow, covering the rules, "which will be basically the same as the rules for the first exam," and "the material for which you'll be responsible." [0:01:15–0:01:41]

### 1. Recap: series-RLC high-pass (output across L) [0:01:54–0:07:11]
**Circuit (f_0003/f_0021):** $\tilde V_s$ (± with + on top) sits on the left edge. The top wire runs through $R$ and then $C$ to the output node. $L$ shunts from the output node to the bottom wire. The output $\tilde V_L$ is taken across $L$, + at top and − at bottom. (He describes it as the "RLC series circuit with the output voltage taken across the inductor.")

From last lecture, by voltage division (f_0021/f_0046):
$$\tilde H(\omega)=\frac{\tilde V_L}{\tilde V_s}=\frac{-\omega^2LC}{1-\omega^2LC+j\omega RC},\qquad M(\omega)=|\tilde H|=\frac{\omega^2LC}{\sqrt{(1-\omega^2LC)^2+\omega^2R^2C^2}}$$
$$\phi(\omega)=\begin{cases}180^\circ-\tan^{-1}\!\left(\dfrac{\omega RC}{1-\omega^2LC}\right)&\omega<\omega_0\\[6pt]-\tan^{-1}\!\left(\dfrac{\omega RC}{1-\omega^2LC}\right)&\omega>\omega_0\end{cases}\qquad \omega_0=\frac{1}{\sqrt{LC}},\quad Q=\omega_0\frac{L}{R}=\frac1R\sqrt{\frac LC}$$
- Phase nuance [0:02:36]: two expressions are needed "because the real part of the denominator of the transfer function changes sign at the pole frequency," and $\tan^{-1}$ alone loses the quadrant.
- **Exact plots (f_0092), linear axes.** $M(\omega)$ starts at 0 at the origin and approaches 1 (dashed) at high ω. The blue curve, "$Q\gg1$", has a tall narrow peak near $\omega_0$. The green curve, "$Q\gtrsim1$", has a small bump. The red curve, "$Q<1$", rises monotonically to 1. $\phi(\omega)$ is one green curve, 180° → 90° at $\omega_0$ → 0°.
- High Q means "low loss, so low resistance in the filter." Q mainly changes the behavior near $\omega_0$, "although it doesn't have as much effect on the behavior at very low or very high frequencies." [0:03:37–0:04:02]

> [!check] Verified (sympy/python): $Z_L/(Z_R+Z_C+Z_L)$ equals the board $H$. The piecewise $\phi$ equals $\arg H$ at six test frequencies on both sides of $\omega_0$. $\phi(\omega_0)=90^\circ$. **No board error.**

> [!note] Added context (mine, verified numerically): $|H(\omega_0)|=Q$ exactly. A peak above 1 exists only for $Q>1/\sqrt2$, and it sits slightly **above** $\omega_0$, at $\omega_0/\sqrt{1-1/(2Q^2)}$ (Q=1 gives $1.414\,\omega_0$ with peak 1.155; Q=5 gives $1.010\,\omega_0$). The board's "Q<1, no peak" label is a loose sketch, because for 0.707<Q<1 a small peak exists.

Q&A on Q intuition [0:04:07–0:07:06]: see Student questions.

### 2. Bode plots of the RLC high-pass, factor by factor [0:07:13–0:24:10]
Board heading: **"Bode plots for high-pass filter:"**. Method [0:07:44]: "take the transfer function and kind of break it apart into the fundamental factors whose behaviors we know how to plot, and then ... put those together."

#### 2a. Factorization [0:08:14–0:10:26] (f_0106)
$$\tilde H(\omega)=\underbrace{(LC)}_{\tilde A_1(\omega)}\;\underbrace{(j\omega)^2}_{\tilde A_2(\omega)}\;\underbrace{\left(\frac{1}{1+j\omega RC-\omega^2LC}\right)}_{\tilde A_3(\omega)}$$
Board: **"$\tilde H(\omega)$ has a 2nd order zero @ origin and a quadratic pole @ $\omega_p=\dfrac{1}{\sqrt{LC}}=\omega_0$."** The pole frequency equals "the resonant frequency of the RLC series circuit." [0:09:27–0:10:15]

#### 2b. $A_1=LC$, the constant [0:10:33–0:11:38] (f_0127)
- Magnitude (dB): a horizontal line. He drew it **below** 0 dB without labelling a value. *(Not said: $20\log_{10}(LC)<0$ for practical L, C.)*
- Phase: "The constant factor is l times c. So that's gonna be positive, so the phase will be zero." Board: "$\phi=0$."

#### 2c. $A_2=(j\omega)^2$, the second-order zero at the origin [0:11:40–0:13:58] (f_0141, f_0166)
- Magnitude axes: $M(\omega)$[dB] with "0dB" on the horizontal axis and a "40dB" tick on the vertical, with ω ticks **1, 10, 100**. "Since it's a zero at the origin, it doesn't have any inherent frequency scale, so we'll just call the frequencies one, 10, a 100." It is 0 dB at ω=1.
- Slope: "every time we have ... a factor of 10 increase in the frequency, the magnitude of that factor goes up by 10 squared ... which is a 100, which is 40 dB." The plot is a straight line through (1, 0 dB) at **+40 dB/decade**.
- Phase: "it's j omega the quantity squared. So that's minus omega squared. So the phase is just the phase of minus one, which is a 180 degrees. And it's independent of frequency." A horizontal line at 180°.

> [!check] $20\log_{10}|(j\omega)^2|$ = 0, 40, 80 dB at ω = 1, 10, 100 (python). ✓

#### 2d. $A_3$, the quadratic pole [0:14:16–0:19:13] (f_0196, f_0223)
- Low ω: "this factor will go to one because omega going to zero will get rid of these terms." So **0 dB, 0°**.
- High ω: "this quadratic term ... will dominate. So this is going to go as basically one over minus omega squared LC." A factor of 10 in ω divides the magnitude by 100, so **−40 dB/decade**. The phase is that of −1, "either plus or minus a 180 degrees."
- **Choosing the branch** [0:18:07]: "To determine which one of those possibilities we should use, we can look at what happens when omega is equal to omega naught." At $\omega_0$, $1-\omega_0^2LC=0$, so $A_3=\dfrac{1}{j\omega_0RC}$. "We have a j in the denominator that has a phase of minus 90 degrees." So "at very high frequencies, it'll make more sense ... to take the phase to be **minus 180 degrees**."
- **Plot to redraw.** Magnitude: flat on 0 dB up to the $\omega_0$ tick, then a straight drop labelled "−40dB/decade". Phase: ticks at $0.1\omega_0$, $\omega_0$, $10\omega_0$; 0° up to $0.1\omega_0$, a straight line through −90° at $\omega_0$ to −180° at $10\omega_0$, then flat at −180° (dashed reference at −180°).

> [!check] sympy: $A_3(\omega_0)=-j\sqrt{L/C}/R=-jQ$, phase −90°. ✓

#### 2e. Add the factors [0:19:23–0:24:10] (f_0310, f_0311)
**Magnitude.** "Basically add them together":

| Region | $A_1$ | $A_2$ | $A_3$ | **Total** |
|---|---|---|---|---|
| $\omega<\omega_0$ | 0 | +40 | 0 | **+40 dB/dec** |
| $\omega>\omega_0$ | 0 | +40 | −40 | **0 dB/dec** |

Level [0:21:30–0:22:23]: as $\omega\to\infty$, "the quadratic pole here will go as one over minus omega squared LC. These other two factors ... also minus omega squared LC," so $H\to1$, which is **0 dB**. **Plot to redraw:** under a "⇓" arrow, $\tilde H(\omega)$ with $M(\omega)$[dB] axes. A green line rises at "40dB/decade" to meet 0 dB at $\omega_0$, then runs flat along 0 dB. (He relabelled the axis end: "This is omega... not omega naught," 0:22:59.)

**Phase** [0:23:02–0:24:03]: "adding up these three constituent phases. So zero degrees, a 180 degrees, and this function here ... shifted upward by a 180 degrees. So instead of going from zero to minus one eighty, it'll go from 180 degrees to zero." **Plot:** axes 0°, 90°, 180° (dashed at 180°), with ticks $0.1\omega_0$, $\omega_0$, $10\omega_0$. The line is flat at 180° up to $0.1\omega_0$, falls linearly through 90° at $\omega_0$ to 0° at $10\omega_0$, then stays flat at 0°.

> [!check] python (ω0=1, Q=1): slope +40.00 dB/dec at $10^{-3}\omega_0$ and 0.00 at $10^3\omega_0$. Limit $H\to1$. Exact phase 90° at $\omega_0$. **No board error.**

### 3. Limitation of straight-line Bode plots [0:24:20–0:25:42]
"When we constructed the Bode plots ... using the linear approximations ... we didn't get any sort of unusual behavior near the pole frequency... **the shape of this is independent of the quality factor.**" The actual transfer function, by contrast, shows "quite different behavior right in the vicinity of the pole or resonant frequency depending on what the quality factor ... is." So "one of the limitations of the linear approximation version of the Bode plots is that it doesn't capture these types of variations in the behavior near the resonant frequency, but it does capture quite well ... the limiting behaviors at low and high frequencies."

### 4. Q&A: adding more factors, and a board error [0:25:45–0:30:32]
A student asked how to handle several zeros and poles at different frequencies (e.g. $\omega_0$ and $\omega_1$, all in terms of L, R, C). His answer: same method, "working them out would be more complicated." You might have "an additional factor ... something rising at a slope of ... 20 dB per decade and then leveling off" (red sketch, f_0388: a line rising into the 0 dB axis at a red tick $\omega_1$, then flat). Combine factors "in the same way."

What he then said and drew (red, on the composite $H$ plot, f_0394), with $\omega_1>\omega_0$:
- Below $\omega_0$: "another kind of 20 dB per decade contribution ... So this would go up at **60 dB per decade**." (Correct.)
- Between $\omega_0$ and $\omega_1$: "you have minus 40 dB per decade plus 20 dB per decade ... minus 20 dB per decade."
- Above $\omega_1$: "the slope would go to minus 40 dB per decade."
- Conclusion: "**it would be a bandpass filter** ... You could exercise more control over the width of the passband by choosing omega naught and omega one appropriately." For $\omega_1<\omega_0$ he said it is "still ... bandpass behavior, but this slope would only be 20 dB per decade."

> [!warning] **Board/speech error, [board differs].** The middle and high-frequency slopes are wrong because they drop the **+40 dB/dec of $A_2=(j\omega)^2$, which persists at all frequencies**. Correct slopes for $H\cdot\dfrac{j\omega/\omega_1}{1+j\omega/\omega_1}$:
>
> | Region | $A_2$ | $A_3$ | extra factor | **Total** |
> |---|---|---|---|---|
> | $\omega<\omega_0$ | +40 | 0 | +20 | **+60** |
> | $\omega_0<\omega<\omega_1$ | +40 | −40 | +20 | **+20** (board: −20) |
> | $\omega>\omega_1$ | +40 | −40 | 0 | **0** (board: −40) |
>
> python ($\omega_0=1,\ \omega_1=100$): 60.0, 19.2, 0.0 dB/dec. The result is a **steeper high-pass, not a bandpass**. With $\omega_1<\omega_0$ it is +60, +40, 0, also a high-pass. To get a bandpass from this HP you need a **falling** factor $1/(1+j\omega/\omega_1)$ with $\omega_1>\omega_0$. That gives +40, 0 (flat passband), −20 (python: 40.0, −0.8, −20.0).
>
> **Lesson for P3:** write a slope table, one column per factor, and carry every factor's slope into all regions above its corner.

Follow-up [0:29:04]: how would you know whether $\omega_1>\omega_0$ when everything is symbolic? (a) You are given values. (b) It is a design problem: "Design a circuit that has these characteristics, then you would have to select values such that ... $\omega_1$ was greater than $\omega_0$." (c) Otherwise, state the cases: "depending on whether $\omega_1$ is less than or greater than $\omega_0$ ... you could get different types of behavior." He framed the choice as "a trade off of what do you value more" (steepness vs a level passband).

### 5. Filter order [0:30:37–0:46:35]
Board heading **"Filter order:"** (f_0399, f_0416). Motivation: filters so far had stopband slopes of 20 or 40 dB/dec, or steeper as in §4. The slope "depends on the power to which the frequency is taken ... in the transfer function. It's 20 dB per decade if it's a linear, or inverse linear, function of omega. It's 40 dB per decade if it's omega squared or one over omega squared." [0:31:18–0:31:47]

Board statements (f_0416):
1. **"For zeros or poles, the steepness of the frequency response increases as the order of the zero or pole increases."** ("The order is essentially the exponent.")
2. **"For a filter as a whole, the order of the filter is the absolute value of the highest power of ω in the dominant behavior of $\tilde H(\omega)$ when ω is in the filter stop band."** "So the order is always a positive number." [0:33:15–0:34:26] He conceded: "there's a whole bunch of prepositional phrases in there."

#### Example 1: series-RLC band-pass (output across R) [0:34:38–0:39:38] (f_0425, f_0433)
**Circuit:** $\tilde V_s$ on the left. The top wire runs through $L$ then $C$ to the output node. $R$ runs from the output node to the bottom wire, and $\tilde V_R$ is across $R$ (+ top).
$$\tilde H(\omega)=\frac{j\omega RC}{1+j\omega RC-\omega^2LC}$$
(He said "ω² L squared ... sorry, LC". The board is correct.) The passband is centered on $\omega_0=1/\sqrt{LC}$, the resonant frequency.
- Board: "stopbands are $\omega\ll\omega_0$, $\omega\gg\omega_0$."
- $\omega\ll\omega_0$: the denominator goes to 1, so $\tilde H\approx j\omega RC$, giving **first order** (+20 dB/dec).
- $\omega\gg\omega_0$: the denominator goes as $-\omega^2LC$, so $\tilde H\approx\dfrac{R}{j\omega L}$, giving **first order** (−20 dB/dec). "The part of this that matters ... is ... the single power of omega in the denominator."
- Board: "Bode plots for the band pass filter showed $M(\omega)$ has slope of ±20dB/decade in stop bands." "Plus or minus 20 dB per decade is what you get for first order filter." [0:38:52]

> [!warning] Adjacent to PS8 9.26 (series RLC bandpass parameters): graded work. The lecture only restates $H$ and its order. The tutor must not use this to compute 9.26's parameters.

> [!check] sympy: $Z_R/(Z_R+Z_C+Z_L)$ equals the board $H$. $\lim_{\omega\to0}H/(j\omega RC)=1$ and $\lim_{\omega\to\infty}H/\big(R/(j\omega L)\big)=1$. ✓

#### Example 2: series-RLC high-pass (output across L) [0:39:47–0:46:35] (f_0442, f_0452, f_0460)
$$\tilde H(\omega)=\frac{-\omega^2LC}{1+j\omega RC-\omega^2LC}$$
- "We only have one stopband, and it is at low frequencies." Board: "stop band is $\omega\ll\omega_0$:" and "$\omega\ll\omega_0$: $\tilde H(\omega)\approx-\omega^2LC\Rightarrow$ **second-order**."
- Board: "Bode plots showed $M(\omega)$ has slope +40dB/decade in stop band."
- The passband is $\omega\gg\omega_0$, "where the transfer function approaches a constant and approaches one."
- Generalization [0:46:17]: "a slope of plus or minus 40 dB is what you get if you have a second order circuit ... **you'll get an additional plus or minus 20 dB in that slope every time you increase the order by one**, because you're increasing the power of omega by one."
- The Q&A on what "ω ≪ ω0" means [0:42:16–0:45:28] is under Student questions.

> [!note] Added context: many texts call the series-RLC bandpass a "second-order" filter because its denominator is quadratic. Ed Yu's definition is per stopband and gives "first order". On his exam, use his definition and show the stopband asymptote that justifies it. If the question is ambiguous, say which definition you are using.

### 6. Active filters: definition and motivation [0:46:40–0:50:28]
Board (f_0466, f_0476):
- **"Active Filters." Reading: Ulaby et al., Secs. 9-6, 9-7.**
- **"Active filters contain components that can generate power and therefore gain, e.g., op amps."**
- **"Op amp and other active filter circuits can be cascaded to improve gain, frequency response, or other characteristics."**

Speech: passive filters have "no circuit components that can give you gain, such as a transistor, or, in our case, an op amp." With only passive parts, "if you cascade multiple units ... you'll lose some voltage every time ... it'll get to be quite small." With active filters "you can build that signal level back up, or you can have amplification combined with filtering." [0:47:10–0:48:32] The op amp is the only gain device in this course so far; "When you get to a course like ECE 438, then you'll learn about how transistors can do this as well." [0:49:13]

### 7. Example: active first-order low-pass filter [0:50:28–1:07:15]

> [!warning] = Lab 5 (first-order active inverting LP of Fig 5.0; R1, R2, C correspond to $R_s$, $R_f$, $C_f$ here): graded work. The tutor must not use this as a walkthrough or a check. It is also adjacent to PS8 (inverting op amp with R1‖C1 input and R2‖C2 feedback): the same $-Z_f/Z_s$ method applies, and the tutor must not extend this example to that circuit. What follows records the lecture only. No solution of mine is added.

**Circuit (f_0484), "a variant on just the simple inverting amplifier."** $\tilde V_s$ (± to ground) connects through a series resistor $R_s$ to the op amp's **inverting (−)** input. The **non-inverting (+)** input is grounded. The feedback network is $R_f$ **in parallel with** $C_f$, connected between the − input node and the op-amp output. $\tilde V_{out}$ is taken at the op-amp output (+) with respect to ground. Blue dashed loops group $R_s$ as **$\tilde Z_s$** (the "impedance of ... the input signal") and $R_f\|C_f$ as **$\tilde Z_f$** (the "impedance of the feedback loop").

**Impedances** [0:53:00–0:54:07]:
$$\tilde Z_s=R_s,\qquad \tilde Z_f=\frac{R_f\cdot\frac{1}{j\omega C_f}}{R_f+\frac{1}{j\omega C_f}}\cdot\frac{j\omega C_f}{j\omega C_f}=\frac{R_f}{1+j\omega R_fC_f}$$
(The $j\omega C_f/j\omega C_f$ multiplier is written in green.)

**KCL at the inverting node** [0:54:19–0:56:10]. By the ideal-op-amp rules, the + input is grounded, so the − input is also at 0 V. Taking the current leaving to the left as $(0-\tilde V_s)/\tilde Z_s$ and the current leaving up and to the right as $(0-\tilde V_{out})/\tilde Z_f$, and with zero current into the op amp:
$$\frac{-\tilde V_s}{\tilde Z_s}-\frac{\tilde V_{out}}{\tilde Z_f}=0\;\Longrightarrow\;\tilde V_{out}=-\frac{\tilde Z_f}{\tilde Z_s}\tilde V_s$$
"Which should look familiar to you because that's basically the result that we got for the inverting op amp amplifier circuit."

**Transfer function** [0:56:19–0:57:57]:
$$\tilde H(\omega)=\frac{\tilde V_{out}}{\tilde V_s}=-\frac{\tilde Z_f}{\tilde Z_s}=-\frac{R_f}{R_s}\underbrace{\left(\frac{1}{1+j\omega R_fC_f}\right)}_{\text{simple pole @ }\omega_0=1/(R_fC_f)}$$
It is a constant times a simple pole. "This is simple enough that we can just essentially get [the Bode plot] directly" without plotting each factor separately [0:58:06].

**Bode plots** [0:58:23–1:01:45] (f_0550/f_0551):
- *Magnitude.* For $\omega\ll\omega_0$ the denominator goes to 1, so $|H|\to R_f/R_s$, a flat line at **$20\log(R_f/R_s)$** (drawn above 0 dB). For $\omega\gg\omega_0$ the factor goes as $1/(j\omega R_fC_f)$, "and the key part of that is that it goes as one over omega," giving **−20 dB/decade**. Redraw: flat at $20\log(R_f/R_s)$ up to a dash-dot vertical at $\omega_0$, then a straight drop labelled "−20dB/decade", crossing the 0 dB axis to the right of $\omega_0$.
- *Phase.* Ticks at $0.1\omega_0$, $\omega_0$, $10\omega_0$, with 0°, 90° (dashed) and 180° marked. Low ω: "we have the phase of minus one, which we'll take to be a 180 degrees." High ω: "the relevant factor is the j in the denominator ... an additional contribution of minus 90 degrees," giving **90°**. Redraw: flat at 180° up to $0.1\omega_0$, linear down to 90° at $10\omega_0$, then flat.
- Takeaways [1:01:45–1:02:29]: first order because of "this minus 20 dB per decade slope corresponding to the linear dependence on omega." As an active filter it can have passband gain "substantially greater than one or zero dB," and "that can be engineered into the design of the filter by selecting the feedback and series resistances."

> [!check] sympy: $R_f\|(1/j\omega C_f)=R_f/(1+j\omega R_fC_f)$. Solving the KCL equation gives $-Z_f/Z_s$. $H$ matches the board. python ($R_f/R_s=10$): 20.00 dB at $10^{-3}\omega_0$, 16.99 dB and 135.0° at $\omega_0$, 95.7° at $10\omega_0$, slope −20.0 dB/dec. **No board error.**

**Q&A: steeper slope via cascading** [1:02:34–1:05:08] (see Student questions). Build "another copy of this same circuit and use this $V_{out}$ in the role of $V_s$." Because "the output of an op amp in the ideal op amp model can basically act as an ideal voltage source," the second copy contributes "another factor like this in the transfer function." No buffer is needed between two such stages. A buffer may be needed after a passive network, because "this resistance here [$R_s$]" would interact with it.

> [!warning] Adjacent to PS8 (active LP design: gain 4, 1 kHz, −60 dB/dec) and PS8 P9.39 (two-stage RC with buffer): graded work. The cascade remarks above are recorded as lecture content only. The tutor must not turn them into a design or buffer walkthrough for those problems.

**Board "Note:" (f_0572, f_0583)** [1:05:09–1:07:15]:
1. **"$\omega_0$ doesn't depend on $R_s$."** If a "realistic voltage source, represented by a voltage source in series with a resistance" drives the filter, "we would change the gain, but not the pole frequency." (He first said "resonant frequency" and corrected himself to "pole frequency".)
2. **"$\tilde V_{out}$ will be unchanged for any load resistance $R_L$ connected to $\tilde V_{out}$."** This is because "the output signal of the circuit is at the output of the op amp."
3. **"op-amp can provide gain in filter pass band."**

### 8. Example: active first-order high-pass filter [1:07:19–1:18:00]
The screen share failed during the setup (1:07:58–1:09:44, black frame f_0587). The circuit below is from f_0589/f_0592.

> [!warning] Adjacent to PS8 (inverting op amp with R1‖C1 input and R2‖C2 feedback). This example's input is a *series* $R_s$–$C_s$, not R‖C, so it is not an exact collision. The tutor must not extend it into that problem's solution.

**Circuit:** same inverting structure. $\tilde V_s$ (± to ground) connects through **$R_s$ in series with $C_s$** to the inverting (−) input. The + input is grounded. **$R_f$ alone** forms the feedback path from the − input to the output. $\tilde V_{out}$ is taken at the output with respect to ground. Blue loops: $\tilde Z_s$ around $R_s$–$C_s$, $\tilde Z_f$ around $R_f$.

$$\tilde Z_s=R_s+\frac{1}{j\omega C_s},\qquad \tilde Z_f=R_f$$
"We can analyze this now in exactly the same way" [1:10:38]. KCL gives $\tilde V_{out}=-\dfrac{\tilde Z_f}{\tilde Z_s}\tilde V_s$, so:
$$\tilde H(\omega)=\frac{-R_f}{R_s+\frac{1}{j\omega C_s}}\cdot\frac{j\omega C_s}{j\omega C_s}=\frac{-j\omega R_fC_s}{1+j\omega R_sC_s}=-R_fC_s\;\frac{\overbrace{+j\omega}^{\text{simple zero @ origin}}}{\underbrace{1+j\omega R_sC_s}_{\text{simple pole @ }\omega_0=1/(R_sC_s)}}$$
(At 1:12:54 he said "minus... Or sorry. Plus $j\omega$". The board shows $+j\omega$.)

**Bode plots** [1:13:47–1:17:22] (f_0619; the phase curve comes from speech only):
- *Magnitude.* High ω: "this goes to just $j\omega R_sC_s$ ... the $j\omega$ here and the $j\omega$ here cancel out. The $C_s$ here and the $C_s$ here cancel out. So we're just gonna have minus $R_f$ over $R_s$." That gives a passband at **$20\log(R_f/R_s)$** (dashed level). Low ω: "the denominator goes to one, and we just have this $j\omega$ ... first order in omega," giving **+20 dB/decade**. Redraw: axes with ticks $0.1\omega_0$, $\omega_0$, $10\omega_0$. A line rising at "20dB/decade" meets the dashed $20\log(R_f/R_s)$ level at $\omega_0$ and then runs flat along it.
- *Phase.* Axes 0°, −90°, −180° (dashed at −180°), with ticks $0.1\omega_0$, $\omega_0$, $10\omega_0$. Low ω: "the denominator here is one ... the relevant factor is minus $j$. So that has a phase of **minus 90 degrees**." High ω ($>10\omega_0$): "we will have $j\omega$ over $j\omega R_sC_s$. So the $j$ here and the $j$ here will cancel out, and we just have the factor of minus one ... that will be **minus 180 degrees**." "The transition will look like this." Reconstructed (not captured on frames): flat at −90° up to $0.1\omega_0$, linear down to −180° at $10\omega_0$, then flat.
- Takeaway [1:17:35]: "because this is an active filter, then we can get gain in the passband that's determined from the design of the circuit. Right? $R_f$ over $R_s$ ... **That's the main distinction that you get from the active filter circuits compared to the passive filter circuits.**"

> [!check] sympy: all three forms of $H$ are equal, and $\lim_{\omega\to\infty}H=-R_f/R_s$. python ($R_s$=1 kΩ, $C_s$=100 nF, $R_f$=10 kΩ, so $\omega_0=10^4$ rad/s): −40.0 dB/−90.1° at $10^{-3}\omega_0$; 16.99 dB/−135.0° at $\omega_0$; 19.96 dB/−174.3° at $10\omega_0$; slope +20.0 dB/dec. **No board error.**

> [!note] Added context: in normalized standard form, $\tilde H=-\dfrac{R_f}{R_s}\cdot\dfrac{j\omega/\omega_0}{1+j\omega/\omega_0}$ (sympy-verified). This separates the passband gain ("design ratio" $R_f/R_s$) from the shape. His $-R_fC_s$ prefactor has units of seconds, so it is not itself the gain.

> [!note] Phase-sign bookkeeping: in §7 he took −1 as **+180°** (plot 180° → 90°). In §8 the factor $-j$ is −90°, which takes −1 as **−180°** (plot −90° → −180°). Both are correct mod 360°. Do not mix the two inside one plot.

### 9. Close and next time [1:18:04–1:18:46]
"What we will do next time is we will talk about **cascaded filter circuits**, which kind of gets back to the question ... how do you get higher order circuits? One way of doing that is cascading multiple stages together, and we'll see an example of how that works." The recording then cuts off: "Oh. Let me skip (?) the final. Oh, so the final, it will be". The remark (apparently about the final exam) is lost.

Sallen-Key, second-order active filters, band-reject/notch realizations, numerical design to a spec (gain/corner/roll-off), cascade math (only previewed in Q&A), a formal cutoff (−3 dB) definition, max power transfer, and semiconductor physics.

---

## Ed Yu's conventions & notation

| Item | His convention (this lecture) |
|---|---|
| Phasors / transfer function | Under-tilde: $\underset{\sim}{H}(\omega)$, $\underset{\sim}{V}_s$, $\underset{\sim}{V}_{out}$, $\underset{\sim}{Z}_s$, $\underset{\sim}{Z}_f$, and the factors $\underset{\sim}{A}_1(\omega)$, $\underset{\sim}{A}_2(\omega)$, $\underset{\sim}{A}_3(\omega)$. (Written $\tilde X$ in this note.) |
| Magnitude / phase | $M(\omega)=|H(\omega)|$; the dB axis is labelled "$M(\omega)$ [dB]" and uses $20\log(\cdot)$. Phase is $\phi(\omega)$ in degrees. Frequency is ω in rad/s throughout (no Hz). |
| Factor names | "constituent factors" / "fundamental factors" $A_1,A_2,A_3$, with braces under each factor of the product. |
| Pole/zero vocabulary | "simple pole @ $\omega_0=\dots$", "simple zero @ origin", "2nd order zero @ origin", "quadratic pole @ $\omega_p=\dots=\omega_0$". "Pole frequency" $\omega_p$ = "resonant frequency" $\omega_0$ for the RLC; he corrects himself when he says "resonant" for an RC pole. |
| Bode axes | Magnitude: a tick at $\omega_0$ (or 1, 10, 100 for a zero at the origin, which "doesn't have any inherent frequency scale"); slope label "±N dB/decade" with an arrow. Phase: ticks at $0.1\omega_0$, $\omega_0$, $10\omega_0$; transitions are straight lines over the two decades $0.1\omega_0$–$10\omega_0$. Dashed reference lines at the asymptotic phase values. |
| Phase of −1 | ±180° chosen per plot: +180° for the RLC HP $A_2$ and the active LP, −180° for the $A_3$ high-frequency limit and the active HP. The branch is decided by evaluating at $\omega_0$. |
| Colors | Green for Bode asymptotes and the rationalizing multipliers ($j\omega C/j\omega C$); red for hypothetical or extra factors; blue dashed loops grouping elements into $Z_s$, $Z_f$. Exact $M(\omega)$ curves are color-coded by Q (blue $Q\gg1$, green $Q\gtrsim1$, red $Q<1$). |
| Op-amp drawing | Inverting input (−) on top, (+) on the bottom tied to ground. $\tilde V_s$ is drawn with its − terminal to ground. $\tilde V_{out}$ is an open terminal pair at the output (+) against ground. |
| Op-amp analysis | Lump the input branch into $Z_s$ and the feedback branch into $Z_f$. KCL at the inverting node with **both currents written as leaving**: $(0-V_s)/Z_s+(0-V_{out})/Z_f=0$. Then $H=-Z_f/Z_s$. |
| Rationalizing | Multiply by $\dfrac{j\omega C}{j\omega C}$ to clear $1/(j\omega C)$ inside a fraction. |
| Order / bands | "stopband", "passband"; "$\omega\ll\omega_0$" ≈ more than a decade below. Order is always positive. |
| Q | $Q=\omega_0L/R=\frac1R\sqrt{L/C}$ (series RLC). |

---

## Intuition & explanations he gives

- **Why low R gives a high, narrow peak** [0:04:29–0:06:28]: "in the limit of zero resistance, all you have is the capacitor and the inductor ... you sort of get a blowup of the current ... infinitely high voltage ... there's nothing to disrupt that." A low R takes you "from sort of the infinite limit to some finite but high value." Width: "you only get that resonant behavior right at the resonant frequency. And if you move a little bit off of it ... the resistance will start knocking that down ... from a very high value, [so] it comes down more sharply." With high R, "that buildup of stored energy and therefore voltage in the capacitor and the inductor, it gets knocked down very quickly," and there is no peak.
- **Bode = add known pieces** [0:07:44]: break $H$ into factors "whose behaviors we know how to plot, and then we'll put those together."
- **No inherent scale for a zero at the origin** [0:12:10]: label the axis 1, 10, 100.
- **Decade arithmetic** [0:12:40]: ×10 in ω multiplied by $\omega^2$ gives ×100, which is 40 dB.
- **Picking ±180°** [0:18:07–0:19:05]: evaluate at $\omega_0$. The quadratic pole becomes $1/(j\omega_0RC)$ (−90°), so continuity makes the high-frequency value −180°.
- **Slopes cancel** [0:21:10]: above $\omega_0$ "the slopes of this factor and this factor will cancel each other out," giving a horizontal line.
- **Bode limitation** [0:24:20–0:25:42]: straight lines miss the Q-dependent behavior near resonance but "capture quite well ... the limiting behaviors at low and high frequencies."
- **Order = exponent** [0:31:34, 0:33:00]: slope ∝ the power of ω; "the order is essentially the exponent."
- **Compare like units** [0:42:43–0:43:12]: "you can only compare values that have the same units ... omega doesn't have the same units as R or C." The relevant comparison is $\omega_0=1/\sqrt{LC}$. "In any given circuit, the frequencies that will be relevant for comparison will generally be ... the nonzero pole or zero frequencies," and bands are "bounded by those frequencies or by zero or infinity."
- **"Much less than" ≈ one decade** [0:44:33–0:45:13]: "very roughly speaking, if you are an order of magnitude below or above, that's usually sufficiently much greater than or much less than," the same convention as the $0.1\omega_0$/$10\omega_0$ phase breakpoints, "not quite arbitrarily, but as the simplest generalization."
- **Why active** [0:47:52–0:48:32]: cascaded passive stages lose voltage each time; active stages "build that signal level back up," or combine amplification with filtering.
- **Same as the inverting amplifier** [0:52:11, 0:56:10]: replace the resistors by impedances $Z_s$, $Z_f$ and you get $-Z_f/Z_s$.
- **Virtual ground** [0:54:50]: the + input is at ground, so the − input "has to be the same, so it's zero as well." No current flows into the op amp.
- **Ideal op-amp output = ideal voltage source** [1:03:09, 1:04:09]: "you can, in principle, connect anything to $V_{out}$ here, and it won't change the output voltage." That is why stages cascade directly and why $R_L$ does not matter.
- **When a buffer is needed** [1:04:22–1:05:02]: if the preceding stage is a "more complicated passive circuit," then "you would have to worry about how this resistance here [$R_s$] interacted with the other things ... in the passive circuit," and "you would want to put ... a buffer" in between.
- **Source resistance in the LP** [1:05:30–1:05:56]: a realistic source adds series resistance, which changes the gain only, because $\omega_0=1/(R_fC_f)$ has no $R_s$.

---

## Emphasis & exam intel

1. **Exam 2 scope from PS8** [0:00:44–0:01:05]: "Except for the sixth problem on the problem set, which has to do with some of the mathematics associated with transforms. So **the first five problems on that problem set will be on material that'll be included on the upcoming exam.**" Passive and active filter problems are in. Transform math (Laplace prep, PS8 #6) appears to be **out**.
2. **Exam logistics** [0:01:15–0:01:41]: "semester exam two ... in person in class ... Wednesday, November 11." The rules "will be basically the same as the rules for the first exam." A detailed scope announcement is to be posted.
3. **Phase-branch rule** [0:18:07]: "To determine which one of those possibilities we should use, we can look at what happens when omega is equal to omega naught."
4. **Bode limitation** [0:25:15]: "one of the limitations of the linear approximation version of the Bode plots is that it doesn't capture these types of variations in the behavior near the resonant frequency." This is a ready P1 answer.
5. **Design framing** [0:29:29]: "you might be asked, okay. Design a circuit that has these characteristics, then you would have to select values such that ..." This points to P2/P4 design parts.
6. **Order definition** (board, f_0416) and "**the order is always a positive number**" [0:33:46].
7. **Slope–order rule** [0:38:52, 0:46:22]: "plus or minus 20 dB per decade is what you get for first order filter"; "**you'll get an additional plus or minus 20 dB in that slope every time you increase the order by one**."
8. **"Much less than"** [0:44:33]: "if you are an order of magnitude below or above, that's usually sufficiently much greater than or much less than."
9. **Active filter definition** (board) [0:48:41]: "Active filters contain components that can generate power and therefore gain, e.g., op amps."
10. **Gain is a design choice** [1:02:11–1:02:29]: passband gain "can be substantially greater than one or zero dB ... engineered into the design of the filter by selecting the feedback and series resistances." This is the P4 "design ratio".
11. **Three notes on the active LP** (board, f_0572/f_0583) [1:05:15–1:07:11]: $\omega_0$ is independent of $R_s$; $V_{out}$ is independent of $R_L$; the op amp gives passband gain.
12. **Main distinction** [1:17:51]: "That's the main distinction that you get from the active filter circuits compared to the passive filter circuits."
13. **Next lecture** [1:18:04]: "cascaded filter circuits ... how do you get higher order circuits? One way of doing that is cascading multiple stages together."
14. **Reading named:** Ulaby et al. §9-6, §9-7.
15. **Lost remark** [1:18:41]: "Oh, so the final, it will be". The audio ends there. Check Canvas for any final-exam announcement.

---

## Student questions

| t | Question (reconstructed) | His answer |
|---|---|---|
| 0:04:07 | Is there an intuitive reason why very high R gives a low resonance peak and very low R a high one? | With R → 0 only L and C remain, so the current and voltages "blow up" with nothing to limit them. Small R gives a finite but high peak. Off resonance, R knocks it down, and because it falls from a high value it falls sharply, so the peak is narrow. Large R damps the stored-energy buildup quickly, so there is no peak. |
| 0:06:31 | (Follow-up, partly garbled) The inductor voltage is $L\,di/dt$, and with low R the current swings hard, so $v_L$ is large? (?) | Agreed: "Because the current will be very high ... it kinda scales up with the current." |
| 0:25:45 | With several poles/zeros at different frequencies ($\omega_0$, $\omega_1$, in terms of L's, R's, C's), how do we build the Bode plot? | Same method, more work. Add each factor's straight-line plot. His example (a +20-then-flat factor at $\omega_1$) contained the slope error flagged in §4. |
| 0:29:04 | How would you know whether $\omega_1>\omega_0$, and by how much, if they are symbolic? | Use given values; or, in a design problem, choose values to get the wanted ordering; or state the cases ("depending on whether $\omega_1$ is less than or greater than $\omega_0$"). |
| 0:42:16 | Does "very low ω" mean $\omega RC\ll1$ (or ω times R, L, C ≪ 1)? | Compare only like units. Compare ω with $\omega_0=1/\sqrt{LC}$ (generally with the nonzero pole/zero frequencies). "Much less than" is roughly an order of magnitude, as in the $0.1\omega_0$/$10\omega_0$ phase convention. |
| 1:02:34 | How do you make the slope even greater, or get a higher magnitude? | Cascade: build another copy and use $V_{out}$ as the next stage's $V_s$. The ideal op-amp output acts as an ideal voltage source, so you get "another factor like this in the transfer function." This is covered next lecture. |
| 1:03:32 | (Follow-up) Can we just connect the stages directly, or do we need an op amp (buffer) in between? | For this configuration, no buffer is needed, because the op-amp output is unaffected by what it drives. After a passive filter you may need a buffer, because this stage's $R_s$ would load the passive network. |

---

## Exam relevance

**P1 (four conceptual short answers: filter concepts and semiconductor physics), medium-high.** Ready stems from this lecture:
- Define filter order and give the order of a series-RLC filter with output across R (first, in each stopband) or across L (second). Relate order to dB/decade.
- "What limitation do straight-line Bode plots have near resonance?" They are independent of Q and miss the resonant peak, while the asymptotes are accurate far from $\omega_0$.
- "What makes a filter active, and what does that buy you?" Gain, load-independent output and lossless cascading.
- "Why doesn't $\omega_0$ of the inverting active LP depend on the source resistance?" "Why is $V_{out}$ independent of $R_L$?"
- "Why does low R give a sharp, high resonance peak?" (Energy buildup and Q.)
- *Semiconductor physics:* **not covered in this lecture.** The TA's "semiconductor physics on the second exam" hint must be served by the 10-05/10-12/10-14 lectures.

**P2 (design/analysis: passive filter design or max power transfer), medium.** Passive RLC HP and BP transfer functions, stopbands and passbands, order. The design remark (choose values so that $\omega_1>\omega_0$) and the corrected §4 lesson on which added factor makes a bandpass. *Max power transfer: not covered here.*

**P3 (filter transfer function, cutoff and Bode plots), high, the core of the lecture.** The full factor-by-factor procedure: factorization, each factor's magnitude and phase, slope addition, the ±180° branch fixed at $\omega_0$, the composite plots, and the $0.1\omega_0$–$10\omega_0$ phase convention. The board error in §4 is exactly the kind of slip "Bode plots in your sleep" is meant to prevent. *A cutoff (−3 dB) definition was not given this lecture.*

**P4 (active op-amp or RLC filter: $H(\omega)$ in factored standard form, filter type, Bode plots, design ratio), high.** The $-Z_f/Z_s$ recipe. First-order LP and HP in factored form. Type from the $\omega\to0$ and $\omega\to\infty$ limits. Bode magnitude and phase including the 180° offset from the inversion. The design ratio $R_f/R_s$ sets the passband gain, and the R in the same branch as the C sets $\omega_0$. Second-order active (Sallen-Key) and cascades are **not** covered here; cascades come next lecture.

**Likely question variants this lecture prepares you for:**
1. Given a series-RLC filter with output across L (or R), factor $H$, draw each factor's Bode plot, and add them. State the order.
2. Given an inverting op-amp filter with some $Z_s$, $Z_f$, find $H=-Z_f/Z_s$ in factored standard form, name the type, draw the Bode plots, and give the passband gain in dB and $\omega_0$.
3. Choose $R_f/R_s$ for a specified passband gain and an RC product for a specified $\omega_0$.
4. Explain in words why the active version can have gain and a load-independent output, and why straight-line Bode plots miss the resonant peak.

---

## Common mistakes / traps

1. **Dropping a factor's slope above its corner.** This is exactly his §4 error (0:28): the $(j\omega)^2$ factor keeps contributing +40 dB/dec forever. Always tabulate the slope per region, one column per factor.
2. **Wrong ±180° branch.** For a quadratic pole, evaluate at $\omega_0$ (−90°), so the high-frequency limit is −180°, not +180°. Keep each phase plot continuous, and do not switch between +180° and −180° partway through a plot.
3. **Forgetting the inverting minus sign.** It shifts the whole phase plot by 180°. The active LP starts at 180°, not 0°. The active HP starts at −90°, not +90°.
4. **Order ≠ denominator degree.** The series-RLC bandpass has a quadratic denominator but is "first order" in each stopband by his definition. Show the dominant-term asymptote to justify the order.
5. **Comparing ω with R or C.** "ωRC ≪ 1" alone is not the criterion he wants. Compare ω with $\omega_0$; "≪" means about a decade.
6. **Reading the asymptote as the true value at the corner.** *(Added context, verified.)* A first-order factor is 3.01 dB below the asymptote at its corner, with phase ±45° from the endpoints (e.g. active HP: 16.99 dB, not 20 dB, and −135° at $\omega_0$). For the RLC HP the true value at $\omega_0$ is $20\log_{10}Q$ dB, not 0 dB.
7. **Pairing the wrong R with the C.** The corner comes from the R and C in the *same* impedance: $R_fC_f$ for the LP (feedback branch) and $R_sC_s$ for the HP (input branch). Passband gain is $R_f/R_s$ in both.
8. **Treating a prefactor as the gain.** In $-R_fC_s\cdot\dfrac{j\omega}{1+j\omega R_sC_s}$ the prefactor has units of seconds. The passband gain is $R_f/R_s$. *(Added context.)* Rewrite in normalized form $-\dfrac{R_f}{R_s}\cdot\dfrac{j\omega/\omega_0}{1+j\omega/\omega_0}$. The same applies to $(LC)(j\omega)^2$: the separate dB levels of $A_1$ and $A_2$ depend on units, and only the product is meaningful.
9. **Assuming every cascade needs a buffer.** Ideal op-amp outputs can drive the next inverting stage directly. Buffers matter after *passive* stages, whose output impedance the next stage's $R_s$ would load.
10. **Assuming source resistance never moves the corner.** That holds for the active LP (his Note 1). *(Added context, sympy-verified.)* In the active HP, a source resistance $R_{int}$ adds to $R_s$ in $Z_s$, so $\omega_0=1/((R_s+R_{int})C_s)$ moves and the gain becomes $R_f/(R_s+R_{int})$.

---

## Self-check

**1.** For $\tilde H(\omega)=\dfrac{-\omega^2LC}{1+j\omega RC-\omega^2LC}$, name the three factors, give each one's magnitude slope and phase, and give the composite asymptotes. Why does the quadratic pole's phase go to −180° rather than +180°?
> [!question]- Answer
> $A_1=LC$: constant level, 0°. $A_2=(j\omega)^2$: +40 dB/dec through 0 dB at ω=1, phase 180°. $A_3=1/(1+j\omega RC-\omega^2LC)$: 0 dB below $\omega_0$ and −40 dB/dec above, phase 0° → −90° at $\omega_0$ → −180° (straight line from $0.1\omega_0$ to $10\omega_0$).
> Composite: +40 dB/dec below $\omega_0$, flat at 0 dB above (since $H\to1$). Phase 180° → 90° at $\omega_0$ → 0°.
> At $\omega_0$ the factor equals $1/(j\omega_0RC)=-jQ$, which is −90°, so continuity forces −180° at high ω.
> Verified: sympy factorization, slopes +40.00/0.00 dB/dec, exact phase 90° at $\omega_0$.

**2.** (His §4 example, corrected.) Multiply that $H$ by $F(\omega)=\dfrac{j\omega/\omega_1}{1+j\omega/\omega_1}$ with $\omega_1=100\,\omega_0$. Give the slope in each region and the filter type. What factor would make a bandpass instead?
> [!question]- Answer
> Slopes: +60 dB/dec ($\omega<\omega_0$), +20 ($\omega_0<\omega<\omega_1$), 0 ($\omega>\omega_1$). This is a **high-pass**, third order in its stopband ($H\propto\omega^3$ at low ω), and **not** a bandpass. The board's −20/−40 dropped $A_2$'s +40.
> For a bandpass use $1/(1+j\omega/\omega_1)$ with $\omega_1>\omega_0$, which gives +40, 0 (flat passband), −20 dB/dec.
> Verified (python, ω0=1, ω1=100): 60.0, 19.2, 0.0 for $F$; 40.0, −0.8, −20.0 for the low-pass factor.

**3.** By Ed Yu's definition, what is the order of a series RLC filter (a) with output across R and (b) with output across L? Which stopband(s) do you inspect, and what is the dominant $H$ in each?
> [!question]- Answer
> (a) Two stopbands. For $\omega\ll\omega_0$, $H\approx j\omega RC$ (power 1). For $\omega\gg\omega_0$, $H\approx R/(j\omega L)$ (power −1, absolute value 1). So it is **first order**, with ±20 dB/dec.
> (b) One stopband, $\omega\ll\omega_0$, where $H\approx-\omega^2LC$. So it is **second order**, with +40 dB/dec.
> Verified: sympy limits of $H$ divided by each approximation → 1.

**4.** Active first-order HP with $R_s=1$ kΩ, $C_s=100$ nF, $R_f=10$ kΩ. Find $\omega_0$ (and $f_0$), the passband gain in dB, the asymptotic and exact $|H|$ and phase at $\omega_0$, and the asymptotic and exact phase at $0.1\omega_0$.
> [!question]- Answer
> $\omega_0=1/(R_sC_s)=10^4$ rad/s, so $f_0=1.59$ kHz. Passband $20\log_{10}(10)=20.0$ dB.
> At $\omega_0$: the asymptote reads 20 dB, the exact value is 16.99 dB (3.01 dB down), and the phase is −135°.
> At $0.1\omega_0$: the asymptotic phase is −90° and the exact phase is −95.7°. The magnitude asymptote is 0 dB and the exact value is −0.04 dB.
> Verified (python): $f_0=1591.5$ Hz; 16.990 dB; −135.00°; −95.71°.

**5.** Ed noted that in the active LP, $\omega_0$ does not depend on $R_s$, so a source resistance changes only the gain. Does that carry over to the active HP of §8? What happens if the source has internal resistance $R_{int}$, and does a load $R_L$ on $V_{out}$ change anything?
> [!question]- Answer
> No. In the HP, $Z_s=R_s+R_{int}+1/(j\omega C_s)$, so $H=\dfrac{-j\omega R_fC_s}{1+j\omega(R_s+R_{int})C_s}$. The corner moves down to $\omega_0'=1/((R_s+R_{int})C_s)$ and the passband gain drops to $R_f/(R_s+R_{int})$.
> $R_L$ changes nothing, because the ideal op-amp output acts as an ideal voltage source (his Note 2).
> Verified: sympy (added context; he did not discuss the HP case).

> [!warning] Board- and speech-error audit
> **One substantive error:** §4 (0:26:43–0:30:26). Adding a "+20 dB/dec then flat" factor at $\omega_1$ to the RLC high-pass was drawn and stated as +60 / −20 / −40 dB/dec, a "bandpass". The correct result is +60 / +20 / 0, a steeper high-pass (python-verified). He dropped the persistent +40 dB/dec of $(j\omega)^2$.
> **Everything else verified (sympy/python): no errors.** That covers the RLC HP $H$, $M$ and piecewise $\phi$, $Q$, the factorization, each factor's Bode plot, the composite plots, the BP stopband asymptotes, the LP and HP active $H$, and their Bode plots.
> **Spoken slips with a correct board:** "ω² L squared … LC" (0:35:36); "omega will go to one" (0:15:15); axis label ω₀ → ω (0:22:59); "resonant … pole frequency" (1:05:17); "minus … plus jω" (1:12:54); "log of RS … RF over RS" (1:15:03); "20 degrees … 20 dB per decade" (0:26:57).
> **ASR artifacts:** "five omega" = φ(ω); "quadratic pull"/"simple pull" = pole; "omega knot" = ω₀; "holes" = poles; "turns" = terms; "d I d two"/"IDT" = di/dt; "polar zero frequency" = pole or zero frequency; "Add very low frequencies" = At very low frequencies; "E R 3 Dot 802" = EER 3.802; "problem eight" = Problem Set 8.
> **Handwriting:** "188" = 180°, "−98" = −90°.
> **Capture gaps:** black frame at 1:08:40 (share dropped); the active-HP phase curve was not captured (speech-reconstructed); audio is cut at 1:18:46.
