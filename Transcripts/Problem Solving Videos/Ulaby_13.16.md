---
course: ECE 411H
kind: problem-video
source: Problem Solving Videos/Ulaby 13.16.pdf
source_pages: 4
author: Prof. Ed Yu
unit: final
topics: [fourier-series, fourier-coefficients, sawtooth-wave, even-odd-symmetry, integration-by-parts, time-scaling, amplitude-scaling, dc-offset, ulaby-13.16]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
deepgram_transcript: deepgram/Ulaby_13.16.deepgram.txt
deepgram_paragraphs: deepgram/Ulaby_13.16.deepgram.md
---

# Ulaby 13.16 — Fourier series of a sawtooth; deducing the series of a scaled/shifted sawtooth

**Summary.** Problem-solving video for Ulaby/Maharbiz/Furse Problem 13.16. The textbook gives the Fourier series of a 4-second-period sawtooth $f_1(t)$ (rising linearly 0 to 20 each period) and asks for the Fourier series of $f_2(t)$, an 8-second-period sawtooth ranging from $-20$ to $+20$. Prof. Yu first computes the series of $f_1(t)$ from scratch (trigonometric form: $a_0 = 10$, $a_n = 0$ by odd/even symmetry after a 2-s time shift, $b_n = -20/(\pi n)$ by integration by parts), confirming the book's expression. He then recognizes $f_2(t) = 2 f_1(\tfrac{1}{2}t) - 20$ and substitutes to get $f_2(t) = -\frac{40}{\pi}\sum_{n=1}^{\infty}\frac{1}{n}\sin(\frac{\pi n}{4}t)$. Exam-relevant lessons: $a_0$ is the average over a period; odd functions have zero cosine coefficients and even functions zero sine coefficients; integrals of a sinusoid over an integer number of periods vanish; scaling and shifting a known waveform maps directly onto its series.

> **Audio transcript (Deepgram nova-3, ECE 411 keyterms, timestamped):** `deepgram/Ulaby_13.16.deepgram.txt` ; paragraph form: `deepgram/Ulaby_13.16.deepgram.md`. Fresh ASR of the video audio; where it disagrees with the Narration section (built from the published auto-captions), prefer this file and the handwritten page.

## Problem statement

(Printed textbook excerpt pasted on page 1.)

*13.16 The Fourier series of the periodic waveform shown in Fig. P13.16(a) is given by

$$f_1(t) = 10 - \frac{20}{\pi}\sum_{n=1}^{\infty}\frac{1}{n}\sin\!\left(\frac{n\pi t}{2}\right).$$

Determine the Fourier series of waveform $f_2(t)$ in Fig. P13.16(b).

**Figure P13.16: Waveforms for Problem 13.16.**

- **Figure (a) $f_1(t)$:** sawtooth versus $t$ (s). Horizontal axis marked $-4, 0, 4, 8$; vertical axis marked 20. In each period of 4 s the waveform rises linearly from 0 (at $t = -4, 0, 4, 8$) to 20 (just before $t = 0, 4, 8$) and then drops vertically back to 0. Shown from $t=-4$ to $t=8$ (three teeth).
- **Figure (b) $f_2(t)$:** sawtooth versus $t$ (s). Horizontal axis marked $-4, 0, 4, 8$; vertical axis marked $20$ and $-20$, with 0 at the origin. The drawn ramp starts at $(-4, 0)$, rises linearly to $20$ at $t = 0$, drops vertically to $-20$, rises linearly through $0$ at $t = 4$ to $20$ at $t = 8$, then drops vertically to $-20$ again. Net: period 8 s, each period a linear ramp from $-20$ to $+20$, zero average.

## Page 1

Header: Ulaby 13.16

(Printed problem statement and Figure P13.16 pasted at upper left, as transcribed above.)

Handwritten at upper right:

**Example:** calculation of Fourier series coefficients.

For $f_1(t)$, we have the analytical expression

$$f_1(t) = 5(t - nT), \qquad nT \le t \le (n+1)T,\ T = 4\ \text{s},\ n \in \mathbb{Z}.$$

Although not required, let's compute its Fourier series:

