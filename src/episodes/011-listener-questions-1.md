---
title: "011: Listener Questions #1"
description: The crew responds to listener questions and a particularly scathing blog post in response to episode 9.
date: 2021-02-24
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/011-listener-questions-1/id1544142288?i=1000510459724"></iframe>

[Cunningham's Law][cunninghams-law] states:

> The best way to get the right answer on the internet is not to ask a question; it's to post the wrong answer.

The crew recently experienced a bit of this law _first hand_ in response to [their episode on Testing][working-code-009]. [Adam Cameron][adam-cameron] - friend of the show and long-time friend of the hosts - posted a [scathing (but loving) rebuttal][adam-cameron-post] of _basically_ everything that Ben said in episode 009. This week, the crew meets to discuss Adam's post; and, to dig more deeply into how testing gets applied in real world scenarios.

Thew crew also attempt to pick apart the relationship between DevOps and engineering - a [question posed by LD2][ld2]. Just don't ask us (or anyone) to define what exactly DevOps is; you ask 10 different people and you'll get 15 different answers.

Oh, and Adam totally built [a website for the show][working-code]! So, heck yeah! It's built on [Eleventy][11ty] and is generated based on Markdown files.

### Triumphs &amp; Failures

- **Adam's Triumph / Failure** - His application had a Cross-Site Scripting (XSS) vulnerability that was exploited. Which is definitely unfortunate. However, he was able to take a bad situation and _turn it into an opportunity_ to practice transparency, clear communication, and a sense of urgency with his customers. In fact, in the end, he was commended by his customers for how well he handled the situation.

- **Ben's Triumph** - He attached some analytics to a user interface (UI) within his application and suddenly a part of the application which has historically been a blackbox was transformed into a rich, emotional experience in which he could "see" users actually consuming the tools that he built. This recent adoption of analytics (into his workflow) has forever changed the way that he will think about what is and is not an important part of the application that he's building. It's amazing how powerful "user empathy" can be to an engineer's motivation.

- **Carol's Triumph** - Her company is over-committed in terms of the work that they have on their schedule. But, instead of making the engineers freak-out over this planning problem, her managers are _doing their job right_ and are protecting their reports from the organizational chaos. It's rare to see managers that understand how to manage _both up and down_ within a company hierarchy! As Adam says in the episode, a good manager is worth their weight in gold.

- **Tim's Triumph** - His frustration over debugging an issue in Redis had grown to the point where he was walking around his house angry. But, instead of trying to _"just muscling through it"_, he decided to step back, **be kind to himself**, and take a break.

  > **ASIDE**: You won't know this from the current recording but this break gave him the opportunity to rethink the problem and ultimately come back and figure out what was going wrong. Such is the magic of mental rest and relaxation!

### Notes &amp; Links

- [OWASP: XSS](https://owasp.org/www-community/attacks/xss/) - consistently on the Top 10 vulnerabilities outlined by the Open Web Application Security Project (OWASP).
- Data Breach Response Plan - an organizational play that outlines how a company responds to data breaches, how quickly they have to notify users, and what immediate and longer-term steps they have to take to mitigate such breaches in the future.
- [Shattered Glass](https://www.imdb.com/title/tt0323944) - a movie in which Hank Azaria's character demonstrates excellent managerial skills.
- [Segment](https://segment.com/) - a popular data pipeline and aggregation platform.
- [Amplitude](https://amplitude.com/) - a popular analytics platform for digital teams.
- [Eleventy][11ty] - a simpler static site generator.
- [Adam Cameron: Thoughts on Working Code podcast's Testing episode][adam-cameron-post] - the rebuttal that we discuss on the show.
- [Cunningham's Law][cunninghams-law] - states, "the best way to get the right answer on the internet is not to ask a question; it's to post the wrong answer."
- [Test-Driven Development](https://en.wikipedia.org/wiki/Test-driven_development) - a test-first methodology for software application development.
- [Singleton Pattern](https://en.wikipedia.org/wiki/Singleton_pattern) - a software design pattern that restricts the instantiation of a class to one "single" instance.
- [Cory Haines](https://articles.coreyhaines.com/) - a well known programmer in the Ruby and testing worlds.
- [Ben Nadel: Singleton vs. Single Instance And A Decade Of Unnecessary Guilt](https://www.bennadel.com/blog/3380-singleton-vs-single-instance-and-a-decade-of-unnecessary-guilt.htm) - the realization that everything he thought about the "Singleton Pattern" was wrong.
- DevOps - who the heck knows what it actually is - platform things mostly? Code++? A mindset? A job title?

Follow the show! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[adam-cameron]: http://blog.adamcameron.me/
[adam-cameron-post]: http://blog.adamcameron.me/2021/02/thoughts-on-working-code-podcasts.html
[cunninghams-law]: https://meta.wikimedia.org/wiki/Cunningham%27s_Law
[11ty]: https://www.11ty.dev/
[ld2]: https://twitter.com/LD2/status/1357493535088332801
[working-code]: https://workingcode.dev/
[working-code-009]: https://workingcode.dev/episodes/009-testing/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/011-listener-questions-1.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:16] **Adam:** Okay. It's show number 11 for February the 17th, 2021. And today on the show, we're going to be answering listener questions and discussing your feedback. And there is some feedback to discuss. But before we get to that. I guess let's do our triumphs and fails, and just because it feels like it's been a while, I'm gonna go first.

[00:00:35] **Adam:** I have, uh, what I'm gonna say is a definite failure that I managed to turn into a triumph. So we have, obviously, a web application. And we had an XSS cross the we had an XSS or cross site scripting vulnerability in our application and it was exploited. Yeah, really. And it was exploited, which means somebody was able to inject some JavaScript into our site.

[00:01:02] **Adam:** And what ended up happening was that JavaScript was running within the admin interface, which is, you know, where our customers can see all the private information that their customers give them. So obviously not a good situation. Um, but. Uh, when all was said and done, my, uh, triumph here is that I was commended for, uh, the way that I handled the situation, the communication that I had with the customer, and, and dealing with the, having the right amount of transparency, and treating it with urgency, and getting it fixed, and cleaning up the data, and walking the line well between being transparent.

[00:01:41] **Adam:** And I'm not giving away too much, right? Right. You don't want to be like, Oh yeah, we totally screwed the pooch on this one, but you also have to be, you have to like take responsibility and ownership of the problem. And so security, we never heard of it. So yeah.

[00:01:57] **Carol:** That's not a

[00:01:57] **Adam:** thing. Let me ask

[00:01:59] **Tim:** you, Adam, do you, do you have, uh, do you guys have an official data breach response protocol, like I've written?

[00:02:08] **Adam:** Probably. Probably.

[00:02:11] **Tim:** Uh. Which leads me to the next question, does everyone

[00:02:14] **Adam:** know it? Um, yeah, I mean, that's a really good question. I'll have to follow up with that. And, um, I mean, I, I know that what I did would be what I would be more than happy. I'm the, I'm the person. That would be more than happy to spend three weeks every year documenting stuff like this because I'm the, I'm the over communicator, right?

[00:02:34] **Adam:** I'm the one. No, we hadn't noticed that. I'm the one that's like, you know how Slack gives you stats? I don't know if you might not know if you, if you're the Slack, like team owner. They send you stats pretty regularly and I'm always like, you know, the number one communicator. I'm the, I use the most emojis and, uh, you know, like talk 40% more than anybody else.

[00:02:54] **Adam:** And, uh, you know, I'm, I'm the one that's like kind of, uh, more often I think than other people. Suggesting that we document processes and stuff like that. And

[00:03:07] **Tim:** the reason I ask is, is, I mean, I know you guys aren't in the PCI, you know, the, the, um, processing credit card kind of thing, but that is, yeah, that is, that is a requirement that you have to have a formal written document that says if there's a breach, you know, who responds to the breach.

[00:03:24] **Tim:** Um, how long do you wait until you, you know, tell your customers about the breach, um, and sort of the communication method that you're going to use to, to explain the breach. So I'm

[00:03:35] **Adam:** probably going to get this wrong. But we, we do have some PCI certifications. I'm like I said, I'm probably going to get this wrong, but I believe it is a SAC, which is S A Q D or B.

[00:03:48] **Adam:** I feel like that's familiar. Um, either way, the way that we have things set up is to minimize our PCI responsibility, like we don't have any credit card numbers ever hit our servers, anything like that. We, we, you know, we keep it all off. You services that, that take on that responsibility for us.

[00:04:07] **Tim:** Yeah, I think it's just important that everyone have, you know, have that because it's it's one of those things that You know, kudos for, you know, getting the compliments on how you communicated it, but you were kind of, sounds like you're kind of winging it.

[00:04:21] **Tim:** So what if you did do it wrong and they're like, well, you shouldn't have said that. Now you possibly opened us to the liability that we don't want you to deal with. So having a, having a written document is extremely

[00:04:32] **Adam:** important. Yeah, no, I'll definitely take that back to the team and see, you know, what we want to do.

[00:04:37] **Adam:** In this case. Um, I, I felt confident running it on my own because, um, so the first thing I did was reply to the ticket as fast as I could. It says, thank you for bringing this to us. You know, we're looking into it. We'll get back to you. And then, um, I started researching it and found that, yes, they were able to inject JavaScript into our app, but fortunately, they weren't able to get anything useful out.

[00:05:02] **Adam:** It was obfuscated JavaScript, so when I de obfuscated it, It was basically trying to grab cookies, and... Share them offsite so that somebody could do session hijacking. Right. And we use HTTP only cookies. So it wasn't, yeah, they got, they got like our Google analytics ID and who knows what else, or I know a few things, but nothing useful.

[00:05:24] **Adam:** Um, and so after I had done all that, I sort of documented everything that they were trying to do, and I sent that back to the customer and I was like, here's what they. Here is what they were trying to do. Absolutely nothing useful got out, uh, and here's why. I know that. With certainty, yeah. Yeah, and, uh, regardless of that fact, I have already cleaned up the data that had the XSS in it, and within the hour I will be deploying changes that prevent any future XSS vulnerabilities in this area, and we're going to, uh, commit to a comprehensive review of the rest of the application.

[00:06:03] **Adam:** Other potential vulnerabilities. So,

[00:06:06] **Tim:** so an after action report?

[00:06:08] **Adam:** Pretty much, yeah. Yeah. So

[00:06:09] **Carol:** with your plan, Tim, does it lay out like what to communicate? Does it have, like, this is kind of what the words are that we're gonna say, like, this is the, the kind of high level detail of what we're gonna say. It, it's very high

[00:06:20] **Tim:** level.

[00:06:21] **Tim:** I mean, it does, it doesn't say, here's the words we're gonna use, but it does lay out. Um, so there's some information you, you have to acknowledge that a breach happened, right? You have to. Uh, you know, say how long it lasted, you have to say what as of now that you know has been exposed, and you have to say what, um, remediation you're going to do to stop it from happening now and prevent it from happening in the future.

[00:06:47] **Adam:** Which sounds very familiar, that's like the script for every breach that you've ever read a news report about. Yeah, yeah. Yeah,

[00:06:51] **Tim:** exactly. But the thing is, it's one of those things, it does give you a lot of latitude because sometimes there is, people will exploit you, but like you said, Adam, there really was no damage.

[00:07:04] **Tim:** Right. And so you, you got to balance. The people are always trying to attack somewhere. So you got to balance how much do you tell the customer right now and they start worrying about stuff that really is not a worry. Right. Versus, you know, all of a sudden all their customers credit cards are being charged, you know.

[00:07:25] **Tim:** And you never said anything, and now, now you look bad. That's a different story, yeah. Yeah, so, it's definitely a balancing act, but yeah, just knowing when, mainly it's a timeline. Sometimes there are no metrics on how soon you tell people. Because you do need to give yourself an amount of time to respond.

[00:07:42] **Tim:** Otherwise, you're giving incomplete information. Uh, and if you send out something and say, Oh, remember we said like five hours ago that... This happened. We found out actually that it really didn't happen. This happened and now there's zero confidence.

[00:07:54] **Carol:** Right. Yeah, you don't want that frantic, immediate, like, response to something.

[00:07:59] **Carol:** You need to think through it. You need to make sure you know exactly what was going on. I think before you say anything, just personally. Yeah.

[00:08:06] **Ben:** It's interesting, uh, how, I don't know if this is a sign of the times or, or how married we are to a lot of our digital workflows. But, you know, my credit card's been stolen probably five times over the last decade from various, you know, Home Depot and Target and places like that.

[00:08:26] **Ben:** And, uh, password breaches and various things. And what was that, um, there was that one big, uh, credit score, like Equifax. Yeah. Equifax. And like literally having my information stolen has never actually motivated me to stop using a particular service. And, and it just, cause like the pain of having to think deeply about trying to find a different service.

[00:08:50] **Ben:** Feels more painful than whatever was stolen. I mean, thankfully it's not like I've never been in a situation where someone's run up like, you know, credit card debt for me. So, you know, knock on wood, but it's amazing how many times you hear about a giant breach and your first thought to yourself is, well, that's the end of that company.

[00:09:10] **Ben:** And then two years later, that company's doing just as successfully as it ever was before.

[00:09:16] **Tim:** I do know of one company that did finish. Uh, ChoicePoint was a company that did background checks and credit checks and things like that. And they had a very serious data breach and it pretty much sunk them. They got bought out.

[00:09:30] **Tim:** Some other company after that, because just because of that breach.

[00:09:34] **Ben:** Yeah. It, it, it feels though, and maybe this is just what makes it into the mainstream media, but it, it, it feels like that's the outlier at

[00:09:45] **Tim:** this point. Yeah. Yeah. I mean, people have gotten, that was. Pretty early on, so I think people have gotten a little bit more used to it.

[00:09:52] **Tim:** You start hearing about Target and Walmart and you're like, well, I'm not going to stop shopping at Walmart. I mean,

[00:09:58] **Adam:** what can you do? Carry around cash. Okay, well, now that we spent, uh, like, you know, 13 minutes on my, on my Triumph, uh, Carol, what do you got? Yeah, so for

[00:10:10] **Carol:** my Triumph or Failure, I'm going to go with the company Triumph.

[00:10:14] **Carol:** Um. We are kind of balls to the walls right now. Like, we are just over, we're not over committed because the customer knows we can't do the work, um, but we just have a backlog that's never ending right now. And it's not support. It's all new work that needs to, that needs to go out. And my company really does a good job of not putting that stress on us.

[00:10:39] **Carol:** So, you know, they're, they're not like, hey, you really need to rush through this project. You got on your plate because we've got 3 more slammed behind you. Instead, last week, we didn't even have story planning. They just pulled a couple people aside for a tear sheet review that we're going to be moving to a new project and everyone else was like, there's really no point to do a big giant review process because we don't want you to think all this has to get done right now.

[00:11:04] **Carol:** So it's just, it's good that the company culture is. Not stressing you out to, like, keep moving to the next thing. Finish this so you can go to the next thing. It's get this done right. But here's what's coming down the pipeline. So, you know. So, I just think it's a good triumph as a team.

[00:11:21] **Adam:** Heck yeah.

[00:11:23] **Tim:** You bet the people above you, they were freaking out.

[00:11:26] **Tim:** Oh, oh

[00:11:26] **Carol:** yeah. I mean, you know they are. But the fact that they're not pushing that down on the lonely people like me, who just write the code, you know. It's, it's good to not have that stress, to know that you have the time to do it right, you have the time and the resources available. And that's

[00:11:43] **Tim:** why they get paid the big

[00:11:44] **Carol:** bucks.

[00:11:45] **Carol:** Yeah. They can put it on their shoulders.

[00:11:48] **Adam:** Yeah. A good manager is worth their weight in gold for sure. Absolutely. Yeah.

[00:11:52] **Ben:** There was a movie. I can't remember what it's called, but, uh, Hank is area. The movie's about this guy who works at a newspaper. I don't know if it was Spider Man. I think maybe it was Lincoln or something like

[00:12:04] **Carol:** that.

[00:12:05] **Carol:** I know that one.

[00:12:06] **Ben:** Sorry. And this kid, he makes up, like he entirely fabricates all of his stories that he writes for the, for the newspaper. And I think it goes on for years or something. Anyway, that's not the point of what I'm saying. Hank Azaria plays that guy's manager in the movie. And Hank Azaria is, is often in some distant office getting yelled at by his boss.

[00:12:27] **Ben:** And then doesn't allow his writers to feel that stress. And I remember seeing this movie. I mean, the movie is probably like 15 years old or maybe more. And I just, I was young. And at the time I was like, that's, is that what managers do? They protect people below them? I'm like, this is crazy. Eye

[00:12:47] **Adam:** opening.

[00:12:47] **Adam:** Hank Azaria, if people aren't recognizing the name, he's Moe from The Simpsons, isn't he? Mm hmm. He's a lot of voices in The Simpsons. You've seen him in a lot of things, yeah?

[00:12:56] **Ben:** He's great. I love him. I have to

[00:12:58] **Carol:** go look him up. Yeah, a good manager goes far. Very far.

[00:13:04] **Adam:** Cool. So, Tim, what about you?

[00:13:07] **Tim:** Well, last week I had a failure.

[00:13:09] **Tim:** I talked about my struggles with, with Red, I don't know if it's Redis, but my Redis situation with my load balancers. So, I don't, this, I don't really know if this qualifies as a Triumph, but I've just been kind to myself and I've just taken a break from it because it got to the point I was walking around the house angry.

[00:13:30] **Tim:** Oh no. And my wife and kids thought that they had done something wrong and they were worried. Um. Because it's like I was constantly thinking about it. I'm just, it's going through my head and I'm like, all right, I'm taking this week off. I'm going to, I took, I took Monday off. Well, you know, Sunday was the Superbowl.

[00:13:48] **Tim:** I took Monday off just to recover from the Superbowl.

[00:13:51] **Adam:** Are we allowed to say that? Do we have the license to say the word superb owl?

[00:13:55] **Tim:** The big game. Sorry. Beep that out. It's the big

[00:13:59] **Adam:** game. I like to call it the superb owl. The superb

[00:14:02] **Tim:** owl. I took Monday off and then just, I just said, I'm not going to look at this this week because I can't.

[00:14:09] **Tim:** I can't even, so.

[00:14:11] **Carol:** Yeah, and it's not like you're thinking, when you're like thinking through all this, it's not like they're necessarily positive things. Like, when I do that, it's just reinforcing that I haven't got it right yet, or that I still haven't figured it out. So then I'm so frustrated, and then when I go work on it, I start out super frustrated too.

[00:14:28] **Carol:** So it doesn't, so taking a week off, probably a good idea. Yeah,

[00:14:31] **Tim:** once you've deleted and rewritten and re deleted code multiple times, at some point you're like, you know what? Yeah. Yeah. We're stepping away. I'm going to work on something else. Good idea.

[00:14:41] **Carol:** I think that's a good call. Yeah.

[00:14:43] **Adam:** Fresh eyes. I'm going to be more like Ben.

[00:14:46] **Adam:** You said be more like Ben? I want to be more like Ben. We all want to be like Ben. Just install seven more enter keys on your keyboard. You'll be alright.

[00:14:54] **Carol:** Tim only wants to be like Ben because he needs a hater.

[00:14:57] **Adam:** What about you Ben?

[00:14:58] **Ben:** So, I, uh, am, have been addicted to analytics lately. At work, we pipe analytics through, I think a system called SegmentIO, and then SegmentIO, I think, then pipes those same metrics into a bunch of other things.

[00:15:13] **Ben:** I think Segment's sort of like a if this then that, but for analytics distribution. And, uh, eventually, one of the places it goes is, is to a system called Amplitude. And Amplitude's... Just charts everything. And, uh, I recently added some tracking to a particular interface within that application because I was doing some performance refactoring without tests.

[00:15:36] **Ben:** Um, and I was kind of blown away at how many people actually use this part of the app. And it, and it's not like it's a massive amount of people. But nobody ever talks about this part of the application at the company. So I just kind of assumed no one ever used it. Yeah. And now that I threw some metrics onto it and, and it's like, you can see who, how many people opened it, who clicked on this button, who did the pagination, who selected these options.

[00:16:05] **Ben:** And, um, it's just, you see the page come to life. In a way that it, it does two things. One, it really colors the way the page gets interacted with, but it also, it turns individuals into meaningful, emotional data points. And I know that seems like almost like a contradictory in terms, but you know, you know what it's like if a, if a product leader comes to you and says, don't worry about this part of the application, not many people use it.

[00:16:39] **Ben:** And that's the end of the conversation. You have this black box understanding. This is just not an important part of the app, so I'm just not going to focus on it. But then you throw metrics on top of it and now you start to see, Oh, you know, dozens of people clicked on this button and hundreds of people clicked on this link.

[00:16:56] **Ben:** You're like, Oh, these are real people. There's real people sitting at a desk somewhere using the software that I'm building. And no amount of someone pointing to it and saying, this is not an important part of the app, don't pay attention to it. Like no amount of hand waving at that point can remove the fact that I can now see these people, so to speak.

[00:17:20] **Adam:** I'm on call this week, and that was my... My noise where something is, I was like, rude.

[00:17:26] **Tim:** Who's, who's Wawa

[00:17:28] **Adam:** sliding bins conversation. I'm sorry, I was just gonna cut it out. But now that you laughed at it, we have to keep it . Oh, somebody, somebody created a ticket with a priority of 11. So that's why I got it. An alert spinal tap.

[00:17:43] **Ben:** Yeah. These tickets, our tickets go to

[00:17:44] **Adam:** 11 . Yeah. That's literally what it does.

[00:17:49] **Ben:** Uh, so anyway, anyway, my triumph is that I put some metrics. into an interface and suddenly it's this rich, emotional experience for me. And that's cool. I never bothered myself with metrics before because I had a product manager and that was his sort of area of expertise was understanding how people use the application, but he is no longer with my team.

[00:18:09] **Ben:** So I'm sort of picking up the reins. It's time to figure it out. Yeah, it's kind of super exciting. And I sort of feel like I've been missing out on the analytics for the last couple of years. Nice.

[00:18:21] **Carol:** And then analytics is now like your, uh, you're like your support puppy, right? Like the thing you hug that makes you happy, your support animal.

[00:18:30] **Ben:** It's like tracking a FedEx package. Where you're going in every 45 minutes and you're clicking the refresh and you're like, what do you mean it hasn't left Columbus, Ohio yet? And, uh, but now it's, I'm, I'm just seeing a little bar chart go up just a little bit, a little bit, a little bit. Makes you

[00:18:45] **Tim:** happy.

[00:18:46] **Tim:** Yeah. You talk about it's not analytics, but, um, so when our company. Got bought back in 2013 one of the first things a company that bought us Made us as a company do is go to customer on sites as a company I mean just lots of people went not just a lot of times, you know sales people go marketing people go visit customers but it's like developers were going on site to visit customers and it's really different when you see A company using an application that you work in every day and they're using it to run their company.

[00:19:21] **Adam:** I'm really sorry about that. So my phone is actually on do not disturb, but that's the whole point of the thing is it can get my attention no matter what.

[00:19:29] **Tim:** And you see people, you see people using your app and you, and that sound goes to your head because like there's this one lady, there was like some print issue that we had.

[00:19:41] **Tim:** And just. Poor woman, her whole job was just moving stacks of paper from one place to another. And I was like, oh my god, we got, you know, it was a little bug. It was kind of low in the backlog. It really wasn't important that I saw this poor woman, what her days were like. I'm like, uh, we need to fix

[00:19:56] **Adam:** that.

[00:19:57] **Adam:** That

[00:19:57] **Carol:** should be an easy fix, like an easy win. And it would make someone's job so much easier. Totally.

[00:20:03] **Ben:** Yeah.

[00:20:05] **Tim:** Oh, and by the way, Ben, addicted to, uh, analytics is the worst Robert Plant song.

[00:20:13] **Adam:** But, okay, so now that I can actually use my brain again and I'm not distracted by alarms, um, I did have a comment that that made me think of, uh, the, so remember we talked about that, uh, sort of.

[00:20:25] **Adam:** Quasi coverage system I had been working on for our testing to do the platform migration. One of the nice sort of downstream side effects of that is that now we have this tool built into our application that tells us what's being used and how much. So we're just going to leave it in place and it's recording which parts of the application are being used and which parts aren't.

[00:20:44] **Adam:** So when, when we need to decide like what features to work on, what bugs need to be worked on, we have that data to go. Well. You know, who cares? Two people have been in that feature in the last six months. It doesn't matter. Yeah. It doesn't matter as much as the one that gets used by 150 people every day.

[00:21:00] **Carol:** Yeah. Or like a 98% of your users. Yeah. Yeah. Dude, we have a website.

[00:21:06] **Adam:** Well, is, is that your, uh, your poor excuse for a transition?

[00:21:13] **Carol:** Um, I don't know. I'm just reading it says announcement, website.

[00:21:17] **Adam:** Well, I mean, do you not Actually, I think it's a fantastic transition. Do you not pay attention to our Discord where I've been sharing the previews of the website with you guys?

[00:21:26] **Adam:** So,

[00:21:26] **Carol:** I saw you were, like, showing something, but I didn't really pay attention too much. I have a lot going on this week. You're fired.

[00:21:33] **Adam:** Okay,

[00:21:35] **Tim:** hold on. Don't discord shame her.

[00:21:41] **Ben:** Did you just pull a cat out of nowhere?

[00:21:44] **Carol:** I just pulled a cat out of my lap. In my lap. That's where it

[00:21:48] **Tim:** goes. She's

[00:21:49] **Adam:** a magician.

[00:21:50] **Carol:** She jumps up at the like, most inappropriate times and then climbs all over me. Then like, go away.

[00:21:58] **Adam:** Sorry. It's okay. So yes, we have a website, uh, and I'm committing to that now, uh, I'm fortunate enough that we record two weeks ahead of, uh, release.

[00:22:08] **Adam:** So I have the next two weeks to put the final touches on it, but it's close enough now that if I don't get it. Done in the next two weeks, I should be ashamed of myself.

[00:22:17] **Carol:** I don't know, you have three other coders on here, so... That's

[00:22:20] **Adam:** true, and, and... We should be helping! Uh, well, you know, I...

[00:22:26] **Tim:** Did you write tests, though?

[00:22:29] **Tim:** Ben's,

[00:22:29] **Carol:** Ben's in charge of our test suite.

[00:22:32] **Adam:** Um, he'll just manual test it, don't worry. I, so...

[00:22:38] **Adam:** I, I gave you guys some very early looks at the work that I was doing and then as we are getting closer to being ready to deploy it and launch it, um, I've been sharing it in with our patrons and discord and gotten some feedback from them and some help. Wait, we got patrons? We'll get to that later too.

[00:22:57] **Adam:** And they know about our website before us? Well, before you apparently. Oh, snap. Um. And, uh, they have contributed to it. So, uh, one of our patrons, Seb, he, uh, you know, he was pointing out a bug in, uh, Safari and I guess on the iPhone, um, and like trying to help me figure out what the problem was and I was like, you know, if I want, if you want, I can just give you access to the repo and you can make a pull request.

[00:23:26] **Adam:** And he's like, yeah, sure. So he did.

[00:23:28] **Ben:** That's awesome. Cool. I can't see Seb Duggan's name without thinking of Street Fighter. I don't know if anyone else has that association. Seb Duggan! Yeah, Seb Duggan! Seb Duggan!

[00:23:40] **Adam:** See, I didn't make that connection because I always think of it as Duggan. Seb Duggan. Oh, maybe

[00:23:44] **Ben:** that's how it's pronounced.

[00:23:45] **Ben:** I have no idea. But in my mind, it's Street Fighter. Subdugan.

[00:23:52] **Adam:** Uh, okay. Um.

[00:23:56] **Carol:** That's a great episode so

[00:23:57] **Adam:** far. Oh yeah. Um, yes, so we have a website and it's coming soon and, uh, it would, uh, you can listen to the episodes on there. Uh, and it looks marginally better. It was designed half by me, half by whoever I got the free template from.

[00:24:13] **Adam:** Uh, and. What's the tech stack? What's the tech stack? It's on Eleventy, which is a static site generator, um, and it's using Sass for CSS. Yeah, Eleventy. I really like it. So I've done some stuff with Gatsby in the past, and Gatsby has a whole lot of really nice features, especially if you're trying to do something complex.

[00:24:31] **Adam:** But... I've had some complaints of things that have been difficult with Gatsby and, um, the build time is problematic, I would say. I know they're working on it and they have a service that can make it faster, but, uh... A paid service? Yeah. Anyway, but Eleventy, I've been very happy with it. It builds very fast and it's easy to use and it's...

[00:24:57] **Adam:** It's very similar to Gatsby in some respects, um, that you don't get the GraphQL of all your data, but there's other ways to, yeah, I don't know, it gives you some other ways to access your data. So like, for example, the, um, all of our episodes, they're just marked down files in a folder and it It creates a collection of that data that I can loop over to make the episodes pages and it can paginate that or I'm just pulling the the most recent episode from that collection to show on the home page of the site sort of thing.

[00:25:28] **Adam:** So yeah, I'm liking that. Um, and just I guess the page that has the most information on it is the support us page because there's a bunch of different ways you can support us in addition to being a patron. Um, And I also... Emotional support. What's that? Emotional support. Emotional support. We're going to need it here soon.

[00:25:47] **Adam:** And I also, well, one of the things that I've been inspired to put on there, I wanted to be very transparent about what we're spending money on that we you know, maybe can justify needing some support for, you know, like we paid for the intro and outro and we want to get an editor and we want transcripts and blah blah blah, all this stuff in the future that we just can't afford to do on our own right now.

[00:26:08] **Adam:** So, anyway, uh, we have a website, so go check it out, workingcode. dev, and, um, outro of that segment.

[00:26:18] **Tim:** Now we just need listeners.

[00:26:21] **Adam:** Well, you know, like I told you, we have four moms between us, uh, uh, Carole has two moms. Five! I have

[00:26:25] **Carol:** two

[00:26:25] **Adam:** moms, don't forget

[00:26:26] **Tim:** that. So, my mom doesn't listen, she thinks computers are demonized.

[00:26:29] **Tim:** demon.

[00:26:38] **Adam:** Okay, so let's move on to our main topic for the day then, uh, which would be listener questions and feedback. And I think that the, the one we should start with if for no other reason than time is, um, Adam Cameron's blog post. So I mentioned previously, we record two weeks ahead of release. Uh, so by the time you hear this, the, the episode nine is two weeks old and, uh, Adam's blog post went up, I think the day after.

[00:27:04] **Adam:** Today's Thursday. Uh, as we're recording this, so yes, the day after episode nine was released and the post in question will be linked in our show notes in case you would like to go read it. It is a little bit of a tome. It's, he's a long writer, kind of like our very own Ben Nadell and, uh. He has a lot to say.

[00:27:25] **Adam:** And so we should respond to that. So it's tough because I don't just have like a short little question from him or a comment that I can read and then we can respond to here on the podcast. I don't want to like require everybody to go read the blog post and come back to the podcast episode. So, uh, I'll just, I guess say, and you guys can.

[00:27:41] **Adam:** Filled in and, and correct me if I get anything of this wrong, he took issue with some of the stuff that we said he felt like maybe some of it was a little irresponsible about testing, right? About testing, yeah. About testing. Um, and uh, so, you know, he wrote, he basically went kind of shot for, shot through the episode and pulled, pulled out the things where we said things that he took issue with and explain.

[00:28:05] **Adam:** And he's a great tester. He is. He has a lot of experience.

[00:28:08] **Tim:** I would, I would point out he is proving Cunningham's law. Does everyone know what Cunningham's law is? Do you have your own law? Oh, never mind. I do. I do. I have my own law. Actually, no. There really is a real law is. So Cunningham's law is that the fastest way to get an answer on the internet is not to post a question, but to post an answer and everyone will tell you you're wrong and give you the correct answer.

[00:28:31] **Tim:** Right. So we, we did, and I'll be honest, I, I kind of thought our, our episode on testing was kind of lame. I, I do. I don't, I, I, I don't know. I just, I left it feeling like, I don't know if we really covered anything useful there. It's a big topic. It is a big topic. Yeah. But I mean the fact that it got this huge response, this giant blog post from Adam says, Okay, well maybe sometimes being lame is okay because you get, you get a good response

[00:28:59] **Adam:** sometimes.

[00:28:59] **Adam:** Some feedback, yeah. Yeah, the only, the only problem there is that not everybody who listens to the episode will end up finding that blog post to, to get the follow up information. Well they will

[00:29:10] **Tim:** after hearing this,

[00:29:11] **Adam:** so. Yeah. Hopefully.

[00:29:12] **Ben:** I just want to say that, uh, you know, I've known Adam for a really long time.

[00:29:16] **Ben:** Both personally and professionally and, uh, and his tone maybe is sometimes hard to decipher in text, but I, I can assure everybody that everything he says comes from a place of love and, and wanting people to be better and, and, and do better. So. Yeah, absolutely. I think the tone, if, if you don't know him, it sounds very heated and abrasive at points, but, uh, it, he doesn't mean to that.

[00:29:42] **Ben:** Yeah. If you know him, that's just his communication style. Yeah.

[00:29:45] **Tim:** He's a kiwi . They don't make any sense. None of 'em do. So I maybe gives get, gives him haters from, from from New Zealand.

[00:29:54] **Carol:** No, don't do that.

[00:29:56] **Ben:** So, so I think mostly he took issue. And,

[00:30:03] **Adam:** uh, with

[00:30:03] **Ben:** me personally, no, uh, no, he took, he took issue with the fact that I don't test, uh, which you

[00:30:09] **Adam:** said you

[00:30:09] **Ben:** don't test. Right. He took issue with the fact that I don't have automated testing and that. I, at the same time, acknowledge that it's a shortcoming and don't proactively work at being better at testing.

[00:30:22] **Ben:** And there's nothing that I could point to in his post that feels wrong in any way whatsoever. I think where I disagree is simply the magnitude, I think, of the takeaway. Uh, which is that I'm, I'm definitely not anti testing and in a perfect world, I would be better at testing and it would be something that I put focus into, but there's a lot of things that I wish I was better at.

[00:30:51] **Ben:** And I, I just happened to spend more time trying to get better at things that are not testing and...

[00:30:58] **Adam:** Like HTML emails? Yeah,

[00:31:00] **Ben:** yeah, exactly. So I've spent, you know, probably, I don't know, 20, 30 hours of just personal time trying to understand how to write HTML emails better. And that... You know, it could seem ludicrous to someone, but for me, that feels like a worthwhile endeavor at this point.

[00:31:15] **Ben:** And, uh, yeah, everything is, everything is a return on investment calculation. And, um, it's hard because there's almost nothing that I think I could say. Where someone couldn't turn around and say, right, but it would be a worthwhile return on investment. It's just, it testing for me is not the thing that I feel like holds me back.

[00:31:44] **Ben:** Um, so it's, it, yes, I wish I was better at it. I wish I was better at Docker and I was better at networking. There's several things. Yeah. Like I know enough Docker to do my work and I know enough security to. Prevent SQL injection

[00:32:01] **Adam:** attacks and cross site scripting attacks.

[00:32:05] **Tim:** But is it the thing that holds your app back? I mean,

[00:32:08] **Adam:** that's really... That's the question, yeah. It's, it's,

[00:32:12] **Ben:** it's tough because, you know, in, in response to the post, our Adam said that, yes, our Adam said that one thing that I maybe got missed in some of the conversation was that I make small changes. My whole mantra in life is small changes deployed often.

[00:32:33] **Ben:** Right. So, it's not like I spend a lot of time refactoring massive parts of an application where I really want that assurity that I changed this code over here and I'm not breaking something way over here disconnected. 90% of what I do is... I want to change this query that only gets called in one place, or I want to break this one request into maybe a primary quest and then a followup Ajax request.

[00:33:01] **Ben:** So it's less blocking time. The things that I do are very small and very focused. I use a lot of feature flags. And even as I'm saying this, I can hear Adam having his own internal conversation where he's like, you're just excusing it. But I don't feel like I'm excusing it because I feel like I'm very focused on.

[00:33:21] **Ben:** A particular set of things, and those particular set of things, I have, let's call them strategies for success, survival mechanisms that I have in place that I feel like allow me to remain fairly efficient and very bug free without having automated testing.

[00:33:40] **Carol:** So, I want to go back to what you said. You were like, you know, if, you know, if you could hear Adam.

[00:33:47] **Carol:** Objecting to what you're saying and in his 1st, like, paragraph, he lays out kind of, like, what our, like, what his thought is on the show in general. And it's, you know, the water cooler talk. It's us just having general conversation. And when I read this entire post, I could see all of us with 5 or 6 more people, like, at a table, and this conversation just going back and forth.

[00:34:12] **Carol:** And it being Adam just talking to Ben, and Ben talking to Adam, and just, you know, it was, in my head, it played out as just that type of conversation. It didn't come across as attacking at all, and I know that some people may read it to be more harsh. But that was the first thing I thought of when I read this was it was just straight up the water cooler conversation between all of us that we have all the time when we were at conferences.

[00:34:33] **Carol:** Like this was a normal conversation.

[00:34:36] **Tim:** Objective, objective received, right? We did it. So it's the cold

[00:34:40] **Adam:** podcast. Right.

[00:34:44] **Tim:** Okay. Yeah, I totally agree. None of us are experts. None of us claim to be experts in the field, right? We're just people doing our jobs and we're, we're not. You know, some of us have written books, but none of us claim to be, uh, you know, so none of us claim to claim to be experts in this world. We're all working through it.

[00:35:03] **Tim:** And so that's what this conversation is, right? It's a conversation between coworkers, both us four and everyone who listens is involved as well. And I can't disagree. The stuff he directed at me, I can't disagree with any of it. I admitted freely in that podcast that I am a hypocrite. When it comes to testing, I know it's value.

[00:35:24] **Tim:** I wish I did it more. Um, I, I, the line I love is, uh, where he said to where he quotes, where I say that I require unit tests because it gives me confidence, a high level of confidence that what they've done, they delivered what they said they're going to do. And he says, like you say, confidence is fantastic.

[00:35:44] **Tim:** Be fantastic, Tim. Be fantastic, Tim. I can't disagree with that. Any leader should eat their own dog food. And I totally agree with that. And I later admitted that I try my best to do that every time I start a project. But the first casualty of war in the battle for recognizing revenue has been traditionally been, and stuff that I've worked on.

[00:36:07] **Tim:** Testing. Yeah.

[00:36:09] **Carol:** It gets cut first.

[00:36:11] **Tim:** Yeah. It's the, it's the, they're like, well, what do we need to do? Well, you know, we, we, we, we cut those and. And then once you start cutting them, they become less useful because you don't have very good code coverage. And now it's like, well, what's the point of even maintaining it?

[00:36:24] **Tim:** So Adam, I hear you. I

[00:36:26] **Adam:** have to push back because if I don't, then I'm going to get called out for not pushing back. I mean, so I don't think that, uh, having fewer tests is going to make them less useful, but it certainly is going to diminish. The, um, what's the word that I'm looking for here? Well, long term dividends, right?

[00:36:46] **Tim:** Well, let me put the situation to you. You're like, all right, we're, so we're spending X percent of our time writing tests, right? So let's say it's 10, 15 and you, and you say, well, why are you doing that? The manager, someone above you says, why are you doing that? Well, you do that. So you have less bugs. And you can make changes and, and know that you haven't broken something, but then the push comes and now you've, you've, you've cut back on your testing and now there's a bug.

[00:37:09] **Tim:** And now the person's like, well, why is there a bug? You said you're doing these tests for that reason. And you're like, well, you made me stop doing the test, right? So it's becomes a circular argument. I get it. And I agree with what Ben says. I mean, the ultimate goal is what if tests didn't stop bugs, we wouldn't do them.

[00:37:27] **Tim:** So if they didn't prove there weren't bugs, we wouldn't do them. The reason we do them is because we have an expectation that it will lower the amount of, of, uh, of bugs in the system. And so, but if you have a way that does, I mean, Ben's perfectly fine with, you know, small changes, atomic changes, feature flags, so that you turn something on, it breaks, you turn it off.

[00:37:48] **Tim:** Right. Right. So that seems to serve his needs. I can't argue that that's, that, that TDD is.

[00:37:58] **Ben:** In the chat, Carol said something about context being king or context is critical. I don't even know what you're referring to. I apologize. But, but the, the thing about that is that there is nothing, nothing happens in a vacuum.

[00:38:12] **Ben:** So where I work, we're not building airplane operating systems and we're not building pacemakers and we're not dealing with financial data. So there is a certain amount of. Worst case scenario, you know, people aren't dying, which is, I don't, not to be flippant about it, but, but there's a certain amount of, and again, I can just hear Adam being like, stop explaining away.

[00:38:38] **Ben:** But, but the reality is, is, is the, the worst case scenario for a lot of the bugs that I could create are not really that bad in the grand scheme of things. Now, again, you can already

[00:38:50] **Adam:** hear it. Sorry, go ahead. It's just, what a luxury to not be dealing with financial data, not be dealing with people's lives.

[00:38:58] **Adam:** It's, it

[00:38:58] **Ben:** is fantastic. Yeah. I'm not going to lie about

[00:39:01] **Adam:** that. I'm a little jealous.

[00:39:04] **Tim:** Yeah, me too.

[00:39:09] **Ben:** But one thing that I did say in the, in the comments to Adam's post is that, And this is not an excuse, but because I don't have tests that prove that something works or lowers the chances that something isn't working, it forces me to really look at the code and understand how the, the invocation happens across related components.

[00:39:34] **Ben:** And I have to follow requests and look to see, well, this calls this query. And, you know, this request triggers this event and these other things are listening for that event. And there's, there's something I think very valuable in a way that I can't necessarily articulate about being forced to create this robust mental model in my head about how the software fits together, that I might not have had if I could just hit a button and run 200 tests that all said the system's working okay after the code that I changed.

[00:40:08] **Ben:** And I'm not saying that that prevents me from doing something that I shouldn't do, but I think... It helps me think about the software in a way that thinking about units of work maybe wouldn't do. I, I don't know if that's true or not, but it feels like there's this value add of having to understand at a more holistic level, how everything's fitting together.

[00:40:36] **Tim:** I've seen cases where all the tests passed and there are still issues,

[00:40:40] **Adam:** right? Yeah, I mean, that goes back to the, the quote that Ben gave on that episode and that Adam repeated that he found the original source for in his post that, that, uh, you know, every bug in production passed the tests. Right. And, and to, I think, repeat a point that Ben made in his response comment, that that was not meant to.

[00:41:05] **Adam:** Uh, give people an excuse to not test. It was to point out that there weren't enough tests in that situation.

[00:41:14] **Tim:** That's like the only response to violence is more violence. I mean, at what point, at what point do you pull back? I mean, I'm just playing devil's advocate on that one, but. Well, I was

[00:41:24] **Ben:** saying that, that, um, manual testing, it's not an, it's not an either or, which I feel like I was being a little bit mischaracterized in that I was saying that manual testing replaces automated testing.

[00:41:38] **Ben:** The more my point was, even with automated testing, I would feel like I had to also do the manual testing because I'd have to assume that the tests are not 100% accurate. Or just because there's a test suite, I don't know if people are maintaining it. Right. Especially if it's an area of the code that doesn't get touched a lot.

[00:41:57] **Ben:** I sort of have to assume the tests are not doing a great job.

[00:42:01] **Carol:** Yeah, I think I followed up to that and was like, I do that. I write the test and I still manually test because I don't trust that the test caught everything that I'm thinking of. I

[00:42:12] **Adam:** think, so Tim, you had said, like, where does it end? And I think that the textbook reply to that is you, when there is a bug that slips through the testing cracks, you write the test to prevent that bug happening again, that you would catch it next time.

[00:42:27] **Adam:** And, and then you move on and you're, you're never going to get 100% of all bugs caught before they get to production. But you can, if you are super diligent. Only ever have each bug one time. Mm-hmm. And even that, I think is asking a bit much, but Yeah.

[00:42:43] **Tim:** Yeah. And I don't think any of us were saying t that t d d is bad.

[00:42:48] **Tim:** No, I don't think any of us were saying that. It's just, we're just acknowledging the real world's. Yeah. Thing of it is that it's hard. Some people don't do it. Um, it's what it is. And sometimes due to economic concerns, they go by the

[00:43:02] **Adam:** wayside. It's, it's unfortunate, but it's true. It is a

[00:43:05] **Tim:** best practice that people should do.

[00:43:07] **Ben:** So this makes me think of something that I'm always fascinated by. Which is when you hear somebody say something publicly or you read something in a book and you think that you understand what that person was saying. And then years later, maybe you find out that your conception of what they were saying is actually not totally off, but not accurate.

[00:43:29] **Ben:** And I've had this realization twice in my life, very vividly. One was, I went through years thinking that the term Singleton was this terrible anti pattern software because a lot of people are like, Oh, Singletons are horrible, blah, blah, blah. And I was watching a presentation given by Corey Haynes, who's big in the Ruby world, and he was on stage.

[00:43:52] **Ben:** And, uh, somebody called him out about, oh, like, well, singletons are bad. He was like, well, it's not a singleton. It's just a single instance of something. And the other guy was like, well, that's a singleton. And Corey Haynes was like, no, that's not a singleton. That's a single instance of something, which is a very different type of pattern.

[00:44:09] **Ben:** Right. And I was like, whoa. For the last 15 years, every time I've heard Singleton, I've been thinking, oh, having a single instance of something, which is a very common pattern in the ColdFusion world. You instantiate a ColdFusion component, you cache it in the application scope or the server scope, and now you have a single instance of it running for the life cycle that application.

[00:44:28] **Ben:** And literally for like a decade, I've thought to myself, I'm a terrible programmer because I have Singletons all over the place. And everybody says that Singletons are anti pattern. And it was this, just this misconception that I had no idea what people meant when they said singleton. So that was one very vivid thing.

[00:44:43] **Ben:** And if I can just quickly, one other thing, TDD for, for years, when I was learning, not learning about, but like listening to people talk about TDD, it was always like, you write your test first. Test driven development for anyone that doesn't know. Yes. Test driven development. Yeah. You write your test first.

[00:44:58] **Ben:** And then you, your tests fail and then you write just enough code to make your test pass and, and rinse and repeat. And so in my mind, again, for years after starting to hear people say this, you think like, oh, line one of code is people writing tests. And then eventually you listen to an interview with someone who's super heavy into testing and they get into more details about what that means.

[00:45:23] **Ben:** And someone will say, well, how do you start writing tests when you don't even know what your software is going to do yet? Like you don't even know what it wants to do yet. And they're like, oh, well, I wouldn't write tests then. Like I have to understand what the software is going to do. So probably what I actually do is write a lot of sort of R&D code.

[00:45:38] **Ben:** Try to find out what it is that I want my software to even do. And then once I start to understand where I want to go, then I start to write tests. And you're like, well, that's a really, really big difference than hearing someone say, well, the very first thing I do is start to write failing tests and then I have to fix the tests.

[00:45:54] **Ben:** Like, so you, you, you get this massive gap in a way that, that has maybe an oversized impact on the way you think about programming. And, and in the reality is. It's, it's, it's an, it's a false understanding and it's just, it's crazy how that happens sometimes.

[00:46:11] **Carol:** I feel like it's often that we hear about what we do with the sugar coating on it.

[00:46:16] **Carol:** You know, it's the cake with the ice cream on top, but then when you find out how each of us work daily and what we're doing. We may be lucky if we have the ice cream cone at the end of the day, you know, like, there is no sugar in between. You're not getting the ice cream. You're just having to plow through it and make the best out of what you've been given.

[00:46:33] **Carol:** And you know, you may not have an application that your company supports putting type into. Like Tim said, you may not be able to write tests because you don't have that choice. You are told to go make money and produce code that makes money. So, I think that our conception of what we do isn't always exactly what we actually

[00:46:55] **Tim:** do.

[00:46:56] **Tim:** And fixing bugs is professional services, so they're, they're, they're okay.

[00:47:00] **Adam:** Yeah. I didn't really follow that metaphor, but I'm hungry. Yeah, I agree.

[00:47:05] **Carol:** Well, being like a software developer's... Very glamorous, right? I mean, it's all shiny.

[00:47:10] **Adam:** That's why I put on my makeup every day. Yeah. Why I shower once a week.

[00:47:15] **Ben:** Whether you need it or not. That's right.

[00:47:19] **Adam:** Okay. Uh, do we have anything else to say to Adam or anybody else? Adam, thank you for the love. Yes, seriously. So, in the, in the top of my comment, my first comment reply, I said, you know, in all seriousness, with no, no, uh, sarcasm intended, your heart matters. And we appreciate the comment.

[00:47:37] **Adam:** Like, I don't think

[00:47:37] **Carol:** I could, um, like, express, like, how it feels just to have someone respond to it in any way, like, but I, I really love this post.

[00:47:46] **Adam:** Yeah.

[00:47:46] **Tim:** Yeah. Particularly writing, you know, War and Peace.

[00:47:48] **Adam:** Yeah. He obviously cares a lot. He spent a lot of time writing that. He does. He does. All right. Well, I think, uh, we're a little long here, uh, but we have time.

[00:47:59] **Adam:** We can do one more. So this question comes to us from LD2 on Twitter. I'm sorry. I don't know your name. You, you make it very hard to know who you are, but.

[00:48:09] **Tim:** Success. I mean, but score on a three letter Twitter handle. Yeah. Yeah. I mean.

[00:48:14] **Adam:** Uh, but his question is, do we have any thoughts on keeping DevOps and development separate, or should they be intermingled?

[00:48:23] **Adam:** Ooh,

[00:48:24] **Ben:** interesting. This is really, uh, this hits close to home for me, personally.

[00:48:28] **Adam:** Yeah.

[00:48:30] **Tim:** I figured Ben would have some, some feelings on this.

[00:48:32] **Ben:** This is, uh, something that I struggle with a lot, and I've struggled with it for years now, because we moved from a development workflow that used to be everyone just, Had to install their own stuff.

[00:48:45] **Ben:** You know, you, you, you join the company, you got a Google doc on install this, this, this, and if it doesn't work, go ask in this chat channel. And we moved from that to a, here's the Docker compose that you have. And then you pull down all your containers and you hit start and there's your developer environment.

[00:49:04] **Ben:** And then everything in production runs in Kubernetes containers. And there was always this tension between the platform team provides this abstraction of what, of how the software runs and you write the application code. And you can get fairly far without having to worry about the separation, but the more complicated stuff gets.

[00:49:32] **Ben:** You just have to start, even if you don't know how DevOps works, you, you have to start to really understand at least at a high level, how everything fits together, because otherwise you don't even know what questions to ask. You don't understand how CPU utilization gets, um, uh, metered or, you know, like capped or, or the fact that disk IO maybe has a particularly high penalty in a Kubernetes platform or.

[00:50:00] **Ben:** Or how the networking works and how systems can call each other. It, it, it, um, it's, it's one of those things where in a perfect world, I'd be really good at DevOps just so I could do my development better, but I'm really not good at DevOps at all. And it is, and it is actually quite a sore point for me in terms of getting my application to run smoothly.

[00:50:23] **Carol:** So I think I have a little bit of confusion. So. Operations is more of, like, where that lives for us. So operations is, like, the people who handle the hardware, who handle the server side and stuff. But when I think of DevOps, I think of the person who's, like, creating our plans for deployment and the person who's writing the tools that developers are using and is making the decisions on, like, what, what, like, JIRA software we're going to be using.

[00:50:48] **Carol:** Like, those type of things, so I guess I'm curious on what the difference is between, like, the DevOps role and just, like, the operations side of it, or are they typically uniform? And I just don't know that.

[00:51:00] **Tim:** I think if you ask 20 people what DevOps is, you get 20 different answers.

[00:51:04] **Adam:** 25 different answers.

[00:51:08] **Carol:** So is it just everything outside of physically writing the code?

[00:51:11] **Carol:** So is it your, um, your DBAs? Is your DBA on the side of the DevOps? Or, I mean, was that part of it?

[00:51:21] **Adam:** Awkward times. I'm going to say, to answer your question, is a DBA a DevOps person? Stop asking hard questions, Carol. Sorry,

[00:51:29] **Carol:** I thought I could ask

[00:51:29] **Adam:** questions.

[00:51:31] **Tim:** Not,

[00:51:32] **Adam:** yeah, just not hard ones. Sorry, sorry. I'm kidding, you can

[00:51:35] **Carol:** ask whatever you want.

[00:51:36] **Carol:** Like, I feel like they would be more on the side of DevOps, because they're not writing it, we're writing it, we're giving it to them, and they're just deploying it. You know, I'm going, here's what I want done, and they're just monitoring backups, and they're doing

[00:51:46] **Adam:** the other stuff. I'm sure Ben will have thoughts and opinions to correct me here, but, uh, I think it depends heavily on what that role does, right?

[00:51:57] **Adam:** If your DBA, if your company is large enough, you have so many databases, that a DBA is there to, like, find the slow running queries and help that developer fix that and make sure that the databases are being properly backed up and, like, that's all that they're in is, like, SQL and backups and... Yep. CP, you know, where's the CPU on the database cluster going bad right now and that sort of thing.

[00:52:18] **Adam:** I think no, like that's database administration, which is entirely separate. But if you're on like a five person team where everybody has to wear seven different hats. then you don't really have a choice and like that DBA is probably also going to be doing other things that would be considered DevOps, so they're, you know, maybe their primary thing is DBA, but they're doing DevOps stuff too.

[00:52:41] **Adam:** When I think of DevOps, I'm thinking of the glue that holds the application together, the automation that does your deploys and monitoring systems and notifications. And, um, script, anything that's automated, scripted deployments. And

[00:52:59] **Ben:** glue is such a perfect word. That's exactly what I was thinking in my head.

[00:53:03] **Ben:** Hmm. That makes

[00:53:04] **Adam:** sense. Ben doesn't correct. I

[00:53:05] **Tim:** mean, you think about the history of it. I mean, early, early on we had situation and this is the way we developed it. And I know some people did and other people laughed at it, but, um, we didn't develop locally, right? We had a code editor. with some ID that we were using and we would, yeah, we would FTP it or, you know, visual source safe or, you know, some other way to get code to a shared development website.

[00:53:34] **Tim:** Um, and then people would do testing there. So there really was no, so, so we had a department that kept those servers running. Your local was your local and you didn't worry about any like running a web server or local database or anything local. Only thing you had was. Basically a text editor, and so that's sort of how we went for years, uh, and then, and there were problems with that.

[00:53:57] **Tim:** Problems were that, you know, stuff you would write sometimes wouldn't work on the server because of server configuration settings, but that wasn't your problem. You just, you just put a ticket in and they, you know, say, hey, this isn't working, you know, I'm getting, you know, some sort of IIS or Apache error.

[00:54:13] **Tim:** Please go fix this, and you as a coder don't care, right? Things switched, so now we're doing local development first, and now of course you have local development, now you have to have your own, uh, you know, your own Apache, your own web server, IIS, whatever it is you're using, NGINX, that you're using locally, so you have to know how to configure that, or get help from people that know how to configure that, so now your knowledge has to go up, and now things that work locally, or don't work locally, that work or don't work in That's It's a shared development system.

[00:54:46] **Tim:** Well, now you, a certain amount of responsibility comes to you. You got to figure out, well, my Apache file is wrong. My IS config is wrong. My server installation is wrong. So you're doing a lot of troubleshooting yourself. That's a little bit more DevOps y. I still don't think that's DevOps y. That's sort of like...

[00:55:01] **Tim:** Maintaining your own local. DevOps, I think, is beyond a step of having a knowledge of not only the code that runs, but having a knowledge of the infrastructure that it runs on. And that is, that the code is dependent on and being able to understand how those play together. Um, which is, I mean, that's a very, that's a broad skill set, but it's helpful to have because sometimes there are issues where you don't really know where the problem lies.

[00:55:33] **Tim:** You don't know, is it a code problem or is it an infrastructure problem? Yep. And if you have two separate teams that don't even understand each other's languages, which we had for a while, then you have finger pointing that can happen. It's like, well, it works

[00:55:49] **Adam:** fine locally. Yeah. Yeah. I was going to kind of say like the, especially.

[00:55:53] **Adam:** In the last few years, we've seen Docker just kind of go nuts. Everybody's using Docker for so much now, and I feel like it's become almost a core competency of a developer if you're using, you know, if you're using Docker in production, then your people who are writing HTML and CSS and JavaScript have to have some ability to put together a Docker container or to understand how That's how it works so that when it goes wrong, when something breaks, they don't have to rely on somebody who's in three time zones over to be available to fix it.

[00:56:28] **Adam:** And I

[00:56:28] **Tim:** think that's, that's the beauty of containerized OSs that we, that we have is that you can script those, right? So because they're scripted, you know, That if I run, you know, a Vagrant up and it builds, you know, a container, um, or a Docker container, whatever it is you're running on, and I'm running from the same script that everyone else is, my system in theory should be exactly the same as your system.

[00:56:53] **Tim:** So that, that, that's a

[00:56:54] **Carol:** big help. And theory is always the key word.

[00:56:57] **Tim:** Until it's not. Until it's not. But

[00:57:00] **Ben:** to something Tim said a minute ago that hit me in the feels, which is that you, you don't know when something is your fault. And, and this, this is probably my number one pain point, maybe not so much in local development because that tends to be a much more stable environment, but once your code hits production and it's running on top of this massive black box, it becomes very challenging to know where you're causing the problem or the platform is causing the problem.

[00:57:29] **Ben:** And I'm. I could give you so many examples, but one that has been biting us just this week is that I had services that were just restarting and, and I couldn't tell why. And I'm looking in the logs and it's just saying that the, I see the machines restarting and I think, well, maybe it's something, maybe my liveness checks are failing or my readiness checks are failing, or there's something that's throwing an error.

[00:57:56] **Ben:** And finally, I get the platform people involved, and they're looking into it, and they're like, Oh, well, your service is running on top of spot instances from Amazon. And at some point, Amazon can just say, Hey, we're about to take your spot instance back. And they give you two minutes to shut your service down.

[00:58:11] **Ben:** And if you haven't shut your service down in time, it just ends. And I'm like, there's literally nothing in my logs that say, oh, by the way, the machine you're running on is about to be taken from you. And I would never know to ask, especially if I was maybe more timid about asking. And I am actually quite timid about asking the platform people for help.

[00:58:32] **Ben:** Cause I always feel like I'm burdening them with my

[00:58:35] **Carol:** worries.

[00:58:36] **Ben:** Yeah, exactly. They're, they're like these wizards that sit off in the corner making machines just happen. Yeah. And I'm like, I don't want to, I don't want to bother them, but. I, you know, half the time I go and ask them for help. It turns out to be that there is actually quite a significant platform.

[00:58:51] **Ben:** I don't want to call it a problem, but there's a root cause that is definitely outside my code and I would have never found that on my own. Yeah.

[00:59:02] **Tim:** So, I mean, I don't know if we're answering LD2's question, but I mean, I think in a perfect world, everyone would. Most of your team, not everyone, but would be able to understand both the infrastructure side of the world and the code side of the world.

[00:59:20] **Tim:** Um, but to be honest, you're probably going to have people, it's a Venn diagram. Yeah. You know, there's a few people that are completely infrastructure and, and on the server, you know, the platform people has been calls them and people are just a hundred percent code. And there's some people who are somewhere in the middle.

[00:59:36] **Tim:** I've done both jobs. And ran both departments. So I feel like I do kind of fit that middle of the Venn diagram. Um, you know, so I see the value in knowing how to do it, but I understand it. It can be hard. Some, some people it's not their jam. They don't really care about how disks work and networks work and firewalls work.

[00:59:57] **Carol:** So, I don't think you have to think of it as a single person with his question. I don't think you have to think of it as, do you have to know it? Like, should more of, should the teams be united? Like, should a team have

[01:00:08] **Adam:** a DevOps person on it?

[01:00:11] **Carol:** And I absolutely say yes to that. Like, if I can't, like Ben said, if I can't figure out what happened with my code past my code point, I should clearly have someone that understands my application.

[01:00:23] **Carol:** And knows the infrastructure. He doesn't have to know what my code's doing, but he has to know, he or she has to know the entire, like, circle of it all. So I do think that they, I, I can't see a reason why you would keep them separate from each other as a team or as, like, a unity.

[01:00:38] **Adam:** Yeah, I mean, of course, the scale of your company or your team or, you know, whatever, uh, where we're, where we're drawing the boundary around this is kind of ambiguous, but the scale matters, right?

[01:00:50] **Adam:** If you've got 500 people at your disposal, then the organization is going to be vastly different than if you have five people, right? So, but I, to your point, Carol, I think that's an awesome idea to like have that one person that's sort of your designated liaison to that side of, of the, the skill, uh, I can talk that language.

[01:01:12] **Adam:** The spectrum, right? Is that the right word? Yeah. Yeah. I guess spectrum. Um, like that would be, that'd be awesome if you just had that one person that like, it's expected that it's okay if you tap them on the shoulder and say like, I have a problem and I'm not sure. If this is code

[01:01:26] **Carol:** or if it's like, I don't even know, I don't even know the question to ask sometimes I'm going, all I know is a failed and see through me a log.

[01:01:35] **Carol:** So what happened with B? Like, I don't know what to ask. Whereas if I were to take that to one of our, what I consider DevOps. They would be like, Oh, well, at least I know who to go ask, or I know how to get the answer, even if they

[01:01:49] **Adam:** don't know.

[01:01:52] **Tim:** Yeah, I think it's a lot. I think it's going to be more in the developers.

[01:01:57] **Tim:** I could be wrong here, but I think the developer, because nowadays we set more of our own stuff up, we probably have a little more insight into, um, you know, how the code works on our infrastructure. Some of the people that work. In, in platform or, you know, setting up servers and things, they might not know any sort of coding.

[01:02:19] **Tim:** Right. Other than maybe some sort of scripting deployment language or something. So then they put in PowerShell. Yeah. Yeah, running things in PowerShell. So it's like, yeah, being able to know the right questions to ask and at least being able to troubleshoot it down to the point where you have eliminated other things because, you know, you don't want to be bothering them kind of.

[01:02:40] **Tim:** Right. Like Ben said, he feels bad asking them, right? You don't want to say, oh, I'm sorry, it was a stupid question because I just missed something. Forgot a semicolon, you know, whatever, um, so if you can get down to the point where you go, look, I've eliminated, and that's typically what I do. If I do need help, I will say, look, I've eliminated this, this, this, this, and this.

[01:02:59] **Tim:** The only thing I could think it can be is like, this is a network configuration error. Like we had something, it was just stupid. We have a web application firewall that we have in production, and it blocks certain things that look like SQL injection. We don't have it in development for some reason and, and this request, persons like this keeps dying.

[01:03:17] **Tim:** Why, why can't we, you know, process these, these credit cards and turns out, you know, someone had some, you know, little Tommy drop tables, um, was trying to make a payment. So, you know, that was the whole reason I'd spend a half a day on that. So, yeah, the, the

[01:03:34] **Ben:** WAF, the web application firewall stuff is particularly.

[01:03:38] **Ben:** Frustrating because it's, it's such a black box, meaning that even when the WAF is blocking a valid request and then someone has to go and fix it, I don't even know where that gets done or why it only seemed to apply to some users and not to others. And not all. Yeah.

[01:03:58] **Tim:** And then you ask, well, what block did they say?

[01:04:00] **Tim:** Well, that's a 600 error. Okay. Can you tell me what particularly in this request was the 600?

[01:04:08] **Ben:** So I guess maybe my overarching thought here would be that as a developer and someone who primarily does development Having a vague notion of how the system fits together has been very important, but my understanding is really very shallow.

[01:04:29] **Ben:** But it's just deep enough to know that some things are probably not my fault and that I should go ask for help.

[01:04:39] **Tim:** But yeah, LD2, if you can get some folks that are true DevOps and know code and infrastructure. Get them. Get them on your team, because they can at least be the translator for those two departments, if they are separate.

[01:04:53] **Adam:** You have your

[01:04:54] **Carol:** unicorn.

[01:04:55] **Ben:** Mm hmm. I love the idea of this sort of mythical, vertically integrated team. We have people assigned to a project or service and they have a DevOps person and a designer and back end people and front end people so that they can all sort of swarm onto tasks and understand them super holistically.

[01:05:17] **Ben:** I've never been on a team like that. No,

[01:05:20] **Tim:** not once.

[01:05:21] **Ben:** Not once. I did, I, for a brief, beautiful moment, I was on a team that actually had an embedded, SRE, Site Reliability Engineer, which is sort of synonymous with DevOps. And he was on our team, I think, for like a month and then he left. But it was, it was a beautiful month.

[01:05:44] **Tim:** Thank you for the question, LD2. Yeah. Absolutely. Write in, let us know your name. Followed you for years on Twitter and I have no

[01:05:51] **Adam:** idea. Yeah, we've

[01:05:52] **Carol:** been following each other a while. We had to have met at a conference or something.

[01:05:56] **Adam:** I'm sure we have. All right, well, uh, let's thank our patrons and get out of here because we've been recording for almost an hour and a half now, um, and we still got to do the after show.

[01:06:07] **Adam:** So if you are unacquainted, if this is your first episode listening, then, uh, you should know. We, after we sign off here, we're going to keep the microphones going and, uh, keep talking about random stuff. I have a question that I'm going to be asking Ben. But, uh, so the after show is something that, uh, we provide to some of our patrons.

[01:06:24] **Adam:** And, uh, it's just our way of thanking them for their financial support to help the podcast keep going. And we got some other benefits, like we have a Discord, and, uh, they get early access to new episodes as soon as they're done being edited. And, and of course, uh, we have to thank our top patrons, which right now is just Monte Chan.

[01:06:40] **Adam:** But Monte. Monte! Our MVP. Beautiful legend. Thank you very much. Um, and I checked earlier. Last I looked, we only had... Last I looked, we had, I think we were up to seven, uh, reviews. Yeah, ratings. Like, ratings, yeah. Ratings on iTunes. Still no reviews, nobody likes us enough to actually say anything about us, but they'll click a little five stars.

[01:07:03] **Carol:** Or they don't like us enough to click one.

[01:07:09] **Adam:** Did somebody do that? No,

[01:07:11] **Carol:** I'm saying, like, that's a good thing.

[01:07:14] **Adam:** Okay. Right? I'm not following, but that's okay. Like, nobody's

[01:07:18] **Carol:** clicked one, so they must like us a lot. They don't dislike. They don't dislike us. Did I

[01:07:22] **Adam:** say it

[01:07:22] **Tim:** wrong? Yeah, you said they don't like us enough to click one. Oh, yeah,

[01:07:25] **Carol:** they don't unlike, dislike.

[01:07:27] **Carol:** Yeah, keys, English, password. Words are hard. Words are hard. I've been writing codes all day. You don't need English for

[01:07:35] **Adam:** that. Thanks to my mom and Ben's mom and Tim's mom and Carol's moms. For your ratings and you know, the a a few more out there apparently. But, uh, yes. Anyway, uh, , this is like the worst Patreon spot ever.

[01:07:51] **Adam:** Um, so let's just do this. Uh, so thank you everybody for listening. Uh, if you would please share the show with a friend. The word of mouth referrals is probably the best way to get somebody to listen to a podcast. Uh, and you can help us other ways by, uh, telling the algorithm to boost our signal. By leaving us a rating or, you know, if you think we've earned it, you could consider supporting us on Patreon.

[01:08:14] **Adam:** It's patreon.com/WorkingCodePod. And you can send us your suggestions or comments or angry blog posts to us on Twitter and Instagram @WorkingCodePod. We'll catch you next week. And until then, Tim, your heart matters. You can

[01:08:31] **Ben:** still say it with me. Oh, yeah. I thought we tried that. It was

[01:08:34] **Adam:** terrible.

[01:08:35] **Adam:** We'll do it again. Right. And remember guys, your heart

[01:08:39] **Carol:** matters. No, just use

[01:08:41] **Adam:** Tim. This is terrible.

[01:09:07] **Adam:** So, if you are unacquainted, if this is your first episode listening, then, uh, you should know. We, after we sign off here, we're gonna keep the microphones going and, uh, keep talking about random stuff. I have a question that I'm gonna be asking Ben, uh, and, uh, I'm gonna cut this out because I don't know what I was gonna say there.

[01:09:27] **Adam:** It's

[01:09:27] **Tim:** gonna get, it's

[01:09:29] **Adam:** gonna get crazy, y'all. Y'all. You Southerners. Y'all.

[01:09:33] **Carol:** We're from Georgia if you didn't know.

[01:09:35] **Tim:** We are from Georgia.
