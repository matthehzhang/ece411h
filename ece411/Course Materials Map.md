# ECE 411H (Fall 2026, Unique 18535): materials inventory for Semester Exam 1

> **Correction 2026-11-06:** `course_files_export.zip` DID contain 36 MP4s (all Ulaby/NR problem-solving videos and the two refresher sessions). They have been extracted to `Problem Solving Videos/` and `Refreshers/` and the zip deleted. Image-only PDFs for the Exam 2 and final units are now transcribed in `../Transcripts/` (see its INDEX.md); originals are in `../_sources_transcribed/`. Root was reorganised the same day: `Admin/`, `Recitations/`, `Labs/`, `Problem Sets/{official,submitted_work}`, `TUTOR_PROMPT.md` renamed `TUTOR_PROMPT_MT1.md`.


> [!warning] Scope update (Ed Yu, 9/28 and 9/30 lectures): **maximum power transfer (§8-5) and semiconductors/devices are NOT on Exam 1.** Exam 1 ends at power factor. Lecture notes now exist in [[Lectures]] (9 of 11 lectures; 9/16 and 9/23 are missing). Anything below that says otherwise predates this.


Root: ``. Inventory date: 2026-10-04. `Exam Preparation Materials/` was excluded because another agent covers it. No videos were watched; captions (.vtt) were skimmed instead.

Exam 1: **Wed 10/07/2026, in class, 75 min.** Coverage is Ulaby Ch 1–8. The lecture schedule puts most of the weight on Ch 4–8, and Ch 1–3 are ECE 302 review.

---

## 0. Headline findings

1. **Problem numbering in the local textbook PDF does not always match the course's numbering.** The course's problem sets, the official solutions (© 2016 NTS solution manual) and the problem-solving videos use the NTS/print numbering. `Textbook/CAD_3rd_ed_OA.pdf` (the Michigan open-access version) is shifted by one for several problems:
   - PS1 "3.22" = OA **3.21**
   - PS1 "5.16" = OA **5.15**
   - PS4 "7.2" = OA **7.1**
   - PS4 "7.7" = OA **7.8**
   - PS4 "7.21" = OA **7.22**
   - PS5 "8.20" = OA **8.19**
   - Video "6.48" = OA **6.47** (OA 6.48 is a different circuit)

   All other assigned and video problems match by number. Problems were matched by text and circuit values. **A tutor that says "see Problem X.YY" must give the OA number.**
2. **No lecture notes or slides exist anywhere locally**, and the Canvas export does not include any. Lectures are in person in ECJ 1.222, simulcast on Zoom and recorded. The only instructor handwritten notes on disk are the refresher "Recorded session notes", which look like OneNote/tablet notes. That suggests lectures are handwritten-on-tablet, but the syllabus never says. The syllabus says a lecture-by-lecture "Lecture Topics" summary is kept in **Canvas → Discussions**, and that file is not on disk.
3. **No problem set covers power factor (§8-4) or ac maximum power transfer (§8-5).** PS5 covers rms, complex power and op-amp ac power only. The only resources for these two topics are the **8.52 video** (ac maximum power transfer) and **Recitation 3** (power factor and Z_L = Z_Th*).
4. **The 10/05 lecture (two days before the exam) is "Semiconductors and solid-state devices", with reading "none".** The 10/05 recitation is "Semester Exam 1 review". Whether semiconductors are on Exam 1 is undetermined. Past Exam 1 papers in Exam Prep (the other agent) should settle it.
5. **The video for 7.68 says the book's printed answer is wrong** (off by a sign, i.e. 180°).
7. The PS4 official solutions (`ECE_411H_PS4_solns_F26.pdf`, 12 pp) are **rasterized images with no text layer**, so they need OCR or vision. The PS1–3 solutions have extractable text.

---

## 1. Syllabus (`ECE 411H syllabus F26.pdf`, 6 pp)

### People and logistics

| Item | Details |
|---|---|
| Instructor | Ed Yu, <email removed>, EER 3.802 (also MER 2.206B at Pickle) |
| TA | Darsh Shah (<email removed>). UGA: none |
| Lectures | MW 9:00–10:30 AM, ECJ 1.222, simulcast on Zoom (<link removed>) |
| Recordings | "All class sessions will be recorded … All class recordings will be made available to all students for the entire semester." Students may not record. |
| Instructor office hours | MW 10:30–11:55 AM, or by appointment, in EER 3.802 |
| TA office hours | Posted on Canvas |
| Lab / recitation | Mon 1:00–3:00 PM. Recitation in EER 0.818, lab in EER 1.828. In person only. |
| Text | Ulaby, Maharbiz & Furse, *Circuit Analysis and Design* 3rd ed. (Michigan Publishing, 2025), stated to be the same as *Circuits* 3rd ed. (NTS, 2016) |
| Supplementary texts | Alexander & Sadiku; Horowitz & Hill; **Nilsson & Riedel** (source of the NR_4-xx videos); Oppenheim & Willsky |

There is no mention of slides, handouts per lecture, or whiteboard format. The only lecture-content artifact mentioned is the "Lecture Topics" thread in Canvas Discussions.

### Grading

| Component | Weight |
|---|---|
| Homework | 5% |
| Laboratory | 10% |
| Semester exams | 50% (2 × 25%) |
| Final | 35% |

