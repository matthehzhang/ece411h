# Ulaby 13.31 video

Deepgram general-nova-3 2025-07-31.0, request 01a1b03a-48d8-7970-8ba4-411fcfa3867c, audio 31.1 min.

**[0:00:03]** Okay. So this is Ulaby problem 13.31, and this is an example here of average power calculations. K. So as an example of average power calculations using Fourier series circuit analysis. Okay.

**[0:00:37]** So what we have here is a problem where we are given... We we have this circuit down here. So an RLC parallel circuit, and we're given the form of the current source here essentially as a Fourier series already. And, the problem is asking us to compute the average power that's dissipated in the resistor, given these values here for the for the circuit components. Okay.

**[0:01:05]** So let's go ahead and redraw the circuit as usual. K. So we have a current source, I sub s of t, an inductor l, a capacitor c, and a resistor r. Okay. And these are all connected in parallel.

**[0:01:36]** Alright? And the resistor is one kiloohm. The inductor is one Henry, and the capacitor is one microfarad. And the current source, I sub s of t, is 10 plus five times the cosine of a 100 t plus 30 degrees minus the cosine of 200 t minus 30 degrees, and that's in milliamps. Okay.

**[0:02:17]** And the question is to find the average power. I'll call it p average. It's an a, right, that's dissipated in the resistor r. Okay. So, to solve this problem, what we wanna do is to take this expression for I sub s of t and convert it to the phasor domain.

**[0:02:50]** Right? Then analyze the circuit in the phasor domain and obtain the current and or the voltage for the resistor r from which we can then calculate the, the power. Okay. So that's, the process that we'll go through. So the first step here is to basically take the Fourier series.

**[0:03:20]** K. The Fourier series expression for I sub s of t, which essentially we have, we pretty much have that already and then express I sub s. Alright. The corresponding, phasor quantity in the phasor domain. Okay.

**[0:03:51]** So, we have that I sub s of t, alright, is equal to 10 plus five times the cosine of 100 t plus 30 degrees minus the cosine of 200 t minus 30 degrees in milliamps. Okay. So in the phasor domain, right, we can see that we have a frequency component at omega equal to zero, another at omega equal to 100 radians per second, and a third at omega equal to 200 radians per second. So in the phasor domain, we can write I sub s as being 10. Alright.

**[0:04:36]** That is the omega equal to zero component plus five times e to the j times 30 degrees. That's from this term here, which is the frequency component at omega equal to a 100 radians per second. And then minus e to the minus j 30 degrees. Right? That is from this term over here.

**[0:05:07]** That is the frequency component at omega equal to 200 radians per second. Right? All of this, again, in milliamps. Okay. So going to the phasor domain, once we had, the series...

**[0:05:25]** The Fourier series expansion for I sub s, going to the phasor domain actually was very straightforward. Part of that was also that these components here are already in, the standard cosine form. Alright? So we didn't have to convert them to the standard cosine form. So once we have that, then the second step is to look at the circuit and analyze it in the phasor domain to obtain the voltage and or the current, for the resistor r.

**[0:05:58]** So to do that, we'll take the voltage at the bottom node here to be zero, then the voltage at this upper node, will take to be v one, and we'll do a simple node voltage analysis essentially, calculating or using KCL at the node v one to solve for the voltage v one, which is just the goat voltage across the resistor as well. And from that, we'll be able to calculate the current... Or sorry, the power. Okay. So what we wanna do then is to analyze the circuit in the phasor domain to obtain the voltage that we labeled v one, as a phasor.

**[0:06:47]** So we're going to apply KCL at that upper node v one. Okay? And when we do that, where we have the current coming in from the left from the, current source... Or sorry. The current going out, to the left along the branch containing the current source, that's gonna be minus I sub s.

**[0:07:08]** Right? Because we have I sub s going in. Then the current flowing down through the inductor, that's gonna be v one over the impedance of the inductor, which is j omega l, plus, the current flowing down through the capacitor, which is v one over the impedance of the capacitor, which is one over j omega c, plus the current flowing downward through the resistor, which is just v one over r. All of that has to add up to zero. Okay?

