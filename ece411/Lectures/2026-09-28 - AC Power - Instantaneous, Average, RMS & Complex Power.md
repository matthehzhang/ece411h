---
course: ECE 411H
date: 2026-09-28
instructor: Ed Yu
topic: AC power — instantaneous, average, rms, complex power S, reactive power Q, conservation of S
reading: Ulaby/Maharbiz/Furse §8-1, 8-2 (instantaneous/average/rms), §8-3, 8-4 (complex power)
sources: Recordings/2026-09-28/transcript.txt (Whisper, ASR errors) + frames/ (tablet notes; authority for equations)
tags: [ece411, lecture, ac-power, exam1]
---

# 2026-09-28: AC Power (Instantaneous, Average, RMS, Complex Power)

> [!info] Source quality
> All equations below were checked against the tablet-note frames. The transcript is used only for wording and quotes. **No numeric worked example was done on the board in this lecture.** The whole lecture was derivation. I checked every derivation numerically with python3 (random $V_m, I_m, \phi_v, \phi_i$, 60 Hz) and all of them hold to about $10^{-14}$. The single numeric example in this note is marked "self-check, not from lecture".

## Summary

- **Why power needs its own treatment:** power is a *product* of $v$ and $i$. Phasors are complex, and the obvious product $\mathrm{Re}[\tilde V\tilde I]$ gives the **wrong** answer. So he derives power in the time domain first and then builds a phasor formula that reproduces it.
- **Instantaneous power** $p(t)=v(t)i(t)=\tfrac12 V_mI_m[\cos(2\omega t+\phi_v+\phi_i)+\cos(\phi_v-\phi_i)]$. This is an oscillating term at $2\omega$ plus a constant.
- **Average power** (averaged over one period $T=2\pi/\omega$): $P_{av}=\tfrac12V_mI_m\cos(\phi_v-\phi_i)=V_{rms}I_{rms}\cos(\phi_v-\phi_i)$. $\phi_v-\phi_i$ is the **power factor angle**.
- **RMS:** $X_{rms}\equiv\big[\tfrac1T\int_0^T x^2dt\big]^{1/2}=X_m/\sqrt2$. RMS matters for anything *quadratic* in the signal ($i^2R$, $v\,i$), and it absorbs the ½.
- **Load cases:** a purely resistive load has $\phi_v-\phi_i=0$, so $P_{av}=V_{rms}I_{rms}$ (the maximum). A purely reactive load has $\phi_v-\phi_i=\pm90^\circ$, so $P_{av}=0$: energy is stored and released each period and none is dissipated.
- **Complex power:** $\boxed{\tilde S=\tfrac12\tilde V\tilde I^*}$ (V·A) with peak phasors, or $\tilde S=\tilde V_{rms}\tilde I_{rms}^*$. It is *defined* so that $\mathrm{Re}[\tilde S]=P_{av}$. The conjugate is what makes the phase $\phi_v-\phi_i$.
- **Reactive power** $Q=\mathrm{Im}[\tilde S]=V_{rms}I_{rms}\sin(\phi_v-\phi_i)$ (VAR) is the *peak power exchanged* back and forth between source and load. In terms of the load impedance $\tilde Z=R+jX$: $P_{av}=\tfrac12|\tilde I|^2R=I_{rms}^2R$ and $Q=\tfrac12|\tilde I|^2X=I_{rms}^2X$.
- **Conservation:** energy conservation implies $\tilde S$ is conserved in a complete, closed circuit, so $\sum_{\text{all elements}}\tilde S=0$ (P and Q each sum to zero).

## Content

### Announcements [0:00:02 – 0:03:18] (frames f_0008, f_0010)
- PS4 was due today (9:00 AM CDT, Canvas). **PS5 is due Mon 10/05 at 9:00 AM CDT** on Canvas. PS5 covers power calculations in the phasor domain.
- **Semester Exam 1 is Wed 10/07/2026, in class.** It covers material from the start of the semester through power transfer calculations using phasors, **but not maximum power transfer calculations.** Details are in the Canvas Exam 1 announcement.
- An **answer sheet template** has been released (Gradescope now, Canvas later). **Bring a physical copy** and write your solutions on it.
- Gradescope is used for exam upload and grading. Problem sets still go to Canvas. You get about 5 min after the exam to scan and upload. Use the **"Exam Upload Practice"** assignment to debug this beforehand.

### Recap / motivation [0:03:39 – 0:09:46] (f_0020, f_0022)
- Last week covered phasor circuit analysis and a (recorded) example of a **cascaded phase-shift circuit**.
- New topic: **Power in AC circuits**, Ulaby Ch. 8.
- Board: *"In general, power = (voltage)·(current). For dc circuits, it's straightforward to determine if a component is supplying or dissipating (receiving/absorbing) power."*
  - In DC, with the passive sign convention, the **sign** of $vi$ tells you supply vs absorb. With complex quantities you "cannot unambiguously say, okay, this is positive or negative" [0:08:53].
