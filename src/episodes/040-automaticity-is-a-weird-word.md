---
title: "040: Automaticity Is a Weird Word"
description: 'On today''s episode, the crew talks about how they use databases; the role of atomic transactions in the reduction of application complexity; and, whether or not they''ve ever felt "held back" by the limitations of a relational database management system. Full disclosure, all of the hosts have far more experience with traditional databases when compared to NoSQL databases.'
date: 2021-09-15
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/040-automaticity-is-a-weird-word/id1544142288?i=1000535406686"></iframe>

The other day, Ben was listening to an [episode of the MongoDB podcast in which Mat Keep][mongodb-67] shared a story about the adding of **atomic transactions** into the MongoDB product. Mat said that the engineer who spearheaded the effort used to joke about the fact that his team was spending a huge amount of time working on a feature that **90% of developers would never need**. For Ben - who leans heavily on transactions for referential integrity - this sounded like an crazy statement. But is it? Are database transactions overrated? Or, is it more so that the _type of use-cases_ that work best in a document database are also the type of uses-cases that don't really need transactions?

On today's episode, the crew talks about how they use databases; the role of atomic transactions in the reduction of application complexity; and, whether or not they've ever felt "held back" by the limitations of a relational database management system. Full disclosure, all of the hosts have far more experience with traditional databases when compared to NoSQL databases.

> **NOTE**: In the show, Ben mentioned that a document database like MongoDB can't enforce schemas like a relational database. And while this was true in earlier versions of the MongoDB product, it is no longer true. In recent updates, MongoDB has added [schema validation and enforcement][mongodb-schema].

## Notes &amp; Links

-  [MongoDB Podcast: Episode 67 - MongoDB Evolved with Mat Keep][mongodb-67]

Follow the show! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media][editor].

[mongodb-67]: https://mongodb.libsyn.com/67-mongodb-evolved-with-mat-keep
[mongodb-schema]: https://docs.mongodb.com/realm/mongodb/enforce-a-document-schema/
[working-code]: https://workingcode.dev/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[editor]: https://www.zcross.media/
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/040-automaticity-is-a-weird-word.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** He was like, he's like, if you think you can just drop dynamo DB, as in, as a replacement of something like SQL database, like you will be very unhappy.

[00:00:09] **Ben:** Because it will not work and it will be very non-performance or it'll be very expensive.

[00:00:14] **Carol:** That makes me feel way better. Cause that's always kind of been my thought is that. Going that way into a document database doesn't seem like where you flow into it's where you would be starting out at. And I've never been in a position where I know what I'm doing up front to start there. So it's always so ever-changing and I never know.

[00:00:35] **Carol:** So

[00:00:36] **Ben:** Anyway databases. What's up with that?

[00:00:38] **Carol:** what's up with those things.

## [00:00:40] Intro

[00:00:40] **Adam:** Okay. Here we go. It is show number 40 and on today's show, we're going to talk about databases and transactions, and hopefully we can come up with a better title for it than that.

[00:01:06] **Adam:** but as usual, we're going to start with our triumphs and fails. And Carol, you get to go first.

## [00:01:10] Carols' Triumphs

[00:01:10] **Carol:** Good because I have two wins

[00:01:13] **Tim:** No, just one.

[00:01:14] **Tim:** just

[00:01:14] **Carol:** No, no, we're going with two.

[00:01:16] **Tim:** fine.

[00:01:17] **Carol:** I am a redhead and a ginger. Right. So I burn

[00:01:21] **Adam:** that's not a triumph, Carolyn.

[00:01:23] **Carol:** Okay. It's a train for my life. Y'all leave me alone. I burn, like I get some burns all the time, so I have to go to the dermatologist. And anyway, so Monday they found the spot and they were like, oh, we're just going to go ahead and take this off to be safe.

[00:01:35] **Carol:** They're like, we'll tell you in two weeks, like if it's anything to worry about or not. So they called the day and I was like, Hey, congratulations, you don't have cancer still. So, yay. Yes, I have cancer is, it's really bad for gingers and red heads. So I have to be very careful about that.

[00:01:50] **Adam:** wait a minute. It, ginger and red hat are two different things.

[00:01:53] **Carol:** Yeah. I mean, the whole super fair skin part of the gender, but you know, the red

[00:01:59] **Adam:** always just assumed that they were like, ginger was like just slang for redhead.

[00:02:02] **Carol:** Oh no, no. You have to be really white and very fair skin and very red head and you have to steal people's

[00:02:08] **Carol:** souls.

[00:02:09] **Tim:** I do know some folks who are African-American who are red hair.

[00:02:14] **Carol:** Really.

[00:02:14] **Tim:** Yeah, I do. Yeah, I do. I know actually know three people

[00:02:18] **Adam:** I don't think

[00:02:19] **Tim:** that live in this area that.

[00:02:20] **Tim:** I'm friends with. So they are African-Americans they have red hair, but they obviously are not light skinned. So Yeah. I agree with what she says, but she, I think ginger kind of covers both.

[00:02:31] **Carol:** yeah. Okay.

[00:02:32] **Tim:** Cause I have two juniors in my house and they both have stolen everyone's soul.

[00:02:36] **Carol:** Yeah. We're evil. What can I say?

[00:02:38] **Tim:** not evil. It's just what you do,

[00:02:40] **Carol:** just what we do. It's by nature.

[00:02:41] **Tim:** it's a passive equality.

[00:02:44] **Carol:** Can I use that one play D and D I'll

[00:02:46] **Tim:** Sure. Yeah, that, that will be your passive quality.

[00:02:49] **Adam:** It doesn't cost you.

[00:02:51] **Tim:** No, it's a free action.

