---
course: ECE 411H
kind: refresher-notes
source: Refreshers/Semiconductors_review_ETY.pdf
source_pages: 6
author: Prof. Ed Yu
unit: exam2
topics: [semiconductors, conductivity, resistivity, mobility, drift-velocity, current-density, ohms-law, microscopic-ohms-law, silicon, covalent-bond, intrinsic-concentration, doping, donor, acceptor, n-type, p-type, electrons-holes, mosfet, threshold-voltage, channel, drain-current, equivalent-circuit, dependent-source, streetman-banerjee]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
---

# Basics of Semiconductors (review from ECE 302/302H, ETY)

**Summary**
Six scanned pages of Prof. Yu's handwritten (lined-paper) review of semiconductor basics carried over from ECE 302/302H. Pages 1–2 derive resistance from first principles: electron concentration $n$, charge $q$, drift velocity $v=\mu\mathcal{E}$, current density $J=nq\mu\mathcal{E}$, $R=\rho\,\ell/A$ with $\rho=1/(nq\mu)$, conductivity $\sigma=1/\rho$, and the microscopic Ohm's law $J=\sigma\mathcal{E}$; then silicon's atomic structure and covalent-bond crystal. Page 3 covers thermally generated electron–hole pairs ($n_i\approx 10^{10}\ \mathrm{cm^{-3}}$ for Si at 300 K) and doping with boron (acceptor) and phosphorus (donor). Page 4 states the $N_D$ / $N_A$ / $n_i$ cases for n-type and p-type, then introduces the MOSFET cross-section (explicitly flagged as "not necessary for ECE 411"). Page 5 explains gate-controlled channel inversion, threshold voltage $V_T$, the $I_D$–$V_G$ and $I_D$–$V_D$ curves, $I_D=(\text{const})[(V_G-V_T)V_D-\tfrac12 V_D^2]$, and the small-signal equivalent circuit (gate capacitor + dependent current source $gV_G$). Page 6 is a reading list (Streetman & Banerjee, chapters 1, 3, 6). Exam relevance: the resistivity/conductivity/mobility material is the physical basis for resistors and for any "why is $R=\rho\ell/A$" question; the MOSFET material is background only.

## Page 1

(Page number "1" handwritten top right. Lined notebook paper with a double red margin line on the left.)

**Basics of Semiconductors (from ECE 302/302H)**

Semiconductors are materials whose properties, e.g., electrical conductivity, can be precisely controlled across, often, a very wide range of values. This controllability, which can be achieved through the introduction of impurity atoms, application of voltage, or other means, is the key to creating devices such as transistors, diodes, LEDs, solar cells, etc.

Consider a semiconductor in which the concentration of electrons that carry electric current is $n$ (in electrons/m$^3$). Each electron has a charge magnitude $q = 1.602\times 10^{-19}$ Coulomb. Assume this semiconductor is used to construct a resistor:

**Figure:** a horizontal cylinder (the semiconductor bar) labelled inside "resistance $= R$", with an arrow from the label "semiconductor" pointing at it. An arrow from "area $= A$" points to the left circular end face. Below the cylinder a double-headed arrow spans its length, labelled "length $= \ell$", with "$\rightarrow x$" indicating the $x$-direction to the right. Wires from the two ends of the cylinder run down and around to a circular voltage source at the bottom labelled "$+\ -$" (+ on the left, − on the right), forming a closed loop. An arrow from the source points down to the next line of text.

The electric field $\mathcal{E}$ in the semiconductor satisfies $\mathcal{E} = -\dfrac{d\phi}{dx}$ where $\phi(x)$ is the electrostatic potential. If $\mathcal{E}$ is constant within the semiconductor, then $V = \mathcal{E}\ell$.

In a typical semiconductor, the velocity, $v$, of an electron depends on the electric field $\mathcal{E}$ as follows:

**Figure:** plot of $v$ (vertical axis) vs $\mathcal{E}$ (horizontal axis). The curve rises linearly from the origin, then bends over and saturates to a constant value at large $\mathcal{E}$. A dashed straight line through the origin (tangent to the initial linear region) is drawn, and an arrow labelled with the equation below points at the linear region.

$$v = \mu\mathcal{E},\qquad \mu = \text{mobility}\ [\mathrm{m^2/V\cdot s}],\qquad \mathcal{E} = \text{electric field}\ [\mathrm{V/m}]$$

