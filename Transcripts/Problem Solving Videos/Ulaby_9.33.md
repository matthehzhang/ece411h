---
course: ECE 411H
kind: problem-video
source: Problem Solving Videos/Ulaby 9.33.pdf (captions: Problem Solving Videos/Ulaby 9.33 captions.vtt)
source_pages: 3
author: Prof. Ed Yu
unit: exam2
topics: [low-pass-filter, rlc-filter, transfer-function, standard-form, bode-plots, cutoff-frequency, quadratic-pole, kcl-phasor, corner-frequency, -40-db-per-decade, phase-plot, chapter-9]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
deepgram_transcript: deepgram/Ulaby_9.33.deepgram.txt
deepgram_paragraphs: deepgram/Ulaby_9.33.deepgram.md
---

# Ulaby 9.33 — Transfer function and Bode plots of a series-L / shunt-C / shunt-R low-pass filter (problem-solving video)

**Summary.** Prof. Yu works Ulaby/Maharbiz/Furse Problem 9.33: a series inductor $L$ feeding a shunt capacitor $C$ and shunt resistor $R$ (output across $R$). (a) By KCL at the output node he obtains $\mathbf H(\omega) = \mathbf V_o/\mathbf V_i = 1/\big(1 + j\omega L/R - \omega^2 LC\big)$ and writes it in standard quadratic-pole form $1/\big(1 + j\omega L/R + (j\omega/\omega_c)^2\big)$ with $\omega_c = 1/\sqrt{LC}$. (b) With $R = 100\ \Omega$, $L = 0.1\ \text{mH}$, $C = 1\ \mu\text{F}$: $\omega_c = 10^5$ rad/s, $\mathbf H(\omega_c) = 10/j$ so $M(\omega_c) = 20$ dB, $M(0) = 0$ dB, and the Bode magnitude plot is flat at 0 dB with a peak to 20 dB at $\omega_c$ followed by a $-40$ dB/dec roll-off; the phase goes $0^\circ \to -90^\circ$ at $\omega_c \to -180^\circ$ over $10^4$ to $10^6$ rad/s. (c) The high-frequency slope is $-40$ dB/dec because $\mathbf H \approx 1/(-\omega^2 LC)$: a $10\times$ change in $\omega$ changes $\mathbf H$ by $10^{-2}$. Exam relevance: second-order low-pass standard form, reading $\omega_c$ off the $(j\omega/\omega_c)^2$ term, the resonance peak at $\omega_c$ ($|\mathbf H(\omega_c)| = R\sqrt{C/L}$-type gain), and the $-40$ dB/dec slope of a quadratic pole.

> **Audio transcript (Deepgram nova-3, ECE 411 keyterms, timestamped):** `deepgram/Ulaby_9.33.deepgram.txt` ; paragraph form: `deepgram/Ulaby_9.33.deepgram.md`. Fresh ASR of the video audio; where it disagrees with the Narration section (built from the published auto-captions), prefer this file and the handwritten page.

## Problem statement

**9.33** For the circuit shown in Fig. P9.33:
(a) Obtain an expression for $\mathbf H(\omega) = \mathbf V_o/\mathbf V_i$ in standard form.
(b) Generate spectral plots for the magnitude and phase of $\mathbf H(\omega)$, given that $R = 100\ \Omega$, $L = 0.1\ \text{mH}$, and $C = 1\ \mu\text{F}$.
(c) Determine the cutoff frequency $\omega_c$ and the slope of the magnitude (in dB) when $\omega/\omega_c \gg 1$.

**Figure P9.33 (Circuit for Problem 9.33):** Input port on the left with $\mathbf V_i$ (+ on top, − on bottom). Inductor $L$ in the top rail from the input + terminal to a node. From that node, capacitor $C$ hangs down to the bottom rail, and to its right resistor $R$ hangs down to the bottom rail (C and R in parallel). Output port on the right, $\mathbf V_o$ (+ top, − bottom), taken across $R$. Bottom rail is common.

