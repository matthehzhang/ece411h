---
course: ECE 411H
date: 2026-10-05
instructor: Prof. Ed Yu
topic: Opening Q&A on complex power; semiconductor properties; Si covalent bonding; electronic states from isolated atom to crystal (energy bands, E_c, E_v, band gap); electrons and holes at T = 0 K vs T > 0 K; band formation vs atomic separation; why a filled band carries no current; Fermi distribution function; n = p and E_F near midgap in a pure, perfect semiconductor
reading: none named in this lecture
source: Recordings/2026-10-05-semiconductors-and-solid-state-devices (transcript + 19 distinct tablet pages from 66 page-final frames; 10 pages carry content, p04 is black, p11-p18 are scroll duplicates of p10; descriptions in frames/pages_described.md)
tags: [ece411, lecture, semiconductors, band-structure, electrons-holes, fermi-distribution, complex-power, exam2]
source_quality:
  - "ASR Deepgram Nova-3, 78.5 min, 9164 words, mean utterance confidence 0.96; 82 words < 0.55 (0.9 %); 13 utterances < 0.7"
  - "Low-confidence spans: 0:02:27, 0:05:30, 0:06:45-0:06:51, 0:09:17, 0:20:19, 0:26:20, 0:38:36-0:38:46, 0:40:54, 0:51:37, 1:11:53. All are fillers or off-mic student questions; none carries a formula or number"
  - "Doc-cam: none (OneNote tablet over Zoom). QUALITY.md blur flag on f_0033 (0:18:06) is really a black frame: the Zoom share dropped 0:18:06-0:18:51; audio is continuous"
  - "3-D Si crystal picture discussed 0:23:41-0:25:01 appears in no frame (speech only)"
  - "p11-p18 (1:12:51-1:13:03) are accidental-scroll duplicates of p10; no content lost"
  - "Audio gaps: none. Student questions are off-mic and fragmentary"
---

# 2026-10-05: Semiconductor Properties, Energy Bands, Electrons & Holes, Fermi Distribution

## Summary

- **Why semiconductors matter.** Their conductivity sits between insulators and metals. More importantly, it **can be controlled over many orders of magnitude**: by impurities (doping, fixed at fabrication) or by an applied voltage (during operation).
- **Si bonding.** Si has 14 electrons and **4 valence electrons**. Each valence electron is shared with a neighbour in a covalent bond, so every atom has **4 nearest neighbours**. Draw it as a 2-D square array; in 3-D the neighbours form a tetrahedron.
- **Isolated atom vs crystal.**
  - Atom: discrete orbitals 1s²2s²2p⁶3s²3p². Closed shells are 1s/2s/2p; the valence electrons are 3s²3p².
  - Crystal: **bands**. The valence band (VB) is lower and the conduction band (CB) higher, with **no states in the band gap** of a pure, perfect crystal.
  - Definitions: **$E_v$ = VB maximum, $E_c$ = CB minimum, $E_g=E_c-E_v$.**
- **Band formation vs separation $a$** (sketch it). For $N$ atoms, the 3s levels ($2N$ states) and 3p levels ($6N$ states) broaden, merge, then split again into a VB (bonding orbitals, **$4N$ states**) and a CB (antibonding orbitals, **$4N$ states**). The **$4N$ valence electrons exactly fill the VB at 0 K.**
- **T = 0 K:** VB full, CB empty. **T > 0 K:** a few electrons are thermally excited into the CB, leaving empty VB states. **"Electrons"** means negative carriers in the CB. **"Holes"** means missing VB electrons, which behave like positive carriers (the bubble analogy).
- **Only partially filled bands carry current.** In a full band every electron has a counterpart moving the opposite way, so the motions cancel. That is why we track the few *empty* VB states (holes) instead of the many VB electrons. Most electrons are in the VB, but that does **not** mean the VB carries most of the current.
- **Fermi distribution function**, the probability that a state at energy $E$ is occupied: $f(E)=1/\left(e^{(E-E_F)/k_BT}+1\right)$, with $k_B=1.381\times10^{-23}$ J/K and $T$ in K. **$E_F$ is the energy where $f=\tfrac12$.** You must be able to state the limits ($f\to1$ well below $E_F$, $f\to0$ well above) and evaluate $f$ numerically.
- **Pure, perfect semiconductor:** $n=p$, because each CB electron leaves a VB hole. Therefore **$E_F$ is near (not exactly at) the middle of the gap.** Doping breaks the $n=p$ link: an impurity can pull electrons out of the VB without putting any into the CB.
- (P2 side, Q&A) **Complex power:** $S=\tfrac12\tilde V\tilde I^*=I_{rms}^2Z_L$. $\mathrm{Re}\,S$ is the average power. $\mathrm{Im}\,S$ is the reactive power, the peak of the zero-average exchange. Pick whichever form you are closest to.

---

## Content

### 0. Announcements [0:00:13–0:04:43]
Typed board, p01 (f_0006/f_0009):
- **Problem Set 5** was due at 9:00 AM CDT today. Solutions come out later today. Grading "probably won't be completed before the exam."
- **Semester Exam 1** is Wed 10/07/2026, in class. Use the dummy template to practise scanning and uploading. **Bring a printed physical copy of the answer-sheet template.**
- Today's recitation is an **exam review** with Darsh (the TA), possibly working old exams from "Exam Preparation Materials."
- **Problem Set 6 was released today, due Wed 10/21/2026, and "covers maximum power transfer and semiconductors."** Spoken [0:02:08]: not on SE1, but "you will be responsible for it for the second exam and the final."
- Answer-sheet upload [0:02:33–0:03:18]: scan to PDF rather than photographing. Photos are lower resolution and the paper comes out gray.
- Past exams [0:03:23–0:04:26]: Canvas has **three years of past exams for SE1, SE2 and the final**, with short numerical or symbolic answers and a **score histogram** for each. They are "probably the best guide... But there are never any guarantees."
- Calculator [0:04:31]: anything without communication or photo capability. A graphing calculator is fine; a phone is not.

