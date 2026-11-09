---
course: ECE 411H
kind: problem-video
source: Problem Solving Videos/Ulaby 13.20.pdf
source_pages: 6
author: Prof. Ed Yu
unit: final
topics: [fourier-series, fourier-series-circuit-analysis, square-wave, odd-symmetry, phasor-domain, node-voltage, kcl, superposition, inductor, transfer-function, polar-form, arctangent-quadrant, gibbs-ringing, ulaby-13.20]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
deepgram_transcript: deepgram/Ulaby_13.20.deepgram.txt
deepgram_paragraphs: deepgram/Ulaby_13.20.deepgram.md
---

# Ulaby 13.20 — Fourier-series circuit analysis: square-wave source driving an R-L ladder

**Summary.** Problem-solving video for Ulaby/Maharbiz/Furse Problem 13.20. A 2-ms-period square wave $v_s(t)$ (2 V for the first half-period, 10 V for the second) drives a ladder: $R_1$ in series, then shunt $L_1$, then $R_2$ in series with $L_2$; $i(t)$ is the current through the $R_2$-$L_2$ branch. Part (a) derives the Fourier series of $i(t)$ symbolically: $v_s$ has $a_0 = 6$, $a_n = 0$ by odd symmetry, $b_n = \frac{8}{\pi n}(\cos\pi n - 1)$, i.e. $v_s(t) = 6 - \frac{16}{\pi}\sum_{n\ \text{odd}}\frac{1}{n}\sin(1000\pi n t)$; the circuit is solved by KCL at the internal node in the phasor domain to get $I = \frac{j\omega L_1}{R_1R_2 - \omega^2 L_1L_2 + j\omega(L_1(R_1+R_2)+R_1L_2)}V_s$, which is put in polar form with careful quadrant handling of the arctangent (denominator real part is negative) and converted back to the time domain. Part (b) evaluates the first five harmonics with $R_1=R_2=10\ \Omega$, $L_1=L_2=10$ mH ($n=1$: $0.1236\cos(1000\pi t + 46.74^\circ)$; $n=3$: $0.01734\cos(3000\pi t+17.85^\circ)$; $n=5$: $0.006394\cos(5000\pi t+10.86^\circ)$; even $n$ zero). Part (c) shows the $n_{max}=100$ plots (Gibbs ringing on $v_s$, exponential-looking $i(t)$). Exam lessons: Fourier-series circuit analysis = phasors + superposition; symmetry kills coefficients; complex-algebra accuracy matters.

> **Audio transcript (Deepgram nova-3, ECE 411 keyterms, timestamped):** `deepgram/Ulaby_13.20.deepgram.txt` ; paragraph form: `deepgram/Ulaby_13.20.deepgram.md`. Fresh ASR of the video audio; where it disagrees with the Narration section (built from the published auto-captions), prefer this file and the handwritten page.

## Problem statement

(Printed textbook excerpt pasted on page 1.)

13.20 Voltage source $v_s(t)$ in the circuit of Fig. P13.20(a) has the waveform displayed in Fig. P13.20(b).

(a) Derive the Fourier series representation of $i(t)$.

(b) Calculate the first five terms of $i(t)$ using $R_1 = R_2 = 10\ \Omega$ and $L_1 = L_2 = 10$ mH.

(c) Plot $i(t)$ and $v_s(t)$ using $n_{max} = 100$.

**Figure P13.20: Circuit and waveform for Problem 13.20.**

- **(a) Circuit:** voltage source $v_s(t)$ (+ on top) on the left; from its + terminal, $R_1$ in series along the top to an internal node; from that node, $L_1$ down to the bottom rail; also from that node, $R_2$ along the top to the right, then $L_2$ down to the bottom rail; $i(t)$ is marked with a downward arrow through the right branch ($R_2$–$L_2$). Bottom rail returns to the source $-$ terminal.
- **(b) Waveform:** $v_s(t)$ versus $t$ (ms). Axis marks $-1, 0, 1, 2$; levels $2$ V and $10$ V. Square wave: $10$ V from $t=-1$ to $0$ ms, $2$ V from $0$ to $1$ ms, $10$ V from $1$ to $2$ ms, $2$ V after $2$ ms. Period $2$ ms.

## Page 1

Header: Ulaby 13.20

(Printed problem statement and Figure P13.20 pasted at upper left, as transcribed above.)

Handwritten at upper right:

**Example:** circuit analysis using Fourier series.

**Figure (redrawn circuit):** $v_s(t)$ voltage source (+ top) on the left; $R_1$ in series on top; internal node; shunt $L_1$ to bottom; $R_2$ in series on top to the right; $L_2$ shunt on the far right; bottom rail common. Below: $R_1 = R_2 = 10\ \Omega$, $L_1 = L_2 = 10$ mH.

**Figure (redrawn waveform, blue):** $v_s(t)$ versus $t$ (ms), axis marks $-1, 0, 1, 2$; levels $10$ V and $2$ V; $10$ V on $(-1,0)$, $2$ V on $(0,1)$, $10$ V on $(1,2)$, $2$ V after 2. Annotated $T = 2$ ms. "Solve for $i(t)$".

a) 1) compute Fourier series for $v_s(t)$:

For $v_s(t)$, $T = 2$ ms $\Rightarrow \omega_0 = \frac{2\pi}{T} = 1000\pi$ rad/s.

$$v_s(t) = a_0 + \sum_{n=1}^{\infty}\big(a_n\cos(n\omega_0 t) + b_n\sin(n\omega_0 t)\big)$$

$$a_0 = \frac{1}{2\text{m}}\left[\int_0^{1\text{m}} 2\,dt + \int_{1\text{m}}^{2\text{m}} 10\,dt\right] = \frac{12\text{m}}{2\text{m}} = 6.$$

(bottom line cut off by page break; it is the top of "$a_n = 0$ since $(v_s(t) - a_0)$ has odd symmetry.")

## Page 2

$a_n = 0$ since $(v_s(t) - a_0)$ has odd symmetry.

$$b_n = \frac{2}{T}\int_0^T v_s(t)\sin(n\omega_0 t)\,dt$$

$$= \frac{2}{2\text{m}}\left[2\int_0^{1\text{m}}\sin(1000\pi n t)\,dt + 10\int_{1\text{m}}^{2\text{m}}\sin(1000\pi n t)\,dt\right]$$

$$= \frac{1}{10^{-3}}\left\{\frac{-2}{1000\pi n}\Big[\cos(1000\pi n t)\Big]_0^{1\text{m}} - \frac{10}{1000\pi n}\Big[\cos(1000\pi n t)\Big]_{1\text{m}}^{2\text{m}}\right\}$$

