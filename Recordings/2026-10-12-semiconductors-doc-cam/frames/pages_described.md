# 2026-10-12-semiconductors-doc-cam: pages described

Description pass per `DESCRIBE_FRAMES_PROMPT.md`. Source: document camera on paper. Ed Yu's tablet failed that morning, and he said at 0:01:00 that the camera does not capture the full width of the sheet. All 37 page JPEGs plus the 5 earlier states were viewed. For the 9 blurry pages and for pages cut off at an edge, neighbouring frames from `index.txt` were viewed instead; each section names the frame it used. Confidence: `[sure]` means frame and speech agree or the frame is unambiguous, `[likely]` means one source only but legible, `[unclear]` means it could not be read. `(?)` marks unreadable text.

Numbers were re-derived with python3 (`kB=1.381e-23`, `q=1.602e-19`, `T=300`).

(Written into the worktree mirror of `Recordings/2026-10-12-semiconductors-doc-cam/frames/`; a hook blocks writes to the base checkout.)

---

## p01  f_0001.jpg  [0:00:00]
**Topic:** none. The frame is all black (recording start).  [sure]
**Speech:** none.

## p02  f_0036.jpg  [0:00:00 – 0:02:52]  (also viewed f_0028)
**Topic:** "Announcements" (underlined)  [sure]
**Board:**
- "1. Results for Semester Exam 1: mean = 71.3, median = 74.5, std dev = 12.8, range = 40.5–9(?), N = 25."  [sure; the right edge is cut off. Speech gives "40 and a half to 92 and a half", so the range is 40.5–92.5 [likely]]
- "Regrade requests open until 5PM (?) time Friday 10/16/26. Please read announce(?) section on regrade requests carefully."  [sure, except the word cut off at the right edge (?)]
**Speech vs board:** the speech adds that the tablet showed a blue screen ("encryption policies for UT had changed"), so the lecture uses the camera. Grades are curved, so regrades only correct a rubric that was applied wrongly, not the rubric itself. Board and speech agree on the numbers.
**Re-derived:** 2026-10-16 is a Friday (python `datetime`). OK.

## p03  f_0083.jpg  [0:02:52 – 0:04:19]  BLURRY. Used f_0052 (0:03:12), f_0077 (0:03:55) and f_0080 (0:04:01)
**Board:**
- "2. This week's recitation will cover material important (!) for Problem Set 6."  [sure]
- "3. Office hours on Wednesday 10/14/26 will [be] 2:30–4:00 PM instead of 10:30–11:55(?), still in EER 3.802."  [likely; "11:55" is partly cut off]
- "4. I may be late to office hours today a[s I will] probably stop by our IT office to try (?) …"  [likely; the rest is off-frame]
**Speech vs board:** the speech adds that the recitation is "complementary to rather than repeating" class. The ASR wrote "E R 3 Dot 802", which is EER 3.802 on the board.

## p04  f_0086.jpg  [0:04:19 – 0:04:48]  Washed-out white page (exposure). Used f_0099 (0:05:16)
**Topic:** "From last time: Fermi distribution"  [sure]
**Speech:** f(E) "tells us what is the probability that an electronic state, an electronic level at a given energy is occupied by an electron."

## p05  f_0107.jpg  [0:04:48 – 0:07:16]
**Board:**
- $f(E)=\dfrac{1}{e^{(E-E_F)/k_BT}+1}$  [sure. The subscript F reads like "P" at 1280 px; speech: "e to the energy minus what we call the Fermi level over Boltzmann's constant times the temperature plus one"]
- $k_B$ = Boltzmann's constant $=1.381\times10^{-23}$ J/K  [sure. The speech starts "1.38" and then corrects itself to "1.381"]
- $T$ = temperature (K)  [sure]
- $E_F$ = Fermi energy or Fermi level  [sure]
- = energy at which $f(E)=\tfrac12$  [sure]
**Speech vs board:** the speech adds that $k_B$ "allows us to convert temperature into energy." The ASR rendered $k_B$ as "case of b".
**Re-derived:** $f(E_F)=1/(e^0+1)=1/2$. OK.