### 1. Q&A: complex power [0:04:51–0:08:32]
No board writing. This is PS5/SE1 material, but it feeds Exam 2's max-power-transfer problem (PS6).

- **Why Re is average power** [0:05:07]: many products of $\tilde V$ and $\tilde I$ could be defined. Complex power "we chose... to have the property... that when we take the real part, it would give us the average power."
- **Im part** [0:05:49–0:06:36]: it "corresponds to the peak power that... is exchanged between the source and the load." A nonzero imaginary part requires $v$ and $i$ out of phase, which needs "an imaginary component to the impedance of the load."
- **Which formula to use** [0:06:38–0:08:32]: student asked about $\tfrac12\tilde V\tilde I^*$ vs $I_{rms}^2Z_L$. "No hard and fast rule." They give the same result.
  - If you already have the current and voltage, $\tfrac12\tilde V\tilde I^*$ is probably easier.
  - If the load impedance is easy to get or already known, use $I_{rms}^2Z_L$.
  - If "the load circuit is kind of a big mess", use $\tfrac12\tilde V\tilde I^*$.
  - Use whichever you are "closer to."

> [!warning] Imprecise spoken statement [0:06:04]
> As transcribed: "in order to have power transfer, you need the current and the voltage to be out of phase." That is **false for average (real) power**. $P=\tfrac12|V||I|\cos(\theta_v-\theta_i)$ is largest when $v$ and $i$ are *in* phase. It is true for **reactive** power: $Q\neq0$ needs a phase difference, i.e. a reactive load. Write "reactive power exchange requires a phase difference" if this comes up in P1.

> [!check] Verified (python3, random complex $\tilde I$ and $Z$)
> $\tfrac12\tilde V\tilde I^*=I_{rms}^2Z=V_{rms}^2/Z^*$, agreeing to $10^{-15}$. The instantaneous power decomposes as $p(t)=P[1+\cos(2\omega t+2\theta_v)]+Q\sin(2\omega t+2\theta_v)$ (residual $6\times10^{-15}$). So $Q$ is the amplitude of the zero-mean part exchanged back and forth, consistent with his "peak power exchanged."

### 2. Plan for the semiconductor unit [0:08:48–0:10:24]
- Last class ([[2026-09-30 - Power Factor, Max Power Transfer & Device Models]]) reminded the class of MOSFETs (from 302/302H) and introduced diodes and BJTs. All of these depend on the properties of semiconductor materials.
- Plan:
  1. Basic semiconductor physics (partly review of 302/302H).
  2. Use it to understand **pn junction diodes**.
  3. That understanding is then "built upon" for **bipolar transistors**.
  4. It also explains "many aspects" of MOSFETs.
- pn-junction structures are "the basis for entire other classes of semiconductor devices."

### 3. Semiconductor properties [0:10:24–0:17:05]
Board heading **"Semiconductor properties"** (p02, f_0013 → f_0025):
- "moderate electrical conductivity - higher than insulators, lower than metals." (The ASR says "connectivity"; the board says conductivity.)
- "conductivity can be controlled over many orders of magnitude via voltage or impurities."
  - **Impurities** are "atoms of elements other than what constitutes the semiconductor itself", added at fabrication. This is "what's called doping": a static change [0:11:56–0:13:04].
  - **Voltage** is applied "during operation" and "essentially changes the concentration of electrons in different parts of a device" [0:12:06].
- "foundation for:" (p02–p03)
  - computer processors, GPUs, memory chips: "predominantly silicon... the most technologically important semiconductor material"
  - communications chips: send and receive in your phone; silicon and other semiconductors
  - displays: "a giant chip... fabricated on glass"
  - solar cells: predominantly Si. Solar-grade Si volume now exceeds chip-grade, a crossover "probably over fifteen years ago" (his claim, not checked)
  - LED lighting: **gallium nitride**, which emits short-wavelength light. Residential lighting share of electricity fell from "close to 20%" to "less than 5%" (his figures, not checked)
  - image sensors: a phone camera chip is silicon
  - etc.
- **Why study the physics** [0:16:18–0:16:59]: to push the performance of a device or circuit, understanding "why it behaves the way it does at a fundamental level" is "really essential in doing that type of engineering at the limits of performance."

### 4. Screen-share interruption [0:17:46–0:19:17]
A Zoom update prompt closed the app. The share was down from 0:18:06 to 0:18:51 (f_0033 is black). Audio continued, and no content was lost: he had just announced the next topic, "electronic states and... band structure" [0:17:25]. Aside [0:19:03]: avoid UT-owned computers, because UT administers them.

### 5. Si bonding: isolated atom vs crystal [0:19:17–0:25:14]
Heading **"Electronic states + band structure of semiconductors"** (p06, f_0039). Sub-heading: "Recall how Si atoms bond to form a Si crystal." Partly review of 302/302H, but "self contained."

**Figure, isolated Si atom (f_0041/f_0043):** a circle "Si" represents the nucleus and closed-shell electrons. Four dots sit around it (top, left, right, bottom); one is labelled "electron". Board: **"4 valence electrons."** Spoken: from silicon's position in the periodic table it has 4 valence electrons and **14 electrons in total** [0:21:03–0:21:13].

**Covalent bond** [0:21:18–0:21:59]: atoms share electrons. "If you have a pair of shared electrons, that constitutes the covalent bond." Each of Si's four valence electrons is shared with a neighbouring Si, so **each Si is bonded to four neighbours.**

