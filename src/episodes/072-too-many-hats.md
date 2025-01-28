---
title: "072: Too Many Hats"
description: "The crew discusses a topic submitted by Mingo Hagen: Do developers wear too many hats, do they spread themselves too thin, and does the work suffer because of it?"
date: 2022-04-27
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/072-too-many-hats/id1544142288?i=1000558851632"></iframe>

Sponsors

- [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

This week on the show, the crew discusses a topic submitted by [Mingo Hagen][mingo-hagen]: _Do developers wear too many hats, do they spread themselves too thin, and does the work suffer because of it?_ There are clears benefits and drawbacks to wearing a lot of hats. Knowing a little bit about a lot of things can cut down on communication overhead and enable teams to move faster. But, without specialization, solutions will almost certainly be sub-optimal; and, "best practices" may not even be known to the engineer. Ideally, a team should consistent of both _generalists_ and _subject-matter experts_. This kind of balance creates a "healthy tension" that tempers perfectionism with pragmatism and keeps everyone moving forward at the right pace.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[mingo-hagen]: https://mingo.nl/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/072-too-many-hats.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** And when you run it a set of services with an open source mentality, we're just like anybody can jump in. And as long as the PR gets reviewed, code can just get committed to that.

[00:00:09] **Ben:** It just feels like weird ownership, boundaries.

[00:00:12] **Adam:** So Ben, have you ever, uh,

[00:00:14] **Ben:** if you ever worked with other humans,

## [00:00:19] Intro

[00:00:19] **Adam:** okay. Here we go. It is show number 72. And on today's show, we're going to talk about wearing too many hats. but first as usual, we're going to start with our triumphs and fails and it looks like it's my turn to go first. So I'm going to start us off with, you tell me, is the triumph or is it a fail?

## [00:00:53] Adam's Triumph

[00:00:53] **Adam:** I guess a brief story, a brief synopsis of what happened. I was working on a cloud microservice thing, I guess you could just say on the microservice and it wasn't doing what I wanted. it's a process that takes in some cases a really long time to run. And we were seeing when, when you're working with these things in the cloud, pretty much the only thing that you get to go on is the logs.

[00:01:15] **Adam:** So I'm trolling through the logs and. The more, I spent probably a day and a half to two days looking at this, just pulling my hair out, trying to figure out what's going on. And the more that I looked at it, the more I was feeling like every time I made one request, two requests were happening when you're like, when you look at the logs and you're like, this doesn't make sense.

[00:01:35] **Adam:** why are we getting two of these things?

[00:01:37] **Ben:** Classic BOGO.

[00:01:38] **Adam:** yeah. And so, I mean, long story short, I was right. how do I explain this? So we're using, the Java SDK to invoke a Lambda directly over a socket, not a web socket, but a socket connection and the default, socket timeout for a direct Lambda invocation is, 50 seconds on the Java.

[00:02:02] **Adam:** And we just didn't realize that when we like wired the service up in order to be able to execute our Lambdas, and I guess we hadn't run into it before, and it wasn't really a problem. Well, so when you've got a process that could run for like a half hour and it's doing big database queries, and then 50 seconds into it, you give up on waiting for a response and you retry it.

[00:02:22] **Adam:** then all of a sudden you start to run into deadlocks and extreme database CPU and memory consumption. And this was a really bad problem. Like I said, I worked on it for like two days and ultimately what it turned out to be was just increase the timeout. and so it would stop giving up and retrying.

[00:02:37] **Adam:** And, it was just so frustrating because it didn't even occur to me for that two days that I was working on it. Like I had this feeling, it feels like when I make one request, there are two running and I kept going, but that's. And it turns out it wasn't impossible. and I just, to me, it was like, if that's the way you feel, when you have a feeling that just, it doesn't seem right, but it feels like something, a particular weird things going on.

[00:03:04] **Adam:** There's a good chance that it is,

[00:03:06] **Tim:** Why was it timing out?

[00:03:07] **Adam:** it was, so the job was just taking longer than 50 seconds to execute. So it wasn't responding to the socket in time. And the Java SDK by default says it, well, if you haven't responded within 50 seconds, I'm going to give up that's the timeout. And then, it gives up, but it has a

[00:03:21] **Tim:** Number tree, number one at one minute.

[00:03:23] **Adam:** I don't ask me, man.

[00:03:24] **Adam:** I'm not a Java developer. the, but so it, by default is 50 seconds then by default it will retry I think, three times. and so it's not only sometimes was it trying twice, but sometimes it was trying three times. and yeah, it was just bad. So, but eventually we figured it out. and so here's where maybe it turns back toward a triumphal a little bit.

[00:03:46] **Adam:** I did fix it. And the fix was, sort of writing Java code, which I am not a fan of doing. I had to write a couple of lines of Java code, but I got copilot to do it for me.

[00:03:56] **Adam:** So yeah, it was, well, so yeah, get hub, copilot. the thing that drives me nuts about trying to use a Java SDK from a CFML application is that most of the Java libraries that I've tried to use in that fashion have poor documentation for somebody who isn't an everyday Java user. And so it's like, oh, you just need to pass it in one of these client configuration class instances. And it's like, but where is that client configuration class instance? how do I instantiate it? And what does it need? What are its arguments? Then I was able to figure it out, but. I did like VAR custom config equals in a new AWS dot and then copilot kicked in and it was like, oh, here, let me get you.

[00:04:37] **Adam:** I read the rest of your code around here. And it figured it out. And I just had to populate the one, the timeout parameter that I wanted to change. And it popped in and it was awesome.

[00:04:46] **Tim:** I need to get on this co-pilot thing.

[00:04:48] **Ben:** So did you ever end up finding the, some sort of a time-out entry in the logs?

[00:04:53] **Adam:** no, it wasn't. It, nothing in particular was actually timing out. It was just that the SDK said that's it. Time has run out for a response to come back. I'm going to retry.

[00:05:04] **Ben:** Gotcha. So the retries were eventually working. So the overall request and really fail quote

[00:05:10] **Adam:** right. It's possible that it was putting something out in like the system log or the application log or something that I just wasn't checking.

[00:05:17] **Adam:** I was concerning myself with the. Logs that I generate from within the microservice. Cause that's where it seemed like things were going wrong and it didn't even occur to me to look at the logs of the color. So.

[00:05:30] **Ben:** I'll tell you time-outs to me feel like black magic. I never know what a reasonable timeout is. And for example, I can ColdFusion. If you want to lock, put a, an exclusive lock around some code, you can give it a timeout, which is how long it'll say and wait for a little. And I feel like, these computers are doing millions of operations a second and the lowest time I, you can give it as a second.

[00:05:54] **Ben:** How has feel like they should not have to wait more than a second for anything that I'm doing inside this lock, but then, inevitably something like garbage collection happens and the thing freezes up, or I don't know, or like making API requests where you can give it a timeout for how long it should wait.

[00:06:10] **Ben:** I just never know what to pick. I always like arbitrarily pick five seconds and it's like, not based on anything at all. That's very frustrating.

[00:06:18] **Tim:** Based on how long do I think I want to wait?

[00:06:21] **Adam:** Well, I think that's not too far from the truth. I think in that situation, I would base it on what is a reasonable user experience at what point should we, at what point should we tell the user? Oh, okay, sorry. We waited. As long as we thought it was reasonable and it didn't get a response. So, try again or

[00:06:40] **Ben:** yeah.

[00:06:40] **Adam:** let us know or whatever, but.

[00:06:42] **Ben:** That's I think you're right. I think that's the key that comes down to it is how do you, what is the experience of the failed requests? Because if you look at the distribution of times for a response for an API call and your P 95 or something, right? Like 95% of all requests fall under this boundary is like 200 milliseconds.

[00:07:00] **Ben:** But then you get some long tail where it's the P 99 will be like seven seconds, something like that. I'm, I'm just making up numbers here. And so on one hand, you can think that I should just let it go. Like if most people are getting super snappy things, like why even have a timeout that's low.

[00:07:17] **Ben:** If the one that is seven seconds eventually returns anyway, like why bother kill it? But the why bother kill? It becomes, well, what if I kill it? And I can do a retry or, that maybe that's hits a different distributed note or something, or I give a better message to the user. And it's like, that's the thing that I never have ready to go is the better user except. it's like the timeout selection is not based on how can I handle this gracefully? it's more just like the, I gotta put a timeout in this call.

[00:07:41] **Tim:** I'm always wondering, should I do, try that, and I know it's going to take. But by the time the user retries, again, enough time would have passed and I'm cashing the Pryor because typically it's like, you're hitting a date about cashing the prior thing. So by time they retry in human time, it will have been cashed.

[00:07:58] **Tim:** And then when they do it, this time will be instant.

[00:08:00] **Ben:** yeah. Yeah. Well, in the, this has been a popular phrase. I've been hearing a lot in some of the client side caching technologies, this, like stale wall revalidate. And I think it's this idea that you're like, this request will always come from the cash if it's available, but it will implicitly trigger an asynchronous request to get the next value.

[00:08:20] **Ben:** So that the next time you make the request, it's up to date. I think sometimes that's in the context of more of a reactive application where you'll end up rendering the fresh data once it's there. So I don't know if that applies everywhere, but

[00:08:32] **Adam:** I don't know if you've heard of the new framework remix

[00:08:35] **Adam:** it's it's in your favorite

[00:08:36] **Ben:** that's the one, Kent C Dodds. Right. He's been hot on that.

[00:08:39] **Adam:** he, yeah. He's been

[00:08:40] **Ben:** He works for them

[00:08:41] **Adam:** pushing a lot. Yeah. He works for them now. It's from the people who created react router. but, I think that's sort of their default posture for a lot of their stuff.

[00:08:48] **Adam:** Is the stairwell revalidate approach I wanted to ask you. have you seen the big angry pink unicorn on GitHub?

[00:08:57] **Tim:** No.

[00:08:57] **Ben:** no.

[00:08:59] **Ben:** Oh, the angry one.

[00:09:00] **Adam:** yeah. Yeah. Yeah. So the it's their error page, right? you it's either that one or the Octocat falling down a ravine, like in a, Roadrunner cartoon. the unicorn always kind of surprises me how fast they return that to you.

[00:09:12] **Adam:** So it, like if they're having issues, which everybody does occasionally. and,I'll get a response in like, I don't know, one second, 700 millisecond, something like that. And it's like, Paige timed out waiting for response. And I'm like, but this is a normal response for my habit. Like you have a really high bar to clear if you're giving up that early.

[00:09:33] **Adam:** Like, I mean, I love it. I love that there that on top of it, and they provide such a great service that they can consider, like a one second way too long to wait and give up at that point. I think that's a really great experience for me the user of their application.

[00:09:46] **Tim:** Just go ahead and sit all your time, Austin. One second. Go

[00:09:49] **Adam:** yeah, if it works for GitHub, it's good enough for

[00:09:51] **Adam:** you.

[00:09:52] **Ben:** I think they have a status page somewhere that shows the latencies of a lot of their end points.

[00:09:58] **Adam:** pretty sure. It's status.github.com.

[00:10:00] **Ben:** Oh, maybe? The angry unicorn with grade. I it's one of those things like operational readiness. It just has like an umbrella term. I feel like it, it's not a very nuanced thing and the nuance is not the right word.

[00:10:14] **Ben:** It's like, there's not a lot of graduation in how good you are at it. It's like you're mediocre. And then the next step is like phenomenal. It's like, it feels like there's not people who are just

[00:10:23] **Ben:** like

[00:10:23] **Tim:** you invest in your investment starts to get into the millions you're like now you're phenomenal.

[00:10:28] **Ben:** It's just, I don't know. There's people who do it super, super, super well.

[00:10:32] **Adam:** I think that's going to tie in nicely with our topic today. So let's come back to that.

[00:10:36] **Ben:** definitely.

[00:10:38] **Adam:** I think that's enough about me. How about you, Tim? What do you got going on?

## [00:10:40] Tim's Fail

[00:10:40] **Tim:** Yeah. It's enough about you, Adam could hog on the show. So you were kind of ambiguous. If it was a triumph of fail. I have a failure, which I stole from Ben. Um,so, I've been working in store procedures for like for the first time. Maybe five years. I mean, I used to work in stored procedures all the time, building store procedures, debugging them.

[00:11:02] **Tim:** And then just because of changing roles and stuff and the type of product I was working on, it's like, I haven't really had to work in store procedures are, I mean, our PostGrest, database has zero store procedures are MySQL database has a few stored procedures. But been writing, nobody was like, it's a failure because I could not remember how to do basic things.

[00:11:23] **Tim:** I was like, how do you do an if statement, do I need a begin and an end block? I do remember there was something about that. And so I'm Googling and going to likeMSSQL, cause this is my, Microsoft SQL tutorials. And I feel like such a newb. Right. And I see like, okay, all right. I was just double-checking.

[00:11:38] **Tim:** and I, I probably wrote 15 store procedures today, and once I got going, it all started coming back to me, but it's like, I felt a real failure that, you know, that this skill that I was like, I felt six years ago, I was like really good at it. Just, I was no longer, good at because time has passed.

[00:11:55] **Tim:** And, your, your memory buffer pushes does garbage collection and pushes all that out of your head.

[00:11:59] **Adam:** Oh, yeah. I delete stuff from memory real fast.

[00:12:02] **Tim:** Yeah. Yeah. Because I do have a, I don't know if it's my saying, but I do say it a lot. It's like, I don't memorize anything. I can Google.

[00:12:09] **Adam:** Yup.

[00:12:10] **Tim:** So I don't try to keep that stuff in my head. So I guess maybe that's a triumph in the fact that it's like, I don't keep all that stuff in my head. I don't have to be a store procedure expert all my life, just when I need it.

[00:12:22] **Tim:** And once you start doing the muscle memory does come back pretty quickly. So I think it's a trial from that regard. So

[00:12:28] **Adam:** Okay, I'll give you that much. I was, I w you were describing all these things about your recent experience and I'm sitting here going, but what about this is at all ambiguous that it might be a triumph. It might be a failure to me. This just sounds like all fail.

[00:12:42] **Adam:**

[00:12:42] **Adam:** not a comment about you, particularly just, this particular

[00:12:45] **Adam:** thing.

[00:12:46] **Tim:** the fact that I cranked out 15 at a day tells you that I, and these weren't simple store procedures. It was just that I needed like three or four Google searches, you know how to do a common table expression. And I forgot about that. it's like, it's just syntax stuff. I knew I knew they were there.

[00:13:00] **Tim:** So

[00:13:01] **Ben:** why are you suddenly dropping into storage procedures? what's the constraint here.

[00:13:05] **Tim:** it's a constraint, it's just sort of the use case. So we have an event driven thing. So every day we're going to send out a ton of emails or, text messages to,

[00:13:15] **Ben:** This is about the payment stuff. You talked about

[00:13:17] **Tim:** yeah, this is for the, actually it was for the insurance side. So your policy is canceled. It's going to cancel if you don't pay now.

[00:13:23] **Tim:** And so this was, I didn't want to do just ad hoc queries on the bill of store procedure, and then just have my API call the store procedure. Take the data and put it in Jason. so that's the reason I'm doing it. It just made more sense to have it in there rather than just writing, ad hoc, SQL inside of, the code

[00:13:40] **Ben:** Interesting. Who was I talking to you or was it Adam? Cameron. Somebody was talking to. Not writing SQL as CF query, but like writing it as string so that you can test the

[00:13:50] **Tim:** because me and him, cause I do that. I do that as

[00:13:52] **Ben:** K can you do that with a stored procedure or is that not possible? The stored procedure?

[00:13:57] **Tim:** No, because I mean, you wouldn't be riding that inside, inside the app, right. You just be calling the store procedure, but you could, have call the store procedure with certain inputs and they always should result with certain outputs.

[00:14:09] **Tim:** You could do

[00:14:10] **Ben:** Got you. You could do like a playback of what it's supposed to. I got to go

[00:14:13] **Ben:** to.

[00:14:14] **Adam:** I still don't feel like I have ever run across a reason that store procedures were absolutely required other than by policy.

[00:14:24] **Ben:** Well, this, all this also sort of dovetails with the topic of the show too, because it used to be, I mean, I say used to be like, I've been around a long time, but there are, I'm sure there are places where the stored procedure is. Part of the reason you had to have started procedures is because that was the database administrator.

[00:14:38] **Ben:** I'm doing an air quotes, like the date, the DB admin was the one who wrote the stored procedures because regular programmers couldn't be

[00:14:45] **Adam:** we're not good enough. Yeah.

[00:14:46] **Adam:** Yeah.

[00:14:47] **Ben:** now everybody's wearing all the hats.

[00:14:49] **Adam:** Ah,

[00:14:50] **Tim:** they say that all the hats. So I ran into a weird thing and I still haven't figured out tomorrow. I'm going to take a crack at figuring out. So in the store procedure, I don't like having. The actual store procedure, where it's maybe doing a select statement, having any sort of hard coded, like numbers are values.

[00:15:06] **Tim:** So everything I want to be, at active or at, status is good or whatever. So I, I build all the variables and then, put them in the SQL statements, select them. And for some reason there was one field. The only thing different, the only thing I know about is I did, I had newly created an index on this one field.

[00:15:26] **Tim:** And if I, in the store procedure, if I used the variable, at, status active and ran it, it took, I don't know how long it took because I stopped it because it was taking like two minutes. I changed that into a hard coded zero and it was three seconds.

[00:15:45] **Tim:** Hmm.and I don't know, I don't know why it kind of blew up.

[00:15:48] **Tim:** I sat there just toggling back and forth going. This makes no sense. I have no clue why this makes a difference to do the query parser that it's a variable and these to take forever. So I'll dig into that tomorrow, but

[00:16:01] **Adam:** The performance of databases is a very arcane, profession sort of thing. Like it's black magic.

[00:16:10] **Tim:** yeah, because the only reason I even created the index is I ran the query, execute on it to show me. And I saw like 70% of the time because I didn't want everything else was coming back within like milliseconds. And this one query that was only slightly different. It was taking, three to four seconds.

[00:16:24] **Tim:** I'm like that's too long. So I tried to optimize it. It said, these fields were index. I threw the index on there and now it took longer if it was a, if it was a, a variable, but it didn't take longer. If it was a hard coded number.

[00:16:36] **Ben:** that's weird.

[00:16:37] **Adam:** So what you're talking about is magic numbers, right? So if you're reading a query or a that's the technical or whatever, idiomatic name for them, just a random integer or whatever appears in your code. It's like, but where did that come from?

[00:16:50] **Tim:** Right.

[00:16:50] **Tim:** I don't like looking at green going, if something equal, if this equals one, then do this. I'm like, well, what does one mean? What in the gimme, explain to me what that means. So I, yeah.

[00:17:00] **Adam:** Right. So by switching it to a variable, you can give that variable and expressive name and then reading the code.

[00:17:06] **Adam:** Makes perfect sense.

[00:17:07] **Adam:** Yup.

[00:17:07] **Tim:** It gives you context. Yep. So that's me. How much you been, hopefully you got a real triumph failure.

## [00:17:12] Ben's Triumph

[00:17:12] **Ben:** grimace. Uh,I'm going with a, yet to be determined. Cause I don't know if this is going to be a success or a failure in the long run.

[00:17:20] **Tim:** This is like a magic eight ball. So.

[00:17:24] **Ben:** So we've had this long standing problem at work where we generate PDFs on the server side using a ColdFusion technology. And if you're in a small. It works pretty well. And that's historically worked very well, but we have some customers who have these just Whoppers of projects, where they've got hundreds of things inside them that we need to output into a PDF.

[00:17:48] **Ben:** And, and trying to generate that PDF on the server side just will, it'll eat up all the memory or it'll just take forever. And then it usually gets terminated prematurely because of a deployment or something like that. it's really something that should have ultimately been split out into its own service, but it never was.

[00:18:04] **Ben:** And there's reasons that it can't at this point. but I have been for years, like literally years and trying to think about how to improve the processing of these PDFs on the server side, so that they're more consistent even for larger projects. And the other day I was like, you know what I mean?

[00:18:19] **Ben:** What if I come at this from a completely different angle? What if, instead of trying to generate the PDF on the server, I try to push that generation to the client side and just bypass the server altogether, because then it's the user's memory and their browser technologies. And maybe that'll be okay.

[00:18:34] **Ben:** And I'm sitting there thinking about it. I was doing some Googling, thinking about the there's some JavaScript libraries that can help you do PDF generation. And then I was thinking about tax time, cause I was just filling out tax documents just recently. And I realized that every time I have to generate a PDF from some, statement inside of a bank account, I'll just do the print feature.

[00:18:56] **Ben:** And my printer has a save as PDF. And I'm like that is that just on Chrome, because I only use Chrome for the most part. So I started looking at it existed at Firefox and safari. And then one of the guys on my team, who's got a windows gaming machine. I asked him to check and he looked at all the various browsers on the windows machines and they all have some form of

[00:19:15] **Ben:** print, a PDF or save as PDF.

[00:19:18] **Adam:** That's a relatively modern addition, right? Like within the last five years.

[00:19:22] **Ben:** think so. I think so. And, but it's great because it's basically using the browsers rendering engine and just like magic PDF. so I was like,

[00:19:32] **Tim:** It's not a great PDF though. It's not a,

[00:19:34] **Ben:** it's it's like pretty good

[00:19:37] **Tim:** it usually has like the URL, the bottom. Doesn't it.

[00:19:41] **Ben:** the settings, they all have settings where you can turn off, you can turn those things off and I'm not saying it's the best user experience. This is why this is yet to be determined. but I'm like, maybe I can just give people a print friendly version of this document and guide them into the now just hit print and do save as PDF and Kablamo.

[00:19:58] **Ben:** You have this PDF that's much more efficient than the one that you couldn't even generate because the server side kept crashing

[00:20:05] **Tim:** It sounds like passing the buck.

[00:20:07] **Ben:** it's

[00:20:08] **Adam:** Which it absolutely is, but I think that it's a very clever approach. And I think whether or not it's going to work depends entirely on the audience that the users that are going to be using this. And it also, I think I have some concerns based entirely on the content. Right. So this is your Invision stuff, right.And so we're talking about like application mock-ups or whatever, that sort of thing. Right. Okay. Because, so we're, we have a similar. effort, I guess I'll say going on right now. but ours is generating, receipts for donations. And so, having a user fiddle with the amount that they donated before they hit the print button, right.

[00:20:46] **Adam:** If they can pop, open

[00:20:47] **Adam:** the dev amount, then that's a big deal. So, but, and so we need to be able to give them a PDF that's watermarked and has the, university seal on it and all that stuff. So, and it has to be flattened to a single raster layer, right? So you can't copy and edit the text and stuff.

[00:21:04] **Adam:** So I'm a little glad I don't have to work on that, but at the same time, the guy who is working on it has gotten to touch a whole lot of really neat stuff. I think he's got like a Lambda function running and it's in a container and it's calling out to, like a postscript to do the printing to PDF.

[00:21:21] **Adam:** and then like returning,it's really interesting what he's doing. and all of us in a Lambda function is pretty cool.

[00:21:27] **Ben:** I mean, ultimately right. I'm working in with some, I'm working inside some pretty significant constraints because ultimate. If I could just factor out the PDF functionality even to its own set of two its own service. I mean, I'm not a huge fan of microservices, but this is the kind of thing exactly that I think should be in its own service.

[00:21:48] **Ben:** It's very CPU intensive. It's very Ram intensive. If I could have that in its own thing and Jack up the Ram or do something where it's like now spawning off to a headless Chrome or something to have the browser do the rendering, but on the server side still, then we'd be cooking with the gas.

[00:22:05] **Ben:** But the problem is,I'm the guy, I'm the guy on the legacy team and there's not that kind of time to get it done. And there's also a bunch of cost constraints about, we have some data isolation issues where I can't just have a centralized service that would do this because I can't, I have customers and I can't send their data to the centralized service, not because of security, but because of contractual

[00:22:27] **Ben:** obligations. Yes, something like that. So it's like, I'd have to give them individual versions of all of these things. And now it's an infrastructure problem and a cost problem and a platform problem. And it's like the best way is not the, it's not the workable way. Unfortunately.

[00:22:46] **Tim:** Have you ever taken a look at a Apache PDF box? It's a Java PDF library. it's a lot more performance.

[00:22:53] **Ben:** I've, I think I've looked at it before. I mean, there was at one point where I was trying to find a whole bunch of different solutions, but

[00:23:00] **Adam:** I think based on your situation where you're the legacy app, it's not going to live forever, getting it done and moving on to the next thing is probably more valuable than getting it. Perfect.

[00:23:11] **Ben:**

[00:23:11] **Ben:** That's how I feel.

[00:23:12] **Adam:** I thinkyou're justified in pushing it down to these. I think you can probably improve that user experience.

[00:23:16] **Adam:** Some, like load the page, pop up a little in-page modal that says, all right, I'm about to hit print when you hit, okay. So you can click the print button for them.

[00:23:24] **Adam:**

[00:23:24] **Adam:** and this is what you need to do. And if you really wanted to go all out, you could like do browser detection says, okay, you're on edge and you show them like a screenshot

[00:23:32] **Ben:** Oh, that's way better than what I was thinking.

[00:23:34] **Adam:** Right. You show them a screenshot and this is where you need to click. Right. But that's a, that's an opening, a big can of worms too. So, but even the, if you just said, Hey, I'm about to open the print dialog. Don't worry. It's just, this is the thing you asked for, save as PDF and you'll get what you want.

[00:23:48] **Tim:** Or just print it, kill some trees.

[00:23:52] **Ben:** I mean the silly thing, and I'm not saying this to disparage any of our customers,

[00:23:56] **Ben:** obviously. Uh, but

[00:23:59] **Tim:** Yeah. Only works on the server.

[00:24:02] **Ben:** the things that they're putting in the PDFs are these mock-ups of product. And they don't fit well on, an, a four or like a letter. I don't know. I can't remember. It was, so it's not like it's not even, like they're doing this to have a really high quality of something.

[00:24:17] **Ben:** It's like they have a process. The process requires them to have a document representation of this thing for regulatory purposes or workflow purposes, or like, I don't know, for whatever reasons I don't even fully understand. So it's like, we just need to satisfy that. And if we can do that in a way that the server doesn't crash, I feel like maybe everyone could just get on board. I don't know, but it's a tough one. It's a tough problem. So that's me. So I have yet to, I, I have it, I have some metrics on it. both the old version, the old server side generation of PDFs still exists. That's used clearly very heavily today. I have this version also available use much, much more lightly, but it's a, it's new and it's fresh.

[00:24:57] **Ben:** So, we'll see where it goes. So it's a, yet to be determined. Triumph for failure. I'd say triumph that I thought outside the box, but

[00:25:06] **Adam:** So as benevolent dictator for life of triumphs and fails, I'm going to go ahead and declare your so triumph. I like it. And Tim, yours is a failure cause store procedures suck and I have yet to be convinced otherwise. And I'm still on the fence about my own. I don't know. You guys can tell me.

[00:25:22] **Ben:** I mean, you got cool stuff going on, technology wise. So I

[00:25:26] **Adam:** Yeah. Oh, okay. So let me tack this on to this happened like hours ago. same project, right? And when I left off, we had the Lambdas running and everything's hunky Dory. I actually, no, I'm sorry. This is a different project, similar stack, but it's slightly different project. This one. Th there's a SQS queue, triggering some stuff to happen.

[00:25:45] **Adam:** And we were getting errors at first when I tried to set it up in QA. but as soon as I like fix the errors, like it's like a, your credentials are wrong, so you can't access the database or whatever. Right. So that sort of thing, as soon as I fix that, the logs are entirely empty, right? So it's all pumping to CloudWatch.

[00:26:02] **Adam:** It creates log streams and law groups as necessary, but everything is just 100% empty.

[00:26:08] **Ben:** Nice.

[00:26:10] **Adam:** I, it was like, okay, I must've done something weird and wrong. So I fixed a couple of other little problems I can figure out or wrong along the way I get through a hundred percent working test today. like a sort of an end-to-end test in QA and still the logs are empty when it's, when it's working. That's when I realized that I'm using that debug module that I love so much. And it requires you to set an environment variable to turn on the logs.

[00:26:35] **Tim:** And it's just, I was working with another guy and when I said it out loud that, oh, it's missing the environment variable. It turns on the logs. We both just cracked up like, duh.

[00:26:46] **Adam:** So yeah.

[00:26:48] **Ben:** That's funny.

[00:26:49] **Adam:** So, let me go ahead and throw this out here now. Carol, couldn't be with us today. She's got jury duty. so doing her civic duty and missing out on the

[00:26:56] **Tim:** for a murder case?

[00:26:59] **Adam:** She won't tell us which one. unfair.

[00:27:01] **Tim:** Well, no, she wouldn't tell us cause she was in jury duty when I asked her. So

[00:27:05] **Adam:** Yeah.

[00:27:05] **Adam:** Well, I don't think she would tell us

[00:27:06] **Adam:** anyway, they're

[00:27:07] **Adam:** not

[00:27:07] **Ben:** got gag orders or

[00:27:08] **Tim:** She'll tell us after it's done.

[00:27:11] **Adam:** hypothetically,

[00:27:13] **Tim:** Yeah.

[00:27:14] **Adam:** allegedly.

## [00:27:15] Mingo's Too Many Hats Question

[00:27:15] **Adam:** Okay. Cool. so our topic today comes to us from a listener sending in a question. So our question comes from Mingo in the Netherlands. Hi Mingo. so here's this question. Do developers today wear too many hats? Does our work suffer for it by spreading yourself too thin? And how many different tasks is too many? I thought that's a really good question. Lots of discuss there.

[00:27:38] **Ben:** I have a love, hate relationship with the idea of wearing too many hats. I, on one hand, I think it would be so nice to have one hat on and just go super deep on that thing and jam out on that thing all day long and not have to worry about everything else. But then I can't get past this idea that the more hats that I wear, the more I can sort of get done at work.

[00:28:03] **Ben:** because the reality is taking some story or task or epic from ideation to completion. Usually you just have to touch a lot of things, whether it's new database stuff or some design stuff, some front end stuff, it's a backend stuff and, task prioritization or some project management, some cross team communication.

[00:28:22] **Ben:** And like, if the more comfortable you are with all those things, the more likely it is that you can actually just get that thing done. so it, it can be super overwhelming though. And it's like, I look over the fence at the people who are just, jamming out in CSS and JavaScript all day. And I'm like, ah, that's a nice life.

[00:28:40] **Ben:** You must really enjoy things. Like, like you're working on it. Like you're on clients, that stuff you never get paged. Like you never caused an outage, right? Like you never deployed a query that took down the server. Good for you. That's awesome. So I don't know. I go back and forth On how I feel about it.

[00:28:56] **Adam:** I mean, I think for me, it comes down to I guess, a combination of personal preference and ability, and I don't even know how to describe it, but like, I guess it's very similar to what you're saying. Ben, the. Specialize then you can go really deep. And I think that gets to the, does your, does our work suffer for it by spreading ourselves too thin?

[00:29:17] **Adam:** if you only ever do JavaScript, you don't have to worry about CSS. You don't have to worry about design. You don't have to worry about SQL any of that. You do JavaScript and API access. Then you're going to get really good at that. And you're going to write really clean code and, have good tests for it.

[00:29:34] **Adam:** And, versus, if you have to do the JavaScript and SQL and the design and the CSS and they, what does the dev ops and the meetings and the project management and everything, then I think, yeah, your work does suffer for it. But I think like you were saying, but there's a trade off,

[00:29:49] **Ben:** it's hard to, because I ultimately want to be really good at stuff. And I know that a limit on how deep I can go on anything and it's not a, it's not a failure. It's like a, almost like a nostalgic regret. Like, oh, I could have lived that life. That would have been

[00:30:09] **Tim:** Multi-use multiuniverse Ben.

[00:30:11] **Ben:** yeah, exactly.

[00:30:12] **Ben:** Oh, back-end only Ben he's living now. He's living large front end only Ben he's having a good time. Or like Ben that went into management like, oh, you know what? He's a force multiplier. Good for you. Manage your ban.

[00:30:24] **Tim:** multiplier.

## [00:30:26] T-Shaped Developers

[00:30:26] **Tim:** really think it depends on your personality. I know I'm the kind of person who likes to know something about everything and it had been, you introduced me to this phrase, a T-shaped developer, right? So the T you know, you're kind of, you have, some knowledge to a D to a certain depth at the top about a lot of things, but there's like that the T part that goes down deep, you have a strong knowledge of a very specific thing.

[00:30:52] **Tim:** And I kind of liked that. I don't like not knowing, how something works, particularly in. That run into this in the organization. So if you have a teams that everyone knows their jobs, and everyone just does their jobs and everyone understands what, what's going on and stuff gets done, you can just hand something off to someone.

[00:31:11] **Tim:** And really just, they got the specs, they can read the ticket or whatever, and they do their stuff. Sometimes it's like there's issues. Well, for us, I don't know every organization, but for sometimes it's like the programmers and the people who deal with the virtual machines and the DNS and the certificates and the infrastructure kind of stuff, as we call it, there's a disconnect. And so I've been in both those worlds. I ran those, both those departments and having that knowledge, I feel like I can bridge that gap. So that is always made me want to know. I don't want to just say that's not my problem. Every part of the app is my problem to a degree. Certainly. A hundred percent of it is my problem, but other parts, maybe 20% is my problem, but I have to know about it.

[00:31:56] **Tim:** And that's just my personality. Other people are just quite happy to, just know about one, not even, some technology, just one, maybe portion of an app, if it's big enough and just, they're the expert on that. They don't care about anything else in it, but that would just, it would drive me nuts to be working in the same thing.

[00:32:12] **Tim:** I like the variety, I like a little change of pace and not dealing. I actually enjoyed working the store procedures. I haven't, even though you hate them, Madam. I hadn't worked in them. And so I haven't built, the, these complex kind of data calls in, in years like, oh, wow, this is pretty cool.

[00:32:29] **Tim:** So yeah, I just need variety. Otherwise I just get really bad.

[00:32:33] **Adam:** I mean, it's just another programming language. Take it back to the store procedures. I think when it gets to me about them, is that the. Ecosystem for them is not as fully developed

[00:32:43] **Tim:** Yeah,

[00:32:44] **Adam:** modern it's at the end. It's hard to get them into version control and deploying them as if he, whatever sort of thing.

[00:32:53] **Adam:** not, they're not that they are difficult to deploy, but that it's a very manual process.

[00:32:58] **Tim:** and I mean, we, we have all that automated, I mean, ever since Microsoft SQL came out with the create or replace, create our altar, statement, it's really made version control a whole lot easier

[00:33:08] **Ben:** That's for tables, like table schemes. You're

[00:33:10] **Tim:** breathing creator, replace store procedures is what

[00:33:13] **Ben:** oh,

[00:33:14] **Tim:** So.

## [00:33:15] Dev Ops

[00:33:15] **Ben:** we had talked about this many episodes ago. I think actually based on another listener question about, like how much dev ops should, you know,and I think that this is an area where people are forced to wear multiple hats. And I think the work does suffer.

[00:33:31] **Ben:** And, because containerization creates this sort of weird abstraction around what's actually being run, not like that your code is being run, but like how it's actually being executed and what the infrastructure is. And if you don't understand how containers work and how containers fit into like a larger deployment ecosystem, it can be very confusing as to why something's not running well.

[00:33:54] **Ben:** Or, like their CPU is maxing out. And like, you don't realize it's because like your container was barely given any CPU and like, you didn't even know that was a thing. and it's just the technology landscape for complex systems now sort of forces you to understand more than you. I don't want to say should, but like more than you used to have to know in order to get things to run well.

[00:34:14] **Adam:** that's an interesting thought. So often I think we hear about like, somebody joining the workforce today has so much more to learn than we did when we joined the workforce.

[00:34:24] **Adam:** But I think that this very closely ties to the amount of hats that we're expected to wear. And I think that is very much because we are.

[00:34:31] **Adam:** pretty far along in our career and, senior developer or higher sort of people. and I wouldn't expect a first year junior developer to be able and willing I'd be happy if they were, but it wouldn't expect them to be able and willing to pick up dev op stuff. And I, all the little stuff that goes along with my projects.

[00:34:51] **Adam:** So,

[00:34:51] **Ben:** I just wish I knew it.

## [00:34:53] Organization Size

[00:34:53] **Adam:** so, I hesitate to talk about Carol on a show that she's not here, but I it's not a negative thing about Carol. It's just she's provides the context. Right. So, we talk about how we, the four of us are so different. we work at different companies. We have different roles when Carol talks about life at her company.

[00:35:10] **Adam:** It's so it's like a culture shock to me because she works at such a big company and.

[00:35:14] **Ben:** much process,

[00:35:16] **Adam:** Exactly red tape and project management goes into it. Whereas in my company, we're five people all in and it's like, okay, here's the project. When can you get it done? Oh, three days. Cool. And it's in production, three, four days

[00:35:29] **Adam:** later.

[00:35:30] **Adam:** and that's everything, that's the meetings, that's the design, that's the tests, that's the coding, it's the QA, it's everything. And I get the feeling that, at Carol's company three or four days is like enough time for them to have the meetings, to hash out what should be in the feature, Right. Like, and I could, I don't think I could go back to that sort of environment. I've worked at companies that big before, and I think I've just become too accustomed to the velocity at my current place.

[00:35:59] **Ben:** Mm.

[00:35:59] **Adam:** And I think that kind of ties into the number of hats thing. Right? So like, because we're so small, it gives us that ability to be so agile, but it also requires that we all can kind of play every position on the field.

[00:36:14] **Ben:** Yeah. Yeah, totally.

[00:36:15] **Tim:** Yeah, I do think as you, as the organization gets bigger, you have more and more specialization, right?

[00:36:20] **Tim:** Just out of the nature.

## [00:36:21] The Curse Of Knowledge

[00:36:21] **Ben:** another downside that I think of wearing hats though, too many hats is

[00:36:26] **Ben:** you sort of,

[00:36:29] **Ben:** you

[00:36:29] **Ben:** sort of have a curse of knowledge, meaning that, a little bit about a lot of things. So I think to some degree you don't feel the need to think outside the box or to explore new options because you're like, I sort of have the tools that I can use to get this. and I think back to, when I first started to learn about her, not learn about, but hear about graph QL and people were raving about, oh, this is so great. Like people can just get data from the server and like, they don't have to deal with the back end people. And as someone who is both back and in front end, I'm like, I don't get it.

[00:37:00] **Ben:** Like, just get the data. Like, how is that hard? And they're like, no, it's like, you can just write the queries on the client side and you can send to the server and services gives you the data. Just write the query is they give you the data. Like, I don't understand what your problem is. Like, where's your friction.

[00:37:14] **Ben:** And it's like, literally months would go by when I started to hear about graph QL and someone was finally like, I don't know how to write SQL. I don't have access to the database. I'm like, oh, I get it. Now you like, literally can write those queries. It's not that you don't want to, but it's like, because I come at it from a, I can dabble in this and I can dabble in that.

[00:37:34] **Ben:** Like there's like, it doesn't occur to me that there's like a newer, more efficient way to do something. And I'm not saying that graph QL is necessarily a newer, more efficient way to do something. I'm just saying like, it's a new thing that it would not have occurred to me to do because I have the quote unquote curse of knowledge of how to gather data on the server side.

[00:37:51] **Ben:** So I think there's this just like, you're less open-minded

## [00:37:55] Not My Problem

[00:37:55] **Tim:** Yeah, speed of a curse of knowledge to paraphrase Spider-Man with great knowledge comes great responsibility. And there's something to be said for saying, you know what? I don't know anything about that. I'm out. Don't call me. don't hit me up

[00:38:09] **Adam:** I have to, have to put in a correction. Sorry. That was uncle Ben.

[00:38:12] **Tim:** From Spider-Man movies. I wouldn't say Spiderman said it,

[00:38:17] **Adam:** You said you were quoting Spider-Man I'm sorry. I just want

[00:38:19] **Adam:** it to be

[00:38:19] **Tim:** movie

[00:38:21] **Adam:** Hey,

[00:38:22] **Ben:** Just phrase it better. Next time

[00:38:24] **Tim:** it was also aunt may.

[00:38:25] **Adam:** I don't think

[00:38:26] **Tim:** Yes, she did. She did the latest movie. I haven't seen it.

[00:38:30] **Adam:** Which, which one? Oh, far from home?

[00:38:32] **Tim:** Yeah.

[00:38:33] **Adam:** No, I haven't seen that one

[00:38:34] **Tim:** So she's I won't spoil

[00:38:35] **Tim:** it for you then. All right. She said that she did say that, but a very important scene, but anyway, yeah, I mean, it's like, if you're like, I, I don't work in this section. I can't help you because if I find know something about something that there's an issue, I feel obligated to help out.

[00:38:52] **Tim:** That's just how I am. Like, I'm going to jump, I'm gonna stop what I'm doing. I'm going to help you out. Even if like I have a deadline or, I'm working on something important. It's like that. That's how I feel. So to be able to say, honestly, say without any internal guilt, I'm sorry. I don't know anything about that.

[00:39:09] **Tim:** Part of the program. I can't help you is refreshing.

[00:39:13] **Ben:** Yeah, I agree with that. A hundred percent. I love being able to say, I'm not your guy. I do not know anything about what you just said.

[00:39:21] **Adam:** That was actually, so when my company was just me and Steve, the. Product that I work on. I was the guy who knew about a hundred percent of the things, because I wrote all the code, for this particular product and hiring other people and like sharing responsibility. It was such a double-edged sword because it's like, I have to let them take control of parts of my baby.

[00:39:43] **Adam:** And I do code review and it's like, you have to sit there and go, I'm not going to comment on that. I'm not going to comment on that. I'm not going to comment on that. It's fine. It's just style. but,at the same time, like that was the, there was some initial hurt giving up that control, but then you hear it years later.

[00:39:58] **Adam:** it's so freeing, like you guys are talking about, there are just parts of the application that I don't know anything about, and that gives me.

[00:40:07] **Tim:** I recently gave acts there. This project is a project. It's a small project, just an API, small API. That I'm the only one who wrote on it for the past three years. And recently I've started opening it up. We hired some more people and I've opened up some new people and they started doing pull requests.

[00:40:25] **Tim:** And so I looked the pull requests looked okay. But then actually when it, there was an error that came up in the lower environments that didn't get caught in a D and lower in the, local. And they're like, oh, we need to fix this area. This is an urgent error. I see you in an area that you just introduced.

[00:40:42] **Tim:** This is, but I didn't bring that up. I'm like, I don't want to, they're getting used to seeing other people muck around in the stuff that like has been my 100, it's only me in there and now the other people's fingers are touching it. it's it's a dirty feeling.

## [00:40:56] Ownership And Boundaries

[00:40:56] **Ben:** yo, can we side quest for a second here

[00:40:58] **Tim:** Sure.

[00:40:59] **Adam:** Ben needs a minute.

[00:41:01] **Ben:** in a minute.

[00:41:02] **Ben:** So this is something that never quite sits right with me. And I think it's because I get too emotionally attached to code, but I think there's also a philosophical conversation to have here, which is at work. We often talk about running teams as sort of like an open source model where yeah.

[00:41:20] **Ben:** A team might own a certain number of services, but if another team needs change those services, like they should feel free to come in and open PRS to change those services. And there's something that has never quite sat right with me about that because. I just like, I want to own the code and I want my team to own the code and I want the code that's in the service that we own to be like part of our subconscious and to have instincts for when an incident happens or we see a change in the, graphs, or we see things start to show up in the air logs.

[00:41:57] **Ben:** Like we should all have the sense of like, oh yeah, we wrote that code. So w we have a good sense of where that might be coming from. And when you run it a set of services with an open source mentality, we're just like anybody can jump in. And as long as the PR gets reviewed, code can just get committed to that.

[00:42:13] **Ben:** It just feels like weird ownership, boundaries.

[00:42:16] **Adam:** So Ben, have you ever, uh,

[00:42:18] **Ben:** if you ever worked with other humans,

[00:42:22] **Adam:** that's not a bad question to start with, but that's not what I was going to ask. so I was going to ask it, have you ever like been the lead maintainer on a somewhat large open source project where you are getting poor? Yeah.

[00:42:38] **Ben:** Honestly, like emotionally, I don't think I could do it.

[00:42:41] **Adam:** So, it's a strange phenomenon. I have the lightest of experience in that field with taffy. There've been, God bless him, maybe a dozen or two dozen people that have put in a pull request or two overtime, and I'm immensely grateful for them and every now and then I'll have to be like, I don't think this is a good addition to the product, you're free to create your own fork, and, use it for your company or whatever would that change.

[00:43:03] **Adam:** But,I'm not gonna accept that into the project or,I've asked people to reconsider an implementation, do it slightly differently sort of thing. so when you're describing. Company sort of services. And I use that term as a, I guess, a business service, more than a technology service, right?

[00:43:21] **Adam:** Like, it may be a technical thing, but,it's a product offered by this area of the business. I like the idea of treating it as open source and allowing people throughout the company to make changes. But I think that it has to come, has to start from a discussion. Right? You should never get a pull request without any warning.

[00:43:39] **Adam:** Right? Like, you shouldn't have it just like you should never be pulled into your office, your bosses office and find out at your yearly review that you're doing terrible. Right. You should see it coming.

[00:43:47] **Tim:** right.

[00:43:48] **Adam:** There should be warning signs. and so, if somebody wants to make a significant change to your project, they, there should be an issue first where they like, bring up the question and discuss it with you.

[00:43:58] **Tim:** I look at it from the opposite side, Ben, and so, I've been in the situation where I, I have my set of stuff that solve for payments. And then I have an internal companies repositories that are pulling from those, th they're not experts on my stuff, but, and I have a fair amount of familiarity with their stuff.

[00:44:18] **Tim:** I just feel it's lazy for me. If there's an issue to say, Hey, you got. not doing something correctly near side and it's causing issues with our payments, fix it. And I know that's going to take a long time. So my natural reaction is just, I'll go create a PR to go say, all right, here's what you need to do.

[00:44:35] **Tim:** Please review this. If you don't agree with it, you can certainly try to come up with your own solution, but here's the problem trying to solve. I just feel it, I know they kind of own the code, their team, but it's like, I feel like I should at least take a college, try at fixing it for them because they may not realize on my side, what's going on.

[00:44:56] **Tim:** So, but I kinda get it. I get what you're saying too.

[00:44:59] **Ben:** There's also, and I know we're way off topic here, but

[00:45:02] **Adam:** Hey, it's our show.

[00:45:03] **Ben:** yeah,yeah. I dunno if you've ever had this experience, but I will sometimes try to plan something out. Like I have an idea and instead of just jumping directly into code, I'll actually try to open up an epic in JIRA and start to write out some tickets and start to actually spend some thought time about how I want to put this together.

[00:45:22] **Ben:** and, maybe it'll take a couple of hours. Maybe it'll take a couple of days, depending on how in depth I want to go. And then every now and then I'm like, okay, now it's time to write code. And I get like 10 lines of code into it. I'm like, yeah, none of this is going to work. Or like, this is like, it's totally not going to, like, now that I'm writing the code and like, my fingers are on the keyboard.

[00:45:39] **Ben:** It's like, it changes the mental model. And now I'm thinking about differently. Now I'm remembering, oh, but I have this other code over here that maybe I can refactor so that I can reuse it here in a way that couldn't have been reused before. And it's like, unless you're the one writing the code in the system that you've been maintaining, like, do you have those moments of insight?

[00:45:56] **Ben:** and if you don't like, if you're just doing PR reviews, it's like,

[00:46:01] **Ben:** I

[00:46:01] **Ben:** don't know.

[00:46:02] **Adam:** I used to come up in an issue firsthand.

[00:46:04] **Ben:** Yeah. I dunno. I just, I have, I mean, it's ultimately, it's very possible that I'm completely off base here and it's just because I'm very emotionally attached to the code and that's end of story. But I.

[00:46:17] **Adam:** Are you going to have like a funeral for the code when the legacy system goes away,

[00:46:21] **Ben:** I'm going to have one of those, the pyres you said, and like push out into

[00:46:24] **Ben:** the river.

[00:46:25] **Adam:** see in the

[00:46:25] **Adam:** light it on

[00:46:25] **Tim:** take a bow and arrow, take a bow and arrow with a flame on it. The, let it

[00:46:32] **Adam:** SD card in your sink

[00:46:33] **Tim:** Yeah.

[00:46:34] **Tim:**

[00:46:34] **Adam:** a little boat, made a toilet paper.

[00:46:36] **Tim:** poor 40 out for the homeys. Uh, goodness. Yeah. So, I mean, as far as this hat things go, I mean, I just, honestly, men go, I think it depends. It depends on your personality. It depends on your, organization. It depends on the size of it. it totally depends if you feel, if you still to stretch though, then maybe that's a conversation needed to have with somebody

## [00:46:57] Trends

[00:46:57] **Ben:** One thing that's interesting. So I listened to a bunch of podcasts technology

[00:47:03] **Ben:** podcast specifically. of a big listener. I listen to a bunch of technology podcasts, and I think just coincidentally, a lot of those podcasts sway towards client-side technologies. And there's a huge movement now with, a lot of client side technologies moving towards the background, like with remix that Adam was talking about earlier, but just all these new kind of react server side rendering, and like confluence of what's a CDN and what's, edge workers and serverless functions and how it's all sort of all these client-side technologies are slowly creeping towards the back end. and it's like, it creates this sort of echo chamber. This is the thing that's, everyone's talking about and you're, and you start to think like, oh, this is all the hot stuff, but then you forget sometimes because you're in this echo chamber that there's this huge world of people who do server side programming, and they're more than happy to have code compiled and execute on demand and pull from databases and not have to like pre-build into static CDN delivery. I kind of forget where I was going with this, but I guess, I guess, sometimes if you just listen to people who don't wear a lot of hats, then I think your view of the technology landscape can start to get very skewed in a

[00:48:27] **Ben:** weird way. Right. Like, if all you did was listened to react developers and them talk about server side rendering, and how do I do builds and incrementally serve cash assets.

[00:48:39] **Ben:** Like you could convince yourself that you don't even need to know a server side development and like database stuff and all this, like battle tested things that we've been doing for the last 30 years. But then you start to talk to those people and they're like, why would I do go through all that rigmarole of rendering all that jazz when I can just have a server side programming, do it and like call it a day.

[00:49:01] **Ben:** And you're like, oh yeah, that sounds really simple when you say it like that. so I th I, even, if you don't wear a lot of hats, I feel like you, you have to be surrounded by people who either have a lot of different hats or with people who have a lot of hats on.

[00:49:14] **Tim:** just around them, it needs to be communication between them. Right. I need to understand their roles.

[00:49:18] **Adam:** Well, yeah, I mean, the landscape has changed, right? When we entered this field, you had an, HTP HTTP server and maybe like some pearls grips or something. Right. and now there's so much different stuff that goes into the average website and the number of hats that you have to choose from has grown exponentially since 15 years ago. So, yeah, I mean, I think the general thesis is yes, our work suffers for it, but sometimes it's worth it, I guess. like Tim was saying that the number of hats that's too many as a personal number, the other thing Ben, you were talking about,going back to server side, I feel like. I've been around in his field long enough. So I started programming in 1999. semi-professionally I guess you could call it amateur. I was part-time working while I was in high school, but, I've seen a shift from like entirely server-side to so much clients. I like thick client thin client and going, or I guess it was the other way around it thin client, that client, and now we're going back to thin client

[00:50:23] **Adam:** and it's, I feel like if I were a more insightful and reflective person, I would be able to tease something interesting out of that. I honestly, I think this is both sort of a triumphant of fail of my own personality. I feel like I'm extremely good at living in the moment. Right. I live now. I don't live 10 minutes ago. I don't live 10 minutes in the future. and. There are times that helps me in, in, not in, just in technology, but also in personal relationships, in dealing with my kids and with stuff that happens to me throughout the day.

[00:50:58] **Ben:** And I feel like it takes away from my ability to,to reflect on my career. Right. I've been doing this for 22 and 23 and change years. And, yeah, I mean, I was there for it all, but I don't know that I have any amazing insight to provide from it. I couldn't write a history book of it all, Yeah, I know what you mean. I know exactly what you mean. I feel like, not to make fun of, it's easy to, it's easy to look at the pendulum swing between the server side and the client side and the service side. And we'll, I'm sure eventually be client side again and like scoff added or make fun of it.

[00:51:33] **Ben:** Like, oh, that's what we were doing 10 years ago. but they're doing it in such different ways and I feel like I'm sure they're much better at the thing that they do. Then the thing that I do that looks like the thing that they do.

[00:51:44] **Adam:** That was a little too abstract for me.

[00:51:47] **Ben:** Click like, yeah, I can write clients I code and they can write client-side code, but like there's so much living in that world of client-side code that like, I'm sure they're doing that much better than I'm doing it,

[00:52:00] **Ben:** but I think they also lose perspective too, because sometimes I listen to people, talk on podcasts about, well, how do I render this thing on the service side, but then have part of it that it has to be specific to a customer.

[00:52:13] **Ben:** So that can't be static that has to be generated dynamically through an API call. But then like, I don't know if the user's locked in yet. So I have to maybe show a login form or maybe show the app, but I don't want to give them a flash of the app, but then have to take them back log in form. Right. And like, because they're struggling with all these problems where if you're doing server-side render and you're like, I just checked to see if they have an active session.

[00:52:33] **Ben:** And if they do give them pop their custom code. And if not, I show them a log in form. Like, like these are problems we solve 15 years ago. I don't understand what you guys are talking about.

## [00:52:41] Log4j

[00:52:41] **Tim:** Yeah, I'm speaking from a great well of ignorance here, but,if so much as client side, it makes me wonder, significantly smart person who can open F 12 developer tools can start messing around in your code and change it because it's all client side, right. that just scares me.

[00:52:56] **Ben:** I mean, I see people, we get tens of thousands of malicious requests against the application that shows up in the air logs all the time. and it is terrifying when the log for J stuff started coming out. Oh my God. The amount of variations of log for J things that we're starting to see show up in logs with terrifying.

[00:53:17] **Ben:** I mean, thankfully I don't think because Lucy was not susceptible to it. and we don't have anything else. That's really running on a Java platform. But just to see it happen. Like even if you're not susceptible and you see it come through, you're like maybe I'm susceptible and I don't know.

[00:53:32] **Ben:** Yeah. This is terrifying.

[00:53:34] **Tim:** You see it, you see the knocks on the doors. You don't know how many doors open, right?

[00:53:38] **Adam:** maybe it's because I have a sort of a default slight, I'll say slight negative opinion of CFML in general. I said slate. they, when they were talking about how so when log for J happened and, it was discovered that Lucy was not vulnerable. I fell and this was my own personal feeling, but I felt like those statements were somewhat smug.

[00:54:04] **Adam:** Like, oh no, we're fine. we're not, vulnerable and

[00:54:07] **Tim:** because of oh, a CGI

[00:54:10] **Adam:** oh, SGI.

[00:54:11] **Tim:** it was. Yeah. Yeah.

[00:54:12] **Adam:** and that, and because, they're on such an old version of log for J that the vulnerability hadn't been introduced yet.

[00:54:20] **Tim:** Yeah. It's nothing to brag about.

[00:54:21] **Adam:** Yeah, exactly. And, like, I didn't want to like, be the guy that was like, oh yeah, you're not vulnerable, but that's because you're on such an old version that probably other vulnerabilities.

[00:54:32] **Adam:** But, I dunno.

[00:54:34] **Ben:** You just can't win. I mean, the reality is not this, not to tangent, but like all languages have problems.

[00:54:40] **Ben:** This is one of the things that I get super frustrated with in, in the programming world in general. People sort of being blind to the fact that the language that they use is basically just as terrible as every other language. Like all languages have so many problems and like you just learn to live with that.

[00:54:57] **Ben:** And I think you forget that the thing you're using, you're just good at it now. And if you went to another language and you didn't have that wealth of information, you'd be terrible. I mean, like, I think everyone, I'm sure a lot of people are familiar with the, the JavaScript whack presentation.

[00:55:13] **Ben:** I don't know if anyone's seen that. There's it's like a lightning talk. I can't remember who did it. It was very famous guy. is it the low dash guy? I can't remember

[00:55:20] **Ben:** some. No, that's not him. Anyway. he walks through like all the really crazy edge cases that you wouldn't ever do on a, on like real-world program, but

[00:55:28] **Ben:** like, oh, Right, right.

[00:55:29] **Ben:** Like object plus string is number, but string plus object is string. And you're like, wow. like why would that make any sense? but like all languages have that and people love JavaScript. Like you can have a whole wet presentation about a technology that people, are jonesing about. and the reality is it's like all languages have that kind of stuff.

[00:55:48] **Ben:** So I just get in my old age when I was younger, I'm sure I was so much more pro language, but like in my old age, I'm just like, all languages are terrible and great at the same time. And you just, you find the one that, that, looks at you the way you look at it. And,and you make beautiful things.

[00:56:04] **Adam:**

## [00:56:04] Patreon

[00:56:04] **Adam:** So this episode of Working Code is brought to you by backend only Ben that's back. I'd only been

[00:56:08] **Tim:** Multiuniverse back in only Ben.

[00:56:12] **Adam:** And listeners like you, if you're enjoying the show, you should consider supporting us on Patreon. It's the best way to help keep the show running Patreon donations, cover the cost of editing and recording. And we couldn't do this every week without those things. So we appreciate all the support that we can get special.

[00:56:26] **Adam:** Thanks to our top Patreon Monte. If you'd like to help us out, you can go to patreon.com/WorkingCodePod. All patrons get early access to an ad free version of new episodes and the after show.

## [00:56:38] Thanks For Listening!

[00:56:38] **Ben:** Are you staring angrily at your phone? Because you could have contributed something valuable to the conversation that we missed. It sounds like you should join our Discord. So you can talk to a bunch of other like-minded coders and share your knowledge. Go to workingcode.dev/discord to join.

[00:56:54] **Adam:** that's going to do it for us this week. We'll catch you next week and until then,

[00:56:57] **Tim:** Remember your heart matters. Even if you have a Schrodinger's fail.
