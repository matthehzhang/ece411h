---
course: ECE 411H
kind: problem-video
source: Problem Solving Videos/Ulaby 13.44.pdf
source_pages: 3
author: Prof. Ed Yu
unit: final
topics: [fourier-transform, euler-identity, complex-exponential, damped-sinusoid, integration-by-parts, finite-duration-signal, ulaby-13.44]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
deepgram_transcript: deepgram/Ulaby_13.44.deepgram.txt
deepgram_paragraphs: deepgram/Ulaby_13.44.deepgram.md
---

# Ulaby 13.44 — Fourier transforms by direct integration: damped sin·cos product and a truncated ramp-exponential

**Summary.** Problem-solving video for Ulaby/Maharbiz/Furse Problem 13.44. Part (a) asks for the Fourier transform of $f(t) = e^{-\alpha t}\sin(\omega_1 t)\cos(\omega_2 t)\,u(t)$ with $\alpha = 0.5\ \text{s}^{-1}$, $\omega_1 = 4$ rad/s, $\omega_2 = 2$ rad/s; part (b) asks for the transform of $g(t) = t e^{-\alpha t}$ on $0 \le t \le 10\alpha$ (zero elsewhere). Prof. Yu solves (a) by rewriting the sine and cosine with Euler's identity so $f(t)$ becomes four complex exponentials, derives the general result $\mathcal{F}[e^{-\alpha t}e^{j\omega_0 t}u(t)] = 1/(\alpha + j(\omega - \omega_0))$, combines pairs over common denominators, and gets $F(\omega) = \frac{3}{(0.5+j\omega)^2+36} + \frac{1}{(0.5+j\omega)^2+4}$. Part (b) is a direct finite-limit integral done by integration by parts, giving $G(\omega) = \frac{-5}{0.5+j\omega}e^{-5(0.5+j\omega)} - \frac{e^{-5(0.5+j\omega)}-1}{(0.5+j\omega)^2}$. Exam lessons: convert trig products to complex exponentials; use integration by parts to remove polynomial factors $t^n$.

> **Audio transcript (Deepgram nova-3, ECE 411 keyterms, timestamped):** `deepgram/Ulaby_13.44.deepgram.txt` ; paragraph form: `deepgram/Ulaby_13.44.deepgram.md`. Fresh ASR of the video audio; where it disagrees with the Narration section (built from the published auto-captions), prefer this file and the handwritten page.

## Problem statement

(Printed textbook excerpt pasted on page 1.)

13.44 Find the Fourier transform of the following signals with $\alpha = 0.5\ \text{s}^{-1}$, $\omega_1 = 4$ rad/s, and $\omega_2 = 2$ rad/s.

(a) $f(t) = e^{-\alpha t}\sin(\omega_1 t)\cos(\omega_2 t)\,u(t)$

(b) $g(t) = t e^{-\alpha t},\ 0 \le t \le 10\alpha$

(From the narration: for other values of $t$, $g(t)$ is 0.)

## Page 1

Header: Ulaby 13.44

(Printed problem statement pasted at upper left, as transcribed above.)

Handwritten at upper right:

**Example:** computing Fourier transforms.

a) $f(t) = e^{-\alpha t}\sin\omega_1 t\,\cos\omega_2 t\,u(t)$ ; $\alpha = 0.5\ \text{s}^{-1}$, $\omega_1 = 4$ rad/s, $\omega_2 = 2$ rad/s

$$= e^{-\alpha t}\left(\frac{1}{j2}\right)\left(e^{j\omega_1 t} - e^{-j\omega_1 t}\right)\left(\frac{1}{2}\right)\left(e^{j\omega_2 t} + e^{-j\omega_2 t}\right)u(t)$$

$$= \frac{e^{-\alpha t}}{j4}\left(e^{j(\omega_1+\omega_2)t} - e^{-j(\omega_1+\omega_2)t} + e^{j(\omega_1-\omega_2)t} - e^{-j(\omega_1-\omega_2)t}\right)u(t)$$

In general,

$$\mathcal{F}\left[e^{-\alpha t}e^{j\omega_0 t}u(t)\right] = \int_0^{\infty} e^{-\alpha t}e^{j\omega_0 t}e^{-j\omega t}\,dt$$

$$= \frac{1}{-\alpha + j\omega_0 - j\omega}\left[e^{-\alpha t}e^{j\omega_0 t}e^{-j\omega t}\right]_0^{\infty}$$

$$= \frac{1}{\alpha + j(\omega - \omega_0)}$$