**Figure, Si crystal (2-D, f_0044/f_0045):**
- A 3 × 3 square array of circled "Si" atoms.
- Every horizontal or vertical neighbour pair is joined by **two black dots inside a red ellipse**, which is one covalent bond. There are 12 bonds.
- Labels: "electrons" (arrow to a dot) and, in red, "covalent bond" (arrow to an ellipse).
- Bonds that would leave the edge of the array are not drawn.

**3-D structure** [0:23:41–0:25:01], *picture not captured in any frame*. "It's not arranged in a square array":
- the structure has **cubic symmetry**
- short bars in the picture are covalent bonds; long bars only outline the cubes
- one highlighted (red) Si is bonded to four nearest neighbours that "form a tetrahedron... a pyramid with a triangular base"
- the 2-D square picture is used because the 3-D one "is very hard to draw"; the feature it preserves is **four nearest neighbours**

> [!note] Added context
> This 3-D arrangement is the **diamond-cubic** lattice, with tetrahedral bond angles of about 109.5°. He did not name it.

### 6. Electronic states: isolated atom → crystal bands [0:25:15–0:35:56]
Heading **"Electronic states occupied by electrons:"** (p06–p07).

**Isolated Si atom (f_0057).**
- Electrons occupy **orbital states**: 1s, 2s, 2p, 3s, 3p, 3d, … [0:26:34].
- **Figure:** vertical "energy" arrow. Levels from the bottom: 1s (2 dots), 2s (2 dots), 2p (6 dots), 3s (2 dots), 3p (2 dots), "⋮" above.
  - A brace **"closed shells"** spans 1s, 2s and 2p.
  - A brace **"valence electrons"** spans 3s and 3p.
- Filling rule [0:27:50]: "we are going to fill the lowest 14 states in energy", because the lowest energy state "minimizes the energy of the system."
  - The count is 2 (1s) + 2 (2s) + 6 (2p) = 10, then 2 (3s) + 2 (3p) = 14.
  - A p orbital holds six electrons (a student answered "six" at 0:27:33).
- Closed-shell electrons "don't really participate in chemical reactions." The electrons in the incompletely filled third shell are the **valence electrons**, which "participate in bonding" and "carry electrical current in a semiconductor crystal" [0:28:45–0:29:38].

**Si crystal (f_0059).** The axes are "energy" (vertical) and position "x" (horizontal).
- **How bands appear** [0:30:27–0:32:23]. Imagine the crystal arrangement with a huge spacing, then shrink it.
  - Far apart, each atom "just looks like an isolated atom."
  - Closer, "this atom knows that this atom is next to it", because "the orbital states... start to overlap."
  - Then the bonds form, and electrons "can move throughout the crystal."
  - The crystal "doesn't so much have the individual orbital states anymore. It has what are called **band states**": states in a range of energy "that extend throughout the entire crystal structure."
- **Valence band** (lower energy) and **conduction band** (higher energy) [0:32:36–0:32:53].
- **Energy band gap** [0:33:03–0:33:30]: "a range of energies between the valence band and the conduction band where there are no electronic states", at least "in a structurally perfect and pure semiconductor."
- **T = 0 K** [0:33:35–0:35:51]. All electrons go to the lowest available states, and "the number of states available in the valence band is exactly equal to the total number of valence electrons in the crystal." Board: **"T = 0 K: all electrons are in valence band, none in conduction band."**
  - **Figure:** line $E_c$ above, line $E_v$ below. The region above $E_c$ is braced "conduction band" (empty) and the gap is braced "energy band gap". Below $E_v$ are three rows of filled dots braced "valence band", with ⋮ below.
- **Band-edge energies** (board, f_0082):
$$E_v=\text{max. energy in valence band},\qquad E_c=\text{min energy in conduction band},\qquad E_g=E_c-E_v\ \text{(spoken, not written)}$$

> [!warning] Lecturer slip, corrected [0:35:22]
> He first said "e sub c here is the maximum energy... Sorry. E sub v is the maximum energy in the valence band." The board subscript on that line is visibly overwritten c → v. Correct: **$E_v$ = top of the VB, $E_c$ = bottom of the CB.**

> [!note] Added context
> A full VB plus an empty CB means no partially filled band. By his later argument (§9), that means no conduction. So an ideal semiconductor at 0 K behaves as an insulator. He did not state this explicitly.

### 7. T > 0 K: electrons and holes [0:35:58–0:46:31]
- The band structure "stays essentially the same" above 0 K [0:36:06].
- *Student question inserted here* [0:36:28–0:41:45], see the table below:
  - VB = **bonding orbitals** and CB = **antibonding orbitals** (chemistry language).
  - A full band allows swapping but "no net motion."
  - A CB electron is not in a "higher orbital than 3p", because the crystal states are combinations of orbitals.
- **Temperature** [0:42:01–0:43:16] is "a measure of the average energy of a system." Above 0 K, "it's not that every electron has that average energy. Some of them have more... some... less." So **a few electrons** reach the CB, and correspondingly there are **a few empty states** in the VB.
- **Figure, T > 0 K (f_0076/f_0081):** the same $E_c$/$E_v$ lines.
  - Three dots are on or just above $E_c$. A label above them, with an arrow, is cropped in every frame; per speech it is "electrons".
  - The top VB rows contain some **open circles**, labelled **"holes"** with an arrow.
  - Board: **"T > 0 K: most electrons are in valence band, a few in conduction band."**
- **Terminology (board, f_0088):**
  - **"Electrons" refers to negative charge carriers in conduction band.**
  - **"Holes" refers to missing electrons in valence band that behave like positive charge carriers.**
  - Spoken [0:45:01–0:45:22]: the absence of a negative charge moving around "is equivalent to having a positive charge move around."
