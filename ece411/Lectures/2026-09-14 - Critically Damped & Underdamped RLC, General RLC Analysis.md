---
course: ECE 411H
date: 2026-09-14
instructor: Prof. Ed Yu
topic: Series RLC critically damped + underdamped step response; analysis of a non-series RLC circuit (Ulaby Ex. 6-10)
reading: Ulaby/Maharbiz/Furse 3e, Secs. 6-7, 6-8; Example 6-10
sources: Recordings/2026-09-14/transcript.txt + frames (100 frames viewed)
tags: [ece411, lecture, rlc, second-order, transient, exam1]
---

# 2026-09-14: Critically damped and underdamped RLC, and analysis of a general RLC circuit

## Summary

- **Critically damped series RLC ($\alpha=\omega_0$), worked numerically.** With $V_s=24$ V, $R=12\ \Omega$, $L=0.3$ H, $C=8.33$ mF: $v_C(t)=-(24+480t)e^{-20t}+24$ V. The repeated root forces the second independent solution $te^{-\alpha t}$.
- **Underdamped series RLC ($\alpha<\omega_0$, i.e. $R<2\sqrt{L/C}$).** The square root $\sqrt{\alpha^2-\omega_0^2}$ is imaginary, so he defines $\omega_d\equiv\sqrt{\omega_0^2-\alpha^2}$, which is real. The solution then contains $e^{\pm j\omega_d t}$. Euler's formula turns these into $\cos\omega_d t$ and $\sin\omega_d t$, so the response is an oscillation inside a decaying exponential.
- **The real-coefficient form.** He writes $v_C=D_1e^{-\alpha t}\cos\omega_d t+D_2e^{-\alpha t}\sin\omega_d t+V_s$ with $D_1=A_1+A_2$ and $D_2=j(A_1-A_2)$. Because $v_C$ is a physical voltage it must be real, so $D_1$ and $D_2$ must be real too. That makes this the easier form to work with.
- **Underdamped worked example.** Same $V_s,R,L$ with $C=0.72$ mF gives $\alpha=20$ Np/s, $\omega_0\approx68$ rad/s and $\omega_d\approx65$ rad/s. The result is $v_C(t)=(-24\cos65t-7.4\sin65t)e^{-20t}+24$ V. It overshoots 24 V and rings down, with the first peak at about $\pi/65$ s.
- **The three behaviours are generic.** Overdamped, critically damped and underdamped responses appear in any RLC circuit, not just the series one, because the circuit always reduces to a 2nd-order linear ODE with constant coefficients.
- **General procedure for any RLC circuit.** He demonstrates it on a non-series topology (Ulaby Ex. 6-10). The steps are: (0) find initial and final conditions from the DC circuits at $t<0$ and $t\to\infty$; (1) derive the ODE, using KCL plus a second relation (branch KVL) to eliminate the extra unknown, differentiating where needed; (2) solve, using the characteristic equation for the complementary function and a constant particular integral; (3) apply the initial conditions; then check against the final condition.
- **Ex. 6-10 result.** The ODE is $i_L''+\tfrac{29}{4}i_L'+10i_L=15$. The roots are $s=-1.85$ and $-5.40$ Np/s, so the response is overdamped. The answer is $i_L(t)=-0.76e^{-1.85t}+0.26e^{-5.40t}+1.5$ A, which matches the final condition $i_L(\infty)=1.5$ A.
- **Conceptual trap he flags.** $v_L(0^-)=0$ does not by itself give $v_L(0^+)=0$, because an inductor voltage can jump. You get $v_L(0)$ from KVL using the continuous quantities $v_C(0)$ and $i_L(0)$, and then $di_L/dt(0)=v_L(0)/L$.

---

## Content

### [0:00:02] Announcements
- Problem Set 2 is due today. **Problem Set 3 is due Mon Sep 21. "This one is a longer problem set, so you should make sure that you leave enough time."**
- **Wed Sep 16:** no live class or office hours. The lecture will be recorded and posted on Canvas, and you should watch it before class on Sep 21. Office hours that Wednesday afternoon, 4:30–6 pm, EER 3.802 (travel permitting).
- **Wed Sep 23:** no class or office hours (he is travelling). The recording will be posted and must be watched before Sep 28.

### [0:02:00] Recap of the previous lecture (series RLC, step input)
- **Circuit (from the 9/9 notes, partly visible at 0:03:12):** $v_s(t)$ ($\pm$, polarity + on top) in series with $R$, $L$ and $C$, with $v_C$ measured across $C$ (+ on top). $v_s(t)=V_s\,u(t)$ with $V_s$ constant and $u(t)=0$ for $t<0$, $1$ for $t\ge0$. Goal: solve for $v_C(t)$ for $t\ge0$.
- **Step 0, initial and final conditions (9/9 notes, shown at 0:10:21):**
  - $t<0$: $v_C(t)=0$ and $i_C(t)=0$, so $v_C(0^-)=0$ and $i_C(0^-)=0$.
  - $t=0$: $v_C$ is continuous, so $v_C(0)=0$. $i_L$ is continuous, so $i_C(0)=i_L(0)=0$. Since $i_C=C\,dv_C/dt$, we must also have $\left.\dfrac{dv_C}{dt}\right|_{t=0}=0$.
  - $t\to\infty$: $C$ behaves as an open circuit and $L$ as a short, so $v_C(\infty)=V_s$ and $i_C(\infty)=0$.
- **Step 1, ODE (9/9):** KVL gives $Ri_C+L\dfrac{di_C}{dt}+v_C=V_s$, with $i_C=C\dfrac{dv_C}{dt}$. Substituting, $RC\dfrac{dv_C}{dt}+LC\dfrac{d^2v_C}{dt^2}+v_C=V_s$, or
  $$\frac{d^2v_C}{dt^2}+\frac{R}{L}\frac{dv_C}{dt}+\frac{1}{LC}v_C=\frac{1}{LC}V_s.$$
