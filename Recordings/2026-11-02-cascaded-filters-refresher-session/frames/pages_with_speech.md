# 2026-00-00-cascaded-filters: board pages with the speech that accompanied them

55 distinct pages from 351 page-final frames. A section's image is the LAST frame of the page (most ink); earlier states of the same page are listed under it. Confidence marks: `(word?)` word < 0.55; `{…}` utterance mean < 0.7. Times are recording time.

## page 01  f_0003.jpg  on screen [0:00:00 – 0:02:24]
<sub>sharpness 1235, ink 4.8 %, colour 2.1</sub>

- [0:00:03] Okay. So in this recording, we are going to go through a couple examples
- [0:00:08] of
- [0:00:09] cascaded filter circuits. One example will be an analysis,
- [0:00:15] and the other example
- [0:00:17] will be a design
- [0:00:19] problem. Okay. So the first example
- [0:00:25] that we're going to look at here is that of cascaded
- [0:00:33] bandpass filter.
- [0:00:38] Okay. And this is going to be an analysis
- [0:00:41] of a circuit. Alright? And so what we're going to do is we're going to take the
- [0:00:48] active lowpass filter and the active highpass filter, the circuits that we discussed in class,
- [0:00:54] and we're going to cascade them. That is we're gonna take the output of one and use it as the input for the other. And what we will see is that we can use this approach
- [0:01:06] with appropriate selection of the
- [0:01:11] corner frequencies for each in order to make a bandpass filter. Alright? So the circuit that we're going to look at is the following. We have our input voltage here, (v?) sub s,
- [0:01:27] that's connected through a one k resistor,
- [0:01:33] okay, to
- [0:01:35] our first op amp. Alright? So this is op amp number one.
- [0:01:41] The noninverting input is (connected?) to ground,
- [0:01:44] and then we have the output. We'll call that voltage v one. And then
- [0:01:49] our feedback connection,
- [0:01:51] okay, is going to be
- [0:01:55] a 10 k resistor
- [0:01:57] in parallel
- [0:02:01] with a capacitor, nine
- [0:02:04] nanofarads.
- [0:02:06] Okay. Then that's connected to the output. So this, you may recall,
- [0:02:11] is
- [0:02:14] our lowpass filter. Okay?
- [0:02:17] And so that's going to let low frequencies through,
- [0:02:20] and it'll
- [0:02:22] cut off high frequencies.
- [0:02:24] Yep. K. And what we wanna do then is to connect that,

## page 02  f_0081.jpg  on screen [0:02:24 – 0:11:46]
<sub>sharpness 2987, ink 7.8 %, colour 2.3</sub>
<sub>earlier states of this page: f_0004.jpg (0:03:48), f_0007.jpg (0:04:48), f_0008.jpg (0:06:08), f_0011.jpg (0:08:07), f_0034.jpg (0:09:34), f_0039.jpg (0:09:52), f_0041.jpg (0:09:52), f_0052.jpg (0:10:12), f_0055.jpg (0:10:12), f_0059.jpg (0:10:33), f_0067.jpg (0:11:22), f_0073.jpg (0:11:23), f_0077.jpg (0:11:24), f_0078.jpg (0:11:24), f_0080.jpg (0:11:46)</sub>

- [0:02:22] cut off high frequencies.
- [0:02:24] Yep. K. And what we wanna do then is to connect that,
- [0:02:30] take the output of that
- [0:02:33] subcircuit,
- [0:02:34] and use it as the input
- [0:02:37] for a highpass filter,
- [0:02:39] which I remember
- [0:02:42] has the following configuration.
- [0:02:46] Okay. So we have
- [0:02:49] our op amp number two.
- [0:02:51] The noninverting input is again connected to ground. Right? And we'll have... This time, it'll be a 12 k resistor
- [0:03:00] and,
- [0:03:01] again, a nine nanofarad capacitor.
- [0:03:04] And then we will have our final
- [0:03:08] output coming from this second op amp. So this will be our output voltage v out.
- [0:03:16] Okay?
- [0:03:17] And
- [0:03:19] we're going to have, for our feedback connection,
- [0:03:24] a 96
- [0:03:27] (kilo?) ohm resistor. Alright? So this
- [0:03:33] is our highpass
- [0:03:36] filter sub circuit. Okay? And so what we want is to have these together to show that this will work as a bandpass filter. Okay?
- [0:03:47] So in order to analyze this circuit, we're going to use the same approach that we used for multiple op amp circuits earlier in the semester. Alright? That is we start off by analyzing the behavior of the circuit, the op amp that is closest to the input. So we're gonna analyze
- [0:04:05] the behavior of this lowpass filter circuit first. Once we use that... Once we do that to get v one, then we will take that as the input for the second
- [0:04:17] (cert...?) Subcircuit over here with op amp number two. So let's look at the part of the circuit with
- [0:04:25] op amp number one. Right? That is the lowpass
- [0:04:30] filter circuit.
- [0:04:34] Okay. So for this circuit, remember from what we discussed in class that
- [0:04:41] the
- [0:04:44] corner frequency, right, the... Or the frequency rather of the...
- [0:04:48] We're going to have a
- [0:04:51] poll here, and the frequency of the poll is going to be
- [0:04:56] the
- [0:04:58] {RC}
- [0:04:59] time... One over (other?) RC time constant of this resistor combined with this capacitor. Right? The 10 kilohm resistor combined with the nine nanofarad capacitor. So we'll call that
- [0:05:12] omega
- [0:05:14] naught
- [0:05:15] one, right, for the first
- [0:05:18] op amp, and that is going to be one over
- [0:05:24] 10 kiloohms
- [0:05:25] times nine
- [0:05:27] nanofarads.
- [0:05:28] And this will end up being... Right. 10 k is 10 to the fourth. Nine nanofarads is nine times 10 to the minus nine farads.
- [0:05:37] So we have, in the denominator, nine times 10 to the minus five.
- [0:05:42] So that becomes one ninth
- [0:05:45] times 10 to the fifth
- [0:05:49] radians per second,
- [0:05:51] which is about
- [0:05:54] 11.1
- [0:05:56] times
- [0:05:57] 10 to the third
- [0:06:01] radians per second. Okay.
- [0:06:05] Now what
- [0:06:07] we will also do is we will calculate
- [0:06:10] the
- [0:06:12] equivalent impedance
- [0:06:14] of this...
- [0:06:16] The equivalent feedback impedance over here. So that is going to be impedance z. We'll call it z f one. Okay?
- [0:06:24] And
- [0:06:27] z f one, right, the
- [0:06:29] feedback impedance associated with the first op amp that we have over here. Okay?
- [0:06:36] We have the resistor and the capacitor in parallel. So the equivalent impedance is just going to be the product of those two impedances divided by the sum, right, since they're in parallel. So it's going to be
- [0:06:50] 10 kilo ohms times one over j omega times nine
- [0:06:56] nanofarads
- [0:06:57] divided by
- [0:06:59] 10 kiloohms plus
- [0:07:01] one over j times omega times nine
- [0:07:04] nanofarads.
- [0:07:05] Alright?
- [0:07:07] And
- [0:07:08] if we take this and we multiply,
- [0:07:12] I'll write it out explicitly here. We'll multiply this by j omega times nine nanofarads
- [0:07:19] divided by j omega times nine
- [0:07:22] nanofarads.
- [0:07:24] Okay? Then what we get in the numerator is just 10 kiloohms.
- [0:07:29] And then in the denominator, we get one plus
- [0:07:32] j omega times
- [0:07:35] 10 kiloohms
- [0:07:39] times nine nanofarads.
- [0:07:41] That becomes
- [0:07:43] 10 kilo ohms
- [0:07:44] over
- [0:07:46] one plus j
- [0:07:48] omega
- [0:07:49] over omega zero one. Right? Because omega zero one is one over 10 k times nine nanofarads,
- [0:07:56] and so that's
- [0:07:57] one over this factor over here. Alright? So that's how we get this feedback impedance
- [0:08:04] for
- [0:08:05] op amp number one.
- [0:08:07] Okay. And then once we have that,
- [0:08:09] alright, we know from our analysis of
- [0:08:13] the lowpass
- [0:08:15] active filter from before or just remembering, right, this is basically like... It has the same topology as an inverting amplifier.
- [0:08:24] So if this were just a resistor, then we know... And we called it, say, RF, and we (called?) this RS, then we know that
- [0:08:32] the output voltage, which in this case is v one, is just going to be minus RF over RS
- [0:08:38] times Versus
- [0:08:40] So here,
- [0:08:42] where
- [0:08:43] now we have a feedback impedance,
- [0:08:45] then the output voltage of that op amp v one is going to be simply minus
- [0:08:51] the feedback impedance
- [0:08:53] (z?) f one that we just calculated divided by
- [0:08:57] the input resistance, which is going to be one kilo ohm,
- [0:09:02] okay,
- [0:09:03] times
- [0:09:05] {(the?) s.}
- [0:09:07] And if we take this and divide it by one kilo ohm, then we just get 10. Right? We have the minus sign, and we have 10 in the numerator, and then we have one plus j omega over omega zero one in the denominator times
- [0:09:25] (v?) s. Okay. So this is what we have for v one.
- [0:09:31] Okay? And that is going to be our
- [0:09:34] input voltage,
- [0:09:36] okay, for
- [0:09:38] this second
- [0:09:40] subcircuit over here, which is the active highpass filter circuit. Alright? And so now let's analyze the behavior of that part of the circuit with v one as its input.
- [0:09:53] Okay. So now we're looking at
- [0:09:57] op amp number two,
- [0:10:01] which behaves as a highpass filter.
- [0:10:05] Okay?
- [0:10:06] And
- [0:10:10] the frequency associated with that, if you remember from our analysis in class, right, the key
- [0:10:17] frequency here, the frequency of
- [0:10:21] both a zero and a pole that we have... Or, actually, the frequency of the pole that we have in this case is going to be one over the RC time constant associated with the 12 k resistor and the nine nanofarad
- [0:10:34] capacitor. Right? So that frequency is going to be one over
- [0:10:40] 12 kilohms times
- [0:10:44] nine nanofarads.
- [0:10:45] Okay. So that is one over...
- [0:10:48] 12 times nine is a 108. Right? And then we have kilo
- [0:10:53] times nano in the denominator. That's 10 to the three times 10 to the minus nine. That's 10 to the minus six in the denominator. That becomes 10 to the
- [0:11:03] six
- [0:11:05] radians per second, or this is approximately 9.26
- [0:11:11] times 10 to the three
- [0:11:16] radians per second. Alright? That's the frequency of the pole in the highpass filter. Alright? And,
- [0:11:24] again,
- [0:11:25] alright, this has basically the topology
- [0:11:29] of the inverting
- [0:11:31] op amp amplifier.
- [0:11:33] Right? So the output voltage v m is going to be just minus 96 k over
- [0:11:40] the impedance of this resistor and capacitor in series times the input voltage v one.