- **Bubble analogy** [0:45:22–0:46:15]: liquid in a bottle. "The electrons are the liquid itself. The holes... bubbles in the liquid." In a nearly full bottle "it's easier to think about how the bubbles are moving around."
- He checked that this was covered in 302/302H; the class said yes [0:46:25].

### 8. How the bands form: energy vs atomic separation $a$ [0:46:34–0:56:57]
Board questions (p08): **"How do conduction + valence band states form? How are they related to covalent bonds? How are bands related to carrier concentrations, mobility, etc.?"** He says he gave "the endpoints" (isolated atom and crystal) and now asks what happens in between.

Board (p09, f_0100): **"Consider N atoms, eg, Si, separated by distance a. The states occupied by valence electrons are distributed in energy, as a function of a, as follows:"**

**Figure (f_0108/f_0114). Redraw it like this:**
1. Vertical axis "energy", horizontal axis "a".
2. At the **right** (large $a$, marked "↦ isolated atoms"), two flat levels: **"3p (6N states)"** on top and **"3s (2N states)"** below. A big brace on the far right says **"occupied by 4N valence electrons."**
3. Going **left** (atoms closer), each level fans out into a widening wedge, because overlapping states must each have "a slightly different energy" [0:51:53].
4. The inner edges of the 3s and 3p wedges meet at an intermediate $a$ (a "<" vertex). In that range the states are "all just kind of mixed together" [0:52:32].
5. Further left they **split apart again** into two hatched bands:
   - upper: **"conduction band, or anti-bonding orbitals"**, braced **"4N states"**
   - lower: **"valence band, or bonding orbitals"**, braced **"4N states"**
   - between them: **"energy band gap"**
6. A **vertical dashed line** at small $a$, labelled **"semiconductor crystal, eg, Si"**, marks the equilibrium separation "what you find in nature" [0:52:55].

**Counting** [0:50:46–0:56:51]:
$$\underbrace{2N}_{3s}+\underbrace{6N}_{3p}=8N\ \text{states}\;\longrightarrow\;\underbrace{4N}_{\text{VB (bonding)}}+\underbrace{4N}_{\text{CB (antibonding)}};\qquad \text{valence electrons}=4\times N=4N$$
So at 0 K the $4N$ valence electrons "completely occupy all of the valence band states" and the CB is empty. As temperature rises, some electrons go up to the CB.

> [!check] Verified (python3)
> Si filling 1s²2s²2p⁶3s²3p² gives 14 electrons, of which 4 are valence. $2N+6N=8N=4N+4N$, and $4N$ valence electrons equal the VB capacity. The board is consistent.

### 9. Which electrons carry current [0:57:00–1:08:01]
**The misconception he raises** [0:57:09–0:57:41]: "most of the electrons are always gonna be in the valence band... intuitively, you might think that... almost all the current is carried by the electrons that are in the valence band because you have so many more electrons... But, actually, that's not quite the case."

**Board (p09 → p10, f_0114 → f_0123):** "In semiconductors, electric current is carried by electrons moving through the crystal in conduction-band or valence-band states, **BUT only electrons in a partially filled band contribute to current.**" Spoken: "perhaps somewhat unexpectedly, if you have a band that is completely filled with electrons, then those electrons cannot actually carry any net electrical current" [0:58:43].

**Why (board, f_0132):** "In brief, this is because if every state in a band is occupied, each electron has a counterpart electron in the same band moving in the opposite direction."
- Spoken [0:59:23–1:00:36]: each band state has an energy and also "momentum associated with it... think of it basically as a velocity."
- "For every state that has a momentum, say, in this direction in a band, there will be some other state that has a momentum in the opposite direction." Fill both and "their motion will cancel."
- With the partner state empty, "you can have some net motion... and that will have some current." There was no drawing; he used gestures.

**Holes as bookkeeping (board, f_0145):** "Because a completely filled band carries no electric current, instead of thinking about electrons moving in an almost-filled valence band, we can think about how the <u>empty</u> states move in the band. These empty states are called "holes"."
- It works because "the sum of the motion of all the electrons that are filled and all the electrons that would have been present in these empty states... has to add up to zero" [1:02:12]. So tracking the few empties is "a lot easier."
- Bubble analogy again [1:07:32–1:07:56]: in a completely full bottle, individual molecules may move, but there is "no net change in the distribution."

**Student follow-ups** [1:02:23–1:06:04], see the table:
- **Pure, perfect crystal.** Every CB electron leaves a VB hole, and both contribute to current.
- **Doped crystal.** "Those impurities can pull some electrons out of the valence band." The electrons sit "at the impurity atom, not up in the conduction band", but "the holes that are left behind... can still carry current." So "there isn't the same connection between electrons in the conduction band and holes in the valence band."
- **Dynamic picture.** A given CB electron may drop back into an empty VB state, but "on average, whenever one... drops down, another one will go up." The net motions of CB electrons and VB holes each contribute to the current.

> [!note] Added context
> Impurities that capture VB electrons (creating holes with no matching CB electrons) are **acceptors** (e.g. B in Si), giving p-type material. Impurities that donate electrons to the CB are donors (n-type). He used neither word in this lecture; presumably they come with doping next class.

### 10. Fermi distribution function [1:08:02–1:15:47]
Motivation [1:08:02–1:10:20]: "we've waved our hands" about a few electrons up and a few empty states down; now be quantitative. Electrons prefer the lowest energies, but thermal energy puts some higher. We want the probability that a state at a given energy is occupied, which leads to "how many electrons will be around in the conduction band, how many holes in the valence band." **This is new; it was not covered in 302/302H** [1:09:02]. The statistical physics is left to ECE 339.

