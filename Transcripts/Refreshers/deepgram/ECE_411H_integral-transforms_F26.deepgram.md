# ECE_411H_integral-transforms_F26

Deepgram general-nova-3 2025-07-31.0, request 01a1b039-527a-7e03-b4ff-c3312308f441, audio 63.8 min.

**[0:00:04]** Okay. So this is a recording on, what we're calling integral transform techniques. Okay. So these techniques include things like the Laplace transform and also the Fourier transform that we'll be talking about during the rest of the semester. And kind of the reason for making this recording is that in Ulaby and actually in, I think, just about every other elementary circuits textbook, When they get to the sections on Laplace transforms and Fourier techniques, there isn't really very much discussion of where these come from mathematically, how they're related to each other and such, and how to understand them.

**[0:00:57]** Mostly, you know, there's maybe a little bit of discussion of that, and then the books pretty much launch right into the relevant formulas and how to use them. Okay. So what I wanted to do in this recording is to step back a little bit and talk about how do we really motivate and understand transform techniques such as the Laplace transform, the Fourier transform. And then later on in three thirteen, you'll talk about what's called the z transform. How do we do this rather than simply applying a bunch of formulas?

**[0:01:57]** Okay. So so this is not essential for what we'll be doing at least initially, and we'll touch on pieces of this later on. But I think it's very helpful with respect to understanding to see some of this upfront. Okay? So that's what we'll do here in this recording.

**[0:02:17]** Right? Now to start off with, you might think back to what you might have learned or seen in three zero two or three zero two h if you took the new version of three zero two or three zero two h with respect to what we call Fourier series. If you don't remember that or if you did not take a new version of those courses, then that's perfectly fine. We'll talk about these in more detail later, and I'll just kind of hit the key points that are relevant to us right now in the recording here. Alright.

**[0:02:52]** So let's recall or perhaps recall, this concept of Fourier series, okay, from, at least the new ECE three zero two and three zero two h. Alright? And, basically, the idea of Fourier series and what's called Fourier's theorem is is that if you have any periodic signal, right, so the signal repeats after some period, say, t, then it's possible to express that signal as a sum of sing... Of sinusoidal signals at a series of frequencies that are equal to the fundamental frequency associated with the period t. That's two pi over t plus frequencies that are integer multiples of that frequency.

**[0:03:51]** Alright? So let's let some signal... We'll call it f of t. Let's let this be a periodic signal, okay, with some period capital t. Alright?

**[0:04:10]** And by periodic, right, what we mean, just to be careful about this here, is that f of t is equal to f of t plus any integer n times the period capital t, and that has to be true for all integer values of n. Right? The symbol capital z here is the symbol that's typically used for integers in mathematics. So this has to be true for all integers n and for any time t, Right? Between minus infinity and infinity.

**[0:04:47]** Right? That's what it means to be a periodic function. So it just repeats itself after some period of time capital t, and we call that period capital... We call capital t the period. Alright?

**[0:05:00]** Now it turns out then that as long as this function f of t is what we'll call here just a a reasonable function, meaning that it's sufficiently smooth, meaning it has, you know, reasonable derivatives and is sufficiently nondiverging. Right? It doesn't go to infinity or minus infinity all over the place. Then we can do this thing that I described. We can express f of t as a sum of sinusoidal signals.

**[0:05:30]** Alright? So what Fourier's theorem says, in a nutshell, is that if this function f of t is what we'll call... We'll just say a reasonable function. Alright. Meaning that it's sufficiently smooth.

**[0:05:56]** And nondiverging. Okay. And in the careful statement of phrase theorem, this is stated much more precisely and rigorously, but this is good enough for us now. Then what Fourier's theorem says is that we can write f of t as a sum of a constant, basically, a zero frequency signal, right, plus a series. Right?

**[0:06:29]** So a sum from n equal to one to infinity of a superposition, basically, of sinusoidal signals. Alright? So some coefficients a sub n times the cosine of n omega naught t plus other coefficients b sub n times the sine of n omega naught t. Alright? Where omega naught here, okay, is the angular frequency associated with the period capital t.

