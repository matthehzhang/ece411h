---
course: ECE 411H
kind: exam-intel
exam: Semester Exam 2 (F26), Wed 2026-11-11 09:00, in class
written: 2026-11-06
inputs: F23 + F24 Exam 2 papers and keys; F23/F24/F25 finals and keys (item pool only); F26 SE2 answer template; SE1 F26 graded exam, key, histogram; Semester Exam 1 details.txt; problem_set_tips_F26; Discord scrape 2026-11-06
excluded: F25 Exam 2 questions/key/transcripts (reserved mock), Transcripts/INDEX.md, .tutor/, lectures, syllabus PDF, everything else
tags: [ece411, exam2, exam-intel]
---

# Exam Intel: ECE 411H Semester Exam 2 (F26)

> [!summary] Bottom line
> - **Format:** 4 problems × 25 pts, 70 min + ~5 min scan/upload, closed book, calculator only. F26 template: P1 a–d, P2 a–c, P3 a–e, P4 a–e. P1 has been 6/6/6/7 on every Semester Exam on disk.
> - **Skeleton (F23 and F24 identical):** P1 = four conceptual items (two semiconductor, two series-RLC filter / Q). P2 = design-to-spec or maximum power transfer. P3 and P4 = one passive filter and one op-amp filter, each asking for $\mathbf H(\omega)$ in factored standard form plus Bode magnitude and phase "as done in class". Neither Exam 2 had any Laplace.
> - **Point sinks:** maximum power transfer to a reactive multi-element load (F24 P2, 15.7/25 = 63%, the worst problem on either Exam 2) and op-amp filters (F23 P3 18.2, F24 P4 17.8, F24 final P3 15.1).
> - **F24 Exam 2 as the Monday full mock:** usable. No Laplace, every part in Exam-2 scope. It has fewer parts than the F26 template (9 vs 13 parts in P2–P4) and its P3 was the easiest problem in the record (23.3/25), so it will understate time pressure. Details in §8.
> - **Verification:** every numeric answer in the five keys was recomputed with sympy/scipy. Two real discrepancies (F24 final P3d bandwidth 200.3 vs 200.0 rad/s; F23 final P4a amplitude 1.2136 vs 1.2141) and one transcript error (F23 final Circuit FE-4 topology) are logged in §11.

---

## 1. Format, rules, and what the Bode stems demand

### 1.1 Logistics

| Item | Value | Evidence |
|---|---|---|
| Date | Wed 11 Nov 2026, class period (MW 9:00–10:30, ECJ 1.222) | F26 SE2 template header "11 November 2026"; `Semester Exam 1 details.txt` |
| Time | 70 min writing, then ~5 min to scan and upload to Gradescope (syllabus: "75 minutes each", as quoted in Exam 1 details) | template p.1 |
| Structure | 4 problems × 25 = 100 | F23 SE2, F24 SE2, SE1 F26 |
| P1 part points | **6 / 6 / 6 / 7** on F23 SE2, F24 SE2, SE1 F26 (also F23 final). F24 and F25 finals used 5 × 5 | papers |
| P2–P4 part points | Not printed. Gradescope assigns unequal part weights: on SE1 F26 they were P2 7/9/9, P3 8/6/5/6, P4 4/6/10/5 + 5 bonus | `SE1_F26_graded_Matthew.md` |
| Allowed | Exam questions, answer sheets, calculator. The Exam 1 announcement also lists writing implements and erasers. No formula sheet. **No Laplace handout:** every final says "exam questions and appended Laplace transform handout"; F23 SE2, F24 SE2 and the F26 SE2 template do not mention one | template p.1; finals p.1 |
| Bonus | SE1 F26 had a +5 bonus (4e). Neither F23 nor F24 Exam 2 had one | papers |
| Pace | 0.7 min per point: 17.5 min per problem, about 4 min per 6-pt P1 part | arithmetic |

### 1.2 Cover-page rules (F26 template p.1, same text as F23/F24 except the last line)

- "PLEASE ATTEMPT ALL PROBLEMS AND SHOW ALL WORK!" Write solutions in the spaces provided. The back of each page is scratch and "ONLY THE FRONT SIDE OF EACH SHEET WILL BE GRADED."
- Exam questions, answer sheets and a calculator are allowed. No other materials and no communication.
- Numbers are known to **3 significant figures** unless stated, so calculate to 3 s.f. Many problems override this with "All numerical values given in this problem are exact". Report final answers to 3 s.f. anyway.
- "You must show all of your work to receive credit." "If you need to make an assumption to answer a question, state it explicitly."
- New on SE1/SE2 F26 templates: "IMPORTANT: FOR SOME PROBLEMS, THE PROBLEM 'BOXES' CONTINUE FROM ONE PAGE TO THE NEXT. BE SURE TO WRITE YOUR ANSWERS IN THE CORRECT PROBLEM BOX!"

### 1.3 F26 Exam 2 answer template (20 pages, viewed page by page)

| Template page | Box |
|---|---|
| 1 | Header + P1(a), half page |
| 2 | P1(b) and P1(c), half page each |
| 3 | P1(d), full page |
| 4 / 5 / 6 | P2(a) / P2(b) / P2(c), one page each |
| 7 / 8 / 9 | P3(a) / P3(b) / P3(c), one page each |
| 10–11 | P3(d), 1.5 pages ("CONTINUED" on p.11 top half) |
| 11–12 | P3(e), 1.5 pages (p.11 bottom half + p.12) |
| 13 / 14 / 15 / 16 | P4(a) / (b) / (c) / (d), one page each |
| 17–18 | P4(e), 2 pages |
| 19–20 | "ADDITIONAL WORK FOR ANY PROBLEM – BE SURE TO LABEL THE PROBLEM NUMBER AND PART CLEARLY!" |

- Pages 1–3 have the same layout as the SE1 F26 template, where P1 was 6/6/6/7 with (d) the 7-pointer. Expect the same on Exam 2.
- Part counts compared with past papers: F23 had P2 a–c, P3 a–c, P4 a–d; F24 had P2 a–b, P3 a–c, P4 a–d. **F26 has 5 parts each in P3 and P4**, more than either previous Exam 2.
- Inference (?): the continued boxes (P3 d, P3 e, P4 e) mark the longest work. On past Exam 2s the long items were a pair of Bode plots or a multi-step derivation (Butterworth ratio, max-power values). The SE1 F26 template continued 4(a) and 4(c), and 4(c) was the 10-pt part, so a continued box is a weak signal of high weight.

### 1.4 Upload procedure (from Exam 1; assumed unchanged (?))

1. Bring a blank printed copy of the template (on disk: `Exams/F26/ECE 411H Semester Exam 2 template F26.pdf`).
2. Write on it, front sides only.
3. In the ~5 min after time is called, scan every page and upload to Gradescope.
4. The question sheet is handed out in class and can be kept.

Gradescope grades each template box as a separate question (SE1 F26 had 16 graded questions, one per part). Work written in the wrong box can be missed, and anything on the "additional work" pages must be labelled.

### 1.5 Bode-plot instructions, verbatim fragments from the stems

| Phrase | Where |
|---|---|
| "using linear approximations as done in class" | F23 SE2 P3b, P4b; F24 FE P2a,b, P3b |
| "using linear approximations for low and high frequencies as done in class" | F24 SE2 P3c, P4c |
| "label the key values on the vertical and horizontal axes of each plot" | all Bode parts |
| "any nonzero slopes in BOTH the Bode magnitude plot and the Bode phase plot" | F23 SE2 P3b (phase slopes graded) |
| "any nonzero slopes in the Bode magnitude plot" | F23 SE2 P4b; F24 SE2 P3c, P4c; F24 FE P2 |
| "all angles should be plotted in the range $-180° \le \phi \le 180°$" | F24 SE2 P3c, P4c |
| "$-180° \le \phi(\omega) < 180°$" | F25 FE P3c |
| "$0° \le \phi(\omega) < 360°$" | F24 FE P3b |
| "key values … expressed in terms of (as needed) $R_1$, $R_2$, $R_3$, $C_1$, and $C_2$, and the numerical values of any nonzero slopes" | F24 FE P3b (symbolic axes allowed) |

What the keys draw:
- **Magnitude:** straight-line asymptotes with corners labelled numerically (e.g. $10^4$, $10^5$) or symbolically ($\omega_p = 1/\sqrt{R_1C_1R_2C_2}$). Plateau levels are labelled (20 dB, 0 dB) and every slope is written as "±20 dB/dec" or "±40 dB/decade".
- **Phase:** a simple pole or zero ramps at ∓45°/dec from $0.1\omega_c$ to $10\omega_c$. A quadratic factor ramps at ∓90°/dec from $0.1\omega_0$ to $10\omega_0$. Overlapping ramps are summed and drawn as separate segments (F23 P3: −45, −90, −45 °/dec).
- **Band-pass peaks:** the keys plot the peak at the **exact** $\lvert\mathbf H(\omega_0)\rvert$, not at the intersection of the asymptotes (see §5.4 and §11).

---

## 2. Every problem, every year

Chapter references are to Ulaby/Maharbiz/Furse, *Circuit Analysis and Design*. Ch. 12 = Laplace is confirmed by the handout's "Table 12-1/12-3". Ch. 9 = frequency response and filters is inferred from PS8 numbering (9.26, 9.38, …). Ch. 8 = AC power and maximum power transfer is (?). Semiconductor items come from the course's own semiconductor unit (TA Recitation 5 on 10-12 covered it; PS6), not from Ulaby (?).

P1 stems are reproduced here and again in the short-answer bank (§10).

### 2.1 F23 Semester Exam 2 (08 Nov 2023), n = 66, mean 77.2

**P1 [25]** Shared instruction: "Answer the questions below. Each should require a few sentences or relatively small amount of math at most. You may also include a sketch/picture if necessary."

| Part | Stem (verbatim) | Topic | Key answer (verified) | Type |
|---|---|---|---|---|
| (a) [6] | "Recall that the quality factor $Q$ of a filter is given by $Q = 2\pi(W_{stored}/W_{dissipated})\vert_{\omega=\omega_0}$. Based on this definition of $Q$, does a very small value of $R$ in an RLC series filter circuit lead to a high or low value for $Q$? Explain." | Q, resonance (Ch. 9) | High Q. R is the only dissipator, so small R shrinks the denominator. | conceptual |
| (b) [6] | "To create an n-type semiconductor from a crystal of pure Si, would you replace some of the Si atoms with B (boron, 3 valence electrons/atom) or As (arsenic, 5 valence electrons/atom)? Explain your answer." | doping | As. Its extra valence electron occupies a conduction-band state. | conceptual |
| (c) [6] | "Explain, in terms of the Fermi distribution function and its dependence on energy, why the current in a pn junction diode increases exponentially with voltage $V$, for $V > 0$." | Fermi function, diode | $f(E)$ falls exponentially with energy. $V>0$ lowers the barrier by $qV$, so the population able to cross grows exponentially. | conceptual |
| (d) [7] | "In a series RLC filter circuit, across which single component ($R$, $L$, or $C$) should the output terminals be connected to create a band pass filter? Explain your answer." | series RLC by output element (Ch. 9) | R. By voltage division, C takes the input at low ω and L at high ω, so $V_R$ peaks in between. | conceptual |

**P2 [25] Filter design with an unknown shunt element.** "Consider Circuit SE2-2 shown at right. All numerical values given in this problem are exact."
- **Figure SE2-2:** voltage source $\mathbf V_s$ (+ on top) at left. A series resistor $R = 100\,\Omega$ runs on the top rail from the source + to the top node. A box labelled $\mathbf Z$ runs from the top node down to the bottom rail, which returns to source −. Open output terminals at the right are across $\mathbf Z$ ($\mathbf V_{out}$, + top, − bottom). This is a series-R, shunt-Z voltage divider with the output across Z.
- (a) "Suppose for this part of the problem that the circuit element $\mathbf Z$ in Circuit SE2-2 consists of a single component, i.e., a resistor, a capacitor, or an inductor. For the circuit to function as a high-pass filter with corner frequency $\omega_c = 1000$ rad/s, what type of component should $\mathbf Z$ be (resistor, capacitor, or inductor), and what should its value be?"
- (b) "Now suppose that $\mathbf Z$ consists of 2 individual components connected in series with each other. For the circuit to function as a band-reject filter, what should those components be (choose two from resistor, capacitor, and inductor). Explain your answer."
- (c) "For the two components you chose in part (b), compute numerical values of the components that will yield $\mathbf V_{out} = 0$ at $\omega = 2000$ rad/s. Are there other component values for which $\mathbf V_{out} = 0$ as well? Explain why or why not."
- **Topic:** passive filter design to a spec; series-LC notch (Ch. 9).
- **Skills:** pick the element from its limiting impedance; $\omega_c = R/L$ for an RL divider; series-LC branch impedance $j(\omega L - 1/\omega C)$; $\omega_0 = 1/\sqrt{LC}$.
- **Verified answers:**
  - (a) Inductor, $L = R/\omega_c = 0.1$ H, since $\mathbf H = j\omega L/(R + j\omega L)$.
  - (b) Capacitor and inductor in series.
  - (c) Any pair with $LC = 1/\omega^2 = 2.5\times10^{-7}\ \text{s}^2$, e.g. $C = 2.5\ \mu$F with $L = 0.1$ H. Only the product is fixed, so infinitely many pairs work.
- **How the key answers (b):** "Most of the input voltage will be across C at low frequencies, and across L at high frequencies, leading to a minimum in transfer function at intermediate frequencies." (A resistor in the branch would keep $\mathbf V_{out} \ne 0$ at the notch.)
- **Type:** (a) and (c) computational, (b) and the (c) follow-up conceptual. Class average 19.5/25.

**P3 [25] Inverting op-amp filter, second-order high-pass with gain.** "Consider Circuit SE2-3 shown at right. All the numerical values given in this problem are exact, and the op amp is always in its linear region of behavior."
- **Figure SE2-3:**
  - Source $\mathbf V_s$ (+ top, − grounded) feeds a series $R_s$, then a series $C_s$, into the op-amp inverting (−) input.
  - The non-inverting (+) input is grounded. Supplies are labelled $+V_{cc}$ and $-V_{cc}$.
  - Feedback from output to − input: $R_f$ (upper branch) **in parallel with** $L_f$ (lower branch).
  - $\mathbf V_{out}$ is taken from the op-amp output (+) to ground (−).
