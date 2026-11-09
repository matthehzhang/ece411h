---
course: ECE 411H
kind: past-exam
source: Exam Preparation Materials/ECE_411H_SE1_short-answers_F26.pdf
source_pages: 3
author: Prof. Ed Yu
unit: exam1
topics: [semester-exam-1, short-answers, answer-key, ideal-op-amp, output-resistance, input-resistance, inductor-current-continuity, inductor-voltage, phasor-phase-relationship, inductive-impedance, average-power, instantaneous-power, time-domain-power-integral, inverting-amplifier, rc-feedback, op-amp-saturation, linear-range, transfer-function, phasor-analysis, step-response, first-order-rc, series-rc-parallel-rl, voltage-divider-impedance, source-current, average-power-to-load, purely-real-load-impedance, second-order-circuit, series-rlc, switched-circuit, initial-conditions, rlc-ode, underdamped-response, capacitor-energy, inductor-energy, charge-maximum-time]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm -r 130 and -r 220 crops) by Claude; typed text via pdftotext -layout
---

# ECE 411H Semester Exam 1 — Fall 2026 — Short Answers (official key)

**Summary.** Prof. Yu's official answer key for Semester Exam 1 given Wednesday 07 October 2026: the question sheet with typed bold answers inserted after each part, plus pasted handwritten (blue-pen scan) answers for 3(a), 3(b), 4(a), 4(b), 4(c), 4(e). Four problems, 25 points each, plus a 5-point bonus (4e) = 105. Key results: 1(a) $R_o = 0$ so the output can source any current without changing $v_o$, $R_i = \infty$ so $i_n = i_p = 0$; 1(b) $i_L$ continuous since $v_L = L\,di_L/dt$, $v_L$ may jump; 1(c) inductive; 1(d) define $P_{avg}$ as the integral of $p(t)$ over one period and integrate explicitly; 2(a) $v_o = -2V_s$, linear for $-4 \le V_s \le 4$ V; 2(b) $\mathbf{V}_o = 1.414e^{j135^\circ}\mathbf{V}_s$; 2(c) $v_o = -4(1 - e^{-250t})$ V for $t > 0$; 3(a) $v_o = 14.12\cos(1000t + 18.69^\circ)$ V; 3(b) $i_s = 99.85\cos(1000t + 63.69^\circ)$ mA; 3(c) $0.4985$ W; 3(d) $C = 5\ \mu$F, $P_{avg} = 0.5184$ W; 4(a) $i(0) = 0.2$ A, $v_C(0) = -4$ V, $di/dt|_0 = 500$ A/s, $dv_C/dt|_0 = 4\times10^3$ V/s; 4(b) $v_C'' + 10^3 v_C' + 10^6 v_C = 10^7$; 4(c) $v_C(t) = -e^{-500t}[14\cos(866t) + 3.464\sin(866t)] + 10$ V; 4(e) $t = 3.303\times10^{-3}$ s. This is the key for the graded exam in `SE1_F26_graded_Matthew.md`; the question sheet itself was not otherwise available.

## Page 1

Header line: "SEMESTER EXAM 1" (left) — "**ECE 411H**" (center, bold) — "07 October 2026" (right).

Centered, bold:
"PLEASE ATTEMPT ALL PROBLEMS AND SHOW ALL WORK!
WRITE ALL EXAM SOLUTIONS IN THE SPACES PROVIDED ON THE EXAM ANSWER SHEETS. YOU MAY USE THE BACK OF EACH PAGE FOR SCRATCH, BUT ONLY THE FRONT SIDES SHOULD BE SCANNED AND UPLOADED."

Bold paragraph: "The exam questions, answer sheets, and a calculator are allowed; no other materials should be consulted during the exam. No communication with any other student is allowed during the exam. You will have 70 minutes from the start of the exam to complete the exam, followed by ~5 minutes to scan and upload your exam answer sheets to Gradescope."

Bold paragraph: "NOTES: Unless otherwise stated, you may assume all numerical quantities given in the exam problems are known to 3 significant figures, and calculate your answers accordingly. You must show all of your work to receive credit. If you need to make an assumption to answer a question, state it explicitly."

Centered, large bold: "ONLY THE FRONT SIDE OF EACH SHEET WILL BE GRADED."

### Problem 1 [25 points total]

1. [25 points total] Answer the questions below. Each should require a few sentences or relatively small amount of math at most. You may also include a sketch/picture if necessary.

(a) [6 points] Explain why, in the ideal op amp model, it is necessary to assume (i) that the op-amp output resistance $R_o$ is zero, and (ii) that the op-amp input resistance $R_i$ is infinite.
**Answer (typed, bold):** (i) output can source any current without changing $v_o$; (ii) $i_n = i_p = 0$.

