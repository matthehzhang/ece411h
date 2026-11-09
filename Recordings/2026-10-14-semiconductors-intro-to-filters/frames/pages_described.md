# 2026-10-14-semiconductors-intro-to-filters: page descriptions

Frame-description pass per `DESCRIBE_FRAMES_PROMPT.md`. Inputs: `QUALITY.md`, `frames/pages_with_speech.md`, all 23 page JPEGs, neighbouring frames from `frames/index.txt` (listed per page), `contact_sheet.jpg`, `transcript.paragraphs.md`, `transcript.txt` (source folder `Recordings/2026-10-14-semiconductors-intro-to-filters/`).

Source caveats carried from QUALITY.md: tablet (not doc-cam), 0 blurry pages; 37 of 57 page-final frames are scroll/extension repeats; Deepgram mean confidence 0.96, 13 utterances < 0.7; student questions off-mic. No numeric worked examples on the board this lecture: the only numbers are constants spoken aloud (e, k_BT, E_g, V_bi), all re-derived below.

Confidence tags: `[sure]` frame and speech agree or the frame is unambiguous; `[likely]` one source only, legible; `[unclear]` cannot be read or meaning not determinable. `(?)` = unreadable.

---

## p01  f_0039.jpg  [0:00:00 – 0:10:36]
**Frames used:** f_0002 (0:00:03, top of page with announcements), f_0010 (title and circuit), f_0024 (0:05:13), f_0036 (0:10:35), f_0039 (page-final, scrolled; top cut off).
**Topic:** typed header "Class Session Notes 2026_10_14" (truncated by toolbar) [sure]; handwritten "From last time – pn junction diode" [sure]
**Board:**
- Typed: "Announcements: 1. A second handout on algebra with complex numbers has been posted. Material in the handout will be very useful for our upcoming coverage of circuit frequency response, filters, and Bode plots. 2. Reminder – my office hours today will be 2:30–4:00PM today rather than 10:30–11:55AM, still in EER 3.802."  [sure]
- "V = 0 (equilibrium)"  [sure]
- $V_{bi}$ = "built-in" potential  [sure]
- $I = 0$  [sure]
**Diagram:**
- Top: a bar split by a dashed vertical line into "p" (left) and "n" (right); a wire from each end runs up to a source "V" with "+" on the left and "−" on the right. "≡" a diode symbol (triangle pointing right, so the anode is on the left) between two terminal circles, with the same source V (+ left) connected across it.  [sure]
- Middle (V = 0 band-edge diagram): $E_c$ (upper solid curve) is high on the p side (left) and bends down to a lower level on the n side (right); $E_v$ runs parallel below it. $E_F$ is one dashed horizontal line straight across, close to $E_c$ on the n side and close to $E_v$ on the p side. Electrons (filled dots) sit on the n-side $E_c$; holes (open circles "oooo") sit at the p-side $E_v$. A vertical arrow labelled $eV_{bi}$ runs from the n-side $E_c$ up to a dashed line extended from the p-side $E_c$ level.  [sure]
- Red additions (~0:06:05–0:07:50): a dashed vertical line at the junction; three red ⊕ (ionized donors) just under $E_c$ on the n side next to the junction; three red ⊖ (ionized acceptors) just over $E_v$ on the p side next to the junction.  [sure: speech "positively charged ... ionized donors in the n-type material ... negatively charged ionized acceptors in the p-type material"]
- Lower ("before contact") diagram, drawn ~0:05:21–0:07:00, labels "P" (left) and "n" (right): flat bands, $E_c$ at one level across, $E_v$ at one level across. p side: a dashed line just above $E_v$ with ⊖ (acceptor ions) on it, holes "ooooo" just below $E_v$. n side: electrons (dots) just above $E_c$, ⊕ (donor ions) just below $E_c$, dashed $E_F$ below them. A red arrow runs from the n-side $E_c$ at the junction diagonally down to the p-side $E_v$ at the junction; short red strokes on the p-side $E_c$ and the n-side $E_v$ at the junction.  [likely: red arrow = electron near the junction recombining with a hole, from speech 0:06:47–0:07:22; the dashed lines as the separate Fermi levels from speech 0:06:35 "the Fermi level was, say, down here for p type and up here for n type"]
- A small circle with a vertical stem at the right margin (f_0039 x≈1078).  [unclear: stray mark, no speech]
**Speech vs board:** speech says the usual office hours are "11:30 to 11:55AM"; the typed board says "10:30–11:55AM". Followed the board. `[board differs from speech]` Speech "second hand ad" = handout. Student question at 0:04:44 (built-in potential from initial diffusion) answered "basically correct"; the ionized-dopant drawing is his elaboration. "Anytime you have charge, you have an electric field, and the integral of the electric field is potential" [0:08:01].  [sure]
**Re-derived:** no numbers on this page.

