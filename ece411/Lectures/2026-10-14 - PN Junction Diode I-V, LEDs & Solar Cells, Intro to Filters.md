---
course: ECE 411H
date: 2026-10-14
instructor: Prof. Ed Yu
topic: pn junction under bias (barrier lowering, Fermi-function argument for exponential current, reverse saturation), diode I-V equation, LEDs and solar cells, introduction to circuit frequency response and filter types
reading: Ulaby/Maharbiz/Furse 3e Ch. 9 (filters; stated on the board). No reading named for the semiconductor part.
source: Recordings/2026-10-14-semiconductors-intro-to-filters (transcript + 23 distinct tablet pages from 57 page-final frames; frame log in frames/pages_described.md)
tags: [ece411, lecture, semiconductors, pn-junction, diode, fermi-dirac, led, solar-cell, filters, exam2]
source_quality:
  - "Speech: Deepgram Nova-3, 76 min, 1018 utterances, 122 wpm, mean confidence 0.96; 92 words < 0.55 (1.0 %); 13 utterances < 0.7 (lowest at 0:04:54, 0:21:43, 0:41:36, 1:07:08, 1:07:16; mostly student cross-talk)"
  - "Board: tablet (not doc-cam), 23 distinct pages, 0 blurry; 37 of 57 page-final frames are scroll/extension repeats (p03, p05, p07-p11, p16 add no ink)"
  - "Spoken math is transcribed as words; student questions are off-mic and fragmentary; every number re-derived with python3"
  - "Page-final frame f_0172 predates a board correction made at 0:51:31 (see f_0175); the last board phrase ('graphically by Bode plots', ~1:15:46) is in speech only, not in any frame"
  - "No audio dropouts; the longest silences (~15-20 s) are writing pauses"
---

# 2026-10-14: PN Junction Diode I-V, LEDs & Solar Cells, Intro to Filters

> [!info] DO-NOT-SOLVE check
> No PS8 problem (9.26, 9.38, 9.39, 9.42, m9.2, 12.2a-c) and no Lab 5 item was worked in this lecture. The filter section is definitions only. Transfer functions and Bode plots start next lecture.

## Summary

- **Forward bias explained with a band diagram:** with $V>0$ on the p side (n side grounded), the electron potential energy on the p side shifts by $(-e)V$. The barrier drops from $eV_{bi}$ to $eV_{bi}-eV$, and the two Fermi levels split by $eV$. You must be able to draw this and label $eV_{bi}-eV$ and $eV$.
- **Why the current is exponential in $V$:** the occupation probability at the barrier-top energy is $f=\big[e^{(E_c+eV_{bi}-eV-E_F)/k_BT}+1\big]^{-1}\approx e^{-(eV_{bi}+E_c-E_F)/k_BT}\,e^{eV/k_BT}$. The barrier top is many $k_BT$ above $E_F$, so the $+1$ can be dropped. That gives the factor $e^{eV/k_BT}$; current ∝ carrier concentration over the barrier ∝ $e^{eV/k_BT}$. Holes behave the same way.
- **Why $I=0$ at $V=0$:** a single, flat $E_F$ means equal occupation at any given energy on both sides, so the diffusion fluxes cancel. Net current needs the Fermi levels on the two sides to differ.
- **Reverse bias ($V<0$):** the over-barrier term shrinks exponentially, but minority carriers (electrons on the p side, holes on the n side) slide down the barrier. Their concentration does not depend on $V$, so the current reverses direction and saturates. It is "roughly independent of V."
- **Diode equation:** $I=I_0\left(e^{eV/k_BT}-1\right)$. The exponential term comes from the majority carriers crossing the barrier; the $-1$ comes from the minority carriers going the other way. The reverse current is 5–10+ orders of magnitude below the on-current. Breakdown occurs at large reverse $V$.
- **LED:** a forward-biased junction in which injected electrons recombine with holes and the energy is emitted as a photon $h\nu$.
- **Solar cell:** a photon with $h\nu\gtrsim E_g$ creates an electron-hole pair that drives current from lower to higher voltage. The cell operates in the 4th quadrant ($V>0$, $I<0$) at the max-$|IV|$ point. Efficiency losses: sub-gap photons are not absorbed, above-gap excess energy is lost as heat, and $V_{op}<V_{bi}<E_g/e$.
- **Filters:** know the definitions of high-pass, low-pass, band-pass, band-reject and passband. Frequency response is described *algebraically* by a **transfer function** and *graphically* by **Bode plots** (next lecture onward).

---

## Content

### 0. Announcements [0:00:02–0:01:45]
- **A second handout on algebra with complex numbers** is posted on Canvas. It is "very useful for our upcoming coverage of circuit frequency response, filters, and Bode plots" (board). Frequency response "involves dealing with essentially rational functions of complex numbers. And so, there are some subtleties to how one does that." [0:00:19–0:00:50]
- Office hours today are 2:30–4:00 PM in EER 3.802.

> [!warning] Board vs speech
> The typed board gives the usual office-hour slot as 10:30–11:55 AM; speech says "11:30 to 11:55AM." This note follows the board. Not exam-relevant.

- His tablet is back, so there is no doc-cam this time.

### 1. Recap: pn junction in equilibrium and the built-in potential [0:01:45–0:08:24]
**Board (f_0010, f_0036):** "From last time – pn junction diode." A bar with **p** on the left and **n** on the right, separated by a dashed junction line, with a source $V$ connected **+ to p, − to n**. "≡" the circuit symbol: a diode (triangle pointing right, so the **anode is the p side**) with the same source across it.

**"V = 0 (equilibrium)" band-edge diagram** (redraw it this way): p side on the left, n side on the right. $E_c$ is high on the left and bends down to a lower level on the right; $E_v$ runs parallel below it. A **single dashed $E_F$** runs straight across, near $E_c$ on the n side and near $E_v$ on the p side. Electrons (filled dots) sit on the n-side $E_c$; holes (open circles) sit at the p-side $E_v$. An arrow labelled **$eV_{bi}$** goes from the n-side $E_c$ up to the p-side $E_c$ level. Board: "**$V_{bi}$ = 'built-in' potential**", "**$I=0$**".

- $E_c(x)$ acts as the potential-energy function for electrons and $E_v(x)$ as the potential-energy function for holes. Hole energy increases *downward*: "to get holes to lower energy, that actually corresponds to an increase in potential energy because, really, what you're doing is you're getting electrons from down here to fill these states up here." [0:03:00–0:03:29]
- The barrier "is kind of what keeps all these electrons over here on the n side and all the holes on the p side." In equilibrium the barriers "exactly counteract the tendency of the electrons to wanna diffuse to the p side and the holes to wanna diffuse to the n side," so the **net current is zero**. [0:03:57–0:04:39]

