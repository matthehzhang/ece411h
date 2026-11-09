---
course: ECE 411H
kind: problem-video
source: Problem Solving Videos/Ulaby 12.10.pdf
source_pages: 8
author: Prof. Ed Yu
unit: exam2
topics: [inverse-laplace-transform, partial-fractions, residues, repeated-poles, complex-poles, textbook-solution-error, table-12-2, ulaby-12.10]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
deepgram_transcript: deepgram/Ulaby_12.10.deepgram.txt
deepgram_paragraphs: deepgram/Ulaby_12.10.deepgram.md
---

# Ulaby 12.10 — Computing inverse Laplace transforms (four functions)

**Summary.** Prof. Yu works Ulaby/Maharbiz/Furse Problem 12.10: find the inverse Laplace transform of four rational functions $F_1$–$F_4$. The uniform procedure is (0) find the poles and their orders (including complex ones via the quadratic formula), (1) write the partial-fraction form, (2) compute the residues (simple poles by cover-up; repeated poles by $\frac{1}{(m-k)!}\frac{d^{m-k}}{ds^{m-k}}$), (3) invert term-by-term with Table 12-2 ($e^{-at}u(t)\leftrightarrow 1/(s+a)$, $t^{n-1}e^{-at}u(t)\leftrightarrow(n-1)!/(s+a)^n$). Part (a) has a triple pole at $s=-1$; the instructor pastes the textbook's "official" solution, shows it omits the $\tfrac12$ factor in the second-derivative residue (gives $-8$ instead of $-4$), and verifies by evaluating $F_1(1)=9/8$ both ways. Parts (b)–(d) have complex-conjugate poles and recombine $e^{\pm j\omega t}$ into $\sin$/$\cos$. Exam relevance: this is the full inverse-LT / partial-fraction procedure needed for every Chapter 12 circuit problem.

> **Audio transcript (Deepgram nova-3, ECE 411 keyterms, timestamped):** `deepgram/Ulaby_12.10.deepgram.txt` ; paragraph form: `deepgram/Ulaby_12.10.deepgram.md`. Fresh ASR of the video audio; where it disagrees with the Narration section (built from the published auto-captions), prefer this file and the handwritten page.

## Problem statement

**12.10** Obtain the inverse Laplace transform of each of the following functions.

- (a) $F_1(s) = \dfrac{(s+2)^2}{s(s+1)^3}$
- (b) $F_2(s) = \dfrac{1}{(s^2+4s+5)^2}$
- *(c) $F_3(s) = \dfrac{\sqrt{2}(s+1)}{s^2+6s+13}$
- (d) $F_4(s) = \dfrac{-2(s^2+20)}{s(s^2+8s+20)}$

(Pasted as a textbook image at the top of page 1; asterisk is the textbook's mark on (c).)

## Page 1

Header (typed): "Ulaby 12.10". Textbook problem image (as above). Handwritten title, underlined: **Example: computing inverse Laplace transforms.**

a) $F_1(s) = \dfrac{(s+2)^2}{s(s+1)^3}$

1) Expand $F_1(s)$ using partial fractions:
$$F_1(s) = \frac{k_1}{s} + \frac{l_1}{s+1} + \frac{l_2}{(s+1)^2} + \frac{l_3}{(s+1)^3}$$

2) Compute coefficients $k_1, l_i$:

$$k_1 = \left[sF_1(s)\right]\Big|_{s=0} = \frac{(0+2)^2}{(0+1)^3} = 4$$

$$l_3 = \left[(s+1)^3F_1(s)\right]\Big|_{s=-1} = \frac{(-1+2)^2}{(-1)} = -1$$

$$l_2 = \left[\frac{d}{ds}\left((s+1)^3F_1(s)\right)\right]\Bigg|_{s=-1} = \left[\frac{d}{ds}\left(\frac{(s+2)^2}{s}\right)\right]\Bigg|_{s=-1}$$
$$= \left[\frac{2(s+2)s - (s+2)^2}{s^2}\right]\Bigg|_{s=-1} = \frac{-2-1}{1} = -3$$

$$l_1 = \frac{1}{2}\left[\frac{d^2}{ds^2}\left((s+1)^3F_1(s)\right)\right]\Bigg|_{s=-1} = \frac{1}{2}\left[\frac{d}{ds}\left(\frac{s^2-4}{s^2}\right)\right]\Bigg|_{s=-1}$$

(last line clipped at page bottom; continued at top of page 2)

## Page 2

$$= \frac{1}{2}\left[\frac{d}{ds}\left(1 - \frac{4}{s^2}\right)\right]\Bigg|_{s=-1} = \frac{1}{2}\left(\frac{+8}{s^3}\right)\Bigg|_{s=-1} = -4$$

$$\Rightarrow F_1(s) = \frac{4}{s} - \frac{4}{s+1} - \frac{3}{(s+1)^2} - \frac{1}{(s+1)^3}$$

Red-ink annotation to the right of this line, with a check mark:
$$\rightarrow F_1(1) = 4 - 2 - \tfrac{3}{4} - \tfrac{1}{8} = 2 - \tfrac{7}{8} = \tfrac{9}{8}\ \checkmark$$

