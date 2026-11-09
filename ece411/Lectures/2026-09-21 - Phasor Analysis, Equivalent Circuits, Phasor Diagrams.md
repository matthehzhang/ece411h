---
course: ECE 411H
date: 2026-09-21
instructor: Prof. Ed Yu
topic: Phasor analysis worked example (RL), impedance transformations & equivalent circuits in the phasor domain, phasor diagrams (series RLC)
reading: Ulaby/Maharbiz/Furse 3e §7-5, §7-6, §7-7
source: Recordings/2026-09-21 (transcript + 55 tablet frames)
tags: [ece411, lecture, phasors, impedance, thevenin, phasor-diagram, exam1]
---

# 2026-09-21: Phasor Analysis, Equivalent Circuits, Phasor Diagrams

## Summary

- **The 5-step phasor recipe, worked end to end on an RL circuit** with a *sine*-form source: (1) convert to cosine form, (2) transform the source, the impedances and the unknowns to the phasor domain, (3) analyze with KVL/KCL, (4) solve for the unknown phasor in polar form, (5) convert back with $v(t)=\mathrm{Re}[\tilde V e^{j\omega t}]$. Result: $v_L(t)=12\cos(4\times10^4t-83.1^\circ)$ V.
- **Units caution:** $\omega t$ is in radians, the phase is in degrees. You mix them in one cosine argument, and that is deliberate.
- **Phasors need a single frequency.** Several sources at different frequencies require superposition (linear circuits only), one frequency at a time.
- **Everything from 302/302H carries over** (series/parallel combination, voltage and current division, source transformations, Thevenin/Norton) **because KCL and KVL hold for phasors.** Replace $R$ with $\tilde Z$.
- **Source transformation:** derived by matching the linear I–V relations at the port. $\tilde V_s=\tilde I_s\tilde Z_s$ and $\tilde I_s=\tilde V_s/\tilde Z_s$, with $\tilde Z_s$ unchanged.
- **Thevenin:** $\tilde V_{Th}=\tilde V_{oc}$. $\tilde Z_{Th}=\tilde V_{oc}/\tilde I_{sc}$ (short-circuit method) fails as 0/0 when $\tilde V_{oc}=0$. In that case use $\tilde Z_{Th}=\tilde V_{ex}/\tilde I_{ex}$ (external-source method) with the independent sources off. Norton is analogous. He previewed max power transfer: $Z_L=Z_s^*$.
- **Phasor diagrams** plot voltage and current phasors as vectors in the complex plane. Series RLC example: $\tilde I=2e^{j66.9^\circ}$, $\tilde V_R=16e^{j66.9^\circ}$, $\tilde V_C=16e^{-j23.1^\circ}$, $\tilde V_L=4e^{j156.9^\circ}$. **$V_R\parallel I$, $V_C\perp I$, $V_L\perp I$, and $V_L$ and $V_C$ are 180° apart.**
- **Absolute vs relative phasor diagrams:** the relative diagram rotates every phasor by one common angle (here so that $\tilde I$ lies on the real axis), which makes the 90°/180° relationships obvious.

---

## Content

### 0. Announcements [0:00:19–0:04:02]
- PS3 was due this morning. PS4 (posted Wed 09/16) is due **Mon Sep 28** and covers sinusoidal signals, complex-number basics and phasor analysis of circuits.
- Today's afternoon slot is **Lab 2**, not recitation.
- Canvas handout #1 covers complex numbers and complex algebra. Handout #2, coming later, covers rational functions of complex numbers for transfer functions.
- No class or office hours Wed Sep 23 because of travel. A recorded lecture replaces it; watch it before Mon Sep 28.
- **Semester Exam 1: Wed 10/07/2026, in person, closed book, closed notes, calculator without communication ability (no phone).** He will post an *answer-sheet template*. Print it, bring it, and write on it, **not on a tablet**. Details on format, turn-in and coverage will be posted closer to the date. **Coverage goes "partway through next week's classes."** [0:02:20–0:03:41]

### 1. Recap and plan [0:05:45–0:07:11]
- Last recording covered the phasor idea, complex impedances of the elements, and the outline of the phasor-analysis steps.
- Today: (a) a simple worked example, (b) impedance and source transformations and equivalent circuits in the phasor domain, (c) phasor diagrams for visualizing phase relationships "graphically rather than algebraically, or in addition to algebraically."

### 2. Example: RL circuit phasor analysis [0:07:11–0:30:32]

**Circuit (frames f_0021, f_0026):** single loop. The independent voltage source $v_s(t)$ is on the left edge with + at the top. Resistor $R$ sits on the top wire. Current $i$ is referenced clockwise (arrow pointing right on the top wire, after $R$). Inductor $L$ is on the right edge with $v_L(t)$ referenced + at top and − at bottom (passive sign convention with $i$). The bottom wire returns to the source.

**Given:** $v_s(t)=15\sin(4\times10^4t-30^\circ)$ V, $R=3\ \Omega$, $L=0.1$ mH. **Find $v_L(t)$.**

