---
course: ECE 411H
kind: problem-video
source: Problem Solving Videos/Ulaby 9.19.pdf (captions: Problem Solving Videos/Ulaby 9.19 captions.vtt)
source_pages: 6
author: Prof. Ed Yu
unit: exam2
topics: [bode-plots, bode-magnitude, bode-phase, straight-line-approximation, transfer-function, standard-form, poles-and-zeros, simple-pole, simple-zero, quadratic-pole, quadratic-zero, pole-at-origin, zero-at-origin, db-scale, decade-slopes, phase-wrapping, limiting-behavior, chapter-9]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
deepgram_transcript: deepgram/Ulaby_9.19.deepgram.txt
deepgram_paragraphs: deepgram/Ulaby_9.19.deepgram.md
---

# Ulaby 9.19 — Bode magnitude and phase plots from four transfer functions (problem-solving video)

**Summary.** Prof. Yu works Ulaby/Maharbiz/Furse Problem 9.19, a four-part problem: generate straight-line-approximation Bode magnitude and phase plots for four voltage transfer functions $\mathbf H(\omega)$. Part (a) has only simple poles/zeros (zero at 10; poles at 2, 50, 100; constant 15); part (b) has second-order zeros at 5 and 50, a third-order pole at the origin and a simple pole at 500 (constant 20); part (c) has a simple zero at 1, a simple pole at the origin and a quadratic pole at 4 (constant 1/20); part (d) has a second-order zero at the origin, a quadratic zero at 10, a simple pole at 1 and a third-order pole at 100 (constant 1/10). For each he rewrites $\mathbf H$ in standard form $K\prod(1+j\omega/\omega_z)/\prod(1+j\omega/\omega_p)$, lists poles and zeros, computes $M(0)$, $M(\infty)$, $\phi(0)$, $\phi(\infty)$, then builds the magnitude plot (slopes $\pm 20N$ dB/dec changing exactly at each pole/zero) and the phase plot (each simple factor ramps $\pm 45^\circ$/dec from $\omega_{p,z}/10$ to $10\omega_{p,z}$; sketch each contribution in blue, sum in green). Key points written on the page: write $\mathbf H$ in standard form; mark all poles/zeros; magnitude contributions add on the dB scale because $\log[ab]=\log a+\log b$; for phase also mark $\omega_{p,z}/10$ and $10\omega_{p,z}$; check limits; start the magnitude plot from the limit where $M$ is a known constant; if the phase leaves $[-360^\circ,+360^\circ]$, translate $\pm360^\circ$ to $0^\circ$. This is the canonical Bode-construction procedure for Exam 2.

> **Audio transcript (Deepgram nova-3, ECE 411 keyterms, timestamped):** `deepgram/Ulaby_9.19.deepgram.txt` ; paragraph form: `deepgram/Ulaby_9.19.deepgram.md`. Fresh ASR of the video audio; where it disagrees with the Narration section (built from the published auto-captions), prefer this file and the handwritten page.

## Problem statement

**9.19** Generate Bode magnitude and phase plots (straight-line approximations) for the following voltage transfer functions.

(a) $\displaystyle \mathbf H(\omega) = \frac{4\times 10^4 (60 + j6\omega)}{(4 + j2\omega)(100 + j2\omega)(400 + j4\omega)}$

(b) $\displaystyle \mathbf H(\omega) = \frac{(1 + j0.2\omega)^2 (100 + j2\omega)^2}{(j\omega)^3 (500 + j\omega)}$

(c) $\displaystyle \mathbf H(\omega) = \frac{8\times 10^{-2} (10 + j10\omega)}{j\omega (16 - \omega^2 + j4\omega)}$

(d) $\displaystyle \mathbf H(\omega) = \frac{4\times 10^4 \omega^2 (100 - \omega^2 + j50\omega)}{(5 + j5\omega)(200 + j2\omega)^3}$

## Page 1

Header: "Ulaby 9.19". The textbook problem statement with all four transfer functions (as above) is pasted at top left.

Handwritten, top right:

**Examples:** Bode plots generated from transfer functions $\underline{\mathbf H}(\omega)$

**a)**
$$\mathbf H(\omega) = \frac{4\times 10^4 (60 + j6\omega)}{(4 + j2\omega)(100 + j2\omega)(400 + j4\omega)}$$

$$= \frac{\boxed{(4\times 10^4)(60)}\;(1 + j\omega/10)}{\boxed{(4)(100)(400)}\;\left(1 + j\frac{\omega}{2}\right)\left(1 + j\frac{\omega}{50}\right)\left(1 + j\frac{\omega}{100}\right)}$$

(The constants $(4\times10^4)(60)$ over $(4)(100)(400)$ are enclosed in a dashed box with a brace underneath: $= 15$.)

simple zero at $\omega = 10$
simple poles at $\omega = 2, 50, 100$

$M(0) = 20\log 15 = 23.5\ \text{dB}$ $\qquad$ $\phi(0) = 0^\circ$
$M(\infty) = 0 = -\infty\ \text{dB}$ $\qquad$ $\phi(\infty) = \pm 180^\circ$

**Figure (Bode magnitude plot, part a, green curve):** Vertical axis labeled $M(\omega)\,[\text{dB}]$ with the value 23.5 marked; horizontal axis $\omega$ (log scale) with ticks at 2, 10, 50, 100, each with a vertical dashed guide line. The green straight-line curve: flat at 23.5 dB from the left up to $\omega = 2$; then descends from 2 to 10, labeled "$-20$ dB/dec."; flat from 10 to 50; descends from 50 to 100, labeled "$-20$ dB/dec"; then descends more steeply beyond 100, labeled "$-40$ dB/dec."

Bottom of page: the beginning of the phase plot (axis label $\phi$, tick "90°", a horizontal dashed line at 90° and the start of a blue dashed line). This plot is split by the OneNote page break and is drawn in full at the top of Page 2.

## Page 2

**Figure (Bode phase plot, part a):** Vertical axis $\phi$ with ticks at $90^\circ$, $0^\circ$, $-90^\circ$, $-180^\circ$ and horizontal dashed guide lines at $+90^\circ$, $-90^\circ$, $-180^\circ$. Horizontal axis $\omega$ with ticks at 0.1, 0.2, 1, 2, 5, 10, 20, 50, 100, 500, 1000.

Blue dashed lines (individual contributions, each with a dot at its endpoints and at the pole/zero frequency):
- simple zero at 10: from $0^\circ$ at $\omega = 1$ up to $+90^\circ$ at $\omega = 100$ (passes $45^\circ$ at 10);
- simple pole at 2: from $0^\circ$ at $\omega = 0.2$ down to $-90^\circ$ at $\omega = 20$;
- simple pole at 50: from $0^\circ$ at $\omega = 5$ down to $-90^\circ$ at $\omega = 500$;
- simple pole at 100: from $0^\circ$ at $\omega = 10$ down to $-90^\circ$ at $\omega = 1000$.

Green solid line (total phase), with green arrows labeling the slope of each segment:
- $0^\circ$ (flat) up to $\omega = 0.2$;
- $0.2 \to 1$: "$-45^\circ$/dec.";
- $1 \to 5$: "$0^\circ$/dec";
- $5 \to 10$: "$-45^\circ$/dec.";
- $10 \to 20$: "$-90^\circ$/dec.";
- $20 \to 100$: "$-45^\circ$/dec.";
- $100 \to 500$: "$-90^\circ$/dec.";
- $500 \to 1000$: "$-45^\circ$/dec";
- flat at $-180^\circ$ beyond 1000.

