# 2026-10-21-passive-filters-and-bode-plots-cont

Deepgram general-nova-3 2025-07-31.0, request 01a1b010-88a0-7ac3-b819-30bdeb0e4e97, audio 78.7 min.

**[0:00:03]** Okay. Let's go ahead and get started. So I have started the recording. I just start with a few announcements. The first one is just a reminder that problem set six was due today.

**[0:00:14]** So hopefully, everyone has turned that in. And then, the second announcement is that problem set seven, has been released on Canvas, and it is due on Monday, November 2. And problem set seven is on transfer functions, Bode plots, and filter circuits and the likes. So basically, the material that we are covering now. And then the third announcement is just a reminder that I won't have office hours today after class because of travel.

**[0:00:43]** And as I announced on Monday, I had extra office hours... Office hours on Monday afternoon that took the place of what I would have had today. So any questions on any of that? Okay. Any questions from our last class meeting?

**[0:01:03]** Okay. Then we'll pick up from where we left off. So what we were discussing last time were kind of transfer functions generally, and what we said at the end or near the end of our last class meeting was that it is generally the case that transfer functions for circuits will have this form here where we have a rational function of, actually, j times omega. Right? It's where omega is the frequency, and the numerator and the denominator are polynomial functions of j times omega.

**[0:01:44]** And that comes about basically because when we have impedances in a circuit, right, they are... Right? For a resistor, it's r, which is real. For a capacitor, one over j omega c. For an inductor, j omega l.

**[0:01:59]** And so when you put those together, when you're adding, say, currents, then you'll get factors of the impedance in each of those terms. And then if you divide out the common factors, then you'll tip... That'll typically give you polynomials in in frequency. Alright? And so...

**[0:02:24]** Alright. When we take the magnitude of the transfer function, then... And then we take the log to put it on the dB scale, then we get sort of the difference of the logs of the numerator and the denominator. Okay? And that will...

**[0:02:43]** If you think about that a little bit, that will give you a hint as to why Bode plots, which is what we'll talk about next, are particularly useful. Okay. Now what we had set up at the end of our last class meeting was a very simple example where we were imagining that we had a transfer function where the numerator was of this form here and the denominator was just one. So this would be the whole transfer function, and we can easily, write down the magnitude and the phase of this transfer function. Okay?

**[0:03:19]** And I asked you, to think about what kind of circuit would actually give rise to a transfer function or a factor in the transfer function that, kind of looks like this. Okay? So, so if you had a chance to think about it, what do you think might give you a transfer function that looks kind of like this? Okay. Well, I'll start off.

**[0:03:52]** I'll give you an example of something that will give you a transfer function that looks something like this. So imagine that you had a circuit that has output terminals like this. Okay? And you have a current, say, represented by a phasor coming in, and then between the output terminals, you have a resistor and an inductor in series. Okay?

**[0:04:29]** Then I... This voltage here, alright, v o as a phasor, it's going to be this current, alright, times the impedance of the resistor and the inductor in series. So r plus j omega l. Alright? And if we factor out the r from that, we get I times r times one plus j omega l over r.

**[0:05:02]** Alright? So this factor over here, right, has exactly the form that we had over here, and it's just multiplied by a constant over here. Alright? So this kind of configuration, that I've shown here is one way that you can get a factor in the transfer function that looks kind of like this, or looks actually exactly like this with, and the exponent being equal to one. Okay?

**[0:05:29]** So given a transfer function that looks like this, then what we want to do next is to plot out the magnitude or at least sketch out the magnitude and the phase and then see how those sketches get translated to kind of the simplified form of the Bode plots. Okay? So let's look first at the magnitude. Okay. So for the magnitude, then...

**[0:06:03]** Alright. What we have is we're gonna plot for now. Alright. We're gonna have the magnitude of the transfer function. This is going to be in dB.

**[0:06:20]** And then we have the frequency, and the frequency is on a log scale. Right? The magnitude is on a log scale because it's in dB. The frequency, from the nature of the Bode plot, we also want to have on a log scale. So this might be omega z.

**[0:06:41]** This would be 10 omega z. This would be point one omega z. Right? And if we look at the magnitude that we have up here... Right.

**[0:06:54]** So it's of this form here. When omega goes to zero, then we have the log of, sorry, this is a one in here. Right? The log of one, which is zero. Okay?

**[0:07:07]** And so we'll start this at zero, and then we have this prefactor of 20 n. Alright? So maybe you'll have 10 n and 20 n, alright, on the vertical scale. Okay. And so what we wanna do is to, on these axes, sketch out what this function looks like.

**[0:07:30]** Okay. So any questions before we do that? Yes. Oh, okay. Great.

**[0:07:35]** Thanks. For the above example, r l in series, where does the factor of n come in? So in this case, n would be one. Alright? I...

**[0:07:45]** To get a larger x... That's this n over here. Right? To get a larger exponent, then, you know, you might imagine that... Okay.

**[0:07:56]** From these output terminals, right, maybe they're connected to something else that looks like this. Okay. And then you would you would end up getting... Or not quite like like that, but, you know, some some other things in between so that, in the end, this would give you another factor of... That looks like this.

**[0:08:29]** And so you would get a... You know, then you would get this squared. Alright? So so to get the higher exponents, typically, you have to have something that has multiple stages, kind of like... It's not exactly like this, but but kind of like this where there's something in between.

