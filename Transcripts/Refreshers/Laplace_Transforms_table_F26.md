---
course: ECE 411H
kind: transform-table
source: Refreshers/ECE_411H_Laplace_Transforms_F26.pdf
source_pages: 2
author: Ulaby/Maharbiz/Furse
unit: exam2
topics: [laplace-transform, transform-pairs, laplace-properties, partial-fractions, poles, time-shift, frequency-shift, time-scaling, differentiation, integration, unit-step, impulse, damped-sinusoid]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
---

# Laplace Transforms table (official Exam 2 handout, F26)

**Summary**
Two-page handout reproducing Ulaby/Maharbiz/Furse Tables 12-2 (Laplace transform pairs, 16 numbered rows plus the "a" shifted variants), 12-1 (10 properties of the Laplace transform) and 12-3 (transform pairs for four pole types: distinct real, repeated real, distinct complex, repeated complex). Header: "Unique: 18535 — ECE 411H: Circuit Theory (Honors) — Fall 2026". This is the table supplied with Exam 2; every inverse-transform step on the exam is expected to be looked up here, so the exact form of each entry (especially rows 10, 12, 15, 16 and the pole table with its $2Ae^{-at}\cos(bt-\theta)$ convention) matters. No ROC column exists in the source: all pairs are one-sided ($f(t)=0$ for $t<0^-$, $T\ge 0$, $a>0$ where written). Content is identical to the F25 handout (see last section).

## Page 1

Header (top of page): "Unique: 18535" (left), "**ECE 411H: Circuit Theory (Honors)**" (center), "Fall 2026" (right).

**Table 12-2:** Examples of Laplace transform pairs for $T \ge 0$. Note that multiplication by $u(t)$ guarantees that $f(t) = 0$ for $t < 0^-$.

Table title (inside box): **Laplace Transform Pairs**. Columns: $f(t)$ | $\mathbf{F}(\mathbf{s}) = \mathcal{L}[f(t)]$. Each row joined by a red double-headed arrow ($\leftrightarrow$). No ROC column exists in the source; the only stated conditions are $T \ge 0$ and $f(t)=0$ for $t<0^-$.

| # | $f(t)$ | $\mathbf{F}(\mathbf{s}) = \mathcal{L}[f(t)]$ | ROC / conditions (as stated in source) |
|---|---|---|---|
| 1 | $\delta(t)$ | $1$ | — |
| 1a | $\delta(t - T)$ | $e^{-T\mathbf{s}}$ | $T \ge 0$ |
| 2 | $1$ or $u(t)$ | $\dfrac{1}{\mathbf{s}}$ | — |
| 2a | $u(t - T)$ | $\dfrac{e^{-T\mathbf{s}}}{\mathbf{s}}$ | $T \ge 0$ |
| 3 | $e^{-at}\,u(t)$ | $\dfrac{1}{\mathbf{s} + a}$ | — |
| 3a | $e^{-a(t-T)}\,u(t - T)$ | $\dfrac{e^{-T\mathbf{s}}}{\mathbf{s} + a}$ | $T \ge 0$ |
| 4 | $t\,u(t)$ | $\dfrac{1}{\mathbf{s}^2}$ | — |
| 4a | $(t - T)\,u(t - T)$ | $\dfrac{e^{-T\mathbf{s}}}{\mathbf{s}^2}$ | $T \ge 0$ |
| 5 | $t^2\,u(t)$ | $\dfrac{2}{\mathbf{s}^3}$ | — |
| 6 | $t e^{-at}\,u(t)$ | $\dfrac{1}{(\mathbf{s} + a)^2}$ | — |
| 7 | $t^2 e^{-at}\,u(t)$ | $\dfrac{2}{(\mathbf{s} + a)^3}$ | — |
| 8 | $t^{n-1} e^{-at}\,u(t)$ | $\dfrac{(n-1)!}{(\mathbf{s} + a)^n}$ | — |
| 9 | $\sin \omega t\,u(t)$ | $\dfrac{\omega}{\mathbf{s}^2 + \omega^2}$ | — |
| 10 | $\sin(\omega t + \theta)\,u(t)$ | $\dfrac{\mathbf{s}\sin\theta + \omega\cos\theta}{\mathbf{s}^2 + \omega^2}$ | — |
| 11 | $\cos \omega t\,u(t)$ | $\dfrac{\mathbf{s}}{\mathbf{s}^2 + \omega^2}$ | — |
| 12 | $\cos(\omega t + \theta)\,u(t)$ | $\dfrac{\mathbf{s}\cos\theta - \omega\sin\theta}{\mathbf{s}^2 + \omega^2}$ | — |
| 13 | $e^{-at}\sin \omega t\,u(t)$ | $\dfrac{\omega}{(\mathbf{s} + a)^2 + \omega^2}$ | — |
| 14 | $e^{-at}\cos \omega t\,u(t)$ | $\dfrac{\mathbf{s} + a}{(\mathbf{s} + a)^2 + \omega^2}$ | — |
| 15 | $2e^{-at}\cos(bt - \theta)\,u(t)$ | $\dfrac{e^{j\theta}}{\mathbf{s} + a + jb} + \dfrac{e^{-j\theta}}{\mathbf{s} + a - jb}$ | — |
| 16 | $\dfrac{2t^{n-1}}{(n-1)!}\,e^{-at}\cos(bt - \theta)\,u(t)$ | $\dfrac{e^{j\theta}}{(\mathbf{s} + a + jb)^n} + \dfrac{e^{-j\theta}}{(\mathbf{s} + a - jb)^n}$ | — |

