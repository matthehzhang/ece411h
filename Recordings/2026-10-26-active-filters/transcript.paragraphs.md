# 2026-10-26-active-filters

Deepgram general-nova-3 2025-07-31.0, request 01a1b010-8f29-7653-a71f-ad2add9e5c08, audio 80.8 min.

**[0:00:03]** Okay. Let's go ahead and get started. So I have started the recording, as usual, and there are just a few announcements. The first one is just a reminder about the, seventh problem set. Okay?

**[0:00:16]** So that's due a week from today. That's Monday, November 2. And then, later this week, on Wednesday, I'll post, the eighth problem set. Okay? And that'll be due in two weeks from today on Monday, November 9.

**[0:00:34]** Okay? And the eighth problem set will be mostly on passive and active filter circuits. And then just a heads up that in about two and a half weeks, we will have the second semester exam coming up. Okay? So that'll be the last exam before the final.

**[0:00:51]** That'll be on November 11. That's a Wednesday, and I'll post more detailed information on that probably later this week. Okay. So any questions on, any of that? Okay.

**[0:01:06]** Any questions from our last class meeting? Okay. If not, then we'll pick up from where we left off. So what we were discussing last time was this bandpass RLC filter. Okay?

**[0:01:22]** So this circuit over here where v sub s is the input voltage, v sub r, is the output voltage, and essentially, we just have, an RLC series circuit here. And we're taking the output to be the voltage across the resistor, And what we worked out at the very end of our last class meeting was that the transfer function for this particular circuit is given by these expressions over here. Alright? And that can be quite easily calculated using just voltage division. Okay.

**[0:01:57]** So any questions on how we got to this point last time? Okay. So if we take that expression or or these expressions for the transfer function, remember what we typically wanna do is to work out explicitly what the magnitude and phase of the transfer function are. So for the magnitude of the transfer function... Alright.

**[0:02:24]** So that's just taking the magnitude of what we just worked out. Then, right, the easiest way to get that is to take, say, this form for the transfer function over here and calculate the magnitude of the numerator divided by the magnitude of the denominator. Alright? So for the numerator, the magnitude is just omega RC, And then for the denominator, the magnitude is going to be, the square root of the real part squared, plus the imaginary part squared. So we're gonna have the square root of the quantity one minus omega squared l c squared plus, omega squared r squared c squared, all of that under the square root.

**[0:03:16]** Okay. So that is the, the magnitude. Alright? And for the phase, here, the easiest thing to do is, to look at this form for the transfer function over here and then take the phase to be the inverse tangent of the imaginary part divided by the real part, right, which is what we what we typically do. So the phase of this transfer function is the inverse tangent of...

**[0:03:52]** And then when we take the imaginary part, right, the denominator here is real. Okay? So we don't have to worry about that when we take the ratio of the real... Of the imaginary part to the real part. When we take the imaginary part over here, and the real part over here, and we compute that quotient, there will be one factor of basically omega r c, right, that cancels out because we have omega squared r squared c squared here and omega r c over here.

**[0:04:20]** So one factor of omega r c will cancel out, and so we just have the inverse tangent of one minus omega squared l c over, omega r c. Okay. And those are, the magnitude and phase of the transfer function. Okay. So any questions on how we did that?

**[0:04:42]** Okay. You know, one thing you might think about is if you had tried to calculate the phase from, over here, taking the phase of the numerator minus the phase of the denominator, it would actually be a little bit trickier trickier. Okay? And so you can think about, why that is. And, later on today, we'll see an example of, you know, why that ended up turning out to be, to be trickier.

**[0:05:10]** Right now, you can just, think about it a little bit. Okay? The other thing that we can notice is that, if we look... Let me get rid of that box there. Okay.

**[0:05:29]** If you look at the overall circuit over here, remember, last time, we talked about this idea of a resonant frequency. Okay? And we said that the resonant frequency generally would be the frequency at which the input impedance. Okay? So, basically, the Thevenin equivalent impedance between the input terminals, if the imaginary parts all canceled out, right, so that it was purely real, then, that would generally behave as the resonant frequency, for the circuit.

**[0:06:07]** And if we look at this circuit over here, then we can see that there will be a frequency at which the impedance of the inductor and the impedance of the capacitor, will cancel each other out. Right? And that will occur when, omega times l, is equal to one over omega times c, right, at that frequency. Okay. So, we will have a resonant frequency for this circuit.

**[0:06:42]** Alright. We'll call it omega naught, and, that condition that I just described will give a res... A resonant frequency of one over the square root of l times c. Alright? And that happens because that's the frequency at which omega l is equal to one over omega c.

**[0:07:05]** And when that condition is satisfied, that means that the impedance of the inductor and the impedance of the capacitor, they will cancel out. Right. So this happens when the frequency is equal to this resonant frequency omega naught. Okay. So any questions?

**[0:07:27]** Okay. So what we wanna do now is to sketch out, not make the Bode plots yet, but do a slightly better sketch of the magnitude and the phase as a function of frequency. Okay? So if we look at the magnitude first, alright, we can see that for very low frequencies, right, as omega goes to zero, what does the magnitude of this transfer function go to? Zero.

**[0:08:04]** Right. Because of the omega in the in the numerator. Alright? As omega goes to infinity, what does the magnitude of the transfer function go to? Yes.

**[0:08:21]** Right. And then as omega becomes very large, then that will go to zero. Right. Okay. At the resonant frequency, what is the value of the magnitude?

**[0:08:38]** Yes. It's one. Right? Because, at the resonant frequency, one over root LC, then this term in the denominator goes to zero. And so we have omega RC over the square root of omega squared r squared c squared, and this...

**[0:08:56]** That square root is just omega RC. So these cancel out, and we have one. Okay. So looking at those three circumstances then tells us that... Alright.