- Board: *"How do we analyze power in ac circuits, in both the time and phasor domains?"*
- Strategy [0:06:22–0:07:13]: one option is to convert phasors back to the time domain and do power there. That always works, and he uses it to *build* a phasor-domain formalism, which is "easier and more efficient". Plan: look at power in the time domain first, decide which quantities we actually want, then find them in the phasor domain.

### Instantaneous and average power, Ulaby §8-1, 8-2 [0:09:46 →]

**Setup [0:10:37 – 0:13:29] (f_0025, f_0030, f_0045):** *"Power transfer between an active (source) circuit and passive (load) circuit."*
- **Active** = contains at least one independent source. **Passive** = contains no independent sources.
- Diagram: a box labelled **"active ac circuit" (source)** on the left. Its two output terminals (o, o) connect to a box labelled **"passive ac circuit" (load)** on the right. Current $i(t)$ flows along the top wire from source to load, with an arrow pointing right. Voltage $v(t)$ is across the terminals, + on top and − on the bottom. This is the passive sign convention for the load.
- $v(t)=V_m\cos(\omega t+\phi_v)$ and $i(t)=I_m\cos(\omega t+\phi_i)$.

**Instantaneous power [0:16:31] (f_0045, f_0061, f_0066).** Board definition: *"instantaneous power: power transferred to load at time t."*

$$p(t)=v(t)\,i(t)=V_mI_m\cos(\omega t+\phi_v)\cos(\omega t+\phi_i)$$

Using $\cos\theta=\tfrac12(e^{j\theta}+e^{-j\theta})$ ("you can do it that way or you can try to remember or look up the formula for the product of cosines"):

$$=\tfrac14V_mI_m\left(e^{j(\omega t+\phi_v)}+e^{-j(\omega t+\phi_v)}\right)\left(e^{j(\omega t+\phi_i)}+e^{-j(\omega t+\phi_i)}\right)$$

Multiply out. The "first × first" and "second × second" terms give the $2\omega t$ pair, and the cross terms give the phase-difference pair:

$$=\tfrac14V_mI_m\left(e^{j(2\omega t+\phi_v+\phi_i)}+e^{-j(2\omega t+\phi_v+\phi_i)}+e^{j(\phi_v-\phi_i)}+e^{-j(\phi_v-\phi_i)}\right)$$

$$\boxed{p(t)=\tfrac12V_mI_m\Big[\underbrace{\cos(2\omega t+\phi_v+\phi_i)}_{\text{oscillating}}+\underbrace{\cos(\phi_v-\phi_i)}_{\text{constant}}\Big]\ \text{(Watts)}}$$

- The first term oscillates at **$2\omega$**. The second does not vary with time, because $\phi_v$ and $\phi_i$ are constants [0:21:42].

**Average power [0:22:24 – 0:26:25] (f_0071, f_0077, f_0081, f_0088).**
- Motivation: what we usually want is *steady-state* power transfer. "Any steady state power transfer will be just the average over one cycle times the number of cycles" [0:22:51].
- Board definition: *"average power: power transferred to load averaged over one period $T=2\pi/\omega$."*

$$P_{av}=\frac1T\int_0^Tp(t)\,dt=\frac1T\int_0^T\tfrac12V_mI_m\big[\underbrace{\cos(2\omega t+\phi_v+\phi_i)}_{\text{integrates to zero}}+\cos(\phi_v-\phi_i)\big]dt$$

- The $2\omega$ term integrates to zero because the interval $T$ holds **two full periods** of it. The constant averages to itself.

$$\boxed{P_{av}=\tfrac12V_mI_m\cos(\phi_v-\phi_i)}\ \text{(Watts)}$$

- Two observations [0:26:46]: (1) $P_{av}$ depends on the **phase difference** $\phi_v-\phi_i$. (2) It is greatest when $v$ and $i$ are in phase. He comes back to the phase later and first explains the ½.

### RMS values [0:27:20 – 0:37:57] (f_0093, f_0098, f_0121–f_0168)
- Goal: explain the ½ and define an amplitude that "absorbs" it.
- Board: *"In addition to sinusoidal signal amplitudes $(V_m, I_m)$, we can define the **root mean square** values, $V_{rms}$ and $I_{rms}$."*
- Board: *"For an electrical signal $x(t)=X_m\cos(\omega t+\phi)$,"*
$$X_{rms}\equiv\left[\frac1T\int_0^Tx^2(t)\,dt\right]^{1/2}$$
  He uses the generic $x$ on purpose: "it applies to any signal", whether current, voltage or anything else [0:29:21]. The square root gives back the original units.
