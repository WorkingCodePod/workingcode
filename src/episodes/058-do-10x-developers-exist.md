---
title: "058: Do 10x Developers Exist?"
description: "We discuss the concept of the '10x Developer'. This notion has its roots in bona fide research; however, much of the nuance has been lost in translation."
date: 2022-01-19
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/058-do-10x-developers-exist/id1544142288?i=1000548344009"></iframe>

Sponsors

- [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

Sometimes, people on the internet are wrong. And this week, that person is Tim, who said something inaccurate about the .net (dotnet) framework. Thankfully, our de facto .net ambassador, [Nathan Strutz][nathan-strutz], sent us a recording that shed light on the current state of .net, its open source architecture, its ability to run on many platforms, and its sweet, sweet modern features. Thank you so much Nathan for keeping us honest! And, keep those recordings coming!

For our main topic, we discuss the concept of the "10x Developer". This notion has its roots in bona fide research; however, much of the nuance has been lost in translation. When many people talk about the 10x Developer, what they imply is that there are _great developers_ that are _10-times more productive_ than the _average developer_. This is where the reality parts way from the research. What the research found is that, in software engineering, the _best engineers_ are 10-times more productive than the _worst engineers_. Which is, perhaps, a much more palatable and relatable comparison.

Of course, few developers work in a vacuum. And, when you're part of a team that is part of a company that is driven by a given culture, there's _so much more_ to being productive than one's ability to jam out code. If you're not working in an environment that actively caters to and encourages agile practices, no amount of coding velocity can escape the _gravity of inaction_.

Also, is [TJ Holowaychuk][tj-holowaychuk] even a real person? Or, is he an artificial persona concocted by a consortium of elite programmers who were keen to show the world what a 10x Developer might look like? We may never know!

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[nathan-strutz]: https://www.dopefly.com/
[tj-holowaychuk]: https://github.com/tj
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-twitter]: https://www.twitter.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/058-do-10x-developers-exist.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** I actually, for the first time, in a really long time, I had to start actively deleting podcasts just based on title.

[00:00:07] **Ben:** I like they were getting too far backed up. I'm like I'm never listened to this. I'm never gonna listen to this. I'm never gonna listen to this. And, now I finally unsubscribed from a few

[00:00:15] **Tim:** You're like working code pod. What's this click

[00:00:18] **Adam:** my code already works.

[00:00:20] **Tim:** about tests

[00:00:22] **Adam:** Yeah.

## [00:00:44] Intro

[00:00:44] **Adam:** It is show number 58 and on today's show, we're going to be talking about 10 X developers, I guess, in some cases, maybe to their face and in some cases behind their back. it depends on who's. but first as usual, we're going to start with our triumphs and fails. And Ben, my man you're going first.

## [00:01:02] Ben's Triumph

[00:01:02] **Ben:** Awesome. Happy new year, everybody. I'm going to kick off our first recording. I guess this is not our first show of 2022, but it's our first. recording of 2022. and I'm kicking off for the triumph at work during the holidays, we have a code and deployment freeze, which means that, between, I think it's like between December 23rd and January 3rd.

[00:01:24] **Ben:** You're not allowed to push anything to production, usually just because so many people are out, should something go wrong? There may not be enough people around with the expertise to fix it, which is a terrifying thought, but whatever, we just go with the flow, So with this, I'm not good at working on stuff if I can't deploy it.

[00:01:42] **Ben:** So because of this downtime, I knew I wanted to change my focus a little bit and do something a little bit more relaxed. And, what I chose to do was upgrade our angular JS library, which was on 1.2 0.22, which is like really old. And I wanted to try and upgrade it to 1.7 0.5, which is what another area of the app was running on.

[00:02:05] **Ben:** And, it was just a journey of looking at the angular migration guide and essentially stepping through all the different version upgrades and what the breaking changes are. And then seeing if those apply to our code base, which involved a lot of regular expressions searching across tags and looking for various attributes and function calls to see if things apply and then creating a list of things that I want to investigate further.

[00:02:29] **Ben:** And then essentially just putting in the new library, local. Refreshing the page, seeing what works, what doesn't work. And then once I could get a fix and then trying to figure out if this is a fix that would have to wait until after the angular JS upgrade, or if this is something I could, sort of like pre-build into the older version, but with the newer syntax or, you know a slightly different call signature or something to that effect, that would make it ready for the upgrade, but not a prerequisite of the upgrade.

[00:02:57] **Ben:** And, I went back and forth like that for like two and a half weeks, three weeks heading into the holidays. And just after the holiday, then I'm super excited to say that, as of about three hours ago, I deleted the entirety of the angular JS 1.2 0.22 library, which was 67,000 lines of code. And, nothing exploded.

[00:03:16] **Ben:** It's been pretty exciting. I'm pretty pleased about that. as is sort of the. at my role on this podcast, I will say that I did it with no tests whatsoever.

[00:03:25] **Carol:** know those coming

[00:03:29] **Adam:** I think you think of that as a triumphant itself? Honestly, man, I feel like you're a way it is. It's like what you're saying to me is I jumped out of a airplane with no parachute and I survived.

[00:03:44] **Carol:** I'm going to keep doing it.

[00:03:46] **Ben:** here's the thing, right. I'll obviously caveat I'm on the legacy team. I'm like the only one who touches this code anymore. There's no one who will come after me to look at this stuff. So there's a lot of, there's a lot more wiggle room than you would have when maybe working with a larger team.

[00:03:59] **Ben:** But it was so interesting because a lot of trying to figure out what needed to be done was again, taking this migration guide on the angular js.org website, which is massive. I mean, it's like pages and pages and pages of documentation on what can break, and then trying to figure out what applies to our code base.

[00:04:16] **Ben:** So even if I had tests, I like, I wouldn't be able to rely on them. I mean, yes. Would they help catch things potentially, but it wouldn't have made it any faster because I'd still have to look at every breaking change in the migration guide and then search through the code to see if it applied. Because even if I have tests, there's no guarantee that all the tests test the things that were breaking and even if they were testing the things that were breaking, there's no guarantee that the nature of the breaking change would be caught or accurately depicted within the test.

[00:04:46] **Ben:** So again, yes, test would have helped perhaps, but it would not have made it any faster or easier because essentially I would have been doing all the manual. correlation

[00:04:56] **Ben:** anyway, I'd

[00:04:57] **Ben:** have

[00:04:58] **Tim:** I'm going to give you a new title, Ben,you're the anti-pattern advocate.

[00:05:03] **Adam:** Uh, anti-testing apologists.

[00:05:04] **Tim:** Yeah, there you go. That might be better.

[00:05:07] **Ben:** we have no plans at this point to upgrade to a more modern, you know, to angular two plus something it's at angular 13 these days we have there's no way we're going to get there. But,

