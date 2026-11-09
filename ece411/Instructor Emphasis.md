# Instructor Emphasis: what Ed Yu actually said (lectures 8/24–9/30)

Synthesized from the 9 lecture notes in [[Lectures]], each built from a Whisper transcript plus the handwritten tablet frames. Timestamps are `[h:mm:ss]` into that day's recording. See also [[Past Exams F23-F24]] · [[Course Materials Map]].

## Exam 1 facts (his words)
- **Date and format:** Wed Oct 7, in class, in person. "Closed book and closed notes… calculator, anything without communication abilities, so no using your phone." [9/21 0:02:20] "It's just the answer sheet, the questions, calculator and writing implement." [8/24 0:11:34]
- **Paper only:** "you have to physically write the exams on paper, not on a tablet." [8/24 0:12:03]
- **Bring a printed answer-sheet template.** Do the Gradescope **"Exam Upload Practice"** assignment beforehand: "There's almost always someone who… has some problem uploading. So please test this before you come to the exam." [9/28 0:02:23; 9/30 0:00:18–0:00:45]
- **Scope ends at power factor:** "this is the end of what you were responsible for… semester exam one will cover material to this point." The board says "SEMESTER EXAM 1 COVERS TO HERE", right after pf = P_av/S = cos(φv − φi). [9/30 0:08:55] It "will not include calculations pertaining to how we maximize power transfer." [9/28 0:00:59] **Out of scope:** max power transfer (§8-5) and semiconductors/devices.
- **3 significant figures:** "On exams… I'll specify you should do things to three significant figures." [9/21 0:26:04]
- **Angle units:** ω in rad/s, phase shifts in **degrees**. There's a boxed CAUTION about mixing them. [9/21 0:12:53]

## How he grades: reasoning over answers
- "we can only give you credit for things that are written in your solutions and where we can see your path of reasoning… **most of the credit is actually for showing us that reasoning**… only a fairly small fraction is for having the correct… numerical answer at the end." [8/24 0:39:49]
- "we can only give you credit for the work that you show… If you get the wrong answer, we can only give you credit for getting the equations." [9/9 1:04:03]
- Calculator use is fine, "but if you make a mistake and didn't explain what you were doing… we can't give you credit… Or any reasoning that is not explained." [9/30 0:41:42]
- The reflection / write-up-your-reasoning tip "carries over to exams": write "what the key elements of the solution were, what my reasoning was" for "whoever would be grading it." [8/31 0:02:04–0:04:31]
- Sanity checks: "if you need a 10,000 volt source, then probably something is wrong… a million amps, that's definitely going to be wrong." "One farad is a giant capacitance." [8/24 0:43:29, 0:57:36]

## By exam problem

### P1 (conceptual): his own explanations, reusable nearly verbatim
- **Continuity:** "if [i_L] were discontinuous, that derivative di/dt would be undefined and the voltage would be undefined, which we cannot have." [8/26 1:05:41] The capacitor case is the dual. "Voltage across a capacitor and current for an inductor… have to be continuous… The other quantities… can change discontinuously." [8/26 1:20:16]
- **DC steady state:** "inductors act as short circuits, and capacitors act as open circuits." [8/26 1:16:06; 9/2 closing key points]
- **Three damping types:** they are universal for any RLC "because in the end you're going to have a second order differential equation." [9/14 0:37:46] The constants D1 and D2 are real because "the voltage across the capacitor has to be a real quantity." [9/14 0:22:11]
- **Why 1st-order can't be underdamped:** a single real root s = −1/τ, so nothing can oscillate. Oscillation needs two energy-storage elements exchanging energy. (Note: two decoupled inductor branches still give no oscillation. [8/26])
- **Series RLC phasor relations:** V_R is in phase with I. V_C and V_L are each 90° from I, so "the voltage across the capacitor and the inductor are 180 degrees out of phase." The "relative phasor diagram," with I on the real axis, makes this "much more obvious." [9/21 1:15:11–1:18:27]
- **Average power vs phase:** "the average power depends on the difference in phases between the voltage signal and the current signal… greatest when the voltage and the current are in phase." [9/28 0:26:46] Purely reactive load: "energy that is transferred to the load for part of the cycle and then transferred back out… but it does not get dissipated." [9/28 0:41:44] Power factor: resistive gives pf = 1; pure L or C gives pf = 0.
- **Why S = ½VI\* and not Re[VI]:** "the phase of [VI] is going to be φv + φi, that's not what we want." He said twice that Re[VI] "will not give you the correct result for power." [9/28 0:06:08, 0:53:43]
- **Impedance → component:** +j means an inductor, −j a capacitor. Realising a given numeric impedance with components is "fair game." An RL/RC equivalent of an RLC network holds at one frequency only. [9/30 0:52:53]

