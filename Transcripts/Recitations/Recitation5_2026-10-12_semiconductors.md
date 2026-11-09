---
course: ECE 411H
kind: refresher-notes
source: Recitations/Recitation5(10-12-26).pdf
source_pages: 4
author: Darsh Shah (TA)
unit: exam2
topics: [semiconductors, silicon, covalent-bond, band-gap, conduction-band, valence-band, conductors, insulators, thermal-excitation, brownian-motion, fermi-dirac-distribution, fermi-level, boltzmann-approximation, boltzmann-constant, density-of-states, effective-mass, electron-concentration, hole-concentration, intrinsic-concentration, gamma-function-integral, doping, donor-level, ps6]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
---

# Recitation 5 (10/12) — Semiconductor physics: bands, Fermi–Dirac, density of states, n and p (TA Darsh Shah)

**Summary**
Handwritten Xournal tablet notes (4 pages) from the first Exam-2-unit recitation. The TA said on Discord that this material "will certainly be on PS6 and on y'all's next exam" and that "there are often questions on semiconductor physics on the second exam." Content: Si as a 4-valence-electron covalent crystal; band diagrams for semiconductor / conductor / insulator; electrons at $T=0$ vs $T>0$ (thermal excitation across $E_g$, recombination, Brownian motion); orders of magnitude for $E_g$ (metal $\simeq 0$, semiconductor 1–3 eV, insulator large) and $k_BT = 0.026$ eV with $k_B = 8.617\times10^{-5}$ eV/K; the Fermi–Dirac distribution $f(E)=1/(e^{(E-E_f)/k_BT}+1)$, its Boltzmann-tail approximation $f\approx e^{-(E-E_f)/k_BT}$, and $E_f$ as the energy where $f=1/2$; the density of states $g_c(E)$, $g_v(E)$ and effective masses $m_c^*=1.18m_e$, $m_v^*=0.81m_e$; a three-panel graphical construction of $n = \int f\cdot g_c$ and $p = \int(1-f)\cdot g_v$; the full derivation of $n = Q\,e^{-(E_c-E_f)/kT}\int_0^\infty e^{-u/kT}u^{1/2}du$ with the gamma-function integral evaluated as $(\sqrt\pi/2)(k_BT)^{3/2}$; the result $p = 2\left(m_v k_BT/2\pi\hbar^2\right)^{3/2}e^{-(E_F-E_v)/k_BT}$; the constants needed for Si at 300 K; and a final page on doping ($10^{14}$–$10^{18}$ cm$^{-3}$ vs $N_{Si}=10^{22}$ cm$^{-3}$), the donor level $E_d$ and how doping shifts $E_f$.

**PS6 mapping** (problem statements in `Transcripts/Problem Sets/PS6_problems.md`):
- **PS6 Problem 3 (hole concentration from density of states)** — directly covered. Page 3 derives $n$ from $\int_{E_c}^\infty f(E)g_c(E)dE$ via the Boltzmann approximation and the substitution $u = E - E_c$, and evaluates the gamma-function integral $\int_0^\infty e^{-u/kT}u^{1/2}du = \frac{\sqrt\pi}{2}(k_BT)^{3/2}$; the problem asks for the mirror-image derivation of $p$ with $1-f(E)$ and $g_v(E)$, whose result $p = 2(m_v^* k_BT/2\pi\hbar^2)^{3/2}e^{-(E_F-E_v)/k_BT}$ is pasted at the bottom of page 3. The $1-f(E)$ approximation and the $p$ integral's limits ($-\infty$ to $E_v$) are set up on pages 2–3.
- **PS6 Problem 4 (intrinsic concentration)** — directly covered: $n_i^2 = np$ (page 3, top line), the $n$ expression, and every constant needed for part (b) is written on page 3 ($k_B$, $\hbar = 1.055\times10^{-34}$ J·s, $m_c^* = 1.18m_e$, $m_v^* = 0.81m_e$, $m_e = 9.11\times10^{-31}$ kg, 1.12 eV, and 1 eV $=1.602\times10^{-19}$ J on page 2).
- **PS6 Problem 5 (simplified ideal diode equation)** — only the background: page 4's point that doping moves $E_f$ and therefore sets $n, p$ through $f(E)$ is the idea behind the hint, but no pn junction, band-edge shift with $V$, or $J(V)$ appears in these notes.
- **PS6 Problem 6 (dimensional analysis, diffusion)** and **Problems 1–2 (maximum power transfer)** — not covered.