(Narration adds: the Bode plots are to be done in the linear (straight-line) approximation; part (c) asks for the cutoff frequency and the Bode magnitude slope at high frequency, $\omega \gg \omega_c$.)

## Page 1

Header: "Ulaby 9.33". The textbook problem statement and Figure P9.33 are pasted at top left (as above).

Handwritten, top right:

**Example:** calculation of transfer function + Bode plots for RLC low-pass filter.

**Figure (redrawn circuit):** Left terminals labeled $+$ (top), $-$ (bottom) with $\tilde{\mathbf V}_i$ between them. Inductor $L$ in the top rail from the top-left terminal to a node labeled $\tilde{\mathbf V}_o$ (node dot). From that node, capacitor $C$ down to the bottom rail; further right, resistor $R$ down to the bottom rail; then the top rail continues to the right output terminal $+$, with $\tilde{\mathbf V}_o$ marked between the right $+$ and $-$ terminals. Bottom rail labeled "$V = 0$" (reference node) with node dots where $C$ and $R$ connect.

a) Calculate $\tilde{\mathbf H} = \tilde{\mathbf V}_o/\tilde{\mathbf V}_i$

b) Bode plots for $R = 100\ \Omega$, $L = 0.1\ \text{mH}$, $C = 1\ \mu\text{F}$

c) Calculate $\omega_c$ and Bode plot slope for $\omega \gg \omega_c$

a) KCL @ $\tilde{\mathbf V}_o$:
$$\frac{\tilde{\mathbf V}_o - \tilde{\mathbf V}_i}{j\omega L} + \frac{\tilde{\mathbf V}_o}{\frac{1}{j\omega C}} + \frac{\tilde{\mathbf V}_o}{R} = 0$$

$$\left(\frac{1}{j\omega L} + j\omega C + \frac{1}{R}\right)\tilde{\mathbf V}_o = \frac{1}{j\omega L}\tilde{\mathbf V}_i\ ;\ \text{multiply by } j\omega L$$

$$\left(1 + j\omega\frac{L}{R} - \omega^2 LC\right)\tilde{\mathbf V}_o = \tilde{\mathbf V}_i$$

$$\Rightarrow\ \tilde{\mathbf H}(\omega) = \frac{\tilde{\mathbf V}_o}{\tilde{\mathbf V}_i} = \frac{1}{1 + j\omega\frac{L}{R} - \omega^2 LC}\ ,\ \text{or}$$

(This last line is cut by the page break and repeated at the top of Page 2.)

## Page 2

$$\Rightarrow\ \tilde{\mathbf H}(\omega) = \frac{\tilde{\mathbf V}_o}{\tilde{\mathbf V}_i} = \frac{1}{1 + j\omega\frac{L}{R} - \omega^2 LC}\ ,\ \text{or}$$

Boxed:
$$\tilde{\mathbf H}(\omega) = \frac{1}{1 + j\omega\frac{L}{R} + \left(\frac{j\omega}{\omega_c}\right)^2}\quad \text{with } \omega_c = \frac{1}{\sqrt{LC}}$$

b)
$$\omega_c = \frac{1}{\sqrt{LC}} = \frac{1}{\sqrt{10^{-4}\cdot 10^{-6}}} = 10^5\ \text{rad/s}$$

$$\tilde{\mathbf H}(\omega_c) = \frac{1}{\cancel{1} + j(10^5)(10^{-6}) - \cancel{1}} = \frac{10}{j}\ \Rightarrow\ M(\omega_c) = 20\log 10 = 20\ \text{dB}$$

(The "1" and the "$-1$" in the denominator are struck through to show they cancel.)

$M(0) = 20\log 1 = 0\ \text{dB}$ since $\tilde{\mathbf H}(0) = 1$.

