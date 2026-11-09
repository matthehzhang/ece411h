# 2026-10-05-semiconductors-and-solid-state-devices

Deepgram general-nova-3 2025-07-31.0, request 01a1b00f-d5b4-7610-ace3-700b45baa6ae, audio 78.5 min.

**[0:00:03]** Okay. Let's go ahead and get started. Oh, so my tablet is trying to force a Zoom update, so we don't wanna do that now. Okay. So I just started the recording.

**[0:00:16]** A few announcements to start with as usual. The first one is that problem set five was due today, so hopefully everyone has turned that in. The solutions will be available later today, but I think we probably, or we may not have it graded by the time of the exam, but you have the solutions available to you, if you want. Second announcement is a reminder that the first semester exam will be, this Wednesday, okay, October 7. And so there's, additional information on the Canvas announcements.

**[0:00:52]** The things you should make sure to do in order to... Or in addition to preparing for the exam are that, you should make sure to use the, the dummy template that's been posted on Gradescope and Canvas to, test your scanning and uploading. And then, also, you should make sure to bring, printed physical copy, okay, that is on paper, of the answer sheet template to the exam. You'll write, the solutions to the exam on that printed answer sheet template. Alright?

**[0:01:27]** Third announcement is that for today's, recitation, that will be an exam review session. So, what Darsh will do is he'll answer any questions that you have. If you have examples of circuit problems that you'd like to go over, he can do that. And, depending on the time, he may do some of the problems from, some of the old exams that have been posted under, exam preparation materials. Okay?

**[0:01:52]** And then the last announcement is that, the sixth problem set has just been released. Okay. So that'll be due on October 21. Alright? And that problem set covers maximum power transfer and semiconductors.

**[0:02:08]** So problem set six is on material that you're not responsible for for this first semester exam, but you will be responsible for it for the second exam and the final. So any questions on any of this? Yes? So it's okay to take pictures, but there are many pages, right, to the template. So that's a lot of pictures, and the uploading may be slower.

**[0:02:44]** Also, our experience is that photographs are actually not as high resolution. They're harder to read than, scanned, PDFs. Okay? So, our pretty strong suggestion is to scan it and upload it as a PDF because the scanning apps are pretty good, and it'll be easier to read because the paper, sometimes it comes out as gray rather than white, and that can make the the writing harder to read. Yes?

**[0:03:23]** Should be very specific. Are there any, practices or, like, capacity gaps on Canvas? There are. There's a section on, Canvas called exam preparation materials, and there are three years of past exams, for all the different... For the first semester exam, second, and the final.

**[0:03:40]** So they have the exam questions. I think there are short answers, right, like numerical answers and things like that, or symbolic answers for the exams. And there's also, for each exam, a histogram of the score distribution for, the students who... For the class that took that exam so you can kind of assess what the difficulty of this... Of that exam was.

**[0:04:00]** Say that the previous exams are a fair representation of what this exam... Like as far as, like, content covers and, like, length and all that. So what I will say is that those pass exams are probably the best guide that you'll the best guide that you'll have available to you of what the upcoming exam might be like. But there are never any guarantees. Any other questions?

**[0:04:28]** Yes. Yes. You can use any calculator that does not have sort of communication and photograph capability. So you can't use your phone calculator app, but you can use, like, a graphing calculator and things like that. Yes.

**[0:04:51]** Any question that you have? Number s. Why Mhmm. The real part, the average, and the complex part, the p power? Oh, so...

**[0:05:07]** Well, we defined the complex power in the way that we did so that when we took the real part, we would get the average power. Right? So, you know, there are a variety of different kind of products of voltage and current, that we can define in the phasor domain, and we chose this particular definition to have the property, right, that when we take the real part, it would give us the average power. Right? If we had chosen to define some power quantity in some other way, then, you know, we would get the the average power in a different way.

**[0:05:49]** For the imaginary part, you know, it it ends up that the imaginary part of that complex power translates to the... Or is the peak power transferred. You know, it's it's basically because in order to have power transfer, you need the current and the voltage to be out of phase, right, to some degree, because, you only get that if there is an imaginary component to the impedance of the load. Alright? And, you know, the way that we have defined the complex power, right, the imaginary part turns out to correspond to the peak power that that is exchanged between the source and the load.

**[0:06:38]** Okay. Yes? I guess, do you have any tips for when to use, I guess, the definition of complex power? Yeah. But what that the complex conjugate by versus, like, the IRMS squared are, like, I guess, going through the the the problem set, there were definitely times where one method was easier than another, but I was a little bit unsure of, like, when to use each of those.

**[0:07:08]** I know they have to be the same thing, but not computationally. Sometimes one's easier. Yeah. I wouldn't say there's a hard and fast recipe, right, for doing it one way or the other. As you said, I...

**[0:07:24]** You know, one half v I star, right, or, you know, I r m s squared times the the impedance of the load. Right? They give you the same thing as they should. You know, if you if you have the current and the voltage already, right, then probably one half v I star is easier. If it is easy to calculate or you have already the impedance of the load, then I...

**[0:07:56]** You know, that may very well be easier. Or if I... You know, the load circuit is kind of a big mess and it'll be hard to calculate its impedance, then I... You know, maybe it's easier to calculate, one half v I star. So so there's no hard and fast rule.

