---
course: ECE 411H
kind: problem-video
source: Problem Solving Videos/Ulaby 13.49.pdf
source_pages: 8
author: Prof. Ed Yu
unit: final
topics: [fourier-transform, fourier-transform-circuit-analysis, triangular-pulse, integration-by-parts, current-division, capacitor-impedance, partial-fraction-expansion, fourier-transform-pairs, sgn-function, time-shift-property, rc-time-constant, ulaby-13.49]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
deepgram_transcript: deepgram/Ulaby_13.49.deepgram.txt
deepgram_paragraphs: deepgram/Ulaby_13.49.deepgram.md
---

# Ulaby 13.49 — Fourier-transform circuit analysis: triangular current pulse into an R-R-C network

**Summary.** Problem-solving video for Ulaby/Maharbiz/Furse Problem 13.49 (the book misprints the circuit as Fig. P13.19; the intended circuit is Fig. P13.18). A single triangular current pulse $i_s(t) = (A/T)t$ on $0 \le t \le T$ drives a current source in parallel with $R_1$, feeding $R_2$ in series with $C$; $v_{out}$ is the capacitor voltage. Prof. Yu computes $I_s(\omega) = \frac{A}{T\omega^2}[(1+j\omega T)e^{-j\omega T} - 1]$ by integration by parts, uses current division and $Z_C = 1/(j\omega C)$ to get $V_{out} = \frac{R_1}{1 + j\omega(R_1+R_2)C}I_s$, splits it into three terms, partial-fraction-expands the auxiliary functions $F_1(\omega) = 1/[\omega^2(1+j\omega(R_1+R_2)C)]$ and $F_2(\omega) = 1/[\omega(1+j\omega(R_1+R_2)C)]$, inverts them with Ulaby Table 13-4 pairs ($\text{sgn}(t) \leftrightarrow 2/(j\omega)$, $|t| \leftrightarrow -2/\omega^2$, $e^{-at}u(t) \leftrightarrow 1/(a+j\omega)$), and applies the time-shift property (Table 13-5) to handle the $e^{-j\omega T}$ factors. Final boxed $v_{out}(t)$ contains exponentials with time constant $(R_1+R_2)C$, sgn terms and $|t|$ terms. Parts (b)/(c) show plots for $C = 0.33\ \mu$F (charges to ~1800 V by 3 ms, decays) and $C = 0.33$ mF (charges to ~4.5 V and holds; time constant up by $10^3$). Exam lessons: transform sources, analyze in $\omega$-domain, invert via tables and properties (time shift for exponential factors).

> **Audio transcript (Deepgram nova-3, ECE 411 keyterms, timestamped):** `deepgram/Ulaby_13.49.deepgram.txt` ; paragraph form: `deepgram/Ulaby_13.49.deepgram.md`. Fresh ASR of the video audio; where it disagrees with the Narration section (built from the published auto-captions), prefer this file and the handwritten page.

## Problem statement

(Printed textbook excerpt pasted on page 1; the "19" in "Fig. P13.19" is struck through and "18" is written above it in green.)

13.49 The circuit in Fig. P13.~~19~~ 18 is excited by the source waveform shown in Fig. P13.33.

(a) Derive the expression for $v_{out}(t)$ using Fourier analysis.

(b) Plot $v_{out}(t)$ using $A = 5$, $T = 3$ ms, $R_1 = 500\ \Omega$, $R_2 = 2\ \text{k}\Omega$, and $C = 0.33\ \mu$F.

(c) Repeat (b) with $C = 0.33$ mF and comment on the results.

**Figure P13.18: Circuit for Problem 13.18.** Current source $i_s(t)$ (arrow up, circled in blue) on the left between the bottom rail and the top rail. From the top rail: $R_1$ shunt to the bottom rail, with current $i_1$ marked downward through it (blue arrow); then $R_2$ in series along the top toward the right, with current $i_2$ marked to the right (blue arrow); then capacitor $C$ shunt to the bottom rail; open output terminals to the right of $C$, labeled $+$ (top) and $-$ (bottom), $v_{out}(t)$.

**Figure P13.33: Waveform for Problem 13.33.** $f(t)$ versus $t$ (s): zero for $t < 0$; rises linearly from $0$ at $t = 0$ to $A$ at $t = T$ (dashed horizontal line at level $A$); drops vertically to 0 at $t = T$; zero afterwards.

## Page 1

Header: Ulaby 13.49

(Printed problem statement and the two figures pasted at upper left, as transcribed above.)

Handwritten at upper right:

**Example:** circuit analysis using Fourier transforms.

**Figure (redrawn circuit):** $i_s(t)$ current source (arrow up) on the left; $R_1$ shunt with $i_1$ arrow downward; $R_2$ in series on top with $i_2$ arrow to the right; $C$ shunt; output terminals to the right labeled $+$ (top) and $-$ (bottom), $v_{out}(t)$. To the right: $R_1 = 500\ \Omega$, $R_2 = 2\ \text{k}\Omega$, $C = 0.33\ \mu\text{F}$.

**Figure (redrawn waveform, blue):** $i_s(t)$ versus $t$ (s): zero before $t = 0$; linear ramp from $0$ at $t = 0$ up to $A$ (dotted level line) at $t = T$; vertical drop to 0 at $T$; zero afterwards. Annotations: $A = 5$ A, $T = 3$ ms; $i_s(t) = \frac{A}{T}t,\ 0 \le t \le T$.

a) in the $\omega$-domain

$$\underset{\sim}{I}_s(\omega) \equiv \mathcal{F}[i_s(t)] = \int_{-\infty}^{\infty} i_s(t)\,e^{-j\omega t}\,dt$$

(bottom line cut off: start of "$\int u\,dv = uv - \int v\,du$", repeated on page 2)

## Page 2

(Top: cut-off fragment of the previous line.)

