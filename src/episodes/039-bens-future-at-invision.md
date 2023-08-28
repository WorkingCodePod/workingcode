---
title: "039: Ben's Future at InVision"
description: 'For last 8-years, Ben Nadel has poured his heart and soul into InVision, a product that drives design collaboration. During this period, his area of expertise has focused on the (now named) "legacy" platform - the ColdFusion and AngularJS monolith that has built the business into what it is today. Soon, however, the "legacy" platform will be wholly subsumed by the "modern" platform - a distributed, microservices architecture built on Go, Node.js, and React.'
date: 2021-09-08
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/039-bens-future-at-invision/id1544142288?i=1000534684392"></iframe>

For last 8-years, Ben Nadel has poured his heart and soul into [InVision][invision], a product that drives design collaboration. During this period, his area of expertise has focused on the (now named) "legacy" platform - the ColdFusion and AngularJS monolith that has built the business into what it is today. Soon, however, the "legacy" platform will be wholly subsumed by the "modern" platform - a distributed, microservices architecture built on Go, Node.js, and React.

In today's episode, Ben opens up about the emotional struggle that he's facing as his role on the legacy platform comes to a end. He wonders what it's going to be like to start over; to go from a big fish in a CFML pond to a novice in a Go ocean; and, to find a way to not feel like a complete failure when his productivity drops significantly.

One of the scariest things for Ben is that he's not sure if he'll be able to trust his gut. While the fundamentals of programming will certainly transfer from the legacy platform over to the modern platform, it's hard to know if future "feelings" will be true indicators of potential problems. Or, if it's just a byproduct of his lack of familiarity with the new architecture and language constructs.

Only time will tell. And, until then, he intends to grind hard and deliver as much value as he possibly can on the legacy platform while he still has time and the skills necessary to get the job done.

> **ASIDE**: While not mentioned by name in the show, [Travis Heinström][travis-heinstrom] - the SVP of Engineering at InVision - is the person who wanted to make sure that Ben has all the room he needs to "feel his feelings" when the legacy platform is shut down. This is perhaps one of the most emotionally-intelligent things that Ben has ever heard a manager ask about.

## Notes &amp; Links

Follow the show! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media][editor].

[invision]: https://www.invisionapp.com/
[travis-heinstrom]: https://www.linkedin.com/in/heinstrom/
[working-code]: https://workingcode.dev/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[editor]: https://www.zcross.media/
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/039-bens-future-at-invision.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** I will say, and this is something I think we had talked about in the chat a little bit. my director, who I report to just recently changed the previous one left to go pink. I'm a CTO somewhere. And I'm the new guy that I report to asked me how connected I enter the code. Am I emotionally connected to the code?

[00:00:19] **Ben:** And I obviously, you know,I think we've talked about this on

[00:00:21] **Carol:** You were honest, right? You had to be

[00:00:23] **Ben:** I said I'm so deeply, emotionally connected to code. And what I appreciate so much is that he said, that's good to know. I wanted to know how much room to give you to have those feelings when it comes time to turn the platform off. And I was like, that's probably the most, I thought it's like, that's like the most emotionally intelligent thing I've heard a director say ever.

[00:00:43] **Carol:** Yeah. I mean, it's like the parent, who's sending their kid off to college. I need my moments to break down and to know that I've got to let you go into the world and it's time for me to move on to another project to fill my time. And you need some time to be emotional about those things.

[00:01:00] **Carol:** They're big life events for you letting your application go. Isn't going to be easy if you're tied to it,

## [00:01:26] Intro

[00:01:26] **Adam:** Okay. Here we go. It is show number 39 for, someday on the timeline that I stopped saying. So I'm not going to include the date and on today's show, we're going to be talking about Ben's future at Invision. He's kind of indicated he's got some feedback lately he wants to discuss, so we're going to go there.

[00:01:42] **Adam:** but first as usual, we're gonna start with our triumphs and fails. And Tim, your turn to go first, buddy. What you got?

## [00:01:47] Tim's Not Triumph or Failure

[00:01:47] **Tim:** I mean, can't, is there something between a triumph and a fail? Can I just stay status quo? this week we've been dealing with a lot of non technical issues, have been some legal issues stuff going on that I've had to get involved in. So, nothing I can talk about in public, unfortunately, but even if I could talk about it, I probably wouldn't.

[00:02:06] **Tim:** it's just not worth it, but yeah, so, it's kind of a status

[00:02:09] **Adam:** fail life has been boring.

[00:02:13] **Tim:** I mean, I, th the things that keep me going is in between all these meetings I'm having to have about this different stuff is,grabbing them bits of code, right. Steadily refactoring the project that I've been refactoring and I'm pretty much almost done now.

[00:02:25] **Tim:** So I'm pretty pleased with that. Cause it went a whole lot easier than I thought it was. So I'm happy about that, But yeah, just overall, this week's been kind of may.

[00:02:34] **Carol:** But the real factor is on the product, the problem that you talked about before with the vendor who you're having to basically change off, right?

[00:02:41] **Tim:** yup. Yeah.

[00:02:41] **Tim:** So I'm next week I'll just be testing all of that, making sure everything, all the scenarios work and go live with it. I thought it was gonna take me about two to three months, but actually take me just about three, four weeks.

[00:02:51] **Carol:** Oh, nice. Nice. Hey Ben, do you hear that? Tim's going to test his gun.

[00:02:57] **Ben:** I guess it's nice to have so much freedom.

[00:03:01] **Tim:** Yeah. Oh, shots fired.

[00:03:02] **Tim:** dude. I just said I'm how I missed you last week. Jeez, Carol, get us out of this. Get us out of this, your turn.

## [00:03:11] Carol's Triumph And Failure

[00:03:11] **Carol:** man. I, so I am at a triumph and failure point. previously I talked about starting up a blog and I went through, get hub pages and actually started it. And it's out there. It's pretty much a it's payrolled to far to get hub. The IO. It is, I have a hello world page. So, but the failure to it is that I've stopped.

[00:03:35] **Carol:** my kid got sick. Everyone around us has COVID we're all quarantined. It's just been a hell of a two weeks, on our plate. And it just wholly set me back and I didn't want any extra stress on me. So I just, I stopped working on it so I will get back to it. But I feel that it's a failure because I let life kind of get in the way and stop

[00:03:55] **Adam:** life has a way of doing that.

[00:03:57] **Carol:** It does. It does. And I don't want to be stressed out if I get COVID from the kids. So I would much rather be at a nice, comfortable spot and not have anything extra on the plate. So

[00:04:06] **Tim:** stopped. He just paused.

[00:04:08] **Adam:** Yep.

[00:04:08] **Ben:** Yeah.

[00:04:09] **Carol:** it'll come back. So I started it.

[00:04:12] **Adam:** count as a stop until you actually fully get started.

[00:04:16] **Carol:** This is