[00:02:53] **Carol:** My second win is I have been writing a whole bunch of tests this week and I am just like rocking mocking. And I didn't like, sometimes it just doesn't work for me. And sometimes I can't mock like different, libraries I've installed or different packages, but I have been able to literally mock everything I've tried doing, which is great because now I don't have to rely on any dependency to any network layers and your database layer, because literally I've just mopped every call to something.

[00:03:17] **Carol:** And once I've figured out how to use. I feel like I just write through so many tests so quickly because there's not a lot of thought to it. It's more of just go get it done and I'm just, I'm loving it. So yay. Mock it. Woo.

[00:03:30] **Ben:** Okay.

[00:03:30] **Adam:** Yeah, I need to get my testing velocity up so that I can keep the momentum there. And I feel like just when I start to get the hang of things, they, I get moved on to something else and it's like, oh, well, okay. Got to set that aside.

[00:03:42] **Carol:** Yeah. Once you fall behind, it's hard to catch back up on it.

[00:03:46] **Carol:** It's good on a new project because there is no catching up. You start there with it. So, Hey lens for me. All right. What about you, Adam? You're up next?

## [00:03:54] Adam's Triumph

[00:03:54] **Adam:** Yeah. I'm gonna go with the triumph this week. I've been having some fun with QR codes, so, we're all pretty familiar with QR codes, I think. but

[00:04:00] **Carol:** Adam, what's a QR code. Tell me more.

[00:04:02] **Adam:** it's,they're referred to as 2d barcodes, which I find, interesting, because does that imply that like the barcode on all your groceries is a one D barcode, right.

[00:04:12] **Adam:** And.

[00:04:13] **Ben:** I think so.

[00:04:14] **Adam:** But two-dimensional means by anyway, like I don't want to get into that whole thing. It's just a semantic thing. Whatever I've been playing with QR codes and they're fun. they're the barcodes that are like on your ups package or whatever, they're square. And they have lots of little like pixels in them.

[00:04:28] **Adam:** And if you didn't know, they have have error correction built into them and you can set like an error correction level and the, so the higher you turn on the error correction, just the more data that ends up in there. Right? You have a bunch of like, I don't know exactly how it works, but I imagine there's like parody bits or whatever that.

[00:04:44] **Adam:** Double-check things. So it just means more data in your QR code, but it also means that, if part of that your code org to get like scratched or whatever, then that the likelihood of still being able to get us a successful scan out of it is still very high.

[00:04:58] **Tim:** Okay.

[00:04:58] **Adam:** And, from what I understand that was intentionally done so that it was intentionally built that way or, specified that way so that people could do what I've been doing this week.

[00:05:09] **Adam:** intentionally like abused that QR code by putting like a logo in the center of it. And so, yeah, so I'm making like branded QR codes, with like, so I have, my customers are universities and so I'm putting like university logos in the center of these QR codes. and they have a nice little stroke around the, oh yeah, they're

[00:05:25] **Carol:** Nice.

[00:05:26] **Adam:** it's just been so fun and,it feels very, if, when you look at it, is it it's got that, that feel of like, this is impressive, this is polished. Right. But it's so easy to do. and so that's just, I'm happy. I'm enjoying that. And.

[00:05:42] **Carol:** this is your first time working with them.

[00:05:44] **Adam:** No, but, this,the other nice thing about this is we're going to, in our product, we're going to use our own logo by default, and then upsell, you can put in your logo instead.

[00:05:53] **Adam:** So this is a nice little,

[00:05:54] **Carol:** it's the little, you're not watermarked,

[00:05:57] **Adam:** right?

[00:05:57] **Tim:** Brandon.

[00:05:58] **Carol:** Yeah. I

[00:05:59] **Adam:** So that'll be a nice little upsell and additional money for the company probably. And yeah, I'm excited

[00:06:04] **Carol:** gets your name out there.

[00:06:05] **Adam:** Yeah. So.

[00:06:07] **Ben:** looking one time into the logic that goes into a QR code because I wanted to play around with them awhile back. And, all I could find was Java libraries that do it. And I was like, come on, I got to be able to write this in ColdFusion and build a new. And I looked at one of the libraries that implements it in Java and it's like 3000 lines of math and bit manipulation.

[00:06:26] **Ben:** I was like, no backing out of the room.

[00:06:31] **Tim:** Yeah, I built a little, open-source project called QR co toad, which built this kind of thing. It was, but it was like I text. So, I mean, all I did was like put an interface for COPD patient on that So yeah, I, wasn't going to write the whole math to build the

[00:06:46] **Adam:** was that ITEX or I text with a T on the end.

[00:06:49] **Tim:** by text with a T.

[00:06:51] **Adam:** Okay.

[00:06:52] **Adam:** And that's like a Java library or something.

[00:06:53] **Tim:** Yeah. As a Java lumber, it's used for building PDFs, but it also had like a sub library that built QR codes, which I just doing introspection on the jar. I said, Okay.

[00:07:05] **Tim:** it does this too. So

[00:07:07] **Adam:** Nice. Yeah. So the way that I'm doing is aiming. If we want to get into this architecture of it, it's kind of a fun little

[00:07:13] **Tim:** let's do.

[00:07:14] **Adam:** That's why I have an ALB route ALB as the application load balancer, which detects based on host name and path and everything, that it should be doing a QR code. And from there at forwards, the request onto Lambda.

[00:07:28] **Adam:** So in Lambda, I'm running a node JS app and it grabs the information out of the URL. So all the data that we want to encode in the QR code is coming in the URL and, including which logo to. And, then, it uses that node library creates a QR code, overlays the appropriate logo, and we'll write it out to S3 and then return the URL of the, like the public URL of that image on S3.

