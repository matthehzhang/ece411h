---
course: ECE 411H
kind: problem-set-solution
source: Problem Sets/ECE_411H_PS7_solns_F26.pdf
source_pages: 17
author: Prof. Ed Yu / TA (pp. 1–15 are publisher solutions, © 2016 National Technology and Science Press; pp. 16–17 are handwritten tablet notes for Problem 7, author TA/instructor)
unit: exam2
topics: [resonance, resonant-frequency, input-impedance, transfer-function, rationalize, bode-plot, straight-line-approximation, standard-form, simple-zero, simple-pole, zero-at-origin, quadratic-pole, damping-ratio, passive-filter, bandpass, highpass, cutoff-frequency, asymptotic-slope, decoupling-capacitor, parasitic-inductance, esr, esl, self-resonance]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; text layer via pdftotext -layout where present
---

# ECE 411H: Problem Set 7 Solutions

**Summary**
Typeset publisher solutions to 9.2, 9.6, 9.18, 9.20, 9.31, 9.34 plus handwritten solutions to the instructor's decoupling-capacitor Problem 7. Key results: 9.2 resonant frequency $\omega_0 = \sqrt{R^2/(R^2LC - L^2)} = 2\times 10^4$ rad/s by setting Im$\{\mathbf{Z}_i\} = 0$; 9.6 $\mathbf{H} = -\omega^2RL_1C/[R(1-\omega^2L_1C) + j\omega(L_1+L_2-\omega^2L_1L_2C)]$, real at $\omega_0 = \sqrt{(L_1+L_2)/(L_1L_2C)}$; 9.18/9.20 each transfer function rewritten in standard form with constant-term dB value, corner frequencies, and full straight-line magnitude and phase plots (including a quadratic pole at 50 rad/s, a double quadratic pole at 16 rad/s with −80 dB/decade, and a double simple pole at 20 rad/s); 9.31 bandpass with $\omega_c = 1/\sqrt{R_1R_2C_1C_2} = 0.5\times 10^6$ rad/s, $\xi = 7/4$, slopes +20/−20 dB/decade; 9.34 highpass with $\omega_c = 1/\sqrt{LC} = 10^4$ rad/s, $\xi = 0.5$, +40 dB/decade. Problem 7: $v_o = f_1V_i + f_2 i_L$ with $f_1 = 1/(1-\omega^2L_pC_d)$, $f_2 = j\omega L_p/(1-\omega^2L_pC_d)$; decoupling works below $\sim\frac{1}{10}\cdot 1/\sqrt{L_pC_d}$; real capacitor $Z = R_{ESR} + j\omega L_{ESL} + 1/j\omega C$ with a V-shaped $|Z|$ and minimum $R_{ESR}$ at self-resonance. This is the core Bode-plot/filter material for Exam 2.

## Page 1

**ECE 411H: Problem Set 7 Solutions**

**Problem 9.2** Determine the resonant frequency of the circuit shown in Fig. P9.2, given that $R = 100\ \Omega$, $L = 5$ mH, and $C = 1\ \mu$F.

**Figure P9.2: Circuit for Problem 9.2.** Two open-circle terminals on the left; an arrow labeled $\mathbf{Z}_i$ (blue) points into the network from the terminals. Top wire: capacitor $C$ in series; then $L$ and $R$ in parallel (two vertical branches) down to the bottom wire, which returns to the lower terminal.

**Solution:**
$$\mathbf{Z}_i = (R\parallel j\omega L) + \frac{1}{j\omega C}$$
$$= \frac{j\omega LR}{R + j\omega L} + \frac{1}{j\omega C}$$
$$= \frac{-\omega^2RLC + R + j\omega L}{-\omega^2LC + j\omega RC}.$$

After a few steps of algebra, the expression simplifies to
$$\mathbf{Z}_i = \frac{\omega^4RL^2C^2 - j\omega[\omega^2(L^2C - R^2LC^2) + R^2C]}{\omega^4L^2C^2 + \omega^2R^2C^2}.$$

At resonance, the imaginary part of $\mathbf{Z}_i$ is zero. Thus,
$$\omega[\omega^2(L^2C - R^2LC^2) + R^2C] = 0,$$
which gives $\omega_0 = 0$ (trivial resonance) and
$$\omega_0 = \sqrt{\frac{R^2}{R^2LC - L^2}}$$
$$= \sqrt{\frac{10^4}{10^4\times 5\times 10^{-3}\times 10^{-6} - 25\times 10^{-6}}}$$
$$= 2\times 10^4\ \text{rad/s}.$$

Footer: All rights reserved. Do not reproduce or distribute. © 2016 National Technology and Science Press

## Page 2

**Problem 9.6** For the circuit shown in Fig. P9.6, determine (a) the transfer function $\mathbf{H} = \mathbf{V}_o/\mathbf{V}_i$, and (b) the frequency $\omega_0$ at which $\mathbf{H}$ is purely real.

**Figure P9.6: Circuit for Problem 9.6.** Input port $\mathbf{V}_i$ (+ top, − bottom) on left. Top wire: series $C$, then node $\mathbf{V}_1$ (blue dot), then series $L_2$ to the output node. Shunt $L_1$ from node $\mathbf{V}_1$ to the bottom wire; shunt $R$ from the output node to the bottom wire. Output port $\mathbf{V}_o$ (+ top, − bottom) across $R$.