[00:04:16] **Ben:** wait, we had set a deadline of September 1st for Carol to have a hello world post. And it is August 29th at the time of this recording. So I feel like that's pure triumph. she came in to several days. I don't, what are there? 31 days in August.

[00:04:32] **Carol:** listen, it literally says hello world. I'm host. I'm hosted with get hub pages.

[00:04:37] **Ben:** yo you nailed it with days to spare.

[00:04:40] **Carol:** Hey, then I guess my Salure is now dry on. Thank you, Ben. Thank you, Ben.

[00:04:44] **Ben:** yeah.

[00:04:46] **Carol:** What about you?

## [00:04:46] Adam's Failure

[00:04:46] **Adam:** I've got a fun fail this week because it was a big fail, but I have absolutely no idea why it happened. So here's what happened. I deployed some code and it had a typo in it, a typo that I had previously seen and thought I fixed, but I think what ended up happening was I forgot to push that commit to the pull request.

[00:05:03] **Adam:** And, so it got deployed without the type of fix. And as a result, all of the data in our setting table for something like eight or 11 or whatever out of our 13 customers, was truncated. Like the entire setting table just got truncated. Yeah.

[00:05:19] **Ben:** Ooh.

[00:05:20] **Adam:** Yeah. And, excuse me. about it for like an hour and a half.

[00:05:27] **Adam:** And, uh, fortunately I was able to recover pretty quickly. we had just recently, done an export from production and, deployed that as the latest database on QA. So we had that, like, it was real simple to go over and like, select all this data as insert statements and recreate them in production real quick.

[00:05:45] **Adam:** But, not only did we have like an hour and a half with no settings, so there was just the whole website looked weird, right? Like, so you log into the admin area and there's nothing on the sidebar because the sidebar is dynamic to show you things that only to only show you things that you have access to. So that sidebar was empty, but there were other things like the system has things that it does on schedule jobs and, like email was scheduled to go out and that sort of thing. And, There were two email, like mass email messages that, managed to get modified during this period with the setting table empty and as a result, because the application couldn't tell what sort of like mode the system was in because that's one of our settings.

[00:06:24] **Adam:** it defaulted to what we call a test mode. So we went through all the paces of like sending that email. We,rendered it and send it off to our email service provider. And the only thing that was different was we included ahead of that said, actually, don't actually send this to you to anybody, right?

[00:06:41] **Adam:** No emails, any actual humans or inboxes, this is just a test. And so it did everything that it was supposed to do. and, in some ways this is a triumph, right. It failed hugely, but it failed gracefully. Right? It did the best possible thing

[00:06:57] **Carol:** So no messages

[00:06:58] **Adam:** right now. Now in this case, we would have, rather those messages gone, that everything about them was fine.

[00:07:03] **Adam:** But, yeah, we would have we're happy that the system did something that, you know, itit failed gracefully, but, we would rather, it just have not failed at all. Now get this, I went back and I looked at the code, that had the type, of course the typo was ridiculously stupid. It was a, I had misspelled setting with only one T like a variable name. And, so, but I went and I looked at the code and here's what the code is doing. It's loading all of the settings. It's literally select, the three columns, not star, but you can think of it as select star from the table and the setting table. And that's it, no filter on it at all. And then it uses cash put to put all those into the in-memory cash.

[00:07:41] **Adam:** That's the goal of that function. And it just runs it on start-up so that, the things that check individual settings on as the application is loading, each of those hits the cash, which was filled with one database query instead of individual database queries for each. So in theory, a great addition to the code and speeds up application startup, but, and that's, it's like select star from the table basically.

[00:08:06] **Adam:** And then a bunch of cash put calls. There's some try-catch and there's like some string concatenation to get the cash key and that sort of thing. And that's it. And I have no idea.

[00:08:16] **Carol:** How the heck did it truncate your

[00:08:18] **Adam:** am, there was that, and one other thing went out in that deploy and the other thing was like a CFM of you change. Right?

[00:08:25] **Carol:** Which wouldn't do it. Yeah.

[00:08:26] **Adam:** I have no idea. I am completely

[00:08:30] **Tim:** pass? Did it pass your tests?

[00:08:33] **Adam:** You had to go there.

[00:08:37] **Tim:** Shots fired again.

[00:08:39] **Adam:** I'm going to plead the fifth on that one. yeah, so it's just, it was terrible. It was, it was a rough afternoon. Had some high points, some low points and. Yeah. If nothing else, I want people to realize, like, I've been doing this full-time since roughly 2004, so coming up on 20 years and it still happens to us.

[00:08:59] **Adam:** Right? Like,

[00:09:00] **Carol:** Mistakes happen. Yeah.

[00:09:02] **Adam:** So

[00:09:03] **Carol:** So if you make that variable change in lower environment and test at what happens,

[00:09:07] **Adam:** I haven't had the opportunity to try that. Yeah. It was like last thing on, on Friday, so

[00:09:12] **Carol:** Cause I, I really want to know like what caused that truncate. And I want to know if it's duplicated, like if it's reproducible almost a duplicatable, I don't think duplicatable is a words.

[00:09:20] **Adam:** sure. It

[00:09:21] **Carol:** See if it's reproducible.

[00:09:22] **Adam:** know.

[00:09:22] **Tim:** you just going to hae a, it could be worse. I'm the guy who truncated every single table in a customer's production database.

[00:09:33] **Carol:** High five, Tim,

[00:09:34] **Tim:** Yep.

[00:09:35] **Carol:** you get gold star.

[00:09:37] **Tim:** Fortunately, there was a very recent backup.

[00:09:39] **Adam:** definitely is a word. So no worries

[00:09:41] **Carol:** Solely

[00:09:43] **Ben:** I, I th there's always that moment of dread that I have not always occasionally where I will get my pull request ready. I get it approved. I deploy it. And the way that stuff, happens at work is, you get,you work on a branch, you get your branch PR proved. Then you actually merge your branch into the main branch using GitHub because, locally developers are not allowed to push to master.

[00:10:09] **Ben:** So you'll merge and get hub. And then I usually pull down master and delete the, the merged branch locally and every now and then I'll do that and I'll go to delete the merge branch. And it'll be like a board, you have uncommitted changes and I'm like what? That was supposed to be in the VR.

[00:10:26] **Carol:** Those are the worst.

[00:10:27] **Ben:** you're, you're uncommitted change hit a chord with me

[00:10:30] **Carol:** All right. So that leaves you, Ben, what do you got going on?

## [00:10:33] Ben's Failure

[00:10:33] **Ben:** yeah. With a failure and a failure that in some ways dovetails with the topic of the show, which is that I've been putting in a lot of extra time at work lately, which I typically don't like to do. And I try never to do, but I've felt compelled to do it through, no one's asked me to do it. So I want to put that out there from a cultural standpoint.

[00:10:56] **Ben:** but I have felt compelled to put an extra time because I feel like I have so little time left. Working on my platform that like, it's like, I need to get in as much value as I possibly can before we turn the lights out. And, again, like, no, one's asked me to do this, but it just there's this sense of ending that I'm fighting.

