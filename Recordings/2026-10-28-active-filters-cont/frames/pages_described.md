# 2026-10-28-active-filters-cont: page descriptions (frame + speech cross-check)

Method: DESCRIBE_FRAMES_PROMPT.md. All 28 page-final frames were viewed, along with the neighbouring frames named per page wherever the page-final frame was scrolled, occluded or blank. Confidence tags: `[sure]` means frame and speech agree or the frame is unambiguous; `[likely]` means one source only, legible; `[unclear]` means unreadable. Computations were re-derived in python3/sympy (scripts in the session scratchpad: verify.py, composite.py, q.py, extra.py).

Source paths: the inputs were read from `Recordings/2026-10-28-active-filters-cont/`. This file was written to the session worktree because a hook blocks writes to the base checkout.

Global caveats:
- Tablet capture. In his handwriting "180" often looks like "188" and "−90" like "−98". Speech confirms 180 and −90 every time, so this file writes 180°/−90° and does not flag them as board errors.
- The screen share stopped from 1:08:40 to 1:09:12 (lecture.chapter.vtt), so f_0587 is a black frame.
- Frames end at f_0619 (1:16:48). The active-HP phase curve drawn at 1:16:48–1:17:22 was **not captured** and is reconstructed from speech only.
- Audio ends mid-sentence at 1:18:46.

---

## p01  f_0002.jpg  [0:00:00 – 0:00:03]
A Zoom "This meeting is being recorded" dialog covers the centre. **Frame used for the text: f_0003.jpg (0:00:05)**, which shows the same page without the dialog.
**Topic:** "Class session notes - 2026_10_2(?)" / "Announcements:"  [sure for the visible part. The date is truncated, but the recording folder says 10-28.]
**Board:**
- 1. Office hours today 1:00–2:30 PM instead of 10:30–11:55 AM, still in EER 3.802.  [sure: f_0003 + speech 0:00:13–0:00:27]
- 2. Problem Set 8 was posted this morning and is due Monday 11/9/2026. It "covers primarily passive and active filter circuits."  [sure]
- 3. Reminder: Problem Set 7 is due 9:00 AM Central, Monday 11/02/2026.  [sure]
- 4. Reminder: Semester Exam 2 is in class on Wednesday 11/11/2026, with a detailed announcement to be posted later this week.  [sure]
- "From last time – high-pass filter"  [sure: f_0021]
**Diagram:** source $\tilde V_s$ (± symbol, + on top) on the left edge. The top wire carries a terminal circle, then $R$, then $C$ to a node. The inductor $L$ shunts from that node to the bottom wire. The output terminals are on the right, + at top and − at bottom, labelled $\tilde V_L$.  [sure]
**Speech vs board:** speech adds that problems 1–5 of PS8 are on Exam 2 material and that the sixth problem ("mathematics associated with transforms") is not (0:00:50–0:01:08). The rules for Exam 2 are "basically the same as the rules for the first exam" (0:01:31).

