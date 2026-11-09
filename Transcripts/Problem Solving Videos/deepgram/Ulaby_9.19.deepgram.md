# Ulaby 9.19 video

Deepgram general-nova-3 2025-07-31.0, request 01a1b039-82b8-7493-98af-6df814c8c3bb, audio 92.6 min.

**[0:00:03]** Okay. So this is Ulaby problem 9.19. Alright? And this is a multipart problem, and it consists of examples of generating Bode plots. Right?

**[0:00:19]** So Bode plots that are generated from transfer functions, h of omega. Okay? And so, so this is a pretty long example because it has so many parts. Alright? So we'll just go through each of these one by one.

**[0:00:44]** Alright? And what we'll want to do is to take a look at each of these transfer functions and then construct the Bode magnitude and phase plots. And we're gonna use the straight line approximation versions of these Bode plots, right, for the four different transfer functions that are shown here. Okay. So we'll go ahead and get started with this.

**[0:01:06]** So the first one of these is where the transfer function h of omega is equal to... It's four times 10 to the fourth times 60 plus j times six omega divided by four plus j times two omega times 100 plus j times two omega times 400 plus j times forming. Okay. So the first thing that we would like to do here is to put this in, the standard form that we have for the transfer function that allows us to more easily think about and generate the Bode plots. And so that means that, for the zeros and the poles...

**[0:01:57]** Right? Remember, zeros are where the numerator goes to zero, poles are where the denominator goes to zero. We want... These are all simple zeros and poles. So we want them to be of the form one plus j omega, divided by, whatever the zero or pole frequency is.

**[0:02:15]** Alright? And so if we do that for each of the zeros and poles, that are, in this expression and we pull all of the necessary constants out to, the front into an overall constant, then what we get is four times 10 to the fourth. Right? That's the constant that was, written in up here. Then from this zero, we pull out a factor of 60.

**[0:02:41]** And then what we're left with is one plus j omega over 10. And then in the denominator, from this four plus j times two omega, we pull out a factor of four. From the 100 plus j times two omega, we pull out a factor of a 100. And then from the 400 plus j times, four omega, we pull out a factor of 400. And then what we have left, for the simple poll factors are from the first one, it's one plus j omega over two.

**[0:03:23]** And from the second, it's one plus j omega over 50. And from the third, it's one plus j omega over a 100. Okay. And then these constants out here, alright, the ones that are contained in this dash line boundary here, if you multiply all these out, you get 15. Okay.

**[0:03:49]** So now if we look at the form of, this transfer function, then we can see that it has a simple zero at omega equal to 10. Alright. That's from this factor up here. And then we have simple poles and omega equal to... From this first factor, it's omega equal to two.

**[0:04:18]** From the second factor, it's omega equal to 50. From the third factor, I... It's omega equal to 100. So we have simple poles at omega equal to two, 50, and a 100. Okay.

**[0:04:32]** So so these will be helpful to us in identifying what are key frequencies in the Bode plots. Right? And and therefore, in the behavior of whatever circuit or other linear system has this transfer function. Okay? We also want to look at some of the limit...

**[0:04:53]** Limiting behaviors of the magnitude of the transfer function, which, remember, we called m, and then the phase, which we called phi. Alright? So I... For the magnitude, we can see that the magnitude at omega equal to zero. Right?

**[0:05:14]** When omega is equal to zero, then each of these pole or zero factors here goes to... It behaves basically as one. Alright? So then the magnitude is zero. It goes towards a constant, which is just this constant in front, 15, and we want to express that on the dB scale.

**[0:05:35]** Right? So it's gonna be 20 times the log base 10 of 15, which is 23.5 dB. Okay? Then, the magnitude at infinity. Alright.

**[0:05:56]** Alright. As omega goes to infinity, then this transfer function basically ends up going as we have one power of omega in the numerator, three powers in the denominator. So it ends up going as one over omega squared. So the magnitude as, omega approaches infinity is going to be... It's gonna go to zero or on the dB scale, it's minus infinity dB.

**[0:06:23]** Okay. So that is the magnitude. What about the phase? When omega is equal to zero, then these zero and pole factors basically, go to one, and we have a positive constant out here. So the phase at omega equal to zero is just zero degrees.

**[0:06:45]** And then the phase as omega goes to infinity, right, we're going to have in the numerator, we have j omega. In the denominator, we basically have j omega cubed. Alright? So we're going to have, j over j cubed, is, minus one. Alright?

**[0:07:08]** And the phase of minus one will be plus or minus a 180 degrees. Right? Depending on what the phase is as we approach, infinity. Alright? So we'll determine that, as we generate the Bode phase plot.

**[0:07:27]** Okay. So now with this information, we can go ahead and start, generating Bode plots. So we will first work out the Bode magnitude plot. K. So we're gonna plot the magnitude of the transfer function.

**[0:07:49]** This is going to be on dB scale. Alright? And we have omega on the horizontal axis. Alright? And we had three poles at two fifty and one hundred and one zero at 10.

**[0:08:09]** Okay. So among the key points here, right, we'll indicate omega equal to 10 and omega equal to 100, then omega equal to two would be somewhere like this. Omega equal to five would be somewhere like... Or sorry. 50, would be somewhere like that.

**[0:08:31]** Okay? And these are going to be key frequencies in the Bode magnitude plot. Okay. So we'll try to align things here like this. Okay?

**[0:08:47]** And then, alright, we have at, omega equal to zero, then, the magnitude was 23.5 dB. So let's mark that on, the vertical scale. Right? And so, what we have here is that... Alright.

**[0:09:12]** If if we are at frequencies below two, right, that's two radians per second, then, all of these zero and and, whole factors over here behave essentially as one. So the magnitude is going to be constant at 23.5. Alright. So let me... I'll draw this in green here.

**[0:09:38]** Okay. So it's going to be a 23.5 all the way up to two. And then, from two to 10, okay, then the numerator and these two, factors in the denominator will still behave as one. This is going to behave as j omega over two. Alright.

**[0:10:01]** So we're gonna go... This is going to go overall in the linear approximation as one over omega in terms of the magnitude. And so that will decrease at 20 dB per decade. Alright. So maybe something like this.

