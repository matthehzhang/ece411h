---
course: ECE 411H
kind: problem-video
source: Problem Solving Videos/Ulaby 12.37.pdf
source_pages: 5
author: Prof. Ed Yu
unit: exam2
topics: [laplace-circuit-analysis, s-domain, nonzero-initial-conditions, capacitor-initial-voltage-source, node-voltage, kcl, cramers-rule, current-source, exponential-input, partial-fractions, real-poles, table-12-2, ulaby-12.37]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
deepgram_transcript: deepgram/Ulaby_12.37.deepgram.txt
deepgram_paragraphs: deepgram/Ulaby_12.37.deepgram.md
---

# Ulaby 12.37 — Laplace circuit analysis with a nonzero initial capacitor voltage

**Summary.** Prof. Yu works Ulaby/Maharbiz/Furse Problem 12.37 (circuit of Fig. P12.36): a current source $i_s(t)$ that is $6$ A for $t\le 0$ and $6e^{-2t}$ A for $t\ge 0$ feeds $R_1 = 10\,\Omega$ (shunt), a series capacitor $C$, then $R_2 = 5\,\Omega$ and $L = 0.6196$ H (both shunt), with $LC = 1/15$ s; find $i_L(t)$ for $t\ge 0$. Because the source is nonzero before $t=0$, $v_C(0^-) = (6\,\text{A})(R_1) = 60$ V (and $i_L(0^-)=0$), so the s-domain circuit needs a $60/s$ voltage source in series with the capacitor impedance $1/sC$. Node-voltage KCL at $V_1$ and $V_2$, Cramer's rule for $V_2$, then $I_L = V_2/(sL)$; after substituting $I_s = 6/(s+2)$ and numbers ($C = 0.1076$ F), the $s$-terms in the numerator cancel and $I_L(s) = -64.56/[(s+2)(s+1)(s+5)]$, three real simple poles. Residues $21.52$, $-16.14$, $-5.38$ give $i_L(t) = [-16.14e^{-t} + 21.52e^{-2t} - 5.38e^{-5t}]u(t)$ A. Exam relevance: the one Chapter 12 video showing how to place the initial-condition source for a capacitor and solve a two-node s-domain circuit by KCL/Cramer's rule.

> **Audio transcript (Deepgram nova-3, ECE 411 keyterms, timestamped):** `deepgram/Ulaby_12.37.deepgram.txt` ; paragraph form: `deepgram/Ulaby_12.37.deepgram.md`. Fresh ASR of the video audio; where it disagrees with the Narration section (built from the published auto-captions), prefer this file and the handwritten page.

## Problem statement

***12.37** Given the current-source waveform displayed in Fig. P12.37, determine $i_L(t)$ in the circuit of Fig. P12.36, given that $R_1 = 10\,\Omega$, $R_2 = 5\,\Omega$, $L = 0.6196$ H, and $LC = (1/15)$ s.

**Figure P12.36 (textbook image), "Circuit for Problems 12.36 and 12.37":** Current source $i_s(t)$ (circle with upward arrow) on the far left between the bottom rail and the top-left node. From the top-left node: $R_1$ hangs down to the bottom rail (shunt); along the top wire, capacitor $C$ in series to the next node; from that node $R_2$ hangs down to the bottom rail (shunt); the top wire continues to the right (current $i_L$ marked with a rightward arrow) to inductor $L$, which hangs down to the bottom rail on the far right.

**Figure P12.37 (textbook image), "Waveform for Problem 12.37":** $i_s(t)$ vs $t$: constant at $6$ A for $t<0$; at $t=0$ it begins an exponential decay labeled $6e^{-2t}$ toward zero.

## Page 1

Header (typed): "Ulaby 12.37". Textbook problem and figure images (as above). Handwritten title, underlined: **Example: circuit analysis using Laplace Transforms with non-zero initial conditions.**

**Figure (handwritten redraw):** Current source $i_s(t)$ (circle, arrow up) at far left; $R_1$ (zigzag) shunt to the bottom rail; capacitor $C$ (plates) in series along the top; $R_2$ (zigzag) shunt; "$\to i_L(t)$" arrow along the top toward $L$ (coil) shunt at the far right; bottom rail common.

$R_1 = 10\,\Omega$, $R_2 = 5\,\Omega$, $L = 0.6196\,\text{H}$, $LC = \dfrac{1}{15}\,\text{s}$

