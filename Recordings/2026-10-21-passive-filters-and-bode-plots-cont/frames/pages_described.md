# 2026-10-21 passive filters and Bode plots (cont.): page descriptions

Description pass per `DESCRIBE_FRAMES_PROMPT.md`. Source folder: `Recordings/2026-10-21-passive-filters-and-bode-plots-cont/`.

Inputs: `QUALITY.md`, `pages_with_speech.md`, all 29 linked page JPEGs, extra frames f_0002, f_0008, f_0031, f_0046, f_0075, f_0134, f_0173, f_0180, f_0198, f_0201, f_0258, f_0304, f_0313, f_0316 (named per page where used), `transcript.paragraphs.md` and `transcript.txt` (read in full).

Notation: the board writes phasors and $H$ with an under-tilde. Here $H$, $N$, $D$, $A_i$, $V$, $I$, $Z$ stand for the under-tilded quantities. `log` on the board is $\log_{10}$. Capital $N$ is the factor order. The board also uses $N(\omega)$ for the numerator polynomial. Same letter, two meanings, as on the board.

Global caveats:
- Frames stop at 1:17:16. The last 30 s of board writing (the conjugate-multiplied $H(\omega)$, 1:17:16–1:17:46) is **speech-only**.
- No audio gaps. The longest stretch between utterance starts is 26 s, inside continuous speech (1:08:13). Pauses of about 10–13 s while he draws axes (0:34:47, 0:38:59, 1:04:25).
- f_0131 (0:37:16) is blurry. I used f_0134 (0:40:13) and f_0154 for that page.

---

## p01  f_0012.jpg  [0:00:00 – 0:02:56]
f_0012 has scrolled. I read the top of the page from f_0002 (0:00:02) and f_0008 (0:02:24).

**Topic:** typed "Class session notes - 2026_10_2(?)" announcement box, then handwritten "From last time:"

**Board:**
- Typed announcements [sure]: (1) PS6 due on Canvas today 9:00 AM Central. (2) PS7 released, due on Canvas 9:00 AM Central **Mon 11/02/2026**, "on transfer functions, Bode plots, and filter circuits." (3) No office hours after class today (travel). Monday's extra office hours replaced them.
- $H(\omega)=\dfrac{N(\omega)}{D(\omega)}=M(\omega)e^{j\phi(\omega)}$ where $N(\omega),D(\omega)$ are polynomial functions of $(j\omega)$ [sure]
- $\Rightarrow M(\omega)=\left|\dfrac{N(\omega)}{D(\omega)}\right|,\quad M(\omega)[\mathrm{dB}]=20\log|N(\omega)|-20\log|D(\omega)|$ [sure]
- Suppose $N(\omega)=\left(1+j\dfrac{\omega}{\omega_z}\right)^N,\ D(\omega)=1.$ [sure]
- $M(\omega)[\mathrm{dB}]=20N\log\left|1+j\dfrac{\omega}{\omega_z}\right|$ [sure; in f_0008/f_0012 the "1" is missing and the line reads "$|+j\omega/\omega_z|$". At 0:07:02 he says "sorry, this is a one in here", and the 1 is present from f_0031 (0:09:04) on. **Board corrected live.**]
- $\phi(\omega)=N\tan^{-1}\dfrac{\omega}{\omega_z}$ [sure]

**Diagram:** none.

**Speech vs board:** the speech adds the reason $H$ is rational in $j\omega$: impedances $R$, $1/j\omega C$ and $j\omega L$ combine, and dividing out common factors leaves polynomials in $j\omega$ [0:01:44–0:02:14]. Taking the log turns the ratio into "the difference of the logs of the numerator and the denominator", which is "a hint as to why Bode plots... are particularly useful" [0:02:24–0:02:49]. The speech agrees with the board.

---

## p02  f_0019.jpg  [0:02:56 – 0:05:31]
**Topic:** a circuit that produces a simple-zero factor (no title)

**Board:**
- $V_o=I\,(R+j\omega L)$ [sure]
- $\phantom{V_o}=I\,R\left(1+j\omega\dfrac{L}{R}\right)$ [sure]