## page 03  f_0133.jpg  on screen [0:11:46 – 0:16:08]
<sub>sharpness 1630, ink 5.4 %, colour 2.1</sub>
<sub>earlier states of this page: f_0091.jpg (0:11:47), f_0092.jpg (0:11:47), f_0097.jpg (0:12:45), f_0101.jpg (0:14:36), f_0114.jpg (0:15:28), f_0125.jpg (0:15:41), f_0129.jpg (0:15:42)</sub>

- [0:11:40] the impedance of this resistor and capacitor in series times the input voltage v one.
- [0:11:47] Okay. So v out,
- [0:11:51] in this case, is going to be minus
- [0:11:54] 96 kilohms
- [0:11:56] divided by... And then that series combination
- [0:12:00] is 12 kilohms
- [0:12:01] plus
- [0:12:03] one over j omega times nine nanofarads.
- [0:12:06] Right? And that's going to be times the input voltage v one.
- [0:12:11] Okay?
- [0:12:12] So now here,
- [0:12:14] what we're going to do is
- [0:12:16] (in?) order to simplify that fraction in the denominator, we're gonna multiply by j omega times nine nanofarads
- [0:12:24] over j omega times nine
- [0:12:28] nanofarads.
- [0:12:29] Right?
- [0:12:30] And then we are going to
- [0:12:33] multiply and divide by 12
- [0:12:38] kilohms.
- [0:12:39] Okay.
- [0:12:41] And we'll see why that's a useful thing to do in a minute. Alright? If we do that,
- [0:12:46] then we're gonna have this minus sign over here. Right? That's carrying over the minus sign from the line above.
- [0:12:54] And then in the numerator, alright, we're going to have
- [0:12:58] j times omega,
- [0:13:00] alright,
- [0:13:01] times
- [0:13:02] nine nanofarads
- [0:13:04] times 12 kilohms. Right? So times
- [0:13:08] nine nanofarads, this is times, times 12
- [0:13:13] kiloohms.
- [0:13:14] Right? And then in the denominator, we're going to have
- [0:13:18] one
- [0:13:20] plus j omega
- [0:13:23] times,
- [0:13:24] again,
- [0:13:26] nine nanofarads
- [0:13:28] times 12
- [0:13:30] kiloohms.
- [0:13:31] Alright?
- [0:13:32] And then... Right. So now we've used up in the numerator this j omega nine nanofarads and 12 k.
- [0:13:40] We have this 96 k left over. So then we're gonna have
- [0:13:45] 96 kiloohms.
- [0:13:47] And then in the denominator,
- [0:13:49] right, we (multiply?) through by this j omega nine nanofarads
- [0:13:53] {with}
- [0:13:54] this expression over here to get this. We have this 12 k left over. So we have 12 k
- [0:14:00] in the denominator.
- [0:14:02] Right?
- [0:14:03] Now over here,
- [0:14:06] alright, this
- [0:14:08] is just eight. Right? 96 over 12 is eight.
- [0:14:11] And then remember,
- [0:14:13] omega zero two is equal to one over
- [0:14:17] 12 kiloohms times nine
- [0:14:20] nanofarads.
- [0:14:21] And so over here in the numerator, this nine nanofarads times 12 kiloohms is one over omega zero two. And down here, this nine nanofarad times 12 kilo ohms is also one over omega zero two. So what we get finally
- [0:14:36] is... And this is all times
- [0:14:40] v one. Okay? So what we get then is we have
- [0:14:45] eight.
- [0:14:47] Alright. That's this eight over here times
- [0:14:51] j omega over omega zero two
- [0:14:55] divided by one plus
- [0:14:58] j omega
- [0:14:59] over omega zero two
- [0:15:01] times
- [0:15:03] v one.
- [0:15:04] Okay?
- [0:15:06] But v one
- [0:15:08] is
- [0:15:10] given by this expression up here. Right? Minus 10 over one plus j omega over omega zero one times v s. So...
- [0:15:18] And then we have a
- [0:15:20] minus sign over here. Alright? That's carrying over this minus sign from up here. So now
- [0:15:26] if we take that expression above,
- [0:15:31] alright, this expression here, and plug it in down here for v one, then this negative sign and this negative sign will cancel out. Right?
- [0:15:40] And what we get
- [0:15:42] is...
- [0:15:45] Alright. We have eight j omega over omega zero two
- [0:15:50] divided by one plus j omega over omega zero two
- [0:15:56] times 10
- [0:15:58] over one plus j omega over omega zero one
- [0:16:02] times
- [0:16:03] the input voltage (v?) s. Alright?
- [0:16:08] And

## page 04  f_0142.jpg  on screen [0:16:08 – 0:18:04]
<sub>sharpness 2477, ink 7.0 %, colour 2.3</sub>
<sub>earlier states of this page: f_0135.jpg (0:17:12), f_0136.jpg (0:17:12)</sub>

- [0:16:08] And
- [0:16:09] {(then,?)}
- [0:16:10] finally, that gives us the transfer function
- [0:16:14] h of omega, right, which is v out
- [0:16:20] over
- [0:16:21] v s. Okay?
- [0:16:23] And that, right, since this is v out
- [0:16:27] over here, right, then the transfer function is just the product of these two factors here in the parentheses.
- [0:16:33] Okay. So that's going to be
- [0:16:36] 80.
- [0:16:37] Right? That's the eight times 10 over here. Then we have
- [0:16:41] times j omega over omega zero two.
- [0:16:45] Alright?
- [0:16:47] That's the rest of the numerator over here.
- [0:16:51] Then we have
- [0:16:53] one over one plus
- [0:16:54] j omega
- [0:16:56] over omega zero two.
- [0:16:59] Alright. That's,
- [0:17:01] this denominator over here
- [0:17:03] times one over one plus j omega over omega zero one.
- [0:17:08] Okay.
- [0:17:10] And
- [0:17:11] that's everything.
- [0:17:12] And so what we see here is that we have... Right. We have a constant.
- [0:17:20] Alright. This term over here, right, we can choose whether to include the omega zero two either here or in the constant. It doesn't really matter, which we do. This is a pole
- [0:17:32] at
- [0:17:34] the origin.
- [0:17:42] Okay. Then
- [0:17:44] this factor of... Or sorry. This is a zero at the origin.
- [0:17:52] Okay. And then over here, we have a (poll?)
- [0:17:56] at
- [0:17:59] omega zero two. Alright. Omega zero two, remember, was we worked out
- [0:18:04] the numerical value up here. It was 9.26

## page 05  f_0147.jpg  on screen [0:18:04 – 0:18:05]
<sub>sharpness 2537, ink 7.0 %, colour 2.5</sub>

- [0:17:59] omega zero two. Alright. Omega zero two, remember, was we worked out
- [0:18:04] the numerical value up here. It was 9.26

## page 06  f_0158.jpg  on screen [0:18:05 – 0:18:11]
<sub>sharpness 2399, ink 6.7 %, colour 2.1</sub>
<sub>earlier states of this page: f_0155.jpg (0:18:10)</sub>

- [0:18:04] the numerical value up here. It was 9.26
- [0:18:08] times 10 to the minus three radians per second. Right? So this is

## page 07  f_0159.jpg  on screen [0:18:11 – 0:18:11]
<sub>sharpness 2246, ink 6.5 %, colour 2.1</sub>

- [0:18:08] times 10 to the minus three radians per second. Right? So this is

## page 08  f_0160.jpg  on screen [0:18:11 – 0:18:11]
<sub>sharpness 1810, ink 5.8 %, colour 2.1</sub>

- [0:18:08] times 10 to the minus three radians per second. Right? So this is

## page 09  f_0177.jpg  on screen [0:18:11 – 0:18:30]
<sub>sharpness 2378, ink 6.8 %, colour 2.4</sub>
<sub>earlier states of this page: f_0171.jpg (0:18:29), f_0172.jpg (0:18:29), f_0173.jpg (0:18:29)</sub>

- [0:18:08] times 10 to the minus three radians per second. Right? So this is
- [0:18:13] 9.26 times
- [0:18:15] 10 to the minus three
- [0:18:19] radians per second. And then this term over here
- [0:18:24] is a pole at omega zero one, right, which we worked out

## page 10  f_0189.jpg  on screen [0:18:30 – 0:18:37]
<sub>sharpness 2856, ink 7.5 %, colour 2.6</sub>
<sub>earlier states of this page: f_0183.jpg (0:18:31)</sub>

- [0:18:32] up here is 11.1
- [0:18:35] times 10 to the third radians per second.

## page 11  f_0197.jpg  on screen [0:18:37 – 0:18:38]
<sub>sharpness 2524, ink 7.0 %, colour 2.1</sub>
<sub>earlier states of this page: f_0192.jpg (0:18:37), f_0195.jpg (0:18:38)</sub>