- **Step 2, general solution method (9/9):** Take $\dfrac{d^2v_C}{dt^2}+a\dfrac{dv_C}{dt}+bv_C=c$. Its homogeneous version is (*): $v_C''+av_C'+bv_C=0$. Since $\frac{d}{dt}e^{st}\propto e^{st}$, try $v_C=Ae^{st}$. That gives $s^2+as+b=0$ (**), "the characteristic equation." So
  $$s=\frac{-a\pm\sqrt{a^2-4b}}{2}=-\frac a2\pm\sqrt{\left(\frac a2\right)^2-b},$$
  and the homogeneous solution is $v_C=A_1e^{s_1t}+A_2e^{s_2t}$.
  - For series RLC, $a=R/L$ and $b=1/LC$. If $R=0$ the roots are imaginary and the solution oscillates at $\omega_0=1/\sqrt{LC}$, the **resonant frequency** [rad/s]. For $R\ne0$ he defines the **damping factor** $\alpha=R/2L$ [Np/s]. A neper is the "unit for differences on a natural logarithmic scale, or equivalently for multiplicative factors on a linear scale." $\alpha\neq0$ means exponential decay of the transient voltages and currents.
  - The particular integral is $v_C=V_s$, so the full solution is $v_C=A_1e^{-\alpha t}e^{\sqrt{\alpha^2-\omega_0^2}\,t}+A_2e^{-\alpha t}e^{-\sqrt{\alpha^2-\omega_0^2}\,t}+V_s$.
  - "There are three distinct behaviors that can occur, corresponding to $\sqrt{\alpha^2-\omega_0^2}$ = real, zero, or imaginary."
  - **(i) Overdamped** ($\alpha>\omega_0$, $R>2\sqrt{L/C}$): two decaying exponentials. The 9/9 example was $V_s=24$ V, $R=64\ \Omega$, $L=0.8$ H, $C=2$ mF, giving $\alpha=40$, $\omega_0=25$, $\sqrt{\alpha^2-\omega_0^2}\approx31.2$, $s=-8.8,-71.2$, and $v_C=-27.38e^{-8.8t}+3.38e^{-71.2t}+24$ V, with the sketch time scale marked $\approx(1/8.8)$ s. My check gives $A_1=-27.37$ and $A_2=3.37$, which matches.
  - **(ii) Critically damped** ($\alpha=\omega_0$, $R=2\sqrt{L/C}$): "Our exponential solution for $v_C(t)$ now has only one independent function, $A_1e^{-\alpha t}$, so we need to find a second independent solution to (*)." **Derivation (9/9 notes, shown 0:10:03–0:10:05):** suppose first that $s_1\ne s_2$, so $e^{s_1t}$ and $e^{s_2t}$ are both solutions. Then $\dfrac{e^{s_2t}-e^{s_1t}}{s_2-s_1}$ is also a solution (i.e. $A_1=\frac{-1}{s_2-s_1}$, $A_2=\frac{1}{s_2-s_1}$). As $s_2\to s_1$, with $s_2=s_1+\Delta s$,
    $$\lim_{s_2\to s_1}\frac{e^{s_2t}-e^{s_1t}}{s_2-s_1}=\lim_{\Delta s\to0}\frac{e^{(s_1+\Delta s)t}-e^{s_1t}}{\Delta s}=\left.\frac{d}{ds}e^{st}\right|_{s=s_1}=te^{s_1t}.$$
    "Thus, our second independent solution to (*) is $te^{s_1t}$." The full solution is $v_C=A_1e^{s_1t}+A_2te^{s_1t}+V_s$.

### [0:04:18] Worked example 1: critically damped series RLC
Written on the board: "(ii) critically damped response: $\alpha=\omega_0$, or $R=2\sqrt{L/C}$. $\alpha=\frac{R}{2L}$ and $v_C(t)=A_1e^{-\alpha t}+A_2te^{-\alpha t}+V_s$ $(t\ge0)$."

**Given:** $V_s=24$ V, $R=12\ \Omega$, $L=0.3$ H, $C=8.33$ mF. Same series circuit, source steps on at $t=0$.

1. **Check the regime** (he does the arithmetic aloud):
   - $\alpha=\dfrac{R}{2L}=\dfrac{12}{0.6}=\dfrac{120}{6}=20$ Np/s.
   - $LC=(3\times10^{-1})(\tfrac{25}{3}\times10^{-3})=25\times10^{-4}$, so $\omega_0=\sqrt{\dfrac{1}{LC}}=\tfrac15\times10^{2}=20$ rad/s ✓. This confirms critical damping.
2. **General solution:** $v_C(t)=A_1e^{-20t}+A_2te^{-20t}+24$ V.
3. **Apply the initial conditions at $t=0$** (from the 9/9 analysis: $v_C(0)=0$, $dv_C/dt|_0=0$):
   - $v_C(0)=0\Rightarrow A_1+24=0$. The $t\,e^{-20t}$ term vanishes at $t=0$.
   - $\left.\dfrac{dv_C}{dt}\right|_{t=0}=0\Rightarrow-20A_1+A_2=0$. The first term gives $-20A_1$. The product rule on $A_2te^{-20t}$ gives $A_2e^{-20t}$ plus $A_2t(-20)e^{-20t}$, and the second piece is zero at $t=0$. The derivative of 24 is 0.
   - So $A_1=-24$ V and $A_2=20A_1=-480$ V.
4. **Result (boxed):**
   $$\boxed{v_C(t)=-(24+480t)e^{-20t}+24\ \text{V}}\quad\text{for }V_s=24\text{ V},\ R=12\ \Omega,\ L=0.3\text{ H},\ C=8.33\text{ mF}$$
5. **Sketch (0:13:00):** $v_C$ starts at 0 with zero slope and rises smoothly (S-shaped) to the dashed asymptote at 24 V, with no overshoot. The tick on the $t$-axis is labelled "$\approx(1/20)$ s". He says the 1/e point is "roughly equal to 1/20th of a second. It's not exactly that because we have this 480t, this linear term in t, but it's roughly that."

> [!warning] The "≈ 1/20 s" tick is a weak approximation for a critically damped curve (the board math is correct)
> Checked with python3 and ngspice: $v_C(1/20\text{ s})=6.34$ V, which is only 26% of the way to 24 V, not 63%. The 63% point is at $t\approx0.107$ s $\approx2.1/\alpha$. He does hedge ("not exactly… order of magnitude"). Do not treat $1/\alpha$ as a time constant when a $te^{-\alpha t}$ term is present. The numbers $A_1=-24$, $A_2=-480$ and $\omega_0=20.004$ (with $C=8.33$ mF; exactly 20 for $C=25/3$ mF) are all correct.