**Step 1: convert $v_s(t)$ to cosine form** [0:09:10]

$$\sin(x)=\cos(x-90^\circ)\;\Rightarrow\;v_s(t)=15\sin(4\times10^4t-30^\circ)=15\cos(4\times10^4t-120^\circ)\ \text{V};\qquad \omega=4\times10^4\ \text{rad/s}$$

He states this step is needed because "this signal is not specified in the usual cosine form." The cosine form "allows us to see immediately what the phase angle is."

> [!note] Board box (f_0038): "CAUTION: notice that we are mixing radians ($\omega t$) and degrees ($-120^\circ$). It will be typical to refer to $\omega$ in rad/s, but phase shifts in degrees." [0:12:53]

**Step 2: transform to the phasor domain** [0:13:53]

$$\tilde V_s=15e^{-j120^\circ};\quad \tilde Z_R=R;\quad \tilde Z_L=j\omega L;\quad i(t)\to\tilde I;\quad v_L(t)\to\tilde V_L$$

The unknowns become phasors, and at the end "we will have to convert that back to the time domain."

**Step 3: analyze in the phasor domain** [0:15:48, 0:18:24]. KVL around the loop:

$$R\tilde I+j\omega L\,\tilde I=\tilde V_s\;\Rightarrow\;\tilde I=\frac{1}{R+j\omega L}\tilde V_s$$

Then $\tilde V_L=j\omega L\,\tilde I$.

**Step 4: solve for $\tilde V_L$** [0:20:05]

$$\tilde I=\frac{1}{3+j(4\times10^4)(10^{-4})}\left(15e^{-j120^\circ}\right)=\frac{15e^{-j120^\circ}}{3+j4}$$

*Rectangular → polar* [0:22:53]. He plots $3+j4$ in the complex plane (Re on the horizontal axis, Im on the vertical) and draws the vector from the origin (f_0077, f_0087).
- Magnitude: $\sqrt{3^2+4^2}=\sqrt{25}=5$ ("a 3-4-5 triangle").
- Angle: $\tan^{-1}(4/3)$ "the inverse tangent of the imaginary part over the real part" $\approx 53.1^\circ$.

$$\tilde I=\frac{15e^{-j120^\circ}}{5e^{j\tan^{-1}(4/3)}}=\frac{15e^{-j120^\circ}}{5e^{j53.1^\circ}}=3e^{-j173.1^\circ}$$

He explains the angle step: $e^{j53.1^\circ}$ in the denominator becomes $e^{-j53.1^\circ}$ in the numerator, then you add the exponents.

[0:26:48] Inductor voltage:

$$\tilde V_L=j\omega L\,\tilde I=j(4\times10^4)(10^{-4})\cdot3e^{-j173.1^\circ}=12\,e^{j90^\circ}e^{-j173.1^\circ}=\underline{12e^{-j83.1^\circ}}$$

The key move is $j=e^{j90^\circ}$: "because it's purely imaginary, that means it's vertical in the complex plane... its phase angle is 90 degrees, and it has magnitude 1." [0:27:43]

**Step 5: convert to the time domain** [0:28:55]

$$v_L(t)=\mathrm{Re}\!\left[\tilde V_L e^{j\omega t}\right]=\mathrm{Re}\!\left[12e^{-j83.1^\circ}e^{j\omega t}\right]\;\Rightarrow\;\boxed{v_L(t)=12\cos(4\times10^4t-83.1^\circ)\ \text{V}}$$

> [!check] Verified (python3 + ngspice AC at $f=\omega/2\pi=6366.2$ Hz): $\tilde I=3.000\angle-173.13^\circ$ A and $\tilde V_L=12.000\angle-83.13^\circ$ V. A time-domain check, $L\,di/dt$ of $i(t)=3\cos(\omega t-173.13^\circ)$, matches $12\cos(\omega t-83.13^\circ)$ to 7 digits. Board numbers are correct. **No board error.**
>
> *Self-checks (mine, not his):* $\tilde V_R=9e^{-j173.1^\circ}$ and $\tilde V_R+\tilde V_L=15e^{-j120^\circ}=\tilde V_s$ ✓. $v_L$ leads $i$ by exactly $90^\circ$ ($-83.1-(-173.1)=90$) ✓. $|\tilde V_R|^2+|\tilde V_L|^2=81+144=225=15^2$ ✓.

### 3. Impedance transformations and equivalent circuits [0:32:47–0:55:01]
Heading on the board (f_0125): **"Impedance Transformations and Equivalent Circuits." Reading: Ulaby et al., Secs. 7-5 and 7-6.**

**Core claim** (board, f_0128): "Since KCL and KVL are valid for phasors, the circuit rules, techniques, etc. from 302/302H carry over to phasors as well." [0:34:09]