- Board: *"$X_{rms}$ is relevant for quantities that are quadratic in $x(t)$, e.g., $p(t)=i^2(t)R$ for power dissipated in R, or quadratic forms in multiple variables, e.g., $p(t)=v(t)i(t)$."*
- Derivation (f_0128, f_0164):
$$\frac1T\int_0^Tx^2dt=\frac1T\int_0^TX_m^2\cos^2(\omega t+\phi)\,dt=\frac1TX_m^2\int_0^T\tfrac12\big(1+\cos(2(\omega t+\phi))\big)dt=\tfrac12X_m^2=X_{rms}^2$$
  It uses $\cos^2\theta=\tfrac12(1+\cos2\theta)$, and the $\cos 2(\cdot)$ term integrates to 0 over two complete periods.
$$\boxed{X_{rms}=\frac{1}{\sqrt2}X_m}\quad(\approx 0.707\,X_m,\ \text{"about 70\%"})$$
- Board (f_0168, f_0172): *"Thus, we have"*
$$P_{av}=\tfrac12V_mI_m\cos(\phi_v-\phi_i)=V_{rms}I_{rms}\cos(\underbrace{\phi_v-\phi_i}_{\text{power factor angle}})$$
  Each rms amplitude absorbs a $1/\sqrt2$, so the pair absorbs the whole ½ [0:35:36].
- Why it matters even though it is "trivial": specs and the literature quote **rms** values, so you need to know what they are and how they relate to the actual signal [0:37:20–0:37:46].

### Effect of the phase difference / load type [0:37:57 – 0:42:55] (f_0172, f_0177, f_0184)
- $P_{av}$ is maximized when $\phi_v-\phi_i=0$ ($\cos 0=1$) and minimized (zero) at $90^\circ$ out of phase.
- The phase difference $\phi_v-\phi_i$ is called the **power factor angle** [0:38:38].
- **Purely resistive load:** the load's Thévenin equivalent is just a resistor. The Thévenin voltage of a passive circuit is always 0. With $\tilde V=\tilde I\tilde Z$ and real $\tilde Z$, $v$ and $i$ have the same phase.
  Board: *"purely resistive load: $\phi_v-\phi_i=0$, $P_{av}=V_{rms}I_{rms}$."*
- **Purely reactive load** (underlined on the board) means $\mathrm{Re}[\tilde Z]=0$: purely capacitive or inductive.
  Board: *"purely reactive load: $\phi_v-\phi_i=\pm90^\circ$, $P_{av}=0$."* The sign depends on whether the load is capacitive or inductive.
- Board (f_0184): *"For a purely reactive load, e.g., L or C, energy is stored and released during each period, but no power is dissipated in the load."*

> [!warning] Imprecise verbal claim (not a board error)
> At [0:39:42–0:41:20] he says a purely resistive load "maximizes the power transfer" and gives "the most power transfer that is possible". That is true **only for fixed $V_m, I_m$**: the $\cos$ factor is largest at 0°. It is **not** the AC maximum-power-transfer result. With a source impedance $\tilde Z_{Th}=R_{Th}+jX_{Th}$, the load that maximizes $P_{av}$ is $\tilde Z_L=\tilde Z_{Th}^*$, which is *not* purely resistive when $X_{Th}\ne0$. Max power transfer is excluded from Exam 1, but on a P1 "explain why" answer, say "for given voltage and current amplitudes" so the grader doesn't read it as a max-power-transfer claim.

### Power calculations using phasors, Ulaby §8-3, 8-4 [0:42:58 →] (f_0192–f_0242)
- Same source/load diagram redrawn with the active (source) and passive (load) boxes, $i(t)\to$, $+v(t)-$ (f_0196).
  - $v(t)=V_m\cos(\omega t+\phi_v)\ \to\ \tilde V=V_me^{j\phi_v}$
  - $i(t)=I_m\cos(\omega t+\phi_i)\ \to\ \tilde I=I_me^{j\phi_i}$ (**peak-amplitude phasors**)
- The load is replaced by its equivalent (f_0197, f_0210): two terminals with a single box labelled $\tilde Z$ "(load)". $\tilde I$ enters the top terminal, with $+\tilde V-$ across it.
- Board: *"Passive (load) circuit contains no independent sources, so its equivalent circuit is just an impedance $\tilde Z$ with"*
$$\tilde Z=\tilde V/\tilde I=\frac{V_m}{I_m}e^{j(\phi_v-\phi_i)}$$
  Note that **the angle of the load impedance is the power factor angle.**