**Key points:**

(i) write $\underline{\mathbf H}(\omega)$ in standard form given in class or Ulaby.

(ii) identify + mark all poles and zeros in $\underline{\mathbf H}(\omega)$

(iii) in magnitude plot, transition from $\omega \to 0$ to $\omega \to \infty$ behavior occurs exactly at each zero or pole. Effects of each pole or zero on plot can be added directly to each other on dB scale, since $\log[ab] = \log a + \log b$. Also check limiting behavior for $M(0)$, $M(\infty)$.

(iv) in phase plot, mark all poles + zeros in $\mathbf H(\omega)$, **plus** $\frac{\omega_{p,z}}{10}$ and $10\omega_{p,z}$ points. For each pole/zero, $\omega \to 0$ behavior occurs for $\omega < \frac{\omega_{p,z}}{10}$, and $\omega \to \infty$ behavior occurs for $\omega > 10\omega_{p,z}$, with linear transition in between. Sketch phase for each zero or pole, then add together. Check limiting behavior for $\phi(0)$, $\phi(\infty)$.

**b)**
$$\mathbf H(\omega) = \frac{(1 + j0.2\omega)^2 (100 + j2\omega)^2}{(j\omega)^3 (500 + j\omega)}$$

(Bottom of page is cut by the page break; the next line, "$= \ldots$" and "2nd order zeros at $\omega = 5, 50$", is repeated in full at the top of Page 3.)

## Page 3

(Top: the tail of the part (b) expression from Page 2, "$(j\omega)^3(500 + j\omega)$", cut off by the page break.)

$$= \frac{\boxed{100^2}\;\left(1 + \frac{j\omega}{5}\right)^2 \left(1 + \frac{j\omega}{50}\right)^2}{\boxed{500}\;(j\omega)^3 \left(1 + \frac{j\omega}{500}\right)}$$

(The constants $100^2$ over $500$ are in a dashed box with a brace: $= 20$.)

2nd order zeros at $\omega = 5, 50$
3rd order pole at $\omega = 0$
simple pole at $\omega = 500$.

$M(0) = \infty$
$$M(\infty) = 20\log\left(\frac{20\,(500)}{5^2 \cdot 50^2}\right) = -15.9\ \text{dB}$$
$\phi(0) = 90^\circ$
$\phi(\infty) = 0^\circ$

**Figure (Bode magnitude plot, part b, green):** Vertical axis $M(\omega)\,[\text{dB}]$ with $-15.9$ marked; horizontal axis $\omega$ with ticks at 0.5, 1, 5, 50, 500, 5000; vertical dashed guides at 5, 50, 500. Green curve: comes down steeply from above the axis at $\omega \approx 1$ to the $-15.9$ level at $\omega = 5$, labeled "$-60$ dB/dec."; from 5 to 50 descends, labeled "$-20$ dB/dec." (minimum at $\omega = 50$); from 50 to 500 rises, labeled "20 dB/decade", reaching $-15.9$ dB at 500; flat beyond 500, labeled "$-15.9$ dB".

**Figure (Bode phase plot, part b):** Vertical axis $\phi$ with ticks $360^\circ$, $270^\circ$, $180^\circ$, $90^\circ$, $0^\circ$, $-90^\circ$; horizontal axis $\omega$ with ticks 0.5, 5, 50, 500, 5000, vertical dashed guides at each.

Blue dashed contributions:
- 2nd-order zero at 5: from $0^\circ$ at $\omega = 0.5$ up to $+180^\circ$ at $\omega = 50$ ($90^\circ$ at 5);
- 2nd-order zero at 50: from $0^\circ$ at $\omega = 5$ up to $+180^\circ$ at $\omega = 500$ ($90^\circ$ at 50);
- simple pole at 500: from $0^\circ$ at $\omega = 50$ down to $-90^\circ$ at $\omega = 5000$ ($-45^\circ$ at 500).

Green total: constant at $90^\circ$ below 0.5; $0.5 \to 5$ rising, labeled "$+90^\circ$/dec." (reaches $180^\circ$ at 5); $5 \to 50$ rising, labeled "$+180^\circ$/dec." (reaches $360^\circ$ at 50); at $\omega = 50$ a vertical drop from $360^\circ$ back to $0^\circ$ (phase translated); $50 \to 500$ rising, labeled "$+45^\circ$/dec" (to $45^\circ$ at 500); $500 \to 5000$ falling, labeled "$-45^\circ$/dec" (to $0^\circ$ at 5000); flat at $0^\circ$ beyond.

**Additional key points:**

(i) often easier to construct magnitude plot starting from a limit (or point) for which $M(\omega) \to$ constant ($M(\infty)$ in this case). [continued on Page 4]

## Page 4

(Top: repeat of the line cut by the page break.)

(i) often easier to construct magnitude plot starting from a limit (or point) for which $M(\omega) \to$ constant ($M(\infty)$ in this case). Same applies to phase.

(ii) if phase plot extends outside the range $\phi \in [-360^\circ, +360^\circ]$, translate phase from $\pm 360^\circ$ to $0^\circ$.

**c)**
$$\mathbf H(\omega) = \frac{(8\times 10^{-2})(10 + j10\omega)}{j\omega(16 - \omega^2 + j4\omega)}$$

$$= \frac{\boxed{(8\times 10^{-2})(10)}\;(1 + j\omega)}{\boxed{(16)}\; j\omega\left(1 + j\frac{\omega}{4} + \left(\frac{j\omega}{4}\right)^2\right)}$$

(Constants in dashed box, brace: $= \frac{1}{20}$.)

simple zero at $\omega = 1$
simple pole at $\omega = 0$
quadratic pole at $\omega = 4$.

$M(0) = \infty$ $\qquad$ $M(\omega) \approx 20\log\frac{1}{20} = -26\ \text{dB}$ for $1 \le \omega \le 4$
$M(\infty) = 0 = -\infty\ \text{dB}$

$\phi(0) = -90^\circ$
$\phi(\infty) = \pm 180^\circ$

**Figure (Bode magnitude plot, part c, green):** Vertical axis $M(\omega)\,[\text{dB}]$ with $-26$ marked and a horizontal dashed line at $-26$ out to $\omega = 1$; horizontal axis $\omega$ with ticks 0.1, 0.4, 1, 4, 10, 40; vertical dashed guides at 1 and 4. Green curve: descends from upper left through the region near $\omega = 0.1$, labeled "$-20$ dB/dec", reaching $-26$ dB at $\omega = 1$; flat at $-26$ dB from 1 to 4; then descends steeply beyond 4, labeled "$-40$ dB/dec".

(Bottom of page: the magnitude plot continues; the phase plot for part (c) is on Page 5.)

## Page 5

(Top: tail of the part (c) magnitude curve from Page 4.)

**Figure (Bode phase plot, part c):** Vertical axis $\phi(\omega)$ with ticks $90^\circ$, $0^\circ$, $-90^\circ$ (label partly overwritten by the green curve), $-180^\circ$; horizontal axis $\omega$ with ticks 0.1, 0.4, 1, 4, 10, 40, vertical dashed guides at each.

