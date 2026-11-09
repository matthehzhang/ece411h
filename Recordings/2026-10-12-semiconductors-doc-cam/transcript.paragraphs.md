# 2026-10-12-semiconductors-doc-cam

Deepgram general-nova-3 2025-07-31.0, request 01a1b02e-41b0-7f33-b9fb-66267e18951d, audio 79.7 min.

**[0:00:03]** Okay. So I have just started the recording. As you may have seen in the announcement on Canvas or as you can probably tell now, our technology mode will be a little bit different today. My tablet computer that I usually teach from, came up with a blue screen this morning, saying that the encryption policies for UT had changed, and now I cannot get into my, to my laptop or to, to the tablet. So, we are going to attempt to use the the camera today.

**[0:00:45]** And then, hopefully, the Zoom recording will be will be okay as well. So, anyway, having said that, there are a few announcements as usual. I guess the the camera does not capture the full width of, the paper here, so I'll try to adjust for that as we, as we go forward. So first of all, as you may have seen, the first semester exam has been graded. The results were quite good.

**[0:01:16]** There's a summary here and then more detailed information on, the Canvas site. So the mean was, 71.3, median 74.5, standard deviation was 12.8, and the range was 40 and a half to 92 and a half. There were 25 people who took the exam. The regrade requests on Gradescope are open until 5PM this Friday. If you would like to submit a regrade request, then, you know, please provide a detailed explanation.

**[0:01:48]** But also, look at the section of the announcements on the regrade requests and read it carefully. The basic idea is that if we just made a mistake in the grading, then, that's easy to correct. But, if you have a question about, you know, something that, amounts to how much partial credit that you should get, for a given partially correct answer, then, since the grades are all curved, the most important thing is that everyone's exam is graded consistently, according to the same rubric. So, if we apply the rubric incorrectly, then... Get rid of this box here.

**[0:02:30]** If we apply apply the rubric incorrectly, then we will correct that. But if you feel that the rubric that we applied to everyone did not give you enough credit, then, you know, we applied the same rubric to everyone. So in fairness to the class as a whole, we have to continue to apply to apply the same rubric to everyone. Let's see. So...

**[0:02:54]** Okay. This week's recitation is important, because it will cover, material that will be important for you to do problem set six. Okay? And it is complementary to rather than repeating what is... What we're doing in class.

**[0:03:12]** Third announcement is that my office hours this Wednesday will be in the afternoon, 02:30 to 4PM, instead of, in the morning after class as usual because, there were some, meetings that were put on my schedule. Location is still in my office, E R 3 Dot 802. And then the last announcement here is that I I may be late to my office hours today because, after class, I will probably stop by our IT office, to see if they can get me back into my tablet. Okay? And then I should be in my office after that.

**[0:03:55]** Okay. Any questions on any of this? Okay. Any questions from our last, class meeting? Remember, we had started a more detailed discussion of semiconductors in our last class meeting before the exam.

**[0:04:14]** Okay. If not, then we will pick up from, where we left off, and I will try to keep everything on the screen here. Okay. So let's see. Yeah.

**[0:04:29]** So we may not cover quite as much material, today. Alright. So, if you remember from last time, what we were doing was, we had just started talking about, what we call the Fermi distribution function, right, which is a mathematical function that tells us, what is the probability that an electronic state, an electronic level at a given energy is occupied by an electron. Right? So for last time...

**[0:04:58]** K. Right? What we had was the Fermi distribution function. Like, a little mark. Oops.

**[0:05:15]** Yeah. That's the edge. Okay. And so this was a function f of e. Alright?

**[0:05:24]** And it would tell us what's the probability that a state at a given energy is occupied by an electron. So this is given by one over e to the energy minus what we call the Fermi level over Boltzmann's constant times the temperature plus one. Okay? So case of b here is Boltzmann's constant, right, which is basically, it's a constant that allows us to convert, temperature into energy. Alright?

**[0:06:04]** So it's one point three eight point three eight one times 10 to the minus twenty third joules per Kelvin. T here is the temperature of the system, I, in Kelvin. And then e sub f here is what we call the Fermi energy or the Fermi level... Oops. Or the Fermi level, and it's basically the energy at which the Fermi distribution function is equal to one half.

**[0:06:51]** Okay? And so so this is the Fermi distribution function. What we wanna do next is to see how this function, allows us to think about and calculate, say, the concentration of electrons and holes, that we have, in a semiconductor. So any questions to hear? Okay.

**[0:07:16]** So... Alright. We'll do that. Let's sketch this out. Alright?

**[0:07:24]** We'll first look at what happens at low temperature. Okay? And so we're gonna make a sketch here of the Fermi distribution function f of v, okay, as a function of energy. So energy, here is on, the vertical axis, and then we'll say that the Fermi level, right, is here. Now if you look at the form of the Fermi distribution function, this is an f here, then you can see that the the range of the Fermi distribution function is from zero to one.

**[0:08:08]** Right? So, if the energy is very high, e is very large, much higher than e f, then we have a large exponential in the denominator, and the Fermi distribution function is close to zero, which makes sense. It tells us that the probability of finding an electron at a at a very high energy state is extremely small. Okay? And in contrast to that, if the energy is very low, say, below the Fermi level, then we have, the exponential of some negative quantity, and then that ex...

