# 2026-10-19-passive-filters-and-bode-plots

Deepgram general-nova-3 2025-07-31.0, request 01a1b010-8372-72b2-ac60-698f692d357a, audio 75.6 min.

**[0:00:03]** Okay. Why don't we go ahead and get started? So I think I've finally resolved the Zoom issues and the forced, update. So just a few, announcements here. First one is that, problem set six, is due on Wednesday, so you should make sure to turn that in.

**[0:00:27]** Problem set seven, I'll post, on Wednesday morning, and it'll be due on Monday, November 2. And problem set seven will cover, transfer functions, Bode plots, and filter circuits, basically the topics that we're discussing right now. And then there's a change to my office hours for this week. So I'll have office hours today at the usual time, so after class, 10:30 to 11:55AM. And then also this afternoon, three to 04:30.

**[0:00:58]** So that's after the, lab session. That'll also be in three dot 08:02. I won't have my regular office hours on Wednesday because I have to take off on a trip shortly after class. So any questions on any of this? Any questions from our last class meeting?

**[0:01:21]** Okay. So we'll pick up from where we left off. So what we were discussing last time we met was we had just started the discussion of the frequency response of circuits and what we called filter circuits, which are basically circuits that exhibit some engineered and useful response as a function of frequency so that at certain frequencies, say, signals are transmitted through the circuit with very little attenuation at other frequencies, they're strongly attenuated. Okay? And I mentioned at the very end that when we quantify the response of circuits, then, you know, one approach is that we can do this algebraically and analytically, and another is that we can try to do it, graphically.

**[0:02:11]** And we're going to do both of these, and we'll start with the, sort of algebraic or analytical, approach, which involves the use of what we call transfer functions. Okay. So the reading for this, okay, is in Ulaby at all, and it's section nine dash one. Okay? And the basic idea of a transfer function is that we imagine that we have some linear circuit.

**[0:02:59]** Okay. And it has two input terminals. Okay. So we have, say, formulated in terms of phasors. We have an input signal, an input voltage, and an input current.

**[0:03:18]** Okay. Our polarities will, be like this. And then we have two other terminals, that were connected that are serving as our output terminals. So we have an output voltage as a phasor and an output current, as a phasor. Okay?

**[0:03:39]** And what we call the transfer function is simply a ratio of the output to the input. Okay? So a transfer function... Right. This is the ratio of the output to the input.

**[0:04:05]** Okay. Now if we look at this, we have two inputs. Right? The voltage and the current, and we have two outputs, also a voltage and the current. So there are, in principle, four different combinations that we can have for the ratio of some output to some input.

**[0:04:23]** And in different settings, right, each of these can be useful, but we will use primarily, one particular ratio, and that is going to be what we call the voltage gain, transfer function. Okay. And what we mean by the voltage gain transfer function, we'll call it, h. We'll put a twiddle under it, to remind us that this is, in general, going to be a complex quantity, and it is simply the ratio of the output voltage, which will be a function of frequency, and considered as a phasor to the input voltage phasor. This is the most common combination.

**[0:05:19]** Okay? But there are others that are sometimes useful. If we're particularly interested in, say, currents that are flowing in the circuit, then we could have or we could use what we call the current gain transfer function. Right? We'll call that h sub I of omega, and that is simply the ratio of the output current to the input current.

**[0:05:47]** So this is I out of omega divided by I in of omega. Alright? And sometimes we're interested in, say, the ratio of a current to a voltage or a voltage to a current. Okay? And, right, if we take a voltage and divide it by a current, that has units of impedance.

**[0:06:13]** Okay. So we can also consider what we call a transfer impedance. Right? That is... We'll call it h sub z of omega, and it is the ratio of the output voltage to the input, current.

**[0:06:41]** Okay. I... And then... Alright. We can also consider the the fourth combination.

**[0:06:47]** Right? If we have a current divided by a voltage that has has units of the inverse of the impedance, and that is sometime... Something that we often call the admittance. And so we have the transfer admittance. Alright?

**[0:07:08]** So that is... The usual symbol for admittance is y. So it's h sub y of omega, and this is the ratio of the output current to the input voltage. Okay. So all of these combinations are possible, but for our purposes, we will look, primarily at the voltage gain transfer function.

**[0:07:33]** Right? The ratio of the output voltage to the input voltage. Okay. So any questions before we continue? Okay.

**[0:07:42]** So... Alright. So we're gonna consider, okay, primarily, the voltage gain transfer function, which we just call h of omega. Okay. And, when we think about the transfer function, alright, it's a complex quantity, so we could formulate that in terms of sort of the rectangular expression for complex quantity, or, we could formulate it in terms of, magnitude and phase.

**[0:08:24]** Alright? And, the most typical way to do it is when you're working out the the transfer function, then very often you're working with, rectangular expressions for complex numbers. But then, when we get to the final result and we wanna understand it, then, it's most, typical and most useful to think about it in terms of its magnitude and phase. Okay? Because, the magnitude and the phase more directly reflect the kind of functionality that we want to get from, a filter circuit.

**[0:08:58]** Okay. So... Alright. What'll happen then is that we can take our transfer function, however we've worked it out, and we'll want to write it in terms of its magnitude, m of omega, and a phase factor either the j phi of omega. Okay?

