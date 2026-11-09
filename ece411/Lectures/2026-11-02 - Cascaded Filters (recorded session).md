---
course: ECE 411H
date: 2026-11-02
date_posted: 2026-11-02
kind: recorded session posted on Canvas (not a regular class)
instructor: Prof. Ed Yu
topic: Cascaded active filters. (1) Analysis of a two-op-amp cascaded band-pass filter (inverting LP into inverting HP). (2) Design of a band-reject filter (two-stage LP in parallel with two-stage HP, summed by an inverting summing amplifier; gain −50, stop band 20–40 kHz, ±40 dB/decade).
reading: none named in the session
source: Recordings/2026-11-02-cascaded-filters-refresher-session (Deepgram transcript, 67 min; 55 frame pages from 351 page-final frames) + Transcripts/Refreshers/cascaded_filters_notes_F26.md (5-page handwritten notes PDF, transcribed)
source_pages: 5 (notes PDF); 55 frame pages (34 are scroll-backs with no new ink)
frames_described: Recordings/2026-11-02-cascaded-filters-refresher-session/frames/pages_described.md
tags: [ece411, recorded-session, cascaded-filters, active-filters, op-amp, band-pass, band-reject, bode-plot, filter-design, summing-amplifier, exam2]
source_quality:
  - "speech: Deepgram Nova-3, 67 min audio, 930 utterances, 7729 words (115 wpm), mean utterance confidence 0.96"
  - "speech: 58 words < 0.55 (0.8 %), 8 utterances < 0.7 (1 %); lowest [0:16:09] 0.54, [0:04:58] 0.56 'RC', [1:01:53] 0.62 'r.', [0:40:15] 0.62 'magnitude', [0:57:35] 0.64 'RF', [0:20:51] 0.66, [0:09:05] 0.66, [0:13:53] 0.68; none of them carries a number"
  - "speech: spoken math is transcribed as words, so symbols, subscripts and signs are ASR guesses; every number in this note was re-derived with python3"
  - "frames: 55 distinct pages from 351 page-final frames (1198 scene changes); 0 blurry"
  - "frames: QUALITY.md calls the source 'document camera / photo' and says the page count is implausible. The actual source is a OneNote for Windows 10 tablet screen capture with a webcam inset, and the 55 pages are scroll positions of one continuous page"
  - "QUALITY.md header id is a placeholder (2026-00-00-cascaded-filters)"
  - "equations follow the notes-PDF transcription (authority); frames and speech supply emphasis and catch one live correction (10^-3 to 10^+3)"
---

# 2026-11-02: Cascaded Filters (recorded session)

A recorded refresher posted on Canvas on 2026-11-02. It is a solo recording with no students present. It works two examples: "One example will be an analysis, and the other example will be a design problem." [0:00:09]

## Summary

- **Analyze an op-amp cascade one stage at a time, starting at the input, then multiply the stage transfer functions: $H=H_1H_2$.** Example 1 is an inverting active LP (1 kΩ in; 10 kΩ ∥ 9 nF feedback) feeding an inverting active HP (12 kΩ + 9 nF in; 96 kΩ feedback):
  $$\tilde H(\omega)=80\,\frac{j\omega/\omega_{0,2}}{(1+j\omega/\omega_{0,2})(1+j\omega/\omega_{0,1})},\qquad \omega_{0,2}=9.26\times10^3\ \text{rad/s},\ \ \omega_{0,1}=11.1\times10^3\ \text{rad/s}$$
  The two inversions cancel, so the overall sign is +.
- **Put every stage into standard form.** Multiply by 1 (as $j\omega C/j\omega C$ or $R/R$) until $RC=1/\omega_0$ appears, then label each factor: constant, zero at the origin, pole at $\omega_0$.
- **Sketch the Bode magnitude region by region from the factors.** Below $\omega_{0,2}$ it rises at +20 dB/dec. Between the corners it is flat at $20\log80=38.1$ dB. Above $\omega_{0,1}$ it falls at −20 dB/dec. That is a band-pass, and it needs the **LP corner above the HP corner**.
  - (Added, verified) The corners are only 0.08 decade apart, so the real peak is **32.8 dB, not 38.1 dB**.
- **Design to a spec in his order:**
  1. Convert Hz to rad/s.
  2. Sketch the target Bode plot.
  3. Pick functional blocks. Each 20 dB/dec of roll-off needs one first-order stage, so ±40 dB/dec needs two stages.
  4. Write each block's transfer function.
  5. Set the corners from the −3 dB band-edge condition.
  6. Choose $R$, then compute $C$.
  7. Design the gain stage.
  8. Draw the combined circuit.
- **A cascade of two identical stages is −6 dB at its own corner.** To be −3 dB at the band edge you need $\omega_{LP}=\omega_1/(\sqrt2-1)^{1/2}$ and $\omega_{HP}=(\sqrt2-1)^{1/2}\,\omega_2$, where $(\sqrt2-1)^{1/2}=0.644$. In Example 2 this gives $\omega_{LP}=1.96\times10^5$ and $\omega_{HP}=1.62\times10^5$ rad/s. With $R=1$ kΩ: $C_{LP}=5.1$ nF and $C_{HP}=6.2$ nF.
- **A band-reject filter is LP and HP in parallel, summed and amplified.** Use an inverting summing amplifier: $V_{out}=-(R_f/R)(V_1+V_2)$, with $R_f=50$ kΩ for $G=-50$. Do **not** put LP and HP in series.
- **Build big circuits from known blocks.** The five-op-amp final circuit is:
  - two inverting LP stages ($R$ in, $R\parallel C_{LP}$ feedback)
  - two inverting HP stages ($R$ then $C_{HP}$ in series at the input, $R$ feedback)
  - one two-input inverting summer
- **(Added, verified) His band-reject design misses its own spec once the two branches are summed.** It is −9.3 dB (not −3 dB) at 20 and 40 kHz, and the real −3 dB band is 11.7–68.5 kHz. Learn the method he uses, and know why it is only approximate.

---

## Content

### 0. Format [0:00:03–0:00:38]
- The session builds on "the active lowpass filter and the active highpass filter, the circuits that we discussed in class."
- To cascade means to "take the output of one and use it as the input for the other."
- "With appropriate selection of the corner frequencies for each," a cascade makes "a bandpass filter" [0:00:48–0:01:11].
- The typed OneNote page title is "Recorded session notes."

### 1. Example 1: cascaded band-pass filter (analysis) [0:00:38–0:26:48]

**Circuit** (frames f_0007, f_0259; notes p.1). Drawn left to right:
- **Source:** $\tilde V_s$ (circle with ±, + on top), bottom terminal grounded.
- **Stage 1, "(low pass)", op-amp 1:**
  - From the + terminal of $\tilde V_s$, a **1 kΩ** resistor runs to the inverting (−) input of op-amp 1. The + input is grounded.
  - Feedback, from the output back to the − input: **10 kΩ (top) in parallel with 9 nF (bottom)**. This pair is circled in green and labelled $\tilde Z_{f1}$.
  - The output node is $\tilde V_1$.
