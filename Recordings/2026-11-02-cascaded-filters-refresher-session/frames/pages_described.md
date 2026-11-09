# 2026-11-02 cascaded filters (recorded session): pages described

Frame-description pass per `DESCRIBE_FRAMES_PROMPT.md`. Inputs (all read from the base checkout `Recordings/2026-11-02-cascaded-filters-refresher-session/`):
- `QUALITY.md`
- `frames/pages_with_speech.md`
- all 55 linked page JPEGs, plus the earlier-state frames named per page
- `frames/index.txt`, `contact_sheet.jpg`
- `transcript.paragraphs.md`, `transcript.txt`
- the notes transcription `Transcripts/Refreshers/cascaded_filters_notes_F26.md`, which is the authority for equations

**Source correction to QUALITY.md.** QUALITY.md labels the source "document camera / photo". It is not. Every frame is a screen capture of **OneNote for Windows 10** (purple title bar, pen toolbar) on a tablet, with a webcam inset of Ed Yu at the top right.
- The 55 "pages" are scroll positions of **one continuous OneNote page**. The posted PDF splits that page into 5.
- 34 of the 55 are scroll-backs that add no ink.
- The page-final frame is often a scroll-back, so new ink sometimes shows only in an earlier state. Each such case names the frame actually used.
- The QUALITY.md header carries a placeholder id, `2026-00-00-cascaded-filters`.

**Re-derivation:** python3 (2026-11-06). Every number marked "(py)" was recomputed from the givens.

Confidence tags: `[sure]` the frame is legible and agrees with the speech or the notes PDF. `[likely]` only one source, but legible. `[unclear]` not readable. `[board differs]` my recomputation does not match the board.

---

## p01  f_0003.jpg  [0:00:00 – 0:02:24]
**Topic:** typed page title "Recorded session notes" (f_0002, 0:00:01). Handwritten: "**Example:** cascaded band pass filter" ("Example:" underlined).
**Board:** no equations yet.
**Diagram (stage 1 only so far):**
- Source $\underset{\sim}{V}_s$: circle with ±, + on top, bottom terminal to ground.
- The + terminal goes up and right through **1 kΩ** to the inverting (−) input node (open circle) of op-amp "**1**".
- The + input goes to ground through an open circle.
- Feedback from the − node to the output: **10 kΩ (top) in parallel with 9 nF (below)**.
- The output goes to an open-circle terminal labelled $\underset{\sim}{V}_1$.
- Label "(low pass)" under the op-amp.  [sure]

**Speech vs board:** they agree on 1 k, 10 k ∥ 9 nF and $V_1$. "This, you may recall, is our lowpass filter... let low frequencies through, and it'll cut off high frequencies" [0:02:06].

## p02  f_0081.jpg  [0:02:24 – 0:11:46]
**Topic:** stage 2 added; headings "Op-amp 1 (low-pass filter):" and "Op-amp 2 (high-pass filter):".
**Diagram (full circuit; from f_0007, 0:04:48, and f_0259):**
- From $\underset{\sim}{V}_1$: **12 kΩ in series with 9 nF** to the − input of op-amp "**2**".
- The + input is grounded.
- A **96 kΩ** feedback resistor runs from the output to the − input.
- The output goes to an open circle "+" labelled $\underset{\sim}{V}_{out}$. A "−" open circle below it is grounded.
- Label "(high pass)".  [sure]

**Board:**
- $\omega_{0,1}=\dfrac{1}{(10\,\mathrm{k\Omega})(9\,\mathrm{nF})}=\dfrac{1}{9}\times10^{5}\ \mathrm{rad/s}\approx 11.1\times10^{3}\ \mathrm{rad/s}$  [sure]
- $\underset{\sim}{Z}_{f1}=\dfrac{(10\,\mathrm{k\Omega})\left(1/j\omega\,9\,\mathrm{nF}\right)}{10\,\mathrm{k\Omega}+\dfrac{1}{j\omega\,9\,\mathrm{nF}}}\left(\dfrac{j\omega\,9\,\mathrm{nF}}{j\omega\,9\,\mathrm{nF}}\right)_{\text{green}}=\dfrac{10\,\mathrm{k\Omega}}{1+j\omega(10\,\mathrm{k\Omega})(9\,\mathrm{nF})}=\dfrac{10\,\mathrm{k\Omega}}{1+j\omega/\omega_{0,1}}$  [sure]
- $\underset{\sim}{V}_1=-\dfrac{\underset{\sim}{Z}_{f1}}{1\,\mathrm{k\Omega}}\underset{\sim}{V}_s=-\dfrac{10}{1+j\omega/\omega_{0,1}}\underset{\sim}{V}_s$ (wavy underline)  [sure]
- $\omega_{0,2}=\dfrac{1}{(12\,\mathrm{k\Omega})(9\,\mathrm{nF})}=\dfrac{1}{108}\times10^{6}\ \mathrm{rad/s}\approx9.26\times10^{3}\ \mathrm{rad/s}$  [sure]
- In f_0259 the 10 kΩ ∥ 9 nF pair is circled in green dashes and labelled $\underset{\sim}{Z}_{f1}$ (green).  [sure]

