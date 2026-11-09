# 2026-09-23-make-up-phasor-analysis-and-ac-power

Deepgram general-nova-3 2025-07-31.0, request 01a1b00f-cf15-71a3-ae20-5104904c3bac, audio 73.1 min.

**[0:00:03]** Okay. Let's go ahead and get started. So this is the recording, that takes the place of the class that we would have had on, Wednesday, September 23. Okay. So what we did at the end of our light regular...

**[0:00:19]** Last regular class meeting was we talked about phasors and specifically about phasor diagrams, which were a way of essentially, more easily representing and visualizing the phase relationships among, different voltages and currents, in a circuit. So, this idea of looking at, phase shifts of signals at different components, then also, it showed us that, it was possible even using something quite simple, such as, a series RLC circuit that we were able to get signals at a variety of phases relative to, say, the input signal. Okay? And so that suggests that using a circuit to achieve a particular phase shift is something that, you know, is certainly an achievable and could be a useful functionality for circuits. Okay.

**[0:01:19]** So what we wanna do today is start off by talking about phase shift circuits. Okay. And the reading for this is in Ulaby et al, and it is section seven dash eight. Okay. And a phase shift circuit is basically...

**[0:01:48]** It's exactly what it sounds like. It is a circuit where, the goal is to be able to get some output signal, say, a voltage that has some well defined and controllable or engineerable phase shift relative to, an input signal. Okay? Now, before we look at how this can be done, it's worth, thinking a little bit about why this might be a useful thing to do. Okay?

**[0:02:17]** And it turns out that, having a circuit that will produce a particular phase shift is actually something that is extremely useful, for example, in communications, signals contexts. Okay. So it turns out that if we're looking at, communication systems... So in communication systems, right, one of the ways that information can be encoded is that if you have a carrier signal. So that is a signal that is at some particular frequency.

**[0:02:58]** Right? So a sinusoidal signal. If you then think about how can information be encoded in that signal. If we just have a a pure sinusoidal signal with a constant amplitude and phase, that actually doesn't carry any significant amount of information. You have to modulate something about that signal in order to carry that information.

**[0:03:21]** So one way that you can imagine doing it is to modulate the the amplitude as a function of time. Another way that you can imagine doing it is to modulate the phase. Now modulating the amplitude might seem like the more intuitive way of doing it, and perhaps it is the more intuitive way of doing it. But if you're modulating the amplitude, then, there are actually a lot of things that can, influence the amplitude of the signal. You know, you can get small variations due to variety of extraneous, influences, and so that can be very susceptible to noise.

**[0:04:00]** And, also, it takes power to, say, increase the amplitude of a signal. Okay? So there are a number of reasons that that might not be the optimal way to do it. Right? Another way that you could do it is to modulate the phase of a signal.

**[0:04:18]** And if you have a constant amplitude but you modulate the phase, you... You're not changing the power. And it turns out that there are very good ways using circuits to both shift the phase of a signal and also to detect a phase shift very sensitively. So phase modulation is actually very useful way to encode information in a carrier signal in a communication system. Okay.

**[0:04:48]** So one way, okay, to encode information, okay, is to modulate the phase of a carrier signal, okay, that has some angular frequency omega. Okay. And the carrier signal, right, with nonzero angular frequency, you know, right, it's it's often very important and useful to have that carrier rather than just, say, sending a DC signal. Because if you are, say, sending a signal wirelessly, okay, or optically, then you inherently have to have something that is a wave. And that means that it has to have a nonzero frequency.

**[0:05:52]** Right? And then... So that will be the carrier frequency of the carrier signal. Okay. So to see how this works, let's imagine that we have some data stream.

**[0:06:04]** Right? So, it's digital data. So it goes between zero and one. And let's imagine that, Okay. We have, right, basically, a stream of bits, alright, that maybe looks something like this.

**[0:06:29]** Right? So it'd be zero one zero one one zero and so forth. And this is a function of time. Okay. So so this is the digital information, the digital signal that we want to encode.

**[0:06:44]** And then we have some carrier signal. Okay? So then, the carrier signal... Alright. Let's sort of extend these boundaries down farther so we can keep track of them.

**[0:07:14]** Okay. So let's imagine the carrier signal. Right? It looks something like this. Oops.

**[0:07:34]** Okay. My intent here is to draw a signal that has a fixed frequency. Okay. Although my artistic skills here are not the greatest. Okay.

**[0:07:47]** So so this is the carrier signal, and it is at some fixed frequency fixed angular frequency omega. Right? And, also, it has an unvarying phase. Alright? Then what we wanna do is use this data stream over here to modulate the phase of the carrier.

