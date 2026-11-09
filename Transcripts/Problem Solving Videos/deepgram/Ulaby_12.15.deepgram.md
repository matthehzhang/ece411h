# Ulaby 12.15 video

Deepgram general-nova-3 2025-07-31.0, request 01a1b039-ff82-70a1-b726-43ecd806104b, audio 54.4 min.

**[0:00:04]** Okay. So this is Ulaby problem 12.15, and this is another example of a circuit analysis using Laplace transforms. Okay. And as it turns out, for this example, it will end up being useful to check the solution by solving using differential equations. Okay.

**[0:00:48]** So we'll see the same circuit here analyzed both ways. Okay. So, this is the circuit that we're looking at over here. Alright. It's a relatively simple circuit, and it has, a voltage source in it that turns on a t equal to two seconds and then goes from zero to one volts, at t equal to two.

**[0:01:12]** Okay. So let's go ahead and, analyze this. So we will redraw the circuit as usual. Okay. So we have two resistors, r one and r two, excuse me, that are connected in parallel.

**[0:01:38]** Then we have an inductor and a capacitor. So the circuit's like this. The voltage source is v sub s of t, and the inductor is l, capacitor c, and we wanna solve for the current through the inductor, I sub l of t. And our circuit parameter values are that r one and r two are each equal to four ohms. The inductance is two Henry's, and the capacitance is point five farads.

**[0:02:13]** And the voltage source, v sub s of t, okay, is like this. I'll draw it in blue here. So it is zero up until two seconds, and then it increases to one volt. Okay. So that is the voltage source.

**[0:02:46]** So analytically, we can write that as v sub s of t is equal to just the unit step function times t minus two, and that's in volts. Okay. And what we wanna do here is to solve for the current I sub l of t. Okay. So the first step here as usual will be to determine the initial conditions for t equal to zero minus.

**[0:03:24]** And in particular, we want the initial conditions for the current through the inductor, I sub l, and for the voltage through the capacitor, across the capacitor v sub c. Alright? So if we're looking at times less than zero, right, then, the voltage source has been off for a long time. Things are in steady state up to that point. And so we take the inductor.

**[0:03:53]** We can convert that to a short circuit. The capacitor behaves as an open circuit. Okay. And v sub s is equal to zero at times less than zero. And we can see pretty easily that in that situation, the current through the inductor at t equal to zero minus is zero.

**[0:04:21]** Right? Because there's no voltage driving the, any current, and the voltage across the capacitor at t equal to zero minus is also equal to zero. So that means that when we convert this circuit to the s domain, then we do not have to introduce any additional sources to account for these initial conditions or, hopefully, those sources will have values of zero. Okay. So now...

**[0:04:51]** Alright. The second step is to transform the circuit to the s domain for t greater than or equal to zero. Okay? So when we do that, we will have a voltage source, v sub s now of s, then we have our resistors. But those are just two four ohm resistors in parallel.

**[0:05:22]** So we can replace those with an equivalent resistance that's just two ohms. Right? Because, two four ohm resistors in parallel has an equivalent resistance of two ohms. Then we have our inductor and capacitor. Okay.

**[0:05:45]** And so the inductor has impedance equal to s times l. So that's just two s since the inductance is two Henry's. And then the capacitor has inductance z sub c... Or sorry. Impedance z sub c.

**[0:06:01]** So that's just one over s c. C is one half, farads. So this becomes two over s. And what we wanna solve for is I sub l of s, the current through the inductor, which is also the current through the capacitor. Okay.

**[0:06:18]** And then finally for the source, in the time domain, the source is u of t minus two. And, if we look at table 12 dash two in Ulaby that has the various common Laplace transform pairs, then we can see that v sub s of s must be e to the minus two s over s. Okay. So this is from Ulaby et al, and it's table 12 dash two. Okay.

**[0:06:57]** So this is the circuit in the s domain. Alright? What we wanna do now is just to do the circuit analysis in the s domain. Right? So now we wanna analyze the circuit in the s domain.

