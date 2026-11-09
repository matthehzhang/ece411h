# 2026-10-28-active-filters-cont

Deepgram general-nova-3 2025-07-31.0, request 01a1b010-8d60-7773-8f3e-459aee18045f, audio 78.8 min.

**[0:00:03]** Okay. Let's go ahead and get started. So, I have started the recording, and as usual, I just have a few announcements. The first one is that there's a change to the office hours schedule today. So I had a meeting that was put on my schedule for this morning, and so instead of having my office hours this morning, I'll have them this afternoon, one to 02:30PM in the usual location, E R 3 Dot 802.

**[0:00:31]** Second announcement is that problem eight, was posted this morning. Okay? And that'll be due on, November 9. That's Monday. So a week from this coming Monday.

**[0:00:44]** And problem set eight, it's mostly about passive and active filter circuits. And so... Except for the the sixth problem on the problem set, which has to do with some of the mathematics associated with transforms. So the first five problems on that problem set will be on material that'll be included on the upcoming exam. Alright?

**[0:01:08]** Third announcement is just a reminder that problem set seven is due at 9AM this coming Monday, November 2. And then finally, a reminder again that we have semester exam two that's coming up. It'll be in person in class, and that'll be on Wednesday, November 11. Okay? And I'll post a, detailed announcement on the exam, that'll talk about, the rules for the exam, which will be basically the same as the rules for the first exam, and also the material for which you'll be responsible on that exam.

**[0:01:44]** So any questions on the announcements? Okay. Any questions from our last class meeting? Okay. If not, then we will pick up from where we left off.

**[0:01:59]** So what we were doing last time, was we were talking about, filter circuits, and we had started to work through this highpass filter circuit that is basically an RLC series circuit with the output voltage taken across the inductor. Right? So we worked out, excuse me, just using, voltage division. We worked out what the transform... Or what the transfer function would be, and then we calculated, its magnitude and phase.

**[0:02:36]** And remember when we talked about the phase, there was a little nuance, to that because, from the nature of the, inverse tangent function, we had to have these two different expressions depending on whether we were below, excuse me, or above the pole frequency. Okay? Because the real part of the denominator of the transfer function changes sign at at the pole frequency, and so we have to be careful about how we calculate the phase. And then what we saw at the very end of our last class meeting was that if we actually sketch out the magnitude as a function of the frequency, what we see is that it can have fairly different behaviors right around the pole frequency omega naught, which is the resonant frequency for the RLC circuit depending on the value of the quality factor. Okay?

**[0:03:37]** So for a high quality factor then, you can have a sharp peak in, the magnitude of the transfer function, although it doesn't have as much effect on the behavior at very low or very high frequencies. And then high quality factor is associated basically with having low loss, so low resistance in the filter. Alright? So, so this is basically what we got to at the end of the last class. Yes?

**[0:04:07]** Why the... Well, is there an intuitive reason as to why a very high resistance would cause low resonance and a very low resistance, high resonance? Yeah. So, so you can think about it. Right?

**[0:04:29]** If you imagine... Alright. This is the circuit that we had. And if you imagine that the resistance is very low, right, say going to zero, then in the limit of zero resistance, all all you have is the capacitor and the inductor. And if the impedance goes to zero, then you sort of get a blowup of the current.

**[0:04:57]** Right? So, you get very high voltage, right, in in that limit, infinitely high voltage. Okay? Because... And there's nothing to disrupt that.

**[0:05:09]** Right? It'll just build up without limit. If you have a low resistance, then, alright, you'll go from sort of the infinite limit to some finite but high value. Alright? And...

**[0:05:26]** Alright. So so that can help you to understand why you have a high value for the transfer function. And then associated with that is that it's it's... The higher it is, it's kind of the narrower the peak is. Right?

**[0:05:39]** And, you know, that's basically because you only can get... You only get that resonant behavior right at the resonant frequency. And if you move a little bit off of it, right, then, you know, once you're off of it a little bit, then the resistance, will start knocking that down. Okay? And you're knocking it down from a very high value, right, it comes down more sharply.

**[0:06:10]** Okay. So... Right. And then if you get to a very high resistance, that buildup of stored energy and therefore voltage in the capacitor and the inductor, it gets knocked down very quickly. Okay.

**[0:06:25]** So you don't get that, that peak in the behavior. Okay. Okay. So Yes. When it's, you know, the the voltage across the inductor is d I d two, a very low resistance.

**[0:06:39]** That current change will be... Oh, as as it's going through its, you know, cycle, that current change will be very high because the the the resistance is low and the current change per time is very high. So the inductive voltage as well. Yeah. Because the current will be very high.

**[0:07:01]** And so, therefore, the IDT, right, it kinda scales up Right. With the current. Right. Yeah. Okay.

**[0:07:06]** Any other care... Questions? Okay. So so this is what the magnitude and phase of the transfer function look like for this highpass filter. What we wanna do starting off today is then to look at what the Bode plots, right, which are kind of the linear approximations, what they look like for this same highpass filter circuit.

**[0:07:33]** So we wanna look now at the Bode plots for the highpass filter. Okay. And so to look at the Bode plots, what we'll do once again is that we will take the transfer function and kind of break it apart into the fundamental factors whose behaviors we know how to plot, and then we'll we'll we'll put those together to get the Bode plot for the complete transfer function. Okay. So if we look at the transfer function that we calculated last time, alright, that's basically this function up here.