From the "official" solutions: (pasted image of the textbook solution manual, transcribed verbatim below)

> $$\mathbf{F}_1(\mathbf{s}) = \frac{(\mathbf{s}+2)^2}{\mathbf{s}(\mathbf{s}+1)^3} = \frac{A}{\mathbf{s}} + \frac{B_3}{(\mathbf{s}+1)^3} + \frac{B_2}{(\mathbf{s}+1)^2} + \frac{B_1}{\mathbf{s}+1},$$
> with
> $$A = \mathbf{s}\,\mathbf{F}_1(\mathbf{s})\big|_{\mathbf{s}=0} = \frac{(\mathbf{s}+2)^2}{(\mathbf{s}+1)^3}\Big|_{\mathbf{s}=0} = 4,$$
> $$B_3 = (\mathbf{s}+1)^3\,\mathbf{F}_1(\mathbf{s})\big|_{\mathbf{s}=-1} = \frac{(\mathbf{s}+2)^2}{\mathbf{s}}\Big|_{\mathbf{s}=-1} = -1,$$
> $$B_2 = \frac{d}{d\mathbf{s}}\left[\frac{(\mathbf{s}+2)^2}{\mathbf{s}}\right]\Big|_{\mathbf{s}=-1} = \frac{2(\mathbf{s}+2)}{\mathbf{s}} - \frac{(\mathbf{s}+2)^2}{\mathbf{s}^2}\Big|_{\mathbf{s}=-1} = -3,$$
> $$B_1 = \frac{d}{d\mathbf{s}}\left[\frac{2(\mathbf{s}+2)}{\mathbf{s}} - \frac{(\mathbf{s}+2)^2}{\mathbf{s}^2}\right]\Big|_{\mathbf{s}=-1}$$
> $$= \left[\frac{2}{\mathbf{s}} - \frac{2(\mathbf{s}+2)}{\mathbf{s}^2} - \frac{2(\mathbf{s}+2)}{\mathbf{s}^2} + \frac{2(\mathbf{s}+2)^2}{\mathbf{s}^3}\right]\Big|_{\mathbf{s}=-1} = -8.$$
> Hence,
> $$\mathbf{F}_1(\mathbf{s}) = \frac{4}{\mathbf{s}} - \frac{1}{(\mathbf{s}+1)^3} - \frac{3}{(\mathbf{s}+1)^2} - \frac{8}{\mathbf{s}+1},$$

Handwritten marks on the pasted image:
- The term $\frac{B_1}{s+1}$ in the first line is circled; a red arrow from it leads to the red note $F_1(1) = \dfrac{(1+2)^2}{1(1+1)^3} = \dfrac{9}{8}$.
- Black handwritten "missing ½" with an arrow pointing at "$B_1 = \frac{d}{ds}$" (i.e. the second-derivative residue should carry a factor $\tfrac{1}{2}$).
- The final term $-\frac{8}{s+1}$ in the "Hence" line is circled; a red arrow leads to the red note $F_1(1) = 4 - \tfrac{1}{8} - \tfrac{3}{4} - 4 = \tfrac{-7}{8}\ ?!$
- The "Hence" result is underlined.

3) Compute inverse LT:
From Table 12-2 of Ulaby et al., we have:
$$e^{-at}u(t) \leftrightarrow \frac{1}{s+a},\ \text{incl. } a = 0,\ \text{i.e.,}\ u(t) \leftrightarrow \frac{1}{s}$$
$$t^{n-1}e^{-at}u(t) \leftrightarrow \frac{(n-1)!}{(s+a)^n}$$

(boxed result clipped at page bottom; shown at top of page 3)

## Page 3

$$\Rightarrow \boxed{f_1(t) = \left[4 - 4e^{-t} - 3te^{-t} - \tfrac{1}{2}t^2e^{-t}\right]u(t)}$$

b) $F_2(s) = \dfrac{1}{(s^2+4s+5)^2}$

0) Find poles of $F_2(s)$:
$$s^2+4s+5 = 0 \Rightarrow s = \tfrac{1}{2}\left[-4 \pm \sqrt{16 - 4(5)}\right] = -2 \pm j$$
$$\Rightarrow F_2(s) = \frac{1}{(s+2-j)^2(s+2+j)^2}$$

1) Expand $F_2(s)$ using partial fractions:
$$F_2(s) = \frac{l_1}{s+2-j} + \frac{l_2}{(s+2-j)^2} + \frac{l_1^*}{(s+2+j)} + \frac{l_2^*}{(s+2+j)^2}$$

2) Compute coefficients $l_1, l_2$:

$$l_2 = \left[(s+2-j)^2F_2(s)\right]\Big|_{s=-2+j} = \frac{1}{(-2+j+2+j)^2} = -\frac{1}{4}$$

$$l_1 = \left[\frac{d}{ds}\left((s+2-j)^2F_2(s)\right)\right]\Bigg|_{s=-2+j} = \left[\frac{d}{ds}\left(\frac{1}{(s+2+j)^2}\right)\right]\Bigg|_{s=-2+j}$$
$$= \left[\frac{-2}{(s+2+j)^3}\right]\Bigg|_{s=-2+j} = \frac{-2}{(-2+j+2+j)^3} = \frac{-2}{(j2)^3} = \frac{1}{4j} = \frac{-j}{4}$$