**[0:10:22]** Okay. So this is minus 20 dB per decade is the slope. Then between ten and fifty, alright, this factor here behaves as omega. This factor here behaves as omega. So they...

**[0:10:40]** In terms of the omega dependence cancel each other out. These two, behave as one. Alright? Because we're still below maybe equal to 50. And so, this basically goes as a constant.

**[0:10:59]** Okay. Then between fifty and one hundred. Alright. Then these two, again, cancel each other out. This behaves as one.

**[0:11:10]** This behaves as omega. So we have essentially one over omega. Alright? And so we're going to go something like... Maybe like this.

**[0:11:24]** So, again, the slope is minus 20 dB per decade. Okay? And then finally, when omega is greater than 100, then all these factors here, right, the omega dependent factors, the zero and the poles, will behave basically as omega. And so we will, this will behave as one over omega squared in terms of the magnitude. And so we will have a sharper slope here, alright, which is minus 40 dB per decade.

**[0:12:05]** Okay. So that is the magnitude plot. Alright? Let's look at the phase plot. K.

**[0:12:19]** The phase plot will be somewhat more complicated. Okay. So, we're gonna extend these axes a little bit farther. So this is now the phase that we're plotting, and, this will be zero degrees. I'll say this will be 90 degrees.

**[0:12:45]** This will be minus 90 degrees. This will be minus a 180 degrees. Okay? And let's see. Let's let's try to extend these out here like this.

**[0:13:08]** Okay. And then we have... Right. This is 10. This is 100.

**[0:13:17]** Say, this over here, this is one. And then, this might be point one here. And then, say a thousand out here, alright, we're gonna need a number of other points, here as well. So we have two. Alright?

**[0:13:38]** Because, that corresponds to... Let's see. I guess it was a pole, okay, at, maybe equal to two. And for the phase plot, that means that we're also going to need to mark that frequency divided by 10 and multiplied by 10. So we have point two here and then 20 here.

**[0:14:03]** Right? Then, we had, right, 10, as a zero. Right? So we already have one and one hundred mark. Then we had 50, alright, as a pole.

**[0:14:21]** So 50 was roughly here. So we're gonna need to mark five and then 500. Okay. And then our final pole was at omega equal to 100. And so we have 10 and a thousand marked here as well.

**[0:14:42]** Okay. So now, what we're going to do is we're going to, just sketch out, and I'll sketch it in blue. Okay. What the phase behavior... What the behavior of the phase is for each zero or pole.

**[0:15:04]** Alright? And so, for example, we had a a simple pole at... Or simple zero at omega equal to 10. Alright? So going back to the transfer function, that's this factor up here.

**[0:15:20]** Alright? And so we can see that the phase of this factor here when omega is very small, say, less than, one. Right, less than one tenth times the zero frequency, then this behaves as one. So it's phase is zero. When omega is very large, say, 10 times the zero frequency or larger, so a 100 or larger, then the phase is basically just given by this j.

**[0:15:49]** So it would be 90 degrees. Okay. So for the zero, this simple zero, the phase undergoes a transition from zero at, one, okay, to 90 degrees at a 100, and it's 45 degrees at the zero frequency itself. So try to draw this straight line here or approximately straight line like that. Okay.

**[0:16:25]** So that is the phase associated with zero, the simple zero at omega equal to 10. Now for the poles... Alright, let's think about the pole at omega equal to two. So that's this factor over here. Okay.

**[0:16:42]** So when omega is much less than two, say, less than point two, then the phase is zero because... Or the contribution of the phase to h of omega is zero because this just behaves as one. When omega is very large, much greater than two, so say 20 or higher, then this looks like just j omega over two in the denominator. So that'll contribute a factor of one over j or minus j to the phase. And the phase of that is...

**[0:17:18]** The phase corresponding to a factor of minus j is minus 90 degrees. Okay. And so for this simple pole at omega equal to two, then we're going to go from a phase of zero at point two to a phase of minus 90 degrees at 20, and it'll be 45 degrees at the pole frequency, which is two itself. So now I'll try to draw a straight line here like this. Okay?

**[0:17:54]** And then we'll have the same thing as what we just drew for the poles at fifty and one hundred. So for the pole... The simple pole at 50, we go from zero phase at five to minus 90 degrees at 500. It's 45 at 50. So we're gonna have something like this.

**[0:18:23]** Okay. And then finally, for the pole at 100, then we're going to go from zero phase at 10 to minus 90 degrees at 100, and it'll be 45 at, 100... Sorry, minus 45. Okay. So it'll look something like this.

**[0:18:49]** Okay. And then anywhere where we have not drawn these blue dash lines, then the phase is just I... It will continue as a constant at whatever the nearest point on the dot... On the dash lines is. Right?

**[0:19:03]** So up here, this would continue as a constant like that. This would continue as a constant like this and so forth. Okay. So, so I won't draw this because I... This is already going to be a very cluttered, diagram here.

**[0:19:20]** Okay. So now, alright, what we want to do is to get the total phase, alright, which I will draw in green. Then, basically, we just want to add all of these up, and we'll be able to check at the end, right, that, as the frequency goes to zero. So all the way on the left, the phase should be zero. As the frequency goes to infinity, then it should be plus or minus a 180 degrees.

**[0:19:51]** Okay. So, if we now just... Right. We can add up all these different contributions, to the phase. Alright?

**[0:20:00]** And, mostly the contributions will come from, the portions of these curves where the phase has a non zero slope with respect to frequency. That's why we only drew those sections. Okay. So for frequencies less than point two, then we're going to have basically the zero frequency behavior. K.

**[0:20:21]** So that's going to look like this. Okay. Then, between point two and one, then we're just going to have this. Alright? Because, the only thing that's contributing a change in the phase is, this simple pull at omega equals two.

**[0:20:49]** Right? So the slope over here is going to be minus 45 degrees per decade. Right? Because that's the slope that we get, in this linear approximation from a simple pole. Alright?

**[0:21:06]** Then, once we get to frequencies between now one and five, alright, we have minus 45 degree per decade slope here, a plus 45 degree per decade slope here. Those will cancel each other out and we'll just have a constant phase. Right? So this will be constant like this. So this will be at zero degrees per decade in case it's not, that apparent from the picture.

