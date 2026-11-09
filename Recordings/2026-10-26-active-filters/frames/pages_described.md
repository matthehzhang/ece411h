# 2026-10-26: page descriptions (frame + speech cross-check)

Produced per `DESCRIBE_FRAMES_PROMPT.md`. Inputs: `QUALITY.md`, `pages_with_speech.md`, all 33 page-final JPEGs, the neighbouring frames named per page, `transcript.paragraphs.md`, `transcript.txt` (all 1121 utterances, including the 8 after 1:20:01 that `pages_with_speech.md` omits). Frame files live in the base checkout at `~/uni/ece411/Recordings/2026-10-26-active-filters/frames/`.

> [!warning] Folder name is wrong about the content
> The folder is called `2026-10-26-active-filters`, but **this lecture has no op-amp or active-filter content at all.** It covers the series-RLC **bandpass** (cutoffs, bandwidth, quality factor $Q$, Bode plots by factors) and starts the series-RLC **highpass** (output across $L$). The board on f_0002 reads "Class session notes - 2026_10_2(?)" (truncated) and then "From last time - band pass RLC filter". The lecture ends at 1:20:43 with "We'll pick up with this on Wednesday", so the highpass Bode plots and, presumably, active filters come on Wed 10/28 or later.

Global caveats (from QUALITY.md): tablet handwriting, 1280 px frames; the phasor under-tilde is legible throughout. One blurry frame (f_0019, 0:06:33) is an early state of p04 and was superseded by f_0040. Pages p12–p26 are mostly **scroll-backs** (the lecturer scrolling up and down to compare), not new ink.

Confidence tags: `[sure]` frame and speech agree or the frame is unambiguous; `[likely]` one source only but legible; `[unclear]` could not be read.

---

## p01  f_0010.jpg  [0:00:00 – 0:02:05]  (also used f_0002.jpg, 0:00:02)
**Topic:** typed "Announcements:" block, then handwritten "From last time - band pass RLC filter" (f_0002) [sure]
**Board (typed, f_0002):**
- "1. Reminder - Problem Set 7 is due 9:00AM Central time on Monday 11/02/2026." [sure]
- "2. Problem Set 8 will be posted this Wednesday, and will be due on Monday 11/9/2026. Problem Set 8 will cover primarily passive and active filter circuits." [sure]
- "3. Reminder - Semester Exam 2 will be in class on Wednesday 11/11/2026. A detailed announcement on the exam will be posted later this week." [sure]
**Board (handwritten):**
- $\underset{\sim}{H}(\omega)=\dfrac{j\omega RC}{1-\omega^2LC+j\omega RC}=\dfrac{\omega^2R^2C^2+j\omega RC(1-\omega^2LC)}{(1-\omega^2LC)^2+\omega^2R^2C^2}$ [sure]
**Diagram:** source $\tilde V_s$ on the left edge (+ on top). The top wire runs from the source through an open terminal circle, then inductor $L$, then capacitor $C$, to a node. From that node resistor $R$ goes down to the bottom wire, and a wire continues right to the + output terminal. The bottom wire returns to the source through an open terminal circle and goes to the − output terminal. Output $\tilde V_R$ is across $R$, + on top. So it is a series L–C–R loop with the output across $R$. [sure]
**Speech vs board:** speech [0:01:20–0:01:54] "this bandpass RLC filter... v sub s is the input voltage, v sub r is the output voltage... the transfer function... can be quite easily calculated using just voltage division". Agrees. [sure]
**Re-derived:** $R/(R+j\omega L+1/(j\omega C))$ equals both board forms (python, 2000 random R, L, C, $\omega$; max error $4\times10^{-15}$). The rationalized form matches to $2\times10^{-16}$. **No board error.**

## p02  f_0014.jpg  [0:02:05 – 0:05:13]
**Topic:** magnitude and phase of the bandpass $H$ (no title) [sure]
**Board:**
- $M(\omega)=|\underset{\sim}{H}(\omega)|=\dfrac{\omega RC}{\sqrt{(1-\omega^2LC)^2+\omega^2R^2C^2}}$ [sure]
- $\phi(\omega)=\tan^{-1}\!\left(\dfrac{1-\omega^2LC}{\omega RC}\right)$ [sure]
**Speech vs board:** for the magnitude he uses the first form, |numerator| over |denominator| [0:02:23]. For the phase he uses the *rationalized* form, whose denominator is real, so the phase is $\tan^{-1}(\text{Im}/\text{Re})$, and "one factor of omega r c will cancel out" [0:03:52–0:04:29]. At [0:04:42] he says that computing the phase as "phase of the numerator minus the phase of the denominator... would actually be a little bit trickier", and that "later on today we'll see an example" (the highpass quadrant issue at 1:06). Agrees with the board. [sure]
**Re-derived:** the board $\phi$ equals the true $\angle H$ for every $\omega$ (max error $1.4\times10^{-14}$ deg). This works because the real part of the rationalized numerator, $\omega^2R^2C^2$, is always $>0$, so $\tan^{-1}$ never lands in the wrong quadrant. The naive route $90^\circ-\tan^{-1}\!\big(\omega RC/(1-\omega^2LC)\big)$ gives $154.62^\circ$ instead of the true $-25.38^\circ$ at $\omega=2\omega_0$ (my test values). That is the "trickier" part he alludes to.

