# 2026-10-05 semiconductors: page descriptions

Inputs, all read from the base checkout `~/uni/ece411/Recordings/2026-10-05-semiconductors-and-solid-state-devices/`:
- `QUALITY.md`
- `pages_with_speech.md`
- every page-final JPEG it links, plus the earlier states listed under each page
- neighbouring frames from `index.txt` where a page was cut off
- `contact_sheet.jpg`
- `transcript.paragraphs.md` and `transcript.txt`

Source: OneNote on a tablet, shared over Zoom. Typed announcements, then black handwriting, with red ink only on p06. There is no doc-cam. The lecture has no circuits and no numerical worked examples.

Confidence tags:
- `[sure]`: frame and speech agree, or the frame is unambiguous.
- `[likely]`: one source only, legible.
- `[unclear]`: unreadable, written `(?)`.

---

## p01  f_0009.jpg  [0:00:00 – 0:10:24]
For item 1 I used **f_0006.jpg** (0:09:36), because the pen toolbar covers item 1 in f_0009.

**Topic:** page header "Class session notes - 2026_10_05_M(?)" (cut off by the toolbar), then "Announcements:" (typed).  [sure]

**Board (typed):**
1. "Reminder - Problem Set 5 due 9:00AM CDT today on Canvas. Solutions will be available later today, but grading of these problem sets probably won't be completed before the exam."  [sure]
2. "Reminder - Semester Exam 1 will be in class on Wednesday 10/07/2026. See Canvas announcements for additional exam information and links to dummy template to practice scanning/uploading, and to the actual exam answer sheet template. YOU WILL NEED TO BRING A PRINTED PHYSICAL COPY OF YOUR ANSWER SHEET TEMPLATE TO THE EXAM."  [sure]
3. "Recitation section today will be an exam review session. Darsh will answer any questions you have, go over examples you request, and time permitting may do some problems from the old exams posted on Canvas under "Exam Preparation Materials"."  [sure]
4. "Problem Set 6 has just been released, and will be due on Wednesday 10/21/2026. Problem Set 6 covers maximum power transfer and semiconductors."  [sure]

**Diagram:** none.

