---
course: ECE 411H
date: 2026-09-30
instructor: Prof. Ed Yu
topics: [apparent power, power factor, power factor angle, maximum power transfer, Thevenin of phasor circuit, MOSFET/BJT equivalent circuits]
reading: Ulaby/Maharbiz/Furse §8-4 (power factor), §8-5 (max power transfer)
exam1_scope: "Exam 1 covers through the power factor angle (0:09:01). Max power transfer and everything after it are NOT on Exam 1."
sources: Recordings/2026-09-30/transcript.txt + frames (54 key pages + 4 neighbours viewed)
tags: [ece411, lecture, exam1]
---

# 2026-09-30: Power Factor, Maximum Power Transfer, Device Equivalent Circuits

> [!important] Exam 1 scope line
> After defining the power factor and power factor angle, Ed Yu wrote **"SEMESTER EXAM 1 COVERS TO HERE"** on the board (frame f_0064, 0:09:01) and said: *"this is the end of what you were responsible for, for the first semester exam."*
> - **On Exam 1:** complex power, $P_{av}$, $Q$, apparent power, power factor, power factor angle, and everything before them.
> - **Not on Exam 1:** maximum power transfer (§8-5) and semiconductors/devices.
> - The max-power-transfer example still drills core Exam-1 skills: a phasor Thevenin equivalent, voltage division, parallel impedances and rationalising. Work through it for P2 practice anyway.

## Summary

- **Recap:** $\tilde S = \tfrac12 \tilde V \tilde I^*$, $P_{av} = \mathrm{Re}[\tilde S]$ (average power dissipated in the load), $Q = \mathrm{Im}[\tilde S]$ ("peak power exchanged between source and load").
- **New definitions:**
  - Apparent power $S \equiv |\tilde S| = \sqrt{P_{av}^2 + Q^2} = V_{rms} I_{rms}$.
  - Power factor $\mathrm{pf} \equiv P_{av}/S = \cos(\phi_v - \phi_i)$.
  - Power factor angle $\phi_z \equiv \phi_v - \phi_i$.
- **Physical reading of pf:**
  - pf = 1 for a purely resistive load.
  - pf = 0 for a purely inductive or capacitive load ($\phi_z = \pm 90°$): no steady-state power reaches the load, it just sloshes back and forth.
  - For efficient transfer, make the load as close to purely resistive as possible.
- **Exam 1 cutoff:**
  - Exam 1 covers material up to the power factor angle.
  - Exam 2 and the final cover later material, with the earlier material "implicitly included".
- **Maximum power transfer (AC), derived by calculus:** set $\partial P_{av}/\partial R_L = 0$ and $\partial P_{av}/\partial X_L = 0$. The result is $\boxed{\tilde Z_L = \tilde Z_s^*}$, i.e. $R_L = R_s$ and $X_L = -X_s$, with $P_{av,max} = |\tilde V_s|^2/(8R_L)$.
- **Worked example (Ulaby Ex. 8-7):**
  - $\tilde V_{Th} = 17.3\,e^{j19.5°}$ V
  - $\tilde Z_s = 2.72 - j2.04\ \Omega$
  - $\tilde Z_L = 2.72 + j2.04\ \Omega$ (inductive)
  - $P_{av,max} = 13.8$ W
- **Q&A points:**
  - An RL or RC equivalent of an RLC network is valid only at one frequency.
  - Transients can't be represented by a single phasor; they are superpositions of many frequencies (Laplace/Fourier, later in the course).
  - Asking you to realise a numeric impedance with components is "fair game".
- **New unit (not Exam 1):** Semiconductors and solid-state devices.
  - MOSFET saturation-region model: gate–source capacitor plus a dependent current source $g\,v_{GS}$.
  - Diode I–V curve, and the pn junction as the building block.
  - BJT model: base–emitter resistor plus a dependent current source $\beta i_B$.

---

## Content

