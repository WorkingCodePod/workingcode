---
title: "135: Note To Self v0.3.0"
description: "On today's episode, the slippery slope of the 'Shift Left' mentality; over-complicating life with JWTs (JSON Web Tokens); dangerous public-on-public method invocation; and, the inherent cost of everything."
date: 2023-07-12
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/135-note-to-self-v0-3-0/id1544142288?i=1000620890080"></iframe>

On today's episode, we invite you into another dimension. A dimension not only of sight and sound, but of mind. Ben's mind. Ben's sick, twisted cavern of decay and depravity wherein we gain insight into what actually makes this man tick. Topics include the slippery slope of the "Shift Left" mentality; over-complicating life with JWTs (JSON Web Tokens); dangerous public-on-public method invocation; and, the inherent _cost_ of _everything_.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/135-note-to-self-v0-3-0.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Adam:** Note to self, everything costs money, time, attention, nothing is free, and thinking any of it is free is making me sad.

[00:00:12] **Tim:** Sad Keanu meme,

[00:00:13] **Carol:** Oh, yes. All right.

## [00:00:35] Intro

[00:00:35] **Adam:** okay, here we go. It is show number 135 and we have everybody on the show today. Welcome back,

[00:00:40] **Carol:** Whoa.

[00:00:41] **Adam:** Good to have you. I'm Adam. They are everybody, And today on the show, we're gonna do another uh, note to self episode.

[00:00:49] **Adam:** Our, our good friend Ben Dell is continuing to pepper us with his

## [00:00:54]

[00:00:54] **Adam:** notes to himself. and so we're gonna go through those and, and there are some interesting, interesting, blah, and there are some interesting things to discuss there. So, But first, as usual, we'll start with our triumphs and fails and as I think is becoming tradition, on a note to self episode.

[00:01:09] **Adam:** Ben why don't we start with you?

## [00:01:11] Ben's Failiumph

[00:01:11] **Ben:** All right, I'm gonna go with uh, fum which is, you know, combination. Little, little from column, a little from column B as far as triumphs go. I took a bunch of photos with people at CF camp, which we discussed last week, and I spent this previous holiday weekend doing color correction and resizing and cropping and adjusting white balance and stuff.

[00:01:33] **Adam:** Putting little arrows on them. That's me.

[00:01:35] **Ben:** So I don't do the arrows anymore cause that's too much work. It's like, it's, it's, it's already enough with the uh, photo, the color correction.

[00:01:42] **Tim:** I think people know it's you by now.

[00:01:43] **Ben:** Yeah. Yeah, yeah, yeah. So I was, I'm excited to have gotten that done. It did take like an absurd amount of time. I think I probably spent like, I don't think it's an exaggeration to say like maybe 16 to 20 hours or

[00:01:57] **Carol:** Woo.

[00:01:57] **Ben:** doing, and on a holiday weekend

[00:01:59] **Adam:** many new photos did you

[00:02:00] **Ben:** I think like 30 something. It was, it was a good, it was a good expedition.

[00:02:06] **Adam:** so almost an hour per photo.

[00:02:08] **Ben:** yeah, it's, it's not a skillset that I have ready to go. So it was kind of learning on the, on the, on the go and, and I was watching some Udemy classes on. Affinity photo, which is what I've been using, seeing as a, a Macromedia fireworks, which has become Adobe fireworks, which has become end of life.

[00:02:26] **Ben:** So I, I need to put my bets on a new piece of software. So anyway, so I'm excited that I got that done, but that did really suck up my entire amount of free time that I had. And so I haven't been working on my Dig Deep Fitness stuff very much, and my blog has become a little bit of a ghost town. I mean, if you look at the last couple of weeks, The only pros that I have are from working code podcasts which is, which is nice.

[00:02:52] **Ben:** But you know, I like to have a little bit more of a cadence to uh, to my writing. Yes, thank you. You're keeping the blog alive. So I'm, you know, I think I had mentioned in one of the previous tris and fails that I've been, I've been struggling to be enthusiastic about more than one thing at a time, and that is continuing to be a little bit of an issue.

[00:03:12] **Ben:** But I'm hoping to, to focus a little bit more on writing. We'll see. So that's what I got. Carol, how about you?

## [00:03:21] Carol's Triumph

[00:03:21] **Carol:** All right, I'm gonna go with Big Triumph. I finally picked a start date for the new job today.

[00:03:27] **Ben:** Oh, yes.

[00:03:28] **Carol:** They've only asked a couple times and I've just kind of, you know, been putting it on the back burner and I've decided to start working again September 25th.

[00:03:38] **Tim:** Wow, that's out there.

[00:03:39] **Ben:** Dang.

[00:03:40] **Carol:** pretty much could have taken like a year off at this point from not working.

[00:03:44] **Carol:** But the

[00:03:45] **Ben:** a sabbatical.

[00:03:46] **Carol:** The reason why I decided to take the time off was we'd move again August the 29th, and all of our stuff will be in storage for a month. So pretty much puts me getting to the new house and getting our stuff and then starting the job that way I don't have to transport monitors and multiple, you know, laptops and computers and all the hardware to Arizona with us, and I don't have to deal with trying to get off work when everything arrives or trying to go in process at this new Army post.

[00:04:18] **Carol:** So it just made sense to push it out and they were willing to let me wait to start later being that it was for, you know, military reasons. They kind of, you know, have to say yes to it. So September 25th, I will start the new job.

[00:04:34] **Adam:** Well, congrats

[00:04:35] **Carol:** Thanks.

[00:04:36] **Tim:** I, I think it's funny, I, I'm, I'm contrasting your immediate emotional reaction when you first got, you know, fired. I, you know, late, I think we used Laid off, but you were fired.

[00:04:46] **Carol:** fired. Yeah.

[00:04:47] **Tim:** was fired. And you're like, cutting, like, we're gonna get rid of cable, we're gonna, you know, cancel Netflix. You're, you're like, you going into, into poverty mode, right?

[00:04:56] **Tim:** You're, you're like, you, we can't spend any money. We're gonna have to eat Ramen every day. And then now you're like, it's been how many months?

[00:05:03] **Carol:** I got le okay, I got fired the last week of January.

[00:05:07] **Tim:** Yeah. So, yeah. I mean, it's been over half a year and you're like, you know what? I could, I could probably take a whole year, eh, I'll start in

[00:05:14] **Carol:** fine. Let's,

[00:05:15] **Tim:** we're good. We're good.

[00:05:16] **Carol:** let's take the whole family to Disney World. Yeah, you are right. I definitely went through that, cut everything off up front because I grew up with nothing. I grew up very poor. I grew up where, you know, we went and paid the power bill every day with coins we could find to try to keep the lights on like another day at times.

