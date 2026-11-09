# Ulaby 12.37 video

Deepgram general-nova-3 2025-07-31.0, request 01a1b039-fce9-7321-930d-f916f0fd6adc, audio 40.6 min.

**[0:00:04]** Okay. So this is Ulaby problem 12.37, and this is an example of circuit analysis using Laplace transforms. Okay. But in this case, it turns out that we will have non zero initial conditions that will require us to introduce an additional source component in the circuit when we transform to the s domain. And that comes about because we have basically non zero current from this current source here for t less than zero.

**[0:00:49]** Okay. So this is circuit analysis using Laplace transforms with, we'll call them non zero initial conditions. Okay. So, let's go ahead and get started. We will, as usual, redraw the circuit.

**[0:01:14]** So we have a current source and then a resistor. Its current source is I sub s of t. The resistor here is r one. We have a capacitor, Then we have another resistor r two. This capacitor...

**[0:01:33]** It's capacitance c. And then we have an inductor all the way over on the right. Okay. So the inductance is l, and the current here, that we wanna solve for is the current through the inductor I sub l of t. Okay?

**[0:01:55]** And the component values here are that r one is equal to 10 ohms, r two is equal to five ohms, l, the inductance, is point six one nine six Henry's. And then l c is one fifteenth of a second, alright, from which we can deduce what c is as well. And this current source, k, I sub s of t is six amps. Okay. And the current source, we'll draw this in blue, okay, is six amps up until t equal to zero and then decreases exponentially six e to the minus two t.

**[0:02:54]** Okay. And so this is t equal to zero. Okay. And so, I sub s of t analytically is six amps for t less than or equal to zero, and it's six e to the minus two t amps for t greater than or equal to zero. And what we want to do here is to solve for I sub l of t for t greater than or equal to zero.

**[0:03:28]** Okay. And we're gonna do this using Laplace transforms. And so the first step here is to determine the initial conditions for t equal to zero minus. Alright? So just before t is equal to zero, specifically for the current through the inductor and the voltage across the capacitor.

**[0:03:57]** Alright? So as usual, we take the capacitor to behave as an open circuit and the inductor to behave as a short circuit. And the current source for t less than zero is six amps. Alright? So we'll redraw the circuit.

**[0:04:25]** In this configuration, the t equal to zero minus configuration. Okay. So this is the resistor r one. The current source is just six amps. And then the capacitor is an open circuit, and the voltage across it is v c.

**[0:04:51]** And then this resistor is r two, and then the inductor is a short circuit. Okay. And we have a current I sub l for the inductor. Okay. We can see that for the inductor, alright, the current has to be zero for t equal to zero minus.

**[0:05:21]** Alright? Because the voltage, right, this is just a... This is an open circuit over here. There's no current along this branch. The voltage across r two has to be zero because it's short circuited over here.

**[0:05:38]** So there's no current through r two. And so by KCL of this node up here, I sub l has to be zero as well. The voltage across the capacitor at t equal to zero minus, right, that is the voltage across the resistor r one. Alright? Because this terminal here is at one terminal of r one.

**[0:06:03]** This terminal over here through this connection is at the opposite terminal of r one. So the voltage across the capacitor is the same as the voltage across r one, in this situation. And that voltage is just the current six amps times the resistance r one. Right? Because no current is gonna flow this way, so the entire six amps has to flow, through the resistor r one.

**[0:06:28]** So v c at zero minus is six amps times r one. R one is 10 ohms, so this is 60 volts. Okay. So now we have a non zero value for v c at zero minus. And so that will mean that, when we transform the circuit to the s domain, then we will need to include a a voltage source to account for that current.

**[0:07:01]** Okay. So now we wanna transform the circuit to the s domain for t greater than or equal to zero. Okay. So let's draw what this will look like. Okay.

**[0:07:22]** We have our current source. Now that's I sub s as a function of s. Okay. And then we have our resistor r one. And then we have our capacitor.

**[0:07:39]** But then in series with the capacitor, we have a voltage source to account for the non zero value of v c at zero minus. K. Then we have our resistor r two. And then we have our inductor l. Alright?