**[0:08:44]** That exponential is very small, and the Fermi distribution function is very close to one. Okay? And that also makes sense. It tells us that states at very low energy are very likely to be occupied by by electrons. Okay.

**[0:08:57]** So that's kind of the intuition there. Right? And so, the Fermi distribution function ranges from zero to one. Okay. It's equal to one half at, the Fermi energy.

**[0:09:13]** And then I... What happens is it decreases exponentially, right, as we go to very high energies, and then it kind of exponentially approaches one as we go to low energies. Alright? So, that's kind of a sketch of the Fermi distribution function. And if we look at the Fermi distribution function up here again, right, you can see that, right, in the exponent, you have the energy minus the Fermi level over, k sub b times t.

**[0:09:45]** Right? So what that means is that the range of energies over which the Fermi distribution function is, you know, significantly different from zero or one, is just within a few times, k sub b times t of the Fermi level. Okay. So if we, look at our sketch again, right, basically, what that means is that the width of this transition here is sort of a few times k sub b times t. Alright?

**[0:10:23]** So that's what the Fermi distribution function looks like. Alright? And then as the temperature increases, that transition will become, it'll occur over a wider range of energies. Alright. So any questions on this?

**[0:10:39]** Okay. So now what we can do is we can see what this implies about the concentrations of, electrons in the valence band... Or sorry, holes in the valence band and electrons in the conduction band. So this is the valence band edge energy. This is the conduction band edge energy.

**[0:11:00]** Our conduction band states are up here, and our valence band states are down here. And so what this sketch tells us is that, if we are at energies close to... Or or in the valence band, right, those are, the way that we've drawn it, they're quite far below the Fermi level. And so these states here in the Fermi level, or in the valence band will be essentially completely filled with electrons, and the states in the conduction band will be just about completely unoccupied. The the conduction band will be empty.

**[0:11:41]** Okay. So the valence band is nearly full of electrons. Oops. And then the conduction band is nearly empty. Okay?

**[0:12:06]** So so the fact that the transition region of the Fermi distribution function is very narrow, and the Fermi level is near the middle of the band gap, which has to be the case because, the concentration of electrons and holes have to be equal to each other, then, right, that then tells us that, we have, hardly any electrons in the conduction band, hardly any holes in the valence band. Alright. So any questions on that? What we wanna do next is to see what happens as we increase the temperature. Okay.

**[0:12:44]** So if we come back here, then let's, look at what happens if we have a high temperature. Okay. So in this case, right, we are again going to sketch out the Fermi distribution function. Okay. The Fermi level will take to be at the same energy.

**[0:13:09]** Fermi distribution function goes from zero to one. Right? And we will again have our conduction and valence band stays like this. Okay? And what happens is that at higher temperature, right, the width and energy of this transition will increase.

**[0:13:40]** Right? It'll... Sort of the slope going this way will get more shallow. Okay. So we'll have something that maybe looks like this instead.

**[0:13:57]** Alright? Because... Right? The temperature is higher so that with that transition occurs over a wider range of energy. And what happens then is that this makes the probability of finding some electrons in conduction band states, are at high energy, it makes that probability higher.

**[0:14:26]** Right? So we'll have some electrons in the conduction band like this. And then correspondingly, there will be some empty states in the valence band, but most of the valence band states will still be will still be occupied. So now we have some electrons in the conduction band, and we will have holes, remember, which are empty states in the valence band. Okay.

**[0:15:11]** So any questions on, these basic ideas so far? Yes. I guess, the diagram on the right side has a region where electrons cannot be there. Right? So Yes.

**[0:15:30]** Right. Like, how do we write this? Oh, okay. So so the Fermi distribution function only tells us what is the probability that a state at a given energy will be occupied by an electron. It does not imply anything about whether there are states at that energy or not.

**[0:15:53]** Okay? What we have over here, right, this is the picture now in a semiconductor of how the states are distributed in energy. Okay? So if there are no states to be occupied over here, even though the probability of a state at this energy being occupied is nonzero, right, if that state were present, if the state is not present, we won't have any electrons in this range of energies. Does that answer your question?

**[0:16:24]** So we can draw the graph for each, like, infinitesimally thin slice of energy level at, like, band, I guess. So, say, if you draw the graph at EC, it will be slightly different from EC plus 0.1. So, so in the recitation section, today, then, Darsh will probably talk a little bit about this idea of density of states, alright, which is at a given energy, alright, which could be, you know, in the conduction band or in the valence band or in the bandgap, this, quantity of the density of states tells us how many states are there basically at that energy. Okay? And then it's normalized to the volume.

**[0:17:21]** Right? So it becomes a concentration of states. Right? And then there's a per unit energy also because, you know, it's a function of energy. And so what that looks like is...

**[0:17:38]** Alright. If I had a different color here on the tablet, then I would do this in a different color, but we'll do it, on black here. So this is the density of states. Okay? And it will look...

**[0:17:50]** Although I draw this in a dash line. Right? It's zero in the band gap, and then it ends up looking, roughly speaking, something like this. Okay. So fewer states right at the, near the extrema of the bands and then increasing as you move farther into the bands.

**[0:18:10]** Okay. And then, you know, roughly speaking, this density of states, which is how many states there are, multiplied by the Fermi distribution function, which is what's the probability that the states will be occupied by an electron, that product will then tell you how many electrons do you have at that energy, and then you would integrate over energy in a given band, say, in the conduction band to get the total number of, or concentration of electrons. Okay. Yes? So is this, dense state graph continuous then, or are there just...

