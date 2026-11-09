---
course: ECE 411H
date: 2026-09-09
instructor: Prof. Ed Yu
topic: Series RLC step response. Initial and final conditions (including the derivative IC), derivation of the 2nd-order ODE for v_C, the characteristic equation, resonant frequency ω0, damping factor α (Np/s), the three damping regimes, a fully worked overdamped example, and the derivation of the critically damped t·e^{st} solution
reading: Ulaby/Maharbiz/Furse 3e §6-2 through §6-6
source: Recordings/2026-09-09 (transcript + 57 listed tablet frames, plus neighbours f_0224 and f_0374)
tags: [ece411, lecture, rlc, second-order, transient, damping, overdamped, critically-damped, initial-conditions, exam1, P1, P4]
---

# 2026-09-09: Series RLC Step Response, Damping, Overdamped & Critically Damped

## Summary

- **Circuit:** a step source $v_s(t)=V_s\,u(t)$ drives a single series loop of $R$, $L$ and $C$. The goal is $v_C(t)$ for $t\ge 0$. He follows a fixed procedure: **0) initial and final conditions → 1) differential equation for one unknown → 2) solve (homogeneous + particular) → apply the two ICs.**
- **Initial conditions come from continuity.** $v_C$ is continuous, so $v_C(0)=v_C(0^-)=0$. $i_L$ is continuous and $i_C=i_L$ in a series loop, so $i_C(0)=0$. **Then $i_C=C\,dv_C/dt$ gives the derivative IC $dv_C/dt|_{0}=0$.** Final conditions ($C$ open, $L$ short): $v_C(\infty)=V_s$, $i_C(\infty)=0$. These serve "mostly as a check."
- **The ODE comes from KVL plus the capacitor law:** $Ri_C+L\,di_C/dt+v_C=V_s$ with $i_C=C\,dv_C/dt$, which gives $\dfrac{d^2v_C}{dt^2}+\dfrac{R}{L}\dfrac{dv_C}{dt}+\dfrac{1}{LC}v_C=\dfrac{V_s}{LC}$. "Usually the hardest part of the problem is getting to a differential equation with only one unknown function."
- **Solving it:** take the homogeneous equation (*), try $Ae^{st}$, and get the characteristic equation (**) $s^2+as+b=0$ with roots $s_{1,2}=-\frac a2\pm\sqrt{(a/2)^2-b}$. The particular integral for a constant forcing term is a constant ($v_C=V_s$). Full solution = homogeneous + particular.
- **Definitions:** $\omega_0=1/\sqrt{LC}$ is the **resonant frequency** in rad/s. $\alpha=R/2L$ is the **damping factor** in **nepers/s** (Np = a unit of natural-log ratio, "like dB but for natural logs"). In this notation $s_{1,2}=-\alpha\pm\sqrt{\alpha^2-\omega_0^2}$.
- **There are three regimes, set by whether $\sqrt{\alpha^2-\omega_0^2}$ is real-nonzero, zero, or imaginary:** overdamped when $\alpha>\omega_0$ ($R>2\sqrt{L/C}$), critically damped when $\alpha=\omega_0$ ($R=2\sqrt{L/C}$), and oscillatory/underdamped when $\alpha<\omega_0$ (only described qualitatively today). With $R=0$ the circuit oscillates forever at $\omega_0$ as energy moves back and forth between $L$ and $C$.
- **Worked overdamped example:** $V_s=24$ V, $R=64\ \Omega$, $L=0.8$ H, $C=2$ mF. Then $\alpha=40$ Np/s, $\omega_0=25$ rad/s, $\sqrt{\alpha^2-\omega_0^2}\approx31.2$, and **$v_C(t)=-27.38e^{-8.8t}+3.38e^{-71.2t}+24$ V**. $A_1$ and $A_2$ come from Cramer's rule. The slow pole sets a time scale of $\approx 1/8.8$ s.
- **Critically damped case:** $s_1=s_2=-\alpha$ leaves only one independent exponential, which cannot satisfy two ICs. He derives the second solution $te^{s_1t}$ as $\lim_{s_2\to s_1}\frac{e^{s_2t}-e^{s_1t}}{s_2-s_1}=\frac{d}{ds}e^{st}\big|_{s_1}$. Full solution: $v_C=A_1e^{s_1t}+A_2te^{s_1t}+V_s$. A numerical example is promised for next lecture.

---

## Content

### 0. Announcements [0:00:02–0:02:16] (f_0004, f_0007)
1. PS1 was due at 9:00 AM today on Canvas. PS2 is due at 9:00 AM Mon Sep 14.
2. PS3 was released this morning and is due at 9:00 AM Mon Sep 21. "The third problem set is pretty long, so you should make sure to get an early start on it."
3. No class or regular office hours on Wed Sep 16. A recorded lecture will be posted; watch it before Mon Sep 21.
4. Barring travel mishaps, there are extra office hours **Wed Sep 16, 4:30–6:00 PM, EER 3.802**.
5. No class or office hours on Wed Sep 23 either. A recording will be posted; watch it before Mon Sep 28.

### 1. Recap and plan [0:02:29–0:03:18]
- Last class started second-order (RLC) circuits and worked an example of finding initial conditions.
- Today: "the details of how we actually solve RLC circuits and the different kinds of behavior that we can get." He starts with a simple configuration and builds toward others.
- **Reading: Ulaby et al. §6-2 through §6-6** [0:03:28] (f_0011).

### 2. The circuit [0:03:48–0:05:57] (f_0011)

**Topology:** one loop. The independent voltage source $v_s(t)$ is on the left edge with + at the top. Going clockwise along the top wire you meet the **resistor $R$**, then the **inductor $L$**. The **capacitor $C$** is on the right edge, and the bottom wire returns to the source.