**[0:08:14]** Then, we can pretty much see very quickly how this should be, broken up into its constituent factors. Right? We have an omega square... Minus omega squared factor, which is j omega, the quantity squared. Right?

**[0:08:27]** So that's going to be a zero at the origin, and because of the square, that'll be a second order zero at the origin. Then we'll have a constant, which is l times c, and then we have one over this denominator, which is going to be a quadratic pole. Okay. So those are the constituent factors that that we have in the transfer function. So we have our constant factor l times c, then we have j omega the quantity squared.

**[0:08:55]** Right? That becomes minus omega squared. And then we have one over one plus j omega r c minus omega squared l c. Alright? And so we'll call this a one of omega.

**[0:09:14]** We'll call this factor a two of omega, and we'll call this last factor here a three of omega. Okay? And just looking at these different factors here, we can see then that transfer function h of omega, right, it has a second order zero at the origin. That's the factor a two of omega, and it has a quadratic pole at a pole frequency, which from looking at the quadratic term in the denominator, alright, we can see that the pole frequency is one over the square root of l times c, which is equal to the resonant frequency, of the RLC series circuit. Okay.

**[0:10:17]** So so that's kind of the nature of, the transfer function in terms of its fundamental factors. And what we can do now is then to kind of plot these out. Alright? Construct the Bode plots for each of them. And so the first factor that we have is just the constant.

**[0:10:43]** Right? So we're gonna plot the magnitude, and now we're gonna plot that on a dB scale, on the decibel scale as a function of omega. And... Alright. The magnitude, is just a constant.

**[0:10:58]** Okay? So, or, the constant factor is... It's a constant, so its magnitude is also constant. And so it'll just look something like that. And then for the phase, alright, phi of omega, then the phase...

**[0:11:21]** Okay. The constant factor is l times c. So that's gonna be positive, so the phase will be zero. Alright. So it'll be like this.

**[0:11:31]** Okay. So the phase here is zero, in this case. Alright. The second factor over here is j omega, the quantity squared. Okay.

**[0:11:47]** So that is a second order zero at the origin. So that is the factor we've called a two of omega. Okay. And that factor will look something like this. If we look at the magnitude on a dB scale, right, we have, again, since it's a zero at the origin, it doesn't have any inherent, frequency scale, so we'll just call the frequencies one, 10, a 100, and so forth.

**[0:12:23]** And say this will be zero dB. Okay? So that'll be the value of a two, the magnitude of a two at a frequency of one. Alright? And what happens here is that since this factor goes as omega squared, then every time we have an order of magnitude, say it's a factor of 10 increase in the frequency, the magnitude of that factor goes up by 10 squared is...

**[0:12:56]** Which is a 100, which is 40 dB. Okay. So if we have 40 dB up here, then the way this factor will look on the magnitude Bode plot is like this. Right? It'll be a linear function on this scale that increases with frequency at a rate of 40 dB per decade.

**[0:13:26]** Okay. And then for the phase, alright, five omega as a function of omega, then, what'll happen is that, it's minus... It's j omega the quantity squared. So that's minus omega squared. So the phase is just the phase of minus one, which is a 180 degrees.

**[0:13:53]** And it's independent of frequency. So it'll look like that. So any questions so far on how we're sort of building up the constituent, Bode plots to eventually get to the Bode plot for, the full transfer function? Okay. So now we have the last factor, which is this quadratic pole over here.

**[0:14:19]** Alright? So that is a three of omega. Okay. And so for that, right, we're again looking at the magnitude on dB scale as a function of the frequency. And then here, we're going to have the pole frequency which is omega naught.

**[0:14:51]** Okay? Now... And we'll call this line here zero dB. Okay. So now if we look at that factor, then what we can see is that at low frequencies, right, the limiting behavior here is that this factor will go to one because omega going to zero will get rid of these terms over here.

**[0:15:15]** So omega will go to one. So the magnitude is going to be 20 times the log of one, which is zero. Alright? Zero dB. And then the phase, will be, zero degrees.

**[0:15:29]** Alright? When we go to very high frequencies, then what will happen is that this quadratic term over here will dominate. So this is going to go as basically one over minus omega squared LC. Alright? And, what happens there is that for every factor of 10 increase in the frequency, the magnitude of this factor will decrease by a factor of a 100.

**[0:16:03]** Alright? So, that's 40 dB. So we're gonna have a slope on the magnitude plot of minus 40 dB per decade. And the phase, right, it's basically the phase of minus one. So, that could be either plus or minus a 180 degrees.

**[0:16:19]** Okay? So what we have here on the magnitude plot is that at low frequencies, we're going to have the magnitude approximated as one, so that's zero dB. And then at high frequencies, above the pole frequency, then we're going to have this going down, and it'll be at a slope of minus 40 dB per decade. Alright? Because it's gonna go as one over omega squared, basically.

**[0:16:59]** Then for the phase, okay, what'll happen is that... Alright. If we take this line to be zero degrees, right, we're gonna have... This is point one omega naught where omega naught again is the pole frequency. This will be omega naught.

**[0:17:21]** This will be 10 omega naught. Okay. And then we'll mark minus 90 degrees and minus a 180 degrees. Okay? What we said was that at, at low frequencies, which for the phase plot we take to be less than point one omega naught, then the phase will be zero.