Each component is curved, and final grades use +/-.

Exam grading (quote): "For exam problems, reasoning and analysis are typically as or more important than the final answer. You should explain your reasoning clearly and show all work. Be sure to erase or cross out any work you do not want to be considered in grading. If you demonstrate mastery of the key concepts required to solve a problem, you will receive substantial credit even if the final answer is not completely correct. Conversely, a correct final answer without explanation or justification will typically receive very limited credit." Regrade requests must be in writing within one week, and the whole exam may be regraded up or down.

### Examinations (quote)

"In general you will be allowed to use a calculator, writing implements and erasers, and the exam question/answer sheets during exams. Any other allowed materials will be specified in advance of each exam. All exams will be in-person, and your exam solutions must be personally written by you, in pen or pencil, on paper exam solution sheets. Writing exam solutions on tablets or other electronic devices will not be allowed."

The dummy exam template is in the zip root (`ECE 411H dummy exam template F26.pdf`, also in Exam Prep). Its rules:
- "The exam questions, answer sheets, and a calculator are allowed; no other materials should be consulted during the exam." The exam is closed-book with **no formula sheet** unless announced.
- "You will have 70 minutes from the start of the exam to complete the exam, followed by ~5 minutes to scan and upload your exam answer sheets to Gradescope."
- Assume 3 significant figures. Show all work. State assumptions explicitly.
- **Only the front side of each sheet is graded.** Answers go in a box per part ("Your answer for Question 1, part (a)").

### Policy on Collaboration (exact)

> Discussion of course material and homework problems is permitted (and encouraged!). However, each student should work through the homework problems (and write up their solutions) independently. For additional details please see the section of this syllabus on Policy on Academic Integrity.

### Course Policy on AI: operative paragraphs (exact)

> Our course policy with respect to AI is as follows. You are allowed to use any AI tool available to you to help explain concepts in circuits or electrical engineering, to identify useful approaches to specific problems in the course, to obtain feedback on solutions you have worked out yourself, or to obtain solutions to problems not assigned as homework. You are not allowed to use AI to obtain worked solutions to assigned homework problems. And you should strive to think deeply and thoroughly about anything you glean from your use of AI.

> To help guide your use of AI, I developed (in spare time waiting at airports during early summer 2026) an "AI circuit tutor" tool you can use via your UT-provided access to ChatGPT. The tool provides conceptual explanations relevant to circuits and electrical engineering and guidance on approaches (but not worked solutions) to problems in circuits and related areas, and it has immediate access to the full text of our textbook by Ulaby et al., including all the problems in the book. It has also been instructed to use terminology and notation consistent with Ulaby et al., and to confine its responses to circuits, electrical engineering, and closely related topics. The tool is available here: https://chatgpt.com/agents/a/agt_6a3aa0ae001c8191ae9a61d041518d54 .

The surrounding "philosophy" paragraphs are about "known knowns" and "unknown unknowns" and are not operative. One sentence from them is worth keeping: "Excessive use of AI, e.g., to provide solutions to homework problems, will prevent you from developing this understanding. However, AI can be a very useful tool for clarifying conceptual understanding or obtaining guidance in, e.g., working out homework problems."

### Homework (exact)

> ECE 411H course policy is that discussion of course material, including homework problems, is allowed and indeed encouraged. However, each student should work through assigned homework problems and write up their solutions independently. Problem-solving is an extremely useful skill in itself, and in addition is the only really effective way to learn the material!
> Specifically, each student is responsible for working out and writing up their own solutions to each homework assignment. Discussion of the course material and problems is encouraged, but practices such as allowing a classmate to copy your homework solutions, or a group working out a problem solution together which everyone then copies down and turns in, are forbidden. Use of problem solutions obtained from other students, over the web, via AI, etc. is forbidden. Students violating course policy on homework will receive a warning possibly followed by a grading penalty and further disciplinary action, in accordance with university policy.

Problem sets are due online at the start of class. No late work is accepted. Solutions are posted on the due date, typically at 6:00 PM Central.

### Tentative lecture schedule (exact rows)

| Date(s) | Topic | Reading (Ulaby) |
|---|---|---|
| 08/24/2026– | First class meeting; introduction and review | |
| 08/26/2026 | Review of first-order circuits, operational amplifiers | |
| 08/31–09/02 | Operational amplifiers and op-amp circuits | Ch 1–5 |
| 09/09 | Op-amp circuits; RLC circuits | Ch 6 |
| 09/14–09/16 | RLC circuits; sinusoidal (ac) circuit analysis, phasors | Ch 6, Ch 7 |
| 09/21–09/23 | Phasor circuit analysis; power in ac circuits | Ch 7, Ch 8 |
| 09/28–09/30 | Power in ac circuits | Ch 8 |
| **10/05** | **Semiconductors and solid-state devices** | **none** |
| **10/07/2026** | **Semester Exam 1** | |
| 10/12–10/14 | Semiconductors and solid-state devices; intro to filters | Ch 9 |
| 10/19–10/21 | Passive filter circuits and Bode plots | Ch 9 |
| 10/26–10/28 | Active filter circuits | Ch 9 |
| 11/02–11/04 | Laplace transforms | Ch 12 |
| 11/09 | Laplace (cont.) | Ch 12 |
| 11/11/2026 | Semester Exam 2 | |
| 11/16–11/18 | Laplace and circuit analysis | Ch 12 |
| 11/23–11/25 | Thanksgiving | |
| 11/30–12/02 | Fourier series and transforms | Ch 13 |
| 12/07 | Fourier transforms, two-ports (if time) | Ch 13 |
| TBD | Final | |

