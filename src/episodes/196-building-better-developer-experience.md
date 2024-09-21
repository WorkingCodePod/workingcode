---
title: "196: Building Better, Developer Experience"
description: "In this week's episode, Adam, Carol and Tim discuss Developer Experience (DX) and its importance in creating a comfortable and efficient workflow for developers."
date: 2024-09-18
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/196-building-better-developer-experience/id1544142288?i=1000669920825"></iframe>

In this week's episode, Adam, Carol and Tim discuss Developer Experience (DX) and its importance in creating a comfortable and efficient workflow for developers. The hosts highlight various elements that impact DX, such as the ergonomics of Integrated Development Environments (IDEs), debuggers, and browser tools.

They emphasize the need for faster build and deployment times to minimize context switching and improve productivity. Strategies for managing development, QA, and production environments, including the use of GitHub Actions, source-controlled database schemas, and automated deployments, are also explored.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/196-building-better-developer-experience.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** So, you know, I rip through, I create my pull request. I could do that really quick from the command line with the gh tool. it takes a minute for somebody to approve it.

[00:00:08] **Adam:** and it takes friggin eight minutes for the test to run, which is annoying, right? And that's kind of, so because of

[00:00:15] **Tim:** Another good reason you should never test.

[00:00:18] **Adam:** Where's

[00:00:18] **Carol:** Where's, where were

[00:00:19] **Tim:** I'm channel. I'm channeling Ben. I'm channeling Ben.

## [00:00:41] Intro

[00:00:41] **Adam:** Okay, here we go. It is show number 196, and on today's show, we're gonna talk about DX. Gotta get that DX, developer experience for the uninitiated. If you know, you know. anyway, but first, as usual, we'll start with our triumphs and fails. Ben is out sick tonight. We wish him well. I guess he just pe he peepled so hard two weeks ago that it's now coming back to hit him now.

[00:01:01] **Adam:** Heh

[00:01:01] **Carol:** yeah.

[00:01:02] **Tim:** It better been.

[00:01:03] **Carol:** Yeah. Feel better bud.

## [00:01:04] Adam's Triumph/Fail

[00:01:04] **Adam:** looks like it is my turn to go first, so I'm gonna kick us off with a try fail. Try fail. Normally I would say fail yumph, but I'm going to start with a triumph and then circle around to a failure. so I figured I had to turn it on instead. So, the triumph portion is that I deleted a buttload of repetitive configuration code.

[00:01:21] **Adam:** Like,

[00:01:22] **Tim:** much, how much would you say a buttload is?

[00:01:25] **Adam:** so this was across two pull requests. The first one deleted 2, 308 lines.

[00:01:31] **Tim:** Mm

[00:01:32] **Adam:** And the second one deleted 2, 872 lines. So I guess a buttload is approximately like in the ballpark of 5, 000 lines of code.

[00:01:40] **Tim:** That's a dump truck. That's a dump truck right there.

[00:01:43] **Adam:** Yeah. like those PRs can twerk,

[00:01:46] **Carol:** Mm-Hmm? . . Well, they could before you got rid of all their

[00:01:50] **Tim:** Yeah. Yeah, that's right.

[00:01:51] **Adam:** so, I mean, I say configuration code, basically, you know, we were doing all this work to become multi tenant. And part of that is like kind of centralizing our configuration and having a single like configuration server that can answer API requests for configuration information that's customer specific or in some cases it's shared across customers, whatever, right?

[00:02:14] **Adam:** Configuration information. And early on in the product's life, we were kind of naive about things like S3 buckets, right? So we were just like, Oh yeah, okay, we need a new S3 bucket for this. Let's go create one. And right, and so like, not only would we go create a new S3 bucket every time we needed, like, something to do with S3, but then we would have to add configuration about how to connect to that S3 bucket, right?

[00:02:35] **Adam:** Because it's got, It's got a bucket name and it's got a, a key and secret to be able to connect to it. And you know, you need the whole path and sometimes you need like URL and not the, the path to like the S3 colon slash slash path. So needless to say for each individual S3 bucket, there's a lot of potential configuration, especially when you're just kind of like, figuring it out as you go, right?

[00:02:56] **Adam:** You don't have a real consistent plan. and so 10 plus years later, We have standardized and, and aggregated things, right? So we, originally we were like creating six, eight, 10 buckets per customer,

[00:03:11] **Carol:** just not, it's not a long term viable strategy because as it turns out, there actually is a limit on the number of buckets you can create in a single AWS account.

[00:03:19] **Adam:** So we needed, we knew we could kind of start to see the walls closing in there. And it was time to clean that up. So a few years back, we made some changes to, consolidate buckets, right? So like each customer just has their, their private bucket. And then we have one shared public bucket. That's like for things that you're, for images that you're going to send out in an email and you need to be able to embed that image, we've just got like static.

[00:03:41] **Adam:** alumniq. com, that's our, our public bucket, And, so we hit, we did all that, consolidation, but we still had the, the legacy config, right? So you still had like 30 config settings per customer for all the different possibilities. Just a lot of repetition between them now. Right. And, and in theory, you could like set, you could squish that down to like, I think I got it down to five configuration settings per customer, which is just like a username and password for the private bucket, a username and password for the, the static bucket specific to that customer, which just grants them like access to their folder within the bucket.

[00:04:12] **Adam:** And then the name of their private bucket. Everything else can be generated, or figured out based on convention. And so I did all of that. and that's, that was the second pull request, right? that was the 2, 800 lines down. and I, so it was minus 2872 plus 295, because you have to put in some replacement lines and stuff.

[00:04:34] **Adam:** Anyway, so that was the Triumph portion, right? I did all that and, and I made some associated changes in the application code to generate the things that were just pulling redundant config before. Fantastic. however, I had such a good experience with that first pull request, which was just like, my process for this was just read the config file top to bottom, Go, okay, that's done.

[00:04:55] **Adam:** We don't need to have that in every customer. Let's move that over to a global or we don't even use this setting anymore. Let me just delete it. Right. Things like that. find all of those that I could. And when I got to a point where it's like, okay, this is, this is enough. I, this is probably too much.

[00:05:09] **Adam:** Let me stop here. Create a pull request. That was the first one. And, you know, it went fine. We did a little bit, kind of, at one point we were like, okay, well, let's just, this looks good enough, let's just throw it up in production, it's like early in the morning, if something happens, I'll fix it, right, it's not like it's 8pm on Friday night where I'm getting ready to like, go to bed and it's gonna be the weekend, it's, I'm here, I'm ready to work, so if

[00:05:31] **Tim:** Move fast and break things.

[00:05:32] **Adam:** Exactly, right? Like I'm here to be agile. Let's, let's be agile. And this is kind of going to lead into today's topic. and so,we had such a positive experience with that first one. Like I just merged them and deployed them and they went up and everything's fine. No big deal. So then I, I

[00:05:48] **Tim:** you went from Megan Thee Stallion down to, you know, Miley Cyrus.

[00:05:53] **Adam:** I totally understood those references and I'm not faking at all right now. Um, we had such a positive experience with that one, I went and I did it again, right? And this second one is where it's like 95 percent of what I changed with just those S3 settings. and I did the same sort of approach, like try to consolidate, clean up, make code changes, and these are in separate repositories, so I've got separate pull requests that have to be merged at the same time and deployed at the same time to keep them in sync, right?

[00:06:20] **Adam:** And, I brought down production for 37 minutes. Ha ha ha!

[00:06:24] **Tim:** So I guess it's the fail part of the try fail.

