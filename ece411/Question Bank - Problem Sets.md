# Question Bank: Problem Sets 6–8 (Exam 2 unit)

Built 2026-11-06 from `Transcripts/Problem Sets/PS6–PS8`, the original PDFs (all figures re-checked against rendered pages), the tips handout, and the TA's Discord grading notes. PS6 and PS7 are graded with keys posted, so they get full treatment. **PS8 is due Mon 11-09 09:00 and is NOT solved here.** Only its statements, figures and problem types appear. Every PS6/PS7 number and every drill answer was re-derived with python3 (numpy/scipy/sympy). `> [!warning]` marks a place where I disagree with the official key. `(?)` marks a reconstruction or an inference.

Exam 2 (Wed 11-11, 70 min, closed book, 4 × 25 pts): **P1** four conceptual short answers (filter concepts and semiconductor physics) · **P2** design or analysis (passive filter design or max power transfer) · **P3** filter transfer function, cutoff and Bode plots · **P4** active (op-amp) or RLC filter: factored standard-form $\mathbf H(\omega)$, filter type, Bode plots, design ratio.

| Item | Type | Exam slot |
|---|---|---|
| PS6-1 (8.51), PS6-2 (8.54) | T1 max power transfer | P2 |
| PS6-3, PS6-4 | T2 carrier statistics | P1 |
| PS6-5, PS6-6 | T3 pn junction / diode equation / dimensional analysis | P1 |
| PS7-1 (9.2), PS7-2 (9.6) | T4 resonance | P2/P4 sub-part |
| PS7-3 (9.18), PS7-4 (9.20) | T5 standard form + straight-line Bode | P3 |
| PS7-5 (9.31), PS7-6 (9.34) | T6 passive filter type / cutoff / slopes | P3/P4 |
| PS7-7 | T7 decoupling caps, ESR/ESL | P1 |
| PS8-1…6 | T8–T13 (labels only) | P4 (T9–T12), P2 (T8) |

---

## Question-style profile

### Who wrote what
- **Textbook problems** (Ulaby/Maharbiz/Furse 3e) selected by Ed Yu: 8.51, 8.54, 9.2, 9.6, 9.18, 9.20, 9.31, 9.34 (graded), plus 9.26, 9.38, 9.39, 9.42 and 12.2 in PS8. The wording on these is Ulaby's, and the keys are the publisher's typeset solutions (©2016 NTS Press).
- **Ed Yu's own problems:** PS6 Q3–Q6 (semiconductors) and the PS8 Q5 wrapper ("Solve the problem below analytically") around an item labelled **m9.2**. The source of m9.2 is unknown (?). The keys for PS6 Q3–6 are handwritten.
- **PS7 Q7** (decoupling capacitors) has hand-drawn figures with red annotation boxes, the same style as the handwritten tablet key. It may be TA-written (?). The TA called this topic a common interview question.

### How the asks are phrased (recurring stems)
- Filter and Bode stems:
  - Find $\mathbf H(\omega)=\mathbf V_o/\mathbf V_i$ **"in standard form"** (m9.2 adds "for creating a Bode plot").
  - **"Generate spectral plots"** of magnitude and phase. In Ulaby's keys these are the true curves (MATLAB), so sketch the real shape, including peaking.
  - **"Bode magnitude and phase plots (straight-line approximations)"**. These are asymptotic plots: draw dashed component lines and a solid sum, and label every corner and every dB value.
  - **"Determine the cutoff frequency $\omega_c$ and the slope of the magnitude (in dB)"** for $\omega/\omega_c\ll1$ and $\gg1$.
  - **"What type of filter is it? What is its maximum gain?"** (PS8 9.38/9.39). This matches the P4 exam pattern.
  - m9.2 adds substituting $\omega=2\pi f$, plotting against $f$ in Hz, and reading the asymptotes and the "two corner frequencies" off the plot.
- Power stem: choose $\mathbf Z_L$ so the power dissipated in it is a maximum, then find how much power that is.
- Resonance stems: "determine the resonant frequency", and "the frequency $\omega_0$ at which $\mathbf H$ is purely real".
- Ed Yu's semiconductor stems:
  - "Show that, for [inequality], [result]". The target result is given, so the derivation is what earns credit.
  - "Obtain an expression for … Your result should be in terms of [list]".
  - "Calculate, at $T=300$ K, …".
  - "What are the units … (in standard mks units)?"
  - "assuming any arbitrary numerical constants of proportionality have magnitude 1".
  - A closing **Hint:** that points back to class ("Recall from class how the band-edge energies … change with $V$").
- PS7 Q7 builds a conceptual ladder:
  1. Write $v_o=f_1V_i+f_2i_L$.
  2. State the "mathematical conditions or inequalities" on $f_1,f_2$.
  3. Draw both Bode plots "on a single set of axes", then say over what frequencies the capacitor "work[s] as intended".
  4. Say how increasing $C_d$ affects that range.
  5. Refine the capacitor model (ESR/ESL), then give the range of near-ideal behaviour and how it trends with capacitor size.
- **"Explain your answer" does not appear in the PS6–PS8 text.** The need to explain comes from three places instead: the tips handout (write a sentence or key phrase naming the law or concept used), the "if no, why not?" in 9.26(b), and the "how does X affect Y" items in PS7 Q7. Assume every P1 answer needs a one-line reason.

### How the givens are phrased
- **Ch. 8 (AC power):** element values are printed on the figure as phasor impedances ($4\ \Omega$, $j2\ \Omega$, $-j4\ \Omega$, $-j2$ kΩ), and sources as amplitude phasors ($20\angle0^\circ$ V, $2\angle0^\circ$ mA).
- **Ch. 9 (filters):** elements are labelled symbolically ($R_1, C_1, L$) on the figure, and the numbers are given in the text ("given that $R_1=1\ \Omega$, $R_2=2\ \Omega$, $C_1=1\ \mu$F…"). Part (a) is symbolic, and the numbers arrive only in part (b).
- **Semiconductors:** every needed formula is supplied ($g_v(E)$, $f(E)$, $n$), along with material constants ("take $E_g=1.12$ eV, $m_c^*=1.18m_e$, $m_v^*=0.81m_e$, $m_e=9.11\times10^{-31}$ kg") and symbol definitions ($E_g\equiv E_c-E_v$). The physical constants are NOT given; the key uses $k_B=8.617\times10^{-5}$ eV/K $=1.381\times10^{-23}$ J/K and $\hbar=1.055\times10^{-34}$ J·s, so memorize these.
- Pedagogical framing: a paragraph opens with what was done in recitation or class, and the problem closes by naming the result's significance ("This value is called the intrinsic concentration…", "…constitute the standard form of the ideal diode equation").

### Figure conventions
- **Ulaby two-ports:** open-circle terminals, "+ $\mathbf V_i$ −" on the left and "+ $\mathbf V_o$ −" on the right, a common bottom wire, and the output across the last shunt element. Phasor quantities are bold. The load is a blue box $\mathbf Z_L$.
- **Op-amp figures (PS8):** a triangle with the inverting (−) input on top and the source drawn with + on top; ground symbols are explicit. In 9.39 the statement asks for $\mathbf V_o/\mathbf V_i$ while the figure labels the source $\mathbf V_s$ (a textbook inconsistency; same quantity).
- **Instructor and TA figures:** hand-drawn, with red boxes naming sub-blocks ("Board Parasitics", "Ideal" ⇒ "Model"). The load is drawn as a current source $i_L(t)$ with its arrow pointing down.

### Units, constants, rounding
- Prefixes: kΩ, mA, mH, µF, nF. $\omega$ in rad/s throughout Ch. 9, except m9.2 (Hz). Semiconductor answers are in cm⁻³: compute in m⁻³ (SI) and divide by $10^6$.
- Rounding in the keys is uneven. Ulaby's keys give 3 s.f. (12.5 W, 1.41 mW, 8.94 V) but sometimes 2 s.f. (6.1 V, $3.3-j2.4$ kΩ; see the 8.54 warning). The handwritten key gives 4 s.f. (0.5673 eV, $9.473\times10^9$) and then states ≈$9.47\times10^9$. dB values appear at 0.1 dB or integer precision (−56.5, −30.1, 32, 14, −48).
- **Default for the exam: 3 s.f., angles in degrees, $\omega$ in rad/s, final answers boxed with units.**

### Recurring templates
1. Thevenin at the load, conjugate match, $P=|\mathbf V_{Th}|^2/8R_{Th}$.
2. Rationalize, then set Im (or Re) = 0 to find a resonance or zero-phase frequency.
3. Factor into $(1+j\omega/\omega_c)$ and $[1+j2\xi\omega/\omega_c+(j\omega/\omega_c)^2]$, list the constant in dB, then the zeros and poles, then sum the asymptotes.
4. Passive ladder: KCL at the one internal node plus a voltage divider, then expand the denominator into $1+j\omega(\dots)+(j\omega)^2(\dots)$, then read $\omega_c$ and $\xi$.
5. Integral with the Boltzmann approximation: substitute $u$, pull out the exponential, finish with a Gamma integral.
6. Superposition split $v_o=f_1V_i+f_2i_L$, then Bode-plot each coefficient.

### Traps seen in PS6–PS7
- **Phasor convention:** Ulaby phasors are amplitudes, so $P_{max}=|\mathbf V_{Th}|^2/(8R_L)$. With rms phasors the denominator is $4R_L$; using rms here would turn 12.5 W into 25 W.
- **Matching:** $\mathbf Z_L=\mathbf Z_{Th}^*$, not $\mathbf Z_{Th}$. When finding $\mathbf Z_{Th}$, a deactivated current source becomes an open circuit (8.54), not a short.
- **A constant $j$ is not $j\omega$.** In 9.20(c) the numerator $j(10+j\omega)\times10^8$ contributes a constant +90° of phase and no magnitude slope.
- **$\xi\ge1$ quadratics are really two real poles.** In 9.20(b), $256-\omega^2+j32\omega=(16+j\omega)^2$, so $\xi=1$. In 9.31, $\xi=7/4$ gives real poles at $1.57\times10^5$ and $1.59\times10^6$ rad/s. A single straight-line quadratic corner overestimates the 9.31 peak by 11 dB.
- **"Cutoff frequency" of a 2nd-order factor** in the keys means the corner (natural) frequency $1/\sqrt{\cdot}$, not the −3 dB point. These coincide only for $\xi=1/\sqrt2$ in LP/HP filters. See the 9.31 and 9.34 notes.
- **Negative real constants** add ±180° of phase: 9.34 starts at +180°.
- **Low-$\xi$ resonance peaks** do not appear in straight-line plots. 9.20(a) has $\xi=0.2$, so the true curve sits +8 dB above the straight line at 50 rad/s. The PS7 Q7 key notes that its undamped resonance "doesn't show up on a bode plot".
- **Unit bookkeeping** in the semiconductor problems: $k_B$ in J/K inside $N_c$, in eV/K in the exponent when energies are in eV, and the m⁻³ → cm⁻³ conversion.
- **Typo in PS6 Q5:** the statement prints $p_n=p_n(V{=}0)$ where it means $p_{n0}$.

### TA grading notes (Darsh Shah, Discord)
- **Neatness costs points, and the penalty grows:** −0.01 on PS2, −0.1 on PS3, "larger" afterwards. Classwide note 1: keep sequential steps strictly in a vertical or horizontal sequence so partial credit can be given.
- **Plot everything asked.** On PS2 many students skipped required plots. Read the whole question, and expect a larger share of missed parts later (also flagged on PS7).
- **PS4:** give all answers when squaring produces several, otherwise points come off.
- **PS6 Q3:** he was surprised by the range of methods students used for the **gamma-function integral**. Recitation 5 (10/12) worked a near-identical problem, including that integral. On 10/20 he said semiconductor-physics questions often appear on the second exam.
- **PS7:** "Make sure you can [do] Bode Plots in your sleep". There are often many Bode questions on Exam 2. On **Q7** many students reached the opposite conclusions, "mostly because you had your Bode Plots backwards or you misunderstood the problem". Decoupling capacitors are a common interview question. (I dispute part of the Q7 key below.)
- **AI warning (9/20):** AI solutions are not always correct and block the intended intuition.