- **Stage 2, "(high pass)", op-amp 2:**
  - From $\tilde V_1$, a **12 kΩ resistor in series with a 9 nF capacitor** runs to the − input of op-amp 2. The + input is grounded.
  - Feedback: **96 kΩ** from the output to the − input.
  - The output is $\tilde V_{out}$ (+ at the output node, − at ground).

**Method** [0:03:47]: "the same approach that we used for multiple op amp circuits earlier in the semester... we start off by analyzing... the op amp that is closest to the input." Find $V_1$ in terms of $V_s$ first. Then use $V_1$ as the input to stage 2.

#### Stage 1: inverting active low-pass [0:04:25–0:09:31]
- Pole frequency, "one over the RC time constant of this resistor combined with this capacitor" [0:04:59]:
$$\omega_{0,1}=\frac{1}{(10\,\text{k}\Omega)(9\,\text{nF})}=\frac{1}{9\times10^{-5}}=\frac19\times10^5\ \text{rad/s}\approx11.1\times10^3\ \text{rad/s}$$
- Feedback impedance. For a parallel pair it is "the product of those two impedances divided by the sum" [0:06:36]. He then multiplies by 1 (shown in green) to clear the compound fraction:
$$\tilde Z_{f1}=\frac{(10\,\text{k}\Omega)\left(\frac{1}{j\omega\,9\,\text{nF}}\right)}{10\,\text{k}\Omega+\frac{1}{j\omega\,9\,\text{nF}}}\cdot\frac{j\omega\,9\,\text{nF}}{j\omega\,9\,\text{nF}}=\frac{10\,\text{k}\Omega}{1+j\omega(10\,\text{k}\Omega)(9\,\text{nF})}=\frac{10\,\text{k}\Omega}{1+j\omega/\omega_{0,1}}$$
- The stage "has the same topology as an inverting amplifier." With resistors the output would be $-R_F/R_S$ times the input. With a feedback impedance it is $-Z_f/R_S$ [0:08:20–0:09:07]:
$$\tilde V_1=-\frac{\tilde Z_{f1}}{1\,\text{k}\Omega}\tilde V_s=\underline{-\frac{10}{1+j\omega/\omega_{0,1}}\,\tilde V_s}$$

> [!warning] = Lab 5: graded work; the tutor must not use this as a walkthrough or check

#### Stage 2: inverting active high-pass [0:09:53–0:15:04]
- He first calls $\omega_{0,2}$ "the frequency of both a zero and a pole," then corrects himself: "Or, actually, the frequency of the pole" [0:10:06–0:10:21]. The stage's zero is at the origin.
$$\omega_{0,2}=\frac{1}{(12\,\text{k}\Omega)(9\,\text{nF})}=\frac{1}{108}\times10^6\ \text{rad/s}\approx9.26\times10^3\ \text{rad/s}$$
- This is again the inverting topology, with $Z_{in}=12\,\text{k}\Omega+1/(j\omega\,9\,\text{nF})$. He multiplies by $j\omega9\,\text{nF}/j\omega9\,\text{nF}$ and by $12\,\text{k}\Omega/12\,\text{k}\Omega$ (both in green). "We'll see why that's a useful thing to do in a minute." [0:12:41]
$$\tilde V_{out}=-\frac{96\,\text{k}\Omega}{12\,\text{k}\Omega+\frac{1}{j\omega\,9\,\text{nF}}}\tilde V_1\cdot\frac{j\omega9\,\text{nF}}{j\omega9\,\text{nF}}\cdot\frac{12\,\text{k}\Omega}{12\,\text{k}\Omega}=-\frac{j\omega\cdot9\,\text{nF}\cdot12\,\text{k}\Omega}{1+j\omega(9\,\text{nF})(12\,\text{k}\Omega)}\overbrace{\left(\frac{96\,\text{k}\Omega}{12\,\text{k}\Omega}\right)}^{8}\tilde V_1=-\frac{8\,j\omega/\omega_{0,2}}{1+j\omega/\omega_{0,2}}\tilde V_1$$
- The reason for the 12 kΩ trick: "this nine nanofarads times 12 kiloohms is one over omega zero two," in both the numerator and the denominator [0:14:21].

#### Combine [0:15:04–0:16:08]
Substitute $\tilde V_1$. "This negative sign and this negative sign will cancel out." [0:15:31]
$$\tilde V_{out}=\left(\frac{8\,j\omega/\omega_{0,2}}{1+j\omega/\omega_{0,2}}\right)\left(\frac{10}{1+j\omega/\omega_{0,1}}\right)\tilde V_s$$

#### Transfer function in factored form [0:16:08–0:18:50]
"The transfer function is just the product of these two factors here in the parentheses." [0:16:27]
$$\tilde H(\omega)=\frac{\tilde V_{out}}{\tilde V_s}=\underbrace{(80)}_{\text{constant}}\ \underbrace{\left(\frac{j\omega}{\omega_{0,2}}\right)}_{\text{zero @ origin}}\ \underbrace{\left(\frac{1}{1+j\omega/\omega_{0,2}}\right)}_{\text{pole @ }\omega_{0,2}=9.26\times10^{3}\ \text{rad/s}}\ \underbrace{\left(\frac{1}{1+j\omega/\omega_{0,1}}\right)}_{\text{pole @ }\omega_{0,1}=11.1\times10^{3}\ \text{rad/s}}$$
- "We can choose whether to include the $\omega_{0,2}$ either here or in the constant. It doesn't really matter." [0:17:20]
- He misspeaks "This is a pole at the origin" and corrects it at [0:17:44]: "Or sorry. This is a zero at the origin." The board label says "zero @ origin."

> [!warning] Board error, corrected live [0:18:08–0:18:52]
> He said and wrote "pole @ $\omega_{0,2}=9.26\times10^{-3}$ rad/s" (frame f_0197). At [0:18:39] he corrected it: "Sorry. This is plus three over here." The board then reads $9.26\times10^{+3}$ (f_0210), and the notes PDF has the corrected value. Use $9.26\times10^{3}$ rad/s.

#### Bode magnitude plot [0:18:50–0:24:47]
He plots only the magnitude, "because that's the plot that will really show us that this is indeed a bandpass filter." [0:19:08]

**Figure** (f_0218; notes p.2):
- **Axes:** vertical axis $M(\omega)\,[\text{dB}]$; horizontal axis $\omega$ (log scale implied).
- **Level:** a vertical-axis tick labelled "$20\log80$", with "$=M_0$" written under it.
- **Corners:** two dashed verticals, $\omega_{0,2}$ on the left and $\omega_{0,1}$ on the right.
- **Asymptotes:**
  - From the lower left, a straight rise labelled "20dB/decade" (with an arrow) up to $\omega_{0,2}$.
  - Flat at $20\log80$ from $\omega_{0,2}$ to $\omega_{0,1}$.
  - A straight fall labelled "−20dB/decade" (with an arrow) beyond $\omega_{0,1}$.
- The flat segment is drawn wide. It is not to scale.