**Origin of $V_{bi}$ (student question, 0:04:44; he answered "basically correct" and elaborated):**
- Lower board diagram (before contact): flat bands, with **P** and **n** drawn side by side. The p side has ionized acceptors (⊖) and holes; the n side has ionized donors (⊕) and electrons. "Originally, the Fermi level was, say, down here for p type and up here for n type." [0:06:33]
- After contact, electrons near the junction find holes and recombine "but only if they're pretty close to the junction" (red arrow on the board). The mobile carriers cancel, and "what you have left behind are these ionized dopants." [0:06:47–0:07:22]
- Upper diagram, red additions: ⊕ ionized donors on the n side and ⊖ ionized acceptors on the p side, both next to the junction.
- "**Anytime you have charge, you have an electric field, and the integral of the electric field is potential.** So that's actually where this built-in potential comes from. It's the potential that is produced by these ionized dopants." [0:08:01–0:08:15]

> [!note] Added context
> The region that holds the ionized dopants is the *depletion region* (or space-charge region). He did not use that term in this lecture.

### 2. Forward bias: the barrier is lowered by $eV$ [0:08:25–0:20:11]
**Sign convention:** "positive voltage to the p side relative to the n side. We can think of the n side as being grounded." [0:08:54]

**Board (f_0040/f_0057):** "When a voltage $V>0$ is applied across the diode, the potential energy difference, for electrons, is shifted by $(-e)V$:" with the annotation "↖ charge magnitude of electron" under $e$.
- Reason: electron potential energy = charge × potential = $(-e)\times(+V)$, so the p-side electron energies are **lowered**. The n side is grounded and unchanged. [0:09:10–0:09:41]
- $e$ = "fundamental charge ... 1.6 times 10 to the minus nineteenth coulombs." The charge of the electron is $-e$. [0:11:59–0:12:20] (Exact value $1.602\times10^{-19}$ C.)

> [!warning] Speech sign slip (board is correct)
> At 0:09:51 he says the barrier "will be reduced ... by an amount that is equal to minus e times that voltage," and at 0:13:20 that the Fermi-level difference "will be minus e times v." The *shift* of the p-side energies is $(-e)V$. The barrier is *reduced by* $+eV$, and the Fermi levels are *split by* $eV$. The board labels ($eV_{bi}-eV$, "eV") are correct. Write it the board's way.

**Three-panel figure (f_0057):**
1. Circuit: a diode between two terminals, with source $V$ (+ to the anode).
2. → p|n bar with $V$ (+ on p, − on n).
3. → **V > 0 band-edge diagram.** The p-side bands are still higher than the n side, but less so. The n-side $E_F$ (dashed) sits just under the n-side $E_c$. The p-side $E_F$ (dashed, labelled on the left) sits just over the p-side $E_v$, and the gap between the two $E_F$ lines is marked "**eV**". The barrier, from the n-side $E_c$ up to the p-side $E_c$ level, is labelled "**$eV_{bi}-eV$**". An electron at the barrier-top energy has an arrow pointing **left** (n → p); a hole has an arrow pointing **right** (p → n). "**→ I**" (current p → n).

- "The height of this barrier now is e times the built-in potential minus e times v. So it's lower." [0:14:37] An electron "up here in energy, now that can move across because it's not blocked by the barrier anymore," and likewise for holes. That motion is the current. [0:14:50–0:15:15]

**Board (f_0060):** "**The energy barriers for electrons + holes to move across the pn junction are shifted by $-eV$  ⟹ $I\neq0$.**" [0:19:21–0:19:59]

**Diffusion explained (student question, 0:15:18):** carriers move randomly. With equal concentrations on both sides, the left-movers and right-movers cancel. "If we have lots of electrons here and very few electrons here ... there will be some net motion of electrons from the high concentration area to the low concentration area. So that's what happens in diffusion generally." [0:15:29–0:16:32]

**Recombination after crossing (student question, 0:16:36):** injected electrons gradually recombine on the p side. Holes flow in from the left to replace them, so "over here, the current is carried mostly by the electrons. But then once you get out here, it's gonna be carried mostly by the holes. But that current basically is gonna be the same." [0:16:42–0:18:06]

**Fermi levels can differ (student question, 0:18:38):** "because we're no longer at equilibrium, the Fermi levels can be different?" "Yes." At high energies there is "still a higher probability of finding electrons over here on the right than on the left," hence net electron motion to the left. [0:18:49–0:19:07]

### 3. Quantifying it: the Fermi function at the barrier top [0:20:11–0:33:29]
**Board (f_0074):** "**The concentration of electrons/holes with energy higher than the barrier increases _exponentially_ with V:**" The current "will be proportional to that concentration." [0:20:45–0:21:38]

#### 3a. V = 0 [0:21:43–0:25:25]
**Figure (f_0076, f_0086):** the V = 0 band diagram on the left. The barrier-top line and the $E_F$ line are extended right onto a plot with **energy vertical** (shared with the band diagram) and **$f(E)$ horizontal, ticked 0 and 1**. The curve (drawn at ~0:27:12) sits at ≈1 at low energy, passes ≈½ at $E_F$, and decays to ≈0 above it. "Remember, it varies between zero and one." [0:22:36]

The energy at the top of the barrier is the n-side conduction-band edge plus the barrier [0:23:22]:
$$E_{top}=E_c+eV_{bi}$$
The Fermi function evaluated there [0:23:31–0:23:51] (board):
$$f(E_{top})=\frac{1}{e^{(E_c+eV_{bi}-E_F)/k_BT}+1}$$
**Approximation** [0:23:57–0:25:20]. The barrier top is "much higher than the Fermi level ... many times $k_BT$":
- at room temperature, "$k_BT$ ... is, like, **one fortieth of an electron volt**";
- $V_{bi}$ is "of the same order as the band gap ... somewhat less than the band gap. ... since the band gap of silicon is **1.1 eV**, ... VBI might be maybe **point six or point seven** eV";
- "so you're gonna have a large number in the exponent, and so this exponential is gonna be much greater than one."

Therefore (board):
$$f(E_{top})\approx e^{-(eV_{bi}+E_c-E_F)/k_BT}$$
"So that is our starting point."

> [!warning] Unit slip in speech
> "VBI might be maybe point six or point seven **eV**" [0:24:35]. $V_{bi}$ is a potential, about 0.6–0.7 **V**; the barrier energy $eV_{bi}$ is about 0.6–0.7 eV.

