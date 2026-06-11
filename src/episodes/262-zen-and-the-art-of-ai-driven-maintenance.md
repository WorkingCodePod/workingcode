---
title: "262: Zen and the Art of AI-Driven Maintenance"
description: "This week is the quiet worry underneath all the productivity gains: What happens to your curiosity when you start handing all the boring work to a machine?"
date: 2026-06-04
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/262-zen-and-the-art-of-ai-driven-maintenance/id1544142288?i=1000771470155"></iframe>

This week is the quiet worry underneath all the productivity gains: that every time you hand the boring work to a machine, you're handing over a little of the curiosity that made you good at the work you care about, until one day the well of ideas just runs dry.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Thursday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

Mentioned in this episode:

- [Taffy](https://taffy.io/) — the REST framework for ColdFusion and Lucee
- [Rest Assured](https://restassuredbook.com) by Adam Tuttle
- [Postman](https://www.postman.com/)
- [Engineering Explained](https://www.youtube.com/@EngineeringExplained)

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/262-zen-and-the-art-of-ai-driven-maintenance.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Cold Open

[00:00:00] **Carol:** I also heard recently at work a term that scared me a little, is that we should be treating agents as employees. it made my stomach a little like, "Ooh, I don't enjoy this," because it suddenly makes me feel replaceable

## [00:00:35] Intro

[00:00:35] **Adam:** Okay, here we go to show number 262, and on today's show, we are gonna get into Zen and the art of AI-driven maintenance.but first, as usual, we'll start with our triumphs and fails. Tim had a scheduling conflict, is unable to be with us tonight, so it's just gonna be ABC: Adam, Ben, Carol.

[00:00:49] And you're just gonna have to deal with that, and we thank you for

## [00:00:53] Adam's Fail: Eating His Words on OpenAPI in Taffy

[00:00:54] **Adam:** it.I'm gonna start us off, and I am gonna go with a solid, confident failiumph, 'cause I can't decide.

[00:01:02] **Carol:** All right

[00:01:03] **Adam:** so, for the uninitiated, I wrote a book many years ago. It's about REST APIs. It's called, "Rest Assured." If you're interested, it's www.restassuredbook.com.

[00:01:13] Not, not sponsored. and I guess may- maybe I should say is sponsored. I don't know. Either way, I wrote the book. You can buy it. That's fine. but, you know, it, it was basically, like, I've been doing API stuff for years. I wrote a framework, and I wanted to crystallize my opinions on things and, you know, explain how I was seeing people do things poorly, how to do them better, and that sort of thing.

[00:01:37] In that book, I came out fairly hard against two things. one is, HATEOAS or, hypermedia as the engine of application state, H-A-T-E-O-A-S, or, or it's probably pronounced some different way that I've now successfully three times managed to not say correctly. and OpenAPI. I'm pretty sure that OpenAPI got mentioned in the book.

[00:01:59] it's been a long time. But, yeah, both just seemed like unnecessary ceremony for enterprise companies who wanna do a bunch of enterprise-y things that, you know, stop being lazy and just do the work type people like me would, not like. And so that's how I described them and, and why I excused them in the book.

[00:02:20] fast-forward to now, I have added OpenAPI spec generation to Taffy, my framework for writing, REST APIs.somewhat begrudgingly, but I did it. Uh, you know, we have a customer who was like... It, it kind of was gonna be the, the differentiator, like whether or not they signed with us.

[00:02:41] And I was like, "Okay, well, let me look into how much it would take," 'cause Taffy has a lot of metadata about your API, right? It has all the

[00:02:53] URI information, can infer a lot of things. There's a lot of like s- very terse configuration via metadata you can do, that sort of thing.and I was able to get like, you know, maybe 80 or 90% of the way there, just off of stuff that you are already feeding into Taffy anyway. So it was r- not that far of a reach to build OpenAPI spec generation.

[00:03:09] And I should say for the uninitiated, if you've heard of Swagger That kind of became the OpenAPI spec. Like the Swagger JSON became the OpenAPI JSON at some point. I am not an expert on this stuff. I just did the bare minimum to figure out how to generate what I need to generate.and that's good enough.

[00:03:28] **Ben:** see, see also Adam is lazy. Swagger is hella verbose from what I remember though

[00:03:34] **Carol:** I love Swagger

[00:03:36] **Adam:** It is... So, uh, the Swagger UI is interesting, right? Like, to, to be able to, like, look at an API and see, okay, these are all the resources, and these are the methods they support, and these are the imports, and, and this is what you get back, and, and being able to interact with it.

[00:03:50] **Carol:** Yep.

[00:03:50] **Adam:** Yeah, I, I mean, Swagger UI was in part inspiration or, or was one of the things that the Taffy dashboard was inspired by, right? Um,

[00:04:02] uh, so I have added OpenAPI generation to Taffy. it's not released yet. It's in a branch, but we're using it at work because we needed this customer to sign, and it's going fine. Um, it did require adding support from some additional methods in your resource CFCs to, like, fit, you know, that last mile, right?

[00:04:23] Like, 80, 90% can be generated from your metadata, you know, all that stuff. And then the last 10% or so is basically what are the possible responses, right? If you get a 200 or 201 or 404, and then what is the shape of the data that will be returned, right? what property... If it's an object, what is that object shape?

[00:04:45] What are the properties? For each property, is it a string? You know, what's the max length? Is it an integer? Is it a number that has decimal points? You know, what's the minimum and ma- and maximum values and all this other stuff. And Taffy just does not-- Because CFML has limited, I gu- Hmm.

[00:05:07] See, now I'm, I'm second-guessing myself. Maybe, maybe I should revisit this and, like, I might be able to pull... Well, for inputs, I could pull from metadata, on your request arguments, maybe. But then if any- if you have, like, deeply nested input objects, that's not gonna work. Anyway, so basically what I did was I added a method, added support for a method to your resource CFCs that allows you to return a chunk of data that gets, like, folded into the OpenAPI spec for that particular resource, right?

[00:05:38] So you say, "Okay, I've got this CFC." When you make a GET request, the GET function handles it, and then this, like, getOpenApiDocs method describes the shape of the response from the GET method. Okay, if it, if you get a 200, this is gonna be the shape. If you get a 404, this is gonna be the shape. If you get a 500, then you're probably at nothing, but

[00:05:59] **Ben:** the, the OpenAPI isn't actually impacting the inputs and outputs of the API call. It's, it's really just setting up information so that another consumer can consume your API

[00:06:12] **Adam:** It's literally just generating a bunch of JSON that describes your API

[00:06:16] **Ben:** Okay,

[00:06:17] **Adam:** and, as far as I can tell, again, see also not an expert, as far as I can tell, the primary benefit of something like this would be, okay, here's our OpenAPI spec, and you can feed this into your machine that will spit out an SDK for you to be able to work with our API.

[00:06:33] Like

[00:06:33] **Ben:** think when you first mentioned OpenAPI, had in my head something else, which I think is maybe called JSON:API which I think is more just a, a schema definition for

[00:06:45] **Adam:** Yeah

[00:06:46] **Ben:** work, where it's like there's a top-level structure and there's a, an array of errors and there's a data sub-key and then inside the data sub-key there's stuff. It's more like how to design APIs that are flexible. That's, that's, that's what I had in my head when you started talking about this. I, I

[00:07:02] **Adam:** Yeah.

[00:07:02] **Ben:** just thinking of the wrong thing

[00:07:03] **Adam:** So, I should, take a second to give credit where credit is due. So, this was, I believe, if, if remembering right, the, the chicken came before the egg here. a request came in from Dan Switzer, who some of you guys might know.

[00:07:17] **Ben:** Dan G. Switzer

[00:07:19] **Adam:** yes sir.and, and, and he was asking basically for sort of his approach to be added to Taffy.

[00:07:26] And I was like, "Well, you know, I can abide the idea. I'm not sure if I like the implementation that you're requesting." and so we went back and forth on it a little bit. And then sort of s- shortly after that, maybe a week later, we got this, like, request for work. And I was like, "Okay, this is, this is my sign," right?

[00:07:41] Like I'm, I need to do this one way or another. So I buckled down and, and got it done. I will say coming back to it, uh,the nice thing, the thing that has made it worth doing for me is that the tedium of tracing through the like 150 whatever URIs that we support, and that... So like if you've got 150 URIs, let's just say maybe 200 or so possible requests you can make.

[00:08:06] You can-- Like some of them are support GET and POST or GET and PUT, something like that.instead of having to go through that list and for each one manually develop this like data structure of the possible responses and, and the types and all of that, I've been able to just throw AI at it and be like, "Here we go.

[00:08:24] Look at..." You know, you can trace this back to a database query or an ORM call if you want. Like how... whatever you need to do, generate the OpenAPI. This is the schema thing that you're supposed to fit. Just do it. And it was like really good for the first, first pass. And I had, you know... A- and then, I added some linting stuff to Taffy too, so it'll like, after it's generating your OpenAPI spec, now it can validate the generated OpenAPI spec.

[00:08:48] So if you have a resource that is poorly documented, right, it's not spitting out good stuff, or if it's, you know, using uppercase key names where they need to be lowercase or something like that, it can warn you about that sort of thing. So that's kind of nice.

[00:09:03] **Ben:** Yeah. I feel like I vaguely remember working on some sort of a Swagger document implementation I don't know, like the early days of InVision, and just getting through it manually and the whole time thinking, "Does anyone even need this? 'Cause this is awful." Like, like maintaining this and then designing semantic domain models and then, like, you could get things that extend to other things and then add their own keys, and it's like this is a type of this kind of other thing.

[00:09:31] It was almost like for

[00:09:33] **Adam:** Yeah. Oh man, when, we finally hit the singularity and the AI, like, takes over and, and, and punishes me, it will not be for all the cursing at AI that I do. It's gonna be for making it write all this nasty JSON

[00:09:48] **Ben:** Oh man. Sounds tedious, but, sounds like it won the client, so

[00:09:53] **Adam:** Yeah, yeah. So we landed that client and, I've been, you know, I still think it's dumb, the whole OpenAPI thing, but dumb things can have their place, I guess

[00:10:05] **Ben:** Solid

[00:10:06] **Carol:** check

[00:10:06] **Ben:** at the end there

[00:10:08] **Adam:** Yeah. So that's what I got going on. what do you got going on,

## [00:10:11] Ben's Triumph: The Transactional Outbox Pattern

[00:10:11] **Adam:** Ben?

[00:10:12] **Ben:** I will go with a small triumph, which is the other week, maybe two weeks ago, I had brought up the idea of adding the transactional outbox pattern to my blog. And just the, the, you know, the high-level overview of what that means is when you're communicating with an external system, you're essentially introducing points of failure, that when you're dealing with data locally, you have your database transactions to atomically either make several things happen or have all of those things not happen kind of one unit of work. the moment you have to talk to an external system, you now get like, well, what if the server crashed here? And what if the server crashed here? And what if the server crashed here? And all these questions about

[00:10:56] **Adam:** Yeah

[00:10:57] **Ben:** So the outbox pattern is that instead of going directly to the external system, you, within the bounds of a single database transaction, you write a message more or less to a local outbox database table so that it gets committed atomically. And then you have some sort of background process that's just constantly trying to flush messages out of that system, and that's where you push them to the external, services. Which in my case is just Postmark. It's an SMTP server. Well, I guess it's a mail server that you can access either via SMTP or I'm old school. Well, lazy, so I just use SMTP, which feels like... Some-somehow when there's an SMTP version and an API version, when you're using the SMTP version, it just feels dirty. Like, God, are you really still using SMTP when you could be making an API call? But, but I, I finally got that in place and, uh, I didn't need it at all.

[00:11:58] It was, you know... I have always just sent out emails directly after things happen on my site, and my site is not mission critical, and it's low volume, and I've never once had an issue with the actual sending of the emails. This was just kind of a funsies, expand your mind, kind of play around with new ideas.

[00:12:18] And, um I finally got it in place, and it seems to be working really well. So it took me a week or two to get there, but I'm happy I got there

[00:12:27] **Adam:** So not to be shitty,

[00:12:28] **Ben:** No,

[00:12:29] **Adam:** I just, I, I just wanna question you, and it's probably gonna feel like pushing back, but, it's more for my own understanding. So based only on the way you described it there, I wanna ask you what the point is of using a database transaction. To, to wrap a single, row insert in a transaction seems like a waste to me

[00:12:50] **Ben:** Right. So it's, it's not a single row. So if you imagine-- So the, the use case here is for someone posting a comment on a blog post, and then I have toa kind of fan-out of emails to everyone who's subscribed to that blog post. So it might go just to the person who posted the comment, 'cause that's...

[00:13:10] Well, it alway- I always get auto-subscribed to all comments. So if you come in and you leave a comment, at the very least, it's going to you and it's going to me.

[00:13:20] **Adam:** Yeah

[00:13:21] **Ben:** also be going to N number of other people. So what would have historically happened is you would have left the comment, and in the transaction,

[00:13:31] **Adam:** Mm-hmm.

[00:13:31] **Ben:** I would have written the comment, I would have subscribed you to the post, and I would have subscribed me to the post.

[00:13:37] So there's three records more or less happening there in that transaction. So that either all happens together or it all fails together.

[00:13:44] **Adam:** Mm-hmm.

[00:13:44] **Ben:** Then once the transaction would have ended, I would have said, "Okay, let, now let me go and get all the people who subscribed to this blog post and send an email to them." And that's outside the transaction.

[00:13:54] **Adam:** Yeah

[00:13:55] **Ben:** So if at any point the server crashed after the transaction, the records would have been saved, which is the mission-critical part, to be fair, but then maybe no emails would have gone out, or maybe three out of seven emails would have gone out before the server crashed, and then I lost, you know, the last four. So with the transactional outbox pattern, of sending the emails directly after the transaction, I actually just write a, like, Adam left a comment message in the outbox, and that's part of that same transaction. So you come in, you leave a comment, and in the same transaction, I do, "Adam left a comment," "Adam is subscribed to this thread," "Ben is subscribed to this thread," and here's the notification that Adam's gonna send out. So that all happens then atomically. So it's like four records that could happen, that get written atomically.

[00:14:45] **Adam:** Okay

[00:14:46] **Ben:** And then in a background scheduled task, I just have something going, you know, looping essentially and saying, "Are there any messages in the outbox?" If there are, "Oh, here's the one that says Adam left a comment."

[00:14:56] So now I go and I send the emails out.

[00:14:59] **Adam:** Okay. So they, adding a subscriber, basically is queuing you up to be sent when the next tick of that job happens.

[00:15:09] **Ben:** Yes, exactly

[00:15:11] **Adam:** And then what is the point of that last record, the, the like notification record you were talking about? Like, I left a comment

[00:15:16] **Ben:** the message. So that's, that's the thing that gets read on the background task. So the background polling essentially says, "Is there anything on the queue?" It pulls off that Adam sent a message, and then I essentially send out the message, and then I-- or send out the emails, and then I delete that message,

[00:15:32] **Adam:** Okay.

[00:15:33] **Ben:** so

[00:15:33] **Adam:** Gotcha

[00:15:35] **Ben:** and the delete never happens, then technically the next time the task runs again, it'll possibly send

[00:15:40] out duplicate emails

[00:15:42] **Adam:** Interesting. Okay. What would happen if Adam and Carol both left comments prior to the next comment notification job tick?

[00:15:56] **Ben:** So in my case, because I'm running on a single ColdFusion instance on a single server, they would just get sent out one after another. But in theory, you could have a situation where you had like multiple workers all consuming from the queue. You know, there's no guarantee that they... I mean, there's a

[00:16:16] **Adam:** Beep out

[00:16:17] **Ben:** that like one gets pulled off before the other, but there's no guarantee that they get processed in the right order,

[00:16:22] **Adam:** Mm-hmm.

[00:16:22] **Ben:** which I think is like the difference between a message queue like RabbitMQ something like Kafka, which Kafka has like guaranteed order processing, whereas

[00:16:36] **Carol:** Hmm.

[00:16:36] **Ben:** like RabbitMQ just has like

[00:16:38] **Carol:** It's, it's

[00:16:39] **Ben:** messages.

[00:16:40] **Carol:** Yeah. Yeah. Yeah.

[00:16:42] **Adam:** They'll deliver them to you in the same order, but they-- the processing is not yet

[00:16:46] **Ben:** But every

[00:16:46] time someone tries to explain to me how Kafka works, I'm like, "Can you repeat "That

[00:16:52] **Adam:** Yeah.

[00:16:53] **Ben:** doesn't make any sense. Can you say that again?"

[00:16:55] **Adam:** Hang on, let me take some

[00:16:57] **Carol:** was a thing. Yeah

[00:16:59] **Ben:** I think it's, I think it was created by LinkedIn, and I think it's, like, how their entire system works.

[00:17:04] **Adam:** I think you have to be on mushrooms to understand it

[00:17:08] **Carol:** We are, uh, we're RabbitMQ, and we're Azure Service Bus to do all that, so. The, the easiest way for me to ever explain to my del- developers, like, how our outbox works is I go, "It's a queue. It sits there until something consumes it. If the consumers are down, the, table just builds and it builds until something says, 'I'm good.

[00:17:29] I can take your message now.'" I was like, "So don't think so much about what the framework is or what it's doing. It's literally just a queue waiting for things to take it off the table."

[00:17:40] **Adam:** Nice.

[00:17:40] **Ben:** so the way I s- I say it in my mind is it's a queue that's on my machine as o- as opposed to a queue that's on your machine kind of

## [00:17:46] Adam's SQS Queuing War Story

[00:17:46] **Ben:** a

[00:17:47] **Adam:** Yeah. I have a fun little queuing story I can throw in here if you guys wanna hear it.

[00:17:52] **Ben:** it up

[00:17:53] **Carol:** Yeah, let's do it

[00:17:54] **Adam:** uh, we use SQS, Amazon SQS to, process, warehouse table imports. So a big chunk of the data that we use on a day-to-day basis needs to be synchronized, and it's a, and it's a lot of data, right? So a customer will send us all told between, on average, maybe 10 files.

[00:18:13] It might be two gigs of data that they're send-sending us every day, and it's the same data. It's just like

[00:18:20] **Ben:** Right.

[00:18:20] **Adam:** of it changed overnight.

[00:18:22] **Ben:** Right. Everything plus what changed yesterday

[00:18:24] **Adam:** well, but it's, it's like the, the data from yesterday, but there's, there might be two new records and four overwrites, you know, with, with changed, you know, I, I updated my address or whatever.

[00:18:35] Anyway, and so but we have to process that, in a way that's, you know, robust and, and efficient and... At the end of the day, we're using queues, right? So we, they send us, they send their files up to S3 for us, and then they send us a webhook to say, "Okay, the file's available, and this is the job you should run, and this is the file name."

[00:18:54] and we put that into a queue, and then there's just a, a limited number of workers that will work on those, right? And they, they take the file off S3, and they import it. And at, at the end of the day, what it's doing is like a load data into, you know, from the file, right? In, in MySQL. We had one customer who, like, rewrote their, process where they're sending us these files, and for whatever reason, there was a bug in it, and it was accumulating.

[00:19:20] So we got a, we got an alert one day that there were, like, 40 messages in the queue that had been there for more than 15 minutes or something like that. It's like, okay, that's, that's weird. it's an anomaly. It's not a big deal. You know, I could see where it spiked real quick, and then it was starting to trend down.

[00:19:36] I'm like, okay, whatever, you know, maybe we've, we've onboarded a bunch of new customers. Maybe it's just this is the new normal, right? You know, maybe three customers all decided to push at the same 6:00 a.m. or whatever, and didn't think too much about it. And then the next day, the number went even higher, and then the next day, the number went even higher.

[00:19:56] Like, okay, this is becoming a problem very quickly.

[00:19:58] **Carol:** Right

[00:19:59] **Adam:** I started digging in, and eventually what I figured out was this one customer, you know, like on day one of this problem, they sent their files. On day two, they sent the files from day one plus the files from day two. On day three, they sent the files from day one and then the files from day two and then the files from day three.

[00:20:13] And I'm like, okay, hang on. So, uh, that's why. Now, fortunately, we do like a FIFO queue, right? First in is first out, and they were sending them in chronological order. So, you know, I talked about this is the same data, and we're just overwriting it every day. So if, if they had sent us in like in reverse chronological order, then they would be sending us old data that we would like now be out of sync, right?

[00:20:38] We would, we would sync today's data, and then we would sync yesterday's data, and then we'd sync two days ago data. And so the data you're looking at in the system today would be the two days ago data. But fortunately, that was not the case. So they got lucky there. and I, you know, I, I sent them the logs of their API request showing, okay, this is the file name, and fortunately, they put the, the date that the file was generated in the file name.

[00:20:59] So I could be very clearly like, "Okay, here's the request timestamp where you called our API, and this is the file name, and I can show you, okay, today you sent three, yesterday you sent two, day before that you sent one, and it's the same files over and over. You're just adding the new one." So, they were able to get that cleared up the next day and all was good.

[00:21:15] But you know, fun little queuing adventures

[00:21:18] **Ben:** Yo, and isn't it interesting, so FIFO,

[00:21:20] first in, first out, every now and then there are things that I learned about in school in a computer science degree, and I'm like, "Oh, that's an interesting fact, but nothing I'll ever use." And then, and then every now and then something like this just pops up and you're like, "Oh yeah, okay. I see how that's useful." FIFO is one of those things that turns out to have... Like when I think about little data structures, like, oh, I have an array and I'm pushing things on and I'm popping things off, and I'm shifting and unshifting, like it always just feels not arbitrary, but like not in, not meaningful.

[00:21:53] But then things like this, you're like, oh yeah, there's actually real meaningful data integrity reasons you do certain algorithms

[00:21:59] **Adam:** Yeah,

[00:21:59] for

[00:21:59] sure. Yeah, the, the... It's almost like they knew what they were talking about in computer science classes in school

[00:22:06] **Ben:** Oh my God. Sorry, just like one, one small note. When I was in school, you know,

[00:22:10] **Adam:** Ding.

[00:22:11] **Ben:** there, are people there are people like me who I think kinda just struggled through school. Like, I did well in school, but 'cause I worked hard and, like, nothing ever really made sense to me, and some classes I did really poorly in, and some classes I did pretty well in. And then there were the people who, you know, from my perspective, it's like everything just seemed so easy, and they just got stuff. And I remember I came out of a computer science class one time and I, and I was complaining to this guy who was one of the, you know, like, the nerdy guys who just got it.

[00:22:44] And I was like, "Oh, this is so stupid. Like, why do we have to learn all these algorithms? It's so ridiculous." And he was like, "Well, you need to learn the algorithms so that you can eventually one day create more effective algorithms to build on top of." And I was just like, "No, bro, we're venting. not learning right now, we're venting.

[00:23:00] That's what this conversation's about." Oh. Anyway, that's my triumph. So okay.

[00:23:09] **Carol:** were in the

[00:23:09] **Ben:** Yeah. Carol, what do you got

[00:23:11] going

## [00:23:11] Carol's Wins: The Savannah Move and Postman Stress Testing

[00:23:11] **Ben:** on?

[00:23:13] **Carol:** Oh, man, I'm gonna go with two wins. All right. So first, I've moved, and we're settling in,

[00:23:19] **Ben:** yeah, congrats

[00:23:21] **Carol:** Thank you. Thank you. I am unpacking boxes, even if that means I'm just moving them to new boxes.

[00:23:28] **Adam:** Yeah

[00:23:29] **Carol:** So for instance, in my office, we had, In my old office, I had an entire closet, which was great for things like, oh, those routers I was gonna get rid of one day and I never did, and all of the extra USB cables and that extra camera I don't use anymore. So now there is a black, like, I don't even know what they're called, those big giant storage bins, like, that you use for

[00:23:56] **Ben:** Yeah.

[00:23:56] **Carol:** you use in your attic, sitting in the middle of my floor, and everything that's technology that isn't currently in use is going in that bin. When the bin is full, something has to come out or what's in my hand is going in the trash.

[00:24:10] Like, we have to have an agreement here. This is the limit of technology I can carry with me from house to house now. I've reached my quota. So we're unpacking just to move some things to other boxes, but that's okay right now. We're, we're accepting the defeat there and gonna call it a win.

[00:24:29] **Ben:** Let me ask you this. You've moved from Georgia to Texas to Georgia

[00:24:34] **Carol:** You forgot Arizona D Arizona.

[00:24:36] **Ben:** Arizona, right. So i- i- is there a, a box that was packed in Georgia made it to Arizona, Texas, now back to Georgia without having ever been unpacked

[00:24:53] **Carol:** It sure is. It's called the baby Christmas box. It's things that were from my, like, childhood that are still in the Christmas box that have never been unwrapped. It has four different color stickers on it now because it's been moved four times. They just recode it every time. This time the guy went through and he's looking at all of our stuff, and he's like, don't see any blue stickers."

[00:25:18] And I was like, "I don't think we have blue stickers." So now everything has blue stickers plus everything we never took off from the last moves.

[00:25:27] **Ben:** Yeah. Amazing

[00:25:29] **Carol:** like they box all your stuff up, and they put these inventory stickers on the boxes or on the stuff that they're moving. So over years of moving, like we have ones from, my husband has Germany, Colorado.

[00:25:40] He has so many on a lot of our furniture. If you flip a kitchen chair over, there's so many stickers under it 'cause we forget to take them off 'cause you don't see it. So then when they unpack it, you have... I had-- We had 41 pages of inventory. You have to

[00:25:53] **Ben:** Oh my goodness

[00:25:55] **Carol:** make sure it arrived at your house, and then you have to list what didn't make it to you. So we have blue for this move. Blue is our sticker, so we'll, we'll slowly get rid of them.

[00:26:07] **Ben:** Nice.

[00:26:09] in this place for a while now

[00:26:11] **Carol:** Yeah. We, uh, we're gonna keep our fingers crossed for it. I think we're gonna enjoy Savannah. It's a little different, but it's close enough to home and family that we have good things around us, so that helps. But I also wanna throw out a technology win.

[00:26:27] **Adam:** Ooh

[00:26:28] **Carol:** guys know you can stress test your APIs? Have you looked at this?

[00:26:34] **Ben:** No.

[00:26:35] **Adam:** Oh.

[00:26:35] **Ben:** I thought

[00:26:36] **Adam:** I stopped using Postman a while back. Yeah

[00:26:38] **Carol:** Yeah, so I kind of got-- I kind of stopped too, but then when I was doing some new integration with some other vendors and then with some third-party stuff, it, it came back up on my plate, and I was like, "Oh, Postman's really handy just to learn, like what their endpoints are doing and better understand the data and what's being returned without needing to code anything."

[00:26:57] I can just grab their specs and go, "Hey, let me pull up their auth endpoint. Let me see what they're looking for. Let me see what projections look like so I better understand before I even start development." I found out that they have a runner process in there that you can then simulate either just straight requests to your endpoint or you can simulate like virtual users. So I had an endpoint that was not doing so well in production, and it's like a PDF generation process, and I went through

[00:27:24] **Ben:** Classic

[00:27:26] **Carol:** PDFs, right? Every

[00:27:28] **Ben:** So heavy

[00:27:29] **Carol:** bad. So I went through and like just did a stress test on my local and then grabbed a dump of my memory and I was like, "Oh, well now I can actually see what's going on with it." But I was like, "Whoa." I was like 20 virtual users and let's just do a peak for like five minutes and they're gonna have all these like sessions at the same time, and while it's hitting the same endpoint, all I was doing was hitting the error endpoint to make sure things looked good at first. And I was like, from there I could just see where we had like a, a small memory leak.

[00:27:57] But then when I got to the PDF generation, I was like, "Oh, look what I can find

[00:28:02] **Adam:** The choir of angels

[00:28:03] **Carol:** test this." Yeah, but I was so happy 'cause I felt like Postman is one of those things, like you said, I quit using it. Like I

[00:28:10] **Adam:** Yeah

[00:28:11] **Carol:** dropped off. I was like, "It's not really helpful for me anymore," and now I'm back to being a fanboy.

[00:28:16] I'm like, "Let me get back on this bandwagon."

[00:28:18] **Adam:** Nice.

[00:28:19] Yeah, I started using one called Thunder Client, It was like an extension for VS Code. and if I'm not mistaken, Postman was, like, switching to an unpaid-- or I'm sorry, s-switching to a paid model of some sort, um, and that kind of turned me off.

[00:28:37] **Carol:** and teams and stuff. Yeah, but for just for my own, it's still found, it's still

[00:28:41] **Adam:** gotcha

[00:28:41] **Carol:** as I'm signed in, I can still store everything locally, but

[00:28:45] **Ben:** Yeah

[00:28:45] **Carol:** force you into their cloud storage. But, you know, I just sign in and like it's cool for what I'm doing. I'm not putting

[00:28:51] **Adam:** Yeah.

[00:28:51] **Carol:** out there

[00:28:52] **Adam:** Well, to bring it full circle, I'm almost certain that in Postman you can import an OpenAPI spec and have it,

[00:29:00] **Carol:** Heck yeah

[00:29:01] **Adam:** easy to interact with your API.

[00:29:03] **Carol:** And look, look who's been doing this work

[00:29:06] **Adam:** Yeah

[00:29:06] **Ben:** Going full Spider-Man, Spider-Man, you know, like pointing meme here

[00:29:10] **Adam:** Everybody pointing at each other, yeah

[00:29:12] **Carol:** I love it

## [00:29:14] AI, Curiosity, and Becoming a Craftsman

[00:29:14] **Carol:** Well, on that note, I wanted to talk a little bit more about the whole outbox pattern stuff. Not about the outbox pattern itself, but because I had to go through, let's call it some mental gymnastics during the course of learning how to use the outbox pattern

[00:29:31] **Adam:** Not mental gardening? Based on, what was it, last week's show?

[00:29:36] **Ben:** to get my mental models in place.Um, keep your mental garden walled off

[00:29:42] my issue here is this: I had, I had heard of the outbox pattern, right? This is why I wanted to use it, because I knew of it, but I had never implemented it myself. And I knew that at the end of the day, I could just ask Claude Code, "Hey, look through this application, look at the points of failure with the emails.

[00:30:04] I wanna do an outbox pattern. up with a table schema, make sure that the tables get written to transactionally, and then come up with some sort of scheduling thing in the background that will do this and, and make me happy."

[00:30:17] **Adam:** Make no mistakes

[00:30:18] **Ben:** and make, yeah, m- u- use best practices, make no mistakes, right?

[00:30:21] Introduce no bugs.

[00:30:22] **Carol:** everything

[00:30:24] **Ben:** So, you know, I don't have a single test. But whatever, that's aside.but like, I wanted to learn more about how the outbox pattern works. So, first what I had to do was I had to get a scheduled task in place, I didn't have any scheduled task running on my site. one of the ways that I've really been finding AI to be helpful is kind of on the outliers of a, of a project. At the very beginning, I like to talk through the problem, get a sense of how it might work, get a sense of where my blind spots are, get a sense of where the complexity might live. You know, just help me think through the issue. Then I like to do the work myself, and then at the end of the task or the project, I like to go to, to Claude Code and say, "Hey, look at all the changes that I've made.

[00:31:10] This is the kind of stuff I'm trying to work on. Is there anything here that I didn't consider? Or, you know, did I introduce any bugs, or are there any points of efficiency that I might be able to address?" So that's how I use it. So, kind of along this line, I have to put my scheduled task in place, and I say, "Hey," I've implemented scheduled tasks like a billion times in my life.

[00:31:29] Then I go to Claude Code and I say, "Hey, can you just take a look and make sure that there's nothing here I haven't messed up?" And it says, "Oh, yeah, this should work, but the scheduled tasks are based on URLs, and technically the URL is accessible publicly even though you're locking it down by local host IP address."

[00:31:44] But like the, the JRun server under the hood or Tomcat or whatever it is, like, if the XML configuration pulls the X-Forwarded-For header and puts it into the CGI remote address, then technically someone could spoof the local IP address, and you're checking on IP address. It could technically still be publicly accessible. It said, "Really, what you should be doing is using something like basic authentication here as a, as like a last mile belt and suspenders." My Claude Code loves to use the term belt and suspenders, uh, security protocol. So I'm like, "Okay, it's been a million years since I've done basic authentication. Let me remember how I do that."

[00:32:20] And then I started to write the code. And then once I had that in place, then I had to start work on the outbox stuff. And I said, "Okay, well help me think through how the database schema should work." it does all this stuff about like, "Oh, well you need to be able to claim messages, and you need to be able to expire messages, and they need to be claimed until...

[00:32:38] And, and like what happens if you have 10 workers all consuming from the queue?" And I'm like, "That's stupid. That's not how this application needs to work." So I'm going through and like I'm, I'm, I'm really trying to do the work because I'm trying to familiarize myself with how the pattern gets applied and what the pattern means. And I'm trying to build up, you know... I use the phrase mental models all the time because really that's what I'm trying to do. I'm trying to build up mental models then do the work, so then I have the muscle memory, if we're gonna just continue to make awesome phrases, for how all of this stuff fits together. And like I love working like that because I feel connected to the code. I feel like I understand how the code works. I feel like I understand how the application works. I feel confident that I'll be able to maintain the code going forward. But I know on some level that's just like old Ben trying to hang on to old grumpy Ben lifestyle, and I could have just asked AI to do all of that, and I probably could have knocked it out in two hours instead of two weeks. You know, not two continuous weeks. This is, you know, my side project. found it very rewarding. Now, I will also say that I'm trying to tweak other parts of my blog to get Parcel JS to work well with ColdFusion. Parcel JS is like a JavaScript and other static asset bundler. You know, you point it at a HTML page, and it just kind of hashes a lot of stuff together and outputs JavaScript and CSS files and, and CSS maps and all that kind of stuff. And

[00:34:10] **Adam:** But it does it through like spidering, right? Like all you have to do is give it your HTML and yeah

[00:34:14] **Ben:** But the thing is, like, that really works great if you have a static site, but I have a ColdFusion site, and you can't really point it at a ColdFusion page and say, "How does this work?" 'Cause a ColdFusion is, you know, dynamic.

[00:34:24] **Carol:** Dumb.

[00:34:25] **Ben:** Yeah.

[00:34:25] **Carol:** yeah, dynamic. Yeah.

[00:34:29] **Ben:** So, I'm helping... I'm getting Claude Code to help me figure out how to get Parcel JS and ColdFusion to play nicer together. And, like, this kind of thing I really just don't care about. To me, this is just a mechanical problem. It's about understanding the API for Parcel. It's about understanding where the friction points are and how it can just work better. And, like, I don't really care that much. It doesn't really mean anything to me. So I'm definitely leaning on AI a lot more here and just say, "Hey, y- you know, if you need to write a plugin for Parcel to make this happen, do it, and I'll take a look at it." But it's not like... I'm not, I'm not using the come up with a plan, and then I'll do it so that I understand how this works the best.

[00:35:10] I just don't care that much. So I'm already living in two different worlds. One is where I just don't care that much, AI can do it, another world where I actually still do truly, deeply care about how this code works, and I'll use AI to help me think about it. But I'm still doing most of the writing of the code and feeling the friction and the, like, I see that you wanna do this, but I don't think that makes sense for this application. Maybe it's a deferred decision that we can make, and I don't need it now, even though it'd be easy to write now. I just don't think it's worthwhile." Where, like, I'm enmeshing myself, I'm marinating myself in the luxurious juices of ColdFusion. And, I don't know. Like, I- I'm, I'm just always so conflicted about whether or not that makes sense or if it's me just refusing to evolve. Does that make sense?

[00:36:05] **Adam:** No.

[00:36:06] **Carol:** It does. I, it, okay, it, it does to me. It does to me a little. I'm glad that you're embracing that there are things that you don't care about and that you can say, go work," right? Like, "Just go do your thing. I don't care that much about it." But you do have this part that you wanna understand, that you wanna get the concept, that you still wanna be, like, involved in the build-out and the full, like, design. To me, that's the piece I still enjoy too. So I will send it through on bugs and I'm like, "Just go fix the bug." Like, I don't even really know the ins and out of this application. You figure it out, find where it doesn't work, and then we'll talk about it. But when I'm talking about full new feature development, I want to be the owner of that architecture still. Like, I want to know how it's operating. I wanna understand it because in the long run I'm gonna support it. It's not gonna support the problems down the road. It may fix a bug, but if it crashes the server, that's gonna be on me. You know? Like, I have to make sure fundamentally it's still correct. So I don't think it's bad to be like, "I wa- I wanna learn.

[00:37:13] I wanna know." AI's taken away a lot of that from us, the get to learn part of it, because it's made it so easy to just have answers at your fingertips that you're sometimes expected to just trust because it sounds so sure of itself that it can't be wrong. And until you challenge it, do you realize that your pattern might not be the best decision for this

[00:37:37] **Adam:** And to be clear, when I said no, that it doesn't make sense, I was just being a troll.

[00:37:42] **Ben:** Yeah, No, I know. I know.

[00:37:43] **Carol:** You're a

[00:37:43] jerk. You're

[00:37:44] **Ben:** And but so, so here's, here's the interesting thing, This is the hard, the part that's hard to reconcile with what the world thinks about AI. So when I first started playing with AI in the context of my blog itself, like what I mean is like in the actual code of the blog and using it to maintain my blog. I said things, I tried to approach things like, "Look through this code and find places for optimization. Look for this code and find, you know, bugs and how can we fix it? Look for this code and find places where we can make it more robust or improve efficiencies." it's not a, it's not a huge code base, you know.

[00:38:22] It's like, I, I don't even know, dozens of files, maybe, maybe 100 files or something.and at no point did it ever say anything even remotely resembling, "Oh, by the way, there's points of failures here where if your server crashes, you'll never send out notifications." The only reason that I even went down this rabbit hole is because I knew of the outbox pattern, and I felt like it could be applied, and I wanted to apply it here to, again, mostly just scratch my own itch.

[00:38:53] But mechanically, it makes sense. It does create a more robust system.

[00:38:57] **Carol:** Is the term resilient too? Like, is that

[00:39:00] **Ben:** Yes,

[00:39:00] **Carol:** Like, it's

[00:39:01] **Ben:** 100%.

[00:39:02] **Carol:** Like, that's the thing we look for, is something that can survive if a service is down. That's what we want our application to do. We want it to respond when things come back online, and just having something go into the ether.

[00:39:14] Like, RabbitMQ really resilient. If it crashes, you kind of lose stuff. So that's why we love the outbox, is because I have that resilient pattern that says, "I'm gonna hold you until things are ready, and when things are ready, we're good."

[00:39:30] **Ben:** Right. So it's-- The, and the, and the point I was driving it was that the only reason that I knew that this pattern existed is because of professional curiosity. You know, I've probably... It, it was probably in, like, the "Enterprise Application Patterns" book by Martin Fowler, or is, you know, I've heard it talked about on podcasts, or I've heard it talked about in Clean Code.

[00:39:54] Or like, I'm, you know, like I'm-- There's like I'm trying to become a craftsman. This is one of the concepts that I've come across. And, and again, like, Claude Code didn't suggest adding this. I suggested it because of everything that I've been exposed to. My concern is that if I stop trying to expose myself to stuff, that I won't think to suggest things in the future, whether it's some new pattern or some new type of database or some, you know, paradigm or whatever. If I'm constantly just, "Hey, AI, do this for me," at some point I just, like, the well of ideas runs dry. if AI doesn't think to suggest it, which again, in this case, it never suggested that I actually do this,

[00:40:43] **Adam:** Mm-hmm.

[00:40:44] **Ben:** then I won't know to suggest those things. And so that's why I constantly feel like I need to have my hands a little dirty so that I build up the, the residue of ideas so that I can then use them going forward.

## [00:41:02] Treating Agents Like Employees

[00:41:02] **Carol:** I also heard recently at work a term that scared me a little, is that we should be treating agents as employees. And when I heard that term, it made my stomach a little like, "Ooh, I don't enjoy this," because it suddenly makes me feel replaceable. if I'm not challenging the AI, if I'm not challenging the agent, if I'm not making things better, then it's just gonna be subpar. It's gonna be what the standard is right now. It's not gonna be something that can be maintained down the road, and I feel like in order to have value for my job, I have to constantly be learning the technology that's best suited, even if AI that

[00:41:47] **Adam:** Yeah. I've, I've heard similar rumblings. it's interesting the way that you took that feeling, and I, I, you know, I have to say I agree when I think about it in that light. But the first thing-- The first place it took my brain was more like treat it as an employee in the way that I would prompt, a, a, an employee to get some work done, right?

[00:42:10] Like... A-and even this goes partly to the discussion earlier about,like how I interact with the LLM to get work done and, and in some ways, sometimes it's like I wanna hash out a plan, right? I want you to talk to... Like, here's the, here's the goal, here's the outcome that I want, and how... Make a suggestion for how we get there.

[00:42:31] And sometimes it's like, "Here's a stack trace, go fix it."

[00:42:34] **Carol:** Yeah

[00:42:34] **Adam:** To the point where now when I get a stack trace, I don't... I-- No preamble, no postamble. I just paste it in the stack trace and hit enter,

[00:42:43] **Carol:** Oh,

[00:42:44] **Adam:** and it, it, it knows what to do with that. I'm like, "Okay, cool."

[00:42:48] **Carol:** Yeah.

[00:42:50] **Ben:** Well,

[00:42:51] **Adam:** And, I'll say too, so in our local development environment, we have the error page disabled, right? So like with a lot of app servers, you have a, a page that you display when there's a server error, right? Like you might log that to your exception logger, but you don't want to show the end user the error message and the s- the whole stack trace.

[00:43:07] That's A, not a good experience, and B, kind of a security leak potentially. And so in our local development environment, to save having to like wait for it to land in the bug log and go pull it out of the bug log and look at it, we just have the error page disabled, and you see the stack trace on the page, right?

[00:43:22] I wrote some code on our local dev version of the error page that takes the stack trace and removes any lines that don't reference a CFM or CFC file so that it's only the relevant lines of the stack trace, so it's fewer tokens that I'm feeding into the LLM

[00:43:40] **Ben:** None of that .java class

[00:43:42] **Adam:** Exactly. Yeah

[00:43:44] **Carol:** Yeah, like in App Insights, you can click the Just My Code part, and it shows you just the relevant stuff to actually your application and the weight kind of gets reduced

[00:43:54] **Ben:** You know, I will say, and, I think this is just also where the industry is focused right now, so I'm, I'm not saying that this is entirely AI's fault. I think this is... It's just of a time everyone's talking about AI. But I also feel like in the last several years, I've just been exposed to fewer ideas. I feel like I used to hear a lot more conversations about a lot more different types of things, trying new stuff, people experimenting with new databases, people just, like, totally trying to come at existing problems from totally new perspectives, I feel like I don't hear any of that anymore.

[00:44:33] And part of that is probably my fault. I'm not being proactive about just randomly reading stuff about technology. you know, I used to read more books. I feel like books aren't getting written as much, or maybe they are, and I just don't know because I'm being lazy about it. But like, there's just even, like every podcast, you know, including ours,

[00:44:54] **Adam:** Yeah

[00:44:55] **Ben:** so AI-focused right now that I just feel like not only am I struggling with the idea that AI making me less curious, I guess. I'm also just feeling like people in general, at least, symptomatically, you know, what I hear and what I've been seeing people talk about feels less curious also. And that also feels very... Again, like, it's like I don't know if that's a problem. That's a problem if it's me from 15 years ago because your ability to evolve as an engineer was based on your exposure to stuff. And I, and I, I'm just constantly wrestling with whether or not it still matters. I still think it does matter, but I'm also just not sure if that's me or not

[00:45:41] **Carol:** I think curiosity's gone. I feel like the problems being solved are different. So we have a whole bunch of new people coming in to where I work, right? So like we've had a bunch of new tech force hires. There's entry level people coming in. The curiosity is there, it's just being solved in a way that we didn't solve it. So their approach is different. So instead of being in a book or even on Stack Overflow, they're just going to another spot that's giving them an answer slightly differently and slightly faster. Actually, probably substantially faster. But I don't think they're less curious. I think they're just as curious and they wanna understand.

[00:46:20] They're just consuming the information differently than you and I did

[00:46:24] **Adam:** I wanna yes and what Carol said, which, so yes, and then also I think that the just sheer volume of stuff, of content to consume, of people applying for jobs is just up. The numbers are through the roof all across the board. And so it takes more work to separate the wheat from the chaff, and find the curious people when you're hiring.

[00:46:50] And, like when we were, we were talking before we started recording about, wearing headphones for meetings and stuff. When I send out invitations for, for, for like a interview, right? To, to interview somebody to potentially hire them, in my invitation, I always make it a point to say, "Please wear headphones and be prepared to appear on camera."

[00:47:13] and if the person is not wearing headphones, if I can hear like myself feeding back through their laptop microphone, that is like you, you've basically given me a 70% reason to not even consider you, right? Like that was... It, it's a very brief email. There's like three sentences. Here's the link. This is the date and time.

[00:47:32] Please be, please wear headphones and be prepared to appear on, on camera. If you can't follow those simple instructions, why should I consider you as an applicant? So

[00:47:43] **Ben:** It's the green M&Ms and the,

[00:47:44] **Adam:** Yes.

[00:47:45] **Ben:** the rider

[00:47:45] **Adam:** And the writer

[00:47:46] **Ben:** All right. Well, I know Carol, you had some stuff you wanted to talk about. I don't wanna

[00:47:50] **Carol:** yeah.

[00:47:50] **Ben:** the time here

[00:47:52] **Carol:** two. I'll, I'll go to the first one 'cause I feel like it kind of goes along with what you're saying. w- I found a problem at work, and a problem in our process, a problem with kinda how we operate, and it's our Zendesk integration and

[00:48:05] **Adam:** is customer service, right?

[00:48:07] **Carol:** Oh, yeah, it's the tier three triage when things need to come to a developer.

[00:48:12] That whole process of something's broken the system and go figure it out.I realized real quick that we weren't doing a great job of fixing root problems. We would fix reoccurring over and over again. And since Zendesk, or I was called the help desk, since the help desk's assignment was just passing along to another developer every week, you know, you forget what you worked two months ago when it's your rotation again, so you fix the same problem again too. So I started reviewing what we're doing, you know, and, and taking note of the problems that reoccur. And every Thursday now I meet with the team that is currently on Zendesk and the team that's transitioning into it, and we go through what got worked, what looks like patterns, what is a one-off, and what's being handed off, the things that we didn't even start yet. And we kinda get an understanding of what it's gonna look like, you know, in the rotation coming up. while I was looking at the handoff process and looking at the things that reoccur, I've just started opening, opening like technical stories in our backlog that say, "Reoccurring help desk ticket." For example, this application, for whatever reason, allows duplicate submits.

[00:49:30] So maybe you have two tabs open, maybe you submit fast, maybe there's a network issue. The submit actually inserts double records of a question-answer, and the problem is down the stream, nothing understands how to handle two responses, so then everything just breaks. Like, you can only have one answer.

[00:49:52] Everything's been coded to say, "What is your answer?" Not, "What is your first answer? What is

[00:49:57] **Adam:** Right

[00:49:57] **Carol:** answer? What's the answer in the middle?" So I've just started opening these z- ADO like technical stories that say Reoccurring issue, through AI, determine its suggestion on how to fix this. you like it, implement it.

[00:50:15] If not, figure out a new route, like analysis for this. So far, they've been really good. I will say the bug hunting is way better than the feature development, in my opinion. So the request thing, the request thing, it was like, "This is a common problem. You're loading the data and then you're submitting it.

[00:50:34] You're not doing a check to see if the data's changed, and you're not doing a merge into the database. So therefore, both submits just assume the data needs to be created." And its first suggestion says, "Oh, we'll create a constraint on the database." I was like: Hold up. That's not a good idea, 'cause all we're doing is just passing the error down the road. 'Cause now I've just said, "Oh, you can just go to the database, and now I'm gonna error on you and say duplicate key constraint instead of fixing the core issue." So I fed that back and it goes, "Oh yeah, you're right. Let's actually solve this problem." And

[00:51:08] **Ben:** Yeah.

[00:51:09] **Carol:** you know, in less than 30 minutes, I had a fix to a problem that's been reoccurring for like six months now. this has been going on for a while, and every rotation someone fixes it, and because they're not doing it often, two months down the road, they forgot they fixed it already.

[00:51:23] **Adam:** Mm-hmm.

[00:51:24] **Carol:** say my love for AI is things like bug hunting, 'cause I don't have to do a ton of research. Like you said, take that error log, throw it in there, say, "Help me, friend," and suddenly you have this suggestion that it could be right, it could be wrong, but at least it gets your brain spinning and it gets you usually to a very close location of where the problem is occurring,

[00:51:48] **Adam:** Yeah

[00:51:48] **Carol:** you can then solve it

[00:51:50] **Adam:** That's been one of my favorite things about our move towards SvelteKit for our app. like one of the very first things that I did was like a submit button component, right? So it's got a disabled prop. You can just disable the button based on whatever you want, but also baked in if you don't otherwise disable the submit button.

[00:52:05] When you click it, it automatically disables itself for like, I forget what it is, it's like probably three quarters of a second or something, just to prevent people who double click buttons on the internet from causing problems like that.

[00:52:15] **Carol:** Oh. Why do you exist? Oh

[00:52:18] **Ben:** Right? Yeah. It is interesting though. the, I, I do find AI to be super helpful for debugging, especially like really weird, hairy cases. But then sometimes it'll try to come up with some really complex solution you say, "Well, like, what if we just test this one assumption or, or think about this one little thing in a, in a different way?"

[00:52:44] And it'd be like, "Oh yeah, that's way better." And I totally overstated the severity of like everything I just said in the previous conversation, is just, I don't know, for some reason I feel of myself I make AI second guess, which I know is like so stupid because it's not

## [00:53:01] Token Optimization and the EV Battery Problem

[00:53:01] **Ben:** guessing, it's just

[00:53:02] **Adam:** Right

[00:53:03] **Ben:** tokening.

[00:53:05] **Carol:** Mmm,

[00:53:05] **Ben:** But

[00:53:06] **Carol:** with Claude, I love to use the /BTW, so I don't know if you do that, but you can just do slash, like, by the way, and give it the information. So I'll see it, like, processing something, and it's going off, and I know at this point, based off the files that it's listing, it's went the wrong way. Like, you are off in la-la land right now, and this isn't where you should be at. I'll be like, "By the way, I think you really should, like, be looking in this interface and where it's implemented at, like, this service layer." And it'll go, "Oh, yeah, let me get back on track there. I clearly, like, went off the rails." So

[00:53:45] **Adam:** Yeah, I never used the BTW. I would always just hit Escape to stop it in its tracks, which gives me... Like, why let it keep burning tokens while I'm typing up the by the way? I'm just like, "Stop it in its tracks." I'll type up my thing like, "You were looking at this. That's dumb. This is what you need to be looking at."

[00:54:00] And, and then it would pick up and go from there.

[00:54:02] **Carol:** I'm kind of spoiled right now 'cause we're on the free give everyone everything models of all the tools that we have access to right now.

[00:54:11] **Adam:** Darrell has Mythos

[00:54:13] **Carol:** s- so don't, uh, my brain's not really spinning on token uses, but we were talking about that today, about getting training from the different vendors on how to optimize our token usage, and I was like, "Oh, crap, I have to think about that in a few months when we start paying for these things."

[00:54:31] **Adam:** Yeah

[00:54:33] **Ben:** I know that this is probably a ridiculous mindset, but I feel like I don't ever want to have to think about token optimization. And I know-- And what, what I mean by that is, like, what I want is a tool that just does that for me in the way that when I'm using my IDE, I'm, like, not worried about how it's set up.

[00:54:54] It's like the, the language servers in the background for syntax highlighting and squigglies and stuff, like the people who built the tool just figured that out and made the tool good for me. that's how I want to think about the tokens. Like, don't

[00:55:08] **Adam:** Yeah

[00:55:08] **Ben:** my problem. Make that... know, do the query optimization and the query parameterization and the query caching and the query analysis plan.

[00:55:16] Like, you do that.

[00:55:19] **Adam:** I think we'll get there one day.

[00:55:20] **Ben:** driver.

[00:55:21] **Adam:** Yeah, I think we'll get there one day, but like, you know, just with the available compute, which seems to be the restriction for inference, like that's the bottleneck. you know, everybody's bud- on a budget really. and so, like one day I think that we'll get there where, you know, there's enough compute and it just won't matter, and then it'll just be you're paying for your subscription and it's unlimited, true unlimited for everybody all the time.

[00:55:47] **Ben:** It... I'm not saying it's gonna be a cheap subscription, but I'm sure it will exist at some point. But I do understand your point as well, about the like I just... don't make me think about it, right? Like there's a video, I- I'm an electric car guy now, right? Like we talked about last week. What, what?

[00:56:03] **Adam:** yeah. And, so there's a, a guy, I watch his videos.

[00:56:07] He's a... the, the YouTube channel is Engineering Explained. He does a lot of like explaining stuff with whiteboards, and he gets into engineering topics and he, he, he's a EV lover and a car guy in general. but, you know, he talks about like, you know, this is... He had a video, a real good video about, how to optimize your battery life over the, over like the lifetime of the car.

[00:56:27] You know, what, what's the minimum charge percent you should get to, and what's like the maximum you should charge to on a daily basis, and how often should you use DC fast charging and all that. And he's like, "You know, yes, there's a lot you can learn here, and there's a lot of like stuff that you can do to sort of micro optimize and save yourself an extra 4% over the life of the battery."

[00:56:46] Right? So like i- in 20 years, it will have degraded instead of from 200 to 190, it might degrade from 200 to 194 or

[00:56:55] **Ben:** Hmm.

[00:56:56] **Adam:** right?so it'll save some percentage either way. But, you know, and then what he goes on to say is like, "But ultimately that's the car manufacturer's problem," right?

[00:57:04] Like just I buy a car, it's got a battery, I put juice in, I use the juice. It lets me know when it's empty, right? Like just like driving a, a gas vehicle or a diesel vehicle. It shouldn't be something I have to think that deeply about. And I think that we'll get there one day, but not yet.

[00:57:24] **Carol:** Yeah. The analogy I've used at work is I remember back in the day when we had rollover minutes, and

[00:57:31] **Ben:** Right?

[00:57:32] **Carol:** our, our family shared like these minutes, right? So we had like 250 local minutes and so many whatever, right? And if

[00:57:41] **Adam:** Long distance, yeah

[00:57:42] **Carol:** over and you could, you know, have a little cushion there. I was like, I just need shared tokens because not everybody on my team uses as much as I do, but sometimes I need a little extra and I need just to dip into that bucket and go,

[00:57:57] **Ben:** You gotta get a little bursty.

[00:57:59] **Carol:** that isn't using." Yeah, I mean, like, you know, you don't know what's gonna happen that month, but I don't wanna be charged out the wazoo because this month I have a lot going on, but last month I was in meetings and planning the entire month and, and paid the same. So I want something that also allows us to like consider our actual consumption and how we can kinda level

[00:58:20] **Adam:** For real.

[00:58:21] **Carol:** so everyone

[00:58:23] **Adam:** tokens would be great

[00:58:24] **Carol:** Rollover tokens would be good, right? Yeah.

[00:58:27] **Adam:** Yeah. Even if it's just like you can, you can save 10% of whatever you didn't use from your last week for this week, and 10% of whatever you didn't use from your last five-hour session for this five-hour session. Like, that would be amazing

[00:58:39] **Carol:** Put it in the ticket. Let's see if they'll do it

[00:58:42] **Adam:** They'll never do

## [00:58:42] Relative vs. Absolute Risk

[00:58:42] **Adam:** it

[00:58:43] **Ben:** You know, ju- th- just to go back to what Adam was saying about the going from 200 miles on a charge to 190 versus 200 to 194, th- this is such a fascinating just way to think about problems in general. I remember, I was listening to a science podcast, I don't know, last summer or something, and they were talking about all this controversy.

[00:59:05] This is about to be non-technical for m- for a moment here. Like, for a long time, it was thought that if women wanted to take hormone replacement therapy after menopause, it increased your risk of breast cancer by, like, 60%. like, somebody, like, and people were, like, freaking out about this, and it, and it changed a lot of women's minds about how they wanna deal with that. then if you look at the research and you hear people who are, like, really knowledgeable about this stuff actually talk about it, it's kind of like the battery problem. Like, yes, went up 60%, but that was from, like, your risk of getting breast cancer was and now it's, like, .072%. So, like, yeah, proportionally it went up a lot, but in the grand scheme of things, it, like, barely moved.

[00:59:51] And I'm not advocating for anything because I don't know the actual details, but, like, it's basically like that. So sometimes you hear the, relative magnitude of how things work, and it seems so crazy, but then you hear the absolute magnitude of how it works and you're like, "Oh, why did we spend so much time thinking about this?"

[01:00:11] **Carol:** Right?

[01:00:11] **Ben:** was this really the problem

[01:00:12] we were trying to solve?

[01:00:14] **Adam:** is tough for people, right? Like, the difference between a billion and a trillion is basically a trillion, right?

[01:00:23] **Carol:** It's funny you brought up those numbers 'cause I just had the conversation with my mother-in-law, and she was telling me, like, how the studies have changed so much. And she told me, she goes, "You should just start taking hormones now because you don't wanna deal with it down the road." She goes, "I

[01:00:38] **Adam:** Wow

[01:00:39] **Carol:** told me that when I was younger 'cause then I would've been in a much better place," right?

[01:00:43] She goes, "Instead, they pushed for us to be like, 'Don't take it. It's not worth the risk of everything else that can develop from it.'" I'm like, man, how things change in just 20 or 30 years

[01:00:55] **Ben:** Yo, crazy

## [01:00:57] Patreon

[01:00:57] **Ben:** stuff

[01:00:58] **Adam:** What a world. All right, well then, let's wrap it up there. This episode of Working Code was brought to you by Ben exposing himself to stuff

[01:01:05] **Carol:** In a good way? In a good way

[01:01:08] **Adam:** and listeners like

## [01:01:09] Thanks For Listening!

[01:01:09] **Adam:** you, if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into universe, then you should consider supporting us on Patreon. Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them.

[01:01:23] Special thanks to our top patrons, Monte and Giancarlo. You guys rock.we're gonna go record the after show, which I should probably have written a script for this part of my monologue at this point, but I still haven't. But you know what it means. Outro music plays. We're gonna come back for those of you who are patrons and say more stuff about stuff, and Ben will keep his pants on hopefully.

[01:01:43] Um,and if you would like to become a patron of the show and get access to the audio of Ben taking his pants off, then, you can go to patreon.com/workingcodepod, and that's how you do that. Do the thing. That's gonna do it for us this week. We'll catch you again next week, and until then

[01:02:08] **Ben:** Remember folks, whether or not you use OpenAPI, Swagger, SOAP for,

[01:02:15] **Adam:** man

[01:02:16] **Ben:** for your wi- for you WSDL heads out there,

[01:02:19] **Carol:** Oh, geez.

[01:02:20] **Adam:** through the heart

[01:02:21] **Ben:** your heart, still matters
