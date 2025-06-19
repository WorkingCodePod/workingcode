---
title: "221: Life in the Trenches of Replatforming"
description: "In this week's episode, the full crew is back to talk about practical replatforming. In past episodes we've discussed replatforming in a more abstract sense, but Adam has much to share about ongoing real-world replatforming at AlumniQ."
date: 2025-06-19
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/5fa55917-1fb5-4e7c-81cf-603d8ebe2c64"></script><div class="redcirclePlayer-5fa55917-1fb5-4e7c-81cf-603d8ebe2c64"></div>

In this week's episode, the full crew is back to talk about practical replatforming. In past episodes we've discussed replatforming in a more abstract sense, but Adam has much to share about ongoing real-world replatforming at AlumniQ. When the rubber meets the road, certain realities and complexities, which may not be obvious, may affect decision-making and replatforming strategy.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/221-life-in-the-trenches-of-replatforming.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Tim:** cause what I've seen coming outta college, it's a lot of Python, some Java, maybe some .NET.

[00:00:04] **Adam:** Agreed. But I, you know, honestly, I think that anybody with those types of skills, if you have Java skills, python skills.net skills,

[00:00:11] **Tim:** nunchuck skills. Bow skills.

[00:00:15] **Ben:** That's a Napoleon dynamite reference Carol.

[00:00:18] **Tim:** eat your steak.

[00:00:18] **Adam:** eat your quesadilla.

## [00:00:19] Intro

[00:00:39] **Adam:** Okay, here we go. It is show number 221. And on today's show we're gonna talk about life in the trenches of replatforming. This is a topic we've kind of gotten a little bit into in the past, but more I think from a theoretical, hypothetical standpoint. And now it's kind of actually happening. So we're gonna dig in a little bit and, and talk about decisions and plan for decisions and stuff and things and, and also stuff.

[00:01:04] **Ben:** Stuff

[00:01:04] **Adam:** And

[00:01:05] **Tim:** More stuff.

[00:01:06] **Adam:** we got the whole crew here today. Welcome back, Carol.

[00:01:09] **Tim:** Hey, welcome back. You feeling better?

[00:01:11] **Carol:** I am, I am. The travel got me, you guys predicted it, but it got me

[00:01:15] **Adam:** yeah,

[00:01:16] **Tim:** Yeah.

[00:01:18] **Adam:** your immune system. You, you should just come with a bubble.

[00:01:21] **Carol:** that I, I actually have another theory. I think I should just start licking the cart every time I go to the grocery

[00:01:28] **Tim:** There you go. Build up that immunity.

[00:01:30] **Carol:** lick the handrail like I'm holding and then start shopping.

[00:01:33] **Adam:** Yeah. Lots safer than licking every toddler that you come by.

[00:01:36] **Tim:** Yeah.

[00:01:36] **Carol:** Parents don't like that around here. I

[00:01:39] **Tim:** Yeah. Weird. Weird. You can.

[00:01:41] **Ben:** It must be a Texas thing.

[00:01:44] **Adam:** Anyway, uh, before we get to that, let's, uh, do our triumphs and fails.

## [00:01:48] Adam's Lambda Fail

[00:01:58] **Adam:** It looks like it is my turn to go first and I am gonna start us off with a big old fat fail. Um, I had fun with Lambda earlier this week. so I'm, I'm working on a process that can be broken into chunks and each one of those chunks, definitely has the possibility of consuming several minutes of runtime.

[00:02:10] **Adam:** To the point where if I, if I didn't break it up into chunks, uh, it would very easily go past the 15 minute mark, right? And 15 minutes is the maximum for running a, a lambda on AWS. And so in order to make this work in, in a way that made sense to my brain, what I decided to do was write a Lambda function.

[00:02:27] **Adam:** And it does, it breaks it up into chunks and it does recursion, right? So process a batch of data and then recurs, right. Call, call another Lambda function, and it doesn't wait for the result. And then it just ends, right? So it, it's Lambda's calling Lambdas all the way down.and that's a sound concept.

[00:02:45] **Adam:** I've used it in other places before. Uh, and it works really well for me. What I, I made the mistake and obviously I said this is infinite recursion. Uh, I made a mistake that, uh, somehow I don't even remember what the mistake was at this point, but somehow I said it so that it was processing the same batch of data over and over.

[00:03:03] **Carol:** oh.

[00:03:03] **Adam:** Yeah. And, uh, and, and I, you know, I was like running a test in QA and I kick it off and it's like, O okay, cool. It's, it's processing batch one takes five minutes, and then I see it start the next Lambda. I'm like, wait a minute, whatcha doing? Processing, processing batch one? No, no. Then the next Lambda starts processing batch one.

[00:03:21] **Adam:** I'm like, no. so, ultimately, the only way that this thing stopped, which was extremely fortunate, eventually, it ran outta database connections. The 'cause I, there was a bug in the code. My bug in the code was, I wasn't properly closing the database connection that I was opening. And so eventually, the database was like, Nope, too many connections not gonna allow anymore.

[00:03:42] **Adam:** And so the Lambda finally failed. Yes. Thank you.

[00:03:46] **Ben:** Yo. It's funny when you're saved by a bug. I've definitely had that where I deployed something, I don't even remember exactly what the context was, but I deployed something where I was missing a filter on a query. So if it had run in production, it would've like updated an entire table.

[00:04:02] **Adam:** from production, whatever. Forget the wear.

[00:04:05] **Ben:** but I had, I was missing like a semicolon or something, something that I didn't catch in development probably.

[00:04:10] **Ben:** 'cause I was on a slightly different version of something. I don't know. I can't even remember why. And I deployed it and it broke. And when I went to fix the bug, I noticed that I was missing the filter. And I was like,

[00:04:19] **Carol:** Ooh,

[00:04:20] **Ben:** God. That was lucky.

[00:04:23] **Adam:** Yep. Somebody was looking out for you there. So,

[00:04:27] **Ben:** I, I have a question about Lambdas. I generally understand the concept of a Lambda, and I understand that you pay for CPU processing time, but can you choose kind of the beefiness of a Lambda the way you can an EC2 instance, or is it just one cookie cutter option?

[00:04:46] **Adam:** So a couple things. I, I, they, I believe the way that they refer to it for pricing is a gigabit second, or gigabyte second. So it is by time, but it is also, it's like multiplied by, percentage of a gigabyte of memory that you allocate

[00:05:02] **Ben:** Gotcha. Similar to a Parsec,

[00:05:05] **Adam:** is that a joke?

[00:05:06] **Ben:** I dunno. Isn't that with the like Han solo? Yeah. Yeah.

[00:05:10] **Adam:** Yeah.

[00:05:11] **Adam:** so, the way that you control the amount of CPU that your Lambda gets is to change the amount of ram that you assign it. So if you assign it, the minimum I think is 512, megs of Ram, then you get sort of minimum spec CPU. And if you wanted to have more CPU, you have to assign it more ram.Um, yeah.

[00:05:28] **Adam:** And I guess it just kind of scales linearly or something anyway. Uh, and so, yeah, so if you give it exactly a gig, then you, and, and your Lambda runs for exactly one second, then you are charged one gig second,

[00:05:39] **Ben:** gotcha. So there's no sense of like, this is a CPU intensive task versus a ram intensive task. It's just a lot or a little.

[00:05:47] **Adam:** Yeah, you get, you get both. What was the other part of your question?

[00:05:51] **Ben:** That was really the question

[00:05:53] **Adam:** I felt like there was a

[00:05:54] **Ben:** I had. I had, I had preface prefaced it with saying that you were charged by the by time, but I didn't know if you could choose. That's all.

[00:06:03] **Adam:** I felt like, okay. Well this is great podcasting. I, I, I felt like there were two answers I wanted to give. I gave one and then I was like, oh no, what was the second one? anyway, so that's me. What do you got going on, Ben?

[00:06:14] **Ben:** I'

## [00:06:14] Ben's Triumphs

[00:06:14] **Ben:** m gonna go with two triumphs.

[00:06:15] **Tim:** What? No, you can't do

[00:06:17] **Ben:** no, I'm more, I'm preloading with two, two are in the chamber. I have, so one, I participated in the Adobe Code Fusion 2025 Hackathon this weekend, which is much less official than it actually sounds. You basically just had to register and then you had to submit something on Monday that showcased some feature that was, uh, newly released within, uh, ACF 2025.

[00:06:42] **Ben:** And I, I built just a small little website that, CSVs comma separated value files as a new kind of their marquee feature for 2025. They,

[00:06:50] **Adam:** exciting.

[00:06:52] **Ben:** Hey, the business world runs on CSVs.

[00:06:55] **Adam:** Oh, tell me about it, buddy. I know.

[00:06:57] **Ben:** So, so I did that. Um, I won't go too much into that, but the other, triumph that I have is that, um, so I use sublime text and I don't know how true this is for other code

[00:07:08] **Tim:** So cutting edge.

[00:07:09] **Ben:** but I, you know, I like to, I like to live on the edge there, on the bleeding edge and, uh, both the tab key and the Enter Key Act to accept auto complete suggestions in sublime text by default.