- [0:18:35] times 10 to the third radians per second.

## page 12  f_0259.jpg  on screen [0:18:38 – 0:25:51]
<sub>sharpness 2964, ink 7.7 %, colour 2.4</sub>
<sub>earlier states of this page: f_0210.jpg (0:18:52), f_0226.jpg (0:24:52), f_0232.jpg (0:24:53), f_0233.jpg (0:24:53), f_0236.jpg (0:24:54), f_0243.jpg (0:24:56), f_0245.jpg (0:24:56), f_0246.jpg (0:24:56), f_0250.jpg (0:24:57), f_0256.jpg (0:25:49), f_0257.jpg (0:25:51), f_0258.jpg (0:25:51)</sub>

- [0:18:35] times 10 to the third radians per second.
- [0:18:39] Sorry. This is plus three over here. This is 11.1
- [0:18:43] times 10 to the third
- [0:18:47] radians per second. Okay.
- [0:18:50] So
- [0:18:51] this is the full transfer function
- [0:18:53] for, this cascaded bandpass filter.
- [0:18:58] And so what we wanna do now is to construct
- [0:19:02] We'll just look at the Bode magnitude plot.
- [0:19:08] Right? Because that's, the plot that will really show us that this is indeed a bandpass filter.
- [0:19:19] Okay. So we're gonna plot the magnitude.
- [0:19:25] I'll write it explicitly as the magnitude of
- [0:19:28] frequency
- [0:19:30] in dB.
- [0:19:32] Okay? And then it'll be a function of
- [0:19:36] frequency.
- [0:19:37] Alright?
- [0:19:38] And
- [0:19:40] we
- [0:19:43] have omega zero two, right, as the... As one pole frequency
- [0:19:47] and then
- [0:19:49] omega zero one as the other pole frequency. Right? These two values here. You can see that, actually, omega zero one is greater than omega zero two. Okay.
- [0:19:59] So now,
- [0:20:02] alright, what we have is
- [0:20:05] the following. Alright?
- [0:20:07] We're going to...
- [0:20:12] If we look at the behavior of this, for frequencies that are less
- [0:20:17] than omega zero two, okay, then what happens is that we have this constant 80 times
- [0:20:25] j omega over omega zero two times
- [0:20:29] one over... And then this is gonna be in the low frequency limit, so it's one over one. And then this is also gonna be in the low frequency limit, so it's one over one. So this is just going to go as j times omega, right, or omega to the first power. So we're going to have a slope here
- [0:20:48] of...
- [0:20:51] {(Mark?) these}
- [0:20:54] frequencies here.
- [0:20:56] K. So we're gonna have a slope here
- [0:20:59] of 20 dB
- [0:21:04] per decade.
- [0:21:05] Okay.
- [0:21:06] Now
- [0:21:08] between omega zero two and omega zero one, Right? We're gonna have j omega over here.
- [0:21:15] And then here, this term is going to be in the high frequency limit. Right? So it's going to be...
- [0:21:22] This is going to behave approximately as one over j omega or, actually,
- [0:21:27] one over j omega over omega zero two.
- [0:21:30] This term over here, since we're still below omega zero one, is going to behave
- [0:21:36] in its low frequency limit, so it's just going to be one. So we have j omega over omega zero two over j omega over omega zero two. That's just one, right, times this constant.
- [0:21:47] So that's constant. It has no dependent on... Dependence on frequency,
- [0:21:52] and it's going to be like this. Okay? It'll be flat.
- [0:21:58] And, in fact, we can see then, right, that
- [0:22:03] the value that we have for this, right, if we wanna now determine
- [0:22:08] where this is, what the numerical value of this is on the magnitude scale, then this term here, right, is j omega over omega zero two, and then we're dividing by j omega over omega zero two because this is in its high frequency limit. So these two basically cancel that to one. This factor here is one. Alright? So the transfer function, h of omega, is just 80. Alright? And so on the dB scale,
- [0:22:36] this is going to be
- [0:22:39] 20 times the log
- [0:22:41] of 80, right, which is probably in the high thirties somewhere. Alright?
- [0:22:48] You can calculate it on your calculator if you want.
- [0:22:52] And then finally, if we go to high frequencies, frequency (of?) (above?)
- [0:22:56] omega zero one, we have
- [0:22:59] j omega here in the numerator. This is going to go as j omega in the denominator.
- [0:23:05] This term over here now is in its high frequency limit. So it's also gonna go as j omega in the denominator. So we're gonna have (basically?) omega
- [0:23:13] over omega squared times some constant.
- [0:23:16] But the key is that we have omega over omega squared or equivalently one over omega.
- [0:23:23] And so that means that the magnitude
- [0:23:27] of the transfer function is going to be decreasing,
- [0:23:31] and the slope is going to be minus 20 dB
- [0:23:35] per decade.
- [0:23:41] Okay.
- [0:23:42] And so this is what the Bode magnitude plot looks like. And then we can see pretty clearly from here that this is
- [0:23:52] bandpass filter. Alright? So the passband is basically
- [0:23:56] it it extends a little bit beyond from omega zero two to omega zero one. Alright?
- [0:24:03] And
- [0:24:05] the peak
- [0:24:06] nonresonant gain here, right, this is now
- [0:24:11] m naught, right, is 20 times the log of 80. So a little bit under 40
- [0:24:19] dB. Right? Because the log of 100 would be two. Right? (Now?) (it...?) And that would be exactly
- [0:24:25] 40 dB. Okay. So what we see here is that by using the active
- [0:24:32] filter circuit that employs these op amps, then we're able to get
- [0:24:39] a magnitude of the transfer function that is significantly in excess of one or equivalently in excess of zero dB. Okay.
- [0:24:49] So so that's basically how we analyze this example. And we can see that, right, the way that we went about it was
- [0:24:58] just to recognize that we have this subcircuit over here, right, that is the lowpass active filter circuit that we've seen before. We have this subcircuit over here, which is the highpass active filter circuit that we've seen before. And we can analyze this using the general approach that we use for multiple op amp circuits (where?) we analyze
- [0:25:22] the behaviors of the op amps one by one starting with
- [0:25:28] the op amp that is closest to the input. Right? That allowed us to get v one in terms of v s, then v one serves as the input voltage to the second op amp. That allows us to get v out in terms of v one, and then, therefore, also in terms of (v?) s. Right? And what we see then is (that?) by putting together the lowpass
- [0:25:50] and the highpass filter,

## page 13  f_0295.jpg  on screen [0:25:51 – 0:26:48]
<sub>sharpness 2171, ink 6.5 %, colour 2.1</sub>
<sub>earlier states of this page: f_0260.jpg (0:25:52), f_0262.jpg (0:26:08), f_0263.jpg (0:26:08), f_0271.jpg (0:26:15), f_0273.jpg (0:26:15), f_0274.jpg (0:26:15), f_0275.jpg (0:26:15), f_0276.jpg (0:26:16), f_0277.jpg (0:26:16), f_0281.jpg (0:26:16), f_0282.jpg (0:26:16), f_0284.jpg (0:26:17), f_0287.jpg (0:26:17), f_0291.jpg (0:26:17)</sub>

- [0:25:50] and the highpass filter,
- [0:25:52] we get this cascaded
- [0:25:54] bandpass filter.
- [0:25:56] The other thing to notice here is that in order for this to be a bandpass filter,
- [0:26:01] we actually have
- [0:26:03] the pole for the lowpass filter being at a higher frequency
- [0:26:08] than the pole
- [0:26:10] for the lowpass filter over here. Alright. It's slightly higher, and that allows this to be
- [0:26:18] a bandpass
- [0:26:20] filter. Alright? If if we
- [0:26:23] had not switched those, then it would not have behaved in in quite this way. Alright. So this is the cascaded
- [0:26:31] bandpass filter. That's... This is basically an analysis problem. Right? We're presented with a circuit, and, basically, we want to figure out its behavior, and then maybe after the fact, understand why it behaves in this way. Okay.
- [0:26:48] The second example that we'll look at here

## page 14  f_0297.jpg  on screen [0:26:48 – 0:26:48]
<sub>sharpness 1475, ink 5.3 %, colour 2.1</sub>

- [0:26:31] bandpass filter. That's... This is basically an analysis problem. Right? We're presented with a circuit, and, basically, we want to figure out its behavior, and then maybe after the fact, understand why it behaves in this way. Okay.
- [0:26:48] The second example that we'll look at here

## page 15  f_0298.jpg  on screen [0:26:48 – 0:28:48]
<sub>sharpness 1529, ink 5.6 %, colour 2.0</sub>

- [0:26:31] bandpass filter. That's... This is basically an analysis problem. Right? We're presented with a circuit, and, basically, we want to figure out its behavior, and then maybe after the fact, understand why it behaves in this way. Okay.
- [0:26:48] The second example that we'll look at here
- [0:26:55] is an example of a band reject,
- [0:27:02] and it's a filter
- [0:27:03] design
- [0:27:05] problem. Okay. So we're going to be given a bunch of conditions, right, that we want the circuit design to satisfy,
- [0:27:13] and then we want to design a circuit that,
- [0:27:18] right, meets those criteria, satisfies those conditions. Okay. So,
- [0:27:23] right, this is really a different kind of undertaking than analyzing
- [0:27:27] a circuit that you're presented with. Alright? Because we have to understand
- [0:27:33] well enough how to create different functionalities
- [0:27:37] using circuits and then how to put them together to get some more complicated functionality.
- [0:27:43] Alright? And so
- [0:27:46] what we wanna do here is we want to design a band reject.
- [0:27:54] Alright? Meaning that over a finite range of frequencies, the output is suppressed. Alright? And then at other frequencies, the output is transmitted or amplified.
- [0:28:04] So we wanna design a band reject
- [0:28:09] active filter
- [0:28:12] with the following.
- [0:28:16] Alright. So that satisfies the following conditions. First,
- [0:28:20] we wanna have an overall
- [0:28:27] voltage gain of minus 50, right, outside
- [0:28:35] stopband.
- [0:28:37] Okay.
- [0:28:41] The second thing that we want is we wanna be able to specify what the stopband is. Right? So the stopband,

