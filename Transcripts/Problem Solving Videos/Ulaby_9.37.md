---
course: ECE 411H
kind: problem-video
source: Problem Solving Videos/Ulaby 9.37.pdf (captions: Problem Solving Videos/Ulaby 9.37 captions.vtt)
source_pages: 3
author: Prof. Ed Yu
unit: exam2
topics: [op-amp-filter, high-pass-filter, non-inverting-amplifier, transfer-function, standard-form, bode-plots, simple-zero, simple-pole, corner-frequency, maximum-gain, kcl-at-inverting-input, ideal-op-amp, limiting-behavior-check, chapter-9]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
deepgram_transcript: deepgram/Ulaby_9.37.deepgram.txt
deepgram_paragraphs: deepgram/Ulaby_9.37.deepgram.md
---

# Ulaby 9.37 — Op-amp high-pass filter: transfer function, Bode plots, filter type and maximum gain (problem-solving video)

**Summary.** Prof. Yu works Ulaby/Maharbiz/Furse Problem 9.37: a non-inverting op-amp stage whose feedback network is $R_2$ from output to inverting input and a series $R_1$–$C$ from the inverting input to ground; $\mathbf V_s$ drives the non-inverting input. (a) KCL at the inverting input (held at $\mathbf V_s$ by the ideal-op-amp rule) gives $\mathbf H(\omega) = \mathbf V_o/\mathbf V_s = \big[1 + j\omega(R_1+R_2)C\big]/\big[1 + j\omega R_1 C\big]$, a simple zero at $\omega_{c1} = 1/((R_1+R_2)C)$ and a simple pole at $\omega_{c2} = 1/(R_1 C)$. (b) With $R_1 = 1\ \text{k}\Omega$, $R_2 = 4\ \text{k}\Omega$, $C = 1\ \mu\text{F}$: $\omega_{c1} = 200$ rad/s, $\omega_{c2} = 1000$ rad/s; $M(0) = 0$ dB, $M(\infty) = 20\log 5 = 13.98 \approx 14$ dB; $\phi(0) = \phi(\infty) = 0^\circ$ with a $+45^\circ$/dec rise from 20 to 100 rad/s, a plateau, then a $-45^\circ$/dec fall from 2000 to $10^4$ rad/s. (c) It is a high-pass filter with maximum gain 14 dB, or $(R_1+R_2)/R_1 = 5$. Key points: straightforward op-amp analysis; Bode plots the "usual" way (cf. Ulaby 9.19); check that the result matches the DC limit ($C$ open, $\mathbf V_o = \mathbf V_s$) and the high-frequency limit ($C$ short, ordinary non-inverting amplifier with gain $1 + R_2/R_1$). Exam relevance: zero-below-pole gives high-pass with finite gain; always sanity-check against open/short capacitor limits.

> **Audio transcript (Deepgram nova-3, ECE 411 keyterms, timestamped):** `deepgram/Ulaby_9.37.deepgram.txt` ; paragraph form: `deepgram/Ulaby_9.37.deepgram.md`. Fresh ASR of the video audio; where it disagrees with the Narration section (built from the published auto-captions), prefer this file and the handwritten page.

## Problem statement

**9.37** For the op-amp circuit of Fig. P9.37:
*(a) Obtain an expression for $\mathbf H(\omega) = \mathbf V_o/\mathbf V_s$ in standard form.
(b) Generate spectral plots for the magnitude and phase of $\mathbf H(\omega)$, given that $R_1 = 1\ \text{k}\Omega$, $R_2 = 4\ \text{k}\Omega$, and $C = 1\ \mu\text{F}$.
(c) What type of filter is it? What is its maximum gain?

**Figure P9.37 (Circuit for Problem 9.37):** An op-amp with inverting input ($-$) on top and non-inverting input ($+$) below. Feedback resistor $R_2$ from the op-amp output back to the inverting input. From the inverting input a wire runs left, then down through $R_1$ and then $C$ (in series) to ground. Source $\mathbf V_s$ (+ terminal up) connects from ground to the non-inverting input. Output $\mathbf V_o$ is taken between the op-amp output terminal (+) and ground (−).

(Narration: the Bode plots are to be done in the linear approximation; from the analysis deduce the filter type and the maximum gain.)

## Page 1

Header: "Ulaby 9.37". The textbook problem statement and Figure P9.37 are pasted at top left (as above).

Handwritten, top right:

**Example:** op-amp high-pass filter circuit.