His three-region reasoning:
- **$\omega<\omega_{0,2}$** [0:20:12]: both pole factors are "in the low frequency limit, so it's one over one." So $H\approx80\,j\omega/\omega_{0,2}$, which "goes as $j\omega$, or omega to the first power." Slope **+20 dB/decade**.
- **$\omega_{0,2}<\omega<\omega_{0,1}$** [0:21:08]: the $\omega_{0,2}$ pole is in its high-frequency limit, $\approx 1/(j\omega/\omega_{0,2})$. It cancels the zero, and the $\omega_{0,1}$ factor is still ≈ 1. So "$H(\omega)$ is just 80." Flat at **$20\log80$**, "probably in the high thirties... a little bit under 40 dB... because the log of 100 would be two" [0:22:36–0:24:22].
- **$\omega>\omega_{0,1}$** [0:22:52]: there is one $j\omega$ on top and two on the bottom, "omega over omega squared, or equivalently one over omega." Slope **−20 dB/decade**.
- He calls $M_0=20\log80$ "the peak nonresonant gain" [0:24:06]. "The passband... extends a little bit beyond from omega zero two to omega zero one" [0:23:52].
- On why op-amps matter: "by using the active filter circuit that employs these op amps, then we're able to get a magnitude of the transfer function that is significantly in excess of one, or equivalently in excess of zero dB." [0:24:25]

> [!check] Verified (python3)
> - **Corners:** $\omega_{0,1}=11{,}111$ rad/s ($f=1768$ Hz) and $\omega_{0,2}=9{,}259$ rad/s ($f=1474$ Hz).
> - **Gain:** $96/12=8$, and $8\times10=80$. $20\log_{10}80=38.06$ dB.
> - **Board formula vs circuit:** a numeric evaluation of the actual circuit equals the board's $H(\omega)$ at $10^2$–$10^6$ rad/s, in both magnitude and phase.
> - **Slopes:** +20.0 dB/dec at the low end and −20.0 dB/dec at the high end.
> - **Board errors:** none other than the corrected exponent.

> [!note] Added context: the real curve never reaches $20\log 80$
> The corners are only $\log_{10}(11{,}111/9{,}259)=0.079$ decade apart, so the flat asymptote is never reached.
> - **True peak:** at $\omega=\sqrt{\omega_{0,1}\omega_{0,2}}=1.014\times10^4$ rad/s, $|H|_{max}=80\,\dfrac{\omega_{0,1}}{\omega_{0,1}+\omega_{0,2}}=43.6$. That is **32.8 dB, 5.26 dB below $M_0$**. The phase there is 0°.
> - **At the corners:** $|H(\omega_{0,2})|=|H(\omega_{0,1})|=32.76$ dB.
> - **Bandwidth:** measured from the true peak, the −3 dB band is $4.19\times10^3$–$2.46\times10^4$ rad/s (667 Hz–3.91 kHz), so $Q\approx0.50$. A cascade of two real first-order sections cannot do better than $Q=0.5$; it reaches 0.5 when the corners coincide.
> - **What to write:** on an exam that asks for the *asymptotic* Bode plot, draw his sketch with $M_0=20\log80$. If asked for the actual peak gain or bandwidth with close corners, evaluate $|H|$ directly.

> [!note] Added context: phase Bode plot (he did not draw one)
> $\angle H=+90^\circ-\tan^{-1}(\omega/\omega_{0,2})-\tan^{-1}(\omega/\omega_{0,1})$. The overall sign is + because the two inversions cancel.
> - **Exact values (python3):** $+88.9^\circ$ at 100 rad/s, $+79.5^\circ$ at $0.1\,\omega_{0,2}=926$ rad/s, $0^\circ$ at $1.014\times10^4$ rad/s, $-79.5^\circ$ at $10\,\omega_{0,1}=1.11\times10^5$ rad/s, and $\to-90^\circ$ beyond.
> - **Straight-line phase:** each pole adds −45°/decade from $0.1\,\omega_0$ to $10\,\omega_0$. Read left to right:
>   - flat at +90° up to 926 rad/s
>   - −45°/dec from 926 to 1111 rad/s
>   - −90°/dec from 1111 to $9.26\times10^4$ rad/s, passing 0° at $1.01\times10^4$ rad/s
>   - −45°/dec from $9.26\times10^4$ to $1.11\times10^5$ rad/s
>   - flat at −90° beyond
> - The straight-line values check: +86.4° at 1111 rad/s and 0.0° at the geometric centre.

#### Why it is a band-pass; ordering of the corners [0:24:47–0:26:48]
- The recap: recognize each subcircuit as a known block, then analyze the op-amps "one by one starting with the op amp that is closest to the input" [0:25:22].
- **Ordering.** "In order for this to be a bandpass filter, we actually have the pole for the lowpass filter being at a higher frequency than the pole for the [highpass] filter... If we had not switched those, then it would not have behaved in quite this way." [0:25:56–0:26:28] (He said "lowpass" twice. The second one means the highpass stage.)
- He frames the whole example as "basically an analysis problem... we want to figure out its behavior, and then maybe after the fact, understand why it behaves in this way." [0:26:31]

> [!note] Added context: what swapping the corners actually does (python3)
> $|H|=K\dfrac{\omega/\omega_{HP}}{\sqrt{(1+(\omega/\omega_{HP})^2)(1+(\omega/\omega_{LP})^2)}}$. The denominator is symmetric in the two corners, so exchanging their values keeps the same band-pass *shape* and multiplies $|H|$ by $\omega_{HP}/\omega_{LP}$.
> - With $\omega_{HP}<\omega_{LP}$ (his case), the mid-band asymptote is the full $K=80$.
> - Reversed, it would be $K\,\omega_{LP}/\omega_{HP}$. Here that is 66.7 (36.5 dB). For widely separated corners it would be a heavily attenuated "pass" band.
>
> So the correct claim is: **the HP corner must lie below the LP corner for the mid-band gain to reach $K$.**

### 2. How cascaded stages combine [0:16:27, 0:34:53, 0:36:45]
- **Transfer functions multiply.** "You just get the product of transfer functions of each individual stage." [0:36:45] He said this, and both examples use it.
- **Slopes add.** He said this: each first-order stage gives ±20 dB/decade, so "together, cascaded, they will give us a slope of minus 40 dB per decade." [0:34:53–0:35:04] A squared factor squares the magnitude: $|1/(1+jx)^2|=1/(1+x^2)$, not $1/\sqrt{1+x^2}$ [0:45:14].
- **dB add.** *Added; he did not state it.* Because $|H_1H_2|=|H_1||H_2|$, the dB values add: $20\log80=20\log10+20\log8=20.00+18.06=38.06$ dB (verified).
- **Phases add.** *Added; he did not discuss phase.* $\angle H=\sum\angle H_k$. See the Example 1 phase note.

> [!note] Added context: loading, and why op-amp stages isolate (he did not discuss loading)
> - **Why the stages don't interact.** Solving stage 1 by itself and then feeding $V_1$ into stage 2 is valid because an ideal op-amp output is an ideal voltage source (zero output impedance). Connecting stage 2's input impedance ($12\,\text{k}\Omega+1/j\omega C$) to $V_1$ therefore does not change $V_1$, so $H=H_1H_2$ holds exactly.
> - **Passive stages are different.** Cascading two identical passive RC low-pass sections gives $H=1/(1+3j\omega RC-(\omega RC)^2)$, not $1/(1+j\omega RC)^2$.
>   - At $\omega=1/RC$: $|H|=1/3$ loaded vs. $1/2$ buffered.
>   - −3 dB point: $0.374/RC$ loaded vs. $0.644/RC$ buffered (python3).
> - **Exam relevance.** This is the P1 "why does an op-amp cascade multiply but a passive one doesn't" answer, and the main trap in P2 passive filter design.