### [0:16:17] (iii) Underdamped response: derivation
Board: "(iii) Underdamped response: $\alpha<\omega_0$ ($\sqrt{\alpha^2-\omega_0^2}$ = imaginary), or $R<2\sqrt{L/C}$." He calls this "a small value of the damping factor" and "basically small values of the resistance."

1. "Since $\sqrt{\alpha^2-\omega_0^2}$ is imaginary, let $\omega_d\equiv\sqrt{\omega_0^2-\alpha^2}$, so $\omega_d$ is real. Then"
   $$v_C(t)=A_1e^{-\alpha t}e^{j\omega_dt}+A_2e^{-\alpha t}e^{-j\omega_dt}+V_s.$$
   This "is just rewriting the general solution that we got last time, but using $\omega_d$ instead of $\sqrt{\alpha^2-\omega_0^2}$." Here $\sqrt{\alpha^2-\omega_0^2}=j\omega_d$.
2. He braces the $e^{\pm j\omega_dt}$ factors as **"oscillatory functions"**: either the pair $\{e^{\pm j\omega_dt}\}$ or the pair $\{\sin\omega_dt,\cos\omega_dt\}$. "We have two independent functions, and there are multiple ways that we can write all the possible combinations of these."
3. "Recall that $e^{j\omega t}=\cos\omega t+j\sin\omega t$ (Euler's formula)." Substituting:
   $$v_C(t)=A_1e^{-\alpha t}(\cos\omega_dt+j\sin\omega_dt)+A_2e^{-\alpha t}(\cos\omega_dt-j\sin\omega_dt)+V_s$$
4. Grouping terms:
   $$=\underbrace{(A_1+A_2)}_{D_1}e^{-\alpha t}\cos\omega_dt+\underbrace{j(A_1-A_2)}_{D_2}e^{-\alpha t}\sin\omega_dt+V_s$$
5. **"Since $v_C(t)$ must be real, we know $D_1,D_2$ must be real as well."** $A_1$ and $A_2$ "might have ended up being complex." So solve for $D_1$ and $D_2$ directly.

**Standard underdamped form (his):**
$$v_C(t)=D_1e^{-\alpha t}\cos\omega_dt+D_2e^{-\alpha t}\sin\omega_dt+V_s,\qquad \omega_d=\sqrt{\omega_0^2-\alpha^2}$$

### [0:26:30] Worked example 2: underdamped series RLC
**Given:** $V_s=24$ V, $R=12\ \Omega$, $L=0.3$ H, $C=0.72$ mF. This is the same as example 1 except $C$ is smaller, so $\omega_0$ is higher and $R$ is now below $2\sqrt{L/C}$.

1. $\alpha=\dfrac{R}{2L}=20$ Np/s (unchanged). $\omega_0=\sqrt{1/LC}\approx68$ rad/s, so $\alpha<\omega_0$ ✓ and the response is underdamped.
2. $\omega_d=\sqrt{\omega_0^2-\alpha^2}\approx65$ rad/s, "the frequency at which these oscillations occur."
3. **General solution:** $v_C(t)=D_1e^{-20t}\cos65t+D_2e^{-20t}\sin65t+24$ V.
4. **Initial conditions (same as before):**
   - $v_C(0)=0\Rightarrow D_1+24=0$, since the $\cos$ term is 1 and the $\sin$ term is 0 at $t=0$.
   - For $dv_C/dt$ he writes out the derivative explicitly (product rule):
     $$v_C'(t)=-20e^{-20t}(D_1\cos65t+D_2\sin65t)+e^{-20t}(65)(-D_1\sin65t+D_2\cos65t)$$
     At $t=0$ he strikes out the sine terms in red, leaving $-20D_1+65D_2=0$.
   - So $D_1=-24$ V and $D_2=\dfrac{20}{65}D_1=-7.4$ V.
5. **Result (boxed):**
   $$\boxed{v_C(t)=(-24\cos65t-7.4\sin65t)e^{-20t}+24\ \text{V}}\quad\text{for }V_s=24\text{ V},\ R=12\ \Omega,\ L=0.3\text{ H},\ C=0.72\text{ mF}$$
6. **Sketch (0:35:00):** $v_C$ starts at 0 with zero slope, rises past 24 V, peaks, dips below 24 V, and oscillates around the 24 V dashed line with decaying amplitude. The first peak is marked "$\approx(\pi/65)$ s". His reasoning: at $t=\pi/65$, $\cos(65t)=\cos\pi=-1$, so the $-24\cos$ term becomes $+24$, "whereas over here [t = 0] this corresponded to the cosine of 0 which is 1… this −24 canceling out with this 24." The oscillation "is going to decay exponentially because of this $e^{-20t}$ factor."

**Verification (python3 + ngspice transient of the series RLC):**
- $\omega_0=68.04$ rad/s, $\omega_d=65.04$ rad/s, $D_2=-7.38$ V (rounds to his −7.4 V) ✓.
- The first peak is at exactly $t=\pi/\omega_d=48.3$ ms. For a zero-IC step, $v_C'(t)=\frac{\omega_0^2}{\omega_d}V_se^{-\alpha t}\sin\omega_dt$, which first vanishes at $\pi/\omega_d$. ngspice gives a peak of 33.13 V at 48.3 ms ✓.
- *(My addition, not on the board.)* Peak value $=24\left(1+e^{-\alpha\pi/\omega_d}\right)=24(1+0.380)=33.1$ V, which is **38% overshoot**. It is not $24+24=48$ V: his "+24" is the cosine term before the $e^{-20t}$ envelope multiplies it. Period $=2\pi/\omega_d=96.6$ ms; envelope time constant $=1/\alpha=50$ ms. Amplitude–phase form: $v_C=25.1\,e^{-20t}\cos(65t+162.9^\circ)+24$ V.

### [0:37:03] The three behaviours are general
- Overdamped: "purely exponential decay… with two different exponential values." Critically damped: "one exponential value but then also a term that goes linearly in t." Underdamped: "a combination of oscillation and exponential decay."
- "Even in more complicated circuit configurations than just the simple RLC series circuit you still get those three basic types of behavior, because in the end you're going to have a second order differential equation and the solutions to that will still be the same kinds of exponentials… the details of that behavior will differ then depending on the specific circuit."

