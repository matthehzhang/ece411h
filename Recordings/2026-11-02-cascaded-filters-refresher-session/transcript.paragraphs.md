# 2026-00-00-cascaded-filters

Deepgram general-nova-3 2025-07-31.0, request 01a1b032-6402-7871-bd67-0aea3d3a362c, audio 67.1 min.

**[0:00:03]** Okay. So in this recording, we are going to go through a couple examples of cascaded filter circuits. One example will be an analysis, and the other example will be a design problem. Okay. So the first example that we're going to look at here is that of cascaded bandpass filter.

**[0:00:38]** Okay. And this is going to be an analysis of a circuit. Alright? And so what we're going to do is we're going to take the active lowpass filter and the active highpass filter, the circuits that we discussed in class, and we're going to cascade them. That is we're gonna take the output of one and use it as the input for the other.

**[0:01:02]** And what we will see is that we can use this approach with appropriate selection of the corner frequencies for each in order to make a bandpass filter. Alright? So the circuit that we're going to look at is the following. We have our input voltage here, v sub s, that's connected through a one k resistor, okay, to our first op amp. Alright?

**[0:01:38]** So this is op amp number one. The noninverting input is connected to ground, and then we have the output. We'll call that voltage v one. And then our feedback connection, okay, is going to be a 10 k resistor in parallel with a capacitor, nine nanofarads. Okay.

**[0:02:06]** Then that's connected to the output. So this, you may recall, is our lowpass filter. Okay? And so that's going to let low frequencies through, and it'll cut off high frequencies. Yep.

**[0:02:25]** K. And what we wanna do then is to connect that, take the output of that subcircuit, and use it as the input for a highpass filter, which I remember has the following configuration. Okay. So we have our op amp number two. The noninverting input is again connected to ground.

**[0:02:54]** Right? And we'll have... This time, it'll be a 12 k resistor and, again, a nine nanofarad capacitor. And then we will have our final output coming from this second op amp. So this will be our output voltage v out.

**[0:03:16]** Okay? And we're going to have, for our feedback connection, a 96 kilo ohm resistor. Alright? So this is our highpass filter sub circuit. Okay?

**[0:03:38]** And so what we want is to have these together to show that this will work as a bandpass filter. Okay? So in order to analyze this circuit, we're going to use the same approach that we used for multiple op amp circuits earlier in the semester. Alright? That is we start off by analyzing the behavior of the circuit, the op amp that is closest to the input.

**[0:04:03]** So we're gonna analyze the behavior of this lowpass filter circuit first. Once we use that... Once we do that to get v one, then we will take that as the input for the second cert... Subcircuit over here with op amp number two. So let's look at the part of the circuit with op amp number one.

**[0:04:27]** Right? That is the lowpass filter circuit. Okay. So for this circuit, remember from what we discussed in class that the corner frequency, right, the... Or the frequency rather of the...

**[0:04:48]** We're going to have a poll here, and the frequency of the poll is going to be the RC time... One over other RC time constant of this resistor combined with this capacitor. Right? The 10 kilohm resistor combined with the nine nanofarad capacitor. So we'll call that omega naught one, right, for the first op amp, and that is going to be one over 10 kiloohms times nine nanofarads.

**[0:05:28]** And this will end up being... Right. 10 k is 10 to the fourth. Nine nanofarads is nine times 10 to the minus nine farads. So we have, in the denominator, nine times 10 to the minus five.

**[0:05:42]** So that becomes one ninth times 10 to the fifth radians per second, which is about 11.1 times 10 to the third radians per second. Okay. Now what we will also do is we will calculate the equivalent impedance of this... The equivalent feedback impedance over here. So that is going to be impedance z.

**[0:06:21]** We'll call it z f one. Okay? And z f one, right, the feedback impedance associated with the first op amp that we have over here. Okay? We have the resistor and the capacitor in parallel.

**[0:06:40]** So the equivalent impedance is just going to be the product of those two impedances divided by the sum, right, since they're in parallel. So it's going to be 10 kilo ohms times one over j omega times nine nanofarads divided by 10 kiloohms plus one over j times omega times nine nanofarads. Alright? And if we take this and we multiply, I'll write it out explicitly here. We'll multiply this by j omega times nine nanofarads divided by j omega times nine nanofarads.

**[0:07:24]** Okay? Then what we get in the numerator is just 10 kiloohms. And then in the denominator, we get one plus j omega times 10 kiloohms times nine nanofarads. That becomes 10 kilo ohms over one plus j omega over omega zero one. Right?

