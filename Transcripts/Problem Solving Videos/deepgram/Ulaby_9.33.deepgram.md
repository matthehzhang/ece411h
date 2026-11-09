# Ulaby 9.33 video

Deepgram general-nova-3 2025-07-31.0, request 01a1b039-1427-7351-b650-9453722175ec, audio 17.6 min.

**[0:00:03]** Okay. So this is Ulaby problem 9.33, and this is an example... Oops. Okay. And this is an example of a calculation of a transfer function.

**[0:00:25]** Okay. And also, construction of Bode plots for an RLC, what will turn out to be a lowpass filter circuit. Okay. So the circuit that we wanna analyze is the one shown here. Okay.

**[0:00:46]** And the resistor r has a value of a 100 ohms. The inductance is point one millihenries, and the capacitance is one microfarad. So we wanna calculate the voltage transfer function, generate the Bode plots, which for this example here, we'll do in the linear approximation and determine the cutoff frequency. Okay. So let's go ahead and, as usual, redraw the circuit.

**[0:01:20]** K. So we have an inductor, capacitor, and a resistor. K. So the circuit looks like this. The input voltage...

**[0:01:44]** Oops. I wanna... I have this as a phasor. The input voltage is at the left hand terminals, and the output voltage is at the right hand terminals. Okay?

**[0:01:58]** And we have an inductance l, a capacitance c, and a resistance r. Okay? And what we wanna do here is to calculate the transfer... The voltage transfer function, right, which is the output voltage over the input voltage. Alright?

**[0:02:21]** And then I... We want to construct the Bode plots for resistance of a 100 ohms, inductance of point one millihenries, and a capacitance of one microfarad. And then, we wanna calculate, the cutoff frequency and the Bode plot slope. That is the magnitude slope, for high frequencies. Alright.

**[0:03:00]** So much greater than, the cutoff frequency. Okay. So, that's the problem that we wanna solve. And so for the first part, alright, we wanna calculate this output voltage over here, and we can do that, simply by applying KCL at this upper node here. Right?

**[0:03:22]** So we'll take the voltage down here to be zero, then the voltage at this upper node is actually just, v naught or v out. And so we wanna apply KCL at that node. Okay? And so if we do that, what we have is that for the current going out to the left through the inductor, then that current is v o over v I over the impedance of the inductor, which is j omega l. Then the current flowing down through the capacitor is v o over the impedance of the capacitor, which is one over j omega c.

**[0:04:09]** And then the current flowing down this way through the resistor is just v o over r, and that's equal to zero. Right? The sum of those three currents, has to be equal to zero. So from here, we just take, this equation, and we group together the terms that are proportional to, v o. And then we can move this term here that's proportional to VI to the right hand side, and then we just solve for VO over VI.

**[0:04:42]** So, for the terms proportional to VO, we have coefficients one over j omega l, that's from this term here, plus j omega c, it's from this term here, plus one over r, it's from this term here. All of these are multiplying v o, and then that's equal to one over j omega l times v I, which we have moved to the right hand side. Alright? Now we can take this equation and we can multiply it by j omega l. Okay?

**[0:05:23]** And so then on the left hand side, j omega l times this first term gives us one. Then j omega l times this third term here gives us j omega l over r. And then j omega l times the second term here gives us minus omega squared l c. Alright? Because j squared gives us minus one, all this times v o.

**[0:05:50]** And then on the right hand side, we just have v I because multiplying by j omega l cancels this factor out. Right? And so now it's very easy for us to calculate the transfer function h. Alright. This is v o over v I.

**[0:06:09]** And so this is just going to be one over one plus j omega l over r minus omega squared l c. Alright? Or if we write this in a form that makes it a little bit easier for us to determine the cutoff frequency, alright, then we can write it as one over one plus j omega l over r. And then, the standard form is that this is now j omega over omega c, the quantity squared. Alright?

**[0:06:54]** And comparing this expression here to this expression here, we can see that omega c is just one over root l c. Alright? So, this is the transfer function that we were asked, to calculate. Alright? Now for the second part of the problem, what we're asked to do is to, construct the Bode plots.

**[0:07:24]** Right? So, we have that omega c, is equal to one over root LC. So that's one over the square root of l is, point one millihenries. So that's 10 to the minus four. And then c is one microfarad.

**[0:07:46]** So that's 10 to the minus six all under the square root. Okay. So we have one over the square root of 10 to the minus 10. That's one over 10 to the minus five or just 10 to the five, and that is in radians per second. Okay.

**[0:08:06]** We can also compute the value of the transfer function at that cutoff frequency. Alright? So that is just going to be... Right. If we look at this expression over here, alright, we have one one over one plus and then j omega l over, r, right, is j and then, it's times omega, right, which is 10 to the fifth.

**[0:08:46]** And then l over r, l is point one millihenries. That's 10 to the minus four. And then r is 100 ohms. So it's 10 to the minus four over 10 to the two. That's 10 to the minus six.