- (a) "Calculate the transfer function $\mathbf H(\omega) = \mathbf V_{out}/\mathbf V_s$ in terms of $R_s$, $C_s$, $R_f$, $L_f$, and $\omega$. Your answer should be in an algebraic form that makes it very straightforward to identify the factors corresponding to any zeros or poles that are present."
- (b) "Suppose $R_s = 100\,\Omega$, $C_s = 1\,\mu$F, $R_f = 1\,\text{k}\Omega$, and $L_f = 10$ mH. Construct the Bode magnitude and phase plots for this circuit, using linear approximations as done in class. Be sure to label the key values on the vertical and horizontal axes of each plot, and any nonzero slopes in BOTH the Bode magnitude plot and the Bode phase plot."
- (c) "What is the value, in terms of (as needed) $R_s$, $C_s$, $R_f$, and $L_f$, of $M(\omega) = \vert\mathbf H(\omega)\vert$ as $\omega\to\infty$? Does this result make sense to you? Explain why or why not."
- **Topic:** active inverting filter with complex $Z_{in}$ and $Z_f$, factored form, Bode with overlapping phase ramps (Ch. 9).
- **Skills:** $\mathbf H = -Z_f/Z_{in}$; $Z_{in} = (1 + j\omega R_sC_s)/(j\omega C_s)$; $Z_f = j\omega L_f/(1 + j\omega L_f/R_f)$; reading the double zero at the origin; summing phase ramps.
- **Verified answers** (sympy identity check plus numeric evaluation):
  - (a) $$\mathbf H(\omega) = \frac{-L_fC_s(j\omega)^2}{(1 + j\omega R_sC_s)(1 + j\omega L_f/R_f)}$$
  - (b) Corners are $1/(R_sC_s) = 10^4$ and $R_f/L_f = 10^5$ rad/s.
    - Magnitude: +40 dB/dec below $10^4$, crossing 0 dB at $10^4$ (since $L_fC_s\omega^2 = 1$ there). Then +20 dB/dec up to $10^5$, then flat at 20 dB.
    - Phase: $-(j\omega)^2 = +\omega^2$, so the phase starts at **0°**, not ±180°. It is flat to $10^3$, then −45°/dec to $10^4$ (−45°), −90°/dec to $10^5$ (−135°), and −45°/dec to $10^6$ (−180°), flat after that.
    - Exact values for comparison: −3.05 dB and −50.7° at $10^4$; 16.95 dB and −129.3° at $10^5$.
  - (c) $M \to R_f/R_s = 10$ (20 dB). At high ω, $C_s$ is a short and $L_f$ is open, so the circuit is an inverting amplifier with gain magnitude $R_f/R_s$.
- **Type:** (a) symbolic, (b) plot, (c) conceptual limit check. Class average **18.2/25, the lowest on F23**.

**P4 [25] Series R feeding a parallel LC tank (band-pass).** "Consider Circuit SE2-4 shown at right. All numerical values given in this problem are exact."
- **Figure SE2-4:** source $\mathbf V_s$ (+ top) feeds a series $R$ on the top rail. From the top node two shunt branches run to the bottom rail: $C$ (left) and $L$ (right), i.e. $L\parallel C$. $\mathbf V_{out}$ (+ top, − bottom) is across the tank.
- (a) "Calculate the transfer function $\mathbf H(\omega) = \mathbf V_{out}/\mathbf V_s$ in terms of $R$, $L$, $C$, and $\omega$."
- (b) "Suppose $R = 100\,\Omega$, $C = 40\,\mu$F, and $L = 1$ mH. Construct the Bode magnitude and phase plots for this circuit, using linear approximations as done in class. Be sure to label the key values on the vertical and horizontal axes of each plot, and any nonzero slopes in the Bode magnitude plot."
- (c) "What type of filter is this? Explain why it works this way, in terms of the component impedances as functions of frequency."
- (d) "Suppose $R$ increases from $100\,\Omega$ to $1000\,\Omega$. Would the bandwidth of the filter increase or decrease? Explain your answer."
- **Topic:** passive second-order band-pass; resonance; bandwidth vs R (Ch. 9).
- **Verified answers:**
  - (a) $$\mathbf H = \frac{j\omega L}{R\left(1 + j\omega L/R + (j\omega\sqrt{LC})^2\right)}$$
  - (b) $\omega_p = 1/\sqrt{LC} = 5000$ rad/s.
    - Key magnitude: +20 dB/dec up to a peak labelled **0 dB** at $\omega_p$, then −20 dB/dec.
    - Key phase: +90° flat to $0.1\omega_p$, a straight line through 0° at $\omega_p$, −90° from $10\omega_p$ on.
    - Exact $\lvert\mathbf H(\omega_p)\rvert = 1$ (0 dB). The pure asymptotes meet at $20\log(\omega_pL/R) = -26.0$ dB because $Q = \omega_pRC = 20$; see §5.4.
  - (c) Band-pass.
  - (d) Bandwidth decreases: $B = 1/(RC) = 250$ rad/s at 100 Ω and 25 rad/s at 1000 Ω (root-found numerically: 249.99 and 25.00).
- **How the key answers:**
  - (c) "L becomes short at low frequency, C becomes short at high frequency, so transfer function is 0 in those limits. At quadratic pole frequency, H = 1."
  - (d) "because $\mathbf Z_{L\parallel C}\to\infty$ as $\omega\to\omega_p$, and larger R means $\vert\mathbf H(\omega)\vert = 1/\sqrt2$ for a larger value of $\mathbf Z_{L\parallel C}$, or smaller deviation in ω."
- **Type:** (a)(b) computational, (c)(d) conceptual. Class average 18.9/25.

### 2.2 F24 Semester Exam 2 (13 Nov 2024), n = 36, mean 75.1 (planned full mock: read only after sitting it)

**P1 [25]** Same shared instruction as F23.

| Part | Stem (verbatim) | Topic | Key answer (verified) | Type |
|---|---|---|---|---|
| (a) [6] | "In a series RLC filter circuit, across which single component (R, L, or C) should the output terminals be positioned in order to create a low-pass filter? Explain your answer." | series RLC by output element | Across the capacitor | conceptual |
| (b) [6] | "Explain why the introduction of acceptor atoms into a semiconductor crystal, e.g., B (3 valence electrons) into Si (4 valence electrons), causes the Fermi level to move closer to the valence-band edge energy of the semiconductor." | doping and $E_F$ | Acceptors remove electrons from (create holes in) the VB. Empty VB states become more probable, so $E_F$ moves toward the VB | conceptual |
| (c) [6] | "Explain, in terms of the mathematical form of the Fermi distribution function, why current in a pn junction diode increases exponentially with increasing voltage." | Fermi function, diode | The barrier for carriers to diffuse across the junction drops with positive V; the form of $f(E)$ then gives an exponential | conceptual (repeat of F23 1c) |
| (d) [7] | "Consider a series RLC filter circuit with output terminals positioned across a single component (R, L, or C). For which types of filter circuits constructed in this manner can the maximum magnitude of the transfer function be greater than 1? Explain your answer." | peaking, Q | Low-pass (across C) or high-pass (across L) | conceptual |