**[0:07:17]** And then in doing so, we can solve for I sub l of s. And then by doing, the inverse Laplace transform, we'll get I sub l of t, which is what we ultimately would like to solve for. Okay. So, to solve... To analyze the circuit in the s domain, essentially, all we have to do is to apply KVL around the circuit loop here.

**[0:07:45]** Okay? So we're going to apply KVL around the circuit loop. And so starting from this voltage source over here, we have that minus v sub s plus our equivalent times I sub l. Right? That's the voltage across the resistor plus z sub l I sub l, the voltage across the inductor, plus z sub c I sub l, the voltage across the capacitor, all that has to add up to zero by k v l.

**[0:08:28]** And if we substitute in now the numerical and s dependent values for these various impedances, then for the resistor, we have two ohms. For the inductor, we have an impedance of two s. For the capacitor, we have an impedance of two over s. All of this is times I sub l, and then that's equal to v sub s where we've taken minus v sub s and moved it to the right hand side. It becomes v sub s.

**[0:08:59]** Okay. Or I... If we solve this for I sub l, alright, then what we get is e to the minus two s. Right? That is from v sub s over s times two plus two s plus two over s.

**[0:09:33]** Right? So this e to the minus two s over s comes from substituting in this expression here for v sub s. Alright? And then this over here in the denominator comes from just dividing by, this term over here. Right?

**[0:09:49]** And so we're gonna take this. We're gonna separate out this factor of either the minus two s, and then we'll write the rest of it as a function f of s. Alright? And that's what we're going to focus on initially. This e to the minus two s will account for this later by using the time shift property of Laplace transforms.

**[0:10:28]** Okay. So we're really gonna focus just on this function f of s. Alright? And then we'll take care of that exponential factor using the time shift property. So f of s here, this is what we want to compute the Laplace trans...

**[0:10:44]** The inverse Laplace transform for its its one over s times two plus two s plus two over s. Or if we multiply through by the s and then factor out a two, we get one over two times it's s squared plus s plus one. Okay. So if we look at this function here, f of s, right, in this particular form, then we can see that it has poles where s squared plus s plus one, is equal to zero. So f of s has poles at s squared plus s plus one is equal to zero.

**[0:11:34]** Okay? And so we can determine the values of s for which that occurs using the quadratic formula. S is equal to one half times minus one plus or minus the square root of one squared minus four. Okay. And so that becomes minus one half.

**[0:11:55]** That's the minus one divided by the two over here plus or minus... Right? The discriminant here under the square root is negative, so we get a factor of j. And then we have the square root of four minus one. That's the square root of three, and then we divide by this two over here.

**[0:12:14]** So j times root three over two. Alright? So one minus one half plus or minus j times root three over two, those are the poles of f of s. And so that means that we can write f of s as one over two times s plus one half minus j root three over two times s plus one half plus j root three over two. Okay.

**[0:12:47]** So now from this form of f of s here, we can do the partial fraction expansion. Okay. So, with the partial fraction expansion, then f of s will be of the form some constant, the residue k one over s plus one half minus j root three over two plus its complex conjugate k one star over s plus one half plus j times root three over two. Okay. The residues are complex conjugates of each other.

**[0:13:29]** I remember because the the poles are complex conjugates of each other. And you can see that the residues have to be complex conjugates of each other pretty easily from just the explicit expressions for the residues. So we only have one residue that we have to calculate, k one. Alright? And then the other one will be its complex conjugate.

**[0:13:52]** So the residue k one, alright, is going to be s plus one half minus j root three over two times f of s evaluated at s equal to minus one half plus j root three over two. Okay. When we multiply f of s by s plus one half minus j root three over two, then we're gonna cancel out this factor in the denominator. And so we will have just one over two times s plus one half plus j root three over two evaluated for this value of s here. Okay.

