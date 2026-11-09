---
course: ECE 411H
unit: exam2
kind: instructor-intel
topic: semiconductors
target: "Semester Exam 2 (Wed 2026-11-11, 70 min, closed book), Problem 1 conceptual short answers"
sources:
  - Transcripts/Recitations/Recitation5_2026-10-12_semiconductors.md
  - Transcripts/Refreshers/Semiconductors_review_ETY.md
  - Transcripts/Exams/SE2_F23_questions.md
  - Transcripts/Exams/SE2_F23_short_answers.md
  - Transcripts/Exams/SE2_F24_questions.md
  - Transcripts/Exams/SE2_F24_short_answers.md
  - Transcripts/Exams/Final_F24_questions.md
  - Transcripts/Exams/Final_F24_short_answers.md
  - Transcripts/Exams/Final_F25_questions.md
  - Transcripts/Exams/Final_F25_short_answers.md
  - Transcripts/Problem Sets/PS6_problems.md
  - Transcripts/Problem Sets/PS6_solutions.md
created: 2026-11-06
tags: [ece411, exam2, semiconductors, fermi-dirac, pn-junction, short-answer-bank]
---

# Semiconductors: recitation, refresher and past P1 answers

This note is the semiconductor half of Problem 1 on Semester Exam 2. It collects every statement the instructors (Prof. Ed Yu and TA Darsh Shah) have made about the semiconductor physics in this course, puts each definition in their own words, and builds a bank of short-answer stems with full-credit answer templates. The filter half of Problem 1 is covered elsewhere.

**Source keys used throughout.**
- **R5 pN**: Recitation 5 (TA Darsh Shah, 2026-10-12), handwritten page N. I checked the figures on pp. 2–4 against the rendered PDF.
- **ETY pN**: Prof. Ed Yu, "Basics of Semiconductors (from ECE 302/302H)" review handout, page N. I checked pp. 3–4 against the rendered PDF.
- **PS6 Pn**: Problem Set 6 statement, problem n. **PS6 sol pN**: PS6 solutions, page N. Pages 3–7 are the instructor's handwritten solutions.
- **SE2-F23 1(b)** and similar: Semester Exam 2, Fall 2023, Problem 1 part (b). "key" means the instructor's short-answer sheet. **FE-F24** and **FE-F25** are the Fall 2024 and Fall 2025 finals.
- Not consulted: lecture recordings and lecture notes (another note covers them, including the pn-junction band-diagram lecture that PS6 P5 refers to), SE2 F25 (held back as the practice exam), and Final F23 (not in this brief).

**Constants (checked with python3).**

| Quantity | Value | Where it appears |
|---|---|---|
| $k_B$ | $8.617\times10^{-5}$ eV/K $= 1.381\times10^{-23}$ J/K | R5 p2, R5 p3; PS6 sol p4 |
| $k_BT$ at 300 K | $0.02585$ eV (the TA rounds to $0.026$ eV $= 26$ meV) | R5 p2; computed |
| $q$ (also written $e$) | $1.602\times10^{-19}$ C; 1 eV $= 1.602\times10^{-19}$ J | ETY p1; R5 p2 |
| $\hbar$, $m_e$ | $1.055\times10^{-34}$ J·s, $9.11\times10^{-31}$ kg | R5 p2–3; PS6 P4 |
| Si effective masses | $m_c^* = 1.18\,m_e$, $m_v^* = 0.81\,m_e$ | R5 p2; PS6 P4(b) |
| $E_g$ | Si 1.12 eV; Ge 0.67 eV | PS6 P4(b); FE-F24 1(e) |
| $N_c = 2(m_c^*k_BT/2\pi\hbar^2)^{3/2}$, Si, 300 K | $3.21\times10^{19}$ cm$^{-3}$ | computed from the PS6 constants |
| $N_v = 2(m_v^*k_BT/2\pi\hbar^2)^{3/2}$, Si, 300 K | $1.83\times10^{19}$ cm$^{-3}$ | computed from the PS6 constants |
| $n_i$, Si, 300 K | $9.47\times10^{9}$ cm$^{-3}$ (PS6 sol p4); $\approx 1\times10^{10}$ cm$^{-3}$ (ETY p3) | both are acceptable |
| $k_BT\ln 10/q$ at 300 K | 59.5 mV (one decade of diode current) | computed |

---

## Exam intel

### Format and rules (verbatim; the same wording on SE2-F23, SE2-F24, FE-F24 and FE-F25)

- The P1 instruction reads: "Answer the questions below. Each should require a few sentences or relatively small amount of math at most. You may also include a sketch/picture if necessary."
- The rules read: "You must show all of your work to receive credit. If you need to make an assumption to answer a question, state it explicitly."
- On numbers: "Unless otherwise stated, you may assume all numerical quantities given in the exam problems are known to 3 significant figures".
- The exam is closed book: "The exam questions, answer sheets, and a calculator are allowed; no other materials should be consulted during the exam." Semester Exam 2 has no formula sheet. The finals append a Laplace handout and nothing else. So far, any number a semiconductor stem needed was printed in the stem itself (FE-F24 1(e) gives both band gaps). The formulas you must carry in memory.
- **Point values.** On SE2, P1 is split (a) 6, (b) 6, (c) 6, (d) 7. In both F23 and F24, parts (b) and (c) were the semiconductor items, worth 12 of the 25 P1 points (12% of the exam). On the finals each P1 part is worth 5 points.

### What has been asked

| Exam | Part | Topic | Points |
|---|---|---|---|
| SE2-F23 | 1(b) | Choosing a dopant for n-type Si: B (3 valence e⁻) or As (5 valence e⁻) | 6 |
| SE2-F23 | 1(c) | Why diode current rises exponentially with $V$, "in terms of the Fermi distribution function and its dependence on energy" | 6 |
| SE2-F24 | 1(b) | Why acceptors (B in Si) move $E_F$ toward the valence-band edge | 6 |
| SE2-F24 | 1(c) | Why diode current rises exponentially, "in terms of the mathematical form of the Fermi distribution function" | 6 |
| FE-F24 | 1(e) | Undoped Si (1.12 eV) vs Ge (0.67 eV): which has more valence-band holes | 5 |
| FE-F25 | 1(e) | Why diode current rises exponentially, "in terms of the behavior of electrons and holes in a semiconductor's conduction band and valence band, respectively" | 5 |

**The pattern.** The diode-exponential question appears on 3 of the 4 exams in my inputs, and it was part (c) on both SE2s. The other semiconductor slot rotates among dopant choice, Fermi-level shift and band gap. On both SE2s the semiconductor items were parts (b) and (c), and parts (a) and (d) were filter concepts.

### Score data

Only whole-P1 averages are published; there are no per-part scores.
- SE2-F23: P1 = 20.3/25 (81%). SE2-F24: P1 = 18.2/25 (73%). FE-F24: P1 = 23.1/25. FE-F25: P1 = 17.1/25, the lowest of the four.
- *Inference:* the two lowest P1 averages came in the years with the acceptor/Fermi-level item (SE2-F24) and the electrons-and-holes version of the diode item (FE-F25). The per-part data needed to confirm that link does not exist.

### The keys' model answers, verbatim

- **SE2-F23 1(b), key:** "As, since extra valence electron compared to Si will occupy a state in the conduction band."
- **SE2-F23 1(c), key:** "Fermi distribution function decreases exponentially with increasing energy. Increasing V>0 lowers barrier for carriers to traverse the pn junction by qV, and therefore exponentially increases the concentration of carriers with sufficient energy to cross the pn junction and contribute to current flow."
- **SE2-F24 1(b), key:** "Acceptor removes electrons from/creates holes in the valence band; probably [sic: probability] of finding empty states in the valence band increases, so Fermi level must move closer to valence band."
- **SE2-F24 1(c), key:** "Energy barrier for carriers to diffuse across junction decreases with positive V, so from form of f(E) one can show that current increases exponentially."
- **FE-F24 1(e), key:** "Germanium" (no explanation in the key).
- **FE-F25 1(e), key:** "At forward bias, more electrons on the n-side have enough energy to surmount the built-in pn junction barrier and move to the p-side, and more holes on the p-side have enough energy to surmount the barrier and move to the n-side, resulting in forward-bias current flow. The concentration of carriers on each side with sufficient energy to surmount the barrier increases exponentially with voltage because the Fermi distribution function well above the Fermi level, and 1-f(E) well below the Fermi level, depend approximately exponentially on voltage/kT."

### What earns credit, judged from how the keys are written

My inputs contain no grading rubric, so this list is inferred from the keys.