**[0:17:48]** So it'll look like this. Then we said that at a very high frequencies, greater than 10 omega naught, we said that, basically, the phase will be the phase of minus one, which could be plus or minus a 180 degrees. To determine which one of those possibilities we should use, we can look at what happens when omega is equal to omega naught. Alright? Omega naught is one over root LC.

**[0:18:18]** So then at that frequency, this last term in the denominator is just going to be minus one. So we'll have one minus one. Those will cancel out. And so this will be... This factor will be equal to one over j omega r c.

**[0:18:32]** Okay? So we have a j in the denominator that has a phase of minus 90 degrees. Okay? So, at omega naught, phase is minus 90 degrees. And then, that means that at very high frequencies, it'll make more sense, right, to take the phase to be minus a 180 degrees.

**[0:19:05]** So it's gonna go like this. Okay. So this is what we have for the Bode plots for that quadratic pull factor. So any questions on this? Okay.

**[0:19:23]** And then the last step is to take these three plots, alright, and basically add them together to get the Bode plot for the entire transfer function. So now we're gonna be looking at the Bode plot for the entire transfer function. And then if we do this for the magnitude first... Okay. This will be our, pole frequency here.

**[0:20:02]** Then if we look at the constituent factors, okay, we have basically constant here. We have a line with an upward slope of 40 dB per decade here. And then if we look first at low frequency, so less than omega naught. Right? This is sloping upward.

**[0:20:23]** This is constant. This is constant. So we are going to have an upward... A rising line. Right?

**[0:20:33]** A line with an upward slope that has a slope of 40 dB per decade. That's where we're gonna have it low frequencies for the magnitude and add the pole frequency omega naught. Okay. If we look at that, well, alright. That's what we'll have at low frequency.

**[0:20:52]** We'll have an upward sloping line. At high frequencies, then we we have still a constant here. We have still an upward sloped line over here. And then from the quadratic pole, we have a downward, line with a slope of minus 40 dB per decade. So the slopes of this factor and this factor will cancel each other out.

**[0:21:17]** Alright? Give... They'll give you a net slope of zero, and then this has a slope of zero. So we're just going to have a a constant Bode plot, for the magnitude. Alright?

**[0:21:30]** So a horizontal line. And the value that we will have for that, if we come back up to the original transfer function here, alright, we can see that, as omega goes to infinity, then what will happen is that the quadratic pole here will go as one over minus omega squared l c. These other two factors here will go as also minus omega squared LC. And, so the whole transfer function, will approach one as omega goes to infinity, and therefore, on the log scale, the magnitude is going to go to zero. It'll be 20 times the log of one, which is zero.

**[0:22:19]** Okay. So we take this to be zero dB here. Then what happens is at high frequencies, right, it's a horizontal line, at zero dB. And then at low frequencies, it is, a rising line, right, with a slope of 40... Oops.

**[0:22:48]** 40 dB per decade. Okay. So that is the Bode magnitude plot for the entire transfer function. Sorry. This is omega.

**[0:23:00]** You're not omega naught. And then for the phase, right, basically, we're just adding up, these, three constituent phases. So zero degrees, a 180 degrees, and this function here. So that's basically going to give us this function here shifted upward by a 180 degrees. So instead of going from zero to minus one eighty, it'll go from 180 degrees to zero.

**[0:23:28]** Okay. So, the phase, Bode plot will look like this. This is the phase. K. This is zero degrees.

**[0:23:42]** Say this is 90 degrees. This is a 180 degrees. This will be point one omega naught, omega naught, and 10 omega naught. Okay. And what the Bode plot will look like is this.

**[0:24:10]** Okay. So any questions on how we constructed the Bode plots for for this transfer function? Okay. And one of the things to notice here is that when we constructed the Bode plots, that is using the linear approximations, right, in the low frequency and high frequency range, then, we didn't get any sort of unusual behavior near the pole frequency or near the resonant, frequency. Right?

**[0:24:42]** This is, the shape of this is independent of the quality factor. Right? Whereas what we saw earlier, right at the very beginning of class today and also in more detail last time was that if you look at the actual transfer function, then you can have quite different behavior right in the vicinity of the pole or resonant frequency depending on what the quality factor of of this circuit is. Alright? And so one of the things that that highlights is that one of the limitations of the linear approximation version of the Bode plots is that it doesn't capture, these types of variations in the behavior near the resonant frequency, but it does capture quite well the behave...

**[0:25:37]** The limiting behaviors at low and high frequencies. Okay? So that's something to, to keep in mind as well. Okay. So any questions to hear?

**[0:25:48]** Yes. In this case, we only have one omega knot. But if there was another, if we if we added in terms of variables like l's and l's, then how would we work with it if there were multiple zeros and holes that were not either just one and omega knot or if it was, like, omega knot for the zero and omega knot for the whole? Oh, yeah. So, so if it were a more complicated circuit, right, that had more of these kinds of factors, in it just from the configuration of the circuit, then, right, the the way that you would get the Bode plot, for that, for example, and and the way that you would calculate the transfer function, you would follow the same sorts of methods that we have used, but, you know, working them out would be more complicated.