> [!check] Verified (python3)
> $k_BT(300\text{ K})=0.02585$ eV. His "1/40 eV" = 0.025 eV is 3.4 % low, which is fine as a mnemonic. $eV_{bi}/k_BT\approx23$–27, so $e^{23.2}\approx1.2\times10^{10}\gg1$, and dropping the $+1$ is safe. For scale: the Boltzmann form is 5 % off at $E-E_F=3k_BT$ and 0.6 % off at $5k_BT$.

#### 3b. V > 0 [0:25:25–0:33:29]
**Figure (f_0092/f_0120):** "V > 0:". The band diagram has a reduced barrier $eV_{bi}-eV$ and the Fermi levels split by $eV$. On the matching $f(E)$ axes, a dot marks $f=\tfrac12$ at the n-side $E_F$. "The Fermi distribution function is gonna be equal to one half there." [0:27:33]

Barrier-top energy [0:28:06]:
$$E_{top}=E_c+eV_{bi}-eV$$
Fermi function (board) [0:28:14–0:28:39]:
$$f(E_{top})=\frac{1}{e^{(E_c+eV_{bi}-eV-E_F)/k_BT}+1}$$
The same approximation holds, "unless you apply a very large voltage. But, usually, it's very difficult to get to that kind of voltage and still have a sustainable current." [0:28:44–0:29:04] Split the exponent: "It's minus eV over kBT in the denominator so becomes plus eV over kBT in the numerator." [0:29:43–0:30:00] Board:
$$f(E_{top})\approx e^{-(eV_{bi}+E_c-E_F)/k_BT}\;\underbrace{e^{eV/k_BT}}_{\text{"f(E) increases exponentially with V"}}$$
**Comparison** [0:30:03–0:31:04]: the first factor is the same as the $V=0$ value, "but now we're multiplying it by $e^{eV/k_BT}$." So
$$\frac{f(E_{top})\big|_{V}}{f(E_{top})\big|_{0}}=e^{eV/k_BT}.$$
"This concentration of electrons that we have up here with sufficient energy to move across the barrier, it has increased exponentially with the voltage." [0:30:54]

**Which $E_F$?** Use the **n-side** $E_F$, because "what we're portraying here is the probability of finding electrons ... specifically on the n side." [0:33:36–0:34:00]

**Board (f_0100/f_0120):**
- "Similarly, holes diffuse from p side to n side of the junction, with exponentially increasing probability with V." The hole barrier is reduced by the same amount. [0:32:05–0:33:02]
- "**⟹ I increases exponentially with voltage for V > 0.**" [0:33:06–0:33:26] Direction: "it flows from the p side to the n side in the diode." [0:39:58]

> [!warning] Notation: two different e's
> "I apologize for the notation here where we have these two e's that mean different things. This lower e here, obviously, is 2.71828. This e up here is the charge magnitude of the electron." [0:30:37–0:30:49] In $e^{eV/k_BT}$ the base is Euler's number and the $e$ in the exponent is $1.6\times10^{-19}$ C.

> [!check] Verified (python3)
> With illustrative values $V_{bi}=0.7$ V, $E_c-E_F=0.1$ eV, $T=300$ K (mine, not his): the exact Fermi ratio $f(V)/f(0)$ equals $e^{eV/k_BT}$ to better than $10^{-5}$ relative error. It is 47.9 at 0.1 V, $1.10\times10^5$ at 0.3 V and $2.51\times10^8$ at 0.5 V. **No board error.**

### 4. Q&A: two Fermi levels, and why there is no current at V = 0 [0:34:01–0:39:43]
**Electron and hole Fermi levels near the junction (student question, 0:34:01):** "Would it not immediately drop but decay off in the middle?" Answer: a single $E_F$ "implies that all the carriers that are described by that Fermi level are kind of in equilibrium with each other." Far from the junction that holds. Near the junction, carriers crossing over are still recombining, so "the electrons are in equilibrium kind of with themselves. The holes are in equilibrium with themselves, but the electrons are not in equilibrium with the holes." [0:34:19–0:36:07]

**Figure (green dashed, f_0110/f_0120):**
- *Electron* Fermi level: level with the n-side $E_F$ through the junction, then sloping down on the p side to the p-side $E_F$.
- *Hole* Fermi level: level with the p-side $E_F$ through the junction, then rising on the n side to the n-side $E_F$.

"In this region over here, they're different from each other, but eventually they become the same." [0:36:12–0:36:57]

> [!note] Added context
> Textbooks call these *quasi-Fermi levels* ($E_{Fn}$, $E_{Fp}$). He did not use the term.

**Why no current at V = 0 (student question, 0:37:02):** "There's nonzero probability that you find [an electron] above that energy ... why isn't current just spontaneously [flowing]?" Answer [0:37:32–0:39:43]:
- Yes, there are some n-side electrons above the barrier, "but then remember, there are also some up here" on the p side at the same energy (board: extra dots at the barrier-top level on both sides).
- "Since the Fermi level is the same on both the p side and the n side ... the concentration of electrons on the p side up at this energy is the same as the concentration of electrons that you have on the n side at this energy. So then this will cancel out with that."
- With $V>0$ the n side is "only $eV_{bi}-eV$ above the conduction band edge," while the p side is "much farther from the Fermi level," so right-to-left flow outweighs left-to-right.
- "**It happens that way because the Fermi levels are no longer the same on the two sides. That's sort of required in order to have net current flow. If the Fermi levels are the same, the current flow would be zero.**" [0:39:27–0:39:43]

### 5. Reverse bias (V < 0) [0:40:04–0:43:47]
**The naive extrapolation is wrong:** "if we just try to generalize that expression, it would tell us that, okay, the current still flowing in the same direction, but it becomes exponentially smaller. **But that's not quite correct.**" [0:40:20–0:40:38]

**Figure (f_0130 → corrected f_0175), "For V < 0, we have":**
- Negative voltage on the p side raises the p-side electron energies, so the p bands sit far above the n bands and the barrier is much higher.
- The over-barrier flow of n-side electrons is reduced exponentially. "And that does happen." [0:41:32–0:41:48]
- But there are also **minority carriers**: "some electrons here [p-side conduction band] and some holes over here [n-side valence band]." The board shows an electron on the p-side $E_c$ with an arrow → (sliding down into the n side) and a hole under the n-side $E_v$ with an arrow ← (into the p side), plus "**← I**".
- These carriers produce current "in the opposite direction." "As you make the voltage more negative, that doesn't really change the concentrations of these electrons or these holes. So these contributions to the currents are roughly constant." [0:42:25–0:43:04]

