---
title: "191: Processing Processes"
description: "In this week's episode, the crew discuss finding the right balance in implementing processes within software development teams."
date: 2024-08-14
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/191-processing-processes/id1544142288?i=1000665245120"></iframe>

In this week's episode, the crew discuss finding the right balance in implementing processes within software development teams. Processes often originate from reactive measures to past mistakes but it is crucial to emphasize the importance of periodically reassessing the necessity and efficiency of these processes.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/191-processing-processes.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** I used to work at a place where all interaction with the database had to be done with using stored procedures. You were not allowed to write inline queries and those stored procedures were managed by the DBA team, right? Like you could write a query and say, I'd like a stored procedure that does this.

[00:00:17] **Adam:** and this is, you know, what my suggestion for a name for it. And it was terrible. It, you know, it was because they had a couple of incidents of. People writing bad queries in it and like breaking production in a really bad way or something like, I get that, but that's a overkill, I think, in my opinion,

## [00:00:55] Intro

[00:00:55] **Adam:** Okay. Here we go. It is show number 191. And on today's show, we're going to talk about process and how there can sometimes be too much of it, or maybe just the right amount, and we're going to figure that out. We're going to solve that problem today. joining me today are Ben and Carol. Tim was supposed to be here.

[00:01:08] **Adam:** We had something come up last minute. Couldn't make it. So just the three of us tonight.

[00:01:12] **Ben:** Yo, yo,

[00:01:13] **Adam:** Welcome everybody, but first, as usual, we'll start with our triumphs and fails. Looks like it's my turn to go first, so, that's what I'm gonna do.

## [00:01:18] Adam's Triumph

[00:01:18] **Adam:** I'm going to go with like a couple of small triumphs together.

[00:01:22] **Adam:** I would say that like work stuff, like, you know, working on code has just been kind of status quo. I've been working on, the, the payment method hybridization stuff that I talked about recently. it's been interesting because it's a, it's an interesting exercise in working backwards. Like normally when I'm writing a feature, I just start to go, okay, well, like what changes do I need to make to the data model and then what, you know, what is the first step?

[00:01:47] **Adam:** Possible point of interaction. And I start from there. It's like, okay, well now the knock on effects of that are, I need to handle it here, or I need to display something new here, or I need to collect something new there. And in this case, because of, the, it's like we're modifying our application at the, at like a fundamental level.

[00:02:04] **Ben:** can you, can you just back up for a second? You said payment hybridization. That does not sound familiar to me.

[00:02:09] **Adam:** No.

[00:02:10] **Ben:** forgive me if you

[00:02:11] **Adam:** sure. That's a quick recap for anybody who hasn't heard. we wrote our application initially to use a gateway called Spreedly, which is like a gateway aggregator. and so. Using their single API, we can, work with, integrate with a variety of different, actual gateways, like Elevon, Authorize.

[00:02:30] **Adam:** net, CashNet, Moderna, not Moderna, that's the,

[00:02:35] **Ben:** That's a, that's a vaccine.

[00:02:37] **Adam:** yeah, yeah, but, but you get my point, a bunch of them can, can send money to a bunch of different places using a single API, which is great. And then eventually we added. Braintree support so that in, in part, so that we can support Apple pay, Google pay, et cetera, the digital wallets.

[00:02:53] **Adam:** and that's been fine, but it's all to now it's always just been either or you can either be a Braintree customer, or you can be a customer that we use spreadly to connect to your gateway. And now we have a customer who has historically been on a spreadly connected gateway that wants to start using Braintree so that they can do Venmo, Google pay, Apple pay, PayPal, et cetera.

[00:03:14] **Adam:** and. The problem is we can't just make, it can't be like on Monday, we're on Spreedly and on Tuesday, we're on Braintree. We could do that, but that's going to cost them a lot of money because they have existing recurring or installment gifts.they have events where people have registered and paid money and they need, To at least have the opportunity to give people refunds without having to go through some backwards, like offline, cut you a check sort of thing, like if you cancel or whatever, right?

[00:03:42] **Adam:** So we still need to maintain a connection to their previous gateway, but we also need to start supporting the new gateway. So we need to be able to run multiple different gateway options in parallel. So that's what this, this project is. It's switching from either or to yes, and, right. And so, I, the first thing I did was like, okay, figure out all the data model changes and, made the additions to the database and added a feature flag and, made some changes to the API so that if the feature flag is on for you, the additional fields that I've created show up in the, your API responses.

[00:04:21] **Adam:** And I'm kind of working backwards from there, right? So like that, that's the end of the line. Stuff happens in the application and then you get your data later that says, okay, these are the payments I should expect. And this is where I can find my money.and I'm working backwards from that all the way to like the original source of where, like, you get to specify what your gateways are and, and this is the configuration and.

[00:04:42] **Adam:** This event uses this gateway. Some of that already exists, like gateway selection, but per event exists because you can have multiple gateways within like the Spreedly connection. You can say like, okay, this account is for event registrations and this account is for gifts. Cause that's a big thing in the, higher ed is they have to keep donations separate from like transactional stuff for tax purposes. So,it's just been a very strange exercise for me because normally if I was thinking about gateway stuff, I would just be like, okay, step one, we need to create some gateway configuration data. So I'd like have the data model set up and like create the settings screen where you can specify your gateways, that sort of thing.

[00:05:23] **Adam:** And then it's like, okay, now we need a gateway selection screen. And then on the checkout page for your event registrations or for your GIFs. I need to look at which gateway you've picked and that sort of thing. And in a lot of ways, I mean, some of this already exists, right? We already have a gateway configuration table.

[00:05:38] **Adam:** So we're kind of halfway there on everything. And then, but because of the changes and trying to keep it all, small PRs that I can deploy frequently, right. Disconnecting deploy from, activation or what, how are, how's it phrased for feature flags, Ben? I'm looking at the feature flag

[00:05:56] **Ben:** I mean, rollout, I guess that's kind of how I would talk about it. You,

[00:06:00] **Adam:** Yeah. Anyway, like separating code deploy from feature turn on. so because of that, I'm trying to get like all the ducks in a row so that, and do small PRs. So that like, we can start to roll this out in stages. And it's been a very backwards experience for me, which is an interesting exercise. I'm not used to thinking this way.

[00:06:24] **Adam:** So it's challenging and kind of fun.

[00:06:26] **Ben:** Yeah.

[00:06:27] **Adam:** That's my work triumph. I'm going to throw in, even though

[00:06:30] **Ben:** what can I, can I, can I just dovetail with you for a second? If you, if you don't mind. We, at one point years ago, maybe like five years ago, tried to add PayPal as an option at the company. We always accepted credit cards, but credit cards apparently are super easy in the United States. And not necessarily for everybody around the world, at least as it's been explained to me.