[00:05:36] **Carol:** Like I can remember that type of poverty. So like the minute I lost my job, my gut instinct was, this is gonna happen again and I can't let this happen. And then suddenly, you know, I had set things up to where it didn't really happen like that and my family was taken care of, and Steve, you know, is financially stable too.

[00:05:54] **Carol:** So we were just fine because we had prepared, but I still didn't realize it.

[00:05:58] **Tim:** Yeah. That, that's like, that's why I called it an emotional reaction. You're, you're, you're going, you're going to the mattresses man. You're going to the mattresses.

[00:06:05] **Carol:** yeah. But yeah, so

[00:06:07] **Adam:** measures come in quick.

[00:06:08] **Tim:** Yep.

[00:06:09] **Carol:** I'm excited to start the new job and I'm excited to take a few more weeks off work before I start, so, yeah.

[00:06:17] **Ben:** Very cool.

[00:06:17] **Adam:** Yeah, I mean, I wouldn't want to have to like start a new job and pick up and move at the same time. That would

[00:06:22] **Carol:** No, no, just the headache of getting all of our stuff to Arizona is enough. Like we meet with our kind of final briefing tomorrow to go through all the process for finalizing the move. So the month of September is gonna be hit or miss for me, you guys, but I'll do my best.

[00:06:38] **Adam:** okay.

[00:06:38] **Tim:** I mean, I don't know why you'd be worried about moving. Nothing bad happened this last

[00:06:41] **Carol:** Oh my God. Right? They're like on, on the forms we fill out. It's like, do you have a moving company you prefer that the government's contracted with? And it's like, do you have any movers you don't wanna use? And I was like, pods don't put any of my items in a pod that, that's the only thing I ask. Yeah. So wins for me.

[00:07:01] **Carol:** Yay. What about you, Tim? What you got?

## [00:07:04] Tim's Failure

[00:07:04] **Tim:** I'm going with a fail. I, I, I missed several episodes recording with you guys cuz they're putting in, so I thought my fiber company was coming out and doing some work. It turns out it's, it's another company. It's a electrical co-op around here called FL Energies, and they're coming in and putting, they're just putting fiber in everyone's house.

[00:07:24] **Tim:** I mean, they're not hooking it up to their house, but they're running the, the lines. And so they cut mine. That was with a different company and they, they knew they cut it, so they reported it, but they gave the wrong address for the cut. So I'm sitting, I, I'm sitting here thinking, oh, they'll fix it anytime now, whatever.

[00:07:42] **Tim:** I tried to go down there and talk to the, the guy. No one spoke English. There was like 20 guys out there. No one spoke any English. Put under Roberta Quest and they're like, oh, we're really backed up. We can maybe get to you next week. I'm like, oh my God.

[00:07:51] **Ben:** No, that's awful.

[00:07:53] **Tim:** But then my, my daughter was walking the dog one day and she said, oh, there's a, there's a guy, you know, down there messing with the fiber.

[00:08:01] **Tim:** So I ran down there and talked to him and he, he said, oh, is it yours? That was cut, that we cut. I'm like, I guess so. And so he explained, you know, we're with a different company. And and so he immediately called eight 11 and he says, Hey, remember he had, he had gave the wrong address for the fiber cut, basically.

[00:08:17] **Tim:** So he called and they, they showed up and like within an hour and a half and fixed it.

[00:08:22] **Ben:** Maybe this is a silly question and maybe no one here can actually answer this, but my very basic naive understanding of fiber optic cable is that, The, the light sort of like bounces around inside the, like it bounces off the surfaces of the, of the wire itself. So if, if you cut it and then how do you fix it such that the integrity of the light transmission is not interrupted, they actually have to like pull it out and like

[00:08:50] **Tim:** Yeah, they, they, they re they, they've rerun it each time the entire, I have a very long driveway, extremely long driveway, and they have to, basically, they don't even pull up the old fiber. That's why the, the guy didn't know what he had cut, cuz there was like four lines that previously they had screwed up. It's like, I'm not sure which one of these is right. So, but yeah. But yeah, they, they rerun it every time and they have like a special end like that goes on each end of it. But yeah, they can't just like, do like

[00:09:18] **Ben:** Yeah, you can't just like patch it.

[00:09:19] **Adam:** Well, but there's gotta be the, there's no way. Like they don't have to run fiber from your house to

[00:09:25] **Ben:** the I S

[00:09:26] **Adam:** P, right? So that there has to be switches in the middle. There has to be. Like junctions. There's like, you can do two RJ 40 fives for the, for cat six or whatever. And you can get a little coupler between them.

[00:09:37] **Adam:** So there's gotta be something similar for

[00:09:39] **Tim:** I know they have this, I've seen them put this little coupler like thing, but, but, but typically if there's been a fiber cut, they just rerun the whole thing every single time.

[00:09:46] **Carol:** Cuz it's hard to maintain that underground.

[00:09:48] **Tim:** Yeah, they keep the, I mean the, the little junction is inside, they call it a flower pot is where the, it's little plastic looks like a man, like a square man manhole cover.

[00:09:59] **Ben:** Yeah. Yeah.

[00:10:00] **Tim:** and so that's where they do the junction in there and then at the house. So anyway, I, I'm back miss you guys. Sorry I missed so many episodes. Um,

[00:10:08] **Ben:** Good.

[00:10:08] **Carol:** We missed you too.

[00:10:10] **Tim:** I'm sure you talked badly about me behind my

[00:10:12] **Ben:** We talked about how handsome you were actually at some point I think.

[00:10:15] **Tim:** I'll never, I'll never know cuz I'm not gonna go listen. So,

[00:10:18] **Carol:** That's what we said too.

[00:10:21] **Tim:** all right, that's me. How about you, Adam?

## [00:10:23] Adam's Triumph

[00:10:23] **Adam:** I am going to take something that kind of sucks and turn it into a triumph. So, I, for, for, I don't know, maybe definitely more than 10, probably close to 15 or 20 years. I had a wart on the bottom of one of my toes, and I didn't know it was a wart. I just thought it was a callous, you know, it just looked like a sort of a, a more light colored piece of skin on my toe, and it's where it would rub on other toes.

[00:10:44] **Adam:** I'm like, okay, fine. That's callous. No big deal. And then, you know, like, like, six months ago or or eight months ago, I was like, wait a minute. That one callous is now like four callouses and it's spread to another toe. I'm like, this

[00:10:55] **Carol:** Oh no.

[00:10:57] **Adam:** So I went into a podiatrist and I saw them, and yes, it's warts and they're removing it.