**Solution:**
**(a)** KCL at node $\mathbf{V}_1$ gives:
$$\frac{\mathbf{V}_1 - \mathbf{V}_i}{\mathbf{Z}_C} + \frac{\mathbf{V}_1}{\mathbf{Z}_{L_1}} + \frac{\mathbf{V}_1}{R + \mathbf{Z}_{L_2}} = 0,$$
where $\mathbf{Z}_C = 1/j\omega C$, $\mathbf{Z}_{L_1} = j\omega L_1$, and $\mathbf{Z}_{L_2} = j\omega L_2$.
Also, voltage division gives
$$\mathbf{V}_o = \frac{\mathbf{V}_1 R}{R + j\omega L_2}.$$
Solving for the transfer function gives
$$\mathbf{H} = \frac{\mathbf{V}_o}{\mathbf{V}_i} = \frac{-\omega^2RL_1C}{R(1 - \omega^2L_1C) + j\omega(L_1 + L_2 - \omega^2L_1L_2C)}.$$

**(b)** We need to rationalize the expression for $\mathbf{H}$:
$$\mathbf{H} = \frac{-\omega^2RL_1C}{R(1 - \omega^2L_1C) + j\omega(L_1 + L_2 - \omega^2L_1L_2C)}\times\frac{R(1 - \omega^2L_1C) - j\omega(L_1 + L_2 - \omega^2L_1L_2C)}{R(1 - \omega^2L_1C) - j\omega(L_1 + L_2 - \omega^2L_1L_2C)}$$
$$= \frac{-\omega^2R^2L_1C(1 - \omega^2L_1C) + j\omega^3RL_1C(L_1 + L_2 - \omega^2L_1L_2C)}{R^2(1 - \omega^2L_1C)^2 + \omega^2(L_1 + L_2 - \omega^2L_1L_2C)^2}.$$

The imaginary part of $\mathbf{H}$ is zero if $\omega = 0$ (trivial solution) or if
$$\omega_0 = \sqrt{\frac{L_1 + L_2}{L_1L_2C}}.$$

Footer: All rights reserved. Do not reproduce or distribute. © 2016 National Technology and Science Press

## Page 3

**Problem 9.18** Generate Bode magnitude and phase plots (straight-line approximation) for the following voltage transfer functions:

(a) $\mathbf{H}(\omega) = \dfrac{30(10 + j\omega)}{(200 + j2\omega)(1000 + j2\omega)}$

(b) $\mathbf{H}(\omega) = \dfrac{j100\omega}{(100 + j5\omega)(100 + j\omega)^2}$

(c) $\mathbf{H}(\omega) = \dfrac{(200 + j2\omega)}{(50 + j5\omega)(1000 + j\omega)}$

**Solution:**
**(a)**
$$\mathbf{H}(\omega) = \frac{30(10 + j\omega)}{(200 + j2\omega)(1000 + j2\omega)} = \frac{300(1 + j\omega/10)}{200\times 1000(1 + j\omega/100)(1 + j\omega/500)}$$
$$= \frac{1.5\times 10^{-3}(1 + j\omega/10)}{(1 + j\omega/100)(1 + j\omega/500)}$$

- Constant term $1.5\times 10^{-3}$ ⟹ $-56.5$ dB
- Simple zero with $\omega_c = 10$ rad/s
- Simple pole with $\omega_c = 100$ rad/s
- Simple pole with $\omega_c = 500$ rad/s

(Rest of page blank.) Footer: All rights reserved. Do not reproduce or distribute. © 2016 National Technology and Science Press

## Page 4

**Figure: Bode magnitude plot for 9.18(a).** Vertical axis dB with ticks 40, 20, 0, −20, −36.5, −40, −56.5, −60; horizontal log axis $\omega$ (rad/s) with decades 1, 10, 100, 1000, 10000. Dashed component lines: green "$20\log|1 + j\omega/10|$" — 0 dB up to $\omega = 10$, then rising +20 dB/decade; dark-blue "$-20\log|1 + j\omega/100|$" — 0 dB up to 100, then falling −20 dB/decade; red "$-20\log|1 + j\omega/500|$" — 0 dB up to 500, then falling −20 dB/decade. Black dotted horizontal line at −56.5 dB labeled "−56.5 dB"; a second dotted line at −36.5 dB. Solid light-blue composite $M$[dB]: flat at −56.5 dB from 1 to 10; rises +20 dB/decade from 10 to 100, reaching −36.5 dB; flat at −36.5 dB from 100 to 500; falls −20 dB/decade above 500 (about −63 dB at 10000). Caption: Magnitude.

