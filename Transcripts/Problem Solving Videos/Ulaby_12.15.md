---
course: ECE 411H
kind: problem-video
source: Problem Solving Videos/Ulaby 12.15.pdf
source_pages: 7
author: Prof. Ed Yu
unit: exam2
topics: [laplace-circuit-analysis, s-domain, series-rlc, delayed-step-input, time-shift-property, partial-fractions, complex-poles, differential-equation-check, homogeneous-solution, particular-integral, textbook-solution-error, kvl, table-12-2, ulaby-12.15]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
deepgram_transcript: deepgram/Ulaby_12.15.deepgram.txt
deepgram_paragraphs: deepgram/Ulaby_12.15.deepgram.md
---

# Ulaby 12.15 — RLC with delayed step input: Laplace solution checked by differential equation

**Summary.** Prof. Yu works Ulaby/Maharbiz/Furse Problem 12.15: two parallel $4\,\Omega$ resistors ($R_{eq}=2\,\Omega$) in series with $L=2$ H and $C=0.5$ F, driven by $v_s(t) = u(t-2)$ V; find $i_L(t)$. Laplace route: zero initial conditions; $V_s(s) = e^{-2s}/s$; KVL gives $I_L(s) = e^{-2s}F(s)$ with $F(s) = 1/[2(s^2+s+1)]$, poles $-\tfrac12\pm j\tfrac{\sqrt3}{2}$, residue $k_1 = 1/(j2\sqrt3)$, so $f(t) = \tfrac{1}{\sqrt3}e^{-t/2}\sin(\tfrac{\sqrt3}{2}t)u(t)$, and the time-shift property gives $i_L(t) = 0.5774\,e^{-(t-2)/2}\sin[0.866(t-2)]u(t-2)$ A. The textbook answer has amplitude $1.14$ (a factor of 2 too large); the instructor re-solves by the time-domain second-order ODE for $v_C$ (homogeneous + particular integral, initial conditions $v_C(2)=0$, $v_C'(2)=0$, $A_1=-1$, $A_2=-1/\sqrt3$), differentiates to get $i_L = C\,dv_C/dt$, and recovers $1/\sqrt3$, confirming the Laplace result. Exam relevance: shows how to pull $e^{-Ts}$ out and apply it at the end, and that the ODE method is a valid cross-check.

> **Audio transcript (Deepgram nova-3, ECE 411 keyterms, timestamped):** `deepgram/Ulaby_12.15.deepgram.txt` ; paragraph form: `deepgram/Ulaby_12.15.deepgram.md`. Fresh ASR of the video audio; where it disagrees with the Narration section (built from the published auto-captions), prefer this file and the handwritten page.

## Problem statement

***12.15** In the circuit of Fig. P12.15(a), $v_s(t)$ is given by the waveform displayed in Fig. P12.15(b). Determine $i_L(t)$, given that $R_1 = R_2 = 4\,\Omega$, $L = 2$ H, and $C = 0.5$ F.

**Figure P12.15 (textbook image):** (a) Circuit — voltage source $v_s(t)$ (+ at top) on the left. From the top-left node, $R_1$ (upper branch) and $R_2$ (lower branch) run in parallel to a top-right node (the two resistors are drawn one above the other, joined at both ends by dots). From the top-right node, $L$ goes downward (current $i_L$ marked with a downward arrow entering $L$), then $C$ below $L$, then the bottom wire returns to the source's $-$ terminal. (b) $v_s(t)$ vs $t$ (s): zero for $t<2$; steps up to $1$ V at $t=2$ s and stays at $1$ V (ticks at $1,2,3,4$ s, and $1$ V). Caption: "Figure P12.15: Circuit and waveform for Problem 12.15."

## Page 1

Header (typed): "Ulaby 12.15". Textbook problem image (as above). Handwritten title, underlined: **Example: circuit analysis using Laplace transforms + check by solving using differential equations.**

**Figure (handwritten redraw):** $v_s(t)$ source (circle, + at top) on the left; from the top-left node, $R_1$ (upper zigzag) and $R_2$ (lower zigzag) in parallel to the top-right node; from there $L$ (coil) downward with "$\downarrow i_L(t)$" marked beside it; $C$ (plates) below $L$; bottom wire returns to the source.

$R_1 = R_2 = 4\,\Omega$, $L = 2\,\text{H}$, $C = 0.5\,\text{F}$

**Figure (handwritten plot):** $v_s(t)$ vs $t$: ticks $1, 2, 3, 4$ on $t$ and $1$ on $v_s$; blue curve is zero until $t=2$, then jumps to $1$ and stays.

$v_s(t) = u(t-2)$ V.

Solve for $i_L(t)$.

1) Determine initial conditions for $t = 0^-$:

For $t = 0^-$, $L \to$ short circuit, $C \to$ open circuit, $v_s = 0$.
$$\Rightarrow i_L(0^-) = 0,\quad v_C(0^-) = 0.$$

2) Transform circuit to s-domain for $t \ge 0$: $R_{eq} = 2\,\Omega$ (circuit drawing begins at page bottom; continued on page 2)

## Page 2

**Figure (s-domain circuit):** $V_s(s)$ source (+ at top) on the left; $R_{eq} = 2\,\Omega$ (zigzag) along the top; at the top-right, "$\downarrow I_L(s)$"; $Z_L = sL = 2s$ (coil) down the right side; $Z_C = \dfrac{1}{sC} = \dfrac{2}{s}$ (plates) below it; bottom return.

