# 2026-09-16-make-up-rlc-and-phasors

Deepgram general-nova-3 2025-07-31.0, request 01a1b00f-db79-7993-a6e9-bdafa141bf36, audio 80.4 min.

**[0:00:03]** Okay. Let's go ahead and get started. So this is the recording that takes the place of the class that would have been on Wednesday, September 16. So what we had done in our last class meeting was that we had gone over a fairly detailed example of how we do RLC second order circuit analysis. Okay?

**[0:00:29]** In one of the upcoming recitation sessions, there will be another, I think, couple examples of that. And there are also a number of examples of, the sort of analysis in the problem solving video... Videos that are posted on Canvas. So I'll refer you to those, in a few minutes. What I wanted to do to start off the recording is just to talk about, some of the key points, okay, for RLC circuit analysis, okay, that we saw illustrated in the example that we did in class.

**[0:01:10]** And then you'll also... I think you will also see in one of the upcoming recitations and also in the problem solving videos if you'd like to view those. So the first point, which is sort of how we get to this in the first place, is that if we have two capacitors and or inductors in circuit, so called reactive elements, then that's the situation that can lead to second order differential equations and therefore second order circuit behavior. So the presence, okay, of two capacitors and or inductors. Okay.

**[0:02:01]** What we call sometimes reactive elements in the circuit. This can lead to second order differential equations for the current and the voltage. And, it's really the second order differential equation that can give rise to, these different behaviors that we've been describing. You know, so called overdamped, critically damped, and underdamped, response. In analyzing and understanding these kinds of circuits, because we have a second order differential equation, we will have two independent solutions, to the differential equation, at least to the homogeneous, form of the differential equation.

**[0:02:57]** And in order to determine the, unknown coefficients of those independent solutions, then we will need two boundary conditions because we will need essentially two linear equations for, our two unknowns. And we get one, from each of those boundary conditions. Okay. So we will need two, initial conditions. Okay.

**[0:03:29]** So for example, in the example that we looked at in class, it was an initial condition for a current. And then, the derivative of that current at t equal to zero, we need two of them in order to determine all of the unknown coefficients. Okay. And so part of solving a typical problem of this type is going to be determining what those initial conditions are. Right?

**[0:04:12]** What we also saw in the solution to the example that we looked at in class is that, the solution to the homogeneous differential equation, what we call the complementary function, those were going to be some form of decaying exponential. And all three of the different types of behavior that we that we specify, over damped, critically damped, or under damped, they all have this exponential decay element to the solution to the homogeneous equation. And so that means that that part of the solution describes the transient response. That is the response that decays away as we approach the steady state situation. Okay.

**[0:04:58]** So the solution to the homogeneous equation, Okay. What we call, the characteristic function or the complementary function. Okay. This complimentary function, okay, describes the circuit's transient response. Okay.

**[0:05:43]** That is the response that decays away as we go to t going to infinity, which is going to be the steady state, situation. Okay? And, as we saw in the, example of the RLC series circuit, that transient response... Okay. That can be overdamped.

**[0:06:13]** That's what happens if you have a large value of the resistance, which leads to high energy dissipation. It can be underdamped, which is what happens if we have a small value of the resistance. Alright? So a slower energy dissipation. Or right at the transition between these, it can be critically damped.

**[0:06:46]** Okay. And then what we also saw was that, when we came up with the particular integral, for, our differential equation, then that particular integral, basically, constant term, that describes the circuit's long term steady state response. Okay? Another way of thinking about it or approaching is to get that steady state response by looking at the final conditions, which we we also did. The way that we did it in class was to do it from the perspective of coming up with the particular integral and then looking at the final conditions as sort of a confirmation of the correctness of that particular integral.

**[0:07:40]** Okay. So the particular integral, Okay. That is the part of the solution that corresponds to the nonzero and, in our case, constant portion on the right hand side of the of the differential equation. This particular integral describes the circuit's long term steady state response. Okay.

**[0:08:21]** And then the final point that I'll make here, which is something that I've mentioned a number of times in class and that I think you'll experience as you work through problems of this type, is that having practice, particularly in coming up with the differential equation that governs the behavior of a particular current or voltage. Having practice in doing that is really the best and probably only way to sort of become good at that process and through that to really understand the nature of the time dependent behavior of these types of circuits. Alright? So practice is extremely helpful. Yeah.

**[0:09:11]** Okay. If anything, that's probably an understatement, right, in developing proficiency. Okay. And analyzing and understanding, second order circuits. In the time domain.

**[0:09:48]** Okay. So, so we did one example, in detail of sort of the... A non series RLC circuit. We did one example in class. There are some other examples that you'll see in an upcoming recitation session, and there are a number of examples of this sort of problem in the video problem solving examples that are on the Canvas site.

**[0:10:12]** And the ones that are on this topic are the ones from chapter six of Ulaby, so where the problem numbers are six dot something. Okay. So you can also see those examples if you wanna see more about how these kinds of analyses are worked out. So you can also see examples of all of this and more examples, right, on the video, problem solving examples page on the Canvas site. Okay.