[00:11:01] **Adam:** That's, you know, pretty bog, standard fact of life. Right. So, but it's, it's really painful. This particular podiatrist they're. Preferred method of removal is the, like basically chemical burns, right? There's, you could do liquid nitrogen and freeze it off, or they can like surgically remove them, or there's, I think there's a third thing or another one that's not this, but what he likes is the, you know, basically he takes the peppers that Tim grows in his yard and he just wipes 'em on the bottom of my toes. And and it turns into blisters. Like they, they put the chemical on my, on your toes, just like they, they take the, it kinda looks like you take a, a q-tip, right? That you use to clean the wax outta your ears. Only the stick part is made out of wood and they just cut the, cut the end off of one end of it, right?

[00:11:40] **Adam:** So it's just like this tiny little piece of wood. And it dips that in the bottle, in that tiny little dot. He just like bop, bop ba, right where he wants, it's a very precise like placement of like half of a drop or a quarter of a drop of this liquid on the spot. And then they put a bandaid over it and they're like, in exactly four hours, not four hours and 15 minutes in exactly four hours.

[00:12:00] **Adam:** You need to scrub this off with soap and water or you will regret it.

[00:12:04] **Carol:** man.

[00:12:06] **Adam:** Because it, it, you know, it, it's causing the skin to blister and it's killing skin cells in order to kill the, those wart cells or whatever and have the body remove them. Anyway, so this is my fourth treatment that I had today because, you know, the first three just weren't good enough and apparently that's pretty, pretty rare

[00:12:21] **Tim:** Probably should have went that extra 15 minutes.

[00:12:22] **Adam:** Yeah, well, no, I mean, that, that would be good, right? That would like be killing deeper skin. But anyway, I guess because I had them for so long, they just grew really deep within the skin. But all, all of this to say, yeah, all this to say I've, for months now off and on, I've had to, you know, be limping around, babying my foot because of blisters on my one toe and I finally found a good solution.

[00:12:47] **Adam:** So if anybody ever has to deal with this I went on Amazon and I found little toe spreaders that you can use for,

[00:12:54] **Carol:** For painting your nails.

[00:12:55] **Adam:** Yeah. Painting your nails. And well, so, and the reason that I thought about this is because the blisters are pretty far forward, like up toward the nail end of my toe.

[00:13:05] **Adam:** And I guess I kinda have long toes. And I was like, you know, if I could just keep these toes from touching each other and touching the ground, the ones that have the blisters on them, that would probably be fine. You know, previously I had like wrapped them up in, in gauze to try, you know, in that cartoon when, when a character like hits their thumb with a hammer and they like wrap it up and it's like a bowling ball of gauze around their thumb.

[00:13:25] **Adam:** That's kind of what I did to my toe. And it was like, okay, you know, I can, I can tolerate this. It's, it brings the pain down to a point where I can kind of mostly walk normal. But this thing, man, I, I've only, it only came in the mail today, but it was like instant relief doesn't take up any room I could put on my sock and shoe.

[00:13:40] **Adam:** Oh my God, it's so nice and I'm so happy to have found that. So I just have to pass that on. If anybody ever has like a problem with your toe and you just won't, don't want them to touch each other. I mean, I paid, I paid extra to get Overnight chipping because I wanted them now.

[00:13:54] **Carol:** So badly.

[00:13:55] **Adam:** Yeah. And I mean, it was like $6 for a hundred, something of them little, just little foam things.

[00:14:01] **Adam:** It's like little foam squares with a cutout for your toe. It's like a U shape. And you just wedge one up in there and it keeps the toes apart. And man, that's so great.

[00:14:08] **Tim:** And Pat patrons, if you wanna hear about my bunions, stay for the after show.

[00:14:14] **Adam:** Sorry, not sorry.

[00:14:16] **Carol:** Oddly enough, I was just thinking kind of like if someone hasn't listened to the show ever and they like, this is their first episode joining, they're like, oh, so this is what it's like to like be an engineer in the day. Right. You get words on your toes. You do? Yeah.

[00:14:34] **Adam:** Yeah. From all those strange showers that we have to use, essentially. I don't know.

[00:14:37] **Carol:** Late nights lots. It's Mountain Dew. It's from all the mountain de, there you go.

[00:14:41] **Adam:** You're killing my chance at a Mountain Dew sponsorship here, Carol. That's okay. Anyway, so that's my, triumph for the day I'm in. I'm, I'm finally found, I finally found relief, so I'm happy about that.

## [00:14:54] Book Club Update

[00:14:54] **Adam:** So normally we would do a book club recap. We are still trying to recover from the chaos and the holiday and everything else.

[00:15:01] **Adam:** So we still haven't met as a book club. I, I did find out, so last week I mentioned I, I missed it because of chaos. And I hoped that they had that meeting without me. It turns out that they did, which is wonderful. Thank you guys for carrying on. They, they did say they missed me, so I was happy to hear that.

[00:15:17] **Adam:** But yeah, so I'm looking forward to it. We'll get it back on, back on track and,

[00:15:21] **Carol:** for Monday at five.

[00:15:23] **Adam:** yeah,

[00:15:24] **Carol:** And what chapter do, do we need to be through?

[00:15:27] **Adam:** so that is a good

[00:15:29] **Carol:** Because the chaos got me very confused cuz I thought it was 21, but I guess now it's not 21. It

[00:15:34] **Adam:** Yeah, we're doing more than one chapter a week. Right. So, the last time that we had left off, So I believe we were reading up through chapter 20 and I believe that's what they covered in that last meeting. But then the next one would be 21 through 25.

[00:15:49] **Ben:** Uh, Okay.

[00:15:50] **Carol:** So 25. All right.

[00:15:52] **Adam:** Yep.

[00:15:52] **Ben:** I have

[00:15:53] **Tim:** the Phoenix Project,

[00:15:54] **Carol:** Yep. The pH bar. Yep.

[00:15:56] **Adam:** So I have a couple chapters to catch up on by

[00:15:58] **Ben:** Yeah, same. Z.

[00:16:00] **Carol:** Yeah.

[00:16:01] **Adam:** easy reading, so

[00:16:02] **Carol:** Easy

[00:16:03] **Carol:** listening.

[00:16:04] **Adam:** Yeah. Alright, well then I guess that brings us to our topic du jour. Anybody want to go first? You, Ben, you said you had one you wanted to add, right?

## [00:16:14] Specialization and Shifting Left

[00:16:14] **Ben:** Yeah, I can kick it off, I guess. All right, so, Note to self. As engineers, we're often lulled into thinking that developers should know more about platform stuff because it's all technology, but this is a slippery slope. Why not become an expert in design so that you don't need a designer or get into sales so that you don't need a sales team? there's a reason that we have specialization.