## p06  f_0116.jpg  [0:07:16 – 0:08:57]
**Board:** the same block as p05, scrolled, with the heading "low T" starting at the bottom.  [sure]
**Speech:** energy goes on the vertical axis. The range of f is 0 to 1. For $E\gg E_F$ there is a large exponential in the denominator, so $f\to0$. For $E\ll E_F$ the exponential is small, so $f\to1$.  [sure]
**Re-derived:** f(E_F+5kT) = 0.0067 and f(E_F−5kT) = 0.9933. Consistent.

## p07  f_0131.jpg  [0:08:57 – 0:11:52]  BLURRY. Used f_0130 (0:11:02)
**Topic:** "low T"  [sure]
**Diagram:** axes with $E$ vertical and $f(E)$ horizontal, ticks "0" and "1". The curve starts near $f=0$ at the top (high $E$), passes through a dot at the tick marked $E_F$ on the E axis, then bends over to $f=1$ at the bottom. A short double arrow across the transition is labelled "few ×k_BT" [likely: "few × k_B T"]. To the right are a horizontal line $E_c$ with a brace "CB" above it and a horizontal line $E_v$ (the VB brace and hatching are added later). The dotted $E_F$ level runs between them, mid-gap.  [sure for the shape and labels]
**Speech:** the transition from 0 to 1 is "just within a few times $k_BT$ of the Fermi level." It widens as T rises. VB states lie far below $E_F$, so they are full; CB states lie far above, so they are empty. He self-corrected "electrons in the valence band… or sorry, holes in the valence band".
**Re-derived:** the 10–90 % width of f is $2\ln 9\,k_BT=4.39\,k_BT$, so "a few $k_BT$" holds. (This number is mine, not on the board.)
**Sketch note:** the dot sits at about $f\approx0.4$ rather than 0.5. This is a hand-sketch inaccuracy; the written definition says $f(E_F)=\tfrac12$.  [unclear: estimated from pixels]

## p08  f_0138.jpg  [0:11:52 – 0:14:19]
**Board:**
- Low-T panel finished: hatching below $E_v$ with a brace "VB". Text: "VB nearly full of electrons / CB nearly empty."  [sure; the text appears completed in f_0145/f_0147]
- "high T" panel: the same axes, but the curve is far more gradual. $E_F$ is dashed at the same height. A long double arrow spanning most of the vertical range is labelled "few ~k_BT" [likely]. Band lines $E_c$ (brace "CB") and $E_v$ are on the right.  [sure for the shape]
**Speech vs board:** speech only: "the Fermi level is near the middle of the band gap, which has to be the case because the concentration of electrons and holes have to be equal to each other" (pure semiconductor). At high T "the slope… will get more shallow."  [likely: not written]

## p09  f_0147.jpg  [0:14:19 – 0:16:48]  (earlier state f_0145)
**Board:** high-T band picture. Filled dots (electrons) sit just above $E_c$ in the CB. Open circles (holes) sit at the top of the hatched VB, just below $E_v$. Text: "electrons in CB / holes (empty states) in VB."  [sure]
**Speech:** a student asks about the gap region; see the note's student questions. Answer: "the Fermi distribution function only tells us what is the probability that a state at a given energy will be occupied by an electron. It does not imply anything about whether there are states at that energy or not."  [sure: speech]

## p10  f_0160.jpg  [0:16:48 – 0:19:12]
**Diagram:** a new sketch at the far right. The vertical axis is unlabelled (energy, aligned with the band picture) and the horizontal axis is labelled "DOS". There are two dashed curves. The upper one starts on the axis at about the $E_c$ level and opens up and to the right (CB density of states). The lower one starts at about the $E_v$ level and curves down and to the right (VB density of states). Nothing is drawn in between, i.e. DOS = 0 in the gap.  [sure for the shape; alignment with $E_c$/$E_v$ is likely]
**Speech (not written):** the DOS is the number of states at an energy, "normalized to the volume… a concentration of states… per unit energy." It is "zero in the band gap," with "fewer states… near the extrema of the bands and then increasing as you move farther into the bands." DOS × f(E) gives electrons per energy, and integrating over the CB gives the electron concentration.  [likely: speech only]
**Speech vs board:** he says "If I had a different color… I would do this in a different color… I'll draw this in a dash line" [0:17:38], which explains why the curves are dashed.

