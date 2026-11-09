# Ulaby 9.4 video

Deepgram general-nova-3 2025-07-31.0, request 01a1b038-ee43-7772-9a20-18babe748d72, audio 11.0 min.

**[0:00:03]** Okay. So this is Ulaby problem 9.4, and this is an example of, calculating the resonant frequency of a simple RLC circuit. Okay. So we will start as usual by redrawing the circuit. Okay.

**[0:00:32]** So our circuit is very simple here. It has a resistor value r, then an inductor of value l, and a capacitor of value c. Okay. And our, circuit parameters here are that r is one kiloohm, l is 10 millihenries, and c is 10 nanofarads. And what we're asked to do here is to determine the resonant frequency of the circuit.

**[0:01:21]** And what we mean here by the resonant frequency is the frequency at which the input impedance, right, we'll call that z sub I. Right? That is the impedance, between these two terminals here. Alright? If we were to connect something to these terminals out here, then what would the impedance of this circuit look like?

**[0:01:42]** That's what, z sub I is. And the resonant frequency is the frequency at which the input impedance, alright, which we've called z sub I here, is purely real. Okay. So this is a fairly straightforward calculation. Essentially, what we can do to calculate the input impedance is to just calculate the impedance of this resistor in parallel with the series connection of the inductor and the capacitor.

**[0:02:22]** Okay. So we can pretty much calculate that directly. Alright. The, input impedance is... Right.

**[0:02:31]** Anytime you have two impedances in parallel, then the equivalent impedance is the product, of the two impedances divided by the sum. So, the product is r, and then, the other impedance is, that of the inductor and the capacitor in series with each other. So we have j omega l for the inductor plus one over j omega c for the capacitor. And then we divide by the sum of the impedances, which is r plus j omega l plus one over j omega c. Okay?

**[0:03:09]** And if we take this and we multiply both the numerator and the denominator by j omega c, then in the numerator, we get r times one minus omega squared l times c. And in the denominator, we get one minus omega squared l times c plus j omega r c. Okay. So this is now our expression for the input impedance z sub I. And in order to determine, the frequency at which, this quantity is purely real, then what we want to do is to put it in the standard rectangular form.

**[0:03:54]** Okay? So to do that, we will, as usual, multiply the numerator and the denominator by the complex conjugate of the denominator. That is by one minus, omega squared l c minus j omega r c. Okay. So if we do that, then what we get is that the input impedance is r times one minus omega squared l c times one minus omega squared l c minus j omega RC.

**[0:04:27]** Okay. And then in the denominator, we have basically the magnitude of this, quantity, up here in the denominator squared. So that is going to be one minus omega squared l c, squared plus omega squared r squared c squared. Okay. And if we then take the new...

**[0:04:53]** Take this and then in the numerator, separate out the real and imaginary parts, then what we get for the real part is r times one minus omega squared l c times the real part of, this term in the parenthesis here, which is one minus omega squared l c. So we have r times one minus omega squared l c, the quantity squared. And then the imaginary part of the numerator is this minus j omega RC times r times one minus omega squared LC. So we have minus j times omega r squared c times one minus omega squared l c. And then the denominator is still the same.

**[0:05:38]** One minus omega squared l c quantity squared plus omega squared r squared c squared. Okay. So now, we can see that... Excuse me. The imaginary part of z sub I is zero when this second term here in the numerator is zero.

**[0:06:01]** And we can see that that happens when one minus omega squared l c is equal to zero or equivalently omega is equal to one over root l c. Okay. So, we can easily see now that the imaginary part of z sub I is equal to zero when one minus omega squared l c is equal to zero, which means that omega is equal to one over the square root of l times c. Alright. So that is one over the square root of...

**[0:06:36]** And then l, remember, was 10 millihenries. So that is 10 to the minus two. Right? 10 times 10 to the minus three. And then c was 10 nanofarads, so that is 10 to the minus eight.

**[0:06:49]** So times 10 to the minus eight. Okay. So that is, the square root of 10 to the minus 10, which is 10 to the minus five. It's in the denominator. So that then becomes 10 to the five radians per second.

**[0:07:05]** Alright. That is the resonant frequency of the circuit. Okay. And that's basically, that's essentially all there is to, solving this problem. So what are the key points here?

**[0:07:22]** Okay. One is that, this was really just a very simple phasor analysis. Alright? So the phasor analysis of this circuit, it really was relatively simple. Okay.

**[0:07:47]** But then the second part of this is, kind of, what was the point of this problem? Or, perhaps more precisely, you know, what happens at the resonant frequency? Okay. And if we look up at the circuit over here, alright, we can see that, basically, the resonant frequency omega equal to one over root LC, that corresponds to the frequency at which the impedances of the inductor and the capacitor. Right?

**[0:08:31]** Since they're in series, we just add those together. And at the resonant frequency, those impedances cancel each other out because the impedance of the inductor is j omega l. Right? The impedance of the capacitor is one over j omega c or equivalently minus j over omega c. Right?

**[0:08:50]** So it's possible at the resonant frequency for the total impedance to be zero. Then this branch here will be a short circuit. And when this is a short circuit, then the resistor ends up not playing any role in the in the circuit. And so the input impedance will actually be zero. Okay.

**[0:09:11]** So that's what the resonant frequency corresponds to, in this case. Alright? And in fact, from this expression here, we can see that indeed because of this one minus omega squared LC squared factor here in the real part of the e sub I, right, we can easily confirm mathematically that at the resonant frequency, the real part and the imaginary part of the input impedance are zero. So the total input impedance is is zero. So what's happening here at the resonant frequency is, in this particular case, the input impedance goes to zero.

**[0:09:52]** Right? And that happens because the branch with the inductor and the capacitor in series, it has zero impedance. So, basically, you have a short circuit between, the input terminals. Okay. And so, if you have, say, even a little bit of voltage, that's applied between those terminals, then you go...

**[0:10:34]** Get a very large current. So very large response for a very small input. And, that is, in general, characteristic that you often see in a resonant circuit or other resonant system. Okay? And we see that very explicitly in, the case of this very simple circuit here.

**[0:10:54]** Okay. So that's everything for this example, and I will now stop the recording.