1. **Every key is a causal chain.** Each one runs: microscopic cause, then band or statistics effect, then conclusion. The SE2-F23 1(c) key has two explicit halves: (i) f(E) decreases exponentially with energy; (ii) $V>0$ lowers the barrier by $qV$, and *therefore* the number of carriers able to cross rises exponentially. An answer with only one half leaves out half the mechanism.
2. **The vocabulary is fixed.** The keys reuse these phrases: "Fermi distribution function", "decreases exponentially with increasing energy", "lowers barrier ... by qV", "carriers with sufficient energy to cross", "occupy a state in the conduction band", "creates holes in the valence band", "probability of finding empty states", "surmount the built-in pn junction barrier", "f(E) well above the Fermi level, and 1−f(E) well below". Use them.
3. **The keys show no math, but the stems invite it.** The SE2-F24 1(c) key says "from form of f(E) one can show". Since that stem asks "in terms of the mathematical form", write $f(E)\approx e^{-(E-E_F)/k_BT}$ and the factor $e^{qV/k_BT}$. It costs one line.
4. **A one-word key is shorthand.** The FE-F24 1(e) key reads only "Germanium", but the stem says "Explain". Do not stop at the choice.
5. **The framing words in the stem decide what you must mention.**
   - "Fermi distribution function and its dependence on energy": the exponential decrease with $E$.
   - "mathematical form": write $f(E)$ and its Boltzmann tail.
   - "electrons and holes ... conduction band and valence band": both carrier types, using $f$ above $E_F$ for electrons and $1-f$ below $E_F$ for holes.
   - The answer template for P-2/P-4/P-6 below covers all three framings at once.

### TA intel

- The R5 transcript summary records the TA saying on Discord that this material "will certainly be on PS6 and on y'all's next exam" and that "there are often questions on semiconductor physics on the second exam". The brief dates the second statement 2026-10-20.
- The four recitation pages contain no exam hints (I checked the rendered pages).
- R5 maps directly onto PS6 P3 and P4 ($n$, $p$, $n_i$).
- The PS6 P5 hint points to *lecture*, not recitation: "Recall from class how the band-edge energies in the pn junction change with V". The pn-junction band diagram is therefore lecture material. PS6 sol p5 reproduces it (see W5 below).
- On ETY p4, Ed Yu flags MOSFETs as "not necessary for ECE 411". Skip that material.
- Ed Yu's own explanation of why $n_i$ matters (PS6 P4) makes a ready-made exam stem: "$n_i$ is one of the important factors limiting the temperature at which devices can operate: at high temperatures, $n_i$ can approach typical dopant concentrations and the ability to control electronic properties and current flow via doping is degraded or lost." It is used as stem N4 below.

### Prediction for F26 SE2 P1 (inference)

- **The diode-exponential item is very likely** (3 of 4 past exams). Prepare one answer that satisfies all three framings (P-2/P-4/P-6 below).
- **The second semiconductor item will probably be a doping, Fermi-level, $n_i$ or conductivity question.** It would be one of: choose a dopant for n- or p-type; which way $E_F$ moves; $n_i$ versus $E_g$ or $T$; conductivity versus doping (that last one is ETY material that has not been asked yet). Stems N1–N12 cover these.

---

## The objects, defined in the instructors' words

Each entry gives the formula, a one-sentence meaning, and the source. Wording in quotation marks is verbatim. Anything outside the sources is marked *added*.

### Crystal, bands, carriers

**Silicon crystal and covalent bond.** "Si → 4 valence e⁻" (R5 p1). Ed Yu: "14 electrons, including 4 valence electrons in outer shell" and "In a silicon crystal, each Si atom is bonded to its four nearest neighbor atoms" (ETY p2).
*Meaning:* each Si atom shares one electron pair with each of its four neighbours, so in a perfect crystal at $T=0$ every valence electron is locked in a bond.

**Semiconductor.** "Semiconductors are materials whose properties, e.g., electrical conductivity, can be precisely controlled across, often, a very wide range of values." That control comes from "the introduction of impurity atoms, application of voltage, or other means" (ETY p1).
*Meaning:* the defining feature is controllability, through doping and through applied voltage.

**Conduction band, valence band, band gap.** $E_g \equiv E_c - E_v$. PS6 P4(a) defines it: "$E_g$ is energy band gap, with $E_g \equiv E_c - E_v$". R5 p1 draws $E_c$ as the upper line and $E_v$ as the lower line, with the gap $E_g$ bracketed between them.
*Meaning:* the valence band holds the bonding electrons; the conduction band holds the states of mobile electrons; the gap contains no states in a pure crystal.
*Values:* Si 1.12 eV, Ge 0.67 eV. R5 p2 gives ranges: "$E_g$ metal/cond. $\lesssim 0$ eV", "$E_g$ semi $\approx$ 1–3 eV", and "$E_g$ insul. $\gtrsim$ (10 keV)?". The insulator entry is wrong; see Conflicts.

**Metal vs semiconductor vs insulator.** R5 p1 draws three band diagrams:
- *Conductors:* the lines are drawn inverted, with $E_v$ above $E_c$. The bands overlap and there is no gap.
- *Semiconductor:* a moderate gap.
- *Insulators:* "$E_g \gg E_{g,\text{semi}}$".

*Meaning:* the size of the gap compared with $k_BT$ decides whether any electrons are thermally present in the conduction band.

**Electrons and holes.** Ed Yu: "At temperatures above absolute zero, some electrons have enough energy to 'escape' from a covalent bond and become mobile (able to move through the Si crystal). The resulting 'hole' that's left behind is also mobile". The electron has "charge $-q$" and the hole has "charge $+q$" (ETY p3). In band language (R5 p1):
- At $T=0$, every electron sits below $E_v$ and the conduction band is empty.
- At $T>0$, "There will > 0 particles w/ energy > $E_g$. For higher T, particles w/ energy > $E_g$ will increase."
- An electron excited across $E_g$ leaves an empty valence-band state, which is the hole. The green sketch on R5 p1 shows the reverse process, recombination.

*Meaning:* a hole is an empty state in the valence band. It moves as neighbouring bond electrons hop into it, and it behaves as a $+q$ carrier.

**Thermal energy.** "$k_BT = 0.026$ eV" with "Boltzmann's const. $(8.617\times10^{-5}$ eV/K$)$" (R5 p2). The exact value at 300 K is 0.02585 eV.
*Meaning:* the energy scale over which the occupation of states changes. A gap of about 1 eV is about $43\,k_BT$.

### Statistics

**Fermi–Dirac distribution.**
$$f(E) = \frac{1}{e^{(E-E_F)/k_BT}+1}$$
R5 p2 calls it the "prob. that a state at $E$ is occupied" and notes "$E\to\infty$, $f(E)=0$". The same form is printed in PS6 P3.
*Meaning:* the probability that an available electron state at energy $E$ is filled. It is near 1 well below $E_F$ and falls toward 0 well above it.

**Fermi level.** R5 p2: "Looking at ①, what $E$ gives $f(E)=1/2$? ↳ $E_f$! ⇒ Fermi level energy."
*Meaning:* $E_F$ is the energy where the occupation probability is exactly $1/2$, at every temperature. Moving $E_F$ is how doping changes $n$ and $p$.

**Probability of a hole, $1-f(E)$.** R5 p3 draws $1-f(E)$ in blue in the $p$ row. PS6 P3 integrates $[1-f(E)]$ against $g_v$.
*Meaning:* the probability that a state at $E$ is empty, which is the probability that a hole sits there.

**Boltzmann approximation.**
- For electrons, R5 p2: "If $k_BT \approx 26$ meV, $E - E_f \gg k_BT$, $f(E)\approx \frac{1}{e^{(E-E_f)/k_BT}} = e^{-(E-E_f)/k_BT}$".
- For holes, PS6 sol p3: "Since we take $(E_F-E_v)\gg k_BT$ ... $\frac{1}{1+x}\approx 1-x$ for $x\ll1$", which gives $1-f(E)\approx e^{-(E_F-E)/k_BT}$.

*Meaning:* far from $E_F$, the tails of $f$ and $1-f$ are pure exponentials in energy. This single fact is the source of every exponential in the diode.

How good the approximation is (python3):

| $E-E_F$ | exact $f$ | $e^{-(E-E_F)/k_BT}$ | Boltzmann overestimate |
|---|---|---|---|
| 0 | 0.5 | 1 | 100% |
| $1\,k_BT$ | 0.269 | 0.368 | 37% |
| $3\,k_BT$ | 0.0474 | 0.0498 | 5.0% |
| $5\,k_BT$ | $6.69\times10^{-3}$ | $6.74\times10^{-3}$ | 0.67% |
| 0.1 eV ($3.9\,k_BT$) | 0.0205 | 0.0209 | 2% |

**Density of states (DoS).** R5 p2: "Density of States (DoS) is the # of states at given $E$ per unit volume", and "Expectation[# of occupied states] = P(state is occupied) · # of states = $f(E)$ · DoS".
$$g_c(E) = \frac{\sqrt2}{\pi^2}\left(\frac{m_c^*}{\hbar^2}\right)^{3/2}(E-E_c)^{1/2},\qquad g_v(E) = \frac{\sqrt2}{\pi^2}\left(\frac{m_v^*}{\hbar^2}\right)^{3/2}(E_v-E)^{1/2}$$
(R5 p2; PS6 P3.)
*Meaning:* the number of available states rises from zero like a square root as you move into either band.