$$= -\frac{1}{\pi n}\Big\{2\big(\cos(\pi n) - 1\big) + 10\big(1 - \cos(\pi n)\big)\Big\}$$

$$b_n = \frac{-1}{\pi n}\big(8 - 8\cos(\pi n)\big) = \frac{8}{\pi n}\big(\cos(\pi n) - 1\big)$$

$$\Rightarrow\ v_s(t) = 6 + \frac{8}{\pi}\sum_{n=1}^{\infty}\frac{(\cos(\pi n) - 1)}{n}\sin(1000\pi n t)$$

$$\cos(\pi n) - 1 = \begin{cases} -2 & n\ \text{odd} \\ 0 & n\ \text{even}\end{cases}$$

$$\Rightarrow\ v_s(t) = 6 - \frac{16}{\pi}\sum_{n=\text{odd}}^{\infty}\frac{1}{n}\sin(1000\pi n t)$$

2) analyze circuit in phasor domain

$$v_s(t) = 6 - \frac{16}{\pi}\sum_{n=\text{odd}}^{\infty}\frac{1}{n}\cos(1000\pi n t - 90^\circ)$$

$$= 6 - \frac{16}{\pi}\sum_{n=\text{odd}}^{\infty}\frac{1}{n}\cos(\omega_n t - 90^\circ),\qquad \omega_n = 1000\pi n$$

(bottom of page: top edge of the next line, which carries "$e^{j90^\circ}$" superscripts; continued on page 3)

## Page 3

(Top: cut-off fragment "$\frac{16}{\pi}\sum_{n=\text{odd}}$" from the preceding line.)

$$\Rightarrow\ \underset{\sim}{V}_s = 6 + \frac{16}{\pi}\sum_{n=\text{odd}}^{\infty}\frac{1}{n}e^{j90^\circ}\quad\text{since } -e^{-j90^\circ} = -(-j) = j = e^{j90^\circ}$$

**Figure (phasor-domain circuit):** source $\underset{\sim}{V}_s$ (+ top) on the left; $R_1$ in series on top to node $\underset{\sim}{V}_1$; from $V_1$, shunt impedance $j\omega L_1$ to the bottom rail; from $V_1$, $R_2$ in series to the right, then $j\omega L_2$ down to the bottom rail, with $\underset{\sim}{I}$ marked by a downward arrow through that right branch; bottom rail labeled $V = 0$.

To the right: solve for $\underset{\sim}{V}_1$, then

$$\underset{\sim}{I} = \frac{\underset{\sim}{V}_1}{R_2 + j\omega L_2}$$

$$\text{KCL @ } V_1:\quad \frac{\underset{\sim}{V}_1 - \underset{\sim}{V}_s}{R_1} + \frac{\underset{\sim}{V}_1}{j\omega L_1} + \frac{\underset{\sim}{V}_1}{R_2 + j\omega L_2} = 0$$

$$\left(\frac{1}{R_1} + \frac{1}{j\omega L_1} + \frac{1}{R_2 + j\omega L_2}\right)\underset{\sim}{V}_1 = \frac{\underset{\sim}{V}_s}{R_1}$$

$$\Rightarrow\ \underset{\sim}{V}_1 = \frac{\underset{\sim}{V}_s}{\left(1 + \frac{R_1}{j\omega L_1} + \frac{R_1}{R_2 + j\omega L_2}\right)}\cdot\left(\frac{R_2 + j\omega L_2}{R_2 + j\omega L_2}\right)$$

(the multiplying factor is written in green)

$$= \frac{\underset{\sim}{V}_s(R_2 + j\omega L_2)}{\left(1 + \frac{R_1}{j\omega L_1}\right)(R_2 + j\omega L_2) + R_1}$$

$$\underset{\sim}{V}_1 = \frac{\underset{\sim}{V}_s(R_2 + j\omega L_2)}{R_1 + R_2 + R_1\frac{L_2}{L_1} + j\left(-\frac{R_1R_2}{\omega L_1} + \omega L_2\right)}$$

$$\Rightarrow\ \underset{\sim}{I} = \frac{\underset{\sim}{V}_1}{R_2 + j\omega L_2} = \frac{\underset{\sim}{V}_s}{R_1 + R_2 + R_1\frac{L_2}{L_1} + j\left(-\frac{R_1R_2}{\omega L_1} + \omega L_2\right)}\cdot\left(\frac{j\omega L_1}{j\omega L_1}\right)$$

(the multiplying factor is written in green)

(bottom line cut off: "$= \frac{j\omega L_1}{\cdots}\underset{\sim}{V}_s$ ; $\omega = n\omega_0$ with", continued on page 4)

## Page 4

$$= \frac{j\omega L_1}{R_1R_2 - \omega^2 L_1L_2 + j\omega\big(L_1(R_1+R_2) + R_1L_2\big)}\,\underset{\sim}{V}_s;\quad \omega = n\omega_0 \text{ with } \omega_0 = 1000\pi.$$

$$\Rightarrow\ \underset{\sim}{I} = \frac{jn\omega_0 L_1}{R_1R_2 - n^2\omega_0^2 L_1L_2 + jn\omega_0\big(L_1(R_1+R_2) + R_1L_2\big)}\,\underset{\sim}{V}_s$$