[00:06:26] **Adam:** Yeah, yeah, yeah. Um,yeah, so, basically, I'm trying to think, how did this work out? So, One of our common patterns is like, we'll make a pull request to get some code review done. And then in order to share it with our teammates for, so they can like poke at it themselves, for code review purposes.

[00:06:47] **Adam:** Right. In order to like, in addition to looking at the code, it's often nice to be able to go like poke the code, poke the app and say, okay, this, I understand why you did this or, you know, whatever, put, put a face to the, to the code as it were. and. So I made my pull request and I merged it into our QA branch, which auto deploys it up to our QA environment.

[00:07:07] **Adam:** I did that for both the config change and the app change. and then I later realized that the QA code change didn't actually deploy just the QA config change because the CI, the continuous integration scripts for. Our application code, one of the things that they do is they download the latest production configuration container from our container repository, the Docker container, brings it down to the local environment during CI and it starts that container so that there's a config service that the application server can hit to get configuration for the purposes of running tests.

[00:07:52] **Adam:** right, because the application has to be able to run in order to run tests. So it pulls down the config container and it runs it, and, and it tries to start up, and the application is, like, crashing, because, did you, I don't know if I already, I already said it, I don't know if you picked up on it, I said it, it grabs the production image.

[00:08:08] **Adam:** Right? And so I've got the production config, and I'm trying to make the QA app code work with my changes. And so the config and the code don't match up, and the CI fails, and the application, the QA application doesn't deploy. Which is in itself not a huge problem, right? I mean, in some manner of speaking, you might say that that's a good thing, right?

[00:08:28] **Adam:** Something failed, and so the app code didn't deploy, right? It kind of caught itself. however, Now we've got QA config deployed, and it's missing a whole bunch of settings that I removed that the QA app server still thinks are there, the one that's actually running. And so we start getting tickets like, hey, the QA server is not working, this and this are broken, whatever.

[00:08:48] **Carol:** And your QA is just your test environment, right?

[00:08:51] **Adam:** Well, so it is, its primary purpose is to be sort of a training and testing environment for our customers to, learn in, to make mistakes in, so that they can then go on and do the right things in their production environment. We also use it for QA purposes, right? We just, it doesn't make a ton of sense for us to have a dedicated QA environment.

[00:09:15] **Adam:** I mean, I guess it does, it kind of does make sense for reasons like this to have a dedicated, like, we are only going to push our stuff to this first for testing purposes. And then we might release it to their QA systems. I mean, it really, that's the, that's the thing is like, we don't have separate like QA and UAT.

[00:09:32] **Adam:** Right? But we are kind of doing both purposes on the same server.

[00:09:36] **Carol:** Okay. So they're joined. Yeah. So the first, the first run of this, you had issues and there were problems in QA, right? Something didn't go right. Okay.

[00:09:46] **Adam:** Yeah.

[00:09:46] **Carol:** going. Where were you?

[00:09:47] **Adam:** QA was down. I got a ticket for that. I'm like, okay, cool. You know, it's QA, so it's not on fire. No problem. I'll get that fixed. And so I'm digging into this issue and I'm like, Oh man, I realized the whole container thing is grabbing the production container. So, I'm looking at something like, have kind of two paths in front of me.

[00:10:05] **Adam:** I can either YOLO, just like, let's push it all to production, I'm here, and I'll deal with whatever fallout happens to come, which is obviously what we picked

[00:10:16] **Tim:** What would Ben do?

[00:10:18] **Adam:** and was maybe perhaps not the best choice given the benefit of hindsight. However, the second option, which would have been smarter, would have been to roll back the config change and split that PR up into first additions, no, no config remove, removals.

[00:10:36] **Adam:** All the new settings that I wanted to add, I would add them, deploy that, and then deploy my code changes that look for the new config,

[00:10:44] **Carol:** Yeah. Then go backwards

[00:10:46] **Adam:** and then go back and, and like a third PR to remove the config I wanted to remove. And

[00:10:51] **Tim:** Ain't nobody got time for that.

[00:10:53] **Adam:** Yeah, it was, it would, I was looking at like at least an hour, of trying to backtrack and figure out how to split stuff up that was already committed.

[00:11:00] **Adam:** And it's just, it was going to be a pain. So I was like, you know what? I'm here. Let's just yellow it up and deal with, you know, come what may. And what came was 37 minutes of downtime.I mean, so it was like 12 minutes of deploy and wait for issues to pop up. And when issues started to come in, okay, well, that didn't go as planned.

[00:11:23] **Adam:** Let's, you know, let me figure out what's going on and figure it out. So then it takes, you know, 5 10 minutes to get the code fixed. To figure out what's going on and then another 10 plus minutes to deploy again, which is annoying. And that's kind of what's in small part inspiring today's episode. so, yeah, I mean,

[00:11:44] **Carol:** I will say 37 minutes down isn't as bad as it could be.

[00:11:49] **Adam:** correct. Yeah, I mean, so the things that people noticed were broken were like event registration, and,

[00:11:57] **Carol:** Did you have any big events going on right now to where there was a huge hit? Yeah, you

[00:12:01] **Adam:** I mean, we've got enough customers now that we should just kind of assume that there's like always something going on at every moment of the day. We don't, we aren't quite that spread across the globe, but like across America, we have pretty much customers in every time zone and, and, America and Canada.

[00:12:15] **Adam:** So, it's, it's kind of, and then, you know, the, these are universities, they do have like alumni clubs. There's like, you know, the Hong Kong alumni club or whatever for people that have moved over there. So it's not, Unheard of for there to be events 24 hours a day.

[00:12:29] **Carol:** Oh, wow. Well, 37 minutes still isn't bad.

[00:12:33] **Adam:** It is not, I'll take it. you know, and, and, you know, fortunately we have the tooling in place. We were able to like post an announcement really quick in admin and people could get to admin. We're able to post an announcement that says like, Oh, we're experiencing a connection issue with our S3 buckets.

[00:12:46] **Adam:** You know, we're working on it and we like, there's multiple updates in there. And I can, that's how I know it was 37 minutes. Cause I could count from the. The time that that first announcement was posted to the time that it was completed. So,

[00:12:58] **Carol:** So it didn't say, oh, Adam screwed it all up. It just said we're having connectivity issues.

[00:13:03] **Adam:** Yeah, you don't really,

[00:13:04] **Tim:** Blame Amazon. Blame Amazon.

[00:13:05] **Adam:** yeah, you don't really, like, post an announcement that says, eh, we YOLO'd some code up and it didn't work out.

[00:13:10] **Adam:** So,

[00:13:12] **Carol:** Not usually. Yeah. Yeah. Yeah.

[00:13:15] **Adam:** I guess the, the lesson here is live and learn. Although, as we will come back and discuss, I think, faster deploys would have been Would have resulted in less downtime.

[00:13:24] **Carol:** Yeah. Agree. And I will talk about that more. I did last episode. I've got, I've got more feelings this one

[00:13:30] **Adam:** Okay, awesome. I can't wait to get into that. So, so that's it for me as I've now eaten almost 14 minutes of our, of our show already.

[00:13:38] **Tim:** We're halfway there.

[00:13:39] **Adam:** yeah, Carol, what do you got going on?

## [00:13:41] Carol's Triumph

[00:13:41] **Carol:** Well, I'm going to make mine short, you know, to compensate for your eating up all of the time. So, I'm going to go with a triumph. And my triumph is that the weather where I live is finally getting to where I can live outside again. And my dog can now go for walks without her feet burning to the asphalt.