**[0:08:14]** Right? So we might say, okay. When the data stream reads zero, then the phase of the carrier will be, just its original phase. Right? The phase is unchanged.

**[0:08:25]** Whereas if, the data, signal is one, then, let's say, the phase, of the carrier signal will be, shifted by a 180 degrees. So it'll just become the negative of itself. Okay. So then if that is our phase shifting scheme, right, we can look at what the modulated carrier signal looks like. Okay.

**[0:08:57]** So, originally... Right? When the data stream is, read zero, the phase is the same. Alright? But now over here, in this region, the...

**[0:09:13]** Or in this interval, the data stream reads one. So we wanna shift the phase of this signal by a 180 degrees. Alright? So, alright, say, making it the, the negative. Okay.

**[0:09:30]** And so if we do that, alright, then what happens is that, we get something like this. Okay? And then here, when it goes back to zero, right, then we have, the original data stream or the the original carrier signal. Alright. So it looks like this.

**[0:10:01]** And then... Alright. So over here, we go back to zero, and so it goes like this. Alright? Let me draw this a little bit better here.

**[0:10:22]** Okay. And then over here, alright, the data stream goes to one, and so we get shifted by a 180 degrees again. Alright? So we go alright. Say...

**[0:10:43]** Well, yeah, that's not a very good drawing there. Let me try to draw that a little bit better. Okay. So Okay. So something like this.

**[0:11:12]** Right? And then it goes back to zero again. Yeah. Yeah. For some reason, this keeps disappearing.

**[0:11:24]** Okay. So so that's the... Basically, the idea of how one might be... Modulate the phase of a carrier signal to carry information. Alright?

**[0:11:36]** My poor artistic skills on notes here, not notwithstanding. And so this scheme for using phase shifts to encode information, right, this is known as it's called phase shift key. Okay. Or a PSK. Alright.

**[0:12:05]** And, right, for the basic idea here, then we can see that in order to implement this, we need to have a circuit that allows us to shift the phase of a current or a voltage. Okay? So to implement, phase shift keying or PSK, right, then we need a circuit that shifts the phase. Okay, of a current or voltage. Okay.

**[0:12:53]** And, so what that means then is that... Alright. If we represent our phase shift circuit here as sort of a a box, whose structure... Circuit structure is yet to be determined, Right. So this is our phase shift circuit.

**[0:13:17]** What we want is to be able to have some input to the phase shift circuit. Alright. We'll call that v n of t. And let's imagine that that is... We'll call it an amp...

**[0:13:34]** We'll have an amplitude of v one times the cosine of omega t. And then what we want from the phase shift circuit is for it to give us some output voltage, v out of t, that is some amplitude v two times the cosine of omega t plus phi. Right? So phi here is the phase shift. And, ideally, what we wanna be able to do is to design this circuit here such that it will give us a particular value of the phase shift.

**[0:14:17]** Okay. So let's see how, this can be done. We'll look at an example here. Okay. And, the example, will be of what we call a cascaded phase shift circuit.

**[0:14:40]** Okay. And what we mean by cascaded here is that we will have subcircuits within the full circuit, such that each sub circuit will give us a phase shift of a certain amount. And then if we want to build up a bigger phase shift, then the idea is to take, the output of one, sub circuit and use it as the input to, what we call a second stage of the circuit so that you get, an additional phase shift. And then you can keep using the output of one stage as the input to the next stage. And as you build these up, then you can gradually build up larger and larger phase shifts.

**[0:15:28]** Okay? So what we will do here is we will look first at, sort of an individual stage. That is an individual sub circuit of the full circuit that gives us some phase shift, and then we'll see how those units can be concatenated. Right? The output of one being used as the input of another so that you can build up a larger phase shift.

**[0:15:53]** Okay. So the first step in this is just to look at what the phase shift would be from a simple RC circuit. Okay. So the circuit that we will look at here is one where we have some input voltage, and we'll take that to ham... Have amplitude v in, and then it'll be times the cosine of omega t.

**[0:16:30]** Alright. So that's in the cosine form already. And then we'll have a capacitor and a resistor. Okay. So we have this.

**[0:16:54]** This is our capacitor with capacitance c, resistor with resistance r, and we want to look at the voltage across the capacitor and the voltage across the resistor. Right? There will be a current I flowing here. Right? And, we wanna see or we wanna get a sense of what kinds of phase shifts we can get if we take our output terminals to be across the capacitor and also what kind of phase shifts that we can get if we take our output terminals to be across the resistor.

**[0:17:30]** Okay? So if we look at this circuit, then, we can see that since this is basically a simple loop, then we can get the current. Now working in the phasor domain, we can get the current as a phasor just by applying KVL around this loop. Okay. So using phasors, we do that.