[00:07:57] **Adam:** All to the original user in, well, under a second. And that is if it has to, generate the image, if the image has already been created. Cause what happens is when that request comes in with the data, I take the data that I'm embedding in the QR code and the logo, because there could be potentially, collisions with the same data, but different logos.

[00:08:14] **Adam:** So combine the two MD five hashes, and that is actually the name that I save it with. S3. So if that file name already exists in my S3 bucket, then I just return that S3 URL real quick. And that happens in like double digit, like very low double digit, like 20 to 30 milliseconds. So I'm super happy with the speed of this thing.

[00:08:36] **Ben:** Very cool.

[00:08:37] **Adam:** Yeah.

[00:08:39] **Ben:** Dan,

[00:08:40] **Adam:** it has been a lot of fun. So, I'm kind of riding high on that one. So I'm just happy to be talking about it. So, Ben, what are you guys.

## [00:08:47] Ben's Triumph

[00:08:47] **Ben:** I'm going to go with a triumph. I've been

[00:08:49] **Tim:** Three in a row.

[00:08:52] **Ben:** I've been inspired. Carol's adventures with AWS and Bryan's talking about AWS and,I've long wanted to start learning more about message cues. So I, this morning downloaded a bunch of AWS SQS jar files, and, started trying to read from and write to an SQS in ColdFusion and Lucy CFML.

[00:09:15] **Ben:** So proud of

[00:09:16] **Ben:** Yeah, it's pretty, as I've said it, I think on previous episodes, some of the biggest mistakes that I've made in building application architectures is making everything synchronous. and really I could have avoided a lot of pain by putting a queue in between some requests and some responses.

[00:09:31] **Ben:** it's not a super simple change. Right? You have re you have to really change the way you think about processing data and how people. Look at that data over time. How, you know, when things are done, what happens if they're not done, what happens if they failed, et cetera, et cetera. So there's a lot to be considered, but, just being able to instantiate this instance of the SQS client and being able to write and read a message, I feel like it's a huge first step.

[00:09:56] **Ben:** it's going to be a much larger step than trying to figure out how to actually consume a Q as part of an ongoing long lived application. first step. So I'm pretty excited about that.

[00:10:06] **Carol:** Next step you need SNS.

[00:10:08] **Carol:** Yes,

[00:10:09] **Ben:** doesn't, that stuff looks pretty cool too.

[00:10:11] **Carol:** it is. It is.

[00:10:12] **Adam:** so the thing that kind of drove me nuts for a long time with CFML was the lack of, asynchronous interaction.

[00:10:21] **Adam:** and in some ways I think it was, like sort of a victim of its own success, like early on, there was a, w not API gateway. What was that called?

[00:10:29] **Ben:** Gateway,

[00:10:30] **Adam:** And then gateway. Yes. Thank you. API gateways and AWS product that I also love. but, oh my

[00:10:37] **Carol:** Okay. And now after show after show.

[00:10:39] **Adam:** so it, event gateway was very useful, but I think that it was a little ahead of its time and so not, it didn't get a whole lot of use.

[00:10:47] **Adam:** And so it stopped being developed and then it just became this. the pun here since we were just discussing this, but like the redheaded stepchild of the

[00:10:57] **Tim:** Ginger.

[00:10:58] **Ben:** Well, it seems so out of brand with everything else that was called fusion. Cause everything. Was super easy. Like you want an application, just here's an index file. Like you want a database query, here's a sea of tag. And then it was like, you want to implement an event gateway. Like you have to have special types of libraries.

[00:11:15] **Ben:** Then you have to have configuration files and they have to be registered in the administrator. And you're like, this is so different than everything

[00:11:21] **Adam:** absolutely. But like I said, I think that it was powerful, but it was ahead of its time. And as a result, nobody used it. And as a result, it got like, it fell behind and

[00:11:30] **Tim:** I don't think it was ahead of its time. I just think it was out of

[00:11:33] **Adam:** Well, well, so, but think about this these days, pretty much any modern platform. If you talk to somebody and tell them, okay, you need to do like a Reddis pubsub right.

[00:11:42] **Adam:** and like publish messages across nodes or something like that. Anybody can do that. Hooking that up in CFML would require like using a Java library and dealing with all the difficulties of that. Some Java libraries work really well with CFML some of them it's like, okay, here's the jar, figure it out for yourself.

[00:11:59] **Adam:** And, I hate that situation personally.

[00:12:03] **Tim:** I mean recently they do have the run as AC, so

[00:12:07] **Adam:** yeah. Yeah. I mean, I. Significantly away from CFML in the last, like maybe five years ago. And so the last couple of releases, I'm not, whatever, I don't have my toe in that pool anymore, but

[00:12:20] **Carol:** I feel like we just hijack Ben's triumph.

[00:12:22] **Ben:** no, this is no,

[00:12:23] **Adam:** a discussion.

[00:12:24] **Ben:** I'll tell you like the big mental block that I have is

[00:12:28] **Tim:** Okay.

[00:12:29] **Ben:** again, how do I, it's one thing to read and write from a message queue as this, like a one-time action. To sit there and pull the queue with long polling technique and have that run in a thread. That's not blocking the overall application, but then also like what happens if that thread dies? Because it

[00:12:48] **Ben:** gets, uh, terminated well, right. But what, there has to be something watching that thread to make sure the thread can respond. And you know, when you're in a node application, it seems so much easier, I guess. There's not this whole concept of threads is like, there's just one event tick or event loop.

[00:13:09] **Carol:** And I don't know. So I tried looking at, the orders guys, the ColdBox guys have this whole async library that they do with the tasks and queues and thread pools and stuff. it's very complicated. It seems like, Didn't help you much?

[00:13:24] **Adam:** Sounds like it

[00:13:25] **Carol:** Well, I was just curious

[00:13:26] **Adam:** Java. You token current with the

