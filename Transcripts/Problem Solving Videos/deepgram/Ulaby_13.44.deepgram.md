# Ulaby 13.44 video

Deepgram general-nova-3 2025-07-31.0, request 01a1b03a-380c-7692-8fb8-cb0d7083a414, audio 21.5 min.

**[0:00:04]** Okay. So this is Ulaby 13.44, and this here is an example of computing for a transforms. Okay. And in this problem, we are given, two different functions. Alright?

**[0:00:26]** Two for the two different parts of the problem with numerical values for the parameters as specified here, and we're asked to calculate the Fourier transforms of these two functions here. So let's go ahead and start with this. The first function is f of t. It's either the minus alpha t times the sine of omega one t times the cosine of omega two t times u of t. And alpha is equal to point five inverse seconds.

**[0:01:06]** Omega one is equal to four radians per second, and omega two is equal to two radians per second. Alright? And, so we wanna compute the Fourier transform of this function here. Alright? And what we are going to do is we're going to...

**[0:01:27]** Basically, we're using the Euler identity to write the sine and the cosine as complex exponential functions. And then when we multiply all this out, we will essentially be taking the Fourier transform of a bunch of complex exponentials, which is relatively straightforward. Alright? So that's how we're gonna proceed with this. So this is going to be either the minus alpha t.

**[0:01:52]** And then for the sine of omega one t, we have one over j times two times e to the j omega one t minus e to the minus j omega one t. And then for the cosine of omega two t, we have one half times e to the j omega two t plus e to the minus j omega two t, and all this times u of t. Okay? And so if we multiply all of this out, then we get e to the minus alpha t over j times four. Right?

**[0:02:30]** The j times four in the denominator is one over j two times one half. And then for the exponentials, we get either the j omega one plus omega two t. That's this term times this term minus e to the minus j the quantity omega one plus omega two t. That's this term times this term. And then from the other two combinations, we get plus e to the j omega one minus omega two t minus e to the minus j omega one minus omega two t.

**[0:03:11]** All of this times u of t. Okay. So now we've written f of t in a form that consists of only, essentially, just complex exponential functions. So let's think about and work out what the Fourier transform is for a complex exponential general. Okay.

**[0:03:34]** So in general, right, what do we have is that the Fourier transform... Suppose we're thinking about the Fourier transform of a function e to the minus alpha t times e to the j omega naught t times u of t. Alright? Then writing that out explicitly as an integral, that's gonna be the integral from zero to infinity of e to the minus alpha t times e to the j omega naught t times e to the minus j omega t times d t. Alright?

**[0:04:13]** The u of t was factored in by taking the integral just to go from zero to infinity minus... Rather than minus infinity to infinity. And if we integrate this, alright, we have one over minus alpha plus j omega naught minus j omega times e to the minus alpha t e to the j omega naught t, e to the minus j omega t from zero to infinity. Evaluating this over here at infinity minus, its value at zero at infinity, this function inside the square brackets is zero because of the either minus alpha t. And at t equals zero, this function in the square brackets is one.

**[0:05:03]** So we just get a minus one from all of this. And then that minus one, we can multiply the denominator by that minus one. And if we do that, what we finally get is one over alpha plus j times omega minus omega naught. Okay. So that is the Fourier transform of, this complex exponential function times u of t generally, and we can use that to compute the Fourier transform of each of these four terms over here in f of t.

**[0:05:41]** Alright? So using that, right, f of omega, right, which is the Fourier transform of this function f of t is going to be one over j times four. Right? That's the constant factor that we had from here. Okay.

**[0:06:07]** And then for the four complex exponentials, we get one over alpha plus j times omega minus the quantity omega one plus omega two. It's the first one minus one over alpha plus j times omega plus omega one plus omega two. It's the second one. Plus one over alpha plus j times omega minus omega one minus omega two minus one over alpha plus j times omega plus omega one minus omega two. Alright?