[00:16:37] **Ben:** The likeness of the context can fool us into thinking that specialization isn't important.

[00:16:43] **Ben:** Th this is something that comes up at work, which, and, and, and I hear this on podcasts as well. There's this, there's this idea, I think it's called Shifting Left, that more and more things are being shifted towards the developer end of the spectrum.

[00:17:00] **Ben:** It's not, you don't just have. A QA team. You have developers who are more in tune to quality assurance. You don't just have a security team. You have developers who are more attuned to security. You don't have just a, an accessibility team. You have developers who are more in tune with accessibility. You don't have a DevOps team.

[00:17:17] **Ben:** You have developers who are more in tune with how platforms work.

[00:17:20] **Tim:** And those make up your team. There you go.

[00:17:23] **Adam:** Yeah, it, it's, I think you're right. I think it is a slippery slope. I feel like what it, what it, the, the negative that I see is that as a small company, that's a lot of jobs, right? A lot of specializations that any one person has to have versus you know, the, the, that's the opposite side of the coin, where the, the, the good side of that is that with the opportunity to specialize, we can get really thoughtful and complex in a good way, I guess.

[00:17:52] **Ben:** There, there was, so there's this comedian, he's dead now, but this guy, Mitch Hedberg I dunno if anyone's ever heard of

[00:17:58] **Tim:** Oh yeah.

[00:17:58] **Ben:** He had kind of very, like, very monotonic delivery and kinda like funny little punchlines. But he has this one bit where he talks about h as, as a comic, he was asked to, I think like become a writer for a TV show.

[00:18:15] **Ben:** And he was like, that doesn't really make any sense. It'd be like going up to a cook and saying, Hey, you're really good at being a cook. How do you feel about running a restaurant? Like it's a totally different skillset. It just happens to sort of be co-located. And I, I a little bit feel the same way with platform oriented stuff.

[00:18:34] **Ben:** Like just because platforms are managed with technologies that somewhat overlap with what we do to on a day-to-day basis. I don't think that there should be this assumption that developers should just be better at platform stuff. I, I think you can benefit, but I, this idea that it should be part of how you work seems dangerous.

[00:18:58] **Tim:** I, I think one of the problems I've seen though in my history is that if you just have like a platform team or you know, we call it ops team and then you have a development team, there's stuff that kind of falls in the cracks between those two things, where ops team, they're just looking at logs and stuff.

[00:19:17] **Tim:** They're like, oh, everything seems to be fine, and programmers are looking at an error. And they're like, I don't really know why this area works on my machine. It works in staging, doesn't work in this other environment. I mean, Carol knows what I'm talking about. And, and so if you don't, typically a person who has a little bit of feet in both worlds can look at the and go, oh, you know, this is, you know, this is, this is caused by the infrastructure set up that's causing this air here, not there, and knock it out pretty quick.

[00:19:43] **Tim:** So, I mean, I get the lull, the lull of that.

[00:19:46] **Ben:** So I do think I, I, I a hundred percent agree that if you have your feet a little bit in both worlds, You can be more effective cuz you better understand the, the vertical integration of the stack. You better understand where issues in bottlenecks might be arising from. I think part of what I am reacting to is that oftentimes in conversations about the delineation between DevOps and product engineering, someone will say something like, oh, we should just give the product engineers access to.

[00:20:19] **Ben:** Kubernetes or we should just give them access to some low level tool because like that'll solve the problem. And I feel like that is definitely not gonna solve the problem. If anything, that will give people guns to shoot both themselves and other people in the foot.

[00:20:33] **Carol:** that's where I spent hours, down a rabbit hole that I don't need to be down. Like I, I, I agree with Tim, like I need enough understanding to communicate to every team involved, just enough understanding of what they do and how I think what I'm seeing is related to how their side handles it.

[00:20:50] **Carol:** But I definitely don't need to be handling any of our cloud setups. I don't need to be managing when we delete files like from aws, like I need, like none of that should be in my control. Some other person needs to be handling this, and they need a very deep understanding. I need to understand how to write the code and how the application runs and where it function at, not, not how the platform actually is handled.

[00:21:16] **Tim:** Mm-hmm. I, I think we as developers sometimes might think we're a little more knowledgeable than we actually are, because we know how to set it up on our machine. Yeah. We, we know, you know, we can, we can deploy Docker on our machine and we can do this sort of stuff, and we can mess around with the, with the, with the web server and, you know,

[00:21:32] **Carol:** Look at me. I'm fancy.

[00:21:33] **Tim:** look at me. Look, I'm doing on my machine. But, you know, you, you start putting that in a cloud environment with, you know, microservices and all this. I mean, that's a whole different olive of yarn there that you're messing with

[00:21:46] **Carol:** Yeah.

[00:21:47] **Ben:** I get, I get even frustrated with. Some, the fact that I have access to things like designating the number of C p u cores that are allocated for my service,

[00:21:58] **Carol:** Why? Why do you need that?

[00:21:59] **Ben:** I'm like, I don't know how much it should be. I, I don't know what three milli cores even means, and like why you can have that in decimals, like 3.2 milli cores like that.

[00:22:09] **Ben:** Even, even if it was physical cores, like I'm a software engineer. I don't understand necessarily in an effective way how the number of cores. Affects the way the software runs or if having

[00:22:21] **Tim:** the pricing

[00:22:22] **Ben:** better. Yeah, that's another thing. They're like, oh, do you want like a, like an M 27 XL RAM oriented machine?

[00:22:29] **Ben:** Or do you want like a z not extra small processing oriented machine? Like,

[00:22:36] **Tim:** A micro with, with, with bursts,

[00:22:37] **Ben:** yeah, like, I don't know.

[00:22:39] **Carol:** B please. I don't know. Yeah.

[00:22:42] **Ben:** So I do feel like there is. Continued strength in having specialized teams, and again, I do think there is a benefit to having a little understanding of how the other side of the world works, but having one person become an expert in more than one thing doesn't feel like the generally applicable solution to making a team more effective.

[00:23:06] **Carol:** I feel like I wouldn't be good at all of it, then like I would just be kind of okay. Like I need to be able to be great at something and that doesn't allow for me to be great.

[00:23:16] **Adam:** Okay. Sounds like we've covered that one.

[00:23:18] **Carol:** All right.

[00:23:19] **Adam:** Carol, you wanna go

## [00:23:20] JWTs and Cookies

[00:23:20] **Carol:** Yeah. Yeah. So this one's from January the 11th. All right, so note to self, another JWT vulnerability was announced today. You know what? Never had a vulnerability. Using cookies to store session tokens.

[00:23:36] **Ben:** Yeah.

[00:23:36] **Carol:** Heart, heart, heart, and nadel.

