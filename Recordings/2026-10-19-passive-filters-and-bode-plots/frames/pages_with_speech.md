# 2026-10-19-passive-filters-and-bode-plots: board pages with the speech that accompanied them

24 distinct pages from 84 page-final frames. A section's image is the LAST frame of the page (most ink); earlier states of the same page are listed under it. Confidence marks: `(word?)` word < 0.55; `{…}` utterance mean < 0.7. Times are recording time.

## page 01  f_0005.jpg  on screen [0:00:00 – 0:02:46]
<sub>sharpness 1466, ink 1.5 %, colour 0.2</sub>
<sub>earlier states of this page: f_0003.jpg (0:02:24), f_0004.jpg (0:02:46)</sub>

- [0:00:03] Okay.
- [0:00:07] Why don't we go ahead and get started? So I think I've finally resolved
- [0:00:13] the Zoom issues and the forced,
- [0:00:16] update.
- [0:00:17] So just a few, announcements here. First one is that,
- [0:00:22] problem set six,
- [0:00:23] is due on Wednesday, so you should make sure to turn that in. Problem set seven, I'll post,
- [0:00:30] on Wednesday morning, and it'll be due on Monday, November 2. And problem set seven will cover, transfer functions, Bode plots, and filter circuits, basically the topics that we're discussing
- [0:00:42] right now.
- [0:00:44] And then there's a change to my office hours for this week. (So?) I'll have office hours today at the usual time, so after class, 10:30 to 11:55AM.
- [0:00:55] And then also this afternoon,
- [0:00:57] three to 04:30. So that's after the, lab session.
- [0:01:02] That'll also be in three dot 08:02.
- [0:01:04] I won't have my regular office hours on Wednesday because I have to take off on a trip shortly after class.
- [0:01:12] So any questions on any of this?
- [0:01:16] Any questions from our last class meeting?
- [0:01:21] Okay. So we'll pick up from where we left off. So what we were discussing
- [0:01:25] last time we met was we had just started the discussion of
- [0:01:31] the frequency response of circuits and what we called filter circuits, which are basically circuits that exhibit
- [0:01:38] some engineered and useful response as a function of frequency so that at certain frequencies, say, signals are
- [0:01:48] transmitted through the circuit with very little attenuation (at?) other frequencies, they're strongly attenuated. Okay? And I mentioned at the very end that when we quantify
- [0:02:00] the response of circuits,
- [0:02:03] then, you know, one approach is that we can do this algebraically and analytically,
- [0:02:08] and another is that we can try to do it, graphically. And we're going to do both of these, and we'll start with the, sort of algebraic or analytical,
- [0:02:18] approach, which involves the use of what we call
- [0:02:23] transfer functions.
- [0:02:28] Okay. So the reading for this,
- [0:02:34] okay, is in
- [0:02:38] Ulaby (at?) all, and it's section nine dash one.
- [0:02:43] Okay?
- [0:02:44] And
- [0:02:46] the basic idea

## page 02  f_0008.jpg  on screen [0:02:46 – 0:04:24]
<sub>sharpness 1432, ink 2.0 %, colour 0.2</sub>
<sub>earlier states of this page: f_0006.jpg (0:03:42)</sub>

- [0:02:46] the basic idea
- [0:02:47] of a transfer function
- [0:02:50] is that we imagine
- [0:02:53] that we have some linear circuit.
- [0:02:59] Okay.
- [0:03:01] And it has
- [0:03:03] two input terminals.
- [0:03:05] Okay. So we have,
- [0:03:07] say, formulated in terms of phasors.
- [0:03:10] We have an input signal, an input voltage,
- [0:03:14] and
- [0:03:16] an input current.
- [0:03:18] Okay. Our polarities will, be like this.
- [0:03:21] And then we have two other terminals,
- [0:03:24] that were connected that are serving as our output terminals.
- [0:03:29] So we have an output voltage as a phasor and an output
- [0:03:36] current, as a phasor. Okay?
- [0:03:39] And
- [0:03:41] what we call the transfer function is simply a ratio of the output to the input. Okay? So a transfer function...
- [0:03:55] (Right.?) This is the ratio
- [0:03:58] of the output
- [0:04:02] to the input.
- [0:04:05] Okay. Now if we look at this, we have two inputs. Right? The voltage and the current, and we have two outputs, also a voltage and the current. So there are, in principle, four different combinations
- [0:04:17] that we can have for the ratio of some output to some input.
- [0:04:23] And in different settings,

## page 03  f_0021.jpg  on screen [0:04:24 – 0:10:21]
<sub>sharpness 2513, ink 3.8 %, colour 0.2</sub>
<sub>earlier states of this page: f_0014.jpg (0:06:45), f_0018.jpg (0:07:45), f_0020.jpg (0:09:36)</sub>

- [0:04:23] And in different settings,
- [0:04:25] right, each of these can be useful, but we will use primarily,
- [0:04:30] one particular ratio, and that is going to be what we call
- [0:04:36] the voltage gain,
- [0:04:38] transfer function.
- [0:04:45] Okay. And what we mean by the voltage gain transfer function,
- [0:04:49] we'll call it, h. We'll put a twiddle under it, to remind us that this is, in general, going to be a complex quantity,
- [0:04:58] and it is simply the ratio of the output voltage,
- [0:05:02] which will be a function of frequency,
- [0:05:04] and considered as a phasor to
- [0:05:08] the input
- [0:05:10] voltage phasor. This is the most common
- [0:05:18] combination.
- [0:05:19] Okay?
- [0:05:20] (But?) there are others that are sometimes useful. If we're particularly interested in, say, currents that are flowing in the circuit, then we could have
- [0:05:33] or we could use (what?) we call the current gain transfer function.
- [0:05:37] Right? We'll call that
- [0:05:39] h sub I
- [0:05:41] of omega, and that is simply the ratio of the output current to the input current. So this is I out
- [0:05:49] of omega divided by I in
- [0:05:54] of omega. Alright?
- [0:05:57] And sometimes we're interested in,
- [0:06:00] say, the ratio of a current to a voltage or a voltage to a current.
- [0:06:05] Okay? And, right, if we take a voltage and divide it by a current, that has units of impedance.
- [0:06:13] Okay. So
- [0:06:15] we can also consider
- [0:06:18] what we call a transfer
- [0:06:22] impedance.
- [0:06:23] Right? That is... We'll call it h sub z of omega,
- [0:06:29] and it is the ratio of the output voltage
- [0:06:34] to the input,
- [0:06:37] current.
- [0:06:41] Okay. I... And then...
- [0:06:44] Alright. We can also consider the the fourth combination. Right? If we have a current divided by a voltage that has has units of the inverse of the impedance, and that is (sometime...?) Something that we often call the admittance.
- [0:06:59] And so we have
- [0:07:01] the transfer
- [0:07:06] admittance.
- [0:07:07] Alright? So that is... The usual symbol for admittance is y.
- [0:07:12] So it's h sub y of omega,
- [0:07:15] and this is the ratio of the output current
- [0:07:19] to the input
- [0:07:23] voltage.
- [0:07:24] Okay.
- [0:07:25] So all of these combinations are possible, but for our purposes, we will look, primarily at the voltage gain transfer function. Right? The ratio of the output voltage to the input voltage. Okay. So any questions before we continue?
- [0:07:41] Okay.
- [0:07:42] So...
- [0:07:45] Alright. So we're gonna consider,
- [0:07:51] okay, primarily,
- [0:07:59] the voltage gain
- [0:08:01] transfer function, which we just call h of omega.
- [0:08:06] Okay.
- [0:08:07] And, when we think about the transfer function, alright, it's a complex quantity,
- [0:08:13] so we could formulate that in terms of sort of the rectangular expression for complex quantity, or, we could formulate it in terms of, magnitude and phase. Alright? And,
- [0:08:26] the most typical way to do it is when you're working out the
- [0:08:32] the transfer function, then very often you're working with, rectangular expressions for complex numbers. But then, when we get to the final result and we wanna understand it, then,
- [0:08:42] it's most, typical and most useful to think about it in terms of its magnitude
- [0:08:47] and phase. Okay? Because,
- [0:08:49] the magnitude and the phase more directly reflect the kind of functionality that we want to get from, a filter circuit. Okay. So...
- [0:09:00] Alright. What'll happen then is that we can take
- [0:09:05] our transfer function, however we've worked it out,
- [0:09:09] and we'll want to write it
- [0:09:12] in terms of its magnitude, m of omega,
- [0:09:15] and a phase factor (either?) the j phi
- [0:09:18] of omega. Okay?
- [0:09:21] And as usual, right, m of omega here, this is the magnitude
- [0:09:27] of the transfer function.
- [0:09:29] And then the phase,
- [0:09:31] {(five?) omega.}
- [0:09:35] Alright. That's going to be the inverse tangent
- [0:09:37] of
- [0:09:39] the imaginary part
- [0:09:45] divided by the real part of
- [0:09:50] the transfer function. Okay.
- [0:09:52] And, I mean, inverse tangent here, (I...?) In the sense that it has the actual correct phase of the transfer function of h of omega rather than being restricted to being between minus pi over two and pi over two. Okay? And we'll talk about that nuance
- [0:10:09] in more detail as we work out specific transfer functions for different types of circuits. So any questions?
- [0:10:18] Okay. So
- [0:10:21] let's think about and just kinda sketch out for now