[00:06:53] **Ben:** So we tried to give the option to either use a credit card or PayPal. And we ended up abandoning that effort because there were so many little details that it's like you needed product to come in. It wasn't just an engineering problem. It was like product had to decide what workflows would have been like.

[00:07:11] **Ben:** And we were going back and forth with the PayPal support. And at one point, one of the use cases that we were trying to figure out was what happens if someone is in the middle of the billing cycle, because we get billed either monthly or annually, they're in the middle of the billing cycle and they want to just change their credit card, or they want to change their payment information for the next start of the next cycle. And, and PayPal was always like, well, it's two different systems, so you probably need them to cancel their current pay period and then just start a new subscription with PayPal. And everyone at this company was like, yeah, that's not going to work then. So catch you later. I, you know, and like, I'm, I'm sure there's better ways to do it, but it was just, there were too many weird cases that we couldn't come together as a team to say, this is the right path forward and ended up, just abandoning it and that's, and that's all to say, you know, my sympathies go out to all of the complexities that I'm sure you're dealing with.

[00:08:04] **Adam:** Yeah, it's, it's, it's a little weird. Like, it feels like. You know, open heart surgery, right? This is not just adding a new fingernail over here on the side. This is a big fundamental piece of the application.

[00:08:17] **Ben:** Yeah, absolutely. So I'm sorry. I didn't mean to stop you from your other triumph, your doubling triumphs.

[00:08:22] **Adam:** I am, I'm, I'm double dipping, technically maybe triple dipping. So something else that happened today, I got a really good deal on some wood. Which is exciting for me as a woodworker. I went and I found it on Facebook marketplace, a guy selling ambrosia maple, which is just maple, but it's been, it's had some beetle larva boring through it, which just leaves these like kind of stains in the wood.

[00:08:46] **Adam:** and it's, it's beautiful wood. I'll send some, I'll put some pictures in our discord. and I got a really good deal on that. That was fun. I'm gonna make a jewelry box for one of my kids and, maybe use it in like, the TV stand my wife wants to build. I'm just really excited about it. It's a good deal.

[00:09:02] **Adam:** and then the last thing is,I'm back working out. I finally motivated myself to, to get back on the horse. and like to the point where today I spent 500 bucks on some adjustable dumbbells. And so I'm

[00:09:17] **Ben:** What brand did you go with?

[00:09:19] **Adam:** their Rep,

[00:09:20] **Ben:** Okay. Yeah, yeah. I know Rep Fitness.

[00:09:22] **Adam:** RepQuickChange, I think is what they're called. yeah, they're, they're I watched a bunch of different reviews and those seem to be, like, sort of the sweet spot for price and durability.

[00:09:29] **Adam:** They have a lifetime guarantee and, and they're easy to use and they seem pretty high quality without being, like, ultimate quality.

[00:09:37] **Ben:** Very cool. Well, I'm super excited as, as a fellow workout enthusiast. I'm always excited to hear equipment review.

[00:09:44] **Adam:** I, I've started to try to get my workouts in, in the middle of the day, which I think is probably going to work a little bit better for me. Like it's, I've become, I've become a slug in the morning. Like the alarm goes off. I get up, I let the dogs out, I let them back in. And then I go crawl back in bed and I just like, I can't motivate to get up and move, which normally, you know, back in the day when I was working out, I would get up early and go like, let the dogs out, let them in and then go downstairs and work out for an hour or 90 minutes.

[00:10:11] **Adam:** And, I just, I don't have that in me right now, but you know, doing it over my lunch break and then finishing with a protein shake as my lunch is, is, much more, I don't know, doable. I motivate myself for that.

[00:10:23] **Ben:** Aren't you up at like 3am jogging or something

[00:10:26] **Carol:** well, not working out so much right now, but yes, we get up pretty early around here, and I can't do what Adam said, so there's no way I could work out at lunch, because once I detach from working, I can't turn my brain back onto it. So,

[00:10:42] **Ben:** a one way door.

[00:10:43] **Carol:** Yeah, like once I walk out and it's closed, there's no coming back to it.

[00:10:46] **Carol:** So I even have issues like if I have a doctor's appointment or I have like a call with my mom or in the middle of the day, I just don't want to go back to work. I don't want it. So I can't imagine having to deal with that struggle every single day. So at least if I work out in the morning, I'm like, all right, I'm awake.

[00:11:03] **Carol:** I'm going, let's just go get this day done. You know, let's, let's do it. Well,

[00:11:07] **Ben:** Very

[00:11:07] **Adam:** I used to be that kind of person. I could just get up and motivate in the morning. I'm getting old.

[00:11:13] **Carol:** it's not just old. Like for me, it's a lot harder cause now Steve's home, he doesn't go in so early. So since he doesn't have to be at work till nine, suddenly those 4 45 AM alarms or even 5 30 alarm just doesn't sound as appealing when your husband's still sleeping next to you.

[00:11:28] **Adam:** Yeah. Yeah. You know what? Part of it, I wonder too, if part of it is like, part of the problem with my motivation is because I'm overweight, right? I could very easily lose 30 pounds, and still be a very healthy weight. And I feel like, That extra weight that I'm carrying around makes me sleep worse. and it just like, I don't know, it's, it feels, it's a lot.

[00:11:54] **Carol:** It's a vicious cycle.

[00:11:57] **Adam:** Anyway, I'm going to stop bogarting the mic, pass it off to my man, Ben, my main man.

## [00:12:03] Ben's Triumph

[00:12:03] **Ben:** I will also go with a triumph, just one for today.

[00:12:07] **Adam:** Rub it in.

[00:12:08] **Ben:** so I've started to, I created a kind of. Proof of concept for a, let's call it, I've been calling it a playground application, which is supposed to be a companion piece to my feature flags book. I wanted to create a little bit of a, of a login scenario where people could go in and I allocate some feature flags and I give them a bunch of demo users and then they can start tweaking some.

[00:12:32] **Ben:** Feature flag targeting so that they could see how different users then receive the feature flags. And it was mostly just because I needed something to put my mind on and I wanted to have something that was a little bit of a vehicle for learning, and this felt very on point with what I've been doing.

[00:12:47] **Ben:** So I got a kind of a V1 working. With Alpine JS, which is a pretty cool framework for very lightweight JavaScript interactivity. But I definitely was hitting some, some edges and some walls with what felt like the right framework to be using. So once I got my version one working, I wanted to then go back and add an Angular 18, which is the latest version of Angular at the time of this recording.

[00:13:13] **Ben:** an Angular 18 version of the application and build an API and the backend to interact with. And I've never used Angular 18 before, though I've been a long fan of Angular itself, and I've never really used a modern version of Angular in conjunction with ColdFusion before, which is what this, companion piece is being built in on the server.

