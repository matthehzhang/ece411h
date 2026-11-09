# Ulaby 13.16 video

Deepgram general-nova-3 2025-07-31.0, request 01a1b03a-35e6-73b3-8a73-a272fa10ca11, audio 34.4 min.

**[0:00:04]** Okay. So this is Ulaby problem 13.16, and this is an example of how we calculate Fourier series coefficients. So this is an example of the calculation of Fourier series coefficients coefficients. Okay. And in this problem here, we have two different waveforms, alright, shown in these images here.

**[0:00:39]** And the problem gives us... The problem statement gives us the form of the Fourier series expansion for f one of t, this one here, and it asks us... Let me move this down a little bit. Okay. It asks us to...

**[0:01:00]** Knowing the Fourier series expansion of this function here to deduce what the Fourier series expansion is for this function down here. So what we'll do in this example is instead of just taking this Fourier series expansion as a given, we'll actually look at this function and we'll calculate this. And then once we've done that, we'll see how this Fourier series expansion for f one can be used fairly straightforwardly to deduce what the Fourier series expansion is for this function f two over here. Okay. So let's go ahead and get started.

**[0:01:39]** If we look at this graph of f one, then we can deduce pretty easily what the corresponding analytical expression, for this is. Because the period of this is four seconds, and, in each period, f one of t increases linearly with time from zero to 20, and then it just repeats that every four seconds. Okay. So from that, what we can deduce is the following. Okay.

**[0:02:14]** So for f one of t, right, we have the following analytical expression, okay, which will be useful to us in explicitly computing the Fourier series coefficients for f one. Alright. So we can see pretty easily that f one of t is equal to five times the quantity t minus n times capital t. And that's valid in the interval from n t, n capital t to n plus one times capital t, where t, the period is four seconds and n is any integer. Okay?

**[0:03:07]** So what we wanna do now is to use this analytical expression to compute the Fourier series expansion, for f one. Alright? So although it's not required for this problem... Okay. So even though it's not required, I think it's still instructive for the purposes of this example to do it.

**[0:03:31]** So now let's go ahead and compute this Fourier series. Okay. The Fourier series expansion for this function f one. So remember, the general form or a general form of the Fourier series expansion is that we can take f one of t to be equal to some constant a naught. Alright?

**[0:03:59]** And that's basically just the average value of f one of t over one period plus a sum of terms for n going from one to infinity where we take a superposition of sine and cosine functions. So it's a coefficient a sub n times the cosine of n omega naught t plus another coefficient b sub n times the sine of n times omega naught t. Alright? Where omega naught is the fundamental frequency associated one... With one period.

**[0:04:35]** So omega naught is two pi over t. And, of course, what, the Fourier series, expression tells us is that we can take any periodic function and express it as a superposition of sines and... Sine and cosine functions at frequencies that are integer multiples of, the fundamental frequency associated with a single period of that function. Another way of saying that using, more of the language of linear algebra is that we can take, the sine and cosine term, functions at those frequencies to be a basis set for expressing, any periodic function. Okay?

**[0:05:25]** And so, what we want to do now is now to calculate these coefficients a naught, a sub n, and b sub n. Alright? So let's start with a naught. Alright? So you may recall from class that, we can compute a naught by taking the average of f one of t over one period.

**[0:05:49]** So it's one over t times the integral from zero to t. This is capital t here of f one of t d t. Right? So, hopefully, you can see, pretty clearly this is just taking the average of f one over one period. So f one of t, right, is five, four.

**[0:06:06]** The interval zero to t is just five times t. So this is gonna be five. And then capital t is equal to four. So it's five fourths times the integral from zero to four of t dt. Alright.

**[0:06:20]** So this is a very easy integral to do. So this is five fourths times, t squared over two evaluated at zero and four. Right? So it's five fourths times... And then evaluated at four, t squared is 16 over two.

**[0:06:38]** Evaluated at zero, it's just zero. Okay? And then we can calculate this quite easily. So we have 20 over two, which is just 10. Right?

**[0:06:49]** So a naught is 10. Right? And in fact, if you look back at the graph of fund... Of the function f one, right, just essentially by looking at it, and thinking about it a little bit, we can see pretty easily that, the average of f one over one period, right, is 10. Right?

**[0:07:10]** Because this is a linear function. It goes from zero to 20, so its average, should be the midpoint, which is 10. Okay. So we can make a little note here in our thinking about this that a naught, alright, the constant coefficient in the four e series expansion, it's really just the average value, alright, of f one of t over one period, capital t. Alright?

**[0:07:48]** So we calculated it explicitly here, but one can, deduce that in other ways, in many cases. Alright? And and any correct way will be valid and will give the correct answer. Okay. So now let's go ahead and try to calculate the coefficients a sub n.