**[0:14:33]** And so that will give us one over two times s, which we take to be one minus one half plus j root three over two. And then it's plus one half plus j root three over two. Okay. And, if we just calculate this, the minus one half and the one half add up to zero, and we have j root three over two plus j root three over two, which is just j times root three, and then we have this two over here. So we have one over j times two root three.

**[0:15:10]** Alright. That's the residue k one. And so that means that f of s is equal to one over j times two root three times one over s plus one half minus j root three over two. Alright. If we go back up here, that's the first term in the partial fraction expansion.

**[0:15:40]** And then from the second term, we'll just have k one star, which is minus one over j two root three times one over this denominator over here. So we're gonna have minus one over s plus one half plus j root three over two. Okay. So now from here, alright, we just have... We have our two simple poles, right, that are complex conjugates of each other.

**[0:16:09]** In this, partial fraction expansion form, the inverse Laplace transform of f of s can be computed, very easily. Right? So from Ulaby et al, from the table of Laplace transform pairs, which is 12 dash two, then what we have... The result that's relevant here is that either the minus a t u of t forms a Laplace transform pair with one over s plus a. Okay?

**[0:16:43]** Including when a is complex, and that will allow us to essentially write down the inverse Laplace transforms of these two terms here. Okay? So we can go ahead and do that. That means that f of t, the inverse Laplace transform of capital f of s is equal to one over j times two root three times... And then it's e to the minus a t.

**[0:17:10]** So e to the minus one half t plus j root three over two t. Alright? That's from this term minus e to the minus one half t minus j root three over two t. All this times u of t. Okay.

**[0:17:41]** We can simplify this. We see that both of these terms here have an e to the minus one half t in them. So we have e to the minus one half t divided by root three. Right? That's this root three over here.

**[0:17:59]** And then what we have left in the numerator, we just have... From each of these terms, all we have left is the complex exponential phase factor. So we have e to the j root three over two t minus e to the minus j root three over two t. And then in the denominator, we have this j times two. Alright.

**[0:18:24]** That will bring inside the big parentheses times u of t. And this expression here in the big parentheses is just the sine of root three over two t. Alright? So what we have then is this is equal to one over root three times e to the minus one half t times the sine of root three over two t times u of t. Alright.

**[0:18:55]** So that is the Laplace... That's the inverse Laplace transform of f of s. Alright? Now if we go back here, remember, we still had this exponential factor e to the minus two s, that we had to worry about in order to get I sub l. Alright?

**[0:19:16]** And eventually, the current I sub l in the time domain. Alright? So, so to take care of that exponential, factor, what we're going to do is we're going to use the time shift property of Laplace transforms. Okay. Specifically, that in general, if a small f of t and capital f of s form a Laplace transform pair, then f of t minus some constant capital t u of times u of t minus capital t forms Laplace transform pair with e to the minus t times s f of s.

**[0:20:04]** And if we said capital t equal to two, then that will give us what we need in order to get that extra exponential factor of... Account for that extra exponential factor of either the minus two s, that we had in I sub l of s. Alright. So we had that I sub l of s was e to the minus two s times f of s. And so that means that I sub l of t is this function here, small f of t shifted in time by two seconds.

**[0:20:47]** Okay. So at t minus two instead of at t. So we have one over root three times e to the minus one half t minus two times the sine of root three over two t minus two times u of t minus two, and that would be in amps. Right? Or if we calculate, some of these, values numerically, right, then what we get is that I sub l of t is equal to...

**[0:21:29]** So one over root three is point five seven seven four. And then we have either the minus one half t minus two. And then the sine of root three over two is o point eight six six, okay, times t minus two times u of T minus two, again, in amps. Okay. So so that's the answer.

**[0:22:03]** Alright? Now, if you look at this and you go to the back of Ulaby, okay, and, you look at the answer to this problem, then what you'll see is something that is different. So let me see if I can paste from the solutions. Paste that in. Okay.

**[0:22:37]** So this should show up here in a minute. Oops. Okay. We didn't want that. Let me get rid of this.