Transcriber notes are in square brackets. Green ink = annotations added during the session; blue ink = emphasis curves/labels.

## Page 1

Header (centred): **ECE 411H – Recitation 5 (10/12)**

Si → 4 valence e⁻

**Figure:** Lewis-style sketch of four Si atoms in a 2×2 arrangement ("Si" written four times: upper-left, upper-right, lower-left, lower-right). Each Si has dots (valence electrons) around it: one dot to its left/right and dots above/below, so that between neighbouring atoms there are pairs of dots. Between the two upper Si atoms a pair of dots is boxed in green and labelled "cova." (covalent bond) in green, with a green arrow pointing down at the box and a second green arrow pointing at a dot above the upper-left Si.

Small annotation with a bent arrow (↱): "440" [illegible, likely: "440", i.e. a course cross-reference; could read "H40"].

⇒ Si crystals are very 'regular'

**Figure:** three band diagrams side by side, each with two horizontal lines.
- Left, labelled **Semiconductor**: upper line $E_c$, lower line $E_v$, vertical bracket between them labelled $E_g$ (moderate gap, about two ruled lines).
- Middle, labelled **Conductors**: the two lines are very close together and *inverted*: the upper line is labelled $E_v$ and the lower line $E_c$ (bands overlap); a tiny bracket labelled $E_g$ (drawn as a short "I").
- Right, labelled **Insulators**: $E_c$ far above $E_v$ (about four ruled lines apart); a long double-headed vertical arrow between them labelled "$E_g \gg E_{g,\text{semi}}$".

**At T = 0K,**

**Figure:** band diagram: line $E_c$ with a double row of open circles (empty states) just above it; line $E_v$ with a scatter of filled dots (electrons) below it; vertical bracket $E_g$ between the lines.

T = average KE of particle ...

**Figure:** plot, vertical axis "# particles", horizontal axis energy; a bell-shaped curve starting near zero, peaking, and decaying; a tick on the horizontal axis under the peak labelled $E_{avg}$.

**At T > 0K,**

There will > 0 particles w/ energy > $E_g$
For higher T, particles w/ energy > $E_g$ will increase

**Figure:** band diagram: line $E_c$ with a mixed row of filled dots and open circles above it (some states now occupied); line $E_v$ with a mixed row of filled dots and open circles below it (some states now empty = holes) and another row of dots further below; vertical double-headed arrow labelled $E_g$ at the left; a **blue** curved arrow from $E_v$ up to $E_c$ (thermal excitation of an electron across the gap). In **green**, inside the gap at the left: a filled dot (electron) with an arrow pointing down toward $E_v$, a small open square (a hole/empty state) beside it, a short diagonal arrow pointing up-right at the dot, and a wiggly arrow (photon/phonon) — a sketch of the electron falling back (recombination).

**Brownian Motion**

**Figure:** a blob-shaped enclosure containing a dot with an arrow to a second dot that has a small up-arrow; "⇒" then a brace containing "← •" and "• →" (particles moving in random directions).

## Page 2

Top right:
$1\text{ eV} = 1.602\text{e-}19\text{ J}$
$\hookrightarrow$ W·s

$E_g$ are metal/conductors, semiconductors, insul.?

- $E_g$ metal/cond. $\simeq 0$ eV
- $E_g$ insul. $\gtrsim (10\text{ keV})?$ [as written, with question mark]
- $E_g$ semi $\approx 1\text{–}3$ eV