---

## 2. Problem Sets (`Problem Sets/`)

The problem-set PDFs are pasted textbook screenshots, so the problem text is images. Problem numbers below are the **course/NTS numbers**, with the OA PDF number added where it differs.

### PS1: due We 09/09, review (Ch 3, 5)

| # | Topic | Textbook problem | OA PDF page |
|---|---|---|---|
| 1 | Node analysis with dependent source (find V_L) | 3.22 (**OA 3.21**) | 183 |
| 2 | Node analysis, supernode (Va, Vb, Vc) | 3.25 | 183 |
| 3 | Thévenin equivalent, then choose R_L | 3.66 | 190 |
| 4 | Max power transfer (bridge, dc) | 3.82 | 192 |
| 5 | Capacitor voltages under dc conditions | 5.16 (**OA 5.15**) | 332 |
| 6 | RC transient i(t) | 5.41 | 335 |

### PS2: due Mo 09/14, op-amps (Ch 4, 5)

| # | Topic | Textbook problem | OA PDF page |
|---|---|---|---|
| 1 | Bridge + inverting amp (Thévenin of the bridge) | 4.10 | 252 |
| 2 | Variable-gain amp (potentiometer βR) | 4.22 | 253 |
| 3 | Design: v_o = 3v1+4v2−5v3−8v4, all resistors integer multiples of 1 kΩ | 4.33 | 254 |
| 4 | Multiple op-amp feedback | 4.47 | 256 |
| 5 | RC op-amp step response | 5.64 | 339 |
| 6 | Two-stage RC op-amp (Vcc = 10 V, saturation) | 5.68 | 339 |

### PS3: due Mo 09/21, RLC (Ch 6)

| # | Topic | Textbook problem | OA PDF page |
|---|---|---|---|
| 1 | Initial and final conditions | 6.9 | 390 |
| 2 | Series RLC: v_C(t), i_L(t) | 6.12, 6.13 (same figure) | 391 |
| 3 | Parallel RLC (SPDT switch): i_L, i_C | 6.36 | 394 |
| 4 | General RLC: ODE for i_L, switch closed at 0 and reopened at 0.5 s | 6.55 | 397 |
| 5 | RLC op-amp: multiple-feedback bandpass filter | 6.58 | 397 |
| 6 | Custom: buck converter (Vg = 5 V, L = 1 mH, C = 50 µF, R_L = 100 Ω). Initial conditions, v_o(t), τ and 4τ settling, MOSFET overvoltage, max f_sw, duty cycle D giving avg v_o = D·Vg | none | |

The official solution for PS3 problem 6 says: "please see Darsh Shah, our TA, for discussion pertaining to the comments in the solutions to this problem."

### PS4: due Mo 09/28, sinusoids and phasors (Ch 7)

| # | Topic | Textbook problems | OA PDF page |
|---|---|---|---|
| 1 | Sinusoidal signals | 7.2 (**OA 7.1**), 7.7 (**OA 7.8**) | 459 |
| 2 | Complex algebra | 7.10 (a–c), 7.11 (a–d), 7.17 (a–c) | 459–460 |
| 3 | Phasors | 7.21 (**OA 7.22**), 7.23, 7.28 | 460–461 |
| 4 | Phasor analysis 1: find i_s(t), RLC, ω = 5×10⁴ | 7.31 | 461 |
| 5 | Phasor analysis 2: ω at which i is in phase with v_s | 7.45 | 464 |
| 6 | Phasor nodal: find i_C(t) | 7.58 | 466 |

The official solutions are image-only, 12 pp.

### PS5: due **Mo 10/05/2026 at the start of class (9 AM)**, ac power (Ch 8). Not yet solved; do not solve.

| # | Topic | Textbook problem | OA PDF page |
|---|---|---|---|
| 1 | Average and rms of periodic signals (\|12cos\|, 4+6cos, 2cos−4sin, 9cos·sin) | 8.16 | 503 |
| 2 | Complex power for each passive element plus conservation check; v = 40cos(10⁵t), R1 = 100, R2 = 500, C = 0.1 µF, L = 0.5 mH | 8.20 (**OA 8.19**) | 503 |
| 3 | S for an RL load (I_s = 4∠0°, Z_C = −j20, Z_L = j20) | 8.27 | 505 |
| 4 | Ac power to R_L in an op-amp circuit (v_in = 0.5cos2000t) | 8.38 | 507 |
| 5 | Custom: inductor ESR loss with a triangular ripple current (baseline I, ripple rI). (a) instantaneous and average power in R; (b) in R_ESR; (c) loss ratio when L doubles (r ∝ 1/L, r = 0.2 originally, R_ESR rises 40%) | none | |

Official PS5 solutions should appear about 6 PM on 10/05.

### `ECE 411H problem set tips F26.pdf` (3 pp)