## p11  f_0170.jpg  [0:19:12 – 0:20:20]  BLURRY (page being moved). Used f_0161 (0:20:12)
**Board:** identical to p10. No new ink.  [sure]
**Speech:** the DOS-continuity answer (an infinite crystal gives a continuous DOS; a finite crystal gives a discrete but extremely dense spectrum; treat it as continuous but "not necessarily differentiable", with a cusp at the band edge).

## p12  f_0192.jpg  [0:20:20 – 0:24:00]  Flagged blurry, but readable. Also viewed f_0191
**Board:**
- "At room temperature (300 K):"  [sure]
- $k_BT=(1.381\times10^{-23}\ \text{J/K})(300\ \text{K})$  [sure; a mark at the "×" looks overwritten (?)]
**Speech:** "a number that's of order 10 to the minus 20… maybe four times 10 to the minus 20 or something like that" in joules [0:21:34–0:21:40].
**Re-derived:** $1.381\times10^{-23}\times300=4.143\times10^{-21}$ J. **[speech differs]**: the spoken "four times $10^{-20}$" is 10× too large. The correct value is $4.14\times10^{-21}$ J. The board never shows a joule value.
**Speech (eV motivation):** $e=1.6\times10^{-19}$ C (magnitude). Potential energy = charge × voltage. "A natural unit of energy… the amount of energy that it takes to change the potential of an electron… by one volt."

## p13  f_0216.jpg  [0:24:00 – 0:28:24]  (earlier state f_0209; also viewed f_0199, f_0206, f_0215, f_0222)
**Board:**
- $k_BT=(1.381\times10^{-23}\ \text{J/K})(300\ \text{K})\left(\dfrac{1\ \text{eV}}{1.602\times10^{-19}\ \text{J}}\right)$  [sure]
- $=0.0259\ \text{eV}$  [sure]
- $\Rightarrow k_B=1.381\times10^{-23}\ \text{J/K}=8.617\times10^{-5}\ \text{eV/K}$  [sure]
- eV = "electron volt"  [sure]
- = energy required to increase the potential of an electron charge magnitude ($1.602\times10^{-19}$ C) by 1 volt.  [sure]
- $=1.602\times10^{-19}$ J  [sure; f_0222]
**Speech vs board:** speech says "1.6… Actually, point six zero two times 10 to the minus nineteenth" and "This is roughly one fortieth of an electron volt."
**Re-derived:** $k_BT=0.02586$ eV, so 0.0259 is OK, and $1/k_BT=38.7\ \text{eV}^{-1}$, so "≈1/40" holds. $k_B$ from his rounded constants is $1.381\times10^{-23}/1.602\times10^{-19}=8.620\times10^{-5}$ eV/K. **[board differs]** by 0.04 %: the board's $8.617\times10^{-5}$ is the accepted CODATA value ($1.380649\times10^{-23}/1.602176634\times10^{-19}=8.617\times10^{-5}$), not the quotient of the constants he wrote. Immaterial at 3 s.f.

## p14  f_0251.jpg  [0:28:24 – 0:31:10]  (bottom of the previous sheet: f_0226 0:29:19, f_0227/f_0228 0:30:08)
**Board:**
- "The energy band gap $(E_c-E_v)$ of Si is ~1.1 eV."  [sure; previous sheet]
- (new sheet) "Thus, in a pure, perfect semiconductor, n and p are typically very small unless T is very high."  [sure]
**Speech:** the band gap is "40 times" $k_BT$ at room temperature, so carrier concentrations are "down by a factor of, you know, roughly e to the minus 20 or so." "Compositionally pure and structurally perfect". The eV is "somewhat coincidentally" convenient because band gaps are about 1 eV. The ASR wrote "k sub e times c" for $k_BT$.
**Re-derived:** $E_g/k_BT=1.1/0.02586=42.5$, so "40 times" is OK. With $E_F$ mid-gap, $(E_c-E_F)/k_BT=21.3$ and $f(E_c)\approx e^{-21.3}=5.8\times10^{-10}$, so "roughly $e^{-20}$" is consistent.

