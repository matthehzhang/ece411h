# Ulaby 12.5 video

Deepgram general-nova-3 2025-07-31.0, request 01a1b039-d9cf-7cc0-aa95-8c2e19f66580, audio 67.1 min.

**[0:00:05]** Okay. This is Ulaby problem 12.5, and this is an example of the calculated... Several examples of the calculation of Laplace transforms. K. So this is an example of calculation of Laplace transforms.

**[0:00:29]** Okay. And the focus here is on, some of the kinds of functions that, one might be likely to encounter in, various circuit analysis problems. Okay. So we'll just go through these one by one. Alright.

**[0:00:45]** So we'll start with part a here. Okay. And for a, the function that we have in the time domain is h one of t, and this is given by 12 t times e to the minus three times t minus four times u of t minus four. We'll remember, as usual, u of t is the unit step function. Okay.

**[0:01:15]** Sort of as a preliminary step, let's think about this function and what is the core of this that we can build upon in order to compute the Laplace transform. And the core function here is really the exponential function here times the unit step function. Alright. So we're gonna let... We're gonna define a function f one of t, and we'll take that to be either the minus three t times u of t.

**[0:01:47]** And if that were the function that, we were dealing with, then its Laplace transform would be capital f one of s, and this is just one over s plus three. And you can get that by looking at, the table, table 12 dash two in Ulaby. Okay. So from here, right, how do we start from this function which has this Laplace transform, and how do we build upon it to get this full function over here? The first thing that we can see is that if we do a time shift, if we replace t in f one of t by t minus four, then we will get this part of the function h one.

**[0:02:36]** Okay. So let's do that first. We'll use the time shift property. Of Laplace transforms to go from t to t minus four. And that's a useful thing to do because, we know how f one of s, how this Laplace transform changes if we introduce a time shift in the time domain.

**[0:03:06]** Alright? And, what we have is that f of t minus, some time shift capital t times u of t minus capital t. It's Fourier transform is either the minus t s times f of s. Okay. So if we know, the Fourier transform...

**[0:03:32]** Or sorry. The Laplace transform of some function just f of t, such as f one of t over here, and then we shift it in time in the time domain, then this tells us what the corresponding Laplace transform is of the time shifted function. Okay? So what we wanna do then is we'll say we will let... Now we'll define a function f two of t.

**[0:03:58]** Okay. And we'll take that to be the time shifted version of f one of t. So it's either the minus three times t minus four times u of t minus four. Okay. So so we've shifted it by four in the time domain.

**[0:04:17]** So this is just our function f one at t minus four. Okay? And, we can also write that... Or that's also equal to f one of t minus four times u of t minus four. Alright?

**[0:04:33]** Because f one, of t minus four already can... Contains the unit step function over here. Alright? And so if we multiply by the unit step function again, then it doesn't matter. We just get the same thing.

**[0:04:47]** So we're free to do that, and that brings it into the form, that we can use, over here. Alright? So now that we have this being equal to f two of t, then we know that it's for... This Laplace transform is e to the minus four s because capital t here is four. So e to the minus four s times, f of s and specifically f one of s, which is one over s plus three.

**[0:05:19]** Okay. So that means that f two of s is equal to either the minus four s. Right? That's this factor over here times one over s plus three. Right?

**[0:05:35]** That's this capital f of s over here where since we're talking about the function f one, it's Laplace transform is f one of s over here one over s plus three. That's how we get this one over s plus three down here. Okay. So now we've gotten the Laplace transform of this part of h one of t. Now we have to figure out how to deal with this additional factor of t over here.

**[0:06:03]** And the way that we deal with that is to use, what's known as the frequency differentiation property of, Laplace transforms, which you can get from, you will be at all. From table 12 dash one, it's property number nine. Okay? So the next step then is to use what's called the frequency differentiation property of Laplace transforms. Okay.

**[0:06:43]** And this says that if you have a function t times f of t in the time domain and, you know the Laplace transform of just the function f of t, then the Laplace transform of t times f of t is minus the derivative with respect to f or with respect to s of f of s, where capital f of s is the Laplace transform of f of t. And, we got this from Ulaby et al. Table is 12 dash one, and it's entry number nine in that table. Okay. So, what we're going to do then is we're going to define yet another function.