**[0:17:51]** We can see that the voltage across the capacitor plus the voltage across the inductor should be equal to the voltage associated with the voltage source. So we have one over j omega c plus r times the current I. Alright. When we multiply this out, right, the one over j omega c times I, right, that's the impedance of the capacitor times the current. That'll give us the voltage as a favor...

**[0:18:16]** As a phasor across the capacitor, then r times I will give us the voltage as a phasor across the resistor. Okay? And the sum of those two voltages has to be equal to the voltage associated with the voltage source v in as a phasor. Okay. So that means that if we just solve for the current phasor, we get v in as a phasor divided by r plus one over j omega c.

**[0:18:51]** Alright? So that is the current. And then to get the voltage across the capacitor, we multiply that current by the impedance of the capacitor, one over j omega c. To get the voltage across the resistor, we multiply by the impedance of the resistor, which is just r. Okay?

**[0:19:11]** So for the capacitor, we have v sub c as a phasor is one over j omega c times the current I. Right? And then... Alright. So that's equal to...

**[0:19:25]** If we take one over j omega c and multiply it by I over here, we can see that we get v n over one, right, from one over j omega c times j omega c plus j omega RC from the resistive, term over here. So we get v n over one plus j omega RC. Okay. Now here, what we will do is we will multiply this by the complex conjugate of the denominator so that in the denominator, we will get a real quantity, the square of the magnitude of this denominator here. And then we'll have that complex conjugate in the numerator that will make it very easy to figure out what the range of possible phases is going to be.

**[0:20:21]** So we're gonna multiply by one minus j omega r c over one minus j omega r c, okay, which we know we're we're always allowed to do. We're just multiplying by one. Alright? And if we do that, then what we get is one minus j omega RC over one plus omega r c, the quantity squared times v n. Okay.

**[0:20:52]** I... And it's very easy to see here now looking at this, factor over here what the range of possible phases is, for VC over v n. Right? And then this will tell us what the range of possible phase shifts is... Will will be for the voltage across the capacitor relative to the voltage input.

**[0:21:15]** Okay. And then, right, we can do the analogous thing for the voltage across the resistor. That is going to be the resistance r times the phasor I. And so that, right, if we multiply this by r over here, we get r over r plus one over j omega c times b n. This, alright, we can multiply by j omega c over j omega c.

**[0:21:53]** Alright? Basically, to get rid of, the one over j omega c in the denominator here. Right? If we do that, we get j omega r c over one plus j omega r c, alright, times b n. Okay.

**[0:22:15]** Then from here, we can do the same thing that we did up here, alright, which is to multiply this by the complex conjugate of the denominator, one minus j omega r c over one minus j omega r c. Alright? And if we carry out that multiplication, then you can see that we get, what we get in the numerator is omega RC, the quantity squared. Right? That's from the j omega RC times minus j omega RC, right, plus j omega RC.

**[0:22:58]** That's from this one over here times j omega RC. And then in the denominator, we get one plus omega r c, the quantity squared, all this times v n. Okay. So this is what we have for v c over here. This is what we have for v r over here.

**[0:23:19]** Alright? Now if we take these two results and we think about, say, for the voltage across the capacitor, what is the range of phase shift angles that we can get for VC relative to VN. That is what is the range of possible phase angles for this factor over here? One minus j omega RC over one plus the quantity omega RC squared. Right?

**[0:23:49]** And it's very easy to see that as a complex number, this is going to have to be in the fourth quadrant of the of the complex plane. Right? Because the real part is positive. The imaginary part is negative. Okay.

**[0:24:06]** So we see that the range of possible phase angles of this quantity here, and therefore, the range of possible phase shifts that we can get for the output being the voltage across the capacitor will be from zero to minus 90 degrees. Right? That's the range of angles in the fourth quadrant of the complex plane. Alright? So relative to the input voltage, then the voltage across the capacitor, right, has a phase angle that ranges between minus 90 degrees and zero degrees.

**[0:24:53]** We'll call phi sub c the the phase shift if the output is taken across the capacitor. Alright? Now if we take the output to be the volts across the resistor, then we're looking at this factor over here and what its range of phase angles is going to be. And here, we can see that this factor has to be in the first quadrant. Right?

**[0:25:20]** Because it has positive real part and positive imaginary part. So that means the range of phase angles of this has to be between zero and plus 90 degrees. Okay. So the voltage p r, right, is phasor. Right?

**[0:25:40]** This has phase angle relative to v n that is between zero and ninety degrees. Okay. And so what we see is that depending on, where we take the output to be, that is where we put the output terminals, then we can get phase shift angles, from minus 90 degrees to 90 degrees. Alright? I...