**[0:07:01]** Alright? So it's just two pi over capital c. And then a naught, a sub n, and b sub n are basically just constants, alright, that we can calculate. Alright? And so so what you see here is that what Fourier's theorem says is that any periodic signal f of t, any periodic function f of t, right, can be written in this form.

**[0:07:29]** Right? A constant, which is basically a zero frequency signal plus a sum of the sinusoidal signals shown here. Right? And so these, you can see now, are at frequencies which are equal to the fundamental angular frequency associated with the period capital t. Right?

**[0:07:49]** That's the case n equal to one. And then integer multiples of that. Okay? And if we use the Euler identity or the Euler's formula, right, to write the cosine and the sine as complex exponentials, then we can see that another way that we can write this is that we can write f of t as a sum from n going to minus infinity to infinity coefficients c sub n. Again, these coefficients are just constants.

**[0:08:25]** Alright? Although for each n, it can be a different constant times the complex exponential e to the j and omega knot t. Right? Where, again, here, omega knot is two pi over t. Okay?

**[0:08:43]** And these ways of writing f of t, right, these are what we call Fourier series. Okay? And so what this says then is that... Or what this implies, okay, is that since we can write now any periodic function, right, or periodic, say, electrical signal in a circuit in this form here, right, what we can then do is we could use, say, phasors, right, to calculate the response of the circuit, right, all the other voltages and currents and so forth at the frequencies omega naught and n times omega naught. Right?

**[0:09:34]** And then once we have all of those, we can combine them by superposition. That is just add them together, and we will get the response of the circuit for this periodic signal that is not necessarily sinusoidal. Alright? So this idea of the Fourier series will allow us to analyze and think about and understand circuits that that operate with any periodic signal, not just sinusoidal signals. Alright?

**[0:10:09]** And that's a very powerful extension. Okay? And so, right, one of the things that this implies, right, then is that by analyzing, okay, a linear circuit's behavior... Okay. And this qualified here that this has to be a linear circuit is important because, remember, we can only apply superposition to linear circuits and linear systems.

**[0:10:43]** Right? Not nonlinear circuits or systems. Alright? So by analyzing a linear circuit's behavior, right, add all these frequencies. Right?

**[0:10:54]** So if frequencies, we'll call them omega sub n. Right? So that's two pi times n over the period capital t, right, or equivalently n times omega naught. Right? By analyzing, say, using phasors, the behavior of the circuit at all these different frequencies, then by superposition...

**[0:11:18]** Right? So now we can understand that circuit's behavior. Now for any periodic signal, right, using this idea of superposition. Okay. So by using the idea of superposition, right, what this has allowed us to go to is from being able to analyze circuits at only a single frequency with a sinusoidal signal to analyzing circuits with any periodic signal.

**[0:12:03]** Right? So that's a major expansion of the situations that that we can consider. Okay. The other thing that we want to point out here or the next thing that we wanna point out here is that, say, if we look at this form of f of t over here, right, the sum from n equal to minus infinity to infinity of these coefficients c sub n times e to the j n omega naught t. Alright?

**[0:12:37]** If we know all the coefficients c sub n, right, that contain... Those coefficients, right, the set of coefficients c sub n contain all the information that we need in order to construct f of t. Or, actually, we need to know omega naught as well. Right? So we need to know the period and the coefficient c sub n.

**[0:13:01]** Alright? But once we have that, we have all the information that we need in order to determine what f of t is. And so in that sense, we can think of the full set of these coefficients, c sub n, as being a representation of the signal f of t, but now in the frequency domain. Right? So the coefficient c sub n tell us for each frequency omega n, right, which is n times omega naught, c sub n tells us, right, how much of the signal f of t is made up of a sinusoidal of the frequency omega n or n times omega naught.

**[0:13:43]** Alright? So we also want to point out here, right, that... Alright. The set of coefficients. Right?

**[0:13:59]** So we'll call the the... That set c sub n. Right? This set of coefficients, right, represents... We can say that it represents f of t in the frequency domain.

**[0:14:21]** Okay. Because the coefficients here, each one corresponds to a particular frequency. So we can think of c sub n as being, in some sense, a function of frequency, and these coefficients contain all the information that we need about f of t. Right? So we can think of those coefficients in this way as being a representation of f of t, but now in the frequency domain rather than in the time domain.