## p02  f_0092.jpg  [0:00:03 – 0:08:46]
The top of the page-final frame is cut off. **Frames used:** f_0021.jpg (0:02:31) and f_0046.jpg (0:04:20) for the equations, f_0092 for the plots.
**Topic:** "From last time – high-pass filter"  [sure]
**Board:**
- $\tilde H(\omega)=\dfrac{\tilde V_L}{\tilde V_s}=\dfrac{-\omega^2LC}{1-\omega^2LC+j\omega RC}$  [sure]
- $M(\omega)=|\tilde H(\omega)|=\dfrac{\omega^2LC}{\sqrt{(1-\omega^2LC)^2+\omega^2R^2C^2}}$  [sure]
- $\phi(\omega)=\begin{cases}180^\circ-\tan^{-1}\!\left(\dfrac{\omega RC}{1-\omega^2LC}\right) & \omega<\omega_0\\[4pt] -\tan^{-1}\!\left(\dfrac{\omega RC}{1-\omega^2LC}\right) & \omega>\omega_0\end{cases}$  [sure]
- $\omega_0=\dfrac{1}{\sqrt{LC}}$  [sure]
- $Q=\omega_0\dfrac{L}{R}=\dfrac{1}{R}\sqrt{\dfrac{L}{C}}$  [sure]
- "Bode plots for high-pass filter:" and "$\tilde H(\omega)=$" (started)  [sure]
**Diagram:** left, $M(\omega)$ against $\omega$ on linear axes, with 0 at the origin, a dashed asymptote at 1, and a tick at $\omega_0$ with a dashed vertical. The blue curve is labelled "$Q\gg1$" and has a tall narrow peak near $\omega_0$ before settling to 1. The green curve is "$Q\gtrsim1$" with a small bump. The red curve is "$Q<1$" and rises monotonically to 1. Right, $\phi(\omega)$ on linear axes: one green curve runs from 180° at low $\omega$ through 90° at $\omega_0$ to 0° at high $\omega$. Ticks are at 180°, 90°, 0° and $\omega_0$.  [sure]
**Speech vs board:** a student asked for intuition about Q (0:04:07). He explained that low R lets the stored energy build up, giving a high, narrow peak, while high R "knocks it down". Full answer in the note. "High quality factor ... associated basically with having low loss, so low resistance" (0:03:53).
**Re-derived:** sympy: voltage division $Z_L/(Z_R+Z_C+Z_L)$ equals the board $H$ ✓. The piecewise $\phi$ equals $\arg H$ at $\omega/\omega_0=0.1,0.5,0.999,1.001,2,10$ (178.17°, 168.10°, 90.36°, 89.64°, 11.91°, 1.83°) ✓. $\phi(\omega_0)=90^\circ$ ✓. $|H(\omega_0)|=\sqrt{L/C}/R=Q$ ✓ (mine). The board is correct.
> Added context (mine, verified numerically): the HP magnitude peaks only when $Q>1/\sqrt2$, and the peak sits slightly *above* $\omega_0$, at $\omega_0/\sqrt{1-1/(2Q^2)}$ (Q=1 gives 1.414 ω0, Q=5 gives 1.010 ω0). The board's "Q<1 → no peak" label is loose: for 0.707<Q<1 a small peak (≤1.15) exists. The sketch is qualitative, so this is not a board error.

## p03  f_0094.jpg  [0:08:46 – 0:08:47]
**Topic:** scroll state of p02. It shows the two plots, "Bode plots for high-pass filter:" and "$\tilde H(\omega)=$".  [sure]
**Board:** nothing new.
**Speech vs board:** "we have our constant factor l times c" (0:08:47), which leads into p04.

## p04  f_0141.jpg  [0:08:47 – 0:14:19]
**Frames used:** f_0106.jpg (0:10:23) for the full factorization line, f_0127.jpg (0:11:48) and f_0141 for the A1 and A2 plots.
**Topic:** "Bode plots for high-pass filter:"  [sure]
**Board:**
- $\tilde H(\omega)=\underbrace{(LC)}_{\tilde A_1(\omega)}\;\underbrace{(j\omega)^2}_{\tilde A_2(\omega)}\;\underbrace{\left(\dfrac{1}{1+j\omega RC-\omega^2LC}\right)}_{\tilde A_3(\omega)}$  [sure]
- "$\tilde H(\omega)$ has a 2nd order zero @ origin and a quadratic pole @ $\omega_p=\dfrac{1}{\sqrt{LC}}=\omega_0$."  [sure]
- $\tilde A_1(\omega)$: $M(\omega)$[dB] is a horizontal green line drawn **below** the black ω-axis (no value written). $\phi(\omega)$ is green on the 0° axis, annotated "$\phi=0$."  [sure for the drawing. The sign of the dB level is not stated in speech: [likely] $20\log_{10}(LC)<0$ for practical L, C.]
- $\tilde A_2(\omega)$: $M(\omega)$[dB] has a vertical-axis tick "40dB" (overwritten, [likely] "40dB"), "0dB" at the horizontal axis, and ω ticks "1", "10", "100". A green straight line crosses 0 dB at ω=1, labelled "40dB/decade". $\phi(\omega)$ is a green horizontal line at "180" (handwriting reads "188"; speech "a 180 degrees" 0:13:39), with a 0° axis below.  [sure]
**Speech vs board:** speech supplies the reasons. LC is positive, so its phase is 0. $(j\omega)^2=-\omega^2$, so the phase is that of −1, "180 degrees ... independent of frequency". The zero at the origin "doesn't have any inherent frequency scale, so we'll just call the frequencies one, 10, a 100". A factor of 10 in ω multiplies $|A_2|$ by $10^2=100$, "which is 40 dB."
**Re-derived:** the factorization equals the board $H$ (sympy ✓). $20\log_{10}|(j\omega)^2|$ = 0, 40, 80 dB at ω = 1, 10, 100 ✓.
> [!note] The A2 sketch's 40 dB tick sits lower than where the drawn line actually reaches ω=10 (scale imprecision). This is not a content error.