## p03  f_0018.jpg  [0:05:13 – 0:06:31]
**Topic:** same page as p01/p02, scrolled to show the circuit and the formulas together [sure]
**Board:** identical to p01 + p02 (circuit, $H$, $M$, $\phi$). He erased a box ("Let me get rid of that box there" [0:05:20]) [likely].
**Speech:** resonant frequency recap: "the frequency at which the input impedance... the Thevenin equivalent impedance between the input terminals... if the imaginary parts all canceled out... purely real" [0:05:29–0:06:05]. $\omega L=1/(\omega C)$ at resonance. [sure]

## p04  f_0040.jpg  [0:06:31 – 0:13:40]  (earlier states f_0019 (blurry) … f_0039; f_0300 and f_0421 show the same sketch fully)
**Topic:** "resonant frequency" plus limit sketches [sure]
**Board:**
- $\phi(\omega)=\tan^{-1}\!\left(\dfrac{1-\omega^2LC}{\omega RC}\right)$ (repeated from p02) [sure]
- "resonant frequency" $\boxed{\omega_0=\dfrac{1}{\sqrt{LC}}}$ [sure]
- "since $\omega_0L=\dfrac{1}{\omega_0C}\Rightarrow\underset{\sim}{Z}_L$ and $\underset{\sim}{Z}_C$ cancel out for $\omega=\omega_0$." [sure]
**Diagram 1 (left), $M(\omega)$ vs $\omega$, linear axes:** green bell curve. It starts at 0 at $\omega=0$, peaks at 1 at $\omega_0$ (green dot), and decays toward 0. The horizontal dashed line at 1 and the dashed line at $1/\sqrt2$ cross the curve at $\omega_{c1}$ (left) and $\omega_{c2}$ (right). Vertical dashed drops go to the axis ticks $\omega_{c1},\omega_0,\omega_{c2}$. A double arrow between the drops is labelled $B$. [sure]
**Diagram 2 (right), $\phi(\omega)$ vs $\omega$:** dashed asymptotes at $+90^\circ$ and $-90^\circ$. The green curve starts at $90^\circ$, falls through $0$ at $\omega_0$ (green dot) and approaches $-90^\circ$. [sure]
**Speech vs board:** Q&A with the class [0:07:45–0:11:13]: $\omega\to0$: $M\to0$ "because of the omega in the numerator"; $\omega\to\infty$: $M\to0$; $M(\omega_0)=1$ because "this term in the denominator goes to zero... that square root is just omega RC... we have one". Phase: $\omega\to0$: $\tan^{-1}(\infty)=90^\circ$; $\omega\to\infty$: $-90^\circ$; $\omega_0$: $0$. "clearly is a bandpass filter" [0:12:07]. Cutoffs at $M=1/\sqrt2$, called $\omega_{c1},\omega_{c2}$; "the difference between them is the bandwidth b" [0:12:41]. All agree with the board. [sure]
**Re-derived:** $|H(\omega_0)|=1$ exactly; $\angle H(\omega_0)=0$. **No board error.**

## p05  f_0089.jpg  [0:13:40 – 0:23:10]  (used f_0049, f_0066, f_0084, f_0304 for the upper part of the page)
**Topic:** cutoff frequencies and bandwidth of the series-RLC bandpass [sure]
> [!warning] = PS8 9.26 (likely): graded work; the tutor must not use this as a walkthrough or check
> This is the general symbolic derivation for the series-RLC bandpass. PS8 9.26 ("series RLC bandpass parameters") almost certainly uses exactly these results.

