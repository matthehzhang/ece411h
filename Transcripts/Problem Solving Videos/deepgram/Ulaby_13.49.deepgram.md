# Ulaby 13.49 video

Deepgram general-nova-3 2025-07-31.0, request 01a1b03a-b03a-7c30-9c70-85725ffacb40, audio 57.7 min.

**[0:00:03]** Okay. This is UOB problem 13.49, and this is an example of, once again, circuit analysis using Fourier transforms. Okay. So the problem, that we are addressing is shown, here on the left. There's actually a misprint in the statement of the problem.

**[0:00:38]** The problem in the book says the circuit in figure p 13.19, but that's actually not correct. The circuit in that figure doesn't include any, output voltage. What they actually meant was the circuit and figure p 13.18, which is shown down here. And so what we are asked to solve for is this output voltage v out labeled here, given an input f of t, where, f of... I sub s of t is equal to f of t given by this triangular waveform shown here.

**[0:01:23]** Okay. So part a asks us to derive an expression for v out using Fourier analysis in terms of these circuit parameters here, r one, r two, and c, and then... And a and capital t. Part b asks for a plot of the output voltage with specific numerical values for all these parameters. And then part c asks for a plot with a different value of the capacitance, point three three millifarads instead of point three three microfarads.

**[0:02:00]** Okay. So let's go ahead and get started on this. And so we will start off as usual by redrawing the circuit. So we have a current source I sub s of t. And then a resistor r one, another resistor r two, and then a capacitor c.

**[0:02:36]** Okay. And, we are asked to solve for this output voltage. Alright? The circuit diagram also has currents I one and I two labeled here. We'll use I two, in part of what we work out.

**[0:02:58]** The, circuit parameters in part b of this problem are that r one is equal to 500 ohms, r two is equal to two kiloohms, and then c is equal to point three three microfarads. Okay. And then the input waveform, I sub s of t, okay, is basically a triangular waveform, not a periodic triangular waveform, just a triangular waveform that looks like this. Okay. So so here, the form of this is that I sub s of t is equal to a over capital t times the time t for zero less than equal to t less than equal to capital t, and it is zero outside of that interval.

**[0:04:12]** And in part b of the problem and part c, we take a equal to five amps and then t equal to three milliseconds. Okay. So, let's go ahead and solve this problem. Alright. So what we're going to do here is we're going to, take this circuit.

**[0:04:35]** We're gonna transform it to the frequency domain, including, computing the Fourier transform of I sub s of t given by this expression here. Right? So that we have all its different frequency components. We will analyze the circuit in the frequency domain to obtain v out as a function of frequency. And then we'll have to compute the inverse Fourier transform, of that to get v out of t.

**[0:05:04]** Alright? So that's how we're going to proceed here. So if we're working in the frequency domain, right, we wanna have our source I sub s of t transformed to the frequency domain. So that would be I sub s... Capital I sub s of omega.

**[0:05:22]** Right? So that is the Fourier transform of I sub s of t. Alright? And that is given formally by the integral from minus infinity to infinity of I sub s of t times e to the minus j omega t dt. Okay.

**[0:05:45]** And if we substitute into that, this expression here for I sub s of t, which is valid between zero and capital t, then we have the integral from zero to capital t of a over t times t times e to the minus j omega t dt. Okay. So here, now, we wanna deal with this factor of t over here in the integrand, and so we're going to deal with that by doing integration by parts. So remember what integration by parts says is that the integral of u dB is equal to u times v minus the integral of v d u. Okay.

**[0:06:28]** So this is the integral that we're starting with over here. This is what we will... I have to compute after doing the integration by parts. And so, what we will want to do then is since we have d u over here, alright, we want to pick u such that it allows us to take the derivative of t so that it becomes just a constant in this integral over here rather than a factor of t. Alright?

**[0:06:54]** And then, whatever is left in here as dV has to be something that we can integrate. Alright? So we can do that by choosing u to be equal to t and d v to be equal to the rest of it, either the minus j omega t d t. Right? A over t here is a constant, so we can just pull that outside the integral.