## p02  f_0046.jpg  [0:10:36 – 0:13:10]
**Frames used:** f_0040 (0:11:56), f_0046.
**Topic:** continuation of p01 (no new title)
**Board:**
- "When a voltage $V>0$ is applied across the diode, the potential energy difference, for electrons, is shifted by $(-e)V$:"  [sure]
**Diagram:** p01's diagrams scrolled up.  [sure]
**Speech vs board:** student asks "what is e again?" [0:11:57]; answer: "fundamental charge ... 1.6 times 10 to the minus nineteenth coulombs ... charge magnitude of the electron ... so the charge of the electron is minus e." The annotation is written on p04's frames.  [sure]
**Re-derived:** $e = 1.602176634\times10^{-19}$ C; his 1.6e-19 is the 2-s.f. value (python ok).

## p03  f_0048.jpg  [0:13:10 – 0:13:35]
**Frames used:** f_0048.
**Topic:** scroll repeat of p01/p02 (V = 0 diagram shown again as "our starting point").
**Board:** no new ink.  [sure]
**Speech vs board:** "this p side, the left hand side in this diagram, is gonna move lower in energy ... the Fermi levels on the p side and the n side will now be different from each other, and the difference will be minus e times v" [0:13:15]. The *magnitude* of the split is $eV$ (board p04 labels it "eV").  [sure]

## p04  f_0057.jpg  [0:13:35 – 0:19:12]
**Frames used:** f_0049 (0:13:38), f_0057; crop of f_0060 for carrier symbols.
**Topic:** continuation (no title)
**Board:**
- Under "$(-e)V$": a hooked arrow pointing at e, with "charge magnitude of electron".  [sure]
- $eV$ (double arrow between the two Fermi levels)  [sure]
- $eV_{bi} - eV$ (barrier height label)  [sure]
- $\rightarrow I$  [sure]
**Diagram:** three panels joined by "→" arrows.
- (a) Circuit: top wire has terminal circle, diode (triangle pointing right = anode left), terminal circle; side wires drop to a source at the bottom marked "+" left, "−" right, labelled V. So + connects to the anode.  [sure]
- (b) The p|n bar (p left, n right, dashed junction) with the source below: + to the p end, − to the n end, labelled V.  [sure]
- (c) V > 0 band-edge diagram: the p-side $E_c$ (left) is still higher than the n-side $E_c$ but by less than at V = 0. n-side $E_F$ dashed just under the n-side $E_c$ (labelled $E_F$ at right); p-side $E_F$ dashed on the left (labelled $E_F$), just over the p-side $E_v$ with holes "oooo". Double arrow "eV" between the two $E_F$ lines. An arrow from the n-side $E_c$ up to a dashed line extended from the p-side $E_c$ is labelled $eV_{bi}-eV$. An electron at the barrier-top energy with an arrow pointing **left** (n → p). A hole "o" below the bands with an arrow pointing **right** (p → n). "→ I" at the bottom (current p → n).  [sure]
**Speech vs board:** ASR "the difference in the framing level is z times v" = "the difference in the Fermi level is e times V" [0:14:23]. Speech: "the height of this barrier now is e times the built in potential minus e times v. So it's lower" [0:14:37]. At 0:14:08 he says "electrons on the p side... Or sorry. On the n side, (are?) holes on the n side": a slip/ASR garble; the board has electrons on the n side and holes on the p side. Followed the board.  [sure]
**Re-derived:** none (symbolic).