**Figure (Bode magnitude plot, green):** Vertical axis $M(\omega)\,[\text{dB}]$ with ticks 20 and 0; horizontal axis $\omega$ with the single tick $10^5$. Green curve: flat at 0 dB from the left up to near $10^5$, a narrow peak rising to 20 dB at $\omega = 10^5$, then descending steeply to the right beyond $10^5$, labeled with an arrow "$-40$ dB/dec."

$\phi(0) = 0^\circ$; $\phi(\omega_c) = -90^\circ$; $\phi(\infty) = -180^\circ$

**Figure (Bode phase plot, green; starts at bottom of Page 2, continued on Page 3):** Vertical axis $\phi$ with ticks $0^\circ$, $-90^\circ$, $-180^\circ$; horizontal axis $\omega$ with ticks $10^4$, $10^5$, $10^6$. Green curve: flat at $0^\circ$ up to $10^4$; straight line down through $-90^\circ$ at $10^5$ to $-180^\circ$ at $10^6$; flat at $-180^\circ$ beyond, labeled "$-180^\circ$".

## Page 3

(Top: remainder of the phase plot from Page 2: ticks $0^\circ$, $-90^\circ$, $-180^\circ$ on the vertical axis; $10^4$, $10^5$, $10^6$ on the horizontal; green line descending from $10^4$ through $10^5$ to $10^6$, then flat, labeled "$-180^\circ$".)

c) As noted in (b), the slope of $M(\omega)$ for $\omega \gg \omega_c$ is $-40$ dB/decade. We can see this by noting that

$$\tilde{\mathbf H}(\omega) \approx \frac{1}{-\omega^2 LC}\ \text{ for } \omega \gg \omega_c,$$

so a $10\times$ change in $\omega$ changes $H(\omega)$ by $10^{-2}\times$, or $-40$ dB.

(Rest of page blank.)

## Narration transcript

Okay, so this is Ulaby problem 9.33, and this is an example of the calculation of a transfer function, and also construction of Bode plots, for an RLC circuit, what will turn out to be a low-pass filter circuit. The circuit that we want to analyze is the one shown here. The resistor $R$ has a value of 100 ohms, the inductance is 0.1 millihenries, and the capacitance is 1 microfarad. We want to calculate the voltage transfer function, generate the Bode plots, which for this example here we'll do in the linear approximation, and determine the cutoff frequency.

So let's go ahead and, as usual, redraw the circuit. We have an inductor, a capacitor, and a resistor. The circuit looks like this; the input voltage (I have this as a phasor) is at the left-hand terminals and the output voltage is at the right-hand terminals. We have an inductance $L$, a capacitance $C$ and a resistance $R$. What we want to do here is to calculate the voltage transfer function, which is the output voltage over the input voltage. Then we want to construct the Bode plots for a resistance of 100 ohms, inductance of 0.1 millihenries and a capacitance of 1 microfarad. And then we want to calculate the cutoff frequency and the Bode plot slope, that is, the magnitude slope for high frequencies, $\omega$ much greater than the cutoff frequency. So that's the problem that we want to solve.

For the first part, we want to calculate this output voltage over here, and we can do that simply by applying KCL at this upper node here. We'll take the voltage down here to be 0; then the voltage at this upper node is actually just $\mathbf V_o$, and so we want to apply KCL at that node. If we do that, what we have is that for the current going out to the left through the inductor, that current is $(\mathbf V_o - \mathbf V_i)$ over the impedance of the inductor, which is $j\omega L$. Then the current flowing down through the capacitor is $\mathbf V_o$ over the impedance of the capacitor, which is $1/(j\omega C)$, and then the current flowing down this way through the resistor is just $\mathbf V_o/R$, and the sum of those three currents has to be equal to 0.