**[0:21:43]** Okay? Then between five and ten, right, we have these three, contributing to, the slope. Right? So we have plus 45 per decade, minus 45 per decade, and minus 45 per decade. So that is again going to start, going down at minus 45.

**[0:22:06]** Okay. That's terrible line there. So I'm trying to draw it like that. Alright. So this is now going at minus 45 degrees per decade.

**[0:22:25]** Okay. Then, from 10 to 20, right, we have now this one comes into play, right, from the, zero... Or sorry, the pole at 100. Right? So we have one plus 45 degrees per decade, three minus 45 degrees per decade.

**[0:22:46]** Okay? So this is going to go at minus 90 degrees per decade. Right? So it'll be a steeper slope, here. So this is minus 90 degrees per decade, okay, up to 20.

**[0:23:06]** And then, when we're beyond 20, then... Alright. This, pole at omega equal to two no longer contributes. Right? Because it's just gonna be to to the slope because it's just constant.

**[0:23:20]** So we have one plus 45 degrees per decade, two minus 45 degrees per decade. So this has gone from... And that will be the case from 20 to 100. Okay. So we're going to go at minus 45 degrees per decade from 20 to 100.

**[0:23:42]** Right? So that'll look something like this. So this is minus 45 degrees per decade. Okay? Then from 100 to 500, right, this is now leveled off, so it doesn't contribute anything, to the slope.

**[0:24:00]** So we have these two poles over here that are each contributing minus 45 degrees per decade to the slope. So that'll be a total of minus 90 degrees per decade. Alright. So maybe that'll be... Right.

**[0:24:17]** We'll label this here, minus 90 degrees per decade. Okay? And then, yeah, maybe I'll try to draw dots here between these transition points. Okay. And then from 500 to a thousand, then we will only have this one pole.

**[0:24:47]** The pole at omega equal to 100 contributing to the slope. It's gonna contribute minus 45 degrees per decade to the slope, and that will end up bringing us down to a 180... Minus a 180 degrees. So here, the slope is minus 45 degrees per decade. And then the phase will just be constant at that value for higher frequencies.

**[0:25:19]** Okay. So, this sketch here is what the phase, Bode plot looks like. Okay? And, as we walked through it, you can kinda see how we constructed it, alright, by just taking into account the contributions of each individual, simple zero or pole, and then just adding them together. Alright?

**[0:25:46]** And that got us this full plot over here. Okay. So what are the key points in this first example of constructing a Bode plot. Right? So so, basically, what we did was, we wanted to write the transfer function.

**[0:26:05]** Right? And the specified in the problem, this is the voltage transfer function. Right? We wanna write this in the standard form that was given in class or that's described in Ulaby. Okay?

**[0:26:26]** And by writing this in the standard form. So, basically, some overall constant in front and then various factors that are either zeros or poles with the constant leading term being one, that makes it more straightforward to generate the Bode plots from that standard form of h of omega. Then the next thing that we did was once we had h of omega in that standard form, we identified... And eventually in the plots, we marked, all the poles and zeros that we found in h omega. Right?

**[0:27:15]** And then, right, to generate the magnitude plot... Alright. Basically, what we did was we noted that the the way the linear... This simple linear straight line approximation works is that the transition, okay, from the limiting behavior. That is the behavior corresponding to omega going to zero to the behavior corresponding to omega going to infinity.

**[0:27:52]** Right? The transition from those two regimes of behavior. Okay, this occurs exactly at each zero or pole. Right? So it's an abrupt transition from the low frequency limit to the high frequency limit at each zero or pole at the zero or pole frequency.

**[0:28:22]** Alright? And then we saw that the effects of each pole or zero on the magnitude plot. Alright. These can be added directly to each other. Okay.

**[0:28:51]** And that applies specifically when we're working on the dB scale, right, which is basically the log, the common log of the transfer function. And those contributions are additive, right, because the contributors, the zeros and the poles and the constants, are factors in h of omega. But when we take the log, right, if we take the log of some product, it's just the sum of the logs of the individual factors. Okay. So that's why these different contributions can be just added to each other in the magnitude plot on the dB scale.

**[0:29:32]** Right? And then we also can check the limiting behavior of the magnitude at zero and, infinite frequency. Okay. So, that's for the magnitude plot. Now for the phase plot, alright, it was a little bit more complicated.

**[0:30:08]** So in the phase plot, alright, what we did was, we had to mark as we did in the magnitude plot all the poles and zeros that we have in h of omega. But then in addition, we also, marked the pole or zero frequency divided by ten and ten times the pole or zero frequency. We mark those points on the frequency axis. Right? Because those are significant points in, the phase plots.

**[0:30:54]** And then what we said was that for each pole were zero. Okay? Then we said that the omega going to zero, the low frequency limit, behavior, this occurs when the frequency is less than the pole or zero frequency divided by 10. And the high frequency limiting behavior, This occurs when the frequency is greater than 10 times the pole or zero frequency. And we have just a linear transition, in between.

**[0:31:57]** Okay. So, for a simple zero or pull, right, we saw that the phase shift changed by 90 degrees, right, plus or minus 90 degrees depending on whether it is a zero or a pole respectively. And then, so that meant that since the transition occurs over two decades, right, then it's half that amount or plus or minus 45 degrees per decade. That's the slope. Alright?

**[0:32:22]** And then, what we did was to sketch, the phase for each zero or pole. Then we added these together. Okay. And we really only, were concerned with the regions of non zero slope since I... The phase will remain flat outside that region.

**[0:32:52]** It won't contribute anything to the overall phase load. Right? And then, again, we can check to confirm that we have the right limiting behavior, alright, for the phase at zero frequency and the phase at very high frequency. Okay. So...

**[0:33:17]** And that was basically the process that we went through in order to generate the Bode plot in that particular example or the Bode plots. Okay. So now keeping all this in mind, let's look at the next example. Alright, where the transfer function is, one plus... Oops.