## p05  f_0059.jpg  [0:19:12 – 0:19:13]
Scroll repeat of p04's three-panel diagram. No new ink.  [sure]

## p06  f_0060.jpg  [0:19:13 – 0:20:11]
**Frames used:** f_0060.
**Board:**
- "The energy barriers for electrons + holes to move across the pn junction are shifted by $-eV$"  [sure]
- "$\Rightarrow I \neq 0$."  [sure]
**Speech vs board:** "shifted then means that they are reduced, and the consequence of that is that the current is no longer zero" [0:19:46].  [sure]

## p07–p11  f_0062, f_0063, f_0065, f_0066, f_0069  [0:20:11 – 0:20:44]
Horizontal and vertical scroll repeats of p06. No new ink in any of them (checked each frame).  [sure]
Speech: "using ... knowledge of the Fermi distribution function to figure out how many electrons are there at sufficiently high energy to diffuse across the junction and not be blocked by the barrier, and how does that concentration depend on the voltage" [0:20:12].

## p12  f_0074.jpg  [0:20:44 – 0:21:43]
**Frames used:** f_0073 (0:21:36), f_0074.
**Board:**
- "The concentration of electrons/holes with energy higher than the barrier increases exponentially with V:" ("exponentially" underlined)  [sure]
**Speech vs board:** speech adds "because then the current, it'll be proportional to that concentration" [0:21:05].  [sure]

## p13  f_0076.jpg  [0:21:43 – 0:24:00]
**Frames used:** f_0075, f_0076; f_0086 and f_0092 for the f(E) curve drawn later on these axes.
**Board:**
- "V = 0:"  [sure]
- $f(E)=\dfrac{1}{e^{(E_c+eV_{bi}-E_F)/k_BT}+1}$  [sure: speech "e to that energy, e c plus e VBI, minus the Fermi energy over k b t plus one"]
**Diagram:** the V = 0 band diagram (p left, n right): $E_c$, $E_v$, single dashed $E_F$; electrons on the n-side $E_c$; holes at the p-side $E_v$; arrow $eV_{bi}$ from the n-side $E_c$ up to the barrier-top dashed line. Both the barrier-top line and $E_F$ are extended right to a second plot: vertical axis = energy (shared with the band diagram), horizontal axis "f(E)" with ticks "0" at the origin and "1". The f(E) curve was added at ~0:27:12–0:27:30 (f_0086): near 1 at low energy, through about 1/2 at the $E_F$ line, falling toward 0 above $E_F$, essentially 0 at the barrier-top line.  [sure]
**Speech vs board:** ASR "connection main edge" = conduction band edge [0:23:22]. Speech: "the energy up here is just the energy of the conduction band edge $E_c$ plus $e V_{bi}$".  [sure] Note: $E_c$ in this formula is the **n-side** conduction-band edge (the arrow starts there).  [likely: inferred from the diagram, confirmed by the student exchange at 0:33:36 about which $E_F$ to use]
**Re-derived:** $f(E_F)=1/(e^0+1)=0.5$ (python ok).