$$f_1(t) = a_0 + \sum_{n=1}^{\infty}\big(a_n\cos(n\omega_0 t) + b_n\sin(n\omega_0 t)\big), \qquad \omega_0 = \frac{2\pi}{T}$$

$$a_0 = \frac{1}{T}\int_0^T f_1(t)\,dt = \frac{5}{4}\int_0^4 t\,dt = \frac{5}{4}\left[\frac{t^2}{2}\right]_0^4 = \frac{5}{4}\left(\frac{16}{2}\right) = 10.$$

Note that $a_0$ is simply the average value of $f_1(t)$ over one period $T$.

(The last line of the page is cut off by the page break; it is the top of the line "period $T$." continued on page 2.)

## Page 2

period $T$.

$$a_n = \frac{2}{T}\int_0^T f_1(t)\cos(n\omega_0 t)\,dt$$

$$= \frac{2}{4}\int_0^4 5t\cos\!\left(\frac{2\pi n}{4}t\right)dt = \frac{5}{2}\int_0^4 t\cos\!\left(\frac{\pi n}{2}t\right)dt;$$

(margin note:) shift by 2 s in time, $\tau = t - 2$, i.e., $t = \tau + 2$

$$= \frac{5}{2}\int_{-2}^{2}(\tau+2)\cos\!\left[\frac{\pi n}{2}(\tau+2)\right]d\tau = \frac{5}{2}\int_{-2}^{2}(\tau+2)\cos\!\left(\frac{\pi n}{2}\tau + \pi n\right)d\tau$$

$$= \frac{5}{2}\left[\int_{-2}^{2}\tau\cos\!\left(\frac{\pi n}{2}\tau + \pi n\right)d\tau + 2\int_{-2}^{2}\cos\!\left(\frac{\pi n}{2}\tau + \pi n\right)d\tau\right]$$

(annotations: in the first integral, $\tau$ is marked "odd" and the cosine is marked "even"; a brace under the first integral reads "$=0$"; a brace under the second integral reads "$=0$")

$$= 0$$

Note that we could also deduce $a_n = 0\ \forall n \ne 0$ since $f_1(t) - 10$ is obviously an odd function, and $\cos(n\omega_0 t)$ is an even function $\forall n \ne 0$ (and for $n = 0$).

$$b_n = \frac{2}{T}\int_0^T f_1(t)\sin(n\omega_0 t)\,dt$$

$$= \frac{2}{4}\int_0^4 5t\sin\!\left(\frac{2\pi n}{4}t\right)dt$$

$$= \frac{5}{2}\int_0^4 t\sin\!\left(\frac{\pi n}{2}t\right)dt;$$

(side note, integration by parts:) $\int u\,dv = uv - \int v\,du$; $u = t$, $dv = \sin\!\left(\frac{\pi n}{2}t\right)dt$; $du = dt$, $v = -\left(\frac{2}{\pi n}\right)\cos\!\left(\frac{\pi n}{2}t\right)$

$$= \frac{5}{2}\left\{\left[-\left(\frac{2}{\pi n}\right)t\cos\!\left(\frac{\pi n}{2}t\right)\right]_0^4 + \left(\frac{2}{\pi n}\right)\underbrace{\int_0^4\cos\!\left(\frac{\pi n}{2}t\right)dt}_{=0}\right\}$$

$$= \frac{5}{\cancel{2}}\left[-\left(\frac{\cancel{2}}{\pi n}\right)4\right] = -\frac{20}{\pi n}$$

(The 2 in the $\frac{5}{2}$ and the 2 in $\frac{2}{\pi n}$ are struck through to show they cancel.)

## Page 3

(Top of page: the bottom fragment of the previous line, "$\frac{5}{2}\left[-\left(\frac{2}{\pi n}\right)4\right] = -\frac{20}{\pi n}$", cut off by the page break.)

$$\Rightarrow\ f_1(t) = 10 - \frac{20}{\pi}\sum_{n=1}^{\infty}\frac{1}{n}\sin\!\left(\frac{\pi n}{2}t\right) \qquad \checkmark$$

From the plots of $f_1(t)$ and $f_2(t)$, we can see that

$$f_2(t) = 2 f_1\!\left(\tfrac{1}{2}t\right) - 20$$