### 3. Example 2: band-reject filter design [0:26:48–1:06:50]
Design is "really a different kind of undertaking than analyzing a circuit... we have to understand well enough how to create different functionalities using circuits and then how to put them together." [0:27:21] A band reject means "over a finite range of frequencies, the output is suppressed... at other frequencies, the output is transmitted or amplified." [0:27:54]

**Specification** (board, f_0309; notes p.2): "Design a band reject active filter with the following:"
- **(i)** overall voltage gain $=-50$ outside the stop band.
- **(ii)** stop band from 20 kHz to 40 kHz:
  - $\omega_1=2\pi(20\,\text{kHz})=40\pi$ krad/s $=1.26\times10^5$ rad/s
  - $\omega_2=2\pi(40\,\text{kHz})=80\pi$ krad/s $=2.51\times10^5$ rad/s
  - "These are just frequencies. They're not angular frequencies... multiply... by two pi." [0:28:59]
- **(iii)** gain rolloff of $\pm40$ dB/decade "outside the stop band."

> [!warning] Spec wording
> Spec (iii) says the ±40 dB/dec roll-off is "outside the stop band," but (i) makes the gain flat at −50 outside the stop band. His sketch puts the −40 and +40 dB/dec skirts at $\omega_1$ and $\omega_2$, heading *into* the stop band. Read (iii) as "each skirt rolls off at 40 dB/decade," meaning second-order skirts.

#### Step 1: "First, come up with overall design, then determine component values, etc." [0:30:40–0:43:58]
"What are the component pieces that we need in order to achieve all of these functions?" [0:30:44]

**Target Bode sketch** (f_0339; notes p.3), drawn in blue:
- **Axes:** vertical axis $M(\omega)\,[\text{dB}]$. Horizontal ticks at $10^4$, $10^5$, $\omega_1$, $\omega_2$, $10^6$, with $\omega_1$ and $\omega_2$ just above $10^5$ and close together.
- **Levels:** dashed horizontals at $20\log50$ and 3 dB below it, with a "3dB" bracket between them.
- **Band edges:** dash-dot verticals at $\omega_1$ and $\omega_2$.
- **Curve:** flat at $20\log50$ from the left; drops at **−40 dB/decade**, crossing the 3 dB line at $\omega_1$; rises at **+40 dB/decade**, crossing the 3 dB line at $\omega_2$; then flat at $20\log50$ again.
- **Braces under the axis:** "2-stage lowpass active filter $\tilde H_{LP}(\omega)$" around $10^5$–$\omega_1$, and "2-stage high-pass active filter $\tilde H_{HP}(\omega)$" around $\omega_2$–$10^6$.
- The definition behind the sketch: "we define the stopband such that at omega one and omega two... the magnitude has dropped down to three dB below its value outside the stopband." [0:33:36–0:33:54]

**Blocks** [0:34:27–0:36:13]:
- Below $\omega_1$, use a low-pass. "To get a slope of minus 40 dB per decade... use a two stage lowpass active filter, where each stage will give us a slope of minus 20 dB."
- Above $\omega_2$, use a two-stage high-pass, "because we want a large transfer function at high frequencies, and we want it to drop off as we go down in frequency," and two stages "will give us a slope of 40 dB per decade."

**Block transfer functions** [0:36:28–0:39:46] (f_0358):
$$\tilde H_{LP}(\omega)=\frac{1}{(1+j\omega/\omega_{LP})^2},\quad\omega_{LP}=\frac{1}{RC_{LP}};\qquad \tilde H_{HP}(\omega)=\frac{(j\omega/\omega_{HP})^2}{(1+j\omega/\omega_{HP})^2},\quad\omega_{HP}=\frac{1}{RC_{HP}}$$
- Board note: "for simplicity, choose the same R values for resistors in $\tilde H_{LP}$ and $\tilde H_{HP}$."
- His reason: "as long as the product of the resistance and the capacitance is the desired quantity... there are many combinations." Choose one $R$, then "choose the capacitances to give us the right frequencies." [0:38:39–0:39:17]
- Neither block has a minus sign, because the two inversions in each block cancel.

**How to combine** [0:40:20–0:42:22]:
- **Not in series.** "We don't wanna take the lowpass subcircuit and the highpass subcircuit and connect them in series, right, because then they'll each severely attenuate things outside the stopband... and also we'll have a nonzero slope outside the stopband."
- **Add instead.** "We want to add this response over here on the left to this response over here on the right and then amplify it to the appropriate level to get a total magnitude of 50 outside the stopband."
- His caveat: "That won't be exactly right because... this slope is actually continuing down. But... it'll be at such a low level... that it doesn't really influence what this looks like."
- Board: "Then combine using an inverting summing amplifier with gain = −50."

**Block diagram** [0:42:24–0:43:47] (f_0415; notes p.3):
- $\tilde V_s$ (input terminal) splits into two parallel paths.
- Upper path: box $\tilde H_{LP}(\omega)$, output $\tilde V_1$. Lower path: box $\tilde H_{HP}(\omega)$, output $\tilde V_2$.
- $\tilde V_1$ and $\tilde V_2$ are the two inputs of a box "inverting summing amplifier with $G=-50$," whose output is $\tilde V_{out}$.

#### Step 2: determine $R$ and $C_{LP}$ [0:43:58–0:50:31]
$$M_{LP}(\omega)=\left|\tilde H_{LP}(\omega)\right|=\left|\frac{1}{(1+j\omega/\omega_{LP})^2}\right|=\frac{1}{1+(\omega/\omega_{LP})^2}$$
- Why there is no square root: "if this were to the one power instead of squared, then the magnitude... would be one over the square root of this denominator... when we have this squared, then the magnitude is just squared as well." [0:45:14]
- "At the edges of the stop band ($\omega=\omega_1,\ \omega=\omega_2$) we want $M(\omega)=1/\sqrt2\Rightarrow M_{LP}(\omega_1)=1/\sqrt2$." The LP block sets the lower edge, "because omega one... is less than omega two." [0:46:55]
$$\frac{1}{1+(\omega_1/\omega_{LP})^2}=\frac{1}{\sqrt2}\ \Rightarrow\ \left(\frac{\omega_1}{\omega_{LP}}\right)^2=\sqrt2-1\ \Rightarrow\ \omega_{LP}=\frac{\omega_1}{(\sqrt2-1)^{1/2}}=\frac{1.26\times10^5\ \text{rad/s}}{(\sqrt2-1)^{1/2}}=1.96\times10^5\ \text{rad/s}=\frac{1}{RC_{LP}}$$
- "There are not unique choices for $r$ and that capacitance, so we can choose one of them to be anything... something nice and simple." [0:48:42] So: $\boxed{R=1\,\text{k}\Omega}$. "Once we've chosen the resistance, then the capacitance, we're not free to choose." [0:49:01]
$$C_{LP}=\frac{1}{R\,\omega_{LP}}=\frac{1}{(1\,\text{k}\Omega)(1.96\times10^5\ \text{rad/s})}=\boxed{5.1\ \text{nF}=C_{LP}}$$
- Each LP stage is the class first-order active low-pass: "we have a resistor in parallel with a capacitor in the feedback connection." [0:50:18]