$v_s(t) = u(t-2) \leftrightarrow V_s(s) = \dfrac{e^{-2s}}{s}$ from Ulaby et al., Table 12-2.

3) Analyze circuit in s-domain, solve for $I_L(s)$ and $i_L(t)$:

KVL around circuit loop:
$$-V_s + R_{eq}I_L + Z_L I_L + Z_C I_L = 0$$
$$\Rightarrow \left(2 + 2s + \frac{2}{s}\right)I_L = V_s,\ \text{or}$$
$$I_L = \frac{e^{-2s}}{s\left(2 + 2s + \frac{2}{s}\right)} \equiv e^{-2s}F(s)$$
(arrow under $e^{-2s}$: "account for this later using time-shift property of LTs.")

$$F(s) = \frac{1}{s\left(2 + 2s + \frac{2}{s}\right)} = \frac{1}{2(s^2 + s + 1)}\quad\text{(underlined)}$$

$F(s)$ has poles at $s^2 + s + 1 = 0$
$$\Rightarrow s = \frac{1}{2}\left[-1 \pm \sqrt{1^2 - 4}\right] = -\frac{1}{2} \pm j\frac{\sqrt{3}}{2}$$
$$\Rightarrow F(s) = \frac{1}{2\left(s + \frac{1}{2} - j\frac{\sqrt{3}}{2}\right)\left(s + \frac{1}{2} + j\frac{\sqrt{3}}{2}\right)}$$

Partial fraction expansion: (continued on page 3)

## Page 3

Partial fraction expansion:
$$F(s) = \frac{k_1}{s + \frac{1}{2} - j\frac{\sqrt{3}}{2}} + \frac{k_1^*}{s + \frac{1}{2} + j\frac{\sqrt{3}}{2}}$$

$$k_1 = \left[\left(s + \tfrac{1}{2} - j\tfrac{\sqrt{3}}{2}\right)F(s)\right]\Bigg|_{s = -\frac{1}{2} + j\frac{\sqrt{3}}{2}} = \frac{1}{2\left(-\frac{1}{2} + j\frac{\sqrt{3}}{2} + \frac{1}{2} + j\frac{\sqrt{3}}{2}\right)}$$
$$= \frac{1}{j2\sqrt{3}}$$

$$\Rightarrow F(s) = \frac{1}{j2\sqrt{3}}\left(\frac{1}{s + \frac{1}{2} - j\frac{\sqrt{3}}{2}} - \frac{1}{s + \frac{1}{2} + j\frac{\sqrt{3}}{2}}\right)$$

From Ulaby et al., Table 12-2, we have:
$$e^{-at}u(t) \leftrightarrow \frac{1}{s+a}$$

$$\Rightarrow f(t) = \frac{1}{j2\sqrt{3}}\left[e^{-\frac{1}{2}t + j\frac{\sqrt{3}}{2}t} - e^{-\frac{1}{2}t - j\frac{\sqrt{3}}{2}t}\right]u(t)$$
$$= \frac{e^{-\frac{1}{2}t}}{\sqrt{3}}\left(\frac{e^{j\frac{\sqrt{3}}{2}t} - e^{-j\frac{\sqrt{3}}{2}t}}{j2}\right)u(t)$$
$$= \frac{1}{\sqrt{3}}e^{-\frac{1}{2}t}\sin\frac{\sqrt{3}}{2}t\ u(t)$$

Time-shift property of LTs:
$$f(t-T)\,u(t-T) \leftrightarrow e^{-Ts}F(s)$$
$$I_L(s) = e^{-2s}F(s)$$

$$\Rightarrow \boxed{\begin{aligned} i_L(t) &= \frac{1}{\sqrt{3}}e^{-\frac{1}{2}(t-2)}\sin\left[\frac{\sqrt{3}}{2}(t-2)\right]u(t-2)\ \text{A, or} \\ i_L(t) &= 0.5774\,e^{-\frac{1}{2}(t-2)}\sin\left[0.866(t-2)\right]u(t-2)\ \text{A} \end{aligned}}$$

## Page 4

(Top: the boxed $i_L(t) = 0.5774\,e^{-\frac{1}{2}(t-2)}\sin[0.866(t-2)]u(t-2)$ A, clipped by the page break.)

Solution from Ulaby et al.: (pasted image of the textbook solution, transcribed verbatim)

> By the shift property of the Laplace transform,
> $$i_L(t) = 1.14e^{-0.5(t-2)}\cos[0.87(t-2) - 90^\circ]\,u(t-2)\ \text{A}$$
> $$= 1.14e^{-0.5(t-2)}\sin[0.87(t-2)]\,u(t-2)\ \text{A}.$$

Handwritten marks: "$1.14e$" in the second line is circled; a large "?" is written to the right of the pasted solution.

Check by using differential equation approach to solve for $i_L(t)$:

**Figure (time-domain circuit):** $v_s(t) = u(t-2)$ source (circle, + at top) on the left; $2\,\Omega$ (zigzag) along the top with "$\to i_L(t)$" arrow; $2\,\text{H}$ (coil) down the right; $0.5\,\text{F}$ (plates) below; bottom return. Label to the right: "Solve by diff. eq. approach."

