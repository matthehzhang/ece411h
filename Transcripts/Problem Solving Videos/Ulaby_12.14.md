---
course: ECE 411H
kind: problem-video
source: Problem Solving Videos/Ulaby 12.14.pdf
source_pages: 4
author: Prof. Ed Yu
unit: exam2
topics: [laplace-circuit-analysis, s-domain, series-rlc, ramp-input, initial-conditions, partial-fractions, complex-poles, polar-form-residue, phase-angle-quadrant, kvl, table-12-2, ulaby-12.14]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
deepgram_transcript: deepgram/Ulaby_12.14.deepgram.txt
deepgram_paragraphs: deepgram/Ulaby_12.14.deepgram.md
---

# Ulaby 12.14 — Series RLC driven by a ramp, solved in the s-domain

**Summary.** Prof. Yu works Ulaby/Maharbiz/Furse Problem 12.14: a series RLC loop ($R=2\,\Omega$, $L=6$ H, $C=2$ F) driven by $v_s(t) = t\,u(t)$ V; find $i(t)$ for $t\ge 0$. Steps: (1) initial conditions are zero ($i_L(0^-)=v_C(0^-)=0$) so no extra sources are needed; (2) transform the circuit ($Z_L = sL$, $Z_C = 1/sC$, $V_s(s) = 1/s^2$); (3) KVL gives $I(s) = 1/[6s(s^2+\tfrac13 s+\tfrac1{12})]$ with poles at $0$ and $-\tfrac16\pm j\tfrac{\sqrt2}{6}$; partial fractions with residues $k_1 = 2$, $l_1 = -1+j\tfrac{\sqrt2}{2} = 1.225e^{j144.7^\circ}$; (4) inverse transform to $i(t) = [2 + 2.45e^{-t/6}\cos(0.2357t + 144.7^\circ)]u(t)$ A. The instructor emphasizes the second-quadrant phase angle (a calculator's $\tan^{-1}$ would give the wrong quadrant) and that the cosine argument mixes radians and degrees. Exam relevance: template for the standard four-step Laplace circuit analysis, including a non-sinusoidal (ramp) source that phasors cannot handle.

> **Audio transcript (Deepgram nova-3, ECE 411 keyterms, timestamped):** `deepgram/Ulaby_12.14.deepgram.txt` ; paragraph form: `deepgram/Ulaby_12.14.deepgram.md`. Fresh ASR of the video audio; where it disagrees with the Narration section (built from the published auto-captions), prefer this file and the handwritten page.

## Problem statement

**12.14** In the circuit of Fig. P12.14(a), $v_s(t)$ is given by the waveform displayed in Fig. P12.14(b). Determine $i(t)$ for $t\ge 0$, given that $R = 2\,\Omega$, $L = 6$ H, and $C = 2$ F.

**Figure P12.14 (textbook image):** (a) Circuit — a single series loop: voltage source $v_s$ (+ terminal at top) on the left; current $i(t)$ marked flowing to the right along the top wire into $R$; $R$ along the top; $L$ down the right side; $C$ below $L$ on the right side; bottom wire returns to the source's $-$ terminal. (b) $v_s(t)$ vs $t$ (s): zero for $t<0$; for $t\ge 0$ a straight ramp passing through $(1\,\text{s}, 1\,\text{V})$, $(2\,\text{s}, 2\,\text{V})$, $(3\,\text{s}, 3\,\text{V})$, with dashed guide lines at those three points; the ramp continues upward with an arrowhead. Caption: "Figure P12.14: Circuit and waveform for Problem 12.14."

## Page 1

Header (typed): "Ulaby 12.14", "Thursday, June 15, 2023 9:14 AM". Textbook problem image (as above). Handwritten title, underlined: **Example: circuit analysis using Laplace Transforms.**

**Figure (handwritten redraw):** Series loop: $v_s(t)$ source (circle, + at top) on the left; $i(t)$ arrow to the right along the top into $R$ (zigzag); $L$ (coil) down the right side; $C$ (plates) below $L$; bottom wire closes the loop.

$R = 2\,\Omega$, $L = 6\,\text{H}$, $C = 2\,\text{F}$

**Figure (handwritten plot):** $v_s(t)$ [V] vs $t$: axis ticks $1, 2, 3$ on $t$, $1, 2$ on $v_s$; blue curve is zero for $t<0$ and a straight line of slope 1 for $t>0$ with an arrowhead.

$v_s(t) = t\,u(t)$ V.

Solve for $i(t)$.

1) Determine initial conditions for $i_L$ and $v_C$ at $t = 0^-$:

For $t = 0^-$, $v_s(t) = 0$ so $i_L(0^-) = 0$, $v_C(0^-) = 0$.

2) Transform circuit to s-domain for $t \ge 0$: (circuit begins at page bottom with label "$I(s)$", continued on page 2)

## Page 2

2) Transform circuit to s-domain for $t \ge 0$:

**Figure (s-domain circuit):** Same series loop: $V_s(s)$ source (+ at top) on the left; $I(s)$ arrow rightward along the top into $R$; $Z_L = sL$ (coil) on the right; $Z_C = \dfrac{1}{sC}$ (plates) below it; bottom return.

$v_s(t) = t\,u(t) \leftrightarrow V_s(s) = \dfrac{1}{s^2}$ from Ulaby et al., Table 12-2.

3) Analyze circuit in s-domain, solve for $I(s)$ and $i(t)$:

KVL around circuit loop:
$$-V_s + RI(s) + Z_L I(s) + Z_C I(s) = 0$$
$$\Rightarrow \left(2 + 6s + \frac{1}{2s}\right)I(s) = V_s = \frac{1}{s^2},\ \text{or}$$
$$I(s) = \frac{1}{s^2\left(2+6s+\frac{1}{2s}\right)},\ \text{or}$$
$$I(s) = \frac{1}{6s\left(s^2 + \frac{1}{3}s + \frac{1}{12}\right)}$$

$I(s)$ has poles at $s = 0$, $s^2 + \frac{1}{3}s + \frac{1}{12} = 0$
$$\Rightarrow s = \frac{1}{2}\left[-\frac{1}{3} \pm \sqrt{\frac{1}{9} - \frac{4}{12}}\right] = -\frac{1}{6} \pm j\frac{1}{2}\sqrt{\frac{2}{9}} = -\frac{1}{6} \pm j\frac{\sqrt{2}}{6}$$

$$\Rightarrow I(s) = \frac{1}{6s\left(s + \frac{1}{6} - j\frac{\sqrt{2}}{6}\right)\left(s + \frac{1}{6} + j\frac{\sqrt{2}}{6}\right)}$$

Partial fraction expansion of $I(s)$: (continued on page 3)

## Page 3

Partial fraction expansion of $I(s)$:
$$I(s) = \frac{k_1}{s} + \frac{l_1}{s + \frac{1}{6} - j\frac{\sqrt{2}}{6}} + \frac{l_1^*}{s + \frac{1}{6} + j\frac{\sqrt{2}}{6}}$$

$$k_1 = \left[sI(s)\right]\Big|_{s=0} = \frac{1}{6\left(0^2 + \frac{1}{3}(0) + \frac{1}{12}\right)} = 2.$$

$$l_1 = \left[\left(s + \tfrac{1}{6} - j\tfrac{\sqrt{2}}{6}\right)I(s)\right]\Bigg|_{s = -\frac{1}{6} + j\frac{\sqrt{2}}{6}} = \frac{1}{6\left(-\frac{1}{6} + j\frac{\sqrt{2}}{6}\right)\left(-\frac{1}{6} + j\frac{\sqrt{2}}{6} + \frac{1}{6} + j\frac{\sqrt{2}}{6}\right)}$$
$$= \frac{1}{\left(-1 + j\sqrt{2}\right)\left(j\frac{\sqrt{2}}{3}\right)} = \frac{1}{-\frac{2}{3} - j\frac{\sqrt{2}}{3}}\cdot\left(\frac{-\frac{2}{3} + j\frac{\sqrt{2}}{3}}{-\frac{2}{3} + j\frac{\sqrt{2}}{3}}\right)$$
$$= \frac{-\frac{2}{3} + j\frac{\sqrt{2}}{3}}{\left(\frac{2}{3}\right)^2 + \left(\frac{\sqrt{2}}{3}\right)^2} = \frac{3}{2}\left(-\frac{2}{3} + j\frac{\sqrt{2}}{3}\right) = -1 + j\frac{\sqrt{2}}{2}$$
$$= 1.225\,e^{j\phi},\quad \phi = 180^\circ - \tan^{-1}\frac{1}{\sqrt{2}} = 144.7^\circ$$
$$= 1.225\,e^{j144.7^\circ}$$