**[0:14:49]** Alright? Another piece of terminology, alright, that we will introduce here is that of basis functions. Okay? So if we look at these expressions here for f of t, right, using Fourier's theorem, right, what... Say, this one down here is saying is that f of t can be written...

**[0:15:15]** Any any periodic function f of t can be written as a sum of terms that are proportional to e to the n omega... A e to the j and omega not t. Alright? And so these functions, e to the j and omega naught t, those functions, then what we say is they constitute a set of basis functions for periodic signals f of t. And what we mean by a set of basis functions means that if we take the entire set of basis functions, then we can take linear combinations of those, and we can use them to express any periodic signal.

**[0:15:57]** Right? And perhaps a more intuitive way of thinking about that is by the correspondence between basis functions and basis vectors in just, say, a three-dimensional space like we're accustomed to to living in here. Right? So in three-dimensional space... And you may have seen this in a calculus based physics course or perhaps even a noncalculus based physics course.

**[0:16:27]** Right? We have vectors in three-dimensional space. Alright? And if you think about all the possible vectors that you can have in a three-dimensional space, then we can write any vector in a three-dimensional space as a linear combination of unit vectors. Right?

**[0:16:49]** That is vectors of length one, one of which points in the x direction, one of which points in the y direction, and one of which points in the z direction. Right? So with that set of three basis vectors, we can take linear combinations of those and construct any vector in three-dimensional space. Right? So that set of three vectors, we call a set of basis vectors for three-dimensional space.

**[0:17:14]** Right? Univectors in the x, y, and z direction. And in a very analogous way, saying that we have a set of basis functions, either the j and omega naught t for all the possible value... An integer values of n, right, that... Right?

**[0:17:36]** That's saying that those basis functions... If you take linear combinations of those basis functions, you can use them to express any periodic signal or function that we've called here f of t. Alright. So... Right.

**[0:17:56]** In the language of linear algebra. Right? Or perhaps more familiarly to you, vectors. Right? Then the set of functions either the j and omega naught t, alright, or...

**[0:18:22]** Alright. We saw up here, it didn't have to be just the complex exponentials. It could be the sine and cosine functions, right, including the n equal to zero term over here. Right? So sines and cosines plus one, right, can be taken to be a set of basis functions for periodic functions as well.

**[0:18:46]** Right? So the set of functions cosine of n omega naught t and the sine of n omega naught t. Right? And, I guess, one for n equal to zero. Right?

**[0:19:01]** Either one of these can serve as a set of what we call basis functions, okay, for any periodic function of t. Right? And this idea of basis functions is one that comes up almost ubiquitously in any discussion of, say, linear systems, linear signals, and then as a subset of that circuits and and the like. So that's something that you'll probably encounter many times throughout your educations if you have not encountered it already. Okay.

**[0:19:52]** So so now we're at a point where we can analyze circuits using Fourier series for any periodic signal. Alright? So then at this point, it's natural to ask the question, well, what about nonperiodic signals? Can we treat those? Alright.

**[0:20:12]** So what about non periodic signals? Okay. And so here, alright, if we think about it a little bit, if we take a periodic signal, but we let the period become very large. Right? Say, we'll let the period capital t go to infinity.

**[0:20:39]** Right? Since for the periodic signal, it can have any dependence on time. You know, within reason, it can have any dependence on time within that period. If we take the period to go to infinity, then, effectively, that allows us to treat nonperiodic signals as well as periodic signals. Right?

**[0:20:58]** So if we take the period to go to infinity, right, then this periodic function f of t is effectively nonperiodic. Okay. And so all we have to do then is to figure out, well, how do we sensibly take the limit of capital t, the period, going to infinity? Alright? When we do that, then what we will see shortly is that the Fourier series, instead of being a sum over sort of discretely spaced frequencies, in the limit of the period going to infinity, the spacing between the frequencies gets closer and closer until it approaches zero.

**[0:21:53]** Right? Because omega naught is two pi over the period. Right? So omega naught in the limit of t going to infinity, omega naught is going to zero. And what we will have, say, looking down here at the Fourier series in the form of complex exponentials is that this sum over all these discretely spaced frequencies, it then becomes an integral over frequency.