$$= \int_0^T \frac{A}{T}\,t\,e^{-j\omega t}\,dt;$$

(side note:) $\int u\,dv = uv - \int v\,du$; $u = t$, $dv = e^{-j\omega t}dt$; $du = dt$, $v = \frac{-1}{j\omega}e^{-j\omega t}$

$$= \frac{A}{T}\left\{\left[\frac{-t}{j\omega}e^{-j\omega t}\right]_0^T + \int_0^T \frac{1}{j\omega}e^{-j\omega t}\,dt\right\}$$

$$= \frac{A}{T}\left\{-\frac{T e^{-j\omega T}}{j\omega} + \frac{1}{j\omega}\left[\frac{-1}{j\omega}e^{-j\omega t}\right]_0^T\right\}$$

$$= \frac{A}{T}\left\{-\frac{T e^{-j\omega T}}{j\omega} - \frac{1}{(j\omega)^2}\left(e^{-j\omega T} - 1\right)\right\}$$

$$\underset{\sim}{I}_s = \frac{A}{T\omega^2}\left[(1 + j\omega T)e^{-j\omega T} - 1\right]$$

analyze circuit in the $\omega$-domain with $\underset{\sim}{Z}_C = \frac{1}{j\omega C}$

$$\underset{\sim}{I}_2 = \frac{R_1}{R_1 + R_2 + \frac{1}{j\omega C}}\,\underset{\sim}{I}_s;\qquad \underset{\sim}{V}_{out} = \underset{\sim}{Z}_C\,\underset{\sim}{I}_2 = \frac{1}{j\omega C}\,\underset{\sim}{I}_2$$

$$\Rightarrow\ \underset{\sim}{V}_{out} = \frac{R_1}{1 + j\omega(R_1 + R_2)C}\,\underset{\sim}{I}_s$$

$$= \frac{AR_1}{T\omega^2}\left[\frac{(1 + j\omega T)e^{-j\omega T} - 1}{1 + j\omega(R_1+R_2)C}\right]$$

$$\underset{\sim}{V}_{out} = \frac{AR_1}{T}\left[\frac{e^{-j\omega T}}{\omega^2\big(1 + j\omega(R_1+R_2)C\big)} + \frac{jT e^{-j\omega T}}{\omega\big(1 + j\omega(R_1+R_2)C\big)} - \frac{1}{\omega^2\big(1 + j\omega(R_1+R_2)C\big)}\right]$$

## Page 3

(Top: cut-off repeat of the last $V_{out}$ line from page 2.)

Let

$$F_1(\omega) = \frac{1}{\omega^2\big(1 + j\omega(R_1+R_2)C\big)} = \frac{k_1}{\omega} + \frac{k_2}{\omega^2} + \frac{l_1}{1 + j\omega(R_1+R_2)C}$$

$$k_2 = \Big[\omega^2 F_1(\omega)\Big]\Big|_{\omega=0} = 1$$

$$k_1 = \left[\frac{d}{d\omega}\big(\omega^2 F_1(\omega)\big)\right]\Bigg|_{\omega=0} = \left[\frac{-j(R_1+R_2)C}{\big(1 + j\omega(R_1+R_2)C\big)^2}\right]\Bigg|_{\omega=0} = -j(R_1+R_2)C$$

$$l_1 = \Big[\big(1 + j\omega(R_1+R_2)C\big)F_1(\omega)\Big]\Big|_{\omega = j\frac{1}{(R_1+R_2)C}} = -(R_1+R_2)^2C^2$$

$$\Rightarrow\ F_1(\omega) = \frac{-j(R_1+R_2)C}{\omega} + \frac{1}{\omega^2} - \frac{(R_1+R_2)^2C^2}{1 + j\omega(R_1+R_2)C}$$

Then from Ulaby et al, Table 13-4, we have

$$\text{sgn}(t) \leftrightarrow \frac{2}{j\omega};\qquad |t| \leftrightarrow \frac{-2}{\omega^2};\qquad e^{-at}u(t) \leftrightarrow \frac{1}{a + j\omega}$$

$$\Rightarrow\ f_1(t) = \frac{(R_1+R_2)C}{2}\,\text{sgn}(t) - \frac{1}{2}|t| - (R_1+R_2)C\,e^{-t/(R_1+R_2)C}\,u(t)$$

(underlined in green)

Let

$$F_2(\omega) = \frac{1}{\omega\big(1 + j\omega(R_1+R_2)C\big)} = \frac{k_1}{\omega} + \frac{l_1}{1 + j\omega(R_1+R_2)C}$$

(last line cut off at the page break; repeated on page 4)

## Page 4

$$= \frac{k_1}{\omega} + \frac{l_1}{1 + j\omega(R_1+R_2)C}$$

$$k_1 = \Big[\omega F_2(\omega)\Big]\Big|_{\omega=0} = 1.$$

$$l_1 = \Big[\big(1 + j\omega(R_1+R_2)C\big)F_2(\omega)\Big]\Big|_{\omega = j\frac{1}{(R_1+R_2)C}} = -j(R_1+R_2)C$$

$$\Rightarrow\ F_2(\omega) = \frac{1}{\omega} - \frac{j(R_1+R_2)C}{1 + j\omega(R_1+R_2)C}$$

Again using results from Ulaby et al, Table 13-4,

$$f_2(t) = \frac{j}{2}\,\text{sgn}(t) - j\,e^{-t/(R_1+R_2)C}\,u(t)$$

(underlined in green)

Then

$$\underset{\sim}{V}_{out}(\omega) = \frac{AR_1}{T}\left[e^{-j\omega T}F_1(\omega) + jT e^{-j\omega T}F_2(\omega) - F_1(\omega)\right]$$

To transform $\underset{\sim}{V}_{out}(\omega)$ to the time domain, also note the time-shift property of Fourier transforms (Ulaby et al, Table 13-5):

