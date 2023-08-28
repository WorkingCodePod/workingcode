---
title: "018: Feature Flags (Finally!)"
description: Feature flags allow software engineers to separate the "deployment" of code from the "releasing" of code. Which means safer deployments; instantaneous roll-backs; smaller Pull Requests (PRs); incremental feature development; load-testing with real-world traffic; and - generally speaking - a big bowl of awesome sauce that you didn't even know you needed!
date: 2021-04-14
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/018-feature-flags-finally/id1544142288?i=1000517096012"></iframe>

For Ben and his team, few things have _fundamentally changed_ the product development life-cycle as much as [LaunchDarkly][launchdarkly], a feature flag management platform. Feature flags allow software engineers to separate the "deployment" of code from the "releasing" of code. Which means safer deployments; instantaneous roll-backs; smaller Pull Requests (PRs); incremental feature development; load-testing with real-world traffic; and - _generally speaking_ - a big bowl of awesome sauce that you didn't even know you needed! And, once you have it, you realize that you can't live without it.

_Mic drop!_

But, while Feature Flags may seem magical, _they aren't magic_. And, moving feature flags through a product development life-cycle requires a certain degree of discipline. Because if you leave feature flags in your code for too long, your application logic can quickly devolve into an unclear, unpredictable maze of control-flow spaghetti.

In other news, the Working Code crew is also about to embark on their fist book club adventure, starting with [Clean Code by Robert Martin][clean-code] (aka, "Uncle Bob"). We intend to review this book in the May 12th episode. Feel free to follow along!

And just when you thought things couldn't get any better, the Working Code Podcast now has a _party line_! Just kidding; but, we do have an **answering service at (512) 253-2633 (That's 512-253-CODE!)**. Please leave us a message with with your comments, questions, and anything else you feel like sharing. We miss hearing your voices!

### Triumphs &amp; Failures

-  **Adam's Triumph** - Historically, when his team needed to host a private npm module, they've stored it in a private GitHub repository and then used git URLs within the `package.json` file. And, this worked _most of the time_. But, it was wonky and there were lots of quirks and edge-cases and they've been on the lookout for a better solution. Enter stage left: [GitHub Packages][github-packages]. These allow you to "officially" store npm modules right alongside the rest of your GitHub hosted code - no hacks, no troubles.

-  **Ben's Failure** - He's generally very regimented about the hours that he keeps. But, in the wake of losing both his Project Manger (PM) and his Engineering Manager (EM), he's been struggling to properly prioritize all the work on his plate. And, instead of being smarter, he's opted to work _harder_ by putting in a few extra hours here-and-there. He understands that it's a _slippery slope_; and, not the life-style that he wants to live; but, if he can _just get ahead of it_, he's confident that he'll get back on the right track.

-  **Carol's Triumph** - She's been wanting to build something with React as means to level-up on her front-end skills. And she finally finished going through a [Udemy][udemy] course on React! Next step: React side project (possibly to track her water intake).

-  **Tim's Triumph** - He's launching a skunk works project that is based on a previous skunk works project. It feels a little bit rogue; and a little bit cowboy; but, it also feels kind of amazing and is something that Tim recommends to everyone (assuming that they have some free time to commit).

> **ASIDE**: A "skunk works project" is a secret project that the rest of (or most of) your company doesn't know about until there's a big reveal. These types of projects may _or may not_ be authorized by the company itself.

### Notes &amp; Links