**[0:33:44]** J times point two omega squared times 100 plus j times two omega squared divided by j omega, the quantity cubed times 500 plus j omega. Okay. So for this... Right. So now the first thing that we wanna do, as we did before is to put this in standard form.

**[0:34:11]** Alright. So here we already have a leading one. Alright. Here we have a leading 100. So we wanna pull that factor out.

**[0:34:18]** And it's a 100 squared because this is a second order zero. So we have 100 squared. Then we have this factor here. It's one plus... Oops.

**[0:34:34]** One plus j omega times point two, which is the same as j omega over five. And then from the second factor, the second order zero, it's one plus. And then when we pull out the factor of, the two factors of 100, we get j omega over 50 squared. Okay. And then in the denominator, alright, we don't have to pull anything out of this.

**[0:34:57]** And then from this factor here, we pull out a factor of 500. Alright. So we have 500 times j omega cubed times one plus j omega over 500. Alright? And this constant out in front, which encompasses the 100 squared over 500, that is equal to 20.

**[0:35:27]** Okay. So now if we look at this... Alright. Let's look at the limiting behavior for the magnitude. So say the magnitude at zero frequency.

**[0:35:38]** Right? At zero frequency, then the numerator... Alright. These zero terms will just go to one. This simple zero...

**[0:35:48]** Simple pole in the denominator will go to one. But we also have this third order pole at the origin. Right? So this is gonna go overall as basically one over omega cubed as omega goes to zero. So that is going to, become infinite.

**[0:36:07]** Alright? And then the magnitude at infinite frequency, right, in the numerator, it's gonna go as omega to the third. Right? Sorry. This was a squared over here.

**[0:36:26]** Right? Because we had the square up here. I forgot to write that down. So in the numerator, this is gonna go as omega to the fourth. In the denominator, this is also gonna go as omega to the fourth.

**[0:36:36]** So this is just going to approach a constant. Alright? And that constant is go... So it's going to be the following. Right?

**[0:36:46]** If we go directly to the dB scale, it's gonna be 20 times the log of whatever constant this whole thing approaches. Right? And so it's gonna have this leading factor here, which is 20. Alright? And then we're going to have, one fifth squared from here, and then one fiftieth squared over here.

**[0:37:13]** And then down here, we're going to have, one over 500. So that becomes 20 times 500. Right? One over one over 500 is just 500. And then in the denominator, we have five squared from over here, and then we'll have a 50 squared from here.

**[0:37:34]** So times 50 squared. Okay. And if we multiply all this out, calculate the log and multiply by 20, we get that this is minus, 15.9 dB. Okay. So that's the limiting behavior.

**[0:37:54]** As the frequency goes to infinity, it approached then the magnitude of the transfer function approach is a constant. Right? Minus 15.9 dB on the on the dB scale. Okay. The other thing, that we wanna note here is, alright, what were the, zeros and poles?

**[0:38:18]** Alright. So if we look at this transfer function here, we can see that we have now second order zeros and omega equal to five and fifty. So let's write that over here. So we have second order zeros at omega equal to five and fifty. Alright.

**[0:38:43]** That's in radians per second. And we have a simple pole at omega equal to 500, and we have a third order pole at omega equal to zero. So we have a third order pull at omega equal to zero, and then we have a simple pull at omega equal to 500. Okay. So we wanna keep all that in mind.

**[0:39:19]** Now let's go and look at the phase. Okay. So say the phase add very low frequency as omega goes to zero, right, that's going to be... Alright. This...

**[0:39:34]** These factors in the numerator will just go to one. This will go to one here. And so we're gonna have one over j omega the quantity cube. In terms of the phase, that's basically a factor of one over j cubed or one over minus j, which is just a factor of j. Right?

**[0:39:51]** So the phase of j is 90 degrees. Okay. And then finally, as the frequency goes to infinity, right, then, we're going to have... Right? Each of these zeros and poles will basically go in terms of their j and omega dependence.

**[0:40:15]** Right? They're gonna go to j omega to the fourth in the numerator and j omega to the fourth in the denominator. Right? So the j's will cancel each other out and the overall phase will be zero degrees. Okay?

**[0:40:31]** At very high frequency. Okay. So now we can take all of this information and generate the Bode plots. Alright? So let's look first at the Bode plot for the magnitude.

**[0:40:55]** K. So this is the magnitude of omega on a dB scale. Alright? And let's see. We'll draw the axis here.

**[0:41:07]** Okay. And we have we have a a pole, a third order pole at the origin. We're not gonna be able to draw the origin on, the scale, but, we also have a second order zeros at omega equal to five and fifty and a simple pull at omega equal to 500. So call this one, and then say we'll call this five fifty, 500, we'll draw 5,000 out here. This is omega, and we'll draw maybe point five here.

**[0:41:55]** Okay. And so we want to mark five fifty and five hundred. Okay. And remember as omega goes to infinity, then, the magnitude goes to... It approaches minus 15.9 dB.

**[0:42:29]** So let's just draw that, say, here. Minus 15.9 on the dB scale. Okay. So now... Alright.

**[0:42:38]** We will draw the magnitude plot in green. So at high frequency, which for our purposes, for the magnitude plot means above 500, then the magnitude is just gonna be flat at minus 15.9 dB. Okay. And then, if we are between fifty and five hundred... Alright.

**[0:43:10]** Let's go back to, the transfer function here. Then between fifty and five... So we're below 500. So this is gonna behave as one. And then all of these will behave in the high frequency limit.

**[0:43:26]** So going as j omega. Right? So we have basically omega to the fourth in the numerator, omega cubed in the denominator. So that's gonna go as omega, and, it's going to be a 20 dB, per decade slope. So that would look maybe something like this.

**[0:43:48]** So the slope here is 20 dB per decade. Alright? Then between five and fifty. Alright. Now this is going to be in the low frequency limit.

**[0:44:08]** This is the low frequency limit. These two are in the, high frequency limit. So we have omega squared over omega cubed. That's one over omega. So the slope is gonna be minus 20 dB per decade.

**[0:44:19]** So that is going to look like this. Okay. So this slope here is minus 20 dB per decade. Okay? And then finally, when we go below five, a frequency of five, radians per second, then all these factors here will be in the low frequency limit, so they'll behave as one.

