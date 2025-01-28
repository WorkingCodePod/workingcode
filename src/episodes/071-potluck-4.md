---
title: "071: Potluck #4"
description: "This week on the show, the crew discusses a potluck of tasty topics."
date: 2022-04-20
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/071-potluck-4/id1544142288?i=1000558142876"></iframe>

Sponsors

- [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

This week on the show, the crew discusses a potluck of tasty topics. Ben is trying to figure out what project he wants to use as his vehicle for learning Docker and container-based deployments. Adam wants to completely overhaul his data synchronization workflow, but is having a lot of trouble getting excited about the work (despite all of the exciting ingredients). Carol is being worn-down by the analysis phase of a project and just wants to start _doing the work_ and accruing some wins for her team! And, Tim just can't wrap his head around Functional Programming (FP) - I mean, how the heck can you possibly program anything without `IF`-statements?!

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/071-potluck-4.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** So you're saying that my first deploy a Docker container shouldn't even be ColdFusion should be something even lighter weight

[00:00:07] **Ben:** and

[00:00:07] **Adam:** Um, I'm saying if you've never used a hammer to drive a nail before don't pick building a house as your first project,

[00:00:15] **Ben:** I know that's the thing that I keep, keep going back and forth on

## [00:00:39] Intro

[00:00:39] **Adam:** here we go. It is show number 71. And on today's show, we're doing a potluck, which means that we are all coming into this blind listeners and hosts alike.

[00:00:47] **Adam:** We don't know what we're talking about, but we're going to figure it out. but as usual, we're gonna start with our triumphs and fails. And Ben, it is your turn to go first, buddy,

## [00:00:55] Ben's Failiumph

[00:00:55] **Ben:** I'm going to go with what I classified as a triumph and what you immediately reclassified as a failure. And we'll meet somewhere in between. so as I'm sure we all, as I'm sure happens to all of us, our preferences in code and our coding methodology changes over time. and, the way that I named my database columns has changed over time.

[00:01:14] **Ben:** When I first started programming, it was snaking. so, you know,word underscore

[00:01:18] **Adam:** all lowercase

[00:01:19] **Ben:** yeah. With all of our case, for columns. but in my actual ColdFusion code, I evolved to using camel case, where there's no underscores and words are separated by an uppercase letter. And, I sorta got tired of that and I started wanting to see my database columns look like my code columns, because they're always in the same context.

[00:01:39] **Carol:** Yes.

[00:01:40] **Adam:** developer focusing on the things that don't matter.

[00:01:42] **Carol:** Yes.

[00:01:44] **Ben:** so, in an effort to just continually try and clean up my code, I went through and I changed 33 database columns and had to touch 71 files that referenced those columns. And,the triumph is that, I did it and I dragged everything forward and I try to leave things better than I found them.

[00:02:02] **Ben:** And the. Failure before call it.

[00:02:05] **Adam:** Yes.

[00:02:06] **Adam:** Yes.

[00:02:07] **Ben:** is that I have zero tests whatsoever. And, and so far I have not seen any errors crop up because of this. And this is not an anti-testing rant. only that,

[00:02:18] **Tim:** it is.

[00:02:19] **Ben:** not explicitly though, perhaps implicitly,testing is a tool like, like anything else.

[00:02:26] **Ben:** And if it speeds you up, that's great. But if it's not speeding you up, then it's not adding value. So for me in this particular, very low value application where no one can die and no one's paying me to do anything. just being able to move really fast and replace a lot of stuff and

[00:02:45] **Adam:** Yeah. I mean, you're absolutely not wrong

[00:02:48] **Carol:** So, but the you Adam hurry

[00:02:52] **Adam:** but the,the thing I want to point out here is that you said no errors yet. Right. and if you had tests, there would be no need for yet. You would know.

[00:03:04] **Ben:** Well, there's always a, there's always a need for yet,

[00:03:10] **Adam:** We'll get you one of these days.

[00:03:11] **Adam:** By the time this podcast goes off the air, we will convert you.

[00:03:15] **Tim:** we might have to run for 20 years, but.

[00:03:19] **Ben:** like I look at the, at huge projects, like, like the Lucy project, right? So when Zach Spencer comes in and he starts messing with the code, Hylo, he'll send me PR to look at just for fun. And, and he'll have, he'll add a test and then he adds the code. So like, I can really respect that.

[00:03:33] **Ben:** Cause you have this massive project to smoke test. It manually would be an outrageously poor use of time and, with unpredictable results. So I totally agree. You know,sometimes you don't want to do anything to an extreme, so it's, I think to some degree it's fun to have the pendulum swing hard the other way, just to know that it can. So

[00:03:55] **Carol:** you sound like a risk taker.

[00:03:58] **Ben:** which is opposite

[00:04:00] **Carol:** It is not. You.

[00:04:03] **Ben:** anyway. So that's me. Adam, what do you got going on this week?

## [00:04:07] Adam's Fail

[00:04:07] **Adam:** So I'm going to call it a fail. And not for the reason that you might be thinking. So my current project, for whatever reason, I think I was just a little bit test fatigued. Cause I've been, I've talked recently about my efforts to really embrace TDD and I still believe it is a good thing and worth doing.

[00:04:27] **Adam:** my, my very first project, I was like, I was a hundred percent code coverage, like

[00:04:33] **Adam:** all the way I D I wasn't perfect at it, but I was aiming for perfection. My second project with it, I relaxed a little bit. I was like, okay, this is helping me write good software. It's not about the perfect score at the end.

[00:04:44] **Adam:** It's about good software and tests that cover the important things. and then this project yeah, I mean, I guess test fatigue is kind of the best way to describe it. I was just tired of fighting with the tooling, the issues with mocking and that sort of thing. And I was like, I just need a week.

[00:05:00] **Adam:** going back to normal pallet cleanser sort of thing. And, and now it's been three weeks and I still don't have any tests. And there've been times where, I finished the thing that I'm working on and it's like, okay, but now what? Right. Like, I feel like TDD got me to this place where I was able to take the list of requirements and turn those into tests.

[00:05:25] **Adam:** And it was just like, just keep going until the tests are gone. And then when you inevitably find things that aren't covered by your tests, when you think, oh, I need to add this feature, then you go either add a placeholder test for it or add it to a notes file or something. and now without that, I'm feeling the lack of it.

[00:05:40] **Adam:** So I still feel a little test fatigue. I'm not sure I'm quite ready to like jump in and write the test for this. And then I'm going to need tests. This is going to be a mission critical piece of software. I dunno, I'm just, I'm kind of all over the place. I'm a little, I find myself at a loss of enthusiasm this week.

[00:05:56] **Tim:** We've got to send Adam Cameron over to break you.

[00:05:58] **Adam:** Yeah. Yeah.

[00:05:59] **Ben:** Well, let me ask you this question, because I know that a huge value add of writing tests as people will explain it, is it forces them to architect their code in a more decoupled, more, composition over inheritance type of way. That makes it easier to test. Even when you're not writing tests. Do you at least find yourself trying to apply those architectural patterns that would have facilitated testing in the first place?

[00:06:25] **Adam:** So I have. I don't know, 20 plus years of experience writing ColdFusion code. And to answer the question is yes, if I was writing CFML, but like over the last five years, maybe a little bit more than that, I've really started to take on a lot of JavaScript. especially node doing Lambda and writing stuff in Docker containers that are going up onto the cloud.

[00:06:49] **Adam:** And I had this bad habit of like, just put everything in one file, Okay. I need to function, go create a new, another function at the bottom of the file. And it's very modular, functional, like a lot of pure functions code. but it's at the end of the day, it's very messy. And I have to, sometimes I don't remember to go back in and clean it up and think, okay, these seven functions are really kind of grouped together.

[00:07:11] **Adam:** they're, they're all surrounding, working with S3 and these 12 functions are about, dealing with files and I'll, group them by what they do or anything. So I try to go back and run like a cleanup pass. We're like, okay, get the code, working, maybe passing tests or whatever.

[00:07:27] **Adam:** And then, with my test passing refactor, not just change refactor, to something that's better. And honestly, that's the whole thing about TDD that I like is that it stops, it introduces this point where normally I would just write the code that I know in my brain, like code just sort of materializes in my brain as I'm thinking about the thing I need to get done.

[00:07:50] **Adam:** And so the easy thing is to just write the code, but doing TDD introduces this point where I go, okay. But I need to do that in a way that's testable. So I might need it to be, it makes me think, okay. But for 90% of the test, I'm going to want this. Function this module to be makeable. So I need to put it over here and write it in this specific way so that it makes it more testable.

[00:08:14] **Adam:** So, yeah.

[00:08:15] **Adam:** does that answer your question?

[00:08:17] **Ben:** Yeah, I think so. I mean, it sounds like even when you're in the one big file, you're still writing stuff. That's decoupled ish, which it feels like it's all, moving towards best practices. So I feel like you're probably still getting a lot of the value of a test driven mentality, even when you don't have the test.

[00:08:36] **Ben:** So don't, I don't mean do down on yourself

[00:08:39] **Adam:** you're not the boss of me.

[00:08:40] **Ben:** also, you know,talk, I brought this up a couple of times, we've talked about Sandy Metz, quite a number of times. And,one of the things that she brings up and I'm fascinated by is this code CATIA, where you have no private functions and that a lot of your private functions can be factored out into other types of objects that you would then inject into the object you're dealing with right now, which it sounds a little bit like you're even recognizing you in your code.

[00:09:05] **Ben:** Like, oh, I have, I mean, private is not so much a thing in JavaScript. but you can imagine, oh, I have these bunch of S3 related functions down at the bottom of my file. Those are more or less private to that module. Right. But you can fax them out and put them into another object. And now I have an S3 object that then gets injected or required into the current file.

[00:09:24] **Ben:** And I dunno, like I'm, that's why I'm so fascinated by this code CATIA, because I can't imagine that it works all the time, but there's so many cases where. The more I work with code, the more I realized like, yeah, that shouldn't be in this file. That should actually be somewhere else because it's clearly its own thing.

[00:09:39] **Ben:** And I can reuse it if it's somewhere else. Anyway, I'm just fascinated

[00:09:43] **Adam:** If that's a conference presentation, you should send me that link and we should include that in the show notes.

[00:09:48] **Ben:** I have a Le it's in a, she has a video of it, but it's part of like a seminar or something. Like it was a recorded seminar, but yeah, it's on YouTube. I'll get you a link

[00:09:58] **Adam:** I would like to watch that. Okay. Let's move on Tim. What's going on, man.

## [00:10:03] Tim's Triumph

[00:10:03] **Tim:** So I've got to try it. So we launched a new product, so we, we deal with, a lot of financial data. So whenever you send nacho, which is the national, account clearing

[00:10:15] **Adam:** Association for cheese on.

[00:10:18] **Tim:** No, no, not Joe,not Joe. It says basically how you send money between banks. Right? So it's basically an electronic check.

[00:10:26] **Tim:** They have a. A requirement that just went into effect a few weeks ago. I think I've talked about this before, but it went into effect a few weeks ago. We were supposed to do some sort of check that the account number is legit. Now. Unfortunately they don't really, they don't provide a database you can hit, so they like kind of leave it to your own devices, but it's basically we subscribed to a database that has like billions of records of like good accounts and bad accounts and things like that.

[00:10:54] **Tim:** And, it was kind of nervous for me launching this because, as I'll talk later in our potluck, I don't really understand functional programming and all this is written in Scala, which, the go, framework, which is all functional programming. And, so me and another teammate, built this to until launch this into.

[00:11:14] **Tim:** And I was like, oh, this is really gonna mess up. And we. And we launched it, you know, worked fine and development where everything worked great. It was making the calls because the calls, the database looks at the account number of the bank. And if it's a good account number, it lets it go through.

[00:11:30] **Tim:** But it doesn't, it stops it. And then we put it up to production and it just first, it just didn't work at all.

[00:11:37] **Carol:** oh

[00:11:37] **Carol:** I mean, oh shoot.

[00:11:39] **Tim:** yeah. oh quick.

[00:11:40] **Carol:** Oh,

[00:11:42] **Tim:** so it could have figured out why, but then I realized, so because we're in a PCI environment, all of our outbound calls have to be, allowed through the firewall. And so we didn't specify.

[00:11:55] **Tim:** So that's why I didn't work. That's the only thing I didn't open the gate to let that call go to this new, destination that we weren't calling before. So open that up. Everything. And just turned it on for our customers that are paying for it. And yeah, it's just chugging along.

[00:12:08] **Tim:** just fantastic. So it's, it's like, I had a lot of trepidation normally on the scholar stuff. I, we use, contractors to do that, but yeah, we did an internally at this time at me and, another programmer and it worked, so

[00:12:20] **Carol:** Yeah, I love that. You're like, I don't understand it. I wrote it. It worked and we're just going to move on. I don't know how this language functions, but that's okay.

[00:12:29] **Tim:** That's okay. Yeah. I just really, yeah, we'll talk about, I'll talk about I'm potluck, but yeah, I definitely need to grok, how, functional programming works. Cause there's like Naria and if statement and I don't get that, there's like zero if statements and the whole code, so

[00:12:43] **Carol:** And a positive note for your it infrastructure team. Your firewall works. Yay.

[00:12:49] **Carol:** yeah. Firewall.

[00:12:52] **Tim:** So that's me. How about you?

## [00:12:53] Carol's Triumph

[00:12:53] **Carol:** Oh, yeah, I'm going to go with the triumph. So this has been my first weekend leadership and it's been exhausting, but it's going really well. everyone seems to be super supportive. I've gotten lots of feedback. Lots of people congratulating me. Lots of, oh. And one of our engineers on the SAS team listens to the show and has been for months and really enjoys it.

[00:13:15] **Carol:** And I was like, oh, that's, that's awesome. He was like, you guys talk about everything in tech that I love hearing about on a podcast. He's like, it's really good. I was like, so awesome. You're my new favorite SAS guy.

[00:13:28] **Tim:** he's kissing up.

[00:13:30] **Carol:** Yeah, it's just, it's going really well. And it's been good to have the support of leadership around me telling me like, here's, what's going on. Here's your new training path. Here's things we need you to accomplish. Here's your goals. Like they're setting us up to succeed in this position. So it's not just been here, feed you to the wolfs, go figure it out.

[00:13:48] **Carol:** There's a lot of support around me. And my team seems to be super supportive of the new structure because who they were reporting to is now my boss. So this person has had direct contact with the team for like 12 years and has been the manager of the team. And then he took over all of engineering.

[00:14:06] **Carol:** So we were worried about the transition a little bit, just because everyone's so close to him and they seem to be super supportive and I love it. Yay.

[00:14:13] **Adam:** did you like going on day one and just like pick the biggest meanest person in the school yard and be like, you're fired.

[00:14:20] **Carol:** So

[00:14:21] **Adam:** Dominic.

[00:14:21] **Carol:** I did not, but we did try down on the day that our promotions were announced with everything going on, that one of our favorite QR QA guys, or SQA team members, bliss, putting in his notice. So I was like, no, you can't do this. Like as we're starting,

[00:14:39] **Tim:** Was it related to the promotion

[00:14:41] **Carol:** no,no, he, no, he had actually put in his notice before that, but it wasn't being announced until closer to his time.

[00:14:47] **Carol:** But yeah, now it's just on, he's been here a long time. Just great. The door will always be open for him to come back. So it's the guy, you know, Ben, Jeff, Miguel,

[00:14:55] **Ben:** I

[00:14:55] **Ben:** have a photo of him, of us together. Just came up on my site the other

[00:15:00] **Carol:** Yeah. He is a great guy. Like I said, it'll all the door will always be open for him to come back. Just ready to put some change. We get there at points.

[00:15:08] **Adam:** Yep.

[00:15:08] **Carol:** So. Who else Who wants to schedule this dinner now? What are we doing? Some potluck I'm hungry.

[00:15:17] **Tim:** I brought the barbecue ribs.

[00:15:19] **Adam:** I'm doing the liquid diet for this week.

## [00:15:21] Ben: Getting Into Docker

[00:15:21] **Ben:** I guess I'll kick it off. Yeah.

[00:15:24] **Carol:** Yeah.

[00:15:25] **Ben:** So towards the beginning of the year, and depending on when you're listening to this, that's the year 2022. I talked about my big goals for the year technologically speaking. And what I really want to do is get to a point where I can build a Docker container and have it get deployed somewhere as a Docker container.

[00:15:43] **Ben:** like as an image that gets pulled down somewhere. Cause right. I do that at work, but someone else built it. So I just use a chat bot to trigger it and code ship does stuff. That's magic that I don't understand. And in my personal stuff, I still just FTP files to the server. So I need to get, yeah, I need to get from one extreme to the other.

[00:16:02] **Ben:** In an effort to learn about Docker. What I needed to do is have a project that I'm learning with. And my problem now is that I'm vacillating sat word between the simple idea that I could probably do, but may never actually use.

[00:16:19] **Ben:** And the much more complicated idea that feels like it might be way too complicated, but it's something that I might actually use every day if I were to build it. So on the simple side, I have this website that currently runs on Netlify as a client side, only application it's for writing poems. I don't even know what the server side component of it would be because I want to, ultimately I want to be able to build a Lucee CFML container because that's what I'd like to do to build server side apps.

[00:16:50] **Ben:** So I feel like maybe I could add user management. There's no user management today. It's just clients. And it stores in your local storage.

[00:16:57] **Adam:** what's your experience level with building a Lucy CFML servers outside of Docker? Like, are you comfortable starting with like, install the Java stuff, hook it up to Tom cat or whatever it is

[00:17:08] **Ben:** II'll be honest. I'm like, I don't even, I don't even have a good understanding of whether or not I have to have Java installed. I mean, I know everything in ColdFusion runs on Java, but I'll go to the installer page and you can get stores with them without Java as embedded. I'm like, I don't even, yeah.

[00:17:26] **Ben:** I'm like that. Does that mean it can run without Java or is there a way to run it where Java is somehow magically on the machine already and

[00:17:34] **Ben:** doesn't have

[00:17:34] **Adam:** Bring your own Java.

[00:17:36] **Ben:** So I like, I don't even understand it at that level. ultimately I would just use some hopefully official Lucy image that at least makes that decision.

[00:17:46] **Adam:** Sure. Yeah. Yeah. Well, I mean, at that point, it's just create the, great a Docker file that is based on the Lucy image and then copy your files into it and boom, you have a CFML server.

[00:17:57]

[00:17:58] **Adam:**

[00:17:58] **Carol:** Magic.

[00:17:59] **Adam:** if you want to do that's probably the easiest on-ramp, but I was going to say like start with, if you're, if you want a small win to, to propel yourself, give you that momentum to keep going, start with something, that's going to be a little easier to get going.

[00:18:13] **Adam:** Like.

[00:18:14] **Ben:** yeah.

[00:18:14] **Adam:** I don't know what other, tools and languages you're familiar with, but for me that would be like node or maybe Python. I really don't like writing Python code. That's just a personal preference, but I'm comfortable with starting up, a Python script and installing the executable sinned stuff.

[00:18:29] **Ben:** So you're saying that my first deploy a Docker container shouldn't even be ColdFusion should be something even lighter weight

[00:18:36] **Ben:** and

[00:18:37] **Adam:** Um, I'm saying if you've never used a hammer to drive a nail before don't pick building a house as your first project,

[00:18:45] **Ben:** I know that's the thing that I keep, keep going back and forth on. Cause so th the opposite end of the spectrum would be I've. I've had this love affair with wanting to build a fitness app for the longest time. And it's because I do fitness. And today I just record all my stuff in the notes app that comes with my Mac or my iPhone, I should say.

[00:19:05] **Adam:** it's a, a quite a coincidence. I do unfit.

[00:19:10] **Carol:** And take no notes.

[00:19:11] **Ben:** and, it's, I have a separate note file for each exercise. And then all I do is I start, my new sets at the top, and I can look at what I did at the bottom. and,I'm just dying to build something that would record that for me and sync it across devices. that's not in a notes app and I think I can make it actually really cool, but then I start to rabbit hole, cause I'm like, well, if it's going to.

[00:19:31] **Ben:** On a mobile device, then I'd love it to potentially operate without a network connection, at least temporarily. But then I'm going to have data drift between what's maybe locally in the phone memory versus on the server.

[00:19:44] **Adam:** Yep. Two-way sync is a

[00:19:45] **Adam:** huge

[00:19:47] **Ben:** So, and I don't want to have to start to get involved with something like couch DB, which is, I think designed very much for this very specific kind of thing.

[00:19:54] **Ben:** Like I really just want to have a relational database, my, MySQL, and I'm pretty sure there are no real tools that exist for a relational database. Yeah. Like everything is document based for the two-way thing. And then I think when I said, well, maybe could I do it like just enough to kind of get stuff done where maybe, every time the phone goes to safety, It will save it locally first and then try to save it also to the server.

[00:20:18] **Ben:** And if it doesn't save to the server, maybe it keeps like a cache of it locally. And then when it can connect, it just pushes all the unsaved stuff to the server and then pulls down all of the data that it should own as the user, because I don't want to have to worry about data reconciliation. I'm very happy with last writer wins kind of a scenario for this kind of thing. So I almost wonder if I could somehow keep it simple where it's just, I sync up and then I sink down and the sink is very loosely. It's basically like I sync up and then I pull everything down, potentially overriding everything that I have locally, but if I did just a sync up, then it shouldn't matter.

[00:20:53] **Ben:** And because it's a fitness app, it's just. it's not like it's going to be gigs of data. It's maybe in the tens of megabytes of data, even if I had to pull everything down, I don't know some, but now it's like, now I'm so focused on something that has nothing to do with Docker at all. Right?

[00:21:08] **Ben:** Like, none of that is necessarily just how do I build a container and deploy to production?

[00:21:13] **Carol:** You should look at J fit by the way, you should go check out the app because it's really cool with how it records everything and how it logs it. So if you're wanting something to think about when you're designing this is a really, when you're designing it, if you go this route, this is a really cool.

[00:21:26] **Ben:** I've heard of a, I know a lot of people have recommended my fitness pal, I think has a very popular

[00:21:32] **Ben:** one

[00:21:32] **Carol:** one to you. Yep. I, so I like J fit because it does reps for me and we'll do countdown. So like when I'm planking and they'll be like, oh, hold you playing for 60 seconds. That does the count down. And it's like flip over, do side planks. And it does my whole clock for me. And it like tells me, okay, take a 32nd break.

[00:21:50] **Carol:** Now start the next.

[00:21:51] **Tim:** Hi, Jay fit because I never actually use it and just do

[00:21:55] **Carol:** Yeah. Yeah.

[00:21:58] **Tim:** I don't exercise. I just started myself.

[00:22:01] **Carol:** And it's also like 50 bucks a year to buy it there. Apple. So

[00:22:06] **Ben:** that's pretty expensive. Although, I

[00:22:07] **Ben:** guess,

[00:22:08] **Carol:** now if you think about how much it costs each month.

[00:22:10] **Carol:** yeah.

[00:22:11] **Tim:** each day it's even cheaper that way.

[00:22:14] **Adam:** Well, I mean, if he, I guess it depends on what it is replacing, right? So if it replaces the need to have like a personal trainer that you're meeting with every month, $50 a year as well worth it.

[00:22:24] **Carol:** Oh

[00:22:24] **Carol:** yeah. Cause

[00:22:25] **Carol:** you can,

[00:22:26] **Ben:** thing

[00:22:27] **Carol:** oh yeah. There's tons of plans.

[00:22:29] **Ben:** I'm so used to thinking about like one time purchases in the app store,

[00:22:32] **Carol:** Yeah. No, everything's subscription based now. Everything's a

[00:22:35] **Carol:** S like a service. Oh

[00:22:36] **Carol:** yeah. It's

[00:22:37] **Carol:** like

[00:22:37] **Carol:** monthly,

[00:22:38] **Ben:** I have so few apps I have, like, I have one screen, my home screen of apps, which is my high priority apps. Those are the things I use mostly every day. And then I have a second screen, which is mostly just a couple of folders of group things and that's it. And I can't stand having more than two screens.

[00:22:54] **Ben:** I watch my wife sometimes she'll try to get to her settings page. And first of all, it drives me crazy that she just doesn't like swipe down from the top, right. To get to some of her settings. Yeah. Like Kara and I'm watching her and she's, she's swiping, swiping, swiping, swiping. I'm like,what are you, what do you have on your phone?

[00:23:10] **Ben:** crazy.

[00:23:11] **Carol:** sometimes I can't find things. So I just swiped down a search. I'm like Gmail, I don't know where the app is now it's moved. I give up.

[00:23:18] **Ben:** It's not in your home screen, but

[00:23:21] **Tim:** She's the

[00:23:22] **Tim:** search

[00:23:22] **Adam:** Okay. And you

[00:23:23] **Adam:** don't reply to

[00:23:24] **Adam:** email anyway. You just need to be able to read it.

[00:23:29] **Carol:** So, yeah, I think creating a fitness app would be really cool for

[00:23:33] **Carol:** you. And I think it would be good to learn with, but it's not going to get you to your Docker point sooner. Right. It's going to get you to designing software and you're not going to be thinking about the and release or how you're going to be using Docker for it.

[00:23:46] **Carol:** You're going to be thinking about your code upfront. Right?

[00:23:49] **Ben:** but my concern is if it's not something that I'm going to be more excited about it am my ever going to do it right. if it's just a simple, how do I build a Docker container? Cause I could theoretically start off the fitness app by doing just the hello world. I built a container and it says welcome to my container. of a thing,

[00:24:10] **Carol:** Got to put the muscle there with it or something,

[00:24:13] **Adam:** Yeah. Well, fortunately,

[00:24:14] **Adam:** there's an

[00:24:14] **Adam:** emoji. right there. Ready for.

[00:24:16] **Adam:** So if the goal is to learn how to build Docker containers and maybe like deploy them or something, I mean, let me start with this. Whatever you can use to motivate yourself to follow through is what is the best choice, right.

[00:24:32] **Ben:** yeah, yeah,

[00:24:32] **Carol:** Yeah.

[00:24:33] **Adam:** but in terms of not getting lost in the weeds of like, okay, I wanna, I want to learn a thing.

[00:24:38] **Adam:** So I'm going to go spend three months building something completely that I could do completely without Docker so that I can throw it in a Docker container. If the goal is to just get your feet wet and get it done and over with so that you may be like, okay, now, like I understand what I don't know about this, so I can go and learn the rest.

[00:24:54] **Ben:** take an app that you already have and put it in a container and deploy it on Google cloud or Amazon or what. worst case scenario, you spend like 30 bucks for a month to throw it up there and,you go, okay, now I know that, and you can just turn it off and delete it. And, now, you know,Yeah, that's

[00:25:11] **Adam:** take your blog.

[00:25:12] **Adam:** Did I say that already?

[00:25:13] **Carol:** I don't think you

[00:25:14] **Carol:** did,

[00:25:14] **Ben:** think

[00:25:15] **Adam:** Yeah. So take your blog engine and just put it up in a container and deploy it and

[00:25:19] **Ben:** I don't know. For some reason I was just like, doesn't excite me. I

[00:25:22] **Adam:** exactly which is yeah.

[00:25:25] **Carol:** which is what Adam said. You're going to have to find something that excites you and do it with that because otherwise you're never going to do it.

[00:25:31] **Ben:** Yeah. And now I'm just so worried that, I'm, hand-wringing over it so much that I'm not gonna start at all. And that's my

[00:25:38] **Carol:** Yup.

[00:25:38] **Ben:** concern.

[00:25:39] **Adam:** Yep.

[00:25:40] **Adam:** Don is better than perfect.

[00:25:41] **Ben:** yeah. A hundred percent. anyway, so that's, what's been weighing on my mind a lot lately. mostly also I've been feeling so out of touch with the angular community, or I should say I've been feeling mostly out of touch with the front end community that I feel like I need to do something that flexes some of the front end technology again, especially, nothing against react, but react 18 just came out.

[00:26:02] **Ben:** and like, I don't know most of the podcasts that I listened to. They're very pro react, which again, nothing against react, but I'm just, I'm an angular fan boy.

[00:26:11] **Ben:** And

[00:26:11] **Adam:** against breathing. I'm just,

[00:26:15] **Carol:** What,

[00:26:15] **Carol:** what was it? Tim said, some of my best friends were react. Developers.

[00:26:19] **Adam:** yeah.

[00:26:20] **Ben:** We got, I remember that. That was hilarious, all right. I don't, I've got nowhere else to go with this. That's my that's the,

[00:26:26] **Adam:** You want to move on? Okay. We can move on.

[00:26:29] **Carol:** Well, I'm glad you got it off your chest.

[00:26:30] **Ben:** Thank you.

[00:26:31] **Carol:** Yeah.

## [00:26:32] Adam: Getting Out Of A Funk

[00:26:32] **Adam:** So I mentioned,just kind of been, not feeling it this week, in my fail for the, for this week's podcast. and I guess my topic would be like, what do you do when you're in a funk, right on paper, the project that I'm working on, I should be really enthusiastic about it checks a lot of boxes for me, but at the same time, I'm just finding myself incredibly distractible and at times incredibly distracted. and I just, I can't force myself to pull myself out of this funk. So you guys can see me right now. I'm sitting on a stool and I switched from my chair to a stool in hopes that it would help my posture help my back pain. And, there's a whole thing there, but. It's effort, right? It takes additional mental and physical effort to focus on sitting on the stool properly.

[00:27:17] **Adam:** And there have been times Mo maybe half of this week. I have not been sitting at my desk. I've just taken my laptop and I've gone down to the couch in the living room, or there's a sofa in my office here. I'll go sit on that.

[00:27:31] **Carol:** Is that normal for you?

[00:27:33] **Adam:** know no, when I had the chair, I was fairly content to be sitting at now, like when the weather's real nice, I'll go sit out on the deck or something like that.

[00:27:40] **Adam:** But you know, all other things being equal, I'm perfectly content to sit at my desk all day. but I noticed that like, I would get into this point where it's like, I can't even think, right. I'm just, I'm consumed to the point where I have to give up something in order to be able to get something done.

[00:27:55] **Adam:** And so I'll go and I'll sit somewhere else and let my back relax,to free up that mental bandwidth to be able to get something done. And I don't think that's causing the funk, but I just feel like. I don't know. I don't know what to do anymore.

[00:28:10] **Carol:** So one thing that I've noticed is when I do make a big change, I can't change multiple things at once. I only need one change going on and it can't overlap because I can't commit to that many. Like I can't start eating healthy and going to the gym and cut out alcohol all in the same week. Not going to happen.

[00:28:28] **Carol:** Only one of them is going to happen. So I'm like, all right, I'm eating healthy right now. But if I don't go to the gym, I'm not gonna beat myself up. If I have a drink, I'm not going to be mad. Like, it's fine. I'll get to where I'm, eating better working out and then cut out drinking completely.

[00:28:42] **Carol:** Cause it just makes you fat. And I've got to quit drinking because I don't want to be fat. So the whole thing

[00:28:46] **Carol:** anyways, that's what was happening here. So I feel like if you are trying to launch this new project or even if you're having to spend time working on this new for it, and you're probably spending time, like in analysis and research, and you're also trying to adjust how you're functioning in your day.

[00:29:07] **Carol:** It may be too much for you all at once. It's going to sound silly, but consider using your chair half the day so that your body gets a break and you're not taking on so much change all at once. And you're able to focus in on the other thing, rather than the, I need to move. I need to address and fidgety in this chair because I can be fidgety.

[00:29:28] **Carol:** And that's my problem. If I can move, I do move. If I kind of lock myself in, then I start fidgeting and I'm able to kind of focus in better.

[00:29:37] **Adam:** Yeah. I mean, I see your point and I agree, but at the same time, like my job is to work on something new every day or every week or whatever. So You know what I mean? am I communicating that? Well,

[00:29:49] **Ben:** I just a point of clarity, the project that you're working on, is it a personal project or it's for work?

[00:29:54] **Adam:** no, this is for work. So yeah, it, and it's, there was this big initiative that I started, trying to be the squeaky wheel about, I don't know, five years ago. and finally about a year ago we started making, it was probably more than five years ago, but finally about a year ago, we started to like, okay, we're gonna, w we're doing it.

[00:30:12] **Adam:** You have the time to start working on this and that. and before that, it was just like, yeah, we agree. We need to do that, but not yet. and then it was now, and pretty much everything that I've worked on is the day the fire that comes up, something's gotta be dealt with.

[00:30:25] **Adam:** all of my project work has been toward that initiative ever since we started that about a year. And maybe it's fatigue on that whole thing too. but, and it's all little things, right? It's like one of the goals of this initiative is to take our monolith, and move it So right now it's, it's pets, not cattle, right?

[00:30:46] **Adam:** It's a, we've got names, easy to servers and they are manually click ops dealt with, and we're moving in the distant future. It will be, you merge a commit and that create, that causes a build to happen, which causes a deploy to happen, which might cause scaling and blue-green deployments.

[00:31:02] **Adam:** And who knows what, but,we're early on in that path. And so a lot of the mini projects I've been biting off are things that like hurdles, we have to clear so that we can get further down that path.

[00:31:12] **Carol:** right.

[00:31:13] **Adam:** And so like it was saying it, it checks all the boxes for me, these are more, I'm using technologies that I like I'm working on a project that I really truly believe in.

[00:31:21] **Adam:** sounds like you're getting the learn lots.

[00:31:23] **Adam:** I am, right. So this is the first project I've ever gotten to use, message queuing on. So we're using SQS,and it's like at the risk of over-complicating, it's actually fairly complex and it's going to take something that's currently a bottleneck for us and like rearchitect it in a way that's potentially hugely scalable.

[00:31:42] **Adam:** as we continue to sign on more customers, this was going to be a big problem for us. So it's taking a problem and turning it into an opportunity. so like I said, it, it checks all the boxes. This should be something I'm excited to work on. And yet,

[00:31:55] **Carol:** distracted.

[00:31:57] **Ben:** I think maybe when you introduced it, I was a little bit confused or maybe I had just had a preconceived notion. This is not a project that you are just starting. You're saying you've been already working on this for like a year.

[00:32:08] **Adam:** well, yeah, I don't,I don't know JIRA to use the JIRA terms, but I'm starting to think of that. It's like an epic versus project versus ticket sort of thing.

[00:32:16] **Carol:** So what would you call this?

[00:32:17] **Adam:** yeah, I mean this particular project I would say is probably like in those three epic project ticket, I would say it's like the project level.

[00:32:25] **Adam:** Right. So that if the epic is,modernize our infrastructure, then the, this particular

[00:32:31] **Ben:** a big

[00:32:32] **Adam:** is, yeah,

[00:32:33] **Carol:** Yeah, this huge

[00:32:34] **Ben:** oh, just modernize your infrastructure.

[00:32:37] **Carol:** five points, please.

[00:32:39] **Adam:** I don't know a JIRA. We don't use that, but,

[00:32:42] **Ben:** What's

[00:32:42] **Ben:** the

[00:32:42] **Ben:** t-shirt size on that.

[00:32:44] **Carol:** Yeah, it goes epic story ticket. So your epic is like the big over holds it on and then you have your stories that break it out and then each story can have the tickets that are assigned to it. Like these are the actual work items for it.

[00:32:59] **Adam:** story is like, as a user, I expect that when I do that. Okay. Yeah. So this is definitely epic or above. I don't know what would be

[00:33:07] **Carol:** Big.

[00:33:07] **Adam:** but

[00:33:08] **Ben:** I

[00:33:08] **Ben:** think a project is,

[00:33:09] **Ben:** well, there's the board, there's your board itself? Which

[00:33:12] **Ben:** I think,

[00:33:13] **Tim:** let's all pray.

[00:33:14] **Carol:** well, we have, but I feel like modernizing a platform couldYeah. Agreed. That could totally be a project.

[00:33:20] **Adam:** we're really going into the weeds on JIRA

[00:33:21] **Carol:** Sorry. I'm so sorry. You guys

[00:33:23] **Adam:** It's okay.

[00:33:24] **Ben:**

[00:33:24] **Carol:** that was because they say you're just starting this new part of this big over

[00:33:29] **Carol:** overall

[00:33:30] **Adam:** So this is what this is it's the smallest possible change that I can make that is. a thing that can be deployed and improve the product by itself, but that's a big thing, right? So this whole project is, we have a bunch of customers and every night, all of our customers, basically give us a copy of their entire database of all their constituents.

[00:33:53] **Adam:** This is schools that we're talking about. So all their alumni and everything, and they basically generate a bunch of CSV files and they put them on S3 for us. And then they call our API early in the morning to say, okay, the files are there. You can go consume them and pull them in. And we have a, we pull in a copy of their data so that we can do the segmentation and all that stuff.

[00:34:09] **Adam:** doing that through the old app server,like in process in the monolith was problematic. And, there were issues where, so we have right now we just have two database clusters. and so. If all of the customers on one of those clusters decided to sync their files all at the same time, then the app servers for those different customers are totally unaware of each other.

[00:34:31] **Adam:** So if they all tried to run big import jobs at the same time, it would probably crash the database sort of thing. So that's why like queuing is one of the big factors of this, right? So all the jobs now get queued and they get processed in serial.

[00:34:45] **Carol:** yeah. In order. Yep.

[00:34:46] **Adam:** Yeah. and async right, you, instead of run the file and then you wait 30 minutes and you get a response, this is okay, the file was imported.

[00:34:53] **Adam:** Now it's going to be run the file and you get a response back within 30 milliseconds that says, okay, we'll do that. And we'll let you know. and,

[00:34:59] **Carol:** So sexy. I

[00:35:00] **Adam:** yeah, and I mean, this whole thing, right? So it used to be. They make the request and then we go, okay, thanks. And we'll go, we go download the file to the app server from S3.

[00:35:10] **Adam:** And then we run validations against that file to CSV. And we know, okay, these are, this is what the columns are supposed to be. So let's look at the first line of this

[00:35:16] **Adam:** two gig file.

[00:35:17] **Adam:** and D are the, isn't the right columns, the right number of columns in the right order, all of that. and a whole bunch of validation.

[00:35:23] **Adam:** Some of them will even read like every line and validate certain things about every line in the file. And then if it passes all the validations, then we have to import that into the database, which is a whole thing. And then sometimes for one or two of the jobs, there's like, okay, well now that table exists.

[00:35:36] **Adam:** We need to like all these, tables that we generate based on their table. We have to regenerate all of our tables.

[00:35:42] **Adam:** and so this, it just spirals out of control really fast. and so, it's just a, it's a really complicated thing. And so it's not one of those things where like, I can just change some tiny little portion of it and deploy that. Changing the modality of the way this entire piece of the system works. So it's like, I'm trying to do the minimum thing.

[00:36:02] **Adam:** That's not going to disrupt anybody,

[00:36:04] **Carol:** And that's a smart way to do it. yeah.

[00:36:06] **Carol:** it's a great.

[00:36:07] **Adam:** So, but at the same time, it's been two weeks and I'm looking at least another week of work to get it all done

[00:36:16] **Adam:** yeah.

[00:36:17] **Carol:** wait, Ican I piggyback on you because I think ours play together. Like I think they kind of go well and let's see if they do

[00:36:24] **Carol:** actually.

## [00:36:25] Carol: Analysis Paralysis

[00:36:25] **Carol:** So I am on this project. That's basically changing how our systems communicate and how our users communicate. And I am 100% and like analysis paralysis right now.

[00:36:36] **Carol:** I am so done researching things. I'm tired of looking at new stuff. I just want to make a decision and write some code and let's move on. And instead, like I've written a CS, I've written stories. I've read the tech doc. I've went back to the tear sheet, updated the tear sheet today. I helped the project manager update slides.

[00:36:54] **Carol:** So she can now present this project to leadership, to like our executive board to go over what we're wanting to do. I just really done researching. I want to write code and all I keep thinking is I really want Ben's backlog. Like right now I would be so happy if I had bins, backlog sitting there because I could pick up something tiny.

[00:37:16] **Carol:** That's just a random go fix it. And yeah, a little win and feel good about myself instead. I'm going, I'm so tired of reading new things and trying to figure out other approaches for this. Can we just make a decision? Like I've made a suggestion, let's just put it out there and see what happens. And most of tech agrees like, okay, we're to a point where we should start coding.

[00:37:35] **Carol:** We know you guys, aren't going to have all your meetings, so the 18th, but we're going to go ahead and start coding. Cause while we're done and I can't pick up any more stories because I really don't have a week to work on something. I need to have some code in when we start. I'm just over the analysis side of stuff to the point where today, I didn't really get a lot done between meetings and just not wanting to research anything else.

[00:37:58] **Carol:** I just did not want to research anymore. I love it. But today I was done with it. And I don't know if that's where you're at, that you just need some small wins, but that's how I felt today. I realized I really needed something like Ben's backlog. And if you guys haven't heard Ben talk about it, Ben has a pretty, pretty big backlog of just small things that you can pick up and work and get your wins out.

[00:38:20] **Carol:** Right. And I don't have that. And I feel like I just need some wins to keep myself motivated.

[00:38:27] **Carol:** So

[00:38:28] **Adam:** Yeah. I mean, I think that you're right. There is a lot of overlap here between our two topics. sometimes when you were talking, it made me think, like, I wonder if like, as a, sort of a next career, when I get too old and have to be put out to pasture and I can't keep up with the kids

[00:38:42] **Adam:** in technology anymore. Right. I wonder if instead of management, if I should do like technical writing, cause I can type like And I love if there's one thing that I like more than the sound of my own voice. It is an email that I wrote that took me four hours to write. Right. Like I'm the type of guy that listens to my own podcast.

[00:39:00] **Adam:** I'm also the type of guy that reads the email that I haven't sent yet four times just to make sure it sounds right. And it's all good and clear.

[00:39:09] **Tim:** And then rejected by 25%.

[00:39:10] **Carol:** as a subscriber to your newsletter, I can confirm you do write a lot

[00:39:17] **Adam:** Just not

[00:39:18] **Adam:** often enough, I guess. Yeah.

[00:39:20] **Ben:** Is there a way that you can take the process that you have today and just like break the steps down so

[00:39:29] **Ben:** that

[00:39:29] **Ben:** you're, it's still doing

[00:39:31] **Carol:** Peninnah Dockery day, or give it to Ben to the employee.

[00:39:34] **Ben:** so it's still doing the exact same thing, but it's put it somehow in, in like little more reusable chunks that can somehow then in the future, be that kind of tied into message queuing, like something that doesn't fundamentally change.

[00:39:48] **Ben:** The thing that breaks it up.

[00:39:50] **Adam:** yeah. I mean, so I guess one thing that I didn't mention. In the current state of things is that some of our customers have so much data and it requires so much processing power and so much time to get through it, all that, not just for this particular job, but, because of this and all of the other scheduled jobs that have to go on for them.

[00:40:10] **Adam:** we have dedicated job processing boxes for certain customers, right? So if you're Bob's university with a alumni, a total lifetime alumni count of a hundred thousand, then it doesn't matter. But for some of our bigger customers that have like half a million alumni, then know, we have a server that is for all intents and purposes, a production server, but no public processes ever hit it.

[00:40:37] **Adam:** Right. It's only ever doing background jobs processing for this type of stuff. we could. I guess maybe the thought is we already did that. Right. That, that jobs box is kind of that thought. Yeah.

[00:40:48] **Ben:** It's so interesting. So are they, I, it, I assume that the dump of data that you're getting is a sort of a subset of what they have on their end.

[00:40:56] **Adam:** Yes. So they don't just like, okay, here's our whole database and export to CSV. they select it because I guess there's, laws about the kink give us active student data. and they try to limit it to only the things that are going to be useful and interesting to them within our system. Right. So if there's a particular audience, let's just say, if they've decided as a company or as a school that they're never going to try to contact anybody over the age of 80, then they would exclude all people over the age of 80 the data that they

[00:41:27] **Ben:** Gotcha. So they get to do some curating on their end before they

[00:41:30] **Adam:** Sorry, Ben or Tim. Didn't mean to be ageist towards you? octogenarians,

[00:41:36] **Ben:** Come on Tim, you still got a couple of years left

[00:41:38] **Tim:** Yeah, for sure.

[00:41:39] **Adam:** sat word. yeah.

[00:41:40] **Ben:** and I assume you're it. So do you have to basically reconcile? So they give you the data. What happens if, for example, you have an alumni record in your end that doesn't show up in one of these data dumps, do you have to then remove it from your database?

[00:41:54] **Adam:** Well, yes and no. what they're giving us is the source of truth. so when we, when they, when something gets updated in our system, we send that to them. and we have, w we'll keep like transactional records and we, they can pull those at any time unrelated to data sync. but yeah, I mean, if a record gets deleted from their warehouse, then the next day should be gone from ours

[00:42:15] **Ben:** Gotcha.

[00:42:15] **Carol:** you may have said this, but how often do data things happen

[00:42:18] **Adam:** Every morning,

[00:42:20] **Adam:** like six o'clock in the morning. yeah. and actually the way that we accomplish that, and maybe that'll make it a little bit clearer is, so when we do this import, we basically, if the table name is warehouse, we do like create a table name, but warehouse underscore new and import all the data and do all the checks and make sure everything's happy hunky Dory.

[00:42:37] **Adam:** And then when we're ready to make the switch, we have a transaction that's like, okay, begin transaction, drop table warehouse, renamed table warehouse, new to warehouse and

[00:42:45] **Adam:** transaction.

[00:42:48] **Ben:** That's awesome. So,

[00:42:49] **Ben:** as far as what would go in the message queue, what would you be breaking the data files up into individual rows and then each row becomes a message or you're like a, a university would become a message

[00:43:04] **Adam:** so the messages like, for the production environment for Bob's university, they will, they're ready to run this particular sank, right? the main warehouse file versus maybe the degree's warehouse file or those, the sport data or whatever. so it'll be like, Bob's university production warehouse, and here's the file name that they said is on S3 for us.

[00:43:25] **Adam:** And then we added grid just to make it unique.

[00:43:28] **Ben:** yeah.

[00:43:28] **Ben:** Dana data is a tough problem.

[00:43:30] **Adam:** Yeah. So it's funny because like we're trying to solve scaling challenges, which again, checks another box for me. Right. This is interesting work, it's not just write another web form. but it's a company of five total people, three full-time developers. And we're solving these really difficult challenges.

[00:43:47] **Adam:** And there's like, not a day goes by that it's that there's not five new things that are like, okay, you need to have this on your radar because it's going to be a thing that we're going to have to deal with. Eventually, like this morning it was, our design is not fresh enough and we're going to end up having to like hire a designer to, because people were getting to the point now

[00:44:05] **Adam:** where people are starting to care more about how it looks and how it makes them feel than how good it does its job.

[00:44:12] **Ben:** frustrates me so much. I mean, in a good way, like I wish I had better design abilities because I know how important.

[00:44:20] **Adam:** yeah. Yeah. And it's tough because like, you designed something and it's totally functional and it's good enough. And then five years goes by and it's like, well, but it's not bad. It's just a little, teeny, tiny bit dated.

[00:44:34] **Carol:** do you guys know what Figma is?

[00:44:37] **Adam:** of it.

[00:44:38] **Carol:** Okay. So we use that at work. We use Figma to create, what the screen should look like and stuff. And as part of like this project that we're working on, there is a design team.

[00:44:49] **Tim:** It's like a wireframe

[00:44:50] **Carol:** Yeah. Yeah. There's a design team. That's sending over they were on the call today, show this a screenshots of everything they wanted to do.

[00:44:56] **Carol:** And I was like, oh, this looks great. Good job. So then we get to the end of it. And we're talking about when we might actually be able to start writing code. And I was like, wait, I'm a little confused. So are we coding these interfaces? And they're like, yeah, we just give you the screenshots. You make it happen.

[00:45:11] **Carol:** I was like, no, you're getting boxes. I'm not doing that. I hate doing front end design.

[00:45:18] **Adam:** That's my thing is like, I used to be exactly like that. Right. Like I, I can do squares and rectangles

[00:45:25] **Carol:** Sometimes you can get, sometimes you can get a border if you're lucky.

[00:45:28] **Adam:** border radius even. Yeah. But like over the years, mostly I've been out of necessity. I have gotten halfway decent at CSS. I can, work my way through a grid and Flexbox, and this and that.

[00:45:41] **Adam:** And it's a little bit of a point of pride for me. But at the same time, like starting from scratch and making quote unquote, a good design, that is not something.

[00:45:50] **Carol:**

[00:45:50] **Adam:** yeah,

[00:45:50] **Carol:** do it.

[00:45:51] **Carol:** Nope. I literally searched when this demo was starting to go through it. I was like on Google I'm like accordion, expand inside accordion, expand and then went to stack overflow copied and pasted it in. I was like, I'm not going to figure out how to get this to expand inside another one.

[00:46:07] **Carol:** I was like, whatever, it'll do its thing. And it

[00:46:10] **Tim:** Yeah. I just send to the artsy fartsy people

[00:46:12] **Carol:** Yep. Well, our artsy-fartsy people sent it back and said, we're coding it now that they designed it. And I was like, wait a minute. Where did this happen? No.

[00:46:23] **Adam:** The real challenge. when we get around to that design task is going to be, we need a fresh design. That's not going to be a nightmare to put on top of our existing functionality. Right. Maintain the same functionality, just clean it up.

[00:46:38] **Adam:** And that's going

[00:46:39] **Ben:** go crazy.

[00:46:40] **Adam:** yeah. You want to move stuff around on the screen?

[00:46:42] **Adam:** That's fine. You want to like change what's on what screen?

[00:46:45] **Adam:** No.

[00:46:47] **Carol:** Well, I think that's mine. My Adams we're wrapped up.

[00:46:50] **Adam:** so it just leaves Tim.

[00:46:52] **Carol:** Yeah. I always went together. So we stood it.

## [00:46:55] Tim: Functional Programming

[00:46:55] **Tim:** Okay, cool. So I feel like the person at the potluck who brings the. Plastic cups and paper plates. I don't really have a whole lot here. So mine is, I just don't understand functional programming.

[00:47:11] **Ben:** Yeah, I,

[00:47:12] **Tim:** it just, it just, it breaks my mind. So like there's no, if statements, I mean, you can do, but there's typically you don't do any it's matching and,mapping and yeah, just it, the parallel is a model.

[00:47:29] **Tim:** I just don't get it. So I'm really need to find a simple way to understand and functional programming because I just don't get it. I don't, if you guys had any experience with it.

[00:47:39] **Adam:** I've never used a,a true functional language. and I'm probably gonna get this wrong. So I'm throwing myself under the bus here. I beat you to it, but like, I think closure might be one. Okay. and it was, I've never used any of those languages, but I have tried as much as possible to embrace the functional style in JavaScript.

[00:48:00] **Adam:** And I love it.

[00:48:01] **Tim:** I mean, everything I've ever done. I saw, I mean, I started like at 12 years of age working on basic. Right. So it's all it functions and go do things. It's all procedural

[00:48:11] **Adam:** You're of our Lord 1900.

[00:48:13] **Tim:** exactly.yeah. Way back when. And so it's like just wrapping my mind around it. And I just realized that, when we're dealing with this deploy is like, I'm looking at reviewing this code and looking at it.

[00:48:25] **Tim:** I'm like, I don't know if this is going to work, but I'm going to post it any way. It does matter. So I got to get better at that. pretty

[00:48:33] **Adam:** I mean, what's your,what's your motivation?

[00:48:35] **Tim:** I mean, pretty much it runs our business. Right.

[00:48:38] **Tim:** So yeah, I got to learn it. So I got to learn it's in Scala. and the. Uh, framework, but yeah, I just got to wrap my head around it.

[00:48:47] **Tim:** So a couple of our developers they've kind of wrapped their heads around it. I don't think they're completely proficient on it as well, because it's like the idea of a whole not having any, if statements just blows my mind. I don't know how I gotta wrap my head around that. So any of our listeners who like are proficient on that just hit me

[00:49:08] **Adam:** There's gotta be like a good book or something functional programming for imperative programmers.

[00:49:14] **Tim:** Yeah, exactly. And it looks like everything's like immutable, so like all the, everything is mutable and parallelism, so yeah. So

[00:49:22] **Carol:** It's immutable and

[00:49:24] **Carol:** immuno.

[00:49:25] **Carol:** Yeah.

[00:49:25] **Carol:** yeah. yeah. You,

[00:49:27] **Carol:** you flip. Yeah. You flipped it.

[00:49:28] **Carol:** Yeah. We're immutable. You're immutable.

[00:49:32] **Adam:** Which I remember the first time I heard about immutable data, it just, it was like a brick sitting in my mind. I'm like, does not compute how applications are about changing data. How do you have immutable data? Because mute is like mutate change. How do you have to changed data that's unchangeable.

[00:49:52] **Adam:** So for anybody out there that is going through that exact same brain fog that I was basically it's you don't change the bucket of memory that contains the value of the variable. You create a new bucket and where possible you can have pointers back to the old bucket so that it uses less memory, but whatever changes is only changed in the new.

[00:50:12] **Tim:** Yeah, but what amazed me though, was scholars, like everything has run so fast. I so incredibly quick. And there's nothing is blocking, right? So everything's like running on different threads and parallelism. It just, it's just amazingly fast. So, I mean, I get the benefit of it, but it's like, I totally don't understand it.

[00:50:31] **Tim:** And this whole deploy that we did recently, it's like, I was so worried that was gonna crash because I didn't understand what was going up. I reviewed it. It's like, no, it looks good to me, but I didn't know what I was looking at. So I got to get better. But on the other side, I do love when we come to ColdFusion, I do love using jars. Like, I mean, taking a jar in and like importing that in and do stuff. So like we had an issue where I needed to take some XML that we were receiving and convert a Jason There was some ways to do that in code, but actually the best way to do it, the fastest way to do it was with the jar is I just love like getting a jar and pouring it in looking all the functions, figuring what they do and then just using it. so much more elegant than, I don't know how to write Java, so

[00:51:26] **Adam:** Yeah, can I go back to my thing briefly? You were talking about stuff being fast and it reminds me. So it's talking about, sometimes we validate these files and they're huge files and, it's a problem in the current app server because it doesn't have the ability to, like, I guess it does have the ability to like, read a file by line, but it's not a fast process.

[00:51:45] **Adam:** so in the new one, I'm using node streams and like streaming the file in, and it just like reads a chunk at a memory. And then it even I've even got it set up to use a module called split, which like, so you're streaming it in and then split, we'll just emit an event every time that there's a new line so that you get one line of data.

[00:52:02] **Adam:** So every event, it broadcasts a data event, every time there's a line. And so you can just process a line at a time and then I've got the validation stuff set up so that after you hit 30 errors, it just stops the stream. It's like, okay, that's enough. We don't need to pile on anymore. This file is bad enough.

[00:52:19] **Adam:** Like here's,here's 30 errors. Try again. and it's just like fast

[00:52:24] **Tim:** So one of our, folks on discord, so I had an issue like parsing, a CSV file. And so they recommended university, which was a jar and that just works fantastic. So I'm like someone sends me a CSB file. I'm importing that and I need to do some actions on it and parsing that, based on, CSV files. Kind of picky to

[00:52:48] **Tim:** of kind of parse works. Fantastic. So yeah,

[00:52:52] **Adam:** Business. Like, I, my experience is that businesses run on like Excel files basically. and then when they want to send you, especially when they want to send something to be processed by a computer, not necessarily by a human, they'll export it or save it as CSV. So basically what I'm saying is business runs on CSV.

[00:53:10] **Adam:** But at the same time, apparently nobody is capable of creating a CSV with properly escaped, like delimiters. And like, so if you want to wrap your string value in quotes, but then you want to have a quote in the middle of it, nobody's capable of.

[00:53:25] **Tim:** Yup. Yeah, it drives me

[00:53:27] **Tim:** nuts and university just handles that.

[00:53:31] **Tim:** so so that's fantastic. So yeah, that's my offering on the potluck. It's great.

[00:53:37] **Ben:** Well, I mean, just to go back to the functional programming stuff, I get very frustrated because there are definitely elements of functional programming that I think I do like a lot, like in JavaScript and in ColdFusion I'm mapping and I'm filtering. And,I'm using iterators and Adam's, I, I I use a pure ish functions.

[00:53:58] **Ben:** a lot of my functions are just acting on data because at least in the way that I architect my ColdFusion applications, they use components, but it's not really object oriented architecture in that it's not stateful components that have data and expose methods. It's mostly a bunch of components that are cached in memory forever, and they have business logic and then you pass them data and they do stuff with that data.

[00:54:22] **Ben:** Or they go to the database to get the data and they do stuff with that data and then they return it. So it's very functional in that sense. and I really like some of that stuff because it keeps it very simple where I get really confused with all the functional programming stuff is the way that you almost have to think about the programming backwards when you're dealing with imperative programs.

[00:54:43] **Ben:** It's very easy to read top down. I get this data and then I call this method and it does some stuff. And then I call this methadone does some stuff and it's very top-down processing with the functional stuff. So much of it feels like I'm calling this thing, that's taking a function that was created from another function that was created from another function that was then created from another function.

[00:55:02] **Ben:** And then you finally get to the bottom of that stack and you figure out what that really inner function is. And then like mentally, you have to then unwind and go back up the stack to figure out, oh, that was passing this and this was passing this. And I find that I get back to that top function.

[00:55:14] **Ben:** I'm like, okay, now I know what I'm dealing with. And it seems like just really mentally exhausting to try and think in that, in those terms. and that's the thing I don't connect with at all.

[00:55:25] **Tim:** Yeah, it's totally a different mindset from Oop, right? It just, it's just a completely different,

[00:55:32] **Carol:** And I feel like I've been doing this so long. I don't know how easy I could switch.

[00:55:37] **Carol:** Like I don't think I could just change how I think about writing code and how I think about an application working and how I think about the process being. So it would be very hard for me to just switch over to a functional language.

[00:55:50] **Tim:** Yeah. We just need to tap into Sean. Corfield his brain. He'll figure it out for us.

[00:55:55] **Ben:** And then someone eventually decides to throw monads into the conversation. I have no idea what a monad is and then someone compares it to a burrito and I don't understand that at all. Yeah. And then someone's like, oh, do you use promises and JavaScript? And I'm like, yeah. And they're like, well, it's basically promises, but not really.

[00:56:11] **Ben:** And I'm like, well, that didn't help clarify at all.

[00:56:17] **Ben:** I don't know. I always come back to the thing. If it's solving a problem that I have, then I'm excited. If it doesn't appear to be solving a problem that I have, then it feels like it's.

[00:56:28] **Adam:** That said there's something to be said for learning things, just to, for the pure joy of

[00:56:34] **Ben:** Sure. Sure.

[00:56:36] **Adam:** Yeah.

[00:56:37] **Ben:** But also, I feel like someone mentioned this earlier in the episode, the idea of, essential complexity, maybe this wasn't this

[00:56:42] **Ben:** episode, there's the

[00:56:43] **Adam:** were not ordered or other together earlier this year.

[00:56:47] **Ben:** So there's the idea of essential complexity and accidental or incidental complexity. The essential complexity is something is complex because it just has to be complex.

[00:56:56] **Ben:** Like there's no way to get around it. And then there's accidental complexity is I just chose to make it this complicated because that's how I put it together. and I think it's fun to learn things. Absolutely. But sometimes people and I'm absolutely guilty of this myself, you get so excited about something that you build in a lot of accidental complexity that didn't need to be there because it was. And I, I'm obviously I'm not a

[00:57:19] **Ben:** functional programmer, but.

## [00:57:23] Patreon

[00:57:23] **Adam:** All right, that's the perfect place to end it. I'm calling it. This episode of Working Code is brought to you by spending eight months writing an app so that you can learn how to make it run in Docker and listeners like you. If you're enjoying this show should consider supporting us on Patreon.

[00:57:37] **Adam:** It's the best way to help keep the show running. Patreon donations cover the cost of editing and recording, and we couldn't do this every week without those things. So we appreciate all the support that we can get special. Thanks. Of course, go out to our top patron Monte. if you'd like to help us out, you can go to patreon.com/WorkingCodePod.

[00:57:53] **Adam:** I'll pay students, get early access to an ad free version of new episodes and our after show, which is going to be a fun one this week.

## [00:57:59] Thanks For Listening!

[00:57:59] **Adam:** So do you have a question or a topic you'd like to hear us discuss? There's a lot of ways to get it to us, like sending it to at working code on I'm sorry.

[00:58:07] **Adam:** Nope. I got that wrong. Like sending it to, @WorkingCodePod on Twitter or Instagram, joining our Discord or at workingcode.dev/discord, emailing us WorkigCodePod@gmail.com or you can even record a voice memo on your phone and email that to us so that we can play it on the show.

[00:58:23] **Adam:** We'd love to have that. That's going to do it for us this week. We'll catch you next week. And until then,

[00:58:28] **Tim:** Remember your heart matters. Even if you can't drop programming like me.

## [00:58:33] Bloopers

[00:58:33] **Adam:** all

[00:58:54] **Tim:** out that Carol is last on the triumphs and bales and I'm last on the potluck, but it

[00:58:58] **Carol:** Somebody didn't organize this very well.

[00:59:01] **Ben:** in.

[00:59:03] **Carol:** Who handled the bullet

[00:59:05] **Adam:** these are problems that are so difficult to solve.

[00:59:07] **Tim:** by one error.

[00:59:10] **Adam:** Uh, I'll have to call in a consultant to reorganize our bullet points, a Salesforce consultant.

[00:59:17] **Tim:** $7,000

[00:59:18] **Adam:** And you, you can't spell programming. So what do you want me to do? Like,

[00:59:22] **Tim:** Yeah, I

[00:59:22] **Carol:** blue line.

[00:59:23] **Tim:** it two, is it two M's yet is

[00:59:24] **Adam:** yeah. gaming

[00:59:27] **Ben:** sorry, can you guys hear that fog

[00:59:29] **Adam:** just, just

[00:59:29] **Carol:** just barely.

[00:59:31] **Ben:** there's just like some

[00:59:33] **Ben:** big, big something going by in the distance

[00:59:36] **Adam:** yeah, it's just like rearchitecting that all to not be a problem. Right. It'll just use whatever bandwidth it has to.

[00:59:44] **Ben:** sorry. It sounded like maybe Tim was urinating.

[00:59:48] **Carol:** he was peeing. He turned his camera off,

[00:59:51] **Carol:** but he didn't mute anything. Hello, Tim, did you pee?

[00:59:55] **Tim:** No, I've poured water.

[00:59:56] **Carol:** Oh,

[00:59:56] **Adam:** Okay.

[00:59:58] **Carol:** we thought it was funny. You turn your camera off and then we heard PE uh, water pouring.

[01:00:03] **Carol:** I'm sorry.

[01:00:04] **Tim:** water, but you want to hear me pee? I can do that too.

[01:00:08] **Adam:** no, thank you. And we're

[01:00:09] **Adam:** good.

[01:00:10] **Tim:** All right.
