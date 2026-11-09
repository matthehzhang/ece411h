# Ulaby 12.10 video

Deepgram general-nova-3 2025-07-31.0, request 01a1b039-e06f-7142-8af1-43a2ead8702a, audio 64.7 min.

**[0:00:04]** Okay. So this is Ulaby, excuse me, problem 12.10. Okay. And this is an example of computing inverse Laplace transforms. Okay.

**[0:00:23]** So we're computing inverse Laplace transforms here. And as you will see, this is mostly a matter of doing partial fraction expansions of these functions shown here. And then using those, you can pretty straightforwardly compute the inverse Laplace transform of of each of these. Okay. So let's go ahead and get started with these.

**[0:00:49]** So we will start with part a. And, here, the function for which we want to compute the inverse Laplace transform is f one of s, and it is s plus two, the quantity squared over s times s plus one, the quantity cubed. Okay. So the first step here is going to, we can easily see what the poles of this are. They're s equal to zero and s equal to minus one.

**[0:01:17]** So we can go ahead and directly, expand this using partial fractions. So first step here will be to expand, f one of this using partial fractions. Okay. And so the form of this expansion will be that f one of s is equal to some constant coefficient k one over s plus coefficient l one over s plus one. And you'll notice that we have s plus one cubed in the denominator.

**[0:01:55]** So this is a third order pole. So we're going to have additional coefficients l two over s plus one quantity squared plus l three over s plus one, the quantity cubed. And we're gonna have to compute, each of these coefficients in order to come up with a full partial fraction expansion. So the next step then is to compute the coefficients k one and l sub I. Alright?

**[0:02:30]** I... And so the way that we compute these coefficients is remember that for k one, right, s equal to zero is just a simple poll. So k one is going to be equal to s times, I guess, it's f one, of s evaluated at s equal to zero. And it's the whole thing evaluated at s equal to zero. Okay.

**[0:02:56]** So if we take f one of s, say in this form over here, and we multiply by s, that's just gets rid of this s in the denominator. So we have s plus two squared over s plus one cubed evaluated at s equal to zero. Okay. So this is just going to be... Alright.

**[0:03:18]** It'll be zero plus two squared in the numerator divided by zero plus one cubed in the denominator, that's four over one, so that's four. Okay. So that's k one. Now for the l's, we start with l three over here. Alright?

**[0:03:38]** And l three, you'll recall, is equal to s plus one cubed times f one of s evaluated s equal to minus one. Okay. The value of the pole. Alright? So when we take f one up here and we multiply by s plus one cubed, then that's just going to give us s plus two squared over s.

**[0:04:06]** So this is going to be minus one plus two squared in the numerator divided by minus one cubed... I'm sorry. Minus one in the denominator. Okay. And this is just going to be minus one.

**[0:04:27]** Okay. So that is l three. Now for l two... Alright. Remember that we...

**[0:04:36]** The way that we compute l two, alright, is that it's the derivative with respect to s of s plus one, the quantity cubed times f one of s evaluated s equal to minus one. Alright? And the reason that it is that or the way we can see that it is that, we can see that by going back to this expression here for f one. If we take this expression here, multiply by s plus one cubed, then here, this term is just a constant. This term will be proportional to s plus one.

**[0:05:15]** This will be proportional to s plus one squared, and this will be proportional to s plus one cubed. If we then take the derivative of this with respect to s, then over here, this term is a constant, so the derivative is zero. This term here will just give us l two, and then these two terms will also give us zero because after we take the derivative, we're still going to have a factor of s plus one remaining in each of those terms. Okay. So those will go to zero.

**[0:05:47]** So all we'll have left is l two. So that's why this expression here, will give us l two. Alright? And so, what we wanna do then is we're gonna take the derivative with respect to s here. So the derivative with respect to s.

**[0:06:04]** Now of... When we take f one of s from the original expression and multiply by s plus one cubed, we're gonna get, again, s plus one... S plus two quantity squared over s. So we have s plus two, the quantity squared over s. We wanna take the derivative of that with respect to s and evaluate it at s equal to minus one.

**[0:06:28]** Alright? And so when we take the derivative, this expression here in the big parentheses, alright, then, this is just a quotient. So its derivative with respect to s is going to be the derivative of the numerator, which is two times s plus two times the denominator, which is s minus the numerator, s plus two, the quantity squared times the derivative of the denominator, which is one divided by the denominator squared, so s squared. We're gonna evaluate this at s equal to minus one. Alright?