**[0:09:21]** And as usual, right, m of omega here, this is the magnitude of the transfer function. And then the phase, five omega. Alright. That's going to be the inverse tangent of the imaginary part divided by the real part of the transfer function. Okay.

**[0:09:52]** And, I mean, inverse tangent here, I... In the sense that it has the actual correct phase of the transfer function of h of omega rather than being restricted to being between minus pi over two and pi over two. Okay? And we'll talk about that nuance in more detail as we work out specific transfer functions for different types of circuits. So any questions?

**[0:10:18]** Okay. So let's think about and just kinda sketch out for now a typical transfer function. Alright? And we'll do this for a lowpass filter circuit. Okay?

**[0:10:36]** And that'll allow us to introduce some terminology and the like that we use in talking about transfer functions generally. Okay? So for a lowpass filter circuit, alright, let's let's look at the magnitude of the transfer function as a function of frequency. Right? So for a lowpass filter circuit, then what we, the functionality we want is that we want the magnitude of the transfer function to be high at low frequencies.

**[0:11:08]** Right? So low frequency signals get transmitted through the circuit, and then we want the transfer function at high frequencies to be, very low. Alright? And so, just kind of, right, sketching it out, we'll have a transfer function that'll look, you know, roughly speaking, something like like this. Alright?

**[0:11:36]** The transfer function is high, at low frequencies, and it's low at high frequencies for a lowpass filter. Okay? So this is kind of a generic shape, right, for the transfer function. And so what we wanna do now is to see, well, what are key quantities, that are associated with this transfer function that, we want to know about and understand and be able to work with? And so one of them, obviously, is going to be, alright, what's the sort of maximum value over here of the transfer function?

**[0:12:11]** Alright? And we will call that m naught. K. That's a zero subscript there. And m naught, we call the gain factor.

**[0:12:25]** Okay. And, this is... The way this is defined, it is, defined as the maximum or sometimes we call it the peak, and it'll be specifically what we refer to as the nonresonant. Okay. Gain in the filters passband.

**[0:12:59]** Okay. And I'll talk about this issue of nonresonant gain, in a few minutes. Alright? But, basically, it's, you know, over the range of frequencies where, we have a high magnitude of the transfer function. So, basically, a low frequency is over here.

**[0:13:17]** What is the maximum value, that's not some localized, peak? Alright? And that's what m naught is over here. Alright? So that's one of the things that we certainly care about.

**[0:13:28]** Alright? Another thing that we care about is, right, what is the frequency at which the transfer function, is significantly below its maximum value? Alright? So, you know, maybe somewhere here. Right?

**[0:13:46]** You can see that, alright, this drops gradually. It drops off gradually. So, there's a question of, you know, where on this curve is the right frequency at which to say, alright, the response has dropped off significantly from, its maximum value. Okay? So, you know, generically, maybe it would be somewhat...

**[0:14:11]** Somewhere like this. We'll call it omega sub c. And more specifically, the way that we define that frequency is that we say that omega sub c, which we call the, corner frequency or sometimes the cutoff frequency, it is the frequency at which the magnitude of the transfer function has dropped to one over the square root of two of its maximum value m naught. So its value here is gonna be m naught divided by the square root of two. Okay?

**[0:14:48]** And this is what we call the corner where sometimes the cutoff frequency omega sub c. Alright? And this is the frequency, right, that you have... It'll be the frequencies at the edge of the range where the transfer function has a high value. Right?

**[0:15:24]** So it's the frequency at the edge. Okay. Or it could be at the edges if it's a bandpass filter. Alright? So here for a lowpass filter, we have only the...

**[0:15:39]** Right. The lower frequency of the of the passband is zero. Right? So, really, we only have to specify the the upper frequency. But if we have a bandpass filter, then we have a lower and upper that we have to specify.

**[0:15:52]** Yes. You had a question? Yeah. Is there a reason, like, a specific physical reason we choose one over root two? Does it have something to do with, like, RMS, or is it just, like, a mathematically convenient, like, value to pick for analysis?

**[0:16:05]** Oh, so so there is some arbitrariness to it, but there is a, you know, well founded justification for picking that particular value. So, right, the way we define the cutoff frequency is it's the frequency at the edges, of the passband. And, specifically, it's the frequency at which, the magnitude of the transfer function is one over root two times... Not... So then, so your question is, why do we pick it as one over root two?

**[0:16:42]** Alright. Now, can you think of a reason, anyone, for that that that would be, a reasonable value to pick? Yes. Like, power output we have made? Yeah.

**[0:16:56]** So that's exactly what it is. So, right, if we think about, the power output of a circuit, Right? And, we wanna think about, alright, what is the least arbitrary criterion we can have for the power having dropped significantly from, its maximum value? Then, you know, sort of, in in some sense, the least arbitrary criterion for that is to say power has dropped to half its value... Or at half its peak value.

**[0:17:25]** Okay? You know, if we said a third or, you know, three quarters or something like that, we could do that, but that would be... It wouldn't be as natural, right, as picking, say, one half. So if the power has dropped to half, its peak value, then remember the power is the voltage times the current. Or for a linear circuit, since the voltage and the current are proportional to each other, the power goes as the square of the voltage or the square of the current.