- **Building $\tilde S$ [0:48:31 – 0:55:32] (f_0226, f_0242, f_0254):**
  - Wrong attempt 1: $\mathrm{Re}[\tilde V\tilde I]$. "That does not actually give you the correct expression for the average power." Its phase is $\phi_v+\phi_i$.
  - Wrong attempt 2: $\mathrm{Re}[\tilde V]\cdot\mathrm{Re}[\tilde I]$, which also does not work.
  - "We have some latitude" in defining a phasor-domain power, and we want a *useful* one. Board: *"For power, we want a complex quantity $\tilde S$ that is a product of current and voltage with"*
  $$\mathrm{Re}[\tilde S]=P_{av}=\tfrac12V_mI_m\cos(\phi_v-\phi_i).$$
  - Taking the real part produces the cosine, so the **phase of $\tilde S$ must be $\phi_v-\phi_i$**. $\tilde V\tilde I$ has phase $\phi_v+\phi_i$. Conjugating the current ($j\to-j$) gives $e^{-j\phi_i}$, so $\tilde V\tilde I^*$ has phase $\phi_v-\phi_i$. Then put the ½ back in from the time-domain result.
  $$\boxed{\tilde S=\tfrac12\tilde V\tilde I^*\quad(\text{V}\cdot\text{A})}\quad\text{(complex power)}$$
- Board (f_0266): *"where $\tilde I^*$ = complex conjugate of $\tilde I$ $=I_me^{-j\phi_i}$."* Board: *"or, equivalently,"*
$$\tilde S=\tilde V_{rms}\tilde I_{rms}^*\quad\text{where }\tilde V_{rms}=V_{rms}e^{j\phi_v},\ \tilde I_{rms}=I_{rms}e^{j\phi_i}$$

### Real and imaginary parts of $\tilde S$ [1:04:52 – 1:10:07] (f_0271, f_0278, f_0281, f_0292)
Board: *"Then"*
$$\tilde S=\tfrac12V_mI_me^{j(\phi_v-\phi_i)}=\tfrac12V_mI_m\left[\cos(\phi_v-\phi_i)+j\sin(\phi_v-\phi_i)\right]=V_{rms}I_{rms}\left[\cos(\phi_v-\phi_i)+j\sin(\phi_v-\phi_i)\right]$$

- Board: $P_{av}=\mathrm{Re}[\tilde S]$ = **average power dissipated in load circuit**.
- Board: $Q=\mathrm{Im}[\tilde S]=V_{rms}I_{rms}\sin(\phi_v-\phi_i)$ = **peak power *exchanged* between source + load circuits** ("exchanged" is underlined).
  - "I'll just assert it here, but if you sort of play around with things in the time domain, then you should be able to show this" [1:06:59]. *Verification (mine):* rewrite $p(t)=P_{av}\big[1+\cos 2(\omega t+\phi_v)\big]+Q\sin 2(\omega t+\phi_v)$. The $Q$ term is the part of $p(t)$ that sloshes back and forth with zero average. For a pure L or C, $p(t)=Q\sin2(\omega t+\phi_v)$, so $|Q|$ is exactly the peak instantaneous power. Checked numerically: the decomposition holds to $10^{-14}$, and for an inductor $\max p(t)=Q$.
- Plausibility argument [1:07:31–1:08:36]: with $v$ and $i$ in phase there is no exchange, which fits a load with nothing that stores energy. The exchange is largest at 90°, which fits a load that only stores energy.
- Board (f_0292): *"Note that $Q\neq0$ only if $\phi_v\ne\phi_i$, and $|Q|$ is maximized for $\phi_v-\phi_i=\pm90^\circ$, i.e., a purely reactive load."*
  *"$\Rightarrow Q$ = 'reactive power' (VAR = Volts·Amps Reactive)."*

### $\tilde S$ in terms of the load impedance [1:10:17 – 1:13:51] (f_0296, f_0302, f_0307)
- Board: *"The load circuit has equivalent impedance $\tilde Z=\tilde V/\tilde I=R+jX$."* He uses $X$ for the imaginary part "because it could be either capacitance or inductance".
$$\tilde S=\tfrac12\tilde V\tilde I^*=\tfrac12\tilde Z\tilde I\tilde I^*=\tfrac12|\tilde I|^2\tilde Z=I_{rms}^2(R+jX)$$
$$\boxed{P_{av}=\tfrac12|\tilde I|^2R=I_{rms}^2R\qquad Q=\tfrac12|\tilde I|^2X=I_{rms}^2X}$$
- Since $I_{rms}^2$ is real, **Re S depends only on the resistive part** of the load and **Im S only on the reactive part**. "The power transfer from the source to the load really depends on, and only depends on, the resistive part of the load impedance, and the power transfer back and forth ... depends only on the reactive part" [1:12:43].

### Conservation of complex power [1:13:56 – 1:16:02] (f_0309)
- Board: *"Conservation of energy $\Leftrightarrow$ $\tilde S$ is conserved in a complete, closed circuit."*
- This is the AC analogue of 302's "power is conserved across all components in a DC circuit".
- Reasoning (spoken, not written): the average powers over all components sum to zero, and the peak exchanged power "if it's transferred from one component, it has to go to another component", so those sum to zero as well. Together: $\sum_{\text{all components}}\tilde S=0$ [1:15:48]. (This uses the passive sign convention on every element, sources included.)
- Ends at [1:16:16]: "There's a little bit more on this topic ... at the beginning of Wednesday's class, and then that will be the end of what you're responsible for for the first midterm exam."

