---
title: "009: Testing"
description: This week, the crew talks about their own views and experience with testing; and, how they currently implement testing at work.
date: 2021-02-10
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/009-testing/id1544142288?i=1000508459735"></iframe>

There are very few people in the programming world who will argue against the idea of _testing software_. But, when it comes to the **mechanisms though which code is tested**, the conversation starts to get interesting. There are those who feel that TDD - Test Driven Development - is "the way"; and, that any divergence from TDD is not only laziness but is, in fact, borderline malfeasance. At the other end of the spectrum are the people who perform all their testing manually; often, relying on QA (Quality Assurance) teams and smoke tests to find regressions before each deployment.

Most people sit somewhere in the middle of these extremes. This week, the crew talks about their own views and experience with testing; and, how they currently implement testing at work. Ben swings heavily towards the manual testing end of the spectrum; Adam and Carol swing heavily towards the automated end of the spectrum; and Tim, who often feels very hypocritical, sits somewhere in the middle.

## Your hosts

- Adam Tuttle -- [Twitter](https://twitter.com/adamtuttle), [Website](https://adamtuttle.codes)
- Ben Nadel -- [Twitter](https://twitter.com/bennadel), [Website](https://www.bennadel.com/)
- Carol Hamilton -- [Twitter](https://twitter.com/k_Roll242)
- Tim Cunningham -- [Twitter](https://twitter.com/timcunningham71)

Follow the show! Our website is [workingcode.dev](https://workingcode.dev) and We're **@workingcode.dev** on [Bluesky](https://bsky.app/profile/workingcode.dev). New episodes weekly on Wednesday.

## Triumphs & Fails

- **Adam's Triumph:** He's been working hard to get his company's application migrated over to a new open-source software stack. And, as of this recording, he's successfully moved 9 of his 13 production servers over to the new setup; and, everything seems to be running smoothly! He's feeling very strong on hitting his goals of migrating the rest of the servers by the end of January.

- **Ben's Failure:** This week has been _kicking his butt_! He hasn't been sleeping well, he can't get comfortable in his chair, and everything seems to hurt. He's carrying a boat-load of tension in his neck and shoulders and he just can't seem to get past it. The only saving grace is that he can use his "standing desk" controls to select the perfect height for _sitting_.

- **Carol's Failure:** She's also having a tough time getting comfortable! Her body hurts from her tail-bone up to her head; and, the heating pad she's using just ain't doing it. She's currently on the hunt for a new chair that might help offer some relief. But, being the Amazonian warrior that she is makes things a bit more challenging. As she says:

  > I can't help it - I have six feet of legs and they have to go somewhere!

  And, as the icing on the cake, she accidentally deleted the configuration settings for _all seven of her home networks_. She had automatic backups configured; but, she accidentally turned them off 3-months ago.

- **Tim's Triumph:** It's been a while since he was able to get into a groove; but, this week, he finally achieved **flow state**: that moment when the world disappears, time loses meaning, and all you can see is the code in front of you as it appears to pour out of your hands without effort or thought. He summed this feeling up quite nicely:

  > I feel less like I'm pushing a stone uphill and more like there's a river just flowing through me.

  I mean, come on, he even wrote a Regular Expression!

## Notes & Links

- [Pure Function](https://en.wikipedia.org/wiki/Pure_function) - a function that produced no side-effects; and, whose outputs are determined entirely by its inputs.
- [CFML](https://www.lucee.org/) - ColdFusion Markup Language, a language specification for one of the most powerful web application runtimes.
- [Jest](https://jestjs.io/) - a popular JavaScript testing framework.
- [Unit testing](https://en.wikipedia.org/wiki/Unit_testing) - a low-level test of an individual unit of code.
- [Integration testing](https://en.wikipedia.org/wiki/Integration_testing) - a mid-level test of a group of software units running together.
- End-to-End / Functional testing - a high-level test of an entire software system, typically looking at happy paths through an application.
- Manual testing - using human to run tests on a piece of software.
- Automated testing - using computers to run tests on a piece of software.
- Static testing - evaluation of code without having to execute it (think linters and strongly typed languages).
- Testing budget - a concept in which the tests that can block a deployment have to run within a certain time window.
- [Rich Hickey: YouTube](https://www.youtube.com/results?search_query=rich+hickey) - please, just go watch all of his videos.
- [Software regression](https://en.wikipedia.org/wiki/Software_regression) - a bug that appears, and often breaks, a previously-working piece of code.
- [Guillermo Rauch](https://rauchg.com/) - CEO of [Vercel](https://vercel.com/).
- [REST Assured](https://rest-assured.io/) - a testing framework for application APIs.
- [Gatling](https://gatling.io/) - load testing software.
- [Feature flags](https://launchdarkly.com/features/feature-flags/) - tooling that allows you to turn parts of an application on or off without having to redeploy it.
- Strangler pattern
- [Ben Nadel: My Personal Best Practices For Using LaunchDarkly Feature Flags](https://www.bennadel.com/blog/3766-my-personal-best-practices-for-using-launchdarkly-feature-flags.htm) - a tome that Ben wrote on how he uses feature flags.
- [Kent C Dodds: Testing JavaScript](https://testingjavascript.com/) - a popular online course about about testing JavaScript.
- [EggHead.io](https://egghead.io/) - a popular subscription service that provides tutorials on web application development.
- [MockBox](https://testbox.ortusbooks.com/mocking/mockbox) - a module within TestBox that allows the internal execution of a software module to be observed.

If you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/009-testing.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:14] **Adam:** All right. It's show number nine for February the 10th, 2021. And today our, and today our topic is going to be testing. Don't laugh at me. Yes, I flubbed. Uh, but before we get into, yeah, well. Before we get into that, let's do our triumphs and fails. Uh, Ben, how about I come to you first? What do you got? Sure,

[00:00:34] **Ben:** I, uh, I'm gonna go with a fail this week.

[00:00:37] **Ben:** Being just that I'm exhausted and I've felt exhausted all week and I can't really chalk it up to poor sleeping or anything. I, I just, I feel mentally disorganized. I feel like I'm not, uh, managing my time very well. And I'm also just having a lot of trouble getting comfortable in my chair. I have a lot of, uh, soreness kind of just in my neck and in my shoulders.

[00:00:59] **Ben:** And I don't know if I'm leaning back too far or not leaning back enough from the height of my desk is wrong. Quite sure what it is. You're just too

[00:01:07] **Adam:** swole, bro. You need to lose

[00:01:09] **Tim:** some muscle mass. You're too

[00:01:11] **Ben:** swole. I, I just, I don't know. I keep, uh, I mean, this is the best thing about having a standing desk, uh, is that I never stand, but I always have a perfectly heighted desk for my chair.

[00:01:24] **Carol:** It is great for people with long legs. There you go. To sit down

[00:01:27] **Ben:** at. I'm constantly adjusting quarter inch this way, quarter inch that way. Trying to find that sweet spot, but, um, yeah, it's just been, it just felt like a long week.

[00:01:38] **Carol:** Man, I'm going to follow that up because I am right there with you. Um, I actually tweeted and was like, Hey guys, who has a desk chair that they love?

[00:01:48] **Carol:** Because I am to the point where I need to go buy one. Like, I have the same failure as you. I am on a heating pad with my neck and shoulders because I... It just hurts from my tailbone up to the base of my head. And I just feel like I'm kind of falling apart. And I can't get my desk up high enough to where it needs to be or low enough.

[00:02:08] **Carol:** I don't know what's going on. But right now... That's what you get for being

[00:02:11] **Adam:** such an Amazon, Carol. I can't

[00:02:13] **Carol:** help it. I have six feet of legs and they have to go somewhere, okay? Like, right now, like, if you guys could see me, I have... Push my desk chair into the foyer and I have a stool at my desk sitting on it.

[00:02:26] **Carol:** I have the kitchen chair in here. I have my kid's desk chair in here because I'm trying to literally find anything that will relieve the pressure off my shoulders and off my neck and it's just, it's not working. I can't sleep. Yeah, it's not fun. And, uh, The other failure I have besides that is I updated my Ubiquiti hardware and I got the warning that says, hey, you know, don't forget this firmware.

[00:02:51] **Carol:** You really need to do a backup. I was like, sure, I'll do a backup and then forgot to do the backup and said, yeah, sure. Let's keep going. And I lost everything. And this isn't like just, oh, what's your network? You don't have your passwords. I have seven networks in my house. And everything is subnetted off.

[00:03:09] **Carol:** So like none of my IO devices know anything about my computer, our phones are separate, like everybody is on their own things. So nothing knows about each other. So I'm like, Oh, this is going to take my entire weekend to fix. That sucks. So yeah, that was not, not a fun day of fixing.

[00:03:29] **Adam:** I love ubiquity, but yeah, that's.

[00:03:32] **Carol:** Imagine, yeah, imagine having to redo every tag you have, every setting.

[00:03:37] **Adam:** Can you, once you do get it back on its feet, is there like a way you can do a backup at that point so you don't have to remember to do it before

[00:03:43] **Carol:** you? Yeah, and I had automatic backups on, but apparently I had turned it off at some point, so the last backup was like three months ago.

[00:03:52] **Carol:** So I was like, well, just starting over, I guess. It's not really going to help me much right here. Yeah, failure.

[00:03:59] **Adam:** Well, good luck with that. I'm gonna, I'm gonna jump in here and go next because... Uh, I'm just real excited, and also I feel like I usually go last, so, um, jump in here. Uh, I know on, like, pretty much every show, maybe there was one or two where I had my triumvirate fail with something unrelated to this big migration that my company has been doing.

[00:04:20] **Adam:** And I'm not saying that this is going to be the end of it, but this is a big one. So, uh, today and yesterday we, uh, have been deploying all that migrated code to production. We have 13 customer servers at the moment and nine of them as of this afternoon have been moved over to the new The whole new stack, um, in production.

[00:04:44] **Adam:** We have the last four we'll do tomorrow. And, you know, it's not without, it hasn't been without some, some frustrations and some bugs, but we expected that, right? You know, we... Made the conscious choice to go to production knowing we didn't have a hundred percent, um, you know, everything tested and we just figured, you know, we've got the critical paths covered.

[00:05:06] **Adam:** We've, you know, we know that credit cards can be charged and that, you know, information is not going to be lost and the, the things that break, you know, we'll fix them. Debug it live. Right. And, and of course, uh, you know, 4. 45 this afternoon. Uh, You know, something came up and I'm sitting here like trying to smash through it and get it fixed so I can go eat my dinner and get back in time to record the podcast.

[00:05:29] **Adam:** So, it's happening. We're going to production and I'm just so excited. And I haven't mentioned this yet, but we're recording. It's still January. It's January 28th. So, we are, it looks like, knock on wood, probably going to hit that deadline of the end of January to get all these boxes moved over to the new code.

[00:05:52] **Adam:** So, super, super psyched. Congrats, bro. That is awesome.

[00:05:57] **Ben:** So, what do you have? Do you currently have? The old servers and new servers all running behind a load balancer or something?

[00:06:03] **Adam:** Yeah, so it's all it's all behind an Amazon ALB and the strategy for deployments was basically we're using a mix of like large instances and mediums and the some of them are on the bursty CPU stuff so you don't get a you you Um, when your server is less active, you're like accruing credits and then when it's more active you're, you're burning those credits.

[00:06:26] **Adam:** And the thing that drives me nuts about Amazon, those bursty instances, is that you start with zero credits. So if you turn the server on and you need to start using it immediately, then you're, basically, it, it looks and feels like you're at zero. A hundred percent CPU utilization because you don't have a CPU to use, basically.

[00:06:46] **Adam:** And so the, the strategy after we kind of figured out what's going on there is. We boot them up like the night before we're gonna start putting them into production and just let them sit there and accrue credits for 12 hours with nothing going on. Um, and then we can put them into rotation. And yeah, it's all behind the, an ALB.

[00:07:07] **Adam:** And so we get it ready and we add it to the, uh, ALB and like rotate the old one out. It's still hot. And if something were to go catastrophically wrong, we could. Swap them back, uh, you know, in a minute or two of ALB config. Very cool. And then once everything's happy, we shut the old one down. Nice. All right, Tim, what do you got?

[00:07:32] **Adam:** Well, you know.

[00:07:33] **Tim:** Besides you losers, Ben and Carol, I had a great week. I mean, I'm tired, but you know, today, today I realized I was, it was six hours that had just gone by in a blink of an eye, and I realized for the first time in a long time, I hit the flow state. What? Oh yes. And I, and you know that moment when you know you're in, it's like, you know, when you know you're in a dream and you're like, I have control of the dream.

[00:08:01] **Tim:** And I was like, I know, I knew I was in the codes, the flow state, and it just felt so good because it'd been so long working from home is new to me and, and there's so many distractions. And, uh, today I was just, I don't know, I was firing on all cylinders. I, and, and this is what impressed me. I thought of you, Ben, actually, because I wrote.

[00:08:22] **Tim:** I debugged and wrote a brand new regex statement. I hate regex. But I thought, you know, like Ben would be so proud of me. I wrote this giant regex and it worked. I was so

[00:08:36] **Adam:** proud of myself.

[00:08:37] **Carol:** So I just got a little giggly because I just imagined Tim sitting there That's completely focused and doing nothing but daydreaming about Ben.

[00:08:47] **Adam:** That

[00:08:47] **Tim:** is most of my days. Yeah. That's true. I have to

[00:08:51] **Ben:** say literally not a day goes by where I don't use regular expressions.

[00:08:56] **Carol:** They are amazing. They're really powerful, but they like, my brain just can't process it. I have to go Google and be like, how do you do this? And then when it works, I'm like, magic.

[00:09:09] **Ben:** What I find that they really shine is in just searching through my code base, searching for method calls and stuff and other kinds of, you know, like this token followed by between zero and 30 characters. And then this other token to try and find various, uh, invocation patterns and stuff.

[00:09:28] **Adam:** Yeah.

[00:09:29] **Tim:** I was proud of myself.

[00:09:30] **Tim:** So yeah, I hit the flow state. And it may not happen again in a while,

[00:09:36] **Adam:** but it's good. I was trying to think about like how, how you could describe the flow state. And for me, the only thing I can think of as a way to like illustrate it is I can compare it to how I feel when I'm like way over caffeinated.

[00:09:50] **Adam:** Like, you know that feeling when it's like, I've had, you know, nine cups of coffee today, and now I can see inside out through time, and I don't have any blood left, just vibration, and I'm gonna go alphabetize the alphabet, because it's all wrong, I'll explain later, and then I'm gonna go fight the moon.

[00:10:07] **Carol:** I, uh, that's not that way for me.

[00:10:10] **Carol:** That kind of just sounds like a high.

[00:10:13] **Adam:** That sounds awful.

[00:10:15] **Carol:** I want to be

[00:10:16] **Adam:** there, Adam.

[00:10:17] **Tim:** Mine is very, very zen like. It's like I don't even realize time is passing and I'm writing things that are working without even putting forth, I feel like, effort. Yeah. And, uh, yeah, that's what it is for me.

[00:10:31] **Carol:** Yeah, I'm more like, more like you, Tim.

[00:10:32] **Carol:** I find myself, I'll sit down and start coding, and I kind of just feel like that giggly bobblehead, like the little bobblehead thing's going on, and everything's just moving, and then all of a sudden, my kids are home and asking about dinner. And it just went from starting to all this got done and I didn't even realize I forgot to eat lunch.

[00:10:51] **Carol:** Like I just went through it and just never

[00:10:53] **Adam:** moved.

[00:10:54] **Tim:** I think the analogy I would use for me is I feel less like I'm pushing a stone uphill and more like there's a river just

[00:11:00] **Adam:** flowing through me. Yeah. Hey, that's a

[00:11:02] **Carol:** really good one. That one

[00:11:03] **Adam:** works. Yeah. All right, so I'm the only one here that gets high off of coding.

[00:11:07] **Adam:** Got it. And we have

[00:11:09] **Carol:** never once considered fighting the moon,

[00:11:11] **Adam:** so yeah. I mean, to be fair, I aim for extreme over caffeination on any given day, so. Hence

[00:11:19] **Carol:** the Mountain Dew. Yeah.

[00:11:21] **Adam:** So what are we talking about today? Let's talk about testing. And so I think maybe up front we should acknowledge, you know, we're not testing experts.

[00:11:29] **Adam:** None of us, as far as I know, have been to like testing college.

[00:11:35] **Adam:** I think

[00:11:36] **Carol:** we've already decided that Ben's code is always good and he never tests

[00:11:39] **Adam:** anything. Right. Ben's code is the definition of correct. Half of that statement is

[00:11:43] **Ben:** true.

[00:11:48] **Adam:** And, uh, so, I guess, really, I just wanted to preface that and say, like, You know, there's a good chance we're gonna get something wrong, and if we do, then let us know. Hit us up on Twitter. Let us know. We need

[00:12:01] **Tim:** some haters, guys. There's way too much love out there.

[00:12:06] **Adam:** Somebody find

[00:12:07] **Carol:** that monster already.

[00:12:11] **Adam:** Uh, so why test? Why should anybody test their code? I mean,

[00:12:16] **Carol:** cause it's what we were told to do. Right. People yell at me when I don't test it. I mean, they really get mad if it goes live, and then things just start busting. It works on my machine. That's good, man. Yeah, that's typical.

[00:12:33] **Adam:** Well,

[00:12:33] **Ben:** I don't do a lot of testing, so maybe I'll, I can jump in and just say why I don't test.

[00:12:39] **Carol:** Like, you test nothing. I

[00:12:41] **Ben:** test nothing. And that's not, it's not like a philosophical approach to life. It's more just, I'm not good at testing. So I, I, I will caveat and say I test manually. I test everything very manually. Yeah.

[00:12:54] **Carol:** So like if you change something on a page, like do you load that and then just make sure that your code doesn't throw like a giant error on the page?

[00:13:02] **Carol:** Yeah,

[00:13:02] **Adam:** basically. Okay. Okay. So, I love you. And that's okay. Thank you, Bid. Yeah. Yeah, I mean, clearly it's working out pretty well for you. You got a good career going, so it's not, it's not that you can't succeed in this industry without testing. I, I, I, you know,

[00:13:18] **Ben:** it's, it's, I don't want to say anything without adding maybe some additional context.

[00:13:23] **Ben:** Okay. I work on a very small team. Two, all the people who work on my team are very, very familiar with the software. Three, we will never, ever hire a new engineer specifically for my team. Cause I'm, I work on the legacy code base. The legacy code base is in the process of being phased out. Uh, I mean it's eight years old, so it's not like this is a flash in the pan phasing out of code.

[00:13:50] **Ben:** Um, but there's... I am definitely in a context where I don't have to worry about hiring a new person and then training them up on a system and then thinking that they'll touch something in the code that they don't understand how it works. That's. That's like the farthest possible thing from my day to day operations currently.

[00:14:11] **Adam:** Sure.

[00:14:11] **Carol:** You just killed so many people's dreams of getting to work with you. Do you know that?

[00:14:17] **Ben:** Well, there's still opportunity, just not on my tiny little four person team.

[00:14:21] **Adam:** Like my

[00:14:22] **Carol:** heart's broken

[00:14:23] **Adam:** right now. Plenty of other positions I'd envision. Absolutely. Um. So, now, would you say, Ben, that, uh, you guys have, or even you personally, have experimented with testing and just not found a productive workflow, or you just never bothered?

[00:14:41] **Ben:** Here, uh, I can wrap my head around testing when it comes to testing a, uh, a data workflow that is completely pure, meaning you have a function or a component that has functions. And you give it some inputs and it generates some outputs. I can 100% wrap my head around testing that. And sometimes actually when I'm writing code that deals with something like that, even though I'm not writing tests per se, I might write a scratch file that instantiates that component and sends data to it and checks the output, just during the development process that I don't have to actually load the whole application.

[00:15:17] **Ben:** Where it breaks down immediately for me. That is when I have to either A, involve a database, or B, involve a user interface. And I know that there's all kinds of stuff that the industry has brought to cater to those problems. I've just never taken

[00:15:36] **Adam:** the time to learn. But if I could restate my question a little bit, like, did you, have you guys experimented with any testing tools?

[00:15:45] **Adam:** And so I know that your stack is primarily CFML. Correct. Um, have you guys experimented with any tools? And I guess this, I'm leading here, uh, because we have, and we are in a similar position with our remaining legacy CFML code, where... 90% of the testing is very manual, and it's for a certain reason, and I'm wondering if we're on the same page there.

[00:16:06] **Adam:** I

[00:16:08] **Ben:** think, you know, we had, uh, way back in the day, I think we had tried MXUnit, which was sort of the, one of the popular frameworks. And then, um... I think, I don't know, yeah, I don't think we ever got past that. I will say, I don't want anyone to think that nobody at my company tests. Lots of people at the company test.

[00:16:31] **Ben:** They're just not on my team.

[00:16:34] **Adam:** Um, okay, well, I mean, I guess I was trying to lead you somewhere and we didn't really get there, but, um, The, the reason that we don't have a whole lot of automated tests for our CFML code is simply performance. So when we started our product, um, we, I wrote, I tried really hard to do TDD.

[00:16:55] **Adam:** I had, if I was writing a new, uh, module or a new section of that module, I would work on code or work on tests along with the code and try to stay ahead of the game there. Um, and what ended up happening was I had, you know, for my Let's say 500 functions that could run. I had 400 tests and, and I don't, I don't want to point a finger in any particular direction, but when you take the stack as a whole and you say, okay, now run my test suite and it takes 10 minutes to run those tests and your product is still in its infancy.

[00:17:33] **Adam:** My, my product and the project that I was working on, and you can see this long road of so much more work that has to be done and all the tests. And it takes 10 minutes to run the tests, uh, you know, early on, there was no way that that was going to be sustainable. And so we kind of abandoned hope there.

[00:17:48] **Adam:** And, uh, I have in more recent years and on a more recent stack seen way better performance of tests, um, specifically in my case on Node. js and like using Jest and testing library, um, and on the UI side with React. Um, and. So we are starting to get more into automated testing and finding it actually really helpful.

[00:18:16] **Adam:** And so I, I, I guess what I wanted to say there is that the, a perfectly valid reason to have few or no tests is if it doesn't work well on your platform. Like, I don't want to point fingers necessarily at, at CFML. Maybe it's, uh, in my opinion, uh, maybe it's the JVM's fault, right? Maybe the JVM is just. Not well suited to the type of programming and testing that I was doing.

[00:18:46] **Carol:** Maybe, but so I wrote, um, an application in C sharp and whenever you would actually run the entire test suite, like it gets ran at check in, it doesn't, you don't run it every time. You only run your tests on whatever functionality you're doing. And then there's full on like deployment tasks. And then there's the check in tasks.

[00:19:04] **Carol:** So those tests still take, you know,

[00:19:12] **Carol:** So, yeah, I think it's just depending on how you're running your tests when you're doing it too.

[00:19:16] **Adam:** And I think another part of that too is something I wanted to get into later in this conversation, but it's, uh, it was still a kind of naive or naive approach in my testing strategy that early on. I didn't really have a.

[00:19:30] **Adam:** Good understanding of the difference between like unit tests and integration tests. And I was trying really hard to have unit tests for everything. And some of those unit tests were like, uh, called this function and then go check the database and make sure that the data was changed in the way I expected it to be changed.

[00:19:44] **Adam:** And that's really integration. Yeah. Yeah. And not only that, but the, the amount of it I was trying to do was just too much. Yeah. Um, and so, yeah, it was, it was just bad all around part, partly bad tests, partly slow. So,

[00:20:02] **Carol:** yeah, but I, I also want to say that if you are starting out and you're, you're starting to add tests, don't let slowness stop you from doing it.

[00:20:11] **Carol:** Like, don't let something be like that, that processing time or it taking the extra time be the, the only reason why you aren't willing to keep moving forward with it.

[00:20:21] **Ben:** Well, let me, let me gently push back against that for a second and, and it's not so much a pushback as it is a thought that I had. Just this morning, and I, and the phrase, uh, testing budget popped into my head.

[00:20:37] **Ben:** I don't know if anyone's ever heard the phrase error budget,

[00:20:41] **Adam:** uh, which is... I've heard the phrase, but I forget. It's

[00:20:43] **Ben:** this concept where, uh, I'm sure I'm going to mangle it. Um, but essentially... Your system has an SLA, a service level agreement, you know, degree of uptime that it has to adhere to. And, and you have a certain budget in terms of the errors and the downtime that can be produced in a, in a particular period.

[00:21:03] **Ben:** And if you exceed that, then typically what could happen is, is, uh, like you can't deploy. You've, you've exceeded your error budget for the week or the month. Something that's taking you over your SLA. So the idea is you can't deploy again because a deployment might introduce new bugs, which would push you further over the SLA.

[00:21:23] **Ben:** And I was thinking about, I was thinking about debugging incidents. And getting a page in the middle of the night and having to jump on a call. And you see the problem and now you have to do a hot fix and push a deployment in the middle of the night. Pants optional. And imagine having to sit there and wait 30 minutes for your test to run just so you can push out a hotfix, which I thought to myself, that would drive me crazy.

[00:21:53] **Ben:** Yep. And I'm, and I'm, and I'm wondering if there is a sort of test budget that you can have for your team where you're like, here is the largest amount of time we're willing to let testing block a deployment. And anything above that becomes tests that have to sit in an optional bucket where it's up to the developer to run them as they see fit, but isn't necessarily a test that would block deployment.

[00:22:16] **Ben:** I don't know if that's totally crazy, but the phrase testing budget popped into my head. Is that something you heard or something you came up with? No, no, it just, it just came to me. Oh,

[00:22:27] **Adam:** okay. It's been magic. I like the concept, uh, and I think if it was something anybody was going to pursue, kind of something you said was like, you have to figure out which tests are critical path, which ones are must pass, and which ones are like, uh, you know, these are low risk areas, I guess would be the things I would look for.

[00:22:50] **Adam:** Right. To make optional. I gotta say, I,

[00:22:54] **Tim:** I feel like a complete hypocrite. On this podcast.

[00:22:59] **Adam:** Um. On this episode?

[00:23:01] **Carol:** Yeah, I was like, all the time or just

[00:23:02] **Adam:** right now?

[00:23:03] **Tim:** No, just this episode, yeah. Thank you, thank you. Yeah, I'm pretty confident I think the rest of the time. But today I really feel like a hypocrite. And I say that because I, when it comes to when we have contractors do work for us, I require unit tests.

[00:23:19] **Tim:** I require so much testing just because it's a way for me to validate the truth of what they're saying they've done. Um, and so everything that, that we have that's done by third parties is very well tested and it's fantastic because I have a high level of confidence. And anytime I start a new project, if I have a Greenfield project, I always start with, with writing some level of unit test.

[00:23:43] **Tim:** And then I get so involved in the actual architecture of the system that I put it off. And I'm like, well, I'm just going to avoid, you know, I don't need to really need a test for this. Um, I'm not really sure where I'm going with this. So I'm not going to write a test first. So I'm kind of experimenting.

[00:23:58] **Tim:** Then my experiment becomes reality. And my reality becomes the released version. And then it's like, well, what's the point of writing a test now? So yeah, I feel like a complete hypocrite

[00:24:08] **Adam:** when it comes to this. Yeah. Uh, so something you said there that I wanted to amplify is confidence. You know, it gives you confidence that they've done what, what you, what the spec was.

[00:24:19] **Adam:** Right. That they've, that they've satisfied the spec. And that's what testing is all about, right? Is it's in increasing confidence that you can deploy this code and nothing is going to be wrong with it. Right? And to the point where, you know, when I think about testing what the, the pinnacle of testing for me is.

[00:24:35] **Adam:** A hundred percent confidence that I can deploy on my way out the door at 4. 55 on Friday afternoon with confidence that I am not going to get paged, uh, with a high degree of confidence, not a hundred percent confidence, but with a high degree that I'm not going to get paged on, you know, Saturday at 4 a.

[00:24:51] **Adam:** m. because some of that code that I just deployed, uh, I want to say a whole bunch of different, uh, like, uh, things, but they're all bad words. I'm trying to stop myself. It went wrong. It failed. As the English say,

[00:25:07] **Tim:** it went pear

[00:25:08] **Adam:** shaped. Yeah, there

[00:25:09] **Carol:** you go. See, I think what differs between the team I'm on and the team you guys have is we have, I think it's 15 ish people touching the exact same code daily.

[00:25:23] **Carol:** So, a patch I can put out today may have not even been in the code base they pulled yesterday when they started working on a bug or a week ago when they had theirs. So, me writing that extra little bit of test...

[00:25:53] **Adam:** But

[00:25:56] **Ben:** I, I think if You use it and then rebuild it. You go around it and then Not true. I, I, yeah, I, I, and this is probably because I don't test a lot, so I'm so used to, to manually testing that I, in one of the past episodes, I mentioned Rich Hickey. He's the creator of Clojure and a bunch of other stuff, I believe.

[00:26:17] **Ben:** And in one of his presentations, he, he asked the audience, what's the one thing that every production bug has in common? It passed all the tests and, and I, and I keep thinking about that because even if you have a huge test suite, I can't help but think you still have to do the manual testing because what if something critical was missed or, and I'm not saying you have to test exhaustively, but if you're working in an area of the application.

[00:26:52] **Ben:** I think you still, it's still incumbent upon you to test the parts of the application that you've touched. So I think the exhaustive test suite, what that does is it catches unexpected bugs, unrelated or things that broke because you didn't expect them to break in a certain way. And I think that's very important.

[00:27:13] **Ben:** But I always get hung up on this idea when people say, well, testing increases the velocity of application development. And I think it can only increase the velocity of application development if you're not testing manually. But I feel like you have to test manually,

[00:27:30] **Adam:** period. Well, but like to Carol's point, you know, that, that whole preventing regressions thing, you know, you and I are developing something sort of two different things in parallel, and I commit mine and go on with my day.

[00:27:43] **Adam:** And then you go and you rebase and you commit yours, and you don't know whether or not you've broken the code that I just committed. Sometimes things. Uh, touch or the share functionality and you changed the function signature that I was using that function and you searched for all the, the uses of that function, and mine wasn't in there because you hadn't rebased yet and Right.

[00:28:04] **Ben:** So, so just, just to be, uh, to clear I'm I, yes. It catches regressions and I think that's a huge value. My, my, where I take a little bit of issue is when people say that it increases the velocity of development over time. I have trouble embracing that.

[00:28:22] **Carol:** I will tell you, like, my workflow is to code, test manually, like, I am in the system looking at what I'm doing and making sure that everything I'm doing is accurate.

[00:28:32] **Carol:** Like, I'm still in there, and then when it goes to SQA, usually when it goes over to either code review or to the SQA team for them to start, Also, manually testing it and running their test suite against it. I then usually start writing tests for it. So my test doesn't come after me and we do the manual still.

[00:28:51] **Carol:** So it doesn't, I don't feel like it improves the velocity any. I feel like it slows it down.

[00:28:58] **Tim:** I'd say this bit, Carol, that I don't believe it increases the velocity in the short term of. of a program. So let's say you have a brand new project. It's unfield tested and you're creating all these tests and all the tests pass.

[00:29:16] **Carol:** Unfield tested. Right.

[00:29:18] **Tim:** And then you put it in production and it fails, right? And so they pass the test, but they still failed in production. That's obviously, so all those tests, you would say, didn't really increase velocity. Where I think it does increase velocity, where you have a long term project that's been around, uh, is stable, and that's kind of the project I'm working on, is it's been around for many years, and anytime we add something new to it, the existing tests are, are a point of truth.

[00:29:48] **Tim:** for that project. I know that this has been a stable project for many years. All these tests passed and now I want five new features. We add those five new features, they write the test for those features, those pass, but the old tests fail. Well, now, now that's kind of what to you said, it catches things that people didn't think about.

[00:30:10] **Tim:** Right. And so that would increase that for me, increases the velocity for a project of maturity because it tells me I don't have to remember everything about every nuance of that program. I can just run the tests and they will at least give me a indicator of where failures could occur. And that saves me time.

[00:30:33] **Adam:** Yep.

[00:30:34] **Ben:** Cosine. I agree. I'll buy that. I guess I would only say that I think it's not as exaggerated as I feel like some people make

[00:30:42] **Adam:** it out to be. Oh yeah. Nothing is ever going to be silver bullet level. Yeah. Um, so and then the other thing I think we've kind of beat around this bush a little bit is like the different types of testing, right?

[00:30:56] **Adam:** So there's, there's a lot of things that you can do and a lot of different sort of, um, um, Levels of testing, I guess, is where I would... How I would categorize them. So you've got degrees of it. Yeah. Yeah. Well, you've got manual testing. Manual testing is testing, but there you go. Right. Uh, you know, and it is in my opinion, the slowest and most prone to human error form of testing.

[00:31:20] **Adam:** Um, and I think that is one area where, uh, automated testing. undoubtedly beats manual testing is like no one is going to accidentally check a box and say the thing passed when it didn't pass if it's there or a human might mistake the answer. You know, it might mistake the test results. Whereas a computer is going to, if you, if the test is well written is going to detect success or failure properly and, uh, record that and they're repeatable on a faster time scale, right?

[00:31:54] **Adam:** So you can run the tests and if something fails, you can make a change and repeat that test.

[00:32:04] **Adam:** Um, but then you have things like, uh, sort of static testing. I would personally include in that, um, in that sort of level, um, things like using a type system, a strongly typed language, um, that enforces things. Um, in, in, I'm heavily in the JavaScript world these days, so I'm thinking of like ESLint that enforces some style rules, but some like, uh, other rules that, that help prevent common pitfalls.

[00:32:34] **Adam:** Um, and then you've got things like Prettier, which will format your code, um, and a couple of other things. And those are like, they pretty much run. More or less instantly when you hit the save button in your editor. Um, and they, you know, they give you the red squigglies if you're using ESLint and it's supported.

[00:32:56] **Adam:** And so it's like, oh, hey, there's a problem here. I'll go fix that. Um, and so that's testing that's helping you before you even. Like in line, real time. Um, and then you've got your like unit tests, which I think we're all fairly familiar with. And I think that where I, the hole that I fell down where I did testing wrong for a really long time is I tried, all I was really aware of was unit tests.

[00:33:19] **Adam:** So I just tried to cram everything that I wanted to test and improve confidence in into a unit test and, or I tried to use unit tests to do too much and that became a problem. And that reminds me of Uh, a very popular phrase I've seen going around in the JavaScript community, which is write tests, not too many, mostly integration tests.

[00:33:39] **Adam:** Um, yeah, I've heard that. I'm going to, see, this is it. I mispronounce names. Guillermo Rauch, I believe, is, and he's the CEO or founder of, um, Vercel. Um, and, uh, I think the, the takeaway from that is a couple of things, right? Like, He says, not too many tests. So focus on what's important to test, right? A hundred percent test coverage is not as important as I think a lot of people make it out to be.

[00:34:08] **Adam:** And he says mostly integration tests, meaning, uh, unit tests, the things that are easy to unit test. So Ben, you had mentioned pure functions is basically what that is. The only thing it does is take the input and give you an output. It doesn't read anything from any other context. It doesn't. create any side effects outside of itself.

[00:34:28] **Adam:** It doesn't save anything to shared cache or anything like that. Um, it's input and output and that's it. Um, and those, those things are very testable. Um, and, uh, if, if you can't test it with like pure function unit tests sort of thing, then maybe it should just be covered by integration tests is kind of what I'm thinking.

[00:34:52] **Adam:** Um, or even end to end tests, which is the sort of the last layer. Or I guess, Tim, you were saying that, uh, end to end tests sometimes get called functional tests? Yeah,

[00:35:05] **Tim:** um, I was thinking particularly of, so what we've been doing recently is a lot of our stuff is APIs. And so to test an API, we've been using REST Assured.

[00:35:15] **Tim:** Uh, so it's rest assured. io. Which lets you basically build a functional test to, to call the API to pass. All these different parameters to log everything that was sent and to log everything that comes back from it. Plus to check the information that stream Jeremy sends gets the proper response back. Um, like I said, most stuff that we're doing is APIs.

[00:35:41] **Tim:** Um, testing them, yet. but, That is more important to me to know that if I send something to an endpoint and, I send these parameters, that I get what I expect. Then, does everything underneath that code, everything billet experiment function All those calls, do they all pass the right thing? Um, I, I feel I get more, when I'm doing it, that's what I'm doing, because I get more bang for the buck out of that, than worrying about, does function whatever send me a, a numeric instead of a string.

[00:36:10] **Tim:** You know, sometimes

[00:36:11] **Adam:** I don't care. Exactly, yeah, the, the user doesn't care if your function, what type it returns. They care, when I press the button, does it do the thing that I... When I ask for

[00:36:19] **Tim:** this, does it, does it give me proper JSON and is it the right thing? And that's, that's really mostly what I care about.

[00:36:24] **Tim:** And then, and then sometimes we do a load testing with Gatling. io, uh, to just basically build a whole bunch of requests and then scale it until the thing dies and see where that, that point is and what breaks.

[00:36:39] **Ben:** I feel like between Rest Assured and Gatling, this is just beautiful wordplay

[00:36:43] **Tim:** on software. Rest assured.

[00:36:48] **Tim:** Take a load of

[00:36:48] **Adam:** my

[00:36:51] **Ben:** Gatling! It's funny, as someone who does very little testing, I still have very strong feelings about a lot of it. Probably ill conceived feelings. But speaking about this idea of testing the API and not necessarily worrying about What methods are getting called under the hood? That's one thing that I've never connected with.

[00:37:10] **Ben:** When I hear people talk about testing, it's this idea of being able to, I think they call them spies. You create these spies where you can see if private methods get called in certain ways. And I always think to myself, why do you care about your private methods? Like that's an implementation detail. That what

[00:37:28] **Ben:** you're. Public methods are returning and that should inherently test your private methods and people have tried to explain it to me Why you actually sometimes want to know but I've I've just never understood.

[00:37:39] **Tim:** Yeah, I think there's a you have a level of pragmatism I think you've earned over the years

[00:37:48] **Ben:** Your heart matters.

[00:37:49] **Ben:** Your heart matters

[00:37:51] **Carol:** These spies need to stop being

[00:37:53] **Adam:** monsters. That's right.

[00:37:55] **Ben:** One thing that I I I think is worth mentioning Is that, um, I have personally gotten a lot of value out of making small changes and deploying very often. Yes. And I think about what Carol was saying about she's working in parallel with her team and they're all working on the same stuff.

[00:38:14] **Ben:** And then you're merging things in and code that didn't exist two days ago now exists in the code that you merged into. And it's, and that can be a fraught with peril. And I find if I can touch the smallest amount of code possible. And then deploy that to production, it, it significantly reduces the amount of damage I can even do.

[00:38:35] **Ben:** And it, and it, again, because I'm a very manual tester, it significantly reduces the amount of code that I have to test, the, the amount of interface within the application that I have to test. So, uh, small changes deployed often is two thumbs up from me.

[00:38:52] **Adam:** I want, I also want to throw out, um, we have had some interesting success using testing tools to enforce, um, I don't even know how to describe it.

[00:39:05] **Adam:** So we're using, we're using some testing tools to validate configurations, uh, as part of deploys. So for example, we're using a tool that is, uh, like a dead man switch for, uh, scheduled tasks, right? You have cron jobs they run. And you want to make sure that they haven't died. We use a service where we pay for a certain number of, like, records that, that can be checked into, and if they go too long without being, uh, checked into, then we get an alert that we can push off to our pager duty or whatever.

[00:39:36] **Adam:** Um, and each of those has a unique ID. And so we have a whole bunch of those unique IDs in config to say, okay, when this job runs, use this ID to check in. And one of the rules that we have enforced on that config is that those IDs can't be reused anywhere else. It has to be for this job and it can only be used with one job for one customer.

[00:39:59] **Adam:** Um, and so it, one, like for example, when we spin up a new customer, we'll copy somebody, an existing configuration file and start updating it for the new customer. And so that helps. Prevent those accidental copy and paste shares of those IDs. So by, you know, you check in a new configuration file and the tests run and it says, well, you have reused this value and you have, you know, this setting is turned on, but it necessitates that you have these other settings filled out, or you've turned on OAuth, but you haven't provided the OAuth server ID or anything like that sort of thing.

[00:40:34] **Adam:** Um, so it helps us from. Misconfiguring things accidentally. So when

[00:40:39] **Carol:** you said that, at first I was like, I have no idea what you're talking about. Like, completely lost right now. But, it almost sounds like it would work too, like if you were moving things between environments, and say you had like a settings file, and you accidentally moved like dev settings up.

[00:40:55] **Carol:** Like, would that be caught as well in that situation?

[00:40:58] **Adam:** Um, the way that we do our config, I don't think that that's something that we could test for. We, like, we have uh, Our servers are aware of what environment they are, and all of our config is shared in one central location. And you say, okay, I want the config for this customer in this environment, um, and maybe a specific setting.

[00:41:16] **Adam:** And it pulls that out of the repository and gives it to you. Interesting.

[00:41:24] **Carol:** Now I'm curious more.

[00:41:27] **Adam:** I'd be happy to show you sometime. It's not something I can make public, but we'll... Yeah,

[00:41:30] **Carol:** I definitely want to see, because now I really am like... We'll need to know more.

[00:41:36] **Adam:** Maybe it's something we can talk about on the after show. Yeah.

[00:41:41] **Ben:** If I could, uh, plug the idea of feature flags for a second.

[00:41:46] **Ben:** So earlier I talked about small changes deployed often. Yeah. Another thing that helps tangentially to testing is feature flags. And the idea behind a feature flag is that you can deploy code, but not necessarily have it turned on for users. So essentially you, you decouple the idea of deployment. And activation of a feature.

[00:42:13] **Ben:** And, uh, the best thing about that is that one, you can deploy changes incrementally to a feature that's not yet feature complete as long as it's behind a feature flag, which again, small changes, less damage. Uh, but then once it comes time to turning a feature on, if you start to see errors coming through in your monitoring or you get paged about something, you can turn the feature flag off.

[00:42:36] **Ben:** And direct users back to the previous version of the feature, uh, which allows you to, and this sounds terrible, but to do all of your testing in production and to crowdsource your testing to all of your users, which sounds, sounds really, really bad, but it's sometimes just the way you have to flush out really hard to find bugs.

[00:43:01] **Tim:** It's like A B testing, but with bugs.

[00:43:04] **Ben:** Exactly.

[00:43:07] **Carol:** And it sounds like, it sounds complex to someone who doesn't know, but it's pretty much just. If it's on, then it's there. Or if it's off, then it's not there. You never have to go in and rip out anything. You just check a value.

[00:43:23] **Adam:** So I'm

[00:43:23] **Tim:** wondering now if that's sort of what I've done.

[00:43:26] **Tim:** I don't know if that's what it's called. But so in the APIs that I write, I always version things. So I'll have a v1, v2. And so if I'm doing a new feature... That could possibly be a breaking feature. I create a new version. You just increment, right? Yeah. And then, yeah, I increment. And then I will, in production, just sometimes put Someone on the, you know, two, two dash three, and then just wait to see what happens.

[00:43:55] **Tim:** And then I'm like, Oh, that, that, that didn't work. So I'll turn it back to two dash two.

[00:44:00] **Adam:** And I don't know what happened. Man,

[00:44:02] **Carol:** network latency or something. It should be back up now.

[00:44:05] **Tim:** Yeah. There's a glitch, a glitch in the matrix. It's gone.

[00:44:10] **Ben:** Well, there's a, there's a pattern. It's called the Strangler pattern, which I think is basically what the, is the concept that Feature Flags helps facilitate, which is where you have, um, two parallel implementations and then you slowly move traffic from one implementation over to the other implementation.

[00:44:29] **Ben:** So the new implementation essentially strangles the old one, um, and, and then eventually you have everyone over to the new implementation. And if you let it soak for long enough, then you can kill the old one.

[00:44:43] **Adam:** Yeah. Yeah. I mean, Ben, you have that blog post about LaunchDarkly. Oh, I love LaunchDarkly. Yeah.

[00:44:50] **Adam:** And I, I've, I've read it like several times, more than three and, uh, Oh, that's right. That was in response to something you asked. Yeah. I forgot about that. And, and I, I can't help it. This is the way my brain works. I read that and I go, this sounds so awesome. And I instantly, without even like, I can read it and at the same time, Tell myself, commit to myself, I am not going to make an effort to implement this on my own.

[00:45:14] **Adam:** And the third thread in the back of my mind is like, yeah, but you could just do this and do that. And, and that's how you could implement that piece. And, um, the, the part where I think I get hung up on it is like the. Uh, splitting for users and being able to control that. That seems, from the outside looking in, having literally zero experience as a user of those tools.

[00:45:40] **Adam:** Um, that seems to be the killer feature, is the ability to, like, on the fly, per user, or per percentage of users, etc, etc. Uh, turn it on and off. So take a

[00:45:51] **Carol:** step back, what is this post? Can you give a little bit of information about the

[00:45:55] **Ben:** post? I think Adam on Twitter or something said, Hey, I've seen you talk about Feature Flag.

[00:46:02] **Ben:** What that?

[00:46:06] **Ben:** So I think I went away and wrote like a tome on everything I love about feature flags I was like here Adam check this out. It's probably it's probably like a like a two hour read so

[00:46:16] **Adam:** So what you're saying is is like every other Tuesday?

[00:46:20] **Ben:** It was, it was like, it was just the perfect opportunity for me to talk about Feature Flags because Feature Flags, and, and we're getting off the testing topic, but Feature Flags are so amazing that I don't care.

[00:46:32] **Adam:** Well, like you said, it's kind of testing in production, and I think that's relevant.

[00:46:35] **Ben:** Feature Flags have, without hyperbole, revolutionized the way that I do development. Because it just completely changes the way you think about architecting your code. Testing your code, deploying your code, the whole application life cycle changes, the ability to deploy with safety, to deploy incrementally, not even just like features, but you can have percentage based rollouts and you can have targeted based rollouts.

[00:47:03] **Ben:** So I'm only going to turn this feature on for this particular subset of users, like Adam was just referring to, where you could say, I'm going to do it for this particular subdomain. You can do it for, here's everyone who ends in, uh, at harvard. edu email address. And so you can really get very interesting with how you roll out your code and how you, uh, apply changes to applications.

[00:47:29] **Ben:** I, I can't say enough good things about FeatureFlags. I, I, I'm at a loss for words.

[00:47:35] **Adam:** Yeah, we will definitely, we'll, we'll link the blog post in the show notes. And if you have a week to kill, you can go read it. A week. Sounds, sounds like an episode topic. I like it.

[00:47:46] **Carol:** Yeah, I agree.

[00:47:49] **Adam:** So are we done with testing? Oh gosh, I feel like, uh.

[00:47:53] **Adam:** I feel like we could, I personally, I could, and I think I proved this last week, but I feel like I could keep talking on this topic forever.

[00:48:01] **Tim:** Like I said, I feel like a total hypocrite. I make other people test, but I am not good at it myself.

[00:48:07] **Adam:** I

[00:48:07] **Carol:** like writing tests. I mean, I've said this before, it actually brings me joy.

[00:48:12] **Carol:** I get to think through things I didn't think about when I was coding it. Um, I get to kind of think about the path that got me there and the path that I didn't consider when I wrote the functionality. And then I know someone coming behind me has a little bit of insight on what was expected if they see a failure and they can maybe go, Oh, well, this is why it's breaking and now I'm understanding more.

[00:48:37] **Adam:** I guess if we're to the point where we're doing like final thoughts before we wrap it up, mine would be the more that I learn how to test well and the more that I write good tests, the more I become a believer in automated testing. Amen. Yeah. You know, I, I don't claim to be anywhere near the top of that mountain, but, uh, like I said, the, the more I do it, the better I get and the better I get, the more I appreciate what I can get from it.

[00:49:07] **Adam:** And like I was talking about earlier. The confidence to push, to deploy at, you know, 4. 50 on Friday afternoon and go into a stress free weekend is, is valuable to me. Like, I don't want to have to worry about a last minute deploy and putting something off because we don't have confidence that we can deploy without issues.

[00:49:28] **Tim:** I would say as a principal in a business, I think that short term, I think testing is kind of a sunk cost maybe, but longterm, I've seen the benefit of it. Uh, particularly whenever you're adding stuff to a mature system that those tests pay dividends later, they don't pay dividends now, but they do. Pay dividends.

[00:49:49] **Tim:** Well, they don't pay as many dividends now. Let me rephrase that before people jump on me. Um, but they do pay dividends in the long

[00:49:56] **Adam:** run.

[00:49:57] **Carol:** You're about to get your official haters. Kevin McCabe,

[00:50:01] **Tim:** come on, be my hater.

[00:50:04] **Ben:** One thing that I've never connected with emotionally when I hear people talk about testing is when they refer to tests as providing documentation about how a feature is supposed to work.

[00:50:16] **Ben:** And as someone who's tried to look at. I have found that tests to understand why something's not working, I have found that they provide no insight into how the feature is supposed to work. Or I guess I should say specifically, they don't provide answers to the question that I have. So for example, if I, if I look at Documentation, documentation.

[00:50:37] **Ben:** And the documentation is ambiguous about something, like maybe I don't understand what a method is supposed to return or the range of inputs it can take. I think to myself, I'll go look at the, at this library's tests to see what it can take. And it's like hundreds of tests in all kinds of various incarnations of.

[00:50:56] **Ben:** And I'm like, well, that didn't help me at all. That was

[00:50:58] **Adam:** way confusing. I'm parse through your tests to figure out that I can take an integer and a float.

[00:51:06] **Ben:** Right, right. It's like, yeah, you can see that it takes an integer, but not necessarily the range or going to take a negative integer.

[00:51:11] **Adam:** Right. To

[00:51:13] **Ben:** say that testing provides documentation, I think, assumes that those tests are extremely robust and written in a very, you know, consumable way, and I think that's, I think you're overselling your, your, uh, your testing at that point.

[00:51:31] **Ben:** Or maybe it's just me. Maybe I don't know. I just never, I never find them as a substitute for documentation.

[00:51:37] **Carol:** They are definitely not a substitute, but I do have a response to that. So if you go look at some of the test output whenever hours are running, it's true scenarios. So it says like the scenario, and that's what it's called, the scenario is...

[00:51:51] **Carol:** This user came in with, say, three drivers, then you basically put the then statement, the winds are the wind and the then statements, and it reads out like English. So it says, you know, this is what triggered it. This is what. And this is what occurred from that event. So if it fails, you have the ability to see where it was at.

[00:52:13] **Carol:** So it's not documentation, but it's more like your cases, like the case that got you there to see how it was working and see how it was functioning.

[00:52:23] **Adam:** Sounds like when the test fails, then you have sort of an immediate context for. What went wrong? Right.

[00:52:31] **Carol:** I can go open the system and do exactly that thing. I can be that user.

[00:52:36] **Carol:** I can have that set up for me and go, okay, here's how we got to this failure without having to go build all these test scenarios in the interface.

[00:52:46] **Adam:** Which is

[00:52:46] **Tim:** useful if you're trying to fix the error, but it may not be useful if you're actually looking for some sort of architectural

[00:52:52] **Adam:** reason. No.

[00:52:53] **Carol:** Oh no, it's definitely not so good for that.

[00:52:55] **Carol:** Which

[00:52:56] **Adam:** I

[00:52:56] **Tim:** think probably is what Ben might be

[00:52:58] **Ben:** looking for. Yeah. And maybe, I mean, things that I think about, or I guess case in point, sometimes, uh, If the Angular documentation is a bit fuzzy, I might try to dip into the GitHub repository for Angular and look at their tests. And they're, they're so outlandishly complicated.

[00:53:20] **Adam:** I scratched

[00:53:21] **Carol:** my head. I'm like,

[00:53:22] **Adam:** huh? Okay. Well, have we said everything we wanted to say about testing? We could probably say more, but... Yeah, we did a terrible job at sticking to a half hour.

[00:53:31] **Carol:** We'll just cut everything Ben said out. No... Cats are pretty! Yeah...

[00:53:41] **Adam:** If we cut all of Ben's, uh, naysaying out of the show, we don't have any, we don't have any show left.

[00:53:48] **Tim:** So, so despite Ben and somewhat I pooh poohing on testing, if people want to learn more about testing, where should they go?

[00:53:56] **Adam:** Well, as I've said before, you know, my head is very much in the JavaScript world, so I have some answers, but my answers are, uh, And I'm sure that most of the concepts that you would learn from the resources I'm going to give would be very transferable.

[00:54:14] **Adam:** They're going to be taught in the context of JavaScript. But the two that immediately spring to mind for me are, uh, testingjavascript. com. It's a paid course by Kent C. Dodds and it's fantastic. Um, it, he covers everything in great detail, but at the same time it isn't tedious and long and drawn out. It's, it's very much like no intro, no outro, just like, here's what you do.

[00:54:39] **Adam:** This is testing. Um, and, and it covers everything that we talked about, the, the static testing, the unit testing, integration, and end to end. Um, And it helps you with getting the tooling set up to do that. The other resource that I would recommend is egghead. io. If you just go on there and you search for testing, um, there's a ton of different test, uh, training courses there that are specific to different technologies.

[00:55:01] **Adam:** So using Jest for testing or testing Angular applications or that sort of thing. Those would be the places that I would start if I was looking for. Some sort of training materials.

[00:55:13] **Carol:** Yeah. And I would do a search for whatever you're writing. Look at how to mock data. Just look at, you know, different tools for that.

[00:55:20] **Carol:** We use Mockbox, you know, just because it's what we have available to us. But any type of mocking ability is really good because it just gives you the ability to set data without having to interact with anything.

[00:55:32] **Adam:** What about our Patreon folks? If everybody wants to. Oh, you said it first, you have to do it.

[00:55:38] **Tim:** So hey guys, apparently we have a Patreon and apparently people are donating to it. You know, a Patreon amazes me. I always think that people are just going to take stuff for free and not, uh... Not contribute, but people are amazingly generous and you guys, we, we love you so much. Appreciate you helping out, uh, patreon.

[00:55:57] **Tim:** com, working code pod. So we have some who've already donated to one of our, uh, top patrons is, uh, Monte Chan. Thank you, Monte. Hearts, hearts. And, uh, he gets, he gets to hang out on our Discord. We have a private Discord that he can hang out and, and, uh, talk to us. And, uh, he also gets early access to new episodes and the after show where we get really crazy.

[00:56:22] **Tim:** So... Fans

[00:56:23] **Adam:** only.

[00:56:24] **Tim:** Fans only. Well, I don't know about that, but, uh, Yeah, so if you, if, if you're feeling generous and you like the show, drop us a few bucks. And, uh, we, we mentioned you on,

[00:56:34] **Adam:** on the

[00:56:34] **Carol:** podcast. Yeah, I mean, the lower levels, what, 4? Four

[00:56:38] **Adam:** dollars a month. Yeah.

[00:56:39] **Tim:** Yeah. You can't even buy a cappuccino for that at Starbucks.

[00:56:43] **Tim:** Yeah, that's

[00:56:43] **Carol:** like seven bucks now. What happened? Stupid

[00:56:51] **Carol:** COVID. I got cheap during

[00:56:52] **Adam:** this. All right. I did look on iTunes and we do not have any reviews to read. There's, there's a bunch of ratings. Uh, yeah. Oh, that's nice. Five ratings and they're all five stars. So thank you. Every

[00:57:04] **Carol:** time I listen, I click five again, hoping it'll submit.

[00:57:09] **Adam:** So to the one person that's rated besides the four of us, thank you, mom.

[00:57:13] **Adam:** Well, actually, I haven't rated, so it wasn't me. Oh, well, then you're fired. Dang it.

[00:57:21] **Carol:** Don't worry, we'll hire you back tomorrow.

[00:57:23] **Adam:** Thanks. All right, so I guess everybody, thank you for listening. And, uh, don't forget to share it with a friend. Those word of mouth referrals are awesome. As I've said, rate us on Apple Podcasts or wherever you get your podcasts if they support it, and send us your topic suggestions.

[00:57:39] **Adam:** We are on Twitter and on Instagram @WorkingCodePod, and we'll catch you next week. Your heart matters.