[00:14:01] **Carol:** So I've been walking her every night after work and it's just been a nice little break because things at work are pretty stressful right now. Now we've got a lot of moving parts happening kind of all at the same time between big features releasing for my team to You know, our two different migrations we have going on.

[00:14:20] **Carol:** So it's, it's pretty hectic. And then on top of that, I'm trying to like step into this new role and cover my team for the, the role I have now. So it's been really, really nice to get outside and walk my dog half a mile around the block every afternoon after work, and I'm loving fall here. So that's a big win for me.

[00:14:41] **Adam:** Yeah, those dog walks are so good for your mental health.

[00:14:44] **Carol:** They are, I agree.

[00:14:46] **Adam:** we do them twice a day and they're, they're amazing. I, I can't imagine what my days would be like without my dog walks. Do you, so I, I don't want to, I'm, I'm definitely not trying to like blame the victim here, but have you guys ever thought of like, getting those little like dog boots

[00:14:59] **Carol:** Yeah, yeah, we have them and she uses them when we're traveling and like, she has to be on the asphalt, but she hates them. They're not fun for her to wear. So even though like, we'll wear them to the house, she's still just trying to shake them off. And she just wants to sit down everywhere we go. So then she ends up burning other parts of her body instead of her paws, you know?

[00:15:18] **Carol:** And then that turns into an issue. So. We have a big enough yard that she gets to play outside, like, in the afternoon when it does cool off, but I'm just glad she can walk now and not die.

[00:15:29] **Adam:** They're not dying. That's important.

[00:15:31] **Carol:** It's good, it's good. But yeah, so, that's me. What about you, Tim?

## [00:15:35] Tim's Triumph/Fail

[00:15:35] **Tim:** So I'm going to go with the triumph. Then I'm going to follow up with the failure. Yeah.

[00:15:40] **Carol:** heh heh heh

[00:15:41] **Tim:** That was a, that was a journey right there. Um,so the triumph is I've been working on voice recognition for a call in line for Spanish, and I was kind of, it's the first time I've done it normally we don't I try to stay away from voice recognition cause it just, it can be kind of finicky, but there was no way around it.

[00:16:00] **Tim:** And I got the English working fine. That was no problem. You know, I, I conquered that a while back and I talked about that before, but this is like the first we did in Spanish. Problem with it is, is my Spanish accent, I guess, is not good enough for the voice recognition software because I

[00:16:15] **Adam:** Yo, Kiero Taco

[00:16:17] **Tim:** yeah, exactly.

[00:16:18] **Tim:** Uno, dos, doble ve, ve, and just like, it didn't recognize a single word I said. So fortunately the customer I was working on this for, I'm like, do you have anyone there who speaks Spanish? They're like, yeah, do you have them test this for me? So I built a Spanish grammar file. It's just a simple little XML file that basically tells, tells the speech recognition engine what things to expect.

[00:16:40] **Tim:** It's all letters and numbers, but, I was kind of concerned. There was a little, I saw a little bug in it, fixed a little bug. And, the tester tested it out in Spanish and it worked. So I was kind of super pleased with that. Got it right on the first try. So I felt very lucky. No, I felt very lucky, very lucky indeed. In fact, in fact, so lucky I'm probably pretty sure once it goes to production, I'm going to get a lot of complaints from the Spanish, from the Spanish speakers.but anyway, so that's my triumph as far as coding goes. And then my fail is, so we recently, or Adam recently created in our discord, a casual gaming channel.

[00:17:14] **Tim:** For like, you know, like the New York times connections and wordle and the waffle game. And, what's the other ones like,

[00:17:20] **Adam:** Australians.

[00:17:21] **Tim:** strands and, yeah. So I started like paying attention to that. And so I, you know, got the New York times app, subscribed to it. Now y'all got me hooked. I'm like absolutely addicted to this.

[00:17:32] **Tim:** So thank you guys. Appreciate

[00:17:34] **Adam:** the first thing I do every morning.

[00:17:36] **Tim:** Yeah. Yeah. I guess that's my pooping time.

[00:17:41] **Carol:** So what are you playing? Like, what is the thing you're addicted to? Is it all of it,

[00:17:45] **Tim:** Just all of it. Just all of it. So they have like a mini crossword puzzle, which is good. Cause I don't like the big crosswords. I never, never cared for those, but, but the mini ones, you know, it's like you can usually do it within five minutes. So that's pretty cool. but my favorite one is called Connections, which I play with my wife, like, and we were driving somewhere and we were, I, we were Found, you could do like the archives of it.

[00:18:09] **Tim:** And so we were going back and playing like old ones together. We were on the drive. So I'd read her the things and she's driving and she really, you know, we really enjoyed it because she loves those, she loves those kinds of games. I've, I've never been a fan, but I am now. so I saved the connections.

[00:18:23] **Tim:** We, at lunch, we get together, have lunch, and then we'd go through the connections and try to figure out, it's basically a bunch of words. So you have like four, four sets. Is it four sets of words,

[00:18:35] **Adam:** Yes, four sets of four words.

[00:18:36] **Tim:** Four sets of four words and they are so, I'm absolutely amazed how good they are at creating these puzzles because it's always like you can find three that look like they really go together and finding that fourth one makes no sense.

[00:18:48] **Tim:** And then a lot of times it's like they cross, like they're like,

[00:18:52] **Carol:** Mm hmm.

[00:18:52] **Tim:** be an either or. Either of these groups, you know, the thing like, you know, something that's purple, shades of purple

[00:18:59] **Carol:** oh yeah, so it's basically you find what is the connection

[00:19:01] **Tim:** right. What's the connection between these words. Right. And

[00:19:04] **Adam:** You just get, you just get 16 random words and you're supposed to guess what the four groups are and they each have something in common. And like, that was one of them was like, all of these things are purple.

[00:19:13] **Tim:** shades of purple. Eggplant is a shade of purple, but you know, they can have another vegetable in there. So you're like, does the eggplant go with purple or does it go with, you know,

[00:19:22] **Carol:** Carrots.

[00:19:22] **Tim:** or carrots? Right. So yeah, that's pretty fun. So thanks guys. You got me addicted. Like, just like, just so glad I needed another time waster in my life.

[00:19:31] **Tim:** So.

[00:19:32] **Carol:** Yeah.

[00:19:32] **Adam:** stop playing Raid Shadow Legends and this is how we're gonna get you off of it. Mm

[00:19:36] **Tim:** I've never played that. Never played that.

[00:19:40] **Carol:** Yeah, the brain teasers are always fun. So my mother in law plays Wordle with like all of her friends and every morning she does it and they screenshot like their whatever their things are that they show with stuff and send it to each other and talk about it.

[00:19:54] **Tim:** Yeah.

[00:19:55] **Carol:** So

[00:19:55] **Adam:** what we're doing in that channel.

[00:19:57] **Tim:** Yeah. We'll post our scores on the chat. You, you probably won't get this reference. Some of the other folks who listen, who read all the Brandon Sanderson stuff will get this. I feel like Taravangian. So in the words of like the, Stormlight Archive series, it's no spoilers here. There's a character who's Taravangian and he's like the king of one of the, of the countries there.

[00:20:18] **Tim:** And, and on certain days he's like super smart. It's just sort of his curse and boon. And some days he's super smart. Some days he's really, really dumb and he's the king. So like they do a test of him every morning. And so if he's like really smart. He also has like no empathy whatsoever. So his solution would be like, you know, just kill all the children and that, you know, that'll solve measles or something, you know, something stupid.