[00:23:40] **Adam:** Has it though, I mean there things like cores and CSRF exist

[00:23:49] **Carol:** do. Yeah.

[00:23:51] **Adam:** because because there, like there's ways to use that for nefarious purposes.

[00:23:57] **Ben:** Yeah, I mean, I'm not saying that cookies is a. Perfect solution. I think when JWTs came out as an industry, we just became infatuated with this idea that we could have a J S O N payload that you could pass around. And in my experience, which is, you know, very personal and very limited, JWTs just cause a lot of complexity.

[00:24:22] **Ben:** And there are vulnerabilities or I don't know if vulnerabilities is the right word, but there's a way to do things not securely. Whether or not you're like forgetting to validate a hashing algorithm or you're, I don't know,

[00:24:34] **Adam:** It's extra work. Yeah.

[00:24:36] **Ben:** there's extra work and cookies are, are so battle tested and over the years are continuing to become more security conscience with the, the strict cookies and H D P only cookies and secure cookies.

[00:24:50] **Ben:** And you can lock it cookie down to a particular path within an application. You can lock it down to a particular subdomain. You could say it's available for, you know, multiple subdomains. It's just such a powerful, flexible, secure storage structure. The fact that anyone like opts into A JWT at this point, unless they have a really good reason to, feels to me like a misstep.

[00:25:17] **Adam:** Yeah. I was just sitting here trying to think like, okay, well then I, I a hundred percent agree, like cookies have been around forever and so we know, or, or we feel like we've run into most, if not all of the ways that you could compromise them. And so these are all solved problems, right? You were talking about secure cookies and HTP only and path specific cookies and that sort of thing. The only thing I can think of where you would have to choose something else other than cookies is if you don't have access to cookies, which

[00:25:45] **Carol:** Yeah, like service or. Of her validation.

[00:25:47] **Adam:** I mean, you could use cookies. I guess the, the, where it might be necessary is if you are not just like a single device that wants to have that session or whatever you wanna share that around or something like that,

[00:26:00] **Tim:** Yeah, that's, that's, that's what I was thinking about. What, what if you've got a cluster of servers that's calling, say for instance an api and it could be coming from any machine. That cookie's gonna be stored locally on the machine doing the calling. Right.

[00:26:14] **Adam:** I mean, the cookie is just a request header, right? The entire body of the cookie gets included as a request header in every request.

[00:26:21] **Ben:** I mean, I, so I, I guess when I think about JWTs versus cookies, I'm very specifically talking about a user facing application where.

[00:26:31] **Adam:** Yeah.

[00:26:32] **Ben:** instead of passing, instead of having the browser, and that's, this is another thing, right? Cookies automatically get passed with your requests. It's, it is just so seamless and with a JWT, because it's typically stored either in memory or in local storage.

[00:26:46] **Ben:** You then have to build the mechanics that actually pass the JWT to the server in requests that need authentication. And then there's all this jazz about, well, the JWT should expire every 15 minutes to make it secure. So then you also have to have a refresh token. And then as you're coming up to those 15 minutes, you have to make a request to get a new token.

[00:27:08] **Ben:** But to me, even that it seems so unlikely to work well because in any application that has heavy client side interactions, you might be making 5, 6, 7 parallel requests, and then is one of those making the refresh. And then what happens to the other ones that are already in flight and have already sent the old token.

[00:27:26] **Ben:** I mean, it's just, it just seems bananas. In fact, at work, we just ran into another issue with JWTs. We have our marketing site puts people into a signup funnel. And as part of that signup funnel, it was passing through a JWT that said, Hey, this user wants to sign up for this particular plan. And the J w T was signed and it had an expiration date.

[00:27:53] **Ben:** And the only reason that it had all of that in place was to theoretically prevent the user from changing the type of plan they were gonna sign up for. I'm like, this ended up causing issues because we were actually sending over expired tokens unbeknownst to us, and the code ended up just skipping over that and defaulting to a different plan on, on like in the failure case and the side case, like if you had just sent that through as a URL parameter it, it would've been fine.

[00:28:20] **Ben:** Like you didn't even have to do this fancy stuff, you just wanted to overcomplicate it for reasons that I don't fully understand.

[00:28:27] **Tim:** That's probably just what they were used to working with. Oh, they're like, oh, I'm used to using jwt. So

[00:28:33] **Ben:** Yeah, so I'm just, I'm just a big fan of cookies and you know, it's not your, I feel like it's not your grandfather's cookies anymore, right there, there's a lot of security options that go into how you designate and how you transport cookies.

[00:28:48] **Adam:** a

[00:28:48] **Tim:** you're in Europe and then you gotta ask permission.

[00:28:52] **Adam:** Oh, okay. Yeah. So actually there's, there's kind of two things that I've been kind of parallel thinking about here. One, whoever named these things or, or gave them their acronym, I guess, I guess naming them, thus giving them their initialism is dummy, let's say, could have done a better, could have done a better job.

[00:29:12] **Adam:** So never use a word that starts with a w when you're, could be creating an initialism, right? J w t that's five syllables

[00:29:23] **Carol:** It is, it's big. Yeah.

[00:29:25] **Adam:** Right? And so people call it a jot, right? Because it's, because j w t is a mouthful. If they had instead called them J s o n internet tokens instead of j s o web tokens, you'd have JIT

[00:29:36] **Ben:** I could say legit,

[00:29:38] **Adam:** or j i d

[00:29:39] **Ben:** that's

[00:29:40] **Adam:** three syllables.

[00:29:41] **Adam:** Anyway, anyway, that's, that's the easier of the two things I've been thinking about.

[00:29:46] **Tim:** This _(quack)_ is bananas. B A N A N A N A. I never know when to stop when spelling bananas.

[00:29:53] **Carol:** Keep going. Keep going.

[00:29:54] **Adam:** Have any of the four of us ever implemented JWTs?

[00:29:57] **Carol:** I have, yep.

[00:29:59] **Adam:** I have. As well

[00:29:59] **Carol:** Yeah.

[00:30:00] **Tim:** have not.

[00:30:00] **Adam:** as a, as a producer, not as a consumer, I guess is kind of where I was headed, but

[00:30:05] **Ben:** I've done well. I've done both, but within the same system.

[00:30:08] **Adam:** Gotcha.

[00:30:09] **Carol:** Pro producer, not consumer.

[00:30:11] **Adam:** Okay. So, it's been years, so I'm, I'm gonna struggle to remember the details, but I guess that might help us suss out, you know, what is the use case And so I'll just try to be brief here. What we did was we had a, an application that we wanted to support like it was a custom designed application by somebody else, and they just wanted to be able to use our application as like SSO for their application.