**[0:44:51]** And we just have a one over omega cubed. Alright? So one over omega cubed is going to have a slope of minus 60 dB per decade. So that's gonna look, say, something like this. Alright.

**[0:45:07]** So this slope here is minus 60 dB per decade. Okay. So this is what the Bode magnitude plot looks like. Okay? And, basically, the way that we arrived at it was we started off, where the magnitude is constant.

**[0:45:31]** Alright? And then in each regime where we... Each frequency range where we know that the behavior will be different because we're crossing some zero or pole frequency, then we just figured out what the slope would be in each of those frequency ranges, and then we constructed the plot accordingly. Okay. So now, let's go ahead and try to generate the phase plot.

**[0:46:03]** So we're gonna draw the axis... Phase axis over here. So that's the phase, and let's draw the frequency axis like this. Okay. So the axis will be at zero degrees, and then we'll have, say, 90 degrees, 180 degrees, 270 degrees, 360 degrees, and we'll go to minus 90 degrees here.

**[0:46:52]** Alright? And then the frequencies that we're going to want to mark are point five, five, 50. Try to line them up with the magnitude plot. 500 and then 5,000. Okay.

**[0:47:19]** And let's try to draw... We'll draw some dash lines, right, so that we can keep track of these. Yeah. I can see here that, it would have been, helpful if I had selected some background, that is more like graph paper, if that's available. Okay.

**[0:47:51]** But, anyway, we'll continue with this. So now, right, what we want to do is just figure out what the different contributions are from the zeros and the poles. Right? So at omega equal five, right, we have a second order zero. Okay.

**[0:48:20]** And so, that's going to... That's this term over here. So at, very low frequency, say omega less than point five, then the phase of this will be zero. Okay. And it'll...

**[0:48:34]** So it'll contribute zero phase to the transfer function. And very high frequency, that is omega greater than, say, 50, which is 10 times five, then, this term here will dominate. When we square it, we get j squared or minus one. That'll be a phase of a 180 degrees. Okay?

**[0:48:55]** And so, what we will get then is from that one, we'll do these in blue. So we'll have a contribution that goes from zero phase to a 180 degrees between five... Or between point five and fifty, and will be at the midpoint 90 degrees in between. K. So, that second order zero will give us a contribution like this to the phase.

**[0:49:33]** Okay. Then we also have a second order zero to omega equal to 50. So by the same reasoning, right, then the phase will go from zero at frequency for this factor here. The phase will go from zero at frequencies below 50 over five. So that's below, five to a 180 at frequencies of 10 times 50 or 500 and higher.

**[0:50:00]** Okay. So, we're gonna go from a phase of... Alright. So that's a zero at 50. So we're gonna go from zero phase at five to 180 degrees at 500, and it'll be 90 degrees at the midpoint.

**[0:50:22]** So that'll be something like this. Okay. And then we have this simple poll at omega yield to 500. For a poll, we're going to go from a phase of zero at omega less than, 500 over 10, so less than 50, to a phase of... It'll be 90 degrees or j in the denominator.

**[0:50:53]** So minus j or minus 90 degrees overall to h of omega. That's the contribution to the phase. At frequencies greater than 10 times 500 or 5,000. So we'll go from zero here to minus 90 here and 45 at the midpoint. So let me try to draw approximately straight line here for the phase like that.

**[0:51:25]** Okay. And then for the third order zero at omega equal to zero, Right? That is this factor here. Alright? That phase is constant.

**[0:51:41]** Okay? It doesn't go, undergo a transition from a low to high frequency. Alright? That's characteristic of a zero or a pole at the origin. We just have this overall factor of j cubed in the denominator, which is minus j in the denominator or just j in the numerator.

**[0:52:00]** So that gives us an overall contribution of 90 degrees. Right? That's the phase of j in the numerator to h of omega. So that means that at very low frequency that is below point five, then our starting phase will be 90 degrees. Okay.

**[0:52:23]** So, we have this here first. Right? That's constant. Okay. And then, as we go from point five to five, alright, then we have just this slope contributing, and it's a slope of 90 degrees per decade.

**[0:52:45]** So that's gonna take us to here. So this slope here is plus 90 degrees per decade. Okay. Then between five and fifty, we have these two phase factors that are each contributing a slope of 90 degrees per decade. So that's a total of a 180 degrees per decade.

**[0:53:09]** So that's gonna take us to here, right, to three sixty. Okay. So here, this slope is a 180 degrees per decade. Okay. So now that's taking us to three sixty.

**[0:53:26]** Alright. When we get to three sixty, then what we'll do is we'll... Right. Three sixty is equivalent to zero. So we'll just bring that back down to zero here.

**[0:53:39]** Okay? And then we'll continue from there. Between fifty and five hundred, we have, plus 90... A slope of plus 90 degrees per decade here and minus 45 degrees per decade here. So that's gonna be a slope of 45 degrees per decade.

**[0:54:02]** And then from 50 or 500 to 5,000, then we will have just this here which is minus 45 degrees per decade. So that's gonna bring us back to here. K. So this is minus 45 degrees per decade. And then above 5,000, then the phase will just be constant at zero.

**[0:54:29]** And we see that, in fact, that is the correct limiting behavior that we deduced from h of omega. Okay. So so those are the Bode plots up here for the magnitude and then down here for the phase. Okay. So from this part of the problem, what were some additional key points?

**[0:55:03]** Okay. One, alright, is that when we constructed the magnitude plot, right, notice that we started over here at high frequency. And we did that because we knew that the magnitude was going to be constant. Alright? There.

**[0:55:23]** And it's just easier to construct the plot starting from a known specific value. Alright? And so, the first point to note here, it's that... Is that it's often easier to construct, the magnitude plot. Okay.

**[0:55:50]** Starting from a limit, okay, or a point, for which the magnitude goes to some constant, right, that we know and can calculate. Right? In this case, it was the high frequency limit. Okay. And the same applies to the phase.