**Diagram:** the left side is "..." (the rest of the circuit). A top wire runs to the + output terminal and a bottom wire to the − terminal. Between the two wires, a vertical branch holds $R$ (top) in series with $L$ (bottom). $V_o$ is across the output terminals, + on top. The current arrow $I$ points right into the top wire (visible in f_0020). [sure]

**Speech vs board:** "if we factor out the r... this factor over here has exactly the form that we had over here, and it's just multiplied by a constant" with exponent 1 [0:04:49–0:05:15]. Neither source writes $\omega_z=R/L$. It is implied by the comparison. [likely]

**Re-derived:** $R+j\omega L=R(1+j\omega L/R)$, so $\omega_z=R/L$ (sympy: difference = 0).

---

## p03  f_0020.jpg  [0:05:31 – 0:05:33]
**Topic:** the same page scrolled 2 s later. It shows the full "Suppose..." line and the $I\rightarrow$ arrow above the circuit. No new ink. [sure]

---

## p04  f_0078.jpg  [0:05:33 – 0:25:37]
Earlier states read: f_0031 (0:09:04), f_0046 (0:12:00), f_0075 (0:25:36, shows the two phase plots in full).

**Topic:** "magnitude:" / "Bode magnitude plot:" / "phase:" / "Bode phase plot:" for the simple zero $(1+j\omega/\omega_z)^N$

**Board:**
- **Green second stage** added to the right of the RL circuit, about 0:08:00. A second $R$–$L$ series branch hangs from a dotted extension of the + and − terminals, with its own output terminals. [sure] This is his answer to "where does $N$ come in". The speech says "not exactly like this... some other things in between". [sure]
- **"magnitude:"** (actual curve). Vertical axis "$M(\omega)$[dB]" with ticks 0, **3N** (green), 10N, 20N. The horizontal axis is $\omega$ (log) with ticks $0.1\omega_z$, $\omega_z$, $10\omega_z$. The green curve starts at 0 at the left corner, rises slowly through a dot at $(\omega_z, 3N)$, then curves steeply up. The label is "$\approx 20N\log|\omega/\omega_z|$" with an arrow to the high-frequency part. [sure]
- "$\approx$" sign, then **"Bode magnitude plot:"**. Axis "$M(\omega)$[dB]" with ticks 0, 10N, 20N and $0.1\omega_z,\ \omega_z,\ 10\omega_z$. Green: flat at 0 dB from the left edge to $\omega_z$, then a straight line rising through a dot at about $(10\omega_z, 20N)$. The label is "$=20N\log|\omega/\omega_z|$". [sure]
- **"phase:"** (actual). Axis $\phi(\omega)$ with ticks 0°, 45°N and 90°N, plus a dashed horizontal line at 90°N. $\omega$ ticks are $0.1\omega_z,\ \omega_z,\ 10\omega_z$. The green S-curve runs from 0° through a dot at $(\omega_z, 45°N)$ and approaches 90°N from below. [sure]
- "$\approx$" sign, then **"Bode phase plot:"**. Same axes. Green: 0° from the left edge to $0.1\omega_z$, then a straight line through a dot at $(\omega_z, 45°N)$ up to $(10\omega_z, 90°N)$, then flat at 90°N (on the dashed line). [sure]

**Speech vs board:**
- $|1+j|=\sqrt2$, "$\tfrac12\cdot20N\log2$... log of two, which is roughly point three... roughly three dB" [0:09:57–0:10:24]. The board writes "3N". The speech agrees.
- Magnitude rule [0:13:21–0:16:47]: "linear approximations... in each of the key regions of behavior". For $\omega<\omega_z$, use the $\omega\to0$ limit (0 dB). For $\omega>\omega_z$, use the $\omega\to\infty$ limit $20N\log|\omega/\omega_z|$, "a straight line on this log log scale".
- Phase rule [0:21:06–0:23:21]: a step at $\omega_z$ "is a little too lousy of an approximation". Use the $\omega\to0$ limit only for $\omega<0.1\omega_z$ and the $\omega\to\infty$ limit only for $\omega>10\omega_z$, with a straight line in between, which "has the advantage of going through the correct point at $\omega_z$". The speech says "point one times z" [0:22:23], a slip for $0.1\omega_z$. **I followed the board.**
- The speech says "magnitude goes to zero" as $\omega\to0$ [0:09:30] and means 0 dB, i.e. $|H|=1$. The board shows 0 on a dB axis. [sure]
- The actual-curve sketches start the curve at the axis corner, but a log axis has no $\omega=0$. This is a sketching convention, not an error.