**Reference directions:**
- $v_C$ is + at the top of $C$ and − at the bottom.
- $i_C$ is drawn on the top wire between $L$ and $C$, pointing right, so it flows clockwise and enters the + terminal of $C$ (passive sign convention).
- "We'll label it as the current through the capacitor. But … that current is actually the same in all the components."

**Source:** $v_s(t)=V_s\,u(t)$, with $V_s$ constant and
$$u(t)=\begin{cases}0 & t<0\\ 1 & t\ge 0\end{cases}$$
No physical switch is drawn; the step function plays the role of the switch.

**Task:** solve for $v_C(t)$ for $t\ge0$.

### 3. Step 0: initial and final conditions [0:06:01–0:11:40] (f_0026, f_0031, f_0035)

He calls this "kind of the zeroth order preliminary step."

**$t<0$ (steady state, source off "since $t=-\infty$"):** there are no sources, so every voltage and current is zero ($L$ acts as a short and $C$ as an open).
$$v_C(t)=0,\ i_C(t)=0\ \Rightarrow\ v_C(0^-)=0,\ i_C(0^-)=0$$

**$t=0$ (the actual ICs):**
- **$v_C$ is continuous** $\Rightarrow v_C(0)=0$.
- **$i_L$ is continuous** $\Rightarrow i_C(0)=i_L(0)=0$, because the circuit is a series loop and $i_C(0^-)=0$.
- **Derivative IC:** "Since $i_C=C\dfrac{dv_C}{dt}$, we must also have $\dfrac{dv_C}{dt}\Big|_{t=0}=0$." [0:08:36–0:09:53]

He explains why both are needed: "in coming up with a complete solution, we will need to apply two initial conditions … one of those will be on $v_C$ at $t=0$. The other one will be on the derivative of $v_C$ … at $t=0$." [0:08:36]

**$t\to\infty$ (final conditions; "mostly a check on the solution"):** the source is on at $V_s$, $C$ behaves as an open circuit and $L$ as a short.
$$v_C(t\to\infty)=V_s,\qquad i_C(t\to\infty)=0$$

> [!tip] Derivative-IC recipe (generalising his move)
> Write the element law for the variable whose derivative you need, then evaluate it at $0^+$ using the continuous quantities:
> - $\dfrac{dv_C}{dt}(0^+)=\dfrac{i_C(0^+)}{C}$
> - $\dfrac{di_L}{dt}(0^+)=\dfrac{v_L(0^+)}{L}$
>
> Here $i_C(0^+)=i_L(0^+)=0$, so the slope is 0. If the inductor had carried current before $t=0$, the slope would be $i_L(0^-)/C$, not zero.

### 4. Step 1: the differential equation for $v_C$, $t\ge0$ [0:11:46–0:18:07] (f_0035, f_0041, f_0048, f_0113)

**The general method:** "apply our standard tools of circuit analysis, but now using for the inductor and the capacitor the differential relationships between current and voltage rather than, or in addition to, … Ohm's law."

He asks which law to use; a student answers KVL. Going around the loop:
$$\text{KVL:}\quad Ri_C+L\frac{di_C}{dt}+v_C=V_s\qquad(1)$$

**Problem:** (1) has two unknowns, $v_C$ and $i_C$, in one equation, so it cannot be solved yet. "What we need is some other relationship." A student supplies it:
$$i_C=C\frac{dv_C}{dt}\qquad(2)$$

**Substitution.** Put (2) into (1). The $L\,di_C/dt$ term becomes a second derivative:
$$RC\frac{dv_C}{dt}+LC\frac{d^2v_C}{dt^2}+v_C=V_s$$

**Normalise.** Divide by $LC$ so the highest derivative has coefficient 1, then order the terms by derivative:
$$\boxed{\frac{d^2v_C}{dt^2}+\frac{R}{L}\frac{dv_C}{dt}+\frac{1}{LC}v_C=\frac{1}{LC}V_s}\quad\text{(2nd-order diff. eqn. for }v_C(t))$$

The equation is second order because of the $di_C/dt$ term: substituting (2) produces $d^2v_C/dt^2$.

> [!important] His stated principle [0:15:22]
> "In general, when you're looking at more complicated circuit configurations, usually the hardest part of the problem is … getting to a differential equation with only one unknown function. And doing that is sort of a matter of using the basic circuit laws … and then figuring out what other relationships we have between currents and voltages."

### 5. Step 2: solving the ODE as a math problem [0:18:07–0:31:06] (f_0048, f_0060, f_0062, f_0078, f_0084, f_0095, f_0097, f_0113–f_0141)

**Generic form** (f_0048):
$$\frac{d^2v_C}{dt^2}+a\frac{dv_C}{dt}+bv_C=c,\qquad a,b,c\ \text{constants}$$
For the series RLC, $a=R/L$, $b=1/LC$ and $c=V_s/LC$ (lowercase $c$, not the capacitance). He asks who has seen this in a math course; "a couple" of students raise hands.

**First consider the homogeneous equation ($c=0$):**
$$\frac{d^2v_C}{dt^2}+a\frac{dv_C}{dt}+bv_C=0\qquad(*)$$

**Why try an exponential** [0:21:34]: the three terms are different derivatives of $v_C$, and they must sum to zero for all $t$ with constant coefficients. So $v_C$, $v_C'$ and $v_C''$ should have the same functional form; otherwise "it would be a miracle if this equation were always satisfied." The exponential is the function whose derivative has the same form as itself. "Since $\frac{d}{dt}e^{st}\propto e^{st}$, consider a trial solution $v_C(t)=Ae^{st}$ to (*)." He calls a trial solution "a fancy word for guess … but here it's a pretty informed guess."