**[0:07:19]** We don't have to worry about it until later on. So then d u is equal to d t, and v is equal to minus one over j omega times e to the minus j omega t. Alright? So if we then use integration by parts to work with this integral over here, we have the constant factor of a over t, which we take to the outside. And then for u times v, we have t times minus one over j omega times e to the minus j omega t evaluated at the limits of integration zero and t.

**[0:08:04]** So we have minus t over j omega times e to the minus j omega t evaluated at zero and t. And then for minus the integral of v d u, then we have minus minus here. So that becomes plus one over j omega times e to the minus j omega t times d t. Alright? So we have plus the integral from zero to t of one over j omega e to the minus j omega t d t.

**[0:08:43]** Okay. And then, if we evaluate this first term over here, then evaluating at the upper limit, we get minus capital t over j omega times e to the minus j omega capital t. And then at the lower limit of integration, this becomes zero because of this t over here, which, takes on a value of zero. So we get a over t. And then from this first term over here, we have minus capital t e to the minus j omega capital t over j omega plus...

**[0:09:23]** And then from the integral, we have one over j omega, which we pull to the outside. And then we're integrating e to the minus j omega t, and that is minus one over j omega times e to the minus j omega t evaluated at the limits of integration zero and capital t. Okay. And so then, if we go ahead and we'll just carry this first term down, and then we'll evaluate this second term over here. So we have a over t times minus t e to the minus j omega capital t over j omega.

**[0:10:04]** And then we have minus one over, j omega, the quantity squared. Okay. So that gives us, minus one over j omega, the quantity squared. And then, we have e to the minus j omega t evaluated capital t minus, the same thing evaluated at zero. That is e to the minus j omega capital t minus one.

**[0:10:37]** Okay. And then, if we just rearrange this slightly, we'll have a over t, and then we'll factor out an omega squared in the denominator. Right? That takes this omega squared out here. Then we have j squared in the denominator.

**[0:10:57]** That becomes minus one that cancels out this plus sign. Alright? And then from this term over here, we'll get a j omega in, the numerator. Okay. So we have a over t omega squared, and then we have one plus j omega t times e to the minus j omega t minus one.

**[0:11:29]** Alright? So so this is what we get finally for I sub s of omega. Okay? So now with this, what we want to do is we want to go back to the circuit up here. Alright?

**[0:11:54]** And, we want to figure out this output voltage v out in the frequency domain. And the way that we can do that is to compute, in the frequency domain, this current I two of omega, which we can do by current division since we know that the total current is I sub s of omega, and that current gets divided between I one and I two since this branch and these, this part of the circuit here are in parallel. Alright. So we can get I two by current division. And then once we have I two, then v out is just the impedance associated with the capacitor, which is one over j omega c times I two.

**[0:12:38]** Alright. So, what we wanna do next then is to analyze the circuit in the frequency domain with the impedance of the capacitor being one over j omega c. Okay. So if we do that, then as I was describing, the current I two in the frequency domain can be obtained by current division. So that's going to be r one, the impedance of the other branch of the two parallel branches divided by the sum of the impedances of the two branches, which is r one plus r two plus one over j omega c.

**[0:13:33]** All of this times the total current that gets divided I sub s. Right? And then once we have I two, then v out is just going to be the impedance of the capacitor times I two since v out is the voltage across the capacitor and I two is the current through the capacitor. So that's going to be one over j omega c times I two. And, I two is given by this expression here, where I s is given by this expression over here.

**[0:14:12]** Okay. So now this means that we can write v out as being equal to, this expression here I two times one over j omega c. Right? So we're gonna have a factor of j omega c that we're introducing in the denominator. So what we get then is in the numerator, we still have r one.

**[0:14:40]** Alright. That's this r one from up here. And in the denominator, when we multiply this by j omega c, we get one from this one over j omega c times j omega c plus j omega times r one plus r two times c. All this times I sub s. I sub s is given, by this expression up here.