**[0:08:05]** And so the capacitor has impedance in the s domain one over s c. The voltage source has a value v c at zero minus over s, which is 60 over s. Okay. And then the inductor has impedance s times l, and then we're trying to solve for this current I sub l of s. Okay?

**[0:08:38]** And the current source in the s domain is as follows. In the time domain, I sub s of t for t greater than zero is six times e to the minus two t times u of t. And that forms a, Laplace transform pair with I sub s of s. Right? This is a standard form, so it's six over s plus two.

**[0:09:08]** And we get that from Ulaby et al, and it's table 12 dash two of common Laplace transform pairs. Right? So this is now the circuit in the s domain. And so what we want to do next is to analyze this circuit in the s domain and solve for I sub l of s. And then once we have that, then we will want to, compute the inverse Laplace transform to get I sub l of t, right, which is what we're actually trying to solve for.

**[0:09:44]** So the next step here is to analyze the circuit in the s domain and solve for initially I sub l of s in the s domain, and then compute the inverse Laplace transform to get I sub l of t back in the time domain. Okay. So, to analyze this circuit, then what we'll do is we'll do a node voltage analysis. So we'll take this bottom node to be our reference node with zero voltage, and then we will have two voltages, v one and v two, add the two extraordinary nodes that we have here. Okay.

**[0:10:32]** And so as usual, we're just going to apply KCL at each of these nodes. So KCL at node v one, the one on the left, right, we take the sum of the outgoing currents to be zero. So the current going out to the left is minus I sub s because it's plus I sub s coming in. The current flowing down through r one is v one over r one. And then the current flowing to the right is the voltage across the capacitor here, which is v one minus v two plus 60 over s.

**[0:11:17]** Right? So it's v one minus the quantity v two plus 60 over s divided by the impedance of the capacitor, which is one over s c. And those three currents have to add up to zero. Okay? And so if we group together our, unknown variables, then for I one...

**[0:11:40]** For v one, we have this term here, one over r one. Then we have this term over here, v one over one over s c. So that's v one times s c. Right? So we have s c times v one.

**[0:11:58]** And then for v two, we have minus v two over one over s c, which is minus s c times v two. And that's equal to I sub s. Right? That's taking this I sub s and moving it to the right, so we change the sign. And then we have minus 60 over s over one over s c on the left, that becomes plus 60 c.

**[0:12:24]** Oops. That is a bigger c here. Plus 60 c on, the right. Okay. And so this is the first equation that we have for our unknown node voltages v one and v two.

**[0:12:47]** Okay. Now we can do apply KCL at the node v two. Okay. And, when we do that, right, we're at node v two, and we're taking the sum of the outgoing currents to be zero. So the current flowing out to the left is going to be the voltage going in the left direction across the capacitor.

**[0:13:09]** So it is v two plus 60 over s minus v one divided by the impedance of the capacitor, so divided by one over s c. Then we'll have the voltage go... The current going down. That's v two over r two. Then the current going to the right, which is v two over s l.

**[0:13:27]** We wanna add those together and they should add up to zero by KCL. So we're gonna have v two plus 60 over s. Alright. That's the voltage at the right hand terminal of the capacitor minus v one divided by one over s c plus v two over r two plus v two over s l. Those have to add up to zero.

**[0:13:57]** And if we again, as usual, group together our unknown, variables, then for v one, we only have this term over here. So that's going to be minus s c times v one. Then for v two, we have one over r two from here. Then we have, v two over one over s c. So that is s c times v two.

**[0:14:32]** And then we have one over s l times v two from over here. So plus one over s l times v two. And then on the right hand side, we have just this term 60 over s divided by one over s c on the left. That becomes minus 60 c on the right. So this is our second, equation.

**[0:14:58]** Alright? So now we have two equations for our two unknown node voltages, v one and v two. Right? If we look at our circuit up here, then, we actually only need to solve for the voltage v two. And then the current, I sub l of this is going to be v two over s l.