**Figure: Bode phase plot for 9.18(a).** Vertical axis $\phi$ (labeled "f" in the typeset font) with ticks 90°, 45°, 0, −45°, −90°; horizontal $\omega$ 1 to 10000. Green dashed "$(1 + j\omega/10)$": 0° at $\omega = 1$, rising linearly (on log axis) to 90° at $\omega = 100$, flat 90° thereafter. Dark-blue dashed "$\frac{1}{(1 + j\omega/100)}$": 0° until 10, falling to −90° at 1000, flat after. Red dashed "$\frac{1}{(1 + j\omega/500)}$": 0° until 50, falling to −90° at 5000, flat after. Solid light-blue "$\phi(\omega)$": rises from 0° at 1 to 45° at 10; flat 45° from 10 to 50; then decreases (through 0° near a few hundred rad/s) to about −60° at 1000 and −90° at 5000; flat −90° thereafter. Caption: Phase.

**(b)**
$$\mathbf{H}(\omega) = \frac{j100\omega}{(100 + j5\omega)(100 + j\omega)^2} = \frac{j10^{-4}\omega}{(1 + j\omega/20)(1 + j\omega/100)^2}$$

- Constant term $10^{-4}$ ⟹ $-80$ dB
- Zero @ origin
- Simple pole with $\omega_c = 20$ rad/s
- Simple pole with $\omega_c = 100$ rad/s, of order 2

Footer: All rights reserved. Do not reproduce or distribute. © 2016 National Technology and Science Press

## Page 5

**Figure: Bode magnitude plot for 9.18(b).** dB axis ticks 20, 0, −20, −40, −54, −60, −80, −94, −100; $\omega$ decades 1, 10, 100, 1000, 10000. Dark-blue dashed "$20\log\omega$": straight line through 0 dB at $\omega = 1$ rising +20 dB/decade. Red dashed "$-20\log|1 + j\omega/20|$": 0 dB until 20, then −20 dB/decade. Green dashed "$-40\log|1 + j\omega/100|$": 0 dB until 100, then −40 dB/decade. Black dashed horizontal line at −80 dB labeled "−80 dB"; dotted lines at −54 and −94 dB. Solid light-blue "$M$[dB]": starts at −80 dB at $\omega = 1$, rises +20 dB/decade to −54 dB at $\omega = 20$; flat at −54 dB from 20 to 100; falls −40 dB/decade above 100 (−94 dB at 1000, continuing down off the plot). Caption: Magnitude.

**Figure: Bode phase plot for 9.18(b).** Axis ticks 90°, 45°, 0, −45°, −90°, −180°; $\omega$ 1 to 1000. Black dashed horizontal at 90° labeled "$j$" (zero at origin). Red dashed "$\frac{1}{(1 + j\omega/20)}$": 0° until 2, falling to −90° at 200, flat after. Green dashed "$\frac{1}{(1 + j\omega/100)}$" (order 2, so slope −90°/decade): 0° until 10, falling to −180° at 1000. (A small arrow connects the label "1/(1+jω/100)" to the green curve.) Solid light-blue "$\phi(\omega)$": 90° from 1 to 2; falls −45°/decade from 2 to 10 (about 58°); falls steeply (−135°/decade) from 10 to 20 (about 18°); falls −90°/decade from 20 to 200 (through 0° near 30 rad/s, reaching about −117° at 200); continues falling to −180° at 1000; flat −180° after. Caption: Phase.

**(c)**
$$\mathbf{H}(\omega) = \frac{(200 + j2\omega)}{(50 + j5\omega)(1000 + j\omega)} = \frac{(1 + j\omega/100)}{250(1 + j\omega/10)(1 + j\omega/1000)}$$

- Constant term $1/250$ ⟹ $-48$ dB
- Simple pole with $\omega_c = 10$ rad/s

Footer: All rights reserved. Do not reproduce or distribute. © 2016 National Technology and Science Press

## Page 6

- Simple zero with $\omega_c = 100$ rad/s
- Simple pole with $\omega_c = 1000$ rad/s

**Figure: Bode magnitude plot for 9.18(c).** dB ticks 20, 0, −20, −40, −48, −60, −68, −80, −88, −100; $\omega$ decades 1, 10, 100, 1000, 10,000. Green dashed "$20\log|1 + j\omega/100|$": 0 until 100, rising +20 dB/decade. Dark-blue dashed "$-20\log|1 + j\omega/1000|$": 0 until 1000, falling −20 dB/decade. Red dashed "$-20\log|1 + j\omega/10|$": 0 until 10, falling −20 dB/decade. Black dotted horizontal lines at −48 dB (labeled "−48 dB"), −68 dB, and −88 dB. Solid light-blue "$M$[dB]": flat −48 dB from 1 to 10; falls −20 dB/decade from 10 to 100 reaching −68 dB; flat −68 dB from 100 to 1000; falls −20 dB/decade from 1000 to 10,000 reaching −88 dB. Caption: Magnitude.

**Figure: Bode phase plot for 9.18(c).** Ticks 90°, 0, −90°; $\omega$ 1 to 10,000. Green dashed "$(1 + j\omega/100)$": 0° until 10, rising to 90° at 1000, flat after. Dark-blue dashed "$\frac{1}{1 + j\omega/1000}$": 0° until 100, falling to −90° at 10,000. Red dashed "$\frac{1}{1 + j\omega/10}$": 0° at 1, falling to −90° at 100, flat after. Solid light-blue "$\phi(\omega)$": falls from 0° at 1 to −45° at 10; flat at −45° from 10 to 1000 (pole-at-10 fall cancels zero-at-100 rise over 10–100; zero rise cancels pole-at-1000 fall over 100–1000); then falls −45°/decade from 1000 to 10,000 reaching −90°. Caption: Phase.