**[0:07:05]** And if we do that, then we have two and then minus one plus two is one. So two times one is one times minus is two times minus one is minus two. So we have minus two. And then over here, we have minus one plus two. That's one squared.

**[0:07:23]** That's one. So minus one divided by, s squared, so minus one squared, that's one. So this is going to be minus three. Okay. So that is l two.

**[0:07:36]** And then finally, we have l one, which is... It's one half times d squared d s squared, times s plus one, the quantity cube, or we're taking the the second derivative of s plus one cubed times f one of s. And we're evaluating this whole thing at s equal to minus one. Alright? And, right, basically, the reason, it works out this way is that, if we go back to this expression here, we're getting l one now.

**[0:08:17]** Right? So if we multiply this by s plus one cubed, alright, then... And we take two derivatives. Right? When we multiply by s plus one cubed, this is gonna be a constant.

**[0:08:28]** So we take even one derivative, this goes to zero. This is going to be proportional to s plus one. When we take two derivatives, that will go to zero. This is proportional to s plus one squared. So when we take two derivatives, that's going to give us two times l one.

**[0:08:46]** This is gonna be proportional to s plus one cube. So when we take two derivatives, we have one factor of s plus one remaining. Evaluate that at s equal to minus one and this goes to zero. So we'll have two l one through this process. And so that's why we need to divide by this one half over here.

**[0:09:07]** Alright? So this is what we want to compute. Alright? So this is going to be one half and then it's the derivative with respect to s. We already computed one derivative of this.

**[0:09:22]** Alright. That was this expression here. Alright. So we don't have to compute that again. Let's just simplify it a little bit and write it in here.

**[0:09:31]** Okay. So to simplify, we can note that this expression here, which is the derivative with respect to s of s plus one cube times f times f one of s is two s squared minus s squared. Alright. So that's gonna be just s squared. Then we have two times two times s.

**[0:09:51]** That's four s. But then we're gonna have minus four s over here. So those cancel out. And then we're gonna have minus four from the last term from scoring the s plus two. So it's s squared minus four divided by s squared evaluated at s equal to minus one.

**[0:10:09]** Right? And that is actually, easy to simplify even a little bit more. So we have one half the derivative with respect to s of one minus four over s squared evaluated as s equal to minus one. Alright? And so this then becomes, one half.

**[0:10:31]** And then it is, when we take the derivative of one minus four over s squared with respect to s, the derivative of one is zero, then we get minus eight over s cubed. That's evaluated at s equal to minus one. Okay. So in the big parenthesis, we have minus eight over minus one cubed. So that's just eight divided by two.

**[0:10:54]** Sorry. That's... Sorry. This is plus eight, divided by s cubed. Because now when we take the derivative of minus four s squared, then we get minus two, with the minus sign that cancels out times four.

**[0:11:09]** So that's eight divided by s cube. So we have this. And then when we evaluate this at s equal to minus one, then we get minus four. Okay. So now we have our residues, minus four for l one, minus three for l two, minus one for l three, and four for k one.

**[0:11:32]** Okay. And we... If we substitute those back into this expression for f one of s over here, then what we get is that f one of s I is equal to four over s minus four over s plus one minus three over s plus one squared minus one over s plus one cubed. Okay. Now here, there's a useful point to make, which is that, if you look at the, official solutions to this problem put out by Ulaby et al, Okay.

**[0:12:28]** What I'm gonna do is go to, the other computer here and see if I can paste those in. K. So I'm gonna paste it up to this point, alright, where they've computed f one of s. Alright. So let me see if I can paste that in over here.

**[0:13:09]** K. And it should show up here. Okay. So now it's showed up here. Alright?

**[0:13:19]** And what you can see, right, is... Right, this is what they've gotten, for their solution. And if you compare that, then what you can see is that it's the same except for this term over here. They have minus eight over s plus one, and we had minus four over s plus one. Alright.

**[0:13:45]** So so what happened here? Well, if you look at, right, the coefficient, the residue that they're calculating for s plus one is b one. And if you look over here, you can see that there's a missing factor of one half. And I explained why that factor of one half has to be in there. Okay?

**[0:14:07]** So, so this is actually, the official solution here, has an error. And if you want to check to see whether, in fact, this official solution is an error or whether what we just worked out up here is an error, then, one thing that you can do, right, is you can take the original... Right. This is not the only way to do it. Alright.