**Substitute.** Each $d/dt$ brings down a factor of $s$:
$$s^2Ae^{st}+asAe^{st}+bAe^{st}=0$$
On the board, the $Ae^{st}$ factors are crossed out in red. Cancelling is legal because "the exponential function is never equal to zero," and $A=0$ is the trivial solution $v_C=0$. This leaves
$$s^2+as+b=0\qquad(**)$$
**(**) is called the characteristic equation of the differential equation (*).**

**Solving for $s$** with the quadratic formula:
$$s=\frac{-a\pm\sqrt{a^2-4b}}{2}=-\frac a2\pm\sqrt{\left(\frac a2\right)^2-b}$$
$$\boxed{s_1=-\frac a2+\sqrt{\left(\frac a2\right)^2-b},\qquad s_2=-\frac a2-\sqrt{\left(\frac a2\right)^2-b}}$$

**General solution to (*)** (f_0122):
$$\boxed{v_C(t)=A_1e^{s_1t}+A_2e^{s_2t},\quad A_1,A_2=\text{constants}}\quad\text{(solution to homogeneous equation)}$$
Two roots give two distinct solutions, and "the general solution … will be any linear combination of those two solutions."

**For the series RLC circuit, $a=R/L$ and $b=1/LC$** (f_0136).

**Student question at [0:31:20]:** what if $b>(a/2)^2$? His answer:
- $s_1$ and $s_2$ become complex, but they are "still valid solutions."
- "If $s_1$ and $s_2$ are real, they'll always be negative," which gives exponentially decaying voltage.
- If they are complex, "you will have oscillatory components … because $e$ to some imaginary number is … cosine plus $j$ times the sine."
- Which case you get depends on "$R/2L$ versus $1/LC$" (more precisely, $(R/2L)^2$ vs $1/LC$).
- There is also "the special case where $s_1=s_2$," which needs an additional solution.

### 6. Special case $R=0$: LC circuit and the resonant frequency [0:33:04–0:37:32] (f_0154, f_0162, f_0174, f_0180, f_0193, f_0195)

Setting $R=0$ gives $a=0$, so
$$s_1=\sqrt{-b},\qquad s_2=-\sqrt{-b}$$
Since $b=1/LC>0$, **$s_1$ and $s_2$ are imaginary, and the solution $v_C(t)$ is oscillatory** ("a sum of sines and cosines"). Because $\sqrt{-1/LC}=j\sqrt{1/LC}$, the angular frequency is
$$\boxed{\omega_0=\sqrt{\frac{1}{LC}}\equiv\textbf{resonant frequency}\quad[\text{radians/sec}\equiv\text{rad/s}]}$$

**Interpretation** [0:36:22]: with only a source, an $L$ and a $C$, "the voltage across the capacitor will just oscillate. It'll oscillate forever. And that corresponds to … energy in the circuit alternating between being stored in the capacitor and the inductor. And if there's no resistor, then there's nothing that can dissipate power."

### 7. $R\neq0$: the damping factor and the neper [0:37:32–0:43:41] (f_0207, f_0212, f_0214, f_0217, f_0220)

A student asks something at [0:37:48] (inaudible; probably about the constant term on the right-hand side (?)). His reply: "Yes, we'll get to that," after first sorting out the exponent.

With $R\ne0$, $a\ne0$. The $-a/2$ term makes the real part of the exponent negative, so the response decays ("exponentially damped"). He defines:
$$\boxed{\alpha\equiv\textbf{damping factor}=\frac{R}{2L}\quad[\text{Nepers/sec}=\text{Npr/s}]}$$
The factor 2 is there "because in our solution we have $a/2$, not $a$." So $\alpha=a/2$ and $\omega_0^2=b$.

**What a neper is** (f_0212): "a unit for differences on a natural logarithmic scale, or equivalently for multiplicative factors of $e$ on a linear scale." At $\alpha=1$ Np/s, "every second … the voltage will decrease by a factor of $e$." A student asks whether this is similar to decibels: "Yes … decibels are for common logs … this is for natural logs. But the idea is the same." [0:41:44]

**$\alpha\ne0\Rightarrow$ exponential decay of transient voltages and currents** (f_0214). A student asks what "transient" means [0:43:26]: "a behavior that will die out with time … exponentially decaying with time."

**Homogeneous solution rewritten in $\alpha,\omega_0$** (f_0217, f_0220):
$$v_C(t)=A_1e^{-\alpha t}e^{\sqrt{\alpha^2-\omega_0^2}\,t}+A_2e^{-\alpha t}e^{-\sqrt{\alpha^2-\omega_0^2}\,t}$$
Equivalently, $s_{1,2}=-\alpha\pm\sqrt{\alpha^2-\omega_0^2}$.

### 8. Particular integral and the full solution [0:43:47–0:49:24] (f_0224, f_0231, f_0240)

"Now consider the particular integral for the full differential equation":
$$\frac{d^2v_C}{dt^2}+\frac{R}{L}\frac{dv_C}{dt}+\frac{1}{LC}v_C=\frac{V_s}{LC}$$
> [!warning] Board glyph on f_0224/f_0231 (9/9, ≈0:45–0:48): the coefficient under $R$ in the particular-integral line looks like a **2** (compare his $L$ in $LC$ on the same line), but he says "R over L" and the earlier line on the same page has $R/L$. Whether it's a slip or a cursive L, the correct coefficient is **$R/L$**. Never copy it as $R/2$.

**Definition:** a particular integral is "just any solution … not the most general solution, just any solution that we can come up with by hook or by crook." **General solution of the full equation = particular integral + general homogeneous solution.**

**Finding it:** guess a function whose derivatives are all zero, i.e. a constant. Since the right-hand side is constant, **$v_C(t)=V_s$** is a solution (f_0231). "If this were some time-dependent function, it would be more complicated."

