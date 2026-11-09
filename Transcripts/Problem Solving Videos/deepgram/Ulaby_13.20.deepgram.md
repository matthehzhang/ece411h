# Ulaby 13.20 video

Deepgram general-nova-3 2025-07-31.0, request 01a1b03a-626f-7ee2-8e35-5b03af147a42, audio 59.2 min.

**[0:00:03]** Okay. So this is Ulaby problem 13.20. Okay. And this is an example of circuit analysis. Using Fourier series.

**[0:00:25]** Okay. So the problem that we have here is that we are given this circuit here that has two inductors, and we're told that, the source of voltage, v sub s over here, is given by this waveform. Okay? And what we need to do is first to calculate the Fourier series representation of I of t. Right?

**[0:00:49]** So we'll need to analyze this circuit using a Fourier series expansion for b sub s. Okay, we need to come up with that expression in terms of, these parameters r one and r two, l one and l two. Then in the second part, what we're asked to do is to calculate numerically the first five terms in this Fourier series expansion of I of t using these numerical values, and then construct a plot of I of t and v s of t from their Fourier series expansions. Okay. So let's go ahead, and we'll start off as usual by redrawing the circuit and the key...

**[0:01:34]** Collecting the key pieces of information. Okay. So the circuit is like this. K. So two resistors, two inductors, and a voltage source.

**[0:01:50]** This is v sub s of t. The resistors are r one and r two. The inductors are l one and l two. Okay? And v sub s of t.

**[0:02:07]** Right? This is time in milliseconds. You know, one millisecond, two milliseconds. This is zero, say minus one. Okay.

**[0:02:18]** And then we have two volts and 10 volts. Okay. And the input voltage v sub s basically looks like this. It's a square wave, okay, that goes between two volts and 10 volts with a period of two seconds. Alright.

**[0:02:51]** So the period here... Or two milliseconds rather is two milliseconds. Okay? And so what we're asked to do is basically to solve for I of t. Right?

**[0:03:08]** And then once we have that, then we want to obtain some numerical values and plots using the following numerical values for the circuit parameters. The resistances are 10 ohms, and the inductances are 10 millihenries each. Okay. So this is the problem that we're solving. Part a is to compute I of t in terms of r one, r two, l one, and l two.

**[0:03:41]** So the first step in that is going to be compete... To compute the Fourier series for v sub s of t. Alright? And that will give us the, basically, the phasor components in, v sub s in the phasor domain or in the frequency domain. Okay.

**[0:04:05]** So v sub s is this function over here, and we can see that, alright, the period as we noted is two milliseconds. So that means that the fundamental frequency omega naught, which is two pi over the period, is 1,000 pi radians per second. Okay? And the Fourier series expansion for v sub s of t is a naught plus sum from n equal to one to infinity of a sub n times the cosine of n omega naught t plus b sub n times the sine of n omega naught t. Alright?

**[0:05:03]** And we wanna calculate these coefficients. Okay? So a naught. Right? Remember, this is just the average value of, v sub s of t.

**[0:05:15]** Okay? So it's going to be one over the period. So one over two milliseconds. We'll write the... Milli is just a small n.

**[0:05:22]** Let's remember that that means a factor of 10 to the minus three. Okay. And then we're gonna integrate from zero to one millisecond. Alright. If we look at this waveform here, from zero to one millisecond is just two d t.

**[0:05:41]** That's two volts. And then from one millisecond to two milliseconds, alright, that's from here to here, it's 10 volts. So 10 d t. Okay. And so this is now, right, it's 10 plus two.

**[0:06:03]** Alright. When you do the integrals, divide it milli, divided by two milli. So we have 10 plus two, which is 12 milli divided by two milli, and that is just six. Okay? And if we look at this waveform here, then, hopefully, it's fairly clear to you that, in fact, the average value of this over one period from, time zero to time two milliseconds, the average value of this, blue waveform here is in fact six volts.