**[0:14:39]** But one, relatively quick check is to take the original expression and say calculate it at s equal to one. Alright. And if you do that, you get one plus two squared over one times one plus one cubed. Right? So that's three squared, that's nine, over two squared, that's eight.

**[0:14:59]** Right? So we can see very easily that the original expression for f one should give us... And s equal to one should be nine eights. Alright? Now let's come down here and figure out what this expression gives us.

**[0:15:17]** So we have four over one, that's four, minus one over one plus one cubed, that's one over, two cubed, that's one eight, minus, three over s plus one squared. Right? So that's three quarters. And then minus eight over s plus one, that's eight over two. That's minus four.

**[0:15:40]** Right? And so if you calculate, what this gives you, then you have four minus four, those cancel out. You have minus one eighth minus three quarters. That's minus one eighth minus six eighths. So that's minus seven eighths.

**[0:15:59]** Alright? So that is not the same as what we calculated up here. Right? So, so this, cannot be correct. If you go back to what we calculated here, alright, and evaluated at s equal to one, then we have four over one, so just four minus...

**[0:16:23]** And then four over s plus one is four over two, so that's minus two minus three over s plus one squared. So that's minus three over two squared, that's minus three quarters. And then minus one over s plus one cube, that's one over... Minus one over two cubes, that's minus one eight. Okay?

**[0:16:44]** And that, right, it's two minus three quarters minus one eighth. So two minus seven eighths, and that's nine eighths. Okay. So that's actually, correct. So, we can move forward with pretty good confidence that, in fact, this is the correct expression for f one of s.

**[0:17:08]** Right. So you should not have access to these, but, perhaps some of you may have access to the... To them. And... But, in fact, in this case, the answer to this in the official solution is not correct.

**[0:17:21]** Okay. So, with that little digression, we can go ahead and, take this expression here for f one of s and use it to convert the... To compute the inverse Laplace transform. Okay. So that'll be the third step here is compute the inverse Laplace transform.

**[0:17:47]** And, now that we have the partial fraction expansion, that's relatively easy. Right? Because if we look at able 12 dash two of Ulaby at all, Alright. You can see that e to the minus a t times u of t forms a Laplace transform pair with one over s plus a. Right?

**[0:18:24]** And that includes the case, a equal to zero, right, which is that u of t forms, a Laplace transform pair with one over s. Okay. And then, since we have higher order poles, we also need this entry which is the t to the n minus one times e to the minus a t u of t forms a Laplace transform pair with n minus one factorial over s plus a to the n. Okay. And if we just use these results, then we can see essentially immediately, we're with very little work that f one of t is...

**[0:19:15]** Right. We have, the inverse Laplace transform of four over s. So that just becomes four u of t. So four. We'll write the u of t at the end since every term will have a factor of u of t.

**[0:19:28]** And then from the minus one over s plus one cubed. Alright. Hey, Ward. Rather, we go back to this one up here. Right.

**[0:19:41]** From the minus four over s plus one. Right? Then we get minus four. And then one over s plus one gives us, e to the minus t along with u of t, a factor which will, just to remind you, we'll add at the end. And then minus three over s plus one squared.

**[0:20:11]** Right? This term over here is going to give us minus three times e? So then, we're using this expression here with n equal to two. So we have the minus three, and then it's t, times e to the minus, t over here. Okay.

**[0:20:37]** So n is equal to two over here and two minus one. That's one factorial. It's just the one, so we don't have to worry about it. Alright? And then we have s plus a, squared versus what we had originally.

**[0:20:50]** And then finally, last term that we have over here is minus one over s plus one cubed. Alright. So, we have the minus sign over here. Then we have one over s plus one cubed. Alright.

**[0:21:10]** So we're gonna have t squared times e to the minus t. But then we'll have three minus one factorial. That's two factorial. That's two. So we have to bring that over here and that become...

**[0:21:22]** Over to the other side, and that becomes one half. So minus one half times t squared times e to the minus t. All of this times u of t. And this is the result. Okay.

**[0:21:41]** So that is, the first part of the problem, part a. Okay. Let's move on now to part b of this example. So we have a function f two of s, and this is one over s squared plus four s plus five, the quantity squared. Right?