[00:30:34] **Adam:** So they wanted to kind of bounce through our application and then receive a packet that says, okay, AlumnIQ says this is who this person is, and they would just trust us. And so that's what we did. We, we, you know, we kind of a redirect that included a. J double u t in the redirect. And yeah, that's

[00:30:52] **Ben:** and I think, I, I think that is actually a use case that does make sense because this, you have a, you have a piece of information that represents some particular user and you have to ensure that it has not been tampered with, and that it contains information that makes sense just for that user, and that you can pass it on in a way where the system that you're passing to doesn't necessarily even have access to the source of the underlying information.

[00:31:19] **Adam:** And it's not a five step nightmare like

[00:31:21] **Ben:** Yeah. Yeah.

[00:31:22] **Carol:** Yeah.

[00:31:23] **Adam:** only calls and Yeah.

[00:31:25] **Ben:** So that to me makes sense. But there are, there are people who just wanna do like a drop in replacement and, oh, I heard that jots are good. So instead of using cookies for session management, I'm gonna use jots for session management. And like, that's, that's the thing that drives me

[00:31:39] **Carol:** the

[00:31:40] **Adam:** Absolutely. Yeah. The new shiny, just because it's the new shiny. For sure.

[00:31:44] **Ben:** All right.

[00:31:44] **Adam:** Tim, you wanna pick one next?

## [00:31:46] Method Dependency

[00:31:46] **Tim:** Yeah, Note to self. Is it okay to have one public method calling another public method on the same object? Or should both those methods be using a common private method? Is it a smell? Should a public API method be aligned with a holistic consumer gesture? Love Ben.

[00:32:08] **Ben:** Yeah, this is so I am not what I, what I would think of as a traditional object oriented programmer. I am very much a procedural programmer. I love me a top-down script, and I use objects all the time, but they're very much pure objects, so to speak, in that they're really just funneling inputs into outputs or inputs into the database or database to outputs.

[00:32:34] **Ben:** Like they, they don't, they don't have a lot of state but they are co-located within objects and. oftentimes struggle with having a public method that does something and then another public method that does that thing plus a little bit more. And I, and I will create that second method so that it turns around and calls the same the it calls the previous public method, but then does a little bit of extra stuff.

[00:33:02] **Ben:** And my concern there is that I'm gonna fool myself one day. That I'll say like, oh, here's a method called fu and I search the rest of the application for things that are calling it and nothing's calling it. So I think, oh yeah, this should be safe to delete. Not realizing that another method on that same object is turning around and calling FU and.

[00:33:24] **Adam:** you have to search within the same

[00:33:26] **Ben:** Yeah. Yeah. That's, but, but it, it, but it, it, it's, it's not so much, I guess, that I'm worried that I'm gonna fall into that trap more. That is the potential for falling into that trap. An indication that there's something wrong with the way I'm wiring things together.

[00:33:40] **Adam:** First thought that I had was like, you're now creating a dependency that that function will never change. Or if it does change, like its output changes That it should also change in the one that you are adding on top of it, the

[00:33:54] **Carol:** Yeah. The second one should be, yeah.

[00:33:56] **Ben:** Right, and that's what I, in, in the note there when I talk about it being aligned with the consumer gesture, I often want to think of a method as being an atomic action that the user might take. Like I want to change the system in some way, and I'm calling this method and it has a meaningful well bounded con concept to it.

[00:34:19] **Ben:** And then my worry is that if I have another public method on the same object that turns around and calls that same thing, like now I've started to blur the lines between what I think is a single atomic action. I mean, this is very just philosophical slash academic thinking, but I dunno, this is the random stuff that goes through my head.

[00:34:39] **Tim:** Yeah, I, I picked this one because I, I kind of initially kind of waffled between the two going, oh, I need, this needs to be private. And, and I've leaned more toward going, having it choose a, a, a public method. A public method calling another public method. And, and here's my reason why. This may or may not be legitimate, but this is, this is how I feel about it.

[00:35:03] **Tim:** So let's say I have a scenario where I have, I'm dealing with a, an insurance policy. And so you have the general policy. So a policy has like expiration date, effective date, you know, the policy holder. And then you have automobiles that make up that policy. Well, I'll create a public policy method that just with limited, you know, all I have to do is give it a, a policy number and it goes retrieves, A J S O N set and says, here's the description of the policy, but then I don't wanna make people do like four or five calls, right?

[00:35:32] **Tim:** So if I want, you know, public method, get auto policy, and so that's gonna combine those two public methods, unless they just want it, you know, they had the, the certain ID and they just wanted it. And it will combine those two, and I'll call it publicly because. And I know, I understand what, what, what Adam was saying about, you know, if you're changing the output.

[00:35:53] **Tim:** But because it is public facing, I'm much less, much less likely to change the output in a, in a breaking manner because I have people consuming it without, you know, making an aversion change. And also my tests would, would tell me if, if they're changing or not. So

[00:36:09] **Tim:** I, I've, um,

[00:36:10] **Adam:** you speak of?

[00:36:13] **Carol:** I held it back. I held it back. Come on, Adam.

[00:36:16] **Tim:** it, by test, will catch it. Yeah. And so that's, that's why I've lean, lean more toward public. And also it's just the, with what I'm using, I'm using mostly Adam's, Kathy framework. I have it set up to do multi-tenant. It's just sometimes it's just easier, sometimes just the way I have it set up to just make the public call to the resource, grab it, rather than trying to dig deep inside and figuring out which tenant I'm currently on.

[00:36:43] **Tim:** And. You know, expanding a, a, a public method private method. So that's what I've leaned toward.

[00:36:49] **Ben:** It, it's interesting. So I have a couple thoughts going through my head. One is about extending objects. So I, I have read, you know, this is a matter of opinion here, but I have read that if you have a, a class or an object and then you extend that class or object, That the only super calls you should be able to make from the concrete class into the base class are for public methods on that base class.

[00:37:19] **Ben:** Like you shouldn't be able to extend an object and then turn around and call a private method on the parent object. Think the thinking being that that's an implementation detail of the base object, like just because you're extending it doesn't mean you should understand or have any understanding of the way it's been implemented internally.

[00:37:41] **Adam:** Mm.

[00:37:41] **Ben:** So in that case, you have one public method on your concrete class calling a public method on the base class, which kind of aligns with public being called by public. But then, I go back to what I think something Uncle Bob said when we were reading the the Clean Code book, which I think he was saying that if you look at a, the implementation of a particular method, that everything in that method should be at the same level of abstraction.

[00:38:09] **Ben:** I think that was from that book. And if you have one public method turning around and calling another public method on the same object, can that even by definition be correct? Because the original public method is a layer, a layer of abstraction and is now being consumed by another public method that's at a different layer of abstraction.