**[0:15:19]** Alright? And so what we wanna do then is to solve these two equations that I have underlined in green. We wanna solve these for v two. We'll do this using parameter's rule. Okay.

**[0:15:41]** And then once we have v two, then I sub l of s is going to be v two over s l. Okay. So, let's write down, the two equations that we had, here. So we have one over r one plus s c. Draw that c a little bit better.

**[0:16:06]** Times v one minus s times c times v two is equal to I sub s plus 60 c. Alright? And then we have minus s times c times v one plus one over r two plus s c plus one over s l times v two is equal to minus 60 c. Okay? And so these are the two equations that we wanna solve, using Cramer's rule.

**[0:16:47]** So Cramer's rule says that v two is going to be determined... The determinant of the matrix of coefficients where the coefficients of v two are replaced by the column vector of constants divided by the determinant of the matrix of coefficients. Okay. So we have the determinant of one over r one plus s c minus s c, and then I sub s plus 60 c and minus 60 c divided by... And in the denominator, we have one over r one plus s c minus s c.

**[0:17:29]** Then we have, minus s c and then one over r two plus s c plus one over s l. Okay. So we wanna compute these, determinants here. And, for a two by two matrix, right, the determinant is just the product of the diagonal terms minus, of the main diagonal terms minus the product of the opposite diagonal terms. And so we have, from the main diagonal minus one over r one plus s c times 60 c.

**[0:18:06]** And then from the op... Minus the opposite diagonal, we get plus, I sub s plus 60 c times s c. And in the denominator, from the main diagonal, we have one over r one plus s c times one over r two plus s c plus one over s l, and then minus s squared c squared. Okay. So now, we want to work this out and simplify it a bit.

**[0:18:43]** So, in the numerator here, we're going to have... The the first term is minus, one over r one times 60 c. So we have minus one over r one times 60 c. And then here we have minus s c times 60 c, but that's gonna cancel out with this plus s c times 60 c. So then the only other term that we have is s s times I s times c.

**[0:19:12]** Alright. So plus s times I s times c. Okay. And then in the denominator, we have, one over r one times r two. Okay.

**[0:19:27]** Then we have one over r one times sc. But then we also have another term that we're gonna get one over r two times sc. So it's actually one over r one plus one over r two times SC. And then we have, one over r one times one over SL. So we have plus one over l r one.

**[0:20:00]** Okay. And then, we've already taken care of this s c times, one over r two. We have s c times s c, but that's gonna cancel out with this minus s squared c squared over here. And then the last term that we have is s c, times one over s l, which is plus c over l. Okay.

**[0:20:24]** So now here, we're going to proceed by multiplying this by l times r one times r two over l times r one times r two. Right? So that'll allow us to, get rid of some of these fractions that we have in the numerator and denominator. And so in the numerator, from the first term, we're going to have minus 60 l times r two times c, and then plus s times I s times r one r two times l c. And then in the denominator, right, l times r one times r two times one over r one r two is just l.

**[0:21:17]** And then, from this second term, in the parentheses, we're gonna get r one plus r two and that's times s times l times c. So we're gonna have s times r one plus r two times l times c. And then from this term over here, we're going to get, r two over s. And then from the last term over here, we're gonna get r one times r two times c. Okay.

**[0:21:53]** So that's v two. Then I sub l of s is going to be v two over s times l. Right? So we take this expression here and we divide it by s times l. Alright?

**[0:22:13]** When we divide by l, we're gonna get rid of this l in the numerator, and then this s over here will multiply that through in the denominator. Okay. So if we do those things, we get in the numerator minus 60 r two times c plus s times I s times r one times r two times c. And then in the denominator, we're gonna have, from this term here, we're gonna have r one plus r two times l c times s squared. Right?

**[0:22:58]** Because we're multiplying through by s. And then we're gonna have from the constant terms, r one r two c plus l times s. And then from the r two over s, we're gonna have plus r two. Okay. Now, the last substitution that we have to make here is that I sub s, we saw earlier, is six over s plus two.