## p15  f_0255.jpg  [0:31:10 – 0:33:27]
**Board:** "To increase n or p to levels useful for devices, need to shift the Fermi level closer to either $E_v$ or $E_c$."  [sure]
**Speech:** electrons and holes "are what actually carry current." Moving $E_F$ toward $E_c$ gives many more electrons "but we'll have even fewer holes". "We can get either many more electrons or many more holes, but, at a given temperature, we can't get both."  [sure]

## p16  f_0278.jpg  [0:33:27 – 0:34:29]
**Board:**
- "Shifting the Fermi level – doping" (underlined heading)  [sure]
- "Can we shift $E_F$ to be closer to $E_v$ or $E_c$, so $n\neq p$"  [sure]
**Speech:** doping is "taking some of the atoms in a semiconductor crystal and replacing them with a different element."

## p17  f_0288.jpg  [0:34:29 – 0:36:01]  BLURRY (page moving). Used f_0279 (0:35:43)
**Board:**
- "… so $n\neq p$ ($n\gg p$ or $p\gg n$)?"  [sure]
- "Yes! This can be accomplished by <u>doping</u> – the introduction of impurity atoms into the (?)"  [sure up to "into the". The speech completes it as "into the semiconductor crystal"; the last words are off-frame [likely]]
**Speech:** impurity atoms have "a different number of valence electrons… so that it shifts the balance between the electrons and the holes."

## p18  f_0305.jpg  [0:36:01 – 0:38:58]
**Board:** "Consider a Si crystal. Si has 4 valence electrons. If impurity atoms with 5 valence electrons/atom, e.g., phosphorus (P) or arsenic (As), are introduced in place of some Si atoms, the crystal will have"  [sure]
**Speech:** each Si valence electron forms one bond to a nearest neighbour. With a 5-valence-electron atom, "that extra electron can go into the conduction band."

## p19  f_0317.jpg  [0:38:58 – 0:39:41]
**Board:** "… an excess of electrons, which will occupy conduction-band states ⇒ $E_F$ will be closer to $E_c$ than to $E_v$:"  [sure]

## p20  f_0347.jpg  [0:39:41 – 0:44:23]  (earlier state f_0342)
**Diagram (bond picture):** "As" in a centre circle with four "Si" circles (up, right, down, left). Each bond is an oval holding two dots, one electron from the Si and one from the As. One extra dot sits at the upper right of the As, with an arrow labelled "extra electron".  [sure]
**Diagram (band picture):** a vertical arrow (energy, labelled "E" at the top) and the line $E_c$ with a brace "CB" above it. Filled dots (electrons) sit just above $E_c$. $E_F$ is a dashed line just below $E_c$. The line $E_v$ has hatching below it and a brace "VB".  [sure]
**Diagram (f(E)):** $E$ vertical, $f(E)$ horizontal from 0 to 1. The dashed $E_F$ line is high on the axis, extended to the right and labelled "$E_F$". The curve crosses it at a dot.  [sure]
**Speech:** "this arsenic atom… all its bonding states are already filled… So this extra electron, the only place that it can go, is into the antibonding orbital or, equivalently, the conduction band." Holes are also reduced, because extra electrons "would like to lower their energy so they'll go and fill… the empty states in the valence band." So "the Fermi level has to be up here closer to the conduction band edge."  [sure]

## p21  f_0350.jpg  [0:44:23 – 0:45:36]
**Board:** "Impurity atoms that provide extra electrons are called <u>donors</u>."  [sure]
**Speech:** "We call them donors because they're essentially donating one of their valence electrons to the conduction band."

## p22  f_0357.jpg  [0:45:36 – 0:48:11]  BLURRY (page moving). Used f_0351 (0:47:04) and f_0352 (0:48:00)
**Board:** identical to p21. No new ink.  [sure]
**Speech:** the student Q&A on P vs As and on why not 6 valence electrons (Se); see the note.