[00:07:23] **Ben:** So when I get my little IntelliSense, if I hit tab, it'll accept it, or if I enter, it'll accept it. and I didn't know that that was something you could configure. And for years it has driven me bonkers because, oftentimes when I'm writing my SQL statements where I, uh, I always have my, my like. Blocks of my SQL statements on different lines.

[00:07:43] **Ben:** So like I have my select and then I have another line for my fours, and I have another line for my, wheres another line for my order buys. And, uh, so I have to get, use, enter to go from line to line. And for years I had to like hit escape to get rid of the thing that would immediately auto, auto suggest after hitting select or four.

[00:08:00] **Ben:** And I went in and I removed the enter key as a, as a hot key to accept the suggestions. Now only tab will accept things and oh my gosh, it has been a game changer for

[00:08:15] **Tim:** now an 11 x developer

[00:08:16] **Ben:** Yo, it is crazy. I'm just a blindly entering through things and not worrying about what auto suggest is saying at all. In fact, sometimes like I can enter so fast, humble brag, that the, the auto suggests, like the IntelliSense actually kind of gets in the way of the continuing of the typing, but, uh, it goes away pretty quick.

[00:08:36] **Ben:** If you were really an 11 X developer, you would've developed the habit of hitting escape as every other key.

[00:08:44] **Ben:** That's, that's what it felt like I was doing sometimes it was driving me nuts. What is, so I know a lot of you are a sublime tech and, um, visual Studio code

[00:08:53] **Tim:** visual code.

[00:08:54] **Ben:** What, uh, what, what key is the accept the IntelliSense on those editors?

[00:09:00] **Carol:** Con

[00:09:01] **Adam:** Honestly, I don't even know. I just have the

[00:09:02] **Carol:** enter. Yeah. Control enter does it? Tab does it, but I use actual visual studio. Enterprise.

[00:09:07] **Ben:** Well use the beefy version.

[00:09:09] **Carol:** Yeah.

[00:09:11] **Adam:** Honestly couldn't tell you. It's like

[00:09:13] **Adam:** tying my shoes. I it's muscle memory. Yeah. Yeah.

[00:09:16] **Ben:** All right. I'm guessing since you never have to fight against it, like I had to fight against it. It's, it's, I'm assuming it's not the enter key 'cause the enter 'cause I'm always entering to get to a new line and it always wants to

[00:09:26] **Tim:** Well, obviously, I mean, you, your, I mean, your screen size is

[00:09:29] **Ben:** Half my characters are new lines.

[00:09:31] **Tim:** it's a, it's a CVS receipt that you're typing in.

[00:09:35] **Ben:** Well, you know, as I grew up on those, uh, TI 80 twos, I got a,

[00:09:39] **Adam:** that's what it is. Ben just has this editor, like, you know, 150 pixels wide, and he uses the rest of the screen for the documentation and a podcast and a YouTube video all at the same

[00:09:49] **Ben:** here's something interesting, quick little tangent. so I'm on one monitor. I've been a one monitor person for about 20 years. I just, that's, that's all, that's all the real estate that I can

[00:09:59] **Tim:** Wow.

[00:09:59] **Ben:** And, uh, my boss at work has like a massive, it looks like three monitors put together, but it's just a single monitor.

[00:10:07] **Ben:** It's enormous. And one thing that I have noticed, and I know that this is not just a screen real estate issue, but it is a also and screen real estate issue. When he wants to do a screen share via Zoom, he's constantly having to switch which window he's sharing. 'cause I imagine if he tried to share his entire screen, it'd be this like tiny little panorama on my

[00:10:29] **Tim:** microscopic,

[00:10:30] **Ben:** Yeah. So, you know, win for having the single small monitor is that I can always share my entire screen and uh, I think it just works pretty well on everyone

[00:10:38] **Tim:** bit of a straw man argument, but, okay.

[00:10:41] **Ben:** I think you miss, spoke. It is a steelman argument

[00:10:44] **Tim:** Okay. Yeah, you stole the man and Yeah, you won. There you go.

[00:10:50] **Carol:** Alright, so that's me. I'm enjoying my tab only lifestyle. got a question for you. Are you using, um, Microsoft SQL at your new gig? Are you using something else for the database?

[00:10:59] **Ben:** I am using Microsoft Sequel and it is so disorienting.

[00:11:03] **Carol:** Aw,

[00:11:03] **Ben:** I thought. So here's here, this is like, that's actually an interesting little conversation unto itself, which is that people always talk about databases and programming languages. Like, oh, it's just syntax changes. It's, you know, you just get used to it and like you're up to speed.

[00:11:17] **Ben:** MySQL feels like it is so different than MSSQL Server, Microsoft SQL Server. It's like in all these strange little ways, like, in MySQL, you can just add a column in the middle of a table. No problem. You know, you can say like a, a modify, add this column after this other column. SQL server. You can only add columns to the end of the table.

[00:11:39] **Tim:** You gotta drop the table and rebuild

[00:11:41] **Ben:** yeah, bonkers Also, uh, you like can't delete a column if it also has a, um, a default constraint on it. So like SQL Micro, uh, MySQL, you can just say, Hey, the default value for this is zero. And like, no problem. I can delete that column, but you in my, in SQL server, you actually have to go and remove the default value before you drop the column.

[00:12:03] **Ben:** Fricking it's bonkers. Uh, and, and it's like these weird little things like. Just paper cuts and they're, and it, it doesn't feel like, oh, it's just a syntax difference. It feels like, oh, this is actually just harder to do these things in this, in

[00:12:17] **Tim:** Yeah.

[00:12:17] **Ben:** platform.

[00:12:19] **Tim:** Yeah. You gotta get used. I mean, I work in three different, uh, Postgres, our Lord and Savior, my sequel and Microsoft Sequel pretty much every day. And it's like, yeah, you just get used to it eventually.

[00:12:30] **Ben:** Oh, it's, so anyway, that's me.

[00:12:32] **Carol:** Well, I had a question about it.

[00:12:34] **Ben:** Question, Question,

[00:12:34] **Ben:** me

[00:12:35] **Carol:** Have they're okay. Okay. So Microsoft SQL Management Studio recently had an update. Have you downloaded the newest update for their management studio?

[00:12:45] **Ben:** Well, so here's, another funny little caveat there. Apparently SQL Server Management Studio is only available for Windows, and I am on Mac and I'm only one of two people on Mac at the, like the entire company. and I did some Googling and apparently something called Azure Data Studio.

[00:13:03] **Carol:** Yeah.

[00:13:04] **Ben:** Is available.

[00:13:05] **Ben:** And it's a kind of akin to the management studio, but it's all,

[00:13:09] **Carol:** I wouldn't use it. Yeah.

[00:13:11] **Ben:** Well that's good to know because it's also expensive, I

[00:13:13] **Carol:** Yeah. Um, so I use Microsoft SQL Server and I use SQL Server Management Studio for most of what I do 'cause it's faster than building my project and opening things up and Visual Studio and then getting to Data Connection. They recently had an update and it's now built on the same as Visual Studio.

[00:13:32] **Carol:** So I have the option of dark mode now.

[00:13:35] **Ben:** ah, nice.

[00:13:37] **Carol:** you know how happy I am when I can write SQL and dark mode. Mm-hmm. I'm pretty happy,

[00:13:42] **Adam:** I've been living that life for a while 'cause I've just been using, uh, not, not Microsoft sql.

[00:13:50] **Ben:** Oh, all right.

[00:13:51] **Adam:** I agree.

[00:13:52] **Ben:** I don't want a tangent on tangent. On tangent. So I'll, uh, I'll say that's me and I'm gonna

[00:13:55] **Adam:** and what have you done with Ben Nadel?

[00:13:57] **Tim:** Alright.

[00:13:57] **Ben:** it over to Carol. Carol, what do you got going on?

## [00:14:00] Carol's Triumph

[00:14:00] **Carol:** All right. I'm gonna go with the triumph too, Ben. I'm gonna be like you. you guys know there's been a lot of changes going on at work recently. We've lost a whole lot of people and the

[00:14:10] **Tim:** In the government?

[00:14:11] **Tim:** yeah,

[00:14:12] **Carol:** yeah, my team specifically lost a lot of developers. We lost, you know, our systems analysts, the people doing the DevOps stuff, and uh, we were in the middle of a big migration when everything happened.

[00:14:25] **Carol:** So that

[00:14:25] **Carol:** was fun. We're moving off VMware to HyperV. So originally we were going to the cloud. Now we've pulled back and going back to using our on-prem resources. So just moving from VMware to HyperV. I just wanna say like it is great to have a team of players that are always willing to just jump in and figure anything out.

[00:14:44] **Carol:** Like looking at logs, showing me logs, just kind of getting through everything. Learning what we didn't know, picking up where other people left off, having to request access to someone else's, like share drive, just to get documents for notes they had on certificate installations that we didn't even know about.

