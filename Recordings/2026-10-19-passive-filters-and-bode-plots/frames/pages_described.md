# 2026-10-19 passive filters and Bode plots: page descriptions

Frame-description pass per `DESCRIBE_FRAMES_PROMPT.md`. Inputs: `QUALITY.md`, `pages_with_speech.md`, all 24 page-final JPEGs plus 31 earlier-state frames (listed per page), `contact_sheet.jpg`, `index.txt`, `transcript.paragraphs.md`, `transcript.txt` (read in full).

Confidence tags: `[sure]` means frame and speech agree or the frame is unambiguous. `[likely]` means one source only, legible. `[unclear]` means unreadable. `(?)` marks a value that could not be read.

Source caveats carried forward:
- Tablet pages (OneNote-style, black/green/red/blue ink). The page scrolls continuously, so many "page-final" frames are scroll positions, not new pages.
- Frames stop at 1:14:24 (f_0480). Speech continues to 1:15:38. The phase formula for the first standard factor is speech-only.
- One blurry frame (f_0023, 0:12:00) is superseded by f_0026.

All formulas below were re-derived with sympy/numpy. **No board arithmetic or algebra error was found.** There is one self-corrected board slip (p16) and one notational caveat (p03, p23).

---

## p01  f_0005.jpg  [0:00:00 – 0:02:46]
Also viewed: f_0002.jpg, f_0003.jpg (typed announcement box).

**Topic:** "Transfer Functions". "Reading: Ulaby et al, Sec. 9-1"  [sure]

**Board (typed box, f_0002/f_0003):**
- "Reminder - Problem Set 6 due on Canvas 9:00AM Central time on Wednesday 10/21/2026."  [sure]
- "Problem Set 7 will be posted Wednesday morning (10/21/2026) and will be due Monday 11/02/2026. Problem Set 7 will cover transfer functions, Bode plots, and filter circuits."  [sure]
- "My office hours this week will be Monday 10/19/2026, 10:30-11:55AM (as usual) and Monday 10/19/2026, 3:00-4:30PM, both in EER 3.802. I will not have office hours on Wednesday 10/21/2026 due to travel."  [sure]

**Speech vs board:** they agree. ASR "three dot 08:02" = EER 3.802 (board).

**Speech framing [0:01:21–0:02:43]:** the last class had started on the frequency response of circuits and on filter circuits, "circuits that exhibit some engineered and useful response as a function of frequency." Response can be quantified "algebraically and analytically" (transfer functions, first) or "graphically" (Bode plots, later).  [sure]

## p02  f_0008.jpg  [0:02:46 – 0:04:24]
Also viewed: f_0006.jpg (state at 0:03:42).

**Topic:** (no title) two-port "linear circuit" box.  [sure]

**Diagram:** a box labelled "linear circuit". Left input port: top terminal (+) with current $\tilde I_{in}$ arrow pointing **into** the box along the top lead; bottom terminal (−); voltage $\tilde V_{in}$ across the port, + on top. Right output port: top terminal (+) with $\tilde I_{out}$ arrow pointing **out of** the box (to the right); bottom terminal (−); $\tilde V_{out}$ across it, + on top. All quantities carry the under-tilde (phasor).  [sure]

**Board:**
- "transfer function = ratio of output to input"  [sure]

**Speech vs board:** they agree. He says there are four possible output/input ratios.

## p03  f_0021.jpg  [0:04:24 – 0:10:21]
Also viewed: f_0014.jpg (0:06:45), f_0018.jpg (0:07:45). f_0020 is the same content.

**Topic:** the four transfer-function types, then magnitude–phase form.  [sure]

**Board (reading order, merged from f_0014 → f_0018 → f_0021):**
- voltage-gain transfer function: $\tilde H(\omega)=\tilde V_{out}(\omega)/\tilde V_{in}(\omega)$, annotated "(most common)"  [sure]
- current-gain transfer function: $\tilde H_I(\omega)=\tilde I_{out}(\omega)/\tilde I_{in}(\omega)$  [sure]
- transfer impedance: $\tilde H_Z(\omega)=\tilde V_{out}(\omega)/\tilde I_{in}(\omega)$  [sure]
- transfer admittance: $\tilde H_Y(\omega)=\tilde I_{out}(\omega)/\tilde V_{in}(\omega)$  [sure]
- "We will consider primarily the voltage gain, $\tilde H(\omega)$. Then"  [sure]
- $\tilde H(\omega)=M(\omega)\,e^{j\phi(\omega)}$ with $M(\omega)=|\tilde H(\omega)|$  [sure]
- $\phi(\omega)=\tan^{-1}\!\left(\dfrac{\mathrm{Im}(\tilde H(\omega))}{\mathrm{Re}(\tilde H(\omega))}\right)$  [sure]

