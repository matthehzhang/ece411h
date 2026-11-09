---
course: ECE 411H
kind: refresher-notes
source: Recitations/Recitation4(10-4-26).pdf
source_pages: 4
author: Darsh Shah (TA)
unit: exam1
topics: [exam-1-review, first-order-circuit, rl-circuit, integrating-factor, time-domain, phasors, nodal-analysis, kcl, second-order-circuit, series-rlc, parallel-rlc, characteristic-roots, overdamped, underdamped, initial-conditions, step-response, phase-difference, voltage-divider]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
---

# Recitation 4 (10/5) — Exam 1 review (TA Darsh Shah)

**Summary**
Handwritten Xournal tablet notes (4 pages) from the TA-run Exam 1 review held the week before Semester Exam 1 (Wed Oct 7); the TA had asked students to bring questions. Four circuits are worked, each stated in two forms, "Time" ($v_{in}=5u(t)$, zero initial conditions) and "Phasors" ($v_{in}=5\cos\omega t$): (1) an RL network (10 Ω ∥ 0.01 µH feeding a 10 kΩ load, with a 50 µF capacitor hung across the source) solved in the time domain by writing a first-order ODE $\dot v_o + v_o/Q = v_{in}/Q$ and solving it with the integrating-factor method, then in the phasor domain by nodal analysis, ending with the question "what is $\angle\tilde V_o-\angle\tilde V_{in}$ at $\omega=100$ rad/s"; (2) a general L–(R_c+C)–R–R_o ladder solved by two phasor KCL equations and a resistive divider $V_o = R_o V_a/(R+R_o)$; (3) a series 10 µH–10 µF–10 kΩ circuit with $v_C(0)=0$, $i_L(0)=0$, giving the overdamped roots $r=-10,\ -10^9$ and constants $C_1=-5$, $C_2=5\times10^{-8}$ from the two initial conditions; (4) a parallel RLC ($R=10$ kΩ series, $C=1$ µF ∥ $L=10$ nH) with step input, giving $r=-50\pm j10^7$ and $v_o(t)=e^{-50t}(5\times10^{-6}\sin 10^7 t)$, using $\dot v_o(0)=v_{in}/RC$. The recurring method is: write KCL at the output node, substitute the element laws ($i_C=C\dot v$, $v_L=L\,\dot i$), reduce to one ODE in $v_o$, get the characteristic roots from the component values, then apply $v(0)$ and $\dot v(0)$ (from the capacitor current at $t=0$). The phasor versions reduce to one or two nodal equations and a complex ratio. Nothing here is beyond Exam 1 scope, but the same first/second-order machinery recurs on Exam 2 and the final.

Transcriber notes are in square brackets. Green ink = annotations added during the session; red ink = step-input sketch on page 4.

## Page 1

Header (centred, underlined): **ECE 411H – Recitation 4 (10/5)**

**Exam 1 Review** (underlined)

$v_o(0) = 0$

**Figure:** Circuit 1 (time-domain version). Independent voltage source $v_{in}$ (circle, + on top, − on bottom) on the far left; its − terminal is on the bottom rail, its + terminal goes up to the top rail (open-circle terminal at the top-left corner). From the top rail two vertical branches drop in parallel to a common node: a resistor labelled **10** (Ω) on the left, and an inductor **0.01 µH** on the right with the inductor current $i_L$ drawn as an upward arrow (from the common node up toward the top rail). The common node is brought out to the right as the output terminal $v_o$ (open circle). From that common node a **10k** (10 kΩ) resistor goes down to the bottom rail, which carries the ground symbol directly under it. Further right, the top rail continues to a node marked with a green dot, from which a **green-ink resistor (no value)** in series with a **50 µF** capacitor goes down to the bottom rail. [The green resistor was added after the first drawing; the equations that follow ignore the capacitor branch entirely, since it sits directly across $v_{in}$ and does not affect $v_o$.] A curved arrow (clockwise "J" shape) is drawn inside the left mesh between the source and the 10/10k branch.

Right of the figure:
- Char: $v_{in}(t) = 5u(t)$ [heading reads "Char:" — the characteristic / time-domain case]
- Phasors: $v_{in}(t) = 5\cos(\omega t)$

**Time Domain:** (underlined)

Green, right: $v_L = L\dfrac{\partial i}{\partial t} \Rightarrow i = \dfrac{1}{L}\int v_L\,dt$, with a green arrow from $v_L$ to the annotation "$v_o - v_{in}$" (i.e., $v_L = v_o - v_{in}$).

Far-right margin (black): $v_o + L\dfrac{\partial i_L}{\partial t} + v_{in} = 0$ [as written; a KVL around the inductor branch, sign convention as the TA wrote it].