**[0:56:32]** Okay. And then the second additional point that is beyond the points that we noted for part a is that, we saw here, right, the phase actually extended beyond 360 degrees. Alright? So if we go outside the range from minus three sixty to three sixty, then, what we wanna do is to bring, the phase plot back to zero because zero, three sixty, and minus three sixty are all the same, alright, in terms of, their trigonometric behavior. Right?

**[0:57:07]** So if the phase applied... Or if it extends outside the range from minus three sixty to three sixty, alright, then, what we will typically do is translate. And what you want to do, right, is to translate the phase from one of those extremes, right, whichever one, it was at. So plus or minus three sixty to zero, and then go from there. Okay.

**[0:57:50]** So, so that's part b of this problem. Alright? Now we will go to part c. Okay. I think parts c and d are a little bit shorter.

**[0:58:05]** Okay. So part c here. Alright. H of omega, it's equal to eight times 10 to the minus two times 10 plus j times 10 omega divided by j omega times 16 minus omega squared plus j times four omega. Okay.

**[0:58:33]** So here again, right, we will put this into a standard form. So we have our constant a times 10 to the minus two. Right? Then from this zero, we will factor out a 10, and that'll leave us with one plus j omega. And then in the denominator, we will factor out a 16 from this quadratic pole here.

**[0:59:00]** So we have a factor of 16, and then that's times j omega times one and then plus j omega over four minus and then... Or sorry. Plus j omega over four, the quantity square. Alright. And these constant factors in front...

**[0:59:36]** Alright. If we multiply those out, right, we have eight times 10 to the minus two times 10, that's point eight. Point eight over 16 is one over 20. Okay. So, looking at this transfer function, we see that we have a simple zero at omega equal to one.

**[1:00:00]** And then, we have a simple poll at omega equal to zero. Okay. And then we have a quadratic pole at omega equal to four. Okay. So that's what we have for this transfer function.

**[1:00:28]** So now let's look at the low and high frequency limiting behavior for, the magnitude of the transfer function. So at zero frequency or very low frequency, right, then the zero and the pole both behave as one. So we just have this omega in the denominator. So this is going to infinity. Alright?

**[1:00:52]** And then, the magnitude at very high frequency, frequency approaching infinity, right, it's going to go as omega over omega q. Right? So one over omega squared. So that's going to go to zero, which is minus infinity on the decimal scale. Okay.

**[1:01:16]** In addition... Alright. So this does not really help us that much in terms of identifying a point or a range where the magnitude is constant. Right? Where we can sort of figure out where the magnitude goes vertically, right, on the Bode plot.

**[1:01:37]** However... Alright. If we look at the frequency range between one and four, then this term, the zero, is gonna be in the high frequency range. So it's gonna behave as j omega. That cancels out with this j omega down here.

**[1:01:55]** Here, since omega is less than four, this is going to be in the low frequency limit, so it'll behave as just one. So for omega between one and four, then the transfer function will behave just as a constant, which as we see here is going to be one twentieth. So what we also see is that m of omega is going to be, again, this is in linear approximation, approximately equal to 20 times the common log of one over 20, which is minus 26 dB. And we will have that behavior for one being less than or equal to omega, being less than or equal to four. Okay.

**[1:02:44]** So that will allow us to figure out where, the magnitude plot goes on the vertical scale. Now we can look at the phase. So the phase at very low frequency zero. Right? These two factors here, the zero and the quadratic pole are gonna behave as one.

**[1:03:03]** And then we'll have this, one over j, right, in the in the transfer function. So that has a phase of minus 90 degrees. Alright. And then finally, the phase at a very high frequency is the frequency goes to infinity. Alright?

**[1:03:26]** Then we're going to have... This will behave as j omega, then I'll cancel out with this j omega. So we're gonna have j omega, the quantity squared over here as the dominant term. So that is a factor of minus one. It doesn't matter whether it's in the numerator or the denominator.

**[1:03:42]** So it's going to be plus or minus a 180 degrees. Okay. And we'll see which of those it is when we construct the Bode phase plot. Okay. So now with this information in hand, then, we can go ahead and calculate or generate the Bode magnitude and phase plots.

**[1:04:07]** Okay. So oops, let's see. For the magnitude plot, alright, we will just draw the axis over here. K. So this is the magnitude plot on the dB scale.

**[1:04:27]** Alright? And we'll draw the frequency axis here. Okay? And so, we have a simple zero at omega equal to one and a quadratic pole at omega equal to four. Alright.

**[1:04:45]** We're not gonna be able... Since the frequency is also on a log scale, we're not gonna be able to get zero on it. Alright. So for the simple zero at omega equal to one, alright, we're eventually gonna wanna have point one, one, and 10. Alright?

**[1:05:06]** Then we have a quadratic pole at omega equal to four. Right? So that would be maybe somewhere here. Okay. So then we're gonna have, point four.

**[1:05:20]** Okay. And then 40, something like that. Okay. Okay. So now I...

**[1:05:31]** Right. For the magnitude plot, here, the key points are omega equal to one and omega equal to four. Okay. And we're gonna have, say, minus 26 dB. Alright?

**[1:05:52]** Because we know that for omega between one and four, then in the linear approximation, the magnitude m of omega on the dB scale is gonna be minus 26 dB. Alright. So that is here. Draw this to make it clear that those are aligned. Okay.

**[1:06:15]** And then when we are at frequencies above four, Right? So that's basically in the high frequency range. Then, we're gonna have... This is in the high frequency range, so it'll go as j omega. That'll cancel out with this.

**[1:06:31]** We're gonna go as one over omega squared. Alright? And so that is going to give us a slope of minus 40 dB per decade. Alright. So that's gonna come down pretty steeply like this.

**[1:06:50]** Okay. And then for frequencies less than one, Alright. Then this will behave as one. This will behave as one. And so we're just gonna have a one over j omega.

**[1:07:10]** So that is going to have a slope of minus 20 dB per decade. Right? So one decade is one to point one, and we'll say that's, you know, maybe here. Okay. And so I'll draw this, and then we just continue that.

**[1:07:30]** So the slope here is minus 20 dB per decade. Okay. So that is the Bode magnitude plot. Okay. And so now we wanna generate the Bode phase plot.

**[1:07:54]** K. So this is the phase. Alright? And let's draw the axis here. Okay.