**Impedances in series** (f_0135). Box chain $\tilde Z_1,\tilde Z_2,\dots,\tilde Z_N$ between two terminals [0:35:25]:
$$\tilde Z_{eq}=\sum_{l=1}^{N}\tilde Z_l$$
Reason: series elements carry the same current and their voltages add. "If you just work out the consequences of that... you pretty directly get" the sum, the same derivation as for resistors. [0:36:29]

**Impedances in parallel** (f_0135). $\tilde Z_1\ldots\tilde Z_N$ between a top bus and a bottom bus, one terminal on each bus [0:37:15]:
$$\frac{1}{\tilde Z_{eq}}=\sum_{l=1}^{N}\frac{1}{\tilde Z_l}$$

**Board statement** (f_0140): "Concepts of voltage and current division apply to impedances just as they applied to resistances in 302/302H." [0:38:23]

#### Source transformations [0:39:26–0:46:42]
**Circuits (f_0148):**
- *Left, the "realistic voltage source":* $\tilde V_s$ (+ on top) in series with a box $\tilde Z_s$ on the top wire, leading to the + output terminal. The bottom wire runs straight to the − terminal. Port current $\tilde I$ points out of the + terminal (to the right), and port voltage $\tilde V$ is + top / − bottom.
- *Right, the "realistic current source":* ideal $\tilde I_s$ (arrow **up**, toward the top node) in parallel with $\tilde Z_s$, both between the top and bottom rails. The top rail goes to the + terminal with $\tilde I$ pointing out (right), and $\tilde V$ is + top.
- They are equivalent when "the relationship between the current and the voltage at the output terminals has to be the same for both."

**Derivation (every step, f_0162):**
- Voltage-source form: the terminal voltage is the source minus the drop across $\tilde Z_s$:
$$\tilde V=\tilde V_s-\tilde I\tilde Z_s\quad\Longleftrightarrow\quad \tilde I=\frac{\tilde V_s}{\tilde Z_s}-\frac{\tilde V}{\tilde Z_s}$$
- Current-source form: the terminal current is the source current minus the current down the $\tilde Z_s$ branch, which is $\tilde V/\tilde Z_s$:
$$\tilde I=\tilde I_s-\frac{\tilde V}{\tilde Z_s}\quad\Longleftrightarrow\quad \tilde V=\tilde I_s\tilde Z_s-\tilde I\tilde Z_s$$
- Both are linear I–V relations, so **match the constant term and the slope** [0:43:48–0:46:33]:
  - Current → voltage: constant terms $\tilde V_s\leftrightarrow\tilde I_s\tilde Z_s$, so **$\tilde V_s=\tilde I_s\tilde Z_s$**. Slopes match, so **$\tilde Z_s$ is unchanged**.
  - Voltage → current: constant terms $\tilde I_s\leftrightarrow\tilde V_s/\tilde Z_s$, so **$\tilde I_s=\tilde V_s/\tilde Z_s$**. Slope $1/\tilde Z_s$ is the same, so **$\tilde Z_s$ is unchanged**.

#### Thevenin equivalent circuits [0:46:56–0:53:39]
**Circuits (f_0166/f_0170):** on the left, a cloud labeled "actual linear circuit" with two terminals, $\tilde I$ out of the top (+) terminal and $\tilde V$ + top / − bottom. On the right, $\tilde V_{Th}$ (+ top) in series with $\tilde Z_{Th}$ on the top wire, leading to the + terminal, with the same $\tilde I$ and $\tilde V$ references.

**Idea:** the I–V relation at the terminals of a linear circuit is linear, so "any circuit configuration that will give us this linear relation with sufficient generality will suffice." Thevenin picks a source in series with an impedance. [0:47:45–0:48:37]

**Results (f_0182):**
- **$\tilde V_{Th}=\tilde V_{oc}$ of the actual linear circuit.** With the terminals open, $\tilde I=0$, so there is no drop across $\tilde Z_{Th}$ and $\tilde V=\tilde V_{Th}$. [0:49:05]
- **$\tilde Z_{Th}=\tilde V_{oc}/\tilde I_{sc}$ (short-circuit method).** Wire the terminals together. The same $\tilde I_{sc}$ must flow in both circuits, so $\tilde Z_{Th}=\tilde V_{Th}/\tilde I_{sc}$. [0:50:06]
  - **Caveat** [0:51:23]: this "only works if the open-circuit voltage is non-zero." If $\tilde V_{oc}=0$ then $\tilde I_{sc}=0$ too, and you get "zero over zero, which is undefined."
- **$\tilde Z_{Th}=\tilde V_{ex}/\tilde I_{ex}$ (external-source method).** Attach an external current *or* voltage source to the terminals and "turn off, that is set to zero, the Thevenin voltage... which is equivalent to turning off all of the independent sources." Then $\tilde Z_{Th}$ is the ratio of terminal voltage to current. [0:51:47–0:52:54]

  > [!note] Mine, not his: "turn off" means *independent* sources only (V source → short, I source → open). Dependent sources, including op-amp models, stay in. He said "independent", so keep that word in a written answer.