[00:13:28] **Ben:** Yeah, it uses a bunch of concurrency and future stuff under the hood. But, I think part of it too, is like, I just don't know what the code would look like. I don't know. It's weird. It's like, I want to have, I'd want to have separation of my code between like here's here are the mechanics of polling, the queue and dealing with cues, and then here's the mechanics of processing the message.

[00:13:50] **Ben:** And I almost want those to be two totally separate things. I wanted to change the queuing mechanism, I'd still have all the logic that processes the thing that I'm trying to do, but maybe doesn't necessarily have to deal with the queue. And I don't know, I'm just trying to separate out the IO from the business logic,

[00:14:08] **Tim:** What's your use case?

[00:14:10] **Ben:** anything, I don't know, everything that

[00:14:12] **Adam:** Does R and D or.

[00:14:14] **Ben:** Well, because I have so little hands-on experience with cues. I don't know. I don't have an instinct for when to use them,

[00:14:21] **Adam:** Hm.

[00:14:22] **Ben:** but,we do a lot of image processing and generating of PDFs, generating zip files, things that could probably be done with a queue.

[00:14:32] **Adam:** Sure.

[00:14:32] **Carol:** I'm assuming I got to learn it and then I'll figure out how to use it, We're going to plug it in

[00:14:38] **Adam:** little bit of a chicken and egg.

[00:14:40] **Tim:** Hmm.

[00:14:41] **Ben:** But, yeah. So what about, what about you, Tim? What you got going on?

## [00:14:43] Tim's Triumph

[00:14:43] **Tim:** so my triumph is not particularly technical again. Sorry. I've been waiting for years to watch Hamilton.

[00:14:49] **Carol:** But I'm right here.

[00:14:50] **Tim:** No, not you, Carol Hamilton.

[00:14:53] **Adam:** Live and in person.

[00:14:55] **Tim:** I want to watch the Broadway play version of Hamilton. So it's like a

[00:15:00] **Carol:** all do.

[00:15:01] **Tim:** Yeah, a friend of mine, he had tic, he has like season tickets to the Fox and get me tickets.

[00:15:08] **Tim:** And so in 2020 for April, we were supposed to go see Hamilton. And, of course, you know what happened? In the spring of 2020. So, but so we're going tomorrow. We're going to see finally, we're going to see Hamilton,

[00:15:23] **Tim:** but what what's even awesomer is that it's the same time as dragon con. So We get to see we're not going to drag up, but we need get to see

[00:15:30] **Carol:** We get to the crazies.

[00:15:31] **Carol:** Yay.

[00:15:32] **Tim:** the crazy people in there cause plays. So, but On the technical side. So I'll I talked about last week. I'm finally delivering all the boring legal info to the parties that need it. So it's just a part of.

[00:15:46] **Adam:** I take the requirements from the users and I bring them to the engineers.

[00:15:50] **Tim:** not even that it's like these deals like, so some, it's like, if you aren't a hundred percent delivering the product, like sometimes you're tying you with a product and that product is a federally regulated institution, like a bank. There's a lot of stuff that you have to go through and they have to.

[00:16:10] **Tim:** They ask you questions that have absolutely nothing because they just have this boiler template stuff. That's just says, Hey, what do you do when you do this? I'm like, we don't do this.

[00:16:22] **Adam:** Yeah,

[00:16:23] **Carol:** Yeah.

[00:16:23] **Tim:** And so, like, so the consumer, or what will a consumer face, like, none of this stuff that you're suggesting.

[00:16:30] **Adam:** not applicable.

[00:16:32] **Tim:** exactly.

[00:16:32] **Tim:** and I, so yeah, just going through that. So that's got through that today. Cause I have like, besides my notebook and my. Inbox zero. I have my, I flag stuff when it comes in, says, importance of my little flag on outlook that says, this is important. Get to answer this, that this is a day, so,

[00:16:53] **Carol:** So wait, does inbox zero? Not count if it's already, like, if you flag it. That means you'll come back to it. that still

[00:17:00] **Carol:** lets

[00:17:01] **Tim:** sure. Yeah. There, there, there, there's some things that are.

[00:17:03] **Carol:** are tricking the system.

[00:17:05] **Tim:** am. I am. Yeah, I am. So I was like, my inbox is zero, but I do have things flagged as like, this is really important and I can't handle this right now, so,

[00:17:17] **Carol:** You've just lost. You just lost a cool point.

[00:17:19] **Tim:** Yeah.

[00:17:20] **Tim:** That's all right. That's all right.

[00:17:23] **Adam:** Okay, well, since Tim hasn't had enough opportunities to mention post-grads lately, we thought that today we would talk about databases and transactions and,

[00:17:34] **Tim:** Postgres

[00:17:36] **Carol:** Fan boy,

[00:17:36] **Carol:** Sam boy.

[00:17:38] **Adam:** So, actually Ben you,proposed this topic because you heard something somewhere else and it made you have feelings. And so tell us what you.

## [00:17:46] Transactions In Document Databases

[00:17:46] **Ben:** Yeah. So the other day I was listening to a podcast about Mongo DB. I think it's Mongo DB is official podcast. I don't know if anyone does this, but sometimes I'll go into my podcast app and I'll just search for random technologies like Mongo DB or redness or ColdFusion. it's kind of like shocking how few things come up for technology-related.

[00:18:06] **Ben:** I don't know if it's just because the app. Podcasting app is terrible or because podcasts searches in general are terrible, but,

[00:18:14] **Tim:** Okay.

[00:18:15] **Ben:** or there's just not that much content. I don't know. Anyway, so I came across as Mongo DB podcasts, and I started to listen to a bunch of them. And there was one that was talking about, this guy was talking about like everything that's changed in Mongo DB in the last 10 years, because when Mongo DB first came out, it had a bunch of hurdles that had to overcome around security and availability.