**P2 [25] AC maximum power transfer.** "Consider Circuit SE2-2 at right. The input signal $\mathbf V_s$ is a sinusoidal signal with amplitude $V_s$ and angular frequency $\omega$."
- **Figure SE2-2:**
  - Top rail, left to right: source $\mathbf V_s$ (+ top), series $R_s$, an open-circle node (the source/load boundary), series $R'$, a node with $C$ shunted to the bottom rail, series $L$, then $R$ shunted to the bottom rail at the far right.
  - The bottom rail is continuous, with an open circle at the boundary.
  - Brackets underneath read "source" ($\mathbf V_s$, $R_s$) and "load" ($R'$, $C$, $L$, $R$).
- (a) "Suppose $C = 0$ and $R' = 0$. Calculate the average power transferred to the load circuit as a function of (as needed) $R_s$, $L$, $R$, $V_s$, and $\omega$."
- (b) "Now suppose $C > 0$ and $R' > 0$. Calculate the values of $C$ and $R'$ that maximize average power transfer to the load circuit. Your answers should be functions of (as needed) $R_s$, $L$, $R$, and $\omega$."
- **Topic:** maximum power transfer and conjugate matching (Ch. 8 (?)). Exam 1 F26 coverage explicitly excluded MPT, so it belongs to Exam 2.
- **Skills:** $P = \tfrac12\lvert I\rvert^2R$; $Z_{load} = R' + \left[\tfrac{1}{j\omega C}\parallel(R + j\omega L)\right]$; matching to a real source impedance requires $\operatorname{Im}Z_{load} = 0$ and $\operatorname{Re}Z_{load} = R_s$.
- **Verified answers** (sympy):
  - (a) $P = \tfrac12 V_s^2R/[(R_s+R)^2 + \omega^2L^2]$.
  - (b) $C = L/(\omega^2L^2 + R^2)$ and $R' = R_s - R/[(1-\omega^2LC)^2 + (\omega RC)^2]$.
  - With $C$ substituted, $R'$ simplifies to $R' = R_s - (R^2 + \omega^2L^2)/R$. This needs $R_s > (R^2+\omega^2L^2)/R$ to keep $R' > 0$; state that assumption.
- **Type:** computational and symbolic. Class average **15.7/25, the worst problem on either Exam 2**.

**P3 [25] RC low-pass with source resistance.** "Consider Circuits SE2-3 at right. The input voltage is $\mathbf V_s$, and the output voltage is $\mathbf V_o$."
- **Figure SE2-3:** source $\mathbf V_s(\omega)$ (+ top), series $R_s$, open-circle node, series $R$, then $C$ shunted to the bottom rail. $\mathbf V_o(\omega)$ (+ top) is across $C$.
- (a) "What type of filter circuit is this? Explain your answer."
- (b) "Suppose $R_s$ can range from 100 Ω to 1000 Ω, with $R = 10$ kΩ and $C = 0.1\ \mu$F. Calculate the cutoff frequency (or frequencies) $\omega_c$, i.e., the frequency (or frequencies) at which $\vert H(\omega)\vert \equiv \vert\mathbf V_o/\mathbf V_s\vert = 1/\sqrt2$, for (i) $R_s = 100\,\Omega$ and (ii) $R_s = 1000\,\Omega$."
- (c) "Now suppose $R_s = 0\,\Omega$, $R = 10$ kΩ, and $C = 0.1\ \mu$F. Construct the Bode magnitude and phase plots for this circuit, using linear approximations for low and high frequencies as done in class. For the phase plot, all angles should be plotted in the range $-180° \le \phi \le 180°$. Be sure to label the key values on the vertical and horizontal axes of each plot, and any nonzero slopes in the Bode magnitude plot."
- **Verified answers:**
  - (a) Low-pass.
  - (b) $\omega_c = 1/((R_s+R)C)$: (i) 990.1 rad/s, (ii) 909.1 rad/s.
  - (c) $\omega_p = 1/RC = 10^3$ rad/s. Magnitude: 0 dB flat, then −20 dB/dec. Phase: 0° to $10^2$, a line through −45° at $10^3$ down to −90° at $10^4$.
- **How the key answers (a):** "Low-pass filter." The expected reason: C is open at low ω, so $V_o = V_s$; C is a short at high ω, so $V_o\to0$.
- **Type:** (a) conceptual, (b)(c) computational. Class average **23.3/25, the easiest problem in the record**.

**P4 [25] Sallen-Key unity-gain low-pass, Butterworth design.** "Consider Circuit SE2-4 shown below. Assume that the op amp in the circuit always behaves in accordance with the ideal op-amp model."
- **Figure SE2-4:**
  - Source $\mathbf V_s(\omega)$ (+ top, − grounded) feeds $R_1$ to node A, then $R_2$ to node B. Node B is the op-amp non-inverting (+) input, drawn on the upper side of the triangle.
  - $C_1$ runs from node A over the top to the op-amp output (feedback). $C_2$ runs from node B to ground.
  - The inverting (−) input is tied straight to the output (follower). $\mathbf V_o(\omega)$ is taken at the output.
- (a) "Calculate the transfer function $H(\omega) \equiv \mathbf V_o/\mathbf V_s$ for this circuit. Express your final answer as a product of factors that are each one of the following (as needed): constant, zero@origin, pole@origin, simple zero, simple pole, quadratic zero, or quadratic pole. Your result should be expressed in terms of $R_1$, $R_2$, $C_1$, $C_2$, and $\omega$."
- (b) "What type of filter is Circuit SE2-4? Explain why it works this way, in terms of the component impedances as functions of frequency."
- (c) "Construct the Bode magnitude and phase plots for this circuit, using linear approximations for low and high frequencies as done in class. For the phase plot, all angles should be plotted in the range $-180° \le \phi \le 180°$. Be sure to label the key values on the vertical and horizontal axes of each plot, and any nonzero slopes in the Bode magnitude plot."
- (d) "A 'Butterworth filter' is a filter designed to have a very flat response across the filter pass band. For Circuit SE2-4, such a filter would have a transfer function magnitude $M(\omega)$ of the form $M(\omega) = 1/\sqrt{1 + (\omega/\omega_p)^4}$. Assuming $R_1 = R_2$, calculate the ratio $C_1/C_2$ that would be required to obtain a transfer function corresponding to a Butterworth filter."
- **Topic:** second-order active low-pass; quadratic-pole Bode; damping design (Ch. 9).
- **Skills:** two-node KCL with $V_B = V_o$; the quadratic-pole standard form; $\lvert H\rvert^2 = 1/[(1-x^2)^2 + (2\zeta x)^2]$, so Butterworth needs $2\zeta = \sqrt2$.
- **Verified answers** (nodal solve in sympy):
  - (a) $$\mathbf H = \frac{1}{1 + j\omega(R_1+R_2)C_2 - \omega^2R_1C_1R_2C_2}$$
  - (b) Low-pass.
  - (c) $\omega_p = 1/\sqrt{R_1C_1R_2C_2}$. Magnitude: 0 dB flat, then −40 dB/dec. Phase: 0° to $0.1\omega_p$, −90° at $\omega_p$, −180° from $10\omega_p$.
  - (d) With $R_1 = R_2$, $2\zeta = 2\sqrt{C_2/C_1}$. Setting this to $\sqrt2$ gives $C_1/C_2 = 2$.
- **How the key answers (b):** "Low-pass filter, due to limiting behavior of capacitors at low and high frequencies." At low ω both capacitors are open, nothing flows in $R_1$ or $R_2$, and the follower gives $H = 1$. At high ω, $C_2$ shorts the + input, so $V_o\to0$.
- **Type:** (a)(c)(d) computational, (b) conceptual. Class average 17.8/25.

### 2.3 Finals: Exam-2-relevant items only (cumulative finals, 115 min, Laplace handout appended)

The finals are an item pool, not a format model: 115 min, a Laplace table, and 5 × 5 P1s in F24/F25. Omitted as not Exam-2 material:
- F23 FE P3 (second-order RLC step transient, Exam 1 material).
- F25 FE P1c is kept only because it shares a figure with 1a/1b.

#### F23 Final (09 Dec 2023), n = 67, mean 71.4

**Figure FE-1ab (P1a, P1b):** a single series loop: source $v_s(t)$ (+ top), then $R$, $L$, $C$ along the top and right side, back to source −. No output is marked.

**Figure FE-1d (P1d):** inverting stage. $v_{in}$ (referenced to ground) feeds a series resistor into the − input; + is grounded. Feedback is a resistor (upper) in parallel with a capacitor (lower), from output to − input. $v_{out}$ is at the output. Components are unlabelled.

| Part | Stem (verbatim) | Topic | Key answer (verified) | Type |
|---|---|---|---|---|
| 1(a) [6] | "Suppose a series RLC circuit, such as Circuit FE-1ab at right, has underdamped response. To achieve overdamped response, would you want to increase or decrease $R$ (keeping the rest of the circuit unchanged)? Explain." | damping, Q (Exam 1 / Ch. 6 (?)) | Increase R: $R > 2\sqrt{L/C}$, or more dissipation damps signals faster | conceptual |
| 1(b) [6] | "Consider an RLC series circuit with a single independent source $v_s(t)$, such as Circuit FE-1ab shown at right. If $v_s(t) = (t + \cos\omega t)[u(t-5) - u(t-10)]$, would it be most efficient to solve for the current in the circuit using differential equations in the time domain, Laplace transforms, or Fourier techniques? Explain." | method choice (Laplace, Ch. 12; final-only) | Laplace, to accommodate initial conditions and avoid a hard ODE | conceptual |
| 1(c) [6] | "Consider a complex number $z = a + jb$, where $a$ and $b$ are real numbers. Keeping in mind the defined range of the mathematical function $\tan^{-1}x$, what is the phase of $z$, in degrees, for (i) $a > 0$ and $b > 0$, and (ii) $a < 0$ and $b < 0$?" | phase quadrant (Bode phase hygiene) | (i) $\tan^{-1}(b/a)$; (ii) $180° + \tan^{-1}(b/a)$ (equivalently $\tan^{-1}(b/a) - 180°$ in the −180..180 range) | conceptual |
| 1(d) [7] | "Consider a 4th-order cascaded active filter circuit consisting of 4 of the subcircuits Circuit FE-1d, shown at right, connected in series with each other, i.e., the output of one subcircuit is connect to the input of the next. (i) What type of filter is the 4th order circuit? (ii) What is the slope of the Bode magnitude plot (in the linear approximation) for the 4th order circuit outside the filter passband?" | cascaded active filters | (i) low-pass; (ii) −80 dB/decade (4 × −20) | conceptual |

**F23 FE P2 [25] Series $L\parallel C$ tank with shunt R (band-reject).** "Consider Circuit FE-2 shown below right. All numerical values given in this problem are exact."
- **Figure FE-2:** source $\mathbf V_s$ (+ top). On the top rail sits a parallel tank, $L$ (upper) $\parallel$ $C$ (lower), in series between the source + and the output node. $R$ runs from the output node down to the bottom rail. $\mathbf V_{out}$ (+ top) is across $R$.
- (a) "What type of filter is this? Explain."
- (b) "Calculate the transfer function $\mathbf H(\omega) = \mathbf V_{out}/\mathbf V_s$ in terms of $R$, $L$, and $C$. Your answer should be in an algebraic form that makes it very straightforward to identify the factors corresponding to any zeros or poles that are present."
- (c) "Suppose $L = 10$ mH, $R = 10\,\Omega$, and $C = 100\,\mu$F. Calculate the numerical value(s) of the corner, i.e., cutoff, frequency (or frequencies, if more than one exists)."
- **Verified answers:**
  - (a) Band-reject.
  - (b) $$\mathbf H = \frac{1-\omega^2LC}{1 + j\omega L/R - \omega^2LC} = \frac{1 + (j\omega/\omega_0)^2}{1 + j\omega L/R + (j\omega/\omega_0)^2},\quad \omega_0 = 1/\sqrt{LC}$$ This is a quadratic zero over a quadratic pole.
  - (c) $\omega_0 = 1000$ rad/s. Cutoffs: 618.0 and 1618.0 rad/s (golden-ratio pair, $\omega_{c2} - \omega_{c1} = 1/(RC) = 1000$).
- **How the key answers (a):** "Band-reject filter." The reason in impedance terms: L is a short at low ω and C is a short at high ω, so $V_{out} = V_s$ at both ends; at $\omega_0$ the tank is open, so $V_{out} = 0$.
- This is the one-element-swapped twin of F23 SE2 P4 (same tank, same R, positions exchanged: BP becomes BR). Class average 17.4/25.

**F23 FE P4 [25] Multiple-feedback (MFB) inverting band-pass driven by a ramp-up input (Laplace).** "Consider Circuit FE-4 shown at right. All the numerical values given in this problem are exact, and the op amp can be considered ideal and is always in its linear region of behavior. $R_1 = 1$ kΩ, $R_2 = 1$ kΩ, $C_1 = 10\,\mu$F, and $C_2 = 8\,\mu$F. The input signal is given by $v_{in}(t) = 5(1 - e^{-10t})u(t)$ V, with $u(t) = 1$ for $t\ge0$, 0 for $t<0$."
- **Figure FE-4 (re-read from the page image; the vault transcript is wrong, see §11):**
  - Source $v_{in}(t)$ (+ top, − grounded) feeds a series $C_1$ to node X.
  - $R_1$ runs from node X to the op-amp − input. $R_2$ runs from node X over the top to the output (outer feedback). $C_2$ runs from the − input to the output (inner feedback).
  - + input is grounded. $v_{out}(t)$ is at the output.
- (a) "Using an analysis technique of your choice, calculate $v_{out}(t)$."
- (b) "As a quick check of the correctness of your solution, you can compute $v_{out}(0)$ and $v_{out}(\infty)$ using the expression you obtained in part (a). What values should you obtain for $v_{out}(0)$ and $v_{out}(\infty)$? Explain your answers."
- **Verified answers:**
  - $$H(s) = \frac{-sR_2C_1}{s^2R_1R_2C_1C_2 + s(R_1+R_2)C_2 + 1} = \frac{-0.01s}{8\times10^{-5}s^2 + 0.016s + 1}$$ Poles at $-100 \pm j50$.
  - (a) $v_{out} = \tfrac{25}{212}\left[(5\cos50t + 9\sin50t)e^{-100t} - 5e^{-10t}\right] = [1.2141\,e^{-100t}\cos(50t - 60.95°) - 0.5896\,e^{-10t}]u(t)$ V. The key prints 1.2136; see §11.
  - (b) $v_{out}(0) = 0$ and $v_{out}(\infty) = 0$. At $t = 0$ the input is 0 and no capacitor is charged. At $\infty$ the input is DC 5 V, which $C_1$ blocks: a band-pass has a zero at $s = 0$.
- **Exam-2 relevance:** only the $H(s)$/$\mathbf H(j\omega)$ derivation (an MFB band-pass). The time response is Laplace, final-only so far. Class average 16.6/25.

#### F24 Final (16 Dec 2024), n = 32, mean 75.0

**Figure FE-1abcd:** source $v_s(t)$ (+ top) at left; the top node is brought out as terminal $a$. A vertical series string runs down the right side: $R$ between $a$ and $b$, then $C$ between $b$ and $c$, then $L$ between $c$ and $d$. Terminal $d$ is the bottom node, back to source −. Taps at every node.

| Part | Stem (verbatim) | Topic | Key answer (verified) | Type |
|---|---|---|---|---|
| 1(a) [5] | "Consider Circuit FE-1abcd shown at right. Which two terminals should be selected as the output terminals for a high-pass filter? Explain." | series RLC by output element | c, d (across L) | conceptual |
| 1(b) [5] | "Consider Circuit FE-1abcd shown at right. Which two terminals should be selected as the output terminals for a band-reject filter? Explain." | series RLC, BR | b, d (across C + L) | conceptual |
| 1(c) [5] | "Consider Circuit FE-1abcd shown at right. If $R = 1$ kΩ, $C = 2\,\mu$F, and $L = 0.8$ mH, what is the resonant frequency of the circuit? Your answer should be a numerical value with appropriate units." | resonance | 25,000 rad/s (3979 Hz); $R$ is a distractor | computational |
| 1(d) [5] | "Consider Circuit FE-1abcd shown at right, with $v_s(t) = 5$ for $t<0$, $5e^{-10t}\cos(\omega t)$ for $t\ge0$. The output terminals for the circuit are $b$ and $c$. Would the most efficient way to solve this problem be to use phasors, Laplace transforms, Fourier series, Fourier transforms, or time-domain analysis? Explain." | method choice (final-only) | Fourier transform (see §11 note) | conceptual |
| 1(e) [5] | "Consider two different semiconductor materials, silicon and germanium, both of which have no dopants or defects, at room temperature. Silicon has an energy band gap of 1.12 eV, and germanium an energy band gap of 0.67 eV. Which semiconductor would you expect to have a higher concentration of holes in the valence band? Explain." | intrinsic $n_i$ vs $E_g$ | Germanium. $n_i \propto e^{-E_g/2kT}$; the gap factor alone is $e^{0.45/(2\cdot0.02585)} \approx 6\times10^3$ (ignoring $N_c$, $N_v$) | conceptual |

**F24 FE P2 [25] Two parallel first-order branches: RC high-pass and RL low-pass, power and power factor.** "Consider Circuit FE-2 shown at right."
- **Figure FE-2:** source $\mathbf V_s(\omega)$ (+ top) drives two branches between the rails.
  - Left branch: $C$ (upper) in series with $R_1$ (lower). $\mathbf V_1$ is across $R_1$ (+ at the $C$–$R_1$ junction).
  - Right branch: $L$ (upper) in series with $R_2$ (lower). $\mathbf V_2$ is across $R_2$.
- (a) "Calculate the transfer function $\mathbf H_1(\omega) \equiv \mathbf V_1(\omega)/\mathbf V_s(\omega)$. Your result should be in terms of (as needed) $R_1$, $R_2$, $C$, $L$, and $\omega$. Then construct the Bode magnitude and phase plots for the transfer function $\mathbf H_1$, using linear approximations as done in class. Be sure to label the key values on the vertical and horizontal axes of each plot, and any nonzero slopes in the Bode magnitude plot."
- (b) Same for $\mathbf H_2 \equiv \mathbf V_2/\mathbf V_s$.
- (c) "Calculate the average power dissipated by (i) the resistor $R_1$ and (ii) the resistor $R_2$ as functions of (as needed) $R_1$, $R_2$, $C$, $L$, $\vert\mathbf V_s(\omega)\vert$, and $\omega$."
- (d) "Suppose $R_1 = R_2 = 8\,\Omega$. For what values of $C$ and $L$ will the cutoff angular frequencies of $\mathbf H_1$ and $\mathbf H_2$ both be $10^4$ rad/s? You should give your answers as numerical values with appropriate units."
- (e) "Assume the cutoff angular frequencies of $\mathbf H_1$ and $\mathbf H_2$ are both equal to $\omega_c$, and that Circuit FE-2 is operating at $\omega = \omega_c$. Without assuming specific numerical values for any parameters in Circuit FE-2, calculate (i) the apparent power $P_s$ for the voltage source $\mathbf V_s(\omega)$, (ii) the average power $P_1$ dissipated by $R_1$, (iii) the average power $P_2$ dissipated by $R_2$, and (iv) the power factor $(P_1+P_2)/P_s$, all when the circuit operates at $\omega_c$. Your results should be expressed in terms of (as needed) $\vert\mathbf V_s(\omega_c)\vert$, $R_1$, and $R_2$."
- **Verified answers:**
  - (a) $\mathbf H_1 = j\omega R_1C/(1 + j\omega R_1C)$, a high-pass with $\omega_0 = 1/R_1C$. Magnitude: +20 dB/dec up to 0 dB, then flat. Phase: +90° falling to 0°.
  - (b) $\mathbf H_2 = 1/(1 + j\omega L/R_2)$, a low-pass with $\omega_1 = R_2/L$. Magnitude: 0 dB, then −20. Phase: 0° falling to −90°.
  - (c) $P_1 = \tfrac12\frac{(\omega R_1C)^2}{1+(\omega R_1C)^2}\frac{\lvert V_s\rvert^2}{R_1}$ and $P_2 = \tfrac12\frac{1}{1+(\omega L/R_2)^2}\frac{\lvert V_s\rvert^2}{R_2}$.
  - (d) $C = 12.5\,\mu$F, $L = 0.8$ mH.
  - (e) $P_s = \frac{\lvert V_s\rvert^2}{2\sqrt2}\sqrt{R_1^{-2}+R_2^{-2}}$, $P_1 = \lvert V_s\rvert^2/4R_1$, $P_2 = \lvert V_s\rvert^2/4R_2$, and $\text{pf} = \frac{1}{\sqrt2}(R_1^{-1}+R_2^{-1})/\sqrt{R_1^{-2}+R_2^{-2}}$. This equals 1 when $R_1 = R_2$, because the two branch currents' reactive parts cancel.
- Class average 16.7/25.

**F24 FE P3 [25] MFB inverting band-pass; exact vs straight-line bandwidth.** "Consider Circuit FE-3 shown at right. Assume the op-amp always behaves according to the ideal op-amp model."
- **Figure FE-3:**
  - Source $\mathbf V_s(\omega)$ (+ top, − grounded) feeds a series $R_1$ to node X.
  - $R_2$ runs from X to ground. $C_1$ runs in series from X to the op-amp − input. $C_2$ runs from X over the top to the output (outer feedback). $R_3$ runs from the − input to the output (inner feedback).
  - + input is grounded. $\mathbf V_o(\omega)$ is at the output.
- (a) "Calculate the transfer function $\mathbf H(\omega) \equiv \mathbf V_o(\omega)/\mathbf V_s(\omega)$ as a function of (as needed) $R_1$, $R_2$, $R_3$, $C_1$, $C_2$, and $\omega$. What type of filter is Circuit FE-3?"
- (b) "Construct the Bode magnitude and phase plots for the transfer function $\mathbf H$, using linear approximations as done in class. Be sure to label the key values on the vertical and horizontal axes of each plot expressed in terms of (as needed) $R_1$, $R_2$, $R_3$, $C_1$, and $C_2$, and the numerical values of any nonzero slopes in the Bode magnitude plot. For the Bode phase plot, all phase angles $\phi(\omega)$ should satisfy $0° \le \phi(\omega) < 360°$."
- (c) "Assume $R_1 = 2.5\,\Omega$, $R_2 = 0.1\,\Omega$, $R_3 = 10\,\Omega$, $C_1 = C_2 = 1$ mF. Using the same linear approximations used to construct Bode plots, calculate the bandwidth of this filter, giving your result as a numerical value with appropriate units."
- (d) "As you did in part (c), assume [same values]. Without using the linear approximations used to construct Bode plots, calculate the bandwidth of this filter directly from the transfer function, giving your result as a numerical value with appropriate units. Explain why this result differs from the one you obtained in part (c)."
- **Verified answers:**
  - (a) Band-pass. $$\mathbf H = \frac{-j\omega R_3C_1}{1 + R_1/R_2 + j\omega R_1(C_1+C_2) - \omega^2R_1R_3C_1C_2}$$
  - (b) $\omega_0 = \sqrt{(R_1+R_2)/(R_1R_2R_3C_1C_2)} = 1019.8$ rad/s.
    - Magnitude: peak labelled $20\log\frac{R_3C_1}{R_1(C_1+C_2)}$ (= +6.02 dB with the part-(c) values; this is the exact $\lvert H(\omega_0)\rvert = 2$), with ±20 dB/dec on either side.
    - Phase: −jω gives −90°, which is 270° in the 0..360 range. Flat at 270° to $0.1\omega_0$, 180° at $\omega_0$, 90° from $10\omega_0$.
  - (c) 721 rad/s, which equals $\omega_0(\sqrt2 - 1/\sqrt2) = \omega_0/\sqrt2$: the −3 dB points lie on the ±20 dB/dec lines from the exact peak.
  - (d) **200 rad/s exactly**, $= (C_1+C_2)/(R_3C_1C_2)$; cutoffs at 924.7 and 1124.7 rad/s. The key prints 200.3 (§11). The two differ because the straight lines ignore the damping term: $Q = \omega_0/B \approx 5.1$, so the true peak is much narrower than the ±20 dB/dec "V".
- Class average **15.1/25, the lowest filter-problem average in the record**.

**F24 FE P4 [25] Two-section RC ladder (Laplace).** "Consider Circuit FE-4 shown at right The input signal is given by $v_s(t) = 5(1-e^{-10t})u(t)$ V …"
- **Figure FE-4:** source $v_s(t)$ (+ top) feeds a series $R_1$ to node A, with $C_1$ shunted to the bottom rail. Series $R_2$ runs to node B, with $C_2$ shunted. $v_{out}$ (+ top) is across $C_2$.
- (a) "Calculate the Laplace transform of $v_s(t)$."
- (b) "Assume $R_1 = 2$ kΩ, $R_2 = 5$ kΩ, $C_1 = 1\,\mu$F, and $C_2 = 2\,\mu$F. Use the Laplace transform technique to calculate $v_{out}(t)$."
- (c) "Your result for $v_{out}(t)$ in part (b) should not exhibit any oscillatory behavior. Show mathematically that with $C_1 = 1\,\mu$F and $C_2 = 2\,\mu$F, there is no combination of positive values of $R_1$ and $R_2$ for which oscillatory behavior will be observed in $v_{out}(t)$."
- **Verified answers:**
  - (a) $V_s = 5/s - 5/(s+10)$.
  - (b) $H = 1/[s^2R_1R_2C_1C_2 + s(R_1C_1 + R_2C_2 + R_1C_2) + 1]$ with poles at −68.34 and −731.66 s⁻¹. $v_{out} = 5 - 5.938e^{-10t} + 0.9454e^{-68.34t} - 7.14\times10^{-3}e^{-731.66t}$ V (key: 0.9453 and 7.138e−3, a rounding difference).
  - (c) With $a = R_1C_1$, $b = R_2C_2$, $c = R_1C_2$, the discriminant is $(a+b+c)^2 - 4ab = (a-b)^2 + c^2 + 2c(a+b) > 0$, so the poles are always real. This holds for any positive values, not just the stated C's.
- **Exam-2 relevance:** the s-domain ladder transfer function (a loaded cascade, i.e. why two RC sections are not $H_1H_2$). The time response is final-only. Class average 20.0/25.

#### F25 Final (12 Dec 2025), n = 17, mean 77.1 (same academic year as the reserved F25 Exam 2: see §8)

**Figure FE-1abc:** source $v_s(t)$ (+ top); the top-right node is terminal $a$. $R$ runs from $a$ down to terminal $b$. From $b$ two parallel branches run to the bottom node, terminal $c$: $C$ in series with "switch 1" (left) and $L$ in series with "switch 2" (right). Both switches are drawn open.

**Figure FE-1d:** source $\mathbf V_s(\omega)$ (+ top), series $R_1$, a node with $C$ shunted down, then series $R_2$, then $L$ down the right side to the bottom rail. Brackets read "source" ($\mathbf V_s$, $R_1$) and "load" ($C$, $R_2$, $L$).

| Part | Stem (verbatim) | Topic | Key answer (verified) | Type |
|---|---|---|---|---|
| 1(a) [5] | "Consider Circuit FE-1abc shown at right. If switch 1 is open and switch 2 is closed, and the output terminals are taken to be terminals $a$ and $b$, what type of filter is this? Explain." | RL by output element | Low-pass (series R–L, output across R) | conceptual |
| 1(b) [5] | "Consider Circuit FE-1abc shown at right. Both switches are closed and the output terminals are taken to be terminals $b$ and $c$. What is the maximum value of the transfer function magnitude, and at what frequency does this maximum value occur? Your results should be expressed in terms of (as needed) $R$, $L$, and $C$." | R + $L\parallel C$ band-pass | 1, at $\omega = 1/\sqrt{LC}$ | conceptual |
| 1(c) [5] | "Consider Circuit FE-1abc shown at right. Switch 1 is closed, and switch 2 is open. Assume $R = 200\,\Omega$, $C = 10\,\mu$F, $L = 5$ mH, and $v_s(t) = 5u(t)$ V where $u(t)$ is the unit step function. At what time (give a numerical value) is the voltage between terminals $b$ and $c$ equal to 3 V? Be sure to show your work." | RC step (Exam 1 skill) | $t = RC\ln(5/2) = 1.833$ ms | computational |
| 1(d) [5] | "Consider Circuit FE-1d shown at right, with $R_2 = 100\,\Omega$, $C = 20\,\mu$F, $L = 2$ mH, and $\omega = 5000$ rad/s. What value of $R_1$ maximizes power transfer from the source to the load? Explain your answer." | MPT trap | $R_1 = 0$ ($Z_{load} = 1 - j10\ \Omega$ is fixed; a series source resistance only wastes power) | conceptual |
| 1(e) [5] | "Explain, in terms of the behavior of electrons and holes in a semiconductor's conduction band and valence band, respectively, why current increases exponentially with increasing voltage across a forward-biased pn junction diode." | Fermi function, diode | See SA-22 | conceptual |

**F25 FE P2 [25] Third-order LC ladder (loaded cascade).** "Consider Circuit FE-2 shown at right."
- **Figure FE-2:** source $\mathbf V_s(\omega)$ (+ top), series $R_s$ to node 1 with $C_1$ shunted down. Series $L$ runs from node 1 to node 2, which has $C_2$ shunted down and $R_L$ shunted down further right. $\mathbf V_o$ (+ top) is across $R_L$.
- (a) "What type of filter is this? Explain your reasoning in terms of the limiting behavior of the circuit's components at low and high frequency."
- (b) "Assume, for just part (b) of the problem, that $R_L\to\infty$. Calculate the transfer function … in this limit. … You do not need to express $\mathbf H(\omega)$ in terms of solely simple or quadratic zeroes or poles, and constants, but your answer should be in the form of a rational function of $\omega$ in resonably [sic] simplified form."
- (c) "Now assume that $R_L$ is finite and nonzero. Calculate the transfer function … in terms of (as needed) $R_s$, $R_L$, $C_1$, $C_2$, $L$, and $\omega$." (same rational-function allowance)
- (d) "Show that your expression for $\mathbf H(\omega)$ from part (c) yields the correct result for $\omega\to0$."
- **Verified answers:**
  - (a) Low-pass.
  - (b) $\mathbf H = 1/[1 + j\omega R_s(C_1+C_2) - \omega^2LC_2 - j\omega^3R_sLC_1C_2]$.
  - (c) $\mathbf H = (j\omega L/R_s)/[(1-\omega^2LC_1 + j\omega L/R_s)(1-\omega^2LC_2 + j\omega L/R_L) - 1]$. Its $R_L\to\infty$ limit reproduces (b) (checked).
  - (d) Expanding the denominator to first order gives $j\omega L(1/R_s + 1/R_L)$, so $\mathbf H\to R_L/(R_s+R_L)$: the DC divider with C open and L short.
- Class average 22.0/25.

**F25 FE P3 [25] Sallen-Key low-pass + input impedance. Same circuit as F24 SE2 P4.**
- **Figure FE-3:** as F24 SE2-4. $R_1$ to node A, $R_2$ to node B and the + input (top pin), $C_1$ from A to the output, $C_2$ from B to ground, − (bottom pin) tied to the output. The source current $\mathbf I_s$ is marked flowing into $R_1$.
- (a) "What type of filter is this? Explain your reasoning in terms of the limiting behavior of the circuit's components at low and high frequency."
- (b) "Calculate the transfer function … Your result should contain only factors corresponding to constants and simple or quadratic zeroes or poles."
- (c) "For part (c) of this problem only, assume $R_1 = R_2 = 1000\,\Omega$, and $C_1 = C_2 = 1\,\mu$F. Construct the Bode magnitude and phase plots … For the Bode phase plot, all phase angles $\phi(\omega)$ should satisfy $-180° \le \phi(\omega) < 180°$."
- (d) "… define an input impedance for this circuit, $\mathbf Z_{in}$, to be $\mathbf Z_{in} = \mathbf V_s/\mathbf I_s$. Calculate $\mathbf Z_{in}$ as a function of (as needed) $R_1$, $R_2$, $C_1$, $C_2$, and $\omega$."
- (e) "Demonstrate that your result for part (d) is correct for $\omega\to0$ and $\omega\to\infty$."
- **Verified answers:**
  - (a) Low-pass.
  - (b) Same $\mathbf H$ as F24 SE2 P4.
  - (c) Corner at 1000 rad/s. Magnitude: 0 dB, then −40 dB/dec. Phase: 0° to 100, −90° at 1000, −180° from $10^4$.
  - (d) $\mathbf Z_{in} = [1 + j\omega(R_1+R_2)C_2 - \omega^2R_1R_2C_1C_2]/[j\omega C_2(1 + j\omega R_2C_1)]$ (sympy-checked).
  - (e) $\omega\to0$: $\mathbf Z_{in}\to1/(j\omega C_2)\to\infty$, because $C_2$ is open and the op-amp input draws no current. $\omega\to\infty$: $\mathbf Z_{in}\to R_1$, because $C_1$ shorts node A to $V_o\to0$.
- Class average 21.1/25. The same circuit scored 17.8 when it first appeared (F24 SE2 P4).

**F25 FE P4 [25] Same Sallen-Key with a damped-cosine input (Laplace).** The op amp is drawn with − on top (tied to the output) and + on the bottom (node B).
- (a) "Determine the Laplace transform, $V_s(s)$, of $v_s(t)$. Explain how you arrived at your result."
- (b) "Assume $R_1 = R_2 = 1000\,\Omega$, and $C_1 = C_2 = 10\,\mu$F. Use the Laplace transform technique to calculate $v_o(t)$ for all values of $t$."
- (c) "Show that your result for $v_o(t)$ in part (b) satisfies the correct boundary condition for $v_o(t)$ at $t = 0$."
- **Verified answers:**
  - (a) $V_s = 4(s+5)/[(s+5)^2 + 10^4]$.
  - (b) $H = 10^4/(s+100)^2$, a repeated real pole. $v_o = [0.10775e^{-100t} - 199.74te^{-100t} + 2.102e^{-5t}\sin(100t - 2.94°)]u(t)$ V, matching to 4 s.f.
  - (c) $v_o$ must be continuous at $t = 0$: $0.10775 + 2.102\sin(-2.94°) \approx 0$.
- Final-only. Class average 16.8/25.

> [!note] Do-not-solve check (PS8 9.26, 9.38, 9.39, 9.42, m9.2, 12.2; Lab 5)

---

## 3. Scores (every number read off the histogram pages, all viewed)

| Exam | n | Mean | Median | SD | Range | P1 | P2 | P3 | P4 |
|---|---|---|---|---|---|---|---|---|---|
| **F23 SE2** | 66 | 77.2 | 80 | 15.1 | 24–100 | 20.3 (81%) | 19.5 (78%) | **18.2 (73%)** | 18.9 (76%) |
| **F24 SE2** | 36 | 75.1 | 78.25 | 13.8 | 29–98 | 18.2 (73%) | **15.7 (63%)** | 23.3 (93%) | 17.8 (71%) |
| F23 Final | 67 | 71.4 | 73 | 11.7 | 45–95 | 20.9 | 17.4 (band-reject TF) | 16.2 (RLC transient) | 16.6 (MFB + Laplace) |
| F24 Final | 32 | 75.0 | 74.6 | 9.1 | 54–91.75 | 23.1 | 16.7 (RC/RL Bode + power) | **15.1 (MFB BP, BW)** | 20.0 (RC ladder Laplace) |
| F25 Final | 17 | 77.1 | 75 | 10.1 | 58–94 | 17.1 | 22.0 (LC ladder) | 21.1 (Sallen-Key + $Z_{in}$) | 16.8 (Laplace) |
| SE1 F26 (this class) | 25 | 71.3 | 74.5 | 12.8 | 40.5–92.5 | 20.1 | 19 | 19.3 | 12.9 |

- The caller's F23/F24 figures are confirmed. Recomputing the means from the bar counts with bin centres (label − 1) gives 76.6 and 74.8, consistent.
- Per-problem averages sum to the printed mean within 0.1, except F23 SE2 (76.9 vs 77.2) and F23 Final (71.1 vs 71.4). Unexplained; likely rounding or regrades.

**Point sinks**
- **F23 SE2:** P3, the inverting op-amp filter with Bode magnitude and phase including phase slopes (18.2). P4 next, the parallel-tank band-pass (18.9).
- **F24 SE2:** P2, maximum power transfer to an $R'$ + C + L + R load (15.7, worst on either Exam 2). Then P4, Sallen-Key + Butterworth (17.8), and P1 (18.2, down 2.1 from F23; plausibly because the acceptor/$E_F$ and $\lvert H\rvert>1$ items are harder than F23's As-vs-B and output-across-R (?)).
- **Overall (Exam 2s, n-weighted by content):**
  - op-amp filter 18.1/25 (72%)
  - design/power 18.2 (MPT alone 15.7)
  - conceptual P1 19.6 (78%)
  - passive filter 20.5 (82%)