**[0:22:21]** K. Frequency is going from minus infinity to infinity. And, effectively, this coefficient c sub n, right, which we can think of as a function of frequency, say, omega n. Right? This coefficient then becomes it becomes a function of frequency that contains all the information about f of t and a modified version of that function c sub n, then it's what we call the Fourier transform.

**[0:23:00]** Okay? So how does this work? Right? As we take the limit or when we take the limit of the period going to infinity, what happens is that the Fourier series, right, then becomes a Fourier integral. Okay.

**[0:23:25]** And this will lead us to the Fourier transform. Okay. So let's see how this works out. Alright. We'll take the, oops, the Fourier series.

**[0:23:51]** Okay. I don't know why it showed up there. We'll take the Fourier series in the complex exponential form. Alright? So the sum from n going to minus infinity to infinity of c sub n times e to the j n omega naught t, right, with omega naught equal to two pi over t.

**[0:24:14]** Okay? What we will see later on in the semester, right, but I'll just give it to you as a result right now, is basically the expression that we can use to calculate c sub n. Alright? So this expansion will hold when we take c sub n to be equal to one over t times the integral from minus t over two to plus t over two of f of t prime times e to the minus j and omega nine t prime... D t prime.

**[0:25:02]** Right? Or we can write it as a function of frequency, say, omega sub n. Right? Remember, omega sub n is just n times omega naught. Right?

**[0:25:18]** We define that up over here. Right? So we can take c to be a function of frequency as well, and then we write it as one over t times the integral from minus t over two to plus t over two of f of t prime, e to the minus j omega sub n times t prime, right, d t prime. Okay? Now in these integrals here, notice that I've used this variable t prime.

**[0:25:55]** The prime here does not indicate differentiation. Okay? It's just that we're using... We have a different variable here. We use t prime.

**[0:26:06]** The t part reminds us that this is a time variable, and the prime tells us that it's different from this t over here. Right? And it's really just a dummy variable of integration. Right? So when we carry out this integral, since we're integrating over t prime, then once we do the integral, there's no t prime left.

**[0:26:25]** There's only omega sub n left, right, which is why this is a function of omega sub n. So we'll just make a note here in case it wasn't clear that t prime here is a variable. Right? It's the variable of integration. Right?

**[0:26:52]** It's not the derivative of t. Okay. And so... Alright. If...

**[0:27:10]** So if if you're curious about how we get this, okay, I'll sketch out sort sort of of very roughly how how this happens. Right? So if we have f of t, right, it's the sum from n going to... From minus infinity to infinity of c sub n, e to the j n omega naught t. Right?

**[0:27:35]** If we take this whole thing and multiply it by e to the minus j times... We'll call it n naught, some specific integer n. Right? We'll call it n naught times omega naught t. Right?

**[0:27:56]** Then what we have is e to the minus j and not omega not t times f of t. Right? And that is equal to, right, the sum for n going from minus infinity to infinity of c sub n times e to the j n minus n naught. Right? Omega naught times t.

**[0:28:25]** Alright? Now if we take both sides of this equation and we integrate it over one period, say, minus t over two to t over two, multiply it by one over t, right, then on the left hand side, we get one over t times the integral from minus t over two to t over two times, right, f of t e to the minus j n naught omega naught t dt. And then on the right hand side, right, we get one term in this sum where n is equal to n naught. Right? Because n naught is any...

**[0:29:15]** Some one particular integer. So when n is equal to n naught, right, then this exponential is zero. Right? So let's pull that term out of this sum. We have one over t times the integral from minus t over two to t over two of c sub n naught, right, times one dt plus the sum over all the other values of n that are not equal to n of one over t times c sub n.

**[0:29:56]** Right? The integral from minus t over two to t over two times e to the j n minus n naught omega naught t d t. Right? Where this exponent here is not zero anymore. Alright?

**[0:30:14]** And it turns out... Right. It's a little bit tricky to do it, but you can show that this integral here actually goes to zero for any n not equal to n naught. And so all we have left over here is this constant integrated from minus t over two to t over two. Right?