**[0:07:42]** And if we group together the terms proportional to v one, we have one over r plus one over j omega l plus j omega c times v one is equal to I sub s. Right? Or if we divide both sides of this equation by this quantity here in the parenthesis to solve for v one, we get the v one is equal to I sub s divided by one over r plus one over j omega l plus j omega c. Alright? So now to further simplify this, we can multiply the numerator and the denominator by j omega r times l.

**[0:08:38]** Okay. And that will, get rid of the fractions, right, in the denominator. And so this will give us in the numerator j omega r times l. Alright. We'll write down the I sub s at the end.

**[0:08:55]** And in the denominator, from j omega r l times one over j omega l, we get r. Alright. From j omega r l times one over r, we get plus j omega l. And then from j omega c times j omega r l, we get minus omega squared r l c. All of this times I sub s.

**[0:09:21]** Okay? And then, we can, group together the real and imaginary terms in the denominator. So we get j omega r l in the numerator and then r times one minus omega squared l c plus j omega l in the denominator, all of this times I sub s. Okay. So that is v one, which is the voltage at the upper node, also the voltage across the resistor in the phasor domain.

**[0:09:57]** Alright. Now, what we wanna do is convert, to the time domain, then compute the average power. Right? Could directly calculate, v one explicitly by substituting in I sub s as a phasor over here, and then using what we know and worked out in class to be the result for the average power, then we don't necessarily have to go back to the time domain explicitly. But in order to see a little bit more about how this problem works, we will actually convert back to the time domain.

**[0:10:44]** Alright? So let's go ahead now and plug in the phasor expression for I sub s and also work with this prefactor over here, basically, the current to voltage transfer function. Alright? By converting this prefactor over here from its current form to the polar form, alright, where the polar form is going to be helpful in working conveniently, particularly with the phase factors in the phasor domain. Okay.

**[0:11:26]** So converting that prefactor into polar form, right, what we need is the magnitude, right, which is going to the magnitude... Be the magnitude of the numerator divided by the magnitude of the denominator. The magnitude of the numerator is just omega times r times l. The magnitude of the denominator is the square root of the real part squared plus the imaginary part squared. So it's gonna be the square root of r squared times one minus omega squared l c, the quantity squared, plus omega squared l squared.

**[0:12:03]** All of this under the square root. And then we have the phase, which is e to the minus j times the inverse tangent of the imaginary part of the denominator divided by the real part of the denominator. So omega l divided by r times one minus omega squared l c. Okay. And then finally, right, it's...

**[0:12:38]** We have this minus sign in the exponent of the phase factor because, without the minus sign, that would be the phase of the denominator. But we're writing this in the numerator, so, we have to put a minus sign in the exponent. Then finally, we have this factor of j over here. We can't forget about that. That's either the j times 90 degrees.

**[0:13:01]** All this times I sub s. Alright? Now, we can plug in numerical values for r and l. Alright? So r was...

**[0:13:15]** And c. R was one kilo ohm. L was one Henry. C is one microfarad. So 10 to the minus six farads.

**[0:13:25]** Okay. So plugging those in, then in the numerator, we have r a thousand times l one. So we... Times omega. So we get a thousand omega divided by the square root of r squared.

**[0:13:38]** It's 10 to the third square. That's 10 to the six times one minus. And then l times c is one times 10 to the minus six. So 10 to the minus six times omega squared quantity squared. And then plus omega squared l squared l is one, so just omega squared.

**[0:13:58]** All this under the square root. Then we have e to the minus j times the inverse tangent now of omega l, which is just omega since l is equal to one times divided by r, which is 10 to the third times one minus omega squared l c, which is 10 to the minus six omega squared. Okay. And then times e to the j times 90 degrees times I sub s. Alright?

**[0:14:35]** So now from this, we can compute, v one at, the frequencies that we know show up in I sub s, which are zero, 100, and 200. Okay. So v one at omega equal to zero, right, we can see, because of this omega in the numerator here, then that's just gonna be zero. Okay? So that means that there's no DC component to the voltage across the resistor.