From here, we just take this equation and group together the terms that are proportional to $\mathbf V_o$, and then we can move this term here that's proportional to $\mathbf V_i$ to the right-hand side, and then we just solve for $\mathbf V_o/\mathbf V_i$. For the terms proportional to $\mathbf V_o$ we have coefficients $1/(j\omega L)$ from this term here, plus $j\omega C$ from this term here, plus $1/R$ from this term here; all of these are multiplying $\mathbf V_o$, and that's equal to $1/(j\omega L)$ times $\mathbf V_i$, which we have moved to the right-hand side. Now we can take this equation and multiply it by $j\omega L$. On the left-hand side, $j\omega L$ times this first term gives us 1; $j\omega L$ times this third term here gives us $j\omega L/R$; and $j\omega L$ times the second term here gives us $-\omega^2 LC$, because $j^2$ gives us $-1$; all this times $\mathbf V_o$. On the right-hand side we just have $\mathbf V_i$, because multiplying by $j\omega L$ cancels this factor.

So now it's very easy for us to calculate the transfer function $\mathbf H$, which is $\mathbf V_o/\mathbf V_i$. This is just going to be $1/(1 + j\omega L/R - \omega^2 LC)$. Or, if we write this in a form that makes it a little bit easier for us to determine the cutoff frequency, we can write it as $1$ over $1 + j\omega L/R$ plus, and the standard form is that this is now $(j\omega/\omega_c)^2$. Comparing this expression here to this expression here, we can see that $\omega_c$ is just $1/\sqrt{LC}$. So this is the transfer function that we were asked to calculate.

Now for the second part of the problem, what we're asked to do is to construct the Bode plots. We have that $\omega_c = 1/\sqrt{LC}$. $L$ is 0.1 millihenries, so that's $10^{-4}$, and $C$ is 1 microfarad, so that's $10^{-6}$, all under the square root. So we have $1/\sqrt{10^{-10}}$; that's $1/10^{-5}$, or just $10^5$, and that is in radians per second.

We can also compute the value of the transfer function at that cutoff frequency. If we look at this expression over here, we have $1$ over $1$ plus $j\omega L/R$: that's $j$ times $\omega$, which is $10^5$, and then $L/R$; $L$ is 0.1 millihenries, that's $10^{-4}$, and $R$ is 100 ohms, so that's $10^{-4}/10^2$, that's $10^{-6}$. (Let me write that 5 a little better here, $10^5$.) And then we have this term over here: $\omega$ is equal to $\omega_c$, so this is just $j^2$, which is $-1$. So this 1 and this $-1$ cancel each other out, and so what we get is $1/(0.1\,j)$, or $10/j$. That means that the magnitude of the transfer function at $\omega_c$ is equal to $20\log 10$, which is just 20 dB.

We can also see from the form that we have for $\mathbf H(\omega)$ that the magnitude of the transfer function at zero frequency, setting $\omega = 0$ here, we can see that $\mathbf H(\omega)$ is just equal to... sorry, the transfer function is just 1. So the magnitude of $\mathbf H(\omega)$ on the dB scale is $20\log 1$, which is 0 dB. We get this because $\mathbf H(0) = 1$.

So then, with this information, we can go ahead and draw the Bode magnitude plot. This is the magnitude of the transfer function in dB; we'll take this to be 0 dB, take this to be 20 dB, and then the cutoff frequency is $10^5$; this is $\omega$. We know that at zero frequency, and for frequencies much less than the cutoff frequency, the magnitude in dB is 0, because $\mathbf H$ is very close to 1. So that's going to be like this; I'm plotting this in green. Then we calculated over here that the magnitude of the transfer function on the dB scale at the cutoff frequency is 20 dB, so that's going to be up here; so this is going to look something like this. And then when we go to high frequencies, where $\omega$ is much greater than $\omega_c$, this quadratic term in the denominator is going to dominate, and the transfer function in terms of its magnitude is just going to go as $1/\omega^2$. So that is going to give us a slope of $-40$ dB per decade. So it's going to look something like this, where this slope is $-40$ dB per decade. So that is the magnitude Bode plot.