Covers the purposes of problem sets, retrospection after solving, rewriting solutions neatly, and the claim that copying solutions inflates the 5% homework grade at the expense of the 85% exam grade. It then shows annotated excellent, marginal, poor and unacceptable write-ups of **Ulaby 2.25**. The rubric:
- labeled diagram
- a sentence on which law is applied
- boxed answers with units
- no bare numerical answers
- intended answer clearly marked

This rubric is the exam write-up standard and the tutor should enforce it.

## 3. Recitations (TA handwritten Xournal notes, 3 pp each) and Refreshers

| File | Topics | Exam 1? |
|---|---|---|
| Recitation1 (8/24) | KCL/KVL sign conventions, node and mesh procedure (worked "70. Solve for" with a dependent source), supermesh/source conversion, Thévenin/Norton process | Yes (Ch 2–3 review) |
| Recitation2 (8/31) | Op-amp with finite open-loop gain A (v_o = A/(1+A)·v_i; A→∞ limit), buffer, inverting and non-inverting derivation with finite A, **instrumentation amplifier (INA)** and a current-sense application (shunt → INA) | Yes (Ch 4) |
| Recitation3 (9/28) | Series RLC step (L = 1 mH, R = 10 mΩ, C = 10 µF; char. eqn), instantaneous power, **rms** of sine and square wave (A/√2), phasors (d/dt → jω), impedance (ω→0 / ∞ limits), RLC phasor divider, **complex power S = P + jQ = V·I\***, **power factor**, **max power transfer Z_L = Z_s\*** | Yes (Ch 6–8). Closest thing to a Ch 8 lecture summary. |
| Refreshers/ECE 411H complex numbers-algebra 1 F26.pdf (3 pp, typed) | Rectangular/polar, conjugate, \|z\| = √(zz\*), complex plane, add in rectangular, multiply/divide in polar | Yes (Ch 7 math) |
| Refreshers/ECE 411H complex numbers-algebra 2 F26.pdf (3 pp, typed) | Rationalizing complex transfer functions into "standard" form, limits as ω→0/∞, phase of quadratic poles/zeros | Partly. Standard-form manipulation is useful for Ch 7–8; quadratic-pole phase is Ch 9 Bode. |
| Refreshers/ECE_411H_sinusoids+complex-num_refresher_F26.mp4 (43.5 min) + `_notes_F26.pdf` (4 pp handwritten) | Sinusoids (Ulaby §7-1): amplitude, ω, T, phase, lead/lag, cosine-standard form (positive amplitude, phase in (−180°, 180°]), complex numbers (§7-2), Euler | Yes |
| Refreshers/Sinusoids-phasors_review_ETY.pdf (8 pp scanned handwriting, "review from ECE 302/302H") | Sinusoids, complex numbers, RC with sinusoidal input by time-domain ODE, then phasors, impedance of R/L/C, phasor-domain RC, magnitude/phase, decibels and log-log plotting preview | Yes (Ch 7; the dB part is Ch 9) |
| Refreshers/Semiconductors_review_ETY.pdf (6 pp scanned, "from ECE 302/302H") | Conductivity, mobility, J = σE, Si lattice, electrons/holes, n_i, doping (n/p type), MOSFET structure, threshold voltage, I_D(sat) = k(V_GS−V_th)², I_D–V_DS curves, MOSFET as VCCS; Streetman refs | Uncertain. This matches the 10/05 lecture (reading "none"), two days before the exam. See §4-11 (PDF 234) and Lab 3. |
| Refreshers/ECE_411H_integral-transforms_F26.mp4 (63.8 min) + `_notes_F26.pdf` (5 pp) | Laplace/Fourier integral transforms | No (Ch 12–13) |
| Refreshers/ECE_411H_Laplace_Transforms_F25/F26.pdf, Fourier_Transforms_F25/F26.pdf (2 pp each; image tables) | Transform pair/property tables | No |

---

## 4. Problem Solving Videos (`Problem Solving Videos/`)

These are recorded by the instructor in May–June 2023. Each Ulaby video has a handwritten OneNote PDF (2–7 pp, image-only) and a .vtt caption file. Every video ends with a "retrospective / key points" segment. The NR_* videos have **no PDF and no captions**. They are Nilsson & Riedel problems 4.64/4.77/4.83 (Ch 4 of N&R = analysis techniques).