[00:20:42] **Tim:** And then if, and if he's really dumb, he's like, he's like, just can't think at all. He has to, but he's like super emotional and cries over everything and super empathetic and just, you know, and so every time I do these, these, Puzzles in the morning. I'm like, Oh man, I'm having a Terravangian bad day. I'm a dummy today.

[00:21:00] **Tim:** I'm not, I'm not allowed to make any policy decisions today. My brain is slow. Anyway, that's me.

[00:21:07] **Adam:** Well, you know, I think, uh, like I said, you're welcome. Yeah. I think it's a good habit to have. It's, it's, it's how, like, I think, I think of it as like waking up my brain in the morning,

[00:21:16] **Carol:** Mm hmm. That's what I use coffee for.

[00:21:19] **Adam:** like I have my caffeine so I could do my connections anyway.

## [00:21:23] Developer Experience

[00:21:23] **Adam:** so we're going to talk about developer experience today, as I alluded to, with very many words previously. For me, what's immediately on my mind when I think of developer experience is fast deploys, right? I want, I want tests to run quickly and I want the deploy to go out quickly.

[00:21:38] **Adam:** What's up?

[00:21:39] **Tim:** Can we, can we box this? So what do we consider developer experience? Cause I, I know that's a term, but I've never really fully understood what that means.

[00:21:47] **Adam:** So, I mean, I guess it, it stems from, or it's inspired by the term user experience, right? Which is slightly different than user interface, right? User experience is about, Giving the user a delightful experience, right? It's right there in the name. Making them not frustrated, giving them what they need when they need it, where they need it, right?

[00:22:08] **Adam:** And making the application behave intuitively. So for me, developer experience is things that directly affect me as a developer that don't affect users of the application or, you know,

[00:22:19] **Carol:** Unless production goes down.

[00:22:22] **Adam:** Well, that's not part of the developer experience. It's poor developer experience that resulted in it being down for so long.

[00:22:28] **Carol:** Oh, no, no, no. You said that it doesn't impact the user. It does impact the user. If your builds take an hour to run, then you can't get a hot fix out. It does impact the user.

[00:22:38] **Adam:** That's true. I, you know, it's, it's entirely possible that if we had like two minute deploys instead of ten plus minute deploys, that I might have been more willing to break that pull request up into

[00:22:49] **Carol:** Mm hmm.

[00:22:50] **Adam:** So yeah, okay, I'll give you that one. But yeah, I mean, so for me, developer experience is everything from like the ergonomics of your IDE, right?

[00:22:58] **Adam:** So we've talked in the past about how like, you know, me personally, when I was a much younger person, I like took pride in the fact that I coded my websites in Notepad, right? No line numbers, no syntax highlighting. Just bold, weird looking black text on a white background. You couldn't even change the font in the versions of notepad that I was using

[00:23:19] **Carol:** It's such a psycho here. Yeah.

[00:23:21] **Adam:** Yeah. we've come a long way, right? So developer experience for me is like, okay, you know, IDEs, plugins, debuggers, you know, the, the, the, even the browser tools, right? So you've got the, the console and the performance stuff and the elements panel and the network tab, all

[00:23:38] **Carol:** Oh, the network tab. Right? Oh, it's

[00:23:41] **Adam:** these are the tools that make my job easier and more delightful.

## [00:23:46] Monorepos

[00:23:46] **Carol:** Yeah, and one of the things that I struggle with sometimes is, as we talk about, you know, bringing out our monolith into all of these other services, well, then the conversations keep going into, well, then this becomes its own repo. Well, that to me is a poor developer experience. If I have to, every time I want to make a change, if it's ever across multiple repos, I have to then make a change, make a PR, pull in another repo, make a change, make a PR and go through it like multiple times, or if I just want to like figure out where something's used at or how it's being referenced in other projects, I don't have an easy way to go find that.

[00:24:23] **Carol:** So I enjoy having like one repo that contains all my projects. Cause then I can deploy and build separately. Like things can work in there that they don't have to like all go together, but I have the ability to work daily more effectively and more efficiently than having to maintain so many repos.

[00:24:43] **Adam:** I think we have like kind of the worst of both worlds, right? So what you're talking about is like a monorepo, right? All the projects live in one, all the related projects live in one repository. So that like, if I'm changing things in this, like it, even if it's deployed as a little standalone package, the code is all shared in the same repository.

[00:25:00] **Adam:** So I make a change to this, what is ultimately a dependency of my application. And I can just like, okay, I'm making that change. It's going to be this version number. And then I can just also update the version number in my

[00:25:11] **Carol:** All the other ones. Yep.

[00:25:12] **Adam:** and then deploy them both at the same time. And then, okay, new, new version of your dependency is available and the application builds and it pulls in this new, new version and, and all is right with the world.

[00:25:21] **Adam:** Sounds great. we have, so we have our monolith application and as over the years we have started to extract things that were struggling performance wise out into microservices. So we have some that are in lambdas and we have some that are like docker containers that run on Fargate, right? there's just, it's a different, execution model, I guess is what I'll call it.

[00:25:42] **Adam:** and those are all within the Monorepo, right? We've got the, the main application and a folder called lambda and a folder called containers and all of that is there together. And so we can do that sort of shared changes there. However, we do also have some separate repos for things like, I've talked previously about TS modules and TSDB and TSRedis, right?

[00:26:02] **Adam:** These are separate repositories. that we, you know, they do us one thing and they do it well. And, and in this case, they're, they're type script, and we publish them as modules to our private GitHub, NPM.repository sort of thing. And we, we pull those into our services. Our lambdas and our containers and our application and all that.

[00:26:23] **Adam:** And so, what you were talking about, we get that we're like, okay, I need to make a change in TS modules so that it can be different for my application. So I have to go make the change, do a pull request, get that merge, create a new version number for it, publish that package, go make a separate change to my application, pull in that, that new dependency version,

[00:26:42] **Carol:** Yep.

[00:26:43] **Adam:** And pull request that and get that published.

[00:26:45] **Adam:** And it is annoying. I totally get you. However, the opposite side of that coin, we also have that where a monorepo can be annoying too, right? So I told you we have all these lambdas and all these containers and our application all in one. And so for each one of those lambdas and for each container, We have a QA deploy script, right?

[00:27:06] **Adam:** These are like continuous integration scripts. We have a QA deploy script, we have a script that'll just run the tests when there's a pull request, and we have a prod deploy script. Just those three things and between them. So if you, if you go to GitHub Actions and you happen to have enough actions in your Repository, you have to like click show more, show more down at the bottom.

[00:27:24] **Adam:** It's kind of like scrolling to the bottom of Twitter and it's like load more tweets, but it's, it's not automatically happening. You have to

[00:27:29] **Carol:** files. Yeah. Yeah.

[00:27:30] **Adam:** Yeah. Yeah. So, I mean, I don't know what the number is. I would say we probably have 100 to 120.

[00:27:36] **Carol:** Oh my goodness.

[00:27:37] **Adam:** Yeah. So you have to go like go in, you scroll down, you click the button, you wait two seconds for it to load more, and then you scroll down, you click the button, you wait two seconds for it to load more all the way to get to the very, you know, you, you know, it's the one that starts with a Z because it's, you never use that one.