[00:11:19] **Ben:** And part of my fight and flight response is, is to just try and cram as much junk into it as I can, while I still have the opportunity to use everything that I know about the platform. It's a platform I've been working on for eight years. I'm not going to go to the modern platform and be nearly as productive as I am today.

[00:11:38] **Ben:** It's gonna, I'm basically starting at zero, plus generalized programming understanding. and I'm like, like what tools do I have left in the box that I can jam into this legacy platform before, before I run out of time.

[00:11:51] **Ben:** Yeah. It almost sounds like one last hurrah, Yeah. Yeah, exactly. It's like, I think about it sometimes I, when I was a kid in middle school, we would occasionally have these drugs seminars and this woman came in and she was talking about the effects of, I think it was special K ketamine on the brain.

[00:12:09] **Ben:** I think that's the drug they were talking about. And she was saying that, when you take this drug and you feel like your brain goes crazy, she's like, literally that is your neurons dying. And like, as their last moment of life, they break open and they release all the neuro-transmitters. And like the higher feeling is your neuro-transmitters like soaking your brain.

[00:12:30] **Ben:** And I feel like that's a little bit the metaphor that I see. It's like my moments here on this platform are ending and I'm like exploding and like trying to release as much value into the world around me as I

[00:12:41] **Adam:** a really sad metaphor, man.

[00:12:43] **Carol:** yeah. You holding back tears right now.

[00:12:48] **Tim:** well, last dance with Mary Jane.

[00:12:50] **Ben:** Okay. Yeah, it's a, it's tough. It's tough. So, I enjoy the exploration of it, what can I do with the tools that I have, but definitely it's been eating into a lot of the other stuff that I like to do and, it's not been great for my just mentality in general, feeling extra stressed.

[00:13:05] **Ben:** I've been having a lot of trouble sleeping and,generally not a great feeling. It's a mix. It's a mixed bag. I'll put it that

[00:13:13] **Adam:** Yeah, I have a question I want to ask you. And I feel like we're just kinda gonna bleed right into today's topics, but

[00:13:19] **Ben:** Yeah, sure.

[00:13:19] **Carol:** So let's just

[00:13:20] **Adam:** we get there, I just wanna play this.

[00:13:21] **Mediaboard:** what would you say you do?

[00:13:28] **Adam:** Okay.

[00:13:28] **Ben:** before we get into stuff, I just want to apologize for the comment about testing. Tim at the top of the show, I've been feeling, I've been feeling very guilty about it for the last five minutes.

[00:13:37] **Tim:** Oh my, my friend. You never have to apologize. I know you have no ill intent ever.

[00:13:43] **Ben:** Thank you.

[00:13:44] **Carol:** And we know you test your code.

[00:13:46] **Tim:** Yeah.

[00:13:46] **Ben:** Yeah. just not automated.

## [00:13:48] End-Of-Life Code

[00:13:48] **Adam:** So the last time we talked at least about this topic, I got a very different impression from your youth. It sounded like you were more confident that the legacy system was going to be staying around for at least a significant amount of time. And right now I'm getting the impression from you that you are way less confident in that.

[00:14:05] **Ben:** Yeah. So there's been a lot of developments and essentially we have a migration team that is, has been, their responsibility has been to move users from the legacy platform to the modern platform, along with all of their data that has proven to be a much larger challenge. Then I think anyone anticipated. And so what's happened is we've started to pull back on the expectation of what it actually means to move to the modern platform. so as we've, let's call it, let's say cut corners. I don't want to say too much because a lot of it is still in discussion. but let's just say that we're easing up on the fidelity of the migration of people.

[00:14:51] **Ben:** And with that pull back and fidelity, there has become more of a real timeline on what it actually means for the end of life, for the legacy platform, to the point where they have actually started to attach a real date to it,

[00:15:06] **Carol:** Oh,

[00:15:07] **Ben:** is early next year.

[00:15:10] **Carol:** oh, wow.

[00:15:11] **Ben:** or not we will actually hit that date. that's a question to be answered over the next however many months, but it was really the first time.

[00:15:21] **Ben:** That they have put a date on it and not just been like a hand wavy, Q2 of financial year, 23, like that kind of talk. and I think that sort of

[00:15:31] **Carol:** They've kind of

[00:15:31] **Ben:** me back. Yeah. Yeah. and that made it more real, I, I've sort of just not, poo-pooed the idea that the legacy platform will go away eventually, but like more and more like I'll cross that bridge when I get to it.

[00:15:43] **Ben:** So why bother thinking about it? And it feels like that bridge is actually in seeing distance now and it, like, it makes me panic a little bit.

[00:15:50] **Ben:** Yeah. It's crazy. When things come from this abstract view to now, you see what's happening because we've worked on apps previously where it's like, oh, in the next five years, we plan to roll off. And the next year it's in the next five years and the next years in the next five years. And And yeah. And historically that's what it's been for us.

[00:16:08] **Carol:** So you didn't have to kind of actually process everything. And we never really had to deal with moving off because it was just some far-fetched idea that someone used to make it sound pretty and we never thought it would actually happen. So you get hung up on those feelings when that's been your baby for so long.

[00:16:25] **Ben:** Yeah. So, so historically managers have always asked me, where do you see yourself at the company once the legacy platform ends? And for the most part, I just deferred on those questions. I mean, like, I don't know who

[00:16:40] **Carol:** Fair enough.

[00:16:40] **Ben:** I'll figure it out when we get there. but now it's sort of a real question that I need to start thinking about.

[00:16:45] **Ben:** and I have no idea because I like everything about what I do. I like the backend programming. I like the database stuff. I like the front end programming. I like to talk to customers. I like to be able to talk to customer. And then make changes that they actually see. So I have that immediate feedback loop in terms of the value of what I'm doing.

[00:17:05] **Adam:** Okay.

[00:17:06] **Ben:** So to some degree, I feel like wherever I end up in the company will be fine. I'll be happy enough, and that can always evolve once I get there. but then on the other hand, I also feel like I don't know a lot about the modern platform. So it feels a little bit weird for me to even try to decide where I'm going to go.

[00:17:25] **Ben:** Like, I almost sound silly, but like I almost want to send out a resume to the other teams of the company and be like, here's the stuff I'm really excited about. Like who wants to.

[00:17:34] **Carol:** Does, I mean, that, that doesn't sound like a bad idea. Like I actually liked that idea and that approach to fi to help the other teams figure out where would be your next place to land because you have been, so tunnel-visioned on this one project and this one technology and this one application that they're going to see where your skills lie and what you would be best suited for.

[00:17:55] **Adam:** was gonna say, I don't think you need to send out a resume, but maybe just like schedule a 20 minute meeting with them, have lunch with each department head or something like that. and, just have a

[00:18:04] **Tim:** One thing I've learned about you over the years been, I mean, I knew you coming in on this podcast, I've grown to know you. I feel a bit more and more is I think you don't realize your own value.