**[0:09:12]** If we plot out the transfer function, right, it's gonna go from zero to one. Alright? We're plotting it as a function of frequency omega. And what happens then is that at the resonant frequency omega naught... I'll do this in green here.

**[0:09:36]** Alright? The magnitude goes to one. And then from there, as we go to zero frequency, the transfer function magnitude goes to zero. And as we go to high frequency, right, it'll go to zero as well. Okay.

**[0:10:00]** So that is the magnitude of the transfer function. If we look at the phase, okay, which is given by this expression over here, as omega goes to zero, then what is the phase going to be? Right. It's 90 degrees because we have one over, basically, omega RC, and that's going to go to infinity, and the inverse tangent of, infinity is 90 degrees. Okay.

**[0:10:36]** What about if omega goes to, infinity? Yes. Negative 90 degrees. Right? Because it'll be the inverse tangent of, minus infinity, and so that's minus 90 degrees.

**[0:11:01]** And then at the resonant frequency, we're going to have the inverse tangent of zero. Right? Because the because the numerator is gonna go to zero, and the inverse tangent of zero is zero. Alright. So for the phase...

**[0:11:21]** Right now we're plotting, the phase as a function of omega. We'll put omega nod here. We'll go from 90 degrees to minus 90 degrees. Okay. And then, what this is gonna look like is, right, it'll start off at 90 degrees, come down through zero at omega naught, and then go to, asymptotically to minus 90 degrees.

**[0:11:55]** Okay. So, so that's what the transfer function phase looks like. Okay? Now if we come back to the magnitude, right, we can see, you know, clearly, is a bandpass filter. And so, what we also wanna do is to figure out what the corner or cutoff frequencies are.

**[0:12:16]** Alright? And there will be two. And they will, occur when the magnitude, is equal to one over root two, and we'll call those, cutoff frequencies. We'll call this omega c one and omega c two. Okay.

**[0:12:41]** I... And then the difference between them is the bandwidth b of this bandpass filter. Okay. So what we wanna do then is to calculate what these cutoff frequencies are, and then from that, what the bandwidth will be just by taking their difference. Okay.

**[0:13:01]** So any questions before we do that? Okay. So so the condition that we have to satisfy is that, right, the magnitude of the transfer function in omega c one and at omega c two, those magnitudes have to be one over root two. Alright? And so what we do then is we just go back to this expression here, and when omega is equal to either one of these cutoff frequencies, then this expression here has to be equal to one over root two.

**[0:13:40]** Okay. So what this condition implies then is that omega... We'll call it c sub I. Right? And I can be either one or two.

**[0:13:52]** So omega c sub I times r times c divided by the square root of one minus omega c sub I squared I l c squared plus omega c sub I squared r squared c squared. Right? This whole thing has to be equal to one over root two. Okay. And then, right, we can take this, and we can make it a little bit simpler by dividing the numerator and the denominator by omega c I times r times c.

**[0:14:32]** Right? Then we'll have one in the numerator, and then this second term under the square root will become one as well. Alright? So, if we do that, what we get is that one over the square root of... Now it's going to be one minus omega c I squared l c over omega c I r c.

**[0:14:58]** That quantity squared plus one, all under the square root, has to be equal to one over root two. And that simplifies it because it tells us that this quantity here is squared. This first term under the square root has to be equal to one. Okay? And so what we get is that one minus omega c I squared times l times c has to be equal to plus or minus omega c I times r times c.

**[0:15:32]** Alright? So all we did was we said this term here equal to one, and then when we take the square root, we get this plus or minus over here. Yes. This specific case, there was very convenient, mathematical operations we could do to remove much of this and and get it in this form. Will most of our transfer functions be so kind or no?

**[0:15:58]** Well, it'll depend on the circuit. And, you know, if if you're kind of thinking in the back of your mind, well, what if it's not so simple on an exam? Then, you know, before we actually give the exam, we work through the problems, alright, to make sure that, you know, they're, doable in the time for the exam. So, you know, so in this case, it worked out to be relatively simple. You know, it...

**[0:16:26]** On an exam, it won't it won't be kind of arbitrarily complicated, but, you know, we'll try to find, you know, the right balance between complexity and simplicity such that it can be done in the context of an exam. Any other questions? Okay. So so once we're at this point, then, right, basically, we can see this is just a quadratic equation for the frequency. So we can just solve that quadratic equation, and that will give us the cutoff frequencies.

**[0:17:00]** Alright? So writing this in the usual form for a quadratic equation, so we're gonna move these two terms here to the right hand side. So we're gonna get l times c times omega c I squared plus or minus r times c times omega c I minus one is equal to zero. Okay. So so that's our quadratic equation, and we can just solve it for omega c I, using the quadratic formula.

**[0:17:34]** And so that'll give us one over two l c times I, and then it's minus or plus r times c. Right? Because it's, the negative of the coefficient of the linear term, plus or minus the square root of r times c, the quantity squared, plus or l c. Alright. So that's just using the, quadratic formula.

**[0:18:03]** And if we multiply through by this one over two l c, then what we get is that this is going to be equal to minus or plus r over two l, plus or minus the square root of r over two l quantity squared plus one over LC. Okay. And that's the result. But what you can see here is that, you know, we... There are actually four possible solutions that have come, to us from here.

**[0:18:47]** Right? Because there are two options for the sign here and two options for the sign here, and they're independent from each other. Okay? So we actually have four solutions here. And the way that we get out of that is that we recognize that, right, if we come back, say, up here, right, that these cutoff frequencies have to be positive.

**[0:19:09]** Okay? And so what we wanna do is to pick, among those four solutions, the two that are positive. Okay? And the two that are positive correspond to taking the plus sign over here, and then this can be either the minus or the plus. Alright?