Blue dashed contributions:
- simple zero at 1: from $0^\circ$ at $\omega = 0.1$ up to $+90^\circ$ at $\omega = 10$ ($45^\circ$ at 1);
- quadratic pole at 4: from $0^\circ$ at $\omega = 0.4$ down to $-180^\circ$ at $\omega = 40$ ($-90^\circ$ at 4).

Green total: starts flat at $-90^\circ$ below 0.1; $0.1 \to 0.4$ rising, labeled "$+45^\circ$/dec" (to $-60^\circ$ at 0.4); $0.4 \to 10$ falling, labeled "$-45^\circ$/dec" (three arrows point at this segment, with dots at $\omega = 1$ and $\omega = 4$); $10 \to 40$ falling more steeply, labeled "$-90^\circ$/dec"; flat beyond 40, labeled "$-180^\circ$".

**d)**
$$\mathbf H(\omega) = \frac{(4\times 10^4)\,\omega^2 (100 - \omega^2 + j50\omega)}{(5 + j5\omega)(200 + j2\omega)^3}$$

$$= \frac{\boxed{(4\times 10^4)(100)}\;\omega^2\left(1 + j\frac{\omega}{2} + \left(\frac{j\omega}{10}\right)^2\right)}{\boxed{(5)(200)^3}\;(1 + j\omega)\left(1 + \frac{j\omega}{100}\right)^3}$$

(Constants in dashed box, brace: $= \frac{1}{10}$.)

2nd order zero at $\omega = 0$
quadratic zero at $\omega = 10$
simple pole at $\omega = 1$
3rd order pole at $\omega = 100$.

$M(0) = 0 = -\infty\ \text{dB}$
$$M(\infty) = 20\log\left[\frac{1}{10}\left(\frac{1}{100}\right)100^3\right] = 60\ \text{dB}$$
$\phi(0) = 0^\circ$
$\phi(\infty) = \pm 180^\circ$.

Bottom of page: start of the magnitude plot for part (d), axis label $M(\omega)\,[\text{dB}]$, tick "60" with a horizontal dashed line at 60 and the green curve reaching the 60 level. Continued in full on Page 6.

## Page 6

**Figure (Bode magnitude plot, part d, green):** Vertical axis with ticks 60, 40, 20, 0, $-20$, $-40$, $-60$ (dB); horizontal dashed line at 60 dB. Horizontal axis $\omega$ with ticks 0.1, 1, 10, 100, 1000; vertical dashed guides at 1, 10, 100. Green curve: from $(\omega = 0.1,\ -60\ \text{dB})$ rising to $(1,\ -20)$, labeled "40 dB/dec."; from 1 to 10 rising to $(10,\ 0\ \text{dB})$, labeled "20 dB/dec"; from 10 to 100 rising steeply to $(100,\ 60\ \text{dB})$, labeled "60 dB/dec"; flat at 60 dB beyond 100.

**Figure (Bode phase plot, part d):** Vertical axis $\phi(\omega)$ with ticks $180^\circ$, $90^\circ$, $0^\circ$, $-90^\circ$, $-180^\circ$, $-270^\circ$; horizontal axis $\omega$ with ticks 0.1, 1, 10, 100, 1000, vertical dashed guides at each.

Blue dashed contributions:
- simple pole at 1: from $0^\circ$ at $\omega = 0.1$ down to $-90^\circ$ at $\omega = 10$;
- quadratic zero at 10: from $0^\circ$ at $\omega = 1$ up to $+180^\circ$ at $\omega = 100$;
- 3rd-order pole at 100: from $0^\circ$ at $\omega = 10$ down to $-270^\circ$ at $\omega = 1000$.

Green total: $0^\circ$ flat up to 0.1; $0.1 \to 1$ falling, labeled "$-45^\circ$/dec" (to $-45^\circ$); $1 \to 10$ rising, labeled "$+45^\circ$/dec." (back to $0^\circ$ at 10); $10 \to 100$ falling, labeled "$-45^\circ$/dec." (to $-45^\circ$ at 100); $100 \to 1000$ falling steeply, labeled "$-135^\circ$/dec." (to $-180^\circ$ at 1000); flat beyond 1000, labeled "$-180^\circ$".

(Rest of page blank.)

## Narration transcript

Okay, so this is Ulaby problem 9.19. This is a multi-part problem, and it consists of examples of generating Bode plots: Bode plots that are generated from transfer functions $\mathbf H(\omega)$. So this is a pretty long example, because it has so many parts. We'll just go through each of these one by one. What we'll want to do is to take a look at each of these transfer functions and then construct the Bode magnitude and phase plots, and we're going to use the straight-line approximation versions of these Bode plots for the four different transfer functions that are shown here.

### Part (a)

So we'll go ahead and get started with this. The first one of these is where the transfer function $\mathbf H(\omega)$ is equal to $4\times10^4$ times $(60 + j6\omega)$, divided by $(4 + j2\omega)$ times $(100 + j2\omega)$ times $(400 + j4\omega)$. The first thing that we would like to do here is to put this in the standard form that we have for the transfer function that allows us to more easily think about and generate the Bode plots. That means that for the zeros and the poles (remember, zeros are where the numerator goes to zero, poles are where the denominator goes to zero), and these are all simple zeros and poles, we want them to be of the form $1 + j\omega$ divided by whatever the zero or pole frequency is. If we do that for each of the zeros and poles that are in this expression, and we pull all of the necessary constants out to the front into an overall constant, then what we get is $4\times10^4$; that's the constant that was written up here. Then from this zero we pull out a factor of 60, and what we're left with is $1 + j\omega/10$. In the denominator, from this $4 + j2\omega$ we pull out a factor of 4, from the $100 + j2\omega$ we pull out a factor of 100, and from the $400 + j4\omega$ we pull out a factor of 400. What we have left for the simple pole factors is: from the first one it's $1 + j\omega/2$, from the second it's $1 + j\omega/50$, and from the third it's $1 + j\omega/100$. And then these constants out here, the ones that are contained in this dashed-line boundary here: if you multiply all these out, you get 15.

So now, if we look at the form of this transfer function, we can see that it has a simple zero at $\omega = 10$; that's from this factor here. And then we have simple poles at $\omega = 2$ from this first factor, $\omega = 50$ from the second factor, and $\omega = 100$ from the third factor. So we have simple poles at $\omega = 2, 50$, and 100. These will be helpful to us in identifying what are key frequencies in the Bode plots, and therefore in the behavior of whatever circuit or other linear system has this transfer function.

We also want to look at some of the limiting behaviors of the magnitude of the transfer function, which, remember, we called $M$, and the phase, which we called $\phi$. For the magnitude, we can see that at $\omega = 0$ each of these pole or zero factors here behaves basically as one, so the magnitude at zero goes towards a constant, which is just this constant in front, 15. We want to express that on the dB scale, so it's going to be $20\log_{10}15$, which is 23.5 dB. Then the magnitude at infinity: as $\omega$ goes to infinity, this transfer function ends up going as, we have one power of $\omega$ in the numerator and three powers in the denominator, so it ends up going as $1/\omega^2$. So the magnitude as $\omega$ approaches infinity is going to go to zero, or on the dB scale, it's $-\infty$ dB. So that is the magnitude.

