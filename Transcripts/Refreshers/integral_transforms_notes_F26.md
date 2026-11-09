---
course: ECE 411H
kind: refresher-notes
source: Refreshers/ECE_411H_integral-transforms_notes_F26.pdf
source_pages: 5
author: Prof. Ed Yu
unit: exam2
topics: [integral-transforms, fourier-series, fourier-transform, laplace-transform, complex-frequency, basis-functions, orthogonality, superposition, periodic-signals, convergence, region-of-convergence, phasors, initial-conditions]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
deepgram_transcript: deepgram/ECE_411H_integral-transforms_F26.deepgram.txt
deepgram_paragraphs: deepgram/ECE_411H_integral-transforms_F26.deepgram.md
---

# Integral Transform Techniques (recorded refresher session notes, F26)

**Summary**
Prof. Yu's handwritten tablet notes from the recorded refresher on why transform techniques exist, not just how to apply them. The chain of reasoning is: Fourier series (from ECE 302/302H) represents any periodic signal as a superposition of harmonics $n\omega_0$, so phasor analysis at each harmonic plus superposition handles any periodic input; the coefficient set $\{c_n\}$ is the frequency-domain representation and $\{e^{jn\omega_0 t}\}$ is a basis. Letting $T\to\infty$ turns the series into an integral, giving the Fourier transform $F(\omega)$ for non-periodic signals (derivation of $c_n$ via orthogonality shown in green, then the $\Delta\omega\to d\omega$ limit). Fourier integrals fail to converge for signals like $u(t)$ and $t^2u(t)$, so one defines complex frequency $s=\sigma+j\omega$, restricts to $t\ge 0$ (lower limit $0^-$), and gets the Laplace transform $F(s)$, which handles initial conditions and growing signals. The notes end with a three-line comparison of Fourier series / Fourier transform / Laplace transform. Exam relevance: this is the conceptual framing Prof. Yu expects behind the Exam 2 transform questions (why $0^-$, why $\mathrm{Re}(s)>0$, the $1/2\pi$ in the inverse Fourier integral).

> **Audio transcript (Deepgram nova-3, ECE 411 keyterms, timestamped):** `deepgram/ECE_411H_integral-transforms_F26.deepgram.txt` ; paragraph form: `deepgram/ECE_411H_integral-transforms_F26.deepgram.md`. Fresh ASR of the video audio; where it disagrees with the Narration section (built from the published auto-captions), prefer this file and the handwritten page.

## Page 1

Small printed header, top left: "Recorded session notes"

**Integral Transform Techniques** (underlined title)

How do we motivate, and understand, transform techniques rather than simplying [sic: "simply"] applying a bunch of formulas?

Recall Fourier series from (new) ECE 302/302H:

Let $f(t)$ be a periodic signal with period $T$:

$$f(t) = f(t + nT)\ \ \forall\, n \in \mathbb{Z} \text{ with } t \in (-\infty, \infty).$$

If $f(t)$ is a "reasonable" function (sufficiently smooth, non-diverging), then

$$f(t) = a_0 + \sum_{n=1}^{\infty}\left[a_n \cos n\omega_0 t + b_n \sin n\omega_0 t\right],\quad \omega_0 = \frac{2\pi}{T} \qquad \text{(Fourier series)}$$

OR

$$f(t) = \sum_{n=-\infty}^{\infty} c_n e^{jn\omega_0 t},\quad \omega_0 = \frac{2\pi}{T}$$

$\Rightarrow$ By analyzing a linear circuit's behavior at frequencies $\omega_n = \dfrac{2\pi n}{T} = n\omega_0$, we can understand its behavior for **any** (underlined) periodic signal using superposition.

Note that the set of coefficients $\{c_n\}$ represents $f(t)$ in the frequency domain.

In the language of linear algebra (or vectors), $\{e^{jn\omega_0 t}\}$ or $\{\cos n\omega_0 t, \sin n\omega_0 t, 1\}$ can serve as a set of **basis functions** (underlined) for any periodic function of $t$.