## p14  f_0080.jpg  [0:24:00 – 0:25:51]
**Frames used:** f_0077–f_0080.
**Board:**
- $\approx e^{-(eV_{bi}+E_c-E_F)/k_BT}$  [sure]
- "V > 0:" (heading for the next part)  [sure]
**Speech vs board:** justification spoken, not written: "at room temperature, k sub b times t ... is, like, one fortieth of an electron volt" [0:24:12]; "the band gap of silicon is 1.1 eV, then ... VBI might be maybe point six or point seven eV. And compared to one fortieth, that's much bigger" [0:24:35]. So the exponential is ≫ 1 and the +1 is dropped. ASR "k sub b times c" = $k_BT$. Unit slip: $V_{bi}$ is a potential (0.6–0.7 **V**); $eV_{bi}$ is 0.6–0.7 eV.  [sure]
**Re-derived (python):** $k_BT$ at 300 K = 0.02585 eV (1/40 = 0.025, 3.4 % low; fine as a mnemonic). $eV_{bi}/k_BT$ = 23.2 (0.6 V) to 27.1 (0.7 V) with 0.02585 eV; 24–28 with 1/40. $e^{23.2}=1.2\times10^{10}$, so the "+1" is negligible. Boltzmann vs Fermi at $E-E_F=3k_BT$: 0.0498 vs 0.0474 (5 % error); at $5k_BT$: 0.6 % error. No board error.

## p15  f_0120.jpg  [0:25:51 – 0:39:47]
**Frames used:** f_0082 (0:27:12), f_0086 (0:27:30), f_0092 (0:31:29), f_0100 (0:33:08), f_0110 (0:37:18), f_0120; crops of f_0120.
**Topic:** "V > 0:" [sure]
**Board:**
- $f(E)=\dfrac{1}{e^{(E_c+eV_{bi}-eV-E_F)/k_BT}+1}$  [sure]
- $\approx e^{-(eV_{bi}+E_c-E_F)/k_BT}\,e^{eV/k_BT}$, with a brace under $e^{eV/k_BT}$ and an arrow from the note "f(E) increases exponentially with V."  [sure]
- "Similarly, holes diffuse from p side to n side of the junction, with exponentially increasing probability with V."  [sure]
- "$\Rightarrow$ I increases exponentially with voltage for V > 0."  [sure]
**Diagram:** V > 0 band diagram: p-side bands lowered; n-side $E_F$ dashed just under the n-side $E_c$ (labels "$E_c$" and "$E_F$" crowded together at the right); p-side $E_F$ dashed on the left, labelled $E_F$, above the holes "oooo"; double arrow "eV" between the two $E_F$ levels; arrow "$eV_{bi}-eV$" from the n-side $E_c$ up to the barrier-top dashed line, which extends right to the f(E) axes. On the f(E) axes (0 to 1), a dot on the $E_F$ line at f ≈ 1/2; no curve drawn on these lower axes.  [sure]
- Green dashed lines (~0:36:12, "let me run it in a different color"): (i) one starts at the n-side $E_F$, stays level through the junction, then slopes down on the p side to meet the p-side $E_F$; (ii) the other starts at the p-side $E_F$, stays level through the junction, then rises on the n side to meet the n-side $E_F$. Speech: "a Fermi level for the electrons that kinda goes like this, and then a Fermi level for the holes that kind of goes like this."  [sure; the term "quasi-Fermi level" was not used]
- Extra electrons (~0:37:39–0:38:30): two dots at the barrier-top energy above the n side and one dot at the same energy above the p side (for the student question on why there is no current at V = 0). A short vertical tick under the p-side dot.  [likely; the tick is unclear]
**Speech vs board:** speech "e to the e c plus EVBI minus EV minus the Fermi level over KT. All this plus one" matches. "It's minus eV over kBT in the denominator so becomes plus eV over kBT in the numerator" [0:29:50]. Notation apology: "these two e's that mean different things ... lower e here, obviously, is 2.71828. This e up here is the charge magnitude of the electron" [0:30:37]. Validity caveat spoken only: the approximation holds "unless you apply a very large voltage" [0:28:47].  [sure]
**Re-derived (python):** with illustrative values $V_{bi}=0.7$ V, $E_c-E_F=0.1$ eV, $k_BT=0.02585$ eV (mine, not his), $f(V)/f(0)=e^{eV/k_BT}$ exactly in the Boltzmann limit: 47.9 at 0.1 V, 1.10e5 at 0.3 V, 2.51e8 at 0.5 V; exact Fermi vs approximation differ by < 1e-5 relative. Board algebra correct. No board error.

