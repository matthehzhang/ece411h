---
course: ECE 411H
date: 2026-08-24
instructor: Prof. Ed Yu
topic: Day 1. Syllabus/logistics (exam rules, grading, AI policy), course map, review of element v–i laws and sources, capacitor physics and the parallel-plate capacitance derivation
reading: Ulaby/Maharbiz/Furse 3e, Ch. 1–5 review (no specific section assigned in class)
sources: Recordings/2026-08-24/transcript.txt + frames (26 pages.txt frames + 3 extra viewed)
tags: [ece411, lecture, capacitor, logistics, exam1]
---

# 2026-08-24: Course intro, element laws, and capacitors

## Summary

- **About 55 of the 82 minutes are logistics.** The parts that matter for the exam: Exam 1 is **in class on Oct 7**, **closed book**, and you may bring only the question/answer sheets, a calculator and a writing implement. You must write on paper, not a tablet. **Most of the credit is for visible reasoning**, and "only a fairly small fraction" goes to the final numerical answer.
- **Element v–i laws** (review from 302): $v=iR$ [Ω], $i=C\,\dfrac{dv}{dt}$ [F], $v=L\,\dfrac{di}{dt}$ [H]. C and L have *differential* v–i relations. That is the reason circuits containing them give differential equations instead of algebraic ones.
- **Sources.** An independent source's $v$ (or $i$) is specified explicitly and drawn as a circle. A dependent source's value is set by a voltage or current *elsewhere* in the circuit, $f(v_x,i_x)$, and it is drawn as a diamond. Dependent sources are used to model complicated devices such as transistors.
- **Capacitors store electric charge, or equivalently energy in the form of an electric field.** Start from $q=Cv$ and differentiate, with $C$ time-independent, to get $i=dq/dt=C\,dv/dt$.
- **Parallel-plate capacitor derivation.** Apply Gauss's law to a box around the bottom plate: $AE=-q/\epsilon$, so $E=-q/(\epsilon A)$. Also $E=-dv/dz=-v/d$. Equating the two gives $q=(\epsilon A/d)v$, so $\boxed{C=\epsilon A/d}$. Large area and small separation give a large capacitance.
- **Physical scale sense.** 1 F is "a giant capacitance" (typical range is pF to mF), and 1 H is a big inductor, while 1 kΩ is an ordinary resistor. He also checks plausibility in general: if a design needs a 10 kV source it is "probably" wrong, and a million amps is "definitely" wrong.
- The lecture stopped before inductors. Inductors, continuity and DC steady state are all in [[2026-08-26 - Inductors and First-Order RC RL]].

---

## Logistics

*Compressed. Only exam-, grading-, materials-, solution-writing- and AI-related items are kept in detail.*

