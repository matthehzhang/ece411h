---
course: ECE 411H
date: 2026-10-12
instructor: Prof. Ed Yu
topic: Fermi distribution function at low and high T, density of states, k_BT and the electron volt, why intrinsic n and p are tiny, doping (donors/acceptors, n-type/p-type), doping levels and the mobility trade-off, pn junction in equilibrium (constant E_F, band bending, built-in potential), forward-bias turn-on preview
reading: none named in this lecture
source: Recordings/2026-10-12-semiconductors-doc-cam (transcript + 37 document-camera pages; 9 blurry, replaced by neighbouring frames; see frames/pages_described.md)
tags: [ece411, lecture, semiconductors, fermi-distribution, density-of-states, doping, donors, acceptors, pn-junction, built-in-potential, exam2]
source_quality:
  - "Document camera on paper (the tablet failed that morning). Page detection was tuned for tablets: 37 distinct pages from 42 page-final frames, so expect missed or spurious breaks."
  - "9 blurry pages (f_0001, f_0083, f_0086, f_0131, f_0170, f_0192, f_0288, f_0357, f_0455). Each was read from a sharp neighbouring frame listed in pages_described.md."
  - "The camera cropped the right edge of the sheet (he said so at 0:01:00). Some announcement text is cut off."
  - "Speech: Deepgram Nova-3, 80 min, mean confidence 0.96. 84 words < 0.55; 10 utterances < 0.7, the lowest at 0:47:21, 0:34:25, 1:13:29, 0:54:49, 0:51:53."
  - "AUDIO GAP: the transcript ends mid-sentence at 1:16:02; the recording runs to ~1:19:43. Pages 36-37 (E_c(x)/E_v(x) as potential energies) are board-only."
  - "Zoom switched to a participant's name tile at 1:16:39-~1:17:00 (no board in those frames)."
  - "Student questions are off-mic and fragmentary. Spoken math is transcribed as words; every number was re-derived with python3."
---

# 2026-10-12: Fermi Distribution, Doping, pn Junction Built-in Potential

## Summary

- **Write and interpret the Fermi distribution function.** $f(E)=\dfrac{1}{e^{(E-E_F)/k_BT}+1}$ is the *probability that a state at energy $E$ is occupied by an electron*. It goes from 1 at low $E$ to 0 at high $E$, equals ½ exactly at $E_F$, and departs from 0 or 1 only within a few $k_BT$ of $E_F$. That transition window widens as $T$ rises.
- **Sketch $f(E)$ next to the band diagram at low T and high T.** Put $E$ on the vertical axis, $f$ on the horizontal axis from 0 to 1, and mark $E_c$, $E_v$, $E_F$. At low T the VB is nearly full and the CB nearly empty. At high T a few electrons appear in the CB and holes (empty states) in the VB.
- **Separate occupation probability from states.** $f$ says nothing about whether states exist. The density of states (DOS, states per volume per energy) is zero in the gap. Electrons per energy = DOS × $f$, and $n$ = that product integrated over the CB.
- **Do the $k_BT$ and eV arithmetic.** At 300 K, $k_BT=0.0259$ eV (about 1/40 eV); $k_B=8.617\times10^{-5}$ eV/K; 1 eV $=1.602\times10^{-19}$ J. $E_g(\text{Si})\approx1.1$ eV $\approx 42\,k_BT$, so in a pure, perfect semiconductor $n$ and $p$ are tiny (suppressed by roughly $e^{-20}$).
- **Explain doping in two pictures.** In the bond picture, P or As (5 valence electrons) leaves one extra electron, which can only go to an antibonding state, i.e. the CB. These atoms are **donors** and make **n-type** material with $E_F$ near $E_c$. B or Al (3 valence electrons) leaves one bond short an electron, i.e. an empty VB state (a hole). These atoms are **acceptors** and make **p-type** material with $E_F$ near $E_v$. In the band picture, draw the matching $E_F$ position and the shifted $f(E)$.
- **Explain the "can't get both" rule.** Moving $E_F$ toward $E_c$ raises $n$ but lowers $p$, and vice versa. At a given $T$ you cannot raise both.
- **Know the doping magnitudes.** Si has $\sim5\times10^{22}$ atoms/cm³; doping is $10^{15}$–$10^{20}$ cm⁻³, i.e. 1 in 500 down to 1 in $\sim5\times10^7$. More dopants give more carriers but more ionized-impurity scattering, hence lower mobility. The trade-off is application-specific.
- **Draw and explain the pn junction in equilibrium.** Carriers diffuse (electrons n→p, holes p→n). In equilibrium **$E_F$ is constant across the whole device**, which is the zero-current condition. The bands bend so that the p side sits higher by $eV_{bi}$. The ionized dopants left behind create charge, then a field, then the built-in potential $V_{bi}$, which blocks further diffusion.
- **Forward-bias preview.** Forward bias is + on the p side. It lowers the barrier, and the current rises exponentially. It turns on noticeably within a couple tenths of a volt of cancelling $V_{bi}$, roughly 0.6 V for Si. $V_{bi}$ relates to turn-on, **not** to breakdown, which happens under reverse bias.

---

## Content

