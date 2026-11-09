# 2026-10-14-semiconductors-intro-to-filters

Deepgram general-nova-3 2025-07-31.0, request 01a1b00f-d274-79f2-9a62-fb3658404a84, audio 76.4 min.

**[0:00:02]** Okay. So I have started the recording, and just a couple announcements. The first one is that I just posted a, another handout on the Canvas site, and it is a handout on, it's it's more on, kind of how to do algebra with complex numbers. And as we will see starting later today, when we start talking about, the frequency response of, circuits and transfer functions and things like that, a lot of that involves dealing with essentially rational functions of complex numbers. And so, there are some subtleties, to how one, does that, and so that's, a lot of what is addressed in this second hand ad.

**[0:00:53]** If you know all this already, then that's perfectly fine. If you want, you know, some additional background or refresher, then I think that will be very useful. Second announcement is that my office hours today will be in the afternoon, 02:30 to 4PM, instead of, the usual 11:30 to 11:55AM. Still be in, EER 3 Dot 802. Okay.

**[0:01:20]** So any questions on any of this or on what we covered in class or what was covered in the recitation section? Recitation on Monday, class last week. Or, I guess, actually, not last week, but on Monday. Okay. And as you can see, I have my tablet back, so we don't have to use the doc cam this time.

**[0:01:45]** Okay. So if there are no questions, then what we had been discussing last time was we had started talking about this particular kind of device, which is a p n junction diode. Okay? And it's basically a p type semiconductor and an n type semiconductor that are joined together so that electrons and holes can flow back and forth between them. And this kind of physical arrangement of p type and n type semiconductors in a circuit, it's represented by the diode symbol, like this.

**[0:02:21]** Okay? And, what we had gotten to at the end of our last class meeting was that, if you have this device in equilibrium. Right, so the p type and the n type sides are in equilibrium with each other, that corresponds to zero voltage being applied across the the diode device. Then I... What we call the energy band edge diagram.

**[0:02:48]** Right? The energy of the conduction band edge and of the valence band edge as a function of position in the device, it ends up looking like this. Okay? And that we can think of the conduction band edge energy as essentially a potential energy function for the electrons and the valence band edge energy, as a potential energy function for holes, recognizing that to get holes to lower energy... Or, yeah, to get holes to lower energy, that actually corresponds to an increase in potential energy because, really, what you're doing is you're getting electrons from down here to fill these states up here.

**[0:03:32]** Okay? So, so this is what essentially the potential energy of the electrons in the holes looks like as a function of position in the p n junction, and, you end up getting this, potential barrier here, right, which we call the... Or potential energy barrier, and the corresponding potential or voltage we call the built in potential of the p n junction. And, one way we can think about this is that this potential energy barrier is kind of what keeps all these electrons over here on the n side and all the holes on the p side. Right?

**[0:04:09]** Because, these electrons have to get additional potential energy to make it over to the p side. The holes have to get additional potential energy to make it over to the n side. And, in equilibrium, that potential... Those potential energy barriers exactly counteract the tendency of the electrons to wanna diffuse to the p side and the holes to wanna diffuse to the n side. Okay?

**[0:04:34]** And since they exactly counteract, then the net current is zero. Yes. Question? So is the reason that that potential gets built up is because, like you said, in an equilibrium, initially, a certain amount of electrons and holes diffuse across. And then because of that, the holes that diffused across would be...

**[0:05:02]** Make that side positive, and the other side that had electrons go would make it negative, and that's potential difference there. Yeah. So that's basically, correct. If we, sort of draw a more elaborate picture here... Alright.

**[0:05:22]** This is the p side. This is the n side. Alright? These are the conduction band edge energies. These are the valence band edge energies.

**[0:05:30]** Then on the p side, you have a bunch of these holes, and on the n side, you have a bunch of electrons. Right? Now remember, alright, to get the electrons in the conduction band, they are, donated to the conduction band by donors, donor impurities. And when that electron goes off to the conduction band and starts being able to move around, what's left behind is a positively charged ion. Right?

**[0:06:01]** So we also have these positively charged... I'll draw them like this. Ionized donors in the n type material, and then we have correspondingly negatively charged ionized acceptors in the p type material. Okay? Now near the junction...

**[0:06:23]** Okay. When... Once you connect these... Alright. Draw this in right here.

**[0:06:30]** Right? Once you connect these, alright, you know, originally, right, the Fermi level was, say, down here for p type and up here for n type. Right? Once you connect these, then, these electrons, right, they can find these holes. Right?

**[0:06:53]** And they'll recombine, but only if they're pretty close to the junction. Alright? And then, you know, what you can imagine happening is that the electrons over here, right, and the... Over here and the holes over here, right, they recombine with each other so they kind of cancel out. Right?

**[0:07:14]** Then you have neither the electron or the... Nor the hole left, but what you have left behind are these ionized dopants. Okay. So if we add that to this picture over here, alright, let's say the, you know, the p n junction is something like that. Okay?

**[0:07:38]** Then, we have some of these... Right? We have ionized donor atoms on the n side and ionized acceptor atoms on the p side. Okay? And so we have these charges now.

**[0:08:01]** And anytime you have charge, you have an electric field, and the integral of the electric field is potential. Right? So that's actually where this built in potential comes from. It's the potential that is produced by these ionized dopants. Is that is that what you're asking?

**[0:08:18]** Yes. Yeah. Okay. Any other questions? Okay.