Note (below table): $(n-1)! = (n-1)(n-2)\ldots 1$.

## Page 2

Header: "*ECE 411H: Circuit Theory (Honors)*" (left, italic), "*Fall 2026* / *Unique 18535*" (right, two lines, italic).

**Table 12-1:** Properties of the Laplace transform ($f(t) = 0$ for $t < 0^-$).

Columns: Property | $f(t)$ | $\mathbf{F}(\mathbf{s}) = \mathcal{L}[f(t)]$. Rows joined by red $\leftrightarrow$.

| # | Property | $f(t)$ | $\mathbf{F}(\mathbf{s}) = \mathcal{L}[f(t)]$ | Conditions (as stated) |
|---|---|---|---|---|
| 1 | Multiplication by constant | $K\,f(t)$ | $K\,\mathbf{F}(\mathbf{s})$ | — |
| 2 | Linearity | $K_1\,f_1(t) + K_2\,f_2(t)$ | $K_1\,\mathbf{F}_1(\mathbf{s}) + K_2\,\mathbf{F}_2(\mathbf{s})$ | — |
| 3 | Time scaling | $f(at)$ | $\dfrac{1}{a}\,\mathbf{F}\!\left(\dfrac{\mathbf{s}}{a}\right)$ | $a > 0$ |
| 4 | Time shift | $f(t - T)\,u(t - T)$ | $e^{-T\mathbf{s}}\,\mathbf{F}(\mathbf{s})$ | $T \ge 0$ |
| 5 | Frequency shift | $e^{-at}\,f(t)$ | $\mathbf{F}(\mathbf{s} + a)$ | — |
| 6 | Time 1st derivative | $f' = \dfrac{df}{dt}$ | $\mathbf{s}\,\mathbf{F}(\mathbf{s}) - f(0^-)$ | — |
| 7 | Time 2nd derivative | $f'' = \dfrac{d^2 f}{dt^2}$ | $\mathbf{s}^2\,\mathbf{F}(\mathbf{s}) - \mathbf{s}\,f(0^-) - f'(0^-)$ | — |
| 8 | Time integral | $\displaystyle\int_{0^-}^{t} f(\tau)\,d\tau$ | $\dfrac{1}{\mathbf{s}}\,\mathbf{F}(\mathbf{s})$ | — |
| 9 | Frequency derivative | $t\,f(t)$ | $-\dfrac{d}{d\mathbf{s}}\,\mathbf{F}(\mathbf{s})$ | — |
| 10 | Frequency integral | $\dfrac{f(t)}{t}$ | $\displaystyle\int_{\mathbf{s}}^{\infty} \mathbf{F}(\mathbf{s}')\,d\mathbf{s}'$ | — |

(No convolution, initial-value or final-value property rows appear on this handout; the ten rows above are the complete Table 12-1 as printed.)

**Table 12-3:** Transform pairs for four types of poles.

Columns: Pole | $\mathbf{F}(\mathbf{s})$ | $f(t)$.

| # | Pole | $\mathbf{F}(\mathbf{s})$ | $f(t)$ |
|---|---|---|---|
| 1 | Distinct real | $\dfrac{A}{\mathbf{s} + a}$ | $A e^{-at}\,u(t)$ |
| 2 | Repeated real | $\dfrac{A}{(\mathbf{s} + a)^n}$ | $A\,\dfrac{t^{n-1}}{(n-1)!}\,e^{-at}\,u(t)$ |
| 3 | Distinct complex | $\left[\dfrac{A e^{j\theta}}{\mathbf{s} + a + jb} + \dfrac{A e^{-j\theta}}{\mathbf{s} + a - jb}\right]$ | $2A e^{-at}\cos(bt - \theta)\,u(t)$ |
| 4 | Repeated complex | $\left[\dfrac{A e^{j\theta}}{(\mathbf{s} + a + jb)^n} + \dfrac{A e^{-j\theta}}{(\mathbf{s} + a - jb)^n}\right]$ | $\dfrac{2A t^{n-1}}{(n-1)!}\,e^{-at}\cos(bt - \theta)\,u(t)$ |

Rest of page 2 is blank.

## Differences vs F25 table

Compared page-by-page against `Refreshers/ECE_411H_Laplace_Transforms_F25.pdf` (2 pp).

- **Identical content.** Table 12-2 (all rows 1–16 and 1a–4a, plus the factorial note), Table 12-1 (all 10 properties) and Table 12-3 (all 4 pole types) are the same images in the same layout; no row or property was added, removed, or changed.
- Only the page headers differ: F25 reads "Unique: 18385 / Fall 2025" where F26 reads "Unique: 18535 / Fall 2026".

## Index terms

Laplace transform pairs, Table 12-2, Table 12-1, Table 12-3, impulse δ(t), shifted impulse δ(t−T), unit step u(t), shifted step u(t−T), 1/s, e^{-Ts}/s, exponential e^{-at}u(t), 1/(s+a), shifted exponential, ramp t u(t), 1/s², shifted ramp (t−T)u(t−T), t² u(t), 2/s³, t e^{-at}, 1/(s+a)², t² e^{-at}, 2/(s+a)³, t^{n−1} e^{-at}, (n−1)!/(s+a)^n, sin ωt, ω/(s²+ω²), sin(ωt+θ), cos ωt, s/(s²+ω²), cos(ωt+θ), damped sine e^{-at} sin ωt, damped cosine e^{-at} cos ωt, (s+a)/((s+a)²+ω²), 2e^{-at}cos(bt−θ), complex conjugate pole pair, e^{jθ}/(s+a+jb), repeated complex poles, factorial note, multiplication by constant, linearity, time scaling f(at), (1/a)F(s/a), time shift f(t−T)u(t−T), e^{-Ts}F(s), frequency shift e^{-at}f(t), F(s+a), time 1st derivative sF(s)−f(0⁻), time 2nd derivative s²F(s)−sf(0⁻)−f'(0⁻), time integral F(s)/s, frequency derivative −dF/ds, frequency integral ∫F(s')ds', f(t)/t, initial condition 0⁻, distinct real pole, repeated real pole, distinct complex pole, repeated complex pole, A/(s+a), A/(s+a)^n, partial fraction expansion, inverse Laplace transform, Ulaby Maharbiz Furse, Exam 2 handout, Fall 2026, Unique 18535, F25 comparison identical