## p23  f_0369.jpg  [0:48:11 – 0:50:55]  Top line cut off. First line from f_0365 (0:49:39)
**Board:** "Conversely, if impurity atoms with 3 valence electrons/atom, e.g., boron (B) or aluminum (Al) are introduced, crystal has too few electrons to form all its bonds (occupy VB states) ⇒ extra holes will be present in VB, $E_F$ will be closer to $E_v$ than $E_c$:"  [sure]
**Speech:** the same text. The ASR wrote "purity atoms", "two few"; these are "impurity atoms", "too few".

## p24  f_0401.jpg  [0:50:55 – 0:51:27]
**Diagram:** a partial bond picture with "B" in the centre circle. Si circles above, to the right and below, with two-dot bond ovals. The left Si is being drawn.  [sure]

## p25  f_0435.jpg  [0:51:27 – 0:53:11]
**Diagram (bond picture):** B in the centre with four Si neighbours. The left bond oval holds one dot (from Si) and one open circle. An arrow from the open circle is labelled "missing electron".  [sure]
**Diagram (band picture):** energy arrow "E" and the line $E_c$ with brace "CB" above it (empty). $E_F$ is dashed, just above $E_v$. The line $E_v$ has open circles (holes) just below it. The VB is hatched below, with brace "VB".  [sure]
**Diagram (f(E)):** $E$ vertical, $f(E)$ horizontal from 0 to 1. The dashed Fermi line is low, and the curve crosses it at a dot. The label at the right end of the dashed line reads **"E_E"** (?). Zooming the crop (f_0435/f_0436, x 940–1080) shows a second "E" where the subscript F should be.  **[board differs]** The speech says "This is the Fermi level. This is zero, and this is one" [0:52:52]. It is $E_F$, and the board subscript is a slip or a malformed F.  [likely]
**Speech:** the missing electron "would have gone into a bonding orbital, then that empty state is going to be in the valence band." $E_F$ sits "down close to the valence band because that corresponds to having a higher probability of finding empty states in the valence band."

## p26  f_0436.jpg  [0:53:11 – 0:55:12]
**Board:** identical to p25. No new ink.  [sure]
**Speech:** the student question on whether "the one half mark" (the Fermi level) has physical meaning. The ASR first rendered it as "Does the hole have intrinsic physical value"; the follow-up "Was it the one half mark?" shows the question is about $E_F$ [likely]. Answer: partly a mathematical definition (½ is "the least arbitrary point"), but physically $E_F$ "has to be the same in equilibrium… across that entire structure" (pn junction).

## p27  f_0455.jpg  [0:55:12 – 0:57:27]  BLURRY (page moving). Used f_0449 (0:56:16) and f_0453 (0:57:26)
**Board:**
- "Impurity atoms that remove electrons (provide holes) are called <u>acceptors</u>."  [sure]
- "donors ⇒ n-type semiconductor (n > p)"  [sure]
- "acceptors ⇒ p-type semiconductor (p > n)"  [sure]
**Speech:** hole motion: a neighbouring bonding electron hops into the empty state, then another hops into the newly emptied state; "that's basically how the holes move around in the valence band." No arrows were drawn for this in any frame I checked (f_0437–f_0453).  [likely]

## p28  f_0483.jpg  [0:57:27 – 1:00:19]
**Board:** "The fraction of atoms replaced by impurities is typically very small, e.g., a crystal of Si has ~$5\times10^{22}$ Si atoms/cm³, and typical concentrations of impurities introduced in doping ~~is~~ are ~$10^{15}$–$10^{20}$ atoms/cm³."  [sure; "is" is struck through and replaced by "are"]
**Speech:** "roughly one in 500 or so at the high end to one in, you know, 10 to the seventh or 10 to the eighth at the low end." The ASR transcribed "10 to the (maybe?) fifteenth"; the board's $10^{15}$ is the value followed.
**Re-derived:** $10^{20}/5\times10^{22}=2\times10^{-3}$ (1 in 500), OK. $10^{15}/5\times10^{22}=2\times10^{-8}$ (1 in $5\times10^7$), which lies between the spoken $10^7$ and $10^8$, OK.