| Video | OA # (if different) | Length | Topic / what it covers | Key takeaway (from captions) | Exam 1 |
|---|---|---|---|---|---|
| NR_4-64_Norton | n/a | 16 min | Norton equivalent (N&R 4.64) | (no captions) | Yes (§3-6) |
| NR_4-77_Thevenin | n/a | 22 min | Thévenin equivalent (N&R 4.77) | (no captions) | Yes (§3-6) |
| NR_4-83_power_transfer_2 | n/a | 25 min | Max power transfer, dc (N&R 4.83) | (no captions) | Yes (§3-8) |
| Ulaby Sec 4-9 instrumentation amplifier | n/a | 31 min | Multi-op-amp analysis of the INA (§4-9) | Analyze each op-amp; should also check intermediate outputs vs supply rails | Yes |
| Ulaby 5.36 | same (PDF 334) | 21 min | First-order RC, switch moves 1→2 (I0 = 21 mA, 2k/3k/4k, 50 µF) | Initial condition from continuity of v_C (i_L); form ODE; fit one constant | Yes |
| Ulaby 5.50 | same (336) | 21 min | RL with two inductors (10 Ω/40 Ω, 1 H …) | First-order despite two L's because the inductor currents are independent | Yes |
| Ulaby 5.65 | same (339) | 21 min | RC op-amp (R3‖C feedback) step input A·u(t) | Homogeneous solution = transient; particular = t→∞ | Yes |
| Ulaby 5.71 | same (339) | 17 min | Three-op-amp loop simulating dv/dt + 5v = 10v_s | Analyze along the signal path (or backwards) to simplify the algebra | Yes |
| Ulaby 6.10 | same (391) | 16 min | Initial and final conditions in RLC (24 V, 12 Ω) | You need both x(0) and dx/dt(0) for second order | Yes |
| Ulaby 6.18 | same (392) | 42 min | Source-free series RLC, i_C(t) (30 V, 2/12/4 Ω, 4 H, 0.64 F) | Solve for v_C (pure ODE), then i_C = C dv_C/dt | Yes |
| Ulaby 6.37 | same (394) | 44 min | Parallel RLC with sources present at t→∞ (24 V, 6 A, 3 Ω, 2 mH, 0.5 mF) | Particular integral gives the t→∞ value; homogeneous gives the transient | Yes |
| Ulaby 6.48 | **OA 6.47** (396) | 59 min | RLC with two switchings (closed 0, open 1 ms; 20 V, 200 Ω, 2.5 H, 2.5 µF) | Solve an intermediate variable (i_L), then get i_C; know overdamped/critical/underdamped forms cold | Yes |
| Ulaby 6.54 | same (396) | 56 min | Harder general second-order (Is = 0.2 A, Rs = 30, …, L = 4 H, C = 5 mF) | Transient vs steady-state decomposition | Yes |
| Ulaby 6.59 | same (397) | 50 min | Second-order op-amp (two-pole Sallen-Key-type LPF), step input | dv_out/dt(0) initial condition needs extra reasoning | Yes |
| Ulaby 7.32 | same (461) | 25 min | Simple phasor analysis: v_ab with i_s = 35sin(300t−15°) mA, 80 Ω, 15 mH, 200 µF | Convert sin → cosine standard form; e^{±j180°} = −1 | Yes |
| Ulaby 7.47 | same (464) | 23 min | Phasor Thévenin impedance plus a matching element to make Z_Th real | Test-source method for Z_Th; complex-number fluency | Yes |
| Ulaby 7.68 | same (467) | 34 min | Phasor nodal analysis, i_x (v_s = 6cos5×10⁵t, 0.1/0.2 Ω, 20 µF caps) | **The book's answer is wrong (sign / 180°)** | Yes |
| Ulaby 8.23 | same (504) | 27 min | Average power per element (60cos4000t, 200 Ω, 100 Ω, 2.5 µF) | Passive sign convention: P < 0 means supplied | Yes |
| Ulaby 8.29 | same (505) | 21 min | Average power in R_L via **phasor source transformations** (100∠0, 1k, 0.6k, j0.8k, −j0.5k, 3k) | All dc techniques carry over to phasors | Yes |
| Ulaby 8.52 | same (510) | 30 min | **ac max power transfer**: Z_L = Z_Th*, P_max (6∠0 V, 1 Ω, j2, 2 Ω, −j2) | Redraw to expose topology; derive power expressions | Yes (only §8-5 resource) |
| Ulaby 9.4, 9.19, 9.33, 9.37 | n/a | 11–93 min | Ch 9 frequency response / filters | n/a | No (Exam 2) |
| Ulaby 12.5, 12.10, 12.14, 12.15, 12.37 | n/a | 33–67 min | Ch 12 Laplace | n/a | No |
| Ulaby 13.16, 13.20, 13.31, 13.44, 13.49 | n/a | 21–59 min | Ch 13 Fourier | n/a | No |

---

## 5. Labs (`Lab Documents/`, `Lab3_Prelab/`)

The schedule comes from `ECE 411H Lab-Recitation schedule F26.pdf`. All sessions are Monday.

| Date | Activity | Report due |
|---|---|---|
| 08/24 | Recitation (Rec1) | n/a |
| 08/31 | Recitation (Rec2) | n/a |
| 09/07 | none (Labor Day) | n/a |
| 09/14 | **Lab 1: Op-Amp Circuits** | 09/21 |
| 09/21 | **Lab 2: RC & RL Circuits, First-Order Filters** | 09/28 |
| 09/28 | Recitation (Rec3) | n/a |
| **10/05** | **Recitation: Semester Exam 1 review** | n/a |
| 10/12 | Recitation | n/a |
| 10/19 | Lab 3: MOSFET Characteristics and Basic Amplifiers | 10/26 |
| 10/26–11/30 | Labs 4–6 (RLC 2nd-order filters; active filters; op-amp oscillators) | n/a |