Footer: All rights reserved. Do not reproduce or distribute. © 2016 National Technology and Science Press

## Page 7

**Problem 9.20** Generate Bode magnitude and phase plots (straight-line approximation) for the following voltage transfer functions:

(a) $\mathbf{H}(\omega) = \dfrac{j5\times 10^3\omega(20 + j2\omega)}{(2500 - \omega^2 + j20\omega)}$

(b) $\mathbf{H}(\omega) = \dfrac{512(1 + j\omega)(4 + j40\omega)}{(256 - \omega^2 + j32\omega)^2}$

(c) $\mathbf{H}(\omega) = \dfrac{j(10 + j\omega)\times 10^8}{(20 + j\omega)^2(500 + j\omega)(1000 + j\omega)}$

**Solution:**
**(a)**
$$\mathbf{H}(\omega) = \frac{j5\times 10^3\omega(20 + j2\omega)}{(2500 - \omega^2 + j20\omega)} = \frac{j5\times 10^3\times 20\omega(1 + j\omega/10)}{2500[1 - (\omega/50)^2 + j\omega/125)}$$
$$= \frac{j40\omega(1 + j\omega/10)}{[1 - (\omega/50)^2 + j\omega/125)}$$
(Bracket mismatch "[ ... )" is as printed.)

- Constant term 40 ⟹ 32 dB
- Zero @ origin
- Simple zero with $\omega_c = 10$ rad/s
- Quadratic pole with $\omega_c = 50$ rad/s

(Rest of page blank.) Footer: All rights reserved. Do not reproduce or distribute. © 2016 National Technology and Science Press

## Page 8

**Figure: Bode magnitude plot for 9.20(a).** dB ticks 80, 52, 40, 32, 0, −40; $\omega$ axis labeled 1, 5, 10, 50, 100, 500, 1000 (rad/s). Green dashed "$20\log\omega$": through 0 dB at $\omega = 1$, +20 dB/decade. Red dashed "$20\log|1 + j\omega/10|$": 0 until 10, then +20 dB/decade. Dark-blue dashed "Quadratic @ 50 rad/s": 0 until 50, then −40 dB/decade (reaching −40 dB at 500). Black dotted horizontals at 32 dB (labeled "32 dB") and 52 dB. Solid light-blue "$M$[dB]": 32 dB at $\omega = 1$; rises +20 dB/decade to 52 dB at 10; rises +40 dB/decade from 10 to 50 reaching 80 dB; flat at 80 dB above 50. Caption: Magnitude.

**Figure: Bode phase plot for 9.20(a).** Ticks 180°, 90°, 0, −180°; same $\omega$ axis. Red/green dashed horizontal at 90° labeled "$j$". Red dashed "Zero @ 10 rad/s": 0° at 1, rising +45°/decade to 90° at 100, flat after. Dark-blue dashed "Quadratic": 0° until 5, falling −90°/decade to −180° at 500, flat after. Solid light-blue "$\phi(\omega)$": 90° at 1, rising to a peak of about 120° at 5, then falling (−45°/decade) to about 107° at 10 and about 63° at 100, then −90°/decade to 0° at 500; flat 0° after 500. Caption: Phase.

**(b)**
$$\mathbf{H}(\omega) = \frac{512(1 + j\omega)(4 + j40\omega)}{(256 - \omega^2 + j32\omega)^2}$$
$$= \frac{512\times 4(1 + j\omega)(1 + j\omega/0.1)}{256^2[1 - (\omega/16)^2 + j\omega/8]^2}$$
$$= \frac{(1 + j\omega/0.1)(1 + j\omega)}{32[1 - (\omega/16)^2 + j\omega/8]^2}$$

- Constant term $1/32$ ⟹ $-30.1$ dB
- Simple zero with $\omega_c = 0.1$ rad/s

Footer: All rights reserved. Do not reproduce or distribute. © 2016 National Technology and Science Press

## Page 9

- Simple zero with $\omega_c = 1$ rad/s
- Quadratic pole of order 2 with $\omega_c = 16$ rad/s

**Figure: Bode magnitude plot for 9.20(b).** dB ticks 40, 20, 0, −20, −40, −60, −80; $\omega$ decades 0.01, 0.1, 1, 10, 100, 1000, with tick marks labeled 16 and 160. Green dashed (zero at 0.1): 0 dB until 0.1, then +20 dB/decade. Red dashed (zero at 1): 0 dB until 1, then +20 dB/decade. Dark-blue dashed (quadratic pole, order 2, at 16): 0 dB until 16, then "−80 dB/decade" (labeled). Dashed horizontal at −30.1 dB labeled "−30.1 dB". Solid light-blue "$M$[dB]": flat −30.1 dB from 0.01 to 0.1; rises +20 dB/decade to about −10 dB at 1; rises +40 dB/decade from 1 to 16 to a peak of about +38 dB at 16; falls −40 dB/decade (net of +40 and −80) above 16, reaching about −42 dB at 1000. Caption: Magnitude.