**[0:08:15]** As you're working through a given problem, you know, often I would say you can see that I... Alright. I'm I'm closer to, you know, being able to get the result this way. So so that's probably the easier way, to do it. Alright.

**[0:08:31]** That's, you know, maybe the the best rule of thumb that I can give you right now. Any other questions? Okay. So any other questions from our last class meeting? Okay.

**[0:08:48]** If not, then we will pick up from where we left off. So what we had done last time was we had started this discussion of semiconductors and various types of semiconductor devices. So I kind of reminded you of MOSFET devices, which you learned about in three zero two or three zero two h, and then we talked some about diodes and bipolar junction transistors. And all of these kinds of devices, right, They are devices that are made from and whose properties depend on the properties of semiconductor materials. Alright?

**[0:09:28]** So what we wanna do in this part of the course is to talk about some of the basic physics of semiconductors, some of which will be reviewed from three zero two or three zero two h, and then, use that understanding of the basic physics of semiconductors to look in particular at how, PN junction diodes, behave. Alright? And that can be built upon to, understand the behavior of bipolar transistors. It also comes into play when one is understanding or trying to understand certain aspects of... Actually, many aspects of how, MOSFETs behave, and p n junction diode structures are really the basis for entire other classes of semiconductor devices that are important in a variety of applications.

**[0:10:24]** Okay. So what we wanna do starting today then is to talk about some of these specific properties of semiconductors. Okay. And just kind of qualitatively, you know, what are the things about semiconductors that make them useful and powerful for making different types of electronic devices? One is that they have moderate electrical connectivity.

**[0:11:06]** Right? So it's intermediate between insulators, right, which have very low electrical connectivity, and metals, have very high electrical conductivity. So the electrical conductivity of semiconductors is higher than that of insulators, okay, but then lower than that of metals. Okay. And what especially makes semiconductors very useful and powerful for making different types of devices is that there are various ways that you can control the conductivity of a semiconductor over many orders of magnitude.

**[0:11:56]** Alright? And that can be done through, essentially, what end up being static changes to, the semiconductor, like introducing impurities, what's called doping, or it can be done, during operation of a particular device, say, by applying a voltage that base... Essentially changes the concentration of electrons in different parts of a device. Okay. So what's especially useful is that the connectivity.

**[0:12:24]** Right, that's the electrical connectivity of semiconductors can be controlled over, many orders of magnitude. Okay. And this can be done during operation by applying, voltage or when one is making a device by introducing impurities. Okay. That is atoms of elements other than what constitutes the semiconductor itself, say something like silicon.

**[0:13:07]** Okay? And... Alright. All of this is important and useful because semiconductors are really the foundation for a wide range of, sort of systems and devices and technologies. So, so, essentially, I write all computer processors, GPUs, memory chips.

**[0:13:41]** Right? These are all made from predominantly silicon, alright, which is the most technologically important semiconductor material. Communications chips. Alright. The chips that send and receive signals in, for example, your smartphone.

**[0:14:02]** Right? These are also all made from semiconductors, lot of them from silicon, but some of them from other types of semiconductor materials. The display, right, on a smartphone or a big LCD panel and so forth is essentially a giant chip, right, that is fabricated on glass. Alright? Solar cells, alright, also are made from semiconductors, predominantly silicon.

**[0:14:35]** It used to be that the solar cell industry would kind of rely on extra silicon that was scrapped from the electronics industry, But now, and in fact, this crossover happened probably over fifteen years ago now, the volume of silicon that is required for solar cells is actually now much larger than that for computer chips. And so, it is its own, kind of dominant, you know, user of certain types of semiconductor materials, things like LED lighting. Right? LED light bulbs and so forth, which have really transformed the lighting industry and also power consumption are also based on a different type of semiconductor, gallium nitride, that is able to emit short wavelength light that can be used to create light bulbs and and things like that. And, you know, that has had an enormous effect on electrical consumption.

**[0:15:40]** You know, back before the days of LED light bulbs, it used to be that, residential electricity consumption, close to 20% of it was used for lighting. Now it's more like, it's less than 5%, alright, which is a big difference. Okay? You know, various types of image sensors. Right?

**[0:16:03]** So the image sensor chip in... Right? The camera in your smartphone, right, for example, is basically a a silicon chip. Right? And there are a variety of sort of more specialized applications.

**[0:16:18]** All of this really depends on semiconductors, and we want to spend some time talking about semiconductors in this course because anytime that you are trying to push the performance, of an individual device or of a system such as a circuit that employs those devices, then really understanding how that device behaves and why it behaves the way it does at a fundamental level, in terms of the underlying semiconductor physics is, is extremely important. It's really essential in doing that type of engineering at the limits of, performance. Okay? So so that's some just sort of very... Some general thoughts about semiconductors.

**[0:17:07]** And so in order to understand them more deeply, what we wanna look at first is what is the nature of the states in a semiconductor that are occupied by electrons, and, you know, how does that effect influence the way electrons move around, basically how current is conducted. Alright? So what we wanna do next is look at electronic states and what's called the band structure of semiconductor. Okay. I'm getting these reminders to update Zoom every five minutes.

**[0:17:51]** So, hopefully, I will not accidentally hit close all and update, which will shut this whole thing down. So we wanna look at... Oops. Oh, no. Uh-oh.

**[0:18:10]** Okay. Let me share this again. Oh, for some reason, it closed the app completely. Okay. I think we're back here.

