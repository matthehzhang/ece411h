---
course: ECE 411H
kind: problem-video
source: Problem Solving Videos/Ulaby 13.31.pdf
source_pages: 4
author: Prof. Ed Yu
unit: final
topics: [fourier-series, average-power, parallel-rlc, phasor-domain, node-voltage, kcl, superposition, orthogonality, units, ulaby-13.31]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
deepgram_transcript: deepgram/Ulaby_13.31.deepgram.txt
deepgram_paragraphs: deepgram/Ulaby_13.31.deepgram.md
---

# Ulaby 13.31 — Average power in a parallel RLC driven by a multi-frequency current source

**Summary.** Problem-solving video for Ulaby/Maharbiz/Furse Problem 13.31. A parallel RLC circuit ($R = 1\ \text{k}\Omega$, $L = 1$ H, $C = 1\ \mu\text{F}$) is driven by $i_s(t) = [10 + 5\cos(100t + 30^\circ) - \cos(200t - 30^\circ)]$ mA, which is already a (finite) Fourier series. Prof. Yu writes the phasor components at $\omega = 0, 100, 200$ rad/s, solves KCL at the top node for the current-to-voltage transfer function $V_1 = \frac{j\omega RL}{R(1-\omega^2 LC) + j\omega L}I_s$, evaluates it at each frequency (DC component is zero because the inductor shorts DC), converts back to the time domain ($v_1(t) = [502.5\cos(100t + 114.23^\circ) - 203.95\cos(200t + 48.23^\circ)]$ mV), and applies the Fourier-series average-power formula for a resistor, $P_{av} = V_{dc}^2/R + \sum \frac{1}{2}|V_n|^2/R$, to get $P_{av} = 1.471\times10^{-4}$ W $= 147.1\ \mu$W. Exam lessons: Fourier-series circuit analysis = phasors per frequency + superposition; only same-frequency voltage/current components contribute to average power; watch units (mA/mV give a $(10^{-3})^2$ factor).

> **Audio transcript (Deepgram nova-3, ECE 411 keyterms, timestamped):** `deepgram/Ulaby_13.31.deepgram.txt` ; paragraph form: `deepgram/Ulaby_13.31.deepgram.md`. Fresh ASR of the video audio; where it disagrees with the Narration section (built from the published auto-captions), prefer this file and the handwritten page.

## Problem statement

(Printed textbook excerpt pasted on page 1.)

13.31 The current source in the parallel RLC circuit of Fig. P13.31 is given by

$$i_s(t) = [10 + 5\cos(100t + 30^\circ) - \cos(200t - 30^\circ)]\ \text{mA}.$$

Determine the average power dissipated in the resistor given that $R = 1\ \text{k}\Omega$, $L = 1$ H, and $C = 1\ \mu$F.

**Figure P13.31: Circuit for Problem 13.31.** A current source $i_s(t)$ (arrow pointing up, circled in blue) in parallel with, left to right, an inductor $L$, a capacitor $C$, and a resistor $R$; all four elements share the same top and bottom nodes.

## Page 1

Header: Ulaby 13.31

(Printed problem statement and Figure P13.31 pasted at upper left, as transcribed above.)

Handwritten at upper right:

**Example:** average power calculations using Fourier series circuit analysis.

**Figure (redrawn circuit):** current source $i_s(t)$ with arrow pointing upward on the left branch; inductor $L$, capacitor $C$, resistor $R$ in parallel to its right; the top node is labeled $\underset{\sim}{V}_1$ and the bottom node is labeled $V = 0$. To the right of the circuit:

$R = 1\ \text{k}\Omega$
$L = 1\ \text{H}$
$C = 1\ \mu\text{F}$

$$i_s(t) = \left[10 + 5\cos(100t + 30^\circ) - \cos(200t - 30^\circ)\right]\ \text{mA}$$

Find average power, $P_{av}$, dissipated in $R$.

1) take the Fourier series expression for $i_s(t)$ and express $\underset{\sim}{I}_s$ in phasor domain:

$$i_s(t) = \left[10 + 5\cos(100t + 30^\circ) - \cos(200t - 30^\circ)\right]\ \text{mA}$$

$$\Rightarrow\ \underset{\sim}{I}_s = \left[10 + 5e^{j30^\circ} - e^{-j30^\circ}\right]\ \text{mA}.$$

(arrows under each term label the frequency: $10 \to \omega = 0$; $5e^{j30^\circ} \to \omega = 100$ rad/s; $e^{-j30^\circ} \to \omega = 200$ rad/s)