**[0:18:47]** Are there, you know, many discrete, I guess, substates within each state, each one with a specific energy level, or is it continuous through? Okay. Yeah. So, so there's a very detailed answer to that question, which I won't go into, all the details of. But, roughly speaking, if you had an infinite semiconductor crystal, this would be a continuous function.

**[0:19:17]** Okay? In any real crystal that is a finite volume, then, it won't be continuous because the, right, the energies at which you can have... Actually have states are... It's a discrete spectrum. Right?

**[0:19:35]** There are discrete values of the energy, but they're extremely close together in energy. So we essentially look at it as a continuous function of energy. Okay? Its derivative does not have to be continuous. Okay?

**[0:19:50]** So you have a... You know, the way I've drawn it here, it has a cusp down here, where the derivative is not continuous. So that can happen. But we we basically think of the density of states as a continuous function but not necessarily differentiable. Okay.

**[0:20:06]** Any other questions? Okay. Let's see. So let's put some numbers on this. I'll go to another sheet here.

**[0:20:23]** Okay. We kind of sketched out what, what this looks like. The edges here. Alright. And, so now, you know, how many, at a given temperature, what does that really correspond to in energy?

**[0:20:45]** How does that compare to the width of the energy band gap and things like that? Right? So we wanna put some numbers on this now. Right? So we're gonna look at, say, at room temperature, which we will take to be 300 Kelvin, alright, then I...

**[0:21:07]** Right. If we calculate Boltzmann's constant times the temperature, right, this is... Remember, it's 1.381 times 10 to the minus 23 joules per Kelvin, and then it's times 300 Kelvin. Alright? Now if you look at that, alright, then you can see that you're going to get...

**[0:21:34]** Alright. Bringing in a number that's of order 10 to the minus 20. Right? Now, you know, maybe four times 10 to the minus 20 or something like that. Okay?

**[0:21:45]** And, you know, it's sort of inconvenient if... Right? And that'll be in joules. Right? But it's it's sort of inconvenient to have to carry around this 10 to the minus 20 all the time.

**[0:21:57]** Right? It would be better if there were some unit of energy that we could use that had an order of magnitude, for for this quantity that's, say, closer to one, and that also had some, you know, nice, easy physical interpretation, alright, in the context of semiconductors and electricity and the like. Okay? And there is such a unit of energy that is the, most common unit of energy that is used for semiconductors, and it is called the electron volt. Okay?

**[0:22:36]** And so an electron volt, remember that, right, the, charge of an electron, right, e, its magnitude is 1.6 times 10 to the minus 19 coulombs. Right? And then we also have electrostatic potential or voltage, which is in units of volts. And so, you know, if we think about current being carried by electrons that have this particular magnitude of charge, and then we think of potential as being in volts, right, we know that the potential energy of an electron at a particular potential or at a particular voltage is the charge of the electron times the voltage. Alright?

**[0:23:25]** So, so given that, a natural unit of energy to use is the amount of energy that it takes to, change the potential of an electron, right, or something that has the same magnitude of charge as the electron by one volt. Okay? And that unit of energy is what we call the electron volt. Okay? And, if we think about what that...

**[0:23:55]** What an electron volt should be, in joules, Right? For... If you take the product of charge and voltage, right, and your charge is in coulombs and your voltage is in volts, then you'll get joules. Okay? But now if we're saying, alright.

**[0:24:14]** We're gonna consider our fundamental charge to be 1.6 times 10 to the minus nineteenth coulombs, then, one electron volt is going to be the charge of the electron, point six times 10 to the minus nineteenth coulombs times one volt. Alright? That'll be 1.6 times 10 to the minus nineteenth joules. That is one electron volt. Okay.

**[0:24:39]** So, we can convert this to electron volts. Right? So e v, lowercase e, uppercase v, is how we write electron volts, and that is 1.6... Actually, point six zero two times 10 to the minus nineteenth joules. Okay, by the reasoning that I just described.

**[0:25:03]** And then if you calculate that, that's going to be point o two five nine electron volts. Okay. So Boltzmann const... Boltzmann's constant times temperature at 300 Kelvin at room temperature is about... It's...

**[0:25:23]** This is roughly one fortieth of an electron volt. Okay? What this also means is that Boltzmann's constant. Right? All it's doing for us is it's converting temperature to energy.

**[0:25:40]** Right? The way that we specified it originally, not sure why this is slightly out of focus here. Wonder if we can do better. Okay. Yeah.

**[0:25:52]** So that's better. Alright. Boltzmann's constant really converts temperature into energy. The way that we originally defined it, it was we had energy in joules, but now, it makes a little more sense for us to have energy and electron volts. Right?

**[0:26:14]** And so, to get it in electron volts, we just take Boltzmann's constant here in joules per Kelvin and multiply by this factor over here, which converts the joules to electron volts. Right? So Boltzmann's constant, we can write it as 1.381 times 10 to the minus 23 joules per Kelvin. We could also write it as 8.617 times 10 to the minus five electron volts per Kelvin. Okay.

**[0:26:48]** And electron volts here. Right? Right? This is what we call this is what we call an electron volt. Okay.