**Figure:** (right) plot, vertical axis "# of part.", horizontal axis $E$; a curve that starts near zero at the origin, rises to a peak and decays toward the right; labelled $e^{-x^2}$ at its tail; a tick on the $E$ axis labelled $0.026$ eV (just right of the peak).

$k_BT = 0.026$ eV
$\hookrightarrow$ K [arrow under $T$: temperature in kelvin]
$\hookrightarrow$ Boltzmann's const. $(8.617\times10^{-5}\text{ eV/K})$ [arrow under $k_B$]

**Fermi Dirac Dist.** (underlined)

① (circled in green)
$$f(E) = \frac{1}{e^{(E-E_f)/k_BT} + 1}$$
$\hookrightarrow$ prob. that a state at $E$ is occupied.

$E \to \infty$, $f(E) = 0$.

If $k_BT \approx 26$ meV, $E - E_f \gg k_BT$,
$$f(E) \approx \frac{1}{e^{(E-E_f)/k_BT}} = e^{-(E-E_f)/k_BT}$$

Looking at ①, what $E$ gives $f(E) = 1/2$?
$\hookrightarrow E_f$! ⇒ Fermi level energy

Density of States (DoS) is the # of states at given $E$ per unit volume
Expectation[# of occupied states]
= P(state is occupied) · # of states.
= $f(E)$ · DoS

holes ↓ (arrow pointing at $g_v$)
$$g_v(E) = \frac{\sqrt2}{\pi^2}\left(\frac{m_v^*}{\hbar^2}\right)^{3/2}(E_v - E)^{1/2}$$
$$g_c(E) = \frac{\sqrt2}{\pi^2}\left(\frac{m_c^*}{\hbar^2}\right)^{3/2}(E - E_c)^{1/2}$$
Right: $\hbar,\ \pi,\ E_v,\ E_c,\ \sqrt2$ — underbrace labelled "const."

⇒ Effective Mass ($m^*$)
$$m_c^* = 1.18\,m_e$$
$$m_v^* = 0.81\,m_e$$
$$m_e = 9.11\times10^{-31}\text{ kg}$$

**Figure:** (right) two small sketches. Top: "$m^*$" — a dot with an arrow pointing into a cube drawn with dots at its corners (an electron entering a crystal lattice), then an arrow out the other side. Bottom: "$m$" — a dot with an arrow pointing into an empty cube with a single dot inside (free electron in empty space), then an arrow out. [Effective mass: the electron's inertia inside the periodic lattice vs in free space.]

## Page 3

$$n_i^2 = np$$

$$\left[\frac{e^-}{\cancel{\text{state}}}\right]\left[\frac{\cancel{\text{states}}}{\cancel{E}\ \text{vol}}\right]$$
["state", "states" and "E" struck through in green — the units of $f(E)\cdot$DoS reduce to electrons per volume]

$$n = \text{sum}\left[f(E)\cdot\text{DoS}\right] = \int_{E_c}^{\infty} f(E)\cdot\text{DoS}$$
$$p = \int_{-\infty}^{E_v}\left(1 - f(E)\right)\cdot\text{DoS}$$

Right: $e^-/c^3 = e^-/cc$ [written "$e^-/c\ 3$"; cm³ meant]; $h^+/cm^3 = h^+/cc$ (a small "m" inserted above the first "c").

**Figure:** Two rows of three plots each, with "×" between the first and second plot and "=" between the second and third in each row; green dashed horizontal guide lines connect the same energies across all three plots in a row.

Row **n** (label at far left):
- Plot 1: vertical axis $E$, horizontal axis $f(E)$. Curve: $f=1$ at low $E$ (bottom of the axis), decreasing smoothly (sigmoid) to 0 at high $E$ (top). Two green dashed horizontal lines: one at $E_c$ (where the curve is already in its tail) and one near the top of the axis. Below the plot: $f(E) = 1/(e^{(E-E_f)/k_BT}+1)$. A green dotted vertical line runs from the curve's $f=1$ end down into the row-p plot below.
- Plot 2: vertical axis $E$ with $E_c$ marked, horizontal axis DoS. Curve starts at $E_c$ on the axis and bends up and to the right (square-root shape) continuing upward. Below: $g_c(E) = \frac{\sqrt2}{\pi^2}\left(\frac{m_c^*}{\hbar^2}\right)^{3/2}(E-E_c)^{1/2}$.
- Plot 3: vertical axis $E$ with $E_c$ marked (green dot), horizontal axis $n$. Curve: a narrow lobe starting at $E_c$, bulging to the right and closing back to the axis at the upper green dashed line (product $f\cdot g_c$ as a function of $E$).

Row **p** (label at far left):
- Plot 1: vertical axis $E$, horizontal axis $f(E)$; **blue** curve $1 - f(E)$: near 0 at low $E$, rising (sigmoid) to 1 at high $E$; a tick on the horizontal axis at 1; two green dashed horizontal lines (one at $E_v$, one lower). Label below in blue: $1 - f(E)$.
- Plot 2: vertical axis $E$ with $E_v$ marked at the top, horizontal axis DoS. Curve starts at $E_v$ on the axis and bends down and to the right then down (square-root shape going downward), with an arrowhead at the bottom. Below: "holes ↓ $g_v(E) = \frac{\sqrt2}{\pi^2}\left(\frac{m_v^*}{\hbar^2}\right)^{3/2}(E_v-E)^{1/2}$".
- Plot 3: vertical axis $E$ with $E_v$ marked at the top (green dot), horizontal axis $p$. Curve: a lobe hanging below $E_v$, bulging right and closing at the lower green dashed line.

Derivation of $n$:
$$n = \int_{E_c}^{\infty}\left(e^{-(E-E_f)/kT}\right)\left(\frac{\sqrt2}{\pi^2}\left(\frac{m_c^*}{\hbar^2}\right)^{3/2}(E-E_c)^{1/2}\right)dE$$
$$= \underbrace{\frac{\sqrt2}{\pi^2}\left(\frac{m_c^*}{\hbar^2}\right)^{3/2}}\int_{E_c}^{\infty} e^{-(E-E_f)/kT}(E-E_c)^{1/2}\,dE$$
[underbrace under the prefactor; it is called $Q$ in the next line]
Green: $u = E - E_c,\quad du = dE$
$$= Q\int_0^{\infty} e^{-(u + E_c - E_f)/kT}\,u^{1/2}\,dE$$
[lower limit written as a dot/0; "$dE$" as written, i.e. $du$]
$$= Q\,e^{-(E_c - E_f)/kT}\underbrace{\int_0^{\infty} e^{-u/kT}\,u^{1/2}\,dE}$$
[underbrace under the remaining integral — this is the gamma-function integral, $\Gamma(3/2)(kT)^{3/2}$]
$$n = Q\,e^{-(E_c - E_f)/kT}\,\frac{\sqrt\pi}{2}\,(k_BT)^{3/2}$$
$$\propto \frac{T^{3/2}}{e^{-T}} \;\Rightarrow\; T^{3/2}e^{T}$$
[as written — a loose proportionality sketch of the temperature dependence; the exponent is really $-(E_c-E_f)/k_BT$, i.e. $\propto T^{3/2}e^{-\text{const}/T}$]

Right column (constants):
$$k_B = 8.617\times10^{-5}\text{ eV/K}$$
$$\hbar = 1.055\times10^{-34}\text{ J·s}$$
Si @ 300K, $m_c^* = 1.18\,m_e$
$m_v^* = 0.81\,m_e$
$$m_e = 9.11\times10^{-31}\text{ kg}$$
$$E_f = 1.12\text{ eV}$$
[as written "$E_f$"; 1.12 eV is the Si band gap $E_g$ given in PS6 problem 4(b)]

Pasted image (printed-looking, different hand, boxed by a rectangle at the bottom-left):
$$p = 2\left(\frac{m_v\,k_BT}{2\pi\hbar^2}\right)^{3/2}e^{-(E_F - E_v)/k_BT}$$
[The pasted clipping is cropped: a second line of text below the formula is cut off and [illegible]. This is the PS6 problem 3 target expression.]

## Page 4

Si is a crystal.
$\hookrightarrow$ % Si ⇒ 99.999%

Doping, ($n$, $p$ (carrier/cc))
$n, p = 10^{14} - 10^{18}$ doping/cc ⇒ $10^{-8} - 10^{-4}$ difference
$N_{Si} = 10^{22}$ atom/cc

**Figure:** (left) band diagram of a doped (n-type) semiconductor: solid upper line ($E_c$, unlabelled) and solid lower line ($E_v$, unlabelled) with a vertical bracket $E_g$ at the far left. Just below the upper line: a row of filled dots (donor electrons) and beneath them a dashed black line labelled $E_d$ (donor level). In **green** at the top-left: "$E_{g2}$" with a small bracket "I" spanning the tiny gap between the upper line and the dot row (the donor ionization energy), and a green curved arrow "(" pointing up from the dot row to the upper line (donor electron excited into the conduction band). A **blue** dashed line just below $E_d$ labelled "$E_{f,\text{new}}$" (blue). A black dashed line at mid-gap labelled "$E_f$" followed by "⇒" (the intrinsic Fermi level, which moves up to $E_{f,\text{new}}$ under doping).

**Figure:** (right) plot, vertical axis $E$, horizontal axis $f(E)$; a sigmoid curve from $f=1$ at low $E$ down to $f=0$ at high $E$, with the step located high on the $E$ axis (the Fermi level has moved up).

⇒ Doping changes $E_f$ ⇒ $n$, $p$

[Rest of page blank.]

## Index terms

Recitation 5, Darsh Shah, semiconductors, silicon, Si, 4 valence electrons, covalent bond, crystal, regular lattice, band diagram, conduction band E_c, valence band E_v, band gap E_g, semiconductor, conductor, insulator, E_g >> E_g,semi, T = 0 K, T > 0 K, average kinetic energy, # particles vs energy, E_avg, thermal excitation, recombination, Brownian motion, 1 eV = 1.602e-19 J, W·s, E_g metal ≈ 0 eV, E_g insulator, E_g semiconductor 1–3 eV, k_B T = 0.026 eV, 26 meV, Boltzmann constant 8.617e-5 eV/K, e^{-x^2}, Fermi–Dirac distribution, f(E) = 1/(e^{(E−E_f)/k_BT}+1), probability a state is occupied, Boltzmann approximation f ≈ e^{-(E−E_f)/k_BT}, Fermi level E_f, f(E_f) = 1/2, density of states, DoS, # of states per unit volume, expectation of occupied states, g_v(E), g_c(E), √2/π², (m*/ħ²)^{3/2}, (E − E_c)^{1/2}, (E_v − E)^{1/2}, effective mass m*, m_c* = 1.18 m_e, m_v* = 0.81 m_e, m_e = 9.11e-31 kg, n_i² = np, electrons per cc, holes per cc, n = ∫_{E_c}^∞ f(E) DoS dE, p = ∫_{-∞}^{E_v} (1 − f(E)) DoS dE, 1 − f(E), graphical product f × DoS = n, substitution u = E − E_c, Q prefactor, ∫_0^∞ e^{-u/kT} u^{1/2} du, gamma function integral, Γ(3/2), (√π/2)(k_BT)^{3/2}, n = Q e^{-(E_c−E_f)/kT} (√π/2)(k_BT)^{3/2}, T^{3/2} dependence, ħ = 1.055e-34 J·s, Si at 300 K, 1.12 eV, p = 2(m_v k_B T/2πħ²)^{3/2} e^{-(E_F−E_v)/k_BT}, effective density of states, intrinsic concentration, doping, carriers per cc, 10^14–10^18 /cc, N_Si = 10^22 atom/cc, 99.999% purity, donor level E_d, E_f,new, doping changes E_f, n-type, PS6 problem 3, PS6 problem 4, PS6 problem 5