**Effective mass.** "$m_c^* = 1.18\,m_e$, $m_v^* = 0.81\,m_e$" (R5 p2). The TA's sketch contrasts an electron moving through a lattice ($m^*$) with one in empty space ($m$).
*Meaning:* the mass that makes a carrier in the periodic crystal behave like a free particle. A larger $m^*$ gives more states (a larger $N_c$ or $N_v$).

**Electron and hole concentrations.**
$$n=\int_{E_c}^{\infty} f(E)\,g_c(E)\,dE \approx N_c\,e^{-(E_c-E_F)/k_BT},\qquad p=\int_{-\infty}^{E_v}[1-f(E)]\,g_v(E)\,dE \approx N_v\,e^{-(E_F-E_v)/k_BT}$$
$$N_{c} = 2\left(\frac{m_{c}^*k_BT}{2\pi\hbar^2}\right)^{3/2},\qquad N_{v} = 2\left(\frac{m_{v}^*k_BT}{2\pi\hbar^2}\right)^{3/2}$$
The integrals are on R5 p3. The closed forms are in PS6 P3 and P4, written with the full prefactor. The names $N_c$ and $N_v$ ("effective density of states") are shorthand added here; the sources write out the prefactor.
*Meaning:* $n$ is the sum over the band of (states) × (probability filled). The Boltzmann tail makes it an effective number of states times one exponential factor. R5 p3 draws this as plot $f$ × plot DoS = a narrow lobe just above $E_c$. *(Added: the lobe peaks at $k_BT/2$ above $E_c$.)*

**Intrinsic concentration.** Ed Yu: "The concentration of electrons, and holes, created by this process is called the intrinsic concentration, $n_i$. For Si at 300 K, $n_i \approx 1\times10^{10}$ cm$^{-3}$" (ETY p3). PS6 P4(b) defines it as "the value of $n$ and $p$ when they are equal to each other. This value is called the intrinsic concentration $n_i$".
$$n_i = \sqrt{N_cN_v}\,e^{-E_g/2k_BT}\quad(\text{Si, 300 K: } 9.47\times10^{9}\ \text{cm}^{-3},\ \text{PS6 sol p4})$$
The square-root form follows from multiplying the $n$ and $p$ formulas; it is written out here, not in the sources.
*Meaning:* the carrier concentration created purely by thermal excitation across the gap. It depends exponentially on $E_g/k_BT$.

**Law of mass action.** R5 p3, top line: "$n_i^2 = np$".
*Why it holds:* multiply the two closed forms. $E_F$ cancels:
$$np = N_cN_v\,e^{-(E_c-E_v)/k_BT} = N_cN_v\,e^{-E_g/k_BT} = n_i^2.$$
The product therefore does not depend on doping. It holds in equilibrium ($V=0$). *(Added: under bias, $np$ near the junction is $n_i^2e^{qV/k_BT}$, which is the diode mechanism.)*

**Intrinsic Fermi level.** From PS6 sol p4:
$$E_c - E_F = \tfrac12E_g - \tfrac34k_BT\ln\!\left(\frac{m_v^*}{m_c^*}\right) = 0.5673\ \text{eV}\ \ (\text{Si})$$
*Meaning:* in undoped material $E_F$ sits essentially at mid-gap. In Si it is 7.3 meV *below* mid-gap, because $m_v^*<m_c^*$ means the valence band has fewer states.

### Doping

**Donor and acceptor.** Ed Yu (ETY p3):
- "B is referred to as an 'acceptor' since it can accept an electron to create an additional hole in the semiconductor."
- "P is referred to as a 'donor' since it can donate an electron to the semiconductor crystal."
- The ions left behind: "hole created by B can move, leaving behind a negatively charged B ion". He struck out "positively" and wrote "negatively" in the original. Also: "electron introduced by P can move, leaving behind a positively charged P ion".
- In band language (SE2-F23 key), the extra electron of As "will occupy a state in the conduction band".

*Meaning:* a group-V atom (P, As) has one electron more than its four bonds need and gives it to the conduction band. A group-III atom (B; *added:* Al, Ga, In) has one too few and takes an electron from the valence band, which creates a hole. The ions stay fixed in the lattice.

**Doping levels and the donor level.** R5 p4:
- "$n, p = 10^{14} - 10^{18}$ doping/cc ⇒ $10^{-8} - 10^{-4}$ difference; $N_{Si} = 10^{22}$ atom/cc". *(Added: the actual density is $5\times10^{22}$ cm$^{-3}$.)*
- The figure places the donor level $E_d$ (dashed) just below $E_c$, separated by a small green-bracketed gap labelled "$E_{g2}$" (the donor ionization energy). A green arrow lifts the donor electrons into the conduction band.

*Meaning:* a few dopant atoms per $10^{4}$–$10^{8}$ Si atoms change $n$ or $p$ by many orders of magnitude, and the donor electron needs only a small energy to reach $E_c$.

**n-type and p-type.** Ed Yu (ETY p4):
- "1) If $N_D = N_A$, then $n = p = n_i$"
- "2) If $N_D \gg N_A$ and $N_D \gg n_i$, $n \approx N_D$ and $n \gg p$. Semiconductor is referred to as n-type (more electrons than holes)"
- "3) If $N_A \gg N_D$ and $N_A \gg n_i$, $p \approx N_A$ and $p \gg n$. Semiconductor is referred to as p-type (more holes than electrons)."

With $np=n_i^2$, the minority concentration is $p = n_i^2/N_D$ in n-type and $n = n_i^2/N_A$ in p-type.

**How doping moves $E_F$.**
- The TA (R5 p4): "⇒ Doping changes $E_f$ ⇒ $n$, $p$". The figure moves $E_f$ from mid-gap up to "$E_{f,\text{new}}$", drawn just below $E_d$.
- Ed Yu's reason for acceptors (SE2-F24 key): the "probability of finding empty states in the valence band increases, so Fermi level must move closer to valence band."
- Solving the $n$, $p$ closed forms with $n\approx N_D$ or $p\approx N_A$ (algebra written out here, not in the sources):
$$E_c - E_F = k_BT\ln\frac{N_c}{N_D}\quad(\text{n-type}),\qquad E_F - E_v = k_BT\ln\frac{N_v}{N_A}\quad(\text{p-type})$$

*One-line reason:* $E_F$ must sit where $f(E)$ reproduces the carrier populations. More electrons in the conduction band needs a larger $f$ near $E_c$, so $E_F$ moves closer to $E_c$. More empty states in the valence band needs a larger $1-f$ near $E_v$, so $E_F$ moves closer to $E_v$.

### Conduction

**Drift, mobility, resistivity, conductivity.** Ed Yu (ETY p1–2):
- $v=\mu\mathcal E$ ("$\mu$ = mobility [m²/V·s]").
- "$J = nqv = nq\mu\mathcal{E}$".
- $R = \rho\,\ell/A$ with "$\rho = \frac{1}{nq\mu}$ [Ω·m] = resistivity".
- "$\rho$ is an intensive (or intrinsic) material property — doesn't depend on size or shape".
- $\sigma = 1/\rho$ [S/m].
- "$J=\sigma\mathcal E$ (microscopic version of Ohm's Law)".

*Meaning:* conductivity is proportional to the carrier concentration, so doping sets resistivity. *(Added: with both carriers present, $\sigma = q(n\mu_n + p\mu_p)$.)*

### pn junction and diode

**pn junction.**
- Ed Yu: "By combining n-type and p-type regions into a single semiconductor device, one can construct transistors, diodes, or other types of electronic devices" (ETY p4).
- PS6 P5: "In a pn junction diode, current flow occurs when a positive voltage $V$ is applied to the p-type terminal relative to the n-type terminal."
- ETY p4 (MOSFET context): "it is very difficult for electrons to enter a p-type region, or holes an n-type region, unless voltages are applied."

**Built-in barrier.** The FE-F25 key calls it "the built-in pn junction barrier"; the SE2-F23 key, the "barrier for carriers to traverse the pn junction". The band diagram (PS6 sol p5, $n$-side grounded) has $E_c$ and $E_v$ high on the p side, stepping *down* across the junction to the n side. The step is the barrier that n-side electrons must climb, and that p-side holes must "climb" downward, to cross.

> [!note] Added context (not in my inputs; the lecture may give it)
> Built-in potential: $V_{bi} = \dfrac{k_BT}{q}\ln\dfrac{N_AN_D}{n_i^2}$. For $N_A = N_D = 10^{16}$ cm$^{-3}$ and $n_i = 9.47\times10^9$ cm$^{-3}$, $V_{bi} = 0.717$ V (python3). Under bias the barrier height becomes $q(V_{bi}-V)$.
> **Depletion region:** near the junction, electrons and holes diffuse across and recombine. That leaves uncompensated fixed ions: $N_A^-$ on the p side and $N_D^+$ on the n side. Their charge creates the field and potential step $V_{bi}$ that stops further net diffusion. Forward bias narrows the region; reverse bias widens it.

**Forward and reverse bias.**
- Forward bias is $V>0$ on the p terminal relative to the n terminal (PS6 P5). It "lowers barrier for carriers to traverse the pn junction by qV" (SE2-F23 key).
- Reverse bias is $V<0$. Evaluating Ed Yu's $J(V)$ (wording mine): $e^{qV/k_BT}\to0$, so $J\to-(A_1n_{p0}+A_2p_{n0})$, a small current that does not depend on $V$.