**Figure (redrawn circuit):** Op-amp triangle pointing right, inverting input ($-$) on top, non-inverting ($+$) below. Feedback resistor $R_2$ in a loop from the output node back to the inverting-input node. From the inverting-input node a wire goes left through resistor $R_1$, then down through capacitor $C$ to ground. $\tilde{\mathbf V}_s$ is a source symbol (+ on top) from ground up to the non-inverting input. Output terminal at right labeled $+$ with $\tilde{\mathbf V}_o$, and a $-$ terminal to ground below it.

a) Calculate $\tilde{\mathbf H}(\omega) = \dfrac{\tilde{\mathbf V}_o}{\tilde{\mathbf V}_s}$

b) Bode plots for $R_1 = 1\ \text{k}\Omega$, $R_2 = 4\ \text{k}\Omega$, $C = 1\ \mu\text{F}$.

c) what type of filter? max gain?

a) KCL at op-amp inverting input:
$$\frac{\tilde{\mathbf V}_s}{R_1 + \frac{1}{j\omega C}} + \frac{\tilde{\mathbf V}_s - \tilde{\mathbf V}_o}{R_2} = 0$$

$$\left(\frac{1}{R_1 + \frac{1}{j\omega C}} + \frac{1}{R_2}\right)\tilde{\mathbf V}_s = \frac{1}{R_2}\tilde{\mathbf V}_o\ ;\ \text{multiply by } \frac{R_2}{j\omega C}$$

$$\left(\frac{R_2}{1 + j\omega R_1 C} + \frac{1}{j\omega C}\right)\tilde{\mathbf V}_s = \frac{1}{j\omega C}\tilde{\mathbf V}_o$$

(This last line is cut by the page break and repeated at the top of Page 2.)

## Page 2

$$\left(\frac{R_2}{1 + j\omega R_1 C} + \frac{1}{j\omega C}\right)\tilde{\mathbf V}_s = \frac{1}{j\omega C}\tilde{\mathbf V}_o$$

$$\left(\frac{R_2\, j\omega C + 1 + j\omega R_1 C}{j\omega C\,(1 + j\omega R_1 C)}\right)\tilde{\mathbf V}_s = \frac{1}{j\omega C}\tilde{\mathbf V}_o$$

$$\Rightarrow\ \tilde{\mathbf H}(\omega) = \frac{\tilde{\mathbf V}_o}{\tilde{\mathbf V}_s} = \boxed{\frac{1 + j\omega(R_1 + R_2)C}{1 + j\omega R_1 C} = \tilde{\mathbf H}(\omega)}$$

$\tilde{\mathbf H}(\omega)$ has a simple zero at $\omega_{c1} = \dfrac{1}{(R_1 + R_2)C}$, and a simple pole at $\omega_{c2} = \dfrac{1}{R_1 C}$

$$\Rightarrow\ \tilde{\mathbf H}(\omega) = \frac{1 + j\omega/\omega_{c1}}{1 + j\omega/\omega_{c2}}$$

b)
$$\omega_{c1} = \frac{1}{(1\text{k} + 4\text{k})\,10^{-6}} = \frac{1}{5}\times 10^3 = 200\ \text{rad/s}$$

$$\omega_{c2} = \frac{1}{(1\text{k})(10^{-6})} = 1000\ \text{rad/s}$$

$$\Rightarrow\ \tilde{\mathbf H}(\omega) = \frac{1 + \frac{j\omega}{200}}{1 + \frac{j\omega}{1000}}$$

$M(0) = 1 \to M(0) = 20\log 1 = 0\ \text{dB}$
$$M(\infty) = 20\log\left(\frac{R_1 + R_2}{R_1}\right) = 20\log 5 = 13.98\ \text{dB} \approx 14\ \text{dB}.$$
$\phi(0) = 0^\circ$
$\phi(\infty) = 0^\circ$

## Page 3

(Top: "$\phi(\infty) = 0^\circ$" repeated from the bottom of Page 2, with the tail of the "$\phi(0)$" line cut off by the page break.)

**Figure (Bode magnitude plot, green):** Vertical axis $M(\omega)\,[\text{dB}]$ with ticks 20 and 14; a horizontal dashed line at 14 dB. Horizontal axis $\omega$ with ticks 0 (origin), 20, 100, 200, 1000, 2000, $10^4$; vertical dashed guide lines at 200 and 1000. Green curve: flat at 0 dB from the left to $\omega = 200$; rises from 200 to 1000, labeled "20 dB/dec" with an arrow, reaching 14 dB at 1000; flat at 14 dB beyond 1000.

