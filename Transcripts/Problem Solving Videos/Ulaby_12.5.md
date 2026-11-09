---
course: ECE 411H
kind: problem-video
source: Problem Solving Videos/Ulaby 12.5.pdf
source_pages: 7
author: Prof. Ed Yu
unit: exam2
topics: [laplace-transform, time-shift-property, frequency-differentiation, unit-step, complex-exponential, table-12-1, table-12-2, ulaby-12.5]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
deepgram_transcript: deepgram/Ulaby_12.5.deepgram.txt
deepgram_paragraphs: deepgram/Ulaby_12.5.deepgram.md
---

# Ulaby 12.5 — Calculation of Laplace transforms (six functions)

**Summary.** Prof. Yu works Ulaby/Maharbiz/Furse Problem 12.5: compute the (forward) Laplace transform of six time-domain functions, each built from an exponential or sinusoid times a unit step, using only the properties in Table 12-1 and the pairs in Table 12-2. The recurring method is: (0) pick a basic pair ($e^{-at}u(t)\leftrightarrow 1/(s+a)$ or the complex exponential), (1) apply the time-shift property $f(t-T)u(t-T)\leftrightarrow e^{-Ts}F(s)$, (2) apply frequency differentiation $t^n f(t)\leftrightarrow(-1)^n\frac{d^n}{ds^n}F(s)$, (3) multiply by the constant. Part (b) is a long quotient-rule grind ($t^2\sin$); part (c) re-derives the Table 12-2 entry $t^{n-1}e^{-at}u(t)\leftrightarrow (n-1)!/(s+a)^n$; parts (e) and (f) show the trick of deliberately introducing a time shift (factoring $e^{-12}$ or $e^{-2}$ out) so the step and exponential share the same shift. Companion narration (.vtt) is transcribed at the end. Exam relevance: this is the canonical forward-transform toolkit for the Chapter 12 portion of Exam 2.

> **Audio transcript (Deepgram nova-3, ECE 411 keyterms, timestamped):** `deepgram/Ulaby_12.5.deepgram.txt` ; paragraph form: `deepgram/Ulaby_12.5.deepgram.md`. Fresh ASR of the video audio; where it disagrees with the Narration section (built from the published auto-captions), prefer this file and the handwritten page.

## Problem statement

**12.5** Determine the Laplace transform of each of the following functions by applying the properties given in Tables 12-1 and 12-2.

- *(a) $h_1(t) = 12\,t\,e^{-3(t-4)}\,u(t-4)$
- (b) $h_2(t) = 27\,t^2\sin(6t-60^\circ)\,u(t)$
- *(c) $h_3(t) = 10\,t^3 e^{-2t}\,u(t)$
- (d) $h_4(t) = 5(t-6)\,u(t-3)$
- (e) $h_5(t) = 10\,e^{-3t}\,u(t-4)$
- (f) $h_6(t) = 4\,e^{-2(t-3)}\,u(t-4)$

(Asterisks are the textbook's marks on parts (a) and (c). The statement is pasted as a textbook image at the top of page 1.)

## Page 1

Header (typed): "Ulaby 12.5". Textbook problem image (as above). Handwritten title at top right, underlined: **Example: calculation of Laplace transforms**

a) $h_1(t) = 12\,t\,e^{-3(t-4)}\,u(t-4)$

0) let $f_1(t) = e^{-3t}u(t)$; then $F_1(s) = \dfrac{1}{s+3}$

1) use time-shift property — $f(t-T)\,u(t-T) \leftrightarrow e^{-Ts}F(s)$

let $f_2(t) = e^{-3(t-4)}u(t-4) = f_1(t-4) = f_1(t-4)\,u(t-4)$

$$\Rightarrow F_2(s) = e^{-4s}\left(\frac{1}{s+3}\right)$$

2) use frequency differentiation property —
$t\,f(t) \leftrightarrow -\dfrac{d}{ds}F(s)$ from Ulaby et al., Table 12-1, #9.

let $f_3(t) = t\,f_2(t) = t\,e^{-3(t-4)}u(t-4)$

$$\Rightarrow F_3(s) = -\frac{d}{ds}F_2(s) = -\frac{d}{ds}\left[e^{-4s}\left(\frac{1}{s+3}\right)\right]$$
$$= -\left\{-4e^{-4s}\left(\frac{1}{s+3}\right) - e^{-4s}\left(\frac{1}{s+3}\right)^2\right\}$$
$$= e^{-4s}\left[\frac{4}{s+3} + \frac{1}{(s+3)^2}\right]$$

3) multiply by constant (12)

$$\Rightarrow \boxed{H_1(s) = 12\,e^{-4s}\left[\frac{4}{s+3} + \frac{1}{(s+3)^2}\right]}$$

## Page 2

(Top: the boxed result $H_1(s) = 12e^{-4s}\left[\frac{1}{s+3}+\frac{1}{(s+3)^2}\right]$ is repeated, partially cut off by the page break — this is the same box as on page 1; the "4" numerator is clipped.)

**Key points:** (underlined)

(i) start with a basic L.T. result, here $e^{-3t}u(t) \leftrightarrow \dfrac{1}{s+3}$

(ii) use L.T. properties in succession — here, time-shift then frequency derivative, then multiplication by constant

(iii) $u(t) = u^2(t) = u^n(t)$.