**[0:07:35]** We'll call it f three of t. Alright. That's equal to t times f two of t. Alright. So that is t times e to the minus three, t minus four times t minus four times u of t minus four.

**[0:07:55]** Okay. And you can see that that is almost the entire function h one over here. Right? Except for this constant 12, which is very easy, to incorporate. We just multiply the final result by 12.

**[0:08:09]** We just have to remember to do that at the end. Okay. So we have this function f three of t. And, since it's t times f two of t, then we know that the Laplace transform of f three of t, capital f three of s, is going to be equal to minus the derivative with respect to s of f two of s. Right?

**[0:08:41]** F two of s, we figured out up here. Okay? So this is now minus the derivative with respect to s of f two of s, which is e to the minus four s times one over s plus three. Okay. And so now we just have to take the derivative of this function here with respect to s.

**[0:09:05]** And if we do that, we get minus. That's this, first minus sign over here. And then when we take the derivative of this product, e to the minus four s times one over s plus, three, When we take the derivative of that, then what we get is the derivative of... Right. It's the derivative of the product.

**[0:09:31]** So it's the derivative of the first term times the second plus the first term times the derivative of the second. Okay. So the first fact... The derivative of the first factor is minus four e to the minus four s. We multiply that by the second factor, one over s plus three.

**[0:09:50]** And then we have the derivative of the second factor, which is minus one over s plus three, the quantity squared times... And then times the first factor, to the minus four s. So we get minus either the minus four s times one over s plus three quantity square. Okay. And so if we just simplify this a little bit, we pull out the overall factor of either the minus four s and we multiply through by this minus sign over here, which gets rid of this minus sign and this minus sign.

**[0:10:30]** And so we get four over s plus three plus one over s plus three quantity squared. Okay. So that's f three of s. And then finally, we just have to multiply by our constant that we had in h one, which was 12. Alright.

**[0:10:58]** If we go back to here, right, that's this constant 12 over here. Okay. And then to incorporate that, all we have to do is to multiply f three of s by 12. And so if we do that, then finally, we get h one of s, that is the Laplace transform of our original function h one is equal to 12 e to the minus four s times four over s plus three plus one over s plus three squared. Right?

**[0:11:40]** And that is our result. Okay. And so, if we go back and look at what we did, then what were the key points here? Okay. The first point was that the way that we approach this was that we started with a basic Laplace transform result.

**[0:12:05]** Alright? And that is the Laplace transform of just the exponential function times the unit step function. Right? That's something that, we know or can look up easily in our Laplace transform table. Alright?

**[0:12:19]** And then what we did was we used a succession of properties of Laplace transforms to build up from this basic, result over here to this full function for which we're computing the Laplace transform in this problem. Alright? So we wanna start... Or what we did here was to start with just the basic Laplace transform result, alright, which is the Laplace transform of an exponential times the unit step function. Right?

**[0:13:00]** So here, it was that either the minus three t times u of t forms a Laplace transform pair with one over s plus three. Okay? And then from there, what we did was to use a number of Laplace transform properties in succession. Okay. Then here's what we did was first, we use the time shift property, alright, which introduced an additional exponential factor in the Laplace transform, then the frequency derivative property.

**[0:13:53]** Okay. We're multiplying by t in the time domain corresponded to taking minus d d s in the s domain. Right? Then we just multiply by our constant. Right?

**[0:14:12]** Which just multiplies the Laplace transform by the same constant. And then that got us to our result. And then the third, thing that we did was to make use of the fact that the unit step function is... If you multiply it by, itself, then you just get the same thing. Because zero times zero is zero, one times one is one.

**[0:14:37]** Right? And in fact, that's true for any power of the unit step function. Okay. So we made use of that observation and property of the unit step function as well. Okay.

**[0:14:50]** So that is it for part a. Okay. So now move on to part b, okay, which is another Laplace transform example. The function for which we wanna compute the Laplace transform is h two of t, and it is 27 t squared times the sine of six t minus 60 degrees times u of t. Alright?

**[0:15:24]** So we're going to approach this in a very similar way. We wanna start off with just some basic Laplace transform result that we can build upon. Alright? And so what we're going to start with here is to look at this sine of 60 minus 60 degrees. But instead of using the sine as our basic function, we're going to use a complex exponential.