## p05  f_0193.jpg  [0:14:19 – 0:18:40]
**Frames used:** f_0166.jpg (0:16:21) and f_0183.jpg (0:18:08). Both show the A1 and A2 plots. The A3 plot is below the visible area in these frames and appears in p06/p07.
**Topic:** same page, A3 being drawn.
**Board:** as p04 (nothing new visible in the page-final frame).
**Speech vs board (A3 reasoning, speech only):**
- Low ω: $A_3\to1$, so 0 dB and 0°. (He said "So omega will go to one" at 0:15:15, a slip for "this factor will go to one".)  [likely]
- High ω: $A_3\approx\dfrac{1}{-\omega^2LC}$, so −40 dB/decade and a phase of "plus or minus 180°".  [sure, matches p07]
- At $\omega=\omega_0$: $1-\omega_0^2LC=0$, so $A_3=\dfrac{1}{j\omega_0RC}$, whose phase is −90°. This picks −180° (not +180°) above $10\omega_0$.  [sure]
**Re-derived:** $A_3(\omega_0)=-j\sqrt{L/C}/R=-jQ$ (sympy), so the phase is −90° ✓.

## p06  f_0196.jpg  [0:18:40]
**Topic:** "$\tilde A_3(\omega)$:" plot started.
**Board:** A1 and A2 plots as before. A3: $M(\omega)$[dB] has a "0dB" line, an "$\omega_0$" tick, green flat at 0 dB to $\omega_0$ and then falling, labelled "−40dB/decade". $\phi(\omega)$ has ticks "0.1ω0", "ω0", "10ω0", "0°" and "−90" (written like "−98"), with green flat at 0° up to 0.1ω0.  [sure]

## p07  f_0223.jpg  [0:18:40 – 0:19:32]
**Topic:** A3 completed.
**Board:**
- A3 magnitude: 0 dB flat to $\omega_0$, then "−40dB/decade".  [sure]
- A3 phase: 0° up to $0.1\omega_0$, a straight line through −90° at $\omega_0$ (dot drawn), reaching −180° at $10\omega_0$, then flat at −180°. A dashed reference line sits at −180°.  [sure]
- Text in speech, not on the board: "at ω0, phase is −90°" (0:18:40).  [sure]

## p08  f_0275.jpg  [0:19:32 – 0:22:12]
The page-final frame is scrolled back to the top (it shows p04 content). **Frames used for the new content:** f_0244.jpg (0:21:35) and f_0256.jpg (0:21:39) for the scroll states, and f_0310.jpg (0:24:00) and f_0311.jpg (0:24:47) for the composite magnitude plot.
**Topic:** composite Bode plot, introduced by a "⇓" arrow under the factor plots.
**Board:** "$\tilde H(\omega)$:" with $M(\omega)$[dB] axes, a "0dB" line and an "$\omega_0$" tick. Green rises from lower-left to $\omega_0$, labelled "40dB/decade", then runs flat along 0 dB. The right end of the axis is labelled "ω" with a smudge where a subscript 0 was removed.  [sure]
**Speech vs board:** below $\omega_0$ the slopes are 0 + 40 + 0 = +40 dB/dec. Above $\omega_0$ they are 0 + 40 − 40 = 0. "The whole transfer function will approach one as ω goes to infinity", so 0 dB (0:21:43–0:22:23). At 0:22:59 he corrected the axis label: "This is omega. ... not omega naught."
**Re-derived:** composite slope below $\omega_0$ = +40.0 dB/dec and above = 0.0 dB/dec (python, ω0=1, Q=1). $\lim_{\omega\to\infty}H=1$ ✓.