**[0:10:59]** And these are the problems. From Ulaby, specifically chapter six of Ulaby. Okay. And there are several examples on the Canvas site that you can take a look at. Okay.

**[0:11:18]** So, so that is pretty much everything that we want to say, in class, for now about time domain analysis of, circuits. What we wanna do next is to start, building up our toolbox for depend... For, of other techniques that can be used to analyze, different types of time dependent circuit behavior. And we will start this off by looking at, what we call, AC, circuit analysis. That is looking at the behavior of, circuits that have specifically sinusoidal signals, and the main tool that we will use for that, will be something called phasors.

**[0:12:05]** And phasors are basically a way of using complex numbers to represent sinusoidal signal quantities in circuits. Alright. So we're gonna look now at AC circuit analysis. Specifically, we're gonna start off by looking at circuits with sinusoidal signals, and we'll see how we analyze those using what we call phasors. Okay.

**[0:12:41]** And the reading for this is in Ulaby at All, and it's chapter seven. Okay. So what do we mean precisely when we talk about AC electrical signals? Right? So AC, electric signals, these refer to currents.

**[0:13:15]** Okay, and voltages, right, that vary with time, but they have a very specific type of time dependence. Right? So, when we say AC signals, we mean signals that are periodic and that have a fixed frequency. Okay. So that does not include all possible time dependent signals, but, it's a very useful class of signals because often, we are in a situation where we just have AC signals.

**[0:14:04]** And furthermore, what we will see later in the course is that we can use our understanding of the analysis of circuits, with AC signals to, basically, by superposition, understand and analyze and eventually design circuits that have, more complicated types of time dependent behavior. Okay. So, later in the course, what we will see is that any time varying signal, okay, can be analyzed and understood as a superposition, okay, of signals at different frequencies. Okay. And there's one significant and important caveat here, which is that since we are invoking superposition, right, for, for this particular concept, then, that idea of being able to look independently at different frequencies and then sort of adding up the responses, it applies specifically to linear circuits and systems.

**[0:15:42]** Okay? So if you have nonlinear behavior, then, in general, you're not able to do this. Although in a subset of circumstances, even for nonlinear systems, you can still do it. Okay. So this applies specifically to linear circuits and systems.

**[0:16:08]** Okay. Because the idea and the formalism of superposition applies specifically to linear circuits and systems. Okay. So in what we will be talking about next, phasors and how we use phasors to analyze circuits, we're going to make very extensive use of some of the basic ideas pertaining to sinusoidal signals. And, also, we'll be doing a lot of arithmetic and algebra with complex numbers.

**[0:16:40]** Okay. So these are things that, I know, to various degrees you had covered in three zero two or three zero two h. But, you know, since it's been a while since you've probably seen them, then what I have done is to create and post a kind of refresher lecture on sinusoidal signals and complex numbers. So it's posted in... I'll post it in the lecture topics discussion board just before the recording for for this recording that I'm making now.

**[0:17:20]** And then I'll also put a link to it in, the announcements on the Canvas site. Okay? So you can find it, either way. And if you feel that you need or would like a refresher on sinusoidal signals and circuits... Or sinusoidal signals and complex numbers, then you can take a look at the recording.

**[0:17:43]** And I will also post the notes from from that recording if you wanna go through it a little more quickly. Okay? Having said that, then what we want to do next is to introduce this idea of phasors and then see how we use phasors to analyze, circuits. Alright? So the reading on phasors is in Ulaby et al, and it's section seven dash three.

**[0:18:22]** Okay. And the basic idea of phasors is that phasors are essentially a way of using complex numbers to represent the behavior of sinusoidal signals. Okay? And I... You know, we have to be careful and precise about exactly how we formulate the correspondence between phasors and the corresponding AC signal because we know that physically signals like currents and voltages and so forth, they're they're real physical quantities, so they have to be real.

**[0:19:04]** That is real in the sense of not having any imaginary numerical component. But the phasers are going to be complex numbers, and so we have to specify how we go back and forth between these two descriptions in a way that, you know, ensures that we do not get things like imaginary voltages or currents. Okay. So phasors, these are complex numbers that are used to represent electrical signals that are at fixed and well defined frequencies. Okay.

**[0:19:59]** So that is, right, AC electrical signals as we have already defined them. Okay. So suppose that we have some AC signal, x of t, that could be a current or a voltage, say. Alright? Then this is going to be a real quantity.

**[0:20:19]** Alright? It's going to be oscillating at some fixed frequency. And so we can always write that as the real part of some complex number we'll call capital x here. And so when I write a twiddle underneath, say, a capital numb... A capital letter like this, a capital letter symbol, the twiddle underneath is going to be an explicit reminder to us that this is a complex quantity that we are talking about.

**[0:20:51]** Okay. Complex in the sense that it can have a real and imaginary component to it. K. We can write an AC signal, small x of t, as the real part of a complex number, capital x, total, times e to the j omega t. And the e to the j omega t is what gives us the oscillating behavior in the AC signal.