**[0:18:34]** Okay. I think I have to start Zoom again. Oh, actually, it's still up. Let me just share again. Share.

**[0:18:50]** Okay. Here we go. K. If you can avoid using a computer that is owned by UT, then you should avoid it because they take control of the administration of the computer and can be quite cumbersome. Okay.

**[0:19:17]** So we wanna look at the electronic states and band structure of semiconductors. Okay. And so some of this may be material that you also saw in three zero two or three zero two h, but if not, that's fine because this will also... This will be still self contained, and I think it's useful as a reminder as well. So you may remember how silicon atoms bond together to form the silicon crystal.

**[0:19:48]** So we wanna recall, right, how silicon atoms, Right? How they bond together to form a silicon crystal, okay, which is the form in which we use silicon to make semiconductor chips and the like. So let's look... Or if we just look at an isolated silicon atom, okay, then we will represent that like this. We have this thing here, which we're using to represent the nucleus of the silicon atom and the electrons in, the closed, shells, right, around, the nucleus.

**[0:20:38]** And then we have the valence electrons, which we will draw individually. Right? So this here, this is an electron. And silicon, we're not in the science classroom, so there's no periodic table in here. But if you remember what the periodic table looks like, then you can see from the position of silicon in the periodic table that it has four valence electrons.

**[0:21:11]** Okay. And, 14, electrons in total. Alright? Now, you may remember from a chemistry course that a typical way that atoms can, bond to each other is by forming covalent bonds, where the electrons are shared, between atoms and those shared electrons then, if you have a pair of shared electrons, that constitutes the covalent bond. Okay?

**[0:21:39]** And in a silicon crystal, right, that's how the atoms are bonded together. Right? Each of these four valence electrons for each silicon atom is shared with a neighboring silicon atom and helps it to form a covalent bond with that neighboring atom. Okay? And so each of the silicon atoms then is bonded in this way to four of its surrounding atoms.

**[0:22:09]** Right? So we can represent this in two dimensions, alright, by drawing just a square array of silicon atoms. Okay. So these are the nuclei and the closed shells, and each of these atoms has four valence electrons around it. Okay.

**[0:22:42]** We won't draw the ones, that extend beyond, the edge here. Okay. So we have, four valence electrons associated with each, atom, and those valence electrons are shared with sort of the corresponding neighboring atom, right, to form covalent bonds like this. Okay. So in red here, these are the covalent bonds.

**[0:23:21]** Okay. And then, again, these black dots here represent, electrons. Okay. So so that's what the crystal looks like when we draw it. Each silicon atom is bonded to its four nearest neighbors.

**[0:23:41]** Alright? But, actually, the way the crystal looks like in three dimensions is like this. Okay? So it's not arranged in a square array. Instead, what you can see, right, if you look at this red one over here, right, you can see that, right?

**[0:23:58]** So these these short bars here represent the covalent bonds, and then these long bars here are shown just to show you... This has what's called cubic symmetry. Right? You can break this up into individual cubes. Alright?

**[0:24:14]** But if you look at this red atom here, which represents one silicon, each of these things represents a silicon atom. This red one over here, you can see that it's bonded to four of its nearest neighbors to form, and its nearest neighbors kind of form a tetrahedron. Right? A pyramid with a triangular base. Okay?

**[0:24:35]** And if you just put all these structures together, then you get this arrangement here, which is how the atoms are actually arranged in a silicon crystal. Okay? But, since this is very hard to draw, on... In a plane, then we will represent it in two dimensions this way with the key, feature here being that each of the atoms has four nearest neighbors to which it's bonded. Okay.

**[0:25:03]** So that is the kind of the physical structure of a silicon crystal. Alright. So any... Are there any questions on that? Okay.

**[0:25:15]** So now, what we wanna think about is the nature of the states that are occupied by electrons. Alright? So we wanna look at the electronic states that are occupied by electrons. Okay. And, again, we'll start off looking at what happens in just an isolated silicon atom, right, which you may remember about what you learned about electronic states in atoms from a high school chemistry course, and then we will see how that then leads to the electronic states that we have in a silicon crystal.

**[0:26:05]** Okay. So if we look first at just an isolated silicon atom, okay, then, right, if you have just an atom generally, I... What is the nature of the states that are occupied by electrons in that atom? What do we call them? Do you remember?

**[0:26:34]** They're orbital states. Right? You have, like, say, if you have a hydrogen atom, you just have a one s orbital. And then as you get to bigger atoms, then first you have the one s orbital, then the two s orbital, then the two p orbital, and then the three s and three p and three d and so forth. Alright?

**[0:26:53]** So, if we have an isolated atom, right, if we plot the energy levels that can be occupied by electrons as a function of energy, right, we have the the lowest energy state is the one s orbital. Alright. That can be occupied by two electrons. Then we have the two s orbital. That can also be occupied by two electrons.

**[0:27:24]** Then we have the two p orbital. Do you remember how many electrons can be occupied by, in p orbitals? It's six. Yes. Very good.

**[0:27:34]** Okay. And then we have three s and three p and so forth. Alright? And, silicon has 14 electrons in total. Okay.

**[0:27:50]** So, essentially, what's gonna happen is that we are going to fill the lowest 14 states in energy. Alright? Because, typically, electrons wanna go to the lowest energy state because that minimizes the energy of the system. So we can have two electrons in the one s orbital, another two in the two s orbital, and then six in the two p orbital. Alright?