[00:13:32] **Ben:** And, I actually had a pretty decent experience with ChatGPT to try and work through how I would wire all this together with Docker. And, yeah, it was, it's like. My experience with ChatGPT is always, it throws out some kind of interesting ideas that are like half wonky, half okay. And then I have to keep saying like, well, what if we do it this way?

[00:13:55] **Ben:** And they have to keep modifying and it's very much a conversation. But what I ended up doing, which I don't think I would have gotten there on my own had ChatGPT not steered me in this direction. But essentially I have a Docker Compose file and I have two services. One is the CFML service and one is the Angular service.

[00:14:15] **Ben:** And what I ended up doing was I mount a volume in the Angular service that actually maps to the ColdFusion service. So when Angular compiles, And writes its files to its local dist or distribution folder. It's actually writing to a folder in the CFML service.

[00:14:36] **Carol:** Ah,

[00:14:37] **Ben:** And, you know, I'm, I'm not a huge Docker expert or anything.

[00:14:41] **Ben:** I know just enough to kind of get things to work sometimes. And anyway, I was, I was actually pretty pleased with. How it's coming together. And, one of the cool things that I think is the Docker file for the Angular service in the Docker file, though, the last command says like, what do you use to like, what command should actually run the process inside of this Docker image?

[00:15:05] **Ben:** And the default command is to just build. The angular files and exit out. And then in the Docker compose file, I override that to be a watch commands that have the build commands so that it'll build, but then it'll stay open and continue watching for file changes. And it just, it felt like I was, I was hitting the boundaries of what I felt confident in, in terms of my technical abilities with Docker and Angular and wiring things together.

[00:15:33] **Ben:** And I don't know, I just feel like I was growing because I was hitting those, those edges of comfort and, and I was just getting something on the screen. It felt very exciting.

[00:15:42] **Carol:** yeah, that's awesome. Yeah. Docker is one of those things that I know just enough to make my projects run that have to have it outside of that. I've kind of lost all ability to go new at it. Cause I don't have to anymore. Everything I use has already been created. So I'm like, oh wait, what do I do again? Like, do I click on containers or images? Which one is the right place to start from? Like, I go back so far. I'm like, I just need whatever I have, like what I have installed to run. Like, that's it.

[00:16:12] **Ben:** Well, that's the thing too, with, with stuff like this, at least for someone who's, I think, more of a product engineer and not like a platform engineer. Is that this style of work really only has to be solved once. And then once you've solved it, you you're spending 99. 99 percent of your time in product development mode, not in how do I wire all the pieces together mode.

[00:16:35] **Ben:** So I'm sure by the next time I try to do this, I will have completely forgotten all of it.

[00:16:40] **Carol:** Oh yeah.

[00:16:40] **Ben:** And what I'll have to do is I'll have to come back to this project, look at how it was implemented, and probably just like copy paste, you know, a couple of key files into a new folder and say, okay, this is now the start of something else.

[00:16:53] **Carol:** You need to like archive your chat GPT, like chat history and throw it in there.

[00:17:01] **Ben:** But, you know, I do feel like I'm starting to get, I don't want to say I'm appreciating chat GPT more because I feel like a lot of it, I'll, I'll do some interactions and I'm like, Oh, this is garbage. And I just go and look up Google and look up documentation, but I'm getting a little bit better at trying to find the right type of value.

[00:17:22] **Ben:** Like I'm, I'm getting, I think, a better understanding of what type of problems it can solve, and I'm not. I'm not underestimating it too much. I'm not overestimating it too much. So I'm feeling

[00:17:34] **Carol:** think you said something there that's really key with how I've been dealing with chat GPT and copilot is that the results aren't always what I need. And I get very frustrated. So I find myself going more to developer docs than I have in the past several years. I used to spend a lot of time just on Stack Overflow or reading through Reddit posts, you know, kind of figuring out what other people had solved.

[00:17:58] **Carol:** I'm like, Oh, okay, this works pretty well. I get that. Good to go. Now, I kind of just skip it and go straight to developer docs. I'm like, tell me what these options are. Like, I'm just going to go read what you've published about the options for this thing. Like, whatever it is I'm trying to solve. Or like, what's available to me when I utilize, like, these functions.

[00:18:17] **Carol:** So, developer docs are the bomb. And I'm getting more deep in them with ChatGPT giving me bad answers.

[00:18:27] **Ben:** Yeah. Well, and it's funny. So what I'm finding is the gesture that I find myself doing over and over again now is I will ask Chachi to do something and it'll give me an answer that may or may not work. But it's something I'm not familiar with, so then I'll take parts of what it gave me and I'll go to the developer docs and I'll look that thing up and now I have a page that is targeted just at this thing and I can really dig in and understand what exactly that's doing.

[00:18:55] **Ben:** So I'm using, ChatGPT is almost helping me craft my Google searches more than it is crafting the answers.

[00:19:03] **Carol:** Yeah, I could see that.

[00:19:06] **Ben:** It's like I've turned Google, I've turned chat GPT into the prompt engineer.

[00:19:11] **Carol:** is now,

[00:19:12] **Ben:** I flipped it. All right. So that's what I got going on. Carol, what do you have going on?

[00:19:18] **Carol:** Well, I'm going to go with the Triumph, but first I want to tell you something that happened this week that made me think about you. I was, I'm a, I have like a subscription to Beachbody On Demand because it has like a ton of workouts I

[00:19:30] **Ben:** is like a fitness app.

[00:19:31] **Carol:** Yeah. Yeah. There's like all kinds of videos. There's different programs you can do.

[00:19:35] **Carol:** they have meal plans, all kinds of stuff, but I love that there are options I can use when I travel, whenever I don't feel like doing weights, there's Tons of like things I can just go pick up and do and follow for 30 minutes. And it's instructed to me. I don't have to figure out how a move works.

[00:19:51] **Carol:** Right. So this week I got a pop up on my phone and it was like, now available on Beachbody On Demand, Dig Deep 6. 0. And I was like,

[00:20:01] **Ben:** Oh, if only that was me.

[00:20:04] **Carol:** I even clicked on it. I'm like, did Ben get on Beachbody and not tell me?

[00:20:08] **Ben:** How awesome would that be? Triple

[00:20:10] **Carol:** yeah, that's your next career.

## [00:20:13] Carol's Triumph

[00:20:13] **Carol:** I'm going to go with the Triumph for the week.

[00:20:15] **Carol:** We are two, I know if Tim was here, he'd be winning too. I am two stories away from being done with our MVP, meaning that the last two efforts, the last two stories are not even big ones. It's just some cleanup with some validation and basically peer review everything with all the other teams so they understand what we've done.