- **Filter/Bode problems on finals:** F24 P3 MFB band-pass with exact vs linear bandwidth, 15.1 (60%); F24 P2 two first-order branches + power, 16.7 (67%); F23 P2 band-reject TF + cutoffs, 17.4 (70%); F25 P3 Sallen-Key + $Z_{in}$, 21.1 (84%); F25 P2 ladder, 22.0 (88%).
- **Pattern:** students lose points on (i) power-matching algebra with several reactive elements, (ii) op-amp filters with non-trivial $Z_{in}/Z_f$ or second-order topologies, and (iii) anything that separates exact behaviour from the straight-line approximation. First-order passive RC/RL with Bode is near-free (93%).

---

## 4. Topic frequency (F23 SE2, F24 SE2, three finals)

Cells give problem/part and points. P2–P4 part points are not printed, so those cells show the problem total. "—" means absent.

| Topic | F23 SE2 | F24 SE2 | F23 Final | F24 Final | F25 Final | Exams with it |
|---|---|---|---|---|---|---|
| Series RLC filter type by output element | 1d (7) BP | 1a (6) LP | — | 1a (5) HP, 1b (5) BR | 1a (5) RL→LP; 1b (5) R+L∥C | 4/5 (2/2 SE2) |
| Q, bandwidth, resonance | 1a (6) Q; P4b $\omega_p$, P4d BW (of 25) | 1d (7) peaking | 1a (6) damping vs R | 1c (5) $\omega_0$; P3c,d BW (of 25) | 1b (5) peak at $1/\sqrt{LC}$ | 5/5 |
| Doping and Fermi level | 1b (6) | 1b (6) | — | — | — | 2/5 (2/2 SE2) |
| Fermi function → diode exponential | 1c (6) | 1c (6) | — | — | 1e (5) | 3/5 (2/2 SE2) |
| Intrinsic concentration vs $T$ / $E_g$ | — | — | — | 1e (5) ($E_g$ at fixed $T$) | — | 1/5 |
| Passive filter design to a spec | P2a–c (25) | — | — | P2d (of 25) | — | 2/5 |
| Band-reject / LC | P2b,c notch; P4 tank BP | — | P2 (25) BR | 1b (5) | 1b (5); P2 LC ladder | 4/5 |
| Max power transfer / conjugate match | — | P2 (25) | — | P2c,e avg/apparent power, pf (not MPT) | 1d (5) $R_1 = 0$ | 2/5 (+1 power) |
| RC/RL cutoff with source resistance | P2a (RL HP, series R) | P3b (of 25) | — | P2a,b,d | 1a (RL) | 4/5 |
| TF in factored standard form | P3a, P4a | P4a (7-factor list) | P2b | P3a | P3b (P2 explicitly exempt) | 5/5 |
| Bode magnitude | P3b, P4b | P3c, P4c | — (1d slope only) | P2a,b; P3b | P3c | 4/5 (2/2 SE2) |
| Bode phase | P3b (slopes graded), P4b | P3c, P4c (−180..180) | — (1c quadrant) | P2a,b; P3b (0..360) | P3c (−180..<180) | 4/5 (2/2 SE2) |
| Active inverting op-amp filter | P3 (25) | — | 1d (7); P4 MFB (25) | P3 MFB (25) | — | 3/5 |
| Sallen-Key / 2nd-order active | — | P4 (25) | P4 MFB is 2nd-order | P3 MFB is 2nd-order | P3, P4 (SK) | 4/5 |
| Butterworth condition | — | P4d | — | — | — | 1/5 |
| Cascaded / loaded filters | — | — | 1d (7) −80 dB/dec | P4 RC ladder | P2 ladder, $R_L$ loading | 3/5 (0/2 SE2) |
| $\lvert H\rvert>1$ and peaking | P3c ($R_f/R_s = 10$) | 1d (7) | — | P3b peak +6 dB | 1b (max = 1) | 4/5 |
| Laplace | — | — | 1b (6); P4 (25) | 1d (5) (answer: Fourier); P4 (25) | P4 (25) | 3/5 (**0/2 SE2**) |
| Phase quadrant / $\tan^{-1}$ range | (P3b phase) | (phase range stated) | 1c (6) | (0..360 range) | (−180..<180) | 1/5 explicit |