**Re-derived (python):** $20\log_{10}\sqrt2=3.0103$ dB ✓. $\log_{10}2=0.30103$ ✓. $\tan^{-1}1=45°$ ✓. The exact simple zero ($N=1$) gives 0.043 dB at $0.1\omega_z$ and 20.043 dB at $10\omega_z$, and its phase is 5.71° at $0.1\omega_z$ and 84.29° at $10\omega_z$. The largest error of the straight-line phase is 5.71°, at $0.1\omega_z$ and $10\omega_z$. These are mine, not on the board.

---

## p05  f_0083.jpg  [0:25:37 – 0:26:19]
**Topic:** p04 scrolled back to the top (the "Suppose..." line and the RL circuit with its green second stage). No new ink. [sure]
**Speech:** the zero terminology begins: the factor "goes to zero when ω... is equal to j times omega z... j times j, which is minus one... one minus one, which is zero" [0:25:41–0:26:14].

## p06  f_0084.jpg  [0:26:19 – 0:26:20] and p07  f_0085.jpg  [0:26:20 – 0:26:21]
**Topic:** scroll states of p04 on the way down. No new ink. [sure]

---

## p08  f_0091.jpg  [0:26:21 – 0:28:52]
**Topic:** definition of a zero (no title)

**Board:**
- "$\omega_z$ is called a **zero** of $H(\omega)$, of order $N$" ("zero" underlined) [sure]
- "(since $\omega=j\omega_z\Rightarrow N(\omega)=H(\omega)=0$)." [sure; the closing parenthesis sits so that it reads "$H(\omega=0)$", but the meaning is $H(\omega)=0$, as the speech confirms at 0:27:00–0:27:17]

**Speech vs board:** "we refer to it specifically as a zero of order n, because n is the exponent" [0:26:49]. **Why the $j$** [0:27:21–0:28:46]: time-domain terms are all exponentials $e^{st}$. Decay is a real exponential. "Oscillatory behavior, which is what we have when we're talking about real frequencies, correspond[s] to imaginary values of s." Details come with Laplace transforms. The speech agrees with the board.

**Re-derived:** $1+j(j\omega_z)/\omega_z=1-1=0$ ✓.

## p09  f_0093.jpg  [0:28:52 – 0:28:53]
Scroll state of p08. No new ink. [sure]

---

## p10  f_0097.jpg  [0:28:53 – 0:32:39]
**Topic:** "Now suppose $D(\omega)=(1+j\omega/\omega_p)^N$, $N(\omega)=1$."

**Board:**
- Now suppose $D(\omega)=\left(1+j\dfrac{\omega}{\omega_p}\right)^N,\ N(\omega)=1.$ [sure]
- $\Rightarrow M(\omega)[\mathrm{dB}]=-20N\log\left|1+j\dfrac{\omega}{\omega_p}\right|$ [sure]
- $\phi(\omega)=-N\tan^{-1}\dfrac{\omega}{\omega_p}.$ [sure]
- $V_o=\dfrac{V_s}{1+j\omega RC}$ [sure]

**Diagram:** the voltage source $V_s$ (circle, + on top) is on the left. $R$ sits on the top wire, leading to the upper output terminal. $C$ is a shunt from the top node to the bottom wire. The output $V_o$ is taken across $C$ at the right-hand terminals. [sure]

**Speech vs board:** "minus minus n times the inverse tangent" [0:30:01] is a stutter, and the board has a single minus. The speech says "voltage source I" [0:31:22], an ASR error for $V_s$. "They're basically the negatives... it's what we had previously to the minus one" [0:30:19–0:30:42]. A real plus an imaginary term in a voltage-division denominator, from R in series with L or C, produces this factor [0:30:58–0:31:18]. **I followed the board.**