[00:20:39] **Carol:** But we're two stories away and we're going to be done with the MVP and they should be out in production by the next sprint. So, woohoo!

[00:20:46] **Ben:** Yo, very cool. Do you have a sense of how many stories were in this MVP?

[00:20:52] **Carol:** no. I'm just gonna go with no. I'm gonna go with

[00:20:55] **Ben:** Was it bigger than a bread box?

[00:20:57] **Carol:** bigger than the red box. Yes, way bigger than the red box, like the size of a car. Um,we demoed it to you in Sprint Review this past Tuesday or Monday, and my product owner made the comment that Carol has gotten this like to completion and, you know, we've only been working on it for a year, to which I immediately responded with, I haven't even been working here a year, so that's not accurate.

[00:21:24] **Carol:** It definitely didn't take me a year to do all this work. I was like, we didn't start it, so like February, like we kind of started brainstorming, in the last year into January, but no code was even touched. So going into January, I was like, but we've been able to shave off so much time processes that were taking like 45 minutes.

[00:21:44] **Carol:** I have completing in under a minute now. So our users are able to completely, re work how they handle hiring. So super exciting.

[00:21:55] **Ben:** Was this when you, when you said the 45 minutes down to one, was this that whole like N plus one query problem that you were dealing with or was that a different

[00:22:03] **Carol:** That's, that was a different thing altogether. Yeah. Yeah, no, this is just, basically they want to make a copy of what they consider like a request to hire someone. And they need the original information, like copied over every time. And the way it was working in the system was it was just constantly like in a loop of, I'm going to create one, I'm going to create one, I'm going to create one.

[00:22:27] **Carol:** And I can't do anything until they're all completely done. So I threw it in on, RabbitMQ and using mass transit to handle all the middle. Layer there, but, using a message and queue system to allow everything to process at the same time. So, yay.

[00:22:46] **Ben:** Very cool. Noice.

[00:22:48] **Carol:** So it's going pretty swell.

[00:22:52] **Ben:**

[00:22:52] **Carol:** Hey, look, my mic works again. it's probably a good thing that I couldn't make my Beachbody On Demand, joke and my,pretty, pretty, pretty good joke. So, uh,Oh,

[00:23:02] **Adam:** but I'm back. You can't get rid of me that easy.

[00:23:05] **Carol:** darn. We tried.

[00:23:06] **Adam:** Anyway, cool. So, congrats on your triumph, Carol. Sorry, I,

[00:23:11] **Carol:** you.

[00:23:12] **Adam:** I couldn't comment as it was going on.

[00:23:13] **Adam:** Anyway, that, it's pretty cool to be that close to, I know, I, I, I know that feeling all too well, being that close, like the, the compliance stuff. You do something big and

[00:23:22] **Carol:** I'm ready. I'm ready for my customers to have it. Like, that's the big thing. They're actually going to D my product owner and a few other of the product side people are going to D. C. next week to do a demo of the entire working thing with IRS to kind of let them know what's coming in. They're spending three days on training for this.

[00:23:42] **Carol:** I don't know why you need three days to click a button, but I'm not going to question it. Go do your training. I'm not going.

[00:23:48] **Adam:** I'm glad I'm not in that training.

## [00:23:52] Accouncement

[00:23:52] **Adam:** All right. Well, so before we get to today's topic, we have a little bit of an announcement to make. this is, as I said much earlier, episode 191. and we've decided that, season one of the Working Code Podcast is going to come to an end at, at, at, with the completion of, episode number 200.

[00:24:10] **Adam:** So you got another nine episodes with us.what does that mean? I guess, kind of what we've decided is we're going to just take a little bit of time off. We've been going for 200 episodes. Ish, consecutive weeks. and we need a break. So we're going to take, you know, probably at least a couple of months off, and, and hope the plan is to come back when we feel better.

[00:24:29] **Adam:** Refreshed and, and ready to, to go at it again. I, there's stuff to figure out with Patreon. Obviously, our patrons are not going to want to continue paying us while we're giving them nothing. That's totally fair. but we got the next nine weeks to figure that out. hopefully there's a way to like, pause it or something.

[00:24:46] **Adam:** but you know, whatever, we'll figure it out. And anything you guys want to add?

[00:24:51] **Ben:** No, I felt like I wanted to make a, you know, mommy and daddy still love you very much kind of a joke and this has nothing to do with you, but not appropriate to make jokes like that. Yeah,

[00:25:05] **Carol:** Yeah. No, I, I will say we appreciate all the support you've given

[00:25:09] **Ben:** yeah,

[00:25:10] **Carol:** when we started this, I had no idea that we would make it to 200 episodes.

[00:25:15] **Adam:** For real.

[00:25:16] **Carol:** I was like,

[00:25:17] **Adam:** a huge,

[00:25:18] **Carol:** nobody wants to hear Adam talk this much.

[00:25:21] **Adam:** even I don't want to hear me talk that much. But, apparently a few people like it. So anyway, that's just a little bit of, of housekeeping.

## [00:25:29] Too Much Process?

[00:25:29] **Adam:** So let's get onto our, our main topic for the day. too much process? Question mark.

[00:25:34] **Carol:** Yeah, like those, three days of training on how to click a button.

[00:25:39] **Ben:** Well, If I can add some context here, because this is something that's been in my mind lately, I listened to a lot of podcasts, not all of which are technical, most of which are technical, but not all of which. And in 2024, which is a presidential election season, a lot of the podcasts have of course, talked about the political race and the political climate.

[00:26:02] **Ben:** And one of the podcasts that I really, really enjoy and cannot recommend is Ezra Klein's podcast. He's, he works for the New York times. And one of the things that I really appreciate about him is he challenges a lot of things that maybe make people feel uncomfortable. And one of the things he challenges is that, we've added a lot of process to A lot of aspects of government and that process was added for very good reasons.

[00:26:32] **Ben:** Right. And before we had process, people just kind of run amok and businesses were dumping toxic waste into rivers and, you know, children were working in factories and safety exits were being locked and people were being burned to death. I mean, lots of really, really terrible things happen and people had to step in and say, okay, we need to regulate and add process and we've a little bit, Backed ourselves into corners in certain ways.

[00:26:58] **Ben:** And one of the things that Ezra Klein keeps hitting on, just as an example, is the housing crisis that we have people in this country who want to buy a house and there's not enough house inventory and the median price of a house in just like the last decade has jumped from like 200 and something thousand to 400 and something thousand.

[00:27:17] **Ben:** And it's everywhere that this, this housing price, this housing crisis. And one of the things that they attribute to this. is just that there is so much process around development and zoning and zoning boards and, environmental studies that have to be done. And he was just interviewing, as an example, the, one of the senators from Hawaii.