**[0:15:52]** Alright? So let's let our function... We'll define a function f one of t that we can work with, and we'll take this to be e to the... It could be plus or minus j times six t minus 60 degrees times u of t. Alright?

**[0:16:14]** And then it's Laplace transform f one of s is e to the minus or plus j times 60 degrees. That's just this e to the plus or minus j times minus 60 degrees, out here in front, which is just a constant. Right? And plus or minus when you multiply the minus sign, gives you minus or plus. And then, for the exponential, part of it, either the plus minus j times six t, then we have one over s minus or plus j times six.

**[0:17:02]** Okay. So this is, the basic result that we're gonna start with. Okay? And, what we'll do here is now we will combine the complex exponentials so that we get, the sign, of the same argument. Alright?

**[0:17:26]** So we're gonna let now a call this new function f two of t. That is the sine of six t minus 60 degrees times u of t. Right? So that's just this function over here. These two factors over here.

**[0:17:45]** Alright? And that's one over two j, okay, times e to the j 60 minus 60 degrees minus e to the minus j 60 minus 60 degrees times u of t. Okay. So, this is just a a basic, property of complex exponentials. Right?

**[0:18:13]** You can combine them in this way to get trigonometric functions. And so now we can take each of these and use this result here to write the Laplace transform of each of these terms and therefore of f of f two of t directly. So if we do that, we get that f two of s is equal to one over two j. Okay. And then, we have...

**[0:18:41]** For this first term over here, e to the j times 60 minus 60 degrees, then we have, that's basically this result over here taking the top sign. Alright? So we get e to the minus j times 60 degrees divided by s minus j times six minus. Right? That's this minus sign over here.

**[0:19:11]** And then we want the Laplace transform in either the minus j times 60 minus 60 degrees times u of t. That's this result here taking the bottom sign corresponding to the minus sign over here. So that is going to be e to the plus j times 60 degrees divided by s plus j times six. Okay. And then from here, right, what we wanna do is to put this in a slightly more, what will turn out to be a slightly more convenient form.

**[0:19:50]** And we'll do that by taking these two terms and putting them over a common denominator. The common denominator is going to be s minus j six times s plus j six. Those are complex conjugates of each other. So when we multiply them to get the common denominator, that common denominator is just going to be s squared plus 36. Okay.

**[0:20:14]** And then in the numerator, we're going to get this e to the j times 60 degrees times s plus j six minus e to the j 60 degrees times s minus j six. K. So we write that out. We have our initial factor one over two j, then we have e to the minus j 60 degrees times s plus j times six minus e to the plus j times 60 degrees times s minus j times six divided by the common denominator, is s squared plus 36. Right?

**[0:20:54]** Which is s minus j six times s plus j six. Okay. And then if we take this and just rearrange things slightly, then we can see if we take the terms up here that are... That have a factor of s. Right?

**[0:21:13]** Is s times e to the minus j 60 minus, e to the plus j times 60 degrees. And then we're dividing by two j, and so that is actually minus the sine of 60 degrees. So from this term and this term, we get minus s times the sine of 60 degrees. And then here from, j six times e to the minus j 60 degrees plus... Because we have minus minus, j six times e to the plus j 60 degrees divided by two j, the j in the denominator will cancel this j and this j here in the numerator, and then we were going...

**[0:22:03]** We're going to get six times e to the j 60 degrees plus e to the minus j 60 degrees over two, which is just the cosine of 60 degrees. So we're gonna get plus six times the cosine of 60 degrees divided by s squared plus 36. Okay. So this is now the Laplace transform for this function here, the sine of six t minus 60 degrees times u of t. Right?

**[0:22:36]** Then from here, alright, we have to figure out how to deal with this factor of t squared, multiplying f two of s. And, to do that, we can take advantage again of the frequency differentiation property. Okay. But now for t squared rather than just t. So we're gonna use, again, the frequency differentiation property.

**[0:23:14]** Okay. As it's given in Ulaby, it is the t times f of t forms a Laplace transform pair with minus d d s f of s. Right? Where f of t and f of s form a Laplace transform fair... Pair.

**[0:23:34]** This is from Ulaby et al. Table 12 dash one is property number nine. Okay? But we can easily generalize this, alright, to higher powers of t. Alright?