[00:18:17] **Carol:** No. I agree with that.

## [00:18:19] Imposter Syndrome

[00:18:19] **Tim:** I think you undersell yourself and your, whatever it is that you wind up doing, you're going to be good at you.

[00:18:26] **Tim:** You will get good at it. You won't be at first, but you will get good at

[00:18:29] **Carol:** You will be an asset.

[00:18:30] **Tim:** Yeah.

[00:18:30] **Tim:** you have a very, you have a process of breaking things down, figuring them out. Right. And so I don't have any doubt that you will succeed at wherever you go. The question is. Do you want to drive that decision yourself right.

[00:18:48] **Tim:** And say, Okay. I'm going to talk to these different teams, find out what they do, kind of tell them what I like to do and see if there's a place there. And they can kind of sell me on coming. Cause I mean, honestly, they should be begging for you to come to the

[00:19:02] **Carol:** And I bet they will. Once they know you're on the market or a team switch.

[00:19:07] **Adam:** you use linting?

[00:19:09] **Carol:** Yeah.

[00:19:09] **Adam:** you require automated testing?

[00:19:13] **Ben:** Tabs or spaces.

[00:19:15] **Tim:** So what I'm saying is you can either be proactive in this and say, all right, I'm going to decide where I'm going to land. Or you can just be reactive and say, well, they'll put me somewhere and I'll figure it out. Which right now it seems maybe a little fear. You just like, well, they'll stick me somewhere and I'll make the best of it.

[00:19:31] **Ben:** It's so tough. I mean, I think you're absolutely a hundred percent, right. I undersell myself a lot and I think that comes from a lot of imposter syndrome and a lot of, I think being a Jack of all trades and master of none, I think also, I, if you put me with the data science people, I don't know anything about data science, so that'd be a mistake.

[00:19:49] **Ben:** But like, if you're dealing with the database administrator, people, I'm like, I love databases, but I don't know anything about administering and like, and excuse me with the front end people. I'm like, I like building interfaces, but I don't know how to do all the razzle dazzle, drag and drop animation stuff.

[00:20:03] **Ben:** And like, you could put me with the backend people and like, that's probably my strongest stuff. Maybe. I don't know. But then like, Same time. I don't know much about using, a lot of the Amazon web service stuff that we actually use on the modern platform. I was

[00:20:19] **Carol:** it so fast. You will learn it so quick. You'll be surprised how quick you can pick that up.

[00:20:24] **Ben:** I think I need to start putting a lot of that more stuff into my kind of independent learning time.

[00:20:30] **Tim:** So Ben, let me ask you, do you think you are excellent at your job now that the job you have now, do you think you're excellent at it?

[00:20:39] **Ben:** I think I'm, I think I'm pretty good.

[00:20:41] **Carol:** Excellent. It's a hard word for anyone to admit that they are, you kind of take X. Did you take I'm pretty good. Yeah.

[00:20:48] **Ben:** think people can give me a task and I will get it done. Well,

[00:20:53] **Tim:** And so all those skills that you have that allow you to be good at your job, you didn't start out being good at those. Right. You got there. Right. And so what I'm saying is you say I'm a Jack of all trades master of none. The reason is because that's what you needed to do, the job You have now.

[00:21:09] **Carol:** You had to figure it out.

[00:21:10] **Tim:** So wherever you're shifted to, or you decide to shift to, you're going to have a, you're going to have a gap, right? You're going to have some things, and some things you don't, and you'll feel that gap, buddy. There's no doubt. No doubt. You'll feel that gap.

[00:21:23] **Ben:** Ah,

[00:21:23] **Tim:** you just don't know what it is now.

[00:21:25] **Tim:** And that's scary.

[00:21:26] **Ben:** and it's scary because, not only am I moving from a legacy platform to a modern platform, but it's a complete shift, not only in terms of architectures going from a monolith to a distributed application, but it's a complete shift in terms of the technologies that I feel very passionate about.

[00:21:44] **Ben:** I'm going from a ColdFusion Lucee CFML backend with an angular front end. To a goaling backend and a react front end and it's it's ah, it's just like, it's so different. It's so many different things at the same time.

[00:22:04] **Tim:** I mean, I feel I went through the same thing several years back when they asked me to move over to the payments side of the house. And, I went from the same thing, a ColdFusion, Lucy, Microsoft SQL database system to, monolith to a distributed, scallop play framework,

[00:22:20] **Ben:** 15 different services.

[00:22:22] **Tim:** some of it's hosted internally. Some of it's in Amazon. I mean, that's, it was scary, but it's like, I actually, once I started learning, I'm like, well, I don't know why I was as scared as I was. It wasn't as bad as I thought. I think a lot of times the unknown. Kind of makes us, we are fearing things we don't even know about.

[00:22:40] **Tim:** And then once we learn about them and we're like, oh, none of the things I expected to go wrong, went wrong. And some of the things I thought were go well didn't but it's, I mean, each day is, brings its own anxiety. So worry about today, today.

[00:22:54] **Ben:** A hundred percent.

[00:22:55] **Carol:** So does it kind of add to what Tim said? The struggle I had with switching to teams, switching technology was that I felt like had become an expert and what I was doing. Not that I'm excellent, but that I was an expert in it. Right. I could pick up a CF app and probably help you, even if I haven't really looked at your code base, like I could go through and, give you some key information that I knew, and I'm 36 years old and I've been doing this for quite a long time, and now I'm switched over to a whole new way of doing it.

[00:23:24] **Carol:** And I'm having to ask like 24 year olds, like, how do I go do this? Because you've been doing this for four years and you've got this under your belt. And then like, I go from being. Expert in what I'm doing too wide eyed and completely lost in some of the steps that it takes. And that was a struggle for me to go from being taught, to not being taught anymore.

[00:23:44] **Carol:** I was like, Ooh, I gotta be okay with saying, I don't know. And being okay that nobody expects me to know anymore. Nobody has that expectation that I'm going to get it day one. They know that this is all new and a complete flip and everything I've worked. that was hard. That was hard.

[00:24:01] **Carol:** and I think dovetailing with that is to some degree I've learned over just a long period of time of doing the same types of stuff to trust my gut when something feels wrong, right. Someone will propose an architectural change. And that can be like, that's not, that doesn't feel right. let's dig into that and figure out why I'm feeling weird about the choice you're making, but when you switched to a new platform and a new language and a new paradigm, like, I don't know if that gut feeling is just, this is all new or that gut feeling is a, you're still doing something weird and I want to talk about it, but it's like now I have to second guess why I'm getting The feelings. Yep. Yep. I get it.

## [00:24:43] Emotional Attachments To Code And Letting Go

[00:24:43] **Ben:** I w I will say, and this is something I think we had talked about in the chat a little bit. my director, who I report to just recently changed the previous one left to go pink. I'm a CTO somewhere. And I'm the new guy that I report to asked me how connected I enter the code. Am I emotionally connected to the code?

