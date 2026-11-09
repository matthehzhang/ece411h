---
course: ECE 411H
kind: transform-table
source: Refreshers/ECE_411H_Fourier_Transforms_F26.pdf
source_pages: 2
author: Ulaby/Maharbiz/Furse
unit: exam2
topics: [fourier-transform, transform-pairs, fourier-properties, fourier-series, rect, sinc, sgn, modulation, convolution, time-scaling, time-shift, frequency-shift, impulse, unit-step, magnitude-spectrum]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
---

# Fourier Transforms table (official Exam 2 handout, F26)

**Summary**
Two-page handout reproducing Ulaby/Maharbiz/Furse Table 13-4 (13 Fourier transform pairs with sketches of $f(t)$ and $|\mathbf{F}(\omega)|$ for the nine "basic functions"), Table 13-5 (12 major properties of the Fourier transform, including time scaling with $1/|a|$, modulation, both convolution properties and the time-integral property with its $\pi\mathbf{F}(0)\delta(\omega)$ term) and Table 13-3 (Fourier series in cosine/sine, amplitude/phase and complex-exponential forms, with coefficient integrals and conversion formulas). Header: "Unique: 18535 — ECE 411H: Circuit Theory (Honors) — Fall 2026". This is the table supplied with Exam 2. The source gives no ROC column (the Fourier integrals converge in the ordinary or distributional sense for every listed row); the only stated condition is $a \ge 0$. Content is identical to the F25 handout (see last section).

## Page 1

Header: "Unique: 18535" (left), "**ECE 411H: Circuit Theory (Honors)**" (center), "Fall 2026" (right).

**Table 13-4:** Examples of Fourier transform pairs. Note that constant $a \ge 0$.

Columns: $f(t)$ (with a small blue sketch of the time function for rows 1–9) | $\mathbf{F}(\omega) = \mathcal{F}[f(t)]$ | $|\mathbf{F}(\omega)|$ (small blue sketch of the magnitude spectrum for rows 1–9). Rows joined by red $\leftrightarrow$. Sub-heading row **BASIC FUNCTIONS** precedes row 1; sub-heading row **ADDITIONAL FUNCTIONS** precedes row 10. Rows 10–13 have no sketches.

| # | $f(t)$ | $\mathbf{F}(\omega) = \mathcal{F}[f(t)]$ | ROC / conditions (as stated) |
|---|---|---|---|
| 1 | $\delta(t)$ | $1$ | — |
| 1a | $\delta(t - t_0)$ | $e^{-j\omega t_0}$ | — |
| 2 | $1$ | $2\pi\,\delta(\omega)$ | — |
| 3 | $u(t)$ | $\pi\,\delta(\omega) + 1/j\omega$ | — |
| 4 | $\mathrm{sgn}(t)$ | $2/j\omega$ | — |
| 5 | $\mathrm{rect}(t/\tau)$ | $\tau\,\mathrm{sinc}(\omega\tau/2)$ | — |
| 6 | $\lvert t \rvert$ | $-2/\omega^2$ | — |
| 7 | $e^{-at}\,u(t)$ | $1/(a + j\omega)$ | $a \ge 0$ |
| 8 | $\cos \omega_0 t$ | $\pi[\delta(\omega - \omega_0) + \delta(\omega + \omega_0)]$ | — |
| 9 | $\sin \omega_0 t$ | $j\pi[\delta(\omega + \omega_0) - \delta(\omega - \omega_0)]$ | — |
| 10 | $e^{j\omega_0 t}$ | $2\pi\,\delta(\omega - \omega_0)$ | — |
| 11 | $t e^{-at}\,u(t)$ | $1/(a + j\omega)^2$ | $a \ge 0$ |
| 12 | $[e^{-at}\sin \omega_0 t]\,u(t)$ | $\omega_0 / [(a + j\omega)^2 + \omega_0^2]$ | $a \ge 0$ |
| 13 | $[e^{-at}\cos \omega_0 t]\,u(t)$ | $(a + j\omega) / [(a + j\omega)^2 + \omega_0^2]$ | $a \ge 0$ |

**Figure:** sketches in the $f(t)$ column (all blue on black axes, $t$ horizontal):
- Row 1: single upward arrow (impulse) at $t=0$ labelled $\delta(t)$, height marked 1.
- Row 1a: upward arrow at $t = t_0$ (to the right of origin), height marked 1.
- Row 2: horizontal line at height 1 for all $t$ (constant).
- Row 3: zero for $t<0$, vertical jump at $t=0$, then horizontal line at height 1 for $t>0$ (unit step).
- Row 4: horizontal line at $-1$ for $t<0$, vertical jump through the origin, horizontal line at $+1$ for $t>0$ (signum).
- Row 5: rectangular pulse of height 1 centred at $t=0$, width marked $\lvert\!\leftarrow \tau \rightarrow\!\rvert$ below (from $-\tau/2$ to $\tau/2$).
- Row 6: V shape, two straight lines of slope $\mp 1$ meeting at the origin ($|t|$).
- Row 7: zero for $t<0$, jumps to 1 at $t=0$, then decays exponentially toward zero.
- Row 8: cosine, amplitude 1, maximum at $t=0$.
- Row 9: sine, amplitude 1, zero at $t=0$ rising.