[00:18:34] **Ben:** kicking the tires, that kind of stuff. And, one of the things that the guy talked about was building transactions into the database, like you would normally expect in a relational database management system, a transaction being that I can perform two separate operations on the database in an atomic way, meaning that they both happen successfully, or they both don't happen successfully.

[00:18:56] **Ben:** There's not like this one work, but one didn't kind of an idea.

[00:18:59] **Adam:** Because they're both in the same transect.

[00:19:01] **Ben:** Because they're both in the same transaction or they either both work or they both roll back. And he was saying that the guy who was building the transactions into Mongo DB was complaining that he was spending all this time on a feature that 90% of developers will never use.

[00:19:17] **Ben:** And that struck me as this like crazy concept that 90% of the people who work with Mongo databases have no need for transactions. And it made me think about my use of transactions and just how I think. Guarantees around writing data to a database that I don't know if I'm crazy, or if I just am so far off from understanding how a document database changes, the way people develop. And he was also talking about in that episode, how databases are so much easier to use because they match more closely the data model that developers are already using in their applications. And it was, again, one of these things where like, I can definitely think of use cases where that's true, where I have a large, complicated document, like an object and memory, and maybe it would be nice to just jam that into a database.

[00:20:08] **Ben:** But for the most part, I'm dealing with very small chunks of data that actually do very closely match my relational database tables. And I don't know, I just, I don't, maybe I don't have enough understanding of how document databases work, but I think there's. I don't know if I'm just not understanding how people think about transactions and at Thomas is that the right?

[00:20:32] **Carol:** saw that word and I was like, how do you even say that correctly?

[00:20:36] **Ben:** that's going to be a hard one. and so, so, thing that talk about that people always talk about with document databases is that you can form your document to match your query pack. So that we're in a relational database, you might have to pull data from multiple tables in a document database.

[00:20:52] **Ben:** You can have those co-located within a single document. And then when you had to read that out of the document database, that's just one request,

[00:20:58] **Adam:** Yeah.

[00:20:59] **Adam:** I'm gonna jump in here a little bit. the. The thing that I've struggled with document databases for the longest time. And this is the primary reason that I am not a heavy document database user, is that I have a lot of data to work with and a lot of different angles that I need to look at it from right.

[00:21:18] **Adam:** Events and reporting and registration is a lot different than the reporting. And so the management of the data is sort of a third angle. You might want to look at it through and in, and that's just like one module of my database here. so repeat that times and modules or whatever. the, my understanding of the document flow is like, you get the document and that has everything you need for the thing you're working on.

[00:21:41] **Adam:** And then you update the document when you're done with it. Right. And that's just not. that doesn't seem like it would hold true in the data that I use in my app. Right. Like I need to update this table over here and this table over here and maybe create a bunch of relationships and it's just like,

[00:21:58] **Carol:** It's not how I think

[00:22:00] **Adam:** right.

[00:22:00] **Adam:** So, and so I think that to me, like that makes your, automative city, and transactions questioning here very relatable to me. Like I. I agree because, well, think that if your application architecture is the type that,you just grab a document and you modify it, if you need to, and then write it back and that's all you're ever doing, then that fits the document database model really well.

[00:22:28] **Adam:** And yeah, you probably don't need translation. But if you are updating multiple related documents and you need them to only update, if the other one also succeeds, then that's what a transaction is for. And I can see how that would be a, of a, an infrequent use case for document database, heavy users. But I, the thing that I struggle with is like, what is the use case?

[00:22:53] **Adam:** Like, I still can't wrap my head around. When is that a better.

[00:22:58] **Ben:** Well, maybe that's, I'm kind of projecting my own usage onto what this guy was saying about Mongo DB, but it could be that his statement is presupposing, that people are choosing Mongo DB for very specific use cases. So maybe his viewpoint. Well, if you're going to use a document database for things that are very good for document databases, then you don't need transactions.

[00:23:21] **Ben:** And I think there's probably a lot of truth in that. But if you look at a document database as not a drop in replacement, but I think a lot of people choose a document database, not necessarily because they have document oriented data just because like they want a database that doesn't have a strict schema and they want to be able to create new collections really

[00:23:40] **Adam:** and they want it to be Webscale.

[00:23:41] **Ben:** And they will, of course they have to ask to be web-scale. And like, I have to imagine those people have to have transactions because they're not necessarily dealing with data. That's really purely geared towards

[00:23:54] **Adam:** right. I think that you can shoehorn any application into a document database, right? Like it's just data. It happens to be schema list so that you can modify your scheme over time or whatever. But, I still struggle to see, like, what is the, what is the right word that I'm looking for here? Like, the. Perfect use case. the example, like if your application uses this sort of data structure, then you should be using a document database. I don't know what that is.

[00:24:20] **Carol:** So Mongo DB doesn't support rollback period, right? Like there is no thought of rollback in

[00:24:25] **Adam:** I mean, if they have transactions, they have to right.

[00:24:28] **Ben:** I think so. I mean, maybe you can't explicitly roll back. Like you can in a relational database. Maybe it's like implicitly, if something fails, then it rolls back. I don't know. I'm not, I

[00:24:38] **Adam:** clearly we are not Mongo

[00:24:39] **Adam:** DB

[00:24:40] **Carol:** Yeah.

[00:24:40] **Carol:** I don't know a lot about document databases, period. So I was just curious because the thought of not having a transaction scares me because so much happens in that transaction. So many things. Need to be successful for it to commit and the thought of partial committing without all of it being right. I can't wrap my head around it.

[00:25:01] **Ben:** and I think there are definitely ways if you have data that has to work successfully together, but you don't have transactions. There are ways that you. Architect the application to have more item, potent actions, meaning actions that are safe to retry if they don't completely succeed, but you have to build that.