**[1:08:07]** So we're going to mark, point one, point four, one, four, 10, and 40, okay, on the frequency axis. And then, we'll mark 90 degrees. This is zero. And then we'll have minus 90 degrees and minus a 180 degrees. Okay.

**[1:08:45]** And so now... Alright. And we will just mark all of these. Okay. And then what we're going to do here as we've done in the previous two parts is we're going to sketch out the contributions of the phase from each of the zeros and poles, and then we'll just add them together.

**[1:09:23]** Okay. So we have a simple zero at omega equal to one. Alright. That's this factor over here. So it undergoes a transition from a low frequency, say omega less than point one, a phase of zero, since it behave...

**[1:09:41]** This factor just behaves as one, to at high frequency, say omega greater than 10 times one or 10 to a phase of 90 degrees. Okay. So we're gonna go from zero at point one to nine degrees at 10, 45 in the middle. Okay. And then we have a quadratic zero and omega equal to four.

**[1:10:20]** Alright? And so that is going to go from a phase of zero at a very low frequency, say, omega less than point four, which is four over 10, to a phase of it'll be a 100 and... Minus a 180 degrees. Right? At a phase, at, frequencies above 10 times four or 40.

**[1:10:44]** Okay. So we're gonna go from 0.4 to minus a 180 at 40, and it'll be minus 90 degrees at at four. Right? We know that it goes, to minus one eighty. Right?

**[1:11:08]** Because at omega equal to four, right, this j omega over four squared, right, becomes minus one. That cancels out with this one. And so all we have left is j over here, and that's gonna be a j in the denominator. Its phase is 90 degrees or minus 90 degrees. Okay?

**[1:11:28]** Because it's minus j in the numerator. So we know that this is at minus 90, and so at 40, it has to be minus one eighty. Okay. So let me draw this dash line. Okay.

**[1:11:46]** Alright. So now, right, we have... Oh, one more thing. Add low frequency. Right?

**[1:11:56]** So below point one, the phase is minus 90 degrees. Okay. So that's where we will start. So at minus 90 degrees, below point one. So it's basically like this.

**[1:12:12]** Okay? Then, from point one to point four, right, we have only this contributing. So that's at plus 45 degrees per decade. That's gonna be something like this. So this is plus 45 degrees per decade.

**[1:12:35]** And then, from point four to 10, alright, then, we have plus 45 degrees per decade minus 90 degrees per decade. Alright? So that is minus 45 degrees, per decade. Alright? So that will bring us back to here.

**[1:13:01]** Okay. And then, right, it's gone from one to 10. It's another 45 degrees. So maybe to... So back to here.

**[1:13:14]** Okay. So we'll continue that line. And then out here from 10 to 40, then it's going to be, just minus 90 degrees per decade as the slope. So something like this. So here, this is minus 45 degrees per decade.

**[1:13:45]** Here, it is minus 90 degrees per decade. Okay? And then I... Once we're above 40, then I... It should continue...

**[1:13:58]** It's just constant at minus a 180 degrees. Alright? And I... So that's what we have over here. Okay.

**[1:14:09]** So that is this part, part c. Alright? And I think there aren't really any additional key points that are important to note here. It's... It was quite similar to what we did in the previous two parts, except that this time, we have a quadratic, pole right here.

**[1:14:34]** And so we just had to think a little bit more about what the limiting behaviors of that would be, how the phase changes and so forth, but, you know, using the ideas that we highlighted in the first two parts. Okay. So now we are finally on part... Oops. We're finally on part d, which is the last part of this problem.

**[1:15:01]** Okay. So here, the transfer function is four times 10 to the fourth times omega squared times 100 minus omega squared plus j times 50 times omega divided by five plus five times plus... Oops. Plus j times five times omega times 200 plus j times two omega cubed. Alright?

**[1:15:39]** So, again, we wanna take this and just put it in the standard form. Okay. So, we have the constant four times 10 to the four. Alright. Then, we're gonna factor out a 100 from here, from the quadratic zero.

**[1:15:59]** So we have a factor of a 100, then we have omega squared, and then one plus... And then it's j times omega over two. That's from the j 50 omega, minus or plus j omega over 10 quantity squared. Okay. And then in the denominator, we'll factor out a five from this first pole.

**[1:16:32]** And then we'll factor out a 200 cubed from this third order pull over here. Alright? And then what we have left will be one plus j omega and then one plus j omega over 100 q. Okay. So this is now in, the standard form.

**[1:16:57]** And this collection of constants out in front, Right? If we calculate that out, then it turns out to be one tenth. Okay. So, if we look at this, what we have here is we have this omega squared in the numerator. So we have a second order zero at omega equal to zero.

**[1:17:28]** Then we have this factor here, which is a quadratic zero at omega equal to 10. So we have a quadratic zero at omega equal to 10. Alright. Then we have here a simple pole at omega equal to one. And then finally here, we have a third order poll at omega equal to 100.

**[1:18:05]** Okay. So those are the poles and zeros. Okay. And then if we look at the limiting behavior of the magnitude, the magnitude at very low frequency, zero is, these factors here go as one. This is omega squared.

**[1:18:26]** So this will go to zero, right, which is, remember, minus infinity dB. Okay? Then the magnitude at very high frequency as omega goes to infinity. Right, this numerator is gonna go as omega to the fourth. The denominator will go as omega to the fourth as well.

**[1:18:49]** Okay? And so, what we're gonna have here is that, the magnitude goes as... Right. It's gonna be 20 times the natural log of... We're gonna have, one tenth.

**[1:19:13]** Alright. And then we're going to have, from this factor over here, we're going to have one over 100. Alright. One over 10 squared. And then from this down here, we're going to have, 100 cubed.

**[1:19:38]** Okay. And so if we multiply all this out, this is 10 to the sixth divided by 10 to the third. Okay. And so, this is going to be 10 to the third over here. We take the natural log...

**[1:19:53]** Sorry. The common log of that, that's three. And we have three times 20, that is 60 dB. Okay? And then the...

**[1:20:07]** For the phase... Alright. The phase at zero, okay, is equal to... Alright. We have...