**Figure (handwritten plot):** $i_s(t)$ vs $t$: blue curve flat at $6$ A for $t<0$, then decaying from $t=0$, labeled "$6e^{-2t}$"; "0" marked at the origin.

$$i_s(t) = \begin{cases} 6\,\text{A} & t \le 0 \\ 6e^{-2t}\,\text{A} & t \ge 0 \end{cases}$$

Solve for $i_L(t)$ for $t \ge 0$.

1) Determine initial conditions for $t = 0^-$:

$C \to$ open circuit, $L \to$ short circuit, $i_s = 6$ A.

**Figure ($t = 0^-$ circuit):** $6$ A current source (arrow up) at left; $R_1$ shunt; an open gap along the top where $C$ was, with "$+\ v_C\ -$" marked across it; $R_2$ shunt; "$\to i_L$" along the top to the right; a short (plain wire, drawn as an open-circle-ended vertical segment closed by wire) at the far right where $L$ was.

$$i_L(0^-) = 0$$
$$v_C(0^-) = (6\,\text{A})(R_1) = 60\,\text{V}.$$

(Page bottom: start of "2) Transform circuit to s-domain for $t \ge 0$:" clipped; continued on page 2.)

## Page 2

2) Transform circuit to s-domain for $t \ge 0$:

**Figure (s-domain circuit):** Current source $I_s(s)$ (arrow up) at far left; node $V_1$ at the top-left; $R_1$ (zigzag) from $V_1$ down to the bottom rail; along the top from $V_1$: capacitor impedance $\dfrac{1}{sC}$ (plates), then in series a voltage source (circle with "+ −", + on the left/capacitor side, − on the right) labeled $\dfrac{v_C(0^-)}{s} = \dfrac{60}{s}$; then node $V_2$; $R_2$ (zigzag) from $V_2$ down to the bottom rail; "$\to I_L(s)$" along the top from $V_2$ to $sL$ (coil) down to the bottom rail at the far right. Bottom rail labeled $V_0 = 0$.

$i_s(t) = 6e^{-2t}u(t) \leftrightarrow I_s(s) = \dfrac{6}{s+2}$ from Ulaby et al., Table 12-2.

3) Analyze circuit in s-domain, solve for $I_L(s)$ and $i_L(t)$:

KCL @ $V_1$:
$$-I_s + \frac{V_1}{R_1} + \frac{V_1 - \left(V_2 + \frac{60}{s}\right)}{\frac{1}{sC}} = 0$$
$$\left(\frac{1}{R_1} + sC\right)V_1 - sC\,V_2 = I_s + 60C\quad\text{(green underline)}$$

KCL @ $V_2$:
$$\frac{\left(V_2 + \frac{60}{s}\right) - V_1}{\frac{1}{sC}} + \frac{V_2}{R_2} + \frac{V_2}{sL} = 0$$
$$-sC\,V_1 + \left(\frac{1}{R_2} + sC + \frac{1}{sL}\right)V_2 = -60C\quad\text{(green underline)}$$

Solve for $V_2$ using Cramer's Rule, then $I_L(s) = \dfrac{V_2}{sL}$:
$$\left(\frac{1}{R_1} + sC\right)V_1 - sC\,V_2 = I_s + 60C$$
$$-sC\,V_1 + \left(\frac{1}{R_2} + sC + \frac{1}{sL}\right)V_2 = -60C$$

$$\Rightarrow V_2 = \frac{\begin{vmatrix} \frac{1}{R_1} + sC & I_s + 60C \\ -sC & -60C \end{vmatrix}}{\begin{vmatrix} \frac{1}{R_1} + sC & -sC \\ -sC & \frac{1}{R_2} + sC + \frac{1}{sL} \end{vmatrix}} = \frac{-\left(\frac{1}{R_1} + sC\right)60C + (I_s + 60C)sC}{\left(\frac{1}{R_1} + sC\right)\left(\frac{1}{R_2} + sC + \frac{1}{sL}\right) - s^2C^2}$$

(The determinant line is clipped at the page bottom; it is repeated at the top of page 3.)

## Page 3

$$\Rightarrow V_2 = \frac{\begin{vmatrix} \frac{1}{R_1} + sC & I_s + 60C \\ -sC & -60C \end{vmatrix}}{\begin{vmatrix} \frac{1}{R_1} + sC & -sC \\ -sC & \frac{1}{R_2} + sC + \frac{1}{sL} \end{vmatrix}} = \frac{-\left(\frac{1}{R_1} + sC\right)60C + (I_s + 60C)sC}{\left(\frac{1}{R_1} + sC\right)\left(\frac{1}{R_2} + sC + \frac{1}{sL}\right) - s^2C^2}$$

