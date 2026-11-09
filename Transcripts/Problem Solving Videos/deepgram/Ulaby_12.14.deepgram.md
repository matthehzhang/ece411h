# Ulaby 12.14 video

Deepgram general-nova-3 2025-07-31.0, request 01a1b039-a5cd-7f13-8cff-60c9163eb440, audio 32.9 min.

**[0:00:03]** Okay. So this is, Ulaby problem 12.14, and this is an example of a circuit analysis using Laplace transforms. Okay. So the problem, that we are solving here is, to look at this particular circuit here, Alright? And to figure out the current that flows around this loop in the situation where the voltage source has this particular form here.

**[0:00:48]** So it's zero up to time equal to zero, and then it increases linear linearly, with time four times greater than or equal to zero. Alright? And here, if the Laplace transform is a useful technique to employ because if we didn't use Laplace transforms. Right? Right.

**[0:01:09]** We can't use phasors because this is not periodic. If we didn't use Laplace transforms and we try to solve a differential equation, associated with this directly, then we would be stuck with having to figure out the particular integral, right, that solves the differential equation for a linear function as the inhomogeneous term. Right? And that's something that, we haven't discussed, so we don't know, if that's going to be straightforward, or not. But we do know how to solve this kind of problem using Laplace transforms.

**[0:01:47]** Okay. So let's go ahead with this. We will, as usual, redraw our circuit. So we have a voltage source with a resistor, an inductor, and a capacitor like this. Okay.

**[0:02:05]** So this voltage source is v sub s of t. Resistor is r, inductor is l, capacitor is c, and we want to solve for the currents I of t, where r, the resistance is two ohms, l, the inductance is six Henry's, and c the capacitance is two farads. Right? These are not necessarily, realistic circuit numbers that you would find in an actual circuit, but they allow us to see the analysis technique and work out, the numbers relatively easily. Okay.

**[0:02:43]** And the voltage source here, b sub s of t, as a function of time... Right. This is zero, one second, two seconds, three seconds, one volt. So this is in volts. Two volts.

**[0:03:00]** It basically looks... I'll draw this in blue here. Alright. It is zero up until time equal to zero, and then it increases linearly. Okay.

**[0:03:17]** So v sub s of t here is just t times u of t, and that's in volts. Alright? And what we're asked to do here is to solve for I of t. Alright? So that's the problem, that we are given here.

**[0:03:39]** Alright? And so the first thing that we want to do is to determine the initial conditions, right, for the current through the inductor and the voltage across the capacitor at time zero minus. Okay? And we need to do that because, when we eventually transform the circuit to the s domain, then if these values are non zero, then we will have to introduce an additional component I... Into the circuit.

**[0:04:22]** Alright? So if we look at the circuit four times less than zero, then I... Or we know the v sub s of t is equal to zero, and it's zero, for a long time before t equal to zero. And so the current through the inductor should be zero, and the voltage across the capacitor should be zero as well. Okay?

**[0:04:54]** So since these are both zero, we will not have to introduce, additional source components into the circuit when we transform it to the s domain. Okay. So then the second step then is to transform, the circuit to the s domain for t greater than or equal to zero. Okay? And so we're going to have our voltage source, resistor, inductor, and capacitor.

**[0:05:36]** Okay. The voltage source will be some function of s now. The resistor will be represented by impedance, which is just r. The inductor has an impedance, which is s times the inductance l. And the capacitor has an impedance, which is one over s times the capacitance c.

**[0:05:59]** And the current will be some function in the s domain also. Alright? So, the first thing that we wanna do here... After drawing this, circuit in the s domain, we wanna figure out what v sub s of s is. Alright.

**[0:06:14]** We know v sub s of t is t times the unit step function. And, we know that t times unit step function forms a Laplace transform pair with the function one over s squared. Right? And that's from Ulaby et al in this table 12 dash two, which is the table of, common Laplace transform pairs. Alright?

**[0:06:47]** So, once we have all of that, then what we wanna do is just to analyze the circuit in the s domain. And then, in doing so, we wanna solve initially for I sub... I of s, which is in the s domain. And then we have to perform the inverse Laplace transform to go back to the time domain, which is the solution that ultimately, we want. Okay.

**[0:07:19]** So, if we just look at this circuit in the s domain, right, then the analysis is very straightforward. We just apply KVL. We enforce KVL going around the circuit loop over here. And I... And the resulting equation, we just solve that for the current I of s.