### 0:00:02 Announcements
See [[#Emphasis & exam intel]] for the verbatim quotes.
- Exam 1 is Wed Oct 7, in class, in person.
- Bring a printed answer-sheet template.
- Do the Gradescope upload-practice assignment.
- PS5 is due Mon Oct 5.
- Office hours today moved to 1–2:30 pm, EER 3.802 (?).

### 0:01:53 Recap: complex power (frames f_0035, f_0045, f_0048)
**Setup:** an **active** source circuit (at least one independent source) drives a **passive** load circuit (no independent sources).
- The load's Thevenin voltage is therefore 0, so the load is just a Thevenin impedance.
- $v(t)$ is defined + on top across the two connecting terminals.
- The current arrow runs from the source to the load along the top wire.

Phasors (amplitude/peak convention):
$$v(t) = V_m\cos(\omega t + \phi_v) \;\to\; \tilde V = V_m e^{j\phi_v}, \qquad i(t) = I_m\cos(\omega t+\phi_i) \;\to\; \tilde I = I_m e^{j\phi_i}$$

$$\text{complex power: } \tilde S = \tfrac12 \tilde V \tilde I^*$$
$$P_{av} = \mathrm{Re}[\tilde S] = \text{average power dissipated in load}$$
$$Q = \mathrm{Im}[\tilde S] = \text{peak power exchanged between source + load}$$

### 0:03:28 Why define more quantities (frame f_0054)
From the board: *"The source circuit provides the full voltage and current ($\tilde V$ and $\tilde I$), but only $P_{av}$ is received by the load. We can define:"*
- If the goal is to move power from source to load, $P_{av}$ is the useful quantity. The peak exchanged power $Q$ is less useful.
- The source must always supply the full $\tilde V$ and $\tilde I$, but only part of that turns into power the load actually receives.

### 0:05:38 Apparent power, power factor, power factor angle (frames f_0056, f_0059)
$$\textbf{apparent power: } S \equiv |\tilde S| = \sqrt{P_{av}^2 + Q^2} = V_{rms} I_{rms}$$
- $\sqrt{P_{av}^2 + Q^2}$ is just the magnitude of a complex number: add the squares of the real and imaginary parts and take the square root.
- $S$ is "in some sense the power being provided by the source", and the most that could possibly be transferred to the load.
- Check: $|\tilde S| = \tfrac12 V_m I_m = \tfrac{V_m}{\sqrt2}\tfrac{I_m}{\sqrt2} = V_{rms}I_{rms}$.

$$\textbf{power factor: } \mathrm{pf} \equiv \frac{P_{av}}{S} = \cos(\phi_v - \phi_i)$$
- The pf measures how efficiently power is transferred to the load.

$$\textbf{power factor angle: } \phi_z \equiv \phi_v - \phi_i$$
(This is also the angle of the load impedance, since $\tilde Z = \tilde V/\tilde I$; the board did not write that out.)

**Limiting cases (0:07:37):**
- $\phi_z = 0$ (purely resistive load) gives $\mathrm{pf} = 1$, the most efficient case.
- $\phi_z = \pm 90°$ (purely inductive or purely capacitive load) gives $\cos = 0$. No power is transferred to the load in steady state; it only goes back and forth.
- For efficient power transfer, make the load as close to purely resistive as possible.

> [!note] Not said in lecture
> He did **not** mention "leading/lagging" pf terminology or pf correction in this lecture. Check Ulaby §8-4 and Recitation 3 if those terms might appear.

### 0:08:55 Exam 1 cutoff (frame f_0064)
The board reads **"——— SEMESTER EXAM 1 COVERS TO HERE ———"**. See the exam-intel section for the quotes.

### 0:11:47 Maximum power transfer (Ulaby §8-5) (frames f_0070, f_0073, f_0079)
**DC recap (ECE 302):** with a fixed source resistance $R_s$, maximum power transfer happens at load resistance $R_L = R_s$.

**AC generalisation.** The general setup is an active AC circuit (source) connected to a passive circuit (load), with load phasors $\tilde V_L$ and $\tilde I_L$.
- Because the circuits are linear and sinusoidal, each side can be replaced by its Thevenin equivalent.
- Source side: $\tilde V_s$ (+ on top) in series with $\tilde Z_s = R_s + jX_s$.
- Load side: just $\tilde Z_L = R_L + jX_L$, since a passive circuit has zero Thevenin voltage.
- Single loop: $\tilde I_L$ flows clockwise into the top of $\tilde Z_L$, and $\tilde V_L$ is measured across the output terminals.
- The answer must reduce to $R_L = R_s$ at $\omega = 0$.

### 0:17:14 Load current and average power (frame f_0088)
$$\tilde I_L = \frac{\tilde V_s}{\tilde Z_s + \tilde Z_L} = \frac{\tilde V_s}{(R_s+R_L) + j(X_s+X_L)}$$
$$P_{av} = \tfrac12 |\tilde I_L|^2 R_L = \frac12\,\frac{|\tilde V_s|^2 R_L}{(R_s+R_L)^2 + (X_s+X_L)^2}$$
Maximise this over $R_L$ and $X_L$, with $\tilde V_s$, $R_s$, $X_s$ held constant. He calls it "a relatively simple problem in multivariable calculus."

### 0:19:33 Conditions for a maximum (frame f_0092)
From the board: *"To maximize power transfer, $P_{av}$, require $\dfrac{\partial P_{av}}{\partial R_L}=0$ and $\dfrac{\partial P_{av}}{\partial X_L}=0$ with $R_s, X_s, \tilde V_s$ fixed."*
- He also said the second derivatives must be negative (he first said "zero", then corrected himself).
- He left the second-derivative check to the students: "you can verify for yourself."

### 0:21:38 ∂/∂R_L (frame f_0121)
He used the quotient rule (derivative of the numerator × denominator − numerator × derivative of the denominator, all over the denominator squared):
$$\frac{\partial P_{av}}{\partial R_L} = \frac{|\tilde V_s|^2}{2}\left[\frac{(R_s+R_L)^2 + (X_s+X_L)^2 - R_L\cdot 2(R_s+R_L)}{\big[(R_s+R_L)^2+(X_s+X_L)^2\big]^2}\right] = 0$$
- The denominator is never zero except in the trivial all-zero case, so only the numerator matters.
- Expanding $(R_s+R_L)^2 - 2R_L(R_s+R_L) = R_s^2 - R_L^2$ gives
$$\Rightarrow\; \underline{R_s^2 - R_L^2 + (X_s+X_L)^2 = 0}$$

### 0:24:12 ∂/∂X_L (frames f_0130, f_0133)
The numerator does not depend on $X_L$, so its derivative is 0:
$$\frac{\partial P_{av}}{\partial X_L} = \frac{|\tilde V_s|^2}{2}\left[\frac{-R_L\cdot 2(X_s+X_L)}{\big[(R_s+R_L)^2+(X_s+X_L)^2\big]^2}\right] = 0$$
$$\Rightarrow R_L(X_s+X_L) = 0 \;\Rightarrow\; \underline{X_L = -X_s}$$
$R_L = 0$ is rejected because it makes $P_{av} = 0$.

### 0:26:43 Back-substitution (frames f_0135, f_0142, f_0145)
$$\text{Then } R_s^2 - R_L^2 = 0 \;\Rightarrow\; \underline{R_L = R_s}$$
$R_L = -R_s$ is rejected as "a pathological case where we have a runaway current because the total impedances cancel out."

### 0:27:54 Result (frames f_0196, f_0202)
$$\boxed{\tilde Z_L = \tilde Z_s^*,\ \text{i.e. } R_L = R_s \text{ and } X_L = -X_s}\quad\text{(max power transfer)}$$
- This one equation captures both conditions.
- Interpretation: the imaginary parts cancel, so the series $\tilde Z_s + \tilde Z_L$ is purely real, and the problem reduces to the DC condition $R_L = R_s$.

### 0:29:39 Maximum power (frames f_0208, f_0209, f_0210)
$$\text{Then } P_{av,max} = \frac18\,\frac{|\tilde V_s|^2}{R_L}$$
- Why $1/8$: the denominator is $(2R_L)^2 = 4R_L^2$, times the $\tfrac12$ in front.
- The second-derivative check is "not done explicitly here", but "it does turn out to be the maximum."
- My own check: the Hessian at the optimum is $\mathrm{diag}(-|\tilde V_s|^2/16R_s^3,\,-|\tilde V_s|^2/16R_s^3)$, which is negative definite, so it is a true maximum.

> [!tip] Unit check (my addition, not on board)
> The $\tfrac18$ applies because $|\tilde V_s|$ is an **amplitude** (peak). In rms terms, $P_{av,max} = V_{s,rms}^2/(4R_L)$, the familiar DC-like form.

### 0:31:10 Worked example: Ulaby Ex. 8-7 (frames f_0211, f_0214, f_0217)
**Circuit (source side):**
- $v_s(t)$ with + on top. Its top terminal goes through a series **4 Ω** resistor to node A.
- From node A to the bottom rail runs a shunt branch: a **60 µH** inductor in series with a **4 Ω** resistor.
- From node A a series **3.33 µF** capacitor goes to the top output terminal.
- The bottom rail is the lower output terminal.
- Load: $\tilde Z_L$ across the output terminals.

**Given:** $v_s(t) = 24\cos(10^5 t)$ V, so $\omega = 10^5$ rad/s.
**Task:** find $\tilde Z_L$ for max power transfer, and $P_{av,max}$.

**Step 0 (0:33:43), from class discussion:**
1. Convert to phasors.
2. Find the Thevenin equivalent of the source circuit. $\tilde Z_{Th}$ gives $\tilde Z_L$, and $\tilde V_{Th}$ is needed for the actual maximum power.

**Step 1: $\tilde V_{Th}$ = open-circuit voltage (0:35:07; frames f_0242, f_0273, f_0277, f_0308, f_0314)**
- Remove the load and find the voltage across the open terminals.
- The capacitor carries no current when the output is open, so it "is not going to affect the voltage of this terminal". The output voltage equals the voltage at node A.
- Node A comes from **voltage division** of $\tilde V_s$ over (L + 4 Ω) against the total (4 Ω + L + 4 Ω):
$$\tilde V_{oc} = \frac{j(10^5)(60\times10^{-6}) + 4}{8 + j(10^5)(60\times10^{-6})}\,\tilde V_s \quad\text{(by voltage division)}$$
- $\omega L = 10^5 \cdot 6\times10^{-5} = 6$, and the phasor of $24\cos(10^5t)$ is just $24$ V.
- Rationalise by multiplying by the conjugate of the denominator (written in green):
$$= \left(\frac{4+j6}{8+j6}\right)(24\text{ V})\left(\frac{8-j6}{8-j6}\right) = \frac{(4+j6)(8-j6)}{8^2+6^2}(24)$$
$$= \frac{32 + 36 + j48 - j24}{100}(24)$$
$$= 16.3 + j5.76 = \underline{17.3\,e^{j19.5°}\ \text{V}} = \tilde V_{Th,s}$$
- The angle is $\tan^{-1}(5.76/16.3) = 19.5°$.
- Exact values: $16.32 + j5.76$, $|\cdot| = 17.31$, $\angle 19.44°$.

**Step 2: $\tilde Z_s$ (0:41:29; frames f_0319, f_0337, f_0341, f_0346, f_0354, f_0373, f_0416, f_0428)**
- Option A: find $\tilde I_{sc}$ and use $\tilde Z_{Th} = \tilde V_{oc}/\tilde I_{sc}$.
- Option B, which he used as "a little bit easier": "essentially the external source method". Turn off the independent sources, so $v_s \to$ short circuit, then compute the equivalent impedance at the output terminals.
- From the board: *"To find $\tilde Z_s$, set $v_s(t)=0$ and calculate equivalent impedance at output terminals."*
- He stressed that you "always have to" turn off the sources in the external source method.

Topology with the source shorted: (4 Ω) ∥ (4 Ω + $j\omega L$), all in series with C. For two parallel branches, product over sum:
$$\tilde Z_s = \frac{1}{j\omega C} + \frac{(4\Omega)(4\Omega + j\omega L)}{4\Omega + 4\Omega + j\omega L}$$
$$= \frac{1}{j(10^5)(3.33\times10^{-6})} + \frac{4\big(4 + j(10^5)(60\times10^{-6})\big)}{8 + j(10^5)(60\times10^{-6})}$$
- $3.33\times10^{-6} = 0.333\times10^{-5}$, so $\omega C = 0.333 \approx \tfrac13$ and $1/(j\tfrac13) = -j3$.
$$= -j3 + \frac{4(4+j6)}{8+j6} = -j3 + \frac{4}{100}(4+j6)(8-j6)$$
$$= -j3 + \frac{1}{25}(68 + j24) = 2.72 - j2.04\ \Omega = \tilde Z_s$$

**Step 3: conjugate match (frame f_0401)**
$$\Rightarrow\ \boxed{\tilde Z_L = \tilde Z_s^* = (2.72 + j2.04)\ \Omega}$$
- He asked the class (0:50:35) whether the imaginary part is a capacitor or an inductor. It is an **inductor**, because it is $+j$. A capacitor gives $1/(j\omega C) = -j/(\omega C)$.
- The source's imaginary part is capacitive ($-j$), so the load must cancel it with an inductive one.
- Realisation (my addition): $L = 2.04/10^5 = 20.4\ \mu$H in series with $2.72\ \Omega$.

**Step 4: $P_{av,max}$ (0:51:30; frames f_0430, f_0440)**
- Only the magnitude of $\tilde V_{Th}$ matters; the phase drops out.
$$P_{av,max} = \frac{|\tilde V_{Th,s}|^2}{8R_L} = \frac{(17.3)^2}{8(2.72)} = \boxed{13.8\ \text{W} = P_{av,max}}$$

> [!check] Verification (python3 / sympy)
> - $j\omega L = j6$ exactly. $1/(j\omega C) = -j3.003$ (rounded to $-j3$).
> - $\tilde V_{oc} = 16.32 + j5.76 = 17.31\angle19.44°$ V ✓
> - $(4+j6)(8-j6) = 68 + j24$ ✓
> - Parallel part $= 2.72 + j0.96$, so $\tilde Z_s = 2.72 - j2.04$ ✓ ($-j2.043$ with exact C). A Norton cross-check gives $\tilde V_{oc}/\tilde I_{sc} = 2.72 - j2.04$ ✓
> - $P_{av,max} = 13.76$ W, which rounds to 13.8 ✓. A full-circuit check, $\tfrac12|\tilde I|^2R_L$ with the conjugate load, also gives 13.76 W ✓
> - Both partial-derivative numerators match sympy ✓

> [!warning] Board / verbal slips (none affect results)
> 1. **No numeric errors on the board.** Rounding is consistent: $16.32 \to 16.3$, and C = 3.33 µF is treated as exactly 1/3 × 10⁻⁵.
> 2. **0:20:08:** he first said the second derivatives "have to be zero", then corrected himself to "negative". Strictly, the Hessian must be negative definite; here it is.
> 3. **1:08:40:** he said "a **dependent voltage source** between the drain and the source". The board (f_0458) shows a **dependent current source** $g\,v_{GS}$, and he says "value of the current" at 1:09:06. It is a current source.

### 0:52:53 Student Q&A block
Covered in [[#Student questions]].

### 1:00:07 Wrap-up of phasors/power
- "This is everything that we wanted to say about phasors and power transfer and the like for now."
- Frequency-dependent behaviour will come back later.

### 1:00:43 Semiconductors and solid-state devices (NOT on Exam 1) (frames f_0445, f_0446, f_0450, f_0458, f_0483, f_0486)
**MOSFET recap from ECE 302/302H:**
- Terminals: drain D, source S, gate G.
- Two voltages control $i_{DS}$: $v_{DS}$ and $v_{GS}$.
- A full description would need a 3-D plot. Instead, plot $i_{DS}$ vs $v_{DS}$ as a family of curves, one per fixed $v_{GS}$, going up with increasing $v_{GS}$ (n-channel).

**Physics, n-channel:**
- A positive gate voltage electrostatically attracts electrons to the channel, so it conducts and a large $i_{DS}$ flows.
- An insufficient or negative gate voltage fails to attract electrons (or pushes them away), so the channel is resistive and only a small current flows.

**Linearising the flat region:**
- He asked which linear element could model the flat part. Answer: a **dependent current source**.
- In the flat region (boxed with a dashed line on the plot, labelled "equivalent circuit model works here"), the current is independent of $v_{DS}$, which is what a current source does.
- The current level depends on $v_{GS}$, so the source is dependent.

**MOSFET equivalent circuit (f_0458):**
- Gate G connects to source S through a **capacitor**, with $v_{GS}$ across it.
- Drain D connects to S through a **dependent current source** $g\,v_{GS}$, pointing D→S.
- The capacitor appears because applying a gate voltage charges it (electrons accumulate in the channel), but ideally no steady-state gate current flows.
- With this model, all the linear-circuit tools apply to transistor circuits.

**Diode (f_0494):**
- Symbol: arrow and bar. $V$ is + on the anode, and $I$ flows from + to − through the device.
- I–V curve: nearly zero current for negative $V$, exponentially increasing current for positive $V$.
- Based on the semiconductor **"pn junction"**, which is "really a very important type of device, not only for electronics".
- This part of the course will spend most of its time on the details of how the pn junction works.

**BJT (frames f_0495, f_0505, f_0508, f_0509, f_0523, f_0539):**
- Two back-to-back pn junctions; a 3-terminal device: C = collector, B = base, E = emitter.
- Emitter arrow pointing out means **npn**; pointing in toward the base means pnp.
- $i_C$ (collector→emitter) is controlled by the **base current** $i_B$, not by a voltage.
- On a plot of $i_C$ vs $v_{CE}$, each curve is flat for fixed $i_B$, and the curves step up with increasing $i_B$. The flat region is circled: "equivalent circuit model works here".

**BJT equivalent circuit (f_0509):**
- B connects to E through a **resistor**, with $i_B$ flowing in at B.
- C connects to E through a **dependent current source** $\beta i_B$ (C→E), with $i_C$ flowing in at C.
- $\beta$ is "typically called beta".

**Next lecture:** semiconductor details leading to the pn junction, which underlies BJTs, LEDs and solar cells.

---

## Ed Yu's conventions & notation
- **Phasors:**
  - Written with a tilde underneath ($\tilde V$, $\tilde I$, $\tilde Z$, $\tilde S$).
  - Lowercase $v_s(t)$ is the time-domain signal; $\tilde V_s$ is its phasor.
  - **Amplitude (peak) phasors**, which is why $\tilde S = \tfrac12\tilde V\tilde I^*$, $P_{av} = \tfrac12|\tilde I|^2R$ and $P_{av,max} = |\tilde V|^2/(8R)$.
- **Polar form:** written as $17.3\,e^{j19.5°}$, an exponential with the angle in degrees, not $\angle$ notation.
- **Impedances:** $\tilde Z = R + jX$. He uses $R_s, X_s$ / $R_L, X_L$ for source and load. The Thevenin voltage of the source is $\tilde V_{Th,s}$, and he also writes $\tilde V_{oc}$.
- **Power symbols:**
  - $P_{av}$ (subscript "av", not "avg"), $Q$, $S$ (apparent, no tilde), $\tilde S$ (complex).
  - pf written lowercase "pf".
  - Power factor angle $\phi_z \equiv \phi_v - \phi_i$; he uses $\equiv$ for definitions.
- **Q terminology:** $Q$ is described as the **"peak power exchanged between source and load"**, not just "reactive power". Use his phrase on P1.
- **Rationalising:** multiply by the conjugate of the denominator over itself (written in green), then use $|\text{den}|^2 = a^2 + b^2$.
- **Answer markup:** boxes final answers and wavy-underlines key intermediate results.
- **Circuit framing:**
  - "Active circuit" means at least one independent source; "passive" means none, so the Thevenin voltage is zero.
  - Thevenin impedance by "essentially the external source method": turn off independent sources (V-source → short).
- **References:** cites "Ulaby et al." section and example numbers (Ex. 8-7), and refers back to "302 or 302H" constantly.
- **Dependent sources:** drawn as diamonds with an arrow inside.

## Intuition & explanations he gives
- **Why define pf (0:04:16):** "The source circuit still, it always has to provide this full voltage and current, but then only some part of that ends up being translated into power that's transferred to and received by the load."
- **Apparent power (0:06:28):** "It's in some sense the power that's being provided by the source, and it is kind of the maximum that you could potentially get transferred to the load."
- **pf as efficiency (0:06:49):** "this is kind of a measure of how efficiently that power is transferred to the load."
- **pf = 1 (0:07:37):** "if the difference between the phases of the voltage and the current is zero, that is, we have a purely resistive load, then the power factor is one. That means that we're in some sense being as efficient as possible in transferring power from the source to the load."
- **pf = 0 (0:08:01):** "If the power factor angle is plus or minus 90 degrees, that is where the load is purely inductive or purely capacitive, then the cosine of that is zero, and we actually are not, in steady state, transferring any power from the source to the load. We're just transferring power back and forth. But none of it is actually received in steady state by the load."
- **Design rule (0:08:43):** "if you want to have efficient power transfer, then what you want is to have the load be as close to purely resistive load as possible."
- **More reactance means lower pf (0:10:26):** "the average power was proportional to the real part of the load impedance, and the reactive power Q was proportional to the imaginary part of the load impedance. So if the imaginary part is getting bigger, then the power factor will become smaller. Or another way you can think about it is that that's going to push the phases of the voltage and the current farther and farther out of phase."
  - Follow-up: "if the real part of the load impedance stayed the same, and the current stayed the same, then the power received by the load would still be the same, but the power transferred back and forth would increase. But in practice, you'll also change the current."
- **Thevenin is always available (0:15:47):** "we're assuming here that the circuits are linear. We can always represent these circuits using their Thevenin equivalents." A passive load's Thevenin equivalent "is just going to be an impedance."
- **Why conjugate matching works (0:28:49):** "if the imaginary parts cancel each other out then the total impedance of the source and the load in series is just real. And then we sort of get back to the condition where the load resistance has to be equal to the source resistance."
- **Why reject $R_L = -R_s$ (0:27:03):** "that gives us sort of a pathological case where we have a runaway current because the total impedances cancel out."
- **Why reject $R_L = 0$ (0:26:22):** "then the average power transferred [is] zero."
- **Why the capacitor drops out of $V_{oc}$ (0:35:45):** "this capacitor over here is not going to affect the voltage of this terminal. The voltage of this terminal here is going to be the same as the voltage over here [node A]." (No current flows through it when the output is open.)
- **Inductor or capacitor? (0:50:35):** "An inductor because it's plus j. If it were a capacitor it would be minus j, because the impedance of the capacitor is one over j omega C which is the same as minus j over omega C. Whereas the source had an equivalent impedance that has a minus j, so its imaginary part is capacitive. So that means that the load sort of has to cancel that out."
- **Equivalent circuits (0:54:50):** "If they are equivalent circuits then by definition they exhibit exactly the same electrical behavior at the terminals. So you wouldn't then be able to tell just from the current and voltage behavior what's happening inside that circuit."
- **Frequency dependence of equivalents (0:56:13, 0:57:41):** "at any given frequency you can write down a Thevenin equivalent for any linear circuit. But then at some other frequency that Thevenin equivalent circuit may be different. So there's not a single unique Thevenin equivalent circuit that will represent an equivalent at all frequencies."
  - Example: a series RLC behaves like an RL or an RC at a given frequency, but a different one at another frequency.
- **Transients vs phasors (0:59:02):** "during that transient it's not that it is operating at just a single frequency as a sinusoidal signal. An exponential transient decaying towards the steady state cannot be represented by just a single frequency sinusoidal signal but it can be represented as a superposition of many different frequencies. And then at each of those constituent frequencies you could do the phasor type analysis." That leads to Laplace and Fourier transforms, "the last part of the course".
- **MOSFET as a dependent current source (1:07:10):** "for any given fixed value of the gate voltage, we have a current that is independent of the voltage VDS. And that's sort of the definition of the behavior of a current source, but it is going to be a dependent current source because the level of the current depends on the voltage applied to the gate."
- **Gate as a capacitor (1:09:20):** "when you apply a voltage to the gate, then you can charge up the capacitor. That corresponds to accumulating electrons in this region. But ideally, there is no current flow, at least in steady state, between the gate and the source. So that's the behavior of a capacitor."

## Emphasis & exam intel
**Every Exam-1 statement, verbatim (ASR-cleaned):**
1. **[0:00:02]** "a reminder that the first semester exam will be a week from today. So that is Wednesday, October 7th. It'll be in class, in person."
2. **[0:00:18]** "there are details about the exam that are posted on Canvas. One thing that you should make sure to do coming to the exam is to bring physical copy that is printed on paper of the answer sheet template that you'll write your exam solutions on."
3. **[0:00:36]** "that is available or it will be available on Gradescope and Canvas sometime later this week."
4. **[0:00:45]** "there's an exam upload practice assignment that's on Gradescope and you can use that to practice or debug your scanning and uploading process. So you should make sure to do that before the exam so that it goes smoothly for the actual exam itself."
5. **[0:08:55] (scope)** "this is the end of what you were responsible for, for the first semester exam. So semester exam one, this will cover material to this point."
   - Board (0:09:01): **"SEMESTER EXAM 1 COVERS TO HERE"**, drawn immediately after the power factor angle $\phi_z \equiv \phi_v - \phi_i$.
6. **[0:09:13] (later exams)** "the second semester exam and the final exam will cover effectively the material that we've covered up to this point, plus the things that we'll be talking about subsequently. The earlier material is sort of implicitly included in the second semester exam because it's really the foundation for what we do subsequently."
7. **[0:41:42] (calculator/grading)** A student asked whether converting to polar on a calculator is OK. Answer: "Yes. You can do that. And as long as you plug the numbers into your calculator correctly then that'll be fine. If you make a mistake and didn't explain what you were doing then you know we can't give you credit for that incorrect answer. Or any reasoning that is not explained."
8. **[0:52:53] (question style)** A student asked whether building or realising the load from components is fair game. Answer:
   - "I would say that's fair game. Because it's actually quite easy to do."
   - "If you're given a numeric complex number numerical value for an impedance, it's always going to be a real part plus or minus some imaginary part. And you can always represent that as a resistor in series with either [an inductor or capacitor]."
   - "If you're given some components that have odd values or whatever, or if you can't combine the reactive components to get the right impedance, … or [if] the question was to explain why did it work out that way, then I would consider something like that to be fair game. Because it requires and [would] test some understanding of what kind of impedance different components give you."
   - Note: this exchange came after the scope cutoff, in the max-power context, so it is general exam-style intel. The skill itself (impedance → component) is Exam-1 material.

**Related logistics (not exam content):**
- PS5 (basic power calculations) is due **Mon Oct 5**.
- Office hours on 9/30 moved to **1–2:30 pm**, same room (EER 3.802 (?)).

**Not mentioned this lecture:**
- No review session.
- No statement on allowed materials (formula sheet, calculator rules) or exam length; "details … posted on Canvas".
- No list of what to study beyond the scope line.

**Top emphasis items:**
1. **Scope:** Exam 1 ends at the power factor angle. Apparent power, pf and $\phi_z$ are in; max power transfer and devices are out.
2. **Written reasoning:** unexplained calculator mistakes earn zero, and so does "any reasoning that is not explained". Show every step: write the rectangular→polar conversion, show the rationalisation, state the method (voltage division, source-off).
3. **pf physics:** resistive load gives pf = 1 (most efficient); purely L or C gives pf = 0, with power only going back and forth. More reactance pushes V and I out of phase.
4. **Phasor Thevenin skills:** open-circuit voltage by voltage division (and noticing elements that carry no current), and $\tilde Z_{Th}$ by turning off independent sources ("you always have to do that in the external source method").
5. **Impedance ↔ component reasoning:** $+j$ means inductive, $-j$ means capacitive. Realising a numeric impedance and explaining why is "fair game". Equivalents hold at one frequency only.

**Exam logistics:** bring the printed answer-sheet template, and run the Gradescope upload practice beforehand.

## Student questions
1. **[0:09:44] More reactance means lower pf?** "The heavier the inductive/capacitive components relative to the resistance, the lower the power factor?"
   - Yes, generally. $P_{av}$ goes with $\mathrm{Re}\,\tilde Z_L$ and $Q$ with $\mathrm{Im}\,\tilde Z_L$, so a growing imaginary part lowers pf. It also pushes V and I further out of phase.
   - **Follow-up:** "If R stays at, say, 10 and the imaginary part grows, the angle increases?" Yes. With the same real part and the same current, received power is unchanged but the power exchanged back and forth increases. In practice the current changes too.
3. **[0:33:43] (he asked) First step for the example?** Students said: use phasors, then find the Thevenin equivalent of the source circuit. Both $\tilde Z_{Th}$ (for $\tilde Z_L$) and $\tilde V_{Th}$ (for $P_{max}$) are needed.
4. **[0:35:07] (he asked) How to find $\tilde V_{Th}$?** Remove the load and compute the open-circuit voltage.
5. **[0:41:42] Can I convert to polar on the calculator?** Yes, if done correctly. An unexplained mistake gets no credit (quote above).
6. **[0:50:35] (he asked) Is the load's imaginary part an inductor or a capacitor?** An inductor, because of the $+j$; it cancels the source's capacitive $-j$.
7. **[0:52:53] Is "realise this impedance with components" fair game?** Yes. See the full answer in the exam-intel section.
8. **[0:54:35] Can any RLC network be reduced to one complex number?** Yes, its equivalent impedance.
   - Equivalent circuits behave identically at the terminals, so you can't tell what's inside from V and I alone.
   - "You may be able to tell from things like is it dissipating a lot of power" (?).
9. **[0:55:37] Why build complex RLC circuits if an R∥L or R∥C (sic) can represent any impedance?**
   - The equivalence holds only at the two terminals and at one frequency.
   - A series RLC looks like an RL or an RC at one frequency, but a different equivalent at another frequency, so they are not truly equivalent.
10. **[0:57:00] Is there a Thevenin equivalent for the transient part?**
    - At any single frequency, any linear circuit has a Thevenin equivalent, but it changes with frequency.
    - A transient (e.g. a decaying exponential after a switch) isn't a single-frequency sinusoid, so phasors can't represent it directly.
    - It is a superposition of many frequencies, which leads to Laplace and Fourier transforms later.
11. **[1:07:07] (he asked) Which linear element models the flat MOSFET region?** A student said a dependent current source. Correct.
12. **[1:10:24] Is that region saturation, and how do we know we're in it?**
    - Yes, it is saturation.
    - There are well-defined relationships: the drain voltage must be sufficiently large for a given gate voltage, and that threshold rises with gate voltage. Details are in ECE 302.
    - The course will focus on a different device (the BJT) rather than MOSFETs.
    - **Follow-up:** "Is the model only valid once we're sure we're in saturation?" Yes. Outside that region you need something else; this is the simplest version, and you add elements for more detail.

## Exam relevance
| Exam slot | What from this lecture maps | Notes |
|---|---|---|
| **P1 (four "explain why")** | pf meaning; why resistive gives pf = 1 and reactive gives pf = 0; why more reactance lowers pf; meaning of $P_{av}$ vs $Q$ ("peak power exchanged") vs apparent $S$; why a capacitor in series with an open output doesn't affect $V_{oc}$; $+j$ means inductor, $-j$ means capacitor; why an RL/RC equivalent of an RLC network holds at one frequency only; why phasors can't capture transients | Highest-yield lecture content for P1. Quote his phrasing ("back and forth", "none of it is actually received in steady state"). |
| **P2 (numeric phasor ladder)** | The Ex. 8-7 mechanics: $j\omega L$, $1/(j\omega C)$, voltage division, product-over-sum parallel combination, rationalising with the conjugate, rect→polar; Thevenin by open-circuit voltage plus source-off impedance | The example's source network *is* a small ladder. A P2 tail may ask for $\tilde S$, $P_{av}$, $Q$, $S$, pf of a load (in scope); a max-power tail is out of scope per 0:08:55. |
| **P3 (two-op-amp impedance synthesizer)** | Indirect: realising a numeric impedance with R plus L or C ($L = X/\omega$, $C = 1/(\omega\lvert X\rvert)$); the sign of the imaginary part tells you the element type | His "fair game" answer applies directly to synthesizer "what element does this emulate / explain why" parts. |
| **P4 (2nd-order RLC transient)** | Only the Q&A: transients are not single-frequency, so use time-domain ODE methods, not phasors | No new P4 content. |

**Likely question variants (in scope):**
- Given $\tilde V$ and $\tilde I$ (or $\tilde Z_L$ and a source), compute $\tilde S$, $P_{av}$, $Q$, $S = V_{rms}I_{rms}$, pf $= \cos\phi_z$, and $\phi_z$.
- "Explain why a purely capacitive load draws current but absorbs no average power."
- "Explain why the pf decreases as $X_L$ grows with $R_L$ fixed."
- "Explain why the source must supply $S$ even though the load only receives $P_{av}$."
- Given a numeric $\tilde Z$ at $\omega$, name and size the series R + L or R + C realisation, and explain why it fails at another frequency.

**Out of Exam-1 scope per the instructor, but core later:** $\tilde Z_L = \tilde Z_s^*$, $P_{av,max} = |\tilde V_{Th}|^2/(8R_L)$, device equivalent circuits.