**Figure (margin sketch, blue/red, labeled "denom"):** complex-plane axes; a blue dot in the second quadrant (negative real part, positive imaginary part) with a line from the origin to it; the angle $\phi$ is marked from the positive real axis counter-clockwise to that line (an obtuse angle); a red dashed line extends from the origin into the fourth quadrant (the direction a calculator's $\tan^{-1}$ would give), with a small red arc marking that incorrect angle.

$$= \frac{n\omega_0 L_1}{\sqrt{\big(R_1R_2 - n^2\omega_0^2 L_1L_2\big)^2 + n^2\omega_0^2\big(L_1(R_1+R_2) + R_1L_2\big)^2}}\;e^{j90^\circ}e^{-j\phi}\,\underset{\sim}{V}_s$$

$$\text{with } \phi = 180^\circ - \tan^{-1}\frac{\big(L_1(R_1+R_2) + R_1L_2\big)n\omega_0}{n^2\omega_0^2 L_1L_2 - R_1R_2}\quad\text{since } \omega_0^2 L_1L_2 > R_1R_2:\ 10^6\pi^2\,10^{-4} > 10^2$$

Then, using the Fourier series expansion for $\underset{\sim}{V}_s$:

$$\underset{\sim}{I} = 6(0) + \frac{16}{\pi}\sum_{n=\text{odd}}^{\infty}\frac{\omega_0 L_1}{\sqrt{\big(n^2\omega_0^2 L_1L_2 - R_1R_2\big)^2 + n^2\omega_0^2\big(L_1(R_1+R_2) + R_1L_2\big)^2}}\;e^{-j\phi}e^{j90^\circ}\cdot e^{j90^\circ},\ \text{or}$$

$$\underset{\sim}{I} = \frac{16}{\pi}\sum_{n=\text{odd}}^{\infty}\frac{\omega_0 L_1}{\sqrt{\big(n^2\omega_0^2 L_1L_2 - R_1R_2\big)^2 + n^2\omega_0^2\big(L_1(R_1+R_2) + R_1L_2\big)^2}}\;e^{+j\tan^{-1}\frac{(L_1(R_1+R_2) + R_1L_2)n\omega_0}{n^2\omega_0^2 L_1L_2 - R_1R_2}}$$

In the time domain, this becomes (boxed):

$$\boxed{i(t) = \frac{16}{\pi}\sum_{n=\text{odd}}^{\infty}\frac{\omega_0 L_1}{\sqrt{\big(n^2\omega_0^2 L_1L_2 - R_1R_2\big)^2 + n^2\omega_0^2\big(L_1(R_1+R_2) + R_1L_2\big)^2}}\cos\!\left(n\omega_0 t + \tan^{-1}\frac{(L_1(R_1+R_2) + R_1L_2)n\omega_0}{n^2\omega_0^2 L_1L_2 - R_1R_2}\right)}$$

$$\boxed{\omega_0 = 1000\pi}$$

b) $R_1 = R_2 = 10\ \Omega$, $L_1 = L_2 = 10$ mH, $\omega_0 = 1000\pi$

(bottom line cut off; repeated on page 5)

## Page 5

(Top: cut-off repeat of "b) $R_1 = R_2 = 10\ \Omega$, $L_1 = L_2 = 10$ mH, $\omega_0 = 1000\pi$".)

$$i(t) = \frac{16}{\cancel{\pi}}\sum_{n=\text{odd}}^{\infty}\frac{10\cancel{\pi}}{\sqrt{\big(100\pi^2 n^2 - 100\big)^2 + 10^6\pi^2 n^2(0.2 + 0.1)^2}}\cos\!\left(1000\pi n t + \tan^{-1}\frac{0.3\cdot1000\pi n}{100(\pi^2 n^2 - 1)}\right)$$

(the $\pi$ in $\frac{16}{\pi}$ and the $\pi$ in $10\pi$ are struck through in green to show they cancel)

$$= \sum_{n=\text{odd}}^{\infty}\frac{16}{10\sqrt{(\pi^2 n^2 - 1)^2 + 9\pi^2 n^2}}\cos\!\left(1000\pi n t + \tan^{-1}\frac{3\pi n}{\pi^2 n^2 - 1}\right)$$

Boxed (first five terms):

$$n = 1:\quad \frac{16}{10\sqrt{(\pi^2 - 1)^2 + 9\pi^2}}\cos\!\left(1000\pi t + \tan^{-1}\frac{3\pi}{\pi^2 - 1}\right) = 0.1236\cos(1000\pi t + 46.74^\circ)$$

$$n = 2:\quad 0$$

$$n = 3:\quad \frac{16}{10\sqrt{(9\pi^2 - 1)^2 + 81\pi^2}}\cos\!\left(3000\pi t + \tan^{-1}\frac{9\pi}{9\pi^2 - 1}\right) = 0.01734\cos(3000\pi t + 17.85^\circ)$$

$$n = 4:\quad 0$$

$$n = 5:\quad \frac{16}{10\sqrt{(25\pi^2 - 1)^2 + 225\pi^2}}\cos\!\left(5000\pi t + \tan^{-1}\frac{15\pi}{25\pi^2 - 1}\right) = 0.006394\cos(5000\pi t + 10.86^\circ)$$

c)

(rest of page blank; plots on page 6)

## Page 6

**Figure (pasted plot, top, red):** $v_s(t)$ versus $t$ (s), horizontal axis $0$ to $4\times10^{-3}$ s with ticks every $0.5\times10^{-3}$; vertical axis $0$ to $12$ with ticks every 2. Square wave reconstructed with $n_{max}=100$: level $2$ on $(0, 1\text{ ms})$, $10$ on $(1, 2\text{ ms})$, $2$ on $(2, 3\text{ ms})$, $10$ on $(3, 4\text{ ms})$; visible Gibbs ringing (overshoot/undershoot spikes) at each transition and small ripple along the flat segments.

**Figure (pasted plot, bottom, cyan):** $i(t)$ versus $t$ (s), same horizontal axis; vertical axis $-0.2$ to $0.15$ with ticks every $0.05$. The curve starts near $+0.12$ at $t = 0$, decays with exponential (concave-up) shape to about $-0.12$ at $t = 1$ ms, then rises with exponential (concave-down) shape to about $+0.12$ at $t = 2$ ms, decays again to $-0.12$ at $3$ ms, and rises to $+0.12$ at $4$ ms; cusps at each millisecond, matching the square-wave transitions.

**Key points:**

(i) Fourier series circuit analysis is based on phasors + superposition.

(ii) symmetry considerations, e.g., odd vs. even functions, can be very powerful in determining the values of certain Fourier series coefficients

(iii) accuracy + proficiency in complex algebra are important.

## Narration transcript

Okay, so this is Ulaby problem 13.20. Okay. And this is an example of circuit analysis using Fourier series.

Okay, so the problem that we have here is that we are given this circuit here that has two inductors, and we're told that the source voltage $v_s$ over here is given by this waveform. Okay? And what we need to do is first to calculate the Fourier series representation of $i(t)$, right. So we'll need to analyze this circuit using a Fourier series expansion for $v_s$; okay, we need to come up with that expression in terms of these parameters $R_1$ and $R_2$, $L_1$ and $L_2$. Then in the second part, what we're asked to do is to calculate numerically the first five terms in this Fourier series expansion of $i(t)$ using these numerical values, and then construct a plot of $i(t)$ and $v_s(t)$ from their Fourier series expansions. Okay? So let's go ahead.