**[0:15:08]** Okay. This is a plus sign here. Alright? And so if we take that and we substitute it in here for I sub s, then what we get is that v m is equal to a times r one over t times omega squared. K.

**[0:15:30]** We'll try to keep these all, visible. Right? So we have a over t omega squared times r one. That gives us this factor here. Then we have what's in the square brackets, for I sub s up here divided by this denominator over here.

**[0:15:51]** Okay. So we have one plus j omega t times e to the minus j omega t minus one in the numerator divided by one plus j omega r one plus r two times c in the denominator. Okay. So now this is our expression for v out. And, to work with this further, what we are going to do is we're going to bring this omega squared back in here, and we're going to separate out, this expression into three terms corresponding to these three different terms in, the numerator.

**[0:16:48]** So that'll give us a one, a r one over t. And then we will have, for this first term here corresponding to the one, it is e to the minus j omega t divided by... Now we're bringing the omega squared inside, the square brackets. So we have omega squared times one plus j omega r one plus r two times c. Alright?

**[0:17:20]** Then from the second term, right, it's j omega t times e to the minus j omega t in the numerator. This omega will cancel out with one power of omega in the denominator. So we're going to get in the numerator j times t e to the minus j omega t divided by, in the denominator, omega times one plus j omega r one plus r two times c. And then from the third term over here, this minus one in the numerator, we're gonna get minus one over omega squared times one plus j omega r one plus r two times c. Okay.

**[0:18:09]** So now we have v out of omega, right, written in this form here, and we are going to need to figure out how to calculate the inverse Fourier transform of this. So, what we're going to need to do is to take this and express it in a way that allows us to, easily identify, say, the frequency side of known Fourier transform pairs or that we can calculate the... Such that we can calculate the Fourier transform, explicitly, relatively easily. Okay. So, let's look at these three terms here.

**[0:18:52]** Alright? We can see this third term out here is one that we can deal with, fairly easily. Because if we do a partial fraction expansion of this, then, we'll get this into a form of basically a sum of simple poles, and that's something that we know how to, for which we know how to compute the Fourier transform. Alright? Basically, it's going to be, exponentials.

**[0:19:20]** Alright? Then these other terms over here, alright, we have, these exponential factors. The j times capital t here is just a constant, so we don't really need to worry about that. And then we have, various combinations of poles in the denominator. Alright?

**[0:19:40]** So we're gonna deal with this term here first, and we will deal with this by computing its partial fraction expansion. And then from there, we'll look at this term over here. We'll compute the partial fraction expansion of just the part... Taking the numerator to be one. So, basically, just the denominator portion of this.

**[0:20:06]** We'll figure out how to deal with the exponential later. This first term is the same as this third term over here times e to the minus j omega t. Alright? So by understanding how we can deal with the exponential over here, that will also allow us to deal with this, this particular term. Okay.

**[0:20:26]** So we're starting off with this third term on the right. So we're gonna let... Let's define a function. We'll call it capital f one of omega, and we'll take that to be one over omega squared times one plus j omega r one plus r two times c. Okay.

**[0:20:50]** I... And then we'll deal with the minus one here later. Alright. So for this, alright, what we want to do is to compute its partial fraction expansion. Right?

**[0:21:02]** So that's gonna be k one over omega plus k two over omega squared plus l one over one plus j omega r one plus r two times c. Right? And k one, k two, and l are just constants. Alright? And we saw, when we talked about Laplace transforms, how we can calculate these.

**[0:21:29]** Okay. K two is equal to, right, omega squared times f one of omega. Right? Evaluated at omega equal to zero. And, if we just take this expression here for f one multiplied by omega squared, so we cancel out this omega squared in the denominator, evaluate this as a may...

**[0:21:50]** At omega equal to zero, we can see this is just one. Then k one is equal to the derivative with respect to omega of omega squared f one of omega evaluated at omega equal to zero again. Okay? And, for this, right, if we have omega squared times f one, that's one over one plus j omega r one plus r two times c. And if we take the derivative of that with respect to omega, then we will get in the numerator minus j times r one plus r two times c divided by the denominator squared.