**Figure:** sketches in the $|\mathbf{F}(\omega)|$ column ($\omega$ horizontal):
- Row 1: flat line at height 1 for all $\omega$.
- Row 1a: flat line at height 1 for all $\omega$.
- Row 2: single upward arrow at $\omega = 0$ labelled $2\pi$.
- Row 3: upward arrow at $\omega=0$ labelled $\pi$, plus two hyperbola-like branches ($1/|\omega|$) decaying away from the origin on both sides.
- Row 4: two hyperbola-like branches ($2/|\omega|$) decaying away from $\omega=0$ on both sides, no impulse.
- Row 5: sinc magnitude: main lobe of height $\tau$ at $\omega=0$, first zeros at $-2\pi/\tau$ and $2\pi/\tau$ (labelled), decaying side lobes (rectified) on both sides.
- Row 6: two branches ($2/\omega^2$) decaying away from the origin, symmetric.
- Row 7: bell-shaped curve peaking at $1/a$ (labelled) at $\omega=0$, symmetric, decaying on both sides.
- Row 8: two upward arrows of height $\pi$ at $-\omega_0$ and $+\omega_0$.
- Row 9: upward arrow of height $\pi$ at $-\omega_0$ and a downward arrow of height $-\pi$ at $+\omega_0$ (sketch shows the signed imaginary part, $\omega_0$ labelled on the axis).

## Page 2

Header: "*ECE 411H: Circuit Theory (Honors)*" (left, italic), "*Fall 2026* / *Unique 18535*" (right, italic, two lines).

**Table 13-5:** Major properties of the Fourier transform.

Columns: Property | $f(t)$ | $\mathbf{F}(\omega) = \mathcal{F}[f(t)]$. Rows joined by red $\leftrightarrow$.

| # | Property | $f(t)$ | $\mathbf{F}(\omega) = \mathcal{F}[f(t)]$ |
|---|---|---|---|
| 1 | Multiplication by a constant | $K\,f(t)$ | $K\,\mathbf{F}(\omega)$ |
| 2 | Linearity | $K_1\,f_1(t) + K_2\,f_2(t)$ | $K_1\,\mathbf{F}_1(\omega) + K_2\,\mathbf{F}_2(\omega)$ |
| 3 | Time scaling | $f(at)$ | $\dfrac{1}{\lvert a \rvert}\,\mathbf{F}\!\left(\dfrac{\omega}{a}\right)$ |
| 4 | Time shift | $f(t - t_0)$ | $e^{-j\omega t_0}\,\mathbf{F}(\omega)$ |
| 5 | Frequency shift | $e^{j\omega_0 t}\,f(t)$ | $\mathbf{F}(\omega - \omega_0)$ |
| 6 | Time 1st derivative | $f' = \dfrac{df}{dt}$ | $j\omega\,\mathbf{F}(\omega)$ |
| 7 | Time $n$th derivative | $\dfrac{d^n f}{dt^n}$ | $(j\omega)^n\,\mathbf{F}(\omega)$ |
| 8 | Time integral | $\displaystyle\int_{-\infty}^{t} f(t)\,dt$ | $\dfrac{\mathbf{F}(\omega)}{j\omega} + \pi\,\mathbf{F}(0)\,\delta(\omega)$ |
| 9 | Frequency derivative | $t^n\,f(t)$ | $(j)^n\,\dfrac{d^n \mathbf{F}(\omega)}{d\omega^n}$ |
| 10 | Modulation | $\cos \omega_0 t\,f(t)$ | $\tfrac{1}{2}[\mathbf{F}(\omega - \omega_0) + \mathbf{F}(\omega + \omega_0)]$ |
| 11 | Convolution in $t$ | $f_1(t) * f_2(t)$ | $\mathbf{F}_1(\omega)\,\mathbf{F}_2(\omega)$ |
| 12 | Convolution in $\omega$ | $f_1(t)\,f_2(t)$ | $\dfrac{1}{2\pi}\,\mathbf{F}_1(\omega) * \mathbf{F}_2(\omega)$ |

(No duality, Parseval, or conjugate-symmetry rows appear on this handout; the twelve rows above are the complete Table 13-5 as printed. The time-integral row uses $t$ as both the dummy variable and the upper limit, exactly as printed.)

**Table 13-3:** Fourier series representations for a periodic function $f(t)$.

Three columns: **Cosine/Sine** | **Amplitude/Phase** | **Complex Exponential**.