**[0:27:00]** And it is basically... It's the energy that's required, to increase the potential, okay, of an electron charge magnitude, alright, which is 1.602 times 10 to the minus nineteenth coulombs, right, by one volt. Alright. That's how we define, the electron volt. Okay?

**[0:27:44]** And... Oops. Right? It is equal to, 1.602 times 10 to the minus nineteenth joules. Okay.

**[0:28:01]** So any questions on any of that? Okay. So so this didn't seem, you know, perhaps quite as efficient as we could have made it if we look at, how much energy and electron volts corresponds to room temperature. Right? We've got about one fortieth, okay, which is still a little bit far off from one, but not as bad as 10 to the minus 20.

**[0:28:26]** Okay? But, you know, what we really wanted to compare it to is the size of the energy band gap. Alright? And if we look at what are the typical energy band gaps of semiconductor, say of silicon, the band gap of silicon is a little over one electron volt. Right?

**[0:28:50]** So it turns out, somewhat coincidentally, right, that the electron volt is a very natural unit both physically and also a very convenient unit to use in terms of the magnitudes that you get for band gaps and things like that. Right? So the energy band gap okay, which is the conduction band edge energy minus the valence band energy, right, of silicon, it's around 1.1 electron volts. It's, 1.1 electron volts at room temperature. Okay.

**[0:29:29]** And that is, it's much larger. Right? It's 40 times, the amount of energy associated with k sub e times c right at room temperature. And so what that also tells us is that if we have a pure and structurally perfect semiconductor, then, what's going to happen is that the concentrations of electrons and holes will be very small at room temperature. Right?

**[0:30:00]** They'll be down by a factor of, you know, roughly e to the minus 20 or so. Okay. So the consequence of this started on a new page here. Okay. Bless you.

**[0:30:23]** Right. So the consequence... Or one of the consequences of this comparison between energy associated with room temperature and band gaps is that in... If you have a compositionally pure and structurally perfect semiconductor, right, what happens is that the concentration of electrons n and the concentration of holes p, right, these are typically very small unless, the temperature is very high. Okay?

**[0:31:12]** And very high would not be, you know, for a material like silicon, that would not be typical. Okay? So given that electrons and holes are what actually carry current, in a semiconductor, then, we can ask, alright. Well, I... You know, if this is true, then how do we actually, get more electrons and holes, and or holes into a semiconductor?

**[0:31:39]** Alright? And from the picture that we had earlier, the Fermi distribution function and the energies of the connection and valence bands, right, then to get more electrons or holes, basically, at at a given temperature, say, basically, what we need to do is we need to move the Fermi level either closer to the conduction band or closer to the valence band. Alright? That picture then also tells us that, say, if we move the the Fermi level much closer to the conduction band, we'll have a lot more electrons in the conduction band, but we'll have even fewer holes in the valence band. Alright?

**[0:32:18]** If we have, the Fermi level very close to the valence band, we'll have more holes in the valence band but even fewer electrons in the conduction band. Right? So the basic idea is that, to increase n or p, right, to levels that are useful for devices. Right? What we need to do is if we think about things in terms of the Fermi level, we need to shift the Fermi level closer to either the valence band edge energy or the conduction band edge energy, but we cannot do both of those things simultaneously.

**[0:33:12]** Alright? So, we can get either many more electrons or many more holes, but, at a given temperature, we can't get both. Okay. So any questions to hear? Okay.

**[0:33:26]** So what we wanna do next then is to talk about ways of basically shifting the Fermi level. Okay. So this is now shifting the Fermi level. Okay. And so the key method that we want to introduce to do this is what's called doping, which is taking some of the the atoms in a semiconductor crystal and replacing them with a different element.

**[0:34:02]** Okay. That's what doping really is. Right? So the question that we're asking here is, can we shift the Fermi level, alright, to be closer to either the valence band edge or the conduction band edge so, that we get concentrations of electrons and holes not equal to each other. And most typically, either the electron concentration being much greater than the hole concentration or the hole concentration being much greater than the electron concentration.

**[0:34:44]** Okay? And, you know, we're sort of asking this as a rhetorical question. The answer to this, of course, is yes. We can do that. And the way that we are going to talk about next of doing that is by introducing what we call impurity atoms.

**[0:35:00]** Right? Some element other than what we originally have in the semiconductor into the crystal that has a different number of valence electrons. Right? So that it shifts the the balance between the electrons and the holes. Right?

**[0:35:15]** So this can be accomplished by what we call doping, which is the introduction, okay, of impurity atoms. Into the semiconductor crystal. Okay. So any questions to hear? Okay.

**[0:35:59]** So what we're going to do then is... Alright. We're gonna think about a silicon crystal. Okay. So let's consider a silicon crystal.

**[0:36:22]** And remember when we first talked about, semiconductor crystals generally, we said that, silicon has four valence electrons. Right? And then each of those valence electrons, helps to form one bond to one of, silicon's nearest neighbor atoms in the crystal. Right? So, if we think about, you know, what would be a good way to basically increase the concentration of electrons, right, in the crystal by introducing some atom into the crystal other than silicon, then, right, if we wanna increase the number of electrons, kind of the, the logical thing to do would be to introduce some atom that has more valence electrons than silicon, right, say five valence electrons instead of four, then that extra electron, can go into the conduction band.

