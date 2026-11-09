---
course: ECE 411H
kind: refresher-notes
source: Refreshers/ECE_411H_cascaded_filters_notes_F26.pdf
source_pages: 5
author: Prof. Ed Yu
unit: exam2
topics: [cascaded-filters, active-filters, op-amp, band-pass-filter, band-reject-filter, low-pass-filter, high-pass-filter, inverting-amplifier, inverting-summing-amplifier, transfer-function, bode-plot, corner-frequency, poles-zeros, filter-design, two-stage-filter, 3db-point]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; captions from .vtt where present
deepgram_transcript: ../../Recordings/2026-11-02-cascaded-filters-refresher-session/transcript.txt
deepgram_paragraphs: ../../Recordings/2026-11-02-cascaded-filters-refresher-session/transcript.paragraphs.md
frames_with_speech: ../../Recordings/2026-11-02-cascaded-filters-refresher-session/frames/pages_with_speech.md
---

# Cascaded filters (recorded session notes, posted 2026-11-02)

**Summary**
Prof. Yu's handwritten tablet notes from the cascaded-filters refresher. Two worked examples. (1) Analysis of a cascaded band-pass filter: an inverting op-amp low-pass stage (1 kΩ input, 10 kΩ ∥ 9 nF feedback, $\omega_{0,1}\approx 11.1\times10^3$ rad/s) feeding an inverting high-pass stage (12 kΩ + 9 nF series input, 96 kΩ feedback, $\omega_{0,2}\approx 9.26\times10^3$ rad/s); the product transfer function $H(\omega)=80\,(j\omega/\omega_{0,2})/[(1+j\omega/\omega_{0,2})(1+j\omega/\omega_{0,1})]$ is factored into constant, zero at origin, two poles, and sketched as a Bode magnitude plot. (2) Design of a band-reject active filter: gain −50 outside a 20–40 kHz stop band with ±40 dB/decade roll-off, realised as a 2-stage low-pass ($H_{LP}$) in parallel with a 2-stage high-pass ($H_{HP}$) combined by an inverting summing amplifier; corner frequencies set by the −3 dB condition for a squared first-order response ($\omega_{LP}=\omega_1/(\sqrt2-1)^{1/2}=1.96\times10^5$ rad/s, $\omega_{HP}=(\sqrt2-1)^{1/2}\omega_2=1.62\times10^5$ rad/s), giving $R=1$ kΩ, $C_{LP}=5.1$ nF, $C_{HP}=6.2$ nF, $R_f=50$ kΩ; the full five-op-amp circuit is drawn. Exam relevance: this is the canonical Exam 2 cascade/filter-design pattern (multiply stage transfer functions, read off poles/zeros, Bode sketch, choose RC from the 3 dB condition).

> **Recording of this session** (video, Deepgram transcript, 351 board frames aligned to speech, QUALITY.md) is in `Recordings/2026-11-02-cascaded-filters-refresher-session/`. Prefer `frames/pages_with_speech.md` there over the Narration-free notes here when you need what was said about each page.

## Page 1

Small printed header, top left: "Recorded session notes"

**Example:** (underlined) cascaded band pass filter

**Figure:** two-op-amp cascade, drawn left to right.
- Source: $\underline{V}_s$ (phasor, tilde under the symbol), an independent voltage source with + on top and − on bottom, bottom terminal grounded.
- Stage 1 (labelled "1" inside the triangle, annotated "(low pass)" below): the source + terminal goes through a 1 kΩ resistor to the inverting (−) input of op-amp 1. The non-inverting (+) input is grounded. Feedback from the output back to the − input is a parallel combination of a 10 kΩ resistor (top branch) and a 9 nF capacitor (bottom branch); this parallel pair is circled in green and labelled $\underline{Z}_{f1}$ (green). The output node of op-amp 1 is labelled $\underline{V}_1$.
- Stage 2 (labelled "2", annotated "(high pass)" below): from $\underline{V}_1$ a 12 kΩ resistor in series with a 9 nF capacitor leads to the inverting (−) input of op-amp 2. The + input is grounded. A 96 kΩ feedback resistor connects the output of op-amp 2 to its − input.
- Output: $\underline{V}_{out}$ taken between the op-amp 2 output node (+ terminal, open circle) and ground (− terminal, open circle with ground symbol).