[00:27:49] **Adam:** So you purposely put a Z there so that it starts, it, it, orders to the bottom of the list, but now you, the one time that you need it, you have to do that. Right. and so that's annoying. And then, like. The, the, the width of that, so the UI. for actions, right? You're, you're, I'm like, okay, I need to, I need to run the QA deploy script for X, Y, Z, Lambda, right?

[00:28:13] **Adam:** So, we have, conventions for how we name our workflows so that they kind of group themselves naturally and you kind of know where to look for them. And so I, I know I need the one that's like QA deploy Lambda and then the name of the Lambda, right? X, Y, Z. And so I've got to like scroll down to that section and they're in alphabetical order and it's just, it's, it's kind of a nightmare to be honest.

[00:28:32] **Adam:** Right. And to the point where, so they did add pinning, right? So

[00:28:36] **Carol:** Yeah. Yeah. I saw that.

[00:28:37] **Adam:** we have one pinned action and that is our prod monolith app deploy script.

[00:28:43] **Carol:** So that's just easier to get to,

[00:28:45] **Adam:** Right. Yeah. That's the one we, we run most often. So that's going to be, it's always first in the list and we never have to do the, the show more or anything like that.

[00:28:53] **Adam:** So yeah, I mean, that's just to point out like, Monorepo is not the silver bullet, right? And that's entirely a GitHub thing, right? It's entirely possible that GitLab, however they do their stuff, might be different or Travis CI or whoever. We just use GitHub actions for ours,

[00:29:07] **Carol:** Yeah, that's what we're using too now. Yeah, and that's what we're seeing. Like, it is stacking, but to me, I would rather go through that and deal with it when I have to deal with it on the one off where I need to make that change versus every time I need to make a change between multiple repos, having to do multiple PRs.

[00:29:25] **Carol:** Making sure they go out together, like making sure everything releases, nothing got missed. If there is something that's dependent on the other, that it's actually getting deployed in the right order, so that I don't break something ahead of time and

[00:29:38] **Adam:** Yep.

[00:29:39] **Carol:** Develop your experience, yo.

[00:29:41] **Adam:** Tim, you're nodding. You got something you want to add in

[00:29:44] **Tim:** Not as far as repos go. We just do one, one project, one repo. It's pretty, pretty straightforward. We don't

[00:29:49] **Adam:** got it easy over there.

[00:29:50] **Carol:** Yeah.

[00:29:51] **Tim:** well, I mean, for the stuff I normally work on, we, so our, our microservices ecosystem, that, that is a mess. all, all these, separate little projects. You never, you gotta, like you said, you gotta make sure you've deployed to them properly

[00:30:03] **Carol:** Yeah. In the right order.

[00:30:05] **Tim:** But, you know, we script all that out, so.

## [00:30:09] Automatic Deploys

[00:30:09] **Adam:** So let me ask you, do you guys have any, anything that automatically deploys anything ever?

[00:30:14] **Carol:** Yeah.

[00:30:16] **Adam:** So what for you triggers an automatic deploy?

[00:30:20] **Carol:** A merge domain. Which

[00:30:22] **Adam:** about production.

[00:30:23] **Carol:** No, no, no. Hold on. Here's where it gets fun. Our main is not production. Our main is development.

[00:30:30] **Adam:** Oh, okay.

[00:30:31] **Carol:** and how you have to branch is not fun at all. We won't go into that because that's a whole nother bad developer experience that I will be working on for the next few months to get hopefully a better solution in place for.

[00:30:44] **Carol:** But yeah, our main actually goes to development. and then we have a test EMB, and then we branch off test, and then we make staging from that, and then that goes to production, right? So it merges to main, they automatically deploy, and then we have our test deploys that run every three hours automatically.

[00:30:59] **Adam:** So when you say a merge to main, which is your development branch, auto deploy, does that mean you have like a single shared development server?

[00:31:06] **Carol:** yeah. Well, there's a bu it's like spread out, but yes, it, it's something, and then goes to all these other places. That's stuff behind the scenes that I don't

[00:31:15] **Adam:** But it, but it's a, it's for. Kind of like the, what I was talking about, how I have QA and UAT in the same place. It sounds like it's just your QA, like let's integrate all of our stuff. My changes, your changes, Tim's changes, all in one place, make sure that everything's happy.

[00:31:27] **Carol:** yeah, we have 40 devs that work on this project, right? So between the 40 of us, we're constantly putting in PR. So all of our stuff goes together throughout the day a lot. There's constantly PRs that go into dev, and then that auto deploys, and then we use Octopus Deploy to actually push it to the servers.

[00:31:43] **Carol:** And that's where it does all the, it goes into it, but then it actually handles what server it physically sits on.

[00:31:49]

[00:31:49] **Tim:** Our deployment is tied in with our Jira ticketing system.

[00:31:53] **Adam:** Okay.

[00:31:53] **Tim:** So it automatically, so, you know, first it goes to, you know, you approve it, approve, review it, approve it, and it will deploy to dev. And then you can roll a bunch of different things together and then deploy that to production.

[00:32:06] **Tim:** And I think that's, that's a great, experience, right? User experience to be able to, developer experience to be able to just, you don't have to like go to the command line manually SSH into the server, you know, do a pull to pull it down. It's just you click, click a button and we have like some, PCI questions to make sure that you've reviewed the code and do all that.

[00:32:28] **Tim:** You can't. Deploy,, unless you've answered those questions, you click that button. And then, you know, within a few minutes, you get a notification on your, we use Teams, your, or your Teams or Slack channel. And you also get an email that says, you know, if it failed or, or, if it built and built properly and that's, I mean, that's fantastic just to just have one place to deal with all of the moving of code from environment to environment with actually, without actually having to get in those environments, which is also a security thing, right?

[00:32:57] **Tim:** So you don't really want. Five or six people all with access to production just in case they need to deploy something, because that, that's a security risk. So if you want to stop them from deploying, you just remove their JIRA permissions.

[00:33:11] **Carol:** What about you, Adam? Do you guys

[00:33:13] **Adam:** So we have a handful of things that automatically deploy to production, but, the, the big ones, like our monolith application and, theare like the big money makers, we do not, we, we try to be more intentional about that because it, it, every now and then it does happen that something gets merged that shouldn't go out yet, or, or, you know, we're like merging two or three things all at once to try and, get a sort of a, a queue ready or whatever, right?

[00:33:41] **Adam:** Like these have all been tested together, integration tested on QA. But they're not yet in main and we don't want to like trigger three deploys against the giving application and have it like maybe blip and act weird when because we merge three things at once. So we want to just merge all three and then say deploy,

[00:34:00] **Tim:** Your application is giving, it's,

[00:34:03] **Adam:** It's giving what?

[00:34:04] **Tim:** it's just giving vibes.

[00:34:06] **Adam:** Okay, it's it's giving money maker. Um, Ooh.

[00:34:12] **Adam:** so, the yeah, so those those things that we are a little bit more closely guarding. We require manual, like, go into GitHub Actions and click the run workflow button to do the deploy. and we have thought about, like, the possibility that GitHub Actions could be down and we need to do a deploy.

[00:34:32] **Adam:** And so, like, all of our GitHub Actions, are based on our makefiles, right? They do the whole GitHub Actions thing, right? They're like, okay, install node and run the tests and the, and running the test is always a simple command. It's like npm run test, for example. and then the deploy is always, or actually, so what we do is all, I said it's all make files, so we have a make command, it's like make test, and that'll run npm run test, which runs the, you know, if it's jest or whatever to run the test.