**Board:** "**I is in the opposite direction, and I roughly independent of V for V < 0.**" [0:43:04–0:43:39]

> [!warning] Board error, self-corrected at 0:51:31
> In the V < 0 diagram the n-side Fermi level (unlabelled dashed line) was first drawn **just above the n-side $E_v$**, where a p-type Fermi level would sit. While answering a later question he said "**This was not correct. This should be up here**," scribbled it out and redrew it **just below the n-side $E_c$** (f_0175, 0:52:48). The page-final frame f_0172 shows the wrong version. On an n-type side, $E_F$ sits near $E_c$.

### 6. The diode I–V characteristic [0:43:47–0:53:31]
**Board (f_0141/f_0172):** "**Thus, the overall I–V characteristic for a pn junction diode is:**"
$$\boxed{I=I_0\left(e^{eV/k_BT}-1\right)}$$
- $I_0$ is "some constant." $I_0e^{eV/k_BT}$ "is what is going to give us the exponentially increasing current ... for positive voltages." For negative $V$ the same term is an "exponentially decreasing contribution" from "the carriers that we have way up at this high energy." [0:44:23–0:45:15]
- "**This minus one comes from these electrons and these holes** [the minority carriers in the V < 0 picture] **moving across the junction ... And it's negative because that current is in the opposite direction.**" [0:45:15–0:45:27]

**Plot (blue, f_0155):** I vertical, V horizontal. For $V>0$ the curve rises exponentially. For $V<0$ it "exponentially approach[es] some small value" (a flat line just below the axis, at $-I_0$). A dashed branch at large negative $V$ plunges sharply: "other things that can happen ... eventually cause it to sharply increase ... we won't talk about that in detail." This is **breakdown** (named at 0:49:47). [0:45:36–0:46:08]

**Plot (red, f_0183), the zoomed-out view:** on a larger current scale the same curve "would still look like zero, and then all of a sudden, it'll turn up very rapidly." That is the one-way-valve picture. [0:49:52–0:50:26]

> [!check] Verified (python3, 300 K)
> $I/I_0$ = −0.979 (−0.1 V), −0.99956 (−0.2 V), −1.0000 (−0.5 V), 0 (0 V), 46.9 (+0.1 V), $1.10\times10^5$ (+0.3 V), $1.20\times10^{10}$ (+0.6 V). This matches the board sketch: it saturates at $-I_0$ within about 0.1 V of reverse bias, and the forward current is ~10 orders of magnitude larger by 0.6 V. *Self-check (mine):* at $V=0$ the two terms cancel ($I_0\cdot1-I_0=0$), consistent with the flat-$E_F$ argument in §4.

**Q (0:46:17): why is the −I₀ term present across the whole curve, even at large forward bias?** The −1 comes from "the electrons that you have just in equilibrium on the p side. This concentration of electrons doesn't change with the applied voltage. And so it's going to be constant." At a large enough forward voltage the model "will not be quite correct ... but usually by the time you get to that point, you have a very high current flowing, and then there will be other factors that end up limiting the current." [0:46:46–0:48:26]

**Q (0:48:30): a diode is a one-way valve, so is reverse current just negligible?** "You were not thinking about the concept of a diode or the functionality of a diode incorrectly." Reverse current exists but "is generally extremely small ... **five or 10 orders of magnitude or more** smaller than the current that you would get once the diode has turned on ... for most practical circuit purposes, that is going to be zero. Unless you have a really terrible diode." [0:48:58–0:49:47]

**Q (0:50:30, Nate): why is the exponential scaled by a tiny $I_0$?** "**You will derive that in problem set six.**" Brief version [0:51:07–0:53:18]:
- The exponential "comes from the nature of the Fermi distribution function."
- The prefactor comes from the concentrations of electrons on the n side and holes on the p side. These set how many carriers sit above the barrier, and they are tied together because "the product of the electron concentration and the hole concentration [on] the n side ... is gonna be constant, and it'll be the same as it is on the p side."
- That is why the forward and reverse terms share the same prefactor. The argument assumes both sides are the same semiconductor ("say silicon"). With different materials, "this prefactor would not necessarily be the same."

> [!note] Added context
> The constant product is the mass-action law, $np=n_i^2$. The equation is usually called the Shockley (ideal) diode equation, and $k_BT/e\approx25.9$ mV at 300 K is the thermal voltage. A consequence of his formula (checked in python): the forward current rises 10× per $k_BT\ln10/e\approx59.5$ mV, i.e. ≈60 mV/decade.

### 7. LEDs [0:53:33–0:57:00]
"Arguably or perhaps inarguably, their most important applications are not so much for diodes that go into a circuit for their electrical functionality. It is at least as important technologically that we have pn junction diodes for their **light emitting and light absorption** characteristics." [0:53:37–0:54:18]

**Board (f_0184/f_0186):** "LED: light emitting diode." The LED is "a **forward biased** pn junction." [0:54:48]

**Figure:** a forward-bias band diagram. Electrons cross right → left and holes cross left → right. At the junction an electron on $E_c$ has a long vertical arrow down to a hole on $E_v$, and a wavy arrow "⇝ **hν**" leaves the junction.

**Board text:** "**electrons + holes recombine and energy lost by the electron is emitted as light.**" Near the junction "you have a pretty high concentration of electrons here and a pretty high concentration of holes here." The electron "loses energy and drops down into this empty state ... that energy has to go somewhere. And in an LED, it's designed and optimized so that that energy is given off as a photon." [0:55:19–0:55:56]

**Q (0:56:31): what is that symbol?** "$h\nu$ ... the Greek letter nu ... the standard symbology used to indicate the energy of a photon: Planck's constant times ... the frequency of the photon." [0:56:36–0:56:51]

> [!warning] Spoken slip (self-corrected)
> "this is the frequency of the electron. Oh, sorry, of the photon." [0:56:43]

### 8. Solar cells [0:57:00–1:08:16]
"Kind of the inverse of that is a solar cell ... it's basically a pn junction under forward bias ... we have positive voltage that's applied here." [0:57:04–0:57:36]

**Figure (f_0199/f_0205), "solar cell":**
- A forward-biased band diagram with the $E_F$ split "eV".
- A photon "hν" (wavy arrow) arrives from the left. It "can be absorbed by an electron in the valence band. And if that photon has sufficient energy, that electron can move up to the conduction band" (vertical line from $E_v$ to $E_c$ at the junction).
- The electron goes → into the n side and the hole goes ← into the p side; "**I ←**".
- "That corresponds to current flowing in this direction, so **from lower voltage to higher voltage** ... that corresponds to energy being supplied, and that energy is coming from the energy of the photon." [0:57:42–0:58:58]