**[0:19:31]** So, from among these four solutions, we wanna select the two solutions for which this cutoff frequency is positive. And then, right, in labeling them, we want, oops, omega c one to be less than omega c two. Okay. Because that's how we label them in, in the plot. So that means that omega c one, right, is going to be that square root term.

**[0:20:12]** So root r over two l quantity squared plus one over l c minus r over two l, and omega c two is equal to root r over two l, the quantity squared plus one over LC, plus r over two l. Okay. So these are, the, the cutoff frequencies for this bandpass filter. Okay. So any questions on how we got to this?

**[0:20:50]** Okay. So if we look at this, one of the things that, we can also calculate from these cutoff frequencies is the bandwidth. Right? Because the bandwidth is just the difference between the cutoff frequencies. Right?

**[0:21:05]** So it's kind of the range of frequencies. It's the width of the range of frequencies that are passed by the filter. And the bandwidth is actually much simpler than what we calculated over here because when we take the difference, this square root term will cancel out. Right? So the bandwidth, which is omega c two minus omega c one, is just equal to r over l.

**[0:21:34]** Right? Because it's r over two l, minus negative r over two l. So that's just r over l. Okay. So that's the bandwidth.

**[0:21:41]** Alright? And so one of the things that we see here is is that if the resistance is small, the bandwidth is very narrow. Right? So it can be... This bandpass filter can be very selective in picking out a particular range of frequencies.

**[0:22:02]** If the resistance is large, then then what'll happen is that the bandwidth is large, so it'll pick out a wide range of frequencies. Okay? Now one of the other consequences of having resistance in the circuit and of the size of the resistance is that the size of the resistor influences how much energy, how much power is dissipated. Alright? Because if you have resistor, inductor, and capacitor, only the resistor is going to be dissipating power.

**[0:22:36]** And so, you know, one of the things that suggests is that if you have this kind of filter circuit, a bandpass filter circuit, then if it dissipates very little power, then perhaps in some way that corresponds to having a very narrow bandwidth. Right? Being very selective in picking out a particular frequency. And, it turns out that that correlation is true under quite general circumstances, and it brings us to this idea of what is called the quality factor, which we call q. Alright?

**[0:23:24]** And so the quality factor, which is a parameter that applies actually to any resonant circuit, okay, and and and particularly to the resonant part of the circuit, what the quality factor is is... Or what it does is that it quantifies... Okay. I... In the context of filter circuits, it quantifies the degree of frequency selectivity.

**[0:24:04]** Okay, of a circuit. And it's related in a pretty fundamental way to the ratio of stored, okay, to dissipated energy in a resonant circuit. Right? So remember that energy can be stored in the reactive components, the inductor and the capacitor, and then it'll be dissipated in, the resistive component. Alright?

**[0:24:46]** And the way that we define the quality factor is that it's equal to two pi times the energy stored. We'll call that w store divided by the energy dissipated in a single cycle of oscillation of the circuit, and this is evaluated at the resonant frequency. Okay? So these parameters here, the energy stored, this is actually... It's the maximum.

**[0:25:29]** Energy that's stored, at the resonant frequency. Okay. And then the denominator, the energy dissipated, this is specifically... It is the energy that is dissipated, okay, during one period of oscillation, okay, where at period t, right, it's two pi over omega naught. Okay.

**[0:26:06]** So so this idea of the quality factor is something that applies to, any kind of resonant circuit or resonant system, alright, where, you can... You have some part of the circuit that can store energy and will also dissipate some energy. And it is it is the ratio of the stored energy, the maximum stored energy, to the energy that is dissipated in one cycle. Yes. Question?

**[0:26:39]** We have seen it as defined by having no imaginary part and only real resistance, then what if the maximum energy stored at w equals w zero b zero? Because at that frequency, it's purely real. At the resonant frequency, it's purely real. Right? Well, so the impedance is real, but that does not mean that there's no energy that is stored in in those components.

**[0:27:10]** Alright? And in particular, right, the energy is gonna go back and forth between the inductor and the capacitor. And so, right. So so there will still be energy stored, in that circumstance. But then if the resistance is very low, then the energy dissipated will be very small.

**[0:27:35]** Okay? So that'll make the denominator here small. Alright? And so I... You know, one of the things that that kind of tells you is that if you want to have a resonator with a very high quality factor, which means it's very efficient at storing energy and also does that over a very narrow range of frequencies, and that can be very desirable for...

**[0:28:02]** You know, if you wanna have a very fine, frequency filter, what you want is to make the loss as low as possible. Okay? In the case of a circuit, the loss is associated with the resistance. Okay. So does that answer your question?

**[0:28:16]** Overall, the the impedance of the whole of the whole filter is real. However, the components inside still have... Are still stored energy. Right. Yes.

**[0:28:26]** So they cancel out. Okay. Any other questions? Yes. Does it make sense to talk about resonant for a circuit that does not contain both inductor and capacitor?

**[0:28:41]** If you don't have, both an inductor and a capacitor, then, the behavior that you will get in the circuit will will basically... And we saw this kind of in the first order circuits that we talked about earlier in the course. It'll always be something that's exponentially decaying. And, you won't be able to get a structure where you can have energy stored that's just kind of oscillating back and forth between the different, components. So then you can't do a quality factor for, like, a real capacitor, I guess.

**[0:29:16]** I... Yeah. So if you just have a capacitor or, you know, say a capacitor in series with a resistor, then I... Yes. You you wouldn't have a, well, you could sort of get a a quality factor if you had an underdamped.