[00:05:15] **Adam:** yeah. So I'm detecting enthusiasm in your voice. Maybe not a ton of it, but some, it sounds like you enjoyed this process. And when you're describing the process of stepping through the version history and,what are all the breaking changes and how does that affect all of our code? That's my nightmare.

[00:05:31] **Adam:** That's.

[00:05:32] **Carol:** that does not sound fun.

[00:05:34] **Ben:** I enjoy the journey of it, right. Understanding that it's a grueling process and then figuring out how to. Take that and breaking it up into things that make it more manageable. So it's like I would have my, my get branch. That was my NG upgrade integration branch. And I'd start working on various breaking changes and I'd say, okay, here's a break change that does affect the code base.

[00:05:56] **Ben:** And I put it in, I'd make sure it works. and then I would do an interactive rebase on the master branch and then move the change that I just made actually, before I upgraded the angular JS library and then check out a detached version of that branch. So essentially I was, it was the old version of angular plus the fix that I just had, I'm saying, okay, now will this fix run properly in the angular 1.2 0.22 version, because that means I could then deploy it pre upgrading of the angular and then have it ready to go.

[00:06:24] **Carol:** Ah, it took me a second to figure out what you were talking about. Knocking the lie right there at the end. The circle was a little big, but now I see. Okay. you were making changes and trying to see if on the old and the new way that the change you made would still be, sufficient and work, right?

[00:06:39] **Adam:** like backwards

[00:06:40] **Adam:** compatible.

[00:06:40] **Carol:** Yeah. Yeah. That's the

[00:06:42] **Ben:** ultimately when I flip the switch and deploy the code that has the newer angular JS version, I want that deployed to be as small as possible and have as few moving parts as possible. Ideally just because the less that could actually break and go wrong. And I was able to actually get

[00:06:58] **Tim:** And because you don't have tests

[00:07:00] **Ben:** and because I don't have tests, so I was able to get like 95% of all the breaking changes actually working with the earlier version of the angular JS library deployed incrementally to production.

[00:07:11] **Ben:** And then the actual final cut over, was really just a handful of files that, that depended on the actual changes in the latest library.

[00:07:19] **Carol:** It's really good. Like Tim and I did that years ago, we had to do an upgrade and it was a pain going through and trying to figure out what all could break with all could happen. I don't wish that on anyone. So the fact that you seem to have enjoyed it and had a good time doing it. Good. I'll see you then.

[00:07:36] **Tim:** power to

[00:07:36] **Tim:** you.

[00:07:37] **Ben:** and thankfully, no one else was working on this code base. If other people were actively adding code while I was trying to do this, I think that would have been a

[00:07:45] **Carol:** Yeah, no, thank you.

[00:07:47] **Tim:** Yeah. That was kind of our situation.

[00:07:49] **Carol:** Yeah.

[00:07:50] **Ben:** Oh no, thank you. Anyway, so that's me. I'm excited about that. Adam, what do you got going?

## [00:07:56] Adam's Triumph

[00:07:56] **Adam:** I am also going to go with a triumph. I know this is kind of just been the running theme for, it feels like months now in my traps and fails, but, we are making big steps towards multitenant and, as the weeks tick by, we continue to make steps. my big accomplishment from the last week or so we had this one microservice.

[00:08:15] **Adam:** That. I mean, I guess we were kind of thinking of it as a microservice, but it was a separate process running on the same server. Right? So we have our ECE two instance running the primary monolith app server. And then we had broken out this other thing to run on its own. and it could run like, a cluster of multiple processes and that sort of thing, but it was all running on the same server.

[00:08:38] **Adam:** It was like node being managed by PM . And one of the hurdles of moving toward multitenant was to get all of those little processes that were maybe somewhere between a half, a dozen and a dozen of these things, that were living on all of our monolith app servers. One for each customer needed to get those to be off of those servers so that we could then take the later step, of getting the app server itself off of those servers.

[00:09:03] **Adam:** and so as of this last week, Shut down all non monolith processes on all production and QA servers.

[00:09:12] **Ben:** Nice.

[00:09:14] **Ben:** Very exciting.

[00:09:14] **Adam:** So that was just the big one. And that was not going to be, accomplished by next week. It'll probably be months before that's completely accomplished the next big thing. This is a, maybe a good discussion to have at some point, but the next big thing is going to be, we used ORM pretty heavily and I'm regretting that decision if only, and I have a lot of reasons that I don't like alarm, but, in this case I'm regretting it because now we're talking about, changing our servers so that any node in the cluster can handle. Any requests for any customer. And in order to do that, all of our customer databases are separate. And so they have different, data source names in Lucy. and so it depends on the application static data source name.

[00:10:04] **Ben:** Oh,

[00:10:05] **Adam:** Yeah. So at this point, our understanding is that we're going to have to replace all of our ORM usage with straight up queries before we can take that next leap, which that's not going to be a quick, easy process.

[00:10:18] **Ben:** Oh, we had a guy at work. This was maybe like a year or two ago come to my team. And he was like, Hey, we're thinking of ways to reduce our costs. And we had, we have a similar situation where we have different tenants running in a lot of different places. And he was like, how much work do you think it would take?

[00:10:33] **Ben:** If every request that comes into the application could use an arbitrary S3 bucket for storage and an arbitrary data source for data access. I'm like in the entire app, he's like, yeah. You know, just for like every, every request coming into the app, I was like, that's a massive amount

[00:10:48] **Adam:** Yeah. You know, two, three years of 10 people's time.

[00:10:54] **Ben:** We need a team of 10, five years.

[00:10:57] **Adam:** Meanwhile, tell me if this picture has a burden to yeah. I need two weeks. One person.

[00:11:02] **Ben:** Oh man. So are you still running, last time we had talked you that you had said you were, you like doubled the number of boxes that you had to have. Are you still running at the, at a larger number? Are you somewhere in a happy medium now?

[00:11:14] **Adam:** So yeah, I think the thing that we talked about last time was all of our QA servers had our architecture is changing, right. Instead of. Manually managed ECE two instances we're switching to more of a configure as code, and that's creating far gate instances and those are, I mean, it's great from a developer productivity and a toil and like doing deploys and everything.

[00:11:36] **Adam:** It's all so much better, but the resources required in order to run those same containers are roughly equivalent containers on far gate versus . The cost is almost triple. and so we've, we made that change for all of our QA and then we went, oh God, we're going to have to figure something out. we've got time, but,being developers is certainly a lot more expensive than paying for hardware every month.

[00:12:00] **Adam:** So

[00:12:02] **Ben:** True. True.

[00:12:02] **Adam:** yeah. I guess. That's it for me? So, Tim, how about you, man? Hey.

## [00:12:06] Tim's Fail

[00:12:06] **Tim:** I'm doing okay. I got it. I got a fail. Of course I, I wasn't on last episode or last show because I was sick and I'm still not a hundred percent, so I don't really have any, I pretty much spent all of last week in bed. And then the beginning of this week, I'm trying my best to work and catch up.