- **Exams** [0:11:22]: "two exams … in class, in person exams on **October 7th and November 11th**," plus the final. The final will "almost certainly" be at the registrar's slot that corresponds to the class meeting time (99%) [0:14:50].
- **Allowed materials** [0:11:34]: "those will be in class, **closed book**. If there are any additional materials that are allowed … when we get to the last part of the course on transforms, then I'll provide some additional materials … But other than that, **it's just the answer sheet, the questions, calculator and writing implement**." There is no formula sheet for Exam 1.
- **Paper only** [0:12:03]: "our policy starting this year is that you have to **physically write the exams on paper**, not on a tablet."
- **Calculator** [0:39:34]: any calculator "that does not have communication or photographic capability." Linear-algebra calculators are fine, **but**: "we can only give you credit for things that are **written in your solutions and where we can see your path of reasoning**. And in grading the exams, **most of the credit is actually for showing us that reasoning and your work** and … only a fairly small fraction is for having the correct, say, numerical answer at the end."
- **Submission** [0:23:34]: you scan your paper exam with your phone at the end and upload it to **Gradescope**. Graded exams come back on Gradescope, and you get about **1 week to request regrades** on semester exams. Turnaround on the final is much shorter.
- **Grading** [0:22:47]: problem sets 5%, lab 10%, semester exams 25% + 25%, final 35%. "Even though the problem sets only count for 5% … they are actually **the key to your understanding the material and getting the 85%** that is associated with the exams."
- **Past exams** [0:06:57]: the Canvas "Exam Preparation Materials" page has every exam from the last three offerings, with score distributions and **short answers in a separate version** "so that you're not looking at the answers while you're trying to work through the problems."
- **Problem sets** (frame f_0005): PS1 is due **Wed Sep 9** and PS2 **Mon Sep 14**, both at **9:00 AM on Canvas**. Problem sets are posted on Canvas only. Solutions are released on the due date, usually at 6 pm [0:03:56].
- **Collaboration** [0:25:53]: discussing with classmates is encouraged, "but in the end, you should sit down by yourself and work out and write out your solutions … that's what you're going to be required to do on the exams."
- **AI policy** (syllabus, frame f_0188; spoken at 0:27:18):
  - **Allowed:** using AI to explain concepts, to find useful approaches to specific problems, to get feedback on solutions you worked out yourself, and to solve problems that were *not* assigned.
  - **Not allowed:** using AI "to obtain worked solutions to assigned homework problems."
  - **Enforcement:** "if you use AI inappropriately, it will be very difficult for you to do well on the exams that count for 85 percent." He fed the old exams to free AIs and "they could all solve all of the problems."
  - **The ECE 411H Circuit Tutor** is a ChatGPT agent, reached through your UT ChatGPT Edu login. It is grounded in the Ulaby PDF, uses Ulaby notation, won't give full worked solutions, and is restricted to circuits/EE topics. He showed that its ASCII circuit diagrams "are, as it turns out, not quite correct." His advice: struggle with a problem yourself first, because "that kind of struggling with it … that's the process of learning."
- **Recordings** [0:13:27] are meant for illness, travel or re-watching. They are "not intended for you to try to watch four weeks worth of classes two days before the exam because that generally doesn't work … I can see … who has watched the recordings and when."
- **People and places:** office hours MW about 10:30 to just before noon, EER 3.802. Put "**ECE 411 H**" in email subjects or the message may hit the spam filter. TA Darsh Shah (tentatively Wed 1–3 pm). Lab/recitation Mon 1–3 pm (EER 0.818 for recitation, EER 1.828 for lab); both are required. There is an unofficial Discord.
- **Texts** [0:16:04]: Ulaby et al. (required; free PDF from the publisher; "pretty concise"). Supplementary: Alexander & Sadiku (detailed, many practice problems of graded difficulty), *The Art of Electronics* (idiosyncratic, deep insight), Nilsson & Riedel (hard problems; "doesn't have that many simple problems"), Oppenheim & Willsky (for the transforms unit).
- **Prerequisite warning** [0:42:33]: "the thing that I think is often a bit challenging is understanding how to **do algebra with complex numbers**." Handouts will come later. This matters for P2 (phasors).
- **Falling behind** [0:41:02]: "if you don't understand things in the beginning, it's not like it'll suddenly become clear later on. It'll just get worse."

---

## Content

### [0:44:27] Course overview (frames f_0295, f_0314, f_0335, f_0350)
Board heading: **"ECE 411H: Circuit Theory (Honors)."**
- **ECE 302(H)** gave an "intro to key c[ircuit concepts, techniques, components]": R, C, L, KCL/KVL, op amps, plus "basics of semiconductor devices + frequency-domain analysis."
- **ECE 411H:**
  - a "more extensive, in-depth treatment of linear circuits"
  - RC, RL and RLC circuits, and op amps. RLC circuits "are more complicated because they're governed by more complicated differential equations."
  - "a bit more on semiconductors + devices" → **ECE 339**. The focus is pn-junction devices (diodes, LEDs, solar cells, bipolar transistors), complementing the MOSFET focus of 302.
  - "more powerful tools for ac circuit analysis":
    - sinusoidal/phasor analysis
    - frequency-dependent response and Bode plots
  - All of it leads into **ECE 438** (green bracket on the board).