**Board (in reading order):**
- $M(\omega_{c1})=M(\omega_{c2})=1/\sqrt2\;\Rightarrow\;\dfrac{\omega_{ci}RC}{\sqrt{(1-\omega_{ci}^2LC)^2+\omega_{ci}^2R^2C^2}}=\dfrac{1}{\sqrt2}$ [sure]
- $\Rightarrow\dfrac{1}{\sqrt{\left(\dfrac{1-\omega_{ci}^2LC}{\omega_{ci}RC}\right)^2+1}}=\dfrac1{\sqrt2}\;\Rightarrow\;1-\omega_{ci}^2LC=\pm\,\omega_{ci}RC$ [sure]
- $\Rightarrow LC\,\omega_{ci}^2\pm RC\,\omega_{ci}-1=0$ [sure]
- $\omega_{ci}=\dfrac{1}{2LC}\left[\mp RC\pm\sqrt{(RC)^2+4LC}\right]=\mp\dfrac{R}{2L}\pm\sqrt{\left(\dfrac{R}{2L}\right)^2+\dfrac1{LC}}$ [sure]
- "Select solutions for which $\omega_{ci}>0$ with $\omega_{c1}<\omega_{c2}$." [sure]
- $\omega_{c1}=\sqrt{\left(\dfrac{R}{2L}\right)^2+\dfrac1{LC}}-\dfrac{R}{2L},\qquad \omega_{c2}=\sqrt{\left(\dfrac{R}{2L}\right)^2+\dfrac1{LC}}+\dfrac{R}{2L}$ [sure]
- $B=\omega_{c2}-\omega_{c1}=\dfrac{R}{L}$ [sure]
**Speech vs board:** method [0:14:19]: divide the numerator and denominator by $\omega_{ci}RC$, so the second term under the root becomes 1 and the first term must equal 1. Then "there are actually four possible solutions... two options for the sign here and two options for the sign here... independent" [0:18:43]. Keep the two positive ones: "taking the plus sign [on the root]... and then this can be either the minus or the plus" [0:19:21]. The ASR at [0:17:56] reads "plus (or?) l c"; the board has $+4LC$, so I followed the board. [sure] Bandwidth: "the square root term will cancel out... R over L" [0:21:13]. Small R gives a narrow, selective band; large R gives a wide band. Only R dissipates power [0:21:41–0:22:36].
**Re-derived (python):** $|H(\omega_{c1})|=|H(\omega_{c2})|=1/\sqrt2$ to $10^{-8}$; $B=R/L$ to $10^{-13}$; the quadratic-formula step $\sqrt{(RC)^2+4LC}/(2LC)=\sqrt{(R/2L)^2+1/LC}$ checked symbolically (sympy). *Mine:* $\omega_{c1}\omega_{c2}=\omega_0^2$ (geometric centre), and $\angle H=\pm45^\circ$ at $\omega_{c1},\omega_{c2}$. **No board error.**

## p06  f_0094.jpg  [0:23:10 – 0:24:48]
**Topic:** "quality factor, Q:" (underlined) [sure]
**Board:**
- $B=\omega_{c2}-\omega_{c1}=R/L$ (top, partly cut) [sure]
- "quality factor, Q: Q quantifies the degree of frequency selectivity of a circuit and is related to the ratio of stored to dissipated energy:" [sure]
**Speech:** Q "applies actually to any resonant circuit... and particularly to the resonant part of the circuit" [0:23:24]. Energy is stored in L and C and dissipated in R [0:24:31]. Agrees. [sure]

## p07  f_0134.jpg  [0:24:48 – 0:33:41]  (Q definition read from f_0116 / f_0285)
**Topic:** definition of Q and the series-RLC result [sure]
**Board:**
- $Q=2\pi\left(\dfrac{W_{stor}}{W_{diss}}\right)\Bigg|_{\omega=\omega_0}$ [sure]
- "$W_{stor}$ = maximum energy stored for $\omega=\omega_0$" [sure]
- "$W_{diss}$ = energy dissipated during one period $T=\dfrac{2\pi}{\omega_0}$." [sure]
- "One can show (Ulaby et al, Sec. 9-4-1) for the RLC series circuit that" $\boxed{Q=\omega_0\dfrac{L}{R}=\dfrac{\omega_0}{B}}$ [sure]
- "high quality factor Q $\Longleftrightarrow$ narrow bandwidth B in general." [sure]
**Speech vs board:** "I won't go through the detailed derivation of this, but it's in the book" [0:31:22]. The ASR "You'll be at all... nine dash four dash one" = Ulaby et al. §9-4-1 (board) [sure]. "The key... part of this relationship is the quality factor being inversely proportional to the bandwidth... very generally true of resonant systems" [0:32:47]. Two student questions here: [0:26:39] stored energy at resonance and [0:28:32] resonance without both L and C (see the vault note).
**Re-derived:** $\omega_0L/R=\omega_0/(R/L)$ is an identity; $=\frac1R\sqrt{L/C}$ checked (python). **No board error.**