**[0:26:13]** Right. So what we see then is that this particular RC circuit, right, depending on the values of the circuit parameters, right, it shifts the phase of an output voltage. You can shift it to either positive or negative values. Right? Or using terminology that is often employed for phase shifts, we can have the phase shift either lead the original signal that corresponds to a phase being greater than zero degrees, or we say that it can lag the original signal.

**[0:27:09]** So that means the phase shift is less than zero degrees. Right? So it can shift the phase of the output to either lead or lag that... Of the input voltage. Okay.

**[0:27:31]** And for the RC circuit, the range of phase shift angles is from minus 90 degrees to plus 90 degrees. Okay. So so that functionality we can get even just from a very simple RC circuit. Alright? But one of the limitations here is that we can only get phase shifts between minus 90 degrees and plus 90 degrees.

**[0:27:56]** Alright? So there may be circumstances where, we would like to get, a phase shift that is outside that range. Right? Say we wanted to... Say, if we want a phase shift of maybe a 180 degrees or a 120 degrees.

**[0:28:09]** Okay? So then to do that, the... This simple RC circuit is not sufficient. We need something more. Alright?

**[0:28:18]** And, what we will look at next is a scheme where we take basic units, which are just the RC circuit that we just looked at, and we concatenate them. That is we take the output of one circuit structure like that and use it as the input for another circuit structure that's also the RC circuit. And then what'll happen is that we'll get some phase shift from that first subunit, and then we'll get an additional phase shift from the next subunit. And if we string these together, then we can get progressively larger phase shifts. Okay?

**[0:28:59]** And so that idea of stringing these circuits together and kind of getting the composition of the functionalities or not exactly, but in some sense, the composition of those functionalities that is successively larger phase shifts in this case, that's called cascading these circuit stages. So we will now look at this idea of the cascaded phase shifting circuit. Okay. And for this... Okay.

**[0:29:42]** The basic idea... Qualitatively, the idea or conceptually. Alright. The idea is that we have multiple stages. Okay.

**[0:29:51]** Each of which has some basic functionality. So let's say this is phase shifter one. Right? Then it will have some input, the NFT, and it'll produce some output. And we will call this stage one.

**[0:30:22]** What we then wanna do is to take that output and use it as the input to a second stage, which is now another phase shifter. Okay. It'll produce its output, and we'll call this stage two. Alright? In the simplest cases, each stage is identical, but they actually are not required to be identical.

**[0:30:56]** So you can have, different, circuit structures at each stage depending on, what is the eventual functionality that you would like to achieve. Okay? And then you just keep doing this until you reach the end. Alright. So we will call that phase shifter n.

**[0:31:25]** Okay. And that will give us our final output voltage, and this is going to be now stage n. Okay. And the specific con... So this is a very general, concept here of stringing these functional units together, And, we will look at this now specifically in the case of constructing a cascaded phase shifting circuit that will allow us to get phase shifts that are outside the range of just from minus 90 degrees to plus 90 degrees.

**[0:32:07]** Okay. So if we want to get phase shifts, we want this to be, say, greater than 90 degrees or less than minus 90 degrees, right, then what we can do is we'll see is that we can cascade, okay, multiple phase shifting circuits. Okay. So let's look at now a specific instance of this. Okay.

**[0:32:57]** So we'll have an input we'll call d sub s of t. Okay. And we're gonna take that input signal, and it's going to go to... Alright. Just an RC circuit here.

**[0:33:26]** Okay. Like this. Okay. So this is the capacitance. This is the resistance.

**[0:33:34]** Alright? And this here is going to be... We'll call this stage one of this cascaded phase shifting circuit. Alright? And then we will take the output of this, which is the voltage across the, resistor, and we will use it as the input to another stage that looks just like this first stage over here.

**[0:33:59]** Alright. So we are again going to have a capacitor. Okay. Capacitance c, resistance r. For simplicity, we will take the second stage to look just like the first stage.

**[0:34:19]** So this is now stage two. Okay. And then we will have one more stage of this. K. Like this, capacitance, resistance, and this will be our output, v out of t.

**[0:34:50]** Okay. And so what we're gonna do here is we're going to take b sub s of t to be, some amplitude capital b sub s times the cosine of omega t. We will take omega, our angular frequency to be 10 to the third radians per second, pass it in c to be one microfarad resistance r to be one kilohm. Okay. And, we wanna think about the voltages at each of these nodes here.

**[0:35:37]** This is v two. This is v one. Okay? And for each of these, at the end of each stage, there will be some phase shift that we get relative to vis a vis. Right?

