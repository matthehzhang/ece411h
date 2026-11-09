# 2026-11-02-laplace-transforms

Deepgram general-nova-3 2025-07-31.0, request 01a1b011-3418-7640-8bbd-386ca384eeb9, audio 77.6 min.

**[0:00:02]** Okay. So I have started the recording as usual. And as always, we'll start with a few announcements. The first couple are pertaining to the homework. So just a reminder that problem set seven, was due today, 9AM, so hopefully, people have turned that in.

**[0:00:20]** And then, the next problem set, problem set eight, is due a week from today, so on Monday, November 9. And then the next announcement is that remember that we have semester exam two coming up on Wednesday, November 11. Okay? So the answer sheet template for that exam will be posted hopefully late this week, but definitely by the beginning of next week. And you should make sure, as with the first exam, to bring a copy of the template to the exam.

**[0:00:54]** And that'll have to be a hard copy template on which you'll physically write your solutions. The fourth announcement is that I have posted a short, what I've called a checkpoint survey on Canvas, and that is just sort of asking about your experiences in the course so far. And compared to the past few years, I've added a few questions on the survey that pertain to the use and impact of AI, which I think even compared to last year is much more prominent and certainly much more powerful. So if everyone can complete the survey by 11:59PM on Sunday, then that'll be particularly helpful to me in understanding your experiences thus far. The final announcement is that there will be handout on Laplace transform pairs that I'll post on Canvas later this week.

**[0:01:50]** That's a topic that we will... That we'll start discussing today. And just to give you a heads up, I will give you a copy of that table for you to use on the final exam, but, of course, you won't have it for the second semester exam because Laplace transforms are not included, in the content on the second, semester exam. So any questions on, these announcements? Okay.

**[0:02:18]** Any questions from our last class meeting? Okay. If not, then we will pick up from where we left off. So basically, what we want to do today is we wanna finish up our discussion of, active filter circuits, and that will bring us to the end of what's covered on the second semester exam. And then we will start the discussion of circuit analysis using Laplace transforms, which will not be on the second semester exam, but it will be on the final.

**[0:02:51]** Okay. So that's what we have coming up for today. And if you remember, back to... If you think back to what we did last week, when we started talking about active filter circuits, then, we talked about, in our last class meeting, two types of first order active filter circuits. We talked about a highpass filter and a lowpass filter.

**[0:03:13]** And actually, one of you, I think, Nathan, you asked this question about whether it's possible to combine multiple circuits like that in order to basically get a higher order filter, which will give you a steeper roll off. And the answer was yes, and our first example today actually shows how this will work. So we want to start off today looking oops, wanted the black pen here. Okay. We'll start off looking at an example of another active filter circuit, which is a cascaded third order lowpass filter.

**[0:04:01]** Okay. And what we will see here is that by taking the basic lowpass filter structure that we talked about last Wednesday and constructing a cascade, so taking the output of one stage and using it as the input to another stage, then we can get essentially the same lowpass filter functionality, but with a high... But a higher order filter so that the drop off is steeper. Okay? And so the circuit that we will look at that does this is this one.

**[0:04:33]** So it's a pretty big circuit, so you should leave room to, include the entire circuit. So we have an op amp, okay, with its output and two inputs. The, noninverting input is connected to ground, and then we have a voltage source v sub s connected through a resistor. This is a 10 ohm resistor to the inverting input, and then our feedback connection will consist of a resistor and a capacitor in parallel with each other. K.

**[0:05:17]** So this will be a 10 kilo ohm resistor and a one nanofarad capacitor, and, this circuit will give us an output voltage v one. Okay? And if you look at this and you look back to what we did last Wednesday, this is basically just the first order active lowpass filter that we looked at last time. Okay. But now what we can do is we can take the output of this stage of the circuit, right, this voltage v one, right, since that is at the output of the op amp, then it'll act, within the limits of the ideal op amp model essentially as, a voltage source.

**[0:06:00]** And so we can use that as the input to a second stage of this circuit, which is just another, first order, active lowpass filter. So we're gonna connect this again through a resistor, but now this resistor is going to be a 10 kiloohm resistor, and we will connect that to a second op amp. Okay. So v one is connected through the resistor to the inverting input, and then the noninverting input is connected to ground. Okay?

**[0:06:35]** And then we have... Again, in our feedback connection, we have the same configuration of a 10 kilo ohm resistor in parallel with a one nanofarad capacitor. That gives us an output voltage v two. Okay? And then we will have one more stage of this, which is essentially just a repeat of the second stage that we just drew.

**[0:07:10]** So where we take, the output v two of the second op amp and connect it through a resistor, which is, again, a 10 kilo ohm resistor, and that is connected to a third op amp, okay, where the noninverting input is again connected to ground. And then we have the same, feedback connection that we had for the other two stages, right, where we have, once again, the 10 kiloohm resistor and the one nanofarad capacitor. And that brings us to the final output of this circuit, which we will call v three. Right? The output voltage of, the third op amp stage in this circuit.

**[0:08:04]** Okay? So this is the circuit that we want to analyze, and what we will see is that each successive stage of this circuit gives us basically another factor of pole in the transfer function. So we'll have three of those, and that will give us a third order lowpass filter. Okay. So that's the basic idea.

**[0:08:28]** Now if you look at these three stages, alright, you can see that each of them has the same configuration for the feedback connection. Right? 10 kilohm resistor in parallel with a one nanofarad capacitor. Okay? And so, you know, as we did before, alright, we can think of that as in terms of just its impedance.