$$\Rightarrow\ f_2(t) = \cancel{20} - \frac{40}{\pi}\sum_{n=1}^{\infty}\frac{1}{n}\sin\!\left(\frac{\pi n}{4}t\right) \cancel{- 20}, \ \text{or}$$

(the $20$ and the $-20$ are struck through in green to show they cancel)

$$\boxed{f_2(t) = -\frac{40}{\pi}\sum_{n=1}^{\infty}\frac{1}{n}\sin\!\left(\frac{\pi n}{4}t\right)}$$

**Key Points:**

(i) calculation of Fourier series expansion for $f_1(t)$ involved straightforward integrals, and certain coefficients can be seen to be zero by symmetry arguments.

(ii) given Fourier series for $f_1(t)$, computing Fourier series for $f_2(t)$ was relatively easy — needed to recognize how $f_1(t)$ could be transformed into $f_2(t)$ by a scaling by 2×, doubling of the period, a vertical shift.

## Page 4

(Only the last line of the key points carries over, cut off at the page break:) a vertical shift.

The rest of the page is blank.

## Narration transcript

Okay, so this is Ulaby problem 13.16. And this is an example of how we calculate Fourier series coefficients. So this is an example of the calculation of Fourier series coefficients.

Okay? And in this problem here we have two different waveforms, all right, shown in these images here. And the problem statement gives us the form of the Fourier series expansion for $f_1(t)$, this one here, and it asks us, down a little bit, okay, it asks us, knowing the Fourier series expansion of this function here, to deduce what the Fourier series expansion is for this function down here. So what we'll do in this example is, instead of just taking this Fourier series expansion as a given, we'll actually look at this function and we'll calculate this. And then, once we've done that, we'll see how this Fourier series expansion for $f_1$ can be used fairly straightforwardly to deduce what the Fourier series expansion is for this function $f_2$ over here. Okay. So let's go ahead and get started.

If we look at this graph of $f_1$, then we can deduce pretty easily what the corresponding analytical expression for this is, because the period of this is 4 s, and in each period $f_1(t)$ increases linearly with time from 0 to 20, and then it just repeats that every 4 s. Okay, so from that, what we can deduce is the following, okay? So for $f_1(t)$, all right, we have the following analytical expression, okay, which will be useful to us in explicitly computing the Fourier series coefficients for $f_1$. All right. So we can see pretty easily that $f_1(t)$ is equal to 5 times the quantity $t$ minus $n$ times capital $T$, and that's valid in the interval from $nT$ to $(n+1)T$, where capital $T$, the period, is 4 s, and $n$ is any integer.

Okay, so what we want to do now is to use this analytical expression to compute the Fourier series expansion for $f_1$. All right. So, although it's not required for this problem, okay, so even though it's not required, I think it's still instructive for the purposes of this example to do it. So let's go ahead and compute the Fourier series, okay, the Fourier series expansion for this function $f_1$.

So remember the general form of the Fourier series expansion is that we can take $f_1(t)$ to be equal to some constant $a_0$, all right, and that's basically just the average value of $f_1(t)$ over one period, plus a sum of terms for $n$ going from one to infinity, where we take a superposition of sine and cosine functions, so it's the coefficient $a_n$ times the cosine of $n\omega_0 t$ plus another coefficient $b_n$ times the sine of $n$ times $\omega_0 t$. All right! Where $\omega_0$ is the fundamental frequency associated with one period. So $\omega_0$ is $2\pi$ over $T$. And of course, what the Fourier series expression tells us is that we can take any periodic function and express it as a superposition of sine and cosine functions at frequencies that are integer multiples of the fundamental frequency associated with a single period of that function. Another way of saying that, using more of the language of linear algebra, is that we can take the sine and cosine functions at those frequencies to be a basis set for expressing any periodic function. Okay, and so what we want to do now is to calculate these coefficients $a_0$, $a_n$ and $b_n$. All right.