## page 04  f_0022.jpg  on screen [0:10:21 – 0:10:23]
<sub>sharpness 1470, ink 2.1 %, colour 0.2</sub>

- [0:10:21] let's think about and just kinda sketch out for now

## page 05  f_0088.jpg  on screen [0:10:23 – 0:22:40]
<sub>sharpness 3819, ink 5.7 %, colour 0.3</sub>
<sub>earlier states of this page: f_0023.jpg (0:12:00), f_0026.jpg (0:14:24), f_0042.jpg (0:19:22), f_0072.jpg (0:21:13), f_0074.jpg (0:21:13)</sub>

- [0:10:21] let's think about and just kinda sketch out for now
- [0:10:26] a typical transfer function. Alright? And we'll do this for
- [0:10:33] a lowpass filter circuit. Okay? And that'll allow us to introduce some terminology and the like that we use in talking about transfer functions generally. Okay? So for a lowpass filter circuit,
- [0:10:46] alright, let's
- [0:10:50] let's look at the magnitude
- [0:10:54] of the transfer function as a function of frequency. Right? So for a lowpass filter circuit, then what we,
- [0:11:01] the functionality we want is that we want the magnitude of the transfer function to be high at low frequencies. Right? So low frequency signals get transmitted through the circuit, and then we want the
- [0:11:15] transfer function at high frequencies to be, very low. Alright? And so, just kind of,
- [0:11:24] right, sketching it out, we'll have a transfer function that'll look,
- [0:11:30] you know, roughly speaking, something like
- [0:11:34] like this. Alright?
- [0:11:36] The transfer function is high, at low frequencies, and it's low at high frequencies for a lowpass filter. Okay? So this is kind of a generic shape, right, for the transfer function. And so what we wanna do now is to see, well, what are key quantities,
- [0:11:53] that are associated with this transfer function that,
- [0:11:57] we
- [0:11:58] want to know about and understand and be able to work with? And so one of them, obviously, is going to be,
- [0:12:05] alright, what's the sort of maximum value over here of the transfer function? Alright? And we will call that
- [0:12:15] m naught.
- [0:12:16] K. That's a zero subscript there. And m naught,
- [0:12:21] we call
- [0:12:23] the gain factor.
- [0:12:25] Okay.
- [0:12:29] And,
- [0:12:30] this is... The way this is defined,
- [0:12:35] it is, defined as the maximum or sometimes
- [0:12:40] we call it the peak,
- [0:12:42] and it'll be specifically what we refer to as the nonresonant.
- [0:12:50] Okay. Gain
- [0:12:53] in the filters
- [0:12:58] passband.
- [0:12:59] Okay. And I'll talk about this issue of nonresonant gain,
- [0:13:04] in a few minutes. Alright? But, basically, it's, you know, over the range of frequencies where, we have a high magnitude of the transfer function. So, basically, a low frequency is over here.
- [0:13:17] What is the maximum value,
- [0:13:19] that's not some localized,
- [0:13:21] peak? Alright? And that's what m naught is over here. Alright? So that's one of the things that we certainly care about. Alright?
- [0:13:30] Another thing that we care about is,
- [0:13:34] right, what is the frequency at which the transfer function,
- [0:13:38] is significantly below its maximum value? Alright? So, you know, maybe somewhere here. Right? You can see that,
- [0:13:48] alright, this drops gradually. It drops off gradually. So, there's a question of, you know, where on this curve is the right frequency at which to say, alright, the
- [0:14:01] response has dropped off significantly from, its maximum value. Okay?
- [0:14:07] So, you know, generically,
- [0:14:10] maybe it (would?) be somewhat... Somewhere like this. We'll call it omega sub c.
- [0:14:15] And more specifically,
- [0:14:18] the way that we define that frequency
- [0:14:22] is that we say that omega sub c, which we call the, corner frequency or sometimes the cutoff frequency,
- [0:14:29] it is the frequency
- [0:14:31] at which the magnitude of the transfer function
- [0:14:35] has dropped to one over the square root of two of its maximum value m naught. So its value here is gonna be m naught divided by the square root of two. Okay?
- [0:14:48] And
- [0:14:50] this is what we call the
- [0:14:54] corner
- [0:14:55] (where?) sometimes the cutoff
- [0:15:03] frequency
- [0:15:04] omega sub c.
- [0:15:07] Alright?
- [0:15:08] And this is the frequency,
- [0:15:13] right, that you have...
- [0:15:16] It'll be the frequencies at the edge of the range where
- [0:15:21] the transfer function has a high value. Right? So it's the frequency at the edge.
- [0:15:30] Okay. Or it could be at the edges if it's a bandpass filter. Alright? So here for a lowpass filter, we have only (the...?) Right. The lower frequency of the of the passband is zero. Right? So, really, we only have to specify the the
- [0:15:48] upper frequency. But if we have a bandpass filter, then we have a lower and upper that we have to specify. Yes. You had a question? Yeah. Is there a reason,
- [0:15:55] like, a specific physical reason we choose one over root two? Does it have something to do with, like, RMS, or is it just, like, a mathematically convenient, like, value to pick (for?) analysis?
- [0:16:05] Oh,
- [0:16:06] so so there is some arbitrariness to it, but there is a,
- [0:16:10] you know, well founded justification for picking that particular value. So,
- [0:16:16] right, the way we define the cutoff frequency is it's the frequency at the edges,
- [0:16:21] of the passband.
- [0:16:27] And, specifically,
- [0:16:30] it's the frequency at which,
- [0:16:33] the magnitude of the transfer function is one over root two times...
- [0:16:38] Not... So then, so your question is, why do we pick it as one over root two? Alright.
- [0:16:44] Now,
- [0:16:46] can you think of a reason, anyone, for (that?) that that would be, a reasonable value to pick? Yes.
- [0:16:53] {Like, power (output?) (we?) have (made??)}
- [0:16:55] Yeah. So that's exactly what it is. So,
- [0:16:59] right, if we think about, the power output of a circuit, Right? (And,?)
- [0:17:06] we wanna think about, alright, what is the least arbitrary criterion we can have for the power having dropped significantly from, its maximum value? Then,
- [0:17:17] you know, sort of, in in some sense, the least arbitrary
- [0:17:20] criterion
- [0:17:21] for that is to say power has dropped to half its value... (Or?) (at?) half its peak value. Okay?
- [0:17:27] (You?) know, if we said a third or, you know, three quarters or something like that, we could do that, but that would be... It wouldn't be as natural, right, as picking, say, one half.
- [0:17:37] So if the power
- [0:17:39] has dropped to half,
- [0:17:41] its peak value, then remember the power is the voltage times the current. Or for a linear circuit, since the voltage and the current are proportional to each other, the power goes as the square of the voltage or the square of the current. And so when the power has dropped to half its value, the voltage of the current have dropped to one over root two,
- [0:18:04] of, of their peak value. And so that's why, it's defined in this particular way with one over root two since
- [0:18:12] the transfer functions are for voltage or current, not for power.
- [0:18:16] Any other questions?
- [0:18:18] Okay. So,
- [0:18:23] alright. Basically,
- [0:18:25] since the power
- [0:18:28] is proportional to,
- [0:18:30] right, the voltage times the current, which goes as basically the voltage squared,
- [0:18:36] then,
- [0:18:38] really, our criterion for defining this corner (cutoff?) frequency is the power.
- [0:18:44] (And,?) the corner frequency is
- [0:18:50] half its peak value.
- [0:18:56] Okay.
- [0:19:01] Alright. If we look at the, again, at, the transfer function,
- [0:19:06] then,
- [0:19:07] we also
- [0:19:09] are often concerned with what we call the bandwidth.
- [0:19:12] Right? So that is, the width and frequency of the range where,
- [0:19:17] we have,
- [0:19:19] our signals in the circuit being transmitted. Alright?
- [0:19:23] And so this is the bandwidth.
- [0:19:29] We call it, we use (capital?) b to indicate the bandwidth, and this is something that we define specifically for lowpass
- [0:19:37] and bandpass filters. Right? It doesn't really make sense to define a bandwidth for a highpass filter because
- [0:19:44] the upper limit is infinite, so the bandwidth will always be infinite. But for a lowpass and a bandpass filter, it does make sense, and it's very useful to have this as
- [0:19:54] (sort?) of a quantity and a concept. Right? So for lowpass
- [0:20:03] and
- [0:20:06] bandpass filters.
- [0:20:09] Okay.
- [0:20:11] The bandwidth b,
- [0:20:13] right, this is the width,
- [0:20:17] and this is the width and frequency,
- [0:20:21] okay, of the passband.
- [0:20:29] Okay. And then,
- [0:20:33] alright, if we look at this, the other thing that,
- [0:20:36] you know, we would pretty obviously be concerned with is how rapidly
- [0:20:41] does the response...
- [0:20:43] Does the transfer function of the circuit
- [0:20:45] drop off as we go out of the passband? Okay?
- [0:20:50] You know, basically, how steep is this curve? Okay?
- [0:20:54] And
- [0:20:56] so to quantify that, really, we're talking about kind of the slope
- [0:21:02] of this curve in some sense. Right?
- [0:21:06] And
- [0:21:07] we will call that,
- [0:21:09] s sub g, and that is what we refer to as the roll off rate.
- [0:21:18] So this is the roll off rate.
- [0:21:22] Call it s g, s, kind of for slope. Right? And this is the rate
- [0:21:33] at which
- [0:21:35] the magnitude of the transfer function (m?) of omega, the rate at which it decreases
- [0:21:41] with frequency
- [0:21:46] outside the passband.
- [0:21:53] Okay. And if we have,
- [0:21:57] right, for our ideal filter, we would want that to be very steep, typically. Right? We might want it... Bless you. Right? We might want it to drop, abruptly to zero. So (now?) we can't really get that, but we would like to have it, be as steep as we can practically make it. Alright? So
- [0:22:14] for...
- [0:22:17] If we think about
- [0:22:19] what would be our ideal,
- [0:22:21] in terms terms of filter performance,
- [0:22:26] then what we would want is for the magnitude of that slope, to be very large.
- [0:22:35] Okay.
- [0:22:36] So, there was one other
- [0:22:40] idea then that we introduced,