- Board (f_0191): **"Norton equivalent circuits generalize to phasors in an analogous way."** [0:52:56]

### 4. Phasor diagrams [0:55:07–1:19:11]
Heading (f_0200): **"Phasor diagrams." Reading: Ulaby et al., Sec. 7-7.**

**Definition (board, f_0203):** "A **phasor diagram** shows voltages and/or currents as vectors in a two-dimensional complex plane, and can be helpful in visualizing phase/magnitude relationships among circuit quantities." Re is on the horizontal axis and Im on the vertical. [0:56:11–0:57:27]

Motivation [0:55:07]: so far phasors were handled "as algebraic quantities, but a lot of times if we're thinking about the phase then it can be easier to understand and visualize what's happening if we have some geometric representation."

#### Example: phasor diagrams for a series RLC circuit [0:57:35]
**Circuit (f_0217):** single loop. $v_s(t)$ is on the left edge with + at top. $R$ sits on the top wire with $v_R$ + left / − right. Current $i$ is clockwise (arrow pointing right on the top wire). $C$ is on the right edge with $v_C$ + top / − bottom. $L$ is on the bottom wire with $v_L$ **+ on the right, − on the left**. All three use the passive sign convention with the clockwise $i$.

**Given:** $v_s(t)=20\cos(500t+30^\circ)$ V, so $\omega=500$ rad/s. $R=8\ \Omega$, $C=0.25$ mF, $L=4$ mH. (The transcript says "millihertz", an ASR error. The board says mF.)

**Phasor domain** [1:00:22]. He boxes the quantities that will be plotted:
- $\boxed{\tilde V_s=20e^{j30^\circ}}$, and $i(t)\to\tilde I$
- $\tilde Z_R=8\ \Omega$
- $\tilde Z_C=\dfrac{1}{j\omega C}=\dfrac{1}{j(500)(0.25\text{ mF})}=-j8\ \Omega$. His mental arithmetic: $500\times10^{-3}=\tfrac12$, $0.25=\tfrac14$, so the denominator is $j\cdot\tfrac18$. The reciprocal of $\tfrac18$ is 8 and the reciprocal of $j$ is $-j$. [1:01:26]
- $\tilde Z_L=j\omega L=j(500)(4\text{ mH})=j2\ \Omega$ ($500\times4=2000$, times $10^{-3}$ gives 2) [1:02:47]

**KVL** [1:03:29] (f_0265, f_0284):
$$(\tilde Z_R+\tilde Z_C+\tilde Z_L)\tilde I=\tilde V_s\;\Rightarrow\;(8-j8+j2)\tilde I=\tilde V_s$$
$$\tilde I=\frac{1}{8-j6}\tilde V_s=\frac{20e^{j30^\circ}}{8-j6}=\frac{20e^{j30^\circ}}{10e^{-j\tan^{-1}(6/8)}}=2e^{j30^\circ}e^{j36.9^\circ}=\boxed{2e^{j66.9^\circ}=\tilde I}$$
- $|8-j6|=10$, "either from the 3-4-5 triangle multiplied by 2 or the Pythagorean theorem." [1:05:58]
- Angle: $\tan^{-1}(-6/8)$, but "we can take the minus sign out of the inverse tangent," which gives $e^{-j\tan^{-1}(3/4)}$. Moving it to the numerator flips the sign, and $\tan^{-1}(6/8)=36.9^\circ$. [1:06:12–1:07:18]

**Element voltages** [1:07:58] (f_0364):
$$\tilde V_R=R\tilde I=(8\ \Omega)\cdot2e^{j66.9^\circ}=\boxed{16e^{j66.9^\circ}=\tilde V_R}$$
$$\tilde V_C=\frac{1}{j\omega C}\tilde I=(-j8\ \Omega)\cdot2e^{j66.9^\circ}=16e^{-j90^\circ}e^{j66.9^\circ}=\boxed{16e^{-j23.1^\circ}=\tilde V_C}$$
($-j=e^{-j90^\circ}$, "because it's a vector pointing directly downward in the complex plane" [1:09:14].)
$$\tilde V_L=j\omega L\,\tilde I=(j2)\cdot2e^{j66.9^\circ}=4e^{j90^\circ}e^{j66.9^\circ}=\boxed{4e^{j156.9^\circ}=\tilde V_L}$$

> [!check] Verified (python3 + ngspice AC at $f=79.577$ Hz): $\tilde I=2.000\angle66.87^\circ$, $\tilde V_R=16.00\angle66.87^\circ$, $\tilde V_C=16.00\angle-23.13^\circ$, $\tilde V_L=4.000\angle156.87^\circ$. All board values are correct to 3 s.f. **No board error.**
>
> *Self-checks (mine):* $\tilde V_R+\tilde V_C+\tilde V_L=20\angle30^\circ=\tilde V_s$ ✓ (KVL closes). **Magnitudes do not add:** $16+16+4=36\neq20$. Instead $|\tilde V_s|^2=|\tilde V_R|^2+(|\tilde V_C|-|\tilde V_L|)^2=256+144=400$ ✓. $\omega_0=1/\sqrt{LC}=1000$ rad/s $>\omega=500$, so $|Z_C|>|Z_L|$, the circuit is net capacitive, and $\tilde I$ *leads* $\tilde V_s$ by $36.9^\circ$. These make good physical-check lines on an exam.