**Figure (Bode phase plot):** Vertical axis $\phi(\omega)$ with ticks $90^\circ$, $0^\circ$, $-90^\circ$. Horizontal axis $\omega$ with ticks 20, 100, 200, 1000, 2000, $10^4$; vertical dashed guides at 20, 100, 200, 1000, 2000, $10^4$.

Blue dashed contributions (dots at endpoints and midpoints):
- zero at 200: from $0^\circ$ at $\omega = 20$ up to $+90^\circ$ at $\omega = 2000$ ($45^\circ$ at 200);
- pole at 1000: from $0^\circ$ at $\omega = 100$ down to $-90^\circ$ at $\omega = 10^4$ ($-45^\circ$ at 1000).

Green total: flat at $0^\circ$ up to 20; rises from 20 to 100, labeled "$45^\circ$/dec" with an arrow (to about $+31^\circ$); flat from 100 to 2000; falls from 2000 to $10^4$ back to $0^\circ$; flat at $0^\circ$ beyond $10^4$.

c) This is a high-pass filter. The maximum gain is 14 dB, or $\dfrac{R_1 + R_2}{R_1} = 5$.

**Key points:**

(i) analysis was a fairly straightforward op-amp circuit analysis.

(ii) Bode plots generated in the "usual" way → high-pass filter, with maximum gain of 14 dB, or 5.

(iii) results for $\tilde{\mathbf H}(\omega)$ and Bode plot (magnitude) make intuitive sense in terms of low-frequency and high-frequency limiting behavior of the circuit.

(Rest of page blank.)

## Narration transcript

Okay, so this is Ulaby 9.37, and this is an example of an op-amp high-pass filter circuit. Basically, what we want to do here is to take the circuit as shown here, and we want to calculate its transfer function, the output voltage over the input voltage, which is $\mathbf V_s$. Then we want to generate the Bode plots for this, which we'll do in the linear approximation. And then from that analysis, we want to deduce what kind of filter this is, and what its maximum gain is.

So let's go ahead with this. As usual, we'll start off by drawing the circuit. We have an op-amp here, and then we have a feedback resistor connection like this. The non-inverting input of the op-amp is connected to our input $\mathbf V_s$, and then the inverting input [narration says "noninverting"; the drawing and the analysis use the inverting input] is connected to ground through a resistor and a capacitor. We have the output voltage over here. This is a capacitor with value $C$, this is a resistor $R_1$, this is a resistor $R_2$. What we're asked to do here is, first, calculate the transfer function, which is the output voltage over our input $\mathbf V_s$. Then we want to generate the Bode plots for $R_1$ equal to 1 kilohm, $R_2$ equal to 4 kilohms and $C$ being 1 microfarad, and then, part (c), based on our analysis, we want to determine what type of filter this is (I already told you the answer, but we'll see why it is that), and then what is its maximum gain.

So let's go ahead and take a look at this. The first part of this is to calculate the transfer function, meaning basically calculating the output voltage, which will be a function of $\mathbf V_s$. To do that we will proceed in the usual way, as we do for op-amps, which is to apply KCL, and in this case at the inverting input of the op-amp, where by the ideal op-amp rules we know that the voltage has to be $\mathbf V_s$, because the voltage at the non-inverting input is $\mathbf V_s$. So for part (a), calculating the transfer function, what we want to do is to apply KCL at the op-amp inverting input, where the voltage is $\mathbf V_s$. The current going out this way to the left is going to be that voltage, $\mathbf V_s$ minus 0, so just $\mathbf V_s$, divided by the impedance of $R_1$ in series with $C$, so that's $R_1 + 1/(j\omega C)$. Then we add to that the current flowing up this way and to the right through the resistor $R_2$. That current is the voltage across the resistor, which is $\mathbf V_s - \mathbf V_o$, divided by the resistance $R_2$. These two currents have to add up to 0.