## page 06  f_0113.jpg  on screen [0:22:40 – 0:24:50]
<sub>sharpness 4367, ink 7.0 %, colour 0.2</sub>
<sub>earlier states of this page: f_0097.jpg (0:22:54), f_0104.jpg (0:24:00), f_0108.jpg (0:24:49), f_0110.jpg (0:24:49)</sub>

- [0:22:40] idea then that we introduced,
- [0:22:43] in the context of the gain factor. Alright?
- [0:22:46] And, so I use this term here nonresonant.
- [0:22:50] Okay?
- [0:22:51] Now the reason that's,
- [0:22:54] that can be an important distinction
- [0:22:57] is that,
- [0:22:59] right, if you have certain types of
- [0:23:03] filter circuits, right, and and in particular, if you have filter circuits where
- [0:23:10] it's basically a second order circuit (and?) say you have a inductor and a capacitor
- [0:23:15] in that circuit,
- [0:23:17] then
- [0:23:18] the
- [0:23:20] magnitude of the transfer function
- [0:23:22] can have this additional feature, right, where,
- [0:23:26] you know, particularly
- [0:23:28] near the edge of the passband,
- [0:23:30] instead of just sort of dropping off smoothly like this, you can have
- [0:23:37] kind of a localized
- [0:23:39] peak
- [0:23:42] in (in?)
- [0:23:45] the response like this,
- [0:23:47] and that is often associated with a frequency at which, say, if you have an inductor and a capacitor, a frequency at which the impedances of the inductor and the capacitor cancel each other out. Okay?
- [0:24:00] And then very often or not uncommonly,
- [0:24:04] the transfer function at that frequency,
- [0:24:08] we'll call that frequency omega naught,
- [0:24:11] will be,
- [0:24:13] very large. Okay?
- [0:24:15] {(And?)}
- [0:24:16] so when we... You know, since this occurs only in a narrow range of frequencies here, then,
- [0:24:22] we don't typically refer to that as the sort of the typical gain factor... Maximum gain factor in the passband. It's really this value, that we care about, not this localized peak. There are other applications and other situations where we do care about the shape of this peak, But,
- [0:24:40] for filter circuits, usually, we're concerned with,
- [0:24:43] what is the more typical response, right, across the the passband.
- [0:24:49] But this idea of the resonant frequency is something that is important and worthwhile to be familiar with. So this is the resonant frequency.

## page 07  f_0184.jpg  on screen [0:24:50 – 0:30:11]
<sub>sharpness 1536, ink 2.0 %, colour 0.2</sub>
<sub>earlier states of this page: f_0116.jpg (0:24:51), f_0121.jpg (0:24:52), f_0123.jpg (0:25:53), f_0126.jpg (0:25:54), f_0145.jpg (0:28:18), f_0146.jpg (0:28:18), f_0148.jpg (0:28:18), f_0149.jpg (0:28:19), f_0155.jpg (0:28:27), f_0156.jpg (0:28:28), f_0157.jpg (0:28:28), f_0159.jpg (0:28:28), f_0161.jpg (0:28:29), f_0178.jpg (0:30:11)</sub>

- [0:24:49] But this idea of the resonant frequency is something that is important and worthwhile to be familiar with. So this is the resonant frequency.
- [0:25:02] Alright. We call it, we denote it by
- [0:25:06] omega naught,
- [0:25:08] and
- [0:25:09] {this}
- [0:25:11] is generally defined as being the frequency
- [0:25:18] at which the input impedance
- [0:25:27] is purely real.
- [0:25:31] And
- [0:25:32] it often
- [0:25:34] corresponds,
- [0:25:39] okay, to
- [0:25:40] an extremum
- [0:25:46] of h of omega.
- [0:25:48] Okay.
- [0:25:49] And,
- [0:25:53] right, just to give you a sense of how this might occur, alright,
- [0:25:58] we can think of... You know, let's imagine that we have
- [0:26:10] a circuit, say, like this. Alright?
- [0:26:15] This is the input.
- [0:26:18] (This?) is the output. Right?
- [0:26:26] And if we look at this, right, then
- [0:26:32] we know that by voltage division,
- [0:26:35] the transfer function of this,
- [0:26:39] right, it is going to be the impedance of the inductor
- [0:26:44] divided by
- [0:26:46] the
- [0:26:47] impedance of these three things in series.
- [0:26:53] Right? We know that's what the result is going to be. We'll look at this in more detail later. But just to give you a sense of what what is... What can happen here, right, let's imagine
- [0:27:04] that we are at some frequency
- [0:27:06] where the impedance of the capacitor and the impedance of the inductor cancel each other out.
- [0:27:12] Okay.
- [0:27:13] So
- [0:27:16] h of omega
- [0:27:18] naught,
- [0:27:19] right, then it's gonna be
- [0:27:22] the impedance of the inductor
- [0:27:24] just divided by r.
- [0:27:26] Right? Because the impedances of the capacitor and the inductor have canceled each other out at that frequency.
- [0:27:33] Then if you imagine that r, the resistance is very small,
- [0:27:39] the
- [0:27:40] transfer function at that frequency can be very large.
- [0:27:44] Alright?
- [0:27:45] In principle, if r goes to zero, the transfer function will go to infinity. Okay?
- [0:27:50] But that will only happen if you're right around the resonant frequency. Okay? So
- [0:27:58] that's
- [0:27:59] sort of a simple example of how you can get that kind of resonant behavior, and you can see that it happens when the impedances of our reactive components here cancel each other out.
- [0:28:12] So any questions on
- [0:28:14] kind of the general shape and characteristics of
- [0:28:18] a transfer function
- [0:28:20] and the terminology associated with key parts of it?
- [0:28:25] Yes. Oh, actually, no. Oh, okay. Mhmm.
- [0:28:30] Oh, so if h is (DL?) over r, it's not purely real.
- [0:28:38] Yeah. So we would take the magnet... We could... And then we would take... To get the magnet... Right. The magnitude
- [0:28:45] would be just
- [0:28:48] this.
- [0:28:49] Right?
- [0:28:50] So it would be,
- [0:28:54] omega l over r. I
- [0:29:00] feel like I'm misunderstanding the concept because if (they?) just take the magnitude, anything will be (healed.?) So, like, it doesn't matter if the impedance Oh,
- [0:29:10] {so}
- [0:29:11] up here, when we say the input impedance,
- [0:29:14] right,
- [0:29:16] that's the impedance that
- [0:29:20] you have when you're considering the two input terminals.
- [0:29:23] Okay?
- [0:29:24] And that... So that impedance can be complex,
- [0:29:29] right, because it's an impedance.
- [0:29:34] This
- [0:29:35] configuration here is just a series RLC circuit.
- [0:29:39] And since,
- [0:29:41] alright, the capacitor and the inductor are in series,
- [0:29:45] right, then,
- [0:29:47] write that input impedance.
- [0:29:49] It's gonna be r plus
- [0:29:51] one over j omega c plus
- [0:29:54] j omega l. (All?) (over??) Yeah.
- [0:29:59] For... It's it's the input impedance. So so from the perspective of the input terminals. Is that what you're asking? Yeah. Okay.
- [0:30:05] Any other questions?
- [0:30:08] Okay.
- [0:30:09] So
- [0:30:11] let's look at an example now of