(b) [6 points] Consider the voltage across an inductor, $v_L$, and the current through the same inductor, $i_L$. Which, if any, of these must be continuous, and why?
**Answer (typed, bold):** $i_L$ continuous since $v_L = L(di_L/dt)$; $v_L$ can be discontinuous.

(c) [6 points] Consider a passive load circuit with complex equivalent impedance $Z_L = R_L + jS_L$ for which the voltage and current are, respectively $v_L(t) = V_L\cos(\omega t + \phi_v)$ and $i_L(t) = I_L\cos(\omega t + \phi_i)$, where $V_L$ and $I_L$ are real and positive. If $\phi_v = \phi_i + 90^\circ$, is $Z_L$ purely resistive, capacitive, or inductive? Explain your answer.
**Answer (typed, bold):** inductive

(d) [7 points] Consider again a passive load circuit for which the voltage and current are, respectively, $v_L(t) = V_L\cos(\omega t + \phi_v)$ and $i_L(t) = I_L\cos(\omega t + \phi_i)$. Show, working purely in the time domain, that the average power dissipated in the load is zero if $\phi_v = \phi_i - 90^\circ$.
**Answer (typed, bold):** Define $P_{avg}$ as integral of instantaneous power over one period and integrate explicitly

### Problem 2 [25 points total] (begins on page 1, continues on page 2)

2. [25 points total] Consider Circuit SE1-2 at right. The time-varying signals $v_s(t)$ and $v_o(t)$ are described, when applicable, by the corresponding phasors $\mathbf{V}_s$ and $\mathbf{V}_o$, respectively. Assume $R_1 = 20$ k$\Omega$, $R_2 = 40$ k$\Omega$, and $C = 0.1\ \mu$F. All numerical values given in this problem are exact, and $V_s$ below is a real, positive constant, in volts.. [sic — two periods as printed]

**Figure: Circuit SE1-2** (right margin). Voltage source $v_s(t)$ (circle, $+$ on top, $-$ on bottom) with its bottom terminal grounded (ground symbol). From the source top, resistor $R_1$ runs horizontally to the op-amp inverting input node (the upper input of the triangle, marked "$-$"). The non-inverting input (lower, marked "$+$") is tied to ground (ground symbol). Two feedback branches run from the output node back to the inverting-input node, drawn stacked above the op amp: upper branch resistor $R_2$, lower branch capacitor $C$ (so $R_2 \parallel C$ between output and inverting input). Supply pins labeled "$+8$ V" (top of triangle) and "$-8$ V" (bottom of triangle). Output node at the right drawn as an open-circle terminal labeled $v_o(t)$. Caption "Circuit SE1-2".

(a) Suppose $v_s(t) = V_s$, i.e., $\omega = 0$. Calculate $v_o(t)$ in terms of $V_s$. For what range of values of $V_s$ is the op amp in its linear region of behavior?
**Answer (typed, bold):** $v_o = -2V_s$. $-4$V to $+4$V

## Page 2

(b) Now suppose $v_s(t) = V_s\cos(250t)$. Use phasor analysis to solve for the phasor $\mathbf{V}_o$ in terms of the phasor $\mathbf{V}_s$, and then solve for $v_o(t)$.
**Answer (typed, bold):** $\mathbf{V}_o = 1.414e^{j135^\circ}\mathbf{V}_s$, $v_o(t) = 1.414V_s\cos(250t + 135^\circ)$

(c) Now suppose $v_s(t) = 2u(t)$ V where $u(t)$ is the unit step function. Solve for $v_o(t)$ for all $t$ ($-\infty < t < \infty$).
**Answer (typed, bold):** $v_o(t) = 0$ for $t < 0$; $v_o(t) = 0$ for $t = 0$; $v_o(t) = -4\left(1 - e^{-250t}\right)$ V for $t > 0$.

### Problem 3 [25 points total]

3. [25 points total] Consider the Circuit SE1-3 at right, with $v_s(t) = 18\cos(\omega t + 30^\circ)$ V, corresponding to the phasor $\mathbf{V}_s$, and $\omega = 1000$ rad/s. Assume all numerical values given in this problem are exact.

**Figure: Circuit SE1-3** (right margin). Voltage source $v_s(t)$ (circle, $+$ on top) at the far left, bottom terminal on the bottom rail. Top rail from the source: resistor $50\ \Omega$, then a pair of open-circle terminals (top and bottom) marking the source/load boundary, with current $i_s(t)$ drawn as an arrow pointing right above the top terminal. To the right of the boundary, the top node feeds two vertical branches to the bottom rail: (1) capacitor "$C = 10\mu$F"; (2) resistor $100\ \Omega$ in series with inductor $100$ mH (resistor above inductor). At the far right, open-circle terminals "$+$" (top) and "$-$" (bottom) across the right-hand branch labeled $v_o(t)$ — i.e. $v_o$ is the voltage across the whole load (top node to bottom rail). Two braces under the circuit: "source" under the left part (source and $50\ \Omega$), "load" under the right part ($C$, $100\ \Omega$, $100$ mH). Caption "Circuit SE1-3".