**[0:08:25]** So then... Oops. What we drew up here is kind of the picture of what happens in equilibrium. Zero voltage applied to the diode. Alright?

**[0:08:40]** What we wanna understand next is what happens if we apply a volt... A non zero voltage. Okay? And, you know, we're gonna think about the case where we apply a positive voltage here. Right?

**[0:08:54]** So that is positive voltage to the p side relative to the n side. We can think of the n side as being grounded. We apply a positive voltage to the p side. Okay? Now if we apply a positive voltage to the p side of, the junction, then what that is going to do is it lowers the potential energy on the p side for the electrons.

**[0:09:20]** Right? Because the potential energy is the charge of the electron, which is minus e times the potential, which is positive. Right? So a positive voltage here will lower the potential energy for electrons on the p side, and then the potential energy for the electrons on the n side will be unchanged because, we're saying that this is grounded. Okay?

**[0:09:43]** And so what that means then is that this potential energy barrier for the electrons will be reduced, and it'll be reduced by an amount that is equal to minus e times that voltage. Right? Because that's the, potential energy contribution that you're getting from the voltage. Okay? And, as we'll see shortly, what that will do is, right, it'll then make it easier for the electrons to get over from the n side to the p side and for the holes to get from the p side to the n side, and that is what produces the current that flows in the p n junction diode.

**[0:10:22]** And as we will see, the nature of the Fermi distribution function then will tell us that that current will increase exponentially with the voltage. Okay. So that's kind of where where this is headed. Alright. So the basic idea, right, is that if we have...

**[0:10:42]** Okay. So when we have a voltage v, right, we'll take that voltage for now to be positive, you know, although you could choose to apply negative voltage also. We'll see what happens in that case a little bit later. If we have a voltage v that's positive, This is applied across the diode. Then what happens is that the potential energy difference, okay, for electrons.

**[0:11:23]** Alright. We'll think... Explicitly, we had electrons for now, but the same sort of thing happens for the holes. Right? This is shifted by an amount that is equal to the voltage's contribution to the potential energy of the electrons on the p side, which is minus e times v.

**[0:11:43]** Right? So it's shifted by this amount minus e times the voltage v. Okay. And so sorry. What what is e again?

**[0:11:59]** E is the, fundamental charge. Right. So 1.6 times 10 to the minus nineteenth coulombs, you know, charge of the electron. Okay. So...

**[0:12:09]** Alright. So this is the, right, charge. Magnitude of the electron. That's what e is, and then so the charge of the electron is minus e. Okay.

**[0:12:23]** So so the situation that we're looking at here is, right, in a circuit, we have a diode, and then now we're applying this voltage across it. And a positive voltage corresponds to positive voltage to the p side, that then in the semiconductor, right, corresponds to applying positive voltage to the p side. Okay. And then if we look at this now in terms of the band edge energy diagram, right, if this is our starting point when the voltage is equal to zero, then, this p side, the left hand side in this diagram, is gonna move lower in energy. Okay?

**[0:13:20]** And so what will happen is that the Fermi levels on the p side and the n side will now be different from each other, and the difference will be minus e times v. Right? The change in the potential energy. So if we just draw that out, okay, we have the Fermi level on the p side and the Fermi level on the inside like this. Okay?

**[0:13:53]** And what this now looks like is basically like this. This is the conduction band edge energy. This is the valence band edge energy. Okay. We have our electrons on the p side...

**[0:14:14]** Or sorry. On the n side, are holes on the n side. And what has happened now, right, the difference in the framing level is z times v, and the height of this barrier now is, e times the built in, potential minus e times v. So it's lower when we apply this positive voltage. And so that means that some of these electrons...

**[0:14:50]** Right? Say if you had an electron that was up here in energy, now that can move across because it's not blocked by the barrier anymore anymore. And the holes, right, some of them, have a high enough potential energy that they can move across, the junction because they are no longer blocked by the barrier either. And that motion of the carriers means that we will have current flowing in this direction. Yes.

**[0:15:18]** Questions? Let's see. It wants to move across, I guess. What's the reasoning for this electron moving? Oh, so it is, it's it's diffusion.

**[0:15:30]** Right? So you have lots of electrons over here. They're be away from each other. Yeah. So they're gonna be moving randomly.

**[0:15:40]** Right? And so, you know, some of them will be moving in this direction. Some of them will be moving in this direction. If we had the same concentration of electrons over here, right, then the electrons from this side that are moving in this direction will be canceled out by the electrons over here that are moving in this direction. But if we have lots of electrons here and very few electrons here, then we'll have a lot of electrons that are kind of going like this from this side, but very few that are going like that.

**[0:16:13]** Right? Because you have so few over here. And so they will no longer cancel each other out. Right? So what'll happen is that, there will be some net motion of electrons from, the high concentration area to the low concentration area.

**[0:16:32]** So that's what happens in diffusion generally. And Do they recombine with, like, more holes? So once they have diffused across, then they will eventually recombine. Right? So you will lose those electrons, and then, you know, the same, sort of thing will happen with the holes that move to the inside.

**[0:16:59]** Right? These electrons will gradually recombine kind of, you know, as they're moving to the left here in this picture. But then what happens then is that in order to maintain the concentration of holes... Because every time an electron recombines, then you lose a hole also. Right?