[00:15:03] **Carol:** It's been kind of nuts, but it's been great to just feel like the effort I'm putting in is matched by the team I have now. They're just jumping in as quickly as I am, so it's just good. And I feel like people should get gold stars and extra cookies more often.

[00:15:21] **Ben:** That is awesome. That, that's always been something that I wish that I could do better. I, I, I feel like I'm a team player, but if I'm asked to change too often or change to things that I don't have an emotional buy-in for, I kind of get a little angry. Not necessarily outwardly, you know, I don't Hulk smash clip my desk or anything, but I, I think I stew and I have worked with the people that you're talking about who are just down to clown no matter what.

[00:15:49] **Ben:** You just throw anything at them and they're like, okay, cool. I got this,

[00:15:53] **Carol:** Yeah, it's, it's kind of nuts. Like for the past several days, we've been on eight and a half, nine hour calls, just screen sharing with each other, with four of us, five of us. Yeah. Just going through and just knocking out problems like, oh, now the firewall won't let this server talk to this server. Well, none of us can change firewall.

[00:16:12] **Carol:** That has to go to big OPM, so now we gotta put in another request. So it's just trying to track it back and when we don't log things in any one place. Suddenly I'm in a database, I'm in firewall logs, I'm in Azure Logs, I'm in like the actual window service logs, you know, figuring out what's going on. So it's been, it's been nuts.

[00:16:31] **Carol:** It's been nuts, but definitely have those people that are just gung-ho and willing to do it. So I'm very grateful and it feels like a giant win the past few days to have a team that does that.

[00:16:42] **Tim:** Good deal.

[00:16:43] **Carol:** But that's, that's me. Big wins. Tim, what do you got?

## [00:16:46] Tim's Fail and Team Effort

[00:16:46] **Tim:** So mine is similar to yours, but I'm going to put the bottom crusty piece of bread on this triumph sandwich you and Ben made. so Adam had a failed. Then we had a, uh, uh, some salami of triumph and some baloney of triumph from Carol. And mine's the, the, uh, the moldy piece of fail bread on the

[00:17:06] **Adam:** remind me not to get a sandwich at Tim's house.

[00:17:08] **Tim:** right?

[00:17:09] **Tim:** Yeah, for sure. so same, same story though. I'll, I'll take the positive out of that, that, that we, I have a very good team of people that jumped on us. So Saturday we had an issue come up and all of a sudden our single sign-on server that we host ourselves just stopped working. And so all of our APIs, a bunch of our products, no one could log into anymore.

[00:17:33] **Tim:** And no one, you know, knew. I mean, like, well, we haven't posted anything like for two weeks to these. Things e either like the, the one, 'cause a lot of the SSO is like it's internal services that are trying to log on to each other, right? So the SSO was running, but, and it would get a GA token, but then whenever the service consuming it, it would say that the token wasn't valid and we couldn't figure it out.

[00:17:55] **Tim:** Why? And so it's like Saturday, Saturday morning, around 10 30, uh, I get, I get a message from a customer and I'm like, ah, crap. Okay. Uh, and the team, I'm now managing their cu, I added a bunch of new people to my team and I don't know all of them personally, and I don't have their phone. Typically I have people's phone numbers or I'm friends with 'em on Facebook or whatever.

[00:18:17] **Tim:** But the person I really needed, I, I, I had no clue. Anything about, it's like, didn't. So I eventually, I was a Facebook friend with someone who works with him, and I sent him a Facebook message and he responded rather quickly. And I'm like, Hey, do you know, do you know so-and-so's number? And he is like, yeah, yeah, here's his cell phone number.

[00:18:35] **Tim:** So he sends me his number and I'm sending him messages. And he is the kind of guy that's like, when on his personal time, it's his personal time, right? So he is just like, puts his phone away, he's not like me, I'm compulsively like looking at my phone, trying to make sure I'm staying at inbox zero and responding and everything.

[00:18:49] **Tim:** He's like, anyway, finally got ahold of him and the, the other team, team members, they all kind of jumped on, but they really needed him for this. And, uh, yeah, fast forward about five hours later, we just found out that, so there was a, a, private key certificate that we were using to sign the, SSO uh, requests and it had expired, right?

[00:19:13] **Tim:** So it was good for five years and expired that Saturday.

[00:19:18] **Ben:** Oh man.

[00:19:19] **Tim:** And so they, but it's like, it wasn't really obvious for, I mean, that, that is what my gut told me from just years of having been around stuff like this. I'm like, when did this start failing? And they're like, just a couple minutes after midnight. I'm like, something expired.

[00:19:32] **Tim:** Right? We haven't changed any code. Nothing's changed. Something has expired. It's either an SSL search somewhere or something, but something has expired here. And um, sure enough, yeah. That, that expired. And uh, I mean, we normally would've caught this, but we've had so much churn in the organization. People have left for other jobs.

[00:19:51] **Tim:** Like our head, like, DevOps guys left it completely and went to be an electrician in Virginia. He's working for like some steel company. He's like making huge amount of money, just like, you know, working as an electrician at a steel mill. but anyway. So normally he would've caught that he had a calendar, but I guess he didn't share that calendar with his team when he left, because normally you'd have a calendar and say, Hey, this is, you know, these SSL certificate, all this expires.

[00:20:19] **Tim:** And so, yeah, so we, we renewed it and everything started working, but it took, you know, like five hours of our Saturday just went to hell. And,

[00:20:26] **Adam:** Nice.

[00:20:27] **Tim:** yeah. Yeah. So that's, that's the failure. Uh, so I made sure, like, so I'm like, how when's this expire now? And they're like, well, 2030. And I'm like, okay, I just sent all of you a calendar invite for, for, for June 6th so that we re renew this long before this fails again.

[00:20:44] **Tim:** Hopefully, hopefully I'll still be around either, you know, if I'm not, hopefully I'm retired. But, we'll see June, June, June 6th, 2030. We'll make sure that it comes up. But yeah, that was, that was a fail, but had a good team to jump on it. I mean, they all, I. I totally, you know, like, Hey guys, if you, you wanna slack off a little bit this week, you, you know, got, all of you put like five, six hours in on a Saturday and I totally appreciate it.

[00:21:07] **Tim:** Like four different people. Five, actually five different people jumped on it to contribute, so

[00:21:13] **Ben:** Oh, certificate expiration stuff is so terrifying. 'cause it, when it fails like that, it just happens out of nowhere. And also, I don't know if you're generating the certificates. We had

[00:21:24] **Tim:** We just, we just generated it.

[00:21:25] **Ben:** so we had a public certificate expire accidentally one time. And when we tried to renew it, they were like, oh yeah, no problem.

[00:21:33] **Ben:** It takes usually between two and three days for the renewal to go through. And we're like, meanwhile our site is completely unavailable. They, they figured it out somehow. I think I, I forget how maybe they purchased it. I think they got an emergency SSL certificate allocation from the hosting company or something.

[00:21:49] **Ben:** Oh, uh, one thing that I remember coming up on our end, uh, and Adam, maybe you can speak to this with the,SOC compliance, I feel like there was something in the SOC compliance about how long certificates were allowed to last. You are not so compliant today, my friend.

[00:22:08] **Carol:** We

[00:22:08] **Tim:** He is wearing no

[00:22:09] **Carol:** see that.

[00:22:09] **Ben:** because I think we had

[00:22:10] **Adam:** just supposed be a joke for us. Thanks.

[00:22:13] **Ben:** because I

[00:22:13] **Tim:** He's showing a bit of ankle guys.

[00:22:15] **Ben:** we had a certificate that was set to expire for like five years or 10 years, something crazy. And I think we ended up having to do like a one year or two year max or something.

[00:22:24] **Adam:** Uh, I don't have that top of mind, but that sounds vaguely familiar. Yeah. And we also, I think as a result of our compliance stuff, I think we ended up setting up some certificate monitoring stuff. So instead of it being on some person's calendar who may or may not still be here, and the years it takes for the certificate to expire, the, there's like a, a service that monitors a bunch of different SSL certificates, and then it, um, will send an email to you like 30 days in advance to like a shared email address, like engineering at alumniQ or whatever.

[00:22:56] **Adam:** Yeah. so,

[00:22:58] **Ben:** and I think, I think the compliance for us was because it was a public facing certificate, so something that service to service internally that

[00:23:05] **Adam:** Yeah.

[00:23:05] **Ben:** if that would

[00:23:06] **Tim:** Probably doesn't fall. Yeah. Hope not because we, we ain't doing that. if I can pull a ben a tangent,

[00:23:12] **Ben:**

[00:23:12] **Tim:** because you just, you just trigger something. So there's another tangent Tuesdays. I like it.

## [00:23:19] AWS Access Keys and Security

[00:23:19] **Tim:** so we had, I, I don't know if any of our listeners, maybe you guys, do any of you use AWS for like S3 bucketing?

[00:23:26] **Ben:** Yeah, sure.

[00:23:28] **Tim:** Did you get, so we got like for every single one of our access keys, we got an email for, like two different organizations within our company, and then also my personal one saying that our access keys had suspicious activity.

[00:23:42] **Adam:** No.