## Page 4

(Top line is the clipped tail of the $l_1$ computation from page 3.)

$$\Rightarrow F_2(s) = \frac{j}{4}\left(\frac{1}{s+2+j} - \frac{1}{s+2-j}\right) - \frac{1}{4}\left(\frac{1}{(s+2+j)^2} + \frac{1}{(s+2-j)^2}\right)$$

3) Compute inverse LT:
From Table 12-2 of Ulaby et al., we have:
$$t^{n-1}e^{-at}u(t) \leftrightarrow \frac{(n-1)!}{(s+a)^n}$$

$$\Rightarrow f_2(t) = \left[\frac{j}{4}\left(e^{-(2+j)t} - e^{-(2-j)t}\right) - \frac{1}{4}t\left(e^{-(2+j)t} + e^{-(2-j)t}\right)\right]u(t)$$
$$= \frac{e^{-2t}}{4}\left[j\underbrace{\left(e^{-jt} - e^{jt}\right)}_{-j2\sin t} - t\underbrace{\left(e^{-jt} + e^{jt}\right)}_{2\cos t}\right]u(t)$$

$$\boxed{f_2(t) = \frac{e^{-2t}}{2}\left[\sin t - t\cos t\right]u(t)}$$

c) $F_3(s) = \dfrac{\sqrt{2}(s+1)}{s^2+6s+13}$

0) Find poles of $F_3(s)$:
$$s^2+6s+13 = 0 \Rightarrow s = \tfrac{1}{2}\left[-6 \pm \sqrt{36 - 4(13)}\right] = -3 \pm j\tfrac{1}{2}\sqrt{16} = -3 \pm j2$$

(next line clipped: "$F_3(s) = \frac{\sqrt2(s+1)}{\ldots}$", continued on page 5)

## Page 5

$$\Rightarrow F_3(s) = \frac{\sqrt{2}(s+1)}{(s+3-j2)(s+3+j2)}$$

1) Expand $F_3(s)$ using partial fractions:
$$F_3(s) = \frac{k_1}{s+3-j2} + \frac{k_1^*}{s+3+j2}$$

2) Compute coefficient $k_1$:
$$k_1 = \left[(s+3-j2)F_3(s)\right]\Big|_{s=-3+j2} = \left[\frac{\sqrt{2}(s+1)}{s+3+j2}\right]\Bigg|_{s=-3+j2}$$
$$= \frac{\sqrt{2}(-3+j2+1)}{-3+j2+3+j2} = \frac{\sqrt{2}(-2+j2)}{j4} = \frac{\sqrt{2}}{2}(1+j) = e^{j45^\circ}$$

$$\Rightarrow F_3(s) = \frac{e^{j45^\circ}}{s+3-j2} + \frac{e^{-j45^\circ}}{s+3+j2}$$

3) Compute inverse LT:
From Table 12-2 of Ulaby et al., we have:
$$e^{-at}u(t) \leftrightarrow \frac{1}{s+a}$$

$$\Rightarrow f_3(t) = \left[e^{j45^\circ}e^{-3t}e^{j2t} + e^{-j45^\circ}e^{-3t}e^{-j2t}\right]u(t)$$
$$= e^{-3t}\underbrace{\left[e^{j(2t+45^\circ)} + e^{-j(2t+45^\circ)}\right]}_{2\cos(2t+45^\circ)}u(t)$$

## Page 6

$$\Rightarrow \boxed{f_3(t) = 2e^{-3t}\cos(2t+45^\circ)\,u(t)}$$

d) $F_4(s) = \dfrac{-2(s^2+20)}{s(s^2+8s+20)}$

0) Find poles of $F_4(s)$:
$$s = 0;\quad s^2+8s+20 = 0 \Rightarrow s = \tfrac{1}{2}\left[-8 \pm \sqrt{64-4(20)}\right] = -4 \pm j\tfrac{1}{2}\sqrt{16} = -4 \pm j2$$
$$\Rightarrow F_4(s) = \frac{-2(s^2+20)}{s(s+4-j2)(s+4+j2)}$$

1) Expand $F_4(s)$ using partial fractions:
$$F_4(s) = \frac{k_1}{s} + \frac{l_1}{s+4-j2} + \frac{l_1^*}{s+4+j2}$$

2) Compute coefficients $k_1, l_1$:
$$k_1 = \left[sF_4(s)\right]\Big|_{s=0} = \frac{-2(0^2+20)}{(0^2+8(0)+20)} = -2.$$
$$l_1 = \left[(s+4-j2)F_4(s)\right]\Big|_{s=-4+j2} = \left[\frac{-2(s^2+20)}{s(s+4+j2)}\right]\Bigg|_{s=-4+j2}$$
$$= \frac{-2\left((-4+j2)^2+20\right)}{(-4+j2)(-4+j2+4+j2)} = \frac{-2(16-j16-4+20)}{(-4+j2)(j4)}$$

(last line clipped; repeated at top of page 7)

## Page 7

