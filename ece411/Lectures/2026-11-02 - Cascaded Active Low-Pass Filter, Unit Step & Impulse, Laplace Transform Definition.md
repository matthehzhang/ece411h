---
course: ECE 411H
date: 2026-11-02
instructor: Prof. Ed Yu
topic: Cascaded third-order active (op-amp) low-pass filter with Bode plots; Semester Exam 2 coverage boundary; why transform methods; unit step, unit impulse (delta) and its sampling property; definition of the Laplace transform and the complex frequency s
reading: Ulaby/Maharbiz/Furse 3e Ch. 12 (§12-1 key functions; §12-2 Laplace transform)
source: Recordings/2026-11-02-laplace-transforms (transcript + 20 distinct tablet pages from 67 page-final frames; descriptions in frames/pages_described.md)
tags: [ece411, lecture, active-filter, op-amp, cascade, bode-plot, laplace, unit-step, delta-function, exam2, final]
source_quality:
  - "Speech: Deepgram Nova-3, 78 min audio, 942 utterances, 9628 words; mean utterance confidence 0.96; 94 words < 0.55 (1.0 %); 14 utterances < 0.7 (lowest 0:10:53, 1:11:14, 0:27:29, 0:16:30)"
  - "Spoken math is transcribed as words: signs, subscripts and T-vs-t are ASR guesses (e.g. 'x of t' for x(T) at 1:11:39, 'poll' for pole at 0:24:11)"
  - "Student questions are off-mic and fragmentary; 0:17:47 is garbled, class answers at 0:34:29-0:34:41 inaudible"
  - "Board: 20 distinct OneNote tablet pages, 0 blurry; the pen toolbar hides the top-centre strip of every frame, so earlier/later frames were used (named in pages_described.md)"
  - "Last frame (1:16:48) stops mid-sentence; the final board line is completed from speech only"
  - "No audio dropouts found"
---

# 2026-11-02: Cascaded Active Low-Pass Filter, Unit Step & Impulse, Laplace Transform Definition

## Summary

