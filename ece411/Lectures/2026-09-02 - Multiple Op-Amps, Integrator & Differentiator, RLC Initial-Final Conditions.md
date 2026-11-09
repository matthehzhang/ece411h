---
course: ECE 411H
date: 2026-09-02
instructor: Prof. Ed Yu
topic: Rules and strategy for circuits with multiple ideal op-amps; op-amp integrator and differentiator; introduction to RLC (second-order) circuits; general solution recipe; worked example of initial and final conditions
reading: Ulaby/Maharbiz/Furse 3e §4-9 (instrumentation amp), Prob. 5.71 (recorded solution), §5-6 (op-amp circuits with capacitors), Ch. 6 (RLC circuits)
source: Recordings/2026-09-02 (transcript + 64 listed tablet frames, plus 10 neighbouring frames)
tags: [ece411, lecture, op-amp, multiple-op-amps, integrator, differentiator, rlc, second-order, initial-conditions, exam1]
---

# 2026-09-02: Multiple Op-Amps, Integrator and Differentiator, RLC Initial and Final Conditions

## Summary

- **Three rules for circuits with several ideal op-amps:** (1) every op-amp individually obeys $i_p=i_n=0$ and $v_p=v_n$. (2) Check that each op-amp stays in its linear region, or else account for saturation. Cascaded gains multiply, so saturation becomes more likely. (3) KCL and KVL hold everywhere, **but the current at each op-amp output is unknown until everything else has been solved**, so KCL at an op-amp output node gets you nowhere mid-analysis.
- **Strategy:** start at the op-amps closest to the known inputs and find their outputs. Each solved output then acts as a known voltage source for the next stage. Work along the signal path and check for saturation as you go.
- **Op-amp integrator.** This is the inverting amplifier with $R$ at the input and $C$ in the feedback path: $\dfrac{dv_o}{dt}=-\dfrac{1}{RC}v_s$, so $v_o(t_2)-v_o(t_1)=-\dfrac{1}{RC}\displaystyle\int_{t_1}^{t_2}v_s\,dt$.
- **Op-amp differentiator.** Swap $R$ and $C$, putting $C$ at the input and $R$ in the feedback path: $v_o=-RC\,\dfrac{dv_s}{dt}$. Its output is zero for a constant input and nonzero only when the input changes.
- **Second-order circuits** contain two inductors and/or capacitors that **cannot be combined into one equivalent element**, and they give a 2nd-order ODE. Two capacitors in parallel do **not** make a circuit second order.
- **General recipe for a 2nd-order circuit with a sudden change at $t=0$:** (0) find the initial ($t\le0$) and/or final ($t\to\infty$) conditions. (1) Derive the 2nd-order ODE for the desired $v$ or $i$. (2) Solve it; the solution has **two unknown coefficients**. (3) Fix them with the initial and/or final conditions.
- **Worked example** (24 V, 2 Ω, 4 Ω, 0.2 H, 6 Ω, 8 mF, step source $4u(t)$ A): $v_C(0)=12$ V, $i_L(0)=2$ A (by continuity), $i_C(0)=4$ A, $v_L(0)=-8$ V, $i_L(\infty)=-2/3$ A, $v_C(\infty)=20$ V. All values were verified with python and ngspice.
- **Key points:** in steady state C is an open circuit and L is a short circuit. At transition points $i_L$ and $v_C$ are continuous. Use ordinary circuit analysis to build on the continuity values and get every other $v$ and $i$ at $t=0^+$.

---

## Content

### 0. Announcements [0:00:02–0:01:06] (f_0005, f_0008)
- **PS1** due Wed Sep 9 ("a week from today"). **PS2** due on Canvas **9:00 AM Mon Sep 14**.
- **PS3** is released Wed Sep 9 and due on Canvas **9:00 AM Mon Sep 21**. "Problem Set 3 is on RLC circuit analysis and many students find it to be time-consuming, so please start work on it well in advance of the due date!" (board). Spoken: "somewhat time consuming. So you should not leave it for the last minute." [0:00:31]
- **No class or regular office hours Wed Sep 16.** A recorded lecture is posted on Canvas instead; watch it before Mon Sep 21.
- At the end [1:18:44]: Monday is Labor Day, so the next class is Wed Sep 9, which picks up the time-domain analysis.

### 1. Circuits with multiple op-amps: basic rules [0:01:20–0:07:11] (f_0021, f_0024, f_0026, f_0027)
Context: Darsh (TA) went through the instrumentation amplifier in recitation. So far the class has only seen single-op-amp circuits, and "the extension to multiple op amps is actually relatively straightforward." [0:01:40]

**Board: "Basic rules for circuits with multiple op amps"** (ideal op-amps):
1. **For each ideal op-amp, require $i_p=i_n=0$ and $v_p=v_n$ as usual.** [0:02:20–0:03:15]
2. **Make sure each op-amp remains in its linear region, or if it doesn't, account for op-amp saturation behavior.** [0:03:15–0:05:08]
   - Why it matters: in a cascade where each stage amplifies, "you can get a gain that is kind of the product of the individual gain factors... so it's easier or more likely... that that will try to push the output of the op amp beyond its supply voltages." [0:04:10–0:05:00]
3. **KCL and KVL apply everywhere in the circuit, BUT the current at each op-amp output is typically not known until everything else has been solved.** [0:05:08–0:06:50]
   - "if you have a node that is connected to the output of one of the op amps, then it's usually not that useful to apply KCL at that node because the output current at the op amp usually will not be known." [0:05:37]
   - "You can apply KCL at the end to figure out what that current has to be." [0:05:57]