**Figure (green/red sketch, complex plane):** Real axis horizontal with tick at $-1$; imaginary axis vertical with tick at $\frac{\sqrt{2}}{2}$. A green dot labeled "$l_1$" sits at $(-1, \frac{\sqrt{2}}{2})$ in the second quadrant, with a green line from the origin to it; the angle $\phi$ is drawn as a green arc from the positive real axis counter-clockwise to that line. A red dashed line extends from the origin into the fourth quadrant (the continuation of the $l_1$ line through the origin), with a red arc labeled
$$\leftarrow \tan^{-1}\frac{-1}{\sqrt{2}} = -\tan^{-1}\frac{1}{\sqrt{2}}$$
i.e. the angle a calculator's arctangent would return, which is in the wrong quadrant.

$$\Rightarrow I(s) = \frac{2}{s} + \frac{1.225\,e^{j144.7^\circ}}{s + \frac{1}{6} - j\frac{\sqrt{2}}{6}} + \frac{1.225\,e^{-j144.7^\circ}}{s + \frac{1}{6} + j\frac{\sqrt{2}}{6}}$$

Compute inverse LT:
From Ulaby et al., Table 12-2, we have: (clipped at page bottom; continued on page 4)

## Page 4

From Ulaby et al., Table 12-2, we have:
$$u(t) \leftrightarrow \frac{1}{s},\qquad e^{-at}u(t) \leftrightarrow \frac{1}{s+a}$$

$$\Rightarrow i(t) = \left[2 + (1.225)\left(e^{-t/6}e^{j(\sqrt{2}/6)t}e^{j144.7^\circ} + e^{-t/6}e^{-j(\sqrt{2}/6)t}e^{-j144.7^\circ}\right)\right]u(t)$$
$$= \left[2 + (1.225)e^{-t/6}\,2\cos\left(\frac{\sqrt{2}}{6}t + 144.7^\circ\right)\right]u(t)$$

$$\Rightarrow \boxed{i(t) = \left[2 + 2.45\,e^{-t/6}\cos\left(0.2357t + 144.7^\circ\right)\right]u(t)\ \text{A}}$$

Annotations under the box: an arrow from "$0.2357t$" labeled **radians**; an arrow from "$144.7^\circ$" labeled **degrees**.

**Key points:** (underlined)

(i) major steps are (1) determine initial conditions $i_L(0^-)$, $v_C(0^-)$, (2) transform circuit to s-domain, (3) analyze in s-domain, (4) inverse transform back to time domain.

(ii) partial fraction expansion allows s-domain solution to be written in a form that is easily transformed back to time domain.

(iii) can be useful to express residues (coefficients) for complex poles in polar form, as phase shift angles appear more naturally.

(iv) accuracy + proficiency in complex algebra are important.

## Narration transcript

Cleaned from `Problem Solving Videos/Ulaby 12.14 captions.vtt`: timestamps and cue numbers stripped, fragments merged into sentences, auto-caption mishearings corrected ("will be problem 12.4" → Ulaby problem 12.14, "polls" → poles, "applause transform" → Laplace transform, "Kvl" → KVL, "phasers" → phasors, "Henry's/ferrets" → henrys/farads, "Jay" → $j$, "you'll be at all" → Ulaby et al., "estimate" → $s$ domain), verbal fillers trimmed. Content is otherwise complete.