---

## 5. Recurring templates and traps

### 5.1 "One element swapped" families

**Series RLC with the output across different elements** (F23 SE2 1d; F24 SE2 1a, 1d; F24 FE 1a, 1b; F25 FE 1a, 1b):

| Output across | Filter | Why (key language) | Max $\lvert H\rvert$ |
|---|---|---|---|
| R | band-pass | C takes $V_s$ at low ω, L at high ω, so $V_R$ peaks at $\omega_0$ | exactly 1 at $\omega_0$ |
| C | low-pass | C open at low ω ($V_C = V_s$), short at high ω | can exceed 1 ($= Q$ at $\omega_0$ when $Q > 1/\sqrt2$) |
| L | high-pass | L short at low ω, open at high ω | can exceed 1 (same condition) |
| L + C (series pair) | band-reject | the pair is a short at $\omega_0$ and open at both extremes | 1 |

**Tank and branch swaps** (all use the same $L$, $C$, $R$):

| Circuit | Filter | Where |
|---|---|---|
| Series R, shunt $L\parallel C$, output across the tank | band-pass, peak 1 at $\omega_0$ | F23 SE2 P4; F25 FE 1b |
| Series $L\parallel C$, shunt R, output across R | band-reject | F23 FE P2 |
| Series R, shunt series-LC branch, output across the branch | band-reject, notch at $1/\sqrt{LC}$ | F23 SE2 P2b,c |

**Bandwidth vs R flips with topology:**
- Series RLC band-pass: $B = R/L$, so raising R widens it.
- R feeding a parallel tank: $B = 1/(RC)$, so raising R narrows it. That is F23 SE2 P4d ("decreases").

**First-order: LP or HP from where the reactive element sits:**
- RC with output across C is low-pass (F24 SE2 P3); across R it is high-pass (F24 FE P2 $\mathbf H_1$).
- RL with output across R is low-pass (F24 FE P2 $\mathbf H_2$; F25 FE 1a); across L it is high-pass (F23 SE2 P2a).

**Op-amp: the same inverting skeleton with $Z_{in}$ and $Z_f$ exchanged.** $\mathbf H = -Z_f/Z_{in}$.
- A capacitor in series in $Z_{in}$ gives a zero at the origin: high-pass behaviour (F23 SE2 P3, $R_s$–$C_s$ in).
- A capacitor in parallel in $Z_f$ gives a pole: low-pass (F23 FE 1d, $R\parallel C$ feedback).
- An inductor behaves the opposite way: $R_f\parallel L_f$ in feedback gives a zero at origin × pole, i.e. high-pass with a gain ceiling $R_f/R_s$.

**Second-order active circuits, two topologies:**
- Sallen-Key LP: R's in series, $C_1$ to the output, $C_2$ to ground (F24 SE2 P4 = F25 FE P3/P4). Swapping R↔C would give the HP Sallen-Key, not yet examined (?).
- MFB band-pass: $C_1$ in series, $R_2$ or $C_2$ outer feedback (F23 FE P4, F24 FE P3).

**MPT direction flip:**
- Free load, fixed source: match $Z_L = Z_s^*$ (F24 SE2 P2).
- Fixed load, free **source** resistance: $R_s = 0$ (F25 FE 1d).

### 5.2 Standard-form factor list Ed Yu demands

F24 SE2 P4a, verbatim: "constant, zero@origin, pole@origin, simple zero, simple pole, quadratic zero, or quadratic pole". F23 phrasing: "an algebraic form that makes it very straightforward to identify the factors corresponding to any zeros or poles". F25 phrasing: "only factors corresponding to constants and simple or quadratic zeroes or poles". The exception is F25 FE P2 (3rd order), which explicitly allowed an unfactored rational function.

| Factor | Form | Magnitude (straight line) | Phase (straight line) |
|---|---|---|---|
| constant | $K$ | $20\log\lvert K\rvert$ flat | 0° if $K>0$; ±180° if $K<0$, chosen to fit the stated range |
| zero @ origin | $(j\omega)^N$ | $+20N$ dB/dec through 0 dB at ω = 1 | $+90N°$ |
| pole @ origin | $(j\omega)^{-N}$ | $-20N$ dB/dec | $-90N°$ |
| simple zero | $1 + j\omega/\omega_c$ | 0, then +20 dB/dec from $\omega_c$ | 0 → +90° over $[0.1, 10]\omega_c$ (+45°/dec) |
| simple pole | $(1 + j\omega/\omega_c)^{-1}$ | 0, then −20 dB/dec | 0 → −90° (−45°/dec) |
| quadratic zero | $1 + 2\zeta(j\omega/\omega_0) + (j\omega/\omega_0)^2$ | 0, then +40 dB/dec | 0 → +180° over $[0.1, 10]\omega_0$ (+90°/dec) |
| quadratic pole | reciprocal of the above | 0, then −40 dB/dec | 0 → −180° (−90°/dec) |

Ed Yu's key style:
- He writes quadratics as $1 + j\omega L/R + (j\omega\sqrt{LC})^2$ or $1 + j\omega(R_1+R_2)C_2 - \omega^2R_1C_1R_2C_2$.
- He pulls the constant out front, e.g. $-L_fC_s(j\omega)^2$, which is a constant times a double zero at the origin.
- A band-pass is constant × zero@origin × quadratic pole.

### 5.3 Phase-range rule

- The range is stated in the stem and differs by exam: $[-180°, 180°]$ (F24 SE2), $[-180°, 180°)$ (F25 FE), $[0°, 360°)$ (F24 FE). F23 SE2 stated none; the key plotted 0 to −180°.
- Find the starting phase from the sign and $j$-power of the low-frequency factor, then map it into the range:
  - $-(j\omega)^2 = +\omega^2$ → 0° (F23 SE2 P3).
  - $-j\omega$ → −90° in the ±180 range, or 270° in the 0..360 range (F24 FE P3).
  - A negative constant → +180° or −180°, whichever keeps the whole curve inside the range.
- F23 FE 1c is the same rule in disguise: for $a<0$, $b<0$, $\angle z = 180° + \tan^{-1}(b/a)$, or $\tan^{-1}(b/a) - 180°$ if the range is ±180.

### 5.4 Straight-line conventions the keys actually use

1. **Corners and slopes** are labelled numerically on the axes; the plateau dB value is labelled (20 dB, 0 dB, $20\log(\cdot)$).
2. **Band-pass peak at the exact value.** In both band-pass keys the peak is drawn at the true $\lvert\mathbf H(\omega_0)\rvert$: 0 dB in F23 SE2 P4, $20\log\frac{R_3C_1}{R_1(C_1+C_2)}$ in F24 FE P3. The asymptotes alone would meet lower (−26.0 dB and −8.13 dB respectively).
   - Draw it the key's way and label the peak value.
   - If time permits, mark the asymptote intersection too.
   - The F24 FE "linear-approximation bandwidth" of 721 rad/s only works with this convention: −3 dB down the ±20 dB/dec lines from the exact peak gives $\omega_0/\sqrt2$ to $\sqrt2\,\omega_0$.
3. **Quadratic poles ignore ζ** for the magnitude (flat, then ∓40, no resonant bump). The phase ramps over two decades centred on $\omega_0$.
4. **Overlapping ramps** produce piecewise phase slopes (F23 SE2 P3: −45, −90, −45 °/dec). When the stem says "BOTH", label every phase slope.

### 5.5 What the keys accept for conceptual parts (argument templates)

- **Limiting impedances + voltage division** (every "what type of filter / explain in terms of the component impedances" stem): C is open at ω→0 and a short at ω→∞; L is the reverse. State the limit of H at both ends and what happens at $\omega_0$ ("At quadratic pole frequency, H = 1").
- **Limit check for "does this make sense"** (F23 SE2 P3c, F25 FE P2d, P3e): reduce the circuit at ω→0 or ∞ to a known one, e.g. an inverting amp ($R_f/R_s$), a DC divider ($R_L/(R_s+R_L)$), or $Z_{in}\to R_1$.
- **Energy:** $Q = 2\pi W_{stored}/W_{diss}$, and R is the only dissipator.
- **Fermi statistics:**
  - For $E - E_F \gg kT$, $f(E) \approx e^{-(E-E_F)/kT}$.
  - Forward bias lowers the barrier by $qV$, so the number of carriers able to cross scales as $e^{qV/kT}$.
  - Donor: the 5th electron goes to the CB, so $E_F$ rises toward $E_c$. Acceptor: holes in the VB, so $E_F$ drops toward $E_v$.
  - Smaller $E_g$ gives larger $n_i \propto e^{-E_g/2kT}$.
- **Short keys are not the expected answer length.** Several key lines are bare ("Across capacitor", "Germanium", "Fourier transform"), but the stems say "Explain". On SE1 F26 the explanation was itself a rubric line ("correct explanation for R_o"). Write the 2–3 sentence reasoning.

### 5.6 Other traps seen in the keys

- Cutoff with source resistance: use the **total** series resistance, $\omega_c = 1/((R_s+R)C)$.
- Resonant frequency asked with an R given: R is a distractor ($\omega_0 = 1/\sqrt{LC}$; F24 FE 1c).
- F23 SE2 P2c "are there other values?": only the **product** LC is fixed.
- A cascade of identical first-order active stages: the slope multiplies (4 × −20 = −80 dB/dec). **Passive** sections load each other, so their H's do not simply multiply (F24 FE P4, F25 FE P2: finite $R_L$ changes H).
- Butterworth: $\lvert H\rvert = 1/\sqrt{1+(\omega/\omega_p)^4}$ is equivalent to $2\zeta = \sqrt2$ (no peaking).
- Exact bandwidth of a second-order band-pass $K j\omega/(a_0 + j\omega a_1 - \omega^2a_2)$ is exactly $a_1/a_2$; you do not need the two cutoffs.

---

## 6. Scope boundary (evidence, not certainty)

| Evidence | Points to |
|---|---|
| F23 SE2 (08 Nov) and F24 SE2 (13 Nov): **zero** Laplace, Fourier, or transient items. Content is filters, Bode, transfer functions, op-amp filters, resonance/Q, semiconductors, MPT | Laplace not tested on Exam 2 |
| Every final appends "the Laplace transform handout" and has a 25-pt Laplace problem (F23 P4, F24 P4, F25 P4) plus a method-choice P1 (F23 1b Laplace; F24 1d Fourier) | Laplace and Fourier are final material |
| The F26 SE2 template header lists only "exam questions, answer sheets, and a calculator", with no handout. Ed Yu appends the table whenever he tests Laplace | Any Laplace on F26 Exam 2 would be without a table: at most a definition, delta/step-function integral, or "which method" item (?) |
| Exam 1 (F26) coverage announcement: "through phasor power calculations, excluding maximum power transfer" | MPT is owed to Exam 2 (F24 SE2 P2 precedent) |
| TA (Discord): "there are often questions on semiconductor physics on the second exam" (10-20); "Make sure you can Bode Plots in your sleep. There are often many Bode Plot questions on the second exam" (11-05) | Semiconductors + Bode confirmed in scope |
| PS6 = semiconductors (gamma-function carrier integral; Recitation 5 on 10-12); PS7 = Bode plots + decoupling capacitors; PS8 = Ch. 9 filters (9.26, 9.38, 9.39, 9.42, m9.2) + 12.2 | Exam 2 ≈ MPT + semiconductors + Ch. 9 (+ maybe 12.1 singularity functions) |

- The Exam 2 "material covered" announcement is **not on disk**. For Exam 1 it was a Canvas announcement 11 days out (Sep 26 for Oct 7), so an Exam 2 equivalent may already be posted. **Check Canvas announcements**; it settles Laplace and cascades.
- Not tested on any Exam 2 or final: a semiconductor **numerical** problem (carrier concentration integral, $n_i(T)$ calculation). PS6 trained it and the TA flagged semiconductors, so a short numeric P1 part (e.g. $n_i$ ratio for two temperatures or gaps) is possible (?).

---

## 7. How Ed Yu grades (SE1 F26 Gradescope rubric + PS-tips handout)

**Rubric structure:** every part is a separate Gradescope question with additive "+n pts" items.
- Method/setup points are separate from answer points, e.g. P2c: "+4 Correct KCL setup, +2 Correct boundary conditions, +3 Correct final answer"; P3c: "+3 a correct method of calculating average power; +2 correct calculation of average power with units".
- A correct setup earns most of a part even if the answer is wrong. A right number without method loses the method points.

**Granularity:** 0.5 pt. 4a scored 1.5/4 as "+1 Correct i(0)=0.2; +0.5 At least one incorrect IC". Generic "+3 partial credit / +2 partial credit" items absorb arithmetic slips: 3d lost only 1 of 6 for a factor-of-10 error plus an unevaluated power.


**Comment style:** terse, naming the missing element:
- 1b, −1 of 6: "need answer for v_L also." Half of a two-part conceptual question answered costs only 1, so answer every sub-question by name.
- 1d, −3 of 7: "average power is the integral of instantaneous power - need to show explicitly that integral goes to zero." The stem said "Show, working purely in the time domain". Quoting the result being proven ($\tfrac12VI\cos\theta$) is circular and earned only partial credit. When the stem prescribes a method ("show", "in terms of the Fermi distribution function", "in terms of the component impedances"), the method is what is graded.