### [0:38:24] Other RLC circuit configurations
- **Reading: Ulaby et al., Secs. 6-7, 6-8.**
- Board: "Other RLC circuit configurations can be analyzed + understood using the same general approach we used for the RLC series circuit."
- More examples: an upcoming recitation and the **problem-solving videos on Canvas**.

### [0:40:36] Worked example 3: Ulaby Ex. 6-10 (non-series RLC, find $i_L(t)$)
**Circuit (0:41:06–0:43:59, frames f_0383/f_0390):**
- The bottom rail is **ground**.
- Left column: 24 V DC source ($\pm$, + on top, always on), with a **4 Ω** resistor in series above it, reaching node A at the top-left.
- Top rail: an **8 Ω** resistor from node A to node B. A **switch is wired directly in parallel with the 8 Ω** (drawn above it) and **closes at $t=0$**. It is open for $t<0$.
- From node B (the top-right node; its voltage is $v_C$) there are two branches to ground:
  - the **2 H inductor** in series with a **12 Ω** resistor below it. $i_L$ is defined **downward** through the inductor, with $v_L$ having + at the top.
  - the **0.2 F capacitor**, with $v_C$ having + at the top.
- **Goal: find $i_L(t)$ for all $t\ge0$.**

"You can see this is a more complicated configuration than just the series RLC circuit, but the way that we approach it will be exactly the same."

#### Step 0: initial and final conditions [0:43:07]
**$t<0$ (switch open, DC steady state, so L acts as a short and C as an open).** Redrawn: 24 V → 4 Ω → 8 Ω → node B. From node B, the L branch (short, $v_L$ marked) and the 12 Ω go to ground. The C branch is open, with $v_C$ across the open terminals. "The switch… we don't have to include because it's open."
- $i_L(0^-)=\dfrac{24\text{ V}}{4\ \Omega+8\ \Omega+12\ \Omega}=1$ A. **$=i_L(0)$**, "since we know that the current through an inductor always has to be continuous."
- $v_L(0^-)=0$, because the inductor acts as a short. **But** "we cannot from this, and only this, conclude that the voltage across the inductor at t = 0 is equal to 0, because the voltage across an inductor can be discontinuous. So we have to wait to figure that out."
- $v_C(0^-)=(12\ \Omega)(i_L(0))=12$ V. **$=v_C(0)$**, by capacitor-voltage continuity. The 12 V across the open C equals the voltage across the L+12 Ω branch, and $v_L=0$.
- **Now** confirm $v_L(0)$: $v_C(0)=12$ V (continuous) and $i_L(0)=1$ A (continuous), so the 12 Ω drops 12 V. Hence $v_L(0)=v_C(0)-12i_L(0)=0$.
- $v_L(0)=0=L\left.\dfrac{di_L}{dt}\right|_{t=0}\Rightarrow\boxed{\left.\dfrac{di_L}{dt}\right|_{t=0}=0}$
- Initial conditions (underlined): $i_L(0)=1$ A and $di_L/dt|_0=0$.

**$t\to\infty$ (switch closed, which "shorts out this 8 Ω resistor").** Redrawn: 24 V → 4 Ω → node B. L is a short in series with the 12 Ω; C is open.
- $i_L(\infty)=\dfrac{24\text{ V}}{4\ \Omega+12\ \Omega}=\dfrac32$ A.
- $v_C(\infty)=(12\ \Omega)\,i_L(\infty)=18$ V.

#### Step 1: differential equation for $i_L(t)$, $t\ge0$ [0:52:04]
"The part that often is kind of the trickiest."

$t\ge0$ circuit: 24 V → 4 Ω → node B (the 8 Ω is shorted by the closed switch). From node B: 2 H in series with 12 Ω to ground ($i_L$ down), and 0.2 F to ground ($v_C$, + at top).

**Node analysis (KCL @ $v_C$), with the sum of currents leaving the node equal to zero:**
$$\frac{v_C-24}{4}+i_L+(0.2)\frac{dv_C}{dt}=0$$
This has two unknown functions, $v_C$ and $i_L$, so a second relation is needed. **Also**, by KVL down the L–R branch:
$$v_C=(2\text{ H})\frac{di_L}{dt}+(12\ \Omega)i_L$$
Substitute $v_C$ (and its derivative $\frac{dv_C}{dt}=2\frac{d^2i_L}{dt^2}+12\frac{di_L}{dt}$):
$$\frac14\left(2\frac{di_L}{dt}+12i_L\right)-6+i_L+(0.2)\left[2\frac{d^2i_L}{dt^2}+12\frac{di_L}{dt}\right]=0$$
Collect terms. $i_L''$: $0.2\times2=0.4$. $i_L'$: $\frac24+0.2\times12=0.5+2.4=2.9$. $i_L$: $\frac{12}{4}+1=4$. Constant: $-6$ moves to the right-hand side.
$$0.4\frac{d^2i_L}{dt^2}+2.9\frac{di_L}{dt}+4i_L=6$$
Divide by 0.4:
$$\boxed{\frac{d^2i_L}{dt^2}+\left(\frac{29}{4}\right)\frac{di_L}{dt}+10\,i_L=15}\qquad(*)$$

#### Step 2: solve the differential equation [1:03:00]
- "Let $i_L(t)=Ae^{st}$. Then the homogeneous equation becomes" $s^2Ae^{st}+\frac{29}{4}sAe^{st}+10Ae^{st}=0$. The $Ae^{st}$ factors are cancelled in red, giving the characteristic equation
  $$s^2+\left(\frac{29}{4}\right)s+10=0$$