**[0:26:43]** What would then happen is that instead of just having, right, a collection of factors like this, you might have an additional factor that, you know, say, maybe was a, you know, something rising at a slope of 20 degrees... 20 dB per decade and then leveling off over here or something like that, you can have additional factors like that. But then sort of combining all of the constituent factors, that make up the, the transfer function and therefore the Bode plots, you would do that in the same way. Right? So if you had, if there were, say, another factor that maybe, you know, kind of went like this, alright, then what would happen is that, right, at at these low frequencies, you would have another kind of 20 dB per decade contribution to the slope.

**[0:27:50]** So this would go up at 60 dB per decade. Alright? Then, I... You know, between... We'll call this omega one.

**[0:27:59]** Okay. So it might look sort of like that. Right? Then in between, right, between omega naught and omega one, right, you have minus 40 dB per decade plus 20 dB per decade. Alright?

**[0:28:17]** So that would be minus 20 dB per decade. So would look like that. Okay. I drew that a little bit too far, but, you get the idea. And then, above omega one, then, the slope would go to minus 40 dB per decade because there's a zero contribution to the slope here.

**[0:28:36]** So it would look, you know, then maybe something like this. Alright? So, so if you had something else in the circuit that gave you a contribution like that, then what you would get is, it would be a bandpass filter. Alright? And you would be able to...

**[0:28:55]** You could exercise more control over the width of the passband by choosing omega naught and omega one appropriately. Alright? How would you know that omega works greater than omega naught and by how much if they were in terms of l's, r's, and c's? Oh, so so so one possibility is that you would just know the values or you'd be given the values. Right?

**[0:29:19]** And then you'd be able to figure out whether it was greater than or less than. You know, another possibility might be that you might be asked, okay. Design a circuit that has these characteristics, then you would have to select values such that if you wanted this kind of functionality, right, omega one, was greater than, omega naught. Right? Or it may be that, you know, if if you really didn't know the values and you have to account for all possibilities, you could...

**[0:29:50]** You would then say something like, well, depending on whether omega one is less than or greater than omega naught, then, you could get different types of, behavior. In in both cases, you would get, sort of the bandpass filter behavior. Right? If you were to imagine this shifted to the left, then it would still give you, the bandpass behavior, but this slope would only be 20 dB per decade. Right?

**[0:30:22]** So it wouldn't drop off as sharply at low frequencies, but it would be level in the passband. Right? And then that's sort of a trade off of what do you value more. Right? Okay.

**[0:30:33]** Any other questions? Okay. So that sort of brings us to the next topic, which is that of the order of a given filter. Okay? So what we've seen in the different types of filter circuits that we have looked at is that, you know, depending on the details of the filter circuit, sometimes you get slopes of, in the end, for the total transfer function, 20 dB per decade.

**[0:31:10]** Sometimes you get 40 dB per decade. We saw here how you might be able to get an even steeper slope. Right? And in each of those cases, the slope of the Bode plot magnitude line depends on the power to which the frequency is taken, right, in the transfer function. Right?

**[0:31:34]** It's 20 dB per decade if it's a linear, or inverse linear, function of omega. It's 40 dB per decade if it's omega squared or one over omega squared and and so forth. Alright? And so so that brings us to the issue of filter order, which basically has to do with the steepness of essentially the increase or the drop off as you approach or move away from the passband of a filter, and it's essentially determined by the power of the frequency you have in the transfer function in that range of frequencies. Right?

**[0:32:15]** So if you have specifically zeros or poles, right, which are kind of the frequency dependent contributions that you can have to the transfer function, then, basically, the steepness of the frequency response. Alright. Basically, the slope, of that Bode magnitude plot that increases basically as the order of zero or a pole increases. Alright? Because remember, the order is essentially the exponent.

**[0:33:04]** So, a higher order will give you a higher power of the frequency. Okay. So that's basically what's happening here. And for a filter as a whole, we define the order of the filter in an analogous way. Right?

**[0:33:22]** So for a filter as a whole, what we do is we say that the order of the filter, okay, is it's the absolute value. Right? So the order is always a positive number. Right? It's the absolute value of the highest power of omega in the dominant behavior, Okay.

**[0:34:09]** The transfer function h of omega, when omega is, in the filter stopband. Alright. That is outside of the passband. Okay. So so there's a whole bunch of prepositional phrases in there, right, which always makes it harder to understand.

**[0:34:38]** So we'll look at some specific examples here. Alright? So let's go back to the bandpass filter, right, that we looked at, earlier on. Right? So this was a filter where we had an input voltage.

**[0:35:00]** This is an s down here, and it was basically going into an RLC series circuit, and we took the output voltage to be across the resistor. Okay. So this is inductor, capacitor, resistor, and the output voltage was across the resistor. And what we worked out for this is that the transfer function, okay, would be j omega RC over one plus j omega RC minus omega squared l squared... Or sorry, LC.

**[0:35:48]** Okay. So so this was a bandpass filter. The passband was basically centered around the pole frequency, one over root l c, which is also the resonant frequency of this circuit. And so the stop bands, alright, are essentially low frequencies. So omega much less than omega naught and omega much greater than omega naught.

**[0:36:18]** Okay? And so the order of the filter is then determined by the dependence of the transfer function on frequency when we are in these stop bands. Okay. So if we look at omega much less than omega naught, okay, then in that case, if we look at the transfer function, the denominator is going to go to one. Alright?