**[0:21:18]** And omega here is the angular frequency x of t, and then j here is the square root of minus one, okay, which we've seen, already. Okay. And in this way of representing this AC electrical signal, small x of t, then this complex number, capital x here, is what we call, the phasor. Right? And the phasor, capital x twiddle, is going to be time independent.

**[0:22:04]** So all the time dependence is in the factor e to the j omega t. X twiddle is time independent, and it is, in general, a complex number. Okay. So this is a time independent. And complex quantity.

**[0:22:30]** And it is a way of representing the AC electric signal in what we call the phasor or often, the frequency domain. Okay. So instead of working in the time domain, alright, we're going to be... And thinking about, say, signals as a function of time, we're going to be in the frequency domain. And what we will see as we develop these ideas is that in the frequency domain, it is very often the case that we will think of things...

**[0:23:13]** Functions as functions of frequency. Right? And we'll see in the last part of the course how we back... Go back and forth between a time domain description of behavior and a frequency domain description of behavior. Understanding and using phasors is really the first step in doing that.

**[0:23:31]** Okay? So we're working in the frequency domain, and the phasor then is a quantity in the phasor or frequency domain that corresponds to our signal x of t, which is a real quantity that describes the signal in the time domain. Okay. So so that's what a phasor is. It's a complex number that we use to represent a...

**[0:24:15]** An AC time dependent signal in the time domain and the correspondence between the AC electric signal small x of t and the phasor capital x twiddle is given by this expression over here. Okay. So let's explore what that correspondence... How that correspondence really works and how we go back and forth, between phasers and, AC signals. So let's take our complex number x twiddle.

**[0:24:48]** We know that we can always write it as its magnitude times e to the j times its phase. Right? So we can write that as a magnitude, the magnitude of x twiddle times the phase factor e to the j five. Alright. So five then is the phase of the complex number x twiddle.

**[0:25:08]** So if we write the phasor in this way, then we know that the corresponding AC signal small x of t, alright, is equal to the real part of capital x twiddle, which in magnitude phase form is the magnitude of x twiddle times e to the j phi, e to the j omega t, alright, which is equal to the real part of the magnitude of x twiddle times e to the j omega t plus phi. Alright? And that is equal to, the magnitude of x total times... Right? When we take the real part of this, the magnitude of any complex number is already real.

**[0:25:57]** Right? So, so we get that full magnitude. And then the real part of e to the j times some angle is just the cosine of that angle. So we get the cosine of omega t plus phi. Okay.

**[0:26:12]** So if we have our phasor written in magnitude phase form like this, then, the magnitude of the phasor is the amplitude of the AC signal, and then the phase of the phasor is a phase shift in, the, the AC signal, in this particular form over here. And then conversely, if we have an AC signal in the time domain written like this, then, this relationship tells us how to get from that AC electric signal to the magnitude and the phase of the corresponding phasor. Okay. So, let's now look, a little more carefully at how things work in the time domain and in the phasor domain. What we have seen so far is that in the time domain, if we are thinking about the behavior of circuits and we have, say, capacitors and or inductors in the circuit, then we are going to get derivatives of current or voltage, right, in the time domain.

**[0:27:29]** So one of the things that we would like to do is to see how, say say, taking derivatives or the inverse integrating in the time domain, what kind of operation that corresponds to in the phasor domain. And what we will see is that differentiation and integration in the time domain end up corresponding to multiplication or division by frequency in the phasor domain. And so going to the phasor domain, one of the things that makes it very powerful is that it allows us to convert differential operations to algebraic operations, right, multiplying by frequency. And so, therefore, we go from differential equations to algebraic equations. Right?

**[0:28:20]** Differential equations in the time domain to algebraic equations in the phasor domain, and solving algebraic equations is easier than solving differential equations. Okay. So that's one of the payoffs that you get from going to the phasor or more generally the frequency domain. So to see how this works, let's consider some current, say, I of t in both the time and the phasor domains. Okay.

**[0:28:58]** So, we have IFT. Right? And we we know that in terms of the phasor, we can write that as the real part of capital I twiddle. So I twiddle is gonna be the phasor, e to the j omega t. And so if we write the phasor in magnitude phase form, then this becomes the magnitude of I twiddle times the cosine of omega t plus pi.

**[0:29:26]** Alright. This is where the phasor I twiddle is equal to its magnitude times e to the j times its phase. Okay. So with that correspondence, let's see how the derivative, the differentiation operation in the time domain carries over to the phasor domain. So in the time domain, alright, we have DIDT.

**[0:29:54]** Alright? And from what we have done so far, you know that we're gonna get DIDTs very naturally in the course of analysis of circuits that have, say, inductors in them. Okay? So if I of t is of this form up here that we've just specified and and we take the derivative with respect to t, then we're gonna get minus omega times the magnitude of I total times the sine of omega t plus phi. Alright?

**[0:30:27]** What happens in the phasor domain? Okay. We have the IDT, and we can write I as the real part of I total times e to the j omega t. And if we take the derivative of this with respect to time, then, right, we can exchange the order of the operation of taking the real part and taking the time derivative. So we're gonna get, the real part of the derivative with respect to time of I twiddle e to the j omega t.