**[0:08:55]** Alright? So this is the the feedback impedance z sub f. Alright? And if we think about the capacitor and the resistor together in that way, then you can see that this has the structure just of an inverting op amp amplifier. Alright?

**[0:09:14]** And so if you remember to what we did when we talked about op amp amplifiers, then we know that the output of this is going to be just v one here. It's gonna be minus z f over this resistor over here times the input voltage. What we also have here is that because each of these feedback connections has the same combination of components, right, 10 k resistor in parallel with one nanofarad capacitor, then each of these stages will have a pole in the transfer function, and that pole will be at the same frequency. Right? That frequency, omega naught, is just going to be one over the resistor value times the capacitor value, so RF times CF.

**[0:10:06]** And so that is going to be one over 10 kilohms times one nanofarad. And if you work that out, right, that's in the denominator, it's 10 to the fourth times 10 to the minus nine. So that's 10 to the minus five in the denominator, so that becomes 10 to the five in the numerator. Right? And that is in radians per second.

**[0:10:29]** Okay. So this is going to be the pole frequency, and it'll be the pole frequency for all the op amp series. Okay. And we'll use this frequency throughout the rest of our analysis of this circuit. So are there any questions to hear?

**[0:10:49]** Yes, Jason. In general, creating filters, they, you know, they have a goal. They want to make some, you know, bandpass filter. Do they sort of memorize, for lack of better word, different kinds, different structures of circuits and then just tune the parameters to fit what they need, or do they usually, like, come up with completely new circuits that try to So the answer is, in many cases, it's somewhere in between. So, alright, it's not really practical, to try to memorize every possible configuration, alright, you know, especially once you get to, more complicated functionalities that you might wanna get.

**[0:11:38]** But there are certainly, you know, there are some basic building blocks. For example, inverting amplifier, right, or how you do summing or a difference, and, you know, just maybe some of the basic filter circuit structures that are important come up frequently and where it's very useful to have that as just part of your working knowledge. Alright? And then from those, then you can build up kind of more complicated structure... Circuit structures and achieve more complicated functionalities.

**[0:12:12]** And then, you know, having some understanding and ultimately intuition for how these different pieces work together and how you can, you know, say, efficiently get a particular function or, you know, really push the limits of the performance of a circuit is very useful as well. And so, you know, basically, a lot of practice and thinking about it is generally how you develop those kinds of capabilities. Is that kind of what you're at... What you're asking? Yeah.

**[0:12:43]** Okay. So so any other questions right now? Okay. So let's go ahead and analyze this circuit. We pointed out that each of these stages has the same feedback impedance, z sub f.

**[0:13:00]** So let's calculate what that impedance is. Right? It's just the impedance of the resistor in parallel with the capacitor. So that's gonna be the product r sub f of the impedances, r sub f times one over j omega c sub f divided by the sum, r sub f plus one over j omega c sub f. Right?

**[0:13:24]** And to simplify this a little bit, we will multiply the numerator and the denominator as usual by j omega c sub f over j omega c sub f. Okay. And if we do that, then what we get is in the numerator, r sub f, and in the denominator, we get one plus j omega r sub f times c sub f. Alright? And so this product here, right, r sub f times c sub f, that's where this frequency omega naught, the pole frequency, comes from.

**[0:14:02]** And if we plug numbers, into this, then for r sub f, that's 10 kilohms, so that's 10 to the fourth divided by one plus j omega. And then, r sub f times c sub f, that's one over omega naught, so that's going to be 10 to the minus five. Okay. So, this is the, the feedback impedance. And once we have that, then we know that the voltage v one.

**[0:14:32]** Right? That's the output voltage of the first stage, okay, of this circuit is going to be, alright, it's minus z sub f over z sub s. Right? Z sub s is, in this case, it's the 10 ohm resistor that's connected between the input signal and the op amp input times the input voltage v sub s. Right?

**[0:15:00]** This is something that perhaps you just remember from the discussion of the inverting amplifier op amp circuit, or you could easily derive it using... By applying KCL, right, at the inverting input of the op amp. Okay. And so what we get from this is z sub f is this expression over here. So we have 10 to the fourth, and then it's divided by this input resistor, 10 ohms.

**[0:15:29]** So we have 10 to the fourth over 10, that's 10 to the third, and then in the denominator, one plus j omega, and then r f times c f is 10 to the minus five times v sub s. So that is the voltage v one, the output of... The output voltage of the first stage of this circuit up here. Right? So v one over here.

**[0:15:57]** So any questions to hear? Okay. So now what we wanna do is we can take this voltage v one that is produced by the first stage of this circuit and take that to act as just the input voltage of this second stage over here. Alright? And, remember, this voltage v one, since this is the op...

**[0:16:23]** Output of the op amp, we can think of it as essentially acting like, just the voltage source. Okay? And so then to get v two, right, v two, the output of the second stage, is going to be just minus the same feedback impedance, z sub f, since that's also the feedback impedance of the second stage, now divided by this resistance over here, right, which is 10 kiloohms, right, rather than 10 ohms. Okay. So we have this over now 10 kiloohms, and that is times the voltage v one, which is now acting as the input to the second stage.

**[0:17:10]** Okay? And if we just plug in the values and the expressions for for all of this, we have the minus sign over here, and then we have z sub f over 10 kiloohms. So for z sub f, we have 10 to the fourth and then... In the numerator, and then we have 10 kiloohms in the denominator, which is also 10 to the fourth. And then from z sub f, we have one plus j omega times 10 to the minus five.