### Self-check example (NOT from lecture; numbers verified with python3)
$\tilde V_s=10\angle0^\circ$ V (peak) drives a series $R=3\,\Omega$, $jX_L=j4\,\Omega$.
$\tilde I=10/(3+j4)=2\angle-53.13^\circ$ A. $\tilde S_{load}=\tfrac12(10)(2\angle{+53.13^\circ})=6+j8$ VA.
Check: $\tfrac12|\tilde I|^2R=\tfrac12(4)(3)=6$ W and $\tfrac12|\tilde I|^2X=8$ VAR. $Q>0$ for an inductive load.
Source (passive sign convention): $\tilde S_{src}=-6-j8$, so $\sum\tilde S=0$ ✓.
Using rms instead: $V_{rms}=7.071$, $I_{rms}=1.414$, $V_{rms}I_{rms}=10$, $\cos 53.13^\circ=0.6$, $P=6$ W ✓.
Wrong method for comparison: $\mathrm{Re}[\tilde V\tilde I]=\mathrm{Re}[20\angle-53.13^\circ]=12$ W ✗ (double the right answer here, and wrong in general).

> [!note] Board errors
> None found. Every line on the board (product-of-cosines expansion, average, rms integral, $\tilde S$ decomposition, $\tilde S=\tfrac12|\tilde I|^2\tilde Z$) checks out symbolically and numerically. The ASR garbles a few phrases, e.g. [0:40:07] "multiplied by the current" for "$P_{av}=V_{rms}I_{rms}$" and [0:52:25] "phi sub m" for $\phi_i$. Trust the frames over the transcript.

## Ed Yu's conventions & notation

- **Phasors are peak-amplitude by default:** $\tilde V=V_me^{j\phi_v}$, $\tilde I=I_me^{j\phi_i}$. Hence **$\tilde S=\tfrac12\tilde V\tilde I^*$**, and **$P_{av}=\tfrac12|\tilde I|^2R$**. If you use **rms phasors** $\tilde V_{rms}=V_{rms}e^{j\phi_v}$, drop the ½: $\tilde S=\tilde V_{rms}\tilde I_{rms}^*$, $P_{av}=I_{rms}^2R$. Never mix the two, which double-counts or drops the ½. Write which one you're using on the exam.
- **Phasor notation:** a tilde *under* the letter ($\underset{\sim}{V}$, $\underset{\sim}{I}$, $\underset{\sim}{Z}$, $\underset{\sim}{S}$). Conjugate: asterisk, $\underset{\sim}{I}^*$. In this note, $\tilde{}$ stands for his under-tilde.
- **Symbols:** $P_{av}$ ("P average") for average power, $Q$ for reactive power, $\tilde S$ for complex power, $X$ for the load reactance, $\tilde Z=R+jX$, $X_{rms}$ for generic rms.
- **Units:** $p(t)$ and $P_{av}$ in **Watts**; $\tilde S$ in **V·A** ("volts times amps"); $Q$ in **VAR** ("volts·amps reactive").
- **Reference direction:** current flows *into* the load's + terminal (passive sign convention for the load), so $P_{av}>0$ means the load absorbs.
- **Power factor angle** = $\phi_v-\phi_i$ (voltage phase minus current phase), which is also $\angle\tilde Z_{load}$.
- **Sign of Q** (implied, not stated as a rule): $Q=I_{rms}^2X$, so **inductive load ($X>0$, $\phi_v-\phi_i=+90^\circ$ for pure L) gives $Q>0$** and **capacitive ($X<0$) gives $Q<0$**. Verified numerically.
- **Power factor $\cos(\phi_v-\phi_i)$ and leading/lagging were NOT defined in this lecture.** He only named the angle. The standard Ulaby convention (textbook, not lecture (?)) is pf $=\cos(\phi_v-\phi_i)$. It is **lagging** when current lags voltage (inductive, $Q>0$) and **leading** when current leads (capacitive, $Q<0$). This is presumably covered Wednesday, and the Course Materials Map says Recitation 3 covers it.
- **Terminology:** "active (source) circuit" means at least one *independent* source. "Passive (load) circuit" means no independent sources, so its Thévenin voltage is 0 and it reduces to a single $\tilde Z$. "Purely reactive load" means $\mathrm{Re}\,\tilde Z=0$.
- The integrals are written as $\frac1T\int_0^T(\cdot)\,dt$, with $T=2\pi/\omega$.

## Intuition & explanations he gives