[00:25:03] **Ben:** And I obviously, you know,I think we've talked about this on

[00:25:05] **Carol:** You were honest, right? You had to be

[00:25:07] **Ben:** I said I'm so deeply, emotionally connected to code. And what I appreciate so much is that he said, that's good to know. I wanted to know how much room to give you to have those feelings when it comes time to turn the platform off. And I was like, that's probably the most, I thought it's like, that's like the most emotionally intelligent thing I've heard a director say ever.

[00:25:27] **Carol:** Yeah. I mean, it's like the parent, who's sending their kid off to college. I need my moments to break down and to know that I've got to let you go into the world and it's time for me to move on to another project to fill my time. And you need some time to be emotional about those things.

[00:25:44] **Carol:** They're big life events for you letting your application go. Isn't going to be easy if you're tied to it, it's going to hurt.

[00:25:51] **Adam:** have mixed feelings, like on one hand,I can relate. Right? So you and I have been with our current companies at Uproxx for approximately the same amount of time. I was pretty much solo developing our product for the first like four plus years. and so a lot of that code is mine, right?

[00:26:08] **Adam:** There's a huge product here and it's, I can look at that and say, I did that. Right. And so.

[00:26:14] **Tim:** Huh?

[00:26:15] **Adam:** The thing that I have struggled with is letting other people work on it, delegating or just saying like, okay, that's going to be your part. And you're going to be the subject matter expert on that thing going forward.

[00:26:25] **Adam:** And I'm just going to have to be hands off. And that has been tough for me, but also liberating. so I,

[00:26:30] **Ben:** can I say, and then this is a very unhealthy thing that I do is that when someone else needs to come in and start maintaining code that I wrote, I have to a little bit be like, okay, that code is now dead to me. Like that is your code

[00:26:45] **Adam:** Oh

[00:26:46] **Ben:** then it's and it's, a complete survival mechanism.

[00:26:49] **Ben:** Like there's. Yeah. Otherwise it's like too painful to see someone come in and start messing with the thing.

[00:26:56] **Adam:** yeah. In some ways I felt, I have thought of this product and the code that I wrote in it as like my baby, my child. And so that's why it's been hard to let it go. But the more I let it go and let somebody else own it. Like I said, it's more freeing, right? It's less that I have to stress over being the subject matter expert over the entire application is incredibly stressful because then anytime anything breaks, everybody just kind of looks at you and being able to share that stage where there's multiple people being looked at it's so, whatever, not relaxing, but it's anti-stress

[00:27:40] **Carol:** It's nice to feel like you have a team that you have someone standing by you and something happens. And if you keep all that to yourself, you don't get to have that. You don't get to have someone to help you when those things do happen. So.

[00:27:50] **Adam:** So now the other side of that coin, right? I said, I can kind of see where you're coming from on this, but for me, the other side of this coin is something, a piece of advice I got many years ago that I really, obviously it stuck with me. And it's just a few simple words. You are not your code. Right? So the code that you write is just a thing.

[00:28:09] **Adam:** It's a by-product of your work. It's the implementation of a feature idea that you came up with or that you implemented, but it's because code is bad, doesn't make you bad, like going into a code review. This is right. Going into a code review. This is really helpful to keep in mind, right?

[00:28:23] **Adam:** Like maybe it's bad code, but that doesn't make you a bad developer. It just needs to be improved. Right. you cut a corner that shouldn't have been cut or whatever you needed to learn more. and I think the same can be applied here. Right? Like, it's okay. Always going to be part of who you are.

[00:28:40] **Adam:** That is you are a part of the applications, legacy in the application as part of your legacy.

[00:28:47] **Ben:** Yeah.

## [00:28:48] Considering New Roles

[00:28:48] **Tim:** Let me ask you Ben. it's I mean, it sounds like you were at an inflection point in your career. This would be a good opportunity for you. I mean, do you want to just keep doing the same thing as you're doing and have been doing in the past, or has there ever been a desire? you talked about how you like working with the customer to be more customer facing, and unless, hands on keyboard.

[00:29:12] **Tim:** I mean, cause it seems like, the people who are in the organization and asking you this because they recognize your value and they want you to be happy. So, has there been any other roles you ever thought? You know what, I don't, I'm not doing that now, but I think maybe it'd be really cool if I could do that

[00:29:27] **Carol:** If I wasn't writing code, what would I be doing? Is that what you mean?

[00:29:31] **Tim:** and writing code, but it's like, just, is there any like different role that, that you think.

[00:29:37] **Ben:** I think part of why I love the role that I'm in right now is because I have, I think as an engineer goes, I'm particularly good at talking to customers and being enthused about what they say and being able to take the ideas that they have and try to turn them into some sort of a solution, trying not to immediately think of the solution, the moment they start talking, which I know is very challenging sometimes.

[00:30:04] **Ben:** but I think as, as much as I don't like people, like, I love customers and I like talking to them, but I have noticed I have like an hour of meetings a day, typically in a Workday, but then some days I'll have like five hours of meetings and it destroys me

[00:30:22] **Tim:** Yeah.

[00:30:22] **Ben:** and, I will talk to managers and they talk about how, like they have like seven straight hours of meetings every day.

[00:30:29] **Ben:** I literally can't imagine how you get out of bed in the morning. Like I, yeah, it's just not what, it's not what sparks joy.

[00:30:36] **Tim:** Yeah.

[00:30:37] **Ben:** So I, there's something I think I need to have code in my life. I need to be writing code. And if I can have some customer facing access as an input to what I'm actually working on, I think that would be the power move.

[00:30:49] **Ben:** But I don't know if there's a role other than individual contributor that I would really get a lot of joy out of.

[00:30:58] **Adam:** I was gonna kind of go down the same route too. Similar question. Right? So not necessarily is this the moment that you need to move up, but like long-term do you, when you retire, do you want to, you're allowed to change your mind over the course of time? Of course. But do you want, if you could make that decision now, would you want to be an individual contributor until the day you retire?

[00:31:18] **Adam:** Or is there going to be some inflection point in the future where you're going to want to step away a little bit?

[00:31:27] **Carol:** pressure.

[00:31:28] **Tim:** Asking the hard questions, man.

[00:31:30] **Carol:** it.

[00:31:30] **Ben:** I did something different, I think it would, always fancied myself, a product manager. I have no formal training nor have I ever led a product team. So the audacity to consider myself any good at that whatsoever. But I love the idea of designing a product and formulating ideas and weighing trade-offs and moving through a minimum viable product to an actual product and getting customer feedback.

[00:32:01] **Ben:** there is something in there that I find very magical.

[00:32:05] **Adam:** Yeah. I mean, so to kind of put this in your own words here, right? So, if instead of writing code, if you could work with the customers and find out what it is that they need, and then you write specs or something along that line and you hand it off and you've got 20 developers working for you and they go, and they write this huge product, you are doing pretty much the same thing, but now you have 20 X output or roughly, right?