**Quasi-Fermi levels under bias.** PS6 P5 hint: "for $V\neq0$, $n$ on the p-side of the junction is determined by $E_F$ on the n-side of the junction, and $p$ on the n-side of the junction is determined by $E_F$ on the p-side of the junction." PS6 sol p5 then writes $E_{F,n}-E_{F,p} = eV$.
*Meaning:* the applied voltage splits the single equilibrium $E_F$ into two levels separated by $qV$. The minority carriers that reach the far side of the junction are populated by the *other* side's Fermi level.

**Minority-carrier injection.** $n_p = n_{p0}e^{eV/k_BT}$ and $p_n = p_{n0}e^{eV/k_BT}$ (PS6 sol p5). Here $n_{p0}$ and $p_{n0}$ are the $V=0$ values, $n_i^2/N_A$ and $n_i^2/N_D$.

**Diffusion and diffusion length.**
- PS6 P6(b): "The primary mechanism for carrier motion and current flow in an ideal pn junction diode is diffusion of holes on the n-side of the junction, and of electrons on the p-side of the junction, in the direction away from the junction." Also: "Diffusion occurs due to spatial variations in the concentration of electrons or holes".
- $J_{diff} = -qD\nabla n$, with $[D]$ = m²/s and $L=\sqrt{D\tau}$ (PS6 sol p6).

**Ideal diode equation.**
$$J(V) = \left(A_1n_{p0} + A_2p_{n0}\right)\left(e^{qV/k_BT}-1\right) = e\left(\frac{D_n}{L_n}n_{p0} + \frac{D_p}{L_p}p_{n0}\right)\left(e^{eV/k_BT}-1\right)$$
(PS6 P5; PS6 sol p7, "one of the standard forms for the ideal diode equation".)
*Meaning:* the current is proportional to the excess minority carriers injected across the junction, and that excess is exponential in $V$.

**Why the current is exponential, built from f(E).** This combines the SE2-F23, SE2-F24 and FE-F25 keys with PS6 sol p5.
1. To cross the junction, a carrier needs energy above the barrier top $E_B$.
2. The number of n-side electrons that qualify is
$$\int_{E_B}^{\infty}g_c(E)f(E)\,dE \;\propto\; e^{-(E_B-E_F)/k_BT}$$
because $f$ has the Boltzmann tail there.
3. Forward bias lowers $E_B$ by $qV$, which multiplies that population by $e^{qV/k_BT}$. Holes on the p side work the same way, with $1-f(E)\approx e^{-(E_F-E)/k_BT}$.
4. The current is proportional to the injected carriers minus their $V=0$ values, giving $J\propto e^{qV/k_BT}-1$.

PS6 sol p5 reaches the same result through quasi-Fermi levels: $n_p = N_ce^{-(E_c-E_{F,n})/k_BT}$ with $E_{F,n}=E_{F,p}+qV$.

---

## Short-answer bank

### Past stems (verbatim), the key, and a full-credit template

**P-1. SE2-F23 1(b) [6 pts], dopant for n-type**
> To create an n-type semiconductor from a crystal of pure Si, would you replace some of the Si atoms with B (boron, 3 valence electrons/atom) or As (arsenic, 5 valence electrons/atom)? Explain your answer.

*Key:* "As, since extra valence electron compared to Si will occupy a state in the conduction band."

*Template:* As. As has 5 valence electrons, one more than Si. Four of them complete the covalent bonds with the four Si neighbours. The fifth is only weakly bound (its donor level $E_d$ lies just below $E_c$), so at room temperature it is donated into a state in the conduction band, leaving behind a fixed, positively charged As⁺ ion. Each As atom therefore adds a mobile electron without adding a hole, so $n\approx N_D\gg p$ (with $p = n_i^2/N_D$) and the crystal is n-type. B, with 3 valence electrons, would instead accept an electron from the valence band, create a hole, and make the crystal p-type.

**P-2. SE2-F23 1(c) [6 pts], diode exponential: f(E) and its energy dependence**
> Explain, in terms of the Fermi distribution function and its dependence on energy, why the current in a pn junction diode increases exponentially with voltage $V$, for $V > 0$.

*Key:* "Fermi distribution function decreases exponentially with increasing energy. Increasing V>0 lowers barrier for carriers to traverse the pn junction by qV, and therefore exponentially increases the concentration of carriers with sufficient energy to cross the pn junction and contribute to current flow."

*Template:*
1. The Fermi distribution function is $f(E) = 1/(e^{(E-E_F)/k_BT}+1)\approx e^{-(E-E_F)/k_BT}$ for $E-E_F\gg k_BT$. The probability that a state is occupied decreases exponentially with increasing energy.
2. To cross the pn junction, an electron in the n-side conduction band (or a hole in the p-side valence band) must surmount the built-in barrier. Only the exponential tail of carriers with energy above the barrier can cross.
3. A forward voltage $V>0$ lowers the barrier by $qV$. That multiplies the concentration of carriers with sufficient energy to cross by $e^{qV/k_BT}$: $n_p = n_{p0}e^{qV/k_BT}$ and $p_n = p_{n0}e^{qV/k_BT}$.
4. The current is proportional to these injected carriers, $J=(A_1n_{p0}+A_2p_{n0})(e^{qV/k_BT}-1)$, so it rises exponentially with $V$.

*Optional sketch* (the stem allows one; not to scale, forward bias, n side grounded):
```
electron
energy       p side                    n side
  ^     Ec ───────────╮
  |                   │ q(Vbi − V)  ← barrier; V > 0 shrinks it
  |                   ╰──────────── Ec   ~~ electron tail, f ≈ e^{-(E-EF)/kT}
  |                        - - - - - EF,n
  |     EF,p - - - -                     (EF,n − EF,p = qV)
  |     Ev ───────────╮ oo hole tail, 1−f ≈ e^{-(EF-E)/kT}
  |                   │ q(Vbi − V)
  |                   ╰──────────── Ev
  +-----------------------------------------> x
```

**P-3. SE2-F24 1(b) [6 pts], acceptors move $E_F$ toward $E_v$**
> Explain why the introduction of acceptor atoms into a semiconductor crystal, e.g., B (3 valence electrons) into Si (4 valence electrons), causes the Fermi level to move closer to the valence-band edge energy of the semiconductor.

*Key:* "Acceptor removes electrons from/creates holes in the valence band; probably [sic] of finding empty states in the valence band increases, so Fermi level must move closer to valence band."

*Template:*
1. B has only 3 valence electrons. To complete its fourth bond it accepts an electron from the valence band, which leaves a fixed B⁻ ion and a mobile hole (an empty state) in the valence band. For $N_A\gg n_i$, $p\approx N_A$.
2. More empty valence-band states means that $1-f(E)$, the probability that a state near $E_v$ is empty, must increase.
3. Since $1-f(E)\approx e^{-(E_F-E)/k_BT}$, a larger $1-f$ at $E_v$ requires a smaller $E_F-E_v$. Explicitly, $p=N_ve^{-(E_F-E_v)/k_BT}=N_A$ gives $E_F-E_v=k_BT\ln(N_v/N_A)$, which shrinks as $N_A$ grows.
4. So $E_F$ moves from near mid-gap toward the valence-band edge. (Si example: $E_F-E_v$ falls from 0.553 eV intrinsic to 0.194 eV at $N_A=10^{16}$ cm$^{-3}$.)

**P-4. SE2-F24 1(c) [6 pts], diode exponential: mathematical form of f(E)**
> Explain, in terms of the mathematical form of the Fermi distribution function, why current in a pn junction diode increases exponentially with increasing voltage.

*Key:* "Energy barrier for carriers to diffuse across junction decreases with positive V, so from form of f(E) one can show that current increases exponentially."

*Template.* Lead with the math, because the stem says "mathematical form":
1. $f(E)=1/(e^{(E-E_F)/k_BT}+1)$. For energies several $k_BT$ above $E_F$, the $+1$ is negligible and $f(E)\approx e^{-(E-E_F)/k_BT}$, a pure exponential in energy.
2. Carriers diffuse across the junction only if their energy exceeds the barrier top $E_B$. Their concentration is $\int_{E_B}^\infty g_c f\,dE\propto e^{-(E_B-E_F)/k_BT}$.
3. Positive $V$ lowers the barrier, $E_B\to E_B-qV$, so this concentration becomes $e^{-(E_B-qV-E_F)/k_BT}=e^{-(E_B-E_F)/k_BT}\,e^{qV/k_BT}$. Holes work the same way, using $1-f(E)\approx e^{-(E_F-E)/k_BT}$.
4. The diffusion current is proportional to the excess carriers that cross: $J=J_s(e^{qV/k_BT}-1)$.

**P-5. FE-F24 1(e) [5 pts], Si vs Ge holes**
> Consider two different semiconductor materials, silicon and germanium, both of which have no dopants or defects, at room temperature. Silicon has an energy band gap of 1.12 eV, and germanium an energy band gap of 0.67 eV. Which semiconductor would you expect to have a higher concentration of holes in the valence band? Explain.