**[0:23:31]** Alright. We had that from up here. Okay? That corresponds to the exponentially decaying currents in the time domain. Okay.

**[0:23:43]** So we wanna take this six over s plus two and substitute it into here for I sub s. And so we're gonna get that I sub l of s is then equal to... We'll write this term here first. It's gonna be r one r two times c times six s over s plus two, and then minus 60 r two times c. And then in the denominator, we have still the same thing, r one plus r two times l c times s squared plus r one r two c plus l s plus r two.

**[0:24:39]** Okay? K. What we do now is we multiply the numerator and the denominator by s plus two. Right? So we multiply this whole thing by s plus two over s plus two, and what we get then is six r one r two c times s.

**[0:25:04]** Right? That's from this term here. And then we get minus 60 r two c times s plus two. Then in the denominator, we have s plus two times, our original denominator. So r one plus r two l c s squared plus r one r two c plus l times s plus r two.

**[0:25:39]** Okay. So now we can start, plugging in some numerical values. And for that, we will need, the value... The numerical value for c. Alright.

**[0:25:50]** So what we were given in the problem was that l c is equal to one over 15. So that means that c is equal to one over 15 l. Alright? So c is equal to one over 15, and then l was 0.6196. Okay.

**[0:26:12]** And so the capacitance is point one zero seven six farads. Okay. So now we can substitute in numerical values. And so in the in the numerator, we get six. R one is 10.

**[0:26:31]** R two is five. And then we'll just keep this as c. Now we're working with this first term over here right now, c times s. And then we have this term over here. So we get minus 60 times r two, which is five times c times s.

**[0:26:56]** And then finally, we have from the two inside the parentheses here minus a 120, r two, which is five, times, c, which now we substitute in point one zero seven six. Okay. And then in the denominator, we get s plus two. And then we have r one plus r two, so that's 10 plus five. Right?

**[0:27:32]** That's this r one plus r two over here times l, which... L c rather, which is one over 15 times s squared. Alright? Then we have r one r two c plus l. So that's 10 for r one.

**[0:27:55]** Five for r 2.1076 for c plus... And then l I is point six one nine six times s, and then finally plus r two, which is five. Okay. So now if we look at this, we can see that, right, this is six times 10 is 60. So we have 60 times five times c times s.

**[0:28:25]** Here we have minus 60 times five times c times s. So these two things cancel each other out. And, all we're left with in the numerator is minus 120 times five times, point one zero seven six. And so that is, it turns out, minus 64.56. And then in the denominator, we have s plus two.

**[0:28:58]** And then we have 10 plus five, that's 15 over 15, that's one, times s squared. K. Then we have 10 times five times point one zero seven six plus point six one nine six. That turns out to be six times s and then plus this five over here. Okay?

**[0:29:24]** So so this actually numerically turns out to be relatively simple. Right? So this is I sub l of s. Alright? And so now, all we need to do is to compute the inverse Laplace transform of I sub l of s.

**[0:29:41]** Alright? And so to do that, we want to identify its poles. So I sub l of s, it has poles at s equal to minus two and an s squared plus six s plus five, which we can factor easily. Right? It turns out to be equal to s plus one times s plus five when that's equal to zero, which means that we also have poles.

**[0:30:11]** These are simple poles at s equal to minus one and minus five. Okay? So that means that we can write I sub l of s in this factored form as minus 64.56 divided by s plus two times s plus one times s plus five. Okay. So we have three simple poles, and so the partial fraction expansion is very straightforward.

**[0:30:46]** K. So now we wanna compute the prior... Partial fraction expansion of this. The form of the partial fraction expansion is that I sub l of s is equal to a residue k one over s plus, oops, two. We'll go in the order that we've written out of those factors.

**[0:31:10]** Plus l one over s plus one plus m one over s plus five. And we wanna compute these residues. Right? These are simple poles, so the computation is pretty easy. Right?