**[0:22:06]** So here, right, we want to find explicitly what the poles of this are. Alright? Because we have to, do a little work at a minimum in our head, but we'll work it out explicitly here to find, the actual poles which are the roots of this quadratic in the denominator. Alright. So the first step is to find the poles of f two of s.

**[0:22:36]** Alright. So that means that we wanna look for the values of s for which s squared plus four s plus five will be equal to zero. Okay. And just by the quadratic formula, that means s is equal to one half times minus four plus or minus the square root of four squared, which is 16 minus four times five, which is 20. Okay.

**[0:23:03]** And, we can see that this is minus two. Right? It's minus four over two. That's minus two plus or minus. And then the discriminant is negative.

**[0:23:13]** Right? So we have j times our one half times the square root of 20 minus 16. That's the square root of four, which is two. So, we have plus or minus two over two times j. So just plus or minus j.

**[0:23:32]** Alright? So those are the roots of, this, function f two. And so that means that we can write f two of s as one over s plus two minus j squared times s plus two plus j squared. Alright. That's the same function.

**[0:23:56]** Alright. Then once we have f two in this form, then we can do the expansion using partial fractions. So now we want to expand f two of s using partial fractions. Okay. So the form of that expansion will be that f two of s is equal to l one over s plus two minus j plus l two over s plus two minus j, the quantity squared.

**[0:24:35]** Right? Because this is a second order pole. Right? Then we have another second order pole here. Right?

**[0:24:43]** Those coefficients, because the roots here are complex conjugates of each other, the the residues, right, will just be the complex conjugates of l one and l two over here. So we have plus l one star over s plus two plus j plus l two star over s plus two plus j, the quantity square. Okay. So, really, we just have to compute l one and l two, then, right, their complex conjugates are trivial to compute. We can just use them.

**[0:25:21]** So what we need to do here is now next to compute these coefficients or residues, l one and l two. Right? So the procedure here is the same as we used earlier in part a. Right? It still works even when the roots are complex.

**[0:25:45]** Okay. So l two is equal to... It's s plus two minus j quantity squared times f two of s evaluated at s equal to minus two plus j. Alright? And, if we compute that, right, f two of s, right, in this form over here, when we multiply by s plus two minus j, the quantity squared, we just get rid of this term in the denominator.

**[0:26:19]** So we're gonna have one over s plus two plus j, the quantity squared, where s is evaluated at, minus two plus j. Alright. So we have one over s which is minus two plus j, plus two plus j quantity squared. Alright. So the minus two and the two cancel each other out.

**[0:26:42]** So we have two j the quantity squared, that is minus one quarter. Okay. So that's l two. Then for the residue l one, right, remember that's the derivative with respect to s of s plus two minus j squared times f two of s evaluated s equal to minus two plus j. Okay.

**[0:27:15]** And so this is going to be equal to, the derivative with respect to s of... And then this function in here is just, well, this where we have s instead of minus two plus j. So it's the derivative with respect to s of one over s plus two plus j squared evaluated at s equal to minus two plus j. Okay. And, if we just go ahead and calculate that derivative, then it's going to be minus two over s plus two plus j, the quantity cubed evaluated s equal to minus two plus j.

**[0:28:03]** So that's going to be minus two divided by minus two plus j plus two plus j cubed. Okay. And so this is going to be minus two over... And then it's going to be j times two cubed. Alright.

**[0:28:26]** And, so in the denominator, we're going to have minus j times eight. So this is going to be just one over four times, j or minus j over four. Okay. So that's l one. Alright?

**[0:28:46]** Then we can take what we've just calculated for l one and l two, and also, their complex conjugates. Right? For l two, the complex conjugate is the same. For l one, the complex conjugate is plus j over four. Right?

**[0:29:01]** And we'll just substitute them into this expression here for f two of s. Right? And if we do that, then we get that f two of s is equal to j over four, alright, times one over s plus two plus j minus one over s plus two minus j. Alright? That's from this term here and this term over here.

**[0:29:37]** Alright? So we have the j over four over here, and then this minus sign that would show up over here. Alright. We just switch the order. Alright.

**[0:29:49]** That's this minus sign over here. Then l one star is plus j over four. So we have plus j over four times one over s, plus two plus j. Alright. That is this term over here.

**[0:30:03]** Okay. Then we have l two and l two star. They're the same. Alright. Times this term plus this term.

**[0:30:12]** Alright. So we have minus one quarter. Alright. That's l two and l two star divided by one over s plus two plus j squared plus one over s plus two minus j squared. Okay.