### Write-up rules from the tips handout (these apply to exams)
- Draw a labelled circuit diagram. It is mandatory whenever you define your own currents or voltages.
- Name the law or concept in a phrase on each step.
- Box final answers, with units.
- Bare correct numbers get minimal or zero credit. Sloppy work, multiple unmarked answers and irrelevant work are penalized. Optional checks are not needed for full credit.

### Most exam-like items in this bank
1. **PS7-6 (9.34):** passive 2nd-order filter, standard form, $\omega_c$, $\xi$, slope, spectral plots (P3/P4).
2. **PS7-4 (9.20a):** straight-line Bode with a zero at the origin plus a quadratic pole (P3).
3. **PS6-2 (8.54):** max power transfer through a bridge with a current source (P2).
4. **PS6-3/PS6-4:** derive $p$ with the gamma integral, then $E_F$ and $n_i$ (P1; flagged by the TA).
5. **PS7-7:** decoupling capacitor and ESR/ESL concepts (P1; flagged by the TA).

For P4 practice while PS8 is off-limits, use drills **D9.2** (inverting bandpass: type, max gain) and **D10.1** (2nd-order active LP, design ratio for $\xi$).

---

## Problem types

| # | Type | Sources | Count |
|---|---|---|---|
| T1 | Max power transfer (Thevenin + conjugate match) | 8.51, 8.54 | 2 |
| T2 | Carrier statistics: DOS, Fermi–Dirac, Boltzmann, $n$, $p$, $n_i$, Gamma integral | PS6 Q3, Q4 | 2 |
| T3 | pn junction: quasi-Fermi levels, ideal diode equation, dimensional analysis | PS6 Q5, Q6 | 2 |
| T4 | Resonance / zero-phase frequency | 9.2, 9.6 | 2 |
| T5 | Standard form + straight-line Bode (simple, origin, quadratic, repeated) | 9.18(a–c), 9.20(a–c) | 2 problems, 6 functions |
| T6 | Passive filter: standard form, type, cutoff, $\xi$, slopes, spectral plots | 9.31, 9.34 | 2 |
| T7 | Decoupling capacitors, ESR/ESL, self-resonance | PS7 Q7 | 1 (10 sub-parts) |
| T8 | Series RLC bandpass parameters ($\omega_0,Q,B,\omega_{c1},\omega_{c2}$) | PS8 9.26 | 1 (label only) |
| T9 | First-order single-op-amp active filter analysis: standard form, spectral plots, type, max gain | PS8 9.38 | 1 (label only) |
| T10 | Second-order active filter, Sallen–Key topology with unity-gain buffer | PS8 9.39 | 1 (label only) |
| T11 | Active filter design to gain / corner / roll-off spec | PS8 9.42 | 1 (label only) |
| T12 | Inverting op-amp with RC networks: $H(\omega)$, $H(f)$, Bode in Hz, asymptotes and corners read from the plot | PS8 m9.2 | 1 (label only) |
| T13 | Impulse sifting-property integrals (Ch. 12; likely final-exam unit (?)) | PS8 12.2(a–c) | 1 (label only) |

### T1 · Maximum power transfer (PS6-1, PS6-2)
**Recipe (as the key does it):**
1. Remove $\mathbf Z_L$ and label the two load terminals.
2. Find $\mathbf Z_{Th}$ ("$\mathbf Z_s$" in the key) by deactivating independent sources: a V-source becomes a short, an I-source becomes an open. Then reduce by series and parallel steps.
3. Find $\mathbf V_{Th}=\mathbf V_{oc}$ by voltage division (8.51) or mesh analysis with a supermesh constraint on the current source (8.54).
4. Set $\mathbf Z_L=\mathbf Z_{Th}^*$.
5. Compute $P_{av}(\max)=\dfrac{|\mathbf V_{Th}|^2}{8R_{Th}}$ with amplitude phasors.
6. Variant: if $\mathbf Z_L$ must be a pure resistance, then $R_L=|\mathbf Z_{Th}|$ and $P=\tfrac12|\mathbf V_{Th}/(\mathbf Z_{Th}+R_L)|^2R_L$.

**Common errors:**
- Using $\mathbf Z_{Th}$ instead of its conjugate.
- Shorting a current source when finding $\mathbf Z_{Th}$.
- Using $4R_L$ with amplitude phasors.
- Forgetting that $\mathbf V_{oc}$ needs the open-circuit condition: no current in the series element next to the load (8.51).
- Rounding intermediate currents. That produced the key's 1° error in 8.54.

### T2 · Carrier statistics (PS6-3, PS6-4)
**Recipe:**
1. Write $p=\int_{-\infty}^{E_v}g_v(1-f)\,dE$ (or $n=\int_{E_c}^{\infty}g_cf\,dE$).
2. Apply Boltzmann. For $E_F-E\gg k_BT$, $1-f=\dfrac{1}{1+e^{(E_F-E)/k_BT}}\approx e^{-(E_F-E)/k_BT}$; the key writes this as $1/(1+x)\approx1-x$.
3. Substitute $u=E_v-E$, with the limits becoming $0\to\infty$, and pull $e^{-(E_F-E_v)/k_BT}$ outside.
4. Evaluate the Gamma integral $\int_0^\infty u^{1/2}e^{-u/k_BT}du=\Gamma(\tfrac32)(k_BT)^{3/2}=\tfrac{\sqrt\pi}{2}(k_BT)^{3/2}$. If you don't remember $\Gamma$, use $u=k_BT\,y^2$: then $2(k_BT)^{3/2}\int_0^\infty y^2e^{-y^2}dy$, and by parts this equals $2(k_BT)^{3/2}\cdot\tfrac{\sqrt\pi}{4}$.
5. Collect: $\dfrac{\sqrt2}{\pi^2}\cdot\dfrac{\sqrt\pi}{2}=\dfrac{2}{(2\pi)^{3/2}}$, which gives $p=2\left(\dfrac{m_v^*k_BT}{2\pi\hbar^2}\right)^{3/2}e^{-(E_F-E_v)/k_BT}\equiv N_ve^{-(E_F-E_v)/k_BT}$.
6. Setting $n=p$ gives $E_c-E_F=\tfrac12E_g-\tfrac34k_BT\ln(m_v^*/m_c^*)$, and $n_i=\sqrt{N_cN_v}\,e^{-E_g/2k_BT}$.
7. Numbers: compute $N_{c,v}$ in SI with $k_B$ in J/K (result in m⁻³, then ÷$10^6$ for cm⁻³). Do the exponent in eV with $k_B=8.617\times10^{-5}$ eV/K.

**Common errors:**
- Using $f$ instead of $1-f$ for holes.
- Wrong limits after the substitution (the sign flip from $du=-dE$).
- Dropping the $(k_BT)^{3/2}$ factor from the integral.
- Mixing J and eV.
- Reporting m⁻³ when cm⁻³ is expected.
- Putting $E_F$ on the wrong side of midgap. It sits below midgap when $m_v^*<m_c^*$, because the smaller $N_v$ needs a closer $E_F$.

### T3 · pn junction / diode equation / dimensional analysis (PS6-5, PS6-6)
**Recipe:**
1. Sketch the forward-bias band diagram: p on the left at higher band energy, quasi-Fermi levels $E_{F,n}$ (n side) and $E_{F,p}$ (p side) with $E_{F,n}-E_{F,p}=qV$.
2. The minority electrons on the p side are set by $E_{F,n}$: $n_p=N_ce^{-(E_c-E_{F,n})/k_BT}=n_{p0}e^{qV/k_BT}$. Likewise $p_n=p_{n0}e^{qV/k_BT}$.
3. Substitute into $J=A_1(n_p-n_{p0})+A_2(p_n-p_{n0})$, which gives $(A_1n_{p0}+A_2p_{n0})(e^{qV/k_BT}-1)$.
4. Dimensional analysis:
   - $[J]=$ A/m² and $[n]=$ m⁻³, so $[A]=$ C·m/s.
   - From $J=-qD\nabla n$, $[D]=$ m²/s.
   - The only length is $\sqrt{D\tau}$, so $L=\sqrt{D\tau}$.
   - Hence $A=q\sqrt{D/\tau}=qD/L$.
   - The sign is positive because current flows p→n for $V>0$.
5. Extension (not asked in PS6; standard result (?)): built-in potential $V_{bi}=\dfrac{k_BT}{q}\ln\dfrac{N_AN_D}{n_i^2}$ from $n_{p0}=n_{n0}e^{-qV_{bi}/k_BT}$, where $n_{p0}=n_i^2/N_A$.

**Common errors:**
- Using the p-side $E_F$ for $n_p$ under bias.
- Forgetting the "−1" term.
- Writing $[A]$ as C/(m²·s): the extra m³ comes from $n$.
- Leaving $A$ as $q\sqrt{D/\tau}$ when part (e) asks for the $D/L$ form.

### T4 · Resonance / zero-phase frequency (PS7-1, PS7-2)
**Recipe:**
1. Build $\mathbf Z_i(\omega)$ (or $\mathbf H(\omega)$) from series and parallel combinations or one KCL.
2. Put it over a common denominator and rationalize by multiplying by the conjugate of the denominator.
3. Set Im = 0 and discard $\omega=0$ ("trivial resonance"). Check the radicand is positive (an existence condition on $R$).
4. Plug $\omega_0$ back in as a check: $\mathbf Z_i(\omega_0)$ must be real. For 9.2 it equals 50 Ω.

**Common errors:**
- Setting $\omega_0=1/\sqrt{LC}$ by reflex. That is wrong whenever $R$ sits in parallel with a reactive element, as in 9.2 where $\omega_0=2\times10^4\neq1/\sqrt{LC}=1.41\times10^4$.
- Algebra slips while rationalizing. Use only the imaginary part of the numerator after multiplying by the conjugate.