**[0:06:33]** Alright. And that's what we just calculated. Okay. What about the coefficients a sub n? That is the coefficients of the cosine terms in the expansion.

**[0:06:44]** Those coefficients are actually all zero. Okay. And the reason for that is that the cosine function is an even function of t. But looking at the waveform here, we can see that the waveform is clearly... Right?

**[0:06:59]** If if we shift it, down by its average value, that is by six, we can see that the waveform is clearly an odd function. Okay. Once it's been shifted down. So... Right.

**[0:07:14]** An odd function will not have any even Fourier components in it. So all the coefficients a sub n for n not equal to zero are zero. Right? And this is because the function v sub s of t minus its average value a naught has odd symmetry. So it has no even function components to it.

**[0:07:41]** Okay. What about the coefficients v sub n for the sine terms of the expansion? Right. These are given by the expression two over t times the integral over one period, so from zero to t, of v sub s of t times the sine of n omega naught t dt. Okay?

**[0:08:05]** And so this is going to be two over two... Over capital t, which is 2,000,002. Alright. And then, we have for the end... For this integral, right, v sub s has two different values.

**[0:08:21]** Either it's two volts from zero to one millisecond and it's 10 volts from one to two milliseconds. So we're gonna break this up into two integrals. The first one is two times the integral from zero to one millisecond of the sine of 1,000 pi n t d t. And then the second is 10 times the integral from one millisecond to two milliseconds of the sine of 1,000 pi n t d t. Okay.

**[0:09:07]** So now, let's just go ahead and compute these integrals. Alright. So for this factor on the outside, two over 2,000,000, that's one over... And then we'll write million now as explicitly 10 to the minus three. Okay.

**[0:09:23]** And then when we do, this first integral, right, we have the factor of two. And then when we integrate the sign, we get a factor of one over minus one over 1,000 pi n in front. So we have minus two over 1,000 pi n in front, and then the cosine of 1,000 pi n t. Right? Evaluated from zero to one millisecond minus 10, and then, it's the same integrand.

**[0:09:57]** So, it's 10 over 1,000 pi n. We get the minus sign here from doing the integral as well, and then it's the cosine of 1,000 pi n t, from one milli to two milli. Okay. All of that times, this leading factor of one over 10 to the minus three. Okay.

**[0:10:24]** So now, we'll pull out the factor of minus one in front, and we'll pull out this factor of 1,000 pi in the denominator, of each term out in front as well. So the one thousands time 10 to the minus three will just give us one. Right? So we get minus and then it's one over pi since we put... We're pulling out this pi over here as well.

**[0:10:49]** And also, we'll pull out the factor of n and then the denominator. So minus one over pi times n. And then for the first term over here, we have two. Right? We've pulled out the factor of minus, one over 1,000 pi times n times...

**[0:11:08]** And then, we have, the cosine of... And then it's 1,000 pi times n times 10 to the minus three. So that's just, the cosine of pi times n minus the cosine of... And then at the lower limit t is equal zero. So it's just the cosine of zero, which is one.

**[0:11:32]** Okay. And then for the second term over here, again, we've pulled out the factor of minus one over 1,000 pi n. So we have plus 10 times, the cosine of 1,000 times milli, that's one, times t, that's two. So two pi... The cosine of two pi n, which is one, right, for all integer values of n.

**[0:11:57]** Alright. Minus... And then we have the cosine of pi times n when we evaluate, this at t equal to 1,000,000. Right? Because it's the cosine of 1,000 times 10 to the minus three, that's one times pi times n.

**[0:12:14]** So just the cosine of pi times n. Alright? All this times minus one over pi n. Okay. And, if we just simplify this a little bit, we have minus one over pi times n.

**[0:12:30]** And then we have minus two plus 10, that's eight. And then we have two cosine of pi n minus 10 cosine of pi n. So that's minus eight times the cosine of pi n. Okay. Or, we can write that as eight over pi times n times the cosine of pi times n minus one.