**[0:37:22]** Alright? And it will increase the concentration of electrons in the conduction band. And that's basically what's done in doping to to increase the electron concentration. Alright? So the idea then is that silicon has four valence electrons.

**[0:37:42]** Alright? And then what that means is that if we have an impurity atom or impurity atoms that have, say, five valence electrons, if we introduce these into the crystal... So, for example, this could be phosphorus, right, or arsenic. Okay. If these are introduced, if we do that in place of some of the silicon atoms, right, then what happens is that you'll have a bunch of extra electrons around, and those will end up going into the conduction band.

**[0:38:48]** Right? So what'll happen is that the crystal it'll have an excess of electrons, And these will occupy, the conduction band states. Okay. I... And so what that means then is that the Fermi level will be closer to the conduction band edge energy than to the valence band edge energy.

**[0:39:40]** Okay. So if we now draw some pictures, right, to illustrate this, right, let's imagine that we have now, say, an arsenic atom. Right? And it's surrounded. We'll just draw the nearest neighbors by silicon atoms.

**[0:40:00]** Right? Each of these silicon atoms will be able to contribute one of its valence electrons to bond with the arsenic. The arsenic will contribute one valence electron to bond with each of its nearest neighbor silicon atoms. But then since arsenic has five valence electrons instead of four, what happens is that there will be... Right.

**[0:40:29]** There's still one extra. Okay? So now we have an extra electron. Okay? And that extra electron, right, if we think back now to kind of this picture of the bonding states being, the valence band states and the antibonding states being, conduction band states, right, this arsenic atom, right, all its bonding states are already filled.

**[0:40:59]** Right? We've already formed these four bonds. So this extra electron, the only place that it can go, is into the antibonding, orbital or, equivalently, the conduction band. Okay. I...

**[0:41:14]** And so if we draw the picture of this using the energy bands, right, what's happening here is that this is the conduction band edge energy. This is valence band edge energy. This is the valence band. So the conduction band. Right?

**[0:41:37]** The conduction... The valence band states are already completely filled because we have, our four valence electrons from arsenic already, forming the bonds, and so we're going to have that extra electron going into the conduction band. And if you have a bunch of these arsenic atoms present, then you'll have, right, more electrons in, the conduction band. Alright. So that's the basic picture.

**[0:42:07]** And if we now think about this in terms of the Fermi level, right, what we've done is we have increased the probability of finding electrons in the conduction band. Alright, it turns out that at the same time, we will have also decreased the probability of finding, holes in the valence band because when we have all these extra electrons around, then if we had any holes in the valence band, some of these electrons would, like to lower their energy so they'll go and, fill the whole state, the empty states in the valence band. So we'll also be decreasing the concentration of holes. Alright? So those things together mean that if we now look at the Fermi distribution function...

**[0:43:05]** Okay. And the Fermi level, right, that means that the Fermi level has to be up here closer to the, conduction band edge. Okay. And so the Fermi distribution function now... Right?

**[0:43:30]** It's gonna look something like this. Right? This should be one. Right? And so, right, you can see with the Fermi level closer to the conduction band edge, the probability of having electrons in the conduction band is going to be higher.

**[0:43:44]** Probability of having holes in the valence band will be lower. Alright? And that's the basic idea of how doping to create electrons in the conduction band works. And this particular variant of doping, where we introduce impurity atoms that have extra valence electrons so that they go into the conduction band, we call those impurity atoms in the semiconductor. We call them donors because they're essentially donating one of their valence electrons to the conduction band.

**[0:44:21]** Right? So impurity atoms alright, that provide extra electrons, these are called donors. Okay. So so any questions on this idea? Yes.

**[0:44:52]** Yeah. Why phosphorus or? Oh, so I... So so your question is really, you know, what if if one extra is good, maybe then two extra is even better. Right?

**[0:45:08]** So why don't we do that? Is that No. I guess my question was just, like, why ours versus... Like, I guess, once they have one extra, like Mhmm. Why one versus another?

**[0:45:17]** But, yeah, I guess why two extra too? That's also a good question. Okay. Yeah. So so to answer the question that you actually asked first, for any given dope and type, there, you know, there are often multiple impurity multiple impurity elements that you could introduce that that will work.

**[0:45:36]** Right? So both for n type doping and for donor doping in silicon, right, phosphorus and arsenic, will both work, and they both work well. And so they are both pretty commonly used. If you go farther from... The farther you go from, sort of the the row in which the semiconductor element, is located in in the periodic table, then, right, if you go farther down, then you get to basically physically bigger atoms.

**[0:46:12]** Okay? And, then you're trying to stick this big atom, right, into a space where there was previously a small atom, and, that ends up not working as well, because it produces some distortion of the lattice around it. That affects the electronic states and, and so forth. You know, if you tried to go, up, then, sometimes that can work, but sometimes there are issues with that also, you know, because of the size mismatching related, related issues. That...

**[0:46:47]** That's one of the, the significant influences. Yes. And then for the second question as to, okay. If five is good, why don't we have, introduce something that has six? Then, right, what happens is that if, say, we introduced some, atom that has six, valence electrons, alright, like selenium, or or something like that, then what will happen is that one of those electrons will, go pretty easily into, the conduction band.

**[0:47:29]** Right? But then... Then it's moving around. It can move around through the crystal. Right?