- **Why power is tricky with phasors** [0:05:27–0:06:11]: "Power ... is a product of current and voltage. ... If you take, say, two phasors and multiply them together, and then take the real part of that product, it's not necessarily that obvious that that is actually going to give you the correct result for power. In fact, that will not give you the correct result for power."
- **Why the sign test fails in AC** [0:08:36–0:09:03]: with the passive sign convention, the sign of $vi$ tells you supply vs receive in DC, "but now if you have a complex quantity, you cannot unambiguously say, okay, this is positive or negative."
- **Instantaneous vs average** [0:14:56–0:15:53]: in AC you *do* know at every instant whether a component is supplying or receiving, from $v(t)i(t)$. But for steady-state transfer "the instantaneous power at a particular time is not sufficient; [you] need to think about what's happening over the whole sinusoidal cycle."
- **Why average over one period** [0:22:35–0:22:51]: "any steady state power transfer will be just the average over one cycle times the number of cycles."
- **Why the $2\omega$ term vanishes** [0:25:27–0:25:40]: "we're integrating essentially a constant times the cosine, and we're integrating that over two full periods. ... 0."
- **Why rms exists** [0:30:19–0:31:58]: it is "relevant for any quantities that are quadratic in the signal", e.g. $i^2R$, or "quadratic forms in multiple variables" like $v\cdot i$. Averaging a squared sinusoid gives $\tfrac12X_m^2$, and rms bundles in the $1/\sqrt2$. "At one level it may seem sort of trivial ... you're redefining a constant ... but ... very often in the literature or in specs ... what you will see is rms quantities" [0:37:20].
- **Why the resistive load gets max $P_{av}$** [0:39:42–0:40:07]: "the voltage as a phasor is equal to the current as a phasor times the impedance of the load, and the impedance is real, so the current and the voltage will have the same phase." (See the warning above about "for fixed amplitudes".)
- **Purely reactive load sloshing energy** [0:41:36–0:42:55]: "If the load is purely reactive ... there is actually no power that is transferred to the load. In steady state, what actually happens is that there is energy that is transferred to the load for part of the cycle and then transferred back out over the other part of the cycle. So it kind of goes back and forth between the source and the load, but it does not get dissipated in the load." Board: "energy is stored and released during each period, but no power is dissipated in the load."
- **Why $\tilde I^*$ (the key P1 explanation)** [0:52:56–0:55:01]: we *choose* a definition so that $\mathrm{Re}[\tilde S]$ equals the time-domain $P_{av}$. Taking the real part gives a cosine of the phase of $\tilde S$, and that phase must be $\phi_v-\phi_i$. "If we multiply just $V$ times $I$ as phasors, the phase of that is going to be $\phi_v+\phi_i$, that's not what we want ... take the current phasor, take its complex conjugate ... then the phase of that product is going to be $\phi_v-\phi_i$."
- **Why not $\tilde V/\tilde I$ even though it has the right phase** [0:56:15]: "physically power always has to be some product of current and voltage, not voltage divided by current. ... if we take the voltage divided by the current, you get an impedance."
- **Why "V·A" not "W" for $\tilde S$** [0:56:31–0:57:16, 1:00:33–1:01:01]: V·A makes it explicit that "we've multiplied a voltage times a current, but then we have to go a little bit farther to really interpret that as ... a physical power quantity." Watts are "power that you can harness" and can be non-electrical. V·A marks an electrical product that isn't yet "useful power".
- **Why a definition with "latitude" is legitimate** [0:57:38–0:58:29]: "there are, in principle, multiple ways that we could define some power quantity, but we want to choose one that is useful for us." A bonus of this choice is that the imaginary part gets a natural meaning: peak power exchanged.
- **Interpretation of Q** [1:07:31–1:08:28]: "if the voltage and the current are in phase, then there's no power exchange, which is sort of what you would expect if there's no inductive or capacitive component ... nothing that can actually store energy. And it is maximized ... when the voltage and current are 90 degrees out of phase ... purely reactive ... If all you have in the load is energy storage, then that corresponds to peak power exchange. If all you have in the load is resistance, then there is no energy that is exchanged."
- **Imaginary means storage, but be careful** [1:01:34–1:02:48]: imaginary parts of $\tilde Z$ (L or C) and of $\tilde S$ relate to energy *storage* rather than dissipation. "But you have to be a little bit careful. ... if you were to just look at voltage as a phasor, then for any nonzero phase it has a real and imaginary part, but that imaginary part of the voltage does not necessarily correspond to ... energy storage versus dissipation."
- **P depends only on R, Q only on X** [1:12:11–1:13:11]: since $I_{rms}^2$ is real, $\tilde S=I_{rms}^2(R+jX)$ splits cleanly. "It's sort of what you would expect, but it tells us more explicitly now..."
- **Conservation of $\tilde S$** [1:14:08–1:15:48]: "In any closed system, energy has to be conserved." Average powers sum to zero, and the exchanged power "if it's transferred from one component, it has to go to another component", so that sums to zero too. Together, $\sum\tilde S=0$.