**[0:30:36]** When we take in a constant and integrate it, we just get the length of the integral over... Of the interval over which we're integrating. That's just that's just t. Right? So we're gonna get one over t times t times c sub n naught, which is just c sub n naught.

**[0:30:54]** Alright? And so that finally gets us to this coefficient being equal to this integral over here, which is basically this result that we have up here. Right? So that's just kind of sketching out how you get to that in case you're interested. Alright?

**[0:31:14]** Now what we wanna remind ourselves here of is that, again, right, when we have this expression here for f of t, then all the information about the function f of t is essentially... Is contained in the set of these coefficients here. Right? Or, equivalently, in c as a function of omega sub n. Alright?

**[0:31:41]** So, again, we'll remind ourselves that the set of all these coefficients, c as a function of omega sub n, right, that set contains all the information, alright, that's required to represent the function f of t, but now it's a representation in the frequency domain. Okay. Because c sub n... C c of omega sub n, alright, is effectively... It's a function of of frequency, and it doesn't have time in it at all.

**[0:32:35]** Alright? So this c as a function of omega n here, this integral here is eventually what is going to be the Fourier transform. Actually, t times this. Right? It's what is going to be the Fourier transform.

**[0:32:54]** Alright? So in order to get to that, right, we need to think a little bit carefully about how we take the limit of t going to infinity. Alright? Because... Alright.

**[0:33:08]** We're multiplying by one over t. So if we take the limit of t going to infinity, then this factor becomes zero over here. And, obviously, we don't want all these coefficients to be zero. Alright? So we have to figure out how we really...

**[0:33:24]** How we correctly take the limit of t going to infinity here. Alright? And to do that, let's let... We'll call it delta omega, right, be two pi over the period t. Alright?

**[0:33:41]** Then when we write the Fourier series for f of t, right, in complex exponential form, it's the sum of n going from minus infinity to infinity. Alright? Then we have the coefficients, c sub n or, equivalently, c of omega n. Alright? That's given by one over t times this integral.

**[0:34:11]** Alright? So we're gonna write down this integral here. Right? And then we're gonna pull out this factor one over t, and we'll include it in a factor of delta omega that we'll write at the end. Alright?

**[0:34:25]** So from the coefficient c sub n, then we'll just retain the integral here. Right? So the integral from minus t over two to t over two. Right? So note that we are not yet taking the limit of t...

**[0:34:37]** Capital t going to infinity. Alright? Then it's the integral of f of t prime e to the minus j omega sub n times t prime, d t prime. Alright? And then we have e to the j omega sub n t.

**[0:34:57]** Alright? Then for the one over t, right, that we pulled out of here, we're going to write one over two pi times delta omega. Okay. And the thing that we wanna notice here is that this thing that we have in the square brackets here, right, this thing... Alright.

**[0:35:21]** This is a function of only frequency, omega sub n, alright, because we're integrating over time. And, again, as we just said, all the information about f of t is contained in this function of omega n over here. Alright? So now we can take this expression and take the limit as t goes... Capital t goes to infinity.

**[0:35:55]** Alright. So that'll make the lower and upper limits of this integral minus infinity and infinity respectively. Then this quantity here, delta omega, which is two pi over capital t, that will go to zero. Okay? But we're taking an infinite sum over here.

**[0:36:16]** Alright? And if you remember back to what you might have done in your calculus course, what happens then is now in the limit of t going to infinity, right, if you have a sum from n going from minus infinity to infinity of something, right, it could be anything times delta omega, right, where delta omega is becoming infinitesimally small, then that infinite sum becomes an integral now from minus infinity to infinity of this same thing over here. Right? Same thing that we had over here, we keep over here, but it's an integral from minus infinity to infinity d omega. Alright?

**[0:37:11]** And then the other thing that we can do is that these frequencies omega sub n, right, when the period capital t was finite, these were discrete quantities. Right? Two pi n over capital t. But when capital t goes to infinity, then the omega n's become a continuous variable. So we'll just call it omega, right, which is a continuous variable.

**[0:37:45]** Okay. So now... Right, once we take the limit of t going to infinity, right, then from this expression that we have up here, right, f of t, now we can write as... We have one over two pi here, so we'll pull that out in front. Right?