**[0:47:35]** Then what you have left is a positively charged ion, in the lattice because it's lost one electron. It started off as neutral, lost one electron, and then, yeah, and then it becomes positively charged. That makes it harder to get that second electron off. Okay. So so, actually, one more or one fewer, if you want holes is what works best.

**[0:48:05]** Any other questions? Okay. So move on to another page here. Okay. Well, I really hope that, the IT people can fix my tablet by Wednesday.

**[0:48:26]** Okay. So so this is how donors work. Right? Getting extra electrons into the, conduction band, then, alright, that also suggests sort of a logical strategy for getting holes into the valence band. Right?

**[0:48:42]** Instead of introducing impurities that have one extra valence electron per atom, to get holes, then what you should do is to introduce impurity atoms that have one fewer valence electron per atom. So three rather than four. Alright? So, alright, this is conversely in comparison to donors. Right?

**[0:49:06]** If we have purity atoms with three valence electrons, right, of these, per atom. Right? So this could be, say, boron, right, or aluminum. Right. These are introduced.

**[0:49:44]** Then what happens is that, the crystal will now have two few electrons. Right? Because you've replaced an atom silicon that has four valence electrons with an atom that has three, say, boron or aluminum. Right? So the crystal, it has too few electrons, okay, to form all its bonds, right, or equivalently to occupy the valence band states.

**[0:50:24]** And so what will happen is that extra holes will be present in now the valence band and Fermi level will be closer to the valence band edge, than to the conduction band edge. Okay. So, alright, if we again draw our picture right now, let's consider a, an atom of boron. It's in the silicon crystal, so it has these four silicon atoms as nearest neighbors. Each of these silicon atoms will contribute, one valence electron to form a bond to, the boron.

**[0:51:20]** The boron has three valence electrons, so it can form three of these bonds. Alright? But then when it tries to form the fourth, there's no fourth valence electron to form that bond. Okay. So you have a missing electron here.

**[0:51:48]** Okay. And since that electron is one that would have formed a bond, so it would have gone into a bonding orbital, then that empty state is going to be in the valence band of the semiconductor. Okay. So, if we draw our band picture, right, then we have, again, the conduction band and the valence band. We have our conduction band states up here, valence band states down here, then what is going to happen is that we're going to have some empty states in the valence band.

**[0:52:33]** The Fermi level will be down close to the valence band because that corresponds to having a higher probability of finding empty states in the valence band. And the Fermi distribution function, alright, will now look like this. This is the Fermi level. This is zero, and this is one. Alright?

**[0:53:02]** And... Alright. The Fermi distribution function will look something like this. Right? So we're gonna have, a higher concentration of holes, than we have of electrons.

**[0:53:23]** Yes. Question? Does the hole have intrinsic physical value, or is it simply a mathematical thing we have cut... Term we have come up with to represent? Like, the...

**[0:53:37]** Was it the one half mark? Or... Yeah. Yeah. Yeah.

**[0:53:41]** So it is... I mean, partly, it's defined mathematically, right, as being, the energy at which the probability of a state being occupied by an electron is is one half. Right? So equal probability of being occupied or unoccupied. Alright?

**[0:53:59]** You know, in that sense, it's sort of arbitrary. Right? We could have chosen some other, you know... One half is for something that goes from zero to one, and one half is kind of the least arbitrary point that we could pick, but we could have picked something else. It is actually physically significant in a number of ways.

**[0:54:19]** One of them is that, as we'll talk about later, if we have, say, semiconductor materials that have... You know, one of them has donors, one of them has, you know, has more electrons, one has more holes, we bring them together to form what's called a p n junction, then, what has to happen is that the Fermi level has to be the same in equilibrium. It has to be the same across that entire structure. Right? So I...

**[0:54:52]** The the Fermi level does represent sort of a quantity that has to be preserved in equilibrium across an entire structure for two, systems that are in equilibrium with each other. Alright? So there is physical significance to it as well. Does that answer your question? Okay.

**[0:55:10]** Any other questions? Okay. So, so now we've seen, how we create electrons in the conduction band, holes in the valence band. Here, right, if we have... Right.

**[0:55:23]** So impurity atoms that essentially remove electrons or, equivalently, that provide holes. Right? These are called acceptors. Right? Because, essentially, what's happening is that, you know, the way the holes will move around is that, some other, electron in the bonding state.

**[0:56:04]** Right? If you have an empty state over here, there's some probability that this electron could move over here. And then once that happens, there's some probability that maybe an electron over here can move into the resulting empty state, and that's basically how the holes move around in in the valence band. Okay. And then one other piece of terminology that we'll introduce is that when we introduce donors, alright, that is to get extra electrons, then we create what's called an n type semiconductor, meaning that the electron concentration is greater than the hole concentration.

**[0:56:50]** If we introduce acceptors, then we create what's called a p type semiconductor, where the concentration of holes, p, is greater than the concentration of electrons, n. Alright? So we'll use these terms, pretty frequently as we, as we move forward. Alright. So any questions on any of that?

**[0:57:25]** Okay. Then, the last thing that we'll say about this before we move on then is... Alright. We've talked, you know, kind of in general terms about, you know, introducing, impurities to create more electrons or more holes, but it's also useful to know, well, you know, how... What concentration of, impurities do we typically have to introduce in order to, sort of be able to create a concentration of electrons or holes that is useful for, typical electronic devices.

