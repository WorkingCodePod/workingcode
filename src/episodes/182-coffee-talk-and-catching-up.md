---
title: "182: Coffee Talk and Catching Up"
description: "On today's show, Tim and Carol share personal updates while Adam and Ben are away. Carol discusses her challenging workday involving a difficult rebase and adjusting to a new routine after moving to Texas."
date: 2024-06-12
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/89da05ae-731a-46b6-ad7e-d4df4f227b88"></script><div class="redcirclePlayer-89da05ae-731a-46b6-ad7e-d4df4f227b88"></div>

On today's show, Tim and Carol share personal updates while Adam and Ben are away. Carol discusses her challenging workday involving a difficult rebase and adjusting to a new routine after moving to Texas.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[laws-of-software]: https://www.laws-of-software.com/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/182-coffee-talk-and-catching-up.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Carol:** It's pretty cool when he talks to me about like what computing is like capable of and what the future of computing looks like. It just doesn't feel real yet, but I think it's 'cause I'm old and I'm, you know, kind of set in my ways a little.

[00:00:13] **Tim:** should be silicon, dammit!

## [00:00:36] Intro

[00:00:36] **Carol:** All right. Welcome to Working Code. It's show number 182. And tonight we're just going to chat a bit. It's only Tim and I, the other two are taking the week off and I'm just catching back up. So we thought it'd just be a good opportunity to just kind of catch up and see what's going on with everything.

[00:00:51] **Tim:** Yeah, no big whoop. It's coffee talk. Coffee, coffee talk.

[00:00:56] **Carol:** But first, we'll kick us off with a Triumphs and Fails, and I am up first.

[00:00:59] **Tim:** Yay. Welcome back, by the way. We

[00:01:01] **Carol:** Oh, thank you. The move has been interesting, to say the least.

[00:01:06] **Tim:** I bet.

[00:01:07] **Carol:** the military life is a great life, and I highly recommend it for everyone if you want lots of challenging days ahead.

## [00:01:16] Carol's Fail

[00:01:16] **Carol:** So I'm going to start us off with a fail. today at work, I was trying to get a branch out for a PR. And I pulled in the latest changes and we've had some projects kind of get pulled that we don't use anymore.

[00:01:29] **Carol:** So there were quite a few changes that I hadn't pulled in yet. we're moving to GitHub Cloud Enterprise. I don't know if I've said that right, but we're going to GitHub Enterprise Cloud. That's the way it's G E C. And I knew some projects were moving around. So there's been some references that have changed and stuff.

[00:01:46] **Carol:** So When I did the poll, it seemed like things came in pretty easy. I rebased my branch off of our, main branch just to kind of get things going and when I did, all things went to heck and back.

[00:02:00] **Tim:** Oh no.

[00:02:01] **Carol:** Yeah. So I don't know exactly what I had done wrong, but. Every package, like, wouldn't load, none of my debug DLL was there.

[00:02:11] **Carol:** Every time I build, it just said there were build errors. It was going awful, very, very bad, to the point where I was convinced that I pulled in bad code. So I probably

[00:02:22] **Tim:** I pulled the wrong branch.

[00:02:23] **Carol:** pulled the wrong branch as possible too, right? So I spent an hour, no, no joking, an hour trying to figure out what I had done wrong. I, stashed all my changes.

[00:02:34] **Carol:** Went back a step, everything built fine, reapplied it, all of a sudden, everything's breaking. It all came back to whenever I, did the rebase, I added an imports to a project that had no idea what that was, and it just happened to be. The very first project that runs in our build. So the entire build would fail and I had 79 errors after.

[00:02:59] **Carol:** So somehow I screwed it up, but it just feels so bad when I spend an hour looking at something and I didn't think to go look at every file that had changes and see if one of the changes wasn't actually something I did. Rebasing and getting current code should be a lot simpler and less damaging.

[00:03:17] **Tim:** rebase. Honestly. I don't think I ever rebase. I probably haven't in the past five years. I haven't rebased

[00:03:23] **Carol:** Really? So I, I don't know why I'm a big fan of rebasing, only if my branch has never been made public.

[00:03:29] **Tim:** Cause you're all about that bass.