**[0:38:05]** It's one over two pi times the integral from minus infinity to infinity of... Alright. That's converting this sum here to an integral as we said we could do over here. And then we have inside the square brackets. Now we have an integral from minus infinity to infinity of f of t prime e to the minus j omega t times t t prime rather, d t prime.

**[0:38:40]** And then we have, right, this e to the j omega t and then d omega. Alright? So now effectively, right, if you look at this, right, we have... Instead of the sum over all these discrete complex exponentials, we have an integral discrete exponentials with these coefficients here. We have an integral over a continuous variable in frequency omega of this quantity here, which is playing the role of those coefficients.

**[0:39:16]** Actually, one over two pi times this integral is playing the role of those coefficients times this complex exponential e to the j omega t. Alright? And just as in the Fourier series, right, the coefficients, right, this times this includes all the information that we need about the function f of t. But now in the frequency domain, this integral here includes all the information that we need now about f of t, but, again, in the frequency domain. And this integral here, alright, that's inside the square brackets, alright, we call this...

**[0:40:02]** It's a function of omega. So we'll call it capital f of omega, and this is what we refer to as the Fourier transform, okay, of f of t. And depending on the context and the convention followed by different practitioners or textbooks, sometimes, the factor of one over two pi is included in here, or sometimes it's square root of this that's included in here. But the main thing really is this integral. Right?

**[0:40:41]** And this is what we call the Fourier transform of f of t. And I... As I've been describing, we can think of it as being the representation of this particular signal, which in the time domain, we write as... And represent as f of t. In the frequency domain, we can write and represent it as its Fourier transform capital f of omega.

**[0:41:07]** Alright? And in either case, f of t or capital f of omega contain all the information that we need in order to completely specify that signal. Alright? So this function capital f of omega, right, the Fourier transform, this is the frequency domain representation of f of t. And in this way, it is similar, alright, to how, say, for phasors...

**[0:41:57]** Right. Remember, alright, this complex favorite phasor, v total, which is the amplitude times either the j five. Right? This is... Essentially, it's the frequency domain representation of v of t, right, being the same amplitude, v sub n times the cosine of omega t plus a phase shift phi.

**[0:42:29]** Right? And it's also similar. Right now, I'm not saying identical. I'm saying similar. Right?

**[0:42:36]** And for the Fourier series, Okay. The coefficients c sub n, right, represents f of t in the frequency domain. Okay. So that is the Fourier transform. Okay?

**[0:43:12]** So if we have some nonperiodic signal, alright, in the time domain and we want to figure out how to work with that in the frequency domain, then we can take the Fourier transform of that signal. That gets us to the frequency domain. And then that Fourier transform function, capital f of omega, basically tells us how much of any given frequency is necessary to accurately represent that nonperiodic signal in in the time domain. Okay. So so that is the Fourier transform.

**[0:43:52]** And so that then allows us to treat not only periodic signals, but also what the Fourier transform gets us is the ability to treat nonperiodic signals, alright, that extend from time equal to minus infinity to infinity. Alright? So that, again, is a major expansion, right, of the range of situations and signals that we can treat in circuits. And, hopefully, what we've seen... What you've seen here is how we can go from Fourier series to, in the infinite for...

**[0:44:30]** In the infinite period limit, the Fourier transform. So then the last thing that we wanna think about is what if we have a signal that, you know, is is not periodic but also leads to a four a transform that is tricky to calculate or undefined. Right? And it's easier to think of examples of this than you might think. Right?

**[0:45:05]** So now that we have the four a transform, what about signal like, say, f of t is equal to just the unit step function? Alright? Now we know we can treat that directly using the differential equation approach, right, because this is very simple. But, you know, it... For the Fourier transform, right, if what we're saying is that that can treat any non periodic signal, then you would think that it should be able to treat something like this.

**[0:45:42]** And it can, but it's tricky. Alright? Another example, alright, would be f of t equal to, say, t squared u of t. Alright? You know, something that is growing with time.

**[0:46:03]** You might have a signal that's growing with time if you have some... Something that's unstable. Right? And so it would be nice to be able to treat that as well. Right?

**[0:46:14]** So so what happens if we take f of t to be one of those forms, but... And then we try to calculate the Fourier transform. Right? So say f of t is equal to u of t. Right?