**[0:29:35]** Well, actually, I guess you don't get that in the first order behavior either. So, yeah, so you don't really get a quality factor, if you have, say, just the capacitor or, you know, an RC circuit or an RL circuit. In order to talk about the quality factor, really, you have to have something that has this kind of resonant behavior. Okay? And and it actually comes up in, many different contexts because resonators, are...

**[0:30:05]** Or can be important for a variety of their functionalities. Does that answer your question? Yeah. Just interesting because I I don't know. I've done a decent amount of, like, quality factor of, like, a real life, you know, faster.

**[0:30:20]** And so I was just wondering, you know, what's... What we're doing then, you know, if it doesn't really make as much sense to the quality factor over the past one. Yeah. So quality factor really applies specifically to something that has this resonant behavior. So there may have been something somewhere else, right, that was giving rise to that type of resonant behavior, and then it would make sense to talk about a quality factor.

**[0:30:46]** But if you just had, like... You know, when you strip away everything else, if it's just a capacitor or capacitor plus a resistor, then that by itself will not give you this kind of resonant behavior. Okay. But, you know, it could be that, you know, there's always some parasitic around, or it could be that it's embedded into some larger system which does have this resonant behavior. And then, yeah, then it would be necessary to look at the details of it.

**[0:31:17]** Okay. Any other questions? Okay. So so I won't go through the detailed derivation of this, but it's in the book if you're interested. So it turns out that one can show, and this is in...

**[0:31:39]** You'll be at all, and it's section nine dash four dash one. Okay? That specifically if you have... What they show is specifically for the RLC series circuit. But it applies more generally to resonant structures as well, you can show that the quality factor in the case of the RLC series circuit is equal to omega naught, the resonant frequency times l over r.

**[0:32:19]** Okay? And if you compare that to the expression that we worked out for the bandwidth with, which is r over l, then this is just equal to omega naught over the bandwidth. Okay? And so... Alright.

**[0:32:47]** The key and sort of particularly interesting part of this relationship is the quality factor being inversely proportional to the bandwidth. And that turns out to be something that is, very generally true of, resonant systems in general, alright, that the high quality factor or having a high quality factor q is related in a quite fundamental way to having a narrow bandwidth b. Okay? And this is true really under quite general circumstances. Okay?

**[0:33:41]** And as you move forward in your educations, you'll probably see things like this coming up in a variety of circumstances. And, you know, particularly for things like communications applications and the like where very often you wanna pick out, they are a range of frequencies, then making resonant structures that have high quality factors, that is low loss, you know, is is an important way of of being able to do that. Okay. So what we'll do next is we'll go back to the original transfer function, and we'll see, how we construct the Bode plot for that from the constituent factors that contribute to, the transfer functions. Are there any other questions before we go ahead with that?

**[0:34:30]** Okay. So now what we wanna do is to look at the Bode plots for the bandpass filter. Okay. So remember, the transfer function is j omega RC divided by one minus omega squared LC plus j omega r c. And so what we wanna do is to, split this transfer function up into, constituent factors that correspond to kind of these fundamental elements of the transfer function that we discussed, last time.

**[0:35:16]** Okay? So if we do that, right, what we can see is that there's a constant factor, r c. There is a zero at the origin factor, j omega. And then there is a quadratic pole, which is one over one plus j omega RC minus omega squared LC. Okay.

**[0:35:46]** So these are our constituent factors. We'll call this one, a one, this one, a two, and this one, a three. Okay? And so splitting it up, in this way, you know, makes it clear that the transfer function has a zero at the origin. Alright.

**[0:36:15]** A simple zero, and it has a quadratic pole. Okay. And the pole is at a pole frequency omega p, which is one over root LC. Right? We, can deduce that because we know that this this quadratic term over here alright, it has to be of the form, right, j omega over omega p squared.

**[0:36:55]** Right? So from that, we can deduce that, the pole frequency is, one over root LC, which is equal to the resonant frequency of, of the circuit. Okay. So so we have these three factors that contribute to the transfer function, and so what we wanna do is to see how how we construct the Bode plots for each of these individual factors, and then from then, how we combine them to get the Bode plot for this transfer function as a whole. Okay.

**[0:37:32]** So any questions before we do that? Okay. So so the idea then is that to get the Bode plot... Okay. For the complete transfer function h of omega, what we wanna do is to construct the plots for the individual factors.

**[0:38:03]** Right? A sub I of omega. Right? And then combine them just by adding them together. Okay.

**[0:38:15]** I... And that works. I remember as we talked about last last time. Right? This works.

**[0:38:25]** Basically because, when we're looking at the magnitude, right, we know that the magnitude we're going to plot on a log scale. Alright? So when we have multiple factors on a log scale, we can just add them together because the log of a product is the sum of the logs. Alright? So it works for the magnitude because the magnitude is plotted on a log scale.

**[0:38:56]** And then for the phase, it works it works because the phase appears in, an exponent in each factor. Okay. So when we multiply the phase factors together, then that corresponds to adding, the phases together. Okay. So if we look at these individual factors and, what the corresponding Bode plots are.

**[0:39:30]** Alright. Let's look first at a one, which is the constant factor, right, r times c. So for the magnitude, right, this is gonna be on a dB scale. Right? Alright.

**[0:39:50]** Typically, what will happen is that if you think about typical values for resistor and typical values for a capacitor, then, the resistance times the times the capacitance is generally going to be, you know, in the appropriate units, it's gonna be less than one. Right? Because the resistor, right, you know, maybe one kilo ohm is a typical, value. In a capacitor, one microfarad, right, might be a typical value. So that's gonna be less than one.

**[0:40:22]** So what we will do is we'll, sort of suggest that by drawing the magnitude down here like this. Okay? And it's independent of frequency. Alright? And then for the phase, right, r times c is always going to be positive, so the phase will be zero.