> [!note] Notation: $M(\omega)=1/\sqrt2$ is normalized
> The board's "$M(\omega)=1/\sqrt2$" means the magnitude relative to the passband level. The actual overall magnitude at a band edge is $50/\sqrt2=35.4$ (that is, $33.98-3.01=30.97$ dB).

> [!warning] = PS8 9.42: graded work; the tutor must not use this as a walkthrough or check
> Step 2 (and step 3) use the −3 dB-edge condition for a cascade of identical first-order stages. PS8 9.42 (active LP: gain 4, corner 1 kHz, −60 dB/decade) needs the same method. The session did only the two-stage case, and this note deliberately gives no extension to any other number of stages. The tutor must not supply that extension or check his 9.42 numbers against this example.

#### Step 3: determine $C_{HP}$ [0:50:31–0:56:14]
$$M_{HP}(\omega)=\left|\frac{(j\omega/\omega_{HP})^2}{(1+j\omega/\omega_{HP})^2}\right|=\frac{(\omega/\omega_{HP})^2}{1+(\omega/\omega_{HP})^2}$$
- "As omega becomes very large, then this magnitude approaches one." [0:52:17]
- "We want $M_{HP}(\omega_2)=1/\sqrt2$":
$$\frac{(\omega_2/\omega_{HP})^2}{1+(\omega_2/\omega_{HP})^2}=\frac{1}{\sqrt2}\ \Rightarrow\ \left(\frac{\omega_2}{\omega_{HP}}\right)^2=\frac{1}{\sqrt2-1}\ \Rightarrow\ \omega_{HP}=(\sqrt2-1)^{1/2}\omega_2=(\sqrt2-1)^{1/2}(2.51\times10^5\ \text{rad/s})=1.62\times10^5\ \text{rad/s}$$
$$\omega_{HP}=\frac{1}{RC_{HP}}\ \Rightarrow\ C_{HP}=\frac{1}{R\,\omega_{HP}}=\frac{1}{(10^3)(1.62\times10^5\ \text{rad/s})}=\frac{1}{1.62\times10^8}=\boxed{6.2\ \text{nF}=C_{HP}}$$
- The board has an arrow from the $R$ to "1kΩ."
- In the HP stage, "that capacitance goes in series with the voltage source and the resistor that are at the input of that circuit." [0:55:51]

> [!check] Verified (python3), steps 2–3
> - **The factor:** $(\sqrt2-1)^{1/2}=0.64359$. A check of each block alone at its own edge gives $M_{LP}(\omega_1)=M_{HP}(\omega_2)=0.70711=1/\sqrt2$ exactly.
> - **$\omega_{LP}$ [board differs: rounding drift].** From the rounded $\omega_1=1.26\times10^5$, $\omega_{LP}=1.958\times10^5\to1.96\times10^5$, as on the board. From the exact $\omega_1=1.2566\times10^5$, $\omega_{LP}=1.953\times10^5$ rad/s, which is 1.95, not 1.96.
> - **$C_{LP}$:** 5.10 nF (board path) or 5.12 nF (exact). Either way, 5.1 nF.
> - **$\omega_{HP}$:** $1.6154\times10^5$ (board path) or $1.6175\times10^5$ (exact). Either way, $1.62\times10^5$.
> - **$C_{HP}$:** $1/1.62\times10^8=6.17$ nF, or 6.18 nF exact. The board's **6.2 nF is 2 s.f.**; to 3 s.f. it is 6.17 nF.
> - **Placement:** $\omega_{LP}>\omega_1$ and $\omega_{HP}<\omega_2$, so here $\omega_{LP}>\omega_{HP}$ (the corners cross).

#### Step 4: design the inverting summing amplifier with $G=-50$ [0:56:44–1:00:19]
**Circuit** (f_0865; notes p.5):
- $\tilde V_1$ goes through $R$, and $\tilde V_2$ goes through a second $R$. Both join at the − input of the op-amp.
- The + input is grounded.
- $R_f$ runs from the output back to the − input.
- The output is $\tilde V_{out}$ (+ at the output, − at ground).
- Equal input resistors "because we want the gain for... each of the voltage inputs to be the same, and then we can just choose $R_F$ as a multiple of $r$." [0:57:52]

**KCL at the inverting input** (virtual ground, $v_-=0$; each term is a current leaving the node) [0:58:12]:
$$-\frac{\tilde V_1}{R}-\frac{\tilde V_2}{R}-\frac{\tilde V_{out}}{R_f}=0\ \Rightarrow\ \tilde V_{out}=-\frac{R_f}{R}\left(\tilde V_1+\tilde V_2\right)$$
- "For $\boxed{R=1\,\text{k}\Omega}$, we choose $\boxed{R_f=50\,\text{k}\Omega}$" (the same $R$ as in the filters) $\Rightarrow\ \tilde V_{out}=-50\left(\tilde V_1+\tilde V_2\right)$.

#### Step 5: combine the subcircuits into the final circuit [1:00:26–1:04:45]
**Final circuit** (f_1045 = f_1198; notes p.5). Five op-amps. To redraw:
- $\tilde V_s$ (input terminal, far left) splits into an upper and a lower path.
- **Upper path, two-stage LP:**
  - Stage A: series $R$ to the − input; feedback $R\parallel C_{LP}$ ($R$ drawn above $C_{LP}$); + input grounded.
  - Stage B, the same: series $R$ from A's output; feedback $R\parallel C_{LP}$; + input grounded.
  - B's output is $\tilde V_1$.
- **Lower path, two-stage HP:**
  - Stage C: series $R$, then series $C_{HP}$, to the − input; feedback $R$; + input grounded.
  - Stage D, the same: $R$ then $C_{HP}$ in series from C's output; feedback $R$; + input grounded.
  - D's output is $\tilde V_2$.
- **Summer E:** $\tilde V_1$ through $R$ and $\tilde V_2$ through $R$ join at the − input; feedback $R_f$; + input grounded. The output is $\tilde V_{out}$ (with a ground terminal).
- **Parts list:** ten $R=1$ kΩ resistors, $2\times C_{LP}=5.1$ nF, $2\times C_{HP}=6.2$ nF, and $R_f=50$ kΩ.

Overall response, from the blocks:
$$\tilde H(\omega)=-50\left[\frac{1}{(1+j\omega/\omega_{LP})^2}+\frac{(j\omega/\omega_{HP})^2}{(1+j\omega/\omega_{HP})^2}\right]$$
This gives −50 at DC and −50 as $\omega\to\infty$.