**Q (0:59:20): if LED and solar cell are the same process in reverse, why don't they both do both?** "Actually, in an LED, this process is also occurring. And in a solar cell, this process is also occurring, but the devices are designed and optimized so that in an LED you're kind of dominated by this process, and in the solar cell, you're dominated by this process." [0:59:35–1:00:01]

**Q (1:00:02): why are LEDs efficient but solar cells inefficient?** "There are very long answers." [1:00:33–1:05:44]
- **LED:** very efficient compared with incandescent or even fluorescent bulbs. When carriers recombine "they're usually pretty close to the band edge," so not much energy is lost.
- **Solar cell:** "low 20% range is very good efficiency." The reasons:
  1. "Sunlight is very broad spectrum," and every photon counts toward incident power. "**Any photon that has an energy less than the band gap just cannot be absorbed** ... there will be no state here for it to go into. So the minimum photon energy that can be absorbed is roughly the band gap." [1:02:11–1:02:57]
  2. Above-gap photons create "a high energy hole and a high energy electron, but then very quickly those will relax back down to the band edge energy, and then that extra energy is **lost as heat**." This is shown as green arrows on the board: a hot electron dropping to $E_c$ and a hot hole rising to $E_v$. "You lose just about all of it." [1:03:00–1:03:47] Illuminating at exactly the band gap ("an LED going into a solar cell") would be "a lot better," though not 100 %.
  3. "The power you're getting out is the current times the voltage." The operating forward voltage "is gonna be less than the bandgap ... because the built-in potential is gonna be less than the bandgap." [1:04:29–1:04:47]
  4. The operating point is not at full voltage or full current (see the I–V plot below).
- One percentage point of efficiency is "quite valuable"; 5 % "has a huge impact." [1:05:45–1:06:27]

**Figure: solar-cell I–V (f_0205, right):**
- The black curve is the **illuminated** cell: the diode curve shifted **down**. It crosses the I axis at a negative current and the V axis at a positive voltage.
- A dot marks the operating point in the **4th quadrant** ($V>0$, $I<0$), with dashed lines to both axes forming a rectangle. "You wanna operate at a point where the product of the current and the voltage in the fourth quadrant is the maximum ... you don't get the full voltage and you don't get the full current." [1:04:54–1:05:21]
- The red curve is the **dark** characteristic (the same curve "shifted upwards," through the origin).

**Q (1:06:31): without sunlight, does it become an LED?** In the dark the I–V shifts back up. "If you were operating at some point out here, then it would behave like a **terrible LED**." In "absolute darkness, there'll be no ... **photocurrent**, and it'll just be operating at the origin." At night there is a little light from the moon, stars and city glow, so "you'll have a tiny box." [1:06:49–1:08:07]

> [!note] Added context
> Silicon's $E_g\approx1.12$ eV at 300 K gives an absorption edge of $\lambda=hc/E_g\approx1.1\ \mu$m (python). The short-circuit and open-circuit points on the illuminated curve are $I_{sc}$ and $V_{oc}$, and the ratio of the max-power rectangle to $I_{sc}V_{oc}$ is the *fill factor*. He did not use these terms.

**Scope marker:** "**So that is everything on semiconductors.**" [1:08:16]

### 9. Circuit frequency response and filters [1:08:16–1:16:21]
**Board title (f_0209): "Circuit Frequency Response – Bode Plots and Filters." "Reading: Ulaby et al, Chapter 9."**
- Earlier the course analysed circuits "with sinusoidal signals that are at a fixed frequency, single frequency." Now the goal is to "generalize that idea to try to understand what's called **circuit frequency response**": "what does the behavior of that circuit look like as a function of frequency?" [1:08:28–1:09:14]
- "In addition to looking at it algebraically, we'll develop a graphical tool to understand and communicate this. This is known as **Bode plots**." [1:09:16–1:09:32]
- "Circuits that are designed to have a particular frequency response are often referred to as **filter circuits** ... they're giving a large response over some range of frequencies and a small response over some other range." [1:09:32–1:09:58]

**Definition (board, f_0214):** "**Filters are circuits that produce output signals with specific (useful) frequency dependence:**"
- Picture it as a two-port: "a circuit that has, say, two input terminals and two output terminals ... relationships between, say, the voltage at the input and the voltage at the output ... the dependence of those relationships on frequency is what we refer to as the response of the filter." [1:10:58–1:11:29] (Speech only; no diagram was drawn.)

**Filter types (board, f_0214 → f_0223):**

| Board term | Board definition | His gloss |
|---|---|---|
| **high-pass filter** | high-frequency signals transmitted, low-frequencies suppressed | high frequencies pass "quite easily, without much attenuation, and low frequency signals are strongly attenuated" [1:11:51] |
| **low-pass filter** | low-frequency signals transmitted, high frequencies suppressed | "by extension and probably pretty obviously" [1:12:41] |
| **band-pass filters** | signals within a specified frequency range are transmitted | [1:13:13] |
| **band-reject filters** | signals within a specified frequency range are suppressed | "kind of the inverse of" band-pass [1:13:48] |
| **passband** | range of frequencies transmitted, or "passed", by the circuit | [1:14:22] |

**Board (f_0223):** "**Circuit frequency response can be described algebraically by a _transfer function_, and**" ... speech continues: "**it can also be described graphically by what we call Bode plots.**" [1:15:15–1:15:58] (The last phrase is not in any captured frame.)

Close: "pick up with a discussion of **transfer functions** next time." [1:16:05]

---

## Ed Yu's conventions & notation