**[0:40:44]** Okay. So we plot the phase as a function of omega, then, that's just going to be here like this. Okay. And that's a phase of zero degrees. Okay.

**[0:41:02]** So that is for the constant factor. Alright? Next, right, what we called a two was the simple zero at the origin. Right? Just j times omega.

**[0:41:16]** Okay. And so for that, when we look at the magnitude in dB... Alright. Remember we said that for a simple zero, at the origin, then, there's no inherent frequency scale to that. So, add a frequency of one, right, then when we take the log, that's gonna give us zero.

**[0:41:48]** So it'll be zero dB, and, we will just have a straight line like this, and the slope here will be 20, oops, 20 dB per decade. Alright. So for every factor of 10 change in, the frequency, we get a 20 dB change, in the, the value of this factor in the transfer function. Okay. And then if we look at the phase, alright, this factor was j times omega.

**[0:42:34]** Alright? So the phase of that is just going to be the phase of j, which is 90 degrees. Okay. Yeah. Question?

**[0:42:41]** Well, box in general, does the y axis... Because, obviously, as as you get closer, it'll never be zero. Like, the the omega will never be zero because it's plotted as a decades. Yes. Right.

**[0:42:55]** So what happens as you draw the line closer to zero? Should we just stop at a certain point? And Oh, yeah. So so this, right, the vertical axis that we've drawn is not at zero frequency. Right?

**[0:43:12]** It's it's at some presumably small frequency, that's in the range that we approximate in the Bode plots as being, the zero frequency behavior. So, yeah, so if you're drawing this on a problem set or an exam or something like that, and you have omega on a log scale, you can draw it, you know, pretty much like it's been drawn, here as, you know, as we'll see in in other examples. You know? And and it's sort of understood, and hopefully everyone who does this will understand that, that vertical axis is not going through omega equal to zero. It's going through some small value of omega.

**[0:43:50]** Okay. So then for the phase... Okay. We know that the phase of j is 90 degrees. Okay.

**[0:44:09]** So the phase is just gonna look like that, and it's also going to be independent of frequency. Okay. And then the last factor is the quadratic pole, a three of omega. Alright? And for that...

**[0:44:38]** Alright. Where if we look at the magnitude on the dB scale as a function of omega, right, for the pole, alright, we know that, omega p or... Which is equal to omega naught, okay, is, sort of the key dividing line. And if we go back to here, right, if we look at this quadratic pole factor over here, then we know that as omega goes to zero or more... Or in the case of the Bode plot, if we take omega being less than omega p, right, it will have the limit...

**[0:45:23]** The... It'll... We will plot it as if it has whatever the limiting behavior is as omega goes to zero. And as omega goes to zero, this factor goes to one. Alright?

**[0:45:35]** So one on log scale is zero dB. Okay. And then as omega goes to infinity, alright, what will happen here is that this quadratic pole factor will go as one over minus omega squared l c. Okay? So for every factor of 10 change in omega, then this factor here will decrease by a factor of a 100.

**[0:46:06]** Right? Because it's omega squared. And so that is 40 dB per decade. Right? If it decreased by a factor of 10, every time omega increased by a factor of 10, that would be 20 dB per decade.

**[0:46:19]** But it's decreasing by a factor of a 100, so that's 40 dB per decade. Okay. So... And what we do in the Bode plot is for all frequencies above, the pole frequency, which is omega naught here, then we assume that, and we, or we approximate that, this factor will behave as if it has its limiting behavior for omega going to infinity. So what the resulting Bode magnitude plot looks like for the quadratic zero is that for omega less than omega naught, it's flat, and then it decreases for omega greater than omega naught, at minus 40 dB per decade.

**[0:47:14]** Okay. And then for the phase, okay, what happens is that... Alright. If we plot the phase, okay, as a function of omega, okay, we're gonna have point one omega naught, omega naught, and 10 omega naught. Okay.

**[0:47:44]** If we go back to... Alright. This expression here, for very low frequencies, then this quadratic pole factor is just gonna... It's gonna go to one, so the phase of that is gonna be zero. If we are at the resonant frequency, which is omega equal to one over root LC, then this one here and this minus omega squared LC will cancel out, and so we'll just have j omega RC in the denominator.

**[0:48:22]** The phase of that is minus 90 degrees. Right? And then as omega goes to infinity, then this is gonna look like one over minus omega squared l c. So it'll... Its phase will be determined by it'll be the phase of minus one, which in this case, we can take to be, minus a 180 degrees.

**[0:48:44]** Okay? And if we plot that out... Right? So we have zero degrees, minus 90 degrees minus a 180 degrees. Okay.

**[0:49:00]** And if we plot that out, right, what we have is below point one omega naught, It has the low frequency behavior, zero degrees. Above 10 omega naught, it has the high frequency behavior, so minus a 180 degrees, and it's 90 degrees at omega naught. And so the Bode plot will look like this. Okay. So now here, we have these three plots, Bode plots for each of the constituent factors, and then to get the Bode plot for...

**[0:49:41]** Or the Bode plots for the transfer function as a whole, then what we wanna do is to add the individual Bode plots together. Right? And that'll give us the whole thing. Okay. So if we do that...

**[0:49:57]** Oops. Alright. So we're gonna put these together, and we're gonna get... From doing so, the Bode plot... Bode plots for, the entire transfer function.

**[0:50:14]** Okay. So for the magnitude, okay, as a function of omega... Alright. We're gonna have omega naught here. And, what's gonna happen is if we look at, alright, these three factors together, right, if we are below omega naught, okay, we have, constants, like a horizontal, Bode plot here, and then we...