[00:32:30] **Ben:** Yeah, I, in theory, I love it. I think I'm just emotionally, I'm not there yet. I feel like to, other bad metaphors, like there's still fight left in this dog.

[00:32:42] **Adam:** So, okay. So it sounds like you're thinking of moving up to anything other than I see as sort of like being put out to pasture.

[00:32:49] **Tim:** Okay.

[00:32:51] **Carol:** Oh,

[00:32:52] **Ben:** I painted it,

[00:32:53] **Adam:** my interpretation of the way he's describing it.

[00:32:56] **Ben:** it.

[00:32:59] **Carol:** you're going to make Ben cry.

[00:33:04] **Ben:** No.

[00:33:06] **Tim:** I struggle with this too one. If I had the ideal position for me personally, it would be kind of what you said about a product type person whose job is to build a prototype of an idea. Right? Get an idea, get that German of an idea, and then, talk to customers, see if there's appetite for that idea and then building a prototype and, we rag on, well, I do rag on ColdFusion a lot.

[00:33:32] **Tim:** It is a fantastic prototyping tool. It's I mean, it's, you can do some really cool stuff really fast. Um, and so, prototyping something really quick and then seeing, how's that working out and then didn't you turn it over to,a team that's gonna, build up the in-service, the real thing.

[00:33:49] **Tim:** that would be my favorite job. Cause I like the new thing and building something new and making an idea come to fruition.

## [00:33:57] Experimentation Culture

[00:33:57] **Ben:** Well, I'll tell you as the whole legacy platform versus modern platform has evolved over the last year. So, one of the guys on my team, Sean Grigson has been pushing really hard for my team, the rainbow team to be re-imagined as what he calls the labs team in V seven, which would be very much a R D

[00:34:17] **Carol:** Just

[00:34:18] **Ben:** like let's experiment with some stuff.

[00:34:20] **Ben:** Let's throw some stuff on the page and see what sticks. and as much as I think our organization. Slowly started to open itself up to the idea of more experimentation and faster iteration. I think culturally, we're not there yet. And I think there's not enough. There's not enough openness to failure yet where I think there's always this sense that if we do something and it doesn't work out, that's a hundred percent waste of effort.

[00:34:52] **Carol:** And then it's not that it's.

[00:34:53] **Ben:** right. And,and until we can embrace the idea of failure as a learning experience, I think we're not quite going to be to the point where people can just like Willy nilly start to

[00:35:02] **Tim:** Just,just tell him, think about the R and D tax credits. You'll get

[00:35:05] **Carol:** yeah. Let's let Tim give you a lesson on it.

[00:35:09] **Tim:** It's not a failure. It's a tax credit.

[00:35:13] **Ben:** Oh man,

[00:35:14] **Carol:** Yeah, we actually have something called clear labs that Clare capital, then they are very strong supporters of let's try this new thing. Let's try to figure out if we can even make a product for it. Let's see if we can acquire another product that does what we're thinking of and then put it in our system.

[00:35:34] **Carol:** So I love that we have clear labs at any point. I can go, I want to work on clear labs and just see what's going on for internal, external, and then go back to my team. It's really goal.

[00:35:42] **Tim:** but I imagine having talked to you, Ben. What's happening is you don't have an official labs team. What you do is you have a bunch of skunkworks, right. which I do all the time, I do something off the books and the next thing you know, it's like, Hey, we need this product. I'm like, well, actually I kind of got the prototype already done.

[00:35:59] **Tim:** Oh, wow. Cool.

[00:36:01] **Ben:** well, a hundred percent. And I think in one of the previous episodes we were joking about. Adam likes to get customer feedback when he builds products.

[00:36:11] **Carol:** Air quoted. Yeah.

[00:36:12] **Ben:** and I like to just work in the dark, but I work in the dark more out of necessity than I then out of. I think it's the right thing to do.

[00:36:20] **Ben:** because culturally speaking, we're not there yet. I have to not make a lot of noise. Ideally, I would love to be pulling customers in, day one to get an idea of what we should be doing, but it's just it's I hate to say risky, but like it's too risky to do that from a like personal standpoint of where I am in the organization.

[00:36:39] **Tim:** Yeah. And I'll tell you some of, so it's something that, that the company that we work for, the parent company that bought us, they have this idea of initiative. So customer initiatives, and it kind of takes the fear of failure out in the fact that if you can get, let's say you have a really good idea and customers are interested in it, but you get customers not only to say, Hey, I'm interested in this.

[00:37:02] **Tim:** They're willing to invest and share some of the financial burden of, of that. they're not paying for the whole thing. They're paying for a portion of it, right? for the added benefit of whenever this does come to fruition, they're getting, a sweetheart, F founder's price that they're going to get that other customers won't.

[00:37:18] **Tim:** So I think that's, the people that maybe don't like the idea of the labs idea are probably. Saying, Well, it's too expensive or, the risk is reward is not good enough, but if you can offset that with, these are, we can get some investment in this. They might look at it a little differently, but that would take some that would take some salesmanship to do that.

[00:37:39] **Ben:** Well, and I think not necessarily positioned as investment, but positioned as brand capital, so to speak. I think there is something magical about working with a customer, the customer, having a problem, and then you actually go and do something about it. Like I know we have a technical account manager at Tam over at Amazon for all of our cloud stuff, and I'm a hundred percent sure if we said, Hey, it'd be great.

[00:38:09] **Ben:** If Amazon web services did. There would be no chance they would actually go and build that thing. a customer comes to us and says, Hey, it'd be really great. If there was a button over here that did this thing, I'd be like, all right, I'll build that for you. No problem. and to some degree, I feel like there's aa lot of power that you can get from being a company that can actually respond to customers, just in terms of their loyalty.

[00:38:32] **Ben:** I don't,

[00:38:33] **Tim:** you put money in the Goodwill bank, right? So, and so when there's, sometimes there's failures, you take some of that money out, but when ever you're doing things like that, it's money in the Goodwill bank.

[00:38:44] **Adam:** Yeah.

[00:38:45] **Adam:** This This

## [00:38:46] Career Building And Long Term Thinking

[00:38:46] **Adam:** is not at all how I thought this discussion was going to go. So when you gave us this sort of prompt about this episode, you, so what you said was exactly. I quoted it here. They keep asking me where my place is in the company, in the future. I never know how to answer that question. And I was coming into this thinking we were going to have to give you like, tough love, like Ben, you have to be intentional about building your career.

[00:39:10] **Adam:** And, I'm thinking, you're kind of a timid person, which is not that I don't think anybody

[00:39:14] **Ben:** A hundred

[00:39:15] **Adam:** that mental picture of you when, when they look at you. Right. you're are a well-built, strong individual.

[00:39:22] **Ben:** I

[00:39:22] **Carol:** Teddy bear. You are a Teddy bear. You've looked like hardcore, but use want to squish you and hug you.

[00:39:29] **Adam:** And yeah. And so like I was, I came in, I wrote notes down. I came in prepared to give you like some tough love. Yeah.