**Speech vs board:** the two agree. Speech adds the following.
- PS6 material is not on SE1, but "you will be responsible for it for the second exam and the final" [0:02:08].  [sure]
- Scan the answer sheet to PDF rather than photographing it. Photos are lower resolution and the paper comes out gray [0:02:33–0:03:18].  [sure]
- Canvas "Exam Preparation Materials" holds three years of past SE1, SE2 and final exams. Each has short numerical or symbolic answers and a score histogram. The past exams are "probably the best guide", "but there are never any guarantees" [0:03:23–0:04:26].  [sure]
- Calculator: any calculator without communication or photo capability. A graphing calculator is fine; a phone is not [0:04:31].  [sure]
- Student Q&A on complex power (PS5 material) [0:04:51–0:08:32]. Nothing was written on the board.  [likely: the student's question is off-mic and fragmentary (ASR 0:04:57 "Number s. Why Mhmm...")]
  - Complex power was defined so that its real part is the average power.
  - The imaginary part "corresponds to the peak power" exchanged between source and load.
  - $\tfrac12\tilde V\tilde I^*$ vs $I_{rms}^2 Z_L$: "no hard and fast rule".
    - If you already have $\tilde V$ and $\tilde I$, use $\tfrac12\tilde V\tilde I^*$.
    - If $Z_L$ is easy to get, use $I_{rms}^2Z_L$.
    - If the load is "a big mess", use $\tfrac12\tilde V\tilde I^*$.
- **Speech imprecision** [0:06:04]: "in order to have power transfer, you need the current and the voltage to be out of phase... you only get that if there is an imaginary component to the impedance of the load."  [sure that this is the wording; the meaning was likely "reactive power"]
  - This is true of *reactive* power exchange ($Q\neq0$).
  - It is false for average power, which is largest when $v$ and $i$ are in phase.

**Re-derived (python3):**
- 10/07/2026 and 10/21/2026 are both Wednesdays.
- With random complex $\tilde I$ and $Z$, the three forms $\tfrac12\tilde V\tilde I^*$, $I_{rms}^2Z$ and $V_{rms}^2/Z^*$ agree to 1e-15.
- The instantaneous power $p(t)=P[1+\cos(2\omega t+2\theta_v)]+Q\sin(2\omega t+2\theta_v)$ reconstructs $v(t)i(t)$ to 6e-15.
- So $Q$ is the peak of the zero-mean exchanged component, which is consistent with his "peak power exchanged".

---

## p02  f_0025.jpg  [0:10:24 – 0:15:07]
Earlier states: f_0010, f_0013 (title visible), f_0020.

**Topic:** "Semiconductor properties" (underlined heading, f_0013).  [sure]

**Board:**
- "• moderate electrical conductivity - higher than insulators, lower than metals."  [sure]
- "• conductivity can be controlled over many orders of magnitude via voltage or impurities."  [sure]
- "• foundation for:" / "computer processors, GPU's, memory chips" / "communications chips" / "display" / "solar cells" (the list continues on p03)  [sure]

**Diagram:** none.

**Speech vs board:** the ASR writes "connectivity" for conductivity at 0:10:58, 0:11:09 and 0:12:24. The board says conductivity, and I followed the board. Speech adds the following.
- Impurities ("what's called doping") are a static change made during fabrication.  [sure]
- Voltage is applied during operation and changes the electron concentration in different parts of a device.  [sure]
- Silicon is "the most technologically important semiconductor material".  [sure]
- A display is "a giant chip... fabricated on glass".  [sure]
- Solar cells now use more silicon than computer chips. The crossover happened "probably over fifteen years ago".  [likely: the lecturer's claim, not checked]

**Re-derived:** nothing numeric.

---

## p03  f_0032.jpg  [0:15:07 – 0:17:05]
Earlier state: f_0029.

**Topic:** continuation of the "foundation for:" list.  [sure]

**Board:** "LED lighting" / "image sensors" / "etc."  [sure]

**Speech vs board:** speech adds the following.
- LEDs use a different semiconductor, gallium nitride, which emits short-wavelength light.  [sure]
- Before LED bulbs, lighting took "close to 20%" of residential electricity. Now it takes "less than 5%".  [likely: the lecturer's figures, not checked]
- A smartphone camera's image sensor is a silicon chip.  [sure]
- Why the course covers semiconductor physics: pushing the performance of a device or circuit "at the limits" requires knowing why the device behaves as it does, at a fundamental level [0:16:18–0:16:59].  [sure]

**Re-derived:** nothing numeric.

---

## p04  f_0033.jpg  [0:17:05 – 0:18:06]
**The frame is fully black** (sharpness 0, ink 0 %).  [sure]
- QUALITY.md lists it as the one "blurry" page. It is not blurry: the Zoom screen share dropped.
- `lecture.chapter.vtt` shows "Sharing Stopped" from 0:18:06 to 0:18:51.
- The audio is continuous.

**Speech:** "what we wanna do next is look at electronic states and what's called the band structure of semiconductor" [0:17:25]. A Zoom update prompt then closed the app [0:17:46–0:18:49].  [sure]

The board content for this span is on the next frame, f_0035 (p05).

---

## p05  f_0035.jpg  [0:18:06 – 0:19:08]
This is a full-desktop frame taken after the re-share. It shows the OneNote window "Class session notes - 2026_10_05_M - OneNote" and the taskbar clock reading 9:19 AM 10/5/2026.  [sure]

**Board:** the tail of the p03 list, then a heading being written: "Electronic states + band structure of s". f_0039 shows it finished as "Electronic states + band structure of semiconductors".  [sure]

**Speech:** an aside advising students to avoid UT-owned computers, because UT controls their administration [0:19:03]. No course content.  [sure]

---

## p06  f_0054.jpg  [0:19:08 – 0:25:43]
Earlier states:
- f_0036
- f_0039 (heading)
- f_0040, f_0041, f_0043 (isolated atom)
- f_0044, f_0045 (crystal drawing complete)
- f_0049, f_0053

**Topic:** "Electronic states + band structure of semiconductors" (underlined).  [sure]

**Board:**
- "Recall how Si atoms bond to form a Si crystal"  [sure]
- "isolated Si atom"  [sure]
- "4 valence electrons"  [sure]
- "Si crystal"  [sure]
- "electrons" (black label, arrow to one dot of a bond pair) and "covalent bond" (red label, arrow up to a red ellipse).  [sure]
- New heading at the bottom (f_0054): "Electronic states occupied by electrons:"  [sure]

**Diagram, isolated atom:**  [sure]
- A circle labelled "Si" stands for the nucleus plus the closed shells.
- Four black dots sit outside it at top, left, right and bottom. These are the valence electrons.
- The top dot is labelled "electron" with an arrow.

**Diagram, crystal (2-D representation):**  [sure]
- A 3 × 3 square array of circled "Si" atoms.
- Every nearest-neighbour pair, horizontal or vertical, is joined by two black dots inside a red ellipse. Each ellipse is one covalent bond, a shared electron pair.
- There are 12 bonds: 2 per row × 3 rows, plus 2 per column × 3 columns.
- Bonds that would extend past the edge of the array are not drawn ("We won't draw the ones that extend beyond the edge" [0:22:42]).

**Speech vs board:**
- "14 electrons in total" [0:21:13] is spoken but not written on this page.  [likely]
- Each of the four valence electrons is shared with a neighbouring atom to form a covalent bond, so every Si has four nearest neighbours.  [sure]
- **A 3-D crystal picture was discussed at 0:23:41–0:25:01, but it appears in no frame.** f_0044 (0:24:00) still shows only the 2-D drawing. What follows comes from speech only.  [likely: speech only]
  - The structure has "cubic symmetry".
  - Short bars are covalent bonds. Long bars are drawn only to show the cubes.
  - One red atom is bonded to four nearest neighbours that "form a tetrahedron... a pyramid with a triangular base".
  - The 2-D square drawing stands in for the 3-D one because the latter "is very hard to draw". The feature it keeps is the four nearest neighbours.

**Re-derived (python3):** filling 1s²2s²2p⁶3s²3p² gives 14 electrons: 10 in closed shells and 4 valence.

---

## p07  f_0091.jpg  [0:25:43 – 0:46:34]
Earlier states: f_0059, f_0082, f_0084, f_0088. The diagrams have scrolled off the top of f_0091, so I also used:
- f_0057 for the isolated-atom levels
- f_0059 for T = 0 K
- f_0076, f_0080, f_0081 for T > 0 K and the E_v/E_c definitions
- f_0088

**Topic:** "Electronic states occupied by electrons:" (the heading from p06).  [sure]

**Board:**
- Left side: "isolated Si atom", with a vertical arrow labelled "energy".  [sure]
  - Horizontal levels, bottom to top: 1s with 2 dots, 2s with 2 dots, 2p with 6 dots, 3s with 2 dots, 3p with 2 dots, then "⋮" above.
  - A brace "closed shells" spans 1s, 2s and 2p. A brace "valence electrons" spans 3s and 3p.
- Right side: "Si crystal". The axes are "energy" (vertical arrow) and "x" (horizontal arrow, meaning position).  [sure]
- T = 0 K band picture:  [sure]
  - The upper horizontal line is $E_c$ and the lower one is $E_v$.
  - The empty region above $E_c$ is braced "conduction band".
  - The region between the lines is braced "energy band gap".
  - Below $E_v$ are three rows of filled dots braced "valence band", with "⋮" below.
  - "T = 0 K: all electrons are in valence band, none in conduction band"  [sure]
- T > 0 K band picture, drawn to the right of the first:
  - The same $E_c$/$E_v$ lines, with three dots on or just above $E_c$.
  - The top valence-band rows contain some open circles, which are empty states.
  - A label above the picture, with an arrow to a conduction-band dot, is cut off in every frame. Speech: "these electrons that are up in the conduction band, we just call them electrons" [0:43:48].  [unclear: label text (?); the meaning is likely "electrons"]
  - "holes" (in quotes), with an arrow to an open circle in the valence band.  [sure]
  - "T > 0 K: most electrons are in valence band, a few in conduction band"  [sure]
- $E_v$ = max. energy in valence band  [sure: subscript overwritten, see below]
- $E_c$ = min energy in conduction band  [sure]
- "“Electrons” refers to negative charge carriers in conduction band"  [sure]
- "“Holes” refers to missing electrons in valence band that behave like positive charge carriers."  [sure]

**Speech vs board:**
- **Lecturer slip, corrected:** at 0:35:22 he says "e sub c here is the maximum energy... Sorry. E sub v is the maximum energy in the valence band". On the board the subscript of the first definition is visibly overwritten (c → v).  [sure]
  - I followed the corrected version: $E_v$ is the VB maximum and $E_c$ is the CB minimum.
  - $E_g = E_c - E_v$ is spoken at 0:35:16 but not written.
- Speech also adds the following.
  - The number of valence-band states is "exactly equal to the total number of valence electrons". So at 0 K the VB is full and the CB is empty [0:33:57].  [sure]
  - There are no states in the gap "in a structurally perfect and pure semiconductor" [0:33:07].  [sure]
  - Band states "extend throughout the entire crystal" [0:32:10].  [sure]
  - Temperature measures *average* energy. Individual electrons have a spread of energies, so at T > 0 a few of them reach the CB [0:42:01–0:43:16].  [sure]
  - Bubble analogy for holes [0:45:22–0:46:15].  [sure]
- Student Q at 0:36:28: "what does it mean to be in the valence band".  [sure]
  - VB/CB is the physics language. The chemistry language is bonding/antibonding orbitals, which form when 3s and 3p mix.
  - Electrons in a full band can swap places but give no net motion. Net motion needs an empty state to move into [0:36:35–0:40:36].
- Student Q at 0:40:51: is a CB electron in an orbital higher than 3p?  [sure]
  - No. In the crystal the original orbitals no longer exist.
  - The states are combinations of orbitals that form the bonding and antibonding orbitals, i.e. the VB and CB [0:41:20–0:41:45].

**Re-derived (python3):** the dots drawn on the atom levels total 2+2+6+2+2 = 14 = Z(Si).

---

## p08  f_0099.jpg  [0:46:34 – 0:48:05]
Earlier states: f_0094, f_0098.

**Board:** "How do conduction + valence band states form? How are they related to covalent bonds? How are bands related to carrier concentrations, mobility, etc.?"  [sure]
- The second "How" has a corrected letter.  [likely]

**Speech vs board:** they agree. He says he has given "the endpoints" (the isolated atom and the crystal) and now asks what happens in between [0:46:42].  [sure]

**Re-derived:** nothing numeric.

---

## p09  f_0114.jpg  [0:48:05 – 0:58:41]
Earlier states:
- f_0100 (top text)
- f_0103
- f_0104 (empty axes)
- f_0105 (3s/3p wedges)
- f_0106 (hatching and labels)
- f_0108 (4N braces and "occupied by 4N valence electrons")
- f_0113

**Board:**
- "Consider N atoms, eg, Si, separated by distance a."  [sure]
- "The states occupied by valence electrons are distributed in energy, as a function of a, as follows:"  [sure]
- Diagram, described below.  [sure]
- "In semiconductors, electric current is carried by electrons moving through the crystal in conduction-band or valence-band states, BUT" (continues on p10)  [sure]

**Diagram (enough detail to redraw):**
- Axes: "energy" is vertical and "a" (interatomic separation) is horizontal.  [sure]
- At the right, where $a$ is large, there are two flat lines.  [sure]
  - The upper line is labelled "3p (6N states)" and the lower one "3s (2N states)".
  - A brace on the far right spans both lines: "occupied by 4N valence electrons".
  - Under the lines is "↦ isolated atoms", an arrow pointing right that marks the large-$a$ limit.
- Moving left, toward smaller $a$:
  - Each line fans out into a widening wedge, i.e. a band of slightly different energies.  [sure]
  - The inner edges of the 3p and 3s wedges meet at an intermediate $a$, drawn as a "<" vertex, and the two merge.  [sure]
  - Further left, the merged region splits again into two separate hatched bands.  [sure]
    - The upper band is labelled "conduction band, or anti-bonding orbitals" and braced "4N states" on the left edge.
    - The lower band is labelled "valence band, or bonding orbitals" and braced "4N states".
    - The gap between them is braced "energy band gap".
- A vertical dashed line at small $a$ is labelled below "semiconductor crystal, eg, Si". This is the equilibrium separation found in nature [0:52:55].  [sure]

**Speech vs board:**
- $N$ atoms have $2N$ 3s states and $6N$ 3p states [0:50:46].  [sure]
- Overlap makes new states that extend across the atoms, and "each of them has to have a slightly different energy". That is why the levels spread [0:51:33–0:52:11].  [sure]
- Then there is an intermediate range where the states are "all just kind of mixed together", after which they "split apart again" [0:52:28–0:52:50].  [sure]
- The VB and the CB each have 4N states [0:55:21].  [sure]
- Student Q at 0:55:46: "six N states... two valence band?"  [sure]
  - 6N is the *total* number of 3p states available. Each atom has six 3p states, but only two of them are occupied.
  - The crystal has 4N valence electrons, and they fill the 4N VB states at 0 K [0:55:52–0:56:51].
- Misconception he raises [0:57:00–0:57:41]: you might expect the VB electrons to carry almost all the current "because you have so many more electrons", but "that's not quite the case".  [sure]

**Re-derived (python3):**
- $2N+6N=8N=4N_{VB}+4N_{CB}$.
- The valence electrons number $4N$, which equals the VB capacity. So the VB is full and the CB empty at 0 K, consistent with the board.

---

## p10  f_0169.jpg  [0:58:41 – 1:12:51]
Earlier states:
- f_0123 (end of the "BUT" sentence)
- f_0132 ("In brief")
- f_0143
- f_0145 (holes paragraph complete)
- f_0153, f_0155, f_0156
- f_0158 (new heading)
- f_0161, f_0166

**Board:**
- "... BUT only electrons in a partially filled band contribute to current."  [sure]
- "In brief, this is because if every state in a band is occupied, each electron has a counterpart electron in the same band moving in the opposite direction."  [sure]
- "Because a completely filled band carries no electric current, instead of thinking about electrons moving in an almost-filled valence band, we can think about how the empty states move in the band. These empty states are called "holes"." ("empty" is underlined)  [sure]
- Heading: "Occupation of states by electrons – Fermi distribution function" (underlined)  [sure]
- "The probability that a state at energy E is occupied by an electron is given by the Fermi distribution function, f(E):" ("Fermi distribution function" is underlined)  [sure]
- $$f(E)=\frac{1}{e^{(E-E_F)/k_BT}+1}$$  [sure: the frame is clear, and the speech is "one over e to the energy minus a reference energy e sub f... over Boltzmann's constant times the temperature plus one"]
- $k_B$ = Boltzmann constant $=1.381\times10^{-23}$ J/(?)  [sure for the number; the unit's last character runs off the right edge (?), and p19 rewrites it as J/K]

**Diagram:** none. The momentum argument was spoken with hand gestures only (checked f_0121–f_0140).  [sure]

**Speech vs board:**
- Each band state has an energy and a momentum ("think of it basically as a velocity"). For every state with momentum one way there is a state with the opposite momentum, so the motions in a full band cancel [0:59:23–1:01:28].  [sure]
- If one partner state is empty, there is net motion and therefore current [1:00:21].  [sure]
- Tracking only the empty states works because the motion of the filled states plus that of the would-be electrons in the empty states "has to add up to zero" [1:02:12].  [sure]
- Student Q at 1:02:23: in undoped Si, do both bands carry current only because CB electrons leave holes behind?  [sure]
  - In a pure, perfect semiconductor, yes. Every CB electron has an associated VB hole, and both contribute to the current [1:02:48–1:03:39].
  - With doping, impurity atoms "can pull some electrons out of the valence band". Those electrons sit at the impurity, not in the CB, and the holes they leave still carry current. So there is no one-to-one link between CB electrons and VB holes [1:03:39–1:04:11].
- Student Q at 1:04:19: do individual electrons go up to the CB briefly and then drop back?  [sure]
  - Yes. On average, whenever one drops down another goes up.
  - The net motion of the CB electrons and the net motion of the VB holes each contribute to the current [1:04:48–1:06:04].
- The Fermi function is new: it was not covered in 302/302H [1:09:02]. He leaves the statistical physics to ECE 339 [1:11:23].  [sure]
- $k_B$ "converts temperature to an equivalent energy" and has units of energy over temperature [1:12:28].  [sure]

**Re-derived (python3):** CODATA gives $k_B=1.380649\times10^{-23}$ J/K. The board value $1.381\times10^{-23}$ is correct to 4 s.f. (relative difference $2.5\times10^{-4}$).

---

## p11–p18  f_0174, f_0177, f_0181, f_0184, f_0185, f_0187, f_0189, f_0190  [1:12:51 – 1:13:03]
These are accidental scroll and ink states while he fixed the "J/K" that ran off the edge ("Be careful where I rest my hand here. Let me try to do this." [1:12:56]).  [sure]
- Each frame shows the p10 content (holes paragraph, Fermi heading, $f(E)$, the $k_B$ line) at a different scroll offset.
- **No new content.**
- Pages 16–18 have no captured speech. That is expected: the whole span lasts 12 s, and the speech belongs to p10 and p19.

---

## p19  f_0203.jpg  [1:13:03 – 1:17:54]
Earlier states: f_0191 (definitions block complete), f_0195, f_0200 (sentence half-written).

**Board (f_0191):**
- $$f(E)=\frac{1}{e^{(E-E_F)/k_BT}+1}$$ (repeated)  [sure]
- $k_B$ = Boltzmann constant $=1.381\times10^{-23}$ J/K  [sure]
- $T$ = temperature in K  [sure]
- $E_F$ = Fermi energy or Fermi level = energy at which $f(E)=\tfrac12$.  [sure]

**Board (f_0203):**
- "In a pure, perfect semiconductor, the concentrations of electrons (n) and holes (p) must be equal to each other, and $E_F$ is near the middle of the energy band gap."  [sure]

**Speech vs board:**
- Limits [1:14:35–1:15:47]. He calls all three physically plausible.  [sure]
  - $E\ll E_F$: the exponent is very negative, so $f\to1$.
  - $E=E_F$: $e^0=1$, so $f=\tfrac12$.
  - $E\gg E_F$: the exponent is large and positive, so $f\to0$.
- $E_F$ is "sort of the dividing line" between energies with higher and lower probability of occupation [1:13:59].  [sure]
- $n=p$ "because the only way that you get electrons in the conduction band is by leaving behind holes in the valence band" [1:16:04].  [sure]
  - So the probability of an empty VB state and the probability of a filled CB state must be similar.
  - Hence $E_F$ lies "near the middle of the band gap... Not necessarily exactly in the middle" [1:16:59–1:17:43].
- The ASR "framing level" at 1:17:34 is "Fermi level".  [sure]
- The next class is Monday 10/12, since Wed 10/7 is SE1. It will go from the Fermi function to electron and hole concentrations, and the implications for devices [1:17:50–1:18:18].  [sure]

**Re-derived (python3):**
- $f$ at $(E-E_F)/k_BT = -5, -3, -1, 0, 1, 3, 5$ is 0.9933, 0.9526, 0.7311, 0.5, 0.2689, 0.0474, 0.0067.
- Symmetry: $f(E_F+\Delta)=1-f(E_F-\Delta)$ holds exactly. This underlies the argument that $E_F$ sits near midgap when $n = p$; the argument itself is not on the board.
- $k_BT$ at 300 K is $4.142\times10^{-21}$ J = 0.02585 eV.

---

## Board-error / discrepancy audit
- **$E_v$ definition (p07, 0:35:22):** he said "e sub c" for the VB maximum and corrected it aloud at once. The board subscript was overwritten c → v, so the final board is correct.
- **$k_B$ unit (p10):** "J/(?)" ran off the page edge and was rewritten as "J/K" on p19. Not an error.
- **Complex-power answer (p01 speech, 0:06:04):** "to have power transfer, you need the current and the voltage to be out of phase" is wrong if read as average power. It is right for reactive power ($Q$). It was spoken only, never written.
- **ASR errors:**
  - "connectivity" → conductivity.
  - "framing level" → Fermi level.
  - "induction band" (0:40:54) → in the conduction band.
- **Not captured:**
  - the 3-D Si crystal picture (0:23:41–0:25:01)
  - the label above the T > 0 K picture (likely "electrons")
  - the full page header ("2026_10_05_M(?)")
- **QUALITY.md correction:** f_0033 is a black frame from the dropped share, not a blurry page.
- No numerical board errors. The only number on the board ($k_B$) checks out.