**[0:08:48]** Okay? And that would get you the higher exponents, and we will see some examples of that later on when we talk about filter circuits and orders of of filter circuits. Okay. So hopefully that answers that question for now. Okay.

**[0:09:07]** So if we come back to, this plot over here. Right? What we wanna do is to plot basically this function here or sketch this function here on these axes. Alright? So if we look at this, alright, we can see that when omega goes to zero, the magnitude goes to zero.

**[0:09:32]** And then as omega becomes very large, then the magnitude goes to infinity. Right? The magnitude goes to infinity as omega goes to infinity. We can also look at what happens when omega is equal to omega z. Alright?

**[0:09:48]** So in that case, omega over omega z is one, and so we have the log of the magnitude of one plus j. Alright? So what is the magnitude of one plus j? Right. It's it's the square root of two, or two to the one half.

**[0:10:08]** So then we have the log of two to the one half. That's one half times the log of two. And so we have one half times 20 n, that's 10 n times the log of two, which is roughly point three. So 10 n times point three is, roughly three dB. Okay?

**[0:10:24]** So we have... Right. We'll indicate three dB or three n over here, and then we have a point like this. And then we know that as omega goes to zero, the magnitude of the transfer function goes to zero. So we're gonna have something like this.

**[0:10:45]** And then as omega increases, then the magnitude will increase as well. So it'll go something like this. And if we look at the form of this here, we can see that as omega becomes very large, then the magnitude of the imaginary part of this becomes much larger than one. And so this looks roughly like, the log of, the magnitude of omega over omega z, okay, times 20 n. So when we get to higher frequencies, larger magnitudes of the transfer function, this is going to look...

**[0:11:29]** Be approximately equal to 20 n times the log of omega... The magnitude of omega over omega z. Okay. So this is kind of a sketch of what the transfer function looks like. Okay.

**[0:11:47]** So any questions on this? Okay. Oh, yes. Sorry. For the original, the I that...

**[0:11:55]** The I times r times one plus, what role is I playing? Like, is it just any arbitrary current source? Or... You mean over over here? Yeah.

**[0:12:11]** Oh, yeah. It would be some current that, you know, we would calculate it in some other way. Right? And we can look at this part of the circuit and think about it in terms of the current that's coming in. Right?

**[0:12:25]** We could also think of it as being... You know, if the the voltage between these is already v o. Right? You know? And then the current we're imagining is determined by something else in the structure of the circuit.

**[0:12:39]** Alright? Or it could be... You could imagine, you just have a current source. Right? It provides that current.

**[0:12:45]** This is just an example of how you get this kind of factor, not this is the only kind of circuit, right, that, that produces this kind of behavior. Yeah. Does that answer your question? Okay. Any other questions?

**[0:12:58]** Okay. So what we wanna do then is to see how this is approximated, how this plot is approximated in the Bode plot and, specifically, the Bode magnitude plot. Okay. And the idea in the Bode plots is that we take sort of the actual plot of, in this case, the magnitude as a function of frequency, where both the magnitude and the frequency are on a log scale. And we construct a plot that has just linear approximations for for this behavior, for the magnitude in each of the key regions of behavior.

**[0:13:52]** Okay? And so if we look at this plot over here, right, basically, there are, sort of two different regions of behavior. There is what happens when omega... The frequency is less than omega z, and what happens when omega is greater than omega z. Alright?

**[0:14:11]** Those are the two main regions of behavior. And what we're gonna do in the magnitude plot... In the Bode magnitude plot is to say, well, in order to simplify this, sum so that we can sketch it out very quickly, you know, at the price of a little bit of loss in accuracy. What we're going to say is that for omega less than omega z, right, basically, low frequency region of behavior, we're going to, make an approximation that the magnitude, that we can sketch the magnitude as just whatever its behavior is in the limit that omega goes to zero. And then for the other main region of behavior at high frequencies, omega greater than omega z, we're going to make the approximation that we can sketch out the behavior, as being the behavior of this function when we go to very high frequencies, which is essentially this.

**[0:15:13]** Okay. So if we go ahead and do all that, alright, then the plot that we get it's gonna look like this. Right? So now... Alright.

**[0:15:27]** We're again looking at the magnitude, zero, 10 NDB, 20 n dB. And, the frequency, this is omega z, point one omega z, and 10 omega z. Right, what we're gonna do is we're gonna say, alright. For low frequencies, omega less than omega z, then, we're gonna make the approximation that we're just gonna plot the limiting behavior as omega goes to zero, omega is very small. And that is that the transfer fund...

**[0:16:11]** The magnitude of the transfer function goes to zero dB. So it'll look like this. Okay? And then for high frequencies, omega greater than omega z, we're going to make the approximation that in that whole region, we have behavior that looks essentially like the high frequency behavior, which is that the magnitude of the transfer function goes as 20 n times the log of the magnitude of omega over omega z. And so that is going to look like this.

**[0:16:48]** It's a straight line on, this log log scale, and the equation for the line in the high frequency region of behavior is then just 20 n times the log of the magnitude of omega over omega z. Okay? And this is the Bode magnitude plot. Right? It's something that we can sketch out very quickly.