$$f(t - t_0) \leftrightarrow e^{-j\omega t_0}F(\omega)$$

$$\Rightarrow\ v_{out}(t) = \frac{AR_1}{T}\Bigg[\frac{(R_1+R_2)C}{2}\,\text{sgn}(t-T) - \frac{1}{2}|t-T| - (R_1+R_2)C\,e^{-(t-T)/(R_1+R_2)C}\,u(t-T)$$

(continues; the next line, "$-\frac{T}{2}\text{sgn}(t-T) + T e^{-(t-T)/(R_1+R_2)C}u(t-T)$", is cut off at the page break and repeated on page 5)

## Page 5

$$\qquad - \frac{T}{2}\,\text{sgn}(t-T) + T\,e^{-(t-T)/(R_1+R_2)C}\,u(t-T)$$

$$\qquad - \frac{(R_1+R_2)C}{2}\,\text{sgn}(t) + \frac{1}{2}|t| + (R_1+R_2)C\,e^{-t/(R_1+R_2)C}\,u(t)\Bigg]$$

Boxed final result:

$$\boxed{\begin{aligned} v_{out}(t) = \frac{AR_1}{T}\Bigg[\ &(R_1+R_2)C\,e^{-t/(R_1+R_2)C}\,u(t) + \big(T - (R_1+R_2)C\big)e^{-(t-T)/(R_1+R_2)C}\,u(t-T) \\ &- \frac{1}{2}(R_1+R_2)C\,\text{sgn}(t) - \frac{1}{2}\big(T - (R_1+R_2)C\big)\text{sgn}(t-T) \\ &+ \frac{1}{2}|t| - \frac{1}{2}|t-T|\ \Bigg]\end{aligned}}$$

b)

(rest of page blank; plots on page 6)

## Page 6

**Figure (pasted plot, top, red):** $i_s(t)$ versus $t$ (s), horizontal axis $-2$ to $10$ ($\times10^{-3}$ s), vertical axis $0$ to $5$. Zero for $t<0$; linear ramp from $0$ at $t=0$ to $5$ at $t = 3$ ms; vertical drop to 0 at $3$ ms; zero afterward.

**Figure (pasted plot, bottom, cyan):** $v_{out}(t)$ versus $t$ (s), same horizontal axis, vertical axis $-500$ to $2000$ with ticks every 500. Zero for $t<0$; rises from 0 at $t=0$ with increasing slope (concave up) to a peak of about $1800$ at $t = 3$ ms; then decays exponentially toward 0, essentially reaching 0 by about $7$–$8$ ms. (Case $C = 0.33\ \mu$F.)

c) change $C$ from $0.33\ \mu$F to $0.33$ mF

## Page 7

**Figure (pasted plot, top, red):** $i_s(t)$ versus $t$ (s), same as page 6: ramp from 0 at $t=0$ to 5 at 3 ms, then drop to 0.

**Figure (pasted plot, bottom, cyan):** $v_{out}(t)$ versus $t$ (s), horizontal axis $-2$ to $10$ ($\times10^{-3}$ s), vertical axis $0$ to $5$. Zero for $t<0$; rises from 0 at $t = 0$ with increasing slope (concave up, parabola-like) to about $4.5$ at $t = 3$ ms; then stays essentially flat at about $4.5$ through $9$ ms (very slow decay). (Case $C = 0.33$ mF.)

When $C$ is increased from $0.33\ \mu$F to $0.33$ mF, the exponential time constant $(R_1+R_2)C$ for the capacitor charging + decay, [one short word struck through] and correspondingly $v_{out}(t)$, increases by $10^3$.

**Key points:**

(i) for Fourier transform circuit analysis, compute Fourier transforms of known source voltages and/or currents, then analyze circuit in $\omega$, i.e., phasor, domain.

## Page 8

(Top: repeat of the cut-off line "then analyze circuit in $\omega$, i.e., phasor, domain.")

(ii) once the desired voltage and/or current obtained in $\omega$-domain, use known Fourier transform pairs (Ulaby Table 13-4) and/or properties (Table 13-5) to compute inverse Fourier transforms and obtain results in time domain. Here, we used time-shift property of Fourier transforms to handle exponential factors in $\omega$-domain.

The rest of the page is blank.

## Narration transcript

Okay, this is Ulaby problem 13.49. And this is an example of, once again, circuit analysis, using Fourier transforms.

Okay, so the problem that we are addressing is shown here on the left. There's actually a misprint in the statement of the problem. The problem in the book says the circuit in Figure P13.19. But that's actually not correct. The circuit in that figure doesn't include any output voltage. What they actually meant was the circuit in Figure P13.18, which is shown down here, and so what we are asked to solve for is this output voltage $v_{out}$, labeled here, given an input $f(t)$, where $i_s(t)$ is equal to $f(t)$, given by this triangular waveform shown here. Okay. So part (a) asks us to derive an expression for $v_{out}$ using Fourier analysis in terms of these circuit parameters here, $R_1$, $R_2$, and $C$, and then $A$ and capital $T$. Part (b) asks for a plot of the output voltage with specific numerical values for all these parameters, and then part (c) asks for a plot with a different value of the capacitance, 0.33 millifarads instead of 0.33 microfarads.

Okay, so let's go ahead and get started on this. And so we will start off as usual by redrawing the circuit. So we have a current source $i_s(t)$, and then a resistor $R_1$, another resistor $R_2$, and then a capacitor $C$. Okay. And we are asked to solve for this output voltage. All right. The circuit diagram also has currents $i_1$ and $i_2$ labeled here; we'll use $i_2$ in part of what we work out. The circuit parameters in part (b) of this problem are that $R_1$ is equal to 500 ohms, $R_2$ is equal to 2 kilohms, and then $C$ is equal to 0.33 microfarads. Okay. And then the input waveform $i_s(t)$, okay, is basically a triangular waveform — not a periodic triangular waveform, just a triangular waveform — that looks like this. Okay. So here, the form of this is that $i_s$ is equal to $A$ over capital $T$ times the time $t$, for 0 less than or equal to $t$ less than or equal to capital $T$, and it is 0 outside of that interval, and in part (b) of the problem, and part (c), we take $A$ equal to 5 amps, and then $T$ equal to 3 ms.