**Full solution for $v_C(t)$ for the series RLC circuit** (f_0240):
$$\boxed{v_C(t)=A_1e^{-\alpha t}e^{\sqrt{\alpha^2-\omega_0^2}\,t}+A_2e^{-\alpha t}e^{-\sqrt{\alpha^2-\omega_0^2}\,t}+V_s}$$

**Student question at [0:49:40]:** "We're told … a second-order differential equation has precisely two solutions. This seems like it has three?" His answer:
- The "two solutions" are the two undetermined constants $A_1$ and $A_2$: "a two-dimensional space … two independent basis vectors."
- The $V_s$ term stays.
- "For any particular circuit there will be … initial conditions … $v_C$ … and $dv_C/dt$ at $t=0$. Those two initial conditions will then allow us to determine $A_1$ and $A_2$."

### 9. Three distinct behaviours [0:49:28–0:53:41] (f_0250)

"There are three distinct behaviors that can occur, corresponding to $\sqrt{\alpha^2-\omega_0^2}$ = **real nonzero, zero, or imaginary**." Which one you get "just depends on the specific values of $R$, $L$ and $C$."

| Case | Condition | $\sqrt{\alpha^2-\omega_0^2}$ | Behaviour (his words) |
|---|---|---|---|
| (i) **Overdamped** | $\alpha>\omega_0$, $R>2\sqrt{L/C}$ | real | "both … terms will just be exponentially decaying" |
| (ii) **Critically damped** | $\alpha=\omega_0$, $R=2\sqrt{L/C}$ | 0 | "the form of the solution … is actually a little bit different" |
| (iii) Underdamped (name not yet used; he says "oscillatory") | $\omega_0>\alpha$, $R<2\sqrt{L/C}$ | imaginary | "exponentially decaying times oscillating behavior" |

The ASR says "R is greater than two over the square root of L over C." The board (f_0255) is authoritative: $R>2\sqrt{L/C}$. Check: $\alpha>\omega_0\iff \frac{R}{2L}>\frac{1}{\sqrt{LC}}\iff R>2\sqrt{L/C}$.

### 10. (i) Overdamped response [0:53:41–0:56:04] (f_0255)

$$v_C(t)=\underbrace{A_1e^{-\alpha t}e^{\sqrt{\alpha^2-\omega_0^2}\,t}+A_2e^{-\alpha t}e^{-\sqrt{\alpha^2-\omega_0^2}\,t}}_{\text{decaying exponential functions}}+V_s$$

Both exponents are negative because $\sqrt{\alpha^2-\omega_0^2}<\alpha$. Physical reasoning [0:55:30]: "if you have a large value of the resistance, then the resistor is what dissipates power. So the energy in the circuit is going to be dissipated more rapidly and you just get exponential decay."

### 11. Worked example: overdamped series RLC [0:56:04–1:07:25] (f_0284, f_0286, f_0287, f_0289, f_0293, f_0296, f_0303, f_0307)

**Given** (same circuit as §2, zero initial state, step at $t=0$): $V_s=24$ V, $R=64\ \Omega$, $L=0.8$ H, $C=2$ mF.

**Parameters:**
$$\alpha=\frac{R}{2L}=\frac{64}{1.6}=40\ \text{Np/s}$$
$$\omega_0=\frac{1}{\sqrt{LC}}=\frac{1}{\sqrt{(8\times10^{-1})(2\times10^{-3})}}=\frac{1}{\sqrt{16\times10^{-4}}}=\frac{1}{0.04}=25\ \text{rad/s}$$
So $\alpha>\omega_0$ ✓, and the circuit is overdamped.

He addresses the units: "what are you doing comparing quantities that have different units? … the relevant units here are actually inverse seconds. Nepers is just something that we have in there to remind ourselves that this is a log scale, and radians are the natural unit for angular quantities." [0:57:57]

$$\sqrt{\alpha^2-\omega_0^2}=\sqrt{40^2-25^2}\approx31.2\ \text{Np/s}$$
$$s_1=-40+31.2=-8.8,\qquad s_2=-40-31.2=-71.2\ \ (\text{s}^{-1})$$
$$\Rightarrow v_C(t)=A_1e^{-8.8t}+A_2e^{-71.2t}+24\ \text{V}$$

**Apply the ICs** ("To determine $A_1$ and $A_2$, recall initial conditions at $t=0$"):
- $v_C(0)=0\ \Rightarrow\ A_1+A_2+24=0$
- $\dfrac{dv_C}{dt}\Big|_{t=0}=0\ \Rightarrow\ -8.8A_1-71.2A_2=0$. Differentiate term by term: the constant vanishes, each exponential brings down its $s$, and $e^0=1$.

**Matrix form:**
$$\begin{pmatrix}1&1\\-8.8&-71.2\end{pmatrix}\begin{pmatrix}A_1\\A_2\end{pmatrix}=\begin{pmatrix}-24\\0\end{pmatrix}$$

**Cramer's rule** ("what I think is an easy way to do it"; the ASR renders "determinant" as "derivative"). Replace the column for the unknown with the RHS, take the determinant, and divide by the coefficient determinant $(1)(-71.2)-(1)(-8.8)=-71.2+8.8=-62.4$:
$$A_1=\frac{(-24)(-71.2)}{-71.2+8.8}=-27.38\ \text{V},\qquad A_2=\frac{-(-24)(-8.8)}{-71.2+8.8}=3.38\ \text{V}$$

**Result** (boxed, f_0303):
$$\boxed{v_C(t)=(-27.38)e^{-8.8t}+(3.38)e^{-71.2t}+24\ \text{V}\quad\text{for }R=64\ \Omega,\ L=0.8\ \text{H},\ C=2\ \text{mF},\ V_s=24\ \text{V}}$$