2) analyze circuit in phasor domain to obtain $\underset{\sim}{V}_1$:

(continues on page 2)

## Page 2

2) analyze circuit in phasor domain to obtain $\underset{\sim}{V}_1$: (repeated heading, partly cut off)

$$\text{KCL @ } V_1:\quad -\underset{\sim}{I}_s + \frac{\underset{\sim}{V}_1}{j\omega L} + \frac{\underset{\sim}{V}_1}{\frac{1}{j\omega C}} + \frac{\underset{\sim}{V}_1}{R} = 0$$

$$\Rightarrow\ \left(\frac{1}{R} + \frac{1}{j\omega L} + j\omega C\right)\underset{\sim}{V}_1 = \underset{\sim}{I}_s,\ \text{or}$$

$$\underset{\sim}{V}_1 = \frac{\underset{\sim}{I}_s}{\frac{1}{R} + \frac{1}{j\omega L} + j\omega C}\cdot\left(\frac{j\omega RL}{j\omega RL}\right)$$

(the multiplying factor $\frac{j\omega RL}{j\omega RL}$ is written in green)

$$= \frac{j\omega RL}{R + j\omega L - \omega^2 RLC}\,\underset{\sim}{I}_s$$

$$= \frac{j\omega RL}{R(1 - \omega^2 LC) + j\omega L}\,\underset{\sim}{I}_s$$

3) convert to time domain, then compute $P_{av}$

$$\underset{\sim}{V}_1 = \frac{\omega RL}{\sqrt{R^2(1-\omega^2 LC)^2 + \omega^2 L^2}}\;e^{-j\tan^{-1}\frac{\omega L}{R(1-\omega^2 LC)}}\;e^{j90^\circ}\;\underset{\sim}{I}_s$$

$$= \frac{1000\,\omega}{\sqrt{10^6(1 - 10^{-6}\omega^2)^2 + \omega^2}}\;e^{-j\tan^{-1}\frac{\omega}{10^3(1-10^{-6}\omega^2)}}\;e^{j90^\circ}\;\underset{\sim}{I}_s$$

$$\underset{\sim}{V}_1(\omega = 0) = 0$$

$$\underset{\sim}{V}_1(\omega = 100) = \frac{10^5}{\sqrt{10^6(1-10^{-2})^2 + 10^4}}\;e^{-j\tan^{-1}\frac{10^2}{10^3(1-10^{-2})}}\;e^{j90^\circ}\;\underset{\sim}{I}_s(\omega = 100)$$

(the bottom of the page shows the top of the next line: "$= 100.5\,e^{j84.232^\circ}\,\underset{\sim}{I}_s(\omega=100);\ \underset{\sim}{I}_s(\omega=100) = 5e^{j30^\circ}$", continued on page 3)

## Page 3

(Top: cut-off repeat of the $\underset{\sim}{V}_1(\omega=100)$ line, denominator $\sqrt{10^6(1-10^{-2})^2 + 10^4}$.)

$$= 100.5\,e^{j84.232^\circ}\;\underset{\sim}{I}_s(\omega = 100);\qquad \underset{\sim}{I}_s(\omega = 100) = 5e^{j30^\circ}$$

$$= 502.5\,e^{j114.23^\circ}$$

$$\underset{\sim}{V}_1(\omega = 200) = \frac{2\times10^5}{\sqrt{10^6(1 - 4\times10^{-2})^2 + 4\times10^4}}\;e^{-j\tan^{-1}\frac{200}{10^3(1-4\times10^{-2})}}\;e^{j90^\circ}\;\underset{\sim}{I}_s(\omega = 200)$$

$$= 203.95\,e^{j78.23^\circ}\;\underset{\sim}{I}_s(\omega = 200);\qquad \underset{\sim}{I}_s(\omega = 200) = -e^{-j30^\circ}$$

$$= -203.95\,e^{j48.23^\circ}$$

$$\Rightarrow\ v_1(t) = \left[502.5\cos(100t + 114.23^\circ) - 203.95\cos(200t + 48.23^\circ)\right]\ \text{mV}$$

Recall that

$$P_{av} = \frac{1}{T}\int_0^T v(t)\,i(t)\,dt$$

$$= V_{dc}I_{dc} + \sum_{n=1}^{\infty}\frac{1}{2}V_n I_n\cos(\phi_{v_n} - \phi_{i_n})$$

For a resistor, $i(t) = v(t)/R \ \Rightarrow\ \phi_{v_n} = \phi_{i_n}$, and