b) $h_2(t) = 27\,t^2\sin(6t-60^\circ)\,u(t)$

0) let $f_1(t) = e^{\pm j(6t-60^\circ)}u(t)$; then $F_1(s) = e^{\mp j60^\circ}\dfrac{1}{s \mp j6}$

1) let $f_2(t) = \sin(6t-60^\circ)\,u(t) = \dfrac{1}{2j}\left(e^{j(6t-60^\circ)} - e^{-j(6t-60^\circ)}\right)u(t)$

$$\Rightarrow F_2(s) = \frac{1}{2j}\left[\frac{e^{-j60^\circ}}{s-j6} - \frac{e^{+j60^\circ}}{s+j6}\right]$$
$$= \frac{1}{2j}\left[\frac{e^{-j60^\circ}(s+j6) - e^{+j60^\circ}(s-j6)}{s^2+36}\right]$$
$$= \frac{-s\sin 60^\circ + 6\cos 60^\circ}{s^2+36}$$

2) use frequency differentiation property —
$t\,f(t) \leftrightarrow -\dfrac{d}{ds}F(s)$ from Ulaby et al., Table 12-1, #9.

let $g(t) = t\,f(t)$ and $g(t) \leftrightarrow G(s)$

$t\,g(t) \leftrightarrow -\dfrac{d}{ds}G(s)$, or $t^2 f(t) \leftrightarrow (-1)^2\dfrac{d^2}{ds^2}F(s)$

$\vdots$

(bottom line cut off by page break; it is the general formula written at the top of page 3)

## Page 3

$$t^n f(t) \leftrightarrow (-1)^n\frac{d^n}{ds^n}F(s)$$

let $f_3(t) = t^2 f_2(t) = t^2\sin(6t-60^\circ)\,u(t)$

$$\Rightarrow F_3(s) = \frac{d^2}{ds^2}\left[\frac{-s\sin 60^\circ + 6\cos 60^\circ}{s^2+36}\right]$$
$$= \frac{d}{ds}\left[\frac{-\sin 60^\circ(s^2+36) - 2s(-s\sin 60^\circ + 6\cos 60^\circ)}{(s^2+36)^2}\right]$$
$$= \frac{d}{ds}\left[\frac{s^2\sin 60^\circ - 12s\cos 60^\circ - 36\sin 60^\circ}{(s^2+36)^2}\right]$$
$$= \frac{(2s\sin 60^\circ - 12\cos 60^\circ)(s^2+36)^2 - 2(s^2+36)(2s)(s^2\sin 60^\circ - 12s\cos 60^\circ - 36\sin 60^\circ)}{(s^2+36)^4}$$
$$= \frac{(2s\sin 60^\circ - 12\cos 60^\circ)(s^2+36) - 4s(s^2\sin 60^\circ - 12s\cos 60^\circ - 36\sin 60^\circ)}{(s^2+36)^3}$$

$$F_3(s) = \frac{-2s^3\sin 60^\circ + 36s^2\cos 60^\circ + 216s\sin 60^\circ - 432\cos 60^\circ}{(s^2+36)^3}$$

3) multiply by constant (27):

$$H_2(s) = 27F_3(s) = \frac{-54s^3\sin 60^\circ + 972s^2\cos 60^\circ + 5832s\sin 60^\circ - 11664\cos 60^\circ}{(s^2+36)^3}$$

$$\Rightarrow \boxed{H_2(s) = \frac{-46.77s^3 + 486s^2 + 5051s - 5832}{(s^2+36)^3}}$$

**Additional key points:** (underlined)

(i) once again, we started with a basic result for LTs and built upon it using properties of LTs and other mathematical tools. (continues on page 4)

## Page 4

(i) once again, we started with a basic result for LTs and built upon it using properties of LTs and other mathematical tools.

(ii) frequency differentiation generalizes to arbitrary powers of $t$, and derivatives of arbitrary order,
$$t^n f(t) \leftrightarrow (-1)^n\frac{d^n}{ds^n}F(s)$$

(iii) $\mathcal{L}\left[e^{-at}u(t)\right] = \dfrac{1}{s+a}$ even for complex values of $a$.

c) $h_3(t) = 10\,t^3 e^{-2t}u(t)$

From Table 12-2, #8 of Ulaby et al., we see directly that
$$t^{n-1}e^{-at}u(t) \leftrightarrow \frac{(n-1)!}{(s+a)^n}\ ;\ \text{here, } n = 4.$$

$$\Rightarrow H_3(s) = 10\,\frac{3!}{(s+2)^4} = \frac{60}{(s+2)^4}$$

We can derive this using frequency differentiation:

0) let $f_1(t) = e^{-2t}u(t)$; then $F_1(s) = \dfrac{1}{s+2}$

1) use frequency differentiation property —
$$t^n f(t) \leftrightarrow (-1)^n\frac{d^n}{ds^n}F(s)$$

let $f_2(t) = t^3 e^{-2t}u(t) = t^3 f_1(t)$

$$\Rightarrow F_2(s) = (-1)^3\frac{d^3}{ds^3}\left(\frac{1}{s+2}\right)$$
$$= (-1)^3\frac{d^2}{ds^2}\left(\frac{-1}{(s+2)^2}\right) = (-1)^3(-1)\frac{d}{ds}\left(\frac{(-2)}{(s+2)^3}\right)$$