Okay, so let's go ahead and solve this problem. All right. So what we're going to do here is we're going to take this circuit, we're going to transform it to the frequency domain, including computing the Fourier transform of $i_s(t)$, given by this expression here, all right, so that we have all its different frequency components. We will analyze the circuit in the frequency domain to obtain $v_{out}$ as a function of frequency, and then we'll have to compute the inverse Fourier transform of that to get $v_{out}(t)$. All right. So that's how we're going to proceed here.

So if we're working in the frequency domain, all right, we want to have our source $i_s(t)$ transformed to the frequency domain. So that would be capital $I_s(\omega)$. Right? So that is the Fourier transform of $i_s(t)$. All right, and that is given formally by the integral from minus infinity to infinity of $i_s(t)$ times $e$ to the minus $j\omega t$, $dt$. Okay? And if we substitute into that this expression here for $i_s(t)$, which is valid between 0 and capital $T$, then we have the integral from 0 to capital $T$ of $A$ over $T$ times $t$ times $e$ to the minus $j\omega t$, $dt$. Okay. So here, now, we want to deal with this factor of $t$ over here in the integrand. And so we're going to deal with that by doing integration by parts. So remember what integration by parts says is that the integral of $u\,dv$ is equal to $u$ times $v$ minus the integral of $v\,du$. Okay? So this is the integral that we're starting with over here; this is what we will have to compute after doing the integration by parts, and so what we will want to do then is, since we have $t$ over here, all right, we want to pick $u$ such that it allows us to take the derivative of $t$, so that it becomes just a constant in this integral over here rather than a factor of $t$. All right. And then whatever's left in here as $dv$ has to be something that we can integrate. All right, so we can do that by choosing $u$ to be equal to $t$, and $dv$ to be equal to the rest of it, $e$ to the minus $j\omega t$, $dt$ — right, $A$ over $T$ here is a constant, so we can just pull that outside the integral; we don't have to worry about it until later on. So then $du$ is equal to $dt$, and $v$ is equal to minus one over $j\omega$ times $e$ to the minus $j\omega t$.

All right. So if we then use integration by parts to work with this integral over here, we have the constant factor of $A$ over $T$, which we take to the outside, and then for $u$ times $v$ we have $t$ times minus one over $j\omega$ times $e$ to the minus $j\omega t$, evaluated at the limits of integration, 0 and $T$. So we have minus $t$ over $j\omega$ times $e$ to the minus $j\omega t$, evaluated at 0 and $T$. And then for minus the integral of $v\,du$, then we have minus minus here, so that becomes plus one over $j\omega$ times $e$ to the minus $j\omega t$ times $dt$. All right, so we have plus the integral from 0 to $T$ of one over $j\omega$, $e$ to the minus $j\omega t$, $dt$. Okay. And then, if we evaluate this first term over here, then evaluating at the upper limit we get minus capital $T$ over $j\omega$ times $e$ to the minus $j\omega$ capital $T$, and then at the lower limit of integration this becomes 0 because of this $t$ over here, which takes on a value of 0. So we get $A$ over $T$, and then from this first term over here we have minus capital $T$ $e$ to the minus $j\omega$ capital $T$ over $j\omega$, plus, and then from the integral we have one over $j\omega$, which we pull to the outside, and then we're integrating $e$ to the minus $j\omega t$, and that is minus one over $j\omega$ times $e$ to the minus $j\omega t$, evaluated at the limits of integration, 0 and capital $T$. Okay? And so then, if we go ahead — we'll just carry this first term down, and then we'll evaluate this second term over here. So we have $A$ over $T$ times minus $T$ $e$ to the minus $j\omega$ capital $T$ over $j\omega$, and then we have minus one over $j\omega$, the quantity squared — okay, so that gives us minus one over $(j\omega)^2$ — and then we have $e$ to the minus $j\omega t$ evaluated at capital $T$, minus the same thing evaluated at 0, that is, $e$ to the minus $j\omega$ capital $T$ minus one.

Okay. And then if we just rearrange this slightly, we'll have $A$ over $T$, and then we'll factor out an $\omega^2$ in the denominator, right; that takes this $\omega^2$ out here; then we have $j^2$ in the denominator, that becomes minus one, that cancels out this minus sign, all right, and then from this term over here we'll get a $j\omega$ in the numerator. Okay, so we have $A$ over $T\omega^2$, and then we have one plus $j\omega T$ times $e$ to the minus $j\omega T$, minus one. All right. So this is what we get, finally, for $I_s(\omega)$. Okay.

So now with this, what we want to do is we want to go back to this circuit up here, all right, and we want to figure out this output voltage $v_{out}$ in the frequency domain, and the way that we can do that is to compute in the frequency domain this current $I_2(\omega)$, which we can do by current division, since we know that the total current is $I_s(\omega)$, and that current gets divided between $I_1$ and $I_2$, since this resistor and this part of the circuit here are in parallel. All right, so we can get $I_2$ by current division, and then once we have $I_2$, then $V_{out}$ is just the impedance associated with the capacitor, which is one over $j\omega C$, times $I_2$. All right. So what we want to do next, then, is to analyze the circuit in the frequency domain with the impedance of the capacitor being one over $j\omega C$. Okay? So if we do that, then, as I was describing, the current $I_2$ in the frequency domain can be obtained by current division. So that's going to be $R_1$, the impedance of the other branch of the two parallel branches, divided by the sum of the impedances of the two branches, which is $R_1 + R_2 + 1/(j\omega C)$, all of this times the total current that gets divided, $I_s$. Right. And then once we have $I_2$, then $V_{out}$ is just going to be the impedance of the capacitor times $I_2$, since $V_{out}$ is the voltage across the capacitor, and $I_2$ is the current through the capacitor. So that's going to be one over $j\omega C$ times $I_2$, and $I_2$ is given by this expression here, where $I_s$ is given by this expression over here.