## Emphasis & exam intel

1. **Exam scope boundary** [0:00:59–0:01:21]: Exam 1 covers "material from the beginning of the semester through our discussion that will start today of power calculations using phasors. **But it will not include calculations pertaining to how we maximize power transfer** between a source circuit and a load circuit. ... the cutoff point will be somewhere around maybe the end of today's class or the early part of Wednesday's class." Repeated at [1:16:16]: "a little bit more on this topic ... at the beginning of Wednesday's class, and then that will be the end of what you're responsible for for the first midterm exam." **So everything in this lecture is in scope**: $p(t)$, $P_{av}$, rms, $\tilde S$, $Q$, $\tilde S=\tfrac12|\tilde I|^2\tilde Z$, conservation. So is whatever he adds at the start of Wednesday 9/30 (likely power factor).
2. **Answer sheet template** [0:01:41–0:02:09]: "there is an answer sheet template, which has been released now ... you'll need to bring a physical copy of that to the class for your exam so that you can write your exam solutions on that."
3. **Gradescope upload** [0:02:23–0:03:14]: "after the exam finishes, you'll have about five minutes or so at the end of class to scan your exam using your phone or a tablet ... There's almost always someone who has not done that and has some problem uploading ... **So please test this before you come to the exam.**"
4. **PS5** [0:00:19–0:00:27]: due Mon Oct 5 (9:00 AM CDT, Canvas). It "basically covers power calculations using phasors and some related topics, so that's what we'll be talking about starting today."
5. **"Re(VI) is wrong" stated twice** [0:06:08] "In fact, that will not give you the correct result for power" and [0:49:29] "...that does not actually give you the correct expression for the average power". A natural P1 "explain why" item.
6. **$P_{av}$ depends on the phase difference** [0:26:46]: "the average power depends on the difference in phases between the voltage signal and the current signal. And the average power that's transferred is greatest when the voltage and the current are in phase." This matches the recurring past-P1 theme (average power vs V–I phase).
7. **Reactive load has $P_{av}=0$** [0:41:36]: "If the load is purely reactive ... there is actually no power that is transferred to the load." Board boxed statement f_0184.
8. **Q left as an exercise** [1:06:59]: "I'll just assert it here, but if you sort of play around with things in the time domain, then you should be able to show this." A possible derivation item. Know $p(t)=P[1+\cos2(\omega t+\phi_v)]+Q\sin2(\omega t+\phi_v)$.
9. **RMS in practice** [0:37:34]: "it is useful and important to know because very often ... in the literature or in specs ... what you will see is ... rms quantities." Expect a problem that gives rms values, or says "120 V rms", and requires the conversion.
10. **Conservation of $\tilde S$** [1:14:08–1:14:42]: stated as the closing point. It is a checking tool for a P2 ladder: $\sum\tilde S_{\text{absorbed}}=\tilde S_{\text{delivered by source}}$.
11. **Reading assignments:** §8-1, 8-2 (instantaneous/average/rms) [0:10:14] and §8-3, 8-4 (complex power) [0:43:28].

## Student questions

- **[0:13:36] "Do we need to care about the current through the bottom branch?"** No separate unknown. The load is a closed two-terminal circuit, so by KCL the same $i(t)$ flows back from right to left on the bottom wire.
- **[0:14:06] "DC currents change with time during transients, so is DC still easier?"** "DC circuits mean specifically nothing is changing with time ... that would be $\omega=0$." With the passive sign convention you know supply vs receive. In AC you also know it at any instant from $v(t)i(t)$. But for steady-state transfer the instant isn't enough, so you average over a cycle.
- **[0:15:53] Follow-up: switching on a constant 10 V source makes a capacitor's power vary, but steady state is trivial?** "Yeah, or easier to calculate ... the DC situation really will refer to that steady state."
- **[0:46:51] "That's just because we have defined passive as no sources?"** "No *independent* sources, right, yes." So the load's Thévenin voltage is 0 and the load is just $\tilde Z$.
- **[0:55:57] "Why not divide $\tilde V/\tilde I$ to get phase $\phi_v-\phi_i$?"** Power must physically be a *product* of current and voltage. $\tilde V/\tilde I$ is an impedance, and the magnitude would also be wrong.
- **[0:56:31] (question inaudible; inferred: why V·A and not W?)** V·A makes explicit that "we've multiplied a voltage times a current", but more interpretation is needed before it is physical, harnessable power (watts).
- **[0:57:23] "If S is defined only so Re S = P_av, what is the significance of the imaginary part?"** It is a deliberate, useful choice. "The imaginary part of this complex power is related to power that is transferred back and forth between the source and the load ... it's the peak power that's transferred back and forth." The definition gives the imaginary part a natural interpretation.
- **[0:58:39] Student: V·A vs W is like "how much you need to be able to carry vs how much you're actually producing"?** "There is a distinction that can be made between ... the maximum power that the source is producing and how much is actually transferred to the load ... I wouldn't say that is the definitive distinction, but that's part of the distinction." Watts also aren't necessarily electrical.
- **[1:01:10] "Can we generally think of imaginary parts as the oscillatory/storage part?"** Often, yes: Im $\tilde Z$ is L or C, which stores and does not dissipate, and Im $\tilde S$ is exchanged power. "But you have to be a little bit careful": the imaginary part of a voltage phasor is just a phase, and it doesn't mean storage.