(last line partially cut by page break; repeated at top of page 5)

## Page 5

$$= (-1)^3\frac{d^2}{ds^2}\left(\frac{-1}{(s+2)^2}\right) = (-1)^3(-1)\frac{d}{ds}\left(\frac{(-2)}{(s+2)^3}\right)$$
$$= (-1)^3(-1)(-2)\left(\frac{(-3)}{(s+2)^4}\right) = \frac{(-1)^3(-1)(-2)(-3)}{(s+2)^4}$$

$$F_2(s) = \frac{3!}{(s+2)^4} = \frac{6}{(s+2)^4}$$

2) multiply by constant (10):

$$H_3(s) = 10F_2(s),\ \text{or}\ \boxed{H_3(s) = \frac{60}{(s+2)^4}}$$

d) $h_4(t) = 5(t-6)\,u(t-3)$

$h_4(t) = 5t\,u(t-3) - 30\,u(t-3)$

0) let $f_1(t) = u(t-3)$; then $F_1(s) = \dfrac{e^{-3s}}{s}$

1) use frequency differentiation — $t\,f(t) \leftrightarrow -\dfrac{d}{ds}F(s)$

$$\Rightarrow H_4(s) = -5\frac{d}{ds}\left(\frac{e^{-3s}}{s}\right) - 30\frac{e^{-3s}}{s}$$
$$= -5\left[\frac{-3s\,e^{-3s} - e^{-3s}}{s^2}\right] - 30\frac{e^{-3s}}{s}$$
$$= 15\frac{e^{-3s}}{s} + 5\frac{e^{-3s}}{s^2} - 30\frac{e^{-3s}}{s}$$

$$\boxed{H_4(s) = 5e^{-3s}\left(\frac{1}{s^2} - \frac{3}{s}\right)}$$

## Page 6

(Top: the boxed $H_4(s) = 5e^{-3s}\left(\frac{1}{s^2}-\frac{3}{s}\right)$ repeated, clipped by page break.)

e) $h_5(t) = 10\,e^{-3t}u(t-4)$

0) let $f_1(t) = e^{-3t}u(t)$; then $F_1(s) = \dfrac{1}{s+3}$

1) $h_5(t) = 10\,e^{-3t}u(t-4)$
$$= 10\,e^{-12}\,e^{-3(t-4)}u(t-4)$$
$$= 10\,e^{-12}f_1(t-4) = 10\,e^{-12}f_1(t-4)\,u(t-4)$$

2) use time-shift property — $f(t-T)\,u(t-T) \leftrightarrow e^{-sT}F(s)$

$$\Rightarrow H_5(s) = 10\,e^{-12}e^{-4s}F_1(s),\ \text{or}$$
$$\boxed{H_5(s) = 10\,e^{-12}\frac{e^{-4s}}{s+3} = \left(6.14\times 10^{-5}\right)\frac{e^{-4s}}{s+3}}$$

**Additional point:** (underlined)

(i) time shifts, or potentially other modifications, can be deliberately introduced to enable useful properties of LTs to be applied — here, time-shift property of LT.

f) $h_6(t) = 4\,e^{-2(t-3)}u(t-4)$ (cut off at bottom of page; continues on page 7)

## Page 7

f) $h_6(t) = 4\,e^{-2(t-3)}u(t-4)$

0) let $f_1(t) = e^{-2t}u(t)$; then $F_1(s) = \dfrac{1}{s+2}$

1) $h_6(t) = 4\,e^{-2(t-3)}u(t-4)$
$$= 4\,e^{-2}\,e^{-2(t-4)}u(t-4)$$
$$= 4\,e^{-2}f_1(t-4) = 4\,e^{-2}f_1(t-4)\,u(t-4)$$

2) time-shift property — $f(t-T)\,u(t-T) \leftrightarrow e^{-sT}F(s)$

$$\Rightarrow H_6(s) = 4\,e^{-2}e^{-4s}F_1(s),\ \text{or}$$
$$\boxed{H_6(s) = 4\,e^{-2}\frac{e^{-4s}}{s+2} = 0.5413\,\frac{e^{-4s}}{s+2}}$$

(Rest of page blank.)

## Narration transcript

Cleaned from `Problem Solving Videos/Ulaby 12.5 captions.vtt`: timestamps and cue numbers stripped, fragments merged into sentences, obvious auto-caption mishearings corrected ("Yulaby" → Ulaby, "applause/plots transform" → Laplace transform, "Jay" → $j$, "you'll be at all" → Ulaby et al.), verbal fillers ("okay", "alright") trimmed. Content is otherwise complete.

This is Ulaby problem 12.5, and this is an example of — several examples of — the calculation of Laplace transforms. So this is an example of calculation of Laplace transforms. The focus here is on some of the kinds of functions that one might be likely to encounter in various circuit analysis problems. So we'll just go through these one by one.

**Part (a).** For (a), the function that we have in the time domain is $h_1(t)$, and this is given by $12t$ times $e^{-3(t-4)}$ times $u(t-4)$, where, remember, as usual, $u(t)$ is the unit step function. So as a preliminary step let's think about this function: what is the core of this that we can build upon in order to compute the Laplace transform? The core function here is really the exponential function times the unit step function. So we're going to define a function $f_1(t)$, and we'll take that to be $e^{-3t}u(t)$. If that were the function we were dealing with, then its Laplace transform would be $F_1(s)$, and this is just $1/(s+3)$, and you can get that by looking at Table 12-2.