**Speech vs board:**
- [0:08:20] "It has the same topology as an inverting amplifier... minus RF over RS". With a feedback impedance in place of RF, $V_1=-Z_{f1}/(1\,\mathrm{k\Omega})\,V_s$.
- [0:10:10] Self-correction: "the frequency of both a zero and a pole... Or, actually, the frequency of the pole". The HP stage's zero is at the origin, not at $\omega_{0,2}$.
- ASR errors: "Versus" [0:08:38] = $V_s$; "poll" = pole.

**Re-derived (py):** $\omega_{0,1}=11{,}111$ rad/s ($f=1768$ Hz). $\omega_{0,2}=9{,}259$ rad/s ($f=1474$ Hz). Stage-1 gain $10\,\mathrm{k}/1\,\mathrm{k}=10$. Board correct.

## p03  f_0133.jpg  [0:11:46 – 0:16:08]
**Topic:** stage-2 output in terms of $V_1$, then in terms of $V_s$.
**Board (first line from f_0097, 0:12:45):**
- $\underset{\sim}{V}_{out}=-\dfrac{96\,\mathrm{k\Omega}}{12\,\mathrm{k\Omega}+\dfrac{1}{j\omega\,9\,\mathrm{nF}}}\underset{\sim}{V}_1\cdot\left(\dfrac{j\omega9\,\mathrm{nF}}{j\omega9\,\mathrm{nF}}\right)\cdot\left(\dfrac{12\,\mathrm{k\Omega}}{12\,\mathrm{k\Omega}}\right)$, with the two unit factors in green  [sure]
- $=-\dfrac{j\omega\cdot9\,\mathrm{nF}\cdot12\,\mathrm{k\Omega}}{1+j\omega(9\,\mathrm{nF})(12\,\mathrm{k\Omega})}\overbrace{\left(\dfrac{96\,\mathrm{k\Omega}}{12\,\mathrm{k\Omega}}\right)}^{8}\underset{\sim}{V}_1;\quad \omega_{0,2}=\dfrac{1}{(12\,\mathrm{k\Omega})(9\,\mathrm{nF})}$  [sure]
- $=-\dfrac{8\cdot j\,\omega/\omega_{0,2}}{1+j\,\omega/\omega_{0,2}}\underset{\sim}{V}_1$  [sure]
- $=\left(\dfrac{8\,j\omega/\omega_{0,2}}{1+j\omega/\omega_{0,2}}\right)\left(\dfrac{10}{1+j\omega/\omega_{0,1}}\right)\underset{\sim}{V}_s$  [sure] (the "$V_{out}=$" label is added in p04)

**Speech vs board:** they agree.
- [0:12:41] On multiplying by 12 kΩ/12 kΩ: "we'll see why that's a useful thing to do". It makes $(9\,\mathrm{nF})(12\,\mathrm{k\Omega})=1/\omega_{0,2}$ appear in both numerator and denominator [0:14:21].
- [0:15:31] "this negative sign and this negative sign will cancel out".

**Re-derived (py):** $96/12=8$, and overall $8\times10=80$. A numerical evaluation of the circuit equals the board expression at $\omega=10^2\ldots10^6$ rad/s, in both magnitude and phase.

## p04  f_0142.jpg  [0:16:08 – 0:18:04]
**Topic:** transfer function.
**Board:**
- $\underset{\sim}{V}_{out}=\left(\dfrac{8\,j\omega/\omega_{0,2}}{1+j\omega/\omega_{0,2}}\right)\left(\dfrac{10}{1+j\omega/\omega_{0,1}}\right)\underset{\sim}{V}_s$  [sure]
- $\underset{\sim}{H}(\omega)=\dfrac{\underset{\sim}{V}_{out}}{\underset{\sim}{V}_s}=(80)\left(\dfrac{j\omega}{\omega_{0,2}}\right)\left(\dfrac{1}{1+j\omega/\omega_{0,2}}\right)\left(\dfrac{1}{1+j\frac{\omega}{\omega_{0,1}}}\right)$, with an underbrace under each factor  [sure]

**Speech vs board:** [0:17:29] "This is a pole at the origin", corrected at [0:17:44] to "Or sorry. This is a zero at the origin." The board label reads "zero @ origin" (p06). Followed: the board and the correction. [0:17:20] "we can choose whether to include the $\omega_{0,2}$ either here or in the constant. It doesn't really matter."

## p05  f_0147.jpg  [0:18:04 – 0:18:05]
Scroll-back to the op-amp 2 derivation (same ink as p03) to read off $\omega_{0,2}$. No new ink.