What about the phase? When $\omega = 0$, these zero and pole factors basically go to one, and we have a positive constant out here, so the phase at $\omega = 0$ is just $0^\circ$. Then the phase as $\omega$ goes to infinity: in the numerator we have $j\omega$, in the denominator we basically have $(j\omega)^3$, so we're going to have $j/j^3$, which is $-1$, and the phase of $-1$ will be plus or minus $180^\circ$, depending on what the phase is as we approach infinity. We'll determine that as we generate the Bode phase plot.

So now, with this information, we can go ahead and start generating the Bode plots. We will first work on the Bode magnitude plot. We're going to plot the magnitude of the transfer function; this is going to be on the dB scale, and we have $\omega$ on the horizontal axis. We had three poles at 2, 50, and 100, and one zero at 10. So among the key points here, we'll indicate $\omega = 10$ and $\omega = 100$; then $\omega = 2$ would be somewhere like this, and 50 would be somewhere like that. These are going to be key frequencies in the Bode magnitude plot, so we'll try to align things here like this. At $\omega = 0$ the magnitude was 23.5 dB, so let's mark that on the vertical scale.

So what we have here is that if we are at frequencies below 2 (that's 2 radians per second), then all of these zero and pole factors over here behave essentially as one, so the magnitude is going to be constant at 23.5. We'll draw this in green here. So it's going to be at 23.5 all the way up to 2. Then from 2 to 10, the numerator and these two factors will still behave as one; this one is going to behave as $j\omega/2$. So overall, in the linear approximation, the magnitude is going to go as $1/\omega$, and so that will decrease at 20 dB per decade. So maybe something like this; this is $-20$ dB per decade as the slope. Then between 10 and 50, this factor here behaves as $\omega$, this factor here behaves as $\omega$, so in terms of the $\omega$ dependence they cancel each other out. These two behave as one, because we're still below $\omega = 50$, and so this basically goes as a constant. Then between 50 and 100, these two again cancel each other out, this behaves as one, this behaves as $\omega$, so we have essentially $1/\omega$, and so we're going to go something like this: again the slope is $-20$ dB per decade. And then finally, when $\omega$ is greater than 100, all these $\omega$-dependent factors, the zero and the poles, will behave basically as $\omega$, and so this will behave as $1/\omega^2$ in terms of the magnitude, and so we will have a sharper slope here, which is $-40$ dB per decade. So that is the magnitude plot.

Now let's look at the phase plot. The phase plot will be somewhat more complicated. We're going to extend these axes a little bit farther. This is now the phase that we're plotting, and this will be $0^\circ$; we'll say this will be $90^\circ$, this will be $-90^\circ$, this will be $-180^\circ$. Let's try to extend these here like this. And then we have: this is 10, this is 100, this over here is 1, and then this might be 0.1 here, and then say 1000 out here. We're going to need a number of other points here as well. So we have 2, because that corresponds to a pole at $\omega = 2$, and for the phase plot that means we're also going to need to mark that frequency divided by 10 and multiplied by 10. So we have 0.2 here and then 20 here. Then we had 10 as a zero, so we already have 1 and 100 marked. Then we had 50 as a pole; 50 was roughly here, so we're going to need to mark 5, and then 500. And then our final pole was at $\omega = 100$, and so we have 10 and 1000 marked here as well.

So now what we're going to do is just sketch out, and I'll sketch it in blue, what the behavior of the phase is for each zero or pole. For example, we had a simple zero at $\omega = 10$. Going back to the transfer function, that's this factor up here. We can see that the phase of this factor, when $\omega$ is very small, say less than one, less than one tenth times the zero frequency, then this behaves as one, so its phase is zero. When $\omega$ is very large, say 10 times the zero frequency or larger, so 100 or larger, then the phase is basically just given by this $j$, so it would be $90^\circ$. So for this simple zero, the phase undergoes a transition from 0 at $\omega = 1$ to $90^\circ$ at 100, and it's $45^\circ$ at the zero frequency itself. So I'll try to draw this approximately straight line like that. That is the phase associated with the simple zero at $\omega = 10$.

Now for the poles. Let's think about the pole at $\omega = 2$; that's this factor over here. When $\omega$ is much less than 2, say less than 0.2, then the contribution of the phase to $\mathbf H(\omega)$ is zero, because this just behaves as one. When $\omega$ is very large, much greater than 2, so say 20 or higher, then this looks like just $j\omega/2$ in the denominator, so that'll contribute a factor of $1/j$, or $-j$, to the phase, and the phase corresponding to a factor of $-j$ is $-90^\circ$. So for this simple pole at $\omega = 2$, we're going to go from a phase of 0 at 0.2 to a phase of $-90^\circ$ at 20, and it'll be $-45^\circ$ at the pole frequency, which is 2 itself. So now we'll try to draw a straight line here like this. And then we'll have the same thing as what we just drew for the poles at 50 and 100. For the simple pole at 50 we go from 0 phase at 5 to $-90^\circ$ at 500, and it's $-45^\circ$ at 50, so we're going to have something like this. And then finally for the pole at 100, we're going to go from 0 phase at 10 to $-90^\circ$ at 1000, and it'll be $-45^\circ$ at 100. So it'll look something like this. Anywhere where we have not drawn these blue dashed lines, the phase just continues as a constant at whatever the nearest point on the dashed lines is. So up here this would continue flat like that, this would continue as a constant like this, and so forth. I won't draw this because this is already going to be a very cluttered diagram.

So now what we want to do is to get the total phase, which I will draw in green. Basically we just want to add all of these up, and we'll be able to check at the end that as the frequency goes to zero, all the way on the left, the phase should be 0, and as the frequency goes to infinity, it should be plus or minus $180^\circ$. So if we now just add up all these different contributions to the phase, mostly the contributions will come from the portions of these curves where the phase has a nonzero slope with respect to frequency; that's why we only drew those sections.

For frequencies less than 0.2, we're going to have basically the zero-frequency behavior, so that's going to look like this (flat at 0). Then between 0.2 and 1, we're just going to have this, because the only thing that's contributing to a change in the phase is this simple pole at $\omega = 2$, so the slope over here is going to be $-45^\circ$ per decade, because that's the slope that we get in this linear approximation from a simple pole. Then for frequencies between 1 and 5, we have a $-45^\circ$ per decade slope here plus a $+45^\circ$ per decade slope here; those will cancel each other out, and we'll just have a constant phase. So this will be constant like this; it's $0^\circ$ per decade, in case it's not apparent from the picture. Then between 5 and 10, we have these three contributing to the slope: $+45$ per decade, $-45$ per decade, and $-45$ per decade. So that is again going to start going down at $-45$. That's a terrible line there; I'm trying to draw it like that. So this is now going at $-45^\circ$ per decade. Then from 10 to 20, now this one comes into play, from the pole at 100. So we have one $+45^\circ$ per decade and three $-45^\circ$ per decade, so this is going to go at $-90^\circ$ per decade; it'll be a steeper slope here, $-90^\circ$ per decade, up to 20. Then when we're beyond 20, this pole at $\omega = 2$ no longer contributes to the slope, because it's just constant. So we have one $+45^\circ$ per decade and two $-45^\circ$ per decade, and that will be the case from 20 to 100. So we're going to go at $-45^\circ$ per decade from 20 to 100; that'll look something like this. Then from 100 to 500, this (the zero) is now leveled off, so it doesn't contribute anything to the slope. We have these two poles over here that are each contributing $-45^\circ$ per decade to the slope, so that'll be a total of $-90^\circ$ per decade. I'll label this here $-90^\circ$ per decade, and maybe I'll draw a dot here between these transition points. And then from 500 to 1000, we will only have this one, the pole at $\omega = 100$, contributing to the slope. It's going to contribute $-45^\circ$ per decade, and that will end up bringing us down to $-180^\circ$. So here the slope is $-45^\circ$ per decade, and then the phase will just be constant at that value for higher frequencies.

So this sketch here is what the Bode phase plot looks like, and as we walked through it you can see how we constructed it by just taking into account the contributions of each individual simple zero or pole and then adding them together, and that got us this full plot over here.

### Key points (instructor retrospective, after part a)

So what are the key points in this first example of constructing a Bode plot? Basically, what we did was we wanted to write the transfer function (as specified in the problem, this is the voltage transfer function) in the standard form that was given in class, or that's described in Ulaby. By writing this in the standard form, so basically some overall constant in front and then various factors that are either zeros or poles, with the constant leading term being one, that makes it more straightforward to generate the Bode plots from that standard form of $\mathbf H(\omega)$.

Then the next thing that we did was, once we had $\mathbf H(\omega)$ in that standard form, we identified, and eventually in the plots we marked, all the poles and zeros that we found.

Then, to generate the magnitude plot, basically what we did was we noted that the way this simple linear, straight-line approximation works is that the transition from the limiting behavior corresponding to $\omega$ going to zero to the behavior corresponding to $\omega$ going to infinity, the transition from those two regimes of behavior, occurs exactly at each zero or pole. So it's an abrupt transition from the low-frequency limit to the high-frequency limit for each zero or pole at the zero or pole frequency. And then we saw that the effects of each pole or zero on the magnitude plot can be added directly to each other. That applies specifically when we're working on the dB scale, which is basically the common log of the transfer function, and those contributions are additive, because the contributors, the zeros and the poles and the constants, are factors in $\mathbf H(\omega)$, but when we take the log of some product, it's just the sum of the logs of the individual factors. So that's why these different contributions can just be added to each other in the magnitude plot on the dB scale. And then we also can check the limiting behavior of the magnitude at zero and infinite frequency. So that's for the magnitude plot.

Now for the phase plot, it was a little bit more complicated. In the phase plot, what we did was we marked, as we did in the magnitude plot, all the poles and zeros that we have in $\mathbf H(\omega)$. But then, in addition, we also marked the pole or zero frequency divided by 10, and 10 times the pole or zero frequency; we marked those points on the frequency axis, because those are significant points in the phase plots. And then what we said was that for each pole or zero, the $\omega$-going-to-zero, low-frequency-limit behavior occurred when the frequency is less than the pole or zero frequency divided by 10, and the high-frequency limiting behavior occurs when the frequency is greater than 10 times the pole or zero frequency, and we have just a linear transition in between. So for a simple zero or pole, we saw that the phase shift changed by $90^\circ$, plus or minus $90^\circ$ depending on whether it is a zero or a pole respectively, and so that meant that, since the transition occurs over two decades, it's half that amount, or plus or minus $45^\circ$ per decade; that's the slope. Then what we did was to sketch the phase for each zero or pole, then we added these together, and we really only were concerned with the regions of nonzero slope, since the phase will remain flat outside that region and won't contribute anything to the overall phase slope. And then again, we can check and confirm that we have the right limiting behavior for the phase at zero frequency and the phase at very high frequency. So that was basically the process that we went through in order to generate the Bode plots in that particular example.

### Part (b)

So now, keeping all this in mind, let's look at the next example, where the transfer function is $(1 + j0.2\omega)^2$ times $(100 + j2\omega)^2$, divided by $(j\omega)^3$ times $(500 + j\omega)$. So for this, the first thing that we want to do, as we did before, is to put this in standard form. Here we already have a leading one. Here we have a leading 100, so we want to pull that factor out, and it's 100 squared, because this is a second-order zero. So we have $100^2$. Then we have this factor here, $1 + j\omega\cdot0.2$, which is the same as $1 + j\omega/5$, and then from the second factor, the second-order zero, it's $1 + $, and when we pull out the two factors of 100, we get $(1 + j\omega/50)^2$. In the denominator, we don't have to pull anything out of this, and from this factor here we pull out a factor of 500. So we have 500 times $(j\omega)^3$ times $(1 + j\omega/500)$, and this constant out in front, which encompasses the $100^2$ over 500, is equal to 20.

So now let's look at the limiting behavior for the magnitude. At zero frequency, in the numerator these zero terms will just go to one, this simple pole in the denominator will go to one, but we also have this third-order pole at the origin, so this is going to go overall as basically $1/\omega^3$ as $\omega$ goes to zero, so that is going to become infinite. And then the magnitude at infinite frequency: in the numerator it's going to go as... sorry, this was a squared over here, because we had the square up here; I forgot to write that down. So in the numerator this is going to go as $\omega^4$; in the denominator this is also going to go as $\omega^4$. So this is just going to approach a constant, and that constant is going to be the following: if we go directly to the dB scale, it's going to be 20 times the log of whatever constant this whole thing approaches. It's going to have this leading factor here, which is 20, and then we're going to have $(1/5)^2$ from here, and then $(1/50)^2$ over here, and then down here we're going to have a $1/500$. So that becomes 20 times 500 ($1/(1/500)$ is just 500), and then in the denominator we have $5^2$ from over here, and then $50^2$ from here. If we multiply all this out, calculate the log and multiply by 20, we get that this is $-15.9$ dB. So that's the limiting behavior as the frequency goes to infinity: the magnitude of the transfer function approaches a constant, $-15.9$ dB on the dB scale.

The other thing that we want to note here is: what were the zeros and poles? If we look at this transfer function here, we can see that we have now second-order zeros at $\omega = 5$ and 50, so let's write that over here: second-order zeros at $\omega = 5$ and 50 radians per second. We have a third-order pole at $\omega = 0$, and then we have a simple pole at $\omega = 500$. So we want to keep all that in mind.

Now let's go and look at the phase. The phase at very low frequencies, as $\omega$ goes to zero: these factors in the numerator will just go to one, this will go to one here, and so we're going to have $1/(j\omega)^3$; in terms of the phase, that's basically a factor of $1/j^3$, or $1/(-j)$, which is just a factor of $j$. The phase of $j$ is $90^\circ$. And then finally, as the frequency goes to infinity, each of these zeros and poles, based on their $j$ and $\omega$ dependence, is going to go to $(j\omega)^4$ in the numerator and $(j\omega)^4$ in the denominator, so the $j$'s will cancel each other out, and the overall phase will be $0^\circ$ at very high frequency.

So now we can take all of this information and generate the Bode plots. Let's look first at the Bode plot for the magnitude. This is the magnitude of $\omega$ on a dB scale, and we'll draw the axis here. We have a third-order pole at the origin; we're not going to be able to draw the origin on the scale. But we also have second-order zeros at $\omega = 5$ and 50, and a simple pole at $\omega = 500$. So call this one 1, and then say we'll call this 5, 50, 500, and I'll draw a 5000 out here. This is $\omega$, and we'll draw maybe 0.5 here. So we want to mark 5, 50, and 500. And remember, as $\omega$ goes to infinity, the magnitude approaches $-15.9$ dB, so let's just draw that, say here, $-15.9$ on the dB scale.

So now we will draw the magnitude plot in green. At high frequency, which for our purposes for the magnitude plot means above 500, the magnitude is just going to be flat at $-15.9$ dB. Then if we are between 50 and 500, let's go back to the transfer function here. We're below 500, so this is going to behave as one, and then all of these will behave in the high-frequency limit, going as $j\omega$. So we have basically $\omega^4$ in the numerator, $\omega^3$ in the denominator; that's going to go as $\omega$, and it's going to be a 20 dB per decade slope. So that would look maybe something like this; the slope here is 20 dB per decade. Then between 5 and 50, now this is going to be in the low-frequency limit, these two are in the high-frequency limit. So we have $\omega^2$ over $\omega^3$; that's $1/\omega$, so the slope is going to be $-20$ dB per decade. That is going to look like this; this slope here is $-20$ dB per decade. And then finally, when we go below a frequency of 5 radians per second, all these factors here will be in the low-frequency limit, so they'll behave as one, and we just have $1/\omega^3$. $1/\omega^3$ is going to have a slope of $-60$ dB per decade, so that's going to look something like this; this slope here is $-60$ dB per decade. So this is what the Bode magnitude plot looks like. Basically the way that we arrived at it was: we started off where the magnitude is constant, and then in each frequency range where we know that the behavior will be different, because we're crossing some zero or pole frequency, we just figured out what the slope would be in each of those frequency ranges, and then we constructed the plot accordingly.

So now let's go ahead and try to generate the phase plot. We're going to draw the phase axis over here, so that's the phase, and let's draw the frequency axis like this. The axis will be at $0^\circ$, and then we'll have, say, $90^\circ$, $180^\circ$, $270^\circ$, $360^\circ$, and we'll go to $-90^\circ$ here. And then the frequencies that we're going to want to mark are 0.5, 5, 50, trying to line them up with the magnitude plot, 500, and then 5000. We'll draw some dashed lines so that we can keep track of these. I can see here that it would have been helpful if I had selected some background that is more like graph paper, if that's available. But anyway, we'll continue with this.

So now what we want to do is just figure out what the different contributions are from the zeros and the poles. At $\omega = 5$ we have a second-order zero; that's this term over here. So at a very low frequency, say $\omega$ less than 0.5, the phase of this will be zero, so it'll contribute zero phase to the transfer function. At very high frequency, that is, $\omega$ greater than, say, 50, which is 10 times 5, this term here will dominate; when we square it, we get $j^2$ or $-1$, and that'll be a phase of $180^\circ$. So what we will get then, from that one (we'll do these in blue), is a contribution that goes from 0 phase to $180^\circ$ between 0.5 and 50, and we'll be at the midpoint, $90^\circ$, in between. So that second-order zero will give us a contribution like this to the phase.