KCL around circuit loop [sic — written "KCL", but the equation is the KVL loop sum]:
$$-v_s(t) + 2i_L + L\frac{di_L}{dt} + v_C = 0\ ;\quad i_L = C\frac{dv_C}{dt}$$
$$\Rightarrow LC\frac{d^2v_C}{dt^2} + 2C\frac{dv_C}{dt} + v_C = v_s(t)$$
$$(2)(0.5)\frac{d^2v_C}{dt^2} + 2(0.5)\frac{dv_C}{dt} + v_C = v_s(t)$$
$$\frac{d^2v_C}{dt^2} + \frac{dv_C}{dt} + v_C = v_s(t) = u(t-2)$$

$v_C(t) = 0$ for $t < 2$ s $\Rightarrow$ $\underline{v_C(2) = 0}$

$i_L(2) = i_L(2^-) = 0 \Rightarrow \dfrac{dv_C}{dt}\Big|_{t=2} = 0$ (clipped at page bottom; repeated on page 5)

## Page 5

$$i_L(2) = i_L(2^-) = 0 \Rightarrow \underline{\frac{dv_C}{dt}\Big|_{t=2} = 0}$$

Solve homogeneous equation, $\dfrac{d^2v_C}{dt^2} + \dfrac{dv_C}{dt} + v_C = 0$. Let $v_C = Ae^{st}$:
$$\Rightarrow s^2 + s + 1 = 0 \Rightarrow s = \frac{1}{2}\left[-1 \pm \sqrt{1^2 - 4}\right] = -\frac{1}{2} \pm j\frac{\sqrt{3}}{2}$$

Solution to the homogeneous equation is
$$v_C(t) = e^{-\frac{1}{2}(t-2)}\left[A_1\cos\frac{\sqrt{3}}{2}(t-2) + A_2\sin\frac{\sqrt{3}}{2}(t-2)\right]$$
(solution to homogeneous eqn. for $t \ge 2$)

particular integral:
$$v_C = 1\ \text{for}\ t \ge 2.$$

The full solution is therefore
$$v_C(t) = e^{-\frac{1}{2}(t-2)}\left[A_1\cos\left[\frac{\sqrt{3}}{2}(t-2)\right] + A_2\sin\left[\frac{\sqrt{3}}{2}(t-2)\right]\right] + 1,\quad t \ge 2.$$

$v_C(2) = 0 \Rightarrow A_1 + 1 = 0 \Rightarrow A_1 = -1.$ (green underline under $A_1 = -1$)

$\dfrac{dv_C}{dt}\Big|_{t=2} = 0 \Rightarrow$
$$\left\{-\frac{1}{2}e^{-\frac{1}{2}(t-2)}\left[A_1\cos\left[\frac{\sqrt{3}}{2}(t-2)\right] + A_2\sin\left[\frac{\sqrt{3}}{2}(t-2)\right]\right] + e^{-\frac{1}{2}(t-2)}\frac{\sqrt{3}}{2}\left[-A_1\sin\left[\frac{\sqrt{3}}{2}(t-2)\right] + A_2\cos\left[\frac{\sqrt{3}}{2}(t-2)\right]\right]\right\}\Bigg|_{t=2} = 0$$
Colored annotations on this line: each $e^{-\frac12(t-2)}$ factor has a green stroke with "1" above it (evaluates to 1); each $\cos[\cdot]$ has a green stroke with "1"; each $\sin[\cdot]$ has a red stroke with "0".
$$-\frac{1}{2}A_1 + \frac{\sqrt{3}}{2}A_2 = 0 \Rightarrow A_2 = \frac{1}{\sqrt{3}}A_1 = \frac{-1}{\sqrt{3}} = A_2$$ (green underline under $\frac{-1}{\sqrt3} = A_2$)

$i_L(t) = C\dfrac{dv_C}{dt} = \dfrac{1}{2}\dfrac{dv_C}{dt}$ (continued on page 6; the first long line is partially visible, clipped at the page bottom)

## Page 6

$$i_L(t) = C\frac{dv_C}{dt} = \frac{1}{2}\frac{dv_C}{dt}$$
$$= \frac{1}{2}\left\{-\frac{1}{2}e^{-\frac{1}{2}(t-2)}\left[-\cos\left[\frac{\sqrt{3}}{2}(t-2)\right] - \frac{1}{\sqrt{3}}\sin\left[\frac{\sqrt{3}}{2}(t-2)\right]\right] + e^{-\frac{1}{2}(t-2)}\frac{\sqrt{3}}{2}\left[\sin\left[\frac{\sqrt{3}}{2}(t-2)\right] - \frac{1}{\sqrt{3}}\cos\left[\frac{\sqrt{3}}{2}(t-2)\right]\right]\right\}$$
$$= \frac{1}{2}e^{-\frac{1}{2}(t-2)}\left[\left(\frac{1}{2} - \frac{1}{2}\right)\cos\left[\frac{\sqrt{3}}{2}(t-2)\right] + \left(\frac{1}{2\sqrt{3}} + \frac{\sqrt{3}}{2}\right)\sin\left[\frac{\sqrt{3}}{2}(t-2)\right]\right]$$
(red stroke through $\left(\frac12 - \frac12\right)$ with "0" written above it)
$$= e^{-\frac{1}{2}(t-2)}\,\frac{1}{2}\left(\frac{1+3}{2\sqrt{3}}\right)\sin\left[\frac{\sqrt{3}}{2}(t-2)\right]$$
(red strokes cancelling "$1+3$" against the "$2$"s: $\frac{1}{2}\cdot\frac{4}{2\sqrt3} = \frac{1}{\sqrt3}$)