**Sketch** (f_0307): $v_C$ starts at 0 with zero slope, rises in an S-shape, and approaches 24 V asymptotically (dashed line at 24 V). A tick on the $t$-axis is marked $\approx(1/8.8)$ s. "The exponential time constant … is mostly going to be determined by this first term." The slow root dominates.

> [!check] Verification (python3 + ngspice transient on the same netlist)
> - Exact values: $\sqrt{975}=31.225$, $s_1=-8.775$, $s_2=-71.225$, $R_{crit}=2\sqrt{L/C}=40\ \Omega$ (so 64 Ω is well into the overdamped region).
> - Exact constants: $A_1=-V_s s_2/(s_2-s_1)=-27.37$ V and $A_2=V_s s_1/(s_2-s_1)=3.37$ V. The board's $-27.38$ and $3.38$ come from solving with the rounded 8.8 and 71.2 (gives $-27.385$, $3.385$). This is rounding, not an error.
> - ICs check: $A_1+A_2=-24$ ✓ and $-8.8A_1-71.2A_2\approx0$ ✓.
> - ngspice `v(C)` at 0.05/0.1/0.2/0.5 s = 6.445 / 12.621 / 19.267 / 23.660 V. This matches the analytic formula to 4 significant figures.
> - At the marked tick $t=1/8.8\approx0.114$ s, $v_C\approx13.9$ V (58% of final, not 63%, because of the fast term and the zero initial slope).
> - Current: $i_C=C\,dv_C/dt=\dfrac{V_s}{L(s_1-s_2)}\left(e^{s_1t}-e^{s_2t}\right)=0.480\,(e^{-8.775t}-e^{-71.225t})$ A. It peaks at 0.314 A at $t=33.5$ ms, which is the inflection point of the S-curve.
> - Physical check: $v_L(0^+)=V_s-Ri(0)-v_C(0)=24$ V, so $di/dt(0^+)=24/0.8=30$ A/s. The whole source step appears across $L$ at $t=0^+$.

**Question at [1:03:58], on solving the 2×2 with a calculator:** "You can, but then you have to make sure that you plug in the numbers correctly, because **we can only give you credit for the work that you show**. So if you say, 'now I'm solving this on my calculator,' and you get the right answer, that's fine. If you get the wrong answer, we can only give you credit for getting the equations."

### 12. (ii) Critically damped response [1:07:30–1:18:32] (f_0324, f_0332, f_0338, f_0351, f_0358, f_0363, f_0367–f_0371, f_0374, f_0381, f_0383)

**Condition:** $\alpha=\omega_0$, i.e. $\sqrt{\alpha^2-\omega_0^2}=0$, or $R=2\sqrt{L/C}$ (f_0324).

**The problem** (f_0332): $s_1=s_2$, so "our exponential solution for $v_C(t)$ now has only **one** independent function, $A_1e^{-\alpha t}$, so we need to find a second independent solution to (*)."

**Derivation (his "limit trick"):**
1. Recall (*) $v_C''+av_C'+bv_C=0$ with general solution $A_1e^{s_1t}+A_2e^{s_2t}$ and $s_{1,2}=-\frac a2\pm\sqrt{(a/2)^2-b}$ (f_0338, f_0351).
2. "Suppose first that $s_1\ne s_2$, and the independent solutions to (*) are $e^{s_1t}$ and $e^{s_2t}$." Any linear combination is also a solution, so "another possible solution is"
$$\frac{e^{s_2t}-e^{s_1t}}{s_2-s_1},\quad\text{i.e. } A_1=\frac{-1}{s_2-s_1},\ A_2=\frac{1}{s_2-s_1}$$
(f_0358)
3. "As $s_2\to s_1$, this solution becomes" $\displaystyle\lim_{s_2\to s_1}\frac{e^{s_2t}-e^{s_1t}}{s_2-s_1}$. Let $s_2=s_1+\Delta s$:
$$=\lim_{\Delta s\to0}\frac{e^{(s_1+\Delta s)t}-e^{s_1t}}{\Delta s}$$
(f_0371)
4. He asks the class what this limit is; a student answers that it is the definition of a derivative:
$$=\frac{d}{ds}e^{st}\Big|_{s=s_1}=te^{s_1t},\qquad\text{with } s_1=-\frac a2\ (=-\alpha)$$
(f_0374)
5. "**Thus our second independent solution to (*) is $te^{s_1t}$**" (f_0383). It is independent of $e^{s_1t}$, and "from the way that we arrived at it, or you can verify it yourself," it solves (*).

**Full critically damped solution** [1:17:53]. This is spoken only; the last frame (1:17:39) predates it (?):
$$v_C(t)=A_1e^{s_1t}+A_2\,t\,e^{s_1t}+V_s,\qquad s_1=-\alpha$$

**Student question at [1:13:15]:** why is the second solution necessary? "If we only had that one independent solution, we would only have one unknown constant … but there would still be two initial conditions … one on $v_C$ and one on $dv_C/dt$ … it would be like having one variable and two different equations … in general, there's no solution to that."

"I think this is a better, at least more satisfying, way to arrive at it than … your professor telling you this is the second solution … now you have this little trick that you could use perhaps in other circumstances as well." [1:17:36]

**Next lecture:** "a specific numerical example that ends up having this critically damped response." [1:18:39]

> [!example] Not from lecture: the same circuit at the critical resistance, for practice
> $R=40\ \Omega$ ($=2\sqrt{0.8/0.002}$), $L=0.8$ H, $C=2$ mF, $V_s=24$ V gives $\alpha=\omega_0=25$ and $s_1=-25$.
> - $v_C(0)=0\Rightarrow A_1=-24$.
> - $v_C'(0)=s_1A_1+A_2=0\Rightarrow A_2=-s_1A_1=-600$ V/s.
>
> $$v_C(t)=24-24e^{-25t}-600\,t\,e^{-25t}\ \text{V}$$
> Note that $A_2$ has units of V/s, not V. This is a common unit-check point.