**[0:17:43]** Okay. So that's minus z sub f over 10 kiloohms. And then we have... Oh, yes. Question.

**[0:17:49]** If it's like, generally speaking, that once we get the the upper bound goes straight to the other one. Mhmm. And I think of it as, like, you know, you just have c f one, m c f two, m c f three, like, all the way, so on and so forth. Then Yeah. Or the transfer functions get multiplied.

**[0:18:08]** Oh, okay. Right. Not necessarily just the feedback. I... And then it's divided by the the Right.

**[0:18:15]** Source. Yeah. So that's the additional factor that goes into the transfer function. And that works because, right, the output of each stage is at the output of the op amp. So it really is acting as, a voltage source.

**[0:18:30]** So it can draw... You can draw any amount of current, right, within the limits of the ideal op amp model. I can draw any amount of current, and they'll still give you the same voltage. If you had a passive, circuit that had multiple stages like this, and we looked at an example that was kind of like that earlier, then connecting the output of one stage to the next stage would change the behavior of that first stage. Okay?

**[0:18:56]** So then you have to be more careful, about how you do that. Here, it's more straightforward. Does that answer your question? That is... It's just you can multiply each transfer function.

**[0:19:09]** Yeah. That's a bit essentially how it'll go here. Yes. You you said with passive filters, a different loads would create different function or, like, would alter the original circuit? It would change the behavior of the original circuit in the in the sense that if you had a, an initial stage that had a particular output voltage, right, when it wasn't connected to anything, then if you take that to be the input to another, say, passive stage, then you'll start drawing some currents through that terminal, and that will change the behavior of that first stage.

**[0:19:48]** So then you have to analyze the whole thing together. Okay. So so what we have here so far is minus z f over 10 kiloohms, and then that is times the voltage v one. Alright? And v one we calculated up here.

**[0:20:05]** So we're gonna multiply this by minus 10 to the third over one plus j omega 10 to the minus five times the original input voltage v sub s. Okay? And if we put all this together, then what'll happen is that these 10 to the fourths will cancel out, The minus signs will cancel out. Okay. And then what you get is, 10 to the third.

**[0:20:41]** Alright. That is this 10 to the third over here over... Now it's going to be one plus j omega 10 to the minus five squared. Right? Because we have two factors, two of the pole factors over here in the total of what would be the transfer function for two stages times v sub s.

**[0:21:04]** Alright? So you can see that sort of the main effect of adding this second stage to the circuit is to give you another pole factor in what would be the transfer function for two stages. And so now this has become... If this were the end, this would be a second order circuit. Right?

**[0:21:23]** Because it has, basically, at high frequencies, omega squared in the denominator. Okay. So any questions to hear? Okay. And then the last step, okay, is to look at the...

**[0:21:38]** To calculate the voltage v three. Right? That is, alright, the output of this third stage of the circuit with the voltage v two as its input. And since this third stage is the same in structure and component values as the second stage, then the analysis will be exactly the same. Alright?

**[0:22:04]** So to get v three, that is going to be minus the feedback impedance z sub f, again, over 10 kiloohms, now times, its input voltage, which is v two. Okay? So we're going to get... It'll be minus. And then from z sub f, we have 10 to the fourth in numerator.

**[0:22:27]** Then from the 10 kiloohms, we have 10 to the fourth in the denominator. And then from z sub f, again, we have one plus j omega 10 to the minus five. Okay? And that is times v two, which is this... Given by this expression over here.

**[0:22:43]** So 10 to the third times in the... Or divided by one plus j omega 10 to the minus five quantity squared times v sub s. Okay? And then here, again, we get the 10 to the fourths, in the numerator and the denominator canceling out. So what we finally get is minus 10 to the third over one plus j omega 10 to the minus five now cubed times v sub s.

**[0:23:20]** Right? And since v three is the final output of the circuit, then we can calculate the transfer function h of omega. Right? That is going to be the output voltage v three over the input voltage v s, and that is just this prefactor over here. Alright?

**[0:23:41]** So it is minus 10 to the third divided by one plus j omega 10 to the minus five now cubed. Okay. So this is the transfer function. And so what we can see is that, alright, we have this factor in the denominator, and that corresponds to having now a third order simple poll. And the pole frequency is omega naught, which we saw earlier is 10 to the fifth radians per second.

**[0:24:24]** Okay. So this is the transfer function. Okay? And we can look at the Bode plots, for this. So if we look at the Bode magnitude plot.

**[0:24:41]** Okay. And so remember the Bode plots, in the terminology and the convention that's used in Ulaby, the Bode plots are the, basically, the log plots of the magnitude versus the log of frequency and then the plot of the phase versus the log of the frequency, using kind of the linear approximations for the limiting behaviors at low and high frequencies for, for the magnitude and the phase. And so for the magnitude, right, this is the magnitude of the transfer function in dB versus frequency, and we will mark point one omega naught where omega naught is the pole frequency omega naught and 10 omega naught. Okay. And for the low frequency behavior of this, right, we have that this is going to go to...

**[0:25:44]** For the magnitude, it's gonna go to 10 to the third, right, because omega is going to zero. And so we're gonna have 20 times the log log base 10 of 10 to the third. The log base 10 of 10 to the third is three, so that's gonna be 60 dB. Okay. So, at low frequencies, this is gonna go to 60 dB.