## p16  f_0126.jpg  [0:39:47 – 0:40:04]
**Frames used:** f_0125, f_0126.
Scroll repeat showing the two text lines of p15. No new ink.  [sure]
**Speech:** "for positive voltage, the current increases exponentially with the voltage, and it flows from the p side to the n side in the diode" [0:39:50].  [sure]

## p17  f_0132.jpg  [0:40:04 – 0:43:49]
**Frames used:** f_0127 (0:40:38), f_0130 (0:43:48), f_0132; f_0174/f_0175 (0:51:08 / 0:52:48) for the later correction; crops of f_0130 and f_0175.
**Board:**
- "For V < 0, we have"  [sure]
- "I is in the opposite direction, and I roughly independent of V for V < 0"  [sure]
- "← I"  [sure]
**Diagram:** reverse-bias band diagram. The p side (left) is raised far above the n side; $E_c$ and $E_v$ drop steeply through the junction. p side: one electron (dot) on the p-side $E_c$ with an arrow pointing **right** (p → n, sliding down the barrier); a dashed line just above the p-side $E_v$ (p-side $E_F$, unlabelled); holes "oooo" at the p-side $E_v$. n side: electrons "••••" on $E_c$ (labelled $E_c$); $E_v$ (labelled $E_v$) with a hole "o" under it and an arrow pointing **left** (n → p). "← I" below (current n → p).  [sure]
- Unlabelled dashed line on the n side: first drawn just **above the n-side $E_v$** (f_0130, f_0172). At ~0:51:31 he said "This was not correct. This should be up here", scribbled it out, and redrew a dashed line just **below the n-side $E_c$** (f_0175).  [sure: both frames plus speech] `[board error, self-corrected]`: the n-side Fermi level belongs just under $E_c$. The page-final frame f_0172 (0:51:07) predates the fix; use f_0175.
**Speech vs board:** "if we just try to generalize that expression, it would tell us that, okay, the current still flowing in the same direction, but it becomes exponentially smaller. But that's not quite correct" [0:40:25]. Low-confidence word "(exponentially?)" at 0:41:36 ("we should reduce exponentially the concentration of carriers that have high enough energy") fits the context.  [likely]

## p18  f_0172.jpg  [0:43:49 – 0:51:07]
**Frames used:** f_0133 (0:44:16), f_0141 (0:45:27), f_0152 (0:48:32), f_0155 (0:48:41), f_0161–f_0172.
**Topic:** "Thus, the overall I–V characteristic for a pn junction diode is:"  [sure]
**Board:**
- $I = I_0\left(e^{eV/k_BT}-1\right)$  [sure: speech "I naught times e to the eV over k b t ... minus one"]
**Diagram:** I–V axes (I vertical, V horizontal), curve in blue: for V > 0 it rises exponentially; for V < 0 it flattens to a small negative constant just below the V axis; a blue **dashed** branch at large negative V turns sharply downward (breakdown, "we won't talk about that in detail").  [sure]
**Speech vs board:** "this minus one comes from these electrons and these holes moving across the junction as shown over here [the V < 0 diagram]. And it's negative because that current is in the opposite direction" [0:45:09]. "That's before you reach this kind of behavior, which is called breakdown of the diode" [0:49:39].  [sure]
**Re-derived (python, 300 K):** $I/I_0$ = −0.979 at −0.1 V, −0.99956 at −0.2 V, −1.0000 at −0.5 V, 0 at 0 V, 46.9 at 0.1 V, 1.10e5 at 0.3 V, 1.20e10 at 0.6 V. The curve shape on the board matches. No board error.