**[0:17:22]** So then you'll have to have some additional holes coming in this way. And so you'll still have... Even though the electrons are recombining with a hole, you will still have net motion of carriers because, over here, right, mostly what's happening is that you'll have electrons moving to the left and recombining, but then, you'll have to have holes coming in from the left and moving to the right in order to resupply the empty states that you have to have on the p side. And so so by the time you get out here, the current... Right?

**[0:17:59]** Over over here, the current is carried mostly by the electrons. But then once you get out here, it's it's gonna be carried mostly by the holes. But but that current basically is gonna be the same. Okay. So that's, sort of the more detailed picture of, what the carriers are doing.

**[0:18:16]** What we wanna understand here is mostly, you know, how these electrons get to the other side and how the holes get to the other side in the first place and how that depends on the voltage. And that will then allow us to see what the current voltage characteristic of a diode looks like. Does that answer your question? Okay. Any other questions?

**[0:18:38]** Yes. So just to, like, get this straight, because we're no longer at equilibrium, the Fermi levels can be different? Yes. Either side of the nets. Yeah.

**[0:18:49]** And so, you know, what that also means then is that at energies up here, you still have a higher probability of finding electrons over here on the right than on the left. And so that's why there's still this net motion of the electrons to the left. Okay. Any other questions? Okay.

**[0:19:11]** So so, essentially, what's happening here is that, right, the energy barriers... Okay. For electrons and holes, right, basically to move, across the p n junction. Right? These are shifted by this amount minus e times the voltage.

**[0:19:48]** Right? So shifted then means that they are reduced, and the consequence of that is that the current is no longer zero. Okay? So that is the basic idea. What we wanna do now is to quantify this, a little bit better.

**[0:20:08]** Okay? And what that involves then is using our understanding of, or at least, you know, knowledge of the Fermi distribution function to, figure out how many electrons are there, at sufficiently high energy, to diffuse across, the junction and not be blocked by the barrier, and how does that concentration depend on the voltage? Okay. So that's, what we want to look at next. K.

**[0:20:43]** We go. Okay. And what we will see shortly here is that that concentration of carriers that have enough energy to move across the barrier, that concentration will increase exponentially with the voltage. Okay? So the concentration...

**[0:21:05]** Right? Because then the current, it'll be proportional to that concentration. Right? So the concentration of electrons or holes that have an energy that is higher than the barrier, this increases exponentially, okay, with the voltage. Okay.

**[0:21:42]** So I... To see why this is the case, we can start off by looking at, again, the situation when we have zero voltage across the p n junction. Okay. So if we draw the band edge energy diagram... Right?

**[0:22:04]** This is the Fermi level. It is constant across the junction, and the band edge energy diagram looks like this. This is the conduction band edge energy. This is the valence band edge energy. Alright.

**[0:22:19]** We have holes over here, electrons over here. And what we wanna do is to look at, in addition, the Fermi distribution function. Right? Remember, it varies between zero and one. Okay.

**[0:22:42]** The Fermi level, right, is here. And, basically, what we wanna look at is what is the Fermi distribution function? What is this value up here? Right? Add an energy that is high enough that if you had an electron there, it could move across the barrier.

**[0:23:09]** Okay? It won't be blocked. And so, right, this... The height of this barrier here is e times the built in potential. Okay?

**[0:23:22]** So so the energy up here is just the energy of the connection main edge e sub c plus e times VBI. Okay? So then the Fermi distribution function is going to be e to that energy, e c plus e VBI, minus the Fermi energy over k b t plus one. Okay? And...

**[0:23:57]** Alright. If we look at this, then, we can see that the energy up here is, much higher than the Fermi level. Much higher meaning that is... It is the energy... This energy difference is typically going to be many times, k sub b times c.

**[0:24:13]** Because remember, we figured out, last time that at room temperature, k sub b times t in the denominator of the exponential here is... Of the exponent is, like, one fortieth of an electron volt. And the built in potential here is going to be... It's it's sort of of the same order as the band gap. Right?

**[0:24:35]** It's somewhat less than the band gap. So it's going to be, you know, since the band gap of silicon is 1.1 eV, then, you know, VBI might be maybe point six or point seven eV. And compared to one fortieth, that's much bigger. Alright? So you're gonna have a large number in the exponent, and so this exponential is gonna be much greater than one.

**[0:24:59]** Alright? And so this will be approximately equal to e to the minus, and we'll write it as e times the built in potential plus e c minus e f over k b t. Right? So that is our starting point. Okay.

**[0:25:25]** So any questions about sort of what we've done here? Okay. So what we wanna do then is to see how this picture is modified if we go to a voltage that is greater than zero. Right? So positive voltage applied to the p side, relative to the n side.

**[0:25:50]** And, right, what we saw just a few minutes ago is that that lowers the potential energy for the p side, right, relative to the n side, right, by an amount that is equal to, e times the applied voltage. And so the band edge energy diagram now will look something like this. Alright. We have our electrons on the n side, our holes on the p side. And what's happened here now is that this barrier has been reduced in height by, e times v.

**[0:26:43]** So this is now e VBI minus e v. Okay. So, you know, we've pulled everything on the p side down to lower energy, so that also reduces the barrier. So now what we wanna do is, again, to look at the Fermi distribution function. Okay.

**[0:27:12]** Right. So, yeah, over over here, it's gonna look something... Right. It looks something like this. Okay.

**[0:27:29]** So now, alright, we have the Fermi level here. Right? So the Fermi distribution function is gonna be equal to one half there. And then at the height of the barrier, now we wanna look at what the Fermi distribution function looks like mathematically. This energy, right, this energy here is now, right, this was e sub c, this is e sub v.