### 0. Recording note and announcements [0:00:03–0:04:14]
- **Technology:** his tablet blue-screened that morning ("encryption policies for UT had changed"), so he lectured on paper under the document camera. "The camera does not capture the full width of the paper." [0:00:16–0:01:05]
- **Semester Exam 1 results** (board f_0028/f_0036): mean 71.3, median 74.5, std dev 12.8, range 40.5–92.5 (the board's right edge is cut off; the value comes from speech), N = 25. Regrade requests are open on Gradescope until **5 PM Fri 10/16/26**; read the regrade section of the announcement. "Since the grades are all curved, the most important thing is that everyone's exam is graded consistently, according to the same rubric." A misapplied rubric gets fixed; "not enough partial credit" does not. [0:01:05–0:02:50]
- **"This week's recitation will cover material important (!) for Problem Set 6."** He called it "complementary to rather than repeating" class [0:02:54]. He later said the recitation is "today" and that the TA (Darsh) would cover the density of states [0:16:44].
- Office hours Wed 10/14/26 move to 2:30–4:00 PM, instead of the usual morning slot (10:30–11:55 (?) per the board), still in EER 3.802. He may be late to office hours today because of a visit to IT. [0:03:12–0:03:52]
- Context: "we had started a more detailed discussion of semiconductors in our last class meeting before the exam." [0:04:00] "We may not cover quite as much material today." [0:04:29]

### 1. The Fermi distribution function (recap) [0:04:14–0:07:16]
Board heading (f_0099): **"From last time: Fermi distribution."** Board (f_0107):

$$f(E)=\frac{1}{e^{(E-E_F)/k_BT}+1}$$

- $k_B$ = Boltzmann's constant $=1.381\times10^{-23}$ J/K. It is "a constant that allows us to convert temperature into energy." [0:05:46–0:06:11]
- $T$ = temperature, in K.
- $E_F$ = **Fermi energy or Fermi level** = **the energy at which $f(E)=\tfrac12$.** [0:06:25–0:06:47]
- Meaning: $f(E)$ is "the probability that a state at a given energy is occupied by an electron." [0:05:23] The goal is to use it to "calculate… the concentration of electrons and holes" in a semiconductor. [0:06:53]

### 2. Sketch of $f(E)$ at low temperature [0:07:16–0:12:43]
**Limits, argued from the formula** [0:08:01–0:08:56]:
- $E\gg E_F$ gives a large exponential in the denominator, so $f\to0$. "The probability of finding an electron at a very high energy state is extremely small."
- $E\ll E_F$ gives the exponential of a negative quantity, which is small, so $f\to1$. "States at very low energy are very likely to be occupied by electrons."
- In between, $f$ "decreases exponentially… as we go to very high energies" and "exponentially approaches one as we go to low energies." [0:09:16–0:09:26]

**Width:** since the exponent is $(E-E_F)/k_BT$, "the range of energies over which the Fermi distribution function is… significantly different from zero or one, is just within a few times $k_BT$ of the Fermi level." [0:09:39–0:10:20] "As the temperature increases, that transition… will occur over a wider range of energies." [0:10:29]

**Figure: "low T" (f_0130/f_0138). Redraw it as follows.**
- Left panel: vertical axis $E$, horizontal axis $f(E)$ with ticks 0 and 1. Mark $E_F$ on the $E$ axis.
- The curve hugs $f\approx0$ at the top, drops through a dot at $(f=\tfrac12, E_F)$, and saturates at $f=1$ at the bottom. The transition is fairly sharp.
- A small double arrow across the transition is labelled "few × $k_BT$".
- Right panel, at the same energy scale: a horizontal line $E_c$ with a brace "CB" above it, and a horizontal line $E_v$ with hatching below it and a brace "VB". $E_F$ is dotted, about mid-gap.
- Written below: **"VB nearly full of electrons. CB nearly empty."**

Reasoning [0:10:51–0:12:31]: VB states lie far below $E_F$, so they are "essentially completely filled". CB states lie far above $E_F$, so they are "just about completely unoccupied." Because the transition is narrow and **"the Fermi level is near the middle of the band gap, which has to be the case because the concentration of electrons and holes have to be equal to each other"** (pure semiconductor), there are "hardly any electrons in the conduction band, hardly any holes in the valence band."

> [!note] Added context (not from this lecture), verified with python3
> $f(E_F\pm k_BT)=0.269/0.731$, $f(E_F\pm2k_BT)=0.119/0.881$, $f(E_F\pm3k_BT)=0.047/0.953$, $f(E_F+5k_BT)=0.0067$. The 10 %→90 % width is $2\ln9\,k_BT=4.4\,k_BT$, which quantifies his "few $k_BT$". The probability that a state is **empty** (a hole) is $1-f(E)$, and $f(E_F+\Delta)=1-f(E_F-\Delta)$. In a real intrinsic semiconductor $E_F$ is mid-gap only if the CB and VB effective densities of states are equal; in Si it sits very slightly below mid-gap. "Near the middle" is his wording.

> [!warning] Sketch inaccuracy (minor)
> On both hand sketches the dot marking $E_F$ sits at roughly $f\approx0.4$, not 0.5 (estimated from pixels (?)). The written definition, $f(E_F)=\tfrac12$, governs. On an exam, draw the crossing at exactly ½.

### 3. $f(E)$ at high temperature [0:12:43–0:15:10]
**Figure: "high T" (f_0138, f_0145/f_0147).**
- The same axes with $E_F$ at the **same energy** as before.
- The curve is much more gradual ("the slope… will get more shallow"). A long double arrow spanning most of the axis is labelled "few ~$k_BT$".
- Band panel: dots (electrons) just above $E_c$ in the CB, and open circles (holes) at the top of the hatched VB just below $E_v$.
- Written: **"electrons in CB / holes (empty states) in VB."**

He explains that the higher temperature spreads the transition, which raises the probability of occupying CB states. "Most of the valence band states will still be occupied," but some are empty; "holes, remember, which are empty states in the valence band." [0:13:32–0:15:07]

### 4. Probability vs. states: the density of states [0:15:10–0:20:11]
A student asks why the gap region shows no electrons although $f$ is nonzero there [0:15:24]. His answer [0:15:36]:

> "The Fermi distribution function only tells us what is the probability that a state at a given energy will be occupied by an electron. It does not imply anything about whether there are states at that energy or not."

"If the state is not present, we won't have any electrons in this range of energies." [0:16:07]

**Density of states** [0:16:48–0:18:42]: it applies "at a given energy… in the conduction band or in the valence band or in the bandgap." It "tells us how many states are there basically at that energy," "normalized to the volume… a concentration of states… and then there's a per unit energy also."

**Figure (f_0160), drawn dashed because he had no second colour.** Vertical energy axis aligned with the band diagram; horizontal axis labelled "DOS". The CB curve starts at zero at $E_c$ and opens up and outward. The VB curve starts at zero at $E_v$ and opens down and outward. The DOS is **zero in the gap**. "Fewer states right at… the extrema of the bands and then increasing as you move farther into the bands."

**How $n$ follows** (spoken, not written; the notation is mine) [0:18:12–0:18:42]: "this density of states… multiplied by the Fermi distribution function… will then tell you how many electrons do you have at that energy, and then you would integrate over energy in a given band":

$$n=\int_{\text{CB}}\mathrm{DOS}(E)\,f(E)\,dE$$

**Is the DOS continuous?** (student, 0:18:42) For "an infinite semiconductor crystal, this would be a continuous function." A finite crystal has a discrete spectrum, but the levels are "extremely close together in energy," so "we basically think of the density of states as a continuous function but not necessarily differentiable." His sketch has "a cusp down here, where the derivative is not continuous." [0:19:00–0:20:00]

> [!note] Added context
> The hole concentration is the analogue over the VB with the empty-state probability: $p=\int_{\text{VB}}\mathrm{DOS}(E)\,[1-f(E)]\,dE$. He did not write this.

### 5. Putting numbers on it: $k_BT$ and the electron volt [0:20:11–0:28:24]
Board (f_0191 → f_0199 → f_0209/f_0216 → f_0222):

$$\text{At room temperature (300 K):}\quad k_BT=(1.381\times10^{-23}\ \text{J/K})(300\ \text{K})\left(\frac{1\ \text{eV}}{1.602\times10^{-19}\ \text{J}}\right)=0.0259\ \text{eV}$$

$$\Rightarrow\ k_B=1.381\times10^{-23}\ \text{J/K}=8.617\times10^{-5}\ \text{eV/K}$$

**eV = "electron volt"** = the energy required to increase the potential of an electron charge magnitude ($1.602\times10^{-19}$ C) by 1 volt $=1.602\times10^{-19}$ J.

His motivation [0:21:30–0:23:52]:
- In joules, $k_BT$ is $\sim10^{-21}$ J, and it is "inconvenient to have to carry around" such powers of ten.
- We want a unit with magnitude near 1 and "nice, easy physical interpretation… in the context of semiconductors and electricity."
- Potential energy is charge × voltage, so "a natural unit of energy to use is the amount of energy that it takes to change the potential of an electron… by one volt."
- $k_BT$ at 300 K "is roughly one fortieth of an electron volt." [0:25:22]
- "Boltzmann's constant really converts temperature into energy." [0:25:56] Written in eV/K it gives energies directly in eV.

> [!warning] Speech error, 0:21:40
> He said $k_BT$ in joules is "of order 10 to the minus 20… maybe four times 10 to the minus 20." **Wrong by 10×.** $1.381\times10^{-23}\times300=4.14\times10^{-21}$ J (python). The board never shows the joule value, and the eV result, 0.0259, is correct.

> [!check] Verified (python3)
> $k_BT=4.143\times10^{-21}$ J $=0.02586$ eV, and $1/k_BT=38.7$ eV⁻¹, so "≈ 1/40" holds. **[board differs, immaterial]** His rounded constants give $k_B=1.381\times10^{-23}/1.602\times10^{-19}=8.620\times10^{-5}$ eV/K. The board's $8.617\times10^{-5}$ is the accepted (CODATA) value. Both round to $8.62\times10^{-5}$ at 3 s.f.

### 6. Band gap vs. $k_BT$: why a pure semiconductor has few carriers [0:28:24–0:31:10]
Board (f_0226/f_0228): **"The energy band gap $(E_c-E_v)$ of Si is ~1.1 eV."** Then (f_0251): **"Thus, in a pure, perfect semiconductor, n and p are typically very small unless T is very high."**
- The eV is convenient "somewhat coincidentally": band gaps come out around 1 eV. [0:28:50]
- 1.1 eV is "40 times the amount of energy associated with $k_BT$ at room temperature," so for a "compositionally pure and structurally perfect semiconductor" the electron and hole concentrations are "down by a factor of, you know, roughly e to the minus 20 or so." [0:29:29–0:30:05]
- "Very high" temperature "would not be typical" for Si. [0:31:10]

> [!check] Verified (python3)
> $E_g/k_BT=1.1/0.02586=42.5$, so "40 times" holds. With $E_F$ mid-gap, $(E_c-E_F)/k_BT=0.55/0.02586=21.3$, so $f(E_c)=5.8\times10^{-10}\approx e^{-21}$. That is consistent with his "roughly $e^{-20}$".

### 7. To get useful carrier densities, move $E_F$ [0:31:10–0:33:26]
Board (f_0255): **"To increase n or p to levels useful for devices, need to shift the Fermi level closer to either $E_v$ or $E_c$."**
- "Electrons and holes are what actually carry current in a semiconductor." [0:31:22]
- Moving $E_F$ much closer to the CB gives "a lot more electrons in the conduction band, but… even fewer holes in the valence band," and the reverse for the VB. [0:32:06–0:32:30]
- **"We can get either many more electrons or many more holes, but, at a given temperature, we can't get both."** [0:33:12]

> [!note] Added context
> The quantitative form of "can't get both" is the mass-action law, $np=n_i^2$ at a given $T$ (independent of $E_F$ for non-degenerate material). He did not state it in this lecture. $n_i$ for Si at 300 K is of order $10^{10}$ cm⁻³; texts quote 1.0–1.5×10¹⁰, so use whatever value a problem gives.

### 8. Shifting the Fermi level: doping [0:33:26–0:36:00]
Board (f_0278, f_0279): **"Shifting the Fermi level – doping."** "Can we shift $E_F$ to be closer to $E_v$ or $E_c$, so $n\neq p$ ($n\gg p$ or $p\gg n$)? Yes! This can be accomplished by **doping**: the introduction of impurity atoms into the [semiconductor crystal]."
- Doping is "taking some of the atoms in a semiconductor crystal and replacing them with a different element." [0:33:53]
- The impurity atoms have "a different number of valence electrons… so that it shifts the balance between the electrons and the holes." [0:35:00–0:35:15]

### 9. Donors and n-type doping [0:35:59–0:44:48]
Board (f_0305, f_0317): **"Consider a Si crystal. Si has 4 valence electrons. If impurity atoms with 5 valence electrons/atom, e.g., phosphorus (P) or arsenic (As), are introduced in place of some Si atoms, the crystal will have an excess of electrons, which will occupy conduction-band states ⇒ $E_F$ will be closer to $E_c$ than to $E_v$."**

**Figure (f_0347/f_0350). Redraw as three panels left to right.**
1. **Bond picture:** As in a central circle with four Si circles (up, right, down, left). Each As–Si bond is an oval holding **two dots**, one electron from Si and one from As. A fifth dot sits loose beside the As, with an arrow labelled **"extra electron"**.
2. **Band picture:** a vertical energy arrow $E$. The $E_c$ line has a brace "CB" above it and **dots just above $E_c$** (electrons). **$E_F$ is dashed just below $E_c$.** The $E_v$ line has hatching below it (full VB) and a brace "VB".
3. **$f(E)$:** $E$ vertical, $f$ from 0 to 1. The dashed $E_F$ is drawn high, so the 0→1 transition sits up near the CB.

Text: **"Impurity atoms that provide extra electrons are called <u>donors</u>."**

**Why the extra electron goes to the CB** [0:40:38–0:41:08]: recall that bonding states form the VB and antibonding states form the CB. "This arsenic atom… all its bonding states are already filled… we've already formed these four bonds. So this extra electron, the only place that it can go, is into the antibonding orbital or, equivalently, the conduction band."

**Why holes also go down** [0:42:22–0:42:50]: "If we had any holes in the valence band, some of these electrons would like to lower their energy so they'll go and fill… the empty states in the valence band. So we'll also be decreasing the concentration of holes." Both effects together put $E_F$ "up here closer to the conduction band edge." [0:43:05]

**Name:** "We call them donors because they're essentially donating one of their valence electrons to the conduction band." [0:44:13]

### 10. Student question: why P vs. As, and why not 6 valence electrons? [0:44:49–0:48:08]
- **P vs. As:** "For any given dopant type… there are often multiple impurity elements that you could introduce that will work… phosphorus and arsenic will both work, and they both work well… both pretty commonly used." [0:45:25–0:45:47]
- **Size matters:** going farther down the periodic table gives "physically bigger atoms," and sticking "this big atom into a space where there was previously a small atom… produces some distortion of the lattice around it. That affects the electronic states." Going up "sometimes… can work, but sometimes there are issues… because of the size mismatching." [0:45:52–0:46:46]
- **Why not 6 valence electrons (e.g., selenium):** one electron goes easily into the CB, but "then what you have left is a positively charged ion in the lattice… That makes it harder to get that second electron off." "**One more or one fewer, if you want holes, is what works best.**" [0:47:02–0:48:00]

### 11. Acceptors and p-type doping [0:48:11–0:53:20]
Board (f_0365, f_0369): **"Conversely, if impurity atoms with 3 valence electrons/atom, e.g., boron (B) or aluminum (Al) are introduced, crystal has too few electrons to form all its bonds (occupy VB states) ⇒ extra holes will be present in VB, $E_F$ will be closer to $E_v$ than $E_c$."**

**Figure (f_0401 → f_0435/f_0436). Redraw as three panels.**
1. **Bond picture:** B in a central circle with four Si neighbours. Three bonds have two dots each. The **left** bond oval holds one dot (from Si) and **one open circle**, with an arrow labelled **"missing electron"**.
2. **Band picture:** energy arrow $E$. The $E_c$ line has an empty "CB" brace above it. **$E_F$ is dashed just above $E_v$.** The $E_v$ line has **open circles (holes) just below it**, with the VB hatched below.
3. **$f(E)$:** the dashed Fermi line is drawn low, so the transition sits near the VB.

Reasoning [0:51:29–0:52:46]: the fourth bond lacks an electron. "Since that electron is one that would have formed a bond, so it would have gone into a bonding orbital, then that empty state is going to be in the valence band." $E_F$ is "down close to the valence band because that corresponds to having a higher probability of finding empty states in the valence band." Result: "a higher concentration of holes than we have of electrons." [0:53:15]

> [!warning] Board slip, 0:52:52 (f_0435/f_0436)
> On the p-type $f(E)$ plot, the Fermi-level label reads **"E_E"** (?) at full zoom. The subscript looks like an E, not an F. He says "This is the Fermi level." It is $E_F$.

### 12. Student question: is the Fermi level physical or just a definition? [0:53:23–0:55:10]
- "Partly, it's defined mathematically… the energy at which the probability of a state being occupied by an electron is one half… In that sense, it's sort of arbitrary… one half is kind of the least arbitrary point that we could pick." [0:53:41–0:54:12]
- "It is actually physically significant… if we… bring them together to form what's called a pn junction, then what has to happen is that **the Fermi level has to be the same in equilibrium. It has to be the same across that entire structure.**" [0:54:15–0:54:47] "A quantity that has to be preserved in equilibrium across an entire structure for two systems that are in equilibrium with each other." [0:54:52]

### 13. Acceptors named; hole motion; n-type and p-type [0:55:10–0:57:25]
Board (f_0449, f_0453):
- **"Impurity atoms that remove electrons (provide holes) are called <u>acceptors</u>."**
- **"donors ⇒ n-type semiconductor ($n>p$)"**
- **"acceptors ⇒ p-type semiconductor ($p>n$)"**

**How holes move** [0:55:52–0:56:20]: "If you have an empty state over here, there's some probability that this electron [in a neighbouring bond] could move over here. And then… maybe an electron over here can move into the resulting empty state, and that's basically how the holes move around in the valence band." (Spoken only; no arrows drawn.)

"We'll use these terms pretty frequently as we move forward." [0:57:08]

### 14. How much doping is typical? [0:57:25–1:00:19]
Board (f_0483/f_0485): **"The fraction of atoms replaced by impurities is typically very small, e.g., a crystal of Si has ~$5\times10^{22}$ Si atoms/cm³, and typical concentrations of impurities introduced in doping are ~$10^{15}$–$10^{20}$ atoms/cm³."**
- Spoken: "roughly one in 500 or so at the high end to one in, you know, 10 to the seventh or 10 to the eighth at the low end… Even at the high end, it's a relatively small fraction." [1:00:08]

> [!check] Verified (python3)
> $10^{20}/(5\times10^{22})=2\times10^{-3}$, or 1 in 500 ✓. $10^{15}/(5\times10^{22})=2\times10^{-8}$, or 1 in $5\times10^7$, which lies between his "$10^7$ or $10^8$" ✓.

### 15. Student question: is there an optimum doping level? Mobility vs. carriers [1:00:19–1:04:40]
The question: with no impurities you get little current, and you can't make every atom an impurity, so where is the optimum? [1:00:26] His answer:
- **Effect 1, more carriers.** If that were all, you would maximize conductivity by adding impurities "until it starts looking not like silicon with some isolated impurities, but like an alloy… once you get to… a significant fraction of 1% or higher." [1:00:55–1:01:49]
- **Effect 2, scattering.** "When… a donor gives up its electron to the conduction band, it leaves behind a positively charged ion that's sort of bonded into the lattice." Coulomb attraction disrupts electron motion: "that influence is called scattering." Think of the electron as a ball that bounces off charged impurities. [1:01:50–1:03:04]
- **Trade-off:** more donors mean more electrons, which "increases the conductivity," but also more scattering, which "reduces the conductivity." "It turns out that [the] decrease in mobility is somewhat smaller than the increase in electron concentration. So if you really want high conductivity, you still wanna have as high an electron concentration as possible." But other device characteristics "depend very heavily on how easily the electrons can move… what's called the mobility," so "what is optimum depends on the specifics of that application." [1:03:09–1:04:36] (ASR writes "connectivity" for conductivity.)

### 16. Semiconductor devices: the pn junction diode [1:04:40–1:07:28]
Board (f_0515/f_0516): **"Semiconductor devices"** and **"pn junction diode:"**
- 302/302H looked at MOSFETs. "What we're gonna do here is to look in more detail at… the PN junction diode." [1:05:13]
- **Figure:** the diode symbol o—▷|—o (triangle pointing right, bar on the right), then "=", then a bar split by a vertical line with **p on the left, n on the right**. The boundary is labelled **"pn junction"**. So the triangle side (anode) is p and the bar side (cathode) is n.
- "The boundary region between these is what we call the PN junction… or this structure overall is often also called the PN junction." [1:06:07–1:06:19]
- **Before contact (same figure):** a dashed vertical line drops from the junction. On the p side, $E_c$, $E_v$ with holes "o o o o", and **$E_F$ dashed just above $E_v$**. On the n side, $E_c$ and $E_v$ at the **same heights** as on the p side, with electrons "• • • •" above $E_c$ and **$E_F$ dashed just below $E_c$** (added at 1:07:11). [1:06:33–1:07:23]

### 17. Contact, diffusion, and the equilibrium condition [1:07:28–1:10:09]
- On contact, "you have lots of electrons over here on the n side… very few over here on the p side… just by diffusion… the concentrations will try to even out." Electrons diffuse n→p and holes diffuse p→n. [1:07:35–1:08:18]
- **The final state:** "one in which the Fermi level, the probability of finding an electron or a hole at a given energy, is the same in equilibrium across the entire structure. Because if it were not the same, then you would get some motion of the electrons or the holes across the junction." [1:08:46–1:09:07]
- Board (f_0517/f_0523): **"In equilibrium, $E_F$ must be constant across the entire device ⇒ $I=0$."** Spoken: "that's required in order for the current to be zero… in equilibrium… zero voltage. We also require that we have zero current." [1:09:14–1:09:44]

### 18. Equilibrium band diagram and the built-in potential [1:10:09–1:13:10]
**Figure (f_0526/f_0539): band-edge energy vs. position $x$. Redraw as follows.**
1. Draw $E_F$ first, as a flat dashed horizontal line across the whole width, with an axis arrow "→ x".
2. **Far left (p side):** it "has to look like a p-type semiconductor." $E_v$ sits just below $E_F$ with holes "o o o o" under it, and $E_c$ sits a band gap above $E_v$. Both are flat.
3. **Far right (n side):** it looks like n-type. $E_c$ sits just above $E_F$ with electrons "• • • •" on it, and $E_v$ sits a band gap below. Both are flat.
4. **Connect them:** "these two have to connect with each other." Both $E_c$ and $E_v$ bend down smoothly (an S-shaped step) through the junction region, staying parallel, so the band gap is constant.
5. Extend the p-side $E_c$ level to the right as a dotted line. A vertical double arrow from the n-side $E_c$ up to that dotted line is labelled **$eV_{bi}$**.

Board: **"$V_{bi}$ = 'built-in' potential."**

"One of the things that happens that's very fundamental to the behavior of a PN junction diode is that you build up a potential energy difference between the p side and the n side… electronic charge $e$ times a potential we call $V_{bi}$." [1:11:11–1:11:41]

**Where $V_{bi}$ comes from** [1:11:53–1:13:08]:
1. As electrons diffuse to the p side and holes to the n side, "a bunch of the electrons will drop down to lower energy and fill these hole states."
2. "What you will have left are the ionized dopants… acceptors on the p side, donors on the n side," which "will have charge associated with them."
3. "That charge will give rise to an electric field," and "the integral of that electric field will give you a potential."
4. "That potential difference basically prevents more diffusion from occurring." In equilibrium the barrier keeps the holes on the p side and the electrons on the n side.

> [!warning] Speech/ASR slip, 1:12:56
> The transcript reads "keep this high concentration of holes on the inside and the high concentration of electrons on the p side." **That is reversed.** The barrier keeps **holes on the p side** and **electrons on the n side**, as his own diagram shows (holes drawn under p-side $E_v$, electrons over n-side $E_c$). "Inside" is probably ASR for "n side", but the sentence as transcribed is wrong. Also at 1:11:58, "holes are diffusing over the inside" is ASR for "over to the n side".

### 19. Student question: $V_{bi}$ vs. breakdown; forward-bias preview [1:13:10–1:16:02]
- **Question:** is $V_{bi}$ related to when the diode breaks down? [1:13:10]
- **Answer:** "It's not so much related to… the breakdown voltage… which is when you apply reverse bias… negative voltage to the p side. **What it relates to instead is the voltage at which the diode turns on under forward bias.**" [1:13:18–1:13:43]
- **Forward bias:** "positive voltage [to] the p side, negative voltage [to] the n side." For a given material "the current, as we will see in detail later, will increase exponentially as you start applying positive voltage to the p side. That's the turn on of the diode." On a curve tracer the I–V rises exponentially, with "a characteristic voltage at which it looks like it's turning on." He seems to have gestured the I–V shape; no curve is on the paper (?). [1:13:54–1:14:43]
- **Mechanism (preview of next lecture):** "as you apply positive voltage to the p side… positive voltage decreases the potential energy for electrons… this barrier will get lower." The turn-on happens **not** when $V_{bi}$ is fully cancelled but "getting within maybe a couple tenths of a volt or something like that." Then "the current due now to the diffusion of electrons that can now diffuse across the junction because the barrier is lower… will start becoming very noticeable, and that's the turn on voltage." [1:15:04–1:15:50]
- **"For a silicon PN junction diode, the turn on, you know, very roughly is maybe around point six volts or so."** [1:15:42–1:16:00]
- The transcript ends mid-sentence here ("And it is that…", 1:16:02).

### 20. Board-only tail (audio gap) [1:16:02–1:19:43]
> [!warning] Audio gap
> No speech was transcribed from 1:16:02 to the end of the recording (~1:19:43). At 1:16:39–~1:17:00 Zoom shows a participant's name tile instead of the board. The board kept changing, so he was still lecturing. Content below is **board only**.

- Frames f_0576–f_0588 (1:17:01–1:18:20): the equilibrium band diagram, unchanged. He points at the p-side $E_c$ and at the $E_v$ bend.
- Board (f_0592/f_0593, 1:18:46–1:19:12), written under "$V_{bi}$ = built-in potential":
  - **"$E_c(x)$ functions as the potential energy for electrons"**
  - **"$E_v(x)$ functions as the potential energy for hol[es]"** (still being written in the last frame)

> [!note] Added context (an interpretation of those two lines, not his words)
> Electrons tend toward lower $E_c$, so the n side (low $E_c$) holds them and the step $eV_{bi}$ is a hill for electrons going n→p. Holes tend toward *higher* $E_v$ (hole energy increases downward on an electron-energy diagram), so the p side holds them. This is the same barrier picture as §18. Check it against the next lecture.

### Not covered in this lecture
The following were **not** stated in this lecture: an explicit formula for $n$ or $p$ in terms of $E_c-E_F$ or $N_c$/$N_v$; $n_i$ and the mass-action law $np=n_i^2$; compensation; the depletion-region width and charge; the Shockley diode equation $I=I_s(e^{V/V_T}-1)$ with $V_T=k_BT/e$ (=25.9 mV at 300 K); reverse saturation current; and the I–V curve (verbal only). PS6 (semiconductors, graded, solutions posted), today's recitation, and the next lecture (2026-10-14) are the places to look.

**DO-NOT-SOLVE check:** this lecture contains no PS8 problem (9.26, 9.38, 9.39, 9.42, m9.2, 12.2a–c) and no Lab 5 circuit. It is all semiconductor physics. No graded-work warning applies.

---

## Ed Yu's conventions & notation

| Item | His convention (this lecture) |
|---|---|
| Occupation function | **"Fermi distribution function"** $f(E)$. He never said "Fermi–Dirac". $f(E)=1/(e^{(E-E_F)/k_BT}+1)$, always written with the "+1" last in the denominator. |
| Fermi level | $E_F$, "Fermi energy or Fermi level", **defined as the energy where $f=\tfrac12$**. |
| Boltzmann constant | $k_B$ (subscript B): $1.381\times10^{-23}$ J/K $=8.617\times10^{-5}$ eV/K. Room temperature is **300 K**, where $k_BT=0.0259$ eV ("about 1/40 eV"). |
| Charge | $e$ = **magnitude** of the electron charge, $1.602\times10^{-19}$ C (positive). The energy step is written $eV_{bi}$. |
| Energy unit | **eV**, "lowercase e, uppercase V". 1 eV $=1.602\times10^{-19}$ J. |
| Band edges | $E_c$, "conduction band edge energy"; $E_v$, "valence band edge energy". Band gap $E_g=E_c-E_v$ (Si ≈ 1.1 eV at RT). Bands labelled "CB"/"VB" with braces. |
| Plot orientation | **Energy on the vertical axis**, $f(E)$ on the horizontal axis (0 to 1), drawn beside the band diagram at the same energy scale. DOS is drawn the same way (horizontal axis "DOS", dashed). |
| Carriers in sketches | Electrons are filled dots **•** just above $E_c$. Holes are open circles **o** just below $E_v$. The filled VB is hatched. $E_F$ is a dashed line. |
| Bond picture | Element symbols in circles. Each bond is an oval with two dots. An extra electron is a loose dot; a missing electron is an open circle in a bond. |
| Concentrations | $n$ (electrons), $p$ (holes), atom densities in **cm⁻³** ("atoms/cm³"). |
| Doping words | "impurity atoms", "dopants", "ionized dopants", "**donors**" (provide electrons; group V: P, As), "**acceptors**" (remove electrons, provide holes; group III: B, Al), "**n-type** ($n>p$)", "**p-type** ($p>n$)". |
| pn junction | "pn junction diode". p on the **left**, n on the **right**; position axis "→ x". Diode symbol: triangle = p (anode), bar = n (cathode). |
| Built-in potential | $V_{bi}$, "built-in" potential, in volts. On the band diagram the step is $eV_{bi}$ (energy). |
| Bias words | Forward bias = "positive voltage to the p side". Reverse bias = "negative voltage to the p side". |
| Prerequisite naming | "302 or 302H" (where MOSFETs were covered). |

---

## Intuition & explanations he gives

- **Why $f\to0$ and $f\to1$:** for $E\gg E_F$, "a large exponential in the denominator… the probability of finding an electron at a very high energy state is extremely small." For $E\ll E_F$, "states at very low energy are very likely to be occupied by electrons." [0:08:08–0:08:56]
- **Width of the transition:** "the range of energies over which the Fermi distribution function is… significantly different from zero or one, is just within a few times $k_BT$ of the Fermi level." [0:09:39–0:10:02]
- **Temperature:** "as the temperature increases, that transition… will occur over a wider range of energies." [0:10:29] At high T, "the slope going this way will get more shallow," which makes CB occupation more probable. [0:13:41–0:14:21]
- **Intrinsic $E_F$:** "the Fermi level is near the middle of the band gap, which has to be the case because the concentration of electrons and holes have to be equal to each other." [0:12:16]
- **Probability ≠ states:** $f$ "only tells us what is the probability that a state at a given energy will be occupied by an electron. It does not imply anything about whether there are states at that energy or not." [0:15:36]
- **DOS × $f$:** the DOS ("how many states there are") times $f$ ("what's the probability that the states will be occupied") "will then tell you how many electrons do you have at that energy," integrated over the band to give the concentration. [0:18:12–0:18:42]
- **DOS continuity:** it is discrete in a finite crystal, but the levels are "extremely close together," so we treat it as "a continuous function but not necessarily differentiable." [0:19:30–0:20:00]
- **Why eV:** it is the natural unit because "the potential energy of an electron at a particular… voltage is the charge of the electron times the voltage," so "the amount of energy that it takes to change the potential of an electron… by one volt" is a natural unit. It is "somewhat coincidentally" convenient too, since band gaps are about 1 eV. [0:23:05–0:23:47, 0:28:50]
- **$k_B$'s role:** "Boltzmann's constant really converts temperature into energy." [0:25:56]
- **Why a pure semiconductor barely conducts:** $E_g$ "is 40 times" $k_BT$, so $n$ and $p$ are "down by a factor of… roughly $e^{-20}$." [0:29:30–0:30:05]
- **Can't raise both:** "we can get either many more electrons or many more holes, but, at a given temperature, we can't get both." [0:33:12]
- **Donor mechanism:** the dopant's "bonding states are already filled… the only place that [the extra electron] can go is into the antibonding orbital or, equivalently, the conduction band." [0:40:54–0:41:08]
- **Donors also kill holes:** extra electrons "would like to lower their energy so they'll go and fill… the empty states in the valence band." [0:42:37–0:42:50]
- **Acceptor mechanism:** the missing electron "would have gone into a bonding orbital, then that empty state is going to be in the valence band." [0:51:53–0:52:04]
- **Hole motion:** a neighbouring bonding electron hops into the empty state, then the next one hops into the newly emptied state: "that's basically how the holes move around in the valence band." [0:56:04–0:56:20]
- **One extra, not two:** after the first electron leaves, "what you have left is a positively charged ion… That makes it harder to get that second electron off." [0:47:35–0:47:56]
- **Dopant size:** a "big atom… into a space where there was previously a small atom… produces some distortion of the lattice… that affects the electronic states." [0:46:13–0:46:35]
- **Mobility trade-off:** ionized dopants are fixed charges, and the Coulomb pull makes electrons "bounce off" them ("scattering"). "Decrease in mobility is somewhat smaller than the increase in electron concentration," but mobility matters for other device characteristics. [1:02:04–1:04:33]
- **Why $E_F$ is flat in equilibrium:** "if it were not the same, then you would get some motion of the electrons or the holes across the junction." Constant $E_F$ is "required in order for the current to be zero." [1:08:57–1:09:38]
- **Why diffusion stops:** ionized dopants leave charge, giving a field and then a potential; "that potential difference basically prevents more diffusion from occurring." [1:12:16–1:12:56]
- **Forward-bias turn-on:** "positive voltage decreases the potential energy for electrons… this barrier will get lower." Current gets "very noticeable" once within "a couple tenths of a volt" of cancelling $V_{bi}$. [1:15:11–1:15:50]
- **Physical meaning of $E_F$:** "a quantity that has to be preserved in equilibrium across an entire structure for two systems that are in equilibrium with each other." [0:54:52–0:55:03]

---

## Emphasis & exam intel

2. **PS6 flag** [0:02:54]: "This week's recitation is important, because it will cover material that will be important for you to do problem set six." The board adds "(!)".
3. **Probability vs. states** [0:15:36]: "It does not imply anything about whether there are states at that energy or not."
4. **"Few $k_BT$" width** [0:09:51]: "just within a few times $k_BT$ of the Fermi level."
5. **Numbers he wrote down** [0:20:58–0:29:23]: 300 K, $k_BT=0.0259$ eV, $k_B=8.617\times10^{-5}$ eV/K, 1 eV $=1.602\times10^{-19}$ J, $E_g(\text{Si})\approx1.1$ eV.
6. **"Can't get both"** [0:33:12]: "we can get either many more electrons or many more holes, but, at a given temperature, we can't get both."
7. **Donor naming** [0:44:13]: donors are "essentially donating one of their valence electrons to the conduction band."
8. **"One more or one fewer… is what works best"** [0:47:56].
9. **Terms for later** [0:57:08]: n-type and p-type: "we'll use these terms pretty frequently as we move forward."
10. **$E_F$ constant** [0:54:40, 1:09:14]: "the Fermi level has to be the same in equilibrium. It has to be the same across that entire structure." Board: "$E_F$ must be constant across the entire device ⇒ $I=0$."
11. **"Very fundamental"** [1:11:11]: the built-in potential difference "is very fundamental to the behavior of a PN junction diode."
12. **$V_{bi}$ ≠ breakdown** [1:13:31]: "What it relates to instead is the voltage at which the diode turns on under forward bias."
13. **Si turn-on** [1:15:54]: "very roughly is maybe around point six volts or so."
14. **Preview** [1:15:04]: "a little preview of… what we'll talk about next time," i.e. the biased junction and exponential current, "as we will see in detail later" [1:14:12].
15. **Exam 1 logistics carry-over:** grades are curved and rubrics are applied uniformly [0:02:11]. Exam 1 mean 71.3, median 74.5, SD 12.8, N = 25.

---

## Student questions

| t | Question (reconstructed) | His answer |
|---|---|---|
| 0:15:24 | The band diagram has a gap where electrons can't be, yet $f(E)$ is nonzero there. How do these fit together? | $f$ is only the occupation probability *if a state exists*. With no states in the gap, there are no electrons there. |
| 0:16:24 | (Fragmentary) So you could draw the graph for each thin energy slice, and at $E_c$ it differs from $E_c+0.1$? (?) | Deferred to today's recitation (Darsh), which covers the density of states. He then sketched the DOS. |
| 0:18:42 | Is the DOS continuous, or many discrete sub-levels? | Continuous for an infinite crystal. A finite crystal has discrete levels "extremely close together", so treat it as continuous but not necessarily differentiable (cusp at the band edge). |
| 0:44:52 | Why phosphorus vs. arsenic (why one element versus another)? | Both work well and both are common. Much bigger atoms (farther down the periodic table) distort the lattice; size mismatch causes issues going up too. |
| 0:53:23 | Does the Fermi level ("the one half mark") have physical meaning, or is it just a mathematical construct? (ASR first says "the hole".) | Partly a definition (½ is "the least arbitrary" choice), but physically $E_F$ must be equal throughout a structure in equilibrium, e.g. across a pn junction. |
| 1:00:26 | With no dopants there's little current, and you can't make every atom a dopant. Where's the optimum? | More dopants mean more carriers, up to the alloy regime (~a fraction of 1 %), but ionized-impurity scattering lowers mobility. The conductivity still rises because the mobility loss is smaller, but the device optimum depends on the application. |
| 1:13:10 | Is $V_{bi}$ related to when the diode breaks down (reverse direction)? | No. Breakdown is a reverse-bias effect (negative voltage on p). $V_{bi}$ relates to the forward-bias turn-on voltage. |
| 1:14:43 | So diffusion builds an opposing potential, and applying positive voltage cancels $V_{bi}$ past a threshold? | "That's basically right." Forward bias lowers the barrier, current becomes noticeable within a couple tenths of a volt of cancelling $V_{bi}$, and Si turns on at ≈ 0.6 V. |

---

## Exam relevance

**P1 (four conceptual short answers on filter concepts and semiconductor physics): HIGH.** This lecture is the main source for the semiconductor half of P1. Likely stems, with answers built from his own reasoning:
- *"Sketch $f(E)$ at low and high T next to the band diagram of a pure semiconductor and explain."* Draw $E$ vertical, $f$ from 0 to 1, crossing ½ at $E_F$ (mid-gap). The transition width is a few $k_BT$ and broadens with T. Low T: VB full, CB empty. High T: some CB electrons and VB holes.
- *"What is the Fermi level?"* It is the energy where $f=\tfrac12$. Physically, it is constant throughout a structure in equilibrium.
- *"Why is $n$ tiny in pure Si at 300 K?"* $E_g\approx1.1$ eV $\approx42\,k_BT$ and $E_F$ is mid-gap, so $f(E_c)\sim e^{-21}$.
- *"$f(E)$ is nonzero in the gap. Are there electrons there?"* No. The DOS is zero in the gap, and $n(E)=\mathrm{DOS}\times f$.
- *"Explain how P or As makes Si n-type."* Use both pictures: the bond picture (5th electron, bonding states full, so it goes to an antibonding state, i.e. the CB) and the band picture with $f(E)$ ($E_F$ near $E_c$; holes also decrease).
- *"Explain how B or Al makes Si p-type and how holes move."* The missing bonding electron is an empty VB state. Neighbouring electrons hop in, and the hole moves. $E_F$ sits near $E_v$.
- *"Can doping increase both $n$ and $p$?"* No. Shifting $E_F$ toward one band moves it away from the other. ($np=n_i^2$ is the added-context version.)
- *"Why not use a 6-valence dopant?"* The positive ion left after the first ionization binds the second electron more tightly.
- *"Why is $E_F$ flat across a pn junction in equilibrium, and what is $V_{bi}$?"* A non-flat $E_F$ would drive a net current, and equilibrium means zero current. Diffusion leaves ionized dopants, giving charge, a field, and the potential $V_{bi}$, which stops further diffusion. Draw the band diagram with $eV_{bi}$.
- *"What does forward bias do?"* + on p lowers the barrier, and the diffusion current rises exponentially. Turn-on is ≈ 0.6 V in Si, slightly below $V_{bi}$. $V_{bi}$ is not the breakdown voltage.
- *"Trade-off in choosing doping level?"* Carrier density against mobility (ionized-impurity scattering).
- *Short numerics:* $k_BT$ at a given T in eV; $f$ at $E-E_F=m\,k_BT$; the dopant fraction $N/(5\times10^{22})$.

**P2 (passive filter design / max power transfer): none.** **P3 (filter transfer function, cutoff, Bode): none.** **P4 (op-amp or RLC filter): none.** Nothing in this lecture touches circuits beyond the diode symbol.

**Feeds:** P1 only (semiconductor sub-questions). Pair it with the 2026-10-05 lecture (crystal bonding, bands, holes; referenced as "last class before the exam") and the 2026-10-14 lecture (biased junction, continued) for complete P1 coverage.

---

## Common mistakes / traps

- **Calling $f(E)$ "the number of electrons."** It is a probability per state. The number of electrons needs DOS × $f$. A nonzero $f$ in the gap does not mean electrons are there.
- **Flipping the $f(E)$ sketch.** With $E$ vertical, $f\to1$ at the **bottom** (low $E$) and $f\to0$ at the **top**. It crosses ½ exactly at $E_F$ (his sketches drift toward ~0.4; don't copy that).
- **Moving $E_F$ with temperature in the intrinsic sketch.** He keeps $E_F$ at the same energy and only widens the transition.
- **Unit slips:** $k_BT=0.0259$ **eV** $=4.14\times10^{-21}$ **J**. (He misspoke "4×10⁻²⁰" J.) $k_B$ is $1.381\times10^{-23}$ J/K or $8.617\times10^{-5}$ eV/K; don't mix the two.
- **Swapping donor/acceptor or n/p.** Group V (P, As, 5 valence electrons) are donors, giving n-type with $E_F$ near $E_c$. Group III (B, Al, 3 valence electrons) are acceptors, giving p-type with $E_F$ near $E_v$.
- **Thinking holes are in the CB, or are "positive electrons."** He defines a hole as an **empty state in the VB**.
- **Claiming doping raises both $n$ and $p$.** It raises one and lowers the other.
- **Thinking "more dopant is always better."** Ionized-impurity scattering lowers mobility.
- **Drawing $E_F$ bent and the bands flat.** In equilibrium it is the reverse: **$E_F$ is flat** and the bands bend. The p side sits higher (for electrons) by $eV_{bi}$.
- **Confusing $V_{bi}$ (volts) with $eV_{bi}$ (energy)** on the band diagram.
- **Attributing $V_{bi}$ to breakdown.** Breakdown is a reverse-bias effect. $V_{bi}$ governs forward turn-on.
- **Saying the diode turns on only when $V_{bi}$ is fully cancelled.** He says turn-on happens "within a couple tenths of a volt" of that point (≈ 0.6 V for Si).
- **Reversing which carriers stay where** (the 1:12:56 slip). Holes stay on the p side and electrons on the n side.
- **Diode symbol orientation:** the triangle (anode) is the p side and the bar (cathode) is the n side. Forward bias is + on the triangle side.

---

## Self-check

**Q1.** At $T=300$ K, using $k_B=1.381\times10^{-23}$ J/K and $1\ \text{eV}=1.602\times10^{-19}$ J, find $k_BT$ in J and in eV. How many $k_BT$ is the Si band gap (1.1 eV)?

> [!question]- Answer
> $k_BT=1.381\times10^{-23}\times300=4.14\times10^{-21}$ J. Then $4.14\times10^{-21}/1.602\times10^{-19}=0.0259$ eV. $E_g/k_BT=1.1/0.0259=42.5$, which matches his "about 40 times". (python3 verified.)

**Q2.** Evaluate $f(E)$ at $E=E_F+3k_BT$ and at $E=E_F-3k_BT$. What energy, in eV at 300 K, is $3k_BT$? What does this say about the "few $k_BT$" width?

> [!question]- Answer
> $f(E_F+3k_BT)=1/(e^{3}+1)=0.0474$ and $f(E_F-3k_BT)=1/(e^{-3}+1)=0.953$. The two sum to 1 by symmetry. $3k_BT=0.0776$ eV. So within about ±3 $k_BT$ (≈ ±0.08 eV) of $E_F$, $f$ moves from about 95 % to about 5 %. This is his "few $k_BT$" transition; the 10–90 % width is $2\ln9\,k_BT=4.4\,k_BT$. (python3 verified.)

**Q3.** Si is doped with $10^{17}$ arsenic atoms/cm³. What fraction of Si atoms is replaced? Is the material n- or p-type, and where is $E_F$ relative to $E_c$ and $E_v$? What happens to the hole concentration compared with pure Si?

> [!question]- Answer
> The fraction is $10^{17}/(5\times10^{22})=2\times10^{-6}$, or 1 in $5\times10^5$ (python3), well inside his 1-in-500 to 1-in-$\sim10^8$ range. As has 5 valence electrons, so it is a **donor** and the material is **n-type**. $E_F$ is **closer to $E_c$ than to $E_v$**. Holes **decrease**: the extra electrons fill empty VB states, and $E_F$ has moved away from $E_v$ ("can't get both").

**Q4.** (Conceptual, P1 style) Explain why the Fermi level must be constant across a pn junction in equilibrium, and explain what creates the built-in potential and why diffusion stops.

> [!question]- Answer
> A difference in $E_F$ means a difference in the probability of finding electrons or holes at a given energy across the junction, which would drive carrier motion (a net current). Equilibrium requires zero current, so $E_F$ must be flat across the whole device. On contact, electrons diffuse n→p and holes p→n, and they recombine (electrons drop into hole states). This leaves **ionized dopants**: negative acceptors on the p side and positive donors on the n side. That fixed charge creates an **electric field**, and the integral of the field is the **built-in potential $V_{bi}$**. On the band diagram the p side sits $eV_{bi}$ higher, a barrier that "prevents more diffusion from occurring". (Lecture 1:08:46–1:13:08.)

**Q5.** (Conceptual) A classmate says: "The built-in potential is the breakdown voltage, and the diode turns on only when the applied forward voltage equals $V_{bi}$." Correct both claims.

> [!question]- Answer
> First, breakdown is a **reverse-bias** effect (negative voltage on the p side); $V_{bi}$ instead sets the **forward-bias turn-on**. Second, forward bias (+ on p) lowers the electron barrier, and the diffusion current rises exponentially. It becomes noticeable once the barrier is within "a couple tenths of a volt" of being cancelled, before $V_{bi}$ is fully cancelled. Si turns on at roughly 0.6 V. (Lecture 1:13:18–1:16:00.)

---

> [!summary] Board-error and discrepancy audit
> - **Speech, 0:21:40:** "$k_BT$… maybe four times 10⁻²⁰ J". The correct value is $4.14\times10^{-21}$ J (10× off). The board's eV result, 0.0259 eV, is correct.
> - **Board, 0:26:37:** $k_B=8.617\times10^{-5}$ eV/K is the CODATA value. His own rounded constants give $8.620\times10^{-5}$. Both round to the same 3 s.f.
> - **Board, 0:52:52:** the Fermi level on the p-type $f(E)$ plot is labelled "E_E" (?). It should be $E_F$, per speech.
> - **Speech/ASR, 1:12:56:** "holes on the inside… electrons on the p side" is reversed. Holes stay on p and electrons on n, per his diagram.
> - **Sketches, 0:09–0:14:** $f$ crosses $E_F$ at about 0.4 on the hand sketches. The definition says ½.
> - **All other numbers verified** (python3): $k_BT=0.0259$ eV ✓; $E_g/k_BT=42.5$ ("40") ✓; $e^{-E_g/2k_BT}=5.8\times10^{-10}$ ("$e^{-20}$") ✓; 1 in 500 and 1 in $5\times10^7$ dopant fractions ✓; 10/14 is a Wednesday and 10/16 a Friday ✓.
> - **ASR fixes:** "case of b" → $k_B$; "f of v" → $f(E)$; "k sub e times c" → $k_BT$; "connectivity" → conductivity; "Ohlins band" → valence band; "dope and type" → dopant type; "purity atoms" → impurity atoms; "two few" → too few; "whole state" → hole state; "VDI" / "b b I" → $V_{bi}$; "die breaks" → diode breakdown; "connection and valence bands" → conduction and valence bands.
> - **Audio gap:** 1:16:02–1:19:43, board only.
