---
course: ECE 411H
date: 2026-08-26
instructor: Prof. Ed Yu
topic: Inductor physics (Ampère + Faraday → L = μN²S/ℓ, v = L di/dt); first-order circuits; RC switch example (debouncing); two-branch RL switch example; key steps for RC/RL analysis (DC steady state, continuity, ODE, ICs)
reading: Ulaby/Maharbiz/Furse 3e, Chapter 5 (RC and RL first-order circuits); extra examples are the Ulaby 5.36 and 5.50 solution videos on Canvas
sources: Recordings/2026-08-26/transcript.txt + frames (all 60 pages.txt frames + 13 extra viewed). AUDIO DROPOUT 0:38:13–1:04:18, so that stretch is reconstructed from frames only
tags: [ece411, lecture, inductor, rc, rl, first-order, transient, continuity, exam1]
---

# 2026-08-26: Inductors and first-order RC/RL circuits

> [!warning] Audio gap
> The transcript jumps from **[0:38:13] to [1:04:18]**. At 1:04:18 he says "Hopefully the audio is back now … if you see something like that … please let me know." For that stretch (the end of the RC solution, the debouncing application, the RL circuit setup and its $t<0$ analysis) the board frames are the only source. Spoken explanations from that window are lost. Wherever I infer intent there, it is marked (?).

## Summary

- **Inductors store electric current, or equivalently energy in the form of a magnetic field.** For a long solenoid (core permeability $\mu$, cross-section $S$, $N$ turns over length $\ell$):
  - Ampère's law gives $B=\mu Ni/\ell$.
  - Faraday's law around the whole N-turn wire gives $\text{emf}=-\frac{d}{dt}(NBS)=-\frac{\mu N^2S}{\ell}\frac{di}{dt}=-L\frac{di}{dt}$, so $\boxed{L=\mu N^2S/\ell}$.
  - To drive $i$ through $L$ the circuit must apply $\boxed{v=+L\,di/dt}$.
- **First-order circuits.** C or L makes the circuit equations differential. A single *equivalent* C or L gives a first-order ODE, and the circuit is called a first-order circuit.
- **RC example.** 5 V source, 10 kΩ, a switch that closes at $t=0$ and shorts the node feeding $R$, and $C$ to ground.
  - For $t<0$ the capacitor is an open circuit at DC, so $v_\text{out}=5$ V.
  - For $t\ge0$, KCL gives $\dfrac{dv_\text{out}}{dt}=-\dfrac{1}{RC}v_\text{out}$, so $v_\text{out}=Ae^{-t/RC}$.
  - **Continuity of $v_\text{out}$ (the capacitor voltage) at $t=0$** fixes $A=5$ V, giving $\boxed{v_\text{out}=5e^{-t/RC}\ \text{V}}$.
  - Application: **switch debouncing**.
- **RL example.** 48 V source, 4 kΩ, and two parallel branches ($6$ kΩ + $1.2$ H, $12$ kΩ + $0.36$ H). An SPDT switch moves from ① to ② at $t=0$.
  - For $t<0$ the inductors are short circuits, so $v_1=24$ V, $i_1=4$ mA, $i_2=2$ mA, $i_3=0$.
  - **$i_L$ is continuous**, so those currents are the initial conditions. Each branch then decays on its own: $i_1=4e^{-t/(0.2\text{ ms})}$ mA and $i_2=2e^{-t/(30\ \mu\text{s})}$ mA.
  - $i_3=i_1+i_2$.
- **Key points (board):**
  1. "In steady state, inductors act as short circuits and capacitors act as open circuits."
  2. "Solve the steady-state circuit configuration(s) first to obtain initial conditions."
  3. "Obtain + solve differential equations using initial conditions to determine constant coefficients."
- **Continuity is physical, not a convenience** (Q at 1:19:59). $v_C$ and $i_L$ "have to be continuous because otherwise … a big spike in voltage or current." Other quantities can jump; in reality they change "at some rapid but finite rate."
- **Time constants:** $\tau=RC$ and $\tau=L/R$. He writes them inline as $e^{-t/(L/R)}$ and $e^{-t/(2\times10^{-4}\,\text{s})}$.
- The planned op-amp start was not reached.

---

## Content

### [0:00:25] Announcements (frames f_0003, f_0004)
1. A hard-copy handout on **Problem Set tips** is in the back. He expects it to be the last paper handout. At [1:20:51] he says he forgot "one thing about these homework tips" and will mention it next class.
2. Complete the Background Survey.
3. Refresher notes on **sinusoidal signals/phasors and semiconductors** (at 302 level) are on Canvas. They are optional.

### [0:01:46] Student Q: can a circuit have no solution or many? (frames f_0005, f_0006)
- "For linear circuits, there will be a **unique solution** … if it's a properly constructed circuit, it should have exactly one solution, not zero or two."
- **Trick example he drew:** two ideal voltage sources **in parallel**, both with + on top, connected to "the rest of the circuit".
  - If their values differ, the configuration is impossible: KVL around the loop fails.
  - If the values are equal, the current through each one is indeterminate ("it could be distributed in any way").
  - In a real circuit, each source's small series resistance would set the split.