| Item | His convention (this lecture) |
|---|---|
| $e$ | **Magnitude** of the electron charge, $1.6\times10^{-19}$ C (positive). The electron charge is $-e$. He also uses $e$ for Euler's number in the same expression, and apologized for it [0:30:37]. |
| Bias sign | $V>0$ means **+ on the p side** relative to the n side; the n side is treated as grounded. The diode-symbol anode (triangle side) is the p side. |
| Current direction | Positive $I$ flows **p → n** through the diode (drawn "→ I" under the forward diagram, "← I" for reverse bias and the solar cell). |
| Band diagrams | p side on the **left**, n side on the **right**. $E_c$ and $E_v$ are solid curves; $E_F$ is **dashed**. Electrons are **filled dots** on $E_c$; holes are **open circles** at $E_v$. Ionized donors ⊕ and acceptors ⊖ are drawn in red. Energy increases upward for electrons; hole energy increases downward. |
| Barrier labels | $eV_{bi}$ at equilibrium and $eV_{bi}-eV$ under bias, measured from the n-side $E_c$ to the p-side $E_c$. The Fermi-level split is labelled "eV". |
| Built-in potential | $V_{bi}$, written with the subscript "bi", called the "'built-in' potential" (quotes on the board). |
| Thermal energy | $k_BT$ (written "$k_BT$", spoken "k sub b T"), ≈ 1/40 eV at room temperature. |
| Fermi function | $f(E)=\dfrac{1}{e^{(E-E_F)/k_BT}+1}$, plotted with **$f$ on the horizontal axis (0 to 1) and energy vertical**, sharing the band diagram's energy axis. $f(E_F)=\tfrac12$. |
| Diode law | $I=I_0\left(e^{eV/k_BT}-1\right)$, with $I_0$ spoken "I naught". |
| Photon | $h\nu$ (Greek nu), drawn as a wavy arrow "⇝". |
| Colours | Black for structure; red for ionized dopants, the near-junction recombination arrow, the zoomed-out diode I–V and the dark solar-cell I–V; green for the separate electron/hole Fermi levels and the hot-carrier relaxation; blue for the diode I–V curve. |
| Filter names (board spelling) | "high-pass", "low-pass", "band-pass", "band-reject", "passband", "transfer function", "Bode plots". |
| Reading citation | "Ulaby et al, Chapter 9." |

---

## Intuition & explanations he gives

- **Bands as potential energy:** "We can think of the conduction band edge energy as essentially a potential energy function for the electrons and the valence band edge energy as a potential energy function for holes." [0:02:56–0:03:10]
- **The barrier holds the carriers apart:** "This potential energy barrier is kind of what keeps all these electrons over here on the n side and all the holes on the p side." In equilibrium it "exactly counteract[s] the tendency" to diffuse. [0:03:57–0:04:30]
- **Where $V_{bi}$ comes from:** "Anytime you have charge, you have an electric field, and the integral of the electric field is potential ... It's the potential that is produced by these ionized dopants." [0:08:01]
- **Why a positive voltage lowers the p side:** "The potential energy is the charge of the electron, which is minus e, times the potential, which is positive." [0:09:20]
- **Diffusion in one sentence:** random motion plus unequal concentrations gives "net motion ... from the high concentration area to the low concentration area." [0:16:23]
- **Current is handed off from electrons to holes:** "Over here, the current is carried mostly by the electrons. But then once you get out here, it's gonna be carried mostly by the holes. But that current basically is gonna be the same." [0:17:58]
- **Why exponential:** "The nature of the Fermi distribution function then will tell us that that current will increase exponentially with the voltage." [0:10:22] "The Fermi distribution function at an energy that is just sufficient to cross the barrier ... increases exponentially with the voltage." [0:31:47]
- **Why the approximation holds:** the barrier top is many $k_BT$ above $E_F$ ($k_BT\approx1/40$ eV vs $V_{bi}\approx0.6$–0.7 V), so "this exponential is gonna be much greater than one." [0:24:04–0:24:59]
- **Equal Fermi levels mean no current:** "If the Fermi levels are the same, the current flow would be zero." Carriers at the same energy on both sides have equal occupation and their fluxes cancel. [0:37:53–0:39:43]
- **One Fermi level means mutual equilibrium:** "If you draw a single Fermi level, that sort of implies that all the carriers that are described by that Fermi level are kind of in equilibrium with each other." Near the junction electrons and holes are not, so each gets its own. [0:34:28–0:36:46]
- **Reverse bias saturates:** the minority-carrier concentrations "don't really change with the voltage," so their contribution is "roughly constant." [0:42:41–0:43:04]
- **The −1 term:** "comes from the electrons that you have just in equilibrium on the p side ... this concentration of electrons doesn't change with the applied voltage." [0:47:26–0:47:47]
- **What exponential growth looks like:** "Exponential increase is something that it looks like zero for a long time, and then all of a sudden it goes ... very high." [0:49:55]
- **LED and solar cell are one process run both ways:** both occur in both devices, and "the devices are designed and optimized so that ... you're dominated by this process." [0:59:38–1:00:01]
- **Why LEDs win:** carriers recombine "pretty close to the band edge," so little energy is lost. Solar cells lose all sub-gap photons and the excess energy of above-gap photons, and they run at $V<V_{bi}<E_g/e$. [1:01:10–1:04:47]
- **A filter is a two-port with a designed frequency dependence:** it gives "a large response over some range of frequencies and a small response over some other range of frequencies, and that's kind of what a filter does in some broad sense." [1:09:43]

---

## Emphasis & exam intel

No statement about Exam 2 scope, format or dates was made in this lecture. Per the TA hint in the brief ("semiconductor physics on the second exam"), §§1–8 are the semiconductor-physics source for Exam 2 P1.

1. **Exponential I–V, stated as the payoff** [0:31:31]: "That's the reason why when you have a diode, and you look at how the current depends on the voltage, that's why it increased exponentially with the voltage. It's basically because of this." Board: "⟹ I increases exponentially with voltage for V > 0."
2. **Net-current criterion** [0:39:34]: "If the Fermi levels are the same, the current flow would be zero."
3. **Naive reverse-bias extrapolation is wrong** [0:40:29]: "...the current still flowing in the same direction, but it becomes exponentially smaller. But that's not quite correct."
4. **Reverse-bias board statement** (f_0132): "I is in the opposite direction, and I roughly independent of V for V < 0."
5. **The diode equation, boxed in this note** (board f_0141): $I=I_0(e^{eV/k_BT}-1)$, with the −1 "negative because that current is in the opposite direction" [0:45:23].
6. **Size of the reverse current** [0:49:16]: "five or 10 orders of magnitude or more smaller."
7. **Two e's** [0:30:37]: "I apologize for the notation here where we have these two e's that mean different things."
8. **$k_BT$ number to memorize** [0:24:12]: "one fortieth of an electron volt" at room temperature. Si band gap is "1.1 eV" and $V_{bi}$ ≈ 0.6–0.7 V.
9. **PS6 link** [0:50:49, 0:53:27]: the $I_0$ prefactor "you will derive ... in problem set six."
10. **Optoelectronics framed as the most important application** [0:53:51]: "arguably or perhaps inarguably, their most important applications are not so much for diodes that go into a circuit."
11. **Solar-cell absorption limit** [1:02:30]: "Any photon that has an energy less than the band gap just cannot be absorbed."
12. **Scope marker** [1:08:16]: "So that is everything on semiconductors."
13. **Next topics** [1:15:22–1:16:10]: "described algebraically by what we call a **transfer function** ... graphically by what we call **Bode plots**." Next lecture starts with transfer functions. The complex-algebra handout is "very useful for our upcoming coverage of circuit frequency response, filters, and Bode plots" (board, 0:00:19).

