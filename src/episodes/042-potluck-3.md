---
title: "042: Potluck #3"
description: 'This week on the podcast, the crew discusses various topics: "Strong opinions, loosely held"; When to upgrade your aging technolgies; The ethics of GitHub Copilot; and Why don''t we see more employee-owned software companies?'
date: 2021-09-29
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/042-potluck-3/id1544142288?i=1000536979967"></iframe>

This week on the podcast, the crew discusses various topics: _"Strong opinions, loosely held"_ - is this a statement with noble intent? Or, does it encourage people to dismiss past evidence and the experiences that have shaped their current view of the world? When is it time to upgrade old technology choices? When the time it takes to upgrade is time _not spent_ on building features, at what point is that cost justified for the business? GitHub Copilot helps you write code, but who gets credit for that? Is it even legal? Have engineers demonstrated enough responsibility in the past to merit an _even more powerful_ copy-paste programming paradigm? And finally, why don't we see more employee-owned software companies? If engineers had more material skin in the game, wouldn't they be _more motivated_ to ship product?

All that _and more_ on this week's show!

## Notes &amp; Links

- [Jeff Atwood: Strong Opinions, Weakly Held](https://blog.codinghorror.com/strong-opinions-weakly-held/)
- [GitHub Copilot](https://copilot.github.com/)
- [The Changelog: We ask a lawyer about GitHub Copilot](https://changelog.com/podcast/458)
- [The Great Game of Business](https://www.greatgame.com/about/what-is-the-great-game-of-business)

Follow the show! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media][editor].

[working-code]: https://workingcode.dev/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[editor]: https://www.zcross.media/
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/042-potluck-3.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Carol:** I've only started seeing posts for people using the beta, like actually using it like a few weeks ago. So that's when I started seeing blog posts and stuff. So maybe they couldn't post about it or anything, but they know I've only started seeing it for a

[00:00:11] **Adam:** So Tim it's like complete for coding, but it's not just completing, like the word you're typing is completing the thought in your head. Right.

[00:00:18] **Carol:** like you caught, like if you write a good comment about what you're trying to accomplish, it can generate

[00:00:24] **Tim:** According to uncle Bob, there is no good comment.

[00:00:27] **Carol:** Yeah. Hey, they're not uncle, Bob's not going to like this at all. But they were saying like the first pass of some of this with some Python tests, it was in Python code that they had, it had like 47% accuracy, like of trying to figure out what the developer was trying to accomplish.

[00:00:44] **Carol:** But my whole thing with this is I was trying to figure out the, who gets credit for this code. It's other generated is not my code

## [00:01:07] Intro

[00:01:07] **Adam:** Hey everybody. It is show number 42 and on today's episode. We are going to have another potluck. we'll figure it's been a while it's time to do it again. So for random topics that we all bring in here with no prior discussion or planning, you're going to see what happens.

[00:01:22] **Adam:** but first as usual, we're going to start with our triumphs and fails, and then it looks like it's your turn to go first, man, what do you got going on?

## [00:01:28] Ben's Triumph

[00:01:28] **Ben:** I'm going to go with a triumph, which is that I spent yesterday and today slicing and dicing data in MySQL. And I think this actually dovetails quite nicely with our previous episode on transactions. I, in our previous show, Adam, you had mentioned that one of the nice things about SQL is that you don't always know how you're going to use your data and you have reporting and you have crud pages and you have other kinds of usages that you need to use.

[00:01:53] **Ben:** And that was with me in the last two days. we essentially had a client who accidentally evicted a bunch of users. Hundreds of users from their system. And we have a lot of historical data. So one of us user gets evicted from a system. We sort of just end a lot of the records. We don't necessarily delete.

[00:02:10] **Ben:** We do a lot of soft deleting. So I spent the last two days comparing historical records to current records. Cause then they had re added a bunch of users to the system. So I had to kind of do these differences between the previous day of the date and the currency, but it was so exciting because you haven't really lived until you've joined a table back to itself and then had to make sense of the, of how those two, relationships match up.

[00:02:34] **Ben:** But, I don't know. It

[00:02:35] **Ben:** Were you trying to like restore? Is it like they, you said they evicted a bunch of users and then re added them where you trying to like restore them as if they had never been evicted. I'm guessing evicted means like soft delete. Yeah. Yeah. So I had to now, not only did I had to bring back some of the users, but then I had to bring back some of the kind of peripheral data that was associated with the users, but had been disassociated when the user was evicted. But, and then I was using SQL statements to generate other CQL statements.

[00:03:03] **Ben:** So I had these really big, complex SQL statements. And then once I would get the records, right, then I would copy and paste it. And then I would, instead of having selective columns, I would do a select of concat where I'd be like insert into table and set. And I had a bunch of columns that John can cast Daymond, so I'd run it.

[00:03:19] **Adam:** And it would produce, results say with 26,000 record insert statements. And then I'd run those in batches of a thousand, just copy and paste them into another terminal window. But, I know just data is thrilling. You are a strange

[00:03:32] **Ben:** MySQL is thrilling.

[00:03:34] **Tim:** Yeah,

[00:03:36] **Ben:** It's so good. It makes so much sense when you, when you're, I don't know.

[00:03:40] **Tim:** I agree. I love it. When you can like transform data, then. Certain trends are out. I also like building charts for data to do visualizing data and seeing stuff that you really just can't see from the raw data.

[00:03:52] **Ben:** yeah, it's a lot of fun. And, I don't know, I've been thinking about indexes a lot lately because of our previous show and, it just all felt very timely. Being able to manage a whole bunch of different data using different queries, so

[00:04:05] **Tim:** Th the data show. That's the one where I lost connection. Right. Wasn't on for

[00:04:08] **Ben:** Yeah.

[00:04:09] **Adam:** Yeah. We said Postgres for you a couple of times.

[00:04:11] **Tim:** thank you. Thank you.

[00:04:14] **Ben:** but, yeah, so, uh,

## [00:04:16] Tim's Triumph

[00:04:16] **Tim:** So.

[00:04:17] **Tim:** triumph, I mean, I guess I call it a tribe. I just really love that the past couple of weeks. customer meetings and also customer prospect meetings. And when they come up with some sort of new feature or new use case that we'd never really had foreseen, there's been times when we've been in a demo when someone's like, Hey, how do you do this?

[00:04:34] **Tim:** And I kind of know what they're talking about, but, yeah, just being able to go, oh yeah. we do that. And then before the next call, the next week, you add that new feature to prove it to them. yeah, we'll schedule a demo. We'll do that. Totally. Just building from scratch. what they're asking for, but, including it into the overall part of the product, I just love being able to do that because sometimes you, when you build a product, you don't foresee all the uses that people are going to need for something. so, for instance, the one I'm thinking of is someone brought up,how do you guys have. Oh, we're sending money to people. Well, how do you OFAC that there's laws, OFA C I forget what it stands for, but there's terrorists lists of people that have sanctions on them and you're not supposed to send those people money or otherwise you get in trouble.

[00:05:21] **Tim:** how do you handle that? Well, quick search. There's tons of APIs out there to do that. And they're pretty inexpensive, so, oh Yeah.

[00:05:27] **Tim:** We totally do that. And, but, by the next demo We were, we've already put it into the product and can, actually do it. So it's not necessarily a lie, you don't say here's how we're already doing it.

[00:05:38] **Tim:** You just say, oh yeah, we do that. So,

[00:05:40] **Carol:** We

[00:05:41] **Tim:** Oh yeah.

[00:05:42] **Carol:** we sure can.

[00:05:43] **Tim:** then you just throw out a lot of acronyms and words that make it sound like, what you're talking about. And then you. just go build it behind the scenes before the next demo.

[00:05:50] **Adam:** Yup.

[00:05:51] **Tim:** I just love that.

[00:05:52] **Ben:** One of the nice things about putting your application behind a CDN content delivery network is that a lot of CDNs will inject a country code header as it passes through to your origin servers. So you can, we use those headers to do the GDPR stuff, as well as the OFAC stuff, which has been pretty helpful.

[00:06:11] **Tim:** very cool. Oh, you Carol.

## [00:06:13] Carol's Triumph

[00:06:13] **Carol:** Yeah, I'm going to go with the triumph too. And this week yeah. Made my one-year market clerk capital. So I, it popped up in my email and I was like, holy cow, I've been here a year. And I feel like I'm learning everything all over again. Cause now I'm going back to this main project. Cause I've been on this other one for so long.

[00:06:33] **Carol:** I'm like, wow, it's been a year.

[00:06:35] **Adam:** today as we're recording

[00:06:37] **Carol:** Uh,it was Tuesday. Yeah, it was

[00:06:40] **Tim:** two days

[00:06:41] **Carol:** Yeah. So two days ago. Yeah, you're in today, so woo. They didn't fire me. Yay.

[00:06:47] **Adam:** cool. We'll congratulate.

[00:06:49] **Carol:** Yay. Thanks. What about you,

## [00:06:51] Adam's Triumph

[00:06:51] **Carol:** Well, I guess there's another four for four. It's like, we need a triumph sound when we get four for four trials, but yeah, that, uh,We need the gongs

[00:07:02] **Tim:** I liked that. I liked that.

[00:07:03] **Carol:** I forget what that's from, but yeah, that's a classic. Anyway, I've got another triumph here, so I'm going to get quacked for this, but I'm okay with it. I just wanted to say, yo ESPP build. If you've not heard of it, it's a, like a con it's a sort of, I would call it a new generation of like bundlers and transformers for JavaScript code. It is fast.

[00:07:26] **Carol:** that should be its tagline.

[00:07:27] **Adam:** there's a lot of things that are neat about it, but. Yeah. I mean, it's one of the things that, Sean was mentioning in our last episode, how like this new generation of tools they're built using tools other than JavaScript, right? So web pack and parcel, and these other things were built using JavaScript to compile the JavaScript, which is fine because then JavaScript people can contribute to it.

[00:07:47] **Adam:** But if you don't need the JavaScript community to be able to contribute to it, and you're okay, kind of moving that responsibility outside the community, then these other systems level languages, rust, and go, and some other stuff can give you sort of out of the box, a whole new level of performance you can get to.

[00:08:07] **Ben:** So we, I did a little check. we have this kind of ties into my topic for the potluck, but, so our application has 26 JavaScript bundles. And when we get to my topic, we'll talk about that. But 26 bundles that we build an and, previously we were building them using Browserify via grunt. Oh,

[00:08:27] **Adam:** Yeah. Yeah.

[00:08:27] **Adam:** And I'll talk about that later, but, to do a full JavaScript rebuild for all of our public facing and admin, like the whole soup to nuts took approximately 90 seconds a little under like 85 and change. And that's on my machine, which is I have 64 gigs of Ram and a top and CPU. And, when I built those desktop, I spared no expense on the hardware, overdo it.

[00:08:52] **Adam:** So it'll last a long time. And so 85 plus seconds to build everything. When I built, when I converted everything to run with IES build, I'll tell you the number in a second, but when I built it, so when I ran it for the first time, I was like, there's no way that was correct. It ran so fast that I was like, I had to have done something wrong.

[00:09:14] **Adam:** And I

[00:09:14] **Tim:** thought he pointed it

[00:09:15] **Carol:** you're hunting for errors. Yeah. You're like.

[00:09:17] **Adam:** Right. Yeah. Like I, it was like, okay, start up, shut down. Don't do nothing. That's how fast it runs. Right. Because I went in and I was like, add a debug output, like make sure you're actually running each bundle. And like, what's the size of the completed bundles and stuff. And I mean, so here it is, it goes, it went from 85 seconds and change to five, one hundredths five over 100 of one second.

[00:09:38] **Tim:** Wow.

[00:09:39] **Carol:** Oh boy.

[00:09:41] **Ben:** even a

[00:09:41] **Adam:** I mean, it's,it's definitely, parallelized, right? So it runs as a promise. It returns a promise. And so you can, what I'm doing is I have a script that, does a promise dot all await promise at all on each of the bundles individually being built. And so it was running. It could effectively be running.

[00:09:59] **Adam:** what'd I say 26 parallel builds.

[00:10:03] **Tim:** Yeah.

[00:10:04] **Adam:** when I did my naive, is this even worth pursuing quick, hacking. I got it down to like seven seconds and I was really impressed with that. It's like, yeah. Seven seconds. So, yeah. I'm just, my pants are blown off or is that a saying that the thing people say

[00:10:21] **Carol:** I've never heard it before, but we'll go with the S sure.

[00:10:25] **Adam:** it's super fast and I'm just excited.

[00:10:26] **Adam:** we're playing with new tools and, that kinda is what made me think of my topic for today. So,

[00:10:32] **Tim:** Cool.

[00:10:33] **Carol:** Well, that's

[00:10:33] **Adam:** yeah. All right. Potluck time, who wants to go first?

## [00:10:37] Strong Opinions, Loosely Held

[00:10:37] **Ben:** I've been thinking a lot about the phrase, strong opinions, loosely held. And it's a phrase that I've heard a bunch of times in the last couple of years and on its surface. I always think about it as this noble intent that I'm open to having my mind changed. And I don't have to die on any Hills about things that I feel, more, I think about it, the less, I like it as a statement of intent, because I think about my learning over the last few decades.

[00:11:07] **Ben:** And so much of what I do is try to build a very strong mental model of how I think the world of programming operates and how applications operate and how databases work and how control flow works and how to, run get based workflows that make sense for your team and how to deploy often. And I'm constantly trying to find the best way to do so.

[00:11:31] **Ben:** For my particular circumstance, my particular team, my particular set of skills and the idea that if I have a strong opinion about something, I should just be open to letting it go seems crazy. Like I wouldn't want to go to a surgeon and me and being like, oh, well, in order to operate on your tumor, like we absolutely

[00:11:50] **Adam:** got this new JavaScript

[00:11:51] **Ben:** And I'd be like, yeah. And then I'm like, well, hold on, what about this other opinion? And then I don't want I'm brain surgeon to be like, you know what, that's a good point. I'm going to totally forget about it. The last three decades of medical training that I've had. And so like, I understand the idea that when faced with new evidence, it's good to be open-minded.

[00:12:13] **Ben:** And if there's something that comes your way, that's truly better than your previous opinion, then you do want to be able to grow as a human being and evolve your thinking. But just generally speaking this idea that if you have strong opinions that are hopefully based on. and evidence, like why should you be open to change your mind really quickly?

[00:12:36] **Ben:** That, that seems kind of crazy. The more I think about it.

[00:12:39] **Tim:** the way you weigh your word, it. sounds doesn't a little passive aggressive. I have a term that I like better than that one in that is, we were talking about it at work yesterday. Disagree, but commit.

[00:12:54] **Ben:** Oh yeah.

[00:12:55] **Tim:** So, I mean, because I mean that, that does happen, right? So you have a strongly held opinion. I have a strongly held opinion and they differ from each other, right.

[00:13:05] **Tim:** There's merits to both. And there are cons to both as well. At some point you just can't. I mean, if you're fully entrenched in both sides are entrenched on those. Then nothing's going to get done and no decision will be made or the worst decision will be made just because someone else will just do it while everyone else is arguing.

[00:13:25] **Tim:** So, and so it's like, yeah. at some point you just get like, look, I disagree with your method, but you know, someone has to make a decision here where, which way we're going with me or Ben. And then we commit to it. So the, and the commitment isn't saying, Hey, I agree with this way. I still disagree.

[00:13:43] **Tim:** I still totally disagree with the way we're going, but I am not gonna bring it back up again. I'm not going to berate people over this. I'm just going to commit to it. I'm going to help build it. I'm going to do my best to make it work. And if the cons that I said are going to happen with that approach, come out and bite us in the butt.

[00:14:00] **Tim:** It might say a little, I told you So but.

[00:14:03] **Adam:** So it sounds like the commit part of that disagree about commit is on the part of the person who is not getting their way. Right? So you and Ben are not arguing, but you know, trying to figure out the right approach to a problem and you can't find a clear winner. So somebody, whoever has the, however, it can be decided, some, a decision is made you pick a direction, it goes so that you don't spend your wheels for six weeks arguing over the decision and the person who doesn't get their way just has to be like, okay, well, I descended and now I'm just going to respect the decision.

[00:14:37] **Tim:** cause the worst is when you have someone who disagrees and then undermines.

[00:14:44] **Carol:** The word.

[00:14:46] **Ben:** at work. The places that I've heard that most often are kind of top down where the product team has an idea. they pitch it to engineers and the engineers don't want to do it, or they don't want to build it the way that the product team is suggesting. And at some point there's a power imbalance.

[00:15:04] **Ben:** in our, I don't know about all companies, but in our companies that are especially product led, the product team will eventually look at the engineers and be like, I need you to disagree and commit because this is how we're building it. And I have fantasized so many times about using that exact phrase in my own conversations, but like going up the chain where I'll say, Hey, I'm going to build this thing.

[00:15:26] **Ben:** And a product manager will come to me and be like, well, that's not really on our roadmap. And I want to be like, well, I need you to disagree and commit because I'm building it.

[00:15:34] **Carol:** So I think I'm looking at this slightly different than you are, or I'm hearing it different than how you guys are kind of saying it. Maybe it's a female male thing. I don't know yet. We'll figure it out. So I take it as that, like, I'm coming to you with this big statement, with this big thing that needs to happen or this my big opinion.

[00:15:54] **Carol:** Like what I'm held strong too, but if the data like isn't there to back it up, or it can't be held or it can't be done, I will like gladly change my mind. Like to me, that's what, how I perceive the, strong opinions loosely held is that I have a passion for it. But if you show me that it's not that I'll gladly.

[00:16:14] **Carol:** Just go. Alright, cool. Then that's what it's not. And we'll go on.

[00:16:17] **Adam:** Yeah, I'm kind of with Carol, I don't see a problem with the phrase, the phrasing, strong opinions weakly held to me. It just, I think you kind of described it the way that I think about it, which is that, you're open to having. But in the meantime, you're going to believe in what you believe in and you're going to believe in it fully.

[00:16:35] **Carol:** Yeah. You got to prove me wrong.

[00:16:37] **Ben:** Well, okay. So I think maybe the part that rubs me the wrong way is that when I've heard the phrase and I've tried to incorporate it into my own thinking, it's almost been this like moral, not moral is not the right word, but this like behavioral compass where like, this is the thing I'm trying to attain, that I should just be able to detach from my strong opinions, almost like a Zen like state instead of feeling like I have to claim to my strong opinions and maybe the part that rubs me the wrong way is that in there as the assumption that I place on it, which is that if I have a strong opinion, that is based on something very important.

[00:17:16] **Ben:** Like past experience or evidence. And then someone just tells me we're not going to do it that way that I should just magically be able to be like, oh, I'll just change my mind then. Like,

[00:17:26] **Carol:** No, I don't, I

[00:17:27] **Adam:** no, that's not what we're saying.

[00:17:29] **Ben:** so I don't know. So maybe that's not how anyone intends it. Maybe that's just how I hear it.

[00:17:34] **Carol:** Maybe, because I think if you are going at it, you've probably taken the time to make sure you have the data, or you have the proof to show that this is a good opinion. Like you've taken the time to work it out. So if someone just says no, then they're, going against everything you've already figured out.

[00:17:51] **Tim:** proof isn't really an opinion.

[00:17:52] **Carol:** just facts, but we're going to call the opinions and not sound like jerks.

[00:17:56] **Ben:** Well, I mean it, especially in our world, it's just say anything as a fact is crazy. It's not crazy, but it's like so much as dependent on the team and the product and the skills and the time

[00:18:08] **Adam:** the facts can change over time when you learn more, when the ecosystem changes or whatever.

[00:18:12] **Tim:** One thing I take issue with, you said, Ben, the situation you said is where you have the product team saying, Hey, we need you to build this way. I don't think product teams should have a say in how it's built.

[00:18:24] **Carol:** That's not their

[00:18:25] **Tim:** you know, the product team is like, what features do we need to have, w what's going to satisfy the customer need what's the roadmap at me?

[00:18:31] **Tim:** why should they have an overriding say in how it's done?

[00:18:36] **Ben:** Ah, organizations are messing, man. Software is messy. That's all I consider.

[00:18:42] **Tim:** They should be just like, here's what we need. Can you fulfill it? Yes, we can. don't tell me, don't micromanage me and say, we've got to use this database and you gotta use this to, what, if we can do it, it's within budget. We're doing it this way.

[00:18:52] **Ben:** Agreed.

[00:18:53] **Carol:** I'm hearing us all say is that our opinions matter and we should new everyone should just do what we say and things would be much better.

[00:19:01] **Adam:** would be much happier at work if everybody did what I said, what I thought was important.

[00:19:04] **Carol:** Right? Right.

[00:19:08] **Ben:** Alright, I think I've covered it. I think we've covered it.

[00:19:11] **Carol:** You didn't even get cut off.

## [00:19:12] The Lifespan Of A Javascript Application

[00:19:12] **Adam:** So what was my topic?

[00:19:14] **Carol:** JavaScript

[00:19:15] **Adam:** Yeah, the lifetime, what is it?

[00:19:16] **Adam:** the lifespan of a JavaScript application. Right. and so I mentioned, we have this application. That, we are, the production builds are still built using grunt to run Browserify. And I mean, if we're going to get into how old this thing is, we have like transforms for Browserify that,we'll compile our handlebars templates, to, to basically put stuff together.

[00:19:41] **Adam:** This was before react was ever like this application was born well before react. And, maybe from before Webpack,if it is, if Webpack already existed, then it wasn't as widespread and common as it is. Now. This was in the heyday of grunt and gulp. and, code splitting was not really a thing that people talked about a ton.

[00:20:03] **Adam:** Like it was still at that point in the landscape when people agreed that it was a good thing to do, but nobody had a good solution for it. It's just like, you need to be doing this and then you figure out how, and so. We figured out a way we just kind of designated, these are the break points between the modules of our applications.

[00:20:18] **Adam:** Every module gets its own bundle, and then there's sort of a core bundle that's included on every page. cause it's that the stuff in there was that common that every patient needs it. So between all of that, we have 26 bundles. and, the topic that I want to talk about, so lifespan of a JavaScript app is this is really old tech.

[00:20:35] **Adam:** And I talked about how I've been playing with S bill to try and speed up that bundling process. And it just made me think like this application is six to eight years old and it definitely has been a growing pain for a long time for us. And, I wanted to talk about like, what is, obviously, you don't want to go from something that's working to something that just came out last week.

[00:21:03] **Adam:** Nobody's using it yet. It's not even version one point, oh, that's the wrong move, which is, this is the point where I say I've been looking at, just for fun. Cause I, I'm on this, this kick of trying new things, but I've been looking at spelt, cause again, cause Sean was talking it up last week and it caught my ear and I'm really interested in there not 1.0 yet.

[00:21:23] **Adam:** And I think spelt is, but the spell kit is not, which is like the next JS of spelled. and yeah, so just like what w what are the warning signs that you look for that it's like, okay, this is going to be coming due soon. We need to think about rearchitecting this application in a way that can reuse a lot of what we have.

[00:21:45] **Adam:** Yeah, I'm not talking about a full rewrite of all the JavaScript. I'm just saying like the tooling needs to be upgraded. Right? it's rotten to the point now where, I mean, it still works, but for years we've already felt behind the curve and now the curve is staring down the barrel of, like, an order of magnitude, if not better change in the way things work,

[00:22:10] **Carol:** But you're not talking about new development areas. You're talking about replacing

[00:22:14] **Adam:** all of the above, we, I said this application is like six to eight years old. We've never stopped developing on it. Right. The product is for Mo for all intensive purposes. Never done. Right. We're adding new modules, we're adding new features. We're adding more reports, we're adding, this and that.

[00:22:27] **Adam:** Swam. Most of us have jobs. Yeah.

[00:22:29] **Adam:** And

[00:22:31] **Carol:** Never done.

[00:22:32] **Adam:** And yeah, so just like, and that's the thing is you can't, you can, you absolutely can. Say, okay. all new development is going to be done over here with a brand new react app, and it's going to use these things and old stuff is, we're hanging on by a thread there sort of thing.

[00:22:48] **Adam:** And if you get the opportunity to migrate it, then you migrate it. But it's tough. Hi.

[00:22:53] **Carol:** I mean, and there's a cost side to that. I mean, it's not just time. It costs money to take your people to write, to rewrite something that's already working. that's hard to

[00:23:02] **Tim:** is it you rewrite? I don't understand. Is it the JavaScript rewriting or just the tools use to like bundle it

[00:23:08] **Adam:** that's the thing is I did this, it was so exciting for me. I did this conversion in my own free time. in one week, and it still has to go through code review. there's no, for IES build so far, I wasn't able to find like a plugin that can do handlebars templates and we only had like 15 of them or something like that.

[00:23:25] **Adam:** So I just rewrote those as functions that take the exact same inputs as the handlebars template would, and it returns the exact same output, but instead of using handlebars, that's just a function that does some

[00:23:35] **Tim:** The JavaScript function.

[00:23:36] **Adam:** Yeah, it does the string concatenation manual. And another thing that we didn't have when this application was born, that we do have now is the, the backtick strings at the template literal thing.

[00:23:46] **Adam:** And you're able to do like the tokens in there that makes it so much easier to do the string concatenation stuff. so it's, I did that, like I said, in all of that in an evening, converted all the whole build process and the handlebars templates and, what was the other thing? Oh, so our existing Browserify, pipeline each bundle.

[00:24:06] **Adam:** can have more than one entry point. So normally with one of these bundles, you give it a single file and index dot JS or whatever, and it sort of follows the dependency tree out and bundles everything together. I think what Browserify is doing is, doing that same thing, but then if you have multiple files as the various entry points, then it takes that resulting bundle.

[00:24:27] **Adam:** And if you had like 300 points and you've got sort of three sub bundles and it just concatenates them together, that's, I'm totally guessing, but that's what my guess is.

[00:24:35] **Carol:** It sounds fancy and right.

[00:24:37] **Adam:** and so, but ESPN doesn't do that. So I had to figure out like, what was the actual value in the multi entry point bundles that we were getting?

[00:24:45] **Adam:** And, the short answer is we weren't getting anything. We were just doing it cause it seemed like it needed to be done. And I don't think it. now that said, I did this evening of work. There's a poll request waiting to be looked at code review and everything. And one of the things we need to do is we have this huge application that is built on top of 26 different JavaScript bundles.

[00:25:07] **Adam:** And now we need to go and test and make sure that nothing broke, right. Because of some obscure feature that didn't doesn't work any as built or got built incorrectly or whatever. So there is that it's, that's the downside, but, it's I guess, so we talked about the there's a cost to, upgrade the application to rewrite it. you decide everything is going to be react or whatever. there's also a cost associated. Having to maintain old code right there. We have more than one application microservices and whatever that are on like a Webpack version.

[00:25:40] **Adam:** That's like three or five versions old that we just, the application has been doing fine and production without ever needing to be touched. So why touch it? And so now we're five versions of Webpack back and the Babel stuff doesn't work anymore. And this and that. And it's like, anytime you need to make a significant change, you either have to spend a week fighting with it, to get it to work, or you have to spend that week upgrading everything and dealing with all the fallout of those upgrades.

[00:26:05] **Adam:** And it's either way it's terrible.

[00:26:09] **Carol:** So that's where you should eat it and go ahead and upgrade. So if you do have a major edit that needs to be made or a major rewrite, you go ahead and eat that time then because otherwise you're going to be facing this in six months when you need to make a change, when something has.

[00:26:21] **Tim:** Carol just told you to eat it.

[00:26:23] **Adam:** she did,

[00:26:24] **Carol:** it.

[00:26:24] **Carol:** You eat, you eat that. So you're going to lose money either way. We know it's not going to be cheap to upgrade if you're not constantly upgrading and maintaining, if you ever get behind, it's going to be expensive. So that's where if you have to do it, go ahead and put the money in

[00:26:39] **Adam:** And generally the way our organization is whoever's doing the work kind of decides, is this worth doing upgrade or should I try to just kind of grit it out? And I'm the guy in the background when it's not me doing the work, I'm the guy in the background is like, it's probably smarter to upgrade, w we're going to have to run through this all again, next time.

[00:26:58] **Adam:** And if you upgrade now, then when we have another feature we need to add next month and we don't have to go through this, but,

[00:27:03] **Tim:** And that's actually one thing I do like about the industry that we're in and with financials and credit cards is PCI basically says you can't be using tech. That is,not supported anymore, into life. Right. So it's like, yeah.

[00:27:17] **Tim:** we're constantly having to update because we won't pass our PCI.

[00:27:21] **Tim:** If we're on like something that's been deprecated for two years and not supported anymore. And there's no security updates weren't anymore. So.

[00:27:29] **Carol:** As security holes

[00:27:30] **Adam:** less than a minute on the clock and there's one more thing I want to say here. So, dependent bot, we have, been turning that on for all of our JavaScript apps and it is awesome. You, it works the best. If you have tests that you can run. Cause it'll, you get the dependent bot PRS and it says, okay, there's a new version of just available.

[00:27:45] **Adam:** Here's it creates a branch with that dependency upgraded. And if your, stuff is set up right, then your tests will run automatically and you'll be like, oh look, there's a new version. And the test pass, I can merge this right. If you have comprehensive and automated testing, not to stare directly independence Seoul here, but,

[00:28:03] **Carol:** Depends

[00:28:04] **Carol:** about

[00:28:05] **Ben:** just lucky. I didn't bring up linting and my strong opinions loosely held.

[00:28:09] **Adam:** yeah, I didn't think of that, but that's definitely one of your strong opinions. So a few more seconds. Anybody have anything else on this topic you want to say?

[00:28:19] **Ben:** It's just really hard it's because, and anytime you're upgrading you're by definition, not building something else, which, if you're a S a you, I know you have a, you're a small scrappy team. Like when someone's not working, that's like a real impact on

[00:28:33] **Adam:** Yeah. I mean it's

[00:28:34] **Ben:** It's not like you're a thousand engineers and taking a few out of rotation to upgrade stuff was going to be like a drop in the bucket.

[00:28:42] **Ben:** it's like.

[00:28:42] **Tim:** I don't know, even with a thousand engineers, I don't think that's an, a drop in the bucket. Right. it's like the organization gets used to the certain amount of progression. Right. And so to say, Hey, we need to cut this down by even X percent, Amanda. It was like.

[00:28:56] **Tim:** I don't remember what's going on her.

[00:29:00] **Adam:** oh, and there's our time. Next topic. Who's up? Why don't you go?

## [00:29:07] GitHub Copilot

[00:29:07] **Carol:** Alright. So I have been really fascinated with get hub copilot. So I think Adam knows what it is. Ben, do you know what it is?

[00:29:18] **Tim:** I'm not from, I'm not familiar.

[00:29:19] **Carol:** you're not familiar. All

[00:29:21] **Tim:** I'm an open vessel.

[00:29:23] **Adam:** Yeah. So, you used it at all?

[00:29:25] **Carol:** correct me if I'm wrong on no, I'm not on the, I'm not on the list yet. I've been waiting. I've been waiting, but I'm not been invited.

[00:29:32] **Carol:** I'm not a cool kid. Maybe one day,

[00:29:33] **Adam:** I didn't even, I didn't

[00:29:34] **Carol:** and I'll get the invite. You didn't sign up. So I asked you when you sign up, how often you use visual studio code and I'm like every day, all the time, that's all I use. So I was like, Ooh, maybe that'll get me bumped up because it's only available in VSTS.

[00:29:49] **Carol:** So, get hub. Copilot is a AI program that they have created. That's basically pair programming. So it auto generates code. It will help you auto-generate test. it's powered by open AI, a new like project that they have going on. Like this came out during the summer, but I don't think the beta started till a few

[00:30:12] **Adam:** Nah, it's more than a

[00:30:13] **Carol:** Like that's when I finally, well, I've only started seeing posts for people using the beta, like actually using it like a few weeks ago. So that's when I started seeing blog posts and stuff. So maybe they couldn't post about it or anything, but they know I've only started seeing it for a

[00:30:26] **Adam:** So Tim it's like complete for coding, but it's not just completing, like the word you're typing is completing the thought in your head. Right.

[00:30:34] **Carol:** like you caught, like if you write a good comment about what you're trying to accomplish, it can generate

[00:30:39] **Tim:** According to uncle Bob, there is no good comment.

[00:30:42] **Carol:** Yeah. Hey, they're not uncle, Bob's not going to like this at all. But they were saying like the first pass of some of this with some Python tests, it was in Python code that they had, it had like 47% accuracy, like of trying to figure out what the developer was trying to accomplish.

[00:31:00] **Carol:** But my whole thing with this is I was trying to figure out the, who gets credit for this code. It's other generated is not my code. Like, I feel dirty about this. Like, I feel like, oh, it's like copying and pasting from stack overflow. Like I just feel gross,

[00:31:16] **Adam:** it gets worse. So, it's machine learning, right? it's trained on a dataset of basically all the open source code on GitHub. Right. And it's looks at what you're typing and it's like, oh, and actually I, from not mistaken, it can look at like the other files in your project, your file structure and the name of the file and take a blank file and suggest what should go in it.

[00:31:36] **Adam:** Right. You're writing a test for this language and it's next to this file. And it's got the same name as this other thing with that spec dot JS instead of dot JS. Right. It's like, oh, you're testing

[00:31:44] **Carol:** So they haven't,

[00:31:46] **Tim:** Guys Skynet's here, guys. Skynet

[00:31:48] **Carol:** they haven't publicly, they haven't publicly said that part of it yet or nothing I've found. Cause they're pretty much like the only context that this has available to it is what's in the

[00:31:57] **Adam:** Okay. Maybe I made that up in my head. Sorry, but

[00:32:01] **Carol:** no someone may have posted it, but get hub hasn't said that yet,

[00:32:05] **Adam:** so here's the thing, here's the rub where I think if you haven't already seen this discussed, you probably will.

[00:32:11] **Adam:** the thing that a lot of people are upset about because it's unclear is there is an awful lot of GPL license code on get hub.

[00:32:19] **Adam:** And the GPL license specifically says you're allowed to use it, but anything you build with GPL code has to also be released under the GPL. So you can't put GPL code into a, non open source or non-free application. Right. And now I'm not a patent attorney, but I'm pretty sure that's the interpretation.

[00:32:42] **Adam:** that's pretty close to the interpretation of the GPL. and so there's this whole kerfuffle going on of is a copilot building code containing snippets of, or even based on, snippets of code that's released into the GPL. And if so, does that affect your code that you write with that?

[00:33:05] **Ben:** Yeah. So there was actually a really interesting episode. I want to say it was on the change log, where they were interviewing a patent lawyer about this very specific thing. And like half of the show centers around the concept of fair use within patented material. And I'm not,

[00:33:21] **Carol:** And copier and copyright material.

[00:33:24] **Ben:** Yeah. And, I think the general gist of that is that our laws allow you to use some small portion of an overall.

[00:33:33] **Ben:** In, when you're writing a critique of it or you're framing it in some other conversation without infringing on the copyright or the patent. And, they were saying that it gets a little funny because GitHub uses entire repositories of code in order to train their machine learning algorithms.

[00:33:52] **Ben:** But the developer who uses copilot to write five lines of code, like that five lines of code is such a tiny fragment of, a multi-million line of code project that they fall under different kind of a category categories. A fair use is it's super, super interesting show.

[00:34:08] **Carol:** Yeah. I listened to that, to the example that they gave was like a teacher in a classroom can use a clip from a movie without having to request authorization to show. And she can't be held responsible for it if she shows us her classroom, like, cause she's using it to criticize or to teach from it.

[00:34:25] **Carol:** And then it becomes, okay, so I was like, Ooh. So the code who owns it, who owns the code that this is gender that's being generated, like who gets credit? And the way get hub lays it out. It's like you don't give credit to the eat pen that you use to write down your notes. You don't give credit to the compiler that compiles your code.

[00:34:46] **Carol:** It's still yours. So this is, they're treating it as no different, there's no difference between the items. And I'm just not for sure how I feel yet. Like I'm not worried that this is going to take my job and that this is going to like replace me. I'm just more of like a, like an impassive. Is this ethical?

[00:35:05] **Carol:** Cause I feel like I'm cheating. I feel like I'm taking something. That's not mine. And I shouldn't be doing that. Like if I'm going to write it, it should be something I've written and not something that someone else wrote for me. And I took credit for it and then took a nap because it got done faster.

[00:35:19] **Carol:** Like, I don't

[00:35:20] **Tim:** I just kind of question though, if your spellcheck was only right, 47% of the time. Cool. How much would you trust it? Right.

[00:35:30] **Carol:** NAMI, I think you still have to, but I'm sure it's going to speed things up. Like if it could, auto-generate my functions for me, just with the variables I put in knowing from some comment like that just gets me at a cleaner starting point or if I can like import my Jess library and go, okay, this is the test that we're going to be writing and it knows how to generate tests to get me on a good path.

[00:35:51] **Carol:** Then that's really

[00:35:52] **Tim:** I'm all for generating tests. That's great.

[00:35:54] **Carol:** just don't know. Yeah. I've always wanted auto generated test.

[00:35:58] **Tim:** But I just feel if my code is so predictable, I must be doing a lot of boiler plate that it's like, oh, you're doing this again here. Let me do it for you

[00:36:08] **Carol:** Yeah. I don't know about that yet. I know that from the posts I've saw, the people who've been doing it are like, you have to write very small and very concise functions to make it work. it's not well with big, complicated logic, but that's how programs should work. You should have small pieces that do the bigger job.

[00:36:24] **Tim:** uncle Bob agrees.

[00:36:27] **Carol:** But the comments, sorry, uncle Bob. Yeah, it seems really cool. I'm excited. I hope I get an invite. Oh, and they're going to sell it. It's not going to be a free tool. It's going to be obviously something that they sell, but I would love to be in the beta on that and just see how it

[00:36:42] **Adam:** I kind of put it in this, in my mind, in this category of like low-code no-code tools. And as much as I am a new technology person, I just don't believe it like, right. I see how unique every bit of code that I write is and how specific it has to be. And I just setting copilot itself aside for a second.

[00:37:05] **Adam:** I feel like those other things low-code, no-code just the Lego block programming is just, it doesn't seem realistic to me. It doesn't seem like it's actually going to be attainable.

[00:37:18] **Ben:** Yeah, I agree. Or like, it works for a certain swath of applications,

[00:37:23] **Adam:** was the, was that like a GPT three or whatever was doing some before copilot hit the scene? There was the, like, there was another like ML sort of thing that was like, you describe your program and it writes it.

[00:37:35] **Adam:** Yeah.

[00:37:36] **Carol:** that's weird.

[00:37:37] **Adam:** Yeah. It was something like that.

[00:37:40] **Carol:** don't

[00:37:40] **Tim:** I totally get why Microsoft would do that. I mean, they bought get hub. It was probably was in their mind at the time. Right. Let's use artificial learning. We have this huge repository of code that we have access to and we can come up with this sort of, I mean, it's a brilliant idea from a

[00:37:57] **Adam:** from a business perspective. Yeah. Okay.

[00:38:01] **Tim:** I feel like I would have to rewrite all the code after it was suggested to me. you

[00:38:06] **Tim:** can lend

[00:38:07] **Ben:** going back to well it's cause I ain't going back to strong opinions. Weakly held, like I have very strong opinions about how I like to format my code and I feel like I would have to rewrite essentially every line that gets added to have my flavor flave

[00:38:21] **Carol:** But that's what it says. If you're really concise up front, it learns from how you do it and it does it your way.

[00:38:27] **Carol:** So I think you would love it. Yeah. So if your variables are all like my underscore name underscore on

[00:38:34] **Adam:** We can keep going.

[00:38:35] **Carol:** Soif you, if so, how you name things like it, it keeps track of that.

[00:38:39] **Carol:** So when it's introducing note new code, it's going to put underscores in your variable names as opposed to doing, camel case,

[00:38:46] **Ben:** Or in your case, lots of land breaks.

[00:38:49] **Ben:** I see how many developers will copy space indented code into a tab, indented code file, and then just leave it like

[00:38:59] **Adam:** that. is how you get

[00:39:00] **Ben:** these are like, yeah, like these are smart, hardworking people doing that. I have to imagine if someone can have code auto generated for them. Like, is it in some ways that's going to make things even worse for like

[00:39:16] **Adam:** I don't think co-pilot's going to do that. I think it's going to be better at that sort of thing. Right? it's not trying to find a code snippet that it has seen in the past that would fit what you're trying to do. It is, it has an understanding of how programming works and tries to understand what you're trying to do and give you an, it tries to write code, to do what you're trying to do.

[00:39:40] **Tim:** I'm telling you guys, this is how we get sky net.

[00:39:44] **Carol:** I think what Ben saying is if you have someone who already copies and pastes in spaces and tabs, they probably shouldn't be given copilot because they're not going to

[00:39:53] **Tim:** They're just going to trust it.

[00:39:54] **Ben:** Well, yeah, and it's not even that not going to get better. It's like if you're already not cleaning up the code that you're putting in, what are the chances that you're going to double check the code that someone else puts in?

[00:40:05] **Carol:** And are you going to understand it?

[00:40:07] **Ben:** I don't know. It makes me a little nervous

[00:40:09] **Carol:** see. We'll see.

[00:40:10] **Ben:** and because we don't work on projects that automatically format

[00:40:13] **Adam:** well, that's the other thing, right? If you, if we're going to do this, linting would save you from the copy and paste, wrong indentation.

[00:40:20] **Ben:** Uh, topic.

[00:40:22] **Tim:** just need your, you just need your own linter the bin, the Dell blunter.

[00:40:27] **Adam:** All right. All right, Tim, your time starts now. What do you got going on? Or where's your, what's your topic?

## [00:40:31] Employee Owned Companies

[00:40:31] **Tim:** So I don't know if mine's really a topic? Maybe I should've gone first. It's more of an, amuse-bouche sort of a philosophical, I've just been thinking about this awhile. you guys know there's several, lots of employee owned companies, right? Where all the company, all the employees, they're basically a stockholder.

[00:40:51] **Tim:** They own the company. They sort of have a,Power structure, where the employees have input into how things are done. And recently I've been trying to find any software company that runs like

[00:41:02] **Tim:** because there's so much overhead software. And I there's so much, I really feel if you gave the developers more control, more power, more say in the, how the company was done, things would be better,

[00:41:14] **Adam:** only that, but I think visibility into what the, what things are going on to enable them to just come in, punch the clock and work on their code that they've been assigned to do.

[00:41:24] **Tim:** Yeah. I th I just feel that, there was a period where programmers were sort of rockstars and now we've kind of gotten into the period where programmers are just kind of mechanics. Right. And I think that's not good for the. Industry as a whole, because then, if you're like, oh, you can be, people are like, oh yeah, I work there.

[00:41:46] **Tim:** And nine, all I do. is just, squash and bugs every now and then. And that's not really what I consider a programmer. So I, the only company I could find, I did a Google, some Google searches today, and there's one company, Epsilon's systems solutions, Inc. They are a hundred percent employee owned.

[00:42:06] **Tim:** They work in mostly government defense, DOD, they, but they're, I mean, they're a software company and they're a hundred percent,

[00:42:13] **Tim:** employee owned, but that's the only one I could find. I just think there'd be so much benefit if the developers who are actually working on stuff had more. At stake and more to gain in the whole game of software.

[00:42:28] **Tim:** Cause it's like the, the, the management tends to like the CFD administration. Those are where the money goes, right. It's where all the money goes up at the top. But then those people aren't really producing anything.

[00:42:40] **Adam:** So I laughed there because you called it a game and I've been waiting for the right moment here to say, there's a book I read, that is, it's not about employee owned businesses, but it is about, making every single employee feel like they're an owner. Like, feel like they have that stake in the company.

[00:42:59] **Adam:** and they, so it's the name of the book is the great game of business. And, the concept is. you kind of open-source your business to the employees, the whole budget ever. I think that it doesn't specifically say in the book, but I think that the idea is like, this is how much we spend on salaries.

[00:43:18] **Adam:** Not that Tim makes this much and Ben makes as much, and that's a separate discussion whether or not you want that to be open, but, right. So you've got the budget. These are our expenses, these are our revenues. This is what we do. And this is, I know this is what this part of the business brings in.

[00:43:30] **Adam:** And we use that to cover this part of the business that runs at a loss and whatever, like, and,setting goals and breaking them up into chunks and like, it's a whole thing. And I would recommend reading the book. I w I found it very inspiring. I read it because we were planning to do that for our business.

[00:43:45] **Adam:** And it just, we kept kind of having to put it off cause different things, for example, COVID and you know, we've got, we just got other things we got to do to survive before we can take on something that's more philosophical. yeah, I mean, like, like I said, I found it inspiring and I would recommend that.

[00:44:03] **Tim:** I'll check it out.

[00:44:05] **Ben:** I also wonder if there's a difference between kind of a lifestyle company versus the startup craze these days where companies are trying to, 10 X their outcomes, I don't know what the right terminology is, but I think it's hard to have an employee led company. When so much of the culture these days is how do you give people options instead of money?

[00:44:30] **Ben:** Or how do have them work extra hard in the hope that one day something will have a huge payoff. I think if you're going to have ownership of the company be so distributed, then you really would have a harder time. I think selling people on that concept where a lot of people probably do.

[00:44:47] **Ben:** Come in, do my work and feed my family and have a nice life and not necessarily worry about, disrupting an industry

[00:44:55] **Tim:** Yeah. I mean, so, I mean, let's say the early people in Facebook, right? They weren't making money. They were doing it for the options, but now they're fully established company. And so you get into this thing where you just have this mass of workers who are basically getting nothing. I sound like a socialist.

[00:45:12] **Tim:** Oh my God. but you have this massive workers who are just working for. very low wages doing repetitive things. I just, I don't know. I was just trying to find a way to make a better life for program, particularly game developers or people who are in the gaming industry, the hours and the deadlines that they set.

[00:45:30] **Tim:** I mean, their quality of life is just trash. I just wonder if you took, if you started a game company with some good funding and made it an employee owned company and said, you know what, let's just build a really good game. And,everyone has stake in it because part of their salary is going to be based off of, the profitability of it, what could they accomplish?

[00:45:51] **Tim:** I just, it's just an experiment that.

[00:45:54] **Tim:** I haven't seen out in the wild. And I just curious about that. So that's sort of

[00:46:00] **Carol:** I also think that if you went that route, you would have more qualified employees because you're going to self maintain that. Right. You're going to make sure that the people working on your product are doing a good job because you have stake in what they're doing. As much as you have stake in what you're doing.

[00:46:17] **Carol:** So you're not going to let someone come in and work. Puts out a bug or two every now and then, and just goes home. Like you're going to want someone who's invested into it and who does a good job. So I think there's positive sides to

[00:46:30] **Tim:** I just try to figure out mentally, what's the model of where you have a, an organization, a group of people where everyone is driving value and being compensated appropriately for the value that they're driving. Because, as eat too many people that all they do is like people in finance, we just move numbers around.

[00:46:52] **Tim:** They don't only create anything. And that then you have people who are generating the actual product who get, a 10th of what someone who just moves numbers around does, and maybe that's just. I'm prejudice because I'm a developer. And I just think we're the ones who, who do all the work. I know the other folks work hard, but it's like, who is actually creating, who's generating the value of the product.

[00:47:17] **Tim:** It's the developers, they're the ones creating stuff. And, but yet it. seems like they, except for maybe a few, who've been there a really long time and have seniority. They're the ones who are just kind of at the lower end there, the mechanics are treated like mechanics. And how do we make that more equitable for everyone?

[00:47:37] **Carol:** I don't feel like that's everywhere. I feel like, you know where I'm at, the engineers are compensated well. Like we don't, I wouldn't say that we aren't treated fairly, we work normal hours. I feel like we get what we deserve. So I think there are companies that aren't

[00:47:52] **Tim:** But do you though,

[00:47:54] **Carol:** owned that. Yeah, I do. I mean, I don't work weekends.

[00:47:58] **Carol:** I don't work nights. I every now and then we'll pull some long hours and it's usually because I want to myself, it's not because it's pushed upon me and it's like, We make good money

[00:48:08] **Tim:** you probably don't know what the folks above you are doing and Megan,

[00:48:11] **Carol:** Yeah. I mean, that's true. That's true. But so one thing they did do is they brought in a, sad. I don't even know the title.

[00:48:18] **Carol:** It just happened. Like in the last couple of months they brought someone in to basically do salary analysis of the entire company and against, other companies that compete against us or do what we do to make sure that we're being treated fairly.

[00:48:33] **Tim:** Everyone's doing that because of the great resignation that's going on right now, everyone

[00:48:37] **Tim:** through

[00:48:37] **Carol:** it's

[00:48:37] **Tim:** is decided to reevaluate their life and they're all at once deciding to change careers. So you gotta make sure you're paying your people. Right. That's all I had.

[00:48:47] **Adam:** Okay.

[00:48:48] **Carol:** That was a

[00:48:49] **Adam:** Well, we've got less than a minute left on your time, so I'm just going to play it now.

[00:48:54] **Tim:** Oh,

[00:48:56] **Carol:** off.

[00:48:57] **Tim:** thanks.

[00:48:57] **Adam:** You're welcome. just thought it would make a, your hater happy.

[00:49:01] **Tim:** Thanks. He he'll hit it no matter

[00:49:02] **Carol:** We

[00:49:03] **Carol:** we cut Tim off. Yay.

## [00:49:08] Patreon

[00:49:08] **Adam:** Cool. So I guess this is the time of the show. When I tell you that this episode is, this episode of working goat is brought to you by a weak opinions, strongly held, and listeners like you. If you like what we're doing here, you might want to consider supporting us on Patreon at patreon.com/WorkingCodePod, to thank our patrons for their support.

[00:49:27] **Adam:** They'll get an invite to our Discord server, where we like to hang out and chat. Any old thing. and we have other parks available, like early access to new episodes and our after show that we're going to go record here in a couple of minutes. Um, oh yeah.

[00:49:41] **Carol:** yeah, you get to play games with us. You guys coming,

[00:49:44] **Adam:** yeah. Sorry. I got this whole anniversary thing going on.

[00:49:48] **Tim:** Ma'am marriage.

[00:49:53] **Adam:** of course we need to think our top patrons, Monte and Peter. Thank you guys so much for your support

## [00:49:57] Thanks For Listening!

[00:49:57] **Adam:** and if paying for podcasts is interesting. No worries. We appreciate you taking the time to listen and there are some freeways that you can help us out too. You can, leave us a rating and review on apple podcasts or wherever you get your podcasts, and you can share the show with your friends and your coworkers.

[00:50:11] **Adam:** please send us your questions and show topics on Twitter or Instagram @WorkingCodePod or leave us a message at 512-253-2633 that's 512-253-CODE. We'll catch you next week. And until.

[00:50:23] **Tim:** Remember guys, your heart man. Even if you have weak opinions, strongly held,

[00:50:30] **Ben:** We can pick and strongly that's funny.

[00:50:33]

[00:50:52]

## [00:50:52] Bloopers

[00:50:52] **Ben:** Well, do you want to just slide right into your topic then?

[00:50:55] **Carol:** No, no, no. You gotta break it up. You gotta make people listen longer because they only want to hear you. And now they're just going to dip out then your next, there you go. We're breaking it

[00:51:06] **Adam:** So let it be written, so let it be done.

[00:51:08] **Carol:** I was like scrolling through and saw this tick talk of like what engineers do. And it was like, what my parents think I do. And it's like, sitting there with headphones on like fixing electronics and stuff. It's like what my boss thinks I do. And it's like, non-stop coding like lots of caffeine.

[00:51:25] **Carol:** It's like what I really do. And it's like in bed taking a nap, the laptop vibrates and opens it like, hello? Yeah. I'm here. Engineering life is hard.

[00:51:37] **Ben:** I saw one the other day. And he was like, what people think hackers do. And it's all this crazy hacking. And then it's like, what hackers actually do. And it's posting memes on Facebook

[00:51:46] **Ben:** that are like your first, the first road you lived at and your first pet name or your superhero name.

[00:51:51] **Carol:** yeah.