So let's start with $a_0$. All right, so you may recall from class that we can compute $a_0$ by taking the average of $f_1(t)$ over one period, so it's one over $T$ times the integral from 0 to $T$ (this is capital $T$ here) of $f_1(t)\,dt$, right? So hopefully you can see pretty clearly this is just taking the average of $f_1$ over one period. So $f_1(t)$, right, for the interval 0 to $T$ is just 5 times $t$. So this is going to be 5, and then capital $T$ is equal to 4, so it's five fourths times the integral from 0 to 4 of $t\,dt$. All right. So this is a very easy integral to do. So this is five fourths times $t^2/2$ evaluated at 0 and 4, right. So it's five fourths times, and then evaluated for $t^2$ is 16 over 2; evaluated at 0 it's just 0. Okay. And then we can calculate this quite easily. So we have 20 over 2, which is just 10. All right, so $a_0$ is 10. All right. And, in fact, if you look back at the graph of the function $f_1$, right, just essentially by looking at it and thinking about it a little bit, we can see pretty easily that the average of $f_1$ over one period is 10, right? Because this is a linear function that goes from 0 to 20, so its average should be the midpoint, which is 10. Okay? So we can make a little note here in our thinking about this, that $a_0$, the constant coefficient of the Fourier series expansion, is really just the average value of $f_1(t)$ over one period, capital $T$. All right, so we calculated it explicitly here, but one can deduce that in other ways in many cases, all right, and any correct way will be valid and will give the correct answer.

Okay, so now let's go ahead and try to calculate the coefficients $a_n$. All right, so in general the coefficient $a_n$ is equal to 2 over $T$ times the integral from 0 to $T$ of $f_1(t)$ times the cosine of $n$ times $\omega_0 t$, $dt$. Okay. So we arrived at this result in class. Right now we'll see an example of the calculation of this coefficient. All right, and again using the language of linear algebra, another way of thinking about this expression is to recognize that if we take the sine and cosine functions at these different frequencies to be our basis elements for expressing $f_1(t)$, then we're getting the coefficient for this particular basis element, cosine of $n\omega_0 t$, by taking the projection, which in this case is the integral, of $f_1(t)$ onto this basis function. So it is analogous, if you think just about vectors, say, in three dimensions, to taking the dot product of some vector with one of the basis elements. All right. But this is a more general way of implementing that concept.

Okay, so let's go ahead and try to calculate this now. All right, so remember capital $T$ is 4 s. So we have 2 over 4 in front of the integral, then we have the integral from 0 to 4, and then $f_1(t)$ over that interval is just 5 times $t$, and then we have the cosine of — remember $\omega_0$ is $2\pi$ over $T$, so $2\pi$ over 4 — so this is $2\pi n$ over 4 times $t$, $dt$. All right. So now, if we multiply out these coefficients in front, 2 over 4 is one half, and then we pull the 5 out of the integral. So we have five halves times the integral from 0 to 4 of $t$ times the cosine, and then the argument of the cosine we can simplify to $\pi$ times $n$ over 2 times $t$, $dt$. All right, so now there are a variety of ways that we could compute this integral. All right, here we will do it fairly explicitly, all right, and the way that we will do it is to shift it by 2 s in time. Right. So we want to shift by 2 s in time, or equivalently, we want to do a change of variables. We'll call our new variable tau, right, the Greek letter tau, and we'll take that to be $t - 2$, or equivalently $t$ is equal to $\tau + 2$. Okay. So now, if we change our variable of integration from $t$ to $\tau$, then we get five halves times the integral now from $\tau$ going from $-2$ to 2, all right, instead of $t$ going from 0 to 4, and then we have $t$, which is just $\tau + 2$, times the cosine of $\pi n$ over 2 times $t$, which is again $\tau + 2$, $d\tau$. All right. Okay. And we can write that, just simplifying it a little bit, as five halves times the integral from $-2$ to 2 of $\tau + 2$ times the cosine of, and then we'll just multiply this out, $\pi n$ over 2 times $\tau$ plus $\pi$ times $n$, $d\tau$. All right, and so now we will multiply out this $\tau + 2$ times the cosine, and we'll separate this out into two separate integrals after doing that. So we're going to have the five halves out in front, and then from the first term we would have the integral from $-2$ to 2 of just $\tau$ times the cosine of $\pi n$ over 2 times $\tau$ plus $\pi n$, $d\tau$. And then the second term will be 2 times the integral from $-2$ to 2 of now just the cosine of $\pi n$ over 2 times $\tau$ plus $\pi n$, again $d\tau$.