**Re-derived:** $V_o=V_s\dfrac{1/j\omega C}{R+1/j\omega C}=\dfrac{V_s}{1+j\omega RC}$, so $\omega_p=1/RC$ (implied, not written) (sympy ✓).

## p11  f_0101.jpg [0:32:39 – 0:32:52], p12  f_0111.jpg [0:32:52 – 0:33:04], p13  f_0112.jpg [0:33:04 – 0:33:05]
Scroll states between p08/p10 and p14. No new ink. Speech: "all these plots should just be reflected through the horizontal axis" [0:32:54]. [sure]

---

## p14  f_0130.jpg  [0:33:05 – 0:37:15]
**Topic:** "magnitude:" / "Bode magnitude plot:" for the simple pole, and the "phase:" heading

**Board:**
- **"magnitude:"** (actual). Axis "$M(\omega)$[dB]". The horizontal axis is drawn at the **top** at the 0 level, with ticks $0.1\omega_p$, $\omega_p$, $10\omega_p$. Vertical ticks are $-3N$, $-10N$, $-20N$. The green curve stays near 0 at the left, passes a dot at about $(\omega_p,-3N)$, and bends steeply down. The label is "$\approx -20\log|\omega/\omega_p|$" with an arrow. [sure that it reads this way] **[board differs: the factor $N$ is missing. It should be $\approx-20N\log|\omega/\omega_p|$, as on the Bode plot beside it.]**
- "$\approx$" sign, then **"Bode magnitude plot:"**. Same axes with ticks $-10N$, $-20N$. Green: flat at 0 dB to $\omega_p$, then a straight line down through about $(10\omega_p,-20N)$. The label is "$=-20N\log|\omega/\omega_p|$". [sure]
- "phase:" heading, plot not yet drawn. [sure]

**Speech vs board:**
- "approximately like minus 20 times the log of the magnitude of omega over omega p" [0:34:30]. The speech drops $N$ too. **Board and speech both omit $N$ on the actual-curve label. Correct is $-20N$.**
- "And then at high frequencies, it's going to increase" [0:34:25]. **Speech slip.** The magnitude *decreases*, and the board curve goes down. I followed the board.
- "linear with a slope, on this log log scale that is equal to minus 20 n times the log of omega over omega p" [0:36:04–0:36:17]. This calls the line's equation its slope. The slope is $-20N$ dB/decade, which he states correctly at 0:54:11.
- At $\omega_p$: "magnitude of one plus j, which is root two... minus three n dB" [0:34:04]. The speech agrees with the board.

**Re-derived:** $-20\log_{10}\sqrt2=-3.01$ dB ✓.

---

## p15  f_0154.jpg  [0:37:15 – 0:42:10]
f_0131 (0:37:16) is blurry, so I used f_0134 (0:40:13) for the full pair of phase plots and f_0154 for the definition.

**Topic:** "phase:" / "Bode phase plot:" for the simple pole, then the pole definition

**Board:**
- **"phase:"** (actual). Axis $\phi(\omega)$ with the horizontal axis at the top at 0°, ticks $0.1\omega_p$, $\omega_p$, $10\omega_p$. Vertical ticks are $-45°N$ and $-90°N$, with a dashed line at $-90°N$. The green curve runs from 0° through a dot at $(\omega_p,-45°N)$ and approaches $-90°N$. [sure]
- "$\approx$" sign, then **"Bode phase plot:"**. Green: 0° to $0.1\omega_p$, a straight line through $(\omega_p,-45°N)$ to $(10\omega_p,-90°N)$, then flat on the dashed $-90°N$ line. [sure]
- "$\omega_p$ is called a **pole** of $H(\omega)$, of order $N$" ("pole" underlined) [sure]
- "(since $\omega=j\omega_p\Rightarrow D(\omega)=0,\ H(\omega)\to\infty$)." [sure]

**Speech vs board:** "a pole basically is defined as a point at which the transfer function goes to infinity in this particular way" [0:40:32]. The phase construction repeats the $0.1\omega_p$ / $10\omega_p$ rule [0:39:15–0:39:50]. The speech agrees with the board.

