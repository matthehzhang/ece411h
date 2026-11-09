---
course: ECE 411H
kind: problem-set
source: Problem Sets/ECE 411H problem set tips F26.pdf
source_pages: 3
author: Prof. Ed Yu
unit: exam2
topics: [problem-set-policy, write-up-guidelines, exam-write-up, grading-expectations, circuit-diagram, explanations, neatness, worked-example, node-voltage, kcl, ohms-law]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; text layer via pdftotext -layout where present
---

# Getting the Most Out of Problem Sets (and Exams) — ECE 411H, Fall 2026

**Summary**
Instructor handout (adapted from an EE 302 document, Fall 2015) on the purpose of problem sets, how to study with them (work alone after discussing, do a retrospective, rewrite solutions, do not copy solutions — PS = 5% of grade, exams = 85%), and how to write up solutions so a grader can award credit: draw a labeled circuit diagram, write a sentence or key phrase naming the law/concept applied, box final answers with units, be neat. Pages 2–3 show the same textbook problem (Ulaby 2.25, node voltages $V_1, V_2, V_3$) worked five ways — excellent, marginal, poor, unacceptable (bare answers), unacceptable (sloppy) — with margin annotations explaining why. Directly relevant to how Exam 2 work will be graded: explanation and clarity earn credit; unexplained numbers do not.

## Page 1

Header: Unique: 18535 — ECE 411H: Circuit Theory (Honors) — Fall 2026

**Getting the Most Out of Problem Sets (and Exams)**

This document is adapted from a very similar document I created during Fall 2015 and distributed in EE 302 for many years.

**I. The purposes of problem sets and homework**

Despite its relatively small contribution to your course grade, problem sets are an integral part of ECE 411H. Doing the problem sets properly is essential for learning the material and improving your problem-solving abilities generally. The problem sets for ECE 411H are intended to serve several purposes:

- Some of the problems on the problem sets can be solved by straightforward application of key concepts and techniques from the course. These types of problems will help you to gain a solid understanding of these concepts and techniques, and to develop proficiency in using them to solve elementary circuits problems.
- Some of the problems are more challenging, either conceptually or with respect to the mathematics involved. These problems should help you to develop a deeper understanding of key concepts, improve your ability to apply them to the analysis or design of circuits, and become better at solving challenging problems generally.
- Occasionally there may be problems that require you to apply fundamental course concepts in ways that go significantly beyond what has been covered in class, but that can definitely be solved using those concepts. These problems are intended to help you develop and refine your ability to understand ideas and their underlying assumptions at a deeper level, and to bring together concepts from multiple fields in new and creative ways.

**II. Getting the most out of course problem sets**

You have a limited amount of time to devote to each of your courses. Here are some tips on how to make the most effective use of the time you spend on problem sets for ECE 411H and, potentially, for other courses.