## page 08  f_0185.jpg  on screen [0:30:11 – 0:31:12]
<sub>sharpness 1139, ink 1.6 %, colour 0.2</sub>

- [0:30:11] let's look at an example now of
- [0:30:14] how we actually calculate
- [0:30:16] transfer function.
- [0:30:21] Okay. And the example that we'll look at here is quite a simple one. It's just an RC
- [0:30:28] filter circuit.
- [0:30:31] Right? Almost the simplest,
- [0:30:33] that,
- [0:30:34] that we can imagine that is not, sort of a trivial circuit.
- [0:30:39] And so what we have here is we have an input,
- [0:30:42] signal we'll call v sub s.
- [0:30:47] Okay.
- [0:30:48] And our actual
- [0:30:50] filter circuit
- [0:30:52] will be
- [0:30:54] a capacitor
- [0:30:58] in series with a resistor
- [0:31:00] like this, so capacitor
- [0:31:03] and a resistor,
- [0:31:05] and we're actually going to consider
- [0:31:07] two different possibilities for where we put the output terminals.
- [0:31:11] Alright?
- [0:31:12] One possibility

## page 09  f_0209.jpg  on screen [0:31:12 – 0:38:20]
<sub>sharpness 1485, ink 2.1 %, colour 0.3</sub>
<sub>earlier states of this page: f_0190.jpg (0:34:01), f_0196.jpg (0:34:02), f_0199.jpg (0:36:00), f_0205.jpg (0:38:20)</sub>

- [0:31:11] Alright?
- [0:31:12] One possibility
- [0:31:14] is that we can take the output, terminals...
- [0:31:18] Draw this a little bit better here.
- [0:31:20] Alright. We can take the output terminals, oops,
- [0:31:24] to be,
- [0:31:25] across the capacitor.
- [0:31:28] We'll call that voltage v sub c, alright, with this, polarity.
- [0:31:33] The other possibility
- [0:31:35] is that we can take the output terminals to be across the resistor.
- [0:31:40] Okay. Like this. Alright?
- [0:31:42] And let's just remind ourselves
- [0:31:45] that the impedance of the capacitor
- [0:31:48] is one over j omega c. Alright. The impedance of the resistor
- [0:31:52] is just r.
- [0:31:54] Alright? So what we wanna do then is to calculate the transfer function first if we take the output terminals to be across the capacitor, and then separately,
- [0:32:04] we will calculate the transfer function if we take the output terminals to be across the resistor.
- [0:32:10] Okay. So
- [0:32:13] so that is what we wanna do here. And let's look first
- [0:32:18] at what we get if we take the output terminals to be across the capacitor. Alright? So,
- [0:32:24] right, for the circuit here to get v sub c, the easiest thing to do is just voltage division. Alright? The voltage across the capacitor
- [0:32:32] is the impedance of the capacitor
- [0:32:35] divided by
- [0:32:37] the series impedance of the resistor and the capacitor together times the input voltage. Okay. So, basically,
- [0:32:47] by voltage division,
- [0:32:50] right, what we have is that the voltage across the capacitor...
- [0:32:55] So the capacitor impedance divided by
- [0:32:58] the resistor impedance plus the capacitor impedance times
- [0:33:04] the input voltage, which is the total voltage across the resistor in series with the capacitor.
- [0:33:09] Alright. So that's just gonna be in the numerator. We have one over j omega c.
- [0:33:14] And then in the denominator, we have r plus one over j omega c, and then that is going to be times
- [0:33:23] v sub s. Alright?
- [0:33:25] So in this form, right, we have fractions in the numerator, fractions in the denominator, so it's a little bit cumbersome to deal with. So to fix that,
- [0:33:35] we'll multiply by j omega c over j omega c. Okay.
- [0:33:40] And when we do that,
- [0:33:42] then what we get is,
- [0:33:45] that
- [0:33:46] v sub c is going to be just... In the numerator, we have one, and in the denominator, we have one plus j omega RC,
- [0:33:54] okay,
- [0:33:56] times
- [0:33:58] v sub s. Alright?
- [0:34:00] So now we have
- [0:34:02] the voltage across the capacitor, v sub c, in terms of the input voltage, v sub s, and, we just divide both sides by v sub s, then that'll be the transfer function. Okay. So,
- [0:34:15] now we're looking at...
- [0:34:17] Alright. Remember, this is the voltage gain
- [0:34:20] transfer function.
- [0:34:27] Okay. So,
- [0:34:29] this is... And we'll use a subscript c here to indicate that
- [0:34:34] we are talking about the transfer function when we take the output voltage across the capacitor,
- [0:34:39] not across the resistor. Okay. So that is
- [0:34:43] v sub c over
- [0:34:45] v sub s.
- [0:34:47] And from this expression here, right, we can see that this is just one over
- [0:34:53] one plus j
- [0:34:55] omega r c. Alright? If we want,
- [0:35:00] we can put that in, sort of the strictly speaking rectangular form by multiplying the numerator the denominator by,
- [0:35:09] one minus j omega RC. Right? The complex conjugate of the denominator.
- [0:35:15] Right? When we do that, that'll make the denominator purely real,
- [0:35:19] and what we get is,
- [0:35:21] one minus
- [0:35:23] j omega r c. And then in the denominator, we have one plus omega squared r squared c squared. Okay?
- [0:35:32] And, in either of these forms, right, either this form over here or this form over here, right, we can then take this transfer function
- [0:35:42] and calculate its magnitude
- [0:35:48] and its phase.
- [0:35:50] Okay. So any questions on how we got the transfer function before we look at the magnitude and the phase?
- [0:35:58] Okay.
- [0:35:59] So...
- [0:36:04] Right. It's pretty easy to calculate the magnitude (and?) the phase.
- [0:36:08] Right? The magnitude,
- [0:36:11] right, is just the magnitude of h sub c of omega. Alright?
- [0:36:16] And it's actually easiest to calculate it from this form over here. Right?
- [0:36:23] Right? We can take... If we have a rational function like this, a fraction, a complex fraction, the magnitude of the fraction is just the magnitude of the numerator divided by the magnitude of the denominator. Right? And the magnitude of the denominator here... Right? The magnitude of the numerator is just one.
- [0:36:40] For the denominator, the magnitude is the square root of the real part squared plus the imaginary part squared. Alright? And so,
- [0:36:48] we're gonna get (for?) the magnitude one over the square root of one plus
- [0:36:54] omega squared r squared
- [0:36:58] c squared. Right? That is the magnitude
- [0:37:01] of, the transfer function. And then the phase,
- [0:37:08] alright, we can get that from, say, over here.
- [0:37:12] Right? It is, the inverse tangent of the imaginary part divided by the real part. We can take the minus sign of the imaginary part and basically pull it outside of the inverse tangent (so?) we get minus
- [0:37:26] the inverse tangent of... And then it's just of omega (r?) c. Right? Because it's omega r c over one.
- [0:37:34] Okay. The other way that we could have gotten this is to look at this
- [0:37:39] form over here for the transfer function
- [0:37:42] and recognize that the phase of the denominator
- [0:37:46] is
- [0:37:47] the inverse tangent of omega RC.
- [0:37:51] And since this is in the denominator,
- [0:37:54] then
- [0:37:55] the (in...?) The the phase of the transfer function itself is just the negative of the phase of the denominator. Right? So minus the inverse tangent of omega RC.
- [0:38:06] Okay. So either way, this is what we get.
- [0:38:09] Okay. So any questions on
- [0:38:12] how we got the magnitude and the phase of the transfer function?
- [0:38:18] Okay. So let's kind of sketch these out, alright, to see what they look like.