**[0:17:14]** And as we will see in a little bit, drawing it in this form makes it very easy to combine the Bode plots for different factors that might come into the complete transfer function. Okay. So any questions on this? Okay. So that is the magnitude.

**[0:17:35]** Now we want to look at the phase. Okay? And so if we look at the phase, the expression that we worked out over here, right, the phase is given by this expression, and we can see that, as omega goes to zero. Right? So at low frequencies, the phase goes to zero, right, because the inverse tangent of zero is zero.

**[0:18:00]** And at very high frequencies, right, omega much larger than omega z, then we're gonna have the inverse tangent of some very large number, and that is going to, approach 90 degrees. Right? So 90 degrees times n will be the phase as omega goes to infinity. Alright? So let's sketch that out in a plot where we again have...

**[0:18:33]** Right now, this is the phase as a function of frequency, and we've seen already that it goes... The phase goes from zero degrees to 90 degrees times n. Okay. And then on the frequency axis, we have omega z, 10 omega z, and point one omega z. Right?

**[0:19:01]** This is on a log scale. Okay. So here... Alright? Now add omega equal to omega z.

**[0:19:10]** Alright. We'll also mark the halfway point 45 degrees times n. If we come back here to the expression for the phase at omega equal to omega z, then we have the inverse tangent of one, which is what? Right. Pi over four of 45 degrees, alright, times n.

**[0:19:37]** Alright. So at omega equal to omega z, we have this point here. And then as we go to, low frequencies, then the phase gradually approaches zero. Alright. So it goes kinda like this.

**[0:19:58]** And then at high frequencies, gradually approaches 90 degrees times n. Okay. So this is the plot of the phase. And so for the Bode plot of the phase where we're making, again, basically linear approximations, right, to, the behavior of, the actual now phase, in the different regions of behavior, Right? Now we wanna look at the Bode phase plot.

**[0:20:38]** Okay. What's gonna happen is we... This is the phase. So this is still going to be on a linear scale for the vertical axis and then a log scale for the horizontal axis, the frequency axis. Okay.

**[0:21:07]** But now, right, if we did, just strictly speaking, the same thing that we did for the magnitude, which is to say that, for omega less than omega z, we'll assume the linear b... The limiting behavior as omega goes to zero. For omega greater than omega z, we will assume the limiting behavior as omega goes to, infinity. Alright? If we did that, then what would happen is we would have, a straight line at the...

**[0:21:32]** At zero phase up to omega z, then a discontinuous jump to 90 degrees times n, and then a straight line out here. Alright? Now that's a little too lousy of an approximation. Okay? So...

**[0:21:46]** Because it doesn't really sufficiently correctly represent the shape of... I lost the cursor over here. The shape of this green curve on the left. Okay? So for the phase, what we do instead is we say, alright, if we we...

**[0:22:06]** In order to have the limiting behavior at low frequencies in the phase plot, we are going to make that approximation only when the frequency is much lower than omega z. And the criterion that we will use for much lower is that omega has to be less than point one times z. Right? So we can do this in those frequencies. And then correspondingly, at high frequencies, right, we will only assume that the phase plot looks like, it's limiting behavior as omega goes to infinity if we are sufficiently far above omega z.

**[0:22:50]** And sufficiently far, we define as being greater than 10 omega z. Okay. So at 10 omega z, then we have this. Okay? And then for the region between point one omega z and 10 omega z, we'll just assume that it goes linearly in between, and that has the advantage of going through the correct point at omega z.

**[0:23:21]** Okay. So this is the Bode phase plot, which is a linear approximation or piecewise linear approximation to, this phase plot over here. Alright. So any questions on, the Bode plots of magnitude and phase? Yes.

**[0:23:39]** Bode plots were, automatically generated. Like, when when we create Bode plots, it samples it or tries at different frequencies. But is that not... Is it... It seems like it's...

**[0:23:52]** Bode plots are human created, rather than, you know, machine created giving the exact values. So so this is, it's sort of a matter of how the term Bode plot is used in different settings. So what we are... The the way that we're using the Bode plot terminology here is the way it is used in the Ulaby textbook, which is that Bode plots refer specifically to these linearly approximated versions. Okay?

**[0:24:26]** Now in other settings, it is sometimes the case that either of these will be... Also be referred. Right? Both of these will be referred to as Bode plots. And then, you know, something like this.

**[0:24:42]** If you really wanted to plot it accurately, then you would you would machine calculate it. Right? And then, you know, sort of the key features would be that, okay. For the magnitude, you're plotting the magnitude... For for the magnitude, plot, you're plotting the magnitude on the dB scale, so therefore a log scale and the frequency on a log scale.

**[0:25:04]** And then for the phase, you're plotting the phase, the vertical axis on a linear scale, and the frequency on a log scale. So in some settings, both of these... Or I guess all four of these are referred to as Bode plots. In Ulaby, which is what we're following here, it's specifically the linearly approximated versions. Okay.

**[0:25:28]** Does that answer your question? Yeah. Okay. Any other questions? Okay.

**[0:25:34]** So the other piece of terminology that we'll introduce here is that when we have this kind of factor in the numerator of a transfer function, we are going to refer to this factor in the transfer function as a zero of the transfer function. And the rationale behind that terminology is that, this factor actually goes to zero when omega equals... Is equal to j times omega z. Right? Because then you would have j times j, which is minus one, and omega...