So now we will, as usual, group together the terms proportional to the same variable. For $\mathbf V_s$ we have this first term over here, so $1/(R_1 + 1/(j\omega C))$, and then from this second term over here we have plus $1/R_2$. Those are multiplying $\mathbf V_s$. And then we have this $-\mathbf V_o/R_2$ on the left, so that becomes $(1/R_2)\mathbf V_o$, without the minus sign, on the right. Now, to simplify this a bit, what we want to do is to take this equation and multiply it by $R_2/(j\omega C)$. Multiplying by $R_2$ will get rid of this $R_2$ and this $R_2$ in the denominators here; multiplying by $j\omega C$ in the denominator will turn this term into just a one. So if we go ahead and do this, then from this first term over here we're going to get an $R_2$ in the numerator, divided by 1 (that's $j\omega C$ times $1/(j\omega C)$) plus $j\omega R_1 C$. And then from the $1/R_2$ term over here, we're going to get just $1/(j\omega C)$. All this times $\mathbf V_s$, and that's equal to, on the right-hand side, $1/(j\omega C)$ times $\mathbf V_o$.

Then here on the left, what we want to do next is to take these two terms and put them over a common denominator, and that common denominator is going to be just the product of the two individual denominators. If we do that, then from this $R_2$ over here we're going to get $R_2$ times $j\omega C$, and then from this 1 over here we're going to get $1 + j\omega R_1 C$; so plus $1 + j\omega R_1 C$, and then our denominator is going to be $j\omega C$ times $(1 + j\omega R_1 C)$. All of this still times $\mathbf V_s$, and then on the right-hand side we get $1/(j\omega C)$ times $\mathbf V_o$.

So now it's very easy for us to solve for the transfer function. $\mathbf H(\omega)$ is $\mathbf V_o/\mathbf V_s$. Essentially, we just divide both sides of this equation by $\mathbf V_s$ and multiply both sides by $j\omega C$, and that's going to cancel out this $j\omega C$ in the denominator over here. So what we're going to get is, in the numerator, $1 + j\omega(R_1 + R_2)C$, divided by $1 + j\omega R_1 C$. So this is our transfer function $\mathbf H(\omega)$.

From looking at this, we can see that this transfer function has one zero, where the numerator goes to zero, and one pole, where the denominator goes to zero. So the transfer function has a simple zero at $\omega$, we'll call it $\omega_{c1}$, and it is $1/((R_1 + R_2)C)$. And it has a simple pole at $\omega_{c2}$, and we can see from the denominator that $\omega_{c2}$ is just $1/(R_1 C)$. So, alternatively, we can write that $\mathbf H(\omega)$ is equal to $(1 + j\omega/\omega_{c1})/(1 + j\omega/\omega_{c2})$, where we have defined $\omega_{c1}$ and $\omega_{c2}$ as shown here. So that's the first part of it, to calculate the transfer function.

Then the second part of the problem is to construct the Bode plots for the magnitude and the phase. To do that, we're going to need the numerical values of the zero and pole frequencies. $\omega_{c1}$, where we have the zero, is $1/((R_1 + R_2)C)$, so it's 1 over, $R_1$ is 1 k and $R_2$ is 4 k, times $C$, which is $10^{-6}$. 1 k plus 4 k is 5 k; k is $10^3$. So we have $5\times10^3$ times $10^{-6}$ in the denominator; that's $5\times10^{-3}$, so $1/(5\times10^{-3})$, which is $\frac{1}{5}\times10^{3}$, which is 200, and that's in radians per second. Then $\omega_{c2}$ is equal to $1/(R_1 C)$, so 1 over 1 k (that's $R_1$) times $10^{-6}$ (that's 1 microfarad), so that is 1000 radians per second. That means that we can write $\mathbf H(\omega)$ as $(1 + j\omega/200)/(1 + j\omega/1000)$. In terms of producing the Bode plots, this is a slightly easier way to look at the transfer function.

Looking at this form for the transfer function, we can see that the magnitude of the transfer function at zero frequency is just 1, which means that on the dB scale this is $20\log 1$, which is 0 dB. And then at very high frequency, as the frequency goes to infinity, if we look at this form of $\mathbf H(\omega)$ here, the numerator is going to be dominated by this term, the denominator by this term over here, and so the limit of this as $\omega$ goes to infinity is just $(R_1 + R_2)/R_1$. On the dB scale it's $20\log((R_1 + R_2)/R_1)$, so that's $20\log 5$, because $R_1$ is 1 k, $R_2$ is 4 k, which is 13.98 dB; we'll call that 14 dB. Then the phase at 0: looking at this form here for $\mathbf H(\omega)$, we can see that that's clearly $0^\circ$. And then the phase at very high frequency, frequency approaching infinity, where these second, $\omega$-dependent terms dominate, you can see that the phase there is going to be 0 as well. But that does not necessarily mean that the phase at every point in between is 0 as well, as we will see. The phase can vary between zero frequency and very high frequency.