**[0:28:27]** That's 10 so far. We have 14. And then we have two more in the three s orbital and then two in the three p orbital. Okay? And as you may remember from chemistry, anytime you have electrons that are in what's called a closed shell, alright, where, you completely occupy the states of, you know, the same number here, one down here or two over here, right, those are called closed shell electrons, and those don't really participate in chemical reactions and things like that.

**[0:29:10]** Alright. So these are the closed shell electrons. And then these electrons up here, which are in the incompletely filled third shell, Right? These are what we call the valence electrons. Okay?

**[0:29:34]** And it's the valence electrons that participate in bonding. They're the ones that carry electrical current in a semiconductor crystal and so forth. Alright? So those are the ones that we'll really be interested in. Okay.

**[0:29:48]** So that's what we have if we just have isolated atoms. Alright. So any questions on that? Okay. So then, what we wanna do is to look at how this changes when we go to, a silicon crystal.

**[0:30:10]** Right? This arrangement over here where we have atoms that are bonded, to each other to form some larger scale structure. So we are, again, going to... Right? We have energy on the vertical axis, and then we're gonna have position.

**[0:30:27]** We'll call that x on the horizontal axis. And what happens if we have atoms that are bonded together in a crystal, right, the way that you can imagine it is that if the atoms are very far apart, right, then each one just looks like an isolated atom. Okay? Because they can't... They don't interact with each other.

**[0:30:49]** This atom does not know about this atom. But then as you bring the atoms closer together, right, imagine that you have this spatial arrangement, but this distance is very large. And then you gradually reduce that distance but keep this same structure. Then at some point, the atoms get close enough together, right, that this atom knows that this atom is next to it. And the way it knows is that the electronic states, right, basically, the orbital states of the individual atoms, they start to overlap with each other a little bit.

**[0:31:27]** Okay? And when that happens, then eventually, right, you keep bringing them closer together, eventually, they form the bonds between the crystals. And once those bonds have formed, then it's possible for the electrons to move. They can move throughout throughout the crystal. Right?

**[0:31:49]** So they can move from one being close to one atom to the next atom to the next atom and so forth, right, because all these states are overlapping. Alright? And, when that happens, then what we say is that the crystal, doesn't so much have the individual orbital states anymore. It has what are called band states that are states within a certain range of energy that extend throughout the entire crystal structure so that electrons are able to move, through the whole crystal. Okay.

**[0:32:23]** So we have these... When we have a crystal, then we have these so called bandstates. Alright? At lower energy, we have what's called the valence band. Okay?

**[0:32:45]** And then at higher energy, we have what's called the conduction band. Okay? So these are ranges of energy, right, that have states that can be occupied by electrons. Right? That's basically how you can think about it.

**[0:33:03]** And then in between, there's a gap. Right? There is a range of energies between the valence band and the conduction band where there are no electronic states. Right? So you cannot have, at least in a structurally perfect and pure semiconductor, you cannot have any states at energies in this range here.

**[0:33:24]** That is called the energy band gap. Okay. Now what we wanna do first is to think about what happens when we are at a temperature of zero Kelvin. So absolute zero. Right?

**[0:33:45]** The significance of that is that, at absolute zero, all of the electrons will go to the lowest energy state that they can. Okay? And it turns out that the number of states available in the valence band is exactly equal to the total number of valence electrons in the crystal. So at zero Kelvin, what will happen is that, right, all of the states in the valence band will be occupied by electrons, and there will be no electrons in the conduction band. Okay.

**[0:34:32]** So in this situation, right, all the electrons are in the valence band, and none are in the conduction band. Okay. And our terminology over here, e sub c and e sub v, right, the terminology is simply... These are what are called the band edge energy. So e sub v is the highest energy in the valence band, and e sub c is the lowest energy in the conduction band.

**[0:35:16]** Okay? So the difference between these two energies then is the energy band gap. Alright? So e sub c here is the maximum energy... Sorry.

**[0:35:30]** E sub v is the maximum energy in the valence band, and e sub c is the minimum energy in the conduction band. Okay. So so that's the picture at zero Kelvin. Alright? Now if we go to a nonzero temperature, right, so temperature greater than zero Kelvin, then the bandstructure, it still stays essentially the same.

**[0:36:17]** Alright? Okay. So this is the conduction band edge energy. This is the valence band edge energy. Alright?

**[0:36:25]** But what happens at, temperatures above... Yeah. Question? I was gonna ask, what does it mean to be in the valence band form? Oh, so so we'll talk a little bit more about this later.

**[0:36:41]** Alright? But it turns out that, you know, valence band... If we look at silicon crystal, okay, then valence band and conduction band, that's sort of the... I'll call it the physics language for the electronic states. Okay?

**[0:37:00]** In the language of chemistry, the valence band states are actually called the bonding orbitals. Okay? And then the conduction band states are the antibonding orbitals. Alright? And so, you know, when you form chemical bonds, what happens is that, say, the, right, the three s and the three p states over here, they kind of get mixed together, and they form a new set of states that are the bonding and antibonding orbitals.