**[0:26:14]** Over omega z, which is one. So you have one minus one, which is zero. Okay? So this frequency... Whoops.

**[0:26:28]** Switch back to black. Right? This frequency omega z, right, this is called zero of the transfer function, and we refer to it specifically as a zero of order n, because n is the exponent, of that factor. And we use that terminology, okay, because when omega is equal to j times omega z, that then implies that the numerator and in this case, the transfer function itself will be equal to zero. Okay.

**[0:27:21]** Now you might ask, okay. Why is this j over here? Alright? And we will get into that in more detail when we start talking about Laplace transforms. But the short version of it right now is that if we think about the...

**[0:27:40]** In the time domain, the different terms that will contribute to the behavior of current or voltage as all being essentially exponential functions. Remember when we talked about time domain behavior? We had exponential decay. Alright. That's an exponential function.

**[0:27:57]** And then we had oscillatory behavior, which is an exponential function with an imaginary coefficient of the time. Okay? A more general way of of looking at that is is saying that, well, we always just have, in the time domain, terms that are proportional to an exponential factor, say, e to the s times t. Alright? And, oscillatory behavior, which is what we have when we're talking about real frequencies, correspond to imaginary values of, s.

**[0:28:35]** Okay? And so that's why we have this, j over here, and we'll formulate things in that more general way in more detail when we get to Laplace transforms. But that's sort of the the short version of it right now. Okay. So any questions before we continue?

**[0:28:55]** Okay. So let's now consider another situation. Okay. Where we're gonna say that now the denominator of the transfer function has, this type of term, one plus j omega over... And then we'll call this reference frequency now omega sub p, alright, to the nth power.

**[0:29:25]** And let's, for simplicity, assume that the numerator is equal to one. Okay? So then in that case, alright, the magnitude in dB is just gonna be minus 20 times n times the log of the magnitude of one plus j omega over omega p. Right? So, basically, the negative of what we had for the zero, and then the phase is going to be minus minus n times the inverse tangent of omega over omega p.

**[0:30:16]** Okay. And, right, these are just... They're basically the negatives of what we had in the previous example, and that should make sense because now we're having this same factor here, but it's in the denominator rather than the numerator. Right? And so it's what we had previously to the minus one.

**[0:30:39]** Okay. So that gives us this negative sign when we take the log, and then the negative sign in the phase as well. Okay. And if you ask, well, what kind of circuit would, give rise to a term like this in the denominator, then, right, if you think about this a little bit, you would get something like this in the denominator if, say, you were doing voltage division, and, the total impedance of whatever series combination, you are applying voltage division to has a real term and an imaginary term, so a resistor, in series with, say, an inductor or a capacitor. Right?

**[0:31:22]** So if you had, say, something like this where we had, where we have a voltage source I, and then a resistor and, say, a capacitor like this. Alright? This is the resistor. This is the capacitor, and this is our output voltage. Right?

**[0:31:47]** If you just calculate v o by voltage division, then you're gonna get v s over one plus j omega r c. Alright? And so that basically has the form of this over here with the exponent n being equal to one. Okay. So so this is an example of the kind of situation where you would get a factor like this.

**[0:32:18]** Okay. So what we wanna do now is essentially the same thing that we did before. We're gonna construct first the sketches of the magnitude, and then of, the phase. And then in each case, we will see, how the linear approximations, give us the Bode magnitude and phase plots. But from what we did, just now, you should already be able to determine what these will look like because these are basically just the negatives of what we had up here.

**[0:32:55]** So in this case, all these plots should just be, reflected through the horizontal axis. Right? And you'll get the negative. Okay. So if we look at the magnitude...

**[0:33:11]** Okay. What'll happen is that right now... Okay. This is the magnitude of omega in dB. Alright.

**[0:33:25]** This is zero. And what'll happen is that I... We'll just get the negative of what we had above. So minus 10 n, minus 20 n, and say minus three n here. Alright?

**[0:33:43]** And at frequencies, right, it's omega p, point one omega p, and 10 omega p. Alright? And what these will look like is as follows. At omega equal to omega p, right, again, we're gonna have the magnitude of one plus j, which is root two. Right?

**[0:34:08]** So that's gonna be minus three n dB. So it's gonna be here. And then at low frequencies, this is going to approach zero like this. And then at high frequencies, it's going to increase. Okay.

**[0:34:30]** And it'll look approximately like minus 20 times the log of the magnitude of omega over omega p. Okay. So this is the what the magnitude looks like. And in the Bode magnitude plot approximation, Okay. It is...

**[0:35:01]** What we're going to do is... Alright. This is the magnitude. DB, this is zero. Say minus 10 n minus 20 n.

**[0:35:17]** This is the frequency. This is omega p, point one omega p, and 10 omega p. Alright? Then, as we did before, we will say that, for the magnitude, for frequencies less than omega p, that is in the low frequency region of behavior, we'll assume, or we'll make the approximation that the magnitude is just whatever its value is at very low frequencies, which is zero dB. And then at high frequencies, omega greater than omega p, we will make the approximation that the magnitude behaves like, it would at extremely high frequencies, which is that it is linear with a slope, on this log log scale that is equal to minus 20 n times the log of omega over omega p.