> [!warning] Verified (python3): the finished design does not meet spec (ii)
> Simulating the full five-op-amp circuit with the board values:
> - **Outside the band the gain is right:** $|H|=49.997$ at $10^3$ rad/s and $49.968$ at $10^7$ rad/s, phase ≈ ±180°.
> - **At the band edges** $|H(\omega_1)|=|H(\omega_2)|=17.2$. That is **−9.3 dB relative to 50, not −3 dB**.
> - **The notch** bottoms out at 28.3 kHz at −19.4 dB relative to 50 (−19.8 dB with unrounded component values).
> - **The actual −3 dB stop band is 11.7 kHz to 68.5 kHz**, not 20–40 kHz.
>
> Why:
> - His caveat at [0:41:21] says the other branch is negligible "well outside the stopband." At the edges it is not: $|V_2/V_s|=0.378$ at $\omega_1$, and $|V_1/V_s|=0.378$ at $\omega_2$.
> - With $\omega_{HP}<\omega_{LP}$, the straight-line asymptotes never dip below the passband at all. The notch comes from phase cancellation: near the centre the two branches are about $\pm85^\circ$ and nearly cancel.
> - The step-2/3 conditions size each block **alone**. A spec-exact design would have to put both branches into the edge condition. He did not do that, and the session does not show it.
>
> **For the exam:** reproduce his procedure, since that is the method taught. If a P1 asks why the stop band doesn't come out exactly, this is the answer.

### 4. Recap [1:04:45–1:06:50]
- "This circuit looks like a very complicated circuit... but you can see, hopefully... how you can build up to the circuit by considering just the fundamental blocks from which this is constructed." [1:04:47–1:05:09]
- The order: a first-order LP, "two of those in series... will give us the second order lowpass filter"; the same for HP; "then we take the outputs of those two blocks, and we invert and sum them with amplification." [1:05:09–1:05:59]
- "First... what are the sort of general blocks, functional blocks that we want to have?... And then we figured out the details of what each of these blocks would have to look like building upon what we know circuits with that kind of functionality should look like." [1:06:10–1:06:37]

---

## Ed Yu's conventions & notation

| Item | His convention (this session) |
|---|---|
| Phasors and transfer functions | **Tilde below** the symbol: $\underset{\sim}{V}_s$, $\underset{\sim}{V}_1$, $\underset{\sim}{V}_{out}$, $\underset{\sim}{Z}_{f1}$, $\underset{\sim}{H}(\omega)$, $\underset{\sim}{H}_{LP}$, $\underset{\sim}{H}_{HP}$. In this note $\tilde X$ stands for his under-tilde. |
| Transfer function | $\tilde H(\omega)=\tilde V_{out}/\tilde V_s$, written as a function of $\omega$ (not $s$). |
| Corner names | $\omega_{0,1}$, $\omega_{0,2}$ numbered by op-amp. $\omega_{LP}$, $\omega_{HP}$ for the block pole frequencies. $\omega_1$, $\omega_2$ for the stop-band edges. Spoken as "pole frequency"; once as "corner frequency." |
| Standard form | $K\cdot(j\omega/\omega_0)\cdot\dfrac{1}{1+j\omega/\omega_0}\cdots$, with "1 +" in each denominator. Each factor is labelled underneath: "constant", "zero @ origin", "pole @ $\omega_0=$ value". He says the $1/\omega_0$ of the zero can go "either here or in the constant." |
| Algebra move | "Multiply by 1" in **green**: $\left(\frac{j\omega\,9\,\text{nF}}{j\omega\,9\,\text{nF}}\right)$ and $\left(\frac{12\,\text{k}\Omega}{12\,\text{k}\Omega}\right)$, to clear compound fractions and expose $RC=1/\omega_0$. |
| Inverting stage | "Same topology as an inverting amplifier": $V_{out}=-\dfrac{Z_f}{Z_{in}}V_{in}$ (spoken "minus RF over RS"). LP stage: $R$ in, $R\parallel C$ feedback. HP stage: $R$ + $C$ in series at the input, $R$ feedback. |
| Multi-op-amp method | Analyze "the op amp that is closest to the input" first; its output is the next stage's input. |
| KCL at a summing node | Currents *leaving* the virtual-ground node, all set equal to 0: $-V_1/R-V_2/R-V_{out}/R_f=0$. |
| Bode axes | "$M(\omega)\,[\text{dB}]$" against $\omega$. The level is labelled as a formula ("$20\log80$", "$20\log50$"), not as a number. Slopes are labelled "20dB/decade", "−40dB/decade" with arrows. Corners are dashed verticals. |
| Passband gain | "$M_0$", "the peak nonresonant gain." |
| Band edges | −3 dB, written as "$M(\omega)=1/\sqrt2$" (normalized to the passband) with a "3dB" bracket on the sketch. |
| Units | Hz is converted explicitly to rad/s ("$40\pi$ krad/s $=1.26\times10^5$ rad/s"). Corners are given in rad/s. Component values carry units. |
| Precision | 3 s.f. for frequencies (11.1, 9.26, 1.26, 2.51, 1.96, 1.62). Final capacitors at 2 s.f. (5.1 nF, 6.2 nF). |
| Design bookkeeping | Numbered steps on the board: "1) First, come up with overall design, then determine component values, etc." "2) Determine R and $C_{LP}$." "3) Determine $C_{HP}$." "4) Design inverting summing amplifier with G = −50." "5) Combine subcircuits into final circuit." |
| Free choices | "Let $\boxed{R=1\,\text{k}\Omega}$." He picks the resistor ("something nice and simple"), then computes the capacitor. One $R$ is used everywhere "for simplicity." |
| Boxing | Boxes chosen and computed component values ($R$, $C_{LP}$, $C_{HP}$, $R_f$). Puts a wavy underline under the intermediate result $V_1$. |
| Spec wording | "overall voltage gain", "stop band", "gain rolloff", "band reject active filter", "2-stage lowpass active filter". |

---

## Intuition & explanations he gives