**Student Q [0:41:35]:** "if you have a transfer function and you want to get it in decibels... taking the log of it and then multiplying by 20." He answered: "Yeah. That's right." (ASR "decimal units" = decibel units.)

---

## p16  f_0160.jpg  [0:42:10 – 0:43:07]
**Topic:** general product form

**Board:**
- "In general, $H(\omega)$ can be written in the form" [sure]
- $H(\omega)=A_1(\omega)A_2(\omega)\cdots A_n(\omega)$ [sure]

**Speech:** "for any linear circuit, there will be a limited number of types of factors... that when you multiply them together constitute the entire transfer function" [0:42:08–0:42:28]. The speech agrees with the board.

## p17  f_0166.jpg  [0:43:07 – 0:43:34]
**Board:** "where each $A_i(\omega)$ is one of the following:" [sure]

---

## p18  f_0170.jpg  [0:43:34 – 0:46:04]
**Topic:** table header and row 1, "constant K"

**Board:**
- Column headers: "$A_i(\omega)$" | "Bode magnitude plot" | "Bode phase plot", with a horizontal rule below. [sure]
- Row "constant $K$". Magnitude: a vertical axis with ticks "$20\log|K|$" (upper) and "0" (lower, on the $\omega$ axis). A green horizontal line sits at the $20\log|K|$ level. Phase: a vertical axis with ticks "0°" (top, on the $\omega$ axis) and "±180°" (lower). One green line lies at 0°, labelled "$K>0$" with an arrow. A second green line lies at ±180°, labelled "$K<0$". [sure]

**Speech vs board:** "it's zero if k is greater than zero, and it's plus or minus a 180 degrees if k is less than zero" [0:45:43]. The speech says "20 times the log of that constant", and the board has $|K|$. **I followed the board.** The magnitude line is drawn above 0 dB, which assumes $|K|>1$. That is a sketch choice, not an error.

---

## p19  f_0179.jpg  [0:46:04 – 0:50:51]
f_0173 (0:48:47) shows the zero-at-origin row in full. f_0179 shows the pole-at-origin row.

**Board:**
- Row "zero @ origin $(j\omega)^N$". Magnitude: vertical ticks 0 and 20N, and $\omega$ ticks **1, 10, 100**. A green straight line passes through dots at $(1, 0)$ and $(10, 20N)$, continues below 0 for $\omega<1$, and is labelled "$20N$ dB/decade". Phase: a flat green line at **90°N**. [sure]
- Row "pole @ origin $\dfrac{1}{(j\omega)^N}$". Magnitude: vertical ticks 0 and $-20N$, and $\omega$ ticks 1, 10, 100. A green line passes through $(1,0)$ and $(10,-20N)$ with the label "$-20N$ dB/decade". Phase: a flat green line at **$-90°N$**. [sure]

**Speech vs board:** "for a zero at the origin, there's no natural frequency scale for it. So we'll just say a frequency of one, 10, a 100" [0:46:57–0:47:10]. "A decade is a factor of 10 change... the slope here is 20 n decibels per decade" [0:47:45–0:48:02]. The examples are the inductor's $j\omega L$ (zero at origin) and the capacitor's $1/j\omega C$ (pole at origin). The phase of $j$ is 90°, so $(j)^N$ gives 90°·N. The speech agrees with the board.

**Re-derived:** $20\log_{10}1=0$ and $20\log_{10}10=20$ ✓.

---

## p20  f_0186.jpg  [0:50:51 – 0:55:12]
f_0180 (0:52:48) shows the simple-zero row mid-construction.

