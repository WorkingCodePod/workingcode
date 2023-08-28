---
title: "019: Makefiles"
description: Today, the crew listens to Adam wax poetically about what makes makefiles so great.
date: 2021-04-21
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/019-makefiles/id1544142288?i=1000518032091"></iframe>

Adam Tuttle first came into contact with **makefiles** (pronounced "make files") back in high school when compiling code. But, at the time, he didn't really understand what they were or how they worked - he was just a consumer. And, after high school, years went by in which he never gave makefiles a second thought. That is, until, one fateful conversation with [Mark Mandel][mark-mandel].

Mark explained that he used makefiles to create aliases for complex Docker commands. This piqued Adam's curiosity; and soon, Adam went down the rabbit hole! Today, he uses makefiles extensively for complex shell commands that he shares across his entire team: building containers, deploying code, generating Pull Requests - and, he's only begun to scratch the surface!

Today, the crew listens to Adam wax poetically about what makes makefiles so great. And, we get to ask him all sort of questions like: can they be used to create `git` aliases? Can this be used with `npx` commands? Is this like npm run scripts? And, why are you still using "boring technology" that was built in the 70s?

This week's sponsored shout-out is **[Wonder Woman Tech][wonder-woman-tech]**, whose mission it is to highlight, celebrate, educate, and amplify Women, BIPOC, and the Underrepresented in Science, Technology, Engineering, the Arts, Math (STEAM), and Innovation.

And finally, don't forget that we are going to have our first book club episode on May 12th for [Clean Code by Robert Martin][clean-code] (aka, "Uncle Bob"). Feel free to read-up and follow along!

### Triumphs &amp; Failures

-  **Adam's Failure** - In what can only be described as _unbridled enthusiasm_ for his team's switch to GitHub Packages, Adam tried to incorporate a few too many changes into what was originally supposed to be the simple swapping of URLs in various `package.json` files. In the end, the migration wound-up including a bunch of test automation and QA deployments which cost his team an additional day in person-hours. But, he did get it done!

-  **Ben's Failure** - He feels like his muse has been on vacation for the last few weeks. Usually his brain is awash with a chaotic symphony of ideas; but, lately, it's just been quiet. These things run in cycles for him; so, he's confident that he'll be back to normal in the near future.

-  **Carol's Triumph** - She just finished her first 2-week rotation on Zendesk duty. Her company rotates all engineers through the Support team twice a year in an effort to build customer empathy and to help educate the engineers on the full landscape of their product-suite. Carol walks away from her rotation with a _deep sense of gratitude_ for her team; and for her customers!

-  **Tim's Triumph and Failure** - After months of mothering his "skunk works" project from ideation and development through to deployment and release, he's suddenly struck with a case of "coder's empty nest syndrome". Without any fires to put-out or customers to consult with, he's not exactly sure what to do with himself. That said, Tim is thrilled to have finally gotten his first _hater_! And while this shade is almost certainly being thrown in jest, it definitely made Tim's week - _his heart is overflowing_!

### Notes &amp; Links