What the lab manual (`ECE_411H_Lab_Manual_F26.pdf`, 90 pp) covers:
- **Lab 1** (manual p. 5): ideal op-amp model (R_in, R_out, A), summing/difference amp hand analysis, input/output range and saturation, TLV2372 in LTspice, inverting amp with varied feedback R, linear range and saturation measurement, four-input summing amp mixing audio (`Lab2_mixed_audio.mp3`).
- **Lab 2** (p. 16): RC/RL time constants from a square-wave response, capacitor/inductor impedance, input impedance, transfer function V_out/V_in, magnitude limits as ω→0/∞, cutoff frequency, frequency-response sweep. This links to §5-4/5-5 and previews Ch 9.
- **Lab 3** (p. 31, after the exam): 2N7000 MOSFET I_D–V_GS and I_D–V_DS, common-source gain, headphone amp.
- Other files: datasheets (tlv2372, tlc2272, STX3120 headphone jack) and `2N7000.REV0.LIB`.

---

## 6. Textbook: `Textbook/CAD_3rd_ed_OA.pdf` (779 pp)

**Offset: PDF page = printed page + 15.** This was verified three ways:
- the embedded page labels (printed 1 → PDF 16, 459 → 474, 743 → 758);
- PDF 411 shows the "7-3 Phasor Domain" heading on printed p. 396;
- PDF 482 shows "8-3 Complex Power" on printed p. 467.

The PDF outline has chapter bookmarks only. The printed TOC calls the answers "Appendix F", but the body and bookmarks call it **Appendix G (Answers to Selected Problems), PDF 758–763**. Appendix D (Mathematical Formulas) is PDF 751 and Appendix B (Simultaneous Equations) is PDF 744.

Format: section (printed p. → **PDF p.**)

**Ch 1 Circuit Terminology** (1 → **16**)
- Overview 2→17
- 1-1 Historical Timeline 4→19
- 1-2 Units, Dimensions, Notation 9→24
- 1-3 Circuit Representation 15→30
- 1-4 Electric Charge and Current 20→35
- 1-5 Voltage and Power 25→40
- 1-6 Circuit Elements 35→50
- Summary 41→56
- Problems 42→57–64 (1.1–1.48)

**Ch 2 Resistive Circuits** (50 → **65**)
- 2-1 Ohm's Law 51→66
- 2-2 Kirchhoff's Laws 60→75
- 2-3 Equivalent Circuits 67→82
- 2-4 Wye–Delta 80→95
- 2-5 Wheatstone Bridge 84→99
- 2-6 Linear vs Nonlinear i–v 86→101
- 2-7 Multisim 94→109
- Summary 100→115
- Problems 101→116–129 (2.1–2.80)

**Ch 3 Analysis Techniques** (115 → **130**)
- 3-1 Linear Circuits 116→131
- 3-2 Node-Voltage Method 117→132
- 3-3 Mesh-Current Method 123→138
- 3-4 By-Inspection Methods 129→144
- 3-5 Linearity and Source Superposition 133→148
- 3-6 Thévenin and Norton Equivalents 140→155
- 3-7 Comparison of Methods 151→166
- 3-8 Maximum Power Transfer 151→166
- 3-9 App Note: BJT 158→173
- 3-10 Nodal Analysis with Multisim 161→176
- Summary 164→179
- Problems 165→180–197 (3.1–3.103)

**Ch 4 Operational Amplifiers** (183 → **198**)
- 4-1 Op-Amp Characteristics 184→199
- 4-2 Negative Feedback 195→210
- 4-3 Ideal Op-Amp Model 196→211
- 4-4 Inverting Amplifier 198→213
- 4-5 Inverting Summing Amplifier 200→215
- 4-6 Difference Amplifier 206→221
- 4-7 Voltage Follower/Buffer 208→223
- 4-8 Op-Amp Signal-Processing Circuits 209→224
- 4-9 Instrumentation Amplifier 214→229
- 4-10 DAC 216→231
- 4-11 MOSFET as Voltage-Controlled Current Source 219→234
- 4-12 Neural Probes 229→244
- 4-13 Multisim 230→245
- Summary 235→250
- Problems 236→251–262 (4.1–4.71)

**Ch 5 RC and RL First-Order Circuits** (248 → **263**)
- 5-1 Nonperiodic Waveforms 250→265
- 5-2 Capacitors 258→273
- 5-3 Inductors 269→284
- 5-4 Response of the RC Circuit 275→290
- 5-5 Response of the RL Circuit 287→302
- 5-6 RC Op-Amp Circuits 295→310
- 5-7 Parasitic Capacitance and Computer Speed 305→320
- 5-8 Multisim 310→325
- Summary 313→328
- Problems 314→329–344 (5.1–5.83)

**Ch 6 RLC Circuits** (330 → **345**)
- 6-1 Initial and Final Conditions 331→346
- 6-2 Introducing the Series RLC 334→349
- 6-3 Overdamped (α > ω0) 341→356
- 6-4 Critically Damped 346→361
- 6-5 Underdamped 348→363
- 6-6 Summary of Series RLC Response 349→364
- 6-7 Parallel RLC 353→368
- 6-8 General Solution for Any 2nd-Order Circuit with dc Sources 359→374
- 6-9 Multisim 369→384
- Summary 373→388
- Problems 374→389–399 (6.1–6.70)