## p08  f_0138.jpg  [0:33:41 – 0:33:42]
**Topic:** scroll state of p07 (boxed $Q$ and "high quality factor Q ⟺ narrow bandwidth B in general") [sure]. No new ink. Speech [0:33:44–0:34:11]: communications applications use high-Q (low-loss) resonators to pick out a band.

## p09  f_0164.jpg  [0:33:42 – 0:41:05]  (used f_0145, f_0156, f_0159)
**Topic:** "Bode plots for bandpass filter:" [sure]
> [!warning] = PS8 9.26 (likely): graded work; the tutor must not use this as a walkthrough or check (the Bode factorization of this exact bandpass)

**Board:**
- $\underset{\sim}{H}(\omega)=\dfrac{j\omega RC}{1-\omega^2LC+j\omega RC}=\underbrace{(RC)}_{\underset{\sim}{A}_1}\underbrace{(j\omega)}_{\underset{\sim}{A}_2}\underbrace{\left(\dfrac{1}{1+j\omega RC-\omega^2LC}\right)}_{\underset{\sim}{A}_3}$ [sure]
- Blue annotation: an arrow from the $-\omega^2LC$ term to $\left(\dfrac{j\omega}{\omega_p}\right)^2$ [sure]
- "$\Rightarrow\underset{\sim}{H}(\omega)$ has a zero @ origin and a quadratic pole at $\omega_p=\dfrac{1}{\sqrt{LC}}=\omega_0$." [sure]
- "To obtain the Bode plot for $\underset{\sim}{H}(\omega)$, construct plots for $\underset{\sim}{A}_i(\omega)$ and combine by adding. This works because $M(\omega)$ is plotted on a log scale, and $\phi(\omega)$ appears in an exponent." [sure]
- $\underset{\sim}{A}_1(\omega)$: $M(\omega)$[dB] vs $\omega$ is a green horizontal line drawn **below** the $\omega$-axis (0 dB, unlabelled). $\phi(\omega)$ is a green line on the $0^\circ$ axis. [sure]
**Speech vs board:** "it has to be of the form j omega over omega p squared... the pole frequency is one over root LC, which is equal to the resonant frequency" [0:36:41–0:37:08]. On $A_1$ he says RC is "generally... less than one", e.g. 1 kΩ × 1 µF, so he draws it below 0 dB [0:39:50–0:40:31]. Its phase is 0 because RC > 0. [sure]
**Re-derived:** $1\,\text{k}\Omega\times1\,\mu\text{F}=10^{-3}$ s → $20\log_{10}(10^{-3})=-60$ dB (python). He drew no number.

## p10  f_0225.jpg  [0:41:05 – 0:48:46]
**Topic:** Bode plots of $A_2$ and the start of $A_3$ [sure]
**Board:**
- $\underset{\sim}{A}_2(\omega)$: $M$[dB] is a green straight line crossing the $\omega$-axis ("0dB") at a tick labelled "1", annotated "← 20dB/decade". $\phi(\omega)$ is a green horizontal line at $90^\circ$. [sure]
**Speech vs board:** a zero at the origin has "no inherent frequency scale", and at $\omega=1$ the log is 0, hence 0 dB [0:41:26–0:41:50]. Phase $=\angle j=90^\circ$. Student question [0:42:41] on the vertical axis (see note). He then sets up $A_3$: $\omega\to0$ gives $A_3\to1$ = 0 dB; $\omega\to\infty$ gives $A_3\sim1/(-\omega^2LC)$, which falls by 100× per decade = $-40$ dB/decade [0:45:32–0:46:19]. **Speech slip** [0:46:52]: "for the quadratic **zero**", but it is the quadratic **pole** (board and context). Phase: 0 at low $\omega$; at $\omega_0$, $A_3=1/(j\omega_0RC)$ so $-90^\circ$; at high $\omega$, $\angle(-1)$ "we can take to be minus 180 degrees" [0:47:44–0:48:44]. [sure]