**[0:17:56]** And so when the power has dropped to half its value, the voltage of the current have dropped to one over root two, of, of their peak value. And so that's why, it's defined in this particular way with one over root two since the transfer functions are for voltage or current, not for power. Any other questions? Okay. So, alright.

**[0:18:23]** Basically, since the power is proportional to, right, the voltage times the current, which goes as basically the voltage squared, then, really, our criterion for defining this corner cutoff frequency is the power. And, the corner frequency is half its peak value. Okay. Alright. If we look at the, again, at, the transfer function, then, we also are often concerned with what we call the bandwidth.

**[0:19:12]** Right? So that is, the width and frequency of the range where, we have, our signals in the circuit being transmitted. Alright? And so this is the bandwidth. We call it, we use capital b to indicate the bandwidth, and this is something that we define specifically for lowpass and bandpass filters.

**[0:19:40]** Right? It doesn't really make sense to define a bandwidth for a highpass filter because the upper limit is infinite, so the bandwidth will always be infinite. But for a lowpass and a bandpass filter, it does make sense, and it's very useful to have this as sort of a quantity and a concept. Right? So for lowpass and bandpass filters.

**[0:20:09]** Okay. The bandwidth b, right, this is the width, and this is the width and frequency, okay, of the passband. Okay. And then, alright, if we look at this, the other thing that, you know, we would pretty obviously be concerned with is how rapidly does the response... Does the transfer function of the circuit drop off as we go out of the passband?

**[0:20:49]** Okay? You know, basically, how steep is this curve? Okay? And so to quantify that, really, we're talking about kind of the slope of this curve in some sense. Right?

**[0:21:06]** And we will call that, s sub g, and that is what we refer to as the roll off rate. So this is the roll off rate. Call it s g, s, kind of for slope. Right? And this is the rate at which the magnitude of the transfer function m of omega, the rate at which it decreases with frequency outside the passband.

**[0:21:53]** Okay. And if we have, right, for our ideal filter, we would want that to be very steep, typically. Right? We might want it... Bless you.

**[0:22:03]** Right? We might want it to drop, abruptly to zero. So now we can't really get that, but we would like to have it, be as steep as we can practically make it. Alright? So for...

**[0:22:17]** If we think about what would be our ideal, in terms terms of filter performance, then what we would want is for the magnitude of that slope, to be very large. Okay. So, there was one other idea then that we introduced, in the context of the gain factor. Alright? And, so I use this term here nonresonant.

**[0:22:50]** Okay? Now the reason that's, that can be an important distinction is that, right, if you have certain types of filter circuits, right, and and in particular, if you have filter circuits where it's basically a second order circuit and say you have a inductor and a capacitor in that circuit, then the magnitude of the transfer function can have this additional feature, right, where, you know, particularly near the edge of the passband, instead of just sort of dropping off smoothly like this, you can have kind of a localized peak in in the response like this, and that is often associated with a frequency at which, say, if you have an inductor and a capacitor, a frequency at which the impedances of the inductor and the capacitor cancel each other out. Okay? And then very often or not uncommonly, the transfer function at that frequency, we'll call that frequency omega naught, will be, very large. Okay?

**[0:24:15]** And so when we... You know, since this occurs only in a narrow range of frequencies here, then, we don't typically refer to that as the sort of the typical gain factor... Maximum gain factor in the passband. It's really this value, that we care about, not this localized peak. There are other applications and other situations where we do care about the shape of this peak, But, for filter circuits, usually, we're concerned with, what is the more typical response, right, across the the passband.

**[0:24:49]** But this idea of the resonant frequency is something that is important and worthwhile to be familiar with. So this is the resonant frequency. Alright. We call it, we denote it by omega naught, and this is generally defined as being the frequency at which the input impedance is purely real. And it often corresponds, okay, to an extremum of h of omega.

**[0:25:48]** Okay. And, right, just to give you a sense of how this might occur, alright, we can think of... You know, let's imagine that we have a circuit, say, like this. Alright? This is the input.

**[0:26:18]** This is the output. Right? And if we look at this, right, then we know that by voltage division, the transfer function of this, right, it is going to be the impedance of the inductor divided by the impedance of these three things in series. Right? We know that's what the result is going to be.

**[0:26:56]** We'll look at this in more detail later. But just to give you a sense of what what is... What can happen here, right, let's imagine that we are at some frequency where the impedance of the capacitor and the impedance of the inductor cancel each other out. Okay. So h of omega naught, right, then it's gonna be the impedance of the inductor just divided by r.

**[0:27:26]** Right? Because the impedances of the capacitor and the inductor have canceled each other out at that frequency. Then if you imagine that r, the resistance is very small, the transfer function at that frequency can be very large. Alright? In principle, if r goes to zero, the transfer function will go to infinity.

**[0:27:49]** Okay? But that will only happen if you're right around the resonant frequency. Okay? So that's sort of a simple example of how you can get that kind of resonant behavior, and you can see that it happens when the impedances of our reactive components here cancel each other out. So any questions on kind of the general shape and characteristics of a transfer function and the terminology associated with key parts of it?

**[0:28:25]** Yes. Oh, actually, no. Oh, okay. Mhmm. Oh, so if h is DL over r, it's not purely real.

**[0:28:38]** Yeah. So we would take the magnet... We could... And then we would take... To get the magnet...