**Ch 7 ac Analysis** (385 → **400**)
- 7-1 Sinusoidal Signals 386→401
- 7-2 Review of Complex Algebra 389→404
- 7-3 Phasor Domain 396→411
- 7-4 Phasor-Domain Analysis 400→415
- 7-5 Impedance Transformations 403→418
- 7-6 Equivalent Circuits 410→425
- 7-7 Phasor Diagrams 413→428
- 7-8 Phase-Shift Circuits 416→431
- 7-9 Phasor-Domain Analysis Techniques 420→435
- 7-10 ac Op-Amp Circuits 429→444
- 7-11 Op-Amp Phase Shifter 431→446
- 7-12 Power-Supply Circuits 432→447
- 7-13 Multisim 437→452
- Summary 443→458
- Problems 444→459–473 (7.1–7.93)

**Ch 8 ac Power** (459 → **474**)
- 8-1 Periodic Waveforms 460→475
- 8-2 Average Power 463→478
- 8-3 Complex Power 467→482
- 8-4 The Power Factor 472→487
- 8-5 Maximum Power Transfer 476→491
- 8-6 Multisim 482→497
- Summary 485→500
- Problems 486→501–514 (8.1–8.68)

### Structure of the in-chapter and end-of-chapter material

The chapter body has three kinds of numbered items:
- **Examples** ("Example 7-3:", worked): Ch1 9, Ch2 19, Ch3 17, Ch4 11, Ch5 19, Ch6 13, Ch7 22, Ch8 7.
- **Exercises** ("Exercise 7-1:", with the "Answer:" printed inline right after): Ch1 9, Ch2 14, Ch3 15, Ch4 12, Ch5 18, Ch6 15, Ch7 17, Ch8 6. These are good for quick drills because the answer is self-contained.
- **Concept Questions** ("Concept Question 7-4:", qualitative, no answers): Ch1 13, Ch2 18, Ch3 18, Ch4 25, Ch5 27, Ch6 9, Ch7 18, Ch8 13. They are good for short-answer exam prep.

Each technology brief (TB) is a sidebar and not exam material.

End of each chapter: a Summary (Concepts, Mathematical and Physical Models table, Important Terms), then Problems grouped by section headers. Problems marked ∗ have answers in Appendix G: Ch1 6, Ch2 20, Ch3 33, Ch4 17, Ch5 21, Ch6 21, Ch7 22, Ch8 20.

Problem-number ranges by section (approximate, ±1 at boundaries):

| Chapter | Section group | Problems |
|---|---|---|
| 3 | §3-2 node | 3.1–3.25 |
| 3 | §3-3 mesh | 3.26–3.51 |
| 3 | §3-4/3-5 by-inspection, superposition | 3.52–3.63 |
| 3 | §3-6 Thévenin/Norton | 3.64–3.80 |
| 3 | §3-8 max power | 3.81–3.88 |
| 4 | §4-1/4-2 | 4.1–4.8 |
| 4 | §4-3/4-4 | 4.9–4.25 |
| 4 | §4-5/4-6 | 4.26–4.39 |
| 4 | §4-8 | 4.40–4.54 |
| 4 | §4-9/4-10 | 4.55–4.58 |
| 4 | §4-11 MOSFET | 4.59–4.61 |
| 5 | §5-1 | 5.1–5.7 |
| 5 | §5-2 C | 5.8–5.22 |
| 5 | §5-3 L | 5.23–5.32 |
| 5 | §5-4 RC | 5.33–5.45 |
| 5 | §5-5 RL | 5.46–5.58 |
| 5 | §5-6 RC op-amp | 5.59–5.72 |
| 6 | §6-1 | 6.1–6.11 |
| 6 | §6-2..6-6 series | 6.12–6.35 |
| 6 | §6-7 parallel | 6.36–6.46 |
| 6 | §6-8 general | 6.47–6.59 |
| 7 | §7-1 | 7.1–7.8 |
| 7 | §7-2 | 7.9–7.20 |
| 7 | §7-3..7-5 | 7.21–7.45 |
| 7 | §7-6 | 7.46–7.50 |
| 7 | §7-7/7-8 | 7.51–7.55 |
| 7 | §7-9 (incl. ac op-amp) | 7.56–7.83 |
| 8 | §8-1 | 8.1–8.16 |
| 8 | §8-2/8-3 | 8.17–8.44 |
| 8 | §8-4 PF | 8.45–8.50 |
| 8 | §8-5 max P | 8.51–8.60 |

---

## 7. `course_files_export.zip` (Canvas export, 144 entries)

Everything in it is already extracted locally:
- Lab Documents
- PS1–PS4 problem PDFs
- every Problem Solving Video file
- the root PDFs (syllabus, tips, refreshers)
- Exam Prep F23/F24/F25 files

The one exception is `ECE 411H dummy exam template F26.pdf`, which sits at the zip root and is present locally only inside `Exam Preparation Materials/`. Its contents are summarized in §1.

**The zip contains no lecture notes, slides or recordings.** PS5, all problem-set solutions, the recitation PDFs, the textbook and the `_F25` Laplace/Fourier tables in `Refreshers/` were downloaded separately. They are not in the 09-17 export.

---

## 8. Topic → best resources for Exam 1

"OA" is the textbook PDF numbering; PDF pages are absolute.