- **What cascading means:** "take the output of one and use it as the input for the other... with appropriate selection of the corner frequencies for each in order to make a bandpass filter." [0:00:54–0:01:11]
- **Why the stage-by-stage method works:** "the same approach that we used for multiple op amp circuits earlier in the semester... start off by analyzing... the op amp that is closest to the input." [0:03:47]
- **An active filter is an inverting amplifier with impedances:** "It has the same topology as an inverting amplifier. So if this were just a resistor... minus RF over RS... here, where now we have a feedback impedance, then the output voltage... is going to be simply minus the feedback impedance... divided by the input resistance." [0:08:20–0:08:57]
- **Why multiply by 12 kΩ/12 kΩ:** so that "this nine nanofarads times 12 kiloohms is one over omega zero two" appears in both the numerator and the denominator. [0:12:41, 0:14:21]
- **Asymptotic Bode reasoning:** take each factor in its "low frequency limit" (→ 1) or its "high frequency limit" (→ $1/(j\omega/\omega_0)$). Count the leftover powers of $\omega$: $\omega^1$ gives +20, $\omega^0$ is flat, $\omega/\omega^2$ gives −20 dB/decade. [0:20:12–0:23:35]
- **Order-of-magnitude check:** $20\log80$ is "a little bit under 40 dB... because the log of 100 would be two." [0:24:11]
- **What op-amps buy you:** "we're able to get a magnitude of the transfer function that is significantly in excess of one, or equivalently in excess of zero dB." [0:24:25]
- **Corner ordering for a cascaded band-pass:** the LP pole must sit above the HP pole. "If we had not switched those, then it would not have behaved in quite this way." [0:25:56–0:26:28]
- **Design vs analysis:** "a different kind of undertaking than analyzing a circuit... we have to understand well enough how to create different functionalities using circuits and then how to put them together to get some more complicated functionality." [0:27:21–0:27:43]
- **Spec first, then a picture:** "the first step is really to just sort of come up with the overall design... What are the component pieces that we need?" Then "let's sketch out what the Bode plot should look like." [0:30:44, 0:31:43]
- **Why two stages:** "each stage will give us a slope of minus 20 dB... together, cascaded, they will give us a slope of minus 40 dB per decade." [0:34:53–0:35:04]
- **Why the high side is a high-pass:** "we want a large transfer function at high frequencies, and we want it to drop off as we go down in frequency." [0:35:47]
- **Why one common R:** "as long as the product of the resistance and the capacitance is the desired quantity... there are many combinations of resistance and capacitance that will give us that." [0:38:39–0:39:06]
- **Why parallel and sum, not series:** in series "they'll each severely attenuate things outside the stopband... and also we'll have a nonzero slope outside the stopband." Instead "add this response... to this response... and then amplify it." [0:40:36–0:41:16]
- **His (approximate) justification for ignoring the other branch:** "That won't be exactly right because... this slope is actually continuing down. But... it'll be at such a low level by the time we get out here that it doesn't really influence what this looks like." [0:41:21–0:41:47] This is true far from the band and false at the band edges; see the verification warning above.
- **Why the squared magnitude has no square root:** "if this were to the one power instead of squared, then the magnitude... would be one over the square root of this denominator... when we have this squared, then the magnitude is just squared as well." [0:45:14–0:45:31]
- **Free vs forced choices:** "there are not unique choices for $r$ and that capacitance, so we can choose one of them to be anything... Once we've chosen the resistance, then the capacitance, we're not free to choose." [0:48:42–0:49:11]
- **Equal summing resistors:** "because we want the gain for... each of the voltage inputs to be the same, and then we can just choose $R_F$ as a multiple of $r$ to get the overall gain factor." [0:57:52–0:58:11]
- **Complex circuits from simple blocks:** "this circuit looks like a very complicated circuit... but you can see, hopefully... how you can build up to the circuit by considering just the fundamental blocks." [1:04:47–1:05:09]

---

## Emphasis & exam intel

The recording never mentions Exam 2, problem sets, labs or the textbook. The notes-PDF transcription's summary calls this "the canonical Exam 2 cascade/filter-design pattern"; that is the transcriber's claim, not his. What he does stress, with timestamps:

1. **Two kinds of problem** [0:00:09]: "One example will be an analysis, and the other example will be a design problem." He returns to the distinction at [0:26:31] and [0:27:21].
2. **Product rule** [0:16:27]: "the transfer function is just the product of these two factors here in the parentheses." Again at [0:36:45]: "you just get the product of transfer functions of each individual stage."
3. **Label the factors** (board, f_0210): "constant," "zero @ origin," "pole @ $\omega_0=$ value." He corrects himself aloud when he misnames one [0:17:44].
4. **The magnitude plot is the proof of filter type** [0:19:08]: "that's the plot that will really show us that this is indeed a bandpass filter."
5. **Corner ordering** [0:25:56]: "in order for this to be a bandpass filter, we actually have the pole for the lowpass filter being at a higher frequency than the pole for the [highpass] filter."
6. **Hz vs rad/s** [0:28:59]: "These are just frequencies. They're not angular frequencies. So to get the angular frequency, we have to multiply these numerical values in hertz by two pi."
7. **Design order** [0:30:44, 0:31:07]: "the first step is really to just sort of come up with the overall design... And then once we've done that... determine the things like the component values."
8. **The band-edge definition** [0:33:36–0:33:54]: "we define the stopband such that at omega one and omega two... the magnitude has dropped down to three dB below its value outside the stopband."
9. **Two stages for 40 dB/decade** [0:34:53]: "each stage will give us a slope of minus 20 dB... together, cascaded... minus 40 dB per decade."
10. **Never in series for a band-reject** [0:40:36]: "we don't wanna take the lowpass subcircuit and the highpass subcircuit and connect them in series."
11. **Free choice of R, forced C** [0:48:42–0:49:11].
12. **Where the HP capacitor goes** [0:55:51]: "that capacitance goes in series with the voltage source and the resistor that are at the input of that circuit." For LP: "a resistor in parallel with a capacitor in the feedback connection" [0:50:18].

---

## Student questions

None. This is a solo recording; the "Yep." at [0:02:24] is his own aside.

---

## Exam relevance


**P3 (filter transfer function + cutoff + Bode plots): high.** Example 1 is the drill:
- Derive each stage's $H$ and put it in standard form.
- Multiply the stages, then label the constant, zeros and poles with their numerical corner frequencies.
- Sketch the asymptotic magnitude with slopes and the $20\log K$ level.

Likely variants:
- different R/C values
- corners far apart, giving a wide flat passband
- corners in the wrong order, so the mid-band is attenuated by $\omega_{LP}/\omega_{HP}$
- a phase plot as well (not shown in the session; see the added phase note)

**P4 (active op-amp or RLC filter: $H(\omega)$ in factored standard form, filter type, Bode, design ratio): high.**
- Both examples are op-amp filters. "Filter type" is read from the Bode shape. "Design ratio" appears as $R_f/R_{in}$ setting the passband gain: $10\,\text{k}/1\,\text{k}=10$ and $96\,\text{k}/12\,\text{k}=8$ in Example 1, and $R_f/R=50$ in Example 2.
- The corner is set by the feedback RC (LP stage) or the input RC (HP stage). The gain is set by the resistor ratio.
- The session's single-stage analyses are the template for "find $H(\omega)$ of this op-amp circuit, identify the type, sketch Bode."

**P2 (design/analysis: passive filter design or max power transfer): medium.**
- The design procedure transfers directly: spec → target Bode sketch → blocks → −3 dB edge condition → pick $R$ → compute $C$.
- The session is active-only. It never addresses **loading**, which is the central issue when cascading passive sections (see the added loading note).
- Max power transfer is not covered.

**P1 (four conceptual short answers): medium.** Stems this session supports:
- Why does an op-amp cascade's $H$ equal the product of the stage $H$'s? (Ideal op-amp outputs are not loaded; added context.)
- How do you make a band-pass from a LP and a HP, and what constraint applies to the corners?
- Why does a band-reject use parallel paths plus a summer rather than a series cascade?
- Why does a two-stage filter roll off at 40 dB/dec, and why is its −3 dB point not at the stage corner?
- How can an active filter have gain above 0 dB?
- Why doesn't a summed band-reject meet its edges exactly when the band is narrow?

Semiconductor physics (the other half of P1) is not touched here.

---

## Common mistakes / traps