## p19  f_0183.jpg  [0:51:07 – 0:53:36]
**Frames used:** f_0156 (0:50:24), f_0179, f_0182, f_0183.
**Board:** second set of I–V axes, curve in red: zero along the axis for all V < 0 and small V > 0, then an almost vertical rise at a positive V.  [sure]
**Speech vs board:** drawn ~0:49:52–0:50:26 for the "one-way valve" question: "if you were looking at this, sort of zoom [out] some ... it would still look like zero, and then all of a sudden, it'll turn up very rapidly. And this is probably what you're thinking of." Same diode, larger current scale.  [sure] Also in this interval: the n-side $E_F$ correction on p17 (0:51:31).
**Re-derived:** none.

## p20  f_0186.jpg  [0:53:36 – 0:57:00]
**Frames used:** f_0184 (0:55:12, title), f_0185, f_0186.
**Topic:** "LED: light emitting diode"  [sure]
**Board:**
- "electrons + holes recombine and energy lost by the electron is emitted as light."  [sure]
- "$\rightsquigarrow h\nu$"  [sure]
**Diagram:** forward-bias band diagram (p left, n right, Fermi levels dashed on each side). An electron above the n-side $E_c$ moves left across the junction (arrow ←); a hole "o" at the p-side $E_v$ moves right (o →). At the junction an electron (dot) on $E_c$ has a long vertical arrow straight down to a hole "o" at $E_v$, with a wavy arrow "⇝ hν" leaving to the right.  [sure]
**Speech vs board:** "in an LED, it's designed and optimized so that that energy is given off as a photon" [0:55:48]. hν: "the Greek letter nu ... Planck's constant times, this is the frequency of the electron. Oh, sorry, of the photon" [0:56:36]: spoken slip, self-corrected.  [sure]

## p21  f_0205.jpg  [0:57:00 – 1:08:24]
**Frames used:** f_0187 (0:57:36), f_0188 (1:00:00), f_0196 (1:02:24), f_0197 (1:04:48), f_0199 (1:06:06), f_0203 (1:07:12), f_0205.
**Topic:** "solar cell" (underlined)  [sure]
**Diagram (band):** forward-biased junction, $E_F$ split "eV" (double arrow between the n-side dashed $E_F$ under $E_c$ and the p-side dashed $E_F$ over $E_v$). A wavy arrow labelled "hν" comes in from the left to the junction. A vertical line at the junction runs from $E_v$ up to $E_c$ (photon absorbed, electron promoted). The new electron at $E_c$ has an arrow → into the n side; the new hole "o" at $E_v$ has an arrow ← into the p side. "I ←" below (current flows n → p inside the device).  [sure]
- Green additions (between 1:02:24 and 1:04:48): a green electron well above $E_c$ with a green arrow down to the $E_c$ electron, and a green hole well below $E_v$ with a green arrow up to the $E_v$ hole.  [likely: matches speech 1:03:16–1:03:40, "you might initially get a high energy hole and a high energy electron, but then very quickly, those will relax back down to the band edge energy, and then that extra energy is lost as heat"]
**Diagram (I–V, right):** I vertical, V horizontal. Black curve = illuminated cell: diode-shaped but shifted down, crossing the I axis at a negative current and the V axis at a positive voltage. A dot on the curve in the 4th quadrant (V > 0, I < 0) with dashed lines to both axes, forming a rectangle (operating point for maximum $|IV|$). Red curve (~1:06:59) = dark characteristic, "shifted upwards", through the origin. A small vertical tick near the V axis.  [sure for the curves; the tick is unclear]
**Speech vs board:** "current flowing in this direction, so from lower voltage to higher voltage ... that corresponds to energy being supplied, and that energy is coming from the energy of the photon" [0:58:19–0:58:51]. "You wanna operate at a point where the product of the current and the voltage in the fourth quadrant is the maximum" [1:05:02].  [sure]
**Re-derived:** spoken figures only. Si $E_g$ "1.1 eV" (1.12 eV at 300 K); the absorption edge $\lambda = hc/E_g$ = 1107–1127 nm (python; mine, not his). "Low 20% range is very good efficiency": not checkable from the source.