[00:12:24] **Tim:** But I, every couple hours I got to go lay down for half hour or so, because yeah, this, this thing's kicking my butt. I thought it was COVID it was not, it was not which I'm actually kind of glad because I've done everything right. triple vaccinated got the booster, in social distancing and all that stuff.

[00:12:42] **Tim:** But yeah, this is just influenza a so, but it's no joke. So,

[00:12:48] **Carol:** well, hate you got it. That sucks.

[00:12:50] **Tim:** but glad to be on the show again, talk to you guys and get to hear what Nathan, what, what did we talk about? 10 X developers. And I think we're going to talk a little bit about a listener. Had some comments called me out on some stuff I said wrong.

[00:13:01] **Tim:** So not quite a hater. Maybe I can turn them into one cause I need more haters. It would make me feel better.

[00:13:07] **Adam:** So Nathan, we're going to need you to call back and say that Postgres sucks.

[00:13:11] **Tim:** Oh,

[00:13:13] **Ben:** The ShotSpotter.

[00:13:13] **Tim:** fired. So that's to me that not a whole lot. How would you, Carol?

## [00:13:17] Carol's Fail

[00:13:17] **Carol:** I'm going to go with a failure to, just haven't felt good this week. Not as bad as you just been like off his day. My head's hurting really bad, but I'm

[00:13:24] **Tim:** not a competition.

[00:13:25] **Carol:** I am on call too. So I don't know if being on call has just like stressed me out and made me not feel good, but this call has stopped. It's not been a fun one.

[00:13:37] **Carol:** It's my second week of it. And they're just fires kind of all over the place that seemed like fire. Not a single one of them have been an actual fire. It has been researched backwards to find out that some other application is down or somebody stops sending us data this year. Or, you know what, two weeks ago we posted code.

[00:13:58] **Carol:** Cause you told us to take this out. It doesn't work anymore. And now you're complaining and it doesn't work anymore. And I'm just like, these are stupid requests to becoming in. So it's just been a, not fun on call situation. So I'm ready for it to be over two more days. My on-call is over and I get to be done.

[00:14:16] **Adam:** I had this realization about on-call and not too long ago, since we're a startup, right? there's only a handful of developers when it started, I was on call 24 7, cause I was like the only non CEO developer are CEOs, capable, but this product was more my, in my hands and we have another one that's kind of his thing.

[00:14:34] **Adam:** And then we hired another developer and my on-call time got cut into. Right. after he was up to speed and then we hired another developer and my on-call time only went down to a third of its original. And then you know that when we hire another, it will be a fourth of it's original. So it's like diminishing returns.

[00:14:51] **Adam:** The more people you hire, if you were optimizing for less frequent, on-call the amount that each new hire contributes to be to you being on call less frequently is fewer and lessand less. If that makes sense. It's I mean, not that I don't want to hire people because it's not going to help as much, but still it's like, it was kind of a sad thought when.

[00:15:15] **Ben:** you just got to go into management and then you have no on-call responsibility.

[00:15:18] **Carol:** How about that, Adam?

[00:15:20] **Adam:** maybe we, talked to,

[00:15:21] **Carol:** We did.We

[00:15:22] **Carol:** did.

[00:15:23] **Adam:** I mean, so this was something I had thought about mentioning during my triumph, but, one of the things that I have done this week as well was, so I kind of came across this old post from whatever, a video from get hubs, like online conference thing. They did a couple of months back, and they have a new version of their like projects thing that's built into their issues.

[00:15:44] **Adam:** Right. It used to just be like, you could do a Kanban board of your issues. Well, now they have a whole lot more functionality built in and it's kind of more like a mix of Kanban and spreadsheets and you can change views and stuff, whatever. but so I, I took the opportunity to. go through all seven pages of the issues in our repo and put them all into one project called roadmap and start to prioritize things like I,

[00:16:06] **Adam:** It comes with a status column by default. I added, importance, urgency, and then priority. Cause the way we think about things as, sort of that matrix grid of, is it important and is it urgent if it's neater than you probably shouldn't do it? If it's both, you should probably do it now. If it's only one then kind of sooner rather than later, whatever.

[00:16:24] **Adam:** But, and so, yeah, and I went through all seven pages of our issues and try to get them all at least, in the right bucket, whether it's like icebox, come back to this way later or backlog come back to this sooner sort of thing. And, that I think.

[00:16:40] **Adam:** Yeah, to my personality. Yes. I very much enjoyed it.

[00:16:44] **Adam:** It wasn't even something that originally I was supposed to do. It was something that, Steve, our CEO was going to do and, he didn't get to it within like 24 hours. And so I started getting itchy. I was like, Ooh, can I could organize stuff? And so I went and organized stuff and he thanked me for it later.

[00:17:00] **Adam:** but it was, yeah, that's just my personality. Right. I think we talked about this either last week or recently how I'm starting to notice that I have these tendencies that you might associate with a product manager. Right. I like to organize a

[00:17:14] **Adam:** light. I like to write certain types of documentation and that just certain aspects of that stuff is appealing to me.

[00:17:23] **Adam:** So I enjoyed that. Okay. Are we ready to move on?

[00:17:27] **Carol:** Yeah.

[00:17:28] **Adam:** it. So here let's do this. our listeners are smart people. They're going to know it's time to pay the bills. So we're going to do our audible ad here.

## [00:17:35] Audible

[00:17:35] **Adam:** Just like every other podcast on the planet, you can help us out by going to audible trial.com/working code pod, sign up for free trial costs.

[00:17:44] **Adam:** You nothing. We get a little bit of money from that and you get a free audio book and 30 days to listen to it, and then you can continue on if you like it or not. If you don't.

[00:17:54] **Tim:** Assuming you don't have one. It's like, I've had one for years. I have a hundreds of books. I couldn't live without audible.

[00:18:00] **Carol:** love all the bowl. Like it's always on in my car then, or a podcast. I get tired of music because I listened to music when I code. So books and podcasts are great for car rides.

[00:18:10] **Tim:** But if you are one of the two people left in the world who don't have audible, please by all means help us out. That'd be awesome.

[00:18:16] **Adam:** We'd really appreciate it.

[00:18:18] **Tim:** We would.

## [00:18:19] Listener Nathan's Notes On Ep. 49: Revisiting Replatforming

[00:18:19] **Adam:** Okay. So we're going to play this voicemail that we got from Nathan for you. let me tee this up by saying that we used to have a phone number, I guess, technically we still do, but we don't advertise it anymore because telephones are old technology and the audio quality is just garbage. Instead, what you can do is make a voice memo on your phone and email that to us@workingcodepodatgmail.com, or I guess if you would rather you and you have a good mic for your computer, you can record it on your computer and send it to the same email address.

[00:18:47] **Adam:** and you'll hear right now this awesome quality voice memo we got from Nathan.