*Key:* "Germanium"

*Template:* Germanium.
1. With no dopants, holes exist only because electrons are thermally excited from the valence band across the gap into the conduction band, so $p=n=n_i$, and $E_F$ sits near mid-gap.
2. Then $p=N_ve^{-(E_F-E_v)/k_BT}\approx N_ve^{-E_g/2k_BT}$, equivalently $n_i=\sqrt{N_cN_v}\,e^{-E_g/2k_BT}$. This falls exponentially as the gap grows.
3. Assuming $N_c$ and $N_v$ are comparable for the two materials (state this assumption), the ratio is $e^{(1.12-0.67)/(2\times0.02585)}=e^{8.70}\approx6\times10^{3}$. Ge has thousands of times more holes.

**P-6. FE-F25 1(e) [5 pts], diode exponential: electrons and holes in the CB and VB**
> Explain, in terms of the behavior of electrons and holes in a semiconductor's conduction band and valence band, respectively, why current increases exponentially with increasing voltage across a forward-biased pn junction diode.

*Key:* see the verbatim FE-F25 answer in Exam intel above ("At forward bias, more electrons on the n-side have enough energy to surmount the built-in pn junction barrier ...").

*Template:*
1. Conduction-band electrons on the n side and valence-band holes on the p side are kept on their own sides by the built-in barrier at the junction.
2. Forward bias $V>0$ lowers that barrier by $qV$. More n-side electrons then have enough energy to surmount it and move to the p side, and more p-side holes have enough energy to move to the n side. These injected carriers diffuse away from the junction and carry the forward current.
3. The number able to cross is set by the Boltzmann tails: $f(E)\approx e^{-(E-E_F)/k_BT}$ well above $E_F$ for electrons, and $1-f(E)\approx e^{-(E_F-E)/k_BT}$ well below $E_F$ for holes. Lowering the barrier by $qV$ multiplies each population by $e^{qV/k_BT}$.
4. So $n_p=n_{p0}e^{qV/k_BT}$, $p_n=p_{n0}e^{qV/k_BT}$, and $J=(A_1n_{p0}+A_2p_{n0})(e^{qV/k_BT}-1)$.

*One answer for all three framings:* write P-6 and open it with sentence 1 of P-4. That single answer satisfies P-2, P-4 and P-6.

### Plausible new stems (same style; model answers)

> [!note] Added context. N1: dopant for p-type
> **Stem:** To create a p-type semiconductor from a crystal of pure Si, would you replace some of the Si atoms with Al (aluminum, 3 valence electrons/atom) or P (phosphorus, 5 valence electrons/atom)? Explain your answer.
> **Model answer:** Al.
> 1. Al has 3 valence electrons, one fewer than Si, so it can complete only three of its four bonds. It accepts an electron from a neighbouring bond, that is, from the valence band, to complete the fourth.
> 2. That leaves a fixed, negatively charged Al⁻ ion and a mobile hole in the valence band. Al is an acceptor, like B on ETY p3.
> 3. Each Al atom adds a hole without adding a conduction-band electron, so for $N_A\gg n_i$, $p\approx N_A\gg n=n_i^2/N_A$, and the crystal is p-type (ETY p4, case 3).
> 4. P is a donor and would make the crystal n-type.

> [!note] Added context. N2: donors move $E_F$ toward $E_c$
> **Stem:** Explain why the introduction of donor atoms, e.g., P (5 valence electrons) into Si (4 valence electrons), causes the Fermi level to move closer to the conduction-band edge.
> **Model answer:**
> 1. P's fifth valence electron is not needed for bonding. Its donor level $E_d$ lies just below $E_c$ (R5 p4), so the electron is easily donated into the conduction band, and $n\approx N_D$.
> 2. The probability that conduction-band states are occupied must therefore increase.
> 3. Since $f(E)\approx e^{-(E-E_F)/k_BT}$ above $E_F$, a larger $f$ near $E_c$ requires a smaller $E_c-E_F$. Explicitly, $n=N_ce^{-(E_c-E_F)/k_BT}=N_D$ gives $E_c-E_F=k_BT\ln(N_c/N_D)$.
> 4. Si example: $E_c-E_F$ falls from 0.567 eV intrinsic to 0.209 eV at $N_D=10^{16}$ cm$^{-3}$. $E_F$ moves up from mid-gap toward $E_c$, matching the TA's $E_{f,\text{new}}$ (R5 p4).

> [!note] Added context. N3: intrinsic $E_F$ at mid-gap
> **Stem:** Explain why the Fermi level in an undoped (intrinsic) semiconductor lies near the middle of the band gap. For Si, with $m_c^*=1.18\,m_e$ and $m_v^*=0.81\,m_e$, does it lie slightly above or slightly below mid-gap?
> **Model answer:**
> 1. In intrinsic material, every conduction-band electron came from the valence band, so $n=p$.
> 2. With $n=N_ce^{-(E_c-E_F)/k_BT}$ and $p=N_ve^{-(E_F-E_v)/k_BT}$, equal concentrations need nearly equal exponents. $E_F$ must therefore sit about equally far from $E_c$ and $E_v$, which is mid-gap.
> 3. Exactly, $E_c-E_F=\tfrac12E_g-\tfrac34k_BT\ln(m_v^*/m_c^*)$ (PS6 P4(a)). For Si, $\ln(0.81/1.18)<0$, so $E_c-E_F=0.5673$ eV $>E_g/2=0.56$ eV.
> 4. $E_F$ is 7.3 meV *below* mid-gap. The valence band has fewer states, so $E_F$ must sit slightly closer to it to give $p=n$.

> [!note] Added context. N4: why $n_i$ rises with $T$, and why that limits devices
> **Stem:** Explain, in terms of the Fermi distribution function, why the intrinsic carrier concentration of a semiconductor increases rapidly with temperature, and why this limits the temperature at which doped devices can operate.
> **Model answer:**
> 1. Intrinsic carriers exist only through thermal excitation across $E_g$. With $E_F$ near mid-gap, the occupancy of a state at $E_c$ is $f\approx e^{-E_g/2k_BT}$, so $n_i=\sqrt{N_cN_v}\,e^{-E_g/2k_BT}$. It rises exponentially as $T$ rises; the $T^{3/2}$ in $N_c$ and $N_v$ is minor.
> 2. Si numbers (PS6 constants, $E_g$ held fixed; python3): $n_i\approx9.5\times10^9$ cm$^{-3}$ at 300 K, $3.3\times10^{12}$ at 400 K, $1.2\times10^{14}$ at 500 K, $1.4\times10^{15}$ at 600 K.
> 3. Once $n_i$ approaches the dopant concentration, $n\approx p\approx n_i$ regardless of doping, and the n/p distinction that junctions depend on disappears. In Ed Yu's words (PS6 P4): "the ability to control electronic properties and current flow via doping is degraded or lost."

> [!note] Added context. N5: band gap vs intrinsic concentration (another material)
> **Stem:** GaAs has a band gap of 1.42 eV and Si a band gap of 1.12 eV. With no dopants, at room temperature, which has the higher concentration of electrons in the conduction band? Explain.
> **Model answer:** Si.
> 1. In undoped material, conduction-band electrons come only from thermal excitation across the gap, so $n=n_i\propto e^{-E_g/2k_BT}$.
> 2. Assuming comparable $N_c$ and $N_v$ (state this; the effective masses differ), the ratio of the exponential factors is $e^{-(1.42-1.12)/(2\times0.02585)}=3.0\times10^{-3}$.
> 3. GaAs therefore has hundreds of times fewer intrinsic electrons. A larger gap means an exponentially smaller occupied tail of $f(E)$ at $E_c$.

> [!note] Added context. N6: majority and minority concentrations (small math)
> **Stem:** Si at 300 K ($n_i=10^{10}$ cm$^{-3}$) is doped with $10^{16}$ cm$^{-3}$ As atoms. Estimate the electron and hole concentrations and explain.
> **Model answer:**
> 1. As is a donor and $N_D\gg n_i$, so $n\approx N_D=10^{16}$ cm$^{-3}$ (ETY p4, case 2).
> 2. In equilibrium $np=n_i^2$ (R5 p3), so $p=n_i^2/n=10^{20}/10^{16}=10^4$ cm$^{-3}$. Using PS6's $n_i=9.47\times10^9$ gives $8.98\times10^3$ cm$^{-3}$.
> 3. Doping raises $n$ by $10^6$ above $n_i$ and suppresses $p$ by the same factor. $E_F$ moved toward $E_c$, so $1-f$ in the valence band became exponentially smaller.