$$P_{av} = V_{dc}I_{dc} + \sum_{n=1}^{\infty}\frac{1}{2}|V_n I_n| = \frac{V_{dc}^2}{R} + \sum_{n=1}^{\infty}\frac{1}{2}\frac{|V_n|^2}{R}$$

$$= 0 + \frac{1}{2}\left(\frac{1}{10^3}\right)\left(502.5^2 + 203.95^2\right)\underbrace{\left(10^{-3}\right)^2}_{\text{since } V_n \text{ were computed in mV.}}$$

(the result box begins at the bottom of the page and is repeated on page 4)

## Page 4

(Top: cut-off end of the annotation "computed in mV.")

$$\Rightarrow\ \boxed{P_{av} = 1.471\times10^{-4}\ \text{W} = 147.1\ \mu\text{W}}$$

**Key points:**

(i) For Fourier series circuit analysis, compute (or recognize) Fourier series for known input voltages/currents, then analyze circuit in phasor domain, using superposition to combine multiple frequencies.

(ii) only voltage + frequency components at the same frequency as each other contribute to average power dissipation. [Written as "voltage + frequency"; from the narration, intended meaning is "voltage and current components at the same frequency".]

(iii) be careful in making sure to work with consistent units.

The rest of the page is blank.

## Narration transcript

Okay, so this is Ulaby problem 13.31. And this is an example here of average power calculations. Okay. So, as an example of average power calculations using Fourier series circuit analysis.

Okay, so what we have here is a problem where we are given — we have this circuit down here, so an RLC parallel circuit, and we're given the form of the current source here, essentially as a Fourier series already. And the problem is asking us to compute the average power that's dissipated in the resistor, given these values here for the circuit components.

Okay, so let's go ahead and redraw the circuit as usual. Okay, so we have a current source, $i_s(t)$, an inductor $L$, a capacitor $C$, and a resistor $R$. Okay. And these are all connected in parallel. All right. And the resistance is one kilohm, the inductor is one henry, and the capacitor is one microfarad, and the current source $i_s(t)$ is 10 plus 5 times the cosine of $100t + 30^\circ$ minus the cosine of $200t - 30^\circ$, and that's in milliamps. Okay, and the question is to find the average power — I'll call it $P_{av}$ — all right, that's dissipated in the resistor $R$.

Okay. So to solve this problem, what we want to do is to take this expression for $i_s(t)$ and convert it to the phasor domain. All right, then analyze the circuit in the phasor domain, and obtain the current and/or the voltage for the resistor $R$, from which we can then calculate the power. Okay, so that's the process that we'll go through.

So the first step here is to basically take the Fourier series expression — for which, essentially, we pretty much have that already — and then express $\underset{\sim}{I}_s$, all right, the corresponding phasor quantity, in the phasor domain. Okay, so we have that $i_s(t)$, all right, is equal to 10 plus 5 times the cosine of $100t + 30^\circ$ minus the cosine of $200t - 30^\circ$, in milliamps. Okay, so, in the phasor domain, right, we can see that we have a frequency component at $\omega$ equal to 0, another at $\omega$ equal to 100 radians per second, and a third at $\omega$ equal to 200 radians per second. So in the phasor domain we can write $\underset{\sim}{I}_s$ as being 10 — all right, that is the $\omega$ equal to 0 component — plus 5 times $e^{j30^\circ}$, that's from this term here, which is the frequency component at $\omega$ equal to 100 radians per second, and then minus $e^{-j30^\circ}$, all right, that is from this term over here, that is the frequency component at $\omega$ equal to 200 radians per second. All right, all of this again in milliamps. Okay. So going to the phasor domain, once we had the Fourier series expansion for $i_s$, going to the phasor domain actually was very straightforward. Part of that was also that these components here are already in the standard cosine form, all right, so we didn't have to convert them to the standard cosine form.