[00:27:40] **Ben:** And Hawaii is all about environmental measures because that's their entire economy, yeah, runs on having a beautiful environment. And they were saying that it's so strict that if you have an apartment building on one block and an apartment building on the next block, and you want to build an apartment building in between those two buildings, you still have to do a ton of environmental impact studies.

[00:28:03] **Ben:** And they're saying you probably don't have to do that considering the fact that you're already building in between two other buildings. But there's so much process. And it's getting in the way of building more housing more quickly. Anyway, this is not a show about politics and it's not a show about housing, but the whole point with it was just to say that we can add process with the highest of, of intent, the best of intent, but then that can back us into places that we don't necessarily want to be.

[00:28:30] **Ben:** And it occurred to me that that probably also happens at companies as well, that we add process because we're trying to solve a particular problem. But at some point that becomes a hindrance and, and gets in the way of actually moving the company and the products forward.

[00:28:48] **Adam:** I used to work at a place where all interaction with the database had to be done with using stored procedures. You were not allowed to write inline queries and those stored procedures were managed by the DBA team, right? Like you could write a query and say, I'd like a stored procedure that does this.

[00:29:07] **Adam:** and this is, you know, what my suggestion for a name for it. And it was terrible. It, you know, it was because they had a couple of incidents of. People writing bad queries in it and like breaking production in a really bad way or something like, I get that, but that's a overkill, I think, in my opinion,

[00:29:27] **Ben:** Yeah. And I think about companies where there's a really heavy QA process. I, I've never really worked at a company that has a heavy QA process. So I can't speak from

[00:29:37] **Adam:** like CrowdStrike.

[00:29:38] **Ben:** experience, but it, it, that also to me always feels like it's a little heavy handed that like everything has to go through a very, Codified procedural QA, regardless of what's being changed.

[00:29:53] **Ben:** And it's just this solving problems with a hammer, but there's no nuance when there, when you can't have nuance and you can't have, I don't know, human evaluation, you, you, you're, you're. Stuck in the status quo. And then how do you ever challenge the status quo to make it better? How do you improve? You know, if you, if you have this hard coded process, how do you ever improve?

[00:30:19] **Ben:** That's

[00:30:21] **Carol:** just today, like I had the conversation about testing this work that we're doing and I had a smoke tester. I didn't even know we have smoke testers. I have so much to learn still about my job. Let's just be real. Like our smoke testers sent back documentation. There was seven pages of screenshots and notes.

[00:30:40] **Carol:** I was really, really excited about this because I was really, really excited about the results of how she tested it, and every little thing was either green or red. So I had to go through and figure out everything that was red and see what was going on with it. Only to realize she was testing before we'd even put code up.

[00:30:54] **Carol:** So she was testing things that weren't even there yet. I'm like, you kind of went to this feature early. I know that, you know, someone told you it was ready to be looked at. She meant that you could start poking around, but don't test it because not everything's deployed yet. So then I'm like, do I send all of this back to you?

[00:31:11] **Carol:** She's like, yeah, just close this one. I have to do a whole new test, a whole new retest every time. I'm like, so even if there's one little thing wrong, you have to retest this in like the seven pages of like screenshots and stuff over again? She goes, every time. I was like, why? She goes, it's just what we've always done.

[00:31:29] **Carol:** I was like, what about if I just give you a story that tells you to test the one thing that was broken? She goes, I guess that could work too. I'm like, we're going to go that route.

[00:31:39] **Adam:** Well, you've got to look for regressions too.

[00:31:41] **Carol:** Yeah. But see, the regression test is happening somewhere else.

[00:31:44] **Adam:** Oh, wow.

[00:31:45] **Carol:** Yeah, she's just smoke testing it. She's just doing the initial, like, does this pass if you, if you like, yeah, it kind of looks pretty good. Let's get it over to the BA for more tests. Then let's do regression testing. Then we do compliance testing.

[00:31:58] **Carol:** So then we do our 508 and accessibility testing. So I'm like, on top of, we have to have code coverage for unit tests and integration tests. So I was like, what about if I just give you one checkbox to retest instead of you giving me seven pages back? Cause you spent days retesting all of this.

## [00:32:16] Zero Process

[00:32:16] **Adam:** want to, I want to kind of maybe draw the other boundary for this conversation. We're talking about too much process. The, something I feel like I've seen several times in the last couple of months is people kind of advocating for like basically zero process, like not even doing code reviews, just hiring trustworthy people and saying here, commit and push and it'll auto deploy when you push sort of thing.

[00:32:42] **Adam:** and. you know, just like hire competent people and get out of their way is sort of the philosophy there, which absolutely you can move faster when you do that. But, that can only last so long, right? As your company grows, eventually you're going to hit compliance points, or you're going to start to need to hire junior developers or something like that.

[00:33:03] **Adam:** And, you're just going to have to have something. I feel like finding that sweet spot is an, is an art for sure.

[00:33:10] **Carol:** Yeah. I completely agree.

[00:33:12] **Ben:** I feel like, I don't know if this is an engineering specific thing or if this is just people in general. But I, I maybe feel that engineering companies have a lot of trouble living in the gray that they have to have these

[00:33:28] **Adam:** Us?

[00:33:30] **Ben:** and, and, and, you know, it's like, it's like, well, if we don't have laws, then everyone will just start murdering each other.

[00:33:37] **Ben:** And you're like, I don't know, I don't think that's really what human nature dictates because there's a lot of people that just coexist peacefully, but you have to have laws because there's just some crazy ass people in the world. Like, it doesn't have to be extremes. I'm, I, so one of the shows that I really enjoy is, John Oliver's Last Week Tonight.

[00:33:59] **Ben:** It's kind of a news comedy show that ends up being more depressing than it is funny. But he will very happily admit that of himself. But one of the things that he comes back to all the time is that we have to change and people, their pushback is always like, well, we don't, you know, we can't change everything.

[00:34:18] **Ben:** So where do you draw the line? And he's like, just draw it somewhere. Like you don't have to have the perfect solution. But doing nothing isn't the right option. And, and I feel like we, as an industry, maybe don't know how to do that. We know how to draw the extreme lines, the either no process or the, you know, I shouldn't be able to look at code and know which developer wrote it because we should all be robots that write exactly the same code.

[00:34:44] **Ben:** Like there's, we don't, we don't do nuance very well as an industry. And I think that's just, it's just weird to me. And I think that maybe it holds us back in a lot of ways. But, you know, then, then

[00:34:58] **Adam:** Yeah.

[00:34:59] **Ben:** I don't, you know, I think the problem is there's good, there's no one size fits all. And you have to just start drawing lines and you have to test those lines.

