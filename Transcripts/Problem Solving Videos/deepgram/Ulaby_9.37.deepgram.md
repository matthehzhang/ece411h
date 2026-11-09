# Ulaby 9.37 video

Deepgram general-nova-3 2025-07-31.0, request 01a1b039-52cb-7bd1-ba0f-715249423315, audio 30.5 min.

**[0:00:05]** Okay. So this is Ulaby 9.37. Alright? And this is an example. Okay, of, an op amp highpass filter circuit.

**[0:00:27]** Okay. So, basically, what we want to do here is to take the circuit as shown here. We wanna calculate its transfer function. Alright? The output voltage over the input voltage, which is v sub s.

**[0:00:42]** Okay. Then we wanna generate the Bode plots for this, which we'll do in the linear approximation. And then, from, that analysis, we want to deduce what kind of filter this is and what its maximum gain is. Okay. So, let's go ahead with this.

**[0:01:02]** So we will... As usual, we'll start off by drawing the circuit. And so we have an op amp here. Okay. And then we have a feedback resistor connection like this.

**[0:01:24]** The noninverting input of the op amp is connected to our input, v sub s, and then the noninverting input is connected to ground through a resistor and a capacitor. Okay? And we have the output voltage over here, v o. Okay. And this is a capacitor with value c.

**[0:01:54]** This is a resistor r one. This is a resistor r two. Okay? And what we're asked to do here is to first calculate the transfer function, okay, which is the output voltage over our input v sub s. Then we wanna generate the Bode plots for r one being equal to one kilo ohm, r two being equal to four kilo ohms, and c being one microfarad.

**[0:02:32]** And then part c, based on our analysis, we wanna determine what type of filter this is. Right? I already told you the answer, but we'll see why it is that. And then what is its maximum gain? Okay.

**[0:02:52]** So, let's go ahead and, take a look at this. So, the first part of this is to calculate the transfer function, meaning basically calculating the output voltage which will, be a function of, v sub s. Alright? And so to do that, we will proceed in the usual way as we do for op amps, which is to apply KCL at, in this case, the inverting input of the op amp where, by, the ideal op amp rules, we know that the voltage has to be v sub s. Right?

**[0:03:26]** Because the voltage at the non inverting input is v sub s. Alright? So for part a, calculating the transfer function, all we wanna do is to apply KCL at the op amp inverting input where the voltage is v sub s. Alright? So the current going out this way to the left is going to be that voltage v sub s minus zero.

**[0:04:01]** So just v sub s divided by the impedance of r one in series with c. So that's r one plus one over j omega c. And then we add to that the current flowing up this way and to the right through the resistor r two. That current is the voltage across the resistor, which is v s minus v o divided by the resistance r two. These two currents have to add up to zero.

**[0:04:28]** Okay? So now we will, as usual, group together, the terms proportional to, the same variable. So for v s, alright, we have this first term over here. So one over... Sorry.

**[0:04:45]** This is r one here. One over r one plus one over j omega c. And then from this second term over here, we have plus one over r two. Okay. Those are multiplying v sub s.

**[0:05:06]** And then we have this minus v o over r two on the left, so that becomes one over r two times v o, without the minus sign on the right. Now, to, simplify this a bit, what we want to do is to take this equation and multiply it by, r two over j omega c. Okay. Multiplying by r two, we'll get rid of this r two and this r two in the denominators here, multiplying by j omega c in the denominator will, turn this term into just a one. Alright?

**[0:05:49]** And so, if we go ahead and, do this, then from this first term over here, we're going to get an r two in the numerator divided by one. Right? That's j omega c times one over j omega c, and then plus j omega r one times c. And then from the one over r two term over here, we're going to get just one over j omega c, all this times v s. And that's equal to, on the right hand side, one over j omega c times v o.

**[0:06:29]** Alright? And then, here on the left, what we wanna do next is to take these two terms and put them over a common denominator. And that common denominator is going to be just the product of the two individual denominators. So if we do that, then from this r two over here, we're going to get r two times j omega c. And then from this one over here, we're gonna get one plus j omega r one c.