- $s=-\dfrac{29}{8}\pm\sqrt{\left(\dfrac{29}{8}\right)^2-10}=-3.625\pm1.772=\begin{cases}-1.85\ \text{Np/s}\\-5.40\ \text{Np/s}\end{cases}$
- Under the radical he braces $(29/8)^2$ as $\alpha^2$ and $10$ as $\omega_0^2$.
- **"Both values of s are real ⇒ overdamped response."** "Alternatively, we see $\alpha=\frac{29}{8}$ and $\omega_0=\sqrt{10}$, so $\alpha>\omega_0$ ⇒ overdamped response."
- "The solution to the homogeneous equation, i.e. the **complementary function**, is" $i_L(t)=A_1e^{-1.85t}+A_2e^{-5.40t}$.
- "A **particular integral** for (*) is $i_L=1.5$ A." The right-hand side is constant, so try a constant: the derivatives vanish and $10i_L=15$ gives $i_L=1.5$.
- **Full solution (before initial conditions are applied):** $i_L(t)=A_1e^{-1.85t}+A_2e^{-5.40t}+1.5$ A $(t\ge0)$.

#### Step 3: apply initial conditions to determine $A_1,A_2$ [1:11:23]
- $i_L(0)=1$ A $\Rightarrow A_1+A_2+1.5=1$.
- $\left.\dfrac{di_L}{dt}\right|_{t=0}=0\Rightarrow-1.85A_1-5.40A_2=0$. Each derivative "brings down a factor of the coefficient in the exponent."
- Matrix form: $\begin{pmatrix}1&1\\-1.85&-5.40\end{pmatrix}\begin{pmatrix}A_1\\A_2\end{pmatrix}=\begin{pmatrix}-0.5\\0\end{pmatrix}$. He uses **Cramer's rule** ("you could use any other method"):
  - $A_1=\dfrac{(-0.5)(-5.40)}{-5.40+1.85}=-0.76$ A
  - $A_2=\dfrac{-(-0.5)(-1.85)}{-5.40+1.85}=0.26$ A
- **The full solution is then**
  $$\boxed{i_L(t)=-0.76e^{-1.85t}+0.26e^{-5.40t}+1.5\ \text{A}}\quad\text{for }t\ge0$$
- "This also agrees with our final condition for $i_L(\infty)$ determined earlier": $i_L\to1.5$ A.

**Verification:**
- python3: roots $-1.853$ and $-5.397$; $A_1=-0.761$, $A_2=0.261$. The formula gives $i_L(0)=1.000$ and $i_L'(0)=0$; $v_C(t)=2i_L'+12i_L$ gives $v_C(0)=12$ and $v_C(\infty)=18$ ✓.
- ngspice, with a real switch across the 8 Ω closing at $t=1$ s and the DC operating point computed beforehand: $i_L(0^-)=1.000$ A and $v_C(0^-)=12.00$ V. Then $i_L(0.5)=1.216$, $i_L(1)=1.382$, $i_L(2)=1.481$, $i_L(3)=1.497$, $i_L(\infty)=1.500$ A; $v_C(\infty)=18.0$ V. All match the closed form ✓. **No board errors in this example.**
- *(My addition.)* Physical picture: $i_L$ rises monotonically from 1 A to 1.5 A with zero initial slope and no overshoot (overdamped). Settling is dominated by the slow root, $\tau\approx1/1.85=0.54$ s. A consistency check: KCL at $t=0^+$ gives $\frac{12-24}{4}+1+0.2v_C'(0)=0$, so $v_C'(0^+)=10$ V/s. That matches $2i_L''(0)+12i_L'(0)=2(5)+0=10$ V/s, where $i_L''(0)=15-10(1)=5$ from (*).

### [1:17:34] Questions and wrap-up
- See *Student questions*. The recorded part (Wednesday) will recap key points from these RLC examples, point to more examples, and **start phasors**, "a powerful tool for analysis of AC, that is sinusoidal signal, circuit behavior."

> [!warning] Board error carried over from the 9/9 notes (shown on screen this lecture at 0:10:13 and 0:20:14–0:20:20)
> In the "Now consider the particular integral for the full differential equation" line, the 9/9 page reads $\dfrac{d^2v_C}{dt^2}+\dfrac{R}{2}\dfrac{dv_C}{dt}+\dfrac{1}{LC}v_C=\dfrac{V_s}{LC}$. **The coefficient should be $R/L$, not $R/2$.** (He says "R over L" while writing it, so it may be a cursive L rather than a slip; either way, use $R/L$.) The same page derives it correctly earlier, as $\frac{d^2v_C}{dt^2}+\frac{R}{L}\frac{dv_C}{dt}+\frac{1}{LC}v_C=\frac{1}{LC}V_s$, and $a=R/L$ gives $\alpha=a/2=R/2L$. He did not correct it in class. If your notes copy that line, fix it.

> [!warning] Minor verbal slip / ASR
> At 0:17:00 the transcript reads "r being less than 2 times the square root of l". The board has the correct $R<2\sqrt{L/C}$. Other ASR errors resolved from the frames: "Orler's formula" = Euler's formula; "24 alpha" (0:28:14) = "20 for α"; "dBCdt" = $dv_C/dt$; "millifurads" = mF.

---

## Ed Yu's conventions & notation

- **Names and units:**
  - $\alpha$ = **"damping factor"**, in **nepers per second**, written "Npr/s" on the board.
  - $\omega_0$ = **"resonant frequency"**, in rad/s.
  - $\omega_d\equiv\sqrt{\omega_0^2-\alpha^2}$ is defined only in the underdamped case and described as "the frequency at which these oscillations occur." (Ulaby calls it the damped natural frequency; he did not use that phrase.)
  - Roots $s_1$ and $s_2$ are given in **Np/s** when real (e.g. "−1.85 Npr/s").
- **Series RLC formulas:**
  - $\alpha=R/2L$ and $\omega_0=1/\sqrt{LC}$.
  - Regime conditions are stated both as $\alpha$ vs $\omega_0$ and as $R$ vs $2\sqrt{L/C}$ (overdamped $R>2\sqrt{L/C}$, critical $=$, underdamped $<$).
  - He also classifies by whether $\sqrt{\alpha^2-\omega_0^2}$ is "real, zero, or imaginary."