[00:38:32] **Ben:** It seems like it's, it's a conflict there.

[00:38:35] **Adam:** Yeah, I, I feel like that's just a, a bridge too far in terms of like trying to follow best practices, just. Just

[00:38:42] **Carol:** like I need more Redland for this show tonight.

[00:38:46] **Adam:** The, the other thing I was thinking about is like, you know, rules are fine. Rules are good in that they help us make a decision when we are struggling to figure out what we should do. But never do it the hard way because the rules tell you not to do it the easy way, right? Like, if you wanna say there's a rule that you can't call private methods when you're call like super private or whatever the, the implementation focuses is like that. There might be some valid reason to say that. But then like, well, what if you just wanna re-implement the public function and change the way that it's done and, and like, okay, we'll cause this private thing that does the data get okay and the data get's not gonna change, it's just the way that I massage it afterwards or whatever, right?

[00:39:28] **Adam:** Like,

[00:39:29] **Ben:** Right, right.

[00:39:30] **Adam:** don't, don't reinvent the wheel. So,

[00:39:32] **Tim:** and, and that's what I was running into when I, when I was using private methods, I found I was doing some boiler template, which I didn't like. I'm like, well, I already have these functions. They're public functions. They do exactly what I want. I give them minimal input, cuz I try to make it as easy as possible for the end user to just have one piece of data and get what they need.

[00:39:50] **Tim:** Why am I doing this extra work here? So I was lazy, but it worked for me.

[00:39:56] **Adam:** You know what lazy devs are sometimes the best devs.

[00:40:00] **Ben:** One of the things that I struggle with, and, and so this is a little bit tangential, but it's at the same time, I think, a similar concept, which is the idea of bulk actions and how bulk actions should be implemented. So imagine that you have a system of documents and you wanna be able to delete a single document.

[00:40:21] **Ben:** And when you delete the single document, let's say stuff happens behind the scenes, maybe an event gets omitted or something gets logged somewhere, and then you wanna be able to create a system where someone can say, Hey, delete all of my documents

[00:40:34] **Adam:** Yep, all 10,000.

[00:40:37] **Ben:** exactly. And the, the thought I think people would have is, okay, no problem.

[00:40:40] **Ben:** I already have this thing that deletes a single document, so I'll just get all of the documents. Yeah. And I'll just call it once for each of these things. But the issue there that I run into is that there's so much stuff that might be happening under the hood that you don't necessarily want to happen for a bulk operation.

[00:40:57] **Ben:** And should there be a separate bulk operation ingress to the logic and that, that may or may not share some of the stuff that the single document deletion uses, but, but is not necessarily the entirety of that. And we, we argue about that at work. We don't have a, a clear winner. As to what that should be.

[00:41:19] **Adam:** It might be case dependent, right? We, we actually just merged some code changes today that made a change to the way that we handled this, right? So we have event registration software. Like you were saying you check into an event, right? You arrive and they scan your badge and it does a single check-in for you.

[00:41:33] **Adam:** No problem. But then like after the fact, they might want to go through the list and say, okay, well I know this person was there, I know this person was there, I know this person was there. When they are scanning through at the end and they like, they, they might check off 150 people that didn't get checked in for whatever reason, but that they know we're there and they wanna bulk check them in.

[00:41:50] **Adam:** And when you check somebody in, like you were talking about, it does like 12 different things. It's not just like, set a checkbox or set a date in a, in a column. It, it's, it does that and then 20 other things. And we were, the, the individual one was using O RM to like, you know, cycle through these individual little tasks for for each individual check-in, which is not that big of a deal.

[00:42:13] **Adam:** But then when you start to do it and you're like, okay, I wanna do that for 500 people, that's, that's a big lift for that one request.

[00:42:20] **Ben:** Yeah.

[00:42:20] **Adam:** of objects to, to thrash.

[00:42:22] **Ben:** It reminds me, I think on a previous episode, I can't remember if this was Carol or Tim, but someone, one of the lessons learned was if you're gonna do some bulk operation in a database like loading data from a file, I think this was like turn off all the index checking and the foreign key checking and it, it's that same kind of thing.

[00:42:41] **Ben:** You're gonna do something that could be done at the individual level, but a bulk operation of a special context. And you might need to handle it in a special way and. We're, we're off in the, in the weeds

[00:42:51] **Adam:** think it was me, but that's okay.

[00:42:53] **Carol:** Well, that's okay. Yeah, I was gonna say pretty it was you. It was you with the files and stuff. But I will say early on in my career, I remember going into Tim's office and going, I don't understand what a deadlock is. Please explain this to me. I'm like, why does this keep happening? He's like, well, you can't call it that many times, the data's already being changed.

[00:43:11] **Carol:** I was like, oh,

[00:43:12] **Adam:** Yep. All right. Well, you think we've got one time for one more?

[00:43:16] **Carol:** yeah,

[00:43:16] **Carol:** do one more.

## [00:43:17] Nothing's Free

[00:43:17] **Adam:** I'll do one, Note to self, it's easy to just say, measure everything and make specialized services. When you don't worry about maintaining that stuff long term, but it will haunt you. Everything costs money, time, attention, nothing is free, and thinking any of it is free is making me sad.

[00:43:40] **Tim:** Sad Keanu meme,

[00:43:42] **Carol:** Oh, yes. All right. Give it to us, Ben.

[00:43:45] **Ben:** So I, I think, so the general underlying sentiment here is that there are people in this world who just believe that parts of software are free. It you and, and no, nothing is free. Nothing exists without effort over the long term. And it just, it drives me crazy because, and I think you only get to this point when you've been at a place maintaining a piece of software for long enough and you realize that vulnerabilities come out and platform issues happen and libraries no longer exist and all kinds of stuff where.

[00:44:22] **Ben:** The thing that you thought, oh, you could just build on a weekend in a hackathon and then never think about again. While suddenly AWS doesn't support the version of Node that, that you're deploying to Lambda, and now you need to update the node. But oh, suddenly the, some, the packages that you're using in that library are end of life because of security vulnerabilities and you can't use them anymore.

[00:44:43] **Ben:** And it's like nothing. There is nothing, there's no, nothing exists in a vacuum. And it, it just drives me crazy when engineers have this fire and forget mentality.

[00:44:56] **Carol:** well, not just engineers. Like I remember being asked multiple times, why is this data not in Google Analytics? And I'm like, because we never added Google Analytics to any of these sites. So you have no data. I don't know who's on there. You won't know. They're like, just add it. I'm like, it's not that simple.

[00:45:13] **Carol:** Like I actually have to go make real changes to the actual code to add it. You can't just turn it on.