**[0:36:46]** Because as omega goes to zero, these terms go away. So the transfer function as a whole will approach, just j omega RC. Okay. So the transfer function h of omega will be approximately equal to j omega RC. Right?

**[0:37:01]** That is linear in frequency. Right? So omega to the first power, right, is how the frequency appears. So that then means that this is a first order filter in terms of its behavior at low frequencies. And then for high frequencies, right, that's the other stopband, then the transfer function h of omega, if we look at the transfer function here again, alright, what we see is that at high frequencies, the denominator is going to go as minus omega squared LC.

**[0:37:44]** Alright? And so we have j omega RC in the numerator minus omega squared LC in the denominator, And so that gives us that the transfer function will basically go as r over j omega l. Alright? And the part of this that matters for determining the order of the filter is that you have this factor here, the single power of omega in the denominator. Alright?

**[0:38:22]** And so that means that in this stopband, at high frequencies, this is also a first order filter. Okay? And so, and then that will correspond to having a slope at low frequencies in the transfer... In the magnitude of the transfer function of plus 20 dB per decade, and then a slope at high frequencies for the magnitude of the transfer function of minus 20 dB per decade. Okay?

**[0:38:52]** And plus or minus 20 dB per decade is what you get for first order filter. Okay. So... Alright. What we see here is that the Bode plots...

**[0:39:07]** Or what we did see, okay, for the bandpass filter, right, what we saw was that these Bode plots showed that the magnitude has a slope of, alright, it was plus or minus 20 dB per decade in the stopbands. Okay. So any questions on these ideas here? Okay. Then, right, what we have looked at what we looked at starting in...

**[0:39:52]** At the end of our last class meeting and continuing today was the highpass filter. Okay? So this, alright, just to remind you, was also based on the RLC series circuit. But now where we take the output voltage to be the voltage across the inductor. Okay.

**[0:40:29]** So this is the output voltage, and what we saw here was that the transfer function is minus omega squared LC over one plus j omega RC minus omega squared LC. Okay. So now here, right, this is a highpass filter. So the stopband is... We only have one stopband, and it is at low frequencies.

**[0:41:01]** Alright? So the stopband here is omega being much less than the pole and resonant frequency omega naught. Alright? And so if we look in that range of frequencies, omega much less than omega naught, at the behavior of the transfer function here, we see that the denominator goes to one. Right?

**[0:41:30]** So because at very low frequencies, these turns will, become negligibly small. And so the transfer function, goes as... Alright. It's going to approach minus omega squared l c. Okay.

**[0:41:47]** And so here, we have omega to the second power in the behavior of, the transfer function. And so that means that this is going to be a second order filter. Okay? And in the Bode plots, that corresponded to the magnitude having a slope of 40 dB per decade in the stopband. Alright.

**[0:42:16]** Yes. Question? When we say very low values of omega, do we indicate that omega times any of the any of the RL or C is much less than one is... Because it... In this this, like, generalization is only possible.

**[0:42:35]** Omega RC is less... Much less than one. So so when you compare values, to each other, you can only compare values that have the same units. Right? So, so if you just took omega r or omega c, then, right, omega doesn't have the same units as r or c.

**[0:42:59]** So... But, the quantity that does have units of frequency is the resonant frequency, right, which is one over root LC. Okay? And that's... So that's the relevant quantity to compare to.

**[0:43:15]** And, right, the stopband is omega much less than omega naught. That's where we want to determine the order of the filter. The passband is omega much greater than omega naught, right, where the transfer function approaches a constant and approaches one. Okay? So so in any given circuit, right, the frequencies that will be relevant for comparison will generally be, kind of the nonzero, pole or zero frequencies.

**[0:43:52]** Okay? And then the... You know, where the stopbands are, where the passbands are, and so forth are then, they're kind of bounded by those frequencies or by zero or infinity. And then, you know, so that's part of it. And the other question is, well, that maybe part of what you're asking is, well, what does much less than mean?

**[0:44:18]** Right? Is it 10 times less than or a 100 times less than? And, you know, that... Again, it it depends a little bit on the details of what all the parameters are. Right?

**[0:44:32]** But, you know, very roughly speaking, if you are an order of magnitude below or above, that's usually sufficiently much greater than or much less than. And sometimes you can get closer to this approximation when you are closer to the boundary, but, you know, very roughly, you know, sort of an order of magnitude off. And, you know, that's part of the idea with, say, the Bode phase plots. Right? We say, alright, if we're much less than, you know, the, polar zero frequency or much greater than, then we have the limiting behavior, and we just, you know, not quite arbitrarily, but, as the simplest generalization take much less than to be, you know, more than an order of magnitude below and much greater than to be more than an order of magnitude above.

**[0:45:23]** Okay. Okay. Is that kind of what you're asking? Yeah. Okay.

**[0:45:28]** Any other questions? Okay. So, right. So we see here from, the nature of the transfer function that this is a second order filter circuit. And corresponding to that, when we looked at the Bode plots or, you know, just analyzed the magnitude of the transfer function, what we saw was that the the magnitude of the transfer function in this case, it has a slope.

**[0:46:03]** It was plus 40 dB per decade in the stopband. Okay. And a slope of plus or minus 40 dB, is what you get, if you have a second order circuit. Okay? And you'll get an additional plus or minus 20 dB, in that slope every time you increase the order by one, right, because you're increasing the power of omega by one.