[00:35:07] **Ben:** And if they're not in the right place, then you have to redraw them. But that's not a, that's not a perfect process.

[00:35:13] **Adam:** And every step on that path costs money. So you have to like, try to do it efficiently so that you're not,

[00:35:19] **Ben:** Right. Well, so the, the irony though, is that, is that not redrawing the lines also costs money. Just looking at Carol's example, this woman spending so much time, I don't know if it was a woman, sorry. I just assumed.

[00:35:30] **Carol:** I think I said she,

[00:35:31] **Ben:** She, okay. This is the, this person is spending all this time doing arguably unnecessary regression testing.

[00:35:40] **Ben:** And that's. Costing the company money when she could be regression testing something else that is more worthy of it. And that's like, I almost wish. So one of the, one of the, I keep going back and forth with this audio book. I can't quite finish it, but it's all about super communicators. And that's one of the things that super communicators do.

[00:35:58] **Ben:** That's one of their superpowers is they will take a problem and reframe it in a way that helps people connect with it. I feel like that's what you need is a super communicator to come in and not just be like, there's too much process, but to be able to take that and mold it in a way that is tangible in terms of.

[00:36:18] **Ben:** This is costing the company, you know, 100, 000 a month. Is that really where we want to be prioritizing our time into, into spending this money? You know, like I'm just making up numbers obviously, but it's just, it's hard. And I think, and I think part of the reason it's hard to change is also because not everyone has the tools to be able to communicate the need for change very effectively.

## [00:36:40] Why Processes Exist

[00:36:40] **Carol:** So I think you said something early on talking about processes in general and the housing kind of issues that were being addressed that you were listening to, but I think you should go back to a lot of these processes were put in place because it was reaction to something that happened.

[00:36:57] **Ben:** Right.

[00:36:59] **Carol:** reaction is, we don't want this to happen again.

[00:37:02] **Carol:** So we add a lot of test coverage to our very like I don't want to say, what's the right word? So our, the areas of the system that are very finicky that could easily break or those that make us a lot of money, because if either of those have issues, we're in trouble. So you spend a lot of money covering that with tests, but then do you spend the same amount of money covering everything with the same amount of tests?

[00:37:29] **Carol:** And that's where I think, like, we've struggled at is. Everything is the same value, so everything should have the same coverage, everything should get the same touches. When in reality, if that button is a little off in color, it's not gonna matter. If we can't take a payment, it's gonna be a problem.

[00:37:50] **Ben:** And I think part of the problem there is you have to have people who, Understand the business, at least to the point where they have the tools to make decisions that are meaningful. Cause I think part of the problem is that even when people want to make a change, they don't know if they can, they don't know if they're empowered to, they don't know if they have the right information and the right evidence, and if they're privy to all the information that needs to be had to even consider making a change like this. And, and part of that comes from maybe a lack of transparency and not in a malicious way, just in a, the company wasn't set up so that the engineers have to understand the business requirements. The more you can pull people into the conversation, the more they feel like they can be part of the solution.

[00:38:42] **Carol:** Yeah, I feel like a lot of our devs are on the side where they don't really know what could help business. They just work off of what's being asked. So customers want this. So we're going to work on this instead of having a lot of opportunity to just innovate and say, here's where we think we should take the system.

[00:39:02] **Carol:** It's usually a response to what the customer wants and not what we think the system needs.

[00:39:09] **Adam:** So maybe this is because you kind of framed this around the current political situation in the country, in the United States, but it occurs to me in a lot of ways, traditional company structure here is very similar to our government. And maybe that's just because, you know, like. You know, like follows, like sort of thing, you know, we, we do what we

[00:39:32] **Ben:** Power structures have a structure.

## [00:39:35] When Do You Stop?

[00:39:35] **Adam:** Well, yeah, but like, you know, so, so a company has a CEO that's like, you know, the, the president of the country, right? The executive branch, they enforce the laws. you've got like, you know, management kind of, writing the laws. And then I don't know in this metaphor, what in a company is the judiciary branch, but it's starting to sound like there might be something here.

[00:39:55] **Adam:** And, you know, as I was, as you were describing there being the potential for too much process as a, as a country, I was kind of sitting here thinking like just end stage capitalism and, you know, wondering to my, this is a little off topic, I guess, but like, as a, as a country, right? The, the, the job of the Congress is to continue writing new laws and, and that's just creating more processes, right?

[00:40:25] **Adam:** Trying to like. Find the ways that people are, exploiting what little loopholes in gray area remains and, and try to write those out of existence or write them in a way that, benefit them and their, their friends. Right? but like, for lack of a better way to ask, like, is, should there be an end?

[00:40:45] **Adam:** Right? Should, should you at some point say like, this is good enough, everything else that comes up should be interpretable from here? Like we don't, I guess if I had to decide right now, I would say like, there should come a point when it doesn't make any sense to write more laws. Like it feels like that's not a sustainable process to just continue on forever.

[00:41:08] **Adam:** Right.

[00:41:10] **Ben:** Yeah. I, I, I, so even if I could even go a little bit farther and pull it back into the company context, not, not just that we're done and everything else going forward is interpretable and extrapolatable, that's probably not a word, but you almost need periods of reflection where you say, should we just be taking this away?

[00:41:31] **Ben:** Like maybe this is just not adding value anymore. It's like fixing a database. The application requirements change over time and you end up with either entire database tables that just are no longer relevant, or you end up with columns in a table that are no longer relevant. And it's one of those things where it's like, ah, it's a little bit of hard work to go and remove a column.

[00:41:53] **Ben:** Cause I probably have to remove all the references to that column. And then there's the chance that I might lock the database table and that'll cause, you know, response issues. And there's a chance that I might drop the wrong thing and then we're totally hosed, but like, yeah, you probably should do house cleaning though.

[00:42:07] **Ben:** I mean, that ultimately will create a more maintainable system. And the same has to be true of the company. At some point you have to step back and say, is the process that we have in place actually adding value? And if it's not, let's experiment with either reducing or maybe even removing that process entirely.

[00:42:27] **Ben:** But it's, it's scary. You know, you, it's scary for people.

[00:42:31] **Carol:** Yeah, I'm right there with you. When Adam was talking about the job, you know, is to keep making more law. I was like, you know what, at some point there should be expiration dates or there should at least be a review point set that say, is this still valid? Like, does this still work? If not, it gets to expire.

[00:42:49] **Carol:** It no longer can be used because we all agree this is dumb and stupid. Don't do it.

[00:42:54] **Adam:** Right. Like a dead man's switch on every law, right? So you have to, you have to renew it or it, or it expires. I love that.

[00:43:00] **Carol:** It's not usable. We don't need it. Yeah.