**[0:12:59]** Okay. And so that is b sub n. And so now we can take these values that we've computed for a naught, which is six, a sub n, which is zero, and b sub n, which is this expression down here. And we'll just plug them back into this Fourier series expansion over here. And if we do that, what we get is that b sub s of t is equal to six plus...

**[0:13:35]** And then it's eight over pi times the sum and going from one to infinity of the cosine of pi n minus one divided by n. Alright. That n is this n over here. Okay. Times the sine of 1,000 pi n t.

**[0:14:03]** Alright? Now we can simplify this a little bit more by noting that the cosine of pi times n minus one is equal to... If n is odd, right, then this is equal to minus two because the cosine of pi n for n odd is minus one. So this is minus two if n is odd, and it's zero if n is even because the cosine of pi n of n is even is, just equal to one, and one minus one is zero. Okay?

**[0:14:39]** And so we can also write that v sub s of t is equal to six and then minus 16 over pi times the sum over odd values of n going up to infinity of one over n times the sine of 1,000 pi n t. Alright? So that's, those are both correct ways of writing the Fourier series expansion for v sub s of t. Okay. Now once we have that, right, what we want to do is to analyze, the circuit in the phasor domain.

**[0:15:26]** Because now what we have is v sub s of t expressed as a linear combination or a superposition of, multiple frequency components where the frequency... The angular frequencies are 1,000 pi n. Okay? So what we do next then is to analyze, the circuit in the phase domain. Okay.

**[0:16:00]** And so, let's take v sub s of t here. Alright? And we'll express it in the standard cosine form, which means converting this sine into a cosine by including a phase shift of minus 90 degrees. Alright. So we can write v sub s of t as being equal to six minus 16 over pi times the sum over odd values of n going to infinity of one over n times the cosine of 1,000 pi n t minus 90 degrees.

**[0:16:38]** Okay? And we can write that as in a slightly different way, six minus 16 over pi times the sum over odd values of n going up to infinity of one over n times the cosine. And instead of writing a thousand pi n all the time, we'll just write that as omega sub n times t minus 90 degrees, where omega sub n is 1,000 pi times n. Okay. So now that we have v sub s of t with each of its terms in the standard cosine form, then what we wanna do is to write it in the frequency domain essentially as a superposition of phasors.

**[0:17:30]** K. So we get the v sub s is equal to six. Alright. That's the constant terms... Term.

**[0:17:36]** Alright. And then plus 16 over pi times the sum over odd values of n going up to infinity of one over n times a phase factor either the j times 90 degrees. And the way that we arrived at that was we recognize that we have the minus sign over here. Alright? And then we...

**[0:18:03]** From this cosign over here, we would have ordinarily e to the minus j times 90 degrees. But if we take minus e to the minus j times 90 degrees, right, that is minus... And then e to the minus j times 90 degrees is minus j. So that's just j, and that is the same as either the j times 90 degrees. Okay.

**[0:18:29]** So that's how we convert this minus sign here to a plus sign, and we get this phase factor either the j 90 degrees over here. Okay. So now we have, our source v sub s in, the frequency domain, essentially in phasor form. Okay. And so now we want to write down, the circuit in phasor form as well.

**[0:19:00]** K. We're equivalently just in the frequency domain. Okay. So now we have our voltage source in phasor form, resistors r one and r two, and then the impedances in the frequency domain of the inductors are j omega l one and j omega l two. And we're gonna try to compute the current here as a phasor as well.

**[0:19:30]** And to do that, what we'll do is we'll... Essentially, we'll use a simple node voltage analysis. We'll take the bottom node, to have a voltage of zero. That means that this node up here, it has a voltage v one. And what we're gonna do is to solve for v one, alright, just by applying KCL, at the node v one.

**[0:19:52]** And then I, we can see very easily, is just v one divided by r two plus j omega l two. Okay. So that'll be our route, to getting I in, the frequency or phasor domain. Once we have that, then, we'll be able to translate it back into the time domain. Alright?

**[0:20:14]** Using sort of the inverse of the process that we use to cat... To get capital v sub s over here. Okay. So now we wanna apply KCL at the node v one. Okay?