**[0:31:23]** K one is equal to s plus two times I l of s evaluated at s equal to minus two. So that's minus 64.56. When we multiply by s plus two, then we get rid of this factor in the denominator. So we just have these two factors over here evaluated at s equal to minus two. So minus two plus one times minus two plus five.

**[0:31:54]** Alright. And so that is minus 64.56 over minus one times three. So over minus three, that ends up being 21.52. Okay? L one.

**[0:32:14]** Alright. The residue for, the pole at s equal to minus one is s plus one times I sub l of s evaluated at s equal to minus one. So for this, right, when we multiply by s plus one, we get rid of the s plus one factor in the denominator. So we get minus 64.56 divided by and then it's minus one plus two times minus one plus five. Okay.

**[0:32:46]** So that's minus 64.56 divided by one times four. So divided by four, that's minus 16.14. And then finally, have m one, the last residue. That's at the pole at s equal to minus five. So it's s plus five times I l of s evaluated at s equal to minus five.

**[0:33:14]** Okay. And so that's minus 64.56 divided by, and then we're getting... When we multiply by s plus five, we get rid of this s plus five in the denominator. So we have, s plus two, that's minus five plus two times minus five plus one. Right?

**[0:33:34]** And so that is minus 64.56 over minus three times minus four. That's minus 64.56 over 12, which is minus 5.38. So what we finally get is that I sub l of s is equal to, 21.52 over s plus two minus 16.14 over s plus one minus 5.38 over s plus five. Okay. So now we have the partial fraction expansion of I sub l of s.

**[0:34:19]** And then from this, it's very easy to compute the inverse Laplace transform. Right? So, basically, if we go to Ulaby et al and look at table 12 dash two, Right? We have the result that we've used in the other examples in here multiple times. The for...

**[0:34:47]** The Laplace transform pair either the minus a t times u of t forms a Laplace transform pair with one over s plus a. Okay. And so from this, we can immediately write down what I sub l of t, the inverse Laplace transform of I sub l of s is. And it's going to be... If we now, arrange these in the order from the slowest exponential to the fastest exponential, it's minus 16.14 times e to the minus t.

**[0:35:23]** Right? That comes from this term over here, plus 21.52 times e to the minus two t. That comes from this first term up here, minus 5.38 times e to the minus five t from this last term over here times u of t, and that's in amps. K. So this is our final result for the current, through the inductor I sub l of t at t greater than zero.

**[0:36:01]** Okay. Okay. So from here, alright, what were the key points? Alright. And if you check this, you should find that at t equal to zero, this in fact is zero as we expected, to be.

**[0:36:25]** Okay. So what were the key points if we go through and, kind of look at this and, think about what we did and what lessons, we can draw, from this. The first point is that, as in the other examples of this type, right, the major steps in executing the Laplace transform analysis of this circuit. These major steps were first to determine the initial conditions, okay, for current through the inductor and voltage across the capacitor. So I sub l at zero minus and v sub c at zero minus.

**[0:37:19]** Then once we did that, to transform the circuit to the s domain. Okay. We needed the initial conditions to do that. In this case, we had, one non zero initial condition. V sub c at zero minus was non zero.

**[0:37:41]** So that meant that we had to introduce an additional voltage source in series with the capacitor to take that into account. Then once we had transformed the circuit to the s domain, we could go ahead and analyze the circuit in the s domain. And then, finally, perform the, inverse transform. Back to the time domain, okay, which is where we wanna be able to get our final answer. And as I noted, right, this example included a situation where we had a non zero initial condition.

**[0:38:38]** So the initial conditions here, specifically, the fact that v sub c is zero minus was non zero, This required the addition of a voltage source, Okay. In series with the capacitor in the estimate. Alright. But once we included that, we could just go ahead and analyze, the circuit in the s domain as we usually do. Okay.

**[0:39:28]** Once again, we saw that the partial fraction expansion for I sub l of s made the inverse Laplace transform very straightforward. Okay. And then finally, we saw here that, as usual, accuracy and proficiency in complex algebra. Right? These are very important in solving these types of problems.

**[0:40:23]** Okay. So that is everything for this example here, and I will now stop the recording.