## p11  f_0263.jpg  [0:48:46 – 0:51:26]  (f_0262 shows the full $A_3$ row)
**Topic:** Bode plot of $A_3$ (quadratic pole) [sure]
**Board:**
- $\underset{\sim}{A}_3(\omega)$: $M$[dB] is green, flat along the 0 dB axis up to the tick $\omega_0$, then a straight line down labelled "← −40dB/decade". [sure]
- $\phi(\omega)$: axis ticks $0.1\omega_0$, $\omega_0$, $10\omega_0$; levels $0^\circ$, $-90^\circ$, $-180^\circ$ (dashed). The green line is flat at $0^\circ$ to $0.1\omega_0$, a straight line through $-90^\circ$ (dot) at $\omega_0$ down to $-180^\circ$ at $10\omega_0$, then flat at $-180^\circ$. [sure]
**Speech vs board:** **Speech slip** [0:49:16]: "it's **90** degrees at omega naught". The board dot is at $-90^\circ$, and he said "minus 90 degrees" at [0:48:22]. Followed the board. [sure]
**Re-derived:** $\angle A_3(\omega_0)=-90^\circ$ exactly (python). Straight-line convention: $-90^\circ$/decade over two decades.

## p12  f_0265.jpg  [0:51:26]
Scroll state showing the $A_1$ and $A_2$ rows again (same ink as p10). Speech "at omega naught..." [0:51:25] begins the scroll back to p04. [sure]

## p13  f_0285.jpg  [0:51:26 – 0:51:31]
Scroll-back through p06/p07: $B=R/L$, the "quality factor, Q" definition and $Q=2\pi(W_{stor}/W_{diss})|_{\omega_0}$ with the $W_{stor}$/$W_{diss}$ definitions. No new ink. [sure]

## p14  f_0292.jpg  [0:51:31 – 0:51:32]
Scroll-back through the p05 cutoff derivation. No new ink, no speech. [sure]

## p15  f_0304.jpg  [0:51:32 – 0:51:43]  (speech belongs to f_0300, 0:51:34)
Scroll-back. The speech "way back here at omega naught, the magnitude of the transfer function is one... zero dB" [0:51:33–0:51:40] refers to the **p04 sketch**, which is on screen in f_0300 (0:51:34), not to f_0304 (top of the p05 derivation). I used f_0300. [sure]

## p16  f_0320.jpg  [0:51:43 – 0:51:46]
Scroll down through p07 ($Q$ definition tail, boxed $Q=\omega_0L/R=\omega_0/B$). No new ink. [sure]

## p17  f_0333.jpg  [0:51:46 – 0:51:48]
Scroll through p09 ("To obtain the Bode plot…", $A_1$ row). No new ink. [sure]

## p18  f_0335.jpg  [0:51:48 – 0:51:49]
Scroll through the p09/p10 $A_1$, $A_2$ rows. No new ink, no speech. [sure]

## p19  f_0336.jpg  [0:51:49 – 0:51:50]
Scroll to the $A_2$ and $A_3$ rows. Below them is a large hand-drawn **downward double arrow** (combine), and the start of the "$\underset{\sim}{H}(\omega)$:" row. No speech. [sure]

## p20  f_0360.jpg  [0:51:50 – 0:52:50]
**Topic:** combined Bode magnitude, below $\omega_0$ [sure]
**Board:** "$\underset{\sim}{H}(\omega)$:" $M(\omega)$[dB] axes. The horizontal axis is labelled "0dB" with tick $\omega_0$. The green line rises to the point ($\omega_0$, 0 dB), annotated "↑ +20dB/decade". [sure]
**Speech:** "if we call this line here zero dB, then what we get for omega less than omega naught is just a line... slope of plus 20 dB per decade" [0:51:52]. Above $\omega_0$: $0+20-40=-20$ dB/decade, "again, we just add the slopes" [0:52:18–0:52:50]. [sure]
**Re-derived / flagged:** the slopes are right. **Vertex level [board differs] from a literal sum of the factor asymptotes.** Adding $A_1+A_2+A_3$ as drawn gives a vertex at $20\log_{10}(\omega_0RC)$. Since $\omega_0RC=R\sqrt{C/L}=1/Q$ (sympy), that is $-20\log_{10}Q$ dB, which is 0 dB only when $Q=1$. He placed the vertex at 0 dB by borrowing the exact value $|H(\omega_0)|=1$ from p04 (his answer to the student at 0:53:58 confirms this "shortcut"). For $Q=10$ the asymptote vertex is −20 dB while the true curve is 0 dB at $\omega_0$ (python). See the warning in the vault note.