[00:34:59] **Adam:** And then, let's just say we can call it make deploy, that's not what it is, but it could be. and that is how we do a production deploy of that service. And that way, should GitHub Actions be down, we don't have to go, Oh crap, what are the nine things that GitHub Actions would have done? We just go, okay, make deploy.

[00:35:15] **Adam:** And that'll run the tests, and it'll build the container locally, and it'll push it up to ECR, and it'll trigger the ECS. Command line tools to say, okay, there's a new container available. Go get it and do your blue green deployment thingy with it. Right. yeah. So, I mean, I have to attribute my coworker on that.

[00:35:33] **Adam:** That was all his idea. And it's, I mean, it has never been necessary, but I think it's a fantastic insurance policy

[00:35:39] **Carol:** Yeah. I'm just thinking that I should probably get something written up. So we have a backup plan cause I don't know what we would do.

[00:35:46] **Tim:** so, Which is so funny cause that, that just totally defeats the whole purpose of why Git was created in the first place. It's decentralized source control without, you know, a main server. Now, now GitHub and Atlassian have become that bottleneck. If it's down and we're screwed,

[00:36:02] **Adam:** you are and you aren't, right? Like you still, everybody still has the Git repo on your local machine. If, if GitHub were to like be hit by, right, let's just say, hypothetically GitHub is all in US East one, and it gets hit by a meteor and there is no more GitHub, right?

[00:36:18] **Carol:** That'd be a real bad developer

[00:36:20] **Adam:** we're bankrupt. Everybody gets a refund and, and we don't have your code anymore. Sorry, go home. We would not be without our code because our, our machines all still have the Git repo. So all you have to do then is go create a GitLab account and, and say, okay,

[00:36:33] **Tim:** meteor.

[00:36:35] **Adam:** Well, yeah, I mean, I'm, I'm close enough to us east 1, I'd be dead too, but, Theoretically, if you were, say, in Seattle, just go create a GitLab account, and you, you add it as a, as a remote to your Git repo, and you should just do Git push, origin, main, or whatever, and boom, it's up, right?

[00:36:51] **Adam:** Like, that is the beauty of, of the distributed part of Git, I think, and I agree that, like, it is a little ironic that GitHub, or that Git is about decentralization, and then GitHub kind of re centralizes some pieces of it, but I think that, Ultimately, what GitHub itself has been is a huge boon for developer experience, right?

[00:37:10] **Adam:** Like the, the code review tools in pull requests has been amazing.

[00:37:16] **Carol:** So great.

[00:37:17] **Adam:** so much better than life pre, pre that.

[00:37:20] **Tim:** Mm hmm.

[00:37:21] **Adam:** and like the addition, like I think that they just kind of wait for things to become like Awesome. That is so awesome that everybody uses them. Right. So like, Travis CI is the one coming to mind.

[00:37:30] **Adam:** Cause that's what we use, but like CI tools and before Travis, and all of that, like, or was it Jenkins? so, like, and they're just like, okay, well, everybody uses that. So let's build it into our product. and then, you know, we can charge you for usage of it sort of thing. And, and so. And honestly, I like it because GitHub Actions is way better than any experience I ever had with Jenkins or Travis.

[00:37:55] **Adam:** And it works, it's easier to understand, it works faster, and it works better. And it's directly right there, integrated in a tool I'm already using,

[00:38:03] **Carol:** Yeah, I do like that. I do like this altogether. I never had to configure Jenkins and I never had any issues with it, so I can't complain, but I will say like some of the setup with the get actions, they have not been fun to deal with, to figure out like why actions won't run on other branches, like why it only runs on main.

[00:38:20] **Carol:** And then you have to tell it to pull the ref the test in order to get it to run on test. And some of those things weren't very fun and it's not. Like, I guess, for me, it would be great if there was a user interface for it, right? If there was some, like, configurable way to do this that made sense to a user, and it didn't just have to be YAML, because then, every time we want to make a change, we have to go through the build process again, and wait 30 minutes, and see if it works or not.

[00:38:48] **Carol:** And that's been a lot of fun, you guys. Just so much fun.

[00:38:53] **Tim:** build process, the new smoke break.

## [00:38:57] Source Control

[00:38:57] **Tim:** Along the lines of source control, I'll kind of tack this on here. Is that source controlled DB schemas. are a fantastic user experience, particularly it's like, so like when you're just trying to get a project set up locally, particularly if it's a new project, you're maybe you're on a new team or whatever, having, you know, source code, that's no issue.

[00:39:19] **Tim:** You pull it down from, from Git or whatever you're using and, and do it. But having the database schema, And to be able to run that against a local database and just, it builds all the tables, sets all the permissions, pre populates it with, you know, test data, that is fantastic. Cause in the, in the past, that was all manuals.

[00:39:39] **Tim:** Like you got your code side done, now you get your database, it's all manual. And that's so error prone, but to have it all in, in source control and this, in build files is such a great experience. Cause then you just say, run this. You're, you're, you're done. Now. You have a local setup.

[00:39:58] **Adam:** And migrations.

[00:40:00] **Carol:** Yeah. I love our migration. It's a great, you keep things in sync. Yeah. Yeah. I love being able to make changes to our model and then just hitting a update and then it just generates my migration for me and it's like, Oh, you changed the model. So clearly that table changed. So here's your new column and here's the create for it.

[00:40:18] **Carol:** And now it just goes in code and gets created all the way up and I don't have to deal with it. Cause yeah, I remember the days, Tim, where we used to have to bring a, like copy of production down. Cause it would get so off sync cause

[00:40:31] **Tim:** Constantly sinking things.

[00:40:34] **Carol:** people would be making changes to devs. It never went up anywhere else.

[00:40:37] **Carol:** And you'd be developing off of like people's changes and they weren't really changes. They weren't even there. And you didn't know until way, way farther, like closer to like, way closer to production, you'd find out that that's a problem and you're like, okay, well, it's time to bring production back down.

[00:40:53] **Tim:** Yeah.

[00:40:53] **Adam:** Yeah. We, we do something similar actually. So we call it cutting a new QA branch. Right. So again, QA for us is QA plus UAT, but, you know, so we, we just have one QA branch and when we merge to it, all of our, anything that's in that monorepo, That is, again, not those like, actually everything automatically because it's QA, right?

[00:41:13] **Adam:** The, the stakes are way lower, right? So all the lambdas, all the containers, the, the main app itself, if we merge to QA and push that up to GitHub, it's getting deployed,which I love. Cause it's just, it's saved me, that alone has saved me probably like two days this year. in, in time, like before we had that, we, it was, you know, you'd have to like, okay, I'm going to go into this folder and run this CLI command to build the Lambda and upload it.

[00:41:41] **Adam:** Okay. Now I got to go to this other folder and do this other Lambda. Same thing. Do that, you know, for 15 different Lambdas, do it for 10 different, Docker containers. Got to go to each of the production servers. For a customer, you know, remote desktop in, open the folder, right click and say, get pull,

[00:41:59] **Carol:** my gosh. Yeah. Yeah.

[00:42:00] **Adam:** was awful. And this is, you know, just in the amount of time saved, like, okay. It got to the point where I was so good. Like I'd done it so many times that like, I would have, I have a, an app called Royal TS, which is like, it's a tabbed interface for remote desktops. Like you can open like 15 different computers in, in tabs.

[00:42:19] **Adam:** Right. And so I would open all of them up, I'd get all of the like, the, the file explorer window is in the same spot on all of them and the command line is open in the same spot on all of them and all of that. And I'd like, You know, switch tab, right click, do the thing. Switch tab, right click, do the thing.