(Bottom of page: the first line of the next page's text is partially visible / cut off at the page break: "[illegible, likely: What about non-periodic signals?]" — repeated in full at the top of page 2.)

## Page 2

(Top edge shows the cut-off tail of page 1's last line: "of basis ..." — fragment only.)

What about non-periodic signals?

For $T \to \infty$, $f(t)$ is effectively non-periodic. The Fourier series then becomes a Fourier integral, leading to the **Fourier transform** (underlined).

$$f(t) = \sum_{n=-\infty}^{\infty} c_n e^{jn\omega_0 t},\quad \omega_0 = \frac{2\pi}{T}$$

(a stray scribbled-out mark appears under "$f(t) =$", below the equals sign)

with
$$c_n = \frac{1}{T}\int_{-T/2}^{T/2} f(t')\,e^{-jn\omega_0 t'}\,dt', \quad\text{or}$$

$$c(\omega_n) = \frac{1}{T}\int_{-T/2}^{T/2} f(t')\,e^{-j\omega_n t'}\,dt'$$

NOTE: $t'$ is a variable (the variable of integration), **not** (underlined) the derivative of $t$.

**[Green-ink derivation of the coefficient formula via orthogonality:]**

$$\left[f(t) = \sum_{n=-\infty}^{\infty} c_n e^{jn\omega_0 t}\right] e^{-jn_0\omega_0 t}$$

$$\frac{1}{T}\int_{-T/2}^{T/2}\left[e^{-jn_0\omega_0 t} f(t) = \sum_{n=-\infty}^{\infty} c_n e^{j(n-n_0)\omega_0 t}\right] dt$$

$$\frac{1}{T}\int_{-T/2}^{T/2} f(t)\,e^{-jn_0\omega_0 t}\,dt = \underbrace{\frac{1}{T}\int_{-T/2}^{T/2} c_{n_0}\,dt}_{=\frac{1}{T}(T c_{n_0}) = c_{n_0}} + \sum_{n \ne n_0}\frac{1}{T}\int_{-T/2}^{T/2} c_n\,e^{j(n-n_0)\omega_0 t}\,dt$$

The last sum (the $n \ne n_0$ terms) has a green arrow drawn from it pointing up-right to "$\to 0$" (i.e., each cross term integrates to zero over a period). The underbrace annotation reads "$= \frac{1}{T}(Tc_{n_0}) = c_{n_0}$".

**[back to black ink]**

$\{c(\omega_n)\}$ contains all ~~the~~ the information required to represent $f(t)$ in the frequency domain. (The word "the" is written twice; the first instance is struck through.)

Let $\Delta\omega \equiv \dfrac{2\pi}{T}$. Then

$$f(t) = \sum_{n=-\infty}^{\infty}\left[\int_{-T/2}^{T/2} f(t')\,e^{-j\omega_n t'}\,dt'\right] e^{j\omega_n t}\,\frac{1}{2\pi}\,\Delta\omega$$

(This equation runs onto the bottom of the page and is repeated at the top of page 3.)

## Page 3

(Top edge: the cut-off top of the same equation, repeated from page 2:)

$$f(t) = \sum_{n=-\infty}^{\infty}\left[\underbrace{\int_{-T/2}^{T/2} f(t')\,e^{-j\omega_n t'}\,dt'}_{\text{a function of } \omega_n}\right] e^{j\omega_n t}\,\frac{1}{2\pi}\,\Delta\omega$$

(the right-hand part "$e^{j\omega_n t}\,\frac{1}{2\pi}\Delta\omega$" is clipped by the page edge; only "$e^{\cdot}$" and "$2\pi\cdot$" fragments are visible on this page — full form taken from the bottom of page 2.)

For $T \to \infty$, $\displaystyle\sum_{n=-\infty}^{\infty}(\ \ )\,\Delta\omega \to \int_{-\infty}^{\infty}(\ \ )\,d\omega$; also, $\omega_n = \dfrac{2\pi n}{T} \to \omega$, a continuous variable.

$$\Rightarrow\ f(t) = \frac{1}{2\pi}\int_{-\infty}^{\infty}\left[\underbrace{\int_{-\infty}^{\infty} f(t')\,e^{-j\omega t'}\,dt'}_{= F(\omega),\ \text{the } \underline{\text{Fourier Transform}} \text{ of } f(t)}\right] e^{j\omega t}\,d\omega$$

$F(\omega)$ is the frequency-domain representation of $f(t)$, similar to how for phasors, $\underline{V} = V_m e^{j\phi}$ is the frequency-domain representation of $v(t) = V_m\cos(\omega t + \phi)$, and for Fourier series, the coefficients $c_n$ represent $f(t)$ in the frequency domain.

BUT what about a signal like $f(t) = u(t)$? or $f(t) = t^2 u(t)$?

$f(t) = u(t)$:
$$F(\omega) = \int_{-\infty}^{\infty} u(t)\,e^{-j\omega t}\,dt = \int_0^{\infty} e^{-j\omega t}\,dt.$$
(Blue-ink annotation under the integrand with a caret: "$e^{-\sigma t}$, $\sigma > 0$" — i.e., the fix is to insert a convergence factor $e^{-\sigma t}$.)

This is tricky to calculate.

$f(t) = t^2 u(t)$:
$$F(\omega) = \int_0^{\infty} t^2 e^{-j\omega t}\,dt$$
(Blue-ink annotation under the integrand with a caret: "$e^{-\sigma t}$, $\sigma > 0$.")

This integral does not converge.

We can define a **complex** (underlined) frequency $s \equiv \sigma + j\omega$ ($\sigma, \omega$ real), and consider an alternative to the Fourier transform — a new transform function $F(s)$ defined in the $s$-domain, or complex frequency domain:

(last line cut off at page bottom; repeated at top of page 4)

## Page 4

(Top edge: cut-off repeat of "a new transform ..." from page 3.)

or complex frequency domain:

$$F(s) = \int_{0^-}^{\infty} f(t)\,e^{-st}\,dt \qquad s \in \mathbb{C}\ (s \text{ complex}).$$

$0^-$ indicates explicitly that $f(0)$ is included in the integral.

We include only $t \ge 0$ rather than $|t| < \infty$ since otherwise the integral wouldn't converge for $\mathrm{Re}(s) \ne 0$. (The word "necessarily" is inserted with a caret between "wouldn't" and "converge": "wouldn't necessarily converge".)

For $f(t) = u(t)$ or $f(t) = t^2 u(t)$, etc., $F(s)$ can easily be computed for $\mathrm{Re}(s) > 0$.

$F(s)$ is called the **Laplace transform** (underlined), and allows us to analyze signals with initial conditions at $t = 0$ and that are constant or growing as $t \to \infty$.

**Fourier series:** superposition of frequencies, each analyzed using phasors, to analyze circuits with any periodic signal.

**Fourier transform:** extension of Fourier series to infinite period to analyze circuits with non-periodic signals.

**Laplace transform:** extension to complex frequencies $s$ (oscillation and exponential decay/growth) to analyze circuits with signals defined [continues on page 5]

## Page 5

(Top edge: cut-off repeat of "(oscillation and exponential decay/growth)" from page 4.)

to analyze circuits with signals defined for $t \ge 0$ and that have initial conditions, including signals with growing amplitude as $t \to \infty$.

Rest of page is blank.

## Index terms

integral transform techniques, Fourier series, ECE 302/302H, periodic signal, period T, f(t) = f(t+nT), reasonable function, sufficiently smooth, non-diverging, trigonometric Fourier series a_n b_n, complex exponential Fourier series c_n, ω₀ = 2π/T, harmonics ω_n = nω₀, superposition, linear circuit, frequency domain representation, basis functions, linear algebra, {e^{jnω₀t}}, {cos nω₀t, sin nω₀t, 1}, non-periodic signals, T → ∞, Fourier integral, Fourier transform, c_n coefficient integral, c(ω_n), variable of integration t', orthogonality derivation, n ≠ n₀ cross terms vanish, Δω = 2π/T, Riemann sum to integral, continuous variable ω, inverse Fourier transform 1/2π ∫F(ω)e^{jωt}dω, F(ω) definition, phasor V = V_m e^{jφ}, v(t) = V_m cos(ωt+φ), unit step u(t), t²u(t), Fourier integral convergence, convergence factor e^{-σt}, σ > 0, complex frequency s = σ + jω, s-domain, complex frequency domain, Laplace transform F(s) = ∫₀⁻^∞ f(t)e^{-st}dt, lower limit 0⁻, f(0) included, one-sided transform t ≥ 0, Re(s) > 0, region of convergence, initial conditions at t = 0, growing signals, exponential decay/growth, oscillation, comparison Fourier series vs Fourier transform vs Laplace transform, Prof. Ed Yu recorded session notes