**[0:08:07]** Alright? So in general, the coefficient a sub n is equal to two over t times the integral from zero to t of f one of t times the cosine of n times omega naught t dt. Okay. So we, arrived at this result in class. Right now, we'll see an example of, the calculation, of this coefficient.

**[0:08:40]** Alright? And, again, using the language of linear algebra, a... Another way of thinking about this expression is, to recognize that if we take the sine and cosine functions at these different frequencies to be our basis elements for expressing f one of t, then we're getting the coefficient for, this particular basis element, cosine, of n omega naught t, by taking the projection, which in this case is the integral of f one of t onto the spaces function. So it is analogous if you think just about vectors, say, in three dimensions to taking the dot product of some vector with one of the basis elements. Alright?

**[0:09:26]** But this is a more general way of implementing that concept. Okay. So, let's go ahead and try to calculate this now. Alright. So remember t, capital t is four, four seconds.

**[0:09:40]** So we have two over four in front of the integral. Then we have the integral from zero to four. And then f one of t, over that interval is just five times t. And then we have the cosine of, remember, omega not is two pi over t, so two pi over four. So this is two pi n over four times t d t.

**[0:10:03]** Alright? So this is now... If we multiply out these coefficients in front, two over four is one half, and then we pull the five out of the integral. So we have five halves times the integral from zero to four of t times the cosine. And then the argument of the cosine, we can simplify to pi times n over two times t d t.

**[0:10:28]** Alright? So now there are a variety of ways, that we could compute this integral. Alright? Well, here, we will do it fairly explicitly. Alright?

**[0:10:40]** And the way that we will do it is to shift it by two seconds in time. Right? So we wanna shift by two seconds in time. Or equivalently, we wanna do a change of variables. We'll call our new variable tau.

**[0:10:59]** Right? The Greek letter tau, and we'll take that to be t minus two. Or equivalently, the t is equal to tau plus two. Okay. So now if we change our variable of integration from t to tau, then we get five halves times the integral now from tau going from minus two to two, alright, instead of t going from zero to four.

**[0:11:24]** And then, we have t, which is tau plus two times the cosine of pi n over two times t, which is again tau plus two d tau. Alright? And we can write that as, just simplifying it a little bit. Five halves times the integral from minus two to two of tau plus two times the cosine of, and then we just multiply this out. Pi n over two times tau plus pi...

**[0:12:04]** Oops. Tau plus pi times n d tau. Right? And so now, we will multiply out, this tau plus two, right, times the cosine, and we'll separate this out into two separate integrals after doing that. So we're gonna have the, five halves out in front.

**[0:12:36]** And then from the first term, we would have the integral from minus two to two of just tau times the cosine... Oops. Okay. Cosine of pi n over two tau plus pi n d tau. And then the second term will be two times the integral from minus two to two of now just the cosine of pi n over two times tau plus pi n, again, d tau.

**[0:13:12]** Alright? So now we have these two integrals. And if we look at them, we can see that the second integral is clearly equal to zero because what we're doing is we're integrating, the cosine function over some integer number of periods. Alright? With the phase shift, but the phase shift, it doesn't matter.

**[0:13:36]** Right? And the number of periods over which we are integrating is just equal to n, right, which is always an integer. So, so that integral is always zero. Alright? What about the first integral over here?

**[0:13:51]** Well, we're integrating from minus two to two. Tau is an odd function. Right? The cosine is an even function. So when we are integrating, an odd...

**[0:14:08]** So an odd function times an even function is an odd function. And when we integrate over, when we integrate an odd function over an integral that's centered at zero, which this is, then that integral is going to be equal to zero as well. Alright? So what we have finally then is that all the coefficients a sub n are equal to zero. Okay.

**[0:14:35]** Now, could we have figured this out some other way? Well, let's go back here and look at f one of t. Alright? So if we take f one of t and, shift it down by 10, right, by this... By its average value.

**[0:14:57]** Right? Then once we do that, we can see that f one of t is, you know, shifted down by 10. So f one of t minus 10 is going to be an odd function. Alright? So if we go from t to minus t, then, f one of t minus 10 changes sign.

**[0:15:19]** Okay. So it's an odd function. And in our expansion here, the coefficients a sub n are for the cosine functions, and the cosine is an even function. Alright? So the projection of an odd function onto an even function is always going to be zero.

**[0:15:36]** Right? And we see that here explicitly, having calculated, this integral here, which is that projection. Okay? So if we... In general, if we have some odd function, right, for which we are trying to compute the, Fourier series expansion, right, then the coefficients of the cosine terms are always gonna be zero.

**[0:16:01]** Okay? Because an odd function will have no, even function components. Similarly, if we have an even function for which we are trying to compute the Fourier series expansion, that even function will not have any, will have not any nonzero coefficients for the sine terms, right, because the sine is an odd function. Alright? And so that's a useful property, alright, for a series expansions to, keep in mind.