**[0:58:07]** And, actually, it turns out that the fraction of atoms that, you have to replace, say, in silicon or most other semiconductors, is actually very small. Right? So the fraction of atoms that will be replaced by impurities, right, is typically very small. Right? So, for example, if we look at a crystal of silicon, right, and doping it by replacing some of the silicon atoms with impurities...

**[0:58:54]** So a crystal of silicon, it has around five times 10 to the 22 atoms per cubic centimeter. Right. Silicon atoms per cubic centimeter. Right? We can compare that to the typical concentrations of impurities that are introduced into silicon when...

**[0:59:23]** Or other semiconductors when doping. So the typical concentrations of impurities, right, introduced in doping. Alright. These are, generally of the order of 10 to the maybe fifteenth to 10 to the 20 impurity atoms per cubic centimeter. Right?

**[1:00:08]** So, you know, roughly one in, 500 or so at the high end to one in, you know, 10 to the seventh or 10 to the eighth at the low end. Alright? So these are really... Even at the high end, it's a relatively small fraction that you're replacing. Yes.

**[1:00:26]** Oh, I get that. I can't just, you know, have all of the atoms be be impurity atoms. And then I get, like... You know, obviously, there's the other side of... If you have no impurity atoms, you you can get less current through it.

**[1:00:41]** But where's kind of, like, the the middle where you can kind of, like, I don't know, I guess, maximize your Oh, yeah. So that's an interesting question. So that when you introduce impurities, you know, roughly speaking, there are two things that are gonna happen. One is what we just talked about that you get... Say, if we talk about donors, right, you get more electrons into the conduction band.

**[1:01:09]** Right? And so if that were the only thing that happened, then I... Right? The way that you maximize the conductivity, say, right, is just you get as many of the impurities in as possible until, it starts looking not like silicon with some isolated impurities, but like an alloy of silicon, right, with, whatever the impurity is. And it starts to look like that at...

**[1:01:39]** You know, once you get to, like, a significant fraction of 1% or higher, right, it starts to look more like, an alloy, right, rather than silicon with, some impurities. The other thing that happens is that the, if you think about, say, the electrons moving around in the semiconductor, then the electrons are negatively charged. Okay? But each of these dopant atoms that you've introduced, when, say, a donor gives up its electron to the conduction band, it leaves behind, a positively charged ion that's sort of bonded into the lattice. So it's sitting there.

**[1:02:20]** It's positively charged. And that positively charged ion will influence the motion of the electrons that are moving in the conduction band because you have a Coulomb attraction between them. Right? And that influence is called scattering. Right?

**[1:02:35]** You can think of it... Right? If you think of the electron as being like a ball, right, that's moving around, in the conduction band, then I... You know, it can, you know, bounce off of, you know, say, an impurity atom, where you can think of it roughly that way. And so its motion will be disrupted when it gets close to an impurity atom because the impurity atom has this charge associated with it.

**[1:03:04]** That's the biggest effect. Right? And, so then, what happens is as you introduce more donors, right, you're introducing... Or you're increasing the concentration of electrons, which increases the connectivity. But then you are also creating more scattering, which reduces the connectivity because the motion of the electrons is disrupted.

**[1:03:33]** And so those, have to be traded off. It turns out that decrease in mobility is somewhat smaller than the increase in electron concentration. So if you really want high connectivity, you still wanna have as high an electron concentration as possible. But there are other characteristics of devices that are very important that, depend very heavily on how easily the electrons can move, right, and what's called the mobility. Right?

**[1:04:07]** And and the mobility, right, that gets decreased as you increase the number of impurities. And so if you want a good device, you don't necessarily want to push the concentration of electrons to... And the connectivity to the limit, you wanna have, depending on the circumstances, different balances between, high electron concentration and high mobility. Okay. And and what is optimum depends on the specifics of that application.

**[1:04:40]** Any other questions? Okay. So now that we've talked about the basics of, you know, semiconductor structure, doping, and things like that, then what we wanna do next is to start applying this to devices, right, and thinking about how do we... How does this play into the way devices behave? Okay.

**[1:05:12]** And the device type that we will look at in detail here in three zero two or three zero two h, you look, in some detail at MOSFETs. Alright? What we're gonna do here is to look in more detail at, what's called the PN junction diode. Okay. And so I...

**[1:05:38]** You know, you may have seen in the circuit the diode circuit symbol. Right? It looks like this. We also introduced it a couple of classes ago. Alright?

**[1:05:49]** And, basically, you know, one of the very common ways of making a diode is to take a piece of p type semiconductor and a piece of n type semiconductor and put them together. Alright. Say like this. And then, the boundary region between these is what we call the PN junction. Okay.

**[1:06:17]** Or this structure overall, is often also called the PN junction. Okay. So now what we wanna do is to think about how this is going to behave based on what we have discussed so far. Alright? So if we first imagine, these two things being separate from each other, okay, they're not connected, then what we'd have is on the p...

**[1:06:48]** For the p type semiconductor, we have our bands like this, and we have more holes than electrons. So the Fermi level is going to be down here close to the valence band. In the n type semiconductor, okay, we have more electrons than holes, And so the Fermi level is going to be up here, close to the conduction band. Alright? So then the question is, what happens when we bring these two into contact with each other?