$$\boxed{i_L(t) = \frac{1}{\sqrt{3}}e^{-\frac{1}{2}(t-2)}\sin\left[\frac{\sqrt{3}}{2}(t-2)\right]u(t-2)}$$

**Key points:** (underlined)

(i) major steps are (1) determine initial conditions $i_L(0^-)$, $v_C(0^-)$, (2) transform circuit to s-domain, (3) analyze in s-domain, (4) inverse transform back to time domain.

(ii) often helpful to notice and use properties of LTs — here, time-shift property to handle factor $e^{-2s}$ in $I_L(s)$.

(iii) partial fraction expansion allows s-domain solution to be written in a form that is easily transformed back to the time domain.

(iv) "official" solutions in text or elsewhere not necessarily correct.

(v) multiple methods for circuit analysis can be used as checks for each other. (continues on page 7)

## Page 7

(v) multiple methods for circuit analysis can be used as checks for each other.

(vi) accuracy + proficiency in complex algebra are important.

(Rest of page blank.)

## Narration transcript

Cleaned from `Problem Solving Videos/Ulaby 12.15 captions.vtt`: timestamps and cue numbers stripped, fragments merged into sentences, auto-caption mishearings corrected ("Yulin" → Ulaby, "polls" → poles, "applause transform" → Laplace transform, "Isobel/I sub L" → $i_L$, "Kvl" → KVL, "Casey all" → KCL, "Henry's/ferrets" → henrys/farads, "Jay" → $j$, "you'll be at all" → Ulaby et al., "estimate" → $s$ domain), verbal fillers trimmed. Content is otherwise complete. Note: the instructor says "KCL around circuit loop" for the time-domain loop equation; the equation itself is KVL.

This is Ulaby problem 12.15, and this is another example of circuit analysis using Laplace transforms. As it turns out, for this example it will end up being useful to check the solution by solving using differential equations. So we'll see the same circuit analyzed both ways.

This is the circuit we're looking at. It's a relatively simple circuit, and it has a voltage source that turns on at $t = 2$ s and goes from $0$ to $1$ volt at $t=2$. So let's analyze this. We will redraw the circuit as usual. We have two resistors, $R_1$ and $R_2$, that are connected in parallel. Then we have an inductor and a capacitor. The voltage source is $v_s(t)$, the inductor is $L$, the capacitor $C$, and we want to solve for the current through the inductor, $i_L(t)$. Our parameter values are that $R_1$ and $R_2$ are equal to $4\,\Omega$, the inductance is $2$ henrys, and the capacitance is $0.5$ farads. The voltage source $v_s(t)$ — I'll draw it in blue — is zero up until $2$ s, and then it increases to $1$ volt. Analytically, $v_s(t)$ is just the unit step function $u(t-2)$, in volts. What we want to do is solve for the current $i_L(t)$.

The first step, as usual, will be to determine the initial conditions for $t = 0^-$, and in particular the initial conditions for the current through the inductor, $i_L$, and for the voltage across the capacitor, $v_C$. If we're looking at times less than zero, the voltage source has been off for a long time, things are in steady state up to that point, and so we take the inductor and convert it to a short circuit, the capacitor behaves as an open circuit, and $v_s = 0$ at times less than zero. We can see pretty easily that in that situation the current through the inductor at $t = 0^-$ is zero, because there's no voltage driving any current, and the voltage across the capacitor at $t = 0^-$ is also equal to zero. That means that when we convert this circuit to the $s$ domain, we do not have to introduce any additional sources to account for these initial conditions — or equivalently, those sources will have values of zero.

The second step is to transform the circuit to the $s$ domain for $t \ge 0$. When we do that, we will have a voltage source $V_s(s)$. Then we have our resistors, but those are just two $4\,\Omega$ resistors in parallel, so we can replace those with an equivalent resistance that's just $2\,\Omega$, because two $4\,\Omega$ resistors in parallel have an equivalent resistance of $2\,\Omega$. Then we have our inductor and capacitor. The inductor has impedance equal to $sL$, so that's just $2s$, since the inductance is $2$ henrys. The capacitor has impedance $Z_C = 1/(sC)$; $C$ is one half, so this becomes $2/s$. What we want to solve for is $I_L(s)$, the current through the inductor, which is also the current through the capacitor. Finally, for the source: in the time domain the source is $u(t-2)$, and if we look at Table 12-2 in Ulaby, which has the various common Laplace transform pairs, we can see that $V_s(s)$ must be $e^{-2s}/s$. This is from Ulaby et al., Table 12-2. So this is the circuit in the $s$ domain.

What we want to do now is the circuit analysis in the $s$ domain. In doing so we can solve for $I_L(s)$, and then by doing the inverse Laplace transform we'll get $i_L(t)$, which is what we ultimately would like. To analyze the circuit in the $s$ domain, essentially all we have to do is apply KVL around the circuit loop. Starting from the voltage source, we have $-V_s$, plus $R_{eq}$ times $I_L$ (the voltage across the resistor), plus $Z_L I_L$ (the voltage across the inductor), plus $Z_C I_L$ (the voltage across the capacitor); all of that has to add up to zero by KVL. If we substitute in the numerical and $s$-dependent values for these impedances: for the resistor we have $2\,\Omega$, for the inductor an impedance of $2s$, for the capacitor an impedance of $2/s$; all of this times $I_L$, and that's equal to $V_s$, where we've moved $-V_s$ to the right-hand side. If we solve this for $I_L$, we get $\dfrac{e^{-2s}}{s\left(2 + 2s + \frac{2}{s}\right)}$. The $e^{-2s}/s$ comes from substituting in the expression for $V_s(s)$, and the denominator comes from dividing by the impedance sum.