> [!note] Added context. N7: conductivity vs doping
> **Stem:** The donor concentration in an n-type Si resistor is increased from $10^{15}$ to $10^{17}$ cm$^{-3}$. How does its resistance change? Explain.
> **Model answer:** The resistance falls by about $100\times$.
> 1. $R=\rho\ell/A$ with $\rho=1/(nq\mu)$ (ETY p2). Resistivity is an intensive property set by the carrier concentration, the charge and the mobility.
> 2. In n-type material $n\approx N_D$, so raising $N_D$ by 100 raises $\sigma=nq\mu$ by about 100.
> 3. The "about" comes from mobility: assuming $\mu$ constant gives exactly 100. In practice $\mu$ drops somewhat at high doping because of ionized-impurity scattering, so the fall is a little less than 100.
> 4. With a typical $\mu_n\approx1350$ cm²/V·s (not from the sources), $\rho$ goes from 4.6 to 0.046 Ω·cm. Intrinsic Si is about $3.6\times10^5$ Ω·cm.

> [!note] Added context. N8: metals, semiconductors, insulators in band terms
> **Stem:** Explain, in terms of energy bands, why metals conduct electricity well, insulators essentially do not, and semiconductors fall in between.
> **Model answer:**
> 1. Carrying current requires electrons with empty states just above them, so that the field can change their energy and momentum.
> 2. In a metal the bands overlap ($E_g\lesssim0$, R5 p1–2). There are always partly filled states at $E_F$, and the metal conducts at any $T$.
> 3. In an insulator $E_g$ is several eV. The conduction-band occupancy, $f(E_c)\approx e^{-E_g/2k_BT}$, is negligible (about $10^{-76}$ for 9 eV at 300 K), and a completely full valence band carries no net current.
> 4. A semiconductor's gap of about 1 eV gives a small but nonzero thermal population ($e^{-E_g/2k_BT}\approx4\times10^{-10}$ for Si). Doping can then raise it by many orders of magnitude.

> [!note] Added context. N9: reverse bias
> **Stem:** What happens to the current in a pn junction diode when a negative voltage (reverse bias) is applied to the p-type terminal relative to the n-type terminal? Explain.
> **Model answer:**
> 1. Reverse bias raises the barrier by $q|V|$. The tail of majority carriers with enough energy to cross shrinks by $e^{-q|V|/k_BT}$ and becomes negligible within about 0.1 V.
> 2. In $J=(A_1n_{p0}+A_2p_{n0})(e^{qV/k_BT}-1)$, the exponential goes to 0, so $J\to-(A_1n_{p0}+A_2p_{n0})\equiv-J_s$.
> 3. The result is a small, voltage-independent reverse current, set by the minority-carrier concentrations $n_{p0}=n_i^2/N_A$ and $p_{n0}=n_i^2/N_D$ that are swept across the junction. At $V=-0.1$ V, $J/J_s=-0.979$; at $-0.2$ V, $-0.9996$.
> 4. Because $J_s\propto n_i^2$, the reverse current grows rapidly with temperature.

> [!note] Added context. N10: compensation (equal donors and acceptors)
> **Stem:** Pure Si is doped with equal concentrations of B and As. Is the result n-type, p-type, or neither? Explain.
> **Model answer:** Neither.
> 1. Ed Yu's handout states "If $N_D = N_A$, then $n = p = n_i$" (ETY p4).
> 2. Each As atom's extra electron fills the empty bond, or hole, of a B atom instead of going into the conduction band. The donors and acceptors compensate each other.
> 3. Only thermally generated carriers remain, $n=p=n_i$, and $E_F$ stays near mid-gap.
> 4. The crystal contains fixed As⁺ and B⁻ ions, but they do not move and carry no current.

> [!note] Added context. N11: what moves and what charge is left behind
> **Stem:** When a B atom replaces a Si atom in a Si crystal, a hole is created. What is the charge state of the B atom afterwards, and which of the two (hole or B atom) carries current? Explain.
> **Model answer:**
> 1. B accepts an electron to complete its fourth covalent bond, so it becomes a negatively charged B⁻ ion fixed in the lattice. Ed Yu crossed out "positively" and wrote "negatively" on ETY p3.
> 2. The hole it created is mobile, with charge $+q$, and carries the current.
> 3. Similarly, a donor P or As becomes a fixed positive ion and releases a mobile electron of charge $-q$.
> 4. Overall charge neutrality: $p-n+N_D^+-N_A^-=0$.

> [!note] Added context. N12: current per 60 mV (small math)
> **Stem:** At 300 K, by roughly what factor does the forward current of an ideal pn junction diode increase when the forward voltage increases by 60 mV? Explain using the Fermi distribution function.
> **Model answer:** About $10\times$.
> 1. For $qV\gg k_BT$, $J\approx J_se^{qV/k_BT}$, so the ratio is $J(V+\Delta V)/J(V)=e^{q\Delta V/k_BT}=e^{0.060/0.02585}=10.2$. Equivalently, the current rises one decade per $k_BT\ln10/q=59.5$ mV.
> 2. The exponential comes from the Boltzmann tail $f(E)\approx e^{-(E-E_F)/k_BT}$. Lowering the barrier by 0.060 eV admits carriers from a part of the tail that is $e^{2.32}\approx10$ times more populated.

---

## Problems worked

Ed Yu's PS6 solutions are posted, so these are full treatments. Every number below was re-run in python3.