**[0:28:41]** Right. The magnitude would be just this. Right? So it would be, omega l over r. I feel like I'm misunderstanding the concept because if they just take the magnitude, anything will be healed.

**[0:29:05]** So, like, it doesn't matter if the impedance Oh, so up here, when we say the input impedance, right, that's the impedance that you have when you're considering the two input terminals. Okay? And that... So that impedance can be complex, right, because it's an impedance. This configuration here is just a series RLC circuit.

**[0:29:39]** And since, alright, the capacitor and the inductor are in series, right, then, write that input impedance. It's gonna be r plus one over j omega c plus j omega l. All over? Yeah. For...

**[0:29:59]** It's it's the input impedance. So so from the perspective of the input terminals. Is that what you're asking? Yeah. Okay.

**[0:30:05]** Any other questions? Okay. So let's look at an example now of how we actually calculate transfer function. Okay. And the example that we'll look at here is quite a simple one.

**[0:30:25]** It's just an RC filter circuit. Right? Almost the simplest, that, that we can imagine that is not, sort of a trivial circuit. And so what we have here is we have an input, signal we'll call v sub s. Okay.

**[0:30:48]** And our actual filter circuit will be a capacitor in series with a resistor like this, so capacitor and a resistor, and we're actually going to consider two different possibilities for where we put the output terminals. Alright? One possibility is that we can take the output, terminals... Draw this a little bit better here. Alright.

**[0:31:21]** We can take the output terminals, oops, to be, across the capacitor. We'll call that voltage v sub c, alright, with this, polarity. The other possibility is that we can take the output terminals to be across the resistor. Okay. Like this.

**[0:31:41]** Alright? And let's just remind ourselves that the impedance of the capacitor is one over j omega c. Alright. The impedance of the resistor is just r. Alright?

**[0:31:54]** So what we wanna do then is to calculate the transfer function first if we take the output terminals to be across the capacitor, and then separately, we will calculate the transfer function if we take the output terminals to be across the resistor. Okay. So so that is what we wanna do here. And let's look first at what we get if we take the output terminals to be across the capacitor. Alright?

**[0:32:22]** So, right, for the circuit here to get v sub c, the easiest thing to do is just voltage division. Alright? The voltage across the capacitor is the impedance of the capacitor divided by the series impedance of the resistor and the capacitor together times the input voltage. Okay. So, basically, by voltage division, right, what we have is that the voltage across the capacitor...

**[0:32:55]** So the capacitor impedance divided by the resistor impedance plus the capacitor impedance times the input voltage, which is the total voltage across the resistor in series with the capacitor. Alright. So that's just gonna be in the numerator. We have one over j omega c. And then in the denominator, we have r plus one over j omega c, and then that is going to be times v sub s.

**[0:33:24]** Alright? So in this form, right, we have fractions in the numerator, fractions in the denominator, so it's a little bit cumbersome to deal with. So to fix that, we'll multiply by j omega c over j omega c. Okay. And when we do that, then what we get is, that v sub c is going to be just...

**[0:33:48]** In the numerator, we have one, and in the denominator, we have one plus j omega RC, okay, times v sub s. Alright? So now we have the voltage across the capacitor, v sub c, in terms of the input voltage, v sub s, and, we just divide both sides by v sub s, then that'll be the transfer function. Okay. So, now we're looking at...

**[0:34:17]** Alright. Remember, this is the voltage gain transfer function. Okay. So, this is... And we'll use a subscript c here to indicate that we are talking about the transfer function when we take the output voltage across the capacitor, not across the resistor.

**[0:34:41]** Okay. So that is v sub c over v sub s. And from this expression here, right, we can see that this is just one over one plus j omega r c. Alright? If we want, we can put that in, sort of the strictly speaking rectangular form by multiplying the numerator the denominator by, one minus j omega RC.

**[0:35:10]** Right? The complex conjugate of the denominator. Right? When we do that, that'll make the denominator purely real, and what we get is, one minus j omega r c. And then in the denominator, we have one plus omega squared r squared c squared.

**[0:35:30]** Okay? And, in either of these forms, right, either this form over here or this form over here, right, we can then take this transfer function and calculate its magnitude and its phase. Okay. So any questions on how we got the transfer function before we look at the magnitude and the phase? Okay.

**[0:35:59]** So... Right. It's pretty easy to calculate the magnitude and the phase. Right? The magnitude, right, is just the magnitude of h sub c of omega.

**[0:36:15]** Alright? And it's actually easiest to calculate it from this form over here. Right? Right? We can take...

**[0:36:24]** If we have a rational function like this, a fraction, a complex fraction, the magnitude of the fraction is just the magnitude of the numerator divided by the magnitude of the denominator. Right? And the magnitude of the denominator here... Right? The magnitude of the numerator is just one.

**[0:36:40]** For the denominator, the magnitude is the square root of the real part squared plus the imaginary part squared. Alright? And so, we're gonna get for the magnitude one over the square root of one plus omega squared r squared c squared. Right? That is the magnitude of, the transfer function.

**[0:37:03]** And then the phase, alright, we can get that from, say, over here. Right? It is, the inverse tangent of the imaginary part divided by the real part. We can take the minus sign of the imaginary part and basically pull it outside of the inverse tangent so we get minus the inverse tangent of... And then it's just of omega r c.