**[0:28:06]** So the energy up here, right, at the top of the barrier is going to be e sub c, the conduction band edge energy, plus e v b I minus e v now. Okay? So this is going to be... So the Fermi distribution function is gonna be one over, then it's e to the e c plus EVBI minus EV minus the Fermi level over KT. All this plus one.

**[0:28:41]** Alright? And so... Alright. It's still gonna be the case, you know, unless you apply a very large voltage. But, usually, it's very difficult to get to that kind of voltage and still have a sustainable, current to get much beyond that voltage and still have a sustainable current.

**[0:29:00]** So it's still going to be the case that this energy up here is much greater than the Fermi level, meaning that that energy minus the Fermi level is gonna be many times k sub b times t. So we're still gonna have a big number in the exponent here, and so this exponential is gonna be much greater than one, and so we can write this as being approximately equal to... Right? It's gonna be e to the minus EVBI plus e c minus e f over k b t. But then we have this additional factor due to the minus eV over here, and it's minus eV over kBT in the denominator so becomes plus eV over kBT in the numerator.

**[0:30:03]** And now if we compare this expression here to this expression here, right, in both cases, it is the value of the Fermi distribution functions, the probability of finding an electron at that energy. It's this when the voltage is zero. When the voltage is positive here, right, we have this factor here, which is the same as this factor here, but now we're multiplying it by, e to the e v over k b t. And I apologize for the notation here where we have these two e's that mean different things. This lower e here, obviously, is, 2.71828.

**[0:30:47]** This e up here, is the charge charge magnitude of the electron. Okay? But, you know, what we see here is that this concentration of electrons that we have up here with sufficient energy to move across the barrier, it has increased exponentially with the voltage. Okay? So we'll have exponentially more electrons that can move across the barrier.

**[0:31:12]** Correspondingly, there will be exponentially more holes that can move across the barrier. And so that means that the current flow that you get, as you increase this positive voltage, will increase exponentially with that voltage. Okay? And that's the reason why when you have a diode, and you look at how the current depends on the voltage, that's why it increased exponentially with the voltage. It's basically because of this.

**[0:31:40]** Right? So, essentially, the key point that we're seeing here is that this factor here tells us that, alright, the Fermi distribution function at an energy that is just sufficient to cross the barrier, right, this increases exponentially with the voltage. Okay. We've drawn out kind of the pictures for electrons, but you can see from the diagrams here that, you know, essentially the same thing is gonna happen with the holes because the barrier for the holes is also being reduced by the same amount. Right?

**[0:32:19]** So, similarly, what's happening concurrently is that holes will diffuse from the p side to the n side of the junction. Alright. With exponentially increasing probability with the voltage. Okay. And so the consequence of all of this is that the overall current increases exponentially with voltage when the voltage is greater than zero.

**[0:33:29]** Okay. So, so any questions on this? Okay. Yes. Over here and then there.

**[0:33:37]** About having the two Fermi levels at, where we chose the the higher Fermi level because that's the Fermi level on the n side. Correct? Yes. Right. So, yeah, so what we're portraying here is, the probability of finding electrons up here.

**[0:33:55]** Right? So... And electrons specifically on the n side. Right? So that's why the Fermi level on the n side is is the right one to use.

**[0:34:01]** Okay. So then in in the middle, would it not be an immediate... Would it be, like, a similar to the... To, a reflection of the e f and... Or e c and e v graphs, the Fermi level, would it not immediately drop but decay off in the middle there?

**[0:34:19]** Yeah. So so what actually happens in the middle here is... So when you draw the Fermi level, if you draw a single Fermi level, that sort of implies that all the carriers that are described by that Fermi level are kind of in equilibrium with each other. Okay? Now, if you're way off on the n side or way off on the p side, then, you know, over here, you have basically just the electrons.

**[0:34:50]** They're all in equilibrium with each other, so you can have a well defined Fermi... Single Fermi level here, and that will also describe the concentration of holes down here. Same thing on the p side if you're far away from the junction. When you're at the junction, you have these carriers that are moving back and forth. Right?

**[0:35:06]** So you have some electrons from over here that are are crossing the junction. They're over here. And then you have some, holes that are crossing the junction over here. And then, you know, as you have... As as you get to the...

**[0:35:25]** Say, for the electrons, as you get to the p side, then you still have some extra electrons. And then as they recombine, you'll sort of... They'll... That concentration will kind of revert back to what it would be in equilibrium for the p side. So what it actually looks like is if you're within the junction or close to the junction, then the, you have...

**[0:35:51]** The the electrons and the holes are not quite in equilibrium with each other. Right? The electrons are in equilibrium kind of with themselves. The holes are in equilibrium with themselves, but the electrons are not in equilibrium with the holes. They're still in the process of recombining to reach that equilibrium.

**[0:36:07]** So what actually happens is that you have... Let me run it in a different color here. You have, you know, a Fermi level for the electrons that kinda goes like this, and then a Fermi level for the holes that kind of goes like this. Okay. So, you're not quite in an equilibrium situation between the electrons and the holes if you are within or close to the junction, and so you can't use a single Fermi level to describe them.

**[0:36:46]** Alright? And so you have a Fermi level for the electrons and a Fermi level for the holes. In this region over here, they're different from each other, but eventually they become the same. Okay. Okay.

**[0:36:59]** Any other questions? Yes. Oh, yes. Right. Yeah.