**[0:26:07]** And then, at frequencies below omega naught in the Bode plot, for the linear approximation, we just take this to be constant. And then at high frequencies, right, so frequencies above omega naught, right, then we take the behavior of this to be its linear behavior at very high frequencies where in the denominator, we're going to have... Basically, it'll go as omega cubed in the denominator. So that means that for every factor of 10 increase in the frequency, we're gonna have a factor of 10 cubed or a thousand increase or decrease in the transfer function. Okay?

**[0:26:51]** And so a factor of 10 to the third decrease for every factor of 10 increase in the frequency gives us a slope of minus 60 dB per decade. Okay. So this is gonna come down kind of like this. So the slope here is minus 60 dB per decade, okay, which is much steeper than what we saw for the first order filter where that slope was minus 20 dB per decade. So instead of going down by a factor of 10 for a factor of change in the frequency, it goes down by a factor of a thousand.

**[0:27:33]** Yes. So, I guess, what's the, like, real world limit for this? Because, like, the theoretical limit is you could just do this amount of times and get a perfect, like, box, basically. But, like, the real world limit, you know, real stuff, like, how... I guess, why don't you just make, like, oh, let me put, you know, five of them in a row?

**[0:27:54]** I mean, these are very cheap parts, I feel like. Yes. So so in principle, you could do that. Although, you know, it's not that cheap and, you know, it doesn't take up zero space or consume zero power. And then a lot of times, in addition to being concerned with...

**[0:28:15]** You know, this is... At some level, it's... We're thinking about dependence on frequency, but we're kind of thinking about it in a framework that's largely a DC, framework. So we're not worried about, you know, parasitic effects or frequency response or anything like that of, the... Say, in this case, the op amps.

**[0:28:34]** And, as, you know, as you try to push their performance of, a given circuit by, you know, adding things that in principle, you should be able to just cascade in this way, then you start reaching other limits of how these things, you know, how these components will, perform so that, you know, if you have many of these together, there's there's more parasitics that takes longer for it to respond and so forth. And so, in practice, you can only go so far in, sort of cascading, the ideal behaviors and expecting to get the ideal behavior out. It's like... I guess, what's kind of the norm with the game? Should it be that you equally spread it out between each, like, stage or just put it on the meeting one and then have all the other ones kinda be more followers?

**[0:29:35]** Oh, so so that depends on, what exactly you're trying to optimize. So, actually, I had a senior design team that was working to build some instrumentation for our lab a few years ago, and one of the things that they had to do was to build, an op amp based circuit that had very high gain, like 10 to the eighth or so because we wanted to amplify a very small current. And then at the same time, have good frequency response. Okay? And so, in that case, right, one of the limitations that, you can have in op amps is that they can only, say, change their output voltage at a certain rate.

**[0:30:28]** Okay? And so if you try to get a huge gain in one stage, then the op amp wouldn't be able to change, the output voltage, at a sufficiently high rate to get that gain. So in that case, you you wanna divide up the gain across multiple stages. There are other situations, you know, again, for some other types of instrumentation that we have had in the lab where you also wanna have an extremely high gain, but if it takes, you know, a long time, right, to get, say, a factor of 10 to the 10 gain, long within reason, meaning, like, half a second or something like that, not minutes, then it was fine. But you had to put all these, components into a vacuum system, and so you wanted it to be compact, not dissipate a lot of power and such.

**[0:31:24]** So, so then you just put one op amp in that's a high performance op amp and a very high value resistor for, to make essentially an inverting amplifier, and that was, you you know, sort of the preferred, design for for that functionality. So it really depends on what you're trying to optimize for, and and that can be quite different, in different circumstances. So, hopefully, that sort of answers your question. Okay. Any other questions?

**[0:31:54]** Okay. So, so that's the magnitude. We also wanna look at the phase. So let's look at the Bode phase plot. Okay.

**[0:32:09]** So there, remember, in the Bode plots, the phase is on a linear scale, but the frequency is still on a log scale. So we have point one omega naught, omega naught, and 10 omega naught. Okay? If we look at the transfer function over here, as omega goes to zero, then the phase will be determined by just this factor of minus one. Alright?

**[0:32:44]** So minus one, has a phase of a 180 degrees. Okay. So what'll happen is at low frequencies, which remember for the phase plot, we take that to be much lower than the pole frequency. So less than, point one omega naught is the convention that we use here. So it's a 180 degrees.

**[0:33:09]** And then, as the frequency increases, what we can see is that, in the denominator, we have this one plus j omega tens times 10 to the minus five. Right? So for that factor, then that will give us a phase angle that is positive and in the first quadrant. Okay? And then it'll be cubed.

**[0:33:35]** So then that phase factor will be multiplied by three. Alright? But for now, the key point is that this is going to be positive phase angle, and so it's going to... Since it's in the denominator, it's gonna subtract from the phase of zero. So it's gonna start coming down.

**[0:33:52]** The phase is gonna start coming down like this. Okay? And then when we get to very high frequencies, say, omega greater than 10 omega naught, what'll happen here is that this will basically... In the denominator, the phase will be determined by a factor equal to j cubed. Alright?

**[0:34:16]** And j cubed has a phase of what? What do you think? Negative. Well, what is what is the what is the phase of j? Right.

**[0:34:37]** And so what's the phase of j cubed? Right. So so you can have it as either negative 90 or as two seventy. Right? So...