**[0:35:53]** So, right, at the output, I'd say the phase is shifted by some phase phi out. Okay? And then, say, after the second stage, so the voltage v two over here, then the phase of that voltage relative to Versus, it's gonna be shifted by some phase angle phi two. Okay. And so what we wanna do here is to solve for, the phase shift, after the second stage, in this whole structure.

**[0:36:39]** And then what is the final, phase shift of v out relative to v s? Okay. So this is what, we wanna do. And so to do that, what we need to do is to solve for, v two and v out, and we will do this using phases. Okay?

**[0:37:01]** Now if we look at this circuit, then we can see that... Right. One way that we can proceed, which is, really the most straightforward way to proceed, is, to use node analysis to get the voltage v two as a phasor. Okay. Then from that, we'll be able to get the phase shift phi two.

**[0:37:26]** And then once we have v two, then we can just use voltage division to get v out. And then correspondingly, the phase phi out. Alright. So that's how we're going to solve this problem here. Okay.

**[0:37:42]** So let's use... We use node analysis. Okay. And so in node analysis, right, what we wanna do is we take our unknown variables to be v one and v two, right, the voltages at the extraordinary nodes, and then we apply KCL at each of those nodes. Alright?

**[0:38:12]** So when we apply KCL, say, at v one, right, we're gonna take, the sum of the outgoing currents as phasors, to be zero. So at the node v one, then we have the current going out this way to the left. Alright. So that's going to be the phasor v one minus the voltage source, as a phasor v s divided by the impedance of the capacitor. Right?

**[0:38:44]** Then, the current going down this way through the resistor is going to be v one over the resistance r. And then the current going to the right through this capacitor over here is going to be v one minus v two over the impedance of the capacitor. And the sum of all these currents has to be zero by KCL, and the impedance of the capacitor here is, as usual, one over j omega c. So that is one of our KCL equations. Then we get second KCL equation by applying KCL at this node over here, v two.

**[0:39:38]** Alright? So for this node, the current going out to the left is going to be v two minus v one over z sub c. So we have v two minus v one over z sub c. Alright? Then we have the current flowing down through this resistor, which is just v two over r.

**[0:40:06]** And then we have the current flowing out to the right over here, and that is going to be v two over, the impedance of the capacitor plus the impedance of the resistor. So that is going to be b two over z c plus r. And those have to all add up to zero. Okay. So now we have...

**[0:40:35]** Right. In the usual way, applying node analysis, we have our two unknown voltages, v one and v two, which are now phasors, and we have two linear equations for those two unknowns. And so that's a system that, we know that we should be able to solve. Okay. So if we take, this first equation up here and just group our unknown coefficients, then for v one, we're going to have one over r, that's this term, plus two over z sub c.

**[0:41:14]** Right? That's this term and this term. Right? That times v one. And then for v two, from this over...

**[0:41:25]** Term over here, we have minus one over z c times v two. And then the last term is this one over here, which if we move it to the right hand side, is one over z c times v sub s. Alright? So that's from the first KCL equation that is at the node v one. And then from the second KCL equation down here, okay, then what we get is, excuse me, minus one over z c times v one.

**[0:42:03]** Right? That's this term over here. And then for v two, we have one over r, this term, plus one over z c, that's this term, plus one over z c plus r, that's this term over here. Right? That is times v two, and this whole thing is going to be equal to zero.

**[0:42:30]** Okay. So now we have, two equations for two unknowns. Our two unknowns are v one and v two. What we wanna solve for is v two. Okay?

**[0:42:43]** So, you can do that any way that you would like. We will do it using Cramer's rule, okay, because that allows us easily to solve for v two without, having to solve for v one. Okay. So let's solve for v two now. Alright.

**[0:43:00]** You can do it however you would like. We'll do it by Kramer's rule. Okay. And so by Cramer's rule v two, it's going to be in the numerator. What we do is we take the, column vector of of constants, one over z c v s and zero, and we use it to replace the coefficients of v two over here, and then we take the determinant of the resulting matrix of of coefficients.

**[0:43:33]** So if we do that, then we get, it is one over z c squared times v sub s. And then in the denominator, we have the matrix of coefficients or we have the determinant of the matrix of coefficients. So that is going to be one over r plus two over z c times one over r plus one over z c plus one over z c plus r. Okay. And then we have minus one over z c square.

**[0:44:19]** Okay. So that's what we have for v two. And then, once we have v two... K. If we look at our original circuit up here, right, once we have the voltage v two, then since the capacitor and the resistor here are in series, right, since this is, just a stub over here, then v out, we can get by voltage division.

**[0:44:50]** Right? V out is going to be, r over, r plus z c times v two, right, by voltage division. Okay. So v out then is going to be equal to r over z c plus r times v two. We know this by voltage division.