**[0:20:27]** And so that means then just that, right, we take the sum of the outgoing currents to be zero. Current going out to the left is v one minus v s over r one. The current current going down through, the inductor j omega l one is v one over j omega l one. And then the current going out to the right is v one divided by r two plus j omega l two. And those all have to add up to zero.

**[0:21:04]** So now if we group together all the terms proportional to v one, we get one over r one plus one over j omega l one plus one over r two plus j omega l two. All this times v one is equal to v s over r one. That's from this term over here, which loses this minus sign when we move it to the right hand side of the equation. Okay. And so then dividing both sides of that equation by this big expression in the parentheses, then what we get is that v one is equal to v s divided by r one times this expression here in the parentheses.

**[0:21:57]** So that is one plus r one over j omega l one plus r one over r two plus j omega l two. Alright? And so now from here, okay, what we can say is we're gonna multiply this by r two plus j omega l two over r two plus j omega l two. Right? That basically gets rid of this r two plus j omega l two in the denominator of the denominator over here.

**[0:22:38]** Alright? And if we do that, then we get the v one is equal to v sub s times r two plus j omega l two. And then in the denominator, we have one plus r one over j omega l one. Those are the first two terms over here times this r two plus j omega l two. And then from this third term here, we just get r one.

**[0:23:08]** We multiply by r two plus j omega l two. So plus r one. Alright? And, if we just take this denominator and multiply this here out a little bit more and then group together the real terms, and separately the imaginary terms, then what we get is in the denominator, the same thing, v s times r two plus j omega l two. And then divided by in the denominator, we have r one from over here.

**[0:23:44]** And then from r two times one, we have plus r two. And then the other real term comes from r one over j omega l one times j omega l two, which gives us r one times l two over l one. Then we have the imaginary terms from, the cross terms in in this product. So we have from, r one over j omega l one times r two, we get minus j times r one r two over omega omega l one. So j times minus r one r two over omega l one.

**[0:24:26]** Alright. We get the minus sign by moving the j from the denominator to the numerator. And then plus one times j omega l two, which is j times omega l two. Like this. Okay.

**[0:24:42]** So that's v one. Alright. Now to get the current I, we take v one and divide by r two plus j omega l two. Alright? So that basically cancel that division, cancels out this r two plus j omega l two in the numerator.

**[0:25:04]** So that means that we get that I, which is v one over r two plus j omega l two, is equal to just v sub s in the numerator divided by the same denominator, which is r one plus r two plus r one l two over l one plus j times minus r one r two over omega l one plus omega l two. Okay. So now here, we will, clean this up a bit more, by getting rid of the fractions in the denominator. We will do that by multiplying, the numerator and the denominator by, j omega l one. So j omega l one over j omega l one.

**[0:26:03]** Okay. And when we do that, then what we get is in the numerator, we have j omega l one times v sub s, which we'll write at the end, divided by n in the denominator, we get... Right now, we'll write the real terms first. Right? So the real terms come from here.

**[0:26:24]** So we have j times j, which is minus one. So minus one times minus r one r two, then the omega l one, they're canceling out with the omega l one in the denominator over here. So we just get plus r one r two. And then from the second term, we get minus from j times j omega squared l one l two. So minus omega squared l one l two.

**[0:26:53]** And then from j omega l one times this first set of terms over here, we get plus j omega, and then it's l one times r one plus r two plus r one l two. Alright? All of this times v sub s. Alright? Here now, right, this is I as a function of any frequency omega.

**[0:27:26]** Right? But we are specifically concerned here since we're working with Fourier series with omega being able to n times the fundamental frequency omega naught with omega naught equal to 1,000 times pi. Alright? And so if we, substitute for omega, if we substitute n times omega naught, then what we get is that the current I is equal to j times n times omega naught l one divided by r one r two minus n squared omega naught squared times l one l two plus j times n times omega naught times l one r one plus r two plus r one l two. Alright.