**[0:08:59]** Let me write that five a little better here. Right? 10 to the five. Alright. And then we have this term over here.

**[0:09:11]** Omega is equal to omega c. Right? So this is just, j squared which is minus one. Okay. And so this one and this minus one cancel each other out.

**[0:09:22]** And so what we get is one over point one times j or 10 over j. Alright? I... And so that means that the magnitude of the transfer function at omega c is equal to 20 times the log of 10. Alright?

**[0:09:49]** Which is just 20 dB. Okay. We can also see from the form that we have for h of omega that the magnitude of the transfer function at zero frequency. Right? So setting omega equal to zero here, we can see that h of omega is just equal to zero.

**[0:10:12]** So the magnitude of h of omega on the dB scale is 20 times... Sorry. The the transfer function is just one. Alright? So it's 20 times the log of one, which is zero dB.

**[0:10:29]** Okay. So we get this, because h at zero is equal to one. Okay. So then, with this information, we can go ahead and draw the Bode magnitude plot. Okay.

**[0:10:49]** So this is the magnitude of the transfer function in dB. Alright? So we'll take this to be zero dB, take this to be 20 dB, and then the cutoff frequency is 10 to the fifth. Okay. So this is omega.

**[0:11:08]** And, we know that at zero frequency and for frequencies much less than the cutoff frequency, generally, the magnitude is in dB. It's zero because h is very close to one. So that's gonna be like this. K. So I'm plotting this in green.

**[0:11:35]** Alright? Then, we calculated up here, alright, that the magnitude of the transfer function on the dB scale, at the cutoff frequency is 20 dB. So that's gonna be up here. K. So this is gonna look something like this.

**[0:11:55]** And then, when we go to high frequencies, alright, where omega is much greater than omega c, then this quadratic term in the denominator is going to dominate. And the transfer function in terms of its magnitude is just going to go as one over omega squared. So that is going to give us a slope of minus 40 dB per decade. Right? So it's gonna look, say, something like this where this slope is minus 40 dB per decade.

**[0:12:33]** Okay. So that is the, magnitude, Bode plot. Then for the phase... Okay, we know that the phase at zero frequency... Right?

**[0:12:52]** At zero frequency, the transfer function is just one, and the phase of that is zero. So the phase at zero frequency is zero degrees. At the cutoff frequency, okay, we saw here, right, that h, the transfer function, is just 10 over j. The phase of 10 over j is minus 90 degrees because the phase of j is 90 degrees and it's in the denominator. Alright?

**[0:13:25]** So, the phase at omega c is minus 90 degrees. And the phase at very high frequency as we go to infinity, right, is, right, at very high frequency, this term in the denominator is going to dominate. So we have basically minus omega squared, in the denominator. The phase of that is minus 180 degrees. Alright.

**[0:13:56]** It's minus one eighty minus... Rather than plus one eighty, alright. We know that'll have to be the case because at omega c, the phase is 90 degrees, not minus 90 degrees. Okay. So with that information, we can go ahead and construct the Bode phase plot.

**[0:14:16]** Okay. And so let's say this is 10 to the four, This is 10 to the five. This is 10 to the six. Alright. This is zero degrees and then, say, minus 90 degrees and minus a 180 degrees.

**[0:14:34]** Right? And we'll draw the, the Bode plot curve itself in green. Right? So at low frequencies, that is below 10 to the fourth. Right?

**[0:14:43]** 10 to the fourth is, the cutoff frequency, 10 to the fifth divided by 10. So we're in the low frequency limit. Phase is zero. Right? At, omega c, the phase is minus 90.

**[0:14:56]** And then at 10 to the sixth at very high frequency. So 10 times omega c or higher. So 10 to the six or higher, the phase is going to be a 180 degrees. Alright. Like this.

**[0:15:11]** Or minus a 180 degrees. Okay. And then we will have or we assume, that the transition is linear like this. So this is the Bode phase plot. Okay.

**[0:15:31]** And then finally, right, what we're asked is to calculate the Bode plot slope for omega much greater than omega c. Right? And we actually did that already up here. Right? It's minus 40 dB per decade, and that's basically because at high frequencies, the transfer function h goes as one over omega squared.

**[0:16:01]** Okay. So as noted in part b, right, slope of the magnitude plot, right, at high frequency. That is for omega much greater than the cutoff frequency. Alright. It's minus 40 dB per decade.

**[0:16:26]** Okay. And we were able to see this by noting that at high frequencies, the transfer function basically goes as one over minus omega squared LC. It's the omega squared part of the denominator that matters here. Right? This is what we have for omega much greater than omega c.

**[0:16:53]** And I... So what would happens is that a 10 x change, for example, in omega, right, it changes h of omega by 10 to the minus two. It divides it by a 100, right, times. And, two orders of magnitude decrease is minus 40 dB. K.

**[0:17:22]** So that's how we get minus 40 dB per decade. Okay. So that's it for, this example here. And so I will stop the recording.