$$\Rightarrow\ F(\omega) = \mathcal{F}[f(t)]$$

$$= \frac{1}{j4}\left[\frac{1}{\alpha + j(\omega - (\omega_1+\omega_2))} - \frac{1}{\alpha + j(\omega + \omega_1 + \omega_2)} + \frac{1}{\alpha + j(\omega - (\omega_1 - \omega_2))} - \frac{1}{\alpha + j(\omega + (\omega_1 - \omega_2))}\right]$$

$$= \frac{1}{j4}\left[\frac{(\cancel{\alpha + j\omega}) + j(\omega_1+\omega_2) - \left[(\cancel{\alpha + j\omega}) - j(\omega_1+\omega_2)\right]}{(\alpha+j\omega)^2 + (\omega_1+\omega_2)^2} + \frac{(\cancel{\alpha+j\omega}) + j(\omega_1-\omega_2) - \left[(\cancel{\alpha+j\omega}) - j(\omega_1-\omega_2)\right]}{(\alpha+j\omega)^2 + (\omega_1-\omega_2)^2}\right]$$

(In each numerator the two $(\alpha + j\omega)$ terms are struck through in green to show they cancel.)

$$= \frac{1}{2}\left[\frac{\omega_1+\omega_2}{(\alpha+j\omega)^2+(\omega_1+\omega_2)^2} + \frac{\omega_1-\omega_2}{(\alpha+j\omega)^2+(\omega_1-\omega_2)^2}\right];\quad \alpha = 0.5\ \text{s}^{-1},\ \omega_1 = 4\ \text{rad/s}$$

(This last line is cut off at the bottom of the page and repeated at the top of page 2.)

## Page 2

(Top: repeat of the line cut off from page 1.)

$$= \frac{1}{2}\left[\frac{\omega_1+\omega_2}{(\alpha+j\omega)^2+(\omega_1+\omega_2)^2} + \frac{\omega_1-\omega_2}{(\alpha+j\omega)^2+(\omega_1-\omega_2)^2}\right];\quad \alpha = 0.5\ \text{s}^{-1}\ \text{[partly cut off]},\ \omega_1 = 4\ \text{rad/s},\ \omega_2 = 2\ \text{rad/s}$$

$$\Rightarrow\ \boxed{F(\omega) = \frac{3}{(0.5+j\omega)^2+36} + \frac{1}{(0.5+j\omega)^2+4}}$$

b) $g(t) = t e^{-\alpha t}$ for $0 \le t \le 10\alpha$ ; $\alpha = 0.5\ \text{s}^{-1}$

$$G(\omega) = \int_0^{10\alpha} t\,e^{-\alpha t}e^{-j\omega t}\,dt;$$

(side note, integration by parts:) $\int u\,dv = uv - \int v\,du$; $u = t$, $dv = e^{-\alpha t}e^{-j\omega t}dt$; $du = dt$, $v = \frac{-1}{\alpha + j\omega}e^{-\alpha t}e^{-j\omega t}$

$$= \left[\frac{-t}{\alpha+j\omega}e^{-\alpha t}e^{-j\omega t}\right]_0^{10\alpha} + \frac{1}{\alpha+j\omega}\int_0^{10\alpha} e^{-\alpha t}e^{-j\omega t}\,dt$$

$$= \frac{-10\alpha}{\alpha+j\omega}e^{-(\alpha+j\omega)(10\alpha)} + \frac{1}{\alpha+j\omega}\left[\frac{e^{-\alpha t}e^{-j\omega t}}{-(\alpha+j\omega)}\right]_0^{10\alpha}$$

$$= \frac{-10\alpha}{\alpha+j\omega}e^{-(\alpha+j\omega)(10\alpha)} - \frac{e^{-(\alpha+j\omega)(10\alpha)} - 1}{(\alpha+j\omega)^2};\quad \alpha = 0.5\ \text{s}^{-1}$$

$$\Rightarrow\ \boxed{G(\omega) = \frac{-5}{0.5+j\omega}e^{-5(0.5+j\omega)} - \frac{e^{-5(0.5+j\omega)} - 1}{(0.5+j\omega)^2}}$$

**Key points:**

(i) Complex exponentials + Euler identity can simplify

(continues on page 3)

## Page 3

(i) Complex exponentials + Euler identity can simplify computation of Fourier transforms.

(ii) For Fourier transforms of functions with factors of $t$ (or $t^n$), integration by parts often useful.

The rest of the page is blank.

## Narration transcript

