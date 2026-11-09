---
course: ECE 411H
kind: problem-set-solution
source: Problem Sets/ECE_411H_PS5_solns_F26.pdf
source_pages: 10
author: Prof. Ed Yu / TA (pp. 1–9 are publisher solutions, © 2016 National Technology and Science Press; p. 10 is handwritten by instructor)
unit: exam2
topics: [average-value, rms-value, periodic-signals, rectified-cosine, trig-integrals, complex-power, node-voltage, conservation-of-complex-power, current-source, rl-load, op-amp, inverting-amplifier, rc-feedback, average-power, inductor-esr, triangular-waveform, conduction-loss]
transcribed: 2026-11-06
method: vision transcription of rendered pages (pdftoppm) by Claude; text layer via pdftotext -layout where present
---

# ECE 411H: Problem Set 5 Solutions

**Summary**
Full worked solutions to PS5. Problems 1–4 (textbook 8.16, 8.20, 8.27, 8.38) are typeset publisher solutions: average/rms of a rectified cosine (24/π V, 8.49 V), dc + cosine (4 V, 5.83 V), difference of two sinusoids (0, √6 = 2.45 V) and a product of sinusoids (2.25 V, 3.9 V) by explicit trig integrals; node-voltage solution of the P8.20 circuit with complex power per element and the check $\mathbf{S}_{total} = 4 - j3.2727$ VA $= -\mathbf{S}_{source}$; the P8.27 RL load $\mathbf{S} = 18.24 e^{j63.4^\circ}$ VA; the P8.38 op-amp RC feedback circuit giving $P_{av} = 2.16$ mW in $R_L$. Problem 5 (handwritten, p. 10) derives $\langle i^2\rangle = I^2(1 + r^2/3)$ for the triangular current, so $P_{avg} = I^2(1 + r^2/3)R$, $P_{ESR} = I^2(1 + r^2/3)R_{ESR}$, and the loss ratio 1.386 when $L$ is doubled. Key exam skills: rms integrals, $\mathbf{S} = \tfrac12 \mathbf{V}\mathbf{I}^*$, $\tfrac12|\mathbf{I}|^2 \mathbf{Z}$, virtual short at op-amp inputs.

## Page 1

**ECE 411H: Problem Set 5 Solutions**

**1. Problem 8.16** Determine the average and rms values of the following periodic waveforms:

(a) $v(t) = |12\cos(\omega t + \theta)|$ V.
(b) $v(t) = 4 + 6\cos(2\pi f t + \phi)$ V.
(c) $v(t) = 2\cos\omega t - 4\sin(\omega t + 30^\circ)$ V.
(d) $v(t) = 9\cos\omega t\,\sin(\omega t + 30^\circ)$ V.

**Solution:**

**(a)**
$$v(t) = |12\cos(\omega t + \theta)| \quad \text{(V)}.$$
$$T = \frac{2\pi}{\omega}.$$

**Figure:** Plot of $v_1(t) = |12\cos\omega t|$ (blue curve) vs. $t$. Vertical axis labeled V with a tick at 12; horizontal axis $t$ with ticks at $T/4$, $T/2$, $3T/4$, $T$. The curve starts at 12 at $t = 0$, falls to 0 at $T/4$ with a cusp, rises to 12 at $T/2$, falls to 0 at $3T/4$, rises to 12 at $T$ (a full-wave-rectified cosine: two humps per period). A dashed vertical line at $t = T$.

Since both $V_{av}$ and $V_{rms}$ are performed over a full cycle, their values will be independent of the value of $\theta$. That is, the average of $|12\cos(\omega t + \theta)|$ is the same as the average of $|12\cos\omega t|$. Furthermore, because of the absolute-value operator, the integral over the first quarter cycle is $1/4$ of the integral over the full cycle. Hence,

$$V_{av} = \frac{4}{T}\int_0^{T/4} 12\cos\omega t\,dt = \frac{4}{T}\cdot\frac{12}{\omega}\sin\omega t\Big|_0^{T/4} = \frac{4}{T}\cdot\frac{12}{\omega}\sin\frac{2\pi}{T}\cdot\frac{T}{4} = \frac{48}{T\omega} = \frac{24}{\pi}\ \text{V}.$$