**[0:37:34]** The bonding orbitals are, the states that form these bonds between, adjacent atoms, and then the antibonding orbitals are the other states. Right? They're in higher energy, and they can only be occupied if there is something that gives the electrons enough energy to go to that higher state. So when we say that electrons are in the valence band, right, then another way of thinking about it in an equivalent way of saying is is that those are... Those electrons are the ones that are actually forming the bonds between the atoms.

**[0:38:16]** Alright? So that's equivalent essentially to saying that they're in the valence band is is that those are the atoms that are forming the bonds. And then if they're in the conduction band, that means that they're kind of free to move around through the antibonding orbitals. Is that kind of what you're asking? Mobile.

**[0:38:36]** So it turns out that in the bonds, the the atoms or or the electrons are also mobile or not so much only in that area, but you have... Right? All of these bonds have formed. Right? So you have electrons in essentially all of the available states.

**[0:39:03]** Right? Now in order for an electron to move, say, from here to here, right, then one of the conditions that's required for that to happen is that, there has to be an empty state available here for it to move to. Okay? And so if all of these states are completely filled with electrons, then there is no net motion, okay, of... You know, the electrons can switch with each other, but there's no net motion because they're all filled.

**[0:39:39]** Alright? Whereas, if they're in the conduction band, you only have a few electrons if you're at temperatures above zero Kelvin, and so they can move around through these states. Now what changes then is if you have... Suppose you took one electron out of the valence band, right, out of one of these bonding states, and it went into the conduction band. Then in the valence band, that is in the bonding states, now you had now you have an empty state, say, here.

**[0:40:10]** Right? Then an electron from here can move to that empty state. Right? And if you had another empty state, say, over here, that electron can move to that empty state. Okay.

**[0:40:24]** So, you can get sort of net motion of the electrons, if you have some empty states available for electrons to move into. Alright. Does that sort of answer your question? Okay. Yeah.

**[0:40:43]** We'll we'll talk more about this, in a few minutes, so maybe that'll, clarify somewhat. Yes? Is the definition of electron being induction band, is it only defined then... Or just just it only mapped to where that electron is, orbital wise or no? If an electron is in the conduction band, does that mean that it's in an orbital higher than three p or no?

**[0:41:20]** Yeah. We'll get into this in more detail in a few minutes. But what happens is that, as you make the transition from the isolated atoms to a crystal, then, when you get to the crystal, structure, you no longer have these original orbital states. Right? That you have essentially combinations of these orbital, right, that that form the bonding and the antibonding orbitals or equivalently the valence band and the conduction band.

**[0:41:48]** Yeah. Okay. Any other questions right now? Okay. So if we're at a temperature above zero Kelvin, then...

**[0:42:01]** Right. Temperature, you may remember from a physics course, is basically a measure of the average energy of a system. Okay? And in this case, we're concerned with the energy of the electrons. Okay.

**[0:42:18]** So when we're at zero Kelvin, the average energy is is is at the lowest possible level. When we are at a temperature above zero Kelvin, then that average energy is higher. Right? But what that also means is that it's not that every electron has that average energy. Some of them have more energy and some of them have less.

**[0:42:41]** Okay? But as soon as you have this extra, energy, thermal energy, right, the energy due to the temperature around, then there will be a few electrons that have enough energy to be up here in the conduction band. Okay. So you'll have few electrons up here, and then correspondingly, you will have a few empty states down here in the valence band. Okay.

**[0:43:17]** So then at a temperature greater than zero Kelvin, right above absolute zero, then instead of all the electrons being in the in the valence band and none in the conduction band, it'll be that most electrons are in the valence band, and, we'll have a few in the conduction band. Okay. And these electrons that are up in the conduction band, we just call them electrons. The empty states in the valence band, we call them holes. Right?

**[0:44:06]** And... Right? So our terminology here now is that in a semiconductor, when we talk about electrons, right, what we will very often mean, right, is that, we'll... When we say electrons, we will be referring to negative charge carriers, which are the electrons themselves in the conduction band. And when we talk about holes, these will be referring to missing electrons in the valence band.

**[0:45:01]** Okay? And they behave essentially like positive charge carriers. Right? Because if we have sort of absence of a negative charge, then that'll essentially... And that moves around.

**[0:45:22]** That's like it's equivalent to having a positive charge move around. Okay? And sort of an analogy to help you visualize this is that... And and for holes in particular, right, it's like if you have some liquid in a bottle, alright, then the electrons are the liquid itself. The holes, you can think of as being bubbles in the liquid.

**[0:45:55]** Right? So, it's often easier, right, if you have a bottle that's, just about full, and it has some bubbles in it, it's easier to think about how the bubbles are moving around than how the liquid is moving around the bubbles. Okay? So, thinking about holes is kind of like thinking about the bubbles in a a nearly full, volume of liquid. Okay?

**[0:46:18]** So that's one way to, kinda visualize it. Alright. So any questions then to here? Okay. Is this stuff that, you talked about in three zero two or three zero two h?

**[0:46:31]** Okay. Alright. Good. So, hopefully, it's not, completely mysterious at this point. So so now we have the question of, you know, how do these conduction and valence band states form?

**[0:46:42]** I kinda gave you the endpoints, alright, of what the electronic states look like in an individual atom and in a crystal, But, you know, what happens in the transition between these states? And then, you know, how is that related to the bonding? And then how does the formation of these bands and the presence of these bands relate to the concentrations of carriers that we have that can actually carry current in the semiconductor device, how they move around, and so forth. Right? So really asking, you know, how do the conduction and valence band states form?