**[0:34:49]** But actually, right, if you think about how this evolves as omega increases, we wanted to take we wanna take it to be two seventy, and that's gonna be subtracted from 180 degrees. So that'll bring us to minus 90 degrees. Okay. So, we'll have this phase out here and then... Alright.

**[0:35:16]** The transition will look like this. Okay. So this is what the Bode phase plot looks like for for this third order lowpass filter. Alright? But, you know, the key point that we really wanted to see here was that by having these multiple stages, we could get a steeper roll off outside the the passband of the filter.

**[0:35:43]** Okay. So any questions here? Yes, Jason. If it's negative originally, why is the phase one eight... I guess it doesn't matter between one eighty and negative.

**[0:35:56]** One eighty and ten. Yeah. So we could have started this... Instead of starting it at one eighty, we could started... We could have started it at minus one eighty.

**[0:36:04]** Okay? And then, it would have gone from minus one eighty, you know, down to 180 minus two seventy. Right? But, you know, in general, we kind of wanna have things, you know, closer to zero. Right?

**[0:36:22]** So, you know, you can add or subtract some integer multiple of 360 degrees from the phase. It's not gonna change anything, and, you know, it's sort of a convention, right, that, is convenient and often used to, say, alright. The phase... You wanna define the phase so that it's within a certain range, say, minus one eighty to one eighty or, zero to three sixty or something like that. Okay.

**[0:36:48]** But if we wanted to, we could have shifted it, by some multiple of three sixty. Any other questions? Okay. So so that's the example that we want to look at of cascaded active filter. Alright?

**[0:37:07]** There are some other examples that I've made recordings of that you can take a look at and that will help you to understand further how to think about and design cascaded filter circuits. So you can also see videos that I will post on Canvas of two additional examples. One of them is a cascaded bandpass filter. Okay. So the same idea of cascading.

**[0:37:47]** Now in this case, it'll be a lowpass filter with a highpass filter, and then by doing that, you can get a bandpass filter. If you switch the order of the frequencies for the lowpass and the highpass, you could get a cascaded band reject filter. And then the other exam... Example that I'll post a video of is band reject filter design. Okay.

**[0:38:17]** And the idea in that example is that you're given a set of parameters that the circuit has to satisfy. So the gain, what the stopband is, and what the roll off has to be, outside of, the band stop, right, where the the band reject region. And then the idea is to design a cascaded filter circuit that actually satisfies all of those conditions. Okay. So so you can take a look at the videos that I'll post to see examples of how those things are done.

**[0:38:53]** And then, right, and then there are the problem solving videos that have been posted for the semester, and there are some examples of these types of filters there as well. And so including these videos that I've listed here, that is the end of what you were responsible for for the second semester exam. So semester exam two basically covers to this point. Okay. And then, what we will do after this, which is to discuss...

**[0:39:33]** Start our discussion of integral transform techniques and specifically Laplace transforms, will be included on the final but not on the second semester exam. So any questions to hear before we continue with the, next major topic? Okay. So if not, then we'll move on to the last big topic for the course, which is the use of Laplace and Fourier techniques to really broaden the class of behavior... Of input signals, right, that we can have in understanding and analyzing and designing circuits.

**[0:40:20]** And we will start off looking at how we use what are called Laplace transforms for analyzing and thinking about circuits. So we wanna look at now the topic of circuit analysis, using Laplace transforms. Okay. And this is discussed in Ulaby et al, and it's chapter 12. Okay.

**[0:40:59]** So to put some context, around this, if you think back to what we have been doing over the course of the semester, basically, what we've been doing is we have been looking at time dependent behavior of circuits and gradually expanding the range of input signals for which we can understand and analyze and ultimately design circuits with particular functionalities. Right? So earlier in the semester, right, what we did was we analyzed circuits in the following situations. Okay. At the very beginning of the semester, right, we started off by looking at circuit behavior in the time domain.

**[0:42:03]** Alright? Because that's, sort of the most intuitive in some sense because, you know, we kind of function in the time domain. And so what we did was we used the basic circuit laws, KCL, KVL, you know, node analysis and the like, and, we use the relationships between current and voltage in the time domain for the different types of components. So Ohm's law, for a capacitor, the voltage is... Or current is equal to c dV dt and so forth.

**[0:42:32]** And we use those to construct differential equations that describe the behavior of currents and voltages in the circuit. And then, we tried to solve those differential equations so that we could get the behavior of the circuits, and we were able to do that but only for, really, the very simplest types of input signals, so constant input voltage or maybe voltages or currents switched on or off, but nothing really more complicated than that. Okay. So what we did first was in the time domain, right, we used differential equations. Okay, to understand the time dependent behavior of circuits, right, the time dependent response, but only for really quite simple input signals.

**[0:43:45]** Okay. So that was useful but really quite limiting. Okay? After that, what we did was we moved to the frequency domain, right, which you saw in an introductory way in three zero two and three zero two h, and we said that we could use phasors to understand the steady state response of circuits if we had signals that were sinusoidal signals. Right?

**[0:44:14]** So oscillating as sines or cosines at a single fixed frequency. Alright? And that allowed us to understand and think about and, you know, develop some intuition for how circuits behaved at a fixed frequency, right, where you had sinusoidal signals in the circuit. Right? So then, right, the next thing was that in the frequency domain, we used phasor analysis, okay, to understand, the steady state response, Okay.

**[0:45:06]** If circuits... Right. The response to sinusoidal signals add a single frequency. Okay. And then we built upon that to think about that frequency then as a parameter that, we could change, not for a single analysis, but it allowed us to, think about how circuits behaved at different frequencies.