- **For non-series circuits** he does not use $R/2L$. He reads the parameters off the normalized ODE $x''+ax'+bx=c$: $\alpha=a/2$ and $\omega_0^2=b$ (Ex. 6-10: $\alpha=29/8$, $\omega_0=\sqrt{10}$). His primary classifier there is the roots themselves: "both values of s are real ⇒ overdamped."
- **Normalized ODE form:** he always divides through so the leading coefficient is 1: $\frac{d^2x}{dt^2}+a\frac{dx}{dt}+bx=c$ (e.g. dividing $0.4i_L''+\dots$ by 0.4). He keeps fractions ($29/4$) rather than decimals in the boxed ODE.
- **Solution forms (all with steady state $X_\infty$ added):**
  - Overdamped: $A_1e^{s_1t}+A_2e^{s_2t}+X_\infty$, which he also writes as $A_1e^{-\alpha t}e^{\sqrt{\alpha^2-\omega_0^2}t}+A_2e^{-\alpha t}e^{-\sqrt{\alpha^2-\omega_0^2}t}+V_s$.
  - Critically damped: $A_1e^{-\alpha t}+A_2te^{-\alpha t}+X_\infty$.
  - Underdamped: $D_1e^{-\alpha t}\cos\omega_dt+D_2e^{-\alpha t}\sin\omega_dt+X_\infty$, with $D_1=A_1+A_2$ and $D_2=j(A_1-A_2)$, both real. He keeps cos/sin separate and does **not** convert to amplitude–phase form.
- **Constants carry units:** $A_1=-24$ V, $D_2=-7.4$ V, $A_1=-0.76$ A.
- **ODE vocabulary:** "homogeneous equation" (right-hand side set to 0); "characteristic equation" (**); "complementary function" (the homogeneous solution, "which in a differential equations class you would typically call the complementary function"); "particular integral"; "full solution (before initial conditions are applied)."
- **Numbered procedure** (used on 9/9 and here):
  - **0)** initial + final conditions
  - **1)** differential equation for $x(t)$, $t\ge0$
  - **2)** solve the differential equation
  - **3)** apply initial conditions to determine $A_1,A_2$
  - then check against the final condition.
- **Initial-condition notation:** he computes quantities at $t=0^-$ from the DC circuit, then writes "$=i_L(0)$" or "$=v_C(0)$" with a squiggly underline only for **continuous** quantities ($i_L$, $v_C$). "$t=0$" in his ICs means just after switching. He never writes $0^+$ explicitly.
- **Reference directions:**
  - $i_L$ is drawn as an arrow **down** through the inductor branch.
  - $v_L$ and $v_C$ use the passive sign convention with **+ at the top** node.
  - KCL is written as "**the sum of all the outgoing currents** = 0," with the source branch current written as $(v_C-24)/4$ leaving the node.
  - The ground node is marked at the bottom rail, and node voltages are taken relative to it.
- **Continuity rules as he states them:** "the current through an inductor always has to be continuous"; "the voltage across the capacitor has to be continuous"; "the voltage across an inductor can be discontinuous."
- **Linear algebra:** he writes the 2×2 system in matrix form and uses **Cramer's rule** ("as usual").
- **Sketches:** horizontal dashed line at the steady-state value; $t$-axis tick at the characteristic time ($\approx1/\alpha$ for critical, $\approx\pi/\omega_d$ for the first underdamped peak); curve in green.
- **Euler:** $e^{j\omega t}=\cos\omega t+j\sin\omega t$, with $j$ as the imaginary unit. Phasors are introduced next lecture; nothing on peak vs rms yet.
- Uses $u(t)$ for the unit step: $v_s(t)=V_s u(t)$.

---

## Intuition & explanations he gives

- **Why the response oscillates when $\alpha<\omega_0$ (0:20:41):** "Instead of just having purely exponential functions, we have sines and cosines in here, so we have oscillation." The imaginary square root turns $e^{\sqrt{\alpha^2-\omega_0^2}t}$ into $e^{\pm j\omega_dt}=\cos\omega_dt\pm j\sin\omega_dt$. "If we look at this form of the solution… we can see immediately that we're going to get some kind of oscillatory behavior because we have cosines and sines in our mathematical form."
- **Why use sin/cos instead of $e^{\pm j\omega_dt}$ (0:22:11):** "In the end it'll be easier to work with because we know that in the end the voltage across the capacitor has to be a real quantity. It can't be a complex quantity because it's the physical voltage." So $D_1$ and $D_2$ must be real, "whereas $A_1$ and $A_2$ might have ended up being complex."
- **What underdamping looks like physically (0:36:43):** "In the underdamped case… you still approach the same steady state value, 24 volts, but then you'll have some oscillation around that value which will decay exponentially as you approach that steady state value." Compared with the other two cases it is "a qualitatively different kind of response."
- **Damping vs resistance:** "Large damping factor corresponding to a large resistance" gives overdamped; "small values of the resistance" gives underdamped (series RLC).
- **Why critical damping needs $te^{-\alpha t}$:** "You reach the limit where those two different exponentials that we got in the over-damped case are equal to each other… we had to come up with a second independent solution." It is the $s$-derivative of $e^{st}$ at the double root (the 9/9 limit derivation).
- **Meaning of the exponent's coefficient (0:15:19):** "The significance of the coefficient in the exponent is that in general it tells you at least the order of magnitude level how much time it takes to get… two-thirds of the distance roughly to the steady state value." If it were $e^{-1000t}$, "this would be approximately 1 millisecond." For a pure exponential, at $t=1/\alpha$ you are $1-1/e\approx2/3$ of the way ("if we say [e is] roughly 3, then it's two-thirds of the way"). With the linear-in-$t$ term it is "not exactly that."
- **Shape of the critically damped curve:** "It starts off with zero slope… and $v_C$ equal to 0, and then it gradually approaches the steady state value of 24 volts" with no overshoot.
- **Why the three behaviours are universal (0:37:46):** "Even in more complicated circuit configurations… you still get those three basic types of behavior, because in the end you're going to have a second order differential equation and the solutions to that will still be the same kinds of exponentials."
- **Why you cannot read $v_L(0^+)$ off the $t<0$ circuit (0:47:02):** "The voltage across an inductor can be discontinuous, so we have to wait to figure that out." Get it from KVL with the continuous quantities: $v_L(0)=v_C(0)-12\,i_L(0)=12-12=0$, so $di_L/dt(0)=0$.
- **Why $i_L$ is continuous and $v_C$ is continuous:** stated as rules ("always has to be continuous") and used to carry $t=0^-$ values to $t=0$. From 9/9: $i_C=C\,dv_C/dt$, so a known $i_C(0)$ gives $dv_C/dt(0)$.
- **How to build the ODE in a messy circuit (1:01:41):** "Applying what in this case was the pretty obvious circuit analysis [node analysis]… we got an equation that involved two unknown quantities, $i_L$ and $v_C$, and then we looked at the circuit and figured out some other relationship between those two functions, and then we just did a substitution so that we would have an equation that only involved one unknown." "Sometimes you'll have to do something like maybe taking the derivative of some equation."
- **Why node analysis here (0:54:01):** "This node down here is at ground… we have the one extraordinary node up here, and we can just apply KCL at that node… and one of those currents will be $i_L$. So that seems like a reasonable path."
- **Why the particular integral is a constant (1:09:30):** "Since the right-hand side is a constant, the easiest particular integral to use here is just a constant value for $i_L$." The derivatives vanish, so $i_L=15/10$.
- **The final value is the particular integral (1:17:40):** "The final condition really just corresponds to the particular integral, the way that we get the particular integral in this case." So the $t\to\infty$ DC analysis is an independent check on the ODE.
- **Effect of the switch:** a closed switch in parallel with the 8 Ω "shorts out this 8 ohm resistor, so basically we can take this 8 ohm resistor… out of the circuit."
- **Characteristic equation shortcut:** each time derivative of $Ae^{st}$ "brings down a factor of s"; "after you've done this once or twice you can pretty much go directly to the characteristic equation."