**[0:07:02]** So plus one plus j omega r one c. And then our denominator is going to be j omega c times one plus j omega r one times c. All of this still times v sub s. And then on the right hand side, we get one over j omega c times v o. Okay.

**[0:07:25]** So now, it's very easy for us to solve for the transfer function. So h of omega. Right? It's v o over v s. Alright?

**[0:07:36]** So, essentially, we just divide both sides of this equation by v s and multiply both sides by j omega c. And that's gonna cancel out this j omega c in the denominator over here. So what we're going to get is in the numerator, one plus j omega, and then it's r one times the quantity r one plus r two times c divided by one plus j omega r one c. Right? So this is our transfer function h of omega.

**[0:08:12]** Okay. And from looking at this, right, we can see that this transfer function, right, it has one zero, right, where the numerator goes to zero and one pole where the denominator goes to zero. So the transfer function, right, it has a simple zero and omega... We'll call it omega c one. Alright?

**[0:08:43]** And it is one over r one plus r two times c. And it has a simple pull at omega c two. Right? And we can see from the denominator that omega c two is just one over r one c. Okay.

**[0:09:10]** And so, alternatively, we can write that h of omega is equal to one plus j omega over omega c one over one plus j omega over omega c two. Okay. Where we have defined omega c one and omega c two as shown here. Okay. So that's the first part of it, to calculate the transfer function.

**[0:09:43]** Then the second part of the problem is to construct the Bode plots, alright, for the magnitude and the phase. So to do that, we're going to need the numerical values of these... Of the zero and pole frequencies. So omega c one, where we have the zero, is... It's one over the quantity r one plus r two times c.

**[0:10:10]** So it's one over... And then r one is one k, and r two is four k times c, which is 10 to the minus six. Okay. So one k plus four k is five k. K is 10 to the third, and so we have five times 10 to the third times 10 to the minus six in the denominator.

**[0:10:34]** So that's one fifth times 10 to the plus three. So one over five times 10 to the minus three which is one fifth times 10 to the plus three. So this is one fifth times 10 to the third, which is 200. Alright. And that's in radians per second.

**[0:10:53]** Then omega c two is equal to one over r one c. So one over one k, that's r one, times 10 to the minus six. Alright. That's one microfarad. So that is a thousand radians per second.

**[0:11:14]** Okay. And so that means that we can write h of omega as one plus j omega over omega c one, which is 200, over one plus j omega over omega c two, which is 1,000. Okay. So this is in terms of, producing the Bode plot, this is a slightly easier way, to look at the transfer function. Looking at this form for the transfer function, we can see that the magnitude of the transfer function at zero frequency is just one.

**[0:12:00]** Alright? Which means that on the dB scale, this is 20 times the log of one, which is zero dB. Okay? And then add very high frequency. As the frequency goes to infinity, then what we have here...

**[0:12:22]** Alright. If we look at, say, this form, of h of omega here, right, it is the numerator is going to be dominated by this term, the denominator by this term over here. And so the limit of this as omega goes to infinity is just r one plus r two over r one. Okay. So this is equal to 20 on the dB scale.

**[0:12:49]** It's 20 times the log of r one plus r two over r one. So that's 20 times the log of five. Alright. Because r one is one k, r two is four k, which is 13.98 dB. We'll call that 14 dB.

**[0:13:13]** Okay? Then the phase at zero. Alright. Looking at this form here for h of omega, we can see that's clearly zero degrees. And then the phase at a very high frequency, frequency approaching infinity where, these second omega dependent terms dominate, you can see that the phase there is going to be zero as well.

**[0:13:41]** Right? But that does not necessarily mean that the phase at every point in between is zero as well as we will see. Okay? So the phase can vary between zero frequency and very high frequency. Okay.

**[0:13:56]** So let's take this information now and generate the Bode plots. Okay. So we'll look first at the Bode magnitude plot. Okay. And we'll draw the frequency axis here.

**[0:14:18]** Alright? We have a a zero at omega c one, which is 200, and a pole at omega c two, which is 1,000. Okay. So, our critical frequencies here, right, we have... We'll say 100 here, 1,010 to the fourth.