**Speech vs board:** at [0:09:52] he says $\tan^{-1}$ here means the "actual correct phase of the transfer function... rather than being restricted to being between minus pi over two and pi over two." The board does not write this caveat. **I followed the speech:** this is the four-quadrant angle (atan2), not the principal value. ASR "(five?) omega" [0:09:31] = $\phi(\omega)$.

**Re-derived:** nothing numeric.

## p04  f_0022.jpg  [0:10:21 – 0:10:23]
**Topic:** scroll position of p03 (same $\tilde H=Me^{j\phi}$ lines). There is no new content. The 2-second boundary is a mis-detection: the speech ("let's ... sketch out ... a typical transfer function") belongs to p05.  [sure]

## p05  f_0088.jpg  [0:10:23 – 0:22:40]
Also viewed: f_0023.jpg (0:12:00, blurry), f_0026.jpg (0:14:24), f_0042.jpg (0:19:22), f_0074.jpg (0:21:13), f_0079.jpg (0:21:36). f_0088 is a scroll position, so I used f_0026, f_0097 and f_0104 for the full sketch.

**Topic:** "low pass" generic response and filter terminology.  [sure]

**Diagram (generic low-pass magnitude, linear axes):** vertical axis $M(\omega)$, horizontal axis $\omega$, both linear. The blue curve is flat at height $M_0$ at low $\omega$, rolls off smoothly through a dashed guide at height $M_0/\sqrt2$ (dashed horizontal line from the vertical axis, dashed vertical drop to the $\omega$ axis labelled $\omega_c$), and then tails toward 0. A double-headed arrow labelled $B$ spans from $\omega=0$ to $\omega_c$. An arrow points at the curve at $\omega_c$, labelled "slope" $=S_G$ (added during p06 time, f_0097).  [sure]

**Board:**
- "gain factor, $M_0$: maximum ("peak") non-resonant gain in filter's pass band."  [sure]
- "corner (or "cutoff") frequency, $\omega_c$: frequency at the edge(s) of the passband at which $M(\omega)=\frac{1}{\sqrt2}M_0$. Since power $\propto vi\sim v^2$, power at $\omega_c$ is half its peak value."  [sure]
- "bandwidth, $B$: for low pass and bandpass filters, $B$ is the width, in frequency, of the passband"  [sure]
- "rolloff rate, $S_G$: rate at which $M(\omega)$ ..." (continued on p06)  [sure]

**Speech vs board:** they agree. The student question at [0:15:52] (why $1/\sqrt2$?) is answered aloud: half power is "the least arbitrary criterion", and $P\propto V^2$, so $V$ drops to $1/\sqrt2$. At [0:18:44] the ASR reads "the corner frequency is half its peak value", which garbles "power at the corner frequency is half its peak value". **I followed the board.** Speech adds that B is not defined for high-pass filters because "the upper limit is infinite" [0:19:40].  [sure]

**Re-derived:** $(1/\sqrt2)^2=1/2$, and $20\log_{10}(1/\sqrt2)=-3.0103$ dB (python).

## p06  f_0113.jpg  [0:22:40 – 0:24:50]
Also viewed: f_0097.jpg (0:22:54), f_0104.jpg (0:24:00), f_0108.jpg, f_0110.jpg (0:24:49).

**Topic:** roll-off rate definition and resonant peak annotation.  [sure]

**Board:**
- "rolloff rate, $S_G$: rate at which $M(\omega)$ decreases with frequency outside the passband. For an "ideal" filter, $|S_G|$ is very large."  [sure]
- On the p05 sketch (f_0104, f_0108), in **red** ink: a dashed-dotted narrow spike rising well above $M_0$ just inside the passband edge, with a red dashed vertical line down to the $\omega$ axis labelled $\omega_0$ (red), placed just left of $\omega_c$.  [sure]