Okay, so now this means that we can write $V_{out}$ as being equal to this expression here, $I_2$, times one over $j\omega C$. All right. So we're going to have a factor of $j\omega C$ that we're introducing in the denominator. So what we get, then, is in the numerator we still have $R_1$ — all right, that's this $R_1$ from up here — and in the denominator, when we multiply this by $j\omega C$, we get one, from this one over $j\omega C$ times $j\omega C$, plus $j\omega$ times $R_1 + R_2$ times $C$. All this times $I_s$. $I_s$ is given by this expression up here. Okay — this is a plus sign here. All right. And so if we take that and we substitute it in here for $I_s$, then what we get is that $V_{out}$ is equal to $A$ times $R_1$ over $T$ times $\omega^2$ — we'll try to keep these all visible, right. So we have $A$ over $T\omega^2$ times $R_1$; that gives us this factor here. Then we have what's in the square brackets for $I_s$ up here, divided by this denominator over here. Okay, so we have one plus $j\omega T$ times $e$ to the minus $j\omega T$ minus one in the numerator, divided by one plus $j\omega(R_1 + R_2)C$ in the denominator.

Okay. So now, this is our expression for $V_{out}$, and to work with this further, what we are going to do is we're going to bring this $\omega^2$ back in here, and we're going to separate out this expression into three terms corresponding to these three different terms in the numerator. So that'll give us $AR_1$ over $T$, and then we will have, for this first term here, corresponding to the one, it is $e$ to the minus $j\omega T$ divided by — now we're bringing the $\omega^2$ inside the square brackets — so we have $\omega^2$ times one plus $j\omega(R_1+R_2)C$. All right. Then from the second term, right, it's $j\omega T$ times $e$ to the minus $j\omega T$ in the numerator; this $\omega$ will cancel out with one power of $\omega$ in the denominator, so we're going to get in the numerator $j$ times $T$ $e$ to the minus $j\omega T$, divided by, in the denominator, $\omega$ times one plus $j\omega(R_1+R_2)C$; and then from the third term over here, this minus one in the numerator, we're going to get minus one over $\omega^2$ times one plus $j\omega(R_1+R_2)C$.

Okay. So now we have $V_{out}(\omega)$, right, written in this form here, and we are going to need to figure out how to calculate the inverse Fourier transform of this. So what we're going to need to do is to take this and express it in a way that allows us to easily identify, say, the frequency side of known Fourier transform pairs, or such that we can calculate the Fourier transform explicitly, relatively easily. Okay. So let's look at these three terms here. All right. We can see this third term out here is one that we can deal with fairly easily, because if we do a partial fraction expansion of this, then we'll get this into a form of basically a sum of simple poles. And that's something for which we know how to compute the Fourier transform; all right, basically, it's going to be exponentials. All right, then these other terms over here, all right, we have these exponential factors; the $j$ times capital $T$ here is just a constant, so we don't really need to worry about that; and then we have various combinations of poles in the denominator. All right. So we're going to deal with this term here first, and we will deal with this by computing its partial fraction expansion. And then from there we'll look at this term over here. We'll compute the partial fraction expansion of just the part — taking the numerator to be one, so basically just the denominator portion of this — and we'll figure out how to deal with the exponential later. This first term is the same as this third term over here times $e$ to the minus $j\omega T$. All right. So by understanding how we can deal with the exponential over here, that will also allow us to deal with this particular term.

Okay, so we're starting off with this third term on the right. So let's define a function — we'll call it capital $F_1(\omega)$ — and we'll take that to be one over $\omega^2$ times one plus $j\omega(R_1 + R_2)C$. Okay, and then we'll deal with the minus one here later. All right! So for this, all right, what we want to do is to compute its partial fraction expansion, right? So that's going to be $k_1$ over $\omega$ plus $k_2$ over $\omega^2$ plus $l_1$ over one plus $j\omega(R_1+R_2)C$. All right, and $k_1$, $k_2$, and $l_1$ are just constants. All right, and we saw when we talked about Laplace transforms how we can calculate these. Okay. $k_2$ is equal to, all right, it's $\omega^2$ times $F_1(\omega)$, right, evaluated at $\omega$ equal to 0, and if we just take this expression here for $F_1$ multiplied by $\omega^2$, so we cancel out this $\omega^2$ in the denominator, evaluate this at $\omega$ equal to 0, we can see this is just one. Then $k_1$ is equal to the derivative with respect to $\omega$ of $\omega^2 F_1(\omega)$, evaluated at $\omega$ equal to 0 again. Okay. And for this, right, if we have $\omega^2$ times $F_1$, that's one over one plus $j\omega(R_1+R_2)C$, and if we take the derivative of that with respect to $\omega$, then we will get in the numerator minus $j$ times $(R_1+R_2)C$, divided by the denominator squared, so one plus $j\omega(R_1+R_2)C$, the quantity squared. This evaluated at $\omega$ equal to 0 — when we set $\omega$ equal to 0, the denominator becomes one. So this is now minus $j$ times $(R_1+R_2)C$. All right, and then finally, for the residue $l_1$, that is given by one plus $j\omega(R_1+R_2)C$ times $F_1(\omega)$, this evaluated at $\omega$ equal to its value at the pole, which is $j$ times one over $(R_1+R_2)C$. Okay. And if we take one plus $j\omega(R_1+R_2)C$ multiplied by $F_1(\omega)$, right, then we're just going to get one over $\omega^2$. And if we calculate one over $\omega^2$ for this value of $\omega$, then we're going to get minus $(R_1+R_2)$, the quantity squared, times $C^2$. Okay, so those are our three residues that we need for the partial fraction expansion of this function $F_1(\omega)$. Okay? And then that gives us the result that $F_1(\omega)$ is equal to $k_1$ over $\omega$ — right, so $k_1$ is this, so minus $j$ times $(R_1+R_2)C$ over $\omega$ — plus $k_2$ over $\omega^2$ — $k_2$ is one, so plus one over $\omega^2$ — and then plus $l_1$ over one plus $j\omega(R_1+R_2)C$; so $l_1$ is this, so we have minus $(R_1+R_2)^2$ times $C^2$ divided by one plus $j\omega(R_1+R_2)C$.