**[0:22:40]** So one plus j omega times r one plus r two times c, the quantity squared. This evaluated at omega equal to zero. When we set omega equal to zero, the denominator becomes one. So this is now minus j times r one plus r two times c. Alright?

**[0:23:02]** And then finally, for the residue l one, that is given by one plus j omega times r one plus r two times c times f one of omega. This evaluated at omega equal to its value at the pole, which is j times one over r one plus r two times c. Okay. And, if we take one plus j omega times r one plus r two times c, multiply it by f one of omega, right, then we're just going to get one over omega squared. And, if we calculate one over omega squared for this value of omega, then we're going to get minus r one plus r two, the quantity squared times c squared.

**[0:23:55]** Okay. So those are our three, residues that we need for the, partial fraction expansion of this function f one of omega. Okay? And then that gives us the result that f one of omega is equal to, k one over omega. Right?

**[0:24:19]** So that's k one is this. So minus j times r one plus r two times c over omega over omega plus k two over omega squared. K two is one, so plus one over omega squared. And then plus l one over one plus j omega r one plus r two c. So l one is this.

**[0:24:45]** So we have minus r one plus r two squared times c squared divided by one plus j omega r one plus r two times c. Okay. So now we have f one of omega in a form with these three terms here where, we can compute its inverse Fourier transform. Right? Taking this back to the time domain using various entries from, the table in ULEB.

**[0:25:19]** That's table 13 dash four that contains, common Fourier transform pairs. Alright. So then from here, from Ulaby et al, table 13 dash four, right, the results that are going to be relevant are that the sine function of t, right, forms a Fourier transform pair with two over j omega, then that the absolute value of t forms a Fourier transform pair with minus two over omega squared, and then that e to the minus a t times u of t forms a Fourier transform pair with one over a plus j omega. Okay. So using these results and what we computed for f one of omega up here, then what we get is that for this first term over here, right, we get...

**[0:26:33]** We use this result. Right? This Fourier transform pair, the sine of t, forms a Fourier transform pair with two over j omega. And... Right.

**[0:26:42]** So we get that f one of t. Right? The inverse Fourier transform of f one of omega up here is... The first term is going to give us r one plus r two times c over two times the sine of t. Alright?

**[0:27:04]** Then the second term, one over omega squared, okay, is going to give us minus one half times the absolute value of t. So minus one half times the absolute value of t. And then this third term over here is going to give us, minus r one plus r two times c. Right? We're gonna pull out a factor of r one plus r two times c from the denominator.

**[0:27:32]** They cancels with one power of those up here, and we will have, one over r one plus r two c plus j omega. And then the end result of that is that this third term gives us, in the time domain, r one plus r two times c times e to the minus t over the quantity r one plus r two times c times u of t. Okay. So that is the Laplace transform... The Fourier transform this function f one of t.

**[0:28:17]** Okay. So we're gonna keep that result in mind because we're gonna use it later. Okay. Now let's go back to v out. Right.

**[0:28:34]** This is v out. Okay. And let's think about how to deal with this term over here. So as an intermediate step to dealing with this term, then what we're going to do is we're gonna think about a function in the frequency domain that is just one over omega times the quantity one plus j omega r one plus r two times c. Alright?

**[0:29:00]** So let us... Let now another function. We'll call it f two of omega. We'll take that to be one over omega times one plus j omega times r one plus r two times c. Right?

**[0:29:17]** And we want to perform a partial partial fraction expansion of this. Okay? So we're gonna get k one over omega plus l one over one plus j omega times r one plus r two times c. Alright? And we need to compute, these residues k one and l one.

**[0:29:46]** So k one, right, we know is just going to be omega times f two of omega evaluated at omega equal to zero. Okay? And so if we multiply f two by omega, we cancel out this omega in the denominator. We evaluate what's left at omega equal to zero. That's just one.