So let's take this information now and generate the Bode plots. We'll first do the Bode magnitude plot, and we'll draw the frequency axis here. We have a zero at $\omega_{c1}$, which is 200, and a pole at $\omega_{c2}$, which is 1000. So our critical frequencies here: I'll say 100 here, 1000, $10^4$; then 200, say, maybe here; 20 here; and then 2000 here. We know that as the frequency goes to infinity, the magnitude is 14 dB, so if this is 20, 14 would be maybe here. The key frequencies here are 200 and 1000. We saw up here that at low frequencies, which for our purposes will be less than 200, the magnitude is 0 dB. 0 dB is where we put the axis, and so the low-frequency part of the Bode plot is like this. Then between 200 and 1000, the denominator is going to go as 1, and the numerator is going to go as $\omega$, so we're going to have a slope of $+20$ dB per decade. So that's going to take us up to 14; so 20 dB per decade. And then at high frequency, meaning above 1000, we're going to have the high-frequency limit, so it'll just stay at 14 dB, like this. I'll draw this so it's clear that these are aligned. So that is the Bode magnitude plot.

Now we want to construct the Bode frequency plot, sorry, not the frequency plot, the phase plot. So $\phi(\omega)$ is a function of $\omega$; the horizontal axis in both cases is the frequency. So we have, say, 20 here, 100 here, 200 here, 1000 here, 2000, and then $10^4$. We'll say this is $0^\circ$, this is $90^\circ$, this is $-90^\circ$. And we will mark these various different frequencies here. So we have a zero at a frequency of 200. That means that at low frequencies, meaning 0.1 times 200, or 20, and below, the phase will be 0, because the 1 term here will be dominant, and then at high frequency, say 10 times 200, that is 2000, and above, this second term in the numerator dominates and the phase will be $90^\circ$. So we go from a phase of, we'll draw this in blue, at 20 we have a phase of 0, then at 2000 we have a phase of $90^\circ$, and at 200 it's halfway, it's $45^\circ$. So that's the contribution to the phase from the zero in the numerator of the transfer function.

Then for the pole, we have a pole at 1000 radians per second. At very low frequencies, meaning a tenth of this, or 100, and below, the phase is 0, and it contributes 0 to the phase of the transfer function. At very high frequency, say 10 times 1000, or 10,000, and above, the phase in the denominator is $90^\circ$, meaning that the phase contribution to $\mathbf H(\omega)$ is $-90^\circ$. So we go from a phase of 0 at 100 to $-90$ at $10^4$, and it's $-45^\circ$ at 1000. So we have a contribution to the phase from the pole at $\omega = 1000$ that looks something like this other blue dashed line that I just drew.

And now we can combine these to get the complete phase plot, noting that at very low frequency and at very high frequency the phase should be 0, as we concluded up here. So that means at very low frequency, say $\omega$ less than 20, the phase is 0. Then, starting at 20, we go up like this; the slope here is $45^\circ$ per decade. Then from 100 to 2000, we have $45^\circ$ per decade up like this, and $45^\circ$ per decade down like this. So those cancel each other out, and we have just the constant phase like this. And then from 2000 to $10^4$, we have $-45^\circ$ per decade, so that'll bring us down like this, and then from $10^4$ and above the phase is 0 again. So that is the Bode phase plot.

So now we see right here both the Bode magnitude plot and the Bode phase plot. We can confirm, by looking at the magnitude plot, that indeed this is acting as a high-pass filter, because we have a larger transfer function, by 14 dB, at high frequencies than at low frequencies. So that takes us to part (c) of this problem, which is asking what kind of a filter this is. This is a high-pass filter. And then it's also asking what is the maximum gain, and the maximum gain is basically the value of the magnitude at high frequency, which we calculated up here. On the dB scale it is 14 dB, or as just a conventional linear gain it's $(R_1 + R_2)/R_1$, which is 5. So the maximum gain, on the dB scale, we can say that it's 14 dB, or on a linear scale it is $(R_1 + R_2)/R_1$, which is 5. And so that is the answer to this.

### Key points (instructor retrospective)