**[0:07:51]** Because omega zero one is one over 10 k times nine nanofarads, and so that's one over this factor over here. Alright? So that's how we get this feedback impedance for op amp number one. Okay. And then once we have that, alright, we know from our analysis of the lowpass active filter from before or just remembering, right, this is basically like...

**[0:08:20]** It has the same topology as an inverting amplifier. So if this were just a resistor, then we know... And we called it, say, RF, and we called this RS, then we know that the output voltage, which in this case is v one, is just going to be minus RF over RS times Versus So here, where now we have a feedback impedance, then the output voltage of that op amp v one is going to be simply minus the feedback impedance z f one that we just calculated divided by the input resistance, which is going to be one kilo ohm, okay, times the s. And if we take this and divide it by one kilo ohm, then we just get 10. Right?

**[0:09:14]** We have the minus sign, and we have 10 in the numerator, and then we have one plus j omega over omega zero one in the denominator times v s. Okay. So this is what we have for v one. Okay? And that is going to be our input voltage, okay, for this second subcircuit over here, which is the active highpass filter circuit.

**[0:09:45]** Alright? And so now let's analyze the behavior of that part of the circuit with v one as its input. Okay. So now we're looking at op amp number two, which behaves as a highpass filter. Okay?

**[0:10:06]** And the frequency associated with that, if you remember from our analysis in class, right, the key frequency here, the frequency of both a zero and a pole that we have... Or, actually, the frequency of the pole that we have in this case is going to be one over the RC time constant associated with the 12 k resistor and the nine nanofarad capacitor. Right? So that frequency is going to be one over 12 kilohms times nine nanofarads. Okay.

**[0:10:46]** So that is one over... 12 times nine is a 108. Right? And then we have kilo times nano in the denominator. That's 10 to the three times 10 to the minus nine.

**[0:10:58]** That's 10 to the minus six in the denominator. That becomes 10 to the six radians per second, or this is approximately 9.26 times 10 to the three radians per second. Alright? That's the frequency of the pole in the highpass filter. Alright?

**[0:11:23]** And, again, alright, this has basically the topology of the inverting op amp amplifier. Right? So the output voltage v m is going to be just minus 96 k over the impedance of this resistor and capacitor in series times the input voltage v one. Okay. So v out, in this case, is going to be minus 96 kilohms divided by...

**[0:11:58]** And then that series combination is 12 kilohms plus one over j omega times nine nanofarads. Right? And that's going to be times the input voltage v one. Okay? So now here, what we're going to do is in order to simplify that fraction in the denominator, we're gonna multiply by j omega times nine nanofarads over j omega times nine nanofarads.

**[0:12:29]** Right? And then we are going to multiply and divide by 12 kilohms. Okay. And we'll see why that's a useful thing to do in a minute. Alright?

**[0:12:45]** If we do that, then we're gonna have this minus sign over here. Right? That's carrying over the minus sign from the line above. And then in the numerator, alright, we're going to have j times omega, alright, times nine nanofarads times 12 kilohms. Right?

**[0:13:06]** So times nine nanofarads, this is times, times 12 kiloohms. Right? And then in the denominator, we're going to have one plus j omega times, again, nine nanofarads times 12 kiloohms. Alright? And then...

**[0:13:33]** Right. So now we've used up in the numerator this j omega nine nanofarads and 12 k. We have this 96 k left over. So then we're gonna have 96 kiloohms. And then in the denominator, right, we multiply through by this j omega nine nanofarads with this expression over here to get this.

**[0:13:56]** We have this 12 k left over. So we have 12 k in the denominator. Right? Now over here, alright, this is just eight. Right?

**[0:14:09]** 96 over 12 is eight. And then remember, omega zero two is equal to one over 12 kiloohms times nine nanofarads. And so over here in the numerator, this nine nanofarads times 12 kiloohms is one over omega zero two. And down here, this nine nanofarad times 12 kilo ohms is also one over omega zero two. So what we get finally is...

**[0:14:37]** And this is all times v one. Okay? So what we get then is we have eight. Alright. That's this eight over here times j omega over omega zero two divided by one plus j omega over omega zero two times v one.

**[0:15:04]** Okay? But v one is given by this expression up here. Right? Minus 10 over one plus j omega over omega zero one times v s. So...

**[0:15:18]** And then we have a minus sign over here. Alright? That's carrying over this minus sign from up here. So now if we take that expression above, alright, this expression here, and plug it in down here for v one, then this negative sign and this negative sign will cancel out. Right?