**[0:15:10]** And if... Even though there is a DC component to the current, I s... And if we look back at the circuit, we can see, that at zero frequency, this inductor is gonna behave as a short circuit. So this node and this node are short circuit to each other. So it makes sense that the DC component of the voltage is zero.

**[0:15:37]** Okay. So that's a quick, little check there that, this result makes sense. Then we can compute v one at omega equal to 100, okay, using this expression up here. Right? So we have a thousand times a 100, that's 10 to the fifth, divided by 10 to the sixth times one minus 10 to the minus six times a 100 squared, that's 10 to the fourth.

**[0:16:08]** So one minus 10 to the minus two quantity squared plus omega squared, that's 10 to the fourth. Okay. Times e to the minus j times the inverse tangent of omega 10 to the two over 10 to the three times one minus 10 to the minus two. Alright? Then times e to the j 90 degrees times I sub s at omega equal to 100.

**[0:16:45]** Alright? And if we calculate out all these numerical values over here, then we get 100.5. Alright? That's this expression here. Alright?

**[0:17:02]** Times e to the j times 84.232 degrees. That includes this e to the j 90 degree, factor over here times the I sub s at omega equal to 100. Alright? From our earlier expression that we worked out for I sub s in the phasor domain, at a 100 radians per second, I sub s was five, times e to the j 30. Alright.

**[0:17:37]** So I sub s at omega equal to 100 was five e to the j 30 degrees. So if we plug that in here for I sub s, then we get five times a 100.5, that's five zero two point five times e to the j, and then 30 plus 84.232, that's one one four point two three degrees. Okay. So that's v one at... Make it equal to a 100 radians per second.

**[0:18:12]** And then at 200, alright, we get from the expression up here. Alright. It's a thousand times 200. That's two times 10 to the fifth divided by the square root of 10 to the sixth times one minus... And then omega squared is four times 10 to the fourth.

**[0:18:39]** So four times 10 to the minus two squared plus four times 10 to the fourth. All this under the square root is either the minus j. It's the inverse tangent of 200. Right? That's omega.

**[0:19:00]** Divided by 10 to the third times one minus four times 10 to the minus two, right, times e to the j 90 degrees times I sub s at omega equal to 200. Alright? And if we work out the numbers here, then for this magnitude over here, we get two zero three point nine five. And then from the phase factors, the two phase factors together, we get e to the j 78.23 degrees. That's gonna be times I sub s at omega equal to 200.

**[0:19:45]** Alright. If we look back again at what we worked out here for I sub s in the phasor domain, the, component at omega equal to 200 is minus e to the minus j 30 degrees. K. So I sub s at omega equal to 200 is equal to minus e to the minus j times 30 degrees. Alright?

**[0:20:11]** And so this is going to be equal to minus two zero three point nine five times e to the j 48.23 degrees. Alright? Or if we wanted to, we could take this minus sign over here and, include it in the phase, if we want it. But it turns out not to matter if we do that. Okay.

**[0:20:38]** So having worked out those components of v one in the phasor domain, then what we get in the time domain is that v one of t is equal to five zero two point five times the cosine of 100 t, plus one fourteen point twenty three degrees. Alright. That's from this result here, right, for the phasor component of v one at omega equal to 100. Right? So we get the same amplitude and then we get this phase 114.23 degrees over here in the standard cosine form at an angular frequency of a 100 radians per second.

**[0:21:22]** And then similarly, we get minus two zero three point nine five. That's this over here times the cosine of 200 t plus 48.23 degrees. And all of this is in millivolts. Okay. So how do we take this and compute the average power?

**[0:21:50]** Alright. So let's recall that in general, the average power, okay, is going to be... It's the average over one cycle of the voltage times the current. Alright? And we worked out in class that this was equal to...