**Speech vs board:** in second-order L-and-C filters, "a localized peak" can appear near the passband edge "at which the impedances of the inductor and the capacitor cancel each other out." $M_0$ is the typical passband value, "not this localized peak."  [sure]

## p07  f_0184.jpg  [0:24:50 – 0:30:11]
Also viewed: f_0121.jpg (0:24:52), f_0126.jpg (0:25:54), f_0148.jpg (0:28:18), f_0161.jpg (0:28:29), f_0178.jpg (0:30:11). f_0145–f_0159 are scroll states with no new ink.

**Topic:** "resonant frequency, $\omega_0$".  [sure]

**Board:**
- "resonant frequency, $\omega_0$: Frequency at which the input impedance is purely real; often corresponds to an extremum of $\tilde H(\omega)$."  [sure]
- $\tilde H(\omega)=\dfrac{\tilde Z_L}{R+\tilde Z_C+\tilde Z_L}$  [sure]
- $\tilde H(\omega_0)=\dfrac{\tilde Z_L}{R}$  [sure]
- $M(\omega_0)=\left|\dfrac{\tilde Z_L}{R}\right|$  [sure] (written in answer to the student question)
- $\tilde Z_{in}=R+\dfrac{1}{j\omega C}+j\omega L$  [sure] (written in answer to the student question)

**Diagram:** input port at left labelled $\tilde V_{in}$ (two open-circle terminals). From the top-left terminal, $R$ then $C$ run in series along the top wire to a node. An inductor $L$ goes from that node down to the bottom wire. The output port is at the right, across $L$, labelled $\tilde V_{out}$. The bottom wire is common. It is a series R–C–L loop with the output taken across $L$.  [sure]

**Speech vs board:** they agree. Speech: when $Z_C$ and $Z_L$ cancel, $H(\omega_0)=Z_L/R$, and "if r goes to zero, the transfer function will go to infinity" [0:27:45]. Student Q [0:28:25]: "if H is jωL over R, it's not purely real" (ASR "DL over r" read as $j\omega L/R$ (?)). Answer: the *input impedance* $R+1/j\omega C+j\omega L$ is what is real at $\omega_0$, not $H$. Then $M(\omega_0)=\omega_0L/R$ [0:28:54].  [sure]

**Re-derived:** $\mathrm{Im}\,Z_{in}=0\Rightarrow\omega_0=1/\sqrt{LC}$. $H(\omega_0)=j\sqrt{L/C}/R$, so $M(\omega_0)=\sqrt{L/C}/R=\omega_0L/R$ (sympy). Numerical check with $L=C=1$, $R=0.1$: the maximum of $|H|$ is at $\omega=1.0025$, not exactly at $\omega_0=1$ ($|H|_{max}=10.013$ vs $|H(\omega_0)|=10$). The board's word "often corresponds to an extremum" is therefore approximate; that is consistent with the board, not an error.

## p08  f_0185.jpg  [0:30:11 – 0:31:12]
**Topic:** "Example: RC filter circuit"  [sure]

**Diagram:** an independent voltage source $\tilde V_s$ (± symbol, + on top) on the left edge. The top wire runs right through an open-circle terminal to a node. From that node, $C$ runs down to a middle node, then $R$ runs down to the bottom node. The bottom wire returns through an open-circle terminal to the source. Three output terminals (open circles) on the right sit at the top node, the middle (C–R) node and the bottom node. $C$ is on top and $R$ on the bottom.  [sure]

**Speech vs board:** they agree. He will take the output across C and, separately, across R.

## p09  f_0209.jpg  [0:31:12 – 0:38:20]
Also viewed: f_0190.jpg (0:34:01), f_0196.jpg (0:34:02), f_0199.jpg (0:36:00).

**Topic:** "$\tilde V_c$:" output across the capacitor.  [sure]

**Diagram additions (f_0190):** $\tilde V_c$ is across C with + at the top and − at the C–R node. $\tilde V_R$ is across R with + at the C–R node and − at the bottom. To the right: $\tilde Z_C=\frac{1}{j\omega C}$ (top partly hidden by toolbar; speech confirms) and $\tilde Z_R=R$.  [sure]

