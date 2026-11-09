---
course: ECE 411H
kind: problem-video
source: Problem Solving Videos/Ulaby 9.4.pdf (captions: Problem Solving Videos/Ulaby 9.4 captions.vtt)
source_pages: 2
author: Prof. Ed Yu
unit: exam2
topics: [resonance, resonant-frequency, rlc-circuit, input-impedance, phasor-analysis, parallel-impedance, series-lc, short-circuit-at-resonance, chapter-9]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
deepgram_transcript: deepgram/Ulaby_9.4.deepgram.txt
deepgram_paragraphs: deepgram/Ulaby_9.4.deepgram.md
---

# Ulaby 9.4 — Resonant frequency of a simple RLC circuit (problem-solving video)

**Summary.** Prof. Yu works Ulaby/Maharbiz/Furse Problem 9.4: find the resonant frequency of a two-terminal circuit consisting of a resistor $R = 1\ \text{k}\Omega$ in parallel with a series $L = 10\ \text{mH}$, $C = 10\ \text{nF}$ branch, where "resonant frequency" is defined as the frequency at which the input impedance $\tilde Z_i$ is purely real. He computes $\tilde Z_i$ as a parallel combination, rationalizes it into rectangular form, sets the imaginary part to zero, and gets $\omega_0 = 1/\sqrt{LC} = 10^5\ \text{rad/s}$. The retrospective emphasizes that at resonance the series $L$–$C$ branch has zero impedance, so the input terminals are shorted and $\tilde Z_i \to 0$ (both real and imaginary parts vanish), i.e. a tiny applied voltage gives a very large current, a hallmark of resonance. Exam relevance: the definition of resonance (Im$\{Z_i\}=0$), the product-over-sum parallel formula, and the "interpret what happens physically at $\omega_0$" step.

> **Audio transcript (Deepgram nova-3, ECE 411 keyterms, timestamped):** `deepgram/Ulaby_9.4.deepgram.txt` ; paragraph form: `deepgram/Ulaby_9.4.deepgram.md`. Fresh ASR of the video audio; where it disagrees with the Narration section (built from the published auto-captions), prefer this file and the handwritten page.

## Problem statement

**9.4** Determine the resonant frequency of the circuit shown in Fig. P9.4, given that $R = 1\ \text{k}\Omega$, $L = 10\ \text{mH}$, and $C = 10\ \text{nF}$.

**Figure P9.4 (Circuit for Problem 9.4):** Two open input terminals on the left (top and bottom). From the top terminal a wire runs right; a resistor $R$ hangs vertically between the top wire and the bottom wire (directly after the terminals). Continuing right along the top wire is an inductor $L$, then the wire turns down through a capacitor $C$ to the bottom wire. So: $R$ is in parallel with the series combination of $L$ and $C$, all across the input terminals.

(Narration clarifies: the resonant frequency means the frequency at which the input impedance $\tilde Z_i$, the impedance seen between the two terminals, is purely real.)

## Page 1

Header: "Ulaby 9.4". The textbook problem statement and Figure P9.4 are pasted at the top left (as above).

Handwritten, top right:

**Example:** resonant frequency of a simple RLC circuit

**Figure (redrawn circuit):** Two terminals at left, marked with an arrow and $\tilde Z_i \rightarrow$ (input impedance looking into the terminals). Resistor $R$ vertical between top and bottom rails just to the right of the terminals. Inductor $L$ in the top rail to the right of $R$; capacitor $C$ at the far right connecting the top rail down to the bottom rail. ($R \parallel (L \text{ series } C)$.)

$R = 1\ \text{k}\Omega$, $L = 10\ \text{mH}$, $C = 10\ \text{nF}$

Determine resonant frequency (input impedance $\tilde Z_i$ is purely real).

$$\tilde Z_i = \frac{R\left(j\omega L + \frac{1}{j\omega C}\right)}{R + j\omega L + \frac{1}{j\omega C}} = \frac{R(1 - \omega^2 LC)}{1 - \omega^2 LC + j\omega RC}$$

$$\tilde Z_i = \frac{R(1-\omega^2 LC)(1 - \omega^2 LC - j\omega RC)}{(1-\omega^2 LC)^2 + \omega^2 R^2 C^2}$$

$$= \frac{R(1-\omega^2 LC)^2 - j\omega R^2 C\,(1-\omega^2 LC)}{(1-\omega^2 LC)^2 + \omega^2 R^2 C^2}$$

$\operatorname{Im}(\tilde Z_i) = 0$ when $1 - \omega^2 LC = 0$

$$\Rightarrow\ \omega = \frac{1}{\sqrt{LC}} = \frac{1}{\sqrt{10^{-2}\cdot 10^{-8}}} = \boxed{10^5\ \text{rad/s} = \omega}$$

(The final result $10^5\ \text{rad/s} = \omega$ is boxed.)

## Page 2

**Key points:**

(i) phasor analysis of circuit was relatively simple

(ii) what happens at the resonant frequency? In this case, $\tilde Z_i \to 0$ since the branch with $L + C$ in series has zero impedance (short circuit between input terminals).

(Rest of page blank.)

## Narration transcript

Okay, so this is Ulaby problem 9.4, and this is an example of calculating the resonant frequency of a simple RLC circuit. So we will start as usual by redrawing the circuit. Our circuit is very simple here: it has a resistor of value $R$, then an inductor of value $L$, and a capacitor of value $C$. Our circuit parameters here are that $R$ is 1 kilohm, $L$ is 10 millihenries, and $C$ is 10 nanofarads. What we're asked to do here is to determine the resonant frequency of the circuit, and what we mean here by the resonant frequency is the frequency at which the input impedance, which we'll call $Z_i$, that is, the impedance between these two terminals here, is purely real. If we were to connect something to these terminals out here, then what would the impedance of this circuit look like? That's what $Z_i$ is. And the resonant frequency is the frequency at which the input impedance, which we've called $Z_i$ here, is purely real.