**[0:30:30]** So that's f two of s. Alright? Then from this, we can calculate the inverse Laplace transform. So now we wanna compute the inverse Laplace transform, basically, by looking up the appropriate entries in table 12 dash two of Ulaby. Right?

**[0:30:54]** So from table 12 dash two of Ulaby, then, alright, the relevant entry here is the t to the n minus one, e to the minus a t times u of t forms a Laplace transform pair with n minus one factorial over s plus a to the n. Alright? And this includes the case where n is equal to one because zero factorial is defined mathematically to be one. Okay. So using this, then we get that f one of t is equal to, from these first terms over here.

**[0:31:48]** Right, it is... There's gonna be a factor of u of t that will save to write just at the very end since it shows up in every term. Right? But we have j over four. Right?

**[0:32:01]** That's this j over four over here. And then, for the inverse Laplace transforms of one over s plus two plus j and one over s plus two minus j, we set n equal to one here, because that gives us one over s plus a I in the s domain, and it gives us just e to the minus a t times u of t in the time domain. So we have e to the minus two plus j t. Right? That's from this one over here, minus e to the minus two minus j times t.

**[0:32:46]** Right? That's from this term over here. Right here, a is equal to two minus j. Here, a is equal to two plus j. Right?

**[0:32:54]** And then from these two terms over here, we get minus one quarter. Then we have t. Right? Because now for these two terms, we set n equal to two. Right?

**[0:33:06]** The numerator here is just one. Right? Because it's one factorial. And then in the time domain, we have t times e to the minus a t where a is either two plus j for this term or two minus j for this term over here. So we have minus one quarter t times e to the minus two plus j t plus e to the minus two minus j t.

**[0:33:34]** All of this times u of t. Okay. And so now... Alright. We can simplify this a little bit.

**[0:33:44]** Right? If you look at this, you can see that every term has a factor of e to the minus two t and also a factor of one quarter. Alright? So we can pull out an overall factor of either the minus two t over four. Then from this first set of terms over here, we get j times e to the minus j t minus e to the j t.

**[0:34:12]** Alright? And then from this second set of terms over here, we have minus t times e to the minus j t plus e to the j t. All of this times u of t. Alright? But now if we look at these, we can see that this is just two j times two times the sine of t.

**[0:34:37]** This is just two times the cosine of t. Alright? And so alright. This is actually minus j times two because I... The order of these, right, I is reversed.

**[0:35:00]** This... We have either the minus j t minus e to the j t. Sine of t is either the plus j t minus either the minus j t over I j times two. Okay. So that's what we have here.

**[0:35:12]** And so if we just make those substitutions... Sorry. This is f two. Then what we finally get is that f two of t. We substitute minus j two times the sine of t over here, then, j times minus j is one.

**[0:35:29]** So we have a two. Here we have a two. We pull both of those out here and that turns the... We have two over four, which is one over two. Right?

**[0:35:37]** So we have e to the minus two t over two times the sine of t. Right? That's from this first term over here minus, t times the cosine of t. All of this times u of t. And that's the answer for, this second part.

**[0:36:04]** Okay. So now, we'll go on to the third part. Alright? That's part c of this example. Okay.

**[0:36:18]** And we have a function f three of s, and it's equal to the square root of two times s plus one divided by s squared plus six s plus 13. Alright? And so here again, right, first, we want to explicitly write out... Identify and write out the poles of this. Right?

**[0:36:42]** There are gonna be two poles that are basically the roots of this quadratic. So we wanna find the poles of f three of s. Okay. So that means that we said s squared plus six s plus 13 to be equal to zero. And by the quadratic formula, that means s is equal to just one half times minus six plus or minus the square root of six squared, which is 36 minus four times 13, which is 52.

**[0:37:16]** Alright? And, so this is going to be equal to minus three. Right? Because that's minus six over two plus or minus. Then we have a j since the discriminant quantity under the square root is negative.

**[0:37:30]** Right? It's negative... It's 36 minus 52, right, which is minus 16. So we have j times the one half that we bring in from the outside times the square root of 16, which is four. So we have minus three plus or minus j times four over two, which is two.

**[0:37:51]** Okay. And, so that means that we can write f three of s as root two times s plus one over s plus three minus j times two over s plus three plus j times two. Alright? And, that makes it, explicit what the poles are of f three of s. Okay.