[00:23:44] **Tim:** You didn't get any of that.

[00:23:46] **Carol:** probably should check that out.

[00:23:47] **Adam:** however, we rotate our access keys for everything every 90 days, and I make my developers rotate 'em every 30 days. But if it's, yeah, if it's not a personal access key for my developer team, then, you know, like the, we have keys for, uh, accounts that have access only at S3, not even, console access, whatever that we share, uh, give to our customers so they can send files to S3 for us.

[00:24:10] **Adam:** those all get rotated every 90 days, that sort of thing.

[00:24:12] **Tim:** Okay. Yeah, so we don't have that policy. Probably should, because we had some access keys that were years old, so apparently there was some sort of leak, like some sort of hack that that. A lot of older keys got and, and no one actually got into anything, but they, they were able to use our access key to try to access and to see what the permission levels were so they knew the access key, uh, or not the, the key itself, but the access ID actually.

[00:24:39] **Tim:** And so we had to go re and we had a bunch of them, so we had to go rotate all of them. Every single one of them actually, we disabled them, make sure nothing broke and then if it, we just, if something did break, we just went and reissued it and updated the code with that access key. But I couldn't find anything on the news about it.

[00:24:56] **Adam:** Yeah. No, it doesn't ring any bells for me. Honestly, the thing that I think is the best about having that posture where we're rotating keys constantly and we have some automations around it, is it gives us the ability, it, it like forces us to build the ability to rotate a key at a moment's notice, right?

[00:25:12] **Adam:** So somebody leaves the company or we find out somebody's abusing it or, or it leaks or whatever, like no problem gone rotated. I can, it's not quite a button press, but it takes me five minutes max to rotate a key and, and without disrupting service.

[00:25:26] **Tim:** Gotcha.

[00:25:27] **Carol:** For us, we use octopus deploy, and in part of our deploy process we send out certs if they're needed. So same thing. So all we do is say new cert, and then it says you don't have it. So push the new, and then we just have to provide like if someone else needs the cert as well.

[00:25:43] **Adam:** Yeah.

[00:25:43] **Carol:** It gives us notification like I think 10 days out when it's about to expire and we have like a runbook that's give it to us sooner.

[00:25:51] **Tim:** Hmm. Interesting. Yeah, and for us, honestly, it's like, it didn't really, I mean, it wasn't like a dangerous thing because the only thing we use those keys for is like, I have one customer that I, that we're uploading PDFs for on their behalf, using the access id and then we're, we use it to store, like just images to pull from the website, from the static S3 bucket.

[00:26:12] **Tim:** So it's not like it, even if they, even if they compromised it, they wouldn't have got anything of value.

[00:26:17] **Adam:** so I'm gonna tangent on your tangent here very briefly. Um,

[00:26:21] **Tim:** Everybody's been,

[00:26:22] **Adam:** I was gonna say, it's everybody's Ben Day Carol. Get your tangent ready. so, uh, another thing that I've learned in the last, like year or two of dealing with compliance stuff is if you can avoid using an access key, that's a better way to do it.

[00:26:34] **Adam:** So like, if you have, like you were talking about uploading PDFs to S3 buckets, using those access keys, if you have, if the service that is doing the uploading, right? Uh, so there's a couple ways you can either do like a pre-signed URL and it basically uploads directly from the browser to S3. You're giving it like, you know, 10 minutes worth of permission to do that sort of thing.

[00:26:53] **Adam:** Or it can like proxy through your app server, right? You upload it to your CFML server. CFML passes it on to s3. If that CFML server is running within AWS, then one of the things that you could do, uh, and you have to, like everything, every service has a role, right? It's running as a role. If it's a Lambda, it has a role, whatever.

[00:27:11] **Adam:** You can take those roles, or you can, you can build a new one if you want. and say this, anything running with this role has access to this bucket period. And then it's basically as if it had that access key as part of the request, but you don't have to rotate it and it can't leak. It's just you're giving this process permission to have that access to that bucket.

[00:27:30] **Adam:** It's super, super nice.

[00:27:32] **Tim:** cool.

[00:27:33] **Ben:** at work, we had to rotate the certificates that people were using that external companies were using to do their single sign-on into Envision and oh my goodness, getting, I don't know, we had like a hundred enterprise clients or something of that point, and getting all of them to rotate the certificates on their end so that they lined up with our end.

[00:27:55] **Ben:** It was like a, it was like a, a one year process to get them all rotated. Oh my goodness. It was insane. And, and literally by the time they were done processing the list of customers, it was basically time to rotate the certificate again.

[00:28:08] **Tim:** Mm-hmm.

[00:28:10] **Ben:** It was insane. Oh my gosh.

[00:28:13] **Tim:** That's like PCI updates. They'll, they'll like release them and then, you know, it's not a real relief. They're like, oh, we're, we're changing these, these things here. You gotta do this, this, and this by this time. And you hit that time and like, nobody's done it. Right. A very small person do it and they're like, okay, we're extending this for the next two years.

[00:28:31] **Tim:** And then they actually do it. 'cause it just takes forever.

[00:28:33] **Adam:** Okay. We're gonna have to get to our main topic for the day.

[00:28:36] **Tim:** Whoosh.

[00:28:36] **Carol:** just tangents.

[00:28:38] **Adam:** yeah. Our, our topic for the day is tangents. Let's, uh, let's keep going. no.

## [00:28:41] Life in the Trenches of Replatforming

[00:28:50] **Adam:** So, uh, life in the trenches of replatforming is, I think, how I framed it. And, you know, we've, we've covered replatforming from a sort of a hypothetical perspective before. And my company is actually doing it now. Now I say that, we have dipped the, the pinky toe of our, of the, of the, the runt of the litter's foot into the pool of replatforming.

[00:29:03] **Adam:** We are literally just getting started. But even, even just that tiny amount, we've had so many decisions to make so much like, there, there's zero inertia and we really need to get up that inertia to, to like have infrastructure that we can then use to build this application stuff. Right.so we, we thought we would kind of revisit the topic from the perspective of it's actually happening now and decisions are being made and that's kind of interesting.

[00:29:30] **Adam:** So

[00:29:31] **Carol:** Yeah. Can I ask a question?

[00:29:33] **Adam:** Sure.

[00:29:33] **Carol:** So when you say you're just like dipping your toes in, like I'm going to be going

[00:29:38] **Ben:** Uh, one toe Carol is

[00:29:40] **Carol:** Sorry. Sorry. My can be my big

[00:29:42] **Ben:** Don't oversell it.

[00:29:43] **Carol:** Yeah, so you're

[00:29:45] **Adam:** It's that weird, like you don't even, you're not even sure it qualifies as a toe, pinky toe.

[00:29:50] **Carol:** how'd you know? I never showed you that. on. So I'm gonna be in the same boat as you, hopefully sooner rather than later. And that I wanna

[00:30:00] **Adam:** That's what I said five years ago.

[00:30:01] **Carol:** Yeah, well that's what they've been saying here for a long time to you, but I'm gonna hopefully pull the trigger on it. So when you say just dipping your toes in, like what is your initial startup?

[00:30:10] **Carol:** Because for me, like I have to, first thing I have to do is take all of our packages and move 'em from like a T net framework to like SDK packages. So like I had some conversions I have to do first and some updates before I can even really start thinking about what the next step is.

[00:30:27] **Adam:** That's a really good question. I think the. The way that it worked out for us, which I, I wish I could say that this was intentional and planned, but I think that it helped, even though it was accidental, which was that I've been wanting to re-platform pretty much since the instant that I created this application on this platform.

[00:30:49] **Adam:** You know, it was, it was like a, I'd rather be over here, but this is what I know and we need to move fast. And this is day one of the company, right? and so it's just been like a regret from day one sort of thing. And so it's always been on the back of my mind that I wanted to replatform and like a couple of years into the product, I, I put up like a, so the, the, the, our legacy platform is called CFML or ColdFusion.

[00:31:10] **Adam:** and so I had a, an index card on my vision board that

[00:31:14] **Tim:** You're a vision board

[00:31:16] **Adam:** it just said C-F-M-L-G-T-F-O,

[00:31:19] **Tim:** right next to live. Laugh, love.

[00:31:20] **Adam:** yeah.so, uh, and below the sunset and, The, so knowing that that was always gonna be a goal, when things started to outgrow our monolith and we had to decide like, okay, we need to break this off. What are we gonna do with it?

[00:31:39] **Adam:** Right? Are we gonna spin up another separate cold fusion server to run this on so that it doesn't bring down the main application server or what I, I started pushing as much of that into, non CFML stuff as possible. So we have kind of a combination of either Lambda functions or fargate services and like 99.9% of our Fargate services are, JavaScript in one way or another, right there.

[00:32:01] **Adam:** Next JS apps or just vanilla JavaScript or vanilla JavaScript as like a no JS application sort of situation. And, and then there's like one or two things that are like basically off the shelf software and then we're just putting it in a Docker container and throwing it up on far fargate. And so that has helped because it has kind of relieved that back pressure of like, we have to get stuff done. We have to, you know, this is, this is a process that's already working and generating, uh, you know, leads and revenue and, and like, it's, it's part of our business. We can't just stop doing this. But it has outgrown our platform in terms of like the performance that it needs.