Then we also have a second-order zero at $\omega = 50$. By the same reasoning, for this factor here, the phase will go from 0 at frequencies below 50 over 10, so below 5, to 180 at frequencies of 10 times 50, or 500, and higher. So that's a zero at 50: we're going to go from 0 phase at 5 to $180^\circ$ at 500, and it'll be $90^\circ$ at the midpoint. So that'll be something like this.

And then we have this simple pole at $\omega = 500$. For a pole, we're going to go from a phase of 0 at $\omega$ less than 500 over 10, so less than 50, to a phase of... it'll be $90^\circ$, or $j$, in the denominator, so $-j$, or $-90^\circ$ overall contribution to $\mathbf H(\omega)$, at frequencies greater than 10 times 500, or 5000. So we'll go from 0 here to $-90$ here and $-45$ at the midpoint. Let me try to draw an approximately straight line here for the phase like that.

And then for the third-order pole at $\omega = 0$ [narration says "zero", meaning the $(j\omega)^3$ pole], that is this factor here. That phase is constant; it doesn't undergo a transition from low to high frequency. That's characteristic of a zero or a pole at the origin. We just have this overall factor of $j^3$ in the denominator, which is $-j$, and then it's just $j$ in the numerator, so that gives us an overall contribution of $90^\circ$ (that's the phase of $j$) to the phase of $\mathbf H(\omega)$. So that means that at very low frequency, that is, below 0.5, our starting phase will be $90^\circ$. So we have this here first; that's constant. Then as we go from 0.5 to 5, we have just this slope contributing, and it's a slope of $90^\circ$ per decade, so that's going to take us to here; this slope here is $+90^\circ$ per decade. Then between 5 and 50, we have these two phase factors that are each contributing a slope of $90^\circ$ per decade, so that's a total of $180^\circ$ per decade. That's going to take us to here, to 360. So here this slope is $180^\circ$ per decade. So now that's taking us to 360. When we get to 360, what we'll do is: 360 is equivalent to 0, so we'll just bring that back down to 0 here. And then we'll continue from there. Between 50 and 500 we have a slope of $+90^\circ$ per decade here and $-45^\circ$ per decade here, so that's going to be a slope of $45^\circ$ per decade. And then from 500 to 5000, we will have just this here, which is $-45^\circ$ per decade, so that's going to bring us back to zero. So this is $-45^\circ$ per decade. And then above 5000, the phase will just be constant at 0, and we see that, in fact, that is the correct limiting behavior that we deduced from $\mathbf H(\omega)$. So those are the Bode plots: up here for the magnitude, and down here for the phase.