## p06  f_0158.jpg  [0:18:05 – 0:18:11]
**Topic:** labels added under the factors of $H(\omega)$.
**Board:**
- "(80)" → "constant"
- "$(j\omega/\omega_{0,2})$" → "zero @ origin"
- "$1/(1+j\omega/\omega_{0,2})$" → "pole @ $\omega_{0,2}=$" (value not yet written)  [sure]

## p07  f_0159.jpg  [0:18:11]  and  p08  f_0160.jpg  [0:18:11]
Scroll positions of the p06 content. No new ink. All three pages share the speech "9.26 times 10 to the minus three", which belongs to p11.

## p09  f_0177.jpg  [0:18:11 – 0:18:30]
Scroll-back up to "Op-amp 2 (high-pass filter): $\omega_{0,2}=\ldots\approx9.26\times10^3$ rad/s" while he reads the value. No new ink.

## p10  f_0189.jpg  [0:18:30 – 0:18:37]
Scroll-back further up ($Z_{f1}$, $V_1$, op-amp 2 lines) while he reads $\omega_{0,1}=11.1\times10^3$. No new ink.

## p11  f_0197.jpg  [0:18:37 – 0:18:38]
**Board:**
- "pole @ $\omega_{0,2}=9.26\times10^{-3}$ rad/s" under the third factor  [sure: the exponent is clearly −3]
- "pole @ $\omega_{0,1}=$" started under the fourth factor

**Speech vs board:** the speech at [0:18:08] also says "times 10 to the minus three". **[board error, corrected live]**
- At [0:18:39] he says "Sorry. This is plus three over here."
- In f_0210 (0:18:52) the exponent reads $10^{+3}$, and the fourth label reads "pole @ $\omega_{0,1}=11.1\times10^{3}$ rad/s".
- Followed: $9.26\times10^{3}$ rad/s (py: 9259.26).

## p12  f_0259.jpg  [0:18:38 – 0:25:51]
The **final frame is a scroll-back** to the circuit (0:25:51), taken while he recaps the method. The Bode content is taken from **f_0217 (0:24:00) and f_0218 (0:24:51)**.
**Topic:** "Bode magnitude plot:"
**Board:**
- Corrected labels: pole @ $\omega_{0,2}=9.26\times10^{+3}$ rad/s; pole @ $\omega_{0,1}=11.1\times10^{3}$ rad/s.  [sure]
- Axis labels "$M(\omega)\,[\mathrm{dB}]$" (vertical) and "$\omega$" (horizontal).  [sure]
- A vertical tick "20log80". In f_0218 a ditto/equals mark and "$M_0$" are written below it, meaning $20\log 80=M_0$.  [sure]

**Diagram (asymptotic magnitude sketch):**
- A straight segment rises from the lower left, labelled "**20dB/decade**" with an arrow. No "+" sign is written; the notes transcription writes it as "+20".
- It breaks at a dashed vertical over $\omega_{0,2}$.
- It runs flat at the 20log80 level to a second dashed vertical over $\omega_{0,1}$, drawn to the right of $\omega_{0,2}$.
- It then falls, labelled "**−20dB/decade**" with an arrow.
- The flat segment is drawn about as wide as the rising segment, so the sketch is not to scale.  [sure]

**Speech vs board:** they agree. He derives the three regions aloud [0:20:07–0:23:35]:
- Below $\omega_{0,2}$: $H\approx80\,j\omega/\omega_{0,2}$, slope +20 dB/dec.
- Between the corners: the zero and the $\omega_{0,2}$ pole cancel, so $H\approx80$ and the curve is flat.
- Above $\omega_{0,1}$: $H\propto\omega/\omega^2$, slope −20 dB/dec.
- [0:24:11] "20 times the log of 80... a little bit under 40 dB... because the log of 100 would be two".
- [0:24:06] He calls $M_0$ "the peak nonresonant gain".
- ASR "{(Mark?) these}" [0:20:51] (confidence 0.66) is probably "mark these frequencies here".

**Re-derived (py):**
- $20\log_{10}80=38.06$ dB $=20\log10+20\log8=20.00+18.06$ dB.
- Slopes: +20.0 dB/dec over 10–100 rad/s and −20.0 dB/dec over $10^6$–$10^7$ rad/s.
- **The asymptotic plateau is never reached.** The corners are only $\log_{10}(\omega_{0,1}/\omega_{0,2})=0.079$ decade apart.
- The true peak is at $\sqrt{\omega_{0,1}\omega_{0,2}}=1.014\times10^4$ rad/s: $|H|=43.6$ (32.80 dB), which is 5.26 dB below 38.06 dB. The phase there is 0°.
- $|H(\omega_{0,2})|=|H(\omega_{0,1})|=32.76$ dB.
- The −3 dB band, measured from the true peak, runs $4.19\times10^3$ to $2.46\times10^4$ rad/s (667 Hz to 3.91 kHz), so $Q\approx0.50$.
- None of this is on the board. It goes into the vault note as added context.