Op-amp 1 (low-pass filter):
$$\omega_{0,1} = \frac{1}{(10\,\mathrm{k}\Omega)(9\,\mathrm{nF})} = \frac{1}{9}\times 10^5\ \mathrm{rad/s} \approx 11.1\times 10^3\ \mathrm{rad/s}$$

$$\underline{Z}_{f1} = \frac{(10\,\mathrm{k}\Omega)\left(1/j\omega\,9\,\mathrm{nF}\right)}{10\,\mathrm{k}\Omega + \dfrac{1}{j\omega\,9\,\mathrm{nF}}}\ \underbrace{\left(\frac{j\omega\,9\,\mathrm{nF}}{j\omega\,9\,\mathrm{nF}}\right)}_{\text{green: multiply by 1}} = \frac{10\,\mathrm{k}\Omega}{1 + j\omega(10\,\mathrm{k}\Omega)(9\,\mathrm{nF})} = \frac{10\,\mathrm{k}\Omega}{1 + j\omega/\omega_{0,1}}$$

$$\underline{V}_1 = -\frac{\underline{Z}_{f1}}{1\,\mathrm{k}\Omega}\,\underline{V}_s = -\frac{10}{1 + j\omega/\omega_{0,1}}\,\underline{V}_s$$
(wavy underline beneath this result)

Op-amp 2 (high-pass filter):
$$\omega_{0,2} = \frac{1}{(12\,\mathrm{k}\Omega)(9\,\mathrm{nF})} = \frac{1}{108}\times 10^6\ \mathrm{rad/s} \approx 9.26\times 10^3\ \mathrm{rad/s}$$

$$\underline{V}_{out} = -\frac{96\,\mathrm{k}\Omega}{12\,\mathrm{k}\Omega + \dfrac{1}{j\omega\,9\,\mathrm{nF}}}\,\underline{V}_1 \cdot \underbrace{\left(\frac{j\omega\,9\,\mathrm{nF}}{j\omega\,9\,\mathrm{nF}}\right)\cdot\left(\frac{12\,\mathrm{k}\Omega}{12\,\mathrm{k}\Omega}\right)}_{\text{green: multiply by 1 twice}}$$

$$= -\frac{j\omega\cdot 9\,\mathrm{nF}\cdot 12\,\mathrm{k}\Omega}{1 + j\omega(9\,\mathrm{nF})(12\,\mathrm{k}\Omega)}\underbrace{\left(\frac{96\,\mathrm{k}\Omega}{12\,\mathrm{k}\Omega}\right)}_{8}\underline{V}_1;\qquad \omega_{0,2} = \frac{1}{(12\,\mathrm{k}\Omega)(9\,\mathrm{nF})}$$
(the bracket over $96\,\mathrm{k}\Omega/12\,\mathrm{k}\Omega$ is annotated "8")

$$= -\frac{8\cdot j\dfrac{\omega}{\omega_{0,2}}}{1 + j\dfrac{\omega}{\omega_{0,2}}}\,\underline{V}_1$$

$$\underline{V}_{out} = \left(\frac{8\,j\omega/\omega_{0,2}}{1 + j\omega/\omega_{0,2}}\right)\left(\frac{10}{1 + j\omega/\omega_{0,1}}\right)\underline{V}_s$$
(this last line is cut off at the bottom of page 1 and repeated at the top of page 2; the two negative signs have cancelled)

## Page 2

$$\underline{V}_{out} = \left(\frac{8\,j\omega/\omega_{0,2}}{1 + j\omega/\omega_{0,2}}\right)\left(\frac{10}{1 + j\omega/\omega_{0,1}}\right)\underline{V}_s$$

$$\underline{H}(\omega) = \frac{\underline{V}_{out}}{\underline{V}_s} = \underbrace{(80)}_{\text{constant}}\ \underbrace{\left(j\frac{\omega}{\omega_{0,2}}\right)}_{\text{zero @ origin}}\ \underbrace{\left(\frac{1}{1 + j\omega/\omega_{0,2}}\right)}_{\text{pole @ } \omega_{0,2} = 9.26\times 10^{3}\ \mathrm{rad/s}}\ \underbrace{\left(\frac{1}{1 + j\frac{\omega}{\omega_{0,1}}}\right)}_{\text{pole @ } \omega_{0,1} = 11.1\times 10^{3}\ \mathrm{rad/s}}$$