Board heading (p10): **"Occupation of states by electrons – Fermi distribution function."** Board: "The probability that a state at energy E is occupied by an electron is given by the **Fermi distribution function**, f(E):"

$$\boxed{f(E)=\frac{1}{e^{(E-E_F)/k_BT}+1}}$$

Board definitions (p19, f_0191):
- $k_B$ = Boltzmann constant $=1.381\times10^{-23}$ J/K. It "converts temperature to an equivalent energy", hence units of energy over temperature [1:12:28]. On the first attempt "J/K" ran off the page edge (p10) and was rewritten.
- $T$ = temperature in K.
- $E_F$ = Fermi energy or Fermi level = **energy at which $f(E)=\tfrac12$**. Spoken [1:13:59]: "sort of the dividing line" between higher and lower probability of occupation.

**Limits he walks through** [1:14:13–1:15:47], "physically, this expression makes sense":
- $E\ll E_F$: the exponent is very negative, so $e^{(\cdot)}$ is very small and $f\approx\frac{1}{1+\text{small}}\to1$. Low states are almost surely occupied.
- $E=E_F$: $e^{0}=1$, so $f=\tfrac12$.
- $E\gg E_F$: the exponent is large and positive, so $f\to0$. High states are almost surely empty.

> [!check] Verified (python3)
> - CODATA $k_B=1.380649\times10^{-23}$ J/K, so the board's $1.381\times10^{-23}$ is right to 4 s.f.
> - $f$ at $(E-E_F)/k_BT=-5,-3,-1,0,1,3,5$ is $0.9933,\ 0.9526,\ 0.7311,\ 0.5,\ 0.2689,\ 0.0474,\ 0.0067$.
> - Exact symmetry: $f(E_F+\Delta)=1-f(E_F-\Delta)$. The chance a state $\Delta$ above $E_F$ is *filled* equals the chance a state $\Delta$ below is *empty*.

> [!note] Added context (not said in lecture)
> - $k_B=8.617\times10^{-5}$ eV/K, and $k_BT(300\,\text{K})=0.02585$ eV ≈ 25.9 meV. The board gives $k_B$ only in J/K. If $E-E_F$ is given in eV, either convert it to J ($\times1.602\times10^{-19}$) or use $k_B$ in eV/K. Mixing the two is a units trap.
> - At $T=0$, $f(E)$ is a step: 1 below $E_F$ and 0 above.
> - For $E-E_F\gg k_BT$ (a few $k_BT$), $f\approx e^{-(E-E_F)/k_BT}$ (the Boltzmann tail). This is the usual route to $n$ and $p$, which he says is next lecture's topic.

### 11. Pure, perfect semiconductor: $n=p$, $E_F$ near midgap [1:15:47–1:17:50]
Board (p19, f_0203): **"In a pure, perfect semiconductor, the concentrations of electrons (n) and holes (p) must be equal to each other, and $E_F$ is near the middle of the energy band gap."**

Reasoning, as spoken [1:16:04–1:17:43]:
1. In a pure, structurally perfect crystal, "the only way that you get electrons in the conduction band is by leaving behind holes in the valence band." Therefore $n=p$. Here $n$ is the electron concentration (negative carriers) and $p$ the hole concentration (positive carriers).
2. So "the probability of finding empty states in the valence band and of finding filled states in the conduction band... have to be sort of similar."
3. Hence the Fermi level "should be near the middle of the band gap... **Not necessarily exactly in the middle, but near the middle.**"

> [!note] Added context
> The symmetry $f(E_F+\Delta)=1-f(E_F-\Delta)$ is what makes "equal probabilities ⇒ $E_F$ midway" work. $E_F$ misses midgap only because the CB and VB have different effective densities of states: $E_i-E_{mid}=\tfrac{k_BT}{2}\ln(N_v/N_c)$. For Si at 300 K this is about −1 to −13 meV, depending on which $N_c,N_v$ values a textbook uses (computed in python3). That is negligible against $E_g/2\approx0.56$ eV. "Near the middle" is the answer he wants.

### 12. Next time [1:17:50–1:18:29]
Next class is **Monday 10/12**, since Wed 10/7 is SE1. It will go "from the Fermi distribution function to actually calculating electron and hole concentration in semiconductor and what the implications of that are for how semiconductor devices behave."

---

## Ed Yu's conventions & notation

| Item | His convention (this lecture) |
|---|---|
| Band-edge symbols | $E_c$ = **minimum** of the conduction band, $E_v$ = **maximum** of the valence band (he slipped once and corrected). $E_g=E_c-E_v$ (spoken). |
| Fermi function | Called the "**Fermi distribution function**", written $f(E)$, lowercase $f$, capital $E$. Form: $1/(e^{(E-E_F)/k_BT}+1)$, with the exponential first and "+1" last in the denominator. |
| Fermi level | $E_F$, "Fermi energy or Fermi level", **defined as the energy where $f(E)=\tfrac12$**. |
| Boltzmann constant | $k_B$ (subscript B), $=1.381\times10^{-23}$ **J/K** (4 s.f.). No eV value given. $T$ in kelvin. |
| Carrier names | "Electrons" (in quotes on the board) = **negative charge carriers in the CB**. "Holes" = **missing electrons in the VB** that behave like positive carriers. "Electrons" in semiconductor talk means CB electrons by default. |
| Concentrations | $n$ = electron concentration, $p$ = hole concentration. |
| Atom count / states | Capital $N$ atoms. States are counted **including spin**: 3s gives $2N$, 3p gives $6N$, VB $4N$, CB $4N$. |
| Diagram axes | Band diagram: **energy vertical, position $x$ horizontal.** Band-formation diagram: **energy vertical, separation $a$ horizontal**, isolated atoms at the right. |
| Physics vs chemistry names | VB ≡ **bonding orbitals**, CB ≡ **antibonding orbitals**. He writes both names on the band-formation figure. |
| "Pure, structurally perfect" | His phrase for an intrinsic semiconductor ("intrinsic" said once, at 1:04:52). It is the condition for $n=p$ and for no states in the gap. |
| Complex power | $S=\tfrac12\tilde V\tilde I^*$ with **peak** phasors, equivalently $I_{rms}^2Z_L$. Re = average power. |
| Course references | "302 or 302H" = prerequisite; "ECE 339" = where statistical physics is covered. |