## p09  f_0320.jpg  [0:22:12 – 0:24:49]
The page-final frame is scrolled to the top again. **Frame used:** f_0311.jpg (0:24:47) for the composite phase.
**Board:** $\phi(\omega)$ axes with "0°", "90°", "180°" (a dashed line at 180°) and ticks "0.1ω0", "ω0", "10ω0". Green is flat at 180° up to $0.1\omega_0$, falls linearly to 0° at $10\omega_0$, then stays flat at 0°.  [sure]
**Speech vs board:** "adding up these three constituent phases. So zero degrees, a 180 degrees, and this function here ... shifted upward by a 180 degrees. So instead of going from zero to minus one eighty, it'll go from 180 degrees to zero." (0:23:06–0:23:28). Agrees with the board.
**Re-derived:** exact phase is 178.2° at 0.1ω0, 90° at ω0 and 1.8° at 10ω0 (Q=0.1 test case) ✓, consistent with the asymptote.

## p10  f_0323.jpg  [0:24:49 – 0:24:50]
**Topic:** scroll state showing "Bode plots for high-pass filter:", the factorization and the "2nd order zero / quadratic pole" line.  [sure]
**Board:** nothing new.

## p11  f_0347.jpg  [0:24:50 – 0:25:43]
**Topic:** scroll state of the A1 and A2 factor plots.  [sure]
**Speech (no new ink):** this is the limitation of Bode plots. The straight-line plot "is independent of the quality factor", while the actual $|H|$ near $\omega_0$ depends strongly on Q. Bode plots "capture quite well ... the limiting behaviors at low and high frequencies" (0:24:20–0:25:42).

## p12  f_0356.jpg  [0:25:43 – 0:25:45]
**Topic:** scroll state with the A2 and A3 plots and the top of the composite.  [sure]
**Speech:** the student question begins ("if there was another ... multiple zeros and poles").

## p13  f_0399.jpg  [0:25:45 – 0:31:48]
**Frames used:** f_0388.jpg (0:27:38) and f_0394.jpg (0:30:37), which show the red extra factor.
**Topic:** answer to the student question about more factors, then the heading "Filter order:".
**Board:**
- Red auxiliary axes under the A3 plots. A red line rises from lower-left and merges into the 0 dB axis at a red tick "$\omega_1$", then runs flat. Speech: "something rising at a slope of ... 20 dB per decade and then leveling off" (0:26:57).  [sure: shape on board, slope from speech]
- On the composite $\tilde H$ magnitude plot: a red tick "$\omega_1$" to the right of $\omega_0$. A red line rises more steeply than the green one up to $\omega_0$ (speech: "60 dB per decade", 0:27:50), falls from $\omega_0$ to $\omega_1$ (speech: "−40 + 20 ... minus 20 dB per decade", 0:28:09), then falls more steeply above $\omega_1$ (speech: "minus 40 dB per decade", 0:28:31). He said "I drew that a little bit too far."  [sure: shape on board, slopes from speech]
- "Filter order:" (underlined)  [sure]
**Speech vs board:** he calls the result "a bandpass filter" whose passband width is set by $\omega_0$ and $\omega_1$ (0:28:49–0:29:04).
**Re-derived:** **[board differs]**. Multiplying the green $H$ (+40 dB/dec below $\omega_0$, 0 above) by the drawn factor $(j\omega/\omega_1)/(1+j\omega/\omega_1)$ (+20 below $\omega_1$, 0 above) gives python slopes of **+60.0 below $\omega_0$, +19.2 (→ +20) between $\omega_0$ and $\omega_1$, and 0.0 above $\omega_1$** (ω0=1, ω1=100). The result is still a **high-pass**, steeper in its stopband, and **not** a bandpass. The board's −20/−40 omits the +40 dB/dec of $A_2=(j\omega)^2$, which persists at all frequencies. With $\omega_1<\omega_0$: +60, +40, 0, also high-pass. A bandpass needs a *falling* factor, $1/(1+j\omega/\omega_1)$ with $\omega_1>\omega_0$, which gives +40, 0 (flat passband), −20 (python: 40.0, −0.8, −20.0).