**[0:46:27]** Then f of omega, alright, capital f of omega, the Fourier transform, would be the integral from minus infinity to infinity of u of t, either the minus j omega t dt. Alright? We'll call this variable of integration here t now instead of t prime again because it it doesn't matter what we call. Right? So we'll just save ourselves having to write the primes.

**[0:46:53]** Right? Then this is going to be from the definition of the unit step function. It'll be the integral from zero to infinity of either the minus j omega t d t. Right? This integral here is tricky to calculate.

**[0:47:16]** Right? And if you think about it for a bit, then you'll see why it's tricky to calculate because it's not clear what the sine or the cosine of infinity is. Alright? It is possible to define things mathematically in a way that you can calculate this, but it's not so easy. Alright?

**[0:47:36]** And what about a second example? F of t is equal to t squared u of t. Then the Fourier transform, capital f of omega, would be the integral from zero to infinity of t squared e to the minus j omega t dt. Alright? You know, this is worse than tricky.

**[0:48:00]** This does not converge. Alright? Okay. So... Right.

**[0:48:14]** So we can't deal with this using, actually, any of the tools that we have developed up to this point. Alright? Unless we are willing to try to solve, you know, what may be a not so easy differential equation to solve. Alright? So then the question is, well, you know, is there some other transform like technique that we can use to treat that kind of sit...

**[0:48:39]** Those kinds of situations? Alright? Now if we look at, right, these two integrals here, right, this one and this one, then, you know, this is tricky to calculate. This one doesn't converge. What would solve both of those problems is if we just had, say, a decaying exponential factor in each of these integrands.

**[0:49:09]** Alright? So... Alright. If we just had an e to the minus, say, sigma t in here, right, where sigma is some real number that's posit... That's greater than zero.

**[0:49:24]** We just had e to the minus sigma t here... T over here. Right? Sigma is some real number greater than zero. Then, right, this decaying exponential will solve all of these problems.

**[0:49:34]** Okay? And so what we can say then is, well, let's generalize our thinking about what appears in this exponential here. Instead of having it be just a pure imaginary number, j omega, okay, Let's allow this to be complex. Okay? And we'll call that complex variable.

**[0:50:06]** That complex, basically, a complex version of... We'll call it the frequency. Alright? We will call that variable s. Alright?

**[0:50:16]** So what we can do now is that we can define a complex frequency. We'll call it s, and it'll have a real part, sigma, plus an imaginary part, j times omega. So sigma and omega here are real. Okay. Omega in here is just the frequency that we are accustomed to dealing with.

**[0:50:51]** Sigma now is something new. Right? Okay. So we can define... We're just gonna define now this gen...

**[0:51:01]** More general variable. Alright? Instead of just j omega, we'll take it to have a real component as well, and we will stick that in this exponential over here. Alright? And so we'll consider an alternative to the Fourier transform.

**[0:51:30]** Right? And this alternative is going to be a new transform function. Okay. We'll call it nef now of s, right, that is defined in what we call... Instead of calling it the frequency domain, we'll call it the s domain.

**[0:51:58]** Right? Because that's the variable that we're using, or we can call it... And it's called both of these things in books and literature in the field. We'll call this the complex frequency domain. Okay.

**[0:52:21]** And so this function f of s now is going to be the integral from zero... Well, and we'll say zero minus explicitly for for a reason that I'll describe in a minute to infinity. It's the integral of f of t e to the minus s t d t, where s now is a complex number or can be a complex number. Okay? And our notation here with the zero minus, right, this indicates explicitly, right, that f of zero is included in the interval.

**[0:53:23]** Okay. This notation... The notation is used this way in Ulaby, but in other sources, you may just see this written as not zero minus, but just as zero. So the integral from zero to infinity. Alright?

**[0:53:38]** But in the context of this setting here, then it should be taken to include the value of the integrand at t equal to zero. Alright? And then the other point to note here is that, right, if we were really making this analogous to, the Fourier transform, then the integral would go from minus infinity to infinity, not zero to infinity. Right? There are circumstances where this particular transform can be defined that way.