[00:32:38] **Adam:** And so we had to figure out something for it. And so I kind of pushed it toward, JavaScript on various things. Right. Lambda or, or Fargate. And then, for the, your question was like, how do we decide, or how do we initiate that transition?

## [00:32:54] How do you Start?

[00:32:54] **Carol:** yeah. It was more like, what was your kind of starting point to

[00:32:57] **Adam:** Yeah. Okay.

[00:32:58] **Carol:** where, like how do you start? Because starting is huge

[00:33:02] **Adam:** It is. They're so, it, it, it's, it, it seems like it should be so easy, right? You just

[00:33:06] **Carol:** is not,

[00:33:07] **Adam:** you know, NPX SV create, okay, and now I've got my application. Just go right? It's not quite that easy. so, I've spent like the last year looking for the perfect project to be like, this is the one, this is the moment where we need to like, jump in and this is our opportunity, right?

[00:33:22] **Adam:** This is, so the application or the feature that we need to build, is, it's like basically a one page app, right? we need it to be, it's gonna be very dynamic. It's gonna have a lot of hiding and showing of fields and different states and stuff. So it need, it's gonna be worth making it something dynamic, right?

[00:33:39] **Adam:** It, it would be too hairy to do it as just like an HTML page with some jQuery on it. So that therein, pulls in the need for something like a next Js, a React, uh, SvelteKit, something. And the direction I've kind of wanted to push the team in is SvelteKit, there's three of us that are like full-time on the engineering team.

[00:33:56] **Adam:** One of those two others. Obviously I'm all in on SvelteKit one other guy

[00:34:01] **Carol:** you don't. You don't

[00:34:02] **Adam:** you don't say, one of the other two guys is not as experienced as me with SvelteKit, but he's done like the tutorial stuff and he's like, oh yeah, this is, this makes total sense. I can't wait to get on this train. Let's go. And the other guy is like, he, he's the one that kind of gets saddled with a lot of the like, okay, this is gonna be,six to nine, six weeks to nine months project on the Legacy platform.

[00:34:25] **Adam:** I need you to make these little changes that are so intricate and, and, they have tendrils deep down in the code, but we need you to figure it out. So he's, he ends up getting stuck on those projects most often. And, uh, that, that means that he doesn't have, have as much time as the rest of us to experiment with newer stuff.

[00:34:43] **Adam:** So he's been the one that's kind of like. I won't say resisting, but maybe a little hesitant or, or, um, not as familiar with SvelteKit. And so he's like, well, you know, maybe, anyway, so we found this application, this, this feature we need to build. And because it is just one page, that means that the footprint that we need to create before it can go to production is very, very small.

[00:35:04] **Adam:** Right? Very small. So that was like the, that was the thing I was looking for is like, I need something that we can identify by URL because that's, our application is multi-tenant, right? Which means that all, we have a variety of different customers. Each of them has their own database, but it's the literal same code running that they're all sharing.

[00:35:24] **Adam:** And what ends up happening is the code looks at the host name, the, the, the domain name of the URL and says, okay, well you're running for customer A, so let's connect to customer a's database and process this request. and so based on that. It means that there's not, like, I can't spin up an extra subdomain to indicate that this is the, the new platform, right?

[00:35:45] **Adam:** It can't be like new dot customer dot whatever, because in a lot of cases, those host names aren't even under our control right there. We do have some customers that are like xyz dot alumni q.com. That's under our control, that's our DNS. But a lot of times the customer wants it to be like, alumni q do their school.edu and they own that DNS and they control it.

[00:36:04] **Adam:** And so asking them to create something like that for us and, and point it to our stuff, it's just, it's not really, I mean, technically we could, but it, it would, it's just not, it doesn't feel like the right solution. Uh, and so basically what that leaves as an option for discerning between Legacy Code and new thing is the rest of the URL, right?

[00:36:23] **Adam:** And so we decided we need something that's gonna be you can figure out if it's Legacy or the new thing just based on the URL. If it's slash XYZ, then go here. If it's not, then go to the legacy code. Uh, and so this application feature came up and it's a one page thing, relatively small footprint, and it's kind of the right time within the team.

[00:36:45] **Adam:** And like I said, I've been waiting for this moment for probably more than a year,

[00:36:49] **Carol:** At least a hundred episodes.

[00:36:52] **Adam:** for sure.

[00:36:54] **Ben:** Let me, let me ask a quick question because I have heard, I don't wanna say horror stories, but I have heard that something like a Next Jsis really problematic because people get excited about hosting it and then it be like, it's, it's like technically you could host it anywhere, but in reality it's very difficult to host it anywhere other than Vercel, I think is the one.

[00:37:14] **Ben:** Is SvelteKit something that you can host on your own, or do you, do you use a service to host SvelteKit?

[00:37:21] **Adam:** Well, so you can host Next JS anywhere, but I think that there are some features they got into a little bit of, uh, let's just say trouble with the community recently. And when I say recently, within the last couple of months, I. Where there's some features in the framework that were not necessarily available for self-hosting people.

[00:37:40] **Adam:** Right. They're, they're like back doors that the platform that they're, that the, that Vercel platform know about and was able to take advantage of to improve performance or, or you know, provide additional functionality.

[00:37:52] **Tim:** Secret sauce.

[00:37:53] **Adam:** Yeah. And which felt a little, antithetical to the whole open source thing, right. So they have committed to opening that up.

[00:38:03] **Adam:** and yes, you can host Next Js anywhere. And, and I just wanted to kind of clear that up. The, to answer your question, yes, you can host SvelteKit anywhere. As far as I know, there's no like backdoors, like SvelteKit or like Next JS had,

## [00:38:15] Fargate, Route53

[00:38:15] **Ben:** So are you, are you doing it inside of just a Fargate docker container then? Is that the plan or?

[00:38:21] **Adam:** is the plan. Yes. yes.

[00:38:25] **Ben:** And fargate, for anyone who's not familiar, that's just one of Amazon's elastic

[00:38:30] **Tim:** Many, many things.

[00:38:32] **Adam:** yeah. Yeah. I mean, so Fargate really kind of encompasses two things. You can either give it a Docker container or you can have it run like EC2 instances, which I think can also be Docker containers, which it's, it's a very weird, I don't understand that whole EC2 side of Fargate. The side of Fargate that I stay on the fence of is we use ECR, their elastic container repository, which is just you, you build a Docker image and you push that image up to.

[00:38:58] **Adam:** ECR, just a, just like if you were gonna push a publicly available image up to Docker hub, you're just pushing it to your private ECR instead. And then in Fargate you can configure task definitions and services and clusters, and you tell it, okay, run this task in this service and then in this cluster, and basically it just spins up your little container over here and potentially assigns it like a public IP if you want, or whatever you know it.

[00:39:23] **Adam:** It basically acts like any server instance, an EC2 or whatever, but it's a Docker container.

[00:39:28] **Tim:** pay as, pay as you go service lets you run and scale containerize applications without managing servers. Learn. How Fargate can help you build, deploy, and optimize your web apps, APIs, microservices, ai ml, and data processing

[00:39:40] **Adam:** Okay.

[00:39:40] **Ben:** Well, there

[00:39:41] **Carol:** Not sponsored.

[00:39:42] **Ben:** So, okay. Just to map out the incoming request, just so that I can understand here, and for the user, for the listeners. So, so, uh, big State dot alumni q.com

[00:39:55] **Adam:** Sure. Yeah.

[00:39:55] **Ben:** makes a request and, uh, it's going through something like a Route 53. I don't know what you guys use for

[00:40:02] **Adam:** We do, we do use Route 53,

[00:40:04] **Ben:** so there's presumably

[00:40:06] **Adam:** is DNS for

[00:40:07] **Ben:** Yeah, yeah.

[00:40:07] **Ben:** For DNS there, there's presumably gonna be some rule in Route 53 that says if the requested resource contains Oh, okay.

[00:40:15] **Adam:** Yeah. So we use Route 53, and that we, we used a lot of different layers, right? So we have Route 53 we use, and it's truck. I'm having a little difficulty going, okay, what is the order of the components in the stack there? But we use R 53. We have an a LB application load balancer where you can say like, okay, this host name goes to this ip, or this host, this URL goes to this lambda or whatever.

[00:40:36] **Adam:** You can kind of have that, and it's, it does load balancing within it. So you can say, here's, here's a group of resources and round robin between them for this host name or whatever. so that's, that's another thing. And then, uh, definitely beneath both of those, and I don't know which one of those comes first in terms of outside from the public, but.

[00:40:53] **Adam:** beneath both of those, we have a Fargate container that is, NGINX proxy, and that is where we do our

[00:40:59] **Ben:** you have an next rule that's gonna say if they're going to slash cool new feature, then actually route them to this, I'm assuming like this IP slash port number, or send them to this IP port number.