**[0:22:55]** Yeah. Okay. And let me try pasting that in again. K. I'm not sure why that is not pasting in.

**[0:23:20]** Okay. I'm gonna try this one more time here. Let's see. Okay. So that should copy it.

**[0:23:47]** And let's see. Okay. So that is not, pasting in properly. Oh, there we go. Okay.

**[0:24:05]** Alright. So, let's see. That's what we wanted. So this is the solution from... You'll be at all.

**[0:24:20]** Okay. So, so this is actually what we wanted. And, basically, what you can see here is that it's it's similar to what we just calculated except this numerical factor here is different. Alright? And so...

**[0:24:34]** Alright. Why is that, the case? Which one of these is, correct? Okay. So now, in order to figure out which one of these is correct, then what we can do is to check by using the differential equation.

**[0:25:02]** Approach. Okay. To solve for I sub l of t. Okay. So, this is something that we did back in the beginning of the semester.

**[0:25:18]** So let's, we'll have to remind ourselves perhaps of how to do that. K. So we're gonna redraw the circuit here. Okay. And the resistor, right, we have the equivalent resistance of two ohms, inductance of two Henry's, and capacitance of, point five farads, and then v sub s of t is u of t minus two.

**[0:25:53]** Okay. And so we're gonna solve this by the differential equation approach. Okay. So, to do that, let's go ahead and we're gonna apply again now... But now in the time domain, we're going to apply, KCL around, this circuit loop.

**[0:26:19]** So KCL around circuit loop. Okay. So from the voltage source over here, we have minus v sub s of t, and then from the resistor. Right? So...

**[0:26:36]** Then we have this current I sub l of t. That's what we're trying to solve for. Then we have from the resistor, the voltage is two I sub l. And then from the inductor, remember the voltage across an inductor is l times d I l d t, so plus l d I l d t. And then the voltage across the capacitor is just v sub c.

**[0:26:59]** And these all add up to zero. We also know that I sub l, right, since the inductor and the capacitor are in series, then the current through the inductor is the same as the current through the capacitor. So I sub l, which is also I sub c, is just c times dBc dt. Alright? We can take this expression for I sub l in terms of v sub c, plug it in over here.

**[0:27:29]** Alright? And we'll get a second order differential equation for v sub c. Once we solve for v sub c, we can get I sub l by multiplying by c and taking the derivative. Okay. So that's how we're gonna proceed here.

**[0:27:42]** So if we take c times dB, c dt and plug it in over here for I sub l, then from this term over here, l d I, l dt, we get l c d squared v c d t squared plus... And then from this term here, two I sub l, we get two times c dBc dt. And then, this vc over here, we just carry over. And then that's equal to v sub s of t on the right hand side. Okay?

**[0:28:28]** And now we can substitute in numerical values. L is two Henry's, c is point five farads, d squared v c d t squared plus two times c is point five farads d v c d t plus v c is equal to v sub s of t. Right? And so both these numerical coefficients here turn out to be one. Right?

**[0:28:55]** Nice and simple. So we get d squared v c d t squared plus d v c d t plus v c is equal to v sub s of t. Alright? Which is equal to the the unit step function at t minus two. Okay.

**[0:29:16]** Now we need initial conditions for this circuit and specifically for v sub c and its derivative with respect to time at t equal to zero. Alright? So v sub c of t is equal to zero for... Or actually for a a t equal to two seconds. Right?

**[0:29:42]** At t less than two seconds. Right? So that means since, the voltage across the capacitor has to be continuous, because otherwise, we would have an undefined current, then v sub c at two is equal to zero. Right? We also know that the current through the inductor at two seconds, right, that has to be equal to the current through the inductor at, prior to two seconds.

**[0:30:14]** Alright? Because for an inductor, the current through the inductor has to be continuous. And so we know that's equal to zero. But the current through the inductor is proportional to dBc dt. That means that dBc dt at t equal to two seconds also is equal to zero.