## page 10  f_0211.jpg  on screen [0:38:20 – 0:40:33]
<sub>sharpness 1630, ink 2.2 %, colour 0.2</sub>

- [0:38:18] Okay. So let's kind of sketch these out, alright, to see what they look like.
- [0:38:25] If we look at the magnitude
- [0:38:29] of the transfer function,
- [0:38:32] okay, then
- [0:38:34] we can see that
- [0:38:36] {(I...?)}
- [0:38:37] Right? This is going to behave as a lowpass filter. Alright? So at (frequencies?)
- [0:38:44] approaching... As omega goes to zero,
- [0:38:47] the magnitude goes to one.
- [0:38:50] And as omega goes to infinity, the magnitude goes to zero. Okay. So
- [0:38:56] it starts at one here. It's a zero down here,
- [0:39:00] and it's going to look
- [0:39:06] something like this. Alright?
- [0:39:10] And then for the phase...
- [0:39:13] Okay. If we look at the phase, when omega is zero, then we have the inverse tangent of zero, which is zero. So the phase is zero at zero frequency.
- [0:39:23] And as omega goes to infinity,
- [0:39:25] alright, then we have the inverse tangent of infinity, which in radians is pi over two. And then we have a minus sign over here. So, the phase of the transfer function overall, goes to minus pi over two in radians as,
- [0:39:41] omega goes to infinity. So the phase
- [0:39:46] is gonna look something like this. Alright. So this is
- [0:39:50] the phase as a function of omega.
- [0:39:55] This is minus pi over two,
- [0:39:58] and it'll look
- [0:40:01] something like that. Okay.
- [0:40:04] So, that's kind of sketching out the magnitude and the phase of the transfer function.
- [0:40:10] What we also wanna do is,
- [0:40:13] to figure out
- [0:40:15] what is the
- [0:40:17] corner or cutoff frequency.
- [0:40:19] Right? So that'll be
- [0:40:21] the frequency at which
- [0:40:24] the magnitude, this expression here, is equal to one over root two. Right? Because the maximum value is one.
- [0:40:31] Okay. So we can easily figure that out.

## page 11  f_0231.jpg  on screen [0:40:33 – 0:43:02]
<sub>sharpness 2794, ink 3.9 %, colour 0.4</sub>
<sub>earlier states of this page: f_0219.jpg (0:42:05)</sub>

- [0:40:31] Okay. So we can easily figure that out.
- [0:40:34] Right? We just say that,
- [0:40:37] alright, the magnitude... The expression for the magnitude at omega c is one over the square root of one plus I, and then it's omega c squared
- [0:40:46] r squared
- [0:40:48] c squared.
- [0:40:50] Alright. This has to be one over the square root of two. Right? So if you look at this, you can see, obviously, this requires
- [0:40:58] that omega c times r times c is equal to one.
- [0:41:02] Right?
- [0:41:04] And so that means that omega c is equal to one over
- [0:41:08] r times c. Alright?
- [0:41:11] So that is,
- [0:41:12] the corner frequency or cutoff frequency. Right?
- [0:41:17] We can also
- [0:41:19] then figure out what the phase is
- [0:41:24] at the corner frequency. Right? And that is now... That is going to be minus
- [0:41:30] the inverse tangent,
- [0:41:32] and
- [0:41:33] omega c times r times c is just one. Right? So it's minus the inverse tangent of one.
- [0:41:39] What's the inverse tangent of one
- [0:41:41] in radians?
- [0:41:44] Right. Pi over four. So this is minus pi over four.
- [0:41:49] Okay. So
- [0:41:52] minus pi over four here.
- [0:41:57] At the corner frequency, the phase of the transfer function is minus pi over four. Okay.
- [0:42:04] So so this is the transfer function of the RC circuit when we have the output terminals across the capacitor. There are a couple things that we can note here.
- [0:42:14] Alright? One
- [0:42:16] is that...
- [0:42:19] Right? If we look at the
- [0:42:22] corner (cutoff?) frequency omega c, right, it's one over RC.
- [0:42:27] Right? And so this is one over just the RC time constant of that circuit. Right?
- [0:42:36] So tau here
- [0:42:38] is the RC time constant.
- [0:42:48] Okay, (of?)
- [0:42:50] the circuit.
- [0:42:53] Alright, where we have the resistor and the capacitor in series,
- [0:42:57] right, it sort of makes sense that that should be the case.
- [0:43:01] Alright? Because

## page 12  f_0235.jpg  on screen [0:43:02 – 0:43:04]
<sub>sharpness 2954, ink 4.2 %, colour 0.5</sub>

- [0:43:01] Alright? Because

## page 13  f_0288.jpg  on screen [0:43:04 – 0:44:51]
<sub>sharpness 2854, ink 4.0 %, colour 0.4</sub>
<sub>earlier states of this page: f_0238.jpg (0:43:05), f_0243.jpg (0:44:10), f_0246.jpg (0:44:10), f_0249.jpg (0:44:11), f_0258.jpg (0:44:12), f_0264.jpg (0:44:13)</sub>

- [0:43:05] if we go back to this circuit here, if we are
- [0:43:09] at low frequencies,
- [0:43:11] okay, then the impedance of the capacitor is high. Right? And so
- [0:43:17] we should expect to have a large value of the voltage across the capacitor, which is what we saw. If we think about it in terms of, you know, how rapidly
- [0:43:27] can,
- [0:43:28] say, the voltage across the capacitor respond if we are changing the voltage, right, then,
- [0:43:36] the time scale for the voltage of the capacitor to respond is basically r time c. Okay? And so if we are at frequencies that are lower than one over RC, right, so, low frequencies, then the voltage across the capacitor is able to respond in time as we're changing the input, and so we get a large responses over... Across the capacitor. If the voltage is changing very rapidly, then there's no time for the capacitor to respond, and so we'll get very little modulation of the voltage across the capacitor, and so VC will be low. Okay. So that's how we can understand
- [0:44:12] that.
- [0:44:14] And then,
- [0:44:16] alright, the other thing that we saw, quite obviously
- [0:44:20] is that if we take the output signal
- [0:44:26] to be the voltage across the capacitor,
- [0:44:29] then this circuit acts
- [0:44:31] as a lowpass filter.
- [0:44:37] Okay. And as we discussed, there are a variety of ways that that
- [0:44:41] you can understand that. So any questions on this?
- [0:44:47] Okay.
- [0:44:48] So the other possibility,

## page 14  f_0312.jpg  on screen [0:44:51 – 0:45:18]
<sub>sharpness 2635, ink 3.8 %, colour 0.5</sub>
<sub>earlier states of this page: f_0296.jpg (0:44:52), f_0301.jpg (0:44:53), f_0302.jpg (0:44:53), f_0309.jpg (0:45:18)</sub>

- [0:44:48] So the other possibility,
- [0:44:52] going back to,
- [0:44:53] just this RC filter circuit, is that, we have our output terminals across just the resistor. Right? It's not really interesting to take the output terminals to be across both of these things together because that voltage is just always the input. Right? So the other interesting possibility is to take the voltage,
- [0:45:13] to be across the resistor, right, to take the output terminals to be across the resistor. So now we wanna analyze what happens in that case.

## page 15  f_0331.jpg  on screen [0:45:18 – 0:45:21]
<sub>sharpness 3162, ink 4.5 %, colour 0.2</sub>
<sub>earlier states of this page: f_0320.jpg (0:45:19), f_0325.jpg (0:45:20)</sub>

- [0:45:13] to be across the resistor, right, to take the output terminals to be across the resistor. So now we wanna analyze what happens in that case.

## page 16  f_0353.jpg  on screen [0:45:21 – 0:47:10]
<sub>sharpness 3104, ink 4.5 %, colour 0.3</sub>
<sub>earlier states of this page: f_0350.jpg (0:46:26)</sub>