[00:41:13] **Adam:** yes, exactly. yeah. So it'll, it's, uh, that is how ours work. Um, so our fargate instances start up and they are assigned into a, I think it's a target group, is the term that they use in AWS and that target group is, by Route 53 given a host name. And then that host name is referenced by the Nginx, uh, proxy thing.

[00:41:39] **Adam:** It's a little,

[00:41:41] **Ben:** Yeah, because

[00:41:41] **Adam:** indirect, but yeah.

[00:41:43] **Ben:** I, I don't know that much about NGINX, but I do remember reading that if you wanted to have it load balance between multiple machines and you have to add and remove machines dynamically, you'd actually have to make, you'd have to like reload the NGINX rules as you're doing that.

[00:41:57] **Ben:** So if you have a, something that's more dynamic that seems like, could be like

[00:42:02] **Adam:** So we do,

[00:42:03] **Ben:** something that makes that a little bit

[00:42:04] **Adam:** yeah. I, I don't know about, so we, for us changing the config for Nginx is a pretty rare thing. but even if we did, we do bluegreen deployments of our Nginx, so we spin up a new node of the NGINX proxy, and once that is there and serving requests, then we can shut down the old one.

[00:42:23] **Adam:** And all that is automated. So it just, it, it just works, basically.

[00:42:28] **Ben:** Nice.

[00:42:29] **Adam:** Yeah. That's one of the nice things about Fargate is you could say, okay, you know, this is a, a. This is the application that you're running and it'll, when you do deployments, you say, okay, here's the new version. And you can tell it, okay, you're allowed to spin up to a maximum of 300% of our, what we consider our usual workforce.

[00:42:45] **Adam:** So if, if your usual is two containers and you say Max is 300, then at most it will ever run six containers at once or six images or whatever the term is.and it, you know, if more are requested, you know, from deploy, stacking up or something, then they just start to wait in line until some of the older ones have been shut down when the deploys finish.

[00:43:07] **Adam:** Anyway.

## [00:43:08] Routing Requests Based on URL

[00:43:08] **Adam:** so to answer Carol's question before Ben's question, yes. The URL is what we're using to indicate which application to route the request to.

[00:43:18] **Tim:** So I'm gonna ask a, like a higher level question. So besides personal preference, you, I know you had your vision board and your, your mimosas and your strawberries and cream and, and said cold fusion GTFO, um, which I don't know what that stands for.

[00:43:34] **Adam:** Get frying pan out.

[00:43:35] **Tim:** oh yeah. Obviously. W

## [00:43:38] Business Reasons for Replatforming

[00:43:38] **Tim:** hat are the business reasons for replatforming?

[00:43:41] **Adam:** So, we have over the years tried to hire CFML developers that are already at a high skill level. And I'm not saying that they don't exist, but what I am saying is the ones that are at the skill level that we want are few and far between and demand a very high salary. Um,

[00:43:57] **Tim:** Mm-hmm.

[00:43:59] **Adam:** and we are willing to train people like we had the co-op with the, the college come on, and that worked out reasonably well.

[00:44:05] **Adam:** It, it definitely helped us understand what the process of bringing on a junior developer on and, and training them up to the skill level that we need would entail, and. I think that a, in my opinion, the, uh, the pool of available CFML developers over the long term, right over the next five to 10 years is only going to continue to shrink, uh, based on what I've seen so far.

[00:44:30] **Adam:** and with that, the, the percentage of those that are going to be highly skilled and, and in our price range is going to probably shrink even faster. and then you flip the other side of the coin, you know, I dunno if you guys pay attention to the, what is it, state of JS survey every year, you know, the, one of the questions on it, or maybe a couple of the questions is like, satisfaction with your tools and what are you, like, what do you love the most?

[00:44:56] **Adam:** Or what, what, what would you choose if you could? And between the two of them SvelteKit and Svelte are just like consistently, number one, number two, kind of flip-flopping back and forth over the last several years. so, and, and I,

[00:45:10] **Tim:** Have you found it easy? Have you found it easier to hire SvelteKit developers?

[00:45:15] **Adam:** So we haven't had to hire anybody yet, but I do know that there is a pool of them available. Like I'm on several Discord servers where people are doing job hunting specifically for felt. There's mailing lists that I'm on that are, not mailing lists, but like a newsletter where they post available self jobs and stuff like that.

[00:45:32] **Tim:** 'cause, 'cause what I've seen coming outta college, it's a lot of Python, some Java, maybe some .NET.

[00:45:39] **Adam:** Agreed. But I, you know, honestly, I think that anybody with those types of skills, if you have Java skills, python skills.net skills,

[00:45:46] **Tim:** nunchuck skills. Bow skills.

[00:45:51] **Ben:** That's a Napoleon dynamite reference Carol.

[00:45:54] **Tim:** eat your steak.

[00:45:54] **Adam:** eat your quesadilla. the, See, you

[00:45:57] **Adam:** cut me all off. That's okay.

## [00:45:58] Transitioning from ColdFusion to JavaScript

[00:45:58] **Adam:** If you have those skills, if you have those fundamental, fundamental programming skills, it will not be hard for you to learn JavaScript stuff there. There's gonna be edge cases. JavaScript is in its own way, kind of a weird language.

[00:46:08] **Adam:** and, but once you have the, the fundamentals of JavaScript, which I would say anybody that's got a couple of years of experience of either Python, dot net or, or what was the other one? Oh, I don't know, whatever. Oh, Java. Uh, those are the three you listed. If you've got a, if you've got three or four years of experience in, in those, I imagine within three or four months, you could be intermediate to advanced in JavaScript.

[00:46:31] **Tim:** And that doesn't apply to cold fusion as well, not that I'm making it a case for cold

[00:46:36] **Ben:** no, no. They're, they're all the. I've heard them all described as C based languages. I don't necessarily know what that means, but,

[00:46:44] **Adam:** The, yeah.

[00:46:45] **Tim:** J Java is not C based.

[00:46:48] **Ben:** I think C more the

[00:46:49] **Adam:** Syntax, the C

[00:46:50] **Adam:** syntax, they're, you can see that like the family tree there, like how they kind of all descend from the same lineage. Syntax wise, they're, they all, you know, they're, they're function calls and semicolons and, and curly braces to denote blocks, that sort of thing. Versus like Python, which is indent as a block.

[00:47:07] **Tim:** Mm-hmm. Right.

[00:47:08] **Ben:** which

[00:47:08] **Adam:** makes Python not a, a, a descendant of C.

[00:47:12] **Tim:** Mm-hmm.

[00:47:13] **Adam:** Anyway, to answer your question, could they learn CFML? Yes. Are you going to be able to convince them that they want to, is a totally different story,

[00:47:23] **Tim:** Okay. Yeah, that's

[00:47:25] **Adam:** this is a skill that we can pay them to learn that if they ever choose to leave us, is a marketable skill.

[00:47:31] **Tim:** right. Yeah.

## [00:47:32] Financial Considerations in Replatforming

[00:47:32] **Tim:** That's, that's, I think that's the big thing that, and for us fin like financial reasons, like, so Adobe recently, they keep making licensing changes to squeeze because their, their, their user base is not growing, right? It's not growing. So they're trying to get more and more money, like any corporation does value to shareholders to try to squeeze more money. And you do that either by growing, which they're not doing, or just getting more money from your existing customers and raising prices. And so I think that's, that's the thing that would move us. I mean, we, we've tried to replatforming several years ago over to from ColdFusion to ASP net. C sharp and they just took, took, took too big of a bite.

[00:48:15] **Tim:** You have to really be very slow and methodical to do that right. And just, you know, and be patient. If you're not patient about it, you can really financially screw yourself over. And, and we did that to ourselves and we're just now recovering from that. And so we're still, the plan is, I mean, asp.net is definitely on the roadmap, definitely on the roadmap, but it's like, it's gonna be more thoughtful.

[00:48:38] **Tim:** And like you're saying, like take things that are new that, that are lower priority and just keep, you know, how do you eat an elephant one bat at a time? So just, just keep biting, keep moving. But don't try to take too big a bite. 'cause otherwise you, you choke and then you don't hit your financial targets.

[00:48:56] **Tim:** 'cause at the end of the day, it's all about a business, not about what cool, cool tech you're running.

[00:49:01] **Adam:** Yeah. You can't keep your customers happy by saying, yes, we know we haven't answered any of your tickets and we haven't built any of the features you've been requesting. But look, we've we're one 10th of the way through our roadmap of completely changing the technology and probably introducing a whole bunch of new bugs

[00:49:15] **Tim:** Yeah,

[00:49:16] **Adam:** without, without giving you anything.

[00:49:17] **Adam:** Yeah, go ahead.

[00:49:18] **Tim:** and absolutely no new features. So yeah.

## [00:49:21] Modern JavaScript Frameworks and Their Benefits

[00:49:21] **Ben:** I, I will say though, one thing that is very nice, very alluring about the idea of a SvelteKit type implementation is that these, these kind of thicker javascripty frameworks have answers for a lot of things that developers have to deal with. Like, what do I do with my Cs s? How does bundling work?