## p14  f_0420.jpg  [0:31:48 – 0:34:40]
**Frame used:** f_0416.jpg (0:34:39), which shows the whole page including the first sentence.
**Topic:** "Filter order:"  [sure]
**Board:**
- "For zeros or poles, the steepness of the frequency response increases as the order of the zero or pole increases." ("their" was struck through and replaced by "the".)  [sure]
- "For a filter as a whole, the <u>order</u> of the filter is the absolute value of the highest power of ω in the dominant behavior of $\tilde H(\omega)$ when ω is in the filter stop band."  [sure]
**Speech vs board:** "the order is always a positive number" (0:33:46). "20 dB per decade if it's a linear, or inverse linear, function of omega. 40 dB per decade if it's omega squared or one over omega squared" (0:31:34). "There's a whole bunch of prepositional phrases in there" (0:34:30).

## p15  f_0424.jpg  [0:34:40 – 0:34:52]
**Topic:** "band pass filter:"  [sure]
**Board:** heading only.

## p16  f_0425.jpg  [0:34:52 – 0:35:58]
**Topic:** "band pass filter:"  [sure]
**Diagram:** $\tilde V_s$ (±) on the left. The top wire carries $L$ then $C$ to the output node. $R$ runs from the output node down to the bottom wire. The output $\tilde V_R$ is across $R$, + at top and − at bottom.  [sure]
**Board:** $\tilde H(\omega)=\dfrac{j\omega RC}{1+j\omega RC-\omega^2LC}$  [sure]
**Speech vs board:** he misspoke "minus omega squared l squared ... Or sorry, LC" (0:35:36). The board is correct. "The passband was basically centered around the pole frequency, one over root LC, which is also the resonant frequency."
**Re-derived:** $Z_R/(Z_R+Z_C+Z_L)$ equals the board $H$ (sympy ✓).
> [!warning] Adjacent to PS8 9.26 (series RLC bandpass parameters): graded work. The lecture only recaps $H$ and the filter order here. The tutor must not use this circuit to compute 9.26's parameters.

## p17  f_0433.jpg  [0:35:58 – 0:39:48]
**Frame used:** f_0429.jpg (0:39:02) as well, which shows the circuit and H above the text.
**Board:**
- "stopbands are $\omega\ll\omega_0$, $\omega\gg\omega_0$"  [sure]
- "$\omega\ll\omega_0$: $\tilde H(\omega)\approx j\omega RC\;\Rightarrow$ first order"  [sure]
- "$\omega\gg\omega_0$: $\tilde H(\omega)\approx\dfrac{R}{j\omega L}\;\Rightarrow$ first order"  [sure]
- "Bode plots for the band pass filter showed $M(\omega)$ has slope of ±20dB/decade in stop bands."  [sure]
**Speech vs board:** agree. "plus or minus 20 dB per decade is what you get for first order filter" (0:38:52).
**Re-derived:** $\lim_{\omega\to0}H/(j\omega RC)=1$ and $\lim_{\omega\to\infty}H/(R/(j\omega L))=1$ (sympy ✓).

## p18  f_0442.jpg  [0:39:48 – 0:40:55]
**Topic:** "high-pass filter:"  [sure]
**Diagram:** same as p01: $R$ and $C$ in series on the top wire, $L$ shunting from the output node to the bottom wire, output $\tilde V_L$.  [sure]
**Board:** $\tilde H(\omega)=\dfrac{-\omega^2LC}{1+j\omega RC-\omega^2LC}$  [sure]

## p19  f_0466.jpg  [0:40:55 – 0:49:20]
**Frames used:** f_0452.jpg (0:45:33), f_0460.jpg (0:46:40) and f_0464.jpg (0:48:00).
**Board:**
- "stop band is $\omega\ll\omega_0$:"  [sure]
- "$\omega\ll\omega_0$: $\tilde H(\omega)\approx-\omega^2LC\;\Rightarrow$ second-order"  [sure]
- "Bode plots showed $M(\omega)$ has slope +40dB/decade in stop band."  [sure]
- "<u>Active Filters</u>" / "<u>Reading</u>: Ulaby et al., Secs. 9-6, 9-7."  [sure]
- "Active filters contain components that can generate power and therefore gain, e.g., op amps."  [sure]
**Speech vs board:** student question at 0:42:16 about whether "low ω" means $\omega RC\ll1$. Answer: compare quantities with the same units, i.e. ω with $\omega_0=1/\sqrt{LC}$; "very roughly ... an order of magnitude" (0:44:33). "You'll get an additional plus or minus 20 dB in that slope every time you increase the order by one" (0:46:22). Passive cascades lose signal and active ones can restore it (0:47:52). ECE 438 covers transistors (0:49:16).
**Re-derived:** $\lim_{\omega\to0}H/(-\omega^2LC)=1$ ✓. Slope +40.0 dB/dec ✓.

