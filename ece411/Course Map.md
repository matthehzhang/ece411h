# ECE 411H (Fall 2026, Unique 18535): Course Map for Semester Exam 2

Built 2026-11-06 (brief A, materials inventory). Course root: ``; paths below are relative to it unless they are `[[wikilinks]]` into this vault.
Exam 1 assets (PS1–PS5, Recitations 1–3, Ch 1–8 textbook TOC, Ch 5–8 videos, E1 lectures) are described in [[Course Materials Map]] and are only linked here, not re-described.
Reserved exam: Fall 2025 Semester Exam 2 (questions and short answers) was not opened and is not cited anywhere in this file.

**Semester Exam 2: Wed 2026-11-11, 09:00–10:15 CT, ECJ 1.222, in class. 70 min writing + ~5 min Gradescope upload. Closed book, no formula sheet, calculator allowed.**

---

## 0. Headline findings

1. **Laplace transforms are NOT on Semester Exam 2, and no Laplace table will be provided for it.** Ed Yu said so twice at the start of the 11-02 lecture (`Recordings/2026-11-02-laplace-transforms/transcript.txt`, 0:01:44–0:02:50) and again at 0:39:04–0:39:41, where he states that SE2 covers material up to and including the cascaded active filter example (plus the two cascaded-filter examples he posted, which are on disk as one 67-min recorded session). This contradicts the syllabus schedule (Laplace 11/02–11/09 before SE2), `README.md` ("Scope (syllabus): … Laplace transforms"), and the `Transcripts/` titles that call the F26 Laplace and Fourier tables the "official Exam 2 handout". See §2, conflicts C1–C2.
2. **PS8 problems 1–5 are SE2 material; problem 6 (12.2, delta-function integrals) is not** (10-28 lecture, 0:00:31–0:01:08).
3. **No "Exam 2 rules and material covered" announcement is on disk.** Ed Yu promised one on 10-26 (for later that week) and again on 10-28, saying the rules would be basically the same as for the first exam. It was not found in the 11-05 Canvas audit. See §9.
5. **Two PS8 numbers do not match the local textbook PDF.** PS8 "9.42" is OA **9.43** (OA 9.42 is a high-pass design), and PS8 "12.2" is OA **12.1** (OA 12.2 is a different set of integrals). OA Appendix G (PDF 761) prints answers for 9.26 and 9.39, which are PS8 problems 1 and 3. Do not open those entries before PS8 is submitted.
6. **Active filters have no problem set with posted solutions until PS8 solutions unlock (Mon 11-09 18:00).** Before then the only worked active-filter material is the video for 9.37, the 10-28 and 11-02 lectures, the cascaded-filters recorded session and notes, textbook §9-6/9-7 examples, and past exams (F23 SE2 P3, F24 SE2 P4, F24 Final P3, F25 Final P3).
7. **The 10-26 recording directory is mislabelled.** `Recordings/2026-10-26-active-filters/` contains no op-amp content (0 mentions). It covers the passive series-RLC band-pass filter, Q and bandwidth (31 mentions of "quality factor"). Active filters start at 0:46:48 of the 10-28 lecture.
8. **MOSFETs are out of scope.** Ed Yu's own semiconductor review (`_sources_transcribed/Refreshers/Semiconductors_review_ETY.pdf`, p. 4) says the MOSFET section is not needed for ECE 411. No F23/F24 SE2 or F23–F25 final asks about MOSFETs. Lab 3 is the only MOSFET material.

---

## 1. Syllabus and logistics (`Admin/ECE 411H syllabus F26.pdf`, 6 pp, all pages viewed)

**Section.** Unique **18535** (the header of every syllabus page and of the lab-recitation schedule). Lectures MW 9:00–10:30 AM in ECJ 1.222, simulcast on Zoom. Lab/recitation Mon 1:00–3:00 PM, in EER 0.818 (recitation) or EER 1.828 (lab).

### Exam rules
- Syllabus p. 1: two in-class semester exams of 75 minutes each. SE2 is listed for Wed 11/11/2026, in class.
- Syllabus p. 4, "Examinations": the verbatim paragraph is already in [[Course Materials Map]] §1 ("Examinations (quote)"). I re-checked it against the PDF on 2026-11-06, and it is identical apart from the line-break hyphenation of "in-person". That quote stops one sentence early. The omitted sentence says that a student caught using unauthorized materials, copying, writing after time is called, or otherwise breaking exam rules will likely get a zero on that exam at minimum, and may face further discipline.
- SE2 answer template p. 1 (`Exams/F26/ECE 411H Semester Exam 2 template F26.pdf`, created by "ety" on 2026-11-04 16:35 CST, 20 pp): the printed rules are identical to the SE1 and dummy templates.
  - Allowed: the exam questions, the answer sheets and a calculator, and nothing else. No communication with other students.
  - Time: 70 minutes from the start, then about 5 minutes to scan and upload to Gradescope.
  - Numbers are good to 3 significant figures unless stated otherwise. Show all work, and state any assumption explicitly.
  - Only the front side of each sheet is graded, and some answer boxes continue onto the next page.
- The SE1 precedent comes from the Sep 26 Canvas announcement, as summarized in `Exams/F26/Semester Exam 1 details.txt`.
  - Allowed: the question sheet, the answer template, a calculator, writing implements and erasers. No other materials.
  - Logistics: bring a blank printed template, write on it, scan the fronts only and upload to Gradescope. Questions are handed out in class and may be kept. A Gradescope "Exam Upload Practice" assignment existed (Sep 28).
  - The 11-02 lecture (0:00:38) repeats the hard-copy template requirement for SE2.

### Exam grading ("Notes on exam grading", p. 2)
The verbatim paragraph is in [[Course Materials Map]] §1 ("Grading", the "Exam grading (quote)" line), checked identical to the PDF. Its operative content:
- Reasoning counts as much as or more than the final answer.
- Cross out any work you do not want graded.
- Demonstrated mastery earns substantial partial credit.
- A bare correct answer earns very limited credit.
- Regrade requests must be written and made within one week, and the whole exam may then be regraded up or down.

The 10-12 lecture (0:01:36–0:02:50) adds how regrades work in practice: one rubric is applied to everyone, so requests that only argue for more partial credit will not succeed.

### AI policy (p. 3)
The operative paragraph and the "AI circuit tutor" paragraph are verbatim in [[Course Materials Map]] §1 ("Course Policy on AI: operative paragraphs (exact)"), checked identical.
- Allowed: AI to explain concepts, to identify approaches, to give feedback on solutions he worked out himself, and to solve problems that were not assigned.
- Not allowed: AI worked solutions to assigned homework problems.

The TA's 2026-09-20 Discord note warns that AI solutions are often wrong and cost the intuition the problems are meant to build.

### Homework and collaboration (pp. 2–4)
"Policy on Collaboration" and "Homework" are verbatim in [[Course Materials Map]] §1 ("Policy on Collaboration (exact)", "Homework (exact)"), both checked identical. The "Problem Sets" paragraph (p. 4) is not quoted there. It says:
- Problem sets are due online at the beginning of class on the due date.
- Late work is not accepted except possibly for serious, documented illness.
- Solutions are posted on the due date, typically at 6:00 PM Central.