**[0:07:39]** Okay. So we wanna apply KVL around the circuit loop. Right? And so that's going to give us... Alright.

**[0:07:52]** The voltage source is going to give us minus v sub s. Then the resistor is going to be r, a voltage r times I of s. The inductor is going to be the inductor impedance z sub l times I of s. And then for the capacitor, it's the capacitor impedance z sub c times I of s. And all those have to add up to zero by k v l.

**[0:08:20]** Right? And so now we can go ahead and substitute in numerical values for our circuit components. And so the resistor is two ohms, remember. The inductance is six Henry's, so the impedance is six s. And then the capacitance is two farads.

**[0:08:43]** So the impedance is one over two s. All of this multiplies I of s. Okay? And that's equal to v sub s. It becomes positive when we move it to the right hand side.

**[0:08:57]** And, v sub s, we saw up here is just one over s squared. Okay. Or we can solve this for I of s, and we get that this is equal to one over s squared times two plus six s plus one over two s. Alright? Oops.

**[0:09:32]** Okay. And if we take this and put it in, the standard form, right, that makes it, a little bit easier to compute the Laplace transform then... Or the the partial fraction expansion, eventually, inverse Laplace transform. What we're gonna do is we're gonna take one factor of s over here and multiply it through these three terms so that we get a quadratic expression for s in here. And we're going to factor out a six, a factor of six from this and pull it to the outside in the denominator.

**[0:10:04]** So we get one over, then we have six s, and then we have s squared. Right? That's from the six s times, s with a factor of six pulled out, plus one third s, that's from two times s, which we multiply through here. With a factor of six pulled out, that becomes one third. And then plus one twelfth, that's one over two s.

**[0:10:35]** When we multiply through by s, that becomes one half. We pull out a factor of six, that becomes one twelfth. Alright. So this is I of s. Alright?

**[0:10:45]** So now this is the function for which we want to compute the inverse Laplace transform to get I of t. And to do that, we want to determine, the values of s at which this has poles. Alright? So I of s has poles at s equal to zero and s squared plus one third s plus one twelfth equal to zero. Alright?

**[0:11:15]** And so for this quadratic over here, to find its roots, we just use the quadratic formula. So s is equal to one half times minus one third plus or minus the square root of one third squared, which is one ninth minus four times one twelfth. Okay. And, so this becomes minus one third times one half. So it's minus one sixth plus or minus.

**[0:11:46]** Alright? This quantity under the square root is negative. Right? So we have a factor of j, and then we'll have our factor of one half from the outside. We bring that in, and then we have one ninth minus four twelfth is one third.

**[0:12:02]** Right? So, when we pull the factor of j out, that becomes one third minus one ninth. That's three ninth minus one ninth. That's two ninth. So we have the square root of two over nine.

**[0:12:15]** Okay. And so this becomes minus one six plus or minus j times the square root of two in the numerator, and then the square root of nine is three. So we have two times three or six in the denominator. Alright? So that means that I of s is equal to one over six s times s plus one sixth minus j times root two over six times s plus one six plus j root two over six.

**[0:12:55]** Okay. So now this is the function for which we want to compute the inverse Laplace transform. And so to do that, we go through the usual procedure of performing the... Writing out the partial fraction expansion, figuring out the residues or or the coefficients in that expansion, and then doing the inverse Laplace transform. So now we wanna do the partial fraction expansion of I of s.

**[0:13:30]** Right? And that is that I of s is equal to... So one gonna be a coefficient k one over s plus coefficient l one over s plus one six minus j root two over six plus l one star. Right, is complex conjugate over s plus one six plus j root two over six. And the residues are complex conjugates to each other because the roots, the poles are complex conjugates of each other.

**[0:14:02]** Okay. And then, to compute the residues, that is these coefficients, right, we do the usual thing. K one is going to be equal to s times I of s evaluated at s equal to zero. Okay. So when we, take I of s and multiply by s, right, if we go to this form up here, then that cancels out this s in the denominator, and then we just have these other terms here evaluated at s equal to zero.

**[0:14:35]** So we're gonna have one over six times zero squared plus one third times zero plus one twelfth. So that is six times one twelve, and the denominator, that's one half, and the denominator, that's two. Alright? For k one. Then we wanna compute l one.