- You should discuss the course material and problem sets with your fellow students, but ultimately you should work out each of the problems on your own, and make sure you understand your solution.
- After solving a problem, take a step back and think about why your solution worked, was efficient or clever, etc., and why other approaches you tried did not work, were very cumbersome, etc. This retrospective process is extremely valuable in maximizing the understanding you gain from doing the problem sets.
- To help you in this retrospective process, you should consider rewriting your solutions, neatly and with clear explanations, and then turning in your rewritten solutions for grading. The rewriting process will help you, and person grading your problem sets, to understand the logic of your solution more clearly. In addition, it will give you practice in writing out clear, understandable problem solutions on exams (when you probably won't have time to rewrite your solutions, and when knowing how to explain your reasoning clearly and quickly in writing is crucial). Both your understanding and your grades are likely to improve.
- Solutions to most or all of the problem sets are available to those who look. In fact, you probably do not have to look very hard to find them. Copying from these solutions will not help you learn the material. Instead, what almost always happens is that high scores on the problem sets (which are worth a total of 5% of your course grade) will be more than offset by low exam scores (worth a total of 85%), because you will not have derived the educational benefit that comes from actually solving the problems.

**III. How to write up your problem set (and exam) solutions**

Writing out clear and complete explanations of your solutions to the problem sets will help you understand your solutions better, give you practice in explaining your work that will be valuable for exams, and enable your problem set grader to award you the full amount of credit warranted on your assignments. The ability to communicate your ideas clearly – to professors, other students or colleagues, fellow members of an engineering team, and other audiences – is essential in nearly any endeavor, and part of our goal is to allow you to improve your ability to communicate clearly and concisely to others. Here are a few guidelines for writing clear problem solutions on the problem sets.

- For solving circuits problems, it is very helpful to draw a circuit diagram with components and variables, i.e., unknown voltages and currents, clearly labeled. The diagram will help you work out the problem more reliably, and will help your grader understand your reasoning and equations so that you receive the full amount of credit warranted. Drawing the circuit, or at least key parts of it, will probably also help you to think about it more clearly.

## Page 2

Header: ECE 411H: Circuit Theory (Honors) — Fall 2026, Unique 18535

- For both problem sets and exams, write out a sentence or two, or a few key phrases, explaining your work or indicating the concept/law you are applying. Doing so will help your grader understand your reasoning and give you the credit you deserve for that understanding.
- Neatness counts! It is your responsibility to communicate your work, and the associated understanding, clearly and succinctly to your graders or professors (and, eventually, your managers, customers, sponsors, audience, etc.). If we cannot read or follow your work, we cannot give you credit for what you have done.

Consider Problem 2.25 at right from Ulaby et al. (1st, 2nd, and 3rd editions). The annotated examples given below of excellent, marginal, and poor solutions should help you to understand what constitutes a clear and complete solution to a homework or exam problem generally, and why.

**Textbook excerpt (right column):** *2.25 After assigning node $V_4$ in the circuit of Fig. P2.25 as the ground node, determine node voltages $V_1$, $V_2$, and $V_3$.

**Figure P2.25: Circuit for Problems 2.25 and 2.26.** Rectangular ladder. Top rail: node $V_1$ (left, red dot), then a $3\ \Omega$ resistor, then node $V_2$ (middle, red dot), then a $3\ \Omega$ resistor, then node $V_3$ (right, red dot). Three vertical $6\ \Omega$ resistors: from $V_1$ down to the bottom rail (left), from $V_2$ down to the bottom rail (middle), from $V_3$ down to the bottom rail (right). Bottom rail node labeled $V_4$ (red, at the middle). A 12 V independent voltage source (circle, "− +" with − on the left and + on the right) sits on an outer loop above the top rail, connected from the $V_1$ side (−) to the $V_3$ side (+); a 3 A current arrow (blue) on that outer top wire points to the right (toward the + terminal/$V_3$ side). On the bottom rail, two blue current arrows labeled 1 A: one on the left segment pointing left (from $V_4$ toward the left $6\ \Omega$), one on the right segment pointing left (from the right $6\ \Omega$ toward $V_4$).

**Excellent solution:** (handwritten in pencil, with typeset callouts)

Callout: "Problem clearly labeled" → the handwritten "2.25" at top left.

**Figure (handwritten redraw):** Same circuit redrawn by hand: "→3A" on the top outer wire, "12V" source with "(− +)", nodes $V_1$, $V_2$, $V_3$ across the top with $3\Omega$ between $V_1$–$V_2$ and $V_2$–$V_3$, three vertical $6\Omega$ resistors, bottom rail with "←1A" on the left segment, "$V_4 = 0$" at the bottom middle, "←1A" on the right segment. Callout: "Clearly drawn circuit diagram".

Handwritten text:
Solve for $V_1$, $V_2$, $V_3$.
Current through $6\Omega$ resistor on right is 1 A from $V_3$ to $V_4$
⇒ $V_3 = (1\text{A})(6\Omega) = \boxed{6\text{V} = V_3}$ by Ohm's Law, since $V_4 = 0$.
By KCL at node $V_4$, current through middle $6\Omega$ resistor is zero
⇒ $V_2 = V_4 = \boxed{0\text{V} = V_2}$
Current through $6\Omega$ resistor on left is 1 A from $V_4$ to $V_1$
⇒ $V_1 = 0 - (1\text{A})(6\Omega) = \boxed{-6\text{V} = V_1}$

Callouts: "Clear and correct explanations of work and results" (arrows to the three explanatory sentences); "Final answers clearly indicated by boxes or other obvious marking, with correct units" (arrow to the boxed $-6\text{V} = V_1$).

OPTIONAL CHECKS:
1. We know that $V_3 - V_1 = 12\text{V}$ from the 12V source. From above, $V_3 - V_1 = 6\text{V} - (-6\text{V}) = 12\text{V}$ ✓
2. The current through the $3\Omega$ resistor on the right is 2 A from $V_3$ to $V_2$ by KCL at $V_3$ ⇒ $V_3 - V_2 = (2\text{A})(3\Omega) = 6\text{V}$. From above, $V_3 - V_2 = 6\text{V} - 0\text{V} = 6\text{V}$ ✓
3. The current through the $3\Omega$ resistor on the left is 2 A from $V_2$ to $V_1$ by KCL at $V_1$ ⇒ $V_2 - V_1 = (2\text{A})(3\Omega) = 6\text{V}$. From above, $V_2 - V_1 = 0\text{V} - (-6\text{V}) = 6\text{V}$ ✓
etc.

Callout: "Not necessary for full credit (unless specifically asked for), but it is often useful to check your results for consistency and/or by using an alternate method of solution."

## Page 3

Header: ECE 411H: Circuit Theory (Honors) — Fall 2026, Unique 18535

**Marginal solution, might be acceptable on an exam:**

**Figure (handwritten redraw, smaller):** same circuit: "→3A", "12V (−+)", $V_1$, $3\Omega$, $V_2$, $3\Omega$, $V_3$; three $6\Omega$ resistors with a current "$I_1\uparrow$" marked on the middle $6\Omega$; "←1A", "$V_4$", "←1A" on the bottom.

Handwritten:
$V_4 = 0\text{V}$.
$V_3 = (1\text{A})(6\Omega) = \boxed{6\text{V}}$
$V_1 = (-1\text{A})(6\Omega) = \boxed{-6\text{V}}$
$V_2 = \boxed{0\text{V}}$ since $I_1 = 0$

Callout: "Only cursory work shown, with minimal explanation" (arrows to the boxed answers).

**Poor to unacceptable solution:**

Callout (arrow to empty space where a diagram would be): "No diagram. Probably acceptable in this case, but unacceptable if you are defining any of your own variables (e.g., currents or voltages)"

Handwritten:
$V_4 = 0\text{V}$. $V_3 = (1\text{A})(6\Omega) = \boxed{6\text{V}}$
$V_1 = (-1\text{A})(6\Omega) = \boxed{-6\text{V}}$
$V_2 = \boxed{0\text{V}}$

Callouts: "Only cursory work shown, with minimal explanation" (arrows to the $V_3$ and $V_1$ lines); "No work or explanation – typically results in zero or minimal credit unless the result is extremely obvious." (arrow to the $V_2$ line).

**Unacceptable solution:**

Handwritten (single boxed line): $V_1 = -6\text{V},\ V_2 = 0\text{V},\ V_3 = 6\text{V}$

Callout: "Correct numerical answer with no explanation – typically gets minimal or zero credit."

**Unacceptable solution:**

**Figure (sloppy handwritten scratch work):** "$V_4 = 0$." then "$V_3 = 6\text{V}$" with the "6V" crossed out; a crossed-out line "$V_2 = 12 - (3)(2) = 6\text{V}$"; a diagonal scribble "$V_3 = 12 + V_1 = ?$"; "$V_1 = 6\text{V}$ by symmetry." (the word "symmetry" written diagonally); "$V_3 = 6\text{V}$"; "$V_2 = 0\text{V}$"; a small random diagram at lower left of three vertical resistors labeled 6, 6, 6 with nodes $V_1$, $V_2$, $V_3$ above and "←1" and "1" below; "$V_4 - V_1 = 1\times 6 = 6\text{V}$"; "$V_1 = -6\text{V}$ ?"; and at the bottom a crossed-out "$3\text{A}\times 12\text{V} = 36\text{W}$".

Callouts: "Crossed-out answers – sometimes unavoidable on exams, but do not do this on homework assignments. Clearly erase or re-write." (arrow to the crossed-out $V_3 = 6V$); "Answer not clearly marked, no explanation or reasoning" (arrow to $V_3 = 6V$); "Incorrect and/or nonsensical reasoning or explanations" (arrow to "$V_1 = 6\text{V}$ by symmetry"); "Generally sloppy and hard to follow, with no clear explanation of logic or reasoning. Do not do this!" (italic, general); "Random/unhelpful diagrams" (arrow to the small three-resistor sketch); "Multiple answers, intended answer not clearly indicated." (arrow to "$V_1 = -6\text{V}$ ?"); "Irrelevant information." (arrow to the crossed-out $3\text{A}\times 12\text{V} = 36\text{W}$).

## Index terms

problem set tips, Getting the Most Out of Problem Sets, exams, EE 302, purposes of problem sets, straightforward problems, challenging problems, beyond-class problems, work on your own, retrospective, rewrite solutions, copying solutions, 5% problem sets, 85% exams, write-up guidelines, circuit diagram, label variables, explain concept or law, neatness counts, grader credit, Problem 2.25, Ulaby, Figure P2.25, node voltages V_1 V_2 V_3, V_4 ground, 12 V source, 3 A, 1 A, 3 ohm, 6 ohm, Ohm's law, KCL, excellent solution, marginal solution, poor solution, unacceptable solution, boxed answers with units, optional checks, consistency check, crossed-out answers, multiple answers, irrelevant information, random diagrams, nonsensical reasoning, by symmetry