### 2. General approach for multiple op-amps [0:07:14–0:11:23] (f_0028, f_0031, f_0036, f_0039)
**Board: "General approach for analyzing circuits with multiple op amps":**
1. **Determine output voltages of individual op amps, starting with those closest to input signals.**
2. **Use output voltages of these op amps as input voltages for subsequent op amps in signal path.**
3. **During analysis, account for op amp saturation behavior.**

Spoken version: "you start near the known input voltages... because you want to start where kind of you know what is going on... Once you get the outputs of those op amps, right, those will basically act as voltage sources, and so you will know them." Then "you just sort of work your way through the circuit until you get to the final output." [0:07:42–0:08:19]

Student Q (saturation, [0:08:53]): if an op-amp saturates, $v_p\neq v_n$ in general, "because that's the nature of the transfer characteristic." You have to model that case explicitly.

**References (board f_0045)** [0:11:23–0:13:08]: "See recitation discussion or recording of instrumentation amplifier example (Ulaby Sec. 4-9) + solution to Ulaby 5.71 for examples." The 5.71 solution is in the Canvas section of recorded Ulaby solutions. The instrumentation-amp recording link goes in the lecture-topics discussion board entry for today.

> [!note] No numeric multi-op-amp example was worked in this lecture. The strategy above is the whole content. For a worked case see Ulaby §4-9 and 5.71.

### 3. Op-amp circuits with capacitors: motivation [0:13:08–0:15:29] (f_0050)
**Board heading:** "Op amp circuits with capacitors". **Reading:** Ulaby et al., Sec. 5-6.

The argument: a capacitor has $i=C\,dv/dt$, while a resistor is "just an algebraic, a direct proportionality relationship." A capacitor therefore lets the KCL currents be proportional to derivatives of voltages. Applying the same KCL analysis as for the inverting, summing and difference amplifiers then gives "not only algebraic relationships between input and output voltages, but... differential relationships or integrative relationships." [0:13:38–0:14:50] There are two canonical examples.

### 4. Example: op-amp integrator [0:15:29–0:27:02] (f_0052, f_0054, f_0063, f_0075, f_0090, f_0096, f_0107)

**Circuit (f_0052):** the op-amp has $v_p$ (non-inverting, +) **tied to ground**. Source $v_s$ (+ on top, − to ground) connects through **$R$** to the inverting node $v_n$. **$C$** sits in the feedback path from $v_n$ to the output $v_o$. It is the inverting amplifier with $R_f$ replaced by $C$.

**Where does C go? (Socratic)** [0:16:49–0:18:21] To get $v_o\propto\int v_s$, put $C$ between $v_o$ and $v_n$. The feedback current is then $\propto dv_o/dt$, and KCL at $v_n$ gives $dv_o/dt\propto v_s$. Integrating that gives $v_o\propto\int v_s$. (A student proposed this placement and he confirmed it.)

**Derivation.** KCL at $v_n$, summing currents **leaving** the node [0:18:49–0:19:32]:

$$\text{KCL}@v_n:\quad \frac{v_n-v_s}{R}+C\frac{d}{dt}(v_n-v_o)=0;\qquad v_p=v_n=0$$

Set $v_n=0$ and multiply by $-1$ [0:19:32–0:20:21]:

$$\frac{v_s}{R}+C\frac{dv_o}{dt}=0\quad\Longrightarrow\quad \frac{dv_o}{dt}=-\frac{1}{RC}\,v_s$$

Integrate both sides from $t_1$ to $t_2$ [0:20:21–0:21:40]:

$$\int_{t_1}^{t_2}\frac{dv_o}{dt}\,dt=-\frac{1}{RC}\int_{t_1}^{t_2}v_s(t)\,dt$$

The integral of a perfect differential is the function evaluated at the limits ("differentiation and integration are inverse operations"):

$$\boxed{v_o(t_2)-v_o(t_1)=-\frac{1}{RC}\int_{t_1}^{t_2}v_s(t)\,dt}$$

**Board: "Circuit acts as an integrator for $v_s(t)$."** "The voltage difference between two different times is proportional to the integral of the input signal." [0:22:09]

**Sign.** The minus sign comes from starting with the inverting configuration. A non-inverting version could drop the sign, "but it would have been a little bit more complicated because you have two resistors, you have to have the voltage divider." [0:22:29–0:23:11]

> [!tip] My addition, not said in lecture: the integrator meets rule 2. With any DC component in $v_s$, $v_o$ ramps at slope $-V_{dc}/RC$ until it hits $\pm V_{cc}$. That is exactly the "check every op-amp output stays inside the rails" step that P3 asks for.

### 5. Example: op-amp differentiator [0:27:06–0:30:50] (f_0114, f_0118, f_0119, f_0121, f_0129, f_0131)

**Circuit (f_0121):** swap the positions of $R$ and $C$. $v_p$ is grounded. $v_s$ (+ top) goes through **$C$** to $v_n$, and **$R$** is the feedback element from $v_n$ to $v_o$. "the obvious way to do the differentiator circuit is to swap the positions of the resistor and the capacitor." [0:27:35]

**Derivation.** KCL at $v_n$, outgoing currents (the capacitor current flows left, the resistor current flows up and right) [0:28:31–0:29:12]:

$$\text{KCL}@v_n:\quad C\frac{d}{dt}(v_n-v_s)+\frac{v_n-v_o}{R}=0;\qquad v_n=v_p=0$$

Set $v_n=0$ and multiply by $-1$ [0:29:23–0:29:54]:

$$C\frac{dv_s}{dt}+\frac{v_o}{R}=0\quad\Longrightarrow\quad\boxed{v_o=-RC\,\frac{dv_s}{dt}}$$

**Board: "Circuit acts as a differentiator for $v_s(t)$."** Use: "if you want a signal that becomes non-zero anytime there's a change in something. Because if you have a constant input, then the output voltage would be zero. Every time it changes, then you'll get a non-zero output." [0:30:14–0:30:36]

> [!tip] My addition, not in lecture. In phasor form both circuits are inverting amplifiers with $\tilde V_o/\tilde V_s=-\tilde Z_f/\tilde Z_{in}$. The integrator gives $-\dfrac{1/(j\omega C)}{R}=-\dfrac{1}{j\omega RC}$ and the differentiator gives $-\dfrac{R}{1/(j\omega C)}=-j\omega RC$. This is the same "replace $R$ with $\tilde Z$" move used in P2 and P3.

He closes [0:30:50]: "that is everything that we want to say for now on first order circuits, including... first order op amp circuits."

### 6. RLC circuits: what "second order" means [0:30:55–0:41:11] (f_0133, f_0135, f_0144, f_0149, f_0150, f_0152, f_0153)

**Board heading:** "RLC Circuits". **Reading:** Ulaby et al., Chapter 6. He believes 302/302H covered this "very little, if at all" (the class agreed). [0:31:35]

**Board text (f_0135, f_0144, f_0149):**
- "Circuits with a single capacitor or inductor, plus resistors + sources, i.e., RC and RL circuits, yield **first-order differential equations** for $i$ and $v$." The solution of a first-order ODE "is always some form of exponential." [0:32:19]
- "Circuits with **two** inductors and/or capacitors that **cannot be combined into a single component**, e.g., RLC circuit, can yield **second-order differential equations** (highest-order derivative is $\dfrac{d^2}{dt^2}$). Circuits governed by 2nd-order differential equations are called **second-order circuits**."
- Why second order: "you're going to have two terms with derivatives, and in order to get down to one variable, you end up having a second order differential equation." [0:33:57]
- These "can have more complicated behavior, significantly more complicated than first order circuits", so "we want to spend actually a fair amount of time" on them. [0:36:23]

**Counter-example (blue, f_0149/f_0152)** [0:37:58–0:39:07]: a voltage source, a series R, and **two capacitors in parallel**. These combine to a single $C_{eq}$, which gives the circuit source–R–$C_{eq}$. "Even though it has two capacitors, [it] is not a second order circuit because it would still give you just a first order differential equation."

**Second sketch (blue, f_0153)** [0:40:41]: a source, a **series C**, then a series R, then a **shunt C** in parallel with a shunt R. A student asked whether these two capacitors combine. Answer: "Yeah," they cannot be combined, so the circuit is second order.

### 7. Generic problem and general approach [0:41:15–0:47:11] (f_0159, f_0160, f_0164, f_0169, f_0171, f_0289, f_0290)

**Board:** "Consider a second-order circuit with a sudden change, e.g., switch thrown or source changed, at $t=0$. General approach:"

0. **Determine initial ($t\le0$) and/or final ($t\to\infty$) circuit conditions, in a manner similar to first-order circuits.** In steady state the inductor is a short and the capacitor is open, "and so you end up just with the resistors and the sources." [0:42:59–0:44:08]
1. **Derive a second-order differential equation for the desired voltage or current** using KCL, KVL and node analysis. [0:44:23–0:45:16]
2. **Solve the differential equation. In general the solution will have two unknown coefficients.** "with the second order differential equation, you're going to have to integrate in some sense twice and you'll get two constants of integration." [0:45:24–0:45:56]
3. **Apply initial and/or final conditions to determine values of unknown coefficients.** The conditions can be "a current or a voltage at $t$ equal to zero and $t$ equal to infinity or a current and voltage or voltage and its derivative at $t$ equal to zero." [0:46:20–0:46:46]

If several changes happen, each one is at "some well specified times." [0:42:27]

### 8. Worked example: determining initial and final conditions [0:47:11–1:14:08] (f_0175, f_0181, f_0200–f_0203, f_0220, f_0224, f_0228, f_0253, f_0261, f_0282–f_0286, f_0295, f_0297, f_0300, f_0304, f_0314, f_0317, f_0327, f_0360, f_0365, f_0374, f_0385, f_0386, f_0389, f_0407, f_0413)

**Circuit (f_0181, corrected f_0261/f_0314).** The node labels are mine: A is the top-left junction, B is the right junction, and the bottom wire is ground.
- **Left branch (A to ground):** a **2 Ω** resistor down from A to the **+** terminal of a **24 V** source. The source's − terminal goes to the bottom wire.
- **Middle series branch (A to B):** **4 Ω** then **0.2 H**. $v_L$ is referenced **+ on the left (4 Ω side)** and **− on the right (B side)**. $i_L$ points **right**, from A toward B.
- **Top branch (A to B):** an independent **current source $(4\text{ A})\,u(t)$** with its arrow pointing **right**, pushing 4 A from A to B.
- **From B to ground:** **6 Ω** in parallel with **C = 8 mF**. $v_C$ is + at the top (B) and − at the bottom. $i_C$ points **right** into the capacitor's top plate (passive convention), so $v_C$ is also the 6 Ω voltage.
- **Unit step (board):** $u(t)=\begin{cases}0 & t<0\\ 1 & t\ge0\end{cases}$. "It's sort of equivalent to having a switch... in series with that... current source that... closes at $t$ equal to zero." [0:50:06–0:50:39]