[00:18:52] **Nathan:** Hey, it's your boy nascent strengths. Again, what's up friends. I'm calling to talk about episode 49, revisiting replatforming. I think you need a little help. So I happily volunteer to be your ColdFusion to.net liaison or interpreter, whatever you need. Starting off. Tim said, dot net only runs on windows.

[00:19:16] **Nathan:** Well, guess what? That no longer, only runs on windows over the past five years, a rewritten version of.net called Danette core has been running on windows, Mac, and Linux in 2020 Microsoft. Renames done that core to.net five. So this is the way going forward. This technology works for me. I develop on windows, but I deploy all my code to Linux.

[00:19:45] **Nathan:** Pretty great. recently.net six was released and it's really good. It's open source. It runs on any platform it's wicked fast, just blazingly quick by default. It comes with C-sharp 10. Mm. F sharp six different languages and.net, or like Kotlin or Java or groovy in the JVM world. So different languages can run.

[00:20:09] **Nathan:** C-sharp has a lot of beautiful parts in the language, especially more in recent years where it's taken a lot of JavaScript character. Without losing all of its type safety. For example, you can use the VAR keyword almost everywhere. The compiler will just figure out all the data types for you. It has all those map filter, reduced types of functions that can run across all types of collections, even asynchronously across CPU cores, but they go by slightly different names, select instead of map, where instead of filter aggregate, instead of reduce the idea is that it's kind of more like querying your.

[00:20:41] **Nathan:** So they use SQL words. Also tiny anonymous arrow functions are really common. Again, type safety still works easily. Thanks to that. Compiler C-sharp 10 just came out with dotnet six. Some of the more notable parts are implicit using statements so that your class files are a lot smaller and simpler and minimal APS.

[00:20:59] **Nathan:** Like an entire microservice in three lines of code. Of course, it's more, if you want to talk to a database or whatever, but three lines of code. That's awesome. Edelman, Ben mentioned asp.net web forms. Well, they're right. Webs forms was absolutely the worst. Just terrible. Post-bacc sloppy syntax. Terrible.

[00:21:20] **Nathan:** Of course you can make terrible code in any language, but it wasn't a good platform for large apps. Of course, that didn't stop. And it pretty quickly broke down when things became complex, but as p.net, NBC, that's actually really good uses conventions that just work. It's a very well thought out framework.

[00:21:39] **Nathan:** It has starter templates that are quickly generated with the dinette CLI uses the razor syntax for HTML templates, which is pretty easy. It's, uh, like a more elegant CFML PHP, in my opinion. It's well thought out. I actually don't use razor though, because I started down the path of JavaScript interfaces with react and view, which are better suited and can integrate natively with Danette applications.

[00:22:06] **Nathan:** That's a cool thing. Moving on. Carol mentioned some pain with MVVM. I feel for you, I have also experienced a form of MVVM hell and it can be pretty bad and super confusing. Adam was talking about service-side JS as a good choice. Yeah. It's very web native. I would say you could look at.net and you may be pleasantly surprised.

[00:22:29] **Nathan:** C sharp really is faster and very similar to TypeScript since Microsoft had a lot to say in it. Final note, the number of programs in the world doubles every five to 10 years, it's debatable, but that means maybe every five years, an actual majority of code. I have no idea about any of the things from say 2015 and before.

[00:22:51] **Nathan:** Very few of the younger people I've worked with have ever heard of ColdFusion, much less seen it to be fair. They also haven't run into PHP, but let that sink in our industry has an immense growth rate, but the demand is still outpacing it. That really explains a lot of the programming memes. I see all these brand new programmers with no idea how we got here.

[00:23:09] **Nathan:** It's crazy. All right. Have you held. Thanks for listening to me for once I really enjoy the podcast. Adios.

[00:23:17] **Carol:**

[00:23:17] **Carol:** Nathan.

[00:23:18] **Adam:** Yeah, Nathan's great. one of my favorite people from Arizona and hang out with,

[00:23:21] **Tim:** How does he not talk without any ums or AHS?

[00:23:25] **Carol:** When he speaks. Yeah. When he speaks, it sounds like he's reading written word.

[00:23:30] **Adam:** but also not like he's following us.

[00:23:33] **Carol:** No,no, he's following us, but there's no, he doesn't pause. There's nothing. He's great. He's just great. Clearly I have this down, pat. He's good.

[00:23:43] **Tim:** Although he totally called me out.

[00:23:45] **Carol:** Everybody does, Tim.

[00:23:49] **Tim:** Yeah, I'm going to just start with that. Nathan. I don't know where I heard that only ran on windows. I'm sorry. I repeated false

[00:23:56] **Carol:** It used to, no, you used to, you were

[00:23:58] **Tim:** Yeah. Five years ago.

[00:24:00] **Adam:** well, you're old. You forget

[00:24:02] **Tim:** Yeah, that's true.

[00:24:03] **Carol:** that. And then of course thing, but I didn't know. It was.net five.

[00:24:07] **Adam:** yeah, so, I guess it's official right now. Nathan is our dotnet ambassador.

[00:24:13] **Tim:** yeah. Yeah.

[00:24:14] **Adam:** He volunteered. So when we have.net questions, we'll give him a.

## [00:24:18] Dark Matter Developers

[00:24:18] **Ben:** His passion about.net reminds me of something that I hear from time to time, which is this concept of dark matter developers. I don't know if anyone has heard this phrase

[00:24:28] **Adam:** It sounds really interesting, but I don't think I've heard it.

[00:24:31] **Ben:** it's this idea that in the social media spheres, there are the popular technologies. Like everybody's talking about react and everyone's talking about node and Deno and rust and.

[00:24:43] **Ben:** And you, if all you do is go along by what you see people talking about publicly, you sort of get this sense that the world has moved on, and these are the hot new technologies, and this is what everyone's doing. And then what you realize is that there's this giant mass of quiet developers that are just sitting there, churning out work, using technology.

[00:25:07] **Ben:** That's been battle tested, and it's not necessarily the new hot thing. Although net is continuing to evolve, obviously, and you don't realize that some massive population of people use.net and it's a super popular language. And it just doesn't get the kind of play that some of the newer technologies get.

[00:25:23] **Adam:** Yeah. So it's the opposite side of, the vocal minority. It's the quiet majority. Yeah, that makes sense.

[00:25:31] **Carol:** It does.

[00:25:32] **Adam:** And I would say it seems intuitive that that's probably true.

[00:25:36] **Ben:** It's so hard to deal with sometimes though, like the nagging voice in the back of your head, as someone who works on typically viewed as legacy technologies,

[00:25:45] **Adam:** Yeah. I mean, it's FOMO, right?

[00:25:48] **Ben:** yeah, it's fun. And actually to, to his point in the recording, that the number of developers doubles every five years and a lot of these people don't even know what you're

[00:25:56] **Adam:** Oh yeah.

[00:25:57] **Ben:** that's that is even, and if you consider like, those are the younger people, they're probably the ones also more likely to be very heavily engaged in social media or more engaged in social media.