We will be concerned primarily with values of $\mathcal{E}$ for which $v = \mu\mathcal{E}$. Larger values of $\mathcal{E}$, for which $v \approx$ constant, can be important in small, high-performance devices operating at high speeds (frequencies).

## Page 2

(Page number "2" top right.)

In general, the current density $J$ [A/m$^2$] carried by electrons with concentration $n$, ~~and~~ charge magnitude $q$, and velocity $v$ is
$$J = nqv = nq\mu\mathcal{E}.$$
(a word between "$n$," and "charge" is struck out; original illegible, likely "and")

For our resistor, the total current is then $I = JA = nq\mu\mathcal{E}A$.

Then by Ohm's Law:
$$R = \frac{V}{I} = \frac{V}{nq\mu\mathcal{E}A} = \frac{\mathcal{E}\ell}{nq\mu\mathcal{E}A} = \underbrace{\frac{1}{nq\mu}}_{\text{material}}\ \underbrace{\frac{\ell}{A}}_{\text{geometry}} \equiv \rho\,\ell/A\qquad\text{with } \rho = \frac{1}{nq\mu}\ [\Omega\cdot\mathrm{m}] = \text{resistivity.}$$

$\rho$ is an intensive (or intrinsic) material property — doesn't depend on size or shape.
$R$ is an extensive (or extrinsic) property — depends on size/shape.

We can also define the conductivity, $\sigma$, of a material as $\sigma = 1/\rho$ $\left[\dfrac{1}{\Omega\cdot\mathrm{m}}\text{ or S/m}\right]$, S = Siemens.