**[1:07:33]** Alright? And if you look at this, right, if you bring them into contact to each other... With each other, then all of a sudden, say, you have lots of electrons over here on the n side. You have very few over here on the p side. And so, right, just by diffusion, right, if you have lots of something over here and very few over here and things can move back and forth, then the concentrations will try to even out.

**[1:08:04]** Right? So so a bunch of these, electrons over here will diffuse on the n side will diffuse over to the p side. Okay? And then the same thing, will happen with the holes. They'll diffuse from the p side over to the n side.

**[1:08:18]** Okay? And what will happen then is that, right, near the junction... Bless you. Right? Then you'll have, you know, if if you do a thought experiment, imagine what happens when you bring these...

**[1:08:35]** Right when you bring these together, you'll start having these, electrons and holes diffusing. And then the question is, alright, what's the final state? Okay. And the final state is one in which the Fermi level, the probability of finding an electron or a hole at a given energy is the same in equilibrium across the entire structure. Because if it were not the same, then you would get some motion of the electrons or the holes, across the junction.

**[1:09:07]** Okay. So what happens here is that in equilibrium, right, then what happens is that the Fermi level has to be constant. Bless you. Across the entire device. Okay.

**[1:09:34]** And that's required in order for the current to be zero. Right? And in equilibrium, right, that's zero voltage. We also require that we have zero current. Okay?

**[1:09:44]** And so... See. I don't have quite enough room to draw it on the right here, so we'll draw it down below. Right? What'll happen then is that...

**[1:09:56]** Right now, the Fermi level is going to be constant across the entire structure. We're now gonna draw... What we're gonna do is we're gonna draw the band edge energy. That's a function of position in the p n junction. Okay?

**[1:10:13]** And we know that very far away from the junction, the semiconductor is going to have to look like a p type semiconductor. So it's gonna look like this, the Ohlins band conduction band. Very far away from the junction on the n side, it'll have to look like this. Right? It'll be...

**[1:10:45]** It'll look like an n type semiconductor. Okay? And then, right, these two have to connect with each other. Right? And so you'll have a transition that will end up looking basically like this.

**[1:11:09]** Okay? And so one of the things that happens that's very fundamental to the behavior of a PN junction diode is that you build up a potential energy difference between the p side and the n side. Alright? That's going to be, right, a charge... Electronic charge e times a potential we call v sub b I.

**[1:11:36]** V sub b I here, oops, is what we call the built in potential. Okay. And... Alright. Basically, what is happening here is that as the electrons are diffusing over to the p side, the holes are diffusing over the inside, then a bunch of the electrons will drop down to lower energy and fill these whole states.

**[1:12:09]** And what you will have left are the ionized dopants. Right? Acceptors on the p side, donors on the n side. Those ionized dopants, the ones that have given up their electrons or holes, will have charge associated with them. That charge will give rise to an electric field.

**[1:12:32]** Right? Because you have electric fields anytime you have charges. And then the integral of that electric field will give you a potential. So you'll have a potential difference then that builds up between the p side and the n side, and that potential difference basically prevents more diffusion from occurring so that once you've built up this potential difference, the built in potential, then in equilibrium, you will be able to keep this high concentration of holes on the inside and the high concentration of electrons on the p side because there's this... There are these barriers, to their diffusion.

**[1:13:10]** Okay. Yes? Is this b b I is related to, like, I guess, when the die breaks? You know? The other way?

**[1:13:19]** So, yeah, so, actually, it's it's not so much related to what you're referring to, which is the breakdown voltage when... Which is when you reply reverse bias. Right? Basically, negative charge... Or negative voltage to the p side.

**[1:13:34]** What it relates to instead is the voltage at which the diode turns on under forward bias. Right? So I... Right? If if you look at the diode like this, right, then you're applying...

**[1:13:54]** Right? You would typically apply positive volt... Right? Positive and negative... Positive voltage is the p side, negative voltage is the n side.

**[1:14:01]** And what happens is that, you know, for a given... For a diode made from a given semiconductor material, the current, as we will see in detail later, will increase exponentially as you start with voltage, as you start applying positive voltage to the p side. That's the turn on of the diode. Okay? And there will be a certain voltage.

**[1:14:30]** Right? If you look at the current voltage characteristic, on a curve tracer or something, right, it'll it'll increase exponentially, so it'll kinda look like this. And you'll... There'll be a characteristic voltage at which it looks like it's turning on. The diffusion creates this kind of dot, and then it's, like, kind of the opposite way.

**[1:14:48]** And then if we apply it, the, like... It's like a negative, I guess. And then when we apply positive voltage, it... Like, once you get to a certain threshold, you're canceling that VDI out. Is that Yeah.

**[1:15:00]** That's basically right. So what'll happen is if we go back to this picture down here, this is a little preview of what will happen, what we'll talk about next time. What happens is that as you apply positive voltage to the p side, right, then positive voltage decreases the potential energy for electrons. Right? So that basically means this barrier will get lower.

**[1:15:28]** And, you know, once it's slow enough, not, all the way to completely canceling out the built in potential, but getting within maybe, a couple tenths of a volt or something like that of doing so. Then the current due now to the diffusion of electrons that can now diffuse across the junction because the barrier is lower will become... Will start becoming very noticeable, and that's the turn on voltage. Right? So for a silicon, PN junction diode, the turn on, you know, very roughly is maybe around point six volts or so.

**[1:16:02]** And it is that