**Absolute phasor diagram** [1:11:11–1:15:00] (f_0456 → f_0475 left). Every phasor is plotted at its computed angle:
- $\tilde V_R$ (black) and $\tilde I$ (red, shorter) are **parallel** at $66.9^\circ$. "They have different magnitudes here, 16 for $V_R$, 2 for the current. We're being a little bit sloppy here because we are comparing numbers that have different units, which you're not really supposed to do. But for our purposes now... the main thing... is that they're parallel." [1:12:04–1:12:32]
- $\tilde V_s$ at $30^\circ$.
- $\tilde V_C$ in the 4th quadrant at $-23.1^\circ$.
- $\tilde V_L$ in the 2nd quadrant at $156.9^\circ$, which he labels as "$66.9^\circ$ from the vertical."
- Green right-angle marks show $\tilde V_R\perp\tilde V_C$ and $\tilde V_R\perp\tilde V_L$.

Observation [1:15:11]: "66.9 plus 23.1 is 90 degrees," so $\tilde V_R$ (and $\tilde I$) is $90^\circ$ from $\tilde V_C$ and also $90^\circ$ from $\tilde V_L$, "and so that means that the voltage across the capacitor and across the inductor are 180 degrees out of phase." The catch is that "we had to stare at it a little bit and look at the numbers."

**Relative phasor diagram** [1:16:22–1:19:03] (f_0475 right). Rotate **all** vectors by a fixed angle, chosen "to highlight some of the phase relationships that we would like to highlight." Here everything rotates **clockwise by $66.9^\circ$**, which puts $\tilde V_R$ and $\tilde I$ on the +Re axis:
- $\tilde I$ (red) and $\tilde V_R$ lie along +Re.
- $\tilde V_s$ sits at $-36.9^\circ$.
- $\tilde V_C$ points **straight down** ($-90^\circ$).
- $\tilde V_L$ points **straight up** ($+90^\circ$).
- Board label: "relative phasor diagram (here, phases shown relative to $\tilde I$)." "We can rotate the phasors by any angle that we want... we can choose something else if we wanted to."

---

## Ed Yu's conventions & notation

| Item | His convention (this lecture) |
|---|---|
| Phasor symbol | **Tilde *below*** the letter: $\underset{\sim}{V}_s$, $\underset{\sim}{I}$, $\underset{\sim}{Z}_L$. Not a tilde above (it clashes with vector arrows) and not boldface (hard to handwrite). He may drop the tilde "if it's clear from the context that it is a phasor." Spoken as "I twiddle." [0:04:37–0:05:24] (In this note $\tilde{X}$ stands in for his under-tilde.) |
| Impedance | Also under-tilde: $\tilde Z_R=R$, $\tilde Z_L=j\omega L$, $\tilde Z_C=1/(j\omega C)$. He writes the value with units: "$-j8\ \Omega$", "$j2\ \Omega$". Admittance was not used this lecture. |
| Reference waveform | **Cosine.** Any sine is converted first with $\sin x=\cos(x-90^\circ)$. |
| Amplitude | **Peak amplitude** (not rms): $15\cos(\cdot-120^\circ)\to15e^{-j120^\circ}$, $20\cos(\cdot+30^\circ)\to20e^{j30^\circ}$. |
| Polar form | **Exponential form $Ae^{j\theta}$ with $\theta$ in degrees** (e.g. $3e^{-j173.1^\circ}$). The $\angle$ notation never appeared. He writes $j=e^{j90^\circ}$ and $-j=e^{-j90^\circ}$ explicitly as factors and combines exponents. |
| Back to time domain | $v(t)=\mathrm{Re}[\tilde V e^{j\omega t}]$, written out every time, then the boxed final answer **with units** ("V"). |
| Angle units | $\omega$ in **rad/s**, phase shifts in **degrees**, mixed inside one argument ($4\times10^4t-83.1^\circ$). |
| Precision | **3 significant figures** on exams (53.1°, 36.9°). Keep a decimal on 3-digit angles (120.7°) so that a later 2-digit result still has 3 s.f. |
| Polar conversion | Plot the number in the complex plane, magnitude by Pythagoras (or spotting 3-4-5), angle $=\tan^{-1}(\text{Im}/\text{Re})$. He pulls the minus sign out: $\tan^{-1}(-6/8)=-\tan^{-1}(3/4)$. |
| Reference directions | Passive sign convention on every element (+ where the reference current enters). Loop current is clockwise. For two-terminal equivalents (source transformation, Thevenin), $\tilde I$ points **out of the + terminal** and $\tilde V$ is + on top. |
| KVL form | "Sum of element drops = source": $(\tilde Z_R+\tilde Z_C+\tilde Z_L)\tilde I=\tilde V_s$. |
| Names he uses | "realistic voltage source configuration" / "realistic current source configuration"; "actual linear circuit"; "short-circuit method"; "external source method"; "open-circuit voltage $\tilde V_{oc}$", "short-circuit current $\tilde I_{sc}$", "$\tilde V_{ex}$, $\tilde I_{ex}$"; "absolute phasor diagram" / "relative phasor diagram"; "302 or 302H" for the prerequisite. |
| Boxing | He boxes final results and the quantities to be plotted. |