(a) Using phasor analysis, solve for $v_o(t)$ for all $t$ ($-\infty < t < \infty$).
**Answer (handwritten, pasted scan, boxed):** $v_o(t) = 14.12\cos(1000t + 18.69^\circ)$ V

(b) Using phasor analysis, solve for $i_s(t)$ for all $t$ ($-\infty < t < \infty$).
**Answer (handwritten, pasted scan):** $i_s(t) = 99.85\cos(1000t + 63.69^\circ)$ mA

(c) Calculate the average power absorbed by the load portion of the circuit.
**Answer (typed, bold):** $0.4985$ W or $0.4985$ V*A

(d) Now assume that the value of the capacitor $C$ can vary. Determine the value of $C$ that makes the load impedance purely real. Then calculate the average power absorbed by the load portion of the circuit.
**Answer (typed, bold):** $C = 5\mu$F; $P_{avg} = 0.5184$ W or $0.5184$ V*A

### Problem 4 [25 points total] (begins on page 2, continues on page 3)

4. [25 points total] Consider Circuit SE1-4 shown at right. The voltage sources $v_s(t)$ and $v_p(t)$ are given by
$$v_s(t) = 10u(t)\ \text{V where } u(t) = \begin{cases} 0 & t < 0 \\ 1 & t \ge 0 \end{cases},$$
$$v_p(t) = 4\ \text{V}.$$
The switch is closed for $t < 0$, opens at $t = 0$, and remains open for all times $t > 0$. In this problem, assume all numerical values given are exact.

**Figure: Circuit SE1-4** (right margin). A rectangular loop with a middle horizontal branch. Top wire: voltage source $v_p(t)$ (circle, "$+\ -$" with $+$ on the left, $-$ on the right) between the top-left corner and a switch at the top-right; the switch is drawn as an open blade with a curved arrow, labeled "$t = 0$", and connects to the top-right corner. Middle horizontal branch (from the left vertical wire to the right vertical wire): resistor $20\ \Omega$ then inductor $20$ mH in series, with current $i(t)$ drawn as an arrow pointing right at the inductor's right end. Left vertical wire, below the middle branch: voltage source $v_s(t)$ (circle, $+$ on top). Right vertical wire, below the middle branch: capacitor $50\ \mu$F with "$+$" above and "$-$" below, voltage $v_c(t)$. Bottom wire closes the loop. Thus for $t < 0$ ($v_s = 0$, switch closed) $v_p$ is in parallel with the $R$–$L$ branch and $C$ hangs off the right node; for $t \ge 0$ (switch open, $v_s = 10$ V) the circuit is a single series loop $v_s \to 20\ \Omega \to 20\ \text{mH} \to C$. Caption "Circuit SE1-4".

(a) Calculate (giving numerical values for each) the following initial conditions at $t = 0$:
$$i(0),\ v_c(0),\ \frac{di}{dt}\Big|_{t=0},\ \frac{dv_c}{dt}\Big|_{t=0}.$$
**Answer (handwritten, pasted scan, four boxed items):** $i(0) = 0.2$ A; $v_C(0) = -4$ V; $500\ \text{A/s} = \dfrac{di}{dt}\Big|_{t=0}$; $\dfrac{dv_C}{dt}\Big|_{t=0} = 4\times10^3$ V/s

(b) Derive a second-order differential equation for $v_c(t)$ valid for $t \ge 0$. Give numerical values for, as needed, all the constant coefficients and any constant inhomogeneous term in your equation.
**Answer (handwritten, pasted scan):**
$$\frac{d^2v_C}{dt^2} + 10^3\frac{dv_C}{dt} + 10^6 v_C = 10^7$$

## Page 3

(c) Solve the differential equation you derived in part (b), and thereby obtain an expression for $v_c(t)$ valid for $t \ge 0$. Use the numerical values given for all circuit parameters.
**Answer (handwritten, pasted scan, boxed):**
$$v_C(t) = -e^{-500t}\left[14\cos(866t) + 3.464\sin(866t)\right] + 10\ \text{V}$$

(d) For $t > 0$, when the energy stored in the capacitor in this circuit is maximized, the energy stored in the inductor in the circuit is minimized. Explain or show why this is the case. *Hint:* recall that capacitors and inductors store energy in the form of electric and magnetic fields, respectively.
**Answer (typed, bold):** Capacitor energy maximized when $|v_C|$ maximized since that maximizes electric field, and inductor energy is maximized when $|i_L|$ is maximized since that maximizes magnetic field. When $|v_C|$ is maximized, we know $dv_C/dt = 0$, so $i(t) = 0$ as well. Thus, $|i_L|$ is maximized when $|v_C|$ is minimized.