[00:25:20] **Ben:** Like, if you can't lean on the power of a transaction, then you have to make up for it in the application code. And that's a lot of added complexity. So it's not like you just like it. I don't know. It just bothers me, I guess when I don't understand things that seems so vastly different from how I understand it. Um, cause even just, I think about signing up in a, in an account. So like, like, let's say you have a service product service and you have to register an account and you have to, I mean, this is this mirrors, a lot of how we do stuff at work where we have a user record and the user record is more of a public facing, but not necessarily a logged in account.

[00:26:02] **Ben:** And then if you sign up, you get both a user record and an account record in the account is like where the path would actually be. Those are two different tables for us. And those, we create those inside of a transaction so that if the account fails, the user rolls back as well.

[00:26:16] **Carol:** Right.

[00:26:17] **Ben:** and the thing is though, is that we can make a lot of queries against the database that read the user, but don't care about the account because we're not necessarily dealing with a logged in situation.

[00:26:26] **Ben:** So in a document database, if you're co-locating data within a document that is intended to be read together all the time, Then in order for something like that, to be atomic without transactions, you'd have to essentially store the user and the account in the same document and always read the account out every time you needed to read the user, unless you would like read partial documents, I guess.

[00:26:46] **Carol:** Can you even read partial documents?

[00:26:49] **Ben:** I think you can like project

[00:26:52] **Adam:** Is that like a view?

[00:26:53] **Ben:** Yeah. I think that you can say like, get me this object, but only return these properties.

[00:26:59] **Carol:** Interesting.

[00:27:00] **Carol:** I really need to learn more about document databases.

[00:27:03] **Ben:** you know, it's still, I I believe it's still has to read the whole thing off of disc, I assume. I'm sure they have lots of magic behind the scenes that make that more efficient, but I don't know.

[00:27:12] **Carol:** I guess, because all I know is the structure. I know it's hard to wrap my brain around

[00:27:19] **Carol:** different.

[00:27:21] **Ben:** Well, so, okay. And then, so dovetailing was one of the other things that the guy said on the podcast, which. it's harder to work with relational databases because the data you have in your application memory doesn't necessarily match the data that you have in your database. But I also find that to not be true most of the time,

[00:27:37] **Adam:** Wait say that again?

[00:27:39] **Ben:** like I think the intent of his statement is. Your data structures in your application are these like complex data structures, like objects with the rays and other objects inside them. And then you have to then map that to a relational database, a flat table

[00:27:56] **Adam:** sure. That's why we have like an object relational mapper, right? Like.

[00:28:01] **Ben:** but also I, this, I guess this is, and this goes back again to your statement about like, what's the right use case for documentation. Even complex structures. I have a lot of things where I'm actually querying for little bits of that data

[00:28:16] **Ben:** structure. So it's nice for me to have tables that have just that data.

[00:28:22] **Ben:** And I don't have to worry about having all kinds of crazy indexes or different serialized versions of objects. It just, I don't know. I mean, I know people who build document databases have to market document databases, right? So they have to tell you how great it is for all the things that you need to do. But I it's just never connected with me the idea of using Mongo DB. I think there are some, again, some use cases, like we use it at work. We have to store these like just giant arbitrary blobs of Jason that clients will give us like,application clients. But for the most part, I love relational databases.

[00:28:57] **Ben:** I never really feel like I'm being held back by having to have a data table.

## [00:29:03] Relational Database Scaling

[00:29:03] **Adam:** So actually, if that's where we want to take this conversation in the places where I feel held back by a relational database is when a table gets to be large enough that it's slowing things down, right. When you get to that, like a couple of million rows and you've got 30 plus column. That's a lot of data and then, a query that feels like it should be fast isn't anymore.

[00:29:26] **Carol:** Right.

[00:29:26] **Adam:** And you have to start, like, I know MySQL is a little bit weird about this, but you know, I've, I have had to do some query optimizations and you look at the final query and it looks stupid. You look at this and you go, all right, I'm going to rewrite this because this is what was this person smoking when they wrote the SQL.

[00:29:42] **Adam:** But then if you like take the quote unquote, like smart way to write the SQL and you compare it to the stupid way, stupid ways, like often many as we've discussed in the past many orders of magnitude faster,

[00:29:52] **Ben:** Well, I think also as I've. As I've had more experience building data-driven applications. One of the things that I've come to learn more recently than I'd like to admit to is that the tables don't have to be as wide as I would have normally done them. So my, like, just going back to the idea of having a user and a user table, my, my kind of historical preference would be to anytime I have another property that I want to associate with the user, I just add a column to that. And so like, I have my user now they have to have GDPR marketing opt in. So I'll just add, some sort of opt in, opt out newsletters, kind of a column. And then they have to have, like, I don't know an address or, maybe an address on there for whatever, or I don't know, like this tables just get wider and wider.

[00:30:37] **Ben:** And I was listening to a podcast a couple of months ago and this guy said something about it. He's like you, everybody keeps throwing columns on a table. Like most of the time you're not reading or like you read that column data, but you don't need

[00:30:50] **Carol:** You don't need it

[00:30:51] **Ben:** It's

[00:30:51] **Ben:** if you're adding data to a table and you don't need it, most of the time put it in a different table.

[00:30:58] **Ben:** He's like, he's like if he said it said something like he was basically saying like the columns in your table, when you read that row, you should be using all those columns.

[00:31:07] **Carol:** I agree.

[00:31:08] **Adam:** How is that different than when you're not selecting those calls?

[00:31:12] **Ben:** I think it's more to do with just the size of the table and the ability to change that table over, over time.