**[0:15:40]** And what we get is... Alright. We have eight j omega over omega zero two divided by one plus j omega over omega zero two times 10 over one plus j omega over omega zero one times the input voltage v s. Alright? And then, finally, that gives us the transfer function h of omega, right, which is v out over v s.

**[0:16:22]** Okay? And that, right, since this is v out over here, right, then the transfer function is just the product of these two factors here in the parentheses. Okay. So that's going to be 80. Right?

**[0:16:37]** That's the eight times 10 over here. Then we have times j omega over omega zero two. Alright? That's the rest of the numerator over here. Then we have one over one plus j omega over omega zero two.

**[0:16:59]** Alright. That's, this denominator over here times one over one plus j omega over omega zero one. Okay. And that's everything. And so what we see here is that we have...

**[0:17:16]** Right. We have a constant. Alright. This term over here, right, we can choose whether to include the omega zero two either here or in the constant. It doesn't really matter, which we do.

**[0:17:29]** This is a pole at the origin. Okay. Then this factor of... Or sorry. This is a zero at the origin.

**[0:17:52]** Okay. And then over here, we have a poll at omega zero two. Alright. Omega zero two, remember, was we worked out the numerical value up here. It was 9.26 times 10 to the minus three radians per second.

**[0:18:11]** Right? So this is 9.26 times 10 to the minus three radians per second. And then this term over here is a pole at omega zero one, right, which we worked out up here is 11.1 times 10 to the third radians per second. Sorry. This is plus three over here.

**[0:18:41]** This is 11.1 times 10 to the third radians per second. Okay. So this is the full transfer function for, this cascaded bandpass filter. And so what we wanna do now is to construct We'll just look at the Bode magnitude plot. Right?

**[0:19:08]** Because that's, the plot that will really show us that this is indeed a bandpass filter. Okay. So we're gonna plot the magnitude. I'll write it explicitly as the magnitude of frequency in dB. Okay?

**[0:19:33]** And then it'll be a function of frequency. Alright? And we have omega zero two, right, as the... As one pole frequency and then omega zero one as the other pole frequency. Right?

**[0:19:53]** These two values here. You can see that, actually, omega zero one is greater than omega zero two. Okay. So now, alright, what we have is the following. Alright?

**[0:20:07]** We're going to... If we look at the behavior of this, for frequencies that are less than omega zero two, okay, then what happens is that we have this constant 80 times j omega over omega zero two times one over... And then this is gonna be in the low frequency limit, so it's one over one. And then this is also gonna be in the low frequency limit, so it's one over one. So this is just going to go as j times omega, right, or omega to the first power.

**[0:20:44]** So we're going to have a slope here of... Mark these frequencies here. K. So we're gonna have a slope here of 20 dB per decade. Okay.

**[0:21:06]** Now between omega zero two and omega zero one, Right? We're gonna have j omega over here. And then here, this term is going to be in the high frequency limit. Right? So it's going to be...

**[0:21:22]** This is going to behave approximately as one over j omega or, actually, one over j omega over omega zero two. This term over here, since we're still below omega zero one, is going to behave in its low frequency limit, so it's just going to be one. So we have j omega over omega zero two over j omega over omega zero two. That's just one, right, times this constant. So that's constant.

**[0:21:49]** It has no dependent on... Dependence on frequency, and it's going to be like this. Okay? It'll be flat. And, in fact, we can see then, right, that the value that we have for this, right, if we wanna now determine where this is, what the numerical value of this is on the magnitude scale, then this term here, right, is j omega over omega zero two, and then we're dividing by j omega over omega zero two because this is in its high frequency limit.

**[0:22:23]** So these two basically cancel that to one. This factor here is one. Alright? So the transfer function, h of omega, is just 80. Alright?

**[0:22:34]** And so on the dB scale, this is going to be 20 times the log of 80, right, which is probably in the high thirties somewhere. Alright? You can calculate it on your calculator if you want. And then finally, if we go to high frequencies, frequency of above omega zero one, we have j omega here in the numerator. This is going to go as j omega in the denominator.

**[0:23:05]** This term over here now is in its high frequency limit. So it's also gonna go as j omega in the denominator. So we're gonna have basically omega over omega squared times some constant. But the key is that we have omega over omega squared or equivalently one over omega. And so that means that the magnitude of the transfer function is going to be decreasing, and the slope is going to be minus 20 dB per decade.

**[0:23:41]** Okay. And so this is what the Bode magnitude plot looks like. And then we can see pretty clearly from here that this is bandpass filter. Alright? So the passband is basically it it extends a little bit beyond from omega zero two to omega zero one.