- "Typically, you won't see something like that … in problems for this course. **But you should understand those kinds of situations also.**"

### [0:04:18] Plan for the day
Inductors ("less intuitive than capacitors, but they're also important"). Then first-order RC and RL circuits, building on Monday's recitation review of circuit analysis. Then op amps if time allows; it didn't.

### [0:05:21] Inductors: physics and $v=L\,di/dt$ (frames f_0010, f_0030, f_0041, f_0052, f_0064–f_0066, f_0073–f_0078)
**Board definition:** "**Inductors** are circuit components that store electric current or, equivalently, energy in the form of a magnetic field."

**Setup (f_0010).**
- A core, drawn in blue, with **magnetic permeability $\mu$** and **cross-sectional area $S$**. It can be air, but "you can make a better inductor if you put some magnetic material in there."
- A coil of **$N$ turns over length $\ell$**.
- An independent current source $i$ (arrow up) drives the coil, and the coil voltage $v$ has **+ at the top and − at the bottom**. Current enters the + terminal, which is the passive sign convention.
- The field $\vec B$ (red) runs up through the core.
- **Approximation:** a very long coil, ideally infinite, so $B$ is non-zero **only inside** and uniform there. "If it's a finite length, then the field kind of comes out at the ends and then has to circle back around."

**Strategy** [0:09:50]: relate $B$ to $i$ (Ampère), relate the emf to $B$ (Faraday), and eliminate $B$ to relate $v$ to $i$. The ratio is $L$.

**Step 1: Ampère's law** (board, f_0030):
$$\oint_C\vec B\cdot d\vec l=\mu\int_{S_C}\vec J\cdot d\vec S_C .$$
- A student offered the "Gauss's law for magnetism" analog; he corrected it: "it's actually … the curl of the field, not the divergence." The differential form is $\nabla\times\vec H=\vec J$ plus a time-dependent term "we're not going to worry about."
- **Path $C$** (green dashed rectangle): one vertical side runs up *inside* the coil along its full length $\ell$, the other side is outside, and two short end segments join them.
  - Inside segment: contributes $B\ell$, since $B$ is uniform and parallel to the path.
  - Outside segment: contributes 0, since $B=0$ there.
  - End segments: contribute 0, because "the magnetic field is going to be perpendicular to the path."
- **Right side:** the wire passes through the surface bounded by $C$ **$N$ times**, so $\int\vec J\cdot d\vec S=Ni$.
- Board: "The magnetic field inside the coil is then given by"
$$B\ell=\mu Ni\quad\Longrightarrow\quad B=\mu\frac{Ni}{\ell}.$$

**Step 2: Faraday's law and Lenz** (board, f_0041 → f_0052):
$$\oint_{C'}\vec E\cdot d\vec l=-\frac{d}{dt}\int_{S'}\vec B\cdot d\vec S,\qquad C'=\text{path along entire wire loop (}N\text{ turns)}.$$
- Lenz's law in words (board): "**A change in magnetic flux through a loop induces an electromotive force (emf), in volts, around the loop opposing the change.**" "The minus sign in the equation is what tells us that it's opposing that change."
- The integral of $\vec E$ along the wire is the emf. Because the path goes around $N$ times, the flux through $S'$ is $N\cdot BS$; here $BS$ is "the flux through one loop."
- Substitute Step 1. Only $i$ changes in time:
$$\text{emf}=-\frac{d}{dt}(NBS)=-\frac{d}{dt}\left(\frac{\mu N^2S}{\ell}\,i\right)=-\underbrace{\left(\frac{\mu N^2S}{\ell}\right)}_{L\ =\ \text{inductance}}\frac{di}{dt}=-L\frac{di}{dt}.$$
- $L$ "tells us … for a given rate of change in the current, how much emf do we develop."

**Step 3: from the inductor's emf to the circuit's $v$** (board, f_0073–f_0078):
- $-L\,di/dt$ is "from the perspective of the inductor … what the inductor is doing in response to the change in the current."
- "From the circuit perspective, if we want to basically force some current $i$ to flow through that loop … we need to apply a voltage that overcomes this emf … that voltage has the opposite sign of the emf."
- Board: "**Then to induce current $i$ to flow through an inductance $L$, we apply a voltage $+L\,\dfrac{di}{dt}$.**"
- Circuit drawn: a voltage source $v$ (+ on top) with current $i$ flowing clockwise (arrow → along the top wire) down through $L$:
$$\boxed{v=L\frac{di}{dt}}$$
- [0:25:11] "If the current's changing rapidly, you need a lot of voltage. If it's changing a little bit or not at all, you need to have little or no voltage." This is the seed of "L is a short at DC."