**[0:38:19]** And once we have that, then we just go ahead and expand f three of s using partial fractions. Okay. And the form of that expansion will be that f three of s will be equal to residue or coefficient k one over s plus three minus j two. And then it's complex conjugate k one star divided by s plus three plus j times two. Okay.

**[0:38:58]** So, really, we only have to compute one coefficient or residue. Alright. So now you just wanna compute our coefficient k one. Alright? And we do that in what now should be a process that's familiar to you.

**[0:39:23]** So it's k one is equal to s plus three minus j times two times f three of s evaluated at s equal to minus three, plus j times two. Alright? So when you multiply f three of s by s plus three minus j times two, we just get rid of this term, this factor here in the denominator, the first factor. And then, we just evaluate what's left at s equal to minus three plus j two. Right?

**[0:40:00]** So this is going to be equal to root two times s plus one over s plus three plus j two evaluated at s equal to minus three plus j two. Alright? And so if we just plug that in, we get root two. And then for the s plus one, it's minus three plus j times two plus one. And then in the denominator, we have s, which is minus three plus j times two plus three plus j times two.

**[0:40:42]** Alright? And so we have in the numerator, it's root two. And then we have minus three plus one, that's minus two, plus j times two. And in the denominator, we have minus three plus three, that's zero. And then j two plus j two, that is j times four.

**[0:41:05]** Okay. And if we cancel out a factor of two from the numerator and the denominator and we divide these two terms, well, by j, okay, then we get root two over two. Right? That's from pulling out the factor of two from here. Then we have two over four that becomes two in the denominator.

**[0:41:34]** We just carry over this root two. And then, alright, we have j times two over j. That's one. And then we have minus... Sorry.

**[0:41:51]** It's it's j times one over j. Right? Because we can't... We pulled out a factor of two. Then we have minus one over j, which is just j.

**[0:42:00]** So one plus j. Right? So this is one plus j, the quantity, one plus j over root two, and that is just either the j times 45 degrees. Okay. And so that means that...

**[0:42:20]** And that's k one. So that means that f three of s, right, using this expression over here, with k one equal to either the j 45 degrees and then k one star then being either the minus j 45 degrees, then we have either the j times 45 degrees over s plus three minus j times two plus e to the minus j 45 degrees over s plus three plus j times two. Alright? So now we have, this expression for f three of s, and we just have to compute the inverse Laplace transform. Right?

**[0:43:11]** And, that again is pretty straightforward because these are just simple polls and we just use the appropriate entry from, the table in Ulaby. So from, again, table 12 dash two, if you will be at all, then what we have is either the minus a t times u of t. Alright? It forms the Laplace transform pair. We've used this many times now with one over s plus a.

**[0:43:45]** Okay. And so that means that f three of t is gonna be equal to right, we're gonna have from this first term here, e to the j times 45 degrees times... And then it'll be e to the minus a t where a is three minus j times two. So either the minus three t times either the j times two t. And then from this second term over here, we have either the minus j times 45 degrees times either the minus three t either the minus j times two t.

**[0:44:32]** Alright? And then all of this times u of t. Alright? Now from both of these terms here, we can pull out a factor of e to the minus three t. So we have e to the minus three t times...

**[0:44:48]** And then we have e to the j times the quantity two t plus 45 degrees, and then e to the j... E to the minus j times the quantity two t plus 45 degrees from this second term over here, all of this times u of t. Alright? But this term in here, right, you can see is just two times the cosine of two t plus 45 degrees. Alright.

**[0:45:20]** So that means that finally what we have is that f three of t is equal to two times e to the minus three t times the cosine of two t plus 45 degrees times u of t. And that's the final result for this part of this example. Okay. So that's part c. And so now, finally, we can go to part d, which is to compute the inverse Laplace transform of a function f four of s, which is minus two times s squared plus 20 divided by s times s squared plus eight s plus 20.

**[0:46:13]** Alright. So here, again, alright, the first step is to find the poles, of this. Right? The values of s for which the denominator goes to zero. So we wanna find the poles of f four of s.

**[0:46:30]** Okay. And so from this factor of s in the denominator, right, obviously, one of the poles is s equal to zero. And then the other, poles correspond to s squared plus eight s plus 20 being equal to zero. So just using the quadratic formula, that means that s will be equal to one half times minus eight plus or minus the square root of eight squared which is 64 minus four times constant term 20. Alright.