**[0:14:49]** Okay? Then 200, say, maybe here, 20 here, and then 2,000 here. Okay. And then we know that as m... As as the frequency goes to infinity, then the magnitude is 14 dB.

**[0:15:16]** So say this is... If this is 20, 14 would be maybe here. Okay. And let's see. The key frequencies here are 201,000.

**[0:15:37]** Okay. So, we saw up here that at low frequencies, which for our purposes will be less than 200, then, the magnitude is zero dB. Right? So zero dB is where we put the axis. And so the low frequency part of the Bode plot is like this.

**[0:16:03]** Then, between 200 and a thousand, right, the denominator is going to go as one, and the numerator is going to go as omega. So we're gonna have a slope of 20 dB per decade, plus 20 dB per decade. So that's gonna take us up to 14. K. So 20 dB per decade.

**[0:16:31]** And then at high frequency, meaning above a thousand, then we're gonna have the high frequency limit. So it'll just stay at 14 dB. Okay. So like this. K.

**[0:16:51]** And we'll draw this so it's clear that these are aligned. Okay. So that is the Bode magnitude plot. Now we wanna construct the Bode frequency plot. Sorry.

**[0:17:15]** Not the frequency plot. The phase plot. So phi of omega. It's a function of omega. Right?

**[0:17:23]** The horizontal axis in both cases is the frequency. So we have, say, 20 here, 100 here, 200 here, thousand here, 2,000, and then 10 to the fourth. Okay. And we'll say this is zero degrees, This is 90 degrees. This is minus 90 degrees.

**[0:17:53]** K. And we will mark these various different frequencies here. Okay. So, we have a zero at 200, frequency of 200. So that means that low frequencies, meaning, point one times 200 or 20 and below, then the phase will be zero.

**[0:18:34]** Right? Because the one term here will be dominant. And then at high frequency, say, 10 times 200, that is 2,000 and above, then this second term in the numerator will dominate and the phase will be 90 degrees. So we go from a phase of... We'll draw this in blue.

**[0:18:51]** So at 20, we have a phase of zero. Then at 2,000, we have a phase of 90 degrees. And at 200, it's halfway. It's 45 degrees. Okay.

**[0:19:11]** So, that's the contribution to the phase from the zero in the numerator of the transfer function. Then for the pole, alright, we have a pole at a thousand radians per second. So at very low frequencies, meaning a tenth of this or a 100 and below, the phase is, zero, and it contributes zero to the phase of the transfer function. At very high frequencies, say, 10 times a thousand or 10,000 and above, the phase in the denominator is 90 degrees, meaning that the phase contribution to h of omega is minus 90 degrees. Okay.

**[0:19:53]** So we go from phase of zero at a 100 to minus 90 at 10 to the fourth, and it's minus 45 degrees at 1,000. K. So we have a contribution to the phase from the pole at omega equal to thousand that looks something like this other blue dash line that I just drew. And now we can combine these to get the complete phase plot. Alright?

**[0:20:30]** Noting that at very low frequency and at very high frequency, the phase should be zero, right, as we concluded up here. Okay. So that means a very low frequency. Say, than 20, omega less than 20, phase is zero. Okay.

**[0:20:49]** Then starting at 20, right, we go up like this. The slope here is 45 degrees per decade. Then from 100 to 2,000, right, we have 45 degrees per decade up like this and 45 degrees per decade down like this. So those cancel each other out, and we have just a constant phase like this. Okay?

**[0:21:30]** And then from 2000 to '10 to the fourth, we have minus 45 degrees per decade. So that'll spring us down like this. And then from 10 to the fourth and above, the phase is zero again. Okay. So, that is the, Bode phase plot.

**[0:21:53]** Okay. So now we see right here both the Bode magnitude plot and the Bode phase plot. Okay? And we can confirm by looking at the magnitude plot that indeed this is acting as a highpass filter. Right?

**[0:22:12]** Because we have, a larger transfer function by 14 dB at high frequencies than at low frequencies. K. So that takes us to part c of this problem, which is asking, what kind of a filter is this? Alright. So this is a highpass filter.