All right. So now we have these two integrals, and if we look at them we can see that the second integral is clearly equal to 0, because what we're doing is we're integrating the cosine function over some integer number of periods, all right, with a phase shift, but the phase shift doesn't matter, right, and the number of periods over which we are integrating is just equal to $n$, right, which is always an integer. So that integral is always zero. All right. What about the first integral over here? Well, we're integrating from $-2$ to 2. Now $\tau$ is an odd function, right? The cosine is an even function. So an odd function times an even function is an odd function. And when we integrate an odd function over an interval that's centered at 0, which this is, then that integral is going to be equal to 0 as well. All right. So what we have finally, then, is that all the coefficients $a_n$ are equal to 0.

Okay. Now, could we have figured this out some other way? Well, let's go back here and look at $f_1(t)$. All right. So if we take $f_1(t)$ and shift it down by 10, right, by its average value, right, then, once we do that, we can see that $f_1(t)$ shifted down by 10, so $f_1(t) - 10$, is going to be an odd function. All right! So if we go from $t$ to $-t$, then $f_1(t) - 10$ changes sign, okay? So it's an odd function, and in our expansion here the coefficients $a_n$ are for the cosine functions, and the cosine is an even function. All right, so the projection of an odd function onto an even function is always going to be 0. All right, and we see that here explicitly, having calculated this integral here, which is that projection. Okay? So in general, if we have some odd function, right, for which we are trying to compute the Fourier series expansion, all right, then the coefficients of the cosine terms are always going to be 0, okay, because an odd function will have no even function components. Similarly, if we have an even function for which we are trying to compute the Fourier series expansion, that even function will have zero coefficients for the sine terms, right? Because the sine is an odd function. All right. And so that's a useful property, all right, for Fourier series expansions to keep in mind. Here we saw it explicitly by actually computing the coefficients for the cosine.

So we should note here, all right, then, we could also deduce that all the $a_n$'s will be equal to 0 for all $n$ not equal to 0, right. For $n$ equal to 0 it's different because $f_1(t)$ has a nonzero average value, right, and $a_0$ is the average value over one period. So this is zero, right, all these other coefficients are 0, because $f_1(t) - 10$, right, so that is shifted by its average value, right, this is obviously an odd function. All right. We can see that from the plot. All right! Whereas the cosine of $n\omega_0 t$, all right, is an even function, all right, and it's even for all values of $n$ not equal to 0, right, which are the ones that are relevant for computing these $a_n$'s with $n$ not equal to 0. All right, and then also the cosine is also an even function for $n$ equal to 0 as well, although that doesn't come into play explicitly for the $a_n$'s where $n$ is not equal to 0.

Okay, so those are the coefficients for the cosine terms in the expansion. They're all 0. All right! What about the coefficients for the sine terms, $b_n$? These, as we saw in class, all right, could be computed as 2 over $T$ times the integral from 0 to $T$ of $f_1(t)$ times the sine of $n\omega_0 t$, $dt$. All right, and so if we just plug in capital $T$ and $f_1(t)$, we get 2 over 4, right, because capital $T$ is 4, times the integral from 0 to 4 of $5t$, all right, that's $f_1(t)$, times the sine of $2\pi n$ over 4, all right, $\omega_0$ is $2\pi$ over capital $T$, so it's $2\pi$ over 4 times $n$ times $t$, $dt$. All right, and we can write that as, again, five halves, all right, take all the constants down in front, times the integral from 0 to 4 of $t$ times the sine of $\pi n$ over 2 times $t$, $dt$.