Okay. So now we have $F_1(\omega)$ in a form, with these three terms here, where we can compute its inverse Fourier transform, right, taking this back to the time domain, using various entries from the table in Ulaby — that's Table 13-4 — that contains the common Fourier transform pairs. All right! So then, from Ulaby et al. Table 13-4, all right, the results that are going to be relevant are that the sign function of $t$, $\text{sgn}(t)$, forms the Fourier transform pair with 2 over $j\omega$; then, that the absolute value of $t$ forms the Fourier transform pair with minus 2 over $\omega^2$; and then that $e$ to the minus $at$ times $u(t)$ forms a Fourier transform pair with one over $a + j\omega$. Okay, so using these results and what we computed for $F_1(\omega)$ up here, then what we get is that, for this first term over here, right, we use this result, all right, this Fourier transform pair — the sgn of $t$ forms the Fourier transform pair with 2 over $j\omega$ — and, all right, so we get that $f_1(t)$, all right, the inverse Fourier transform of $F_1(\omega)$ up here: the first term is going to give us $(R_1 + R_2)C$ over 2 times the sgn of $t$. All right. Then the second term, one over $\omega^2$, okay, is going to give us minus one half times the absolute value of $t$. So minus one half times the absolute value of $t$. And then this third term over here is going to give us minus $(R_1 + R_2)C$ — right, we're going to pull out a factor of $(R_1 + R_2)C$ from the denominator; that cancels with one power of those up here, and we will have one over $(R_1+R_2)C$ plus $j\omega$ — and then the end result of that is that this third term gives us, in the time domain, $(R_1+R_2)C$ times $e$ to the minus $t$ over the quantity $(R_1+R_2)C$, times $u(t)$. Okay, so that is the inverse Fourier transform of this function, $f_1(t)$. Okay, so we're going to keep that result in mind because we're going to use it later.

Okay. Now let's go back to $V_{out}$. All right, this is $V_{out}$. Okay. And let's think about how to deal with this term over here. So as an intermediate step to dealing with this term, then what we're going to do is we're going to think about a function in the frequency domain that is just one over $\omega$ times the quantity one plus $j\omega(R_1+R_2)C$. All right. So let's define another function; we'll call it $F_2(\omega)$. We'll take that to be one over $\omega$ times one plus $j\omega(R_1+R_2)C$. All right, and we want to perform a partial fraction expansion of this. Okay, so we're going to get $k_1$ over $\omega$ plus $l_1$ over one plus $j\omega(R_1+R_2)C$. All right, and we need to compute these residues $k_1$ and $l_1$. So $k_1$, all right, we know, is just going to be $\omega$ times $F_2(\omega)$ evaluated at $\omega$ equal to 0. Okay. And so if we multiply $F_2$ by $\omega$, we cancel out this $\omega$ in the denominator; we evaluate what's left at $\omega$ equal to 0; that's just one. Okay. Then we have $l_1$, and that is one plus $j\omega$ times the quantity $(R_1+R_2)C$, times $F_2(\omega)$, evaluated at $\omega$ equal to $j$ times one over $(R_1+R_2)C$. Okay. And if we take one plus $j\omega(R_1+R_2)C$ multiplied by $F_2(\omega)$, then what we get is just one over $\omega$; we're going to evaluate that at this value of $\omega$ over here, and so that gives us minus $j$ times $(R_1+R_2)C$. Okay? And so that means that $F_2(\omega)$, right, its partial fraction expansion is given over here with $k_1$ equal to one, $l_1$ equal to minus $j$ times the quantity $(R_1+R_2)C$. So $F_2(\omega)$, then, is one over $\omega$ minus $j$ times $(R_1+R_2)C$ divided by one plus $j\omega(R_1+R_2)C$.

All right. So now here, okay, these are, once again, results in the frequency domain that we can look up in Ulaby et al. Table 13-4, and using that, then we can directly write down what the corresponding inverse Fourier transformed time-domain functions are. So now again at this point we're using results from Ulaby et al. Table 13-4. All right! Then what we get is that $f_2(t)$, okay, is equal to — so for one over $\omega$, all right, we use the Fourier transform pair that the sgn of $t$ forms a Fourier transform pair with 2 over $j\omega$, or equivalently one over $\omega$ forms a Fourier transform pair with $j$ over 2 times the sgn of $t$. So we have $j$ over 2 times the sgn of $t$ from the one over $\omega$, and then from minus $j$ times $(R_1+R_2)C$ over one plus $j\omega(R_1+R_2)C$, then we use this Fourier transform pair over here, and what we get is that we have minus $j$ times $e$ to the minus $t$ over $(R_1+R_2)C$, times $u(t)$. Okay, so this is the inverse Fourier transform of $F_2(\omega)$.