Bode magnitude plot:

**Figure:** axes $M(\omega)\,[\mathrm{dB}]$ (vertical) vs $\omega$ (horizontal, log scale implied). A tick on the vertical axis is labelled "$20\log 80$" with "$= M_0$" written beneath it ($M_0$ is the plateau level). The asymptotic curve: rises at "+20 dB/decade" (label with an arrow pointing at the rising segment) from the lower left, reaches the plateau at $\omega_{0,2}$ (dashed vertical line, labelled $\omega_{0,2}$ on the axis), stays flat at $20\log 80$ until $\omega_{0,1}$ (second dashed vertical line, labelled $\omega_{0,1}$, slightly to the right of $\omega_{0,2}$), then falls at "−20 dB/decade" (label with arrow pointing at the falling segment). The plateau between the two corner frequencies is narrow because $\omega_{0,2}$ and $\omega_{0,1}$ are close (9.26 k and 11.1 k rad/s).

**Example:** (underlined) band reject filter design

Design a band reject active filter with the following:
- (i) overall voltage gain $= -50$ outside the stop band.
- (ii) stop band from 20 kHz to 40 kHz ($\omega_1 = 40\pi$ krad/s $= 1.26\times 10^5$ rad/s, $\omega_2 = 80\pi$ krad/s $= 2.51\times 10^5$ rad/s)
- (iii) gain rolloff of $\pm 40$ dB/decade outside the stop band.

1) First, come up with overall design, then determine component values, etc.

(Bottom of page: the start of the target Bode sketch — "$M(\omega)\,[\mathrm{dB}]$" axis label and the top of a blue curve — is cut off and repeated in full at the top of page 3.)

## Page 3

**Figure:** target Bode magnitude sketch. Vertical axis $M(\omega)\,[\mathrm{dB}]$ with a tick labelled "$20\log 50$"; a short bracket just below that level is labelled "3 dB" (the −3 dB drop at the band edges). Horizontal axis $\omega$ with ticks labelled $10^4$, $10^5$, $\omega_1$, $\omega_2$, $10^6$ (log scale; $\omega_1$ and $\omega_2$ are between $10^5$ and $10^6$, close together). Blue curve: flat at $20\log 50$ from the left, dropping at "−40 dB/decade" (blue label with arrow) just past $\omega_1$ (dashed vertical line), then rising at "+40 dB/decade" (blue label with arrow) just before $\omega_2$ (second dashed vertical line), then flat at $20\log 50$ to the right. Dashed horizontal lines mark the $20\log 50$ level and the level 3 dB below it. A dotted/dashed V-shaped notch is drawn between the two dashed verticals. Under the axis, blue braces: the region around $10^5$ is labelled "2-stage low pass active filter $\underline{H}_{LP}(\omega)$"; the region around $10^6$ is labelled "2-stage high-pass active filter $\underline{H}_{HP}(\omega)$".

$$\underline{H}_{LP}(\omega) = \frac{1}{\left(1 + j\omega/\omega_{LP}\right)^2},\qquad \omega_{LP} = \frac{1}{R\,C_{LP}}$$

$$\underline{H}_{HP}(\omega) = \frac{\left(j\omega/\omega_{HP}\right)^2}{\left(1 + j\omega/\omega_{HP}\right)^2},\qquad \omega_{HP} = \frac{1}{R\,C_{HP}}$$

(A large right brace groups these two lines with the note:) for simplicity, choose the same $R$ values for resistors in $\underline{H}_{LP}$ and $\underline{H}_{HP}$.

Then combine using an inverting summing amplifier with gain $= -50$:

**Figure:** block diagram. $\underline{V}_s$ (open-circle input terminal on the left) splits into two parallel paths: the upper path goes through a box labelled $\underline{H}_{LP}(\omega)$ whose output node is labelled $\underline{V}_1$; the lower path goes through a box labelled $\underline{H}_{HP}(\omega)$ whose output node is labelled $\underline{V}_2$. Both $\underline{V}_1$ and $\underline{V}_2$ feed a box labelled "inverting summing amplifier with $G = -50$", whose output is $\underline{V}_{out}$ (open circle on the right).