**Student Q [0:25:27]:** *Is $S'$ the area through the loop $C'$?* "S is the cross-sectional area of this core … the area inside one loop, and then S′ is the area that is associated with going around N times, so it's going to be $N\times S$."

**Why the physics matters** [0:25:58]: "For the rest of the course, we're going to sort of hide away all this stuff about electric fields and magnetic fields … and just think about inductors and capacitors as **lumped circuit elements**." But to design a real C or L, for example on a chip, you need to know how to make it larger or smaller. "Especially inductors, it's actually not that easy to make loops and things like that on a planar surface and do it very compactly."

> [!note] Scale check (my numbers)
> An air-core solenoid ($\mu_0$) with $N=100$, $S=1\ \text{cm}^2$ and $\ell=1$ cm gives $L=\mu_0N^2S/\ell\approx126\ \mu$H. That fits 8/24's "one henry is a big inductor": $L\propto N^2$, so large $L$ needs many turns and a high-$\mu$ core.

### [0:27:19] RC and RL first-order circuits (frames f_0082, f_0087, f_0091, f_0092)
Board heading: **"RC and RL First-Order Circuits."** **Reading: Ulaby et al., Chapter 5.**

**On his note style** [0:28:15]: "I write everything out very completely in sentences … I want your notes to be a useful resource for you after class or maybe even after this course … if I just sort of sketched out things … when you go back and look at it later … it's sort of mysterious as to what was really going on." This is also a model for how to write exam solutions.

**Board:**
- "Circuits containing capacitors and/or inductors lead to **differential** rather than algebraic equations."
- "Circuits with a single (equivalent) capacitor or inductor lead to **first-order** differential equations, and are called **first-order circuits**."

Spoken detail:
- A first-order circuit is one "whose behavior is governed by a first order differential equation, meaning you only have $d/dt$, you don't have $d^2/dt^2$."
- He adds "or if you have certain configurations" [0:32:33].
- **"Equivalent":** "if you have two capacitors in parallel, and then resistors everywhere else, that's still going to be a first order circuit because you can combine those two capacitors in parallel very easily into a single capacitor."
- Why it matters [0:30:44]: "solving differential equations is harder than solving algebraic equations, and gives you richer behavior."

### [0:33:43] Example 1: RC circuit analysis (frames f_0097, f_0102, f_0123, f_0128, f_0149, f_0155, f_0159, f_0181, f_0183, f_0190, f_0198, f_0202)
**Circuit (f_0097).**
- An independent source of **5 V** (+ on top, − to the grounded bottom rail). Its top terminal runs along the top wire to a **10 kΩ** resistor going down to node **A**.
- From A, a switch (marked "t=0" in green, with a closing arrow) goes down to the ground rail.
- Also from A, a resistor **$R$** goes right to node **out**.
- Capacitor **$C$** runs from *out* to the ground rail.
- Output port: $v_\text{out}$, + at node *out* and − at ground. So $v_\text{out}=v_C$.
- The switch is open for all $t<0$ "back to minus infinity" and **closes at $t=0$**.
- Board: "Solve for $v_\text{out}(t)$ if switch closes at $t=0$." $R$ and $C$ are symbolic.

**1) Switch open ($t<0$)** [0:35:29]. He asks the class, and someone answers 5 V.
- Reasoning (spoken): the switch has been open a long time, so nothing is changing, and "for this capacitor here, the current is going to be zero because $dv/dt$ is zero."
- The circuit is a single loop through 10 kΩ, $R$ and $C$, so the loop current is 0, there is no drop across either resistor, and "this five volts will carry over all the way over to here."
- Board: $\boxed{v_\text{out}(t)=5\text{ V}\ \ (t<0)}$.

**2) Switch closes at $t=0$** [0:37:03].
- Node A is now tied directly to ground, so it sits at 0 V.
- KCL at the $v_\text{out}$ node, summing *outgoing* currents: left through $R$ to node A at 0 V, plus down through $C$, with "nothing connected out here, so there's zero current" out of the port.
- Board:
$$\text{KCL @ }v_\text{out}:\quad\frac{v_\text{out}-0}{R}+C\frac{dv_\text{out}}{dt}=0\;\Longrightarrow\;\frac{dv_\text{out}}{dt}+\frac{1}{RC}v_\text{out}=0,\ \text{or}\ \frac{dv_\text{out}}{dt}=-\frac{1}{RC}v_\text{out}.$$

*— audio drops out at 0:38:13; the rest of this example comes from the board —*

- Board: "The solution is $v_\text{out}(t)=Ae^{-t/RC}$, $A$ = constant."
- Board: "**$A$ is determined by applying appropriate boundary conditions, in this case, that $v_\text{out}(t)$ must be continuous at $t=0$.**"
- Board: $\Rightarrow A=5$ V, so
$$\boxed{v_\text{out}(t)=(5\text{ V})\,e^{-t/RC}\quad(t\ge0)}.$$