We're going to take this and separate out the factor of $e^{-2s}$, and write the rest as a function $F(s)$. That's what we'll focus on initially; the $e^{-2s}$ we'll account for later using the time-shift property of Laplace transforms. So we're really going to focus just on this function $F(s)$, and then we'll take care of the exponential factor using the time-shift property. $F(s)$, for which we want to compute the inverse Laplace transform, is $\dfrac{1}{s\left(2 + 2s + \frac{2}{s}\right)}$, or, if we multiply through by the $s$ and factor out a $2$, $\dfrac{1}{2(s^2 + s + 1)}$.

If we look at this function in this form, we can see that it has poles where $s^2 + s + 1 = 0$. We determine the values of $s$ for which that occurs using the quadratic formula: $s = \frac{1}{2}\left[-1 \pm \sqrt{1^2 - 4}\right]$. That becomes $-\frac{1}{2}$ (the $-1$ divided by $2$) plus or minus — the discriminant under the square root is negative, so we get a factor of $j$, and we have $\sqrt{4-1} = \sqrt{3}$, divided by the $2$ — $j\frac{\sqrt{3}}{2}$. So $-\frac{1}{2}\pm j\frac{\sqrt{3}}{2}$; those are the poles of $F(s)$. That means we can write $F(s) = \dfrac{1}{2\left(s + \frac{1}{2} - j\frac{\sqrt{3}}{2}\right)\left(s + \frac{1}{2} + j\frac{\sqrt{3}}{2}\right)}$.

From this form of $F(s)$ we can do the partial fraction expansion. $F(s)$ will be of the form $\dfrac{k_1}{s + \frac{1}{2} - j\frac{\sqrt{3}}{2}} + \dfrac{k_1^*}{s + \frac{1}{2} + j\frac{\sqrt{3}}{2}}$. The residues are complex conjugates of each other, remember, because the poles are complex conjugates of each other, and you can see that the residues have to be complex conjugates pretty easily from the explicit expressions for the residues. So we only have one residue to calculate, $k_1$; the other will be its complex conjugate. The residue $k_1$ is $\left(s + \frac{1}{2} - j\frac{\sqrt{3}}{2}\right)F(s)$ evaluated at $s = -\frac{1}{2} + j\frac{\sqrt{3}}{2}$. When we multiply $F(s)$ by that factor, we cancel it in the denominator, so we have just $\dfrac{1}{2\left(s + \frac{1}{2} + j\frac{\sqrt{3}}{2}\right)}$ evaluated at that value of $s$: $\dfrac{1}{2\left(-\frac{1}{2} + j\frac{\sqrt{3}}{2} + \frac{1}{2} + j\frac{\sqrt{3}}{2}\right)}$. The $-\frac{1}{2}$ and $\frac{1}{2}$ add up to zero, and we have $j\frac{\sqrt{3}}{2} + j\frac{\sqrt{3}}{2} = j\sqrt{3}$, and then the $2$ out front. So $k_1 = \dfrac{1}{j2\sqrt{3}}$.

That means $F(s) = \dfrac{1}{j2\sqrt{3}}\cdot\dfrac{1}{s + \frac{1}{2} - j\frac{\sqrt{3}}{2}}$ — that's the first term in the partial fraction expansion — and from the second term we have $k_1^*$, which is $-\dfrac{1}{j2\sqrt{3}}$, times $\dfrac{1}{s + \frac{1}{2} + j\frac{\sqrt{3}}{2}}$. So we have $\dfrac{1}{j2\sqrt{3}}\left(\dfrac{1}{s + \frac{1}{2} - j\frac{\sqrt{3}}{2}} - \dfrac{1}{s + \frac{1}{2} + j\frac{\sqrt{3}}{2}}\right)$.

Now from here we have two simple poles, complex conjugates of each other, in the partial fraction expansion, so the inverse Laplace transform of $F(s)$ can be computed very easily. From Ulaby et al., from the table of Laplace transform pairs, Table 12-2, the result that's relevant is that $e^{-at}u(t)$ forms a Laplace transform pair with $\frac{1}{s+a}$, including when $a$ is complex, and that will allow us to essentially write down the inverse Laplace transforms of these two terms. So $f(t)$, the inverse Laplace transform of $F(s)$, is $\dfrac{1}{j2\sqrt{3}}$ times $e^{-at}$, so $e^{-\frac{1}{2}t + j\frac{\sqrt{3}}{2}t}$ from the first term, minus $e^{-\frac{1}{2}t - j\frac{\sqrt{3}}{2}t}$, all times $u(t)$. We can simplify this: both terms have an $e^{-\frac{1}{2}t}$, so we have $\dfrac{e^{-\frac{1}{2}t}}{\sqrt{3}}$ — that's the $\sqrt{3}$ — and what we have left in the numerator from each term is just the complex exponential phase factor, $e^{j\frac{\sqrt{3}}{2}t} - e^{-j\frac{\sqrt{3}}{2}t}$, and in the denominator the $j2$, which we bring inside the big parentheses, times $u(t)$. The expression in the big parentheses is just $\sin\frac{\sqrt{3}}{2}t$. So $f(t) = \dfrac{1}{\sqrt{3}}e^{-\frac{1}{2}t}\sin\left(\frac{\sqrt{3}}{2}t\right)u(t)$. That is the inverse Laplace transform of $F(s)$.