**Figure: Bode phase plot for 9.20(b).** Ticks 180°, 90°, 0, −90°, −180°, −270°, −360°; $\omega$ 0.01 to 1000 with marks 1.6 and 160. Green dashed (zero at 0.1): 0° at 0.01, rising to 90° at 1, flat. Red dashed (zero at 1): 0° at 0.1, rising to 90° at 10, flat. Dark-blue dashed "Quadratic pole, second order": 0° until 1.6, falling −180°/decade to −360° at 160, flat. Solid light-blue "$\phi(\omega)$": rises from 0° at 0.01 to 45° at 0.1, to 135° at 1, to a peak of about 150° at 1.6; then falls steeply, crossing 0° near 10 rad/s, reaching −180° at 160; flat at −180° thereafter. Caption: Phase.

Footer: All rights reserved. Do not reproduce or distribute. © 2016 National Technology and Science Press

## Page 10

**(c)**
$$\mathbf{H}(\omega) = \frac{j(10 + j\omega)\times 10^8}{(20 + j\omega)^2(500 + j\omega)(1000 + j\omega)}$$
$$= \frac{j10\times 10^8(1 + j\omega/10)}{20^2\times 500\times 1000(1 + j\omega/20)^2(1 + j\omega/500)(1 + j\omega/1000)}$$
$$= \frac{j5(1 + j\omega/10)}{(1 + j\omega/20)^2(1 + j\omega/500)(1 + j\omega/1000)}$$

- Constant term 5 ⟹ 14 dB
- Simple zero with $\omega_c = 10$ rad/s
- Simple pole of order 2 with $\omega_c = 20$ rad/s
- Simple pole with $\omega_c = 500$ rad/s
- Simple pole with $\omega_c = 1000$ rad/s

(Rest of page blank.) Footer: All rights reserved. Do not reproduce or distribute. © 2016 National Technology and Science Press

## Page 11

**Figure: Bode magnitude plot for 9.20(c).** dB ticks 20, 14, 0, −20, −40, −60, −80; $\omega$ decades 1, 10, 100, 1000, 10000. Green dashed (zero at 10): 0 until 10, +20 dB/decade. Red dashed labeled "Pole of order 2" (at 20): 0 until 20, −40 dB/decade. Olive dashed (pole at 500): 0 until 500, −20 dB/decade. Dark-blue dashed (pole at 1000): 0 until 1000, −20 dB/decade. Dashed horizontal at 14 dB labeled "14 dB". Solid light-blue "$M$[dB]": flat 14 dB from 1 to 10; rises +20 dB/decade to 20 dB at 20; falls −20 dB/decade from 20 to 500 (about −8 dB at 500); falls −40 dB/decade from 500 to 1000 (about −20 dB at 1000); falls −60 dB/decade above 1000 (about −80 dB at 10000). Caption: Magnitude.

**Figure: Bode phase plot for 9.20(c).** Ticks 180°, 90°, 0, −90°, −180°, −270°; $\omega$ 1 to 10000 with marks 50 and 500 on the axis. Black dashed horizontal at 90° labeled "$j$". Green dashed (zero at 10): 0° at 1 rising to 90° at 100. Red dashed (pole order 2 at 20): 0° at 2, falling −90°/decade to −180° at 200, flat. Olive dashed (pole at 500): 0° at 50, falling to −90° at 5000. Dark-blue dashed (pole at 1000): 0° at 100, falling to −90° at 10000. Solid light-blue "$\phi(\omega)$": 90° at 1, rising slightly to about 103° at 2, then falling: about 72° at 10, about 40° at 50, crossing 0° near 100, about −40° at 200, about −100° at 1000, reaching −180° at 10000. Caption: Phase.

Footer: All rights reserved. Do not reproduce or distribute. © 2016 National Technology and Science Press

## Page 12

**Problem 9.31** For the circuit shown in Fig. P9.31:
(a) Obtain an expression for $\mathbf{H}(\omega) = \mathbf{V}_o/\mathbf{V}_i$ in standard form.
(b) Generate spectral plots for the magnitude and phase of $\mathbf{H}(\omega)$, given that $R_1 = 1\ \Omega$, $R_2 = 2\ \Omega$, $C_1 = 1\ \mu$F, and $C_2 = 2\ \mu$F.
(c) Determine the cutoff frequency $\omega_c$ and the slope of the magnitude (in dB) when $\omega/\omega_c \ll 1$ and when $\omega/\omega_c \gg 1$.

**Figure P9.31: Circuit for Problem 9.31.** Input $\mathbf{V}_i$ (+ top, − bottom) on left. Top wire: series $R_1$, node $\mathbf{V}_1$ (blue dot), series $C_2$, output node. Shunt $C_1$ from $\mathbf{V}_1$ to bottom wire (with a ground symbol at the bottom of $C_1$); shunt $R_2$ from output node to bottom wire. Output $\mathbf{V}_o$ (+ top, − bottom) across $R_2$.