## p13  f_0295.jpg  [0:25:51 – 0:26:48]
Scroll-down view of the Bode sketch ($20\log80=M_0$). No new ink.
**Speech:**
- [0:25:56] "in order for this to be a bandpass filter, we actually have the pole for the lowpass filter being at a higher frequency than the pole for the lowpass filter". The second "lowpass" is a slip for **highpass** (stage 2).
- Followed: LP pole $\omega_{0,1}=11.1\times10^3$ > HP pole $\omega_{0,2}=9.26\times10^3$, consistent with [0:19:53] "omega zero one is greater than omega zero two".
- [0:26:23] "If we had not switched those, then it would not have behaved in quite this way."

**Re-derived (py):** swapping the two corner values leaves the band-pass *shape* unchanged and scales $|H|$ by $\omega_{0,2}/\omega_{0,1}$. The mid-band asymptote becomes $80\cdot\omega_{0,2}/\omega_{0,1}=66.7$ (36.5 dB) instead of 80. If the corners were widely separated and in the wrong order, the mid-band would be strongly attenuated.

## p14  f_0297.jpg  [0:26:48]
Scroll-down view (Bode sketch and blank space). No new ink.

## p15  f_0298.jpg  [0:26:48 – 0:28:48]
**Topic:** "**Example:** band reject filter design" ("Example:" underlined).
**Board:**
- "Design a band reject active filter with the following:"  [sure]
- "(i) overall voltage gain = −50 outside the stop band."  [sure]
- "(ii) sto" (in progress)  [sure]

**Speech:**
- [0:27:21] "this is really a different kind of undertaking than analyzing a circuit".
- [0:27:54] A band reject means "over a finite range of frequencies, the output is suppressed... at other frequencies, the output is transmitted or amplified."

## p16  f_0309.jpg  [0:28:48 – 0:30:42]
**Board:**
- "(ii) stop band from 20 kHz to 40 kHz ($\omega_1=40\pi$ krad/s $=1.26\times10^{5}$ rad/s, $\omega_2=80\pi$ krad/s $=2.51\times10^{5}$ rad/s)"  [sure]
- "(iii) gain rolloff of ±40 dB/decade outside the stop band."  [sure]

**Speech vs board:** they agree.
- [0:28:59] "These are just frequencies. They're not angular frequencies... multiply... by two pi."
- [0:30:11] Spec (iii) spoken as "the slope, right, outside the stopband to be plus or minus 40 dB per decade."

**Wording issue:** "outside the stop band" in (iii) contradicts (i), which says the gain is flat at −50 outside the stop band. The p17 sketch puts the −40 and +40 dB/dec skirts heading *into* the band, below $\omega_1$'s −3 dB point and above $\omega_2$'s. So (iii) should be read as "each skirt rolls off at 40 dB/decade (second order)". Followed: the sketch.

**Re-derived (py):** $2\pi(20\,\mathrm{kHz})=1.2566\times10^5$ rad/s and $2\pi(40\,\mathrm{kHz})=2.5133\times10^5$ rad/s. Board correct to 3 s.f.

## p17  f_0339.jpg  [0:30:42 – 0:36:27]
**Topic:** "1) First, come up with overall design, then determine component values, etc."
**Board/diagram (target Bode sketch, curve in blue):**
- Vertical axis label "$M(\omega)\,[\mathrm{dB}]$", with a tick "20log50" and a dashed horizontal line at that level.
- A second dashed horizontal line sits lower. A small bracket between the two is labelled "**3dB**".
- Horizontal axis $\omega$ with ticks $10^{4}$, $10^{5}$, $\omega_1$, $\omega_2$, $10^{6}$. $\omega_1$ and $\omega_2$ sit just right of $10^5$, close together, each with a dash-dot vertical line.
- The blue curve is flat at 20log50 from the left and falls steeply to the 3 dB-down line at $\omega_1$ (label "**−40dB/decade**", arrow).
- It rises steeply from the 3 dB-down line at $\omega_2$ (label "**+40dB/decade**", arrow), then runs flat at 20log50.
- Blue braces under the axis: $10^5$–$\omega_1$ labelled "2-stage lowpass active filter $\underset{\sim}{H}_{LP}(\omega)$"; $\omega_2$–$10^6$ labelled "2-stage high-pass active filter $\underset{\sim}{H}_{HP}(\omega)$".  [sure]

**Speech:**
- [0:33:36–0:33:54] "we define the stopband such that at omega one and omega two... the magnitude has dropped down to three dB below its value outside the stopband."
- [0:34:53–0:35:04] Two stages because "each stage will give us a slope of minus 20 dB... together, cascaded, they will give us a slope of minus 40 dB per decade."
- [0:35:47] HP "because we want a large transfer function at high frequencies, and we want it to drop off as we go down in frequency."