**Sketches (f_0204, f_0206):**
- $v_s(t)$: he labels the effective drive seen by the RC, i.e. the voltage at node A (?), as 5 V for $t<0$ and dropping to 0 at $t=0$.
- $v_\text{out}(t)$: flat at 5 V, then an exponential decay from $t=0$ with a tick at $t=RC$ on the time axis (one time constant). The value there is $5e^{-1}\approx1.84$ V.

> [!note] Role of the 10 kΩ (my inference; audio missing)
> After the switch closes, node A is clamped to 0 V. The 10 kΩ therefore drops out of the $v_\text{out}$ dynamics and only sets the source current through the closed switch, $5/10\text{k}=0.5$ mA. Without it the switch would short the 5 V source directly. Before closing, it carries no current because $C$ is open at DC. $\tau=RC$ involves only $R$ and $C$.

**Verification:** ngspice with arbitrary $R=1$ kΩ and $C=1\ \mu$F gives $v_\text{out}(0^-)=5.000$ V and $v_\text{out}(\tau)=1.8394$ V, against $5e^{-1}=1.8394$ V. ✓

**"Why is this useful?" (board, f_0207–f_0219)**
- Board: "**One application is switch 'debouncing'**: when the switch is first closed, the physical contact may form intermittently at first."
- Sketch: $v_s(t)$ at 5 V, then a train of narrow 5 V spikes just after $t=0$ (the switch bouncing), then 0.
- Matching sketch of $v_\text{out}(t)$: only small ripples near the 5 V level (circled in red and ticked), then a smooth exponential decay.
- Board: "**Adding R and C prevents large, abrupt changes in $v_\text{out}$.**" In other words, the RC low-pass with $\tau=RC$ much longer than the bounce duration filters out the bounces. (The spoken explanation was lost to the audio gap.)

### [≈0:57:36] Example 2: RL circuit analysis (frames f_0220, f_0229, f_0233, f_0240, f_0244, f_0286, f_0301, f_0310, f_0332, f_0335, f_0355, f_0369, f_0378, f_0381, f_0394, f_0407, f_0416, f_0430, f_0440–f_0453, f_0474–f_0481, f_0514, f_0523)
**Circuit (f_0229, final form in f_0440).**
- Source $v_s=48$ V (+ on top). From its + terminal, a **4 kΩ** resistor runs along the top to node **$v_1$**.
- From $v_1$ the top rail continues to two parallel branches, both returning to a common **bottom node marked as ground**:
  - Branch 1: $R_1=6$ kΩ in series with $L_1=1.2$ H, current $i_1$ downward.
  - Branch 2: $R_2=12$ kΩ in series with $L_2=0.36$ H, current $i_2$ downward.
- From $v_1$ a vertical wire drops to switch terminal **②**. The current in that wire is **$i_3$, drawn upward** (from ② into node $v_1$).
- **SPDT switch:** the pole is wired to the ground node at the bottom of the branches.
  - Position **①** connects it to the bottom-left wire to the source's − terminal, which completes the source loop.
  - Position **②** connects ground to the wire up to $v_1$, which shorts the top of the branches to their bottom.
- "Solve for $i_1(t)$, $i_2(t)$, $i_3(t)$ if switch moves from ① to ② at $t=0$."

**1) Switch at ① for $t<0$** (board, f_0240/f_0244; spoken explanation lost to the audio gap):
- Board: "**$L_1, L_2$ behave as short circuits since $di/dt=0$.**"
- Board: "By voltage division:"
$$v_1=\frac{6\text{k}\,\|\,12\text{k}}{4\text{k}+6\text{k}\,\|\,12\text{k}}(48\text{ V})=24\text{ V}\qquad(6\text{k}\|12\text{k}=4\text{k},\ \text{so }4/8\text{ of }48\text{ V}).$$
- Board: "Thus, for"
$$\boxed{t<0:\quad i_1=\frac{24\text{ V}}{6\text{ k}\Omega}=4\text{ mA},\quad i_2=\frac{24\text{ V}}{12\text{ k}\Omega}=2\text{ mA},\quad i_3=0}$$
- Check: the 4 kΩ carries $48/(4\text{k}+4\text{k})=6$ mA $=i_1+i_2$ ✓.

**2) Switch moves to position ② at $t=0$, so $t\ge0$** (audio returns at 1:04:18):
- **Initial conditions at $t=0$** (board, f_0310): "$v_1=0$, $i_1=4$ mA, $i_2=2$ mA, **since $i$ must be continuous for inductors.**"
- **Why $i_L$ is continuous** [1:05:31]: "the current voltage relationship for an inductor is that the voltage is equal to $L\,dI/dt$. So if $I$ were discontinuous, that derivative $dI/dt$ would be undefined and the voltage would be undefined, which we cannot have. So we know that **the current through an inductor always has to be continuous**."
- **Why $v_1$ may jump** [1:06:20]: "This is ground down here. We can always choose it to be ground as our reference … it's going to go from whatever it was up here, 24 volts, to zero, and **that can happen instantaneously when the switch moves**." Board: $v_1(0)=0$.
- $i_3$ "we can figure out … basically from KCL."