### P2 (phasor network)
- **Convert sine to cosine first:** "This signal… is not specified in the usual cosine form. So the first thing that we need to do is convert." [9/21 0:09:22]
- **Always return to the time domain:** v(t) is "always going to be the real part of the phasor times e^{jωt}." [9/21 0:29:13] Box the final answer in cosine form, with units.
- Everything from 302 carries over "since KCL and KVL are valid for phasors": series/parallel, division, source transformation, Thévenin/Norton. Phasors need a single frequency.
- **Thévenin:** get Z_Th by turning off the independent sources. If V_oc = 0, the short-circuit method fails as 0/0, so use the external-source method. [9/21, 9/30]
- **His notation:** peak-amplitude phasors (rms only in the power material), written as A e^{jθ} with θ in degrees.

### P3 (op-amps)
- **Output within the rails:** "we also have to always remember that the output voltage has to be within the supply voltages." The board has −Vcc ≤ v_o ≤ +Vcc. [8/31 0:37:43] "Make sure each op amp remains in its linear region." He said this three times. [9/2 0:03:34, 0:10:46] In a cascade, gains multiply. [9/2 0:04:37]
- **The ideal model needs negative feedback** (output tied to v₋). [8/31 0:39:09]
- **Output current:** "KCL and KVL apply everywhere in the circuit, BUT the current at each op amp output is typically not known until everything else has been solved." [9/2 0:05:08] The supply pins carry current, so KCL over only the signal pins doesn't balance. [8/31 0:11:06]
- **Work forward from the inputs:** "starting with those closest to input signals… those will basically act as voltage sources." [9/2 0:07:42]
- Derive gains from the circuit; don't recall them by resistor label, because labels change roles between circuits. [8/31]

### P4 (2nd-order transient): the point sink
- **Order of work:** the "zeroth order preliminary step… is to determine what the initial and final conditions are." The final conditions are "mostly a check." [9/9 0:06:01, 0:10:11]
- **The hard part:** "usually the hardest part… is getting to a differential equation with only one unknown function." [9/9 0:15:22] "The part that often is kind of the trickiest… a differential equation that we can solve for i_L(t)… valid for t ≥ 0." [9/14 0:52:04]
- **Second initial condition:** take it on the derivative, using dv_C/dt(0⁺) = i_C(0⁺)/C or di_L/dt(0⁺) = v_L(0⁺)/L. "We cannot… conclude that the voltage across the inductor at t equal to 0 is equal to 0, because the voltage across an inductor can be discontinuous." Get v_L(0⁺) by KVL from v_C(0) and i_L(0). [9/9 0:08:36; 9/14 0:47:02] On the exam, write 0⁻ and 0⁺ explicitly; his board writes "(0)" for 0⁺. [9/2]
- **One method for every topology:** "Most of RLC circuit analysis will be some variation of this… sometimes taking the derivative." [9/14 1:02:07] For a non-series circuit (Ex 6-10), read α = a/2 and ω₀² = b off the normalized ODE x″ + ax′ + bx = c. **α = R/2L only for series RLC** (parallel: 1/2RC).
- **Classify** by α vs ω₀, by the roots being real or complex, or by R vs 2√(L/C) (series). "The easiest way to see it is that both values of s are real… overdamped." [9/14 1:07:12]
- **Check the final value:** "If you do everything else properly, then it should satisfy the final condition… it's sort of good to see that, in fact, it does." [9/14 1:17:45]
- He did a full **critically damped** numeric example on 9/14, a case never yet seen on a past Exam 1 P4.

## Board / recording issues to know about
- **9/9 particular-integral line:** the coefficient under R looks like "2". It's **R/L** (he says "R over L").
- **9/2:** a capacitor written as 8 µF was corrected in class to **8 mF**.
- **8/26:** **no audio 0:38–1:04.** That stretch (end of the RC example, debouncing, RL setup) comes from the board frames only.
- **9/30:** he said "dependent voltage source" for the MOSFET, but it's a current source. Out of scope anyway.