**[0:28:31]** All of this times v sub s. Okay. So now, alright, what we wanna do is we wanna take this prefactor here for v sub s, alright, and write it in polar form. Alright? That is with a magnitude and a phase angle.

**[0:28:57]** Okay? And so the magnitude of this is going to be just the magnitude of the numerator divided by the magnitude of the denominator. Right? The magnitude of the numerator is clearly just n omega naught L1. Alright.

**[0:29:11]** So we have N omega naught L1 in the numerator. And then the magnitude of the denominator is the square root of the real part squared plus the imaginary part squared. Alright? So we're gonna get the square root of r one r two minus n squared omega naught squared l one l two quantity squared plus n squared omega naught squared times l one r one plus r two plus r one l two quantity squared. All of this under the square root.

**[0:29:59]** And then we have phase factors. So we're going to have e to the j 90 degrees. That's from this factor of j that was here in the numerator. Right? So we can't forget about that.

**[0:30:16]** And then if we take the... This denominator here to have a phase angle of phi, then, we're going to get a phase factor in the numerator of either the minus j times phi. All of this times v sub s. Alright. This v sub s is this v sub s over here.

**[0:30:39]** Okay? And the phase factor phi, right, which is the phase of this denominator over here, is a 180 degrees times... Or minus the inverse tangent of l one times r one plus r two plus r one l two times n omega naught divided by n squared omega naught squared l one l two minus r one r two. Alright? So, so the way that we get the minus sign here is because we switched the order, right, of these two, terms over here.

**[0:31:29]** Right? Here, it's r one r two minus n squared, etcetera. Here, it's n squared, etcetera, minus r one r two. So that's how we get the minus sign, in front. Right?

**[0:31:39]** And, it is 180 minus this inverse tangent here instead of just being minus this inverse tangent. And, the reason for that is as follows. Right? It turns out that over here, right, the real part of this denominator here is actually always going to be negative. Right?

**[0:32:04]** And the reason for that is that n is going to be greater than or equal to one. Alright. We're, not including the constant term right now because that'll... Because of the end of the numerator, they'll turn out to be, zero. Okay?

**[0:32:21]** But what happens is that omega naught squared, l one, l two, is always greater than r one times r two for the values of, l one, l two, r one, and r two that we're using in this problem. Remember, l one and l two are 10 millihenries each, so 10 to the minus two each. Omega naught is 1,000 pi. So on the left, we're gonna get from omega naught squared. We're gonna get 10 to the six times pi squared.

**[0:32:51]** And then from l one times l two, we're going to get 10 to the minus four. R one and r two, remember, are 10 ohms each. So we're gonna get 10 to the two. Right? A 100.

**[0:33:03]** And so the left hand side is a 100 pi squared. The right hand side is a 100. Right? So clearly, this inequality always holds. And so that means that this real part in the denominator is negative.

**[0:33:18]** Okay? Let me draw a little picture here. Okay. Then... So we're looking at the denominator.

**[0:33:29]** Right? So the real part is negative. Right? The imaginary part we can see here is always positive. Right?

**[0:33:40]** So maybe up here somewhere. Right? So that means that we're always out here something like this, and so that should be the angle phi. Alright? But, actually, if we were to take the numerator or...

**[0:33:55]** So the imaginary part divided by the real part and take the inverse tangent of that, what we would actually get is this angle here. Okay? And that's not the angle. And say if you were to plug it into your calculator and do it, you would get this angle here. And so to get this angle here, we actually need to add a 180 degrees to it.

**[0:34:22]** Okay? It has the same inverse tangent, but it's in the second quadrant, which is correct rather than the fourth quadrant, which is incorrect. Okay? So that's why it's one eighty minus this inverse tangent here instead of just minus this inverse tangent. Okay.

**[0:34:39]** So that's a similar issue to what we encountered when we talked about phasors generally earlier in the semester. Okay. So now what we wanna do is we wanna take the Fourier series expansion for v sub s, which we worked out earlier. Alright? It is this up here.