Okay. So now, what we want to do is to go back to our expression for $V_{out}$ over here and write this in terms of our functions $F_1(\omega)$ and $F_2(\omega)$, and whatever else we need, and if we do that, then what we get is that $V_{out}(\omega)$ is $AR_1$ over $T$ — okay, that's our overall factor out in front — and then from that first term in our expression for $V_{out}$ that we had up above, we get $e$ to the minus $j\omega T$ times $F_1(\omega)$. Right. That's this term over here, all right, because $F_1(\omega)$ is just this one over $\omega^2$ — right, it's one over $\omega^2$ times this quantity in the parentheses here. All right. This second term is going to be $j$ times $T$ times $e$ to the minus $j\omega T$ times $F_2(\omega)$, right, because $F_2(\omega)$ was one over $\omega$ times this quantity in the parentheses. And then this third term over here is just going to be minus $F_1(\omega)$. Okay. So if we come back down here and write that down, the second term is plus $j$ times $T$ times $e$ to the minus $j\omega T$ times $F_2(\omega)$, and then the third term is minus $F_1(\omega)$. Okay? So we know how to transform $F_1(\omega)$ to the time domain, right? This will just give us $f_1(t)$, right, which we calculated up here. All right, these other two terms have these exponential functions, $e$ to the minus $j\omega T$ — right, the $jT$ here is just a constant, so we don't really have to work too hard to deal with that; we just keep multiplying by it. All right, but to deal with the exponential factors, then what we want to do is to take advantage of what's known as the time shift property of Fourier transforms, and that's something that we discussed in class, and also it's in Ulaby et al. Table 13-5, the table of Fourier transform properties. Okay.

So to transform $V_{out}(\omega)$ to the time domain, all right, what we also need to do is, we can note the time shift property for Fourier transforms. Okay. And this is in Ulaby et al. Table 13-5. Okay, and what the time shift property tells us is that $f(t - t_0)$, for some constant $t_0$, in the time domain forms a Fourier transform pair with $e$ to the minus $j\omega t_0$ times $F(\omega)$, where $f(t)$ and $F(\omega)$ themselves form a Fourier transform pair. Right. So this says that an exponential phase factor in the frequency domain corresponds to a shift in time in the time domain, so that will allow us to deal with these exponential factors that show up here and here in $V_{out}(\omega)$. All right.

And so if we use this property here along with the $f_1(t)$ and the $f_2(t)$ that we calculated several minutes ago, all right, then what that will finally give us is that $v_{out}(t)$ is equal to the following — see if we can keep that there. So it's going to be $AR_1$ over $T$, and then from this first term, this is going to give us just small $f_1(t)$, but evaluated at a time-shifted time, $t$ minus capital $T$. Okay? And so that is going to then be — if you go back and look at what we had for $f_1(t)$, all right, it's this — so we're going to get these three terms evaluated not at $t$ but at $t$ minus capital $T$. Okay. So if we write those down, then it's going to be $(R_1+R_2)C$ over 2 times the sgn of $t$ minus capital $T$, minus one half the absolute value, not of $t$, but of $t$ minus capital $T$, minus $(R_1+R_2)C$ times $e$ to the minus, and then it's $t$ minus capital $T$ divided by $(R_1+R_2)C$, times $u$ of $t$ minus capital $T$. Okay. Then here, from this second term, we're going to have lowercase $f_2(t)$ times $jT$. But $f_2(t)$ is going to be evaluated not at $t$ but at $t$ minus capital $T$. So $f_2$ was given by this expression over here, so we're going to evaluate this at $t$ minus capital $T$ and multiply it by $j$ times $T$. All right. And so if we do that, all right, then we get minus capital $T$ over 2 times the sgn of $t$ minus capital $T$, all right, plus capital $T$ times $e$ to the minus $t$ minus capital $T$ over $(R_1+R_2)C$, times $u$ of $t$ minus capital $T$. And then finally, we will have minus, and then from $F_1(\omega)$, when we perform the inverse Fourier transform of that, we just get minus $f_1(t)$. All right, and so that is going to be minus $(R_1+R_2)C$ over 2 times the sgn of $t$, plus one half times the absolute value of $t$, plus $(R_1+R_2)C$ times $e$ to the minus $t$ over $(R_1+R_2)C$, times $u(t)$.

All right, and we will write this in a slightly different way now for the final result, all right, just by grouping the terms a little bit differently. So we have $AR_1$ over $T$ out in front, and then, to start off with, we will put together these terms here that have the exponentially decaying functions over here. All right. And so first, we'll have the exponentially decaying function evaluated at just $t$. So we will have $(R_1+R_2)C$ times $e$ to the minus $t$ over $(R_1+R_2)C$, times $u(t)$. All right. That's this term here. And then for these two terms here we're going to have $T$ minus the quantity $(R_1+R_2)C$, both of those times the exponential factor now evaluated at $t$ minus capital $T$, times the unit step function in $t$ minus capital $T$. So we're going to have plus $T$ minus $(R_1+R_2)C$ times $e$ to the minus $t$ minus capital $T$ over $(R_1+R_2)C$, times $u$ of $t$ minus capital $T$. Okay, so that takes care of this term and this term. Then we will have our terms that are proportional to the sgn function. Again, we will start with this one that is not time shifted. So we have minus one half $(R_1+R_2)C$ times the sgn of $t$, right? That's this term here. And then we'll have these two terms here, and we'll write those as minus one half times $T$ minus the quantity $(R_1+R_2)C$, all right, times the sgn of $t$ minus capital $T$, right? So that's this term and this term. And then finally, we will have the terms that have the absolute value of $t$. Okay, so we have plus one half times the absolute value of $t$ — that's this term — minus one half times the absolute value of $t$ minus capital $T$ — that is this term here — and that is everything.