**[0:30:34]** Okay. So this and this, these are the initial conditions that we will have to apply for our differential equation in order to come up with the complete solution. Okay. So now, right, we have this differential equation here to solve. And as usual, what we do is we first solve the homogeneous equation.

**[0:30:57]** Okay? Which is where the right hand side, v sub s of t, is set equal to zero. Okay. So we wanna solve the homogeneous equation, which is the d squared v c d t squared plus d v c d t plus v c is equal to zero. And so to do that, we let v c be equal to some constant a times e to the s t.

**[0:31:32]** Okay? And then we plug that in to the homogeneous equation here. And what we end up getting is an equation for s, s squared plus s plus one is equal to zero. Alright? And so that means s, we can get that, just by solve...

**[0:31:50]** By using the quadratic formula. So it's one half times minus one plus or minus the square root of one squared minus four, or that's four times one. And this is minus one half plus or minus... Alright. The discriminant is negative.

**[0:32:07]** So it's j times... Ends up being root three over two. Okay. So that means that the solution to the homogeneous equation, then is that v sub c of t is equal to, it is... I'll write it as e to the minus one half and then t minus two.

**[0:32:45]** Right? That's from this minus one half and s over here. And then times some constant a one times the cosine of root three over two times t minus two plus a two times the sine of root three over two times t minus two. This is the solution to the homogeneous equation. Right?

**[0:33:21]** For t being greater than or equal to two seconds. Okay. Now you might ask, well, how can we put in two... T minus two here, here, and here instead of t? Right?

**[0:33:33]** What we did when we solve these sorts of problems at the beginning of the semester was we plugged in t, But it's actually perfectly fine to do this time shift and plug in t minus two because all that will do is change the values of these coefficients, which as yet are undetermined. Right? So anything that just changes the values of these coefficients, we can do. And then we just have to make sure that we solve correctly for those coefficients later, you know, or at least we... That we solve consistently for those coefficients later.

**[0:34:09]** Okay. So we're free to do this, time shift over here. Alright? Now we need to come up with the particular integral. Okay.

**[0:34:25]** And for that... Alright. That's for t greater than or equal to two seconds. So the right hand side, we just set equal to one, and we need to come up with some function v sub c of t that solve this equation when the right hand side is equal to one. And, if you remember, right, the solution in that case, where the right hand side is equal to a constant is just that v sub c is equal to that constant, in this case, equal to one.

**[0:34:52]** So the particular integral here is that v sub c is equal to one for t greater than or equal to two. Okay. So then to get the full solution, we just add the particular integral to the solution to the homogeneous equation. Right? So the full solution is therefore that v sub c of t is equal to e to the minus one half t minus two times a one times the cosine of root three over two times t minus two.

**[0:35:40]** Put square brackets here so it's clear. Plus a two times the sine of root three over two times t minus two. K. All of this plus one. That's the solution for t greater than or equal to two seconds.

**[0:35:57]** Alright? Now we need to solve for a one and a two. So we use the initial conditions that we derived earlier. That v sub c at t equal to two is equal to zero and dBCDT at t equal to two is also equal to zero. Okay.

**[0:36:17]** So from the initial condition that v sub c at two is equal to zero, then, what happens here is that, this cosine term, here, the cosine of zero is one. The sine of zero is zero. So... And then this exponential is just one since the exponent is zero. So we just have that a one plus one.

**[0:36:46]** That one is this one out here is equal to zero, which means that a one is equal to minus one. Alright. Our second initial condition is that dB, c, dt evaluated at t equal to two is equal to zero. Okay. And so for that, right, we need to take the derivative of this here with respect to t.

**[0:37:14]** Alright? And so we'll give ourselves some room here to take that derivative. Right. Basically, we have a, this one over here at the end, we won't have to worry about because when we take the derivative of that, it'll be zero. Okay?