$$= \frac{-2(16-j16-4+20)}{(-4+j2)(j4)} = \frac{-2(32-j16)}{-8-j16} = \frac{2(4-j2)}{1+j2}\cdot\left(\frac{1-j2}{1-j2}\right)$$
$$= \frac{2(4-j2)(1-j2)}{1^2+2^2} = \frac{2}{5}\left(4 - j2 - j8 - 4\right) = \frac{2}{5}(-j10) = -j4$$

$$\Rightarrow F_4(s) = \frac{-2}{s} - j4\left(\frac{1}{s+4-j2} - \frac{1}{s+4+j2}\right)$$

3) Compute inverse LT:
From Table 12-2 of Ulaby et al., we have:
$$u(t) \leftrightarrow \frac{1}{s},\qquad e^{-at}u(t) \leftrightarrow \frac{1}{s+a}$$

$$\Rightarrow f_4(t) = \left[-2 - j4\left(e^{-4t}e^{j2t} - e^{-4t}e^{-j2t}\right)\right]u(t)$$
$$= \left[-2 + \frac{4e^{-4t}}{j}\underbrace{\left(e^{j2t} - e^{-j2t}\right)}_{2j\sin 2t}\right]u(t)$$

$$\boxed{f_4(t) = \left[-2 + 8e^{-4t}\sin 2t\right]u(t)}$$

**Key points:** (underlined)

(i) general procedure for computing inverse LTs is to identify poles + orders (including complex poles), expand (continues on page 8)

## Page 8

(i) general procedure for computing inverse LTs is to identify poles + orders (including complex poles), expand using partial fractions, compute partial fraction coefficients, and find inverse LT using standard forms + properties in tables in Ulaby et al.

(ii) published/textbook solutions are not always reliable/correct!

(iii) important to be proficient and accurate in performing complex algebra!

(Rest of page blank.)

## Narration transcript

Cleaned from `Problem Solving Videos/Ulaby 12.10 captions.vtt`: timestamps and cue numbers stripped, fragments merged into sentences, auto-caption mishearings corrected ("polls" → poles, "applause transform" → Laplace transform, "Jay" → $j$, "you'll be at all" → Ulaby et al., "estimate/S domain" → $s$ domain), verbal fillers trimmed. Content is otherwise complete.

So this is problem 12.10, and this is an example of computing inverse Laplace transforms. As you will see, this is mostly a matter of doing partial fraction expansions of these functions shown here, and then using those you can pretty straightforwardly compute the inverse Laplace transform of each of these. So let's go ahead and get started.

**Part (a).** The function for which we want to compute the inverse Laplace transform is $F_1(s) = \dfrac{(s+2)^2}{s(s+1)^3}$. The first step: we can easily see what the poles of this are — they're $s=0$ and $s=-1$. So we can go ahead and directly expand this using partial fractions. The form of this expansion will be $F_1(s) = \frac{k_1}{s} + \frac{l_1}{s+1}$, and you'll notice that we have $(s+1)^3$ in the denominator, so this is a third-order pole, and we're going to have additional coefficients $\frac{l_2}{(s+1)^2} + \frac{l_3}{(s+1)^3}$. Then we have to compute each of these coefficients in order to come up with a full partial fraction expansion.

The way we compute these: remember that for $k_1$, $s=0$ is just a simple pole, so $k_1 = sF_1(s)$ evaluated at $s=0$. If we take $F_1(s)$ and multiply by $s$, that just gets rid of this $s$ in the denominator, so we have $\frac{(s+2)^2}{(s+1)^3}$ evaluated at $s=0$: $\frac{(0+2)^2}{(0+1)^3} = \frac{4}{1} = 4$. So $k_1 = 4$.

Now for the $l$'s. We start with $l_3$. $l_3$, you'll recall, is $(s+1)^3F_1(s)$ evaluated at $s=-1$, the value of the pole. When we multiply $F_1$ by $(s+1)^3$ that gives us $\frac{(s+2)^2}{s}$, so this is $\frac{(-1+2)^2}{-1} = -1$. So $l_3 = -1$.

Now for $l_2$. Remember that the way we compute $l_2$ is that it's the derivative with respect to $s$ of $(s+1)^3F_1(s)$, evaluated at $s=-1$. The way we can see that is by going back to the expression for $F_1$ in partial-fraction form: if we multiply by $(s+1)^3$, then the $k_1$ term is proportional to $(s+1)^3$, the $l_1$ term is proportional to $(s+1)^2$, the $l_2$ term is proportional to $(s+1)$, and the $l_3$ term is a constant. If we then take the derivative with respect to $s$, the constant term's derivative is $0$, the $l_2$ term will just give us $l_2$, and the other two terms will also give us $0$ because after we take the derivative we still have a factor of $(s+1)$ remaining in each of those terms, which goes to zero at $s=-1$. So all we have left is $l_2$; that's why this expression gives us $l_2$. So we take the derivative with respect to $s$ of — when we take $F_1(s)$ from the original expression and multiply by $(s+1)^3$, we get $\frac{(s+2)^2}{s}$ — and evaluate at $s=-1$. This is a quotient, so its derivative is the derivative of the numerator, $2(s+2)$, times the denominator $s$, minus the numerator $(s+2)^2$ times the derivative of the denominator, which is $1$, divided by the denominator squared, $s^2$. Evaluate at $s=-1$: $2\times(-1+2) = 2$, times $-1$ is $-2$; then $(-1+2)^2 = 1$, so minus $1$; divided by $(-1)^2 = 1$. So this is $-3$. That is $l_2$.