**[0:36:19]** Alright. So that's what we have for the, for the, magnitude and the Bode magnitude plot. Okay? And then for the phase, Okay. Then what'll happen, right, if we look at the expression for the phase up here is that at low frequencies omega going to zero, the phase will go to zero.

**[0:36:55]** At high frequencies omega going to infinity, the phase will go to minus 90 degrees times n. And then, at omega equal to omega p, we'll have the inverse tangent of one. So that's going to be 45 degrees, so it's gonna be minus 45 degrees times n. Okay. So, if we draw that out...

**[0:37:24]** Okay. Then... Alright. We're looking at the phase versus the frequency. The phase is on a linear scale, and the frequency is on a log scale.

**[0:37:50]** Okay. And what it looks like here is at omega equal to omega p, remember, it was 45 degrees times... Minus 45 degrees times n, and it's gonna go to zero as we go to very low frequencies. And then it's going to go to minus 90 degrees times n as we go to high frequencies. Alright.

**[0:38:20]** So this is what the phase plot looks like. And then with the linear approximations that, in the terminology of Ulaby, give us the Bode phase plot. Okay. What we're going to do is, again, we're plotting the phase on a linear scale, and then the frequency Okay. On a log scale...

**[0:39:15]** Okay. And the way that we construct the Bode plot is we say that at very low frequencies, less than, point one omega p, then we assume the behavior... We make the approximation that it behaves as it would at, omega going to zero and at very high frequencies, omega greater than 10 omega p, then we make the approximation that it'll behave as it does at omega going to infinity, and then we have linear interpolation between these. Okay. So that is what the Bode phase...

**[0:39:58]** Or or the phase plot and the Bode phase plot look like. So any questions on the magnitude and phase plots? Okay. And then the terminology that we associate with a factor of this form in the transfer function, basically, having a factor like this in the denominator is that we call this a pole of the transfer function of order n, the exponent over here. Alright?

**[0:40:32]** And a pole basically is defined as a point at which the transfer function goes to infinity in this particular way here. Okay. So omega sub p, right, is called a pole of h of omega, and it's of order n, which is the exponent. And the way the pole is defined is that when omega is equal to j times omega p, then that means that the denominator is equal to zero, and the transfer function itself goes to infinity. Okay.

**[0:41:29]** So any questions on this? Yes. This is general math solving factor. If you have a transfer function and you want to get it in decibels, just simply the way you would do it is by taking the log of it and then multiplying by 20. That's, you know, that's how you convert units to decimal units.

**[0:41:52]** Yeah. That's right. Yeah. Okay. Any other questions?

**[0:41:57]** Okay. So so now we've looked at two examples of the types of factors that you can get in a transfer function. It turns out that for for any linear circuit, there will be a limited number of types of factors, right, that you can get that when you multiply them together constitute the entire transfer function. Okay. So in general, what's gonna happen is that the transfer function h of omega, right, this can be written in the following form where we have...

**[0:42:45]** Bless you. The transfer function being equal equal to a product of a bunch of factors where those factors are selected from a limited set of possibilities. Okay. So what we wanna do is to just enumerate what these possibilities are. Okay?

**[0:43:12]** So when we have the transfer function in this form, right, each factor a sub I of omega, right, will be one of the following. Okay. So we're gonna make a table, a pretty big table here of all the different kinds of factors. Alright? So we will have, you know, what the factor is itself, and then what we wanna do is to sketch out this...

**[0:43:53]** The corresponding Bode magnitude plot and the corresponding Bode phase plot. Okay. So so what are the different factors that can appear in a transfer function for a circuit in general? One possibility is just to have some overall constant factor. Right?

**[0:44:28]** That could be the voltage scale or or something like that. And so the Bode plots for a constant, right, are very simple. K. So, frequency on the horizontal axis. And then, right, if we just take 20 times the log of this, right, this is gonna be 20 times the log of that constant.

**[0:45:01]** And, alright, it's gonna be just that constant. And then for the phase, Alright. I will call this zero degrees, and then this will be... Right. It could be plus or minus a 180 degrees.

**[0:45:30]** And the phase will be a constant independent of frequency as well. And it'll be either zero or plus or minus a 180 degrees. It's this. It's zero if k is greater than zero, and it's plus or minus a 180 degrees if k is less than zero. Alright?

**[0:45:56]** So that's how we would construct the magnitude and phase plots, the Bode magnitude and phase plots. We just have a constant factor. Okay? Then, right, sort of going up in order of complexity, it's also possible to have zero at the origin. That is at omega equal to zero.

**[0:46:24]** Right? That would be a factor of the foreign j omega to the nth power. Right? So you might get this if you have... Right?

**[0:46:31]** Right? If you're multiplying by, say, the impedance of an inductor, right, which is j omega l. Right? You would get a factor like this. Okay.

**[0:46:41]** And for this, alright, the Bode magnitude plot... Alright. This is zero dB. Take this to be 20 n. And then, right, for a zero at the origin, there's no natural, frequency scale, for it.

**[0:47:06]** So we'll just say a frequency of one, 10, a 100, and so forth. And what will happen here is that at the frequency of one, we're at zero at a frequency of 10. We're at 20 n. Alright. So the Bode plot...