**[0:30:05]** Okay? Then we have l one, and that is one plus j omega times the quantity r one plus r two times c times f two of omega evaluated at omega equal to j times one over r one plus r two times c. Okay? And if we if we take one plus j omega r one plus r two times c, multiply by f two of omega, then what we get is just one over omega. We're gonna evaluate that at this value of omega over here.

**[0:30:48]** And so that gives us minus j times r one plus r two times c. Okay? And so that means that f two of omega, right, it's partial fraction expansion is given over here with k one equal to one, l one equal to minus j times the quantity r one plus r two times c. So f two of omega then is one over omega minus j times r one plus r two times c divided by one plus j omega r one plus r two times c. Alright?

**[0:31:35]** So now here... Okay. These are... Once again, these are results in the frequency domain that we can look up in, Ulaby et al table 13 dash four. And using that, then, we can directly write down what the corresponding inverse trans...

**[0:31:56]** Inverse Fourier transformed time domain functions are. So now, again, at this point, we're using results from Ulaby et al, table 13 dash four, alright, then what we get is that f two... Oops. F t, okay, is equal to... So for one over omega, right, we use the, Fourier transform pair that the sine of t forms a Fourier transform pair with two over j omega or equivalently, one over omega forms a Fourier transform pair with j over two times the sine of t.

**[0:32:54]** So we have j over two times the sine of t from the one over omega, and then from minus j times r one plus r two c over one plus j omega r one r two c, then, we use this, Fourier transform pair over here. And what we get is that, we have minus j times e to the minus t over r one plus r two times c times u of c. Okay? So this is the inverse Fourier transform of f two of omega. Okay.

**[0:33:48]** So now what we want to do is to go back to our expression for v out over here and write this in terms of our functions f one of omega and f two of omega and whatever else we need. And if we do that, then what we get is the v out of omega is a r one over t. Okay. That's our overall, factor out in front. And then from that first term in our expression for v out, that we had up above, we get e to the minus j omega t times f one of omega.

**[0:34:45]** Right? That's this term over here. Alright? Because f one of omega is just this one over omega squared or it's it's one over omega squared times this quantity in the parentheses here. Alright?

**[0:35:03]** This second term is going to be j times t times e to the minus j omega t times f two of omega. Right? Because f two of omega was one over omega times this quantity in the parenthesis. And then this third term over here is just going to be minus f one of omega. So if we come back down here and write that down, the second term is plus j times t times e to the minus j omega t times f two omega, and then the third term is minus f one of omega.

**[0:35:42]** Okay. So, we know how to transform, f one of omega, to the time domain. Right? This will just give us f one of t, right, which we calculated up here. Alright.

**[0:35:58]** These other two terms have these exponential functions either the minus j omega t in them. Right? The j t here is just a constant, so we don't really have to work too hard to deal with that. We just keep multiplying by it. Alright?

**[0:36:14]** But to deal with the exponential factors, then what we want to do is to take advantage of what's known as the time shift property of Fourier transforms. And that's something that we discussed in class and also it's in Ulaby at all table 13 dash five, the table of Fourier transform properties. Okay. So to transform the app of omega to the time domain, Alright. What we also need to do is, we can note, the time shift property.

**[0:37:07]** For a transforms. Okay. And this is in... You'll be at all table thirteen dash five. Okay.

**[0:37:24]** And what the time shift property, tells us is that f of t minus some constant t naught in the time domain forms a Fourier transform pair with either the minus j omega t naught times f of omega, where f of t and f of omega themselves form a Fourier transform pair. Right? So this says that an exponential phase factor in the frequency domain corresponds to a shift in time in the time domain. So that will allow us to deal with these exponential factors that show up here and here in v out of omega. Alright?

**[0:38:11]** And so if we use this property here along with the f one of t and the f two of t that we calculated several minutes ago, alright, then what that will finally give us is that v out of t is equal to the following. See if we can keep that there. So it's going to be a r one over t. And then from this first term, this is going to give us, just a, it'll give us small f one of t, but evaluated at a time shifted time t minus capital t. Okay.