**Solution: (a)** At node $\mathbf{V}_1$, KCL gives:
$$\frac{\mathbf{V}_1 - \mathbf{V}_i}{R_1} + \frac{\mathbf{V}_1}{\mathbf{Z}_{c_1}} + \frac{\mathbf{V}_1}{\mathbf{Z}_{c_2} + R_2} = 0.$$
Voltage division gives
$$\mathbf{V}_o = \frac{R_2\mathbf{V}_1}{\mathbf{Z}_{c_2} + R_2}.$$
With $\mathbf{Z}_{c_1} = 1/j\omega C_1$ and $\mathbf{Z}_{c_2} = 1/j\omega C_2$, solution is
$$\mathbf{H}(\omega) = \frac{\mathbf{V}_o}{\mathbf{V}_i} = \frac{j\omega R_2C_2}{(1 + j\omega R_1C_1)(1 + j\omega R_2C_2) + j\omega R_1C_2}.$$
To express denominator in standard form, we expand it to get
$$\mathbf{H}(\omega) = \frac{j\omega R_2C_2}{1 + j\omega(R_1C_1 + R_2C_2 + R_1C_2) + (j\omega\sqrt{R_1R_2C_1C_2})^2}$$
$$= \frac{j\omega K}{1 + j2\xi\omega/\omega_c + (j\omega/\omega_c)^2},$$
where
$$K = R_2C_2,\qquad \omega_c = \frac{1}{\sqrt{R_1R_2C_1C_2}},$$
$$\xi = \frac12\omega_c[R_1C_1 + R_2C_2 + R_1C_2].$$

**(b)** For $R_1 = 1\ \Omega$, $R_2 = 2\ \Omega$, $C_1 = 1\ \mu$F, and $C_2 = 2\ \mu$F.
$$K = 4\times 10^{-6},\qquad \omega_c = 0.5\times 10^6\ \text{rad/s},$$
$$\xi = \frac74.$$
Hence,
$$\mathbf{H}(\omega) = \frac{j4\times 10^{-6}\omega}{1 + j\frac72\omega/\omega_c + (j\omega/\omega_c)^2},$$

Footer: All rights reserved. Do not reproduce or distribute. © 2016 National Technology and Science Press

## Page 13

with $\omega_c = 0.5\times 10^6$ rad/s.
$$M\ [\text{dB}] = 20\log|\mathbf{H}(\omega)|$$
Spectral plots of $M$ [dB] and $\phi(\omega)$ are shown in Figs. P9.31(a) and (b).

**Figure: Figures P9.31(a) and (b)** (MATLAB-style plots, blue solid curves on dotted log grid). (a) $M$ (dB) vs $\omega$, vertical ticks 0, −20, −40, −60, −80; horizontal $10^3$ to $10^9$. The curve starts near −48 dB at $\omega = 10^3$, rises at +20 dB/decade, rounds over to a broad maximum of about −5 dB near $\omega \approx 5\times 10^5$, then falls at −20 dB/decade to about −60 dB at $10^9$. (b) $\phi$ (deg) vs $\omega$, vertical ticks 100, 0, −100; horizontal $10^3$ to $10^9$. The phase is about +90° at $10^3$, stays near 90° until roughly $10^5$, decreases smoothly through 0° near $5\times 10^5$, reaches about −90° by $10^7$, and stays at −90° to $10^9$.

**(c)** From part (b), the cutoff frequency of the quadratic pole is
$$\omega_c = 0.5\times 10^6\ \text{rad/s}.$$
Low-frequency asymptote ($\omega/\omega_c \ll 1$):
$$\mathbf{H}(\omega)\simeq j4\times 10^{-6}\omega\quad\Longrightarrow\quad\text{slope of } M\ [\text{dB}] \text{ is } +20\ \text{dB/decade}.$$
High-frequency asymptote ($\omega/\omega_c \gg 1$):
$$\mathbf{H}(\omega)\simeq\frac{j4\times 10^{-6}\omega}{j^2\omega^2/\omega_c^2} = -j\frac{4\times 10^{-6}\omega_c^2}{\omega} = \frac{-j10^6}{\omega}\quad\Longrightarrow\quad\text{slope} = -20\ \text{dB/decade}.$$

Footer: All rights reserved. Do not reproduce or distribute. © 2016 National Technology and Science Press

## Page 14

**Problem 9.34** For the circuit shown in Fig. P9.34:
(a) Obtain an expression for $\mathbf{H}(\omega) = \mathbf{V}_o/\mathbf{V}_i$ in standard form.
(b) Generate spectral plots for the magnitude and phase of $\mathbf{H}(\omega)$, given that $R = 10\ \Omega$, $L = 1$ mH, and $C = 10\ \mu$F.
(c) Determine the cutoff frequency $\omega_c$ and the slope of the magnitude (in dB) when $\omega/\omega_c \ll 1$.

**Figure P9.34: Circuit for Problem 9.34.** Input $\mathbf{V}_i$ (+ top, − bottom); series $C$ on the top wire; then shunt $L$ and shunt $R$ in parallel to the bottom wire; output $\mathbf{V}_o$ (+ top, − bottom) across the parallel $L \parallel R$.