[00:31:19] **Carol:** Yeah. Like when you were talking about the marketing stuff, I'd be like, okay. User marketing table, like that information needs to live outside of the user table. It needs to be its own table so that I don't go pull it. Yeah.

[00:31:29] **Ben:** So like GDPR just came out where like three years ago, two, three years ago.

[00:31:34] **Adam:** Is

[00:31:34] **Ben:** And imagine having an application that was running for a decade prior to that, you might have hundreds of thousands or millions of records in a user table. And if you had to add GDPR information to it at that point, now you have to migrate this online.

[00:31:47] **Ben:** So you don't have downtime and you have to add a column and do you know all kinds of fun data gymnastics in order to do that seamlessly or to Carol's point, you could just create a new table for GDPR preferences. And there's nothing to migrate other than the create table. And then you just start writing to it and it's like, there's no downtime.

[00:32:06] **Ben:** There's no, as, a super amount of processing on the database and for the vast majority of queries that you run on the application that read users and don't care one iota about GDPR compliance, they don't get hit with having to read that data off of the, record. Cause even if you return a record, I mean, sorry, even if you return a subset of columns, you still have to read the whole record.

[00:32:27] **Ben:** Off the file system or, again, there's probably all kinds of magic about caching and in-memory stuff, but

[00:32:32] **Adam:** The database reads it into

[00:32:33] **Adam:** or read parts of it. Yeah. Hm.

[00:32:35] **Ben:** So I don't know, like, I guess I've when people talk about their data model and not fitting easily into a relational database, like again, that's just one of those things it's never resonated with me.

[00:32:44] **Ben:** It's never felt right. Well, and I'll tell you like the few times where I've really wished that I had more of a flexible schema and maybe I'll create a text column and then I'll throw some Jason in it. Like, I always end up regretting it because at some point years later, There's dirty data in that column structure of that Jason structure is inconsistent.

[00:33:07] **Ben:** It's, keys changed names over time, the casing of the keys and that Jason file has changed over time. And it's like, if I had just had a table that had all the keys that I need, I would know forever and eternity, what was in that table. And I would never have to guess, or never have to worry about cleaning up dirty data.

[00:33:24] **Adam:** Tim Tim is being awfully quiet over there. I don't know if he's got disconnected or what, but, the I'm surprised he hasn't chimed in to tell us how often the Jason column type is in Postgres. And he's not saying anything yet, so he must be disconnected. Sorry we

[00:33:38] **Carol:** might have disconnected.

[00:33:39] **Adam:** but yeah, like that's, that is the thing that I would say if a week goes by and I haven't heard.

[00:33:47] **Adam:** My CEO say, if we only were on Postgres, then this thing that we're trying to do would be a lot easier. And it's 99% of the time. It's because of face on like Jason columns and post-grads

## [00:33:59] Transactions Pros/Cons

[00:33:59] **Adam:** so, pros and cons transactions.

[00:34:03] **Ben:** Yeah.

[00:34:03] **Adam:** yeah.

[00:34:04] **Ben:** Although I do. I don't want to say that transactions are the end all be all I have over time, tried to rely less on transactions by creating actions that can be run safely multiple times that they fail. So, so like one of the use cases we have a lot at work is deleting kind of the parent of this entity hierarchy.

[00:34:24] **Ben:** So you can imagine. Yeah. So, so, like at work we have this concept of documents and documents have screens and screens have comments. And, and so if someone goes to delete a document, we have to delete the document and the screens and the comments, and like all the old versions of the screens and a whole bunch of other stuff.

[00:34:45] **Ben:** And I think early on. As, I don't want to say naive, but as less experienced developers, we would throw that whole thing in a transaction because we're like, well, we've got to delete everything. So it has to happen in one transaction. And then it locks up the database because it takes like 30 seconds to actually delete all that data.

[00:35:01] **Ben:** And then that's causing transaction locks on other things that are going to that table. And then you can start to rethink. And you're like, well, if I delete the less important things first, like I try to delete the comments and the screens first, and I delete the document last then if it fails halfway. The user can still see the document, but it's like half the data's gone, but like, all right. So then they try to delete the document again, and now it starts to go through the lesser important things. And you can build ways that can safely run things multiple times that would normally be in a transaction when the transaction is maybe too expensive.

[00:35:32] **Ben:** But again, like you have to architect your applications to do that.

## [00:35:36] Picking A Starter Database

[00:35:36] **Adam:** Yeah. I mean, I keep coming back to the idea. Like, I don't think that I have come across an application that I couldn't, if I wanted to shoe horn into Mongo DB or couch DB or any of these other, like Cassandra. as long as it's a key value store or something like that, like you can make any application work there.

[00:35:54] **Adam:** Why can't you make any application work? A relational database that, and if your application is like a MapReduce over a crib, I don't even know what word I was trying to say there over a ridiculously large amount of data, like terabytes or petabytes then. Yeah, sure. Like there's having a database specifically built for doing that MapReduce over a large amount of data is going to be faster than trying to do that in MySQL or pull it, God forbid, pulling that into memory and doing it in memory.

[00:36:25] **Carol:** Yeah.

[00:36:26] **Adam:** But aside from that, like your run of the mill, forms based web application, I feel like any database is good enough. Just get your app working. That's all it matters.

[00:36:40] **Ben:** And relational databases are so flexible to your point earlier about you have data, but then you also have to run reports on that data and you don't necessarily know what those reports are going to be ahead of time. Like when you're building an application for the first time, you don't know what it's going to do.

[00:36:54] **Ben:** I mean, you might have an idea, but nothing stays the same and nothing certainly stays the same after users start using it and complaining or having feature requests. To me, it feels like the relational database should be the default choice because it's the most flexible.