**Find:** (a) $v_C(0)$, $i_L(0)$; (b) $i_C(0)$, $v_L(0)$; (c) $v_C(\infty)$, $i_L(\infty)$.

> [!warning] Board error, self-corrected. The capacitor was first written as **8 µF** (f_0181). At [0:58:18] he said "Actually, this is millifarads here, not microfarads," and he relabelled it **8 mF**. The redrawn $t=0$ circuit (f_0261, f_0314) shows 8 mF. **None of the answers to (a)–(c) depends on the values of $L$ or $C$.** They matter only for the transient (§9). The C value does change the *character* of the transient: 8 mF gives an underdamped response and 8 µF gives an overdamped one (see §9).

**Step 1: draw the circuit for $t=0^-$, i.e. $t<0$ (f_0220)** [0:51:33–0:55:49]. The current source has been off "for essentially infinite time", so the circuit is in steady state. The current source is drawn as an **open** (two open terminals), L is drawn as a **short** (two dots joined by a wire), and C as an **open** (terminals o + $v_C$ − o).

What is left is a single series loop: 24 V, 2 Ω, 4 Ω, short, 6 Ω.

$$i_C(t=0^-)=0\ \text{(open terminal)},\qquad v_L(t=0^-)=0\ \text{(short)}$$
$$i_L(t=0^-)=\frac{24\text{ V}}{2\,\Omega+4\,\Omega+6\,\Omega}=2\text{ A},\qquad v_C(t=0^-)=(6\,\Omega)(2\text{ A})=12\text{ V}$$

($v_C$ equals the 6 Ω voltage because the two are in parallel, and the 2 A loop current flows through the 6 Ω.)

**Why solve $v_C$ and $i_L$ first?** (student Q [0:56:05]) "when we go from $t$ equal to zero minus to $t$ equal to zero... that... 4 amp current source is suddenly turning on. But we know that the voltage across the capacitor and the current through an inductor always have to be continuous." [0:56:19–0:56:58]

**Step 2: draw the circuit for $t=0$ (f_0261, f_0282, f_0314)** [0:57:06–0:59:07]. The full circuit is drawn with the 4 A source **present** and L and C behaving as real elements, "rather than having the more simple steady state behavior."

**(a) By continuity** (boxed on the board, f_0314) [0:59:07–1:00:20]:

$$\boxed{v_C(0)=12\text{ V by continuity},\qquad i_L(0)=2\text{ A by continuity}}$$

**(b) $i_C(0)$ by KCL at node B** (f_0317, f_0327) [1:00:30–1:04:45]. Node B is "the node that is just to the right of the inductor... that has the four branches coming out of it." The only unknown current there is $i_C$. Known currents: from the left, $i_L(0)=2$ A in. From the top, 4 A in. Down through 6 Ω, $v_C(0)/6=12/6=2$ A. Sum of outgoing currents $=0$:

$$-4\text{ A}-i_L(0)+i_C(0)+\frac{v_C(0)}{6\,\Omega}=0\;\Longrightarrow\;-4-2+i_C(0)+\frac{12\text{ V}}{6\,\Omega}=0$$
$$\boxed{i_C(0)=4\text{ A}}$$

($12/6=2$ cancels the $-2$, which leaves $i_C(0)=4$.) Note $i_C$ **jumped** from $0$ at $0^-$ to $4$ A at $0$. Only $v_C$ and $i_L$ must be continuous.

**(b) $v_L(0)$ by KVL** (f_0374, f_0385) [1:04:53–1:08:52]. "Since we now know all the currents," take KVL around the outer loop through the 24 V source, 2 Ω, 4 Ω, L, and the 6 Ω‖C (voltage $v_C$). KCL at A shows the 2 Ω carries $i_L(0)+4$ A. Going clockwise:

$$-24\text{ V}+(2\,\Omega)\big(i_L(0)+4\text{ A}\big)+(4\,\Omega)\,i_L(0)+v_L(0)+v_C(0)=0$$
$$-24+2(2+4)+4(2)+v_L(0)+12=0$$
$$\boxed{v_L(0)=-8\text{ V}}$$

The $-24$ cancels the $12+12$, which leaves $8+v_L(0)=0$.

**(c) Final conditions: draw the circuit for $t\to\infty$ (f_0389)** [1:09:08–1:10:31]. The circuit is back in steady state: L is a short and C is open, but **the 4 A source is now active**. That leaves three resistors and two sources.

**$i_L(\infty)$ by KVL** around the loop 24 V, 2 Ω, 4 Ω, 6 Ω (f_0407) [1:10:57–1:13:10]. KCL at A puts $4+i_L$ through the 2 Ω. With C open, KCL at B puts $4+i_L$ through the 6 Ω.

$$-24\text{ V}+(2\,\Omega)(4\text{ A}+i_L)+(4\,\Omega)\,i_L+(6\,\Omega)(4\text{ A}+i_L)=0$$
$$-24+8+2i_L+4i_L+24+6i_L=0\;\Longrightarrow\;12\,i_L=-8\;\Longrightarrow\;\boxed{i_L(\infty)=-\tfrac{2}{3}\text{ A}\approx-0.667\text{ A}}$$