**Solution:**
**(a)** Voltage division yields
$$\mathbf{H}(\omega) = \frac{\mathbf{V}_o}{\mathbf{V}_i} = \frac{(R\parallel j\omega L)}{1/j\omega C + (R\parallel j\omega L)}$$
$$= \frac{-\omega^2LC}{1 + j\omega L/R + j^2\omega^2LC}$$
$$= \frac{-(\omega/\omega_c)^2}{1 + j2\xi\omega/\omega_c + (j\omega/\omega_c)^2},$$
with
$$\omega_c = \frac{1}{\sqrt{LC}},\qquad \xi = \frac{\omega_cL}{2R}.$$

**(b)** For $R = 10\ \Omega$, $L = 1$ mH, and $C = 10\ \mu$F,
$$\omega_c = 10^4\ \text{rad/s},\qquad \xi = 0.5.$$
Spectral plots of $M$ [dB] and $\phi(\omega)$ are shown in Figs. P9.34(a) and (b).

(Rest of page blank.) Footer: All rights reserved. Do not reproduce or distribute. © 2016 National Technology and Science Press

## Page 15

**Figure: Figures P9.34(a) and (b)** (MATLAB-style plots). (a) $M$ (dB) vs $\omega$, vertical ticks 20, 0, −20, −40, −60, −80; horizontal $10^2$ to $10^7$. The curve starts at −80 dB at $\omega = 10^2$, rises linearly at +40 dB/decade to about 0 dB at $\omega = 10^4$ (with a very slight overshoot of about +1 dB just above $10^4$, since $\xi = 0.5$), then is flat at 0 dB from about $2\times 10^4$ to $10^7$. (b) $\phi$ (deg) vs $\omega$, vertical ticks 100, 0, −100; horizontal $10^2$ to $10^7$. Phase is 180° at $10^2$, flat until about $3\times 10^3$, falls smoothly through 90° at $10^4$ to about 0° by $10^5$, and stays at 0° to $10^7$.

**(c)** For $\omega/\omega_c \ll 1$,
$$\mathbf{H}(\omega)\simeq -\left(\frac{\omega}{\omega_c}\right)^2\quad\Longrightarrow\quad\text{slope} = +40\ \text{dB/decade}.$$

Footer: All rights reserved. Do not reproduce or distribute. © 2016 National Technology and Science Press

## Page 16

(Handwritten on digital ruled paper, black ink with red, blue, light-blue, and orange annotations.)

**7. a i)**

**Figure:** Circuit: voltage source $V_i$ (circle, ± ) on the left; top wire passes through inductor $L_p$ and resistor $R_p$, both inside a red box labeled "Board Parasitics" in red; a red diagonal slash is drawn through $R_p$ (indicating it is neglected/removed). Node $v_o$ on the top wire after the parasitics. Between the top wire and the bottom wire, where the capacitor would be, two small open circles with a red arrow labeled "no cap" (the capacitor is absent). On the right, a current source $i_L(t)$ (circle with arrow pointing down) from the $v_o$ node to the bottom wire.

$$\frac{V_i - v_o}{j\omega L_p} = i_L(t)\ \Rightarrow\ v_o = V_i - j\omega L_p\,i_L(t)$$
(blue annotation: an arrow pointing up at $V_i$ labeled "$f_1 = 1$"; a blue brace under $j\omega L_p$ labeled "$f_2$".)

**ii)**

**Figure:** Same circuit as above (source $V_i$, red "Board Parasitics" box containing $L_p$ and slashed-out $R_p$, node $v_o$), now with a capacitor $C_d$ in shunt from the $v_o$ node to the bottom wire, and the current source $i_L(t)$ (arrow down) on the right.

$$\frac{V_i - v_o}{j\omega L_p} = \frac{v_o}{1/j\omega C_d} + i_L\ \Rightarrow\ v_o\left[\frac{1}{1/j\omega C_d} + \frac{1}{j\omega L_p}\right] = \frac{V_i}{j\omega L_p} - i_L$$
(red annotation with an arrow from the bracket: "$= j\omega C_d + \frac{1}{j\omega L_p} = \frac{1 - \omega^2L_pC_d}{j\omega L_p}$")
$$\Rightarrow v_o = \frac{\cancel{j\omega L_p}}{1 - \omega^2L_pC_d}\cdot\frac{V_i}{\cancel{j\omega L_p}} - \frac{j\omega L_p}{1 - \omega^2L_pC_d}\,i_L = \underbrace{\frac{1}{1 - \omega^2L_pC_d}}_{f_1}V_i - \underbrace{\frac{j\omega L_p}{1 - \omega^2L_pC_d}}_{f_2}i_L$$
(the two cancelled $j\omega L_p$ factors have red slashes; blue braces label $f_1$ and $f_2$.)

**b)** $f_1(\omega)\to 1$, $f_2(\omega)\to 0$

(red note:) ($f_1 \gg f_2$ is not quite correct since $f_1 = 1\text{E}{-5}$, $f_2 = 1\text{E}{-10}$ would still be terrible for $v_o$)

**c)**