**[0:24:01]** Alright? And the peak nonresonant gain here, right, this is now m naught, right, is 20 times the log of 80. So a little bit under 40 dB. Right? Because the log of 100 would be two.

**[0:24:22]** Right? Now it... And that would be exactly 40 dB. Okay. So what we see here is that by using the active filter circuit that employs these op amps, then we're able to get a magnitude of the transfer function that is significantly in excess of one or equivalently in excess of zero dB.

**[0:24:47]** Okay. So so that's basically how we analyze this example. And we can see that, right, the way that we went about it was just to recognize that we have this subcircuit over here, right, that is the lowpass active filter circuit that we've seen before. We have this subcircuit over here, which is the highpass active filter circuit that we've seen before. And we can analyze this using the general approach that we use for multiple op amp circuits where we analyze the behaviors of the op amps one by one starting with the op amp that is closest to the input.

**[0:25:31]** Right? That allowed us to get v one in terms of v s, then v one serves as the input voltage to the second op amp. That allows us to get v out in terms of v one, and then, therefore, also in terms of v s. Right? And what we see then is that by putting together the lowpass and the highpass filter, we get this cascaded bandpass filter.

**[0:25:56]** The other thing to notice here is that in order for this to be a bandpass filter, we actually have the pole for the lowpass filter being at a higher frequency than the pole for the lowpass filter over here. Alright. It's slightly higher, and that allows this to be a bandpass filter. Alright? If if we had not switched those, then it would not have behaved in in quite this way.

**[0:26:28]** Alright. So this is the cascaded bandpass filter. That's... This is basically an analysis problem. Right?

**[0:26:35]** We're presented with a circuit, and, basically, we want to figure out its behavior, and then maybe after the fact, understand why it behaves in this way. Okay. The second example that we'll look at here is an example of a band reject, and it's a filter design problem. Okay. So we're going to be given a bunch of conditions, right, that we want the circuit design to satisfy, and then we want to design a circuit that, right, meets those criteria, satisfies those conditions.

**[0:27:21]** Okay. So, right, this is really a different kind of undertaking than analyzing a circuit that you're presented with. Alright? Because we have to understand well enough how to create different functionalities using circuits and then how to put them together to get some more complicated functionality. Alright?

**[0:27:44]** And so what we wanna do here is we want to design a band reject. Alright? Meaning that over a finite range of frequencies, the output is suppressed. Alright? And then at other frequencies, the output is transmitted or amplified.

**[0:28:04]** So we wanna design a band reject active filter with the following. Alright. So that satisfies the following conditions. First, we wanna have an overall voltage gain of minus 50, right, outside stopband. Okay.

**[0:28:41]** The second thing that we want is we wanna be able to specify what the stopband is. Right? So the stopband, we wanna take this to be from 20 kilohertz to 40 kilohertz. Right? So these are now not...

**[0:29:01]** These these are just frequencies. They're not angular frequencies. So to get the angular frequency, we have to multiply these numerical values in hertz by two pi. Right? Then we'll get the angular frequency in radians per second.

**[0:29:14]** So omega one, corresponding to the lower frequency of the stopband, is going to be two pi times 20 kilohertz. So it's 40 pi kiloradians per second, which is numerically 1.26 times 10 to the fifth radians per second. And then omega two, okay, is two pi times 40 kilohertz. So that is 80 pi kiloradians per second. And numerically, that works out to 2.51 times 10 to the fifth radians per second.

**[0:30:01]** K. So that's the second condition that we wanna satisfy. And then the third is that we want the gain roll off, right, that is the slope, right, outside the stopband to be plus or minus 40 dB per decade. Right? So outside stopband.

**[0:30:35]** Okay. So this is the problem that we want to solve here. Alright? So how do we do this? Well, the first step is really to just sort of come up with the overall design.

**[0:30:48]** Right? What are the component pieces that we need in order to achieve all of these functions. Alright? And then once we have determined that, then we can figure out how to design each of the sub circuits and how to put them together. Okay?

**[0:31:07]** So the first step really is to come up with the overall design. Right? And then once we've done that, right, determine the things like the component values. Okay. So so let's think about what we want here.

**[0:31:39]** Alright? So let's... To do that, let's sketch out what the Bode plot should look like. Okay. So we want we want an overall gain of 50.

**[0:32:00]** Okay? So that means that outside the stopband, right, then what we want... In particularly well outside the stopband, what we want is for the transfer function to have... We want the overall voltage gain to be minus 50. So we want the transfer function to have a magnitude of 50 or in dB, it should be 20 times the log of 50.