[00:42:33] **Adam:** Switch tab, right click, do the thing for all of them. And then you go back to the first one. It's like, okay, now I do the command line thing. Change tab. Now I do the command line thing. Change tab. And I would just rip through them all really quick. And people at work, my coworkers would be impressed with how fast I could do a deploy, but at the same time I'm sitting there going, God, I hate this so much.

[00:42:49] **Carol:** I just can't imagine having to do that now, like, with how I work, like, it doesn't even cross my mind that I would ever have to remote desktop into a server to make a change or to have anything happen.

## [00:43:02] Fast Builds

[00:43:02] **Adam:** So, I mean, we've touched on a lot of things here. one thing I guess, do you, do you think it's worth spending time? Should we spend the time to. Talk about like the importance of fast builds and like why that's necessary and important and beneficial.

[00:43:20] **Carol:** Yeah, I mean, I think it's worth, worth the conversation. Um,

[00:43:24] **Tim:** of the idea. Right?

[00:43:25] **Carol:** It was. Right. So, okay, let's just let, let's start with what happened to me today, right? So production is down. Stuff's broken. A, it takes some time to figure out the problem, diagnose it and fix it. Right. So let's say that's 17 minutes. And then the, the rest of, the rest of my 37 minutes was like, okay, make the code change.

[00:43:47] **Adam:** Pull request, merge, and deploy, right? Which you would think, you know, make a, make a code change, which I'll tell you, it was not that big. It was like four or five lines of code change. and, and commit.

[00:43:59] **Carol:** not your, not your big,

[00:44:01] **Adam:** Correct. The fix was just like some missing lines, basically. so commit, pull request, right?

[00:44:07] **Adam:** Okay. So for the pull request, I've gotten, I, I. Try to avoid the, a GUI for Git, right? There are a few things, like if I have a lot of stuff I'm trying to commit, I'll, I'll fall back to a GUI because it's just a little more ergonomic than the command line. But for, especially if I'm doing one file sort of thing, man, I just rip through it on the command line, right?

[00:44:27] **Adam:** Like, git add whatever, git commit, here's my message, push. I've got like a bunch of, uh, aliases in my terminal. So like, right, so I just do gh space e. That's like a, even that is just, Shorthand for git status minus SB, right? Because I like that view of the git status, but I just need it to be like just a few keys that I can hit and get the thing,

[00:44:51] **Carol:** So side, little side thing on that though, the bad problem with aliases though is when you're trying to teach someone how to do something and I'm just typing in and I just do get and I put CO and I'll type my branch name because that's just an alias for checkout. So I'm like, git checkout, and I type my branch, and then they'll come back and go, I don't understand, like, this command, does it work for me?

[00:45:12] **Carol:** Like, how do I figure it out? I'm like, oh, well, here's all my aliases. You should learn them if you want to learn from me. So where, when you do use a GUI, then there aren't those learning, like, curves on it. Then someone can just see it. Yeah.

[00:45:26] **Adam:** yeah, that or working on like somebody else's machine or, you know, if you have a different machine, you don't have the same aliases set up, whatever.

[00:45:32] **Carol:** Yeah. So sorry. Yeah. Go back. So, yeah.

[00:45:34] **Adam:** yeah. So, you know, I rip through, I create my pull request. I could do that really quick from the command line with the gh tool. and then, you know, we've got, it takes a minute for somebody to approve it.

[00:45:46] **Adam:** and it takes friggin eight minutes for the test to run, which is annoying, right? And that's kind of, so because of

[00:45:53] **Tim:** Another good reason you should never test.

[00:45:56] **Adam:** Where's

[00:45:56] **Carol:** Where's, where were

[00:45:57] **Tim:** I'm channel. I'm channeling Ben. I'm channeling Ben.

[00:45:59] **Adam:** Right. so this is, this is one of my chief complaints about CFML in today. And I'm sure that if

[00:46:07] **Tim:** Just one

[00:46:07] **Adam:** sure that there are people who are smarter than me that can make CF run faster, and I welcome them to come fix my builds for me for free, because I would love to have that, but, or, or they can teach me, or they can publish a blog post on how to do it.

[00:46:21] **Adam:** I just can't figure it out there. It is what it is. Right. So we've got our, our cold fusion container, which takes. You know, maybe two minutes to build and then, you know, takes frigging four minutes to start and then we got to run, everything, right.

[00:46:35] **Tim:** a long time to

[00:46:36] **Adam:** it's so slow. And this is Lucy, not ACF, which is even faster or Lucy is faster than ACF.

[00:46:42] **Adam:** and so it's at a point now, where our, the, the, the GitHub actions script includes a thing where we like, okay, start the CFML container. And wait a maximum of five minutes for it to report healthy. And if it doesn't report healthy, then just fail this run

[00:46:59] **Carol:** Oh, wow.

[00:47:01] **Adam:** Because we don't want it to run for 20 minutes, right?

[00:47:04] **Adam:** Before it finally comes up or whatever. It's like, just if you can't get it done in five minutes, that's it. You've cut off. Try again. and it's just, it's painful.

[00:47:13] **Carol:** Yeah. And the,

[00:47:14] **Adam:** When it does fail, like if you have a syntax error or something, I had that, that was one of the problems I had to fix with my, my second PR today was like, you know, I made some code changes and it was a very simple syntax error, right?

[00:47:26] **Adam:** Like return, a string in quotes and a, and a variable after it. and I forgot the little ampersand between the two, right? So you just have quote and then variable name and, and. Get, you just get like, oh, I can't, I, tag, what is it? script expression. Can't be cast as a tag or something like that.

[00:47:43] **Adam:** Like this is not, this is not helpful. Debug information.

[00:47:46] **Carol:** no, not at all.

[00:47:48] **Carol:** so I will say, let me, lemme throw in a plug here. it's a cfml thing. Oh, wow. Where's Ben? I need him.

[00:47:54] **Adam:** right, so, command box, you guys have, I'm sure heard of Command Box. there. It's like a. It's a, free and open source, like CFML command line utility, and it does a lot of things, and then there are, there is a separate project called CFLint, you may or may not have heard of that.

[00:48:12] **Adam:** It's, it's supposed to be like, you know, ESLint, but for cold fusion code, whatever. I've worked with it over the years, off and on, never been super happy with it. I did try to contribute. I just, you know, between time and, and motivation kind of, you know, however, I recently learned there is like a CFLint plugin for command box where you can basically say like box CFLint and then give it a specific CFC name or something.

[00:48:36] **Adam:** And it will like run CFLint on that file and tell you the things that it thinks might be wrong. Like it gives you warnings

[00:48:41] **Carol:** Ooh, fancy.

[00:48:43] **Adam:** yeah, I'll put the link in the show notes, but that helped me. That was the way that I found this problem. So like, I, I saw that there was this syntax error, right? And I just, it's not even that big of a file.

[00:48:53] **Adam:** It's like a hundred line file, something like that. So I just scanned it real quick. I'm like, okay, everything has a semicolon, everything. Like I did fix a couple of things that were just a little funky that it was like, okay, this doesn't need to be a string with a variable and pound signs in it. I can just move the variable outside of the string sort of thing.

[00:49:07] **Adam:** Like let's simplify and clean up. And I still couldn't find anything wrong and it failed again. So I'm like, okay, well,at that point I remembered this boxcflint thing and I pointed that at it and it, it did take a, you know, a good, like six, eight seconds to run because ColdFusion is slow, but, it did point out this problem and I was like, yes, thank you.