**Board:**
- Row "simple zero @ $\omega_z$: $\left(1+j\dfrac{\omega}{\omega_z}\right)^N$". Magnitude: vertical ticks 0 and 20N, and $\omega$ ticks $\omega_z$, $10\omega_z$. Green: flat at 0 to $\omega_z$, then a line through about $(10\omega_z,20N)$, labelled "$20N$ dB/decade". Phase: vertical ticks 0° and 90°N (dashed), $\omega$ ticks $0.1\omega_z,\ \omega_z,\ 10\omega_z$. Green: 0° to $0.1\omega_z$, a line up to 90°N at $10\omega_z$, then flat. [sure] The 45°N midpoint is not labelled on this table page.
- Row "simple pole @ $\omega_p$: $\dfrac{1}{\left(1+j\dfrac{\omega}{\omega_p}\right)^N}$". Magnitude: ticks 0 and $-20N$; $\omega_p$, $10\omega_p$. Green: 0 to $\omega_p$, then down through about $(10\omega_p,-20N)$, labelled "$-20N$ dB/decade". Phase: ticks 0°, $-90°N$ (dashed); $0.1\omega_p,\ \omega_p,\ 10\omega_p$. Green: 0° to $0.1\omega_p$, down to $-90°N$ at $10\omega_p$, then flat. [sure]

**Speech vs board:** "starting at zero degrees going to minus nine degrees times n" [0:54:30]. **Speech/ASR slip** for ninety; the board says $-90°N$. "the slope here is minus 20 dB... 20 n dB per decade" [0:54:11] is corrected live.

---

## p21  f_0192.jpg  [0:55:12 – 0:57:00]
**Board:**
- "quadratic zero @ $\omega_z$" [sure]
- $\left[1+j2\xi\dfrac{\omega}{\omega_z}+\left(\dfrac{j\omega}{\omega_z}\right)^2\right]^N$ [sure]

**Speech:** a student asks what the letter is. "That's the Greek letter xi... basically just the coefficient of the linear term... It'll typically be related to the resistance." "A little squiggle on the top and then, like, a script e with a little tail on the bottom." Capital Xi is "three horizontal bars". He will use the lowercase [0:56:04–0:56:56]. ASR renders it as "c" at 0:56:22.

---

## p22  f_0269.jpg  [0:57:00 – 1:08:36]
f_0269 itself shows the **top of the table** (constant K, zero @ origin, part of pole @ origin). He scrolled back up at about 1:06:24 to explain additivity. The quadratic rows drawn during this interval are read from **f_0198 (1:02:25)**, **f_0201 (1:03:05)** and **f_0286 (1:08:40, complete)**.

**Board (quadratic zero row, f_0198/f_0201):**
- Circuit: the current source $I$ (circle, arrow **up**) on the left feeds the top wire to the upper output terminal. Between the top and bottom output terminals hangs a vertical series branch: $R$ (top), $L$ (middle), $C$ (bottom). The output voltage is across the terminals. There are no element labels on the board; the speech names them "a resistor, an inductor, and a capacitor all in series" [0:57:31]. [sure]
- Magnitude: vertical ticks 0 and **40N**, and $\omega$ ticks $\omega_z$, $10\omega_z$. Green: flat at 0 to $\omega_z$, then a steep line through about $(10\omega_z, 40N)$, labelled "$40N$ dB/decade". [sure]
- Phase: vertical ticks 0° and **180°N** (dashed), and $\omega$ ticks $0.1\omega_z,\ \omega_z,\ 10\omega_z$. Green: 0° to $0.1\omega_z$, a line up to 180°N at $10\omega_z$, then flat. [sure]

**Board (quadratic pole row, f_0201 + f_0286):**
- "quadratic pole @ $\omega_p$: $\dfrac{1}{\left[1+j2\xi\dfrac{\omega}{\omega_p}+\left(\dfrac{j\omega}{\omega_p}\right)^2\right]^N}$" [sure]
- Circuit: the voltage source (circle with ±) on the left. The top wire carries $R$ then $L$ in series (zig-zag then coil) to the upper output terminal. $C$ is a shunt from the top node to the bottom wire, and the output is across $C$. There are no element labels on the board; the speech names them "a resistor and an inductor and a capacitor" [1:03:33]. [sure]
- Magnitude: the $\omega$ axis at the top at 0, with ticks $\omega_p$, $10\omega_p$. Green: flat at 0 to $\omega_p$, then a steep line down through a dot at about $(10\omega_p,\ \text{lower tick})$, labelled "$-40N$ dB/decade". **The lower vertical tick is labelled "40N" with no minus sign (zoomed crop of f_0286 confirms). [board differs: it should be $-40N$.]**
- Phase: the $\omega$ axis at the top at 0°, with ticks $0.1\omega_p,\ \omega_p,\ 10\omega_p$, and a dashed line at **$-180°N$**. Green: 0° to $0.1\omega_p$, a line down to $-180°N$ at $10\omega_p$, then flat. [sure]