**[0:45:20]** Okay. So now let's go ahead and, try to calculate these putting numbers in from, what we specified up here. Okay. So we come back down here. Right?

**[0:45:46]** So from v two, the expression that we have over here, right, what we're going to do is we're first going to replace z sub c by one over j omega c. Okay. So v two is equal to... In the numerator, we have one over z c, the quantity squared. So one over z c is just j omega c.

**[0:46:10]** When we square it, we get minus the quantity omega c squared. Right? We'll write the Versus, at the end. And then in the denominator, right, what we have is we have one over r plus... And then two over z c is j times two omega c, and then we have one over r.

**[0:46:37]** Right? So that what we just wrote down is this term here. Then from this term over here, we have one over r plus j omega c plus... And then one over z c plus r is j omega c over one plus j omega r c. Okay?

**[0:46:57]** And then finally, for minus one over z c squared, that is going to give us plus omega c, the quantity squared. All of this times v sub s. Okay. So now what we wanna do is to multiply by r squared over r squared. Alright?

**[0:47:26]** And that will allow us to, among other things, get rid of the one over r's in here. Okay. So we carry out that multiplication, then we get... In the numerator, we get minus omega r c quantity squared. And then in the denominator, if we distribute out the r square...

**[0:47:57]** So one factor of r goes here and one factor of r goes here, we get one plus j times two omega RC times one plus j omega RC plus j omega RC over one plus j omega RC Mhmm. Plus omega RC, the quantity squared. Okay. So now, alright, you see that, throughout this expression, the various non numerical parameters, right, they always appear in this combination omega times r times c. Okay.

**[0:48:48]** So what is that equal to numerically? Omega, remember, is 10 to the third radians per second. R is one kilo ohm, and c, the capacitance, is one microfarad. Right? So that's 10 to the third times 10 to the third times 10 to the minus six, and that's one.

**[0:49:10]** So omega RC is just equal to one. Okay? So that makes our numerical calculations much simpler. Okay. So we get in the numerator here now.

**[0:49:26]** Okay. We get... It's just gonna be minus one. Okay. And then in the denominator, right, from over here, we get one plus j times two times one plus...

**[0:49:45]** And this is j. Alright. That's from the j omega RC over here. And then this over here is j over one plus j. Okay.

**[0:49:57]** And then, over here, we just get plus one. Okay. Now here, right, if we look at this j over one plus j in the denominator, right, we have j over one plus j. Okay. So...

**[0:50:19]** Alright. Simplify that. Let's multiply that by the complex conjugate of the denominator. So one minus j or... Over itself.

**[0:50:26]** One minus j over one minus j. Okay. And so then, what we get here is j times one minus j divided by... And then one plus j times one minus j is just two. Okay?

**[0:50:44]** And so when we multiply this out, we have one half times... And then j times j times minus j over here is just one, and then j times one over here is j. So one half times one plus j. Alright. So that's what we have for this j over one plus j over here.

**[0:51:12]** Right? So now if we substitute that in, we get minus one over one plus j times two times one plus j. And then for j over one plus j, we write, plus one half plus j times one half. Okay. And then plus one.

**[0:51:38]** Okay. And then simplifying that a little bit more, we have minus one in the numerator times one plus j times two. And then, for this term over here, we have one plus one half, which is three halves, plus j plus j times one half, which is j times three halves. So we have three halves times the quantity one plus j, alright, plus one. Okay.

**[0:52:09]** And so now just continuing to simplify this, we still get minus one in the numerator. And then, we have in the denominator, we have three halves. That's this three halves over here. And when we multiply one plus j times two by one plus j, we're going to get one plus j times three minus two. Okay?

**[0:52:40]** And then plus one. Alright? Oops. Okay. And then now we simplify this a little bit more where we have minus one.

**[0:52:55]** And then in the denominator, we have one minus two, that's negative one times three halves, that's negative three halves, plus one, that's negative one half. So we have negative one half. And then for the imaginary part, we have three halves times j times three, so plus j times nine halves. Alright? And then here, now, right, you should be, very familiar with this process here.

**[0:53:27]** We multiply by the complex conjugate of, the denominator over itself. So we have minus one half minus j times nine halves over minus one half minus j times nine halves. Okay. And, right, if we multiply that out, we can see that... Right.

**[0:53:57]** The minus one here and the minus signs in here will cancel each other out. So in the numerator, we just get one half plus j times nine halves. And then in the denominator, right, we have this denominator multiplied by its complex conjugate. So that product is gonna be the real part squared plus the imaginary part squared. So we get one quarter plus 81 over four.

**[0:54:32]** Alright? And then we're going to get, right? It'll be four or or it's it's 82 over four in the denominator. So that's two over 41. Right?