---

## Intuition & explanations he gives

- **Why convert to cosine first:** the standard cosine form "allows us to see immediately what the phase angle is, so we can write it as a phasor." [0:11:01]
- **Why radians for $\omega$ but degrees for phase:** "radians are kind of the natural unit for angles, so that when you take the sine or the cosine and its derivatives... it works out the way that you want without some extraneous numerical factor in front. But for the phase angles we will typically use degrees... because we have much more intuition for what 120 degrees looks like versus what 2.3 radians [looks like]." [0:11:30–0:12:15]
- **Phasors vs time-domain analysis:** the earlier time-domain methods "were not restricted to just sinusoidal signals" (steps, exponentials). "Phasors are specifically for sinusoidal signals," meaning AC "with a fixed and specified frequency." Later, by superposition, "you can construct ultimately almost any kind of signal by taking a superposition of sinusoidal signals at different frequencies." [0:17:05–0:18:21]
- **DC is the trivial limit:** with non-time-varying signals "it's essentially a steady-state situation, so a capacitor will behave as an open circuit, an inductor as a short circuit, and all you'll have are sources and resistors." [0:16:34]
- **Why every signal shares one frequency:** "ultimately all the signals in a circuit... come from the independent sources," so if the source is at $\omega$, "all the other signals will have that same frequency." With several sources at different frequencies "you would not be able to analyze the whole thing all at once using phasors," so use superposition, one source at a time. "It would have to be a linear circuit... because superposition only works for linear systems." [0:31:11–0:32:39]
- **Why the 302 toolbox carries over:** "KCL and KVL can be applied in their usual form for phasors, and therefore everything that depends on KCL and KVL... which is just about everything that we do with circuits... will carry over as well." [0:34:09–0:34:33]
- **Series rule reason:** the voltages of series components add to the total voltage and the currents are the same; "work out the consequences of that" and you get $\sum\tilde Z$, the same derivation as for resistors. [0:36:29]
- **Equivalent circuit = same port I–V line:** "these being equivalent circuits means that the relationship between the current and the voltage at the output terminals has to be the same." For source transformations, match "the constant term" and "the slope." [0:40:40, 0:44:44–0:46:26]
- **Thevenin rationale:** the port relation of a linear circuit is linear, so "any circuit configuration that will give us this linear relation with sufficient generality will suffice." Thevenin picks a source plus a series impedance. [0:47:49–0:48:19]
- **Why the short-circuit method can fail:** with $V_{oc}=0$, $I_{sc}=0$, which gives "zero over zero, which is undefined." Use an external source instead. [0:51:28]
- **Why AC power is trickier (preview):** "for power you're multiplying current and voltage, so if you're taking a complex representation of the current and the complex representation of the voltage, you have to be a little bit careful about how you multiply them together." [0:54:29–0:54:52]
- **$j$ as a rotation:** $j$ "is purely imaginary, that means it's vertical in the complex plane, so its phase angle is 90°, and it has magnitude 1." $-j$ is "a vector pointing directly downward." [0:27:43, 1:09:14]
- **What a phasor diagram buys you:** it makes "the phase and to some degree the magnitude relationships" visible. In the series RLC, $V_R\parallel I$, while $V_C$ and $V_L$ are each at $90^\circ$ to $I$ and so at $180^\circ$ to each other. The relative diagram (rotated so $\tilde I$ is horizontal) makes "the 90 degree phase relationships and also the fact that the voltage across the capacitor and the inductor are 180 degrees out of phase... much more obvious." [1:15:11–1:18:27]
- **Units caveat on diagrams:** putting $\tilde I$ (A) and $\tilde V_R$ (V) on one plot compares "numbers that have different units, which you're not really supposed to do." What carries meaning is the *direction* (phase), not the relative length between V and I. [1:12:18]

---

## Emphasis & exam intel