[00:39:36] **Ben:** Oh,

[00:39:36] **Carol:** about to pair it. You bins.

[00:39:38] **Ben:** love,

[00:39:38] **Adam:** okay, so maybe there's somebody out there listening to this who needs this advice, right? So career building is a thing, right? you can come in and punch the clock and write the software to the spec that you're given and then punch out and go home.

[00:39:51] **Adam:** And there's nothing wrong with that, but what,

[00:39:55] **Carol:** It's not who

[00:39:56] **Adam:** but the four of us know, but

[00:39:58] **Carol:** you're right, right.

[00:39:59] **Adam:** the possibility when you, if you assume that role, there's a much higher likelihood that life is going to surprise you, right. You're going to get laid off or you're going to get moved to a department and have to do something you hate or who knows what, your career building for me, with the way I look at it is like, I have sort of short-term goals and long-term goals, and I try to work those things backwards.

[00:40:20] **Adam:** Right? So long-term goals. Where do I want to be? Where do I want to be when I retire and. What can I set a short term goals that will be like stepping stones for me to get there. And then for those short term goals, what do I need to do from where I am now to get there? Right. So sort of working backwards.

[00:40:36] **Adam:** All right. Like, so you want to have Thanksgiving dinner on the table at 2:00 PM. the Turkey's hot, the mashed potatoes are hot, the,and so how do you time everything you have to work backwards from that, right? The Turkey takes a lot longer to cook than the mashed potatoes.

[00:40:49] **Adam:** So you have to schedule things. and so I like that idea of working backwards, like pick a goal and maybe my goal will change before I get there, but I'm being intentional about, okay, this is what I need to accomplish to get to that goal. And

[00:41:03] **Ben:** let me ask you a question quickly. and maybe this is completely unrelated, but I know that we have joked about in the chat to get your kids on a bus at 7:30 AM. You're planning for that at 9:00 PM the day before. And then like, do you feel that having kids has helped you with longer term thinking or do you think you've just always been a long-term planner and having kids is

[00:41:27] **Adam:** I think that, that having kids could be something that would help people that are not already long-term planners, but I personally have been a longterm thinker for a long time.

[00:41:36] **Ben:** I'm a terrible, I can think like a week ahead of time and anything beyond that feels very overwhelming to me.

[00:41:43] **Adam:** Yeah. And I mean, this is something I struggle with my kids. They are, they see whatever's right in front of their face and nothing beyond that. and that is very difficult when you're trying to motivate them to do something or to try to get them to learn a lesson. It's like, don't egg my shed because then somebody has to clean it up right there.

[00:41:59] **Adam:** They're just like, but it's fun to throw exit the shed.

[00:42:02] **Carol:** Okay.

[00:42:03] **Carol:** Right. So I will say, I think having kids does help you with the long-term vision planning, because we're looking at Peyton going, dude, you're a junior, you need to be touring colleges. You need to be studying for your act. You think that's next year. Well, yeah, next year is going to be here before you know it, and you're not going to be prepared for it.

[00:42:23] **Carol:** So it does force you to kind of take the initiative to teach them those longterm planning skills. So I think it does help

[00:42:30] **Adam:** I had a very similar conversation with my oldest, a couple of nights ago at dinner.

[00:42:35] **Carol:** that he has to go to college

[00:42:36] **Adam:** He's 12.

[00:42:38] **Carol:** Take the sat.

[00:42:39] **Adam:** that question, not that conversation, but the conversation, the sort of the meta conversation we're having here about planning, right? So I told him like, you're going into the seventh grade. Now that the number one thing you need to learn over the course of the next two years is how to learn.

[00:42:53] **Carol:** Girls are

[00:42:53] **Adam:** No, that's a different, that's a social learning. School-wise the thing you need to learn is how to learn, because then you're going to high school and that's where it counts. That's what colleges are going to look at. If you choose to go to college, you have to have performed reasonably well at high school to get into a college that you want to go to.

[00:43:10] **Adam:** And I told him about how I struggled because so, growing up, I was the kid who did really well in school without trying. And so I coasted on that until about like, 10th grade, somewhere around 10th and 11th, and then the subjects got hard. And just like that, I start, I dropped from like an all a student to like all C minuses and DS in like one semester,

[00:43:32] **Carol:** didn't know how to study. You didn't know how to learn.

[00:43:35] **Adam:** and so that's what I was talking to him about is like, we gotta figure out what works for you.

[00:43:39] **Adam:** And, he knows he has ADHD. And we talk about like, this is what's difficult for you and how do we, how do we, talk about writing things down? And even though nobody else is writing it down, sort of thing, like whatever, got to find what works for you so that you can be successful. And yeah, that planning ahead stuff.

[00:43:57] **Ben:** It's interesting. I'm talking about going from someone who just sort of naturally did well and then suddenly running into challenges. One thing that I think is helpful for me is that everything feels a little bit hard. Like I, in programming, I don't like none of it feels natural to me and I work really hard at trying to understand.

[00:44:23] **Ben:** And I'm constantly trying to think about how to improve stuff. What am I doing wrong and seeing other people's stuff and trying to, once I get past the imposter syndrome, like how can I then actually learn from what they're doing? And, uh,

[00:44:36] **Ben:** I think because a lot of it feels challenging all the time and it like the learning aspect, doesn't worry me.

[00:44:46] **Ben:** I love reading documentation. I'm like, w I'm one of those people who, when I want to learn something new, like the first thing I'll do is open up the documentation and read it from end to end, just to like, know what's going on, what's out there. What are the possibilities? So I dunno,I, to some degree, like I was never a great student.

[00:45:04] **Ben:** I was sort of like a mid good student. And, I think that's helped me a lot

[00:45:12] **Carol:** I think so to you. Yeah.

[00:45:14] **Tim:** I mean, programming is such a complex.

[00:45:16] **Tim:** activity. If you come at, come at, come at it with an, with a attitude of overconfidence, you're going to fail.

[00:45:22] **Carol:** and your software is going to fail.

[00:45:24] **Tim:** Yeah.

[00:45:24] **Tim:** You're going to

[00:45:25] **Carol:** are going to go down.

[00:45:26] **Tim:** the times when I thought I w I just had it all figured out was the projects that just total

[00:45:31] **Carol:** burned. They burned to the ground. Yeah. If I was terrified, it might've went up. Okay. Yeah.

[00:45:37] **Tim:** Yeah.

[00:45:38] **Tim:** Yep.

[00:45:39] **Ben:** So, so what other tough love did you have anything

## [00:45:41] Consulting

[00:45:41] **Adam:** I think that the majority of it, oh, so I was going to talk about one of the things I was considering was there was a possibility that you were, afraid of leaving your current role because it meant giving up, working on ColdFusion CFML stuff.

[00:45:56] **Ben:** I am also, I, that is a very

[00:45:57] **Adam:** And one of the things I was gonna say is like, it is totally reasonable to decide, to go out and do like consulting, right?