**[0:45:45]** Okay. So circuit response as a function of frequency that led us to the idea of filter circuits and the like, where you want to engineer a particular type of behavior, as a function of frequency. Okay? But that's still pretty limiting. Right?

**[0:46:01]** If you have, for example, a circuit where you have sinusoidal signals at multiple frequencies that are present at the same time, right, then what we've talked about so far doesn't really allow you to do that explicitly if you have non periodic signals, right, then except for very simple cases which you can analyze directly in the time domain, then what we've done doesn't really allow us to treat those kinds of situations either. Alright. So what we wanna do now is to address the question of really how do we understand, okay, circuits that have, in some sense, arbitrary input signals. Okay. Or at least, you know, where the range of possible inputs goes well beyond what we have treated thus far.

**[0:47:05]** Okay. And doing this is what these transform techniques, Laplace and Fourier techniques, will allow us to do. Alright? So the idea then is that these transform techniques, basically, what they give us is a systematic way of going from the time domain to the frequency domain, recognizing that analysis in the frequency domain is going to be a lot simpler because you're trading differential equations in the time domain for algebraic equations in the frequency domain, and therefore, you can treat a much wider range of situations in a mathematically tractable way in the frequency domain, and transform techniques are kind of the key in allowing you to make that transition to the frequency domain. So transfer transform techniques, right, what they do is that they allow us to connect a time domain circuit or a little more precisely, time domain description of a circuit.

**[0:48:23]** Right? So time domain circuit description, for example, a differential equation, alright, we can go from that to the frequency domain. Alright? And in the frequency domain, things are simpler mathematically because you're dealing with algebraic equations rather than differential equations. Okay.

**[0:48:56]** So in the frequency domain, okay, the circuit is described, okay, by algebraic rather than differential equations. Okay. So, so kind of a map, right, of what we are doing here is that... Alright. We have the time domain, and we have the frequency domain.

**[0:49:50]** Okay. And in the time domain, right, the way that we describe the behavior of currents and voltages was essentially using differential equations. Okay? And then under sort of limited circumstances, we could solve those differential equations to get current and voltage, okay, as functions of time. Okay.

**[0:50:26]** So that's what we did, at the beginning of the semester. Right? What we would like to do is to be able to take a description like this here, a differential equation based description, and go from that to the frequency domain. And the transform approach is basically what allows us to do that. So we'll talk first about Laplace transforms, then we will talk about Fourier techniques, Fourier series and Fourier transforms.

**[0:51:04]** Those transform approaches will take us from the time domain to the frequency domain where differential equations become algebraic equations, okay, with frequency as a parameter that appears in those algebraic equations, then, right, they're algebraic equations. We're typically dealing with linear circuits, so we have linear algebraic equations that are very easy to solve. Right? So we can get a solution to the algebraic equations that will give us the current and the voltage, okay, as functions of frequency. Okay?

**[0:51:55]** But, you know, since we live in the time domain, very often what we really want or also want is to have a description of the currents and voltages in the time domains. So that means that we also have to be able to go back. So instead of doing the transform, we need to be able to do the inverse transform. Okay. And that will get us back to the current and the voltage as a function of time.

**[0:52:27]** Now looking at this, you know, it may seem that this is sort of a roundabout way. It's not obvious that this should be easier. But in fact, this approach here, once you get beyond very simple input signals, will generally be much harder. Right? So this is really much harder.

**[0:52:50]** Okay. And going through this process here will be a very powerful approach for treating more complicated situations. Yes. Question. Okay.

**[0:53:02]** So the... We haven't done it in transforms, but the only way we are able to get from time domain to frequency domain previously is if our time domain signal was a very, very specific kind of function, which was a sinusoid. Right. Okay. Yeah.

**[0:53:20]** I... And so, what these techniques allow us to do is to go to the frequency domain for a much broader set of sort of input signals in the circuit and, therefore, signals that are propagating in in the circuit. Okay. So what we will focus on here in class is mostly discussing, you know, basically how you execute transforms and the like and then how they are applied to different types of circuits. Alright?

**[0:53:56]** But in the past, there have often been some questions about, well, you know, how are these things really connected in a more fundamental way, and how can we understand, say, where does... You know, how do you go from, say, phasors to maybe a Fourier series description and from that to to transforms, and how are these really connected to each other in terms of their sort of fundamental mathematical structure? And so what I have also done is a few years ago, I made another recording that talks about that in more detail. Right? So it's basically going from the idea of phasors where you can analyze...

**[0:54:45]** You can figure out what's happening at a single frequency. Right? But then going from there to the idea of Fourier series where one can show, and you may have seen a little bit of this in three zero two or three zero two h, it turns out that any periodic signal can be expressed as a sum of signals at different frequencies that are basically multiples where the frequencies are multiples of some fundamental frequency. And then if you're dealing with linear circuits, then you can use superposition to combine the responses to all those frequencies to get the response to any periodic signal. Alright?

**[0:55:31]** So that's the leap from phasors to, Fourier series, which allow you to treat any periodic signal. And then from there, you can show, and the video will show, how... If you take the Fourier series approach and you extend it to the limit of, essentially, an infinitely long period, then mathematically, that gets you from Fourier series to Fourier transforms. And one of the things that that allows you to do is that if your period is infinitely long, then essentially, you know, you can take your signal to be anything within reason over that infinitely long period. And so, essentially, what you're able to do then is you can, treat the behavior of circuits in response to nonperiodic signals.