**Board:**
- "By voltage division: $\tilde V_c=\dfrac{\tilde Z_C}{\tilde Z_R+\tilde Z_C}\tilde V_s=\dfrac{\frac{1}{j\omega C}}{R+\frac{1}{j\omega C}}\tilde V_s\,\left(\dfrac{j\omega C}{j\omega C}\right)$" (last factor in green)  [sure]
- $=\dfrac{1}{1+j\omega RC}\tilde V_s$  [sure]
- "voltage-gain transfer function:"  [sure]
- $\tilde H_c(\omega)=\dfrac{\tilde V_c}{\tilde V_s}=\dfrac{1}{1+j\omega RC}\left(\dfrac{1-j\omega RC}{1-j\omega RC}\right)=\dfrac{1-j\omega RC}{1+\omega^2R^2C^2}\equiv M_c(\omega)e^{j\phi_c(\omega)}$ (conjugate factor in green)  [sure]
- $\Rightarrow M_c(\omega)=|\tilde H_c(\omega)|=\dfrac{1}{\sqrt{1+\omega^2R^2C^2}}$  [sure]
- $\phi_c(\omega)=-\tan^{-1}(\omega RC)$  [sure]

**Speech vs board:** they agree. Green ink is the "multiply by one" factor. He gives two routes to the phase: (a) from the rationalized form, $\tan^{-1}(\mathrm{Im}/\mathrm{Re})$, pulling out the minus sign; (b) from $1/(1+j\omega RC)$, phase = −(phase of denominator). Magnitude is "easiest" from the unrationalized form: |numerator|/|denominator|.  [sure]

**Re-derived:** $Z_C/(R+Z_C)=1/(1+j\omega RC)$; the rationalized form and $M_c$ agree (sympy). **No board error.**

## p10  f_0211.jpg  [0:38:20 – 0:40:33]
**Topic:** sketches of $M_c$ and $\phi_c$ (linear axes).  [sure]

**Diagram:**
- Left plot: vertical axis $M_c(\omega)$ with ticks 1, $1/\sqrt2$, 0. Horizontal axis $\omega$ (linear). The curve starts flat at 1, bends down through the dotted guide at $(\omega_c,1/\sqrt2)$, and approaches 0.  [sure]
- Right plot: vertical axis $\phi_c(\omega)$. The $\omega$ axis is drawn at the top (the $\phi=0$ line). The curve starts at 0 at $\omega=0$ and falls monotonically toward a dashed horizontal asymptote labelled $-\pi/2$.  [sure]

**Speech vs board:** they agree. $\omega\to0$: $M\to1$, $\phi\to0$. $\omega\to\infty$: $M\to0$, $\phi\to-\pi/2$ "in radians." "This is going to behave as a lowpass filter."

## p11  f_0231.jpg  [0:40:33 – 0:43:02]
Also viewed: f_0219.jpg (0:42:05).

**Topic:** corner frequency and phase at the corner, LP case.  [sure]

**Board:**
- $\dfrac{1}{\sqrt{1+\omega_c^2R^2C^2}}=\dfrac{1}{\sqrt2}\Rightarrow\omega_c=\dfrac{1}{RC}$, $\quad\phi_c(\omega_c)=-\tan^{-1}(1)=-\pi/4$  [sure]
- On the phase sketch: a $-\pi/4$ tick on the vertical axis, a dotted line from it to the curve, and a dotted vertical line up to an $\omega_c$ label above the axis.  [sure]

**Re-derived:** $\omega_c=1/RC$ (sympy solve). $-\tan^{-1}(1)=-0.7854$ rad $=-45^\circ$. **No board error.**

## p12  f_0235.jpg  [0:43:02 – 0:43:04]
**Topic:** scroll-back to the $\tilde V_c$ derivation (same as p09). There is no new ink. In f_0235 the numerator of the second fraction shows only "$j\omega C$" because its "1" is hidden behind the toolbar; f_0190/f_0312 show the full $\frac{1}{j\omega C}$. **No board error.** The speech ("Because if we go back to this circuit here") belongs to the intuition on p13.  [sure]

## p13  f_0288.jpg  [0:43:04 – 0:44:51]
Also viewed: f_0264.jpg (0:44:13). f_0288 is a scroll position; I used f_0264 and f_0331 for the note text.