### Additional key points (instructor retrospective, after part b)

So from this part of the problem, what were some additional key points? One is that when we constructed the magnitude plot, notice that we started over here at high frequency, and we did that because we knew that the magnitude was going to be constant there, and it's just easier to construct the plot starting from a known specific value. So the first point to note here is that it's often easier to construct the magnitude plot starting from a limit, or more generally a point, for which the magnitude goes to some constant that we know and can calculate. In this case it was the high-frequency limit. And the same applies to the phase.

Then the second additional point, beyond the points that we noted for part (a), is that we saw here the phase actually extended beyond $360^\circ$. If we go outside the range from $-360$ to $360$, then what we want to do is to bring the phase plot back to 0, because 0, 360 and $-360$ are all the same in terms of their trigonometric behavior. So if the phase extends outside the range from $-360^\circ$ to $360^\circ$, then what we will typically do is translate the phase from whichever of those extremes it was, plus or minus 360, to 0, and then go from there.

### Part (c)

So that's part (b) of this problem. Now we will go to part (c). I think parts (c) and (d) are a little bit shorter. Part (c): $\mathbf H(\omega)$ is equal to $8\times10^{-2}$ times $(10 + j10\omega)$, divided by $j\omega$ times $(16 - \omega^2 + j4\omega)$. Here again, we will put this into a standard form. We have our constant $8\times10^{-2}$. Then from this zero we will factor out a 10, and that'll leave us with $1 + j\omega$. In the denominator we will factor out a 16 from this quadratic pole here, so we have a factor of 16, and then that's times $1 + j\omega/4 + (j\omega/4)^2$. And these constant factors in front, if we multiply those in: we have $8\times10^{-2}$ times 10, that's 0.8; 0.8 over 16 is $1/20$.

So looking at this transfer function, we see that we have a simple zero at $\omega = 1$, and then we have a simple pole at $\omega = 0$, and then we have a quadratic pole at $\omega = 4$. So that's what we have for this transfer function.