## p21  f_0402.jpg  [0:52:50 – 0:56:43]  (full $H$ row visible in f_0466; build-up in f_0384, f_0400)
**Topic:** completed Bode plots of $H$ [sure]
**Board:**
- $M(\omega)$[dB]: a triangle peaking at ($\omega_0$, 0 dB), "↑ +20dB/decade" on the left and "← −20dB/decade" on the right. [sure]
- $\phi(\omega)$: levels $90^\circ$, $0^\circ$, $-90^\circ$ (dashed). Ticks $0.1\omega_0$, $\omega_0$, then the third tick **first labelled "$\omega_0$"** (f_0384, 0:55:54) and later corrected to "**$10\,\omega_0$**" (f_0466). The green line is flat at $90^\circ$ to $0.1\omega_0$, a straight line through $0^\circ$ at $\omega_0$ to $-90^\circ$ at $10\omega_0$, then flat. [sure]
**Speech vs board:** phase sums [0:55:23–0:55:53]: below $0.1\omega_0$, $0+90+0=90^\circ$; above $10\omega_0$, $0+90-180=-90^\circ$; at $\omega_0$, $0+90-90=0$. He said "point one omega naught, omega naught, and omega naught" [0:55:07]. **Board error, acknowledged:** the third label should be $10\omega_0$; a student pointed it out at [0:57:24] and he fixed it ("You're right. Thank you. It should be 10 omega naught", 0:57:40). [sure]
**Re-derived:** true $\angle H(\omega_0)=0$, and $\pm45^\circ$ at the cutoffs. The straight-line phase is consistent.

## p22  f_0403.jpg  [0:56:43 – 0:56:48]
Scroll-back through p09 (zero at origin, quadratic pole at $\omega_p=1/\sqrt{LC}=\omega_0$; "To obtain the Bode plot…"). Speech: "go back and compare to what we had sketched out earlier". No new ink. [sure]

## p23  f_0410.jpg  [0:56:48 – 0:56:51]
Scroll-back through p05/p06 ($\omega_{c1},\omega_{c2}$, $B=R/L$, Q definition). No new ink. [sure]

## p24  f_0427.jpg  [0:56:51 – 0:57:19]  (target sketch in f_0421, 0:56:58)
Scroll-back. The speech "right back here... these are very consistent with what we got for the Bode plots... the Bode plots kind of make linear approximations to the different ranges of behavior" [0:56:52–0:57:17] refers to the p04 sketches, which are on screen in **f_0421**. f_0427 is mid-scroll (p05 derivation). He also says "this is the disadvantage of working on a tablet rather than on the board" (no side-by-side view). [sure]

## p25  f_0437.jpg  [0:57:19 – 0:57:24]
Scroll through p07–p09 (boxed $Q$, "Bode plots for bandpass filter", the start of the factorization). Student: "it should be 10 omega naught on the bottom there" [0:57:24]. [sure]

## p26  f_0448.jpg  [0:57:24 – 0:57:30]
Scroll through the p09/p10 factor plots ($A_1$, $A_2$). "Did I not write it that way? Let me see here." [sure]

## p27  f_0466.jpg  [0:57:30 – 0:58:50]
**Topic:** final $H$ Bode plots with the corrected $10\,\omega_0$ label (as described in p21). [sure]
**Speech:** correction accepted [0:57:40]. Student question [0:57:58]: is it a coincidence that $\omega_0=$ the pole frequency? "No... that pole is what gives you the peak... it ends up being a quadratic pole because it's second order... you have the RLC" [0:58:10–0:58:39]. [sure]

## p28  f_0472.jpg  [0:58:50 – 1:02:24]  (title and circuit from f_0467, 1:00:00)
**Topic:** "Example: high-pass filter" (underlined "Example") [sure]
**Diagram (f_0467):** $\tilde V_s$ on the left edge (+ top). The top wire runs through an open circle, then resistor $R$, then capacitor $C$, to a node. Inductor $L$ goes from that node down to the bottom wire, and the top wire continues to the + output terminal. Output $\tilde V_L$ is across $L$ (+ top / − bottom). Open circle on the bottom wire. So it is the same series loop with **R and L swapped** relative to p01. [sure]
**Board:**
- "$\underset{\sim}{Z}_L=j\omega L\to0$ as $\omega\to0$, and $\underset{\sim}{Z}_L\to\infty$ as $\omega\to\infty$, so this circuit should make sense intuitively as a high-pass filter." [sure]
- "Circuit has a resonant frequency $\omega_0=\dfrac1{\sqrt{LC}}$" [sure]
- "since $\omega_0L=\dfrac{1}{\omega_0C}\Rightarrow\underset{\sim}{Z}_L+\underset{\sim}{Z}_C$ cancel out at $\omega=\omega_0$" (completed in f_0473) [sure]
**Speech:** "We will have time to start this but not to finish it, today" [0:58:51]. "instead of taking the output voltage to be the voltage across the resistor, we take it to be the voltage across the inductor... we've exchanged the resistor and the inductor" [0:59:34–0:59:50]. The reasoning is voltage division at the limits. Agrees. [sure]