**[0:35:08]** Alright? And we're gonna plug it into the expression that we had for I, and then that's going to help us to get the, the different phase or components of I. Alright? So what we need to do now is we wanna use the four a series expansion for v sub s that we worked out earlier. Right?

**[0:35:44]** So we're gonna take that and and we're gonna plug it into here for v sub s. Alright? So we're... We get that I is equal to... Right.

**[0:35:53]** So the first term in the Fourier series expansion for v sub s, if we go back up here, with six, that's at a frequency of zero. Okay? And so that corresponds to n being zero up here. Right? And so we're actually gonna get no contribution to I from that because it's six times zero.

**[0:36:17]** Right? Then for the nonzero positive values of n, right, we have plus 16 over pi times the sum over the odd values of n of one over n times e to the j 90 degrees. Alright? And that's going to be multiplying these factors over here. Right?

**[0:36:43]** So the one over n will cancel this n out over here, and then we'll have everything else. Okay. So we're gonna get plus then a 16 over pi times the sum over odd values of n. And then since the one over n in v sub s cancels out with this n over here, we just have omega naught times l one divided by... And then we have the square root of, now we'll write...

**[0:37:16]** We'll take... Since this is squared, right, we can just... I change the order of this and it doesn't matter. Right? Because minus one squared is one.

**[0:37:24]** So we have n squared omega naught squared, l one l two minus r one r two, the quantity squared, plus n squared omega naught squared times l one r one plus r two plus r one l two quantity squared. Okay. Times... And then we have e to the minus j phi. Right?

**[0:37:59]** That's this factor over here times e to the j 90 degrees. That's this factor here. And then in addition, we have from v sub s another factor of e to the j 90 degrees. Okay. And then, when we multiply these phase factors, we have either the 180 degrees here.

**[0:38:28]** From either the minus j phi, we get e to the minus one eighty degrees or e to the minus j times one eighty degrees. So those will cancel each other out. And so for the phase, we'll just have e to the plus because it's minus minus j times this inverse tangent over here. Okay. So if we write all that out, then we get I is equal to six times zero, right, which is zero.

**[0:38:57]** So just 16 over pi times the sum over odd values of n going to infinity. Then this big expression here, omega naught over l one divided by the square root of n squared omega naught squared l one l two minus r one r two quantity squared plus n squared omega naught squared times l one r one plus r two plus r one l two quantity squared, all of that under the square root. And then e to the plus j times the inverse tangent of... And then it's this argument up here. So l one times r one plus r two plus r one l two times n omega naught divided by n squared omega naught squared l one l two minus r one, r two.

**[0:40:15]** Okay. So now we wanna convert this back to the time domain, and, that is going to correspond each one of these terms in the Fourier series expansion. Alright? In the phasor or frequency domain has its corresponding time domain component, which we know how to, write, from our earlier... From our discussion of phasors earlier in the semester.

**[0:40:47]** So we just have to convert each of these phasor terms, basically, in... Back into the time domain. And then the sum of all those will then be the Fourier series expansion of IoT in the time domain. Okay. So in the time domain, right, what happens is that now this becomes the following.

**[0:41:13]** We'll see if we can fit this all on one line here. Alright. So I of t is equal to 16 over pi times the sum over odd values of n going to infinity of... Then it's omega naught l one divided by the square root of n squared omega naught squared l one l two minus r one r two squared plus n squared omega naught squared times l one r one plus r two plus r one l two squared. Alright.

**[0:41:57]** All of this. Now what the phase factor does is it contributes a phase to the cosine. Right? So now it's the cosine of n omega naught t, plus this phase, which is the inverse tangent of l one times r one plus r two plus r one l two times n omega naught divided by n squared omega naught squared l one l two minus r one r two. Okay.

**[0:42:37]** And so this is our answer for IFT in the time domain expressed as a Fourier series expansion, right, as a function of, the parameters r one, r two, l one, l two, and omega naught. Alright? So your omega naught, remember, is 1,000 times pi. Okay. So that is the result for part a.