**[0:23:55]** So, for example, we can let, say, g of t be equal to t times f of t, and then g of t forms... Will take it to form a Laplace transform pair with capital g of s, then t times g of t forms a Laplace transform pair with minus derivative with respect to s of g of s. Right? But then instead of g of t over here, we can write t times f of t, then we get on that left hand side, t squared times f of t. And it forms a Laplace transform pair with minus d d s of minus d d s of f of s.

**[0:24:49]** So minus one squared d squared d s squared f of s. Okay? And then if we just basically keep on, doing that, then we can come up with, the expression for, in general, the Laplace transform of t to some power n times f of t. And what you get is the t to the n of f of t forms a Laplace transform pair with minus one to the n, d n, d s n of f of s. Okay.

**[0:25:32]** So, so this is the property that we're going to use now. So we're going to let f three of t, okay, be equal to now t squared times f two of t, where f two of t, alright, was this function here. Right? Sine of six t minus 60 degrees times u of t. And so when we multiply that by t squared, we get almost the whole function h two except for this constant 27, and we'll just multiply by that constant at the end.

**[0:26:10]** Okay. So f three of t is equal to t squared times f two of t, which is t squared times sine of six t minus 60 degrees times u of t. Alright? And we can use this frequency differentiation property, alright, to compute now the four... The Laplace transform of f three of t in terms of the Laplace transform of f two of t, which we just computed.

**[0:26:50]** Up here, that's f two of s. Okay. Okay. So using this frequency differentiation property, we get that f three of s, right, the Laplace transform of f three of t is equal to the second derivative. Alright.

**[0:27:09]** So we're applying basically this formula here. Okay? Because we have a t squared. So we have the minus one squared, which is one, and it's the second derivative, d squared d s squared of now the Laplace transform of the sine of 60 minus 60 degrees times u of t. And we just figured out a few minutes ago that that is minus s times the sine of 60 degrees plus six times the cosine of 60 degrees divided by s squared plus 36.

**[0:27:47]** Okay? So we'll take one derivative of that first. Okay. That is going to be, when we take the derivative of this with respect to s, it's the derivative of the numerator times the denominator minus the numerator times the derivative of the denominator divided by the denominator square. Right?

**[0:28:10]** That's the, quotient rule, right, basically, for taking derivatives. So the derivative of the numerator with respect to s is just minus the sine of 60 degrees. So we have minus the sine of 60 degrees. That times now the denominator, s squared plus 36, minus the numerator times the derivative of the denominator. The derivative of the denominator is just two s, and then the numerator is minus s times the sine of 60 degrees plus six times the cosine of 60 degrees.

**[0:28:50]** All of this will be divided by the denominator squared, s squared plus 36, the quantity squared. Okay. So, here, before we take another derivative, let's see if we can, simplify this expression in the square brackets here a little bit. Alright? If we look at this and we look at the terms proportional to s squared, we have minus s squared times the sine of 60 degrees plus, because we have minus sign here, minus sign here, s squared times two times the sine of 60 degrees.

**[0:29:31]** So that's going to give us overall s squared times the sine of 60 degrees. Alright? Then we can look at the terms proportional to s. Alright? There's only one term.

**[0:29:48]** It's minus two s times six times the cosine of 60 degrees. So that's minus 12 times s times the cosine of 60 degrees. And then finally, we have, the terms that are the constant term, which is minus 36 times the sine of 60 degrees. So minus 36 times the sine of 60 degrees divided by s squared plus 36 quantity squared. Okay.

**[0:30:24]** So now we can take the derivative of, this. Alright? And when we do that, again, we're gonna use the, quotient rule, right, for taking, derivatives. And so it's the derivative of the numerator, right, which is two s times the sine of 60 degrees minus 12 times the cosine of 60 degrees times the denominator, so times s squared plus 36, the quantity squared, minus the numerator times the derivative of the denominator. Right?

**[0:31:03]** The derivative of the denominator is two s squared plus 36 times two s. We multiply that by the numerator, which is s squared times the sine of 60 degrees minus 12 s times the cosine 60 degrees minus 36 times the sine of 60 degrees. Right? All of this divided by s squared plus thirties... The denominator squared.

**[0:31:37]** So s squared plus 36 to the fourth power. Okay. Now here, we can cancel out an overall factor of s squared plus 36 for the numerator and the denominator. Right? If we do that, we get two s times the sine of 60 degrees minus 12 times the cosine of 60 degrees times s squared plus 36, just to a single power, minus...