[00:26:06] **Ben:** It's like this compounding effect that you get these weird echo chambers of,of the new people, not knowing the old stuff and thinking all the new hotness in social media is the thing to be focusing.

[00:26:17] **Adam:** Yeah.

[00:26:18] **Tim:** I kind of feel that way when, Sean, Corfield kind of berates me for like, not reading a book from 1960 about programming. I'm like okay. Shot and whatever. All right.

[00:26:29] **Ben:** Well, you know, everything,everything, that's, what's the phrase like everything is that's old as new

[00:26:33] **Tim:** Yeah.

[00:26:34] **Carol:** Oh, yeah, that is a

[00:26:35] **Ben:** Uh, youeven I forget which podcast it was, they were talking about predictions for the upcoming year and they were talking about how monolith. Kind of back in Vogue, again, like everyone's swung really hard in the microservices world and they realized how hard that is to do, especially with small teams.

[00:26:51] **Ben:** And now the idea of these modular monoliths or things with more of a monitor repo type thing, like people are like, oh yeah, that actually solved a whole lot of problems and was made life a lot easier. And then, react was like super, super popular. And now people are not leaving react, but people are moving from react to other things like view and, and some of the server side, even in the react world, going back to some of the server side rendering, it's so fascinating to watch,

[00:27:15] **Carol:** feel like you get to be a pioneer of that bin of the moving to microservices, and then going back to monolith. You're like I did at first, I was there

[00:27:25] **Ben:** oh man,

[00:27:26] **Ben:** shutter, shutter.

[00:27:27] **Carol:** with that. We were talking today at work about things that we're going to learn in 2022. You and our newest engineer that we hired says, well, I guess I'm going to learn angular JS because we use that here.

[00:27:40] **Carol:** That's the first time. And I don't know how long someone said, I'm going to learn angular JS. I was like, whoa, it just caught me off guard that someone has to learn this because everybody knows it or I thought so. Yeah, that was interesting.

[00:27:55] **Ben:** That's exciting.

[00:27:56] **Adam:** It's been a long time since I've done angular. I probably was in like the 1.2 ish era. And then. we had a couple of small projects in it, but it didn't end up going anywhere. That was like a product that we tried out and then the product itself kind of flopped. and by the time we came back and had a similar need react was more, appealing to us.

[00:28:16] **Adam:** And so we, we tried that out and that kind of stuck. So I have no idea what modern angular looks like. I did. I wanted to say, I was kind of surprised when Nathan said the dot-net is now open source. I didn't really realize that's the, I mean, that's great for them. I think that's only gonna benefit the platform and it probably helps with it being cross-platform and I mean, I guess going back to the whole thing, the whole episode that he was referring to was about replatforming.

[00:28:45] **Carol:** And so that patron that, we were talking about in that episode, they've since, settled on Kotlin, which I think is like a Java thing. does it sound like a Tim word?

[00:28:55] **Adam:** I don't know.

[00:28:57] **Carol:** Tim knows.

[00:28:57] **Carol:** Kotlin I don't know why though.

[00:28:59] **Tim:** I don't know, Caitlyn, we talking about

[00:29:02] **Carol:** I guess a swore you said this before.

[00:29:04] **Tim:** no, I got schooled on it. Cause I didn't know. I didn't. Yeah, we were talking about that on this episode that Nathan's talking about.

[00:29:10] **Tim:** Yeah.

[00:29:10] **Carol:** Oh, okay. It's all

[00:29:11] **Tim:** Yeah. We were reviewing Kotlin I'm like, I don't know nothing about Kotlin

[00:29:14] **Adam:** Okay.

[00:29:15] **Adam:** Maybe we just remembered hearing you say

[00:29:17] **Carol:** yeah.

[00:29:18] **Tim:** I said the word that's about it.

[00:29:20] **Tim:** I said, I didn't know anything about it.

[00:29:21] **Adam:** do any of you guys have any experience with like C sharp or F sharp?

[00:29:24] **Carol:** Yeah, C sharps, what I wrote@thegovernmentgigandwewereon.net. So we had a VB project as well. And when I was leaving, would they were in the process of re doing the architect, planning to switch the BB project over to.net core. So I left before that happened, but yeah, C-sharp.

[00:29:41] **Adam:** I did some C-sharp at a previous life. And I would have to say like, if some of the things that are available to me now were either not available at all, or we're just like, sort of outlawed like this, the whole hypothetical question that we explored in episode 49. for various reasons, certain things were eliminated from the list.

[00:29:58] **Adam:** So if, like if I couldn't do node right now, probably near the top of my list would be like C sharp, especially if I had known that it would run on any platform and was open-source that sort of thing?

[00:30:10] **Tim:** I,

[00:30:10] **Tim:** wasn't the only one.

[00:30:11] **Adam:** yeah, no.

[00:30:14] **Adam:** I

[00:30:14] **Carol:** mean, yeah,

[00:30:14] **Adam:** too, that I knew that there was, I was a familiar that there was like a,what was it called mano?

[00:30:20] **Adam:** Was that it, where you could run ASP? I think it, yeah, it wasn't like classic ASP. It was asp.net on Linux or something, but it was like a community project for trying to get some compatibility with.net. And I don't think it had gotten very far at the time that I was playing with it and it just wasn't as useful as I would have needed it to be.

[00:30:42] **Adam:** So

[00:30:42] **Adam:** yeah.

[00:30:43] **Tim:** So I have a question about arrow functions and he, Nathan was touting the arrow functions. And I know, I mean, I know what they are. I've been exposed to them. Scala uses them. You can use them in JavaScript too. I'm pretty sure, but I mean, it's pretty much,

[00:30:57] **Tim:** it's a Lambda, it's an anonymous function, but here's my question on it. It seems to me the fact that you're building a function, you don't have a name on it to describe what it does almost kind of goes against the clean code principle in my mind that we talked about from uncle Bob Martin, am I wrong in that?

[00:31:16] **Adam:** it's an interesting question to ask. So even before arrow functions, it was possible to do unnamed closures in JavaScript, right? So you could like, as a callback, you could just pass an anonymous function is what it was called. Cause it doesn't have a name. and the impression that I got after a few years of doing that was that while it was possible and yeah, it saved you some keystrokes and not having to think about what, an appropriate name for the function would be.

[00:31:43] **Adam:** the. Cost of that choice was that then in a stack trace, you would just get like function instead of the name of the function, which makes it harder to figure out what's what you're looking at in that stack trace. I think the stack trace is really the only thing I can think of for those anonymous functions.

[00:32:01] **Adam:** That is a downside.

[00:32:04] **Tim:** Yeah. Cause our scholar stack, we use it. There's,arrow functions all over the place. And, but I've never personally wrote one just because I like to know what is that function doing? And I give it a name. And so, maybe I just don't understand, is it buying? Is it buying me anything else other than the fact that I'm not having to name it?