[00:03:30] **Carol:** I'm all about that bass. We're all dancing. It's great. So yeah, so it just, it was a struggle today. I had some other stuff going on, so then to feel like my projects weren't working and my laptops decided to just give me a blue screen twice a day.

[00:03:46] **Carol:** I'm just fed up with the day and ready for it to be over with.

[00:03:50] **Tim:** I hear ya. Seems like that all kind of compiles when you move. Everything's out of sorts. You're in a new place. You don't have a routine yet. It's like, we realize what creatures of habit we are and that when we get out of that, it's like, things just go badly. That's what I'm afraid of. You know, when I head for this month long Ireland trip,

[00:04:08] **Carol:** Yeah, it's

[00:04:09] **Tim:** things are going to be bad for, things are going to be bad for the first week.

[00:04:13] **Carol:** And that's what my husband had said to you. We're such creatures of habit that even though we're kind of used to moving now, it's still just the, where did someone put the coffee and we don't have any creamer and it's not just as simple as running to the grocery store.

[00:04:28] **Carol:** You have to find the nearest grocery store on a map and figure out like which ones are open. You don't know any of this stuff yet.

[00:04:35] **Tim:** Yeah, don't you guys have the PX?

[00:04:37] **Carol:** We're not living on post. We're living off

[00:04:39] **Carol:** Uh,Yep. Yeah. If we lived on post, we'd just shop at the commissary and PX for everything. It's just cheaper and there's no tax, but we're living off post. We wanted a pool.

[00:04:51] **Tim:** hear ya. You can have mine.

[00:04:53] **Carol:** Yeah. We love it. We love it. The dog loves it. Let's be real.

[00:04:56] **Tim:** The dog likes swimming in your pool?

[00:04:58] **Carol:** the dog swims every day.

[00:05:00] **Tim:** Oh wow.

[00:05:00] **Carol:** Yep. That's me. What about you, Tim? What you got?

## [00:05:04] Tim's Triumph

[00:05:04] **Tim:** Well, I'm going to, you know, I'm going to be the yin to your yang there. I've got, I got, I got to triumph. So you missed a few of them. I talk past couple of weeks about my AI presentation that I did in Nashville and, went really well. I don't know if I, yeah, you probably missed that too. So I fired our sales guy and, basically I'm taking his role and doing the sales for the end of the year.

[00:05:28] **Tim:** And, he was supposed to go speak at a, At a conference in Nashville and his topic was just basically about our product, you know, spitting out features and. And, and, and things that our product does. And I'm like, you know what, I'm going to twist it around. I'm going to talk about AI and some stuff I've been working on.

[00:05:44] **Tim:** I did that. And so my triumph is that I got a new product sold due to my AI presentation.

[00:05:51] **Carol:** No way.

[00:05:52] **Tim:** Yeah. So I got, I got a new products. Now the bad thing is I actually have to make this a real product because as of right now, it's kind of, it's kind of vaporware is kind of, you know, very, very much alpha level.

[00:06:03] **Tim:** And so now I got to build that into, into a usable product and, and, but unfortunately, the person. He's doing it. They're very much kind of early adopter and they're like, you know, if I could just save some money and not have to pay someone, you know, 15 an hour to answer phones, I can pay, you know, 25 cents a minute, it says, yeah, it'd be great.

[00:06:24] **Tim:** So I'm like, well, what do you need it to do? He goes, well, I don't know, like this, this, and this could do that. I'm like, yeah, sure. Okay. So

[00:06:32] **Carol:** Well, they seem like a great partner to start off with.

[00:06:34] **Tim:** yeah, they're, they're, they're kind of just excited about anything new and shiny. So I think they're a good one to launch this with. And, Yeah. Knowing me, I will just kind of do like the initial kind of proof of concept, see how it runs for a little bit, and then turn it over to the development team and say, all right, make this scalable.

[00:06:52] **Carol:** Yeah. Make it better.

[00:06:54] **Tim:** yeah, yeah. Since Ben isn't here, I have to like, you know, hold up his side and sing the praises of ColdFusion. The one good thing about ColdFusion, it is very good at quick prototyping stuff.

[00:07:03] **Carol:** So quick, right?