$\sigma$ or $\rho$ can also be used to derive a microscopic, or intensive, version of Ohm's Law:
$$I = V/R\ \text{(Ohm's Law)} = \frac{\mathcal{E}\ell}{\rho\ell/A} = \left(\frac{\mathcal{E}}{\rho}\right)A$$
(in the middle expression the denominator "$\rho\ell/A$" has a scribbled-over character after $\rho\ell$, corrected to $/A$)

$$\Rightarrow\ \frac{I}{A} = \frac{1}{\rho}\mathcal{E},\ \text{or}\ \boxed{J = \sigma\mathcal{E}}\quad\text{(microscopic version of Ohm's Law)}$$

What elements/materials act as semiconductors?

The most widely used semiconductor material is silicon (Si):

**Figure:** periodic-table tile: "14" top left, "Si" centred, "28.09" at the bottom.

- 14 protons + 14 neutrons (atomic mass $= 28$) + isotopes
- 14 electrons, including 4 valence electrons in outer shell
- Column IV (Group 14)

In a silicon crystal, each Si atom is bonded to its four nearest neighbor atoms:

**Figure:** left, "isolated Si atom": a circled "Si" with four single dots around it (above, below, left, right), one dot labelled "← electron", and caption "4 valence electrons" below. An arrow points right to "Si crystal": a 3×3 grid of circled "Si" atoms, each pair of horizontal and vertical neighbours joined by an oval containing two dots (a shared electron pair). One dot is labelled "electron"; one oval (right side, middle row) is bracketed and labelled "covalent bond".

## Page 3

(Page number "3" top right.)

At temperatures above absolute zero, some electrons have enough energy to "escape" from a covalent bond and become mobile (able to move through the Si crystal). The resulting "hole" that's left behind is also mobile:

**Figure:** left, a single circled "Si" with four two-dot bond ovals (up, down, left, right). Arrow to the right: the same Si atom, but the right-hand bond oval now contains only one dot; a free dot above-right is labelled "→ electron, charge $-q$", and the vacancy in the bond (an open small circle) is labelled "\"hole\", charge $+q$".

The concentration of electrons, and holes, created by this process is called the intrinsic concentration, $n_i$. For Si at 300 K, $n_i \approx 1\times 10^{10}\ \mathrm{cm^{-3}}$.

The concentrations of electrons and holes in a semiconductor can be changed by ~~[illegible, struck through, likely: adding]~~ replacing some of the semiconductor atoms, e.g., Si, with atoms that have more or fewer valence electrons:

**Figure (left):** "boron: ~~[scribble]~~ 3 valence electrons". A circled "Si" bonded (two-dot oval) to a circled "B" on its right; B has bond ovals above, below and to the right, but the bond to the right of B contains only one dot; an arrow from below labelled "hole" points at the vacancy.
Caption: hole created by B can move, leaving behind a ~~positively~~ negatively charged B ion. (The word "positively" is struck through and "negatively" written beneath it; a small scribbled-out blob follows.)

**Figure (right):** "phosphorus: 5 valence electrons". A circled "Si" bonded to a circled "P" on its right; P has four two-dot bond ovals (up, down, left, right) plus one extra dot above-right labelled "← electron".
Caption: electron introduced by P can move, leaving behind a positively charged P ion.

B is referred to as an "acceptor" since it can accept an electron to create an additional hole in the semiconductor.
P is referred to as a "donor" since it can donate an electron to the semiconductor crystal.

(Rest of page blank.)

## Page 4

(Page number "4" top right.)

Suppose
- $N_D$ = concentration of donors [m$^{-3}$]
- $N_A$ = concentration of acceptors [m$^{-3}$]
- $n_i$ = intrinsic concentration [m$^{-3}$].
- $n\ (p)$ = concentration of electrons (holes) [m$^{-3}$]

1) If $N_D = N_A$, then $n = p = n_i$
2) If $N_D \gg N_A$ and $N_D \gg n_i$, $n \approx N_D$ and $n \gg p$. Semiconductor is referred to as n-type (more electrons than holes)
3) If $N_A \gg N_D$ and $N_A \gg n_i$, $p \approx N_A$ and $p \gg n$. Semiconductor is referred to as p-type (more holes than electrons).

By combining n-type and p-type regions into a single semiconductor device, one can construct transistors, diodes, or other types of electronic devices.

**Metal-Oxide-Semiconductor Field Effect Transistors (MOSFETs)** (underlined)

NOTE: The material in this section was covered in ECE 302/302H (new version), but is not necessary for ECE 411.

Consider the following semiconductor structure (viewed in cross-section):

**Figure:** rectangular cross-section of a p-type Si substrate (labelled "p-type Si" in the lower part). Near the top surface, two U-shaped n-type wells labelled "n-type" on the left and right; between them the surface region is labelled "channel". Three contacts on top with open-circle terminals: "source (S)" over the left n-well, "gate (G)" over the channel (a horizontal plate line above the channel), and "drain (D)" over the right n-well.

As drawn here, the "channel" region is p-type Si, with electric current carried by holes.

The source and drain regions are n-type, with current carried by electrons.

In a typical MOSFET structure, it is very difficult for electrons to enter a p-type region, or holes an n-type region, unless voltages are applied.

## Page 5

(Page number "5" top right.)

The gate contact (G) in a MOSFET is used to enable electrons to travel between the source (S) and ~~[struck word, illegible]~~ drain (D), by applying a voltage to the gate that attracts electrons to the channel, thereby converting the channel to n-type:

**Figure (left):** MOSFET cross-section labelled "S", "G: $V_G = 0$", "D: $V_D > 0$" across the top. Two n wells in a p substrate; the S terminal and the substrate (bottom-left) are both tied to ground symbols. Caption: "$V_G = 0$: no current I ~~from~~ between source + drain." (the word "from" is struck through and replaced by "between").

**Figure (right):** same structure labelled "S", "$V_G > V_T > 0$", "$V_D > 0$" with a current arrow "$\downarrow I_D$" into the drain terminal. Under the gate, between the n wells, a row of dots with upward arrows (electrons drawn into the channel). S and substrate grounded. Caption: "$V_G > V_T > 0$: electrons attracted to channel region below gate $\Rightarrow I_D > 0$ since electrons can now travel from S to D."

**Margin text (right):** $V_T$ = threshold voltage = minimum voltage required to convert channel to n-type ($n > p$)

If one analyzes this structure in detail, $I_D$ vs $V_G$ looks like this:

**Figure:** $I_D$ (vertical) vs $V_G$ (horizontal). The curve is zero up to $V_G = V_T$ (marked on the axis with a small arrow and label "$V_T$"), then rises, concave up, with a dashed tangent line drawn along the rising portion extrapolating back to $V_T$.

$$I_D = (\text{constant})\left[(V_G - V_T)V_D - \tfrac12 V_D^2\right]$$

$I_D$ vs $V_D$ looks like this:

**Figure:** $I_D$ (vertical) vs $V_D$ (horizontal). Family of four curves from the origin: each rises then flattens to a horizontal plateau; higher plateaus for higher $V_G$. An upward arrow on the right is labelled "increasing $V_G > V_T$". The lowest curve, essentially flat along the axis, is labelled "$V_G < V_T$".

In circuits:

**Figure (left):** n-channel MOSFET symbol: gate terminal "G" on the left (open circle), with "$v_G$" marked + (at G) to − (at S) below it; drain "D" at top right (open circle) with current "$\downarrow i_D$" entering, and "$v_D$" marked + (at D) to − (at S); source "S" at bottom right (open circle), connected to ground. An arrow "→" points to the plot on the right.

**Figure (right):** $i_D$ vs $v_D$ family of curves (same shape as above), label "increasing $v_G$" with upward arrow. A dashed rectangle encloses the flat (saturation) portion of the curves, with a scribbled arrow from the caption "equivalent circuit model works here" pointing at that region. (A scribbled-out blob appears at the top left of the axes.)

Below the symbol: "III equivalent circuit" (the "III" is a scribbled mark before the words "equivalent circuit").

**Figure:** equivalent circuit. Gate terminal "G" (open circle, top left) with "$v_G$" marked + to − across a capacitor from G down to the bottom rail. Drain terminal "D" (open circle, top right) with current "$\downarrow i_D$" (partly scribbled over) flowing down through a diamond-shaped dependent current source labelled "$g\,v_G$" (arrow pointing down) to the bottom rail. The bottom rail connects the capacitor's lower plate, the dependent source's lower end, the source terminal "S" (open circle, bottom right) and a ground symbol.

## Page 6

(Page number "6" top right.)

For a more detailed discussion of these topics, see (for example):

B. G. Streetman and S. Banerjee, *Solid State Electronic Devices*
- semiconductor materials + crystals: Chapter 1 (5th ed.)
- electrons, holes, + energy bands: Chapter 3 (5th ed.)
- field-effect transistors: Chapter 6 (5th ed.)

(Rest of page blank, lined paper.)

## Index terms

basics of semiconductors, ECE 302/302H, electrical conductivity, impurity atoms, transistors, diodes, LEDs, solar cells, electron concentration n, electron charge q = 1.602×10⁻¹⁹ C, semiconductor resistor, cross-sectional area A, length ℓ, electric field E = −dφ/dx, electrostatic potential φ(x), V = Eℓ, drift velocity v = μE, mobility μ [m²/V·s], velocity saturation, high-field constant velocity, current density J = nqv = nqμE, total current I = JA, Ohm's law R = V/I, R = ρℓ/A, resistivity ρ = 1/(nqμ) [Ω·m], material vs geometry factors, intensive/intrinsic property, extensive/extrinsic property, conductivity σ = 1/ρ [S/m], Siemens, microscopic Ohm's law J = σE, silicon Si, atomic number 14, atomic mass 28.09, 4 valence electrons, Column IV Group 14, isolated Si atom, Si crystal, covalent bond, four nearest neighbors, thermal generation, mobile electron, hole, charge −q, charge +q, intrinsic concentration n_i ≈ 1×10¹⁰ cm⁻³ at 300 K, doping, boron 3 valence electrons, phosphorus 5 valence electrons, acceptor, donor, negatively charged B ion, positively charged P ion, N_D donor concentration, N_A acceptor concentration, n and p, n = p = n_i, n-type n ≈ N_D, p-type p ≈ N_A, MOSFET, metal-oxide-semiconductor field effect transistor, cross-section, source S, gate G, drain D, channel, p-type substrate, n-type wells, holes vs electrons as carriers, threshold voltage V_T, channel inversion n > p, V_G = 0 no current, V_G > V_T > 0 I_D > 0, I_D vs V_G curve, I_D vs V_D curves, I_D = const[(V_G−V_T)V_D − ½V_D²], saturation region, increasing V_G, MOSFET circuit symbol, i_D, v_D, v_G, equivalent circuit, gate capacitor, voltage-controlled current source g v_G, Streetman Banerjee Solid State Electronic Devices 5th ed., Chapter 1, Chapter 3, Chapter 6, not necessary for ECE 411