**[0:47:27]** Right? How are they related to this picture where we have the covalent bonds? And then how are the bands related to carrier concentrations, mobility, and the like. Okay. So what we wanna do then is, to think about what happens if we have, some number of atoms that...

**[0:48:15]** And we think about the structure of the silicon crystal as a function of the separation, right, the distance between, the atoms. So we wanna consider some number n of atoms. Right? So, for example, silicon atoms, these are separated by some distance we'll call a. Alright?

**[0:48:48]** And what we wanna look at is how the states are distributed in energy as a function of that separation. Right? Where if they're very far apart, we know that in that limit, we should have the individual atom orbital states, and then if they're sufficiently close together, we have the band states. Right? But what happens in between?

**[0:49:07]** Okay. So if we draw a picture, then what we'll see is that the states that are occupied by the valence electrons, these are distributed in energy, right, as a function of a, Alright. It's separation a in the following way. Okay. So if we draw a picture of this, alright, we have energy on the vertical axis and then this separation a on the horizontal axis.

**[0:50:04]** Okay? And, right, we know that if the atoms are far enough apart, right, say they're a kilometer apart or a meter apart, right, then they're gonna behave like isolated atoms, and we'll just have the individual atom orbital states. Right? So at some... Beyond some minimum distance, then these are just gonna behave like isolated atoms.

**[0:50:32]** Okay? And what we will have are just the orbital states. Alright. Three s states and the three p states. Right?

**[0:50:46]** And if we have some number capital n of atoms, then the total number of three s states is two n. Right? Because each atom has two three s states. And then the total number of three p states is six n. Okay.

**[0:51:09]** So, this is our starting point. Okay? And then as I was describing earlier, if the atoms move closer together, then the orbital states from adjacent atoms will start having a little bit of overlap. Alright? And once they have that overlap, then what will happen is that you won't...

**[0:51:33]** You will no longer have two identical orbital states, one on each atom. What will happen instead is that those states will form new states that can... They extend across both of these atoms or in the whole crystal that extend across the whole crystal. Okay? And those states, each of them has to have a slightly different energy from each other.

**[0:52:00]** Right? So what'll happen is that the states that are occupied by the electrons start spreading out an energy a little bit. And then as you keep moving the atoms closer together, then... Alright. The states from the from the original three s orbitals and the original three p orbitals, they start to overlap in energy.

**[0:52:28]** Okay? And then as you keep going, right, what happens is there'll be some intermediate range of separations of the atoms where these are all just kind of mixed together. But then eventually, alright, they will split apart again, okay, like this. And in a silicon crystal, the equilibrium separation that you have in the crystal, right, what you find in nature is actually here, where I've drawn this dashed line. So this is the separation that corresponds to a semiconductor crystal.

**[0:53:17]** For example, a silicon crystal. Okay? And so at that point, what has happened is that the three s and the three p, the original orbital states, right, they started interacting with, with each other. They get mixed together, and then they get separated out again into a set of states that are at lower energy. Those are the valence band states.

**[0:53:47]** Alright? Or I... In the language of chemistry, those states are the bonding orbital states. Okay. And then at higher energy up here, we have what we will call the conduction band states, but we can also refer to as in language of chemistry, the antibonding orbitals.

**[0:54:29]** Okay. And then, you know, all this shaded region here, right, these are the ranges of energy where we have electronic states available, and the separation in energy between the antibonding orbitals and the bonding orbitals, or equivalently between the conduction band and the valence band, that is the energy band gap. Okay. So so this is sort of the more detailed picture of how as you bring atoms closer together, you get, these orbital states interacting and eventually forming these bonding and antibonding orbitals or equivalently valence band and conduction band states. And it turns out that each of these, alright, the valence band and the conduction band, we have four n states.

**[0:55:34]** Alright. So four n states in the conduction band, four n states in the valence band. Okay. Now that is significant... Yes.

**[0:55:46]** Question? Six n state. It will be two valence band. Oh, so so this is the total number of states available. Alright?

**[0:55:57]** So each... So for each atom, right, you have six three p states available, but then only two of those will be occupied. Okay. So in the crystal, we have states that are occupied by a total of four n valence electrons. Okay.

**[0:56:26]** Because we have four valence electrons with each atom, so we have a total of four n valence electrons. And so those, at zero Kelvin, right, you will completely occupy all of the valence band states. You'll have nothing in the conduction band, but then as you increase the temperature, then, some of those electrons will have enough energy to be up in the conduction band. Okay. So so any questions on this basic picture?

**[0:57:00]** Okay. Now, there's one other point that is worthwhile to mention here, which is that if we, start thinking about how these electrons carry current, right, the electrical conductivity in, semiconductor, then you might think that, okay, most of the most of the electrons are always gonna be in the valence band. Right? There'll only be a small number in the conduction band. So, intuitively, you might think that, okay, almost all the current is carried by the electrons that are in the valence band because you have so many more electrons.

**[0:57:38]** Right? But, actually, that's not quite the case. Alright? So it is the case that the current is carried by electrons that are moving through some combination of the conduction band and the valence band. Right?

**[0:57:53]** So in semiconductors, generally, right, what's happening is that electric current, okay, is carried by electrons moving through the crystal in either conduction band or valence band states. Okay. But the caveat to this is that, you know, perhaps somewhat unexpectedly, if you have a band that is completely filled with electrons, then those electrons cannot actually carry any net electrical current. Okay. So the caveat to this is that only electrons in a partially filled band will contribute to the current.