-  [`gh`](https://github.com/cli/cli) - GitHub's command-line interface (CLI).
-  [`npx`](https://docs.npmjs.com/cli/v7/commands/npx) - Run local and remote binaries from the command-line in your Node application context.
-  [npm Run Scripts](https://docs.npmjs.com/cli/v7/commands/npm-run-script) - Run arbitrary scripts from your `package.json` file.
-  [Homebrew](https://brew.sh/) - A popular package manager for Mac and Linux.
-  [`grep`](https://linux.die.net/man/1/grep) - A shell command for searching files and input streams.
-  [`find`](https://linux.die.net/man/1/find) - A shell command for searching for a file within a file tree.
-  [`awk`](https://linux.die.net/man/1/awk) - A shell command for pattern scanning and processing language.
-  [`sed`](https://linux.die.net/man/1/sed) - A shell command for stream editing and text transformation.
-  [`xargs`](https://linux.die.net/man/1/xargs) - A shell command for building other command-line executions using the input stream.

Follow the show! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[clean-code]: https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship-ebook/dp/B001GSTOAM
[mark-mandel]: https://www.compoundtheory.com/
[wonder-woman-tech]: https://wonderwomentech.com/
[working-code]: https://workingcode.dev/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/019-makefiles.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Tim:** I always say I don't know how we'll talk long on a topic. Yeah, I'll say the same thing for Makefiles,

[00:00:04] **Adam:** but you know, it'll probably be two hours long. Probably. I know

[00:00:07] **Ben:** nothing about Makefiles, so I'm, I'm curious.

[00:00:10] **Adam:** This is good, because like, I feel like last week we were kind of diving into something that Ben is really passionate about and just letting his passion carry the show.

[00:00:17] **Adam:** And I feel like, oh, my shoes floor us too. Oh, squirrel. Yeah.

[00:00:43] **Adam:** Well then, here we go. It is show number 19 for April the 21st of 2021, which just so happens to be my birthday. Happy birthday! Thank you, thank you. It'll be the 9th anniversary of my 30th birthday. And on today's show, we're going to, uh, I'm going to fill your ears with my love for Makefiles. Last week, we let Ben preach the good news about Feature Flags.

[00:01:10] **Adam:** So this year, this. So this week I'm going to preach the good news about Makefiles. Oh yeah. Let's see how it goes. Uh, as usual though, first we're going to do our triumphs and fails and looks like it's my turn to go first. So I think it's good that I have a fail this week because I've been on a streak of too many triumphs here.

[00:01:27] **Adam:** Um, I think that it would be easy to view this in a good way, but I'm going to choose to look at it through the lens as like a failure. So I think I've mentioned recently. That my team is in the process of switching from using git urls in our package. json file for our node applications using git urls for private repository access or having private modules.

[00:01:52] **Adam:** Uh, and we're switching from that to using a private, an actual private npm registry. We just so happen to choose github packages, uh, because we are using github for our other, for our code hosting and pull requests and code reviews and all that. So it made sense to use the free tier of their package registry and we're using their free tier of their continuous delivery stuff, GitHub actions, all that.

[00:02:16] **Adam:** So, um, anyway, the, the fail here is that, uh, doing that refactor, moving our stuff from get URLs to, uh, GitHub package registry. I let myself get excited. And so we had, we have many microservices and, uh, like 20, somewhere between 20 and 24 of them. And in the process of doing all those conversions, I got excited about how easy it was going to be to do the GitHub actions for them as well to do like tests automatically for pull requests and for automatic deployment to our QA environments and stuff.

[00:02:49] **Adam:** And so this refactoring that was supposed to be just convert Git URLs to the private package registry. turned into that plus a bunch of automate test automation and, uh, QA deployments and all that. And, you know, it's fine. It all worked out in the end, but what... It was originally planned and scoped for a single day for three people to deploy all these services and, and go slow and be methodical and test everything.

[00:03:19] **Adam:** Became that single full day for three people plus an extra half day for two of us again the following day because we just couldn't finish in time with all the changes that... were made unnecessarily. Should have been a separate pull request at a different time. I let the excitement get the best of me, and so I did too much.

[00:03:37] **Adam:** Yeah, but you only went over by

[00:03:38] **Ben:** half a day. That's not so bad.

[00:03:40] **Adam:** Half a day for two people. So it was an extra full day, full person day. You're an overachiever. Yeah. No, I mean, like I said, it would be easy to see it as a positive, uh, you know, good stuff got done. Right. But I, I let my excitement get the best of me and I did more than I was supposed to do.

[00:03:57] **Adam:** We've all done it. The pull request though was pretty massive. I mean, when you change that many package JSONs, especially when you're changing modules that haven't been updated in a long time because they're stable. We went from version one to version two of the package lock. json, which I don't know if you know anything about, but there's a lot more detail in version two.

[00:04:18] **Adam:** And so Ben would have like jumped outside of his skin if he saw this pull request. It was like plus 300 lines of code. Or no, I'm sorry. It was like minus 300 lines of code plus like 6,000 and Whoa,

[00:04:31] **Carol:** I bleach

[00:04:31] **Adam:** please. Yeah. No, most of that was stuff you won't, wouldn't have to look at a package lock. JSON can be, for the most part, ignored.

[00:04:39] **Adam:** Yeah, I'm, I'm always

[00:04:40] **Ben:** shocked at how big the pack, uh, package lock file, yeah. Changes are, you go to install one library and like 17. Things in your lockfile change. You're like, Hmm, yeah, I feel like I made a mistake, but I can't

[00:04:54] **Adam:** know that. Yeah. I think the only mistake in that case is like, it's so hard to look at the module that you want to use and make sure it's not going crazy with its dependencies and that its dependencies aren't going crazy with their dependencies and like all the way down the tree.

[00:05:09] **Adam:** I think the only thing you really can do to try to prevent that explosion of modules is to install it and see what changes. You know, you install one simple thing and you get 300 new packages. Hmm, maybe I'll find something else. So that's me, Tim, what do you got this week? Well, I've got a

[00:05:24] **Tim:** fail and a triumph.

[00:05:26] **Tim:** Let's do the fail first.

[00:05:27] **Adam:** Okay.

[00:05:28] **Tim:** So, you know, I've been working on this project, you know, like my, my skunk works project and it's finally, it's in production and I don't know what to do with myself. You know, you go through the process, you come up with an idea, you prototype it, you're so in love with it and so exciting and you're like, okay, you decide it's going to be a real product.

[00:05:50] **Tim:** And so you're excited about that. And initially you think, oh, it's, it's the prototype is just so close to being done. Just a few, few tweaks. Right. And then like nine months later, you're like, oh, there's a whole lot more we had to do to it. Now it's live. And it's like, I just don't know what to do with myself.

[00:06:05] **Tim:** I sit there. Looking at my emails going, all right, what's next? I don't have any burning

[00:06:11] **Adam:** fire to work on right now, so. It sounds like you have Coder's Empty Nest Syndrome. Yeah, it's like, yeah, the baby's left the house. I don't. It has to be. Yeah, so

[00:06:20] **Tim:** it's like, I gotta, I gotta start stirring up. I've got another project that I'm hopping on, but I'm not going to be the main developer on it.

[00:06:26] **Tim:** Um, so that it's always hard for me when I'm playing second fiddle on a, on a, on a project. So maybe I gotta find another

[00:06:34] **Adam:** Skunkworks to get started.

[00:06:35] **Carol:** Are you capturing any analytics on that? That you could go look at to see the usage and stuff? Is it being used and

[00:06:41] **Adam:** being adopted? Yeah,

[00:06:43] **Tim:** that's what I was doing today.

[00:06:43] **Tim:** I was building everything to capture the analytics and do that sort of stuff. Uh, building all that out, but like, there's nothing, they're not, it's not being fully launched yet. So it's not really being utilized fully. So next week I'll be knee deep and I shouldn't

[00:06:58] **Adam:** be looking at it, but I will. I know I will.

[00:07:00] **Adam:** You can't stop yourself. No,

[00:07:02] **Carol:** I can't stop myself. I had all that stuff going on a few weeks back, um, with that big project I was on. So I just got all of the analytics stuff up. So I've been watching it for four days now, three days, three and a half days. And I'm trying to figure out why one button.

[00:07:23] **Carol:** And I'm like, what do they not like about this section?

[00:07:27] **Adam:** That's funny. It's the wrong shade of blue. I was like, why aren't they clicking it? Yeah. Yeah. I

[00:07:33] **Tim:** was doing load testing today, so I threw a whole bunch of requests just to see how the production environment will handle lots of requests. And it, it did okay.

[00:07:41] **Tim:** Some, some things that it talks to that I have no control over didn't do so well, but yeah. The actual

[00:07:47] **Adam:** app I wrote is great. Good. Your

[00:07:48] **Carol:** code works. Someone else's

[00:07:50] **Adam:** doesn't. Somebody else's problem.

[00:07:52] **Tim:** You using Gatling? Actually, no, cause it's not a Gatling. I use that for Scala projects. This, I just kind of built my own.

[00:07:59] **Tim:** This is a Lucy project. I just built my own, um, request using threads to just constantly hit the server with requests. Nice. Running it in threads. But our triumph since the beginning of this podcast. I've wanted haters. You know I've wanted haters, guys. That's how you know

[00:08:19] **Adam:** you made it. When you got haters,

[00:08:23] **Tim:** you know you made it.

[00:08:24] **Tim:** We finally have one. Adam Cameron tweeted the other day that he hates our podcast and this warms my heart. Particularly me, Kim Cunningham, because I'm the worst.

[00:08:37] **Adam:** I didn't even see the tweet!

[00:08:39] **Tim:** My heart is so full, it's just

[00:08:42] **Adam:** overflowing right now. I have to go find the tweet. We'll put it in the show notes.

[00:08:46] **Adam:** Good, because I, uh, I missed it.

[00:08:48] **Ben:** Was it in response to anything in particular? I think

[00:08:51] **Tim:** he listened to the podcast where I was complaining we

[00:08:53] **Adam:** didn't have any haters yet. So all of them? Yeah,

[00:08:58] **Tim:** yeah, pretty much. So he, he, he finally took the, I think he was just being nice, even though he's saying he's hating

[00:09:05] **Adam:** us, so.

[00:09:06] **Adam:** Yeah, I think there was tongue firmly planted in cheek for that one. Your heart matters, Adam. Even if it's hating, it's, your heart matters. That's me. How about you, Carol? Um,

[00:09:19] **Carol:** I'm going to go with the Triumph. So I have my first rotation on Zendesk. So if you don't know what Zendesk is, it's basically your customer support for your application.

[00:09:29] **Carol:** So whenever users are using it and there's a problem, it's where the bugs come to to be fixed. So it's the triage, it's the Research the weird things and just figure out what's going on and what's happening. And we do a two week rotation on it and I am still very, um, green on a lot of the application overall.

[00:09:50] **Carol:** I know kind of the core of what we're doing and I know the pieces I've been in, but when we're talking about all of the other stuff that we touch outside of it, I don't have a clue. So when these tickets are coming in, they're like, Oh, this data isn't working. I'm like, that's not even our data. So then I'm in Slack going, where does this data come from?

[00:10:08] **Carol:** And my team is amazing because they're going, Oh, you have to send this person, this thing. And that's where all of that happens at. So not only did I survive, I also learned a lot about the things that our application actually communicates with that I wouldn't have been exposed to just by working through our backlog or working through current development that we have going on.

[00:10:27] **Carol:** So. I survived it, I didn't cry, and I learned. Yay! Nice. Two weeks of Zendesk done.

[00:10:33] **Adam:** Very cool. Do you feel like that that's a good way to, like, onboard you to the rest of the application? Give you some experience and some awareness of what's going on out there? Or is it a little too overwhelming?

[00:10:44] **Carol:** I think at this point, it's good.

[00:10:45] **Carol:** So, I've been there six, no, four, five, I don't know, a couple months. I can't tell you when I got there. It was like October, I think. So, you know, I've been there a few months and I've learned a lot. So, I think it's a good point. If they would have done this right out the bat, I would have just been overwhelmed and been terrified to touch anything because everything touches something else and it wouldn't have been a good situation.

[00:11:07] **Carol:** But where I'm at now, it's a good thing. It's a good time for it. And I think with the size of our team, we only do two rotations a year.

[00:11:15] **Ben:** Does the support team have a knowledge base or some sort of kind of copy and paste? Frequently asked questions sort of a thing?

[00:11:24] **Carol:** Um, we just go look at the Zendesk tasks that were open, just basically pull them all up in JIRA.

[00:11:31] **Carol:** And we kind of just go backwards and go, okay, has this been repetitive? The other thing they do is if it is repetitive, then a ticket goes in to actually fix the root. So even if you don't fix the root now, the root is in the backlog now to be fixed. So the core problem gets addressed.

[00:11:44] **Adam:** Thanks. Cool, cool, cool.

[00:11:49] **Adam:** So I think you, Ben, what you got?

[00:11:52] **Ben:** I'm going to go mostly fail, but then a small triumph just to make myself feel better. But my general failure is that I sort of just feel like my muse has been on vacation the last couple of weeks. I just haven't, uh, I feel like I've been missing some pep in my step and, uh, my brain has been emptier than usual.

[00:12:12] **Ben:** Like a lot of times I'll just have all kinds of random thoughts and ideas swimming around in my head. And, uh, my head's just been very quiet lately, which is not, uh, I don't know, I don't know what direction to go in when that happens. So I'll come out of it, these things run in cycles for me, so I will be, uh, noisy brained soon enough, I'm sure.

[00:12:34] **Carol:** Uh. Do you think maybe it's, uh, coming down some? Because you were pretty kind of hectic the last week, right? With working over and having more stuff going on, so it's just recovery?

[00:12:46] **Ben:** I think it has to do with work stress, so I think I've been very busy at work and maybe a little too busy. Sometimes when I have more than I can handle at work, my brain sort of shuts down because it doesn't know how to process the information very effectively.

[00:13:01] **Ben:** Um, and I think it, like, it quiets itself so that I don't stress out so much about all the things that I could be doing that I'm not doing right now. I wish I had your brain. I don't know. It's kind of like, uh, sticking your head in the sand a little bit, but, uh, so I will say that I do have a small triumph, which is that, um, a couple of the people on my team have been doing some time on other teams at the company.

[00:13:29] **Ben:** And, uh, they're all feeling the pain of not having those quick pull request reviews. Mm hmm. We have on our team. Uh, I've had several people now say that some of their PRs will sit open for more than 24 hours. And they compare that to our team, where just as an experiment, one of the guys who's been doing time on other team, opened up a PR, dropped it in our Slack channel, didn't even mention anybody, like didn't adhere to the channel or anything.

[00:13:55] **Ben:** And his PR just coincidentally got reviewed within two minutes. Wow. And he was just like, Oh, this is, this is crazy. How did these other teams take forever? So I felt good about that. I feel like the culture on my team is

[00:14:07] **Adam:** intense. Cool. So everybody's ready to have me brain dump, make files into your heads now, right?

[00:14:13] **Adam:** Do it. Isn't there a command you can run? Like, make people know, make files. Yeah. So I mentioned to you guys before we got started recording that I had, I took some time to write down some notes and I have a lot of things to say, but I really want the conversation to be organic and go wherever it wants to go.

[00:14:33] **Adam:** So I think where I want to start is, I think it makes some sense to just kind of paint the picture a little bit of like, where did make come from and why is it in my life? Um, and then we can kind of go wherever from there. So, um, my first personal exposure to make was in high school, um, which as we've, uh, kind of, I guess alluded to was a long time ago, more than 20 years ago.

[00:15:01] **Adam:** Um, and so I was doing, uh, I guess it was a computer science class and we were doing C programming, um, for those that don't know, C was the precursor to C Which I think most people have probably heard of, um, and I see sharp if you're new. net. Oh, there you go. Yeah. The more modern, um, and the, I don't know if it was just.

[00:15:27] **Adam:** poorly explained or if it was too over my head at the time to stick and, and, you know, stick with me all these years. But I know we used Makefiles at the time to compile our code, but I, after I was out of high school, I just sort of completely forgot about them. Like I, I remember that they exist, but like never really had any need for them after high school.

[00:15:51] **Adam:** In college, I got an internship doing, uh, like, desktop programming stuff, mainframe programming, and then I moved on to web and Visual Basic stuff, and so like, just, there was kind of no use for Makefiles in that world, and this is, you know, early to mid 2000s. Um, and so, uh, it kind of just fell by the wayside.

[00:16:10] **Adam:** And then a few years ago, at a conference, one of my friends, Mark Mandel, um, was giving a presentation on some Docker stuff. And I was talking to him after his presentation, and he just kind of casually threw out there that he uses MIG files to Um, sort of save, effectively save aliases for docker commands because I was talking about how confusing it can be to try and remember all of the nuance of the various docker commands, docker run versus docker build versus docker push and the difference between images and containers and blah, blah, blah, all that stuff.

[00:16:45] **Adam:** And he was telling me about, you know, okay, well, you figure it out once and then you write it in your makefile and you have like an alias. I just remember, like, make up spins up my dev environment, make down turns it off, all that, um, and A light bulb went on in my head. I was like, oh, okay. And then so, and I think I've mentioned to you guys before, we use Makefiles in my team, and we have now for a couple of years after I had that conversation with Mark, to effectively share, um, shell script simplifications, right?

[00:17:16] **Adam:** So anything that you might do on the command line, That might be sort of a complex, long, if you want to pipe together a bunch of commands to do something or whatever, even if it's just a single command, but it's complex, like a Docker something or other, um, then, uh, we have a makefile in the root of our project and, and it's useful.

[00:17:37] **Adam:** So you can tell it to like make, tests if you wanted to run the tests or you know make up make down that sort of thing make deploy make publish to publish without running a deploy that sort of thing um and so i've been just even that alone has made me personally like sort of re fall in love with makefiles over the last let's say three to five years and then In the last, I don't even know, like six weeks, I learned there's just so much more to Makefiles.

[00:18:08] **Adam:** There's, I've been able to, I've been using them for a few years now and I started to have these ideas of ways that my Makefiles could be even better if something was possible. And when you think about an idea long enough and you start to ask the right questions, you start to Google the right things, ask the right people the right questions with the right words, you start to learn like, Oh, well, it can kind of do that, that sort of thing.

[00:18:32] **Adam:** So there's a lot of like, Little tips and tricks and sort of, in my mind, I call them hacks. Things like, for example, we can get to this later, but makefiles don't technically have inheritance, but you can kind of get something that feels a little bit like inheritance. So that you can have a shared sort of base makefile with a lot of your reusable logic in it, and then you can have a like a per project makefile that includes that and overwrites the bits that need to be overwritten, but then it inherits a lot of that shared functionality.

[00:19:05] **Adam:** So, can

[00:19:05] **Ben:** I, just to interrupt you for a second, what's a makefile? Right. Yeah, yeah. I feel like I still don't, I sort of understand where you're going, but I, I feel like, can we stop and just do a definition?

[00:19:19] **Adam:** Absolutely. Um, so let me, let me take a step sort of even further back from that. Um, I, I mentioned that my first exposure was through compiling code for C programs.

[00:19:35] **Adam:** And I, this is where I'm a little bit out of my depth. I don't know if make was created for C programming or if maybe it predates C. I'm not sure, but like I said, that was my first exposure. It was particularly useful for C programming because the, um, to compile your program was a multi step process, right?

[00:19:54] **Adam:** So you have to compile the code into objects and then you link those objects together into an executable. And those were two separate commands. And, um, one of the, like, amazing things about Makefiles is it has dependency resolution in it. Um, and it's, it's a little bit, um, old school because it is based on the file system.

[00:20:16] **Adam:** So if you're more familiar with like, again, this is already a little outdated, but more recent in the timeline, Grunt versus Gulp, right? So Grunt, you can do tons of cool stuff, but pretty much every individual process would like read something from disk, do something interesting to it, and then write it back out to disk.

[00:20:35] **Adam:** And then the next step would read that file from disk, do something interesting to it, and write it back out to disk. Whereas Gulp was read the file, modify it, and pass it in memory to the next step. And that would modify and pass it in memory to the next step. So, um, Makefiles, like I said, are a little bit more old school, and everything is sort of file system based.

[00:20:53] **Adam:** Or that's the intention. So with your C program, you would have your source code file, and you'd have like some header files. And you say, okay, compile this file or this, this program, whatever. Um, and the output of that is a o file, object. Um, and then the, the next step is to take all of your objects and link them together into your final executable.

[00:21:19] **Adam:** And in order to do that second step, make your executable from your objects, the object files have to exist, which requires that first step of compiling, right? And so in your makefile, you can say, you can have like, um, let's just call, let's call them our targets. And you can kind of think of targets and make files as like individual scripts, right?

[00:21:40] **Adam:** So you've got a make script that is compile and another one that's link. And you can call, like, for example, you can say make link. And if those dot object files are missing, because you've defined them as dependencies, to be able to run make link, you have to have, you know, foo. o and bar. o. And if either one of those two files is missing, Then it will go, okay, well how do I create that?

[00:22:02] **Adam:** And you have another script called foo. o and it says, okay, well, foo. o file is missing. I need to create that. So I'm going to go and run the script called foo. o and that script runs and Whatever needs to happen, happens. And at the end, it outputs a file called foo. o. And then if the same is true for bar.

[00:22:22] **Adam:** o, then it runs that script. Or if bar. o already exists in the file system, then it skips that step. And then once the dependencies are resolved, then it will run the script you asked for. And that can go however many layers down you need. If you need to go 10, 000 layers deep, you can go 10, 000 layers deep.

[00:22:38] **Adam:** You're probably going to get a buffer overflow or a stack overflow or something, but, um, you know, theoretically infinite. And just some

[00:22:48] **Tim:** history on Makefiles. So, they're old.

[00:22:51] **Adam:** I mean, they came out in 19 Older than Tim. Yeah. Well, actually, no, they're not.

[00:22:56] **Tim:** 1976, they came out, uh, and it was part of Unix. So, it was, yeah, it was basically to, when you compile code, to, to check dependencies and see what needs to be recompiled.

[00:23:08] **Tim:** Right. So, you know, if you're not coming from a world of compiled code, something like, like a Makefile is probably not. Something you would automatically think of, even though it can be used for more than just compiling code, it could almost, like, uh, Adam was saying, can be used to, to run any sort of disparate commands that you want in, in a fashion.

[00:23:28] **Adam:** Exactly. Almost, almost like a very powerful macro language, almost. Yeah, it was created for the purpose of, again, I'm not 100% sure on this, but I think it was created for the purpose of managing compilation, complex compilation, where you have, you know, maybe, maybe for a simple program, it feels unnecessary, but when you've got.

[00:23:47] **Adam:** You know, dozens of executables you need to create and all of them have various headers and whatever like managing that and making sure that when you pass off this project to somebody else, they're going to have everything they need to compile it all is going to work. Um, but at the end of the day, all it is, is a sort of template that when combined with the executable, the program called Make, um, It allows you to have effectively arbitrary command line scripts that have built in dependency resolution.

[00:24:22] **Adam:** Um, basically think of it as you could write a, a little command line app in whatever language that you're comfortable with, right? You could write command line apps and Node, or Ruby or Pearl or whatever. Um, and, and, you know, pipe them together. If you're familiar with the Unix command piping. thing. Um, but what make gives you that you don't get if you're just writing your own little scripts together is there's a lot of boilerplate, boilerplate in the, in the process of creating a command line script, right?

[00:24:56] **Adam:** You have to tell it how to get the arguments out of the, uh, out of the command. And, um, if you want to have multiple scripts, it basically, it kind of gives you a way to create, uh, a complex and, and interrelated processes. And, and take out the, the part you wouldn't want to think about, right? I want to write the process of how my, my application needs to be handled or changed or compiled or whatever.

[00:25:24] **Adam:** I don't want to have to write a bunch of code that is, this is how you do command line stuff, right? Does that make sense? Yeah. I

[00:25:32] **Ben:** guess maybe one of the things I'm struggling with is the difference between a, a bash script Okay. And, and make. So, for example, questions that popped in my mind. Do I need to have a particular shell installed to run make, like Bash or SH?

[00:25:49] **Ben:** Or, or is make like a completely self contained thing?

[00:25:53] **Adam:** Right. So, make is completely self contained. It'll run on every shell I've ever tried. Um, I run it on Zshell right now, but I run it on Bash and, and Cshell. And... Like, can I,

[00:26:06] **Ben:** in a make file, could I run echo hello world or...

[00:26:11] **Adam:** Yes, as a matter of fact, um, so a makefile when you get down into the contents of it, basically, um, you define different targets in it.

[00:26:19] **Adam:** And the way that you define it is you have like name of target. So call it Ben, right? Ben colon. And then if you want any dependencies after that, you little space after your colon and write down the file name that okay, before Ben can run, there has to be a working code dot podcast file, right? And if that file doesn't exist, Uh, in the working directory because so you if that let's just say that workingcode.

[00:26:43] **Adam:** podcast file has to be in a folder called lib if so if you write lib/workingcodepodcast if that doesn't exist then it goes and finds a target of that name that whole file name and runs that that's what so that's how it does dependency resolution and then below that So, below your target, you can, uh, basically just run a bunch of other commands.

[00:27:07] **Adam:** So, if you indent, and I'm 90% sure you have to do a tab, I don't, it'll probably work with spaces, but. Thank you. Tab, as we previously discussed on, I guess it was on the after show, tabs are just better, superior in all ways. So, uh, you go down to the next line, you hit tab, and once you hit tab, you are effectively in the shell, right?

[00:27:30] **Adam:** So there's makefile commands, and I don't want to get into those because those are complex, and those are one of those things that I've only recently learned. In the last like six weeks that are sort of that higher level like you need to spend some time doing basic makefile stuff to really grok how makefiles themselves are intended to work.

[00:27:51] **Adam:** And then when you start to get into the more complex needs and desires for things that your makefile would do, that's when you start doing other, uh, other commands and variables and stuff. But basically, if it's all the way against the left edge of the file, it's a make command or target. And then if you indent, you can do echo, or find, or, um, grep, or whatever, you know, like regular, you're basically on the shell at that point.

[00:28:15] **Adam:** Interesting. So, you can string together commands and like pipe them, just like you would if you were typing in the shell, um, and you can run multiple commands in a single target. So,

[00:28:30] **Ben:** just going back to the thing that Mark Mandel was talking about with, I don't want to say aliasing, I don't, I don't know if aliasing is the right term, but I know I've heard people talk about the complexity of git commands and they will in their bash profile create aliases like GCM for git commit with message sort of thing.

[00:28:52] **Carol:** Exactly what I'm thinking.

[00:28:54] **Ben:** Yeah. So, so can you, I mean, instead of having a bash profile for GCM, could you do something like make GCM and. build the same kind

[00:29:03] **Adam:** of aliasing? So you can, absolutely. Um, I'm 90% sure that you can write a make target that you pass arguments into on the command line. So you could do like make GCM and then maybe quote your message for the the git commit message.

[00:29:20] **Ben:** Oh, so when you call make, does it typically not

[00:29:23] **Adam:** take arguments? In the, in my usage, I haven't really found a need for that. There's like one sort of advanced thing that we can talk about later that where I have sent in a few arguments, but, um, in general, no. Like you, you you call

[00:29:45] **Adam:** Um, Docker build, right? And it knows, okay, there is a file named Dockerfile. Capital D, all one word, Dockerfile, no extension. Make is similar. You call make, and it assumes that there is... a file called capital M makefile, all one word, no extension. Right? Uh, and it will run that. And just like Docker, you can do like dash T or whatever to sell it.

[00:30:09] **Adam:** Okay, no, we'll actually My company is special and we're doing, you know, Dockerfile dot, or dot whatever, you know, you can change the file name. Same thing is true for, for make. I don't know what the, the argument is, but you can change the file. Um, so you call make and then you give it, it's like make space and then the name of the target that you want to run in the make file.

[00:30:29] **Adam:** And, and like I said, I think that you can pass arguments in after that, but I'm not positive.

[00:30:36] **Ben:** It's interesting, the dependency resolution actually reminds me a little bit of the way that the Docker Compose files work, I think, where you can say like, here's service A, and service A has a dependency on B and C, so when you do Docker

[00:30:49] **Adam:** Compose up.

[00:30:51] **Adam:** Yeah, I mean, so Compose is interesting because not only does it do that, but it can link them together, right? So like by hostname, you can, you can just have like, Your Redis container comes up and you say that the container name is Redis. And so in your other containers that are linked together, you don't have to know a host name or anything like that.

[00:31:08] **Adam:** You just say, talk to, the host name is just Redis, right? So it, it connects to it over that shared connection by that. Um, however, Docker Compose, everything has to be a Docker container, right? So if you have other things that you want to do, so, so Compose isn't going to solve everything that you can do with a MIG file.

[00:31:28] **Adam:** Let's go back a step here. You guys compared this to putting git aliases in your bash profile. I also put a bunch of aliases in my bash profile, especially for git, but also for lots of other things. And the difference for me, the way I'm thinking about makefiles versus my personal command line aliases.

[00:31:51] **Adam:** For me, those command line aliases are very personal. You know, I, I prefer, um, I have, I have CO, uh, alias to, uh, get checkout, right? So I can do CO branch name, right? Um, and I have like, uh, I guess this isn't, see, there's, there's lots of different places things can go. I have, I think it's in my Git config somewhere, wherever you put in, you can do like mine is, but I have, uh, so it's get space ST, which for me is the same thing as doing get status dash S B.

[00:32:29] **Adam:** I believe it is. Um, I'm thinking get status. That's why it's ST, but it's get status dash SB, which is just, it's a short version and it's like color coded and it's compact and it shows you. Only what you need to know when you're thinking git status, not... It is in git config,

[00:32:44] **Carol:** by the way. Okay. You're

[00:32:44] **Adam:** accurate.

[00:32:45] **Adam:** Yeah, thank you. Um, so, like I was saying, that's very personal. I might prefer git st, you might prefer something else. Um, I have like git lg, which is like the way that I like to view the git log on the command line. That sort of thing. Whereas the makefile, um, the way that my team uses it, we have it checked into our repo.

[00:33:06] **Adam:** And so those are shared across the entire team. And it's a great way to standardize on something, right? So you hire a new developer, and you bring them up. And in their onboarding documentation, it says, Okay, here's how you spin up our local dev development environment. You clone these repos. Um, or something we're moving towards is actually a like you clone one repo and in it is a makefile that will go and clone a bunch of other repos for you with the correct folder names so that they're relative to each other because we have some things that like reach outside of themselves and go around the corner to the other thing and um, so it it's helpful sometimes especially with our docker compose it kind of does that Reaching all over the place thing.

[00:33:47] **Adam:** Um, but, uh, so it's helpful to have them have the same folder names and be relative to each other that way. And so that's a direction that we're heading. So we have that make file and it's a, it's a good way to have sort of standard commands that the team is all familiar with and can, we can just say, Oh yeah, you, you know, you run make rebuild and it will.

[00:34:09] **Adam:** Clean all of your Docker containers out and start from scratch and rebuild everything. And we all sort of know that and can help remember and remind each other when something's going wrong. Oh yeah, when that happens you need to run make rebuild sort of thing.

[00:34:21] **Ben:** Do you have a like a make scripts folder where you have kind of like set aside bash scripts that then the make script can call or is everything embedded right in the make file?

[00:34:33] **Adam:** In my usage. Pretty much everything is right in the MIG file. Um, so yeah, that's a good point though. So your, your MIG file can call anything, right? Like we said, it's, it is on the command line. Um, and so, one thing that I was experimenting with yesterday was, um, if you're familiar with NPX, which is like, NPM run a thing without actually permanently installing it.

[00:34:59] **Adam:** Um, so I was, there, when you do an AWS Lambda update function when you want to like publish new code to Lambda over the CLI and like upload a zip file of source code. Um, there, what happens with the, the CLI tool, the response comes back and it is an interactive response. Like it prints JSON on the screen and you have to hit the Q button on your keyboard to make that go away.

[00:35:24] **Adam:** Right. Which is, Super annoying, right? It's just a JSON packet. Like, console, uh, you know, print that to standard out and exit or something. Like, why are you going to make me press the Q button? So what I did was I figured out how to, um, I wrote a very, it's like a two or three line node script that It looks for some JSON in a certain argument number on the process.

[00:35:49] **Adam:** argv, the list of arguments that are coming into the app. And it parses that JSON, and one of the values in it is, was the deploy successful or not. And so, I wrote this little package, and I published it up to our private package registry. And the hope was that you could just do like npx, uh, and I forget what the exact name was, basically like lambda update parse or something like that, right?

[00:36:16] **Adam:** And then, then you give it the command after that to do the AWS publish. And, um, and they, the intent was you no longer have to press the Q button and it's going to automatically print was the deploy successful or not, right? It parses that JSON and just spits out that one little line that you don't care about and also takes away the interactivity.

[00:36:37] **Adam:** Um, and so I was doing that. So I had a makefile. It was running NPX, you know, my command. And then the AWS command after that, and trying to parse that. Didn't ultimately work out, I think, probably because, and this is getting a little, I guess, technically off topic, but hey, it's our show, we can go where we want.

[00:36:57] **Adam:** Um, we, like I've mentioned before, we're kind of moving heavily towards GitHub Actions because it's there and it's free. The free tier, oh my goodness, is so generous. of their package repo and GitHub Actions. And there's another one. I think they have like a container registry. We have been like just going whole hog on this.

[00:37:20] **Adam:** You can set a spending limit, right? So I was like, okay, well, don't let me spend more than 5 a month and we'll see how soon we hit that. And even before that, there's like you get a certain amount for free and it's like 30, 000 or 3, 000 minutes a month of GitHub Actions usage, which is like their basically their Travis CI type service.

[00:37:41] **Adam:** And we have barely even begun to scratch the surface of what we can use for free in a month. 55 minutes in a month or something like that out of 3, 000. So we're not at all worried about paying for it. I love GitHub Actions and I'm not afraid to say it. In the,

[00:38:01] **Carol:** uh, in the words of Ben, you have feelings. I do.

[00:38:04] **Carol:** I

[00:38:04] **Adam:** do. I have some feelings about it. The, the reason that I bring that up, though, is because, a little frustratingly, so GitHub Actions, the node package that they provide by default is the LTS version, which makes sense. I'm not complaining about that. But that so that's node 14 and node 14 comes with npm version 6 whatever the latest release of in the 6th line of versions is it's not going to go it'll do 6.

[00:38:34] **Adam:** 14 or whatever but it's not going to go up to 7 um and there's a bug I think in it's either in npm or in npx where if you're using a private scoped package for like in npx. So ours was not just like npx command but it was actually npx @AlumnIQ/ my private command and it won't it's like not noticing the file that's supposed to tell it where it can find that command and it's saying oh your your command that you're trying to find isn't available in the package registry 404.

[00:39:05] **Adam:** Because it's looking at the public registry, not the one where it actually exists, even though I've provided information that tells it where to look. And, and it works for me locally. So I was like, I spent an hour or so, whatever, the other day, and I figured out that if I make GitHub Actions run with, um, Node 15, which is their current, like, latest release, whatever, um, then it has NPM 7.

[00:39:26] **Adam:** And I think that that is working further. Like, it gets further down the line. I'm still getting some bugs, but that's where I had to end my day the other day, and that's where I left it. And I kind of forgot why we went down that, uh, that rabbit hole. Now, for our

[00:39:42] **Tim:** Scala stack, we don't use makefiles. We use something called SBT, Scala Build Tool.

[00:39:49] **Tim:** Okay. It's very similar to make file though. So it it, you can import dependencies, you can, you know, set variables in it and it will basically compile your SS Scala code. If you want to use a specific version of something, you can specify whatever version you want and it'll only, you know, if we're using scallop two point 11.8, you'll go grab that and then make sure that the dependencies that you're using kind of match that.

[00:40:16] **Tim:** Um, The older version that this, they've updated this, uh, in recent years, but they're, they had, you were talking about how, uh, make files, you know, if you have a tab, right, well, they had spaces, so it was very white space dependent, which was annoying. But they've since fixed that, uh, but sort of the same thing.

[00:40:36] **Tim:** So anytime we're, we're compiling a new, uh, Scala project, we compile it, we run SBT, it goes and grabs everything. Make sure if you want to get the most recent, recent versions of all your dependencies and see how it works. Um, sometimes you don't necessarily want the most recent version, but so you can specify all that.

[00:40:57] **Tim:** Uh, we don't deploy with it though. I don't know if, if make does like can help with deployments. What we deploy with is with, um, with. With Fabric files, with Python, it says that you can do remote execution over SSH to a remote server, so it can run things remotely, so we compile it, and then the Fab file will basically zip everything, zip the code up, um, move it via SSH to the target server, you know, if it's development or your deployment, put it up on the server, Uncompile it and then run, run a, not uncompile it, but unzip it and put, uh, you know, do whatever it needs to on, on the shell remotely, get it, get it, get it, um, get it on to the new server and then restart services and stuff like that.

[00:41:49] **Adam:** That's how we use it. Okay. So, gosh, it's going to be tough for me to remember all these things, but different things that you said triggered different things that I wanted to talk about. Um, so you had said you brought up the tabs versus spaces thing, which reminded me that I wanted to say, like, you know, all of the stuff that I've discussed so far, for the most part, you could say, you could make the argument, well, if I'm using GitHub Actions, why not just put all the things that I want to do into a GitHub Action workflow file?

[00:42:18] **Adam:** Why put it in the makefile? And for me, there's two reasons there. One, um, GitHub Actions are configured using YAML, which the way that I think of YAML is it's like JSON, but worse.

[00:42:34] **Adam:** Uh, which is, you know, it's white space, uh, has significance and it's spaces and whatever. I'm just not a fan of YAML. Uh, the other thing about the Why we choose to use makefiles instead of just putting everything in the GitHub actions is to give ourselves that insurance policy. So our, our GitHub actions are kind of actually, for the most part, a repeated boilerplate.

[00:42:56] **Adam:** So it, let's see, it has to specify the operating system. So we're on Ubuntu, whatever. Um, it has to check out the code. Um, we send some information into our Discord to, uh, you know, let us know the builds are running or whatever, or if the tests failed, we want to know about that, that sort of thing. And then, um, if it's going to be publishing to AWS, then there's a, a step you can include that uses environment variables to log you into ECR so you can publish a container, that sort of thing.

[00:43:25] **Adam:** The majority of the actual, like, work that's going to go on For us is a single runs like make deploy sort of thing. Um, and the reason that we do that is so that on the off chance that GitHub Actions is down or all of GitHub is down or whatever, we are not prevented from being able to deploy and we're not forced to like go through a YAML file and go, okay, what was the next command I need to run manually?

[00:43:49] **Adam:** In that situation, we can just go, okay, well, I'm going to go to the root of my repository. I'm going to type make deploy, and it's going to do it. And I can do that because I have, you know, the right permissions in my AWS CLI. Choose not to for, you know, compliance reasons. But that option is open to us if we need it.

[00:44:07] **Adam:** Something

[00:44:08] **Ben:** Tim said triggered a thought in my head, which is about dependencies. Yeah. Now you've talked about dependencies in terms of make targets. I think about containerization and one of the value adds of containerization is that it's baked in dependencies, meaning if I want to spin up a container that's a particular build of Linux and has like the right version of image magic and all its own apt get.

[00:44:35] **Ben:** For proper versions of various dependencies, that's all self contained. How do you deal with something where makefile depends on a bash script and that script has to be installed? Do you, are you running, I guess, so I guess question one is. Are you running the make files on your host computer or are you running them inside of a Docker container that has all of its own bash dependencies installed?

[00:45:02] **Adam:** We are not running them in a bash inside of a container. We're running them locally, but, and, and this could be just the relative, uh, newness of the way that we're using make, maybe we just haven't evolved to the point where we need. a lot of complex stuff outside of what we get for free from the command line.

[00:45:23] **Adam:** The majority of the commands that are run in our MIG files are, um, you know, grep and xargs and we're using the one that immediately comes to mind though is the the gh command line tool which is githubs like CLI for accessing their API and doing sort of things. So, I've talked a little bit before about how my team is trying really hard to move from not multi tenant to multi tenant.

[00:45:51] **Adam:** And in the process, we're currently, we have 11, um, customer environments. And so we have 11 QA servers and 11 production servers and 11 production branches, one for each of those environments. And as a result, and we also have a main branch. So as a result, when there's a feature that is going to affect everybody, it gets forked off of main.

[00:46:10] **Adam:** We develop it, we test it, it gets merged back into main, and then it also gets merged into 11 customer branches. And then we have to deploy 11 QA sites and 11 production branches. And it's a bit of a pain. And so one of the things, it does, it sucks. And I don't want to throw anybody under the bus, but I was like complaining about this when it was like three or four.

[00:46:31] **Adam:** And I was like, wait a minute, I can see this is going to get bad real fast. And I was like, we need to multi tenant. This is a priority. And, and I've been, I've been the, the squeaky wheel saying, this is going to be a big problem. We need to handle this now, um, for years and, and we're finally moving there.

[00:46:49] **Adam:** And that just fills my heart with joy to see it finally happening. Um, we're, we're making that progress and that just makes me so happy, but. Uh, so one of the things in, that we, that we automate, we have sort of a set of other scripts that we share and you can just put these on your path and that makes it easy.

[00:47:05] **Adam:** So we have, um, for our pull requests, I created a script called GDPR, which was a tongue in cheek, uh, poke at the, like the European Union GDPR sort of thing. Um, but it's, Gosh dang pull requests is what GDPR stands for in our, in our case. Um, and basically it's so wholesome. Yeah. Yeah. And so you're on your feature branch or whatever, and you run GDPR and it asks you for a title and a body, and then it goes and it creates all of those pull requests to merge your feature branch into all of the branches that it needs to create.

[00:47:38] **Adam:** Right. So it automates all of that work. And so what would have taken you an hour to do manually, it does in 30 seconds. Which it could do faster, but they actually, I found out they're rate limiting their API, and we were starting to get, uh, once we got over a certain number of customers, some of those pull requests would just get ignored, dropped.

[00:47:54] **Adam:** Like, okay, well, I guess I have to add a sleep in there now, and so now it sleeps three seconds between each one, but... Uh, so

[00:47:59] **Ben:** as far as the GH, which I assume is

[00:48:02] **Adam:** the GitHub CLI that we... Yeah, that's provided by GitHub. So,

[00:48:06] **Ben:** if, for example, you needed to update the version of GH that you have, is that part of like a package JSON file that then...

[00:48:16] **Ben:** gets bumped and then everybody has that installed when they run the makefile kind of thing or does like if you needed to increase the version of gh how does that get managed across

[00:48:27] **Adam:** the team right now i don't have a good answer for that question right now it's a good question um and i can see it's definitely going to be a problem at some point in the future like when they you know they change features deprecate stuff whatever I can definitely see when that's going to happen, but it hasn't bitten us yet.

[00:48:43] **Adam:** And so it's been one of those things, if I can call back to a recent episode, we've just chosen not to prematurely optimize.

[00:48:51] **Ben:** I wonder if you could have package. json and makefile sort of run in, in like synergistically, like. Could you have package. json entries for GH and then have make use NPX and GH so that it's running a local version of

[00:49:08] **Adam:** GH sort of thing?

[00:49:09] **Adam:** I'm pretty sure that GH is written in Ruby or something else. It's not a node. I'm pretty sure that it's not a node thing. And that, um, so when, when I installed it, I installed it through brew, which is a Mac, uh, package system, package manager. Yeah, homebrew. Yeah, the command is brew. So I was thinking of it, think of it as that.

[00:49:27] **Adam:** Um, so yeah, I did brew install gh and it just shows up and you have to log in and then there. And so, you know, if something goes wrong, somebody, it'll go sideways. The, the command that somebody is trying to run will fail and they'll speak up in our team chat and we'll, somebody will help them troubleshoot and we'll go, okay, yeah, you just need to upgrade your latest gh.

[00:49:42] **Adam:** And I think when that becomes. problematic enough that, you know, people are annoyed by it happening too often, then we'll figure something out. One thing you can do, though, is you can just, again, this is, it goes back to anything you can do on a shell script, you can do in a makefile. Um, so you can say, uh, like, you can chain commands together and say, okay, when this one finishes, run this one, but only if it was successful.

[00:50:10] **Adam:** So you could, for example, say, uh, like gh dash dash version, and Like ampersand ampersand, then run a gh command, right? And so what that's going to do is it's going to print out the version, but it's also, in the process of doing that, going to verify that the person has it installed. And if they don't have it installed, then the command is going to fail.

[00:50:28] **Adam:** They're trying to print out the version, and then it's just going to exit from that. It'll say, command not found gh, whatever. And then somebody says, well, why am I getting command not found gh? Oh, you have to install gh, go run brew install.

[00:50:39] **Ben:** Does, does makefile have any sense of like a, like a pre flight or life cycle?

[00:50:44] **Ben:** Like. Run this target before every other target, where you could do some sort of, do these environment variables exist, or... I

[00:50:52] **Adam:** like where your head is at, and if you don't read deeply into the documentation, the answer I think, I'm pretty sure, would be no. But that's one of those questions that I have been asking recently and I figured out a way to do it.

[00:51:10] **Adam:** Now, I shouldn't take any credit for this. I figured out by finding various tips and hacks on Stack Overflow. So you can put a wildcard in a target name. The way that it basically works is Oh, not only can you put a wildcard or a target name, but you can then put, let me, let me pull up my make file that I'm thinking about here because I don't want to get it wrong.

[00:51:33] **Adam:** Okay. So I'm sharing my screen now. Can you guys see that? Yep. I know this is great podcasting, but bear with me. I was thinking about this when I was driving home today. Some aspects of this are probably going to be very visual and either what I will do is, depending on, you know, I'm going to edit this, depending on how this conversation goes, either I will just put code snippets in the show notes or I will post, you know, all the relevant details on my blog and we can link to that from the show notes.

[00:52:00] **Adam:** Oh, yeah. So look in the show notes and you'll see something visual available there. So. At the very end of my makefile here, I have a target called and that's just a wildcard. So basically, if you run a make command and it doesn't match anything else, it's going to run this command, which is just sort of the catch all wildcard And then I have two things here listed as dependencies.

[00:52:23] **Adam:** One is called checkForMakefileUpdate, which we'll come back to, and the other is FromBaseMakefile.

[00:52:31] **Adam:** And so what that lets me do is... And again, this is kind of combining things, but this is, I mentioned inheritance before and kind of faking it. This is actually my base makefile and something else includes this one. And you can override. So I've got, let's just say I have like a foo here, food, uh, and then dash from base makefile.

[00:52:53] **Adam:** Um, and I can echo foo there, right? Um, and If, if you have your other makefile that you are, uh, that you include this base makefile into, um, you can then create your own foo, and if you run makefoo, it'll run yours, um, and then from yours, so like, bear with me, this isn't the same file, but imagine that this is in a separate file, right?

[00:53:23] **Adam:** I'll put some dashes there. Our imaginations are good. Okay, good. So you got foo, and I want to echo bar here, right? That's fine. If you, if I run makefoo, I'm going to see echo bar. And that's, that's what's going to happen there. However, I, from here, I can also run make boo from base makefile. So this is effectively Calling super, right?

[00:53:44] **Adam:** Ah, used words

[00:53:47] **Carol:** I

[00:53:47] **Adam:** understand, man. Right? So I'm, I'm calling the, the parent implementation of this same target. Okay. Okay. So now we've, we've established, we've got a wildcard target that runs a base implementation if you don't override it. Right? You can override it and you can also call the super version of it.

[00:54:09] **Adam:** Now, I mentioned this check for makefile update, um, dependency on my wildcard target. Um, so what that does is, you can probably imagine, um, this is from a repo that we're creating that has that base makefile we want to share between multiple projects. And this is going to be checked out. Sort of outside of your project, but relative to it in a nearby folder.

[00:54:34] **Adam:** And when it runs this check for make file update target, it's going to go up and run a get poll to make sure that you have the latest version of the base make file before it, uh, includes it. So that ba So think of it this way, the reason, the reason it works like this is because I asked myself, okay, we can share code between, uh, projects with a, a base make file that gets included and we do this stuff.

[00:54:59] **Adam:** Now, how do I make sure that everyone's always using the latest version? How do I do automatic updates without having to make you go run a git pull in every place where you're, you've got this base makefile? And this is the answer. It does it for you. Interesting. So that is, Ben, you're asking about... Um, you know, can you run code before everything?

[00:55:21] **Adam:** And the answer is sort of if you're willing to, you know, I think technically, you know, purists would look at this and go, Oh my God, that's such a dirty hack. Get that away from me. Right. But for me, I'm looking at this and going, that's freaking cool. And yeah, it takes some explaining, which makes it a little, there's some smell to it, but I'm, it's a smell I'm willing to tolerate because it does cool stuff.

[00:55:46] **Adam:** I, you

[00:55:47] **Ben:** know, I look at this and I, I'm not very good at the command line. So, so this is a crazy statement, probably. That's

[00:55:53] **Adam:** a great transition to where I want to go next. Go ahead. But

[00:55:56] **Ben:** I almost look at it and it reminds me a little bit of the Docker build files where you can, in like your build can start from another image and then run a bunch of commands and yes, I guess most of those commands are very Docker image related, but I wonder if there would be some sort of opportunity, cause I know you can.

[00:56:18] **Ben:** So my understanding with the way Docker works is that it can spin up a container and then keep it running, or it can spin up a container, run a command, and then shut the container down, sort of like a one off thing. And I, I'm not saying that that would be any better in any way whatsoever. I'm, I'm trying to just build like metaphors in my mind to wrap my head around how this stuff works.

[00:56:37] **Ben:** Right. And it almost, I, I wonder if you could do some sort of like Docker build that's based on other Docker builds. But then I guess you lose your target. So then the whole point of it is the targets. Right. I guess. Right. All right. That was just a stream of consciousness. Forget it.

[00:56:52] **Adam:** That's okay. No, no, uh.

[00:56:55] **Adam:** What was the thing that you said that made me go? I want, that's where I'm going to go next. Command line. Oh, right. Yeah. So you had mentioned that you, you're not particularly good at the command line. And that's something I wanted to kind of talk about. Here, let me stop sharing my screen. Um, yes. Makefiles are going to work best for you if you are comfortable or, or, Whoever is making this makefile that gets shared among your team is comfortable on the command line.

[00:57:21] **Adam:** That's one of the benefits too, right? You only need one or two people that can figure this out. And then you've got awesome command line foo that can be shared among the team for zero base cost. But yes, some knowledge of the command line and tools there is going to take you a long way. Like, and even just very simple tools, right?

[00:57:42] **Adam:** Like most people, if they're not super familiar with how it works, understand what grep is, right? There's some, some text content and you want to search through it for words or, or regexes or whatever. You can include your search or you can exclude your matches. He loves regex. Yeah, I do. Like, I feel like just, if you could learn, and I didn't like, think in advance of specific commands that I wanted to list here, but I feel like There's probably less than 10 commands that if you could, you don't even have to master the commands, you just have to remember, okay, this command does this, and I need to go look up what that, what the syntax is.

[00:58:16] **Adam:** So like, for me, the ones that immediately spring to mind, obviously grep. Find is very useful if you're doing stuff on the file system. Um, for example, there was a thing that I did recently. Oh, and um, so this check for makefile update thing we talked about. One of the problems that I saw as I was starting to implement this was like, Okay, well, but we have make commands that call other make commands that call other make commands.

[00:58:38] **Adam:** And for each one of those, it's going to run check, check for makefile update. And so then that's going to do a get pull in that repo for every single make target. And that's going to add over time or, or once you have a complex enough task that you're trying to run, it's going to add a bunch of time to the time it makes that script run, which is annoying.

[00:58:59] **Adam:** And so what I did was I used find to check the timestamp on a file that gets get ignored so it doesn't get in your repo. And it just says like this was the last time that I did the search. And whatever the timestamp on the file is, that's when the last get pull was, and then I only run it. If it hasn't happened in the last 12 hours.

[00:59:19] **Adam:** So when we go to run check for make file update, if that file has been touched in the last 12 hours, then we just skip it. Like, okay, done. There's no update. Um, and so that was like a find command and what did I say? Grab find. Um, A A W K. Um, what's that? I, I have no idea what it stands for. It's, it's one of those that's like, It can do a hundred different things, and that kind of goes against the UNIX philosophy of do one thing and do it well.

[00:59:50] **Adam:** But it's just a super powerful thing, and I use it for one thing. If you have, uh, like a string of text, and it's got space delimited stuff, right? Something spits out like a table of what would appear to be a table on the command line. It's with some white space between columns. You can very easily use awk to print a certain column in that row.

[01:00:09] **Adam:** So, for example, that thing that I did that creates all the pull requests for us, um, the gh command. We'll let you, oh, uh, so yes, another thing is we've created all these pull requests. Now, somebody has to go review it and approve all of them, right? I was going to ask you about that earlier. Right. Yeah. And that's super annoying.

[01:00:27] **Adam:** Yeah. So you review the main one and then you have to go through and you just click approve, submit, approve, submit, approve, submit because they're all the same. Um, I made a script that automates that using the gh command line because they have a command to approve pull requests. Um, and the way that that works is you use the search.

[01:00:48] **Adam:** Like it has a, you can search your pull requests and there's a way to search by feature branch, right? So give me all the pull requests that are using this as their head, my feature branch. And it'll return all those, and it returns like, here's the pull request number, and here's the title, and here's a bunch of other stuff in random columns.

[01:01:05] **Adam:** I don't care about all that. I just want the pull request number so that I can say, okay, merge this one. Yeah, it's done. So, right. So the command is like gh pr search, and then in quotes, like head colon, current branch name, which you can use. You can run a get command to get the current branch name, right?

[01:01:21] **Adam:** And so you get that back, and then I run awk on it, and there's a way to make it print the first column, and so for each of those lines that comes back, it does print just the first column, so I get rid of everything else after that, and then, um, the next, so this, this is a good, because it transitions into the next, like CLI command or app, I think you should know, which is called XARGs, which is basically it takes multiple rows and turns them into multiple commands.

[01:01:48] **Adam:** So normally, if you get multiple rows of output, it's just like one string with a bunch of line breaks in it, right? And you can grep that and you can like filter it down or whatever. But what if you want to take each one of those lines, in this case, you know, a pull request ID number, and I want to run approve on those pull requests.

[01:02:05] **Adam:** You pass it, uh, you pass that output to the input of XARGs with some extra stuff and you can take each of those lines individually as input to another command. So, XARGs, GH, PR, Approve, and then some syntax that I can't fit into a podcast to, to, okay, so this is where the input goes. And so now I'm approving that one and it'll run that command that you put after EXARGs after each line of input.

[01:02:33] **Adam:** Does anyone else feel like they've just drank from a fire hydrant? Yeah, I feel like

[01:02:37] **Carol:** Adam's way nerding out

[01:02:38] **Adam:** right now. Oh, right. Way. He's so excited.

[01:02:41] **Ben:** It's funny, it's like when you hear on the radio about people who have taken LSD. What? And then they never see the world the same after that. It's like taking LSD.

[01:02:52] **Ben:** completely alters your perspective on life going forward. I feel like once people have learned to use awk, and there's another one I think called sed, which gets used a lot. It's like, once you've used awk and sed, you're like, I can never see the world the same again. Everything now gets piped through awk

[01:03:07] **Tim:** and sed,

[01:03:07] **Adam:** period.

[01:03:08] **Adam:** You've broken through the makings. So, I mean, by no means am I claiming, uh, any sort of ninja status with this stuff. Like, I feel very low on the skill level of all this stuff. What I know is roughly what command do I need to go figure out? What syntax do I need to go look up to do the thing that I want to do?

[01:03:28] **Adam:** Like, I know, okay, awk helps me get a single column from some output. And then I go look up the syntax or find it in one of my old scripts. And grep is how I search stuff. And you can do grep include or grep exclude. And you know, I don't remember any of that stuff, but I can, I know where to go. Google. But what amazes me

[01:03:46] **Tim:** is that the tech you're talking about here, all of this, the software is like written in the early 70s.

[01:03:51] **Adam:** Yes. Yes.

[01:03:52] **Tim:** Yeah. I mean, this is so old school. I mean, that's, and it's, it's still works. I mean, everyone's in love with the new shiny sexy, but you know, the stuff that works, man, and has worked for decades is

[01:04:03] **Adam:** rock solid. Exactly. It's, it's bulletproof. It's. Got great tests. So you know it's working. Um, do you, I mean, I forget what show this was on, but we talked about, um, use boring technology, right?

[01:04:19] **Adam:** You, this is something you can count on being rock solid stable. It's not going to break on you. It's going to work the same way every time. It's a little quirky. Like we talked, and this is when I'm, when I'm doing this stuff that I'm talking about here, I'm kind of pushing the boundaries of what it was intended for, right?

[01:04:33] **Adam:** I don't think when they created this wildcard stuff that they were intending for somebody to use. Inher it fit to, to trump up something that kind of, if you squint the right way, looks like inheritance and auto updating, like that sort of thing. That was never intended. But you made it work. But you can make it work.

[01:04:50] **Adam:** You can do some cool stuff. And they're not going to be

[01:04:52] **Tim:** releasing like every, you know, six months. No. And make a breaking change, right? I mean, this stuff has been, I mean, they're not, they're not

[01:04:59] **Adam:** Stable. Stable. Yeah. Yeah. Our Makefiles, they're not changing the way Makefiles work. They

[01:05:05] **Tim:** haven't done it for

[01:05:06] **Adam:** decades.

[01:05:07] **Carol:** The episode with scalability, by the way, like scaling.

[01:05:11] **Adam:** Okay. Tim's X. Oh, that's right. That was Tim's.

[01:05:17] **Adam:** I

[01:05:17] **Tim:** just, I just find that fascinating. Yeah. I mean, I, I was so in love with Linux. I just really had, you know, which is based off of Unix. It's just, it's quirky, but once you get to know it and really use it, it's so consistent as it's compared to other operating systems. Being able to type stuff out and being able to build files that do stuff rather than, you know, clicking everywhere with a visual interface is just so much an advantage.

[01:05:48] **Tim:** I was listening

[01:05:49] **Ben:** to an interview the other day, I can't remember even what podcast, but one of the guys was joking about how the, Unix philosophy is do one thing and do one thing well. He's like, which holds up really well until you look at the man pages for any of these things. He does have a thousand different arguments.

[01:06:06] **Ben:** Yeah,

[01:06:06] **Adam:** yeah. No, like, for example, git. Like, why is the command that, that I personally and probably most of you Use to create a branch. Why is that get checkout dash B, right? Why isn't it get branch?

[01:06:20] **Tim:** Yeah, there's yeah, there's so many inconsistencies particularly and get it with some of the command language, but

[01:06:27] **Carol:** And that's the, that's the thing I know most when you talk about command line.

[01:06:31] **Carol:** It's just get commands. It's, you know, ways to make that faster. So I was like, Ben earlier, I'm like, I just, my mind can't get away from aliasing things when you're talking about this. It's just an alias to something that's going to happen instead of it being a single line. You're talking about files and a multitude of actions instead of just.

[01:06:50] **Adam:** Yeah, aliases are a double edged sword because they're great on your local system. They make you more efficient, right? You, I can just do GCM or whatever, right? But then if you end up out of your element, if your computer breaks and you get a new one, or if you're over at somebody else's desk or whatever, and you have to do this stuff, you're like, uh, my muscle memory is now useless to me.

[01:07:11] **Tim:** That's when I stick everything in a gist, a GitHub gist. And I just have a command. I go pull those down and it creates all those things for me on

[01:07:20] **Adam:** from the gist. Yeah. Who cares? It's somebody else's computer. They can deal with the aliases later. I'll delete it later. No, I

[01:07:25] **Carol:** just slide over. I'm like, you handle all of these things.

[01:07:28] **Carol:** Get me on a branch, get me where I need to be, then slide back over and I'll start looking at

[01:07:31] **Adam:** the code. Yeah. I, I, it, it's private because I've got some private stuff in it, but I have a dot files repo on GitHub. Just my personal stuff, and it, it, I have all my aliases in there, so if I'm somewhere else and I don't.

[01:07:43] **Adam:** Uh, and I need to know, okay, well, what exactly am I doing when I'm using that alias that I have stored up in my brain? Um, I can go look it up and, okay, that's the command that I'm actually doing.

[01:07:53] **Ben:** I think about, uh, the closest thing that I come to using a makefile, I, I guess would be, npm run scripts. Yes.

[01:08:01] **Ben:** Okay. Oh, perfect. See, scripts can be kind of a recursive is not the right word, but you can have a run script that then calls other run scripts

[01:08:09] **Adam:** and they can call other things on the command line. Yeah. So I thought that would be a good way to wind this down was there are other scripting tools out there.

[01:08:18] **Adam:** Why would you choose make over any of them? Right. And so the one that you pointed out would be the my first choice if it wasn't make, I would probably use npm scripts, because I'm already doing Node stuff. I already have a package JSON, and I'm familiar with them. And And A lot of times I do have NPM scripts, so something that's specific to that project like to, um, if I'm doing like compile a bunch of JavaScript down to a single compressed file or, you know, run development mode of our framework, that sort of thing.

[01:08:48] **Adam:** It might be like NPM run dev or whatever. And then, um, one thing that we'll do is no matter what framework is being used in that particular app, Uh, you can standardize, okay, make up, we'll spin it up, and it doesn't matter if that make up calls npm run dev, or if it's doing a Ruby thing, or whatever, like, in app, make up makes it up, right, for dev, sort of thing.

[01:09:12] **Adam:** And, why would you choose makefiles over something like npm scripts? I guess, the first thing that comes to mind for me is, use boring technology. Right. NPM is still evolving, changing. And for the better. I'm not complaining about NPM changing. But, like this NPX thing that I was talking about earlier on GitHub Actions, it's not working.

[01:09:32] **Adam:** Well, I had no question and we have yet to have a problem where make wasn't working the way we wanted it to on GitHub Actions. Well,

[01:09:40] **Ben:** in an NPM script... Each individual script, if you're not calling out to another file, is literally one line of

[01:09:47] **Adam:** code. So it can only be one line. Yeah.

[01:09:49] **Ben:** Yeah. If you need to do a complex thing, it's a long line.

[01:09:54] **Ben:** Whereas with the make file, it looks like it's a lot more flexible in terms of just

[01:09:59] **Adam:** Yeah. And you can't really, um, separate them, right? They get smushed together. The assumption is that if you're going to put some stuff there, it's going to be a little bit of stuff. And if you happen to have one really long command, okay, that's livable.

[01:10:10] **Adam:** If you happen to have 20 really long commands, um, there's no, you can't put a line break between them. Cause when the next time you run NPM install or whatever, it's going to smush them all back together. You can't put like comments in that file that's going to get stripped out. And. Yeah, like there's ways to do in a makefile, you can do like a continuation, uh, in a shell script, you can do the same thing in a makefile, so you can break one command across multiple lines, a little bit of extra syntax, but you can't do that in an npm script.

[01:10:39] **Adam:** There's, again, there's ways around all of this, but I think that for me, The benefits of the makefile are consistency across projects, sharing that the shortcuts, for lack of a better word, scripts with my team, and removing the boilerplate of setting up command line scripts. Like, we could just as easily have like a scripts folder, and it could have a bunch of Node.

[01:11:02] **Adam:** js files in it, and those things could go and like... Use the FS library and check does this file exist? If not, then I need to go run this other script to create it first. That sort of thing. Or we could just use make and say, okay, when I need to run this, this file has to exist. And if not, this is how you create it.

[01:11:18] **Adam:** Like it, it abstracts a lot of that management of dependencies out into very simple forms. And so it lets you focus on the part you care about, if that makes sense. Okay. Your heart matters. We're done.

[01:11:38] **Carol:** Well, I like it because I don't have to know all the command line. Like if, if I was on your team, you've already done this work.

[01:11:43] **Carol:** So I just have to know the command to do it. And now that extra work is off my

[01:11:48] **Adam:** plate. And like I was saying with that GDPR thing, we have multiple and and they approve PR thing. We have multiple scripts that we share on our team. And they again, going back to our onboarding doc, it's like, okay, you're going to want to clone this repo and you want to put this folder on your path so that when you run such and such command, it'll go find it from there.

[01:12:07] **Adam:** And then. We can share tools like that that are very specific to our team and our workflow, but that, uh, are, are important to share and useful and efficient, productive. If I want to know,

[01:12:19] **Carol:** I can open the file and read it to see what it is doing.

[01:12:21] **Adam:** Exactly. And there's getblame on it. So you can go, okay, well, Tuttle wrote this, uh, you know, explain this to me.

[01:12:28] **Adam:** What is this doing? That's why it broke. Yeah. That's why it's awful. So you're done making out with me. Oh my God. Um, for tonight. We can talk about it more next time. Alright, well, are we ready to wrap it up then? I think we are. I think so. Okay. Well then... I learned a lot. My brain hurts, so... In a good way, hopefully.

[01:12:47] **Adam:** Oh yeah. Cool. Well then, I guess this would be the part where I'm gonna read our newest review, uh, on iTunes. We have another review. So, to whoever... Be a hater? Well, it gave us five stars. You can't hate that much. BobbyC2. The topics discussed are real world experiences of software developers. Their experiences are interesting and provide insight into different scenarios that we encounter in this profession.

[01:13:12] **Adam:** One can relate to similar experiences. and learn from others to make better decisions in the future. I also appreciate the honesty, openness, and vulnerability that the hosts show in discussing topics that may not always be easy to share. Yes, that was the goal, right? Like community and being honest and open and celebrating, not only the triumphs of our day to day life in this profession, but the failures too, because those are worth celebrating.

[01:13:38] **Adam:** Thank you, Bobby. Your heart

[01:13:39] **Tim:** matters, man. Love you. Appreciate it.

[01:13:41] **Adam:** Don't know you. But I love you. Cool. Cool. All right. Yes. Thank you for the review. So, uh, we've got a bunch of people supporting us on Patreon, and we really appreciate their support. If you think we've earned it, Which is crazy. We love you all.

[01:13:55] **Adam:** If you think we've earned it, please consider supporting us on Patreon. You can find us there at patreon.com/WorkingCodePod. We have different support tiers with different perks, like a lifetime invite to our Discord server, early access to new episodes, and the after show where we keep the mics running for another 10 to 15 minutes after the show ends.

[01:14:13] **Adam:** We also have what we call our top tier on Patreon for people who want to pay a little bit extra and in exchange, they get what we call sponsored shout out. So this week's sponsored shout out is going to go to WonderWomenTech, which is WonderWomen, W O M E N tech.com.

[01:14:29] **Carol:** We are generations is the theme this year for them, by

[01:14:32] **Adam:** the way.

[01:14:33] **Adam:** To everyone that just listens to the show. Thanks for listening. Don't forget to share the show with a friend because there's no better support than word of mouth referral. Tell the algorithms to boost our signal by leaving us a review and a rating on iTunes or wherever you get your podcast. Send us your topic suggestions on Twitter or Instagram @WorkingCodePod, or leave us a message on our new hotline at 512-253-2633.

[01:14:53] **Adam:** That's 512-253-CODE. We'll catch you next week. And until then, your heart matters.