**[1:20:19]** These are all one. This goes to omega squared. This is positive. So the phase at zero is zero degrees. And then the phase at very high frequency, right, as the frequency goes to infinity is going to be, we have j squared over here, which is minus one.

**[1:20:39]** And then we have j to the fourth in the denominator, which is just one. So, we have an overall minus sign in the transfer function, and so that's going to have a phase of plus or minus 180 degrees. Okay. So now... Alright.

**[1:21:00]** This is what we need in order to construct the Bode plots. Okay. So let's... As usual, we will construct the magnitude plot first. Okay.

**[1:21:18]** This is on dB scale. Okay. And, our starting point is going to be 60. Alright? So let's draw our frequency axis here.

**[1:21:39]** And then we have, the key points on the frequency axis are, we have a, simple pole at omega equal to one, quadratic zero to make it equal to 10, and a third order pole at omega equal to 100. Okay? And so, we're gonna wanna go from, say, point one, make this one, 10, 100. Make this 1,000. K.

**[1:22:15]** So that's omega. And then let's see. We're gonna start off at very high frequency. This is going to be at 60. And so we'll mark these points here.

**[1:22:38]** Okay. And then, our poles and zeros are at one ten and one hundred. Okay. So now at, at very high frequency, right, the magnitude, we saw is 60. K.

**[1:23:10]** So that's gonna be, say, up here. Alright? And we'll draw this dash line here to show that these are aligned. Okay. And then when we're between omega equal to a 100 and omega equal to 10.

**[1:23:33]** Right? So we're below omega equal to a 100. So this factor, just becomes one. Alright? This is omega squared.

**[1:23:40]** This is omega squared. So that's omega to the fourth in the numerator. This is omega in the denominator. So that is omega cubed. So this is gonna have a positive slope of 60 dB per decade.

**[1:23:53]** Alright. So for one decade, that'll be like this. This is 60 dB per decade. Okay. Then, for omega between one and ten, then this is going to be...

**[1:24:15]** This is gonna be in the low frequency, regime. So this will be one. This will be one here. And so we'll just have omega squared over, omega. So that's going to go as omega, which is plus 20 dB per decade.

**[1:24:38]** K. So here, this is 20 dB per decade. Alright? And then, say, below that. Okay.

**[1:24:55]** Then this goes to one. These are also, behaving in the low frequency limit. So so we'll take those as one. So we just go as omega squared, which, has a slope of 40 dB per decade. Right?

**[1:25:08]** So maybe that's... We'll take a point one that'll be minus 60 then. And so the slope will look something like this. So this is a slope of 40 dB per decade. Okay.

**[1:25:24]** So this is the magnitude, Bode plot. And so now we wanna do the phase plot. K. So this will be the phase. Alright?

**[1:25:44]** And let's draw the axis here. Right? So we have point one, one, 10, 100, and 1,000. And we'll mark all of these on the phase plot. Okay.

**[1:26:30]** And then for the actual phases, we'll take this to be zero. So the axis is at zero, and we'll go to 90 degrees, 180 degrees, minus 90 degrees, minus one eighty, minus two seventy. Okay. So now, we'll go back to our zeros and poles. Okay.

**[1:27:07]** So so the zero at omega equal to zero, that's just the omega square. That doesn't contribute any change to the phase and it and it contributes the constant of zero to the phase. Right? So we don't have to really worry about that as far as the phase plot is concerned. Alright?

**[1:27:22]** Then, at omega equal... For the, simple pole, omega equal to one, then we go from a phase of zero for omega less than, one over 10, less than point one, to a phase of minus 90 degrees, at omega equal to 10. Alright? So as usual, we'll draw that in blue. So from point one to zero to 10, it's at minus 90, and it's at minus 45 at omega equal to one.

**[1:28:00]** So that's gonna look like this. Then we have at omega equal to 10, we have the quadratic zero up here. So that's gonna go from a phase of zero at omega less than equal to one to a phase of a 180 degrees at... So just a factor of minus one at omega greater than or equal to 100. Okay.

**[1:28:35]** So we're gonna go from zero to a 180 degrees at 190 degrees at 10. K. So that looks like this. And then finally, we have the third order zero, or sorry. Third order pole in the denominator, from this factor in the denominator over here.

**[1:29:03]** So this is gonna go from a phase of zero at omega equal to 10 to a phase of, minus 270 degrees. That's j cubed, right, in the denominator at, omega equal to a thousand. Right? So we're gonna go from zero degrees here to minus two seventy at a thousand. Right?

**[1:29:28]** And then it'll be halfway at omega equal to 100. K. So that's gonna be something like this. And then for the overall phase plot, alright, we just add these together noting that I... In the low frequency limit, the phase is zero.

**[1:29:57]** Okay? So we have a phase of zero up to point one. Okay? And then, from point one to one, right, we have only this contributing. That's a slope of minus 45 degrees per decade.

**[1:30:19]** And it's gonna go like this. So that's minus 45 degrees per decade. Then, from one to 10, we have minus 45 degrees per decade from here and plus 90 degrees per decade from here. So that's plus 45 degrees per decade overall. So that's gonna bring us up like this.

**[1:30:44]** So this is plus 45 degrees per decade. Alright? Then from 10 to 100, we have plus 90 degrees per decade minus 135 degrees per decade. So that's gonna be minus 45 degrees per decade. So that'll bring us to minus 45 here.

**[1:31:11]** So this is minus 45 degrees per decade. Okay. And then finally, from 100 to a thousand, we have just minus 135 degrees per decade from, this third order pole here. So that's gonna bring us down to minus one eighty. So that'll be like this.

**[1:31:36]** This is minus 135 degrees per decade. Okay? And then, for omega greater than a thousand, this will be flat at minus a 180 degrees. Okay? And that is the entire, Bode phase plot.

**[1:32:00]** Okay. And again, right, we basically constructed this, both of these plots using the same ideas and key points that we had highlighted in the earlier parts of this problem. Okay. So that is, this entire example, which hopefully gives you a very good idea of how to construct Bode plots from transfer functions and how to think about and understand them. Okay.

**[1:32:30]** So I'll stop the recording here now.