**[0:46:35]** So any questions on that? Okay. So so the next element of filter behavior and filter circuits that we wanna talk about involves what we call active filters. Okay. And the reading for this is in Ulaby et al, and it is sections nine dash six and nine dash seven.

**[0:47:10]** Okay. And the difference here between active filters and what we have talk... Been talking about up to this point, are passive filters, is that in passive filters, there are no circuit components that can give you gain, right, such as a transistor, or, in our case, an op amp or op amps. Okay? In active filters, I...

**[0:47:40]** What makes them active filters is that you can have these components that give you gain, and we'll see that explicitly, in some of our examples, by using op amps in the filter circuits. And the advantage of that is that if you have only passive components, then, you know, eventually, say, if you cascade multiple units of, say, a particular kind of filter together, you'll lose some voltage every time. Right? So eventually, that voltage, will... It'll gradually be derated, and eventually, it'll get, to be quite small.

**[0:48:16]** It can get to be quite small if you have active filters with the possibility of having gain in the circuit, then you can build that signal level back up, or you can have amplification combined with filtering. Okay. So so that's what you get by using active filters. So, definitionally, what we have is that active filters, right, they contain components, alright, that can generate power and therefore gain. Okay.

**[0:49:07]** And the example, of this type of component that we have available to us right now is op amps. Okay? When you get to a course like ECE four thirty eight, then you'll learn about how transistors can can do this as well. Alright? So the idea then is that op amp and other active filter circuits, Alright.

**[0:49:44]** These can then be cascaded, okay, to improve the gain or the frequency response or other characteristics of the circuit. Okay. So that's the basic idea. And what we wanna do now is just to talk about some examples and go through some examples of, initially, some simple active filter circuits. So any questions before we do that?

**[0:50:27]** Okay. So the first example that we will look at, okay, is an active first order lowpass filter. Okay. So this circuit looks like this. So we have an op amp in it now.

**[0:51:01]** Okay. And it'll be a variant on just the the simple inverting amplifier, right, that we looked at, earlier in the semester. Okay. So we're gonna have an input voltage, call it v s as usual, be connected through a series resistance r s, okay, to the inverting input of the op amp. And then for our feedback connection, we will have a resistor and a capacitor that are connected in parallel with each other.

**[0:51:52]** So call this r f and c f. Okay. So if we... And then this will be the output voltage over here. Alright?

**[0:52:08]** Just to be explicit about it, we'll draw it like that. Okay. So this is the circuit that we want to look at. Alright? And if you look at this, right, you can see that it has, it has the same basic structure as just the inverting op amp, amplifier circuit that we looked at earlier, in the semester.

**[0:52:30]** And, alright, to make that comparison, right, more explicit, then what we can do is... Alright. We can kind of lump, these two basic elements together. Right? We'll call this the impedance of, basically, the input the input signal.

**[0:52:56]** We'll call that z sub s, and then we will have the impedance of the feedback loop z sub f. Alright? And so for the input, that impedance is just this series resistance r sub s. Alright? And then for the feedback connection, the impedance of that feedback connection is the impedance of a resistor in parallel with a capacitor.

**[0:53:26]** So that equivalent impedance, oops, is going to be... Right. It's r f times one over j omega c f divided by r f plus one over j omega c f. Alright? We can multiply this by j omega c f over j omega c f.

**[0:53:53]** And if we do that... Alright, what we get then is that this is equal to r f over one plus j omega r f c f. Alright. This is the feedback impedance. Okay.

**[0:54:10]** So this is the circuit that we would like to look at. Alright. So any questions on this? Excuse me. Okay.

**[0:54:19]** So if we look at this right now, what we wanna do is we wanna calculate v out as a function of v s. Alright? And we will do this in the usual way. So if you think back to what we did when we were talking about op amp circuits, essentially, what we wanna do is to apply KCL at this input node, alright, the inverting input of the op amp. Right?

**[0:54:50]** So if we do that, alright, what we have, we know that the voltage at this input node is zero because by the ideal op amp rules, we know that since the voltage at the noninverting input is zero because it's connected directly to ground, we know the voltage at the inverting input has to be the same, so it's zero as well. Right? So if we apply KCL, right, we have the current going out this way to the left, which is zero minus v s. So just minus v s divided by, the impedance z sub s. And then, the current flowing upward and to the right this way is just zero minus v out divided by z sub f.

**[0:55:39]** Right? So minus v out divided by z sub f, and then those two have to add up to zero because the current going into the op amp is zero. Alright? So these add up to zero, and so we get that v out is equal to minus z f over z s times v s. Right?

**[0:56:10]** Which should look familiar to you because that's basically the result that we got for the inverting op amp amplifier circuit. Okay? And then once we have that, then we can calculate the transfer function h of omega. Okay? And that is equal to v out over v s.

**[0:56:34]** Right? So that is from this expression here. Right? It is minus z f over z s. Alright?

**[0:56:48]** And right over here, we have z f and z s that we have already figured out. So then we're gonna get minus z f, so minus r f and then divided by z s. So minus r f over r s times one over one plus j omega r f c f. Alright. That's gonna be the transfer function.