Similarly,
$$V_{rms} = \left[\frac{4}{T}\int_0^{T/4} 144\cos^2\omega t\,dt\right]^{1/2}.$$

Let $x = \omega t$.
Also, at $t = \frac{T}{4}$, $x = \frac{\omega T}{4} = \frac{\pi}{2}$.

$$V_{rms} = \left[\frac{4\times 144}{\omega T}\int_0^{\pi/2}\cos^2 x\,dx\right]^{1/2}.$$

Since $\int\cos^2 x\,dx = \frac14\sin 2x + \frac{x}{2}$,

$$V_{rms} = \left\{\frac{288}{\pi}\left[\frac14\sin 2x + \frac{x}{2}\right]\Big|_0^{\pi/2}\right\}^{1/2} = 8.49\ \text{V}.$$

**(b)**
$$v(t) = 4 + 6\cos(2\pi f t + \phi)\quad\text{(V)}.$$

Footer: All rights reserved. Do not reproduce or distribute. © 2016 National Technology and Science Press

## Page 2

The average of 4 is simply 4, and the average of the cosine function is zero, irrespective of the values of $f$ and $\phi$.
Hence,
$$V_{av} = 4\ \text{V},$$
$$V_{rms} = \left\{\frac1T\int_0^T [4 + 6\cos(2\pi f t + \phi)]^2\,dt\right\}^{1/2}.$$

Let $x = 2\pi f t + \phi$, $dx = 2\pi f\,dt$.
The limits will then be from $x_1 = \phi$, to $x_2 = 2\pi f T + \phi$.
In view of $f = 1/T$, $x_2 = 2\pi + \phi$.
Hence,

$$V_{rms} = \left[\frac{1}{2\pi f T}\int_\phi^{2\pi+\phi}(4 + 6\cos x)^2\,dx\right]^{1/2}$$
$$= \left[\frac{1}{2\pi}\int_\phi^{2\pi+\phi}(16 + 48\cos x + 36\cos^2 x)\,dx\right]^{1/2}$$
$$= \left\{\frac{1}{2\pi}\left[16x + 48\sin x + 36\left(\frac14\sin 2x + \frac{x}{2}\right)\right]\Big|_\phi^{2\pi+\phi}\right\}^{1/2}$$
$$= 5.83\ \text{V}.$$

**(c)**
$$v(t) = 2\cos\omega t - 4\sin(\omega t + 30^\circ)\quad\text{(V)}.$$

Since the average of the sum of two terms is equal to the sum of the averages of the two individual terms, and since the average of a sinusoidal waveform is zero, regardless of its phase angle, it follows that

$$V_{av} = 0.$$
$$V_{rms} = \left[\frac1T\int_0^T[2\cos\omega t - 4\sin(\omega t + 30^\circ)]^2\,dt\right]^{1/2}$$
$$= \left\{\frac1T\left[4\int_0^T\cos^2\omega t\,dt - 16\int_0^T\cos\omega t\sin(\omega t + 30^\circ)\,dt + 16\int_0^T\sin^2(\omega t + 30^\circ)\,dt\right]\right\}^{1/2}$$

Using the identities
$$\int\cos^2 x\,dx = \frac14\sin 2x + \frac{x}{2},\qquad \int\sin^2 x\,dx = -\frac14\sin 2x + \frac{x}{2}$$
$$\int\cos ax\,\sin(ax + b)\,dx = \frac{x}{2}\sin b - \frac{\cos(2ax + b)}{4a},$$

Term 1:
$$\int_0^T\cos^2\omega t\,dt = \frac1\omega\int_0^{\omega T}\cos^2 x\,dx = \frac{T}{2\pi}\int_0^{2\pi}\cos^2 x\,dx = \frac{T}{2\pi}\left(\frac14\sin 2x + \frac{x}{2}\right)\Big|_0^{2\pi}$$

Footer: All rights reserved. Do not reproduce or distribute. © 2016 National Technology and Science Press

## Page 3

$$= \frac{T}{2}.$$