**$v_C(\infty)$** (f_0413) [1:13:10–1:14:00]:

$$v_C=(6\,\Omega)(4\text{ A}+i_L)=(6\,\Omega)\left(\tfrac{10}{3}\text{ A}\right)=\boxed{20\text{ V}=v_C(\infty)}$$

> [!check] Verification (python with exact fractions, plus an ngspice transient using a step current source):
> $i_L(0^-)=2$, $v_C(0^-)=12$, $i_C(0)=4$, $v_L(0)=-8$, $i_L(\infty)=-2/3$, $v_C(\infty)=20$. Simulation: $v_C(1\,\mu s)=12.0$ V, $i_L(1\,\mu s)=2.00$ A, $v_L(2\,\mu s)=-8.00$ V, $v_C(0.4\,s)=20.0$ V, $i_L(0.4\,s)=-0.667$ A. **All board numbers are correct.**
>
> Superposition sanity check for $t\to\infty$ (mine). The 24 V source alone gives $v_C=24\cdot\frac{6}{12}=12$ V. The 4 A source alone (24 V shorted) splits between the 4 Ω path (B→A directly) and the 8 Ω path (6 Ω + 2 Ω via ground). The 6 Ω gets $4\cdot\frac{4}{12}=\frac43$ A, so it adds $8$ V, and $12+8=20$ V ✓. $i_L$ gets $-4\cdot\frac{8}{12}=-\frac83$ A, so $i_L=2-\frac83=-\frac23$ A ✓.

> [!note] Spoken slips in the transcript, all harmless because the board is correct. At [0:49:26] he said "a voltage source, or sorry, a current source." At [0:50:59] he described part (b) as "current through the inductor and voltage across the inductor"; the board says $i_C(0),v_L(0)$. At [1:03:54] he said "minus 4, oh, sorry, 6 ohms." At [1:08:30] the spoken cancellation "2 times the quantity 2 plus 4 plus 12" is garbled; the board line $-24+2(2+4)+4(2)+v_L(0)+12=0$ is right.

### 9. (Not in this lecture) Preview: the ODE this example sets up for P4 practice
He stopped at the initial and final conditions and said next lecture would cover "how we actually do that analysis for currents or voltages as a function of time" [1:18:54]. The rest of this section is **my derivation**, checked numerically, so you can practice the P4 pipeline on the same circuit.

For $t>0$, node A gives $v_A=24-2(4+i_L)=16-2i_L$. The series branch gives $L\,\dfrac{di_L}{dt}=v_A-4i_L-v_C$. KCL at B gives $i_L+4=\dfrac{v_C}{6}+C\dfrac{dv_C}{dt}$:

$$L\frac{di_L}{dt}=16-6i_L-v_C,\qquad C\frac{dv_C}{dt}=i_L+4-\frac{v_C}{6}$$

Checks at $t=0$: $L\,di_L/dt=16-12-12=-8=v_L(0)$ ✓ and $C\,dv_C/dt=2+4-2=4=i_C(0)$ ✓.

Eliminate $i_L=C\dot v_C+v_C/6-4$:

$$LC\,\ddot v_C+\left(\frac{L}{6}+6C\right)\dot v_C+2v_C=40$$

With $L=0.2$ H and $C=8$ mF this is $0.0016\,\ddot v_C+0.08133\,\dot v_C+2v_C=40$, i.e. $\ddot v_C+50.8\,\dot v_C+1250\,v_C=25000$.
- $\alpha=25.4\ \text{s}^{-1}$ and $\omega_0=35.4$ rad/s. Since $\alpha<\omega_0$ the response is **underdamped**, with $\omega_d=24.6$ rad/s.
- Particular solution: $v_C(\infty)=40/2=20$ V ✓, which matches (c).
- Initial conditions: $v_C(0)=12$ V and $\dot v_C(0)=i_C(0)/C=4/0.008=500$ V/s. These are the "voltage and its derivative at $t=0$" he mentioned [0:46:20], and part (b) exists to supply the derivative.
- Solution: $v_C(t)=20+e^{-25.4t}\left[-8\cos(24.6t)+12.1\sin(24.6t)\right]$ V. The peak is $22.5$ V at $t=55.1$ ms, a 2.48 V overshoot above 20 V (ngspice: 22.48 V at 55.1 ms ✓).
- With the uncorrected **8 µF** the roots are $-20803$ and $-60.1$ s$^{-1}$ (**overdamped**). The initial and final values are the same, but the shape is completely different.

### 10. Key points (board f_0422, f_0426, f_0427) [1:14:19–1:16:52]
1. **In steady state, C → open, L → short.** "that makes the steady state situation considerably simpler."
2. **At transition points, e.g. $t=0$, $i_L$ and $v_C$ are continuous.** "if we know the steady state values, then when some change occurs, those steady state values have to be retained." He names these moments "**transition points**."
3. **Use the usual circuit analysis tools to build on (2) and obtain the other currents and voltages.** "the specifics of that will vary depending on the circuit, but that's the general idea."

---

## Ed Yu's conventions & notation

