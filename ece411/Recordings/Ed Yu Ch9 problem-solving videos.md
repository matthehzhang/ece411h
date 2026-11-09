---
course: ECE 411H
kind: instructor-intel
instructor: Prof. Ed Yu
unit: exam2
exam: Semester Exam 2, Wed 2026-11-11 (70 min, closed book, 4 x 25 pts)
sources:
  - Transcripts/Problem Solving Videos/Ulaby_9.4.md, Ulaby_9.19.md, Ulaby_9.33.md, Ulaby_9.37.md
  - Transcripts/Problem Solving Videos/deepgram/Ulaby_9.{4,19,33,37}.deepgram.md (timestamps)
  - Transcripts/Refreshers/cascaded_filters_notes_F26.md
  - _sources_transcribed/Problem Solving Videos/Ulaby 9.{19,33,37}.pdf (figures cross-checked)
verified: every number recomputed with python3 (numpy/scipy) on 2026-11-06
tags: [ece411, exam2, bode-plots, filters, op-amp-filter, rlc-filter, resonance, instructor-intel]
---

# Ed Yu Ch9 problem-solving videos (9.4, 9.19, 9.33, 9.37) + cascaded-filters notes

This note collects what Prof. Yu's own Chapter 9 videos and his 2026-11-02 cascaded-filters notes show about **how he builds Bode plots, writes $\mathbf H(\omega)$, and checks answers**. It is mapped onto the Exam 2 format: P1 conceptual, P2 design/analysis, P3 filter $\mathbf H$ + cutoff + Bode, P4 active or RLC filter.

- Timestamps are `[mm:ss]` into the video audio (Deepgram file), `[h:mm:ss]` past one hour. Video files: `Problem Solving Videos/Ulaby <n> video.mp4`.
- His spoken statements are given as **close paraphrases** with timestamps. One short verbatim quote is marked as such.
- "SL" means the straight-line (asymptotic) approximation. "Exact" means $|\mathbf H|$ and $\angle\mathbf H$ evaluated numerically.
- PS8 (9.26, 9.38, 9.39, 9.42, m9.2, 12.2) and Lab 5 are **not** solved here. 9.37 below is a close relative of PS8 9.38. Nothing in this note works 9.38.

---

## Exam intel

**How he presents a Bode plot (all four 9.19 parts, 9.33, 9.37)**