Term 2:
$$\int_0^T\cos\omega t\sin(\omega t + 30^\circ)\,dt = \left(\frac{t}{2}\sin 30^\circ - \frac{\cos(2\omega t + 30^\circ)}{4\omega}\right)\Big|_0^T$$
$$= \frac{T}{2}\sin 30^\circ - \frac{\cos 30^\circ}{4\omega} + \frac{\cos 30^\circ}{4\omega}$$
$$= \frac{T}{2}\sin 30^\circ.$$

Term 3:
$$\int_0^T\sin^2(\omega t + 30^\circ)\,dt = \frac{T}{2\pi}\left(-\frac14\sin 60^\circ + \frac14\sin 60^\circ + \frac{2\pi + 30^\circ}{2} - \frac{30^\circ}{2}\right)$$
$$= \frac{T}{2}.$$

Hence,
$$V_{rms} = \left[\frac1T\left(4\frac{T}{2} - 16\frac{T}{2}\sin 30^\circ + 16\frac{T}{2}\right)\right]^{1/2}$$
$$= \sqrt{6} = 2.45\ \text{V}.$$

**(d)**
$$v(t) = 9\cos\omega t\,\sin(\omega t + 30^\circ).$$

Using the identity
$$\int\cos ax\,\sin(ax + b)\,dx = \frac{x}{2}\sin b - \frac{\cos(2ax + b)}{4a},$$
$$V_{av} = \frac{9}{T}\int_0^T\cos\omega t\sin(\omega t + 30^\circ)\,dt$$
$$= \frac9T\left[\frac t2\sin 30^\circ - \frac{\cos(2\omega t + 30^\circ)}{4\omega}\right]\Big|_0^T$$
$$= \frac9T\left[\frac T2\sin 30^\circ - \frac{\cos 30^\circ}{4\omega} + \frac{\cos 30^\circ}{4\omega}\right] = \frac94 = 2.25\ \text{V}.$$
$$V_{rms} = \left[\frac1T\int_0^T 81\cos^2\omega t\,\sin^2(\omega t + 30^\circ)\,dt\right]^{1/2}.$$

Let $x = \omega t$, $dx = \omega\,dt$.
Upper limit of integral becomes $\omega T = 2\pi$.
$$V_{rms} = \left[\frac{1}{2\pi}\int_0^{2\pi} 81\cos^2 x\,\sin^2(x + 30^\circ)\,dx\right]^{1/2}.$$

Apply the identity
$$\sin(x + y) = \sin x\cos y + \cos x\sin y.$$

Footer: All rights reserved. Do not reproduce or distribute. © 2016 National Technology and Science Press

## Page 4

Thus,
$$\sin^2(x + 30^\circ) = (\sin x\cos 30^\circ + \cos x\sin 30^\circ)^2$$
$$= (0.866\sin x + 0.5\cos x)^2$$
$$= 0.75\sin^2 x + 0.866\sin x\cos x + 0.25\cos^2 x.$$

The integral then becomes:
$$V_{rms} = \left[\frac{81}{2\pi}\int_0^{2\pi}(0.75\cos^2 x\sin^2 x + 0.866\sin x\cos^3 x + 0.25\cos^4 x)\,dx\right]^{1/2}.$$

From integral tables:
$$\int\cos^2 x\sin^2 x\,dx = -\frac18\left[\frac14\sin 4x - x\right]$$
$$\int\sin x\cos^3 x\,dx = -\frac{\cos^4 x}{4}$$
$$\int\cos^4 x\,dx = \frac38 x + \frac14\sin 2x + \frac1{32}\sin 4x$$

Hence,
$$V_{rms} = \left\{\frac{81}{2\pi}\left[\frac{-0.75}{8}\left(\frac14\sin 4x - x\right) - \frac{0.866}{4}\cos^4 x + 0.25\left(\frac38 x + \frac14\sin 2x + \frac1{32}\sin 4x\right)\right]\Big|_0^{2\pi}\right\}^{1/2}$$
$$= 3.9.$$

(Rest of page blank.) Footer: All rights reserved. Do not reproduce or distribute. © 2016 National Technology and Science Press