Finally we have $l_1$, which is $\frac{1}{2}\frac{d^2}{ds^2}$ of $(s+1)^3F_1(s)$, evaluated at $s=-1$. The reason it works out this way: go back to the partial-fraction expression; if we multiply by $(s+1)^3$ and take two derivatives, the $l_3$ term is a constant and goes to zero on the first derivative; the $l_2$ term is proportional to $(s+1)$ and goes to zero after two derivatives; the $l_1$ term is proportional to $(s+1)^2$, so two derivatives give $2l_1$; the $k_1$ term is proportional to $(s+1)^3$, so after two derivatives we have one factor of $(s+1)$ remaining, which goes to zero at $s=-1$. So we have $2l_1$ through this process, and that's why we need to divide by $2$ — the one-half over here. We already computed one derivative — that was the expression for $l_2$ — so we don't have to compute it again; let's just simplify it. The derivative with respect to $s$ of $(s+1)^3F_1(s)$: in the numerator we have $2s^2$ minus $s^2$, so that's going to be just $s^2$; then we have $2\times 2\times s$, that's $4s$, but then we're going to have $-4s$ over here from squaring, so those cancel out; and then we have $-4$ from the last term, from squaring the $(s+2)$. So it's $\frac{s^2-4}{s^2}$, evaluated at $s=-1$. That is actually easy to simplify even a little more: it's $1 - \frac{4}{s^2}$. So $l_1 = \frac{1}{2}\frac{d}{ds}\left(1-\frac{4}{s^2}\right)$ at $s=-1$. The derivative of $1$ is $0$; the derivative of $-4/s^2$ is $+8/s^3$ (we get $-2$ with the minus sign cancelling, times $4$, that's $8$ over $s^3$). Evaluated at $s=-1$: $8/(-1)^3 = -8$, times $\frac{1}{2}$, gives $-4$.

So now we have our residues: $-4$ for $l_1$, $-3$ for $l_2$, $-1$ for $l_3$, and $4$ for $k_1$. If we substitute those back into the partial fraction expression, we get $F_1(s) = \frac{4}{s} - \frac{4}{s+1} - \frac{3}{(s+1)^2} - \frac{1}{(s+1)^3}$.

Now here there's a useful point to make, which is that if you look at the official solutions to this problem put out by Ulaby et al. — what I'm going to do is go to the other computer and paste it up to this point, where they've computed $F_1(s)$. So now it's showed up here. What you can see is that this is what they've gotten for their solution, and if you compare, it's the same except for this term: they have $-\frac{8}{s+1}$, and we had $-\frac{4}{s+1}$. So what happened here? If you look at the residue they're calculating for $s+1$, it's $B_1$, and you can see there's a missing factor of one-half — and I explained why that factor of one-half has to be in there. So the official solution here has an error.

If you want to check whether the official solution is in error, or whether what we just worked out is in error, one thing you can do — this is not the only way, but a relatively quick check — is to take the original expression and calculate it at $s=1$. If you do that you get $\frac{(1+2)^2}{1\cdot(1+1)^3} = \frac{9}{8}$. So the original expression for $F_1$ at $s=1$ should give $9/8$. Now let's figure out what their expression gives. $4/1 = 4$; $-1/(1+1)^3 = -1/8$; $-3/(1+1)^2 = -3/4$; $-8/(1+1) = -4$. So $4 - 4$ cancel, and we have $-1/8 - 3/4 = -1/8 - 6/8 = -7/8$. That is not the same as what we calculated, so this cannot be correct. If you go back to what we calculated and evaluate at $s=1$: $4/1 = 4$; $-4/2 = -2$; $-3/2^2 = -3/4$; $-1/2^3 = -1/8$. That's $2 - 3/4 - 1/8 = 2 - 7/8 = 9/8$. So that's actually correct, and we can move forward with pretty good confidence that this is the correct expression for $F_1(s)$. You should not have access to these solutions, but perhaps some of you may, and in this case the answer in the official solutions is not correct.

With that little digression, we can take this expression for $F_1(s)$ and use it to compute the inverse Laplace transform. That's the third step. Now that we have the partial fraction expansion, that's relatively easy, because if we look at Table 12-2 of Ulaby et al., you can see that $e^{-at}u(t)$ forms a Laplace transform pair with $\frac{1}{s+a}$, and that includes the case $a=0$, which is $u(t)\leftrightarrow\frac{1}{s}$. And since we have higher-order poles, we also need the entry $t^{n-1}e^{-at}u(t)\leftrightarrow\frac{(n-1)!}{(s+a)^n}$. If we just use these results, we can see essentially immediately, with very little work, that $f_1(t)$ is: the inverse Laplace transform of $4/s$ is $4u(t)$ — we'll write the $u(t)$ at the end since every term will have a factor of $u(t)$; from $-4/(s+1)$ we get $-4e^{-t}$; from $-3/(s+1)^2$ we use the entry with $n=2$, and $(2-1)! = 1$, so we don't have to worry about it: $-3te^{-t}$; and finally from $-1/(s+1)^3$ we have $t^2e^{-t}$ but with $(3-1)! = 2$ which has to be brought over to the other side as one-half: $-\frac{1}{2}t^2e^{-t}$. All of this times $u(t)$. This is the result for part (a).

**Part (b).** We have $F_2(s) = \dfrac{1}{(s^2+4s+5)^2}$. Here we want to find explicitly what the poles are; we have to do a little work, at a minimum in our head, but we'll work it out explicitly to find the roots of this quadratic in the denominator. So the first step is to find the poles: we look for the values of $s$ for which $s^2+4s+5 = 0$. By the quadratic formula, $s = \frac{1}{2}\left[-4 \pm \sqrt{16 - 20}\right]$. This is $-2$ (that's $-4/2$) plus or minus — the discriminant is negative, so we have $j$ times $\frac{1}{2}\sqrt{20-16} = \frac{1}{2}\cdot 2 = 1$ — so $-2\pm j$. Those are the roots, so we can write $F_2(s) = \dfrac{1}{(s+2-j)^2(s+2+j)^2}$ — the same function.