**[0:54:45]** And then times one half plus j times nine halves. Alright. So that is going to be one over 41 times one plus j times nine. Alright? And this is equal to v two over v s.

**[0:55:10]** Alright? So what we did... Yeah. So back here, right, this was v two over Versus Right? We divided both sides here by, by Versus Okay.

**[0:55:27]** Okay. So we have one over 41 times the quantity one plus j times nine. Right? And, so we can figure out the phase of that very easily. That's the phase phi two.

**[0:55:41]** Right? It's the phase of v two relative to v s. Okay. So that is going to be the inverse tangent of the imaginary part nine divided by the real part one. Alright?

**[0:55:57]** And if you calculate that, by plugging it into your calculator, you should get that this is 83.7 degrees. Okay. So that is the phase that we have after two stages of these phase shifting circuits. Right? So over here.

**[0:56:24]** Okay. So that is not quite over 90 degrees. Alright? So what we wanna do now is to figure out what v out is. Right?

**[0:56:36]** So what the voltage will be after this third stage of, our cascaded phase shifting circuit. Okay? And for v out, we can get that just by voltage division. Okay. So then v out as a phasor.

**[0:57:08]** Right? That's going to be equal to r over z c plus r times v two. Alright. So that's r over one over j omega c plus r times v two. Alright.

**[0:57:31]** Then this, alright, we can multiply by j omega c over j omega c. And if we do that, we get j omega RC over one plus j omega RC times v two. K. And remember, omega RC was equal to one. Okay.

**[0:58:07]** So if we make that substitution, then in the numerator, we're just gonna have j. And in the denominator, we're gonna have one plus j times v two. Alright? And then remember we saw up here, right, the j over one plus j is equal to one half times the quantity one plus j. Okay.

**[0:58:43]** So if we make that substitution, we have one half times one plus j times v two. Okay. And, we saw just a few minutes ago that v two was equal to one over 41 times the quantity one plus j nine times v s. Right? So we take this.

**[0:59:09]** We divide both sides of this equation by v s, right, then what we get is that v out over v s is equal to one half times one plus j v two over v s. Alright? So that's one half times one plus j, and then v two over v s from up here, right, is one over 41 times quantity one plus j nine. So we have times one over 41 times one plus j times nine. Alright?

**[0:59:55]** And if we multiply, this out, right, we're gonna get one over 41 times one half. And then one plus j times one plus j nine is gonna be one plus j times 10 minus nine. Alright? And then... So we're gonna have one over 41, and then one minus nine, that's minus eight, and then times one half is gonna be minus four.

**[1:00:35]** And then we have the one half times j times 10, so that is plus j times five. Okay. So this now is v out over v s. Okay. Now if you were to plug this into your...

**[1:01:01]** If you were to take this and say, alright. Well, the phase angle of this quantity here then should just be the inverse tangent of five over minus four. Alright? Then, that will actually give you the incorrect answer. Okay?

**[1:01:24]** And the reason is that... Alright. We can see it if we plot things out in the two dimensional complex plane like this. Alright? So we have...

**[1:01:43]** If we neglect the one over 41 over here. Alright. Well, we're... We'll keep it. Right?

**[1:01:49]** So the imaginary part of... Or the real part of this is minus four over 41. Right? So say that's over here, minus four over 41. The imaginary part is five over 41.

**[1:02:05]** So here, say five over 41. Alright. So v out over v s is a complex number here on, the two dimensional complex plane. Right? Like this.

**[1:02:22]** Okay. But if you were to take this here and say, alright. Well, the the phasing... So the phase angle that we want is this. Alright?

**[1:02:40]** And you can see that it clearly is greater than 90 degrees. Alright? But if you were to take this expression here and say, oh, well, the phase angle of this is just the inverse tangent of five over minus four. If you were to plug that into your calculator and calculate it, then the angle that you will actually get is a negative phase angle. It is this angle here.

**[1:03:12]** Right? This is minus the inverse tangent of five over four or, equivalently, the inverse tangent of five over minus four. Okay? And the reason is that... Right.

**[1:03:26]** When we define a function, it's sort of nice for it to be single valued. And your and your calculator, right, it wants the function to be single... That it can calculate to be single valued. And so in order to make the inverse tangent single valued, right, you can see here from this little, plot that, right, there's clearly more than one angle that has, an inverse tangent of, or that is the inverse tangent of five over minus four. Right?

**[1:03:59]** And so it's the question of which one, should you pick. The calculator picks whatever angle is in the range between minus 90 degrees and plus 90 degrees. And in calculus, that is how the inverse tangent function is typically defined. Right? It's...