**[0:06:58]** And so this is equal to one over j times four. And then what we're going to do here is we're going to take the first two terms and put them, over a common denominator, which will be the product of these two denominators here. That means that in the numerator here, we'll have alpha... We'll have this denominator, and the numerator here, we'll have this denominator. And then we'll do the same thing in combining these two terms over here over a common denominator consisting of the product of this denominator and this denominator.

**[0:07:36]** Okay. So if we do all that, then what we get from these first two terms is alpha plus j omega. Right? So this is now going to be this denominator here because we're multiplying this fraction by this in the numerator and also in the denominator. So it's alpha plus j omega plus j times omega one plus omega two.

**[0:08:04]** Alright? And then minus what we have for this numerator over here, which is going to be this denominator. So minus the quantity alpha plus j omega minus j times omega one plus omega two. All of that divided by the product of these two denominators, which is alpha plus j omega, the quantity squared, plus omega one plus omega two, the quantity squared. Alright?

**[0:08:47]** And then we're gonna do the same thing for these two terms over here. So in the numerator, we will get alpha plus j omega plus j times omega one minus omega two minus the quantity alpha plus j omega minus j times omega one minus omega two divided by the common denominator alpha plus j omega squared plus omega one minus omega two squared. Okay. So now... Alright.

**[0:09:35]** We can simplify this a little bit because we can see that, in this first term over here, in the numerator, these two terms cancel out. And these two terms can be combined to give us two j times the quantity omega one plus omega two. In this second term over here, this term and this term cancel out. And then this term and this term in the numerator can be combined to give us two j times the quantity omega one minus omega two. Okay.

**[0:10:06]** And then if we factor out those j times twos from each of these terms, then that'll cancel out with the j times four in the denominator to give us just one half. So we get one half times... And then what we have left in the first term is omega one plus omega two divided by alpha plus j omega quantity squared plus omega one plus omega two, the quantity squared. And then from this second term over here, we get omega one minus omega two divided by alpha plus j omega squared plus omega one minus omega two squared. Okay.

**[0:10:50]** And if we now substitute in the numerical values, which are that alpha is equal to point five inverse seconds, omega one is equal to four radians per second, and omega two is equal to two radians per second, then what we get is that f of omega is equal to... From this first term, have omega one plus omega two. That's four plus two. That's six divided by two. That's three divided by, alpha, which is point five plus j omega quantity squared, and then plus omega one plus omega two, that's six squared.

**[0:11:34]** That's 36. And then from the second term, have omega one minus omega two. That's four minus two. That's two times one half. That's one divided by...

**[0:11:48]** And then the denominator is point five plus j omega quantity squared plus omega one minus omega two, that's four minus two, that's two squared, that's four. Okay. So that's what we have here for f of omega. Right? The Fourier transform of, the function f of t that was given in the problem.

**[0:12:15]** Then part b of this problem is that we're given a function g of t and is equal to t times e to the minus alpha t. And, that is for zero or less than equal to t less than or equal to 10 alpha. For other values of t, this is zero, and alpha is equal to point five inverse seconds. Okay. So here, we can write the Fourier transform explicitly as an integral from zero to 10 alpha of t times e to the minus alpha t e to the minus j omega t d t.

**[0:13:01]** Okay. So now for this integral, what we want to do is I... We we can do the integral easily if we can reduce this t to just a constant. And we can do that using integration by parts. Right?

**[0:13:16]** So the integral of u times d v is equal to u v minus the integral of v times d u. So what we want to do is... Right. This is the this is the integral that we start with. This is the integral that we wanna be able to compute.

**[0:13:31]** And so what we wanna do is to choose u to be such that when we take its derivative, we get rid of this t. Okay? So we can take u, and then what's left has to be something that we can integrate. Alright? But it's just exponentials here so we can integrate those.