**[0:50:52]** And and also horizontal Bode plot down here, and then we have one factor that gives us an upward slope of 20 dB per decade. Okay? So when we add these together, we're going to get, a plot for omega less than omega naught that is just an upward, sloping line with a slope of 20 dB per decade, right, that we get from here. Because when we add lines... Line plots, then we can just add the slopes.

**[0:51:19]** Alright? And then the other thing that we can see is that at omega naught... Alright. Remember we saw way back here at omega naught, the magnitude of the transfer function is one. Alright?

**[0:51:41]** So, when we take the log of that, that is going to be zero, zero dB. Okay. So if we call this line here zero dB, then what we get for omega less than omega naught is just a line like this that has a slope of plus 20 dB per decade. Okay. Now if we go to the other range of frequencies, omega greater than omega naught, right, then we can see that we have a horizontal, Bode plot over here, a line that's sloping upward at plus 20 dB per decade, and then here, a line that's sloping downward at minus 40 dB per decade.

**[0:52:41]** So when we add these three together, we're gonna get a downward sloping line with a slope of minus 20 dB per decade. Alright? Because, again, we just add the slopes. So we get this over here, alright, that has a slope of minus 20 dB per decade. And that is the, Bode magnitude plot.

**[0:53:10]** Okay? And we can see here that, you know, if you if you look at this, then you can see that, yes, indeed, this also shows that the functionality we have is a bandpass filter, alright, with the maximum at omega equal to omega naught. Okay. So any questions on how we got the magnitude Bode plot before we move on to the phase? Yes.

**[0:53:35]** The constant term, it doesn't contribute to the slopes, but it contributes to the value of the magnitude. Right? Say, it moves it up and down on the plot. And so, you know, the way that we thought it... Yeah.

**[0:53:58]** So so we took a little shortcut, right, and went to the original transfer function and realized that, okay, at omega naught, it has a value of one. So So it didn't... Is set up a way of doing it. I guess that would be good if I'm just, like, purely adding the loading plus. Oh, then, you would actually have to, you know, plug in numerical values, I guess, and then...

**[0:54:22]** Or by some other method deduce that, you know, what the overall scale factor is. And that that overall scale factor gives you a magnitude of one at the resonant frequency, okay, which is... That's sort of what we did anyway. But, we just... Since we did it earlier, we borrowed that result from earlier.

**[0:54:46]** Any other questions? Okay. So then for the phase, right? Now we're gonna be plotting... Oops.

**[0:55:02]** Okay. The phase as a function of frequency, and we'll label point one omega naught, omega naught, and omega naught. Alright? And if we go back to our phase plots over here, right, we can see that for omega less than point one omega naught, we have zero plus 90 degrees plus zero, so it'll be 90 degrees. And then for omega greater than 10 omega naught, we have zero plus 90 degrees minus a 180 degrees, so that's minus 90 degrees.

**[0:55:46]** And add omega equal to omega naught, we have zero plus 90 degrees minus 90 degrees, so that's zero. Alright. So I... Alright. The range here is going to be 90 degrees, zero to minus 90 degrees.

**[0:56:09]** Okay. And what the Bode phase plot will look like is it'll start off at 90 degrees, and then as... At at large... At high... Very high frequencies, it's minus 90 degrees.

**[0:56:22]** And then we connect these going through zero like this. So that is the Bode plot for for the phase, for this transfer function. And if we look at this and we go back and compare to what we had sketched out earlier, right back here, this is the disadvantage of working on a tablet rather than on the board. Right? You can see that, right, basically, I...

**[0:57:04]** For the magnitude and the phase, I... Right, that these are very consistent with what we got for the Bode plots. Right? But the Bode plots, kind of make linear approximations, right, to, the different ranges of behavior. Be it should be 10 omega naught on the bottom there.

**[0:57:29]** Did I, not write it that way? Let me see here. You mean, yeah, you mean this 10 omega naught? Or... Oh, sorry.

**[0:57:41]** Yes. Okay. Yes. You're right. Thank you.

**[0:57:43]** It should be 10 omega naught. Just for, like, notes. Yes. Right. Yes.

**[0:57:51]** Okay. Thank you for that correction. Any other questions? Yes. Was it coincidence that omega naught was the same as one over square LC is the same as the pole frequency?

**[0:58:10]** No. It was not a coincidence. So so that pole is what gives you the peak. Right? Because, you know, in the limit of the resistance going to zero that, you know, the, pole goes to infinity.

**[0:58:25]** If the resistance is nonzero, it goes to some finite value. And it ends up being a quadratic pole because it's a second order. Right? You have the RLC. So...

**[0:58:37]** Yeah. So, yeah, there are fundamental reasons that it worked out that way. Any other questions? Okay. So so let's look at another example here.

**[0:58:51]** We will have time to start this but not to finish it, today. And this example that we would like to look at is a highpass filter, okay, but still based on just the same RLC series circuit. Okay. So we're gonna have an input voltage, v sub s, and then a resistor and a capacitor and an inductor. Okay.

**[0:59:32]** So resistor, capacitor, and inductor. And instead of taking the output voltage to be the voltage across the resistor, we take it to be the voltage across the inductor. So, essentially, this is the same circuit that we had before, except that we've exchanged, the resistor and the inductor. Okay? So if we look at this circuit, then, right, we can deduce pretty easily that, this should behave as a highpass filter.

**[1:00:06]** Alright? Because if we look at the impedance of the inductor, right, the impedance of the inductor is just j omega l, and this goes to zero as omega goes to zero. So what we should expect is that low frequencies, v sub l should be very small, alright, basically, by voltage division. And then we can also see that the impedance of the inductor goes to infinity as omega goes to infinity. So at very high frequencies, again, by voltage division, we should have a large output voltage, and that is basically what corresponds to, highpass filters.