**[0:43:18]** Then part b, right, asks us to take this expression and substitute in specific numerical values for the resistors and the inductors, right, and compute the first five terms in the four a series expansion of I of t. Right? So we take r one and r two to be equal to 10 ohms, l one and l two to be equal to 10 millihenries, And then remember, omega naught is 1,000 pi. Okay. So then, if we plug those values into this big expression up here, then what we get is that I of t is equal to 16 over pi times the sum over odd values of n up to infinity of...

**[0:44:14]** And then in the numerator, right, we have omega knot, which is thousand pi times l one, which is 10 millihenries or point o one. Thousand times point o one is 10. So we have 10 pi divided by... And then in the denominator, we have omega naught squared. So that's 10 of the six pi squared times l one times l two.

**[0:44:42]** They are each 10 to the minus two. So we have 10 to the six times 10 to the minus four. That's a 100. Then we have our pi squared and then the n squared minus r one r two. That's minus 10 times 10, which is a 100 squared plus...

**[0:45:03]** And then over here, right, we have omega naught squared. That's going to be 10 of the six times pi squared times n squared. So we have 10 to the six pi squared times n squared. And then l one times r one plus r two. R one plus r two is 20 times point o one is point two.

**[0:45:25]** And then r one l two, that's 10 times point o one. That's point one quantity squared. Okay. And then we have the cosine of 1,000 I n t. Right?

**[0:45:47]** That's n omega naught t plus the inverse tangent of... And then in the numerator here, right, that's basically just... It's the the l one times r one plus r two plus r one l two is just point two plus point one. That's point three times n times omega naught. So that's a thousand I times n divided by and then the denominator in the argument of the inverse tangent is just what's inside the parentheses here.

**[0:46:25]** Right? Because that's this expression here. So it's going to be 100 times pi squared n squared minus one. Okay? And we just simplify this a little bit more, right, then this pie and the pie down here, right, these cancel out.

**[0:46:51]** Okay? Then we get, if we take the denominator and under the square root, we factor out a factor of 10 to the fourth, then that becomes 10 to the two outside the square root. Alright? And then 10 over 10 of the two becomes a 10 in the denominator. Alright?

**[0:47:13]** And then we'll have the 16, which we can put in the numerator. Okay. So, we'll get the sum over I values of n. And then we have 16 in the numerator and then 10 in the denominator. And what we have left under the square root is going to be pi squared n squared minus one quantity squared plus...

**[0:47:42]** And then over here, we have point three squares. That's point o nine times 10 to the six. That is nine times 10 to the fourth. We factored out the 10 to the fourth. So we just have nine times pi squared times n squared.

**[0:48:02]** Oops. All of this under the square root. Then we have the cosine of 1,000 I n t plus the inverse tangent. And then all we have here from these numerical factors is point three times a thousand, that's 300, divided by 100, that's three. So that's three pi n divided by pi squared n squared minus one.

**[0:48:36]** Okay. So now that is a relatively simple form that we can then use to calculate, to do some numerical calculations. Okay. So we're gonna calculate the first five terms in the full expansion, which includes the even terms. And we...

**[0:48:58]** But we know the even terms are zero. Right? So those will be easy. So for n equal to one, we have from this prefactor here, right, it's 16 over 10 times the square root of... And then it's pi squared times one squared, which is pi squared minus one squared plus nine pi squared times one squared.

**[0:49:21]** So just nine pi squared. Alright. Times the cosine of 1,000 pi times t, again, since n is equal to one, plus the inverse tangent of, in the numerator, three pi, in the denominator, pi squared minus one. And if you calculate all that out, what you get is point one two three six times the cosine of 1,000 pi t, plus 46.74 degrees. Okay.

**[0:50:04]** For n equal to two, alright, the result is zero. Okay. We saw that earlier. For n equal to three, okay, then again using this expression here, we get 16 over 10 times the square root of, now it's going to be pi squared n squared with n equal to three is nine pi squared minus one, the quantity squared, plus... And then we have nine pi squared n squared with n equal to three.