[00:37:09] **Ben:** And that potentially as your application matures and you see where there may be bottlenecks or things that are too difficult to do in a relational schema, like then you can start to choose, I think, a specialized database that handles those types of use cases more efficiently.

[00:37:26] **Ben:** It, the idea of choosing Mongo DB or any of the document database. I'm not trying to pick on Mongo DB. That was

[00:37:32] **Carol:** just happens to be the one. Yeah.

[00:37:33] **Ben:** the idea of choosing anything that's not relational by default, seems like you're backing yourself into a corner. don't need to worry about horizontal scalability that comes with like a easily shardable document database when you're just trying to prove the idea of your product.

[00:37:49] **Carol:** Okay.

[00:37:49] **Ben:** I remember listening to a podcast, this guy was talking about, I think he worked on the Amazon database team and he was talking about dynamo DB. And he was saying how amazing dynamo DB is, if you know, a hundred percent, what your queries are going to look like ahead of

[00:38:03] **Ben:** time,

[00:38:04] **Carol:** But

[00:38:04] **Carol:** we

[00:38:04] **Ben:** like, right. He was like, he's like, if you think you can just drop dynamo DB, as in, as a replacement of something like SQL database, like you will be very unhappy.

[00:38:14] **Ben:** Because it will not work and it will be very non-performance or it'll be very expensive.

[00:38:20] **Carol:** That makes me feel way better. Cause that's always kind of been my thought is that. Going that way into a document database doesn't seem like where you flow into it's where you would be starting out at. And I've never been in a position where I know what I'm doing up front to start there. So it's always so ever-changing and I never know.

[00:38:41] **Carol:** So

[00:38:41] **Ben:** Anyway databases. What's up with that?

[00:38:44] **Carol:** what's up with those things.

[00:38:46] **Adam:** Okay. Well, I don't have anything else to add. You guys got you guys done.

[00:38:50] **Adam:** Yeah.done. Getting that off your

[00:38:51] **Adam:** chest.

[00:38:52] **Carol:** info.

[00:38:52] **Ben:** you. Thank you. Had to get on my soap box, I guess.

[00:38:55] **Adam:** right.

[00:38:56] **Carol:** Sad. We lost him. Cause man

[00:38:58] **Carol:** Postgres would

[00:38:59] **Carol:** have been great.

[00:39:00] **Adam:** Postgres Postgres. Yeah. right.

## [00:39:04] Patreon

[00:39:04] **Adam:** Well then I guess that wraps it up. So, this episode of Working Code is brought to you by Postgres that's Postgres. It's just better than your database and listeners like you. If you like what we're doing, here on the podcast, you might want to consider supporting us on Patreon at patreon.com/WorkingCodePod new this week.

[00:39:21] **Adam:** James England. Welcome aboard. Glad to.

[00:39:24] **Carol:** Welcome.

[00:39:24] **Adam:** And so to thank our patrons for their support, they all get an invite to our Discord server. We were hanging out and chat about the podcast and stuff. We have other parts available, like early access to new episodes and our after show. And I realized after I said it. I threw out pros and cons for transactions, and we did that real quick. but regular listeners to the show probably don't know what that is in the after show. we often tackle like rapid-fire topics, pros and cons. We'll just throw something out and you can either do a quick, I'm for it, or I'm against it, pros and cons, or we might back it up with some reasoning and some discussion, whatever.

[00:39:55] **Adam:** so that's what that was when we glossed over that real quick. so if you're interested in more of that, you might be interested in the after. of course we need to thank our top patrons, Monte and Peter. Thank you guys so much for your support

## [00:40:05] Thanks For Listening!

[00:40:05] **Adam:** and if paying for podcasts, isn't your thing. No worries.

[00:40:07] **Adam:** We appreciate you taking the time to listen, and there are some free ways that you can help us out too. You could share the show with your friends and your cohort. Or you can leave us a rating and review on apple podcasts or wherever you get your podcasts. please send us your questions and your show topics on Twitter or Instagram @WorkingCodePod, or you can leave us a message at 512-253-2633.

[00:40:28] **Adam:** that's 512-253-CODE. We'll catch you next week. And until then,

[00:40:33] **Carol:** Your heart matters.

[00:40:34] **Adam:** since Tim's not here.

## [00:40:57] Bloopers

[00:40:57] **Carol:** I know who's going to say it. I thought you were like showing off a

[00:41:00] **Adam:** No. I was like, well, somebody who's got it. Who's going to step up. Cool.

[00:41:04] **Carol:** I think Ben should do it.

[00:41:06] **Ben:** I think Carol nailed

[00:41:07] **Carol:** he's more like mushy than me.

[00:41:09] **Adam:** He's got a bigger heart.

[00:41:10] **Carol:** He's got a bigger heart than me, for sure.

[00:41:12] **Carol:** Yeah. And he said he lost connection.

[00:41:15] **Adam:** And he was blaming Riverside saying it's not his internet connection.

[00:41:18] **Carol:** He's so excited for Hamilton. He wouldn't go like, go ahead and look at this outfit.

[00:41:24] **Adam:** Yeah, he's getting dressed up as king George.

[00:41:26] **Carol:** I love it. I love Hamilton. It's not because it's my last name.

[00:41:30] **Adam:** It's not only because it's your last.

[00:41:32] **Tim:** You know, I couldn't find my tickets. I was like stressing out today. Cause Jason has like season tickets to the Fox and he sold me four tickets of who I

[00:41:41] **Carol:** Oh, nice.

[00:41:42] **Tim:** And so I'm like searching through my email for Hamilton and so much. It was like, oh, not you Carol. I don't want you. I want my tickets. Give me my tickets. Get out of my way, Carol.

[00:41:54] **Carol:** You're not the first person to say that.

[00:41:57] **Tim:** But I don't mean it.