BONUS [+5 points]:

(e) At what time (give a numerical value) does the charge magnitude on the capacitor reach its maximum?
**Answer (handwritten, pasted scan):** $t = 3.303\times10^{-3}$ s

Rest of page blank.

## Transcriber's verification (not in the source)

All numeric answers re-derived and consistent with the printed circuits: 3(a) $Z_{load} = (-j100)\parallel(100 + j100) = 100 - j100\ \Omega$, $\mathbf{V}_o = \mathbf{V}_s Z_{load}/(Z_{load} + 50) = 14.12\angle18.69^\circ$ V; 3(b) $\mathbf{I}_s = 18\angle30^\circ/(150 - j100) = 0.09985\angle63.69^\circ$ A; 3(c) $\tfrac12|\mathbf{I}_{RL}|^2(100) = \tfrac12(14.12/141.4)^2(100) = 0.4985$ W; 3(d) $\text{Im}(j\omega C + 1/(100 + j100)) = 0 \Rightarrow C = 5\ \mu$F, $Z_{load} = 200\ \Omega$, $P = \tfrac12(18/250)^2(200) = 0.5184$ W. 4(a) for $t<0$: $i = v_p/R = 4/20 = 0.2$ A, $v_C = -v_p = -4$ V (the $+$ of $v_p$ is at the $v_s$-side node, which is at 0 V); at $t = 0^+$: $L\,di/dt = 10 - 20(0.2) - (-4) = 10 \Rightarrow 500$ A/s, $dv_C/dt = i/C = 0.2/50\mu = 4000$ V/s. 4(b) series KVL $LC v_C'' + RC v_C' + v_C = 10$ with $R/L = 1000$, $1/LC = 10^6$. 4(c) $\alpha = 500$, $\omega_0 = 1000$, $\omega_d = \sqrt{10^6 - 2.5\times10^5} = 866.0$ rad/s, underdamped; $A = -14$ from $v_C(0) = -4$, $B = -3.464$ from $-500A + 866B = 4000$. 4(e) $dv_C/dt = 0 \Rightarrow \tan(866t) = -4000/13856 \Rightarrow 866t = 2.8606 \Rightarrow t = 3.303$ ms (first peak, $v_C \approx 12.39$ V).

## Index terms

Semester Exam 1, SE1 F26, 07 October 2026, answer key, short answers, Problem 1, Problem 1a, Problem 1b, Problem 1c, Problem 1d, Problem 2, Problem 2a, Problem 2b, Problem 2c, Problem 3, Problem 3a, Problem 3b, Problem 3c, Problem 3d, Problem 4, Problem 4a, Problem 4b, Problem 4c, Problem 4d, Problem 4e, bonus, Circuit SE1-2, Circuit SE1-3, Circuit SE1-4, ideal op amp model, output resistance R_o = 0, input resistance R_i = ∞, i_n = i_p = 0, inductor current continuity, v_L = L di_L/dt, inductor voltage discontinuous, Z_L = R_L + jS_L, φ_v = φ_i + 90°, inductive, φ_v = φ_i − 90°, average power, instantaneous power, integral over one period, time domain, inverting amplifier, R_1 = 20 kΩ, R_2 = 40 kΩ, C = 0.1 µF, ±8 V supplies, v_o = −2V_s, linear range −4 V to +4 V, ω = 250 rad/s, V_o = 1.414e^{j135°}V_s, 1.414 V_s cos(250t + 135°), unit step 2u(t), v_o = −4(1 − e^{−250t}), v_s = 18 cos(ωt + 30°), ω = 1000 rad/s, 50 Ω, C = 10 µF, 100 Ω, 100 mH, source, load, v_o = 14.12 cos(1000t + 18.69°), i_s = 99.85 cos(1000t + 63.69°) mA, 0.4985 W, purely real load impedance, C = 5 µF, 0.5184 W, v_s = 10u(t), v_p = 4 V, switch opens at t = 0, 20 Ω, 20 mH, 50 µF, i(0) = 0.2 A, v_C(0) = −4 V, di/dt = 500 A/s, dv_C/dt = 4×10³ V/s, second-order ODE, v_C'' + 10³ v_C' + 10⁶ v_C = 10⁷, underdamped, α = 500, ω_d = 866, v_C(t) = −e^{−500t}[14 cos(866t) + 3.464 sin(866t)] + 10, capacitor energy, inductor energy, electric field, magnetic field, dv_C/dt = 0, charge maximum, t = 3.303×10⁻³ s