**[0:50:37]** That becomes 81 pi squared. Okay. Times the cosine now of 3,000 pi t, right, since n is three over here, plus the inverse tangent of nine pi, that's three pi n divided by nine pi squared minus one. Okay. And if you calculate that out numerically, you get point o one seven three four times the cosine of 3,000 pi times t plus 17.85.

**[0:51:24]** Alright? Then the n equal to four term, we saw earlier. All the even terms are zero. So that term is zero. And then finally, for n equal to five, we get 16 over 10 times the square root of...

**[0:51:44]** Then it's pi squared n squared is 25 pi squared then minus one squared plus. And then we have nine pi squared times n squared. That's nine times five squared, which is nine times 25, which is 225 pi squared. All the end of the square root. And then it's the cosine of 5,000 pi times t plus the inverse tangent of three pi n, which is 15 pi divided by pi squared n squared minus one, 25 pi squared minus one.

**[0:52:24]** Okay. If we calculate that out numerically, it's point zero zero six three nine four times the cosine of 5,000 pi t plus 10.86 degrees. Okay. So all of this alright. These are the first five terms in the Fourier expansion of I of t.

**[0:53:01]** Okay. So that's part b. Then part c asks for the plots, okay, of I of t and v sub s of t. I... And so I will just take those from the solutions and paste them in.

**[0:53:43]** K. And they should show up for us shortly here. Okay. There we go. Alright.

**[0:54:03]** So what you can see here, this is v sub s. And, right, you can see that it looks, very much like the idealized waveform, that we saw in the problem statement except it has, this little ringing over here because these are computed, with a finite number of terms. And so you can still see it pretty prominently. You'll always get a little bit of this even with a large number of terms. And then down here, right, what you see is I of t.

**[0:54:35]** And so what you can see is that the the current, it is sort of gradually builds up with a time constant that is determined by the values of the circuit parameters. Okay. So this was a fairly long example. What are some of the key points that we can extract from this? Right?

**[0:55:05]** If we, go back and think about, what we did here. Right? One is that when we're doing Fourier series circuit analysis, really, what we're doing is we're breaking up our, typically, our input signals into a superposition of components at different frequencies. Alright? At any single frequency, it's really just the same as doing phasor analysis, alright, which we looked at in a lot of detail and very extensively earlier in the semester.

**[0:55:38]** And then we use the idea of superposition, which we can apply to any linear circuit to combine the results at different frequencies just by adding them together. Okay? And that's really what, for a series circuit analysis comes down for comes down to. It's breaking, our inputs up into individual frequency components, analyzing each frequency essentially, in the phasor domain, and then combining those results, which we know we can do using superposition. Alright?

**[0:56:09]** So Fourier circuit analysis or Fourier series circuit analysis, Right? Essentially, it's based on phasors. Right? Plus, it works because for linear circuits, we can do superposition. Okay.

**[0:56:43]** Another point that we can note here was... Remember, we saw that when we were computing the, Fourier series expansion of our input voltage, we saw that, all of the coefficients of the cosine terms were zero because, the signal for which we are computing the Fourier series, was, an odd function. Right? Once we subtracted off the average value and the cosine is an even function, therefore, the coefficients of all the cosine terms in the expansion have to be zero. Okay?

**[0:57:25]** And in general... Okay. These types of symmetry considerations So for example, on versus even functions. K. These types of symmetry considerations, right, they can be very powerful in determining the values of certain Fourier series coefficients.

**[0:58:18]** And in particular, in determining when some of them are zero. And then the third point that we'll note is that as we were doing this example, we had to do quite a bit of complex algebra. Okay? And so having good accuracy and proficiency in complex algebra is very helpful in solving these types of problems. Right?

**[0:58:44]** So accuracy and proficiency in complex algebra. Are important. Okay. So that is it for, this example. Okay.

**[0:59:09]** And I will now stop the recording.