Okay, so this is Ulaby 13.44. And this here is an example of computing Fourier transforms.

Okay? And in this problem we are given two different functions, all right, for the two different parts of the problem, with numerical values for the parameters as specified here. And we're asked to calculate the Fourier transforms of these two functions here.

So let's go ahead and start with this. The first function is $f(t)$. It's $e^{-\alpha t}$ times the sine of $\omega_1 t$ times the cosine of $\omega_2 t$ times $u(t)$. And $\alpha$ is equal to 0.5 inverse seconds, $\omega_1$ is equal to 4 radians per second, and $\omega_2$ is equal to 2 radians per second. All right, and so we want to compute the Fourier transform of this function here. All right, and what we are going to do is, basically, we're using the Euler identity to write the sine and the cosine as complex exponential functions. And then, when we multiply all this out, we will essentially be taking the Fourier transform of a bunch of complex exponentials, which is relatively straightforward. All right. So that's how we're going to proceed with this.

So this is going to be $e^{-\alpha t}$, and then for the sine of $\omega_1 t$ we have one over $j$ times 2 times $e^{j\omega_1 t}$ minus $e^{-j\omega_1 t}$, and then for the cosine of $\omega_2 t$ we have one half times $e^{j\omega_2 t}$ plus $e^{-j\omega_2 t}$. And all this times $u(t)$. Okay. And so, if we multiply all of this out, then we get $e^{-\alpha t}$ over $j$ times 4 — all right, the $j$ times 4 in the denominator is one over $j2$ times one half — and then for the exponentials we get $e^{j(\omega_1 + \omega_2)t}$, that's this term times this term, minus $e^{-j(\omega_1+\omega_2)t}$, that's this term times this term, and then from the other two combinations we get plus $e^{j(\omega_1 - \omega_2)t}$ minus $e^{-j(\omega_1 - \omega_2)t}$. All of this times $u(t)$.

Okay? So now we've written $f(t)$ in a form that consists essentially of just complex exponential functions. So let's think about and work out what the Fourier transform is for a complex exponential. Okay, so in general, all right, what we have is that the Fourier transform — suppose we're thinking about the Fourier transform of a function $e^{-\alpha t}$ times $e^{j\omega_0 t}$ times $u(t)$. All right, then writing that out explicitly as an integral, that's going to be the integral from 0 to infinity of $e^{-\alpha t}$ times $e^{j\omega_0 t}$ times $e^{-j\omega t}$, $dt$. All right, the $u(t)$ was factored in by taking the integral just to go from 0 to infinity, rather than minus infinity to infinity. And if we integrate this, all right, we have one over minus $\alpha$ plus $j\omega_0$ minus $j\omega$, times $e^{-\alpha t}e^{j\omega_0 t}e^{-j\omega t}$ from 0 to infinity. Evaluating this over here at infinity minus its value at 0: at infinity, this function inside the square brackets is 0 because of the $e^{-\alpha t}$, and at $t$ equals 0 this function in the square brackets is one. So we just get a minus one from all of this, and then that minus one we can multiply the denominator by, and if we do that, what we finally get is one over $\alpha$ plus $j$ times $\omega$ minus $\omega_0$. Okay, so that is the Fourier transform of this complex exponential function times $u(t)$ generally, and we can use that to compute the Fourier transform of each of these four terms over here in $f(t)$. All right.

So, using that, right, $F(\omega)$, all right, which is the Fourier transform of this function $f(t)$, is going to be one over $j$ times 4 — all right, that's the constant factor that we had from here — okay, and then for the four complex exponentials, we get one over $\alpha$ plus $j$ times $\omega$ minus the quantity $\omega_1 + \omega_2$, that's the first one; minus one over $\alpha$ plus $j$ times $\omega + \omega_1 + \omega_2$, the second one; plus one over $\alpha$ plus $j$ times $\omega - \omega_1 - \omega_2$; minus one over $\alpha$ plus $j$ times $\omega + \omega_1 - \omega_2$. All right.

