---
course: ECE 411H
date: 2026-08-31
instructor: Prof. Ed Yu
topics: [op-amp terminals and currents, transfer characteristic, linear vs saturation regions, finite-gain equivalent circuit, ideal op-amp model, golden rules, negative feedback, non-inverting amp, inverting amp, inverting summing amp, non-inverting summing amp, difference amp, voltage follower/buffer]
reading: Ulaby/Maharbiz/Furse Ch. 4 (§4-1, §4-2 for basic characteristics) and §5-6
exam1_scope: Yes. Op-amps are the foundation for Exam 1 P3 (two-op-amp impedance synthesizer).
sources: Recordings/2026-08-31/transcript.txt + frames (all 53 listed in pages.txt, plus neighbours f_0032, f_0047, f_0339, f_0340)
tags: [ece411, lecture, exam1, op-amps]
---

# 2026-08-31: Op-Amps: Ideal Model and Basic Amplifier Circuits

> [!info] What this lecture is (and is not)
> - It is all **DC and symbolic**: there are no numeric worked examples. Every result is a formula in resistor ratios.
> - Op-amps with **capacitors and inductors**, and circuits with **multiple op-amps**, were announced for "the next couple classes" (0:06:33). Those are the direct precursors of Exam 1 P3; this lecture supplies the rules they rest on.
> - Any numbers in this note are **my own checks**, labelled as such.

## Summary

- **Terminals and KCL:** an op-amp has inputs $v_p$ (non-inverting, +) and $v_n$ (inverting, −), output $v_o$, and supply pins $\pm V_{cc}$.
  - KCL over the whole chip is $i_o = i_p + i_n + i_+ + i_-$.
  - The **supply pins carry current**, so the input currents do **not** equal the output current.
- **Transfer characteristic:** $v_o$ vs $(v_p - v_n)$ has three regions.
  - Linear region: $v_o = A(v_p - v_n)$, with open-loop gain $A \sim 10^4$–$10^8$.
  - Positive and negative saturation: $v_o$ is pinned at $\pm V_{cc}$.
  - Course assumption: the op-amp is always in its linear region.
- **Linear-region equivalent circuit:**
  - $R_i$ across the inputs.
  - A dependent voltage source $A(v_p - v_n)$ to ground, in series with $R_o$, feeding the output.
  - Typical values: $R_i \sim 10^6$–$10^{13}\,\Omega$, $R_o \sim 1$–$100\,\Omega$, $V_{cc} \sim 5$–$24$ V.
- **Ideal limits:** $A\to\infty$, $R_i\to\infty$, $R_o\to 0$. These give the **golden rules**:
  - $v_p = v_n$
  - $i_p = i_n = 0$
  - the output supplies whatever $i_o$ is needed to make the first two true.
  - Always also check $-V_{cc}\le v_o\le +V_{cc}$.
- **Negative feedback:** the golden rules and linear operation assume negative feedback (output connected to $v_n$, often through a resistor). Feedback to $v_p$ drives the op-amp into saturation.
- **Five amplifier circuits derived:**
  - Non-inverting: $v_o = \frac{R_1+R_2}{R_2}v_s$
  - Inverting: $v_o = -\frac{R_f}{R_s}v_s$
  - Inverting summing: $v_o = -\frac{R_f}{R_1}v_1 - \frac{R_f}{R_2}v_2$
  - Non-inverting summing: $v_o = \frac{R_3+R_4}{R_4}\left[\frac{R_2}{R_1+R_2}v_1 + \frac{R_1}{R_1+R_2}v_2\right]$
  - Difference: $v_o = \frac{R_1+R_2}{R_1}\frac{R_4}{R_3+R_4}v_2 - \frac{R_2}{R_1}v_1$
- **Design idea ("KCL is a condition on a sum of voltages"):**
  - Each "source + series resistor" attached to an op-amp input node adds one weighted term to the KCL sum.
  - This is how you **design** summing and difference circuits, not just analyse them.
- **Voltage follower / buffer:** $v_o = v_s$. It draws no current from the source, so the output does not depend on the load.

---

## Content

### 0:00:04 Announcements (frame f_0004)
- **Problem Set 1** is due **9:00 AM CDT Wed Sep 9**. **Problem Set 2** is due **9:00 AM CDT Mon Sep 14**. Submit both as PDFs on Canvas.
- Travel week of Sep 14–18: **no class or office hours Wed Sep 16**.
  - He will record a lecture and post it on Canvas by the end of Sep 16.
  - It picks up where the Sep 14 class ends.
  - Watch it before **Mon Sep 21**, which picks up where the recording ends.