**[0:59:23]** Okay. And, right, the reason for this is basically that if you have all the states in a given band occupied by electrons, right, each of those states is characterized by some energy. Right? You have a... It's a it's a state at a particular energy, but then each of those states also has momentum associated with it.

**[0:59:48]** Alright? You can think of it basically as a velocity, right, more intuitively. And for every state that has a momentum, say, in this direction in a band, there will be some other state that has a momentum in the opposite direction. So if both of those are occupied, then their motion will cancel each other out. Okay?

**[1:00:12]** And so so if every state is occupied, for everyone going like this, you'll also you'll also have one that's going like this, and so their motion will cancel out. Okay? But if you only have this and this state is empty, then you can have some net motion associated with just this one, and that will have some current associated with it. Okay. So the short version of this is that if every state in a band is occupied, right, then each electron, it has a counterpart electron, right, in the same band It's moving in the opposite direction.

**[1:01:28]** Okay. And those will cancel each other out. Okay. And it's really this that makes it so useful to think about holes. Alright?

**[1:01:41]** Because since the completely filled band has no net has no ability to carry net current, then it's only when you have empty states that you can carry current. Then I... Instead of thinking about how all the electrons in a completely... In a in a mostly filled band are moving, then you can talk instead about how the empty states are moving. That's much easier to keep track of, and that works because the sum of, the motion of all the electrons that are filled and all the electrons that that would have been present in these empty states, that has to add up to zero.

**[1:02:23]** Right? So keeping track of just the empty states is a lot easier. Yes? Technically, both bands can carry current in undoped the silicon crystal. Really, it's just because of the electrons that are in the conduction band.

**[1:02:37]** Like, even though both bands are carrying it, it's because that they left the the holes in, the valence bands. They can actually carry around. Right? So, yeah, so in a, structurally perfect and pure semiconductor where the only place that electrons from the valence band can go is up to the conduction band, then it is the case that having electrons in the conduction band, then, you know, each one has some associated empty state in the valence band that are left behind. Right?

**[1:03:13]** You can have current that is carried both by... Or, you know, there will be a contribution to the current from the electrons in the conduction band. There will also be a contribution of the current from the holes in the valence band. Right? But, you know, as as you noted, the presence of the of the holes in the valence band is always gonna be associated with, the presence of electrons in the conduction band.

**[1:03:39]** Now if you introduce some impurity atom, right, in in doping, which you may have talked about in in three zero two or three zero two h, then, those impurities can pull some electrons out of the valence band. Right? So those electrons, they'll just be, right, at the impurity atom, not up in the conduction band. But in that case, the holes that are left behind in the valence band can still carry current. Okay?

**[1:04:09]** So in that situation, there isn't the same connection between electrons in the conduction band and holes in the valence band. Does that answer your question? Yeah. Okay. Yes.

**[1:04:19]** Yeah. But truly where individual electrons in this huge lattice are not throughout their entire journey in the conduction band, but they keep... Like, they'll be in the conduct... Conduction band for a brief moment and go back down. But in general, the the cumulative amount is, you know, whatever whatever the equation says it will be.

**[1:04:48]** So so, basically, yes. So it is the case that, you know, say if you had just what's called an intrinsic semiconductor, structurally perfect, no, impurities, then a nonzero temperature. You'll you'll have some electrons in the conduction band, some holes in the valence band. Those can each move around, right, due to a voltage and... Or or what have you.

**[1:05:12]** But it will also be the case that, you know, if if you labeled some electron up here, right, that came from some state down here, that electron up here, that particular electron may drop back down into an empty state down here. But then on average, whenever one of these electrons drops down, another one will go up to the, conduction band and and then carry current in, you know, a similar way. And since there's a net movement in one direction, the the the average the average net net direction will be in in the current then or in the direction of the current? Yes. Then the net motion of, the electrons in the conduction band and the net motion of the holes in the valence band will each, contribute to the electrical current.

**[1:06:04]** Okay. Any other questions? Okay. So, right, it's because of this... Right?

**[1:06:13]** Because a completely filled band, right, carries no electric current. Alright. Then instead of thinking about the electrons moving in an almost filled valence band. We can think about and also calculate, how the empty states are moving in the band. Okay.

**[1:07:22]** And these empty states are what we call holes. Okay. And, again, you can kind of use the bubble in a liquid analogy. Right? Instead of thinking about how the liquid is moving around, we're thinking about how the bubbles, are moving around.

**[1:07:42]** Okay? And if the bottle is completely full, then, there's no net motion of the liquid within the bubble. Alright? Individual, say, liquid molecules may move around, but there's no net change in the distribution of that liquid. Okay.

**[1:07:56]** So any questions to there? Okay. So, so we've sort of, you know, we've waved our hands about, you know, how, okay, if we're at a nonzero temperature, then there'll be some electrons in the conduction band, and some empty states in the valence band. Right? But we wanna be more quantitative about this.

**[1:08:19]** Okay? So, now we wanna talk about, okay, the occupation of states by electrons. Right? So what is the probability that a state, say, in the conduction band or in the valence band, or more generally, that a state at a given energy, what is the probability that that state will be occupied by an electron, say, at a given temperature? And that leads us to what we call the Fermi distribution function.