**Topic:** notes on the LP result.  [sure]

**Board:**
- "Note: 1) $\omega_c=1/\tau$ where $\tau=RC$ is the RC time constant of the circuit."  [sure]
- "2) Output signal $\tilde V_c(\omega)$ acts as a low-pass filter." ("low-pass filter" underlined)  [sure]

**Speech (intuition, [0:43:05–0:44:12]):** at low frequency $|Z_C|$ is high, so most of the voltage drops across C. Also, "the time scale for the voltage of the capacitor to respond is basically R times C." Below $1/RC$ the capacitor voltage "is able to respond in time"; above it "there's no time for the capacitor to respond," so $V_C$ is small.  [sure]

## p14  f_0312.jpg  [0:44:51 – 0:45:18]
**Topic:** scroll-back to the circuit and the $\tilde V_c$ derivation (p09 content). The speech: the output across R+C together "is just always the input," so the other interesting choice is across R. There is no new ink.  [sure]

## p15  f_0331.jpg  [0:45:18 – 0:45:21]
**Topic:** scroll position showing the p10/p11 plots and the p13 notes (all text legible here). There is no new content.  [sure]

## p16  f_0353.jpg  [0:45:21 – 0:47:10]
Also viewed: f_0350.jpg (0:46:26).

**Topic:** "$\tilde V_R$:" output across the resistor.  [sure]

**Board:**
- "By voltage division: $\tilde V_R=\dfrac{\tilde Z_R}{\tilde Z_R+\tilde Z_C}\tilde V_s=\dfrac{R}{R+\frac{1}{j\omega C}}\tilde V_s\,\left(\dfrac{j\omega C}{j\omega C}\right)$" (last factor in green)  [sure]
- $=\dfrac{j\omega RC}{1+j\omega RC}\tilde V_s$  [sure]
- ~~$\equiv M_R(\omega)e^{j\phi_R(\omega)}$~~ written after $\tilde V_s$, then **crossed out**  [sure]

**Speech vs board:** at [0:47:04]: "Or, actually, this is not quite there yet." He crossed out the $\equiv M_Re^{j\phi_R}$ because that expression is $\tilde V_R$, not $\tilde H_R$. You must first divide by $\tilde V_s$. **This is a self-corrected board slip, not an error in the final result.**

**Re-derived:** $R/(R+Z_C)=j\omega RC/(1+j\omega RC)$ (sympy). **No error.**

## p17  f_0366.jpg  [0:47:10 – 0:49:34]
Also viewed: f_0359.jpg (0:47:59).

**Board:**
- $\tilde H_R(\omega)=\dfrac{\tilde V_R}{\tilde V_s}=\dfrac{j\omega RC}{1+j\omega RC}\equiv M_R(\omega)e^{j\phi_R(\omega)}$  [sure]
- $\Rightarrow M_R(\omega)=\dfrac{\omega RC}{\sqrt{1+\omega^2R^2C^2}}$  [sure]
- $\phi_R(\omega)=\dfrac{\pi}{2}-\tan^{-1}(\omega RC)$  [sure]

**Speech vs board:** they agree. Phase = phase(numerator) − phase(denominator). The numerator $j\omega RC$ has phase $\pi/2$ "in radians." At [0:48:52] he says "magnitude of the numerator minus the magnitude of the..." and self-corrects aloud to "the phase of the numerator minus the phase of the denominator." **I followed the corrected speech, which matches the board.**

**Re-derived:** sympy and numerical checks agree; at $\omega RC=1$: $M_R=0.7071$, $\phi_R=45.00^\circ$.

## p18  f_0405.jpg  [0:49:34 – 0:54:49]
Also viewed: f_0369.jpg (0:51:18), f_0379.jpg (0:53:27).

**Topic:** HP sketches, corner frequency and notes.  [sure]

**Diagram (f_0379):**
- Left: vertical axis $M_R(\omega)$ with ticks 1 (dashed horizontal asymptote) and $1/\sqrt2$. Horizontal axis $\omega$ (linear). The curve starts at the origin, rises concave-down through the dotted guide at $(\omega_c, 1/\sqrt2)$, and approaches the dashed line at 1.  [sure]
- Right: vertical axis $\phi_R(\omega)$ with ticks $\pi/2$ (dashed asymptote), $\pi/4$ and 0. The curve starts at $\pi/2$ at $\omega=0$, passes $(\omega_c,\pi/4)$ with dotted guides, and decays toward 0.  [sure]