This is Ulaby problem 12.14, and this is an example of circuit analysis using Laplace transforms. The problem that we are solving here is to look at this particular circuit and to figure out the current that flows around this loop, in the situation where the voltage source has this particular form: it's zero up to time equal to zero, and then it increases linearly with time for times greater than or equal to zero. Here the Laplace transform is a useful technique to employ, because if we didn't use Laplace transforms — we can't use phasors because this is not periodic — and if we tried to solve a differential equation associated with this directly, then we would be stuck with having to figure out the particular integral that solves the differential equation for a linear function as the inhomogeneity term. That's something we haven't discussed, so we don't know that's going to be straightforward. But we do know how to solve this kind of problem using Laplace transforms.

So let's go ahead. We will, as usual, redraw our circuit. We have a voltage source with a resistor, an inductor, and a capacitor like this. The voltage source is $v_s(t)$, the resistor is $R$, the inductor is $L$, the capacitor is $C$, and we want to solve for the current $i(t)$, where the resistance is $2\,\Omega$, the inductance is $6$ henrys, and the capacitance is $2$ farads. These are not necessarily realistic circuit numbers that you would find in an actual circuit, but they allow us to see the analysis technique and work out the numbers relatively easily. The voltage source $v_s(t)$ as a function of time: this is $0$, $1$ s, $2$ s, $3$ s; $1$ volt, $2$ volts; I'll draw this in blue. It is zero up until time equal to zero, and then it increases linearly. So $v_s(t)$ here is just $t\,u(t)$, in volts. What we're asked to do is to solve for $i(t)$. That's the problem we are given.

The first thing we want to do is to determine the initial conditions for the current through the inductor and the voltage across the capacitor at $t = 0^-$. We need to do that because when we eventually transform the circuit to the $s$ domain, if these values are nonzero, then we will have to introduce an additional component into the circuit. If we look at the circuit for times less than zero, $v_s(t)$ is equal to zero, and it's zero for a long time before $t=0$. So the current through the inductor should be zero, and the voltage across the capacitor should be zero as well. Since these are both zero, we will not have to introduce additional source components into the circuit when we transform it to the $s$ domain.

The second step is to transform the circuit to the $s$ domain for $t\ge 0$. We're going to have our voltage source, resistor, inductor, and capacitor. The voltage source will be some function of $s$ now. The resistor will be represented by an impedance which is $R$; the inductor has an impedance which is $s$ times the inductance $L$; and the capacitor has an impedance which is $1/(sC)$. The current will be some function in the $s$ domain also. The first thing we want to do after drawing this circuit in the $s$ domain is figure out what $V_s(s)$ is. We know $v_s(t)$ is $t$ times the unit step function, and we know that $t\,u(t)$ forms a Laplace transform pair with $1/s^2$. That's from Ulaby et al. Table 12-2, which is the table of common Laplace transform pairs.

Once we have all of that, what we want to do is analyze the circuit in the $s$ domain. In doing so we want to solve initially for $I(s)$ in the $s$ domain, and then we have to perform the inverse Laplace transform to go back to the time domain, which is the solution that ultimately we want. If we look at this circuit in the $s$ domain, the analysis is very straightforward. We just apply KVL — we enforce KVL going around the circuit loop — and in the resulting equation we solve for the current $I(s)$. So we apply KVL around the circuit loop. The voltage source gives us $-V_s(s)$; the resistor gives $R\,I(s)$; the inductor gives the inductor impedance $Z_L$ times $I(s)$; and for the capacitor, the capacitor impedance $Z_C$ times $I(s)$. All of those have to add up to zero by KVL. Now we substitute in numerical values for our circuit components: the resistor is $2\,\Omega$; the inductance is $6$ henrys, so the impedance is $6s$; the capacitance is $2$ farads, so the impedance is $1/(2s)$. All of this multiplies $I(s)$, and that's equal to $V_s(s)$ — it becomes positive when we move it to the right-hand side — and $V_s$ we saw up here is just $1/s^2$. We can solve this for $I(s)$: it's equal to $\dfrac{1}{s^2\left(2 + 6s + \frac{1}{2s}\right)}$.