**[0:47:26]** The magnitude of plot is gonna look like this. Okay? And the slope here is gonna be 20 n dB for every factor of 10 change in the frequency, and, we refer to a factor of 10 change, in this case, in the frequency, but it could be for for anything in general as being, this much per decade. Right? So a decade is a factor of 10 change in this terminology.

**[0:48:00]** Okay. So the slope here is, 20 n decibels per decade. Okay. That's how we, how we refer to it. And then for the phase, okay, the phase of this, alright, we can see is just going to be, it's the phase of j, which is 90 degrees to the nth.

**[0:48:26]** We're taking that to the nth power, so the phase is gonna be 90 degrees times n. Okay. So this will be the phase, for zero at the origin. So any questions on this? Okay.

**[0:48:45]** Then, alright. The next possibility is that we have a pole at the origin. Okay. And that's where we have a factor that's of the form one over j omega to the n. Alright?

**[0:49:04]** And you can imagine getting a factor like this, if you are multiplying by the impedance of a capacitor, one over j omega c. Alright? Then you would get, the j omega in the denominator. Okay? And so for that, alright, the Bode magnitude plot, is going to be...

**[0:49:29]** Alright. We have zero and then minus 20 n here. And the frequencies, again, since there's no, natural frequency scale for a pole at the origin, we just have numerical frequencies of one, 10, and a 100. And at a frequency of one, we're taking the log of one, so it gives us zero dB. And then in a frequency of 10, then it's minus 20 n.

**[0:50:00]** And so the Bode plot of the magnitude is gonna look like this with a slope of minus 20 n dB per decade. Okay. And then, the phase for the pole at the origin, right, we have a j in the denominator, which has a phase of minus 90 degrees. And then that j in the denominator is to the nth power, so the total phase associated with this factor is going to be minus 90 degrees times n. K.

**[0:50:39]** Like this. Okay. So any questions on the pole at the origin? Okay. And then kind of just, you know, moving slightly up in complexity, then we have, the zeros, and the poles add some nonzero frequency, which are the examples that we just looked at.

**[0:51:05]** Okay? And so we have, what's called a simple zero, at some frequency omega z, and that's where we have a factor one plus j omega over omega z, right, to the nth power. So this would be a simple zero of order n. Alright? And this one, right, we just looked at earlier in class today.

**[0:51:37]** Alright. So, we have zero twenty n, and this is omega z. Say, this is 10 omega z. And what the magnitude plot looks like, as we saw, is like this. Right?

**[0:52:06]** And the slope here is 20 n dB per decade. Okay. And then for the, phase plot... Alright. Remember, we saw that this would go from zero degrees to 90 degrees times n.

**[0:52:33]** Alright? And then we wanna mark omega z, 10 omega z, and point one omega z, and the phase plot looks like this. Okay. So that is the simple zero, which we looked at earlier in class. And then we also have the second example that we looked at, which is the simple pole at some frequency.

**[0:53:12]** We'll call that, which we called omega p. Alright? And that's where we have a factor one over one plus j omega over omega p to the n. Right? So that's a simple pole of order n.

**[0:53:27]** Okay? And for the simple pole, Right? The plots are just the negative of what we had for the simple zero. So zero minus 20 n and omega, say omega p and 10 omega p. Okay.

**[0:53:50]** And then we have the low frequency behavior for... Of the magnitude for frequencies less than omega p, and then the high frequency behavior for frequencies greater than omega p. Alright? And so the slope here is minus 20 dB... 20 n dB per decade.

**[0:54:16]** Okay. And then for the phase, alright, it's just the negative of the phase that we had for, the simple zero. So starting at zero degrees going to minus nine degrees times n. And then frequencies point one omega p, omega p, and 10 omega p. And the phase plot for the simple pole, alright, will look like this.

**[0:55:01]** Okay. So any questions on the simple zero and the simple pole and their, Bode magnitude and phase plots? Okay. So we have two more. Oops.

**[0:55:18]** Okay. So in addition to a simple zero, we can also have what's called a quadratic zero. At some frequency, we'll again call... Since it's a zero, we'll call it omega z. And that is a factor that looks like one plus j times two times some constant.

**[0:55:50]** We'll call it xi, alright, times omega over omega z, plus j omega over omega z, the quantity squared What what the n. Letter is that? That's the Greek letter xi. It's it's the symbol that is used for... It's basically just the coefficient of the linear term in, the quadratic zero is, has this factor c in it.

**[0:56:23]** It'll typically be related to the resistance, in... That you have in a circuit, and this is just the symbol that is is typically used for this. Oh, well, it's it's a little squiggle on the top and then, like, a script e with a little tail on the bottom. And then the capital letter version of it is just three horizontal bars, but we will use the lowercase version here. Okay.

**[0:56:57]** So that's the quadratic zero. That's... So that is the lowercase Greek letter xi. And this is something that you could get... Right?

**[0:57:08]** If you imagine, say, you have current source, And now, right, you need three terms here. So you need a real term and two imaginary terms. Alright? And it turns out that you can get that if you have, say, a resistor, an inductor, and a capacitor all in series. Right?

**[0:57:42]** You can get a term like this because you'll have r plus j omega l plus one over j omega c. And if you multiply through by j omega c, then you'll end up getting something that looks like this. Okay. So this is the kind of situation where, you could get, a quadratic zero. Alright?