**[0:32:28]** Alright? So here we have 20 times the log of 50, and then we're going to want transfer function to have a magnitude at that level when we're well outside the stopband. Alright? So this is the frequency. And then, you know, our stopband consisted of frequencies that were kind of in the low 10 to the fifth radians per second.

**[0:32:56]** So maybe here, we'll have 10 to the fourth radians per second. Here, this will be 10 to the fifth. And then omega one maybe is here. And omega two maybe is here. Then this will be 10 to the sixth and so forth.

**[0:33:14]** Okay? And so then what we want, alright, is if we're well outside the stopband, draw this in blue here, we want the magnitude to be like this. And then we define the stopband such that at omega one and omega two, then the magnitude has dropped down to three dB below its value outside the stopband. Okay. So what we actually want is this.

**[0:34:05]** Okay. And we want the slope here to be minus 40 dB per decade, and we want the slope here to be plus 40 dB per decade. Alright? So so this is what we want. Okay?

**[0:34:27]** And if we think about this, then if we just think about frequencies less than omega one, right, the way that we can get this kind of behavior is to use a lowpass filter. Right? So here, alright, we want... And then to get a slope of minus 40 dB per decade, then what we want... You know, one way to do that is to use a two stage lowpass active filter, right, where each stage will give us a slope of minus 20 dB.

**[0:35:01]** Okay? And then together, cascaded, they will give us a slope of minus 40 dB per decade. Right? So here, we want a two stage lowpass active filter. And let's say that its transfer function should be h sub l p of omega.

**[0:35:24]** Alright? And then up here, at higher frequencies, right, the way that we get this kind of behavior, just on the right, is to have a two stage highpass active filter. Okay. It's a highpass filter, right, because, right, we want a large transfer function at high frequencies, and we want it to drop off as we go down in frequency. And then it's two stages because that will give us a slope of 40 dB per decade.

**[0:36:04]** Okay? And so that might correspond to a transfer function we'll call h sub HP for highpass of omega. Okay? So... And then we wanna combine these in some appropriate way and get the overall gain as well.

**[0:36:21]** So we'll talk about how we combine these in a minute, but let's first think about what we want these transfer functions for the lowpass and the highpass filter components to be. Alright? For the lowpass filter alright. Remember we talked about the active first sort of lowpass filter in class, and then we talked about what happens if you cascade them. Right?

**[0:36:50]** And, basically, you just get the product of transfer functions of each individual stage. And so for the lowpass two stage active filter, then the transfer function is going to be one over one plus j omega over some appropriate pole frequency omega sub LP squared. Alright. Squared because it's a SUSH filter. And omega l p, alright, the pole frequency is going to be one over some resistance times a capacitance we'll call c sub l p.

**[0:37:32]** Alright? So that's the transfer function that we wanna get for the lowpass filter. And we basically... From what we talked about in class, we know how to get that. We take the one stage first order active lowpass filter, and we cascade it with another filter just like that, and we're gonna get, basically this.

**[0:37:56]** Okay. Then for the highpass filter, right, it's the same thing. Alright? We're going to take two of the first order highpass active filters that we talked about in class. We're going to cascade them, put one after the other, and the transfer function for that combination will be the transfer function of the first and the second multiplied by each other.

**[0:38:22]** So we're going to get j omega over omega sub h p squared over one plus j omega over omega sub HP squared. Right? And, alright, the pole frequency omega sub HP, in this case, is going to be one over... Yeah. We can take the resistance to be the same.

**[0:38:47]** Right? Because as long as the product of the resistance and the capacitance is the desired quantity, then we can... We... There are many combinations of resistance and capacitance that will give us that. So we can take the resistances in the lowpass subcircuit and the highpass subcircuit.

**[0:39:07]** We take them to be the same, and then we have to choose the capacitances to give us the right frequencies. Right? So part of what we're gonna do here is, basically, for simplicity, we choose the same resistance values for the resistors in the lowpass and the highpass subcircuits. Okay. So so that gets us...

**[0:39:51]** You know, basically, this type of behavior that we see here in the blue curve Bode plot... Bode magnitude plot. Right? Then the other part that we have to do is to get outside the stopband. We wanna get the magnitude of the transfer function to be at the right level, which is magnitude of the gain of 50.

**[0:40:19]** Okay? And for circuits that have these transfer functions over here for the lowpass and the highpass components, then the way that we can combine these, right, we also have to figure out how to get these functionalities together. Right? And we don't wanna take the lowpass subscurve and the highpass subscurve and connect them in series, right, because then they'll each severely attenuate things outside the stopband. We don't really want that.