**Figure:** Log-log sketch of $|f_1|$ (red) and $|f_2|$ (blue) vs $\omega$. Vertical axis labeled "$|f_1|$" (red) and "$|f_2|$" (blue) with an arrow pointing both up and down (log magnitude); horizontal axis $\omega$. A tick on the $\omega$ axis labeled $1/\sqrt{L_pC_d}$. Red $|f_1|$: flat at the 0 dB level (along the axis) from low frequency up to $1/\sqrt{L_pC_d}$, then falls at "−40dB/dec" (red slope triangle) above it. Blue $|f_2|$: rises at "20dB/dec" (blue slope triangle) from the lower left up to $1/\sqrt{L_pC_d}$, then falls at "−20dB/dec" (blue) above it. An orange brace over the low-frequency portion is labeled "Region" (orange). Light-blue note with an arrow to the corner: "at $\omega = 1/\sqrt{L_pC_d}$ there is an infinite Q resonant peak, but it doesn't show up on a bode plot", with a further light-blue note "↳ b/c no R".

$C_d$ works (ie, $v_o = V_i$) when $|f_1|\to 1$ (red), $|f_2|\to 0$ (blue)
⇒ Low frequencies (below $\sim\frac{1}{10}\frac{1}{\sqrt{L_pC_d}}$ or "Region" (orange))

**d)** $C_d\uparrow$, $\omega_0 = 1/\sqrt{L_dC_d}$ ↓ (as written, "$L_d$"; evidently $L_p$)
⇒ right bound of "Region" (orange) decreases

## Page 17

(Handwritten, continued.)

**e i)** $Z_{cap} = 1/j\omega C$

**ii)** **Figure:** Sketch of $|Z_{cap}|$ (red label) vs $\omega$ on log axes: a single straight red line falling from upper left to lower right with slope triangle labeled "−20dB/dec", crossing the $\omega$ axis.

**iii)** $Z = R_{ESR} + j\omega L_{ESL} + 1/j\omega C$

**iv)** **Figure:** Sketch of $|Z|$ (red) vs $\omega$: a red V shape — falling at "−20dB/dec" (slope triangle) from the upper left to a minimum point (red dot) on the $\omega$ axis, then rising at "20dB/dec" to the upper right. The minimum is annotated "↳ $= R_{ESR}$". An orange brace labeled "Region" spans the falling (capacitive) portion from low frequency up to a dashed orange vertical line just before the minimum.
↳ this is true for significant magnitude separation between $L_{ESL}$ & $C$ which is almost always true

**v)** Low frequencies in "Region" (orange) (below $\sim\frac{1}{10}\omega_0 = \frac{1}{10}\frac{1}{\sqrt{L_{ESL}C}}$)

**vi)** Large (both physically and in value) capacitors have high ESL + ESR
↳ Thus, these act as capacitors for smaller ranges of frequencies ("Region" (orange) shrinks)

(Rest of page blank.)

## Index terms

Problem Set 7 solutions, PS7, problem 9.2, problem 9.6, problem 9.18, problem 9.20, problem 9.31, problem 9.34, problem 7, resonant frequency, input impedance Z_i, R parallel j omega L, imaginary part zero, omega_0 = sqrt(R^2/(R^2 L C - L^2)), 2e4 rad/s, trivial resonance, KCL node V_1, voltage division, transfer function H = V_o/V_i, rationalize, complex conjugate, omega_0 = sqrt((L1+L2)/(L1 L2 C)), Bode plot, straight-line approximation, standard form, constant term in dB, -56.5 dB, -80 dB, -48 dB, 32 dB, -30.1 dB, 14 dB, simple zero, simple pole, zero at origin, 20 log omega, pole of order 2, quadratic pole, quadratic pole of order 2, -40 dB/decade, -80 dB/decade, corner frequency omega_c, 10 rad/s, 20 rad/s, 50 rad/s, 16 rad/s, 100 rad/s, 500 rad/s, 1000 rad/s, 0.1 rad/s, 1 rad/s, phase plot, 45 deg/decade, 90 deg/decade, 180 deg/decade, -180 degrees, -360 degrees, magnitude plot M[dB], phi(omega), damping ratio xi, xi = 7/4, xi = 0.5, K = R2 C2, omega_c = 1/sqrt(R1 R2 C1 C2), 0.5e6 rad/s, omega_c = 1/sqrt(LC), 1e4 rad/s, bandpass filter, highpass filter, low-frequency asymptote, high-frequency asymptote, +20 dB/decade, -20 dB/decade, +40 dB/decade, spectral plots, Figures P9.31(a) and (b), Figures P9.34(a) and (b), decoupling capacitor C_d, board parasitics, L_p, R_p neglected, load current i_L(t), f_1(omega) = 1/(1 - omega^2 L_p C_d), f_2(omega) = j omega L_p/(1 - omega^2 L_p C_d), f_1 = 1 without cap, f_2 = j omega L_p without cap, f_1 -> 1, f_2 -> 0, Region, 1/sqrt(L_p C_d), infinite Q resonant peak, no R, one-tenth rule, C_d increases lowers omega_0, Z_cap = 1/(j omega C), Z = R_ESR + j omega L_ESL + 1/(j omega C), ESR, ESL, V-shaped impedance, minimum = R_ESR, self-resonant frequency 1/sqrt(L_ESL C), large capacitors high ESL and ESR, Region shrinks