[00:07:04] **Tim:** Yeah. Fast and dirty, get it out fast and dirty. Part of that is just the language itself, but other part of it, you know, him and I have been doing this for.

[00:07:12] **Tim:** 20 something years, 25 years, right? Yeah. You don't, I don't even have to think about it to build up, build with it. But, yeah, if I really want it to be a, a sellable product that scales it, we're going to redo it in another language. So,

[00:07:26] **Carol:** Yeah, that's, it's funny you said that. I had the same thought today when I was working through another issue, just with some types and how things are derived. I was like, I really miss ColdFusion and the ability to just write code that I could read and understand. I'm like, wait, where do I put, Like, brackets, where do I put parentheses?

[00:07:45] **Carol:** Like, which one's a type? Which one's a generic? Like, I don't remember. I just enjoyed the days when I could just write English almost, and it, I could understand it just by reading it.

[00:07:55] **Tim:** yeah. It's very verbose. Yeah. And, one of our, one of our discord members brought up, I forget who it was, but they pointed out that the podcast syntax. Which I know, I know Ben listens to, he always talks about it, but they, they referenced ColdFusion, the other

[00:08:11] **Carol:** way.

[00:08:12] **Tim:** they, they basically said, I guess basically they're talking about like technologies that have died and then like, you're looking for developers to work in it and they're, I guess, I didn't listen to it, but the reference was, I guess those ColdFusion developers are making bank.

[00:08:27] **Carol:** I've said that, you know, I really have said that. I think I've said it a few times on the show that it's slowly becoming the, like Cobalt, the only a few people are really good at it. And those people are very valuable when you find them and you tend to pay a lot cause it's cheaper to pay one person than to rewrite everything and hire a whole new staff,

[00:08:46] **Tim:** Yep. I guess that's my post retirement plan. Yeah.

[00:08:51] **Carol:** for ColdFusion.

[00:08:53]

## [00:08:53] Tim's Trip to Belfast

[00:08:53] **Tim:** So not really a triumph, but, you know, next week I'm going to be in the same situation as you, as I mentioned, we'll we're flying out Belfast. So as of, you know, it's a Thursday. So next Thursday I'll be, we'll be on the plane

[00:09:06] **Carol:** Oh, wow. How long's the flight?

[00:09:09] **Tim:** I forget. It's like, I think it's like seven, eight hours.

[00:09:12] **Carol:** Okay. That's not bad.

[00:09:13] **Tim:** That's not too bad. I'm not sure you, you, you leave it. We leave it like 8 PM and you get there at like. 7am the next day, but you lose time. So there's a five hour time difference. It's all, it's all wibbly wobbly. Tommy, why me stuff? It's really hard to, but yeah, but yeah, we'll get there and then, then we'll get to Airbnb in Belfast and I'll start working from working from there and taking some time off, but I'm sure I'll be out of sorts for the first few, several few days while I try to figure out the routine.

[00:09:43] **Carol:** Yeah. The jet lag is a real thing and it sucks. Like anytime you lose more than five hours, it's just awful. And hopefully if you guys, you said what time you're gonna land there, is it am or pm?

[00:09:55] **Tim:** AM it's like, yeah. So Yeah, supposedly like sleep, it's an overnight flight, but they keep waking you up. There's too many movies to watch. So you land there and you land there, you maybe had a three hour nap and you're like wasted.

[00:10:08] **Carol:** Oh yeah. But yeah, you still gotta stay awake the whole day, so you get yourself on schedule. 'cause if you go to sleep, you are screwed. Don't do that.

[00:10:15] **Tim:** Takes, takes it. Yeah, for sure. Well, anyway, that's me. Adam is, has date night with his, with the missus.

[00:10:22] **Carol:** Well,

[00:10:22] **Tim:** for, good for him. Good for him. He's got a, got a, you know, happy, happy wife, happy life.

[00:10:31] **Carol:** Yeah. And then Ben's got family in town, right?

[00:10:34] **Tim:** His sister's both of his sisters.

[00:10:36] **Carol:** Which sounds pretty cool. That's pretty lucky.

[00:10:39] **Tim:** I can't believe we, you know, we've been doing this podcast. Almost four years now?

[00:10:44] **Carol:** Crazy. Yeah.