- **Branch 1** [1:08:16]. With the switch at ②, the top and bottom of each branch are both at 0 V, "so the total voltage drop across $R_1$ and $L_1$ has to be zero." Board:
$$R_1i_1+L_1\frac{di_1}{dt}=0\;\Longrightarrow\;\frac{di_1}{dt}=-\frac{R_1}{L_1}i_1$$
$$\Longrightarrow\;i_1(t)=\big[i_1(t{=}0)\big]e^{-t/(L_1/R_1)}=\boxed{(4\text{ mA})\,e^{-t/(2\times10^{-4}\,\text{s})}=i_1(t)}$$
  - "Mathematically it has the same form as the equation … for voltage in the RC circuit, except that the coefficient here, instead of being $-1/RC$, it's $-R_1/L_1$."
  - "We took the **shortcut of specifying the constant as the initial value**, because … if we substitute $t=0$ in here, this is just going to be 1."
  - Arithmetic said aloud: $L_1/R_1=1.2\text{ H}/6\text{ kΩ}=0.2\times10^{-3}=2\times10^{-4}$ s. "Exponential decay with a time constant of 0.2 milliseconds."

- **Branch 2** [1:11:25]: "exactly the same … except that we have $R_2$ and $L_2$." Board:
$$i_2(t)=\big[i_2(t{=}0)\big]e^{-t/(L_2/R_2)}=\boxed{(2\text{ mA})\,e^{-t/(3\times10^{-5}\,\text{s})}=i_2(t)}$$
  Arithmetic: $0.36/12\text{k}=0.03\times10^{-3}=3\times10^{-5}$ s, i.e. 30 µs.

- **Why it is still "first order" with two inductors** [1:11:25]: "these two branches are in parallel, that's why this is a first order circuit despite having two inductors, right, because this branch and this branch, they always have the same voltage, so they're not really interacting with each other."

- **$i_3$** [1:13:30]: "once we have the switch in position 2, then there's no current in this part of the circuit [source + 4 kΩ], so then $I_3$ just has to be equal to $I_1+I_2$, … by KCL at that top node." Board:
$$i_3(t)=i_1(t)+i_2(t)\;\Longrightarrow\;\boxed{i_3(t)=4e^{-t/(2\times10^{-4}\,\text{s})}+2e^{-t/(3\times10^{-5}\,\text{s})}\ \text{mA}}\quad(t\ge0).$$
  So $i_3$ jumps from 0 at $t<0$ to 6 mA at $t=0^+$. That is allowed, because $i_3$ is not an inductor current.

**Verification** (python + ngspice, SPDT switch modeled with two complementary switches, DC operating point taken in position ①):
- $i_{L1}(0^+)=3.99999$ mA.
- $i_{L1}(\tau_1)=1.4715$ mA, against $4e^{-1}=1.4715$ mA ✓.
- $i_{L2}(\tau_2)=0.73574$ mA, against $2e^{-1}=0.73576$ mA ✓.
- DC node voltages 6 µV ≈ 0 after switching ✓.
- $i_3$: 6.00 mA at $0^+$, 4.18 mA at 30 µs, 1.47 mA at 0.2 ms, 0.027 mA at 1 ms.

> [!note] Derived quantities he did not compute (useful for P4-style reasoning)
> - **Inductor voltages jump** even though the currents don't. Before switching, $v_{L1}=v_{L2}=0$ (DC shorts). At $0^+$, KVL in each branch gives $v_{L1}(0^+)=-R_1i_1(0)=-24$ V and $v_{L2}(0^+)=-R_2i_2(0)=-24$ V.
> - Hence $\dfrac{di_1}{dt}(0^+)=v_{L1}(0^+)/L_1=-20$ A/s, which equals $-i_1(0)/\tau_1$ ✓, and $\dfrac{di_2}{dt}(0^+)=-66.7$ A/s ✓. This "get $di_L/dt(0)$ from $v_L(0)/L$" step is exactly what 2nd-order RLC problems need.
> - Stored energy at $t=0$: $\tfrac12L_1i_1^2=9.6\ \mu$J and $\tfrac12L_2i_2^2=0.72\ \mu$J. All of it is dissipated in $R_1$ and $R_2$ as $t\to\infty$.

> [!warning] Looseness in "first-order circuit" for this example (conceptual, not an arithmetic error)
> After $t=0$ the two R–L branches are *decoupled* first-order circuits, each with a single $\tau$. But **$i_3=i_1+i_2$ is a sum of two exponentials with different time constants**, so $i_3$ alone satisfies a *second*-order ODE. The board's rule says a single *equivalent* L leads to first order, and $L_1$, $L_2$ cannot be merged into one equivalent L here (each has its own series R). The precise statement is that the circuit has two state variables that happen not to interact for $t\ge0$. Keep this in mind for P1 ("why can't a first-order circuit be underdamped?"). That argument applies to a circuit governed by **one** first-order ODE, with one real root $s=-1/\tau$.