**[0:32:08]** And then we have two times two s, so that's four s. Alright. We've canceled out. Now this s squared plus 36, and so we have just this last term over here, which is s squared times the sine 60 degrees minus 12 s times the cosine of 60 degrees minus 36 times the sine of 60 degrees. All of this divided by s squared plus 36, not to the fourth, now to the third because we canceled out one power from the numerator and the denominator.

**[0:32:53]** Okay. So now let's, try to simplify the numerator a bit here. So let's go by powers of s. So let's look at, the terms proportional to s cube. We have from this term times this term, two s cube times the sine of 60 degrees.

**[0:33:12]** And then from this four s times s squared, we have minus four s cube times the sine of 60 degrees. So that gives us minus two s cubed times the sine of 60 degrees. Right? And then for the terms proportional to s squared, we have minus 12 cosine of 60 degrees times s squared, and then plus 48, four times 12 s squared times the cosine of 60 degrees. So that's plus 36 s squared times the cosine of 60 degrees.

**[0:33:54]** And then if we look at the terms proportional to s, alright, we have two s times the sine of 60 degrees times 36. Right? That's 72, s times the sine of 60 degrees. And then we have, minus minus s plus four times 36. That's a 144 s times the sine of 60 degrees.

**[0:34:19]** So it's a 144 plus 72, that's 216 s times the sine of 60 degrees. And then finally, we have, the constant term, which is minus 12 times 36 times the cosine of 60 degrees. Right? 12 times 36 is 360 plus, 72. So that is 432.

**[0:34:52]** So minus 432 times the cosine of 60 degrees. All of this divided by s squared plus 36 cubed. Okay. So that is f three of s. Right?

**[0:35:14]** The Laplace transform of this. And to get the final result, we just have to multiply by this constant 27. Alright. And then we'll be done. Okay.

**[0:35:32]** So the last step here is to multiply by our leading constant here, which is 27. Right? And so finally, get that h two of s is equal to... Right. It's 27 times f three of s.

**[0:35:54]** Right? This is what we just calculated up here. And so that is going to be, right, if we just multiply this through, minus 27 times two. So that's minus 54 times s cubed times the sine of 60 degrees. Then we have 27 times 36.

**[0:36:18]** That's 972. Okay, times s squared times the cosine of 60 degrees. Then we have from this term, 27 times 216. So that's plus 5,832 s times the sine of 60 degrees. And finally, minus 27 times 432, that's 11,664 times the cosine of 60 degrees.

**[0:36:58]** All of this divided by s squared plus 36, the quantity cubed. And now if we just evaluate the sine and the cosine of 60 degrees. Right? The sine of 60 degrees is root three over two. The cosine of 60 degrees is one half.

**[0:37:21]** Okay. And so finally, what we get is that h two of s is equal to... It ends up being minus 46.77 s cubed plus 486 s squared plus 5,051 s minus fifty eight thirty two. Okay. And, that is divided by s squared plus 36, the quantity q.

**[0:38:08]** Okay. So... Alright. So that is the answer to the second part. And there are a few additional key points.

**[0:38:29]** To note here. Alright? First is... Right. Again, right, our basic strategy here, once again, was to start with a basic result for Laplace transforms.

**[0:38:45]** Alright? All the way back up here. This was just the Laplace transform for a complex exponential, and then we just sort of built upon it using the basic properties of Laplace transforms and other simple mathematical tools. Right? Expressing the sign as a sum of complex exponentials, then using frequency differentiation and multiplying by the constant in the end.

**[0:39:12]** Okay. So we started with a basic result for Laplace transforms and then built upon it. Using properties of Laplace transforms, right, and other mathematical tools. Okay. The second point to note here is, as we showed, that this property of frequency differentiation, right, can be generalized to, derivatives of arbitrary order.

**[0:40:08]** Right? And correspondingly, powers of t or or arbitrary powers of t. Right? So this property of frequency differentiation, right, it generalizes to arbitrary powers of t and then correspondingly, derivatives, okay, of arbitrary order. Alright.

**[0:40:50]** And the key result that we derived in this example was the t to the n f of t forms a four... A Laplace transform pair with minus one to the n, the derivative d n d s n of f of s. Okay. And then the third point that, we should note here is that the Laplace transform of e to the minus a t times u of t. Right?