**[0:22:34]** And then it's also asking what is the maximum gain of this? Right? And the maximum gain is basically the value of the magnitude at high frequency, which, we calculated up here. On the dB scale, it is 14 dB or as, just a conventional, linear gain. Right?

**[0:22:59]** It's r one plus r two over r one, which is five. Alright? So the maximum gain, right, is on the dB scale, we can cut... We can say that it's 14 dB. Right?

**[0:23:21]** Or on a linear scale, it's r one plus r two over r one, which is five. Okay. And so so that is the answer, to this. Okay? And if we look at this problem, alright, it was actually...

**[0:23:44]** The analysis was quite simple. Right? It was basically just analyzing this as a simple op amp circuit. Right? So if we think about what were some of the key points here.

**[0:24:03]** Right? The analysis was, fairly straightforward. Op amp circuit analysis. Okay. And then, once we had the transfer function, we were able to construct the Bode plots in the usual way, which was shown here.

**[0:24:38]** And, also, there are, several examples of this in, one of the earlier, problems. It was Ulaby 9.19. Alright? And so, right, the Bode plots were generated, right, in the usual way. And from the Bode plots, we could conclude that this was a highpass filter.

**[0:25:23]** And, we could basically read from the Bode plot that the maximum gain of 14 dB or as a conventional linear gain, five, r one plus r two over r one. Okay. Now let's go back and look at the circuit and think about whether these results actually make sense if we just think about the circuit a little bit. Alright? So if we're a very low frequency, then this capacitor is going to behave like an open circuit.

**[0:26:05]** Alright? So there'll be no current flowing along this branch. There's also no current flowing along this branch going to the op amp inverting input. Therefore, the current along this branch here has to be zero as well, and the voltage across r two has to be zero. So the output voltage has to be equal to whatever the voltage is over here, and that voltage is v sub s.

**[0:26:28]** Right? Since the, input voltages of the op amp have to be equal to each other. So at low frequencies, we should get v o is equal to v s, which in terms of the transfer function, that means that the transfer function should be one. Alright? And so, on the Bode plot, that should correspond to zero dB.

**[0:26:51]** And if we look at the Bode plot, you can see, in fact, that's what we have over here. Alright? And so, you know, after going through all the formalism of calculating the transfer function and so forth, we can go back and check to see if, does that result make, sort of intuitive sense. Right? And so the...

**[0:27:12]** At low frequency, it certainly does. How about at high frequencies? At very high frequencies, this capacitor behaves basically like a short circuit. And so this circuit here now just looks like a conventional inverting op amp amplifier circuit. Alright?

**[0:27:35]** And... Or non inverting op amp amplifier circuit. Right? Since the input voltage is connected to the non inverting input. Right?

**[0:27:44]** So it's just a conventional... At high frequencies, it's just a conventional non inverting op amp amplifier circuit. And we know that that circuit has a gain of r one plus r two over r one. Okay. And in fact...

**[0:28:06]** Alright. If we look at the transfer function here, we can see that that is indeed the limiting mathematical form of the transfer function as omega becomes very large. And when we calculated the magnitude of the transfer function numerically, we got that, it was five on a linear scale or 14 on the dB scale, and we see that in the Bode plot as well. Okay. So, the third point that we will make here is that, the results for h of omega and the Bode plot, particularly for the magnitude, make intuitive sense.

**[0:29:09]** In terms of the low frequency and high frequency limiting behavior of the circuit. Okay. And, this idea of sort of after you get some result, going back and thinking about, and testing to see whether, it makes reasonable intuitive sense, whether it has the correct behavior as you go to certain simplifying limits is actually quite useful and important in kind of validating or checking that your result actually makes sense. Okay? If you get a result that predicts obviously incorrect behavior in one of these simplifying limits, then you know that it's probably a good idea to go back and check either of what you did in that analysis or what your intuitive understanding of what the circuit should be doing is or perhaps both.

**[0:30:22]** Okay. So that is everything for this example, and I will now stop the recording.