- **KCL means the sum of currents *leaving* the node equals 0.** He uses this in every KCL here (integrator, differentiator, node B). Each term is written as $(v_{\text{node}}-v_{\text{other}})/R$ or $C\,\frac{d}{dt}(v_{\text{node}}-v_{\text{other}})$. An incoming current gets a minus sign, e.g. $-4$ A for the current source feeding node B.
- **Capacitor $i=C\,dv/dt$ assumes passive sign convention:** "the current flowing from the higher voltage to the lower voltage, in the sense that we've defined $v$." [0:23:53]
- **KVL** goes around the loop starting at the source's − terminal: $-24\text{ V}+\dots=0$ (rises are negative, drops positive in his writing).
- **Op-amp labels:** $v_p$ (+, non-inverting), $v_n$ (−, inverting), $v_o$ (output), $v_s$ (source). Ideal: $i_p=i_n=0$, $v_p=v_n$.
- **Time labels:** $t=0^-$ is "the limit as $t$ goes to zero from the left... which is the steady state situation." Plain **$t=0$** (e.g. $i_C(0)$, $v_L(0)$) means **just after the change** ($0^+$ in textbook notation). He never writes $0^+$.
  > [!warning] Notation trap. The board step 0 says "initial ($t\le0$)". The initial *steady-state* values hold for $t<0$, but at $t=0$ itself the non-continuous quantities have already jumped ($i_C$: $0\to4$ A; $v_L$: $0\to-8$ V). Only $v_C$ and $i_L$ carry over. On the exam, write $0^-$ and $0^+$ explicitly to avoid ambiguity.
- **Steady-state redraws:** a source that is off is drawn as **two open terminals (o o)**, a shorted L as **two dots joined by a wire**, and an open C as **o + $v_C$ − o**. Each phase ($0^-$, $0$, $\infty$) gets its own redrawn circuit.
- **Unit step** $u(t)$: 0 for $t<0$, 1 for $t\ge0$. A source "$(4\text{ A})u(t)$" is equivalent to a switch that closes at $t=0$.
- **Final answers are boxed with units**, e.g. $i_C(0)=4$ A, $v_L(0)=-8$ V, $i_L(\infty)=-\frac23$ A, $20\text{ V}=v_C(\infty)$.
- **Justification is written next to the answer**, e.g. "by continuity" beside $v_C(0)$ and $i_L(0)$, and "By KCL at $t=0$ we see:" / "By KVL at $t=0$ we see:" before the equation.
- He calls the textbook "Ulaby et al." and cites section numbers (4-9, 5-6, Ch. 6).

---

## Intuition & explanations he gives

- **Why op-amp output current is useless mid-analysis:** "if you're in the middle of your analysis, then usually applying KCL at the output of an op amp will not help you that much because you'll always have this unknown current coming out of the op amp." [0:05:57] The output current is whatever the op-amp has to supply, and it is set by everything else.
- **Why cascades saturate:** gains multiply. "after those two stages, you can get a gain that is kind of the product of the individual gain factors... it's easier or more likely... that that will try to push the output of the op amp beyond its supply voltages." [0:04:37]
- **Solved op-amp outputs behave as voltage sources:** "Once you get the outputs of those op amps, right, those will basically act as voltage sources, and so you will know them." [0:08:04]
- **Saturation breaks $v_p=v_n$:** "if one of the op amps is in saturation, then yes, it could be the case that the input voltages are no longer equal to each other, right, because that's the nature of the transfer characteristic." [0:08:53]
- **Why a capacitor gives calculus:** "we'll be able to have currents that are derivatives of voltages rather than just being proportional to the voltage." [0:14:50]
- **Where to put C for an integrator:** C between $v_o$ and $v_n$, "because then that current will be proportional to the derivative of the output... through KCL applied at $v_n$, you'll get that the derivative of the output is proportional to $v_s$... And then if you integrate that expression, you'll get that the output voltage itself is proportional to the integral." [0:17:59–0:18:21]
- **Where the minus sign comes from:** "it comes in because we've started from the inverting amplifier configuration." [0:22:29]
- **The KCL sign doesn't depend on the bookkeeping direction:** summing all outgoing or all incoming currents gives the same equation and the same minus sign, "But what you cannot do is to say that the sum of the current coming in this way and the current going out that way has to be zero." [0:25:24]
- **What a hardware integrator is good for:** counting pulses from a turnstile or laser-break sensor. "for each event, you get a pulse, a voltage pulse. Then what this would do is effectively count up those pulses... if you care about cost and complexity, one op amp is probably better than a microprocessor." [0:25:57–0:26:59]
- **What a differentiator is good for:** detecting change. "if you have a constant input, then the output voltage would be zero. Every time it changes, then you'll get a non-zero output." [0:30:27]
- **First order means exponential:** "the solution to first order differential equation is always some form of exponential." [0:32:19]
- **Why two storage elements give 2nd order:** "you're going to have two terms with derivatives, and in order to get down to one variable, you end up having a second order differential equation." [0:33:57]
- **"Independent" storage elements:** two parallel capacitors combine into one $C_{eq}$, "so... even though it has two capacitors, [it] is not a second order circuit." [0:38:26–0:38:51]
- **A Thevenin equivalent doesn't reduce order:** "a Thevenin equivalent for a circuit is only how that circuit looks with respect to a specific set of output terminals... whereas if we're looking at a circuit as a whole... there won't be some unique set of... output and input terminals." [0:39:51–0:40:23]
- **Two unknown coefficients:** "you're going to have to integrate in some sense twice and you'll get two constants of integration." [0:45:45]
- **Why $v_C$ and $i_L$ are continuous** (a P1 classic): "for a capacitor, we know that the current is equal to the capacitance times $dv/dt$... So if the voltage across the capacitor were not continuous, that capacitor would have an undefined current... for the inductor, we know that the voltage is equal to $L\,di/dt$, and if the current $i$ were discontinuous, then the voltage would be undefined." [1:05:20–1:06:12]
- **Steady state:** the source has been off "for essentially infinite time... so the circuit will be in steady state, and therefore the inductor will be behaving as a short circuit, the capacitor as an open circuit." [0:51:49]
- **Finding $i_C(0)$:** at the node, it "is effectively the only unknown current in this circuit." [1:01:06] Pick the node or loop where exactly one quantity is unknown.
- **Unit step as a switch:** "having this unit step function here, it's sort of equivalent to having a switch... in series with that... current source that say closes at $t$ equal to zero." [0:50:06]