**[1:00:52]** So just looking at these limiting behaviors, we can deduce that... Right. This circuit... Okay. It should make sense sort of intuitively as a highpass filter.

**[1:01:21]** Okay. So... And then the other thing that we can notice is that... Right. Again, this is an RLC series circuit, and so it will also have a resonant frequency, right, a frequency at which the input impedance is purely real, and that resonant frequency is again going to be one over root LC because that's the frequency at which the impedances of the capacitor and the inductor cancel each other out.

**[1:01:48]** Okay. So this circuit has a resonant frequency, right, omega naught, which is one over root LC. Right? Basically, since, again, omega naught l is equal to one over omega naught c, which means that the impedances of the inductor and the capacitor cancel out at omega equal to omega naught. Okay.

**[1:02:28]** So what we wanna do with this then is, again, to calculate the transfer function and then try to understand it. Okay. So any questions before we do that? Okay. Give myself some more room here.

**[1:02:51]** Okay. So, basically, we're gonna use voltage division again. Right? That's the easiest thing to do. So what happens is that, right, by voltage division, we can see that the voltage across the inductor, right, it's gonna be the impedance of the inductor divided by the total series resistance.

**[1:03:15]** Right? So the impedances of the resistor plus the capacitor plus the inductor times the input voltage v sub s. So the resistance of the inductor is j omega l. And then in the denominator, we have the resistor impedance r plus the capacitor impedance one over j omega c plus the inductor impedance j omega l times the input voltage, v sub s. Alright?

**[1:03:50]** And then the transfer function is just, v sub l, the output voltage divided by v sub s, the input voltage. Okay. So we get that h of omega. Alright. The transfer function which is v l over v s, this is equal to just this prefactor over here.

**[1:04:14]** Right? So it's j omega l divided by r plus one over j omega c plus j omega l. Okay. And then to simplify this a little bit, to get rid of this fraction that we have in the denominator, we will multiply by j omega c over j omega c. Okay.

**[1:04:40]** And when we do that, then what we get in the numerator is minus omega squared l c. And in the non... Denominator, we get as we had before, one minus omega squared l c plus j omega r c. Okay. So that's the transfer function.

**[1:05:03]** Any questions on that? Okay. So now from this, right, we wanna calculate the, the magnitude and the phase. Alright? So the magnitude...

**[1:05:17]** Oops. Okay. So the magnitude. Alright. So the mang...

**[1:05:36]** That's the magnitude of the transfer function. Right? If we look at this expression over here, then the magnitude is just going to be the magnitude of the numerator divided by the magnitude of the denominator, right, just as we did before. So for the numerator, the magnitude is omega squared LC. And for the denominator, the magnitude is...

**[1:05:58]** Right? It's the square root of the real part squared plus the imaginary part squared. So the square root of one minus omega squared l c, the quantity squared, plus omega squared r squared c squared. Okay. So that's the magnitude.

**[1:06:20]** And for the phase The two. Okay. Here, it's a little bit tricky. There are two different expressions that we're gonna have to use. Okay?

**[1:06:33]** So if we look at this expression up here, right, then we know that, in general, the phase is going to be the phase of the numerator minus the phase of the denominator. Right? Now let's think for the for the numerator, it's pretty straightforward. The phase is, right. We have the minus one here, so, the phase is a 180 degrees.

**[1:07:04]** Now for the denominator, let's think first about what happens for low frequencies, specifically omega less than omega naught. Right? Where, remember, omega naught was one over root LC. For omega less than omega naught, then this real part is positive. Okay?

**[1:07:27]** And the imaginary part of the denominator is also positive. Okay. So, this quantity in the denominator is in the first quadrant of the complex plane. Right? So if we make a little sketch here of the complex plane, Right?

**[1:07:46]** This is the imaginary axis. This is the real axis. Then the denominator for low frequencies, omega less than omega naught, is in the first quadrant. Right? So the phase of the denominator, is here for omega less than omega naught.

**[1:08:09]** Okay? And so in that case, right, the inverse tangent is gonna be positive, and it'll be what what you get just by typing that, you know, the real part or the imaginary part over the real part into your calculator. So, for omega less than omega naught, then the phase is going to be... The overall phase of the transfer function gonna be the phase of the numerator, 180 degrees, minus the phase of the denominator, which is the inverse tangent of omega r c over one minus omega squared LC. Alright.

**[1:08:48]** That's what the phase is for omega less than omega naught. Okay. So any questions on that? Okay. Now let's think about what happens if omega is greater than omega naught.

**[1:09:06]** Okay? And, specifically, what happens in the denominator? If omega is greater than omega naught, greater than one over root LC, then what happens here is that this real part is negative. Right? The imaginary part is still positive.

**[1:09:27]** Okay. So if you have the real part being negative, the imaginary part's still positive, that is the second quadrant over here. Right? So the phase of the denominator is over here in the second quadrant for omega greater than omega naught. But if you were to, you know, take, say, this expression here and use your calculator to calculate it, then what'll happen is it...

**[1:09:57]** It'll give you a value, an angle in the fourth quadrant, okay, when in reality, it should be up here in the second quadrant. So in order to get the correct phase, right, what you have to do is to take this expression here, alright, and add a 180 degrees to it. And that'll give you the correct phase, which is over here in the second quadrant. So then when you take the phase of the numerator minus the phase of the denominator, the 180 degrees that we had up here, and the 180 degrees that you have to add to get yourself into the right quadrant over here, will cancel each other out. Okay?

**[1:10:47]** So what we will actually have for the phase of this overall transfer function here is going to be just minus the inverse tangent of omega r c over one minus omega squared l c. Right? This is what we have when omega is greater than omega dot. Okay? So, so this is one of the circumstances where I...