2) Determine $R$ and $C_{LP}$:

$$M_{LP}(\omega) = \left|\underline{H}_{LP}(\omega)\right| = \left|\frac{1}{\left(1 + j\omega/\omega_{LP}\right)^2}\right| = \frac{1}{1 + (\omega/\omega_{LP})^2}$$

At the edges of the stop band ($\omega = \omega_1$, $\omega = \omega_2$) we want

(continues at top of page 4; the first line "$M(\omega) = 1/\sqrt2 \Rightarrow M_{LP}(\omega_1) = 1/\sqrt2$" is partly cut off at the page bottom)

## Page 4

(Top edge: cut-off repeat of "At the edges of the stop band (...)" from page 3.)

$$M(\omega) = \frac{1}{\sqrt2}\ \Rightarrow\ M_{LP}(\omega_1) = \frac{1}{\sqrt2}$$

$$\frac{1}{1 + \left(\dfrac{\omega_1}{\omega_{LP}}\right)^2} = \frac{1}{\sqrt2}\ \Rightarrow\ \left(\frac{\omega_1}{\omega_{LP}}\right)^2 = \sqrt2 - 1$$

$$\Rightarrow\ \omega_{LP} = \frac{\omega_1}{(\sqrt2 - 1)^{1/2}} = \frac{1.26\times 10^5\ \mathrm{rad/s}}{(\sqrt2 - 1)^{1/2}} = 1.96\times 10^5\ \mathrm{rad/s} = \frac{1}{R\,C_{LP}}$$

Let $\boxed{R = 1\,\mathrm{k}\Omega}$.

Then
$$C_{LP} = \frac{1}{R\,\omega_{LP}} = \frac{1}{(1\,\mathrm{k}\Omega)(1.96\times 10^5\ \mathrm{rad/s})} = \boxed{5.1\ \mathrm{nF} = C_{LP}}$$

3) Determine $C_{HP}$:

$$M_{HP}(\omega) = \left|\underline{H}_{HP}(\omega)\right| = \left|\frac{\left(j\omega/\omega_{HP}\right)^2}{\left(1 + j\omega/\omega_{HP}\right)^2}\right| = \frac{(\omega/\omega_{HP})^2}{1 + (\omega/\omega_{HP})^2}$$

We want $M_{HP}(\omega_2) = \dfrac{1}{\sqrt2}$

$$\Rightarrow\ \frac{(\omega_2/\omega_{HP})^2}{1 + (\omega_2/\omega_{HP})^2} = \frac{1}{\sqrt2}\ \Rightarrow\ \left(\frac{\omega_2}{\omega_{HP}}\right)^2 = \frac{1}{\sqrt2 - 1}$$

$$\Rightarrow\ \omega_{HP} = (\sqrt2 - 1)^{1/2}\,\omega_2 = (\sqrt2 - 1)^{1/2}\,(2.51\times 10^5\ \mathrm{rad/s}) = 1.62\times 10^5\ \mathrm{rad/s}$$

$$\omega_{HP} = \frac{1}{R\,C_{HP}}\ \Rightarrow\ C_{HP} = \frac{1}{R\,\omega_{HP}} = \frac{1}{(10^3)(1.62\times 10^5\ \mathrm{rad/s})} = \frac{1}{1.62\times 10^8} = \boxed{6.2\ \mathrm{nF} = C_{HP}}$$
(an arrow from the $R$ in $1/(R\,C_{HP})$ points down to "1 kΩ")

4) Design inverting summing amplifier with $G = -50$:

(Bottom of page: the top of the summing-amplifier schematic — "$R_f$" label and the start of its resistor — and the heading "KCL at inverting input:" are cut off and repeated in full at the top of page 5.)

## Page 5

**Figure:** inverting summing amplifier. Input $\underline{V}_1$ (open circle) through a resistor $R$ and input $\underline{V}_2$ (open circle) through a second resistor $R$ both join at the inverting (−) input node of an op-amp. The + input is grounded. A feedback resistor $R_f$ connects the op-amp output to the − input. The output $\underline{V}_{out}$ is taken between the output node (+, open circle) and ground (−, open circle with ground).