[00:32:23] **Tim:** And I, I hear the argument is that, well, this is a function that you're only gonna use exactly in one place all the time. And that's probably true, but I'm sure that there's an exception. Maybe I can't think of one, but.

[00:32:34] **Adam:** So in, in JavaScript, there are other things about them. the biggest one being that it, an arrow function has no, this, pointer, I guess, is what you would call it. it, it uses the, this from its parent closure.

[00:32:49] **Ben:** it maintains the, this in which it was

[00:32:51] **Tim:** And has access to the parents scope. Is that.

[00:32:54] **Adam:** Not just that it has access, all closures have access, but like, so for example, jQuery, right? if you did a, an event handler for a button, click and jQuery, and you give it a function as the callback, and you did like dollar sign parentheses this to get the element that was clicked. If your callback function was an arrow function, you wouldn't get the element that was clicked because there is no this, you get basically an empty. I actually ran into that the other day. Cause it just happened to be updating some code that was jQuery and a button click handler. And I was like, oh, I Unix, I know this. Right. I, threw in an arrow function cause I thought I was being clever. And then I spent 15 minutes going, Wyatt, why am I not getting the reference that I should be getting?

[00:33:38] **Adam:** Oh duh, because this doesn't exist or is not what I'm expecting it to

[00:33:43] **Tim:** and cause what's in that arrow function is only the. Clear on the left-hand side. Right.

[00:33:47] **Adam:** it still has a, this pointer, but it doesn't get a unique, this pointer bound to anything

[00:33:56] **Tim:** Gotcha. Okay. All right. I understand.

[00:33:58] **Adam:** the parent, whatever, the, whatever this pointed to immediately before the arrow function is what it points to inside there.

[00:34:07] **Tim:** Gotcha. Okay.

[00:34:08] **Adam:** And that's specific to JavaScript. I don't know if that's also true

[00:34:11] **Adam:** for

[00:34:12] **Tim:** think, I don't think, that's a true in Scala.

[00:34:14] **Ben:** there's also some syntactic sugar in terms of the return statements I like with, with a fatter. If it's a, if it's just a simple mapping expression, for example, like your fat arrow function takes point and then returns point dot X or something, then, you, you could theoretically exclude even the curly brackets around the function body.

[00:34:36] **Ben:** And you, I think you can.

[00:34:37] **Ben:** even exclude the return

[00:34:38] **Ben:** statement, but going back to your clean code statement, the idea of defining a function and not having curly braces and not having explicit return statement to me feels like

[00:34:50] **Ben:** that feels like as far away from clean as you can get.

[00:34:53] **Carol:** It feels so dirty.

[00:34:55] **Adam:** Did we talk, maybe it was on the aftershave or something, but didn't we talk recently about, a blog post that kind of came across my radar. Like maybe it's time to stop recommending clean code.

[00:35:04] **Carol:** II have it open in my tabs still and I haven't finished reading it. That's a long

[00:35:08] **Carol:** post.

[00:35:08] **Adam:** It is, it's got a lot of comments on it too. So the scroll bar is not exactly indicative of, uh, how long it is, but it is a long post by itself. And I mean, just in case we haven't already covered it. I think that the thesis of that discussion, it was just that, like, it was an okay book for its time. but a lot has changed and also there's a lot that can be kind of discarded based on, if you have, if you happen to be lucky enough to have 10 or 20 years of experience in

[00:35:33] **Carol:** Right. the learned,

[00:35:35] **Adam:** you know, you learn better practices, things that are specific to your language or your framework or whatever, that kind of overrule the default rules that you would assume from something like clean.

[00:35:46] **Ben:** One of the things going back to Nathan's call and the dotnet stuff. one of the podcasts that I really enjoy listening to is called dotnet rocks and part of why I enjoy it so much is I don't know anything really about.net. I dabbled in C-sharp maybe like 15 years ago for like three months. so I'm sure that what I use then is, has like almost.

[00:36:06] **Ben:** Resemblance to what is actually available today, but I find it really interesting to listen to podcasts about technologies that I don't have any experience with, because it's like, you're not only listening. You're trying to then translate what they're saying into something that may or may not make sense in the technologies that you understand.

[00:36:24] **Ben:** And I like, I love listening to Golang podcasts and the.net podcast and just any podcasts I can get my hands on.

[00:36:30] **Adam:** Are you, are you doing active listening? Like, are you listening with intent to try and learn when you do these things? Cause you talk about this and it just seems so foreign to me. I would be so confused trying to follow these discussions about something that I have no idea what's going on

[00:36:44] **Ben:** it's a background noise, but I, it's a background noise during certain activities. Like I couldn't code and listen to a podcast for examples, but I can do it when driving or when walking the dog, something where I can sort of dedicate some amount of brain processing to it.

[00:36:58] **Ben:** a lot of times I don't understand even what they're talking about. So it's more like light listening and then they'll say something that strikes a chord and then I kind of go into a deeper listening

[00:37:07] **Ben:** state and then pop back up to lighter listening. Cause also, I guess there's a lot of, there's a lot of, just jib jab, and then eventually they talk about? something very technical.

[00:37:17] **Adam:** about.

[00:37:18] **Tim:** We never do that.

[00:37:21] **Ben:** So, you know, some of it doesn't require as much deep thinking, but,it's just really funny. I actually think I've I over the holidays, I reached a sort of a terminal velocity. Of podcasts that I can listen to. I actually, for the first time, in a really long time, I had to start actively deleting podcasts just based on title.

[00:37:42] **Ben:** I like they were getting too far backed up. I'm like I'm never listened to this. I'm never gonna listen to this. I'm never gonna listen to this. And, now I finally unsubscribed from a few

[00:37:49] **Tim:** You're like working code pod. What's this click

[00:37:53] **Adam:** My code already works.

[00:37:54] **Tim:** about tests

[00:37:57] **Adam:** Yeah.

[00:38:00] **Tim:** I need to send these in the hub because in the, M model view view model in the VM is a pain in the butt, and I'm glad that he agrees with that. So, yeah. Woo.

[00:38:11] **Adam:** Yeah. I don't think I know anybody that did that doesn't have scars from it in

[00:38:16] **Carol:** hurts so bad. The cuts they're deep. So

[00:38:20] **Adam:** Cool. I also liked his comment about, just, and we've briefly touched on this before, but like the number of programmers in the world doubles every five to 10 years. So

[00:38:27] **Adam:** like half of programmers have never heard of stuff that started or before 20 15, 20 15 seems like not that, I mean, it was not that

[00:38:37] **Ben:** right.

[00:38:39] **Adam:** That was the year before Trump got elected. Like,

[00:38:41] **Tim:** does that mean in a hundred years? Like 80% of the population will be programmers, but I don't know the math on that.

[00:38:47] **Adam:** yeah. I mean, I think probably by the math, it's an exponential growth probably by then everybody on the planet will be a programmer and half of all people in wounds.

[00:39:00] **Carol:** no, there'll be no programmers. It'll all be AI should be writing itself.

