---
title: "010: Scaling"
description: This week, the crew talks about their experience in scaling web application systems; what they have - and _haven't yet_ - had the need to consider; and, how they calculate the return on investment (ROI) when it comes to adding complexity to a potential solution ("innovation tokens", anyone?).
date: 2021-02-17
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/010-scaling/id1544142288?i=1000509526078"></iframe>

An engineer at SquareSpace once referred to his company as "an overnight success, 7-years in the making." This cheeky insight pays homage to the _marathon of work_ that is often required when building a successful product and / or business. Which begs the question: when is it appropriate to start thinking about scale? Should you be taking it into account during early ideation and the construction of your MVP (Minimum Viable Product)? Or, should you kick the can down the road with the assumption that you can always throw money at the problem later (either by hiring smart people or by vertically scaling your existing compute resources)?

This week, the crew talks about their experience in scaling web application systems; what they have - and _haven't yet_ - had the need to consider; and, how they calculate the return on investment (ROI) when it comes to adding complexity to a potential solution ("innovation tokens", anyone?).

If you like this episode about scaling, you may also enjoy our previous episode on [Monoliths vs. Microservices][working-code-005].

### Triumphs &amp; Failures

-  **Adam's Triumph** - After switching to a new platform, his ORM (Object-Relational Mapping) code stopped working for "reasons". And, instead of spending a whole week trying to figure it out, he just spent a single day replacing the problematic ORM queries with native SQL statements. This was a veritable "Master Class" in pragmatic problem solving.

-  **Ben's Failure / Triumph** - This week has been _kicking his butt_! He's exhausted and stressed out - even his feet hurt. This is due, primarily, to the HTML emails that he's been crafting at work. That said, he's been able to take his "failure" and transform it into a "triumph" by channeling that frustration into an exciting new approach for building HTML emails that's powered by ColdFusion Custom Tags. It's still early, but he's hella stoked on the concept!

-  **Carol's Triumph** - She wrote some rather complicated code that dealt with edge-cases in her application that weren't really ever going to happen. And, when her teammates discussed this with her, she did the honorable thing and removed her code, leaving in its place a much simpler solution. The real triumph here is that she was able to overcome the "sunk cost fallacy" we engineers often succumb to when having to confront the questionable value of our own solutions.

-  **Tim's Failure** - What started out as a thrilling exploration of Redis has turned into a battle for sanity! For reasons that he has not yet been able to understand, the data that he's been writing to a Redis cache isn't always available for immediate read. This is in his local development environment and he's _the only one_ hitting the code. It just doesn't make any sense!

### Notes &amp; Links