And we'll start off as usual by redrawing the circuit and collecting the key pieces of information. Okay, so the circuit is like this. Okay, so two resistors, two inductors and a voltage source. This is $v_s(t)$. The resistances are $R_1$ and $R_2$. The inductors are $L_1$ and $L_2$. Okay. And $v_s(t)$, all right, this is time in milliseconds: 1 ms, 2 ms, this is 0, this is minus one. Okay. And then we have 2 volts and 10 volts. Okay, and the input voltage $v_s$ basically looks like this. It's a square wave, okay, that goes between 2 volts and 10 volts, with a period of 2 — all right, so the period here, our $T$, is 2 ms. Okay. And so what we're asked to do is basically to solve for $i(t)$, all right, and then once we have that, then we want to obtain some numerical values and plots using the following numerical values for the circuit parameters: the resistances are 10 ohms, and the inductances are 10 millihenries each. Okay, so this is the problem that we're solving.

Part (a) is to compute $i(t)$ in terms of $R_1$, $R_2$, $L_1$ and $L_2$. So the first step in that is going to be to compute the Fourier series for $v_s(t)$. All right, and that will give us basically the phasor components in $v_s$ in the phasor domain, or in the frequency domain. Okay, so $v_s$ is this function over here, and we can see that, all right, the period, as we noted, is 2 ms. So that means that the fundamental frequency $\omega_0$, which is $2\pi$ over the period, is $1000\pi$ radians per second. Okay? And the Fourier series expansion for $v_s(t)$ is $a_0$ plus the sum from $n$ equal to one to infinity of $a_n$ times the cosine of $n\omega_0 t$ plus $b_n$ times the sine of $n\omega_0 t$. All right, and we want to calculate these coefficients.

Okay. So $a_0$, all right, remember, this is just the average value of $v_s(t)$, okay, so it's going to be one over the period, so one over 2 ms — we'll write the milli as just a small m; let's remember that that means a factor of $10^{-3}$. Okay. And then we're going to integrate from 0 to 1 ms. All right, if we look at this waveform here, from 0 to 1 ms it's just 2, that's 2 volts. And then from 1 ms to 2 ms, all right, then, from here to here it's 10 volts. So $10\,dt$. Okay. And so this is now, all right, it's 10 plus 2, all right, when you do the integrals, divided by 2 milli. So we have 10 plus 2, which is 12 milli, divided by 2 milli, and that is just 6. Okay? And if we look at this waveform here, then hopefully it's fairly clear to you that in fact the average value of this over one period, from time 0 to time 2 ms, the average value of this blue waveform here is, in fact, 6 volts, all right, and that's what we just calculated.

Okay? What about the coefficients $a_n$, that is, the coefficients of the cosine terms in the expansion? Those coefficients are actually all 0. Okay? And the reason for that is that the cosine function is an even function of $t$. But looking at the waveform here, we can see that the waveform is clearly, right, if we shift it down by its average value, that is, by 6, we can see that the waveform is clearly an odd function, okay, once it's been shifted down. Right, an odd function will not have any even Fourier components in it. So all the coefficients $a_n$ for $n$ not equal to 0 are 0. All right. And this is because the function $v_s(t)$ minus its average value $a_0$ has odd symmetry. So it has no even function components to it.

Okay, what about the coefficients $b_n$ for the sine terms of the expansion? All right. These are given by the expression 2 over $T$ times the integral over one period, so from 0 to $T$, of $v_s(t)$ times the sine of $n\omega_0 t$, $dt$. Okay. And so this is going to be 2 over capital $T$, which is 2 ms. All right, and then we have, for this integral, all right, $v_s$ has two different values: either it's 2 volts from 0 to 1 ms, and it's 10 volts from one to 2 ms. So we're going to break this up into two integrals. The first one is 2 times the integral from 0 to 1 ms of the sine of $1000\pi n t$, $dt$, and then the second is 10 times the integral from 1 ms to 2 ms of the sine of $1000\pi n t$, $dt$.

Okay, so now let's just go ahead and compute these integrals. All right. So for this factor on the outside, 2 over 2 milli, that's one over, and then we'll write 1 milli now explicitly as $10^{-3}$. Okay. And then when we do this first integral, right, we have the factor of 2, and then when we integrate the sine, we get a factor of minus one over $1000\pi n$ in front. So we have minus 2 over $1000\pi n$ in the front, and then the cosine of $1000\pi n t$, all right, evaluated from zero to one millisecond; minus 10 — and then it's the same integrand, so it's 10 over $1000\pi n$; we get the minus sign here from doing the integral as well — and then it's the cosine of $1000\pi n t$ from one milli to 2 milli. Okay, all of that times this leading factor of one over $10^{-3}$.

Okay, so now we'll pull out the factor of minus one in front, and we'll pull out this factor of $1000\pi$ in the denominator of each term out in front as well. So the 1000 times $10^{-3}$ will just give us one. All right. So we get minus, and then it's one over $\pi$, since we're pulling out this $\pi$ over here as well, and also we'll pull out the factor of $n$, so minus one over $\pi$ times $n$. And then, for the first term over here we have 2 — all right, we've pulled out a factor of minus one over $1000\pi$ times $n$ — times, and then we have the cosine, and then it's $1000\pi$ times $n$ times $10^{-3}$, so that's just the cosine of $\pi$ times $n$, minus the cosine of, at the lower limit $t$ is equal to 0, so it's just the cosine of 0, which is one. Okay? And then for the second term over here, again we've pulled out the factor of minus one over $1000\pi n$, so we have plus 10 times the cosine of 1000 times milli — that's one — times $t$, that's 2, so the cosine of $2\pi n$, which is one, right, for all integer values of $n$; all right, minus, and then we have the cosine of $\pi$ times $n$ when we evaluate this at $t$ equal to 1 milli, right? Because it's the cosine of 1000 times $10^{-3}$, that's one, times $\pi$ times $n$, so just the cosine of $\pi$ times $n$. All right, all this times minus one over $\pi n$. Okay. And if we just simplify this a little bit, we have minus one over $\pi$ times $n$, and then we have minus 2 plus 10, that's 8, and then we have 2 cosine of $\pi n$ minus 10 cosine of $\pi n$, so that's minus 8 times the cosine of $\pi n$. Okay, or we can write that as 8 over $\pi$ times $n$ times the cosine of $\pi$ times $n$ minus one. Okay. And so that is $b_n$.

