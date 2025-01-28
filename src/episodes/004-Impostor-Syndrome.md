---
title: "004: Impostor Syndrome"
description: This week, the crew talks about their own mistakes, feelings of fraud, insecurities, and how Impostor Syndrome manifests in their own careers.
date: 2021-01-06
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/004-impostor-syndrome/id1544142288?i=1000504501994"></iframe>

Impostor Syndrome is a psychological pattern in which people doubt their skills, talents, and accomplishments. Most of us have felt something like this in our careers, whether it's a fleeting moment or a persistent fear that we're going to be discovered as frauds. These feelings can be overwhelming, even debilitating; but, they can also drive us towards self-improvement.

This week, the crew talks about their own mistakes, feelings of fraud, insecurities, and how Impostor Syndrome manifests in their own careers.

## Your hosts

- Adam Tuttle -- [Twitter](https://twitter.com/adamtuttle), [Website](https://adamtuttle.codes)
- Ben Nadel -- [Twitter](https://twitter.com/bennadel), [Website](https://www.bennadel.com/)
- Carol Hamilton -- [Twitter](https://twitter.com/k_Roll242)
- Tim Cunningham -- [Twitter](https://twitter.com/timcunningham71)

Follow the show! Our website is [workingcode.dev](https://workingcode.dev) and We're **@workingcode.dev** on [Bluesky](https://bsky.app/profile/workingcode.dev). New episodes weekly on Wednesday.

## Triumphs & Fails

- **Adam's Failure:** Adam accidentally destroyed a database by running a migration script on _the wrong database_! Thankfully it was a QA (Quality Assurance) database which could be restored - no critical client-data was lost.
- **Ben's Triumph:** He's deleted 200K lines of unused vendor code. That means shipping less code to production with every deployment. He also merged one of his unnecessary microservices back into the monolith.
- **Carol's Triumph:** She's not dying! Woot woot! She had gotten COVID-19 right on the heels of a kidney infection; but it is currently feeling much better (and is nursing her sons back to health as well).
- **Tim's Triumph:** He's been playing around with Redis as a means to make his applications more resilient. One thing he wants to do is centralize his Session management such that he can pushed new code to production without having to reset user-session data.

## Notes & Links

- [Breaking Bad](https://www.imdb.com/title/tt0903747/) - critically acclaimed TV drama.
- [Adam Sandler's Click](https://www.imdb.com/title/tt0389860/) - comedy about appreciating your life.
- [Redis](https://redis.io/) - blazing fast in-memory database and data-structure storage.
- [PM2](https://pm2.keymetrics.io/) - a production-grade process manager for Node.js.
- [Amazon ECR](https://aws.amazon.com/ecr/) - Elastic Container Registry.
- [Amazon Fargate](https://aws.amazon.com/fargate/) - serverless compute for containers.
- [GitHub Actions](https://github.com/features/actions) - automation tools for your GitHub workflows.
- [The Push Train](http://pushtrain.club/) - Dan McKinley's presentation on managing the human side of continuous delivery.
- [Lagom Framework](https://www.lagomframework.com/) - an opinionated microservices framework for moving away from the monolith.
- [Little Bobby Tables](https://xkcd.com/327/) - classic XKCD comic.
- [Multi-Stage Builds in Docker](https://docs.docker.com/develop/develop-images/multistage-build/)
- [Mike Cannon-Brookes: TED Talk on How you can use impostor syndrome to your benefit](https://www.ted.com/talks/mike_cannon_brookes_how_you_can_use_impostor_syndrome_to_your_benefit)
- [WTFs per minute](https://blog.codinghorror.com/whos-your-coding-buddy/) - Coding Horror comic on code quality.
- [1 Corinthians 10:12](https://biblehub.com/1_corinthians/10-12.htm) - "Therefore let him who thinks he stands be careful that he does not fall."
- [GoTime podcast](https://changelog.com/gotime) - one of the ChangeLog podcasts.
- [Mythical Man Month](https://amzn.to/3mowUIU) - iconic essays on software engineering.
- [99 Bugs in the code](https://imgur.com/a/sZLJB) - grumpy cat's take on the 99 Bottles song.
- [Perfect is the enemy of the good](https://en.wikipedia.org/wiki/Perfect_is_the_enemy_of_good) - trap that many product companies fall into.
- [Neil Gaiman's address to the University of the Arts Class of 2012](https://www.youtube.com/watch?v=2OwRUyZMKwI) - "Make good art".
- The 10x programmer - toxic programming myth about unicorn developers.
- [Ruby Rogues EP 220 with Laurent Bossavit](https://devchat.tv/ruby-rogues/226-rr-the-leprechauns-of-software-engineering-with-laurent-bossavit/) - discusses the book, "The Leprechauns of Software Engineering", which covers among other things the myth of the 10x programmer.
- [Radio Lab: Lying to Ourselves](https://www.wnycstudios.org/podcasts/radiolab/segments/91618-lying-to-ourselves)
- [The "Peter Principle"](https://en.wikipedia.org/wiki/Peter_principle) - people in a hierarchy tend to rise to their "level of incompetence".
- [The Dunning-Kruger Effect](https://en.wikipedia.org/wiki/Dunning%E2%80%93Kruger_effect) - a cognitive bias in which people with low ability at a task overestimate their ability.

[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/004-Impostor-Syndrome.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:16] **Adam:** Alright, it's show number four for January's, uh, bleh. I screwed it up

[00:00:21] **Carol:** already. Tim's dancing. You know, distracting. Distracting.

[00:00:25] **Adam:** It's the music. Yeah. Alright, it's show number four for January the 6th, 2021. Can you guys believe it? It's already 2021. We're, we're recording this in December still. Uh, and on today's show, we're going to talk about imposter syndrome, but before we jump into triumphs and fails, we just wanted to briefly acknowledge that, uh, this is the first episode that we're recording after we have launched.

[00:00:46] **Adam:** So our first episode is out. We're live! We're live! And people are listening to it and it's been going wonderful. We have like over, let me pull up the stats here. 87!

[00:00:58] **Carol:** Over 87! And zero haters

[00:01:00] **Adam:** yet.

[00:01:01] **Tim:** Zero haters. We haven't made it till we got haters. We need some haters, brothers.

[00:01:08] **Adam:** Episode 1 has 90 downloads.

[00:01:11] **Adam:** Does that mean listens? Not necessarily. It just means downloads. It's like, for me, I have, um, I have a, like, a lot of podcasts that I listen to set up to automatically download and add it to my, like, playlist. And so I get, I'm like 36 hours behind, but that's because, you know, some episodes, some podcasts I put at the top of my queue and some go to the bottom.

[00:01:32] **Adam:** And so, and then when I find a new show, it's like, okay, I go through their entire, like, last year or two catalog and I go, okay, well, I'm going to listen to that one and that one and that one. And so I, I, I have been. So I end up adding, like, two or three or ten hours to my playlist, and so, like, right now, I'm many hours behind.

[00:01:50] **Adam:** Plus, you know, audiobooks,

[00:01:51] **Tim:** and... We're at 90%, because we only know 100 people, all of us together, right? Yep. So we're at 90%, we're almost there. Come on, guys. And

[00:01:58] **Carol:** we share, we share easily 75% of those 90. Exactly.

[00:02:03] **Tim:** Yeah. That's what I meant. All of us as a whole, we only know 100 people.

[00:02:08] **Adam:** Yeah, I currently have 33 hours and 12 minutes in my podcast queue to listen to.

[00:02:12] **Adam:** Holy cow. I mean, I guess it helps that I listen at like 2x, kind of as my baseline.

[00:02:18] **Ben:** Do you ever wish you could listen or watch movies on 2x? It's a terrible instinct,

[00:02:24] **Adam:** but sometimes I do, actually. So I, I watch most of the TV that I watch, I watch on Plex. And, and I have a a browser extension that allows me to speed up any online video.

[00:02:34] **Adam:** So I watched it in the browser. That's, it's been wonderful because there's like, there's shows that I want to go back and

[00:02:40] **Tim:** rewatch. Young people, Get off my lawn, you young people.

[00:02:44] **Adam:** Yeah, so I'm, I'm wrapping up a rewatch of Breaking Bad. It's been, you know, many years since I saw it. And I'm going back through it.

[00:02:50] **Adam:** And the thing that's been painful about it is that it's slow. It's a, it's a very kind of methodical, slow paced show. It's a wonderful show, but it's so slow. And so I've been watching it at like 2x, uh, and it's been great because then I can watch like two episodes on my lunch break instead of just one or something.

[00:03:07] **Adam:** You're fast forwarding

[00:03:08] **Tim:** your life. It's gonna be like that Oh

[00:03:12] **Adam:** yeah, what was that movie? Remote. I don't think

[00:03:14] **Tim:** I've seen that one. Where he fast forwarded through, through all the good parts of his

[00:03:17] **Adam:** life. Oh.

[00:03:19] **Ben:** Well, uh, Adam Sandler also has a version of that, I think, called Click,

[00:03:23] **Tim:** or... No, I'm sorry, you're 100% correct.

[00:03:25] **Tim:** I was totally wrong. It was not Jim Carrey, and it's not remote, it was that. It was completely what you said.

[00:03:31] **Carol:** This is why you've never heard of it, Adam.

[00:03:32] **Tim:** That's right.

[00:03:33] **Adam:** Click, yeah. Alright, well, uh, I guess let's do Triumphs and Fails. Uh, you know what? I'm gonna, I'm gonna take the reins. Uh, let's see, Tim, I'm gonna come to you first.

[00:03:43] **Adam:** What do you got for us this week? So, I've been playing

[00:03:46] **Tim:** around with Redis, uh, a little late to the game. Yeah, I actually read some of your blog, Ben, before I... Jumped on the Redis train, but yeah, it's just been messing around with that. It's just really cool technology. I love how easy it is to set up and to scale and just, yeah, it's just quick and fast.

[00:04:06] **Tim:** And I just, I wish more technology were like that. It just, it just makes sense. You can, it does a whole lot. I don't need it for everything it does. But what I needed to do, it does and does easily. So, I'm just really happy to set up a Redis cluster and to use it. We're getting a lot more load balancing and trying to make things more fail redundant.

[00:04:28] **Adam:** So, what are you using it for?

[00:04:30] **Tim:** So, that thing I talked about in an earlier episode where it's financial data. We just need to persist some data across multiple nodes for a short period of time. Okay. And I didn't want to do it. You know, using sticky sessions or anything like that. I just wanted something simple and Redis fits the bill.

[00:04:49] **Adam:** That's awesome. It's working great. Yeah, we use

[00:04:51] **Ben:** Redis for our sessions as well. Yes.

[00:04:53] **Adam:** Pretty awesome. We do too. And, uh, I was, that's, I was going to bring that up as well. The, the thing that kind of blew my mind at first and then as soon as I, as soon as I saw it was happening and thought about it, I was like, that makes perfect sense.

[00:05:05] **Adam:** Is that if you use external storage for your sessions, then your sessions survive, uh, app server restart. Yep. Which, if you're using the in memory sessions, which is the default, then, then they don't. Yeah, that's

[00:05:21] **Tim:** one of the biggest reasons. We want to be able to update code and update, do service patches and everything on a node and not take everything down.

[00:05:28] **Tim:** So that way we can just go through 1, nodes, restart them, and you never lose a session in production. So, 100% uptime.

[00:05:36] **Ben:** Nice. I have this sense about Redis that I want to use it more, but I don't know how. Like, there's the API. I mean, it does some much more complicated things, but the general API for it's quite simple because it's basically just kind of getters and setters on this giant keystore.

[00:05:55] **Ben:** And it's so fast. And I'm like staring at it. I'm like, what do I do? How do I leverage this? There's got to be more things I can use it for.

[00:06:03] **Adam:** I did a really fun thing with Redis, um, so we, uh, one of the things in our product that is kind of heavy lifting is, uh, list segmentation, right? So you, we have a giant list of all of your people that you know about, and you, we wanted what, we wanted it to be possible for you to say, okay, give me a list of everybody that is currently over the age of 80 that lives in this zip code that has an engineering degree that they received in 2000.

[00:06:29] **Adam:** for that, um, has made a gift in the past, right? Like it made a donation. That's a lot of criteria to put in there. And we wanted it to be a system where we can set up individual criteria. Like, okay, give me the people that Made a gift in this year or that are this age or live in the zip code, whatever, and they can kind of mix and match the criteria themselves.

[00:06:51] **Adam:** So we started out with sort of like a SQL builder approach and, um, building a SQL query. And it was Functional, but it's hard to build that in a performant way, um, and so what we ended up doing was each of those filters, um, returns, like, a set of the primary keys, and then we throw all of those into different sets in Redis, and then Redis has, uh, I forget what the...

[00:07:17] **Adam:** It's called Sinter, Set Intersection. So you have, like, a set for each one of these filters, and then you say, okay, give me the intersection of all these filters, all these IDs, and it gives you the, only the IDs that are in all of them. And then you've got the list of IDs that match all of your filters, and you can go, okay, here's your list of people.

[00:07:33] **Adam:** It's super fast and, and awesome.

[00:07:36] **Ben:** Very cool.

[00:07:37] **Tim:** That's my

[00:07:38] **Adam:** triumph. Awesome. All right, Carol, what do you got for us

[00:07:41] **Carol:** this week? So I don't have anything work related that's triumph or failure because being sick, I pretty much couldn't use my brain. So I guess for me, the triumph is I'm not dying anymore. Right here, right now, I am getting over COVID, but the failure would be that both of my children got it.

[00:08:00] **Carol:** So, um, they're both in the other. Part of the house sick. So we're just trying to get through it.

[00:08:07] **Adam:** I figure once it's in the house, you kind of got to assume everybody's going to get it. Yeah.

[00:08:11] **Carol:** I was, I was hoping they'd be asymptomatic, but they weren't. They've run fevers, they've coughed, they've got the whole thing going on.

[00:08:18] **Carol:** So we're just trying to get through.

[00:08:21] **Adam:** Well, we're glad you're on the mend and

[00:08:22] **Tim:** it wasn't as bad as it could be.

[00:08:23] **Carol:** Oh yeah, absolutely. I feel very lucky that all I had was what I had because I've heard way

[00:08:29] **Adam:** worse. Uh, I've got

[00:08:32] **Tim:** a friend, he's older, but, uh, he's in his seventies, he's, he's in ICU right now with COVID.

[00:08:38] **Tim:** Yeah. Oh, jeez. Praying that he, he makes it through.

[00:08:42] **Adam:** Absolutely. All right, Ben, how about you? What do you

[00:08:45] **Ben:** got? I have some pretty good triumphs, I believe. Uh, so. We'll

[00:08:52] **Adam:** see about that.

[00:08:54] **Ben:** You know, typically, I mean, I guess it depends on your business, but typically between Thanksgiving And New Year's stuff is usually just a little quieter.

[00:09:04] **Ben:** Businesses are not always, you know, at work. So I've been taking the opportunity to do some stuff that's not necessarily feature development. So one thing that I did was I went through our application and I did an audit of our Third party JavaScript vendor libraries, and I ended up deleting over 200,000 lines of code.

[00:09:25] **Ben:** Oh. Which on one hand you're like, but nobody was using that code 'cause it was all old versions of libraries. Right. But on the other hand, It has to get packaged into a docker container, and then that docker container has to get pulled down to everything that gets deployed. So I like to have the, the Boy Scout rule where I'm just like baby stepping towards a leaner, lighter development environment.

[00:09:48] **Ben:** So I was pretty excited about that. And then the other triumph I have was we at work have a giant monolith amongst other things. And years ago. A couple of teams tried to start slicing parts of that monolith off into microservices, and we were very naive in how we were doing things back then and made some poor, let's call it boundary choices around some of those microservices.

[00:10:16] **Ben:** And I've spent some time merging those microservices back into the monolith, and I just finished merging back in, I think. My fourth microservice back into the monolith, back into the right sized service . And, uh, you know, now it's just another container that doesn't have to get deployed anywhere and, uh, uh, easier to maintain.

[00:10:39] **Ben:** And, um, it gives me an opportunity to, to, uh, tweet out my Thanos gif where he is putting one of the stones back into the, yeah. The gauntlet, I don't know what the name of the gauntlet is. I think the infinity stone gauntlet.

[00:10:51] **Adam:** The power glove. Yeah, yeah. The Nintendo power glove.

[00:10:54] **Ben:** I was pretty excited about that.

[00:10:56] **Adam:** That's cool. Awesome.

[00:10:59] **Carol:** It feels like the opposite. Like it feels like that's something typically you wouldn't be super excited about that. I took the microservice back to the major app. So, well, I

[00:11:10] **Ben:** think, you know, what we see. In our industry in general, and I'm sure this is everywhere, is everything operates on some sort of a pendulum, right, where an idea becomes popular, you go way too far in one direction, then you realize you went too far, you start coming back, and you overcorrect, and then you find a balance eventually.

[00:11:29] **Adam:** Yeah.

[00:11:29] **Tim:** Yeah, I mean, if microservices aren't done right, it doesn't, I mean, particularly if they're all talking the same data source. Yeah, exactly. If the data source becomes a bottleneck, then what's the point of the microservice?

[00:11:40] **Adam:** Yeah, we're experiencing some of those growing pains now, too. We have, um, a similar story coming from just a single monolith, one application server did everything, and sort of as things became bottlenecks, we would break those off into their own microservices.

[00:11:56] **Adam:** Um, and one of the pains that we're going through now is, initially, we were, um, rewriting those things as Node. js things, uh, or like Node. js sort of micro apps, and running those on the same server using PM2, and then more recently we've been creating containers out of them, deploying them to ECR, the Amazon Elastic Container Registry, and then They're running them on Fargate, which is part of their Elastic Container service, ECS, if I'm getting that correct.

[00:12:32] **Adam:** Um, sure. And, uh, it's just been kind of a, it's been a whirlwind couple of weeks where we're... So we're kind of losing track of what is the right way to do development on this little part of the project, what is, you know, how do you, the development environments are getting kind of tangled and, um, deploy procedures are getting a little bit tangled, but at the same time we are improving our, um, like our CI situation, we're starting to make a lot more use of GitHub Actions and, um, so it's like, things kind of have to get worse before they get better.

[00:13:09] **Adam:** At least for us.

[00:13:12] **Ben:** Yeah. And, and one thing that's interesting and I've, and I've heard people talk about this in various...

[00:13:21] **Ben:** And I think this is sort of, I don't want to say this is where we went wrong, but this is sort of some of the stumbling that we did at first was that we weren't necessarily solving technology problems. We were solving people problems, right? We had too many people trying to go through one deployment queue.

[00:13:37] **Ben:** Yep. So it was like we wanted to create separate lines of deployment just so that we could push more people's code up into production concurrently, having nothing to do with necessarily how that code was organized, which turned out to be not a great

[00:13:50] **Adam:** choice. So I guess this is probably a good place. I'm going to plug a presentation by Dan McKinley.

[00:13:57] **Adam:** You might've heard of him. I think he's, his like Twitter handle and his handle everywhere is McFunly, if I remember correctly. Um, he has, uh, he has many good presentations, but the one that I'm thinking of is called the Push Train and it's about, um, continuous delivery, um, and just the way that, that they learned or they figured out how to do it.

[00:14:18] **Adam:** I guess it was when he was at Etsy, if I'm remembering correctly. Um, uh, yeah. I'm looking at it now. I'll, I'll put a link in the show notes, but it was a, it was a really good presentation and good to, uh, think through some of the challenges of, uh, many developers working on the same project and dealing with many releases in a day sort of thing.

[00:14:42] **Adam:** It's cool.

[00:14:43] **Tim:** My, my opinion, if, if you want to take a look at it, someone who's done microservice correctly, I'd look at the Logum framework, uh, Logum. How do you spell that? So Lagom is a Swedish word. My wife is Swedish. And so Lagom kind of means in Swedish, they, they have this idea of you don't have too much, you don't have too little, you have just enough is just right.

[00:15:05] **Tim:** Um, and that's Lagom, L A G O M framework. com. Um, it's based off of Scala and Acca. It's a very highly opinionated framework, so they, they don't give you a whole lot of room to kind of do things the way you think you should, but it's a very well done microservices framework if you ever want to take a look at that.

[00:15:29] **Tim:** We don't actually use it, we look, we did. Evaluate it. But if I ever did want to get more into, uh, microservices, I would use that because they would kind of force you into best practices.

[00:15:42] **Adam:** You said it was scale or what? Uh, well, s

[00:15:45] **Tim:** Scala or Play or aca. So acas the actor service that's used. Okay.

[00:15:51] **Adam:** Interesting.

[00:15:53] **Adam:** Never heard of this before.

[00:15:55] **Ben:** Well, and, and Adam, have you done your triumph? Sorry. I have not. Why? Let's, let's jump to yours because I think the deployment stuff is actually an interesting segue into the topic of imposter syndrome.

[00:16:07] **Adam:** Okay. Interesting. Okay. Um, so for my, uh, I guess I'll go with a fail this week.

[00:16:13] **Adam:** Um, I destroyed a database yesterday. Oh no. Fortunately for me, it was a QA database. There was a customer that had some work in progress on that database that they were working on with somebody else, and they're going to have to do that work over again. But all things considered, it wasn't that big of a deal.

[00:16:31] **Adam:** I was able to restore a backup from production and, and, um, move along. But it was just a reminder of... You know, don't get complacent and be super careful with destructive operations. I was, so what I was doing was, uh, preparing a script for, um, creating a new database, like mostly empty database for new customers, um, which just needs to be updated every once in a while when we, you know, as we evolve our product, we have more tables and more sort of placeholder startup data.

[00:17:05] **Adam:** Uh, and, um, I was And I was just working on setting it up for a new customer and iterating through, okay, it failed that time, so what do I need to fix? The table creation is out of order or something. And I slipped over into the wrong database. And just, I just am so glad that it was QA and not production, because I felt terrible for it being QA.

[00:17:27] **Adam:** If it had been production, I probably would have, like, committed seppuku or something. Oh, man. I actually

[00:17:34] **Tim:** truncated entire live customers databases one time. Oh no. What, what? Fortunately they were, they, they were having an internet outage at the time, so they actually had no transactions that entire day.

[00:17:47] **Tim:** Wow. Oh wow. That you're lucky. Lucky, lucky. So I just restored, I just restored the, the latest midnight backup, and they were none the

[00:17:53] **Adam:** wiser. Wow. Cool. I did, I did, uh, a very destructive action on a production database. Once I was working for Purdue, the chicken company. Um, it was just a, oh, they're here. Right.

[00:18:08] **Adam:** They have a processing plant, a very big processing plant in Georgia, but the corporate headquarters is in Maryland. Um, and, uh, so I was, I was a low, like pretty much the lowest man on the totem pole. So the only people lower than me were like the current college interns. I had recently graduated and was full time, uh, but I was entry level and, um, I was working on something.

[00:18:31] **Adam:** I don't even remember the circumstances. I just know somehow I ruined. All the data for like, one day, I guess I ruined the table and we had to restore it from a backup or something. Um, but the thing that sticks with me about this is, like, you know, I had that like, oh God moment. And I went and I told my supervisor what had happened.

[00:18:52] **Adam:** The table is destroyed. We're gonna have to do something about it. She's like, okay, well, don't worry about it. Um, you know, we'll, we'll restore it from backup. I think the only person that was working in there today was Don. And, um, you know, so it's just, just one person's work. And I had a heart attack at that moment, or, or, you know, I felt like I was going to have a heart attack because Don was the director of IT.

[00:19:15] **Adam:** Except that wasn't the Don she was talking about. The Don she was talking about was... A college intern, so they just happen to have the same name. But I was like, she just said Don, and I'm like, are you kidding me? I have to go tell the director of IT that I destroyed his entire day's work.

[00:19:33] **Carol:** That's all from the guy whose job title is Little Bobby Drop Tables.

[00:19:40] **Adam:** You did,

[00:19:41] **Carol:** for a minute.

[00:19:42] **Adam:** Yeah, that was it for a while. Yeah, Little Bobby Tables, or... I did, I think I still have business cards somewhere with, like, that XKCD. Little

[00:19:50] **Carol:** Bobby Drop Tables. The,

[00:19:53] **Adam:** yeah, the SQL injection drop table. XKCD snippet. I put that on business cards at one point, because I could choose my own title, so why not?

[00:20:02] **Adam:** Right? Still sitting. Yeah, I didn't drop the table, but I certainly messed it up.

[00:20:10] **Ben:** Talking about deployments, you know, we'll get into what Impostor Syndrome is, but for me personally, the thing that gives me Impostor Syndrome much more so than anything else is the distance between the raw code in my IDE and code running on production.

[00:20:29] **Ben:** And every step and level of complexity that people involve in, in bridging that gap makes me feel so inadequate sometimes. I will be honest and say that I still have applications where I FTP my code to production. Nothing that I get paid for, but I still like, you know, it works and it's good enough. But, uh, just the degree of.

[00:20:56] **Ben:** Infrastructure that can go into deployments is awe inspiring. You're not

[00:21:00] **Adam:** editing it over FTP, right? Like Dreamweaver? I mean,

[00:21:03] **Ben:** no, no, no, no. I mean, sometimes you got to jump onto the server and edit some files live.

[00:21:09] **Carol:** What? Nobody ever does that. Come on. You don't open Notepad on the RDP you have open and change it?

[00:21:18] **Ben:** Oh man, the worst is Ft P files, FTPing a bunch of files across a bunch of directories and then you go to check the site and it's just 500 server error . And you have no idea which file it was that broke it. Yeah,

[00:21:31] **Adam:** that's, so you said the, the distance between your, your code and the i d D, your between your code and the i d E and uh, and.

[00:21:40] **Adam:** What did you mean by that? Like all the DevOps steps and

[00:21:43] **Ben:** stuff? Yeah, exactly. And the degree to which that can become very manual versus very automated, right? I talked about how in some cases I have old code that I just FTP up. And it just, it's live when it hits the FTP server, but then there's all sorts of continuous integration and unit testing that runs automatically and docker container builds and auto scaling groups and all, you know, just all kinds of jazz that you can throw at a problem like that.

[00:22:18] **Ben:** And when I hear people talk about that more so than almost anything else, that makes me feel like. You people are real programmers and I have no idea what I'm

[00:22:28] **Adam:** doing. That's interesting because, like, I think that, yeah, I'm with you on, it can be very daunting and... Uh, a little scary and, and, um, make you feel small and, and inconsequential and, and ignorant.

[00:22:42] **Adam:** But at the same time, that, for me, is probably one of the most interesting and, um, just, it's the area of my job right now that I think I enjoy the most because I'm learning the most. That's awesome. You know, on a day to day basis, we're, right now, we're going through and we're editing GitHub Actions workflows and doing Docker builds.

[00:23:00] **Adam:** And I recently learned about, like, what are they called? Um. Not, not intermediary containers, but the layers. Well, so in your Dockerfile, this is what I learned. You can have like, you know, from let's just say you're doing like a Node. js container from Node, whatever, or LTS, but you can do like from Node, As builder, right?

[00:23:21] **Adam:** So you can say, like, I'm building a layer, but that layer is going to be thrown away when we're done. So, like, I can do, run my unit tests, and, um, if I need to compile something that, uh, so, like, we have a config container, and, and we start out with JavaScript files, and we compile those down into JSON. Um, and so that all happens in the, the build layer, and then we copy that into the final layer so that our docker container, the image that we push up to ECR is much smaller.

[00:23:50] **Adam:** It doesn't have all the, the source code. It only has the artifacts that you actually need to deploy. Um, and it's just, it's kind of mind blowing to see how, um, sophisticated and, uh, It's just, it's super interesting to see. It is fascinating. I think

[00:24:08] **Ben:** that's a multi stage build.

[00:24:11] **Adam:** Yeah, I couldn't tell you for sure.

[00:24:12] **Adam:** Yeah, I can't

[00:24:12] **Ben:** remember. And I think it's one of those things where if I really sat down and I really focused on understanding the foundational mechanics of it, then I think it would be much less daunting. But even now, I mean, I use Docker every day, but like so many other things, I'm using it. In the capacity that I'm using something else that someone built and I'm sort of, I don't want to say maintaining it, but I'm, I'm leveraging it and editing it as necessary, but I didn't start it.

[00:24:48] **Ben:** So there was a lot of, uh, there was a lot of tribal knowledge around the technology that's already put in place by the

[00:24:54] **Adam:** time I get there. Right. Yeah. That is a good intro to imposter syndrome. Um, so it's like, um, because you are lacking a little bit of knowledge there. It makes you feel inadequate or, or like you're an imposter.

[00:25:10] **Adam:** Like you don't belong or, or people are giving you trust that you don't deserve.

[00:25:18] **Ben:** Yeah. I like to think about it. I visualize it in my head as, as a really inaccurate Venn diagram. If anyone remembers Venn diagram from school where you have overlapping circles. Yeah. Right. In reality, everybody's skill set is some form of overlapping circles, but.

[00:25:37] **Ben:** When you are feeling like an imposter, at least the mental model that I have, is I don't have an overlapping circle. My circle is entirely contained within someone else's circle. And it's like, I assume that other people know everything that I know inside my little circle, but then they know all this other stuff that, uh, that's inside their circle as well, which is obviously not the case, but that's how it feels sometimes.

[00:26:03] **Tim:** Which amazes me that the famous Ben Nadell feels that way.

[00:26:10] **Adam:** I mean, there's a certain

[00:26:10] **Tim:** segment of, of the community that's like, everyone knows you, right? They, they, they look at you like, you know, you're the guy, right? And if you, if you feel that way, then I think they should, you know, realize that, that we're all, we're all human, right? We all, we all feel that way. If Ben Nadell feels that way, for God's sake, man.

[00:26:29] **Ben:** I think everyone must feel it. I hope everyone feels it, I

[00:26:32] **Adam:** guess. I think, yeah, I mean. I think that anybody who is pushing themselves is going to feel it, or anybody who attains a certain... Once you start to make progress in your career and you start to get a promotion or more responsibility, it's almost inevitable that that sort of feeling creeps in, um, because it, it, to me, it's a signal that you're pushing outside of your comfort zone, right?

[00:27:03] **Adam:** If all, if everything you ever did was things that you had already done a thousand times before and you're super comfortable with it, then, um, then you would never feel, um, unqualified for the job.

[00:27:16] **Ben:** And I think it's also. And I don't want to say getting acknowledgement's not the right word, but it's almost like you, in order to feel some degree of imposter syndrome, you have to be cognizant of the fact that there are things, not that just, not, not just that you don't know, but that you'd probably like to know, right?

[00:27:37] **Ben:** If you go through work, not caring about things, then you're probably not going to have feelings of imposter syndrome. Doesn't matter, right? Like, you know, Adam, you talk about woodworking and part of me, uh, you know, wants to know how to work with wood. So I look at that. I'm like, oh man, Adam knows how to program and he knows how to build stuff with wood.

[00:27:59] **Ben:** That's crazy. But then if, if, you know, Tim can eat insanely spicy peppers and I'm like, you don't want to do that. That's not a skill I want to know about.

[00:28:12] **Tim:** Uh, I, you know, if you've got teenage kids, you know, they. They seem to lack the imposter syndrome, which is, which is scary, which is a blessing, but it's also scary because it's like they, they, they, they learn something and they think automatically they're like the genius at it.

[00:28:29] **Tim:** I don't know. Maybe it's just my kids.

[00:28:32] **Adam:** It's like the Dunning

[00:28:34] **Tim:** Kruger effect. I'm scared of people who don't have the feeling of imposter syndrome at some point in their life. I'm scared of myself sometimes whenever I don't feel that if I don't feel that level of Imposter syndrome. I'm like, yeah, I'm missing some, I'm obviously missing something

[00:28:49] **Adam:** here.

[00:28:52] **Adam:** Yeah. I mean, it's a, it's a signal for your brain. Right. And, and it can be useful. It can, you know, if you're, if you're setting a goal to push yourself, push your boundaries and push yourself out of your comfort zone, then it can be a good indication that you're achieving that goal. Right. So like something that I was doing a few years back was getting more into public speaking, presenting at conferences and that sort of thing.

[00:29:15] **Adam:** And that, that fear. of public speaking, I think, is a, is a sort of a classic imposter syndrome. Like, I've fooled these people into giving me a stage and a microphone, and I am not qualified to be here. People are going to think that I'm going to do a terrible, or that, that I've done a terrible job, and, um, you haven't even given the presentation yet.

[00:29:37] **Adam:** So, it's just, it's this worry that you're, uh, not qualified, and... I mean, I don't know. I would, I would say. Trail off into nothing. And

[00:29:50] **Tim:** I've got an interesting perspective on this because just kind of the way our, our company structure is, I've been around a lot of multi millionaires. I mean, some extremely, the company that we're a part of is right.

[00:30:04] **Tim:** Well, it's just, well, it's just like, it's made, it's, it's a bunch of. Companies that are held by another company. They're all software companies. Everyone's in software, but it's, you know, it's hundreds of companies and some of these people are insanely rich and insanely successful and insanely smart. And yet you can still see most of them struggle with this.

[00:30:27] **Tim:** They struggle with this. I did like, you have a guy who, you know, he started a company that, you know, was extremely successful and they, they pushed him up the chain. And now he's like a manager of this really CEO of this really huge company, but CEO is not necessarily the place where he's most comfortable and you can see him kind of flailing.

[00:30:49] **Tim:** And that's, it's just interesting to see. I think part of imposter syndrome is whenever you believe that because you're smart at one thing, that you're smart at everything, which is not true. When you're younger, you think if you put your mind to it, you can do everything. And maybe when you're younger, your mind is pliable enough to be able to adjust.

[00:31:11] **Tim:** But as you get older and you... Follow certain paths, your mind becomes sort of cemented in that path, and the ability to pivot to something completely different gets harder and harder. And so, you know, you've succeeded, succeeded, succeeded, like, well, here, you know, try this. And you think, well, obviously, I can do this because I can do anything, and you can't do anything.

[00:31:32] **Tim:** You think you can, until you can't. And then that's, that's when you, you, the Peter principle, I think, you know, we were going to talk about that, but that's eventually at some point you will fail upward. You will find that place where you realize you're not as good, naturally as good at what you think you are.

[00:31:50] **Tim:** And some things you're really, really gonna have to work at. And some things you're just gonna have to say, I can't do that. For me, that's sales. I tried my best at it. I couldn't do it. Um, I went back to programming because, you know, it's just a skill set I don't have. And that was hard to accept. That's an ego blow to think that there's things you can't do, but...

[00:32:09] **Tim:** There's some things you cannot do.

[00:32:13] **Ben:** Well, there's a tension always in my mind between, there's the things that, uh, I want to be better at, and then there's the things where I feel like to try and become better at that would just be to fight something that, that feels insurmountable. Like, I want to be a better programmer and maybe I want to expand the type of...

[00:32:36] **Ben:** programming that I do, and that feels like a worthwhile challenge to the point of sales. Like if I had to go sit in a sales seat, I mean, I can struggle and I can fight, try to become better, but I, I feel like I would have, it, it would just be joyless the entire time. I don't think I would ever get to a point where it felt like I was.

[00:32:56] **Ben:** Getting to the top of that

[00:32:57] **Tim:** hill. And trust me, you don't know until you try it. I tried.

[00:33:03] **Adam:** It's,

[00:33:03] **Tim:** it's good to know now.

[00:33:08] **Ben:** Well, here's something that's crazy. So Adam talked about imposter syndrome in terms of public speaking and giving presentations. Yeah. I kid you not. I, when I was going to go to my first ever conference as an attendee, not a speaker, was a CF United down in Bethesda, Maryland. And I had to psych myself up just to register to attend because I felt like, who am I to go to a programming conference with all these programmers?

[00:33:37] **Ben:** Like, I'm nobody. I mean, this is, you know. 15 something odd years ago, I almost felt like I had to achieve a certain degree of mastery before I could even go to a conference that was about the thing that I do for a living. I mean, that's nuts in hindsight, but at the moment it felt very, very real, especially because you look at the speaker list and you're like, these are the people who go to a conference like this.

[00:34:01] **Ben:** I'm not a Sean Corfield or Ray Camden.

[00:34:07] **Carol:** Or Tim Cunningham.

[00:34:09] **Tim:** Tim Cunningham. Thank God you're not, man. You're much

[00:34:13] **Adam:** better.

[00:34:15] **Carol:** Do you guys know who Mike Cannon Brooks is? I don't. He is the founder of Atlassian. Okay. Yeah. So he actually did a TED talk about imposter syndrome and, uh, the link would be in the show notes, but he goes through when it started, you know, they're, I think, Australian, like an Australian company or whatever.

[00:34:37] **Carol:** And they want like the small startup, like entrepreneurs of the year. And then went on to compete, like, with 40 other countries and I don't remember if they won or not, but he was talking about sitting there and him and, you know, the guy that he was working with had, you know, all of 70 people and they're competing with people who employ 40, 000 and he was sitting there like in a rented suit and he was like, I just feel like I'm so out of place, like, at some point, someone's going to walk up to us and go, we screwed up.

[00:35:10] **Carol:** Go back home. You're not who's supposed to be here. And he said that, you know, all the guys, like he had talked to or whatever, who have these huge companies and employ 40, 000 people, all feel the same way. That at some point, someone's going to walk up and go, you're not the right person for this. Go home, we screwed up.

[00:35:31] **Carol:** And I feel like that's how I am at work a lot. I'm like, at some point, someone's going to look at a PR and go, why did we ever hire her? So then I take my pull request and I sit and read it again and read it again and read it again. And I'm like, someone's going to Read this and go, why, and send me home.

[00:35:51] **Carol:** So I know I struggle with that, with feeling out of place, but I typically am able to use it to do better. To be like, okay, it's okay if I feel like I'm not good enough, because that just gives me something to try to be good at. It gives me like a place to advance.

[00:36:09] **Adam:** That reminds me of, uh, an old, I guess you could say it's like a webcomic.

[00:36:14] **Adam:** It's not really like an ongoing comic or anything, but it was specifically about... Um, code reviews, um, you know what, I think it might've been from, um, Coding Horror, Jeff Atwood. Um, and it was, it was basically like the measure of code quality is the, uh, like WTFs per minute at your code review, right? Like everybody's going to have some, but like the lower you get that number, the better, right?

[00:36:43] **Adam:** So nobody pretty much is ever going to be at zero, but, um, You know, so just reducing that number is really what you should be focusing on, not eliminating it.

[00:36:55] **Ben:** One thing that I was going to say is that, uh, when I was in school in biology, I think it was, they were talking about walking, bipedal walking, and that essentially walking is a controlled fall in so much as you're falling forward.

[00:37:14] **Ben:** And in order to stop yourself from falling, you have to step forward and that's essentially the act of walking. And, and I, and I think it's interesting to think about imposter syndrome from a perspective like that, meaning that you don't ever get so good at walking where you're not falling forward. that you have to do the falling forward in order for the walking to be meaningful.

[00:37:35] **Ben:** And imposter syndrome to me can be a little bit like that. Like I have to have that imposter syndrome, that sort of free fall in order for me to step forward and, and improve my understanding of things. And if I ever stopped feeling that free fall, I might stop wanting to step forward and improve my skills.

[00:37:55] **Carol:** Yeah. I never want to be in that place. I want to always feel like there's something ahead of me that I don't know that I. need to learn that I have something to to grow into something to achieve. I don't want to be stale or stagnant and just look, hey, I got this.

[00:38:12] **Tim:** I think it's that, uh, tension, right? So, I mean, as human beings, we tried.

[00:38:16] **Tim:** We live in a chaotic world and we try to make sense of the chaos. Um, if we get to the point where it's too. Ordered, we get bored. And if it's too chaotic, we get overwhelmed. So it's, it's that trying to find that, that, that yin and yang, that, that edge balancing the straddling the side between chaos and order.

[00:38:38] **Tim:** That, that fine line is kind of like where we like to live as human beings. Um, but it's a struggle whenever we get too comfortable. Uh, there, there's a, there's a principle, beware ye who thinks he's standing, for lest he shall fall. It's because whenever you think you are on solid ground, that's the moment the world comes up and, and, and, and bites you in the butt.

[00:38:59] **Tim:** That if you think, if you think you're on stable ground, that, that's when you have the most to lose. And that, that's just life. So yeah, you know, people worry about imposter syndrome, but I just, it's like. I think if we just acknowledge everybody has it at some point in life, it doesn't mean you're a failure.

[00:39:19] **Tim:** It doesn't mean you're crazy. Just, it's just part of life. Just accept it and move on. Everybody has it at some point and if you don't have it, you're going to have it. And when you have it, when you have it, just acknowledge it for what it is and move on. I, what I feel for is to people that, I mean, all of us are privileged to a certain degree.

[00:39:40] **Tim:** Um, three of us are white males and one's a white female. Um, But the people who their entire life have been told they're not good enough, and that's why it's easy for them to give up whenever they feel that imposter syndrome. Um, you know, if you haven't been raised by people that tell you to push and push and push, maybe you don't have that impetus to get past.

[00:40:00] **Tim:** So, I think it's important that, although right now we're talking about how it affects us, to acknowledge that there might be people around us who are feeling that right now, who feel... Like they don't belong and are might just decide to leave and to let them know that they're not alone. They're what they're feeling is valid and that they got to push through it just like everyone else.

[00:40:25] **Tim:** It might be harder for them. They might not believe it, but don't don't listen to the voices that those voices, those voices

[00:40:31] **Adam:** are liars. It's a, it's a good reminder to give encouragement to your teammates, even if you're not like their manager or something to just like, you know, say, Hey, that was a really good pull request or, or, you know, I really liked your idea for that solution that we had at the standup meeting or whatever, you know, it's a good idea.

[00:40:50] **Carol:** I get slacks throughout the week just for my teammates just going, Hey, just a reminder, you're really doing a good job. Like, even though you don't know what you're doing, like I'm feeling out of it. Like. I'm questioning what all these acronyms mean. Like, you're doing a good job. Like you're asking questions, you're, you know, learning things, you're putting out PRs that might not be right, but they're still going out and you're trying.

[00:41:15] **Carol:** So, I do get that constant feedback from my team where they're like. You're doing good. I'm like, good, because I don't feel like I'm doing good. I'm not producing like I was at my other job. Like, I'm not on top of everything. So I'm like, I feel like I'm way behind. And it is good to get that, um, reassurance

[00:41:33] **Adam:** from them.

[00:41:34] **Adam:** Right. And then on the other side of it is like, if you're hearing those things, if you're, if you're sitting there feeling like an imposter, but you're hearing the occasional like, attaboy, people are telling you, you did a good job, then those are the signals that you should be looking for. Um, that. You're, you're fooling yourself into believing you're not qualified, right?

[00:41:55] **Adam:** You're, you actually are, right? You were promoted because you were worthy of that promotion. You were given that project because, uh, it was a good fit for you or because it would be just the right amount of, um, You know, new responsibility for you or new, um, new topic for you to learn, that sort of thing.

[00:42:18] **Carol:** Oh, excuse me, I have a confession. So, a couple of years ago, I actually reached out to Ben and was like, hey, you know, are you guys hiring? And he was like, sure, send me a code, like, send me some code and I'll, you know, we'll take a look and talk to you. I laid in my bed and cried because I was like, Oh God, Ben's going to look at my code.

[00:42:36] **Carol:** Ben's going to look at my code.

[00:42:38] **Adam:** I can't do this. Don't just put in lots of line breaks. You'll

[00:42:40] **Carol:** be fine. No. You know, here's what happened. I spent a week going, I can't send him code, like there's no way he would ever hire me if he looked at what I wrote. Like there's no way, like, I can't do this. I ended up like emailing back and like saying, Hey, nevermind, changed my mind or whatever.

[00:42:56] **Carol:** I was so terrified of having Ben read my code. Although I'm asking him about doing that. So it definitely, that was one of the worst, worst ones for me when I was like, I'm not good enough. I'm not good enough.

[00:43:12] **Ben:** Oh, that's so, I thought you were going to tell me that I hadn't like, It's all your fault. Yeah.

[00:43:17] **Ben:** Like pulled your coat apart and really made fun of it or something. No, I would love that. That's

[00:43:21] **Carol:** not like me. That would be like the best thing. Like, that's fine. If you do that, I just needed the courage to be like, someone can read what you write. It's fine.

[00:43:32] **Ben:** I was listening to, uh, one of the podcasts I really enjoy is, uh, called Go Time.

[00:43:39] **Ben:** I think it's part of the ChangeLog series of podcasts, and it's about Go, and I don't know anything about Golang. Which I think is maybe part of why I like it. I feel like I'm stepping outside a little bit. And, uh, they were interviewing a guy the other week who's been programming, I think since the eighties or something.

[00:43:54] **Ben:** And at the end of the show, they asked him if he could give advice to his younger self, what's the most important advice that he could give him. And he had two things. He said, one, do the simplest thing that works. And two, be kind to yourself. And I feel like That's so much about what we're talking about right now.

[00:44:17] **Ben:** It is. And it hits me. I've tried to be kinder to myself after hearing that for sure.

[00:44:25] **Carol:** It's not easy to do. No, it's not. I'm definitely my roughest critic.

[00:44:32] **Ben:** Although, interestingly, I think the simpler you try to keep your solutions, the kinder you are to yourself. Because it's a tighter feedback loop, right?

[00:44:45] **Ben:** You, if you, when you try to design complex systems in your head and they sound right, and then you start to put them on paper and you start to run into a lot of problems and things seem more complicated, right? So now you're thinking like, Oh, I can't design systems like this. And it's like, you start to spiral.

[00:45:02] **Ben:** Whereas if you were like, I could solve this with an if statement instead of some giant. inheritance polymorphism, because if statements are bad, right, then like you solve that problem and you move on to something else. And you're like, you know what, I'm crushing it this week. I've already shipped three tickets.

[00:45:19] **Ben:** Yeah. Definitely. Well, so one thing that helps me, I don't want to say overcome, but become more aware of the fact that I'm unnecessarily feeling like an imposter is, is I, I'll notice people say things. Or, or I noticed that people don't know things that I just assume everybody knows and, and, uh, the, the one that always comes to mind for me and it's, and it's only because I've heard it several times is people will bring up on a, on an interview, the Mythical Man Month and I just assume that's like programming 101, like everyone's heard of the Mythical Man Month and, and you'll be listening to someone in an interview who's been programming for.

[00:46:05] **Ben:** 10, 20 years and someone brings up the Mythical Man month and they're like, oh, what's that? That sounds interesting. And you're like, what ? I don't, I don't,

[00:46:12] **Carol:** I don't dunno what it's, excuse me, I don't, I don't, I literally don't know what you're talking about. Yeah. Interesting. Yeah. What it's,

[00:46:18] **Adam:** so I, I, I guess I should raise my hand here and say I've heard of it.

[00:46:22] **Adam:** I know it's a book, and I've had people explain to me, like, roughly what the book is about, so I get the concept, but I have not read the book. So I don't know if you have, Ben. I think I had to read it as

[00:46:32] **Ben:** part of a course, a school course. Okay. It was one of the, it was like part of the curriculum, but the, so the mythical man month, the basis of the mythical man month is this idea that you can think about.

[00:46:46] **Ben:** effort in terms of man months, essentially the number of people times the amount of time is this man month. I'm like, like, you know, force meters kind of a thing. Like,

[00:46:56] **Adam:** right. So like if, if it was going to take Ben, uh, a hundred hours to do this project, then the, the man month idea is like, well, then can you put the project and do it in half the time, four people and do it in a quarter of the time.

[00:47:10] **Adam:** Oh, so nine pregnant women. Right.

[00:47:12] **Ben:** Exactly. Like a woman can give birth in nine months, but nine women can't give birth in one month. Okay. And it's, uh, it. It's this notion that you can just throw more people at the problem, and it'll cut down on the time to delivery, when in reality, the more people you throw at a problem, the longer it usually takes to complete it.

[00:47:36] **Ben:** 99

[00:47:38] **Tim:** little bugs in the code, 99 little bugs. Take one down, patch it around, 127

[00:47:43] **Adam:** little bugs in the code. Exactly.

[00:47:46] **Carol:** Yeah.

[00:47:48] **Ben:** So anyway, I find that I'll, I'll, I'll tune in to those little points in a conversation where I'm listening to someone and they're brilliant by all accounts. And then they'll say something and you're like, Oh, okay, you're brilliant, but maybe you're brilliant in an area of focus that I'm just not involved in, but I know things probably that you don't.

[00:48:10] **Ben:** And yeah, it almost sounds petty, but it makes, you know, you're like, ah, I know something you don't know, we're all human. Yeah.

[00:48:20] **Tim:** I, I think with, with like a... Imposter syndrome will sometimes strike. When you have a kind of a greenfield project and you're trying at the very, you're, you know, you're used to solving very difficult problems, maybe an existing code set, and then you reset and you're, you're back to this kind of greenfield, do whatever you want and you're, you have no restraints and you realize, shoot, I have no idea how to start.

[00:48:46] **Tim:** Yeah. Right. Have you felt that before? Oh my God. Yes. So, and I think the problem is, is too many options, right? It's analysis paralysis. It's, it, what Voltaire said, you know, perfect is the enemy of the good. You, you, you're like, I, I have, I can do this perfectly now. And so you're afraid to start because the second you start, you start going down the road of possible, uh, imperfection, but you can't be perfect.

[00:49:12] **Tim:** So be good. Continue to be good. When it's not good, stop and make it good. That's really all you can do, right?

[00:49:24] **Ben:** There's a, uh, I'm gonna mangle this quote, but it's something like, An imperfect solution completed is infinitely better than a perfect solution never completed. Something like that.

[00:49:37] **Adam:** I

[00:49:37] **Carol:** don't have heard that one.

[00:49:38] **Carol:** Done. We're all shaking our heads. I wish you could see

[00:49:40] **Ben:** us. . It's funny, when I was very young in my career, I don't know if someone said this to me or if I heard it in a talk, someone said that the best way to get things done is to find the busiest person you can find and assign it to them. And I, and, and for years I did not understand what the heck that meant.

[00:50:01] **Ben:** And now that I'm a busy person, I totally get it because if someone assigns something to me, I'm going to do, and I don't mean this in a pejorative way, but I'm going to do the least amount of work it takes to get it done so that I can move on with the rest of my stuff. Like, I'm not going to think about what's the perfect opportunity here.

[00:50:18] **Ben:** How many, you know, what future can I plan for and complexities can I abstract away? I'm going to solve the problem and then move on to my next problem. Yep.

[00:50:28] **Adam:** That's so true, like, they're, you know, I have projects that I work on that are like pre planned, and then I have like a bug dropped on my desk at, you know.

[00:50:38] **Adam:** 7am or whatever and it's like that that bug gets a patch and a pull request and sometimes even deployed before like 9am, whereas the project takes weeks. Yep,

[00:50:48] **Ben:** 100%.

[00:50:49] **Tim:** Sometimes I fantasize about, you know, what if I only had to really work one day a week? What sort of, you know, project could I do the other time?

[00:50:55] **Tim:** Then I realized there was a point in my life in my 20s when a company that... I was the part I've got bought out and they basically kept me on full salary and I only had to work one day a week and I realized I spent the rest of that time just goofing off so

[00:51:12] **Tim:** I know exactly what I would build if I only had to work one day a week.

[00:51:16] **Adam:** And build a robot that reads Reddit, and it's made out of meat, and it's just me. Elon,

[00:51:21] **Tim:** Elon Musk, I would, Elon Musk, I would not be.

[00:51:30] **Ben:** So, so I think we've danced around feeling like imposters and,

[00:51:37] **Ben:** and I, and I guess maybe to be more direct in, in a meta question is, is it a good thing or a bad thing?

[00:51:44] **Tim:** It's a

[00:51:44] **Adam:** thing. Yeah, I mean, it's a, it's a feeling that we all get, and I think that it depends on what your goals are, right? So, like, for me... I've tried to, in, in recent years, frame it for myself as, uh, as something that's good.

[00:51:58] **Adam:** So, like, another thing, um, it, it reminds me of this other tactic that I had. So, like, if I was gonna, getting ready to go on stage to do, uh, like a presentation or speaking gig sort of thing, you know how you get that, the pit in your stomach, you get the cold sweat, you feel like you have to go to the bathroom, that sort of thing.

[00:52:14] **Adam:** Adrenaline rush. Um, somebody once shared with me that, that especially the adrenaline rush part of that is, that's your body preparing you to be able to think faster on your feet and to be more aware of what's going on around you. And so that actually helps you do a good job and it, Because you're thinking faster, it also makes you more able to notice your little ticks and your, the, the things that you do that are imperfect, um, but that most people will probably let slide by without ever even noticing them.

[00:52:49] **Adam:** But that concept of like, the adrenaline rush is... is a good thing. It's, it's your body preparing you to do well. Um, that sort of changed the game for me in terms of public speaking. Um, and I was able to sort of start seeing that the nerves as a good thing. Like, okay, this is, it's time to get amped because my body is getting terrified.

[00:53:14] **Adam:** Um, but similarly with imposter syndrome, you know, I have been, I think for most of my career, I've been just trying to push hard and, and grow and become a more valuable member of my team, and so when, um, when I realized that imposter syndrome can be a good indicator for me that I have hope. Like, reach the limit of where I need to push to, right?

[00:53:41] **Adam:** So maybe if I'm starting to feel that way, then it's like, okay, stop asking for more responsibility. Um, stop saying, yeah, oh yeah, I can handle that because you've reached the limit of what you should, or what I, I have reached the limit of what I should, and maybe it's time to actually start learning and, and, uh, delivering the promises I've made before I start making more promises.

[00:54:04] **Ben:** And if I can echo back what I think you're saying, and what I feel like Carol was saying with her job application story, is that imposter syndrome is good when it's a driving force, and then when it flips over to an impedance, that's a problem. You want it to inspire you, you don't want it to deter you.

[00:54:26] **Ben:** Yep.

[00:54:27] **Carol:** Yeah, that's pretty much how I was going to say it was, you know, when it causes you to shut down, then it's a problem. When you can use it to do better, when you can use it to be the thing that pushes you or the thing that you learn from, then I think it's good. You just have to figure out how to balance

[00:54:43] **Adam:** it.

[00:54:44] **Adam:** So what do you do then if it is, if you realize it is in your way and it's not a good signal, if it's something that's bad, like what do you do in that case? You

[00:54:53] **Carol:** lay in your bed and cry and don't send Ben any code. Not

[00:54:56] **Adam:** what did you do? What should you do?

[00:55:01] **Tim:** I mean, I think it's, it's how you internalize it, right?

[00:55:03] **Tim:** I imagine it kind of like you're a race car driver and you want to drive fast at your goal, but there's those little, you know, those little warning bumps on the side of the shoulder of the road and you know, you want to get just. Close enough to those as possible to get the outside curve, but you don't want to get too far in the rumble strips.

[00:55:23] **Tim:** And so that's, it's an indicator, right? So if, if you're, if you're feeling the rumble strips, you know, all right, I'm on the edge, but if you're on it too much, you might think, okay, I need to come up a bit. I think if you let it paralyze you, it's controlling you. And if you never hear it. Because you're afraid of it, then it's controlling you.

[00:55:41] **Tim:** So again, it's that, it's that tension, that living on, on the edge of, of creativity. Uh, use it, use it as a guidepost, but don't, don't use it as something to, to be afraid of.

[00:55:55] **Ben:** Absolutely. One thing that I find is very helpful to me and not just in terms of imposter syndrome, but in terms of, we talked about burnout and mental exhaustion in a previous episode.

[00:56:07] **Ben:** And, and I think this is just a tool that I use for a lot of things. And sometimes you just got to work on a lot of small things in a row, that movement begets positivity. I mean, you hear people talk about it when you're feeling down, sometimes just the act of smiling, right? And getting up and walking around like that can have a positive impact on your, on your feelings.

[00:56:29] **Ben:** And I feel the same way about a sense of, um, fulfillment and ability. If I can even take a ticket out of JIRA that's a spelling mistake, right, like that takes no skill to fix. But if I fix it and I push it up and I can drag that ticket across the Kanban board, like I feel good about that. And then I do that, you know, a couple of times in a row and suddenly I'm feeling actually pretty jazzed about myself.

[00:57:00] **Ben:** All wins.

[00:57:01] **Tim:** Yeah. Definitely. It's something for checking that thing off your list that makes you feel accomplished.

[00:57:09] **Carol:** Oh, yeah. Do you guys know who Neil Gaiman is? I love him. Yeah. Pretty amazing. Have you, did you, have you ever listened to the commencement speech that he did that, um, is like, I think it's titled Make Good Art.

[00:57:21] **Carol:** So he talks about imposter syndrome in there and you know, he, um, explains how he is basically how he had struggled, you know, and talked to his wife and everything and was like, you know, at some point someone's going to show up at our front door with a clipboard that says. And you have to get a job from nine to five, and you have to go to work because this isn't a thing people do.

[00:57:44] **Carol:** Like, you can't do this. And, um, throughout that speech, he talks to the graduates, and he's just kind of explaining how, um, When you're happy, you know, make good art. When you're sad, make good art. When people tell you it's not good, make good art, because at the end of the day, you are the only version of you that exists out there, and your brain is the only one that thinks like you think.

[00:58:10] **Carol:** So, use that to be what you are. What is good to you? Don't let someone else, you know, tell you that what you're doing isn't good because it's coming from you. So just make good art. Just make good art. And I feel like that's how we are with code sometimes, you know, if everybody thought the exact same way about how something right, like should be written, then.

[00:58:32] **Carol:** Why do you need so many engineers? Why do you need so many developers? We're all going to think alike. But the fact that you put us together, and when we're thinking through the processes, everybody thinks differently. So then you come up with a good solution. So you just do the best you can.

[00:58:47] **Ben:** Absolutely.

[00:58:48] **Ben:** And, and I know, so in the technology world, there's not just the technology, but then there's a lot of content production around the technology, whether it's blogging or presentations or... writing books like some of the people on this call. And, and, and I think there's always a sense of, of fear that is what I have to write going to be meaningful for other people or is the video that I'm going to make be meaningful for other people.

[00:59:14] **Ben:** And I would, I would... It's the podcast that we're recording. Yeah. Right. Is this going to be interesting at all to anybody? And, and I will say that it will always be interesting to, at the very least you. Yeah. And. Almost certainly at least one other person and at the end of the day, if you're making good art for yourself and you're making good art for someone else, that's, that's a pretty good step in the right direction.

[00:59:39] **Ben:** And it's going to be much better than that in reality, but. Everything is interesting enough for somebody, trust me on that

[00:59:46] **Adam:** one. My mom says all of my art is good.

[00:59:49] **Carol:** So he even, he talks about that. He even says like, the best work he's ever done is things he did for himself that made him happy. And the worst things that he's ever put out were things that he did just to make money.

[01:00:03] **Carol:** Things that he did because someone told him he had to do it, so therefore he did it. And, you know, when he did it for himself and was just happy doing what he loved, it was the best, the best outcome.

[01:00:16] **Ben:** So I think we could probably all relate to that on some level.

[01:00:19] **Tim:** Just make

[01:00:20] **Ben:** good art. So we talk about doing lots of small little things, and it can make you feel like you're not achieving a lot.

[01:00:29] **Ben:** And that makes me think of this idea of the 10x programmer. You may have heard that get talked about in other presentations or podcasts. And it's this idea that there is a, it's this idea that there is a class of developer. That's so much more productive. They're 10 times more valuable than other developers.

[01:00:51] **Ben:** And people always talk about that this is actually based on studies that were done. And, um, a guy, I can't remember the name of the guy or the name of the book, but this guy wrote about all these history of these myths in the programming world. and he was being interviewed about it and one of the myths is the 10x programmer and he was saying that part of where this myth comes from is that it's a misinterpretation of the study that was done and What this guy found in a study from like the 60s or 70s was that the best programmers are 10 times more productive than the very worst programmers.

[01:01:28] **Ben:** It wasn't a comparison of the best to the average, which is typically how people discuss it. And I think it's, you know, terribly toxic to think about it in that term. Yeah. But when you realize that it's a comparison of the best to the absolute worst, you're like, yeah, I'm much better than the worst programmer, even if I'm not the best programmer.

[01:01:47] **Ben:** I think that's a much more healthy understanding of the original intent behind that study.

[01:01:52] **Tim:** It's kind of like comparing the Super Bowl Patriots versus a high school team, and it's really not

[01:01:57] **Adam:** fair, right? They're not comparable.

[01:02:00] **Tim:** It's, you know, yeah, some entry level programmer is compared to some guy who's known it for um, uh, 10, 15 years and is extremely fast at it.

[01:02:10] **Tim:** I mean, yeah.

[01:02:12] **Carol:** Who knows the application? Who knows the workflow? Who knows all of it? Yeah. They're not the same.

[01:02:19] **Tim:** But that's not to be said that maybe there's a few unicorns out there like Ben. Oh,

[01:02:25] **Ben:** well, it's interesting. I mean, so we've been doing this for a while. Technology, not this podcast. And. When you think about where we started in our respective careers, you know, when I started it was you did JavaScript or JavaScript, and then they invented CSS, and then they killed Flash, and then there were server side programming languages, and then there were, uh, unit tests, and then continuous integration, and all this other stuff, and it just, it's become so huge, and I think we have all had the benefit and the privilege of Learning that incrementally over decades.

[01:03:06] **Ben:** Oh yeah. Can you imagine we're sitting here talking about imposter syndrome. How about people getting into this field today and they don't have that. Slow burn of introducing new technologies. Today, you jump in and you have to know, you know, React, or Angular, and CSS, and HTML, and a server side language, and databases, and continuous integration, and containerization, and auto scaling.

[01:03:34] **Ben:** It makes my heart race. Right, I'm like, I'm saying it, I'm like, oh my gosh. On

[01:03:38] **Tim:** the flip side, on the flip side, I would... Totally want, if I could delete the VB script that I had to learn back in the day, I would totally. But it's still taking up space in my brain. They don't have to learn that stuff either.

[01:03:52] **Ben:** But I mean, that's a, talk about being kind to yourself. You have a lot to learn. Yeah,

[01:04:03] **Ben:** it's got to be daunting. I'm daunted by the things I have to, or at least that I feel like I have to learn. And that's on top of however many years I've already been doing this. I think

[01:04:13] **Tim:** we kind of missed a bit of the point here on the topic of imposter syndrome. Yeah, I think so. Yeah, yeah, I think, I mean, we have some good stuff, don't get me wrong, but...

[01:04:25] **Tim:** We talked a lot about insecurity. A lot of what we said really can just be insecurity.

[01:04:31] **Carol:** And they relate?

[01:04:33] **Tim:** I think they relate. But I think the, the key to impostor syndrome is that this is, this is a syndrome that people who have made it, you know, people who have reached their goals, who have achieved what they plan to achieve, and they still feel like a fraud.

[01:04:49] **Tim:** Ah, okay. Does that make

[01:04:51] **Carol:** sense? It does a little. I think, so to me, I think they go hand in hand, like the insecurity kind of lets it linger, lets it come up because you have some kind of insecurity. Maybe not though.

[01:05:03] **Tim:** Well, I mean, I think everyone struggles with insecurity at some point. But it's whenever you have maybe reached for a goal and you finally make it and then you reach that pinnacle, whatever that is, it can be professional, personal, whatever that that hill you're trying to climb and you finally get to the top and you know you've done it and you still feel like you're a fraud like every like people are going to come and take your trophy away because you didn't really earn it.

[01:05:33] **Tim:** I think that is the heart of what imposter syndrome is. I don't think we really...

[01:05:53] **Carol:** And, uh, there's podcast, so, yeah. You So we're talking about the people who are doing it right, but still feel like their trophy is going to be ripped away because someone's going to feel like they've done it wrong. Yeah,

[01:06:02] **Tim:** so that was Tom Brady, and I'm wearing my Falcons shirt right now, so yeah, I agree with you.

[01:06:08] **Tim:** Does

[01:06:08] **Carol:** he play for the Falcons?

[01:06:09] **Tim:** No, Tom Brady played for the Patriots to beat the Falcons in the Super Bowl.

[01:06:13] **Ben:** I'd just like it to be clear that I will never get a single sports reference that is said on this show.

[01:06:19] **Carol:** See, I only knew someone to... Flated some balls and they won something and they had the trophy taken away.

[01:06:26] **Carol:** I do that. I do that. The details non existent. I can see that. I can see that, you know, we kind of missed it a little bit. I would agree with you.

[01:06:36] **Tim:** Yeah, because a lot of stuff we said, everyone's going to feel about being an imposter at some point, but people where it becomes the syndrome portion, it's people that by any measure are extremely successful and everyone look at them and go, wow, they made it.

[01:06:51] **Tim:** And those are the people that they still for some reason feel like they're a fraud and they're afraid they're going to get exposed. I've seen that. I'll be honest, I don't think I've ever reached any pinnacle of success where I feel like that would be me.

[01:07:03] **Carol:** No, but I mean, but me looking at you, I feel like you're a success.

[01:07:07] **Carol:** Like you've done it right. You've, you've mentored people. You have an amazing family. Like your life to me is you've made that, like you've done it right. Yeah. I don't.

[01:07:17] **Tim:** feel imposter syndrome in that regard. I just feel like, okay, that's kind of, this is what I was working for. I don't feel like I was going to be taken away from me, but I, I've met people who have from nothing started multi million dollar companies through just sheer hard work and a bit of luck, honestly.

[01:07:34] **Tim:** And they honestly are scared to death because they have no clue how they got to where they got. Oh, I feel like they didn't earn it, and they don't deserve it. And it, it just weird. People that I've met who really suffer from this, it's a weird thing because they, they are constantly questioning themselves and they're also very suspicious at times of others who maybe seem like they're on the up and up, and coming up and rather than mentor them, they're a bit scared of them.

[01:08:01] **Tim:** Um, Like intimidated? Yeah. Yeah. Because they're afraid that these other successful people are going to expose them for who they really are, and it's all in their head.

[01:08:11] **Ben:** I see. So you're saying that what we've talked to previously is more just kind of a sense of insecurity and this is a sense of insecurity that's taken to a point where it's almost a paranoia and like a debilitating fear.

[01:08:28] **Tim:** Yeah. I mean, this, this is a, I mean, if you look at it on the Wikipedia, it is a psychological pattern. I mean, this is kind of originally, uh, diagnosed with particularly prevalence among high achieving women back when. You know, women breaking the glass ceiling was extremely rare, um, and this postural syndrome that, that kind of became a debilitating, crippling thing in their life.

[01:08:50] **Tim:** But yeah, you see it in more and more with, particularly the tech industry, where honestly a lot of people that have become extremely successful in tech industry, it's because they were at the right place at the right time. I feel like that. And that sense of luck, you know, that they get, they feel like they're, you know, they're millionaires, billionaires.

[01:09:12] **Tim:** They feel it's unearned because they realize that they're maybe not smarter than the other people around them. But to be honest, they were at the right place at the right time and they made their millions. They cashed out and now they're... Everyone looks at them like they're some guru and they inside don't feel really different from anyone else.

[01:09:30] **Tim:** So they, it becomes sort of a toxic feeling to them.

[01:09:34] **Ben:** Interesting. Yeah.

[01:09:38] **Tim:** That's all I really had. I mean, that's, I just, I just wanted to check that out. No, I

[01:09:41] **Carol:** think that's good. I think it's, it's a good kind of, I wish we could have entered that. I wish we could have entered that way and maybe, you know, we would have kept on topic a little better.

[01:09:50] **Carol:** No, I

[01:09:51] **Tim:** don't think we got off topic.

[01:09:51] **Carol:** Dang, Tim! Where were you at when we recorded the first time?

[01:09:56] **Adam:** I was

[01:09:56] **Tim:** sleepy. That's where I was. So, that's all I had. No, it was good.

[01:10:03] **Carol:** Good information. It's very interesting and I agree. Yeah.

[01:10:07] **Ben:** I'll tell you, uh, I had, I had wanted to bring this up on the previous show, but I didn't really have a, a, the right moment and, um,

[01:10:15] **Adam:** no entry

[01:10:16] **Ben:** point there.

[01:10:16] **Ben:** Yeah. There was no, there was no appropriate ingress, uhhuh, , uh, and that's a B L C word. Yeah. Yeah. Ingress. Ingress, ingress and egress . Um, and, uh, I, I was listening to an episode of, I want to say it was Freakonomics the other day, and they were talking about people who are good at lying to themselves. And uh, and they were interviewing the, I think it was swimmers on the show.

[01:10:45] **Ben:** And they would ask some swimmers if, if, uh, there are these things that they can imagine about their life that aren't true. And the ones that were unable to imagine these uncomfortable thoughts tended to actually be more successful. in their sport. And uh, they were saying that because like they get on that starting block or they get out on the field and there is no, there is no possibility that they lose in their minds.

[01:11:12] **Ben:** And uh, and they ended up being more successful, but, um, sorry, I don't actually know where I was going with this. Let's just get the whole thing out.

[01:11:19] **Tim:** Cut that out. I can see that. I mean, if you, if you. Particularly in sports, visualization is a big thing. Visualize yourself making the shot. If you visualize all the ways you're going to miss, chances are you're going to miss.

[01:11:31] **Adam:** Your hands start

[01:11:31] **Carol:** shaking, your heart starts racing, where if you feel like no matter what you do is going in the basket, you're just kind of more, you're steady, you're secure, you're, you know, everything's, everything's lined up.

[01:11:43] **Ben:** It's so interesting though. I mean, this is way off topic at this point, but in terms of programming, I feel like when you see people who And they have this sense that it's just going to work out.

[01:11:55] **Ben:** I feel like those are the people who make a lot of mistakes or they deploy something not considering an edge case and it's, you know, a terrible oversight. And then,

[01:12:04] **Carol:** yeah, oh no, sorry.

[01:12:06] **Ben:** And the people who think about what's everything that can go wrong. Like, let me, let me do the pre post mortem in my head.

[01:12:16] **Ben:** Like how did, how did I fail? And now let me fix that before we do it. Thank

[01:12:20] **Carol:** Yep. Yeah, we, I think we've all seen that happen. Um, I know I have personally, and I've been in that spot where I'm going, hey, let's just get this out quick. Let's just keep it moving, you know, and then we start releasing things because we aren't thinking through it all.

[01:12:32] **Carol:** We feel too secure in that people trust us to just get it right, that we forget to stop and think through everything, and then we break stuff.

[01:12:43] **Tim:** Yeah, because I mean, with programming, you, you've got to The happy path is the easy path, right? Figuring out the happy path when you read code, you decide, all right, let's just assume everything goes the way it's supposed to, and what does that...

[01:12:58] **Tim:** If you stop there, it, you're not done, you got to figure out, all right, how, what are all the ways that someone can come through this process and really try to mess things up? And now you've got a program for that. So yeah, I think that level of pessimism is, is sort of needed and you have to,

[01:13:18] **Carol:** yeah, yep.

[01:13:19] **Carol:** Absolutely. I agree. It's needed.

[01:13:22] **Tim:** If you're feeling those feelings of imposterism or fraud, um, having a support system that pushes you can help you get past that. And I think that may have triggered what you were thinking about.

[01:13:32] **Carol:** Yeah, for me, um... I feel like a lot of people think I have my _(quack)_ together, right?

[01:13:38] **Carol:** Like, and typically I pretty much do. Maybe I shouldn't say _(quack)_. I don't know if I think we were trying to avoid the curse words. Right? He'll bleep it out. Let's bleep it out. twice now. Everybody throw in one if you want. So, um, I feel like I have my things together pretty well and people around me tend to think that.

[01:13:55] **Carol:** So when it hit me hard. I think it came from like what you were saying, the background, um, I came from foster homes and I came from a mom at 16 and, um, a pretty rough background starting into this and I didn't have the support of people going, you can do this, keep trying, you'll figure it out, um, as a

[01:14:17] **Tim:** teenager.

[01:14:18] **Tim:** So you say from a mom at 16, were you saying you were

[01:14:22] **Carol:** a mom? Yeah. Oh yeah. Yeah. I had a kid at 16. So I've been a mom for a hot minute, you know, hot minute. Um, and they're both, my kids are amazing. They're, they're really good kids, but so I'd never came from. Like, uh, like a good solid foundation of you can do it.

[01:14:41] **Carol:** You can do it. So when I decided to, you know, reach out to Ben and it hit me that someone's going to realize I don't belong here, it kind of just triggered everything. I think like, you don't belong. You don't belong. So don't do this. Just go back. And maybe that's insecurity like you were talking about, or maybe it is.

[01:15:01] **Carol:** Part of the imposter syndrome, but everyone around me was like, look, you could do it. You can do it. And I'm sitting here going, if I show it to him, clearly I can not do this. So I think. Knowing that you can, sometimes you just need someone to tell you, like you were saying, not everyone comes from somewhere that had the people telling them.

[01:15:19] **Carol:** And that is, is key to success is having a good support system.

[01:15:24] **Tim:** Yeah. Wow. I did not know that. I mean, when I first met you, all I saw was someone that was very talented and determined and I never would have guessed that about your background, Carol. Oh,

[01:15:34] **Carol:** thank you. I appreciate it. Yeah. I'll never forget the interview with you.

[01:15:38] **Carol:** You were like, do you know what ColdFusion is? I was like, Like nuclear science? Is this like, what are we doing here? This is a really small place to have anything radioactive. I don't know.

[01:15:50] **Tim:** Yeah, so full disclosure for those that don't know, I hired Carol probably for your first job, right? Your first programming

[01:15:57] **Adam:** job.

[01:15:57] **Carol:** It was my, that was actually my first like, yeah, my first tech job. As an intern in college, the dean reached out and was like, hey, we have these, these things that we're trying to get going and we think you'd be perfect. Go try it. I was like, okay. I was

[01:16:10] **Tim:** working with the local colleges trying to get some, uh, some college students in to, uh, get programming jobs.

[01:16:17] **Tim:** Wow. That's, that's amazing. I did not know this story about you.

[01:16:21] **Carol:** And then Ben made me cry.

[01:16:26] **Tim:** He's a big bully, that Ben.

[01:16:29] **Ben:** It's super interesting. I mean, it's such a fascinating story, but just, it offers so much perspective on The amount of stuff that people can take for granted that you would never think is something you can take for granted. Like, Oh, you had parents that encourage you to be great, like that, you know, there's a, there's a certain degree of privilege in just having that kind of situation that you don't even, you're not even cognizant of it most of the time.

[01:16:56] **Adam:** Yeah. Alright, well that seems like a good enough place to wrap it up. Uh, I want to thank everybody for listening. We are officially live now, and we have, like, listeners, and, and, uh...

[01:17:06] **Tim:** No haters. We need haters.

[01:17:09] **Adam:** Uh, and, uh, so I guess with that, uh, just want to say thank you to everybody that's listening. Remind you to please share the podcast with a friend if you think that there's somebody that would, uh, enjoy listening to this.

[01:17:21] **Adam:** Maybe somebody that's suffering with imposter syndrome and, and, um, needs a pick me up. Um, so, you know, those word of mouth referrals really help us out. If you are still feeling generous after that, we would love, uh, a five star rating on iTunes or wherever you get your podcasts, uh, that's supposed to help us out a lot.

[01:17:39] **Adam:** If you have anything you want us to talk about on the podcast, hit us up on Twitter or Instagram. @WorkingCodePod, and I guess, uh, until next time, have a good night.

[01:18:08] **Tim:** Wow. I just got notified zoom 5. 42 is here. Oh, you're going to want to get on that. Yeah. Get on that

[01:18:14] **Ben:** quick. If you thought 5. 41 was great,

[01:18:19] **Carol:** sit down.