**[0:31:09]** Okay. And, since I twiddle is independent of time, right, then with respect to differentiation, it acts as a constant. So taking the derivative with respect to time of this quantity just brings down a factor of j times omega. So this is gonna be the real part of j omega times I twiddle times e to the j omega t. Okay.

**[0:31:35]** And so this expression here now gives us the phasor representation of the I d t. And what this tells us is that this factor multiplying either j omega t is actually the phasor representation of the I d t. Right? So this is the phasor representation of the I d t. And what this has shown us is that a derivative with respect to time in the time domain becomes multiplication by j omega in the phasor domain.

**[0:32:26]** Alright? So we have, indeed, converted a differential operation in the time domain to just an algebraic operation, multiplying, multiplication by j omega in the phasor domain. Alright? And so instead of getting differential equations, we will get algebraic equations. Okay.

**[0:32:47]** Now in working through this, right, it's it's not necessarily that immediately obvious that this over here will give us a correct phasor representation of the derivative with respect to time in the sense that if we evaluate this, you know, will we in fact get this expression here that we worked out explicitly by taking the derivative of the AC signal expression in the time domain. So let's quickly check that. So if we do a quick check, right, then the real part of j omega, I twiddle, e to the j omega t. Right? That is this thing over here.

**[0:33:34]** Right? Right? That's gonna be the real part of j omega. And then I twiddle is the magnitude of I twiddle, and then we're gonna get either the j omega t plus five. Right?

**[0:33:57]** And then from here, alright, we can use Euler's formula. Alright. This is the real part of j omega times I twiddle times... And then for e to the j times the quantity omega t plus phi, we have the cosine of omega t plus phi plus j times the sine of omega t plus phi. Alright?

**[0:34:24]** And then when we take the real part of this, then what you can see is that because of this j out here, then, this cosine term is going to go away because this first term overall is gonna be purely imaginary. And so we will only get the sine term over here, and we'll have a factor of j squared, which gives us a minus sign. Okay. So this is gonna be equal to, taking the real part, minus omega times the magnitude of I times the sine of omega t plus phi. Okay?

**[0:35:03]** And if we compare that to what we had up here, just explicitly calculating the derivative of I with respect to t in the time domain, you can see that it's the same thing. Right? So in fact, this did work. Okay. So, so that's what we get for differentiation.

**[0:35:23]** In the phasor domain, differentiation with respect to time, ends up being multiplication by j omega. What that then suggests is that if we have integration in the time domain, that should correspond to division by j omega in the phasor domain. And in fact, that turns out to be the case. So similarly, if we have the integral, say, of I of t dt, alright, that's gonna be, in terms of phasors, the real part of I twiddle, e to the j omega t dt. Alright?

**[0:36:04]** Which, again, we can exchange the order of taking the real part and taking the integral. So we have the integral of I twiddle e to the j omega t dt. Okay. And when we do this integral, right, I total is independent of time, so we can pull it outside the integral. And then when we integrate e to the j omega t dt, then that's just one over j omega times e to the j omega t.

**[0:36:35]** So now we get the real part of I twiddle over j omega times e to the j omega t. This is now the phasor representation of the integral of I of t dt. And so what this shows us is that this factor multiplying either the j omega t is the phasor representation okay, of the integral of I of t d t. So as we expected, integration with respect to time and the time domain corresponds to division by j omega in the phasor domain. Again, we're going from, you know, essentially, calculus operation integration to an algebraic operation division by j omega in the in the phasor domain.

**[0:37:34]** Okay. So so what we've seen here then is the differentiation Okay. And integration and the time domain. Okay. These become algebraic operations in the phasor domain.

**[0:38:12]** Okay. So then, what that also means is that differential equations in the time domain. These become now algebraic equations. In the phasor domain. Okay.

**[0:38:45]** And so instead of having to solve differential equations in the time domain, now at least if you are working with sinusoidal signals, you can replace that by solving algebraic equations in the phasor domain, which is actually much easier. Okay. So that's how signals go back and forth, between the time phasor domain. What we wanna look at next is how circuits and circuit components, go back and forth, or go into the phasor domain. Alright.

**[0:39:20]** So how are circuits and circuit components? How are these represented in the phasor domain? Okay. So so, basically, we wanna look at this for, resistors, inductors, and capacitors. Alright.

**[0:39:53]** So let's look first at resistors, which are the simplest. Okay? So for a resistor... Alright. It looks like this.

**[0:40:08]** So resistor r, and it has some voltage across it, we'll call v sub r, and a current flowing through it, we'll call I sub r. Alright? So in the time domain... Alright. We know from Ohm's law that all we have is that v sub r is equal to the resistance r times I sub r.

**[0:40:33]** Okay? So what we wanna do now is to represent the voltage and the current here, v sub r and I sub r, in the phasor domain and see... And then, plug that representation into Ohm's law and see, what relation we get, between the phasors. Alright. So in the phasor domain, alright, what we have is that v sub r, right, is a phasor.