> [!example] Not from lecture: an underdamped preview ($R=16\ \Omega$, same $L$, $C$, $V_s$)
> $\alpha=10$, $\omega_0=25$, and $\omega_d\equiv\sqrt{\omega_0^2-\alpha^2}=22.91$ rad/s (the textbook's symbol; **Yu has not introduced $\omega_d$ yet**).
>
> $$v_C=24+e^{-10t}(-24\cos22.91t-10.47\sin22.91t)\ \text{V}$$
> It overshoots to a peak of 30.09 V at $t=\pi/\omega_d=0.137$ s.

---

## Ed Yu's conventions & notation

- **Procedure labels (on the board):** "**0) initial + final conditions**" → "**1) differential equation for $v_C(t)$, $t\ge0$**" → "**2) solve the differential equation**". Step 2 runs: homogeneous eq. **(*)** → trial solution $Ae^{st}$ → characteristic eq. **(**)** → roots $s_1,s_2$ → general homogeneous solution → **particular integral** → full solution → apply ICs for $A_1$, $A_2$. Write in this order on the exam.
- **IC bookkeeping:** he writes three lines, "$t<0$:", "$t=0$:" and "$t\to\infty$:". He goes from $0^-$ to $0$ by continuity, writes "$v_C$ continuous ⇒", "$i_L$ continuous ⇒", and then "Since $i_C=C\,dv_C/dt$, we must also have $dv_C/dt|_{t=0}=0$." He writes $v_C(0)$, not $v_C(0^+)$, for the post-switch IC.
- **Reference directions:** passive sign convention. $i_C$ (labelled at the capacitor, though it is the loop current) enters the + terminal of $v_C$. Source + on top. KVL written as $\sum$ drops $=V_s$.
- **ODE normal form:** divide so the coefficient of the highest derivative is 1, and order the terms from the highest derivative down. Generic coefficients are lowercase $a,b,c$ (lowercase $c$ is not the capacitance).
- **Symbols and units:**
  - $\alpha\equiv$ "damping factor" $=R/2L$ (series RLC), in **Np/s** (he writes "Npr/s").
  - $\omega_0\equiv$ "resonant frequency" $=1/\sqrt{LC}$, in **rad/s**.
  - $\sqrt{\alpha^2-\omega_0^2}$ is also given in Np/s when real (31.2 Np/s).
  - Constants are $A_1$ and $A_2$; units of V for exponential terms, V/s for the $te^{st}$ coefficient.
- **Solution forms used so far:**
  - Overdamped: $A_1e^{-\alpha t}e^{+\sqrt{\alpha^2-\omega_0^2}t}+A_2e^{-\alpha t}e^{-\sqrt{\alpha^2-\omega_0^2}t}+V_s$. He keeps $e^{-\alpha t}$ factored out, then collapses to numeric exponents $e^{-8.8t}$, $e^{-71.2t}$.
  - Critically damped: $A_1e^{s_1t}+A_2te^{s_1t}+V_s$ with $s_1=-a/2=-\alpha$.
  - Underdamped: not yet written. $\omega_d$ is **not defined in this lecture**.
- **Root ordering:** $s_1$ takes the "+√" (slower, less negative) root and $s_2$ the "−√" root.
- **Damping criteria are stated three equivalent ways:** $\alpha$ vs $\omega_0$; $\sqrt{\alpha^2-\omega_0^2}$ real/zero/imaginary; $R$ vs $2\sqrt{L/C}$.
- **Linear solve:** matrix form, then **Cramer's rule**. A calculator is OK, but only shown work earns credit.
- **Time scale:** he quotes the dominant (slow) root, $\approx1/|s_1|$, as "the exponential time constant."

## Intuition & explanations he gives

- **Continuity (P1 gold):** "we know that $v_C$, the voltage across the capacitor, has to be continuous … We also know that the current through the inductor has to be continuous." [0:07:38–0:08:06] The derivative IC is then forced by $i_C=C\,dv_C/dt$: zero capacitor current at $t=0$ means zero slope of $v_C$. [0:08:59–0:09:53]
- **DC steady state:** "The inductor is behaving as a short circuit, the capacitor as an open circuit." At $t\to\infty$, "$i_C$ … has to be zero because the capacitor is an open circuit, and $v_C$ has to be equal to $V_s$." [0:06:45, 0:10:52–0:11:19]
- **Final conditions are a check:** "this will sort of be mostly a check on the solution that we get." [0:10:11]
- **Why one ODE with one unknown:** KVL alone gives "two unknowns in one equation. So we're not able to solve for these unknown functions. What we need is some other relationship." [0:14:06–0:14:33]
- **Why second order:** "It'll be second order because we have a $di_C/dt$ term … and when we take this derivative … of [$C\,dv_C/dt$], we're going to get a second derivative of $v_C$." [0:15:10]
- **Why exponentials:** the terms are different-order derivatives that must cancel with constant coefficients, so "$v_C$ and its first and second derivative should have very similar mathematical form, because if you had different functional forms … it would be a miracle if this equation were always satisfied." [0:21:51–0:22:13]
- **Cancelling $Ae^{st}$ is legal** "because we know the exponential function is never equal to zero," and $A=0$ is "a trivial solution." [0:25:28–0:25:36]
- **Real roots are always negative** (decay); complex roots give oscillation via $e^{j\theta}=\cos\theta+j\sin\theta$. [0:31:45–0:32:23]
- **Resonance/energy exchange:** with $R=0$, $v_C$ "will oscillate forever … energy in the circuit alternating between being stored in the capacitor and the inductor. And if there's no resistor, then there's nothing that can dissipate power." [0:36:22–0:37:04]
  - *Not from lecture, but it follows directly:* oscillation needs a **quadratic** characteristic equation with complex roots, which needs **two independent energy-storage elements** that can trade energy back and forth. A first-order RC/RL circuit has one storage element, so its characteristic equation is linear with one real negative root, and it cannot be underdamped. This is the standard P1 answer, built on his energy-sloshing explanation.
- **Damping from resistance:** a large $R$ makes the circuit overdamped because "the resistor is what dissipates power. So the energy … is going to be dissipated more rapidly and you just get exponential decay." [0:55:30–0:55:47]
- **Neper:** "a unit for differences on a natural logarithmic scale … or multiplicative factors of $e$ on a linear scale … a damping factor of 1 Np/s means … every second the voltage will decrease by a factor of $e$." "Similar to decibels, except decibels are for common logs." [0:40:19–0:41:53]
- **Units when comparing $\alpha$ and $\omega_0$:** both are really s⁻¹. Np and rad are reminders of a log scale and an angle. [0:57:57–0:58:23]
- **Particular integral:** "just any solution … by hook or by crook." For constant forcing, look for a function whose derivatives are all zero, i.e. a constant. [0:45:08–0:47:24]
- **Why the solution is homogeneous + particular** (from the "three solutions?" question): the two arbitrary constants span a 2-D space, and the ICs pin down a point in it. [0:49:55–0:51:03]
- **Why a second solution is needed in the critical case:** one constant cannot satisfy two ICs ("one variable … two different equations … in general there's no solution"). [1:13:30–1:14:09]
- **$te^{st}$ as a derivative with respect to $s$:** the limit of a difference quotient of two valid solutions is itself a valid solution. "A little trick that you could use perhaps in other circumstances." [1:15:53–1:17:51]
- **Dominant time constant:** "it's mostly going to be determined by this first term … approximately 1/8.8 seconds." [1:07:03–1:07:21]

## Emphasis & exam intel

1. **Show your work; only shown work earns credit.** "We can only give you credit for the work that you show … if you get the wrong answer, we can only give you credit for getting the equations." [1:04:03–1:04:16] For P4, write the IC equations and the $2\times2$ system explicitly before using the calculator.
2. **Getting the single-unknown ODE is the hard part.** "Usually the hardest part of the problem is figuring out … getting to a differential equation with only one unknown function." [0:15:22] He repeats the idea at [0:11:51] ("come up with a differential equation that we can solve for a single unknown") and [0:16:00].
3. **Two ICs, one of them a derivative.** "We will need to apply two initial conditions … one … on $v_C$ at $t=0$. The other … on the derivative of $v_C$ … at $t=0$." [0:08:36] He derives it from $i_C=C\,dv_C/dt$ and asks "Any questions on those and how we got to them?" [0:09:59]. He returns to both ICs to find $A_1$ and $A_2$ [1:00:13] and again in the critical-case question [1:13:43].
4. **Initial and final conditions are step zero.** "The zeroth order preliminary step that we need to go through is to determine what the initial and final conditions are." [0:06:01] Final conditions are "mostly a check on the solution." [0:10:11] He closes the example by checking that the plot goes to 24 V, "which is what we had figured out earlier was the final condition." [1:06:39–1:06:52]
5. **Continuity of $v_C$ and $i_L$** is invoked as the justification each time, never assumed silently. [0:07:38, 0:08:06]
6. **The three regimes and their criteria** come in three equivalent forms ($\alpha$ vs $\omega_0$, discriminant real/zero/imaginary, $R$ vs $2\sqrt{L/C}$). "Which one of these we get basically just depends on the specific values of R, L and C." [0:53:25] He verifies with a ✓ that $\alpha>\omega_0$ before choosing the solution form [0:57:49].
7. **Units:** α in Np/s and ω0 in rad/s, both really s⁻¹. He explicitly heads off the "different units" objection. [0:57:57]
8. **Cramer's rule is his preferred 2×2 solver** ("what I think is an easy way to do it"), though "you can solve it any way you would like." [1:03:17–1:03:41]
9. **Coming next:** a numerical critically damped example [1:18:39]. The underdamped case has not been formally done yet, so expect it in the following lecture or the recorded ones.
10. PS3 is "pretty long … get an early start." [0:00:34] It likely covers this material, as it is due Sep 21 (?).

## Student questions

| Time | Question (paraphrased) | His answer |
|---|---|---|
| 0:13:05 | (Prompt) Which law gives the ODE for a single loop? | Student: KVL. ✓ |
| 0:14:33 | (Prompt) What second relation links $i_C$ and $v_C$? | Student: $i_C=C\,dv_C/dt$. ✓ |
| 0:20:31 | (Prompt) First step for $v''+av'+bv=c$? | Student (inaudible) → "solve a slightly simpler problem … set the right-hand side equal to zero … the homogeneous equation." |
| 0:31:20 | What if $b>(a/2)^2$? | Complex $s_1,s_2$, still valid; oscillatory components. Real roots are always negative (decay). Special case $s_1=s_2$ needs an extra solution. |
| 0:37:48 | (Inaudible; probably about the RHS constant / $V_s$ (?)) | "Yes, we'll get to that." He handles the exponent first. |
| 0:41:44 | Is the neper like decibels? | Yes. dB uses common logs, Np natural logs; "the idea is the same." |
| 0:43:26 | What does "transient" mean? | Behaviour that dies out with time (exponentially decaying). |
| 0:46:09 | (Prompt) Guess a particular integral? | Student: "…plus a constant." → yes, $v_C=V_s$, since a constant has zero derivatives. |
| 0:49:40 | A 2nd-order ODE has two solutions; this has three? | $A_1$ and $A_2$ span a 2-D solution space. $V_s$ is the particular part and stays. The ICs fix $A_1$ and $A_2$. |
| 1:03:58 | Can we solve the 2×2 on a calculator? | Yes, but only shown work earns credit; a wrong calculator answer earns credit only for the equations. |
| 1:13:15 | Why is a second solution needed when $\alpha=\omega_0$? | One constant cannot satisfy two ICs (one unknown, two equations → no solution in general). |
| 1:15:59 | (Prompt) What does this limit look like? | Student: the definition of the derivative of $e^{st}$ with respect to $s$ at $s_1$. ✓ |

## Exam relevance

**P1 (conceptual "explain why"), directly supplied by this lecture:**
- *Why is $v_C$ continuous / $i_L$ continuous?* He asserts continuity here. The underlying reason ($i_C=C\,dv_C/dt$: a jump in $v_C$ needs infinite current, i.e. infinite power for a step change in stored energy $\tfrac12Cv^2$) is from the earlier lecture; state it in that form.
- *L and C at DC:* $L$ is a short and $C$ is an open in steady state. He uses this for both the $t<0$ and $t\to\infty$ conditions.
- *Why can't a 1st-order circuit be underdamped?* Use his framing: oscillation = energy exchanged between $L$ and $C$ at $\omega_0$, which requires complex roots of a quadratic characteristic equation. A single storage element gives a linear characteristic equation with one real root $-1/\tau$.
- *What does α physically mean / why does large R overdamp?* $R$ dissipates energy. α (Np/s) is the e-folding rate of the envelope.
- *Why does the critically damped case need $te^{st}$?* Two ICs need two independent functions. Be ready to reproduce the limit/derivative argument in 3–4 lines.
- *Why is $dv_C/dt(0)=0$ here?* Because $i_C(0)=i_L(0)=0$ by inductor-current continuity in a series loop.

**P4 (2nd-order RLC transient, historically the lowest-scoring problem).** This lecture is the template. Follow his exact sequence and show each step:
1. $t<0$ steady state ($L$ short, $C$ open) → $v_C(0^-)$, $i_L(0^-)$.
2. Continuity → $v_C(0^+)$, $i_L(0^+)$. **Derivative IC** via $C\,dv_C/dt=i_C(0^+)$ (or $L\,di_L/dt=v_L(0^+)$, found from KVL at $0^+$).
3. $t\to\infty$ → final value (the particular solution for a DC source), kept as a check.
4. KVL/KCL plus element laws → eliminate to one unknown → normalise to $x''+ax'+bx=c$, **with numbers**.
5. Characteristic equation → $\alpha$, $\omega_0$ → classify (state $\alpha$ vs $\omega_0$ explicitly) → pick the form.
6. Apply both ICs → $2\times2$ → Cramer's rule → boxed answer.
7. **Physical check:** $x(0)$, $x'(0)$, $x(\infty)$, sign/shape (no overshoot if overdamped).

**Likely variants and traps (beyond what he covered today):**
- **Critically damped with numbers:** e.g. set $R=2\sqrt{L/C}$. Get $A_1$ from $x(0)$, then $A_2=x'(0)-s_1A_1$ (units V/s). See the practice box in §12.
- **Underdamped:** $\alpha<\omega_0$, $\omega_d=\sqrt{\omega_0^2-\alpha^2}$, form $e^{-\alpha t}(B_1\cos\omega_dt+B_2\sin\omega_dt)+x_\infty$. Not yet derived in class; the next lecture or recordings should cover it.
- **Non-zero initial state:** e.g. a switch opens or closes with $i_L(0^-)\ne0$ or $v_C(0^-)\ne0$. Then $dv_C/dt(0^+)=i_L(0^+)/C\ne0$. Watch the sign relative to the $i_C$ reference arrow.
- **Solving for a different variable** ($i_L$ or $v_L$ instead of $v_C$): differentiate the KVL equation, or use the $v_C$ solution and $i=C\,dv_C/dt$. The characteristic equation (and therefore α and ω0) is the same for every variable in the circuit; only the ICs and particular solution change.
- **Non-canonical topologies:** parallel RLC or series-parallel mixes (e.g. $R$ in parallel with $C$, in series with $L$). **α is not always $R/2L$.** It is whatever $a/2$ comes out of *your* ODE (parallel RLC: $\alpha=1/2RC$). Derive the ODE; do not pattern-match the formula. This is his stated "hardest part."
- **Source turning off** ($V_s[1-u(t)]$) or a DC source with a switch: the particular solution becomes 0 or another constant, and the procedure is identical.

**Not relevant to P2/P3** (phasor ladder, op-amp impedance synthesiser), except that $\omega_0=1/\sqrt{LC}$ reappears as the resonance frequency in phasor problems.

> [!warning] Board/ASR issues found
> - **No substantive board errors.** The overdamped numbers check out exactly (ngspice agrees to 4 significant figures). $A_1=-27.38$ and $A_2=3.38$ use the rounded roots −8.8 and −71.2; with exact roots (−8.775, −71.225) they are −27.37 and 3.37. This is rounding only.
> - In f_0224/f_0231, the $R/L$ coefficient looks like "$R/2$" (slip or cursive L; he says "R over L"). The correct coefficient is $R/L$; do not copy it as $R/2$.
> - ASR errors: "two over the square root of L over C" should be $2\sqrt{L/C}$ (board f_0255); "derivative" in the Cramer's-rule passage should be "determinant"; "solitary"-type mishearings do not occur in this lecture.
> - The critically damped full solution $A_1e^{s_1t}+A_2te^{s_1t}+V_s$ is from audio only. No frame after 1:17:39 exists.