So from here, how do we start from this function which has this Laplace transform, and build upon it to get this full function over here? The first thing we can see is that if we do a time shift — if we replace $t$ in $f_1(t)$ by $t-4$ — then we will get this part of the functionality of $h_1$. So let's do that first. We'll use the time shift property of Laplace transforms to go from $t$ to $t-4$, and that's a useful thing to do because we know how $F_1(s)$ changes if we introduce a time shift in the time domain. What we have is that $f(t-T)u(t-T)$, for some time shift $T$, has Laplace transform $e^{-Ts}F(s)$. So if we know the Laplace transform of some function $f(t)$, such as $f_1(t)$ over here, and then we shift it in the time domain, this tells us what the corresponding Laplace transform is of the time-shifted function.

So we'll define a function $f_2(t)$, and we'll take that to be the time-shifted version of $f_1(t)$: it's $e^{-3(t-4)}u(t-4)$. We've shifted it by 4 in the time domain. So this is just our function $f_1(t-4)$. We can also write that as $f_1(t-4)\,u(t-4)$, because $f_1(t-4)$ already contains the unit step function. So if we multiply by the unit step function again, it doesn't matter — we just get the same thing. We're free to do that, and that brings it into the form that we can use with the time-shift property. So now that we have this equal to $f_2(t)$, we know its Laplace transform is $e^{-4s}$ — $T$ here is 4 — times $F_1(s)$, which is $1/(s+3)$. So $F_2(s) = e^{-4s}\cdot\frac{1}{s+3}$.

So now we've gotten the Laplace transform of this part of $h_1(t)$. Now we have to figure out how to deal with the additional factor of $t$ over here, and the way we deal with that is to use what's known as the frequency differentiation property of Laplace transforms, which you can get from Ulaby et al., Table 12-1, property number 9. This says that if you have a function $t\,f(t)$ in the time domain, and you know the Laplace transform of just $f(t)$, then the Laplace transform of $t\,f(t)$ is minus the derivative with respect to $s$ of $F(s)$, where $F(s)$ is the Laplace transform of $f(t)$.

So we're going to define yet another function, $f_3(t) = t\,f_2(t)$, that is $t\,e^{-3(t-4)}u(t-4)$. You can see that is almost the entire function $h_1$, except for the constant 12, which is very easy to incorporate: we just multiply the final result by 12; we just have to remember to do that at the end. Since $f_3(t) = t f_2(t)$, we know that $F_3(s) = -\frac{d}{ds}F_2(s)$. $F_2(s)$ we figured out up here, so this is minus the derivative with respect to $s$ of $e^{-4s}\cdot\frac{1}{s+3}$. Now we just have to take the derivative of this product with respect to $s$. We get minus (that's the first minus sign) and then the derivative of the product: derivative of the first factor times the second plus the first factor times the derivative of the second. The derivative of the first factor is $-4e^{-4s}$; multiply that by the second factor $\frac{1}{s+3}$. Then the derivative of the second factor is $-\frac{1}{(s+3)^2}$, times the first factor $e^{-4s}$. So we get $-e^{-4s}\frac{1}{(s+3)^2}$. If we simplify a little, pull out the overall factor of $e^{-4s}$, and multiply through by the leading minus sign, which gets rid of the two minus signs, we get $\frac{4}{s+3} + \frac{1}{(s+3)^2}$. That's $F_3(s)$.

Finally, we just have to multiply by the constant we had in $h_1$, which was 12. To incorporate that, all we have to do is multiply $F_3(s)$ by 12. So finally we get $H_1(s)$, the Laplace transform of our original function $h_1$: $H_1(s) = 12e^{-4s}\left[\frac{4}{s+3}+\frac{1}{(s+3)^2}\right]$. That is our result.

If we go back and look at what we did, what were the key points? The first point was that the way we approached this was to start with a basic Laplace transform result: the Laplace transform of just the exponential function times the unit step function. That's something we know or can look up easily in our Laplace transform table. Then what we did was use a succession of properties of Laplace transforms to build up from this basic result to the full function for which we're computing the Laplace transform. So we started with just the basic Laplace transform result — here it was that $e^{-3t}u(t)$ forms a Laplace transform pair with $1/(s+3)$. Then from there we used a number of Laplace transform properties in succession. First we used the time shift property, which introduced an additional exponential factor in the Laplace transform. Then the frequency derivative property, where multiplying by $t$ in the time domain corresponds to taking $-\frac{d}{ds}$ in the $s$ domain. Then we just multiplied by our constant, which just multiplies the Laplace transform by the same constant, and that got us to our result. The third thing we did was to make use of the fact that the unit step function, if you multiply it by itself, you just get the same thing, because $0\times 0 = 0$ and $1\times 1 = 1$ — and in fact that's true for any power of the unit step function. So we made use of that observation and property of the unit step function as well. That is it for part (a).