**[0:37:02]** So since, I mean, electrons are, like... Even though they have the average energy, there there are variation. Yeah. So that's why you have zero. There's nonzero probability that you find it above that energy, probability.

**[0:37:20]** Right? Yes. So when it's your volts, there are still... And how's that diffusing over to the high side? The why isn't current just spontaneously Ah, okay.

**[0:37:32]** So that's a good question. So so there are some electrons up here. Right? You know, the the probability of finding them is much lower. Right?

**[0:37:42]** But there are some up here. But then remember, there are also some up here. Okay? And since the Fermi level is the same, right, on both the p side and the n side, you have the concentration of electrons on the p side up at this energy is the same as the concentration of electrons that you have on the n side at this energy. So then this will cancel out with that.

**[0:38:19]** Okay. You'll you'll have carriers moving from both sides, and they'll cancel each other out. Now down here, right, you have some electrons up here. You also have some electrons up here, but there are fewer because over here, you're only eVbi minus eV above the the conduction band edge. Alright?

**[0:38:48]** Over, over here, right, basically, you're much farther from the Fermi level. So you have a lot fewer of these electrons up here, than you have over here. And so the net motion will be... Right? The electrons moving from the right to the left will...

**[0:39:08]** In terms of their contribution to the current, they will outweigh these electrons here moving to the right because there are so many more of these. Okay. So that's the more complete picture of what's happening here. Does that answer your question? Well, I'm gonna have to look back.

**[0:39:27]** I think... Yeah. Okay. Yeah. It it happens that way because the Fermi levels are no longer the same on the two sides.

**[0:39:34]** That's that's sort of required in order to have net current flow. If the Fermi levels are the same, the current flow would be zero. Okay. So so what we've seen from all this is that for positive voltage, the current increases exponentially with the voltage, and it flows from the p side to the n side in the diode. Right?

**[0:40:04]** But then what happens if we have the voltage less than zero? Alright. If we just try to generalize this, then it would tell us that, okay, we have... You know, if we just try to generalize that expression, it would tell us that, okay, the current still flowing in the same direction, but it becomes exponentially smaller. But that's not quite correct.

**[0:40:38]** Okay. Because if we... Let's now draw a picture that corresponds to what happens if we have a negative voltage. Right? So for a negative voltage, right, that's negative voltage applied to the p side, that is raising the potential energy for the electrons on the p side.

**[0:40:55]** Okay. So the band edge energy diagram is gonna look... Oops. Look like this. Right?

**[0:41:17]** This is the conduction band edge energy, the valence band edge energy as usual. Right? We have our electrons and holes. And based on what we have said so far, right now, right, this barrier is much higher. So we should reduce exponentially the concentration of carriers that have high enough energy, say, and electrons that have high enough enough energy to move over from the n side to the p side.

**[0:41:48]** And that does happen. But remember that, right, we also have some electrons here and some holes over here. Okay? Now there are a lot more electrons over here than electrons at the same energy over here. Okay?

**[0:42:09]** So, you will have net current flowing in this direction from the electrons and in this direction, for the holes. Right? And so you will get current flowing the opposite direction from these electrons over on the p side and these holes over here on the n side. Okay? But then as you make the voltage more negative, that doesn't really change the concentrations of these electrons or these holes.

**[0:42:49]** So these contributions to the currents are roughly constant. Okay? They just depend on, you know, how many electrons we have over here and how many holes we have over here. Those don't really change with the voltage. Okay?

**[0:43:04]** And so what happens then is that the current now at negative voltage, it's in the opposite direction. And then, also, the current is roughly independent of the voltage, right, when the voltage is less than zero. Right? You'll have kind of an exponential decrease in, the current flowing to the right be... As you make the barrier higher, but, the biggest effect will be from these carriers here.

**[0:43:47]** And so if you put all this together, then what happens is that the overall current voltage characteristic, right, for a PN junction diode. Alright. It looks like the following. Alright. Replying the current as a function of voltage, and that current will be...

**[0:44:27]** It'll be some constant. We'll call it I naught times e to the eV over k b t. Alright? So this is what is going to give us the exponentially increasing current as a function of voltage in... For positive voltages.

**[0:44:48]** And then there will be a minus one over here. Right? So that when we have negative voltages, right, we get a gradually decreasing... Exponentially decreasing contribution from this, right, that exponentially decreasing contribution corresponds to, you know, the carriers that we have way up at this high energy over here. And then this minus one comes from these electrons and these holes, moving across the junction as shown over here.

**[0:45:23]** Right? And it's negative because that current is in the opposite direction. So this is the overall, expression that we get for the current in a diode. And so if we plot that out, I'll do it in blue here. Alright.

**[0:45:40]** For positive voltage, it's gonna be increasing exponentially. And then for negative voltage, it's going to kind of exponentially approach some small value like this. And then if you go to very negative voltages, then there are other things that can happen that can cause it to... That will eventually cause it to do... To sharply increase.

**[0:46:08]** Okay? But we won't talk about that in detail here. Okay. So any questions on this? Yes.

**[0:46:17]** What is the term, for minus... Well, it'd be minus I naught. Why is that, I guess, superimposed throughout the entire IV curve? What if the EC in the end... The the Mhmm.

**[0:46:32]** Conduction band energy at the n junction is greater than the con... Than the conduction band at the p junction. Wouldn't those not want to diffuse? I mean, that I naught term would sort of fall out. Oh, Yeah.