---

## Emphasis & exam intel

1. **Deriving the ODE is the hard step.** [0:52:04] "We get to the part that often is kind of the trickiest, which is to come up with a differential equation that we can solve for $i_L(t)$, and that is valid for $t\ge0$." → Exam P4(b) is always "derive the ODE with numbers," and the past P4 class averages are 42–44%.
2. **Inductor voltage can jump, so don't assume $v_L(0^+)=v_L(0^-)$.** [0:47:02] "We cannot from this, and only this, conclude that the voltage across the inductor at t equal to 0 is equal to 0, because the voltage across an inductor can be discontinuous, so we have to wait to figure that out." [0:48:17] "It'll turn out to be 0, but it's only now that we can confirm that." → This is the standard way to get the 2nd IC: $di_L/dt(0)=v_L(0)/L$.
3. **The same method works for every RLC topology.** [0:40:14] "Other RLC circuit configurations can be analyzed and understood using basically the same general approach." [1:02:07] "Most of RLC circuit analysis will be some variation of this: applying the standard tools… and then coming up with other relationships that we know have to be true among the various different currents and/or voltages." → Exam P4 has used a non-canonical topology (F24). Don't plug into $R/2L$ unless the circuit really is series.
4. **The three behaviours come from any 2nd-order ODE.** [0:37:46] "You still get those three basic types of behavior, because in the end you're going to have a second order differential equation." → P1 "explain why" material.
5. **Classify from the roots.** [1:07:12] "The easiest way to see it is that both values of s are real, which means that… we're in the case of over-damped response." Alternatively, compare $\alpha=a/2$ with $\omega_0=\sqrt b$.
6. **Use the real sin/cos form for underdamped.** [0:22:11] "It'll make more sense in the end to write it in terms of sines and cosines… the voltage across the capacitor has to be a real quantity." [0:25:20] "Since… $v_C$ has to be real… $D_1$ and $D_2$ are going to have to be real as well."
7. **Check the final value.** [1:17:45] "If you do everything else properly, then it should satisfy the final condition that we determined, but it's sort of good to see that, in fact, it does." This matches the exam's "physical check" sub-part.
8. **You may need extra quantities to get the ICs.** [1:18:19] "We needed $v_C$ at zero in order to figure out what $di_L/dt$ was at t equal to zero." (The final $v_C$ was "not necessary… we did it anyway just for illustration.")
9. **Product rule when differentiating the underdamped and critical forms.** He writes out $v_C'(t)$ in full and strikes the terms that vanish at $t=0$ (0:31:17–0:33:12, and 0:08:45 for $te^{-20t}$). Expect sign and derivative errors here.
10. **Go straight to the characteristic equation.** [1:05:18] "After you've done this once or twice, you can pretty much go directly to the characteristic equation."
11. **Reading and practice:** Ulaby Secs. **6-7, 6-8**; **Example 6-10** is the in-class example; more examples in an upcoming recitation and the **Canvas problem-solving videos**.
12. **Logistics:** PS3 (long) is due Mon 9/21. Wed 9/16 and 9/23 lectures are recorded only. Next topic: **phasors**.

---

## Student questions

1. **[0:09:35] "Where did the initial conditions $v_C(0)=0$ and $dv_C/dt|_0=0$ come from?"** (Reconstructed (?); the question itself is inaudible.) He scrolls back to the 9/9 notes. For $t<0$ the source is off, so all currents and voltages are 0. By continuity $v_C(0)=0$. The inductor current, which is also the capacitor current, is continuous and so 0 at $t=0$. Since $i_C\propto dv_C/dt$, that derivative is 0 too.
2. **[0:14:09] "Why did you get [≈1/20 s]?"** Because the exponential is $e^{-20t}$: at $t=1/20$ s it equals $e^{-1}$. The $480t$ term is $480/20=24$ there, "so it's not exactly that, but that's sort of the order of magnitude… you get it from the exponent."
3. **[0:14:47] Follow-up (inaudible (?), about the significance of that time).** If it were $e^{-1000t}$ it would be about 1 ms. The coefficient in the exponent tells you, at the order-of-magnitude level, how long it takes to get about 2/3 of the way to steady state.
4. **[0:15:42] "So that's the general rule?"** Yes, but it isn't exact here because of the linear-in-$t$ term. Without it you'd be at $1-1/e\approx2/3$ of the way.
5. **[0:19:32] "I understand where the j goes and $\omega_0$, but wouldn't this give us a value that's two times what we had before? Like negative two…"** (Reconstruction uncertain (?).) He scrolls back to the 9/9 roots $s=-\frac a2\pm\sqrt{(a/2)^2-b}$ and the general solution. Answer: "We absorb that two in the denominator into how we define the different quantities, the damping factor and the resonant frequency." That is, $\alpha=a/2=R/2L$, so no stray factor of 2 appears.
6. **[0:45:55] (He asks the class) "What is that current?"** Class: 1 A, since $24/(4+8+12)$.
7. **[0:47:28] (He asks) "What do you think $v_C(0^-)$ is?"** Class: 12 V, because 1 A flows through the 12 Ω and the open C sits across that branch.
8. **[0:55:33] (He asks) "What is the current flowing out to the right?"** Student: the capacitor current, $0.2\,dv_C/dt$.
9. **[0:56:20] (He asks) "What is another relationship between $v_C$ and $i_L$?… What is the voltage across the inductor?"** Student (answer partly inaudible): the branch voltage, which gives $v_C=2\,di_L/dt+12\,i_L$.
10. **[1:17:34] (Partly inaudible (?)) "Does the final condition have to come out automatically / do you have to check it?"** "The final condition really just corresponds to the particular integral, the way that we get the particular integral in this case. If you do everything else properly, then it should satisfy the final condition… but it's sort of good to see that, in fact, it does."
11. **[1:18:05] "Why do we also have to solve for $v_C$ initial and final, or is that just in the case that isn't overdamped?"** For the initial conditions, $v_C(0)$ was needed to get $di_L/dt(0)$. For the final condition it wasn't needed: "we did it anyway just for illustration."