## page 16  f_0309.jpg  on screen [0:28:48 – 0:30:42]
<sub>sharpness 2096, ink 6.6 %, colour 2.0</sub>

- [0:28:50] we wanna take this to be from
- [0:28:54] 20 kilohertz
- [0:28:56] to 40 kilohertz.
- [0:28:59] Right? So these are now not... These these are just frequencies. They're not angular frequencies. So to get the angular frequency, we have to multiply these numerical values in hertz by
- [0:29:10] two pi. Right? Then we'll get the angular frequency in radians per second. So omega one, corresponding to the lower frequency of the stopband,
- [0:29:19] is going to be two pi times 20 kilohertz.
- [0:29:22] So it's 40 pi
- [0:29:24] kiloradians
- [0:29:26] per second,
- [0:29:28] which is
- [0:29:30] numerically 1.26 times 10 to the fifth
- [0:29:34] radians per second.
- [0:29:37] And then omega two, okay,
- [0:29:41] is two pi times 40 kilohertz. So that is 80
- [0:29:46] pi
- [0:29:48] kiloradians per second.
- [0:29:51] And numerically, that works out to 2.51
- [0:29:54] times
- [0:29:57] 10 to the fifth
- [0:30:00] radians per second. K. So that's the second condition that we wanna satisfy.
- [0:30:05] And then the third
- [0:30:07] is that we want (the?) gain
- [0:30:11] roll off, right,
- [0:30:14] that is the slope, right,
- [0:30:17] outside
- [0:30:18] the stopband
- [0:30:20] to be plus or minus
- [0:30:23] 40 dB
- [0:30:27] per decade. Right? So outside
- [0:30:32] stopband.
- [0:30:35] Okay. So this is the problem that we want to solve here. Alright?
- [0:30:40] So how do we do this? Well, the first step

## page 17  f_0339.jpg  on screen [0:30:42 – 0:36:27]
<sub>sharpness 1463, ink 5.1 %, colour 3.4</sub>
<sub>earlier states of this page: f_0313.jpg (0:31:37), f_0330.jpg (0:32:55), f_0331.jpg (0:32:55), f_0336.jpg (0:34:29)</sub>

- [0:30:40] So how do we do this? Well, the first step
- [0:30:44] is really to just sort of come up with the overall design. Right? What are the component pieces that we need in order to achieve all of these functions. Alright? And then once
- [0:30:57] we
- [0:30:59] have determined that, then we can figure out how to design each of the sub (circuits?) and how to put them together. Okay? So the first step
- [0:31:10] really is to come up
- [0:31:15] with the overall design.
- [0:31:20] Right? And then
- [0:31:22] once we've done that, right, determine
- [0:31:27] the things like the component values.
- [0:31:33] Okay.
- [0:31:34] So so let's think about
- [0:31:38] what we want here. Alright?
- [0:31:41] So let's... To do that,
- [0:31:43] let's sketch out
- [0:31:46] what the Bode plot
- [0:31:49] should look like.
- [0:31:53] Okay.
- [0:31:54] So we want we want an overall gain
- [0:31:58] of 50. Okay? So that means that outside the stopband,
- [0:32:04] right, then what we want... (In?) particularly well outside the stopband, what we want is for
- [0:32:12] the transfer function to have...
- [0:32:16] We want the overall (voltage?) gain to be minus 50. So we want the transfer function
- [0:32:21] to have a magnitude of 50 (or?) in dB, it should be 20 times the log of 50. Alright? So here we have 20 times the log
- [0:32:32] of 50,
- [0:32:34] and then we're going to want
- [0:32:37] transfer function to have a magnitude at that level
- [0:32:40] when we're well outside the stopband. Alright?
- [0:32:44] So this is the frequency.
- [0:32:46] And then,
- [0:32:49] you know, our stopband
- [0:32:51] consisted of frequencies that were kind of in the low 10 to the fifth radians per second. So maybe here, we'll have 10 to the fourth radians per second.
- [0:33:02] Here, this will be 10 to the fifth.
- [0:33:04] And then omega one (maybe?) is here.
- [0:33:08] And omega two maybe is here.
- [0:33:11] Then this will be 10 to the sixth and so forth. Okay?
- [0:33:19] And so then what we want,
- [0:33:21] alright, is if we're well outside the stopband, draw this in blue here, we want
- [0:33:32] the magnitude to be like this.
- [0:33:34] And then
- [0:33:36] we define the stopband
- [0:33:38] such that at omega one and omega two,
- [0:33:41] then
- [0:33:44] the magnitude has dropped down to
- [0:33:50] three dB below its value
- [0:33:54] outside the stopband.
- [0:33:56] Okay. So what we actually want
- [0:33:59] is
- [0:34:01] this.
- [0:34:05] Okay.
- [0:34:07] And we want the slope here to be minus 40 dB
- [0:34:14] per decade, and we want the slope here to be plus
- [0:34:18] 40 dB
- [0:34:20] per decade. Alright?
- [0:34:22] So so this is what we want.
- [0:34:25] Okay?
- [0:34:27] And if we think about this,
- [0:34:30] then
- [0:34:31] if we just think about frequencies less than omega one, right, the way that we can get this kind of behavior is to use a lowpass filter. Right? So here,
- [0:34:42] alright, we want... And then to get a slope of minus 40 dB per decade, then what we want...
- [0:34:49] You know, one way to do that is to use a
- [0:34:53] two stage lowpass active filter, right, where each stage will give us a slope of
- [0:35:00] minus 20 dB. Okay? And then together, cascaded,
- [0:35:04] they will give us a slope of minus 40 dB per decade. Right? So here, we want a two stage
- [0:35:12] lowpass
- [0:35:13] active filter.
- [0:35:17] And let's say that its transfer function should be h sub l p of omega.
- [0:35:24] Alright?
- [0:35:25] And then up here,
- [0:35:28] at higher frequencies,
- [0:35:29] right, the way that we get
- [0:35:32] this kind of behavior, just on the right, is to have a two stage
- [0:35:40] highpass active filter.
- [0:35:46] Okay.
- [0:35:47] It's a highpass filter, right, because, right, we want a large transfer function at high frequencies, and we want it to drop off as we go down in frequency.
- [0:35:57] And then it's two stages
- [0:35:59] because that will give us a slope of 40 dB per decade. Okay? And so that might correspond to a transfer function we'll call h sub HP for highpass
- [0:36:12] of omega.
- [0:36:13] Okay?
- [0:36:16] So...
- [0:36:17] And then we wanna combine these in some appropriate way and get the overall gain as well. So we'll talk about how we combine these in a minute, but let's first think about

## page 18  f_0358.jpg  on screen [0:36:27 – 0:40:32]
<sub>sharpness 1789, ink 5.5 %, colour 2.9</sub>
<sub>earlier states of this page: f_0340.jpg (0:38:24), f_0345.jpg (0:39:50), f_0346.jpg (0:39:50), f_0348.jpg (0:39:51), f_0352.jpg (0:40:19), f_0354.jpg (0:40:20), f_0356.jpg (0:40:32)</sub>

- [0:36:28] what we want these transfer functions for the lowpass and the highpass filter components to be. Alright? For the lowpass filter
- [0:36:39] alright. Remember (we?) talked about the active first (sort?) of lowpass filter in class,
- [0:36:45] and then we talked about what happens if you cascade them. Right? And, basically, you just get the product of transfer functions of each individual stage.
- [0:36:57] And so for the lowpass two stage active filter, then the transfer function is going to be one
- [0:37:06] over
- [0:37:07] one plus j omega
- [0:37:10] over some appropriate
- [0:37:12] (pole?) frequency omega sub LP squared. (Alright.?) Squared because it's a SUSH filter.
- [0:37:19] And
- [0:37:21] omega (l?) p, alright, the pole frequency
- [0:37:24] is going to be one over
- [0:37:27] some resistance
- [0:37:28] times
- [0:37:30] a capacitance we'll call c sub l p. Alright?
- [0:37:34] So that's the transfer function that we wanna get for the lowpass filter. And we basically... From what we talked about in class, we know how to get that. We take the
- [0:37:46] one stage
- [0:37:47] first order active lowpass filter, and we cascade it with another filter just like that, and we're gonna get,
- [0:37:55] basically this. Okay.
- [0:37:58] Then for the highpass
- [0:38:01] filter,
- [0:38:02] right, it's the same thing. Alright? We're going to take two of the
- [0:38:07] first order highpass active filters that we talked about in class. We're going to cascade them, put one after the other, and the transfer function for that combination will be the transfer function of the first and the second multiplied by each other. So we're going to get j omega over omega sub h p squared
- [0:38:29] over
- [0:38:30] one plus j omega over omega sub HP
- [0:38:35] squared. Right?
- [0:38:37] And,
- [0:38:39] alright, the pole frequency omega sub HP, in this case, (is?) going to be one over... Yeah. We can take the resistance to be the same. Right? Because as long as the product of the resistance (and?) the capacitance
- [0:38:51] is
- [0:38:52] the desired
- [0:38:54] quantity,
- [0:38:56] then we can... We... There are many combinations of resistance and capacitance that will give us that. So we can take the resistances in the lowpass
- [0:39:06] subcircuit and the highpass subcircuit. We take them to be the same, and then we have to choose
- [0:39:11] the
- [0:39:13] capacitances
- [0:39:14] to give us the right frequencies.
- [0:39:17] Right? So part of what we're gonna do here is, basically, for simplicity,
- [0:39:24] we choose
- [0:39:27] the same
- [0:39:30] resistance values
- [0:39:34] for the resistors
- [0:39:38] in
- [0:39:40] the lowpass
- [0:39:42] and the highpass
- [0:39:45] subcircuits.
- [0:39:46] Okay.
- [0:39:47] So
- [0:39:49] so that gets us...
- [0:39:51] You know, basically,
- [0:39:53] this type of behavior that we see here in the blue curve Bode plot... Bode magnitude plot. Right? Then the other part that we have to do is to
- [0:40:03] get
- [0:40:05] outside
- [0:40:06] the stopband. We wanna get the magnitude of the transfer function to be
- [0:40:11] at the right level, which is
- [0:40:15] {magnitude}
- [0:40:16] of the gain of 50.
- [0:40:19] Okay?
- [0:40:20] And
- [0:40:22] for circuits that have these transfer functions over here for the lowpass and the highpass components,
- [0:40:29] then the way that we can combine these, right, we also have to figure out how to get these functionalities