---

## Intuition & explanations he gives

- **What makes semiconductors useful:** "you can control the conductivity of a semiconductor over many orders of magnitude", statically by doping or during operation by voltage, which changes the electron concentration in parts of a device. [0:11:39–0:12:24]
- **Why EEs learn the physics:** to push a device or circuit's performance, knowing "why it behaves the way it does at a fundamental level... is really essential." [0:16:18–0:16:59]
- **Filling rule:** electrons fill the lowest 14 states because that "minimizes the energy of the system." [0:27:50]
- **Closed shell vs valence:** closed shells "don't really participate in chemical reactions". Valence electrons bond and "carry electrical current." [0:28:45–0:29:38]
- **How an atom "knows" it is in a crystal:** "the orbital states of the individual atoms, they start to overlap with each other a little bit." [0:31:12–0:31:27]
- **Band states are delocalized:** they "extend throughout the entire crystal structure so that electrons are able to move through the whole crystal." [0:32:10]
- **Why the levels broaden into bands:** once orbitals overlap, the new shared states "each of them has to have a slightly different energy." [0:51:53]
- **VB = bonding, CB = antibonding:** VB electrons "are the ones that are actually forming the bonds." CB electrons are "kind of free to move around through the antibonding orbitals." [0:38:00–0:38:31]
- **Why a full band gives no net motion:** to move, an electron needs "an empty state available... to move to". In a full band "the electrons can switch with each other, but there's no net motion." [0:39:03–0:39:41]
- **Temperature is an average:** "it's not that every electron has that average energy. Some of them have more energy and some of them have less", so a few reach the CB. [0:42:01–0:42:51]
- **Hole as positive carrier:** the absence of negative charge moving around "is equivalent to having a positive charge move around." [0:45:14–0:45:22]
- **Bubble analogy:** electrons are the liquid and holes are bubbles. In a nearly full bottle it is easier to follow the bubbles. In a completely full bottle there is "no net change in the distribution." [0:45:22–0:46:15, 1:07:32–1:07:56]
- **Filled band, counterpart argument:** each state has a momentum ("think of it basically as a velocity"), and every momentum has an opposite partner, so a full band's motions cancel. With one partner empty there is net current. [0:59:23–1:01:28]
- **Why holes are the right bookkeeping:** filled states plus the would-be electrons in the empty states sum to zero motion, so "keeping track of just the empty states is a lot easier." [1:01:58–1:02:23]
- **Doping breaks $n=p$:** impurities "can pull some electrons out of the valence band", leaving holes with no CB electrons. [1:03:39–1:04:11]
- **Dynamic equilibrium:** individual electrons drop back, but "on average, whenever one of these electrons drops down, another one will go up." [1:05:12–1:05:39]
- **$k_B$ meaning:** "a constant that converts temperature to an equivalent energy." [1:12:28]
- **$f(E)$ plausibility:** low-energy states should be occupied and high-energy states empty, and the limits of the formula do exactly that. [1:14:13–1:15:47]
- **Why $E_F$ is near midgap when $n=p$:** the probability of an empty VB state and of a filled CB state must be "sort of similar." [1:16:59–1:17:26]
- **Complex power definition is a choice:** "we chose this particular definition... [so] that when we take the real part, it would give us the average power." [0:05:07–0:05:43]

---

## Emphasis & exam intel

1. **Exam 2 coverage** [0:02:08]: PS6 (maximum power transfer *and semiconductors*) is "material that you're not responsible for for this first semester exam, but you will be responsible for it for the second exam and the final." This lecture is the start of that semiconductor material.
2. **Past exams** [0:03:23–0:04:26]: three years of SE2s are on Canvas with answers and histograms. They are "probably the best guide... But there are never any guarantees."
3. **"Perhaps somewhat unexpectedly"** [0:58:43]: a completely filled band carries no net current. The board's capitalized "**BUT** only electrons in a partially filled band contribute to current" is the line to reproduce in a P1 answer.
4. **Named misconception** [0:57:30]: "you might think that... almost all the current is carried by the electrons that are in the valence band because you have so many more electrons... But, actually, that's not quite the case."
5. **New material, not 302 review** [1:09:02]: he asked and confirmed the class had not seen the Fermi function. Everything else today was partly review.
6. **Definition of $E_F$** [1:13:41]: "the energy at which f of e is equal to one half." It is boxed by being the defining board line.
7. **Precision of the midgap claim** [1:17:26]: "Not necessarily exactly in the middle, but near the middle." Say "near", not "at".
8. **$E_c$ vs $E_v$** [0:35:22]: he mixed them up himself and corrected it. Expect them to be easy to swap under time pressure.
9. **Student confusions he resolved in class** (likely P1 distractors):
   - 6N 3p states vs 2 occupied per atom [0:55:46].
   - A CB electron is not in "an orbital higher than 3p" [0:41:04].
   - Holes in undoped vs doped material [1:02:23].
10. **Complex-power tip** [0:07:37]: with $\tilde V$ and $\tilde I$ in hand, $\tfrac12\tilde V\tilde I^*$; with $Z_L$ handy, $I_{rms}^2Z_L$.
11. **Calculator** [0:04:31]: no phones; a graphing calculator is fine. Said for SE1; presumably the same rule for SE2 (?).