And so now we can take these values that we've computed for $a_0$, which was just 6, $a_n$, which is 0, and $b_n$, which is this expression down here, and we'll just plug them back into this Fourier series expansion over here. And if we do that, what we get is that $v_s(t)$ is equal to 6 plus, and then it's 8 over $\pi$ times the sum, $n$ going from one to infinity, of the cosine of $\pi n$ minus one, divided by $n$ — right, that $n$ is this $n$ over here — okay, times the sine of $1000\pi n t$. All right. Now we can simplify this a little bit more by noting that the cosine of $\pi$ times $n$ minus one is equal to — if $n$ is odd, all right, then this is equal to minus 2, because the cosine of $\pi n$ for $n$ odd is minus one, so this is minus 2 if $n$ is odd; and it's 0 if $n$ is even, because the cosine of $\pi n$ if $n$ is even is just equal to one, and one minus one is 0. Okay. And so we can also write that $v_s(t)$ is equal to 6, and then minus 16 over $\pi$ times the sum over odd values of $n$, going up to infinity, of one over $n$ times the sine of $1000\pi n t$, right? So those are both correct ways of writing the Fourier series expansion for $v_s(t)$.

Okay. Now, once we have that, all right, what we want to do is to analyze the circuit in the phasor domain, because now what we have is $v_s(t)$ expressed as a linear combination, or a superposition, of multiple frequency components, where the angular frequencies are $1000\pi n$. Okay. So what we do next, then, is to analyze the circuit in the phasor domain. Okay. And so let's take $v_s(t)$ here, all right, and we'll express it in the standard cosine form, which means converting this sine into a cosine by including a phase shift of minus 90 degrees. All right. So we can write $v_s(t)$ as being equal to 6 minus 16 over $\pi$ times the sum over odd values of $n$ going to infinity of one over $n$ times the cosine of $1000\pi n t$ minus 90 degrees. Okay. And we can write that in a slightly different way: 6 minus 16 over $\pi$ times the sum over odd values of $n$ going up to infinity of one over $n$ times the cosine, and instead of writing a thousand $\pi n$ all the time, we'll just write that as $\omega_n$ times $t$ minus 90 degrees, where $\omega_n$ is $1000\pi$ times $n$.

Okay, so now that we have $v_s(t)$ with each of its terms in the standard cosine form, then what we want to do is to write it in the frequency domain, essentially as a superposition of phasors. Okay, so we get that $\underset{\sim}{V}_s$ is equal to 6 — all right, that's the constant term — and then plus 16 over $\pi$ times the sum over odd values of $n$ going up to infinity of one over $n$ times a phase factor $e$ to the $j$ times 90 degrees. And the way that we arrived at that was, we recognize that we have the minus sign over here, all right, and then from this cosine over here we would have ordinarily $e$ to the minus $j$ times 90 degrees. But if we take minus $e$ to the minus $j$ times 90 degrees, right, that is minus, and then $e$ to the minus $j$ times 90 degrees is minus $j$, so that's just $j$, and that is the same as $e$ to the $j$ times 90 degrees. Okay, so that's how we convert this minus sign here to a plus sign, and we get this phase factor $e^{j90^\circ}$ over here. Okay, so now we have our source $V_s$ in the frequency domain, essentially in phasor form.

Okay. And so now we want to write down the circuit in phasor form as well, so we can work with it just in the frequency domain. Okay. So now we have our voltage source in phasor form, resistors $R_1$ and $R_2$, and then the impedances in the frequency domain of the inductors are $j\omega L_1$ and $j\omega L_2$, and we're going to try to compute the current here as a phasor as well, and to do that, what we'll do is we'll essentially use a simple node voltage analysis. We'll take the bottom node to have a voltage of 0. That means that this node up here has a voltage $V_1$, and what we're going to do is to solve for $V_1$ just by applying KCL at the node $V_1$, and then $I$, we can see very easily, is just $V_1$ divided by $R_2$ plus $j\omega L_2$. Okay. So that'll be our route to getting $I$ in the frequency, or phasor, domain. Once we have that, then we'll be able to translate it back into the time domain, all right, using sort of the inverse of the process that we used to get capital $V_s$ over here.

Okay. So now we want to apply KCL at node $V_1$, okay? And so that means, then, just that, right, we take the sum of the outgoing currents to be 0: the current going out to the left is $V_1$ minus $V_s$ over $R_1$; the current going down through the inductor $j\omega L_1$ is $V_1$ over $j\omega L_1$; and then the current going out to the right is $V_1$ divided by $R_2$ plus $j\omega L_2$. And those all have to add up to 0. So now, if we group together all the terms proportional to $V_1$, we get one over $R_1$ plus one over $j\omega L_1$ plus one over $R_2 + j\omega L_2$, all this times $V_1$, is equal to $V_s$ over $R_1$. That's from this term over here, which loses this minus sign when we move it to the right-hand side of the equation. Okay. And so then, dividing both sides of that equation by this big expression in the parentheses, then what we get is that $V_1$ is equal to $V_s$ divided by $R_1$ times this expression here in the parentheses, so that is one plus $R_1$ over $j\omega L_1$ plus $R_1$ over $R_2 + j\omega L_2$. All right!

And so now from here, okay, what we can say is, we're going to multiply this by $R_2 + j\omega L_2$ over $R_2 + j\omega L_2$. All right, that basically gets rid of this $R_2 + j\omega L_2$ in the denominator of the denominator over here. All right, and if we do that, then we get that $V_1$ is equal to $V_s$ times $R_2 + j\omega L_2$, and then in the denominator we have one plus $R_1$ over $j\omega L_1$ — those are the first two terms over here — times this $R_2 + j\omega L_2$, and then from this third term here we just get $R_1$: we multiply by $R_2 + j\omega L_2$, so plus $R_1$. All right. And if we just take this denominator and multiply this here out a little bit more, and then group together the real terms and separately the imaginary terms, then what we get is, in the numerator, the same thing, $V_s$ times $R_2 + j\omega L_2$, and then divided by, in the denominator, we have $R_1$ from over here, and then from $R_2$ times one we have plus $R_2$, and then the other real term comes from $R_1$ over $j\omega L_1$ times $j\omega L_2$, which gives us $R_1$ times $L_2$ over $L_1$. Then we have the imaginary terms from the cross terms in this product. So we have, from $R_1$ over $j\omega L_1$ times $R_2$, we get minus $j$ times $R_1R_2$ over $\omega L_1$ — so $j$ times minus $R_1R_2$ over $\omega L_1$; all right, we get the minus sign by moving the $j$ from the denominator to the numerator — and then, plus one times $j\omega L_2$, which is $j$ times $\omega L_2$, like this. Okay, so that's $V_1$.