**[0:56:21]** Alright? So that's what, Fourier transforms get you and how Fourier transforms are related to Fourier series. And then from there, the video will talk about how, you know, one of the limitations of the Fourier transform approach is that it doesn't allow you to include initial conditions, say things happening at a particular time in a circuit. And, also, it doesn't deal well with situations where you might have a growing signal. Okay?

**[0:56:56]** And so I... That then leads to the idea of Laplace transforms, which involves a generalization of the frequency variable to one that, can be complex. Right? You can have it a real and an imaginary component, and doing that allows you to, as we will see, incorporate both initial conditions into one's treatment and also, allows one to treat certain types of growing signals because you can still get the transform integrals to converge. Okay.

**[0:57:32]** So, this video, which is optional, the active filter circuit videos are not optional. You should look at those. But this integral transform video is optional if you are interested. So that video sort of walks you through that development as I just described. Right?

**[0:57:52]** So you can also see, if you are interested, an optional, video recording. And I'll post all these sometime, hopefully, today, right, on integral transforms. Okay. So, any questions then before we continue? Okay.

**[0:58:25]** So in order to, implement and use, these transfer function, transform functions, one of the things that we need to do is to introduce or, in some cases, revisit some basic mathematical functions and kind of recap or introduce, the corresponding properties of these functions. So we wanna look now at, some key mathematical functions and their properties. Okay. That will come up pretty regularly in the use of these transform techniques. And so the reading for this is in Ulaby et al, and this is in section 12 dash one.

**[0:59:22]** Okay. So, so there are actually really just two of these that we need to introduce right now. One of them is one that we have seen before in the context of switches, and the behavior of switches, that we talked about early in the semester when we were working in the time domain, and that is, what we call the unit step function. Okay. U of t.

**[0:59:50]** Alright. And the unit step function, alright, remember, was a function that is zero for t less than zero, and it is one for t greater than zero. And... Alright. So if we plot it, u of t as a function of time and say, well, I draw t equal to zero here, then the unit step function...

**[1:00:21]** Right. This is zero. This is one. Okay. Then the unit step function, right, it's zero for negative times, and it is one for positive times.

**[1:00:39]** Okay? When we were using this early in the semester, we said that, you know, we were using this for, you know, basically the operation of a switch closing or opening. So we said at that time that the value of the unit step function at t equal to zero was one. Right? So if we were looking at a transition where a switch was closing, then at t equal to zero, the switch was closed.

**[1:01:06]** Okay? So so that is common but not universal. Right? So depending on the circumstance, sometimes, right, u at t equal to zero, can be defined as having a value of zero or sometimes one half or one, right, depending on the circumstances. Okay.

**[1:01:41]** But if it matters, we'll generally try to be clear about, you know, how exactly we're defining it. And and there are a lot of circumstances where, you know, it matters in terms of making the mathematics more rigorous, but practically speaking, it doesn't matter so much. Okay. So that's the unit step function. Alright?

**[1:02:01]** Oops. Now if we look at this function, then one of the questions that may naturally arise, and, you know, would definitely arise, for example, if we were looking at, say, this unit step function is being maybe a voltage applied to a capacitor. Right? One of the questions is, well, what is the derivative of this function? And, especially, what is the derivative of this function at t equal to zero?

**[1:02:35]** Right? For t not equal to zero, it's easy. The derivative is zero. But, at t equal to zero, it's less clear, what that derivative should be. So that brings us to what we call the unit impulse or sometimes what's called the delta function.

**[1:03:04]** Okay? And the symbol for this is the Greek letter delta, lowercase delta of t. Okay? And the unit impulse or delta function, delta of t, is defined to be a function that is zero whenever the time is not equal to zero and infinite at t equal to zero with the additional condition that the integral from minus infinity to infinity of the delta function is equal to one. Okay.

**[1:03:53]** And so, right, if we try to sketch this out, alright, we're looking at delta of t as a function of t at t equal to zero, then, right, this is going to be a function that is zero everywhere except at t equal to zero. And at t equal to zero, it becomes infinite in such a way that its integral is one. Okay? So, you know, so it's sort of unintuitive what this... What the nature of this function really is.

**[1:04:35]** And so one way that can be helpful in thinking about it is to define... You know, in addition to the delta function having these properties, we can also think of the delta function as being, sort of the limit of a function that has some peak, say, a Gaussian function. Right? We can take the delta function to be the limit of that type of function as the width of the function goes to zero. Alright.

**[1:05:09]** So a very narrow Gaussian. And the amplitude, the peak value goes to infinity, but in such a way that the integral, is one or remains finite. Okay? And so there are a variety of ways that one can do that. One of them that is quite common is that you can say the delta function, delta of t.

**[1:05:35]** We can take it to be the limit as some parameter a goes to zero of one over the absolute value of a times the square root of pi times the exponential of minus t over a, the quantity squared. Okay. So this is, you know, exactly what I was describing. It's a Gaussian peak. Right?

**[1:06:01]** Because it goes as e to the minus t over a, the quantity squared. But if you take the limit of a going to zero, then at t equal to zero, it becomes infinite because of this absolute value of a in the denominator, and, also, it becomes, it has zero width because of this a in the denominator of the exponent. Okay? But if you calculate the integral of this from minus infinity to infinity, then what you get is that the integral of this is one independent of a. Okay?