[00:39:06] **Tim:** Yep.

[00:39:06] **Carol:** Self writing stuff, writing code.

## [00:39:08] 10X Developers

[00:39:08] **Adam:** So 10 X developers. We said we were going to talk about this. yeah, so it kind of came up in this, this Twitter thread that was shared in our, discord. And it was like a thread full of advice, the whole, I mean, it was this whole thing. there was a bunch of advice given by, a former engineering manager.

[00:39:29] **Adam:** I don't want to get into it, but one of the things in that thread was, that 10 X developers are real. and, yeah, and so it just sort of reignited that, that argument

[00:39:38] **Tim:** I mean, is that a t-shirt size or

[00:39:40] **Adam:** only immediately following, Thanksgiving and.

[00:39:43] **Tim:** all right. I kind of feeling like that right now.

[00:39:45] **Ben:** but a 10 act developer, I believe the concept is that there are developers that are 10 times more productive than other developers.

[00:39:53] **Carol:** Like naturally, right. Just, they're

[00:39:55] **Carol:** just

[00:39:55] **Carol:** good at

[00:39:56] **Adam:** have a proclivity. and I think that it's a very loaded discussion, right? There's people that consider themselves to be awesome. And so they call themselves 10 X developers. and I think that in some ways it can be used as like gatekeeping to tell people that they're terrible or whatever, to make people feel bad.

[00:40:11] **Adam:** And of course that's bad. but at the same time, this is all actually based on more than one, like several scientific studies, and part of the part of what makes this. Not well understood is that the nuance gets lost here. The difference, it's not that there are people that are 10 times better than the average developer.

[00:40:30] **Adam:** It's that the difference between the absolute best developers that were studied and the absolute worst was about 10 X. And the things that they were measuring were like, time to debug a problem sort of thing. And so 10 times the amount of time versus like the worst people took 10 times longer than the best people sort of thing. And I mean, that totally sounds reasonable, right? There's going to be people that are, there's going to be a bell curve. And the people at the, all it's saying is that the distance between the low end and the high end of the bell curve is about 10 X.

[00:41:04] **Tim:** I mean, is that different than any other field?

[00:41:08] **Adam:** No, And, I mean, so I think part of what, made the discussion interesting in Discord was that, bundled in with that advice. And like, in some of the articles, the blog posts that you'll find about it, some people will say things like, okay, so 10 X developers are real. And if you can get them, that would obviously sort of like by definition, be better than not getting them.

[00:41:30] **Adam:** So you should try to get them, on your team or hire them, whatever. And you will hear arguments like, wouldn't, you rather have one Isaac Newton rather than 10, average developers. And, I mean, even that I think like, I think I might given the choice. I might take 10 average developers

[00:41:51] **Ben:** Well, no one wants to work with the jerk. Right? So, so a lot of times the 10 X developer concept is sort of co located with this idea of the jerk developer, who thinks that they're better than everybody else. And like, doesn't want to deal with other people. And doesn't, why do I have a product manager?

[00:42:09] **Ben:** Like that's stupid. I could just rock this out myself. Like nobody wants to deal with that kind of person, regardless of how good they are. but I do think that there are people who are really good at their jobs who are also just terribly nice people and great to get along with and work really well with team.

[00:42:24] **Tim:** Yeah, we had one like that and his development skills. I see development skills like programming code and fixing bugs and diagnosing problems as a developer. I think in my mind, what is more valuable is the person who is very good at architecting, a complete system from scratch.

[00:42:42] **Tim:** Right. They can take it, you can give them an idea and they can architect a complete system. And then once it's,basically a prototype and flushed out, now those other developers can go in and they know where things are. It makes sense. Everything flows together, that kind of person, I think they're definitely worth.

[00:43:01] **Tim:** Cause we had one on our team and he was amazing. He built structures that we kind of go and still look at the day go, well, how did he build that? Okay, let me kind of copy what he did. that was pretty amazing. and the other developers are better for it because they're now working in a system that makes sense rather than a ball of mud.

[00:43:19] **Tim:** so I don't, when I think today to next developers, just single contributors who all they're doing is just working on a code set. Maybe some are better than others. I don't know the factor is there, but I think to me, what's the most valuable is who's architecting the system from the beginning to create the ecosphere that you're going to be working in, because we all know that once it's architected, it's very hard to rearchitect it again.

[00:43:44] **Tim:** So you've got to do that very well. At least the first time.

[00:43:48] **Ben:** And I think the comment that you're making about an individual contributor versus an architect. Makes me also think about the difference between an individual contributor and a, an a team culture that is conducive towards productivity, because I'm sure that many of us have worked with the person who can just jam out code really fast, but then you're the one supporting it for the next five years.

[00:44:12] **Ben:** And it's like the junkiest code. They just happened to, rip it out in a weekend. but I think when I think of productivity, it's not just about an individual, it's about how the team works and what the team's priorities are. And you have to create an environment in which people can really flex their creativity and flex their productivity and get into their states of flow.

[00:44:34] **Ben:** and if you're not in a good environment, I feel like no matter how productive you are naturally, that's going to be hampered to the point where, probably drive you crazy.

[00:44:44] **Adam:** yeah. Yeah. I mean, there's a whole lot more to being a good developer than being able to implement what it says in the spec and, to pull the team together to help define that vision, to think around corners before they're visible. these are all really important skills to develop.

## [00:45:03] Managing Productivity Between Developers

[00:45:03] **Carol:** I also struggle with when managers are comparing developers to each other. So when they ask were work to be done and they go, okay, what's going to take you a day to do this. But if I go ask this to next developer, it's only going to take them an hour to get this done. So why can't you, why can't you work at that level?

[00:45:21] **Carol:** Like, why aren't you good enough? And it, it does start pitting you against each other so they can cause problems in that way, if it's not managed correctly.

[00:45:29] **Adam:** So I don't have a whole lot of management experience. And I think that you at least have a bunch of team lead experience, if not better than that. Carol, just my recollection of your

[00:45:37] **Adam:** experience. How, if you have any thoughts or experience in this situation, how would somebody better handle that situation if they were that manager?

[00:45:48] **Carol:** Oh, so we've had the personally been involved with those issues before where we pad, requests come in for big development work to be done. And I put out a quote for my team to do the work and it comes back down and says, Hey, we talked to someone else on the other team who is a great engineer.

[00:46:05] **Carol:** And he says, oh, without any knowledge of what's going on, he could do it in half the time. So then my response back to upper management is take it off my team and go put it on his team. Then like fine. If he can get it done faster, that's why I'm telling you my team. Can't get it done any faster. That's it.

[00:46:21] **Carol:** Like I gave you what I gave you based off of what I researched. I did all the legwork for the specs. Like I'm telling you, this is what we would. And nine times out of 10, when they go back and relook or the other developer gets brought in, it's nothing was communicated fully. They didn't have full specs.