**[0:58:08]** And so for this... Alright, if we look at the Bode magnitude plot, right, then we have zero. And if we think about... You know, and this is omega p... Or zero...

**[0:58:33]** Sorry. Omega z and 10 omega z. Okay. So if we look at the form of the quadratic zero, then what we can see is that, right, as omega goes to zero, then these second... The second and third terms here will become very small, and we'll just have one.

**[0:58:56]** So, the magnitude will go to the log of one, which is zero. But then when we go to very high frequencies, right, it's this omega squared term that will dominate, and so this will go as omega over omega z to the two n. Alright? And then the j goes away when we take the magnitude. So we're gonna have the log of omega over may...

**[0:59:20]** Over over omega z to the two n. Alright? So when we bring that two n and the exponent out in front of the log, we're gonna have, two n times 20, which is 40 n. Alright? So for every increase at high frequencies, above omega z, then for every factor of 10 increase in the frequency, then in dB, the magnitude of the transfer function now is gonna increase by 40 n rather than 20 n because we have this extra factor of two here from the the quadratic exponent.

**[0:59:59]** Okay. So what the Bode magnitude plot is gonna look like is that at low frequencies, so less than omega z, we have the limiting behavior as omega goes to zero, which is just zero dB. And then at high frequencies, we have the limiting behavior as omega becomes very large, which is going to be a straight line here. But now the slope of this is going to be 40 n dB per decade. Okay.

**[1:00:34]** So it's steeper, alright, than, if we had the simple zero. And then for the phase, we have omega on a log scale again. Right? For the phase, omega goes to zero, right, we just have the phase of one or one to the end, which is zero degrees. Okay?

**[1:01:10]** And then as omega becomes very large, now we have... Right? This last term, the quadratic term is going to be dominant, so we're gonna have j to the two n. Alright? So the phase at high frequencies will be the phase of j to the two n, and that is 90 degrees times two n, which is a 180 degrees times n.

**[1:01:37]** Alright? So, at high frequencies, we're gonna approach a phase of a 180 degrees times n. Okay. So what the Bode phase plot will look like is that at very low frequencies, less than point one omega z, the phase is going to be approximated as zero. At very high frequencies, omega greater than 10 omega z is gonna be approximated as a 180 degrees times n.

**[1:02:07]** And then we have the linear interpolation between these like this. Okay. So that is the quadratic zero. Any questions on that? Okay.

**[1:02:21]** Then the last one is, as you might guess, the quadratic pole. At some frequency, we'll call again, since it's a pole, omega p. Alright? And that is where we have a factor of just one over one plus j times two xi omega over omega p plus j omega over omega p quantity squared to the nth power for a quadratic pole of order n. And for something like this, alright, we might get this if we have a situation where we're calculating, say, an output voltage by voltage division, where the total series combination that we have is a resistor plus a capacitor plus an inductor, right, to give us the three terms, each with a different power of omega.

**[1:03:28]** So that might be, say, a voltage source and then, say, a resistor and an inductor and a capacitor, say, like this. Right? Something like this where we have the output terminals at the right over here, right, that would give us a factor like this in the transfer function. Okay. And so here, alright, we're gonna have...

**[1:04:00]** Right. The Bode plots are just going to be... They'll basically be the negative of what we had up here because we have this factor here corresponding to the quadratic zero, but now it's in the denominator. Alright? So when we take the log, we get a negative sign.

**[1:04:19]** When we look at the phase, we get a negative sign also. Alright. So for the magnitude... Right. Frequency on a log scale.

**[1:04:37]** And then in dB, it's gonna go from zero, and then the scale here is gonna be 40 n. Right? It's gonna be 40 n change in the magnitude for every factor of 10 change in the frequency. So it's gonna look like this. Right?

**[1:05:03]** So the slope here now is minus 40 n dB per decade. Okay. And then for the phase, alright, it's going to be just the negative of what we drew up here. Right? Because now we have, this quadratic term in the denominator, so, we calculate the phase of the denominator.

**[1:05:34]** And then for the overall transfer function, we get the negative of that phase. Okay. So it's gonna go from zero degrees to minus a 180 degrees times n. Okay. And our frequencies here are point one omega p, omega p, and 10 omega p.

**[1:06:00]** Okay. It's gonna... And it'll look Like this. Okay. So any questions on the quadratic pole?

**[1:06:17]** Okay. Now one of the reasons that these linear approximations to the magnitude and the phase are particularly useful is that, right, if we look at the for... The general form of the transfer function that we have up here. Right? When we look at the magnitude of this and take the log, right, then what'll happen is that the log of this product here will just be the sum of the logs of the individual factors.

**[1:07:01]** Alright? And so to get... If we have a whole bunch of these factors here, then for the magnitude, we can quite quickly construct the Bode plot just by taking the Bode plots for the individual factors and then adding them up. Right? And adding constants, right, in a plot is easy.

**[1:07:25]** Right? You just increase the level. And adding these linear functions over here is also easy because when you add two linear functions together, it's still a linear function, and the slope is just the sum of the slopes of the individual lines. Right? So so this approach makes it very easy, to construct the Bode magnitude plot for even a pretty complicated, transfer function.

**[1:07:52]** And then for the phase, right, that that idea of just adding the individual plots together also works because the phases always appear in exponents. Right? If we are each of these factors in the magnitude and phase form. And when you have exponential terms that are multiplying each other, then the phases just add up. Alright?