**Re-derived (py):** $20\log_{10}50=33.98$ dB.

## p18  f_0358.jpg  [0:36:27 – 0:40:32]
**Board:**
- $\underset{\sim}{H}_{LP}(\omega)=\dfrac{1}{\left(1+j\omega/\omega_{LP}\right)^{2}},\quad \omega_{LP}=\dfrac{1}{R\,C_{LP}}$  [sure]
- $\underset{\sim}{H}_{HP}(\omega)=\dfrac{\left(j\omega/\omega_{HP}\right)^{2}}{\left(1+j\omega/\omega_{HP}\right)^{2}},\quad \omega_{HP}=\dfrac{1}{R\,C_{HP}}$  [sure]
- A right brace groups both lines: "for simplicity, choose the same R values for resistors in $\underset{\sim}{H}_{LP}$ and $\underset{\sim}{H}_{HP}$."  [sure]

**Speech:**
- [0:36:45] For a cascade "you just get the product of transfer functions of each individual stage."
- [0:38:39] Same R "because as long as the product of the resistance and the capacitance is the desired quantity... there are many combinations."
- [0:37:12] ASR "Squared because it's a SUSH filter" `(?)`; most likely "two-stage".
- No minus signs appear in $H_{LP}$ or $H_{HP}$: each inverting stage contributes −1, and the two cancel (consistent with p44).

## p19  f_0363.jpg  and  p20  f_0364.jpg  [0:40:32 – 0:40:34]
Scroll positions of the p17/p18 content. No new ink.

## p21  f_0387.jpg  [0:40:34 – 0:42:25]
**Board:** "Then combine using an inverting summing amplifier with gain = −50:"  [sure]
**Speech:**
- [0:40:36–0:40:58] "we don't wanna take the lowpass subcircuit and the highpass subcircuit and connect them in series, right, because then they'll each severely attenuate things outside the stopband... and also we'll have a nonzero slope outside the stopband."
- [0:41:00] "we want to add this response... to this response... and then amplify it."
- [0:41:21–0:41:47] "That won't be exactly right because... this slope is actually continuing down. But... it'll be at such a low level... that it doesn't really influence what this looks like."
- ASR "subscurve" = subcircuit.

## p22  f_0430.jpg  [0:42:25 – 0:45:56]
The **final frame is a scroll-back** to $H_{LP}$/$H_{HP}$ (0:45:56). The block diagram is taken from **f_0415 (0:44:32)**.
**Diagram:**
- $\underset{\sim}{V}_s$ (open circle, left) feeds a node that splits into two parallel paths.
- Upper path: box "$\underset{\sim}{H}_{LP}(\omega)$" to an open circle $\underset{\sim}{V}_1$.
- Lower path: box "$\underset{\sim}{H}_{HP}(\omega)$" to an open circle $\underset{\sim}{V}_2$.
- Both feed one box, "inverting summing amplifier with G = −50", whose output is an open circle $\underset{\sim}{V}_{out}$.  [sure]

**Board:** "2) Determine R and $C_{LP}$:"  [sure]

## p23  f_0454.jpg  [0:45:56 – 0:46:55]
Scroll position showing "Then combine..." and the block diagram. No new ink.

## p24  f_0540.jpg  [0:46:55 – 0:51:15]
The **final frame** shows the block diagram and the start of step 2. The rest of step 2 is taken from **f_0499 (0:47:49) and f_0515 (0:50:30)**.
**Board:**
- $M_{LP}(\omega)=\left|\underset{\sim}{H}_{LP}(\omega)\right|=\left|\dfrac{1}{(1+j\omega/\omega_{LP})^{2}}\right|=\dfrac{1}{1+(\omega/\omega_{LP})^{2}}$  [sure]
- "At the edges of the stop band ($\omega=\omega_1,\ \omega=\omega_2$) we want"  [sure]
- $M(\omega)=\dfrac{1}{\sqrt2}\ \Rightarrow\ M_{LP}(\omega_1)=\dfrac{1}{\sqrt2}$  [sure] Here $M$ means the magnitude *normalized to the passband level*; the actual overall magnitude at a band edge is $50/\sqrt2$.
- $\dfrac{1}{1+(\omega_1/\omega_{LP})^{2}}=\dfrac{1}{\sqrt2}\ \Rightarrow\ \left(\dfrac{\omega_1}{\omega_{LP}}\right)^{2}=\sqrt2-1$  [sure]
- $\Rightarrow\ \omega_{LP}=\dfrac{\omega_1}{(\sqrt2-1)^{1/2}}=\dfrac{1.26\times10^{5}\ \mathrm{rad/s}}{(\sqrt2-1)^{1/2}}=1.96\times10^{5}\ \mathrm{rad/s}=\dfrac{1}{R\,C_{LP}}$  [sure]
- "Let $\boxed{R=1\,\mathrm{k\Omega}}$."  [sure]
- "Then $C_{LP}=\dfrac{1}{R\,\omega_{LP}}=\dfrac{1}{(1\,\mathrm{k\Omega})(1.96\times10^{5}\ \mathrm{rad/s})}=\boxed{5.1\,\mathrm{nF}=C_{LP}}$"  [sure]