- Two separate plots, magnitude above phase. The frequency axes are aligned, with vertical dashed guide lines dropped through both plots at every key frequency. He comments that a graph-paper background would have helped (9.19 [47:19]).
- Magnitude axis label: $M(\omega)\,[\text{dB}]$. Phase axis label: $\phi$ or $\phi(\omega)$, with ticks at multiples of $90^\circ$. The $\omega$ axis is logarithmic. He points out that $\omega = 0$ cannot appear on the axis (9.19 [41:07], [1:04:45]).
- He ticks **every pole and zero frequency** on the magnitude axis. On the phase axis he **also** ticks $\omega_{p,z}/10$ and $10\,\omega_{p,z}$ for each one (9.19 [13:38], key point at [30:08]).
- **Every non-zero slope is labelled**, e.g. "−20 dB/dec." or "−45°/dec". In 9.19(a) he also labels a flat phase segment "0°/dec" so that it cannot be misread (9.19 [21:06]).
- He labels the dB level of the **anchor** segment: 23.5, −15.9, −26, 60 (9.19), 0 and 20 (9.33), 14 (9.37), and the end values of the phase (−180°, 0°).
  - He does **not** write the dB value at every breakpoint. For example, the 9.54 dB plateau in 9.19(a) and the −35.9 dB minimum in 9.19(b) are left unlabelled.
  - Past exams require "label key values on both axes", so on the exam you must add these values. The tables in [[#Problems worked]] list them.
- Colour scheme (useful for your own scratch work): each factor's phase contribution is drawn as a blue dashed ramp, and the total is drawn solid green (9.19 [14:42], [19:20]).

**Standard form**

- First step, every time: put $\mathbf H$ in the standard form from class or Ulaby. That means an overall constant in front, and every pole and zero factor written with a leading term of **1** (9.19 [26:05]–[26:26]; written key point (i) on the slide).
- He collects all the pulled-out constants in a dashed box and evaluates the box to a single number $K$ (15, 20, 1/20, 1/10).
- He then lists the poles and zeros with their order: "simple zero at ω = 10", "3rd order pole at ω = 0", "quadratic pole at ω = 4" (written key point (ii)).

**Sanity checks he always does**

- Before plotting, he computes the four limits $M(0)$, $M(\infty)$, $\phi(0)$, $\phi(\infty)$ (every part of 9.19, plus 9.33 and 9.37). After plotting, he checks that both ends of the plot agree with them (9.19 [19:20], [29:32], [32:52]; written key points (iii) and (iv)).
- If $\phi(\infty)$ is the phase of $-1$, he writes "$\pm180^\circ$" and decides the sign later, from the plot. He says the sign depends on how the phase approaches infinity and that the plot will settle it (9.19 [07:08]).
  - 9.33 uses the same logic: the phase is $-90^\circ$ at $\omega_c$, so the high-frequency limit must be $-180^\circ$, not $+180^\circ$ ([13:56]).
- After deriving $\mathbf H$ from a circuit, he re-derives the limits from the circuit itself (9.37 [25:23]–[29:09]):
  - At low frequency the capacitor is an open circuit, so the stage is a follower with $\mathbf V_o = \mathbf V_s$ (0 dB).
  - At high frequency the capacitor is a short, so the stage is a plain non-inverting amplifier with gain $(R_1+R_2)/R_1$.
  - He calls this kind of limit check "quite useful and important" for validating a result. If a limit comes out wrong, recheck either the algebra or your intuition about the circuit (9.37 [29:09]).
- Even when $\phi(0) = \phi(\infty) = 0$, the phase in between need not be zero (9.37 [13:41]).

**How he shows work for a circuit problem (9.4, 9.33, 9.37)**

1. Redraw the circuit and label phasors and element values. He says "as usual" each time (9.4 [00:03], 9.33 [01:20], 9.37 [01:02]).
2. Write one KCL equation:
   - at the output node, with the bottom rail as reference (9.33 [03:00]); or
   - at the op-amp inverting input, which the ideal-op-amp rule holds at $\mathbf V_s$ (9.37 [02:52]).
3. Group the terms by variable. Multiply through by a factor chosen to clear the nested fractions ($j\omega L$ in 9.33; $R_2/(j\omega C)$ in 9.37).
4. Solve for $\mathbf V_o/\mathbf V_i$, **box** $\mathbf H(\omega)$, then rewrite it in standard form with the corner frequencies named ($\omega_c$, $\omega_{c1}$, $\omega_{c2}$).
5. Substitute numbers. State $M$ in dB using $20\log_{10}$. He corrects himself out loud when he says "natural log" (9.19 [1:18:49]).
6. Finish with a short written "Key points" list (on the slide at the end of every video).

---

## His Bode-plot procedure

Reconstructed from 9.19 (all four parts plus the two written key-point lists) and 9.33, with 9.37 as a confirming example.

1. **Standard form.**
   $$\mathbf H(\omega)=K\,(j\omega)^{\pm N}\,\frac{\prod_i\left(1+\dfrac{j\omega}{\omega_{z,i}}\right)^{n_i}\ \prod\left[1+j2\zeta\dfrac{\omega}{\omega_0}+\left(\dfrac{j\omega}{\omega_0}\right)^2\right]}{\prod_k\left(1+\dfrac{j\omega}{\omega_{p,k}}\right)^{m_k}\ \prod\left[\cdots\right]}$$
   - Pull the constant out of each factor, **including powers**: $(100+j2\omega)^2 \to 100^2(1+j\omega/50)^2$ and $(200+j2\omega)^3 \to 200^3(1+j\omega/100)^3$.
   - Convert coefficients into corner frequencies: $1+j0.2\omega = 1+j\omega/5$.
   - For a quadratic, the corner $\omega_0$ comes from the $\omega^2$ term: $16-\omega^2+j4\omega = 16\left[1+j\omega/4+(j\omega/4)^2\right]$, so $\omega_0 = 4$.
   - Multiply the boxed constants together to get $K$.
2. **List the poles and zeros** with their orders, including any at the origin.
3. **Compute the limits** $M(0)$, $M(\infty)$, $\phi(0)$, $\phi(\infty)$.
   - In each limit, every $(1+j\omega/\omega_c)$ factor becomes either $1$ or $j\omega/\omega_c$.
   - Convert magnitudes with $20\log_{10}$. Example from 9.19(a): $M(0) = 20\log 15 = 23.5$ dB.
   - If a limit is the phase of $-1$, write $\pm180^\circ$ and decide the sign from continuity of the plot.
4. **Magnitude axes.** Tick each pole and zero frequency and draw a dashed vertical through it. Mark the anchor level in dB on the vertical axis.
5. **Anchor the magnitude** on a segment where $M$ is a known constant. Use the first of these that exists:
   - $M(0)$, if it is finite and non-zero (9.19a: 23.5 dB; 9.33: 0 dB; 9.37: 0 dB);
   - otherwise $M(\infty)$ (9.19b: −15.9 dB; 9.19d: 60 dB);
   - otherwise a mid band where the $\omega$-dependence cancels (9.19c: on $1\le\omega\le4$, $M = 20\log(1/20) = -26$ dB).

   He states this as a rule: it is easier to start from a known constant, and the same applies to the phase (9.19 [55:03]–[56:32]).
6. **Walk the intervals between breakpoints.**
   - In each interval, replace every factor below its corner by $1$ and every factor above its corner by $j\omega/\omega_c$.
   - Count the net power $n$ of $\omega$. The slope is $20n$ dB/dec.
   - The slope changes **abruptly, exactly at each corner**. He describes it as a sudden switch from the low-frequency limit to the high-frequency limit at each pole or zero frequency (9.19 [27:15]–[28:22]).
   - Contributions add on the dB scale because $\log(ab) = \log a + \log b$ (9.19 [28:51]).

   Magnitude contribution of each factor type:

   | factor | magnitude (dB) | break at |
   |---|---|---|
   | constant $K$ | flat at $20\log_{10}\lvert K\rvert$ | — |
   | $(j\omega)^{\pm N}$ (pole or zero at origin) | slope $\pm 20N$ dB/dec at **all** $\omega$, no break | — |
   | $(1+j\omega/\omega_c)^{\pm n}$ | 0 dB below $\omega_c$, $\pm20n$ dB/dec above | $\omega_c$ exactly |
   | quadratic $[1+j2\zeta\omega/\omega_0+(j\omega/\omega_0)^2]^{\pm1}$ | 0 dB below $\omega_0$, $\pm40$ dB/dec above | $\omega_0$ exactly |
   | $\omega^2$ written as a real number (9.19d) | +40 dB/dec at all $\omega$ | — |

7. **Underdamped quadratic: compute the corner value directly** and draw the peak. In 9.33 he evaluates $\mathbf H(\omega_c) = 10/j$, so $M(\omega_c) = 20\log 10 = 20$ dB, and draws a spike to 20 dB at $\omega_c$ on top of the 0 dB / −40 dB/dec asymptotes (9.33 [08:06]–[11:55]).
   - In general $M(\omega_0) = 20\log_{10}\dfrac{1}{2\zeta} = 20\log_{10}Q$ for a quadratic pole.
   - In 9.19(c) $\zeta = 0.5$, which gives 0 dB, so no peak. He does not discuss $\zeta$ there.
8. **Phase axes.** Ticks at multiples of $90^\circ$. On the frequency axis, tick every $\omega_{p,z}$ **and** $\omega_{p,z}/10$ and $10\,\omega_{p,z}$.
9. **Draw each factor's phase ramp** (blue dashed):
   - It is $0^\circ$ for $\omega < \omega_c/10$.
   - It reaches its full value for $\omega > 10\,\omega_c$.
   - In between it is linear in $\log\omega$. That is two decades, so the slope is half the total change per decade (9.19 [30:54]–[31:57]).

   Phase contribution of each factor type:

   | factor | phase | slope between $\omega_c/10$ and $10\omega_c$ | value at $\omega_c$ |
   |---|---|---|---|
   | $K>0$ | $0^\circ$ | — | — |
   | $(j\omega)^{\pm N}$ | constant $\pm90N^\circ$, **no ramp** (9.19 [51:25]–[51:41]) | — | — |
   | $(1+j\omega/\omega_c)^{\pm n}$ | $0 \to \pm90n^\circ$ | $\pm45n^\circ$/dec | $\pm45n^\circ$ |
   | quadratic, $\pm1$ power | $0 \to \pm180^\circ$ | $\pm90^\circ$/dec | $\pm90^\circ$ |
   | real $\omega^2$ | $0^\circ$ (9.19 [1:27:07]) | — | — |

   - Examples of combined orders: a third-order pole gives $-270^\circ$ over two decades, i.e. $-135^\circ$/dec (9.19d). A double zero gives $+90^\circ$/dec (9.19b).
   - Outside its ramp, each contribution stays flat at its nearest end value. He does not draw those flat parts, because they do not change the slope (9.19 [18:49], [32:22]).
10. **Sum to get the total** (green):
    - Start at $\phi(0)$, which includes the constant from any $(j\omega)^{\pm N}$ factor.
    - In each interval between consecutive marks (corners, $/10$ points, $\times10$ points), add the slopes of the ramps that are active there.
    - Label each segment's slope, including $0^\circ$/dec.
    - Confirm that the final value equals $\phi(\infty)$ and that the $\pm180^\circ$ choice from step 3 is consistent.
11. **Phase range.** His video rule: if the phase leaves $[-360^\circ, +360^\circ]$, translate it by $360^\circ$ back toward $0^\circ$. In 9.19(b) the phase reaches $+360^\circ$ at $\omega = 50$ and is redrawn from $0^\circ$ (written additional key point (ii); [53:26], [56:32]–[57:50]).
    > [!warning] Exam rule is tighter
    > Past exams say "phase in −180..180". Wrap whenever the curve crosses $\pm180^\circ$. Plotted on the exam, 9.19(b) as he drew it (values up to 360°) would violate that instruction. The exam-compliant version is in [[#9.19(b)]].
12. **Check against the circuit** for circuit problems: inductor or capacitor open or short at DC and at high frequency (9.37). Then read off the filter type and the maximum gain from the plot (9.37 (c)).

**What his procedure does NOT include** (relevant to "3 dB at the corner" and "negative K"):

- **No ±3 dB corner correction** in any of the four videos. His straight-line magnitude has a sharp corner, exactly as on his slides. The only "3 dB" in these sources is in the cascaded notes, where it labels the −3 dB band edges and the design condition $M = 1/\sqrt2$.
  - Standard facts you can use as checks, though he does not draw them: a simple factor is off its asymptote by $20\log\sqrt2 = 3.01$ dB at $\omega_c$, and its exact phase is $\pm45^\circ$ at $\omega_c$. The straight-line phase is off by at most $5.7^\circ$ at $\omega_c/10$ and at $10\omega_c$.
- **No negative-$K$ example.** Every $K$ in these videos is positive: 15, 20, 1/20, 1/10, 1, 1.
  - In the cascaded notes, the two inverting stages' minus signs cancel, giving $K = +80$. The band-reject design has overall gain $-50$, but no phase plot is drawn.
  - Inferred rule, consistent with his $\pm180^\circ$ handling and the exam range: a negative $K$ adds a constant $\pm180^\circ$. Pick the sign that keeps the whole curve inside $[-180^\circ, 180^\circ]$. This is **not** demonstrated in his videos.
- **Pole or zero at the origin, magnitude.** He never anchors it as "0 dB at $\omega = 1$". He always anchors on a constant segment (step 5) and lets the $\pm20N$ dB/dec slope run toward $\omega\to0$ (9.19b, 9.19c).

---

## Problems worked

### Ulaby 9.4: resonant frequency of $R \parallel (L + C)$ (11.0 min)

**Statement.** Find the resonant frequency of the circuit with $R = 1$ kΩ, $L = 10$ mH, $C = 10$ nF. "Resonant" means the frequency at which the input impedance $\tilde Z_i$ is purely real (9.4 [01:21]–[01:42]).

**Circuit.** Two input terminals. $R$ is connected directly across them. In parallel with $R$ is a series branch: $L$ in the top rail, then $C$ down to the bottom rail.

**His method.**
1. Use product-over-sum for the parallel combination:
   $$\tilde Z_i = \frac{R\left(j\omega L + \frac{1}{j\omega C}\right)}{R + j\omega L + \frac{1}{j\omega C}}$$
2. Multiply top and bottom by $j\omega C$:
   $$\tilde Z_i = \frac{R(1-\omega^2LC)}{1-\omega^2LC+j\omega RC}$$
3. Multiply by the complex conjugate of the denominator to get rectangular form:
   $$\tilde Z_i = \frac{R(1-\omega^2LC)^2 - j\omega R^2C(1-\omega^2LC)}{(1-\omega^2LC)^2+\omega^2R^2C^2}$$
4. Set $\operatorname{Im}\tilde Z_i = 0$. This requires $1 - \omega^2LC = 0$, so $\omega_0 = 1/\sqrt{LC} = 10^5$ rad/s (boxed).

**Key point.** At $\omega_0$ the series $L$–$C$ branch has zero impedance and shorts the terminals. So $\tilde Z_i = 0$: the real part is zero too, because of the $(1-\omega^2LC)^2$ factor. A small voltage drives a very large current, which he calls the hallmark of resonance ([07:47]–[10:54]).

**Verified.**
- $\omega_0 = 1.000\times10^5$ rad/s.
- The rationalized $\tilde Z_i$ matches the direct parallel formula at $3\times10^4$, $0.999\times10^5$ and $2\times10^5$ rad/s.
- $\tilde Z_i(\omega_0) \to 0$.

**Exam slot.** P1 (definition of resonance, physical interpretation) or a P2 warm-up.

> [!note]
> $\omega = 1/\sqrt{LC}$ makes $\operatorname{Im}\tilde Z_i = 0$ only because $\tilde Z_i$ itself vanishes there. With this topology there is no other real-impedance frequency except $\omega \to 0$ and $\omega \to \infty$. Do not assume "purely real" always means "$\tilde Z_i = R$".

### Ulaby 9.19: straight-line Bode plots from four transfer functions (92.6 min)

**Statement.** Generate Bode magnitude and phase plots (straight-line approximations) for:
- (a) $\dfrac{4\times10^4(60+j6\omega)}{(4+j2\omega)(100+j2\omega)(400+j4\omega)}$
- (b) $\dfrac{(1+j0.2\omega)^2(100+j2\omega)^2}{(j\omega)^3(500+j\omega)}$
- (c) $\dfrac{8\times10^{-2}(10+j10\omega)}{j\omega(16-\omega^2+j4\omega)}$
- (d) $\dfrac{4\times10^4\omega^2(100-\omega^2+j50\omega)}{(5+j5\omega)(200+j2\omega)^3}$

Exam slot: **P3** (and the Bode half of P4). This video is the canonical procedure.

#### 9.19(a)

$$\mathbf H = 15\,\frac{1+j\omega/10}{(1+j\omega/2)(1+j\omega/50)(1+j\omega/100)}$$

- Zero at 10. Poles at 2, 50, 100.
- $M(0) = 20\log15 = 23.52$ dB. $M(\infty) = -\infty$ dB, since $\mathbf H \sim 1/\omega^2$.
- $\phi(0) = 0^\circ$. $\phi(\infty) = \pm180^\circ$; the plot settles it as $-180^\circ$.
- Magnitude slopes: 0 until 2; −20 dB/dec from 2 to 10; 0 from 10 to 50; −20 from 50 to 100; −40 beyond 100.
- Phase slopes (°/dec): 0 below 0.2; −45 on 0.2–1; 0 on 1–5; −45 on 5–10; −90 on 10–20; −45 on 20–100; −90 on 100–500; −45 on 500–1000; flat at −180° beyond.

| ω (rad/s) | 0.2 | 1 | 2 | 5 | 10 | 20 | 50 | 100 | 500 | 1000 |
|---|---|---|---|---|---|---|---|---|---|---|
| SL $M$ (dB) | 23.52 | 23.52 | 23.52 | 15.56 | **9.54** | 9.54 | 9.54 | **3.52** | −24.44 | −36.48 |
| exact $M$ | 23.48 | 22.59 | 20.67 | 15.83 | 12.17 | 9.65 | 5.73 | −0.42 | −24.65 | −36.53 |
| SL $\phi$ (°) | 0 | **−31.5** | −31.5 | −31.5 | **−45.0** | **−72.1** | −90.0 | **−103.6** | **−166.5** | −180 |
| exact $\phi$ | −4.9 | −22.6 | −37.1 | −50.2 | −50.7 | −54.0 | −80.6 | −113.0 | −163.9 | −171.9 |

- The SL magnitude crosses 0 dB at $\omega = 122.5$ rad/s.
- The bold values are ones he does not write but the exam's "label key values" requires.

#### 9.19(b)

$$\mathbf H = 20\,\frac{(1+j\omega/5)^2(1+j\omega/50)^2}{(j\omega)^3(1+j\omega/500)}$$

- Double zeros at 5 and 50. Triple pole at 0. Simple pole at 500.
- $M(0) = \infty$.
- $M(\infty) = 20\log\dfrac{20\cdot500}{5^2\cdot50^2} = 20\log 0.16 = -15.92$ dB.
- $\phi(0) = +90^\circ$, because $1/j^3 = j$. $\phi(\infty) = 0^\circ$.
- He builds the magnitude **from high frequency down**: flat at −15.9 dB above 500; +20 dB/dec on 50–500; −20 on 5–50; −60 below 5.
- He builds the phase from $+90^\circ$: +90°/dec on 0.5–5; +180°/dec on 5–50 (reaches 360°); **drop to 0°**; +45°/dec on 50–500; −45°/dec on 500–5000; then flat at 0°.

| ω | 0.5 | 1 | 5 | 50 | 500 | 5000 |
|---|---|---|---|---|---|---|
| SL $M$ (dB) | **44.08** | **26.02** | −15.92 | **−35.92** | −15.92 | −15.92 |
| exact $M$ | 44.17 | 26.36 | −9.81 | −29.85 | −18.84 | −15.96 |
| SL $\phi$, his drawing | 90 | 117.1 | 180 | 360 → 0 | 45 | 0 |
| SL $\phi$, wrapped to [−180, 180] | 90 | 117.1 | 180 → **−180** | 0 | 45 | 0 |
| exact $\phi$ (principal value) | 102.5 | 114.8 | −169.2 | −17.1 | 32.4 | 4.5 |

- The SL magnitude crosses 0 dB at $\omega = 2.71$.
- Exam-compliant phase: run $90^\circ \to 180^\circ$ over 0.5–5, then jump to $-180^\circ$ at $\omega = 5$. Continue at $+180^\circ$/dec to $0^\circ$ at 50, then $+45^\circ$ at 500, then $0^\circ$ at 5000. This is the same curve shifted by $-360^\circ$ on 5–50, with no jump at 50.

#### 9.19(c)

$$\mathbf H = \frac{1}{20}\,\frac{1+j\omega}{j\omega\left[1+j\omega/4+(j\omega/4)^2\right]}$$

- Zero at 1. Pole at 0. Quadratic pole at $\omega_0 = 4$.
- $M(0) = \infty$ and $M(\infty) = -\infty$, so neither limit anchors the plot. He anchors on the mid band instead: for $1 \le \omega \le 4$, $M \approx 20\log(1/20) = -26.02$ dB ([1:01:16]–[1:02:44]).
- $\phi(0) = -90^\circ$. $\phi(\infty) = \pm180^\circ$, settled by the plot as $-180^\circ$.
- Magnitude slopes: −20 dB/dec below 1; flat on 1–4; −40 above 4.
- Phase slopes (°/dec): +45 on 0.1–0.4; −45 on 0.4–10; −90 on 10–40; flat at −180° beyond.
- He explains why the quadratic is at $-90^\circ$ at $\omega = 4$: there $(j\omega/4)^2 = -1$ cancels the 1, leaving $1/j$ ([1:11:08]).

| ω | 0.1 | 0.4 | 1 | 4 | 10 | 40 |
|---|---|---|---|---|---|---|
| SL $M$ (dB) | **−6.02** | −18.06 | −26.02 | −26.02 | **−41.94** | **−66.02** |
| exact $M$ | −5.97 | −17.37 | −22.75 | −25.76 | −41.27 | −65.97 |
| SL $\phi$ (°) | −90 | **−62.9** | −80.8 | **−107.9** | **−125.8** | −180 |
| exact $\phi$ | −85.7 | −74.0 | −59.9 | −104.0 | −160.3 | −175.7 |

- The quadratic has $\zeta = 4/(2\cdot4) = 0.5$, so $|1/(2\zeta)| = 1$: no peak (0 dB correction at $\omega_0$).
- The SL magnitude crosses 0 dB at $\omega = 0.05$.

#### 9.19(d)

$$\mathbf H = \frac{1}{10}\,\frac{\omega^2\left[1+j\omega/2+(j\omega/10)^2\right]}{(1+j\omega)(1+j\omega/100)^3}$$

- Double zero at 0 (written as the real $\omega^2$). Quadratic zero at 10. Pole at 1. Triple pole at 100.
- $M(0) = -\infty$.
- $M(\infty) = 20\log\left[\tfrac{1}{10}\cdot\tfrac{1}{100}\cdot100^3\right] = 60$ dB.
- $\phi(0) = 0^\circ$, because $\omega^2$ is real and positive. $\phi(\infty) = \pm180^\circ$, settled as $-180^\circ$.
- Magnitude, from high frequency down: flat at 60 dB above 100; +60 dB/dec on 10–100; +20 on 1–10; +40 below 1.
- Phase slopes (°/dec): −45 on 0.1–1; +45 on 1–10; −45 on 10–100; −135 on 100–1000; flat at −180° beyond.

| ω | 0.1 | 1 | 10 | 100 | 1000 |
|---|---|---|---|---|---|
| SL $M$ (dB) | −60 | −20 | 0 | 60 | 60 |
| exact $M$ | −60.03 | −22.11 | **13.81** | **51.87** | 59.88 |
| SL $\phi$ (°) | 0 | −45 | 0 | −45 | −180 |
| exact $\phi$ | −3.0 | −19.9 | −11.4 | −71.2 | −165.7 |

> [!warning] 9.19(d): the "quadratic zero at 10" is overdamped
> $100-\omega^2+j50\omega$ has $\omega_0 = 10$ and $2\zeta/\omega_0 = 1/2$, so $\zeta = 2.5 > 1$. It factors into two **real** zeros: $100(1+j\omega/2.087)(1+j\omega/47.91)$, where $2.087\times47.91 = 100$ and $2.087 + 47.91 = 50$.
> - Treating it as a double break at 10, as both the problem framing and his solution do, leaves the SL magnitude **13.8 dB low at ω = 10**. The 8.1 dB gap at ω = 100 is the ordinary triple-pole corner rounding and is present either way.
> - The SL phase is off by up to 28.6°, against 15.6° for the real-zero SL.
> - The correct SL magnitude uses breaks at 1, 2.09, 47.9 and 100. The slopes are then +40, +20, +40, +60, 0 dB/dec, through −20 dB at 1, −13.6 dB at 2.09, +13.6 dB at 10, +40.8 dB at 47.9, and 60 dB at 100.
> - For the exam: **check $\zeta$ = (linear coefficient)/(2ω₀) for any quadratic. If ζ ≥ 1, factor it into real corners.** If a problem explicitly says "quadratic", follow his method and state the assumption.

### Ulaby 9.33: series-L, shunt C ∥ R low-pass (17.6 min)

**Statement.**
- (a) Find $\mathbf H = \mathbf V_o/\mathbf V_i$ in standard form.
- (b) Draw spectral (Bode, straight-line) plots for $R = 100$ Ω, $L = 0.1$ mH, $C = 1$ μF.
- (c) Find $\omega_c$ and the magnitude slope for $\omega \gg \omega_c$.

**Circuit.** $\mathbf V_i$ (+ on top) on the left. $L$ runs in the top rail to the output node. From that node $C$ goes to ground and, beside it, $R$ goes to ground. $\mathbf V_o$ is taken across $R$, and the bottom rail is the reference.

**His method.**
1. KCL at the output node:
   $$\frac{\mathbf V_o-\mathbf V_i}{j\omega L} + j\omega C\,\mathbf V_o + \frac{\mathbf V_o}{R} = 0$$
2. Multiply by $j\omega L$:
   $$(1 + j\omega L/R - \omega^2LC)\,\mathbf V_o = \mathbf V_i$$
3. Boxed result:
   $$\mathbf H = \frac{1}{1 + j\omega L/R + (j\omega/\omega_c)^2},\qquad \omega_c = 1/\sqrt{LC}$$
   ([03:00]–[07:24])

**Answers and verification.**
- $\omega_c = 1/\sqrt{10^{-4}\cdot10^{-6}} = 10^5$ rad/s. ✓
- $\mathbf H(\omega_c) = 1/(1 + j\cdot0.1 - 1) = 10/j$, so $M(\omega_c) = 20$ dB and $\phi(\omega_c) = -90^\circ$. ✓
- $M(0) = 0$ dB. $\phi(0) = 0^\circ$. $\phi(\infty) = -180^\circ$.
- Phase SL: $0^\circ$ up to $10^4$, a straight line through $-90^\circ$ at $10^5$, reaching $-180^\circ$ at $10^6$.
- (c) The slope is −40 dB/dec, because $\mathbf H \approx 1/(-\omega^2LC)$: ten times the frequency divides $\mathbf H$ by 100, which is −40 dB ([16:26]–[17:22]). The exact $M(10^7) - M(10^6) = -40.09$ dB ✓.
- He does not compute these, but they are verified: $\zeta = \omega_cL/(2R) = 0.05$ and $Q = R\sqrt{C/L} = 10$. The exact peak is 20.01 dB at $0.9975\,\omega_c$.

| ω (rad/s) | 1e4 | 5e4 | 8e4 | 1e5 | 2e5 | 1e6 |
|---|---|---|---|---|---|---|
| his plot $M$ (dB) | 0 | 0 | 0 | 20 (computed peak) | −12.0 | −40 |
| exact $M$ | 0.09 | 2.48 | 8.66 | 20.00 | −9.56 | −39.91 |
| SL $\phi$ (°) | 0 | −62.9 | −81.3 | −90 | −117.1 | −180 |
| exact $\phi$ | −0.6 | −3.8 | −12.5 | −90.0 | −176.2 | −179.4 |

> [!warning] 9.33: "cutoff" here is the corner (resonant) frequency, not a −3 dB point
> His $\omega_c = 1/\sqrt{LC}$ is the corner of the quadratic pole, and it is what the Bode construction needs. With $Q = 10$, $|\mathbf H|$ there is **+20 dB, not −3 dB**.
> - The −3 dB point relative to the DC gain is at $1.551\times10^5$ rad/s ($1.55\,\omega_c$).
> - $|\mathbf H|$ returns to 0 dB at $1.411\times10^5$ rad/s.
> - Applying the half-power rule relative to the peak ($M_{max}/\sqrt2$) gives a band of $0.946$–$1.046\times10^5$ rad/s around the peak. That is meaningless as a low-pass cutoff.
>
> If an exam asks for a "−3 dB cutoff" of an underdamped second-order filter, say which definition you are using. To match his answer, give $\omega_c = 1/\sqrt{LC}$.

> [!warning] 9.33: straight-line phase is crude for high Q
> The two-decade ramp puts $-62.9^\circ$ at $5\times10^4$ rad/s, but the exact phase is $-3.8^\circ$. With $\zeta = 0.05$ the real phase is almost a step at $\omega_c$. Draw the ramp because it is "as done in class", but do not use it to read off values.

**Exam slot.** P4 (RLC filter: $\mathbf H$ in standard form, type = low-pass, Bode) and P3 (cutoff + Bode).

### Ulaby 9.37: op-amp high-pass (non-inverting, $R_1$–$C$ to ground) (30.5 min)

**Statement.**
- (a) Find $\mathbf H = \mathbf V_o/\mathbf V_s$ in standard form.
- (b) Draw spectral plots for $R_1 = 1$ kΩ, $R_2 = 4$ kΩ, $C = 1$ μF.
- (c) What type of filter is it, and what is its maximum gain?

**Circuit.**
- $\mathbf V_s$ (+ up) drives the non-inverting input.
- $R_2$ runs from the output back to the inverting input.
- From the inverting input, $R_1$ in series with $C$ goes to ground.
- $\mathbf V_o$ is taken from the output to ground.

(At [01:24] he says "non-inverting" for the $R_1$–$C$ input by mistake. The drawing and the analysis use the inverting input.)

**His method.**
1. KCL at the inverting input, which is held at $\mathbf V_s$:
   $$\frac{\mathbf V_s}{R_1 + 1/(j\omega C)} + \frac{\mathbf V_s-\mathbf V_o}{R_2} = 0$$
2. Multiply by $R_2/(j\omega C)$, combine over a common denominator, and solve ([02:52]–[07:36]):
   $$\boxed{\mathbf H = \frac{1 + j\omega(R_1+R_2)C}{1 + j\omega R_1C} = \frac{1+j\omega/\omega_{c1}}{1+j\omega/\omega_{c2}}}$$
   with a zero at $\omega_{c1} = 1/((R_1+R_2)C) = 200$ rad/s and a pole at $\omega_{c2} = 1/(R_1C) = 1000$ rad/s.

**Answers and verification.**
- $M(0) = 0$ dB. $M(\infty) = 20\log 5 = 13.98 \approx 14$ dB. $\phi(0) = \phi(\infty) = 0^\circ$.
- Magnitude: 0 dB up to 200, then +20 dB/dec to 1000, reaching $20\log_{10}5 = 13.98$ dB, then flat at 14 dB.
- Phase: +45°/dec on 20–100, a plateau at $45\log_{10}5 = 31.5^\circ$ from 100 to 2000, then −45°/dec back to $0^\circ$ at $10^4$.
- (c) It is a high-pass filter. The maximum gain is $(R_1+R_2)/R_1 = 5$, i.e. 14 dB.
- Checks:
  - The standard form matches the direct non-inverting formula $1 + R_2/(R_1 + 1/j\omega C)$ at every frequency tested.
  - Exact $M(200) = 2.84$ dB (SL 0) and $M(1000) = 11.14$ dB (SL 13.98). The corners are only 0.7 decade apart, so the corrections are not exactly 3 dB.
  - The exact maximum phase is $41.8^\circ$ at $\sqrt{200\cdot1000} = 447$ rad/s. The SL plateau is $31.5^\circ$.

> [!note] Filter "type" here
> The DC gain is 1 (0 dB), not 0, so low frequencies are only attenuated *relative to* high frequencies, by 14 dB. Strictly, this is a high-frequency boost (shelf) with high-pass shape. He classifies it by the shape of $M(\omega)$. On an exam, give the type **and** the two plateau gains.

**Exam slot.** P4, active version: $\mathbf H$ in factored standard form, type, Bode, and the design ratio $(R_1+R_2)/R_1$. The 9.38 cousin on PS8 is graded work and is not covered.

### Cascaded-filters notes (posted 2026-11-02)

These come from a refresher with no Chapter 9 video. The session recording exists under `Recordings/2026-11-02-cascaded-filters-refresher-session/` but was not an input here.

#### Example 1: two-stage band-pass

**Circuit.**
- Stage 1, inverting low-pass: 1 kΩ input resistor, feedback $10\text{ k}\Omega \parallel 9\text{ nF}$. So $\mathbf V_1 = -10/(1+j\omega/\omega_{0,1})\,\mathbf V_s$ with $\omega_{0,1} = 1/(10\text{k}\cdot9\text{n}) = 1.111\times10^4$ rad/s ✓.
- Stage 2, inverting high-pass: 12 kΩ + 9 nF in series at the input, 96 kΩ feedback. Its gain is $-8\,(j\omega/\omega_{0,2})/(1+j\omega/\omega_{0,2})$ with $\omega_{0,2} = 1/(12\text{k}\cdot9\text{n}) = 9.259\times10^3$ rad/s ✓.
- The two minus signs cancel:
  $$\mathbf H = 80\,(j\omega/\omega_{0,2})\,\frac{1}{(1+j\omega/\omega_{0,2})(1+j\omega/\omega_{0,1})}$$
  He annotates the factors as constant, zero at origin, pole, pole.
- Bode sketch: +20 dB/dec, then a plateau at $M_0 = 20\log 80 = 38.06$ dB between $\omega_{0,2}$ and $\omega_{0,1}$, then −20 dB/dec. This product form matches a direct circuit computation ✓.

> [!warning] The straight-line plateau is never reached
> The two corners are only 0.08 decade apart. The exact peak is **32.80 dB** at $1.014\times10^4$ rad/s, which is **5.26 dB below** the drawn $20\log80$. The exact −3 dB band is $4.19\times10^3$ to $2.46\times10^4$ rad/s ($Q \approx 0.50$). Label $M_0$ as the asymptote, not the peak gain.

#### Example 2: band-reject design

**Specification.** Gain −50 outside a 20–40 kHz stop band, with ±40 dB/dec roll-off.

**His design.**
- $\omega_1 = 40\pi$ krad/s $= 1.257\times10^5$ rad/s ✓; $\omega_2 = 80\pi$ krad/s $= 2.513\times10^5$ rad/s ✓.
- The structure is a 2-stage low-pass $\mathbf H_{LP} = 1/(1+j\omega/\omega_{LP})^2$ in parallel with a 2-stage high-pass $\mathbf H_{HP} = (j\omega/\omega_{HP})^2/(1+j\omega/\omega_{HP})^2$. An inverting summer combines them: $\mathbf V_{out} = -(R_f/R)(\mathbf V_1 + \mathbf V_2)$.
- Set each branch to $1/\sqrt2$ at its own band edge:
  - $\omega_{LP} = \omega_1/\sqrt{\sqrt2-1} = 1.953\times10^5$ rad/s. The notes write $1.96\times10^5$, from rounding $\omega_1$ to $1.26\times10^5$; this is negligible.
  - $\omega_{HP} = \sqrt{\sqrt2-1}\,\omega_2 = 1.618\times10^5$ rad/s ✓.
- With $R = 1$ kΩ: $C_{LP} = 5.12 \to 5.1$ nF ✓, $C_{HP} = 6.18 \to 6.2$ nF ✓, and $R_f = 50$ kΩ ✓.
- The final circuit has five op-amps.

> [!warning] Summed response does not meet the 20–40 kHz spec (verified numerically)
> Each branch was designed **alone**. In the sum, the other branch is not negligible at the band edge: $|\mathbf H_{HP}(\omega_1)| = 0.376$. It is also about 170° out of phase with $\mathbf H_{LP}$, so the two partly cancel.
> - At $\omega_1$ and $\omega_2$, $|\mathbf H|/50 = 0.343$, i.e. **−9.3 dB, not −3 dB**.
> - The actual −3 dB stop band is **11.7–68.5 kHz** ($7.34\times10^4$ to $4.30\times10^5$ rad/s).
> - The notch reaches only **−19.8 dB**, at $1.777\times10^5$ rad/s (28.3 kHz).
> - $\omega_{LP} > \omega_{HP}$, so the two branches' straight-line plots overlap at 0 dB and show no notch at all. The dip comes entirely from phase cancellation.
>
> If you are asked to reproduce this design, follow his method, since that is what was taught. If you are asked to *verify* band edges of a parallel/summed design, evaluate the **sum**, not each branch.

**Exam slot.** P4/P2 design: cascade = product of stage transfer functions; pick $R$, then set $C$ from a 3 dB condition; design ratio = $R_f/R$.

---

## Traps & emphasis

1. **Pull constants out of powered factors with the power.** $(100+j2\omega)^2$ gives $100^2$; $(200+j2\omega)^3$ gives $200^3$. He forgot the square himself in 9.19(b) and caught it ([36:07]).
2. **Coefficient to corner.** $j0.2\omega = j\omega/5$, and $j50\omega/100 = j\omega/2$. For a quadratic, the corner comes from the $\omega^2$ term: $\omega_0 = \sqrt{\text{constant}/\text{coefficient of }\omega^2}$. The linear term gives $\zeta$.
3. **Real $\omega^2$ vs $(j\omega)^2$.** $\omega^2$ contributes $0^\circ$, while $(j\omega)^2 = -\omega^2$ contributes $180^\circ$ (9.19d [1:27:07]).
4. **Origin factors have no ramp.** Their phase is a constant $\pm90N^\circ$ and their magnitude slope applies at all frequencies. You cannot plot $\omega = 0$.
5. **Magnitude breaks at $\omega_c$; phase breaks at $\omega_c/10$ and $10\omega_c$.** Slopes in the phase total change at the /10 and ×10 marks, which is why he ticks them. Missing a mark gives wrong segment slopes, e.g. 9.19(a) has seven distinct phase segments.
6. **$\pm180^\circ$ ambiguity.** Leave it open in the limits and settle it by continuity (9.19 [07:08], 9.33 [13:56]).
7. **Anchor on a known constant**, not on $\omega \to 0$ when $M(0)$ is infinite. In 9.19(c) neither limit is usable, so find the band where the factors cancel.
8. **Phase in between can be non-zero even when $\phi(0) = \phi(\infty)$** (9.37 [13:41]).
9. **Sanity-check every $\mathbf H$ against circuit limits** (C open/short, L short/open). He frames this as the general validation habit (9.37 [29:09]).
10. **Resonance definition.** At resonance $\operatorname{Im}\tilde Z_i = 0$. The physical picture is that the series LC branch becomes a short and the response is large for a small input (9.4).
11. **Underdamped quadratic.** Compute $M(\omega_c)$ directly by substituting $\omega_c$, where the 1 and the $(j\omega/\omega_c)^2 = -1$ cancel, and draw the peak (9.33).
12. **Why −40 dB/dec.** Ten times the frequency gives $10^{-2}$ in $\mathbf H$ (9.33 (c)). Expect a P1-style "explain the slope" question.
13. **Multiple-order ramps.** Double zero: +90°/dec. Triple pole: −135°/dec. Quadratic: ±90°/dec. All of them span the same two decades.
14. **Label 0°/dec segments.** He does so explicitly to avoid ambiguity.
15. **Cascades.** Multiply the stage transfer functions. Each inverting stage contributes a minus sign, and pairs cancel (cascaded notes).
16. Narration slips to ignore. The slides are correct in every case:
    - 9.19 [17:18], [17:54], [50:53]: "45" for pole midpoints that are $-45^\circ$.
    - 9.19 [18:23]: "−90 at 100" for the pole at 100, whose ramp ends at 1000.
    - 9.19 [49:33]: "50 over five" for 50/10.
    - 9.19 [51:25]: "third order zero" for the pole at the origin.
    - 9.19 [1:09:41]: "nine degrees" for 90° (the zero-at-1 ramp ends at 90°).
    - 9.19 [1:10:20]: "quadratic zero at 4" for the pole.
    - 9.19 [1:28:35]: a garbled "180 at 190" for 180° at 100 and 90° at 10.
    - 9.33 [09:49]: "H(0) = 0", self-corrected to 1.
    - 9.33 [13:56]: "phase at ω_c is 90, not −90", which is reversed; the slide says −90°.
    - 9.37 [01:24]: "non-inverting" for the inverting input.

---

## Conflicts

| # | Item | Source A | Source B | Resolution for the exam |
|---|---|---|---|---|
| 1 | Phase range | Video rule (9.19 slide, key point (ii); verbatim at [56:32]: "if we go outside the range from minus three sixty to three sixty"): translate only outside [−360°, 360°] | Past-exam instruction: phase in [−180°, 180°] | Use the exam rule. Wrap at ±180°. 9.19(b) as drawn (90°→360°) would not comply; see the wrapped row in its table. |
| 2 | Corner correction | His videos: sharp straight-line corners, no 3 dB | Exact response: 3.01 dB at a simple corner, 6 dB at a double corner (e.g. 9.19b exact −9.8 dB vs SL −15.9 dB at ω = 5) | Draw the straight lines "as done in class". Use the 3 dB facts only for P1 conceptual questions or checks. |
| 3 | 9.19(d) quadratic zero | Problem and his solution: quadratic zero at ω₀ = 10 | ζ = 2.5: two real zeros at 2.087 and 47.91 | Check ζ first. Ignoring it costs 13.8 dB at ω = 10 and 28.6° of phase. |
| 4 | "Cutoff" in 9.33 | His ω_c = 1/√LC = 10⁵ rad/s (M = +20 dB there) | Half-power (−3 dB re DC) point: 1.55×10⁵ rad/s | Give 1/√LC as the corner/cutoff to match him. Name the definition if −3 dB is asked. |
| 5 | 9.37 "high-pass" | His classification by shape | DC gain is 1, not 0 (a shelf) | State the type plus both plateau gains (0 dB, 14 dB). |
| 6 | Cascaded band-pass $M_0$ | Notes label the plateau $20\log80 = 38.06$ dB | Exact peak 32.80 dB | Label $M_0$ as the asymptote. |
| 7 | Band-reject design | Notes: each branch set to −3 dB at its own band edge | Summed response is −9.3 dB at the edges; actual stop band 11.7–68.5 kHz | Reproduce the method; verify the sum if asked. |
| 8 | Narration vs slide | Slips listed in Traps #16 | Slides | Slides are right in every case. |
| 9 | Textbook | No "textbook-solution-error" flag appears in these four transcripts or the cascaded notes. The textbook's printed answers were not in this brief's inputs, so his answers were not compared with Ulaby's. | — | — |

---

## Top 5 takeaways (ranked for Exam 2)

1. **Use his fixed opening sequence, every time.** Standard form with leading-1 factors and a numerically boxed $K$, then a pole/zero list with orders, then $M(0)$, $M(\infty)$, $\phi(0)$, $\phi(\infty)$ in dB and degrees, all before drawing. The limits are both the anchor and the end-of-plot check. *(P3, P4)*
2. **Magnitude.** In each interval the slope is $20\times$(net power of $\omega$) dB/dec, with an abrupt break exactly at each corner. Anchor on a known constant level ($M(0)$, $M(\infty)$, or a mid band where factors cancel). Label every slope **and** the dB value at every breakpoint; he skips the latter, but the exam requires it. *(P3, P4)*
3. **Phase.** Each simple factor ramps over $\omega_c/10 \to 10\omega_c$ at $\pm45^\circ$/dec (quadratic $\pm90^\circ$/dec), and origin factors are constant $\pm90N^\circ$. Tick the /10 and ×10 points, sum the active slopes per interval, and **wrap at ±180° for the exam**, not at ±360° as in his video. *(P3, P4)*
4. **Circuit to $\mathbf H$.** Redraw, write one KCL (at the output node, or at the op-amp inverting input where $v_- = v_+$), multiply through to clear fractions, and box $\mathbf H$. Then sanity-check the limits: C open at DC, C short at HF. From the plot read off the type and the design ratio; e.g. the max gain of 9.37 is $(R_1+R_2)/R_1 = 5$ (14 dB). *(P4, P2)*
5. **Second-order specifics.** $\omega_c = 1/\sqrt{LC}$ is read off the $(j\omega/\omega_c)^2$ term. Compute $M(\omega_c)$ by substitution (1 and −1 cancel) and draw the resonant peak, here $20\log Q = 20$ dB. The high-frequency slope is −40 dB/dec because ten times the frequency gives $10^{-2}$. Check $\zeta$: if $\zeta \ge 1$, factor into real corners (9.19d). Resonance means $\operatorname{Im}Z = 0$, and the series LC branch acts as a short (9.4). *(P1, P3, P4)*

---


All files are in `Problem Solving Videos/`. Slides are in `_sources_transcribed/Problem Solving Videos/Ulaby <n>.pdf`. Transcripts are in `Transcripts/Problem Solving Videos/`.

| Video | Watch | What to watch for |
|---|---|---|
| `Ulaby 9.19 video.mp4` (92.6 min) | **[28:51]–[33:17]** (primary) | His own recap of the method: why dB contributions add, the limit checks, marking $\omega/10$ and $10\omega$, why a simple factor is ±45°/dec (90° over two decades), and summing only the sloped regions. |
| same | [19:20]–[24:47] | Summing four phase ramps interval by interval in 9.19(a). Watch how each slope changes at a /10 or ×10 mark, not at the corner. |
| same | [51:25]–[54:29], then [55:03]–[57:50] | A pole at the origin gives constant phase with no ramp. The phase runs past 360° and is reset to 0. The "start from a known constant" rule. Remember the exam range is ±180°. |
| same | [1:00:28]–[1:02:44] | 9.19(c): neither limit is finite, so he finds the 1–4 rad/s band where $\mathbf H$ is constant (−26 dB) and anchors there. |
| `Ulaby 9.33 video.mp4` (17.6 min) | **[08:06]–[12:33]** | Substituting $\omega_c$ into the standard form (1 and −1 cancel, giving $10/j$), the 20 dB peak, the 0 dB DC level, and the −40 dB/dec roll-off. Then [12:33]–[15:31] for the phase, including why the limit is −180° and not +180°. |
| `Ulaby 9.37 video.mp4` (30.5 min) | **[02:52]–[07:36]** | KCL at the op-amp inverting input held at $\mathbf V_s$, the multiply-through trick, and the common denominator leading to the boxed $\mathbf H$. This is the P4 derivation pattern. |
| same | [25:23]–[29:09] | The limit sanity check: capacitor open (follower, 0 dB) and capacitor short (non-inverting gain $1+R_2/R_1$). Copy this check onto every filter answer. |
| `Ulaby 9.4 video.mp4` (11.0 min) | **[07:05]–[10:54]** | What resonance means physically: the L and C reactances cancel, the branch shorts the input, and $Z_i = 0$. This is P1 conceptual material. |