---

## Student questions

| t | Question (reconstructed) | His answer |
|---|---|---|
| 0:02:27 | (Off-mic) Can we photograph the answer sheet instead of scanning? (?) | OK, but it is many pages, uploads are slower and photos are harder to read. Strongly suggests scanning to PDF. |
| 0:03:23 | Are there practice exams on Canvas? Are they representative? | Yes: three years of SE1/SE2/final exams with short answers and score histograms. They are the best guide, with no guarantees. |
| 0:04:28 | (Off-mic) Which calculators are allowed? | Any without communication or photo capability. A graphing calculator is OK; a phone is not. |
| 0:04:51 | Why is the real part of complex power the average power, and what is the imaginary part? (fragmentary) | Complex power was *defined* so that Re = average power. Im "corresponds to the peak power" exchanged between source and load, and needs a reactive load (see the warning in §1). |
| 0:06:38 | When should I use $\tfrac12\tilde V\tilde I^*$ vs $I_{rms}^2 Z_L$? | No fixed rule; they agree. Use $\tfrac12 VI^*$ if you have V and I or the load is messy. Use $I_{rms}^2Z_L$ if $Z_L$ is easy or known. |
| 0:36:28 | What does it mean to be in the valence band? | VB = bonding orbitals: those electrons form the bonds. CB = antibonding orbitals: those electrons are free to move. |
| 0:38:36 | (Follow-up, garbled) Aren't bonding electrons also mobile? (?) | In a full band electrons can swap but give no net motion. Net motion needs empty states, e.g. after an electron is promoted to the CB. |
| 0:40:51 | If an electron is in the CB, is it in an orbital higher than 3p? | No. In the crystal the original orbitals are replaced by combinations forming the bonding/antibonding orbitals, i.e. the VB/CB. Details followed in §8. |
| 0:55:46 | The 3p level has 6N states, but only two valence electrons per atom go there? | 6N is the total number of states available. Each atom has six 3p states, only two occupied. The crystal's $4N$ valence electrons fill the $4N$ VB states at 0 K. |
| 1:02:23 | In undoped Si, do both bands carry current only because CB electrons left holes behind? | Yes, for a pure, perfect crystal: both contribute, and holes always pair with CB electrons. With doping, impurities can pull electrons out of the VB, and the resulting holes conduct with no CB partner. |
| 1:04:19 | Individual electrons only sit in the CB briefly and drop back, but the cumulative amount follows the equation? | Yes. A given electron may drop back, but on average another goes up. The net motions of CB electrons and VB holes each contribute to the current. |
| 0:46:25 / 1:09:02 | (He asked) Did you cover this / the Fermi function in 302/302H? | Bands and holes: yes. Fermi function: no, "So this is new." |

---

## Exam relevance

Exam 2 (Wed 2026-11-11, 4 × 25 pts). The TA's hint is "semiconductor physics on the second exam." **No PS8 problem and no Lab 5 item is worked in this lecture.**

**P1 (four conceptual short answers, filters + semiconductor physics): HIGH.** This lecture is the conceptual base of the semiconductor half. Likely stems, each answerable from the board lines above:
- *Why are semiconductors useful for devices?* Their conductivity is intermediate, and it is controllable over many orders of magnitude by doping (fabrication) or applied voltage (operation).
- *Explain how energy bands form in a Si crystal / sketch energy vs atomic separation.* 3s ($2N$) and 3p ($6N$) broaden, mix, then split into a VB ($4N$, bonding) and a CB ($4N$, antibonding) with a gap. Mark the equilibrium spacing.
- *Why is the valence band exactly full at 0 K?* $4N$ VB states and $4N$ valence electrons (4 per Si).
- *Why does a completely filled band carry no current?* Every occupied state with momentum $+k$ has a partner with $-k$, so the velocities cancel. Only partially filled bands conduct.
- *What is a hole, and why does it act like a positive charge?* It is an empty VB state. The absence of negative charge moving is equivalent to a positive charge moving. Use the bubble analogy.
- *Most electrons are in the VB; why doesn't the VB carry most of the current?* A nearly full band's current equals that of its few empty states (holes), by the cancellation argument.
- *Define $E_F$; give $f(E)$; state the limits.* $f(E_F)=\tfrac12$, $f\to1$ well below, $f\to0$ well above.
- *Where is $E_F$ in a pure, perfect semiconductor, and why?* Near midgap, because $n=p$ and the symmetry of $f$. Say "near", not "at".
- *How does doping change the picture?* Impurities can take electrons from the VB without supplying CB electrons, so $n\neq p$ (the acceptor case; donors come next lecture).
- *T = 0 K vs T > 0 K band filling.* Thermal energy spreads electron energies, so a few cross the gap.

**P2 (passive filter design or max power transfer): LOW–MEDIUM.** Only the opening Q&A applies.
- $S=\tfrac12\tilde V\tilde I^*=I_{rms}^2Z_L$, with Re = average power. Know when each form is quicker.
- Watch the wording trap: real power is largest *in* phase. Reactive power needs a phase difference.

**P3 (filter transfer function + cutoff + Bode): NONE.**

**P4 (active/RLC filter H(ω), type, Bode, design ratio): NONE.**

**Likely numeric variant inside P1:** "Evaluate the probability that a state X eV above (or below) $E_F$ is occupied (or empty) at T K." Use $f(E)$ with consistent units. See Self-check Q3.