**[0:41:28]** This is one over s plus a. Alright. We knew that. And this works even for complex values of a. Okay.

**[0:41:44]** So that was the other, useful thing or another useful thing that we got out of this example. Okay. So let's continue now. Alright? Now we'll move on to part c of this problem.

**[0:41:59]** Alright? And so now we have the function h three of t, and it is 10 t cubed e to the minus two t times u of t. Alright? And so here, right, one way we could do this is to look directly at, table 12 dash two in Ulaby, and we can actually, read off the result pretty much directly from the table. Alright?

**[0:42:28]** So from table 12 dash two is entry number eight of Ulaby et al. Right? We can see directly, alright, that... Alright. T to the N minus one, E to the minus AT times U of T.

**[0:42:57]** Right? If... So if look at that, you can see that's, right, pretty much directly the form of this here with n equal to four. Right? This forms a Laplace transform pair with n minus one factorial divided by s plus a to the n.

**[0:43:17]** And so here in this example, n is equal to four. Alright? And so we can just take that result and use it directly to get the Laplace transform of h three of t. So capital h three of s, it'll be 10 times n minus one. So that's three factorial divided by, s plus...

**[0:43:46]** And then a is equal to two. Alright? To the fourth. Alright? Because n is equal to four.

**[0:43:53]** Three factorial, that's three times two times one, that's six. So six times 10 is 60 divided by s plus two to the fourth. Alright? So, this is the, the answer. Right?

**[0:44:10]** But it's perhaps not quite as instructive, to just read it off the table. We can actually derive this result using frequency differentiation. And in fact, this will allow us to derive... Essentially, see how this entry in the table comes about. Right?

**[0:44:28]** So we can drive this using, again, this property of frequency differentiation for Laplace transforms. Alright. So we're gonna take our basic function, right, f one of t. We'll take that to be either the minus two t times u of t. Then we know that f one of s, it's Laplace transform, is one over s plus two.

**[0:45:06]** Okay. Then, when we multiply this, right, then here... Right. We need to multiply this by t q. Alright.

**[0:45:20]** So... And then that'll allow us to use this property of frequency differentiation, which in the previous part of the... Of this example, we derive for arbitrary powers of t and correspondingly arbitrary orders of differentiation. So we're gonna use frequency... The frequency differentiation property of Laplace transforms.

**[0:45:53]** Right? That is that t to the n f of t forms a Laplace transform pair with minus one to the n times d d n d s n of f of s. Right? I... And so we're going to now let f two of t, right, be t cubed e to the minus two t times u of t, which is t cubed times f one of t.

**[0:46:29]** Alright? And using this frequency... This generalized frequency differentiation property, then we see that f two of s, right, the Laplace transform of f two of t over here is going to be equal to minus one cubed times the third derivative, d cubed d s cubed of one over s plus two. Okay. And it's relatively easy to take successive derivatives of one over s plus two.

**[0:47:04]** Alright. So this is gonna be minus one cubed. And then if we take one derivative explicitly, we'll have d squared d s squared of the derivative of one over s plus two, which is minus one over s plus two quantity squared. Alright? Then we can take one more derivative of this with respect to s, and then we'll also pull this minus one, to the outside.

**[0:47:36]** So we have our minus one cubed, and then the minus one now that we're pulling out in front of the derivative. And then we have d d s of the derivative of one over s plus two, the quantity squared, which is minus two over s plus two, the quantity cubed. Okay. And then we can pull this minus two out in front and take the final derivative of... With respect to s of this.

**[0:48:09]** Now it's gonna be one over s plus two, the quantity cubed. So we're gonna have minus one cubed times minus one. Now pulling out the minus two times minus two. And then taking the derivative with respect to s of one over s plus two quantity cube, we get minus three divided by s plus two to the fourth. Okay.

**[0:48:34]** So this is now minus one cubes times minus one times minus two times minus three divided by s plus two to the fourth. Alright? And so we see here all the minus signs cancel out, and they will always can... All cancel out. So we just get three factorial divided by s plus two to the fourth, which is six over s plus two to the fourth.

**[0:49:07]** Okay? And so now, by just seeing how this worked out, you can start to see, or hopefully completely see, right, where this n minus one factorial comes from and why this is s plus a to the nth power. Alright? So then from here, alright, the last step is just to multiply by our overall constant factor in h three, which was 10. Right?