1. **Exam logistics** [0:02:20–0:03:41]: "Wednesday, October 7th... in person here in this room... closed book and closed notes, and you'll be allowed to use a calculator, anything without communication abilities, so no using your phone as a calculator." Write on the posted answer-sheet template, "not on a tablet." "The material that you will be responsible for will go partway through next week's classes."
2. **Significant figures** [0:26:04]: "On exams and such, usually... I'll specify you should do things to **three significant figures**." For 3-digit angles, "it's probably better to keep that point 7, so that in the end, if it ends up being a two-digit degree number, you'll still have that third significant figure."
3. **CAUTION, mixed angle units** (boxed on the board, f_0038) [0:12:53]: "notice that we are mixing radians ($\omega t$) and degrees ($-120^\circ$)... if you're actually trying to calculate something numerically, you have to be careful about that." Calculator mode traps: $\tan^{-1}$ in degrees, $\omega t$ in radians.
4. **Sine → cosine first** [0:09:22–0:10:46]: "This signal over here is not specified in the usual cosine form... So the first thing that we need to do is convert that signal to the usual cosine form." $\sin x=\cos(x-90^\circ)$. (Past exams use sine-form sources as a trap; see [[Past Exams F23-F24]].)
5. **Single-frequency requirement** [0:31:13]: "We can only use phasor analysis if there's only a single angular frequency." With multiple frequencies, use superposition, and that needs a linear circuit.
6. **Always convert back** [0:15:38, 0:28:43]: "eventually we will have to convert that back to the time domain," via $\mathrm{Re}[\tilde V e^{j\omega t}]$. "**Remember, it's always going to be the real part of** the phasor times $e^{j\omega t}$." [0:29:13] The final answer is boxed in cosine form with units.
7. **Get the result into magnitude-phase form** [0:22:00–0:22:39]: "when we convert... back to the time domain, what we will want is to have that voltage in... magnitude and phase form, not in this rectangular form." So convert denominators like $3+j4$ to polar.
8. **"Everything from 302 carries over"** (board statement) [0:33:33–0:35:10]: series/parallel, voltage/current division, source transformations, Thevenin/Norton, "because KCL and KVL are valid for phasors." This is a ready-made P1 justification.
9. **Short-circuit-method failure mode** [0:51:23]: "that only works if the open-circuit voltage is non-zero." The fallback is the external-source method with independent sources turned off.
10. **Max power transfer preview** [0:53:53–0:54:27]: "to maximize the power transfer... take the load impedance and set it to the **complex conjugate** of the source impedance... we'll see that later."
11. **Phasor-diagram takeaways** [1:15:11–1:18:22]: in series RLC, $V_R$ and $I$ are parallel, $V_C$ and $V_L$ are each $90^\circ$ from $I$, and $V_C$ and $V_L$ are $180^\circ$ out of phase. The relative diagram rotated to $\tilde I$ shows it at a glance.
12. **Unit sloppiness on diagrams** [1:12:18]: comparing V and A lengths is "not really supposed to" be done. Only the parallelism matters.
13. **Readings named:** Ulaby §7-5 and §7-6 (impedance transformations and equivalent circuits), §7-7 (phasor diagrams).

---

## Student questions

| t | Question (reconstructed) | His answer |
|---|---|---|
| 0:03:54 | (Inaudible; apparently about something changed on Canvas, perhaps a due date or setting.) (?) | "Darsh must have changed that, and so... that should be okay." (Darsh is presumably the TA (?).) |
| 0:04:37 | What notation do we use for phasors? | The tilde **below**. A tilde above can clash with a vector sign, and boldface is hard to handwrite. He uses it consistently but may drop it when a quantity is clearly a phasor. |
| 0:05:30 | (ASR-garbled.) Do we need to show the tilde explicitly at every step (e.g. on homework or exams)? (?) | "As long as it's clear that it's a phasor quantity... that would generally be okay." (?) |
| 0:11:11 | In $15\cos(4\times10^4t-120^\circ)$, aren't we mixing radians and degrees? | Yes, deliberately. $\omega$ in rad/s (the natural unit, so derivatives have no stray factors), phase in degrees (more intuitive). Be careful numerically. He then wrote the CAUTION box. |
| 0:16:34 | What about DC (non-time-varying) signals? | Even simpler: steady state, C is an open, L is a short, and only sources and resistors remain. Phasors are specifically for sinusoidal (AC) signals at a fixed, specified frequency. Time-domain methods handle general inputs. Superposition of sinusoids comes later. |
| 0:26:04 | How many digits / significant figures? | On exams he will usually specify **3 s.f.** (53.1°). Keep the decimal on angles like 120.7° so that later 2-digit results keep 3 s.f. |
| 0:30:36 | Is the frequency of the signal across each component the same as the input frequency, so you just reuse it? | Yes. Phasors require a single $\omega$. All signals originate from the independent sources, so they share the source frequency. With several sources at different frequencies, use superposition one source at a time. |
| 0:32:29 | (Follow-up) So that only works for linear circuits? | Yes: "linear components, because superposition only works for linear systems." |
| 0:53:53 | (About max power transfer to a load in the phasor domain / Thevenin.) | Covered later with AC power. Preview: represent the source by its Thevenin equivalent and set $Z_{load}=Z_s^*$. Power in the phasor domain is more complicated because you multiply complex V and I and must do it carefully. |
| 0:55:01 | (Inaudible follow-up.) (?) | "Yeah, not necessarily. That's right." (Context lost (?). Possibly whether $Z_L=Z_s^*$ means the load is purely resistive, or whether the load must equal $Z_s$.) |