KCL at the $v_o$ node (bracketed):
$$\left[\frac{v_o}{10k} + \frac{v_o - v_{in}}{10} + i_L = 0\right]$$

Inductor element law (bracketed):
$$v_L = \left[v_o - v_{in} = L\frac{\partial i_L}{\partial t} = L\,\dot i_L\right]$$

A curved arrow from the KCL bracket down to:
$$\Rightarrow\quad i_L = -\frac{v_o}{10k} - \frac{v_o - v_{in}}{10}$$
and a long curved arrow from this $i_L$ expression back up into the $L\,\dot i_L$ of the element law (substitution).

$$v_o - v_{in} = L\,\overline{\left(-\frac{v_o}{10k} - \frac{v_o - v_{in}}{10}\right)}^{\,\bullet}$$
[an overbar with a dot over the whole parenthesis: time derivative of the bracket]

Green "1)":
$$v_o - v_{in} = L\left(-\frac{\dot v_o}{10k} - \frac{\dot v_o - \dot v_{in}}{10}\right)$$

Green "2)":
$$\dot v_o\underbrace{\left[\frac{L}{10k} + \frac{L}{10}\right]}_{Q} + v_o = v_{in} \quad\Rightarrow\quad \dot v_o + \frac{1}{Q}v_o = \underbrace{\frac{1}{Q}v_{in}}_{\text{green: } C}$$
[Underbrace labelled $Q$ under the bracket; green underbrace under $\frac{1}{Q}v_{in}$ labelled "C", with a green arrow from this "C" down to the $C$ in the generic ODE below.] [As written. Step 2 drops the $\dot v_{in}/10$ term of step 1 and absorbs the sign — for $v_{in}=5u(t)$, $\dot v_{in}=0$ for $t>0$.]

**Integration Factor** (text, left margin)

$$\dot y + ay = \underline{C}$$
$$e^{\int a\,dt}\left[\dot y + ay\right] = C e^{\int a\,dt}$$
$$\left[y\,e^{\int a\,dt}\right]^{\bullet} = C e^{\int a\,dt}$$
$$y = \frac{1}{e^{\int a\,dt}}\int C e^{\int a\,dt}\,dt$$