[00:49:43] **Ben:** Like, how do I ship a JS file that has a hash of the file contents in the file name and integrate that in with my layout files?

[00:49:51] **Adam:** exactly. And and more and more.

[00:49:52] **Ben:** yeah, you can do that with a cold fusion application, but you are solving that problem there. You know, no one else is solving it for you.

[00:50:00] **Adam:** And, and that's just because, unfortunately cold fusion, was born before those problems were well understood. Right. Or, or some of 'em before the problems existed or

[00:50:10] **Ben:** Well, I think it's, it's a hard problem. I mean, if you look at, um, the Ruby on Rails ecosystem, which is arguably kind of having a, a, a second act right now, that seems to be gaining popularity again, even on from, I'm not a Ruby on Rails developer, so I'm, I'm, I may say things that are incorrect here, but from everything that I've heard on the podcast, I listen to their whole world of bundling, uh, JavaScript files and their whole like asset delivery pipeline has been very janky and people have complained about it for a long time, and it's gone through like three or four different iterations and like they're only now I think people are starting to say, oh, it's actually really starting to come together.

[00:50:53] **Ben:** Keep in mind, Ruby Rails has been around for like 20 years, you know?

[00:50:57] **Adam:** And Ruby itself much longer than that.

[00:50:59] **Ben:** Right, and, and the fact that SvelteKit is JavaScript based and you know, these, these view and Angular and react, that they're all JavaScript based. They have that end-to-end understanding of how everything comes together, which is very powerful.

[00:51:11] **Ben:** I'm, you know, it's hard to argue against that

[00:51:15] **Adam:** So. We're, we've been going for a little bit less than an hour now. There's a couple things that I wanna make sure I mention.

## [00:51:21] Unexpected Challenges in Replatforming

[00:51:21] **Adam:** just because they have been unexpected challenges,

[00:51:24] **Ben:** no longer having the CF query tag.

[00:51:28] **Adam:** actually no, that has not been a

[00:51:29] **Ben:** Oh no.

[00:51:31] **Adam:** so, what, so, okay, there's, that's an interesting point as well too.

[00:51:34] **Adam:** So the, because we spent years moving stuff into microservices, Lambdas and, and Fargate stuff built on JavaScript. We have now also got some infrastructure around doing stuff like that. Re a couple, many episodes ago I talked about creating, ts modules repo for my organization. So it's like taking a module that I had built that had, it was basically like a collection of utilities, right?

[00:51:59] **Adam:** But it was just written in JavaScript and then it had, it accrued so much technical debt that I was like, I, I hate working on this thing. And so I took all the lessons learned and also converted it to TypeScript and rebuilt it as a, a. Uh, module that we can install and even the install works differently.

[00:52:15] **Adam:** and, and that, so like I'm able to pull that into this SvelteKit project, right? So like doing things, like getting a setting from our configuration settings is exactly the same way we've been doing it for years from our Lambdas and Fargate services and querying the database exactly the same way we've been doing it for years from our Lambdas and Fargate services.

[00:52:33] **Adam:** All I need to know, it's like I, I need to, I've got a function in my util library, actually. It's in the TSDB library, that it's like, get DB and you, you pass it, customer and environment, right? So I say it's, Benjamin University, in production and I get back, a connected MySQL pool, uh, with the type safe and everything.

[00:52:52] **Adam:** And I get, I get that back and then it's, it's just connected to your database and ready to go. And, uh, I don't have to worry about what is the config to do that. I just 'cause the, the module figures that out. Um, which is nice.the other stuff that I wanted to mention, that I, these were like kind of a little bit of a blind corner for me when we started this.

[00:53:12] **Adam:** Like, I was, I was very excited. I know I was kind of a little bit blinded by my own excitement. but like I mentioned, this is a multi-tenant application and it has to be able to connect to the database and you get the customer from the host name, and that's another, you know, we have a utility function that's like, okay, given this host name, what customer is it and what environment is it?

[00:53:29] **Adam:** Right? 'cause that's the host name indicates that, and that pulls from our config, which is live and could possibly have changed since this is when the application started and it, and it handles all that. and that's just built into the utilities anyway. So the two challenges that, were not immediately obvious to me when I kind of was like, okay, let's, let's give this a go.

## [00:53:48] Internationalization and Accessibility

[00:53:48] **Adam:** were internationalization. and, the, there's, there's a small bit of, Space within the SvelteKit application where you don't have access to stuff like the host name, so, a no JS or a SvelteKit, react, et cetera. None of these things have one thing from I will give credit work creditors to. CFML has this one thing that's great, the request scope, right?

[00:54:14] **Adam:** So request comes in and there are things in the request scope, you know, or actually you can put whatever you want

[00:54:20] **Carol:** Say you can put stuff in the

[00:54:21] **Adam:** Yeah. And, and it's available through the entire request. It doesn't matter how many functions deep you go, how many objects you've created, and whether you're in ORM or not.

[00:54:31] **Adam:** And, and IT request scope is available because a request is in the middle of being processed and you've got that available to you. That does not exist in anywhere else that I have, played with. It might exist in some other languages, but none of the ones that I've been in. and so that, that has presented challenges that I've had to figure out a way around and.

[00:54:50] **Adam:** In particular, I've been trying to be, it's a little bit against my nature, but I've been trying to be super diligent about avoiding being too clever, right? So we've got the, we've got a utility library that can take a customer and environment and give us a database connection. And, and, and so it would be very easy to just, okay, I've got a service layer, you know, a ts file that's like, okay, this is where my database, you know, this is my, person service, right?

[00:55:18] **Adam:** And, and you say add person. And that add person can connect to the database and do it. But in order to make that work, that that function that you're calling has to know what customer and and environment, and when I say environment production or qa, whatever, uh, to connect to, right? And I don't wanna have to, thinking about it in terms of like front end UI stuff.

[00:55:37] **Adam:** I don't have to prop drill customer and environment down through the service layer, right? If I call ad person and that needs to, before it does that like call create reservation or something, I don't want to have to then hand off. Customer and environment from a person to create reservation, which might call another function that calls another function.

[00:55:53] **Adam:** I don't wanna have to do that all the way down. And we don't have request scope available to do that. So we've had to kind of come up with a solution to that problem without being too clever. Now we're being a little clever, but, what, what, what, what I did was myself and this other developer that I said that is not quite hesitant, but is, is the least excited of the three of us.

[00:56:13] **Adam:** he and I have been the ones working on it, kind of pair programming. I've tried as much as possible to be hands off, like let him do the programming, and I'm just kind of pairing with him and, and giving advice and pointing stuff out

[00:56:23] **Ben:** Your

[00:56:23] **Ben:** five

[00:56:23] **Tim:** that working out?

[00:56:25] **Adam:** It's hard, but it's, it's moving me toward my goal, which is good for me, as satisfying.

[00:56:31] **Adam:** the, the way that we kind of handled that problem in terms of like, okay, we need to solve this database thing. I. Let's kind of come up with, we, we brainstorm for like a half hour together, and then we, uh, split up and he developed one solution. I developed another solution and it was like, let's see what it looks like, see what the code looks like, see how clever it ends up having to be in order to work, and that sort of stuff.

[00:56:53] **Adam:** And then we kind of compared and decided to go with the one I wrote.but uh, yeah, you know, it's, it's little stuff like that. And then an another one I wanted to, accessibility. So you, you mentioned that like the, the, JavaScript bundling, where do you put your css?

[00:57:07] **Adam:** All that stuff, that these are problems that are solved in modern frameworks.I think it, to my knowledge, SvelteKit is the only one that will give you, by default compiler warnings. And you can actually change a setting to make it compiler errors, like when you build your product, product to go to product to production.

[00:57:25] **Adam:** Stumbling over my words. you can make it throw errors that say, this is, you've done something here that makes it inaccessible. now obviously that doesn't catch a hundred percent of stuff, but at least it's helping you somewhat. Right.

[00:57:35] **Carol:** Inaccessible. Do you mean like 5 0 8 compliant, like screen reader accessibility or do you mean accessible from your code base? Okay.

[00:57:43] **Adam:** Yeah, accessibility, like screen readers, uh, you know, prefers reduced motion or some of it is just like, you put a click event on this diviv, uh, and be the, the accessibility guidelines, you know, it's more specific than that, but, you know, because of this, you're supposed to also have like some sort of keyboard handler as well.

[00:58:01] **Adam:** It'll give you that. I run into that one all the time. I,

[00:58:04] **Ben:** It's like, it's like, um, if you go into your Chrome dev tools and they have the lighthouse evaluations, and that's just sort of a static analysis of what's already been rendered. But I'm assuming that one of the nice things about Svelte is it's, it is the compiler. So it has, I think, a more intimate understanding of how the application's being wired together.

[00:58:25] **Adam:** Indeed.

[00:58:26] **Tim:** I think Carol had a couple questions.

[00:58:28] **Carol:** I think we could ask them later, like as you get, as you progress further along. 'cause it seems like you're not ready to ask or like answer like how you're gonna measure success or like how do you determine financially if this was a good decision.