- [0:45:13] to be across the resistor, right, to take the output terminals to be across the resistor. So now we wanna analyze what happens in that case.
- [0:45:23] Okay. So this is now taking the voltage
- [0:45:26] across the resistor to do the output. And, again, (we?) can calculate that voltage using
- [0:45:32] voltage division. Alright? So, again,
- [0:45:39] by voltage division,
- [0:45:42] Alright. What happens here is that, right, the voltage across the resistor
- [0:45:46] is the impedance of the resistor
- [0:45:49] divided by the impedance
- [0:45:51] of the resistor plus the impedance of the capacitor
- [0:45:55] times the input voltage v sub s. So that's gonna be r
- [0:46:01] over r plus
- [0:46:03] one over j omega c times
- [0:46:07] v sub s.
- [0:46:08] And, again, alright, to deal with this fraction that we have in the denominator,
- [0:46:14] we can multiply the numerator and the denominator by
- [0:46:19] j omega c.
- [0:46:21] Alright. So we're just multiplying by one, so it's still gonna be the same,
- [0:46:25] but it makes it easier to,
- [0:46:28] deal with algebraically.
- [0:46:30] And if we do that, then what we get is
- [0:46:35] j omega RC in the numerator.
- [0:46:37] And then in the denominator, we have one plus
- [0:46:43] j omega RC, alright, times
- [0:46:48] v sub s. Right?
- [0:46:50] And we can take this
- [0:46:53] and,
- [0:46:54] determine what the magnitude of the transfer function
- [0:46:58] is and what the phase is.
- [0:47:04] Right? Or, actually, this is not quite there yet.

## page 17  f_0366.jpg  on screen [0:47:10 – 0:49:34]
<sub>sharpness 1335, ink 2.0 %, colour 0.2</sub>
<sub>earlier states of this page: f_0359.jpg (0:47:59), f_0365.jpg (0:49:33)</sub>

- [0:47:11] (Right?) now (we?) see that the
- [0:47:14] transfer function, right, we'll call it h sub r,
- [0:47:18] okay, of omega to remind us that, we're talking about the voltage across the resistor. So it's the output voltage, the voltage across the resistor divided by the input voltage (v?) sub s.
- [0:47:30] And,
- [0:47:32] should now... From this expression here, right, we can see this is just j omega (RC?)
- [0:47:37] over one plus
- [0:47:39] j omega RC.
- [0:47:41] And so this now,
- [0:47:45] we wanna write in terms of its magnitude
- [0:47:50] and phase.
- [0:47:51] Okay. So any questions on how we got the transfer function in this case?
- [0:47:56] Okay.
- [0:47:58] So
- [0:48:00] for this complex expression over here,
- [0:48:05] alright, we can calculate
- [0:48:07] its magnitude.
- [0:48:09] Alright? So,
- [0:48:11] looking at this expression, the magnitude... Right? Again, this is a (a?) complex fraction. So the magnitude of the complex fraction is going to be the magnitude of the numerator
- [0:48:21] divided by the magnitude of the denominator.
- [0:48:24] Right? The magnitude of the numerator is just omega RC,
- [0:48:31] and the magnitude of the denominator is the square root of one plus,
- [0:48:36] omega squared
- [0:48:38] r squared c squared.
- [0:48:40] Okay.
- [0:48:41] So this is the magnitude of the transfer function
- [0:48:44] and then the phase.
- [0:48:49] Okay, it's going to be
- [0:48:52] the magnitude of the numerator
- [0:48:54] minus the magnitude of the... Or sorry. The the phase of the numerator minus the phase of the denominator.
- [0:49:01] So the phase of the numerator
- [0:49:04] is what
- [0:49:07] (in?) radians?
- [0:49:08] Right. Pi over two
- [0:49:11] minus
- [0:49:13] the phase of the denominator. Right? What's the phase of the denominator?
- [0:49:22] Right. So it's...
- [0:49:24] So minus the inverse tangent of
- [0:49:27] omega RC.
- [0:49:29] Okay.
- [0:49:31] So these are the magnitude and the phase,
- [0:49:34] and

## page 18  f_0405.jpg  on screen [0:49:34 – 0:54:49]
<sub>sharpness 1648, ink 2.4 %, colour 0.2</sub>
<sub>earlier states of this page: f_0369.jpg (0:51:18), f_0378.jpg (0:53:00), f_0379.jpg (0:53:27), f_0391.jpg (0:54:47)</sub>

- [0:49:34] and
- [0:49:35] now we can plot
- [0:49:37] these out.
- [0:49:40] Right? If we look at the magnitude, m sub r of omega as a function of omega,
- [0:49:45] right, now we can see that, as omega goes to zero,
- [0:49:50] right, the magnitude,
- [0:49:52] goes to zero.
- [0:49:54] So here.
- [0:49:55] And then as omega goes to infinity,
- [0:49:58] the magnitude of the transfer function goes to one.
- [0:50:01] Alright?
- [0:50:02] So we have one up here.
- [0:50:06] So the transfer function is gonna look
- [0:50:10] sorta like this. Okay.
- [0:50:13] I... And then what we will eventually or shortly wanna do is to calculate the
- [0:50:19] quarter frequency,
- [0:50:22] alright, which we again define as the frequency at which the magnitude of the transfer function is equal to one over root two of its maximum value. Okay.
- [0:50:33] Before we calculate that, we'll look at the phase.
- [0:50:36] Alright. The phase here, when omega goes to zero, this inverse tangent is zero, so the phase will be pi over two. When omega goes to infinity, alright, we have the inverse tangent of infinity, which is pi over two, so the phase will go to zero.
- [0:50:51] Okay.
- [0:50:52] So for the phase...
- [0:50:57] Right. Phi sub r of omega. It's a function of omega. Then it's gonna go from
- [0:51:03] pi over two to zero,
- [0:51:08] and it's just gonna look something
- [0:51:13] like this.
- [0:51:15] Okay.
- [0:51:16] So
- [0:51:19] now we can come back to the magnitude
- [0:51:22] and calculate
- [0:51:23] the the cutoff frequency omega c. Alright? So what we wanna do then is to set
- [0:51:30] this expression for the magnitude at omega equal to omega c, set it equal to one over root two. Okay. So we're gonna have
- [0:51:39] omega c times r times c divided by the square root of one plus
- [0:51:45] omega c squared times r squared times c squared.
- [0:51:49] That's equal... Going to be equal to one over root two.
- [0:51:53] And, again, here, right, we can see that,
- [0:51:58] if omega c is equal to one over r c, we'll have one in the numerator, which is this, and we'll have the square root of one plus one or the square root of two in the denominator. Alright? So,
- [0:52:10] we can see again that this tells us that the cutoff frequency omega c is
- [0:52:17] just one over RC.
- [0:52:20] And then if we look at the phase
- [0:52:23] at the cutoff frequency,
- [0:52:26] right, this is pi over two minus,
- [0:52:30] the
- [0:52:32] the inverse tangent of
- [0:52:34] one. Right? The inverse tangent of one, from,
- [0:52:39] the other variant of this we know is pi over four. So, this is going to be pi over two minus pi over four, which is pi over four. Okay?
- [0:52:47] So
- [0:52:50] the phase at the cutoff frequency is pi over four. Alright?
- [0:52:57] So this is what the transfer function looks like
- [0:53:00] for,
- [0:53:02] the RC filter circuit if we take the output to be across the resistor.
- [0:53:07] And the things that we can notice here are, first, again,
- [0:53:14] Okay. Omega c is equal to... Right. It's one over the RC time constant
- [0:53:20] of the circuit.
- [0:53:23] Okay. And the explanation for it is basically the same as
- [0:53:27] what we had
- [0:53:29] for the
- [0:53:31] for the other variant where we took the output terminals across the capacitor.
- [0:53:35] And what we see here is that just looking at
- [0:53:40] the transfer function or, you know, thinking about the behavior of the components in the circuit as a function of frequency,
- [0:53:47] we can see that,
- [0:53:50] when the output terminals are connected across the resistor,
- [0:53:53] this is going to behave as
- [0:53:56] a highpass filter. Right? And and that happens basically because,
- [0:54:02] at high frequencies,
- [0:54:04] the impedance of the capacitor,
- [0:54:06] goes to zero. Right? It's very small, so all the voltage drop will be across the resistor. Right? And so that's why we have a large output voltage at high frequencies. Okay. So,
- [0:54:17] here, when we take the output
- [0:54:21] signal
- [0:54:23] to be the voltage across the resistor, then this acts
- [0:54:28] as a highpass
- [0:54:35] filter.
- [0:54:36] Okay. So any questions on
- [0:54:39] this?
- [0:54:42] Okay. So so that's a very simple example of how we calculate transfer functions.
- [0:54:49] And,

## page 19  f_0408.jpg  on screen [0:54:49 – 0:56:45]
<sub>sharpness 1604, ink 2.4 %, colour 0.2</sub>