Okay, so now, here in computing this integral, all right, what we're going to use is integration by parts, all right, which is an integration method that I would suggest for an integral like this, because when we integrate by parts, we can bring down the power of this factor $t$ over here by one, so that it just becomes a constant. All right. So remember that integration by parts says that the integral of $u\,dv$ is equal to $u$ times $v$ minus the integral of $v\,du$. Right? So the integral of $u\,dv$ is what we're starting with, and what we want to do is to figure out, in the integrand here, what should we pick $u$ to be, what should we pick $dv$ to be, in order to be able to compute this integral over here. All right, and our goal is to take this factor of $t$ down to a constant. All right. So that means that we should take $u$ to be equal to $t$. All right, and $dv$ then is everything else, which is the sine of $\pi n$ over 2 times $t$, $dt$. All right, then $du$ is equal to $dt$, and then $v$ is equal to the integral of the sine of $\pi n$ over 2 times $t$, which is minus 2 over $\pi n$ times the cosine of $\pi n$ over 2 times $t$. Okay. And so now, using the integration by parts formula here, all right, then what we have is that $b_n$ is equal to five halves, and then for $u$ times $v$, all right, we have, and we're going to be evaluating this at the limits of integration, it is minus 2 over $\pi n$ times $t$ times the cosine of $\pi n$ over 2 times $t$, evaluated at 0 and 4, the limits of integration. And then for minus $v\,du$, all right, we have minus minus, so that's plus, then we have 2 over $\pi n$ times the integral from 0 to 4 of the cosine of $\pi n$ over 2 times $t$, $dt$. All right. So we've done what we wanted: we got rid of the $t$ in the integral. All right. So, then, here, all right, this integral here is 0. Okay? Because again, we're integrating a cosine function over an integer number of full periods. All right, so that integral is going to be 0. And so what we are left with is five halves, okay, times, and then it's minus 2 over $\pi n$, all right, times, and then so we're evaluating at 4, $t$ is 4, and then the cosine of $\pi n$ over 2 times $t$ is going to be the cosine of $2\pi n$, which is always one. All right, and then, when we evaluate this at the lower limit, it's 0 because we have $t$ equal to 0 over here, right? So this is what we have for our result. And if we multiply this out, right, it's just 5 times 4 times minus one, which is minus 20, over $\pi$ times $n$. Okay, so that is what $b_n$ is. All right.