**[0:54:13]** But for our purposes, we will define it from zero to infinity. It makes things a little bit simpler because by taking the integral from zero to infinity, then for the real part of s being positive, then we know this is gonna converge. Right? So we include only t greater than equal to zero in the interval rather than the full range of t going from minus infinity to infinity. Because otherwise, the integral it wouldn't converge, right, for the real part of s being nonzero.

**[0:55:12]** It wouldn't necessarily converge. Right. And often, it wouldn't converge. Alright. Because, right, in in one direction, you would be getting a growing exponential rather than a decaying exponential one direction in time.

**[0:55:29]** Okay. But once we have the possibility of this exponential being complex and that is having a decaying real component, alright, then all these kinds of integrals will converge nicely, and this transform will be well defined and nice and convergent and so forth. Alright? So now, right, if we have f of t equal to u of t or f of t equal to, say, t squared times u of t and many other things that could not be treated, right, using Fourier transforms. Alright?

**[0:56:19]** In this case, now this alternate transform f of s, it can easily be computed, alright, as long as the real part of s is positive. Alright? Because then the integral will have a decaying exponential, right, and sufficiently large... And the decaying exponential will kill just about any... Right?

**[0:56:49]** It'll allow this converge for, you know, any non exponentially growing function within reason for f of t. Alright? And if f of t is exponentially growing, you just have to pick the real part of s large enough to cancel that out. Okay. So now this new transform function f of s, this is what we call the Laplace transform.

**[0:57:22]** Okay. And among other things, right, what it allows us to do, right, is that it allows us to analyze signals that have initial conditions at t equal to zero, right, because that's one of the boundaries of the integral. And, right, that are constant or growing as t goes to infinity. And there are circumstances where that can be useful as well. Okay.

**[0:58:09]** So so those are the tools that we'll be introducing and working with over the remainder of the semester. Fourier series, Fourier transforms, and Laplace transforms. Although we will start with the last of these, the Laplace transform, then we'll go to Fourier series and Fourier transforms. Alright. But just to recap, right, all these series and transform techniques allow us to do...

**[0:58:35]** What they allow us to do is, for each one of them, to really greatly expand the range of the types of signals for which we can analyze the behavior of circuits and for which we can develop an understanding that will allow us and you to design suitable circuits with a given functionality. Right? So we talked first about four a series. Okay. And the idea here was that if you took a superposition, right, of frequencies or at least the appropriate superposition of frequencies, right, each of which can be analyzed using phasors.

**[0:59:30]** Alright. This allows us then to analyze circuits with any periodic signal. Right? Not just sinusoidal signals. Alright?

**[0:59:48]** So that's a major expansion, right, in what we can what we can treat. Then from there, we saw how taking the limit of that period in a Fourier series to go to infinity led us to the Fourier transform. Okay. And so the Fourier transform then is an extension of the idea of the Fourier series to an infinite period, and this allows us to analyze circuits with nonperiodic signals. Alright?

**[1:00:45]** Again, a major expansion in the class of circuits that... And signals in circuits that we can analyze and understand and design around. And then finally, we got to Laplace transforms, okay, which involved essentially generalizing the concept of frequency so that it can be complex. Right? So this was then an extension to complex frequencies, alright, which include then the possibility of oscillation.

**[1:01:31]** Alright. That's the imaginary part of the complex frequency and exponential decay or growth, right, from the real part of the complex frequency. And this then allowed us to analyze or will allow us to analyze circuits with signals that are defined, right, for positive times, right, and that have initial conditions that we want to incorporate. Right? And it includes signals with...

**[1:02:32]** That have growing amplitude as time goes to infinity. Right? And there are circumstances where that can be very useful as well. Having initial conditions is is very common. Okay.

**[1:02:50]** So so that's sort of a broader picture of these fourier and Laplace techniques, how they're related to each other, a little bit about mathematically where they come from and what they enable. Right? And, you know, with that as background and context, then perhaps what we do with respect to the applications of these techniques to different types of circuits and signals that go into them, perhaps that will sort of make more sense by have... Being able to look at them in this this bigger picture. And, hopefully, also, this will help set the stage for you to understand these techniques better when you encounter them again in ECE three thirteen and other courses.

**[1:03:40]** Okay. So that is it for this recording.