## p20  f_0480.jpg  [0:49:20 – 0:50:28]
**Frame used:** f_0476.jpg (0:50:27), which is unoccluded.
**Board:** "Op amp and other active filter circuits can be cascaded to improve gain, frequency response, or other characteristics."  [sure]

## p21  f_0550.jpg  [0:50:28 – 1:05:11]
**Frames used:** f_0481.jpg (0:50:48, title), f_0484.jpg (0:54:21, circuit and $Z$'s), f_0501.jpg (0:56:19, KCL), f_0529.jpg (0:58:05, H), f_0543.jpg (1:02:44), f_0549.jpg (1:05:10) and f_0550.
> [!warning] = Lab 5 (first-order active inverting LP of Fig 5.0, R1/R2/C ↔ Rs/Rf/Cf here): graded work. The tutor must not use this as a walkthrough or check. It is also adjacent to PS8 (inverting op-amp with R1‖C1 input and R2‖C2 feedback): same −Zf/Zs method, and the tutor must not extend it to that circuit.

**Topic:** "Example: active first-order low-pass filter"  [sure]
**Diagram:** $\tilde V_s$ (±, bottom to ground) connects through $R_s$ to the op-amp inverting (−) input node. The non-inverting (+) input is tied to ground. The feedback is $R_f$ in parallel with $C_f$, between the − input node and the op-amp output. The output terminal $\tilde V_{out}$ is + at the output and − at a ground terminal. Blue dashed loops enclose $R_s$ (labelled "$\tilde Z_s$") and $R_f\|C_f$ (labelled "$\tilde Z_f$").  [sure]
**Board:**
- $\tilde Z_s=R_s$  [sure]
- $\tilde Z_f=\dfrac{R_f\left(\frac{1}{j\omega C_f}\right)}{R_f+\frac{1}{j\omega C_f}}\cdot\left(\dfrac{j\omega C_f}{j\omega C_f}\right)$ (multiplier in green)  [sure]
- $\tilde Z_f=\dfrac{R_f}{1+j\omega R_fC_f}$  [sure]
- By KCL: $\dfrac{-\tilde V_s}{\tilde Z_s}-\dfrac{\tilde V_{out}}{\tilde Z_f}=0\;\Rightarrow\;\tilde V_{out}=-\dfrac{\tilde Z_f}{\tilde Z_s}\tilde V_s$  [sure]
- $\tilde H(\omega)=\dfrac{\tilde V_{out}}{\tilde V_s}=-\dfrac{\tilde Z_f}{\tilde Z_s}=-\dfrac{R_f}{R_s}\underbrace{\left(\dfrac{1}{1+j\omega R_fC_f}\right)}_{\text{simple pole @ }\omega_0=\frac{1}{R_fC_f}}$  [sure]
- "Bode plots:" $M(\omega)$[dB] is flat at "$20\log(R_f/R_s)$" up to $\omega_0$ (dash-dot vertical at $\omega_0$), then falls with the label "−20dB/decade". The flat level is drawn above the 0 dB axis.  [sure]
- $\phi(\omega)$: ticks "0°", "90°" (dashed reference), "180°", "0.1ω0", "ω0", "10ω0". Green is flat at 180° up to $0.1\omega_0$, falls linearly to 90° at $10\omega_0$, then stays flat at 90°.  [sure]
**Speech vs board:** KCL at the inverting node, which sits at 0 V by the ideal op-amp rule, with no current into the op amp (0:54:50–0:55:57). "Which should look familiar ... the result that we got for the inverting op amp amplifier" (0:56:10). "We won't go through ... constituent factors ... this is simple enough that we can just essentially get it directly" (0:58:06). Low ω: phase of −1, "which we'll take to be a 180 degrees". High ω: the j in the denominator adds −90°, giving 90° (1:00:43–1:01:40). Board and speech agree.
**Re-derived:** sympy: $R_f\|(1/j\omega C_f)=R_f/(1+j\omega R_fC_f)$ ✓. Solving the KCL equation gives $\tilde V_{out}/\tilde V_s=-Z_f/Z_s$ ✓. $H=-(R_f/R_s)/(1+j\omega R_fC_f)$ ✓. Numeric check with $R_f/R_s=10$: 20.00 dB at $10^{-3}\omega_0$, 16.99 dB and 135.0° at $\omega_0$, 95.7° at $10\omega_0$, slope −20.0 dB/dec ✓.

## p22  f_0551.jpg  [1:05:11]
**Topic:** scroll state showing the Bode plots of p21 and an "N" (the start of "Note:").  [sure]

## p23  f_0570.jpg  [1:05:11 – 1:06:00]
**Topic:** scroll state of p21 (H, simple pole, Bode plots).  [sure]
**Speech:** "the resonant frequency ... Not the resonant frequency. The pole frequency, it doesn't depend on RS" (1:05:17). A realistic source (V source plus series R) "would change the gain ... but not the pole frequency."

## p24  f_0572.jpg  [1:06:00 – 1:06:47]
**Board:**
- "Note:"  [sure]
- "1) $\omega_0$ doesn't depend on $R_s$."  [sure]
- "2) $\tilde V_{out}$ will be unchanged for any load resistance $R_L$ connected to $\tilde V_{out}$."  [sure]

## p25  f_0583.jpg  [1:06:47 – 1:07:17]
**Board:** "3) op-amp can provide gain in filter pass band."  [sure]

## p26  f_0586.jpg  [1:07:17 – 1:07:44]
**Board:** "<u>Example</u>: active first-order high-pass filter"  [sure]

## p27  f_0587.jpg  [1:07:44 – 1:08:40]
**Frame:** all black (sharpness 0). The screen share stopped (VTT "Sharing Stopped" 1:08:40.9–1:09:11.8). **Frames used instead:** f_0589.jpg (1:09:36) and f_0592.jpg (1:10:45); see p28.
**Speech:** "we have an op amp here ... The noninverting input, connect to" (1:07:50–1:07:58), then silence until 1:08:55: "let me figure out how to get myself back into ... if I can still share here." Then a gap from 1:09:03 to 1:09:22. "All of these Zoom or IT malfunctions are now preserved forever" (1:09:30).

## p28  f_0619.jpg  [1:08:40 – 1:16:48]
**Frames used:** f_0589.jpg (1:09:36, circuit without labels), f_0592.jpg (1:10:45, labelled circuit and $Z$'s), f_0605.jpg (1:12:43, KCL and H), f_0615.jpg (1:13:49, factored form), f_0618.jpg (1:14:24, magnitude axes) and f_0619 (1:16:48, magnitude plot and phase axes).
> [!warning] Adjacent to PS8 (inverting op-amp with R1‖C1 input and R2‖C2 feedback; this example's input is a *series* RsCs, not R‖C). It is not an exact collision, but the tutor must not extend this example into that problem's solution.

**Topic:** "Example: active first-order high-pass filter"  [sure]
**Diagram:** $\tilde V_s$ (±, to ground) connects through $R_s$ in series with $C_s$ to the inverting (−) input node. The (+) input is grounded. $R_f$ runs from the − input node to the op-amp output. The output terminal is $\tilde V_{out}$ (+) against ground. Blue dashed loops label $\tilde Z_s$ (around $R_s$, $C_s$) and $\tilde Z_f$ (around $R_f$).  [sure]
**Board:**
- $\tilde Z_s=R_s+\dfrac{1}{j\omega C_s}$, $\tilde Z_f=R_f$  [sure]
- By KCL: $\dfrac{-\tilde V_s}{\tilde Z_s}-\dfrac{\tilde V_{out}}{\tilde Z_f}=0\Rightarrow\tilde V_{out}=-\dfrac{\tilde Z_f}{\tilde Z_s}\tilde V_s$  [sure]
- $\tilde H(\omega)=\dfrac{\tilde V_{out}}{\tilde V_s}=\dfrac{-R_f}{R_s+\frac{1}{j\omega C_s}}\left(\dfrac{j\omega C_s}{j\omega C_s}\right)=\dfrac{-j\omega R_fC_s}{1+j\omega R_sC_s}$ (multiplier in green)  [sure]
- $=-R_fC_s\,\dfrac{+j\omega}{1+j\omega R_sC_s}$, with an arrow labelling "$+j\omega$" as "simple zero @ origin" and a brace under the denominator: "simple pole @ $\omega_0=\dfrac{1}{R_sC_s}$."  [sure. The "+" follows his spoken correction "minus... Or sorry. Plus j omega" at 1:12:54.]
- "Bode plots:" $M(\omega)$[dB] has ω ticks "0.1ω0", "ω0", "10ω0" and a dashed level "$20\log(R_f/R_s)$". Green rises with the label "20dB/decade" and levels onto the dashed line at about $\omega_0$.  [sure]
- $\phi(\omega)$: axes with "0°", "−90°", "−180°" (dashed at −180°) and ticks "0.1ω0", "ω0", "10ω0". **No curve in the last captured frame.**  [sure for the axes]
- Phase curve, speech only (1:16:28–1:17:22): −90° for $\omega\to0$ ("the relevant factor is minus j"), −180° for $\omega>10\omega_0$ ("the factor of minus one ... minus a 180 degrees"), "and the transition will look like this."  [likely: drawn after the last frame; reconstructed as −90° flat to $0.1\omega_0$, a linear fall to −180° at $10\omega_0$, then flat]
**Speech vs board:** at high ω, "the j omega here and the j omega here cancel out ... just minus RF over RS", so the magnitude limit is $20\log(R_f/R_s)$. He misspoke "log of RS ... RF over RS" and corrected it at 1:15:03. Low ω: "first order in omega ... slope of 20 dB per decade". Closing remark (1:17:35): "because this is an active filter, then we can get gain in the passband that's determined from the design of the circuit ... RF over RS. That's the main distinction ... compared to the passive filter circuits."
**Re-derived:** sympy: $-R_f/(R_s+1/j\omega C_s)=-j\omega R_fC_s/(1+j\omega R_sC_s)=-R_fC_s\cdot(+j\omega)/(1+j\omega R_sC_s)$ ✓. $\lim_{\omega\to\infty}H=-R_f/R_s$ ✓. Numeric check with $R_s=1$ kΩ, $C_s=100$ nF, $R_f=10$ kΩ: $\omega_0=10^4$ rad/s. The table is −40.0 dB/−90.06° at $10^{-3}\omega_0$, −0.04 dB/−95.7° at $0.1\omega_0$, 16.99 dB/−135.0° at $\omega_0$, 19.96 dB/−174.3° at $10\omega_0$. The slope below $\omega_0$ is +20.0 dB/dec ✓.
> [!note] Phase-sign bookkeeping: for the LP he wrote −1 as +180° (plot 180°→90°). For the HP, −1·j becomes −90° (plot −90°→−180°). Both are correct mod 360°. Pick one representation per plot and stay continuous.

---

## Audio and frame gaps
- 1:07:58 → 1:08:55: no speech; the screen share failed (black frame f_0587).
- 1:09:03 → 1:09:22: no speech, while the share is re-established.
- 1:16:48 → end: no frames. The active-HP phase drawing is not captured.
- 1:18:38 → 1:18:46: an off-topic tail, "Oh. Let me skip the final. Oh, so the final, it will be", cut off mid-sentence. The content (apparently about the final exam) is lost. "skip" may be an ASR error (?).

## Board errors / discrepancies found
1. **p13 (0:26:43–0:30:26), [board differs], substantive.** Adding a first-order factor that rises at +20 dB/dec and levels off at $\omega_1$ to the RLC high-pass gives slopes +60 / +20 / 0, which is a steeper **high-pass**. The board and speech give +60 / −20 / −40 and call it a "bandpass". The +40 dB/dec of $(j\omega)^2$ was dropped above $\omega_0$. A bandpass needs a falling factor $1/(1+j\omega/\omega_1)$, $\omega_1>\omega_0$, which gives +40 / 0 / −20.
2. Spoken slips with a correct board: "ω² L squared … sorry, LC" (0:35:36); "So omega will go to one" for "this factor goes to one" (0:15:15); the axis label ω₀ corrected to ω (0:22:59); "resonant frequency … not the resonant frequency, the pole frequency" (1:05:17); "minus … sorry, plus jω" (1:12:54); "log of RS … RF over RS" (1:15:03); "20 degrees … 20 dB per decade" (0:26:57).
3. Handwriting only: "188" = 180°, "−98" = −90°.