1. **Hz vs rad/s.** 20 kHz is $1.26\times10^5$ rad/s, not $2\times10^4$. $\omega_0=1/RC$ is in rad/s, so for $f_0$ divide by $2\pi$. (Example 1: $\omega_{0,1}=11.1\times10^3$ rad/s is 1.77 kHz.)
2. **Exponent slips.** $1/(12\,\text{k}\cdot9\,\text{n})=1/(108\times10^{-6})$ is $9.26\times10^{3}$, not $10^{-3}$. He made this exact slip live and corrected it [0:18:39].
3. **Calling $j\omega/\omega_0$ a pole.** It is a **zero at the origin**: +20 dB/dec and +90°. He misspoke this once too [0:17:29].
4. **Putting a two-stage block's corner at the desired −3 dB frequency.** At its own corner a two-stage cascade is **−6.02 dB**. For −3 dB at the edge: $\omega_{LP}=\omega_1/0.644$ (corner *above* the edge) and $\omega_{HP}=0.644\,\omega_2$ (corner *below* the edge).
5. **Wrong magnitude of a squared factor.** $|1/(1+jx)^2|=1/(1+x^2)$. It is not $1/\sqrt{1+x^2}$, and not $1/(1+x^2)^2$.
6. **Sign bookkeeping.** Each inverting stage contributes −1. Two in a chain give +; the summer supplies the overall −. Example 1's $H$ is positive (+90° at low frequency). Example 2's gain is −50 at both extremes.
7. **Reading the asymptote as the actual peak.** With corners 0.08 decade apart, Example 1 peaks at 32.8 dB, not $20\log80=38.1$ dB. Report the asymptotic level only when asked for the asymptotic plot.
8. **Corner order for a cascaded band-pass.** The HP corner must be below the LP corner. Otherwise the mid-band is attenuated by $\omega_{LP}/\omega_{HP}$.
9. **A band-reject built as a series cascade.** LP × HP makes a band-*pass*. With these blocks it peaks at −10.5 dB and falls away on both sides (python3). The band-reject needs parallel paths and a sum.
10. **Forgetting the passband level in the edge condition.** The board's $M=1/\sqrt2$ is normalized. The actual edge magnitude is $50/\sqrt2$.
11. **HP vs LP stage topology.** LP: $C$ in **parallel with $R_f$** in the feedback path. HP: $C$ in **series with $R_{in}$** at the input. Swapping them swaps the filter type.
12. **Trusting the block-by-block edge design for a narrow stop band.** For a one-octave stop band, the summed response misses the −3 dB edges badly (−9.3 dB here). If asked to verify a design, evaluate the summed $H$.

---

## Self-check

> [!question]- 1. Example 1: write $\tilde H(\omega)$ in standard form, name the filter type, and give the asymptotic passband level and the slopes.
> $\tilde H(\omega)=80\,\dfrac{j\omega/\omega_{0,2}}{(1+j\omega/\omega_{0,2})(1+j\omega/\omega_{0,1})}$, with $\omega_{0,2}=1/(12\,\text{k}\cdot9\,\text{n})=9.26\times10^3$ rad/s (HP stage) and $\omega_{0,1}=1/(10\,\text{k}\cdot9\,\text{n})=11.1\times10^3$ rad/s (LP stage).
> - **Type:** band-pass.
> - **Slopes:** +20 dB/dec below $\omega_{0,2}$ (zero at the origin), flat between the corners, −20 dB/dec above $\omega_{0,1}$.
> - **Level:** $M_0=20\log80=20\log10+20\log8=38.06$ dB.
> - Verified with python3 against a direct circuit evaluation.

> [!question]- 2. Why is Example 1's actual peak gain below $20\log80$, and what is it?
> The two corners are only 0.079 decade apart, so neither pole reaches its high-frequency limit before the other one starts.
> - At $\omega=\sqrt{\omega_{0,1}\omega_{0,2}}=1.014\times10^4$ rad/s, $|H|=80\,\omega_{0,1}/(\omega_{0,1}+\omega_{0,2})=43.6$.
> - That is **32.8 dB**, 5.26 dB below the 38.06 dB asymptote. The phase there is 0°.
> - (python3)

> [!question]- 3. Two buffered, identical first-order LP stages with stage corner $\omega_c$: what is the cascade's magnitude at $\omega_c$, and where is it −3 dB? How does this set $\omega_{LP}$ in Example 2?
> - $|H(\omega_c)|=1/(1+1)=1/2$, which is −6.02 dB.
> - −3 dB requires $1/(1+x^2)=1/\sqrt2$, so $x^2=\sqrt2-1$ and $\omega_{-3\,\text{dB}}=(\sqrt2-1)^{1/2}\omega_c=0.644\,\omega_c$.
> - So the stage corner must sit **above** the band edge: $\omega_{LP}=\omega_1/0.644=1.96\times10^5$ rad/s (board), which gives $C_{LP}=1/(1\,\text{k}\Omega\cdot1.96\times10^5)=5.1$ nF.
> - (python3: 0.64359; 5.10 nF)

> [!question]- 4. In the final band-reject circuit, what is $V_{out}/V_s$ at DC and as $\omega\to\infty$? Account for every sign.
> **−50 in both limits.**
> - **At DC:** each LP stage is $-(R\parallel C)/R\to-1$, so the two LP stages give $(-1)^2=+1$. The HP branch → 0. The summer gives $-50(1+0)=-50$.
> - **As $\omega\to\infty$:** each HP stage is $-R/(R+1/j\omega C)\to-1$, so the HP branch → +1. The LP branch → 0. Again −50.
> - (python3: $|H|=49.997\angle\approx180^\circ$ at $10^3$ rad/s and $49.968\angle\approx-178^\circ$ at $10^7$ rad/s.)

> [!question]- 5. Why does he combine the LP and HP blocks in parallel through a summing amplifier rather than in series, and does the resulting design actually meet the 20–40 kHz −3 dB spec?
> **Why parallel (his reasoning, [0:40:36]):** in series the response is the product $H_{LP}H_{HP}$, and "they'll each severely attenuate things outside the stopband... and also we'll have a nonzero slope outside the stopband." The product is a band-pass (here it peaks at −10.5 dB). The sum keeps each branch's passband at unity, and the summer adds the −50 gain.
>
> **Does it meet spec? No** (python3). The summed response is −9.3 dB at 20 kHz and at 40 kHz, and the real −3 dB stop band is 11.7–68.5 kHz.
> - Each block was sized as if the other branch were negligible at its edge, but $|H_{HP}(\omega_1)|=|H_{LP}(\omega_2)|=0.378$.
> - The notch exists only through phase cancellation, and its depth is −19.4 dB.

> [!summary] Board-error audit
> - **One live board error:** $\omega_{0,2}$ was written and spoken as $9.26\times10^{-3}$, then corrected to $10^{+3}$ [0:18:39].
> - **Speech slips** (the board was right): "pole at the origin" corrected to "zero" [0:17:44]; "pole for the lowpass... than the pole for the lowpass" means highpass [0:26:03]; "both a zero and a pole" corrected to "the pole" [0:10:10].
> - **Rounding:** $\omega_{LP}$ from the exact $\omega_1$ is $1.95\times10^5$, against the board's 1.96 (no effect on 5.1 nF). $C_{HP}=6.2$ nF is 2 s.f. for 6.17–6.18 nF.
> - **Spec wording:** (iii) "outside the stop band" conflicts with (i).
> - **Design-method limitation (the substantive one):** the summed band-reject response misses its −3 dB edges, giving −9.3 dB and a real band of 11.7–68.5 kHz.
> - **ASR artefacts:** "Versus" = $V_s$; "poll" = pole; "subscurve" = subcircuit; "highpass passiveness" = HP capacitance; "SUSH filter" `(?)`, probably "two-stage".