[00:45:19] **Tim:** Oh, oh. And, and as Google's been telling me for the past six months, they're changing the way they're doing analytics. So you gotta cha change your code now because, because they wanna do it a different way cuz everyone caught on to their privacy snares. So.

[00:45:33] **Ben:** Yeah, exactly. So the, the more diversity that you build into your code base and the more services you build and the more variety of technologies and databases and programming languages and strategies and observability approaches and event approaches. I mean, like everything just adds rot over

[00:45:55] **Carol:** it does. Yeah.

[00:45:56] **Tim:** Yeah,

[00:45:56] **Tim:** I I heard an interesting story today on on the radio. It was public radio, and they were talking about in, in like 1960s, like, I think it was 64 or 65. A developer who, like, who was working for the government said, Hey, you know, we only used two digits to store the year. It'd be super easy. I mean, comp, there's not a whole lot of computers right now.

[00:46:17] **Tim:** It'd be super easy if we just go ahead and make that four digits, you know, it take a little extra memory space, but it's not a big deal. We, we can handle that. And the government's like, eh, You know, it's, it's 40 years from now.

[00:46:29] **Carol:** We got time,

[00:46:30] **Tim:** we before, cuz you know when y2k right? That's the whole Y2K issue.

[00:46:33] **Tim:** They only stored it in, they're, you know, he's like, we're, we're not really sure if when it kicks over in 2000, if it's gonna go like to 1900, that could really screw some things up cuz the dates are know different. And so this thing that could have been solved, right then, this little maintenance issue that they could have done and just been done with, it cost the government billions of dollars

[00:46:53] **Carol:** Oh yeah.

[00:46:54] **Tim:** in the late nineties to fix that issue.

[00:46:58] **Tim:** So, yeah, so you're right. Things, things cost you, you, you gotta, you gotta maintain the stuff. For the long term. And, and I, I've been guilty of it, ally, I picked like, oh, this tool looks cool, but let's, let's throw this tool in here. You know, never used it before, but I like to learn about it, you know, it's just my techno curiosity.

[00:47:13] **Tim:** And then like years later it's like, oh, we gotta renew licenses on this. And they have some breaking changes, so now it's gonna be a, a eight week project to get these, you know, this one small change that they made that now, you know, we took advantage of, you know, years ago and now gotta go change. It's like, oh my God, are you serious?

[00:47:29] **Carol:** And sometimes I question, is anyone even looking at this data? Like when you're talking about monitoring and like, does anyone even look at it? There was an email I used to get from Google ANA Analytics, I hate that word. I'm sorry. There was a report I built for custom data for some views on the page to see if something was being adopted or not.

[00:47:49] **Carol:** The person who asked me to request it quit, his boss said he didn't want it. I was the only one getting the email and I'm no longer there, so I don't know what's happening.

[00:48:00] **Tim:** it's, it's going, it's going to some inbox somewhere.

[00:48:04] **Ben:** Yo.

[00:48:04] **Carol:** no one's watching it, why do it? You know?

[00:48:07] **Ben:** at work we've been as, as we've talked about on the show previously, we had a very large reduction in force last year, and, and we've had some additional departures and As, as a side effect of all of that, we now have services that no one really owns. No one really understands. I haven't worked on a big part of that.

[00:48:24] **Carol:** Yeah.

[00:48:26] **Ben:** A big part of that is our, our data analytics side of the house, and we're also now involved in this large cost cutting efforts, you know, just to increase the, the runway for the company. And a, a big part of the cost cutting has been examining. The analytics, and we have these data lakes in, I think it's called Redshift or something or other.

[00:48:47] **Ben:** We have the, you know, data goes from here to here to there to, and gets materialized and chopped up and, and aggregated and all this stuff. And we're trying to figure out how to save those costs. And I've been in these meetings and I just say, can we just delete it all? Like, just, we don't know who uses any of this data.

[00:49:03] **Ben:** We don't know who generates these reports. Let's just delete all of it. And then as people start to complain like, Hey, my report doesn't work, let's ask them, do you actually need this report? Or you know, what is the least amount of work we can do to get you the least amount of data to help you get your job done?

[00:49:21] **Ben:** And then

[00:49:21] **Carol:** Oh yeah.

[00:49:22] **Ben:** rebuild from scratch.

[00:49:24] **Carol:** Yep.

[00:49:25] **Ben:** Cuz right now we're spending so much money. Yeah, it's bananas. How expensive this stuff is.

[00:49:29] **Carol:** Oh

[00:49:30] **Tim:** th th this is how I like to visualize ChatGPT and those, these large language models actually work. They just have a whole bunch of little people that don't know what they're doing, but, but they all move around really, really fast. Yeah. And it's like, it is like, just run it through a hundred year, like time cycle, but like at, you know, in a few seconds on a computer scale and it'll come up with something pretty good.

[00:49:51] **Tim:** That's kind of what we all do, let's be honest. Got this organization of a whole bunch of people and no one's really has any clear handle on everything that's going on, but, you know, it's working. It's a pretty close answer. Sometimes it's wrong. It hallucinates a little bit, but, you know, may maybe human beings, we are just a simulation.

[00:50:10] **Ben:** Oh.

[00:50:10] **Tim:** Wow. What, what's in this beer? Geez,

## [00:50:14] Patreon

[00:50:14] **Adam:** Well, I guess that's gonna do it for us tonight. So this is the part of the show where I tell you that this episode of Working Code is brought to you by pedicure Toast Spacers available on Amazon Cheap unless you want them overnight.

[00:50:24] **Adam:** And listeners like you, if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe than you should consider supporting us on Patreon or patrons, cover our recording and editing costs. And we couldn't do this every week without them.

[00:50:35] **Adam:** Special thanks to our top patrons, Monte and Giancarlo. You guys are awesome.

## [00:50:41] Thanks For Listening!

[00:50:41] **Adam:** We are about to go record our after show, except Ben, cuz he's tired and he has family over. So, say goodbye to Ben cuz

[00:50:48] **Carol:** Bye, Ben.

[00:50:50] **Adam:** But

[00:50:50] **Adam:** uh, the after show is something that our patrons get to listen to the outro rolls.

[00:50:56] **Adam:** And then we just keep talking until we feel like we've said enough and then we turn the mics off. And if that sounds interesting to you, then you can,

[00:51:04] **Tim:** I mean, you sold it so hard. I mean, I don't see, I don't see, I don't see how they could not want that.

[00:51:09] **Adam:** Then you can go to patreon.com/WorkingCodePod that's gonna do it for us this week. We'll catch you next week. And until then,

[00:51:17] **Tim:** Remember, your heart matters even if you don't know everything about the platform.