So once we have that, then the second step is to look at the circuit and analyze it in the phasor domain to obtain the voltage and/or the current for the resistor $R$. So to do that we'll take the voltage at the bottom node here to be 0. Then the voltage at this upper node we'll take to be $V_1$, and we'll do a simple node voltage analysis, essentially calculating, or using, KCL at the node $V_1$ to solve for the voltage $V_1$, which is just the voltage across the resistor as well, and from that we'll be able to calculate the current — all right, sorry, the power. Okay. So what we want to do, then, is to analyze the circuit in the phasor domain to obtain the voltage that we labeled $V_1$ as a phasor. So we're going to apply KCL at that upper node $V_1$, okay? And when we do that, we have the current coming in from the left from the current source — oh, sorry, the current going out to the left along the branch containing the current source, that's going to be minus $\underset{\sim}{I}_s$, all right, because we have $I_s$ going in. Then the current flowing down through the inductor, that's going to be $V_1$ over the impedance of the inductor, which is $j\omega L$; plus the current flowing down through the capacitor, which is $V_1$ over the impedance of the capacitor, which is one over $j\omega C$; plus the current flowing downward through the resistor, which is just $V_1$ over $R$. All of that has to add up to 0. Okay. And if we group together the terms proportional to $V_1$, we have one over $R$ plus one over $j\omega L$ plus $j\omega C$, times $V_1$, is equal to $\underset{\sim}{I}_s$. All right, or if we divide both sides of this equation by this quantity here in the parentheses to solve for $V_1$, we get that $V_1$ is equal to $I_s$ divided by one over $R$ plus one over $j\omega L$ plus $j\omega C$. All right.

So now, to further simplify this, we can multiply the numerator and the denominator by $j\omega R$ times $L$. Okay. And that will get rid of the fractions, right, in the denominator. And so this will give us in the numerator $j\omega R$ times $L$, right — we'll write down the $I_s$ at the end — and in the denominator, from $j\omega RL$ times one over $j\omega L$ we get $R$, all right; from $j\omega RL$ times one over $R$ we get plus $j\omega L$; and then from $j\omega C$ times $j\omega RL$ we get minus $\omega^2 RLC$; all of this times $I_s$, okay? And then we can group together the real and imaginary terms in the denominator. So we get $j\omega RL$ in the numerator, and then $R$ times $(1 - \omega^2 LC)$ plus $j\omega L$ in the denominator, all this times $I_s$. Okay, so that is $V_1$, which is the voltage at the upper node, also the voltage across the resistor, in the phasor domain.

Right now, what we want to do is convert to the time domain, then compute the average power. All right. We could directly calculate $V_1$ explicitly by substituting in $I_s$ as a phasor over here, and then, using what we know and worked out in class to be the result for the average power, then we don't necessarily have to go back to the time domain explicitly, but in order to see a little bit more about how this problem works, we will actually convert back to the time domain. All right, so let's go ahead now and plug in the phasor expression for $I_s$, and also work with this prefactor over here — basically the current-to-voltage transfer function — all right, by converting this prefactor over here from its current form to the polar form, all right, where the polar form is going to be helpful in working conveniently with the phase factors in the phasor domain.

Okay, so converting that prefactor into polar form, all right, what we need is the magnitude, right, which is going to be the magnitude of the numerator divided by the magnitude of the denominator. The magnitude of the numerator is just $\omega$ times $R$ times $L$. The magnitude of the denominator is the square root of the real part squared plus the imaginary part squared. So it's going to be the square root of $R^2$ times $(1 - \omega^2 LC)$ quantity squared plus $\omega^2 L^2$, all of this under the square root, and then we have the phase, which is $e$ to the minus $j$ times the inverse tangent of the imaginary part of the denominator divided by the real part of the denominator, so $\omega L$ divided by $R$ times $(1 - \omega^2 LC)$. Okay? And then, finally, right, we have this minus sign in the exponent of the phase factor, because without the minus sign, that would be the phase of the denominator. But we're writing this in the numerator, so we have to put a minus sign in the exponent. Then, finally, we have this factor of $j$ over here; we can't forget about that. That's $e^{j90^\circ}$. All this times $I_s$.

All right! Now we can plug in numerical values for $R$, $L$ and $C$. All right, so $R$ was one kilohm, $L$ was one henry, $C$ is one microfarad, so $10^{-6}$ farads. Okay. So plugging those in, then in the numerator we have $R$, 1000, times $L$, one, times $\omega$, so we get a thousand $\omega$, divided by the square root of $R^2$ — it's $10^3$ squared, that's $10^6$ — times one minus, and then $L$ times $C$ is one times $10^{-6}$, so $10^{-6}$ times $\omega^2$, quantity squared, and then plus $\omega^2 L^2$ — $L$ is one, so just $\omega^2$ — all this under the square root. Then we have $e$ to the minus $j$ times the inverse tangent, now, of $\omega L$, which is just $\omega$ since $L$ is equal to one, divided by $R$, which is $10^3$, times one minus $\omega^2 LC$, which is $10^{-6}\omega^2$. Okay. And then times $e^{j90^\circ}$ times $I_s$.