-  [Redis](https://redis.io/) - a blazing-fast in-memory data structure store.
-  [CFRedis](https://github.com/MWers/cfredis) - a ColdFusion client for the Jedis Java driver for Redis.
-  [Jedis](https://github.com/redis/jedis) - a blazingly small and sane Java client for Redis.
-  [Mango Blog](https://www.mangoblog.org/) - an extensible blog engine released under the Apache license, built with ColdFusion.
-  [CockroachDB](https://www.cockroachlabs.com/) - a distributed SQL database built on a transactional and strongly-consistent key-value store.
-  [Dan McKinley: Boring Technology Club](http://boringtechnology.club/) - a spoken word version of Dan's essay, "Choose Boring Technology".
-  [Ben Nadel: "Enterprise" is not a dirty word](https://www.bennadel.com/blog/3976-enterprise-is-not-a-dirty-word.htm) - a blog post discussing the merits of "enterprise" software.
-  [FrameworkOne (FW/1)](http://framework-one.github.io/) - a light-weight conventions-over-configuration framework for ColdFusion web applications.
-  Blocking-Request Budget - a concept in which serving a user's request can only entail a limited number of blocking requests.
-  [AWS Fargate](https://aws.amazon.com/fargate/) - services compute for containers.
-  [AWS Lambda](https://aws.amazon.com/lambda/) - a "functions as a service" (FaaS) platform.
-  [Mailgun](https://www.mailgun.com/) - an email service provider (ESP) built for developers.
-  [Let's Encrypt](https://letsencrypt.org/) - a nonprofit Certificate Authority that has brought free TLS certificates to the masses.

Follow the show! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-005]: /episodes/005-monoliths-vs-microservices/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/010-scaling.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:14] **Adam:** Okay, here we go. This is show number 10 for February the 17th. And on today's show, I believe we're going to be talking about scaling. We'll get to that. Uh, but first we're going to do our triumphs and fails. And Carol, I'm going to come to you first this week. What do you got?

[00:00:28] **Carol:** Sweet! So, um, I don't really know if you call this a triumph or a failure yet, so you guys kind of got to help me figure it out.

[00:00:36] **Carol:** So, I told you about the project I got put on with my two design buddies who were working on this big effort, right? So I spent a couple hours writing some code that... Just basically, you know, found out if some values were unique, and if it was, it let the unique value remain. Otherwise, it just forced the user to make a change.

[00:00:55] **Carol:** It was like, okay, we can't determine what is accurate, so you have to figure that out. And I put it up, and I'm like, hey, it's out there, move on to something else. And then I get a ping that's like, hey, can we talk about the code you just submitted? And I'm like, yeah, sure, let's talk about it.

[00:01:14] **Carol:** So yeah, we were just thinking that we could go, if it's this, good, if not, then that, then we're good to go, right?

[00:01:21] **Carol:** I was like, yeah, you probably could do that. I was just trying to, you know, get it pretty accurate. And the two of them were like, yeah, I think we could just go the other way. And I was like, all right, cool. I will take my code out. And I guess my, my triumph feeling is that I didn't cry. I was like. Cool, I'll just rip it out and put an if statement here and I'm good to go.

[00:01:43] **Carol:** And at the end of it, I was like, it's fine. Actually. It's doing the exact same thing, just a lot less complex than what I wrote, so I didn't cry when I had to remove my code.

[00:01:54] **Tim:** So were you trying to be a little too fancy, in their opinion? I mean, what was the reason that just an if statement sufficed?

[00:01:59] **Adam:** Yeah,

[00:01:59] **Carol:** I mean, I think it was that it was doing more than was actually needed, and the situation where this would ever happen was almost never going to happen, except with my mock data, which caused it to happen.

[00:02:14] **Carol:** So if it's never going to happen, then we're good to just assume it's never going to

[00:02:19] **Adam:** happen. I listened to another podcast that is, uh, All the people on it are video creators, they're like YouTube personalities and they're all in woodworking and they talk about sometimes how they have to murder their babies, right?

[00:02:32] **Adam:** So they, um, they, they make the project and they record all this stuff and they think of the thing that they're crafting, the story they're telling, the video as, you know, something that they love and they, they, um, it's like a child, right? They're creating this thing. Um, in order to, uh, tell the best story, or for whatever reason to hit some sort of time goal or something like that, they have to cut a lot out, and it's, it can be a hard feeling to get rid of something that you really feel an attachment to.

[00:03:05] **Adam:** Attachment to, yeah. Yeah, so they call it, you know, murdering your babies. Although

[00:03:08] **Tim:** the petty person in me would, would mark down somewhere that code and then if that edge case ever does happen, like two years from now, you'd be like, look, I told you guys.

[00:03:19] **Carol:** So it's pretty much like, how often is a school district going to be split when you live in the house?

[00:03:25] **Carol:** Like when are you going to have an elementary school, a middle school and a high school that aren't in the same school district for that address? You don't know? Yeah. You don't know? My mock data said it was gonna

[00:03:37] **Adam:** happen all the time. A

[00:03:39] **Ben:** hundred percent of families. Always.

[00:03:42] **Tim:** That's a hill to die on, Carol.

[00:03:43] **Adam:** A hill to die on.

[00:03:44] **Adam:** Yes, yes. But without crying. Okay, well I guess I'll go next. Today I had a really rough day. I'm not, I'm gonna call this a triumph though. I had a really rough day. It was one of those days where you just, you spend your entire day working on one thing and by the end of the day I had a headache and my eyes were glazed over and I just...

[00:04:03] **Adam:** I felt like, every time I felt like I was getting near the end of this task, I found another little hallway I had to go down, and, and you get to the end of that hallway and there's another one, and the end of that hallway and there's another one, and it's just, it, it, I was refactoring a function, uh, and removing ORM and putting in, uh, SQL queries, and, It just kept going and kept going, always with the abstraction.

[00:04:28] **Adam:** And it took me all day, but I finally got it out onto QA by the end of the day. And after several rounds of fixing the parts that didn't work the first time through, it's finally working. So, that's my triumph, is it took me all day to do one task, but... I got it done, and I don't have to think about it tomorrow.

[00:04:47] **Adam:** So

[00:04:47] **Tim:** if I heard you right, you're taking out ORM? Yes. And putting in just, so, I mean, I thought ORM is like the magic bullet that fixes everything. Why would you ever do that?

[00:04:55] **Adam:** Kind of

[00:04:56] **Carol:** like how Ben hates microservices?

[00:05:00] **Adam:** Um, well, I mean, I guess to answer your question, we, it's not a philosophical thing. It's a technical thing.

[00:05:06] **Adam:** The, um, the ORM code was working fine. on the old platform and on the new platform, uh, it's for whatever reason causing issues. And instead of spending a week troubleshooting, it took me a day to just rewrite the whole thing in queries and it's fine. So, and it, it had something to do with mixing queries and ORM and something that sounds totally benign and like it shouldn't matter, but.

[00:05:30] **Adam:** Unfortunately it does. So, uh, it's just like, it sucks, but it's, this is the hand we've been dealt. So we're going to fix it. Yeah.

[00:05:38] **Tim:** ORM is great when it works, but when it doesn't work, I find it very hard to figure out why it doesn't work. Yeah.

[00:05:43] **Adam:** Yeah.

[00:05:45] **Ben:** One of the things that I do with SQL that it, I hadn't, I didn't think of it for a few years and then I started doing it and it just made such a huge difference and it's going to sound crazy.

[00:05:57] **Ben:** But at the top of every query that I write,

[00:06:00] **Adam:** I put a bunch of comments, Ben, no,

[00:06:03] **Ben:** no, I do, I put a comment at the top of the query that says the name of the file and the method that is running this query. Oh, yeah, because what happens is then when things start to show up in the general log or the slow log, it tells me exactly where that query is getting run from.

[00:06:20] **Ben:** And, um, it helps tremendously. For locating performance problems. Yeah, it's a good idea.

[00:06:26] **Tim:** I should start doing that.

[00:06:28] **Carol:** I don't see the point of it. I guess I'm missing something.

[00:06:32] **Ben:** Because so if you're, if you're, it's, it's one thing to think about performance when you're looking at the application code and you're running your tests.

[00:06:39] **Ben:** Right. But it's another to then be reactive to performance problems in production where you see that. It's, old says, specifically for those on the side that want to get some more education or really solve problems by doing stuff yourself. Um, It's winners say like, What do you mean by data? Um, as you can see, things like when

[00:07:00] **Ben:** you

[00:07:14] **Carol:** click delete, you'll just get deleted. But right when you're done unboxing, Now, now I'm following.

[00:07:19] **Adam:** Yeah,

[00:07:20] **Tim:** because I've done a lot of that, trying to troubleshoot, like, some SQL statements that are, like, killing the server, and you don't know why, and you're not really sure where it's coming from. Yeah.

[00:07:29] **Tim:** Particularly in a terrible, uh, a system that's using triggers, which... Mmm. Don't ever put... No, no, no. Don't ever put... Triggers is a... Don't ever put business logic in triggers.

[00:07:37] **Adam:** It's the worst thing. Don't put anything in triggers. Triggers

[00:07:41] **Tim:** are just bad. Triggers are

[00:07:43] **Adam:** ridiculous. You can't troubleshoot podcast. Yeah.

[00:07:47] **Tim:** Oh, I could, I could talk for days on how much I hate triggers.

[00:07:50] **Adam:** Oh. Okay, uh, well, Tim, why don't you keep going? You got a triumph or a fail this week.

[00:07:56] **Tim:** Alright, I'm not gonna try to be like you guys and sugarcoat a, a failure as a triumph, okay? I, I, I flat out failed this week. Not this week, the past two days.

[00:08:08] **Tim:** So, earlier... I spoke about how I wanted to, you know, I'm using Redis now, and I was in love with Redis. Well, I hate Redis now.

[00:08:19] **Adam:** And it's probably not fair to Redis. I'm sure it's not Redis fault. We

[00:08:23] **Tim:** still love you, Redis. Yeah, it's probably something I'm doing. It's, it's, you know, it's not you. It's me, Redis. So, I, I've got the Redis cluster set up. I'm writing to the cluster, doing an object cache, and On my local it works fantastic, but when I actually put it up, I have a load balancer with multiple instances, and all the instances are talking to the Redis cash store.

[00:08:48] **Tim:** And periodically, and that's the worst part, it's not 100%. There are things I will put into the cash that should be there, and then I immediately call the cash to get it out, and it's not there. And I can't figure out why it is. Now I've, I've alleviated it somehow by doing a terrible workaround of, I wrote a function that whenever I'm putting stuff into the cache, I basically do a block to say, all right, I've just put it in there.

[00:09:18] **Tim:** Now I'll now check, do I have it? I'll go get it. And if I don't get it, I will keep trying to get it and doing a pause in between until I get it. And that works, but I don't Redis is it's supposed to be super fast. So I don't know If my Redis setup is wrong. I don't know if there's network communication that that's missing I don't know the the driver that i'm using for this is a release candidate.

[00:09:45] **Tim:** It is not Uh, uh, version one, so it's somewhat kind of still beta, so I don't know if that's wrong. Could be playing into it. Yeah, I, I don't know where it, or if I'm just using it wrong.

[00:09:57] **Adam:** Right, I don't know anything about Scala, but I, it sounds like what I would expect if I was using an async writer, but assuming it was synchronous.

[00:10:06] **Adam:** So it's not done writing,

[00:10:07] **Tim:** is it? This actually isn't in Scala. This isn't Lucy. So, but

[00:10:10] **Ben:** when you say cluster, just to paint a clearer picture, are you saying you have a primary Redis cache and then you have replicas? Yes. Okay, so you, you think that you're writing to the primary. And then your read is maybe hitting a replica and it hasn't replicated yet.

[00:10:26] **Ben:** I don't even

[00:10:26] **Tim:** think that far because I mean the driver is set up to only really talk to the primary. Gotcha. So I don't see how it would even know about the replicas. The replicas are just there for redundancy. Um, so yeah, I'm just baffled. It's one of those things when you start writing code to try to fix a problem and then you...

[00:10:45] **Tim:** All day yesterday I wrote and wrote and wrote and then I got it to where it was somewhat working but it still wasn't 100% so I basically deleted everything I did yesterday.

[00:10:54] **Adam:** I hope you stashed it. Murder that baby.

[00:10:56] **Tim:** I mean it was on a branch but I'm like you know what this this shouldn't be this hard.

[00:11:01] **Tim:** Yeah. Right I'm just putting stuff in a cache and getting it back out it shouldn't be this hard and I still don't at the end of the day I'm still wondering I don't know where the failure is.

[00:11:11] **Adam:** I feel like the failure. Um, I have some, I have a, some loosey code that's hitting Redis, uh, we're using CFRedis and...

[00:11:22] **Adam:** We use JEDIS at work. It's the Java... I think that's, I think that might be what we're using under the hood. Like CFRedis is a CFC wrapper for JEDIS. Um... And I, we haven't had any of that problem, so I can send you my code, maybe, and... Yeah, maybe, maybe I need to,

[00:11:35] **Tim:** yeah, just use a different one, because I'm using the, uh, the Lucy, the standard Lucy Redis provider.

[00:11:42] **Tim:** Hmm. Um, and it's a release candidate, it's not, it's not, they don't have a version 1 yet, so I don't, I don't know if they're the problem. I don't, I would imagine if it's a release candidate, it's probably closed. I'm not doing anything really that spectacularly difficult. Is it

[00:11:57] **Ben:** just you, or is it, uh, are there other people trying to hit this code at the same time?

[00:12:03] **Ben:** It's just

[00:12:03] **Tim:** me. I'm not, yeah, it's just me. In

[00:12:06] **Ben:** a, in a, if it was a, if it was like a concurrent request situation, getting unexpected data would lead me to think there's like a un, an unvarred variable that's leaking into the page context. And then maybe someone else's request is resetting

[00:12:25] **Tim:** the variable.

[00:12:28] **Tim:** Yeah, not if it's just single threaded and I'm uniquely naming the key that I'm storing, so, you know, so, anyway. Yeah, I'm frustrated, but yeah, I will take you up on that, Adam. I will look at that and next week we'll be talking about what a hero you are.

[00:12:45] **Carol:** Look, your failure just

[00:12:46] **Adam:** turned into a triumph. Yeah, I'll send you my Patreon link and...

[00:12:53] **Adam:** Okay, Ben, what do you got?

[00:12:55] **Ben:** Uh, I have a failure and a triumph. Failure is that this week has just generally been kicking my ass. Um, I've just been tired and stressed. All week I've been working on putting together HTML emails and it's just emails are

[00:13:12] **Adam:** terrible, never fun,

[00:13:14] **Ben:** never fun. And, um, and these are building on top of emails that someone else wrote.

[00:13:19] **Ben:** So it's, I don't even have the kind of the contextual thinking about how they were put together. And like even my feet hurt and I'm, I sit down all day and just like the stress has been. Everywhere. So I'm exhausted. I'm so happy that tomorrow's Friday, but on the flip side to that, I've been thinking about these emails and, and kind of scraping the bottom of the barrel of my mind, trying to come up with a way to make it more enjoyable to build emails and I'm doing some R&D on using ColdFusion custom tags.

[00:13:53] **Ben:** As a way to create a DSL domain specific language. Oh, it's a deep cut for putting together some emails. And, uh, it's still, it's still pretty rough, but I'm, I'm, I'm kind of stoked on where it's going. It's a, essentially I put together stuff that looks like just vanilla HTML and I can sprinkle in some styles and it has all the power of ColdFusion behind it.

[00:14:16] **Ben:** So, you know, right now, when we at work, when we put together an HTML email, we import these node modules and then you have to compile the node module, like you have to run it through grunt and grunt takes all the CSS and it inlines it into the styles and then it, it does all this other weird stuff. And it's such a pain and.

[00:14:36] **Ben:** If I can get to a point where it's just edit some ColdFusion code, refresh the page, and it works. Sweet. Sitting pretty. So I'm tentatively stoked on where that's going. Nice.

[00:14:47] **Adam:** That's pretty cool. Yeah,

[00:14:49] **Tim:** I've had to write some, um, responsive email, HTML, and it's, it's so, it's, it's very much like working, you know, seven years ago, because everything is inline styles.

[00:15:00] **Tim:** You really can't be doing the whole CSS tags and everything in emails. It just doesn't understand that. But Outlook

[00:15:07] **Ben:** still uses Microsoft Word to render their emails, I believe.

[00:15:11] **Adam:** Yeah.

[00:15:13] **Tim:** But yeah, there's a, there's a few places out there that have some templates that are actually pretty good. Yeah.

[00:15:19] **Ben:** Yeah. Carol was mentioning she had some, uh, responsive receipt templates that she was using.

[00:15:24] **Ben:** I think that was Tim. Oh, that was Tim. I'm sorry. We

[00:15:27] **Carol:** sound just alike. It's fine. We look alike too. You look alike too. Yeah. You just were like, someone from Georgia gave me this.

[00:15:35] **Ben:** I don't people well, as Carol said.

[00:15:38] **Carol:** I don't people well at all. So I would like to say, you had said previously that you got some feedback at the session that you gave on custom tags.

[00:15:49] **Carol:** Yes. That said it was pretty vanilla, right? Pretty basic, yeah. Pretty basic. Is this like your, I need to do better now? Like, I'm going to improve my, presentation

[00:16:03] **Adam:** 13 years ago? Look at this. Uh huh. No, it's really. Read it.

[00:16:08] **Carol:** Actually. Yes.

[00:16:12] **Ben:** I don't know. I think it's pretty cool. I think it's going to be. Custom

[00:16:16] **Adam:** tags is one of those things that I feel like 90% of the things that 90% of the people need to do with them is boring. Yeah,

[00:16:25] **Carol:** they don't do

[00:16:25] **Adam:** anything fun with it. It's a view layer encapsulation technique.

[00:16:30] **Adam:** Uh, but I have been exposed to some custom tag stuff that kind of like blew my mind. Yeah. There was a blogging engine for CFML called MangoBlog. Um, and it heavily used custom tags and they like, um, provided data to each other with like a context sort of thing. And I had never seen that done so well. And it was, it was, I never fully understood it.

[00:16:58] **Adam:** That's how cool and, uh, like, uh, powerful and complex it was. It was like, it would take, honest to goodness, studying. And I wasn't willing to do that. I was just like, I need to get my thing done, go over here and do the work.

[00:17:11] **Ben:** Well, that's, I mean, that's some of the stuff that I'm trying to do here because you can, you can nest the tags and then to your point.

[00:17:18] **Ben:** Uh, you have the get base tag data where you can start to reach up into ancestral tags and you can interact with the page scope inside of those tags. And, uh, so I'm using that to, to essentially implement some of the cascading properties of CSS, but in a, in a kind of DOM traversal way where the DOM is custom tags.

[00:17:40] **Adam:** Interesting.

[00:17:41] **Ben:** We'll see. It might be a hot mess, but at the moment it's balancing out the, uh. The tragedy that is my working hours.

[00:17:49] **Adam:** Cool. Well, hey guys, you want to talk about scaling? Sure.

[00:17:54] **Tim:** Yeah. All right. I threw this out there because scaling is one of those things that. In my mind, I don't think about until it's too late.

[00:18:06] **Tim:** I don't know at what point you really start to take scaling seriously because scaling is hard. I'm going to say it up front. It is hard. It is a design choice that has long term consequences to your project. And typically, but typically with a project, I start out with a proof of concept, right? So I just want to build something.

[00:18:27] **Tim:** I'm not going to worry about scaling in a proof of concept. Just not going to do it. And then you come up with an MVP, right? The Minimum Viable Product. Maybe I do it there, but a lot of times I don't. But then sometimes what happens because of real world concerns is you take your MVP and what happens, your MVP starts selling.

[00:18:47] **Tim:** Yep. And now. You got to worry about scaling because at some point, you know, this thing's going to fall

[00:18:53] **Adam:** over. Before you know it, you're seven years in and you're restarting the application every six hours so that it doesn't fall over when you're taking a nap. Scheduled restarts at midnight.

[00:19:03] **Tim:** Exactly. So, I mean, scaling is a hard topic for me because I don't know necessarily how to define it because scaling can mean different things for different purposes and when to do it.

[00:19:19] **Tim:** So that's what why I'm throwing this this out on the table is. What do you guys, I mean, help me, what, how do we,

[00:19:27] **Adam:** how do we scale? You're not

[00:19:28] **Carol:** talking about scalable code. Like, I feel like when we all write code, we think of scaling, right? We're thinking of how it's going to run low or how it's going to run high.

[00:19:38] **Carol:** I know you're not talking about code specific, right? You're talking

[00:19:41] **Adam:** about just... Well, I mean, code's

[00:19:42] **Tim:** definitely a part of it. I would think modular code can tend to be more scalable. That's my opinion. But I'm talking about more about, like, for instance, your database. For me, database is always... It seems to be the, the one point of failure and the one bottleneck because everything all your code is really is doing is just massaging stuff to stick it in a database at some point or some, somehow to persist the data, um, which is why I've been, we'll talk about this a little bit more later is why I've been looking at CockroachDB, which is the distributed database.

[00:20:15] **Tim:** Oh, that's a real

[00:20:15] **Adam:** thing. Oh yeah. CockroachDB.

[00:20:17] **Carol:** Yeah. I haven't even looked at that. I thought you were just joking about something. Dang.

[00:20:23] **Adam:** Should've

[00:20:23] **Carol:** Googled that one.

[00:20:25] **Adam:** Yeah, Adam's got a

[00:20:26] **Tim:** sticker there. Yeah. So

[00:20:28] **Ben:** I think, I think though, you talked about scaling, not thinking about scaling until it's too late. And I almost think that that's the right time to think about it.

[00:20:40] **Ben:** It's when it's a little bit too late. Because

[00:20:42] **Tim:** if you plan ahead, you don't know what

[00:20:45] **Carol:** you're truly planning for. Like.

[00:20:50] **Carol:** To me, you don't know what the outlook's gonna look like, but once you need it, then you see the, the issues that are arising, you see what you actually have to work with.

[00:21:00] **Adam:** I think maybe the middle ground here is to have an idea of what it would take to scale various parts of your application, like, um, the database or a particularly CPU intensive process or something like that, um, whether it be, uh, you know, I need to put this on a powerful server, um, This would be like scaling up, or I need to run this massively parallel, so like on lambda or something with a lot of parallel execution.

[00:21:34] **Adam:** Have an idea of what you want to do to Deal with any particular, uh, feature in order to, uh, handle it, not being able to keep up anymore and then build in a way that's not going to stop you or slow you down too much from doing that. That's kind of what I have in mind. So, like, I agree with Ben and Carol saying, like, don't even.

[00:22:00] **Adam:** I don't write a line of code specifically for the purpose of scaling until you can't, the code that you have can't keep up anymore, but I guess my caveat to that is don't intentionally take on the technical debt that's going to make it harder, significantly harder for you to scale that when it comes time.

[00:22:21] **Adam:** And I think the other thing, the other piece that I keep thinking about here is that, um, writing code for scale. It's difficult to get from one to two, but once you can do that, going from two to 17 to 147 parallelization is, is easy or easier. But

[00:22:43] **Tim:** I mean, a lot of the assumptions, not assumptions, let me back up.

[00:22:50] **Tim:** So the choices that you make as. As far as, uh, your caching strategy, your load balancing strategy, your, uh, your persistence layer, what you're going to use as your database, all of those things feed into scale. But scale can mean different things. For instance, does scale mean, are we going into new geographies?

[00:23:12] **Tim:** So we're not just North America, you know, we, we, we're in China, we're in Japan, we're in Asia. We're in India, we're in, you know, we're in Europe, we're all, we're global. That is a different kind of scaling than just saying, our target customer is North America, uh, during this time period and it's a very kind of, uh, targeted

[00:23:33] **Adam:** market.

[00:23:34] **Adam:** So that's more like geographic scaling and latency?

[00:23:39] **Adam:** Is that kind of what you're worried about there? Yeah. So,

[00:23:41] **Tim:** I mean, are you trying to scale so that, that people from all over the world are going to get the same experience? Versus your North American people, because you happen to be in North America, are getting a good experience, but your, your customers in Japan are not getting an experience because, you know, you've built it.

[00:24:00] **Adam:** So I guess, I mean, the question I'm asking myself is, are you talking about, you need one central source of truth? So you don't want to have like, you said you're, you're talking about this globalization problem. You don't want to split it up into separate, if you're building Twitter, you don't want India Twitter and Asia Twitter and North America Twitter.

[00:24:17] **Adam:** You want one Twitter that they all share. Yeah, exactly. Um, yeah. No, I have not had the pleasure of having that problem yet. Right.

[00:24:28] **Tim:** And, and I haven't either, but it's like, it could be a problem. So where do you decide that? Do I worry about that now? Right? So, I mean, we deal in financial markets and the financial markets are global.

[00:24:40] **Tim:** So, do we worry about that right now or do I just put that problem off until, you know, we get our first, you know, uh, we have customers in North America and Canada and Europe, but I worry about Asia and, you know, at some point, do I just worry about that then and then have to address it? And now I realize that.

[00:24:59] **Tim:** Some other choice that I've made prior, uh, using a replicated MySQL server all locally is now hindering me because the latency between them is far. So that's, that's

[00:25:12] **Adam:** what I'm struggling with. My honest answer? I kick the can and then I hire somebody really smart to deal with it

[00:25:18] **Ben:** for me. Well that's, that's what I was going to say too because I, I, my biggest limiting factor.

[00:25:23] **Ben:** Is that I can think as far as my skillset, and I don't know how to build a globally distributed system with, you know, multi zone region replication and Amazon web services that that's, that's like a whole team of people doing that, whatever that is. I think in the early days of trying to ideate on a product.

[00:25:47] **Ben:** And come up with your MVP. There there's not to be flippant about it, but there's something to say that early scaling problems, you can throw money at bigger servers, you know, scaling up. Nobody wants to scale up long term, but in the short term, doubling the size of your database is going to actually get you pretty

[00:26:04] **Adam:** good mileage buys you the time to scale horizontally.

[00:26:07] **Adam:** Yep. Yep.

[00:26:09] **Tim:** And that has been the strategy in the past. I'm not been happy with that because. It just feels like a brute force method that it just really should be something more elegant to attack that.

[00:26:24] **Adam:** Like Ben said, that's kind of outside my skill set. I would love to have that skill someday, but for right now it's outside, um, but the things that are pinging in my brain here, there's like, um, eventual consistency databases.

[00:26:38] **Adam:** So I don't know. Any names of them off the top of my head, but I want to say Mongo might have this model. And

[00:26:46] **Tim:** that's why I'm also looking at Cockroach right now because, uh, Cockroach, you have to have at least three nodes in order to even run one. Um, I think you can actually do two, but, but three is, is...

[00:26:57] **Tim:** That's pretty much what you have to do and it reaches a consensus. It's ACID, it uses normal SQL, it uses the, yeah, T SQL, it uses, um, uh, the Postgres wire protocol. So, I mean, it's, it's pretty freaking awesome, but it's also pretty freaking new. Um, so, it's just something I keep, keep an eye on because I, my, my dream would just be to have, You know, cloud based CockroachDB centers all around the globe, all of them running, all of them talking to each other, and it doesn't matter if one goes down.

[00:27:31] **Tim:** It's the chaos monkey thing. I want to be able to just totally nuke North America, nuke North America, and everything just

[00:27:37] **Adam:** keeps running. The cockroaches survive. The cockroaches survive. So I'm gonna, I'm gonna pull up Ben Nadell here, and instead of Rich Hickey, I'm going to... Uh, point to the guy that I point to often, which is, uh, Dan McKinley.

[00:27:50] **Adam:** Uh, he has a presentation that he's given, uh, the, and it has its own website. It's called BoringTechnology. club. And one of the concepts in this, uh, presentation is to, you, I mean, it's, it's what's in the name boring technology, use boring technology. And what he says is like, you, you kind of, the more. new, innovative, exciting technology that you use in an application, the harder it's going to be to keep it all going long term.

[00:28:18] **Adam:** So he from this perspective of you have like a certain number of innovation tokens in a project that you can use. And so if you pick, uh, you know, a brand new database, well, maybe then nothing else should be, you know, you should be using PHP and that's it and notepad and, um, uh, you know, or, or something like that.

[00:28:39] **Adam:** Right. So like the more out there you go on one thing, the more boring everything else should be. If I

[00:28:47] **Ben:** can, if I can just piggyback on what you're saying, just go on a tangent for two seconds.

[00:28:52] **Adam:** Go! Cause I'm getting more buzzwords. Run! We gotta get some synergy. Symmetry? This is

[00:28:56] **Ben:** point of mind for me. I wrote a post the other day called Enterprise is Not a Dirty Word.

[00:29:02] **Ben:** And what that stems from is listening to a lot of podcasts, especially around this time when I think some sort of state of the JavaScript or state of the GitHub or some survey just came out. Yeah. And, and what you hear often is that, oh, you know, this. Technology XYZ, it's losing popularity, but it's still used very heavily in the enterprise as if, as if like that's where technology goes to die.

[00:29:28] **Ben:** And I, the, the, the issue I take with that is to Adam's point, boring technology allows you to build solid products and to say that something is used heavily in the enterprise to me. It's a very dependable piece of software. It's not going anywhere. Because you know who's not using it? If it's not dependable?

[00:29:47] **Ben:** Enterprise. They're spending, you know, hundreds of thousands of dollars, millions of dollars a year on infrastructure, on software licensing. Like, it's, it's gotta be useful if they're using it. And I just... I

[00:29:58] **Adam:** challenge

[00:29:58] **Tim:** that assertion. So I, I think a lot of times they're, they're tied into it because they've been using it and the cost of redoing it is too high.

[00:30:07] **Tim:** So it's, it's just, it's the throw money at the problem, right? It's like, yeah, I'm sure we got to buy all these licenses, but you know what? It works. Uh, we really don't want to redo it. It, it, maybe it could be marginally better if we rewrote it in something different, newer, but we're not going to. So

[00:30:23] **Adam:** I'm sure the truth is somewhere in the middle there.

[00:30:26] **Ben:** I would argue that the throwing money at it is, is in a sense, voting on the things that are important to work on, that emphasizing the technology itself, there's no return on investment there, whereas having something that's trusted, it might not be the best, but it's dependable, allows the teams to focus on building the products, delivering to customers, solving customer needs as opposed to solving infrastructure

[00:30:56] **Adam:** needs.

[00:30:56] **Adam:** Yeah, the newer and more untested the product, the technology is, the more you're going to be dealing with the quirks of the technology and potential bugs, and less you'll be able to focus on your product.

[00:31:11] **Carol:** You're going to be solving those core product issues instead of

[00:31:14] **Adam:** your own.

[00:31:16] **Ben:** Now, I will caveat heavily to say that part of my emotions here are the fact that I use a lot of technologies that people keep saying, Oh, well that's still popular in the enterprise.

[00:31:25] **Ben:** Yeah.

[00:31:26] **Tim:** Right. Yeah. And I think another part of scaling besides what I was talking about, the global scaling, it is. You know, initially, how I approach software is you have a very small team that builds a prototype, sometimes one person, a lot of times I'm the only person building a prototype, hand it off to someone else, it's a small team of maybe two, three people, they take it to the MVP, um, but then now it becomes, you know, a money maker, and you go into maintenance and adding new features.

[00:32:00] **Tim:** Scaling the ability to, to maintain that code, to build that code, to extend that code. That's, I think, what I was talking about before is more sort of like the, the technology, hardware, um, you know, underlying design, database sort of things. Writing the code in such a way that it can be scaled to address future concerns is also a challenge because I only know how to write code the way I like.

[00:32:28] **Tim:** Right? Not everyone likes the way I write code. So, how do you guys address that of building a project with the idea that eventually this is going to become a staple of the company that is going to have to be built, maintained, and improved upon over the

[00:32:46] **Adam:** years? I'd say code, like the person who will be maintaining it after you.

[00:32:53] **Adam:** Knows where you sleep and has a murderous tendency, right? Like, honestly, like code for readability and for just like cleanliness, easy to maintain, uh, you know, comment well and, and try to abstract things in a way that makes sense.

[00:33:16] **Carol:** And so someone can come behind you and then grow that based off what you've built.

[00:33:21] **Carol:** And I think it's also important to have a well balanced team. Like, it's really hard to think about scaling, like Adam and Ben both said, when you don't know what is out there, when you don't know what you're supposed to be doing. So if you are, you know, at a point where you've now made this product go out and it's working, then you should invest in people that know those skills that can help you then scale it.

[00:33:46] **Ben:** Also, if you can create, if you understand your own limitations in, in terms of what you understand about technology. If you can build layers of abstraction that can potentially allow you to swap things out in the future, then you can sort of hedge against poor decisions. For example, let's say you needed to do something where you were going to process messages.

[00:34:13] **Ben:** Everyone who's experienced would be like, Oh, we just, then you're going to use some sort of message queue. But if you're just, if you're just a person and you're on your local machine and you're building a data driven application, you can say, well, yeah, but I don't want to have both a database and a message queue set up.

[00:34:32] **Ben:** Cause then like, do I have to have RabbitMQ or something? AMPQ running locally? Do I have to use Amazon SQS or something? So you can say, well, you know what, for the MVP, I'm just going to use a data table. That's my messaging system, and as long as I have an API layer around it, then later I can switch that out with something that's more robust and battle tested, and I'm not going to have to have lots of like crazy transactional lock in or something, but I understand databases, I don't understand message keys very well, but I can hedge against that and build it in such a way that theoretically I could swap it out later when it proves to be necessary.

[00:35:08] **Ben:** That

[00:35:08] **Adam:** makes sense.

[00:35:11] **Tim:** Yeah, I mean, and that's just sort of basic object oriented programming, right? I mean, looking at... Things from building functions that do specific things that you can later refactor those functions to do different things or extend them. Am I wrong?

[00:35:28] **Ben:** I think it's the idea, right? I mean, look, I don't really know that much about object oriented programming.

[00:35:34] **Ben:** I, I told myself. This is, this is like, uh, what do they call it in the hype cycle? I don't know what the peak of the hype cycle is. The

[00:35:42] **Adam:** peak of disillusionment? It was the trough of

[00:35:44] **Ben:** disillusionment. I, years ago, I didn't know anything about object oriented programming. I told myself if I just continue to work hard and eat my vegetables, I would one day understand object oriented programming.

[00:36:00] **Ben:** And you know, this was, this was kind of around the time Malcolm Gladwell came out with, um, what was it? The Blink. Outliers. Outliers. And there was all this stuff about like, oh, you got to put in your 10, 000 hours. And I was like, Oh, I'll just put in my 10, 000 hours and I'm going to emerge on the other end.

[00:36:15] **Ben:** This object oriented programming master. And, uh, you know, 15 years later, I can't object oriented program. Um, I'm still mostly just writing procedural code and handwriting SQL statements. It's, uh, I'm, I don't know. So I forget where I was going with that other than to say that I don't know that much about object oriented programming, other than you're creating an API and you're passing messages.

[00:36:43] **Ben:** It's all about implementation detail, hiding,

[00:36:46] **Adam:** and... Yeah. I feel like I struggled with it for a really long time, and then when I finally got a framework that clicked well with the way my brain works, uh, so we use a, an MVC framework, so it's called Framework One, and the way that you organize your views and your controllers and your services...

[00:37:06] **Adam:** works well for my brain, and it helps me separate out, this is my view logic, this is my service logic, and this is sort of a layer that connects the two, and, and this is where session variables live, and that sort of thing. And I don't know if that technically makes what I've been doing, object oriented programming, but I feel like it's well organized code.

[00:37:26] **Adam:** And that is good enough for me. That's how I feel.

[00:37:31] **Tim:** Yeah, I think well organized code is probably better. I mean, object oriented is just the methodology. It's the one I brought up because that's the one I use. Yeah, if it's well organized, then you can scale it. You're not... Everything that is running each function has its own purpose.

[00:37:50] **Tim:** And you're not doing too many things in one function. And so, it's just a matter of if you want to scale a team, you know, they're going to work on...

[00:38:11] **Ben:** I feel like one of the problems that we've had in our software, when I say we, I mean like the software I work on, is that we've had too much coupling too far down in the control flow of the application. That there were things that we coded to happen at the same time, and I always feel like that should have happened higher up in the application.

[00:38:39] **Ben:** And then the things down lower should have been much lower. More loosely coupled or completely decoupled from each other. Um, cause when you, when I got into programming, the whole idea of anything being asynchronous or eventually consistent, you know, even to this day, I'm still trying to wrap my head around what that means and what that.

[00:38:58] **Ben:** That implies for an application. So everything had to happen in lockstep, like you did this and it called an API and it sent an email and like all of those things had to happen or the system would explode. Like I didn't have any way to compensate for something like that. But I think a big part of scaling is embracing this idea that the world is just asynchronous and things all over the place are eventually consistent.

[00:39:23] **Ben:** Just because a user signs up in your system and they have to get a welcome email, like those don't have to be right next to each other in the code for that to, for that to be consistent, like those can be completely decoupled and you can imagine a world where an email has to get re sent or doesn't get sent at all for whatever reasons and that was, that's, that's still something I'm trying to understand how to both retrofit into the existing application, but then to also.

[00:39:51] **Ben:** Think about new applications going forward.

[00:39:54] **Tim:** And is that where messaging queues are helpful?

[00:39:57] **Ben:** I think so. And in, in, in some, in some

[00:39:59] **Adam:** ways. Yeah, that's one approach I was looking for. I feel like the last time GitHub went down. They had, on their status page, a list of like, um, these are the number of errored, you know, Git requests in the last, or over time, right, and, uh, how many, um, asynchronous of this type of operation we are behind, right, the requests have been queuing or they're sitting in the work queue sort of thing, um, and it's not on their status page right now, but I was, that is what came to mind when you were talking about, you know, separating the welcome email from the signup.

[00:40:37] **Adam:** Process. Well, GitHub's

[00:40:39] **Ben:** such an interesting example for me because GitHub works really, really well. 99.99% of the time. Yeah. But every now and then you'll go to create a pr mm-hmm. , and it'll refresh the page and it'll just give you a 4 0 4 that your PR can't be found and like the really angry unicorn.

[00:40:58] **Ben:** Yeah. Yeah. And, you know, looping back to Tim's discussion about Redis and writing to the cash and then reading, and all of a sudden the, the read's not there. It's not there. Yeah. I mean, I don't know what's happening in GitHub, obviously, but something is, something is asynchronous, or something is eventually consistent, and you, you just happened to hit a read replica that didn't have your PR replicate to it yet, and it's 404, and at some point they just say, that's a calculated risk, that that's going to happen, you know, one out of every million requests, and the user's going to refresh, and life goes

[00:41:29] **Tim:** on.

[00:41:30] **Tim:** Yeah,

[00:41:32] **Adam:** I always... I am amused when I get the like, okay, the page timed out sort of thing from, from GitHub. And it was literally like one and a half seconds, two seconds. And I'm like, you're, you're operating at another level from me, right? Like we have timeouts too, but ours are like 60 seconds or, or for certain things like 10 minutes.

[00:41:52] **Adam:** Um, well, I'm talking, you know, these are big things, like whole database table synchronizations across things. But, uh, but still like to, to detect that, uh, that I couldn't handle. You know, whatever, loading the page, connect to Redis, whatever. And I gave it two seconds and that was not good enough. And so I'm going to return to the user.

[00:42:10] **Adam:** Like, good for them. That's, that's awesome. Great user experience on, for me. Uh, but. It's just, uh, I, I can't, uh, I'm jealous to, to be able to operate at that, at that level. There was a,

[00:42:28] **Ben:** an, I was listening to an interview a couple of years ago. I want to say it was with a developer from the New York Times, but I don't know if that's true.

[00:42:37] **Ben:** And they were talking about something that was just very interesting in terms of people thinking on a different scale. And they had, I forget what they called it, it was like a blocking request budget. When a request comes into the server, they have a budget for the number of blocking requests that processing that response can take before they can serve data up to the user.

[00:42:59] **Ben:** And that if you're going to exceed that, that can't be part of the parent request. That has to be a subsequent request that the browser makes back to the server to get data because otherwise they were finding that they just, they couldn't manage. Performance over time, unless they had some number they could point to and be like, Oh, you know, you've exceeded your blocking request budget.

[00:43:19] **Ben:** That can't be part of this parent request.

[00:43:22] **Adam:** And was this like enforced in like code review or? I don't know. It may have been tribal. Yeah. Who knows? Okay. It's interesting. Just all the

[00:43:32] **Ben:** different ways people think about putting software together. It's so fascinating.

[00:43:36] **Tim:** Yeah. Yeah, it is. It's and there's so many answers.

[00:43:41] **Tim:** It just kind of leaves you, you know, wondering which was the right

[00:43:44] **Adam:** one, right? None of us know.

[00:43:45] **Tim:** We just try. I think we've been talking about this almost an hour and, uh, no one's given me an answer yet, guys. Well,

[00:43:51] **Adam:** so maybe it's a good time to pivot then. So when you, when you brought up the topic of scaling, I thought this was going to be a sort of a different discussion and I...

[00:43:58] **Adam:** I'm curious if you would like to have some, uh, maybe sample scaling stories. Although, like I said, we haven't had that geographic scaling issue even across, like, availability zones on, uh, Amazon or Regions. Is that what they call them? I don't remember. Um, but a technical scaling issue, like computer couldn't keep up or server couldn't keep up sort of thing.

[00:44:19] **Adam:** Um, I mean, I have a story in mind that I wouldn't mind telling and we can, if you guys want to go that way, we can go that way or we can not. Sure. Okay. Yeah. I mean, I've got stories too where I've solved scaling in the past, but, you know, it's. And I think this one in particular, I feel like is a good example of not prematurely, not prematurely optimizing and then dealing with it well when we got there.

[00:44:46] **Adam:** So. Um, we have a, our product has a module that is very heavily used for marketing and it sends a lot of email. Um, and the, it was originally like the MVP was made on ColdFusion and the, uh, and it was not an enterprise license. It was a standard license, which means that all mail was, I think that the mailer was single threaded if I'm not mistaken.

[00:45:12] **Adam:** Um, and so. Ultimately what that meant was it could send something like, I don't know, 3, 000, 4, 000 emails an hour, something like that, 4, 500 emails an hour, which sounds like a lot. But we, some of our customers are large and they want to send an email to say 300, 000 people and they might want to send more than one of those in a day.

[00:45:37] **Adam:** Um, and I promise this is not spam. This is actually like legitimate email people have signed up for type thing. You say that. We're not judging. Uh, but, uh, you know, so, it's one thing to be, to take a while to send out an email, but when, when the customer clicks send on an email, they're expecting, I'm sending an email to 300, 000 people and I want it to go and I want it to go now.

[00:46:01] **Adam:** Like, I don't want it to take three days to send my message. Um, and so that became a problem for us relatively quickly after this email module started to take off. And I forget what the middle step was. But where we have ended up, so originally we, we, um, we wrote database records to a queue table, uh, and they were, they, that table contained the rendered body, text and HTML bodies of the emails, uh, rendering was sort of a separate phase, and then when it was time to send, The theory was they would all be rendered in advance, and then we would just read a row, send the email, update it to mark it as sent, and move on to the next one.

[00:46:44] **Adam:** And that's what we were doing with the one that could go 4, 500 an hour or whatever. And obviously that wasn't going to keep up. So where we have since ended up is we still have that same table, but now, um, we write the row to that table and the text and HTML bodies are blank and it sends an Amazon SNS message, uh, that has some, some context information you're rendering for this customer.

[00:47:11] **Adam:** This is the message ID, um, that might be it, uh, whatever, a couple of other details. And that SNS message gets picked up by a Lambda, which will go and write empty files onto S3 for each recipient of that message. And then the file name indicates things like Uh, the customer, and the message ID, and the recipient ID, and then there's an S3 trigger that, uh, triggers another lambda, uh, function that, uh, will do the rendering, and write all of the rendered content, the HTML content, and the text body, and the subject, which can be dynamic, to that same file, and then it just sits there, in a separate S3 bucket.

[00:48:00] **Adam:** And then when it's time to send, we have a separate, uh, I don't know what you would call it. It's just a micro server, um, it's running on, uh, ECS, Elastic Container Service, is Fargate. Um, it's a Node. js app and, um, it uses the Mailgun API to send mail. And we have found that we can send email so fast that we get blocked by Mailgun using that service.

[00:48:30] **Adam:** So we had to write in, uh, what we call a governor. And so we have a throttle limit. Yeah, so we, we have a limit that we set. We want to send no more than, say, 6, 000 a minute, um, and we use, uh, multiple threads to do the sending, right? We do, here's a batch of 1, 000, send those to any given Lambda function, and the function runs, and it says, okay, I'm going to send those 1, 000, and then it says, okay, well, I've only been running for 8 seconds, and I know a Lambda thread can go for 3 minutes, or whatever this was.

[00:49:00] **Adam:** I think they can run longer now, but at the time. Um, and so it would go, okay, I have time to do more. So it would check in back with, uh, the orchestrator of this whole thing, um, and say, okay, I can do more work if you want me to. And, and they would get another batch and go send another thousand messages and keep looping.

[00:49:15] **Adam:** And then that, the orchestrator guy, uh, has to keep track of the per minute max, right? That's 6, 000 or whatever it's going to be. Um, and. We're doing math with like standard deviations to decide, okay, yes, we've got threads that can run and they have the headroom to send more right now, but, uh, are we going, are we in danger of hitting our limit if we, uh, if we do send more?

[00:49:40] **Adam:** So it'll back off and send less or send none depending on, uh, how much is left in this, what we call a calendar minute. Um, and yeah, and it, it's, uh, it was interesting. It's, it was, One of those scenarios where we have a huge problem, right? The customers are pissed at us because we're not sending email fast enough.

[00:50:02] **Adam:** And so we hunkered down, uh, pre pandemic in a, uh, in a hotel. And we're like, okay, block out all distractions, no email, no client meetings, just got the team together and said, fix this. Figure it out. Yep. And, uh, it was fun and exciting and probably not the healthiest thing to do. You know, like working 18 plus hour days on this problem, but it was exciting technology for us at the time.

[00:50:32] **Adam:** We hadn't, uh, hadn't done much with Lambda and containers and stuff, so. So that's

[00:50:37] **Tim:** an example of, you know. Scaling

[00:50:39] **Adam:** when need arises. Yes, exactly.

[00:50:41] **Carol:** How did you come up with the solution? Is it something you guys knew about? Did you bring someone in to help advise? What, like, what was that piece?

[00:50:51] **Adam:** We were familiar with what the technology was capable of, like using lambda functions and uh, yeah, I mean it was kind of uh, this is the problem that we have and Looking over at that solution over there, they, this is the, what they advertise as a possible fix for that type of problem.

[00:51:10] **Adam:** And so what, what's missing in the middle? What are the puzzle pieces we need to figure out? And we would play with one or two, you know, kind of like your, um, pair planning. Yeah. Uh, come up with a couple of ideas, talk to each other about, um, uh, and decide which way is probably the best to go do a quick proof of concept, uh, and see if it works out for us and then go with the one that works best.

[00:51:33] **Adam:** Do you have

[00:51:34] **Tim:** any idea what the upper limit of that solution would be? Like, when would be the next time you'd have to redo it? That's a good

[00:51:39] **Adam:** question. Um, so, the answer is... Probably not anything reasonable. I think the next time that we would have to change the technology would be, uh, for other problems other than that.

[00:51:52] **Adam:** So right now, like I said, we're, we are limiting ourselves to a few thousand per calendar minute. Uh, and that is we, we do that by having worker lambdas that the, the, we call it a conductor. Like it's conducting an orchestra of email, um, so the conductor is dealing with these four workers, um, and, or up to four workers, and in theory we could go up to 20 or 100, not, I guess not 100, right?

[00:52:21] **Adam:** Isn't Lambda Year Limited like 100 concurrent executions, or is it 1, 000? I think it might be 1, 000. It might be 1, 000. Either way, it's a ridiculous amount, um, and so we could, in theory, turn up our per minute max and turn up our number of allowable workers. And it'll just, every, so it's on a timer, it will go and say, okay, um, do I need to send more this minute or, or can I send more this minute in terms of our per minute max?

[00:52:49] **Adam:** And uh, have I reached the number of maximum workers? And if both of those are in positive direction, then it'll spin up a new worker and say, here's your batch.

[00:52:57] **Ben:** Well, how do you, when you talk about having to put a governor on how fast you're sending emails because you start getting blocked by.

[00:53:06] **Adam:** It wasn't by spam filters, it was by our mail provider.

[00:53:09] **Adam:** So we're using Mailgun, but before that it was, we were using, it doesn't matter. Uh, and, and so we're sending email over an API request instead of doing SMTP, uh, and their API limits the number of API requests that you can make per minute, I guess it is.

[00:53:28] **Ben:** Interesting. I wonder if you could, I don't know if this would be a bad solution, but you could almost do Shard API keys based on some subset of clients.

[00:53:40] **Ben:** Like if you have, if like Harvard, for example, sends out bajillion emails, just give them their own API key.

[00:53:48] **Carol:** That's like where my head was going when he was talking about his limits. I was like, I wonder if he could work around

[00:53:53] **Adam:** that. There are a bunch of ways that would be possible to work around that. One of the problems with our, that we would run into is that when you're sending an email, you're sending it from a specific domain and that domain has to be attached to the account that's sending it, like our Mailgun account.

[00:54:09] **Adam:** And I don't know if you can attach multiple, you probably can have multiple Mailgun accounts. is allowed to send on behalf of a certain domain. Um, and so that's one possibility. Another is, uh, Melgun has a different approach to, uh, this problem, which is that they support, you can make one API request and say, okay, here's.

[00:54:36] **Adam:** 10,000 people I want you to send this message to, and you send them like a message template and a separate, uh, list of, okay. For this email address, these are the values that I want you to put in for the token. So they do the rendering for you? Mm-hmm. like a mail merge? Is that Yeah. Yeah. Very much like a mail merge.

[00:54:50] **Adam:** We use SendGrid. Syngrid works pretty much the same way. And, and if we didn't already have the infrastructure to do all of the rendering, on our side in advance, ready to go before we got to Mailgun, then we probably would have used that, but we already had it on our side, and so it made more sense to just not rewrite that part of our infrastructure, uh, and go this way.

[00:55:14] **Carol:** So you still have a couple options to scale this project as is.

[00:55:18] **Adam:** Yeah, and the first thing that I think we would do is throw money at it, right? So, increase our account level so that we can get a higher API limit sort of thing. So, what does your

[00:55:28] **Ben:** local development look like for something like this? Because this is the, the, I think the flip side of a scaling conversation is always, you know, what does it look like in production?

[00:55:39] **Ben:** It has all the bells and whistles, but then when I boot up my MacBook to start doing some coding, do I also have to have

[00:55:46] **Adam:** an Amazon?

[00:55:47] **Ben:** Key and SQS's and Amda's setup or you have to start running something called like local stack Which I think kind of mocks out a lot of the Amazon APIs, but

[00:55:59] **Adam:** yeah, I don't know you found that the primary problem that I think people Building these massively parallel systems have, and that is local value does rely on the ointment.

[00:56:12] **Adam:** uh, yes. So there is another, I think you're right. And then another one of those I think is called Sam Local, I think, and Sam is an acronym that I don't remember what it, oh, that might be what I'm thinking of. And uh, the idea is to basically like give you a container that you can run locally. So you have like a local.

[00:56:32] **Adam:** Uh, Lambda container, and you can run functions inside of that, and they can have mock things that they can work with to say, okay, I sent the email, or okay, I wrote the file to S3, whatever it's going to be. Um.

[00:56:43] **Ben:** And I think that's a community driven project. I don't think that's like the Amazon team. Yeah,

[00:56:48] **Adam:** I'm not sure.

[00:56:49] **Adam:** We're not using it. So what we do is, uh, very carefully test in QA. Yeah. Uh, so we have a separate, uh, Set of S3 buckets and a separate, um, Lambda set of Lambda functions. And we very, very carefully and thoroughly sanitize email addresses because, uh, before the podcast began, uh, a major fail I had was I accidentally sent from QA to real people like.

[00:57:22] **Adam:** Let's say, on the order of thousands of emails. With links to the QA environment. After you

[00:57:28] **Tim:** said you swear

[00:57:28] **Adam:** it's not spam. Oh yeah, it was spam that time. But, uh, it was, testing is just poorly sanitized. It was after, you know, it, it. One of the things that you do in order to test well is you, uh, occasionally.

[00:57:44] **Adam:** Copy your production database down to QA so that you have real data to play with that is shaped the same way as production data, that sort of thing. And we just hadn't, uh, hit max tier on our sanitization game at that point. You know, there were email addresses buried here and there, and so I... I

[00:58:07] **Tim:** think Ben hit on it though, the challenge that developing locally in a way that simulates the problem of scale is not easy.

[00:58:15] **Tim:** It's not. You wind up mocking a bunch of things, which is fine, but yeah, I mean, I guess it's why a lot of times the things you find out are really only only in

[00:58:27] **Adam:** production. Yeah, have good logs.

[00:58:30] **Carol:** This is a silly one, but this is from when Tim and I worked together. We used to run into the issue of what happens when you're on HTTPS versus HTTP.

[00:58:39] **Carol:** I mean, our productions are all on secure and then all of a sudden I have things that aren't working in production that work fine in local because there is no HTTP. There's no, I don't have any cert issues on my local that I have to account for.

[00:58:54] **Adam:** So we actually recently solved that problem for ourselves for the second time.

[00:58:59] **Adam:** The first time we were using, uh, Once is never enough, Adam. Well, we were using a service, uh, called localhost. tools. And so, basically, there's a lot of these things out there where it's called, it's kind of dynamic DNS, but whatever you point it at points back to localhost. So you get a public facing hostname that, and it uses a real TLD so that, you know, like Chrome doesn't say, oh, you can't do this because you're running on localhost.

[00:59:27] **Adam:** Um, and They have a wildcard SSL certificate, and so you run, like, you know, foo. localhost. tools, and it points to your local machine, and you've got an Apache header set up to respond to foo. localhost. tools, and you can run that on SSL, and that's fine. And then, for whatever reason, I think localhost. tools shut down.

[00:59:48] **Adam:** They're not doing it anymore. So we have, we bought another domain, and we just do sort of the same thing, uh, on our own. I

[00:59:55] **Tim:** mean, now that Let's Encrypt is, is, you can do SSL certs for

[00:59:58] **Adam:** free, that, that's... Yeah, the hard part is just setting something up to be able to do it locally on what looks like a, a, uh, publicly available TLD.

[01:00:09] **Adam:** So that other things that are looking at that, treat it as if it's public.

[01:00:13] **Carol:** Yeah, the same thing, yep.

[01:00:14] **Adam:** The

[01:00:15] **Tim:** scaling thing that I've run into, again, it's where this need creates, you know, we have a very highly transactional database, very, um, it's not flat at all, but doing reporting many times can be the thing that can cause you issues.

[01:00:31] **Tim:** So, I mean. And this is probably a pretty common attack pattern for it to address the issue is to basically we don't need all the data at the second it's there typically reports are going to be after the we're dealing with financial transactions so you're only looking in the past it doesn't need to be up to the millisecond so Correct.

[01:00:51] **Tim:** So taking the data that we have, shipping it off, sanitizing it, shipping it off to a PostgresSQL database and RDS up in Amazon, flattening the entire view so that you don't have to do any joins to pull any data, and then only doing your reads for reporting off of that data source versus going to your transactional database, which is doing all the work, which slows things down.

[01:01:14] **Tim:** So that, I wouldn't even call that scaling. I would just say that's kind of the way you should deal with, you know, Have, have different platforms for one, for reading, one for writing, uh, just, that's just the way you should do things. But it's all

[01:01:27] **Ben:** about, it's all about the skillset that you have available and the, and the money you have.

[01:01:33] **Ben:** I mean, if you're, if you're one person and you're thinking about, how do I present data to somebody? I mean, I imagine that for most people, the default reaction isn't to create some sort of,

[01:01:51] **Ben:** RedshiftDataLake in Amazon and doing entity transform. What is it? ETL? I don't even know what all the acronyms stand for, but it's...

[01:01:59] **Adam:** Extract, transform, and load.

[01:02:01] **Ben:** Yeah. It's like my reaction to that is, is there just an additional index I can throw on this table? It'll make it a little faster to get the data.

[01:02:08] **Ben:** Cause like that's, that's the tools I know how to use. And that's the money I have to throw at it. It's so tough. I'm not saying that my way is better at all. I'm saying like...

[01:02:20] **Tim:** No, I'm pretty sure your way's worse.

[01:02:29] **Tim:** Yeah, I, I, yeah, I, it's funny because that's immediately where my head went. It's like, I, I, but that's only because I've come from a world where the pain of trying to run reports on your actively being updated database was so painful. Table locks, yeah. I'm like, I am never doing

[01:02:46] **Adam:** that again. It is terrible.

[01:02:47] **Adam:** I'm like, go kill,

[01:02:48] **Carol:** go kill, go kill.

[01:02:49] **Ben:** If you're lucky you get a read replica. But again, I'm not saying that it's better. I'm saying, I'm saying that I think what is so challenging about thinking about scale is that you, you don't scale an application independently of your business. Your application and your business sort of have to scale in lockstep because the complexities that go into scaling the application necessitate a wider array of

[01:03:14] **Adam:** skill sets.

[01:03:15] **Adam:** Yeah. I

[01:03:17] **Carol:** think you said it, Tim, too. You were like, I know to do this because I've had the pain of dealing with it. And that's where it goes with getting the team that Is set to do that.

[01:03:31] **Tim:** Well, the team was me, I know , so, but I had the skills. Yeah. So fortunately, but, uh, yeah, it, it's challenge. It's, I, I, I don't think, I would like to think I could eventually be the person who could like, foresee the problems, but I, you know, in software you can't even plan nine months ahead.

[01:03:50] **Tim:** Mm-hmm. trying to plan anything nine months ahead is just, is a fool's folly because you're, things are gonna change. Right. Business. Needs are going to change, markets are going to change, technology is going to change, your, your knowledge is going to change. So, you know, yeah, I'm going to try to do my best to know, to deal with what I know could be a problem based off the business that I have now, but I don't know my business is going to be like two years from now, so I can't really build for that.

[01:04:20] **Carol:** I don't think you should let that stress you out or stop you from moving forward with things either.

[01:04:25] **Tim:** Oh, I never did. Like,

[01:04:28] **Carol:** if you have a good idea, don't let being scared to scale stop you from moving forward with something. So if someone's starting something new right now, don't be so scared that you can't grow it to not move forward with it.

[01:04:41] **Carol:** I'm

[01:04:41] **Tim:** just looking for validation that it's okay to use CockroachDB. Use it. Use it.

[01:04:45] **Carol:** I mean, I feel like if you nuke the U. S., then your database is still going to be there, right? Isn't that what you said? Europe still has your data. You're good.

[01:04:52] **Adam:** Yeah, that's it. I'm good. Just spend your innovation tokens on that.

[01:04:56] **Ben:** There you go. As long as you can get a dump of your data, you're not, you're not buying, you're not, you know, nothing's set

[01:05:03] **Adam:** in stone. You're not locked in, yeah. Yeah, if it's relational

[01:05:05] **Ben:** database, then you can move it. Exactly.

[01:05:10] **Adam:** All right, before we wrap things up, uh, let's tell people about our Patreon. Uh, we, we have a Patreon, uh, and it is because of, uh, the generous support of our patrons on Patreon that we don't have to do disingenuous sponsor ads and tell you how much Tim loves his, uh, metal bikini, avatar, and we, we're very thankful for the people that support us on Patreon because it helps us so much.

[01:05:38] **Adam:** Keep the show running and cover the costs and, uh, just makes us excited to come back and keep going. And, of course, I just want to mention anybody that supports us there gets our Discord invite and at certain levels we have access to all of our new episodes as soon as they're done being edited and notes being written and we have the after show like we were talking about.

[01:05:59] **Adam:** And at the very top level after show is lit. , last week's was awesome when we did some bike shedding. That was great. I was thinking, do you guys think, uh, we should publish like a special episode of the podcast? Just add it to our normal feed. It'll just be like last week's after show. Just show people Here's what you missing.

[01:06:16] **Adam:** What the after show? Yeah. This is what you're missing. This is what the after show is. Like this is what you would get. Maybe like

[01:06:20] **Tim:** little snippets of different after shows. Like the best of Right. So they can get a little taste. I like that idea. Okay. Yeah.

[01:06:26] **Adam:** I have

[01:06:27] **Carol:** something to add to it, but we'll save it for the

[01:06:28] **Tim:** after show.

[01:06:29] **Tim:** But I'll tell you who's enjoying the after show. Monte Chan, because he's a top patron. Monte

[01:06:33] **Carol:** Chan. If I meet him, buying him a beer.

[01:06:37] **Adam:** That's it. You legend, you. Absolutely. All right. So, uh, thanks everybody for listening. And don't forget to share the show with a friend because there's no better support than a word of mouth referral.

[01:06:49] **Adam:** Help the algorithms boost our signal by leaving us a review or rating on iTunes or wherever you get your podcasts. And if you think we've earned it, please consider supporting us on Patreon. Send us your topic suggestions on Twitter or Instagram at @WorkingCodePod. We'll catch you next week. And until then, your heart matters.

[01:07:33] **Tim:** Back up. I do it too. I don't notice

[01:07:34] **Adam:** it. I really,

[01:07:35] **Carol:** it's funny 'cause I, I notice my likes and whatevers like, like we're,

[01:07:40] **Adam:** we're all our worst critic. When I, when I edit the thing, I hear every single pause where I'm, um, trying to think of the next words. Yeah. You um, and

[01:07:50] **Tim:** I, I'll go and you Well, you know, I, yeah.

[01:07:53] **Tim:** I, I, I, I, I'll do that

[01:07:54] **Adam:** until I find the word I'm looking for a specific word.

[01:07:57] **Carol:** Yeah. We're just gonna, when you do that, we're just gonna start throwing out random words. There you go. Nothing associated to what you're talking

[01:08:03] **Adam:** about though. Okay. Alright. Well, we've been going for well over an hour now. We should, uh, switch over.

[01:08:08] **Carol:** Wow. 30 minute goal,

[01:08:10] **Adam:** huh? Yeah. Let's, uh, let's move over to the after show so that we can get Ben off to bed on time or close to on time. May I go pee first? Yeah, sure. While Carol is peeing, I'm going to tell everybody about our Patreon.

[01:08:26] **Carol:** I'll wait. That was just

[01:08:28] **Adam:** awkward. Alright. I'll cut that. Go ahead. Okay.

[01:08:31] **Adam:** Yeah.

[01:08:32] **Tim:** You're a grown woman. You never have to ask permission

[01:08:35] **Adam:** for that. Tim just walks away. You don't have to ask permission to do anything. Tim just leaves. Remember guys, your heart matters. I don't know if you'll be able to sing that. We can, we can, if it's bad, I'll just like use Tim's.