-  [LaunchDarkly][launchdarkly] - an amazing platform for feature flag based application development.
-  [Flagsmith](https://www.flagsmith.com/) - a feature flag service that has hosted, cloud, and on-premise solutions.
-  [Split IO](https://www.split.io/) - a feature flag service with a free tier option.
-  [Ben Nadel: My Personal Best Practices For Using LaunchDarkly Feature Flags](https://www.bennadel.com/blog/3766-my-personal-best-practices-for-using-launchdarkly-feature-flags.htm) - on opus on how Ben's team uses LaunchDarkly and feature flags.
-  [Ben Nadel: Viewing The LaunchDarkly Feature Flag Evaluation Process As A Pure Function](https://www.bennadel.com/blog/3612-viewing-the-launchdarkly-feature-flag-evaluation-process-as-a-pure-function.htm) - a helpful analogy for understanding how user targeting works in LaunchDarkly.
-  [Adil Aijaz: Managing Feature Flags](https://www.oreilly.com/library/view/managing-feature-flags/9781492028598/) - an O'Reilly book on feature flag management.
-  [StatsD](https://github.com/statsd/statsd) - the de facto standard for recording application metrics in web development.
-  [FusionReactor](https://www.fusion-reactor.com/) - an application performance monitoring (APM) solution for the JVM.
-  [Loggly](https://www.loggly.com/) - a log aggregation service that requires no proprietary agents.
-  [Datadog](https://www.datadoghq.com/) - a modern (and totally awesome) platform for monitoring, logging, and StatsD metrics.

Follow the show! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[clean-code]: https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship-ebook/dp/B001GSTOAM
[github-packages]: https://github.com/features/packages
[launchdarkly]: https://launchdarkly.com/
[udemy]: https://www.udemy.com/
[working-code]: https://workingcode.dev/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/018-feature-flags-finally.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:14] **Adam:** Okay, here we go, this is show number 18 for April the 14th, and on today's show we're going to be talking about feature flags, finally! We're gonna get there. And, uh, on today's show... Nope, I already said that.

[00:00:26] **Adam:** But first, we're going to do our triumphs and fails as usual. Uh, Carol's back this week. Welcome back, Carol. Yay! Woohoo! How you feeling? Much better. Yay. Yay. But we're not gonna start with you. Darn, why

[00:00:37] **Carol:** not?

[00:00:39] **Adam:** Okay, fine, fine. You're out of order. You lost your turn, right? You weren't here. It's a loser turn. You go to the back of the line.

[00:00:43] **Adam:** Oh. Uh. Tim, I'm going to start with you. What do you got this week?

[00:00:48] **Tim:** So my triumph this week is just, I'm reveling in the joy of a skunk work project and by skunk work, I mean kind of a project that built on the sly, you know, it was kind of like your after hours project at any time you had a little downtime, you worked on it.

[00:01:05] **Tim:** Um, knowing that it was something that your company needed, but never really fully gave you permission to work on. And then eventually it becomes a mission critical part of your architecture. So I've done that for probably every year of my life. And right now I'm launching. Launching a Skunkwork project, actually two Skunkwork projects.

[00:01:25] **Tim:** So let's say Skunkwork project based off of prior Skunkwork project. So one was sort of a unified API layer that I wrote because we didn't have one for disparate systems, multi tenant systems. And now I'm building another project on top of that, which was, uh, integrated voice phone system that, uh. That I knew we needed.

[00:01:50] **Tim:** So yeah, I'm just, you know, if, if you have the luxury to do it, it feels really good whenever you, something that you said, you know, we really should work on this and it got no traction. And you're like, you know what, I'm going to spend any extra cycles I have to work on this. And then eventually it's like, you know what, we really need this.

[00:02:09] **Tim:** And you're like, guess what? I already built it. That feels, that feels really good. It's a little maverick, it's a little cowboy. I don't, you know, it's probably not good for every organization, but if you can get away with it, it makes you feel really cool.

[00:02:24] **Ben:** How long has the, uh, Skunk Works project been in stealth mode?

[00:02:28] **Ben:** When stealth mode,

[00:02:30] **Tim:** so stealth mode prop. So I probably last year around June, I started this and then around, I, I showed them the MVP of it around November. And they're like, this is great. We need this. I'm like, cool. And so the rest of it has just been working with customers to get it launched. So, which it's launching, it's launching tomorrow.

[00:02:54] **Adam:** So sweet. Thanks. Congratulations. That's awesome. And then can you tell us what it is? Is this the thing

[00:02:59] **Carol:** you haven't been able to tell us? No, no, this

[00:03:00] **Tim:** is not the million dollar idea. This is not familiar. That's my next skunk work projects. When I'm done with this one. No, this is, this is a pretty simple kind of integrated voice response system, phone.

[00:03:11] **Tim:** payment thing. It's, it's nothing sexy, but it's something that, that we needed. But yeah, my, my million dollar idea. I'll let you guys know.

[00:03:18] **Adam:** Cool. It's coming. It's coming. Carol, what you got? Yeah, so

[00:03:23] **Carol:** I'm going to go with the Triumph this week. For my New Year's resolution, one of the things I wanted to do was start learning React, and I wanted to write a little app just to track, like, my water intake.

[00:03:33] **Carol:** Just something, you know, to play with. And I finally finished my Udemy course on React. And it shouldn't have taken me so long, but I've kind of procrastinated, and I started other courses with it, and then I finally, like, wrapped that up this week, so it's done. So I learned a lot. Um, Udemy's awesome. If you have a subscription at work, I recommend you use it.

[00:03:53] **Carol:** Use it outside of work, too. I mean, of course, they're Not sponsored. Not sponsored, no. But, I mean, we get it free through work. So I get an hour and a half every week on the clock to actually learn something in Udemy or something, whatever I want to learn. Um, but I use it outside of work, too, to take extra stuff because an hour and a half isn't enough, usually.

[00:04:12] **Carol:** But yeah, woohoo, I learned some React.

[00:04:15] **Adam:** I finished my first course. Uh, this is always like a pet peeve of mine. I wish the internet came with a pronunciation guide. I always thought it was you to me. It might be. Cause, so like, the way I, the reason that I think that is because it's like you. To me. 'cause like anybody can train, can like make a course on Udemy and anybody can take a course on Udemy.

[00:04:33] **Adam:** So

[00:04:34] **Carol:** that's funny. It might be that I've clearly been saying it

[00:04:37] **Adam:** wrong. I've thought about it like Academy. I've said it the same way you do

[00:04:39] **Carol:** Carol Udemy and maybe it's a, you know, a Southern thing. It's a southern thing,

[00:04:43] **Adam:** I'm sure. Is it GIF or gifs? Gifts. Don't get me. Sorry. It's gifts. It's gif. Uh, the, the other one, it took me like 10 years to realize that I C Q was, I seek.

[00:04:54] **Adam:** You, I didn't know that was forever ago before your time, like,

[00:05:01] I

[00:05:01] **Carol:** don't even know what that is in reference

[00:05:02] **Adam:** to you. It's it was a well messenger basically before there was a, yeah, yeah,

[00:05:08] **Carol:** yeah, cool. Yeah, that's me. Yeah. When's about you,

[00:05:12] **Ben:** Ben? I just want to say when I was in school, I was down the hall from a guy who had a custom.

[00:05:17] **Ben:** Uh, typing sound for his ICQ, where it was like a typewriter. And he would blast this typewriter noise through his computer speakers. I was just like, how do you think that's appropriate in a close living space? That's not how humans

[00:05:31] **Carol:** interact. I'm going to have to go look this thing up.

[00:05:35] **Adam:** It's not that impressive or anything.

[00:05:38] **Adam:** It's just a chat program. It's all it was. It's like, yeah, MSN Messenger or AOL InstaMessenger sort of thing.

[00:05:43] **Carol:** Oh, so it was its own system. It's not a... Right. A acronym that you put in a message, like, okay, that's where I was confused. I was like, you told someone ICQ and that was it. Now you're married. All right.

[00:05:56] **Carol:** What about you, Ben? What you got this

[00:05:58] **Ben:** week? This week I'm going to go with a failure. Um, I'm usually fairly regimented about how I work. Uh, I start at the same time every day and I try to end at the same time every day. But, uh, for the last week or two, maybe three, I've been putting in some extra hours. Um, my team lost their engineering manager and their project manager, like in the span of a month.

[00:06:22] **Ben:** And, uh, my team does a lot of interrupt driven work. So we have projects, but then support will come to us or someone from the customer facing team will come to us and they're like, Hey, you know, we need this done or customers complaining about this and suddenly you have to decide whether or not the things you're working on are the important things or the thing that was just brought up by the support team, the important thing.

[00:06:41] **Ben:** And, um, I'm typically good about. Time management, but I just have not been able to wrap my head around all of the things that are on my plate the last couple of weeks. And instead of maybe taking time to prioritize them better, I've just been trying to put in a few extra hours here and there, which it hasn't been excessive, but it's just, it's not, I feel like it's a slippery slope and it's not the lifestyle that I want.

[00:07:08] **Ben:** So I want to, I want to make sure that that doesn't get out of control. And I. Don't think it will because I'm sort of using it as an excuse or I'm, I'm excusing the behavior by I have like one or two medium sized projects that I just want to get done. And then once those are done, I feel like I'll be back in control, which I assume is what every addict ever tells themselves.

[00:07:31] **Ben:** But, um, it's just. It feels like a failure on my part to properly manage my own work and my own

[00:07:39] **Adam:** time. I quit whenever I want, man.

[00:07:43] **Ben:** I could work normal hours whenever.

[00:07:47] **Carol:** That's been at nine o'clock at night.

[00:07:51] **Ben:** So, but um, you know, I'm in good spirits and I feel like I'm doing good work and I just want to make sure that I'm doing that good work in the allocated

[00:07:59] **Adam:** work hour.

[00:08:00] **Adam:** Yeah, I mean, it sounds like the things that you're working on are things that you have a personal. Interest in seeing completed. Yes. And you know, whether that's because you want to meet the deadline or because you are excited about the technology or whatever, like if, if there's that personal interest, I think it's not entirely unhealthy to dedicate some extra time occasionally.

[00:08:23] **Adam:** Yeah. Yeah.

[00:08:25] **Ben:** Yes. A hundred percent. And I think drawing that, that distinction there is, is important because. If I didn't do the little extra time and I didn't finish those tasks, literally no one at the company would complain. It's the, the, I have to get stuff done or I get in trouble work is always during work hours.

[00:08:46] **Ben:** And then what I've been doing in a little extra time is the special side projects that I, uh, I call them side hustles, but it's still, you know, it's all work. But, uh, it's sort of self guided work that, uh, that I'd like to get done. Nice. Yeah, I found that, you know, working

[00:09:03] **Tim:** from home during this pandemic, which is the longest I've ever worked from home, I found myself just sitting by the computer more.

[00:09:11] **Tim:** Sometimes I'm not even, don't even necessarily have something I'm working on, I just, I'm just checking my email to see if there is, like, you know, it's like six, you know, five, six hours after closing time and I'm still like, what's happening? Which I never did when I was, like, working at the office,

[00:09:29] **Adam:** so. Well, I've been, I've been working from home for going on 10 years now, and I've developed a really healthy ability to totally separate from work at the end of the day.

[00:09:39] **Adam:** You know, like, there'll be notifications from our team chat and emails, and I'm just not, uh, aware of them at all. Which has been wonderful, and it's been wonderful for me, but not for my teammates who are like, emailing me, you know, when it's 4. 30 on the West Coast and they're busy, but.

[00:09:57] **Carol:** Yeah, I physically switch laptops off the dock.

[00:10:00] **Carol:** So, I'll take my work laptop and detach it and put it in my personal laptop. That way I don't have the urge to keep reading Slack messages, or I don't have the urge to open the, The email, like all that's gone. So everything from that day is closed. And now it's back to what I was doing after hours for my own stuff.

[00:10:16] **Carol:** Yeah, that, that's what

[00:10:17] **Adam:** works for me. That's interesting.

[00:10:19] **Ben:** I just have one laptop. Yeah. I'll tell you, and I, and I don't know if this is a mentality thing or a privilege thing or a combination of the two. But I'm always surprised how many people need a computer to be sent to them when they start a new job.

[00:10:37] **Ben:** Like, they don't have a computer ready to go from their previous computing requirements. Right. Um, which, you know, could just be that they have to have a special computer for work that they can't have personal stuff on. I totally understand that.

[00:10:49] **Carol:** No, my thing is that it's not that I have to have a work laptop from the office, but they're very strict.

[00:10:56] **Carol:** Well, I don't know about here because we haven't had the conversations, but most companies are pretty strict on anything. You've develop on said hardware becomes proprietary. Oh, that's so when I'm creating my own things, I'm writing my own code. I want there to be a very clear separation of what. Of who owns what I'm writing,

[00:11:14] **Adam:** so yeah, that's a good point.

[00:11:16] **Adam:** And the other thing that I was thinking about was. Um, like if you are coming from another job and you, you were, you were using their computer and you have to give it back when you quit the job, like now you need a new work computer. Well, I guess that takes it to me. Uh, this week I have a triumph, which is that I finally took the time to learn GitHub packages.

[00:11:36] **Adam:** So my team, we're very heavily JavaScript and we've been using NPM for years and years now. Um, and I've kind of always wanted to have a, like a private NPM, um, namespace, like NPM Enterprises, I think what they originally called it, just like private packages on NPM so that we could have closed source stuff, but the ease of use of NPM, and to do that until like this week, we were I've been using, uh, Git URLs in our package JSON, so you can do, like, Git plus HTTP, blah, blah, blah.

[00:12:10] **Adam:** There's, like, documentation on npmjs. org about it. And it works, but it's got some quirks, and it's just not the same developer experience as using public modules on NPM. And so this week, part out of frustration with, you know, we have, I think, 24, something like that, microservices. And having to keep them all up to date and the quirks of having to figure that out for each of them and all that, I just decided it was time to find another solution.

[00:12:40] **Adam:** We do have a GitHub team plan, I guess is what you would call it, and that includes things like a certain amount of the GitHub Actions, their CI service. And also, GitHub Packages, a certain amount of that for free. Um, and then it seems to be really affordable after you reach your free limit. So, we're giving that a go, and we're gonna see how that goes, and so far I'm super happy with it.

[00:13:04] **Adam:** For all I can tell, it works just like public npm, except you have to have a npmrc file in. Like, as a sibling to every package JSON, to say this is where your namespaced packages or your scoped packages, where the repository is for them. And other than that, it's gravy. It's been going great. Loving it. So it's just for deployment?

[00:13:24] **Adam:** Um, for deployment and for dev stuff. I mean, it's just like we have a bunch of different modules that we, like we have a config module that contains a bunch of different config stuff, like customer config and sort of global config that we can import into different projects so that it's all shared. We only have the config in one place.

[00:13:40] **Adam:** We have, like, some logic that gets shared between different applications. Some utilities. And then the other awesome thing about this is, um, I think it might be possible to do this with the git URLs, but in, sort of, in conjunction with switching to GitHub packages, I also turned on Dependabot for all of our private repos.

[00:13:58] **Adam:** And so now it's giving me security update. Notifications for all of our private repositories and telling us about, you know, security updates for all the different modules that we're using. So it's been nice. It kind of helps keep everything up to date. What goes

[00:14:11] **Ben:** in the package JSON file? Is it, is it still a URL though?

[00:14:15] **Ben:** It's just not a.

[00:14:17] **Adam:** Great. So, okay. So my company is called AlumnIQ. Our namespace is like at AlumnIQ. Just so like, I have a couple of packages that I've deployed to public NPM. They're open source that are like at a total slash whatever. And this works exactly the same way in terms of what it looks like in the package.

[00:14:32] **Adam:** Jason. The only difference is the package name gets that at AlumnIQ prefix and then there's in that npmrc file you specify at AlumnIQ I forget the exact syntax but basically you say this namespace and then there's a some delimiter and then it says this is the the url for the package repository so in this case it's just some special host name at github that says okay use github packages for that namespace and so it In the early days of NPM, there would be people who would like mirror the entire public NPM repository and you could like change your repository URL to use somebody else's.

[00:15:09] **Adam:** And it's basically the same thing, but it's scoped to just packages with that prefix.

[00:15:14] **Ben:** Interesting. I didn't even know that uh, NPM could do that. That they could sort of, I don't know if alias is the right word, or I guess create like resolvers for prefixes?

[00:15:22] **Adam:** Like namespace sort of thing? Yeah. That's pretty awesome.

[00:15:25] **Adam:** I didn't know that. I think that's part of their business model. It's like public stuff is all free, but then if you want private... You know, closed source stuff, then you can pay extra for that.

[00:15:34] **Ben:** Very

[00:15:34] **Adam:** cool. What's the difference

[00:15:35] **Carol:** between NuGet and NPN? Cause we had a bunch of NuGet packages. I

[00:15:40] don't

[00:15:40] **Adam:** think NuGet is JavaScript.

[00:15:41] **Adam:** Is it?

[00:15:42] **Carol:** No, it was C sharp stuff that we were doing. I

[00:15:45] **Adam:** mean, there's, there's like pip for Python and Ruby gems or it's just their package manager. Oh, okay. Okay, cool. Well, before we move on to our main topic for the day and learn all about feature flags, there's a couple of things that we wanted to announce and sort of, uh, Get the ball rolling on.

[00:16:02] **Adam:** So Tim, tell us about the hotline. You've set it up. You take the honors here. The idea of our podcast is

[00:16:07] **Tim:** like, it's a virtual water cooler where a bunch of friends, we hang out. We talk about developing code and our challenges of the day. And if you want to add your voice to this virtual water cooler, then you can hit us up on our new voice message service and leave us a shout out, a review, a topic request on our message line.

[00:16:24] **Tim:** That's 512. 2, 5, 3, 2, 6. Three, three. That's five. 1, 2, 2, 5, 3 code. Nice. Nice. Yes. But yeah, we want you to be part of the conversation, so join

[00:16:36] **Adam:** us and to all

[00:16:37] **Carol:** of our, uh, conference friends, we miss hearing your voices. So please

[00:16:41] **Adam:** call. In fact,

[00:16:43] **Tim:** we actually got this message just recently.

[00:16:50] **Carol:** So we had no idea

[00:16:51] **Adam:** who that was,

[00:16:52] **Tim:** right? I don't know who that was. I don't, did you, I didn't share the

[00:16:55] **Adam:** number with anybody. I posted it in our discord. I figured. Okay.

[00:16:58] **Tim:** That is one of our Discord members, so yeah.

[00:17:01] **Adam:** Alright, um, so then the other sort of announcement that we wanted to throw out there is we're going to try something else new here, you know, tossing out lots of different ideas and seeing what sticks.

[00:17:10] **Adam:** Um, it was suggested that we should read a book. Um, I think, uh, our, our, uh, off the cuff extemporaneous commentary maybe gives people the impression sometimes that we're not well read. So, it was suggested that we read Clean Code by Uncle Bob Martin. And we will. Yeah. You know what? We're going to turn it into content.

[00:17:30] **Adam:** We're going to read the book and we're going to discuss it as an episode of the podcast. So, uh, yes, we're going to read Clean Code by Robert Martin, which If you're lucky, you might be able to get a copy from your local library, or you might have to buy it from Amazon, or there's actually

[00:17:46] **Tim:** an

[00:17:46] **Ben:** Audible book of it.

[00:17:48] **Ben:** Use your credits.

[00:17:49] **Adam:** It's crazy. We're going to discuss it on episode number 22, which should air on May the 12th. And if my math is correct, that is four weeks from today as you're hearing this or as we've released this episode. So we're looking forward to that and should be a good discussion. And now I suppose on with the show.

[00:18:04] **Adam:** So Ben, you've been talking about. Feature flags, like they're the, the Messiah for so long now. We, we have to know what's the, the good news. Stop teasing. Come on, man. Bring it on. No, maybe, maybe now would be a good time to say not sponsored, right? Not by LaunchDarkly or anybody else, but we're open to it.

[00:18:21] **Adam:** Hint, hint. Right. LaunchDarkly, reach out. Love to have you on.

[00:18:27] **Ben:** So I state this with. No hyperbole that I believe feature flags have fundamentally changed the way that I program more so than any other technique that I have ever learned. And essentially what a feature flag is, is the ability to separate the idea of deploying code from the idea of releasing code.

[00:18:54] **Ben:** Before feature flags, you wrote your code, you push it to production, and it either worked or it didn't work. And if it didn't work, you either had to quickly push a fix or you had to revert and roll back all of your changes. By putting your code behind a feature flag, what it allows you to do is deploy your code to production, leave it dormant, meaning that it's not facing your users.

[00:19:20] **Ben:** Unless you have some sort of feature flag technology that allows you to target specific users such as users internally to your company, users that have certain email addresses, users that fit into some sort of a bucketing scheme, and then you could even roll out users based on percentages typically using some sort of a C R C codes, so on.

[00:19:42] **Ben:** So you could slowly roll it out to say, 2% of users and then 10% of users and 50%, a hundred percent, and so on and so forth. And once you have this mechanism in place where you can separate the deployment of code from the releasing of code, it really radically changes the way that you think about architecture and about how you incrementally can build a feature.

[00:20:09] **Ben:** Because again, without feature flags, it's basically. All or nothing, because there's no way to hide things from your users. But once you have this ability to launch darkly or to deploy things without being visible, you can start to deploy what you could consider incomplete features. And the other week we were talking about pull requests and how I have some very heavy feelings about how pull requests should be managed within a team.

[00:20:35] **Ben:** And one of those feelings that I have is that pull requests should be very small or as small as possible. And part of the way that my team is able to do that is because we essentially live and die by feature flags, and we're able to ship parts of features to production that aren't necessarily feature complete from a holistic standpoint, but are feature complete from maybe a slice of a feature.

[00:21:02] **Ben:** So like all of the server side components. Or all of the controller components, but just raw HTML without the CSS, and then people can come back and do CSS after that. And the reason you like to break things up about it is because it keeps easier to think about when you're talking about pull requests.

[00:21:20] **Ben:** And reviews, meaning that someone can look at, say, the server side workflow for data processing of a feature, and they don't necessarily have to worry about all of the client side code at the same time. They can look at just the server side portion, validate whether or not that meets the requirements.

[00:21:37] **Ben:** Then we can ship that, and it's behind a feature flag, so it doesn't matter. And then the next PR can be maybe just the client side implementation. And the person who reviews the client side code essentially doesn't have to think about the server side code at all. The server side code has already been validated and deployed.

[00:21:53] **Ben:** So you treat the existing code in production almost like you're consuming a third party API at that point. And it just, it just, it's so powerful. I can't underscore how much it has changed the way that we develop it.

[00:22:07] **Adam:** So, I'm glad you took a pause there because I've been wanting to interject this question here.

[00:22:11] **Adam:** No, sorry. No, it's fine. Uh, you, you keep making that point where you can deploy a chunk of a project Like you said, the server side components, and then later deploy another chunk, and when I'm thinking about this, the, the workflow, the lifecycle that I'm seeing in my head is that each of those deploys comes with an associated, like, pull request and code review of its own, and I think something that I'm getting stuck on is when I'm going to, like, if I don't have feature flags, when I'm looking at that code and doing the code review, one of the things that I'm looking for is to make sure that, like, the client side code, the API that it's using, the shape of the requests matches the shape of the requests that the server side code is expecting.

[00:23:05] **Adam:** And if that, like, if that server side code is already deployed... If I wanted to compare that, I guess I would have to go look it up in the code base and, and make sure that like the function arguments are the same, they're in the right order, that sort of thing. Which is totally doable, but I guess one of the things that I like about grouping them together in the same pull request is that they're already right there, right there in the diff.

[00:23:28] **Adam:** Both of these things change and, and makes it a little easier to find them, especially if the pull request isn't overly long. Sure. If you're separating those two things. Do you not run into that problem or do you have some other way of

[00:23:44] **Ben:** avoiding it? I think it comes down to a matter of trust in that you trust that the previous pull request was, was evaluated properly.

[00:23:56] **Ben:** And so you can essentially have a big check mark around this circle of code that's been already deployed so that when you then have to evaluate the client side code that consumes that server side code, you,

[00:24:10] **Adam:** it. Right. But I guess what I'm talking about here is not that it's not that the client code is wrong, but it's that integration layer between the two, right?

[00:24:18] **Adam:** If you've got the exact same arguments, but if you've got them transposed, if you've got two of them switched, right? If you're calling a function,

[00:24:24] **Ben:** um, Yeah, sure. I mean, ultimately, I guess part of the question becomes what is the role of the person doing the review of code? Uh, and I, I'd say from, from how you're describing it, we view PR responsibilities maybe a little bit differently.

[00:24:45] **Ben:** Okay. In my eyes, the person doing the review is not necessarily responsible for ensuring the accuracy of all of the code that the person writing the code should be doing that. And it's, it's too much responsibility for the person at work. We call it ensuring the success that, that the person doing the review, their role is not to ensure the success of the code that the person writing the code is there to ensure the success of the code that the person doing the review.

[00:25:16] **Ben:** Is there more to catch red flags or large architectural problems that things like the order of arguments, to me, is out of scope for how we handle PRs at work?

[00:25:31] **Tim:** I kind of feel dumb here. I kind of need to ask you to zoom out a little bit more and give me a bigger picture. Is feature flags, is it a style of coding?

[00:25:41] **Tim:** Is it a service that you pay for? I mean, I don't fully understand. The benefits sound great. I just don't know Yes. So how do you do

[00:25:51] **Ben:** it? Uh, essentially you, you can describe it fundamentally as an if statement that there is a mechanism by which you can, in your code, say, if this condition is true, execute this control flow of code else use this other control flow of code.

[00:26:10] **Ben:** And the feature flag is the condition of that if statement. And then the mechanism by which that condition is made available to the developer. That's, that becomes now an implementation detail. So for example, we use LaunchDarkly at work. So the thing that provides us with the information for that if statement is their LaunchDarkly client.

[00:26:32] **Ben:** They have clients in a variety of languages, so we use the the Java SDK because we're on ColdFusion. But essentially, you could do it with the keys stored in Redis, you could look things up in a database, and essentially all it becomes is if this feature is turned on for Tim. Do this code, otherwise fall back to the old code, kind of a thing.

[00:26:56] **Carol:** Yeah, the way I think about it is if you had users and say you wanted to have like a settings table that says, you know, has access to this, you know, you know, to this button. You could then in even a database, you know, put. A 1 flag for 10 of your 100 users that you have. And those 10 would then have access to it, so it would just say, if.

[00:27:17] **Carol:** Setting equals true, then show that button, um, else they're not going to get it. So then when you kind of vet it out, you. Introduce it to more of your users, and that isn't how it works with. Launched darkly from what I had saw online, but that's kind of just how features work in my head. Like, that's how I think of them.

[00:27:37] **Adam:** So how do you prevent

[00:27:38] **Tim:** your code? I mean, it's not an if statement though, in practice, I mean, otherwise your code would be a huge mess of giant, confusing if statements. I mean.

[00:27:47] **Ben:** Well, it can be, it can become a giant mess of if statements and part of the discipline of using feature flags. is having a life cycle around how they're applied to the code.

[00:28:00] **Ben:** So if you leave your feature flags in your code for too long, then they start to rot and the code becomes complicated, and it's hard to look at the code and understand what's actually happening because you can't necessarily see. In the code itself, what the state of that feature flag is, meaning, has it been rolled out to every user, has it been rolled out to a segment of users.

[00:28:21] **Ben:** So, ideally you want to keep your feature flags in your code for as short a period as possible. So typically, when you're working on a project that uses feature flags, you'll deploy the code behind feature flag, then you roll the feature out to users, and then once it's been fully rolled out to users... You want to make sure that you go in and now what we call committing to the new workflow, which includes removing the feature flag and then removing the old code that is no longer been being called anymore because of the new, the new change in the control.

[00:28:57] **Adam:** The way that I've been thinking about it as I'm hypothetically. Implementing this in my head over the last months since Ben has started This little devil on my shoulder telling me feature flags feature flags has been To think about it like if there's some code that I want to do an alternate version of Think about trying to encapsulate that in a function call And then have an alternate function call that I can make so that your if the if becomes like if feature is on whatever call this function else call the other function close the conditional so yeah I mean it is an if but it's as compact as you can possibly make it and that also makes it easy to delete the old one.

[00:29:35] **Adam:** Right then

[00:29:36] **Carol:** to rip it out becomes a lot.

[00:29:39] **Adam:** So,

[00:29:39] **Tim:** so what part does LaunchDarkly do then? I mean, if you could just do this in an if statement, what,

[00:29:44] **Ben:** what service are they providing? Yeah. So essentially what LaunchDarkly provides is the entire mechanism for defining and changing your feature flags over time, as well as targeting different sets of users.

[00:29:56] **Ben:** And then of course they have a whole seat model for who on your team can actually log into the LaunchDarkly dashboards and actually change that stuff. So until you start to use LaunchDarkly itself, it's hard to understand why you would pay for it because it feels like something you could build. But the, the, the technique that they use is actually super, super clever.

[00:30:18] **Ben:** Essentially, if you think about trying to implement it with a database, for example, and then you want to check your feature flags at various points in your request, then you either have to go to the database at the top of your request, get all of your feature flags for the current user. And then propagate those feature flags down to the rest of the request processing.

[00:30:37] **Ben:** Or, you just on the fly hit your database, so if you want to check feature flags 6 or 7 times in a request, then you have to hit the database 6 or 7 times. There can be some performance implications there. The way that the LaunchDarkly client works is essentially they keep a... A rule system in memory in their client, and then they're using, um, server sent events or streams.

[00:31:02] **Ben:** I, it's technology I don't understand, but essentially they have, uh, uh, the client and your code is connected to their servers. So when you go into the LaunchDarkly dashboard and you update the feature flag targeting on their servers, It's sending these events in real time to your code. And then all the code, all the client is doing in your code is updating this rule system in memory.

[00:31:24] **Ben:** So even if you check feature flags. You know, hundreds of times within a single request, which is crazy. I'm not advocating for that. But even if you were to do that, all it's really doing is checking an in memory data structure. So there's essentially no latency to how it works. And the updates happen instantaneously between the LaunchDarkly servers and the LaunchDarkly client that you have running in your code.

[00:31:47] **Ben:** So it's, it's just, it's, it's all the things that you could build if you wanted to make having feature flags, a differentiating feature for your. Company, but that's probably not the product you're building. So you, you pay for it and you have LaunchDarkly build out the cool tooling and then you focus on your business.

[00:32:06] **Ben:** And, um, it's really, it's, it's a, it's a very impressive piece of. Uh,

[00:32:13] **Adam:** technology, I think. Something that we've kind of touched on a little bit so far that I think might be worth digging into a little bit more is the user segmentation stuff. So, you and Carol have both mentioned a little bit on the ability to do like a, like a staged rollout.

[00:32:26] **Adam:** You can start with, say, 1% of users or, you know, users for this particular customer. If you have a group of users. Geographical? Geographical, yeah. So there's a, an open source, I guess, competitor to LaunchDarkly. It's called, uh, Flagsmith that I was playing with. Uh, a couple of months ago, I guess, and the, one of the reasons that I kind of gave up on that effort at the time was, it was frustrating to me the way that it seemed like they want, wanted me to register new users with the system.

[00:32:57] **Adam:** Um, and it seemed like my choices were either to preload them all, you know, like, in advance of them ever hitting the application. Like just load all my users in and every time I add a user also go over and add it to their system. Or to like register a user at login and then it just it seemed not ideal to me.

[00:33:22] **Adam:** I don't know if LaunchDarkly is any different. But the other, the other part about this, and I know you and I, Ben, have talked about this a little bit off podcast, um, the, the way they do segmentation is very, um, opaque and interesting to me. Like, if you're gonna do, if you, if the request is to do, you know, 5% of users, is that deterministic?

[00:33:47] **Adam:** Or is it like the first 5% of users to hit it? Or like, you know what I mean? Like if I say 5%, how does it determine whether Ben gets it and whether Carol gets it and whether Tim gets it right? It, it

[00:33:59] **Ben:** is deterministic in, in the sense that the hardest part of learning how to use LaunchDarkly was wrapping your head around.

[00:34:07] **Ben:** How the targeting works. So how do you target a specific user, specific subset of users? And essentially what I talked about earlier is that how, what the launch darkly client is doing is maintaining a rules engine in memory. So you almost don't think about it as targeting specific set of users. You think about it as, what are the inputs to this rules engine, and then the rules engine spits out some segment of users, and then I can then either turn a feature on for all those users, or some percentage of those users.

[00:34:41] **Ben:** So, when it comes to something like, let's say I want to target the user with ID 1234. You're not necessarily targeting the user with ID 1234. You're saying there's a rule that targets this user whose primary key is 1234 that gets synced over to this in memory rules engine. Then what happens is when your application says, Hey, I need the feature flag for this request more, more or less, that ask of the LaunchDarkly client has to provide a set of inputs to that rules engine.

[00:35:10] **Ben:** So it says, I need these feature flags, and the data associated with this request is userID1234, email is johnsmith at example. com, you know, started date is November 2020, and then the rules then just says, okay, here's all these inputs, do any of these inputs now match any of these rules? Oh, here's, you know, we have this rule for user1234, so now I can just Return that this feature flag is turned on for this user.

[00:35:35] **Ben:** That took me like six months to really understand how that was working. It was, it was just very weird. It felt like a very inverted way of thinking about targeting people. But once you think about it, kind of like a pure function is the mental model that I have now that you're the rules engine defines the logic of the pure function.

[00:35:55] **Ben:** And then your application has to provide all the inputs that drive that rules engine. So what I mean is, let's say you wanted to target all users that end with an email address that ends with at alumniq. com. Well, if you then go to the LaunchDarkly client in your code and say, Hey, I need all the feature flags for user ID 1, 2, 3, 4, the rules engine's like, well, I don't know who user ID 4 is, or at least I don't know how that associates with the rule that you gave me about email addresses.

[00:36:23] **Ben:** Right now, What makes that even more confusing is that what you were saying earlier about how you have to register users, well, LaunchDarkly sort of does that as well. When you. Ask for feature flags. There's also an operation where you can identify users and it builds up this user base in LaunchDarkly, which sort of makes you think that LaunchDarkly is this database where if you identify this user with an ID and an email address, that you can target the email, but not provide the email and the code.

[00:36:53] **Ben:** Cause they would just have this connection in its own database, but that's, it's just not how it works. Now that's a LaunchDarkly specific thing. That's not a feature flag specific thing. That's just how their rules engine and their matching works. Talking about the targeting is probably the most complicated part.

[00:37:10] **Adam:** I think I get the, like the inversion of targeting sort of thing you're talking about there all except I still don't understand how percentages work. Right? So like if I said 50% of users, like, is that totally random? But then it's like, once it's decided, it picks them at random, but then it, it, once it's decided, it somehow remembers which users got on and off

[00:37:30] **Ben:** or it's my understanding is that all of the percentages boil down to Being able to take a set of input values and create a consistent integer.

[00:37:42] **Ben:** Okay. Um, I think internally a lot of the feature flag systems use a, something called CRC 32, which I think can take like any input and give you some sort of like a checksum sort of thing. Yeah, yeah, exactly. So essentially the percentage based rollouts become, here are all these inputs, generate the number, and then that number boils down to.

[00:38:05] **Ben:** Some value between 0 and 100 probably based on some sort of modulus. Yep. Arithmetic. Okay. So as, as long as you can consistently take those inputs and generate an integer, then the percentages can be calculated consistently as well.

[00:38:20] **Adam:** And that answers the question for me. Perfect. Thank you.

[00:38:22] **Tim:** Could you like, if you want to 50% say if, if your user ID is odd, give them the New feature, if it's

[00:38:29] **Adam:** even don't, that's kind of what it boils down to, except it's the c r C instead of user.

[00:38:33] **Adam:** Right?

[00:38:34] **Ben:** Right. Like LaunchDarkly is cool because you can mix and match different rules. So you could have rules that say, target this specific set of users regardless of percentage rollout. And then you could also have a percentage rule as, as the default rule. So, essentially, the rules engine in LaunchDarkly, it's like this fall through kind of decision tree, so you can target people very specifically, and then if they don't get targeted, I think it can fall through to lower level rules, and then you can do default rules, and those can all have percentages, so it's, you can specifically include people, you can specifically exclude people, think you can target groups of people, and then do percentage rollouts based on those groups as well.

[00:39:16] **Ben:** You know, we, Like a lot of technologies, we started out trying to be maybe more clever than we needed to be. And over time, we've decided that, or we've found patterns that are just more straightforward, where it's basically, you're targeting specific users, or you're targeting maybe a specific company, or you're just doing a percentage.

[00:39:37] **Ben:** And then ultimately you're driving to a hundred percent. Or if you have features that you know will never be released broadly. You know, we just stop it at some sort of a company level.

[00:39:48] **Tim:** So, so it sounds like this is by no means a good practice or a recommended practice, but there's been times

[00:39:53] **Ben:** it's a mandatory practice.

[00:39:55] **Ben:** No, no, no.

[00:39:56] **Adam:** The thing he's getting ready to say, okay.

[00:40:00] **Tim:** Is so sometimes it's like there, there's a function that I've written that for some reason is it works 90% of the time, but there's this percentage of. People that for some reason it doesn't work and it works fine in development. Works fine in staging.

[00:40:17] **Tim:** It's just production where it breaks. And so I have at times created a function version two or three, whatever, and put an if statement around it that basically says, if you are this person and that person sometimes is usually me, it's something that identifies me coming during the request, do this. And so that I can run through and test it.

[00:40:40] **Tim:** In the only environment where I can figure out where it is. And then I figure out, I learned something from that. And then at some point I go, all right, I figured this out. I'll incorporate the change, delete all those if statements that I, that I put in there and launch it, but it's just a lot more sophisticated and it probably has some, some better reporting and tracking mechanisms on it.

[00:41:01] **Adam:** Tim, you just created a feature.

[00:41:03] **Tim:** I did it years ago. I didn't

[00:41:04] **Adam:** even know. You didn't even know it. I didn't even know. I should have started LaunchDarkly. I mean, it's like debugging in production, but only you can see it happening. Yeah, exactly right. It's, it's,

[00:41:13] **Tim:** it's, yeah. I feel like we've all

[00:41:14] **Carol:** done it. Yeah.

[00:41:15] **Adam:** Yeah. I think everybody's done it. At some

[00:41:17] **Ben:** point. Well, I mean, this is so completely relevant to what I just did at work. So one thing that I've been spending like the last week and a half doing was merging a microservice, a Go microservice back into our ColdFusion monolith. And what made this adventure particularly exciting was that I can't run that Go service locally.

[00:41:40] **Ben:** So I'm digging through the code in their repository, trying to understand what the data model looks like and the API response, but I can't call it until my code reaches production. So as part of the development process, and this is probably gonna make a lot of people throw up in their mouths a little bit, is I literally have a feature flag that will call the API.

[00:42:01] **Ben:** And then log the payload to our log aggregation service. We use Logly at work. And then I would deploy this code. I would turn it on for my user. I would look at what shows up in the logging, then I would turn the feature flag off for my user, and this fell back to some older code that would get logged as well, and then I would literally take the JSON payload with the feature flag off, and the JSON payload with the feature flag on, and compare it in this JSON diffing tool to see where my model of the data was inconsistent with the model returned from Golang, and then I would make more changes locally, and then I would deploy it again, I would do the same thing, and it was Uh, literally debugging live behind feature flags, which, if I didn't have feature flags, I don't even know how I would have begun to attempt something like this.

[00:42:48] **Ben:** It would have been, uh, crazy.

[00:42:51] **Tim:** You guys don't want to know how the sausage

[00:42:52] **Ben:** is made, y'all. Yeah.

[00:42:56] **Adam:** That's why they're here, because they need somebody to commiserate with.

[00:42:58] **Carol:** They all understand. So, one that I had looked at before, it's called SplitIO. I posted the link to it in there. I don't know if you guys have ever looked at it, but they actually have some pretty cool, like, references in, on the site if you wanted to go through and just check out, um, some definitions of stuff.

[00:43:15] **Carol:** But one of the things that you would ask about, Adam, was, um, how the percentages roll out and they actually are like, hey, we'll just explain to you what progress, like, what progressive delivery is, like, and how it works. So they kind of explain. A little bit in detail there, so if you want to go look at it.

[00:43:35] **Carol:** Heck yeah. And then they have links to a few books too, if you were curious.

[00:43:40] **Adam:** Books? I don't read anything.

[00:43:42] **Carol:** We'll add it to our reading list. There's like a feature flag

[00:43:46] **Ben:** book. That's cool, I didn't know there were any books about

[00:43:49] **Carol:** feature flags. Managing feature flags. It's an O'Reilly book.

[00:43:53] **Adam:** Well, this is important then, what's the animal?

[00:43:58] **Tim:** O O O'Reilly?

[00:43:59] **Carol:** Actually a ski thing. Like, cause aren't all the O'Reilly books, they have animals on the front? Is that what you were referencing? Yeah. No, this is like ski slopes. Yeah.

[00:44:10] **Adam:** I gotta go look this up.

[00:44:12] **Carol:** Yeah, just go to the main site and scroll down to almost the bottom. It looks like you're going down a ski slope.

[00:44:18] **Carol:** It's the only one I've seen that doesn't have an animal. Did they run out of animals? I mean, these are your future

[00:44:22] **Adam:** flags. Maybe my ad blocker is killing it. Give me a second. Multiple ad blockers. I got to turn off. I don't want to see any ads. Yeah, seriously. I don't see it. I just split it to you. It's always, I'm at the bottom.

[00:44:40] **Adam:** I can't scroll down anymore. All right, Drake. Is there a link to it that I'm not clicking

[00:44:46] **Carol:** or like? No, I mean, I put it in the notes to show notes. It's the top one. I just put it on there. Oh, weird.

[00:44:53] **Adam:** I put it in discord. Yeah. Yeah. That's like, that's weird. Slom skiing. Weird that I don't see it. Maybe they turned it off for my user.

[00:45:03] **Adam:** Yeah. You don't

[00:45:03] **Carol:** have that feature.

[00:45:04] **Adam:** Yeah.

[00:45:05] **Tim:** So Ben, I got to ask you, are there any negatives to this? Are there anything, is there anything that you would change about feature flags or is it just like the perfect morsel? I

[00:45:17] **Ben:** mean, the, the biggest downside is that you have to have dedication around how you move feature flags through your application, because we have over a thousand feature flags in our LaunchDarkly dashboards right now.

[00:45:30] **Ben:** And not all of those exist in my application, but certainly I'd say hundreds of those feature flags exist in my application. And it's, it can be very challenging to maintain code that is in flux. Um, so if you're dedicated to writing code behind a feature flag, Rolling it out to users and then removing that feature flag and the dead code that's no longer needed, then it's all gravy.

[00:46:00] **Ben:** But if you don't have the dedication around that, your code can definitely become fairly confusing.

[00:46:06] **Carol:** You have the feature out and say the feature throws errors and you don't get it resolved. Do you, if you kill that feature and realize this isn't a feature we're going to use, or the feature isn't actually acceptable and you don't like the workflow with it.

[00:46:21] **Carol:** Do you also then go remove that feature and take that code out if you don't approve it once it goes in production?

[00:46:28] **Ben:** Yes. Uh, essentially, so one of the other use cases that we have for FeatureFlag is that it allows us to load test in production. So sometimes you'll, one of the changes that you'll need to make in an application is you'll need to refactor a SQL query.

[00:46:45] **Ben:** End. Or any kind of database query and you can run explains and look at, uh, query plans locally, but sometimes those aren't entirely accurate because they're based on statistical models of the amount of data you have locally. So. Sometimes you just don't know how rubber is going to meet the road until your code hits production.

[00:47:04] **Ben:** Now you could spin up an entirely different staging database and have a team that helps you manage load testing in a staging server. You actually could run load tests. Yeah, like you could actually run load tests in like a thing people do. Or... You just do it all in production.

[00:47:22] **Adam:** You Bill O'Reilly

[00:47:23] **Ben:** it. So, so what you could do is you, you write your alternate control flow, control flow through the code.

[00:47:31] **Ben:** With the new database query, you deploy that to production behind a feature flag. Then you very slowly roll that feature flag out and you just watch your database graphs. And if it. 2% of rollout, you see a 30% jump in your database. C P U, that query turned out to be a really bad idea. Not a good, not a good one.

[00:47:52] **Ben:** And sometimes you gotta just bite the bullet and say, Hey, we need to rethink the way that we're gonna refactor this code. So you roll it back, you delete all that code, and you, you know, go back to the architecting phase. But a lot of times you'll refactor a query, deploy it, start to roll it out incrementally.

[00:48:09] **Ben:** See absolutely no change in your database. And, you know, what could have taken you days of load testing validation now becomes... Uh, essentially no overhead to your development workflow. Now see,

[00:48:22] **Tim:** that was probably the most compelling argument you've made so far. Ah, nice. Right there. Because I've seen that effect where you make a change to the, to the data query.

[00:48:34] **Tim:** You think it's just a simple change. It shouldn't have any effect and it does. Databases are weird like that. And yeah, that, that's very compelling to be able to just run that and see how it changes the query plans is. Can be very, very insightful.

[00:48:50] **Ben:** We actually got bit by a really bizarre edge case a couple of years ago.

[00:48:55] **Ben:** Uh, in MySQL, there's a query optimization called multi range reads, I think, which is essentially where you have a query that has two different in statements where you can say a value is in this set of values and another value is in this set of values. And sometimes MySQL will look at that query and decide for reasons I don't understand.

[00:49:16] **Ben:** That it's just going to swap the order in which those in statements runs, which is super problematic if the second one wasn't indexed and was depending on the first one to limit the, the intermediary data set tremendously. So what runs on an index locally, whatever reason hits production and it's no longer hitting an index because it's changed the query optimization.

[00:49:42] **Ben:** And then all of a sudden it's doing a full table scan. You know, typically in production, you never want to do a full table scan, but if it's behind a feature flag, you just turn that bad boy off.

[00:49:53] **Tim:** Yeah. You just sold me on that, that, that right there. He sold me a

[00:49:56] **Adam:** hundred percent. Nice. So you've talked a little bit about.

[00:50:00] **Adam:** How it's easy to use a feature flag to create, like, an experiment in your branch logic of the code, and you just kind of went through using it to, like, swap out a SQL statement for an experiment. Are there any other use cases that might not be immediately obvious? Right, I can swap, I could swap out which JavaScript file I'm going to include, something like that.

[00:50:19] **Adam:** But I'm trying to think, like, are there other use cases or uses of this functionality that I'm not thinking of that, you know, maybe they're not immediately obvious, but they're, like, super useful? Sure, uh,

[00:50:31] **Ben:** the first one that jumps to mind is the idea of what we call operational feature flags. So instead of thinking of a, most of our feature flags are very short lived because we want to deploy experimental code, make sure that it works, and then roll it out to everybody and call it a day.

[00:50:47] **Ben:** But we have a lot of feature flags that change lower level parts of the system, and we want to be able to do that on an ongoing basis. So, for example, I have a feature flag that turns on more low level logging. We call it debug level logging, where if we log data at an info or a debug level, so if you think of, just for people who aren't familiar with log levels, typically there's multiple log levels, so there's like fatal error warning.

[00:51:16] **Ben:** Info debug and then I think trace ose, I can't remember if Yeah. Verb Yeah. Or trace. Um, so a lot of times you'll log things that say info or trace or a debug level that you don't actually wanna log in production because it would just be a tremendous volume of data. So you can turn those things off and put them behind a feature flag.

[00:51:37] **Ben:** And then inside your log object or whatever object in your application code does the, the actual writing of the logs. You could have it look at a feature flag and say, well, if this log entry is below info level, then don't log it unless this feature flag is on, then do log. So, if you run into a situation where you really can't understand why something's happening in production, you can turn that low level login on, and suddenly your application will start spewing logs.

[00:52:07] **Ben:** So you, you know, maybe leave it running for a few minutes while you try to reproduce an issue, then you turn that lower level login off, and now you can go look at your logs. Try to find what's happened. So operational things, we have a lot of operational flags, maybe like 20 or 30 operational flags. These are flags that are going to live for the entire lifetime of the application.

[00:52:28] **Ben:** Things that affect, like we could, um, you've talked before. About taking things out of your load balancer. Um, in the, in the Kubernetes system, I don't, I can't remember what containerization you're using, but like in Kubernetes, there's a liveness check and a readiness check, and that'll determine whether or not traffic is going.

[00:52:48] **Ben:** The readiness check determines whether or not traffic will go to a pod. And then the liveness check determines whether or not the pod is healthy and should be kept alive. And you can actually use feature flags to influence the way those status checks respond. So if you have a pod that's not running properly.

[00:53:04] **Ben:** But isn't failing any of its checks. We have some operational feature flags where we can say, I'm going to target this pod ID, and then the health probes for those pods can essentially take themselves offline based on the feature flags. Oh,

[00:53:18] **Adam:** interesting. Oh, that's interesting. So you would, in that case, you would like look at what hardware is serving the request and include that into the inputs of the rules engine?

[00:53:28] **Ben:** Yeah, exactly. So essentially with the LaunchDarkly client, Every user has a key or, you know, what you can, a user is really just a key and the key could be a user ID from a database, the key could be a pod ID, the key could be anything. It's completely arbitrary. It's just a string. So most of the time it's a user ID for us because we're targeting users.

[00:53:52] **Ben:** Uh, but for the operational ones, especially the health probe related ones, the key is the, the ID reported by the pod. And I can't remember, I think it's some sort of like... Environment variable that Kubernetes injects or I can't remember where we get that ID from, but it's unique to every single running instance.

[00:54:09] **Carol:** Can you use it for like A B testing? Like if you're looking at a workflow or you're looking at, um, X, what is the word whenever they accept how the work's going? Like you accept the adaptability. That's not the right word. Accessibility? Uh, not accessibility, but like it's in Google. Conversion? No, hold on one second.

[00:54:29] **Carol:** Have it open right here.

[00:54:31] **Adam:** I

[00:54:31] **Ben:** was going to ask about AB testing too. Yeah. One thing that we tried to do, and this is not really feature flag specific, but we had feature flags that determined whether or not certain experiments were turned on. And then in other tracking software, like other analytics software, what we would try to do is take all of the feature flags for that user and jam it in what they call traits for this particular AB testing.

[00:54:58] **Ben:** Um, and that quickly destroyed our quotas when it came to the A B testing. Cause I think they were looking at how much data we were storing with each event, and suddenly we were jamming this huge rules engine, more or less, into the traits that we were tracking with all of our user events. And I thought, I can't remember if it was optimizely.

[00:55:17] **Ben:** Somebody was like, no, I don't think so. That's way too much data. So please remove that from your code. Can you, can you use it for speed testing? Can you define speed testing?

[00:55:27] **Tim:** So, you make a change. Is it more performant

[00:55:31] **Ben:** than the previous? Oh, yeah. I mean, well, so, yes, but yes with caveats. Meaning yes in that I often do that, but then I need something that tells me whether or not the, uh, experimental code is actually faster.

[00:55:46] **Ben:** So, that might be a StatsD metric that I'm including with each control flow branch. Or it might be something like a... We use Fusion Reactor at work to monitor the JVMs, and you can include custom metrics with your Fusion Reactor tracing, so I could look at my Fusion Reactor request tracing, and then at parts of that request you get segments, and those segments can be named and have times, but typically I use StatsD.

[00:56:16] **Ben:** And then StatsD feeds into Datadog as the monitoring application that we use for all of our metrics. So, what I'll do for, to make it more concrete, is I'll create a StatsD metric that's like, Feature, Speed, Experiment. And then in one control flow branch, where I say if the feature flag is turned on, then log the duration of that metric, but I tag it with Experiment.

[00:56:42] **Ben:** And then in the other control flow branch, I'll tag the same metric, but then I'll, or I'll record the same metric, but I'll tag it with control. So then I have one metric that has two tags, experiment and control. And then I can put that as on a graph and I can see how they compare to each other. And what's interesting too is, is then you can start to roll those experiments out incrementally based on percentages.

[00:57:02] **Ben:** So sometimes you get almost a two rosy picture early on. So if you start rolling, experiment out to like 10% of people. It looks like it's performing wildly better, but the percentages are just based on this random hashing of inputs to a consistent integer. And then what happens is then you start to roll out to more and more percentage.

[00:57:23] **Ben:** And sometimes you hit 50% of users in your experiment and 50% of users in your control. And now you get a better distribution and suddenly your experimental code isn't quite performing great as it was early on. Maybe it's still better, but it's not, you know, once you get a better traffic going to your experiment, it's, it's not as.

[00:57:43] **Ben:** Amazing as you thought it was going to be. Yeah. Three seconds

[00:57:47] **Carol:** back, the word was adoption.

[00:57:53] **Carol:** There we go.

[00:57:55] **Adam:** Just slice that and just cut that. Just cut that. You guys are totally managering right now. It won't be that hard, right? You just take that from over there and you put it over there and everything's fine. I mean, it's just a small word. It won't

[00:58:09] **Carol:** take long. Adoption. I'll say it slow.

[00:58:14] **Adam:** My, my whole team has, uh, trained ourselves really well.

[00:58:18] **Adam:** Certain key words, we notice ourselves saying them, and we've, we've trained ourselves to like, always put it in quotes. Like, anytime you use the word just, it's just this like, light bulb goes off in our head. It's like, you are making an assumption when you say just. Anything after

[00:58:31] **Tim:** the but. It's bad. Right.

[00:58:33] **Tim:** Negates, negates the previous

[00:58:34] **Adam:** sentence. Like, just add an index? No. It's never that easy.

[00:58:38] **Carol:** Oh, now I get it. Took me a second to understand what you meant with the dress thing. Right.

[00:58:44] **Adam:** Just cut out the word adoption and move it over there.

[00:58:47] **Carol:** Just update the one record. That's all you have to do. Right.

[00:58:51] **Ben:** Just delete that page.

[00:58:53] **Adam:** Says Ben. So I don't know who wrote this question about QA and testing. Oh,

[00:58:58] **Carol:** yeah, that was me. So if you are delivering in small increments. How do you get that tested through, like, an SQA or a QA team? Um, if it's not really a fully delivered product, do you wait and test at the end, or do you try to deliver little pieces that can be tested?

[00:59:17] **Carol:** Yeah, great

[00:59:17] **Adam:** question. They test in production?

[00:59:19] **Ben:** More or less, yes.

[00:59:21] **Carol:** Okay, let's go. Okay, let's go. You can't test in production. Do you have a workflow that would make sense

[00:59:27] **Ben:** for that? Well, so right now I'm actually in the middle of trying to build, uh, a new feature for our enterprise users. And I just this morning.

[00:59:37] **Ben:** Got enough of that feature live to the point where I feel like now I can start to show it to our CFT, our Customer Facing Team, and also to our security team, because there's some security implications with the feature. And it's not feature complete yet, but it is isolated behind a feature flag, so now what I can do is go to the people on the security team that are responsible for application and turn the feature flag on for them.

[01:00:02] **Ben:** In live? Oh, in live. Oh my god. Well, that's great because everything is behind the feature flag. So even if you have code that has, I mean, heaven forbid, a vulnerability in it, you're still opening up. Yeah. You're still only opening up access to a limited set of specifically targeted people. So that gives them the opportunity to go in and look to see if there's anything that they need to change or, or isn't compliant with something.

[01:00:32] **Ben:** And then you can go to the support team and we can say, Hey, you know, here's this feature we're working on. Is there any new documentation that needs to be generated? They can go through and give their perspective from how they think users are going to react to it because they're the most user facing people.

[01:00:46] **Ben:** And then you can start to sort of collaboratively flesh out, polish this feature in production behind this feature flag before you turn it on for your general user.

[01:00:55] **Carol:** It just sounds so scary to me.

[01:00:57] **Ben:** It's, it's amazing. It's amazing. I can't tell you. I mean, like, so, you know, I, uh, I talk about how I don't do a lot of testing or I And I, I, FeatureFlag, I hate to say that FeatureFlag doesn't, it doesn't replace testing, but it makes me very comfortable with not having automated testing because it gives me a lot of confidence in the ability to change things incrementally and look at them in a very narrow focus.

[01:01:32] **Ben:** And then worst case scenario, turn features off if I find out that they're not working properly. Because it's a limited launch. Yeah.

[01:01:41] **Carol:** And it's faster to turn the feature off, usually, than it is to roll back the code, or...

[01:01:46] **Ben:** Oh yeah, it's instantaneous.

[01:01:50] **Adam:** So I had a thought about your question, Carol, for, um, using feature flags in conjunction with having, like, a dedicated testing team or something.

[01:01:57] **Adam:** Yeah, like we do, yeah. If you just take out the element of like what Ben's team does where they break everything down and they deploy an individual line of code in its own pull request and you do like you know one medium sized pull request with the entire feature in it then you could turn it on in your QA environment for The team or whatever.

[01:02:18] **Carol:** Yeah, I mean, in my head, the way I think about it is that, you know, we have our story that we're going to be working on and then we have all of the ACs for it. That you would have to break out an AC into functional code. Oh, acceptable, acceptable, uh, acceptance criteria, acceptance criteria. There you go.

[01:02:37] **Carol:** It's basically the piece you have to do. So there'll be like, 10 things you have to do on the story. So, you would want to be able to break that out into each little piece, so they could test, like, AC1, AC2, AC3, and then at the end, when it's all together, you would then be able to turn it on for a full test.

[01:02:56] **Carol:** But I think they would be very frustrated with us if we just put out all of it and then at the end said, go do it without giving them the time

[01:03:05] **Ben:** beforehand to do it. Uh, and one thing that this is LaunchDarkly specific, so I don't know how well this can be extrapolated to other feature flagging implementations, but on the LaunchDarkly side, they have what they call, I think, projects.

[01:03:23] **Ben:** Projects, I believe, just boils down to an SDK key. So you could have a different key for different environments. So you might have a key for local development, a key for staging, and a key for production. And then you have a single set of feature flags across all of those environments, but then you can target the keys in different environments.

[01:03:45] **Ben:** So you could turn something on in just the staging environment, but not in production. Or you could turn it on just in your local developments while you're developing the feature, but not in production. So again, that's LaunchDarkly specific, but I assume that's probably a common pattern. Split has that.

[01:04:04] **Adam:** So Something that I'm kind of tripping on here, and this probably shows one of my current frustrations with our code base and our workflow. The way that we are currently structured, deploys are not the fastest thing. It's a little bit frustrating to like, I was explaining to you guys in private some of my frustrations with our code base today.

[01:04:21] **Adam:** The proliferation of pull requests, if you remember that discussion. So, the idea, like, so for every feature that I wanted to deploy, right, even if I take the thing I said before and sort of, package multiple Invision pull requests up into what would be one AlumniQ pull request. Every feature that I want to deploy, instead of being one pull request and one deploy, is now two pull requests and two at a minimum, right?

[01:04:46] **Adam:** So I've got to put it out in production with a feature flag to test it. Assuming it's one that I'm going to put behind a feature flag and do the testing. And then at the end of that test, I have to go, I either have to decide that The experiment was successful. I'm going to rip out the old code, which takes another deploy, or I'm taking out the experiment because it was unsuccessful and maybe I'll try again.

[01:05:06] **Adam:** Maybe I won't, but basically I'm looking at roughly instead of end deploys. Now I'm talking about two end deploys. So we've gone up, I guess that's not technically an order of magnitude, but it's a significant amount of deploys. I don't know how fast deploys and how. Painful or painless deploys are at your, in your environment, but is that something that you think is going to be, uh, something to consider when deciding whether or not to use something like Feature Flags?

[01:05:31] **Adam:** Uh,

[01:05:32] **Ben:** so deploys at work are good. They're not great. When we deploy, it goes to preview environment, and then it goes to a multi tenant environment, and then it goes to a series of single tenant environments. Those are our promotion. We call them like promote from tier to tier. Um, roughly speaking from initial, well, from the time that CodeShip is done building the containers, because that can sometimes vary wildly, that can maybe take like 10 minutes just to build the container.

[01:06:03] **Ben:** Once the container is finished, then it roughly takes between 3 and 5 minutes to get to the, to the preview environment. Then once we've verified and preview, it can take like 10 minutes to get from preview to multi tenant. And then it can take... Anywhere from 10 minutes to like 45 minutes to get from the multi tenant to all the single tenants because a lot of times things will fail or, um, Amazon will run out of a certain size of machine and then we can't spin up the, the nodes for some subset of single tenant instances and then the deploys get stuck.

[01:06:40] **Ben:** So that sucks. Um, But usually, we try to be pretty good about including the feature flags and staying dedicated to that. Sometimes, if the feature flag is really small, I won't bother removing it right away. I'll, I keep a text file in my IDE. Of like, here's the feature flags that I've used lately, and I need to go and delete these.

[01:07:04] **Ben:** And then sometimes, I'll have a PR that just deletes like, six different feature flags. Combine them up, yeah. They just cover, yeah. Because otherwise, yeah, you're like, I don't want to go through this whole 45 minute deploy to remove six lines of code, that's crazy.

[01:07:18] **Adam:** And, yeah, so do you have to, I mean, I guess this is entirely a question about your environment, but then do you have to sort of babysit that entire deploy process, or can you just kick it off and walk away and know that by the end of the day, That feature flag will be cleaned up and if it somehow breaks things, then you're going to get a page or whatever.

[01:07:35] **Ben:** Uh, I mean, people typically babysit their deploys. I mean, I'll be much more cautious going to our multi tenant environment because that's the first time it hits user facing traffic. If it hits the multi tenant environment and it seems pretty successful. I'll promote from multi-tenant to single-tenant, and I don't really watch the deploys at that point because I feel like the single-tenant is basically rubber stamps of multi-tenant, right?

[01:07:59] **Ben:** There are all kinds of weird little caveats and edge cases, but, um, for the most part, if it hit multi-tenant successfully and I'm watching the database graphs and I'm watching the, the error logs and, and nothing's tripping, any red flags, then, then I'll just promote to single tenant and I'll go and I'll usually start working on something else.

[01:08:21] **Ben:** But it is, you know, and then it's not, uh, not every line of code gets wrapped in a feature flag, it's, it's risk evaluation and risk mitigation. So. And some things don't lend well to feature flag, like c s s changes depending on how your application's architected. Mm. It's c s s isn't really something you can necessarily wrap behind a feature flag because it's kind of this externalized

[01:08:46] **Adam:** resource.

[01:08:47] **Adam:** I wish I it'd be a pain. The, the feature flag is an embedded style tag with important tagged on the end of it. , oh.

[01:08:55] **Ben:** You know, sometimes like what your feature flag can do is your feature flag can change which class gets applied to an element. And then you could have, then, you know, you have two different style blocks.

[01:09:09] **Ben:** I don't know what you would call them yet.

[01:09:12] **Tim:** So, so far been, I've been processing this entire conversation through a ColdFusion filter because that's where you come from. And that's where You know, I started, but I just actually right now did a Google about Scala and, um, LaunchDarkly and FeatureFlags and found actually one of the companies, one of our partners that we use for Scala development, and they had a whole thing.

[01:09:39] **Tim:** I put it in the, um, the Google Doc there.

[01:09:44] **Adam:** One of the

[01:09:44] **Tim:** things they talk about, it's a good, it's a good use case is KillSwitch. Right, so you can use LaunchDarkly and FeatureFlags as a kill switch of, you know, you release it out to 1% of your users, you get feedback, it's not performing well, or whatever, you can kill it immediately.

[01:10:03] **Tim:** And that's, I mean, if you have a huge customer base, you know, prevent, if the choice is, I'm going to fail in front of 1% of my users, or... A hundred percent of my users, I'd much rather fail. Yeah. One, please. Yeah. That's a much easier PR problem than a hundred percent of people like, Oh, sorry, we released this and it really messed everything up, particularly when you're dealing with people's money.

[01:10:30] **Ben:** Well, absolutely. And you know, going back to the idea that at least in the launch darkly implementation, you can target different environments. So at work, we have a multi tenant environment and then a bunch of single tenant environments. Single tenant environments are a higher price point contractually speaking.

[01:10:47] **Ben:** So sometimes if we have, let's call it particularly risky code, we'll turn it on in multi tenant, which are just lower price point clients, let it sit there for maybe a day or two in case something blows up. And if nothing blows up, then we can turn it on in our single tenant environments because they have, you know, contractually different SLAs, service level agreements, and, and support contract.

[01:11:14] **Tim:** If you're going to fail, fail in front of the people that don't pay you much.

[01:11:18] **Ben:** Fail in front of the free users if possible.

[01:11:23] **Carol:** So did you guys open the link that Tim put in, because that's what I was laughing at. I did. That image. Why? It was like, I see you like feature flags, so we're going to copy a feature flag to another feature flag.

[01:11:36] **Ben:** Exhibit. Yo dawg. That's awesome.

[01:11:40] **Adam:** Yo

[01:11:40] **Tim:** dawg, I hear you like

[01:11:41] **Ben:** feature flags. I'm going to

[01:11:44] **Carol:** have a feature flag for my feature flag.

[01:11:49] **Adam:** Didn't help it.

[01:11:51] **Tim:** All right. I'm sold. How much does this cost me, Ben? If I call them now and sign up, what's it cost me? Come on. Lunch Darkly

[01:11:57] **Carol:** is expensive, isn't it? It's not cheap. It

[01:12:00] **Adam:** is

[01:12:01] **Ben:** not cheap. It's not cheap. And I, and I really wish they had some sort of a more developer friendly price model, meaning, you know, like a lot of, a lot of SaaS companies will have some sort of like free for open source or free for developers, but then super expensive for everybody else.

[01:12:22] **Ben:** And LaunchDirectly I think only has trials and then you, then you have to

[01:12:26] **Adam:** pay. Yeah. There was a 14 day free

[01:12:28] **Ben:** trial. Similar to Datadog, which we also use. Datadog I think only has a trial. They don't have any sort of free tier, which the thing that bugs me about it the most is that a lot of times I just want to experiment with the code and, and maybe I, maybe they've released a new version of their client and I don't necessarily want to have to.

[01:12:51] **Ben:** Experiment with that new client in my application context. I just want to spin up some sort of, you know, standalone skeleton example, dropping this new client, but I have to either use my. My, uh, API key from work, which feels a little sketchy, or I have to sign up for their 14 day trial and do all of my experimentation in their 14 day trial.

[01:13:11] **Ben:** It feels like there's some sort of missing opportunity there for allowing people to experiment a little bit more freely. Split.

[01:13:20] **Carol:** Gives you a free account. That's pretty cool.

[01:13:23] **Adam:** Up to 10 seats. So we, we never really did say what LaunchDarkly costs. So their starter package is 75 a month, gives you one account to log in and change flags, and they limit you to 1000 monthly active users, client side.

[01:13:36] **Adam:** Now, I guess, does that only matter if you're doing client side flag evaluation?

[01:13:41] **Ben:** Yes. So there's, there's a client side. SDK that you would use in your JavaScript code, and then there's a server side SDK. At least on my team at work, we don't use the client side SDK at all. Essentially. When you load your application, part of the loading of the application is you get a giant configuration object from the server, and that configuration object contains all of the feature flag evaluations for that user, and then, for the most part, that's, that's the mode that that user's using.

[01:14:12] **Ben:** Thank you. And if you turn a feature flag on for them, depending on how things are implemented, sometimes I'd have to refresh the page to get the new feature flag. But the client side SDK is more expensive to use from what I understand. Yeah.

[01:14:28] **Adam:** Yeah. So this is saying 75 a month gets you a thousand monthly active users.

[01:14:34] **Adam:** And if you need more than that, you have to go up to professional, which is 325 a month, and that gets you 10, 000 monthly active client side users. And above that, it's just

[01:14:43] **Ben:** call us. Yeah. And I think on the server side, it runs monthly active users on the server side SDK, I think is like blocks of 25, 000.

[01:14:56] **Ben:** For. It's an incremental cost. It's still expensive, but it's not, I think it's not nearly as expensive as the client side

[01:15:02] **Adam:** one. They don't even list it in their pricing table. No. Yeah, when it says call me, it means it's... If you gotta know, it's too much for you. You can't afford to sit at this table. We need to figure out the number.

[01:15:14] **Adam:** So

[01:15:15] **Carol:** someone wanted to try it, like, without having to pay.

[01:15:18] **Adam:** Yeah. So Carol, you had mentioned that split. io, I don't see prices on their, their page. They have a pricing page, but then it

[01:15:27] **Carol:** doesn't have numbers on it. If you go down, it says free up to 10 seats. If you are having issues with viewing things,

[01:15:34] **Adam:** huh? No, no, no.

[01:15:34] **Adam:** I see free up to 10 seats, but then the other ones don't have numbers

[01:15:37] **Carol:** on them. Oh yeah. I don't know what the other price is, but if someone's wanting to learn and not wanting to have to worry about a 14 day trial and figure it out during that point. You, you don't get stuck with that if you wanted to try it.

[01:15:48] **Adam:** Yeah. I might have to look into this one because like it's, like you said, it's up to 10 seats. It says it's unlimited feature flags and limited environments and limited segments.

[01:15:56] **Carol:** So if you want, that is the metric. It's a key that they use to actually evaluate everything. So it's like a

[01:16:05] **Adam:** user key. It's

[01:16:06] **Carol:** monthly track keys.

[01:16:07] **Adam:** Yeah. Okay.

[01:16:09] **Ben:** Okay. So ideally, if you wrap up your client, some sort of. Abstraction or wrapper, you know, so in our code, we don't have a lot. We don't use the LaunchDarkly client. We have a feature flag service and you pass the feature flag service, some keys, and then internally it happens to use the LaunchDarkly SDK.

[01:16:31] **Ben:** Yes.

[01:16:32] **Adam:** So I saw a presentation about this that I loved. Um, I forget, I wish I could remember what it was called. It had some, you know, cute, funny name, but basically the idea was like, wrap everything. If it's not your code, and I think it was a, pardon the adult humor here, but I think it was like a condom joke, like wrap it up sort of thing, um, and that way if you decide you don't like this library, you could just wrap Take it out and put a different library in and you've got your own API that you write in your wrapper and you just wire it up to the other library and none of your other code has to change.

[01:17:06] **Adam:** You've used your own facade service.

[01:17:08] **Ben:** Totes mcgoats. Ah, I

[01:17:10] **Adam:** wish I could remember with that. Presentation was called. That was an awesome presentation. So we, we talked a little bit about split.io. Um, the other one that I had said that I tried was called Flag Smith. That's flag smith.com. And I abandoned that effort because I was it there, it looks to me, uh, the sense that I get is they're still pretty early days.

[01:17:28] **Adam:** The, as far as I know, they only have a data center over in, um, I think they're on AWS, but they're, so they're using whatever, um, you know, England or Central Europe sort of data center. They don't have anything over in the States yet. So latency is a little bit higher than you would probably prefer, um, for like loading that initial data load or whatever, or request.

[01:17:52] **Adam:** But I will say they have a free tier. Uh, I mean, it's a, it's not as nice as splits. It's one team member, one project, unlimited environments, unlimited feature flags, unlimited identities and segments, third party integrations, A B testing and M V T testing, and yeah, some other stuff I don't know. And 50, 000 requests per month.

[01:18:11] **Adam:** That's on their

[01:18:11] **Carol:** free tier. See, that's good. If someone's trying to learn and just kind of get a product up and see if they can get it working, because I can't get anything done in 14 days. I have too many injects and you know what I have going on that 14 day project. This is something that's gonna be doing on

[01:18:25] **Adam:** the side.

[01:18:26] **Adam:** So when I was doing it, I was trying to use their Java. Integration, their SDK, and I abandoned it because I'm not a Java developer and their Java docs were like, here's how you set it up with Maven. Here's how you set it up with whatever the other one is. Uh, and I don't know those and it just drove me nuts.

[01:18:44] **Adam:** Like, it was like. If you're not going to use one of these two build systems to build your Java app, then you have to go dig up the jars from some random third party website and hope that you have all of them and the right ones. And then, then you have to like unzip them and try to figure out what the structure of the objects are so that you can stand.

[01:19:01] **Adam:** I'm like, just give me good docs and give me the jars. Right? Sounds like fun. Yeah, anyway, sorry, not to totally hate on FlexNips, but like I said, they're early days, hopefully it'll get better. A little

[01:19:12] **Carol:** like side thing, our Ops guys, where Tim, where I used to work at with Tim, they had like a glass baby food jar.

[01:19:19] **Carol:** And it was like in a little glass jar and we had this VIN file or like a jar file that they had to put on servers. So it was like whenever you needed your VIN jar, they would hand you like the glass thing full of like nuts and bolts and they're like, here's your jar. Just go do something with it. I'm like, that's not what we need.

[01:19:37] **Carol:** Let's make this work.

[01:19:39] **Ben:** What's on your shirt? This is the

[01:19:41] **Tim:** Simeon Army. This is, uh, Ryan Anklam gave me this. It's the, uh... Netflix. Yeah, Chaos Monkey.

[01:19:49] **Adam:** T shirts. Oh, nice. So what

[01:19:50] **Carol:** broke today?

[01:19:52] **Adam:** Nothing. I wore it.

[01:19:53] **Tim:** I put it on right before the show because I figured

[01:19:55] **Adam:** everything would be all right.

[01:19:56] **Carol:** That's why your

[01:19:57] **Adam:** mic didn't work.

[01:19:59] **Ben:** Let me check my

[01:19:59] **Adam:** phone. Oh, wait. Yeah, everything's gone down. Yeah, no. It's all

[01:20:03] **Carol:** done. The internet's shut down. I don't know how this is recording.

[01:20:07] **Adam:** So, I feel like I have to, I owe them this much, so I was frustrated with their Java integration, but it looks like they have a bunch of different other things, like you can use it over REST, or they have a Node client SDK, and a bunch of other things, so maybe, like I said, we have a bunch of different microservices, maybe I'll try adding flags for one of our Node apps or something, so.

[01:20:27] **Adam:** Yeah, give it a try. Yep, I might take a look at Split. They have a

[01:20:32] **Carol:** lot of documentation. That's the thing I liked when I was reading through everything and kind of looking at it was it seemed like it seemed very helpful

[01:20:40] **Ben:** when I was thinking about preparing for this show, collecting my thoughts.

[01:20:44] **Carol:** You had to collect your thoughts, this sounds, I mean, this feels like something that you just know

[01:20:48] **Ben:** all the time.

[01:20:49] **Ben:** I think about feature facts all the time, honestly. Um, but what I was thinking about was the fundamental pillars of application, development, observability, stability, all the ilities. Yeah. And I think about, I have my log aggregation. Yep. My metrics. And my feature flags. I was thinking about which ones of these I could give up.

[01:21:13] **Ben:** Like I was hoping to be able to come to this episode and be like, feature flags was the one pillar I couldn't give up. But it's really hard because I feel like logs, metrics, and feature flags. All work together. Yeah, it's a tripod.

[01:21:27] **Tim:** Yeah.

[01:21:27] **Ben:** Stable, right? Yeah. It feels very much like a tripod. Like, I don't think I could get rid of my logs cause then I wouldn't know if errors were happening and I wouldn't know if I should turn features off.

[01:21:37] **Ben:** I feel like I wouldn't want to get rid of my metrics because I wouldn't know if anything performed better or worse when I deploy an experiment. And I can't get rid of feature flags because it's completely revolutionized the way that I do product development. So, I don't know. It allows you to

[01:21:54] **Tim:** react quickly to the other two things, right?

[01:21:57] **Ben:** Yeah, 100%. So, I almost feel like logs, metrics, and feature flags are this holy trinity, if I can offend anybody there, of like getting the applications to work. Properly just added it to RIF trifecta. Maybe that's better to Ben's Bible logs, logs, metrics, and feature flags. Are this, this trifecta of operational readiness and observability in your application?

[01:22:27] **Ben:** I don't think I could give up one of them.

[01:22:31] **Adam:** So I dunno if you guys caught my face there a second ago. I just had this like involuntary cringe. Um, and that was not related to anything any of you said or did, but I just saw our recording thing is up to an hour 40. Oh, wow. I mean, we, we had 10 minutes on the clock before we really started the show, but still, wow.

[01:22:48] **Adam:** Uh, so. We've been chatting a lot.

[01:22:49] **Ben:** Let's end this now. Yeah. I didn't even realize that. Your heart matters. in a hurry,

[01:22:55] **Adam:** then your heart matters. We're done. Alright, uh, well, we've got a bunch of people supporting us on Patreon and we really appreciate their support. If you think we've earned it, please consider supporting us on Patreon.

[01:23:06] **Adam:** You can find us there at patreon.com/WorkingCodePod new this week. We have a new Patreon. Nate, welcome aboard. Thanks for joining the team. Well welcome Nate. We have different support tiers with different perks like a lifetime invite to our discord server, early access to new episodes, and the after show where we keep the mics running for another 10 to 15 minutes after the show ends and Ben is probably going to fall asleep because we're already really late in the evening.

[01:23:27] **Adam:** We have what we call our top tier on Patreon for people who want to pay a little bit extra. And in exchange, they get what we call a sponsored shout out. So this week's sponsored shout out, once again, is going to go to GirlsWhoCode. So, yes, please do send them pizza, send them your support, send them money, send them your time, send them your extra equipment that could be coded on and maybe send them a raspberry pie or an old laptop.

[01:23:52] **Adam:** And, uh, yeah, help them out. Um, to everyone that just listens. Thank you for listening. Don't forget to share the show with a friend because there's no better support than a word of mouth referral. Tell the algorithms to boost our signal by leaving us a review and a rating on iTunes or wherever you get your podcasts.

[01:24:08] **Adam:** Send us your topic suggestions on Twitter or Instagram @WorkingCodePod or leave us a message at 512-253-2633. That's 512-253-CODE. We'll catch you next week and until then, your heart matters.

[01:24:40] **Adam:** Wow. I might not have flubbed anything in the middle there. No, you did good. Yeah, good

[01:24:45] **Carol:** job. We should rush you out at the end every time.

[01:24:49] **Adam:** So. I need to jump in here. All of us, all four of us are often guilty of saying I was just going to say, and then the thing, and that makes it really hard to edit. So you're, you're welcome to say I was just going to say, but then just pause for, you know, a half second before you say the thing, because when, when I'm looking at that waveform, trying to find the spot to cut it.

[01:25:09] **Adam:** So, because if I include that, I was just going to say, then you can tell there was an interruption there or something. Sorry, dad. Do better, Tim.

[01:25:19] **Ben:** So who's going to, Carol's going to say something? I don't

[01:25:22] **Carol:** remember what I just said.

[01:25:26] **Adam:** I'm sorry.