All right. So now from this we can compute $V_1$ at the frequencies that we know show up in $I_s$, which are 0, 100, 200. Okay, so $V_1$ at $\omega$ equal to 0, all right, we can see, because of this $\omega$ in the numerator here, then that's just going to be 0. Okay, so that means that there's no DC component to the voltage across the resistor, even though there is a DC component to the current $I_s$. And if we look back at the circuit, we can see that at zero frequency this inductor is going to behave as a short circuit. So this node and this node are short-circuited to each other. So it makes sense that the DC component of the voltage is 0. Okay, so that's a quick little check there that this result makes sense.

Then we can compute $V_1$ at $\omega$ equal to 100, okay, using this expression up here, right? So we have a thousand times a hundred, that's $10^5$, divided by $10^6$ times one minus $10^{-6}$ times a hundred squared — that's $10^4$, so one minus $10^{-2}$ — squared, plus $\omega^2$, that's $10^4$. Okay, times $e$ to the minus $j$ times the inverse tangent of $\omega$, $10^2$, over $10^3$ times one minus $10^{-2}$. All right, then times $e^{j90^\circ}$ times $I_s$ at $\omega$ equal to 100. All right, and if we calculate out all these numerical values over here, then we get 100.5, all right, that's this expression here, all right, times $e$ to the $j$ times $84.232^\circ$ — that includes this $e^{j90^\circ}$ factor over here — times $I_s$ at $\omega$ equal to 100. All right, from our earlier expression that we worked out for $I_s$ in the phasor domain, at a hundred radians per second $I_s$ was 5 times $e^{j30^\circ}$. All right, so $I_s$ at $\omega$ equal to 100 was $5e^{j30^\circ}$. So if we plug that in here for $I_s$, then we get 5 times 100.5, that's 502.5, times $e$ to the $j$, and then 30 plus 84.232, that's $114.23^\circ$. Okay? So that's $V_1$ at $\omega$ equal to 100 radians per second.

And then at 200, all right, we get, from the expression up here, all right, it's 1000 times 200, that's $2\times10^5$, divided by the square root of $10^6$ times one minus — the $\omega^2$ is $4\times10^4$, so $4\times10^{-2}$ — squared, plus $4\times10^4$, all this under the square root; $e$ to the minus $j$ the inverse tangent of 200 — right, that's $\omega$ — divided by $10^3$ times one minus $4\times10^{-2}$; all right, times $e^{j90^\circ}$ times $I_s$ at $\omega$ equal to 200. All right! And if we work out the numbers here, then for this magnitude over here we get 203.95, and then from the phase factors, the two phase factors together, we get $e$ to the $j$ $78.23^\circ$. That's going to be times $I_s$ at $\omega$ equal to 200. All right, if we look back again at what we worked out here for $I_s$ in the phasor domain, the component at $\omega$ equal to 200 is minus $e^{-j30^\circ}$. Okay, so $I_s$ at $\omega$ equal to 200 is equal to minus $e$ to the minus $j$ times $30^\circ$. All right, and so this is going to be equal to minus 203.95 times $e$ to the $j$ $48.23^\circ$. All right, or if we wanted to, we could take this minus sign over here and include it in the phase, if we wanted. But it turns out not to matter if we do that.

Okay, so having worked out those components of $V_1$ in the phasor domain, then what we get in the time domain is that $v_1(t)$ is equal to 502.5 times the cosine of $100t + 114.23^\circ$ — all right, that's from this result here, right, for the phasor component of $V_1$ at $\omega$ equal to 100; all right, so we get the same amplitude, and then we get this phase $114.23^\circ$ over here in the standard cosine form, at an angular frequency of a hundred radians per second — and then similarly we get minus 203.95, that's this over here, times the cosine of $200t + 48.23^\circ$, and all of this is in millivolts.

Okay, so how do we take this and compute the average power? All right. So let's recall that in general the average power, okay, it's going to be the average over one cycle of the voltage times the current. All right, and we worked out in class that this was equal to, all right, if we express the voltage and the current in their Fourier series forms, it's the product of the DC components, plus the sum from $n$ going from one to infinity of one half times the voltage amplitude times the current amplitude times the cosine of the phase difference between the voltage and the current at that frequency. Okay. Now for a resistor, the current, all right, in general is just the voltage divided by the resistance; that's just Ohm's law, right? Since the resistance is purely real, then the phases of the voltage and the current, they're equal to each other. All right! And when they're equal, then this cosine factor over here is always equal to one. All right, so for a resistor the average power is just $V_{dc}$ times $I_{dc}$ plus the sum from $n$ going from one to infinity of one half, and then it's the magnitude of $V_n$ times $I_n$. All right, so that's going to be $V_{dc}^2$ over $R$, right, again just using Ohm's law, plus the sum from $n$ going from one to infinity of one half $|V_n|^2$ over $R$.