$$\Rightarrow v_o(t) = \frac{1}{e^{t/Q}}\int C e^{t/Q}\,dt$$
$$= \frac{1}{e^{t/Q}}\int \frac{v_{in}}{Q} e^{t/Q}\,dt$$
$$= \frac{1}{e^{t/Q}}\left[\frac{v_{in}}{\cancel{Q}}\left[\cancel{Q}\,e^{t/Q}\right] + C\right]$$
[both $Q$'s struck through in green — they cancel; green annotation "integration const." with an arrow pointing at the $+C$]
$$= v_{in} + C e^{-t/Q}$$

$$v_o(0) = 0 = v_{in} + C e^{-t/Q}$$
$$\Rightarrow C = -v_i$$
[written "$-v_i$"; i.e., $C = -v_{in}$, so $v_o(t) = v_{in}(1 - e^{-t/Q})$ — the last line is not written.]

## Page 2

**Phasors** (underlined)

**Figure:** Circuit 1 redrawn for the phasor case, without the green resistor: source $v_{in}$ (circle, + top) on the left between top and bottom rails; from the top rail the **10** Ω resistor and the **0.01 µH** inductor (with $i_L$ upward arrow) drop in parallel to the common node, which is the $v_o$ terminal (open circle to the right); **10k** from that node to the bottom rail; ground symbol on the bottom rail below the 10k; and the **50 µF** capacitor directly between the top rail and the bottom rail at the far right. Same clockwise curved arrow in the left mesh.

Right of figure:
Phasors: $v_{in}(t) = 5\cos(\omega t)$
$$\tilde V_{in} = 5e^{j\phi} = 5$$

KCL at the output node (phasor):
$$\frac{\tilde V_o - 5}{j\omega L} + \frac{\tilde V_o - 5}{10} + \frac{\tilde V_o}{10k} = 0$$

$$\Rightarrow \tilde V_o\left[\frac{1}{j\omega L} + \frac{1}{10} + \frac{1}{10k}\right] = 5\left[\frac{1}{10} + \frac{1}{j\omega L}\right]$$

$$\Rightarrow \tilde V_o = 5\,\frac{\left[\frac{1}{10} + \frac{1}{j\omega L}\right]}{\left[\frac{1}{j\omega L} + \frac{1}{10} + \frac{1}{10k}\right]} = 5\,\frac{(1000)\,j\omega L + 10k}{10k + (1k)\,j\omega L + j\omega L}$$
[Green annotation "$j\omega L(10k)$" written beside both the numerator and the denominator: multiply top and bottom by $j\omega L\cdot 10\text{k}$.]

$\omega = 100$ rad/sec

$$\angle\tilde V_o - \angle\tilde V_{in}\ ?$$
[The question is posed (phase of the output relative to the input at $\omega=100$ rad/s) but not evaluated on the page. Rest of page blank.]

## Page 3

**Figure:** Circuit 2 (general ladder, phasor domain). Input terminal $v_{in}$ (open circle, far left) → series inductor **L** → node **a** (labelled above the node with a tilde, written as $\tilde V_o$ but referred to as $V_a$ in every equation below; a green bracket "[" marks this node). From node a: a shunt branch down to ground consisting of resistor **$R_c$** in series with capacitor **C** (ground symbol at the bottom). From node a the top wire continues → series resistor **R** → output node $v_o$ (open-circle terminal on the right). From the output node a shunt resistor **$R_o$** goes down to ground (ground symbol; green bracket under $R_o$).

$$v_{in} = 5\cos(\omega t) = \tilde V_{in} = 5$$

KCL at node a:
$$\frac{V_a - V_{in}}{j\omega L} + \frac{V_a - V_o}{R} + \frac{V_a}{R_c + 1/j\omega L} = 0 \;\Rightarrow\; V_a\left[\frac{1}{j\omega L} + \frac{1}{R} + \frac{1}{R_c + 1/j\omega L}\right] = \frac{V_{in}}{j\omega L} + \frac{V_o}{R}$$
[The third-branch impedance is written "$R_c + 1/j\omega L$" in both places (sic); the branch is $R_c$ in series with $C$, so $R_c + 1/j\omega C$ is meant. The right-hand equation is underlined in green.]

KCL at the output node:
$$\frac{V_a - V_o}{R} = \frac{V_o}{R_o} \;\Rightarrow\; V_o\left(\frac{1}{R} + \frac{1}{R_o}\right) = \frac{V_a}{R_o} \;\Rightarrow\; V_o = \frac{R_o}{R + R_o}\,V_a.$$
[Middle step written "$V_a/R_o$" (sic); it should be $V_a/R$, and the final divider result $V_o = R_o V_a/(R+R_o)$ is the correct one. Final result underlined in green.]

**Figure:** Circuit 3. Input $v_{in}$ (open circle) → series inductor **10 µH** → series capacitor **10 µF** → output node $v_o$ (open circle to the right); from the output node a **10k** resistor down to ground.

**Figure:** (right of circuit 3) $t = 0$ sketch of the same circuit: "5V" at the left end of a wire; the wire carries a dot, then an arrowhead (current direction, left to right), then a dot, and ends in an open circle; a gap; another open circle begins the wire to the output node $v_o$ (open circle), with a resistor from that node down to ground. Annotations: "$v_c(0) = 0$V" above the gap and "$i_L(0) = 0$A" below the arrowed wire.

Time: $v_{in} = 5u(t)$
Phasors: $v_{in} = 5\cos(\omega t)$; $\omega = 200$ rad/sec.

$$\frac{\partial^2 i_L}{\partial t^2} + \frac{R}{L}\frac{\partial i_L}{\partial t} + \frac{1}{LC}i_L = 0$$

$$LC\,\ddot v_c + RC\,\dot v_c + v_c = v_{in}$$
$$\hookrightarrow r = -10,\ -1\times10^9$$

$$v_c(t) = C_1 e^{-10t} + C_2 e^{-10^9 t}\ \left[+\ \varphi\right]$$
Arrows beneath: $C_1 \Rightarrow -5$, $\;C_2 \Rightarrow 5\times10^{-8}$.

Bracketed pair (initial conditions):
$$v_c(0) = 0 = C_1 + C_2 + \varphi$$
$$i_L(0) = i_c(0) = C\frac{\partial v_c}{\partial t} = C\left[-10C_1 - 10^9 C_2\right] = 0$$
[$\varphi$ is the particular/steady-state term, $=5$ for the step input; rest of page blank.]

## Page 4

Top line:
$$i_c(0) = C\frac{\partial v_c}{\partial t} = C\dot v_o = \frac{v_{in}}{R} \;\Rightarrow\; \dot v_o = \frac{v_{in}}{RC}$$
$v_o(0) = 0$

**Figure:** Circuit 4. Independent voltage source $v_{in}$ (circle, + on top) on the left between the top and bottom rails; from its + terminal a series resistor **R** along the top wire to a node; from that node, in parallel to the bottom rail: capacitor **C** and inductor **L** (two vertical branches); the same node is brought out to the right as the output terminal $v_o$ (open circle). Below the source: $v_{in} = 5u(t)$.

**Figure:** (red ink, right) step plot: horizontal axis $t$, vertical axis at $t=0$; the curve is 0 for $t<0$ and jumps to level "5" (dashed tick on the vertical axis) for $t>0$. Label:
$$5u(t) = \begin{cases} 5, & t>0\\ 0, & t<0\end{cases}$$

KCL at the output node:
$$\frac{v_{in} - v_o}{R} = i_c + i_L \;\Rightarrow\; \frac{v_{in} - v_o}{R} = C\frac{\partial v_o}{\partial t} + i_L \;\Rightarrow\; i_L = \underbrace{\frac{v_{in} - v_o}{R} - C\frac{\partial v_o}{\partial t}}$$

$$i_c = C\frac{\partial v_c}{\partial t} = C\frac{\partial v_o}{\partial t}$$
$$v_L = v_o = L\frac{\partial i_L}{\partial t}$$
(a long curved arrow carries the underbraced $i_L$ expression into the next line)
$$\Rightarrow v_o = L\frac{\partial i}{\partial t} = L\frac{-\dot v_o}{R} - LC\,\ddot v_o$$
$$\Rightarrow \ddot v_o + \frac{1}{RC}\dot v_o + \frac{1}{LC}v_o = 0$$

$$\Rightarrow R = 10k,\quad C = 1\,\mu F,\quad L = 10\,nH$$
$$\Rightarrow r = -50 \pm j\,(10^7)$$
Green, right margin: $\left.\dfrac{\partial}{\partial t}\right|_{t=0}$

Arrows from "$-50$" to the exponent and from "$10^7$" to $\omega$ in:
$$\Rightarrow v_o(t) = e^{-50t}\left(C_1\cos(\omega t) + C_2\sin(\omega t)\right)$$
$$v_o(0) = C_1\cos(\omega t) = 0$$
$$\dot v_o(0) = -50(1)\left[\cancel{C_1\cos(\omega t)} + \cancel{C_2\sin(\omega t)}\right] + (1)\left[\cancel{0} + C_2\,\omega\cos(\omega t)\right]$$
[green: "0" written over $C_1\cos(\omega t)$ and over $C_2\sin(\omega t)$, both struck through; the first term in the second bracket is written as a struck-through 0]
$$= C_2\,\omega\,\cancel{\cos(\omega t)}\quad[\text{green: } 1 \text{ written over the struck-through cosine}]$$
$$= \frac{5}{10k\,(10^{-5})} = 50$$
[as written: $10k\times10^{-5}$; with $C = 1\,\mu F = 10^{-6}$ this would be $5/(10^4\cdot10^{-6}) = 500$ — the TA's arithmetic uses $10^{-5}$]
$$\Rightarrow C_2 = \frac{50}{\omega} = 5\times10^{-6}$$

$$v_o(t) = e^{-50t}\left(5\times10^{-6}\sin(10^7 t)\right)$$

[Rest of page blank.]

## Index terms

Recitation 4, Exam 1 review, Darsh Shah, first-order RL circuit, 10 ohm, 0.01 µH, 10 kΩ, 50 µF, v_o(0)=0, 5u(t), 5cos(ωt), time domain, KCL at output node, inductor element law v_L = L di/dt, i = (1/L)∫v_L dt, integrating factor, ẏ + ay = C, e^{∫a dt}, Q = L/10k + L/10, v̇_o + v_o/Q = v_in/Q, integration constant, v_in + C e^{-t/Q}, phasors, Ṽ_in = 5e^{jφ} = 5, nodal analysis, 1/jωL, Ṽ_o = 5(1000 jωL + 10k)/(10k + 1k jωL + jωL), ω = 100 rad/s, phase difference ∠Ṽ_o − ∠Ṽ_in, L–R_c–C–R–R_o ladder, node a, V_a, R_c + 1/jωC, voltage divider V_o = R_o V_a/(R+R_o), series RLC, 10 µH, 10 µF, 10k, v_C(0)=0, i_L(0)=0, ω = 200 rad/s, d²i_L/dt² + (R/L) di_L/dt + i_L/LC = 0, LC v̈_c + RC v̇_c + v_c = v_in, characteristic roots r = −10, −10^9, overdamped, C_1 = −5, C_2 = 5×10^{-8}, particular solution φ, parallel RLC, R = 10k, C = 1 µF, L = 10 nH, v̈_o + v̇_o/RC + v_o/LC = 0, r = −50 ± j10^7, underdamped, e^{-50t}(C_1 cos ωt + C_2 sin ωt), v̇_o(0) = v_in/RC, i_c(0) = C dv/dt, C_2 = 50/ω = 5×10^{-6}, v_o(t) = e^{-50t} 5×10^{-6} sin(10^7 t), step input, initial conditions, derivative at t=0