**[1:09:02]** Okay. So is this something that you discussed in three zero two or three zero two h? Okay. So this is new. Alright.

**[1:09:09]** So... Alright. We said earlier that, okay. If you have electrons in some physical system, in this case, in a semiconductor, they will tend to want to occupy the states that are at the lowest energy, right, because that, minimizes the energy of the system as a whole. But if you have some extra energy around, say, thermal energy associated with nonzero temperature, then there'll be some electrons that are not in the lowest possible energy state, but at some higher energy.

**[1:09:39]** Okay? And so what we would like to have is some function that will allow us to calculate at a given energy what is the probability that a state at that energy will be occupied by an electron. If we if we have that, then we can calculate the probability that, say, a state at an energy in the conduction band will be occupied, the probability that a state at an energy in the valence band will be empty, and we can then calculate, you know, how many electrons will be around in the conduction band, how many holes in the valence band. Okay. So that's the idea of the Fermi distribution function.

**[1:10:20]** And what the Fermi distribution function tells us is what is the probability that a state at a given energy will be occupied by an electron. Okay. So the probability that a state at some energy, we'll call it e, right, the probability of that is occupied by an electron. Right? This is given by what we call the Fermi distribution function.

**[1:11:13]** Okay. And, typically, we represent this by f of e. Alright? And... Right.

**[1:11:23]** So there's a lot of statistical physics and such, which if you take ECE three thirty nine, you may learn about some of it. I'll just give you the result that comes from that kind of analysis, which is that the Fermi distribution function has the mathematical form. It's one over e to the energy minus a reference energy e sub f, called the Fermi level or the Fermi energy over Boltzmann's constant times the temperature plus one. Okay. So this...

**[1:12:01]** In this expression here, k sub b is the Boltzmann constant. Okay. And, right, if we look at this expression here, we can see we have energies in the numerator, and we have the Boltzmann constant times temperature in the denominator. So the Boltzmann constant is basically just... It's a constant that converts temperature to an equivalent energy.

**[1:12:36]** Alright? So we should have units of energy over temperature, say, joules per Kelvin. Right? And so the numerical value of this is 1.381 times 10 to the minus 23, joules per Kelvin. Be careful where I rest my hand here.

**[1:12:59]** Let me try to do this. Okay. I'm just gonna not try to write on the edge here. It's 1.381 times 10 to the minus 23 joules per Kelvin. Alright?

**[1:13:15]** T here is the temperature in Kelvin. And then this e sub f over here, right, this is the... We call it the Fermi energy or sometimes the Fermi level. And it is basically... It is the energy at which f of e is equal to one half.

**[1:13:59]** Right? So, in some sense, it's sort of the dividing line, dividing energy between the range where, you have a higher probability of, state being occupied by an electron and a lower probability. Right? So so that's what the Fermi level or Fermi energy is. And if you look at this expression here, right, what you can see is that, you know, physically, this expression makes sense because what you would expect is that at very low energies, states that are very low energies should have a high probability of being occupied by an electron.

**[1:14:35]** Right? States that are very high energies, should have a low probability of being occupied by an electron. Right? And if you look at this expression here, if e is very low, say much lower than the Fermi level, the Fermi energy, then you'll have a negative value in this exponent. Right?

**[1:14:56]** So e to the e minus e f over k t... K b t is going to be very small. Right? So this will look like one over one plus something very small. So the probability of a state at that low energy being occupied by an electron will be very close to one, right, which is what you would expect.

**[1:15:14]** When e is equal to the Fermi energy, then we have e to the zero, which is one. Right? So we have one half, right, as the value of the Fermi distribution function. And if we are at very high energies, then, right, we'll have a large positive value in this exponent. So e to the e minus e f over k b T will be very large, and the probability of this very high energy state being occupied by an electron will be, correspondingly very small.

**[1:15:47]** Right? So, physically, this all makes, should make sense to you or at least be plausible to you. Right? The other thing that we'll note just finishing up is that if we have a pure perfect semiconductor. Right?

**[1:16:04]** So in a pure and structurally perfect semiconductor, right, then we know that the concentration of electrons and the concentration of holes, they have to be the same as each other. Right? Because the only way that you get electrons in the conduction band is by leaving behind holes in the valence band. Right? So the concentrations of electrons, we'll call that concentration n.

**[1:16:41]** And of holes, we'll call that concentration p. Right? N and p correspond basically to negative positive charge carriers. Right? These have to be equal to each other.

**[1:16:59]** Alright. So in some sense, right, what that means then is that the probability of finding empty states in the valence band and of finding filled states in the conduction band, alright, these have to be sort of similar to each other. Alright? And so, what that then suggests is that the, in this situation, the Fermi level should be near the middle of the band gap. Right?

**[1:17:26]** Not necessarily exactly in the middle, but near the middle. Alright? And and that, in fact, turns out to be the case. Right? So the framing level then is near the middle of the energy band gap.

**[1:17:50]** Okay. So what we will do, next time, which will be, next Monday, is, we'll start talking about... We'll go into more detail on this and how you can go from the Fermi distribution function to actually calculating, electron and hole concentration in semiconductor and what the implications of that are for how semiconductor devices behave. So any questions to hear? Okay.

**[1:18:18]** If not, then we will stop here for today, and I will stop the recording now. Okay. And