**[0:37:31]** So, really, we have this product of this exponential function and this thing in the square brackets. Alright? So, we'll just apply the product rule for taking a derivative. So the derivative of this whole thing is gonna be the derivative of the first factor, which is minus one half, e to the minus one half times t minus two times the second factor, a one times the cosine of root three over two times t minus two plus a two times the sine of root three over two times t minus two. Alright.

**[0:38:18]** What's the brackets here? Plus, the first factor, e to the minus one half t minus two times the derivative of the second factor, which is this whole thing in the square brackets. Alright? So when we take the derivatives of, the cosine and the sine here, we'll get a factor of root three over two. And then we'll get minus a one times the sine of root three over two t minus two.

**[0:38:54]** Right? Because the derivative of the cosine is minus the sine plus a two times the cosine of root three over two times t minus two. Alright? Because the derivative of the sine is just the cosine. Alright?

**[0:39:12]** Close the square brackets here. And then, right, we want to evaluate this at t equal to two, and this whole thing has to be equal to zero. Okay. So now, when we evaluate this at t equal to two, then, all the arguments of the trigonometric functions are going to be zero. So this...

**[0:39:44]** The sine goes to zero, this sine goes to zero, this cosine goes to one, this cosine goes to one, and this exponent... Exponential. These exponentials go to one. Okay. So what we get then is from this part over here, we just get minus one half times a one.

**[0:40:11]** Okay. And then from this second term over here, we get plus root three over two times a two. So plus root three over two times a two, that's equal to zero. Alright. That means that a two is going to be equal to one over root three times a one.

**[0:40:41]** A one, we saw up here is minus one. So this is just minus one over root three. Alright. And that's what a two is. Okay.

**[0:40:52]** So these two results here are our coefficients. Okay? And then now, finally, we can solve for I sub l of t. Alright. We know that this is c times dBc dt.

**[0:41:12]** Alright. C, the capacitance is one half a farad. So this is one half times dBc dt. So we just have to calculate that. Alright?

**[0:41:25]** And, we actually calculated the derivative of v sub c of t... V sub c with respect to t up here. Alright? So we can use that result plugging in, the values that we figured out for a one and a two. Alright?

**[0:41:42]** So if we go ahead and do that, then we're gonna have a one half in front. That's this one half over here. Okay. And then we're going to have, just following along here, a minus one half e to the, minus one half t minus two. And then a one is minus one, so we have minus the cosine of root three over two times t minus two.

**[0:42:24]** And then a two is minus one over root three. So minus one over root three times the sine of root three over two times t minus two. Right? And then we have plus... Now we're moving on to this second term over here plus e to the minus one half times t minus two times root three over two.

**[0:42:59]** And then we have minus a one. So that's just one times the sine of root three over two times t minus two. And then plus a two, that's minus one over root three times the cosine of root three over two times t minus two. Okay. All of this times the one half.

**[0:43:27]** Alright? And so now, alright, we can go ahead and turns out that there are some simplifications that we can, come up with here by pulling out. We have this factor of one half over here overall on the outside. Then we have, in both of these terms, e to the minus one half t minus two. So we have either the minus one half t minus two.

**[0:44:01]** Okay. And then for the rest of this, we can group together first the terms that are proportional to the cosine. So from over here, from this cosine, we have minus one half times minus one. So that's one half. Right?

**[0:44:17]** That got us this term. And then from this cosine over here, we have plus root three over two times minus one over root three. That's minus one half. Alright. That got us this term over here times the cosine of root three over two times t minus two.

**[0:44:39]** Okay. So that's gonna go to zero. Alright. We can see. And then for the sine terms, alright, we have...

**[0:44:49]** From this first sign over here, we have minus one half times minus one over root three. So that is, one over two root three. Right. That got us this term. And then finally, from over here, we have plus root three over two.

**[0:45:12]** That's this term, and that's times the sine of root three over two times t minus two. Alright? And so now, alright, we can see... Alright. This goes to zero.