## Exam relevance

| Past slot | How this lecture feeds it | Likely variants |
|---|---|---|
| **P1 (4 × "explain why")** | The **highest-yield** use. Past P1s regularly ask about average power vs V–I phase, and this lecture supplies the model answers. | (a) Why does a purely inductive/capacitive load absorb zero average power? (energy stored then returned each half-cycle; $\cos 90^\circ=0$). (b) Why is $P_{av}$ max when $v,i$ are in phase (for given amplitudes)? (c) Why $\tilde S=\tfrac12\tilde V\tilde I^*$ and not $\tfrac12\tilde V\tilde I$? (the conjugate makes the phase $\phi_v-\phi_i$; $\tilde V\tilde I$ has $\phi_v+\phi_i$ and $\mathrm{Re}$ of it is not $P_{av}$). (d) Where does the ½ / $1/\sqrt2$ come from? ($\langle\cos^2\rangle=\tfrac12$.) (e) Why does $P_{av}$ depend only on R and Q only on X? ($\tilde S=I_{rms}^2\tilde Z$, and $I_{rms}^2$ is real.) (f) Why must $\sum\tilde S=0$? (energy conservation plus exchanged power must go somewhere.) (g) Physical meaning of Q. |
| **P2 (numeric phasor ladder)** | Very likely add-on this year: after solving the ladder, "find the average power delivered by the source / absorbed by $R_2$ / reactive power of $L$" | Use $P=\tfrac12|\tilde I_R|^2R$ per resistor, $Q=\tfrac12|\tilde I|^2X$ per reactive element, $\tilde S_{src}=\tfrac12\tilde V_s\tilde I_s^*$. **Check $\sum\tilde S=0$** (source delivered = sum absorbed). Watch for **rms vs peak** given values (e.g. "120 V rms"). Watch the passive sign convention on the source. |
| **P3 (two-op-amp impedance synthesizer)** | The synthesized $\tilde Z_{in}=R+jX$ determines $P$ and $Q$ drawn from the driving source: $\tilde S=\tfrac12|\tilde I_{in}|^2\tilde Z_{in}$ | Variants (?): "What average power does the source deliver to the synthesized inductor?" Answer: 0 if $\tilde Z_{in}$ is purely reactive; Q > 0 if inductive. If the synthesized $R$ is negative, $P_{av}<0$: the circuit *delivers* power, which comes from the op-amp supplies (dependent sources). This is why conservation must include the op-amps. |
| **P4 (2nd-order RLC transient)** | Little direct overlap. The shared concept is energy stored in L and C. | At most a conceptual tie-in: L and C store but don't dissipate energy, so only R dissipates. |

**Must-memorize (closed book, no formula sheet):**
$p(t)=\tfrac12V_mI_m[\cos(2\omega t+\phi_v+\phi_i)+\cos(\phi_v-\phi_i)]$,
$P_{av}=\tfrac12V_mI_m\cos(\phi_v-\phi_i)=V_{rms}I_{rms}\cos(\phi_v-\phi_i)$,
$X_{rms}=X_m/\sqrt2$,
$\tilde S=\tfrac12\tilde V\tilde I^*=\tilde V_{rms}\tilde I_{rms}^*=P+jQ$,
$Q=V_{rms}I_{rms}\sin(\phi_v-\phi_i)$,
$\tilde S=\tfrac12|\tilde I|^2\tilde Z\Rightarrow P=I_{rms}^2R,\ Q=I_{rms}^2X$,
$\sum\tilde S=0$.
Also derivable in under 2 min: $\tilde S=\tfrac12|\tilde V|^2/\tilde Z^*$ (from $\tilde I=\tilde V/\tilde Z$; not on board but follows directly). This is handy for parallel elements where you know $\tilde V$.

**Top traps:** (1) using $\mathrm{Re}[\tilde V\tilde I]$; (2) forgetting the ½ with peak phasors, or adding it with rms; (3) using $|\tilde V_{\text{source}}|$ instead of the element's own voltage/current in $\tfrac12|\tilde I|^2R$; (4) sign of $Q$ for a capacitor (negative); (5) saying "resistive load maximizes power transfer" without "for fixed amplitudes".