If we put this in the standard form, which makes it a little easier to compute the partial fraction expansion and eventually the inverse Laplace transform, we take one factor of $s$ and multiply it through these three terms, so that we get a quadratic expression in $s$, and we factor out a $6$ and pull it outside into the denominator. We get $1$ over $6s$ times $s^2$ (from $6s$ times $s$ with the factor of $6$ pulled out) plus $\frac{1}{3}s$ (from $2$ times $s$, with the $6$ pulled out that becomes $\frac{1}{3}$) plus $\frac{1}{12}$ (that's $\frac{1}{2s}$ times $s$, which is $\frac{1}{2}$, with the $6$ pulled out becomes $\frac{1}{12}$). So $I(s) = \dfrac{1}{6s\left(s^2 + \frac{1}{3}s + \frac{1}{12}\right)}$.

Now this is the function for which we want to compute the inverse Laplace transform to get $i(t)$, and to do that we want to determine the values of $s$ at which it has poles. $I(s)$ has poles at $s=0$ and where $s^2 + \frac{1}{3}s + \frac{1}{12} = 0$. For this quadratic, to find its roots we use the quadratic formula: $s = \frac{1}{2}\left[-\frac{1}{3}\pm\sqrt{\left(\frac{1}{3}\right)^2 - 4\cdot\frac{1}{12}}\right]$. This becomes $-\frac{1}{3}\times\frac{1}{2} = -\frac{1}{6}$, plus or minus — the quantity under the square root is negative, so we have a factor of $j$, and we bring in the $\frac{1}{2}$ from outside — $4/12 = 1/3$, so we pull the $j$ out and it becomes $\frac{1}{3} - \frac{1}{9} = \frac{3}{9} - \frac{1}{9} = \frac{2}{9}$. So we have $\sqrt{2/9}$. The square root of $2$ in the numerator, the square root of $9$ is $3$, times the $2$ gives $6$ in the denominator. So $s = -\frac{1}{6}\pm j\frac{\sqrt{2}}{6}$. That means $I(s) = \dfrac{1}{6s\left(s + \frac{1}{6} - j\frac{\sqrt{2}}{6}\right)\left(s + \frac{1}{6} + j\frac{\sqrt{2}}{6}\right)}$.

Now this is the function for which we want to compute the inverse Laplace transform, so we go through the usual procedure of writing out the partial fraction expansion, figuring out the residues or coefficients in that expansion, and then doing the inverse Laplace transform. The partial fraction expansion of $I(s)$ is $\frac{k_1}{s} + \frac{l_1}{s + \frac{1}{6} - j\frac{\sqrt{2}}{6}} + \frac{l_1^*}{s + \frac{1}{6} + j\frac{\sqrt{2}}{6}}$; the residues are complex conjugates of each other because the poles are complex conjugates of each other.

To compute the residues we do the usual thing. $k_1 = sI(s)$ evaluated at $s=0$. When we take $I(s)$ and multiply by $s$, that cancels the $s$ in the denominator, and we have the other terms evaluated at $s=0$: $\frac{1}{6\left(0 + 0 + \frac{1}{12}\right)}$. $6\times\frac{1}{12} = \frac{1}{2}$ in the denominator, so $k_1 = 2$.

Then we compute $l_1$, following the same procedure: $\left(s + \frac{1}{6} - j\frac{\sqrt{2}}{6}\right)I(s)$ evaluated at $s = -\frac{1}{6} + j\frac{\sqrt{2}}{6}$. Multiplying by that factor cancels it in the denominator, and we have the other two factors left, evaluated at that $s$: $\dfrac{1}{6\left(-\frac{1}{6} + j\frac{\sqrt{2}}{6}\right)\left(-\frac{1}{6} + j\frac{\sqrt{2}}{6} + \frac{1}{6} + j\frac{\sqrt{2}}{6}\right)}$. Working this out: $6$ times the first factor in parentheses is $-1 + j\sqrt{2}$. In the second factor, $-\frac{1}{6} + \frac{1}{6} = 0$, and $j\frac{\sqrt{2}}{6} + j\frac{\sqrt{2}}{6} = j\frac{\sqrt{2}}{3}$. Multiplying out the terms in the denominator: $j\sqrt{2}\cdot j\frac{\sqrt{2}}{3} = -\frac{2}{3}$, and $j\frac{\sqrt{2}}{3}\times(-1) = -j\frac{\sqrt{2}}{3}$. So we have $\dfrac{1}{-\frac{2}{3} - j\frac{\sqrt{2}}{3}}$. Now we multiply numerator and denominator by the complex conjugate of the denominator, $-\frac{2}{3} + j\frac{\sqrt{2}}{3}$; that gives the magnitude squared of the denominator in the denominator, and the conjugate in the numerator: $\dfrac{-\frac{2}{3} + j\frac{\sqrt{2}}{3}}{\left(\frac{2}{3}\right)^2 + \left(\frac{\sqrt{2}}{3}\right)^2}$. In the denominator we have $\frac{4}{9} + \frac{2}{9} = \frac{6}{9} = \frac{2}{3}$, which becomes $\frac{3}{2}$ in the numerator: $\frac{3}{2}\left(-\frac{2}{3} + j\frac{\sqrt{2}}{3}\right)$. Multiply through: $-1 + j\frac{\sqrt{2}}{2}$.

So we've gotten $l_1$ in rectangular form, but it turns out to be useful to put it into polar form now, because that will allow us to get a phase shift angle out of it more easily. The magnitude is $\sqrt{1 + \left(\frac{\sqrt{2}}{2}\right)^2}$, which ends up being $1.225$, times $e^{j\phi}$ for some phase angle $\phi$, where $\phi = 180^\circ - \tan^{-1}\frac{\sqrt{2}/2}{1}$, or equivalently $\tan^{-1}\frac{1}{\sqrt{2}}$. That turns out to be $144.7^\circ$. So $l_1 = 1.225\,e^{j144.7^\circ}$.

Here you might ask: why didn't we just take $\frac{\sqrt{2}}{2}$ divided by $-1$ and compute the inverse tangent of that? The reason is: if we draw out $l_1 = -1 + j\frac{\sqrt{2}}{2}$ — this is $-1$, this is $\frac{\sqrt{2}}{2}$ — we know that point is out here, in the second quadrant, and the angle we want is this one. Just looking at the form, we know it has to be in the second quadrant. But if we were to take just the inverse tangent of $\frac{\sqrt{2}/2}{-1}$, that would actually give us — in red — this angle here, because computing the inverse tangent of $-\frac{1}{\sqrt{2}}$, which is minus the inverse tangent of $\frac{1}{\sqrt{2}}$, if you stuck that into your calculator, is going to give you an angle between $-90^\circ$ and $90^\circ$. So we have to take that and shift it by $180^\circ$ — that's this $180^\circ$ here — in order to get what is actually the correct angle. That is why we calculated the phase angle this way. That's something that, as hopefully you know from our discussion of phasors, is important to be mindful of and to do correctly.

Now that we have $k_1$ and $l_1$, we know that $I(s) = \frac{2}{s}$ (that's $k_1/s$) plus $\frac{l_1}{s + \frac{1}{6} - j\frac{\sqrt{2}}{6}}$ plus $\frac{l_1^*}{s + \frac{1}{6} + j\frac{\sqrt{2}}{6}}$, with $l_1 = 1.225e^{j144.7^\circ}$, and when we compute its complex conjugate we just put a minus sign in front of the $j$. So $I(s) = \dfrac{2}{s} + \dfrac{1.225e^{j144.7^\circ}}{s + \frac{1}{6} - j\frac{\sqrt{2}}{6}} + \dfrac{1.225e^{-j144.7^\circ}}{s + \frac{1}{6} + j\frac{\sqrt{2}}{6}}$. That is the current in the $s$ domain.

What we need to do now is compute the inverse Laplace transform. We just have a sum of simple poles here, so we know that the inverse Laplace transform is just going to be a sum of exponentials — in this case, with the pole at $0$, it is an exponential with zero in the exponent, or just one. From Ulaby et al. Table 12-2, the table of common Laplace transform pairs, $u(t)$ forms a Laplace transform pair with $1/s$ — that gives us the first term — and $e^{-at}u(t)$ forms a pair with $1/(s+a)$; we could also use that to get the first term with $a=0$, and we use it to get the second and third terms. Using these results, we get from the first term in $I(s)$ $2u(t)$ — every term will have a factor of $u(t)$ so we write it at the end — plus $1.225$, a factor common to both of the other terms, times, from the first of them, $e^{-at}$, which is $e^{-t/6}$ times $e^{+j(\sqrt{2}/6)t}$, times $e^{j144.7^\circ}$; and from the last term, $e^{-t/6}e^{-j(\sqrt{2}/6)t}e^{-j144.7^\circ}$. All of this times $u(t)$.

Then: it's $2 + 1.225$ times — both of these terms have a factor of $e^{-t/6}$, so we can pull that out in front — and the other factors in these two terms, you can see pretty easily, are equal to $2\cos\left(\frac{\sqrt{2}}{6}t + 144.7^\circ\right)$, times $u(t)$. If we simplify a little more, multiplying $2$ by $1.225$ and putting in a decimal value for $\frac{\sqrt{2}}{6}$, what we finally get is $i(t) = \left[2 + 2.45e^{-t/6}\cos(0.2357t + 144.7^\circ)\right]u(t)$, in amps. This is the answer.

As I had noted, or perhaps will note in class, you have to be a little careful here, because this term, $0.2357t$, is an angle in radians, because the angular frequency is typically given in radians per second, while this, $144.7^\circ$, is in degrees. So we've added things in different units, which ordinarily is a no-no. But that is typically how these are written, so we have to be cognizant that this is in radians and this is in degrees.

### Key points (instructor retrospective)

What are some of the key points that we can extract from this particular example? First, we saw what the general procedure is for doing circuit analysis using the Laplace transform. The major steps are: first, determine the initial conditions for the current through the inductor and the voltage across the capacitor — one has to do this for all the inductors and capacitors in the circuit; in this case there was only one of each. Then, once we have those, we transform the circuit to the $s$ domain. If some of these initial conditions were nonzero, we would have to introduce additional source components into the $s$ domain circuit, but in this particular case they were both zero, so we didn't have to. Then we do the analysis of the circuit in the $s$ domain, which is the same as just doing conventional circuit analysis, except that you have impedances that can be functions of $s$. Once you've done that and gotten the result you want — in our case that was $I(s)$ in the $s$ domain — you perform the inverse transform back to the time domain.

The second point, which we also saw in the examples of how to compute inverse Laplace transforms more generically, is that the partial fraction expansion allows the $s$ domain solution that we obtained to be written in a form that is easily transformed back to the time domain.

A third point is that when we computed the residues — the coefficients in the partial fraction expansion — we expressed the residues for the complex roots in polar form, and that was useful because it allowed us to get the phase shift angles quite directly once we did the inverse Laplace transform. So keep in mind that it can be useful to express the residues, the coefficients for complex poles, in polar form, at least at the end. You don't have to work with it in polar form throughout, but at the end it can be useful, because the phase shift angles appear this way more naturally.

The last point, which you may have noticed as we worked through this example and perhaps others, is that accuracy and proficiency in complex algebra are very important. That is it for this example, and I will stop the recording.

## Index terms

Ulaby 12.14, Problem 12.14, Figure P12.14, circuit analysis using Laplace transforms, s-domain circuit, series RLC, ramp input, t u(t) ↔ 1/s², initial conditions, i_L(0⁻), v_C(0⁻), no additional source needed, Z_L = sL, Z_C = 1/(sC), KVL, I(s), i(t), poles, quadratic formula, -1/6 ± j√2/6, partial fraction expansion, residues, k1 = 2, l1 = -1 + j√2/2, polar form, 1.225 e^{j144.7°}, magnitude, phase angle, second quadrant, 180° - tan⁻¹(1/√2), calculator arctangent wrong quadrant, complex conjugate residues, rationalize denominator, Table 12-2, u(t) ↔ 1/s, e^{-at} u(t) ↔ 1/(s+a), 2 cos(ωt + φ), e^{-t/6}, 0.2357 rad/s, 144.7°, radians vs degrees, 2.45, i(t) = [2 + 2.45 e^{-t/6} cos(0.2357t + 144.7°)] u(t) A, phasors not applicable (non-periodic), particular integral for ramp, R = 2 Ω, L = 6 H, C = 2 F, four-step procedure, complex algebra, Prof. Ed Yu, problem solving video, Chapter 12