**[0:14:56]** That's going to be following the same procedure. S plus one six minus j root two over six times I of s evaluated at s equal to minus one six plus j root two over six. Okay. And so here, alright, if we look at this expression here for I of s, then multiplying by s plus one six minus j root two over six is gonna cancel out this term in the denominator, and then we'll just have these other terms left here evaluated at s equal to minus one six plus j root two over six. So that's gonna give us one over six times s, which is minus one six plus j root two over six times s minus one six plus j root two over six plus one six plus j root two over six.

**[0:16:02]** Alright? And we worked all this out, then we have, six times this first factor in parentheses here. So we have, six times minus one six, that's minus one, plus... And then j times root two over six times six. So j times root two.

**[0:16:27]** No. Okay. And then over here, we have minus one six plus one six, that's zero. And then we have j times root two over six plus j times root two over six. That becomes j times root two over three.

**[0:16:42]** Okay. And if we multiply out these terms in the denominator, we get one over, and then we have j root two times j root two over three. That becomes, minus two thirds. And then we have j root two over three times minus one. That's minus j root two over three.

**[0:17:09]** Alright? So now here, we're going to multiply the numerator and the denominator by the complex conjugate of the denominator. So minus two thirds plus j root two over three over minus two thirds plus j root two over three. That'll give us the magnitude squared of the denominator in the denominator and then this in the numerator. So we get minus two thirds plus j root two over three over...

**[0:17:41]** Then it's two thirds squared plus root two over three squared. Okay. In the denominator, we have... This is four ninths. Right?

**[0:17:53]** Two thirds of quantity squared plus two ninths. That's six ninths in the denominator or two thirds in the denominator. That becomes three halves in the numerator times minus two thirds plus j root two over three. Okay. And then we multiply this through, we get minus one plus j times root two over two.

**[0:18:18]** Alright? And, if we take that, now what we wanted... So we've gotten l one now into rectangular form, but it turns out here, it's actually useful to put it into polar form now. Alright? Because that'll allow us to get a phase shift angle out of it more easily.

**[0:18:39]** So if we figure out the magnitude of this, that's the square root of one plus, root two over two, the quantity squared. Alright? And so that ends up being 1.225. And then that's times e to the j times some phase angle phi where phi is equal to a 180 degrees minus the inverse tangent of root two over two or equivalently one over root two over one. Okay?

**[0:19:13]** And that turns out to be 144.7 degrees. And so l one ends up being equal to 1.225 times e to the j times a 144.7 degrees. Okay. So here, you might ask, well, why didn't we just take root two over two divided by minus one and compute the, inverse tangent of that? Okay.

**[0:19:42]** And the reason, right, is that, right, if we sort of draw out... Right. This is l one. Alright? And we draw out, minus one plus j times root two over two, then that's going to be this minus one.

**[0:20:04]** And say this is root two over two. Right? We know that that point is actually out here. Alright? And so the angle that we want is this.

**[0:20:21]** Right? But, so we know that it has to be in the second quadrant. Alright? Because just looking at this form here, we know that had... That...

**[0:20:30]** That's in the second quadrant. But if we were to take just the inverse tangent of root two over two over minus one, then that would actually give us... Put this in red. This angle here. So this angle here is what you would actually get if you computed the inverse tangent of minus one over root two, which is minus the inverse tangent of one over root two.

**[0:21:04]** Right? So if you stuck that into your calculator and calculated, you would get this angle here because it's gonna give you an angle that is between minus 90 degrees and 90 degrees. And so we have to take that and shift it by a 180 degrees, which is this 180 degrees here in order to get what is actually the correct angle. Alright. So that is why we calculated the phase angle in this way.

**[0:21:32]** Alright? So that's something that, as hopefully you know, it's from our discussion of phasers, is important to, be mindful of and, to do correctly. Okay. So now that we have k one and l one, then we know that I sub s or I of s, right, is is k one over s. So that's two over s and then plus l one over s plus one six minus j root two over six, plus l one star over s plus one six plus j root two over six.

**[0:22:10]** And l one is given by this expression here. And when we use... When we compute its complex conjugate, we just put a minus sign in front of the j here. Alright? So I of s is going to be two over s plus 1.225 e to the j one forty four point seven degrees divided by s plus one six minus j root two over six plus 1.225 e to the minus j one forty four point seven degrees.

**[0:22:47]** Alright. That's the complex conjugate of this residue over here over s plus one six, plus j root two over six. Okay. So that is the current I in the s domain. And what we need to do now is compute the inverse Laplace transform.