**[0:46:46]** So so the reason that we always have that minus one term there is that... Okay. There it is. This contribution is... Right.

**[0:47:02]** Let's just think about the electrons, for a second, and the holes will behave in an analogous way. This contribution here is due to sort of the high energy electrons from the n side moving from the n side to the p side, and that changes exponentially with the voltage because you're changing the height of that barrier. This minus one comes from the electrons that you have, you know, just in equilibrium on the p side. Right, this concentration of electrons doesn't change with, the applied voltage. And so, right, it's going to be constant.

**[0:47:50]** Now I I guess what you were asking if I understood correctly is that, well, if you were applying positive voltage, then eventually, maybe this would be even lower than that. So so that can happen. If you apply a large enough voltage, that can happen. But... And and this will not be quite correct when you get to that point.

**[0:48:16]** But, usually, by the time you get to that point, you have a very high current flowing, and then there will be other factors that end up limiting the current. Okay. Okay. Okay. Yes.

**[0:48:30]** So I think maybe I learned this from, but I was always told that diodes are kinda like a one way valve or currents in a sense. If it's possible to have current flowing in the opposite direction through the diode, do we just... Is it just like... Is the magnitude of that just negligible enough for us to treat it that way, or am I thinking about the whole concept of a diode as well? So so you were not thinking about the concept of a diode or the functionality of a diode, incorrectly.

**[0:49:03]** So so back here, right, there there is current that's flowing in the opposite direction, but, it is generally extremely small. Right? So, many orders of magnitude, like five or 10 orders of magnitude or more, smaller than the current that you would get once this has... Once the diode has turned on. Okay?

**[0:49:27]** So so there is this small negative contribution, but, you know, for most practical circuit purposes, that is going to be zero. Okay? Unless you have a really terrible diode, right, then this can be larger, and you have to worry about it a lot. And that's before you reach this kind of behavior, which is called breakdown of the diode. And so, you know, I've kind of...

**[0:49:55]** Right. Exponential increase is something that it looks like zero for a long time, and then all of a sudden it goes... Alright. It's very high. So, you know, if you were looking at this, right, sort of zoom down some, right, then it would look...

**[0:50:18]** Right. This be zero. It would still look like zero, and then all of a sudden, it'll turn up very rapidly. Right? And this is probably what you're thinking of.

**[0:50:30]** Okay. Yeah. Did you have a question, Nate? I... The exponential fairness scaled by, like, I naught.

**[0:50:38]** Like, I guess I'm just I'm just thinking, like, why would... Because, you know, I naught is, like, this really, really low current number. Why are we scaling more exponential like that? So you will derive that in problem set six. You know?

**[0:50:56]** But the the short... The, you know, the... Just briefly, the reason is that, you know, what... So this exponential comes from the nature of the Fermi distribution function and how the probability of finding, carriers at a given energy changes with with energy and and corresponding with the voltage. This prefactor over here, it comes from, you know, what is the probability of finding...

**[0:51:31]** This was not correct. This should be up here. It comes from the probability of, you know, what is the concentration of electrons that you have over here and holes that you have, over here? That ends up also influencing how many electrons you have up here and how many holes you have down here, through essentially what works out to be the same, prefactor. Okay?

**[0:52:00]** So, you know, so it really comes about because the concentration of electrons here and of holes, down here, those are related to each other. Right? Because, essentially, the product of the electron concentration and the hole concentration, say, the n side has to be... Is is gonna be constant, and it'll be the same as it is on the p side, concentration of the of the holes and the electrons. And because that is constant, then I...

**[0:52:36]** This prefactor effectively ends up being the same. Okay? Because right, if the concentration of holes that you had down here were not related to the concentration of electrons and not related to, in the same way, to the concentration of electrons here or the concentration of holes over here, then this would no longer be true. And so if you had different semiconductor materials, right, we're essentially assuming here these are the same semiconductor materials, say silicon. Right?

**[0:53:08]** If they were different, then you would no longer have that relationship, and, this prefactor would not necessarily be the same. Okay. Any other questions? Does that sorta make sense? Yeah.

**[0:53:24]** Yeah. I guess. Okay. Yeah. Yeah.

**[0:53:27]** And you'll see more of that in problem set six. Okay. So then the last thing that I'll say is that, you know, we've been talking about PN junction diodes, specifically in the context of electric circuits, what the current is as a function of voltage and so forth. But it turns out that p n junction diodes, you know, arguably or perhaps inarguably, their most important applications are not so much for diodes that go into a circuit for their electrical functionality. It is at least as important technologically that we have p n junction diodes for their light emitting and light absorption characteristics.

**[0:54:18]** Right? So, for example, if you look at an LED, right, a light emitting diode, right, that is basically a p n junction. And, you know, through its influence on lighting, it has really changed the world. And what is happening in a PN junction diode is basically when it's operating, it is a forward biased PN junction. Oops.

**[0:54:58]** Okay. But then, you know, as you have the electrons moving across the junction and the holes moving across the junction, right, then, you know, you have some, holes and some electrons, right, they're moving across the junction, alright, then one of the things that can happen is that as they're moving across the junction, you have a pretty high concentration of electrons here and a pretty high concentration of holes here. The electron, alright, it can recombine with the hole, so it loses energy and drops down into this empty state. And in doing so, right, that energy has to go somewhere. And, in an LED, it's designed and optimized so that that energy is given off as a photon.