**[0:16:38]** Here, we saw it explicitly by actually computing, the coefficients for the cosine. So we should note here, alright, that we could also deduce that all the a sub n's will be equal to zero for all n's not equal to zero. Right? For n equal to zero, it's different because, f one of t has a nonzero average value. Right?

**[0:17:08]** And and a naught is the average value over one period. So this is zero. Right? All these other coefficients are zero because f one of t minus 10. Right?

**[0:17:20]** So that is shifted, by its average value. Right? This is obviously an odd function. Right? We can see that from the plot.

**[0:17:35]** Right? Whereas the cosine of n omega naught t, right, is an even function. Alright? And it's even for all values of n not equal to zero, right, which is... Which are the term...

**[0:17:57]** The ones that are relevant for computing these a sub n's with n not equal to zero. Right? And then also, I... The cosine is also an even function for n equal to zero as well, although that doesn't come into play explicitly for the a sub n's where n is not equal to zero. Okay.

**[0:18:21]** So those are the coefficients for the cosine terms in the expansion. They're all zero. Alright? What about the coefficients for the sine terms, b sub n? Those, we saw in class, alright, could be computed as two over t times the integral from zero to t of f one of t times the sine of n omega naught t d t.

**[0:18:49]** Alright? And so, if we just plug in capital t and f one of t, we get two over four. Right? Because capital t is four times the integral from zero to four of five t. Right?

**[0:19:03]** That's f one of t times the sine of two pi n over four. Alright? Omega naught is two pi over capital t. So it's two pi over four times n times t dt. Alright?

**[0:19:20]** And, we can write that as, again, five halves. Right? Taking all the constants out in front times the integral from zero to four of t times the sine of pi n over two times t dt. Okay. So now here, in computing this integral, alright, what we're going to use is integration by parts, alright, which is an integration method that should suggest for an integral like this.

**[0:19:57]** Because when we integrate by parts, we can bring down the power of, this factor t over here by one so that it just becomes a constant. Alright? So remember that integration by parts says that the integral of u dB is equal to u times v minus the integral of v to u. Right? So the integral of u d v is what we're starting with, and what we wanna do is to figure out, in the integrand here, what should we pick u to be, what should we pick d v to be, in order to, be able to compute this integral over here.

**[0:20:35]** Alright? And, our goal is to, take this, factor of t down to a constant. Alright? So that means that we should take u to be equal to t. Alright?

**[0:20:51]** And d v then is everything else, which is the sine of I n over two times t d t. Alright? Then d u is equal to d t, and then v is equal to, it's the integral of the sine of pi n over two times t, which is minus two over pi n times the cosine pi n over two times t. Okay. And so now, using the integration by parts formula here.

**[0:21:24]** Alright? Then what we have is that b sub n is equal to five halves. And then for u times v, right, we have... And we're gonna be evaluating this at the limits of integration. It is minus two over pi n times t times the cosine of pi n over two times t evaluated at zero and four, the limits of integration.

**[0:21:59]** And then for minus v d u, right, we have minus minus, so that's plus. Then we have two over pi n times the integral from zero to four of the cosine of pi n over two times t times d t. Right? So the cosine of pi n over two t dt. Alright?

**[0:22:26]** So... Alright. We've done what we wanted. We got rid of the t in the integral. Alright?

**[0:22:32]** So then here, alright, this integral here is zero. Okay? Because, again, we're integrating, cosine function over an integer number of full periods. Alright? So that integral is going to be zero.

**[0:22:53]** And so what we are left with is five halves, okay, times, and then it's minus two over pi n. Alright? Times... And then, so we're evaluated at four. T is four.

**[0:23:18]** And then the cosine of pi n over two times t, is going to be the cosine of two pi n, which is always one. Alright? And then when we evaluate this at the lower limit, it's zero because we have t equal to zero over here. Right? So, this is what we have for our result.

**[0:23:39]** And if we multiply this out, right, it's just five times four, times minus one, which is minus 20 over pi times n. Okay. So that is what b sub n is. Alright? And now that we have a naught, a sub n, and b sub n, then we can see that f one of t...

**[0:24:08]** Alright. It's a naught. If you go back up here, to the general form of the Fourier series expansion, it's a naught, which is 10. Alright? Plus the sum of a sub n times cosine of n omega naught t.

**[0:24:24]** All these a sub n's here for n not equal to zero are zero, plus b sub n times, the sine of n omega naught t. So the b sub n's we just computed, they're nonzero. So we just have to substitute them into this expression here. Alright? So we get that f one of t is equal to a naught, which is 10, minus 20 over pi.