> [!summary] Board-error audit
> - No numerical errors on the board. The only number, $k_B=1.381\times10^{-23}$ J/K, is correct to 4 s.f.
> - One spoken slip, corrected live: "$E_c$" said for the VB maximum at 0:35:22, with the board subscript overwritten to $E_v$.
> - One imprecise spoken claim in the complex-power Q&A at 0:06:04: power transfer "needs" $v$, $i$ out of phase. This is true only for reactive power.
> - ASR-only errors: "connectivity" → conductivity, "framing level" → Fermi level, "induction band" → in the conduction band.
> - Not captured in any frame: the 3-D crystal picture (0:23:41–0:25:01) and the label above the T > 0 K picture (per speech, "electrons").

---

## Common mistakes / traps

- **Swapping $E_c$ and $E_v$.** $E_c$ is the **bottom** of the conduction band; $E_v$ is the **top** of the valence band. The lecturer slipped on this himself.
- **"The VB has more electrons, so it carries more current."** No. A completely full band carries zero net current. A nearly full band carries exactly the current of its holes.
- **Treating a hole as a real positive particle.** It is an *empty state* in the VB whose motion is equivalent to a positive charge moving. Use his board wording: "missing electrons in valence band that behave like positive charge carriers."
- **Confusing states with electrons.** 3p has $6N$ states, but only $2N$ electrons occupy them. The VB has $4N$ states, and $4N$ electrons fill it at 0 K.
- **A CB electron is not in a "3d"-type higher atomic orbital.** In a crystal the atomic orbitals are replaced by delocalized band states (bonding/antibonding combinations).
- **"$E_F$ is exactly at midgap."** He said "near... not necessarily exactly." The intrinsic condition is $n=p$, not $E_F$ = midgap.
- **Assuming $n=p$ always.** That holds only for a pure, structurally perfect semiconductor. Doping breaks it.
- **$f(E)$ is a probability per state, not a number of electrons.** Getting $n$ needs the density of states as well (next lecture).
- **Units in $f(E)$.** The board gives $k_B$ in J/K. If $E-E_F$ is in eV, convert it (×$1.602\times10^{-19}$) or use $k_B=8.617\times10^{-5}$ eV/K (added context).
- **Sign in the exponent.** It is $+(E-E_F)/k_BT$ with "+1" in the denominator. Check: $E<E_F$ must give $f>\tfrac12$.
- **"0 K means no electrons anywhere."** At 0 K the VB is completely full; only the CB is empty.
- **Complex power:** do not claim real power transfer needs $v$ and $i$ out of phase. Reactive power does.

---

## Self-check

**Q1.** Silicon has 14 electrons. Write the isolated-atom configuration and identify the valence electrons. For a crystal of $N$ atoms, give the number of states in the VB and in the CB, and say why the VB is exactly full at 0 K.
> [!question]- Answer
> 1s²2s²2p⁶3s²3p². The closed shells (1s, 2s, 2p) hold 10 electrons, and the **4 valence electrons** are 3s²3p². The 3s levels give $2N$ states and the 3p levels $6N$, $8N$ in total, which split into **$4N$ VB (bonding)** and **$4N$ CB (antibonding)**. There are $4N$ valence electrons and they fill the lowest states, so at 0 K they exactly fill the $4N$ VB states and the CB is empty. (python3: 2+2+6+2+2 = 14 and 2N+6N = 4N+4N.)

**Q2.** Explain in two sentences why a completely filled band carries no net current, and why this makes "holes" useful.
> [!question]- Answer
> Every band state has a momentum (velocity), and for every occupied state moving one way there is an occupied counterpart in the same band moving the opposite way. Their contributions cancel, so a full band carries zero net current. In a nearly full VB the total current therefore equals what the few *empty* states would contribute, so we track those empty states ("holes"), which behave like positive carriers. The alternative is tracking all the electrons.

**Q3.** At $T=300$ K, what is the probability that a state 0.2 eV **above** $E_F$ is occupied? What is the probability that a state 0.2 eV **below** $E_F$ is **empty**? Use $k_B=1.381\times10^{-23}$ J/K.
> [!question]- Answer
> $(E-E_F)/k_BT=\dfrac{0.2\times1.602\times10^{-19}\ \text{J}}{1.381\times10^{-23}\times300\ \text{J}}=7.73$.
> - Occupied above: $f=1/(e^{7.73}+1)=\mathbf{4.37\times10^{-4}}$.
> - Empty below: $1-f(E_F-0.2\ \text{eV})=1-0.99956=\mathbf{4.37\times10^{-4}}$. This is the same by the symmetry $f(E_F+\Delta)=1-f(E_F-\Delta)$.
>
> (python3: 4.3733e-4 both; the Boltzmann approximation $e^{-7.73}=4.375\times10^{-4}$.) *Numbers chosen by me, not from the lecture.*

**Q4.** In a pure, structurally perfect semiconductor, why must $n=p$, and what does that imply about $E_F$? Name one way the equality is broken.
> [!question]- Answer
> The only source of CB electrons is promotion from the VB, and each promotion leaves exactly one hole, so $n=p$. Equal numbers require the probability of a filled CB state to be similar to the probability of an empty VB state. Because $f$ is symmetric about $E_F$, this puts **$E_F$ near (not necessarily exactly at) the middle of the gap**. **Doping** breaks it: impurity atoms can capture VB electrons (creating holes with no CB electron), or donate electrons.

**Q5.** State $f(E)$, define $E_F$, and give $f$ for $E\ll E_F$, $E=E_F$, $E\gg E_F$.
> [!question]- Answer
> $f(E)=\dfrac{1}{e^{(E-E_F)/k_BT}+1}$, the probability that a state at energy $E$ is occupied by an electron. $E_F$ (Fermi energy or Fermi level) is the energy at which $f=\tfrac12$.
> - $E\ll E_F$: $f\to1$.
> - $E=E_F$: $f=\tfrac12$.
> - $E\gg E_F$: $f\to0$.
>
> (python3: $f(\pm5k_BT)=0.0067/0.9933$.)