---

## Emphasis & exam intel

1. **Op-amp output current is unknown, so don't KCL there** [0:05:37–0:06:50]. This is written on the board as a capital "BUT": "KCL and KVL apply everywhere in the circuit, BUT the current at each op amp output is typically not known until everything else has been solved." It applies directly to P3, where the source current is found by KCL at the *input* node, never at an op-amp output.
2. **Check every op-amp's linear region** [0:03:15, 0:10:46]. It appears in both board lists: rule 2, "Make sure each op amp remains in its linear region, or if it doesn't, account for op amp saturation behavior", and approach step 3, "During analysis, account for op amp saturation behavior." It was repeated three times in total. This is the P3 sub-question "max input so every op-amp output stays within ±Vcc."
3. **Work from the inputs forward** [0:07:42, 0:09:28]: "Determine output voltages of individual op amps starting with those closest to input signals... Use output voltages of these op amps as input voltages for subsequent op amps in signal path."
4. **PS3 (RLC) is time-consuming** [0:00:31]: "you should not leave it for the last minute." It is also on the board with an exclamation mark. RLC is the P4 topic.
5. **"We want to spend actually a fair amount of time"** on second-order circuits, which have "significantly more complicated" behavior [0:36:23–0:36:32]. This signals a major exam topic (P4).
6. **The 4-step recipe (steps 0–3)** is on the board in full. The "two unknown coefficients" and "apply initial and/or final conditions" steps are the skeleton of every P4 solution.
7. **Continuity of $i_L$ and $v_C$** was stated four times: [0:56:40], [0:59:26], [1:05:20 student Q], and [1:15:06 key point 2]. The boxed answer reads "**by continuity**". Write that phrase as your justification.
8. **Key points list** (f_0427) is his own summary of how to do initial conditions: "1) In steady state, C → open, L → short. 2) At transition points, e.g., $t=0$, $i_L$ and $v_C$ continuous. 3) Use usual circuit analysis tools to build on (2) to obtain other currents + voltages."
9. **Draw a separate circuit for each phase.** He redrew the circuit three times ($t=0^-$, $t=0$, $t\to\infty$) and said "to make it a little bit easier for us to think about that, we're going to just redraw the circuit." [0:52:07] Since grading rewards written reasoning, show these redraws.
10. **Not every condition is always needed** [1:17:16–1:18:32]: "you don't necessarily have to get every single one, but it's good to know how to get all of them." In a full problem you can write the general solution first and then find only the conditions you need.
11. **Readings:** Ulaby §4-9 (instrumentation amplifier), the recorded solution to Ulaby 5.71 (multi-op-amp), §5-6 (op-amp circuits with capacitors), Ch. 6 (RLC).
12. **Logistics:** Labor Day (no class Mon Sep 7). No class Wed Sep 16 (recorded lecture, watch before Sep 21).

---

## Student questions

1. **[0:08:53] What if an op-amp saturates? Are the inputs still equal?** No. In saturation $v_p\neq v_n$ in general, "that's the nature of the transfer characteristic." Model the saturated output explicitly.
2. **[0:17:38] (Socratic answer) Where should the capacitor go for an integrator?** A student said: in the feedback path, between $v_o$ and $v_n$. Confirmed.
3. **[0:22:16] Is the integrator's minus sign just a labeling artifact?** No. It comes from the inverting configuration. A non-inverting integrator is possible but needs a voltage divider and is more complicated.
4. **[0:23:11] Which way is the current defined in the KCL?** Both currents point *out of* $v_n$, one left through $R$ and one up and right through $C$. $C\,dv/dt$ uses $v$ defined from higher to lower potential in the direction of the current, which is why it is $C\frac{d}{dt}(v_n-v_o)$.
5. **[0:24:23] If you took the current from $v_s$ toward $v_n$ instead, wouldn't you get $+1/RC$?** No. Summing all incoming currents gives $(v_s-v_n)/R+C\frac{d}{dt}(v_o-v_n)=0$, which is the same equation with the same minus sign. You can't mix one incoming and one outgoing current and set their sum to zero; setting them *equal* still gives the minus sign.
6. **[0:25:52] Why build a hardware integrator?** It is a cheap, simple counter of sensor pulses (turnstiles, laser beam breaks), and one op-amp is cheaper than a programmed microprocessor.
7. **[0:36:59] Can't you Thevenin-reduce a 2nd-order circuit to one storage element and make it first order?** A Thevenin equivalent works for any linear circuit, but it describes the circuit only at one specific pair of terminals and doesn't change the circuit's internal order. "Order" is about storage elements that cannot be combined, as in the parallel-C example. He offered to continue in office hours.
8. **[0:40:41] (sketch f_0153: series C, R, shunt C ∥ R) Can these two capacitors be combined?** No, so the circuit is second order.
9. **[0:56:05] Is there a reason you solved $v_C$ and $i_L$ first?** Yes. They are continuous, so their $0^-$ values carry straight over to $t=0$ when the source turns on. Everything else is found from them.
10. **[1:05:19] Why are $v_C$ and $i_L$ always continuous?** $i_C=C\,dv_C/dt$ and $v_L=L\,di_L/dt$, so a jump would require infinite (undefined) current or voltage.
11. **[1:16:57] Why find all six conditions instead of solving the ODE first and then finding only the two you need?** "It doesn't matter whether we find the initial and or final conditions before or after obtaining the general solution." This example was meant to show how to get each kind of condition.