Once we have $F_2$ in this form, we can do the expansion using partial fractions. The form will be $F_2(s) = \frac{l_1}{s+2-j} + \frac{l_2}{(s+2-j)^2}$, because this is a second-order pole, plus the terms for the other second-order pole. Because the roots are complex conjugates of each other, the residues will just be the complex conjugates of $l_1$ and $l_2$: $+\frac{l_1^*}{s+2+j} + \frac{l_2^*}{(s+2+j)^2}$. So really we just have to compute $l_1$ and $l_2$; their complex conjugates are trivial to compute.

The procedure is the same as in part (a); it still works even when the roots are complex. $l_2 = (s+2-j)^2F_2(s)$ evaluated at $s=-2+j$. Multiplying by $(s+2-j)^2$ gets rid of that factor in the denominator, so we have $\frac{1}{(s+2+j)^2}$ at $s=-2+j$: $\frac{1}{(-2+j+2+j)^2}$. The $-2$ and $2$ cancel, so we have $(2j)^2 = -4$, so $l_2 = -\frac{1}{4}$. For $l_1$, it's the derivative with respect to $s$ of $(s+2-j)^2F_2(s)$ at $s=-2+j$, which is $\frac{d}{ds}\frac{1}{(s+2+j)^2}$ at $s=-2+j$. That derivative is $\frac{-2}{(s+2+j)^3}$, evaluated at $s=-2+j$: $\frac{-2}{(-2+j+2+j)^3} = \frac{-2}{(j2)^3}$. In the denominator we have $-j8$, so this is $\frac{1}{4j}$, or $-\frac{j}{4}$. That's $l_1$.

Then we take what we've calculated for $l_1$ and $l_2$ and their complex conjugates — for $l_2$ the complex conjugate is the same; for $l_1$ the complex conjugate is $+\frac{j}{4}$ — and substitute into the expansion. We get $F_2(s) = \frac{j}{4}\left(\frac{1}{s+2+j} - \frac{1}{s+2-j}\right)$ — that's from the $l_1$ and $l_1^*$ terms; we just switched the order so the minus sign goes on the $s+2-j$ term — $-\frac{1}{4}\left(\frac{1}{(s+2+j)^2} + \frac{1}{(s+2-j)^2}\right)$, from $l_2$ and $l_2^*$.

From this we calculate the inverse Laplace transform by looking at the appropriate entries in Table 12-2. The relevant entry is $t^{n-1}e^{-at}u(t)\leftrightarrow\frac{(n-1)!}{(s+a)^n}$, and this includes the case $n=1$, because $0!$ is defined to be $1$. Using this, $f_2(t)$ is — there's a factor of $u(t)$ we'll write at the end — $\frac{j}{4}$ times, for the inverse transforms of $\frac{1}{s+2+j}$ and $\frac{1}{s+2-j}$ we set $n=1$, which gives just $e^{-at}$: $e^{-(2+j)t} - e^{-(2-j)t}$; here $a = 2+j$ for the first and $a = 2-j$ for the second. Then from the two second-order terms, $-\frac{1}{4}t$ — now $n=2$, numerator is $1! = 1$, and in the time domain we have $te^{-at}$ — $\left(e^{-(2+j)t} + e^{-(2-j)t}\right)$. All times $u(t)$.

Now we can simplify. Every term has a factor of $e^{-2t}$ and a factor of $\frac{1}{4}$, so pull out $\frac{e^{-2t}}{4}$. From the first set of terms we get $j\left(e^{-jt} - e^{jt}\right)$, and from the second set $-t\left(e^{-jt} + e^{jt}\right)$. But $e^{-jt} - e^{jt}$ is actually $-j2\sin t$ — because the order is reversed: $\sin t = \frac{e^{jt} - e^{-jt}}{2j}$ — and $e^{-jt}+e^{jt} = 2\cos t$. Making those substitutions: $j\times(-j) = 1$, so we have a $2$ here and a $2$ there; pulling both out, $2/4 = 1/2$. So finally $f_2(t) = \frac{e^{-2t}}{2}\left[\sin t - t\cos t\right]u(t)$. That's the answer for part (b).