[00:46:38] **Carol:** It was, Hey, how about how long just guessed would it take you to do this? And they're like, oh, you know about a week. And I'm like, yeah, it's going to take about six weeks because QA testing is going to take two

[00:46:48] **Carol:** weeks on this.

[00:46:49] **Adam:** yeah,

[00:46:50] **Carol:** yeah.

[00:46:51] **Adam:** yeah. Do they just don't fully understand what they're being asked or they gave that the classic optimistic. Oh yeah. a week.

[00:46:58] **Carol:** and maybe something else, but I pushed back that's my approach has pushed back and I don't usually get walked on. So.

[00:47:07] **Adam:** Yeah. You're not the type of person to let anybody walk.

[00:47:10] **Carol:** Not usually. I mean, there are times I don't have a choice, like not walk on me, but there are times that we just have to bite the bullet and go look commitments were made outside of what we know, and we're going to do our best to achieve it. But there's a good there's knowledge up front that the deadlines you're asking for aren't doable bias.

[00:47:27] **Carol:** And I just want everyone to know that it might not happen. And as long as we communicate upfront, I feel better about missing deadlines than not up then not saying it.

[00:47:37] **Ben:** This is totally random, but it.

[00:47:39] **Ben:** just popped into my mind when you were talking about putting stuff on the other team. I don't know why the very non-sequitur, but there's this guy he's used to being in the node world. I don't think he actually does it anymore. This guy, TJ Halloween, Chuck,

[00:47:51] **Ben:** who he created express.

[00:47:53] **Ben:** He created like all of the super popular node libraries back in the day. And, Unbelievably productive human being. And I remember reading a thread somewhere where someone was actually theorizing that he wasn't a real person, that he was actually a group of developers. They were purposefully trying to portray themselves as an individual to be seen as super productive, but just the amount of stuff

[00:48:17] **Adam:** colluding so that they can all claim to be him and,all get the rewards of being thought to be him.

[00:48:23] **Carol:** That's pretty sunny. Yeah.

## [00:48:25] Defining Productivity

[00:48:25] **Ben:** I feel like team culture is people always talk about team culture as being so important, but I always feel like there's so many little details that don't get discussed in terms of productivity. one of the things that popped in my head as we're talking here was the whole, Two-way doors concept that I think Jeff Bezos made very popular.

[00:48:42] **Ben:** And, th the idea for people who haven't heard of this is that there are decisions. There are doorways that you can walk through. And if you can walk back out the other way, then it's not a decision that you have to make very heavily, whereas like a door that you walk through and you can never open it again.

[00:48:56] **Ben:** Like you actually have to do a lot of planning upfront because you don't get to undo that decision. There, teams that, that have this concept of two-way doors and bias towards action and incremental builds. And I w I don't know where I'm going with the soft, but I think part of what makes someone productive.

[00:49:17] **Ben:** They have a lot of experience. They sort of have a sense of what decisions they can make, what decisions they can't make on their own, what things actually need team to help with, and then understanding what happens if they make a mistake and then they have to be working on a team. That's okay with all of that stuff happening.

[00:49:33] **Ben:** And there have to be working in a company where, individual contributors might be allowed to make more independent decisions and have a certain amount of autonomy and freedom and, be able to collaborate with people maybe outside of their team to shape the product And to in order to be productive.

[00:49:47] **Ben:** I feel like you have to have not just instincts about programming. You have to have instincts about how to work with your team and work with your company and when it's okay to make mistakes. And when it's not okay to make mistakes, like it's not just how fast can I write code? If anything, how fast can I write code is like the smallest part of what it takes to be super, super productive.

[00:50:07] **Tim:** And I'd say, be careful, who's the one that's defining what productivity is. Right. some people are like, number of tickets done, number of bugs, fixed, how quickly they were determined around meet, meeting a deadline that, someone set in a certain period of time is that productivity.

[00:50:22] **Tim:** I've seen some people that take really long time in my opinion to do something. But when they do it, it's rock solid. And there's others who are really fast. And when they do it, you know that you're going to be cleaning up stuff for the next few weeks. So how do you define productivity?

[00:50:37] **Tim:** Sure. Are they 10 X, whatever. But if you're the one labeling yourself to next, you need to go to another room and find someone smarter than you. Cause a hubris is on its way.

[00:50:50] **Adam:** Yeah, go let some air out of your head.

[00:50:52] **Tim:** Exactly.

## [00:50:53] Patreon

[00:50:53] **Adam:** Okay. This episode of Working Code is brought to you by 10 X podcasters. If you know, you know,and listeners like you, if you like what we're doing here, you might want to consider supporting us on Patreon at patreon.com/WorkingCodePod. If you are like living under a rock and you don't know what Patreon is, it's basically a way for you to vote for the things that you would like to continue to.

[00:51:15] **Adam:** And you vote by giving your money to those things. you can support us for as little as $4 a month, and all of our patrons get access to our after show, which is just more of us rambling on about random, whatever an early access to new episodes, as soon as they're ready. we really appreciate all of our patrons, but our biggest things go out to our top patrons money and Peter,

## [00:51:33] Thanks For Listening!

[00:51:33] **Adam:** but you know, what if patronizing podcasts, isn't your thing.

[00:51:36] **Adam:** That's totally cool too. We appreciate just that you took the time to listen. If you enjoyed this episode, please share it with your, coworkers and with your friends, and your grandma to listeners or listeners.

[00:51:45] **Adam:** it would really help us out if you could leave us a rating and a review on apple podcasts or wherever you get your podcast. please send us your questions and show topics on Twitter or Instagram @WorkingCodePod, or you can join our Discord and share your ideas there.

[00:52:00] **Adam:** and just like Nathan, you can record a voice memo on your phone and email it to us@workingcodepodatgmail.com. we'll catch you next week. And until then

[00:52:09] **Tim:** So remember guys today, actually we're recording it's January 6th and, it is the one-year anniversary of when the catchphrase, your heart matters, came up in response to. Traumatic day that we had last year, January 6th,

[00:52:25] **Adam:** I forgot about that.

[00:52:27] **Tim:** which side of the aisle you're on, you have to say that was quite something after going through one year of pandemic and then to see what happened at the Capitol.

[00:52:36] **Tim:** And now here we are in year two of the pandemic. I think it's safe to say that every one of us are very much underestimating the amount of stress that our lives have been under these past two years. So just remember your heart matters.

[00:52:51] **Carol:** Yup.

[00:52:51] **Adam:** we're wrapping up a second full year of pandemic started March of 2020.

[00:52:56] **Adam:** Yeah.

[00:52:56] **Ben:** bananas.

[00:52:57] **Adam:** All right. Love you guys. And, we're going to go to the after show.

[00:53:00]

## [00:53:00] Bloopers

[00:53:00] **Tim:** it's an Anon, it's a Lambda. It's at a nominal, a non.

[00:53:24] **Adam:** Words are hard

[00:53:26] **Adam:** bloopers.