**[0:40:54]** And, also, we'll have a nonzero slope outside the stopband. We don't want that either. Instead, what we want to do is, really, we want to add this response over here on the left to this response over here on the right and then amplify it to the appropriate level to get a total magnitude of 50 outside the stopband. Okay? That won't be exactly right because when we're out here, then we will have...

**[0:41:28]** You know, this slope is actually continuing down. But, actually, look, it'll be at such a low level, right, by the time we get out here that it doesn't really influence what this looks like. And similarly, this will be at a very low level by the time we get out here, and so it won't have much quantitative influence on what happens here either. Okay. So the way that we combine these and then also bring in, the requisite gain is, that we combine these using, an inverting summing amplifier that has a gain of minus 50.

**[0:42:22]** Okay. And so kind of in terms of basic block units, right, if we have our input voltage signal like this, then we wanna take that and send it in parallel to one subcircuit, which will give us the lowpass filtering behavior. And then also to another subcircuit that will give us the highpass behavior. Alright? We will have output voltages that are, say, v one and v two.

**[0:43:03]** Then we want to take those and use those as the two inputs for an inverting summing amplifier that has a gain equal to minus 50. Okay. And we saw earlier in the semester when we talked about op amp circuits generally. Right? We know how to do this.

**[0:43:37]** And then finally, that will give us the desired output voltage. Right? So this is the general concept of how we want to proceed here. Okay? And so what we need to do next is to figure out how we design each of these individual blocks, and then we can put them all together in the way that I've shown here.

**[0:43:58]** Alright. And so we can take as our next step then to essentially figure out how to design this lowpass filter circuit. Alright? Given that its transfer function is going to look like this over here. Alright?

**[0:44:19]** So that means we wanna determine... We need to determine this resistance r and then the capacitance associated with the lowpass filter circuit. Okay. So the magnitude of this cascaded lowpass filter circuit is what it's gonna be is... Right.

**[0:44:45]** It's the magnitude of this transfer function, right, that we have specified. So it's going to be the magnitude of one over one plus j omega over omega l p squared. Right? The magnitude of this is just one over one plus omega over omega l p squared. Right?

**[0:45:14]** Because if this were to the one power instead of squared, then the magnitude of this whole thing would be one over the square root of this denominator. Alright? And so when we have this squared, then the magnitude is just squared as well. So that's basically how we get this. Okay.

**[0:45:32]** In addition, what we want is that... Alright. So when we are... This is the lowpass filter. So at low frequencies, this has a magnitude of one.

**[0:45:49]** Alright? So at the edges of the stopband, right, omega one and omega two, right, up here, and omega one is going to be the relevant frequency for the lowpass filter, which gives us this behavior, then we want the magnitude to be one over the square root of two. Right? So at the edges of the stopband, right, that is at omega equal to omega one and omega equal to omega two, right, then what we want is that we want the magnitude of the transfer function to be one over the square root of two. Alright?

**[0:46:42]** And so that means that the magnitude of the transfer function for the lowpass subcircuit, we want that when evaluated at omega one. Okay? It's omega one, right, up here because omega one, we saw, is less than omega two. Okay. We want that to be equal to one over the square root of two.

**[0:47:12]** Okay. So that means that... Alright. We want one over one plus omega one over omega l p squared. Alright.

**[0:47:22]** That's the magnitude of the lowpass subcircuit. We want this to be equal to one over the square root of two. And... Alright. So that means that omega one over omega lowpass, the the pole frequency squared, has to be equal to the square root of two minus one.

**[0:47:46]** Right? That's just simple algebra to get that. And if we solve that for the pole frequency of the lowpass filter, then it's going to be omega one over square root of two minus one to the one half power. Right? And so then just working this out numerically, omega one is 1.26 times 10 to the fifth radians per second, and we're dividing that by the square root of two minus one to the one half power.

**[0:48:22]** That ends up being equal to 1.96 times 10 to the fifth radians per second. Okay. And, we want that, to be equal to one over r times, some capacitance. Alright. So now, right, there are not unique choices for r and that capacitance, so we can choose one of them to be anything.

**[0:48:50]** So let's choose the resistance. Right? We're free to choose whatever value we want for that. So let's choose something nice and simple. We'll take it to be one kilo.

**[0:49:00]** Okay? Once we've chosen the resistance, then the capacitance, we're not free to choose. We have to figure out what value the capacitance satisfies this equation here. Right? So then what happens is that the capacitance is one over r times omega l p.

**[0:49:27]** So that is one over r. We chose it to be one kilohm, and omega l p, right, is this value here, 1.96 times 10 to the fifth radians per second. Okay. And if we calculate that out, then we get 5.1 nanofarads. So this is the capacitance that we use in the lowpass filter circuit.