**[0:41:02]** Right? Or we know it's gonna be the real part of a phasor, capital v sub r, times e to the j omega t. And then the current, I sub r, is going to be the real part of a phasor I total sub r times e to the j omega t. So what we wanna do now is to figure out from Ohm's law what the relationship has to be between the phasors, v sub r twiddle and I sub r twiddle. Okay?

**[0:41:35]** And we do that by taking these expressions over here for v sub r and I sub r in the time domain and just substituted them into Ohm's law over here. Alright? So what we get then is that the real part of v sub r twiddle, e to the j omega t, That's a small b sub r in the time domain is equal to r times the real part of I sub r twiddle either the j omega t. Okay? And then since r, the resistance, is real, we can write this as the real part of r times I sub r e to the j omega t.

**[0:42:24]** Okay. And then if we move everything to the left hand side, then what we get is that the real part of b sub r twiddle minus r times I sub r twiddle times e to the j omega t is equal to zero. Okay. Now looking at this, it might be tempting to say immediately, well, that means that v sub r total has to be equal to r times I sub r total. So so in fact, that is the case, but we have to be a little bit careful about how we do that.

**[0:43:04]** Right? So in order for that to be true, it requires, first of all, that, this quantity in the parenthesis here, v sub r minus r, I sub r, be time independent. Okay? Because if it were not time independent, then it could have a time dependence that cancels out this e to the j omega t. And then this could be, it could be purely...

**[0:43:29]** What's left could be purely imaginary. So it could be nonzero, but the real part of this could still be zero. So we need to use the fact that phasors are time independent. Okay. And then, also, right, we know that the other factor, either the j omega t, it's never zero.

**[0:44:03]** Right? Because if it were zero, then, right, that... This equation could hold without v sub r minus r times I sub r being equal to zero. And it also oscillates between real and imaginary. Okay.

**[0:44:32]** So that means that, yeah, with with all of this together, then it means that, in fact, this quantity in the parentheses has... Really does have to be equal to zero. So given all of this, then we can also conclude, in fact, that b sub r twiddle minus r times I sub r twiddle is equal to zero, or, equivalently, b sub r twiddle is equal to r times I sub r twiddle. So, essentially, what we have here is that Ohm's law in the time domain carries, over to being kind of the obvious analog in the phasor domain. Okay.

**[0:45:21]** So v sub r total is equal to r times I sub r total. Okay. So we can call this Ohm's law for phasers. Okay. So that's what we have for resistors in the phasor domain.

**[0:45:53]** What about, say, inductors? Okay. For an inductor... Alright. It looks like this.

**[0:46:05]** So it has an inductance l, some voltage v sub l, and a current flowing through an I sub l. Right? And for an inductor, we know that in the time domain, the current voltage relationship is that v sub l is equal to l times d I sub l d t. Right? And what we wanna do here is basically the same thing that we did for resistors.

**[0:46:35]** We wanna write b sub l and I sub l in the time domain. We wanna write them in terms of their phasors, plug those expressions back into this relationship over here, and see what that tells us about how the phasors for v sub l and isodal are related to each other. So in the phasor domain, right, again, what we have for the voltage and the current are that v sub l is equal to the real part of capital v sub l twiddle, that's the phasor, times e to the j omega t, and the current isobel is equal to the real part of I sub l twiddle. Alright. I sub l twiddle is the phasor for the current isobel times e to the j omega t.

**[0:47:24]** Okay. Now we will take these expressions here and plug them into, the current voltage relationship that we have for an inductor in the time domain. And if we do that, what we get is on the left hand side, we have the real part of v sub l twiddle, e to the j omega t, and that's equal to, on the right hand side, l times the derivative with respect to time of the real part of I sub l total, e to the j omega t. And, right, we can again exchange the order of the, derivative with respect to time and taking the real part, recognize that I sub l twiddle is independent of time. So the derivative with respect to time, is applied essentially only to either the j omega t, and it just brings down a factor of j omega.

**[0:48:26]** So this becomes the real part of... Right. And we can move the l inside the square brackets and taking the real part of as well because l is real. So we get the real part of j omega l times I sub l twiddle times e to the j omega two. Okay.

**[0:48:47]** And so from this, now what we see is that v sub l total over here has to be equal to j omega l times I sub l total over here. So what we get for an inductor is that v sub l twiddle in the phasor domain is equal to j omega l times I sub l twiddle on the right hand side. And so what you can see here is that a differential relationship between voltage and current for the inductor in the time domain now becomes an algebraic relationship between the phasors, b sub l twiddle and I sub l twiddle in the phasor domain. Okay? And then finally, we can look at capacitors.

**[0:49:44]** Okay. So a capacitor... Alright. It's like this. Capacitance c, voltage v sub c, and a current I sub c.

**[0:49:58]** Okay. For a capacitor, we know that the current voltage relationship in the time domain is that the current I sub c is equal to c times dB sub c dt. Right? If we go to the phasor domain... Alright.