**Board:**
- $\dfrac{\omega_cRC}{\sqrt{1+\omega_c^2R^2C^2}}=\dfrac{1}{\sqrt2}\Rightarrow\omega_c=\dfrac1{RC}$, $\quad\phi_R(\omega_c)=\dfrac\pi2-\tan^{-1}(1)=\pi/4$  [sure]
- "Note: 1) Again $\omega_c=1/\tau$ with $\tau=RC$"  [sure]
- "2) Output signal $\tilde V_R(\omega)$ acts as a high-pass filter." ("high-pass filter" underlined)  [sure]

**Speech:** "at high frequencies, the impedance of the capacitor goes to zero... so all the voltage drop will be across the resistor" [0:53:58].  [sure]

**Re-derived:** $\omega_c=1/RC$ (sympy). $\pi/2-\pi/4=\pi/4$. **No board error.**

## p19  f_0408.jpg  [0:54:49 – 0:56:45]
**Topic:** "Bode Plots". "Reading: Ulaby et al, Sec. 9-3"  [sure]

**Speech (no board text beyond title):** Bode plots put frequency on a log scale and magnitude on a log scale, with phase linear. "The way the Bode plot terminology is used in Ulaby, and therefore the way that we will use it here, a version of those plots where we make kind of linear approximations ... will be what we strictly refer to as the Bode plot" [0:56:11–0:56:35]. The linear approximations "make it very easy to combine" sub-part plots.  [likely: speech only for the "strictly" convention]

## p20  f_0409.jpg  [0:56:45 – 0:57:36]
**Board:**
- "Bode plots are log-log plots of $M(\omega)$ vs. $\omega$, and linear-log plots of $\phi(\omega)$ vs. $\omega$."  [sure]
- "Ve" (start of next line, completed on p21)  [sure]

## p21  f_0438.jpg  [0:57:36 – 1:04:05]
Also viewed: f_0419.jpg (1:00:50), f_0430.jpg (1:02:24).

**Board:**
- "Very useful for visualizing and thinking about circuit frequency response."  [sure]
- "The decibel (dB) scale:" (underlined)  [sure]
- "Recall that decibels (dB) quantify the ratio of power $P$ to a reference value $P_0$. Often $P_0=1\,$W or 1 mW. Define power gain $G$:" ("ratio" underlined)  [sure]
- $G=P/P_0\;\Rightarrow\;\boxed{G\,[\mathrm{dB}]=10\log_{10}\dfrac{P}{P_0}}$  [sure]
- "Each 10X change in $P$ changes $G$[dB] by 10 dB."  [sure]
- "Since $\log_{10}2\approx0.30$, a 2X change in $P$ changes $G$[dB] by ~3 dB."  [sure]

**Speech:** "dBm ... one milliwatt" reference [1:00:34]. 100X gives 20 dB [1:02:14]. "At the cutoff frequency, the transfer function ... it's reduced by three dB compared to its maximum value" [1:04:13].  [sure]

**Re-derived:** $\log_{10}2=0.30103$, $10\log_{10}2=3.0103$ dB, $10\log_{10}100=20$ dB. **No error.**

## p22  f_0447.jpg  [1:04:05 – 1:05:52]
Also viewed: f_0445.jpg.

**Board:**
- "Also, since power $\propto\tilde V\tilde I^*$ and, for linear circuits, $\tilde V\propto\tilde I$, we also have"  [sure]

## p23  f_0466.jpg  [1:05:52 – 1:10:36]
Also viewed: f_0460.jpg (1:07:13).

**Board:**
- $G\,[\mathrm{dB}]=10\log_{10}\!\left(\dfrac{P}{P_0}\right)=10\log_{10}\!\left(\left|\dfrac{\tilde V^2}{\tilde V_0^2}\right|\right)=20\log_{10}\!\left(\dfrac{|\tilde V|}{|\tilde V_0|}\right)=20\log_{10}\!\left(\dfrac{|\tilde I|}{|\tilde I_0|}\right).$  [sure]
- "In general, $\tilde H(\omega)$ will be of the form"  [sure]
- $\tilde H(\omega)=\dfrac{\tilde N(\omega)}{\tilde D(\omega)}\equiv M(\omega)e^{j\phi(\omega)}$, "where $\tilde N(\omega)$, $\tilde D(\omega)$ are polynomial functions of $(j\omega)$."  [sure]