Then for the phase: we know that the phase at zero frequency, the transfer function is just 1 and the phase of that is 0, so the phase at zero frequency is $0^\circ$. At the cutoff frequency, we saw here that the transfer function is just $10/j$; the phase of $10/j$ is $-90^\circ$, because the phase of $j$ is $90^\circ$ and it's in the denominator. So the phase at $\omega_c$ is $-90^\circ$. And the phase at very high frequency, as we go to infinity: at very high frequency this term in the denominator is going to dominate, so we have basically $-\omega^2$ in the denominator; the phase of that is $-180^\circ$. It's $-180$, minus rather than plus 180; we know that'll have to be the case because at $\omega_c$ the phase is $-90^\circ$, not $+90^\circ$. [Narration says "90 degrees, not minus 90 degrees"; the page reads $\phi(\omega_c) = -90^\circ$, which is what the argument requires.]

So with that information, we can go ahead and construct the Bode phase plot. Let's say this is $10^4$, this is $10^5$, this is $10^6$. This is $0^\circ$, and then say $-90^\circ$ and $-180^\circ$, and we'll draw the Bode plot curve itself in green. At low frequencies, that is, below $10^4$ ($10^4$ is the cutoff frequency $10^5$ divided by 10), we're in the low-frequency limit; the phase is 0. At $\omega_c$ the phase is $-90$, and then at $10^6$, at very high frequency, so 10 times $\omega_c$ or higher, the phase is going to be $-180^\circ$, like this. And then we assume that the transition is linear, like this. So this is the Bode phase plot.

And then finally, what we're asked is to calculate the Bode plot slope for $\omega$ much greater than $\omega_c$, and we actually did that already up here: it's $-40$ dB per decade, and that's basically because at high frequencies the transfer function $\mathbf H$ goes as $1/\omega^2$. So, as noted in part (b), the slope of the magnitude plot at high frequency, that is, for $\omega$ much greater than the cutoff frequency, is $-40$ dB per decade. We were able to see this by noting that at high frequencies the transfer function basically goes as $1/(-\omega^2 LC)$; it's the $\omega^2$ part in the denominator that matters here. This is what we have for $\omega \gg \omega_c$. And so what happens is that a $10\times$ change in $\omega$ changes $\mathbf H(\omega)$ by $10^{-2}$; it divides it by 100, and a two-orders-of-magnitude decrease is $-40$ dB. So that's how we get $-40$ dB per decade.

### Key points (instructor retrospective)

So that's it for this example here. [No separate key-points segment was recorded for this video; the closing remarks above, restating that the $-40$ dB/dec slope follows from $\mathbf H \approx 1/(-\omega^2 LC)$ and that a $10\times$ change in $\omega$ gives a $10^{-2}\times$ change in $\mathbf H$, are the retrospective content, and are also written as part (c) on Page 3.]

## Index terms

Ulaby 9.33, Problem 9.33, Figure P9.33, low-pass filter, RLC filter, series inductor, shunt capacitor, shunt resistor, transfer function, $\mathbf H(\omega) = \mathbf V_o/\mathbf V_i$, standard form, KCL at output node, phasor KCL, $j\omega L$, $1/(j\omega C)$, multiply by $j\omega L$, $1 + j\omega L/R - \omega^2 LC$, $(j\omega/\omega_c)^2$, quadratic pole, cutoff frequency, $\omega_c = 1/\sqrt{LC}$, $10^5$ rad/s, $\mathbf H(\omega_c) = 10/j$, $M(\omega_c) = 20$ dB, resonance peak, $M(0) = 0$ dB, $\mathbf H(0) = 1$, Bode magnitude plot, Bode phase plot, $-40$ dB/dec, $\phi(0) = 0^\circ$, $\phi(\omega_c) = -90^\circ$, $\phi(\infty) = -180^\circ$, linear phase transition $10^4$ to $10^6$, $\mathbf H \approx 1/(-\omega^2 LC)$, $10\times$ change in $\omega$ gives $10^{-2}\times$, $R = 100\ \Omega$, $L = 0.1\ \text{mH}$, $C = 1\ \mu\text{F}$, Prof. Ed Yu, Chapter 9