KCL at inverting input:
$$-\frac{\underline{V}_1}{R} - \frac{\underline{V}_2}{R} - \frac{\underline{V}_{out}}{R_f} = 0$$

$$\Rightarrow\ \underline{V}_{out} = -\frac{R_f}{R}\left(\underline{V}_1 + \underline{V}_2\right)$$

For $\boxed{R = 1\,\mathrm{k}\Omega}$, we choose $\boxed{R_f = 50\,\mathrm{k}\Omega}$

$$\Rightarrow\ \underline{V}_{out} = -50\left(\underline{V}_1 + \underline{V}_2\right)$$

5) Combine subcircuits into final circuit:

**Figure:** complete five-op-amp band-reject filter. $\underline{V}_s$ enters at an open-circle terminal on the far left and splits into an upper (low-pass) and a lower (high-pass) path.
- Upper path, stage A: series $R$ from $\underline{V}_s$ to the − input of op-amp A; + input grounded; feedback from output to − input is $R$ in parallel with $C_{LP}$ (the resistor $R$ drawn above the capacitor $C_{LP}$). Output of A goes through a series $R$ to the − input of op-amp B; + input grounded; feedback of B is again $R \parallel C_{LP}$. Output of B is the node $\underline{V}_1$.
- Lower path, stage C: series $R$ then series $C_{HP}$ from $\underline{V}_s$ to the − input of op-amp C; + input grounded; feedback resistor $R$ from output to − input. Output of C goes through series $R$ then series $C_{HP}$ to the − input of op-amp D; + input grounded; feedback resistor $R$. Output of D is the node $\underline{V}_2$.
- Summing stage: $\underline{V}_1$ through a resistor $R$ and $\underline{V}_2$ through a resistor $R$ both join at the − input of op-amp E; + input grounded; feedback resistor $R_f$ from output to − input. Output of E is $\underline{V}_{out}$, taken between the output node (+, open circle) and ground (−, open circle with ground symbol).

Rest of page is blank.

## Index terms

cascaded band pass filter, cascaded filters, active filter, op-amp low-pass stage, op-amp high-pass stage, inverting amplifier gain −Zf/Zin, feedback impedance Z_f1, 10 kΩ ∥ 9 nF, 1 kΩ, 12 kΩ series 9 nF, 96 kΩ, corner frequency ω₀,₁ = 1/((10kΩ)(9nF)) ≈ 11.1×10³ rad/s, ω₀,₂ = 1/((12kΩ)(9nF)) ≈ 9.26×10³ rad/s, V₁ = −10/(1+jω/ω₀,₁) Vs, gain 8, gain 10, overall gain 80, transfer function H(ω) = Vout/Vs, constant factor, zero at origin, pole at ω₀,₂, pole at ω₀,₁, Bode magnitude plot M(ω) dB, 20 log 80, M₀, +20 dB/decade, −20 dB/decade, band reject filter design, overall voltage gain −50, stop band 20 kHz to 40 kHz, ω₁ = 40π krad/s = 1.26×10⁵ rad/s, ω₂ = 80π krad/s = 2.51×10⁵ rad/s, ±40 dB/decade rolloff, 20 log 50, 3 dB, 2-stage low pass active filter H_LP(ω) = 1/(1+jω/ω_LP)², 2-stage high-pass active filter H_HP(ω) = (jω/ω_HP)²/(1+jω/ω_HP)², ω_LP = 1/(R C_LP), ω_HP = 1/(R C_HP), inverting summing amplifier, G = −50, block diagram, magnitude M_LP(ω) = 1/(1+(ω/ω_LP)²), M_HP(ω), 1/√2 condition at stop band edges, (ω₁/ω_LP)² = √2 − 1, ω_LP = ω₁/(√2−1)^{1/2} = 1.96×10⁵ rad/s, ω_HP = (√2−1)^{1/2} ω₂ = 1.62×10⁵ rad/s, R = 1 kΩ, C_LP = 5.1 nF, C_HP = 6.2 nF, R_f = 50 kΩ, KCL at inverting input, Vout = −(R_f/R)(V₁+V₂), five op-amp final circuit, parallel LP and HP paths, Prof. Ed Yu recorded session notes, posted 2026-11-02