**Part (b).** Now move on to part (b), which is another Laplace transform example. The function for which we want to compute the Laplace transform is $h_2(t)$, and it is $27t^2\sin(6t-60^\circ)u(t)$. We're going to approach this in a very similar way: we want to start off with some basic Laplace transform result that we can build upon. What we're going to start with here is to look at this $\sin(6t-60^\circ)$, but instead of using the sine as our basic function, we're going to use a complex exponential. So let's define a function $f_1(t)$ that we can work with, and we'll take this to be $e^{\pm j(6t-60^\circ)}u(t)$. Then its Laplace transform $F_1(s)$ is $e^{\mp j60^\circ}$ — that's just the $e^{\pm j(-60^\circ)}$ out in front, which is just a constant (plus-or-minus times the minus sign gives you minus-or-plus) — and then for the exponential part, $e^{\pm j6t}$, we have $\frac{1}{s\mp j6}$. So this is the basic result that we're going to start with.

What we'll do now is combine the complex exponentials so that we get the sine of the same argument. We'll call this new function $f_2(t) = \sin(6t-60^\circ)u(t)$ — that's just these two factors over here. That's $\frac{1}{2j}\left(e^{j(6t-60^\circ)} - e^{-j(6t-60^\circ)}\right)u(t)$. This is just a basic property of complex exponentials: you can combine them in this way to get trigonometric functions. Now we can take each of these and use our result to write the Laplace transform of each term, and therefore of $f_2(t)$, directly. We get $F_2(s) = \frac{1}{2j}\left[\frac{e^{-j60^\circ}}{s-j6} - \frac{e^{+j60^\circ}}{s+j6}\right]$: for the first term, taking the top sign, we get $e^{-j60^\circ}$ divided by $s-j6$; then minus the Laplace transform of $e^{-j(6t-60^\circ)}u(t)$, taking the bottom sign, which is $e^{+j60^\circ}$ divided by $s+j6$.

From here, what we want to do is put this in what will turn out to be a slightly more convenient form, by putting these two terms over a common denominator. The common denominator is going to be $(s-j6)(s+j6)$; those are complex conjugates of each other, so when we multiply them the common denominator is just $s^2+36$. In the numerator we get $e^{-j60^\circ}(s+j6) - e^{+j60^\circ}(s-j6)$. So we have our initial factor $\frac{1}{2j}$, then $\frac{e^{-j60^\circ}(s+j6) - e^{+j60^\circ}(s-j6)}{s^2+36}$. If we rearrange slightly: the terms that have a factor of $s$ are $s\left(e^{-j60^\circ} - e^{+j60^\circ}\right)$ divided by $2j$, and that is actually $-\sin 60^\circ$. So from those terms we get $-s\sin 60^\circ$. Then from $j6e^{-j60^\circ}$ plus (because we have minus minus) $j6e^{+j60^\circ}$, divided by $2j$ — the $j$ in the denominator cancels the $j$'s in the numerator — we get $6\cdot\frac{e^{j60^\circ}+e^{-j60^\circ}}{2}$, which is just $6\cos 60^\circ$. So we get $\frac{-s\sin 60^\circ + 6\cos 60^\circ}{s^2+36}$. This is now the Laplace transform of $\sin(6t-60^\circ)u(t)$.

Then from here we have to figure out how to deal with this factor of $t^2$ multiplying $f_2$, and to do that we can take advantage again of the frequency differentiation property — but now for $t^2$ rather than just $t$. The frequency differentiation property, as given in Ulaby et al. Table 12-1, property 9, is that $t\,f(t)$ forms a Laplace transform pair with $-\frac{d}{ds}F(s)$, where $f(t)$ and $F(s)$ form a Laplace transform pair. But we can easily generalize this to higher powers of $t$. For example, let $g(t) = t\,f(t)$, and take $g(t)$ to form a Laplace transform pair with $G(s)$. Then $t\,g(t)$ forms a Laplace transform pair with $-\frac{d}{ds}G(s)$. But instead of $g(t)$ we can write $t\,f(t)$; then on the left-hand side we get $t^2 f(t)$, and it forms a Laplace transform pair with $-\frac{d}{ds}$ of $-\frac{d}{ds}F(s)$, so $(-1)^2\frac{d^2}{ds^2}F(s)$. If we basically keep on doing that, we can come up with the expression in general for the Laplace transform of $t^n f(t)$: $t^n f(t)$ forms a Laplace transform pair with $(-1)^n\frac{d^n}{ds^n}F(s)$. So this is the property that we're going to use now.

We're going to let $f_3(t) = t^2 f_2(t)$, where $f_2(t)$ was $\sin(6t-60^\circ)u(t)$. When we multiply that by $t^2$ we get almost the whole function $h_2$, except for the constant 27, and we'll just multiply by that constant at the end. So $f_3(t) = t^2\sin(6t-60^\circ)u(t)$, and we can use this frequency differentiation property to compute the Laplace transform of $f_3(t)$ in terms of $F_2(s)$, which we just computed. Using this property, $F_3(s)$ is equal to the second derivative — we're applying this formula with $n=2$, so $(-1)^2 = 1$ and it's $\frac{d^2}{ds^2}$ — of the Laplace transform of $\sin(6t-60^\circ)u(t)$, which we figured out a few minutes ago is $\frac{-s\sin 60^\circ + 6\cos 60^\circ}{s^2+36}$.