> [!warning] Disagreement: late work
> [[Course Materials Map]] §2 paraphrases this as "No late work is accepted". The syllabus allows a possible illness exception. The TA also offers time extensions if asked before the deadline, with submission before the 6 PM solution release (Discord #problem-sets, 2026-11-05). I believe the syllabus plus the TA message. The vault paraphrase is too strict.

### Office hours
- **Instructor** (syllabus p. 1): MW 10:30–11:55 AM or by appointment, EER 3.802. He is also often at MER 2.206B (Pickle Research Campus). Recorded one-off changes: Wed 10-14 moved to 2:30–4 PM; Mon 10-19 added 3–4:30 PM and cancelled Wed 10-21; Wed 10-28 moved to 1–2:30 PM. SE2-week hours have not been announced. The regular slots are Mon 11-09 and Wed 11-11 after the exam.
- **TA Darsh Shah** (<email removed>). The syllabus defers TA hours to Canvas. The Canvas OH page (per `Admin/RESOURCE_INVENTORY_2026-11-05.md`) and Discord say Thu 10 AM–noon in EER 1.808 (Power Lab), with Zoom at <link removed> He moves them to Tuesday the week of a PS deadline or exam (Oct 6, Oct 13, Oct 20/21).

### Recording policy (p. 1)
- Regular class meetings are simulcast on Zoom and recorded. Labs and recitations are not.
- Recordings are for this class only, protected under FERPA, and may not be shared outside the class.
- Students may not record class (UT HOP 2-9970) without the instructor's permission or a Disability & Access accommodation.
- Labs, recitations and office hours are in person only unless noted.
- The syllabus says a lecture-by-lecture "Lecture Topics" summary lives in Canvas Discussions. The 11-05 audit found that the Zoom recording links are posted there.

### Lab and recitation (p. 4)
- Sessions are in person only, and participation is required.
- There are only six labs. The TA runs recitation or review in the other weeks.
- The TA handles all lab issues, including lab grading.

### Weights (p. 2)

| Component | Weight |
|---|---|
| Homework (problem sets) | 5% |
| Laboratory | 10% |
| Semester Exam 1 | 25% |
| Semester Exam 2 | 25% |
| Final | 35% |


### Exam 2 unit: syllabus schedule vs what was actually taught

| Date | Syllabus row (p. 6) | Reading | What the recording shows | Recording dir (`Recordings/…`), length |
|---|---|---|---|---|
| 10/05 | Semiconductors and solid-state devices | none | Start of semiconductors (band gap and Fermi function appear: "Fermi" ×14, "band gap" ×5 in the transcript), two days before SE1. PS6 announced as not on SE1 but on SE2 and the final (0:02:03) | `2026-10-05-semiconductors-and-solid-state-devices/`, 78 min, tablet |
| 10/07 | Semester Exam 1 | | | |
| 10/12 | Semiconductors; intro to filters | Ch 9 | SE1 stats; detailed semiconductors (Fermi ×59, doping ×11, density of states ×5 in the transcript). Taught on the doc cam because the tablet failed; 9 blurry frames | `2026-10-12-semiconductors-doc-cam/`, 80 min |
| 10/14 | (same row) | Ch 9 | pn junction: band-edge diagram, built-in potential, quasi-Fermi levels, diode I–V. Filters are introduced only at 1:09:41–end. Also announces the complex-numbers handout #2 | `2026-10-14-semiconductors-intro-to-filters/`, 76 min |
| 10/19 | Passive filter circuits and Bode plots | Ch 9 | Transfer functions (§9-1), resonance at ~0:28, RC example at 0:30, Bode plots from 0:55 | `2026-10-19-passive-filters-and-bode-plots/`, 76 min |
| 10/21 | (same row) | Ch 9 | Bode factors (constants, zeros/poles at the origin, simple, quadratic); passive band-pass example at 1:12 | `2026-10-21-passive-filters-and-bode-plots-cont/`, 79 min |
| 10/26 | Active filter circuits | Ch 9 | **Passive**: series-RLC band-pass magnitude and phase, Q, bandwidth. Zero op-amp mentions | `2026-10-26-active-filters/`, 81 min |
| 10/28 | (same row) | Ch 9 | RLC high-pass (output across L), Q and peaking; **active filters from 0:46:48** (first-order active LP and HP) | `2026-10-28-active-filters-cont/`, 79 min |
| 11/02 | Laplace transforms | Ch 12 | 0:03–0:39 is a cascaded third-order active low-pass filter, which is **the end of SE2 scope**. Laplace and integral transforms after that are not on SE2 | `2026-11-02-laplace-transforms/`, 78 min |
| (posted 11/02) | — | — | Recorded session (the notes PDF was created 2023-10-25): cascaded band-pass analysis plus a band-reject design (gain −50, stop band 20–40 kHz, ±40 dB/dec) | `2026-11-02-cascaded-filters-refresher-session/`, 67 min, doc cam |
| 11/04 | Laplace transforms | Ch 12 | **No recording on disk.** No 11-04 Lecture Topics post as of the 11-05 audit. Laplace only, so outside SE2 scope | — |
| 11/09 | Laplace (cont.) | Ch 12 | Not yet held. Outside SE2 scope | — |
| 11/11 | Semester Exam 2 | | | |

Each directory has `lecture.mp4`, Deepgram `transcript.txt` and `transcript.paragraphs.md`, `QUALITY.md`, and per `QUALITY.md` a `frames/pages_with_speech.md`. All are machine output, so re-derive any number before trusting it. The ten E2-unit lecture notes are being written by other agents; this file only lists the recordings.

---

## 2. Logistics conflicts


|---|---|---|---|---|---|---|---|---|
| Date | Wed 2026-11-11 | "11 November 2026" | — | SE2 assignment exists; questions handed out in class | — | Wed 11-11 | 10-26 (0:00:40), 10-28 (0:01:15), 11-02 (0:00:23): Wed Nov 11 | We 11/11/2026 |
| Time | 09:00–10:15 CT | 70 min writing + ~5 min upload | SE1: same split | — | — | 09:00–10:15 | in person, in class | "in class", 75 min; class is 9:00–10:30 |
| Room | in class | not stated | ECJ 1.222, taken from the lecture schedule | — | — | ECJ 1.222 | — | lectures in ECJ 1.222 |
| Materials | closed book, calculator | questions, answer sheets, calculator | question sheet, template, calculator, writing implements, erasers | Laplace handout announced Nov 4 | — | — | 10-28: rules basically the same as SE1; 11-02: no Laplace table at SE2 | calculator, writing implements, erasers, question/answer sheets; anything else announced in advance |
| Coverage | — | — | SE1: up to phasor power calculations, excluding max power transfer | no SE2 coverage announcement found | semiconductors, Bode plots (hints) | — | 11-02: through cascaded active filters; Laplace excluded. 10-28: PS8 Q1–5 in scope | schedule runs to "11/09 Laplace transforms (continued)" before SE2 |

> [!warning] C1: SE2 coverage. Syllabus, README and Transcripts INDEX vs the 11-02 lecture
> - **Syllabus p. 6** puts Laplace (Ch 12) on 11/02–11/09, before SE2. `README.md` turns that into a scope that includes Laplace.
> - **11-02 lecture**: Laplace transforms are not part of the SE2 content (0:02:07). SE2 covers material up to that point, meaning the end of the cascaded-filter example (0:39:20). Laplace will be on the final.
> - **I believe the lecture.** It is the instructor's own recorded statement, it is later than the syllabus, the syllabus marks its schedule as tentative, and it agrees with the 10-28 statement that only PS8 Q1–5 are exam material. F23 and F24 SE2 also had no Laplace content.
> - **Residual risk:** the promised Canvas announcement could still say otherwise. Re-check Canvas Announcements (§9).

> [!warning] C2: Laplace and Fourier tables labelled "official Exam 2 handout"
> - `Transcripts/INDEX.md`, `Transcripts/Refreshers/Laplace_Transforms_table_F26.md` and `…/Fourier_Transforms_table_F26.md` call these tables the official Exam 2 handout and say the Laplace one is the table supplied with Exam 2.
> - Nothing in the sources supports this. The PDFs carry no exam marking. They were created 2026-08-20, long before the Nov 4 handout announcement. The SE2 template allows only questions, answer sheets and a calculator. The 11-02 lecture says SE2 gets no Laplace table.
> - The Fourier table is Ch 13 material, taught 11/30–12/07, after SE2.
> - I believe these are final-exam handouts. Finals F23–F25 list the appended Laplace transform handout among the allowed materials. The transcript labels are wrong.

> [!warning] C3: Duration. Syllabus "75 minutes" vs template "70 minutes + ~5 minutes upload"

> [!warning] C4: PS5 scope
> `Transcripts/Problem Sets/PS5_problems.md` (summary) and `Transcripts/Problem Sets/README.md` describe PS5 (rms, complex power, op-amp ac power, ESR loss) as Exam 2 material. The SE1 announcement covered phasor power calculations, and the 10-05 lecture names PS6 as the first problem set that is not on the first semester exam. **I believe PS5 is Exam 1 unit.** Only maximum power transfer (PS6 Q1–2) moved to SE2.

> [!warning] C5: TA office hours in exam week

> [!warning] C6: Canvas audit says the 10-12 recording "does not exist"
> `Admin/RESOURCE_INVENTORY_2026-11-05.md` reports Zoom error 3,301 for 10-12. Its URL is missing two characters ("…MEMmz**6W**Qe2…" in `Recordings/lectures.tsv` and the download log, versus "…MEMmzQe2…" in the inventory). The recording downloaded fine from the correct URL and is on disk, 80 min. I believe the recording exists and that the inventory error came from the truncated URL.

> [!warning] C7: Cascaded-filters MP4 location
> The inventory and `Course Materials Map` (correction header) place it at `Refreshers/ECE_411H_cascaded_filters_F26.mp4`. That file does not exist there. The same 208,777,088-byte video is at `Recordings/2026-11-02-cascaded-filters-refresher-session/lecture.mp4`. `QUALITY.md` names it "2026-00-00-cascaded-filters", and the pipeline ran it from `Refreshers/Recordings`, which was then moved.

> [!warning] C8: README folder claims
> `README.md` says `Recitations/` holds TA notes 1–5. Only Recitations 1–3 are there. Recitations 4–5 are in `_sources_transcribed/Recitations/`, with transcripts in `Transcripts/Recitations/`. Likewise, the semiconductor review, cascaded-filter notes, integral-transform notes and Laplace/Fourier tables are in `_sources_transcribed/Refreshers/`, not `Refreshers/`.

> [!warning] C9: Recitation 4 date
> The file is named "10-4-26" and the transcript file "2026-10-04", but the page header says "(10/5)" and the lab schedule has the SE1 review recitation on Mon 10/05. The session was Mon 10/05. Discord posted it 10-06.

> [!warning] C10: Lecture directory labels vs content
> Directory names follow the syllabus topic, but the lectures ran about one class behind it. The 10-26 "active-filters" lecture is passive (finding 7), and active filters ran 10-28 into 11-02. Search by content, not by directory name.

Other checks found no conflict:
- Date: Wed 11-11 in every source.
- Room: ECJ 1.222 everywhere it is stated.

**No "Exam 2 rules and material covered" announcement is on disk.** The SE1 equivalent was a Canvas announcement (Sep 26) summarized in `Exams/F26/Semester Exam 1 details.txt`. The SE2 one would be in **Canvas → Announcements** (course 1454964). The 11-05 audit lists only the Nov 4 Laplace-handout announcement.

---

## 3. Assignments

Weights: problem sets share **5%** and labs share **10%**. The per-item split is not stated. Each component is curved (syllabus p. 2).

| Item | Due (CT) | Grading basis | Official solutions on disk | Topics |
|---|---|---|---|---|
| PS1 | We 09/09 09:00 | TA-graded with comments; neatness deductions (−0.01 on PS2, −0.1 on PS3, "larger" later); plot everything asked | `Problem Sets/official/ECE_411H_PS1_solns_F26.pdf` | E1: node analysis, Thévenin, dc max power, C/RC ([[Course Materials Map]] §2) |
| PS2 | Mo 09/14 09:00 | same | `…/ECE_411H_PS2_solns_F26.pdf` | E1 op-amps, RC op-amp |
| PS3 | Mo 09/21 09:00 | same | `…/ECE_411H_PS3_solns_F26.pdf` | E1 RLC; includes 6.58, an RLC op-amp multiple-feedback band-pass |
| PS4 | Mo 09/28 09:00 | same | `…/ECE_411H_PS4_solns_F26.pdf` (image-only) | E1 sinusoids, complex algebra, phasors |
| PS5 | Mo 10/05 09:00 | same | `_sources_transcribed/Problem Sets/ECE_411H_PS5_solns_F26.pdf`; transcript `Transcripts/Problem Sets/PS5_solutions.md` | **E1 unit** (C4): rms/average, complex power, op-amp ac power (8.38), inductor ESR loss |
| PS6 | We 10/21 09:00 | same | `_sources_transcribed/Problem Sets/ECE_411H_PS6_solns_F26.pdf` (7 pp: pp. 1–2 publisher 8.51/8.54; pp. 3–7 handwritten Q3–6); transcript `PS6_solutions.md` | Max power transfer 8.51, 8.54; hole concentration from DOS (gamma integral), intrinsic $n_i$ for Si, simplified ideal-diode equation, dimensional analysis $L=\sqrt{D\tau}$ |
| PS7 | Mo 11/02 09:00 | same | `_sources_transcribed/Problem Sets/ECE_411H_PS7_solns_F26.pdf` (17 pp: 9.2 p1, 9.6 p2, 9.18 pp3–6, 9.20 pp7–11, 9.31 pp12–13, 9.34 pp14–15, Q7 pp16–17 handwritten); transcript `PS7_solutions.md` | Resonance (9.2), RLC transfer function (9.6), Bode straight-line plots incl. quadratic factors (9.18, 9.20), passive filters (9.31 band-pass, 9.34 high-pass), decoupling capacitors with ESR/ESL (Q7) |
| **PS8** | **Mo 11/09 09:00** | same | **None.** Canvas asgmt 7652594 unlocks **Mo 11/09 18:00** | **DO NOT SOLVE** (below) |
| PS9 | Opens Mo 11/09 12:00 PM (Canvas asgmt 7652596). Due date not on disk; the solutions asgmt is locked until **Mo 12/07 18:00**, which implies due Mo 12/07 09:00 (?) | same | none | not on disk (post-SE2; Laplace/Fourier presumably (?)) |
| Lab 1 Op-amp circuits | lab 09/14, report Mo 09/21 23:59 | TA; pre-lab checked for completion only; report = answers to the highlighted items in order (manual p. 4) | n/a | E1 |
| Lab 2 RC & RL, first-order filters | 09/21 → Mo 09/28 23:59 | same | n/a | E1 (previews Bode) |
| Lab 3 MOSFET characteristics & basic amplifiers | 10/19 → Mo 10/26 23:59 | same | n/a | 2N7000 $I_D$–$V_{GS}$, $I_D$–$V_{DS}$, $V_{th}$, common-source gain, loading, headphone amp (manual pp. 31–39). Out of SE2 scope |
| Lab 4 RLC, second-order filters | 10/26 → Mo 11/02 23:59 | same | n/a | Series RLC transient (over/critical/under), series RLC band-pass Bode, parallel RLC low-pass Bode plus audio (manual pp. 40–46). Practice value only |
| **Lab 5 Active filters** | 11/02 → **Mo 11/09 23:59** | same | n/a | **DO NOT SOLVE** (below) |
| Lab 6 Op-amp oscillators | 11/30 → Mo 12/07 23:59 | same | n/a | Phase-shift and Wien-bridge oscillators (manual pp. 54–61). After SE2 |
| Checkpoint survey (Canvas) | **Su 11/08 23:59** | unknown (?) | n/a | Course experience plus AI-use questions (11-02 lecture) |
| Quizzes | none found on disk or in the Canvas audit | — | — | — |
| SE1 | We 10/07 (done) | 74.5/105 | `Transcripts/Exams/SE1_F26_short_answers.md` | E1 |

### Do-not-solve list (graded and due before Wed 11-11 09:00, or assigned homework)

1. **Problem Set 8**, due **Mon 11-09 09:00**. Statements are in `Transcripts/Problem Sets/PS8_problems.md` and the original is `_sources_transcribed/Problem Sets/ECE_411H_PS8_F26.pdf`. Record the statement and type only. No solutions, answers or checks.
   - **9.26.** Series RLC band-pass ($R = 5\ \Omega$, $L = 20$ mH, $C = 0.5\ \mu$F): find $\omega_0, Q, B, \omega_{c1}, \omega_{c2}$, then ask whether $Q$ can be doubled at fixed $\omega_0$ and $R$. *Type: resonance/Q/bandwidth parameters.* (OA 9.26 has an Appendix G answer.)
   - **9.38.** Non-inverting op amp with $R_2$ to ground and $R_1 \parallel C$ in feedback ($99$ k$\Omega$, $1$ k$\Omega$, $0.1\ \mu$F): $\mathbf H$ in standard form, magnitude and phase plots, filter type, maximum gain. *Type: active filter analysis plus Bode.*
   - **9.39.** Unity-gain Sallen-Key-style circuit ($R_1 = R_2 = 100\ \Omega$, $C_1 = 10\ \mu$F, $C_2 = 0.4\ \mu$F): same three parts. *Type: second-order active filter plus Bode.* (OA 9.39 has an Appendix G answer.)
   - **"9.42" = OA 9.43.** Design an active low-pass filter with gain 4, corner 1 kHz and −60 dB/decade. *Type: cascaded active filter design.*
   - **m9.2.** Inverting op amp with $R_1 \parallel C_1$ at the input and $R_2 \parallel C_2$ in feedback ($3.3$ k$\Omega$, $10$ k$\Omega$, $0.01\ \mu$F, $0.1\ \mu$F): $\mathbf H(\omega)$ in standard form, $\mathbf H(f)$, Bode plots in $f$, low- and high-frequency asymptotes, two corner frequencies. *Type: active filter Bode analysis.*
   - **"12.2" (a–c) = OA 12.1.** Three integrals of polynomial or exponential factors against sums of shifted $\delta$'s. *Type: sifting property.* **Not on SE2** (10-28 lecture).
2. **Lab 5 report (Active Filters)**, due **Mon 11-09 23:59**. Tasks are in `Labs/Lab Documents/ECE_411H_Lab_Manual_F26.pdf` pp. 47–53. The pre-lab (pp. 47–49) was already submitted (`Labs/Lab5_Prelab/`).
   - Task 1: first-order active inverting low-pass filter ($R_1 = R_2 = 10$ k$\Omega$, $C = 10$ nF). Measure the Bode plot, then read roll-off, cutoff and gain into Table 5.0. Repeat with $R_2 = 20$ k$\Omega$, giving predictions first. Name one advantage and one disadvantage against passive filters.
   - Task 2: Sallen-Key low-pass ($10$ k$\Omega$, $10$ nF). Table 5.1, and compare second-order with first-order roll-off.
   - Task 3: Sallen-Key high-pass ($10$ k$\Omega$, $10$ nF). Table 5.2.
   - Task 4: crossover network. Find the new cutoff frequencies for LP ($10$ k$\Omega$, $100$ nF) and HP ($1$ k$\Omega$, $100$ nF), wire up audio, capture input-vs-output spectra, and compare Sallen-Key with the Lab 4 RLC low-pass.
   - *Type: measurement report with hand predictions.*
   - `Labs/Lab5/captures/` is **empty**, and only sweep and analysis scripts exist in `Labs/Lab5/scripts/`. No Lab 5 data is on disk.
4. **PS9**, which opens Mon 11-09 12:00. It is assigned homework, and the syllabus forbids AI worked solutions to assigned homework regardless of date. Its statements are not on disk.
5. Indirect leaks of PS8 or Lab 5 answers, to be held until after the deadline shown:

| Hold until | Material | Why |
|---|---|---|
| Mon 11-09 23:59 | F24 SE2 P4 (symbolic $\mathbf H$, Butterworth $C_1/C_2$) | Same circuit as PS8 9.39 and Lab 5 Tasks 2 and 4 |
| Mon 11-09 23:59 | F25 Final P3 (b, c) | Same circuit as PS8 9.39 and Lab 5 Tasks 2 and 4 |
| Mon 11-09 23:59 | `Transcripts/Exams/SE2_F24_short_answers.md` P4 | Holds the F24 SE2 P4 answers |
| Mon 11-09 23:59 | Video 6.59 (two-pole Sallen-Key-type op-amp circuit, step response; E1 map description, not re-checked (?)) | Probably the same topology (?) |
| Mon 11-09 09:00 | OA Appendix G (PDF 761) entries for 9.26 and 9.39 | Answers to PS8 Q1 and Q3 |
| Mon 11-09 09:00 | Textbook Example 9-10 ("Third-Order Lowpass Filter", PDF 553) and the 11-02 cascaded third-order low-pass example | Fine for teaching the method, but not applied to PS8's gain-4 / 1 kHz numbers |

> [!note] Added context
> Item 5 is my inference from comparing circuit topologies. PS8 Fig. P9.39 and F24 Circuit SE2-4 both have $R_1$ then $R_2$ in series into the + input, $C_1$ from the $R_1$–$R_2$ node to the output, $C_2$ from the + input to ground, and the − input tied to the output. That leaves only **Tue 11-10** for Sallen-Key practice on past exams.

---


| File(s) | Why untrusted |
|---|---|
| `Transcripts/Problem Sets/PS6_fixes_submitted.md` and `_sources_transcribed/Problem Sets/ps6_fixes/*` | AI-written PS6 corrections |
| `Exams/F26/Generated Mock 1 F26.pdf` (3 pp, pdfTeX, created 2026-10-06 19:37) | Tutor-generated E1 mock, not instructor material. Header "Generated Mock Exam 1" |
| `.tutor/` | Exists. Not opened |
| `Labs/Lab3_Prelab/`, `Labs/lab3/`, `Labs/Lab4_Prelab/`, `Labs/Lab4/captures/`, `Labs/Lab5_Prelab/`, `Labs/Lab5/scripts/` | Authorship not stated. Scripted LTspice and capture pipelines suggest agent assistance (?) |
| `ece411/Lessons/*`, `Tutor Log.md`, `Memorize.md`, `Handoff - Nspire rlc program.md`, `TUTOR_PROMPT_MT1.md` | AI tutor artifacts from E1. `Tutor Log.md` is a log of real E1 sessions: usable as a weak signal, not as proof |
| [[Past Exams F23-F24]] §3 (histogram table) and §6 (scope bullet) | **Contain Fall 2025 Exam 2 statistics and a problem description.** That is reserved-exam leakage. Skip those lines if F25 SE2 is being held out as a mock |
| `Transcripts/*` (Claude vision transcriptions) and `Recordings/*/transcript.txt` (Deepgram) | Machine output. Errors found in this pass: C1/C2 labels (Laplace/Fourier "Exam 2 handout") and C4 (PS5 "Exam-2 material"). Re-derive numbers from the originals |
| `Admin/RESOURCE_INVENTORY_2026-11-05.md` | Agent-written. Stale MP4 path (C7) and truncated Zoom URL (C6) |
| `_sources_transcribed/Recitations/Recitation4(10-4-26).pdf` p. 4 | TA arithmetic slip (E1 material). It computes $\dot v_o(0)=5/(10\text{k}\cdot10^{-5})=50$, but the stated $C = 1\ \mu$F gives $5/(10^4\cdot10^{-6}) = 500$ V/s (verified), so $C_2$ should be $5\times10^{-5}$, not $5\times10^{-6}$. The damping $\alpha = 50$ on the same page does use $C = 1\ \mu$F |

---

## 5. Textbook: `Textbook/CAD_3rd_ed_OA.pdf` (779 pp; Ulaby, Maharbiz & Furse, *Circuit Analysis and Design* 3e, Michigan OA)

**Offset: PDF page = printed page + 15.** Checked on two rendered pages: PDF 516 shows printed "501" (9-1 The Transfer Function), and PDF 646 shows printed "631" (12-1 Unit Impulse Function). The text layer agrees on PDF 527 = 512, 537 = 522, 545 = 530, 553 = 538, 571 = 556, 654 = 639, 656 = 641, 670 = 655, 680 = 665, 758 = 743 and 761 = 746. This matches the E1 map's offset ([[Course Materials Map]] §6). Ch 8 §8-5 Maximum Power Transfer is printed 476 = **PDF 491**.

### Ch 9 Frequency Response of Circuits and Filters (printed 500 → PDF 515)

| Section | Printed | PDF |
|---|---|---|
| Chapter opener, contents, objectives | 500 | 515 |
| Overview / 9-1 The Transfer Function (Ex 9-1 Resonant Frequency, PDF 521) | 501 | 516 |
| 9-2 Scaling (Ex 9-2 Third-Order LP Filter, PDF 523) | 507 | 522 |
| TB22 Noise-Cancellation Headphones | 509 | 524 |
| 9-3 Bode Plots (9-3.1 dB scale, PDF 527; 9-3.2 Poles and zeros, PDF 530; Ex 9-4/9-5 Bode Plots I/II, PDF 533/535; Ex 9-6 Bandreject, PDF 536) | 512 | 527 |
| 9-4 Passive Filters (9-4.1 Bandpass Filter: $\omega_0$, $Q$, $B$, PDF 538; Ex 9-7 Filter Design, 541; Ex 9-8 Two-Stage Bandpass, 542) | 522 | 537 |
| 9-5 Filter Order (Ex 9-9, PDF 546) | 530 | 545 |
| TB23 Spectral and Spatial Filtering | 533 | 548 |
| 9-6 Active Filters (9-6.1 Single-pole lowpass, PDF 552) | 536 | 551 |
| 9-7 Cascaded Active Filters (Ex 9-10 Third-Order Lowpass, PDF 553; Ex 9-11 Bandpass, 556; Ex 9-12 Bandreject, 557) | 538 | 553 |
| TB24 Electrical Engineering and the Audiophile | 544 | 559 |
| 9-8 Application Note: Modulation and the Superheterodyne Receiver | 547 | 562 |
| 9-9 Spectral Response with Multisim | 550 | 565 |
| Summary | 555 | 570 |
| Problems 9.1–9.61 | 556–565 | 571–580 |

Problem groups (from the section headers in the text layer; boundaries ±1):

| Problems | Section(s) |
|---|---|
| 9.1–9.8 | §9-1 |
| 9.9–9.12 | §9-2 |
| 9.13–9.25 | §9-3 |
| 9.26–9.36 | §9-4/9-5 |
| 9.37–9.48 | §9-6/9-7 |
| 9.49–9.50 | §9-8 |
| 9.51–9.58 | §9-9 (Multisim) |
| 9.59–9.61 | TB questions |

### Ch 12 Circuit Analysis by Laplace Transform (printed 630 → PDF 645). Outside SE2 scope (C1)

| Section | Printed | PDF |
|---|---|---|
| Chapter opener | 630 | 645 |
| Overview / 12-1 Unit Impulse Function | 631 | 646 |
| 12-2 The Laplace Transform Technique | 633 | 648 |
| TB28 3-D TV | 637 | 652 |
| 12-3 Properties of the Laplace Transform (Table 12-1, PDF 657; Table 12-2, PDF 658) | 639 | 654 |
| 12-4 Circuit Analysis Procedure | 641 | 656 |
| 12-5 Partial Fraction Expansion | 644 | 659 |
| TB29 Mapping the Entire World in 3-D | 648 | 663 |
| 12-6 s-Domain Circuit Element Models | 652 | 667 |
| 12-7 s-Domain Circuit Analysis | 655 | 670 |
| 12-8 Multisim Analysis of Circuits Driven by Nontrivial Inputs | 662 | 677 |
| Summary | 665 | 680 |
| Problems 12.1–12.50 | 665–673 | 680–688 |

12.1–12.2 sit under "Sections 12-1 and 12-2: Impulse Response and Complex Algebra". The later group boundaries are jumbled in the text layer (?).

### End-of-chapter answers
The printed TOC calls the answers "Appendix F, Answers to Selected Problems, printed 743". The body calls it Appendix G and it starts at PDF 758, the same naming disagreement the E1 map already noted.
- **Ch 9 answers are on PDF 761** for 9.2, 9.3, 9.5, 9.8, 9.10, 9.13, 9.14, 9.16, 9.21, 9.23, **9.26**, 9.29, 9.32, 9.35, 9.37, **9.39**, 9.41, 9.46, 9.50. The bold entries are PS8 problems.
- **Ch 12 answers are on PDF 762** for 12.4, 12.5, 12.7, 12.9, 12.10, 12.11, 12.12, 12.15, 12.18, 12.22, 12.25, 12.28, 12.31, 12.34, 12.37, 12.44.
- In-text "Exercise" items print their answers inline.

> [!warning] Numbering: OA PDF vs course (NTS print) numbering for the E2 unit
> I matched each problem by its statement and values in the text layer.
> - **Match:** PS7 9.2, 9.6, 9.18, 9.20, 9.31, 9.34; PS8 9.26, 9.38, 9.39; videos 9.4, 9.19, 9.33, 9.37, 12.5, 12.10, 12.14, 12.15, 12.37 (12.37 uses the Fig. P12.36 circuit).
> - **Mismatch:** PS8 "9.42" = **OA 9.43**, and PS8 "12.2" = **OA 12.1**.
> - A tutor citing these must give the OA number. This extends the E1 list in [[Course Materials Map]] §0.
> - Coverage note: I read the TOC and the two chapter-opener pages as instructed, and in addition read the problem pages (PDF 571–580, 680–688) and Appendix G (PDF 760–762) as **text only**, for this numbering check and the answer-location list. I did not read the answers themselves.

---

## 6. Other assets

### Recitations (TA Darsh Shah, handwritten; recitation weeks only)

| # | Date | File | Covers | Transcribed |
|---|---|---|---|---|
| 1 | Mon 08/24 | `Recitations/Recitation1(8-24-26).pdf` | KCL/KVL, node/mesh, Thévenin/Norton ([[Course Materials Map]] §3) | no |
| 2 | Mon 08/31 | `Recitations/Recitation2(8-31-26).pdf` | Finite-gain op amp, instrumentation amp | no |
| 3 | Mon 09/28 | `Recitations/Recitation3(9-28-26).pdf` | Series RLC, rms, phasors, $\mathbf S=\mathbf V\mathbf I^*$, power factor, **max power transfer $\mathbf Z_L=\mathbf Z_s^*$** (the only E2 topic here) | no |
| 4 | Mon 10/05 (C9) | `_sources_transcribed/Recitations/Recitation4(10-4-26).pdf` (4 pp viewed) → `Transcripts/Recitations/Recitation4_2026-10-04_exam1_review.md` | SE1 review: RL first-order by integrating factor, phasor nodal, series/parallel RLC step (with the slip noted in §4) | yes |
| 5 | Mon 10/12 | `_sources_transcribed/Recitations/Recitation5(10-12-26).pdf` (4 pp viewed) → `Transcripts/Recitations/Recitation5_2026-10-12_semiconductors.md` | Si bonding, $E_g$ classes, $k_BT \approx 0.026$ eV, Fermi–Dirac and the Boltzmann limit, DOS $g_c, g_v$, effective masses, $n$ and $p$ integrals (substitution, gamma integral), doping shifts $E_F$. The TA said it contains material needed for PS6 | yes |
| — | Mon 11/09 | not yet held | **Semester Exam 2 review**, EER 0.818, 13:00–15:00 | — |

10/19, 10/26 and 11/02 were lab weeks (Labs 3–5).

### Refreshers and handouts

| File | What | E2 relevance |
|---|---|---|
| `Refreshers/ECE 411H complex numbers-algebra 1 F26.pdf` (3 pp) | Rectangular/polar, conjugate, multiply/divide | Background |
| `Refreshers/ECE 411H complex numbers-algebra 2 F26.pdf` (3 pp, viewed) | Rationalizing transfer functions into "standard" form; limits as $\omega\to0,\infty$; **phase of quadratic poles/zeros with the ±180° quadrant correction above $\omega_p$**. Posted 10-14 per that lecture | **High** (Bode phase) |
| `Refreshers/ECE_411H_sinusoids+complex-num_refresher_F26.mp4` (43.5 min) + `_notes_F26.pdf` | Sinusoids, complex numbers | E1 |
| `Refreshers/Sinusoids-phasors_review_ETY.pdf` (8 pp) | 302 review; ends with dB and log-log plotting | Low (dB intro) |
| `_sources_transcribed/Refreshers/Semiconductors_review_ETY.pdf` (6 pp, viewed) → `Transcripts/Refreshers/Semiconductors_review_ETY.md` | Conductivity, mobility, $J=\sigma E$, Si lattice, electrons/holes, $n_i \approx 10^{10}$ cm$^{-3}$ at 300 K, donors/acceptors, n/p type; then a MOSFET section the note itself says is not needed for ECE 411; Streetman refs | **High** (semiconductors), except the MOSFET part |
| `Refreshers/ECE_411H_integral-transforms_F26.mp4` (63.8 min) + `_sources_transcribed/Refreshers/ECE_411H_integral-transforms_notes_F26.pdf` (5 pp, viewed; PDF created 2023-10-30) → `Transcripts/Refreshers/integral_transforms_notes_F26.md`, Deepgram in `Transcripts/Refreshers/deepgram/` | Fourier series → Fourier transform → Laplace motivation | Outside SE2 scope |
| `Recordings/2026-11-02-cascaded-filters-refresher-session/lecture.mp4` (67.1 min) + `_sources_transcribed/Refreshers/ECE_411H_cascaded_filters_notes_F26.pdf` (5 pp, viewed; PDF created 2023-10-25) → `Transcripts/Refreshers/cascaded_filters_notes_F26.md` | (1) Analysis of a cascaded band-pass: inverting LP stage ($1$ k$\Omega$ in, $10$ k$\Omega\parallel 9$ nF) followed by inverting HP stage ($12$ k$\Omega$ + $9$ nF in, $96$ k$\Omega$ feedback). (2) **Design** of a band-reject filter: LP and HP second-order branches summed by an inverting summer with gain −50, $R = 1$ k$\Omega$, solving for $C_{LP}$ and $C_{HP}$ from the −3 dB edges | **High** (explicitly in SE2 scope, 11-02 lecture 0:37–0:39) |
| `_sources_transcribed/Refreshers/ECE_411H_Laplace_Transforms_F26.pdf` (2 pp, viewed) → `Transcripts/Refreshers/Laplace_Transforms_table_F26.md` | Ulaby Tables 12-2, 12-1, 12-3 with the F26 header. Same content as the handouts appended to the F23–F25 finals | Final exam, not SE2 (C2) |
| `_sources_transcribed/Refreshers/ECE_411H_Fourier_Transforms_F26.pdf` (2 pp, viewed) → `Transcripts/Refreshers/Fourier_Transforms_table_F26.md` | Tables 13-4, 13-5, 13-3 | Final only |
| `…/ECE_411H_Laplace_Transforms_F25.pdf`, `…/ECE_411H_Fourier_Transforms_F25.pdf` | F25 copies; MANIFEST says identical content | none |

### Problem-solving videos (Ed Yu, recorded 2023; `Problem Solving Videos/`)

| Video | Length | Problem (OA match) | Transcript | SE2 relevance |
|---|---|---|---|---|
| Ulaby 8.52 | 30.2 min | ac max power transfer: Thévenin by Cramer's rule, $\mathbf Z_L=\mathbf Z_{Th}^*$, $P=\lvert\mathbf V_{Th}\rvert^2/(8R_L)$ (OA 8.52, asterisked) | captions + 4-pp PDF (viewed); not in `Transcripts/` | **Only max-power video** |
| NR_4-83_power_transfer_2 | 25 min | dc max power (Nilsson & Riedel) | none (no captions) | Low |
| Ulaby 9.4 | 11.0 min | Resonant frequency, $R \parallel (L + C)$, $\operatorname{Im}\mathbf Z_i=0$ | `Transcripts/Problem Solving Videos/Ulaby_9.4.md` + `deepgram/` | Resonance |
| Ulaby 9.19 | 92.6 min | Four Bode problems: simple, repeated, quadratic, origin factors; phase-wrapping rule | `Ulaby_9.19.md` + deepgram | **Bode core** |
| Ulaby 9.33 | 17.6 min | Series-L, shunt-C, shunt-R low-pass; quadratic pole, resonant peak, −40 dB/dec | `Ulaby_9.33.md` + deepgram | Passive second-order |
| Ulaby 9.37 | 30.5 min | Non-inverting op-amp high-pass (simple zero and pole), max gain | `Ulaby_9.37.md` + deepgram | **Only active-filter video** |
| Ulaby 6.59 | 50 min | Two-pole Sallen-Key-type op-amp circuit, step response (E1 video; description from the E1 map, not re-checked (?)) | captions + PDF | Topology familiarity; hold until after 11-09 (§3) |
| Ulaby 12.5, 12.10, 12.14, 12.15, 12.37 | 67.1, 64.7, 32.9, 54.4, 40.6 min | Laplace forward/inverse, s-domain RLC, initial-condition sources (12.10 and 12.15 flag textbook-answer errors) | `Ulaby_12.*.md` + deepgram | Outside SE2 (final) |
| Ulaby 13.16, 13.20, 13.31, 13.44, 13.49 | — | Fourier series/transform | `Ulaby_13.*.md` + deepgram | Final only |
| Ch 5–8 and Sec 4-9 videos, NR 4.64/4.77 | — | E1 ([[Course Materials Map]] §4) | captions + PDFs | E1 |

### Labs 3–5
These are out of exam scope except as practice. Details are in §3 (rows Lab 3–5). The Lab 4 Bode measurements of series-RLC band-pass and parallel-RLC low-pass filters are the closest lab analogue to SE2 problems. Lab 5 is do-not-solve until Mon 11-09 23:59.

### Discord exam hints (`Admin/Discord_ECE411H_F26_scrape_2026-11-06.md`; TA Darsh Shah; timestamps UTC as scraped)
- **2026-10-12 16:40Z** (#general): semiconductors will appear on PS6 and on the next exam.
- **2026-10-20 03:41Z** (#general): know semiconductor physics well; the second exam often has semiconductor-physics questions.
- **2026-11-05 15:09Z** (#problem-sets, PS7 notes): be able to do Bode plots effortlessly, because the second exam often has many Bode-plot questions. Many students reached the opposite conclusion on PS7 Q7 because their Bode plots were backwards. Decoupling-capacitor choice is a common interview question. Read the released solutions. Time extensions are available if requested before the deadline, with submission before the 6 PM solution release.
- **2026-10-22 14:04Z** (#problem-sets, PS6 notes): Recitation 5 worked a problem very similar to PS6 Q3, including the gamma-function integral.
- **2026-09-20 / 09-22 / 09-15** (#problem-sets): messy work loses points, the deduction grows over the term, plot everything asked, and AI solutions are unreliable.
- #exam-2-preparation is empty.

---

## 7. Topic → best resources (Exam 2 unit)

Key: **L** = lecture recording dir (`Recordings/…`) with timestamps; **T** = textbook § and PDF pages; **PS** = problem set items with official solutions (PS8 = do-not-solve, no solutions until 11-09 18:00); **V** = videos and refreshers; **X** = past exams. "SE2" means F23/F24 Semester Exam 2 (`Transcripts/Exams/SE2_F2x_questions.md` and `…_short_answers.md`). "FE" means Finals F23–F25 (`Transcripts/Exams/Final_F2x_*.md`). F25 SE2 is never used.

| Topic | L | T | PS (official solutions) | V / refreshers / recitation | X |
|---|---|---|---|---|---|
| **Semiconductors & solid-state devices** (bands, Fermi–Dirac, DOS, n/p doping and $E_F$, $n_i$, pn junction, diode exponential I–V; MOSFET not required) | 10-05 (whole), 10-12 (whole, doc cam), 10-14 (0:00–1:09) | none (syllabus reading "none"). §4-11 MOSFET (PDF 234) is optional only | **PS6 Q3–6** (solns pp. 3–7) | Rec 5; Semiconductors_review_ETY; Discord hints 10-12, 10-20 | SE2 F23 P1(b) n-type B vs As, P1(c) Fermi function → exponential diode I–V; SE2 F24 P1(b) acceptors move $E_F$ toward $E_v$, P1(c) same diode question; FE F24 P1(e) Si vs Ge holes; FE F25 P1(e) forward-bias explanation |
| **Transfer functions & filter types** (LP/HP/BP/BR by output placement; standard factored form; $\omega\to0,\infty$ limits) | 10-14 (1:09–end), 10-19 (0:00–0:55), 10-21, 10-26, 10-28 (0:00–0:46) | §9-1 PDF 516; §9-4 PDF 537; §9-5 PDF 545 | PS7 Q2 (9.6), Q5 (9.31), Q6 (9.34). PS8 Q1–3, Q5 do-not-solve | V 9.33, 9.37; complex-numbers handout 2 | SE2 F23 P1(d) (BP across R), P2(a), P4(a, c); SE2 F24 P1(a) (LP across C), P1(d) ($\lvert H\rvert>1$), P3(a); FE F23 P2(a, b); FE F24 P1(a, b) (terminal pairs), P2(a, b); FE F25 P1(a), P2(a–d) |
| **Resonance, Q, bandwidth** | 10-19 (~0:28), 10-26 (whole: Q ×31, bandwidth), 10-28 (Q and peaking, 0:00–0:46) | §9-1 (Ex 9-1, PDF 521); §9-4.1 Bandpass PDF 538 | PS7 Q1 (9.2). PS8 Q1 (9.26) do-not-solve | V 9.4, 9.33 (peak at $\omega_c$) | SE2 F23 P1(a) (Q vs R), P4(d) (bandwidth vs R); FE F24 P1(c) (resonant frequency), P3(c, d) (bandwidth, linear vs exact); FE F25 P1(b) (peak of $\lvert H\rvert$) |
| **Bode plots** (straight-line magnitude and phase; simple, repeated, quadratic, origin factors; phase-range conventions) | 10-19 (0:55–end), 10-21 (whole), 10-26, 10-28 | §9-3 PDF 527 (dB 527, poles/zeros 530, Ex 9-4/9-5 PDF 533/535) | **PS7 Q3 (9.18), Q4 (9.20)**, plus plots in Q5–7 (solns pp. 3–17). PS8 Q2, Q3, Q5 do-not-solve | **V 9.19** (92.6 min); 9.33; 9.37; complex-numbers handout 2 (quadratic phase); Discord 11-05 | SE2 F23 P3(b), P4(b); SE2 F24 P3(c), P4(c); FE F24 P2(a, b), P3(b) (phase $0^\circ\le\phi<360^\circ$); FE F25 P3(c); FE F23 P1(c) (phase quadrant of $a+jb$) |
| **Passive filter design** | 10-19, 10-21 (BP example at 1:12), 10-26, 10-28 | §9-4 PDF 537 (Ex 9-7 Filter Design, 541; Ex 9-8, 542); §9-5 PDF 545 | PS7 Q5, Q6, **Q7 decoupling caps** (solns pp. 12–17) | Lab 4 manual (pp. 40–46); Lab 2 | SE2 F23 P2 (choose Z for HP $\omega_c = 1000$; series-LC notch at 2000 rad/s); SE2 F24 P3 (RC LP with source resistance, cutoffs); FE F23 P2(c) (band-reject corners); FE F24 P2(d) (C, L for $\omega_c = 10^4$); FE F25 P2 (third-order ladder, loaded vs unloaded) |
| **Active (op-amp) filters incl. Sallen-Key and cascades** | 10-28 (0:46:48–end); 11-02 (0:03–0:39, cascaded third-order LP; end of SE2 scope) | §9-6 PDF 551; §9-7 PDF 553 (Ex 9-10 third-order LP, 9-11 BP, 9-12 BR) | **None posted until 11-09 18:00.** PS8 Q2–5 do-not-solve. Tangential: PS3 #5 (6.58), PS5 #4 (8.38) | V 9.37; cascaded-filters session + notes; video 6.59 (hold, §3); Lab 5 (do-not-solve) | SE2 F23 P3 (inverting, $R_s$–$C_s$ in, $R_f\parallel L_f$ feedback); **SE2 F24 P4 (Sallen-Key LP + Butterworth; hold until after 11-09)**; FE F23 P1(d) (fourth-order cascade slope); FE F24 P3 (inverting active band-pass, bandwidth); **FE F25 P3 (Sallen-Key LP + $Z_{in}$; hold)** |
| **Max power transfer (conjugate matching)** | 09-30 (E1 vault note [[2026-09-30 - Power Factor, Max Power Transfer & Device Models]]) | §8-5 PDF 491; problems 8.51–8.60 | **PS6 Q1 (8.51), Q2 (8.54)** (solns pp. 1–2) | **V 8.52**; Rec 3; NR_4-83 (dc) | **SE2 F24 P2** (lowest class average that year, 15.7/25 = 62.8%); FE F25 P1(d) |
| **Laplace basics (δ function, transform table): NOT on SE2 (C1)** | 11-02 (0:39–end); 11-04 missing; 11-09 pending | §12-1 PDF 646; §12-2 648; §12-3 654; Tables 12-1/12-2 PDF 657–658 | PS8 Q6 ("12.2" = OA 12.1) do-not-solve | V 12.5, 12.10, 12.14, 12.15, 12.37; integral-transforms refresher; Laplace table F26 | none on SE2 F23/F24. FE only: F23 P1(b), P4; F24 P1(d), P4; F25 P4 |

Past-exam class statistics (read from the viewed histograms; per-problem percentages computed):

| Exam | N | Mean | Median | SD | P1 / P2 / P3 / P4 (% of 25) |
|---|---|---|---|---|---|
| SE2 F23 (08 Nov 2023) | 66 | 77.2 | 80 | 15.1 | 81.2 / 78.0 / 72.8 / 75.6 |
| SE2 F24 (13 Nov 2024) | 36 | 75.1 | 78.25 | 13.8 | 72.8 / 62.8 / 93.2 / 71.2 |
| Final F23 | 67 | 71.4 | 73 | 11.7 | 83.6 / 69.6 / 64.8 / 66.4 |
| Final F24 | 32 | 75.0 | 74.6 | 9.1 | 92.4 / 66.8 / 60.4 / 80.0 |
| Final F25 | 17 | 77.1 | 75 | 10.1 | 68.4 / 88.0 / 84.4 / 67.2 |

The F23 SE2 per-problem averages sum to 76.9, not the printed mean of 77.2 (rounding, or bonus (?)). F24 sums to 75.0 against a printed 75.1.

---

## 8. Exam artifact types (what SE2 shows and demands)

Sources: `Transcripts/Exams/SE2_F23_questions.md` and `SE2_F24_questions.md`, checked against the rendered PDFs. Both papers have 4 problems × 25 points.

| Artifact | What the paper shows | What the answer must contain | Where (F23 / F24 SE2) |
|---|---|---|---|
| **Short conceptual answers** | P1 has four parts (6/6/6/7 pts), each answerable in a few sentences or a little math; sketches allowed | Physical reasoning in sentences. The diode-exponential-I–V-from-the-Fermi-function question appeared **both years** | F23 P1(a–d); F24 P1(a–d) |
| **Circuit schematics with labelled components** | Named circuits (Circuit SE2-2/3/4) with component symbols and values (F23 states all values are exact), source polarity, and output terminals marked +/−. F24 P2 brackets the source and load portions | Redraw and label nodes; use impedances | every circuit problem |
| **Algebraic transfer function in factored standard form** | F23 P3(a) wants a form that makes the factors corresponding to zeros and poles easy to identify. F24 P4(a) lists the allowed factor types: constant, zero@origin, pole@origin, simple zero/pole, quadratic zero/pole | $\mathbf H(\omega)=K\,\dfrac{\prod(1+j\omega/\omega_z)\cdots}{\prod(1+j\omega/\omega_p)\cdots}$, with quadratic factors as $1+j2\xi\omega/\omega_c+(j\omega/\omega_c)^2$ | F23 P3(a), P4(a); F24 P4(a) |
| **Bode magnitude and phase plots drawn by hand** | straight-line approximations as done in class; you must "label the key values on the vertical and horizontal axes of each plot" and every nonzero slope (F23 P3(b) asks for slopes on BOTH plots). F24 fixes the phase range to $-180^\circ\le\phi\le180^\circ$. FE F24 P3(b) uses $0^\circ\le\phi<360^\circ$ | dB axis with the plateau value and corner frequencies on a log $\omega$ axis; slopes in ±20N dB/dec; phase breakpoints at $\omega_{p,z}/10$ and $10\,\omega_{p,z}$ with ±45°/dec per simple factor; phase inside the stated range | F23 P3(b), P4(b); F24 P3(c), P4(c) |
| **Short written explanation of behaviour** | explain the filter behaviour in terms of how each component impedance varies with frequency; say whether a limiting result makes sense | $\omega\to0$ and $\omega\to\infty$ limits (C open/short, L short/open), physical sanity check | F23 P3(c), P4(c, d); F24 P3(a), P4(b) |
| **Design / choose components** | Choose the element type and value for a given $\omega_c$; choose two series elements for a notch, then values and uniqueness; choose $C$ and $R'$ for maximum power; choose $C_1/C_2$ for a Butterworth response | Conditions written symbolically, then solved; a uniqueness argument | F23 P2(a–c); F24 P2(b), P4(d) |
| **Numeric cutoff** | $\omega_c$ defined where $\lvert H\rvert=1/\sqrt2$ for two source resistances | Exact cutoff, not the asymptote | F24 P3(b) |

The SE2 F26 answer template has **17 answer boxes**: P1 (a–d), P2 (a–c), P3 (a–e), P4 (a–e). Boxes for 3(d), 3(e) and 4(e) continue onto the next page, and pp. 19–20 are for additional work. F23 had 14 parts and F24 had 13, so F26 Problems 3 and 4 will each have five parts (?). On SE1 one 5-point part of P4, probably 4(e), was a bonus (SE1 was scored out of 105) (?).

> [!note] Added context
> The exam is graded by rubric from the photographed fronts of the answer sheets. The problem-set write-up standard ([[Course Materials Map]] §2, and `Transcripts/Problem Sets/problem_set_tips_F26.md`) applies directly. Its five points are a labelled diagram, the law used named, boxed answers with units, no bare numbers, and the intended answer clearly marked.

---

## 9. Gaps and where they probably live

| Gap | Probable location | Notes |
|---|---|---|
| **SE2 rules and material-covered announcement** | Canvas → Announcements (course 1454964) | Promised on 10-26 and 10-28. Not in the 11-05 audit. Decides C1 for certain. Also check whether a Gradescope "Exam Upload Practice" was reopened |
| **11-04 lecture recording** | Canvas → Discussions → "Lecture Topics" (discussion 5749779), Zoom link | No post existed as of the 11-05 audit. Laplace only, so low priority for SE2 |
| **11-09 lecture** | Same place, after Mon 11-09 | Not yet held. Laplace only |
| **Recitation 11-09 SE2 review notes** | Discord #general, posted after the session (Rec 4 appeared the next day) | The only TA-made SE2 review artifact to expect |
| **PS8 official solutions** | Canvas assignment 7652594, unlocks **Mon 11-09 18:00** | The first worked active-filter problem-set solutions |
| **Lab 5 report requirements beyond p. 49** | The task list is on disk (manual pp. 49–53). The Canvas Lab 5 assignment page or rubric is not | Report format is the general rule on manual p. 4. No Lab 5 measurement data on disk (`Labs/Lab5/captures/` empty) |
| TA office hours, exam week | Discord #general or Canvas | Probably Tue 11-10 (C5, (?)) |
| Instructor office hours, exam week | Canvas announcement or 11-09 lecture | Regular slots fall on Mon 11-09 and after the exam |
| Graded PS6 and PS7 feedback | Canvas / Gradescope | Not on disk. AI-written submissions, so of little diagnostic value anyway |
| Full worked solutions to SE2 F23/F24 | none exist | Only short answers. Worked steps must come from the tutor and be checked against the short answers |
| Nov 4 Laplace handout | Canvas announcement / Files | For the final. The local F26 table (created 2026-08-20) is probably the same (?) |
| `frames/pages_with_speech.md` for each E2 lecture | `Recordings/<dir>/frames/` | Present per `QUALITY.md` but not part of this inventory. The lecture-note agents use them |