Row 1 (series form):
- Cosine/Sine: $f(t) = a_0 + \displaystyle\sum_{n=1}^{\infty} (a_n \cos n\omega_0 t + b_n \sin n\omega_0 t)$
- Amplitude/Phase: $f(t) = a_0 + \displaystyle\sum_{n=1}^{\infty} A_n \cos(n\omega_0 t + \phi_n)$
- Complex Exponential: $f(t) = \displaystyle\sum_{n=-\infty}^{\infty} \mathbf{c}_n e^{jn\omega_0 t}$

Row 2:
- Cosine/Sine: $a_0 = \dfrac{1}{T}\displaystyle\int_0^T f(t)\,dt$
- Amplitude/Phase: $A_n e^{j\phi_n} = a_n - jb_n$
- Complex Exponential: $\mathbf{c}_n = \lvert \mathbf{c}_n \rvert e^{j\phi_n};\quad \mathbf{c}_{-n} = \mathbf{c}_n^*$

Row 3:
- Cosine/Sine: $a_n = \dfrac{2}{T}\displaystyle\int_0^T f(t)\cos n\omega_0 t\,dt$
- Amplitude/Phase: $A_n = \sqrt{a_n^2 + b_n^2}$
- Complex Exponential: $\lvert \mathbf{c}_n \rvert = A_n/2;\quad c_0 = a_0$

Row 4:
- Cosine/Sine: $b_n = \dfrac{2}{T}\displaystyle\int_0^T f(t)\sin n\omega_0 t\,dt$
- Amplitude/Phase: $\phi_n = \begin{cases} -\tan^{-1}\!\left(\dfrac{b_n}{a_n}\right), & a_n > 0 \\[2ex] \pi - \tan^{-1}\!\left(\dfrac{b_n}{a_n}\right), & a_n < 0 \end{cases}$
- Complex Exponential: $\mathbf{c}_n = \dfrac{1}{T}\displaystyle\int_0^T f(t)\,e^{-jn\omega_0 t}\,dt$

Bottom row (spanning all columns): $a_0 = c_0;\quad a_n = A_n \cos\phi_n;\quad b_n = -A_n \sin\phi_n;\quad \mathbf{c}_n = \tfrac{1}{2}(a_n - jb_n)$

Rest of page 2 is blank.

## Differences vs F25 table

Compared page-by-page against `Refreshers/ECE_411H_Fourier_Transforms_F25.pdf` (2 pp).

- **Identical content.** Table 13-4 (rows 1–13 and 1a, with the same sketches), Table 13-5 (all 12 properties) and Table 13-3 (all Fourier-series rows and the bottom conversion line) are the same images in the same layout; no row or property was added, removed, or changed.
- Only the page headers differ: F25 reads "Unique: 18385 / Fall 2025" where F26 reads "Unique: 18535 / Fall 2026".

## Index terms

Fourier transform pairs, Table 13-4, Table 13-5, Table 13-3, basic functions, additional functions, impulse δ(t), shifted impulse δ(t−t₀), e^{-jωt₀}, constant 1, 2πδ(ω), unit step u(t), πδ(ω)+1/jω, signum sgn(t), 2/jω, rect(t/τ), τ sinc(ωτ/2), sinc main lobe 2π/τ, |t|, −2/ω², e^{-at}u(t), 1/(a+jω), cos ω₀t, π[δ(ω−ω₀)+δ(ω+ω₀)], sin ω₀t, jπ[δ(ω+ω₀)−δ(ω−ω₀)], e^{jω₀t}, 2πδ(ω−ω₀), t e^{-at}u(t), 1/(a+jω)², damped sine, damped cosine, ω₀/[(a+jω)²+ω₀²], (a+jω)/[(a+jω)²+ω₀²], magnitude spectrum |F(ω)|, multiplication by a constant, linearity, time scaling (1/|a|)F(ω/a), time shift e^{-jωt₀}F(ω), frequency shift F(ω−ω₀), time 1st derivative jωF(ω), time nth derivative (jω)^n F(ω), time integral F(ω)/jω + πF(0)δ(ω), frequency derivative t^n f(t), (j)^n d^nF/dω^n, modulation cos ω₀t f(t), ½[F(ω−ω₀)+F(ω+ω₀)], convolution in t, F₁(ω)F₂(ω), convolution in ω, (1/2π)F₁*F₂, Fourier series, cosine/sine form, amplitude/phase form, complex exponential form, a₀, aₙ, bₙ, Aₙ, φₙ, cₙ, c₋ₙ = cₙ*, |cₙ| = Aₙ/2, c₀ = a₀, Aₙe^{jφₙ} = aₙ − jbₙ, φₙ quadrant rule aₙ>0 aₙ<0, cₙ = ½(aₙ − jbₙ), aₙ = Aₙ cos φₙ, bₙ = −Aₙ sin φₙ, period T, fundamental ω₀, Ulaby Maharbiz Furse, Exam 2 handout, Fall 2026, Unique 18535, F25 comparison identical