**[0:55:56]** And that's basically what happens in an LED. Alright? So the electrons and the holes, alright, they recombine. Alright? And the energy lost by the electron is emitted.

**[0:56:27]** As light. Right? That's basically what's happening in, like, an LED light bulb or an LED indicator light. Yes. What what does that symbol am I speaking?

**[0:56:36]** Oh, sorry. This is h... This is the Greek letter nu, and this is the standard, symbology that is used to indicate the energy of a photon. Right? Planck's constant times, this is the frequency of the electron.

**[0:56:51]** Oh, sorry, of the photon. Okay. So so that is what is done in an l... Or what happens in an LED, you know, which really has changed the world. And, you know, kind of the inverse of that is a solar cell.

**[0:57:10]** Right? The idea there is that, again, it's basically a PN junction under forward bias. Okay. But now what's happening is that... Well, we have positive voltage that's applied here.

**[0:57:39]** Now what's happening is that you have light coming in. Alright? I'll draw it like this, And that photon can be absorbed by an electron in the valence band. And if that photon has sufficient energy, that electron can move up to the conduction band, and then the electron in the hole will move like that. So that corresponds to current flowing in, this direction, so from lower voltage to higher voltage.

**[0:58:28]** Okay? And so what is happening in a solar cell is that through this kind of process, the energy of the photon through this absorption process then gets turned into electrical energy because it causes current to flow from lower voltage to higher voltage. Right? And that corresponds to energy being supplied, and that energy is coming from the energy of the photon. That is essentially, what is happening in a solar cell, which, you know, is also changing, the world.

**[0:59:04]** So these are, you know, sort of additional functionalities that you can get from a PN junction diode that have turned out to be, you know, over the last decade or two, extremely, important. Yes. Question. So these are basically this, like, the same process in reverse with these two devices. Mhmm.

**[0:59:28]** What's, like, a mechanical difference that's making them not, like, do the same thing simultaneously, I guess? Oh, so so, actually, in an LED, this process is also occurring. And in a solar cell, this process is also occurring, but the devices are designed and optimized so that in an LED, you're kind of dominated by this process. And in the solar cell, you're dominated by this process. Yes.

**[1:00:02]** And there's probably a question that's gonna take... If you got any longer than that to answer, but I guess just, like, kind of a general idea, like, why are LEDs so good and solar cells so bad? It seems like same process, but kind of like, you know, the reverse. Mhmm. But like, so solar cells are super inefficient, whereas LEDs are...

**[1:00:21]** I mean, I know that they're, you know, fairly efficient, but maybe is it just, you know... I guess, yeah, why why does that happen? Yeah. So so there are very long answers to that Yeah. Yeah.

**[1:00:33]** Yeah. To that question. In an LED, right, they are very efficient compared to, say, an incandescent light bulb, or to a... Even to a fluorescent light bulb. You know, they're certainly not a 100% efficient, but they are very efficient.

**[1:00:54]** And, you know, so part of that is that, you know, when you forward bias the, the PN junction that constitutes an LED, then, you know, these these carriers, they... As they're moving across the junction, they... Most of their energy can get turned into light because they're gonna be... They will end up... When they recombine, they're usually pretty close to the band edge.

**[1:01:27]** Alright? And so there's not that much loss that, that can occur through, you know, losing this extra energy here or this extra energy here. There's loss that can incur through, you know, other things and such, but, you know, those are pretty well understood, and they're not as severe as sort of the non idealities that happen in a solar cell. In a solar cell, you know, it's it's very hard to make, the solar cell extremely efficient. So, you know, low 20% range is very good efficiency, right, for a solar cell.

**[1:02:11]** So part of the reason is that, sunlight is very broad spectrum. Okay? So it has a lot of different photon energies contained with it... Within it, and all those different energy photons count towards the amount of incident power. Okay?

**[1:02:30]** Now any photon that has an energy less than the band gap just cannot be absorbed. Right? Because the electron down here, right, if it if it gets... Gets absorbed... If it absorbs a photon, but the photon is too low energy, there will be no state here for it to go into.

**[1:02:52]** So the minimum photon energy that can be absorbed is roughly the band gap. Okay? Now if you have a photon that has an energy greater than the bandgap, right, then that photon, it counts more towards the amount of incident power. But what happens is that, right, you might initially get a high energy hole and a high energy electron, but then very quickly, those will relax back down to the band edge energy, and then that extra energy is lost as heat. Okay?

**[1:03:33]** Because this process of losing energy is very fast, so it'll happen, you know, almost instantly. So you lose that extra energy above the band gap. You lose just about all of it Yeah. Through processes like this. You know, you...

**[1:03:51]** If if you illuminated it only with energy right at the band gap, it would be actually very much more efficient. If you had an LED going into a solar cell somehow, you know, like, it would be a lot better. Yeah. It wouldn't be a 100% efficiency, but it would be a lot better. Yes.

**[1:04:06]** Right. And so, you know, these loss mechanisms, not absorbing the low energy photons and then losing the extra energy of the high energy photons, they dramatically decrease the efficiency of, of a solar cell. And then, you know, you get energy out the... Right? Power.

**[1:04:29]** The power you're getting out is the current times the voltage. Right? But the voltage is going to be less than... The the forward bias voltage of which the solar cell operates is gonna be less than the bandgap. Okay?

**[1:04:43]** Because the built in potential is gonna be less than the bandgap. And, right, if you look at... Whoops. Right? What's the current voltage characteristic of a solar cell when it's illuminated looks like is something like this.