## p29  f_0473.jpg  [1:02:24 – 1:02:46]
Same page as p28 scrolled down; the resonance line is completed ("cancel out at $\omega=\omega_0$"). [sure]

## p30  f_0478.jpg  [1:02:46 – 1:03:58]
**Topic:** "By voltage division:" [sure]
**Board:**
- $\underset{\sim}{V}_L=\dfrac{\underset{\sim}{Z}_L}{\underset{\sim}{Z}_R+\underset{\sim}{Z}_C+\underset{\sim}{Z}_L}\underset{\sim}{V}_s=\dfrac{j\omega L}{R+\frac{1}{j\omega C}+j\omega L}\underset{\sim}{V}_s$ [sure]
**Speech:** "the total series resistance" and "the resistance of the inductor is j omega L" [1:03:14–1:03:25] are slips for *impedance*; the board is correct. [sure]

## p31  f_0482.jpg  [1:03:58 – 1:05:14]
**Topic:** HP transfer function [sure]
**Board:**
- $\Rightarrow\underset{\sim}{H}(\omega)=\dfrac{\underset{\sim}{V}_L}{\underset{\sim}{V}_s}=\dfrac{j\omega L}{R+\frac1{j\omega C}+j\omega L}\left(\dfrac{j\omega C}{j\omega C}\right)=\dfrac{-\omega^2LC}{1-\omega^2LC+j\omega RC}$ (the $j\omega C/j\omega C$ factor is in green) [sure]
**Speech:** multiply by $j\omega C/j\omega C$ "to get rid of this fraction that we have in the denominator" [1:04:26]. The denominator is the same as the bandpass. Agrees. [sure]
**Re-derived:** matches the voltage divider to $4\times10^{-13}$ (python). **No board error.**

## p32  f_0560.jpg  [1:05:14 – 1:18:45]  (full page states f_0492, f_0527, f_0533, f_0564)
**Topic:** HP magnitude, phase (quadrant correction), $Q$, magnitude sketch vs $Q$ [sure]
**Board (reading order):**
- $M(\omega)=|\underset{\sim}{H}(\omega)|=\dfrac{\omega^2LC}{\sqrt{(1-\omega^2LC)^2+\omega^2R^2C^2}}$ [sure]
- Complex-plane sketch: axes Im (up) and Re (right). "$\phi_{denom}$, $\omega<\omega_0$" is written in the **first** quadrant and "$\phi_{denom}$, $\omega>\omega_0$" in the **second** quadrant. [sure]
- $\phi(\omega)=\begin{cases}180^\circ-\tan^{-1}\!\left(\dfrac{\omega RC}{1-\omega^2LC}\right) & \text{for }\omega<\omega_0\\[4pt] -\tan^{-1}\!\left(\dfrac{\omega RC}{1-\omega^2LC}\right) & \text{for }\omega>\omega_0\end{cases}$ [sure]
- "quality factor $Q=\omega_0\dfrac{L}{R}=\dfrac1R\sqrt{\dfrac{L}{C}}$" [sure]
- $\Rightarrow M(\omega_0)=\omega_0\dfrac{L}{R}=Q$ [sure]
- Sketch: vertical axis labelled "$M(\omega)$[dB]" with ticks "1" and "0" (see the error below), horizontal axis $\omega$ with tick $\omega_0$ and a dashed vertical at $\omega_0$ and a dashed horizontal at 1. Three curves all start at 0 at $\omega=0$ and approach 1 at high $\omega$:
  - red "low $Q<1$": rises monotonically, passes below 1 at $\omega_0$ (red dot), approaches 1 from below; [sure]
  - green "moderate $Q>1$": rises steeply, with a modest peak just above 1 near $\omega_0$ (green dot), then settles to 1; [sure]
  - blue "high $Q\gg1$": a sharp tall peak at about $\omega_0$, then decays to 1. [sure]