---

## Exam relevance

**P1 (four "explain why" items):** likely prompts from this lecture, with the answer he gave:
- *Why are $v_C$ and $i_L$ continuous while $i_C$ and $v_L$ can jump?* Because $i_C=C\,dv_C/dt$ and $v_L=L\,di_L/dt$; a discontinuous $v_C$ or $i_L$ would require infinite current or voltage. The example shows it: $i_C$ went $0\to4$ A and $v_L$ went $0\to-8$ V at $t=0$, while $v_C=12$ V and $i_L=2$ A held.
- *Why is C an open and L a short in DC steady state?* All derivatives are zero, so $i_C=0$ and $v_L=0$.
- *Why is a circuit with two capacitors not necessarily second order?* If they combine (series or parallel) into one $C_{eq}$, the ODE stays first order.
- *Why does a 2nd-order solution need two conditions?* The ODE effectively integrates twice, giving two constants.
- *Why not apply KCL at an op-amp output?* The output current is unknown until the rest of the circuit is solved.
- *Why does a cascade of amplifiers risk saturation?* Gains multiply.
- *Why does the integrator or differentiator have a minus sign?* It is built on the inverting configuration.
- *Why do the initial and final values not depend on L and C?* Steady state replaces L and C by a short and an open, and at $t=0$ only continuity is used. The 8 µF → 8 mF correction changed nothing in (a)–(c).

**P2 (phasor ladder):** not covered directly. The phasor view of the integrator and differentiator ($-\tilde Z_f/\tilde Z_{in}$, my addition in §5) is the bridge.

**P3 (two-op-amp impedance synthesizer):** this lecture supplies the analysis method.
1. Apply $i_p=i_n=0$ and $v_p=v_n$ to **each** op-amp.
2. **Start at the op-amp nearest the source** and express its output in terms of $\tilde V_s$. Then treat that output as a known source for the second op-amp, and get the second output in terms of $\tilde V_s$.
3. Find the **source current** by KCL at the input node, where the source current enters through passive elements. **Do not use KCL at an op-amp output**; that current is unknown until the end.
4. **Saturation check (rule 2):** write each $|v_{o,k}|$ as (gain$_k$)$\times|V_s|$ and require each to be $\le V_{cc}$. The **binding constraint is the largest gain**, and since gains multiply in a cascade, the later stage usually binds. The max input is $V_{cc}/\max_k|\text{gain}_k|$.
5. **Equivalent element:** compute $\tilde Z_{in}=\tilde V_s/\tilde I_s$. A form $j\omega L_{eq}$ means an inductor and $1/(j\omega C_{eq})$ means a capacitor. The integrator and differentiator show how a capacitor in an op-amp stage introduces a $j\omega$ or $1/(j\omega)$ factor.

**P4 (2nd-order RLC transient):** this lecture is the setup half of P4. Follow it step for step:
1. **$t=0^-$ redraw:** L as a short, C as an open, with the pre-switch sources. Solve the resistive circuit for $i_L(0^-)$ and $v_C(0^-)$.
2. **Continuity:** $i_L(0^+)=i_L(0^-)$ and $v_C(0^+)=v_C(0^-)$. Write "by continuity."
3. **$t=0^+$ circuit:** the real L and C with the post-switch sources. KCL gives $i_C(0^+)$, so $dv_C/dt(0^+)=i_C(0^+)/C$. KVL gives $v_L(0^+)$, so $di_L/dt(0^+)=v_L(0^+)/L$. **These derivatives are the second initial condition the ODE needs.**
4. **$t\to\infty$ redraw:** L as a short, C as an open, with the post-switch sources. Solve for the final values, which equal the particular solution of the ODE.
5. **ODE:** KCL and KVL in terms of $i_L$ and $v_C$ (two first-order equations), then eliminate one variable. The worked example becomes $LC\,\ddot v_C+(L/6+6C)\dot v_C+2v_C=40$ (my derivation in §9).
6. **Solve:** two unknown coefficients, fixed by $v_C(0^+)$ and $\dot v_C(0^+)$.
7. **Physical check:** $v_C(\infty)$ from the ODE must match the $t\to\infty$ redraw ($40/2=20$ V ✓), and the $t=0$ derivatives must match the $0^+$ KCL and KVL. Superposition at $t\to\infty$ is a quick independent check.

Practice target: finish §9 by hand. The answer is $v_C(t)=20+e^{-25.4t}[-8\cos 24.6t+12.1\sin 24.6t]$ V, peak 22.5 V at 55.1 ms.