Now, if we go back, remember we still had the exponential factor $e^{-2s}$ to worry about in order to get $I_L(s)$, and eventually the current $i_L(t)$ in the time domain. To take care of that exponential factor we're going to use the time-shift property of Laplace transforms: in general, if $f(t)$ and $F(s)$ form a Laplace transform pair, then $f(t-T)u(t-T)$ forms a Laplace transform pair with $e^{-Ts}F(s)$. If we set $T = 2$, that gives us what we need to account for the extra exponential factor $e^{-2s}$ in $I_L$. We had $I_L(s) = e^{-2s}F(s)$, so $i_L(t)$ is this function $f(t)$ shifted in time by $2$ s — $t-2$ instead of $t$: $i_L(t) = \dfrac{1}{\sqrt{3}}e^{-\frac{1}{2}(t-2)}\sin\left[\frac{\sqrt{3}}{2}(t-2)\right]u(t-2)$, in amps. Or, if we calculate some of these values numerically, $1/\sqrt{3} = 0.5774$, $\frac{\sqrt{3}}{2} = 0.866$, so $i_L(t) = 0.5774\,e^{-\frac{1}{2}(t-2)}\sin[0.866(t-2)]u(t-2)$, again in amps. That's the answer.

Now if you look at this and go to the back of Ulaby and look at the answer to this problem, what you'll see is something that is different. Let me see if I can paste from the solutions — this should show up here in a minute. We didn't want that; let me get rid of this and try pasting again. I'm not sure why that is not pasting in. Let me try one more time. Oh, there we go. So this is the solution from Ulaby et al. Basically what you can see is that it's similar to what we just calculated, except that this numerical factor here is different. So why is that the case — which one of these is correct?

In order to figure out which one is correct, what we can do is check by using the differential equation approach to solve for $i_L(t)$. This is something we did back at the beginning of the semester, so we'll have to remind ourselves of how to do that. We're going to redraw the circuit: the resistor — we have the equivalent resistance of $2\,\Omega$ — inductance of $2$ henrys, capacitance of $0.5$ farads, and $v_s(t) = u(t-2)$. We're going to solve this by the differential equation approach. To do that, we're going to apply the loop law around this circuit loop, but now in the time domain. From the voltage source we have $-v_s(t)$; then from the resistor, with the current $i_L(t)$ that we're trying to solve for, the voltage is $2i_L$; then from the inductor — remember the voltage across an inductor is $L\frac{di}{dt}$ — plus $L\frac{di_L}{dt}$; and then the voltage across the capacitor is just $v_C$; these all add up to zero. We also know that since the inductor and the capacitor are in series, the current through the inductor is the same as the current through the capacitor, so $i_L$, which is also $i_C$, is just $C\frac{dv_C}{dt}$. We can take this expression for $i_L$ in terms of $v_C$, plug it in, and we'll get a second-order differential equation for $v_C$. Once we solve for $v_C$, we can get $i_L$ by multiplying by $C$ and taking the derivative. That's how we'll proceed.

If we take $C\frac{dv_C}{dt}$ and plug it in for $i_L$: from the term $L\frac{di_L}{dt}$ we get $LC\frac{d^2v_C}{dt^2}$; from $2i_L$ we get $2C\frac{dv_C}{dt}$; and the $v_C$ we just carry over; that's equal to $v_s(t)$ on the right-hand side. Now substitute numerical values: $L$ is $2$ henrys, $C$ is $0.5$ farads: $(2)(0.5)\frac{d^2v_C}{dt^2} + 2(0.5)\frac{dv_C}{dt} + v_C = v_s(t)$. Both numerical coefficients turn out to be one — nice and simple — so we get $\frac{d^2v_C}{dt^2} + \frac{dv_C}{dt} + v_C = v_s(t) = u(t-2)$.

Now we need initial conditions for this circuit, specifically for $v_C$ and its derivative with respect to time. $v_C(t)$ is equal to zero for $t$ less than $2$ s. That means — since the voltage across the capacitor has to be continuous, because otherwise we would have an undefined current — $v_C(2) = 0$. We also know that the current through the inductor at $2$ s has to equal the current through the inductor just prior to $2$ s, because for an inductor the current has to be continuous, and so we know that's equal to zero. But the current through the inductor is proportional to $\frac{dv_C}{dt}$, so $\frac{dv_C}{dt}$ at $t = 2$ s is also equal to zero. These are the initial conditions we will have to apply to our differential equation in order to come up with the complete solution.