So we'll take one derivative of that first. When we take the derivative with respect to $s$, it's the derivative of the numerator times the denominator minus the numerator times the derivative of the denominator, divided by the denominator squared — that's the quotient rule. The derivative of the numerator with respect to $s$ is just $-\sin 60^\circ$; times the denominator $s^2+36$; minus the numerator times the derivative of the denominator, which is $2s$, with the numerator being $-s\sin 60^\circ + 6\cos 60^\circ$. All of this is divided by $(s^2+36)^2$. Before we take another derivative, let's simplify the expression in the square brackets. Looking at the terms proportional to $s^2$: we have $-s^2\sin 60^\circ$, plus (minus times minus) $2s^2\sin 60^\circ$, so overall $s^2\sin 60^\circ$. Terms proportional to $s$: there's only one, $-2s\cdot 6\cos 60^\circ = -12s\cos 60^\circ$. Finally the constant term is $-36\sin 60^\circ$. Divided by $(s^2+36)^2$.

Now we take the derivative of this, again with the quotient rule. It's the derivative of the numerator, $2s\sin 60^\circ - 12\cos 60^\circ$, times the denominator $(s^2+36)^2$, minus the numerator times the derivative of the denominator, which is $2(s^2+36)\cdot 2s$, times the numerator $s^2\sin 60^\circ - 12s\cos 60^\circ - 36\sin 60^\circ$, all divided by the denominator squared, $(s^2+36)^4$. Here we can cancel an overall factor of $s^2+36$ from numerator and denominator. We get $(2s\sin 60^\circ - 12\cos 60^\circ)(s^2+36)$, to a single power, minus $4s$ times $(s^2\sin 60^\circ - 12s\cos 60^\circ - 36\sin 60^\circ)$, divided by $(s^2+36)^3$ — not to the fourth now, to the third, because we cancelled one power.

Now let's simplify the numerator by powers of $s$. Terms proportional to $s^3$: $2s^3\sin 60^\circ$ from the first product, and $-4s^3\sin 60^\circ$ from the second, giving $-2s^3\sin 60^\circ$. Terms proportional to $s^2$: $-12s^2\cos 60^\circ$, plus $4\times 12 = 48$, giving $+36s^2\cos 60^\circ$. Terms proportional to $s$: $2s\sin 60^\circ\times 36 = 72s\sin 60^\circ$, and then minus minus $4\times 36 = 144$, so $144+72 = 216s\sin 60^\circ$. Finally the constant term: $-12\times 36\cos 60^\circ$; $12\times 36$ is $360+72 = 432$, so $-432\cos 60^\circ$. All divided by $(s^2+36)^3$. That is $F_3(s)$.

To get the final result we just have to multiply by the constant 27. So $H_2(s) = 27F_3(s)$: $-27\times 2 = -54s^3\sin 60^\circ$; $27\times 36 = 972s^2\cos 60^\circ$; $27\times 216 = 5832s\sin 60^\circ$; and $-27\times 432 = -11664\cos 60^\circ$; divided by $(s^2+36)^3$. If we evaluate the sine and cosine of $60^\circ$ — $\sin 60^\circ = \sqrt{3}/2$, $\cos 60^\circ = 1/2$ — finally we get $H_2(s) = \dfrac{-46.77s^3 + 486s^2 + 5051s - 5832}{(s^2+36)^3}$. That is the answer to the second part.

There are a few additional key points to note here. First, again, our basic strategy was to start with a basic result for Laplace transforms — all the way back up here, this was just the Laplace transform for a complex exponential — and then we built upon it using the basic properties of Laplace transforms and other simple mathematical tools: expressing the sine as a sum of complex exponentials, then using frequency differentiation, and multiplying by the constant at the end. So we started with the basic result for Laplace transforms and built upon it using properties of Laplace transforms and other mathematical tools. The second point is that, as we showed, this property of frequency differentiation can be generalized to derivatives of arbitrary order, and correspondingly powers of $t$ of arbitrary power: $t^n f(t)$ forms a Laplace transform pair with $(-1)^n\frac{d^n}{ds^n}F(s)$. The third point is that the Laplace transform of $e^{-at}u(t)$ is $1/(s+a)$ — we knew that — and this works even for complex values of $a$. That was another useful thing we got out of this.

**Part (c).** Now we have the function $h_3(t) = 10t^3e^{-2t}u(t)$. One way we could do this is to look directly at Table 12-2 in Ulaby, and we can actually read off the result pretty much directly from the table. From Table 12-2, entry number 8 of Ulaby et al., we can see directly that $t^{n-1}e^{-at}u(t)$ — if you look at that you can see that's pretty much directly the form of this with $n=4$ — forms a Laplace transform pair with $(n-1)!/(s+a)^n$. Here $n = 4$. So we could just take that result and use it directly: $H_3(s) = 10\cdot\frac{3!}{(s+2)^4}$, since $a = 2$ and $n = 4$. $3! = 3\times 2\times 1 = 6$, so $6\times 10 = 60$, divided by $(s+2)^4$. So this is the answer, but it's perhaps not quite as instructive to just read it off the table. We can actually derive this result using frequency differentiation, and in fact this will allow us to see how this entry in the table comes about.