**[0:50:23]** We wanna write the current I sub c and the voltage b sub c in terms of their respective phasors. And as we have seen now a couple times already, v sub c in the time domain is gonna be the real part of v sub c twiddle times e to the j omega t. So v sub c twiddle is the phasor for the voltage across the capacitor. Then I sub c in the time domain is equal to the real part of I sub c twiddle, e to the j omega t. So capital I sub c twiddle is the current through the capacitor in the phasor domain.

**[0:51:06]** And we wanna take now these phasor expressions here and plug them into the current voltage relationship in the time domain for the capacitor and see what it tells us about how the voltage and current phasors are related to each other for a capacitor. So if we do that, then on the left hand side where we have I sub c, we have the real part of I sub c twiddle e to the j omega t. And then on the right hand side, we have c times the derivative with respect to time of the real part of v sub c total e to the j omega t. Okay? And what we can do as we have done before is to recognize that the capacitance being real can be moved inside the square brackets.

**[0:52:06]** Alright? Because then it won't affect taking the real part. And then when we apply the differential operator, the derivative with respect to time, then the capacitance and the phasor are time independent, so they behave just as constants. And we're just taking the derivative with respect to time of either the j omega t, which brings down a factor of j omega. Alright?

**[0:52:27]** So we get then doing all of that, the real part of j omega c, v sub c twiddle, e to the j omega t. Okay? And then equating this over here all the way on the left with this that we arrived at all the way on the right, then what we get is that, I sub c total is equal to j omega c v sub c total. Or we solve for the voltage phasor v sub c total is equal to one over j omega c times I sub c 12. Okay.

**[0:53:17]** So this now is the relationship between the voltage and the current for a capacitor in the phasor domain. Okay? And what we see again is that a differential relationship in the time domain has become just an algebraic relationship in the phasor domain. Alright? Now if we step back a little bit and look at what we have now derived for the resistor, capacitor, and inductor, what we see in each case is that in the phasor domain, we get a direct proportionality relationship between the voltage and the current for each of these three components.

**[0:54:05]** Okay? And in the case of a resistor, the proportionality constant is just r, the resistance. In the case of the inductor, the proportionality constant is j omega l. And in the case of the capacitor, the proportionality constant is one over j omega c. But they all have...

**[0:54:29]** For each of these three components, these relationships all have the common form where the voltage as a phasor is equal to some parameter times the current as a phasor. Alright? And we will call that parameter the complex impedance. Okay. So what we see now from looking at these three relationships together is that we can define what we call a complex impedance.

**[0:55:05]** Okay. We'll usually just call it the impedance, and we will recognize that it is complex. And the symbol that we'll use for it is capital z. And here, we'll write a twiddle underneath to remind us that it it is complex. Okay?

**[0:55:21]** And the defining relationship for the impedance is that it is the ratio of the voltage phasor to the current phasor. Alright? And with this definition of the impedance and, the relationships between the current and voltage phasors that we have now arrived at for, the resistor, the inductor, the capacitor, what we can then see is that the impedance for a resistor is just the resistance. The impedance for an inductor... Alright.

**[0:56:04]** If we go back to this relationship over here that we derive for an inductor, v over I is going to be j omega l. Okay. So the impedance for the inductor is j omega l. So the inductor. And then the impedance for a capacitor, right, from this relationship that we derived over here, again, we take the voltage phasor divided by the current phasor, then the impedance is gonna be one over j omega c.

**[0:56:45]** So this is the impedance of capacitor. Okay. And what we also see from the way the impedance is defined is that if we have a short circuit, then that corresponds to the impedance being zero. Right? Intuitively, we know that's the case for a resistor.

**[0:57:19]** Right? And then, right, it makes sense that a short circuit, should correspond to, the impedance being zero because, the impedance being zero means that we have zero voltage for any amount of current, that's the defining behavior of a short circuit. And then correspondingly, an open circuit corresponds to the impedance becoming infinite. Alright? So in the case of the resistor, intuitively, makes sense because, right, an infinite resistance is an open circuit.

**[0:58:05]** And in terms of the defining relationship, voltage over current for the impedance, when the impedance is infinite, that means that, the current is zero or any voltage. Alright? And that's the, you know, defining behavior of an open circuit. Okay? With that, it then allows us to see how the inductor and the capacitor behave in terms of the limits as frequency goes to zero, whether it's a short circuit or an open circuit.

**[0:58:41]** Okay. So for an inductor, Alright. We can see that the impedance of the inductor goes to zero. That is we have short circuit behavior when the frequency goes to zero. Right?

**[0:59:05]** Because the impedance of the inductor is proportional to frequency. So when the frequency goes to zero, we have zero impedance, so short circuit. When the frequency become... Goes to infinity, so very high frequencies, then the impedance of the inductor goes to infinity as well. So it behaves as an open circuit.

**[0:59:25]** So z sub l goes to infinity, that is an open circuit when omega goes to infinity. Alright? And then correspondingly for a capacitor, okay. Then the impedance of a capacitor goes to infinity, which is an open circuit when the frequency goes to zero. Right?

**[1:00:05]** We can see that from this relationship up here. Right? The frequency goes to zero. That is omega goes to zero. The impedance of the capacitor becomes infinitely large.