**Part (c).** We have $F_3(s) = \dfrac{\sqrt{2}(s+1)}{s^2+6s+13}$. Again, first we want to explicitly identify the poles — there are two, the roots of the quadratic. Set $s^2+6s+13 = 0$; by the quadratic formula $s = \frac{1}{2}\left[-6\pm\sqrt{36 - 52}\right]$. This is $-3$ plus or minus $j$ — the discriminant $36-52 = -16$ is negative — times $\frac{1}{2}\sqrt{16} = 2$. So $s = -3\pm j2$. That means we can write $F_3(s) = \dfrac{\sqrt{2}(s+1)}{(s+3-j2)(s+3+j2)}$, which makes the poles explicit.

Then we expand using partial fractions: $F_3(s) = \frac{k_1}{s+3-j2} + \frac{k_1^*}{s+3+j2}$. So we only have to compute one coefficient. $k_1 = (s+3-j2)F_3(s)$ at $s=-3+j2$. Multiplying by $(s+3-j2)$ gets rid of the first factor in the denominator; then we evaluate what's left: $\frac{\sqrt{2}(s+1)}{s+3+j2}$ at $s=-3+j2$. Plug in: $\sqrt{2}(-3+j2+1)$ in the numerator, and $-3+j2+3+j2$ in the denominator. Numerator: $\sqrt{2}(-2+j2)$. Denominator: $-3+3 = 0$, and $j2+j2 = j4$. Cancel a factor of $2$ from numerator and denominator, and divide the two terms by $j$: we get $\frac{\sqrt{2}}{2}$, then $j\cdot\frac{1}{j} = 1$ and $-\frac{1}{j} = j$, so $(1+j)$. So $k_1 = \frac{(1+j)}{\sqrt{2}}$, and that is just $e^{j45^\circ}$. So $F_3(s) = \frac{e^{j45^\circ}}{s+3-j2} + \frac{e^{-j45^\circ}}{s+3+j2}$, with $k_1^* = e^{-j45^\circ}$.

Now we compute the inverse Laplace transform, which is pretty straightforward because these are just simple poles; from Table 12-2, $e^{-at}u(t)\leftrightarrow\frac{1}{s+a}$, which we've used many times now. So $f_3(t)$: from the first term, $e^{j45^\circ}$ times $e^{-at}$ where $a = 3-j2$, so $e^{-3t}e^{j2t}$; from the second term $e^{-j45^\circ}e^{-3t}e^{-j2t}$; all times $u(t)$. From both terms we can pull out $e^{-3t}$, leaving $e^{j(2t+45^\circ)} + e^{-j(2t+45^\circ)}$, and you can see that's just $2\cos(2t+45^\circ)$. So finally $f_3(t) = 2e^{-3t}\cos(2t+45^\circ)u(t)$. That's the final result for part (c).

**Part (d).** Finally we compute the inverse Laplace transform of $F_4(s) = \dfrac{-2(s^2+20)}{s(s^2+8s+20)}$. Again, the first step is to find the poles, the values of $s$ for which the denominator goes to zero. From the factor of $s$, obviously one pole is $s=0$; the other poles correspond to $s^2+8s+20 = 0$. By the quadratic formula, $s = \frac{1}{2}\left[-8\pm\sqrt{64-80}\right]$, so $-4$ plus or minus $j$ times $\frac{1}{2}\sqrt{16} = 2$: $s = -4\pm j2$. So $F_4(s) = \dfrac{-2(s^2+20)}{s(s+4-j2)(s+4+j2)}$.

With $F_4$ in this form, we expand using partial fractions as usual: for the pole at $s=0$ we have $\frac{k_1}{s}$, and for the other two poles $\frac{l_1}{s+4-j2} + \frac{l_1^*}{s+4+j2}$, because those poles are complex conjugates and therefore their residues are too. These are all simple poles. Now we compute $k_1$ and $l_1$; $l_1^*$ is trivial. $k_1$, the residue at $s=0$, is $sF_4(s)$ at $s=0$: multiplying by $s$ cancels the $s$ in the denominator, and we evaluate the rest at $s=0$: $\frac{-2(0+20)}{0+0+20} = -2$. Then $l_1 = (s+4-j2)F_4(s)$ at $s=-4+j2$: $\frac{-2(s^2+20)}{s(s+4+j2)}$ at $s=-4+j2$. We get $-2\left((-4+j2)^2+20\right)$ over $(-4+j2)(-4+j2+4+j2)$. In the numerator, $(-4+j2)^2 = 16 - j16 - 4$ (the $16$ from $(-4)^2$, $-j16$ from the cross terms, $-4$ from $(j2)^2$), plus $20$. The denominator: $(-4+j2)$ times, from the second factor, $-4+4 = 0$ and $j2+j2 = j4$. Continuing: numerator $-2(16-4+20 - j16) = -2(32-j16)$; denominator $j2\cdot j4 = -8$ and $-4\cdot j4 = -j16$, so $-8-j16$. Cancel a factor of $8$ (really $-8$) from numerator and denominator: $\frac{2(4-j2)}{1+j2}$. To simplify further, multiply numerator and denominator by the complex conjugate of the denominator, $\frac{1-j2}{1-j2}$: we get $\frac{2(4-j2)(1-j2)}{1^2+2^2}$, so $\frac{2}{5}$ times the product: $4\cdot 1 = 4$; $-j2\cdot 1 = -j2$; $4\cdot(-j2) = -j8$; $(-j2)(-j2) = -4$. So $\frac{2}{5}(4 - j2 - j8 - 4) = \frac{2}{5}(-j10) = -j4$. So the residue $l_1 = -j4$.