## page 19  f_0363.jpg  on screen [0:40:32 – 0:40:33]
<sub>sharpness 1856, ink 5.6 %, colour 3.2</sub>
<sub>earlier states of this page: f_0359.jpg (0:40:33), f_0360.jpg (0:40:33)</sub>

- [0:40:29] then the way that we can combine these, right, we also have to figure out how to get these functionalities

## page 20  f_0364.jpg  on screen [0:40:33 – 0:40:34]
<sub>sharpness 1865, ink 5.6 %, colour 3.2</sub>

- [0:40:29] then the way that we can combine these, right, we also have to figure out how to get these functionalities

## page 21  f_0387.jpg  on screen [0:40:34 – 0:42:25]
<sub>sharpness 1565, ink 5.6 %, colour 2.1</sub>
<sub>earlier states of this page: f_0365.jpg (0:40:35), f_0375.jpg (0:41:48), f_0383.jpg (0:42:25), f_0386.jpg (0:42:25)</sub>

- [0:40:29] then the way that we can combine these, right, we also have to figure out how to get these functionalities
- [0:40:35] together.
- [0:40:36] Right? And we don't wanna take the lowpass
- [0:40:39] subscurve and the highpass subscurve and connect them in series, right, because then
- [0:40:46] they'll each
- [0:40:48] severely attenuate
- [0:40:51] things outside
- [0:40:52] the stopband. We don't really want that. And, also, we'll have a nonzero slope outside the stopband. We don't want that either.
- [0:41:00] Instead, what we want to do is, really, we want to add
- [0:41:05] this response over here on the left to this response over here on the right and then amplify it to the appropriate level to get a total
- [0:41:16] magnitude of 50 outside the stopband. Okay?
- [0:41:21] That won't be exactly right because
- [0:41:25] when we're out here, then we will have... You know, this slope is actually continuing down. But, actually, look, it'll be at such a low level, right, by the time we get out here that it doesn't really influence
- [0:41:36] what this looks like. And similarly,
- [0:41:38] this will be at a very low level by the time we get out here, and so (it?) won't have much quantitative influence on what happens here either. Okay.
- [0:41:47] So
- [0:41:49] the way that we combine these
- [0:41:53] and then also bring in, the requisite gain
- [0:41:57] is,
- [0:41:58] that we combine these
- [0:42:03] using,
- [0:42:05] an inverting
- [0:42:12] summing amplifier
- [0:42:17] that has a gain
- [0:42:20] of minus 50.
- [0:42:22] Okay.
- [0:42:24] And so kind of in terms of basic block units, right,

## page 22  f_0430.jpg  on screen [0:42:25 – 0:45:56]
<sub>sharpness 2233, ink 6.5 %, colour 3.0</sub>
<sub>earlier states of this page: f_0388.jpg (0:43:12), f_0392.jpg (0:44:11), f_0394.jpg (0:44:11), f_0412.jpg (0:44:19), f_0414.jpg (0:44:20), f_0415.jpg (0:44:32), f_0423.jpg (0:45:55), f_0424.jpg (0:45:55), f_0425.jpg (0:45:55), f_0429.jpg (0:45:55)</sub>

- [0:42:24] And so kind of in terms of basic block units, right,
- [0:42:29] (if?) we have our input voltage signal like this, then we wanna take that
- [0:42:35] and send it in parallel
- [0:42:38] to one subcircuit,
- [0:42:40] which will give us the lowpass
- [0:42:46] filtering behavior.
- [0:42:49] And then also to another subcircuit
- [0:42:52] that will give us the highpass behavior.
- [0:42:56] Alright? We will have output voltages that are, say, v one
- [0:43:01] and v two.
- [0:43:03] Then we want to take those
- [0:43:08] and use those as the two inputs
- [0:43:12] for
- [0:43:17] an inverting summing amplifier
- [0:43:25] that has a gain equal to minus 50.
- [0:43:29] Okay. And we saw earlier in the semester when we talked about op amp circuits generally. Right? We know how to do this.
- [0:43:37] And then finally,
- [0:43:39] that will give us
- [0:43:40] the desired output voltage. Right? So this is the general concept of how we want to proceed here. Okay?
- [0:43:48] And so what we need to do next is to figure out how we design each of these individual blocks, and then we can put them all together in the way that I've shown here. (Alright.?)
- [0:44:00] And so
- [0:44:02] (we?) can take as our next step then to
- [0:44:05] essentially figure out how to design
- [0:44:07] this lowpass
- [0:44:09] filter circuit. Alright? Given that
- [0:44:13] its transfer function is going to look like this over here. Alright?
- [0:44:19] So
- [0:44:21] that means we wanna determine...
- [0:44:24] We need to determine this resistance r
- [0:44:27] and then the capacitance associated with the lowpass
- [0:44:32] filter circuit.
- [0:44:35] Okay. So the magnitude
- [0:44:38] of
- [0:44:39] this cascaded
- [0:44:41] lowpass filter circuit is what it's gonna be is... Right. It's the magnitude of this transfer function,
- [0:44:49] right, that we have
- [0:44:51] specified.
- [0:44:53] So it's going to be the magnitude of
- [0:44:56] one over
- [0:44:58] one plus j omega over omega l p squared.
- [0:45:03] Right?
- [0:45:04] The magnitude of this is
- [0:45:08] just one over one plus
- [0:45:10] omega over omega l p
- [0:45:12] squared. Right? Because if this were
- [0:45:17] to the one power instead of squared, then the magnitude
- [0:45:21] of this whole thing would be one over the square root of this denominator. Alright? And so when we have this squared, then the magnitude is just squared as well. So that's basically how we get this. Okay.
- [0:45:32] In addition, what we want is that...
- [0:45:36] Alright. So
- [0:45:39] when we are...
- [0:45:42] This is the lowpass filter.
- [0:45:44] So at low frequencies,
- [0:45:46] this has a magnitude of one. Alright? So at the edges of the stopband,
- [0:45:51] right, omega one and omega two,

## page 23  f_0454.jpg  on screen [0:45:56 – 0:46:55]
<sub>sharpness 2542, ink 7.4 %, colour 2.1</sub>
<sub>earlier states of this page: f_0432.jpg (0:45:56), f_0433.jpg (0:46:11), f_0434.jpg (0:46:11), f_0441.jpg (0:46:12), f_0444.jpg (0:46:13), f_0445.jpg (0:46:13), f_0452.jpg (0:46:55), f_0453.jpg (0:46:55)</sub>

- [0:45:58] right, up here, and omega one is going to be the relevant frequency for the lowpass filter, which gives us this behavior, then we want the magnitude to be
- [0:46:09] one over the square root of two. Right? So
- [0:46:14] at the edges
- [0:46:19] of the stopband,
- [0:46:23] right, that is at omega equal to omega one and omega equal to omega two, right,
- [0:46:32] then what we want is that we want the magnitude
- [0:46:37] of the transfer function to be one over the square root of two. Alright?
- [0:46:42] And so that means that the magnitude of
- [0:46:46] the transfer function for the lowpass
- [0:46:49] subcircuit,
- [0:46:51] we want that when evaluated at omega one.
- [0:46:55] Okay? It's omega one,

## page 24  f_0540.jpg  on screen [0:46:55 – 0:51:15]
<sub>sharpness 2543, ink 7.3 %, colour 2.2</sub>
<sub>earlier states of this page: f_0462.jpg (0:46:56), f_0466.jpg (0:46:57), f_0468.jpg (0:46:57), f_0471.jpg (0:46:57), f_0472.jpg (0:47:03), f_0479.jpg (0:47:04), f_0484.jpg (0:47:04), f_0489.jpg (0:47:05), f_0495.jpg (0:47:14), f_0499.jpg (0:47:49), f_0510.jpg (0:48:42), f_0511.jpg (0:49:16), f_0512.jpg (0:49:16), f_0515.jpg (0:50:30), f_0518.jpg (0:50:55), f_0519.jpg (0:50:55), f_0526.jpg (0:51:14), f_0531.jpg (0:51:14), f_0535.jpg (0:51:15)</sub>