**[0:49:59]** The resistance that we use is one kilo. And the design of each stage of this two stage lowpass filter circuit is the same as that of the first order lowpass circuit... Lowpass filter circuit that we talked about in class, okay, which is that we have a... The key part is we have a resistor in parallel with a capacitor in the feedback connection of that op amp circuit. Okay.

**[0:50:31]** So that's the lowpass part of the circuit. Then we have the highpass part of the circuit. And, again, right, we've chosen the value of the resistance. It's gonna be one kilohm. So, basically, we have to figure out what the capacitance value is.

**[0:50:47]** Right? So we wanna determine the capacitance value for the high pass part of the circuit. So the transfer function, right, magnitude... Right? So it's the magnitude of the highpass filter transfer function.

**[0:51:12]** So from what we specified that transfer function to have to be. Alright? We said it's gonna be a transfer function like this because when we talked about the highpass filter circuit in class, we got something like this. Without the squares, we have two stages that are cascaded, then that gives us the squares. Okay?

**[0:51:33]** So we have the highpass filters. We have the magnitude of that function. So it's the magnitude of j omega over omega highpass squared over one plus, right, j omega over omega highpass quantity squared. Alright. Taking the magnitude of that, and the magnitude of that is in the numerator, it's omega over omega highpass squared.

**[0:52:05]** In the denominator, it's one plus omega over omega highpass squared. Okay. And, again... Alright. What we want...

**[0:52:17]** Right? So we can see that as omega becomes very large, then this magnitude approaches one. Right? Because the numerator goes as omega over omega highpass squared. The denominator goes as omega over omega highpass squared since this one is very small compared to this term for high frequencies, and this works out just to be one overall.

**[0:52:39]** So what we want then is that at omega equal to omega two... Right? So this is the highpass behavior that we want. And so at omega equal to omega two, we want the magnitude of that transfer function to be one over root two. Alright?

**[0:52:59]** So we want the magnitude of the highpass transfer function evaluated at omega two. We want it to be one over the square root of two. Right? So that means that omega two over omega highpass, right, the pole frequency over one plus omega two over omega highpass squared, right, has to be equal to one over the square root of two. Alright?

**[0:53:36]** And, right, if you just do the algebra to solve for omega two over omega omega highpass squared, and this is one over the square root of two minus one. Right? It's very simple to get that. And so we can solve this for the pole frequency omega highpass. Right?

**[0:53:56]** It's equal to square root of two minus one to the one half times omega two, right, or the square root of two minus one to the one half times an omega two. Remember, we worked out up here is 2.51 times 10 to the fifth radians per second. Alright. So this is 2.51 times 10 to the fifth radians per second. And if we multiply that out, we get 1.62 times 10 to the fifth radians per second.

**[0:54:44]** Alright? Now we know that that pole frequency for the highpass filter circuit, right, from what we did in class, is one over r times this capacitance c sub HP. Right? And we chose r to be one kiloohm already, right, which means that the capacitance in the highpass filter circuit is going to be... Right.

**[0:55:15]** It's one over r times omega highpass, the whole... The pole frequency. So that is one over r is 10 to the third ohms. And then omega HP, we just figured out as 1.62 times 10 to the fifth radians per second, and this ends up being one over 1.62 times 10 to the eighth, which is 6.2 nanofarads. So that is the capacitance in the highpass filter circuit.

**[0:55:51]** And remember from the configuration of the first order active highpass filter that we talked about in class, that capacitance goes in series with the voltage source and the resistor that are at the input of that circuit. Okay. So now we've figured out the component values, the resistor and then the two capacitors, capacitance values that go into the lowpass and highpass blocks of this overall circuit. Right? So, basically, we know what this unit looks like and what this unit looks like.

**[0:56:31]** Now we just have to figure out or remind ourselves of how we design the inverting summing amplifiers so that we have a gain of minus 50. K. So then this next step here, right, is to design the inverting summing amplifier, alright, to have a gain of minus 50. Okay. So remember from when we talked about op amps earlier in the semester, right, that the basic design for the inverting summing amplifier is like this.

**[0:57:20]** This is our output voltage. The noninverting input is grounded, and then we have feedback resistor RF. And then we have two inputs, each of which is connected through a resistor to the inverting input of the op amp. Right? So...

**[0:57:52]** And these resistors, we can take to be r in each case. Right? Because we want the gain for each of them to be... Each of the voltage inputs to be the same, and then we can just choose RF as a multiple of r to get the the overall gain factor for those input voltages. So then if we just apply in the usual way, KCL at the inverting input of the op amp, then...