### 0:01:54 Study-method point from the "tips" handout
See [[#Emphasis & exam intel]]. In short:
- After solving a problem, go back and analyse what worked and why.
- Write a clean solution that explains your reasoning, as he did as a student.
- He said this "carries over to exams".

### 0:05:06 Topic and reading (frame f_0014)
Board: **"Operational Amplifiers. Reading: Ulaby et al Chap. 4, Sec. 5-6."**

Plan for the op-amp unit:
1. Review the basic characteristics.
2. DC op-amp circuits. The class background survey showed inverting and non-inverting amps were well remembered, but summing and difference amps were "fuzzier".
3. Circuits with **multiple op-amps**.
4. Op-amps **plus capacitors or inductors**, which "behave a little bit differently and give you different functionality".

### 0:07:12 Basic op-amp characteristics (frames f_0014, f_0022, f_0027, f_0028)
Board: **"Basic op-amp characteristics. Reading: Ulaby et al, Secs. 4-1, 4-2."**

**Circuit symbol (f_0022):**
- Triangle with the **+ input on top** labelled $v_p$ and the **− input below** labelled $v_n$.
- Output at the apex labelled $v_o$.
- $+V_{cc}$ pin on the top edge and $-V_{cc}$ pin on the bottom edge.

**Current reference directions (as drawn):**
- $i_p$: arrow **into** the + input.
- $i_n$: arrow **into** the − input.
- $i_o$: arrow **out of** the output.
- $i_+$: arrow **down into** the $+V_{cc}$ pin.
- $i_-$: arrow **up into** the $-V_{cc}$ pin.

**Terminology (board):**
- $v_p$ = non-inverting (or "positive") input voltage.
- $v_n$ = inverting (or "negative") input voltage.
- $+V_{cc}$ = positive supply voltage; $-V_{cc}$ = negative supply voltage.
- $v_o$ = output voltage.

He explained that "positive" and "negative" refer to the terminal symbol (+ or −), "not necessarily because their values are always positive or negative".

**KCL on the whole op-amp (0:10:39):**
$$\boxed{i_o = i_p + i_n + i_+ + i_-}$$
- $i_o$ is the only current drawn **leaving** the chip; the other four are drawn entering.
- Because the supply pins carry current, you **cannot** say that the sum of input currents equals the output current. He called this "the key thing here" (quote in the exam-intel section).

### 0:12:18 Transfer characteristic (frames f_0032, f_0040, f_0044, f_0045)
Board: *"The functional behavior, or transfer characteristic, of an op amp can be plotted as follows:"*
- Even though $v_p$ and $v_n$ can be set independently, **only the difference $v_p - v_n$ matters** for the op-amp's function.
- **Plot:** horizontal axis $v_p - v_n$; vertical axis $v_o$, with ticks at $+V_{cc}$ and $-V_{cc}$.
- **Green curve:**
  - A very steep line through the origin.
  - It bends into a flat line at $+V_{cc}$ on the right and at $-V_{cc}$ on the left.
  - Dashed vertical lines mark the narrow linear band.
- **Three regions (labelled on the board):**
  - **Linear region** (near the origin, $v_p \approx v_n$):
    $$v_o = A(v_p - v_n),\qquad A = \text{open-loop gain, typically} \sim 10^4\text{–}10^8$$
  - **Positive saturation region** (right): $v_o$ pinned at $+V_{cc}$.
  - **Negative saturation region** (left): $v_o$ pinned at $-V_{cc}$.
- **Why saturation exists:** the output "is not able to exceed the bounds of those supply voltages". A linear relation at large $|v_p - v_n|$ would demand an output that is "too large in magnitude".
- Because $A$ is so large, the line is very steep. Being in the linear region therefore means being "very close to the condition that $v_p$ is equal to $v_n$". The ideal-model version of this is $v_p = v_n$ exactly.
- Board: **"We will typically assume the op amp is operating in its linear region."**
  - The reason: the circuits "will have been designed in a way that basically keeps the circuit and the op amp in its linear region".
  - He said this is the same assumption as in EE 302/302H.

> [!tip] Width of the linear band (my arithmetic from his numbers)
> The linear region spans $|v_p - v_n| \le V_{cc}/A$. For example, $V_{cc} = 10$ V and $A = 10^6$ give $\pm 10\ \mu$V. This is why "linear region" and "$v_p \approx v_n$" mean the same thing.

### 0:19:12 Op-amp equivalent circuit for the linear region (frames f_0047, f_0051)
Board: *"Op amp equivalent circuit for linear region of operation:"*

The model is drawn **inside** an enlarged op-amp triangle.
- **$R_i$** connects the $v_p$ terminal to the $v_n$ terminal.
  - The voltage across it is $(v_p - v_n)$, + at the $v_p$ end.
  - $i_p$ flows in at $v_p$ and $i_n$ flows in at $v_n$.
- **Dependent voltage source $A(v_p - v_n)$** (a diamond, + on top).
  - Its − terminal goes to **ground**; its + terminal goes to $R_o$.
- **$R_o$** sits in series between the dependent source and the output terminal $v_o$; $i_o$ flows out.

That is the entire model: two resistors and one voltage-controlled voltage source.

**Parameter table (f_0051, f_0059):**

| parameter | typical value | "ideal" value |
|---|---|---|
| $A$ = open-loop gain | $10^4$–$10^8$ | $\infty$ |
| $R_i$ = input resistance | $10^6$–$10^{13}\ \Omega$ | $\infty$ |
| $R_o$ = output resistance | $1$–$100\ \Omega$ | $0$ |
| $V_{cc}$ = supply voltage | 5 to 24 V | (none) |

**Notes he gave on each parameter:**
- **$A$ (0:26:37):**
  - Take $A = 10^6$. Then $v_p - v_n = 1\ \mu$V already gives $v_o = 1$ V, and $10\ \mu$V gives 10 V. (The ASR says "amps"; see the warning below.)
  - The idealisation of an almost-vertical line is a vertical line with infinite slope, and that gives $v_p = v_n$.
- **$R_i$ (0:28:08):**
  - It is "the resistance the inputs see". It is very high, so it is idealised as infinite.
  - That gives $i_p = i_n = 0$: if $R_i = \infty$ and the currents were nonzero, the voltages would be infinite.
- **$R_o$ (0:29:37):**
  - It is small. A nonzero $R_o$ causes a voltage drop when $i_o$ is large, so it **limits how much current the output can deliver**.
  - With $R_o = 0$, "in principle any amount of current can come out of the op-amp output and we will still get this voltage".
- **$V_{cc}$ (0:33:06):**
  - Supplies are usually not drawn in circuit diagrams because they clutter them, but "we should always remember that they are present".
  - $V_{cc}$ is specific to the op-amp. There is **no ideal value** for it.

> [!warning] Transcript slip
> At 0:27:17 he says an output of "one amp" and "10 amps". He means **1 V** and **10 V**, since $A\,(v_p - v_n)$ is a voltage. Check: $10^6 \times 10^{-6}$ V = 1 V and $10^6 \times 10^{-5}$ V = 10 V.

### 0:33:54 Ideal op-amp model and golden rules (frames f_0071, f_0077, f_0090, f_0095)
Board: *"The 'ideal' parameter values for the op amp equivalent circuit model then lead to the **ideal op amp model**, which we will use for most op amp circuit analysis + design."*

$$\begin{aligned}
A&\to\infty &&\Longrightarrow\quad v_p = v_n\\
R_i&\to\infty &&\Longrightarrow\quad i_p = i_n = 0\\
R_o&\to 0 &&\Longrightarrow\quad \text{output can provide any } i_o \text{ required to satisfy } v_p=v_n \text{ and } i_p=i_n=0
\end{aligned}$$

- A brace on the board labels these three as **"golden rules" of op amp behavior**.
- Below them is a separate line he says to "always remember":
$$\boxed{-V_{cc} \le v_o \le +V_{cc}}$$

- **Why $A\to\infty$ forces $v_p = v_n$** (answering a student at 0:38:05):
  - If $v_p \ne v_n$, then $v_o = A(v_p - v_n)$ would be infinite.
  - With $v_p - v_n = 0$, "infinity times 0 can be anything". That "anything" is "whatever output voltage is required to get the other two things to be true".

### 0:39:09 Negative feedback note (frames f_0104, f_0110)
A student asked when the linear-region assumption is valid. He said **"this is an important point here."**

Board: ***"NOTE: ideal op amp model + operation in linear region typically assume op amp has negative feedback (output connected to $v_n$, often through a resistor)."***
- Without negative feedback, the op-amp "will not kind of be driven back to the condition that $v_p$ is equal to $v_n$".
- On the transfer characteristic, connecting the output to $v_n$ "drives you back to the origin".
- Connecting the output to $v_p$ "will actually drive you out into saturation".
- Feedback is "often through a resistor, although it doesn't have to be". The buffer at the end of the lecture is the direct-wire case.

### 0:41:55 Amplifiers: what they are
An amplifier takes an input voltage (or current) and gives an output that is a multiple of it.

### 0:42:46 Example: non-inverting op-amp amplifier (frames f_0111, f_0124, f_0128, f_0129, f_0135, f_0139, f_0140)
**Circuit (f_0124):**
- The source $v_s$ (+ on top, − to ground) connects **directly** to $v_p$, the + input, drawn on top. The current $i_p$ is labelled entering.
- **$R_1$** runs from the output node $v_o$ down to a middle node; **$R_2$** runs from that node to ground.
- The middle node connects back to $v_n$ (− input, $i_n$ labelled) by a wire. This is the negative feedback path.
- Side note on the board: ***"Note: power supply connections $\pm V_{cc}$ not explicitly shown, but must be present."*** He added that you must connect them if you build this on a breadboard.

**Derivation (f_0135).** Board: *"By voltage division at node $v_n$ (since $i_n = 0$), with $v_n = v_p$:"*
1. With $i_n = 0$, no current leaves the $R_1$–$R_2$ junction toward the op-amp, so $R_1$ and $R_2$ carry the same current. They are **effectively in series**.
2. Voltage division:
$$v_n = \frac{R_2}{R_1+R_2}\,v_o \;\Rightarrow\; v_o = \left(\frac{R_1+R_2}{R_2}\right)v_n$$
3. Golden rule plus the direct connection: $v_n = v_p = v_s$.
$$\boxed{v_o = \left(\frac{R_1+R_2}{R_2}\right)v_s}$$

- **"Non-inverting"** means the proportionality constant is **positive**.
- By choosing the resistors you can get "any value of this … gain factor … that is greater than one".

### 0:49:22 Example: inverting op-amp amplifier (frames f_0141, f_0150, f_0167, f_0209, f_0237)
**Idea:**
- Keep negative feedback (output to $v_n$).
- Apply the input signal at the **inverting** input instead, which gives a negative constant of proportionality.

**Circuit (f_0150):**
- The op-amp is drawn with the **− input on top**.
- **$R_f$** (feedback) runs from $v_o$ back over the top to $v_n$.
- $v_s$ (+ on top, grounded −) connects through **$R_s$** to $v_n$.
- **$v_p$ is grounded.**

**Why $R_s$ is needed (0:51:16):**
- If $v_s$ connected directly to $v_n$, then $v_n = v_p = 0$ would be impossible except when $v_s = 0$, "which is not that interesting".
- $R_s$ lets $v_n$ sit at 0 V while $v_s \neq 0$.

**Derivation.** Board: *"Apply KCL at node $v_n$, noting that $v_n = v_p$ for an ideal op amp $\Rightarrow v_n = v_p = 0$."*
- He takes KCL as the sum of currents **flowing out of** the node = 0. The current into the op-amp is 0, so only two terms remain:
  - Out to the left through $R_s$: $(0 - v_s)/R_s$.
  - Up through $R_f$: $(0 - v_o)/R_f$.
$$-\frac{v_s}{R_s} - \frac{v_o}{R_f} = 0 \;\Rightarrow\; \boxed{v_o = -\frac{R_f}{R_s}\,v_s}$$

The gain is negative, and any negative value is available by choosing the resistors.

### 0:54:17 Example: inverting summing amplifier (frames f_0167, f_0169, f_0175, f_0177, f_0205, f_0246, f_0249)
**Key way of thinking.** Board: *"Notice that for the inverting amplifier, KCL applied at node $v_n$ imposed a condition on the **sum** of voltages ($v_s$ and $v_o$), weighted by resistors in series with those voltages. This suggests a strategy for creating an inverting summing amplifier:"*
- "The summing function is a manifestation of KCL."
- KCL is a condition on a sum of currents, and each current is a voltage divided by a resistance. So "KCL then really is a condition that is imposed on a sum of voltages."
- This "way of thinking" helps for analysis and also for **design**: "if we were presented with the task of designing some circuit that gave this behavior".

**Circuit (f_0184):**
- $R_f$ feedback from $v_o$ to $v_n$; $v_p$ grounded.
- $v_1$ connects through $R_1$ to $v_n$; $v_2$ connects through $R_2$ to the same $v_n$ node.

**Derivation.** KCL at $v_n$, with $v_n = v_p = 0$ and currents out of the node:
$$-\frac{v_1}{R_1} - \frac{v_2}{R_2} - \frac{v_o}{R_f} = 0 \;\Rightarrow\; \boxed{v_o = -\frac{R_f}{R_1}v_1 - \frac{R_f}{R_2}v_2}$$
He also rewrote it in blue (f_0190): $v_o = -\left(\frac{R_f}{R_1}v_1 + \frac{R_f}{R_2}v_2\right)$, a **sum followed by an inversion**.
- To add more inputs, attach more "source + series resistor" branches to $v_n$.
- **Application** (student Q, 1:03:51): add a DC offset (battery or supply) to an AC oscillator signal centred on zero.

### 1:05:15 Example: non-inverting summing amplifier (frames f_0190, f_0254, f_0261, f_0266, f_0277, f_0293, f_0305, f_0322)
Board: *"Again, use the idea that KCL imposes a condition on the sum of voltages, and apply to non-inverting amplifier circuit:"*

**Reasoning:**
- Attach sources through resistors to **$v_p$** (non-inverting).
- One more change is needed. In the plain non-inverting amp $v_s$ was wired **directly** to $v_p$, so $v_p$ would always equal that source. A resistor is needed there too, so that "$v_p$ [is] some weighted average of the two inputs".

**Circuit (f_0277):**
- The op-amp is drawn with the **+ input on top**.
- $v_1$ connects through $R_1$ to $v_p$; $v_2$ connects through $R_2$ to $v_p$.
- Feedback divider: **$R_3$** from $v_o$ to a junction node, and **$R_4$** from that junction to ground. The junction is wired to $v_n$.

**Derivation:**
1. **Voltage division at $v_n$** (valid because $i_n = 0$):
$$v_n = \frac{R_4}{R_3+R_4}v_o \;\Rightarrow\; v_o = \left(\frac{R_3+R_4}{R_4}\right)v_n$$
2. **KCL at $v_p$** (currents out to the left, and $i_p = 0$):
$$\frac{v_p - v_1}{R_1} + \frac{v_p - v_2}{R_2} = 0 \;\Rightarrow\; \underbrace{\left(\frac1{R_1}+\frac1{R_2}\right)}_{\frac{R_1+R_2}{R_1R_2}}v_p = \frac{v_1}{R_1} + \frac{v_2}{R_2}$$
$$\Rightarrow\; v_p = \left(\frac{R_2}{R_1+R_2}\right)v_1 + \left(\frac{R_1}{R_1+R_2}\right)v_2$$
3. Use $v_p = v_n$:
$$\boxed{v_o = \left(\frac{R_3+R_4}{R_4}\right)\left[\left(\frac{R_2}{R_1+R_2}\right)v_1 + \left(\frac{R_1}{R_1+R_2}\right)v_2\right]}$$

Note the cross-pairing: $v_1$ is weighted by $R_2$ and $v_2$ by $R_1$, as a voltage divider would give.

### 1:05:33 Aside: why "inverting summing" and not "subtracting"?
- The inverting summer does $-(\text{sum})$: summation, then inversion.
- "Subtracting" would suggest taking a **difference**, which is the next circuit.

### 1:13:42 Example: difference amplifier (frames f_0336, f_0339, f_0340, f_0344, f_0354, f_0358)
**Idea:** put one "source + series resistor" unit on the inverting input and another on the non-inverting input.

**Circuit (f_0339):**
- The op-amp is drawn with the **− input on top**.
- **$R_2$** is the feedback resistor from $v_o$ to $v_n$.
- $v_1$ connects through **$R_1$** to $v_n$.
- $v_2$ connects through **$R_3$** to $v_p$, and **$R_4$** runs from $v_p$ to ground.
- Why $R_4$: without it, $v_p = v_2$ always (no current flows into $v_p$). $R_3$ and $R_4$ form a divider, giving "a little more flexibility to adjust the voltage at $v_p$".

**Derivation (f_0340, f_0344, f_0354):**
1. **KCL at $v_n$** (currents out):
$$\frac{v_n - v_1}{R_1} + \frac{v_n - v_o}{R_2} = 0 \;\Rightarrow\; \underbrace{\left(\frac1{R_1}+\frac1{R_2}\right)}_{\frac{R_1+R_2}{R_1R_2}}v_n - \frac1{R_1}v_1 = \frac1{R_2}v_o$$
$$\Rightarrow\; v_o = \left(\frac{R_1+R_2}{R_1}\right)v_n - \frac{R_2}{R_1}v_1$$
2. **Voltage division at $v_p$:** $v_p = \left(\frac{R_4}{R_3+R_4}\right)v_2$, and $v_n = v_p$.
$$\boxed{v_o = \left(\frac{R_1+R_2}{R_1}\right)\left(\frac{R_4}{R_3+R_4}\right)v_2 - \frac{R_2}{R_1}v_1}$$

This is a **weighted difference** between $v_2$ and $v_1$.

> [!note] Not said in lecture: the matched case
> If $R_3 = R_1$ and $R_4 = R_2$, the result reduces to $v_o = \frac{R_2}{R_1}(v_2 - v_1)$, a true difference. I checked this with sympy.
> Ulaby uses this form. It is a quick answer if a problem gives matched resistors.

> [!warning] Board self-correction (f_0344)
> The voltage-division line at $v_p$ was first started with $v_1$, then struck out and rewritten with $v_2$. He also says "V1 or V2" at 1:17:48. The correct expression is $v_p = \frac{R_4}{R_3+R_4}v_2$, as the final boxed result uses.
>
> Also at 1:15:05 he says "through a resistor, call this R2, through a resistor R3". This is a verbal slip: the board labels the $v_2$-side series resistor **$R_3$**.

### 1:18:48 Example: voltage follower, or "buffer" (frame f_0362; the drawing is incomplete in the frames)
Board title: **"Example: voltage follower, or 'buffer'"**. The last captured frame (1:19:12) shows only the empty triangle. The circuit below is reconstructed from the transcript (?).
- $v_n$ is wired **directly** to the output: negative feedback with no resistor.
- The input source $v_s$ connects to $v_p$ **through a series resistor $R_s$**.
- He calls the op-amp part "the buffer".

**Analysis:** $v_o = v_n = v_p$, and $v_p = v_s$ because $i_p = 0$ means no drop across $R_s$. So
$$\boxed{v_o = v_s}$$

**Why it is useful:**
- Connect any load to the output and the output voltage is still $v_s$.
- Without the buffer, a load connected directly after $R_s$ would see a voltage that "would vary depending on the value of the load" (a divider with $R_s$).
- "The value and utility of the buffer is that it **doesn't draw any current from the source**." The load current comes from the op-amp output, and so ultimately from the supplies.

He ran slightly long and stopped at 1:21:08.

### Verification (my checks, not from the lecture)
**Symbolic re-derivation (sympy).** All six boxed results reproduce exactly:
- non-inverting, inverting, inverting summing
- non-inverting summing (both the $v_p$ expression and the final result)
- difference amp
- buffer

**Finite-gain model (sympy, full $R_i$/$R_o$/$A$ circuit).** Two configurations, each with ideal gain magnitude 10:
- Non-inverting: $R_1 = 9$ kΩ, $R_2 = 1$ kΩ, ideal gain 10.
- Inverting: $R_f = 10$ kΩ, $R_s = 1$ kΩ, ideal gain −10.

| $A$ | $R_i$ | $R_o$ | non-inv gain | inv gain | $v_n - v_p$ (non-inv, per 1 V in) |
|---|---|---|---|---|---|
| $10^4$ | 1 MΩ | 100 Ω | 9.990 | −9.989 | −1.01 mV |
| $10^5$ | 1 MΩ | 50 Ω | 9.999 | −9.999 | −100 µV |
| $10^6$ | 1 TΩ | 1 Ω | 10.00 | −10.00 | −10 µV |

- Closed forms with $R_i=\infty$, $R_o=0$:
  - Non-inverting: $\dfrac{v_o}{v_s} = \dfrac{A(R_1+R_2)}{AR_2 + R_1 + R_2}$
  - Inverting: $\dfrac{v_o}{v_s} = -\dfrac{AR_f}{AR_s + R_f + R_s}$
  - Both go to the ideal results as $A\to\infty$. This confirms numerically that the golden rules are the $A\to\infty$ limit, with $v_p - v_n$ in the µV range.

**ngspice check: difference amp.** Values: $R_1=1$k, $R_2=10$k, $R_3=2$k, $R_4=5$k, $v_1=0.3$ V, $v_2=0.5$ V, with a finite-gain op-amp ($A=10^5$, $R_i=1$ MΩ, $R_o=50$ Ω).
- Simulated $v_o = 0.92847$ V.
- Ideal formula: $11\cdot\frac57\cdot0.5 - 10\cdot0.3 = 0.928571$ V.
- Simulated $v_p - v_n = 9.3\ \mu$V.

**ngspice check: non-inverting summer.** Values: $R_1=1$k, $R_2=3$k, $R_3=4$k, $R_4=1$k, same $v_1$ and $v_2$.
- Simulated $v_o = 1.74999$ V.
- Ideal: $v_p = 0.350$ V, so $v_o = 5\times0.350 = 1.75$ V.

**Board errors in final content: none found.** The only issues are the self-corrected $v_1\to v_2$ and the verbal slips noted above.

---

## Ed Yu's conventions & notation

- **Lowercase** $v_p, v_n, v_o$ and $i_p, i_n, i_o, i_+, i_-$ for op-amp quantities, with supply rails $\pm V_{cc}$. The subscripts are **p/n**, not +/−, on the input voltages.
- **Current directions:**
  - $i_p$, $i_n$ point **into** the inputs.
  - $i_o$ points **out of** the output.
  - $i_\pm$ point **into** the supply pins.
  - With these, whole-chip KCL is $i_o = i_p + i_n + i_+ + i_-$.
- **KCL sign convention:** he writes the **sum of currents flowing out of the node = 0**, each as (node voltage − far-end voltage)/R.
  - Inverting amp: $-\frac{v_s}{R_s} - \frac{v_o}{R_f}=0$.
  - Difference amp: $\frac{v_n-v_1}{R_1}+\frac{v_n-v_o}{R_2}=0$.
- **Choice of method:**
  - **Voltage division** when the $i_n=0$ (or $i_p=0$) rule makes two resistors effectively in series. He always states "since $i_n = 0$".
  - **KCL at $v_n$** when $v_n$ is pinned at 0 (grounded $v_p$).
- **Order of steps he writes:**
  1. Relate $v_o$ to $v_n$ (feedback network).
  2. Find $v_p$ from the input network.
  3. Invoke $v_p = v_n$, written "; $v_p = v_n$" on the board.
  4. Box the final result.
- **Drawing orientation:**
  - Circuits that use the non-inverting input are drawn with the **+ input on top** (non-inverting amp, non-inverting summer).
  - Circuits with inverting signal paths are drawn with the **− input on top** (inverting amp, inverting summer, difference amp). Read pin labels; don't assume.
- **Resistor names are reused with different roles in each circuit.** Don't memorise gains by label; derive them.

| circuit | feedback (vo→vn) | vn→ground | input resistor(s) |
|---|---|---|---|
| non-inverting amp | $R_1$ | $R_2$ | none ($v_s$ direct to $v_p$) |
| inverting amp | $R_f$ | none | $R_s$ to $v_n$ |
| inverting summer | $R_f$ | none | $R_1$, $R_2$ to $v_n$ |
| non-inverting summer | $R_3$ | $R_4$ | $R_1$, $R_2$ to $v_p$ |
| difference amp | $R_2$ | none | $R_1$ to $v_n$; $R_3$ to $v_p$, with $R_4$ from $v_p$ to ground |

- **Supplies are not drawn** but are "must be present". Ground for the dependent source is the midpoint of symmetric supplies.
- "**Golden rules**" is his term for $v_p=v_n$, $i_p=i_n=0$, and "output provides any $i_o$". He lists $-V_{cc}\le v_o\le V_{cc}$ separately, as something to "always remember".
- "**Open-loop gain**" is $A$. "Transfer characteristic" is $v_o$ vs $v_p - v_n$.
- Headings take the form "Example: …". Final results are boxed.

---

## Intuition & explanations he gives

**Why only $v_p - v_n$ matters (0:12:45):**
- "Even though $V_P$ and $V_N$ can be specified independently of each other, for the op amp what really matters in terms of the functionality of the op amp is the difference between the two input voltages."

**What saturation is (0:15:19–0:15:43, 0:24:42):**
- The linear relationship "cannot continue to very large differences because then the output voltage would be too large in magnitude. So what happens is … saturation of the op amp, where the output voltage $V_O$ just gets pinned at one of the supply voltages."
- In saturation, "the op amp just looks like a voltage source".
- The output cannot exceed the supplies because the supplies are where the output's energy comes from: "the output voltage is not able to exceed the bounds of those supply voltages".

**Why $v_p = v_n$ (0:27:02, 0:38:12):**
- With $A = 10^6$, 1 µV of difference already gives 1 V out, and 10 µV gives 10 V. "That green curve … is very steep, and … the idealization of something that is almost vertical … is … just vertical, which corresponds to the slope being infinite."
- "If A is assumed to be infinitely large, then if $V_P$ were not equal to $V_N$, the output voltage would be infinite. So the approximation that A is infinite then basically requires that $V_P$ be equal to $V_N$ … when you have infinity times 0 it can be anything, and it turns out that that anything is … whatever output voltage is required to get the other two things to be true."

**Why $i_p = i_n = 0$ (0:28:50):**
- "If we assume that $R_i$ is infinite and the currents are non-zero, then that would correspond to infinite voltages, which is not going to happen. So … that is where … the approximation in the ideal op-amp model that the input currents are 0 … ultimately comes from."

**What $R_o$ means physically (0:30:18–0:30:49, 0:32:05):**
- "What this output resistance represents is … something that limits the amount of current that can come out of the op-amp at its output. If we assume that this output resistance is 0, … in principle any amount of current can come out of the op-amp output and we will still get this voltage."
- "It's not that we're choosing to put a resistor there, it's that this is how the op-amp behaves." It is a lumped representation of internal wires and components.

**What an equivalent circuit is (0:24:07):**
- "An equivalent circuit is not the actual circuit that is in the op amp. It is a representation of what is actually in the op amp that gives the same electrical behavior at the terminals within the region of operation that we're interested in."
- Outside the linear region the chip's components haven't changed; the **representation** must change.

**Why the power-supply currents matter (0:11:06–0:11:34):**
- "It might be tempting to say, well, by KCL, the sum of the input currents should be equal to the output current. But that's not correct, because we also have currents associated with these power terminals."

**Why negative feedback (0:39:48–0:40:39):**
- "It is generally the case that the op-amp is connected in a way that you have negative feedback, … some connection often through a resistor between the output and the inverting input … because if you don't have that then the op-amp will not … be driven back to the condition that $V_P$ is equal to $V_N$."
- "If you look at the transfer characteristic you can kind of see how having the output connected to [$V_N$] … drives you back to the origin … whereas if you … have the output connected to $V_P$, then that'll actually drive you out into saturation."

> [!note] Mechanism, in my words; not stated this explicitly in lecture
> Suppose $v_o$ rises with feedback to $v_n$. Then $v_n$ rises, $v_p - v_n$ falls, and $v_o$ is pushed back down: a stable equilibrium at $v_p \approx v_n$.
> With feedback to $v_p$, a rise in $v_o$ raises $v_p - v_n$, which raises $v_o$ further: runaway to $+V_{cc}$.

**Why the circuits stay linear (0:18:15):**
- The circuits "will have been designed in a way that basically keeps the circuit and the op amp in its linear region of behavior."

**Why non-inverting amp resistors are "in series" (0:45:50):**
- "The currents going into the inputs of the op-amp are both zero, so … there's no current flowing along this way, so R1 and R2 are effectively in series, because they always have to have the same current as each other, and so we can use voltage division."

**Why the inverting amp needs $R_s$ (0:51:16):**
- "If we had $V_S$ directly connected to $V_N$, then we wouldn't be able to get $V_N$ equal to $V_P$, except for the special case that $V_S$ is equal to zero … so we have this resistor … that allows this voltage $V_N$ to go to zero for non-zero $V_S$."

**KCL as a summing engine (0:55:36–0:56:27):**
- "The summing function is a manifestation of KCL, because what KCL says is that the sum of all the currents flowing out of a particular node has to be zero … but each of those currents is proportional to a voltage … So KCL then really is a condition that is imposed on a sum of voltages in a circuit."

**Why the non-inverting summer and difference amp need the extra resistor (1:07:43, 1:15:28):**
- Without a resistor in series (and, for the difference amp, $R_4$ to ground), $v_p$ is just stuck at the one directly connected source.
- The extra resistor makes $v_p$ "some weighted average of the two inputs", or lets $v_p$ "not have to be equal to $V_2$".

**Why the buffer is useful (1:20:14–1:20:59):**
- "No matter what load you connect to it, the output voltage is going to be equal to $V_S$, whereas if you didn't have this buffer … the voltage across that load resistor would vary depending on the value of the load … the value and utility of the buffer is that it doesn't draw any current from the source."

---

## Emphasis & exam intel

1. **Post-solution reflection, and writing up reasoning, "carries over to exams"** (0:02:04–0:04:31).
   - "some of that carries over to exams … what I think is the most important point from that handout"
   - "once you have solved any particular problem, you should take a few minutes and kind of go back and think about what you did … why maybe some of the approaches that you tried initially did not work and what it was … that finally did work"
   - As a student he would "write up the solution and sort of explain, both to myself and whoever would be grading it, what the key elements of the solution were, what my reasoning was". This matches the exam's grading of **written reasoning**.
2. **Supply-pin currents** (0:11:06): "**the key thing here is to remember that these power terminals have current associated with them** … it might be tempting to say … the sum of the input currents should be equal to the output current. But that's not correct."
3. **Supplies are always present even when not drawn.** He said this three times: 0:33:06, 0:43:50, and on the board (f_0124):
   - "we should always remember that they are present"
   - Board: "±V_cc not explicitly shown, but must be present."
4. **Output bounded by the rails** (0:37:43): "**finally we also have to always remember that the output voltage has to be within the supply voltages**." Boarded as $-V_{cc}\le v_o\le +V_{cc}$. This is the basis of the P3 "max input amplitude" sub-question.
5. **Negative feedback** (0:39:09): "**Oh, yeah, so this is an important point here** … why can we always assume or under what conditions can we assume that the op-amp is in its linear region." He then boarded a "NOTE:" about it.
6. **Ideal model for everything** (0:34:58): "for pretty much all the circuit analysis that we're going to do … we're going to use the ideal op-amp model."
7. **Linear-region default** (0:18:01): "we are typically going to assume … that we are always in the linear region." Boarded.
8. **KCL-as-sum-of-voltages is a design tool** (0:58:44): "that way of thinking then will help us not only to analyze some circuits that we're presented with but also to understand, okay, if we were presented with the task of designing some circuit that gave this behavior … how would we actually get that functionality."
   - Also at 1:03:25: "you should be able to see very easily how to generalize this".
9. **Golden rules by name** (0:37:30): "these conditions here are what we sometimes refer to as the golden rules of op-amp behavior". He repeated the phrase.
10. **Coming next** (0:06:33): "circuits that have multiple op-amps and then circuits that have op-amps plus, say, capacitors or inductors, which behave a little bit differently and give you different functionality." This is the lead-in to the P3 impedance-synthesizer material.
11. **Survey diagnosis** (0:06:14): inverting and non-inverting amps were well recalled, but "summing amplifiers, difference amplifiers … were a little fuzzier." That is why he derived both summers and the difference amp in full.

---

## Student questions

1. **0:11:40 Could the rails be reversed (e.g. "+V_cc" = −10 V)?**
   - "You would not typically do that, because there are components inside the op amp, transistors and the like, and those do not behave symmetrically. So it does matter."
2. **0:22:48 Which ground is the dependent source connected to?**
   - With symmetric supplies, ground is their midpoint.
   - "It doesn't matter so much that this is connected to ground." It makes the source voltage well defined and "provides a source for the current that eventually flows through the output".
3. **0:23:39 The components are fixed on the chip, so how can the circuit change outside the linear region?**
   - An equivalent circuit reproduces the terminal behaviour only within the region of interest.
   - In saturation the op-amp looks like a voltage source. The representation changes; the chip does not.
4. **0:30:56 Is $R_o = 0$ justified by supply-current limits?**
   - "Ultimately it can be related to that". However, internal components that effectively act as resistance are "more of a limiting factor", because "you could always connect a bigger power supply".
5. **0:31:48 Why include $R_o$ at all, rather than connecting the source directly?**
   - It is not a design choice. It is the lumped effect of real internal resistance (wires, components).
6. **0:38:05 Why does the ideal model give $v_p = v_n$?**
   - Infinite $A$ with finite $v_o$ requires a zero difference. "Infinity times 0" equals whatever output satisfies the other rules.
7. **0:39:09 (question inaudible; from the answer: when can we assume linear operation?)**
   - Negative feedback. He called it "an important point" and boarded the NOTE.
8. **0:44:26 Why is it called "non-inverting"?**
   - The gain constant is positive. The inverting amplifier has a negative constant.
9. **0:44:57 Is the output generally connected to the inverting terminal?**
   - "For these kinds of amplifiers, that's generally what will happen, yeah."
10. **0:48:56 (question partly inaudible; apparently whether the non-inverting gain can be exactly 1) (?)**
    - "If you had $R_1$ equal to zero … you can get very close, but there's always a little bit of resistance … practically speaking, you get very close to one, but it's hard to get exactly equal to."
    - **Clarification (mine):** in the **ideal model**, $R_1 = 0$ (or $R_2\to\infty$) gives a gain of exactly 1. That is the voltage follower derived at the end of this lecture. His "can't get exactly 1" is a practical remark about real wires, not a property of the ideal model. On an exam, the gain is ≥ 1 with equality for the follower.
11. **1:03:39 What are practical applications of a summing amplifier?**
    - Adding a DC offset (battery or supply) to an AC oscillator signal centred on zero.
12. **1:04:40 (question inaudible)**
    - He answered that "we want to understand what the functionality of this circuit as a whole is … the output as a function of some input signals" (?). He was possibly explaining why everything is solved for $v_o$.
13. **1:05:33 Why not call it a "subtracting amplifier"?**
    - It is a sum then an inversion, $v_o = -\left(\frac{R_f}{R_1}v_1+\frac{R_f}{R_2}v_2\right)$. "Subtracting" suggests a difference, which is the difference amplifier.
14. **0:57:40 (in-class prompt from him)** How should the inverting amp be modified for a second input?
    - A student said: connect it through a resistor to the inverting input. He replied: "that's exactly right".

---

## Exam relevance

### P1: "explain why" conceptual items (high yield from this lecture)
Model one-to-three-sentence answers, built from his own reasoning:

**Why may we set $v_p = v_n$?**
- $v_o = A(v_p - v_n)$ with $A \sim 10^4$–$10^8$, and $|v_o| \le V_{cc}$.
- So $|v_p - v_n| \le V_{cc}/A$, which is µV-scale. Idealising $A\to\infty$ makes the difference zero.
- This holds **only in the linear region**, which needs **negative feedback**.

**Why $i_p = i_n = 0$?**
- $R_i \sim 10^6$–$10^{13}\ \Omega$. A finite current through an infinite $R_i$ would need an infinite voltage.

**Why doesn't $i_p + i_n = i_o$?**
- KCL on the chip includes the supply-pin currents: $i_o = i_p+i_n+i_++i_-$.
- The output current is supplied by the rails, not by the inputs.

**What does saturation mean physically? Why can't $v_o$ exceed $\pm V_{cc}$?**
- The output is powered by the supplies, so it cannot exceed them. In saturation, $v_o$ is pinned at a rail and the op-amp acts like a voltage source.
- In saturation, $v_p = v_n$ **no longer holds** and the linear analysis is invalid.

**Why is negative feedback needed?**
- Feedback to $v_n$ opposes any change in $v_o$ and drives the op-amp back toward $v_p - v_n \approx 0$, the origin of the transfer characteristic.
- Feedback to $v_p$ reinforces the change and drives it to saturation.

**Why use a buffer?**
- It draws zero input current, so the source is unloaded and $v_o = v_s$ for any load. The load current comes from the op-amp output and supplies.

**Why does the inverting amp need $R_s$?** (And why do the summer and difference amp need $R_4$ or a series resistor?)
- **$R_s$:** without it, $v_n$ could not sit at 0 V while $v_s \ne 0$.
- **Series resistor on $v_p$, or $R_4$:** without it, $v_p$ would be locked to one source.

**Why is $R_o = 0$ in the ideal model, and what does a nonzero $R_o$ do?**
- A nonzero $R_o$ drops voltage at high $i_o$, so it limits deliverable current.
- With $R_o = 0$, the output can supply whatever current the golden rules require.

### P3: two-op-amp impedance synthesizer (the main payoff)
This lecture provides the toolkit for P3; the capacitor and inductor versions come in later lectures.

1. **Analysis method:**
   - Apply the golden rules at each op-amp.
   - Use KCL at the input nodes. A grounded $v_p$ means $v_n = 0$ (virtual ground); otherwise $v_n = v_p$ = whatever $v_p$ is tied to.
   - Use voltage division wherever $i_n = 0$ makes elements series-connected.
   - In phasor form the same algebra holds with $R \to \tilde Z$. For example, an inverting stage gives $\tilde V_o = -\frac{\tilde Z_f}{\tilde Z_s}\tilde V_s$. This is my extrapolation; he has not done this yet.
2. **Source current $i(t)$:**
   - Find it from KCL at the source node. The op-amp **inputs draw zero current**, so the source current flows only through the external elements.
   - The op-amp **outputs** supply whatever current the feedback elements need. That current comes from the rails, which is why $i_o \neq i_p + i_n$.
   - Never set the source current equal to an op-amp output current without checking KCL.
3. **"Max input amplitude so EVERY op-amp output stays within $\pm V_{cc}$":**
   - This is his "always remember" condition $-V_{cc}\le v_o\le+V_{cc}$, applied to **each** op-amp.
   - Write every output as $v_{o,k} = G_k v_s$, where $G_k$ is a phasor magnitude $|\tilde G_k|$ at the given $\omega$ in the AC case. Then
     $$|v_s|_{max} = \frac{V_{cc}}{\max_k |G_k|}.$$
   - Check the **intermediate** op-amp output too, not just the last one. The first stage often has the larger gain.
   - My illustration: a non-inverting stage with $R_1 = 9$ kΩ and $R_2 = 1$ kΩ has gain 10; with $V_{cc} = 12$ V, $|v_s|_{max} = 1.20$ V. An inverting stage with $R_f/R_s = 10$ gives the same 1.20 V.
   - State on the exam **why**: beyond this the op-amp saturates, $v_p = v_n$ fails, and the analysis is invalid.
4. **"Replace the box by a single R, L or C":**
   - Compute $\tilde Z_{in} = \tilde V_s/\tilde I_s$.
   - If $\tilde Z_{in}$ is real, it is a resistor. If $\propto j\omega$, it is an inductor with $L_{eq}$ = coefficient. If $\propto 1/(j\omega)$, it is a capacitor.
   - The op-amp's ability to supply arbitrary $i_o$ (the third golden rule) is exactly what lets the box draw a current that a passive network couldn't. This is the physical "why" for a P1 or P3 explanation.
   - Not covered in this lecture; flagged for the C/L op-amp lectures.
5. **Read pin orientation:** he draws − on top in inverting-type circuits and + on top in non-inverting ones. Exam figures may do either.

### P2: phasor ladder
Indirect relevance only. The voltage-division and KCL habits carry over, and an op-amp stage may appear inside a phasor circuit.

### P4: 2nd-order RLC transient
Not covered by this lecture.

### Formula sheet to memorise (closed book; derive rather than recall, since resistor labels vary)

| circuit | result |
|---|---|
| non-inverting | $v_o = \left(1+\frac{R_{fb}}{R_{gnd}}\right)v_s$ |
| inverting | $v_o = -\frac{R_f}{R_s}v_s$ |
| inverting summer | $v_o = -R_f\sum_k \frac{v_k}{R_k}$ |
| non-inverting summer | $v_o = \left(1+\frac{R_3}{R_4}\right)\frac{R_2v_1+R_1v_2}{R_1+R_2}$ |
| difference | $v_o = \left(1+\frac{R_2}{R_1}\right)\frac{R_4}{R_3+R_4}v_2 - \frac{R_2}{R_1}v_1$ (matched: $\frac{R_2}{R_1}(v_2-v_1)$) |
| follower | $v_o = v_s$ |