**W1. R5 p3: electron concentration $n$ (the TA's derivation, the model for PS6 P3).**

> [!check]- Solution
> 1. Units first (R5 p3): $f(E)\cdot\text{DoS}$ has units $[\text{e}^-/\text{state}]\,[\text{states}/(E\cdot\text{vol})]$. Integrating over $E$ leaves electrons per volume.
> 2. Sum (states) × (probability filled) over the conduction band and use the Boltzmann tail for $f$:
> $$n=\int_{E_c}^{\infty}e^{-(E-E_f)/kT}\,\frac{\sqrt2}{\pi^2}\left(\frac{m_c^*}{\hbar^2}\right)^{3/2}(E-E_c)^{1/2}\,dE$$
> 3. Pull out the constant $Q=\frac{\sqrt2}{\pi^2}\left(\frac{m_c^*}{\hbar^2}\right)^{3/2}$. Substitute $u=E-E_c$, $du=dE$; the limits become $0\to\infty$:
> $$n=Q\int_0^\infty e^{-(u+E_c-E_f)/kT}u^{1/2}\,du=Q\,e^{-(E_c-E_f)/kT}\int_0^\infty e^{-u/kT}u^{1/2}\,du$$
> 4. The remaining integral is a gamma function: $\int_0^\infty e^{-u/kT}u^{1/2}du=\Gamma(3/2)(kT)^{3/2}=\frac{\sqrt\pi}{2}(k_BT)^{3/2}$.
> 5. Result:
> $$n=Q\,e^{-(E_c-E_f)/kT}\,\frac{\sqrt\pi}{2}(k_BT)^{3/2}=2\left(\frac{m_c^*k_BT}{2\pi\hbar^2}\right)^{3/2}e^{-(E_c-E_F)/k_BT}$$
> **Check (python3):** the prefactors agree, $\frac{\sqrt2}{\pi^2}\cdot\frac{\sqrt\pi}{2}=\frac{2}{(2\pi)^{3/2}}=0.12699$. The gamma integral at $k_BT=0.02585$ eV is $3.6835\times10^{-3}$ eV$^{3/2}$ both numerically and in closed form.
> **TA slip:** the R5 line "$\propto T^{3/2}/e^{-T}\Rightarrow T^{3/2}e^{T}$" is wrong. The correct dependence is $n\propto T^{3/2}e^{-(E_c-E_F)/k_BT}$.

**W2. PS6 P3: hole concentration $p$ (Ed Yu's method).**

> [!check]- Solution (PS6 sol p3)
> 1. Start from the definition with the valence-band DoS:
> $$p=\int_{-\infty}^{E_v}g_v(E)[1-f(E)]\,dE=\frac{\sqrt2}{\pi^2}\left(\frac{m_v^*}{\hbar^2}\right)^{3/2}\int_{-\infty}^{E_v}(E_v-E)^{1/2}\left[1-\frac{1}{e^{(E-E_F)/k_BT}+1}\right]dE$$
> 2. Substitute $u=E_v-E$, $du=-dE$. The minus sign flips the limits to $0\to\infty$:
> $$p=\frac{\sqrt2}{\pi^2}\left(\frac{m_v^*}{\hbar^2}\right)^{3/2}\int_0^\infty u^{1/2}\left[1-\frac{1}{e^{(E_v-E_F)/k_BT}e^{-u/k_BT}+1}\right]du$$
> 3. Since $(E_F-E_v)\gg k_BT$, the quantity $x=e^{-(E_F-E_v)/k_BT}e^{-u/k_BT}\ll1$. Use $\frac{1}{1+x}\approx1-x$, so the bracket becomes $1-(1-x)=x$:
> $$p=\frac{\sqrt2}{\pi^2}\left(\frac{m_v^*}{\hbar^2}\right)^{3/2}e^{-(E_F-E_v)/k_BT}\int_0^\infty u^{1/2}e^{-u/k_BT}\,du$$
> 4. The integral is the same gamma integral as in recitation, $\frac{\sqrt\pi}{2}(k_BT)^{3/2}$. Collecting the constants (same identity as W1):
> $$\boxed{p=2\left(\frac{m_v^*k_BT}{2\pi\hbar^2}\right)^{3/2}e^{-(E_F-E_v)/k_BT}}$$

**W3. PS6 P4(a): where $E_F$ sits when $n=p$.**

> [!check]- Solution (PS6 sol p4)
> 1. Set $n=p$. The common factor $2(k_BT/2\pi\hbar^2)^{3/2}$ cancels:
> $$(m_c^*)^{3/2}e^{-(E_c-E_F)/k_BT}=(m_v^*)^{3/2}e^{-(E_F-E_v)/k_BT}$$
> 2. Multiply both sides by $e^{-(E_c-E_F)/k_BT}$ and divide by $(m_c^*)^{3/2}$. On the right, the exponents add to $-(E_c-E_v)/k_BT$:
> $$e^{-2(E_c-E_F)/k_BT}=\left(\frac{m_v^*}{m_c^*}\right)^{3/2}e^{-(E_c-E_v)/k_BT}$$
> 3. Take the natural log of both sides:
> $$-\frac{2}{k_BT}(E_c-E_F)=-\frac{E_c-E_v}{k_BT}+\frac32\ln\frac{m_v^*}{m_c^*}$$
> 4. Solve for $E_c-E_F$, using $E_g=E_c-E_v$:
> $$\boxed{E_c-E_F=\tfrac12E_g-\tfrac34k_BT\ln\!\left(\frac{m_v^*}{m_c^*}\right)}$$

**W4. PS6 P4(b): $n_i$ for Si at 300 K.**

> [!check]- Solution (PS6 sol p4)
> 1. Fermi level: $E_c-E_F=\tfrac12(1.12)-\tfrac34(8.617\times10^{-5})(300)\ln(0.81/1.18)$. Here $\ln(0.81/1.18)=-0.3762$ and $k_BT=0.025851$ eV, so the second term is $+0.0073$ eV. Result: $E_c-E_F=0.5673$ eV.
> 2. Electron prefactor. Ed Yu uses SI units here, with $k_B=1.381\times10^{-23}$ J/K:
> $$N_c=2\left(\frac{1.18(9.11\times10^{-31})(1.381\times10^{-23})(300)}{2\pi(1.055\times10^{-34})^2}\right)^{3/2}=3.214\times10^{25}\ \text{m}^{-3}$$
> 3. Electron concentration: $n=N_c\,e^{-0.5673/0.025851}=3.214\times10^{25}\times e^{-21.945}=9.473\times10^{15}$ m$^{-3}$ $=9.473\times10^{9}$ cm$^{-3}$.
> 4. Hole side: $N_v=1.828\times10^{25}$ m$^{-3}$ and $E_F-E_v=1.12-0.5673=0.5527$ eV, so $p=9.477\times10^{15}$ m$^{-3}$ $=9.477\times10^{9}$ cm$^{-3}$.
> 5. Answer: $n=p=n_i\approx9.47\times10^{9}$ cm$^{-3}$.
> **Check (python3):** without rounding $E_c-E_F$ to 0.5673, both $n$ and $p$ come out to $9.475\times10^{15}$ m$^{-3}$. The 0.004 spread in the key comes only from that rounding. The rounding-free route is $n_i=\sqrt{N_cN_v}e^{-E_g/2k_BT}$, which gives the same $9.475\times10^{9}$ cm$^{-3}$.
> **Unit trap:** the SI result is in m$^{-3}$. Divide by $10^6$ to get cm$^{-3}$.

**W5. PS6 P5: simplified ideal diode equation.**

> [!check]- Solution (PS6 sol p5)
> **Band diagram (from class):** $V$ is applied to the p side, with the n side grounded. $E_c$ and $E_v$ are high and flat on the p side, step down through the junction, and are lower and flat on the n side. The two quasi-Fermi levels are separated by $E_{F,n}-E_{F,p}=eV$. The electron concentration on the p side is $n_p$; the hole concentration on the n side is $p_n$.
> 1. Following the hint, $n_p$ (electrons at the p-side $E_c$) is set by the n-side Fermi level $E_{F,n}$:
> $$n_p=2\left(\frac{m_c^*k_BT}{2\pi\hbar^2}\right)^{3/2}e^{-(E_c-E_{F,n})/k_BT}$$
> 2. Write $E_{F,n}=E_{F,p}+eV$ and split the exponential:
> $$n_p=2\left(\frac{m_c^*k_BT}{2\pi\hbar^2}\right)^{3/2}e^{-(E_c-E_{F,p})/k_BT}\,e^{eV/k_BT}=n_{p0}\,e^{eV/k_BT}$$
> The first factor is the equilibrium value $n_{p0}$: the p-side bulk keeps the same $E_c-E_{F,p}$ it had at $V=0$.
> 3. Holes are the mirror image. $p_n$ is set by the p-side Fermi level:
> $$p_n=2\left(\frac{m_v^*k_BT}{2\pi\hbar^2}\right)^{3/2}e^{-(E_{F,p}-E_v)/k_BT}=2\left(\frac{m_v^*k_BT}{2\pi\hbar^2}\right)^{3/2}e^{-(E_{F,n}-E_v)/k_BT}e^{(E_{F,n}-E_{F,p})/k_BT}=p_{n0}\,e^{eV/k_BT}$$
> 4. Substitute into the current model and factor:
> $$J(V)=A_1(n_p-n_{p0})+A_2(p_n-p_{n0})=A_1n_{p0}(e^{eV/k_BT}-1)+A_2p_{n0}(e^{eV/k_BT}-1)$$
> $$\boxed{J(V)=(A_1n_{p0}+A_2p_{n0})(e^{eV/k_BT}-1)}$$
> The problem statement writes $q$ where the solution writes $e$; both mean the magnitude of the electron charge.

**W6. PS6 P6: dimensional analysis to the standard ideal diode equation.**

> [!check]- Solution (PS6 sol p6–7)
> **(a)** $J$ is in A/m² $=$ C/(s·m²), and $n_{p0}$, $p_{n0}$ are in m$^{-3}$. So $[A_1]=[A_2]=$ **C·m/s**.
> **(b)** From $J_{diff}=-qD\nabla n$: $[\text{C/(s·m}^2)]=[\text{C}][D][\text{m}^{-1}][\text{m}^{-3}]$, so $[D]=$ **m²/s**.
> **(c)** The coulombs must come from $q$. The only way to build metres from $D$ and $\tau$ is $\sqrt{D\tau}$. Seconds come from $\tau$. So
> $$A=\pm q\sqrt{D\tau}/\tau=\pm q\sqrt{D/\tau}.$$
> Check: C·$\sqrt{(\text{m}^2/\text{s})/\text{s}}$ = C·m/s ✓.
> **(d)** $L_n=\sqrt{D_n\tau_n}$ and $L_p=\sqrt{D_p\tau_p}$ (units m ✓).
> **(e)** $A=\pm q\sqrt{D/\tau}=\pm qD/\sqrt{D\tau}=\pm qD/L$.
> **Sign (p7, "not necessary for full credit"):** electrons are injected from the n side to the p side and diffuse left; holes are injected from p to n and diffuse right. Both give electric current from left to right for $V>0$, so $A_1,A_2>0$:
> $$J(V)=e\left(\frac{D_n}{L_n}n_{p0}+\frac{D_p}{L_p}p_{n0}\right)\left(e^{eV/k_BT}-1\right)$$

**W7. Drill numbers for "a small amount of math".**

> [!note] Added context (computed with python3 from the PS6 constants; not in the sources)
> | Doping (cm$^{-3}$) | Minority concentration (cm$^{-3}$) | Fermi level position |
> |---|---|---|
> | $N_D=10^{15}$ | $p=9.0\times10^4$ | $E_c-E_F=0.268$ eV |
> | $N_D=10^{16}$ | $p=9.0\times10^3$ | $E_c-E_F=0.209$ eV ($E_F-E_i=0.359$ eV) |
> | $N_D=10^{17}$ | $p=9.0\times10^2$ | $E_c-E_F=0.149$ eV |
> | $N_A=10^{16}$ | $n=9.0\times10^3$ | $E_F-E_v=0.194$ eV |
> | intrinsic | $n=p=9.47\times10^9$ | $E_c-E_F=0.567$ eV |
>
> Diode factors: $e^{qV/k_BT}=48$ at 0.1 V, $1.1\times10^5$ at 0.3 V and $1.2\times10^{10}$ at 0.6 V.

---

## Traps & emphasis

1. **Dopant ion charges.** B becomes B⁻ and P/As become P⁺/As⁺. These ions are fixed; the hole ($+q$) and the electron ($-q$) are what move. Ed Yu himself first wrote "positively charged B ion" and corrected it to "negatively" (ETY p3).
2. **Band bookkeeping.** Electrons live in the conduction band and holes in the valence band. $n$ integrates $f\cdot g_c$ upward from $E_c$; $p$ integrates $(1-f)\cdot g_v$ downward from $E_v$. The FE-F25 stem is built on this "respectively".
3. **$E_F$ moves toward the band of the majority carrier.** Donors push it toward $E_c$ and acceptors toward $E_v$. The reason is always stated through $f$ or $1-f$ (the SE2-F24 key: "probability of finding empty states in the valence band increases").
4. **$f(E_F)=1/2$ at every temperature.** The Boltzmann tail requires $\lvert E-E_F\rvert\gg k_BT$; it is 5% off at $3\,k_BT$ and 100% off at $E_F$.
5. **The diode answer has two halves, and both are needed:** (i) $f$ decays exponentially in energy; (ii) $V>0$ lowers the barrier by $qV$. If the stem says "electrons and holes", cover both sides of the junction. If it says "mathematical form", write $f(E)$.
6. **Write $e^{qV/k_BT}-1$, not $e^{qV/k_BT}$**, when you give $J(V)$. The $-1$ is what makes $J(0)=0$ and gives $J\to-J_s$ under reverse bias.
7. **$np=n_i^2$ holds only in equilibrium.** Under bias, the injected minority concentrations carry the factor $e^{qV/k_BT}$.
8. **Units.** $n_i$ is $9.47\times10^{15}$ m$^{-3}$ $=9.47\times10^{9}$ cm$^{-3}$. When $\hbar$ and $m$ are in SI, $k_B$ must be in J/K (1.381e-23). Exponents need $k_BT$ in the same units as the energies (0.02585 eV).
9. **Assumptions must be stated.** In a material comparison (Si vs Ge), write "assuming comparable $N_c,N_v$". This is the exam's own rule.
10. **What not to study.** MOSFETs are "not necessary for ECE 411" (ETY p4). The DoS integrals and dimensional analysis are PS6-level, not P1-level, so far. P1 uses only their *results*.

---

## Conflicts

| # | Item | Recitation (TA) | Handout (ETY) | Keys / PS6 | Resolution |
|---|---|---|---|---|---|
| 1 | $n_i$, Si, 300 K | not stated | $\approx1\times10^{10}$ cm$^{-3}$ (p3) | $9.47\times10^{9}$ cm$^{-3}$ (PS6 sol p4) | Both are correct to rounding; python3 gives $9.475\times10^9$ from the PS6 constants. Use whatever value a stem gives; otherwise $10^{10}$. |
| 2 | $k_BT$ at 300 K | 0.026 eV (p2) | not stated | $8.617\times10^{-5}\times300=0.02585$ eV (sol p4) | Same value. Use 0.0259 when precision matters. |
| 3 | Charge symbol | not used | $q$ (p1) | PS6 P5: $q$, $e^{qV/k_BT}$; PS6 sol: $e$, $e^{eV/k_BT}$; SE2-F23 key: "by qV" | All mean $1.602\times10^{-19}$ C. Write $q$ to match the stems. |
| 4 | Fermi-level symbol | $E_f$, $E_{f,\text{new}}$ | not used | $E_F$; quasi-levels $E_{F,n}$, $E_{F,p}$ (sol p5) | Notation only. |
| 5 | Effective mass | $m_c^*$, $m_v^*$; pasted $p$ formula uses $m_v$ (no star) | not used | $m_c^*$, $m_v^*$ | Same quantity. |
| 6 | Boltzmann step | approximates $f$ directly, for $E-E_f\gg k_BT$ (p2) | n/a | approximates $1-f$ via $\frac{1}{1+x}\approx1-x$, for $(E_F-E_v)\gg k_BT$ (sol p3) | Same result. |
| 7 | Substitution | $u=E-E_c$, $du=dE$ (for $n$) | n/a | $u=E_v-E$, $du=-dE$ (for $p$; limits flip) | Mirror images. |
| 8 | Temperature dependence | "$\propto T^{3/2}/e^{-T}\Rightarrow T^{3/2}e^{T}$" (p3) | n/a | not stated | **R5 is wrong.** The correct form is $n\propto T^{3/2}e^{-(E_c-E_F)/k_BT}$ and $n_i\propto T^{3/2}e^{-E_g/2k_BT}$. |
| 9 | Insulator band gap | "$\gtrsim$ (10 keV)?" (p2, with the TA's own question mark) | n/a | n/a | **R5 is wrong by about 10³.** Insulator gaps are several eV (added: diamond about 5.5 eV, SiO₂ about 9 eV). |
| 10 | Constants list | "$E_f = 1.12$ eV" (p3) | n/a | $E_g=1.12$ eV (PS6 P4(b)) | R5 mislabels the band gap as $E_f$. |
| 11 | Donor picture | donor level $E_d$ just below $E_c$, small ionization gap "$E_{g2}$", $E_{f,\text{new}}$ just below $E_d$ (p4) | bond picture: P "can donate an electron to the semiconductor crystal" (p3) | SE2-F23 key: extra electron "will occupy a state in the conduction band" | Consistent; the key compresses the ionization step. Use band language on the exam. |
| 12 | Barrier mechanism | not covered | not covered | SE2-F23/F24 keys: barrier lowered by $qV$. FE-F25 key: "surmount the built-in pn junction barrier" plus $f$ and $1-f$. PS6 sol p5: $E_{F,n}-E_{F,p}=eV$. | Same physics, two pictures. The barrier picture is the exam answer; the quasi-Fermi-level picture is the derivation. |
| 13 | Wording in the FE-F25 key | n/a | n/a | $f$ and $1-f$ "depend approximately exponentially on voltage/kT" | Read this as $qV/k_BT$; dimensionally it must be an energy over $k_BT$. |
| 14 | Concentration units | "/cc" | m$^{-3}$ for $N_D$, $N_A$, $n$, $p$ (p4); $n_i$ in cm$^{-3}$ (p3) | PS6 sol: m$^{-3}$, then converted to cm$^{-3}$ | Watch the factor of $10^6$. |
| 15 | Si atom density | $N_{Si}=10^{22}$ atom/cc (p4) | n/a | n/a | Order of magnitude only (added: $5.0\times10^{22}$ cm$^{-3}$). |
| 16 | PS6 P5 statement | n/a | n/a | "$p_n = p_n(V{=}0)$" | Typo for $p_{n0}=p_n(V{=}0)$. |
| 17 | Sign of $A_1$, $A_2$ | n/a | n/a | "$\pm$" in sol p6(c, e); "$+$" on sol p7 | Positive for the p-to-n current convention. |
| 18 | SE2-F24 1(b) key | n/a | n/a | "probably" | Read as "probability". |
| 19 | TA's $f(E)$ sketches | in the $n$/$p$ panels (p3), $f$ is still near its knee at $E_c$, and $1-f$ near $E_v$ | n/a | n/a | Not to scale. In a non-degenerate semiconductor $E_F$ is many $k_BT$ from both edges, so $f(E_c)\ll1$. The lobe shapes are still right. |
| 20 | PS6 sol p5 figure, as transcribed | n/a | n/a | the transcript places "$E_{F,p}$ ... slightly below the p-side $E_c$ region" | That is inconsistent with p-type material, where $E_{F,p}$ should be near $E_v$ on the p side. I could not check the PDF (outside my render allowance). The algebra only uses $E_{F,n}-E_{F,p}=eV$ and is unaffected. |

---

## Top 5 takeaways

1. **Have the diode-exponential answer ready in 4 sentences.** It was on 3 of the 4 exams in my inputs, and it was part (c) on both SE2s. The chain: $f(E)\approx e^{-(E-E_F)/k_BT}$ (and $1-f$ for holes) → electrons and holes must surmount the built-in barrier → $V>0$ lowers the barrier by $qV$ → the population that can cross grows by $e^{qV/k_BT}$ → $J=(A_1n_{p0}+A_2p_{n0})(e^{qV/k_BT}-1)$. Cover both carriers, and write $f(E)$ explicitly.
2. **For doping, go from valence count to band to $E_F$.**
   - 5 valence electrons (P, As): donor, electron into the conduction band, n-type, $E_F$ toward $E_c$.
   - 3 valence electrons (B, Al): acceptor, takes an electron from the valence band, hole, p-type, $E_F$ toward $E_v$.
   - Back each with $E_c-E_F=k_BT\ln(N_c/N_D)$ or $E_F-E_v=k_BT\ln(N_v/N_A)$, and know which ion is left behind (B⁻, P⁺).
3. **$n_i=\sqrt{N_cN_v}\,e^{-E_g/2k_BT}$ ($\approx10^{10}$ cm$^{-3}$ for Si at 300 K).** A smaller gap or a higher $T$ means exponentially more carriers (Ge has about 6000× more than Si). In equilibrium $np=n_i^2$, so the minority concentration is $n_i^2/N$.
4. **Write the four statistics facts cold:** $f(E)=1/(e^{(E-E_F)/k_BT}+1)$; $f(E_F)=1/2$; the Boltzmann tail applies when $\lvert E-E_F\rvert\gg k_BT$; and $n=N_ce^{-(E_c-E_F)/k_BT}$, $p=N_ve^{-(E_F-E_v)/k_BT}$.
5. **Answer format:** choice, then mechanism, then one formula, in 3–4 sentences, using the keys' vocabulary ("Fermi distribution function", "barrier lowered by qV", "carriers with sufficient energy", "empty states in the valence band"). State any assumption. A band-diagram sketch is allowed.