**[0:49:45]** That's this 10 up here. Okay. And so what we get then is h three of s is equal to 10. Right? This is f two of s.

**[0:50:02]** F two of s. Right? Or... Alright. If we plug in f two of s, given explicitly here, over here, we get 60 over s plus two quantity to the fourth power.

**[0:50:22]** Right? Which is the answer. To same thing that we got reading directly from the table. Okay? But with a little bit more explanation and hopefully where you can see how this comes from what we had derived previously or how it can be arrived at from what we had derived previously.

**[0:50:41]** Okay. Let's move on to part d. Now we have a function h four of t. This is five times t minus six times u of t minus three. Okay.

**[0:50:58]** So here, the new twist is that we have two different time shifts. Right? By six over here and by three over here. Alright? But, actually, you know, we don't have to think of this as a time shift at all.

**[0:51:13]** We can just think of this as two terms, and then the six is just a constant. So we can write this as h four of t. We can also write it as five t times u of t minus three, minus 30 times u of t minus three. Okay. So from here, right, this is zero.

**[0:51:44]** This is step zero, our usual step zero. What is the basic function that we wanna start with? It's really just the unit step function. So f one of t, take it just to be u, but we'll take it to be u of t minus three. Alright?

**[0:52:00]** And then reading from the table in Ulaby, we know that the corresponding Laplace transform is either the minus three s over s. We could also arrive at that, by recognizing that the Laplace transform of just u of t is one over s and then using the time shift property, which gives us the additional factor of either the minus three s. Alright. So either way would be fine. Then from here...

**[0:52:33]** Oops. For the first term, since we have this additional factor of t, we can... We know that we can use the the simple first order frequency differentiation property. Right? So we're gonna use frequency differentiation, right, which is that we know that t times f of t forms a Laplace transform pair with minus d d s f of s.

**[0:53:13]** Okay. Where f of t and capital f of s form a Laplace transform pair. And so, using that, we can pretty much immediately go to figure out the Laplace transform of h four of t. So capital h four of s is for the first term over here, it's going to be minus five times the derivative with respect to s of the Laplace transform of u of t minus three, which is either the minus three s over s. And then for this second term over here, it's going to be minus 30.

**[0:53:54]** And then we just have the Laplace transform of u of t minus three, which is e to the minus three s over s. Okay. So now we just have to work this out. Alright? And so we have for the first term minus five, And then we're taking the derivative of this function over here, either the minus three s over s.

**[0:54:20]** Alright? And so if we use, say, the quotient rule, then the derivative of this is minus three times s times e to the minus three s. Alright. Minus e to the minus three s times one. So just e to the minus three s divided by s squared.

**[0:54:45]** And then we'll just carry, over the second term 30 minus 30 times either the minus three s over s. Alright? And then if we just separate out these two terms here, then from the first term, we get minus five times minus three, that's 15, e to the minus three s, then we have s over s squared, which is just s in the denominator. Then we have plus five, that's this minus five times minus one, right, times e to the minus three s over s squared, and then carrying down that last term again, minus 30 e to the minus three s over s. Right?

**[0:55:39]** So then... Okay. The first term and the third term work out to, minus 15 e to the minus three s over s. And so we're gonna have, we can pull out an overall factor of five either the minus three s. And then we have one over s squared.

**[0:56:04]** That's from this term over here. And then from the combination of these two terms, we get minus three over s. And that's the answer. Okay. So that was a relatively simple, example there.

**[0:56:27]** Right? Now we'll go to part e. Okay. So this here was part d. Right.

**[0:56:38]** So now we'll go to part e, of this problem, right, which is to compute the Laplace transform of our function of a function h five of t, which is 10 e to the minus three t times u of t minus four. Okay. So, again, right. What's the basic function that we wanna start with? It's going to be, an exponential times the unit step function.

**[0:57:09]** So we'll let f one of t, it'll be either the minus three t times u of t. Right? Then f one, it's, Laplace transform is one over s plus three. Okay. So how do we make use of that given that we have u of t minus four over here?

**[0:57:35]** Alright. Well, let's rewrite things slightly. We can write h five of t to be equal to... It's 10 e to the minus three t u of t minus four. Okay?

