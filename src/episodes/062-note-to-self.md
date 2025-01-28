---
title: "062: Note To Self"
description: "This week on the show, the crew peers into the deep, dark recesses of Ben's mind and tries to understand what exactly makes him tick."
date: 2022-02-16
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/062-note-to-self/id1544142288?i=1000551271147"></iframe>

Sponsors

- [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

This week on the show, the crew peers into the deep, dark recesses of Ben's mind and tries to understand what exactly makes him tick. Composed of equal parts rant and dialogue, the topics range from throwing errors on delete operations, handling bulk operations idempotently, feeling guilty about using backup cameras, keeping large task backlogs, reprioritizing tasks on-the-fly, transpiling JavaScript to ES5 for legacy browsers, the benefits and drawbacks of a robust QA (Quality Assurance) phase, and the cargo culting of `let` and `const` in the greater JavaScript community.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/062-note-to-self.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Tim:** Note to self. Sure. To love there. Let and const love. Ben

## [00:00:31] Intro

[00:00:31] **Adam:** Here we go. It is show number 62 and on today's show, we're going to talk to Ben's inner monologue. Uh, um, he has this habit of leaving notes for himself in our private channel and discord. And so we're just going to go through those. to Ben about his notes to himself. but first as usual, we are going to start with our triumphs and fails and as luck would have it, Ben, you are first. What do you got going on, man?

## [00:00:58] Ben's Triumph

[00:00:58] **Ben:** I'm going to kick it off for the triumph. And that is that I went from a initial thought an idea for a feature in the product to a deployed MVP in front of users in two days. And, that two days of development included like 10 different deploys. If I have to shade, just how much I lean into feature flags and incremental development and small iterations.

[00:01:23] **Ben:** And, I was just really excited to be able to get it done. And, I'm,

[00:01:25] **Adam:** Yeah, you don't have to feel bad that it took you two whole days, man.

[00:01:30] **Ben:** I'm definitely leaning hard into. Ask for forgiveness. Don't ask for permission mode at work, as I've said, many times in the past, the only person left on the legacy platform, I'm basically unsupervised. So anytime I see a ticket that addresses a user friction, I'm just like, yeah, I'll do that. And, I'm just having a good time doing it.

[00:01:52] **Ben:** So pretty excited.

[00:01:54] **Tim:** Nice. Now these just are they MVPs within a already existing structure is like a completely separate thing on its own.

[00:02:02] **Ben:** this is all, added to the existing application that the users are currently engaged with. Although increasingly fewer users as they move over to the new platform,

[00:02:12] **Carol:** That's a that's really good. Cause a few weeks back, you were kind of a little bummed out by how things were going. So it's good to hear positive.

[00:02:20] **Ben:** year's blues, but,I'm just kicking it hardcore now. And, uh,you know, it is, I, they're predicting. I think I can say this. They're predicting that the migration from the old platform to the new platform will be done by the end of the year. So the way I look at it that because we know they're under 11 months to try and remove friction and add some value for the users that are still there.

[00:02:41] **Ben:** And,there's no bar, of number of users where I'm going to stop caring. That's sort of my mentality right now and I'm just going to keep pushing what I can push.

[00:02:50] **Adam:** So when we talked about feature flags originally, and I think also when we talked about, like poll request, velocity, both sort of prior episodes, I was struggling to wrap my head around. a good reason for why you would want to deploy unfinished code behind a feature flag.

[00:03:07] **Adam:** And I never really came up with a good reason. I just kind of accepted it as like, okay, well, it seems to work for you and that's fine. but I was kind of reading and learning the other day and I can remind myself of, continuous integration and continuous deployment and one of the aspects of continuous integration that really click in my head until that moment, like earlier this week was that as you're continuously merging your changes back into, let's just call it the main brain.

[00:03:35] **Adam:** Your tests are going with it now, obviously not your tests, but hypothetical Ben, who writes tests, his tests are going into. So the benefit then becomes that even though your features are incomplete, if somebody were to break something that you're in the middle of working on, right, then your tests will start to fail for them.

[00:04:00] **Adam:** I think that was like a big light bulb, like moment for me.

[00:04:04] **Ben:** Yeah, sure. I can definitely see that I have, uh, which is the one where it's like you feel for the person, even though you don't actually experience it yourself.

[00:04:12] **Adam:** Yeah. Empathy.

[00:04:13] **Ben:** I have empathy for your test driven development benefits. I mean, just to, I can give you a very practical example. So the feature that I was working on has to do with changing or slightly changing permissions model.

[00:04:24] **Ben:** And part of the complexity of dealing with the application is that it's a spa, a single page application, which means that at any point. user's browser has code open that may have been loaded for a day or for several days. And then it's going to be interacting with servers that are being deployed continuously behind the scenes.

[00:04:45] **Ben:** So you get that sort of drift between what the client expects and what the server expects, and then when you're deploying code. And if that deployment is going to a horizontally scaled servers, then at any one moment during that deploy, some servers have the new code and some servers have the old code and the browser because of round robining and the load balancer might hit the old servers.

[00:05:11] **Ben:** It might hit the new servers. So one of the things that I had to do in this feature was I wanted to change the structure of a permissions model that was being returned in an API response. So this API response had a bunch of data, and then it has a little side object that says, and here's the things you can do with that data, just to help me render that.

[00:05:31] **Ben:** So I didn't want to change both the server side code and the client side consuming code at the same time, because there'd be a chance that someone would refresh their browser, adjust the wrong moment, get the new client side code that expected a new structure, but then be making an API request to the old server.

[00:05:51] **Ben:** that was not yet returning that structure. So instead of doing them both at the same time, our deployed just the changes to the server side, make sure that's rolled out and then deploy the changes to the client's side, to make sure that any refresh browser is hitting a server that has the most up-to-date code and coordinating that it doesn't always have to be done behind a feature flag.

[00:06:13] **Ben:** If your change is completely additive, then it doesn't have to be behind a feature flag, unless you want the ability to quote unquote roll back, using the feature flag, but that's just to illustrate the small deploys and the incremental.

[00:06:26] **Adam:** Yeah, I don't quite follow how that helps with drift, right? Like the, how the incremental deploys helps with drift, but that's okay. We don't have to get into that

[00:06:35] **Ben:** Yeah, no worries. It's the client side and the server side code are all in the same repository and they all go out with the same deploys. So I can't, choose to deploy just the server side code.

[00:06:46] **Adam:** Right, but the, I guess maybe I misunderstood you. So the drift that I was thinking of was somebody keeps their browser window open for a week and never leaves the tab. Right. So they're not getting new client code.

[00:06:57] **Ben:** Right. So, so that's, that person's probably okay. the issue is that in the middle of the deployment, what if a user refreshes their browser and the request that serves up their client side code is the new code, which is expecting a new structure on the server, but then the API requests, they make substance.

[00:07:17] **Ben:** Still mid deploy, hit an old server that hasn't yet been updated. So now they have new code. That's expecting new structure, but they're getting old structure.

[00:07:25] **Adam:** goodness,

[00:07:26] **Ben:** Yeah. it's,

[00:07:27] **Adam:** that's a mind bender.

[00:07:28] **Ben:** it's, it's definitely something it's, it's an edge case. it doesn't always happen. It depends on the volume of the traffic for the particular feature.

[00:07:35] **Ben:** And I'll tell you, to be honest, sometimes I will deploy stuff in a, in an edgy case area of the application that I know doesn't get a lot of usage. And I just be like, you know what, there's a chance that in the few minutes that this is deploying, if someone were to refresh their page at the wrong time, they're going to get an error.

[00:07:51] **Ben:** And I'm like, I'm just going to eat that cost because I don't want to have to do two deploys.

[00:07:56] **Carol:** See, we just do after hours appointments in those cases. So if we feel like it could have any impact, we just pull it to an after hours deployment rather than splitting it up.

[00:08:06] **Ben:** Yeah. it's all, a trailer.

[00:08:08] **Carol:** Yeah.

[00:08:08] **Ben:** It all depends on how important the part of the application

[00:08:11] **Tim:** Except for that one use in Australia.

[00:08:16] **Ben:** Anyway. So that's my triumph. What about you, Adam? When you got.

## [00:08:19] Adam's Fail

[00:08:19] **Adam:** so I'm on call this week and, sometime. software fails and it's not my fault that it fails, but when it fails,let me be less abstract and more concrete. I'm on call this week. And, sometimes there were alerts that were coming to me, but I wasn't getting any alert sounds. I would get the notification.

[00:08:38] **Adam:** It would pop up on my phone if I happen to be looking at my phone, but it wouldn't make any sound. My, my phone was not on, do not disturb. My volume is all the way up, blah, blah, blah. And because I didn't respond to these alerts, they were escalating to some of my coworkers and I felt like a total because it's, there is their week to not be on, on call rotation. Right. And so I feel like a when I a, an alert happens and it escalates beyond me. when I should have caught it. And fortunately, I was having a little bit of a rough week and I was spending some time pairing with a couple of my coworkers and alerts were happening while I was on video chat with them.

[00:09:18] **Adam:** And like, I heard the alert go off on their phone and I was like, wait a minute, I'm the one on call? Why did you get that? And, and so we went to talking about it and that's when I realized, like, something's messed up with the software. I like reinstalled the app on my phone and started messing with notifications.

[00:09:32] **Adam:** Couldn't get it working. So now I have it on my iPad as well as my phone. And of course, now that I set it up on the iPad too, so that, I don't get, I don't miss any. Now when alarms go off, they go off on both and I have to deal with it on both. But yeah, so it's just, it's a little bit of a rough week softwares failing me and making me look bad when I'm, you know, I'm not

[00:09:53] **Carol:** It's not even your software.

[00:09:54] **Adam:** Yeah. It's not my software. I'm not doing anything wrong. It's just, I feel that. I'm not living up to my, the standard I set for myself

[00:10:02] **Ben:** No, I hear you. I, my team that almost never gets paged, like maybe once every two years we get page,

[00:10:12] **Adam:** Yeah. I mean, you're talking about a longer term thing, but yet when you say my team now, you mean

[00:10:16] **Carol:** And assist you.

[00:10:18] **Ben:** well, this is even back when there was a handful of like four people on the team we never, ever got paged because there was really no active development that was pushing the boundaries of anything. it was kind of the application was in a stable known state. and I have a reminder on my phone that goes off at nine 30 and it reminds me to turn my volume on and make sure that my PagerDuty app is.

[00:10:41] **Ben:** So I'll open a PagerDuty app and I swipe down just to make sure that it gets a status update. I'm like, okay, I can go to sleep. And I, for whatever reason forgot to do at one night, a couple of months ago. And of course that was the night the server crashed. And not only did I not get the page, but none of the engineers on my team got the page.

[00:10:59] **Ben:** It went all the way up to the engineering

[00:11:01] **Carol:** Oh, no.

[00:11:03] **Tim:** Um,

[00:11:03] **Adam:** Was that the,

[00:11:04] **Adam:** was that the, like the Thanksgiving one that we talked about recently?

[00:11:07] **Ben:** No, no,this I guess was like a year ago,

[00:11:10] **Carol:** I will say. One of my coworkers messaged me the other day and said that he had just finished the episode where, you drop some F-bombs and told me to send you hugs because man, that sounded rough,

[00:11:23] **Ben:** No, it was good times now in retrospect.

[00:11:27] **Carol:** And if you have the urge to rewrite any angular JS code, he has a job for you.

[00:11:34] **Adam:** Oh, I guess I'm not living up to my job here. My task is to throw it over to Tim. That was my failure. And second failure to keep the ball rolling. What's what's going on for you?

## [00:11:48] Tim's Triumph

[00:11:48] **Tim:** so I'm going for triumph. I mean, I had an extremely productive week. I mean, just really just it's Thursday today, we're recording. And just the everyday is just like, has been revelation after revelation. just getting a lot of stuff, done, stuff that I've been avoiding. but just finally tackled it and then just there's some, there's a lot of times in software and the software we do is like, it's not necessarily stuff you're building.

[00:12:10] **Tim:** It's like getting a partnership with a certain provider that can, they're the only ones who have this type of information or data or this API and it's all financial stuff. So there's all this due diligence and the security it's like it takes forever. I mean, I've been working on some of this stuff. 14, 15 months. It's like everything this week is just kind of lined up in, just kind of fell in place. And then we had some customers that are prospects that,that we thought we had lost and they came back like the same week and they were asking for the exact same thing that we just finally figured out and got it solved.

[00:12:43] **Tim:** And so I just felt like everything came together this week and just, I dunno, it's like the cards fell in place sometimes you're the kicker. And sometimes you're the ball this time. I was this week. I was the kicker man and it felt good.

[00:12:56] **Adam:** Everything's coming up, Millhouse.

[00:12:58] **Tim:** Yeah, man. just, it just feels good to move stuff forward.

[00:13:01] **Tim:** Cause sometimes it's like, you got, this is Boulder that you just constantly pushing up the hill, constantly pushing up the hill and it's like, this will never get done. And then you get in friction internally from the company. Cause why is this taking so long? Well, you know, what if legal got out of my way and finance got out of my way and all these other regulatory crap, if they just get out of my way, that the problem is not the technology, we built the technology, the problem is the relationships, the contracts and all this other stuff that is totally outside my expertise.

[00:13:30] **Tim:** And I even if it were my expertise, it's not something I want to do. I'm not interested in that. I really don't care about that stuff. I want you to take care of it. And it just felt like that Boulder got to the top of the hill and now it's like, I'm running now I'm having to run to catch up with it.

[00:13:44] **Tim:** Right. Cause it's getting ahead of me. So it's an exciting feeling.

[00:13:48] **Carol:** Yeah. There's nothing like the finish line. The finish line is the

[00:13:51] **Tim:** why isn't the finish line? Isn't not the finish line, but it's like, it's finally there's is less friction now. Right? This is forward progress rather than just a constant battle for me

[00:14:01] **Tim:** to kindly just battle to get this thing going.

[00:14:04] **Tim:** So

[00:14:05] **Carol:** well, I hope you find the finish line soon then.

[00:14:07] **Tim:** it's insight. And so

[00:14:09] **Carol:** Good,

[00:14:09] **Tim:** how about.

## [00:14:10] Carol's Triumph

[00:14:10] **Carol:** I'm going to go with the triumph. So a few weeks back, we started this new sprint/cycle process for how we eat. And at first, there were just all of these big unknowns. We didn't really fully understand what we were doing, but you know, we're a team players.

[00:14:29] **Carol:** We're like, let's go try this and figure out what we got to do to make this work. So going into it, there's just a lot of downtime and none of us liked downtime, but you can't go pick up anything from the backlog because you should really be researching cycle work. So it's just, it's been a huge adjustment and I haven't fallen apart and we haven't went completely crazy because none of us like change.

[00:14:51] **Carol:** We are like, my team is, are we're creatures of habit. This is what we do. Right. We're really set in how we do things. And we, like, we just moved the same way every day. So to pull half the team off of sprint work and put them on a cycle, oh, and the cycle lasts eight weeks. It's not just a couple of weeks here.

[00:15:10] **Carol:** And then you go back to the team it's you're on cycle work for eight weeks. So it's a whole new way of doing things. And it's just been an adjustment, but. It's actually being accepted really well and going over pretty smooth, I think.

[00:15:23] **Adam:** When you say it's being accepted well by the developers, by the managers

[00:15:27] **Carol:** so all the other teams, all the other engineering teams were already doing this.

[00:15:31] **Carol:** We were just the only, only piece in the organization that wasn't, so they're like, Hey, we need you to align with some of our cycles because now your work is impacting our work and we need everything to go out together. So we're going to need to steps and things like this. So. Yeah. It's being accepted very well by our engineer.

[00:15:51] **Carol:** So, yeah. And they're doing good with us. They're being very helpful and understanding that we don't know what we're doing. So me and my pair programming buddy, we kinda got in trouble today. I'm going to air quote in trouble. We didn't get in trouble. We went to the first tech review and had already coded the entire project.

[00:16:11] **Carol:** And they're like, oh, this is the initial review. Next time don't code it yet. Go ahead. And let's do the review and write all the documentation and get everything before you code it. I was like, oh, we already have the PRS out. I'm sorry. They're like, no, you're learning. It's fine. I'm like, nobody told us not to code.

[00:16:30] **Carol:** So

[00:16:30] **Ben:** It's research you're researching.

[00:16:32] **Carol:** Yeah.

[00:16:33] **Tim:** guys write the documentation prior to.

[00:16:35] **Carol:** Yeah, we write the document. So we have a tear sheet review, which is kind of the business requirements. It's it just lays out what their problem is and what they think might be some helpful solutions. Like we don't have to use their solutions. It's just, here's the problem. Maybe this will help you in coming up with a design, then we take the tear sheet and we write that into a technical document.

[00:16:55] **Carol:** So the technical document has everything laid out for how it's going to impact the system, what changes we're going to make in the database, what the new structure's going to look like. And along with questions that we just don't know answers to, and that we need business input from, so then we're supposed to go back.

[00:17:10] **Carol:** Well, we didn't have any questions, so we just did it. So

[00:17:14] **Tim:** So it's not really, it's not user documentation.

[00:17:16] **Carol:** no, it's all technical documentation. It's just to lay out the changes and so that we can get back together as a group and go over the new structure.

[00:17:24] **Adam:** kinda like a project plan.

[00:17:26] **Tim:** Yeah.

[00:17:26] **Carol:** yeah, I'm loving it though. So eight weeks is going to be a long time though.

[00:17:32] **Ben:** As far as the problem that this is solving is it just an issue of getting all the teams deploying at the same time?

[00:17:38] **Carol:** no. So we actually won't be deploying at the same time. We will still be deploying as we get done with the work. So the deployments and releases, aren't tied together with the cycle. It's just that, like, we have another organization that's created this API that we're hooked up to you. So we now have to change authentication in order to actually get to that.

[00:17:59] **Carol:** And because we're not in their cycle process, it was just kind of their backlog. So we have like a few things that are overlapping with each other, and it was just to get those overlapping projects to the end point at the same time. So they'll be holding some of their stuff waiting on hours, or there'll be times where we finish, but hold, waiting on theirs to get done. So

[00:18:17] **Ben:** processes, such a hard thing. I'm not against process. I know process has its place, but I'm definitely all over the place. Sometimes. I remember I had an engineering manager a while back and he desperately wanted to use burn down charts, which are, I guess, charts that show you.

[00:18:35] **Carol:** We're running out of time.

[00:18:36] **Ben:** Yeah, something like that. But in every sprint I would complete like 11 tickets and create like 27 new tickets for myself. So the burn down charts were just like horizontal lines and he was like, please stop creating tickets. And I'm like, but I have ideas.

[00:18:55] **Tim:** oh,

[00:18:56] **Carol:** you're burndown chart should really only be what's in the sprint. Like as far as that goes, like your burndown chart should say, okay, here's my. Here's what manpower we have to do the sprint. And now I need to see that we are finishing the work with the resources that we have. So you shouldn't be adding to the sprint

[00:19:13] **Tim:** that's it goes in the backlog,

[00:19:15] **Carol:** Nice. The backlog.

[00:19:16] **Tim:** you can work it while it's in the backlog. Just don't tell anybody.

[00:19:19] **Carol:** Just don't put it in the sprint bucket then nobody knows.

[00:19:21] **Ben:** so hard. I have such a fear of the backlog. The backlog to me, feels like a place that stuff goes to die. part of my problem is I don't know how to use JIRA, very effective. And sometimes it's literally just, I don't know how to get to the backlog. And then I think there's like different forms of backlogs for the different types of boards or something.

[00:19:40] **Ben:** And then some things are projects and some things are boards. I'm very confused by the flexibility and the robustness of JIRA. So I ended up just using my to-do column as my personal backlog. So all of my new tickets go right into the

[00:19:54] **Ben:** dues, which I think is part of the problem.

[00:19:57] **Tim:** Yeah, I dunno. That's kind of your viewpoint. It's like to, to a business where you're charging money for doing the work backlog is like future money. That's all it is

[00:20:08] **Tim:** that's that's future professional services. that's like your piggy bank.

[00:20:11] **Carol:** Yeah. It's not your support ticket. It's not your combat board. It is the, what we got that we can do. That's development, new.

[00:20:19] **Tim:** Yep.

[00:20:20] **Ben:** That makes sense. we do a product, so it's not like. There's no explicit monetary value attached to any particular ticket. it's more the overall value proposition for the product itself.

[00:20:31] **Tim:** Gotcha.

[00:20:32] **Carol:** I love that we all do the same things, but do it so differently. And yeah, it's just great.

[00:20:38]

## [00:20:39] Audible

[00:20:39]

[00:21:01] **Adam:**

## [00:21:01] Throw An Error On Non-Existant Delete?

[00:21:01] **Adam:** Note to self, to throw or not to throw an error. When a delete operation is requested for something that doesn't exist quietly, exit defer idempotency to a higher level in the call stack don't know,

[00:21:19] **Carol:** Love then.

[00:21:23] **Adam:** oh, this is going to be good. I like this

[00:21:24] **Ben:** so good.so, so this is a thought that I ha I've been having a lot lately as I've one been refactoring the, my blogging platform. And also just as I've been trying to modernize some of the legacy platform at work and the idea here. A user makes a request to delete a record or to end the relationship between a record or to do something that's usually some sort of, yeah,

[00:21:48] **Adam:** We need to

[00:21:49] **Adam:** talk.

[00:21:51] **Ben:** and I'm gripped with, let's say I need to delete a record by an ID.

[00:21:56] **Ben:** Do I need to, in my low-level service, make a request to the database to get that record by ID first, to make sure that it exists. And then if it doesn't say like, Hey, you asked me to delete this thing and it doesn't exist. So here's a big juicy error. Or do I just quietly say, oh, that thing must not exist.

[00:22:15] **Ben:** So maybe the user like click the submit button twice and the first one went through. Okay. So I'm just going to ignore the second one and just quietly pass by and return. Or, and this point about item potency, do I, as the low-level data access layer, throw an error and say, Hey, you asked me to delete this thing and it's not there.

[00:22:36] **Ben:** So Kablamo it explosion, and then leave something higher up in the stack and say, oh, this delete operation through a not found error. So I'm going to just ignore it at my level, the application where I can sort of massage some higher level business logic into the workflow,

[00:22:52] **Adam:** I can tell you that I never think about this problem unless I need to do something weird. Right? So 99.9, 9% of the time, I just write some SQL. It says delete from table where ID equals X. SQL is like, or, whatever database is just gonna be like, oh, that row doesn't exist. I'm just going to delete zero rows.

[00:23:12] **Adam:** Okay. Done.

[00:23:14] **Ben:** Yeah, totally. And as someone who always has the little performance monkey on his back, thinking about how is this code going to perform? Does the database query. The idea of pulling a record back, just to see if it exists before you then delete, it feels like, oh, that's wasted CPU cycles,

[00:23:32] **Carol:** dirty.

[00:23:33] **Ben:** but then I struggle with the idea of, yeah, but I'm mutating the system.

[00:23:38] **Ben:** And should the mutations of the system be where I'm worried so much about performance or should I really just be worried about performance on the, like the view rendering and the reeds and not, I don't care about throwing away clock cycles when I'm doing the crud operations.

[00:23:53] **Adam:** I know what I just said, but,

[00:23:58] **Carol:** I

[00:23:58] **Carol:** take it all

[00:23:59] **Adam:** I'm also coming from one of my applications is very heavy. ORM uses. And you can delete like using HQL or whatever. So you don't necessarily have to load the entity in order to delete it. If you happen to have it, you could just say, okay, delete this entity. And that's fine where I, that starts to become something where I have to make a decision is we audit log, like everything that you do.

[00:24:25] **Adam:** And so in addition to saying, Carol deleted,message 45. I also want to log, what will, what was the subject of that message? And maybe a few other bits of metadata about that message so that, if the record's gone. So instead of having to pull something, pull a database backup and restore it so that I know what message she deleted, I can go, oh, okay.

[00:24:46] **Adam:** that was, expect it to be deleted. So I don't have to worry about that. So I could see in that case needing to do a select for. In order to get the details so that you can audit log that you're about to delete that thing.

[00:25:00] **Ben:** That, that makes sense. And I think that's a pretty valid use case as well. I mean, I think people create audit logs in applications all the time. Yeah. It's something I just go back and forth on. It's so easy to just fire off a delete from,

[00:25:15] **Ben:** and it doesn't matter if it exists.

[00:25:17] **Tim:** I don't know. I'm kind of torn. I mean, the end result is the same, Right.

[00:25:21] **Tim:** So the result is I want this record gone. And for some reason you get multiple deletes and the first one got, there is a race condition or something that deleted it. Why thornier? And the second one, because now you've got to go figure it out.

[00:25:35] **Tim:** And you're like, well, it is deleted. why are we airing? But why do I have to bubble this up the stack?

[00:25:40] **Adam:** Well, I think my perspective on the way Ben explained it was that by throwing an error, you give the entire stack potentially until whatever layer catches it and ignores it, the opportunity to make a decision based on that event.

[00:25:56] **Adam:** Right.

[00:25:56] **Adam:** I can either let it continue to bubble. I can handle it or I can ignore it.

[00:25:59] **Tim:** so maybe you do a delete if you find out you deleted no rose. error. And then the next one goes, well, how did it. get deleted? Like if you've been the error logging in or something and then ignored if it's not a problem.

[00:26:13] **Adam:** All

[00:26:13] **Tim:** I, no, no, it's, it's, it's a good thought. It's a good

[00:26:16] **Ben:** interesting. And it's sort of like a slightly tangential. bulk operations are another thing where this feels like I don't have a good pattern of, I don't have an established pattern of how like do bulk operation, because let's say that you're submitting a request to delete 10 records, not just one record.

[00:26:35] **Ben:** And, say that in the middle of that bulk delete, there's some sort of a deadlock on the database and the request fails. And, let's say that the client retries or something, or those let's just say that the, we showed the user, Hey, this didn't work. Maybe you should try it again. So they click the submit again and they're submitting the same 10 IDs because they don't know what failed or what worked.

[00:26:55] **Ben:** So now it's, rerunning the same bulk operation and, five of them might work and five of them might reference IDs that no longer exist. and I feel like I don't want to ruin the bulk operation just because one of the things failed. I want to try and do as many things as pawn.

[00:27:10] **Carol:** so your bulk operation, isn't in a transaction, so it's not, if it fails, there's a full roll back. Okay.

[00:27:16] **Ben:** right, right, right. Yeah, exactly. and part of the reason I'm trying to shy away from high level transactions as much as possible, because I'd rather have someone get a partial success, as long as it doesn't leave the system. And in an inconsistent state, like deleting,if two records have to be deleted together, I'd wrap that in transaction.

[00:27:35] **Ben:** But if someone wants to do a bulk operation where they're doing essentially the same operation, but 10 times I'd kind of want to just let those play out individually. but then not to tangent one more time, but, and then it

[00:27:47] **Adam:** Well, I mean, why not?

[00:27:49] **Carol:** your

[00:27:49] **Ben:** then it becomes like in the middle of the operation, What if there are different types of errors.

[00:27:54] **Ben:** Okay. So there's the, I want to delete a record, but it doesn't exist. That's one type of issue. It's call it. But then there's the user asked to delete this one record, but they, from a security standpoint, don't have access to that record. And I'm like, do I treat that as not existing? Or do I just ignore it and let the rest of the bulk operation proceed?

[00:28:13] **Ben:** Or is this a special case where I say, actually, this is a totally different beast of a different color and you should get an error now because you're trying to do something illegal

[00:28:23] **Tim:** Oh one, no access, right?

[00:28:24] **Adam:** Oh, 4 0 1 would be, I don't know who you are. 4 0 3, not allowed.

[00:28:27] **Tim:** 4, 3, 4, 3.

[00:28:29] **Ben:** But then it begs the question, like why is someone performing a bulk operation where half the ideas they have access to and half they don't, but then it could be,

[00:28:36] **Carol:** but it could be malicious.

[00:28:37] **Ben:** It

[00:28:38] **Ben:** could be malicious, but it could also be again,

[00:28:41] **Adam:** I think

[00:28:42] **Ben:** Not to play edge case, bingo, but like what happens if, as the person was about to submit the form, another member of their team remove them from a project that owned one of the IDs that they're about to access. So like as the mouse button is going down, suddenly one of the ideas become invalid and I'm

[00:29:00] **Adam:** mission, impossible movie.

[00:29:02] **Carol:** Ben, your users. I don't like them anymore. No, I'm

[00:29:06] **Ben:** it's all just like theoretical thought experiments on handling any cases and when to throw errors. But anyway, this is the kind of stuff that becomes note to self.

[00:29:15] **Adam:** Okay. Speaking of.

[00:29:19] **Tim:** I got the next one

[00:29:20] **Carol:** All right.

## [00:29:21] Backup Camera Guilt

[00:29:21] **Tim:** note to self. Sometimes I feel guilty about using a backup camera. When parking is that something I see in other parts of my life, love Ben.

[00:29:36] **Carol:** Okay, please explain this. What is wrong with the backup camera?

[00:29:41] **Ben:** backup cameras are magical. They're

[00:29:43] **Carol:** They're the best they have lines and everything.

[00:29:46] **Ben:** God. It's the best. I and I think they're becoming mandatory or maybe,

[00:29:50] **Adam:** They already are in all new vehicles.

[00:29:51] **Ben:** yeah, so they're clearly a huge value add they're a safety feature. They're a convenience feature, et cetera. but part of me feels like, am I, is my, the muscle that is my ability to parallel park.

[00:30:06] **Ben:** is that starting to atrophy now that I'm using a camera, which it almost certainly is because I use my camera for everything. And, but then I wrestle with this. Is that a bad thing? Or is that a fear-based thing? Am I, it is the fact that I'm getting worse at something that I used to be better.

[00:30:25] **Ben:** Just a fear response or should I lean into the technology and embrace it as sort of a, an augmented sense of self?

[00:30:34] **Carol:** So when we back up the car, I am the one that looks at the camera. I very rarely look at my mirrors. It's only if I can't see something in the camera or my car beeps at me and I'm like, well, there's nothing on the camera. Why is it beeping? Steve is the one that puts his hand on the passenger seat and turns his head around backwards and looks in the mirrors.

[00:30:55] **Carol:** Yeah. Does it mean very rarely uses the camera, even though it's on, I could cover it up and he could still back up. You cover it up and unlike where's the camera. I don't know how so I fully think that it does. You start figuring out how to do things because you get so dependent on the technology. And I think for people who don't get dependent on technology, they're probably going to go further.

[00:31:17] **Carol:** If something happens in the rest of us,

[00:31:19] **Adam:** Yeah. It's like, tell me, the cell phone number of somebody that you met in the last five years.

[00:31:27] **Carol:** nobody tell him like, yeah, I was like, nobody's telling my kids this. Okay. I know one of their phone numbers and not the other.

[00:31:33] **Adam:** Oh,

[00:31:35] **Carol:** have the oldest one's memorized because he got his phone first. When the youngest got his, I never memorized it. So

[00:31:44] **Adam:** Yeah. And my oldest just got his first phone and phone number a couple, I guess. Yeah, his birthday. So couple months ago. And, I, yeah, I know that the first six digits of his phone number are the same as mine because they match. But the last for mono.

[00:31:59] **Carol:** you're in my favorites list. Hunt. It's fine.

[00:32:02] **Ben:** Yeah.

[00:32:03] **Ben:** I know my childhood phone number, my personal phone number and my wife's number. That's it.

[00:32:08] **Adam:** It's like, Hey Siri, call That's your phone number? And now the iPad starts to go off. Sorry.

[00:32:18] **Carol:** So do you see this in other parts of your life, other than the camera? What other parts do you see then?

[00:32:24] **Ben:** Well, I think about it in terms of a lot of technology stuff. I'm struggling to find a really relevant example, but

[00:32:32] **Tim:** I imagine if you use copilot, you'd

[00:32:34] **Carol:** Yes. I feel guilty. I was thinking that when you were, when I read this one, cause that hitting tab and just having it fill in the code for me, I'm like, oh yeah, that looks right next.

[00:32:47] **Ben:** well, exactly, and, we had talked about on previous episodes, the fact that a number of us are sort of old dinosaurs and we

[00:32:53] **Ben:** hearkened back some of us, I say, and we hearkened back to this time when there, there wasn't a dev ops team and there wasn't a database administrator, there was just you and maybe one or two other people, and you had to know the things and you had to know how to do the JavaScripts and the CSS.

[00:33:10] **Ben:** And then the. And now I don't know how to do anything platform related. I sort of barely understand how Docker works and these are all really amazing technologies that I work with. But there's this layer of abstraction that I feel that guilt is not the right word, but it's like, I feel intimidated because it reflects back on me.

[00:33:30] **Ben:** And how little I know about those things.

[00:33:32]

[00:33:33] **Tim:** with the backup camera. I do. Cause I have like, I'm a cheapskate. I have all my vehicles are old. My truck is from 1986, right?

[00:33:42] **Adam:** dude, your truck is almost older than me.

[00:33:45] **Tim:** Yeah. it's the same make and model that I learned to drive on when I was 15. it's like, so it doesn't have a backup camera. So none of my vehicles have backup cameras, but I use my wife's car and I used a backup camera. Like if I become, and it's like so awesome, like if I become dependent on this, I might forget how to do it in my truck.

[00:34:02] **Carol:** you will,

[00:34:03] **Tim:** Don't feel guilty about it, but it's like, like I can't, it was like, it's like a mad max, don't. Become dependent on the water.

[00:34:11] **Adam:** I bet you, there is a really high correlation between people who enjoy using copilot and people who like lenders.

[00:34:22] **Tim:** True.

[00:34:23] **Carol:** Yes. Yeah.

[00:34:25]

## [00:34:25] Deep Backlogs

[00:34:25] **Carol:** Dear diary, I've already created like four different epics this week in Jera. I love the idea of creating a deep backlog and I lean into having to reprioritize things on the fly love then. So Ben, let's talk about your love for JIRA

[00:34:45] **Adam:** and how much you love the backlog.

[00:34:47] **Carol:** backlogs.

[00:34:49] **Tim:** deep backlogs

[00:34:51] **Adam:** D backlogs. We've been the Dell.

[00:34:54] **Carol:** Yes.

[00:34:55] **Tim:** own standalone podcast.

[00:34:57] **Ben:** so so this almost relates back to, Carol's triumphant talking about process. And I was saying that I had an engineering manager kept wanting to do burn down charts and I was ruining it for everybody because I just kept creating tickets. I love the idea of being able to maximize the time in the day. And if I only have a single epic then kind of to Carol's point earlier about downtime is that if you have a process that requires you to have downtime, then to me, that's like lost value. Add I could be doing something there and I didn't have the opportunity.

[00:35:29] **Ben:** I will be monitoring slack channels lightly, and I'm not like obsessively monitoring, but I'm just watching to see what people are talking about in the support channel or the customer facing team channel or the customer success channel. And sometimes the last go, Hey, does, do we have this feature on the app or, Hey, a customer just came to us and said, this XYZ isn't working well for them, or could they lodge a feature request and I'm honing in on those.

[00:35:51] **Ben:** And if there's something that catches my fancy shiny thing, then I create an epic for it as almost like a placeholder that here's something I kind of want to work on. It might not be the thing I work on right now, but I want to know that it's there and it's been recorded and I don't necessarily create all the tickets in the epic, but I know it's an epic worth of effort, so I'll create the epic and then I'll go back to my other stuff.

[00:36:13] **Ben:** And then if I'm in the middle of something where I get blocked or I'm waiting for, I dunno, And I can quickly switch over to another epic just for a moment. Like some epics are more about like random work. Like I have an epic that I created this week just for feature flag cleanup. So I create a lot of feature flags in the application and I'm sometimes lazy about removing them.

[00:36:34] **Ben:** So sometimes if I have a 30 minutes to kill her an hour to kill, I'll look at that epic. And I say, oh, this feature flag, I can probably rip out in 15 minutes. Let me just go ahead and delete the rest of that. And so I'm finding the gaps in my day and I'm plucking right-sized efforts to correlate with the right size gap that I'm currently in the middle of.

[00:36:52] **Ben:** and I use these, this deep backlog of stuff as a way to just constantly cram more stuff into my day because I work very set hours. I'm not one of those people who is like very focused at 11:00 PM, at 11:00 PM, I've already been asleep for an

[00:37:07] **Tim:** Um,

[00:37:09] **Ben:** So I maximize the time that I have.

[00:37:10] **Ben:** And I just like to create basically in the same way that I do note to. Any feature idea that enters my head. I want to get into the ticketing system so that even if I don't work on it for six months, I know. Yeah. I know that five months from now, I'm going to be bored and I'm going to be scrolling through my tickets and I'll be like, oh right.

[00:37:28] **Ben:** I totally forgot about that one. let me see if I can knock that one out this week.

[00:37:32] **Tim:** Earlier, you said you couldn't even find the backlog. So it sounds to me like you're using epics as a backlog.

[00:37:36] **Ben:** Yes. Yeah. I, okay. let me just quickly look at my, whereas my agile board. So my agile board currently has 71 items in the, to do column.

[00:37:47] **Carol:** That's a lot,

[00:37:49] **Ben:** Yeah. That's a lot. So that's how I roll though. That's I don't know how to organize it otherwise.

[00:37:54] **Carol:** but it works for you and you're a one person team now, so that's okay.

[00:37:57] **Ben:** Yeah. Yeah, exactly. So to me, it's like when I have a moment and, or I'm not sure what I want to do next, I'll just scroll down that to do list and I'll find the. That feels like the right balance of how much work do I want to be doing right now? How hard is something going to be? How much time do I have to dedicate to it?

[00:38:13] **Ben:** And I'll scroll down and I'll find the thing that feels like it's the, the Indiana Jones sack of sand to get the gold head.

[00:38:22] **Carol:** So I would love to have you on our team because around Christmas we hit this point where me and two other, three other engineers were in the backlog looking, and there's literally nothing to work on. We couldn't find anything that was in the realm of what we were capable of doing. Like, they were things that the integration team has to work on, or they were things that other people had already started and needed to finish up.

[00:38:47] **Carol:** So they weren't really things we could pick up. So I just hit the error log. I hear error management system and was like, I'm going to find things to work on over here because there's nothing in the backlog. If we had. I would have 61 things to choose from right now. And I could just work anything in the 15 minute window.

[00:39:03] **Carol:** If you blocked it off, like, Hey, go clean up these feature flags. Great. You've already done the legwork to tell me what needs to happen so I can go make it work. I hate doing the legwork of finding what needs to be done. So I think every team should have someone like you in that role that finds the things that are needed and gets them in the hands of the developers. So

[00:39:24] **Ben:** I'll tell you one thing that I have tried to push several times of the company and it has never gotten any traction for reasons that I don't quite fully understand. I wanted to come up with some sort of a special JIRA label that you could assign to tickets. And these tickets were tickets created by engineers for engineers, and I wanted to call them, make it rain tickets.

[00:39:47] **Ben:** Cause you're making it rain. And I, and I wanted,and I wanted as a company for us to celebrate like, oh, look at this month we did, 150. Product roadmap tickets. And we did, 37 make it rain tickets, like, look how motivated our engineers are to just find problems in the system and be self motivated to fix them.

[00:40:09] **Ben:** And I get so jazzed up just even talking about it. And I feel like I'm talking to a concrete wall when I bring it up at work. I

[00:40:18] **Carol:** depressing

[00:40:19] **Ben:** I, you know what I think it is. I think there from the product side of the house, I think there's a theoretical idea that, oh, wouldn't it be great if people were self-directed and motivated, but from a rubber meeting, the road perspective, I think a lot of times the idea of engineers just going off and doing work is very scary for some people.

[00:40:38] **Ben:** Yeah, yeah,yeah, exactly. some people call it rogue. Some people could call it self motivated.

[00:40:44] **Tim:** I know in our company years back,when. Okay, thank you. Were there at the time, Carol, we would have these like bounty, like these competition bounty days where everyone would try to like, just go knock out as much stuff as they could. And it was like of a free for all like a hunger games kind of thing.

[00:40:58] **Carol:** That was like cash prizes and yeah, sure. I mean, maybe it looked good to the customers cause they saw their cause. numbers went down,

[00:41:05] **Tim:** they saw their numbers went down, but honestly the level of stuff that came out was, Yeah. it didn't overall improve the product. So we, we just, we don't do that anymore.

[00:41:15] **Carol:** we do have, we're supposed to have, we didn't around Christmas cause we was out of work, but we have what we call technical debt task. So we have all these things that are labeled as technical debt. And it's, if you don't have something to do, you go pick up some technical debt and just clean it up, find something that needs, tests, coverage, find something that, we're not using anymore.

[00:41:32] **Carol:** There's something being called that really doesn't happen. So just go spend some time and clean that up. So we do have the technical debt in our backlog that the developers create and we prioritize into work as well.

[00:41:43] **Tim:** Yeah. W we're doing something similar like that too. Now it works a lot

[00:41:47] **Carol:** Yeah, the bounty on it, it just, like you said, you push out crap because it's about quantity, not quality.

[00:41:53] **Tim:** it is. Neo's numbers game. It wasn't a quality game and that doesn't help the software.

[00:41:57] **Adam:** So I want to go back to Carol. You said like at Christmas time you were picking stuff out of the error log because you didn't have anything in the backlog to do.

[00:42:04] **Carol:** Yeah.

[00:42:05] **Adam:** Just like you said, you'd like to have been on your team. I'd love to have that on my team. Right? Like.

[00:42:09] **Carol:** Yeah.

[00:42:11] **Adam:** We started out,we started our product Greenfield just, 10, no less than 10 years ago.

[00:42:16] **Adam:** And, we started with the best of intentions. Like literally every error that was trapped by the system went into a log that would push into our team chat. And I would look at every single exception that got

[00:42:27] **Carol:** Oh yeah.

[00:42:29] **Adam:** Yeah. Yeah. we still, I mean, we have a chat room dedicated to bugs or the bug log thing.

[00:42:34] **Adam:** and we try to, if it's something that should be fixed, that's why it's in chat. Right? Like some of them, sometimes it's just, awareness of volume, right? If they're, if you're getting one error an hour, it's not a big deal, but when you start to get 30 an hour or a hundred and. then something's up.

[00:42:49] **Adam:** And,that, that becomes a lot easier to notice and there's other ways of getting that sort of alerting. But, we started, with the best of intentions, like every exception, we're going to look at it, we're going to find out why. and like, if it's just because the user shouldn't have been able to double click that button, but they were, or, like just fixing all those little things.

[00:43:05] **Adam:** And now it's gotten to the point where it's starting to become noise, right. and things that are of value are starting to slip through the cracks because there's too much noise. The noise to signal ratio is off.

[00:43:19] **Carol:** So what, what we have is a priority flag on our errors. So if I see an error that's getting thrown and I realized that it's just kind of a noise air, it's not really an error, but we probably should go figure out a better way to handle when this doesn't happen. Like it's not a problem, but something caused that error to be thrown.

[00:43:37] **Carol:** We can actually go in and change the level on it. So that just becomes like a low level. And it's not in your face then, but when you have free time, go grab it and see if you can kind of figure out what's going on with it. That way the high priority ones stay high priority. And they're not. So masked by the low level things.

[00:43:54] **Carol:** And if I had a dream job, if I had like, could do my dream job, it would be nothing but living in air management and just fixing every single error log entry until there's like, no air locks. That's my dream job. That's what I would want it to do. I would love it. I would spend every day

[00:44:09] **Carol:** doing nothing with it.

[00:44:10] **Tim:** Are you, a sadist? Goodness.

[00:44:12] **Carol:** have no way. I get super happy when I open it up. I'm like, oh, this happened a hundred times over a month. I'm like, let me go figure out why, let me get to the root of it or let me figure out if it's not really a problem and get that gone, like clean it up. Move on.

[00:44:25] **Carol:** my

[00:44:26] **Adam:** That reminds me like, you know,

[00:44:27] **Adam:**

[00:44:27] **Adam:** early on, I was talking about early on, we looked at every single exception and we tried to like clean them up. It was the best feeling in the world to be able to email a customer and say, I saw that you have created an error or you ran into an error when you tried to do this thing, I fixed the error and you should be able to do that now.

[00:44:42] **Adam:** And they're like, wait,

[00:44:43] **Adam:** what?

[00:44:43] **Carol:** I didn't even tell you. Yeah. I didn't even tell you. Yeah.

[00:44:47] **Ben:** Have you ever had bugs that you try to attack several times over a long period of time, or like I have bugs where I'll see it in the airlock for a long time. And I'm like, you know what? This is the week. This is the week that I'm going to fix this and I try it and I get like an hour into it.

[00:45:04] **Ben:** And I'm like, oh yeah, I remember now this is why I couldn't solve it last time. And then I'll give up. And then months later I'll be like, you know what, I'm going to get that damn bug. This is the week. This is the week. And I just keep failing over and over again.

[00:45:17] **Carol:** Absolutely. But I keep going back to them. I keep going back. my favorite one is we have a connection to FEMA to basically get, updates on any disasters that have happened. And for whatever reason, They keep changing some of the HTML and one of the things that they're sending us and someone codes it to look for something, and it's not there anymore.

[00:45:38] **Carol:** So I fixed it once now they've changed it again. And I'm like, Aw, I've got to come up with a better solution, but it's like 29,000 errors over a month. Like, this is a lot of errors. I was like, oh boy. So yeah, you got to just keep going back to

[00:45:53] **Ben:** Yeah. And sometimes you go back that fourth time and for whatever reason, that's when you finally make that connection.

[00:46:00] **Carol:** and

[00:46:00] **Carol:** clicks.

[00:46:01] **Ben:** You're like, ah, that was the line I was missing.

[00:46:04] **Carol:** I would chase bugs for a living any day.

[00:46:08]

## [00:46:09] Legacy Support

[00:46:09] **Ben:** Note to self went back to transpiling my JavaScript sad Panda.

[00:46:17] **Carol:** Love Ben.

[00:46:19] **Ben:** So, as I've mentioned, several times, I've been trying to modernize my blogging platform. And one of the things that I made the decision to do was drop support for I 11. And I thought that when I did that, I'd be in this evergreen world where everybody was on modern browsers all the time. And I could just stop transpiling, which is the idea of taking modern JavaScript and compiling it down into a JavaScript that's supported by older browsers.

[00:46:46] **Ben:** I thought I could just stop doing that and start shipping. Async await to the browser and start shipping, string literals,

[00:46:52] **Adam:** You totally can't. You just got to stop caring about your.

[00:46:55] **Ben:** I know that's and like, it was, it goes fine. And then I start monitoring the error logs, and I see stuff coming in and I'm like, who are these people who are

[00:47:04] **Carol:** And clearly they love your blog. So why are you pushing them away?

[00:47:08] **Ben:** and the thing is, it becomes, it's this philosophical problem, because. I could get rid of those errors by just changing one line in my package dot J song, which is this browsers list property, which tells parcels my compiler. It tells parcel how much to transpile the code back to late to legacy support.

[00:47:28] **Ben:** And all I have to do to get rid of those areas is add that one line. And it's like, do I have a moral obligation to put that line in there to get that experience better for those people? and I want to be the person who says, I don't need to do that, but I can, I have to, I had to go back

[00:47:44] **Ben:** to transplanting to

[00:47:45] **Adam:** here, web fundamentals been progressive.

[00:47:49] **Ben:** So I mean the reality. Yes, I agree. I, and I consider doing that. So right now, I ship just a single JavaScript file to the browser and that does all the things and I did consider. For example, there's one thing that toggles the menu, opening the navigation menu. when you go from a desktop sized application to a mobile site application, I changed it from a navbar to a little drop down menu.

[00:48:15] **Ben:** And there's just like a couple of lines of JavaScript that runs that menu. And so I thought to myself, well, if I don't transpile this whole thing, I could split just that part out, say to a different JavaScript file and give it better support, because the reality is that doesn't do anything except have mouse event handlers.

[00:48:33] **Ben:** So it doesn't even have anything fancy. And then I wouldn't have to worry and I could think all the navigation would still work on a mobile device, even if the main JavaScript payload didn't compile properly on the client, but then it just, it gets complicated. Now I'm shipping multiple JavaScript files and that just seems like a pain in the butt. So I thought it was living in this brave new world of evergreen browsers. And I'm definitely leaning into the fetch API and promises being a native part of the browser. So I'm not poly filling anything. but I just, I had to get rid of those errors in the error log. They may not even have been doing anything.

[00:49:08] **Ben:** I don't know.

[00:49:10] **Carol:** So I would be curious to know what pages they were getting too. Like, are we looking

[00:49:14] **Ben:** I mean, it's a blog, it's a blog. There is

[00:49:16] **Ben:** no pages.

[00:49:17] **Carol:** well, are we looking at, are they looking at like posts from 2014 of ColdFusion updates? Because then that would explain why they're probably

[00:49:26] **Ben:** me, ColdFusion as an evergreen technology.

[00:49:32] **Carol:** I started,

[00:49:34] **Ben:** I don't know. Browser support is such a, it's such a prickly issue for me, Adam. It sounds like you have some opinions here. Whoa, what are you doing? What. I mean, you work in education, so that's like a whole different

[00:49:48] **Adam:** Yeah. there's laws about accessibility and stuff. we transpile, we're currently using. And we just target. I think it's ESBL four because

[00:49:57] **Adam:** why not? Yeah.

[00:49:58] **Ben:** like really all,

[00:49:59] **Adam:** It's either .

[00:50:00] **Tim:** Hmm.

[00:50:01] **Adam:** it's gotta be S five, I think.

[00:50:03] **Tim:** Does AOL browser work on that?

[00:50:05] **Adam:** I don't know. it's kind of a, don't ask, don't tell sort of situation. yeah, I mean,

[00:50:11] **Ben:** Ah, let me ask you this. And if you're not comfortable talking about it, we can skip it, but you're building a feature for a platform. Essentially. You have a platform service. what do you test in browser wise? what do you feel obligated to tell.

[00:50:24] **Adam:** yeah. so it's funny because we, our product is kind of split in half. We have, an admin interface that is used almost exclusively by. And university staff. And then we have what we call pub site or the public facing thing, which is, so in admin stuff, they'll like create an event that their constituents, their alumni and friends of the university can register for example, and then on the public site that, the public can register to attend that event. And, so we kind of have different requirements for the two. We've just sort of accepted that a reasonably modern browser and JavaScript are absolutely required for, for admin. So we can take a little bit more Liberty, cut a few corners on, progressive enhancement type stuff in admin. And in pub site, we have, a responsibility to check accessibility scores, make sure we're doing all the right stuff.

[00:51:21] **Adam:** There's. The disabled and, screen readers and et cetera, et cetera, can all use the site.

[00:51:26] **Ben:** What are you cracking open E 11 or anything and checking on that or

[00:51:31] **Adam:** no, we kind of rely on a few tools to like lighthouse and whatever to there's different browser extensions that you can audit with. And we've deemed that to be good enough,

[00:51:42] **Ben:** that's where I'm at

[00:51:43] **Adam:** as a, I mean, we're a technically a five person team, but truly when it comes to time spent engineering this product, it's a three person team with a, sort of a dedicated sales and support person on the side.

[00:51:56] **Adam:** and so we don't, yeah, we just don't have the bandwidth to be that thorough we've kind of decided, good enough is good enough.

[00:52:05] **Adam:** So we would make an effort to, meet and exceed the letter of the law, but we don't make any guarantees.

[00:52:11]

## [00:52:12] What's A QA Phase?

[00:52:12] **Adam:** Note to self a QA phase. What's a QA phase.

[00:52:21] **Tim:**

[00:52:21] **Adam:** Love Ben.

[00:52:22] **Ben:** I'm mostly work alone at work. So I

[00:52:25] **Adam:** This is news to me.

[00:52:29] **Ben:** I do everything from generating tickets to trying to hack together. Designs did writing the SQL scripts to deploying it and testing it and everything. and I was I'm now in the middle of. The planning phases for a migration, and I'm working with a product manager that's on the modern system, the modern platform.

[00:52:49] **Ben:** And this is, this has been such an extensive planning phase. It's so long. We've been doing this planning for months where I forget whole aspects of the plan, just because we've spent so much time planning, different areas. Anyway. So he's talking about the timelines and when are we going to get this done?

[00:53:06] **Ben:** And when's marketing going to get their stuff done. And when is the technical stuff going to get done? And then he's like, how long do you think we'll need to budget for QA? And I was like, QA, QA, what? Like, I'm going to build it and ship it away. You're ducking.

[00:53:22] **Carol:** Yeah.

[00:53:23] **Ben:** And I, and it's, it was just one of those things where it highlighted to me how different my day-to-day is as this like remanent of a bygone era and the new teams who have much more robust processes in place.

[00:53:37] **Ben:** They have people and they have. Systems that help do all the testing. And I don't even know what that world is like anymore.

[00:53:44] **Tim:** how much quicker can you deploy versus they

[00:53:47] **Ben:** Well, I mean,

[00:53:49] **Adam:** There's nobody

[00:53:50] **Adam:** in his

[00:53:50] **Adam:** way.

[00:53:51] **Ben:** Carol, you look like you got something to say there.

[00:53:53] **Carol:** no, we not only have a QA team. We have a S QA team. So we don't have, we have senior quality assurance members. So we have like higher end QA than just your off the street person coming in to learn how to test your system. It's

[00:54:10] **Carol:** like

[00:54:11] **Adam:** wanting support and you escalate me.

[00:54:12] **Tim:** I didn't know. They had a caste system in QA.

[00:54:14] **Carol:** So we like, one of our test automation, engineers has her doctorate.

[00:54:20] **Carol:** So I mean, we have people writing our automation test who are very qualified at what they're doing. This. Isn't just like some random user passing something for you on the front end and looking at it, they're actually taking your logic and making sure the test follows what the customers wanted. So, yeah, it's kind of completely different.

[00:54:41] **Carol:** Yeah. And that's why I said at the beginning of the show, we do the same things, but it's crazy how we do them so differently. Like this whole new cycle thing that we're in, it's eight weeks ago. Six week of development and two weeks of QA. And since we're kind of short on QA, it's possible that some of the developers are going to be testing other developers work like to assist the QA teams.

[00:55:04] **Carol:** But the point is that it has to be done and like a six week window. So you have time for quality to get through everything they need to do because they do front end tests. They do regression testing, they run all of our automation. There is so much testing that gets done before we deploy anything that I couldn't imagine deploying code now.

[00:55:24] **Carol:** And it breaking because it goes through so many tests.

[00:55:27] **Carol:** It's none of the thing anymore.

[00:55:29] **Ben:** how long does the QA phase take? So, so you got these eight week cycles. Is there a QA portion of those eight weeks cycles or that's unrelated to the cycles?

[00:55:37] **Carol:** Technically it's a two week at the end of it. Again, this is my first time on a cycle. So this is learn as we go kind of thing, but it's eight weeks, six weeks development, two week QA close out window is when they're wrapping everything up. But like we just handed over the project that we finished early to QA.

[00:55:53] **Carol:** So they're going to start testing it now because it's ready for them. But in the release it, whenever they sign off on it, so they don't have to wait till the end. So it really just depends on how big the effort is. And also we look at what the impact of something failing is to the system. So if we're talking about losing some

[00:56:10] **Carol:** substantial amount of money, then it's going to spend more time in QA.

[00:56:15] **Carol:** Then if I just changed the header on a form.

[00:56:18] **Ben:** I think this actually ties perfectly back to the backup camera thought experiment there, which is that, do you think, and this is a strictly hypothetical here. Do you think engineers that know they're going to have a robust QA process at the end of their cycle? Do you think they test as thoroughly as if they weren't going to have QA is QA making people sloppy, I guess, is to put

[00:56:43] **Adam:** And Carol. Remember your boss listens to the show.

[00:56:48] **Carol:** Right.

[00:56:49] **Ben:** is totally hypothetical

[00:56:51] **Tim:** I saw her face. I know the answer is,

[00:56:53] **Carol:** Hypothetically speaking, I would say yes, it can, you know, pushoff. Yeah, that's a good word. Good word. Because again, I know that if I get something slightly off, it's going to be caught by some automated tests and it's going to get picked up. But typically I do a pretty good job testing my own stuff, but I test less of my own stuff now, like in the front end than I did at my previous job and my previous job, I pushed nothing out that I didn't run through the entire system through every process.

[00:57:22] **Carol:** Cause I wanted to make sure I didn't bust anything that I didn't even know about now. I'm just like, all right. Log in worked. I got to the page. PR is out the door. Yeah. It's literally all I have to do because I know everything else is covered on the backend.

[00:57:36] **Tim:** QA worry about edge cases. It's not my problem.

[00:57:39] **Ben:** my machine.

[00:57:42] **Tim:** Exactly.

[00:57:43] **Carol:** So yeah, it can.

[00:57:45] **Tim:** It's funny.

[00:57:46] **Ben:** It's so interesting. I'm so torn about it because on the one hand, I definitely love the idea of having a series of gates between the software that's being developed and the users and quality being ensured at those various gates. But then I do worry that it makes things slower and sloppier, maybe not as a final product, because you have so many eyes on it, but it's like, what if you got rid of that?

[00:58:12] **Ben:** And then just hardened, like, there's this whole concept of what is it called? Shifting left, right in the security world. They're talking about this all the time. It feels like, everybody's responsible for security. It's shifting left in the product development cycle.

[00:58:24] **Ben:** And I almost wonder if QA, like why isn't QA shifting left as well. I, sorry. That's let me just ranting, but, I know, I don't want to put anybody out of a job.

[00:58:33] **Carol:** No for me. If I were to be responsible for QA my own work, I'm only going to go down the path that I know of. So I know what I changed and I know that area and I'm going to go do that peace testing. I'm not going to think to test the rest of the system. I'm not going to regression test the rules and Jen against this change to know if the rules engine is also picking up something from this that I didn't even know about.

[00:58:57] **Carol:** So for me, I think QA super important because I, as a developer am only going to test that little piece that I touch. I'm not going to go do the whole system. So yeah,

[00:59:09] **Ben:** It makes sense. It makes sense. part of me is probably just jealous that I don't have QA people.

[00:59:13] **Adam:** I, I could not do a manual QA person's job. it would,I would probably walk into traffic before the end of my first week.

[00:59:21] **Tim:** Yeah, it's a, Yeah,

[00:59:23] **Tim:** it's a totally different skillset and mindset. Right. Then from a developer, developers want to build stuff from the ether and people like testing stuff and, they like finding flaws and things. right. and pointing them out. So it's just a different personality.

[00:59:36]

## [00:59:36] Peeps Sure Do Love Let and Const

[00:59:36] **Tim:** Note to self. Sure. To love there. Let and const love. Ben

[00:59:51] **Carol:** let's have it. Come on

[00:59:53] **Ben:** Yeah, I am just VAR for life, baby.

[00:59:56] **Tim:** VAR for life

[00:59:57] **Ben:** so, so for the, for people who are listening, uh, what we're talking about is variable declarations in JavaScript, specifically old school, there was VAR variables. So used to like far X equals three,

[01:00:10] **Tim:** in the beginning. There was VAR and it was very good.

[01:00:12] **Ben:** And then, people like hated on this and I don't fully understand why.

[01:00:16] **Ben:** And so then they said, oh, well, modern JavaScript. It has to have led and cons, which are now these block level scoping for variables, which apparently solve a whole bunch of problems that people are running into every day. and I just, I don't buy it. I mean, yes, I understand that there are some edge cases that are solved by having let and const and locking a variable to a particular scope. But the reality is you can't in, in the same conversation, say, Hey, modern JavaScript and clean JavaScript should have small functions, that are, do one thing and do one thing well, and have well-named variables and should be broken down into function calls.

[01:00:54] **Ben:** And those function calls should be telling people what things are going to do instead of having comments. You can't preach all of that and then say that, oh, well, I should do const for variable. So that it tells the person what that variable is going to do and how it's used. I'm like, shouldn't everything that you just said already have taken care of that.

[01:01:11] **Ben:** If I'm looking at a function I'm ranting. Now, I apologize if I'm

[01:01:14] **Ben:** looking at a

[01:01:15] **Tim:** That's okay. We love it.

[01:01:16] **Ben:** and it's five lines long, and I declare a variable LaVar and I use it once. Like you don't have to see that it's cons to know that it's never going to change. Like you got five lines of codes to work with. And

[01:01:30] **Tim:** But the problem is you see, you can read, declare an update, VAR.

[01:01:34] **Ben:** This is okay.

[01:01:35] **Ben:** It's okay.

[01:01:35] **Tim:** it, but, but if it gets complex, you might accidentally do it and screw up.

[01:01:41] **Ben:** I

[01:01:41] **Ben:** don't know. It's like, but then it just feels like as someone who's been in the industry for a long time, my perspective on it from the outside is some very bright people at one point said, Hey, you should be doing Latin cons cause it's solve problems. And then a whole bunch of other people were like, oh, well of course we should be doing that because these really smart people over here said it.

[01:02:02] **Ben:** And it's obviously solving a lot of problems. And then it became like, just this like cargo cult philosophy on variable usage to the point where people are like, I just like their arguments to me. Don't even make any sense.

[01:02:17] **Adam:** Yeah,

[01:02:17] **Tim:** Well, as a person who's accidentally like re I thought something should be like a Singleton that should never, the variable should never change and accidentally done it in my code. I do appreciate, if you let, if you use lead in and you try to read, declare it, it's going to error.

[01:02:33] **Tim:** So, you know, very quick.

[01:02:35] **Adam:** I mean, I see your point, Ben. I think, my perspective is say you use Latin const and you're trans pilot back to yes. I mean, it's possible. It turns pilot all the way back to like PS4 probably. Right. It's going to transpile it to VAR and it's just going to treat it with the respect that it needs in order to accomplish all the same goals. So it's definitely possible to write equally well-performing code, identical functioning code without those keywords. But, I think the argument in favor of them is that those in combination with additional tools like TypeScript can alert you to potential problems before you would have to like, notice it happening in the browser and go, oh, okay.

[01:03:19] **Adam:** That's because I, that variable already exists and I overrode it accidentally sort of thing. So it's a matter of the tools alerting you to a problem now that you couldn't, or wouldn't have found that problem otherwise, but it's bringing it to your attention rather than waiting for you to.

[01:03:38] **Carol:** So I had to read a blog post about this. This was a while back. So I had to go find it, while you were talking. So sorry, I didn't really totally listen to everything, but totally, I get the gist of it. Right. But in the bottom of it, she's like my conclusion about letting Constance, I don't care. I would use whatever convention already exist in the code base. And if my linter throws a problem, then I'll address it when that happens.

[01:04:03] **Tim:** That's funny,

[01:04:04] **Carol:** And I was like, that totally made me think of this whole conversation. So I had to

[01:04:07] **Carol:** go through.

[01:04:08] **Tim:** Ben would agree if he used a lender.

[01:04:11] **Ben:** I, I,

[01:04:12] **Carol:** Linda Linda's exists to serve you. So she also says this windows exists to serve you if your linter rule annoys you and your team, delete it.

[01:04:25] **Tim:** We found your soul mate,

[01:04:26] **Tim:** Ben.

[01:04:28] **Ben:** I look at it, like salt in that I know salt can be dangerous if you have too much of it, right. It can lead to high blood pressure. Various problems I

[01:04:38] **Adam:** An extremely tasty food.

[01:04:41] **Ben:** but like, my blood pressure is good. And when I go to my general physician and he takes my blood pressure and it does all my blood work, like my blood pressure is good. My cholesterol is good. So I don't see reason to curb salt usage on my day to day until I find some level of usage that's actually problematic.

[01:05:00] **Ben:** And the doctor says, Hey, you should dial back on that salt a bit. And I look at far the same way, like, yeah, maybe there's some edge cases that let and const will fix, but it's just one more thing to have to think about it. Doesn't actually solve problems that I find myself running into. And by using far, I just know how things work and I don't have to ever think about it and I don't have to worry about, well, I declared it at this block, originally in my algorithm, but now my algorithm is changing and I need to declare it here and here.

[01:05:32] **Ben:** So now I need to change it from a lead to a VAR. And then, oh, well now it's,I'd had a, I dunno, like whatever, it's like, it's just, it adds complexity, whereas just using VAR just works and it just solves all my problems.

[01:05:44] **Tim:** Okay. We use VAR Willy nilly. No, this let const mumbo jumbo and we get

[01:05:52] **Carol:** Yeah,I want to recycle back to some of these conversations when Ben's on a giant team, when he's not, all robe, coding,

[01:06:04] **Ben:** no, it'll be super interesting to see how my reality is checked when I have a number of other people that can.

[01:06:12] **Tim:** for sure. No, you can't. Yes, I can.

## [01:06:20] Patreon

[01:06:20] **Adam:** So this episode of Working Code was brought to you by the new hip hot cast, deep backlogs with Bendel and listeners like you, I'm sorry. I'm broke myself. If you're enjoying the podcast, you should consider supporting us on Patreon support from listeners. Like you helps to keep the mics on and we appreciate each and every one of you, you can join that crew over at patreon.com/WorkingCodePod. All of our patrons get early access to an ad-free version of new episodes, and they get our after show, which is more of this drivel.

[01:06:58] **Adam:** I don't know why you would want to listen to it, but apparently some of you do, we really appreciate all of their support, but our biggest thanks. Go out to our top patrons, Monte and Peter. Thank you guys so much.

## [01:07:07] Thanks For Listening!

[01:07:07] **Adam:** did you know that word of mouth referrals are the gold standard of marketing?

[01:07:11] **Adam:** I just made that up, but it sounds pretty good. So, please try to think of someone that you think would enjoy this podcast and suggest that they give it a listen. That's going to be it for us this week. We'll catch you next week and until then,

[01:07:21] **Tim:** No to self and the deepest part of me, I

[01:07:29] **Carol:** Yeah.

[01:07:31] **Tim:** that our listeners, they have a heart. They really do some of them give some of them, listen. Some of them comment on our Discord channel. One thing I find over and over again is that their heart really matters. Love Ben.