**[0:13:48]** So we take u to be equal to t, and then d v is either the minus alpha t, either the minus j omega t d t, alright, which we can integrate. Then d u is equal to d t, and then v is equal to minus one over alpha plus j omega times e to the minus alpha t e to the minus j omega t. Alright? So g of omega then is equal to... We started with this integral here, and then we're going to use this right hand side.

**[0:14:36]** So u times v evaluated at the limits of integration. So that's t times minus one over alpha plus j omega. So that's minus t over alpha plus j omega. Okay. Times these exponentials, e to the minus alpha t, e to the minus j omega t evaluated from zero to 10 alpha.

**[0:15:00]** And then we have minus the integral of v d u. V is this expression here. So this minus and this minus will cancel out. So we get plus one over alpha plus j omega. Right?

**[0:15:13]** That's this one over alpha plus j omega here times the integral from zero to 10 alpha of e to the minus alpha t e to the minus j omega t d t. Alright? And so from this first term over here, when we evaluated at the upper limit of integration, we get minus t, which is minus 10 alpha over alpha plus j omega times e to the minus alpha plus j omega times 10 alpha, which is t. And then at the lower limit of integration, which is t equal to zero, then this t over here will give us a factor of zero. So this whole...

**[0:15:58]** So this will be zero. Okay? Then from the integral, we get one over alpha plus j omega. And then integrating these complex exponentials, we get e to the minus alpha t, either the minus j omega t divided by minus the quantity alpha plus j omega evaluated at zero and ten alpha. Okay.

**[0:16:28]** So I then just carrying over this first term over here, we have minus 10 alpha over alpha plus j omega times e to the minus alpha plus j omega times 10 alpha. And then we have minus, that's this minus sign over here. Then in the denominator, we have alpha plus j omega, the quantity squared. That's this factor and this factor. And in the numerator, we have this evaluated at 10 alpha minus this evaluated at zero.

**[0:17:06]** So we have e to the minus alpha plus j omega times 10 alpha minus... And then a t equal to zero, the numerator is just one. Okay. So now, remember, alpha is equal to point five inverse seconds. So if we take that value for alpha and plug it in here, then what we finally get for g omega is minus 10 alpha.

**[0:17:40]** Alpha being minus... Being point five is minus five over point five plus j omega. Then we have e to the minus and then 10 alpha, that's five times point five plus j omega. Alright. Minus.

**[0:17:59]** And then we have e to the minus five times point five plus j omega minus one divided by point five plus j omega, the quantity squared. Right? And so this is the Fourier transform of the function g of omega. Right? Sorry.

**[0:18:24]** G of t that we were given in the problem. Okay. So what are some of the key points here if we think back on what we did in this example? Alright. The first is that when we did part a of this problem, right, back here, we were able to make it relatively simple by converting everything to complex exponentials using the Euler...

**[0:18:53]** Essentially, the Euler identity. Alright? And that actually made it quite a bit simpler to compute the Fourier transform because you were just computing the Fourier transform of complex exponentials, which as we saw here is quite straightforward to do. Alright. So first point that we can note here is that complex exponentials and the Euler identity.

**[0:19:23]** Okay. These often... And in this case, I did, I can simplify the computation of Fourier transforms, particularly Fourier transforms that involve trigonometric functions. Right? Because we can convert those to complex exponentials.

**[0:19:51]** And then, if we're multiplying a bunch of trigonometric functions together, then all we get is a combination of terms that are all just complex exponentials, and the Fourier transforms of those are easy to compute. Then, the second thing that we noted here, was that we saw in part b that if we had Fourier transforms of functions that have, factors that are polynomials of t, then we can use integration by parts to get rid of those, factors of t. In this case, it was just a linear term in t, linear factor in t, and, to get back to essentially just, complex exponentials again. Right? So for Fourier transforms, functions with factors of t or more generally t to the n, right, then integration by parts is often useful.

**[0:21:04]** Okay. If we were t to some power, then, we could do multiple n, basically, successive integrations, by parts, and that would bring us down back eventually to, just having a constant again. Okay. So that is it for, this example, and I will now stop this recording.