## Page 5

**2. Problem 8.20** In the circuit shown in Fig. P8.20, $v(t) = 40\cos(10^5 t)$ V, $R_1 = 100\ \Omega$, $R_2 = 500\ \Omega$, $C = 0.1\ \mu$F, and $L = 0.5$ mH. Determine the complex power for each passive element, and verify that conservation of energy is satisfied.

**Figure P8.20 Circuit for Problem 8.20.** Voltage source $v(t)$ (+ top) on left; $R_1$ in series on the top wire; then a node from which $C$ (middle, shunt) and the series pair $R_2$ (top) + $L$ (bottom) (right, shunt) go to the bottom rail. (Same as the problem statement figure.)

**Solution:** At node $\mathbf{V}_1$ in the circuit of Fig. P8.20(a),

**Figure: Fig. P8.20 (a).** Phasor-domain redraw: source $\mathbf{V}$ (+ top), series $R_1$ on top wire, node $\mathbf{V}_1$ (marked red) at the top of the capacitor branch. Currents marked in red: $\mathbf{I}_1$ with arrow pointing LEFT along the top wire toward $R_1$ (i.e., from node $\mathbf{V}_1$ back through $R_1$ toward the source — defined as flowing from $\mathbf{V}_1$ to $\mathbf{V}$); $\mathbf{I}_2$ with arrow pointing DOWN into the capacitor, labeled $\frac{-j}{\omega C}$; $\mathbf{I}_3$ with arrow pointing RIGHT along the top wire into the $R_2$ + $j\omega L$ branch. A ground symbol (red) at the bottom of the capacitor branch. Right branch: $R_2$ on top, $j\omega L$ below.

$$\frac{\mathbf{V}_1 - \mathbf{V}}{R_1} + \frac{\mathbf{V}_1}{-j/\omega C} + \frac{\mathbf{V}_1}{R_2 + j\omega L} = 0$$

With $\mathbf{V} = 40$ V, $\omega = 10^5$ rad/s, $R_1 = 100\ \Omega$, $R_2 = 500\ \Omega$, $L = 0.5$ mH, and $C = 0.1\ \mu$F, solution leads to

$$\mathbf{V}_1 = 25.84 e^{-j39.29^\circ}\ \text{V},$$
$$\mathbf{I}_1 = \frac{\mathbf{V}_1 - \mathbf{V}}{R_1} = \frac{25.84 e^{-j39.29^\circ} - 40}{100} = (-0.2 - j0.16)\ \text{A},$$
$$\mathbf{I}_2 = \frac{\mathbf{V}_1}{-j/\omega C} = j\omega C\mathbf{V}_1 = j0.2584 e^{-j39.29^\circ} = 0.2584 e^{j50.71^\circ}\ \text{A},$$
$$\mathbf{I}_3 = \frac{\mathbf{V}_1}{R_2 + j\omega L} = (0.0364 - j0.0364)\ \text{A}.$$

Complex power:
$$\mathbf{S}_{R_1} = \frac12|\mathbf{I}_1|^2 R_1 = 3.3388\ \text{W},$$
$$\mathbf{S}_{R_2} = \frac12|\mathbf{I}_3|^2 R_2 = 0.66116\ \text{W},$$
$$\mathbf{S}_L = \frac12|\mathbf{I}_3|^2(j\omega L) = j0.066116\ \text{VAR},$$

Footer: All rights reserved. Do not reproduce or distribute. © 2016 National Technology and Science Press

## Page 6

$$\mathbf{S}_C = \frac12|\mathbf{I}_2|^2\left(\frac{-j}{\omega C}\right) = -j3.3388\ \text{VAR},$$
$$\mathbf{S}_{source} = \frac12\mathbf{V}\mathbf{I}_1^* = \frac12\times 40\times\mathbf{I}_1^* = (-4 + j3.2727)\ \text{VA}.$$

Sum of all complex powers of passive elements:
$$\mathbf{S}_{total} = 3.3388 + 0.66116 + j0.066116 - j3.3388 = 4 - j3.2727\ \text{VA},$$
which is equal to the complex power *supplied* by the source.