**[1:04:16]** As a value, right, its range is between minus 90 degrees and 90 degrees. Okay. But in this case, that's the incorrect answer. Right? What we want actually is that plus a 180 degrees, that gives us the correct phase angle phi out.

**[1:04:39]** Right? So in this case, what we want is for phi out to be... We have to add a 180 degrees because of this issue that I was just describing to what we have formally, which is the inverse tangent of... Or minus the inverse tangent of five over four. And if you calculate that, it's a 128.7 degrees.

**[1:05:04]** Okay. And from this diagram here, right, that looks, about right. So this is the actual correct result. We can also verify it over here, alright, by noticing that... Alright.

**[1:05:26]** If we look at this, okay, one half times one plus j, that clearly has a phase angle of 45 degrees. Alright. The one over 49... One over 41 times the quantity one plus j times nine. Alright.

**[1:05:45]** We just calculated up here. That has that has a phase angle of 83.7 degrees. Okay. And so if we put these together, then... Alright.

**[1:06:04]** And the product of these two is, the actual... It should... It's it's the same as this. Right? So it should have the same phase angle.

**[1:06:11]** And if we add these two phase angles together, then clearly, get 128.7 degrees. Okay. So that checks out. Alright. And so this is an issue that one has to be, somewhat careful of in calculating the phases of, complex numbers in the way that we are going to be using them.

**[1:06:37]** Here, you have to be cognizant of, you know, which is the correct value, of the phase angle given that the inverse tangent function is multivalued. Okay? And kind of drawing out a little picture like we have over here or visualizing it... This picture in your head is, you know, usually a very good way of determining, which is actually the correct phase angle. Is it directly the inverse tangent, or do you have to, shift it by a 180 degrees?

**[1:07:15]** In this case, what we saw was that you had to shift it by a 180 degrees. Okay. Now the last thing... Right? So what we see here then is that now we actually have gotten a phase shift angle of greater than 90 degrees.

**[1:07:33]** Alright? And we did that by using this cascaded phase shifter. Alright? So we see now that the cascaded phase shifter, it gives us phase angle phi f that is greater than 90 degrees, which, you could not get from just a single stage. We didn't quite get there with the values that we selected using, two stages, but three stages didn't get us there.

**[1:08:04]** Okay? A trade off here, though, is that as we add more and more stages, if we're only using passive components, right, resistors, capacitors, and inductors, then, what will inevitably happen is that the amplitude of the voltage will decrease. And we can see that by comparing the magnitude of v two over v s, right, which is... It's basically, the, the amplitude, the relative amplitude that we get after two stages to the magnitude of v out over v s, which is the relative, magnitude that we get after the third stage. Alright.

**[1:08:56]** So the trade off here is that the amplitude, okay, of the voltage, it decreases as more stages are added. Okay. I... And so, for example, if we look at the magnitude of v two over the magnitude of v s, alright, what we saw up here, right, is that this is one over 41 times the quantity one plus j times nine. So the magnitude of this is the square root of one over 41 squared plus nine over 41 squared.

**[1:09:54]** Okay. So this is gonna be square root of one over 41 squared plus nine over 41 squared. Right? If you calculate that, then you get around point two two. Okay.

**[1:10:09]** We can compare that to the magnitude of the m over the magnitude of the s. Right? That's the relative amplitude that we get after the third stage. Alright, we saw up here, right, v out over v s is this. So the magnitude of this is the square root of four over 41 squared plus five over 41 squared.

**[1:10:43]** Okay. So we've had the square root of four over 41 squared plus five over 41 squared. And if you calculate this, you get that it's, point one six. Okay. So, the magnitude of the the amplitude of the voltage signal is decreasing as we're adding more stages.

**[1:11:06]** Alright. So in order to rectify that, and we will see this later on in the course when we talked about, when we talked about active, filter circuits and the like, then the way that you can, rectify this is you can introduce, components into your circuit that will give you gain. Alright? And, the way that we will do this is to use op amps. Right?

**[1:11:33]** That's basically the the component that we have at our disposal right now that will give us gain. Right? So this problem of decreasing voltage amplitude, this can be addressed by using an op amp for amplification. Okay. So that is everything that we wanted to say about, phase shift circuits.

**[1:12:11]** So that's what we'll finish up with for this recording. And what we will do in our next class meeting is we will start talking about, how we do calculations of power, using phasers. And there, it's a little bit more complicated because we're going to be taking complex quantities, say voltage and current, and multiplying them by each other. And so we have to be a little bit more careful about how we go from that complex quantity to the power of which ultimately is a real quantity. Okay.

**[1:12:48]** So we'll start discussing that in class on Monday. Okay. So that is it for the for the recording, and I will now stop the recording.