- [0:46:55] Okay? It's omega one,
- [0:46:58] right, up here because omega one, we saw, is less than omega two.
- [0:47:05] Okay. We want that to be equal to one over the square root of two.
- [0:47:12] Okay. So that means that... Alright. We want one over one plus
- [0:47:18] omega one over omega (l?) p squared.
- [0:47:22] Alright. That's the magnitude of the lowpass subcircuit.
- [0:47:27] We want this to be equal to one over
- [0:47:30] the square root of two.
- [0:47:33] And... Alright. So that means that
- [0:47:36] omega one
- [0:47:38] over omega
- [0:47:40] lowpass, the the pole frequency squared,
- [0:47:44] has to be equal to the square root of two minus one. Right? That's just simple algebra to get that.
- [0:47:51] And if we solve that for
- [0:47:55] the (pole?) frequency of the lowpass filter, then it's going to be omega one
- [0:48:01] over
- [0:48:03] square root of two minus one to the one half power. Right?
- [0:48:08] And so then just working this out numerically, omega one is 1.26
- [0:48:12] times 10 to the fifth
- [0:48:15] radians per second, and we're dividing that by the square root of two minus one
- [0:48:20] to the one half power. That ends up being equal to 1.96
- [0:48:25] times 10 to the fifth
- [0:48:28] radians per second. Okay.
- [0:48:31] And, we want that,
- [0:48:34] to be equal to
- [0:48:36] one over r times,
- [0:48:39] some capacitance. Alright. So now,
- [0:48:42] right, (there?) are not unique choices for r and that capacitance,
- [0:48:47] so we can choose one of them to be anything.
- [0:48:50] So let's choose the resistance. Right? We're free to choose whatever value we want for that. So let's choose something nice and simple. We'll take it to be one kilo.
- [0:49:00] Okay?
- [0:49:01] Once we've chosen the resistance,
- [0:49:04] then the capacitance,
- [0:49:06] we're not free to choose. We have to figure out what value (the?) capacitance
- [0:49:11] satisfies this equation here. Right?
- [0:49:15] So then
- [0:49:16] what happens is that the capacitance
- [0:49:20] is one over r times
- [0:49:25] omega l p. So that is one over r. We chose it to be one kilohm, and omega l p, right, is this value here, 1.96
- [0:49:37] times 10 to the fifth
- [0:49:40] radians per second. Okay.
- [0:49:43] And if we calculate that out, then we get 5.1
- [0:49:48] nanofarads.
- [0:49:50] So this
- [0:49:52] is
- [0:49:53] the capacitance that we use in the lowpass
- [0:49:58] filter circuit. The resistance that we use is one kilo. And the design of each stage of
- [0:50:05] this two stage lowpass filter circuit is the same as that of the first order lowpass
- [0:50:13] circuit... Lowpass filter circuit that we talked about in class, okay,
- [0:50:18] which is that we have a... The key part is we have a resistor in parallel with a capacitor
- [0:50:25] in the feedback connection of that op amp circuit.
- [0:50:29] Okay.
- [0:50:31] So that's the lowpass
- [0:50:32] part of the circuit.
- [0:50:35] Then we have the highpass part of the circuit. And, again, right, we've chosen the value of the resistance. It's gonna be one kilohm. So, basically, we have to figure out what the capacitance value is. Right? So we wanna determine
- [0:50:53] the capacitance value for the high
- [0:50:56] pass part of the circuit.
- [0:50:58] So the transfer function,
- [0:51:01] right,
- [0:51:02] magnitude...
- [0:51:04] Right? So it's the magnitude of
- [0:51:09] the highpass filter transfer function. So from what we specified
- [0:51:14] that transfer function to have to be. Alright? We said it's gonna be a transfer function like this because when we talked about the highpass filter circuit in class, we got something like this. Without the squares, we have two stages that are cascaded, then that gives us the squares. Okay?

## page 25  f_0556.jpg  on screen [0:51:15 – 0:51:32]
<sub>sharpness 2577, ink 7.3 %, colour 2.1</sub>
<sub>earlier states of this page: f_0544.jpg (0:51:16)</sub>

- [0:51:14] that transfer function to have to be. Alright? We said it's gonna be a transfer function like this because when we talked about the highpass filter circuit in class, we got something like this. Without the squares, we have two stages that are cascaded, then that gives us the squares. Okay?

## page 26  f_0684.jpg  on screen [0:51:32 – 0:52:59]
<sub>sharpness 2516, ink 6.9 %, colour 2.1</sub>
<sub>earlier states of this page: f_0557.jpg (0:51:32), f_0561.jpg (0:51:33), f_0564.jpg (0:51:33), f_0565.jpg (0:51:33), f_0566.jpg (0:51:33), f_0568.jpg (0:51:34), f_0569.jpg (0:51:34), f_0570.jpg (0:51:34), f_0577.jpg (0:52:15), f_0581.jpg (0:52:15), f_0582.jpg (0:52:15), f_0584.jpg (0:52:16), f_0593.jpg (0:52:17), f_0594.jpg (0:52:17), f_0596.jpg (0:52:17), f_0601.jpg (0:52:18), f_0602.jpg (0:52:18), f_0605.jpg (0:52:18), f_0614.jpg (0:52:39), f_0618.jpg (0:52:40), f_0620.jpg (0:52:40), f_0623.jpg (0:52:40), f_0631.jpg (0:52:41), f_0636.jpg (0:52:42), f_0640.jpg (0:52:42), f_0645.jpg (0:52:43), f_0651.jpg (0:52:43), f_0652.jpg (0:52:44), f_0653.jpg (0:52:44), f_0654.jpg (0:52:44), f_0657.jpg (0:52:48), f_0661.jpg (0:52:56), f_0669.jpg (0:52:57), f_0670.jpg (0:52:57), f_0671.jpg (0:52:57), f_0676.jpg (0:52:58), f_0677.jpg (0:52:58), f_0678.jpg (0:52:58), f_0683.jpg (0:52:58)</sub>

- [0:51:14] that transfer function to have to be. Alright? We said it's gonna be a transfer function like this because when we talked about the highpass filter circuit in class, we got something like this. Without the squares, we have two stages that are cascaded, then that gives us the squares. Okay?
- [0:51:33] So
- [0:51:35] we have the highpass filters.
- [0:51:38] We have the magnitude of that function. So it's the magnitude of
- [0:51:43] j omega over omega highpass squared
- [0:51:48] over
- [0:51:49] one plus,
- [0:51:51] right, j omega over omega highpass
- [0:51:54] quantity squared. (Alright.?) Taking the magnitude of that,
- [0:51:58] and the magnitude of that is (in?) the numerator, it's omega over omega highpass squared.
- [0:52:05] In the denominator, it's one plus omega over omega highpass
- [0:52:10] squared.
- [0:52:11] Okay.
- [0:52:12] And, again...
- [0:52:14] Alright.
- [0:52:16] What we want... Right? So we can see that
- [0:52:19] as omega becomes very large,
- [0:52:22] then this magnitude approaches one. Right? Because the numerator goes as omega over omega highpass squared. The denominator goes as omega over omega highpass squared since this one is very small compared to this term for high frequencies,
- [0:52:36] and this works out just to be one overall.
- [0:52:39] So what we want then
- [0:52:41] is that
- [0:52:42] at omega equal to omega two...
- [0:52:46] Right? So this is the highpass behavior that we want. And so (at?) omega equal to omega two, we want the magnitude of that transfer function to be one over root two. Alright?
- [0:52:59] So

## page 27  f_0715.jpg  on screen [0:52:59 – 0:54:15]
<sub>sharpness 2780, ink 7.6 %, colour 2.2</sub>
<sub>earlier states of this page: f_0689.jpg (0:52:59), f_0690.jpg (0:52:59), f_0691.jpg (0:52:59), f_0693.jpg (0:54:12), f_0694.jpg (0:54:12), f_0697.jpg (0:54:13), f_0700.jpg (0:54:13), f_0702.jpg (0:54:13), f_0704.jpg (0:54:13), f_0707.jpg (0:54:14), f_0711.jpg (0:54:14)</sub>

- [0:52:59] So
- [0:53:04] we want the magnitude
- [0:53:06] of the highpass
- [0:53:09] transfer function evaluated at omega two. We want it to be one over the square root of two. Right?
- [0:53:16] So that means that
- [0:53:18] omega two over omega highpass, right, the pole frequency
- [0:53:23] (over?) one plus
- [0:53:26] omega two over omega highpass
- [0:53:29] squared,
- [0:53:30] right, has to be equal to one
- [0:53:32] over the square root of two. Alright?
- [0:53:36] And, right, if you just do the algebra to solve for omega two
- [0:53:41] over omega omega highpass squared,
- [0:53:44] and this is one over the square root of two minus one. Right? It's very simple to get that.
- [0:53:49] And so we can solve this
- [0:53:52] for
- [0:53:53] the pole frequency omega highpass. Right? It's equal to
- [0:53:58] square root of two minus one
- [0:54:01] to the one half times
- [0:54:03] omega two,
- [0:54:05] right, or the square root of two minus one to the one half times an omega two. Remember, we worked out

## page 28  f_0724.jpg  on screen [0:54:15 – 0:54:16]
<sub>sharpness 1907, ink 5.7 %, colour 3.4</sub>
<sub>earlier states of this page: f_0720.jpg (0:54:15), f_0721.jpg (0:54:15)</sub>

- (no speech captured in this span)

## page 29  f_0725.jpg  on screen [0:54:16 – 0:54:16]
<sub>sharpness 1780, ink 5.4 %, colour 3.4</sub>

- (no speech captured in this span)

## page 30  f_0743.jpg  on screen [0:54:16 – 0:54:21]
<sub>sharpness 1609, ink 5.3 %, colour 3.4</sub>
<sub>earlier states of this page: f_0726.jpg (0:54:16), f_0742.jpg (0:54:21)</sub>

- [0:54:17] up here is 2.51
- [0:54:20] times 10 to the fifth radians per second.

## page 31  f_0744.jpg  on screen [0:54:21 – 0:54:21]
<sub>sharpness 1722, ink 5.2 %, colour 3.4</sub>

- [0:54:20] times 10 to the fifth radians per second.

## page 32  f_0776.jpg  on screen [0:54:21 – 0:54:26]
<sub>sharpness 2559, ink 6.9 %, colour 2.1</sub>
<sub>earlier states of this page: f_0747.jpg (0:54:22), f_0752.jpg (0:54:22), f_0753.jpg (0:54:22), f_0754.jpg (0:54:23), f_0759.jpg (0:54:23), f_0760.jpg (0:54:23), f_0761.jpg (0:54:23), f_0764.jpg (0:54:24), f_0770.jpg (0:54:25), f_0771.jpg (0:54:25), f_0772.jpg (0:54:25), f_0773.jpg (0:54:25)</sub>