**[1:06:42]** So when you take this limit, then the integral remains as one, but it becomes infinitely narrow and infinitely high. Okay. So that's, you know, one way of thinking about the nature of this, delta or impulse function. Okay. And then we can also notice, right, that because of this integral property over here, then, if we were to take to take...

**[1:07:16]** Bless you. If we were to take the integral from minus infinity to... And take the upper limit to be, some negative time, right, that integral would be zero. Right? But then, if the upper limit to be...

**[1:07:30]** Were to be some positive time, the integral would be one. Okay. So looking at it that way, we can see that the unit step function, u of t, is going to be the integral from minus infinity to the time t delta of t prime d t prime, right, where t prime is the variable of integration. Right? So if t is less than zero, this integral is zero.

**[1:08:00]** If t is greater than zero, then this integral is one. Alright? And then if you take the derivative of both sides of this, then what you get on the left is the derivative with respect to time of u at t of t. And then on the right hand side where you're taking the derivative of an integral, so you just get the integrand itself, delta of t. Alright?

**[1:08:30]** So, so then what we see here is that this, unit impulse or delta function is indeed the derivative of the unit step function. Okay? And that's what... Or it's one of the things that makes it useful in... When we're using transform techniques more generally.

**[1:08:50]** So any questions then to hear? Yes? And what t prime is and why... What would be the derivative of u of t prime? Oh, so t prime here is just the variable of integration.

**[1:09:02]** Right? So we could easily... We could equally well have said, well, this is the integral from minus infinity to t of delta of, you know, x d x. Right? It's just the variable of integration as opposed to t prime, the derivative of t.

**[1:09:20]** Alright? And then this t over here, the upper limit of integration is the same as this time here. Okay? And then, right, when you take the derivative of this, then it's the integrand evaluated at this limit of integration. Okay.

**[1:09:37]** And that's how you get this. Okay. Okay. Is is that what you're asking? Yes.

**[1:09:42]** Okay. Yes. Right. Okay. Any other questions to hear?

**[1:09:52]** Okay. Now very often when we are using this delta or impulse function, it'll come up in a context where it's being multiplied by some other function. Alright? So from what we've defined so far, right, we can also see that, right, if some other function, we'll call it x of t, right, is a continuous function of time t, right, then we can say the following things. If we have x of t times delta of t, right, that's gonna be the same as x evaluated zero times delta of t.

**[1:10:48]** Right? Because the delta function is zero for all values of t less than... Or other than zero. Okay? And then corresponding to that, we can just do a shift in time, x of t times delta of t minus some time capital t is x of capital t times delta of t minus capital t.

**[1:11:14]** And then this property here, then if we just integrate both sides of this, right, we'll have the integral from minus infinity to infinity of x of t times delta of t minus capital t dt. And then on the right hand side, if we integrate that from t equal to minus infinity to infinity, then we're just going to get x of t. Right? So, taking some function, multiplying it by the delta function, and integrating it basically just picks out the value of that function at the time when the delta function is nonzero. And this is sometimes referred to as the sampling property of delta of t.

**[1:12:11]** Right? Because it's basically sampling the value of the function by which it's multiplied at a particular time. Right? The time when the delta function is nonzero. So any questions to hear?

**[1:12:28]** Okay. So, with those kind of mathematical preliminaries, then that brings us to the Laplace transform itself. Okay. And the reading for this is in Ulaby et al, and it's section 12 dash two. Okay?

**[1:12:59]** So I'm just going to give you the definition of, the Laplace transform. Right? So this is going to be a mathematical operation that we perform on some function of time, okay, to bring... To make it, into a function of, some other variable that we interpret as the frequency. Okay.

**[1:13:19]** So the idea is that given a function of time, alright, we'll call it f of t, then it's Laplace transform. Okay. We call that function capital f, and it'll be a function of some other variable s, which will turn out to be a complex version of the frequency, that Laplace transform, we also write it as the Laplace transform operator. We'll write it as a script l. So it's the Laplace transform operator operating on f of t.

**[1:14:09]** And the way that we define the Laplace transform is that f of s, which is the Laplace transform of f of t, it is the integral from zero minus, right, meaning the sort of the left hand side of zero to infinity of our function of time f of t times e to the minus s t dt. Alright? And since we're not integrating over s, then this integral will be a function of s, and that function of s is the Laplace transform. Okay. And this variable s, right, it is a complex variable.

**[1:15:09]** So it has a real part that we call sigma, a regulator sigma, and then it has an imaginary part, so plus j times the imaginary part omega. Right? And so sigma and omega are both real. Right? So s is a complex variable.

**[1:15:39]** Alright? And it's often called the complex frequency. Okay. And omega here, as we will see, is, the same omega as we have been dealing with, you know, just the the regular frequency that, you know, we're very familiar with already. And then this notation here where we take the lower limit of integration to be zero minus.

**[1:16:12]** Right? Right? Basically, that's just explicitly reminding us. It's not universally used, but we will sort of use that notation here. It's just reminding us that the integral can include some initial condition at t equal to zero.

**[1:16:26]** Okay. So the zero minus lower limit of integration I indicates that the integral can include an initial condition at t equals zero. And that's how initial conditions come into play, when we use Laplace transforms. So any questions to hear? Okay.

**[1:17:14]** If not, then, we will stop here for today, and we'll pick up with this discussion of, Laplace transforms and also inverse Laplace transforms in our, like, next class meeting on Wednesday. And so I will now stop the recording.