[00:43:02] **Ben:** Well, the worst, I mean, so the, the perfect context for that kind of thinking to me is when you ask, why are we doing it this way? And then the answer is, well, the person who put that in place no longer works here. That should almost be, that should like trip a switch. We're saying, okay, then on Friday, we're going to have a meeting to decide whether or not we want to keep doing it this way.

[00:43:23] **Ben:** If the person who put this in place, can't be here to argue for it, then the de facto response is that it's no longer needed. And we now have to argue to keep it. So

[00:43:32] **Carol:** Expired. Okay. So what process would you kill? You, you've got one that you have to have something that you're like, this is what I would get rid of

[00:43:43] **Ben:** I was thinking about this the other day, actually, and I was thinking about it a little bit in the context of Twitter. So when Elon Musk bought Twitter and Twitter is arguably a complete show now, so it's not even like a really good example, but people do point out the fact that he came in and he basically stripped it of so many of its essential parts. And it still runs. And there's a lot of argument about why it still runs probably because they put a really good system in place to begin with. I don't even understand what

[00:44:17] **Carol:** because that's, that's all Twitter's for now.

[00:44:20] **Ben:** idea was

[00:44:23] **Carol:** Anyway.

[00:44:24] **Ben:** he removed things until it hurt. And I, and I feel disgusting, even mentioning. his name in the context of anything worth discussing, because I find him actually quite an important person, but it's like, you almost want to, see how much you can remove until things start to hurt again. And I, you know, at Envision, we've gone from a team of, I don't know how many, several hundred engineers or 150 engineers, whatever we used to have, and we're down to literally three engineers.

[00:44:56] **Ben:** And that sucks a lot.

[00:44:59] **Carol:** Yeah.

[00:45:01] **Ben:** It's also not on fire either.

[00:45:05] **Carol:** Somehow it's still kind of functioning, I

[00:45:07] **Ben:** Yeah. And so you're like, it just really makes you think how many other things can you have removed and things would have actually continued to work? How many things that weren't actually all that important? I, of course, historically rail against the idea of linting.

[00:45:24] **Ben:** That's like my particular hill that I enjoy to die on. But it's like, as a thought experiment, if you just removed all linting, like, what, what would actually happen? Like, some people would put some braces in a weird place. Some people would do spaces, some would do tabs, but like at the end of the day, so what, and

[00:45:43] **Carol:** It still runs,

[00:45:44] **Ben:** yeah, I'm like, your application.

[00:45:46] **Ben:** And, and, and that's the argument that I always come back with back to is that all of the things that linting is protecting you against isn't actually the stuff that matters for your application. It's the people's stuff. And so much of the process is about people stuff and not technical stuff. And. Keep peeling it back until you're like, okay, here's the amount of interpersonal friction that I'm willing to live with because it allows everything else to be easier.

[00:46:14] **Ben:** And that line might be different for everybody else. It might be different for every company.

[00:46:18] **Carol:** Yeah, linting's nice because it does take away those conflicts that you have between people over unnecessary things.

[00:46:24] **Ben:** Well, that's

[00:46:25] **Carol:** really matter. So, if we all agree to just do it, just let it happen. Let's agree.

[00:46:31] **Adam:** Yeah. I think the true value out of a linter is that it avoids conversations, right? It's a, it's a immediate, it doesn't matter. We can't have this conversation because the linter, the linter answers it.

[00:46:42] **Carol:** did it. Done did it.

[00:46:46] **Adam:** I mean, I won't go on a whole rant or anything, but I do have a blog post called Sweat the Small Stuff, which I guess we'll put a link in the show notes. And it's basically like. Taking that, what you were describing there, Ben, and just like letting that play out year after year, after year, after year, you're going to slowly rot the code, right?

[00:47:06] **Adam:** With little things that don't matter in isolation, but then when 50 developers have been slowly adding their own small amount of rot here and there, all of a sudden you notice like, man, I really hate working on this code base because it's ugly and weirdly organized and. Like half of this function or half of this file is the functions are in an alphabetical order.

[00:47:27] **Adam:** And then the other half of the functions are just like, ah, it just felt like putting it there.

[00:47:32] **Ben:** Totally. And

[00:47:33] **Carol:** I'm that person. I just pick a random spot that I think makes sense. And that's where I put it. Everyone else on my team just goes to the bottom of the file. Like that's where new functionality lives. Like everything's divided between public and private, obviously. So you're like, okay, let's go put public here, private here.

[00:47:49] **Carol:** But I tend to go, Oh, well, this is happening around these areas. So I want functionality to exist together. I like it to be that way. Like if I'm doing this, I want everything that's touching this area, like together. No, it's straight up. Most of the other people are, it goes to the very last one, no matter what. I'm like, okay.

[00:48:09] **Ben:** I've definitely seen all three of those things. I've, I've seen alphabetical. I've seen always to the end and co located and I've seen them mixed in the same file for sure.

[00:48:19] **Carol:** Alphabetical would kill my brain. I can't think like that. I can't spell. Like, don't make me put things in order like that.

[00:48:27] **Adam:** What if your linter did it for you?

[00:48:29] **Carol:** That would be nice.

[00:48:30] **Ben:** I think I heard the craziest thing the other day on the GoTime podcast, part of the changelog series of podcasts. I hope I'm making this up because otherwise it just sounds crazy to me. But I think what they were saying was that when they use a map, I think is what their terminology is, which would be like a cold fusion struct or a JavaScript object, when they use a map and they iterate over the keys, the Golang runtime will purposefully.

[00:48:58] **Ben:** Iterate in random ways every time so that you can't even accidentally expect the keys to be iterated in a particular order. And that to me is, again, like maybe that's not true. Maybe I misheard that, but that to me is almost a perfect example of what we're talking about, where someone was so afraid that a person would make the wrong choice, that they just made a bad choice.

[00:49:24] **Ben:** Excuse my French, like a crazy decision about how the runtime should work to, to stop people from making that choice.

[00:49:30] **Carol:** Oh my goodness.

[00:49:31] **Adam:** I mean, as long as it's performant, I think that's great. Now that's not saying every type of loop is always in a total random order. That's saying for a map, which is, uh,

[00:49:39] **Ben:** like iterating over the keys.

[00:49:41] **Adam:** right. That's a, it's a functional, approach, right? You're, you're saying. Iterate over the keys and replace each key with the value of calling this function on, and passing it that, that current value, right?

[00:49:55] **Ben:** Right,

[00:49:56] **Adam:** Current value in, new value out. It doesn't matter what order they get called in. And so by doing it randomly, if you do have some sort of a side effect bug, Then it's going to become more apparent sooner. I mean, honestly,