And now that we have $a_0$, $a_n$ and $b_n$, then we can see that $f_1(t)$, all right, it's $a_0$, if you go back up here to the general form of the Fourier series expansion, it's $a_0$, which is 10, all right, plus the sum of $a_n$ times the cosine of $n\omega_0 t$ (all these $a_n$'s here for $n$ not equal to 0 are 0), all right, plus $b_n$ times the sine of $n\omega_0 t$. So the $b_n$'s we just computed, they're nonzero, so we just have to substitute them into this expression here. All right! So we get that $f_1(t)$ is equal to $a_0$, which is 10, minus 20 over $\pi$ — that's the minus 20 over $\pi$ from what we just calculated for $b_n$ — times the sum, $n$ goes from one to infinity, of one over $n$, all right, that's this one over $n$ from $b_n$ over here, times the sine of $\pi n$ over 2 times $t$. Okay? And if we look at that expression and compare it to what was given in the problem up here, all right, it's the same. Okay, so indeed, we've gotten the correct Fourier series expansion, at least the same as the one that's given in the book, which is the correct one. And so that result checks out.

Okay, next, what we want to do is to figure out how the function $f_2$ is related to $f_1$, and then from that to see if we can then easily deduce, from the Fourier series expansion for $f_1$ that we just calculated, what the Fourier series expansion for $f_2$ is over here. All right, and so if we look at $f_1$ and $f_2$, we can see that there are a few relatively straightforward differences. One is that the amplitude of $f_2$ is twice the amplitude of $f_1$, right? It's a total range of 40 rather than 20. All right, so we'll need to take $f_1$ and scale it by a factor of 2. Okay? Then you can see that it's shifted down so that its average value is 0. Okay, so after multiplying this by 2, we're going to have to shift it down by 20, okay, to get $f_2$. And then we can see that the period of $f_2$ is 8 s, whereas the period of $f_1$ is 4. But it's still a linear function in here. So that means that from $f_1(t)$, what we'll want to do is take the time axis and divide by 2. All right, and that'll scale out the period accordingly. So instead of having $f_1(t)$, what we really want is $f_1(\tfrac{1}{2}t)$.

Okay. So putting all of that together, right, basically what we can see is that from the plots of $f_1(t)$ and $f_2(t)$, all right, we can see that, as I just described, $f_2(t)$ is equal to 2 times $f_1(\tfrac{1}{2}t)$ minus 20. Right? This factor of 2 over here is the vertical scaling by a factor of 2. This minus 20 is the downward shift, and then this one half $t$ is expanding out the time axis, so that we get twice the period for $f_2$ as we had for $f_1$. Okay. And so now here, since we have the Fourier series expansion for $f_1(t)$, all right, all we have to do is to use that for $f_1$ down here, where we have one half $t$ instead of $t$, and then that'll give us the Fourier series expansion for $f_2(t)$. Right. So we just go ahead and do that. Then what we get is that $f_2(t)$ is equal to, right, 2 times $f_1(\tfrac{1}{2}t)$, so it's 2 times 10, which is 20, minus, and then 2 times 20 over $\pi$, so minus 40 over $\pi$, times the sum from $n$ equal to one to infinity of one over $n$ times the sine of, and then, instead of $t$, we have one half $t$ in the argument, so it'll be $\pi n$ over 4 times $t$. Okay, and then minus 20 over here. Okay. And we can simplify this a little bit, all right, because the 20 here and the minus 20 here cancel each other out. And so what we get finally is that $f_2(t)$ is equal to minus 40 over $\pi$ times the sum for $n$ equal to one to infinity of one over $n$ times the sine of $\pi n$ over 4 times $t$, and that's the answer.

Okay, so this is an example of calculating Fourier series coefficients and using the result for one function to deduce the Fourier series expansion for a function that is similar in certain key ways.

### Key points (instructor retrospective)

Okay. So if we look at that, what are some of the key points here? Okay. And thinking about this retrospectively, having worked out the answer, one is that when we calculated the Fourier coefficients, it was basically just doing a bunch of integrals. Okay, so the calculation of the Fourier series expansion for $f_1(t)$, all right, what it basically involved was a bunch of straightforward integrals. All right, and, as we saw in various stages in this process, there were certain coefficients that we could see, in retrospect, should be 0 just by applying some simple symmetry arguments. Certain coefficients, all right, can be seen to be 0, all right, essentially by symmetry arguments. Okay, for example, the arguments that we made based on whether functions were even or odd.

Okay, then the second point here, all right, which relates to the question that was more explicitly asked in this problem, is that if we're given the Fourier series for one function, then we could straightforwardly deduce what the Fourier series would be for another function that was related to it in certain ways, by scaling either the vertical or the horizontal axis, and also shifting vertically along the vertical axis, right? So, given the Fourier series for the function $f_1(t)$, which was actually given in this problem, although we saw how that was calculated as well, then computing — and it's really more deducing than computing — the Fourier series for $f_2(t)$ was relatively easy, once we saw how $f_1$ and $f_2$ were related to each other. So what we needed to do was that we needed to recognize how $f_1(t)$ basically could be transformed into $f_2(t)$, all right, by a combination of vertical shift — or actually, probably, to put this in the most appropriate order, scaling by a factor of 2, doubling of the period, and then vertical shift, okay, of that result. Okay? And then applying the same transformations to the Fourier series expansion for $f_1(t)$ then gave us directly the Fourier series expansion for $f_2(t)$. Okay.

## Index terms

Ulaby 13.16, Problem 13.16, Fourier series, Fourier series coefficients, trigonometric Fourier series, a_0, a_n, b_n, average value over one period, DC component, fundamental frequency, omega_0 = 2 pi / T, sawtooth waveform, periodic ramp, period T = 4 s, period 8 s, analytical expression f_1(t) = 5(t - nT), change of variables, time shift by 2 s, tau = t - 2, odd function, even function, symmetry argument, odd times even is odd, integral over integer number of periods is zero, projection onto basis function, basis set of sines and cosines, linear algebra analogy, dot product, integration by parts, u dv = uv - v du, cos(2 pi n) = 1, b_n = -20/(pi n), f_1(t) = 10 - (20/pi) sum (1/n) sin(pi n t / 2), f_2(t) = 2 f_1(t/2) - 20, amplitude scaling, time scaling, doubling of period, vertical shift, f_2(t) = -(40/pi) sum (1/n) sin(pi n t / 4), Fig. P13.16, Ulaby/Maharbiz/Furse