And so this is equal to one over $j$ times 4, and then what we're going to do here is we're going to take the first two terms and put them over a common denominator, which will be the product of these two denominators here. That means that in the numerator here we'll have this denominator; in the numerator here we'll have this denominator; and then we'll do the same thing in combining these two terms over here over a common denominator consisting of the product of this denominator and this denominator. Okay. So if we do all that, then what we get from these first two terms is $\alpha + j\omega$ — right? So this is now going to be this denominator here, because we're multiplying this fraction by this in the numerator and also the denominator — so it's $\alpha + j\omega$ plus $j$ times $\omega_1 + \omega_2$, all right, and then minus what we have for this numerator over here, which is going to be this denominator, so minus the quantity $\alpha + j\omega$ minus $j$ times $\omega_1 + \omega_2$; all of that divided by the product of these two denominators, which is $(\alpha + j\omega)$ squared plus $(\omega_1 + \omega_2)$ squared. All right, and then we're going to do the same thing for these two terms over here. So in the numerator we will get $\alpha + j\omega$ plus $j$ times $\omega_1 - \omega_2$, minus the quantity $\alpha + j\omega$ minus $j$ times $\omega_1 - \omega_2$, divided by the common denominator $(\alpha + j\omega)^2$ plus $(\omega_1 - \omega_2)^2$.

Okay, so now, all right, we can simplify this a little bit, because we can see that in this first term over here in the numerator these two terms cancel, and these two terms can be combined to give us $2j$ times the quantity $\omega_1 + \omega_2$. In this second term over here, this term and this term cancel out, and then this term and this term in the numerator can be combined to give us $2j$ times the quantity $\omega_1 - \omega_2$. Okay? And then, if we factor out those $j$ times twos from each of these terms, then that'll cancel with the $j$ times 4 in the denominator to give us just one half. So we get one half times, and then what we have left in the first term is $\omega_1 + \omega_2$ divided by $(\alpha + j\omega)$ quantity squared plus $(\omega_1 + \omega_2)$ quantity squared, and then from this second term over here, $\omega_1 - \omega_2$ divided by $(\alpha + j\omega)^2$ plus $(\omega_1 - \omega_2)^2$.

Okay. And if we now substitute in the numerical values, which are that $\alpha$ is equal to 0.5 inverse seconds, $\omega_1$ is equal to 4 radians per second, and $\omega_2$ is equal to 2 radians per second, then what we get is that $F(\omega)$ is equal to: from this first term we have $\omega_1 + \omega_2$, that's 4 plus 2, that's 6, divided by 2, that's 3, divided by $\alpha$, which is 0.5, plus $j\omega$, quantity squared, and then plus $\omega_1 + \omega_2$, that's 6 squared, that's 36. And then from the second term we have $\omega_1 - \omega_2$, that's 4 minus 2, that's 2, times one half, that's one, divided by, and then the denominator, it's $0.5 + j\omega$ quantity squared plus $\omega_1 - \omega_2$, that's 4 minus 2, that's 2, squared, that's 4. Okay, so that's what we have here for $F(\omega)$, right, the Fourier transform of the function $f(t)$ that was given in the problem.

Then the second part of this problem is that we're given a function $g(t)$, and it's equal to $t$ times $e^{-\alpha t}$, and that is for 0 less than or equal to $t$ less than or equal to $10\alpha$; for other values of $t$ this is 0, and $\alpha$ is equal to 0.5 inverse seconds. Okay, so here we can write the Fourier transform explicitly as an integral from 0 to $10\alpha$ of $t$ times $e^{-\alpha t}e^{-j\omega t}$, $dt$. Okay, so now for this integral, what we want to do is — we can do the integral easily if we can reduce this $t$ to just a constant, and we can do that using integration by parts. All right, so the integral of $u$ times $dv$ is equal to $uv$ minus the integral of $v$ times $du$. So what we want to do is, right, this is the integral that we start with, this is the integral that we want to be able to compute. And so what we want to do is to choose $u$ to be such that when we take this derivative, we get rid of this $t$. Okay, so we can take $u$, and then what's left has to be something that we can integrate. All right, but it's just exponentials here, so we can integrate those. So we take $u$ to be equal to $t$. And then $dv$ is $e^{-\alpha t}e^{-j\omega t}dt$, all right, which we can integrate. Then $du$ is equal to $dt$, and then $v$ is equal to minus one over $\alpha + j\omega$ times $e^{-\alpha t}e^{-j\omega t}$. All right.