**[0:37:31]** Right? Because it's omega r c over one. Okay. The other way that we could have gotten this is to look at this form over here for the transfer function and recognize that the phase of the denominator is the inverse tangent of omega RC. And since this is in the denominator, then the in...

**[0:37:56]** The the phase of the transfer function itself is just the negative of the phase of the denominator. Right? So minus the inverse tangent of omega RC. Okay. So either way, this is what we get.

**[0:38:09]** Okay. So any questions on how we got the magnitude and the phase of the transfer function? Okay. So let's kind of sketch these out, alright, to see what they look like. If we look at the magnitude of the transfer function, okay, then we can see that I...

**[0:38:37]** Right? This is going to behave as a lowpass filter. Alright? So at frequencies approaching... As omega goes to zero, the magnitude goes to one.

**[0:38:50]** And as omega goes to infinity, the magnitude goes to zero. Okay. So it starts at one here. It's a zero down here, and it's going to look something like this. Alright?

**[0:39:10]** And then for the phase... Okay. If we look at the phase, when omega is zero, then we have the inverse tangent of zero, which is zero. So the phase is zero at zero frequency. And as omega goes to infinity, alright, then we have the inverse tangent of infinity, which in radians is pi over two.

**[0:39:31]** And then we have a minus sign over here. So, the phase of the transfer function overall, goes to minus pi over two in radians as, omega goes to infinity. So the phase is gonna look something like this. Alright. So this is the phase as a function of omega.

**[0:39:55]** This is minus pi over two, and it'll look something like that. Okay. So, that's kind of sketching out the magnitude and the phase of the transfer function. What we also wanna do is, to figure out what is the corner or cutoff frequency. Right?

**[0:40:20]** So that'll be the frequency at which the magnitude, this expression here, is equal to one over root two. Right? Because the maximum value is one. Okay. So we can easily figure that out.

**[0:40:34]** Right? We just say that, alright, the magnitude... The expression for the magnitude at omega c is one over the square root of one plus I, and then it's omega c squared r squared c squared. Alright. This has to be one over the square root of two.

**[0:40:53]** Right? So if you look at this, you can see, obviously, this requires that omega c times r times c is equal to one. Right? And so that means that omega c is equal to one over r times c. Alright?

**[0:41:11]** So that is, the corner frequency or cutoff frequency. Right? We can also then figure out what the phase is at the corner frequency. Right? And that is now...

**[0:41:27]** That is going to be minus the inverse tangent, and omega c times r times c is just one. Right? So it's minus the inverse tangent of one. What's the inverse tangent of one in radians? Right.

**[0:41:44]** Pi over four. So this is minus pi over four. Okay. So minus pi over four here. At the corner frequency, the phase of the transfer function is minus pi over four.

**[0:42:02]** Okay. So so this is the transfer function of the RC circuit when we have the output terminals across the capacitor. There are a couple things that we can note here. Alright? One is that...

**[0:42:19]** Right? If we look at the corner cutoff frequency omega c, right, it's one over RC. Right? And so this is one over just the RC time constant of that circuit. Right?

**[0:42:36]** So tau here is the RC time constant. Okay, of the circuit. Alright, where we have the resistor and the capacitor in series, right, it sort of makes sense that that should be the case. Alright? Because if we go back to this circuit here, if we are at low frequencies, okay, then the impedance of the capacitor is high.

**[0:43:15]** Right? And so we should expect to have a large value of the voltage across the capacitor, which is what we saw. If we think about it in terms of, you know, how rapidly can, say, the voltage across the capacitor respond if we are changing the voltage, right, then, the time scale for the voltage of the capacitor to respond is basically r time c. Okay? And so if we are at frequencies that are lower than one over RC, right, so, low frequencies, then the voltage across the capacitor is able to respond in time as we're changing the input, and so we get a large responses over...

**[0:43:56]** Across the capacitor. If the voltage is changing very rapidly, then there's no time for the capacitor to respond, and so we'll get very little modulation of the voltage across the capacitor, and so VC will be low. Okay. So that's how we can understand that. And then, alright, the other thing that we saw, quite obviously is that if we take the output signal to be the voltage across the capacitor, then this circuit acts as a lowpass filter.

**[0:44:37]** Okay. And as we discussed, there are a variety of ways that that you can understand that. So any questions on this? Okay. So the other possibility, going back to, just this RC filter circuit, is that, we have our output terminals across just the resistor.

**[0:45:01]** Right? It's not really interesting to take the output terminals to be across both of these things together because that voltage is just always the input. Right? So the other interesting possibility is to take the voltage, to be across the resistor, right, to take the output terminals to be across the resistor. So now we wanna analyze what happens in that case.

**[0:45:23]** Okay. So this is now taking the voltage across the resistor to do the output. And, again, we can calculate that voltage using voltage division. Alright? So, again, by voltage division, Alright.

**[0:45:42]** What happens here is that, right, the voltage across the resistor is the impedance of the resistor divided by the impedance of the resistor plus the impedance of the capacitor times the input voltage v sub s. So that's gonna be r over r plus one over j omega c times v sub s. And, again, alright, to deal with this fraction that we have in the denominator, we can multiply the numerator and the denominator by j omega c. Alright. So we're just multiplying by one, so it's still gonna be the same, but it makes it easier to, deal with algebraically.