**[0:57:52]** But we can equally well write that as 10. Right? And then we'll introduce a factor of either the minus 12, which will then allow us to write times either the minus three t minus four. Alright? So we've multiplied by either the minus 12 and then through this four over here, either the plus 12.

**[0:58:13]** So that's just multiplying by one times u of t minus four. Okay? And we can write this now as 10 e to the minus 12. And then this product over here, e to the minus three times the quantity t minus four times u of t minus four is just f one of t minus four. Okay.

**[0:58:44]** And then we can multiply by u of t minus four again. Right? Because that doesn't change anything. So it's 10 either the minus 12 f one of t minus four times u of t minus four. Okay.

**[0:59:01]** And then once we've done that, that allows us to use the time shift property to determine the Laplace transform of f one of t minus four times u of t minus four. Okay. So now we can use the time shift property. Alright. Which is that f of t minus t times u of t minus t forms a Laplace transform pair with either the minus s t times f of s.

**[0:59:42]** Right? We use that, also in one of the earlier parts of this example. Okay. And so that means that the Laplace transform of small h five of t, capital h five of s is 10 e to the minus 12 times e to the minus four s times the Laplace transform of our original function f one. Alright?

**[1:00:13]** And up here, right, capital f one of s is one over s plus three. Alright. So what we get then is that h five of s is equal to 10, e to the minus 12, e to the minus four s over s plus three. Or if we work out the numerical value for 10 e to the minus 12, it's 6.14 times 10 to the minus five e to the minus four s over s plus three. And that's the answer for part e.

**[1:01:00]** So there's one additional point that we can note here. Alright. If we think about, what we did in this problem, and that is that what we did here was we deliberately introduced an additional time shift over here because that then allowed us to use the time shift property of Laplace transforms. Right? So it may have looked like we were making things a little bit more complicated, but that was actually a route to making it, more tractable.

**[1:01:36]** Right? So in this case, time shifts or a time shift, right, or more generally, potentially other modifications. Alright. These can be deliberately introduced, Right. To enable the various useful properties of Laplace transforms to be applied.

**[1:02:22]** Okay. And here, we did this so that we can use the time shift property of the Laplace transform. Okay. So that was part e, and now we were... We are at last at part f of this.

**[1:02:49]** This is the last part of this example. Okay. And so we have a time domain function h six of t, and it is four times either the minus two t minus three u of t minus four. Okay? And the idea here is actually pretty similar to, what we did in part e.

**[1:03:18]** Alright? What we're going to do is we're going to introduce an additional time shift over here so that we can use the time shift property of Laplace transforms. So the basic function that we're gonna be working with is, again, exponential function, e to the minus two t u of t. Alright. Then f one of s is one over s plus two.

**[1:03:50]** Okay? And so we're gonna take... Alright. We have the h six of t is equal to four e to the minus two times t minus three u of t minus four. Alright.

**[1:04:08]** So now we will... What we wanna do is to have the same time shift in the unit step function and in this exponential function over here. So we'll have four e to the minus two, then it's either the minus two times the quantity t minus four. Right? So we've multiplied by either the minus two over here.

**[1:04:29]** And then by changing this from three to four, we've multiplied by e to the plus two. Alright? Times u of t minus four. Okay. And so this is four e to the minus two.

**[1:04:48]** And then it's our function f one, but now time shifted. So f one of t minus four. Alright? And we can multiply as, as we did before by the unit step function without changing anything. Four is...

**[1:05:01]** So it's four e to the minus two f one of t minus four u of t minus four. Okay? And then from here, now we can use the time shift property, that is that f of t minus some time shift capital t times u of t minus capital t forms a Laplace transform pair with either the minus s t. F of s. Okay.

**[1:05:38]** And so finally, that gives us the capital h six of s. The Laplace transform of h six of t is four e to the minus two times e to the minus four s. Right? That's this time shift factor over here times, f one of s. Right, which we have from up here is one over s plus two.

**[1:06:09]** And so what we finally get then is that h six of s is four e to the minus two e to the minus four s over s plus two. And, if we calculate numerically four times e to the minus two, it is o point five four one three, and then we have e to the minus four s over s plus two. Okay. And so that is the result for, this last part of this example. And so that completes the solutions to Ulaby problem 12.5.

**[1:06:57]** K. So I will stop the recording now.