**[1:08:18]** And so that means that when we construct the Bode plot for the Bode phase plot for a complicated transfer function like this, then all we have to do is add up the phases of the individual factors, right, to get, the total phase. And so that makes constructing the phase plot very straightforward as well. Okay. So one of the reasons this is particularly useful is that the Bode plots for each factor, Right? A sub I, right, in the overall transfer function, these can be added to each other, alright, to obtain the Bode plots for the total transfer function.

**[1:09:24]** Okay. So, any questions to hear? Okay. So so that's kind of the machinery of transfer functions and Bode plots. What we wanna do now is to take, this machinery and these ideas and apply them to look at various types of filter circuits, and we will start off by looking at what we call passive filter circuits.

**[1:09:59]** Okay. And the reading for this is in Ulaby et al, and it's sections nine dash four and nine dash five. Okay? And what we mean by passive filter circuits are basically filter circuits that, right, in the filter part of it, have only passive elements, so r, l, and c. Alright?

**[1:10:32]** There will be some active source to drive the circuit, but in the filter, you get the filter functionality only from passive components. And that is in contrast to what we call active filters, which we'll talk about a little bit later, which have components like, in our case, it'll be op amps. In other circuits that you'll learn about in subsequent courses, that can... It can be transistors or other types of active devices, you know, something that gives you gain. Okay?

**[1:11:01]** Those we will refer to as active filters. So passive filters, right, are filter circuits, right, that contain only passive elements. Right? So r, l, and c, I, right, plus the input signals, alright, which could be represented as a source of some sort. And that is in contrast to active filters, which contain things like op amps or transistors or other active devices.

**[1:12:11]** Alright. So, basically, devices that can give you gain. Okay? And we'll see when we start talking about that why it's useful to have that. Okay.

**[1:12:21]** So any questions before we continue? Okay. So let's look at an example of a passive filter circuit, and this example will be a bandpass filter. Okay. So we're gonna have our input signal, which will represent as a voltage source v sub s.

**[1:12:52]** Okay? And this will just be a simple RLC series circuit where we have an inductor and a capacitor and a resistor, and the output voltage is taken across the resistor. So we'll call it v sub r. Alright. So this is the inductor, capacitor, and resistor.

**[1:13:19]** Okay. So this is the bandpass filter that we want to analyze. If we look at this circuit, then, right, we can sort of see that it is going to act as a bandpass filter because at very low frequencies, the impedance of the capacitor will be very high, much higher than the impedance of the, resistor. So the output voltage will be very low. At very high frequencies, the impedance of the inductor will be very high.

**[1:13:54]** And so, again, the output voltage here, the voltage across the resistor will be very low. And then in between, there will be some frequency where the impedance of the inductor and the capacitor will cancel each other out. Okay? And so we'll have, essentially, all of the input signal appearing across the resistor. Okay.

**[1:14:18]** So, just looking at this, it should make sense to you that, this is going to act as a bandpass filter. Okay? And we can calculate the output voltage just by using current, voltage division. Okay. So if we use voltage division, right, we get that the output voltage is equal to...

**[1:14:47]** Right, the impedance of the resistor over the impedance of the resistor plus, the impedance of the inductor plus the impedance of the capacitor times the input voltage v sub s. So this is gonna be r over r plus j omega l plus one over j omega c times v sub s. Alright? And so we can immediately calculate what the transfer function is. Right?

**[1:15:22]** It's just, in general, it's the output voltage. In this case, it's v r over the input voltage v s. Alright? So it's going to be this prefactor over here. Right?

**[1:15:34]** So it's gonna be r over r plus j omega l plus one over j omega c. Alright? And we can simplify this a little bit by multiplying the numerator and the denominator, right, by j omega c. And so we will get j omega r c in the numerator, and then in the denominator, we get one minus omega squared l c plus j omega r c. Right?

**[1:16:10]** So here, you can already see, that in this transfer function, we're gonna get a quadratic pole due to this factor in the denominator, and we're going to get a zero at the origin, right, plus some constant or multiply by some constant. Okay. So you can already see how these different factors that we talked about are coming into play here. To help us analyze this in a little more detail, we can multiply this by the complex conjugate of the denominator, right, over itself. So we're only multiplying by one.

**[1:16:47]** So we multiply by one minus omega squared l c minus j omega RC over the same thing. One minus omega squared LC minus j omega RC. K. And then if we do that, we'll just finish up with this here. Right?

**[1:17:18]** We're gonna get omega squared r squared c squared plus j omega r c times one minus omega squared l c. And then in the denominator, we're just gonna get the magnitude squared of the denominator, which is the real part squared plus the imaginary part squared. So one minus omega squared l c squared plus omega squared r squared c squared. Okay. And so this, right?

**[1:17:50]** We can take the transfer function and think about it either in this form or in this form. Okay? And what we will do starting next time on Monday is we will look at the magnitude and phase of this transfer function, and then that will allow us to introduce some other ideas related to the bandwidth and quality and factor and so forth that we have for filter surface specifically and for frequency dependent circuits more generally. Okay. So any questions on this before we finish?

**[1:18:33]** Okay. If not, then, we will stop here for today, and I will now stop the recording.