(Rest of page blank.) Footer: All rights reserved. Do not reproduce or distribute. © 2016 National Technology and Science Press

## Page 7

**3. Problem 8.27** Determine $\mathbf{S}$ for the RL load in the circuit of Fig. P8.27, given that $\mathbf{I}_s = 4\angle 0^\circ$ A, $R_1 = 10\ \Omega$, $R_2 = 5\ \Omega$, $\mathbf{Z}_C = -j20\ \Omega$, $R = 10\ \Omega$, and $\mathbf{Z}_L = j20\ \Omega$.

**Figure P8.27: Circuit for Problem 8.27.** Same as problem statement: $\mathbf{Z}_C$, $R_1$, and current source $\mathbf{I}_s$ (arrow up) in parallel between top and bottom rails; $R_2$ in series from the top rail to terminal $a$; load $R$ in series with $\mathbf{Z}_L$ from $a$ down to $b$ on the bottom rail; shaded box labeled Load.

**Solution:**

**Figure:** Solution redraw of the same circuit with the top rail node labeled $\mathbf{V}$ (blue dot at the junction above the current source), current $\mathbf{I}$ (blue arrow pointing right) flowing from node $\mathbf{V}$ through $R_2$ toward terminal $a$, and a ground symbol on the bottom rail at the lower left (bottom rail is the reference).

$$\mathbf{V}\left(\frac{1}{\mathbf{Z}_C} + \frac{1}{R_1} + \frac{1}{R_2 + R + \mathbf{Z}_L}\right) = \mathbf{I}_s$$
$$\mathbf{V}\left(\frac{1}{-j20} + \frac{1}{10} + \frac{1}{5 + 10 + j20}\right) = 4$$

Solution gives
$$\mathbf{V} = 31.6 - j4.6 = 31.93 e^{-j8.28^\circ}\ \text{V}.$$

For RL load:
$$\mathbf{S} = \frac12\mathbf{V}_{ab}\mathbf{I}^*$$
$$= \frac12\frac{(10 + j20)}{15 + j20}\mathbf{V}\times\left(\frac{\mathbf{V}}{15 + j20}\right)^*$$
$$= (5 + j10)\frac{|\mathbf{V}|^2}{|15 + j20|^2} = 11.18 e^{j63.4^\circ}\times\frac{(31.93)^2}{625} = 18.24 e^{j63.4^\circ}\ \text{VA}.$$

(Rest of page blank.) Footer: All rights reserved. Do not reproduce or distribute. © 2016 National Technology and Science Press

## Page 8

**4. Problem 8.38** Determine the amount of power delivered to $R_L$ in the circuit of Fig. P8.38, given that $v_{in}(t) = 0.5\cos 2000t$ V, $R_1 = 1$ k$\Omega$, $R_2 = 10$ k$\Omega$, $C = 0.1\ \mu$F, $R_L = 1$ k$\Omega$, and $L = 0.2$ H.

**Figure P8.38: Op-amp circuit for Problem 8.38.** Same as problem statement: $v_{in}(t)$ (grounded −) → $R_1$ → inverting input; + input grounded; feedback $R_2 \parallel C$ from output to inverting input; output $v_{out}$ drives $\mathbf{I}_L$ (arrow down) through $R_L$ then $L$ to ground.

**Solution:**

**Figure:** Phasor-domain redraw with labels (blue): source $\mathbf{V}_{in}$ (+ top, − grounded); current $\mathbf{I}_1$ (arrow right) flows from the source through $R_1$ to the inverting-input node, which is labeled $\mathbf{V}_n = \mathbf{V}_p = 0$ (blue dot); $\mathbf{I}_n = 0$ (arrow right into the op-amp − input). From the inverting node, $\mathbf{I}_1$ (arrow up) goes up into the feedback network, splitting into $\mathbf{I}_2$ (arrow up, into the $R_2$ branch on top) and $\mathbf{I}_C$ (arrow right, into the capacitor branch labeled $-j/\omega C$). Both feedback branches terminate at the output node $\mathbf{V}_{out}$ (open circle). From $\mathbf{V}_{out}$, $\mathbf{I}_L$ (arrow down) flows through $R_L$ then $j\omega L$ to ground. Op-amp + input grounded.