Now we have this differential equation to solve, and as usual what we do is first solve the homogeneous equation, which is where the right-hand side $v_s(t)$ is set equal to zero: $\frac{d^2v_C}{dt^2} + \frac{dv_C}{dt} + v_C = 0$. To do that we let $v_C$ be some constant $A$ times $e^{st}$, plug that into the homogeneous equation, and what we end up with is an equation for $s$: $s^2 + s + 1 = 0$. We get $s$ by the quadratic formula: $\frac{1}{2}\left[-1\pm\sqrt{1^2 - 4}\right]$, which is $-\frac{1}{2}$ plus or minus — the discriminant is negative, so it's $j$ times — $\frac{\sqrt{3}}{2}$. That means the solution to the homogeneous equation is $v_C(t) = e^{-\frac{1}{2}(t-2)}$ — I'll write it as $(t-2)$, from the $-\frac{1}{2}$ in $s$ — times $A_1\cos\frac{\sqrt{3}}{2}(t-2) + A_2\sin\frac{\sqrt{3}}{2}(t-2)$, for some constants $A_1$, $A_2$. This is the solution to the homogeneous equation for $t \ge 2$ s.

Now you might ask, how can we put in $t-2$ here, instead of $t$? What we did when we saw these sorts of problems at the beginning of the semester was we plugged in $t$. But it's actually perfectly fine to do this time shift and plug in $t-2$, because all that will do is change the values of these coefficients, which as yet are undetermined. Anything that just changes the values of these coefficients we can do; we just have to make sure that we solve correctly — or at least consistently — for those coefficients later. So we're free to do this time shift.

Now we need to come up with the particular integral. For $t\ge 2$ s the right-hand side is just equal to one, and we need some function $v_C(t)$ that solves the equation when the right-hand side is one. If you remember, the solution in the case where the right-hand side is a constant is just that $v_C$ equals that constant — in this case one. So the particular integral is $v_C = 1$ for $t \ge 2$. To get the full solution we add the particular integral to the solution of the homogeneous equation: $v_C(t) = e^{-\frac{1}{2}(t-2)}\left[A_1\cos\left[\frac{\sqrt{3}}{2}(t-2)\right] + A_2\sin\left[\frac{\sqrt{3}}{2}(t-2)\right]\right] + 1$ — I'll put square brackets so it's clear — for $t \ge 2$ s.

Now we need to solve for $A_1$ and $A_2$. We use the initial conditions we derived earlier: $v_C$ at $t=2$ is zero, and $\frac{dv_C}{dt}$ at $t=2$ is also zero. From $v_C(2) = 0$: the cosine of $0$ is one, the sine of $0$ is zero, and the exponential is just one since the exponent is zero. So we have $A_1 + 1 = 0$ — that one is the particular integral — which means $A_1 = -1$.

Our second initial condition is $\frac{dv_C}{dt}$ at $t=2$ equal to zero. For that we need to take the derivative of the full solution with respect to $t$; give ourselves some room. The $+1$ at the end we won't have to worry about, because its derivative is zero. So really we have the product of the exponential and the thing in square brackets; we apply the product rule. The derivative is: the derivative of the first factor, $-\frac{1}{2}e^{-\frac{1}{2}(t-2)}$, times the second factor $\left[A_1\cos\frac{\sqrt{3}}{2}(t-2) + A_2\sin\frac{\sqrt{3}}{2}(t-2)\right]$; plus the first factor $e^{-\frac{1}{2}(t-2)}$ times the derivative of the second factor. When we take the derivatives of the cosine and sine we get a factor of $\frac{\sqrt{3}}{2}$, and $-A_1\sin\frac{\sqrt{3}}{2}(t-2)$ (because the derivative of cosine is minus sine) plus $A_2\cos\frac{\sqrt{3}}{2}(t-2)$ (because the derivative of sine is cosine). We evaluate this whole thing at $t=2$ and set it equal to zero. When we evaluate at $t=2$, all the arguments of the trigonometric functions are zero: the sines go to zero, the cosines go to one, and the exponentials go to one. So from the first part we get $-\frac{1}{2}A_1$, and from the second part we get $+\frac{\sqrt{3}}{2}A_2$; that's equal to zero. That means $A_2 = \frac{1}{\sqrt{3}}A_1$, and $A_1$ we saw is $-1$, so $A_2 = -\frac{1}{\sqrt{3}}$. These two results are our coefficients.

Now finally we can solve for $i_L(t)$. We know this is $C\frac{dv_C}{dt}$; the capacitance is one-half farad, so it's $\frac{1}{2}\frac{dv_C}{dt}$, and we just have to calculate that. We actually calculated the derivative of $v_C$ with respect to $t$ above, so we can use that result, plugging in the values for $A_1$ and $A_2$. We have a $\frac{1}{2}$ in front. Then, following along: $-\frac{1}{2}e^{-\frac{1}{2}(t-2)}$ times — $A_1 = -1$, so $-\cos\frac{\sqrt{3}}{2}(t-2)$, and $A_2 = -\frac{1}{\sqrt{3}}$, so $-\frac{1}{\sqrt{3}}\sin\frac{\sqrt{3}}{2}(t-2)$. Plus, moving to the second term, $e^{-\frac{1}{2}(t-2)}\frac{\sqrt{3}}{2}$ times — $-A_1$ is just $1$, so $\sin\frac{\sqrt{3}}{2}(t-2)$, plus $A_2$, which is $-\frac{1}{\sqrt{3}}$, times $\cos\frac{\sqrt{3}}{2}(t-2)$. All of this times the one-half.