### T5 · Standard form + straight-line Bode (PS7-3, PS7-4)
**Recipe (the key's bullet format):**
1. From every factor pull out its constant so each factor reads $(1+j\omega/\omega_c)$. Write quadratics as $[1-(\omega/\omega_c)^2+j2\xi\omega/\omega_c]$, with $\omega_c=\sqrt{\text{constant}}$ and $\xi$ from the middle coefficient. If $\xi\ge1$, factor the quadratic into two simple poles (my recommendation; the keys don't always do it).
2. List the elements:
   - "Constant term $K$ ⟹ $20\log K$ dB"
   - "Zero @ origin"
   - "Simple zero with $\omega_c=\dots$"
   - "Simple pole of order 2 …"
   - "Quadratic pole with $\omega_c=\dots$"
3. Magnitude:
   - With no $(j\omega)^{\pm n}$ factor, start flat at $20\log K$.
   - With such a factor, draw a line through $20\log K$ at $\omega=1$ with slope $\pm20n$ dB/dec.
   - At each corner the slope changes by ±20 dB/dec per simple order, or ±40 per quadratic.
4. Phase:
   - $K>0$ contributes 0; $K<0$ contributes ±180°; a constant $j$ contributes +90°; $(j\omega)^n$ contributes $90n$°.
   - A simple zero or pole ramps ±45°/dec from $\omega_c/10$ to $10\omega_c$.
   - A quadratic ramps ±90°/dec over the same two decades (±180° total).
   - Add the piecewise-linear segments; the slope changes at every $\omega_c/10$ and $10\omega_c$.
5. Draw the dashed component lines and the solid sum. Label every corner and every breakpoint dB value, as the key does.

**Common errors:**
- Not normalizing factors, e.g. leaving $(200+j2\omega)$ instead of $200(1+j\omega/100)$, so the constant comes out wrong.
- Treating a constant $j$ as $j\omega$.
- Missing the phase kinks at $\omega_c/10$ and $10\omega_c$ of every factor. The 9.20(b) key does this.
- Using ±45°/dec for a quadratic.
- Using −40 dB/dec for a squared quadratic, which is really −80.

### T6 · Passive filter: type, cutoff, slopes (PS7-5, PS7-6)
**Recipe:**
1. Do KCL at the internal node (ladders) or a voltage divider with a parallel combination.
2. Expand the denominator into $1+j\omega(\cdot)+(j\omega)^2(\cdot)$ and match it to $1+j2\xi\omega/\omega_c+(j\omega/\omega_c)^2$. Report $K$, $\omega_c$ and $\xi$ symbolically, then numerically.
3. Type comes from the limits:
   - $\lvert H\rvert$ finite → 0: lowpass.
   - 0 → finite: highpass.
   - 0 → 0: bandpass.
   - Finite → finite with a dip: bandstop.
4. The slopes come from the low- and high-frequency asymptotic forms of $\mathbf H$, as in the key.
5. Maximum gain: for a bandpass, evaluate at $\omega_c$, where the quadratic is purely imaginary. For LP/HP with $\xi<1/\sqrt2$, the peak is $1/(2\xi\sqrt{1-\xi^2})$.
6. Spectral plots: sketch the true curve. Its value at $\omega_c$ is $1/(2\xi)$ times the asymptote value for a quadratic.

**Common errors:**
- Calling $\omega_c$ the −3 dB frequency when $\xi\neq1/\sqrt2$.
- Missing the 180° phase from a $-(\omega/\omega_c)^2$ numerator.
- Using the straight-line peak as the "maximum gain" when $\xi\ge1$.

### T7 · Decoupling capacitors, ESR/ESL (PS7-7)
**Recipe:**
1. Do KCL at the $v_o$ node and split by superposition: $f_1=\partial v_o/\partial V_i$ is dimensionless, and $f_2=\partial v_o/\partial i_L=-\mathbf Z_{out}$ is in ohms.
2. Without $C_d$: $f_1=1$, $f_2=-j\omega L_p$.
3. With $C_d$: $f_1=\dfrac{1}{1-\omega^2L_pC_d}$ and $f_2=-\dfrac{j\omega L_p}{1-\omega^2L_pC_d}=-\left(j\omega L_p\parallel\tfrac{1}{j\omega C_d}\right)$, with $\omega_0=1/\sqrt{L_pC_d}$.
4. Bode plots:
   - $\lvert f_1\rvert$ is flat, then falls −40 dB/dec above $\omega_0$.
   - $\lvert f_2\rvert$ rises +20 dB/dec below $\omega_0$ and falls −20 dB/dec above it, with an unbounded peak at $\omega_0$ when there is no resistance.
5. Real capacitor: $Z=R_{ESR}+j\omega L_{ESL}+1/(j\omega C)$.
   - $\lvert Z\rvert$ is V-shaped, falling −20 dB/dec, reaching its minimum $R_{ESR}$ at $\omega_{SR}=1/\sqrt{L_{ESL}C}$, then rising +20 dB/dec.
   - The part behaves as a capacitor below about $\omega_{SR}/10$.
   - Bigger parts have larger ESL and lower $\omega_{SR}$.

**Common errors:**
- Bode plots drawn backwards: the TA's PS7 note.
- Treating $f_2$ as dimensionless. "$f_2\to0$" really means $\lvert f_2i_L\rvert\ll$ the allowed ripple.
- The direction of the conclusion. See the warning at PS7-7 before memorizing the key's answer.

### T8–T13 · PS8 types (labels only; DO NOT SOLVE until PS8 is submitted Mon 11-09)
- **T8:** series RLC bandpass parameters, plus a $Q$-redesign question (9.26).
- **T9:** first-order active filter with one op-amp. Standard form, spectral plots, filter type, max gain (9.38).
- **T10:** second-order active filter, Sallen–Key topology with unity-gain buffer. Standard form, spectral plots, filter type, max gain (9.39).
- **T11:** active filter design to gain / corner-frequency / roll-off spec (9.42).
- **T12:** inverting op-amp with RC impedances at input and feedback. $\mathbf H(\omega)$, $\mathbf H(f)$, Bode in Hz, asymptotes, corner frequencies (m9.2).
- **T13:** impulse sifting-property integrals over finite and infinite limits (12.2).

---

## Every problem

### PS6 (due 10/21; graded; key posted)

#### PS6-1 · 8.51 Maximum power transfer 1 · T1
**Statement:** In a phasor-domain circuit, a source $20\angle0^\circ$ V (+ on top) drives a series $4\ \Omega$ resistor to node A. An inductor $j2\ \Omega$ runs from A to the bottom rail (shunt). From A, a series capacitor $-j4\ \Omega$ leads to the load $\mathbf Z_L$, which returns to the bottom rail. Choose $\mathbf Z_L$ for maximum power dissipated in it, and find that power.

> [!check]- Solution
> 1. $\mathbf Z_{Th}$ (source shorted): $-j4+\dfrac{4(j2)}{4+j2}=-j4+(0.8+j1.6)=0.8-j2.4\ \Omega$.
> 2. $\mathbf V_{oc}$: no current flows in $-j4$, so $\mathbf V_{oc}$ is the voltage across $j2$: $\dfrac{20(j2)}{4+j2}=4+j8=8.94\angle63.4^\circ$ V.
> 3. $\boxed{\mathbf Z_L=\mathbf Z_{Th}^*=0.8+j2.4\ \Omega}$
> 4. $P_{max}=\dfrac{|\mathbf V_{Th}|^2}{8R_{Th}}=\dfrac{80}{6.4}=\boxed{12.5\ \text{W}}$
>
> Verified: a brute-force search over $\mathbf Z_L$ peaks at 12.5 W at $0.8+j2.4\ \Omega$. Matches the key.

#### PS6-2 · 8.54 Maximum power transfer 2 · T1
**Statement:** The circuit is a diamond bridge with top, left, right and bottom nodes:
- Left–top: $-j2$ kΩ.
- Top–right: $4$ kΩ.
- Left–bottom: $8$ kΩ.
- Right–bottom: $-j6$ kΩ.
- A current source $2\angle0^\circ$ mA sits across the horizontal diagonal, arrow pointing right (left → right node).
- $\mathbf Z_L$ connects top to bottom through an outer rail on the right.

Choose $\mathbf Z_L$ for maximum power, and find the power.

> [!check]- Solution
> 1. $\mathbf V_{oc}$ by mesh analysis. Take $\mathbf I_1$ clockwise in the upper triangle (it flows top→right through 4 kΩ) and $\mathbf I_2$ clockwise in the lower triangle (right→bottom through $-j6$ kΩ).
>    - Supermesh KVL around the outer diamond: $(4-j2)\mathbf I_1+(8-j6)\mathbf I_2=0$ (kΩ).
>    - Source constraint: $\mathbf I_2-\mathbf I_1=2$ mA.
>    - Solving: $\mathbf I_2=\dfrac{8-j4}{12-j8}=0.615+j0.0769$ mA and $\mathbf I_1=-1.385+j0.0769$ mA.
> 2. $\mathbf V_{oc}=4\text{k}\,\mathbf I_1-j6\text{k}\,\mathbf I_2=-5.08-j3.38=6.10\angle{-146.3^\circ}$ V. Nodal analysis gives the same result.
> 3. $\mathbf Z_{Th}$ (source opened): $(4-j6)\parallel(8-j2)$ kΩ $=\dfrac{20-j56}{12-j8}=3.31-j2.46$ kΩ.
> 4. $\boxed{\mathbf Z_L=3.31+j2.46\ \text{k}\Omega}$, and $P=\dfrac{6.10^2}{8(3308)}=\boxed{1.41\ \text{mW}}$

> [!warning] Key vs. my numbers (8.54), minor
> - The key gives $\mathbf I_1=-1.37+j0.076$ mA, $\mathbf V_s=6.1\angle-145.3^\circ$ V and $\mathbf Z_L=(3.3+j2.4)$ kΩ.
> - Exact values: $\mathbf I_1=-1.385+j0.0769$ mA and $\mathbf V_{oc}=6.10\angle{-146.3^\circ}$ V. The key's −145.3° comes from its rounded $\mathbf I_1$; python reproduces −145.3° with those rounded inputs.
> - $\mathbf Z_{Th}=3.308-j2.462$ kΩ, so to 3 s.f. $\mathbf Z_L=3.31+j2.46$ kΩ. The key's "$-j2.4$" truncates 2.46.
> - $P=1.41$ mW agrees.
>
> I believe the exact values. The fault is rounding of intermediates, which is exactly what 3-s.f. grading would penalize.

#### PS6-3 · Hole concentration from density of states · T2
**Statement:** You are given $p=\int_{-\infty}^{E_v}g_v(E)[1-f(E)]\,dE$ with $g_v=\frac{\sqrt2}{\pi^2}\left(\frac{m_v^*}{\hbar^2}\right)^{3/2}(E_v-E)^{1/2}$ and the Fermi function $f=1/(e^{(E-E_F)/k_BT}+1)$. Show that for $E_F-E_v\gg k_BT$, $p\approx2\left(\frac{m_v^*k_BT}{2\pi\hbar^2}\right)^{3/2}e^{-(E_F-E_v)/k_BT}$. (The recitation did the same for $n$.)

> [!check]- Solution
> 1. $1-f=\dfrac{1}{1+e^{(E_F-E)/k_BT}}$. For $E\le E_v$ we have $E_F-E\ge E_F-E_v\gg k_BT$, so $1-f\approx e^{-(E_F-E)/k_BT}$. The key writes this as $1/(1+x)\approx1-x$.
> 2. Substitute $u=E_v-E$, so $du=-dE$ and the limits run $0\to\infty$. Then $e^{-(E_F-E)/k_BT}=e^{-(E_F-E_v)/k_BT}e^{-u/k_BT}$.
> 3. $p=\dfrac{\sqrt2}{\pi^2}\left(\dfrac{m_v^*}{\hbar^2}\right)^{3/2}e^{-(E_F-E_v)/k_BT}\displaystyle\int_0^\infty u^{1/2}e^{-u/k_BT}du$
> 4. The integral is $\Gamma(\tfrac32)(k_BT)^{3/2}=\tfrac{\sqrt\pi}{2}(k_BT)^{3/2}$ (sympy confirms).
> 5. The prefactor is $\dfrac{\sqrt2}{\pi^2}\cdot\dfrac{\sqrt\pi}{2}=\dfrac{1}{\sqrt2\,\pi^{3/2}}=\dfrac{2}{(2\pi)^{3/2}}$, which gives the stated result ✓ (sympy ratio = 1).
>
> How good is the approximation? A numerical comparison of exact Fermi–Dirac with Boltzmann at 300 K gives exact/approx = 0.953 at $E_F-E_v=0.05$ eV, 0.993 at 0.1 eV and 0.9998 at 0.2 eV.

#### PS6-4 · Intrinsic concentration · T2
**Statement:** You are given $n\approx2\left(\frac{m_c^*k_BT}{2\pi\hbar^2}\right)^{3/2}e^{-(E_c-E_F)/k_BT}$ and the $p$ from PS6-3.
- (a) Find $E_c-E_F$ (in eV) for which $n=p$, in terms of $E_g$, $k_B$, $T$, $m_c^*$, $m_v^*$ ($E_g\equiv E_c-E_v$).
- (b) For Si at 300 K ($E_g=1.12$ eV, $m_c^*=1.18m_e$, $m_v^*=0.81m_e$, $m_e=9.11\times10^{-31}$ kg), compute $n=p=n_i$.

The problem notes that high $n_i$ at high $T$ degrades control by doping.

> [!check]- Solution
> **(a)**
> 1. Setting $n=p$: $(m_c^*)^{3/2}e^{-(E_c-E_F)/k_BT}=(m_v^*)^{3/2}e^{-(E_F-E_v)/k_BT}$.
> 2. Write $E_F-E_v=E_g-(E_c-E_F)$, take logs and solve: $\boxed{E_c-E_F=\tfrac12E_g-\tfrac34k_BT\ln(m_v^*/m_c^*)}$
>
> **(b)**
> 1. $E_c-E_F=0.56-\tfrac34(0.025851)\ln(0.6864)=\boxed{0.567\ \text{eV}}$ (0.5673). $E_F$ sits 7.3 meV below midgap.
> 2. $N_c=3.21\times10^{19}$ cm⁻³ and $N_v=1.83\times10^{19}$ cm⁻³.
> 3. $n=p=n_i=\sqrt{N_cN_v}e^{-E_g/2k_BT}=\boxed{9.47\times10^{9}\ \text{cm}^{-3}}$ ($9.47\times10^{15}$ m⁻³).
>
> The key reports $n=9.473\times10^9$ and $p=9.477\times10^9$. The tiny mismatch comes from rounding 0.5673 inside the exponent. With the key's constants python gives exactly $9.475\times10^9$ for both, and with CODATA constants $9.49\times10^9$. Agrees at 3 s.f.

#### PS6-5 · Simplified ideal diode equation · T3
**Statement:** In a pn diode with forward voltage $V$ (p relative to n), $J(V)\approx A_1(n_p-n_{p0})+A_2(p_n-p_{n0})$, where $n_p$ is the electron concentration on the p side, $p_n$ the hole concentration on the n side, and the subscript 0 marks the value at $V=0$. Show that $J(V)=(A_1n_{p0}+A_2p_{n0})(e^{qV/k_BT}-1)$. The hint: under bias, $n$ on the p side is set by the n-side $E_F$, and $p$ on the n side by the p-side $E_F$.

> [!check]- Solution
> 1. Band diagram under forward bias: the quasi-Fermi levels split by $E_{F,n}-E_{F,p}=qV$.
> 2. $n_p=N_ce^{-(E_c-E_{F,n})/k_BT}=N_ce^{-(E_c-E_{F,p})/k_BT}e^{(E_{F,n}-E_{F,p})/k_BT}=n_{p0}e^{qV/k_BT}$
> 3. $p_n=N_ve^{-(E_{F,p}-E_v)/k_BT}=N_ve^{-(E_{F,n}-E_v)/k_BT}e^{(E_{F,n}-E_{F,p})/k_BT}=p_{n0}e^{qV/k_BT}$
> 4. Substituting: $\boxed{J=(A_1n_{p0}+A_2p_{n0})(e^{qV/k_BT}-1)}$ ✓

#### PS6-6 · Dimensional analysis and the ideal diode equation · T3
**Statement:**
- (a) Give the mks units of $A_1$ and $A_2$ in PS6-5.
- (b) Given $J_{diff}=-qD\nabla n$, give the units of $D_n$ and $D_p$ ($\tau$ is in seconds).
- (c) With unit-magnitude constants, express $A_1$ in terms of $q$, $D_n$, $\tau_n$, and $A_2$ in terms of $q$, $D_p$, $\tau_p$.
- (d) Express the diffusion lengths $L_n$ and $L_p$ (in metres) in terms of $D$ and $\tau$.
- (e) Express $A_1$ and $A_2$ in terms of $q$, $D$ and $L$. Together with PS6-5 this gives the standard ideal diode equation.

> [!check]- Solution
> - **(a)** $[J]=\text{C/(s·m}^2)$ and $[n]=\text{m}^{-3}$, so $\boxed{[A]=\text{C·m/s}}$
> - **(b)** $\text{C/(s·m}^2)=\text{C}\cdot[D]\cdot\text{m}^{-1}\cdot\text{m}^{-3}$, so $\boxed{[D]=\text{m}^2/\text{s}}$
> - **(c)** Write $A=q^aD^b\tau^c$. Matching units gives $a=1$, $b=\tfrac12$, $c=-\tfrac12$ (sympy). So $\boxed{A_1=q\sqrt{D_n/\tau_n},\ A_2=q\sqrt{D_p/\tau_p}}$; the key writes ± here and fixes the sign on its p. 7.
> - **(d)** $\boxed{L=\sqrt{D\tau}}$
> - **(e)** $\boxed{A_1=qD_n/L_n,\ A_2=qD_p/L_p}$. Both are positive because the electrons injected into p and the holes injected into n both give conventional current p→n for $V>0$. So $J=q\left(\dfrac{D_n}{L_n}n_{p0}+\dfrac{D_p}{L_p}p_{n0}\right)(e^{qV/k_BT}-1)$, which matches the key.

### PS7 (due 11/02; graded; key posted)

#### PS7-1 · 9.2 Resonant frequency · T4
**Statement:** A two-terminal network is a capacitor $C$ in series with the parallel combination of $L$ and $R$. Find the resonant frequency for $R=100\ \Omega$, $L=5$ mH, $C=1\ \mu$F.

> [!check]- Solution
> 1. $\mathbf Z_i=\dfrac{j\omega LR}{R+j\omega L}+\dfrac{1}{j\omega C}$
> 2. $\operatorname{Im}\mathbf Z_i=\omega L\dfrac{R^2}{R^2+\omega^2L^2}-\dfrac1{\omega C}=0$, so $\omega_0=\sqrt{\dfrac{R^2}{R^2LC-L^2}}$. This requires $R>\sqrt{L/C}=70.7\ \Omega$.
> 3. $\omega_0=\sqrt{10^4/(5\times10^{-5}-2.5\times10^{-5})}=\boxed{2.00\times10^4\ \text{rad/s}}$ (not $1/\sqrt{LC}=1.41\times10^4$).
> 4. Check: $\mathbf Z_i(\omega_0)=50.0\ \Omega$ (real). Matches the key.

#### PS7-2 · 9.6 RLC transfer function · T4
**Statement:** A two-port ladder: series $C$, shunt $L_1$ (from node $\mathbf V_1$), series $L_2$, then shunt $R$, with $\mathbf V_o$ across $R$. Find (a) $\mathbf H=\mathbf V_o/\mathbf V_i$ and (b) the $\omega_0$ at which $\mathbf H$ is purely real.

> [!check]- Solution
> 1. KCL at $\mathbf V_1$: $(\mathbf V_1-\mathbf V_i)j\omega C+\dfrac{\mathbf V_1}{j\omega L_1}+\dfrac{\mathbf V_1}{R+j\omega L_2}=0$. Divider: $\mathbf V_o=\mathbf V_1\dfrac{R}{R+j\omega L_2}$.
> 2. $\boxed{\mathbf H=\dfrac{-\omega^2RL_1C}{R(1-\omega^2L_1C)+j\omega(L_1+L_2-\omega^2L_1L_2C)}}$ (sympy-identical to the key).
> 3. The numerator is real, so $\mathbf H$ is real when the denominator's imaginary part vanishes: $\boxed{\omega_0=\sqrt{\dfrac{L_1+L_2}{L_1L_2C}}}$
> 4. Extra check (not in the key): $\mathbf H(\omega_0)=1+L_2/L_1$, which is real and >1.

#### PS7-3 · 9.18 Bode plots 1 · T5
**Statement:** Generate straight-line Bode magnitude and phase plots for
- (a) $\dfrac{30(10+j\omega)}{(200+j2\omega)(1000+j2\omega)}$
- (b) $\dfrac{j100\omega}{(100+j5\omega)(100+j\omega)^2}$
- (c) $\dfrac{200+j2\omega}{(50+j5\omega)(1000+j\omega)}$

> [!check]- Solution (straight-line breakpoints verified by script; all match the key)
> **(a)** $\mathbf H=\dfrac{1.5\times10^{-3}(1+j\omega/10)}{(1+j\omega/100)(1+j\omega/500)}$. Constant −56.5 dB; zero at 10; poles at 100 and 500.
> - Magnitude: −56.5 dB flat to 10; +20 dB/dec up to −36.5 dB at 100; flat to 500; −20 dB/dec after (−62.5 dB at $10^4$).
> - Phase: 0 at 1; +45°/dec to 45° at 10; flat 45° from 10 to 50; −45°/dec to 31.5° at 100; −90°/dec to −58.5° at 1000; −45°/dec to −90° at 5000; flat after.
>
> **(b)** $\mathbf H=\dfrac{j10^{-4}\omega}{(1+j\omega/20)(1+j\omega/100)^2}$. Constant −80 dB; zero at the origin; pole at 20; double pole at 100.
> - Magnitude: −80 dB at $\omega=1$, rising +20 dB/dec to −54 dB at 20; flat to 100; −40 dB/dec after (−94 dB at 1000).
> - Phase: 90° to 2; −45°/dec to 58.5° at 10; −135°/dec to 17.9° at 20 and −117° at 200; −90°/dec to −180° at 1000.
>
> **(c)** $\mathbf H=\dfrac{(1/250)(1+j\omega/100)}{(1+j\omega/10)(1+j\omega/1000)}$. Constant −48 dB.
> - Magnitude: −48 dB flat to 10; −20 dB/dec to −68 dB at 100; flat to 1000; −20 dB/dec after (−88 dB at $10^4$).
> - Phase: −45°/dec from 0° at 1 to −45° at 10; flat −45° from 10 to 1000; −45°/dec to −90° at $10^4$.

#### PS7-4 · 9.20 Bode plots 2 · T5
**Statement:** Generate straight-line Bode magnitude and phase plots for
- (a) $\dfrac{j5\times10^3\omega(20+j2\omega)}{2500-\omega^2+j20\omega}$
- (b) $\dfrac{512(1+j\omega)(4+j40\omega)}{(256-\omega^2+j32\omega)^2}$
- (c) $\dfrac{j(10+j\omega)\times10^8}{(20+j\omega)^2(500+j\omega)(1000+j\omega)}$

> [!check]- Solution
> **(a)** $\mathbf H=\dfrac{j40\omega(1+j\omega/10)}{1-(\omega/50)^2+j\omega/125}$. Constant 40 = 32.0 dB; zero at the origin; zero at 10; quadratic pole $\omega_c=50$ with $\xi=0.2$.
> - Magnitude: 32 dB at $\omega=1$; +20 dB/dec to 52 dB at 10; +40 dB/dec to 80 dB at 50; flat 80 dB after. True peak 88.1 dB at 50 ($1/2\xi=2.5$, +8 dB).
> - Phase: 90° at 1; +45°/dec to 121.5° at 5; −45°/dec to 107.9° at 10 and 62.9° at 100; −90°/dec to 0° at 500; flat after.
>
> **(b)** $\mathbf H=\dfrac{(1+j\omega/0.1)(1+j\omega)}{32[1-(\omega/16)^2+j\omega/8]^2}$. Constant −30.1 dB; zeros at 0.1 and 1; quadratic pole of order 2 at 16 with $\xi=1$. In fact $256-\omega^2+j32\omega=(16+j\omega)^2$, a 4th-order real pole.
> - Magnitude: −30.1 dB flat to 0.1; +20 dB/dec to −10.1 dB at 1; +40 dB/dec to **38.1 dB at 16**; −40 dB/dec after (−1.9 dB at 160, −33.8 dB at 1000). The true value at 16 is 26.0 dB.
> - Phase: 0 at 0.01; 45° at 0.1; 135° at 1; 144.2° at 1.6; then −135°/dec to **36.7° at 10**; then −180°/dec, through 0° at 16, to −180° at 160; flat after.
>
> **(c)** $\mathbf H=\dfrac{j5(1+j\omega/10)}{(1+j\omega/20)^2(1+j\omega/500)(1+j\omega/1000)}$. Constant $j5$: +14.0 dB and **+90° of phase with no slope**.
> - Magnitude: 14 dB flat to 10; +20 dB/dec to 20 dB at 20; −20 dB/dec to −8.0 dB at 500; −40 dB/dec to −20 dB at 1000; −60 dB/dec after (−80 dB at $10^4$).
> - Phase: 90° at 1; 103.5° at 2; 72.1° at 10; 40.6° at 50; 13.5° at 100; −40.6° at 200; −103.5° at 1000; −166.5° at 5000; −180° at $10^4$.

> [!warning] 9.20(b): the key's plot is drawn inaccurately (the setup is right)
> - **Magnitude:** the key's solid line peaks at about 35 dB at $\omega=16$ (measured off the zoomed PDF). The correct straight-line value is $-10.1+40\log_{10}16=38.1$ dB. Its tail then ends near −43 dB, where the correct value at 1000 is −33.8 dB.
> - **Phase:** the key draws one straight segment from 1.6 to 160. But the zero at 1 keeps adding +45°/dec until 10, so the correct line has a kink at 10. On 1.6–10 the slope is −135°/dec, reaching 36.7° at 10 (the key shows about 25°); on 10–160 it is −180°/dec. It crosses 0° at 16 (the key: about 13).
> - **Which I believe:** my values. They follow from the key's own bullet list and were checked by script. The plots are drafting errors and do not change the method.

#### PS7-5 · 9.31 Passive filters 1 · T6
**Statement:** A two-port ladder: series $R_1$, shunt $C_1$ (at node $\mathbf V_1$), series $C_2$, then shunt $R_2$, with $\mathbf V_o$ across $R_2$.
- (a) Find $\mathbf H=\mathbf V_o/\mathbf V_i$ in standard form.
- (b) Draw spectral plots for $R_1=1\ \Omega$, $R_2=2\ \Omega$, $C_1=1\ \mu$F, $C_2=2\ \mu$F.
- (c) Find the cutoff $\omega_c$ and the dB slopes for $\omega/\omega_c\ll1$ and $\gg1$.

> [!check]- Solution
> 1. KCL at $\mathbf V_1$, plus the divider $\mathbf V_o=\mathbf V_1R_2/(R_2+1/j\omega C_2)$, gives $\mathbf H=\dfrac{j\omega R_2C_2}{(1+j\omega R_1C_1)(1+j\omega R_2C_2)+j\omega R_1C_2}$ (sympy-identical).
> 2. Expanding, $\boxed{\mathbf H=\dfrac{j\omega K}{1+j2\xi\omega/\omega_c+(j\omega/\omega_c)^2}}$ with $K=R_2C_2$, $\omega_c=1/\sqrt{R_1R_2C_1C_2}$ and $\xi=\tfrac12\omega_c(R_1C_1+R_2C_2+R_1C_2)$.
> 3. Numbers: $K=4\times10^{-6}$ s, $\omega_c=5.00\times10^5$ rad/s, $\xi=7/4$.
> 4. Slopes: +20 dB/dec below, because $\mathbf H\approx j4\times10^{-6}\omega$; −20 dB/dec above, because $\mathbf H\approx-j10^6/\omega$.
> 5. Phase runs from +90° to −90°, passing 0° at $\omega_c$. **Type: bandpass. Max gain: 0.571 (−4.86 dB) at $5.00\times10^5$ rad/s.**

> [!warning] 9.31: what "cutoff" means (a definition caveat, not an arithmetic error)
> - The key's $\omega_c=0.5\times10^6$ rad/s is the corner (centre) frequency of the quadratic. It is where the peak occurs, not a half-power point.
> - The true −3 dB band, relative to the −4.86 dB peak, runs from $1.33\times10^5$ to $1.88\times10^6$ rad/s.
> - Because $\xi=1.75>1$, the denominator factors into real poles at $1.57\times10^5$ and $1.59\times10^6$ rad/s. A straight-line plot built on those two corners peaks at −4.0 dB, close to the true −4.86. A single quadratic corner at $5\times10^5$ predicts +6.0 dB, 11 dB too high.
> - On an exam that asks for the "cutoff" of a bandpass, give $\omega_c$ as defined in the key and add the half-power pair.

#### PS7-6 · 9.34 Passive filters 2 · T6
**Statement:** A two-port: series $C$, then shunt $L$ in parallel with shunt $R$, with $\mathbf V_o$ across $L\parallel R$.
- (a) Find $\mathbf H$ in standard form.
- (b) Draw spectral plots for $R=10\ \Omega$, $L=1$ mH, $C=10\ \mu$F.
- (c) Find $\omega_c$ and the dB slope for $\omega/\omega_c\ll1$.

> [!check]- Solution
> 1. Divider: $\mathbf H=\dfrac{R\parallel j\omega L}{1/j\omega C+R\parallel j\omega L}=\boxed{\dfrac{-(\omega/\omega_c)^2}{1+j2\xi\omega/\omega_c+(j\omega/\omega_c)^2}}$ with $\omega_c=1/\sqrt{LC}$ and $\xi=\omega_cL/(2R)$ (sympy-identical).
> 2. $\omega_c=\boxed{1.00\times10^4\ \text{rad/s}}$ and $\xi=0.5$.
> 3. Slope below $\omega_c$: **+40 dB/dec**. **Type: highpass**; high-frequency gain 1 (0 dB).
> 4. Spectral shape: −80 dB at $10^2$, 0.0 dB at $\omega_c$, a peak of **+1.25 dB at $1.41\times10^4$** (because $\xi<0.707$), then 0 dB after.
> 5. Phase: 180° at low frequency, 90° at $\omega_c$, 0° at high frequency. Matches the key.
>
> Caveat: the −3 dB point (relative to the 0 dB passband) is at $7.86\times10^3$ rad/s, not at $\omega_c$, since $\xi\neq0.707$.

#### PS7-7 · Decoupling capacitors (application) · T7
**Statement:**
- **Figure 7.1:** a DC source $V_i$ drives, through the board parasitics (series $L_p$ then $R_p$, in a red box; the text says to ignore trace resistance and capacitance), the node $v_o$. From $v_o$ a decoupling capacitor $C_d$ goes to ground, together with a load current sink $i_L(t)$ (arrow down).
- **Figure 7.2:** a real capacitor modelled as $R_{ESR}$, $L_{ESL}$ and $C$ in series.

Parts:
- (a) Write $v_o=f_1(\omega)V_i+f_2(\omega)i_L(\omega)$ (i) without $C_d$ and (ii) with $C_d$. $V_i$ is constant and $i_L$ varies.
- (b) What conditions on $f_1$ and $f_2$ make $v_o=V_i$ with $C_d$ present?
- (c) Draw the magnitude Bode plots of $f_1$ and $f_2$ on one set of axes. Over what frequencies does $C_d$ work as intended?
- (d) What is the effect of increasing $C_d$?
- (e) (i) Impedance of an ideal C. (ii) Its Bode plot. (iii) Impedance with ESR and ESL. (iv) Its Bode plot. (v) The range of near-ideal behaviour. (vi) How that range changes as capacitor value and size grow.

> [!check]- Solution (key's answers, my corrections in the warning)
> - **(a)(i)** $v_o=V_i-j\omega L_p\,i_L$, so $f_1=1$ and $f_2=-j\omega L_p$.
> - **(a)(ii)** KCL at $v_o$ gives $f_1=\dfrac{1}{1-\omega^2L_pC_d}$ and $f_2=-\dfrac{j\omega L_p}{1-\omega^2L_pC_d}$. The key labels $f_2$ without the minus sign that the stated form $v_o=f_1V_i+f_2i_L$ requires; only the magnitude matters for the plots.
> - **(b)** $f_1\to1$ and $f_2\to0$. The key adds that "$f_1\gg f_2$" is not sufficient. Note that $f_2$ is in ohms: the real condition is $\lvert f_2\rvert\lvert i_L\rvert\ll$ the allowed droop.
> - **(c)** Plot shapes:
>   - $\lvert f_1\rvert$: 0 dB, then −40 dB/dec above $\omega_0=1/\sqrt{L_pC_d}$.
>   - $\lvert f_2\rvert$: +20 dB/dec below $\omega_0$, −20 dB/dec above.
>   - An infinite-Q peak sits at $\omega_0$ (no R), which straight-line plots do not show.
>
>   The key's answer: the capacitor works at low frequencies, below about $\omega_0/10$.
> - **(d)** The key: increasing $C_d$ lowers $\omega_0$, so the working region shrinks.
> - **(e)** Real-capacitor answers:
>   - (i) $Z=1/(j\omega C)$.
>   - (ii) A straight line at −20 dB/dec.
>   - (iii) $Z=R_{ESR}+j\omega L_{ESL}+1/(j\omega C)$.
>   - (iv) A V shape: −20 dB/dec, then a minimum of $R_{ESR}$ at $1/\sqrt{L_{ESL}C}$, then +20 dB/dec.
>   - (v) Below about $\tfrac1{10}\cdot1/\sqrt{L_{ESL}C}$.
>   - (vi) Larger capacitors have larger ESL and ESR, so the ideal range shrinks.
>
>   I agree with (e).

> [!warning] PS7-7 (c)/(d): I disagree with the key's conclusion on physical grounds
> **The key says:** the decoupling capacitor works for $\omega\lesssim\omega_0/10$, and a larger $C_d$ shrinks that range. The TA graded the opposite answer as "backwards".
>
> **My reading:**
> - The problem states that $V_i$ is constant. So $f_1$ only acts at $\omega=0$, where $f_1(0)=1$ with or without $C_d$. That condition is automatically met.
> - Everything $C_d$ does is in $f_2=-(j\omega L_p\parallel 1/j\omega C_d)$, the impedance the load sees.
>   - For $\omega\ll\omega_0$, $f_2\approx-j\omega L_p$, the same as without $C_d$. The capacitor does nothing there; $v_o\approx V_i$ only because the trace impedance $\omega L_p$ is small.
>   - For $\omega\gg\omega_0$, $\lvert f_2\rvert\approx1/(\omega C_d)\ll\omega L_p$. This is the regime where $C_d$ supplies the fast load current.
>   - With an ideal capacitor, $C_d$ beats the bare trace exactly when $\lvert1-\omega^2L_pC_d\rvert>1$, that is for $\omega>\sqrt2\,\omega_0$.
> - Python, with $L_p=10$ nH and $C_d=100$ nF ($\omega_0=3.16\times10^7$ rad/s, 5.0 MHz):
>   - At $0.1\omega_0$: $\lvert f_2\rvert$ = 0.0319 Ω with the capacitor vs 0.0316 Ω without.
>   - At $\omega_0$: unbounded.
>   - At $10\omega_0$: 0.0319 Ω vs 3.16 Ω, about 100× better.
> - So a larger $C_d$ lowers $\omega_0$ and lowers $1/(\omega C_d)$. That *extends* the useful band *downward*. The upper limit is set by the capacitor's own ESL, as part (e) shows. This is standard power-distribution practice: bulk capacitors for low frequencies, small low-ESL capacitors for high frequencies. If $V_i$ carries ripple, $f_1\to0$ above $\omega_0$ is also desirable, because the $L_pC_d$ pair filters it.
>
> **Steelman of the key:**
> - If you require $f_1\approx1$ and $f_2\approx0$ at the same $\omega$ across the whole spectrum, only $\omega\ll\omega_0$ satisfies both.
> - The undamped resonance at $\omega_0$ really is a hazard.
>
> **Which I believe:** the physics reading above. The key's region is where $v_o\approx V_i$ holds trivially, not where $C_d$ is doing the work.
>
> **Exam strategy:** an exam graded by the same logic may expect "low frequencies". Write the $f_1$/$f_2$ conditions, draw the correct Bode shapes, and state both facts in one line each:
> 1. $v_o\approx V_i$ for $\omega\ll\omega_0$ (the trace alone suffices).
> 2. $C_d$ reduces $\lvert f_2\rvert$ only for $\omega>\sqrt2\,\omega_0$; avoid $\omega\approx\omega_0$; ESR damps the peak.

### PS8 (due Mon 11/09 09:00): statements only

#### PS8-1 · 9.26 Passive filter circuit parameters · T8 · **DO NOT SOLVE: graded, due Mon 11-09**
**Statement:** A series RLC bandpass filter has $R=5\ \Omega$, $L=20$ mH, $C=0.5\ \mu$F.
- (a) Determine $\omega_0$, $Q$, $B$, $\omega_{c1}$ and $\omega_{c2}$. (The asterisk in the PDF marks a back-of-book answer.)
- (b) Can $Q$ be doubled by changing $L$ and/or $C$ while keeping $\omega_0$ and $R$ unchanged? If yes, propose values; if no, explain why not.

**Figure:** none given.

#### PS8-2 · 9.38 Active filters 1 · T9 · **DO NOT SOLVE: graded, due Mon 11-09**
**Statement:**
- (a) Obtain $\mathbf H=\mathbf V_o/\mathbf V_s$ in standard form.
- (b) Generate spectral plots of magnitude and phase for $R_1=99$ kΩ, $R_2=1$ kΩ, $C=0.1\ \mu$F.
- (c) What type of filter is it, and what is its maximum gain?

**Figure P9.38:** An op-amp with − input on top and + input on the bottom.
- Source $\mathbf V_s$ (+ on top), − terminal to ground, + terminal straight to the **non-inverting (+) input**.
- From the inverting (−) input node, $R_2$ goes to ground.
- The feedback from output to the − input is $R_1$ **in parallel with** $C$ ($C$ drawn as the outer loop).
- $\mathbf V_o$ is taken from the op-amp output to ground.

#### PS8-3 · 9.39 Active filters 2 · T10 · **DO NOT SOLVE: graded, due Mon 11-09**
**Statement:**
- (a) Obtain $\mathbf H=\mathbf V_o/\mathbf V_i$ in standard form. The figure labels the source $\mathbf V_s$. The asterisk marks a back-of-book answer.
- (b) Generate spectral plots for $R_1=R_2=100\ \Omega$, $C_1=10\ \mu$F, $C_2=0.4\ \mu$F.
- (c) What type of filter is it, and what is its maximum gain?

**Figure P9.39 (also used for 9.40):**
- Source $\mathbf V_s$ (+ on top, − to the bottom wire) feeds series $R_1$ to a middle node, then series $R_2$ to a second node wired to the op-amp **+ input**.
- $C_1$ goes from the middle node **up to a top wire that connects to the op-amp output**.
- $C_2$ goes from the second node down to the bottom wire.
- The op-amp − input is tied directly to the output (unity-gain follower).
- $\mathbf V_o$ is taken from the output to the bottom wire.

#### PS8-4 · 9.42 Active filter design 1 · T11 · **DO NOT SOLVE: graded, due Mon 11-09**
**Statement:** Design an active lowpass filter with gain 4, corner frequency 1 kHz and a gain roll-off of −60 dB/decade. **Figure:** none.

#### PS8-5 · m9.2 Bode plot analysis · T12 · **DO NOT SOLVE: graded, due Mon 11-09**
**Statement:** Solve analytically.
- (a) Find $\mathbf H(\omega)$ of the circuit, written in standard form for a Bode plot.
- (b) Substitute $\omega=2\pi f$ to express it in terms of $f$ (Hz).
- (c) Generate Bode magnitude and phase plots versus $f$ for $R_1=3.3$ kΩ, $R_2=10$ kΩ, $C_1=0.01\ \mu$F, $C_2=0.1\ \mu$F.
- (d) From the plot, give (1) the low-frequency asymptotes for magnitude and phase, (2) the high-frequency asymptotes, and (3) the corner frequencies (the problem states there are two).

**Figure m9.2:**
- An AC source $v_s$ (+ on top, − grounded) connects through $R_1$ **in parallel with** $C_1$ to the op-amp **− input**.
- The **+ input is grounded**.
- The feedback from output to the − input is $R_2$ **in parallel with** $C_2$.
- The output is labelled $v_{out}$.

#### PS8-6 · 12.2 Simple integrals · T13 · **DO NOT SOLVE: graded, due Mon 11-09**
**Statement:** Evaluate
- (a) $G_1=\int_{-\infty}^{\infty}(3t^3-4t^2+3)[\delta(t)+2\delta(t-2)]\,dt$
- (b) $G_2=\int_{-4}^{4}2(e^{-3t}+1)[\delta(t)-2\delta(t-2)]\,dt$
- (c) $G_3=\int_{-12}^{16}4[t\sin(2\pi t)-1][\delta(t-1)+\delta(t-6)]\,dt$

**Figure:** none.

---

## Variant drills

All answers were computed and checked with python3 (sympy derivations, numpy sweeps). Drills for PS8-only types (T8–T13) **deliberately use a different topology or spec** from the PS8 item, so none can be transcribed into a PS8 answer. Each says how it differs.

### T1 · Max power transfer

#### D1.1
A phasor-domain source $12\angle0^\circ$ V drives a series $6\ \Omega$ resistor to node A. A capacitor $-j8\ \Omega$ runs from A to ground. From A, a series inductor $j3\ \Omega$ leads to the load $\mathbf Z_L$, which returns to ground. Choose $\mathbf Z_L$ so that the power dissipated in it is a maximum. How much power will that be?

> [!check]- Answer
> 1. $\mathbf Z_{Th}=j3+\dfrac{6(-j8)}{6-j8}=j3+(3.84-j2.88)=3.84+j0.12\ \Omega$
> 2. $\mathbf V_{Th}=\dfrac{12(-j8)}{6-j8}=7.68-j5.76=9.60\angle{-36.9^\circ}$ V
> 3. $\boxed{\mathbf Z_L=3.84-j0.120\ \Omega}$ and $P=\dfrac{9.6^2}{8(3.84)}=\boxed{3.00\ \text{W}}$

#### D1.2
A current source $10\angle0^\circ$ mA (arrow up) feeds a node A that has a $1$ kΩ resistor and a $-j1$ kΩ capacitor to ground. From A, a series $j2$ kΩ inductor leads to $\mathbf Z_L$, which returns to ground.
- (a) Choose $\mathbf Z_L$ for maximum power, and give the power.
- (b) If $\mathbf Z_L$ must be a pure resistance $R_L$, what $R_L$ maximizes the power, and how much is it?

> [!check]- Answer
> 1. $\mathbf Z_{Th}=j2+(1\parallel-j1)=0.5+j1.5$ kΩ, and $\mathbf V_{Th}=10\text{ mA}\times(0.5-j0.5)\text{ k}\Omega=5-j5=7.07\angle-45^\circ$ V.
> 2. **(a)** $\mathbf Z_L=0.5-j1.5$ kΩ and $P=\dfrac{50}{8(500)}=\boxed{12.5\ \text{mW}}$
> 3. **(b)** $R_L=|\mathbf Z_{Th}|=\boxed{1.58\ \text{k}\Omega}$, giving $P=\tfrac12\left|\dfrac{\mathbf V_{Th}}{\mathbf Z_{Th}+R_L}\right|^2R_L=\boxed{6.01\ \text{mW}}$. A brute-force sweep confirms the optimum at 1.581 kΩ.

### T2 · Carrier statistics

#### D2.1
Electrons in the conduction band have $g_c(E)=\frac{\sqrt2}{\pi^2}\left(\frac{m_c^*}{\hbar^2}\right)^{3/2}(E-E_c)^{1/2}$ and occupancy $f(E)$.
- (a) Show that, for $(E_c-E_F)\gg k_BT$, the average kinetic energy $\langle E-E_c\rangle=\dfrac{\int_{E_c}^\infty(E-E_c)g_cf\,dE}{\int_{E_c}^\infty g_cf\,dE}$ equals $\tfrac32k_BT$.
- (b) Evaluate $\int_0^\infty u^{1/2}e^{-u/k_BT}du$ without quoting the Gamma function.

> [!check]- Answer
> **(a)**
> 1. Apply Boltzmann: $f\approx e^{-(E-E_F)/k_BT}$. Substitute $u=E-E_c$. The prefactor and $e^{-(E_c-E_F)/k_BT}$ cancel in the ratio.
> 2. $\langle u\rangle=\dfrac{\int_0^\infty u^{3/2}e^{-u/k_BT}du}{\int_0^\infty u^{1/2}e^{-u/k_BT}du}=k_BT\dfrac{\Gamma(5/2)}{\Gamma(3/2)}=k_BT\dfrac{3\sqrt\pi/4}{\sqrt\pi/2}=\boxed{\tfrac32k_BT}$ (sympy).
>
> **(b)**
> 1. Let $u=k_BT\,y^2$, so $du=2k_BT\,y\,dy$. Then the integral is $2(k_BT)^{3/2}\int_0^\infty y^2e^{-y^2}dy$.
> 2. By parts: $\int_0^\infty y^2e^{-y^2}dy=\left[-\tfrac y2e^{-y^2}\right]_0^\infty+\tfrac12\int_0^\infty e^{-y^2}dy=\tfrac12\cdot\tfrac{\sqrt\pi}{2}$.
> 3. Result: $\boxed{\tfrac{\sqrt\pi}{2}(k_BT)^{3/2}}$

#### D2.2
Use the $n$ and $p$ expressions from PS6-4.
- (a) For GaAs at 300 K, take $E_g=1.42$ eV, $m_c^*=0.067m_e$, $m_v^*=0.48m_e$. Calculate $E_c-E_F$ (in eV) for $n=p$, and calculate $n_i$.
- (b) Show that $np$ is independent of $E_F$ and equals $n_i^2$.
- (c) Si (PS6-4 parameters) is doped so that $n=N_D=10^{16}$ cm⁻³. Find $p$ and $E_c-E_F$.
- (d) Find $n_i$ of Si at 400 K, assuming $E_g$ and the masses do not change.

> [!check]- Answer
> - **(a)** $E_c-E_F=0.71-\tfrac34(0.02585)\ln(0.48/0.067)=\boxed{0.672\ \text{eV}}$. $N_c=4.35\times10^{17}$ and $N_v=8.34\times10^{18}$ cm⁻³, so $n_i=\boxed{2.25\times10^6\ \text{cm}^{-3}}$.
> - **(b)** $np=N_cN_ve^{-(E_c-E_F)/k_BT}e^{-(E_F-E_v)/k_BT}=N_cN_ve^{-E_g/k_BT}=n_i^2$. $E_F$ cancels.
> - **(c)** $p=n_i^2/N_D=(9.47\times10^9)^2/10^{16}=\boxed{8.98\times10^3\ \text{cm}^{-3}}$, and $E_c-E_F=k_BT\ln(N_c/N_D)=0.02585\ln(3.21\times10^3)=\boxed{0.209\ \text{eV}}$.
> - **(d)** $n_i(400\text{ K})=\boxed{3.28\times10^{12}\ \text{cm}^{-3}}$, 346× the 300 K value. At 500 K it is $1.18\times10^{14}$, approaching typical doping levels; that is the PS6-4 remark.

### T3 · pn junction / diode equation

#### D3.1
A Si pn junction at 300 K has $N_A=10^{17}$ cm⁻³ on the p side and $N_D=10^{16}$ cm⁻³ on the n side; take $n_i=9.47\times10^9$ cm⁻³. In equilibrium $E_F$ is flat and the band edges step down from p to n by $qV_{bi}$. Using $n=N_ce^{-(E_c-E_F)/k_BT}$ on each side, show that $V_{bi}=\dfrac{k_BT}{q}\ln\dfrac{N_AN_D}{n_i^2}$, and compute it.

> [!check]- Answer
> 1. $n_{n0}=N_D$ and $n_{p0}=n_i^2/N_A=898$ cm⁻³.
> 2. $E_{c,p}-E_{c,n}=qV_{bi}$, so $\dfrac{n_{p0}}{n_{n0}}=e^{-qV_{bi}/k_BT}$ and therefore $V_{bi}=\dfrac{k_BT}{q}\ln\dfrac{N_D}{n_i^2/N_A}$.
> 3. $V_{bi}=0.02585\ln(1.115\times10^{13})=\boxed{0.777\ \text{V}}$

#### D3.2
For the junction of D3.1: on the p side $D_n=25$ cm²/s and $\tau_n=1\ \mu$s; on the n side $D_p=10$ cm²/s and $\tau_p=1\ \mu$s.
- (a) Find $L_n$, $L_p$ and the saturation current density $J_s=q(D_nn_{p0}/L_n+D_pp_{n0}/L_p)$.
- (b) What fraction of the current do holes carry?
- (c) Find $J$ at $V=0.6$ V, and the $V$ needed for $J=1$ A/cm².
- (d) By what factor does $J$ change for each additional 60 mV of forward bias?

> [!check]- Answer
> - **(a)** $L_n=\sqrt{D_n\tau_n}=50.0\ \mu$m and $L_p=31.6\ \mu$m. $J_s=\boxed{5.27\times10^{-12}\ \text{A/cm}^2}$. Unit check: C·(cm²/s)/cm·cm⁻³ = A/cm².
> - **(b)** Holes carry 86.3%: the lightly doped side has the larger minority population.
> - **(c)** $J(0.6\text{ V})=\boxed{0.0633\ \text{A/cm}^2}$, and $V=k_BT\ln(1/J_s+1)=\boxed{0.671\ \text{V}}$.
> - **(d)** $e^{0.060/0.02585}=\boxed{10.2\times}$ (59.5 mV/decade).

### T4 · Resonance

#### D4.1
A two-terminal network is an inductor $L$ in series with the parallel combination of $R$ and $C$.
- (a) Determine the resonant frequency for $R=50\ \Omega$, $L=2$ mH, $C=1\ \mu$F.
- (b) What is $\mathbf Z_i$ at resonance?
- (c) For what values of $R$ does a nonzero resonant frequency exist?

> [!check]- Answer
> 1. $\mathbf Z_i=j\omega L+\dfrac{R}{1+j\omega RC}$, and $\operatorname{Im}\mathbf Z_i=\omega L-\dfrac{\omega R^2C}{1+\omega^2R^2C^2}=0$.
> 2. **(a)** $\omega_0=\sqrt{\dfrac1{LC}-\dfrac1{R^2C^2}}=\sqrt{5\times10^8-4\times10^8}=\boxed{1.00\times10^4\ \text{rad/s}}$
> 3. **(b)** $\mathbf Z_i=\dfrac{R}{1+\omega_0^2R^2C^2}=\boxed{40.0\ \Omega}$
> 4. **(c)** $R>\sqrt{L/C}=44.7\ \Omega$.

#### D4.2
A two-port ladder: series $R_1$, shunt $C$, series $L$, then shunt $R_2$, with $\mathbf V_o$ across $R_2$. Take $R_1=R_2=1$ kΩ, $L=10$ mH, $C=10$ nF.
- (a) Determine $\mathbf H=\mathbf V_o/\mathbf V_i$.
- (b) Find the frequency at which $\mathbf V_o$ lags $\mathbf V_i$ by exactly 90°, and $\mathbf H$ there.
- (c) Is there any $\omega>0$ at which $\mathbf H$ is purely real? Explain.

> [!check]- Answer
> - **(a)** $\mathbf H=\dfrac{R_2}{R_1+R_2-\omega^2R_1LC+j\omega(L+R_1R_2C)}$ (sympy).
> - **(b)** The real part of the denominator is zero at $\omega=\sqrt{\dfrac{R_1+R_2}{R_1LC}}=\boxed{1.41\times10^5\ \text{rad/s}}$, where $\mathbf H=\boxed{-j0.354}$.
> - **(c)** No. $\operatorname{Im}(\text{den})=\omega(L+R_1R_2C)>0$ for every $\omega>0$.

### T5 · Standard form + straight-line Bode

#### D5.1
Generate Bode magnitude and phase plots (straight-line approximations) for $\mathbf H(\omega)=\dfrac{10^4(5+j\omega)}{j\omega(100+j\omega)(1000+j\omega)}$.

> [!check]- Answer
> Standard form: $\mathbf H=\dfrac{0.5(1+j\omega/5)}{j\omega(1+j\omega/100)(1+j\omega/1000)}$. Constant −6.02 dB; pole at the origin; zero at 5; poles at 100 and 1000.
> - **Magnitude:** a −20 dB/dec line through −6.0 dB at $\omega=1$ (0 dB at 0.5, +14 dB at 0.1); flat −20 dB from 5 to 100; −20 dB/dec to −40 dB at 1000; −40 dB/dec after (−80 dB at $10^4$).
> - **Phase:** −90° up to 0.5; +45°/dec to −45° at 5 and −31.5° at 10; flat from 10 to 50; −45°/dec to −45° at 100; −90°/dec to −135° at 1000; −45°/dec to −180° at $10^4$.
> - Exact checks: −5.85 dB and −79° at $\omega=1$; −43.1 dB and −130° at 1000.

#### D5.2
Generate straight-line Bode plots for
- (a) $\mathbf H_a(\omega)=\dfrac{j40\omega}{1600-\omega^2+j16\omega}$. What is the actual $\lvert\mathbf H_a\rvert$ at the corner frequency?
- (b) $\mathbf H_b(\omega)=\dfrac{-j200(10+j\omega)}{(100+j\omega)^2}$.

> [!check]- Answer
> **(a)** $\mathbf H_a=\dfrac{j0.025\omega}{1-(\omega/40)^2+j\omega/100}$. Constant −32.0 dB; zero at the origin; quadratic pole $\omega_c=40$ with $\xi=0.2$.
> - Magnitude: −32 dB at $\omega=1$, rising +20 dB/dec to 0.0 dB at 40, then −20 dB/dec.
> - Phase: +90° until 4, −90°/dec to −90° at 400.
> - Actual value at 40: $\lvert\mathbf H_a\rvert=\boxed{2.50\ (+7.96\ \text{dB})}$, phase exactly 0°. Bandpass, max gain 2.5.
>
> **(b)** $\mathbf H_b=\dfrac{-j0.2(1+j\omega/10)}{(1+j\omega/100)^2}$. The constant $-j0.2$ gives **−14.0 dB and −90° with no slope**.
> - Magnitude: flat −14 dB to 10; +20 dB/dec to +6.0 dB at 100; −20 dB/dec after (−14 dB at 1000, −34 dB at $10^4$).
> - Phase: −90° up to 1; +45°/dec to −45° at 10; −45°/dec to −90° at 100; −90°/dec to −180° at 1000; flat after.
> - Exact at 100: 0.04 dB (the double pole sits 6 dB under its asymptote).

### T6 · Passive filter type and cutoff

#### D6.1
A two-port: series $L$, then shunt $R$ in parallel with shunt $C$, with $\mathbf V_o$ across $R\parallel C$.
- (a) Obtain $\mathbf H=\mathbf V_o/\mathbf V_i$ in standard form.
- (b) For $L=1$ mH, $C=0.1\ \mu$F and $R=50\ \Omega$, determine $\omega_c$, $\xi$, the filter type, the slope for $\omega/\omega_c\gg1$, and the actual −3 dB frequency.
- (c) What value of $R$ makes $\omega_c$ the −3 dB frequency?

> [!check]- Answer
> - **(a)** $\mathbf H=\dfrac{1}{1+j\omega L/R+(j\omega)^2LC}$, so $\omega_c=1/\sqrt{LC}$ and $\xi=\dfrac1{2R}\sqrt{L/C}$.
> - **(b)** $\omega_c=\boxed{1.00\times10^5\ \text{rad/s}}$ and $\xi=1.00$. Lowpass, −40 dB/dec. $\lvert\mathbf H(\omega_c)\rvert=1/(2\xi)=-6.02$ dB, and the −3 dB point is $\boxed{6.44\times10^4\ \text{rad/s}}$ ($=\omega_c\sqrt{\sqrt2-1}$).
> - **(c)** For $\xi=1/\sqrt2$: $R=\sqrt{L/C}/\sqrt2=\boxed{70.7\ \Omega}$. Check: $\lvert\mathbf H(\omega_c)\rvert=-3.01$ dB.

#### D6.2
A two-port: the parallel combination of $L$ and $C$ is in series with the input, and $R$ is the shunt element at the output ($\mathbf V_o$ across $R$). Take $L=1$ mH, $C=1\ \mu$F, $R=100\ \Omega$.
- (a) Obtain $\mathbf H$ in standard form and identify the filter type.
- (b) Find $\omega_0$, the bandwidth $B$, and the half-power frequencies.
- (c) Give the dB slopes for $\omega\ll\omega_0$ and $\omega\gg\omega_0$.

> [!check]- Answer
> - **(a)** $\mathbf H=\dfrac{1-\omega^2LC}{1-\omega^2LC+j\omega L/R}=\dfrac{1+(j\omega/\omega_0)^2}{1+j2\xi\omega/\omega_0+(j\omega/\omega_0)^2}$, with $\xi=\omega_0L/2R=0.158$. **Bandstop (notch).**
> - **(b)** $\omega_0=\boxed{3.16\times10^4\ \text{rad/s}}$, $B=1/(RC)=\boxed{1.00\times10^4\ \text{rad/s}}$ ($Q=3.16$). $\omega_{c1,c2}=\mp\tfrac B2+\sqrt{(B/2)^2+\omega_0^2}=\boxed{2.70\times10^4,\ 3.70\times10^4\ \text{rad/s}}$ (numerically $\lvert\mathbf H\rvert=0.707$ at both).
> - **(c)** 0 dB/dec at both ends ($\lvert\mathbf H\rvert\to1$). Phase: 0° → −90° just below $\omega_0$ → +90° just above → 0°.

### T7 · Decoupling capacitors, ESR/ESL

#### D7.1
Two capacitors are available: 10 µF (ESR 5 mΩ, ESL 1 nH) and 100 nF (ESR 20 mΩ, ESL 0.5 nH).
- (a) Find each self-resonant frequency.
- (b) Compute $\lvert Z\rvert$ for each at 100 kHz and at 50 MHz.
- (c) Over what frequency range does each behave approximately as an ideal capacitor?
- (d) Which would you choose to decouple a 50 MHz load current, and why?

> [!check]- Answer
> - **(a)** $f_{SR}=1/(2\pi\sqrt{L_{ESL}C})$: $\boxed{1.59\ \text{MHz}}$ for 10 µF and $\boxed{22.5\ \text{MHz}}$ for 100 nF.
> - **(b)** At 100 kHz: 0.159 Ω (10 µF) vs 15.9 Ω (100 nF). At 50 MHz: 0.314 Ω vs **0.127 Ω**. Both are above their self-resonance there, so both act inductively.
> - **(c)** Below about $f_{SR}/10$: roughly up to 160 kHz for the 10 µF and up to 2.3 MHz for the 100 nF.
> - **(d)** The 100 nF. Its smaller ESL gives lower impedance at 50 MHz even though its capacitance is 100× smaller. Use the 10 µF for low-frequency current; in practice put both in parallel.

#### D7.2
In the PS7-7 circuit, take $L_p=20$ nH ($R_p$ ignored) and $C_d=100$ nF, with the capacitor's ESR $R=0.1\ \Omega$ in series (ESL ignored).
- (a) Write $f_2(\omega)$ as an impedance expression.
- (b) Find $\omega_0$.
- (c) Compare $\lvert f_2\rvert$ with and without $C_d$ at $\omega_0/10$, at $\omega_0$ and at $10\omega_0$.
- (d) For an ideal $C_d$ (no ESR), above what frequency does $C_d$ make $\lvert f_2\rvert$ smaller than the bare trace does?

> [!check]- Answer
> - **(a)** $f_2=-\left[j\omega L_p\parallel\left(R+\dfrac1{j\omega C_d}\right)\right]$
> - **(b)** $\omega_0=1/\sqrt{L_pC_d}=\boxed{2.24\times10^7\ \text{rad/s}}$ (3.56 MHz).
> - **(c)** $\lvert f_2\rvert$ with $C_d$ vs without, at three frequencies:
>
> | | With $C_d$ | Without |
> |---|---|---|
> | $\omega_0/10$ | 0.0452 Ω | 0.0447 Ω |
> | $\omega_0$ | 2.05 Ω (≈$L_p/RC_d=2$ Ω; unbounded if $R=0$) | 0.447 Ω |
> | $10\omega_0$ | 0.111 Ω | 4.47 Ω |
>
> - **(d)** Where $\lvert1-\omega^2L_pC_d\rvert>1$, i.e. $\omega>\boxed{\sqrt2\,\omega_0}$.
>
> ESR damps the resonance; that is why a little ESR is useful in decoupling networks. This drill shows the physics behind the PS7-7 warning.

### T8 · Bandpass parameters (variants of PS8 9.26: different topology, parallel RLC; the series-RLC formulas differ, derive them yourself)

#### D8.1
A **parallel** RLC circuit ($R=2$ kΩ, $L=10$ mH, $C=0.1\ \mu$F, all in parallel) is driven by a current source $\mathbf I_s$, and the output is the voltage across the combination ($\mathbf H=\mathbf V/\mathbf I_s$). Determine $\omega_0$, $Q$, $B$, $\omega_{c1}$, $\omega_{c2}$, and the maximum of $\lvert\mathbf H\rvert$.

> [!check]- Answer
> - $\omega_0=1/\sqrt{LC}=3.16\times10^4$ rad/s.
> - $B=1/(RC)=5.00\times10^3$ rad/s.
> - $Q=\omega_0/B=R\sqrt{C/L}=6.32$.
> - $\omega_{c1}=2.92\times10^4$ and $\omega_{c2}=3.42\times10^4$ rad/s; numerically $\lvert\mathbf H\rvert/R=0.707$ at both.
> - $\lvert\mathbf H\rvert_{max}=R=2.00$ kΩ at $\omega_0$.

#### D8.2
Design a parallel RLC bandpass with $R=10$ kΩ, centre frequency 10 kHz and bandwidth 500 Hz. Give $C$, $L$, $Q$ and the half-power frequencies in Hz.

> [!check]- Answer
> - $C=1/(RB)=1/(10^4\cdot2\pi\cdot500)=\boxed{31.8\ \text{nF}}$
> - $L=1/(\omega_0^2C)=\boxed{7.96\ \text{mH}}$
> - $Q=20$
> - $f_{c1}=9.75$ kHz and $f_{c2}=10.25$ kHz.

### T9 · First-order active filter (variants of PS8 9.38: inverting topology with a series-RC input, NOT a non-inverting amplifier with R‖C feedback)

#### D9.1
An inverting op-amp amplifier has $R_1=1$ kΩ in series with $C_1=0.1\ \mu$F from $\mathbf V_s$ to the − input, a feedback resistor $R_2=20$ kΩ, and the + input grounded.
- (a) Obtain $\mathbf H$ in standard form.
- (b) Generate the straight-line plots.
- (c) What type of filter is it, and what is its maximum gain?

> [!check]- Answer
> - **(a)** $\mathbf H=-\dfrac{R_2}{R_1+1/j\omega C_1}=-\dfrac{R_2}{R_1}\dfrac{j\omega/\omega_c}{1+j\omega/\omega_c}$ with $\omega_c=1/(R_1C_1)=10^4$ rad/s.
> - **(b)** Magnitude +20 dB/dec below $\omega_c$, flat 26.0 dB above; at $\omega_c$ the exact value is 23.0 dB. Phase −90° at low frequency, −135° at $\omega_c$, −180° at high frequency.
> - **(c)** **Highpass. Max gain 20 (26.0 dB)** as $\omega\to\infty$.

#### D9.2
Same as D9.1, but now the feedback is $R_2=10$ kΩ in parallel with $C_2=1$ nF, with $R_1=1$ kΩ and $C_1=1\ \mu$F in series at the input.
- (a) Obtain $\mathbf H$ in factored standard form.
- (b) What type of filter is it, and what is its maximum gain?
- (c) Find the −3 dB frequencies.

> [!check]- Answer
> - **(a)** $\mathbf H=-\dfrac{j\omega R_2C_1}{(1+j\omega R_1C_1)(1+j\omega R_2C_2)}=\dfrac{-10\,(j\omega/10^3)}{(1+j\omega/10^3)(1+j\omega/10^5)}$
> - **(b)** **Bandpass.** The straight-line midband is 20 dB, with slopes +20 and −20 dB/dec. The exact maximum is $\boxed{9.90\ (19.9\ \text{dB})}$ at $\sqrt{10^3\cdot10^5}=10^4$ rad/s.
> - **(c)** $\boxed{981\ \text{and}\ 1.02\times10^5\ \text{rad/s}}$. Phase −90° → −180° (at $10^4$) → −270°.

### T10 · Second-order active filter (variants of PS8 9.39: multiple-feedback inverting topology, NOT Sallen–Key)

#### D10.1
**Multiple-feedback circuit:**
- $\mathbf V_i$ → $R_1$ → node A.
- $C_1$ from A to ground.
- $R_2$ from A to $\mathbf V_o$.
- $R_3$ from A to the op-amp − input.
- $C_2$ from the − input to $\mathbf V_o$.
- + input grounded.

Questions:
- (a) Obtain $\mathbf H$ in standard form.
- (b) For $R_1=R_2=R_3=R$, show that $\xi=\tfrac32\sqrt{C_2/C_1}$, and choose $C_2/C_1$ for $\xi=1/\sqrt2$.
- (c) With $R=10$ kΩ, $C_1=90$ nF and $C_2=20$ nF, find $\omega_c$, the filter type, the maximum gain and the high-frequency slope.

> [!check]- Answer
> - **(a)** KCL at A and at the virtual-ground node gives (sympy) $\mathbf H=\dfrac{-R_2/R_1}{1+j\omega C_2\left(R_2+R_3+\dfrac{R_2R_3}{R_1}\right)+(j\omega)^2R_2R_3C_1C_2}$
> - **(b)** $\omega_c=1/(R\sqrt{C_1C_2})$ and $2\xi/\omega_c=3RC_2$, so $\xi=\tfrac32\sqrt{C_2/C_1}$. Setting $\xi=1/\sqrt2$ gives $C_2/C_1=2/9$.
> - **(c)** $\omega_c=\boxed{2.36\times10^3\ \text{rad/s}}$ (375 Hz) and $\xi=0.707$. **Lowpass, max gain 1 (0 dB) at DC**, −40 dB/dec. $\lvert\mathbf H(\omega_c)\rvert=-3.01$ dB. Phase 180° → 90° at $\omega_c$ → 0°.

#### D10.2
**Multiple-feedback bandpass:**
- $\mathbf V_i$ → $R_1$ → node A.
- $R_2$ from A to ground.
- $C_1$ from A to the − input.
- $C_2$ from A to $\mathbf V_o$.
- $R_3$ from the − input to $\mathbf V_o$.
- + input grounded.

Questions:
- (a) Obtain $\mathbf H$ in standard form.
- (b) For $R_1=10$ kΩ, $R_2=1$ kΩ, $R_3=200$ kΩ and $C_1=C_2=10$ nF, find $\omega_0$, $B$, $Q$, the filter type and the gain at $\omega_0$.

> [!check]- Answer
> - **(a)** $\mathbf H=\dfrac{-j\omega\,\dfrac{C_1R_2R_3}{R_1+R_2}}{1+j\omega\dfrac{R_1R_2(C_1+C_2)}{R_1+R_2}+(j\omega)^2\dfrac{R_1R_2R_3C_1C_2}{R_1+R_2}}$
> - **(b)** Values:
>   - $\omega_0=\sqrt{\dfrac{1/R_1+1/R_2}{R_3C_1C_2}}=\boxed{7.42\times10^3\ \text{rad/s}}$ (1.18 kHz).
>   - $B=\dfrac{C_1+C_2}{R_3C_1C_2}=\boxed{1.00\times10^3\ \text{rad/s}}$ and $Q=7.42$.
>   - **Bandpass.** Gain at $\omega_0$: $-\dfrac{R_3C_1}{R_1(C_1+C_2)}=\boxed{-10\ (20\ \text{dB})}$. A numerical sweep confirms the peak of 10.0 and $B=1.00\times10^3$.

### T11 · Active filter design (variants of PS8 9.42: highpass and bandpass specs, NOT lowpass at −60 dB/dec)

#### D11.1
Design an active **highpass** filter with a passband gain of 10, a corner frequency of 500 Hz, and a low-frequency roll-off of +40 dB/decade. Use $C=0.1\ \mu$F capacitors.

> [!check]- Answer
> 1. Each first-order stage gives 20 dB/dec, so +40 dB/dec needs **two cascaded first-order inverting HP stages** (the D9.1 topology), each with $\omega_c=1/(R_1C)=2\pi(500)$. That makes $R_1=\boxed{3.18\ \text{k}\Omega}$.
> 2. Split the gain: stage 1 has $R_2=31.8$ kΩ (gain 10), stage 2 has $R_2=R_1=3.18$ kΩ (gain 1). Two inversions cancel.
> 3. Overall $\mathbf H=10\dfrac{(jf/500)^2}{(1+jf/500)^2}$.
> 4. Checks: $\lvert\mathbf H\rvert$ = 5 at 500 Hz (−6 dB from the passband), 9.90 at 5 kHz, and 0.099 at 50 Hz (+40 dB/dec).
>
> The corner here means the Bode (asymptotic) corner. The cascade's −3 dB point is $500/\sqrt{\sqrt2-1}=777$ Hz. If the spec meant −3 dB, scale both stage corners down by 0.644.

#### D11.2
Design a single-op-amp active **bandpass** filter with a midband gain of 20 dB, corner frequencies 100 Hz and 10 kHz, and ±20 dB/decade skirts. Use $R_1=1$ kΩ.

> [!check]- Answer
> 1. Use the D9.2 topology. $R_2/R_1=10$ gives $R_2=10$ kΩ.
> 2. $C_1=1/(2\pi\cdot100\cdot R_1)=\boxed{1.59\ \mu\text{F}}$ and $C_2=1/(2\pi\cdot10^4\cdot R_2)=\boxed{1.59\ \text{nF}}$.
> 3. Check: peak 9.90 (19.9 dB) at 1 kHz; −3 dB at 98.1 Hz and 10.2 kHz.

### T12 · Op-amp Bode in Hz (variants of PS8 m9.2: different networks, a single-R input with series-RC lead, and a series-RC feedback with a pole at the origin; neither uses R‖C on both sides)

#### D12.1
An inverting op-amp has input network $R_1$ in parallel with the series combination of $R_3$ and $C$, feedback $R_2$, and the + input grounded. Take $R_1=R_2=10$ kΩ, $R_3=1$ kΩ, $C=10$ nF.
- (a) Find $\mathbf H(\omega)$ in standard form.
- (b) Rewrite it as $\mathbf H(f)$.
- (c) Give the low- and high-frequency asymptotes (magnitude and phase) and the corner frequencies.

> [!check]- Answer
> 1. **(a)** $\dfrac1{Z_{in}}=\dfrac1{R_1}+\dfrac{j\omega C}{1+j\omega R_3C}$, so $\mathbf H=-\dfrac{R_2}{R_1}\dfrac{1+j\omega(R_1+R_3)C}{1+j\omega R_3C}$.
> 2. **(b)** $\mathbf H(f)=-\dfrac{R_2}{R_1}\dfrac{1+jf/f_z}{1+jf/f_p}$ with $f_z=\dfrac1{2\pi(R_1+R_3)C}=\boxed{1.45\ \text{kHz}}$ and $f_p=\dfrac1{2\pi R_3C}=\boxed{15.9\ \text{kHz}}$.
> 3. **(c)** Asymptotes:
>    - Low frequency: 0 dB, 180°.
>    - High frequency: $20\log11=\boxed{20.8\ \text{dB}}$, 180°.
>    - The phase rises above 180° between the corners. The maximum lead is about 56° at $\sqrt{f_zf_p}=4.80$ kHz (python gives −123.6° ≡ 236.4° there).

#### D12.2
An inverting op-amp has input $R_1=10$ kΩ and feedback $R_2=47$ kΩ in series with $C_2=10$ nF; the + input is grounded.
- (a) Find $\mathbf H(f)$ in standard form.
- (b) Give the low- and high-frequency asymptotes and the corner frequency.

> [!check]- Answer
> 1. **(a)** $\mathbf H=-\dfrac{R_2+1/j\omega C_2}{R_1}=-\dfrac{1+jf/f_z}{jf/f_1}$ with $f_z=\dfrac1{2\pi R_2C_2}=\boxed{339\ \text{Hz}}$ and $f_1=\dfrac1{2\pi R_1C_2}=1.59$ kHz.
> 2. **(b)** Asymptotes:
>    - Low frequency: an integrator line at −20 dB/dec that would reach 0 dB at $f_1=1.59$ kHz if extended; phase +90°.
>    - High frequency: $20\log4.7=\boxed{13.4\ \text{dB}}$, phase 180°.
>    - One finite corner, at 339 Hz, where the exact value is 16.5 dB at 135°.

### T13 · Sifting integrals (variants of PS8 12.2: time-scaled impulse and impulses outside the limits; likely final-exam material (?))

#### D13.1
Evaluate $\displaystyle\int_{-\infty}^{\infty}(t^2+2)\,\delta(3t-6)\,dt$.

> [!check]- Answer
> $\delta(3t-6)=\tfrac13\delta(t-2)$, so the integral is $\tfrac13(4+2)=\boxed{2}$ (sympy).

#### D13.2
Evaluate
- (a) $\displaystyle\int_{-1}^{3}\cos(\pi t)[\delta(t+2)+\delta(t-1)-2\delta(t-2.5)]\,dt$
- (b) $\displaystyle\int_{0}^{4}e^{-t}[\delta(t-1)+3\delta(t-5)]\,dt$

> [!check]- Answer
> - **(a)** $t=-2$ lies outside the limits, so it contributes 0. $\cos\pi=-1$ and $\cos(2.5\pi)=0$, so the result is $\boxed{-1}$.
> - **(b)** Only $t=1$ is inside the limits: $\boxed{e^{-1}=0.368}$ (sympy).

---

## Key errata summary
1. **8.54:** $\angle\mathbf V_{oc}$ is −146.3°, not −145.3° (a rounding artifact). $\mathbf Z_L=3.31+j2.46$ kΩ, not $3.3+j2.4$. $P=1.41$ mW is correct.
2. **9.20(b) plots:** the magnitude peak should be 38.1 dB, not about 35. The phase needs a kink at 10 rad/s (36.7°) and crosses 0° at 16, not about 13. The setup and bullet list are correct.
3. **PS7 Q7(c)/(d):** I dispute the conclusion. $C_d$ helps above about $\sqrt2\,\omega_0$, and a larger $C_d$ extends the useful band downward. Minor: $f_2$ needs a minus sign to match the stated form.
4. **Definition caveats (not errors):** 9.31's $\omega_c$ is the centre frequency of the bandpass, whose −3 dB band is $1.33\times10^5$–$1.88\times10^6$ rad/s. 9.34's −3 dB point is at $7.86\times10^3$ rad/s, not $\omega_c=10^4$.
5. **PS6-4:** the key's $n$ and $p$ differ in the 4th digit only because of rounding; the exact value is $9.475\times10^9$ cm⁻³ for both.