**Student Q [1:14:38]:** *Why is the current in the 4 kΩ resistor zero after switching?* "We have moved the switch from position 1 to position 2 … this branch goes around like this, but then it's not connected to anything over here, right, so there's no current flowing along any of this series of branches." Follow-up [1:15:15]: you have to *realize* this from the topology, since "you wouldn't be able to solve for that independently because you wouldn't necessarily know independently what the voltage is over here." The left source/4 kΩ part is floating, so its node voltage is undefined relative to ground.

### [1:15:47] Key points for RC, RL circuit analysis (board, f_0488, f_0502, f_0497)
1. "**In steady state, inductors act as short circuits and capacitors act as open circuits.**" Spoken: "so that's an important thing to realize and use."
2. "**Solve the steady-state circuit configuration(s) first to obtain initial conditions.**" Spoken: "which for us here was $t$ less than 0 … or maybe sometimes is more than one."
3. "**Obtain + solve differential equations using initial conditions to determine constant coefficients.**" Spoken: "go through sort of the normal methods of circuit analysis to get the differential equations."

Board: "See recordings of solutions to **Ulaby 5.36, Ulaby 5.50** on Canvas for more examples" (the "video problem solving examples").

> [!note] What he did *not* state in this lecture
> Both examples decay to zero, so he never wrote the general forced form $x(t)=x(\infty)+[x(0^+)-x(\infty)]e^{-t/\tau}$, nor $\tau=R_\text{Th}C$ or $\tau=L/R_\text{Th}$ with a Thévenin resistance. His method is always: steady state, then ICs via continuity, then KCL/KVL to an ODE, then $Ae^{-t/\tau}$ (+ particular solution), then fix $A$ from the IC. The 9/14 note shows he keeps exactly this pipeline for 2nd order, with the "final condition" step added.

### [1:18:59] End-of-class questions
- *What are RL circuits used for, if RC is for debouncing?* [1:19:25] "If you want to make **resonance circuits** … circuits that have, say, elevated response at a particular frequency, like a filter … that's probably the most … common situation for using inductors. **Inductors are often hard to make, so you kind of use them if you really need them.**"
- *How can some quantities be continuous while others jump? Is that an assumption, or real?* [1:20:08] "In real life, it is the case that, you know, **voltage across a capacitor and current for an inductor, they have to be continuous because otherwise, what you would end up getting is like a big spike in voltage or current.** The other quantities, you know, we assume that they can change discontinuously, but in practice they'll change at some rapid but finite rate that's determined by other things and not inherently the, you know, things like continuity across capacitors or inductors."

---

## Ed Yu's conventions & notation

- **Passive sign convention everywhere.** Current enters the + terminal of the element.
  - Solenoid (f_0010): $i$ from the source flows into the + (top) end of the coil, $v=L\,di/dt$.
  - $v$-source driving $L$ (f_0075): $i$ leaves the source's + terminal and enters $L$ at the top, $v=L\,di/dt$.
  - RL branches: $i_1$, $i_2$ point *down* from $v_1$ through $R$ then $L$, so the KVL is $R_1i_1+L_1\,di_1/dt=0$ with both terms positive.