- [0:54:49] And,
- [0:54:50] you know, as you saw from this, it can be very helpful to plot out what the magnitude and the phase
- [0:55:00] look like as a function of frequency.
- [0:55:03] Okay? And
- [0:55:05] it turns out that there's a very systematic way of doing this that, in particular, allows one to combine,
- [0:55:12] many different components. And, from the plots of how,
- [0:55:16] the
- [0:55:18] (circuit?) behaves as a function of frequency for sort of subparts of the circuit, we can easily construct what happens for the circuit as a whole. And the graphical tool that we use for this
- [0:55:31] will be, what we call Bode plots.
- [0:55:35] Okay. And the reading for this
- [0:55:39] is in
- [0:55:44] Ulaby et al, and it's section
- [0:55:47] nine dash three. Okay.
- [0:55:49] And the idea... The basic idea in a Bode plot is that instead of plotting everything on a linear scale,
- [0:55:58] what we do is we put the frequency on a log scale and also the magnitude on a log scale. Alright?
- [0:56:06] But we keep the phase on a linear scale. Alright? And then in addition,
- [0:56:11] the way, the Bode plot terminology is used in Ulaby,
- [0:56:16] and therefore, the way that we will use it here,
- [0:56:21] a version of those plots where we make kind of linear approximations to what the plots look like over specific ranges of frequency (will?) be what we strictly refer to as the Bode plot. And by making those linear approximations, it makes it very easy to combine
- [0:56:40] kind of the Bode plots for different subparts of the circuit to get the Bode plots Bode plot for the circuit as a whole. Okay? So the basic idea is that

## page 20  f_0409.jpg  on screen [0:56:45 – 0:57:36]
<sub>sharpness 1646, ink 2.2 %, colour 0.2</sub>

- [0:56:40] kind of the Bode plots for different subparts of the circuit to get the Bode plots Bode plot for the circuit as a whole. Okay? So the basic idea is that
- [0:56:51] Bode plots,
- [0:56:54] they're
- [0:56:55] essentially... They're log log plots.
- [0:56:58] So both axes on log scales
- [0:57:00] of,
- [0:57:02] the
- [0:57:04] magnitude of the transfer function
- [0:57:06] as a function of frequency.
- [0:57:09] And then
- [0:57:12] linear log plots.
- [0:57:15] So,
- [0:57:17] right, of the phase
- [0:57:21] versus the frequency. Right? So the phase, which is the vertical axis, is on a linear scale. The
- [0:57:28] frequency,
- [0:57:29] is the horizontal axis, is on a log scale. Okay?
- [0:57:33] And, these are very useful,

## page 21  f_0438.jpg  on screen [0:57:36 – 1:04:05]
<sub>sharpness 3344, ink 4.9 %, colour 0.2</sub>
<sub>earlier states of this page: f_0419.jpg (1:00:50), f_0426.jpg (1:01:12), f_0430.jpg (1:02:24)</sub>

- [0:57:38] okay, for
- [0:57:40] really visualizing
- [0:57:45] and thinking about,
- [0:57:52] in general, the frequency response of circuits.
- [0:58:01] Okay.
- [0:58:03] So
- [0:58:05] since we are going to be talking about, in particular,
- [0:58:09] the magnitude of the transfer function on a log scale,
- [0:58:13] then, it's also very helpful to have
- [0:58:18] a set of units that is kind of a natural set of units to use for,
- [0:58:24] for a log scale or at least a natural scaling. Okay? And this is something that,
- [0:58:31] I think you've probably seen in 03/2002 or 03/2002 h, and that is the decibel scale. Right? It's it's sort of the natural way of
- [0:58:41] quantifying,
- [0:58:43] what happens
- [0:58:45] when you're thinking about, quantities in terms of logs, which means that you're thinking really in terms of multiples
- [0:58:53] by which quantities change rather than,
- [0:58:55] sort of constant addition
- [0:58:58] or, you know, additive (changes?) to,
- [0:59:01] to quantities. So we wanna just review,
- [0:59:08] the decibel or dB scale.
- [0:59:12] Okay. What it means and how we use it. Alright?
- [0:59:16] So,
- [0:59:17] you may remember from three zero two or three zero two h that, when you use decibels,
- [0:59:22] really what that allows you to do is to easily
- [0:59:26] talk about and quantify
- [0:59:28] changes by quantities,
- [0:59:31] by constant factors, or equivalently (to?) talk about ratios
- [0:59:35] of
- [0:59:36] different quantities relative to some reference.
- [0:59:39] Okay. So
- [0:59:42] can perhaps recall, alright, that
- [0:59:47] decibels,
- [0:59:51] alright, or dB, these quantify
- [0:59:56] really the ratio,
- [1:00:00] and it's most commonly the ratio of power.
- [1:00:05] Right? It's... And it's really the ratio. Right? So (of?) power p, right, to some reference value.
- [1:00:16] We'll call p naught. Okay. And,
- [1:00:20] in the context of, electrical circuits,
- [1:00:24] then
- [1:00:26] often
- [1:00:27] that reference value p naught is equal to,
- [1:00:31] we take it to be one watt (or?)
- [1:00:34] sometimes if we talk about, say, dBm or something like that, maybe one
- [1:00:41] milliwatt.
- [1:00:42] Okay?
- [1:00:44] So,
- [1:00:46] if we are talking about ratios of power, right, to some reference value, then
- [1:00:54] it makes sense to define
- [1:00:59] what we call a power gain.
- [1:01:09] G. Alright?
- [1:01:11] And
- [1:01:13] that power gain
- [1:01:15] is just the power
- [1:01:17] divided by that reference value.
- [1:01:20] Okay?
- [1:01:21] And
- [1:01:23] in decibels...
- [1:01:24] So the power gain
- [1:01:27] in decibels is going to be, it's 10 times the log
- [1:01:32] of,
- [1:01:34] p over p naught. So it's 10 times
- [1:01:37] the log, and it's the log base 10
- [1:01:40] of p
- [1:01:42] over p naught. Alright? So this is how we define power gain in decibels.
- [1:01:48] Right? So every time you have a change in the power by a factor of 10,
- [1:01:55] right, the log
- [1:01:56] changes by one,
- [1:01:59] and then by multiplying by 10,
- [1:02:01] that makes it so that in decibels,
- [1:02:04] a change in the power by a factor of 10 corresponds to 10 decibels. Okay? And a change in the power by a factor of a 100
- [1:02:14] is 20 decibels
- [1:02:16] and so forth. Okay.
- [1:02:19] So,
- [1:02:21] essentially, what happens here is that each
- [1:02:25] 10 x change,
- [1:02:27] okay, in the power,
- [1:02:30] Right? It changes
- [1:02:33] g
- [1:02:34] in decibels
- [1:02:36] by
- [1:02:38] 10 dB.
- [1:02:40] Okay. So any questions on that basic idea?
- [1:02:45] Okay.
- [1:02:48] Now
- [1:02:49] we're not always
- [1:02:51] going to be working with or want to think about changes by a factor of 10. Sometimes
- [1:02:57] it's very useful to think about things doubling. Alright? So
- [1:03:03] if the power, say, doubles,
- [1:03:07] then
- [1:03:09] we take the log of two. Right? The log of two is around point three.
- [1:03:14] Okay? So a doubling of the power changes
- [1:03:20] the gain in decibels by point three times 10, which is three. Alright. So three decibels corresponds to a change in the power by a factor of two. Okay. So, basically,
- [1:03:33] since the log
- [1:03:35] base 10 of two
- [1:03:37] is approximately equal to point three zero,
- [1:03:40] right, then
- [1:03:43] a two x change,
- [1:03:47] say doubling or halving
- [1:03:49] in the power,
- [1:03:53] it changes
- [1:03:55] power gain in dB
- [1:03:59] by
- [1:04:00] around three decibels.
- [1:04:02] Okay.
- [1:04:05] And so, for example,

## page 22  f_0447.jpg  on screen [1:04:05 – 1:05:52]
<sub>sharpness 2105, ink 3.1 %, colour 0.2</sub>
<sub>earlier states of this page: f_0445.jpg (1:05:51)</sub>

- [1:04:05] And so, for example,
- [1:04:07] if we have a,
- [1:04:11] say, lowpass filter,
- [1:04:13] then, at the cutoff frequency,
- [1:04:16] the, transfer function will have been,
- [1:04:20] it's reduced by three dB compared to its maximum value. Alright?
- [1:04:26] Now
- [1:04:27] the other thing that we have to notice and be careful of here is that this power gain g is defined as a ratio of powers.
- [1:04:37] But when
- [1:04:38] we
- [1:04:39] are talking about transfer functions,
- [1:04:42] we're talking about most commonly voltage, but sometimes current,
- [1:04:48] and power is proportional to the square of the voltage or the current or, you know, the voltage times the current. So,
- [1:04:58] if we're looking at ratios of voltage or current, then the way that we convert that to decibels is a little bit different, okay, to take into account that squared relationship.
- [1:05:09] Right? So the other thing that we have to notice here is that
- [1:05:15] since the power
- [1:05:18] is proportional to...
- [1:05:20] Right? It's the voltage,
- [1:05:22] right, voltage times the complex conjugate of, the current.
- [1:05:28] And
- [1:05:29] if we're talking about linear circuits,
- [1:05:34] then
- [1:05:36] the voltage is proportional to
- [1:05:39] the current. Right? So, basically, the power is going as the voltage squared or the current squared,
- [1:05:48] then it is also going to be the case that...