**[0:39:01]** And so that is going to then be... If you go back and look at, what we had for f one of t. Right? It's this. So we're gonna get these three terms evaluated not a t, but a t minus capital t.

**[0:39:19]** Okay? So if we write those down, then it's going to be r one plus r two times c over two times the sine of t minus capital t minus one half the absolute value, not of t, but of t minus capital t minus r one plus r two times c times e to the minus, and then it's t minus capital t divided by r one plus r two times c times u of t minus capital t. Okay? Then here from this second term, we're going to have lowercase f two of t times j t, but f two of t is going to be evaluated not at t but at t minus capital t. So f two was given by, this expression over here.

**[0:40:25]** So we're going to evaluate this at t minus capital t and multiply it by j times t. Alright? And so if we do that, alright, then we get minus capital t over two times the sine of t minus capital t, alright, plus capital t times e to the minus t minus capital t over r one plus r two times c times u of t minus capital t. And then finally, we will have minus, and then from f one of omega, when we perform the inverse Fourier transform of that, we just get... We get minus f one of t.

**[0:41:21]** Alright? And so that is going to be minus r one plus r two times c over two times the sine of t plus one half times the absolute value of t plus r one plus r two times c times e to the minus t over r one plus r two times c times u of t. Alright? And we will write this in a slightly different way now for the final result, alright, just by grouping the terms a little bit differently. So we have a r one over t out in front.

**[0:42:14]** And then to start off with, we will put together, these terms here that have the exponential exponentially decaying functions over here. Alright? And so first, we'll have the exponentially decaying function evaluated at, just t. So we will have r one plus r two times c times e to the minus t over r one plus r two c times u of t. Alright.

**[0:42:50]** That's this term here. And then for these two terms here, we're going to have t minus the quantity r one plus r two times c. Both of those times the exponential factor now evaluated at t, minus capital t times the unit step function at t minus capital t. So we're going to have plus t minus r one plus r two times c times e to the minus t minus capital t over r one plus r two times c times u of t minus capital t. Okay?

**[0:43:39]** So that takes care of this term and this term. Then we will have our terms that are proportional to the sine function. Again, we will start with, this one that is not time shifted. So we have minus one half r one plus r two times c times the sine of t. Right?

**[0:44:06]** That's this function here... This term here. And then we'll have these two terms here, and we'll write those as minus one half times t minus the quantity r one plus r two c, alright, times the sine of t minus capital t. Right? So that's this term and this term.

**[0:44:38]** And then finally, we will have, the terms that have the absolute value, of t. Okay. So we have plus one half times the absolute value of t, that's this term, minus one half times the absolute value of t minus capital t. That is this term here, and that is everything. Okay.

**[0:45:15]** So that is the result from for part a. Alright? So we've calculated analytically an expression for v out of t, in terms of, the parameters r one, r two, c, capital a, and capital t. Alright? Part b asked us to...

**[0:45:40]** If we go back to the statement of the problem back here, Okay. It asked us to plot v out using these numerical values, alright, for these different parameters. And so for that, I... What I will do is I will just paste in from the solutions. K.

**[0:46:14]** So let me do that on the other computer here. Okay. Let's see if that pasted in here. Okay. It should be showing up soon.

**[0:46:56]** Okay. There it is. So, so I sub s of t, remember, is this function here. Right? And then v out.

**[0:47:07]** Right? Basically, what you can see is that as I sub s is increasing, then we're gradually... Basically, we're gradually charging up the capacitor. Right? Because v out is the voltage across the capacitor.

**[0:47:20]** So we're gradually charging it up. When the current turns off, then we are discharging the we're discharging the capacitor. Alright? So it discharges like this. Okay.

**[0:47:36]** So that is part b. Alright? Then part c is that we change c from point three three microfarads to point three three millifarads. Okay? And, if we do that, right, basically, what we should expect is that the time constant, for discharging should increase.