$$= \frac{-\frac{1}{R_1}60C + sI_sC}{\frac{1}{R_1R_2} + \left(\frac{1}{R_1} + \frac{1}{R_2}\right)sC + \frac{1}{sLR_1} + \frac{C}{L}}\ ;\ \text{multiply by } \frac{LR_1R_2}{LR_1R_2}$$

$$= \frac{-60LR_2C + sI_sR_1R_2LC}{L + s(R_1+R_2)LC + \frac{R_2}{s} + R_1R_2C}$$

$$I_L(s) = \frac{V_2}{sL} = \frac{-60R_2C + sI_sR_1R_2C}{(R_1+R_2)LCs^2 + (R_1R_2C + L)s + R_2}\ ;\quad I_s = \frac{6}{s+2}$$

$$I_L(s) = \frac{R_1R_2C\frac{6s}{s+2} - 60R_2C}{(R_1+R_2)LCs^2 + (R_1R_2C+L)s + R_2}$$
$$= \frac{6R_1R_2Cs - 60R_2C(s+2)}{(s+2)\left[(R_1+R_2)LCs^2 + (R_1R_2C+L)s + R_2\right]}\ ;\ LC = \frac{1}{15} \Rightarrow C = \frac{1}{15L}$$
$$\Rightarrow C = \frac{1}{15(0.6196)} = 0.1076\,\text{F}$$

$$= \frac{6(10)(5)Cs - 60(5)Cs - 120(5)(0.1076)}{(s+2)\left[(10+5)\frac{1}{15}s^2 + \left((10)(5)(0.1076) + 0.6196\right)s + 5\right]}$$
(red strokes through "$6(10)(5)Cs$" and "$60(5)Cs$": these two terms cancel)

$$I_L(s) = \frac{-64.56}{(s+2)(s^2 + 6s + 5)}$$

$I_L(s)$ has poles at $s = -2$, $s^2 + 6s + 5 = (s+1)(s+5) = 0 \Rightarrow s = -1, -5$

$$\Rightarrow I_L(s) = \frac{-64.56}{(s+2)(s+1)(s+5)}$$

## Page 4

$$\Rightarrow I_L(s) = \frac{-64.56}{(s+2)(s+1)(s+5)}$$
(numerator clipped at page top)

Partial fraction expansion:
$$I_L(s) = \frac{k_1}{s+2} + \frac{l_1}{s+1} + \frac{m_1}{s+5}$$

$$k_1 = \left[(s+2)I_L(s)\right]\Big|_{s=-2} = \frac{-64.56}{(-2+1)(-2+5)} = 21.52$$
$$l_1 = \left[(s+1)I_L(s)\right]\Big|_{s=-1} = \frac{-64.56}{(-1+2)(-1+5)} = -16.14$$
$$m_1 = \left[(s+5)I_L(s)\right]\Big|_{s=-5} = \frac{-64.56}{(-5+2)(-5+1)} = -5.38$$

$$I_L(s) = \frac{21.52}{s+2} - \frac{16.14}{s+1} - \frac{5.38}{s+5}$$

Compute inverse LT:
From Ulaby et al., Table 12-2, we have:
$$e^{-at}u(t) \leftrightarrow \frac{1}{s+a}$$

$$\Rightarrow \boxed{i_L(t) = \left[-16.14e^{-t} + 21.52e^{-2t} - 5.38e^{-5t}\right]u(t)\ \text{A}}$$

**Key points:** (underlined)

(i) major steps are (1) determine initial conditions $i_L(0^-)$, $v_C(0^-)$, (2) transform circuit to s-domain, (3) analyze in s-domain, (4) inverse transform back to time domain.

(ii) here, initial conditions ($v_C(0^-) \ne 0$) required addition of (continues on page 5)

## Page 5

(ii) here, initial conditions ($v_C(0^-) \ne 0$) required addition of a voltage source in series with the capacitor in the s-domain.

(iii) partial fraction expansion for $I_L(s)$ made inverse LT very straightforward.

(iv) accuracy + proficiency in complex algebra are important.

(Rest of page blank.)

## Narration transcript