It turns out there are some simplifications. We have the overall factor of $\frac{1}{2}$ on the outside; both terms have $e^{-\frac{1}{2}(t-2)}$, so pull that out. Then group the terms proportional to the cosine: from the first cosine we have $-\frac{1}{2}\times(-1) = \frac{1}{2}$; from the second cosine we have $\frac{\sqrt{3}}{2}\times\left(-\frac{1}{\sqrt{3}}\right) = -\frac{1}{2}$. So the cosine coefficient is $\frac{1}{2} - \frac{1}{2}$, which goes to zero, we can see. Then for the sine terms: from the first sine we have $-\frac{1}{2}\times\left(-\frac{1}{\sqrt{3}}\right) = \frac{1}{2\sqrt{3}}$; and from the second, $+\frac{\sqrt{3}}{2}$; times $\sin\frac{\sqrt{3}}{2}(t-2)$. So the first term goes away entirely, and what we have left is $e^{-\frac{1}{2}(t-2)}$, then the $\frac{1}{2}$, and for the term in parentheses we put both terms over a common denominator of $2\sqrt{3}$: $\frac{1+3}{2\sqrt{3}}$, times $\sin\frac{\sqrt{3}}{2}(t-2)$. $1+3 = 4$, and $2\times 2 = 4$ in the denominator, so those cancel. What we have left is $\frac{1}{\sqrt{3}}e^{-\frac{1}{2}(t-2)}\sin\frac{\sqrt{3}}{2}(t-2)$. Remember this was valid only for $t \ge 2$, so in fact this is times the unit step function $u(t-2)$. This is $i_L(t)$ — our solution — and you can see it has the $\frac{1}{\sqrt{3}}$ out in front. If you go back to what we did earlier, that's actually the same result we got there. So in fact the solution we worked out is correct, and the solution in Ulaby et al. turns out to be incorrect: it's a factor of $2$ too large.

So that's the result, and now we've seen this particular circuit analyzed in two different ways: using the Laplace transform approach and using the differential equation approach. You can decide in this case which you thought was easier.

### Key points (instructor retrospective)

Looking back on this, what are some of the key points? The first one is that, at least with respect to the Laplace transform approach, once again the major steps we went through are: first, determine the initial conditions, because that influences how we transform to the $s$ domain — if we have nonzero initial conditions for current through an inductor or voltage across a capacitor, then we have to introduce additional source components in the circuit. So determine the initial conditions, $i_L(0^-)$ and $v_C(0^-)$. Then, once we have those, we transform the circuit to the $s$ domain. Then, once we have the circuit in the $s$ domain, we analyze it in the $s$ domain. Then, once we have the solution in the $s$ domain, we do the inverse transform back to the time domain.

The second point: remember when we did the Laplace transform analysis, one of the things we did was pull out that exponential factor $e^{-2s}$ from the solution in the $s$ domain and deal with it separately in performing the inverse Laplace transform — we dealt with it at the end using the time-shift property. That kind of separation can often be helpful. So it's often helpful to notice and to use properties of Laplace transforms; the particular example we saw here was that we used the time-shift property to handle the factor of $e^{-2s}$ in $I_L(s)$, the $s$-domain solution for the current.

We saw, as usual, that the partial fraction expansion is a very useful tool in allowing the $s$-domain solution to be written in a form that can easily be transformed back to the time domain.

When we got the result, we saw that it was different from the result printed in Ulaby, and by doing the differential equation analysis we saw that in fact the solution we had worked out by Laplace transforms was correct, and the solution printed in Ulaby was incorrect — it was off by a factor of $2$. So one of the lessons is that the "official" solutions in the text, or perhaps elsewhere, are not necessarily correct.

Something that came along with this is that it's useful to know multiple methods to analyze and think about circuits, because sometimes you can use one as a check for another. So multiple methods for circuit analysis can be used as checks for each other.

The last point, as we've seen repeatedly if you've looked at many of these examples, is that accuracy and proficiency in complex algebra are important if you want to get the correct result. That is everything for this example, and I will now stop.

## Index terms

Ulaby 12.15, Problem 12.15, Figure P12.15, circuit analysis using Laplace transforms, s-domain circuit, parallel resistors, R_eq = 2 Ω, series RLC, delayed step input, u(t-2), e^{-2s}/s, initial conditions, i_L(0⁻) = 0, v_C(0⁻) = 0, inductor short circuit, capacitor open circuit, Z_L = sL = 2s, Z_C = 1/(sC) = 2/s, KVL, I_L(s), i_L(t), e^{-2s} F(s), time-shift property, f(t-T) u(t-T) ↔ e^{-Ts} F(s), F(s) = 1/(2(s²+s+1)), poles -1/2 ± j√3/2, partial fraction expansion, residue k1 = 1/(j2√3), complex-conjugate residues, Table 12-2, e^{-at} u(t) ↔ 1/(s+a), sin from complex exponentials, (1/√3) e^{-t/2} sin(√3 t/2), 0.5774, 0.866, textbook solution error, factor of 2, 1.14 vs 0.5774, differential equation check, second-order ODE, d²v_C/dt² + dv_C/dt + v_C = u(t-2), v_C(2) = 0, dv_C/dt(2) = 0, capacitor voltage continuity, inductor current continuity, homogeneous equation, characteristic equation s² + s + 1 = 0, A e^{st}, particular integral v_C = 1, A1 = -1, A2 = -1/√3, time-shifted homogeneous solution, product rule, i_L = C dv_C/dt, multiple methods as checks, complex algebra, R1 = R2 = 4 Ω, L = 2 H, C = 0.5 F, Prof. Ed Yu, problem solving video, Chapter 12