**[0:48:11]** Okay? And so what we'll do here is we will paste that in as well. Yes. Grab this. K.

**[0:48:51]** And Paste that in, and we will wait for that to show up. Okay. And it looks like this. So, basically, what we see is that... Right.

**[0:49:29]** The charging doesn't necessarily look that different. But, actually, it is different because if you look up here, right, it's charging up to... This is times 10 to the minus... Right. So so on this scale here, it's 1,500.

**[0:49:50]** Alright? This scale up here, this is only single digits. Okay? So, it is... The capacitor is actually charging up much more slowly, and it's also discharging, much more slowly.

**[0:50:02]** Alright? So, basically, what happens is that when the capacitance is increased, then the characteristic time constant, which is the quantity r one plus r two times c, correspondingly increases as well. And so the charging and discharging of the capacitor is much slower, which is what the numerical results basically show us. Right? So when the capacitance is increased from point three microfarads to point three three millifarads, right, then what happens is that the exponential time constant, r one plus r two times c, right, for the capacitor charging and decay.

**[0:51:09]** And then correspondingly, v out of t, alright, it increases by factor of 10 to the third. Alright? And we see that in the numerical results. Okay. So what are the key points if we go back and look at what we did here?

**[0:51:44]** What are the key points and, perhaps lessons, that we can draw from this? Okay. The first is that... Alright. Once again, if you watch some of the other, examples, when we're doing circuit analysis by Fourier transform, what we do essentially is we take the known source voltages and or occurrence, and we compute their Fourier transforms so we see what different frequency components those source voltages and or occurrence contain.

**[0:52:18]** Right? Then we analyze the circuit in the frequency that is the phasor domain so that we obtain the response of the circuit, whatever quantity we are trying to solve for as a function of frequency. Right? That works at each different frequency. Right?

**[0:52:34]** And so we get a function of frequency. And then once we have that function of frequency, then we perform the inverse Fourier transform to bring it back to the time domain, which is where we typically want our, final result. And to do that, what we wanna do is to take our function in the frequency domain and put it into a form that, allows us to more straightforwardly compute or look up the inverse Fourier transform. Right? Either by looking at, so the common Fourier transform pairs in, table 13 dash four of Ulaby or, by taking advantage of, some of the, known properties of, Fourier transforms, which are listed and summarized in table 13 dash five.

**[0:53:30]** Okay. So, the first point is that if we're doing a Fourier transform circuit analysis, then, essentially, what we're doing... What we want to do is we wanna compute the Fourier transform or transforms of our known source voltages and or currents, Right. That tells us, what is... What are the components of those known source voltages and or currents at different frequencies?

**[0:54:19]** And then once we have that, we can analyze the behavior of the circuit as a function of frequency. Right? So, essentially, add each, different frequency and the frequency that is basically the phasor domain. Right? So then we analyze the circuit and the frequency, right, basically, that is the phasor domain.

**[0:54:49]** Alright? Once we've obtained our result in the frequency domain... Right? So once the desired voltage or current right. Here it goes.

**[0:55:05]** And or current is obtained in the frequency domain, then what we want to do is, to put that function or those functions in a form that is easily transformed back to the time domain using either known Fourier transform pairs or, the various properties of Fourier transforms. Right? So we wanna use known Fourier transform pairs. Right? Ulaby.

**[0:55:52]** That's in Ulaby table 13 dash four and or for you transform properties. Those are in table 13 dash five, right, to compute the inverse for a transforms and thereby to obtain our results in the time domain, okay, which is where we typically want them. And so what we did with respect to the latter in this particular example was we used the time shift property of Fourier transforms to handle exponential factors that were present in the frequency domain. Right? So here, we used the time shift property.

**[0:57:09]** Right? A four d transforms to handle the exponential factors that were present in the frequency domain. Okay. That's not the only way to do it, but, I think in this case, it was actually the simplest way to do it. Okay.

**[0:57:37]** So that is everything for this example, and I'll stop the recording now.