All right, now to get the current $I$, we take $V_1$ and divide by $R_2 + j\omega L_2$. All right. So that division basically cancels out this $R_2 + j\omega L_2$ in the numerator. So that means that we get that $I$, which is $V_1$ over $R_2 + j\omega L_2$, is equal to just $V_s$ in the numerator divided by the same denominator, which is $R_1 + R_2 + R_1 L_2/L_1$ plus $j$ times minus $R_1R_2$ over $\omega L_1$ plus $\omega L_2$. Okay. So now here, we will clean this up a bit more by getting rid of the fractions in the denominator. We will do that by multiplying the numerator and the denominator by $j\omega L_1$. So $j\omega L_1$ over $j\omega L_1$. Okay. And when we do that, then what we get is, in the numerator, we have $j\omega L_1$ times $V_s$, which we'll write at the end, divided by, and in the denominator — we'll write the real terms first, right? So the real terms come from here. So we have $j$ times $j$, which is minus one, so minus one times minus $R_1R_2$; then the $\omega L_1$ here cancels out with the $\omega L_1$ in the denominator over here, so we just get plus $R_1R_2$; and then from the second term we get minus, from $j$ times $j$, $\omega^2 L_1L_2$, so minus $\omega^2 L_1L_2$; and then from $j\omega L_1$ times this first set of terms over here, we get plus $j\omega$, and then it's $L_1$ times $R_1 + R_2$ plus $R_1L_2$. All right! All of this times $V_s$.

All right, here, this is $I$ as a function of any frequency $\omega$, right? But we are specifically concerned here, since we're working with Fourier series, with $\omega$ being equal to $n$ times the fundamental frequency $\omega_0$, with $\omega_0$ equal to 1000 times $\pi$. All right. And so, if we substitute for $\omega$ — we substitute $n$ times $\omega_0$ — then what we get is that the current $I$ is equal to $j$ times $n$ times $\omega_0 L_1$, divided by $R_1R_2$ minus $n^2\omega_0^2$ times $L_1L_2$ plus $j$ times $n$ times $\omega_0$ times $L_1(R_1 + R_2) + R_1L_2$, right, all of this times $V_s$.

Okay, so now, all right, what we want to do is we want to take this prefactor here for $V_s$, right, and write it in polar form, right, that is, with a magnitude and a phase angle. Okay. And so the magnitude of this is going to be just the magnitude of the numerator divided by the magnitude of the denominator, right? The magnitude of the numerator is clearly just $n\omega_0 L_1$. All right, so we have $n\omega_0 L_1$ in the numerator, and then the magnitude of the denominator is the square root of the real part squared plus the imaginary part squared. All right, so we're going to get the square root of $R_1R_2$ minus $n^2\omega_0^2 L_1L_2$, quantity squared, plus $n^2\omega_0^2$ times $L_1(R_1+R_2) + R_1L_2$, quantity squared, all this under the square root. And then we have phase factors. So we're going to have $e$ to the $j$ 90 degrees — that's from this factor of $j$ that was here in the numerator, right? So we can't forget about that. And then, if we take this denominator here to have a phase angle of $\phi$, then we're going to get a phase factor in the numerator $e$ to the minus $j$ times $\phi$, all of this times $V_s$. All right! This is this over here. Okay.

And the phase factor $\phi$, all right, which is the phase of this denominator over here, is 180 degrees minus the inverse tangent of $L_1$ times $R_1 + R_2$ plus $R_1L_2$, times $n\omega_0$, divided by $n^2\omega_0^2 L_1L_2$ minus $R_1R_2$. All right, so the way that we get the minus sign here is because we switch the order, right, of these two terms over here: right here it's $R_1R_2$ minus $n^2$ etc.; here it's $n^2$ etc. minus $R_1R_2$. So that's how we get the minus sign in front, right? And it is 180 minus this inverse tangent here, instead of just being minus this inverse tangent, and the reason for that is as follows. All right, it turns out that over here, right, the real part of this denominator here is actually always going to be negative, right, and the reason for that is that $n$ is going to be greater than or equal to one. All right, we're not including the constant term right now, because, because of the $n$ in the numerator, it'll turn out to be 0. Okay, but what happens is that $\omega_0^2 L_1L_2$ is always greater than $R_1$ times $R_2$ for the values of $L_1$, $L_2$, $R_1$, $R_2$ that we're using in this problem. Remember, $L_1$ and $L_2$ are 10 millihenries each, so $10^{-2}$ each; $\omega_0$ is $1000\pi$. So on the left, we're getting from $\omega_0^2$ a $10^6$ times $\pi^2$, and then from $L_1$ times $L_2$ we're going to get $10^{-4}$. $R_1$ and $R_2$, remember, are 10 ohms each, so we're going to get $10^2$, all right, a hundred. And so the left-hand side is a hundred $\pi^2$, the right-hand side is a hundred, right. So clearly this inequality always holds. And so that means that this real part in the denominator is negative.

Okay, let me draw a little picture here. Okay. So we're looking at the denominator, right? So the real part is negative, all right. The imaginary part we can see here is always positive, right? So maybe up here somewhere. All right. So that means that we're always, here, something like this. And so that should be the angle $\phi$. All right. But actually, if we were to take the imaginary part divided by the real part and take the inverse tangent of that, what we would actually get is this angle here. Okay? And that's not the angle. And if you were to plug it into your calculator and do it, you would get this angle here, and so to get this angle here, we actually need to add 180 degrees to it. Okay, it has the same inverse tangent, but it's in the second quadrant, which is correct, rather than the fourth quadrant, which is incorrect. Okay, so that's why it's 180 minus this inverse tangent here, instead of just minus this inverse tangent. Okay, so that's a similar issue to what we encountered when we talked about phasors generally earlier in the semester.