| Topic | Textbook (§, PDF pp) | Problem sets (course # → OA #) | Videos | Recitation / refresher / lab | Extra practice (OA, ∗ = answer in App. G) |
|---|---|---|---|---|---|
| KCL/KVL, node/mesh, supernode, dependent sources | §2-2 (75), §3-2 (132), §3-3 (138), §3-4/3-5 (144–154) | PS1 #1 (3.22 → OA 3.21), #2 (3.25) | none | Rec1 | ∗ items in 3.1–3.51 |
| Thévenin/Norton, source transformation | §3-6 (155–165) | PS1 #3 (3.66); PS2 #1 (4.10, Thévenin of a bridge) | NR_4-64 Norton, NR_4-77 Thévenin | Rec1 | 3.64–3.80 |
| dc max power transfer | §3-8 (166–172) | PS1 #4 (3.82) | NR_4-83 | none | 3.81–3.88 |
| Ideal op-amp: inverting, non-inverting, summing, difference, follower | §4-2–4-8 (210–228) | PS2 #1–#4 (4.10, 4.22, 4.33, 4.47) | none | Rec2 (finite-A derivation); Lab 1 | 4.9–4.54 |
| Instrumentation amp, multi-op-amp circuits | §4-9 (229) | PS2 #4 (4.47) | Sec 4-9 INA | Rec2 (INA, current sense) | 4.55–4.58 |
| Capacitors, inductors, energy, series/parallel, dc steady state | §5-2 (273), §5-3 (284) | PS1 #5 (5.16 → OA 5.15) | none | none | 5.8–5.32 |
| First-order RC/RL transients (switching, τ, x(∞)+[x(0)−x(∞)]e^{−t/τ}) | §5-1 (265), §5-4 (290), §5-5 (302) | PS1 #6 (5.41) | 5.36, 5.50 | Lab 2 | 5.33–5.58 |
| RC op-amp circuits (integrator, differentiator, saturation) | §5-6 (310) | PS2 #5 (5.64), #6 (5.68) | 5.65, 5.71 | none | 5.59–5.72 |
| RLC initial/final conditions (incl. derivatives) | §6-1 (346) | PS3 #1 (6.9) | 6.10 | none | 6.1–6.11 |
| Series RLC: α, ω0, over/critical/underdamped | §6-2–6-6 (349–367) | PS3 #2 (6.12, 6.13) | 6.18 | Rec3 p.1 | 6.12–6.35 |
| Parallel RLC | §6-7 (368) | PS3 #3 (6.36) | 6.37 | none | 6.36–6.46 |
| General second-order, multiple switchings | §6-8 (374) | PS3 #4 (6.55); #6 (buck converter, custom) | 6.48 (→ OA 6.47), 6.54 | none | 6.47–6.59 |
| Second-order op-amp circuits | §6-8 (374) | PS3 #5 (6.58) | 6.59 | none | 6.58–6.59 |
| Sinusoids (standard cosine form, lead/lag) | §7-1 (401) | PS4 #1 (7.2 → OA 7.1; 7.7 → OA 7.8) | none | sinusoids refresher video + notes; Sinusoids-phasors review ETY | 7.1–7.8 |
| Complex algebra | §7-2 (404); App. D (751) | PS4 #2 (7.10, 7.11, 7.17) | none | Complex numbers 1 & 2 refreshers | 7.9–7.20 |
| Phasors, impedance, admittance, Z combos | §7-3–7-5 (411–424) | PS4 #3 (7.21 → OA 7.22, 7.23, 7.28), #4 (7.31), #5 (7.45) | 7.32 | Rec3 (phasors, Z); Sinusoids-phasors review ETY | 7.21–7.45 |
| Phasor Thévenin/Norton, matching | §7-6 (425) | none | 7.47 | none | 7.46–7.50 |
| Phasor diagrams, phase-shift circuits | §7-7, 7-8 (428–434) | none | none | none | 7.51–7.55 |
| Phasor node/mesh/superposition (incl. different ω) | §7-9 (435) | PS4 #6 (7.58) | 7.68 (book answer wrong) | none | 7.56–7.83 |
| ac op-amp circuits | §7-10, 7-11 (444–446) | PS5 #4 (8.38, unsolved) | none | none | ac op-amp items in 7.56–7.83 |
| Average and rms of periodic waveforms | §8-1 (475) | PS5 #1 (8.16), #5 (triangle ESR loss; unsolved) | none | Rec3 (rms sine, square) | 8.1–8.15 |
| Average and complex power, S = V_rms I_rms\*, conservation | §8-2, 8-3 (478–486) | PS5 #2 (8.20 → OA 8.19), #3 (8.27) (unsolved) | 8.23, 8.29 | Rec3 (S = P + jQ) | 8.17–8.44 |
| Power factor, PF correction | §8-4 (487) | **none** | none | Rec3 (brief) | 8.45–8.50 |
| ac max power transfer (Z_L = Z_Th\*; purely resistive load case) | §8-5 (491) | **none** | **8.52** | Rec3 | 8.51–8.60 |
| (?) Semiconductors / MOSFET basics (10/05 lecture) | §4-11 (234) (only textbook coverage) | none | none | Semiconductors_review_ETY; Lab 3 prelab | 4.59–4.61 |

Write-up standard for every topic: the "problem set tips" rubric (diagram, labeled variables, the law cited, boxed answers with units, 3 sig figs). Only the front side of each answer sheet is graded.