**[0:47:02]** So this is minus four because that's minus eight over two plus or minus. And then here we have 64 minus 80. That's minus 16, under the square root. So we have j. We bring in the one half from the outside, and it's the square root of 16.

**[0:47:21]** Alright? So this is minus four plus or minus j times two. Okay. So, this means that, f four of s, alright, can be written as minus two times s squared plus 20 divided by s times s plus four minus j times two times s plus four plus j times two. Okay.

**[0:47:54]** So with f four in this form, then, we can expand that using partial fractions as usual. So we're gonna expand f four of this, okay, using Partial fractions. Okay. So we get that f four of s is equal to... Alright.

**[0:48:25]** For, the pole at s equal to zero, right, we have k one over s. Okay. And then for, the other two poles at s equal to minus four plus or minus j times two, we have l one over s plus four minus j times two plus l one star over s plus four plus j times two. Alright? Because those poles are complex conjugates of each other, therefore, their residues will be complex conjugates of each other as well.

**[0:48:58]** Okay. And then once we have, f four in in this form with the poles, and their order is clearly identified, these are all simple poles, then we just wanna compute the coefficients or residues k one and l one, and then l one star is trivial to compute. Okay. So k one, the residue at s equal to zero is as usual. Right?

**[0:49:31]** We take our function, multiply it by s, and if we evaluate it at s equal to zero... Okay. So we can take, f four in this original form up here. We multiply by s that cancels out this s in the denominator, and then we just have the rest of this evaluated at s equal to zero. So it's going to be minus two, and then it's s squared plus 20.

**[0:49:59]** So zero squared plus 20 divided by s squared, zero squared, plus eight s, eight times zero, plus 20. And, so we have 20 over 20 times minus two. That's minus two. So that's k one. Then we have to compute l one, which is by basically the same procedure, s plus four minus j times two times f four of s evaluated at s equal to minus four plus j times two.

**[0:50:41]** Alright? And so if we take now this form for f four of s, multiply by s plus four minus j times two, that gets rid of the corresponding factor in the denominator. And then we just have what's left evaluated at s equal to minus four plus j times two. Okay. So we're gonna get...

**[0:51:04]** It's going to be minus two times s squared plus 20 divided by s times s plus four plus j times two evaluated at s equal to minus four plus j times two. Okay. So we're gonna get minus two times... And then s squared is minus four plus j times two quantity squared plus 20 divided by s, which is minus four plus j times two, and then s plus four plus j two, which is minus four plus j two plus four plus j two. Alright?

**[0:51:53]** And so now we're gonna have... In the numerator is minus two. And then, for this minus four plus j two, the quantity squared, we're gonna have 16. Alright. That's minus four, the quantity squared, minus j times 16, right, from the cross terms in that scoring.

**[0:52:13]** And then we have, j two, the quantity squared, which is minus four. All that plus 20. And then we're gonna divide by, minus four plus j times two. Right? That's this first factor over here.

**[0:52:32]** And then from the second factor, we have minus four plus four, which is zero, and then j two plus j two. So this is just j times four. Okay. So if we just continue this computation, we have minus two in the numerator, then we have 16 minus four, that's 12, plus 20, that's 32, minus j times 16. Right?

**[0:52:57]** That's this minus j times 16 here, divided by... And then in the denominator, we have j two times j four. That's minus eight. And then minus four times j four, so that's minus j times 16. Okay.

**[0:53:20]** And we can cancel out a factor of eight now in the numerator and the denominator. So that's gonna give us two times, or minus eight from the numerator and the denominator. So it's gonna give us two times four minus j times two over one plus j times two. Alright? So now here, alright, to simplify this further, we're gonna multiply the numerator and the denominator by the complex conjugate of the denominator, which will allow us to put this into rectangular form.

**[0:53:54]** So we're multiplying by one minus j two over one minus j two. Okay. And when we do that, we get a two times four minus j two times one minus j two divided by... And then in the denominator, we get one squared plus two squared. Alright?

**[0:54:14]** So this is going to be... We have two over five here. Right? So we have two fifths. And then, from the pot...

**[0:54:24]** Product of these two complex numbers, we have four minus j times two minus j times eight minus four. Alright. That's four times one is the four, minus j two times one is the minus j two, four times minus j two is the minus j eight, and then the j... Minus j two times minus j two is the minus four. Okay.