**Explanation is graded on conceptual parts:** rubric lines are "correct explanation for $R_o$" and "correctly deduce type of impedance from phasor phase relationship". The PS-tips handout: "Correct numerical answer with no explanation – typically gets minimal or zero credit"; "write out a sentence or two, or a few key phrases, explaining your work or indicating the concept/law you are applying"; box final answers with units; draw and label the circuit if you define variables; neatness counts; cross out cleanly; one clearly marked answer.

**Rounding tolerance:** 3b accepted 0.100 A for 99.85 mA.

**Units:** carry a rubric line ("with units").

**Weights:** exams are 85% of the course grade and problem sets 5% (PS-tips handout). The syllabus PDF itself was not opened (outside B1's input list); "75 minutes each" is quoted from `Semester Exam 1 details.txt`.

**Implications for Exam 2:**
- Write the factored $\mathbf H$ even if the Bode plot fails. They are separate parts.
- On every Bode plot, label the corner values, dB levels, and each slope (magnitude, plus phase when "BOTH").
- State the phase range used.
- Put something in every box. A setup line earns the setup item.

---

## 8. Item pool and the proposed split

Slots: **P1** conceptual · **P2** design-or-power · **P3** passive filter + Bode · **P4** active or RLC filter + Bode.

Difficulty: E/M/H, using the class average where one exists.

Recommendations:
- **SET** = per-slot timed set.
- **MOCK** = Monday 11-09 full mock.
- **POST** = hold until after the mock (twin of a mock item).
- **AVOID** = out of Exam-2 scope or a reserved-year twin.

| ID | Item | Slot | Pts | Diff. | Recommendation |
|---|---|---|---|---|---|
| A1 | F23 SE2 1a Q vs R | P1 | 6 | E | TE (bank) |
| A2 | F23 SE2 1b As vs B n-type | P1 | 6 | E | TE (bank) |
| A3 | F23 SE2 1c Fermi → diode exponential | P1 | 6 | M | TE. Twin of F24 1c; on the mock it becomes a recall check, which matches what F26 will test |
| A4 | F23 SE2 1d BP across R | P1 | 7 | E | TE (family root for §5.1) |
| A5 | F23 SE2 P2 shunt-Z design (L 0.1 H; series LC notch) | P2 | 25 | M (19.5) | SET (P2) before the mock |
| A6 | F23 SE2 P3 inverting $R_sC_s$ / $R_f\parallel L_f$ filter + Bode, phase slopes | P4 | 25 | H (18.2) | TE first (overlapping phase ramps), then a timed redo |
| A7 | F23 SE2 P4 series R + $L\parallel C$ band-pass, BW vs R | P3/P4 | 25 | M (18.9) | SET (P3), including the exact-peak convention |
| B1 | F24 SE2 P1 (a–d) | P1 | 25 | M (18.2) | MOCK |
| B2 | F24 SE2 P2 max power transfer | P2 | 25 | H (15.7) | MOCK |
| B3 | F24 SE2 P3 RC LP + $R_s$, Bode | P3 | 25 | E (23.3) | MOCK |
| B4 | F24 SE2 P4 Sallen-Key + Butterworth | P4 | 25 | H (17.8) | MOCK |
| C1 | F23 FE 1a overdamping vs R | P1 | 6 | E | SET (P1, low priority; Exam 1 topic) |
| C2 | F23 FE 1b Laplace/Fourier/time method | P1 | 6 | E | AVOID unless Canvas puts Laplace in scope |
| C3 | F23 FE 1c phase of $a+jb$ by quadrant | P1 | 6 | E | TE for the phase-range rule |
| C4 | F23 FE 1d 4-stage inverting RC cascade: LP, −80 dB/dec | P1 | 7 | E | SET (P1). Top priority given the 11-02 cascade session |
| C5 | F23 FE P2 series $L\parallel C$ + shunt R band-reject | P3 | 25 | M (17.4) | SET (P3); add "sketch Bode" as an extension |
| C6 | F23 FE P4 MFB band-pass: $H(s)$ only | P4 | ~10 (?) | H | TE for the $H$ derivation; AVOID the time response (Laplace) |
| D1 | F24 FE 1a HP terminals (c,d) | P1 | 5 | E | POST (twin of F24 SE2 1a) |
| D2 | F24 FE 1b BR terminals (b,d) | P1 | 5 | E | POST |
| D3 | F24 FE 1c $\omega_0$ with R distractor | P1 | 5 | E | SET (P1) |
| D4 | F24 FE 1d method choice (Fourier) | P1 | 5 | M | AVOID (final-only; key debatable, §11) |
| D5 | F24 FE 1e Si vs Ge holes | P1 | 5 | E | SET (P1) before the mock (semiconductor drill) |
| D6 | F24 FE P2a,b,d RC-HP / RL-LP Bode + design | P3 | ~15 (?) | M (16.7 whole) | SET (P3) before the mock |
| D7 | F24 FE P2c,e branch powers, apparent power, pf | P2 | ~10 (?) | M | SET (P2) after the mock (power algebra, MPT-adjacent) |
| D8 | F24 FE P3 MFB band-pass, 0..360 phase, BW linear vs exact | P4 | 25 | H (15.1) | TE (hardest filter item on disk), then SET |
| D9 | F24 FE P4 RC ladder | P3 | 25 | M (20.0) | AVOID the Laplace parts. Use (c)'s discriminant idea and the s-domain ladder $H$ only if cascades are in scope |
| E1 | F25 FE 1a/1b switched R–C–L terminals | P1 | 10 | E | POST, pending the twin check below |
| E2 | F25 FE 1c RC step time | — | 5 | E | AVOID (Exam 1 skill) |
| E3 | F25 FE 1d $R_1$ for MPT ($R_1 = 0$) | P1/P2 | 5 | M | POST (MPT trap; pairs with B2 debrief) |
| E4 | F25 FE 1e electrons/holes diode explanation | P1 | 5 | M | TE (bank) before the mock; the wording is the model answer for the diode item. Low twin risk: the same question is already in F23 and F24 SE2 1c |
| E5 | F25 FE P2 3rd-order LC ladder, loading | P3 | 25 | M (22.0) | POST, pending the twin check |
| E6 | F25 FE P3 Sallen-Key + $Z_{in}$ | P4 | 25 | M (21.1) | POST: same circuit and same $\mathbf H$ as mock item B4. Using it before Monday gives away B4(a)–(c) |
| E7 | F25 FE P4 Sallen-Key Laplace | — | 25 | H (16.8) | AVOID (Laplace) |

> [!warning] Reserved-year twins (F25)
> F25 FE items share an academic year with the reserved F25 Exam 2. Ed Yu reuses circuits: F24 SE2 P4 reappeared as F25 FE P3 and P4, and F25 FE P3 and P4 share one circuit. B1 was barred from opening F25 Exam 2, so it cannot say which F25 FE items duplicate it. **Before using E1, E5 or E6, have the format-only F25 reader confirm they do not duplicate F25 Exam 2 circuits.** Treat them as AVOID until cleared. E4 is exempt: its content is already in the F23/F24 keys.

### 8.1 F24 Exam 2 as the Monday 11-09 full mock: verdict

**Usable as-is.** It contains no Laplace, Fourier or transient item, and every part sits in Exam-2 scope (MPT was excluded from Exam 1, so it is owed to Exam 2). Caveats:
1. **Sallen-Key + Butterworth (P4):** it was taught before Exam 2 in F24. Confirm the F26 lectures reached second-order active filters by 11-09 (PS8 9.38–9.42 suggests yes, (?)). If not, P4 becomes a teaching item and the mock drops to 75 points.
2. **Shorter than F26:** F24 has P2 a–b, P3 a–c, P4 a–d (9 parts) against F26's a–c / a–e / a–e (13 parts). P3 was also the easiest problem in the record (23.3/25). The mock will under-load the clock. Optional fix: keep 70 min and append F23 SE2 P2(c) as "P2(c)" and F23 SE2 P3(c) as "P4(e)". Both are short and in style.
3. **Twins to avoid before Monday:** E6 (F25 FE P3, the same Sallen-Key), D1 and D2 (F24 FE 1a,b, the same series-RLC-terminal question as F24 1a), and E3 (F25 FE 1d, an MPT trap that primes B2).
4. **Print the F26 template** and grade with §7 rubric logic: separate setup and answer points, 0.5-pt granularity, "Missing" = 0.

### 8.2 Proposed split

| Use | Items |
|---|---|
| Teaching (Fri 11-06 to Sun 11-08) | A1–A4, C3, E4 (P1 bank); A6 (inverting active filter, phase ramps); D8 (MFB band-pass, 0..360, exact vs linear BW); C6 $H(s)$ only; §5 templates |
| Per-slot timed sets before the mock | P1: C1, C4, D3, D5. P2: A5. P3: A7, C5, D6. P4: A6 redo |
| **Full mock Mon 11-09** | **F24 SE2 (B1–B4)**, 70 + 5 min on the printed F26 template |
| Post-mock (Tue 11-10) | D1, D2, E3, D7 (MPT/power after the B2 debrief), E6, plus E1/E5 if cleared; re-drill the weakest mock slot |
| Avoid | C2, D4, E2, E7, D9 time-domain, C6 time-domain; E1, E5, E6 until the twin check clears them |

---

## 9. Ranked predictions for F26 Exam 2

1. **P1 has the diode-exponential-via-Fermi-function explanation plus a second semiconductor item** (doping → $E_F$ shift, or $n_i$ vs $E_g$ or $T$). Very high.
   - Both prior Exam 2 P1s had exactly two semiconductor parts, (b) and (c).
   - The diode question ran three straight years (F23 SE2 1c, F24 SE2 1c, F25 FE 1e).
   - TA 10-20: "often questions on semiconductor physics on the second exam". PS6 was semiconductors.
2. **P1 has a series-RLC "which element / which terminals gives filter X" item, with a twist:** terminal taps, switches, $\lvert H\rvert>1$ peaking, or Q vs R. Very high.
   - 2/2 Exam 2s (F23 1d; F24 1a + 1d) and 2/3 finals (F24 1a,b; F25 1a,b).
   - Q or peaking appeared on both Exam 2s (F23 1a, F24 1d).
3. **An op-amp filter problem, probably P4 (5 parts, 2-page last box).** Expect $\mathbf H$ in the 7-factor standard form, Bode magnitude and phase with a stated phase range and labelled slopes, then a limit check or design condition (Butterworth ratio, bandwidth, $M(\infty)$). High.
   - 2/2 Exam 2s (F23 inverting $Z_{in}/Z_f$; F24 Sallen-Key). Every final has a second-order active circuit.
   - TA 11-05: "Bode Plots in your sleep … many Bode Plot questions on the second exam".
   - The MFB band-pass (F23 FE P4, F24 FE P3) is the second-order topology not yet used on an Exam 2: a natural rotation (?).
4. **A passive filter problem, probably P3 (5 parts, two 1.5-page boxes).** Expect $\mathbf H$, filter type from impedance limits, Bode plots, and a parameter sweep (bandwidth vs R, cutoff vs source R). High.
   - 2/2 Exam 2s (F23 P4, F24 P3).
   - With the cascaded-filters session posted 11-02, the most likely new twist is a cascade: a two-section or loaded ladder without Laplace (F24 FE P4, F25 FE P2 style), or "n identical stages → slope" (F23 FE 1d) (?).
5. **P2 (3 parts) is maximum power transfer to a reactive load or a filter design to a spec.** Medium-high for "one of the two", about even between them (?).
   - MPT: Exam 1 explicitly excluded it, F24 P2 sets the precedent, and it was the worst-scored item.
   - Design: F23 P2 had exactly three parts, the F26 P2 shape.
   - Either way the template gives P2 three full pages: expect algebra, not a one-liner.

Below the line:
- Laplace on Exam 2 is **low**: 0/2 prior Exam 2s, and the template header lists no handout. At most a P1 item on $\delta(t)$/step integrals (PS8 12.2) or "which method".
- A semiconductor numeric (an $n_i$ ratio) is low-medium.
- A Butterworth/peaking condition is medium, as a P4 last part.

---

## 10. Short-answer bank (memorize)

Each entry gives the verbatim stem, the key's own words, a full answer in the key's argument style (the answer to write), and the source area. Lecture attributions are by topic; B1 did not open lecture files, so section-level sourcing is (?).

### 10.1 P1 items, all five exams

**SA-01 · F23 SE2 1a [6] · Q vs R** · *Ch. 9 series RLC / quality factor (?)*
- **Stem:** "Recall that the quality factor $Q$ of a filter is given by $Q = 2\pi(W_{stored}/W_{dissipated})\vert_{\omega=\omega_0}$. Based on this definition of $Q$, does a very small value of $R$ in an RLC series filter circuit lead to a high or low value for $Q$? Explain."
- **Key:** "High value of Q. R dissipates power so small R reduces the denominator in Q."
- **Answer:** High Q. In a series RLC, R is the only element that dissipates energy. At $\omega_0$ the stored energy sloshes between L and C while the energy lost per cycle is proportional to $I^2R$. A smaller R makes $W_{dissipated}$ smaller, so $Q$ is larger ($Q = \omega_0L/R = \tfrac1R\sqrt{L/C}$). The bandwidth $B = R/L$ narrows correspondingly.

**SA-02 · F23 SE2 1b [6] · n-type dopant** · *semiconductor unit: doping (Rec. 5, PS6)*
- **Stem:** "To create an n-type semiconductor from a crystal of pure Si, would you replace some of the Si atoms with B (boron, 3 valence electrons/atom) or As (arsenic, 5 valence electrons/atom)? Explain your answer."
- **Key:** "As, since extra valence electron compared to Si will occupy a state in the conduction band."
- **Answer:** Arsenic. Four of its five valence electrons complete the covalent bonds with neighbouring Si. The fifth is weakly bound (a donor level just below $E_c$) and at room temperature ends up in the conduction band, so electrons become the majority carrier ($n \approx N_D$) and $E_F$ moves up toward $E_c$. Boron would instead accept an electron from the valence band, creating holes (p-type).

**SA-03 · F23 SE2 1c [6] · diode exponential (Fermi function and its energy dependence)** · *semiconductor unit: pn junction*
- **Stem:** "Explain, in terms of the Fermi distribution function and its dependence on energy, why the current in a pn junction diode increases exponentially with voltage $V$, for $V > 0$."
- **Key:** "Fermi distribution function decreases exponentially with increasing energy. Increasing V>0 lowers barrier for carriers to traverse the pn junction by qV, and therefore exponentially increases the concentration of carriers with sufficient energy to cross the pn junction and contribute to current flow."
- **Answer:**
  - $f(E) = 1/(1 + e^{(E-E_F)/kT}) \approx e^{-(E-E_F)/kT}$ for $E - E_F \gg kT$, so the number of carriers falls off exponentially with energy above the band edge.
  - Only carriers with energy above the junction barrier $q(V_{bi} - V)$ can cross. Forward bias lowers the barrier by $qV$, so the crossing population, and hence the current, grows as $e^{qV/kT}$: $I = I_s(e^{qV/kT} - 1)$.

**SA-04 · F23 SE2 1d [7] · output across R gives band-pass** · *Ch. 9 series RLC filters (?)*
- **Stem:** "In a series RLC filter circuit, across which single component ($R$, $L$, or $C$) should the output terminals be connected to create a band pass filter? Explain your answer."
- **Key:** "R. By voltage division, most of the input voltage will be across C at low frequencies, and across L at high frequencies, so voltage across R will be maximum at intermediate frequencies leading to formation of pass band."
- **Answer:** Across R. $\mathbf H = j\omega RC/(1 - \omega^2LC + j\omega RC)$. At low ω, $Z_C\to\infty$ takes nearly all of $V_s$; at high ω, $Z_L\to\infty$ does. At $\omega_0 = 1/\sqrt{LC}$, $Z_L + Z_C = 0$, so $V_R = V_s$ ($\lvert H\rvert = 1$), giving a pass band centred at $\omega_0$.

**SA-05 · F24 SE2 1a [6] · output across C gives low-pass** · *Ch. 9 series RLC filters (?)*
- **Stem:** "In a series RLC filter circuit, across which single component (R, L, or C) should the output terminals be positioned in order to create a low-pass filter? Explain your answer."
- **Key:** "Across capacitor"
- **Answer:** Across C. At low ω, $Z_C = 1/(j\omega C)$ dominates the loop, so $V_C\to V_s$. At high ω, $Z_L$ dominates and $Z_C\to0$, so $V_C\to0$. $\mathbf H = 1/(1 - \omega^2LC + j\omega RC)$ is a quadratic pole: flat, then −40 dB/dec above $\omega_0$.

**SA-06 · F24 SE2 1b [6] · acceptors pull $E_F$ toward $E_v$** · *semiconductor unit: doping, Fermi level*
- **Stem:** "Explain why the introduction of acceptor atoms into a semiconductor crystal, e.g., B (3 valence electrons) into Si (4 valence electrons), causes the Fermi level to move closer to the valence-band edge energy of the semiconductor."
- **Key:** "Acceptor removes electrons from/creates holes in the valence band; probably [sic: probability] of finding empty states in the valence band increases, so Fermi level must move closer to valence band."
- **Answer:** Each B atom has only three valence electrons, so it captures an electron from the Si valence band to complete its bonds, leaving a hole. More empty VB states means $1 - f(E_v)$ rises. Since $p = N_v e^{-(E_F - E_v)/kT}$, a larger hole concentration requires a smaller $E_F - E_v$, so the Fermi level moves down toward the valence-band edge.

**SA-07 · F24 SE2 1c [6] · diode exponential (mathematical form of $f(E)$)** · *semiconductor unit: pn junction*
- **Stem:** "Explain, in terms of the mathematical form of the Fermi distribution function, why current in a pn junction diode increases exponentially with increasing voltage."
- **Key:** "Energy barrier for carriers to diffuse across junction decreases with positive V, so from form of f(E) one can show that current increases exponentially."
- **Answer:** Write the math. For energies well above $E_F$, $f(E) \approx e^{-(E-E_F)/kT}$ (Boltzmann tail). The electrons on the n side able to diffuse over a barrier of height $q(V_{bi} - V)$ number $\propto \int_{E_b}^\infty g(E)f(E)\,dE \propto e^{-q(V_{bi}-V)/kT}$; holes go the same way via $1 - f(E)$. So the diffusion current $\propto e^{qV/kT}$.

**SA-08 · F24 SE2 1d [7] · which series-RLC outputs can exceed $\lvert H\rvert = 1$** · *Ch. 9 resonance / peaking (?)*
- **Stem:** "Consider a series RLC filter circuit with output terminals positioned across a single component (R, L, or C). For which types of filter circuits constructed in this manner can the maximum magnitude of the transfer function be greater than 1? Explain your answer."
- **Key:** "Low-pass (output terminals across C) or high-pass (output terminals across L)."
- **Answer:** The low-pass (across C) and high-pass (across L).
  - At $\omega_0$ the L and C voltages cancel each other, but each alone has magnitude $Q\lvert V_s\rvert$ ($\lvert V_C(\omega_0)\rvert = \lvert V_s\rvert/(\omega_0RC)$).
  - With light damping ($Q > 1/\sqrt2$) the magnitude peaks above 1 near $\omega_0$.
  - Across R (band-pass), $\lvert H\rvert = R/\lvert R + j(\omega L - 1/\omega C)\rvert \le 1$, so it can never exceed 1.

**SA-09 · F23 FE 1a [6] · underdamped → overdamped** · *RLC transients, Exam 1 material (Ch. 6 (?))*
- **Stem:** "Suppose a series RLC circuit, such as Circuit FE-1ab at right, has underdamped response. To achieve overdamped response, would you want to increase or decrease $R$ (keeping the rest of the circuit unchanged)? Explain."
- **Key:** "Increase R. R>2sqrt(L/C) for overdamping, or increasing R increases power dissipation so signals are damped more quickly."
- **Answer:** Increase R. For series RLC, $\alpha = R/2L$ and $\omega_0 = 1/\sqrt{LC}$; overdamping needs $\alpha > \omega_0$, i.e. $R > 2\sqrt{L/C}$. More R dissipates the stored energy faster (lower Q), which kills the oscillation.

**SA-10 · F23 FE 1b [6] · method choice (final-only)** · *Ch. 12 Laplace*
- **Stem:** "Consider an RLC series circuit with a single independent source $v_s(t)$, such as Circuit FE-1ab shown at right. If $v_s(t) = (t + \cos\omega t)[u(t-5) - u(t-10)]$, would it be most efficient to solve for the current in the circuit using differential equations in the time domain, Laplace transforms, or Fourier techniques? Explain."
- **Key:** "Laplace transform, to accommodate initial conditions and avoid solving challenging differential equation."
- **Answer:** Laplace. The input is a gated ramp plus cosine switched on at $t = 5$ and off at $t = 10$. The time-shift property handles the $u(t-5)$ and $u(t-10)$ windows, initial conditions enter algebraically, and the ODE becomes algebra. Phasors need sinusoidal steady state and Fourier series needs periodicity.

**SA-11 · F23 FE 1c [6] · phase quadrant** · *complex numbers / Bode phase*
- **Stem:** "Consider a complex number $z = a + jb$, where $a$ and $b$ are real numbers. Keeping in mind the defined range of the mathematical function $\tan^{-1}x$, what is the phase of $z$, in degrees, for (i) $a > 0$ and $b > 0$, and (ii) $a < 0$ and $b < 0$?"
- **Key:** "(i) $\tan^{-1}(b/a)$. (ii) $180°+\tan^{-1}(b/a)$"
- **Answer:** $\tan^{-1}$ only returns angles in $(-90°, 90°)$, i.e. quadrants I and IV.
  - (i) $z$ is in quadrant I, so $\theta = \tan^{-1}(b/a)$.
  - (ii) $z$ is in quadrant III, but $b/a > 0$ makes $\tan^{-1}$ return a quadrant-I angle, so add 180°: $\theta = 180° + \tan^{-1}(b/a)$. In a −180..180 convention that is $\tan^{-1}(b/a) - 180°$.

**SA-12 · F23 FE 1d [7] · 4-stage inverting RC cascade** · *Ch. 9 cascaded active filters (?)*
- **Stem:** "Consider a 4th-order cascaded active filter circuit consisting of 4 of the subcircuits Circuit FE-1d, shown at right, connected in series with each other, i.e., the output of one subcircuit is connect to the input of the next. (i) What type of filter is the 4th order circuit? (ii) What is the slope of the Bode magnitude plot (in the linear approximation) for the 4th order circuit outside the filter passband?"
- **Key:** "(i) low-pass filter. (ii) -80 dB/decade."
- **Answer:** Each stage has $\mathbf H = -(R_f/R_{in})/(1 + j\omega R_fC)$: a low-pass, −20 dB/dec above $1/R_fC$. An ideal op-amp output is a zero-impedance source, so the stages do not load each other and $\mathbf H_{tot} = \mathbf H^4$. The cascade is low-pass with $4\times(-20) = -80$ dB/decade outside the pass band.

**SA-13 · F24 FE 1a [5] · high-pass terminals** · *Ch. 9 series RLC (?)*
- **Stem:** "Consider Circuit FE-1abcd shown at right. Which two terminals should be selected as the output terminals for a high-pass filter? Explain."
- **Key:** "c,d"
- **Answer:** c and d, across L. L is a short at low ω ($V_L\to0$) and open at high ω, where C is a short and $V_L\to V_s$. $\mathbf H = -\omega^2LC/(1 - \omega^2LC + j\omega RC)$: +40 dB/dec below $\omega_0$, flat above.

**SA-14 · F24 FE 1b [5] · band-reject terminals** · *Ch. 9 series RLC (?)*
- **Stem:** "Consider Circuit FE-1abcd shown at right. Which two terminals should be selected as the output terminals for a band-reject filter? Explain."
- **Key:** "b,d"
- **Answer:** b and d, across the series C–L pair. At low ω C is open and at high ω L is open, so the pair carries all of $V_s$ at both extremes. At $\omega_0 = 1/\sqrt{LC}$, $Z_L + Z_C = 0$, so $V_{bd} = 0$: a notch.

**SA-15 · F24 FE 1c [5] · resonant frequency** · *Ch. 9 resonance (?)*
- **Stem:** "Consider Circuit FE-1abcd shown at right. If $R = 1$ kΩ, $C = 2\,\mu$F, and $L = 0.8$ mH, what is the resonant frequency of the circuit? Your answer should be a numerical value with appropriate units."
- **Key:** "25,000 rad/s (or 3979 Hz)"
- **Answer:** $\omega_0 = 1/\sqrt{LC} = 1/\sqrt{(0.8\times10^{-3})(2\times10^{-6})} = 2.50\times10^4$ rad/s $= 3.98$ kHz. R does not set the resonant frequency; it sets Q and the bandwidth.

**SA-16 · F24 FE 1d [5] · method choice (final-only)** · *Ch. 12–13 Laplace/Fourier (?)*
- **Stem:** "Consider Circuit FE-1abcd shown at right, with $v_s(t) = 5$ for $t<0$, $5e^{-10t}\cos(\omega t)$ for $t\ge0$. The output terminals for the circuit are $b$ and $c$. Would the most efficient way to solve this problem be to use phasors, Laplace transforms, Fourier series, Fourier transforms, or time-domain analysis? Explain."
- **Key:** "Fourier transform"
- **Answer (reasoning reconstructed (?)):** The Fourier transform. The input is specified for all time, $-\infty<t<\infty$, and is neither a steady sinusoid (phasors) nor periodic (Fourier series), so the Fourier transform handles it in one pass without separate initial conditions. B1 notes that unilateral Laplace with $v_C(0^-) = 5$ V from the $t<0$ DC steady state also works; see §11.

**SA-17 · F24 FE 1e [5] · Si vs Ge intrinsic holes** · *semiconductor unit: intrinsic carriers*
- **Stem:** "Consider two different semiconductor materials, silicon and germanium, both of which have no dopants or defects, at room temperature. Silicon has an energy band gap of 1.12 eV, and germanium an energy band gap of 0.67 eV. Which semiconductor would you expect to have a higher concentration of holes in the valence band? Explain."
- **Key:** "Germanium"
- **Answer:** Germanium. In an intrinsic crystal every hole comes from an electron thermally excited across the gap, so $p = n = n_i = \sqrt{N_cN_v}\,e^{-E_g/2kT}$ (the Fermi-function tails at the band edges). The smaller gap gives exponentially more carriers: about $e^{(1.12-0.67)/(2\cdot0.0259)} \approx 6\times10^3$ from the gap factor alone. The same exponent makes $n_i$ rise steeply with $T$.

**SA-18 · F25 FE 1a [5] · series R–L, output across R** · *Ch. 9 first-order filters (?)*
- **Stem:** "Consider Circuit FE-1abc shown at right. If switch 1 is open and switch 2 is closed, and the output terminals are taken to be terminals $a$ and $b$, what type of filter is this? Explain."
- **Key:** "Low-pass filter"
- **Answer:** With switch 1 open the circuit is R in series with L, and terminals a, b are across R. At low ω L is a short, so $V_R = V_s$; at high ω L is open, so $V_R\to0$. $\mathbf H = 1/(1 + j\omega L/R)$: low-pass with corner $R/L$.

**SA-19 · F25 FE 1b [5] · R feeding $L\parallel C$, peak value** · *Ch. 9 band-pass / resonance (?)*
- **Stem:** "Consider Circuit FE-1abc shown at right. Both switches are closed and the output terminals are taken to be terminals $b$ and $c$. What is the maximum value of the transfer function magnitude, and at what frequency does this maximum value occur? Your results should be expressed in terms of (as needed) $R$, $L$, and $C$."
- **Key:** "1, at $\omega = 1/\sqrt{LC}$"
- **Answer:** The output is across the $L\parallel C$ tank fed through R, a band-pass. At $\omega_0 = 1/\sqrt{LC}$ the tank admittance $j\omega C + 1/(j\omega L) = 0$, so $Z_{tank}\to\infty$, no current flows in R, and $V_{bc} = V_s$: $\lvert H\rvert_{max} = 1$. Away from $\omega_0$, L (low ω) or C (high ω) shorts the output.

**SA-20 · F25 FE 1c [5] · RC step time** · *first-order transients, Exam 1 skill*
- **Stem:** "Consider Circuit FE-1abc shown at right. Switch 1 is closed, and switch 2 is open. Assume $R = 200\,\Omega$, $C = 10\,\mu$F, $L = 5$ mH, and $v_s(t) = 5u(t)$ V where $u(t)$ is the unit step function. At what time (give a numerical value) is the voltage between terminals $b$ and $c$ equal to 3 V? Be sure to show your work."
- **Key:** "1.833 ms"
- **Answer:** The circuit is R–C in series with $v_{bc} = v_C = 5(1 - e^{-t/RC})$ and $RC = 2$ ms. Setting $3 = 5(1 - e^{-t/RC})$ gives $t = RC\ln(5/2) = 1.833$ ms. L is out of the circuit.

**SA-21 · F25 FE 1d [5] · MPT when the source resistance is the variable** · *Ch. 8 MPT (?)*
- **Stem:** "Consider Circuit FE-1d shown at right, with $R_2 = 100\,\Omega$, $C = 20\,\mu$F, $L = 2$ mH, and $\omega = 5000$ rad/s. What value of $R_1$ maximizes power transfer from the source to the load? Explain your answer."
- **Key:** "$R_1 = 0$"
- **Answer:** $R_1 = 0$. Here the load is fixed ($Z_{load} = \tfrac{1}{j\omega C}\parallel(R_2 + j\omega L) = 1 - j10\ \Omega$) and the adjustable element is the source resistance. $P_{load} = \tfrac12\lvert V_s\rvert^2\operatorname{Re}Z_L/\lvert R_1 + Z_L\rvert^2$ falls monotonically as $R_1$ grows. Conjugate matching ($Z_L = Z_s^*$) answers the opposite question: choosing the load for a fixed source.

**SA-22 · F25 FE 1e [5] · diode exponential (electrons and holes)** · *semiconductor unit: pn junction*
- **Stem:** "Explain, in terms of the behavior of electrons and holes in a semiconductor's conduction band and valence band, respectively, why current increases exponentially with increasing voltage across a forward-biased pn junction diode."
- **Key:** "At forward bias, more electrons on the n-side have enough energy to surmount the built-in pn junction barrier and move to the p-side, and more holes on the p-side have enough energy to surmount the barrier and move to the n-side, resulting in forward-bias current flow. The concentration of carriers on each side with sufficient energy to surmount the barrier increases exponentially with voltage because the Fermi distribution function well above the Fermi level, and 1-f(E) well below the Fermi level, depend approximately exponentially on voltage/kT."
- **Answer:** This key is the model answer to reproduce. It covers four points: CB electrons on the n side and VB holes on the p side; a barrier lowered from $qV_{bi}$ to $q(V_{bi} - V)$; the $f(E)$ tail for electrons and the $1-f(E)$ tail for holes; hence $\propto e^{qV/kT}$.

### 10.2 Conceptual sub-parts inside P2–P4

**SA-23 · F23 SE2 2b · components for band-reject** · *Ch. 9*
- **Stem:** "Now suppose that $\mathbf Z$ consists of 2 individual components connected in series with each other. For the circuit to function as a band-reject filter, what should those components be (choose two from resistor, capacitor, and inductor). Explain your answer."
- **Key:** "Capacitor and inductor. Most of the input voltage will be across C at low frequencies, and across L at high frequencies, leading to a minimum in transfer function at intermediate frequencies."
- **Answer:** C and L. The series branch has $Z = j(\omega L - 1/\omega C)$: open at both extremes, so $V_{out} = V_s$, and zero at $\omega_0 = 1/\sqrt{LC}$, which shorts the output. A resistor in the branch would leave $V_{out} \ne 0$ at the notch.

**SA-24 · F23 SE2 2c (second sentence) · other component values?** · *Ch. 9*
- **Stem:** "…compute numerical values of the components that will yield $\mathbf V_{out} = 0$ at $\omega = 2000$ rad/s. Are there other component values for which $\mathbf V_{out} = 0$ as well? Explain why or why not."
- **Key:** "Any combination of L and C with $LC = 2.5\times10^{-7}\ \text{s}^2$, e.g., C = 2.5uF, L = 0.1H."
- **Answer:** Yes. $\mathbf V_{out} = 0$ only requires the branch impedance to vanish, $\omega^2LC = 1$, which fixes the product $LC = 1/2000^2 = 2.5\times10^{-7}$ s². Any pair with that product works. The pairs differ only in notch width, which is $R/L$.

**SA-25 · F23 SE2 3c · $M(\infty)$ of the inverting filter** · *Ch. 9 active filters (?)*
- **Stem:** "What is the value, in terms of (as needed) $R_s$, $C_s$, $R_f$, and $L_f$, of $M(\omega) = \vert\mathbf H(\omega)\vert$ as $\omega\to\infty$? Does this result make sense to you? Explain why or why not."
- **Key:** "M = R_f/R_s. This makes sense because at high frequencies C is short, L is open and circuit looks like an inverting amplifier, which has gain of magnitude R_f/R_s."
- **Answer:** As the key.

**SA-26 · F23 SE2 4c · R-fed tank type** · *Ch. 9*
- **Stem:** "What type of filter is this? Explain why it works this way, in terms of the component impedances as functions of frequency."
- **Key:** "Band pass filter. L becomes short at low frequency, C becomes short at high frequency, so transfer function is 0 in those limits. At quadratic pole frequency, H = 1."
- **Answer:** As the key. At $\omega_p$ the tank is an open circuit, so no current flows in R and $V_{out} = V_s$.

**SA-27 · F23 SE2 4d · bandwidth vs R** · *Ch. 9*
- **Stem:** "Suppose $R$ increases from 100 Ω to 1000 Ω. Would the bandwidth of the filter increase or decrease? Explain your answer."
- **Key:** "As R increases, bandwidth decreases … because $\mathbf Z_{L\parallel C}\to\infty$ as $\omega\to\omega_p$, and larger R means $\vert\mathbf H(\omega)\vert = 1/\sqrt2$ for a larger value of $\mathbf Z_{L\parallel C}$, or smaller deviation in ω."
- **Answer:** Decreases: $B = 1/(RC)$ goes from 250 to 25 rad/s (Q from 20 to 200). The opposite of series RLC, where $B = R/L$.

**SA-28 · F24 SE2 3a · RC with source R** · *Ch. 9*
- **Stem:** "What type of filter circuit is this? Explain your answer."
- **Key:** "Low-pass filter."
- **Answer:** C is open at low ω, so no current flows and $V_o = V_s$. C is a short at high ω, so $V_o\to0$. $\mathbf H = 1/(1 + j\omega(R_s+R)C)$.

**SA-29 · F24 SE2 4b and SA-36 · F25 FE 3a · Sallen-Key type** · *Ch. 9 active filters (?)*
- **Stems:** "What type of filter is Circuit SE2-4? Explain why it works this way, in terms of the component impedances as functions of frequency." / "What type of filter is this? Explain your reasoning in terms of the limiting behavior of the circuit's components at low and high frequency."
- **Key:** "Low-pass filter, due to limiting behavior of capacitors at low and high frequencies." / "Low-pass filter"
- **Answer:** At low ω both C's are open, so no current flows through $R_1$ or $R_2$, $V_+ = V_s$, and the follower gives $V_o = V_s$ ($H = 1$). At high ω, $C_2$ shorts the + input to ground, so $V_o\to0$.

**SA-30 · F23 FE 2a · series tank, shunt R** · *Ch. 9*
- **Stem:** "What type of filter is this? Explain."
- **Key:** "Band-reject filter"
- **Answer:** L is a short at low ω and C is a short at high ω, so the series element vanishes and $V_{out} = V_s$ at both extremes. At $\omega_0 = 1/\sqrt{LC}$ the tank is open, so $V_{out} = 0$.

**SA-31 · F23 FE 4b · $v_{out}(0)$ and $v_{out}(\infty)$** · *Ch. 12 + active band-pass*
- **Stem:** "As a quick check of the correctness of your solution, you can compute $v_{out}(0)$ and $v_{out}(\infty)$ using the expression you obtained in part (a). What values should you obtain for $v_{out}(0)$ and $v_{out}(\infty)$? Explain your answers."
- **Key:** "$v_{out}(0) = 0$ and $v_{out}(\infty) = 0$."
- **Answer:** At $t = 0$, $v_{in} = 5(1-1) = 0$ and the capacitors are uncharged, so $v_{out}(0) = 0$. As $t\to\infty$ the input is DC 5 V, which $C_1$ blocks (the band-pass $H(s)$ has a zero at $s = 0$), so $v_{out}\to0$.

**SA-32 · F24 FE 3a · MFB type** · *Ch. 9 active filters (?)*
- **Stem:** "…What type of filter is Circuit FE-3?"
- **Key:** "Band pass filter."
- **Answer:** At low ω the series $C_1$ into the − input is open, so no current reaches $R_3$ and $V_o = 0$. At high ω the gain falls as $1/(\omega R_1C_2)$. The transfer function is a zero at the origin times a quadratic pole: band-pass.

**SA-33 · F24 FE 3d (explain) · exact vs straight-line bandwidth** · *Ch. 9*
- **Stem:** "…Explain why this result differs from the one you obtained in part (c)."
- **Key:** "200.3 rad/s" (no reason printed)
- **Answer:** The straight-line plot replaces the quadratic pole by its asymptotes and ignores the damping term $j\omega R_1(C_1+C_2)$. With $Q = \omega_0/B \approx 5.1$ the true peak is far narrower than the ±20 dB/dec "V" (200 vs 721 rad/s). The exact bandwidth is the denominator's $a_1/a_2 = (C_1+C_2)/(R_3C_1C_2)$.

**SA-34 · F25 FE 2a · LC ladder type** · *Ch. 9 cascades/ladders (?)*
- **Stem:** "What type of filter is this? Explain your reasoning in terms of the limiting behavior of the circuit's components at low and high frequency."
- **Key:** "Low-pass filter"
- **Answer:** At low ω the C's are open and L is a short, so $V_o = V_sR_L/(R_s+R_L)$. At high ω, $C_1$ and $C_2$ short their nodes and L opens, so $V_o\to0$ (third order: −60 dB/dec).

**SA-35 · F25 FE 2d · ω→0 check** · *Ch. 9*
- **Stem:** "Show that your expression for $\mathbf H(\omega)$ from part (c) yields the correct result for $\omega\to0$."
- **Key:** none printed.
- **Answer:** To first order the denominator is $j\omega L(1/R_s + 1/R_L)$, so $\mathbf H\to(1/R_s)/(1/R_s + 1/R_L) = R_L/(R_s+R_L)$: the DC divider with C open and L short.

**SA-37 · F25 FE 3e · $Z_{in}$ limits** · *Ch. 9 (?)*
- **Stem:** "Demonstrate that your result for part (d) is correct for $\omega\to0$ and $\omega\to\infty$."
- **Key:** none printed.
- **Answer:**
  - $\omega\to0$: $\mathbf Z_{in}\to1/(j\omega C_2)\to\infty$. At DC, $C_2$ is open and the op-amp input draws no current, so no current can flow.
  - $\omega\to\infty$: $\mathbf Z_{in}\to R_1$. $\lvert H\rvert\to0$ so $V_o\to0$, and $C_1$ shorts node A to $V_o$, so $I_s = V_s/R_1$.

**SA-38 · F25 FE 4c · boundary condition** · *Ch. 12 (final-only)*
- **Stem:** "Show that your result for $v_o(t)$ in part (b) satisfies the correct boundary condition for $v_o(t)$ at $t = 0$."
- **Key:** "$v_o(t)$ must be continuous at $t = 0$."
- **Answer:** $v_o$ equals the voltage on $C_2$ (and $v_A - v_o$ is the voltage on $C_1$). Capacitor voltages cannot jump with a finite input, so $v_o(0^+) = v_o(0^-) = 0$. Check: $0.10775 + 2.102\sin(-2.94°) \approx 0$.

---

## 11. Verification log and discrepancies

Method: sympy symbolic identity checks of every transfer function and impedance, nodal re-derivation of each op-amp circuit, scipy root-finding for every cutoff and bandwidth, numeric ODE or inverse-Laplace comparison for every time response. All other key values match to the printed precision.

> [!warning] F24 Final P3(d): exact bandwidth
> **Key: 200.3 rad/s. B1: 200.0 rad/s.** For $\mathbf H = Kj\omega/(a_0 + j\omega a_1 - \omega^2a_2)$ the half-power points satisfy $\omega^2a_2 \pm \omega a_1 - a_0 = 0$, whose roots differ by exactly $a_1/a_2 = (C_1+C_2)/(R_3C_1C_2) = 2\times10^{-3}/(10\cdot10^{-6}) = 200$. Root-finding gives cutoffs at 924.70 and 1124.70 rad/s. B1 believes 200 rad/s; the key's 200.3 is most likely rounded intermediate cutoffs. At 3 s.f. both read "200".

> [!warning] F23 Final P4(a): amplitude
> **Key: $1.2136\,e^{-100t}\cos(50t - 60.95°)$. B1: $1.2141$.** The exact result is $v_{out} = \tfrac{25}{212}[(5\cos50t + 9\sin50t)e^{-100t} - 5e^{-10t}]$, and $\tfrac{25}{212}\sqrt{106} = 1.21411$. With the key's 1.2136, $v_{out}(0) = -0.0003 \ne 0$, contradicting its own part (b). Rounding; both are 1.21 at 3 s.f. B1 believes 1.2141.

> [!warning] Transcript error: F23 Final Circuit FE-4
> `Transcripts/Exams/Final_F23_questions.md` and `Final_F23_short_answers.md` describe FE-4 as "$C_1$ → $R_1$ → − input; $R_2\parallel C_2$ feedback". **The page image shows a multiple-feedback circuit:**
> - $C_1$ runs from the source to node X.
> - $R_2$ runs from **node X** to the output.
> - $R_1$ runs from X to the − input.
> - $C_2$ runs from the − input to the output.
>
> The transcript topology gives real poles at −100 and −125 s⁻¹ and cannot produce the key's $e^{-100t}\cos 50t$. The MFB topology gives poles at $-100\pm j50$ and reproduces the key. B1 did not edit the transcripts (instructions: modify no other files). Someone should correct both FE-4 figure lines.

> [!warning] F23 SE2 P4(b) and F24 Final P3(b): where the band-pass peak sits
> Not an error, a convention. Both keys draw the peak at the exact $\lvert\mathbf H(\omega_0)\rvert$: 0 dB, and $+6.02$ dB $= 20\log\frac{R_3C_1}{R_1(C_1+C_2)}$. The intersection of the straight-line asymptotes is lower: −26.0 dB ($Q = 20$) and −8.13 dB. Follow the key's convention and label the peak value. The F24 FE "linear" bandwidth of 721 rad/s depends on it.

> [!warning] F24 Final P1(d): method choice
> **Key: "Fourier transform"** (no reasoning printed). B1's view: unilateral Laplace with initial conditions from the $t<0$ DC steady state ($v_C(0^-) = 5$ V, $i(0^-) = 0$) is at least as efficient. A constant for all $t<0$ has no ordinary Fourier transform (it needs $\pi\delta(\omega)$ terms). The key is what gets graded. Final-only, low priority for Exam 2.

Minor rounding, consistent at 3 s.f.:
- F24 Final P4(b): key 0.9453 and $7.138\times10^{-3}$ vs computed 0.94537 and $7.141\times10^{-3}$.
- F25 Final P4(b): matches to 4 s.f.
- F23 SE2 and F23 Final per-problem averages sum 0.3 below the printed means (§3).

Caller's figures checked:
- F23 SE2 mean 77.2, median 80, SD 15.1, n 66, P1–P4 20.3/19.5/18.2/18.9: **confirmed**.
- F24 SE2 mean 75.1, median 78.25, SD 13.8, n 36, P1–P4 18.2/15.7/23.3/17.8: **confirmed**.
- P1 part points 6/6/6/7 on both: **confirmed**.

---

## 12. Coverage and exclusions

**Viewed page by page** (59 PNGs at 90 dpi, plus 250 dpi crops of the F23 key Bode sketches and five op-amp figures; all PNGs deleted afterwards):
- F23 and F24 Exam 2 questions + histogram (3 + 3 pp) and short answers (3 + 3 pp).
- F23, F24 and F25 finals (4 + 5 + 5 pp) and their short answers (4 + 5 + 4 pp).
- The F26 SE2 template (20 pp).

**Read:** the 10 exam transcripts, `_FORMAT.md`, `SE1_F26_graded_Matthew.md`, `SE1_F26_histogram.md`, `SE1_F26_short_answers.md`, `problem_set_tips_F26.md`, `Semester Exam 1 details.txt`, and the Discord scrape.

**Not opened, by rule:**
- Anything F25 + Exam 2/SE2.
- `Transcripts/INDEX.md`, `.tutor/`.
- Lecture notes, the syllabus PDF, `PS8_problems.md`.

Consequences:
- Section-level lecture attributions are (?).
- The F25 twin check is deferred to the F25 format reader.