[00:50:10] **Ben:** time you run it

[00:50:12] **Adam:** I agree. It does sound a little bit but at the same time, like it also sounds a little bit like big brain, galaxy brain. This is kind of genius.

[00:50:22] **Ben:** I don't know. I don't know.

## [00:50:24] Getting to the Right Amount of Process

[00:50:24] **Ben:** I mean, so, so linting, I obviously have strong feelings about, QA processes. I also have really strong feelings about. I think, I think mandatory and arbitrary QA always seems like very heavy handed to me. I think people should be involved in deciding what to get handed off to the QA engineers.

[00:50:47] **Ben:** The argument is always, but at some point, someone will make a mistake and something should have been QA'd and it wasn't. And then there was a bug and maybe an outage. And that's always how we come back to the, and that's why we need all this process. But we, we've always, I think the issue is we always run into a counterfactual problem, meaning like what Adam was just saying about how, well, if we don't have any process, then over time it begins to rot and everything gets worse and worse and it becomes chaos.

[00:51:19] **Ben:** The problem is, is that we can also find examples in the other direction. That there are companies that are very strict about how they want to architecture things. And it also becomes chaos and it also becomes unmaintainable messes of, you know, things. Of hundreds of microservices and nobody understands how the system works and it's, and it's madness.

[00:51:38] **Ben:** And you're like, yeah, but it's really consistent madness. But, and then there's going to be teams that are chaotic and it still just works really well. And I, you know, I don't know what the secret is in either direction, but it's, it's hard to, it's almost unfair to always use the extreme opposite as the reason to not do something.

[00:52:00] **Adam:** I think if there is a one size fits all solution to this problem, it's going to be develop a culture where it's always okay to question the process and to, to modify the process.

[00:52:14] **Carol:** Amen. I agree on that.

[00:52:17] **Ben:** Yeah, agreed.

[00:52:18] **Carol:** there are no answers, assume there's an issue with the process.

[00:52:21] **Ben:** and then, like, then quickly, you're going to create a culture where every decision has to be documented so that someone can go back and refer to it. And you're like, Oh, it's like, now we have more process.

[00:52:35] **Adam:** Oh man, I'm going through so much of that with the SOC 2 stuff. It's like, You have, you can't just, contract with new customers and bring them on board and do stuff. You have to have like a physical check, not a physical, it can be digital, but you have to have an, an instance of a checklist for the onboarding process.

[00:52:51] **Adam:** And you have to have an instance of your offboarding checklist when a customer like wants to end their contract and you have to like show, okay, this person, you know, filled out the checklist on this date. And it was reviewed and accepted by this other person. And it's just like, it's just, it's a big exercise in CYA, cover your ass.

[00:53:13] **Adam:** and the whole SOC 2 thing, in my opinion, there's, there's a lot of good that comes out of it, but it's, it really is like inventing, a whole, not just a job, but like a whole industry,

[00:53:27] **Carol:** There is. Yeah.

[00:53:28] **Adam:** auditors and documentation people and software needed to get it done. And it's like. It, it, like 90 percent of the stuff that you're supposed to do there is like, obvious.

[00:53:39] **Adam:** The other 10 percent is like, okay, cool, yeah, I guess we should do that, you know, okay, fine. Man, it's just, it's so much, for lack of a better word, paperwork. To prove that you're doing the things that you are already doing. And it's so frustrating to have to spend time doing that.

[00:53:54] **Carol:** But a lot of those, again, went into place because companies weren't handling people's credit cards correctly. The industry starts losing money because of hacks, because of stolen money that they can't recover. Like there's lots of reasons why those things were put into place. But again, You should reevaluate, like, is that process still the right process for this?

[00:54:19] **Carol:** Is there better measures that could be taken that pretty much make this process, like, null?

[00:54:26] **Adam:** And the, the infuriating thing is like, the people that are enforcing these restrictions, Like the PCI, payment card industry, security standards and stuff. Not them specifically, but like really high up organizations within the ecosystem. They're like, Experian, the, the credit score people like had like terrible, terrible security and like massive data breaches.

[00:54:50] **Adam:** It's like. How, how are they not, and you know, you know, for a fact that they were PCI compliant and they probably had, you know, this and that ISO, compliance stuff and SOC 2, you know, whatever, like, was that just like a rubber stamp for them and they got a pass because like, who cares or, or, you know, and yet my little seven person company has to spend 30, 000 last year, you know, Just on, contracts, like software and, and auditor contracts, not even on my time to, to deal with that.

[00:55:21] **Adam:** Like, it's crazy.

[00:55:22] **Carol:** Processes, man.

[00:55:25] **Ben:** So many. It's, it's crazy about just come back to actual laws. Every time you hear about these laws that are on the books

[00:55:38] **Adam:** Oh, yeah, yeah.

[00:55:38] **Ben:** like the 1910s.

[00:55:40] **Adam:** It's, it's, it's illegal to walk your goat across the street on Sundays type thing.

[00:55:45] **Carol:** Mm hmm.

[00:55:46] **Ben:** Absolutely.

[00:55:47] **Carol:** In Alabama, it's illegal to beat your wife with a rod longer, or bigger than your pinky. Mm hmm.

[00:55:55] **Adam:** that's where the rule of thumb thing came from. You could do it as long as it was no wider than your thumb.

[00:56:00] **Carol:** Yeah.

[00:56:00] **Ben:** Oh my goodness. It's crazy what we've had to put on the books.

[00:56:05] **Carol:** Yeah.

[00:56:06] **Adam:**

## [00:56:06] Patreon

[00:56:06] **Adam:** All right. Well then this episode of working code is brought to you by my new brand of potato chips. I'm calling them Beachbody on demand and listeners like you, if you're enjoying the show and you want to make sure that we can continue to keep putting more of whatever this is out into the universe for another nine weeks, then you should consider supporting us on Patreon.

[00:56:23] **Adam:** Our patrons cover our recording, editing, and transcription costs. And we couldn't do this without you. Every of the next nine weeks without them. Special thanks to top patrons, Monte and Giancarlo. You guys rock. You've been with us for a very long time. We very much appreciate your and everybody else's support.

[00:56:36] **Carol:** 100%.

[00:56:37] **Adam:** And as I said earlier, we'll figure it out. We'll, we'll be in touch. and as always, you know, you are free to do with your Patreon support, what you feel is right.

## [00:56:49] Thanks For Listening!

[00:56:49] **Adam:** anyway, we're going to go do the after show thing. If you'd like to hear that, you can go to patreon.com/workingcodepod, and get our after show.

[00:56:58] **Adam:** That's going to do it for us this week. We'll catch you next week. And until then,

[00:57:01] **Ben:** Remember folks, your heart matters.