## page 23  f_0466.jpg  on screen [1:05:52 – 1:10:36]
<sub>sharpness 2504, ink 3.5 %, colour 0.2</sub>
<sub>earlier states of this page: f_0452.jpg (1:07:12), f_0460.jpg (1:07:13)</sub>

- [1:05:54] Alright. The power gain in dB
- [1:05:57] (is?) going to be 10
- [1:05:59] times log base 10 of
- [1:06:02] the power over some reference.
- [1:06:04] So that's going to be 10 times
- [1:06:07] the log base 10 of,
- [1:06:10] say, the voltage
- [1:06:13] squared over,
- [1:06:16] the reference voltage squared.
- [1:06:18] And so that's going to be 20.
- [1:06:22] Alright. These will be magnitudes
- [1:06:24] times
- [1:06:26] the log base 10 of,
- [1:06:30] say, the magnitude of the voltage as a phasor over
- [1:06:35] the corresponding reference,
- [1:06:39] and it will also be 20 times
- [1:06:43] the log base 10 of,
- [1:06:46] say, the same type of ratio for
- [1:06:50] currents.
- [1:06:51] Okay. So if we're talking about ratios of voltage or current, then it's a factor of 20 in front, not a factor of 10, and that's because the power goes to the voltage squared.
- [1:07:02] Okay. So any questions on that?
- [1:07:07] Okay.
- [1:07:09] So
- [1:07:13] let's now start to think about more generally
- [1:07:16] what transfer functions
- [1:07:19] are going to look like mathematically
- [1:07:21] as a function of frequency. Alright? So in general...
- [1:07:28] Alright. If we...
- [1:07:30] Say if we're calculating some transfer function, right, for a linear circuit,
- [1:07:35] the transfer function will be,
- [1:07:40] in general,
- [1:07:42] of the following mathematical form.
- [1:07:45] Alright? It's going to be,
- [1:07:49] a rational function of frequency. So we're gonna have
- [1:07:53] a numerator,
- [1:07:54] which is a function of frequency (divided?) by a denominator,
- [1:07:58] which is a function of frequency. We're gonna have to convert that
- [1:08:03] to (corresponding?) magnitude
- [1:08:08] and phase. Alright?
- [1:08:12] And
- [1:08:14] the numerator... Right? I'm writing this as a capital n. I'm putting the serifs on there to emphasize this as a capital,
- [1:08:22] letter. So n of omega
- [1:08:24] and
- [1:08:25] d of omega. Right? We put the twiddles there to remind ourselves that these are complex functions,
- [1:08:33] and they are,
- [1:08:35] going to be
- [1:08:39] polynomial functions
- [1:08:43] of,
- [1:08:45] in general, of j omega. Alright? And, you know, basically, the reason it works out that way is because,
- [1:08:54] when we are relating currents and voltages to each other, they're typically related to each other for a given component by,
- [1:09:03] the impedance of that component. And the impedances always have, right, well, (the?) resistor is just r. It's real. But then in terms of frequency, the impedances always have j and omega together. Right? For a capacitor, one over j omega c. For an inductor, j omega l. Right? So whenever we get the frequency
- [1:09:22] in there, we're also gonna get this factor of j, and we'll see later when we talk about
- [1:09:27] Laplace transforms. Right? Why having j
- [1:09:32] omega turns out to be a natural combination and useful combination to work with, and they'll end up being polynomials. Right? (Ration...?) Polynomials in the numerator and in the denominator. So a rational function (basically?) because,
- [1:09:46] know, you say if you're adding together a bunch of currents or voltages that are related to the other by impedances, then you're gonna get,
- [1:09:55] you know, sort of a
- [1:09:58] a linear function of
- [1:10:01] {(constant?)}
- [1:10:02] one over j omega and j omega. Right? And then when you manipulate that algebraically,
- [1:10:08] right, you might get... You know, you get something like that in the numerator,
- [1:10:12] and then,
- [1:10:14] you know, you might get (this...?) Some polynomial function of j omega times,
- [1:10:19] some voltage is equal to some other polynomial times current or something like that. And then, to solve for that voltage or, you know, time some other voltage, solve for that voltage, you have to divide by that first polynomial. That's how you get this rational function. Okay. So that's... This is kind of the natural mathematical form that we will get for

## page 24  f_0480.jpg  on screen [1:10:36 – 1:14:24]
<sub>sharpness 2279, ink 3.0 %, colour 0.2</sub>
<sub>earlier states of this page: f_0475.jpg (1:12:32)</sub>

- [1:10:19] some voltage is equal to some other polynomial times current or something like that. And then, to solve for that voltage or, you know, time some other voltage, solve for that voltage, you have to divide by that first polynomial. That's how you get this rational function. Okay. So that's... This is kind of the natural mathematical form that we will get for
- [1:10:39] transfer function.
- [1:10:41] Oh, was there a question?
- [1:10:46] Okay.
- [1:10:48] I thought I heard something. (I?) (definitely?)
- [1:10:51] heard that. I (think?) someone (on?) Zoom (maybe.?) Excellent. Yeah. (You?) did. Okay. So, yeah, so, anyway,
- [1:10:58] yeah, if if there are questions on Zoom, as usually, you can, type in (into?) the chat or you can just, speak up.
- [1:11:07] So we're gonna have,
- [1:11:10] right, the magnitude
- [1:11:12] of the transfer function is then just going to be...
- [1:11:16] Alright. It's the magnitude of
- [1:11:20] this rational function.
- [1:11:22] Okay.
- [1:11:24] And
- [1:11:27] in dB,
- [1:11:29] alright, this is going to be 20 times
- [1:11:33] the log base 10 of
- [1:11:36] the magnitude of the numerator
- [1:11:39] minus
- [1:11:40] 20 times
- [1:11:42] log base 10,
- [1:11:44] the magnitude of the
- [1:11:48] denominator.
- [1:11:50] Okay.
- [1:11:51] And so you can start to see, right, if you have the numerator and the denominator as rational functions,
- [1:11:58] or as polynomial functions of j omega,
- [1:12:02] then
- [1:12:03] if we can figure out, well, what are the typical
- [1:12:07] factors,
- [1:12:08] right, that will go into the numerator or into the denominator in different circumstances,
- [1:12:14] then,
- [1:12:15] basically, by adding or subtracting them, we can get,
- [1:12:19] the magnitude
- [1:12:21] on the dB scale of the transfer function as a whole. And that will be a large part of,
- [1:12:29] you know, what makes the Bode plots,
- [1:12:32] particularly useful is that since you're plotting things on a log scale for the magnitude, you can add, or subtract,
- [1:12:39] different contributions,
- [1:12:41] very easily, corresponding to different factors.
- [1:12:44] Okay. So that's the idea of what we're going to want to do. We're gonna start introducing
- [1:12:49] the typical factors that you get in
- [1:12:53] the numerator or the denominator of a transfer function, and then with the tool of Bode plots, we can easily combine them. Okay.
- [1:13:00] So, just to give you a little preview of this. Right? Let's suppose...
- [1:13:07] Alright. The first
- [1:13:09] example
- [1:13:10] that we'll look at is where we have... Let's suppose we have a transfer function where the numerator
- [1:13:17] has a factor
- [1:13:18] that is of the form one plus
- [1:13:22] j omega over some constant we'll call omega z
- [1:13:27] to the nth power. Right? So this n over here is not the same as this n of omega. That's why we have the (series?) over here to distinguish them. And let's suppose the denominator
- [1:13:38] is just one.
- [1:13:40] Okay.
- [1:13:42] So,
- [1:13:44] if we look at this, then
- [1:13:48] the magnitude
- [1:13:52] in dB,
- [1:13:54] right, it's gonna be 20 n,
- [1:13:56] alright, times
- [1:13:59] the log.
- [1:14:01] We're always gonna be working with log base tens here. So when I write log LOG, we're gonna always assume that that is log base 10 even though we're not gonna write the, 10 subscript explicitly anymore.
- [1:14:14] So it'll be one plus... The magnitude of one plus,
- [1:14:17] j omega over omega
- [1:14:21] z,
- [1:14:22] And the phase