So this is a fairly straightforward calculation. Essentially what we can do to calculate the input impedance is to just calculate the impedance of this resistor in parallel with the series connection of the inductor and the capacitor. So we can pretty much calculate that directly. Any time you have two impedances in parallel, the equivalent impedance is the product of the two impedances divided by the sum. So the product is $R$ times the other impedance, which is that of the inductor and the capacitor in series with each other: we have $j\omega L$ for the inductor plus $1/(j\omega C)$ for the capacitor. And then we divide by the sum of the impedances, which is $R + j\omega L + 1/(j\omega C)$. If we take this and multiply both the numerator and the denominator by $j\omega C$, then in the numerator we get $R$ times $(1 - \omega^2 LC)$, and in the denominator we get $1 - \omega^2 LC + j\omega RC$. So this is now our expression for the input impedance $Z_i$.

In order to determine the frequency at which this quantity is purely real, what we want to do is to put it in the standard rectangular form. To do that we will, as usual, multiply the numerator and the denominator by the complex conjugate of the denominator, that is, by $1 - \omega^2 LC - j\omega RC$. If we do that, then what we get is that the input impedance is $R(1-\omega^2 LC)$ times $(1 - \omega^2 LC - j\omega RC)$, and then in the denominator we have basically the magnitude squared of this quantity up here in the denominator, so that is going to be $(1-\omega^2 LC)^2 + \omega^2 R^2 C^2$. If we then take this and, in the numerator, separate out the real and imaginary parts, what we get for the real part is $R(1-\omega^2 LC)$ times the real part of this term in the parentheses here, which is $1-\omega^2 LC$; so we have $R(1-\omega^2 LC)^2$. And then the imaginary part of the numerator is this $-j\omega RC$ times $R(1-\omega^2 LC)$, so we have $-j\omega R^2 C(1-\omega^2 LC)$. The denominator is still the same: $(1-\omega^2 LC)^2 + \omega^2 R^2 C^2$.

So now we can see that the imaginary part of $Z_i$ is zero when this second term here in the numerator is zero, and we can see that that happens when $1 - \omega^2 LC = 0$, or equivalently $\omega = 1/\sqrt{LC}$. So we can easily see now that the imaginary part of $Z_i$ is equal to zero when $1 - \omega^2 LC = 0$, which means that $\omega = 1/\sqrt{LC}$. That is $1$ over the square root of: $L$, remember, was 10 millihenries, so that is $10^{-2}$ (10 times $10^{-3}$), and $C$ was 10 nanofarads, so that is $10^{-8}$. So that is the square root of $10^{-10}$, which is $10^{-5}$; it's in the denominator, so that then becomes $10^5$ radians per second. That is the resonant frequency of this circuit. And that's essentially all there is to solving this problem.

### Key points (instructor retrospective)

So what are the key points here? One is that this was really just a very simple phasor analysis. The phasor analysis of this circuit really was relatively simple. But then the second part of this is kind of what was the point of this problem, or perhaps more precisely: what happens at the resonance frequency? If we look up at the circuit over here, we can see that basically the resonant frequency $\omega = 1/\sqrt{LC}$ corresponds to the frequency at which the impedances of the inductor and the capacitor (since they're in series, we just add those together) cancel each other out, because the impedance of the inductor is $j\omega L$ and the impedance of the capacitor is $1/(j\omega C)$, or equivalently $-j/(\omega C)$. So it's possible at the resonant frequency for the total impedance to be zero. Then this branch here will be a short circuit, and when this is a short circuit, the resistor ends up not playing any role in the circuit, and so the input impedance will actually be zero. So that's what the resonant frequency corresponds to in this case.

And in fact, from this expression here we can see that indeed, because of this $(1 - \omega^2 LC)^2$ factor here in the real part of $Z_i$, we can easily confirm mathematically that at the resonant frequency the real part and the imaginary part of the input impedance are both zero, so the total input impedance is zero. So what's happening here at the resonant frequency, in this particular case, is that the input impedance goes to zero, and that happens because the branch with the inductor and the capacitor in series has zero impedance; so basically you have a short circuit between the input terminals. And so if you have even a little bit of voltage applied between those terminals, then you get a very large current: a very large response for a very small input. That is in general a characteristic that you often see in a resonant circuit or other resonant system, and we see that very explicitly in the case of this very simple circuit here. Okay, so then.

## Index terms

Ulaby 9.4, Problem 9.4, Figure P9.4, resonant frequency, resonance, input impedance, $\tilde Z_i$, purely real impedance, RLC circuit, resistor in parallel with series LC, parallel impedance product over sum, $j\omega L$, $1/(j\omega C)$, $-j/(\omega C)$, multiply numerator and denominator by $j\omega C$, complex conjugate of denominator, rectangular form, real part, imaginary part, $\operatorname{Im}(Z_i)=0$, $1-\omega^2 LC = 0$, $\omega_0 = 1/\sqrt{LC}$, $10^5$ rad/s, $R = 1\ \text{k}\Omega$, $L = 10\ \text{mH}$, $C = 10\ \text{nF}$, phasor analysis, short circuit at resonance, zero impedance branch, large response to small input, key points, Prof. Ed Yu, Chapter 9