- [0:54:20] times 10 to the fifth radians per second.
- [0:54:26] Alright. So this is 2.51

## page 33  f_0789.jpg  on screen [0:54:26 – 0:56:15]
<sub>sharpness 2656, ink 7.1 %, colour 2.1</sub>
<sub>earlier states of this page: f_0782.jpg (0:54:27), f_0785.jpg (0:54:46)</sub>

- [0:54:26] Alright. So this is 2.51
- [0:54:30] times 10 to the fifth
- [0:54:34] radians per second. And if we multiply that out, we get 1.62 times 10 to the fifth
- [0:54:43] radians per second. Alright?
- [0:54:46] Now we know that
- [0:54:49] that (pole?) frequency
- [0:54:51] for the highpass filter circuit, right, from what we did in class, is one over r times
- [0:54:59] this capacitance c sub HP.
- [0:55:01] Right? And we chose r to be
- [0:55:06] one kiloohm already,
- [0:55:08] right, which means that
- [0:55:11] the capacitance in the highpass filter circuit is going to be... Right. It's one over r times
- [0:55:18] omega
- [0:55:20] highpass, the whole... The pole frequency.
- [0:55:22] So that is one over r is 10 to the third ohms.
- [0:55:27] And then omega HP, we just figured out (as?) 1.62
- [0:55:30] times 10 to the fifth
- [0:55:33] radians per second,
- [0:55:36] and this ends up being one over 1.62
- [0:55:39] times 10 to the eighth,
- [0:55:41] which is 6.2
- [0:55:43] nanofarads.
- [0:55:45] So that is the capacitance
- [0:55:48] in
- [0:55:50] the highpass filter circuit. And remember from the configuration of the first order active highpass filter that we talked about in class, that capacitance goes in series
- [0:56:02] with the voltage source and the resistor that are at the input of that circuit. Okay. So now we've figured out the component values, the resistor (and?) then the two capacitors,
- [0:56:14] capacitance values that go into the

## page 34  f_0859.jpg  on screen [0:56:15 – 0:57:07]
<sub>sharpness 1643, ink 5.6 %, colour 2.1</sub>
<sub>earlier states of this page: f_0796.jpg (0:56:16), f_0806.jpg (0:56:24), f_0807.jpg (0:56:24), f_0808.jpg (0:56:24), f_0812.jpg (0:56:25), f_0813.jpg (0:56:25), f_0814.jpg (0:56:25), f_0815.jpg (0:56:25), f_0818.jpg (0:56:25), f_0821.jpg (0:56:26), f_0826.jpg (0:56:26), f_0829.jpg (0:56:41), f_0831.jpg (0:56:41), f_0836.jpg (0:56:42), f_0838.jpg (0:56:42), f_0839.jpg (0:56:42), f_0844.jpg (0:56:43), f_0850.jpg (0:56:43), f_0851.jpg (0:56:44), f_0854.jpg (0:56:44), f_0857.jpg (0:57:07), f_0858.jpg (0:57:07)</sub>

- [0:56:14] capacitance values that go into the
- [0:56:19] lowpass
- [0:56:20] and highpass blocks
- [0:56:23] of
- [0:56:25] this overall circuit. Right? So, basically, we know what this unit looks like and what this unit looks like. Now we just have to figure out or remind ourselves of how we design the inverting summing amplifiers so that we have a gain of minus 50.
- [0:56:44] K. So then this next step here,
- [0:56:47] right, is to design
- [0:56:50] the inverting
- [0:56:56] summing amplifier,
- [0:57:00] alright,
- [0:57:01] to have a gain
- [0:57:05] of minus 50.
- [0:57:07] Okay.

## page 35  f_0926.jpg  on screen [0:57:07 – 1:00:19]
<sub>sharpness 1683, ink 5.6 %, colour 2.1</sub>
<sub>earlier states of this page: f_0860.jpg (0:57:36), f_0865.jpg (1:00:00), f_0866.jpg (1:00:00), f_0871.jpg (1:00:01), f_0877.jpg (1:00:01), f_0880.jpg (1:00:02), f_0885.jpg (1:00:02), f_0891.jpg (1:00:03), f_0895.jpg (1:00:03), f_0899.jpg (1:00:03), f_0900.jpg (1:00:04), f_0901.jpg (1:00:04), f_0907.jpg (1:00:04), f_0908.jpg (1:00:05), f_0918.jpg (1:00:19), f_0920.jpg (1:00:19), f_0921.jpg (1:00:19), f_0923.jpg (1:00:19)</sub>

- [0:57:07] Okay.
- [0:57:08] So remember from when we talked about op amps earlier in the semester,
- [0:57:13] right, that the basic design for the inverting summing amplifier
- [0:57:19] is like this. This is our
- [0:57:25] output voltage.
- [0:57:27] The noninverting input is grounded,
- [0:57:30] and then we have
- [0:57:33] feedback resistor
- [0:57:35] {RF.}
- [0:57:38] And then we have two inputs,
- [0:57:44] each of which is connected through a resistor
- [0:57:47] to the inverting input
- [0:57:50] of the op amp. Right? So... And these resistors, we can take to be
- [0:57:55] r in each case. Right? Because we want the gain for each of them to be... Each of the voltage inputs to be the same,
- [0:58:02] and then we can just choose (RF?)
- [0:58:04] as a multiple of r to get the the overall gain factor for those input voltages.
- [0:58:12] So then if we just apply in the usual way, KCL at the inverting input
- [0:58:22] of the op amp, then... Alright. We know that the voltage at the inverting input is zero. So applying KCL, then the current up through this upper resistor r is minus v one over r. The current through
- [0:58:36] this lower resistor r is minus v two
- [0:58:40] over r, and (that?) the current
- [0:58:44] out this way through r f is minus v out
- [0:58:49] over r f.
- [0:58:52] Right? That's equal to zero.
- [0:58:54] And so if we solve that for
- [0:58:57] the output voltage, then that's minus r f over r times v one plus
- [0:59:05] v two, alright, where v one and v two are the outputs of the lowpass and highpass active filter blocks. Alright?
- [0:59:15] And so if we take this r, (we?) take it to be the same value as we had for the for the filters, right, namely one kilohm,
- [0:59:23] then in order for this overall gain factor to be minus 50, we want (r?) f to be 50 kilohms.
- [0:59:30] Right? So for r,
- [0:59:33] it's (the?) one kilo ohm.
- [0:59:37] Right? Then we choose
- [0:59:41] RF is equal to 50
- [0:59:46] kilo ohms, and that means that the output voltage
- [0:59:50] will be equal to minus 50 times v one
- [0:59:55] plus v two. Okay.
- [0:59:58] And
- [1:00:00] so now we have everything.
- [1:00:02] Alright?
- [1:00:03] In
- [1:00:06] this overall design here... Alright? And I'll draw this out explicitly in a minute. Right? We have... We know what these two units should look like (including?) their component values, and we just figured out what the inverting summing amplifier
- [1:00:19] should look like.

## page 36  f_0930.jpg  on screen [1:00:19 – 1:00:24]
<sub>sharpness 2988, ink 7.7 %, colour 2.1</sub>
<sub>earlier states of this page: f_0927.jpg (1:00:23), f_0929.jpg (1:00:24)</sub>

- [1:00:06] this overall design here... Alright? And I'll draw this out explicitly in a minute. Right? We have... We know what these two units should look like (including?) their component values, and we just figured out what the inverting summing amplifier
- [1:00:19] should look like.
- [1:00:23] Oops.

## page 37  f_0942.jpg  on screen [1:00:24 – 1:00:25]
<sub>sharpness 1826, ink 6.1 %, colour 2.1</sub>
<sub>earlier states of this page: f_0934.jpg (1:00:24), f_0936.jpg (1:00:24), f_0937.jpg (1:00:24), f_0940.jpg (1:00:25), f_0941.jpg (1:00:25)</sub>

- [1:00:23] Oops.

## page 38  f_0943.jpg  on screen [1:00:25 – 1:00:25]
<sub>sharpness 1674, ink 5.8 %, colour 2.1</sub>

- (no speech captured in this span)

## page 39  f_0965.jpg  on screen [1:00:25 – 1:03:37]
<sub>sharpness 2990, ink 7.7 %, colour 2.1</sub>
<sub>earlier states of this page: f_0944.jpg (1:02:24), f_0949.jpg (1:03:35), f_0950.jpg (1:03:35), f_0953.jpg (1:03:35), f_0957.jpg (1:03:36), f_0958.jpg (1:03:36), f_0962.jpg (1:03:36), f_0963.jpg (1:03:36)</sub>

- [1:00:26] Okay. So then the last step is to combine
- [1:00:34] the sub circuits into the final circuit.
- [1:00:43] Okay. And so what this is going to look like, right, is we have
- [1:00:49] our input voltage,
- [1:00:52] and we wanna send that
- [1:00:55] to
- [1:00:57] our two
- [1:00:59] filter circuits. Right? Each of which is a
- [1:01:03] two stage
- [1:01:06] filter. Right? So the upper circuit that we'll draw
- [1:01:11] is the lowpass
- [1:01:14] two stage filter circuit.
- [1:01:18] K. So remember for a lowpass
- [1:01:24] active filter, the feedback loop contains
- [1:01:28] a resistor. All these resistors are r. This is c
- [1:01:32] lowpass,
- [1:01:34] alright, connected to the output.
- [1:01:37] Then
- [1:01:38] we take
- [1:01:40] this output
- [1:01:41] and use it as the input to a second active lowpass filter circuit that is configured exactly as this first one is over here. So we have another resistor
- [1:01:53] {r.}
- [1:02:00] K. Ground connection to the other input.
- [1:02:04] And then
- [1:02:06] we again have...
- [1:02:15] Right, our resistor and capacitor
- [1:02:19] in parallel, right, for the feedback connection. And then final... And then that's eventually going to go to the inverting summing amplifier. But before we draw that, let's draw the
- [1:02:34] highpass filter unit. So we have, in that case, a resistor in series with a capacitor. This resistor is still r. Now the capacitor is the highpass
- [1:02:45] passiveness that we calculated.
- [1:02:50] Those will be inputs to
- [1:02:53] an op amp,
- [1:02:55] and the feedback connection here
- [1:02:59] is just the resistor r. Okay?
- [1:03:02] Then we have...
- [1:03:06] That is the input to the same thing.
- [1:03:09] Alright. So we're cascading two units of this together.
- [1:03:19] K.
- [1:03:20] So here we have
- [1:03:23] another resistor r. Okay.
- [1:03:26] And so this is the voltage
- [1:03:28] v one.
- [1:03:31] This is the voltage v two. Alright. So in what we have drawn here so far,