**[0:57:15]** Okay. So it is minus r f over r s times one over one plus j omega r f c f. Alright? So what we see here is that, right, we have a constant out here, and then we have this factor over here, which is a simple pole at omega equal to one over r f, c f. Right?

**[0:57:43]** So this is a simple pull, and we'll just call it omega naught is equal to one over RF c f. Okay. So from that, alright, we can quite easily now construct the Bode plots. Right? We won't go through the exercise of, you know, breaking it up into the constituent factors and, you know, constructing the Bode plots for each of those and then combining them because this is simple enough that we can just essentially get it directly.

**[0:58:23]** Okay. So if we look at the Bode plots... Okay. We will plot the magnitude first as usual. Okay.

**[0:58:41]** So it's the magnitude as a function of frequency, and we have... Alright. The pole frequency omega naught over here. Alright? And, right, basically, what we can see is that at low frequencies...

**[0:59:00]** Alright. So omega much less than omega naught. This denominator here just goes to one. The second term goes to zero. So the magnitude is going to be r f over r s.

**[0:59:12]** Okay. So what we have then is on the dB scale, then we have 20 times the log of RF over RS. Right? That's the limiting value as we go to low frequencies. Okay.

**[0:59:34]** And so we will have this. And then, at high frequencies, omega much greater than, the pole frequency omega naught, then this factor here will go as, basically one over j omega RFCF. Alright? And the key part of that is that, it goes as one over omega. Alright?

**[0:59:56]** And so we will have a downward slope over here, and that slope will be minus 20 dB per decade. Okay. And then for the phase, right, what we have is that, if we now wanna construct a phase plot, five omega as a function of omega, This will be point one omega naught. This will be omega naught. This will be 10 omega naught.

**[1:00:35]** Okay? This is zero degrees. We'll also mark 90 degrees and a 180 degrees. Okay. Add very low frequencies.

**[1:00:46]** Right? So less than point one omega naught. Then, this second term here goes to one, and so we have the phase of minus one, which will take to be a 180 degrees. As omega goes to infinity, so very high frequencies, then this factor will go as one over j omega RFCF, and so we'll have, in terms of the phase, the relevant factor is the j in the denominator. All right?

**[1:01:15]** So that will make an additional contribution of minus 90 degrees to the phase. Okay. So what we'll have then oops, okay, is that at low frequencies, have a phase of, a 180 degrees. Very high frequencies, we have a phase of 90 degrees, and then the transition looks like this. Okay.

**[1:01:45]** So, this is what we have for, this, active first order lowpass filter. Right? We can see it's a first order filter because it has this minus 20 dB per decade slope corresponding to the linear dependence on omega to high frequencies. And because it is an active filter, right, we can see that we can get gain. Right?

**[1:02:11]** That is a magnitude of the transfer function in the passband that can be substantially greater than one or zero dB. Okay? And that can be engineered into the design of the filter by selecting the feedback and series resistances. Okay. So...

**[1:02:34]** Oh, yes. How about you make the slope even greater? Or, I guess, a higher magnitude? Yeah. So so we'll get to this...

**[1:02:43]** Or one way that you can do this probably next time, which is that... Right? If you had a circuit like this and then you have the output voltage, right, basically given by this, if you then constructed another copy of this same circuit and use this v out in the role of v s... Okay, remember the output of an op amp in the ideal op amp model can basically act as an ideal voltage source. Right?

**[1:03:18]** So it can play the role of this v s. And then... If you took this output and connect it to to another copy of all of this, then you would get another, basically, another factor like this in the transfer function. Right. Like, I'll put it into the pins for these, like, we were to stack them, or would I have to put, an op amp?

**[1:03:42]** So that depends on the details of the circuit configuration. But in this case, right, if we're taking the output of the op amp and connecting it directly as the input, say, this point to the next unit that looks like this, okay, then you wouldn't need another op amp in between because, right, you can, in principle, connect anything to v out here, and it won't change, the output voltage. Right? That's one of the things that you get from, the ideal op amp. From an op amp in the ideal op amp limit.

**[1:04:22]** But if you had, you know, if if you had back here some more complicated passive circuit, right, that was giving you some filtering function and you wanted to add this active filter circuit as another unit, subsequently, then you would have to worry about how this resistance here, say, interacted with, the other things that were in the passive circuit. And so in that circumstance, it may be that you would want to put, say, a, a buffer or something like that in between. Okay. But if you're connecting another unit like this at the output, you wouldn't have to. Okay.

**[1:05:06]** Does that answer your question? Okay. So there are a few things that we wanna note here. Okay. One is that, in this case, the resonant frequency...

**[1:05:20]** Not the resonant frequency. The pole frequency, it doesn't depend on RS. Right? So if we were... You know, if we attached to this not an ideal voltage source but some realistic voltage source, right, represented by a voltage source in series with a resistance, then we wouldn't change the pole frequency because the pole frequency doesn't depend on RS.

**[1:05:53]** We would change the gain, right, but not the pole frequency. Okay? Another point to note is that, right, because the op amp... Because the output signal of the circuit is at the output of the op amp, then you can add any load resistance to it, and you won't change that output voltage. Right?

**[1:06:18]** So v out, this will be unchanged, alright, for any load resistance, say RL, that's connected to v out. And then it's up here. Alright. The third point to note is that... Alright.

**[1:06:54]** Because this is now an active circuit, you can have gain. Right? So the op amp, it can provide gain in the filter passband. Okay. So that is the sort of active first order lowpass filter.