[00:10:45] **Tim:** Is it? Yeah, 2020 we started. And, he, you know, all the stuff I talk about being in movies and all this, he's never brought up until recently. He just casually mentioned that his sister, like his works in the makeup department and like on a ton of movies.

[00:10:59] **Carol:** What?

[00:11:00] **Carol:** Yeah. So like, uh,And that's the one that's here right now?

[00:11:05] **Tim:** Yeah, well, both of them are there. So yeah, she's there. I told, I told him to tell her hello and she says she's working on a TV show with Jude Law and Jason Bateman called Black Rabbit.

[00:11:15] **Carol:** Ooh, that's interesting.

[00:11:18] **Tim:** So yeah, I can't believe all these years. He never mentioned, Oh yeah, my sister works in movies.

[00:11:22] **Tim:** She actually works in movies like on a regular basis. This is something I just do every now and then. But, yeah. So enjoy your time with your sisters, men. Hope you have a good time

[00:11:32] **Carol:** Ditto.

[00:11:33] **Tim:** and enjoy your time with your wife, Adam.

[00:11:35] **Carol:** Yeah. Yeah.

[00:11:37] **Tim:** Say no more, say no more.

[00:11:39] **Carol:** so cheesy.

[00:11:41] **Tim:** We are cheesy. I'm a dad. I'm allowed to be cheesy.

[00:11:44] **Carol:** You're loud.

## [00:11:45] Carol's in Texas

[00:11:45] **Carol:** Well, as far as life thing goes, if you want to kind of chat about that a little bit, I'm getting settled into the new place. we're in Texas. It is hot. It is very, very hot.

[00:11:56] **Tim:** What part of Texas?

[00:11:57] **Carol:** we're in El Paso.

[00:11:58] **Tim:** Okay.

[00:11:59] **Carol:** So we are at the border. We're, our city actually touches New Mexico.

[00:12:04] **Carol:** So we touch New Mexico and Mexico. So we're at that corner of Texas. We're all the way out West Texas.

[00:12:11] **Tim:** So you're not too terribly far from where you were before.

[00:12:13] **Carol:** Nah, it's only about four and a half hour drive to our previous base. So our move here wasn't terrible as far as, you know, us getting here in our cars and driving and staying a night or two in a hotel, it wasn't bad, it just took a little while to get our stuff. Things are going well, adjusting. I didn't think I was going to have a hard time adjusting to the new schedule, but I really am. And it feels like every day I start work later and later, even though I'm starting at the same time. And it feels like I have to work longer and longer. And I don't know if it's like, because my family's here or there's stuff going on in the house or.

[00:12:48] **Carol:** I still don't know the area. I just know that my days feel very long and it feels like I'm just not adjusting to the new, new digs quite yet.

[00:12:58] **Tim:** Yeah, it's a process.

[00:13:00] **Carol:** Yeah. It takes time.

[00:13:01] **Tim:** family's here? You got family?

[00:13:03] **Carol:** yeah. Yeah. I don't think I mentioned that. I guess that should have been a triumph. Peyton, our youngest is home from college, so he had to move out. He had to move out of his dorm about two weeks before we moved to Texas. So he flew out a week while we were in Arizona. And hung out with us, then went back to Georgia and then they arrived about a week ago.

[00:13:21] **Carol:** So him and his girlfriend are here for the entire month of June. So they're here visiting, or I guess it's kind of his home, I guess, because he doesn't have a home yet. He's a college kid.

[00:13:31] **Tim:** He's homeless, poor baby.

[00:13:32] **Carol:** I know, right? And then he'll go back, spend July with his dad, and then they are moving into an apartment in August and starting back to school.

## [00:13:40] Quantum Computing

[00:13:40] **Carol:** So, about him, a cool thing. We should have him on the show one night and talk to him. He is, he's finally got all of his major stuff. Like he's known he was going to do physics forever. Like he's just known that that's where he was going to go in life. but he has decided to, concentrate on quantum computing.

[00:14:00] **Tim:** Whoa. Wow.

[00:14:02] **Carol:** Yeah. So he wants to develop the next hardware that, Generations we'll use.

[00:14:08] **Tim:** Good for him.