- He will ask for questions at the start of every class. He expects you to re-read your notes after class, and something "that seemed pretty clear … doesn't quite make as much sense" later.

### [0:54:53] Brief review of key topics from 302/302H (frames f_0367, f_0400, f_0406, f_0414)
"One of the defining characteristics of a circuit component is the relationship that that component embodies between voltage and current."

| Element | v–i law | Symbol | Parameter (unit) |
|---|---|---|---|
| Resistor | $v=iR$ (Ohm's law) | zig-zag | $R$ = resistance (Ω) |
| Capacitor | $i=C\,\dfrac{dv}{dt}$ | two parallel plates | $C$ = capacitance (F) |
| Inductor | $v=L\,\dfrac{di}{dt}$ | coil | $L$ = inductance (H) |

- **Why C and L give ODEs** [0:56:47]: "the defining relationship between current and voltage is a **differential relationship rather than an algebraic** relationship … That is why when you have circuits that have capacitors and/or inductors, you end up getting differential equations."
- **Scale** [0:57:36]:
  - "one farad is a giant capacitance … we could be working with maybe **picofarads to perhaps millifarads**."
  - "One henry is a big inductor."
  - "1,000 ohms is a pretty typical resistor. But you would be pretty hard pressed to find a 1,000 farad capacitor or a 1,000 henry inductor."
- **Voltage sources** [0:59:00]: "v specified explicitly, or in terms of i or v elsewhere in a circuit." A voltage source "gives you a voltage that is the same **regardless of how much current is flowing through** that voltage source."
  - *Independent:* a circle with ±, value $v$.
  - *Dependent:* a diamond with ±, $v=f(v_x,i_x)$.
  - Dependent sources are "very useful ways of representing the behavior of some more complicated device, like maybe a transistor, … using simple two-terminal linear components."
  - [1:00:57] He also says that if the controlling quantity were the element's *own* current or voltage, "it would typically be one of these." He points at something, presumably the resistor, since a source whose voltage is proportional to its own current is just a resistance. (?)
- **Current sources** [1:01:05]: "i specified explicitly, or in terms of i or v elsewhere in a circuit." Independent: a circle with an arrow, value $i$. "The arrow shows the direction of this current." Dependent: a diamond with an arrow, $i=f(v_x,i_x)$.

**Student Q [1:02:27]:** why are some capacitors drawn with one curved plate? "In principle, a capacitor should be symmetric … but some types of capacitors, it does matter which is the positive terminal … then usually it's drawn with … one curved terminal." The polarity dependence "comes about because of the physics of how that type of capacitor is actually made" (electrolytic capacitors).

### [1:03:25] Capacitors and inductors as energy-storage elements (frames f_0434, f_0441, f_0445)
- "Capacitors and inductors are devices that can **store energy**." A capacitor stores it as an electric field (charge). An inductor stores it as a magnetic field, "or correspondingly current that is associated with that magnetic field."
- Board definition: **"Capacitors are circuit components that store electric charge, or, equivalently, energy in the form of an electric field."**
- [1:05:13] "The energy, say, for an electric field goes as the electric field squared. For a magnetic field, it's the magnetic field squared." He gave no circuit-level energy formula in this lecture (see the note at the end of this section).
- **Physical picture (f_0441):** two conductors separated by an insulator. A voltage source $v$ (+ on top) is connected across them, and current $i$ flows into the top plate. The plates carry $+q$ (top) and $-q$ (bottom).
- **Defining relation** [1:07:06]:
$$q=Cv\quad\Longrightarrow\quad i=\frac{dq}{dt}=C\frac{dv}{dt}\qquad(C\text{ time-independent}).$$
  - "If you have a large capacitance, then it only takes a little bit of voltage to produce a given amount of charge … the capacitance is sort of **a measure of how efficiently this particular device stores electric charge**."
  - "You can think of this charge being built up by this current flow."
  - The reference directions are the **passive sign convention**: $i$ enters the plate at the higher assumed potential (+).

### [1:08:53] Parallel-plate capacitor: deriving $C=\epsilon A/d$ (frames f_0459, f_0490, f_0509, f_0532, f_0537, f_0593, f_0603)
**Setup (f_0459).** The source $v$ (+ on top) is connected across two plates. Each plate has **area $A$**, the top carries $+q$ and the bottom $-q$, and the **separation is $d$**. The gap holds a dielectric with **dielectric constant $\epsilon$**. Axes: $z$ points up (normal to the plates), and $x,y$ lie in the plate plane.

Goal: relate $q$ to $v$ in terms of $A,d,\epsilon$, which gives $C$. Plan: find $E$ inside from the charge, then integrate $E$ across the gap to get $v$.

1. **Gauss's law** (board): $\displaystyle\oint_S\vec E\cdot d\vec S=\int_V\frac{\rho}{\epsilon}\,dV$, which is "basically the total charge divided by the dielectric constant."
   - "The trick in using Gauss's law for electrostatic problems is to figure out what's a convenient volume." You want one where the flux has a simple geometric relationship to the volume and the enclosed charge is easy to find.
   - **Choice:** a small box (red dashed in f_0490/f_0593) enclosing the **bottom plate**. Its top face is inside the gap and its bottom face is outside the plates.
2. **Field structure** (board): "The electric field $\vec E$ between the parallel plates is given by $\vec E=E\hat z$, and $\vec E=0$ outside the plates."
   - It points along $z$ because, for very large plates, "there's no variation in the x and y direction."
   - It is zero outside, "again, assuming that the plates have an extremely large area."
3. **Evaluate the flux.** Only the box's top face contributes, because it is the only face inside the plates with a non-zero $\vec E\cdot d\vec S$. The enclosed charge is $-q$:
$$AE=-\frac{q}{\epsilon}\quad\Longrightarrow\quad E=-\frac{q}{\epsilon A}.$$
   The minus sign means $\vec E$ points in $-\hat z$ (down), as it must, "from the positive charge to the negative charge."
4. **Field–potential relation** (board): "In addition, we know $\vec E=-\vec\nabla v$, or $E=-\dfrac{dv}{dz}$ in 1D." So
$$E=-\frac{dv}{dz}=-\frac{v}{d}.$$
   **Why the derivative is just $v/d$** [1:17:55]: $E$ is uniform in the gap. "If we were to make this box taller inside here, the amount of charge doesn't change. So that means the electric field has to be the same."
5. **Combine the two expressions for $E$** (f_0603):
$$-\frac{v}{d}=-\frac{q}{\epsilon A}\;\Longrightarrow\;q=\underbrace{\frac{\epsilon A}{d}}_{C}\,v\;\Longrightarrow\;\boxed{C=\frac{\epsilon A}{d}}\quad\text{(capacitance of a parallel-plate capacitor)}.$$

**Interpretation** [1:19:37]: "If you want a **large capacitance**, you want to have a **large area and a small separation** … a structure that has a small area … [gives] a small capacitance. And that actually comes up in many different contexts."

> [!note] Scale check (my numbers, not from the board)
> With $\epsilon=\epsilon_0=8.854\times10^{-12}$ F/m, $A=1\ \text{cm}^2$ and $d=1\ \mu$m, $C\approx 885$ pF. Getting 1 F with the same gap would take $A\approx1.1\times10^{5}\ \text{m}^2$. That is why "one farad is a giant capacitance" and why large capacitors rely on high-$\epsilon$ dielectrics, very thin layers and huge effective areas.

**Student Qs** [1:20:03]:
- *"Why is there a minus sign in $AE=-q/\epsilon$?"* The left side is just the flux, field × area, "with no negative sign," and $E$ itself may be positive or negative. The minus on the right is there "because we're looking at the bottom plate and that has charge minus q." So $E<0$, meaning the field points in $-z$, i.e. downward.
- *"What is $\rho$?"* "It is the charge density, so charge per unit volume. So when you integrate that, you get the total charge."

[1:21:24] Close: "we'll pick up next time with inductors, which I know are less intuitive than capacitors."

> [!note] Exam-relevant facts that were *not* derived in this lecture
> These were not on the board on 8/24 or 8/26, but Exam 1 P1/P4 assume them. They are standard Ulaby Ch. 5 results, so check them against the text.
> - Stored energy: $w_C=\tfrac12Cv^2$, $w_L=\tfrac12Li^2$.
> - Capacitors: in parallel, $C_\text{eq}=\sum C_k$; in series, $1/C_\text{eq}=\sum 1/C_k$.
> - Inductors combine like resistors: $L_\text{eq}=\sum L_k$ in series, $1/L_\text{eq}=\sum1/L_k$ in parallel.
> - Continuity of $v_C$ follows from $i=C\,dv/dt$: a jump in $v_C$ would need infinite current. On 8/26 he gave the dual argument for $i_L$ explicitly and used $v_C$ continuity in the RC example.

---

## Ed Yu's conventions & notation

- **Lower-case $v,i$ for time-varying quantities.** He writes $v=iR$, $i=C\,dv/dt$, $v=L\,di/dt$ with no subscripts in the element laws.
- **Passive sign convention throughout:** current enters the element's + terminal. In the capacitor sketch, $i$ flows from the source's + terminal into the $+q$ plate, which makes $i=C\,dv/dt$ positive when $v$ is rising.
- **Source symbols:** circle = independent, diamond = dependent. Voltage sources are marked ±; current sources carry an arrow giving the reference direction. A dependent value is written $f(v_x,i_x)$.
- **Units always stated** with parameters: Ω, F, H.
- **Derivation style:** physics first. He states a law in integral form, picks a clever Gaussian surface, uses symmetry and the large-plate approximation, and then combines two expressions for the same quantity. He writes complete sentences on the board ("By Gauss's Law, we know …", "Combining these expressions for E, we get …"). He explained why on 8/26: so the notes are readable later. This is also the solution style he grades.
- **Sign bookkeeping:** he keeps the sign of $E$ explicit, with axes defined first, and then interprets the sign physically (field points downward). He does not just drop the minus signs.

## Intuition & explanations he gives

- **Why circuits with C or L give differential equations** [0:56:47]: "The relationship between current and voltage for those two types of components is a differential relationship." *(This is the root of every P4 question.)*
- **What capacitance means** [1:07:15]: "If you have a large capacitance, then it only takes a little bit of voltage to produce a given amount of charge. But if you have a small capacitance, to get that same amount of charge, you need much more voltage. So the capacitance is sort of a measure of how efficiently this particular device stores electric charge."
- **Current builds up charge** [1:08:14]: "You can think of this charge being built up by this current flow." So $i=dq/dt=C\,dv/dt$.
- **Energy lives in the fields** [1:05:08]: "Any time you have charge, that charge produces an electric field. And there is energy … associated with fields … the energy for an electric field goes as the electric field squared. For a magnetic field, it's the magnetic field squared."
- **Why $E$ is uniform between the plates** [1:17:55]: "If we were to make this box taller inside here, the amount of charge doesn't change. So that means the electric field has to be the same."
- **Field direction** [1:16:29]: "The electric field should point from the positive charge to the negative charge."
- **Design rule** [1:19:37]: "If you want a large capacitance, you want to have a large area and a small separation."
- **Dependent sources as device models** [0:59:39]: they are "very useful ways of representing the behavior of some more complicated device, like maybe a transistor … using simple two-terminal linear components."
- **Ideal voltage source** [0:59:06]: "gives you a voltage that is the same regardless of how much current is flowing through that voltage source."
- **Physical plausibility** [0:43:29]: "if you're designing a circuit and somehow what you're getting is that you need a 10,000 volt source, then probably something is wrong, maybe not necessarily, but probably. If it's telling you, oh, you need a million amps, that's definitely going to be wrong."
- **Transforms** [0:51:20]: "you convert differential equations in the time domain to algebraic equations in the frequency domain. And it's a lot easier to solve algebraic equations than differential equations. And it also gives you insight into what ultimately is the time-dependent behavior."

## Emphasis & exam intel

- [0:39:49] **"We can only give you credit for things that are written in your solutions and where we can see your path of reasoning. And in grading the exams, most of the credit is actually for showing us that reasoning and your work and … only a fairly small fraction is for having the correct, say, numerical answer at the end."** This is the single most important exam-technique statement in the course: write every step and state every assumption (e.g. "DC steady state ⇒ C is an open circuit").
- [0:11:34]–[0:12:03] **"In class, closed book … it's just the answer sheet, the questions, calculator and writing implement … you have to physically write the exams on paper."** There is no formula sheet, so the element laws, $C=\epsilon A/d$ and the rest must be memorized.
- [0:22:58] **"Even though the problem sets only count for 5% of the grade, they are actually the key to … getting the 85% that is associated with the exams."**
- [0:06:57] Past exams from 3 offerings, with score distributions and separate short answers, are on Canvas, "useful … in helping you to sort of get a sense of what's expected on the exams."
- [0:28:03] **"If you use AI inappropriately, it will be very difficult for you to do well on the exams."**
- [0:13:27] Cramming recordings "two days before the exam … generally doesn't work … I can see that it definitely does not work."
- [0:42:33] Complex-number algebra is "often a bit challenging." Expect it on P2 (phasor ladder).
- [0:43:57] "Getting a sense of what are reasonable values for quantities with units is important as well." Units and plausibility checks are part of good written reasoning.
- [0:26:21] Write your own solutions, "because that's really the only way to make sure that you really understand them, and that's what you're going to be required to do on the exams."

## Student questions

- [0:14:07] *Virtual office hours?* No. In-person only, because running both at once is "cumbersome." Use Discord or the AI tutor instead.
- [0:14:46] *When is the final confirmed?* The registrar confirms around the 1st–2nd week of November. It is ~99% certain to be the slot matching the class time.
- [0:20:44] *Which problems in the supplementary books are worth doing?* Problems that walk you through variations ("what happens if you do this") are conceptual and useful. Ones that "just analyze the circuit and give you a bunch of weird numbers" are less useful.
- [0:21:28] *Are the supplementary books free?* No, but they are in the library. Alexander & Sadiku costs about \$150–200. He warns against unauthorized PDF sites ("there may be other things that come along with them").
- [0:39:28] *What calculators?* Anything without communication or photographic capability; linear algebra is OK. But credit only goes to visible reasoning (see Emphasis).
- [1:02:27] *Capacitor symbol with a curved plate?* It marks a polarized capacitor; the polarity comes from how it is made.
- [1:20:03] *Sign in $AE=-q/\epsilon$?* The Gaussian box encloses the bottom plate, whose charge is $-q$. $E<0$ means the field points down.
- [1:21:08] *What is $\rho$?* Charge per unit volume.

## Exam relevance

- **P1 (conceptual "explain why"):**
  - Explain why C and L give differential equations: their v–i laws are derivatives.
  - Use $i=C\,dv/dt$ for capacitor reasoning. At DC, $dv/dt=0$ gives $i=0$, so the capacitor is an open circuit; this is formalized on 8/26. A finite $i$ forbids a jump in $v$, which is continuity.
  - Possible "how would you increase C?" item: raise $A$ or $\epsilon$, or reduce $d$, from $C=\epsilon A/d$.
  - Be able to state that a capacitor stores energy in its E field, $\propto E^2$, i.e. $\tfrac12Cv^2$ (formula not given in this lecture).
- **P2 (phasor ladder):** nothing direct. The warning about complex-number algebra applies.
- **P3 (op-amp impedance synthesizer):** dependent-source notation (diamond, $f(v_x,i_x)$) is the language of op-amp models. Nothing else here.
- **P4 (2nd-order RLC transient):** this lecture supplies the element laws that every KVL/KCL equation is built from. The grading-policy statement means you must show reference directions, the IC reasoning and each algebra step.
- **All problems:** credit goes mostly to visible reasoning, the exam is closed book with no formula sheet, it is written on paper, and answers need units and a plausibility check.