Okay, so that is the result for part (a). All right. So we've calculated analytically an expression for $v_{out}(t)$ in terms of the parameters $R_1$, $R_2$, $C$, capital $A$ and capital $T$. Right. Part (b) asked us, if we go back to the statement of the problem back here, okay, it asked us to plot $v_{out}$ using these numerical values, all right, for these different parameters. And so for that, what I will do is I will just paste in from the solutions. Okay, so let me do that on the other computer here, and paste it in here. Okay. It should be showing up soon. Okay, there it is. So $i_s(t)$, remember, is this function here, all right, and then $v_{out}$, right — basically, what you can see is that, as $i_s$ is increasing, then we're gradually, basically, we're gradually charging up the capacitor, right? Because $v_{out}$ is the voltage across the capacitor. So we're gradually charging it up; when the current turns off, then we are discharging the capacitor. All right! So it discharges like this. Okay, so that is part (b).

All right, then part (c) is that we change $C$ from 0.33 microfarads to 0.33 millifarads. Okay. And if we do that, right, basically what we should expect is that the time constant for this charging should increase. Okay? And so what we'll do here is we will paste that in as well. Grab this, okay, and paste that in, and we'll wait for that to show up. Okay. And it looks like this. So basically, what we see is that, right, the charging doesn't necessarily look that different. But actually it is different, because if you look up here, right, it's charging up to — this is times $10^{-3}$ — all right, so on this scale here it's 1500; all right, this scale up here, this is only single digits. Okay, so the capacitor is actually charging up much more slowly, and it's also discharging much more slowly. All right! So basically, what happens is that when the capacitance is increased, then the characteristic time constant, which is the quantity $(R_1+R_2)C$, correspondingly increases as well, and so the charging and discharging of the capacitor is much slower, which is what the numerical results basically show us. All right. So when the capacitance is increased from 0.33 microfarads to 0.33 millifarads, right, then what happens is that the exponential time constant $(R_1+R_2)C$, right, for the capacitor charging and decay, and then correspondingly $v_{out}(t)$, all right, it increases by a factor of $10^3$. All right, and we see that in the numerical results.

### Key points (instructor retrospective)

Okay, so what are the key points, if we go back and look at what we did here? What are the key points, and perhaps lessons, that we can draw from this? Okay. The first is that, right, once again — if you watch some of the other examples — when we're doing circuit analysis by Fourier transform, what we do essentially is we take the known source voltages and/or currents, and we compute their Fourier transforms. So we see what different frequency components those source voltages and/or currents contain. All right, then we analyze the circuit in the frequency, that is, the phasor, domain, so that we obtain the response of the circuit — whatever quantity we are trying to solve for — as a function of frequency, right; that works at each different frequency, right? And so we get a function of frequency. And then once we have that function of frequency, then we perform the inverse Fourier transform to bring it back to the time domain, which is where we typically want our final result. And to do that, what we want to do is to take our function in the frequency domain and put it into a form that allows us to more straightforwardly compute or look up the inverse Fourier transform, right, either by looking at the common Fourier transform pairs in Table 13-4 of Ulaby, or by taking advantage of some of the known properties of Fourier transforms, which are listed and summarized in Table 13-5. Okay?

So the first point is that if we're doing Fourier transform circuit analysis, then, essentially, what we want to do is we want to compute the Fourier transform, or transforms, of our known source voltages and/or currents. All right, that tells us what are the components of those known source voltages and/or currents at different frequencies, and then, once we have that, we can analyze the behavior of the circuit as a function of frequency, right, so essentially at each different frequency, and the frequency domain is basically the phasor domain. All right. So then we analyze the circuit in the frequency, right, basically, that is the phasor, domain.

All right! Once we've obtained our result in the frequency domain — all right, so once the desired voltage and/or current is obtained in the frequency domain — then what we want to do is to put that function, or those functions, in a form that is easily transformed back to the time domain using either known Fourier transform pairs or the various properties of Fourier transforms. Right, so we want to use known Fourier transform pairs — all right, that's Ulaby Table 13-4 — and/or Fourier transform properties — those are in Table 13-5 — to compute the inverse Fourier transforms, and thereby to obtain our results in the time domain. Okay, which is where we typically want them. And so what we did with respect to the latter in this particular example was, we used the time shift property of Fourier transforms to handle exponential factors that were present in the frequency domain. All right! So here, we used the time shift property of Fourier transforms to handle the exponential factors that were present in the frequency domain. Okay, that's not the only way to do it, but I think in this case it was actually the simplest way to do it.

Okay, so that is [recording ends; caption file is cut off here].

## Index terms

Ulaby 13.49, Problem 13.49, Fig. P13.18, Fig. P13.33, misprint Fig. P13.19, Fourier transform circuit analysis, triangular pulse, ramp i_s(t) = (A/T) t on 0 to T, A = 5 A, T = 3 ms, R_1 = 500 ohm, R_2 = 2 kilohm, C = 0.33 microfarad, C = 0.33 millifarad, Fourier transform integral, integration by parts, u dv = uv - v du, I_s(omega) = (A/(T omega^2))[(1 + j omega T) e^{-j omega T} - 1], omega-domain, capacitor impedance Z_C = 1/(j omega C), current division, I_2, V_out = R_1 I_s / (1 + j omega (R_1+R_2) C), three-term split, partial fraction expansion, residues k_1 k_2 l_1, double pole at omega = 0, pole at omega = j/((R_1+R_2)C), F_1(omega), F_2(omega), Ulaby Table 13-4 Fourier transform pairs, sgn(t) <-> 2/(j omega), |t| <-> -2/omega^2, e^{-at} u(t) <-> 1/(a + j omega), f_1(t), f_2(t), Ulaby Table 13-5 Fourier transform properties, time-shift property f(t - t_0) <-> e^{-j omega t_0} F(omega), unit step u(t - T), exponential time constant (R_1 + R_2) C, capacitor charging and discharging, v_out(t) boxed result, plots of i_s(t) and v_out(t), time constant increases by 10^3, Ulaby/Maharbiz/Furse