So then $G(\omega)$ is equal to — we started with this integral here, and then we're going to use this right-hand side. So $u$ times $v$ evaluated at the limits of integration: so that's $t$ times minus one over $\alpha + j\omega$, so that's minus $t$ over $\alpha + j\omega$, okay, times these exponentials $e^{-\alpha t}e^{-j\omega t}$, evaluated from 0 to $10\alpha$. And then we have minus the integral of $v\,du$; $v$ is this expression here, so this minus and this minus will cancel out, so we get plus one over $\alpha + j\omega$ — right, that's this one over $\alpha + j\omega$ here — times the integral from 0 to $10\alpha$ of $e^{-\alpha t}e^{-j\omega t}$, $dt$. All right, and so, from this first term over here, when we evaluate it at the upper limit of integration, we get minus $t$, which is minus $10\alpha$, over $\alpha + j\omega$, times $e$ to the minus $(\alpha + j\omega)$ times $10\alpha$, which is $t$; and then at the lower limit of integration, which is $t$ equal to 0, then this $t$ over here will give us a factor of 0, so this will be 0. Okay. Then, from the integral, we get one over $\alpha + j\omega$, and then, integrating these complex exponentials, we get $e^{-\alpha t}e^{-j\omega t}$ divided by minus the quantity $\alpha + j\omega$, evaluated at 0 and $10\alpha$.

Okay. So then, just carrying over this first term over here, we have minus $10\alpha$ over $\alpha + j\omega$ times $e$ to the minus $(\alpha + j\omega)$ times $10\alpha$, and then we have minus — that's this minus sign over here — then in the denominator we have $(\alpha + j\omega)$ quantity squared, that's this factor and this factor, and in the numerator we have this evaluated at $10\alpha$ minus this evaluated at 0. So we have $e$ to the minus $(\alpha + j\omega)$ times $10\alpha$, minus, and then at $t$ equal to 0 the numerator is just one. Okay, so now, remember, $\alpha$ is equal to 0.5 inverse seconds. So if we take that value for $\alpha$ and plug it in here, then what we finally get for $G(\omega)$ is minus $10\alpha$, $\alpha$ being 0.5, is minus 5, over $0.5 + j\omega$, and then we have $e$ to the minus, and then $10\alpha$, that's 5, times $(0.5 + j\omega)$; all right, minus, and then we have $e$ to the minus 5 times $(0.5 + j\omega)$, minus one, divided by $(0.5 + j\omega)$ quantity squared. All right. And so this is the Fourier transform of the function $g(t)$ that we were given in the problem.

### Key points (instructor retrospective)

Okay, so what are some of the key points here, if we think back on what we did in this example? All right! The first is that when we did part (a) of this problem, all right, back here, we were able to make it relatively simple by converting everything to complex exponentials using, essentially, the Euler identity. All right. And that actually made it quite a bit simpler to compute the Fourier transform, because we were just computing the Fourier transform of complex exponentials, which, as we saw here, is quite straightforward to do. All right. So the first point that we can note here is that complex exponentials and the Euler identity, okay, these often, and in this case did, simplify the computation of Fourier transforms, particularly for transforms that involve trigonometric functions, right, because we can convert those to complex exponentials. And then, if we're multiplying a bunch of trigonometric functions together, then all we get is a combination of terms that are all just complex exponentials, and the Fourier transforms of those are easy to compute.

Then the second thing that we noted here was that we saw in part (b) that if we had Fourier transforms of functions that have factors that are polynomials of $t$, then we can use integration by parts to get rid of those factors of $t$ — in this case it was just a linear term in $t$, a linear factor in $t$ — and to get back to essentially just complex exponentials again. Right? So for Fourier transforms of functions with factors of $t$, or, more generally, $t^n$, all right, then integration by parts is often useful. Okay, if we had $t$ to some power, then we could do multiple, $n$ basically, successive integrations by parts, and that would bring us down back eventually to just having a constant again.

Okay, so that is it for this example, and I will now stop this recording.

## Index terms

Ulaby 13.44, Problem 13.44, Fourier transform, Euler identity, complex exponential, sine as complex exponentials, cosine as complex exponentials, 1/(j2), damped sinusoid, product of sinusoids, e^{-alpha t} u(t), unit step u(t), F[e^{-alpha t} e^{j omega_0 t} u(t)] = 1/(alpha + j(omega - omega_0)), one-sided integral 0 to infinity, common denominator, (alpha + j omega)^2 + (omega_1 + omega_2)^2, F(omega) = 3/((0.5+j omega)^2+36) + 1/((0.5+j omega)^2+4), alpha = 0.5 s^-1, omega_1 = 4 rad/s, omega_2 = 2 rad/s, finite-duration signal, g(t) = t e^{-alpha t} on 0 to 10 alpha, integration by parts, u dv = uv - v du, u = t, polynomial factor t^n, G(omega) = (-5/(0.5+j omega)) e^{-5(0.5+j omega)} - (e^{-5(0.5+j omega)} - 1)/(0.5+j omega)^2, Ulaby/Maharbiz/Furse