---

## Student questions

| t | Question (reconstructed) | His answer |
|---|---|---|
| 0:04:44 | Does the built-in potential arise because electrons and holes initially diffuse across, leaving one side positive and the other negative? | "Basically correct." He drew the ionized donors (⊕, n side) and acceptors (⊖, p side) left behind after near-junction recombination; their charge gives a field whose integral is $V_{bi}$. |
| 0:11:57 | What is $e$ again? | The fundamental charge, $1.6\times10^{-19}$ C, the magnitude of the electron's charge; the electron's charge is $-e$. |
| 0:15:18 | What makes the electron move across? | Diffusion: random motion plus a concentration difference gives a net flow from high to low concentration. |
| 0:16:36 | Do the crossed electrons recombine with holes? | Yes, eventually. Holes flow in from the left to replace the ones lost, so the current is electron-carried near the junction and hole-carried farther into the p side, with the same total. |
| 0:18:38 | Since we're out of equilibrium, can the Fermi levels differ on the two sides? | Yes. At high energies there is a higher probability of finding electrons on the right, hence net electron motion to the left. |
| 0:33:36 | We used the higher Fermi level because that's the n-side one? | Yes. We want the probability of finding electrons on the n side, so the n-side $E_F$ is the right one. |
| 0:34:01 | In the middle, doesn't the Fermi level fall off gradually rather than jump? | Near the junction electrons and holes aren't in equilibrium with each other, so there are separate electron and hole Fermi levels (green dashed). They differ near the junction and merge far away. |
| 0:37:02 | At V = 0 some n-side electrons are above the barrier; why isn't there spontaneous current? | The p side has the same occupation at that energy (same $E_F$), so the fluxes cancel. Under bias the n side has many more carriers at that energy. Net current requires unequal Fermi levels. |
| 0:46:17 | Why does the −I₀ term persist across the whole I–V curve? What if forward bias pushed the n-side $E_c$ above the p-side $E_c$? | −1 comes from equilibrium minority electrons on the p side, whose number is independent of V. At a large enough forward V the model fails, but by then the current is high and other effects limit it. |
| 0:48:30 | Diodes are taught as one-way valves; is the reverse current just negligible? | Yes, practically: 5–10+ orders of magnitude below the on-current, effectively zero except for "a really terrible diode." Breakdown occurs at large reverse V. He sketched the zoomed-out red curve. |
| 0:50:30 | (Nate) Why is the exponential scaled by such a tiny $I_0$? | Derived in PS6. The exponential comes from the Fermi function; the prefactor comes from the n-side electron and p-side hole concentrations, linked by the constant $np$ product in one material (e.g. Si). With different materials the prefactor would differ. |
| 0:56:31 | What is that symbol (hν)? | Greek nu; $h\nu$ is the photon energy, Planck's constant times the photon frequency. |
| 0:59:20 | LED and solar cell are the same process in reverse; what stops each from doing both? | Both processes happen in both; each device is designed and optimized so that one dominates. |
| 1:00:02 | Why are LEDs so efficient but solar cells so inefficient? | LED: recombination near the band edges loses little. Solar: broad spectrum; sub-gap photons are not absorbed; above-gap excess is lost as heat almost instantly; $V_{op}<V_{bi}<E_g/e$; the operating point is below both full V and full I. Low-20 % is very good. |
| 1:06:31 | Without sunlight, would the solar cell act as an LED at the same voltage? | The dark I–V shifts back up (red curve). Forward-biased, it "would behave like a terrible LED." In absolute darkness there is no photocurrent and it sits at the origin; at night it has a "tiny box." |

---

## Exam relevance

**P1 (four conceptual short answers on filter concepts and semiconductor physics): primary.** This lecture plus the previous semiconductor lecture(s) are the semiconductor half of P1, and the filter definitions are the concept half. Likely stems (my prediction, built from what he emphasized):
- *Sketch the band diagram of a pn junction at V = 0, V > 0 and V < 0. Label $E_c$, $E_v$, $E_F$, the barrier height and the Fermi-level split.* Use $eV_{bi}$; $eV_{bi}-eV$ with $E_F$ split $eV$; $eV_{bi}+e|V|$.
- *Explain why the forward current of a pn junction increases exponentially with V.* The barrier is lowered by $eV$. The occupation at the barrier top is in the Boltzmann tail, $f\approx e^{-(E-E_F)/k_BT}$, so it grows by $e^{eV/k_BT}$. The current is proportional to the number of carriers above the barrier.
- *Why is the reverse current small and nearly independent of V?* It is carried by minority carriers sliding down the barrier, whose concentration is set by equilibrium doping and not by V. It saturates at $-I_0$.
- *Why is $I=0$ at $V=0$ even though some carriers can cross?* $E_F$ is flat, so the occupation at each energy is equal on both sides and the fluxes cancel.
- *Where does the built-in potential come from?* Ionized dopants left after near-junction recombination; charge gives a field, and the integral of the field is the potential.
- *Explain LED operation, and why a solar cell can't convert all incident solar power.* Sub-gap photons pass through; above-gap excess energy thermalizes; $V_{op}<V_{bi}<E_g/e$; operation is at the max-$|IV|$ point.
- *Define high-pass, low-pass, band-pass, band-reject and passband, and say what a transfer function and a Bode plot each describe.*

**P2 (passive filter design or max power transfer): low.** Only the filter vocabulary (which band must be passed). No design method was given.

**P3 (filter transfer function, cutoff, Bode plots): low, prerequisite only.** The words "transfer function" and "Bode plots" are introduced here; the method starts next lecture. The complex-algebra handout announced today is the algebra prerequisite.

**P4 (active or RLC filter: H(ω), type, Bode, design ratio): low.** The filter-type taxonomy here is what P4's "identify the filter type" sub-part uses.

> [!summary] Board-error audit
> - **One board error, self-corrected:** the n-side $E_F$ in the V < 0 diagram was drawn near $E_v$ and moved to just below $E_c$ at 0:51:31 (f_0172 wrong, f_0175 fixed).
> - **Speech slips:** "$V_{bi}$ ... 0.6 or 0.7 eV" (should be V); the barrier "reduced by minus e times V" (it is reduced by $+eV$; the board is correct); "electrons on the p side ... or sorry, on the n side"; "frequency of the electron" (corrected to photon); the usual office hours are "11:30" in speech vs 10:30 on the board.
> - **Rounding:** "$k_BT\approx1/40$ eV" is 3.4 % below 0.02585 eV.
> - **ASR artefacts:** "framing level is z times v" = Fermi level is eV; "k sub b times c" = $k_BT$; "connection main edge" = conduction band edge; "Ulaby Dahl" = Ulaby et al.
> - **No numeric worked example** appeared; every formula on the board checks out (python3).