## p29  f_0485.jpg  [1:00:19 – 1:02:24]  (earlier state f_0484)
**Board:** identical to p28. No new ink.  [sure]
**Speech:** the student question on the optimum doping level: alloy limit, ionized-impurity scattering. See the note.

## p30  f_0494.jpg  [1:02:24 – 1:04:53]  (also viewed f_0486)
**Board:** p28 scrolled up. No new ink; the mobility/scattering discussion is speech only.  [sure]
**Speech:** ionized donors are positive ions "bonded into the lattice"; Coulomb attraction disrupts electron motion ("scattering"); mobility drops; "decrease in mobility is somewhat smaller than the increase in electron concentration." The ASR writes "connectivity" for **conductivity** throughout.

## p31  f_0515.jpg  [1:04:53 – 1:07:07]  (also viewed f_0516)
**Board:**
- "Semiconductor devices" (underlined heading)  [sure]
- "pn junction diode:" (underlined)  [sure]
- A diode symbol, o—▷|—o (triangle pointing right, bar on the right), then "=", then a rectangle split by a vertical line with "p" on the left and "n" on the right. The boundary is labelled "pn junction" with a small brace. A dashed vertical line drops from the junction through the band sketches below.  [sure]
- Separated band sketches. p side (left of the dashed line): $E_c$ line; $E_F$ dashed just above $E_v$; $E_v$ line with holes "o o o o". n side (right): $E_c$ line at the same height, $E_v$ line at the same height.  [sure]
**Speech:** 302/302H covered MOSFETs; here "the PN junction diode" in more detail. A p-type piece and an n-type piece are put together, and "the boundary region between these is what we call the PN junction."
**Check:** the symbol's triangle side (anode) maps to p and the bar side (cathode) maps to n. Correct.

## p32  f_0523.jpg  [1:07:07 – 1:10:11]  (also viewed f_0517)
**Board:**
- n side completed: dots "• • • •" just above $E_c$; $E_F$ dashed just below $E_c$; labels $E_c$, $E_F$, $E_v$.  [sure]
- Annotation at the upper right, with an arrow down toward the bands and an arrow pointing right: "in equilibrium, $E_F$ must be constant across the entire device ⇒ $I=0$"  [sure]
- At the bottom, the start of a new diagram: a dashed horizontal line labelled $E_F$ and an axis arrow "→ x".  [sure]
**Speech:** bringing the pieces together, electrons diffuse n→p and holes p→n. The final state is the one where "the probability of finding an electron or a hole at a given energy is the same in equilibrium across the entire structure… if it were not the same, then you would get some motion… across the junction." Also "that's required in order for the current to be zero… zero voltage… zero current."

## p33  f_0539.jpg  [1:10:11 – 1:12:20]  (also viewed f_0526)
**Diagram (equilibrium band diagram vs x):** $E_c$ is high and nearly flat on the left (p side). It bends down smoothly through the junction region to a lower flat level on the right (n side), labelled $E_c$, with electrons (dots) just above it. $E_v$ runs parallel to $E_c$ throughout, with holes "o o o o" just below $E_v$ on the left. $E_F$ is a flat dashed line across the whole diagram, just below $E_c$ on the n side and just above $E_v$ on the p side. The left $E_c$ level is extended to the right by a dotted line. A vertical double arrow from the n-side $E_c$ up to that dotted line is labelled "$eV_{bi}$". The axis arrow is "→ x".  [sure]
**Board:** $V_{bi}$ = "built-in" potential  [sure]
**Speech:** "you build up a potential energy difference between the p side and the n side… electronic charge e times a potential we call $V_{bi}$." The ASR also writes this as "v sub b I", "VDI", "b b I".