## p22  f_0214.jpg  [1:08:24 – 1:12:34]
**Frames used:** f_0206 (1:09:36), f_0209 (1:10:12), f_0210 (1:11:26), f_0214.
**Topic:** "Circuit Frequency Response – Bode Plots and Filters" (underlined)  [sure]
**Board:**
- "Reading: Ulaby et al, Chapter 9."  [sure; ASR "Ulaby Dahl" = "Ulaby et al."]
- "Filters are circuits that produce output signals with specific (useful) frequency dependence:"  [sure]
- "high-pass filter: high-frequency signals transmitted, low-frequencies suppressed."  [sure]
**Speech vs board:** speech adds the two-port picture (no diagram drawn): "a circuit that has, say, two input terminals and two output terminals ... relationships between, say, the voltage at the input and the voltage at the output ... the dependence of those relationships on frequency is what we refer to as the response of the filter" [1:10:58–1:11:29]. High-pass: high frequencies "transmitted from the input to the output, quite easily, without much attenuation, and low frequency signals are strongly attenuated" [1:11:51].  [likely: speech only for the two-port]

## p23  f_0223.jpg  [1:12:34 – 1:15:45]
**Frames used:** f_0216 (1:13:45), f_0220 (1:14:56), f_0223.
**Board:**
- "low-pass filter: low-frequency signals transmitted, high frequencies suppressed."  [sure]
- "band-pass filters: signals within a specified frequency range are transmitted."  [sure]
- "band-reject filters: signals within a specified frequency range are suppressed."  [sure]
- "passband: range of frequencies transmitted, or "passed", by the circuit."  [sure]
- "Circuit frequency response can be described algebraically by a transfer function, and" ("transfer function" underlined)  [sure]
- Continuation, **speech only** (no frame after 1:15:45): "It can also be described graphically by what we call Bode plots" [1:15:43–1:15:55].  [likely]
**Speech vs board:** band-reject is "kind of the inverse of" band-pass [1:13:48]. Close: "we will stop here for today and pick up with a discussion of transfer functions next time" [1:16:05].  [sure]

---

## Discrepancy and board-error log
1. **p17/p19, 0:51:31: n-side Fermi level misplaced in the V < 0 diagram, self-corrected.** First drawn just above the n-side $E_v$; scribbled out and redrawn just below $E_c$ ("This was not correct. This should be up here."). Page-final frame f_0172 shows the uncorrected state; f_0175 shows the fix.
2. **p01: office hours.** The board says the usual slot is 10:30–11:55AM; speech says "11:30 to 11:55AM". The board was followed.
3. **0:24:35: unit slip.** "VBI might be maybe point six or point seven eV": $V_{bi}$ ≈ 0.6–0.7 V, i.e. $eV_{bi}$ ≈ 0.6–0.7 eV.
4. **0:24:12: rounding.** $k_BT$ "one fortieth of an electron volt" = 0.025 eV vs 0.02585 eV at 300 K (3.4 % low). Fine as a mnemonic, but it shifts numeric answers (e.g. ×54.6 vs ×47.9 per 0.1 V).
5. **0:09:51 / 0:13:20: sign wording.** "Reduced by ... minus e times that voltage" and "the difference will be minus e times v". The p-side electron PE shifts by $(-e)V$, so the barrier is *reduced by* $eV$ (positive amount) and the $E_F$ split is $eV$. The board ($eV_{bi}-eV$, "eV") is consistent and correct.
6. **0:14:08: carrier-side slip.** "electrons on the p side... Or sorry. On the n side, (are?) holes on the n side". The board shows electrons on n and holes on p.
7. **0:56:43: "frequency of the electron"**, self-corrected to photon.
8. **ASR:** "framing level is z times v" = Fermi level is eV; "k sub b times c" = $k_BT$; "connection main edge" = conduction band edge; "Ulaby Dahl" = Ulaby et al.; "hand ad" = handout.
9. **Frames:** the final board phrase "graphically by Bode plots" is not in any frame (speech only).