---

## Common mistakes / traps

- **Bias sign:** forward bias is **+ on the p side** (anode). It *lowers* the barrier to $e(V_{bi}-V)$. Reverse bias raises it to $e(V_{bi}+|V|)$.
- **"Reduced by −eV":** the p-side electron energies shift by $(-e)V$, but the barrier is reduced by $+eV$. Don't write a barrier of $eV_{bi}+eV$ for forward bias.
- **Two e's:** in $e^{eV/k_BT}$ the base is 2.718 and the exponent's $e$ is $1.6\times10^{-19}$ C. With $V$ in volts and $k_BT$ in joules, or $eV$ in eV with $k_BT$ in eV, the exponent is dimensionless. Don't mix eV and J.
- **$V_{bi}$ vs $eV_{bi}$:** a potential (V) vs an energy (eV). He said "0.6 or 0.7 eV" for $V_{bi}$.
- **Wrong Fermi level:** n-side electron occupation uses the **n-side** $E_F$. On an n-type side $E_F$ sits near $E_c$, not near $E_v$ (his own board slip at 0:51:31).
- **Naive reverse-bias extrapolation:** reverse current is *not* "the forward current, exponentially smaller." It flows the opposite way and saturates at $-I_0$, because minority carriers are fed by equilibrium concentrations.
- **"Diodes block reverse current completely":** false strictly; it is $-I_0$, which is tiny (5–10+ orders smaller). The zero-current picture is a zoomed-out approximation. Breakdown occurs at large reverse $V$.
- **Dropping the +1 in $f(E)$ only works in the tail:** the Boltzmann form needs $E-E_F\gg k_BT$. It is 5 % off at $3k_BT$ and badly wrong near $E_F$ (it gives $f(E_F)=1$ instead of ½).
- **Single vs separate Fermi levels:** under bias, near the junction, electrons and holes need separate Fermi levels. One flat $E_F$ means equilibrium and zero net current.
- **Solar-cell quadrant:** the cell delivers power in the **4th quadrant** ($V>0$, $I<0$, current flowing from low to high voltage inside the device). The max-power point is at neither $V_{oc}$ nor $I_{sc}$.
- **Photon absorption:** $h\nu<E_g$ is not absorbed at all. The excess $h\nu-E_g$ of above-gap photons is lost as heat, not converted.
- **Filter vocabulary:** band-reject is the inverse of band-pass. The passband is a *range of frequencies*, not a gain value. A transfer function is algebraic and a Bode plot is graphical; they are two descriptions of the same frequency response.

---

## Self-check

**Q1.** Starting from the Fermi function, show by what factor the occupation probability at the barrier-top energy (for n-side electrons) changes when a forward bias $V$ is applied, relative to $V=0$. Evaluate the factor for $V=0.1$ V at 300 K.

> [!question]- Answer
> At $V=0$: $E_{top}=E_c+eV_{bi}$, so $f_0=\big[e^{(E_c+eV_{bi}-E_F)/k_BT}+1\big]^{-1}\approx e^{-(eV_{bi}+E_c-E_F)/k_BT}$. The $+1$ is dropped because $E_{top}-E_F\gg k_BT$.
> At $V>0$: the barrier drops by $eV$, so $E_{top}=E_c+eV_{bi}-eV$ and $f_V\approx e^{-(eV_{bi}+E_c-E_F)/k_BT}\,e^{eV/k_BT}$.
> Ratio: $f_V/f_0=e^{eV/k_BT}$.
> With $k_BT=0.02585$ eV: $e^{0.1/0.02585}=\mathbf{47.9}$. With his "1/40 eV": $e^{4}=54.6$. (python3)

**Q2.** At $V=0$ some electrons on the n side have enough energy to cross the barrier. Why is the net current zero, and what condition is required for net current?

> [!question]- Answer
> With no bias there is a single, flat $E_F$. At any energy above the barrier, the occupation $f(E)$ is the same on the p side as on the n side, so the electrons diffusing n → p are balanced by electrons at the same energy diffusing p → n (likewise for holes). Net current requires the Fermi levels on the two sides to differ, which an applied bias provides (split $=eV$). His words: "If the Fermi levels are the same, the current flow would be zero."

**Q3.** Using $I=I_0(e^{eV/k_BT}-1)$ at 300 K, compute $I/I_0$ at $V=-0.2$ V and $V=+0.6$ V. Explain physically where each term comes from and why the reverse current is nearly independent of $V$.

> [!question]- Answer
> $I/I_0(-0.2\text{ V})=e^{-7.74}-1=\mathbf{-0.99956}$. $I/I_0(+0.6\text{ V})=e^{23.2}-1\approx\mathbf{1.20\times10^{10}}$. (python3)
> - The **exponential term** is majority carriers (n-side electrons, p-side holes) crossing the barrier. Their number above the barrier scales as $e^{eV/k_BT}$.
> - The **−1 term** is minority carriers (electrons in the p side, holes in the n side) sliding *down* the barrier in the reverse direction. Their concentration is fixed by equilibrium doping and does not change with $V$, so it is a constant $-I_0$. Under reverse bias the exponential dies off and $I\to-I_0$.

**Q4.** Give the four reasons from lecture why a silicon solar cell is at best in the "low 20 %" efficiency range.

> [!question]- Answer
> 1. Sunlight is broad-spectrum; photons with $h\nu<E_g$ cannot be absorbed (no empty state to go into), yet they count toward the incident power.
> 2. Photons with $h\nu>E_g$ create hot electrons and holes that relax to the band edges almost instantly; the excess $h\nu-E_g$ is lost as heat.
> 3. Output power is $IV$, and the operating forward voltage is below $V_{bi}$, which is below $E_g/e$.
> 4. The max-power operating point in the 4th quadrant gives neither the full voltage nor the full current.
>
> (Contrast: an LED is efficient because carriers recombine near the band edges.)

**Q5.** A circuit passes signals between 2 kHz and 5 kHz with little attenuation and suppresses everything else. Name the filter type and its passband, and name the algebraic and the graphical descriptions of its frequency response.

> [!question]- Answer
> It is a **band-pass filter**; the **passband** is 2–5 kHz (the range of frequencies "transmitted, or 'passed', by the circuit"). The algebraic description is the **transfer function**; the graphical description is the **Bode plot(s)**. (If it suppressed 2–5 kHz and passed the rest, it would be a band-reject filter.)