Now let's look at the low- and high-frequency limiting behavior for the magnitude of the transfer function. At zero frequency, or very low frequency, the zero and the pole both behave as one, so we just have this $\omega$ in the denominator, so this is going to infinity. And then the magnitude at very high frequency, frequency approaching infinity, is going to go as $\omega/\omega^3$, so $1/\omega^2$, so that's going to go to zero, which is $-\infty$ on the decibel scale. So this does not really help us that much in terms of identifying a point or a range where the magnitude is constant, where we can figure out where the magnitude goes vertically on the Bode plot. However, if we look at the frequency range between 1 and 4, then this term, the zero, is going to be in the high-frequency range, so it's going to behave as $j\omega$; that cancels out with this $j\omega$ down here. Here, since $\omega$ is less than 4, this is going to be in the low-frequency limit, so it'll behave as just one. So for $\omega$ between 1 and 4, the transfer function will behave just as a constant, which, as we see here, is going to be $1/20$. So what we also see is that $M(\omega)$ is going to be, again in the linear approximation, approximately equal to $20\log_{10}(1/20)$, which is $-26$ dB, and we will have that behavior for $1 \le \omega \le 4$. So that will allow us to figure out where the magnitude plot goes on the vertical side.

Now we can look at the phase. The phase at very low frequency: these two factors here, the zero and the quadratic pole, are going to behave as one, and then we'll have this $1/j$ in the transfer function, so that has a phase of $-90^\circ$. And then finally, the phase at very high frequency, as the frequency goes to infinity: this will behave as $j\omega$, that'll cancel out with this $j\omega$, so we're going to have $(j\omega)^2$ over here as the dominant term. That is a factor of $-1$; it doesn't matter whether it's in the numerator or the denominator. So it's going to be plus or minus $180^\circ$. We'll see which of those it is when we construct the Bode phase plot.

So now, with this information in hand, we can go ahead and generate the Bode magnitude and phase plots. For the magnitude plot, we will draw the axes over here. This is the magnitude plot on the dB scale, and we'll draw the frequency axis here. We have a simple zero at $\omega = 1$ and a quadratic pole at $\omega = 4$. Since the frequency is also on a log scale, we're not going to be able to get zero on it. For the simple zero at $\omega = 1$, we're eventually going to want to have 0.1, 1, and 10. Then we have a quadratic pole at $\omega = 4$, so that would be maybe somewhere here, so then we're going to have 0.4, and then 40, something like that.

So now, for the magnitude plot, here the key points are $\omega = 1$ and $\omega = 4$, and we're going to have, say, $-26$ dB, because we know that for $\omega$ between 1 and 4, in the linear approximation, the magnitude $M(\omega)$ on the dB scale is going to be $-26$ dB. So that is here; I'll draw this to make it clear that those are aligned. Then when we are at frequencies above 4, that's basically in the high-frequency range: this is in the high-frequency range, so it'll go as $j\omega$, that'll cancel out with this, and we're going to go as $1/\omega^2$. So that is going to give us a slope of $-40$ dB per decade, so that's going to come down pretty steeply like this. And then for frequencies less than 1, this will behave as one, this will behave as one, and so we're just going to have a $1/(j\omega)$. So that is going to have a slope of $-20$ dB per decade. One decade is 1 to 0.1, and we'll say that's maybe here, and then we just continue that. So the slope here is $-20$ dB per decade. So that is the Bode magnitude plot.

So now we want to generate the Bode phase plot. This is the phase, and we draw the axes here. We're going to mark 0.1, 0.4, 1, 4, 10, and 40 on the frequency axis, and then we'll mark $90^\circ$, this is 0, and then we'll have $-90^\circ$ and $-180^\circ$. And so now we will mark all of these. Then what we're going to do here, as we've done in the previous two parts, is sketch out the contribution to the phase from each one of the zeros and poles, and then we'll just add them together.

We have a simple zero at $\omega = 1$; that's this factor over here. So it undergoes a transition from, at low frequency, say $\omega$ less than 0.1, a phase of 0, since this factor just behaves as one, to, at high frequency, say $\omega$ greater than 10 times 1, or 10, a phase of $90^\circ$. So we're going to go from 0 at 0.1 to $90^\circ$ at 10, with 45 in the middle. Then we have a quadratic pole at $\omega = 4$ [narration says "quadratic zero"; the page and the sketch treat it as the pole], and so that is going to go from a phase of 0 at a very low frequency, say $\omega$ less than 0.4, which is 4 over 10, to a phase of $-180^\circ$ at frequencies above 10 times 4, or 40. So we're going to go from 0 at 0.4 to $-180$ at 40, and it'll be $-90^\circ$ at 4. We know that it goes to $-180$ because at $\omega = 4$ this $(j\omega/4)^2$ becomes $-1$, that cancels out with this one, and so all we have left is the $j$ over here, and its phase is $90^\circ$, or $-90^\circ$ because it's in the denominator. So we know that this is at $-90$, and so at 40 it has to be $-180$. So let me draw this dashed line.

So now we have one more thing: at low frequency, below 0.1, the phase is $-90^\circ$, so that's where we will start. So at $-90^\circ$ below 0.1, basically like this. Then from 0.1 to 0.4, we have only this contributing, so that's $+45^\circ$ per decade; that's going to be something like this. So this is $+45^\circ$ per decade. And then from 0.4 to 10, we have $+45^\circ$ per decade and $-90^\circ$ per decade, so that is $-45^\circ$ per decade, so that will bring us back to here. And then from 1 to 10 it's another 45 degrees, so maybe to back to here. So we'll continue that line, and then out here from 10 to 40, it's going to be just $-90^\circ$ per decade as the slope, so something like this. So here this is $-45^\circ$ per decade; here it is $-90^\circ$ per decade. And then once we're above 40, it should continue; it's just constant at $-180^\circ$. And so that's what we have over here.

So that is part (c), and I think there aren't really any additional key points that are important to note here. It was quite similar to what we did in the previous two parts, except this time we have a quadratic pole right here, and so we just had to think a little bit more about what the limiting behaviors of that would be, how the phase changes, and so forth, using the ideas that we highlighted in the first two parts.

### Part (d)

So now we are finally on part (d), which is the last part of this problem. Here the transfer function is $4\times10^4$ times $\omega^2$ times $(100 - \omega^2 + j50\omega)$, divided by $(5 + j5\omega)$ times $(200 + j2\omega)^3$. So again we want to take this and just put it in the standard form. We have the constant $4\times10^4$. Then we're going to factor out a 100 from here, from the quadratic zero, so we have a factor of 100; then we have $\omega^2$, and then $1 + j\omega/2$ (that's from the $j50\omega$) $+ (j\omega/10)^2$. And then in the denominator, we'll factor out a 5 from this first pole, and then we'll factor out a $200^3$ from this third-order pole over here, and then what we have left will be $(1 + j\omega)$ and then $(1 + j\omega/100)^3$. So this is now in the standard form, and this collection of constants out in front, if we calculate that out, turns out to be $1/10$.

So if we look at this, what we have here is: we have this $\omega^2$ in the numerator, so we have a second-order zero at $\omega = 0$. Then we have this factor here, which is a quadratic zero at $\omega = 10$. Then we have here a simple pole at $\omega = 1$. And then finally, here we have a third-order pole at $\omega = 100$. So those are the poles and zeros.