**[0:45:31]** Okay. And so that first term goes away entirely. And so what we have left is either the minus one half times t minus two, then one half. That's this one half over here. And then for this term here in the parentheses, we can put both of these terms on top of a common denominator, which is two root three.

**[0:46:00]** So we're gonna have one plus three over two root three, alright, times the sine of root three over two times t minus two. Okay. And now, alright, we can see this one plus three, that's four. And then we have two times two or four in the denominator. So those are going to cancel out.

**[0:46:29]** This one plus three cancels out with this two times two. And so what we have left is one over root three times e to the minus one half t minus two times the sine of root three over two times t minus two. Alright? And remember, this was valid only for t greater than equal to two. So in fact, this is times the unit step function u of t minus two.

**[0:47:00]** Okay. And so this, right, this is I sub l of t. Alright. This is our solution. And...

**[0:47:12]** Or you can see it has this one over root three out in front. And if you go back to what we did earlier... Okay. That's actually the same result as we got over here. Alright?

**[0:47:30]** So in fact, the solution that we worked out is correct. The solution in Ulaby, at all, turns out to be incorrect. It's a factor of two, too large. Okay. Okay.

**[0:47:45]** So, so that's the result. And now we've seen this particular circuit, analyzed in two different ways. We've seen it, analyzed using the Laplace transform approach, and we've seen it analyzed using the, differential equation approach. Right? You can decide in this case which you thought was easier.

**[0:48:06]** Alright? But now just looking back on this, what are some of the key points here? The first one is that, at least with respect to the, Laplace transform approach, right, once again, the major steps here that we went through are, first of all, to determine the initial conditions. Okay. Because that influences the, how we transform to the s domain.

**[0:48:44]** Because if we have nonzero initial conditions for current through an inductor, voltage across the capacitor, then we have to introduce additional source components in the circuit. Right? So we wanted to determine the initial conditions I sub l at zero minus and v sub c at zero minus. Alright? Then once we have those, we transform the circuit to the s domain.

**[0:49:18]** Then once we have the circuit in the s domain, we can analyze it in the s domain. And then once we have the solution in the s domain, then we do the inverse transform back to the time domain. Okay. Second point to note here is that... Remember, when we did the Laplace transform analysis, one of the things that we did was we pulled out that exponential factor, either the minus two s from, the solution in the s domain, and we dealt with that separately in trans...

**[0:50:09]** In performing the inverse Laplace transform. Okay. So we dealt with that at the end using this high shift property of Laplace transforms. And that kind of, separation can often be helpful. Right?

**[0:50:23]** So it's often helpful to notice and to use properties of Laplace transforms. And the particular example of this that we saw here was that we used the time shift property of Laplace transforms to handle the factor of either the minus two s in I sub l of s. Right? The estimated solution for the current. Okay.

**[0:51:11]** We saw, as usual, that doing this partial fraction expansion. Alright. That's a very useful tool in allowing the s domain solution to be written in a form that can easily be transformed back to the time domain. Alright. So it allows the estimate solution to be written in a form that is easily transformed back to the time domain.

**[0:52:05]** Okay. When we got the result, we saw that it was different from the result that is printed in Ulaby. Alright? And, by doing the differential equation analysis, we saw that, in fact, the solution that we had worked out by Laplace transforms was, correct, and the solution printed in Ulaby was incorrect. It was off by a factor of two.

**[0:52:34]** Alright? So, one of the lessons here is that the official solutions in the text or perhaps elsewhere are not necessarily correct. Alright. Something that came along with this was that it's useful to know multiple methods, right, to, analyze, and think about circuits because sometimes you can use one as a check for another. Right?

**[0:53:17]** So multiple methods for circuit analysis can be used as checks for each other. Okay. And then, the last point here is, as we've seen, repeatedly, if you've looked at, many of these examples, we can see that accuracy and proficiency in complex algebra. These are important. Okay.

**[0:54:11]** If you want to get the correct result. Okay. So that is everything for, this example. Alright? And I will now I will now stop this recording.