**[1:05:02]** And you wanna operate at a point where the product of the current and the voltage in the fourth quadrant is the maximum. So it'll be something like this. So you don't get the full voltage person, and you don't get the full current. Right? You kinda get...

**[1:05:21]** You know, what you get is this. And, you know, the fact that the the current is a little bit lower and the voltage is a little bit lower also cuts down the efficiency. Okay. So all these things then combine to make, you know, say, a silicon solar cell that has, you know, low 20%, range of efficiency is actually really good. Okay.

**[1:05:45]** And, you know, there's, a huge amount of technological work that goes into... You know, if you can make a solar cell one percentage point better, right, that's actually quite valuable. You know? And people would, like, kill their mother to get five percentage So, yeah, so a lot of these kinds of things really are what technologists who work in these areas try to figure out. You know?

**[1:06:15]** If if you could make a solar cell that's 5% more efficient, that has a huge impact. Right? And these are the kinds of things that, people who work in these types of technologies, you know, really think about and try to improve. Yes? Wait.

**[1:06:31]** So for instance, the same diode, if sunlight's not hitting the solar cell, then there would be only the baseline reverse current. So would it turn into, like, a light emitting diode if the voltage is kept at the same rate, but there's no sunlight? So, yeah, so if you... So in the absence of sunlight, then the current voltage characteristic would look... It just...

**[1:06:57]** You shifted Yeah. Upwards. So it'd be like this. And if you were operating at some point out here, then it would behave like a terrible LED. Like, turn off at night or So what'll happen is that it'll try to operate at, you know you know, it...

**[1:07:28]** It'll... It's the same idea as here, right, except that you'll have a tiny box in here. Right? Because the current will be... You know, if if it's really in absolute darkness, there'll be no, what's called photocurrent, and it'll just be...

**[1:07:48]** It'll be operating at the origin. Alright? If it's at night, you actually get a little bit of light from, you know, the moon, stars, the, you know, reflection off the clouds of, you know, light from cities and things like that, but it's a very small amount. Right? So you'll you'll have a tiny box.

**[1:08:11]** Any other questions? Okay. So that is everything on semiconductors. Now we are going to come back in, the last few minutes today to circuits. And what we want to do now is, what we had done earlier was we talked about how to think about and analyze and design circuits, with sinusoidal signals that are at a fixed frequency, single frequency.

**[1:08:44]** What we now wanna do is to kind of generalize that idea to try to understand what's called circuit frequency response. That is if we look at a circuit and I, say, understand what it's doing at one frequency, then at another frequency, a whole bunch of different frequencies, then what does the behavior of that circuit look like as a function of frequency? And so we will develop a graphical tool. In addition to looking at it algebraically, we'll develop a graphical tool, to understand and communicate this. This is known as Bode plots.

**[1:09:32]** And then circuits that are designed to have a particular frequency response are often referred to as filter circuits because, you know, usually, what they're doing is they're giving a large response over some range of frequencies and a small response over some other range of frequencies, and that's, you know, kind of what a filter does in some broad sense. So the reading for this is in Ulaby Dahl, and it's in chapter nine. Okay. So the general idea is that, you know, what we refer to as a filter is a circuit that has some particular designed or engineered response as a function of frequency. Right?

**[1:10:23]** So filters generally leaders... These are circuits that produce output signals that have various specific and typically, useful, frequency dependence. Alright. So you can think of it as a circuit that has, say, two input terminals and two output terminals. Your input signal is at the input terminals.

**[1:11:07]** Your output signal is at the output terminals. And, you wanna have various types of relationships between, say, the voltage at the input and the voltage at the output. Okay? And then, the dependence of those relationships on frequency is what we refer to as the, the response of the filter. Okay.

**[1:11:30]** So so what are useful frequency dependencies to have in various types of filter circuits? We can have what's called a highpass filter. Okay? And what we mean by this is that if we look at the output compared to the input, in a highpass filter, the high frequency signals are trans... Basically, they're transmitted from the input to the output, quite easily, without much attenuation, and low frequency signals are strongly attenuated.

**[1:12:05]** Right? Sort of, you know, what you would expect. So in this case, what happens is that, high frequency signals are transmitted. Okay. And low frequency signals are suppressed.

**[1:12:33]** Okay. Then, another possibility is that you can have what's called a lowpass filter. Right? And this, you know, by extension and probably pretty obviously means that, right, low frequency signals are transmitted, and high frequencies are suppressed, then you can have what are called bandpass filters. And so this means that signals within some specified frequency range, okay, are transmitted.

**[1:13:45]** Okay. And then correspondingly, you can have kind of the inverse of this, which is a band reject filter. And here, the signals within a specified frequency range are suppressed. Okay. And then associated with this is what we often refer to as a passband, which is the range of frequencies, that are transmitted or sometimes we say passed by the circuit.

**[1:14:52]** Okay. So these are, some of the typical types of circuit, filters that we can have, and we're going to, starting next time, we're going to try to describe all of this, and understand it quantitatively. Right? So, we can do this algebraically. So the circuit frequency response, Right?

**[1:15:22]** This can be described algebraically by what we call a transfer function. That's what we'll start off with. Okay. It can also be described graphically by what we call Bode plots. Okay.

**[1:15:58]** And so we will look at that, as well. So any questions on all of this? Okay. If not, then we will stop here for today and pick up with a discussion of transfer functions next time. And I will now stop the recording.