- **Reference directions are drawn first and then kept**, even when the true current is opposite. Example: $i_3$ is defined upward in the switch wire, and the sign then falls out of KCL ($i_3=i_1+i_2>0$).
- **Ground choice:** "We can always choose it to be ground as our reference." In the RL example he added the ground symbol at the bottom of the branches after drawing the circuit.
- **KCL written as "sum of outgoing currents = 0"**, e.g. $\frac{v_\text{out}-0}{R}+C\frac{dv_\text{out}}{dt}=0$, with node voltages written explicitly ("$-0$").
- **First-order ODE in two equivalent forms:** $\frac{dx}{dt}+\frac{1}{\tau}x=0$ "or" $\frac{dx}{dt}=-\frac{1}{\tau}x$. Solution $x=Ae^{-t/\tau}$ with "A = constant", then A from the IC. He also uses the shortcut $x(t)=[x(t{=}0)]\,e^{-t/\tau}$.
- **Time constant:** $\tau=RC$ and $\tau=L/R$, written inline as $e^{-t/RC}$, $e^{-t/(L_1/R_1)}$, and with numbers as $e^{-t/(2\times10^{-4}\,\text{s})}$ (units inside the exponent's denominator). He marks $t=RC$ on sketches as the one-time-constant tick.
- **How he finds initial values:**
  1. Analyze the $t<0$ configuration as **DC steady state**: L becomes a short ("since $di/dt=0$"), C becomes open ("$i=0$ because $dv/dt=0$").
  2. Get the $v_C$ and $i_L$ values by voltage division or Ohm's law.
  3. Carry them across $t=0$ by **continuity of $v_C$ and $i_L$**.
  4. Recompute everything else (e.g. $v_1$, $i_3$) from the *new* topology at $t=0^+$, because those may jump.
- **How he finds final values (implicit here):** source-free, so everything $\to0$. Spelled out explicitly from the RLC lectures onward.
- **Validity ranges always attached:** "($t<0$)", "($t\ge0$)". Final answers are boxed with units ("(5 V)", "(4 mA)", "mA").
- **Board style:** full sentences ("A is determined by applying appropriate boundary conditions, in this case, that …"). Numbered phases "1) switch open ($t<0$)", "2) switch closes at $t=0$". He writes "initial conditions at $t=0$" rather than distinguishing $0^-$/$0^+$ in this lecture.

## Intuition & explanations he gives

- **What an inductor does** [0:05:42]: "What inductors do is essentially they can act as a store of electric current or correspondingly of energy in the form of a magnetic field … the magnetic field that you get from that particular configuration of current flow."
- **Lenz's law in his words** [0:17:05]: "If you have a change in the magnetic field flux, say inside a coil, then … you will develop an electromotive force, an EMF, that tries to oppose that change. So if this field decreases … this inductor will try to increase the current that's flowing here … that increase in the current will then … have the effect of increasing the field, so opposing that initial change. And then in order to drive that current from the circuit, you need to apply a voltage that basically cancels out that EMF. So it'll have the opposite sign."
- **Inductor emf vs. applied voltage** [0:23:43]: "$-L\,di/dt$: that's kind of from the perspective of the inductor … what the inductor is doing in response to the change in the current. But then from the circuit perspective, if we want to … force some current $i$ to flow … we need to apply a voltage that overcomes this emf."
- **L at DC, the root of "L = short"** [0:25:11]: "If the current's changing rapidly, you need a lot of voltage. If it's changing a little bit or not at all, you need to have little or no voltage."
- **C at DC, the root of "C = open"** [0:36:06]: "if it's been in this state for a long time, then the currents and voltages are not going to be changing. So for this capacitor here, the current is going to be zero because $dv/dt$ is zero."
- **Why $i_L$ must be continuous (the P1 answer, nearly verbatim)** [1:05:31]: "the voltage is equal to $L\,dI/dt$. So if $I$ were discontinuous, that derivative $dI/dt$ would be undefined and the voltage would be undefined, which we cannot have. So we know that the current through an inductor always has to be continuous." The dual argument for C is $i=C\,dv/dt$: a $v_C$ jump would need infinite current.
- **Physical meaning of continuity** [1:20:16]: "voltage across a capacitor and current for an inductor, they have to be continuous because otherwise, what you would end up getting is like a big spike in voltage or current."
- **Non-state variables can jump** [1:06:36]: $v_1$ goes "from 24 volts to zero, and that can happen instantaneously when the switch moves." In reality, such jumps happen "at some rapid but finite rate that's determined by other things" [1:20:34].
- **Why C/L circuits are harder and richer** [0:29:38]: resistor-only circuits give algebraic equations, "relatively easy to solve. If you have capacitors and/or inductors … you don't get algebraic equations, you get differential equations. And solving differential equations is harder … and gives you richer behavior."
- **RL ≅ RC mathematically** [1:08:46]: "it has the same form as the … differential equation that we got for voltage in the RC circuit, except that the coefficient here, instead of being $-1/RC$, it's $-R_1/L_1$."
- **Decoupled parallel branches** [1:11:30]: "they always have the same voltage, so they're not really interacting with each other."
- **Debouncing** (board): "Adding R and C prevents large, abrupt changes in $v_\text{out}$." The RC can't follow the fast bounce transients, because $v_C$ changes only at a rate set by $\tau$.
- **Parallel ideal voltage sources** [0:03:11]: with different values the configuration is impossible; with equal values the current split is undefined; real series resistance resolves it.
- **Inductors in practice** [1:19:46]: "Inductors are often hard to make, so you kind of use them if you really need them." The classic use is resonant circuits and filters. On chips, "it's actually not that easy to make loops … on a planar surface and do it very compactly" [0:27:00].

## Emphasis & exam intel

- [1:16:06] **"In steady state, inductors act as short circuits, and capacitors act as open circuits, all right, so that's an important thing to realize and use."** This is key point #1 on the board and a recurring Exam-1 P1 item.
- [1:05:31] **"The current through an inductor always has to be continuous"**, with the full $dI/dt$ argument. The board says "since $i$ must be continuous for inductors." The RC board says "$v_\text{out}(t)$ must be continuous at $t=0$." This continuity pair is recurring P1 material and the core of every P4 initial condition.
- [1:16:47] **Procedure:** "first we solved for the steady state circuit configuration … to obtain the initial conditions … then … the normal methods of circuit analysis to get the differential equations … using then the initial conditions to determine the constant coefficients." This is the P4 skeleton, and he keeps it for 2nd-order RLC (cf. the 9/14 note: Step 0 → 1 → 2 → 3).
- [1:20:16] **Only $v_C$ and $i_L$ are guaranteed continuous**; "the other quantities … can change discontinuously." For example, $v_1$ jumps 24 → 0 V [1:06:36] and $i_3$ jumps 0 → 6 mA.
- [0:28:26] **He writes complete sentences so notes are readable later.** That matches 8/24's "most of the credit is … showing us that reasoning." Write exam solutions the same way: state "L acts as a short since $di/dt=0$", "by continuity of $i_L$", and so on.
- [0:04:04] Ill-posed circuits (parallel ideal voltage sources): "you won't see something like that … in problems for this course. But you should understand those kinds of situations also." A possible P1-style twist.
- [1:11:25] Why two inductors can still give a "first-order" circuit: the branches are in parallel, so they see the same (zero) voltage and don't interact. Also see the warning above about $i_3$.
- [1:18:28] Extra worked examples are the **Ulaby 5.36 and 5.50 solution videos** on Canvas.
- [0:25:58] After today, C and L are lumped elements, but "it's important to understand the physics of these components." A possible P1 "how would you increase L/C?" item: $L=\mu N^2S/\ell$ and $C=\epsilon A/d$.

## Student questions

- [0:01:46] *Can a linear circuit have zero or multiple solutions?* A properly constructed linear circuit has exactly one. The counterexample is parallel ideal voltage sources (impossible if the values differ, indeterminate current split if equal). Real series resistance fixes it.
- [0:11:16] *Is Ampère's law like a magnetic version of Gauss's law?* "Very close. It's actually the cross product, the curl of the field, not the divergence." The name is Ampère's law, and he uses the integral form. Someone also mentioned Lenz's law, which he said relates the *field* to the emf and comes next.
- [0:25:27] *Is $S'$ the area enclosed by $C'$?* Yes: $S'=N\times S$, the core cross-section counted once per turn.
- [1:14:38] *Why is the 4 kΩ current zero after switching?* The source/4 kΩ branch is left open at terminal ①, so no closed path exists. You must see this from the topology; it can't be solved for, since the floating node's voltage is unknown.
- [1:19:14] *What are RL circuits used for?* Resonant circuits and filters. Inductors are hard to make, so they're used only when needed.
- [1:19:59] *Is continuity a modeling assumption or real?* Real for $v_C$ and $i_L$ (otherwise infinite current or voltage spikes). Other quantities are idealized as jumping but really change fast at a finite rate.

## Exam relevance

- **P1 (conceptual "explain why"):**
  - **L/C at DC steady state:** "$v=L\,di/dt$ and $di/dt=0$, so $v=0$ and L acts as a short; $i=C\,dv/dt$ and $dv/dt=0$, so $i=0$ and C acts as an open." This is key point #1 verbatim.
  - **Continuity of $v_C$ and $i_L$:** use his $dI/dt$-undefined argument plus the physical "spike" argument. Contrast with non-state variables that may jump ($v_1$, $i_3$, $v_L$).
  - **Why a 1st-order circuit can't be underdamped** (not argued in this lecture; built from its pieces): a circuit governed by one first-order ODE $\dot x+x/\tau=0$ has characteristic equation $s+1/\tau=0$. That has a single **real** root $s=-1/\tau$, so the response is a pure exponential $Ae^{-t/\tau}$ and can never oscillate. Oscillation needs a complex-conjugate pair of roots, which needs a 2nd-order characteristic polynomial, i.e. two independent energy-storage elements that exchange energy (L↔C). Mind the warning: two decoupled RL branches give a sum of real exponentials, still with no oscillation.
  - Possible items: how to increase $L$ (more turns, $N^2$; higher $\mu$; larger $S$; shorter $\ell$) and why inductors are hard to integrate.
- **P2 (phasor ladder):** no phasors yet. The reusable skill is the ladder reduction in the RL $t<0$ step ($6\text{k}\|12\text{k}=4\text{k}$, then a voltage divider).
- **P3 (two-op-amp impedance synthesizer):** op amps were planned but not reached. Nothing here.
- **P4 (2nd-order RLC transient):** this lecture is the template.
  1. DC steady state for $t<0$ (L short, C open), giving $i_L(0^-)$ and $v_C(0^-)$.
  2. Continuity, so $i_L(0^+)=i_L(0^-)$ and $v_C(0^+)=v_C(0^-)$.
  3. Re-draw the $t\ge0$ topology and recompute the jumpable quantities from KVL/KCL. In the RL example, $v_L(0^+)=-24$ V and so $di_L/dt(0^+)=v_L(0^+)/L$. This is the second IC that a 2nd-order ODE needs.
  4. KCL/KVL gives the ODE; solve, apply the ICs, and check the $t\to\infty$ value.
  - Write each of these with a stated justification. Per 8/24, that is where most of the points are.