Okay, so now, what we want to do is we want to take the Fourier series expansion for $V_s$, which we worked out earlier — all right, it is this, up here — and we're going to plug it into the expression that we had for $I$, and then that's going to help us to get the different phasor components of $I$. All right! So what we need to do now is we want to use the Fourier series expansion for $V_s$ that we worked out earlier. All right! So we're going to take that and we're going to plug it into here for $V_s$. All right! So we get that $I$ is equal to, right, so the first term in the Fourier series expansion for $V_s$, if we go back up here, is 6. That's at a frequency of 0. Okay? And so that corresponds to $n$ being 0 up here, right? And so we're actually going to get no contribution to $I$ from that, because it's 6 times 0. All right, then, for the nonzero positive values of $n$, all right, we have plus 16 over $\pi$ times the sum over the odd values of $n$ of one over $n$ times $e$ to the $j$ 90 degrees, all right, and that's going to be multiplying these factors over here. All right. So the one over $n$ will cancel this $n$ out over here, and then we'll have everything else. Okay, so we're going to have plus, then, a 16 over $\pi$ times the sum over odd values of $n$, and then, since the one over $n$ in $V_s$ cancels out with this $n$ over here, we just have $\omega_0$ times $L_1$ divided by, and then we have the square root of — now we'll write, we'll take, since this is squared, right, we can just change the order of this, and it doesn't matter, right, because minus one squared is one — so we have $n^2\omega_0^2 L_1L_2$ minus $R_1R_2$, the quantity squared, plus $n^2\omega_0^2$ times $L_1(R_1+R_2) + R_1L_2$, quantity squared. Okay, times, and then we have $e$ to the minus $j\phi$, right, that's this factor over here, times $e$ to the $j$ 90 degrees, that's this factor here, and then, in addition, we have from $V_s$ another factor of $e$ to the $j$ 90 degrees. Okay? And then, when we multiply these phase factors, we have $e$ to the $j$ 180 degrees here; from $e$ to the minus $j\phi$ we get $e$ to the minus $j$ 180 degrees, so those will cancel each other out, and so, for the phase, we'll just have $e$ to the plus, because it's minus minus $j$ times this inverse tangent over here.

Okay. So if we write all that, then we get $I$ is equal to 6 times 0, all right, which is 0, so just 16 over $\pi$ times the sum over odd values of $n$ going to infinity, then the big expression here, $\omega_0 L_1$ divided by the square root of $n^2\omega_0^2 L_1L_2$ minus $R_1R_2$, quantity squared, plus $n^2\omega_0^2$ times $L_1(R_1+R_2) + R_1L_2$, quantity squared, all that under the square root, and then $e$ to the plus $j$ times the inverse tangent of, and then it's this argument up here, so $L_1$ times $R_1 + R_2$ plus $R_1L_2$, times $n\omega_0$, divided by $n^2\omega_0^2 L_1L_2$ minus $R_1R_2$.

Okay, so now we want to convert this back to the time domain, and that is going to correspond — each one of these terms in the Fourier series expansion, all right, in the phasor or frequency domain, has its corresponding time domain component, which we know how to write from our discussion of phasors earlier in the semester. So we just have to convert each of these phasor terms basically back into the time domain, and then the sum of all those will then be the Fourier series expansion of $i(t)$ in the time domain. Okay? So in the time domain, all right, what happens is that now this becomes the following — we'll see if we can fit this all on one line here. All right, so $i(t)$ is equal to 16 over $\pi$ times the sum over odd values of $n$ going to infinity, then it's $\omega_0 L_1$ divided by the square root of $n^2\omega_0^2 L_1L_2$ minus $R_1R_2$, squared, plus $n^2\omega_0^2$ times $L_1(R_1+R_2) + R_1L_2$, squared. All right, all of this — now, what the phase factor does is it contributes a phase to the cosine, so now it's the cosine of $n\omega_0 t$ plus this phase, which is the inverse tangent of $L_1$ times $R_1 + R_2$ plus $R_1L_2$, times $n\omega_0$, divided by $n^2\omega_0^2 L_1L_2$ minus $R_1R_2$. Okay. And so this is our answer for $i(t)$ in the time domain expressed as a Fourier series expansion, all right, as a function of the parameters $R_1$, $R_2$, $L_1$, $L_2$, and $\omega_0$. Right. So here, $\omega_0$, remember, is 1000 times $\pi$. Okay, so that is the result for part (a).

Then part (b), all right, asks us to take this expression and substitute in specific numerical values for the resistors and the inductors, right, and compute the first five terms in the Fourier series expansion of $i(t)$. All right! So we take $R_1$, $R_2$ to be equal to 10 ohms, $L_1$ and $L_2$ to be equal to 10 millihenries, and then, remember, $\omega_0$ is $1000\pi$. Okay? So then, if we plug those values into this big expression up here, then what we get is that $i(t)$ is equal to 16 over $\pi$ times the sum over odd values of $n$ up to infinity of, and then in the numerator, all right, we have $\omega_0$, which is $1000\pi$, times $L_1$, which is 10 millihenries, or 0.01; 1000 times 0.01 is 10, so we have $10\pi$. Divided by, and then in the denominator we have $\omega_0^2$, so that's $10^6\pi^2$, times $L_1$ times $L_2$ — they are each $10^{-2}$, so we have $10^6$ times $10^{-4}$, that's a hundred — then we have our $\pi^2$, and then the $n^2$, minus $R_1R_2$, that's minus 10 times 10, which is a hundred, squared; plus, and then over here, all right, we have $\omega_0^2$, that's going to be $10^6$ times $\pi^2$ times $n^2$, so we have $10^6\pi^2$ times $n^2$, and then $L_1$ times $R_1 + R_2$ — $R_1 + R_2$ is 20, times 0.01 is 0.2 — and then $R_1L_2$, that's 10 times 0.01, that's 0.1, squared. Okay? And then we have the cosine of $1000\pi n t$, right, that's $n\omega_0 t$, plus the inverse tangent of, and then in the numerator here, all right, that's basically just, the $L_1$ times $R_1 + R_2$ plus $R_1L_2$ is just 0.2 plus 0.1, that's 0.3, times $n$ times $\omega_0$, so that's a thousand $\pi$ times $n$, divided by, and then the denominator in the argument of the inverse tangent is just what's inside the parentheses here, right? Because that's this expression here. So it's going to be 100 times $\pi^2 n^2$ minus one.

Okay? And we just simplify this a little bit more. All right, then this $\pi$ and the $\pi$ down here, all right, these cancel out. Okay, then we get, if we take the denominator, and under the square root we factor out a factor of $10^4$, then that becomes $10^2$ outside the square root, all right, and then 10 over $10^2$ becomes a 10 in the denominator. All right, and then we'll have this 16, which we can put in the numerator. Okay. So we'll get the sum over odd values of $n$, and then we have 16 in the numerator, and then 10 in the denominator, and what we have left under the square root is going to be $\pi^2 n^2$ minus one, quantity squared, plus, and then over here we have $0.3$ squared, that's $0.09$, times $10^6$, that is $9\times10^4$; we factored out the $10^4$, so we just have 9 times $\pi^2$ times $n^2$, all of this under the square root. Then we have the cosine of $1000\pi n t$ plus the inverse tangent, and then, what we have here from these numerical factors is 0.3 times a thousand, that's 300, divided by 100, that's 3. So that's $3\pi n$ divided by $\pi^2 n^2$ minus one. Okay. So now, that is a relatively simple form that we can then use to do some numerical calculations.