**Speech vs board:**
- Quadratic zero high-frequency limit: "it's this omega squared term that will dominate... omega over omega z to the two n... two n times 20, which is 40 n" [0:59:01–0:59:28]. "It's steeper... than if we had the simple zero" [1:00:34]. Phase: "j to the two n... 90 degrees times two n, which is a 180 degrees times n" [1:01:15–1:01:30]. The speech agrees with the board.
- He first says "this is omega p" while labelling the quadratic-zero axis, then corrects himself: "Sorry. Omega z" [0:58:28–0:58:33]. The board has $\omega_z$.
- "the phase of one or one to the end" [1:01:02] is ASR for "one to the N".
- Quadratic pole magnitude: "it's gonna go from zero, and then the scale here is gonna be 40 n" [1:04:37]. **The speech also lacks the minus.** The slope label on the board, "$-40N$ dB/decade", is correct, and so is the spoken "minus 40 n dB per decade" [1:05:03].
- Additivity [1:06:18–1:08:36]: "the log of this product here will just be the sum of the logs of the individual factors... adding constants... you just increase the level... the slope is just the sum of the slopes of the individual lines... the phases always appear in exponents... the phases just add up."
- Neither board nor speech mentions the dependence on $\xi$ near $\omega_c$ (a resonant peak or dip). The asymptotes drawn do not depend on $\xi$.

**Re-derived (sympy):**
- Series RLC driven by a current: $Z\cdot j\omega C=1+j\omega RC-\omega^2LC=1+j2\xi\frac{\omega}{\omega_0}+\left(\frac{j\omega}{\omega_0}\right)^2$ with $\omega_0=1/\sqrt{LC}$ and $\xi=\frac R2\sqrt{C/L}$. So $V=I\cdot\frac{1}{j\omega C}\cdot[\text{quadratic}]$: a quadratic zero times a pole at the origin (and constant $1/C$). The speech says "if you multiply through by j omega c" [0:57:51]. ✓
- RLC with output across $C$: $V_o/V_s=1/(1-\omega^2LC+j\omega RC)$, a pure quadratic pole with the same $\omega_0$ and $\xi$. ✓
- The quadratic factor at $\omega=\omega_0$ equals $j2\xi$. Its phase is exactly 90° (per order) for any $\xi$, consistent with the line passing 90°N at $\omega_c$. Its magnitude is $20\log(2\xi)$, which is 0 dB only for $\xi=0.5$: −13.98 dB for $\xi=0.1$, +6.02 dB for $\xi=1$. This is mine, not stated in lecture.
- $20\log_{10}(10^2)=40$ ✓.

## p23  f_0278.jpg  [1:08:36 – 1:08:38] and p24  f_0286.jpg  [1:08:38 – 1:08:40]
Scroll states while he scrolls down through the completed table: p23 shows the pole @ origin, simple zero and simple pole rows; p24 shows both quadratic rows. They contain no new ink beyond p18–p22. f_0286 is the best frame of the quadratic rows (described under p22). [sure]

---

## p25  f_0302.jpg  [1:08:40 – 1:09:35]
**Board:** "Bode plots for each factor $A_i(\omega)$ in $H(\omega)$ can be added to each other to obtain the Bode plots for $H(\omega)$." [sure]
**Speech:** "So that's kind of the machinery of transfer functions and Bode plots" [1:09:33]. The speech agrees. **No worked combined (multi-factor) example in this lecture.**

---

## p26  f_0315.jpg  [1:09:35 – 1:12:44]
f_0304 (1:12:00) shows the heading, and f_0313 (1:12:17) shows the definitions.

**Board:**
- "**Passive Filter Circuits**" (underlined heading) [sure]
- "Reading: Ulaby et al, Secs. 9-4, 9-5." [sure]
- "**Passive** filters are filter circuits that contain only passive elements (R, L, C) plus input signals" [sure]
- "**Active** filters contain op amps, transistors, or other active devices." [sure]
- "**Example**: band pass filter." [sure]