**[0:58:24]** Alright. We know that the voltage at the inverting input is zero. So applying KCL, then the current up through this upper resistor r is minus v one over r. The current through this lower resistor r is minus v two over r, and that the current out this way through r f is minus v out over r f. Right?

**[0:58:52]** That's equal to zero. And so if we solve that for the output voltage, then that's minus r f over r times v one plus v two, alright, where v one and v two are the outputs of the lowpass and highpass active filter blocks. Alright? And so if we take this r, we take it to be the same value as we had for the for the filters, right, namely one kilohm, then in order for this overall gain factor to be minus 50, we want r f to be 50 kilohms. Right?

**[0:59:30]** So for r, it's the one kilo ohm. Right? Then we choose RF is equal to 50 kilo ohms, and that means that the output voltage will be equal to minus 50 times v one plus v two. Okay. And so now we have everything.

**[1:00:02]** Alright? In this overall design here... Alright? And I'll draw this out explicitly in a minute. Right?

**[1:00:11]** We have... We know what these two units should look like including their component values, and we just figured out what the inverting summing amplifier should look like. Oops. Okay. So then the last step is to combine the sub circuits into the final circuit.

**[1:00:43]** Okay. And so what this is going to look like, right, is we have our input voltage, and we wanna send that to our two filter circuits. Right? Each of which is a two stage filter. Right?

**[1:01:07]** So the upper circuit that we'll draw is the lowpass two stage filter circuit. K. So remember for a lowpass active filter, the feedback loop contains a resistor. All these resistors are r. This is c lowpass, alright, connected to the output.

**[1:01:37]** Then we take this output and use it as the input to a second active lowpass filter circuit that is configured exactly as this first one is over here. So we have another resistor r. K. Ground connection to the other input. And then we again have...

**[1:02:15]** Right, our resistor and capacitor in parallel, right, for the feedback connection. And then final... And then that's eventually going to go to the inverting summing amplifier. But before we draw that, let's draw the highpass filter unit. So we have, in that case, a resistor in series with a capacitor.

**[1:02:40]** This resistor is still r. Now the capacitor is the highpass passiveness that we calculated. Those will be inputs to an op amp, and the feedback connection here is just the resistor r. Okay? Then we have...

**[1:03:06]** That is the input to the same thing. Alright. So we're cascading two units of this together. K. So here we have another resistor r.

**[1:03:25]** Okay. And so this is the voltage v one. This is the voltage v two. Alright. So in what we have drawn here so far, Right?

**[1:03:40]** We've gotten... We've drawn these two blocks over here. We've gotten up to v one and v two, and then those are the inputs for the inverting summing amplifier. Right? And that inverting summing amplifier looks like this.

**[1:03:56]** Okay. So we take those two as the inputs to... Right. These are resistors with resistances r. K.

**[1:04:13]** And these are the inputs to one more op amp. Alright. That's the inverting summing amplifier with a feedback resistance RF, alright, that we figured out for r equal to one k, RF is equal to 50 kilo ohms. And that gives us our output voltage. And so that is the whole thing.

**[1:04:47]** Right? So you can see that, actually, this circuit looks like a very complicated circuit. Okay? And it is a fairly complicated circuit, but you can see, hopefully, through what we have discussed here, how you can build up to the circuit by considering just the fundamental blocks from which this is constructed. Right?

**[1:05:09]** So we have the single stage, just the first order lowpass filter up here, and we saw that you could put two of those in series. Right? And that'll give us the second order lowpass filter. Alright? We analyze and class the highpass filter down here.

**[1:05:31]** Alright? The first order active highpass filter. Again, we can cascade these as we saw in a similar example in class and get the second order filter behavior. Then we take the outputs of those two blocks, and we invert and sum them with amplification over here to get the final output. And that's how we get the the final design for this circuit here that will satisfy all these criteria that we specify.

**[1:06:08]** Alright? And, basically, right, you can see how we kind of went through this step by step. First, we figured all out... Well, what are the sort of general blocks, functional blocks that we want to have? Alright?

**[1:06:20]** That got us to this. Alright? And then we figured out the details of what each of these blocks would have to look like building upon what we know circuits with that kind of functionality should look like from what we've done earlier in the semester. Okay? And then, you know, all of that together gets us to, you know, this final...

**[1:06:45]** What actually looks like quite a complicated circuit over here, but you can kind of see now, hopefully, how we can get to this using the basic elements that, that we've talked about thus far. Okay. So that's it for, for these two examples, and I will now stop the recording.