If we look at this problem, the analysis was actually quite simple. It was basically just analyzing this as a simple op-amp circuit. So if we think about what were some of the key points here: the analysis was fairly straightforward op-amp circuit analysis. And then once we have the transfer function, we were able to construct the Bode plots in the usual way, which was shown here, and also there are several examples of this in one of the earlier problems; it was Ulaby 9.19. So the Bode plots were generated in the usual way, and from the Bode plots we could conclude that this was a high-pass filter, and we could basically read from the Bode plot the maximum gain of 14 dB, or, as a conventional linear gain, 5, $(R_1 + R_2)/R_1$.

Now let's go back and look at the circuit and think about whether these results actually make sense, if we just think about the circuit a little bit. If we're at very low frequency, then this capacitor is going to behave like an open circuit, so there'll be no current flowing along this branch. There's also no current flowing along this branch going to the op-amp inverting input. Therefore the current along this branch here has to be 0 as well, and the voltage across $R_2$ has to be 0. So the output voltage has to be equal to whatever the voltage is over here, and that voltage is $\mathbf V_s$, since the input voltages of the op-amp have to be equal to each other. So at low frequencies we should get $\mathbf V_o$ equal to $\mathbf V_s$, which, in terms of the transfer function, means that the transfer function should be 1, and so on the Bode plot that should correspond to 0 dB. If we look at the Bode plot, you can see, in fact, that's what we have over here. And so, after going through all the formalism of calculating the transfer function and so forth, we can go back and check to see: does that result make sort of intuitive sense? At low frequency it certainly does.

How about at high frequencies? At very high frequencies this capacitor behaves basically like a short circuit, and so this circuit here now just looks like a conventional inverting op-amp amplifier circuit, or rather, a non-inverting op-amp amplifier circuit, since the input voltage is connected to the non-inverting input. So at high frequency it's just a conventional non-inverting op-amp amplifier circuit, and we know that that circuit has a gain of $(R_1 + R_2)/R_1$. And in fact, if we look at the transfer function here, we can see that that is indeed the limiting mathematical form of the transfer function as $\omega$ becomes very large, and when we calculated the magnitude of the transfer function numerically, we got that it was 5 on a linear scale, or 14 on the dB scale, and we see that in the Bode plot as well.

So the third point that we will make here is that the results for $\mathbf H(\omega)$ and the Bode plot, particularly for the magnitude, make intuitive sense in terms of the low-frequency and high-frequency limiting behavior of the circuit. This idea of, after you get some result, going back and thinking about and testing to see whether it makes reasonable intuitive sense, whether it has the correct behavior as you go to certain simplifying limits, is actually quite useful and important in validating or checking that your result actually makes sense. If you get a result that predicts obviously incorrect behavior in one of these simplifying limits, then you know that it's probably a good idea to go back and check either what you did in that analysis, or what your intuitive understanding of what the circuit should be doing is, or perhaps both. Okay, so then.

## Index terms

Ulaby 9.37, Problem 9.37, Figure P9.37, op-amp high-pass filter, high-pass filter, non-inverting amplifier, ideal op-amp rules, inverting input at $\mathbf V_s$, KCL at inverting input, $R_1$ in series with $C$, feedback resistor $R_2$, $R_1 + 1/(j\omega C)$, multiply by $R_2/(j\omega C)$, common denominator, transfer function, $\mathbf H(\omega) = \mathbf V_o/\mathbf V_s$, $[1 + j\omega(R_1+R_2)C]/[1 + j\omega R_1 C]$, standard form, simple zero, simple pole, $\omega_{c1} = 1/((R_1+R_2)C)$, $\omega_{c2} = 1/(R_1 C)$, 200 rad/s, 1000 rad/s, $(1 + j\omega/200)/(1 + j\omega/1000)$, $M(0) = 0$ dB, $M(\infty) = 20\log 5 = 13.98$ dB, 14 dB, $(R_1+R_2)/R_1 = 5$, maximum gain, Bode magnitude plot, Bode phase plot, 20 dB/dec, $45^\circ$/dec, $-45^\circ$/dec, phase plateau, $\phi(0) = 0^\circ$, $\phi(\infty) = 0^\circ$, $\omega/10$ and $10\omega$ phase points, low-frequency limit capacitor open, high-frequency limit capacitor short, $\mathbf V_o = \mathbf V_s$ at DC, gain $1 + R_2/R_1$, sanity check limiting behavior, key points, Ulaby 9.19 reference, $R_1 = 1\ \text{k}\Omega$, $R_2 = 4\ \text{k}\Omega$, $C = 1\ \mu\text{F}$, Prof. Ed Yu, Chapter 9