**[0:46:30]** And if we do that, then what we get is j omega RC in the numerator. And then in the denominator, we have one plus j omega RC, alright, times v sub s. Right? And we can take this and, determine what the magnitude of the transfer function is and what the phase is. Right?

**[0:47:04]** Or, actually, this is not quite there yet. Right now we see that the transfer function, right, we'll call it h sub r, okay, of omega to remind us that, we're talking about the voltage across the resistor. So it's the output voltage, the voltage across the resistor divided by the input voltage v sub s. And, should now... From this expression here, right, we can see this is just j omega RC over one plus j omega RC.

**[0:47:41]** And so this now, we wanna write in terms of its magnitude and phase. Okay. So any questions on how we got the transfer function in this case? Okay. So for this complex expression over here, alright, we can calculate its magnitude.

**[0:48:09]** Alright? So, looking at this expression, the magnitude... Right? Again, this is a a complex fraction. So the magnitude of the complex fraction is going to be the magnitude of the numerator divided by the magnitude of the denominator.

**[0:48:24]** Right? The magnitude of the numerator is just omega RC, and the magnitude of the denominator is the square root of one plus, omega squared r squared c squared. Okay. So this is the magnitude of the transfer function and then the phase. Okay, it's going to be the magnitude of the numerator minus the magnitude of the...

**[0:48:56]** Or sorry. The the phase of the numerator minus the phase of the denominator. So the phase of the numerator is what in radians? Right. Pi over two minus the phase of the denominator.

**[0:49:15]** Right? What's the phase of the denominator? Right. So it's... So minus the inverse tangent of omega RC.

**[0:49:29]** Okay. So these are the magnitude and the phase, and now we can plot these out. Right? If we look at the magnitude, m sub r of omega as a function of omega, right, now we can see that, as omega goes to zero, right, the magnitude, goes to zero. So here.

**[0:49:55]** And then as omega goes to infinity, the magnitude of the transfer function goes to one. Alright? So we have one up here. So the transfer function is gonna look sorta like this. Okay.

**[0:50:13]** I... And then what we will eventually or shortly wanna do is to calculate the quarter frequency, alright, which we again define as the frequency at which the magnitude of the transfer function is equal to one over root two of its maximum value. Okay. Before we calculate that, we'll look at the phase. Alright.

**[0:50:37]** The phase here, when omega goes to zero, this inverse tangent is zero, so the phase will be pi over two. When omega goes to infinity, alright, we have the inverse tangent of infinity, which is pi over two, so the phase will go to zero. Okay. So for the phase... Right.

**[0:50:58]** Phi sub r of omega. It's a function of omega. Then it's gonna go from pi over two to zero, and it's just gonna look something like this. Okay. So now we can come back to the magnitude and calculate the the cutoff frequency omega c.

**[0:51:26]** Alright? So what we wanna do then is to set this expression for the magnitude at omega equal to omega c, set it equal to one over root two. Okay. So we're gonna have omega c times r times c divided by the square root of one plus omega c squared times r squared times c squared. That's equal...

**[0:51:50]** Going to be equal to one over root two. And, again, here, right, we can see that, if omega c is equal to one over r c, we'll have one in the numerator, which is this, and we'll have the square root of one plus one or the square root of two in the denominator. Alright? So, we can see again that this tells us that the cutoff frequency omega c is just one over RC. And then if we look at the phase at the cutoff frequency, right, this is pi over two minus, the the inverse tangent of one.

**[0:52:35]** Right? The inverse tangent of one, from, the other variant of this we know is pi over four. So, this is going to be pi over two minus pi over four, which is pi over four. Okay? So the phase at the cutoff frequency is pi over four.

**[0:52:55]** Alright? So this is what the transfer function looks like for, the RC filter circuit if we take the output to be across the resistor. And the things that we can notice here are, first, again, Okay. Omega c is equal to... Right.

**[0:53:16]** It's one over the RC time constant of the circuit. Okay. And the explanation for it is basically the same as what we had for the for the other variant where we took the output terminals across the capacitor. And what we see here is that just looking at the transfer function or, you know, thinking about the behavior of the components in the circuit as a function of frequency, we can see that, when the output terminals are connected across the resistor, this is going to behave as a highpass filter. Right?

**[0:53:58]** And and that happens basically because, at high frequencies, the impedance of the capacitor, goes to zero. Right? It's very small, so all the voltage drop will be across the resistor. Right? And so that's why we have a large output voltage at high frequencies.

**[0:54:15]** Okay. So, here, when we take the output signal to be the voltage across the resistor, then this acts as a highpass filter. Okay. So any questions on this? Okay.

**[0:54:43]** So so that's a very simple example of how we calculate transfer functions. And, you know, as you saw from this, it can be very helpful to plot out what the magnitude and the phase look like as a function of frequency. Okay? And it turns out that there's a very systematic way of doing this that, in particular, allows one to combine, many different components. And, from the plots of how, the circuit behaves as a function of frequency for sort of subparts of the circuit, we can easily construct what happens for the circuit as a whole.