So we're going to take our basic function $f_1(t) = e^{-2t}u(t)$; then its Laplace transform is $F_1(s) = 1/(s+2)$. Then we need to multiply this by $t^3$, and that will allow us to use the frequency differentiation property, which in the previous part we derived for arbitrary powers of $t$ and correspondingly arbitrary orders of differentiation: $t^n f(t)$ forms a Laplace transform pair with $(-1)^n\frac{d^n}{ds^n}F(s)$. We'll let $f_2(t) = t^3e^{-2t}u(t) = t^3 f_1(t)$. Using this generalized frequency differentiation property, $F_2(s) = (-1)^3\frac{d^3}{ds^3}\frac{1}{s+2}$. It's relatively easy to take successive derivatives of $1/(s+2)$. If we take one derivative explicitly, we have $(-1)^3\frac{d^2}{ds^2}$ of $-\frac{1}{(s+2)^2}$. Then we can take one more derivative, and we'll also pull the $-1$ outside: $(-1)^3(-1)\frac{d}{ds}$ of the derivative of $\frac{1}{(s+2)^2}$, which is $\frac{-2}{(s+2)^3}$. Then we pull this $-2$ out in front and take the final derivative with respect to $s$ of $\frac{1}{(s+2)^3}$: we get $(-1)^3(-1)(-2)\cdot\frac{-3}{(s+2)^4}$. So this is $(-1)^3(-1)(-2)(-3)/(s+2)^4$. We see that all the minus signs cancel out — and they always will — so we just get $3!/(s+2)^4$, which is $6/(s+2)^4$. Just seeing how this worked out, you can start to see, or hopefully completely see, where this $(n-1)!$ comes from and why this is $(s+a)^n$.

Then the last step is just to multiply by our overall constant factor in $h_3$, which was 10. So $H_3(s) = 10F_2(s)$, or, plugging in $F_2(s)$ explicitly, $60/(s+2)^4$ — the same thing we got reading directly from the table, but with a little more explanation, where you can see how it can be arrived at from what we had derived previously.

**Part (d).** Now we have the function $h_4(t) = 5(t-6)u(t-3)$. Here the new twist is that we have two different time shifts: by 6 over here and by 3 over here. But actually we don't have to think of this as a time shift at all. We can just think of this as two terms, and the 6 is just a constant. So we can write $h_4(t) = 5t\,u(t-3) - 30u(t-3)$. From here — step 0, our usual step 0 — what is the basic function we want to start with? It's really just the unit step function. So $f_1(t)$ we'll take to be $u(t-3)$, and reading from the table in Ulaby we know the corresponding Laplace transform is $e^{-3s}/s$. We could also arrive at that by recognizing that the Laplace transform of just $u(t)$ is $1/s$, and then using the time shift property, which gives the additional factor of $e^{-3s}$. Either way is fine. Then for the first term, since we have this additional factor of $t$, we know we can use the simple first-order frequency differentiation property: $t\,f(t)$ forms a Laplace transform pair with $-\frac{d}{ds}F(s)$. Using that we can pretty much immediately figure out the Laplace transform of $h_4(t)$: $H_4(s)$ for the first term is $-5\frac{d}{ds}$ of the Laplace transform of $u(t-3)$, which is $e^{-3s}/s$; and then for the second term we just have $-30$ times the Laplace transform of $u(t-3)$, which is $e^{-3s}/s$.