---

## Exam relevance

**P1 ("explain why" conceptual), high relevance.** Stems this lecture directly supports:
- *"In a series RLC with sinusoidal excitation, explain why $v_R$ and $v_C$ (or $v_R$ and $v_L$) are always 90° apart"*, or *"why $v_L$ and $v_C$ are 180° apart."* Answer: the same $\tilde I$ flows through every element. $\tilde V=\tilde Z\tilde I$, with $\tilde Z_R=R$ real, $\tilde Z_L=j\omega L$ at $+90^\circ$ and $\tilde Z_C=-j/(\omega C)$ at $-90^\circ$. So $\tilde V_R\parallel\tilde I$, $\tilde V_L$ leads by $90^\circ$, $\tilde V_C$ lags by $90^\circ$, and therefore $\tilde V_L$ and $\tilde V_C$ are $180^\circ$ apart. Sketch the relative phasor diagram. (This stem appeared in past P1s; see [[Past Exams F23-F24]].)
- *"Why can't you add the voltage amplitudes around a loop?"* Phasors add as vectors: $16+16+4\neq20$, but the vector sum is $20\angle30^\circ$.
- *"Why can't you use one phasor analysis with sources at two frequencies?"* A phasor encodes amplitude and phase at one implicit $\omega$. Use superposition (linear circuits only).
- *"Why do series/parallel, division and Thevenin carry over to phasors?"* KCL and KVL hold for phasors.
- *"When does $Z_{Th}=V_{oc}/I_{sc}$ fail?"* When $V_{oc}=0$ (0/0). Use an external test source with the independent sources off.
- *"Why do inductors/capacitors look like shorts/opens at DC?"* (his aside at 0:16:34) $\omega=0$ gives $Z_L=0$ and $Z_C\to\infty$.

**P2 (numeric phasor ladder), high relevance.** The full procedure as he does it: sin→cos, then phasors and impedances, then KVL/KCL or division/Thevenin, then rectangular→polar, then $\mathrm{Re}[\cdot\,e^{j\omega t}]$, then a boxed $A\cos(\omega t+\phi)$ with units, at 3 s.f. Likely variants: a sine-form source; a 2-node ladder where you take a Thevenin equivalent of the left part; "find $v_{out}(t)$" and then "which $C$ in a range maximizes the phase shift? Explain" (answer via Thevenin plus the monotone $\tan^{-1}$). Pitfalls he flagged: degree vs radian mode, and the sign of angles when dividing.

**P3 (two-op-amp impedance synthesizer), medium relevance.** This lecture supplies the tools rather than the topology. Write $\tilde I=\tilde V_s/\tilde Z_{eq}$ in polar form and read the element type from the phase of $\tilde I$ relative to $\tilde V$. A $+90^\circ$ lead means $\tilde Z_{eq}=-jX$, a capacitor; a $-90^\circ$ lag means $+jX$, an inductor; in phase means a resistor. The $j=e^{j90^\circ}$ bookkeeping and the phasor-diagram reasoning ($V_L\perp I$, $V_C\perp I$) are exactly what the "identify the equivalent R/L/C" part needs. Convert back to $i(t)$ in cosine form.

**P4 (2nd-order RLC transient), low direct relevance.** The same series-RLC topology appears, but this lecture is sinusoidal steady state only. The one useful link is the DC/steady-state aside ($C$ open, $L$ short) for initial and final conditions. Do not apply phasors to a transient.

**Likely question variants this lecture prepares you for:**
1. A sine-source RL/RC loop: find $v_L(t)$ or $v_C(t)$ (the lecture's RL example with numbers swapped).
2. A series RLC: find $\tilde I$ and each element voltage, sketch the absolute and the relative phasor diagram, and state the 90°/180° relations.
3. Prove KVL closes on the diagram (vector sum equals the source), or explain why the magnitudes don't sum.
4. Source-transform a $\tilde V_s$–$\tilde Z_s$ pair into $\tilde I_s\parallel\tilde Z_s$, or the reverse, inside a ladder.
5. Find the Thevenin equivalent of an AC sub-circuit. Know which method fails when $V_{oc}=0$.
6. Decide whether the circuit is net capacitive or inductive (compare $\omega$ to $1/\sqrt{LC}$, or compare $|Z_C|$ to $|Z_L|$), and hence whether $I$ leads or lags $V_s$.

> [!summary] Board-error audit
> No arithmetic or sign errors on the board. Both examples were verified with python3 and with ngspice AC analysis to 4+ digits. Transcript-only ASR errors: "millihertz" → **mF** (0:59:39), "gradients" → radians (0:20:53), "Uliby" → Ulaby, "I twill/twiddle" = $\tilde I$. The absolute phasor diagram is not to scale between V and A quantities, which he acknowledged.