**Speech vs board:** the numerator phase is $180^\circ$ ("we have the minus one here") [1:06:59]. For $\omega<\omega_0$ the denominator is in the 1st quadrant and the calculator value is right. For $\omega>\omega_0$ the real part is negative, so the denominator is in the 2nd quadrant, "but if you... use your calculator... it'll give you... an angle in the fourth quadrant... add a 180 degrees", and the two $180^\circ$s cancel [1:09:09–1:10:44]. "since the inverse tangent is typically defined as a function that has a range of minus 90 degrees to plus 90 degrees..." [1:11:17]. At $\omega_0$ the magnitude equals $\omega_0L/R=Q$ [1:12:43–1:13:44]. A large R gives $Q<1$; a small R gives $Q>1$; a very small R gives a "sharp and quite high peak" [1:15:48–1:17:55].
**Board error, acknowledged verbally:** the axis says "$M(\omega)$[dB]" and at [1:13:52] he said "we're plotting the magnitude... in dB", but the ticks are linear (0 and 1, curves starting at 0). At [1:19:56] he said "Oh, sorry. This is not decibels. This is just..." The "[dB]" label is **still on the board** in the last frame f_0567. Read the plot as **linear** $M$. [sure]
**Re-derived (python):** the piecewise $\phi$ matches $\angle H$ for all $\omega$ (max error $3\times10^{-14}$ deg); $|H(\omega_0)|=Q$ exactly; the limits are 0 and 1. *Mine:* the HP peak is at $\omega/\omega_0=1/\sqrt{1-1/(2Q^2)}>1$ with value $Q/\sqrt{1-1/(4Q^2)}$, and it exists only for $Q>1/\sqrt2$. For $Q=0.8$ or $0.9$ ("low $Q<1$" by his label) the curve overshoots 1 (peaks 1.025, 1.082). So the monotone red curve is right only for $Q\le1/\sqrt2\approx0.707$ **[board differs, minor]**. For $Q=10$ the peak is at $1.0025\,\omega_0$ with value $10.01$, so "peak at $\omega_0$" is a good approximation for high Q.

## p33  f_0567.jpg  [1:18:45 – 1:20:48]
**Topic:** HP phase sketch [sure]
**Board:** "$\Rightarrow M(\omega_0)=\omega_0\frac{L}{R}=Q$", the same three-curve magnitude sketch, and below it $\phi(\omega)$ with levels $180^\circ$, $90^\circ$, $0^\circ$. The green curve starts at $180^\circ$, passes through $90^\circ$ (dot) at the middle tick and approaches $0^\circ$. The tick label under the middle tick is cut off at the frame edge `(?)`; the speech says "This is omega naught" [1:19:04] [likely].
**Speech vs board:** "it doesn't have that sort of special behavior near the resonant frequency" [1:18:13]: $180^\circ$ at low $\omega$, $90^\circ$ at $\omega_0$, $0^\circ$ at high $\omega$. Agrees. [sure]
**Re-derived:** $\angle H(\omega_0)=90^\circ$ (python). The phase curve's steepness near $\omega_0$ in fact depends on Q (sharper for high Q). He drew one curve; *mine, not his.*
**Speech after the last frame (1:19:28–1:20:43, transcript.txt):** student: approaching 1 from below, is that 0 dB? Answer: "it can actually approach from either side", then "This is not decibels" (label correction). Student: can the output be arbitrarily large with small R? "arbitrarily high but finite. But then as you make it higher, it'll be more narrow... the characteristic behavior of resonant systems generally" [1:20:21]. Class ends: "We'll pick up with this on Wednesday" [1:20:40].

---

## Error / discrepancy register

| # | t | Source | What | Status |
|---|---|---|---|---|
| 1 | 0:55:07–0:57:40 | board p21 | Third phase tick labelled $\omega_0$; should be $10\omega_0$ | Student caught it; corrected on board |
| 2 | 1:13:52, 1:19:56 | board p32/p33 | HP magnitude axis labelled "[dB]" with linear ticks 0, 1 | Acknowledged verbally ("This is not decibels"); label never erased |
| 3 | 0:51:52–0:54:38 | board p20/p21 | Combined straight-line magnitude vertex drawn at 0 dB. A literal sum of the factor asymptotes gives $20\log(\omega_0RC)=-20\log Q$ dB (0 dB only if $Q=1$) | Not acknowledged. His answer to the student's question (0:53:58) calls it a "shortcut" using $\lvert H(\omega_0)\rvert=1$ |
| 4 | 1:16:23 | board p32 | "low $Q<1$" curve drawn monotone; true HP overshoots 1 for $0.707<Q<1$ | Minor; not acknowledged |
| 5 | 0:46:52 | speech | "quadratic zero" for the quadratic pole | Slip; board correct |
| 6 | 0:49:16 | speech | "90 degrees at omega naught" for $A_3$; it is $-90^\circ$ | Slip; board and 0:48:22 correct |
| 7 | 1:03:14–1:03:25 | speech | "series resistance", "resistance of the inductor" for impedance | Slip; board correct |
| 8 | 0:17:56 | ASR | "plus (or?) l c" for $+4LC$ | ASR; board correct |
| 9 | various | ASR | "You'll be at all" = Ulaby et al.; "omega nod/dot" = $\omega_0$; "w zero b zero" = $\omega_0$; "box in general" = "Bode... (?)" | ASR only |