Now we just have to work this out. For the first term, $-5$ times the derivative of $e^{-3s}/s$: using the quotient rule, the derivative is $\frac{-3s\,e^{-3s} - e^{-3s}}{s^2}$. We carry over the second term, $-30e^{-3s}/s$. If we separate out the terms, from the first we get $-5\times -3 = 15$, $e^{-3s}$, and $s/s^2$ is just $s$ in the denominator; then $+5$ (that's $-5\times -1$) times $e^{-3s}/s^2$; then carrying down the last term, $-30e^{-3s}/s$. The first and third terms work out to $-15e^{-3s}/s$. So we can pull out an overall factor of $5e^{-3s}$, and then we have $1/s^2$ from the middle term and, from the combination of the other two, $-3/s$. That's the answer: $H_4(s) = 5e^{-3s}\left(\frac{1}{s^2} - \frac{3}{s}\right)$. That was a relatively simple example.

**Part (e).** Now we'll go to part (e), which is to compute the Laplace transform of $h_5(t) = 10e^{-3t}u(t-4)$. Again, what's the basic function we want to start with? It's going to be an exponential times the unit step function. So let $f_1(t) = e^{-3t}u(t)$; then its Laplace transform is $F_1(s) = 1/(s+3)$. How do we make use of that, given that we have $u(t-4)$ over here? Let's rewrite things slightly. We can write $h_5(t) = 10e^{-3t}u(t-4)$. But we can equally well write that as $10$, and then we'll introduce a factor of $e^{-12}$, which will then allow us to write $e^{-3(t-4)}$. We've multiplied by $e^{-12}$, and then through this 4 over here, $e^{+12}$, so that's just multiplying by one. Times $u(t-4)$. We can write this now as $10e^{-12}$ times — this product $e^{-3(t-4)}u(t-4)$ is just $f_1(t-4)$. And then we can multiply by $u(t-4)$ again, because that doesn't change anything. So it's $10e^{-12}f_1(t-4)u(t-4)$. Once we've done that, that allows us to use the time shift property to determine the Laplace transform of $f_1(t-4)u(t-4)$. The time shift property is that $f(t-T)u(t-T)$ forms a Laplace transform pair with $e^{-sT}F(s)$ — we used that also in one of the earlier parts. So the Laplace transform of $h_5(t)$, $H_5(s)$, is $10e^{-12}e^{-4s}$ times the Laplace transform of our original function $f_1$, and $F_1(s) = 1/(s+3)$. So $H_5(s) = 10e^{-12}e^{-4s}/(s+3)$, or, if we work out the numerical value for $10e^{-12}$, it's $6.14\times 10^{-5}\,e^{-4s}/(s+3)$. That's the answer for part (e).

There's one additional point we can note here. If we think about what we did in this problem, we deliberately introduced an additional time shift over here, because that then allowed us to use the time shift property of Laplace transforms. It may have looked like we were making things a little more complicated, but that was actually a route to making it more tractable. So in this case a time shift, or more generally potentially other modifications, can be deliberately introduced to enable the very useful properties of Laplace transforms to be applied. Here we did this so that we could use the time shift property.

**Part (f).** Now we are at last at part (f), the last part of this example. We have a time domain function $h_6(t) = 4e^{-2(t-3)}u(t-4)$. The idea here is actually pretty similar to what we did in part (e): we're going to introduce an additional time shift so that we can use the time shift property. The basic function we'll be working with is again an exponential, $f_1(t) = e^{-2t}u(t)$, and $F_1(s) = 1/(s+2)$. We have $h_6(t) = 4e^{-2(t-3)}u(t-4)$. What we want is to have the same time shift in the unit step function and in the exponential function. So we'll have $4e^{-2}$ times $e^{-2(t-4)}$ — we've multiplied by $e^{-2}$ over here, and by changing this from 3 to 4 we multiplied by $e^{+2}$ — times $u(t-4)$. So this is $4e^{-2}$ times our function $f_1$, but now time shifted: $f_1(t-4)$. We can multiply, as we did before, by the unit step function without changing anything: $4e^{-2}f_1(t-4)u(t-4)$. From here we can use the time shift property, that $f(t-T)u(t-T)$ forms a Laplace transform pair with $e^{-sT}F(s)$. Finally that gives us $H_6(s) = 4e^{-2}$ times $e^{-4s}$ — that's the time shift factor — times $F_1(s)$, which from up here is $1/(s+2)$. So $H_6(s) = 4e^{-2}e^{-4s}/(s+2)$, and if we calculate numerically, $4e^{-2}$ is $0.5413$, so $0.5413\,e^{-4s}/(s+2)$. That is the result for this last part of this example, and that completes the solutions to Ulaby problem 12.5. I will stop the recording now.

### Key points (instructor retrospective)

The retrospectives in this video are delivered after each part rather than in a single closing segment; they are collected here.

After part (a):
- Start with a basic Laplace transform result (here $e^{-3t}u(t)\leftrightarrow 1/(s+3)$), something you know or can look up in the table.
- Use Laplace transform properties in succession: time shift (introduces an $e^{-Ts}$ factor), then frequency differentiation (multiplying by $t$ in time is $-d/ds$ in $s$), then multiplication by the constant.
- $u(t) = u^2(t) = u^n(t)$: multiplying by the unit step again changes nothing, which lets you put a shifted function into the exact form the time-shift property requires.

After part (b):
- Again: start with a basic result (the complex exponential) and build on it using properties of LTs and other mathematical tools (Euler's identity to write sine as complex exponentials, frequency differentiation, multiply by constant).
- Frequency differentiation generalizes: $t^n f(t)\leftrightarrow(-1)^n\frac{d^n}{ds^n}F(s)$.
- $\mathcal{L}[e^{-at}u(t)] = 1/(s+a)$ holds even for complex $a$.

After part (c):
- The Table 12-2 entry $t^{n-1}e^{-at}u(t)\leftrightarrow(n-1)!/(s+a)^n$ can be derived by repeated frequency differentiation; the minus signs always cancel, which is where the $(n-1)!$ and the power $n$ come from.

After part (e):
- Time shifts (or other modifications) can be deliberately introduced — e.g. factoring $e^{-12}$ out of $e^{-3t}$ to make the exponential's shift match the step's shift — to enable a useful property (time-shift) to be applied. It looks like a complication but makes the problem tractable.

## Index terms

Ulaby 12.5, Problem 12.5, Laplace transform, forward Laplace transform, Table 12-1, Table 12-2, time-shift property, frequency differentiation property, property #9, Table 12-2 entry #8, unit step function, u(t), u^n(t) = u(t), exponential times unit step, 1/(s+a), complex a, complex exponential, Euler identity, sin(6t-60°), sine as complex exponentials, common denominator, s^2+36, quotient rule, product rule, t^n f(t), (-1)^n d^n/ds^n F(s), t^{n-1} e^{-at} u(t), (n-1)!/(s+a)^n, 3!, factorial, e^{-4s}, e^{-3s}, e^{-12}, e^{-2}, deliberately introduced time shift, multiply by constant, h1(t), h2(t), h3(t), h4(t), h5(t), h6(t), H1(s), H2(s), H3(s), H4(s), H5(s), H6(s), 12 t e^{-3(t-4)} u(t-4), 27 t^2 sin(6t-60°) u(t), 10 t^3 e^{-2t} u(t), 5(t-6) u(t-3), 10 e^{-3t} u(t-4), 4 e^{-2(t-3)} u(t-4), 60/(s+2)^4, 6.14e-5, 0.5413, -46.77 s^3 + 486 s^2 + 5051 s - 5832, sin 60° = √3/2, cos 60° = 1/2, Prof. Ed Yu, problem solving video, Chapter 12