Okay, so we're going to calculate the first five terms in the full expansion, which includes the even terms, but we know the even terms are 0, all right, so those will be easy. So for $n$ equal to one, we have, from this prefactor here, all right, it's 16 over 10 times the square root of, and then it's $\pi^2$ times one squared, which is $\pi^2$, minus one, squared, plus $9\pi^2$ times one squared, it's just $9\pi^2$, all right, times the cosine of $1000\pi$ times $t$, again, since $n$ is equal to one, plus the inverse tangent of, in the numerator $3\pi$, in the denominator $\pi^2$ minus one, and if you calculate all that out, what you get is 0.1236 times the cosine of $1000\pi t$ plus 46.74 degrees. Okay. For $n$ equal to 2, all right, the result is 0. Okay, we saw that earlier. For $n$ equal to 3, okay, then, again using this expression here, we get 16 over 10 times the square root of, now it's going to be $\pi^2 n^2$ with $n$ equal to 3, is $9\pi^2$, minus one, the quantity squared, plus, and then we have $9\pi^2 n^2$ with $n$ equals 3, that becomes $81\pi^2$. Okay. Times the cosine now of $3000\pi t$, all right, since $n$ is 3 over here, plus the inverse tangent of $9\pi$ — that's $3\pi n$ — divided by $9\pi^2$ minus one. Okay? And if you calculate that out numerically, you get 0.01734 times the cosine of $3000\pi$ times $t$ plus 17.85 degrees. All right, then the $n$ equal to 4 term — we saw earlier all the even terms are 0, so that term is 0 — and then finally, for $n$ equal to 5, we get 16 over 10 times the square root of, then it's $\pi^2 n^2$, that's $25\pi^2$, then minus one, squared, plus, and then we have $9\pi^2$ times $n^2$, that's 9 times 5 squared, which is 9 times 25, which is 225, $\pi^2$, all that under the square root, and then it's the cosine of $5000\pi$ times $t$ plus the inverse tangent of $3\pi n$, which is $15\pi$, divided by $\pi^2 n^2$ minus one, $25\pi^2$ minus one. Okay, if we calculate that out numerically, it's 0.006394 times the cosine of $5000\pi t$ plus 10.86 degrees. Okay, so all of this, all right, these are the first five terms in the Fourier expansion of $i(t)$. Okay, so that's part (b).

Then part (c) asks for the plots, okay, of $i(t)$ and $v_s(t)$, and so I will just take those from the solutions and paste them in. Okay, and they should show up for us shortly here. Okay, there we go. All right. So what you can see here, this is $v_s$, and, right, you can see that it looks very much like the idealized waveform that we saw in the problem statement, except it has this little ringing over here, because these are computed with a finite number of terms, and so you can still see it pretty prominently. You'll always get a little bit of this, even with a large number of terms. And then down here, all right, what you see is $i(t)$. And so what you can see is that the current sort of gradually builds up with a time constant that is determined by the values of the circuit parameters.

### Key points (instructor retrospective)

Okay, so this was a fairly long example. What are some of the key points that we can extract from this, right, if we go back and think about what we did here? All right, one is that when we're doing Fourier series circuit analysis, really what we're doing is we're breaking up, typically, our input signals into a superposition of components at different frequencies. All right, at any single frequency, it's really just the same as doing phasor analysis, all right, which we looked at in a lot of detail and very extensively earlier in the semester. And then we use the idea of superposition, which we can apply to any linear circuit, to combine the results at different frequencies, just by adding them together. Okay. And that's really what Fourier series analysis comes down to: it's breaking our inputs up into individual frequency components, analyzing each frequency essentially in the phasor domain, and then combining those results, which we know we can do, using superposition. All right. So, for circuit analysis, our Fourier series circuit analysis, right, essentially is based on phasors, all right, plus — it works because for linear circuits we can do superposition.

Okay. Another point that we can note here was, remember, we saw that when we were computing the Fourier series expansion of our input voltage, we saw that all of the coefficients of the cosine terms were 0, because the signal for which we are computing the Fourier series was an odd function, all right, once we subtracted off the average value, and the cosine is an even function. Therefore, the coefficients of all the cosine terms in the expansion have to be 0. Okay. And in general, okay, these types of symmetry considerations, so, for example, odd versus even functions, okay, these types of symmetry considerations, right, they can be very powerful in determining the values of certain Fourier series coefficients, and in particular in determining when some of them are 0.

And then the third point that we'll note is that, as we were doing this example, we had to do quite a bit of complex algebra. Okay. And so, having good accuracy and proficiency in complex algebra is very helpful in solving these types of problems. Right, so accuracy and proficiency in complex algebra are important.

Okay, so that is it for this example. Okay? And I will now [recording ends; caption file is cut off here].

## Index terms

Ulaby 13.20, Problem 13.20, Fourier series circuit analysis, square wave, period T = 2 ms, fundamental frequency omega_0 = 1000 pi rad/s, a_0 = 6, average value, a_n = 0, odd symmetry, v_s(t) - a_0, b_n = (8/(pi n))(cos(pi n) - 1), cos(pi n) - 1 = -2 for odd n, odd harmonics only, v_s(t) = 6 - (16/pi) sum odd (1/n) sin(1000 pi n t), standard cosine form, sine to cosine minus 90 degrees, phasor V_s, -e^{-j90} = e^{j90}, phasor-domain circuit, inductor impedance j omega L, node voltage analysis, KCL at V_1, V_1/(R_2 + j omega L_2), transfer function I/V_s = j omega L_1/(R_1 R_2 - omega^2 L_1 L_2 + j omega(L_1(R_1+R_2) + R_1 L_2)), polar form, magnitude and phase, phi = 180 degrees minus arctangent, second-quadrant arctangent correction, omega_0^2 L_1 L_2 > R_1 R_2, superposition, i(t) Fourier series boxed result, R_1 = R_2 = 10 ohm, L_1 = L_2 = 10 mH, 0.1236 cos(1000 pi t + 46.74 deg), 0.01734 cos(3000 pi t + 17.85 deg), 0.006394 cos(5000 pi t + 10.86 deg), n_max = 100 plot, Gibbs ringing, time constant, complex algebra proficiency, Fig. P13.20, Ulaby/Maharbiz/Furse