Okay. And so, to compute the average power, right, having computed the Fourier series components of the voltage already — so the voltage has zero DC component, so this doesn't contribute anything, all right, so that's 0. And then we have plus one half — that's this one half over here — times one over $10^3$, all right, that's the one over $R$ over here since $R$ is one kilohm, and then we have the sum of the voltage amplitudes, right, at the different frequencies, so $502.5^2$ plus $203.95^2$, and then those were amplitudes in millivolts. So if we want the average power in watts, we have to multiply by $10^{-3}$ to convert the voltages to volts, and then squared, since we're taking the voltages squared, right? So this factor here is included because the $V_n$'s were computed in millivolts. Okay? And so then, if we just calculate out these numbers, then what we get is that the average power is $1.471\times10^{-4}$ watts, or we can express it in microwatts: it's 147.1 microwatts. Okay, so that's the answer for this example.

### Key points (instructor retrospective)

And now, if we look back on what we did and think about what some of the key points were in this example, one is, all right, basically what we did was, in doing the Fourier series circuit analysis, what we did was we computed the Fourier series for the known input voltages and currents — in this case we were basically given that information — then we converted that to the phasor domain, okay, and then we analyzed the circuit in the phasor domain, right, which is a relatively straightforward thing to do; we know how to do it from earlier in the semester at a single frequency; then we use the idea of superposition to combine the multiple frequencies in the Fourier series expansion together. We can do that for voltages and currents, since those are linear quantities and we have a linear circuit. All right, so that first point is that, for Fourier series circuit analysis in general, all right, what we want to do is to compute, or in this case really to recognize, the Fourier series for our known input voltages and/or currents. All right, then, once we have those components, each of which is at a specific frequency, then we analyze the circuit in the phasor domain, all right, which works at a particular frequency, and then we can use the idea of superposition — right, we don't really have to use it explicitly; we're using it implicitly in doing the Fourier series analysis — so we're using superposition to combine our results from multiple frequencies.

Okay. The second point is that, from what we've worked out in class, all right, we saw that only the voltage and current components that are at the same frequencies as each other, right, contribute to the average power dissipation. So here we just want to recognize that, all right, that only the voltage and current frequency components at the same frequency as each other, all right, contribute to the average power dissipation. Okay, and that's basically because of the nature of the trigonometric integrals that are involved. So the cross terms will essentially all end up going to 0. All right, and so we only have to take, right, we basically take the square of each individual frequency combination.

And then finally, you'll notice that at the end, right, we were given the current, and therefore we calculated the voltage, in milliamps and millivolts respectively. But we had to remember at the end to include this factor of $10^{-3}$ for each, and so in the calculation of power, $10^{-3}$ squared, in order to get the power in watts, all right, and then we could convert that to whatever other unit we want; in this case we converted it to microwatts, right? So we want to be careful in general in making sure to work with consistent units. Okay.

## Index terms

Ulaby 13.31, Problem 13.31, Fourier series circuit analysis, average power, P_av, parallel RLC circuit, current source, phasor domain, phasor I_s, frequency components omega = 0 100 200 rad/s, standard cosine form, node voltage analysis, KCL, inductor impedance j omega L, capacitor impedance 1/(j omega C), transfer function V_1/I_s = j omega RL / (R(1 - omega^2 LC) + j omega L), polar form, magnitude and phase, inverse tangent, e^{j90 degrees}, DC component zero (inductor shorts DC), V_1(omega=100) = 502.5 e^{j114.23 deg} mV, V_1(omega=200) = -203.95 e^{j48.23 deg} mV, v_1(t) time domain, P_av = V_dc I_dc + sum (1/2) V_n I_n cos(phi_v - phi_i), resistor phi_v = phi_i, P_av = V_dc^2/R + sum (1/2)|V_n|^2/R, orthogonality of different frequencies, cross terms vanish, superposition, unit conversion mA mV (10^-3)^2, P_av = 1.471e-4 W = 147.1 microwatt, R = 1 kilohm, L = 1 H, C = 1 microfarad, Fig. P13.31, Ulaby/Maharbiz/Furse