## page 40  f_0987.jpg  on screen [1:03:37 – 1:03:39]
<sub>sharpness 2644, ink 7.1 %, colour 2.1</sub>
<sub>earlier states of this page: f_0967.jpg (1:03:37), f_0968.jpg (1:03:37), f_0971.jpg (1:03:37), f_0973.jpg (1:03:37), f_0975.jpg (1:03:38), f_0980.jpg (1:03:38), f_0981.jpg (1:03:38), f_0982.jpg (1:03:38), f_0986.jpg (1:03:39)</sub>

- (no speech captured in this span)

## page 41  f_1006.jpg  on screen [1:03:39 – 1:03:48]
<sub>sharpness 2446, ink 6.7 %, colour 2.1</sub>
<sub>earlier states of this page: f_0990.jpg (1:03:39), f_0999.jpg (1:03:48), f_1001.jpg (1:03:48)</sub>

- [1:03:40] Right? We've gotten... We've drawn these two blocks over here. We've gotten up to v one and v two, and then those are the inputs for the inverting summing amplifier.

## page 42  f_1019.jpg  on screen [1:03:48 – 1:03:50]
<sub>sharpness 2927, ink 7.6 %, colour 2.1</sub>
<sub>earlier states of this page: f_1007.jpg (1:03:49), f_1008.jpg (1:03:49), f_1011.jpg (1:03:49), f_1015.jpg (1:03:50), f_1016.jpg (1:03:50), f_1018.jpg (1:03:50)</sub>

- [1:03:40] Right? We've gotten... We've drawn these two blocks over here. We've gotten up to v one and v two, and then those are the inputs for the inverting summing amplifier.
- [1:03:50] Right? And that inverting summing amplifier

## page 43  f_1028.jpg  on screen [1:03:50 – 1:03:54]
<sub>sharpness 2512, ink 7.1 %, colour 2.1</sub>
<sub>earlier states of this page: f_1023.jpg (1:03:51)</sub>

- [1:03:50] Right? And that inverting summing amplifier
- [1:03:53] looks like this.

## page 44  f_1069.jpg  on screen [1:03:54 – 1:06:00]
<sub>sharpness 3080, ink 7.8 %, colour 2.1</sub>
<sub>earlier states of this page: f_1030.jpg (1:03:55), f_1037.jpg (1:03:55), f_1045.jpg (1:04:49), f_1051.jpg (1:05:58), f_1055.jpg (1:05:59), f_1056.jpg (1:05:59), f_1057.jpg (1:05:59), f_1059.jpg (1:05:59), f_1061.jpg (1:05:59), f_1063.jpg (1:06:00), f_1064.jpg (1:06:00), f_1065.jpg (1:06:00), f_1068.jpg (1:06:00)</sub>

- [1:03:56] Okay. So we take those two as the inputs
- [1:03:59] to...
- [1:04:07] Right. These are resistors with resistances r.
- [1:04:11] K.
- [1:04:13] And these
- [1:04:18] are the inputs to one more op amp.
- [1:04:23] Alright. That's the inverting summing amplifier
- [1:04:29] with a feedback resistance RF, alright, that we figured out for r equal to one k, RF is equal to 50 kilo ohms.
- [1:04:36] And
- [1:04:40] that gives us
- [1:04:43] our output voltage.
- [1:04:45] And so that is the whole thing. Right? So you can see that, actually, this circuit looks like a very complicated circuit.
- [1:04:53] Okay?
- [1:04:55] And it is a fairly complicated circuit, but you can see, hopefully,
- [1:04:59] through what we have discussed here, how you can build up to the circuit by considering
- [1:05:05] just the fundamental blocks from which this is constructed. Right? So we have the
- [1:05:11] single stage, just the first order lowpass filter up here, and
- [1:05:17] we saw that you could put two
- [1:05:20] of those in series. Right? And that'll give us the second order lowpass filter.
- [1:05:27] Alright? We analyze and class the highpass filter down here. Alright? The first order active highpass filter.
- [1:05:34] Again, we can cascade these as we saw in a similar example
- [1:05:38] in class and get the second order filter behavior. Then we take the outputs of those two blocks,
- [1:05:46] and we
- [1:05:47] invert and sum them with amplification over here to get the final output. And that's how we get the the final design for this circuit here
- [1:05:59] that

## page 45  f_1070.jpg  on screen [1:06:00 – 1:06:00]
<sub>sharpness 2636, ink 7.1 %, colour 2.1</sub>

- [1:05:59] that

## page 46  f_1074.jpg  on screen [1:06:00 – 1:06:01]
<sub>sharpness 2600, ink 7.0 %, colour 2.1</sub>
<sub>earlier states of this page: f_1071.jpg (1:06:00)</sub>

- [1:05:59] that

## page 47  f_1094.jpg  on screen [1:06:01 – 1:06:03]
<sub>sharpness 1963, ink 5.7 %, colour 3.5</sub>
<sub>earlier states of this page: f_1075.jpg (1:06:01), f_1078.jpg (1:06:01), f_1079.jpg (1:06:02), f_1080.jpg (1:06:02), f_1081.jpg (1:06:02), f_1084.jpg (1:06:02), f_1087.jpg (1:06:02), f_1090.jpg (1:06:03), f_1093.jpg (1:06:03)</sub>

- [1:06:02] will satisfy

## page 48  f_1125.jpg  on screen [1:06:03 – 1:06:18]
<sub>sharpness 1807, ink 5.7 %, colour 3.4</sub>
<sub>earlier states of this page: f_1095.jpg (1:06:03), f_1109.jpg (1:06:10), f_1119.jpg (1:06:17), f_1124.jpg (1:06:18)</sub>

- [1:06:02] will satisfy
- [1:06:05] all (these?) criteria
- [1:06:06] that we specify. Alright? And, basically,
- [1:06:10] right, you can see how we kind of went through this step by step. First, we figured all out... Well, what are the sort of general blocks, functional blocks that we want to have? Alright?

## page 49  f_1131.jpg  on screen [1:06:18 – 1:06:19]
<sub>sharpness 2113, ink 6.2 %, colour 3.2</sub>
<sub>earlier states of this page: f_1126.jpg (1:06:18), f_1128.jpg (1:06:18), f_1129.jpg (1:06:18)</sub>

- [1:06:10] right, you can see how we kind of went through this step by step. First, we figured all out... Well, what are the sort of general blocks, functional blocks that we want to have? Alright?

## page 50  f_1157.jpg  on screen [1:06:19 – 1:06:39]
<sub>sharpness 2565, ink 7.3 %, colour 2.1</sub>
<sub>earlier states of this page: f_1142.jpg (1:06:29), f_1143.jpg (1:06:29), f_1147.jpg (1:06:29)</sub>

- [1:06:10] right, you can see how we kind of went through this step by step. First, we figured all out... Well, what are the sort of general blocks, functional blocks that we want to have? Alright?
- [1:06:20] That got us to this.
- [1:06:23] Alright? And then we figured out the details of what each of these blocks would have to look like building upon what we know circuits with that kind of functionality
- [1:06:34] should look like from what we've done
- [1:06:37] earlier in the semester. Okay? And then, you know, all of that together gets us to,

## page 51  f_1164.jpg  on screen [1:06:39 – 1:06:40]
<sub>sharpness 2609, ink 7.2 %, colour 2.1</sub>
<sub>earlier states of this page: f_1159.jpg (1:06:40), f_1163.jpg (1:06:40)</sub>

- [1:06:37] earlier in the semester. Okay? And then, you know, all of that together gets us to,

## page 52  f_1168.jpg  on screen [1:06:40 – 1:06:41]
<sub>sharpness 2506, ink 6.8 %, colour 2.1</sub>
<sub>earlier states of this page: f_1165.jpg (1:06:40)</sub>

- [1:06:37] earlier in the semester. Okay? And then, you know, all of that together gets us to,

## page 53  f_1176.jpg  on screen [1:06:41 – 1:06:42]
<sub>sharpness 2879, ink 7.6 %, colour 2.1</sub>
<sub>earlier states of this page: f_1172.jpg (1:06:41), f_1174.jpg (1:06:41)</sub>

- [1:06:37] earlier in the semester. Okay? And then, you know, all of that together gets us to,

## page 54  f_1180.jpg  on screen [1:06:42 – 1:06:42]
<sub>sharpness 2719, ink 7.5 %, colour 2.1</sub>

- [1:06:37] earlier in the semester. Okay? And then, you know, all of that together gets us to,

## page 55  f_1198.jpg  on screen [1:06:42 – 1:06:44]
<sub>sharpness 2325, ink 6.9 %, colour 2.1</sub>
<sub>earlier states of this page: f_1185.jpg (1:06:43), f_1186.jpg (1:06:43), f_1189.jpg (1:06:43), f_1195.jpg (1:06:44)</sub>

- [1:06:37] earlier in the semester. Okay? And then, you know, all of that together gets us to,
- [1:06:44] you know, this final...