**[0:55:27]** And the graphical tool that we use for this will be, what we call Bode plots. Okay. And the reading for this is in Ulaby et al, and it's section nine dash three. Okay. And the idea...

**[0:55:52]** The basic idea in a Bode plot is that instead of plotting everything on a linear scale, what we do is we put the frequency on a log scale and also the magnitude on a log scale. Alright? But we keep the phase on a linear scale. Alright? And then in addition, the way, the Bode plot terminology is used in Ulaby, and therefore, the way that we will use it here, a version of those plots where we make kind of linear approximations to what the plots look like over specific ranges of frequency will be what we strictly refer to as the Bode plot.

**[0:56:35]** And by making those linear approximations, it makes it very easy to combine kind of the Bode plots for different subparts of the circuit to get the Bode plots Bode plot for the circuit as a whole. Okay? So the basic idea is that Bode plots, they're essentially... They're log log plots. So both axes on log scales of, the magnitude of the transfer function as a function of frequency.

**[0:57:09]** And then linear log plots. So, right, of the phase versus the frequency. Right? So the phase, which is the vertical axis, is on a linear scale. The frequency, is the horizontal axis, is on a log scale.

**[0:57:32]** Okay? And, these are very useful, okay, for really visualizing and thinking about, in general, the frequency response of circuits. Okay. So since we are going to be talking about, in particular, the magnitude of the transfer function on a log scale, then, it's also very helpful to have a set of units that is kind of a natural set of units to use for, for a log scale or at least a natural scaling. Okay?

**[0:58:28]** And this is something that, I think you've probably seen in 03/2002 or 03/2002 h, and that is the decibel scale. Right? It's it's sort of the natural way of quantifying, what happens when you're thinking about, quantities in terms of logs, which means that you're thinking really in terms of multiples by which quantities change rather than, sort of constant addition or, you know, additive changes to, to quantities. So we wanna just review, the decibel or dB scale. Okay.

**[0:59:13]** What it means and how we use it. Alright? So, you may remember from three zero two or three zero two h that, when you use decibels, really what that allows you to do is to easily talk about and quantify changes by quantities, by constant factors, or equivalently to talk about ratios of different quantities relative to some reference. Okay. So can perhaps recall, alright, that decibels, alright, or dB, these quantify really the ratio, and it's most commonly the ratio of power.

**[1:00:05]** Right? It's... And it's really the ratio. Right? So of power p, right, to some reference value.

**[1:00:16]** We'll call p naught. Okay. And, in the context of, electrical circuits, then often that reference value p naught is equal to, we take it to be one watt or sometimes if we talk about, say, dBm or something like that, maybe one milliwatt. Okay? So, if we are talking about ratios of power, right, to some reference value, then it makes sense to define what we call a power gain.

**[1:01:09]** G. Alright? And that power gain is just the power divided by that reference value. Okay? And in decibels...

**[1:01:24]** So the power gain in decibels is going to be, it's 10 times the log of, p over p naught. So it's 10 times the log, and it's the log base 10 of p over p naught. Alright? So this is how we define power gain in decibels. Right?

**[1:01:49]** So every time you have a change in the power by a factor of 10, right, the log changes by one, and then by multiplying by 10, that makes it so that in decibels, a change in the power by a factor of 10 corresponds to 10 decibels. Okay? And a change in the power by a factor of a 100 is 20 decibels and so forth. Okay. So, essentially, what happens here is that each 10 x change, okay, in the power, Right?

**[1:02:30]** It changes g in decibels by 10 dB. Okay. So any questions on that basic idea? Okay. Now we're not always going to be working with or want to think about changes by a factor of 10.

**[1:02:56]** Sometimes it's very useful to think about things doubling. Alright? So if the power, say, doubles, then we take the log of two. Right? The log of two is around point three.

**[1:03:14]** Okay? So a doubling of the power changes the gain in decibels by point three times 10, which is three. Alright. So three decibels corresponds to a change in the power by a factor of two. Okay.

**[1:03:30]** So, basically, since the log base 10 of two is approximately equal to point three zero, right, then a two x change, say doubling or halving in the power, it changes power gain in dB by around three decibels. Okay. And so, for example, if we have a, say, lowpass filter, then, at the cutoff frequency, the, transfer function will have been, it's reduced by three dB compared to its maximum value. Alright? Now the other thing that we have to notice and be careful of here is that this power gain g is defined as a ratio of powers.

**[1:04:37]** But when we are talking about transfer functions, we're talking about most commonly voltage, but sometimes current, and power is proportional to the square of the voltage or the current or, you know, the voltage times the current. So, if we're looking at ratios of voltage or current, then the way that we convert that to decibels is a little bit different, okay, to take into account that squared relationship. Right? So the other thing that we have to notice here is that since the power is proportional to... Right?

**[1:05:21]** It's the voltage, right, voltage times the complex conjugate of, the current. And if we're talking about linear circuits, then the voltage is proportional to the current. Right? So, basically, the power is going as the voltage squared or the current squared, then it is also going to be the case that... Alright.

**[1:05:55]** The power gain in dB is going to be 10 times log base 10 of the power over some reference. So that's going to be 10 times the log base 10 of, say, the voltage squared over, the reference voltage squared. And so that's going to be 20. Alright. These will be magnitudes times the log base 10 of, say, the magnitude of the voltage as a phasor over the corresponding reference, and it will also be 20 times the log base 10 of, say, the same type of ratio for currents.