[00:58:42] **Adam:** Those are good questions. Uh, and definitely I'm not prepared to answer. I didn't think about that stuff at all.

## [00:58:47] Planning and Executing the Migration

[00:58:47] **Adam:** The plan is to sort of, spider web out, right?

[00:58:50] **Adam:** So we start with this one screen, and then. Because it's sort of URL based and, and beyond URL based, I'm thinking of it as like URL prefix, right? The fir not a, not a set number of characters, but like if the URL starts with this, then go to the new app. Or if it starts with this, then go to the new app.

[00:59:05] **Adam:** Or if it starts with this, then go to the new app else. Go to the old app, right? And so, fortunately, our application, it, if you're familiar with framework one in CFML, um, that's the MVC framework that we're using. it's, it's also organized very heavily around the URL and I think it will lend itself well to that style of, conversion migration.

[00:59:28] **Adam:** So fingers crossed, but that's the plan is to like, okay, we finished this application, we're ready to take on the next thing. We just have to identify what is that chunk of the application and like all of its children that we're gonna do. And so hopefully we can bite that off in small enough chunks to make it possible to, continue.

[00:59:47] **Adam:** To avoid having to do like, okay, this is gonna take six months.

[00:59:50] **Carol:** That's what you don't want to happen.

[00:59:52] **Adam:** Right. Exactly. We, you know, everything, all the changes that we do, there's gonna be ones, you know, we're, we're starting from scratch in a lot of ways or on a lot of different things. Like this whole database, multi-tenant database connection thing I was talking about, like, try not to be too clever.

[01:00:07] **Adam:** there's gonna be, I'm sure, at least a handful, probably a couple handfuls, more of those types of things, problems we're gonna have to solve. And, so ignoring those, the, the, the goal is that no project that we take on should last like more than two weeks-ish, right? So if you, if you take on one of those projects that should last two weeks or less, and then also you have to solve one or two of those problems, then maybe that becomes three to four weeks.

[01:00:34] **Adam:** If it becomes more than four weeks, then I think that we've made a mistake. so, but that's the plan.

[01:00:39] **Carol:** Yeah, it seems like it's more achievable when you break it out into smaller bits like that. Because at the end you're burnout. You forget what you did to actually even spin it up to make it start, you know? I'm like, I don't even know like how to start this docker image now that I've been using it for six months.

[01:00:55] **Carol:** Like, what was that command to sell someone else how to do it?

[01:00:58] **Adam:** Yeah.

## [01:00:58] Visual Consistency and Design System

[01:01:11] **Adam:** And the other we didn't even talk about, like visually. Uh, the other kind of problem that we're solving here is our existing application is very much like Bootstrap three. What are they on now? Five, six, something like that. so it's bootstrap three. and, it's, it's looking a little dated. We're, we're trying to bring, like, get away from that and also solve some other similar problems, right?

[01:01:21] **Adam:** So like with our bootstrap stuff, we don't, we're not pulling from a component library, so we're just re-implementing forms all over the place. So there's some things that are inconsistent, right? With the shape of the form. Sometimes the label's above the field, sometimes it's to the left.

[01:01:35] **Adam:** Sometimes

[01:01:35] **Carol:** Gotta love those.

[01:01:37] **Adam:** sometimes it's nine grid columns wide. Sometimes it's eight, sometimes it's six, sometimes it's 10. You know, like, so trying to clean that up and, and build that consistent language and also move to something, probably not, it's probably just gonna be tailwind, but away from that, that bootstrap three.

[01:01:54] **Adam:** so yeah. And the challenge, the biggest challenge that I see with that is gonna be, okay, well, we obviously can't bite off and, and migrate our entire event registration module in one, two week sprint. So we're gonna have to do some sub chunk of that, right? It's just like the refund modal or something.

[01:02:13] **Adam:** Right. And, that's gonna make it look very different. You, you know, I, do you guys ever use TripIt? I think it was TripIt. Yeah. It's, it's a service where you can like forward your confirmation emails that you get from making flight reservations and hotel reservations, rental car reservations, and then it takes all the relevant details and pulls them out into useful just like a table basically of, you know, this is your confirmation number and this is the date and this is when your flight lands and all that.

[01:02:41] **Adam:** and their website for the longest time was terrible. And then they, they like started this project and it was like, okay, the, the homepage is terrible, but now this one screen is so much nicer. And it was that way for like months and months and maybe even years. And then eventually, like another screen got converted.

[01:02:58] **Adam:** And I like, I, I totally understand why you have to do it that way. And it's a little jarring for the user. And so my goal is to just try to keep those chunks that are changing small enough that we can continue to keep up the pace and be like, yeah, we're changing stuff. And then, you know, you're seeing new stuff pop in, but that's just the way it's gonna be and we're gonna slowly replace everything one, one little screen at a time.

[01:03:19] **Carol:** So it's funny about the change like we've had. So many meetings and so many calls to try to figure out, like as we implement a new design system, do we first work on a single thing, like a banner and everywhere this banner exists, it's gonna look this way through the whole system. Or do we take on a page at a time, like what's the, the least intrusive to the end user?

[01:03:45] **Carol:** And is it having this button that's slightly different from all the other buttons on the page? Or should just one page be totally different from the rest of the system? So I will tell you, we've not made a decision.

[01:03:59] **Adam:** Yeah.

[01:03:59] **Carol:** We don't know.

[01:04:00] **Ben:** an easy decision to

[01:04:01] **Carol:** not No. 'cause these are your users, you know, and you want their experience to be the best because like my users are in this system all day long doing their job.

[01:04:10] **Adam:** Yep. Absolutely. Yeah, mine too. Uh, you know, it's like within any one organization of, of my customers, uh, there's maybe somewhere between three and 30 people that use our software, but the ones that do are in it all day every day. And so, uh, you know, keeping them happy is paramount.

[01:04:29] **Adam:** Alright, well it sounds like we've kind of brought this to a natural conclusion. It's been a little over an hour, so, uh, I think we're gonna do the thing where we wrap it up.

## [01:04:36] Patreon

[01:04:36] **Adam:** so this episode, word code was brought to you by Crusty Fail Sandwiches. Sandwiches. I can't even, I've, I've spoken too much tonight.

[01:04:42] **Adam:** My, my mouth muscles are tired. crusty fail

[01:04:46] **Ben:** sounds like a tongue twister in and of itself. Mouth muscles are tired.

[01:04:51] **Adam:** and listeners like you, if you're enjoying a show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them.

[01:05:03] **Adam:** Special thanks to our top patrons, Monte and Giancarlo.

## [01:05:06] Thanks For Listening!

[01:05:06] **Adam:** And special shout out. We have a new patron this week. Felicia, welcome aboard.

[01:05:11] **Carol:** welcome,

[01:05:12] **Carol:** Felicia.

[01:05:13] **Adam:** She's

[01:05:13] **Adam:** been really active in the Discord.

[01:05:15] **Tim:** yeah,

[01:05:15] **Tim:** yeah, I think she's going,

[01:05:18] **Tim:** go ahead. No,

[01:05:19] **Carol:** Hmm.

[01:05:19] **Adam:** No, you, no,

[01:05:20] **Carol:** Oh,

[01:05:21] **Tim:** I've talked. I've talked more

[01:05:22] **Carol:** Okay. I'll go then. So I think I saw too, that she is having, or was having one of the same pain points I have, which is writing vb. Uh,

[01:05:34] **Tim:** Seems like she's in college right

[01:05:36] **Tim:** now. I. Yeah. So yeah. Welcome. She's been, yeah, a, a, a breath of fresh air in the, in the Discord channel. Not that the rest of you are sour air. It's just, you know, nice to have some, some, some fresh, some fresh perspective.

[01:05:49] **Carol:** just called you all lame. I'm kidding.

[01:05:51] **Tim:** I

[01:05:51] **Adam:** Hi. His hater meter is running a little low. You

[01:05:54] **Tim:** yeah. No, no. Yeah. I, I need to stir up some hater.

[01:05:57] **Tim:** Adam, Adam Cameron is gone, so I don't have any haters left, so, yeah.

[01:06:01] **Adam:** alright. patrons, that was the thing I was talking about. basically, uh, in an, in exchange for your patronage, what you get is early access to new episodes and, the after show and, a special patron only area of our discord. After show, if you're not acquainted, is after the outro music plays.

[01:06:19] **Adam:** We're just gonna keep talking about a couple of things. Uh, we have a list going here. Carol wants to prod Tim about inbox zero. and then, I have a, I have a jump run thing I wanna talk about a little bit. so we'll get into that. If you'd like to hear stuff like that and support us in the process, you can go to patreon.com/workingcodepod.

[01:06:37] **Adam:** We'd love to have you. And that's gonna do it for us this week. We'll catch you next week and until then,

[01:06:41] **Tim:** Hey guys, we would never replatform our love for you. Your heart matters.

[01:06:46] **Ben:** Wow.

[01:06:47] **Carol:** Oh, so cute.