$\mathbf{V}_{in} = 0.5\angle 0^\circ$ V.
Since $\mathbf{V}_n = 0$,
$$\mathbf{I}_1 = \frac{\mathbf{V}_{in}}{R_1}.$$
Also,
$$\mathbf{I}_1 = \mathbf{I}_2 + \mathbf{I}_C$$
$$= \frac{\mathbf{V}_n - \mathbf{V}_{out}}{R_2} + \frac{\mathbf{V}_n - \mathbf{V}_{out}}{-j/\omega C}$$
$$= -\mathbf{V}_{out}\left(\frac{1}{R_2} + j\omega C\right).$$

Footer: All rights reserved. Do not reproduce or distribute. © 2016 National Technology and Science Press

## Page 9

Hence,
$$\mathbf{V}_{out} = -\left(\frac{R_2}{R_1}\right)\left(\frac{1}{1 + j\omega R_2 C}\right)\mathbf{V}_{in}$$
$$= -\left(\frac{R_2}{R_1}\right)\frac{1 - j\omega R_2 C}{1 + \omega^2 R_2^2 C^2}\mathbf{V}_{in}.$$

For $\mathbf{V}_{in} = 0.5$ V, $R_1 = 1$ k$\Omega$, $R_2 = 10$ k$\Omega$, $\omega = 2000$ rad/s, and $C = 0.1\ \mu$F,
$$\mathbf{V}_{out} = -(1 - j2)$$
$$= 2.24 e^{j116.6^\circ}\ \text{V}.$$
$$\mathbf{I}_L = \frac{1}{R_L + j\omega L}\mathbf{V}_{out}$$
$$= \frac{1}{10^3 + j400}\times 2.24 e^{j116.6^\circ} = 2.08 e^{j94.8^\circ}\quad\text{(mA)}.$$

Power delivered to $R_L$ alone is:
$$P_{av} = \frac12|\mathbf{I}_L|^2 R_L = \frac12\times(2.08)^2\times 10^{-6}\times 10^3 = 2.16\ \text{mW}.$$

(Rest of page blank.) Footer: All rights reserved. Do not reproduce or distribute. © 2016 National Technology and Science Press

## Page 10

(Handwritten on ruled paper, black ink. Instructor's solution to Problem 5.)

**5. a)** The instantaneous power dissipated in $R$ is $p(t) = [i(t)]^2 R$.
The average power is obtained by averaging $p(t)$ over one period, $T$, of the current waveform. Thus, we want to average $[i(t)]^2$:
$$P_{avg} = \langle p(t)\rangle = \frac1T\int_0^T [i(t)]^2 R\,dt = \left(\frac1T\int_0^T[i(t)]^2\,dt\right)R \equiv \langle i^2\rangle R$$
$$\langle i^2\rangle = \frac1T\int_0^T[i(t)]^2\,dt\ ;$$ we can average over any interval of duration $T$, or shift the waveform by any amount of time, so

**Figure (small sketch, labeled "assume:"):** axes $i(t)$ vs $t$; a dashed horizontal line at level $I$; the waveform starts at $t = 0$ at its peak (above $I$), descends linearly to a trough at $t = T/2$ (below $I$), and rises linearly back to the peak at $t = T$ (dashed vertical line at $T$). I.e., the waveform is shifted so that a "V" shape spans one period, centered at $T/2$: $i(t) = I + rI(1 - 4t/T)$ on $0 \le t \le T/2$.

and also note that the integral from 0 to $T/2$ has the same value as the integral from $T/2$ to $T$.