## p34  f_0555.jpg  [1:12:20 – 1:15:03]  Motion-blurred view of the whole sheet. Used f_0549 (1:13:45) and f_0554 (1:14:24)
**Board:** p31–p33 content. No new ink.  [sure]
**Speech:** origin of $V_{bi}$: ionized dopants (acceptors on p, donors on n) leave charge, the charge creates an electric field, its integral is a potential, and the potential "prevents more diffusion." Student Q: $V_{bi}$ vs breakdown. Answer: $V_{bi}$ relates to the forward-bias turn-on voltage, not breakdown; breakdown is under reverse bias (negative voltage on p).
**Not on the board:** at 1:14:33 he says the I–V "will increase exponentially, so it'll kinda look like this". No I–V curve appears in f_0549–f_0573, so he probably gestured.  [unclear]
**Speech vs physics:** at 1:12:56 the transcript reads "keep this high concentration of holes on the inside and the high concentration of electrons on the p side". **This is reversed.** Holes stay on the p side and electrons on the n side. Either a speech slip or ASR ("inside" ≈ "n side"); I followed the board diagram (holes drawn on p, electrons on n).

## p35  f_0575.jpg  [1:15:03 – 1:16:48]  (earlier state f_0574, 1:16:39)
**Frame:** a black Zoom tile showing a participant's name (Zoom switched to a participant view). No board content.  [sure]
**Board for 1:15:03–1:16:39:** used f_0573 (1:15:48); it shows the same p33 diagram, and he points at the n-side $E_c$ where it meets the bend.  [sure]
**Speech:** forward bias (positive voltage on p) lowers electron potential energy on the p side, so the barrier gets lower. Current becomes noticeable when the barrier is "within maybe a couple tenths of a volt" of cancelling $V_{bi}$. "For a silicon PN junction diode, the turn on… very roughly is maybe around point six volts or so." **The transcript ends at 1:16:02 mid-sentence ("And it is that").**

## p36  f_0588.jpg  [1:16:48 – 1:18:20]  NO SPEECH. Viewed f_0576 (1:17:01), f_0581 (1:17:47), f_0588 (1:18:20)
**Board:** the p33 diagram, unchanged. He points at the p-side $E_c$ (f_0581) and at the bend in $E_v$ (f_0588), evidently explaining it, but there is no audio transcript.  [sure for the board; content of the explanation unknown (?)]

## p37  f_0593.jpg  [1:18:20 – 1:19:12]  NO SPEECH. Viewed f_0592 (1:18:46) and f_0593 (1:19:12)
**Board (below "V_bi = built-in potential"):**
- "$E_c(x)$ functions as the potential energy for electrons"  [sure]
- "$E_v(x)$ functions as the potential energy for hol[es]"  [likely; still being written in the last frame]
**Audio gap:** the recording runs to about 1:19:43 (79.7 min of audio per Deepgram), but no speech was transcribed after 1:16:02. About 3 min 40 s of lecture has only the board.

---

## Summary of discrepancies

| t | Source | Issue | Followed |
|---|---|---|---|
| 0:21:40 | speech | "maybe four times $10^{-20}$" J for $k_BT$ at 300 K. Correct: $4.14\times10^{-21}$ J | python value |
| 0:26:37 | board | $k_B=8.617\times10^{-5}$ eV/K, while $1.381\times10^{-23}/1.602\times10^{-19}=8.620\times10^{-5}$ (board uses the CODATA value) | board (correct to 3 s.f. either way) |
| 0:52:52 | board | Fermi level on the p-type f(E) plot labelled "E_E" (?) | speech: $E_F$ |
| 1:12:56 | speech/ASR | "holes on the inside… electrons on the p side" (reversed) | board diagram: holes on p, electrons on n |
| 0:09–0:14 | board sketch | f(E) curves cross $E_F$ at f ≈ 0.4, not 0.5 (hand sketch) | definition $f(E_F)=1/2$ |
| 1:16:02–1:19:43 | audio | no transcript, but the board keeps changing | board only |
| various | ASR | "case of b" = $k_B$; "f of v" = f(E); "k sub e times c" = $k_BT$; "connectivity" = conductivity; "Ohlins band" = valence band; "dope and type" = dopant type; "purity atoms" = impurity atoms; "two few" = too few; "fill the whole state" = hole state; "VDI", "b b I" = $V_{bi}$; "when the die breaks" = diode breakdown; "reply reverse bias" = apply reverse bias; "connection and valence bands" = conduction and valence bands; "E R 3 Dot 802" = EER 3.802 | n/a |