Then if we look at the limiting behavior of the magnitude: the magnitude at very low frequency, these factors here go as one, this is $\omega^2$, so this will go to zero, which is, remember, $-\infty$ dB. Then the magnitude at very high frequency, as $\omega$ goes to infinity: this numerator is going to go as $\omega^4$; the denominator will go as $\omega^4$ as well. So what we're going to have here is that the magnitude goes as 20 times the log [narration says "natural log", corrects to common log below] of: we're going to have $1/10$, and then from this factor over here we're going to have $1/100$, $1/10^2$, and then from this down here we're going to have $100^3$. If we multiply all this out, this is $10^6$ divided by $10^3$, so this is going to be $10^3$ over here; we take the common log of that, that's 3, and we have 3 times 20, that is 60 dB.

And then for the phase: the phase at 0 is, these are all one, this goes as $\omega^2$, this is positive, so the phase at 0 is $0^\circ$. And then the phase at very high frequency, as the frequency goes to infinity, is going to be: we have $j^2$ over here, which is $-1$, and then we have $j^4$ in the denominator, which is just 1. So we have an overall minus sign in the transfer function, and so that's going to have a phase of plus or minus $180^\circ$.

So now this is what we need in order to construct the Bode plots. As usual, we will construct the magnitude plot first. This is on the dB scale, and our starting point is going to be 60. Let's draw our frequency axis here. The key points on the frequency axis are: we have a simple pole at $\omega = 1$, a quadratic zero at $\omega = 10$, and a third-order pole at $\omega = 100$. So we're going to want to go from, say, 0.1, make this 1, 10, 100, make this 1000. So that's $\omega$. Then we're going to start off at very high frequency; this is going to be at 60, and so we'll mark these points here. Our poles and zeros are at 1, 10, and 100.

So now, at very high frequency, the magnitude is 60. So that's going to be, say, up here, and we'll draw this dashed line here to show that these are aligned. Then when we're between $\omega = 100$ and $\omega = 10$, we're below $\omega = 100$, so this factor just becomes one. This is $\omega^2$, this is $\omega^2$, so that's $\omega^4$ in the numerator; this is $\omega$ in the denominator, so that is $\omega^3$. So this is going to have a positive slope of 60 dB per decade. For one decade, that'll be like this; this is 60 dB per decade. Then for $\omega$ between 1 and 10, this is going to be in the low-frequency regime, so this will be one, this will be one here, and so we'll just have $\omega^2/\omega$, so that's going to go as $\omega$, which is $+20$ dB per decade. So this is 20 dB per decade. And then below that, this goes to one, these are also behaving in the low-frequency limit, so we'll take those as one, so we just go as $\omega^2$, which has a slope of 40 dB per decade. So at 0.1 that'll be $-60$, and so the slope will look something like this. So this is a slope of 40 dB per decade. So this is the magnitude Bode plot.

And so now we want to do the phase plot. This will be the phase, and let's draw the axes here. We have 0.1, 1, 10, 100, and 1000, and we'll mark all of these on the phase line. And then for the actual phases, we'll take this to be 0, so the axis is at 0, and we'll go to $90^\circ$, $180^\circ$, $-90^\circ$, $-180^\circ$, $-270^\circ$.

So now we'll go back to our zeros and poles. The zero at $\omega = 0$, that's just the $\omega^2$: that doesn't contribute any change to the phase, and it contributes the constant of 0 to the phase, so we don't have to really worry about that as far as the phase plot is concerned. Then, for the simple pole at $\omega = 1$, we go from a phase of 0 for $\omega$ less than 1 over 10, less than 0.1, to a phase of $-90^\circ$ at $\omega = 10$. As usual, we'll draw that in blue. So from 0.1 at 0 to 10 at $-90$, and it's at $-45$ at $\omega = 1$; that's going to look like this. Then at $\omega = 10$ we have the quadratic zero up here, so that's going to go from a phase of 0 at $\omega \le 1$ to a phase of $180^\circ$, so just a factor of $-1$, at $\omega \ge 100$. So we're going to go from 0 to $180^\circ$ at 100, and $90^\circ$ at 10. So that looks like this. And then finally, we have the third-order pole in the denominator, from this factor in the denominator over here. This is going to go from a phase of 0 at $\omega = 10$ to a phase of $-270^\circ$ (that's $j^3$ in the denominator) at $\omega = 1000$. So we're going to go from $0^\circ$ here to $-270$ at 1000, and then it'll be halfway at $\omega = 100$. So that's going to be something like this.

And then for the overall phase plot, we just add these together, noting that in the low-frequency limit the phase is 0. So we have a phase of 0 up to 0.1. Then from 0.1 to 1 we have only this contributing; that's a slope of $-45^\circ$ per decade; it's going to go like this. So that's $-45^\circ$ per decade. Then from 1 to 10, we have $-45^\circ$ per decade from here and $+90^\circ$ per decade from here, so that's $+45^\circ$ per decade overall, so that's going to bring us up like this; this is $+45^\circ$ per decade. Then from 10 to 100 we have $+90^\circ$ per decade, $-135^\circ$ per decade, so that's going to be $-45^\circ$ per decade; so that'll bring us to $-45$ here. So this is $-45^\circ$ per decade. And then finally, from 100 to 1000, we have just $-135^\circ$ per decade from this third-order pole here, so that's going to bring us down to $-180$. So that'll be like this; this is $-135^\circ$ per decade. And then for $\omega$ greater than 1000, this will be flat at $-180^\circ$. And that is the entire Bode phase plot.

### Key points (instructor retrospective, closing)

And again, we basically constructed both of these plots using the same ideas and key points that we had highlighted in the earlier parts of this problem. So that is this entire example, which hopefully gives you a very good idea of how to construct Bode plots from transfer functions and how to think about and understand them. Okay, so while [recording ends mid-sentence].

## Index terms

Ulaby 9.19, Problem 9.19, Bode plot, Bode magnitude plot, Bode phase plot, straight-line approximation, voltage transfer function, $\mathbf H(\omega)$, standard form, $1 + j\omega/\omega_z$, $1 + j\omega/\omega_p$, overall constant, simple zero, simple pole, second-order zero, third-order pole, pole at origin, zero at origin, $(j\omega)^3$, quadratic pole, quadratic zero, $1 + j\omega/\omega_0 + (j\omega/\omega_0)^2$, $M(\omega)$ in dB, $20\log_{10}$, $M(0)$, $M(\infty)$, $\phi(0)$, $\phi(\infty)$, $\pm 180^\circ$, 23.5 dB, $-15.9$ dB, $-26$ dB, 60 dB, $-20$ dB/dec, $-40$ dB/dec, $-60$ dB/dec, 20 dB/dec, 40 dB/dec, 60 dB/dec, $\pm 45^\circ$/dec, $\pm 90^\circ$/dec, $180^\circ$/dec, $-135^\circ$/dec, $\omega_{p,z}/10$, $10\omega_{p,z}$, two-decade phase transition, $\log[ab] = \log a + \log b$, dB scale additivity, limiting behavior, phase wrapping, translate $\pm 360^\circ$ to $0^\circ$, start magnitude plot from constant limit, constant-magnitude frequency range, phase of $j$, phase of $-j$, phase of $-1$, $1/j^3 = j$, poles at 2 50 100, zero at 10, zeros at 5 50, pole at 500, zero at 1, pole at 4, zero at 10 (quadratic), pole at 1, pole at 100 (third order), key points, additional key points, Prof. Ed Yu, Chapter 9