**[1:00:16]** And then the impedance of the capacitor goes to zero, that is we have a short circuit when the frequency is very high. That is in the limit of omega going to infinity. Alright. Okay. So so that is sort of how we think about phasors, how we go between a time domain representation and a phasor or frequency domain representation of a given AC signal and then how we represent our main circuit components, resistor, capacitor, and inductor in the phasor domain.

**[1:01:05]** Alright? With all of that in hand, then what we can do is we can start looking at how we do circuit analysis in the phasor domain. So now we're moving on to phasor domain, circuit analysis. Okay. And the reading for this is in Ulaby et al, and it is section seven dash four.

**[1:01:41]** Okay. And, so the the short version of it is that all of the tools that we have used for circuit analysis in the time domain that you are familiar with and very proficient at can be mapped in a very straightforward way and applied in a very straightforward way in the phasor domain as well. And that's basically because KCL and KVL can be applied to phasors in essentially the same way as we've applied them to time domain, currents, and voltages. Alright. So KCL and AVL, right, these apply to phasors essentially in the same way as to time domain currents and voltages.

**[1:02:46]** Okay. And so more explicitly, right, if we're looking at, say, KCL at a node, okay, then we know what KCL at a node says in the time domain. It says that if we sum over all of the outgoing branches from a node, then the sums, the sum over all the outgoing currents has to be zero. Okay. But if we express each of those currents as a phasor, then it's very straightforward to see that the corresponding condition on, the current phasors is that the sum over all of the branches connected to that node of the outgoing currents also has to be equal to zero.

**[1:03:41]** Right? So so for this, we can see that KCL applies in exactly the same way to phasors as it does to time domain currents. And then correspondingly, if we're applying KVL, say, around the loop, okay. Alright. Remember, that says that if we sum over all of the components going around that loop and we add up all the voltages associated with those components, they have to add up to zero.

**[1:04:16]** Then if we write each of those voltages, in terms of its corresponding phasors, then it is, again, very easy to see that the sum over all of those components of the voltage phasers has to be equal to zero. Okay. So so this works essentially all in exactly the same way in the phasor domain as in the time domain. Alright. So, what happens then is that noted mesh analysis.

**[1:04:53]** Okay. Thevenin and Norton equivalents. Okay. And all of the other sort of tools and techniques of circuit analysis that we generally apply, these can be applied to phasors. Okay.

**[1:05:21]** Just as you have done, we have done two circuits in the time domain. Okay. So what are the key steps in doing this? What we'll do today in this recording is I'll kind of outline the key steps of how this works. And then starting next time, we will see how that's carried out in an example.

**[1:05:54]** Okay. So the key steps in phasor domain circuit analysis are, first of all, we have to get all our currents and voltages into the phasor domain. Right? So we wanna defend... Define the phasor quantities corresponding to our currents and voltages.

**[1:06:25]** But we have to be a little bit careful about how we do this. To do it, we use what's called the cosign form or sometimes the standard cosign form, okay, for our time domain quantities. Okay. So, for example, what we saw earlier was that if we have some voltage, we'll call it v one of t, and we write it in the time domain as some amplitude capital v one times the cosine of omega t plus phi. Right?

**[1:07:07]** Then... Alright. That is going to be... We know that we can write that as the real part of b one e to the j times phi e to the j omega t. Okay?

**[1:07:23]** And this then, is the standard way that we define the phasor corresponding to v one. So v one... Capital v one twiddle. So this then becomes the real part of now the phasor b one twiddle times e to the j omega t. Alright?

**[1:07:46]** And b one twiddle is equal to b one e to the j pi. Alright. So that, is very straightforward. But we have to be a little bit careful. Alright.

**[1:08:01]** Let's suppose we had another signal, v two of t, which in the time domain, we write it as v two times, say, the sine of omega t. Okay. It is not the case that the phasor corresponding to v two is this magnitude v two times one corresponding to a phase angle of zero because here we have the sine function and not the cosine function. What we have to do is to take this signal here and write it in this standard cosine form, which means, some amplitude times the cosign of omega t plus, whatever the appropriate phase angle is. Right?

**[1:08:58]** So if we do that to this signal, then we can write it as v two times the cosine of omega t minus 90 degrees. Okay. Because introducing this phase shift of minus 90 degrees is how we go from the cosine, to the cosine. Okay? And then what we have is that now this is equal to the real part of v two times e to the minus j times 90 degrees, right, times e to the j omega t.

**[1:09:43]** Okay. And this now is the phasor b two twiddle. So this now becomes the real part of b two twiddle times e to the j omega t. Alright? So this now, this is sort of the, alright, the the definitional relationship.

**[1:10:06]** And to make the conversion easy, we wanna put, our signal in the time domain into this, cosine form over here. So now what we have is that v two is equal to the amplitude v two times e to the minus j times 90 degrees. Okay. So the key point here is that to go from a time domain sinusoidal signal to the phasor domain, we always have to write the time domain signal in this standard cosign form over here in order to make the straightforward... To use the straightforward correspondence to the corresponding phasor.