---

## Exam relevance

**P4 (2nd-order RLC transient: ICs → ODE with numbers → solve → physical check).** This lecture is P4 end to end.
- (a) **ICs.** Use the DC $t<0$ circuit (L short, C open). Carry $i_L$ and $v_C$ across $t=0$ by continuity. Get the derivative IC from the *other* element through KVL/KCL: $di_L/dt(0)=v_L(0)/L$ with $v_L(0)=v_C(0)-Ri_L(0)$, or $dv_C/dt(0)=i_C(0)/C$. Expect to be asked for 3–4 quantities at $t=0$: $i_L$, $v_C$, $v_L$, $di_L/dt$.
- (b) **ODE "with numerical coefficients and inhomogeneous term."** Use KCL at the top node plus branch KVL, substitute, differentiate, and normalize. Ex. 6-10 is the template for a non-canonical topology like F24 P4.
- (c) **Solve.** Use the characteristic equation and classify by the roots. Write the right form: two exponentials; $A_1e^{-\alpha t}+A_2te^{-\alpha t}$; or $D_1e^{-\alpha t}\cos\omega_dt+D_2e^{-\alpha t}\sin\omega_dt$. Add the constant particular integral, then fit $A_1,A_2$ (or $D_1,D_2$) with Cramer's rule.
- (d) **Physical check.** The $t\to\infty$ limit must equal the DC final value (= the particular integral). The initial value and slope must match the ICs. Sketch with the dashed asymptote and the time-scale tick.

**P1 ("explain why") stems this lecture supports (one equation + one sentence each):**
- Why does a series RLC ring when $R<2\sqrt{L/C}$? The characteristic roots are complex, $-\alpha\pm j\omega_d$, so $e^{\pm j\omega_dt}$ means sin/cos oscillation inside the $e^{-\alpha t}$ envelope.
- Why must $D_1$ and $D_2$ be real? $v_C$ is a physical (real) voltage, and $\cos$ and $\sin$ are real independent functions.
- Why is $te^{-\alpha t}$ needed at critical damping? There is a double root, and a 2nd-order ODE needs two independent solutions to satisfy two ICs.
- Why can't you conclude $v_L(0^+)=0$ from $v_L(0^-)=0$? An inductor's voltage can jump; only $i_L$ is continuous (and only $v_C$ for capacitors).
- Why do all RLC circuits show the same three behaviours? Every one reduces to a 2nd-order linear constant-coefficient ODE.
- Why does the final value equal the particular integral? With a constant forcing, all derivatives vanish in steady state, which is the same as the L-short/C-open DC circuit.
- What does the exponent's coefficient tell you? The time scale: at $t=1/\alpha$ a single exponential has gone about 63% of the way. **Caution:** not for $te^{-\alpha t}$, where it is only 26%.
- (Past-exam stem, same logic) Why can't a first-order circuit be underdamped? Its single real root $s=-1/\tau$ cannot produce oscillation.

**Likely question variants this lecture prepares for:**
- **Critically damped P4.** It has never appeared on Exam 1 (F23–F25). He spent part of this lecture on a full numeric example. Practice the $te^{-\alpha t}$ derivative at $t=0$: $\frac{d}{dt}[A_2te^{-\alpha t}]_{0}=A_2$.
- **Underdamped series RLC with nonzero ICs** (e.g. a switch opening across C, like F23). Then $D_1=x(0)-X_\infty$ and $D_2=[x'(0)+\alpha D_1]/\omega_d$.
- **A non-series topology asking for $i_L$ or $v_C$.** The ODE must come from KCL plus branch KVL; $\alpha$ and $\omega_0$ come from the normalized coefficients, not $R/2L$.
- **"Find the peak / time of maximum" bonus.** For a zero-IC underdamped step, the first peak is at $t=\pi/\omega_d$ with value $X_\infty(1+e^{-\alpha\pi/\omega_d})$. Here that is 48.3 ms and 33.1 V.
- **Choose a component value for a given regime.** For example, pick $C$ to make the circuit critically damped: $C=4L/R^2$, giving 8.33 mF for $R=12\ \Omega$, $L=0.3$ H.

**P2/P3:** there is no direct content. Euler's formula $e^{j\omega t}=\cos\omega t+j\sin\omega t$ is the bridge to phasors, which start in the next (recorded) lecture.

**Formulas to memorize from this lecture (closed book, no sheet):**
- Series RLC: $\alpha=\dfrac{R}{2L}$, $\omega_0=\dfrac1{\sqrt{LC}}$, $\omega_d=\sqrt{\omega_0^2-\alpha^2}$. Regimes: $R\gtrless2\sqrt{L/C}$.
- General: $x''+ax'+bx=c$ gives $s=-\frac a2\pm\sqrt{(a/2)^2-b}$, so $\alpha=a/2$, $\omega_0^2=b$, $x_p=c/b$.
- Underdamped ICs: $D_1=x(0)-x_p$ and $-\alpha D_1+\omega_dD_2=x'(0)$.
- Critically damped ICs: $A_1=x(0)-x_p$ and $-\alpha A_1+A_2=x'(0)$.