[00:46:05] **Adam:** There's there are a ridiculous number of companies that have a load of CFML code and they need somebody to maintain it. And the better you are at it, the more you can sell it. And you can make top dollar doing that. The problem with that approach that I have personal experience with is all of their code is awful because

[00:46:24] **Carol:** it is not maintainable.

[00:46:26] **Adam:** no longer work there that wrote it wrote.

[00:46:30] **Carol:** our reason.

[00:46:31] **Adam:** So,

[00:46:32] **Tim:** It'd be obedient. Being a contractor is less about writing code And more about, lining up jobs and selling yourself constantly, which is

[00:46:38] **Ben:** And that's, that is definitely not my

[00:46:39] **Adam:** So, but it's, I mean, if that, if what was important to you is staying with CFML, then there's ways to do that. Even if it doesn't mean staying at Nvidia. what else? yeah.

[00:46:50] **Ben:** All right. I'll tell you part of me, I'm worried that part of me will always go to the next language and then compare it to ColdFusion and like,

[00:47:02] **Tim:** Okay.

[00:47:03] **Ben:** your your language choices, stupid. Like this would have been so much easier in ColdFusion. Like I wouldn't have to worry about passing around pointers and D referencing pointers and allocating memory.

[00:47:12] **Ben:** Like this is stupid. Like the language should have just figured this out for me. And, I'm worried that I'm not going to get past that

[00:47:19] **Carol:** You will,

[00:47:20] **Adam:** I want to remind you of something that Adam layman said. and you may not have been there when he said it, or I was at a presentation that

[00:47:27] **Ben:** Adam layman, former product lead for ColdFusion. Okay. Just wanna make sure we're all

[00:47:32] **Adam:** something he said, go ahead.

[00:47:34] **Tim:** now, director of

[00:47:34] **Tim:** a product director

[00:47:35] **Adam:** of products at Spotify. Yeah. he said you don't truly know a programming language until you can name 10 things you hate about it.

[00:47:42] **Ben:** Yeah, totally.

[00:47:44] **Carol:** I like it.

[00:47:45] **Adam:** And that obviously, these things stick in my head, that resonated with me and,

[00:47:49] **Tim:** even though I never programmed, I must know react then. Cause I get named, I can, I can, I can name 10 things right now.

[00:47:55] **Adam:** It's not, it's a qualifier. It's not the only qualifier.

[00:48:03] **Ben:** Oh, that's so good.

[00:48:05] **Adam:** Tell me you're old without telling me you're old, get off my lawn. but that seems like a good place to end it. Okay. So,

[00:48:17] **Carol:** the Ben you are amazing and anywhere you land, you will fit into a team.

[00:48:23] **Carol:** I know. it's just, it's scary and it's unknown and all those things are okay.

[00:48:29] **Adam:** and we'll be here to have your back.

[00:48:31] **Ben:** Thank.

[00:48:31] **Carol:** part of it's part of growing up, buddy. You got this. Yeah,

[00:48:35] **Tim:** the older I get the less, I know what I want to do when I grow

[00:48:37] **Carol:** I agree. I actually completely agree with that.

[00:48:42] **Tim:** Thanks. I stolen off someone on Twitter just

[00:48:44] **Carol:** Nice. Nice. What was the thing we did? It was like, if you heard it here, you heard it second.

[00:48:50] **Tim:** If you steal it from me, you stole twice.

## [00:48:52] Patreon

[00:48:52] **Adam:** All right. All right. This episode of Working Code is brought to you by being promoted out to pasture and listeners like you. If you like what we're doing here, you might want to consider supporting us on Patreon at patreon.com/WorkingCodePod a new this week. We have a new patrons, Sean, thank you, and welcome aboard.

[00:49:11] **Carol:** Asia

[00:49:12] **Adam:** And to thank our patrons for their support. Everybody gets an invite to our Discord server, where we hang out and chat about the podcast and work stuff and life stuff, and our triumphs and fails of everyday life. And we have other parks available like early access to new episodes and the after show, of course we need to thank our top patrons, Peter and Monte.

[00:49:30] **Adam:** Thank you guys so much for your support.

[00:49:32] **Tim:** Okay.

## [00:49:33] Thanks For Listening!

[00:49:33] **Adam:** If paying for podcasts, isn't your thing. No worries. We appreciate you just taking the time to listen. And here are some freeways you can help us out too. You could share the show with your friends and your coworkers. You could leave us a rating and a review on apple podcasts or wherever you get your podcasts.

[00:49:47] **Adam:** Those would be really helpful and beneficial. And you know, what else would help you could send us your questions and your show topics on Twitter or on Instagram @WorkingCodePod, or you could leave us a voice message at 512-253-2633 that's 512-253-CODE. We'll catch you next week. And until then,

[00:50:05] **Tim:** heart matters and your heart matters twice as much.

[00:50:09] **Carol:** I will second

[00:50:11] **Adam:** then who?

[00:50:12] **Ben:** are great.

[00:50:12] **Adam:** Me?

[00:50:14] **Tim:** F everyone

[00:50:15] **Adam:** this week though.

[00:50:17] **Tim:** just this way.

[00:50:18] **Adam:** All right.

[00:50:39]

## [00:50:39] Bloopers

[00:50:39] **Ben:** Oh my God. She just like, wants to go up there so bad.

[00:50:42] **Tim:** She wants to be on the show. Ben.

[00:50:44] **Ben:** Come here, to say hi to everybody?

[00:50:47] **Adam:** pees on you.

[00:50:49] **Tim:** Lucy. It's Lucy, right?

[00:50:51] **Carol:** Yeah. Hi.

[00:50:53] **Adam:** uh,

[00:50:54] **Ben:** no, no. Oh my God. And her little hoochie is wet. I can feel it on my arm. Sit down. she's dirty girl

[00:51:05] **Carol:** Tim. We told you,

[00:51:07] **Tim:** I know, right?

[00:51:08]

[00:51:08] **Ben:** I have to pause here for a second, cause my dog like really wants to get up into her PB bed. So I'm just gonna let her do it.

[00:51:17] **Tim:** Oh, Lucy.

[00:51:19] **Tim:** This episode of working co is brought to you by Lucy's PPB. Yeah.

[00:51:22] **Carol:** Yeah.

[00:51:23] **Adam:** Oh, it was not by her,

[00:51:25] **Carol:** who pee on things,

[00:51:26] **Adam:** rug or.

[00:51:28] **Ben:** She's such a doofus and now she's sniffing around local wise. It smells so weird up here. Okay.

[00:51:36] **Adam:** So.

[00:51:37] **Carol:** So I was looking at the doc and you were reading off everything and I couldn't see like the last little two bullet points. And I was like, man, Adam, why don't you just scroll? And I was like, oh It's mine. You're not like, screen-sharing this.

[00:51:50] **Tim:** It's funny.

[00:51:52] **Carol:** I was like, why don't I just scroll?