**Speech vs board:** they agree. "If we're talking about ratios of voltage or current, then it's a factor of 20 in front, not a factor of 10" [1:06:51]. The serifed capital N is meant to distinguish the numerator function from the exponent N used on p24 [1:08:14]. Polynomials in $j\omega$ arise because the impedances always carry $j$ and $\omega$ together ($1/j\omega C$, $j\omega L$). "We'll see later when we talk about Laplace transforms" why $j\omega$ is natural [1:09:22].

**Caveat (not a board error):** $10\log(P/P_0)=20\log(|V|/|V_0|)$ holds only when $V$ and $V_0$ are referred to the same (resistive) impedance. He states it under "power ∝ V²" for a linear circuit and does not state the same-impedance condition. For a transfer function, $20\log_{10}|H|$ is simply the definition used.

## p24  f_0480.jpg  [1:10:36 – 1:14:24] (+ speech-only tail to 1:15:38)
Also viewed: f_0475.jpg (1:12:32).

**Board:**
- $\Rightarrow M(\omega)=\left|\dfrac{\tilde N(\omega)}{\tilde D(\omega)}\right|$, $\quad M(\omega)[\mathrm{dB}]=20\log_{10}|\tilde N(\omega)|-20\log_{10}|\tilde D(\omega)|.$  [sure]
- "Suppose $\tilde N(\omega)=(1+j\omega/\omega_z)^N$, $\tilde D(\omega)=1$."  [sure]
- $M(\omega)[\mathrm{dB}]=20N\log|1+j\omega/\omega_z|$  [sure]
- "$\phi$" (unfinished in the last captured frame)  [sure]

**Speech-only tail [1:14:22–1:15:38]:** "And the phase is going to be N times the inverse tangent of omega over omega z," i.e. $\phi(\omega)=N\tan^{-1}(\omega/\omega_z)$  [likely: speech only; frames end at 1:14:24]. He says "log" without subscript means $\log_{10}$ from now on [1:14:01]. Next time he will "sketch out what these two functions look like on the appropriate log-log or linear-log scales." Thought question for Wednesday: with $N=1$, "how would you get a combination like this in some expression for, say, a voltage or a current in a circuit?" [1:14:55]

**Re-derived:** $20\log_{10}|1+j|=3.010$ dB and $\tan^{-1}(1)=45^\circ$ at $\omega=\omega_z$ ($N=1$). At $\omega=10\omega_z$: 20.04 dB and $84.29^\circ$.

---

## Discrepancy summary
1. **p16, self-corrected board slip:** $\equiv M_R(\omega)e^{j\phi_R(\omega)}$ was written after the $\tilde V_R$ expression (still multiplied by $\tilde V_s$) and crossed out; he rewrote it under $\tilde H_R=\tilde V_R/\tilde V_s$.
2. **p17, speech slip:** "magnitude of the numerator minus magnitude of the..." was corrected aloud to "phase ... minus phase."
3. **p05, ASR garble:** "the corner frequency is half its peak value" should read *power* at $\omega_c$ is half its peak value (board correct).
4. **p03, notational caveat:** the board writes $\tan^{-1}(\mathrm{Im}/\mathrm{Re})$; he states aloud it means the full-quadrant phase.
5. **p23, implicit assumption:** $10\log P$ ratio $=20\log V$ ratio needs equal reference impedance (not stated).
6. **p07, approximate wording:** $\omega_0$ "often corresponds to an extremum." For the L-output series RLC the $|H|$ peak sits slightly above $\omega_0$ (1.0025 $\omega_0$ at $Q=10$).
7. ASR errors: "quarter frequency" = corner frequency (0:50:19); "03/2002 (h)" = 302/302H (0:58:31); "three dot 08:02" = EER 3.802; "Ulaby at all" = Ulaby et al.; "(five?) omega" = $\phi(\omega)$; "DL over r" = $j\omega L/R$ (?).

No computed board value disagrees with python. No `[board differs]` flags.