[00:14:08] **Carol:** Pretty cool. It's pretty cool when he talks to me about like what computing is like capable of and what the future of computing looks like. It just doesn't feel real yet, but I think it's 'cause I'm old and I'm, you know, kind of set in my ways a little.

[00:14:22] **Carol:** but yeah, for him to talk and be so excited about where he sees hardware going, it's just impressive.

[00:14:27] **Tim:** should be silicon, dammit!

[00:14:31] **Carol:** don't want to think about a computer that could very quickly break, like, all my hash. Like, any algorithm I have now isn't going to stand up to what he plans to build. I go, I don't like you anymore.

[00:14:44] **Tim:** That's definitely cool. I don't even know how you get into that field.

[00:14:47] **Carol:** Yeah. He's, he's loved physics his whole life. He's been giant, nerd when it comes to math and science, but toward the last few years of high school.

[00:14:56] **Carol:** Yeah. Yeah. He did AP and he had to petition the board of education to take AP physics two, because it wasn't even offered as curriculum at his school. So he had to self teach himself and he had to have a teacher sign off on it. And he's just, since that first AP physics class, he's loved physics and he's known that was where he was going to go.

[00:15:15] **Tim:** That's cool.

[00:15:16] **Carol:** Yeah. He's pretty, pretty smart.

[00:15:19] **Tim:** Yeah. That's awesome.

[00:15:20] **Carol:** Yeah.

## [00:15:21] Young 'uns

[00:15:21] **Tim:** So, maybe some of our listeners, I, I'm getting a feel for the demographics of our listeners. They're probably skew. age wise, little more mature in their, in their, in their career progression. We're not, we're not getting the young, like out of college, like the cutting edge kind of kid.

[00:15:38] **Tim:** I had a call with one of the AI companies that I've been using to build on, bland AI. And I had a call, Their website is basically that they had to talk about some features, like, you know, if you're interested, talk to our, talk to our sales team about, enterprise support. I'm like, all right, let me find out what enterprise, what, what is that?

[00:15:58] **Tim:** What does it mean? Cause they don't really spell it out. They're like, yeah, just talk to it. So several weeks ago, I set up a call and the guy gets on, it's, a Google meet and. swear he was a fetus. And, and I'm trying not to be that guy, but I'm just looking at him going, wow, you're working at like a really, really big, like cutting edge AI company right now, and you, you don't

[00:16:29] **Carol:** shave yet?

[00:16:30] **Tim:** I know, right? I don't think he did. He had like big curly hair and he had a little wispy patch on his chin, but he probably didn't shave because it looked like really kind of smooth, right? Like the kind of baby I was like, and I'm trying not to be, you know, I was very respectful, but, at the same time I'm thinking, oh my God, is this what people thought of like 25 something years ago when they talked to me?

[00:16:52] **Tim:** Of course, back then we didn't really have video conferencing too

[00:16:54] **Carol:** a little different, right? Your

[00:16:55] **Tim:** But when we met,

[00:16:56] **Carol:** to tell it

[00:16:57] **Tim:** yeah, but when we met in person, people are like, Oh, who's this kid?

[00:17:00] **Carol:** Mm hmm.

[00:17:01] **Tim:** And now it's like, I'm not a kid anymore. Now I'm the one going, Oh, he looks like a baby. How cute.

[00:17:07] **Carol:** Oh yeah. We've seen that. Steve tells me often that I'm definitely gonna be the get off my lawn kind of person. Way before he is, cause he doesn't typically follow the, this is how we've always done it and this is how we should keep doing it and this is, you know, the way that works, I tend to go, why do you want to change it?

[00:17:26] **Carol:** Like everything's working well. Like don't interrupt the flow. Just let it keep happening. I understand you have new ways, like just let it keep going. And he's not like that. So when we talk to Peyton and he's all like smart and innovative and you know, all of 19, I go, uh,

[00:17:44] **Tim:** But now I think I understand my dad a bit better. So my dad growing up. You know, I would talk about stuff and get excited about stuff. And he would just kind of, I could tell he was just humoring me. And, and then you just, well, he's like, you're just so smart. You that's what he, and now like Max does that to me, Max is like, he'll get really excited about something.

[00:18:04] **Tim:** And I have this gut reaction to like, sometimes, cause a lot of times he's making a big assumption