**[0:22:15]** Right? If we express the voltage and the current in their Fourier series forms, it's the product of the DC components plus the sum from n, going from one to infinity of one half times the, voltage amplitude times the current amplitude times the cosine of the phase difference between the voltage and the current at that frequency. Okay. Now, for a resistor, the current, alright, in general is just the voltage divided by the resistance. That's just Ohm's law.

**[0:23:12]** Right? Since the resistance is purely real, then the phase of the voltage and the current, they're equal to each other. Alright? And when they're equal, then this cosine factor over here is always equal to one. Alright?

**[0:23:31]** So for a resistor, the average power is just v d c times I d c plus sum from n going to one to infinity of one half, and then it's the magnitude of v sub n times I sub n. Right? So that's going to be, v d c squared over r. Right? Again, just using Ohm's law plus the sum from n going to one to infinity of one half v sub n squared over r.

**[0:24:08]** Okay? And so we can use that to compute the average power, right, having computed the, Fourier series components of the voltage already. So, the voltage has zero DC components, so this doesn't contribute anything. Alright? So that's zero.

**[0:24:31]** And then we have plus one half. That's this one half over here times one over 10 to the third. Right? That's the one over r over here since r is one kilo ohm. And then we have the sum of, the voltage, amplitudes, right, at the different frequencies.

**[0:24:55]** So 502.5 squared plus two zero three point nine five squared. And then, those were amplitudes in millivolts. So if we want the average power in watts, we have to multiply by 10 to the minus three to convert the voltages to volts and then square it since we're taking the voltages square. Right? So this factor here is included because the v sub n were computed in millivolts.

**[0:25:37]** Okay. And so then, if we just calculate out these numbers, then what we get is that the average power is 1.471 times 10 to the minus four watts, or we can express it in microwatts as a 147.1 microwatts. Okay. So that's the answer, for this example. And, if we look back on what we did and think about what some of the key points were in this example, one is...

**[0:26:17]** Right. Basically, what we did was in doing the Fourier series circuit analysis, what we did was we computed, the Fourier series for the known input voltages and currents. In this case, we were basically given that information. Then we converted that to the phasor domain. Okay?

**[0:26:37]** And then we computed... We analyzed the circuit in the phasor domain, right, which is a relatively straightforward thing to do. We know how to do it from earlier in the semester at a single frequency, then we use the idea of superposition to combine, the multiple frequencies in the four a series expansion together. We can do that for voltages and currents since those are linear quantities and we have a linear circuit. Alright?

**[0:27:07]** And then... Alright. So that first point is that for for a series circuit analysis in general, right, what we wanna do is to compute, right, or in this case, really to recognize, the Fourier series for, our known input voltages and or occurrence. Alright? Then...

**[0:27:52]** Alright. Once we have those components, each of which is at a specific frequency, then we analyze the circuit in the phasor domain, alright, which works at a particular frequency. And then, we can use the idea of superposition. Right? We don't really have to use it, explicitly.

**[0:28:20]** We're using it implicitly, in doing, the Fourier series analysis. So we're using superposition to combine our results from multiple frequencies. Okay. The second, point is that, from what we worked out in class, right, we saw that only the voltage and current components that are at the same frequencies as each other, right, contribute to the average power dissipation. So here, we just wanna recognize that.

**[0:29:01]** Right? That only the voltage and frequency components at the same frequency as each other, right, contribute to the average power dissipation. Okay. And that's basically because of the nature of the trigonometric integrals that are involved. So the other...

**[0:29:44]** The cross terms will essentially all end up going to zero. Right? And so we only have to take... Right. We basically take the square of each individual frequency combination.

**[0:29:59]** And then finally, I... You'll notice that at the end, right, we were given the current, and therefore, we calculated the voltage in milliamps and millivolts respectively. But we had to remember at the end to include this factor of 10 to the minus three for each. And so in the calculation of power, 10 to the minus three squared in order to get the power in watts. Alright?

**[0:30:29]** And then we could convert that to whatever, other unit, we want. In this case, we converted it to microwatts. Right? So, we wanna be careful in general in making sure to work with consistent units. Okay.

**[0:30:58]** So that is, this example. You will be 13.31, and I will stop the recording here.