**[0:54:55]** And, so this becomes two fifths. So, times minus j times 10. Alright? So this is just minus j times four. Right?

**[0:55:10]** Because these cancel out to two and one. So it's just minus j times four. And so that means that f four of s... Right? So the residue l one is, just minus j times four.

**[0:55:25]** So f four of s is going to be equal to k one over s. So that's minus two over s. Okay. And then minus j times four. Alright?

**[0:55:43]** Times, one over s plus four minus j two, and then it'll be minus one over s plus four plus j times two. Because when we take the complex conjugate of l one, since it's imaginary, it gives us a minus sign. So we have minus j times four times one over s plus four minus j times two minus one over s plus four plus j times two. Alright? So that is f four, of s.

**[0:56:14]** And then from that, we can compute the inverse Laplace transform. Okay. And so, again, from table 12 dash two of u will be the l. Alright. What we have is...

**[0:56:41]** Alright. We have u of t forming a Laplace transform pair with one over s. That's actually a special case of another entry e to the minus a t times u of t forming a Laplace transform pair with one over s plus a. Right? So if you said a equal to zero here, then you get this.

**[0:57:03]** Okay. So that means then that f four of t... Right? The inverse Laplace transform of minus two over s is just minus two times u of t, which we'll include at the end. And then over here from these two terms, we have minus j times four.

**[0:57:27]** And then from this first term over here, we have e to the minus four t times e to the j two t. And then from this second term over here, we have minus, e to the minus four t e to the minus j times two t. All of this times u of t. Right? And so, if we simplify this a little bit, we're gonna get minus two.

**[0:58:06]** That's still this first term over here. And then, minus j times four is the same as plus four over j. And then we're gonna pull this either the minus four t out in front as a factor as well. So we're gonna have plus four e to the minus four t over j. And then, for this term over here, we have e to the j two t.

**[0:58:34]** And then from this term over here, minus e to the minus j two t. All this times u of t, the unit step function over here. Now this is two j times the sine of two t. Right? Then the j here in the numerator and the j in the denominator cancel each other out.

**[0:58:59]** And so what we finally get for f four of t is minus two. It's the same minus two as over here, plus eight. Eight because it's four times two times e to the minus four t times the sine of two t times u of t. Okay. And this is the final result.

**[0:59:31]** Okay. So now we're finished, working out this example. What are some of the key points? Alright. If we look at this retrospectively, right, right, what you've now seen four times, in this example is that the general procedure for computing inverse Laplace transforms is, to identify the poles if they're not obvious.

**[0:59:56]** That includes complex poles and then identifying correctly the order of those poles. Expand then your function in the s domain using partial fractions, compute the partial fraction coefficients or residues. And then once you have the partial fraction expansion, then it's easy to find the inverse Laplace transform using the standard forms in Ulaby et Right? So the general procedure k, for computing inverse Laplace transforms, right, is for us to identify the poles and their orders. Right?

**[1:00:52]** This includes complex poles. Then expand, the function that you have in the s domain using partial fractions. Okay. And we saw many examples of how to do that, in this example. Alright.

**[1:01:23]** Compute the partial fraction coefficients. Right? Or we can also refer to those as residues. And then finally, find the inverse Laplace transform using the standard, forms and sometimes other properties, that we have in the tables in Ulaby et al. Alright?

**[1:02:12]** And those tables are also in a handout that you have gotten or or will get depending on, when you were watching this. Okay. Then, the second point that we want to note here is that as we saw in one part of this example, in part a, that I... Right. Even if you have access to, the published or textbook solutions, then you cannot always count on their correctness.

**[1:02:42]** Alright? So the published or textbook solutions are not always reliable or correct. Okay. Sometimes your solutions, may not be correct. And, we saw one instance, when I pointed that out in part a of this example of, you know, one way that you can do a quick check, to see if, your solution or the, published solutions are, correct.

**[1:03:30]** Right? If you get something that's inconsistent, then you know that something somewhere is not correct. If you get something that is consistent, then it increases the likelihood actually by quite a lot that I... It is actually correct. Okay.

**[1:03:46]** So being on the lookout generally for for mistakes both in what you see elsewhere and in what you're doing yourself is something that is useful and worthwhile to develop as a habit. Alright? And finally, we saw here, through many examples as well, that's... It's important, right, to be proficient and accurate in performing Complex algebra. Okay.

**[1:04:33]** So that is everything for this example, and I will now stop the, recording.