- **Exam 2 boundary, stated three times and written on the board:** Semester Exam 2 covers active filter circuits **up to and including the two posted cascaded-filter videos** (cascaded bandpass filter; band-reject filter design). The board says "**SEMESTER EXAM 2 COVERS TO HERE**" right before "Circuit Analysis using Laplace Transforms". **Laplace transforms are not on Exam 2. They are on the final.** [0:01:55, 0:02:35, 0:39:04]
- **Logistics:** Exam 2 is Wed 11/11/2026, in class. The answer-sheet template will be posted by the beginning of next week; bring a hard copy and write on it. PS8 is due Mon 11/09, 9:00 AM. The Laplace-pair table handout is for the final only, not Exam 2.
- **Worked example, cascaded third-order active low-pass:** three inverting op-amp stages. Each has feedback $R_f\parallel C_f=10\text{ k}\Omega\parallel1\text{ nF}$, so every stage has its pole at $\omega_0=1/R_fC_f=10^5$ rad/s. The input resistors are **10 Ω**, 10 kΩ and 10 kΩ. Result: $\tilde H(\omega)=-\dfrac{10^3}{(1+j\omega10^{-5})^3}$.
- **Why cascading works here:** each op-amp output acts as an ideal voltage source, so the next stage does not load it and **the stage transfer functions multiply**. A passive cascade loads the previous stage and must be analysed as a whole.
- **Bode plots:** magnitude flat at **60 dB** up to $\omega_0$, then **−60 dB/decade** (versus −20 for one stage). Phase starts at **180°** (from the $-1$), falls between $0.1\omega_0$ and $10\omega_0$, and ends at **−90°** ($j^3$ counted as 270°, and $180°-270°$).
- **Why transforms:** time-domain differential equations handle only simple inputs, and phasors handle one sinusoidal frequency. Laplace/Fourier transforms turn the differential equations into **algebraic** equations for (nearly) arbitrary inputs; an inverse transform brings the answer back to the time domain.
- **Unit step and unit impulse (§12-1):** $u(t)$ is 0 for $t<0$ and 1 for $t>0$, and $u(0)$ is convention-dependent (0, ½ or 1). $\delta(t)$ is 0 for $t\neq0$ and infinite at 0, with unit area. It is the limit of a narrowing Gaussian. $u(t)=\int_{-\infty}^t\delta(t')dt'$ and $du/dt=\delta$.
- **Sampling property:** $\int_{-\infty}^{\infty}x(t)\delta(t-T)\,dt=x(T)$ for $x$ continuous.
- **Laplace transform (§12-2):** $F(s)\equiv\mathcal L[f(t)]=\int_{0^-}^{\infty}f(t)e^{-st}dt$, where $s=\sigma+j\omega$ is the "complex frequency". The $0^-$ lower limit lets initial conditions at $t=0$ enter. The lecture stopped at the definition: **no transform pairs or properties were derived.** Pairs and the inverse transform come next class (Wed 11/04).

---

## Content

### 0. Announcements [0:00:02–0:02:18]
Board (typed, f_0003):
1. "Problem Set 7 was due today on Canvas at 9:00AM Central time."
2. "Problem Set 8 is due on Canvas 9:00AM Central time on Monday 11/09/2026."
3. "Answer sheet template for Semester Exam 2 will be posted by the beginning of next week. Be sure to bring/prepare a copy of the template for the exam, which will be in class on Wednesday 11/11/2026."
4. A "Checkpoint Survey" on Canvas (experiences in ECE 411H, including use and impact of AI), due 11:59 PM Sunday 11/08/2026.
5. "A handout on Laplace Transform pairs will be posted on Canvas later this week. You'll also be provided with a copy of the tables in this handout to use for the final exam."

Spoken additions: the template will come "hopefully late this week, but definitely by the beginning of next week". It must be "a hard copy template on which you'll physically write your solutions" [0:00:38–0:00:59]. The Laplace table "you won't have... for the second semester exam because Laplace transforms are not included, in the content on the second, semester exam" [0:01:55–0:02:13].

### 1. Plan for the day [0:02:23–0:03:37]
"Finish up our discussion of active filter circuits, and that will bring us to the end of what's covered on the second semester exam. And then we will start the discussion of circuit analysis using Laplace transforms, which will not be on the second semester exam, but it will be on the final." Last class covered first-order active high-pass and low-pass filters. Nathan had asked whether stages can be combined to get "a higher order filter, which will give you a steeper roll off". The answer is yes, and today's first example shows how.

### 2. Example: cascaded third-order low-pass filter [0:03:43–0:37:01]
Board title (f_0011): **"Example: cascaded third-order low-pass filter."**

**Circuit (f_0012), drawn left to right** [0:03:43–0:08:05]:
- **Stage 1:** $\tilde V_s$ (+ on top, − to ground) feeds a **10 Ω** resistor into the inverting (−) input of op-amp 1. The (+) input is grounded. The feedback from output to (−) is **10 kΩ in parallel with 1 nF**. The output is $\tilde V_1$. "This is basically just the first order active lowpass filter that we looked at last time." [0:05:25]
- **Stage 2:** $\tilde V_1$ → **10 kΩ** → (−) of op-amp 2, with (+) grounded and feedback 10 kΩ ∥ 1 nF. The output is $\tilde V_2$.
- **Stage 3:** identical to stage 2, driven by $\tilde V_2$. The output terminals $\tilde V_3$ have + at the op-amp output and − at ground.
- A green dashed circle around the stage-1 feedback pair is labelled $\tilde Z_f$. "Each successive stage... gives us basically another factor of pole in the transfer function. So we'll have three of those, and that will give us a third order lowpass filter." [0:08:08–0:08:24]
- Each stage "has the structure just of an inverting op amp amplifier", so $\tilde V_{out}=-(\tilde Z_f/\tilde Z_s)\tilde V_{in}$. [0:09:01–0:09:32]

> [!warning] Stage 1's input resistor is **10 Ω**, not 10 kΩ (board "10Ω"; speech "This is a 10 ohm resistor" [0:04:59]; "the 10 ohm resistor" [0:14:46]). This is what makes the DC gain $10^3$ (60 dB). Stages 2 and 3 use 10 kΩ and have unity DC gain magnitude.

**Pole frequency, same for all stages** [0:09:32–0:10:41] (f_0032):
$$\omega_0=\frac{1}{R_fC_f}=\frac{1}{(10\text{ k}\Omega)(1\text{ nF})}=10^5\ \text{rad/s}\quad\text{"For all op-amp stages."}$$
His arithmetic: "10 to the fourth times 10 to the minus nine... 10 to the minus five in the denominator, so that becomes 10 to the five in the numerator."

**Feedback impedance** [0:12:51–0:14:25] (f_0032). Parallel R and C is product over sum. Multiply the top and bottom by $j\omega C_f$ (written in green):
$$\tilde Z_f=\frac{R_f\left(\frac{1}{j\omega C_f}\right)}{R_f+\frac{1}{j\omega C_f}}\cdot\frac{j\omega C_f}{j\omega C_f}=\frac{R_f}{1+j\omega R_fC_f}=\frac{10^4}{1+j\omega10^{-5}}$$
"This product here, $R_f$ times $C_f$, that's where this frequency $\omega_0$, the pole frequency, comes from." [0:13:49]

**Stage 1 output** [0:14:25–0:15:55] (f_0079):
$$\tilde V_1=-\frac{\tilde Z_f}{\tilde Z_s}\tilde V_s=-\frac{10^3}{1+j\omega10^{-5}}\tilde V_s$$
($10^4/10=10^3$.) You can recall $-Z_f/Z_s$ from the inverting amplifier "or you could easily derive it... by applying KCL... at the inverting input of the op amp." [0:15:02]

**Stage 2 output** [0:16:00–0:21:28] (f_0085 → f_0110). $\tilde V_1$ "is the output of the op amp, we can think of it as essentially acting like just the voltage source." [0:16:21]
$$\tilde V_2=-\frac{\tilde Z_f}{10\text{ k}\Omega}\tilde V_1=+\frac{\cancel{10^4}}{\cancel{10^4}(1+j\omega10^{-5})}\left(+\frac{10^3}{1+j\omega10^{-5}}\tilde V_s\right)=\frac{10^3}{(1+j\omega10^{-5})^2}\tilde V_s$$
On the board he overwrote the two minus signs with red "+" and struck the $10^4$s in red: "these 10 to the fourths will cancel out. The minus signs will cancel out." [0:20:22] "The main effect of adding this second stage... is to give you another pole factor... If this were the end, this would be a second order circuit... at high frequencies, omega squared in the denominator." [0:21:03–0:21:28]

**Stage 3 output** [0:21:32–0:23:19] (f_0124). "The analysis will be exactly the same":
$$\tilde V_3=-\frac{\tilde Z_f}{10\text{ k}\Omega}\tilde V_2=-\frac{\cancel{10^4}}{\cancel{10^4}(1+j\omega10^{-5})}\left(\frac{10^3}{(1+j\omega10^{-5})^2}\tilde V_s\right)=-\frac{10^3}{(1+j\omega10^{-5})^3}\tilde V_s$$

**Transfer function** [0:23:19–0:24:22] (f_0127, f_0129):
$$\boxed{\tilde H(\omega)=\frac{\tilde V_3}{\tilde V_s}=-\frac{10^3}{(1+j\omega10^{-5})^3}}$$
A brace under the denominator is labelled **"3rd order simple pole @ $\omega_0=10^5$ rad/s"**.

> [!check] Verified (python3 and ngspice AC with $10^8$-gain VCVS op-amps). The stage-by-stage product equals the board's closed form at every test frequency. $\omega_0=10^5$ rad/s ($f_0=15.92$ kHz). DC: 60.00 dB, 180°. **No board error.**

**Bode magnitude plot** [0:24:28–0:27:30] (f_0143 → f_0172, left). Axes: "$M(\omega)$ [dB]" against $\omega$ on a log scale, with ticks at $0.1\omega_0$, $\omega_0$ and $10\omega_0$ and a dashed vertical line at $\omega_0$.
- Low frequency: $|H|\to10^3$, and "20 times the log base 10 of 10 to the third... that's gonna be 60 dB." It is drawn flat at 60 dB up to $\omega_0$. [0:25:38–0:26:18]
- High frequency: "it'll go as omega cubed in the denominator", so "a factor of 10 to the third decrease for every factor of 10 increase in the frequency gives us a slope of **minus 60 dB per decade**." [0:26:23–0:27:10] The green line falls from $(\omega_0, 60\text{ dB})$ and meets the horizontal axis (0 dB) at $10\omega_0$. Label: "−60 dB/decade".
- "Much steeper than what we saw for the first order filter where that slope was minus 20 dB per decade." [0:27:17]
- He reminds the class of the Ulaby convention: Bode plots are the log magnitude and the linear phase against log frequency, "using kind of the linear approximations for the limiting behaviors at low and high frequencies." [0:24:41–0:25:04]

**Bode phase plot** [0:31:57–0:35:45] (f_0165 → f_0172, right). Axes: "$\phi(\omega)$" on a linear scale against log $\omega$, with the same ticks.
- Low frequency ("much lower than the pole frequency. So less than 0.1 $\omega_0$ is the convention that we use"): the phase comes only from the $-1$, which is **180°**. [0:32:39–0:33:07]
- Each denominator factor $1+j\omega10^{-5}$ has a positive, first-quadrant angle. It is cubed, "so then that phase factor will be multiplied by three", and because it sits in the denominator it is subtracted, so the curve comes down. [0:33:09–0:33:55]
- High frequency ($\omega>10\omega_0$): the denominator phase is that of $j^3$. He asked the class: "you can have it as either negative 90 or as two seventy... if you think about how this evolves as omega increases... we wanna take it to be two seventy, and that's gonna be subtracted from 180 degrees. So that'll bring us to **minus 90 degrees**." [0:34:08–0:35:07]
- Drawn: flat at 180° to about $0.1\omega_0$, a straight descent through about $\omega_0$, reaching −90° at $10\omega_0$, then flat at −90° (dashed guide).
- Point of the example: "by having these multiple stages, we could get a steeper roll off outside the passband of the filter." [0:35:31]

> [!note] Added context (mine, not his; verified with python3 and ngspice)
> - **The exact phase at $\omega_0$ is $180°-3(45°)=45°$.** The straight-line phase segment falls at $-135°$/decade (that is, $-45°$/decade per pole) from $(0.1\omega_0,180°)$ to $(10\omega_0,-90°)$ and passes through 45° at $\omega_0$. Exact values: 162.9° at $0.1\omega_0$ and −72.9° at $10\omega_0$.
> - **The exact magnitude at $\omega_0$ is 50.97 dB**, which is $3\times3.01=9.03$ dB below the asymptote corner, not 3 dB. At $10\omega_0$ it is −0.13 dB (asymptote 0 dB).
> - **The −3 dB (half-power) cutoff is not $\omega_0$** for a repeated pole: $\omega_c=\omega_0\sqrt{2^{1/3}-1}=0.510\,\omega_0=5.10\times10^4$ rad/s (8.11 kHz; ngspice 8.10 kHz). If a P3 asks for "the cutoff frequency" of a cascade of identical poles, this is the trap. He did not discuss it.

> [!warning] Speech slips, board correct
> - [0:33:39] "Since it's in the denominator, it's gonna subtract from the phase of zero." The plotted phase starts at **180°**, not 0°. He probably meant the denominator factor's own phase, which starts from 0°. Follow the board.
> - [0:36:05–0:36:11] Answering Jason, he said that starting at −180° the curve "would have gone from minus one eighty... down to 180 minus two seventy." Starting at −180° the endpoint is $-180°-270°=-450°\equiv-90°$. The spoken "180 minus 270" is a slip or an ASR drop of "minus". [unclear]
> - Terminology: "3rd order simple pole" is his and Ulaby's Bode-table usage for $(1+j\omega/\omega_0)^3$. In complex-analysis terms it is a triple (repeated) real pole, not a "simple" one.

### 3. Additional cascaded-filter videos and the Exam 2 boundary [0:36:56–0:39:52]
Board (f_0176, f_0177): **"See videos of: – cascaded bandpass filter – band reject filter design"**
- Cascaded bandpass: "a lowpass filter with a highpass filter, and then by doing that, you can get a bandpass filter. If you switch the order of the frequencies for the lowpass and the highpass, you could get a cascaded band reject filter." [0:37:42–0:38:06]
- Band-reject design: "you're given a set of parameters that the circuit has to satisfy. So the gain, what the stopband is, and what the roll off has to be, outside of, the band stop... design a cascaded filter circuit that actually satisfies all of those conditions." [0:38:16–0:38:41]
- The semester's problem-solving videos also contain "some examples of these types of filters." [0:38:53]

Board (f_0179): **"——— SEMESTER EXAM 2 COVERS TO HERE ———"**
"Including these videos that I've listed here, that is the end of what you were responsible for for the second semester exam. So semester exam two basically covers to this point." [0:39:04–0:39:25]

### 4. Circuit analysis using Laplace transforms: motivation [0:39:58–0:58:24]
Board (f_0180/f_0183): **"Circuit Analysis using Laplace Transforms." "Reading: Ulaby et al, Chapter 12."** This is "the last big topic for the course... Laplace and Fourier techniques to really broaden the class... of input signals." [0:39:58–0:40:16]

**Recap of the semester** (f_0189/f_0193) [0:41:02–0:45:56]. "Earlier in the semester, we analyzed circuits in the following situations:"
- "in the time domain, used differential equations to understand time-dependent response to simple input signals." These were constant inputs, or "voltages or currents switched on or off, but nothing really more complicated than that... useful but really quite limiting." [0:41:58–0:43:49]
- "in the frequency domain, used phasor analysis to understand steady-state response of circuits to sinusoidal signals at a single frequency." Treating frequency as a parameter then "led us to the idea of filter circuits." [0:43:50–0:45:56]

**The question** (f_0199) [0:45:56–0:47:06]: **"How do we understand circuits with arbitrary input signal?"** The methods so far cannot handle several sinusoids at once or non-periodic signals, except very simple cases.

**Statement** (f_0206) [0:47:06–0:49:26]: **"Transform techniques allow us to connect a time-domain circuit description, eg, differential equation, to the frequency domain, in which the circuit is described by algebraic rather than differential equations."**

**The map** (f_0211) [0:49:30–0:52:55]. Redraw as two columns:

| time domain | | frequency domain |
|---|---|---|
| differential equations | —— **transform (Laplace/Fourier)** ——→ | algebraic equations |
| ⇣ dotted arrow, "(MUCH HARDER)" | | ↓ solid arrow, "solution" |
| current, voltage vs. time | ←—— **inverse transform** —— | current, voltage vs. frequency |

- "We're typically dealing with linear circuits, so we have linear algebraic equations that are very easy to solve." [0:51:29]
- "It may seem that this is sort of a roundabout way... But in fact, this approach here [the direct time-domain route], once you get beyond very simple input signals, will generally be much harder." [0:52:27–0:52:50]
- Order of topics: Laplace first, then Fourier series and Fourier transforms. [0:50:50–0:51:04]

**Optional video** (f_0230) [0:53:35–0:58:17]: **"Also see: optional video recording on Integral Transforms."** It goes phasors (one frequency) → Fourier series (any periodic signal, by superposition in linear circuits) → Fourier transform (period → ∞, so non-periodic signals) → Laplace transform. The Fourier transform "doesn't allow you to include initial conditions" and "doesn't deal well with... a growing signal." Laplace generalizes the frequency variable to a complex one, which lets you "incorporate... initial conditions" and "treat certain types of growing signals because you can still get the transform integrals to converge." [0:56:34–0:57:25]

### 5. Key mathematical functions and properties [0:58:24–1:12:28]
Board (f_0237): **"Key mathematical functions + properties." "Reading: Ulaby et al, Sec. 12-1."** "There are actually really just two of these that we need to introduce right now." [0:59:23]

**Unit step function** (f_0245) [0:59:36–1:02:03]:
$$u(t)=\begin{cases}0 & t<0\\ 1 & t>0\end{cases}$$
- Plot: green line at 0 for $t<0$, a jump at $t=0$ (dashed vertical), and a green line at 1 for $t>0$.
- **"u(0) can be defined as 0, ½, or 1 depending on circumstances."** Earlier in the semester they took $u(0)=1$ for a switch closing at $t=0$ ("at t equal to zero, the switch was closed"). That "is common but not universal". "If it matters, we'll generally try to be clear... it matters in terms of making the mathematics more rigorous, but practically speaking, it doesn't matter so much." [1:00:40–1:01:52]

**Unit impulse (delta) function** (f_0248, f_0257, f_0262) [1:02:03–1:07:00]. Motivation: if $u(t)$ is a voltage applied to a capacitor, what is its derivative at $t=0$? For $t\neq0$ it is 0. At $t=0$ "it's less clear." [1:02:19–1:02:44] Board: **"unit impulse (or delta) function, δ(t):"**
$$\delta(t)=\begin{cases}0 & t\neq0\\ \infty & t=0\end{cases}\qquad\textbf{and}\qquad\int_{-\infty}^{\infty}\delta(t)\,dt=1$$
- Plot: axes $\delta(t)$ vs $t$, a green line along 0, and a green **upward arrow** at $t=0$.
- Gaussian-limit picture [1:04:32–1:06:56]:
$$\delta(t)=\lim_{a\to0}\frac{1}{|a|\sqrt\pi}\,e^{-(t/a)^2}$$
  "It becomes infinite because of this absolute value of a in the denominator, and... it has zero width because of this a in the denominator of the exponent... the integral of this is one independent of a." So the limit "becomes infinitely narrow and infinitely high" with unit area.

> [!check] Verified (sympy): $\int_{-\infty}^{\infty}\frac{1}{a\sqrt\pi}e^{-(t/a)^2}dt=1$ for every $a>0$, and the peak $1/(a\sqrt\pi)\to\infty$ as $a\to0$.

**Step ↔ impulse** (f_0262) [1:07:01–1:08:47]. If the upper limit of $\int_{-\infty}^{\tau}\delta$ is negative the integral is 0, and if positive it is 1. Board **"NOTE:"**
$$u(t)=\int_{-\infty}^{t}\delta(t')\,dt',\qquad \frac{d}{dt}u(t)=\delta(t)$$
Differentiating an integral with respect to its upper limit gives the integrand. This is "one of the things that makes it useful... when we're using transform techniques more generally." In answer to a student he also wrote $\int_{-\infty}^{t}\delta(x)\,dx$ to show that $t'$ is only a dummy variable (see Student questions).

**Sampling property** (f_0263, f_0268) [1:09:52–1:12:28]. "Very often... it'll come up in a context where it's being multiplied by some other function." Board: **"We can also see that if x(t) is a continuous function of t, then:"**
$$x(t)\,\delta(t)=x(0)\,\delta(t)$$
$$x(t)\,\delta(t-T)=x(T)\,\delta(t-T)$$
$$\int_{-\infty}^{\infty}x(t)\,\delta(t-T)\,dt=x(T)\qquad[\text{"sampling" property of }\delta(t)]$$
The first holds "because the delta function is zero for all values of t... other than zero". The second is a time shift. Integrating both sides gives the third: "taking some function, multiplying it by the delta function, and integrating it basically just picks out the value of that function at the time when the delta function is nonzero." [1:10:48–1:12:17]

> [!note] Added context: the same property is often called the **sifting** property. It needs $x$ continuous at $T$ (he said this), and with finite integration limits the result is $x(T)$ only if $T$ lies inside the limits (otherwise 0). He only wrote the $-\infty$ to $\infty$ form. PS8 problem 12.2 applies this property; it is graded work and is not worked here.

### 6. The Laplace transform: definition [1:12:30–1:17:13]
Board (f_0270): **"Laplace Transform." "Reading: Ulaby et al, Sec 12-2."**

Board (f_0274, f_0279): **"Given a function of time, f(t), its Laplace transform $F(s)\equiv\mathcal L[f(t)]$ is"**
$$\boxed{F(s)\equiv\mathcal L[f(t)]=\int_{0^-}^{\infty}f(t)\,e^{-st}\,dt}\qquad\text{(Laplace transform)}$$
- "Since we're not integrating over s, then this integral will be a function of s, and that function of s is the Laplace transform." $\mathcal L$ is "a script L", the Laplace transform operator. [1:13:54–1:14:59]
- **"$s\equiv\sigma+j\omega$ ($\sigma,\omega\in\mathbb R$) is a complex variable, often called the complex frequency."** "Omega here, as we will see, is the same omega as we have been dealing with." [1:15:01–1:16:03]
- **"The $0^-$ lower limit of integration indicates that the integ[ral can include an initial condition at $t=0$]"**. The bracketed completion is from speech; the last frame stops at "integ". "It's not universally used, but we will sort of use that notation here... And that's how initial conditions come into play, when we use Laplace transforms." [1:16:06–1:17:08]

### 7. Wrap-up [1:17:13–1:17:31]
"We'll pick up with this discussion of Laplace transforms and also inverse Laplace transforms in our next class meeting on Wednesday." No transform pairs, properties or worked transforms were done in this lecture.

---

## Ed Yu's conventions & notation

| Item | His convention (this lecture) |
|---|---|
| Phasors | Under-tilde on every phasor quantity, including $\tilde V_s$, $\tilde V_1$, $\tilde Z_f$, $\tilde Z_s$ **and $\tilde H(\omega)$**. ($\tilde X$ here stands in for his under-tilde.) |
| Inverting stage | $\tilde V_{out}=-\dfrac{\tilde Z_f}{\tilde Z_s}\tilde V_{in}$. He names the feedback impedance $\tilde Z_f$ and the input-side impedance $\tilde Z_s$, and says it can be recalled or rederived "by applying KCL at the inverting input." |
| R∥C simplification | Product over sum, then multiply top and bottom by $j\omega C_f$ (written in green) to reach $R_f/(1+j\omega R_fC_f)$. |
| Standard form | He writes it numerically, $1+j\omega10^{-5}$, and identifies $R_fC_f=1/\omega_0$. Gain prefactor first: $-10^3/(1+j\omega10^{-5})^3$. |
| Naming | "pole frequency $\omega_0$"; "3rd order simple pole @ $\omega_0$"; "pole factor"; "roll off"; "passband"; "stopband"/"band stop"/"band reject region". |
| Cancellation marks | Red strike-throughs on cancelled factors; red "+" written over cancelled minus signs. |
| Bode axes | "Bode magnitude plot: $M(\omega)$ [dB]" and "Bode phase plot: $\phi(\omega)$". Log-ω ticks at exactly $0.1\omega_0$, $\omega_0$, $10\omega_0$, with a dashed vertical at $\omega_0$. Straight-line asymptotes in green. |
| dB | $20\log_{10}|H|$; "log base 10 of 10 to the third is three, so that's gonna be 60 dB." |
| Phase "low/high" | For phase plots, "low frequency" means $<0.1\omega_0$ and "high" means $>10\omega_0$ ("the convention that we use here"). |
| Phase branch | Choose the branch by continuity as $\omega$ increases ($j^3\to270°$, not $-90°$). Otherwise keep the phase "closer to zero", in a range such as $(-180°,180°]$ or $[0°,360°)$; "you can add or subtract some integer multiple of 360 degrees... it's not gonna change anything." A negative real gain is plotted as **+180°**. |
| Unit step | $u(t)=0$ for $t<0$, $1$ for $t>0$. Earlier in the semester $u(0)=1$ (switch closed at $t=0$); $u(0)$ is now "0, ½, or 1 depending on circumstances." |
| Impulse | "unit impulse (or delta) function, δ(t)", drawn as an upward arrow at $t=0$. Dummy integration variable $t'$ (or $x$). |
| Sampling | He calls it the **"sampling" property** (in quotes). |
| Laplace | Capital letter for the transform: $F(s)\equiv\mathcal L[f(t)]$, script $\mathcal L$, lower limit $0^-$ (he says "zero minus"). $s=\sigma+j\omega$ with $\sigma,\omega$ real, called the "complex frequency". |
| Readings named | Ulaby Ch. 12 (overall), §12-1 (key functions), §12-2 (Laplace transform). |

---

## Intuition & explanations he gives

- **Op-amp outputs make cascading clean:** "the output of each stage is at the output of the op amp. So it really is acting as a voltage source. So it can... draw any amount of current, right, within the limits of the ideal op amp model... and they'll still give you the same voltage." So "the transfer functions get multiplied." [0:18:12–0:18:39]
- **Passive cascades load each other:** "If you had a passive circuit that had multiple stages like this... connecting the output of one stage to the next stage would change the behavior of that first stage... you'll start drawing some currents through that terminal... So then you have to analyze the whole thing together." [0:18:39–0:19:47]
- **Each stage adds a pole:** "the main effect of adding this second stage to the circuit is to give you another pole factor... at high frequencies, omega squared in the denominator." Three stages give $\omega^3$, which means a 1000× drop per decade, or −60 dB/dec. [0:21:03, 0:26:33–0:27:30]
- **Why the phase starts at 180°:** as $\omega\to0$ "the phase will be determined by just this factor of minus one... minus one has a phase of 180 degrees." [0:32:39]
- **Why the phase ends at −90°:** the denominator tends to $(j\omega10^{-5})^3$ with phase $\angle j^3$. "Either negative 90 or as two seventy... if you think about how this evolves as omega increases, we wanna take it to be two seventy", and $180°-270°=-90°$. [0:34:08–0:35:07]
- **Design practice:** don't try "to memorize every possible configuration". Know the "basic building blocks... inverting amplifier... summing or a difference... some of the basic filter circuit structures" and build up from them. Intuition comes from "a lot of practice and thinking about it." [0:11:19–0:12:38]
- **Limits of ideal cascading:** the analysis is "in a framework that's largely a DC framework. So we're not worried about... parasitic effects or frequency response... of the op amps." Cascading many stages costs space and power and adds "more parasitics that takes longer for it to respond", so "you can only go so far in... cascading the ideal behaviors and expecting to get the ideal behavior out." [0:27:59–0:29:13]
- **Where to put the gain:** it depends on what you optimize. A senior-design instrument needed about $10^8$ gain with good frequency response; op-amps "can only change their output voltage at a certain rate", so the gain was divided across stages. Another lab amplifier (about $10^{10}$ gain, half-second response acceptable, inside a vacuum system, so compact and low power) used one high-performance op-amp with "a very high value resistor" as an inverting amplifier. [0:29:35–0:31:44]
- **Course arc:** time-domain differential equations (simple inputs) → phasors (one sinusoidal frequency, steady state) → frequency as a parameter (filters) → transforms (arbitrary inputs). [0:41:02–0:47:06]
- **Why transforms pay off:** "you're trading differential equations in the time domain for algebraic equations in the frequency domain", and for linear circuits those are "linear algebraic equations that are very easy to solve". The detour through the frequency domain beats the direct route, which "will generally be much harder." [0:47:36–0:52:50]
- **Why Laplace rather than Fourier:** a complex frequency lets you "incorporate... initial conditions" and "treat certain types of growing signals because you can still get the transform integrals to converge." [0:57:03–0:57:25]
- **What δ really is:** "sort of unintuitive"; think of it as "the limit of... a Gaussian... as the width of the function goes to zero" while "the integral is one or remains finite." [1:04:25–1:05:20]
- **δ is the derivative of the step:** integrate δ to get $u$, then differentiate both sides. [1:07:35–1:08:37]
- **Sampling:** multiplying by δ and integrating "picks out the value of that function at the time when the delta function is nonzero." [1:11:43]
- **The $0^-$ limit:** it is "explicitly reminding us... that the integral can include some initial condition at t equal to zero... that's how initial conditions come into play." [1:16:06–1:17:08]

---

## Emphasis & exam intel

> [!important] **Exam 2 coverage: answered.** Laplace transforms are **not** on Semester Exam 2. He said so three times and drew the boundary on the board. Exam 2 ends at active filters, **including the two posted cascaded-filter videos**, which he called "not optional".

1. **Exam date and place** [0:00:23]: "remember that we have semester exam two coming up on Wednesday, November 11." Board: "the exam, which will be in class on Wednesday 11/11/2026."
2. **Answer-sheet template** [0:00:38–0:00:59]: "the answer sheet template for that exam will be posted hopefully late this week, but definitely by the beginning of next week. And you should make sure, as with the first exam, to bring a copy of the template to the exam. And that'll have to be a hard copy template on which you'll physically write your solutions." Board: "Be sure to bring/prepare a copy of the template for the exam."
3. **Laplace table, final only** [0:01:44–0:02:13]: "there will be handout on Laplace transform pairs that I'll post on Canvas later this week... I will give you a copy of that table for you to use on the final exam, but, of course, you won't have it for the second semester exam because Laplace transforms are not included, in the content on the second, semester exam."
4. **Today's split** [0:02:23–0:02:50]: "finish up our discussion of, active filter circuits, and that will bring us to the end of what's covered on the second semester exam. And then we will start the discussion of circuit analysis using Laplace transforms, which will not be on the second semester exam, but it will be on the final."
5. **The two videos are Exam 2 material** [0:37:07–0:37:31, 0:39:04–0:39:25]: "There are some other examples that I've made recordings of... videos that I will post on Canvas of two additional examples" (cascaded bandpass filter; band-reject filter design). "Including these videos that I've listed here, that is the end of what you were responsible for for the second semester exam. So semester exam two basically covers to this point."
6. **Board line** [0:39:58, f_0179]: "SEMESTER EXAM 2 COVERS TO HERE", placed after "See videos of: cascaded bandpass filter / band reject filter design" and before "Circuit Analysis using Laplace Transforms".
7. **Laplace on the final, not Exam 2** [0:39:28–0:39:41]: "integral transform techniques and specifically Laplace transforms, will be included on the final but not on the second semester exam."
8. **Videos: required vs optional** [0:57:25–0:57:42]: "this video, which is optional, the active filter circuit videos are not optional. You should look at those. But this integral transform video is optional if you are interested." Posting: "I'll post all these sometime, hopefully, today." [0:58:05]
9. **Problem-solving videos** [0:38:53]: "there are the problem solving videos that have been posted for the semester, and there are some examples of these types of filters there as well."
10. **The band-reject design video's task** [0:38:16–0:38:41]: given "the gain, what the stopband is, and what the roll off has to be... design a cascaded filter circuit that actually satisfies all of those conditions." This is the spec-to-circuit shape of a P4 "design ratio" or P2 design question.
11. **Homework** [0:00:10–0:00:23]: PS7 was due 11/02 at 9 AM. "Problem set eight, is due a week from today, so on Monday, November 9" (board: 9:00 AM Central, on Canvas).
12. **The δ/step material is also beyond the Exam 2 line:** §12-1 (unit step, impulse, sampling) was taught after the board boundary, as preliminaries for Laplace. PS8, though, is due before the exam and includes a delta-function problem (12.2). That is a homework obligation, not an Exam 2 topic.
13. **Not mentioned in this lecture:** a review session, PS9, Gradescope, closed-book or calculator rules for Exam 2, or the number and format of problems.

---

## Student questions

| t | Question (reconstructed) | His answer |
|---|---|---|
| 0:03:13 | (Recalled from last class, Nathan) Can first-order stages be combined into a higher-order filter with steeper roll-off? | Yes. Today's first example is that cascade. |
| 0:10:49 | (Jason) Do filter designers memorize standard structures and tune values, or invent new circuits? | "Somewhere in between." Memorizing every configuration isn't practical. Know the building blocks (inverting amp, summing/difference, basic filter structures), build up from them, and develop intuition through practice. |
| 0:17:47 | (Garbled) So each stage's output just goes into the next, and you multiply...? | "The transfer functions get multiplied." Each stage contributes the factor $-Z_f/Z_s$ (feedback over source). This works because each op-amp output acts as a voltage source. |
| 0:19:05 | With passive filters, would the load alter the original circuit? | Yes. The next passive stage draws current from the first stage's output terminal and changes its behaviour, so you must analyse the whole thing together. |
| 0:27:33 | What's the real-world limit? Why not cascade five cheap stages for a near-ideal box? | In principle you could, but it isn't free (space, power). The ideal analysis ignores parasitics and op-amp frequency response, and many stages add parasitics and slow the response. |
| 0:29:22 | Should gain be spread evenly across stages or put in one stage with followers? | It depends on the optimization target. Slew-rate limits favoured splitting the gain in a $10^8$-gain senior-design amplifier. A compact, low-power vacuum-system amplifier ($10^{10}$ gain, slow response OK) used one high-performance op-amp with a very large feedback resistor. |
| 0:34:21 | (He asked the class) What is the phase of $j^3$? | Off-mic answers ("Negative"). Phase of $j$ is 90°, so $j^3$ is −90° or 270°. Take 270° by continuity, giving $180°-270°=-90°$. |
| 0:35:47 | (Jason) If the gain is negative, why start the phase at +180° rather than −180°? | Either works; multiples of 360° change nothing. Starting at −180° just shifts the whole curve by −360°. Conventionally keep the phase near zero, e.g. in $(-180°,180°]$ or $[0°,360°)$. |
| 0:52:58 | So previously the only way from the time domain to the frequency domain was if the signal was a sinusoid? | Right. Transforms let you go to the frequency domain for a much broader set of input signals. |
| 1:08:53 | What is $t'$? Is it the derivative of $t$? | No. $t'$ is just the variable of integration; it could equally be $x$: $\int_{-\infty}^t\delta(x)dx$. The upper limit $t$ is the same $t$ as on the left. The derivative of the integral with respect to its upper limit is the integrand evaluated at that limit. |

---

## Exam relevance

**Laplace and delta material (§§5–6 above): none for Exam 2.** It is explicitly excluded. Save it for the final, where the Laplace-pair table will be provided.

**P4 (active op-amp or RLC filter: $H(\omega)$ in factored standard form, filter type, Bode plots, design ratio): direct, high.** This example is the P4 template:
1. Recognize each stage as an inverting amplifier, so $H_k=-Z_{f,k}/Z_{s,k}$.
2. Reduce $R_f\parallel C_f$ to $R_f/(1+j\omega R_fC_f)$. The pole is at $1/R_fC_f$.
3. Multiply the stage functions (valid for op-amp stages only). Track the sign: an odd number of inverting stages gives a negative overall gain and a 180° phase offset.
4. State the type and order: $K/(1+j\omega/\omega_0)^N$ is an $N$th-order low-pass.
5. Draw the Bode plots: $20\log|K|$ flat, then $-20N$ dB/dec past $\omega_0$; phase from $\angle K$ down by $90N°$ across $0.1\omega_0$–$10\omega_0$.
6. Design ratios here are $R_f/R_s$ (per-stage gain) and $R_fC_f$ (pole). The posted **band-reject filter design** video is the spec-to-component version and is required viewing.

**P3 (filter transfer function + cutoff + Bode): high.** These are the same Bode skills for repeated poles. Watch the cutoff trap: the corner $\omega_0$ is not the −3 dB frequency once poles repeat ($\omega_c=0.510\,\omega_0$ for $N=3$). Keep "corner/pole frequency" and "half-power cutoff" distinct in your answer, and state which you mean.

**P1 (four conceptual short answers on filter concepts): medium-high.** Likely stems this lecture answers:
- *Why can you multiply the transfer functions of cascaded op-amp stages but not of cascaded passive RC sections?* The op-amp output is an ideal voltage source (zero output impedance), so the next stage's current draw does not change $V_1$. A passive section's output voltage depends on its load.
- *Why does adding identical stages steepen the roll-off?* Each stage adds a pole factor, so the high-frequency gain falls as $\omega^{-N}$, i.e. $-20N$ dB/decade.
- *Why does the phase of $-K/(1+j\omega/\omega_0)^3$ go from 180° to −90°?* The $-1$ contributes 180° and each pole contributes 0° → −90°, giving $180°-270°$.
- *Why not cascade indefinitely?* Ideal-model limits: parasitics, op-amp bandwidth and slew rate, power and space.

**P2 (passive filter design or max power transfer): low.** The one link is the loading caveat: passive stages cannot simply be multiplied; the whole network must be solved.

---

## Common mistakes / traps

- **Misreading stage 1's 10 Ω as 10 kΩ.** That would give 0 dB DC gain instead of 60 dB. Read component values off the board carefully.
- **Dropping the overall sign.** Three inverting stages give $(-1)^3=-1$, so the phase plot starts at ±180°, not 0°. Two stages give $+1$, starting at 0°.
- **Using −20 dB/decade for a cascade.** The slope is $-20N$ dB/dec for $N$ identical poles (−60 here).
- **Phase span.** $N$ poles drop the phase by $90N°$ in total (270° here), at a straight-line slope of $-45N°$/decade between $0.1\omega_0$ and $10\omega_0$, not −90° total.
- **Phase wrap mistakes.** Choose the branch by continuity ($j^3\to270°$). Writing "+270°" at high frequency, or jumping from +180° to −90° discontinuously, misreads the plot. Any constant ±360° shift of the whole curve is fine.
- **Calling $\omega_0$ the −3 dB cutoff for repeated poles.** At $\omega_0$ a triple pole is 9.03 dB down. The half-power point is $0.510\,\omega_0$.
- **Assuming passive cascades multiply.** Only buffered (op-amp-output) stages do.
- **dB for voltage ratios uses $20\log_{10}$**, not $10\log_{10}$.
- **(Final, not Exam 2)** $\delta(0)$ is not "1". The **area** is 1. $u(0)$ is convention-dependent.
- **(Final)** The sampling property needs $x$ continuous at $T$, and $T$ must lie inside the integration limits.
- **(Final)** The Laplace lower limit is $0^-$, not $0$ or $-\infty$. It is what lets impulses and initial conditions at $t=0$ count.
- **Study-time trap:** don't spend Exam 2 prep on Laplace. Do finish PS8 (due 11/09), which contains delta-function integrals.

---

## Self-check

**Q1 (P4 style).** Two cascaded inverting stages. Stage 1 has input resistor 1 kΩ and feedback 10 kΩ ∥ 10 nF. Stage 2 has input resistor 10 kΩ and the same feedback. Give $\tilde H(\omega)$ in factored standard form, the filter type and order, the DC gain in dB, the asymptotic roll-off, the low- and high-frequency phase, and the exact $|H|$ (dB) and phase at $\omega_0$.

> [!question]- Answer
> $\omega_0=1/(10^4\cdot10^{-8})=10^4$ rad/s. Stage gains are $-10/(1+j\omega/10^4)$ and $-1/(1+j\omega/10^4)$, so
> $$\tilde H(\omega)=\frac{+10}{(1+j\omega10^{-4})^2}$$
> This is a second-order low-pass. DC gain $20\log_{10}10=20$ dB. Roll-off −40 dB/decade above $10^4$ rad/s. Phase 0° at low frequency (two inversions cancel), falling to −180° at high frequency. At $\omega_0$: $20-20\log_{10}2=13.98$ dB and −90°. (python3 verified.)

**Q2 (P3 trap).** For the lecture's $\tilde H(\omega)=-10^3/(1+j\omega10^{-5})^3$, what are $|H|$ and $\angle H$ exactly at $\omega=10^5$ rad/s, and where is the −3 dB frequency?

> [!question]- Answer
> $|1+j|^3=2^{3/2}$, so $|H|=10^3/2.828=353.6$, i.e. $60-30\log_{10}2=50.97$ dB (9.03 dB below the corner of the asymptotes). $\angle H=180°-3(45°)=45°$. The −3 dB point solves $(1+x^2)^{3/2}=\sqrt2$, giving $x=\sqrt{2^{1/3}-1}=0.510$. So $\omega_c=5.10\times10^4$ rad/s (8.11 kHz), not $10^5$. (python3 and ngspice verified.)

**Q3 (P1 style).** Why could Prof. Yu multiply the three stage transfer functions, and what goes wrong if you do the same with three cascaded passive RC low-pass sections?

> [!question]- Answer
> Each stage's output is an ideal op-amp output, which behaves as an ideal voltage source: it can supply whatever current the next stage draws without its voltage changing. So $V_1$ is the same whether or not stage 2 is attached, and $H=H_1H_2H_3$. A passive RC section's output voltage depends on the current drawn from it. Attaching the next section loads it and changes $V_1$, so the product of the unloaded transfer functions is wrong and the whole network must be solved together (0:18:20–0:19:47).

**Q4 (P1/P4).** On his phase plot for $-10^3/(1+j\omega/\omega_0)^3$, why does the curve end at −90° rather than +270°, and would starting at −180° be wrong?

> [!question]- Answer
> The $-1$ contributes 180°. As $\omega\to\infty$ the denominator behaves like $(j\omega/\omega_0)^3$, whose angle grows continuously from 0° to 270° as $\omega$ increases. Subtracting gives $180°-270°=-90°$. Writing "−90°" for $\angle j^3$ would break continuity with how the angle evolves. Starting at −180° is not wrong: it shifts the whole curve by −360° (ending at −450°), which is the same phase. He prefers keeping values near zero.

**Q5 (final exam only, not Exam 2).** Evaluate $\int_{-\infty}^{\infty}\cos(\pi t)\,\delta(t-1)\,dt$ and $\int_{-\infty}^{\infty}(t^2+1)\,\delta(t+2)\,dt$. Then use the definition with its $0^-$ limit to find $\mathcal L[\delta(t)]$, and say what changes if the lower limit were $0^+$.

> [!question]- Answer
> By the sampling property, $\cos(\pi\cdot1)=-1$ and $(-2)^2+1=5$. $\mathcal L[\delta(t)]=\int_{0^-}^{\infty}\delta(t)e^{-st}dt=e^{0}=1$, because the impulse at $t=0$ lies inside $[0^-,\infty)$. With a $0^+$ lower limit the impulse would be excluded and the integral would be 0. That is why he insists on $0^-$: whatever happens at $t=0$ (impulses, initial conditions) is kept. (sympy verified. The pair $\mathcal L[\delta]=1$ was not derived in lecture; it is added context.)

---

> [!summary] Board-error audit
> No arithmetic or sign errors on the board. Every number was re-derived with python3 and the transfer function was checked with ngspice AC: $\omega_0=10^5$ rad/s, $10^4/10=10^3$, 60 dB, −60 dB/dec, 180° → −90°, and the Gaussian integral = 1.
> **Speech slips:** "subtract from the phase of zero" (0:33:39; the phase starts at 180°); "from minus one eighty... down to 180 minus two seventy" (0:36:11; should be −450° ≡ −90°).
> **ASR errors:** "poll" → pole (0:24:11); "x of t" → $x(T)$ (1:11:39); "a regulator sigma" → σ (1:15:11); "(RF?)" → $R_f$ (0:10:02).
> **Terminology note:** "3rd order simple pole" means a triple real pole.
> **Missing frame:** the final board sentence (the $0^-$ meaning) is completed from speech only.