Cleaned from `Problem Solving Videos/Ulaby 12.37 captions.vtt`: timestamps and cue numbers stripped, fragments merged into sentences, auto-caption mishearings corrected ("you'll be" → Ulaby, "polls" → poles, "applause transform" → Laplace transform, "Isobel/I sub L" → $i_L$, "Kcl/Caseyl" → KCL, "Kramer's" → Cramer's, "9 0 initial conditions" → nonzero initial conditions, "Henry's" → henrys, "you'll be at all" → Ulaby et al., "estimate/est domain" → $s$ domain), verbal fillers trimmed. Content is otherwise complete.

This is Ulaby problem 12.37, and this is an example of circuit analysis using Laplace transforms, but in this case it turns out that we will have nonzero initial conditions that will require us to introduce an additional source component in the circuit when we transform to the $s$ domain. That comes about because we have nonzero current from this current source for $t$ less than zero. So this is circuit analysis using Laplace transforms with, we'll call them, nonzero initial conditions.

Let's get started. We will, as usual, redraw the circuit. We have a current source and then a resistor; the current source is $i_s(t)$; the resistor here is $R_1$; we have a capacitor; then we have another resistor; the capacitor is $C$; and then we have an inductor all the way over on the right. The inductance is $L$, and the current that we want to solve for is the current through the inductor, $i_L(t)$. The component values are that $R_1$ is $10\,\Omega$, $R_2$ is $5\,\Omega$, the inductance $L$ is $0.6196$ henrys, and $LC$ is one-fifteenth of a second, from which we can deduce what $C$ is as well. This current source $i_s(t)$ is $6$ amps — I'll draw this in blue — $6$ amps up until $t = 0$, and then decreases exponentially: $6e^{-2t}$. This is $t = 0$. So $i_s(t)$ analytically is $6$ amps for $t \le 0$, and $6e^{-2t}$ amps for $t \ge 0$. What we want to do is solve for $i_L(t)$ for $t \ge 0$, and we're going to do this using Laplace transforms.

The first step is to determine the initial conditions for $t = 0^-$ — just before $t = 0$ — specifically for the current through the inductor and the voltage across the capacitor. As usual, we take the capacitor to behave as an open circuit and the inductor to behave as a short circuit, and the current source for $t < 0$ is $6$ amps. We'll redraw the circuit in this configuration, the $t = 0^-$ configuration: this is the resistor $R_1$, the current source is just $6$ amps, the capacitor is an open circuit and the voltage across it is $v_C$, this resistor is $R_2$, and the inductor is a short circuit; we have a current $i_L$ for the inductor. We can see that for the inductor the current has to be zero for $t = 0^-$: this is an open circuit over here, so there's no current along this branch; the voltage across $R_2$ has to be zero because it's short-circuited, so there's no current through $R_2$; and so by KCL at this node $i_L$ has to be zero as well. The voltage across the capacitor at $t = 0^-$ is the voltage across the resistor $R_1$, because this terminal is one terminal of $R_1$ and this terminal, through this connection, is the opposite terminal of $R_1$. So the voltage across the capacitor is the same as the voltage across $R_1$ in this situation, and that voltage is just the current, $6$ amps, times the resistance $R_1$, because no current is going to flow this way — the entire $6$ amps has to flow through the resistor. So $v_C(0^-) = 6\,\text{A}\times R_1$; $R_1 = 10\,\Omega$, so this is $60$ volts. Now we have a nonzero value for $v_C$ at $0^-$, and that means that when we transform the circuit to the $s$ domain, we will need to include a voltage source to account for that.

So now we want to transform the circuit to the $s$ domain for $t \ge 0$. Let's draw what this will look like. We have our current source — now that's $I_s$ as a function of $s$. Then we have our resistor $R_1$. Then we have our capacitor, but in series with the capacitor we have a voltage source to account for the nonzero value of $v_C$ at $0^-$. Then we have our resistor $R_2$, and then our inductor. The capacitor has impedance in the $s$ domain $1/(sC)$. The voltage source has a value $v_C(0^-)/s$, which is $60/s$. The inductor has impedance $sL$. We're trying to solve for this current $I_L(s)$. The current source in the $s$ domain is as follows: in the time domain $i_s(t)$ for $t > 0$ is $6e^{-2t}u(t)$, and that forms a Laplace transform pair with $I_s(s)$ — this is a standard form — $6/(s+2)$. We get that from Ulaby et al. Table 12-2 of common Laplace transform pairs. So this is now the circuit in the $s$ domain.

What we want to do next is analyze this circuit in the $s$ domain and solve for $I_L(s)$, and then once we have that we compute the inverse Laplace transform to get $i_L(t)$, which is what we're actually trying to solve for. To analyze this circuit we'll do a node voltage analysis. We'll take this bottom node to be our reference node with zero voltage, and then we have two voltages, $V_1$ and $V_2$, at the two extraordinary nodes. As usual, we apply KCL at each of these nodes.

KCL at node $V_1$, the one on the left: we take the sum of the outgoing currents to be zero. The current going out to the left is $-I_s$, because it's $+I_s$ coming in. The current flowing down through $R_1$ is $V_1/R_1$. The current flowing to the right is the voltage across the capacitor — which is $V_1$ minus the quantity $V_2 + 60/s$ — divided by the impedance of the capacitor, $1/(sC)$. Those three currents have to add up to zero. If we group together our unknown variables: for $V_1$ we have $1/R_1$ from this term, and $V_1$ over $1/(sC)$, which is $sC$ times $V_1$ — so $\left(\frac{1}{R_1} + sC\right)V_1$. For $V_2$ we have $-V_2/(1/(sC))$, which is $-sC\,V_2$. That's equal to $I_s$ (taking $-I_s$ to the right, which changes the sign) plus — the $60/s$ over $1/(sC)$ on the left becomes $+60C$ on the right. So this is the first equation for our unknown node voltages $V_1$ and $V_2$.

Now we apply KCL at node $V_2$, again taking the sum of the outgoing currents to be zero. The current flowing out to the left is the voltage going in the left direction across the capacitor, $V_2 + 60/s - V_1$, divided by the impedance of the capacitor, $1/(sC)$. Then the current going down, $V_2/R_2$. Then the current going to the right, $V_2/(sL)$. Those have to add up to zero. Grouping unknowns: for $V_1$ we only have the one term, $-sC\,V_1$. For $V_2$ we have $1/R_2$, then $V_2/(1/(sC))$ which is $sC\,V_2$, and then $1/(sL)$ times $V_2$. On the right-hand side, the term $60/s$ divided by $1/(sC)$ on the left becomes $-60C$ on the right. So this is our second equation.

Now we have two equations for our two unknown node voltages $V_1$ and $V_2$. If we look at our circuit, we actually only need to solve for the voltage $V_2$, and then the current $I_L$ is going to be $V_2/(sL)$. So what we want to do is solve the two equations I've underlined in green for $V_2$. We'll do this using Cramer's rule, and then once we have $V_2$, $I_L(s) = V_2/(sL)$. Let's write down the two equations: $\left(\frac{1}{R_1} + sC\right)V_1 - sC\,V_2 = I_s + 60C$, and $-sC\,V_1 + \left(\frac{1}{R_2} + sC + \frac{1}{sL}\right)V_2 = -60C$. Cramer's rule says that $V_2$ is the determinant of the matrix of coefficients with the coefficients of $V_2$ replaced by the column vector of constants, divided by the determinant of the matrix of coefficients. So we have the determinant of $\begin{pmatrix} \frac{1}{R_1}+sC & I_s+60C \\ -sC & -60C \end{pmatrix}$, divided by the determinant of $\begin{pmatrix} \frac{1}{R_1}+sC & -sC \\ -sC & \frac{1}{R_2}+sC+\frac{1}{sL} \end{pmatrix}$.

We want to compute these determinants. For a $2\times 2$ matrix the determinant is the product of the main-diagonal terms minus the product of the opposite-diagonal terms. So in the numerator, from the main diagonal we have $-\left(\frac{1}{R_1}+sC\right)60C$, and minus the opposite diagonal gives $+(I_s+60C)sC$. In the denominator, from the main diagonal we have $\left(\frac{1}{R_1}+sC\right)\left(\frac{1}{R_2}+sC+\frac{1}{sL}\right)$, and then $-s^2C^2$.

Now we work this out and simplify. In the numerator, the first term is $-\frac{1}{R_1}60C$. Then we have $-sC\cdot 60C$, but that cancels with the $+sC\cdot 60C$. So the only other term is $+sI_sC$. In the denominator we have $\frac{1}{R_1R_2}$; then $\frac{1}{R_1}sC$, but we also get another term $\frac{1}{R_2}sC$, so it's $\left(\frac{1}{R_1}+\frac{1}{R_2}\right)sC$; then $\frac{1}{R_1}\cdot\frac{1}{sL}$, so $+\frac{1}{sLR_1}$; we've already taken care of $sC\cdot sC$, which cancels with the $-s^2C^2$; and the last term is $sC\cdot\frac{1}{sL}$, which is $+\frac{C}{L}$.

Now we proceed by multiplying this by $\frac{LR_1R_2}{LR_1R_2}$; that'll allow us to get rid of some of these fractions. In the numerator, from the first term we get $-60LR_2C$, and then $+sI_sR_1R_2LC$. In the denominator, $LR_1R_2\cdot\frac{1}{R_1R_2}$ is just $L$; from the second term in the parentheses we get $(R_1+R_2)$ times $sLC$, so $s(R_1+R_2)LC$; from the next term we get $\frac{R_2}{s}$; and from the last term we get $R_1R_2C$. So that's $V_2$.

Then $I_L$ is $V_2/(sL)$. We take this expression and divide by $sL$. When we divide by $L$ we get rid of the $L$ in the numerator, and the $s$ multiplies through the denominator. So in the numerator we get $-60R_2C + sI_sR_1R_2C$, and in the denominator we have $(R_1+R_2)LCs^2$ (because we're multiplying through by $s$), then $(R_1R_2C + L)s$ from the constant terms, and from the $R_2/s$ we get $+R_2$.

The last substitution is that $I_s$ is $6/(s+2)$, as we saw earlier — that corresponds to the exponentially decaying current in the time domain. We substitute that in for $I_s$. So $I_L(s)$ is — writing this term first — $R_1R_2C\cdot\frac{6s}{s+2} - 60R_2C$, and in the denominator still $(R_1+R_2)LCs^2 + (R_1R_2C+L)s + R_2$. Now we multiply the numerator and the denominator by $(s+2)$. What we get is $6R_1R_2Cs$ from the first term, and then $-60R_2C(s+2)$. In the denominator we have $(s+2)$ times our original denominator, $(R_1+R_2)LCs^2 + (R_1R_2C+L)s + R_2$.

Now we can start plugging in numerical values, and for that we need the numerical value for $C$. What we were given in the problem was $LC = 1/15$, so $C = \frac{1}{15L}$, and $L$ was $0.6196$. So the capacitance is $0.1076$. Substituting: in the numerator we get $6\times 10\times 5\times C\times s$ — $R_1$ is $10$, $R_2$ is $5$, and we'll just keep this as $C$ for now — then $-60\times 5\times C\times s$, and finally, from the $2$ inside the parentheses, $-120\times 5\times C$, where now we substitute in $0.1076$. In the denominator we get $(s+2)$, then $R_1+R_2 = 10+5$, times $LC = \frac{1}{15}$, times $s^2$; then $R_1R_2C + L = (10)(5)(0.1076) + 0.6196$, times $s$; and finally $+R_2 = 5$.

Now if we look at this, we can see that $6\times 10 = 60$, so we have $60\times 5\times C\times s$ here and $-60\times 5\times C\times s$ there, so these two cancel each other out. All we're left with in the numerator is $-120\times 5\times 0.1076$, and that turns out to be $-64.56$. In the denominator we have $(s+2)$, then $(10+5)/15 = 1$ times $s^2$; then $10\times 5\times 0.1076 + 0.6196$ turns out to be $6$, times $s$; and then $+5$. So numerically this turns out to be relatively simple. So $I_L(s) = \dfrac{-64.56}{(s+2)(s^2+6s+5)}$.

Now all we need to do is compute the inverse Laplace transform of $I_L(s)$, and to do that we want to identify its poles. $I_L(s)$ has poles at $s=-2$ and where $s^2+6s+5$ — which we can factor easily as $(s+1)(s+5)$ — is equal to zero, so we also have simple poles at $s=-1$ and $s=-5$. We can write $I_L(s)$ in factored form as $\dfrac{-64.56}{(s+2)(s+1)(s+5)}$. We have three simple poles, so the partial fraction expansion is very straightforward.

The form of the partial fraction expansion is $I_L(s) = \frac{k_1}{s+2} + \frac{l_1}{s+1} + \frac{m_1}{s+5}$ — going in the order we've written the factors — and we want to compute these residues. These are simple poles, so the computation is easy. $k_1 = (s+2)I_L(s)$ at $s=-2$: multiplying by $(s+2)$ gets rid of that factor in the denominator, so we have $-64.56$ over the other two factors at $s=-2$: $(-2+1)(-2+5) = (-1)(3) = -3$. So $-64.56/(-3) = 21.52$. $l_1$, the residue for the pole at $s=-1$, is $(s+1)I_L(s)$ at $s=-1$: $-64.56$ divided by $(-1+2)(-1+5) = (1)(4) = 4$; that's $-16.14$. Finally $m_1$, the residue at $s=-5$, is $(s+5)I_L(s)$ at $s=-5$: $-64.56$ divided by $(-5+2)(-5+1) = (-3)(-4) = 12$; that's $-5.38$. So finally $I_L(s) = \frac{21.52}{s+2} - \frac{16.14}{s+1} - \frac{5.38}{s+5}$.

Now we have the partial fraction expansion of $I_L(s)$, and from this it's very easy to compute the inverse Laplace transform. We go to Ulaby et al. Table 12-2, and we have the result that we've used in the other examples multiple times: $e^{-at}u(t)$ forms a Laplace transform pair with $\frac{1}{s+a}$. From this we can immediately write down $i_L(t)$, the inverse Laplace transform of $I_L(s)$. Arranging the terms from the slowest exponential to the fastest: it's $-16.14e^{-t}$ (from the $s+1$ term), $+21.52e^{-2t}$ (from the first term), $-5.38e^{-5t}$ (from the last term), times $u(t)$, in amps. This is our final result for the current through the inductor $i_L(t)$ for $t > 0$. If you check this, you should find that at $t = 0$ this is in fact zero, as we expected it to be.

### Key points (instructor retrospective)

What were the key points? If we go through and think about what we did and what lessons we can draw from this: the first point is that, as in the other examples of this type, the major steps in executing the Laplace transform analysis of this circuit were, first, to determine the initial conditions for the current through the inductor and the voltage across the capacitor, $i_L(0^-)$ and $v_C(0^-)$. Then, once we did that, to transform the circuit to the $s$ domain — we needed the initial conditions to do that. In this case we had one nonzero initial condition, $v_C(0^-)$ was nonzero, so that meant we had to introduce an additional voltage source in series with the capacitor to take that into account. Then, once we had transformed the circuit to the $s$ domain, we could go ahead and analyze the circuit in the $s$ domain, and then finally perform the inverse transform back to the time domain, which is where we want to be to get our final answer.

As I noted, this example included a situation where we had a nonzero initial condition. So the initial conditions here — specifically the fact that $v_C(0^-)$ was nonzero — required the addition of a voltage source in series with the capacitor in the $s$ domain. But once we included that, we could just go ahead and analyze the circuit in the $s$ domain as we usually do.

Once again, we saw that the partial fraction expansion for $I_L(s)$ made the inverse Laplace transform very straightforward.

Finally, we saw here that, as usual, accuracy and proficiency in complex algebra are very important in solving these types of problems. That is everything for this example, and I will now stop the recording.

## Index terms

Ulaby 12.37, Problem 12.37, Problem 12.36, Figure P12.36, Figure P12.37, circuit analysis using Laplace transforms, nonzero initial conditions, initial capacitor voltage, v_C(0⁻) = 60 V, i_L(0⁻) = 0, voltage source in series with capacitor, v_C(0⁻)/s = 60/s, s-domain circuit, current source, 6 A, 6 e^{-2t} u(t) ↔ 6/(s+2), t = 0⁻ circuit, capacitor open circuit, inductor short circuit, node voltage analysis, reference node, V1, V2, KCL at V1, KCL at V2, 1/(sC), sL, Cramer's rule, 2×2 determinant, I_L(s) = V2/(sL), LC = 1/15 s, C = 1/(15L) = 0.1076 F, R1 = 10 Ω, R2 = 5 Ω, L = 0.6196 H, cancelling s terms, -64.56, (s+2)(s²+6s+5), (s+1)(s+5), three real simple poles, partial fraction expansion, residues, k1 = 21.52, l1 = -16.14, m1 = -5.38, Table 12-2, e^{-at} u(t) ↔ 1/(s+a), i_L(t) = [-16.14 e^{-t} + 21.52 e^{-2t} - 5.38 e^{-5t}] u(t) A, check i_L(0) = 0, four-step procedure, complex algebra, Prof. Ed Yu, problem solving video, Chapter 12