**[0:24:47]** That's the 20 over pi from what we just calculate. That's the minus 20 over pi from what we just calculated for b sub n times the sum. N goes to one to infinity of one over n. Right? That's this one over n from b sub n over here times the sine of pi n over two times t.

**[0:25:09]** Okay. And if we look at that expression and compare it to what was given in the problem up here, alright, it's the same. Okay. So indeed, we've gotten the correct Fourier series expansion, at least the same as the one that's given to the book, which is which is the correct one. And, so that result checks out.

**[0:25:34]** Okay. Next, what we wanna do is to figure out how the function f two is related to f one. And then from that, to see if we can then easily deduce from the Fourier series expansion for f one that we just calculated what the Fourier series expansion for f two is over here. Alright? And so if we look at f one and f two, we can see that there are a few relatively straightforward differences.

**[0:26:06]** One is that the amplitude of f two is twice the amplitude of f one. Right? It's a total range of 40 rather than 20. Alright? So we'll need to take f one and increase scale it, by a factor of two.

**[0:26:24]** Okay? Then you can see that it's, shifted down so that its average value is zero. Okay. So we're gonna have to... After multiplying this by two, we're gonna have to shift it down by 20, okay, to get f to get f two.

**[0:26:43]** And then we can see that the period of f two is eight seconds, whereas the period of f one is four, but it's still a linear function in here. So that means that, from f one of t, what we'll wanna do is to take the time axis and divide by two. Alright? And that'll scale out, the period accordingly. So instead of having f one of t, what we really want is f one of one half t.

**[0:27:14]** Okay. So putting all of that together, right, basically, what we can see is that from the plots of f one of t and f two of t. Alright. We can see that as I just described, f two of t is equal to two times f one of one half t minus 20. Right?

**[0:27:47]** This factor of two over here is the vertical scaling by a factor of two. This minus 20 is the downward shift, And then this one half t is expanding out the time axis so that we get twice the period for f two as we had for f one. Okay? And so now here, since we have the four a series expansion for f one of t, alright, all we have to do is to use that for, now f one down here where we have one half t instead of t, and then that'll give us the four a series expansion for f two of t. Right?

**[0:28:24]** So if we just go ahead and do that, then what we get is that f two of t is equal to, right, two times f one of half t. So it's two times 10, which is 20, minus... And then two times... 20 over pi is... So minus 40 over pi times the sum from n equal to one to infinity of one over n times the sine of.

**[0:28:55]** And then instead of t, we have one half t in the argument. So it'll be pi n over four times t. Okay. And then, minus 20 over here. Okay.

**[0:29:13]** And we can simplify this a little bit. Alright? Because the 20 here and the minus 20 here cancel each other out. And so what we get finally is that f two of t is equal to minus 40 over pi times the sum from n equal to one, to infinity of one over n times the sine of pi n over four times t. And that's the answer.

**[0:29:44]** Okay. So, so this is an example of, calculating a Fourier series coefficients and using, the result for one, function to deduce the four a series expansion for, a function that is similar in a certain key ways. Okay. So if we look back at this, what are some of the key points here? Okay.

**[0:30:11]** In, thinking about this retrospectively having worked out the answer. One is that when we calculated the Fourier coefficients, it was basically just doing a bunch of integrals. Okay. So the calculation of the Fourier series expansion for f one of t. Right?

**[0:30:41]** This... Basically, what it involved was a bunch of straightforward integrals. Alright. And, as we saw, at various stages in this process, there were certain coefficients that, we could see in retrospect, should be zero, just by applying some simple symmetry arguments. Right?

**[0:31:12]** And certain coefficients. Alright, can be seen to be zero, alright, essentially by symmetry arguments. Okay. For example, the arguments that we made based on, whether functions were even or odd. Okay.

**[0:31:44]** Then, the second point here, right, which relates to, the question that was more explicitly asked for, asked in in this problem is that if we're given the Fourier series for one function, then we could straightforwardly deduce what the Fourier series would be for another function that was related to it in some... In in certain ways by scaling either the vertical or the horizontal axis and also shifting vertically along the vertical axis. Alright. So given the four a series for the function f one of t, which was actually given in this problem, although we saw how that was calculated as well, then computing. And it's really more deducing than computing I here.

**[0:32:44]** The four a series for f two of t, it was relatively easy once we saw how f one and f two were related to each other. So what we needed to do was that we needed to recognize how f one of t, right, basically, could be transformed. Into f two of t, alright, by a combination of a vertical shift or actually, probably to put this in the most appropriate order, a scaling by a factor of two, doubling of the period and then vertical shift, okay, of of that result. Okay. And then applying the same transformations to the Fourier series expansion for f one of t, then gave us directly the Fourier series expansion for f two of t.

**[0:34:16]** Okay. So that is it for this example, and I'll stop the recording now.