**[1:07:19]** The last thing that we'll do today is we will look at a second, also relatively simple example, which is an active first order highpass filter. Okay. And it has a structure that is quite similar to what we just looked at. Alright. So we have an op amp here.

**[1:07:55]** Okay. The, noninverting input, connect to Okay. So let me figure out how to get myself back into... If I can still share here. Okay.

**[1:09:22]** K. So let me okay. I guess all of these Zoom or IT malfunctions are now preserved forever since this is being recorded. So... Okay.

**[1:09:38]** So then let's see. So we have... Just gonna update here. Okay. Alright.

**[1:09:45]** So that's working again. So we have just a feedback resistor over here. Okay? And then this is our output voltage. Okay.

**[1:10:01]** So, again, right, what we wanna do is we wanna think about the input and output impedances. Right? So this is going to be the series input impedance z sub s, and then this will be the feedback impedance z sub f. So z sub s here is... Right.

**[1:10:27]** It's r s plus one over j omega c s, and then the feedback impedance is just RF. Okay. And we can analyze this now in exactly the same way, that we did for the, let me bring up the chat box here just in case. Okay. In the same way that we did the the lowpass filter circuit.

**[1:10:58]** Right? So, basically, again, if we apply KCL at the inverting input of the op amp, we get that minus v s over z s minus v out over z f is equal to zero. And then if we solve for v out, we get that it's equal to, once again, minus z f over z s times v s. Alright? And so the transfer function is then the output voltage over the input voltage, and so it's going to be ZF over ZS.

**[1:11:48]** So Rf divided by Rs plus one over j omega CS. Alright? So this is going to be... Or it's minus that. Minus r f over r s plus one over j omega c s.

**[1:12:08]** And then here, we're gonna multiply by j omega c s over j omega c s so that we get rid of, this fraction in the denominator. Okay. So we get minus j omega r f times c s divided by one plus j omega r s times c s. Okay? And then if we take this and, we separate it out into its constituent factors, then we get minus r f c s.

**[1:12:50]** Right? Essentially a constant. And then we have minus... Or sorry. Plus j omega divided by one plus j omega r s c s.

**[1:13:04]** Okay. And so we see here that we have a simple zero at the origin. Right? We have this constant factor out front. And then, from this term in the denominator, we see that we have...

**[1:13:23]** Now it's a simple pole at a frequency which we will again call omega naught, and it's one over r s times c s. Okay. So any questions to hear? Okay. Now we can go ahead and construct the Bode plots for this transfer function.

**[1:13:55]** Okay. And, again, we will just go directly to, the Bode plot rather than, using the intermediary of, the individual factors. Okay. So we have, right, we're looking at the magnitude on a dB scale as a function of frequency. So we have point one omega naught, omega naught, and 10 omega naught.

**[1:14:26]** Okay? And, what we see is that right here, this is a highpass filter. Right? If we are at high frequencies, then, in the denominator, this goes to just j omega r s c s. So we're gonna have the j omega here and the j omega here cancel out.

**[1:14:47]** The c s here and the c s here cancel out. So we're just gonna have minus r f over r s. The magnitude of that is just r f over r s. So we're gonna have 20 times the log of r s... R f over r s.

**[1:15:09]** Okay. And that will be the limiting value of the magnitude of the transfer function at high frequencies. And then at low frequencies, right, so omega much less than omega naught, then the denominator goes to one, and we just have this j omega over here. And so that is first order in omega. So this is gonna be a first order circuit, and we're gonna have a transfer function that looks like...

**[1:15:47]** Magnitude that looks like this with a slope of 20 dB per decade. So that is the magnitude. And then for the phase, right, if we plot that out... So phi of omega is a function of omega. This is point one omega naught.

**[1:16:13]** This is omega naught. This is 10 omega naught. Right? This is zero degrees, and we will mark minus 90 degrees and minus 180 degrees. Okay.

**[1:16:28]** And what we see is that as omega goes to zero, right, so at very low frequencies, then the denominator here is one. And so we just have, for the phase, the relevant factor is minus j. So that has a phase of minus 90 degrees. Okay. So that's gonna be like this.

**[1:16:52]** And then for very high frequencies, alright, so omega, say, greater than 10 omega naught, then what'll happen is we will have j omega over j omega r s c s. So the j here and the j here will cancel out, and we just have the factor of minus one that will determine the phase, and that will be minus a 180 degrees. Okay. And, the transition will look like this. Okay.

**[1:17:25]** So these are the Bode plots that we have for this active first order highpass filter. And, basically, what we see here is, you know, again, because this is an active filter, then we can get gain in the passband that's determined from the design of the circuit. Right? R f over r s. Alright?

**[1:17:51]** That's the main distinction that you get from the active filter circuits compared to the passive filter circuits. Okay. So any questions on this? Okay. If not, then we will stop here for today.

**[1:18:08]** And what we will do next time is we will talk about cascaded filter circuits, which kind of gets back to the question that, Nathan, you had asked, how do you get, higher order circuits? One way of doing that is cascading, multiple stages, together, and we'll see an example of how that works, starting in our next class meeting. Okay. So that is it for today, and I will now stop the recording. Oh.

**[1:18:41]** Let me skip the final. Oh, so the final, it will be