**[1:10:46]** Okay? And you can, you know, easily imagine or practice what are other examples of how this works out. K. So that's the first step, getting all your currents and voltages into the phasor domain. Key point there is to use the standard cosign form to do that correctly.

**[1:11:06]** At least that's the easiest way to do it correctly. Then, what you have to do is transform, the circuit of interest to the phase domain. One part of that is getting the currents and voltages into the phasor domain, which we've just seen, and then applying that, say, to, the sources and such in the circuit. And then the other part is representing the passive components, resistors, inductors, and capacitors in terms of their complex impedances. Right?

**[1:11:51]** So in transforming a circuit to the phasor domain, we wanna get our currents and voltages in terms of their corresponding phasors. And then we wanna take our resistors, represent those using the impedance of resistor, which is just the resistance. Inductors are represented using the inductor impedance, which is j omega l, and then capacitors are represented using the, impedance of a capacitor, which is one over j omega c. Okay. So as a very simple example, right, let's imagine that we have a circuit where we have a voltage source, a resistor, and a capacitor in a simple loop.

**[1:12:55]** Alright. So this is the resistor. This is the capacitor. And let's imagine that our voltage source is some amplitude capital b sub s times the cosine of omega t minus a 135 degrees. Okay.

**[1:13:13]** And what we wanna do is to figure out what the current is around this loop. Then to represent this in the phasor domain... Okay. Then we would have... For the source, we would write it as a phasor, capital b sub s total, and the phasor corresponding to this signal over here.

**[1:13:43]** You can see that this is already in the cosine form. So the phasor is the amplitude capital b sub s times e to the minus j times a 135 degrees. Okay. And that takes into account, this phase angle over here. And then for the resistor, its impedance is r.

**[1:14:09]** For the capacitor, its impedance is one over j omega c, and then we're going to be working with the current as a phasor as well. So this is how we would represent this circuit in the phasor domain. Okay? And then once we have that, then we just apply the usual tools of circuit analysis to the circuit that we have now formulated in the phasor domain. In the case of this very simple example here, that would just be, basically, KVL around this loop here.

**[1:14:50]** Alright? So in general, what we would do is to formulate KCL, KVL, and so forth, in the phasor domain. Okay. In this particular example over here, alright, we would be applying k v l going around loop. So we would have the voltage across the resistor, which is the resistor impedance, z sub r twiddle times the current, plus the voltage across the capacitor, which is z sub c twiddle times the current I twiddle.

**[1:15:39]** And the sum of those two would have to be equal to, the phasor for the voltage source. Right? And so then, if we just plug in the appropriate impedances, right, for the resistor, the impedances are. For the capacitor, the impedance is one over j omega c. So both of these are multiplying isototal.

**[1:16:01]** That's the left hand side. And then on the right hand side, we have v sub s total, right, which we'll keep it as that for now. Alright. So that's how we, in this case, formulate KVL. And once we have, our circuit equations, then we just have to solve those equations for whatever our unknown phase and variables are.

**[1:16:35]** K. So now we solve for the unknown phase or variable or variables. So in this case over here, right, the unknown that we wanted to solve for is I over here. Right? The phasor for the current going around the loop.

**[1:16:54]** So we would just solve this equation here for I, which means dividing both sides by r plus one over j omega c. Okay. So I, as a phasor, I twiddle, right, is b sub s twiddle over r plus one over j omega c. Okay. What we will see frequently going forward is that it's very convenient to get rid of these fractions that we have in a numerator or a denominator.

**[1:17:31]** So we wanna take this equation and multiply it by j omega c over j omega c. Right? We can always multiply by one, which is what we're doing here. And so if we do that, then what we get is j omega c over one plus j omega r c times v sub s total. Alright?

**[1:17:55]** So that is now our solution in the phasor domain for the current I. Alright? Sometimes, we will be content to work with, the solution in the phasor domain, but very often, what we really want is the solution in the time domain. So what we need to do then is to take that solution in the phasor domain and convert it back to the time domain. So we wanna convert the phasor back to the time domain.

**[1:18:37]** Okay. So then that would give us the current I as a function of time t. So that is going to be... Right. Definitionally, we know it's the real part of the phasor I twiddle times e to the j omega t.

**[1:18:53]** And, we solve for I twiddle. It's this expression here. Alright? So it's going to be the real part of j omega c over one plus j omega r c times... And then v sub s total is the amplitude of the original signal v sub s times e to the j omega t minus a 135 degrees.

**[1:19:23]** Okay. And then to complete, the solution, then it would be necessary to take this expression in the square brackets and work with it in a way that allows you to get just the real part of that. And, starting next time, we'll see a number of examples of exactly how, this is done in different circumstances. Okay. So so that's basically the the general approach of how we do phase and I mean, circuit analysis.

**[1:19:57]** What we'll do starting next time is we'll start looking at some examples of, of how we do this and how various types of tools that we use in circuit analysis carry over to, the phasor domain. So that is everything that I wanted to have for this recording. And so I will now stop the recording, and we will meet for class again on Monday.