**[0:23:13]** Okay? And, for that, right, we have... Right? We just have, some of simple poles here. So we know that the inverse Laplace transform is just going to be a sum of exponentials.

**[0:23:27]** In this case, with the pole at zero, it is an exponential with zero in the exponent or just one. Right? So from Ulaby et al, and it's table 12 dash two, which is the table of common Laplace transform pairs, then we have that u of t forms Laplace transform pair with one over s. Right? That'll give us the first term, and either the minus a t u of t forms a Laplace transform pair with one over s plus a.

**[0:24:05]** We could also use that to get the first term here with a equal to zero, and we use this to get the second and the third terms. Okay. So then, using, these results to, calculate the inverse Laplace transform, we get from the first term in I of s, we get two times u of t. Every factor will... Every term will have a factor of u of t, so we'll write that at the end.

**[0:24:36]** And then plus 1.225. Right? That factor is common to both of these. Alright? And then from this first term over here, we have e to the minus a t.

**[0:24:53]** So that's e to the minus t over six, times e to the plus j root two over six times t times e to the j one forty four point seven degrees. And then from this second term or or this last term over here, we get plus e to the minus t over six times e to the minus j root two over six t times e to the minus one forty four point seven degrees. All of this times u of t. Okay. And then we can take this.

**[0:25:40]** Alright? And write it as two plus 1.225. Alright? And then, both of these terms here have a factor of either the minus t over six. So we can pull that out in front.

**[0:25:59]** And then, the other factors in these two terms, you can see pretty easily, are equal to two times the cosine of root two over six t plus a 144.7 degrees times u of t. Alright? And if we just simplify this a little bit more, multiplying two by 1.225 and then, putting in a decimal value for root two over six, alright, then what we finally get is I of t is equal to two plus 2.45 e to the minus t over six times the cosine of, o point two three five seven t plus a 144.7 degrees. Alright. Times u of c, and that's in amps.

**[0:27:05]** And this is the answer. Right? As I had noted, or perhaps will note in class, you have to be a little bit careful here because this term here is an angle in radians. Alright? Because the angular frequency is typically given in radians per second.

**[0:27:26]** This is in degrees. So we've written, an angle. We've added things in different units, which, ordinarily is a no no. Okay? But, that is typically how these are written here.

**[0:27:40]** So we just have to be cognizant that, in fact, this is in radians and this is in degrees. Okay. So, what are some of the key points, okay, that we can extract from this particular example? So first, alright, we saw kind of what the general procedure is for doing circuit analysis using Laplace transform. Right?

**[0:28:12]** The major steps here are that first, we determine the initial conditions for the current through the inductor and the voltage across the capacitor. Right? One has to do this for all the inductors and capacitors in circuit. In this case, there were only one of each. Then once we have those, we transform the circuit to the s domain.

**[0:28:52]** Okay. If, some of these initial conditions were non zero, we would have to introduce additional source components, into the s domain circuit. But in this particular case, they were both zero, so we didn't have to do that. And then, we do the analysis of the circuit in the s domain, alright, which is, the same as just doing conventional circuit analysis except that you have impedances that can be functions of s. And then once you've done that, then you wanna perform, and you've gotten the result that you want.

**[0:29:36]** In our case, that was I of s, in the s domain, then you want to perform the inverse transform back to the time domain. Okay. Second point that we can note, which we also saw in the examples of just how to compute inverse Laplace transforms more generically, is that the partial fraction expansion, right, that we use. This allows the s domain solution that we obtained to be written in a form that is easily transformed back to the time domain. Okay.

**[0:30:49]** A third point that can be noted here is that one of the things that we did here was that when we computed the residues, that is the coefficients and the partial fraction expansion, we expressed the residues for the complex roots in polar form. Alright? And that was useful because it allowed us to get the phase shift angles or what turned out to be the phase shift angles, quite directly, once we did the inverse Laplace transform. So we wanna keep this in mind that it can be useful to express the residues. Right?

**[0:31:34]** That is the coefficients for complex poles in polar form. Right? At least at the end. You don't have to work with it in polar form throughout. But at the end, it can be useful to express them in polar form.

**[0:31:58]** And the reason for this is that the phase shift angles appear this way more naturally. Okay. And then the last point, which, you may have noticed, as, we work through, this example and perhaps others is that accuracy and proficiency in complex algebra are important. Okay. So that is it for, this example here.

**[0:32:49]** Alright? And I will stop stop the recording now.