Then $F_4(s) = \frac{-2}{s}$ (that's $k_1/s$) $- j4\left(\frac{1}{s+4-j2} - \frac{1}{s+4+j2}\right)$, because when we take the complex conjugate of $l_1$, since it's imaginary, it gives a minus sign. From this we compute the inverse Laplace transform. From Table 12-2, $u(t)\leftrightarrow\frac{1}{s}$ — actually a special case of $e^{-at}u(t)\leftrightarrow\frac{1}{s+a}$ with $a=0$. So $f_4(t)$: the inverse transform of $-2/s$ is $-2u(t)$; then $-j4\left(e^{-4t}e^{j2t} - e^{-4t}e^{-j2t}\right)$; all times $u(t)$. Simplifying: $-j4$ is the same as $+\frac{4}{j}$, and pulling $e^{-4t}$ out front, $-2 + \frac{4e^{-4t}}{j}\left(e^{j2t} - e^{-j2t}\right)$. The parenthesis is $2j\sin 2t$; the $j$'s cancel, so finally $f_4(t) = \left[-2 + 8e^{-4t}\sin 2t\right]u(t)$, because it's $4\times 2$. This is the final result.

So now we're finished working out this example.

### Key points (instructor retrospective)

What are some of the key points, looking at this retrospectively? What you've now seen four times in this example is that the general procedure for computing inverse Laplace transforms is to identify the poles, if they're not obvious — that includes complex poles — and then identify correctly the order of those poles. Then expand your function in the $s$ domain using partial fractions, compute the partial fraction coefficients or residues, and then, once you have the partial fraction expansion, it's easy to find the inverse Laplace transform using the standard forms in Ulaby et al. So the general procedure for computing inverse Laplace transforms is: first identify the poles and their orders, including complex poles; then expand the function in the $s$ domain using partial fractions (we saw many examples of how to do that here); compute the partial fraction coefficients, which we can also refer to as residues; and finally find the inverse Laplace transform using the standard forms, and sometimes other properties, that we have in the tables in Ulaby et al. Those tables are also in a handout that you have gotten or will get, depending on when you are watching this.

The second point is that, as we saw in part (a), even if you have access to the published or textbook solutions, you cannot always count on their correctness. The published or textbook solutions are not always reliable or correct. Sometimes your solutions may not be correct either. We saw one instance, which I pointed out in part (a), of one way you can do a quick check to see if your solution or the published solution is correct. If you get something inconsistent, you know that something somewhere is not correct. If you get something consistent, it increases the likelihood, actually by quite a lot, that it is correct. So being on the lookout generally for mistakes, both in what you see elsewhere and in what you're doing yourself, is something that is useful and worthwhile to develop as a habit.

Finally, we saw through many examples as well that it's important to be proficient and accurate in performing complex algebra. That is everything for this example, and I will now stop the recording.

## Index terms

Ulaby 12.10, Problem 12.10, inverse Laplace transform, partial fraction expansion, residues, partial fraction coefficients, simple pole, repeated pole, third-order pole, second-order pole, complex poles, complex-conjugate poles, complex-conjugate residues, cover-up method, derivative method for repeated poles, 1/2 d²/ds² factor, missing ½, official solution error, textbook solution error, check by evaluating F(1), 9/8, -7/8, quadratic formula, discriminant, Table 12-2, e^{-at} u(t) ↔ 1/(s+a), u(t) ↔ 1/s, t^{n-1} e^{-at} u(t) ↔ (n-1)!/(s+a)^n, 0! = 1, Euler identity, sin t = (e^{jt} - e^{-jt})/2j, cos t = (e^{jt}+e^{-jt})/2, e^{j45°}, (1+j)/√2, rationalizing complex denominator, complex algebra, F1(s), F2(s), F3(s), F4(s), f1(t), f2(t), f3(t), f4(t), (s+2)^2/(s(s+1)^3), 1/(s^2+4s+5)^2, √2(s+1)/(s^2+6s+13), -2(s^2+20)/(s(s^2+8s+20)), 4 - 4e^{-t} - 3t e^{-t} - ½ t² e^{-t}, (e^{-2t}/2)(sin t - t cos t), 2 e^{-3t} cos(2t+45°), -2 + 8 e^{-4t} sin 2t, poles -2±j, -3±j2, -4±j2, k1, l1, l2, l3, A, B1, B2, B3, Prof. Ed Yu, problem solving video, Chapter 12