**Speech vs board:** they agree.
- [0:45:14] On why the magnitude is the squared form: "if this were to the one power instead of squared, then the magnitude... would be one over the square root of this denominator... when we have this squared, then the magnitude is just squared as well."
- [0:48:42] On choosing R: "there are not unique choices for r and that capacitance, so we can choose one of them to be anything."
- [0:49:01] "Once we've chosen the resistance, then the capacitance, we're not free to choose."

**Re-derived (py):**
- $(\sqrt2-1)^{1/2}=0.64359$.
- From the board's rounded $\omega_1=1.26\times10^5$: $\omega_{LP}=1.958\times10^5$, which rounds to the board's 1.96e5.
- From exact $\omega_1=1.2566\times10^5$: $\omega_{LP}=1.9525\times10^5$ rad/s. **[board differs: rounding drift, 1.95 vs 1.96]**
- $C_{LP}=5.10$ nF (from 1.96e5) or 5.12 nF (exact). Both round to 5.1 nF.
- Check: $M_{LP}(\omega_1)=0.70711=1/\sqrt2$.

## p25  f_0556.jpg  [0:51:15 – 0:51:32]
Scroll-back to the block diagram. No new ink.

## p26  f_0684.jpg  [0:51:32 – 0:52:59]
The **final frame is a scroll-back** to step 2 (0:52:58). Step 3 is written during this span (earlier states f_0557–f_0683), and its finished state is visible in f_0693 (see p27).