[00:49:25] **Adam:** so, yeah, that, that ultimately was part of the fix, which was great. So, I will definitely put,that in the show notes, that link, that was super useful in a pinch.

[00:49:34] **Carol:** So we were talking about build times, right? Why they're important. Like, why it matters to the developer. Well, for us, like I said, we got 40 people, right? Right. And on the average, like the, each developer puts in one to four PRs every day. So if you like average it out, it's like almost two PRs a day, like per developer is what it comes to.

[00:49:55] **Carol:** Well, when your build time takes 30 minutes, just for the initial, like getting it through the gated check in process, just to where it's in main or in development, right? If I go to do it, someone else does their PR, mine gets canceled. Because we don't want dual deployments running at, or dual builds or dual deployments running at the same time.

[00:50:16] **Carol:** So now I have to wait for the second one to go. Well, with so many people, guess what happens? Another one comes in and suddenly your one code change that you were making, because you couldn't get it out in a few minutes, is now stacked to like, you know, 45 minutes before you can even see if it's on dev.

[00:50:32] **Carol:** And, I don't know about you guys, but I hate context switching when I need to go test something immediately. It just frustrates me because then I go back and I completely forget I needed to check that thing on main or check that thing on test and figure out what's going on. I forget I have to go switch the story now to ready for testing or update anything.

[00:50:52] **Carol:** And it just, it gets old. So that's a big, a big losing point for me when builds take a long time is that they stack. And now everything just feels out of whack for me.

[00:51:03] **Adam:** Yeah.

[00:51:03] **Adam:** So, I, I totally agree. it, that's the thing is like the, the, if it runs quickly, if it's close enough to just consider it as instant, right. If it's

[00:51:12] **Carol:** Mm hmm.

[00:51:12] **Adam:** seconds, then I just, I stay focused, right. I'm right there. I create the pull request. I see everything starting to pop in as green.

[00:51:19] **Adam:** and it just keeps me on task way better. and keeps me happier for

[00:51:24] **Carol:** So you were talking about your whole like tab system for your remote desktop, like tool you had, right? My Chrome now, that's the way it is every day with GitHub because someone will be like, oh, I've put this PR in. Can you go ahead and look at it? Well, I look at it, it's not even through building yet, so first I wanna make sure it's gonna pass.

[00:51:44] **Carol:** So now I have like 10 tabs open. You know, some of them are mine, some of them are other people. They're all just waiting. And of course in the meantime I'm having meetings and I don't remember to go back to them for a while. So now they're still waiting on me to get approval and yeah, it's a nightmare.

[00:51:59] **Adam:** yeah, so I don't think it hel I don't think it shows anything about statuses of like, you know, the, the checks that are running in GitHub. However, I do really like, I have this tool for, it shows up in my, I guess you'd call it the command bar? Like the upper right by the clock in Mac OS.And it's just, it looks like a GitHub icon, and I click on it, or it shows the GitHub icon and it shows me I've got currently 30 pull requests that are, are relevant, right?

[00:52:26] **Adam:** Like it shows me all the ones that I've created that haven't been merged yet and whatever status they're in, and it shows me like, these are the ones waiting for my review. if they've been like reviewed, but they're requested a change, like it breaks them down like that. It would be really nice if that would show like the, the status.

[00:52:40] **Adam:** like, so here are all the ones that are waiting for review and, you know, okay, the first five, these are still waiting for

[00:52:46] **Carol:** They're still building.

[00:52:46] **Adam:** other three, if these are, these are green or red thing, then you can go, okay, well, the red one, I'm just going to go say, like, ping me when, when the tests are passing.

[00:52:55] **Adam:** Right. I'll see if I can find the, cause I'm sure there's going to be people that want this. I'll see if I can find what, what tool this is. Cause of course, like the menu itself doesn't tell you anything about what app this is. I'll have to figure out

[00:53:07] **Carol:** Like what you're actually using. Yeah.

[00:53:08] **Adam:** Yeah.

[00:53:09] **Carol:** Yeah. So for me, like, even if I go in to look at just the PRs that are assigned to me, I have so many because as the lead architect now, every single Dependabot PR automatically goes to me. And then it also goes to the teams that are handling it. So I'm like, I can't even filter unless I filter out Dependabot.

[00:53:30] **Carol:** Like it's, it's crazy. It's a lot right now. My developer experience is not great, but it's getting better every day. I will say that. Like it's small, small things to keep speeding up the builds, clearing out the, the security findings and stuff and making it more usable.

[00:53:48] **Adam:** Yep. I, I have a, so I use Arc Browser, and you can, I like the way that it does like pins tabs, right? You just have this section of tabs that are always there. You can even close the tab. So it's not using memory, but it remembers like what the URL was, for example. And so I have one that's like, you know, my pull requests

[00:54:05] **Carol:** Mm hmm.

[00:54:05] **Adam:** you know, it goes to the pull request thing and then it's, you know, get rid of anything with label dependencies, cause those are all from Dependabot and get rid of anything with this label and get rid of anything with that feature or whatever.

[00:54:16] **Adam:** And so it has all those like filters pre applied, which is really nice. All right. Well, I think, that's gonna about do it for us.

## [00:54:23] Patreon

[00:54:23] **Adam:** Okay, I'm just going to go with a, with a genuine thing in here. I'm going to say this episode of Working Code was brought to you by our Discord server, right? Like, the people there are awesome, right? I, I genuinely want more people who listen to this show to come hang out with us. It's a great place to go, and just a great community to be a part of,

[00:54:42] **Tim:** A supportive group. Very

[00:54:44] **Carol:** they're very, yeah. Are you gonna make it to game night?

[00:54:47] **Adam:** going to try.

[00:54:48] **Tim:** Seems like, yeah, seems like Brian is organizing a game night. I think you want to do, Adam, you want to do a, Cards Against Humanity?

[00:54:54] **Adam:** That was my suggestion. It seems like other people are more interested in, uh, code names.

[00:54:58] **Carol:** That game is so fun. I love it.

[00:55:01] **Tim:** I would like a Cards Against Humanity. I would show up for that, for sure.

[00:55:06] **Adam:** anyway, so if you want to join our discord, you can go to, what is it? It's workingcode.dev/discord. That's right. I apologize for my barking dog, but this is the outro, so we're just going to let it go.

[00:55:15] **Adam:** it's also, in addition to our Discord, brought to you by listeners like you, just like PBS.

[00:55:21] **Adam:** If you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo, you guys rock.

## [00:55:36] Thanks For Listening!

[00:55:36] **Adam:** We do actually have a new patron to thank this week and welcome aboard, Brian,

[00:55:40] **Carol:** Hey, Brian!

[00:55:41] **Adam:** I believe he might be, yeah, yeah, I think it's our third or fourth

[00:55:45] **Tim:** I think it's

[00:55:45] **Adam:** Brian in the, in the Discord server, we need more Brians, if you're, if you're a Brian and you're not on our Discord, you gotta come join up, cause, we, it's like Brian gang or something.

[00:55:54] **Adam:** Anyway, so you can go to patreon.com/WorkingCodePod if you want to throw us a few dollars and help keep this show running, keep the lights on and the mics running. we would greatly appreciate it.that's going to do it for us this week. We'll catch you next week. And until then,

[00:56:07] **Tim:** All right, Matt, cue the Irish whistle music. As I read you an Irish blessing. May your bills always be quick. May your source control be true. May your linters shine warm upon your face. Until we meet again, your heart matters.