**Speech:** "there will be some active source to drive the circuit, but in the filter, you get the filter functionality only from passive components". Active devices are ones "that can give you gain... we'll see when we start talking about that why it's useful to have that" [1:10:26–1:12:18]. The speech agrees with the board.

---

## p27  f_0321.jpg  [1:12:44 – 1:16:48]
f_0316 (1:14:20) shows the circuit.

**Diagram (f_0316):** under "Example: band pass filter.", the source $V_s$ (circle, ± with + on top) is on the left. The top wire runs left to right through $L$ (coil, labelled L) and then $C$ (labelled C) to a node, which continues to the + output terminal. $R$ is a vertical shunt from that node to the bottom wire. The output $V_R$ is across $R$, + on top and − on the bottom terminal. The bottom wire returns to the source. [sure]

**Board:**
- "By voltage division:" [sure]
- $V_R=\dfrac{Z_R}{Z_R+Z_L+Z_C}V_s=\dfrac{R}{R+j\omega L+\frac{1}{j\omega C}}V_s$ [sure]
- $\Rightarrow H(\omega)=\dfrac{V_R}{V_s}=\dfrac{R}{R+j\omega L+\frac{1}{j\omega C}}\left(\dfrac{j\omega C}{j\omega C}\right)=\dfrac{j\omega RC}{1-\omega^2LC+j\omega RC}$ (the $j\omega C/j\omega C$ factor in green) [sure]

**Speech vs board:** the qualitative argument [1:13:28–1:14:18]. At low $\omega$, "the impedance of the capacitor will be very high, much higher than the impedance of the resistor. So the output voltage will be very low." At high $\omega$, "the impedance of the inductor will be very high", so the output is low again. "In between, there will be some frequency where the impedance of the inductor and the capacitor will cancel each other out... essentially all of the input signal appearing across the resistor." Reading $H$: "we're gonna get a quadratic pole due to this factor in the denominator, and we're going to get a zero at the origin, right, plus some constant" [1:16:08–1:16:18]. "using current, voltage division" [1:14:27] is a self-correction to voltage division. The speech agrees with the board.

**Re-derived (sympy):** $\dfrac{R}{R+j\omega L+1/j\omega C}=\dfrac{j\omega RC}{1-\omega^2LC+j\omega RC}$ ✓. At $\omega=1/\sqrt{LC}$, $H=1$ (mine).

> [!warning] Related to PS8 9.26 (series RLC bandpass parameters). This is the lecture's general symbolic derivation, not the graded problem. Do not extend it into 9.26's numbers.

---

## p28  f_0325.jpg  [1:16:48 – 1:17:07] and p29  f_0330.jpg  [1:17:07 – 1:17:16]
**Board:** the same equation line followed by a green factor [sure]:
$$\cdot\left(\dfrac{1-\omega^2LC-j\omega RC}{1-\omega^2LC-j\omega RC}\right)$$
(multiply by the complex conjugate of the denominator over itself.)

**Speech-only continuation [1:17:16–1:17:46], frames end at 1:17:16** [likely: speech only]:
$$H(\omega)=\frac{\omega^2R^2C^2+j\omega RC\,(1-\omega^2LC)}{(1-\omega^2LC)^2+\omega^2R^2C^2}$$
"in the denominator, we're just gonna get the magnitude squared of the denominator, which is the real part squared plus the imaginary part squared" [1:17:29]. "We can take the transfer function and think about it either in this form or in this form" [1:17:50].

**Preview [1:17:57–1:18:24]:** "starting next time on Monday... we will look at the magnitude and phase of this transfer function... bandwidth and quality factor... for filter circuits specifically and for frequency dependent circuits more generally." ASR renders these as "quality and factor" and "filter surface".

**Re-derived (sympy):** $j\omega RC(1-\omega^2LC-j\omega RC)=\omega^2R^2C^2+j\omega RC(1-\omega^2LC)$. Denominator $(1-\omega^2LC)^2+(\omega RC)^2$. Both match the spoken result ✓.