**[1:06:51]** Okay. So if we're talking about ratios of voltage or current, then it's a factor of 20 in front, not a factor of 10, and that's because the power goes to the voltage squared. Okay. So any questions on that? Okay.

**[1:07:09]** So let's now start to think about more generally what transfer functions are going to look like mathematically as a function of frequency. Alright? So in general... Alright. If we...

**[1:07:30]** Say if we're calculating some transfer function, right, for a linear circuit, the transfer function will be, in general, of the following mathematical form. Alright? It's going to be, a rational function of frequency. So we're gonna have a numerator, which is a function of frequency divided by a denominator, which is a function of frequency. We're gonna have to convert that to corresponding magnitude and phase.

**[1:08:09]** Alright? And the numerator... Right? I'm writing this as a capital n. I'm putting the serifs on there to emphasize this as a capital, letter.

**[1:08:22]** So n of omega and d of omega. Right? We put the twiddles there to remind ourselves that these are complex functions, and they are, going to be polynomial functions of, in general, of j omega. Alright? And, you know, basically, the reason it works out that way is because, when we are relating currents and voltages to each other, they're typically related to each other for a given component by, the impedance of that component.

**[1:09:05]** And the impedances always have, right, well, the resistor is just r. It's real. But then in terms of frequency, the impedances always have j and omega together. Right? For a capacitor, one over j omega c.

**[1:09:17]** For an inductor, j omega l. Right? So whenever we get the frequency in there, we're also gonna get this factor of j, and we'll see later when we talk about Laplace transforms. Right? Why having j omega turns out to be a natural combination and useful combination to work with, and they'll end up being polynomials.

**[1:09:40]** Right? Ration... Polynomials in the numerator and in the denominator. So a rational function basically because, know, you say if you're adding together a bunch of currents or voltages that are related to the other by impedances, then you're gonna get, you know, sort of a a linear function of constant one over j omega and j omega. Right?

**[1:10:05]** And then when you manipulate that algebraically, right, you might get... You know, you get something like that in the numerator, and then, you know, you might get this... Some polynomial function of j omega times, some voltage is equal to some other polynomial times current or something like that. And then, to solve for that voltage or, you know, time some other voltage, solve for that voltage, you have to divide by that first polynomial. That's how you get this rational function.

**[1:10:33]** Okay. So that's... This is kind of the natural mathematical form that we will get for transfer function. Oh, was there a question? Okay.

**[1:10:48]** I thought I heard something. I definitely heard that. I think someone on Zoom maybe. Excellent. Yeah.

**[1:10:53]** You did. Okay. So, yeah, so, anyway, yeah, if if there are questions on Zoom, as usually, you can, type in into the chat or you can just, speak up. So we're gonna have, right, the magnitude of the transfer function is then just going to be... Alright.

**[1:11:17]** It's the magnitude of this rational function. Okay. And in dB, alright, this is going to be 20 times the log base 10 of the magnitude of the numerator minus 20 times log base 10, the magnitude of the denominator. Okay. And so you can start to see, right, if you have the numerator and the denominator as rational functions, or as polynomial functions of j omega, then if we can figure out, well, what are the typical factors, right, that will go into the numerator or into the denominator in different circumstances, then, basically, by adding or subtracting them, we can get, the magnitude on the dB scale of the transfer function as a whole.

**[1:12:25]** And that will be a large part of, you know, what makes the Bode plots, particularly useful is that since you're plotting things on a log scale for the magnitude, you can add, or subtract, different contributions, very easily, corresponding to different factors. Okay. So that's the idea of what we're going to want to do. We're gonna start introducing the typical factors that you get in the numerator or the denominator of a transfer function, and then with the tool of Bode plots, we can easily combine them. Okay.

**[1:13:00]** So, just to give you a little preview of this. Right? Let's suppose... Alright. The first example that we'll look at is where we have...

**[1:13:12]** Let's suppose we have a transfer function where the numerator has a factor that is of the form one plus j omega over some constant we'll call omega z to the nth power. Right? So this n over here is not the same as this n of omega. That's why we have the series over here to distinguish them. And let's suppose the denominator is just one.

**[1:13:40]** Okay. So, if we look at this, then the magnitude in dB, right, it's gonna be 20 n, alright, times the log. We're always gonna be working with log base tens here. So when I write log LOG, we're gonna always assume that that is log base 10 even though we're not gonna write the, 10 subscript explicitly anymore. So it'll be one plus...

**[1:14:15]** The magnitude of one plus, j omega over omega z, And the phase is going to be n times the inverse tangent of omega over omega z. Right? So what we'll do next time is we will, you know, kind of sketch out what these two functions look like, on the appropriate log log or linear log scales. What I will leave you with now is, to think a little bit about, you know, how you might... Let's...

**[1:14:57]** To make it simpler, let's assume n is one. Alright? How would you get a combination like this in, some expression for, say, a voltage or a current in a circuit? Okay. So, I'll leave you with this.

**[1:15:16]** You can think about that, and we'll start with this next time. Alright. So any questions? Okay. If not, then we will stop here for today and pick up with this on Wednesday, and I will now stop the recording.