**[1:11:17]** You know, since the inverse tangent is typically defined as a function that, you know, has a range of minus 90 degrees to plus 90 degrees, then if the actual correct phase is not within that range, then you're gonna have to add or subtract a 180 degrees to get the right phase... The correct phase. Okay? And this is a circumstance where you actually have to do that. So any questions on that?

**[1:11:50]** Okay. So, the other thing that we can note here is that... Alright. Since this is a resonant circuit, alright, it has a resonant frequency, then, we can look at this quality factor that, we talked about earlier. Right?

**[1:12:17]** So the quality factor of q, remember, we said that in general for an RLC series circuit, it's gonna be omega naught l over r or equivalently, one over r times root l over c. Okay? Now if we look at our transfer function over here, okay, and we set omega equal to omega naught, which is one over root LC, then this real part of the denominator is going to go to zero. Right? So what we're gonna have, or we'll look at the magnitude over here.

**[1:12:59]** Alright? This first term under the square root is gonna go to zero. And so in the denominator, we're just gonna have the square root of omega squared r squared c squared, which is omega r c. In the numerator, we have, omega squared l c. So that magnitude at the resonant frequency is just gonna be omega, omega naught l over r, okay, which is equal to the quality factor.

**[1:13:31]** Okay. So what we see then is that the magnitude of the transfer function at the resonant frequency, Right? We can see from our explicit expression for the magnitude is equal to omega naught l over r. And then by doing this comparison over here, we can see that that's actually equal to q. Okay?

**[1:13:52]** And this has implications for what the plot of... And the behavior of the magnitude look like. Alright? So now we're plotting the magnitude of the transfer function in dB as a function of frequency, but, we're not yet making the linear approximation, to get the Bode plot. Okay?

**[1:14:21]** So this will be, the resonant frequency omega naught. Okay. And we know if we look at our expression for, the magnitude of the transfer function, if omega goes to zero, then the magnitude is gonna go to zero because we have the omega squared here in the numerator. And as omega goes to infinity, then what'll happen is that, this omega squared l c, the quantity squared, is going to be the dominant term under the square root. We take the square root of that, and we just get omega squared LC in the denominator.

**[1:15:06]** That's the same as the numerator, and so, the magnitude of the transfer function will go to one at very high frequencies. K. So we have zero here and one here. Okay. And, alright, if we kind of sketch out the transfer function, we know that it's gonna go.

**[1:15:31]** Right, it's approaching zero at low frequencies, and then it's gonna approach, one at high frequencies. But then at omega naught, it's going to be equal to the quality factor. Now if we look at the quality factor, say, by... In this expression over here, then what we can see is that if we have a sufficiently large resistance, we can always make this quality factor less than one. Alright?

**[1:16:04]** So if we have a large resistance corresponding to a low quality factor, then, alright, the magnitude of the transfer function, which is equal to the quality factor at the resonant frequency is gonna look... Right. It'll look something like this. Okay. So this is if we have a low quality factor which is less than one.

**[1:16:33]** Alright? But then if you think about what happens if we reduce the resistance, then you can see that, right, as the resistance, you can always make it sufficiently small that the quality factor is greater than one. Alright? So another possibility is that, you know, we still have the same behavior at zero or as the frequency approaches zero, but then we have a quality factor that's greater than one. Right?

**[1:17:07]** So we'll have something like this. Okay? So this is what we would have if we had a moderate quality factor, right, which is greater than one, right, but not that large. And then, right, if you made the resistance really small, you can imagine that the quality factor would be very large. Okay?

**[1:17:31]** And so in that case, you could get... Should have left myself a little more room here. Alright. Something like this where it comes to, you know, a sharp and quite high peak going like this. Right?

**[1:17:50]** This is what you would have if you had a very high quality factor. Right? Much greater than one. Okay. So depending on the quality factor, if you look at the magnitude of the transfer function, you can have, these quite different types of behavior right in the vicinity of the resonant frequency.

**[1:18:12]** Okay? If you look at the phase, right, for the phase, it doesn't have that sort of special behavior near, the resonant frequency. It just... Right? The phase goes, towards a 180 degrees at low frequencies, alright, because this becomes zero.

**[1:18:31]** And at high frequencies, it goes towards zero because this denominator dominates the omega squared. And then right at the resonant frequency, it's 90 degrees. Right? So the phase... Right?

**[1:18:48]** Just to finish this up here. Right? The phase as a function of frequency. Right? We have zero degrees, 90 degrees, and a 180 degrees.

**[1:19:04]** Okay. This is omega naught. Right? It is going to start off in a 180. Alright.

**[1:19:15]** Go through 90 and then approach zero. Okay. So this is what the phase is going to look like for this filter. So any questions on, any of this? Yes.

**[1:19:29]** Two questions. So if the magnitude is approaching, basically one. Right? Mhmm. You're approaching one from underneath and to zero decibels because...

**[1:19:44]** Alright. Zero decibels means equal in, but to equal out. Yeah. It it can actually approach from either side as as you go to infinity. I'm I'm talking about, like, why is...

**[1:19:56]** So we have one decibel that we approach to as it goes to finish. Oh, sorry. This is not decibels. This is just... Yeah.

**[1:20:06]** Sorry about that. Is it... Was that your question? Yeah. Okay.

**[1:20:10]** So I guess we can achieve, like, arbitrarily high transfer voltage or whatever if we, like, may end up in time or if it is small. Yes. So arbitrarily high but finite. But then as you make it higher, it'll be more narrow. Okay.

**[1:20:28]** And that's sort of the characteristic behavior of resonant systems generally. So, yeah, so that can happen. Any other questions? Okay. We're running slightly long, so why don't we stop here for today?

**[1:20:43]** We'll pick up with this on Wednesday.