## p27  f_0715.jpg  [0:52:59 – 0:54:15]
The **final frame is a scroll-back** to $H_{LP}$/$H_{HP}$ and the block diagram. Content is taken from **f_0693 (0:54:12)**.
**Topic:** "3) Determine $C_{HP}$:"
**Board:**
- $M_{HP}(\omega)=\left|\underset{\sim}{H}_{HP}(\omega)\right|=\left|\dfrac{(j\omega/\omega_{HP})^{2}}{(1+j\omega/\omega_{HP})^{2}}\right|=\dfrac{(\omega/\omega_{HP})^{2}}{1+(\omega/\omega_{HP})^{2}}$  [sure]
- "We want $M_{HP}(\omega_2)=\dfrac{1}{\sqrt2}$"  [sure]
- $\Rightarrow\ \dfrac{(\omega_2/\omega_{HP})^{2}}{1+(\omega_2/\omega_{HP})^{2}}=\dfrac{1}{\sqrt2}\ \Rightarrow\ \left(\dfrac{\omega_2}{\omega_{HP}}\right)^{2}=\dfrac{1}{\sqrt2-1}$  [sure]
- $\Rightarrow\ \omega_{HP}=(\sqrt2-1)^{1/2}\,\omega_2=(\sqrt2-1)^{1/2}\,($ (in progress)  [sure]

**Speech:** [0:52:17] "as omega becomes very large, then this magnitude approaches one."
**Re-derived (py):** with $u=(\omega_2/\omega_{HP})^2$, $u/(1+u)=1/\sqrt2$ gives $u=1/(\sqrt2-1)=2.414$. Correct.

## p28  f_0724.jpg  and  p29  f_0725.jpg  [0:54:15 – 0:54:16]
No speech captured. **Scroll-backs** to the target Bode sketch (p17 content) as he scrolls up to find the value of $\omega_2$. No new ink.

## p30  f_0743.jpg  [0:54:16 – 0:54:21]  and  p31  f_0744.jpg  [0:54:21]
Scroll-back to "1) First, come up with overall design..." and the sketch. The speech "up here is 2.51 times 10 to the fifth" refers to the p16 line, which is above the visible area. No new ink.

## p32  f_0776.jpg  [0:54:21 – 0:54:26]
Scroll back down through step 2 to the start of step 3. No new ink.

## p33  f_0789.jpg  [0:54:26 – 0:56:15]
**Board:**
- $\Rightarrow\ \omega_{HP}=(\sqrt2-1)^{1/2}\omega_2=(\sqrt2-1)^{1/2}(2.51\times10^{5}\ \mathrm{rad/s})=1.62\times10^{5}\ \mathrm{rad/s}$  [sure]
- $\omega_{HP}=\dfrac{1}{R\,C_{HP}}\ \Rightarrow\ C_{HP}=\dfrac{1}{R\,\omega_{HP}}=\dfrac{1}{(10^{3})(1.62\times10^{5}\ \mathrm{rad/s})}=\dfrac{1}{1.62\times10^{8}}=\boxed{6.2\,\mathrm{nF}=C_{HP}}$  [sure]
- An arrow runs from the $R$ in $1/(R\,C_{HP})$ to "1kΩ".  [sure]

**Speech vs board:** they agree. [0:55:51] "that capacitance goes in series with the voltage source and the resistor that are at the input."
**Re-derived (py):**
- $\omega_{HP}=1.6175\times10^5$ rad/s (exact $\omega_2$) or $1.6154\times10^5$ rad/s (from 2.51e5). Both round to $1.62\times10^5$.
- $1/(1.62\times10^8)=6.17$ nF; the exact value is 6.18 nF. The board's 6.2 nF is rounded to 2 s.f.; to 3 s.f. it is 6.17–6.18 nF.
- Check: $M_{HP}(\omega_2)=0.70711$.

## p34  f_0859.jpg  [0:56:15 – 0:57:07]
**Board:** "4) Design inverting summing amplifier with G = −50:"  [sure]

## p35  f_0926.jpg  [0:57:07 – 1:00:19]
The **final frame is a partial render** of step 2: the bottom half is blank, a OneNote scroll artifact. Content is taken from **f_0865 (1:00:00)**.
**Diagram:**
- $\underset{\sim}{V}_1$ (open circle) through $R$ and $\underset{\sim}{V}_2$ (open circle) through $R$ meet at a node wired to the − input (open circle) of an op-amp.
- The + input is grounded.
- $R_f$ runs from the output back to the − input.
- The output goes to an open circle "+" $\underset{\sim}{V}_{out}$, with a "−" open circle to ground.  [sure]

**Board:**
- "KCL at inverting input:" $\ -\dfrac{\underset{\sim}{V}_1}{R}-\dfrac{\underset{\sim}{V}_2}{R}-\dfrac{\underset{\sim}{V}_{out}}{R_f}=0$  [sure]
- $\Rightarrow\ \underset{\sim}{V}_{out}=-\dfrac{R_f}{R}\left(\underset{\sim}{V}_1+\underset{\sim}{V}_2\right)$  [sure]
- "For $\boxed{R=1\,\mathrm{k\Omega}}$, we choose $\boxed{R_f=50\,\mathrm{k\Omega}}$"  [sure]
- $\Rightarrow\ \underset{\sim}{V}_{out}=-50\left(\underset{\sim}{V}_1+\underset{\sim}{V}_2\right)$  [sure]

**Speech vs board:** they agree.
- The KCL terms are currents *leaving* the virtual-ground node: [0:58:24] "the current up through this upper resistor r is minus v one over r."
- [0:57:52] Equal input resistors "because we want the gain for... each of the voltage inputs to be the same."
- ASR "{RF.}" [0:57:35] (confidence 0.64) matches $R_f$ on the board.

## p36  f_0930.jpg  [1:00:19 – 1:00:24]
Scroll-back to step 3. The "Oops" at 1:00:23 is a scroll mishap. No new ink.

## p37  f_0942.jpg  [1:00:24 – 1:00:25]  and  p38  f_0943.jpg  [1:00:25]
Scroll positions of the step-4 summing amplifier. No new ink.

## p39  f_0965.jpg  [1:00:25 – 1:03:37]
The **final frame is a scroll-back** to steps 3–4 (1:03:36). The final circuit's LP and HP chains are taken from **f_0949 (1:03:35)**.
**Topic:** "5) Combine subcircuits into final circuit:"
**Diagram (so far):** an upper chain of two LP stages ending at $\underset{\sim}{V}_1$ and a lower chain of two HP stages ending at $\underset{\sim}{V}_2$. Full description under p44/p55.  [sure]
**Speech:**
- [1:01:24] "for a lowpass active filter, the feedback loop contains a resistor. All these resistors are r. This is c lowpass."
- [1:02:34–1:02:59] HP: "a resistor in series with a capacitor... the feedback connection here is just the resistor r."
- ASR "highpass passiveness" [1:02:45] = HP capacitance.
- ASR "{r.}" [1:01:53] (confidence 0.62) = the second stage's input resistor R.

## p40  f_0987.jpg  [1:03:37 – 1:03:39],  p41  f_1006.jpg  [1:03:39 – 1:03:48],  p42  f_1019.jpg  [1:03:48 – 1:03:50],  p43  f_1028.jpg  [1:03:50 – 1:03:54]
Scroll-backs through the block diagram and steps 2, 3 and 4, on the way up to show "that inverting summing amplifier looks like this" [1:03:50]. No new ink.

## p44  f_1069.jpg  [1:03:54 – 1:06:00]
The **final frame is a scroll-back** to steps 2–3 (1:06:00). The completed final circuit is in **f_1045 (1:04:49)** and is identical to f_1198 (p55).
**Diagram (complete band-reject filter, five op-amps):**
- $\underset{\sim}{V}_s$ (open circle, far left) goes to a node that splits upward and downward.
- **Upper LP chain:**
  - Stage A: series $R$ to the − input of op-amp A; feedback $R$ (top) ∥ $C_{LP}$ (below); + input grounded.
  - A's output goes to an open circle, then series $R$ to the − input of op-amp B; feedback $R\parallel C_{LP}$; + input grounded.
  - B's output is the open circle $\underset{\sim}{V}_1$.  [sure]
- **Lower HP chain:**
  - Stage C: series $R$, then series $C_{HP}$, to the − input of op-amp C; feedback $R$; + input grounded.
  - C's output goes to an open circle, then series $R$, then series $C_{HP}$, to the − input of op-amp D; feedback $R$; + input grounded.
  - D's output is the open circle $\underset{\sim}{V}_2$.  [sure]
- **Summer:** $\underset{\sim}{V}_1$ through $R$ and $\underset{\sim}{V}_2$ through $R$ meet at the − input of op-amp E; feedback $R_f$; + input grounded. E's output is the open circle "+" $\underset{\sim}{V}_{out}$, with a "−" open circle to ground.  [sure]
- **Values (from steps 2–4):** all ten resistors are $R=1$ kΩ; $C_{LP}=5.1$ nF (×2); $C_{HP}=6.2$ nF (×2); $R_f=50$ kΩ.

**Speech:** [1:04:47–1:05:09] "this circuit looks like a very complicated circuit... but you can see, hopefully... how you can build up to the circuit by considering just the fundamental blocks."
**Re-derived (py), full circuit with board values:**
- Outside the band the gain is −50: $|H|=49.997$ at $10^3$ rad/s and $49.968$ at $10^7$ rad/s, phase ≈ ±180°.
- **The −3 dB condition is not met at the band edges.** $|H(\omega_1)|=17.2$ (24.7 dB, **−9.3 dB** relative to 50) and $|H(\omega_2)|=17.2$ (−9.3 dB).
- The other branch is not negligible at the edges: $|V_2/V_s|=0.378$ at $\omega_1$ and $|V_1/V_s|=0.378$ at $\omega_2$.
- The notch minimum is at 28.3 kHz, $|H|=5.34$ (−19.4 dB relative to 50).
- The actual −3 dB stop band is **11.7 kHz to 68.5 kHz**, not 20–40 kHz.
- With exact (unrounded) component values: −9.29 dB at both edges, the same 11.7–68.5 kHz band, notch −19.8 dB.
- Cause: the design method treats each branch alone at its own band edge. He flagged this qualitatively ("won't be exactly right" [0:41:21]), but only for frequencies far outside the band. **[design does not meet spec (ii) once the summed response is checked]**

## p45  f_1070.jpg … p54  f_1180.jpg  [1:06:00 – 1:06:42]
Closing scroll-through of the whole page during the recap [1:06:10–1:06:34]: "First, we figured... what are the... functional blocks... Then we figured out the details of what each of these blocks would have to look like." No new ink. What each frame shows:
- p45 f_1070, p46 f_1074: steps 2–3
- p47 f_1094: the target Bode sketch
- p48 f_1125: "1) First..." with the sketch
- p49 f_1131: $H_{LP}$/$H_{HP}$
- p50 f_1157: the block diagram and step 2
- p51 f_1164, p52 f_1168: step 2
- p53 f_1176: steps 3–4
- p54 f_1180: step 4

## p55  f_1198.jpg  [1:06:42 – 1:06:44]
The final circuit, complete (same as p44 / f_1045). The closing speech at [1:06:45] is not attached to any page in pages_with_speech.md: "What actually looks like quite a complicated circuit over here, but you can kind of see now, hopefully, how we can get to this using the basic elements... So that's it for these two examples, and I will now stop the recording."

---

## Cross-check against the notes transcription (`cascaded_filters_notes_F26.md`)
- Every equation and value in the notes matches the frames: 11.1e3, 9.26e3, 80, 1.26e5, 2.51e5, 1.96e5, 5.1 nF, 1.62e5, 6.2 nF, 50 kΩ, and all five circuits.
- The notes show the *corrected* $9.26\times10^{3}$. The live board briefly showed $10^{-3}$ (f_0197).
- The notes write "+20 dB/decade" on the rising segment; the board writes "20dB/decade" with no sign.
- The notes' summary calls this "the canonical Exam 2 cascade/filter-design pattern". That is the transcriber's claim. Ed Yu never mentions Exam 2 anywhere in the recording.
- The notes call the source "tablet notes". That matches the frames and contradicts QUALITY.md's doc-cam label.

## Student questions
None. This is a solo recording. The "Yep." at [0:02:24] is his own aside, and no second voice appears.