[00:18:10] **Carol:** Mm hmm.

[00:18:11] **Tim:** it's slightly wrong, or maybe there's just a perspective he hasn't really thought about it. I'm like, nah. Don't yuck his yum. Just, just, yeah, pat him on the head and go, man, you're so smart. You're really, really smart.

[00:18:21] **Tim:** And I'm like, okay, dad, I get you. I get, I see what you were doing. I see what you were doing there. Don't, don't yuck his yum. So,

[00:18:28] **Carol:** I like that saying. Yeah, we gotta let them learn, right? Sometimes they have to learn by making a few wrong assumptions to understand, you

[00:18:36] **Tim:** And I don't want, I don't want my, middle aged bitterness to rub off on them. So, so yeah,

[00:18:43] **Carol:** Well, this isn't a super long show, guys. We're just kinda chatting a bit. Just wanted to catch up.

[00:18:49] **Tim:** I want to get Carol back on here cause we missed you.

[00:18:51] **Carol:** Yeah, I'm glad I was available this week. Should be around for the most of the time you're gone, so I'll cover for ya.

[00:18:58] **Tim:** Yeah. And I actually, I might be able to, I mean, I don't know if I'll be able to take my good microphone. We're flying, buddy passes, to Ireland. So we can't take like a whole lot of stuff with us. We only like the carry on and the anything that fits under the chair, but I might be able to hop on a, a show or two and, For, because it's like five hours ahead.

[00:19:15] **Tim:** So when you guys were, we're, we're recording normally around 637 Eastern Standard Time, it'll be later in the evening. I'll be well lubricated with the Guinness and

[00:19:26] **Carol:** We would love to have you on then. Come back.

[00:19:29] **Tim:** yeah, we'll see. Otherwise, otherwise this might be the last one for like four or five weeks. So.

[00:19:34] **Carol:** yeah. Well, if we don't get to hear from you, I hope you have a great trip.

[00:19:38] **Tim:** Oh, I'm sure I will. Sure. I will just, just worried about kind of working in a different time zone. Cause I'm definitely not taking 30 days off completely.

[00:19:46] **Carol:** No.

[00:19:47] **Tim:** I just not only, well, I could, I do have enough time to do that, but I'm pretty sure that I'd get fired afterward because everything, everything broke.

[00:19:56] **Tim:** At least maybe, well, maybe it will. I don't know. I mean, it's my ego saying that it would break. Maybe I'm going to be fine. We'll see. I'll let you guys know. Maybe I'm, maybe I'm not as poor. Well, to be fair, since I'm doing the sales calls, I actually do have to take those sales calls and I have no control over when they're scheduled, so it's like,

[00:20:13] **Carol:** yeah. So you're gonna have to work some.

[00:20:15] **Tim:** yeah, I'm gonna have to work definitely for the sales stuff.

[00:20:17] **Tim:** But as far as coding, I can, I can probably put that on pause. So talk us out, Carol.

## [00:20:23] Patreon

[00:20:23] **Carol:** All right, guys. Well, thanks for listening to us just chat for a minute. We truly appreciate it. This episode of Working Code was brought to you by 30 Days of Vacation and Moving Again, and of course, listeners like you. If you're enjoying the show and you want to make sure we can keep putting more of whatever this is out into the universe, you should consider supporting us on Patreon.

[00:20:45] **Carol:** Our Patreon Covers our recording, editing, and transcription costs. And we couldn't do it every week without them. Special thanks to our top Patreons, Monte and Giancarlo.

## [00:20:56] Thanks For Listening!

[00:20:56] **Carol:** I don't think we're gonna do an after show today, guys. It's just us. We'll catch up next week, I'm sure. Adam and Ben will be on, and I'll be around too. So your homework this week is tell a friend or leave a review on workingcode.dev/review. We'd love to hear what you think about us. Maybe don't judge us too harshly based off this episode. So that's it for this week.

[00:21:19] **Carol:** We'll catch you next time. And until then,

[00:21:22] **Tim:** You know what? I'm never taking a vacation from this guys, but your heart matters.

[00:21:25] **Carol:** aw, we love you, Tim.

[00:21:28] **Tim:** Love you too.