$$\Rightarrow\langle i^2\rangle = \frac1T\left[\int_0^{T/2}\left(I + rI\left(1 - \tfrac{4t}{T}\right)\right)^2 dt + \int_0^{T/2}\left(I - rI\left(1 - \tfrac{4t}{T}\right)\right)^2 dt\right]$$
$$= \frac1T\left[\int_0^{T/2}\left(I^2 + 2rI^2\left(1 - \tfrac{4t}{T}\right) + r^2 I^2\left(1 - \tfrac{4t}{T}\right)^2\right)dt + \int_0^{T/2}\left(I^2 - 2rI^2\left(1 - \tfrac{4t}{T}\right) + r^2 I^2\left(1 - \tfrac{4t}{T}\right)^2\right)dt\right]$$
(Between the two bracketed integrands there is a scribbled-out mark with a "+" written beneath it — the author crossed out a symbol and wrote "+" to join the two integrals.)
$$= I^2 + \frac{2r^2 I^2}{T}\int_0^{T/2}\left(1 - \tfrac{4t}{T}\right)^2 dt = I^2 + \frac{2r^2 I^2}{T}\left[\frac13\left(-\frac{T}{4}\right)\left(1 - \tfrac{4t}{T}\right)^3\right]_0^{T/2}$$
$$= I^2 + \frac{r^2 I^2}{6}(1 + 1) = I^2 + r^2 I^2/3 = I^2\left(1 + \tfrac13 r^2\right)$$
$$\Rightarrow \boxed{P_{avg} = I^2\left(1 + r^2/3\right)R}$$

**b)** For this part of the problem, we simply substitute $R_{ESR}$ for $R$:
$$\boxed{P_{ESR} = I^2\left(1 + r^2/3\right)R_{ESR}}$$

**c)** From part (b), we know the average conduction-related loss is
$P_{avg} = I^2(1 + r^2/3)R_{ESR}$. If the inductor $L$ doubles in value (the word "value" is inserted above a crossed-out word, [illegible, likely: "size"]), we have
$r \to r' = \tfrac12 r$ and $R_{ESR}\to R'_{ESR} = 1.4R_{ESR}$, with $r = 0.2$.
$$\Rightarrow P'_{avg} = I^2\left(1 + r'^2/3\right)R'_{ESR} = I^2\left(1 + \frac{r^2}{12}\right)(1.4R_{ESR})$$
$$\Rightarrow\frac{P'_{avg}}{P_{avg}} = \frac{I^2(1 + r^2/12)(1.4R_{ESR})}{I^2(1 + r^2/3)R_{ESR}} = \frac{1 + r^2/12}{1 + r^2/3}(1.4) = \frac{1 + \frac{(0.04)}{12}}{1 + \frac{(0.04)}{3}}(1.4) = \boxed{1.386}$$

## Index terms

Problem Set 5 solutions, PS5, problem 1, problem 2, problem 3, problem 4, problem 5, 8.16, 8.20, 8.27, 8.38, average value V_av, rms value V_rms, rectified cosine, |12 cos|, 24/pi, 8.49 V, dc offset, 4 V, 5.83 V, sum of sinusoids, sqrt(6), 2.45 V, product of sinusoids, 2.25 V, 3.9 V, trig integral identities, int cos^2, int sin^2, int cos ax sin(ax+b), int cos^2 sin^2, int sin cos^3, int cos^4, quarter-cycle symmetry, change of variable x = omega t, node-voltage equation, V_1 = 25.84 e^{-j39.29}, I_1, I_2, I_3, complex power per element, S_R1 = 3.3388 W, S_R2 = 0.66116 W, S_L = j0.066116 VAR, S_C = -j3.3388 VAR, S_source = -4 + j3.2727 VA, S_total = 4 - j3.2727 VA, conservation of complex power, (1/2)|I|^2 Z, (1/2) V I*, Figure P8.20(a), current source node equation, V = 31.93 e^{-j8.28}, current divider, S = 18.24 e^{j63.4} VA, RL load, op amp virtual short, V_n = V_p = 0, I_n = 0, RC feedback, V_out = -(R2/R1)/(1 + j omega R2 C) V_in, V_out = -(1 - j2), 2.24 e^{j116.6}, I_L = 2.08 e^{j94.8} mA, P_av = 2.16 mW, instantaneous power i^2 R, <i^2>, triangular waveform, ripple r, I^2(1 + r^2/3), P_ESR, R_ESR, r' = r/2, 1.4 R_ESR, loss ratio 1.386, switch-mode power supply, inductor doubled
