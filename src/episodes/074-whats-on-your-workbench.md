---
title: "074: What's On Your Workbench?"
description: "This week on the show, the crew talks about what they've been working on recently."
date: 2022-05-11
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/074-whats-on-your-workbench/id1544142288?i=1000560489741"></iframe>

Sponsors

- [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

This week on the show, the crew talks about what they've been working on recently. Adam is exploring the use of AWS (Amazon Web Services) message queues and S3 in order to manage nightly data processing in a way that _won't crush_ his application servers. Tim has been approved to use the national "Do Not Call" list and is now working to integrate this list into his communications workflow. Ben is dealing with post-deployment depression, which is often what happens when he's at the end of his R.O.P.E. And, Carol is de-scoping a massive project down into an MVP (Minimum Viable Product) that can be shipped within a single sprint in order to demonstrate the value-add of the concept!

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/074-whats-on-your-workbench.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** I've tried to do the I young and on the computer and I, for whatever

[00:00:03] **Carol:** Okay.

[00:00:03] **Ben:** I just could never figure it out.

[00:00:05] **Adam:** Well, it's probably dying when you try to open it because you have 170 million unanswered.

## [00:00:32] Intro

[00:00:32] **Adam:** Okay, here we go. It is show number 74. Can you guys believe we are nearly three quarters of a way to a hundred episodes?

[00:00:38] **Ben:** Okay.

[00:00:39] **Carol:** No.

[00:00:40] **Adam:** and on today's show, we're going to be talking about what's on your work bench. we're just gonna kind of go around the horn and talk about what we've been working on and hope that turns out interesting. As usual though, we're going to start with our triumphs and fails and Carol you're up for.

## [00:00:55] Carol's Triumph

[00:00:55] **Carol:** All right guys, last week I had a failure because I just could not get caught up from jury duty and from being out of work six working days, dealing with all of that and just life and. I'm caught up. I am going to call that a triumph and that is worth celebrating. I have my emails responded to you.

[00:01:14] **Carol:** I have the meetings scheduled and I'm balancing the new, promotion along with what I need to be doing really well this week so much. So I'm even writing code and I am ecstatic about that. So, I celebrated it.

[00:01:29] **Ben:** Aren't you supposed to be managing?

[00:01:31] **Carol:** I'm doing both. So I get to manage and I get to be an individual contributor. So that was,that was the stipulation of taking the promotion.

[00:01:38] **Carol:** Was that I didn't want to give up that hat yet because I love writing code. I love doing that part of it. So I wanted to be able to still be an individual contributor and maintain that freshness and what I'm doing. Yeah.

[00:01:50] **Ben:** It's going to be super interesting. Over the next couple of months to see how that balance feels. Because as someone who loves to write code myself, always wonder if I would have the dedication to be a manager or if I'd constantly just be yearning to be all. Let me just squeeze in some code time here.

[00:02:09] **Ben:** Let me squeeze some code time there. I want to say if it's going to tear you apart,

[00:02:13] **Carol:** Well, I hope not. I hope it does not tear me apart, but I'll keep you posted. Hey, what about, you've been with.

## [00:02:23] Ben's Triumph

[00:02:23] **Ben:** I am going with the triumph. And that is that I shipped something at work today. And, it wasn't a huge thing, but, it was one of those things where it's been a feature request from our users for literally years. And I can't even remember why we didn't build it. It's like it took five, four days, I think, like four working days for me to build. And, and I think it's going to actually be something people use. and I just can't understand why it was never actually added to the roadmap. So I'm just excited to, find the gun had done. basically the way, one of the ways that Invision works is you're creating documents. And then you can give people links to those documents.

[00:03:05] **Ben:** Like you can with a Google document or you just send people a link and then they can access a version, like a read only version of it. but the problem is. Is when people go in and change settings for these lengths, it actually, the system generates new links. So it kind of creates these immutable links.

[00:03:21] **Ben:** And, and it's very confusing for people because they want to change the way something works, but then they have to redistribute a URL because now it applies different permissions to the document. And, I built them the ability to just go in and actually change the settings without changing the URL.

[00:03:35] **Ben:** And yeah, and it. It didn't even seem complicated on the onset. So I, again, just like someone in a product level said like, no, we're not going to build this. And then it got put on a backlog somewhere. And I, assuming there were competing priorities and there was a reason that this wasn't built that were valid at the time, but I don't remember what those were.

[00:03:55] **Ben:** So it's weird now to now reflect back and say, what, why was this not built? This was so easy to be. So,

[00:04:02] **Adam:** it could have been based on bad assumptions, just like they were assumed it would take too long or be too complicated or something.

[00:04:09] **Carol:** or somebody went into it and found every hole they could possibly think of that was ever going to happen. And in reality, those holes don't happen. That's what I tend to do anyways.

[00:04:19] **Ben:** Well, that's actually, I mean, that raises a good point. I'll say that earlier on in my career, I definitely felt very compelled to come up with solutions that worked for everyone. And if someone pitched an idea, I was definitely one of the first people to jump in and be like, well, actually that won't work for this various, thin vertical of people who don't use the system that way.

[00:04:39] **Ben:** And if we can't do it uniformly for everyone, then it doesn't make sense. And now, as I'm getting older and I've been working on the same product for a really long time, I'm like, what? If this makes 20% of our users lives better than that feels pretty worth it to me. And we'll figure something else out for those 80% people that it doesn't work.

[00:04:58] **Ben:** And just keep iterating and iterating until we add enough value to enough people that the product becomes compelling.

[00:05:04] **Carol:** I like that approach.

[00:05:06] **Ben:** yeah. So that's me, Adam, what do you got going on?

## [00:05:09] Adam's Triumph

[00:05:09] **Adam:** mine is almost exactly the same thing, except instead of like shipping a feature request. so my triumph is I shipped a thing, but basically, we've had this problem that's been annoying us for, I don't know, six months or more. So we have a, instead of like sending emails to say, the job, succeeded and needing to recognize the fact that you didn't get an email to be aware of the fact that something. We have, we use a service called dead man snitch. and so you're like you have a scheduled task, right. A Cron job and it runs. And the last thing it does when it's done is to just send a HTTP requests, a dead man snitches says, okay, I ran the job. So if it stops making those check-ins then dead man's nature will let us know.

[00:05:54] **Adam:** And we have it hooked up to our ops. Janie. We have a hookup to our Discord and we get emails. It's like all of the alarms, but it's the other way around. Right. Instead of having to human notice that you didn't get an email, you just have to wait for an email or another alarm to show up. and so we've had the, a couple of these jobs for months now that, I guess I'll say like, they'll go into an alarm state and then literally seconds later, they will check in as being fixed working again. And sometimes it's so fast that you get the I'm working again, alarm before you get the I'm broken alarm. and I got one of those last night at like 10 30, I had just, I'd like just, dozed off to sleep. And my wife has like rubbing my shoulder and she's like, you hear your phone going off. Right. And I'm like, huh, I had no clue. and so I woke up and I looked at it and I'm like, it's another one of those things that, it wakes me up just to let me know that it failed and fixed itself in seconds apart.

[00:06:54] **Ben:** I was so annoyed at that. So this. I fixed that. and I w I had another thing too, that I fixed. It was similar, but it's just like these little minor annoyances that you let ride for so long. And then the fix turns out to be so easy. It's like,why have we waited this long? Well, what was the F the fix? I mean, was it that the timing on the, like the window that it has to receive, something was just a little too.

[00:07:20] **Adam:** not a small window, but the way that the windows aligned. So the snitch thing was set up to expect to check in every 15 minutes. And it was looking for that to run like say on the hour, right? So between zero and 15 minutes in between 15 and one second and 30 minutes and et cetera, et cetera, and the Cron job was set up to run.

[00:07:41] **Adam:** Every 15 minutes. So if the job took more than a minute to run, then the check-in would be late at some point on one of those things. And it would just, it would be late by a second, maybe two. And so what I did, I changed the Chron scheduler to just be like two, two minutes later, right. Instead of star slash 15, it was like, okay, run it to at, 17 at 32 and 47.

[00:08:06] **Ben:** the whole, Cron timing notation, every time I've had to deal with it, it just seems. Like both super powerful and incredibly esoteric.

[00:08:17] **Ben:** There was,

[00:08:17] **Ben:** there was a, website.

[00:08:18] **Adam:** I got a Chron tab.guru.

[00:08:21] **Ben:** Is that what it is? The word where you're

[00:08:22] **Ben:** like tells you what it

[00:08:23] **Adam:** I gotta get that a shout out.

[00:08:24] **Ben:** Yeah. Yeah. This is the one I was talking. This was one of the, say I had to do something with a Cron job the other day.

[00:08:29] **Ben:** Oh, it was, I think it was a Netlify. The scheduled function. It uses Cron times to determine when it's supposed to execute. And I had to go to this and it was like, I just had to look at the list of things. There was like a list of common uses that it did. And I was like, yeah, that's the one I want every 15 minutes.

[00:08:45] **Carol:** Yeah, you have to do that. And, the bridge and a lot of the triggers and AWS stuff. So I was like, what are we doing? I don't know.

[00:08:55] **Adam:** Yeah, the syntax is it's. I think it's like, it's relatively easy to read once it's written. You can, if you know what you're trying to figure out, it's relatively easy to, okay. This is every 15 minutes for between these hours or whatever, but just read, like, writing it from scratch is pretty difficult sometimes.

[00:09:13] **Carol:** Yeah,

[00:09:14] **Adam:** . So I guess that's it for me. Tim has definitely been here this whole time. how about you

[00:09:18] **Adam:** man

[00:09:19] **Tim:** Just surprise.

## [00:09:19] Tim's Triumph

[00:09:19] **Tim:** Yeah. I enjoy all your triumphs. They're amazing. I got triumph too. it's a clean sweep.

[00:09:24] **Adam:** from

[00:09:25] **Adam:**

[00:09:25] **Tim:** did I mention, have I mentioned before the show that Postgres.

[00:09:29] **Adam:** no.

[00:09:29] **Tim:** I mentioned that.

[00:09:30] **Adam:** What

[00:09:30] **Adam:** is

[00:09:30] **Adam:** this? What is this Postgres that you speak

[00:09:32] **Ben:** I think maybe once.

[00:09:34] **Ben:** maybe

[00:09:34] **Tim:** Oh,

[00:09:34] **Tim:** it's, it's, it's a JavaScript library

[00:09:39] **Tim:** no. So that's when you guys texted me to say that we were recording. Cause I obviously didn't check my messages. that's what I was doing. I was trying to import, so we're importing the.

[00:09:50] **Carol:** we're

[00:09:50] **Tim:** Do not call registry. So here in the United States, we have a, supposedly you can put your list on the government list and telemarketers won't call you that doesn't seem to stop them.

[00:09:59] **Tim:** However, but yeah, and it will get into what's on my workbench. I'm doing something along those lines, but I was just, I was using a tool to import and it's going to take 54 hours and it was like 24 million records in this CSV file that the government gives you. They give you no automated way to download it.

[00:10:16] **Tim:** And so I found command line called copy. I can just connect to my Amazon RDS copy. I went to go watch a little bit of American idol with my wife and it was done within like three songs. So,

[00:10:29] **Carol:** So he.

[00:10:31] **Tim:** now it's building the indexes on it, which would probably take just as long. So, but yeah, that's just, I, I know most databases have a tool like that, but it was just pretty. To see how much, much more quickly that can be done than the brute force way.

[00:10:46] **Adam:** Yeah, that'll actually kind of tie in nicely to what's on my work bench too. So.

[00:10:50] **Ben:** Well, the other day you were talking about how much you love jar files. Was this relating to that or unrelated?

[00:10:56] **Tim:** No, no, no. Just a hundred percent just taking a CSV file from the government and putting it in, putting it into a database so that we can look up and make sure that our customers aren't sending messages to people that are on the call.

[00:11:10] **Tim:** Yeah. And I was also trying to see, in, in SQL server you have like a no lock hinting. I thought I was trying to see if the database was getting updated because I was impatient. and, but they don't know that I have no lock hinting that a select statement by default does not lock ever

[00:11:25] **Ben:** What would you even have to put lock hinting around

[00:11:28] **Tim:** well, Microsoft SQL server. Sometimes

[00:11:30] **Tim:** if you do a select, unless you specify with no lock, it will try to lock that record that you're selecting. And if you're selecting a bunch of them, while the system is trying to do a bunch of updates, it can cause deadlocks deadlocks is like the biggest problem I've ever faced

[00:11:44] **Tim:** in Microsoft SQL server.

[00:11:45] **Tim:** And I

[00:11:46] **Tim:** never

[00:11:46] **Tim:** run into

[00:11:47] **Ben:** Was it into a new table or

[00:11:49] **Tim:** Brenner database.

[00:11:50] **Carol:** Yeah,

[00:11:50] **Ben:** gotcha. Okay. All right.

[00:11:52] **Tim:** But I, I just didn't, I didn't realize that, that there is no even lock hinting for pre-select statements.

[00:11:58] **Tim:** There might be, but by default it's a Naloxone. Anyway, Postgres rocks.

## [00:12:03] AWS Services For Database Import

[00:12:03] **Adam:** All right. I guess that leads us into a what's on your work bench.

[00:12:07] **Adam:** So, you were talking about importing CSV files, and that's a big chunk of the work that our database does on any given day, just in terms of like volume of data written. we get a full set of database files from every customer every day. Or for, I'll say for most of them, both production and QA, and we import the in is basically a clean sheet of their entire,list of constituents, a bunch of details about them and a bunch of related tables about all of them.

[00:12:34] **Adam:** and we have to import that and that's such a big, Job to do. It can be so taxing on the database and on the application server that I, what I've been working on for the last little while here is, a tool that instead of running that sort of in the main thread and the application server, we're putting that in a queue and working on it.

[00:12:52] **Adam:** off of the main server, even it's, we're running an Amazon ECS instance, a Docker container, and it pulls jobs out of a queue. And then, it works on those jobs and we actually have like, oh gosh, what is it? I think we

[00:13:06] **Carol:** you,

[00:13:06] **Adam:** four production ques and two QA queues because we're partitioning based on the database partition that you're in.

[00:13:14] **Adam:** And then also. whether the job that you're trying to run as fast or slow, so you might be on like database one fast or database, two slow queue, depending on what you're trying to do. So it's a very complex thing. But at the end of the day, what is trying to do is efficiently, import CSV files into the database.

[00:13:33] **Adam:** And another really neat thing is we finally figured out how to do, so that we're using. And it has a low data from file or loaded in file. Well, I guess in Amazon's fork of MySQL, I guess it's probably technically they call it a Rora, I think. But, they have low data from S3, so we don't even have to download the file in order to yeah.

[00:14:00] **Adam:** And our customers are already putting it on S3. They put it on S3 and then they call us to let us know that it's there, but we have like a shared. and so we do actually download the file because we do some validations on it first, but we download the file and then we just tell RDS. Okay, go ahead.

[00:14:14] **Adam:** Once we're sure it's valid. We said, go ahead and import this file. and it is super fast, impressively, fast,

[00:14:21] **Carol:** so side note, they call you every morning to tell you they've uploaded a file.

[00:14:26] **Adam:** not on the telephone, and API.

[00:14:28] **Carol:** I just, I wanted to make sure I understood the communication here. Okay.

[00:14:32] **Adam:** Yeah.yeah, no, I mean, it's a valid question. it's just been such an interesting thing to work on. Remember, I think I had a fail recently that like I was working on a project that was super interesting in terms of like the technology that I was working on, but I just was not feeling motivated.

[00:14:48] **Adam:** it's this project, like, it's so many interesting, like this is my first thing, working with a cute.

[00:14:54] **Carol:** fuse

[00:14:54] **Adam:** and,I'm working with Lambdas to do like the dead letter queue. I've got an ECS,the whole ECS like stack, right? You have task definitions and services and containers and stuff.

[00:15:06] **Adam:** And it's, I think the only brand new thing for me in all of this is the queuing, but still it's been super interesting. And, we are so as

[00:15:16] **Adam:** a. Yesterday, I think like yesterday midday, this is now deployed quote unquote to QA for one customer. Thank you. Feature flags. and, and there, they were really impressed to see it running in QA.

[00:15:30] **Adam:** it's working really well. and so now,

[00:15:32] **Carol:** now, like

[00:15:34] **Adam:** I guess all that's left to do is, the last 90%, right? The first 90% takes half the effort, the last 10% takes the other half the effort, which it shouldn't be too bad. Right. I've got a bunch of SQL scripts that are needed to move from one repository to another.

[00:15:47] **Adam:** And there are some, so the, this whole tool. is like, basically we want to run this job that imports these files, and some of the steps of the import are complex enough that you can't just do it with SQL. You need some app server functionality. and so. Tool is, has a list of script files and they could be either SQL files, which it'll like, read the file and run the SQL, or it can be the previous app server was called fusion.

[00:16:13] **Adam:** So it's a CFM file and it would just execute that file and whatever it was in there would get executed. And now I'm converting that to be JavaScript. So it runs on node in our ECS container,

[00:16:23] **Carol:** that's probably going to be faster to you than what you were running on ColdFusion,

[00:16:27] **Adam:** It has been surprisingly good.

## [00:16:29] CloudWatch Logs

[00:16:29] **Adam:** I guess another really interesting thing is here. So, we've been using CloudWatch logs for a long time and we discovered, I think they've been continually improving CloudWatch logs, especially log insights. And we discovered that if you. Emit logs as Jason. So instead of saying like, the job has done, this was the job name and it took this long.

[00:16:51] **Adam:** If you just admit an object that contains like consistent key names. So you can say, customer is XYZ and environment is production. And, job name is warehouse and duration is this. You can actually like query that in CloudWatch log insights. It like, kind of does a MapReduce on the whole, on all of your, and you choose which log streams you want to.

[00:17:12] **Carol:** to query.

[00:17:13] **Adam:** and it finds all those log statements for you, which is super, super cool because previously that was my biggest frustration with CloudWatch logs is trying

[00:17:20] **Adam:** to

[00:17:20] **Carol:** you. Can't get

[00:17:21] **Carol:** through

[00:17:22] **Adam:** Yeah. Trying to find the needle in the haystack. You know, you you're running so much. The whole point of the thing is like you're running so much stuff in parallel.

[00:17:30] **Adam:** Right? You've got that's like the big selling point is you can run a ridiculous amount of computing and. Okay. And it all spits out a bunch of logs and you can aggregate all those logs, but then trying to find something when you're debugging or whatever, it can be a nightmare and this, using log insights to, to query through it has been phenomenal.

[00:17:49] **Carol:** Yeah. when I first got into Sumo logic, that was the very first thing I looked at. I was like, can we filter out all of these messages and sure enough, I can take all of that and create different columns for it. So then I'm like, oh, I can see this is on dev. I can see this is on QA. I can see what function this come from.

[00:18:05] **Carol:** I was like sold, give me some oat logic and get it fast. I'm like, cause we can't get through any logs in any AWS environment without it.

[00:18:13] **Adam:** Yeah.

[00:18:14] **Ben:** The issue that we run into with logs is talking about consistent keys in your log structure is like one team, a log user IDs as an integer. And then another team will log user IDs as a string. And then we go to search for it and whatever powers, all the indexing under the hood just gives up.

[00:18:32] **Ben:** It says, well, you gave me both. So I'm going to give you back neither. You can either search for them as string or as number, because I don't understand what it is super

[00:18:39] **Carol:** Oh, that's awful.

[00:18:41] **Ben:** Yeah.

[00:18:42] **Tim:** Yeah. We have sort of a challenge. Cause not a hundred percent of our stuff is, in the cloud or AWS or Azure, actually we have somebody to buy us some Azure and then some on-prem, anything that. PCI related credit card related. We have to be on prem. so we're taking a look at, cause our logs are everywhere.

[00:18:58] **Tim:** one of my developers suggested elk stack,

[00:19:03] **Tim:** elk. It's the same people that created Alasta search and they sort of have a, you can sort of build your own kind of logging things. So I don't know, we have a research ticket for it. We'll take a look about that.

[00:19:16] **Ben:** Yeah, we did. We use a service called cabana a long time ago, and I think cabana was basically like a productized version of the elk stack. So I was like managed.

[00:19:26] **Tim:** Yeah. That's what else stands for Elasticsearch

[00:19:29] **Carol:** with the ball

[00:19:29] **Ben:** Okay. But the query languages for logs are very powerful, but also very esoteric sometimes.

[00:19:36] **Adam:** I actually kind of like what you get for CloudWatch insights. It's in some ways, very similar to SQL, but in other ways, not. When you open it up, it's got sort of a default query in there that has, 50 to 75% of what you would use on any given query, list these fields, sort by this and, filter by this sort of thing.

[00:19:58] **Adam:** And so you can either, it gives you a nice little reminder of what's available, in terms of like, operators, I guess you would call those sort and filter. and, this index is right there. So it's just like a quick modify.

[00:20:08] **Ben:** That's nice.

[00:20:09] **Carol:** I like when it gives you the nice interface where you could do the downs, like, I want to find this category in here. And then from that you have the little toggle button that says, show me the SQL for it, or the things called, like JC. Cool. I don't know what it's actually, I've never read the whole sentence.

[00:20:23] **Carol:** Right. So I just toggle it and then I can see what it used to create those filters. I'm like, oh, now I'm understanding. And now I'm learning how to write this myself.

[00:20:33] **Adam:** Yeah. And then in insights, when, after you run a query and it starts to like read through your data, it notices when you've got like, okay, you searched for these things and I'll give you your results. But then over here on the side, it says, 75% of the rows that returned also have these fields in common.

[00:20:50] **Adam:** Do you want to filter in any of

[00:20:51] **Adam:** those? It's a pretty nice.

## [00:20:54] SQS

[00:20:54] **Ben:** I want to go back to your message queues for a second.

[00:20:57] **Adam:** Yeah.

[00:20:57] **Ben:** what actually goes into the message item on the queue? Cause you're,you're asking the database to import an entire file from S3. So I assume it's not the file itself in the queue cause that's probably too big for QS anyway. So what does the message have?

[00:21:13] **Adam:** The, so if I'm not mistaken, by default and Amazon SQS queue, the message is like limited to like 256 characters.

[00:21:22] **Ben:** think it's okay.

[00:21:24] **Adam:** I don't think it's kilobytes. I think it's like bites, but anyway, it's not that much. anyway, so what we're sending is we're sending a Jason packet that contains a few things, right? So.

[00:21:36] **Adam:** That just uniquely identifies the request so that if we get duplicates, they're easy to ignore. actually, so I did that specifically because I talked to a couple of people that have done a bunch with SQS. Thank you, Twitter. I was tweeting about this stuff and people were like, you should do this, you should do that.

[00:21:50] **Adam:** And I'm like, actually, would you mind having a conversation with me? Like, let's go over here in DMS where we can have more than 280 characters and, chat about. And I got a lot of really great advice. One of which was like, even though Amazon says, it's a guarantee. If you use a Five-O queue, they quote unquote guarantee the exactly once delivery.

[00:22:09] **Adam:** But he was like, that's kind of hogwash. Like they try, but they don't guarantee. Yeah. they try, they give it the old college try to do exactly once delivery, but you might get it twice. You might get it. Never, you never know.

[00:22:23] **Adam:** and

[00:22:23] **Carol:** And so,

[00:22:24] **Adam:** yeah, so it contains the job ID. It contains the, like the name of the job that they were trying to do, I guess, hang on. Maybe it would take, make more sense if I took you back a step in the job, the. Feature that we're replacing that did it inline on the app server. Right. So they would make an API request and they would say, okay, we want to run the warehouse job.

[00:22:42] **Adam:** The file name is warehouse dot CSV. when you're done email these people and let them know, and, we have the feature, but I don't think anybody actually uses it where we can send you a web hook when it's done so that like programmatically, and you don't have to check your email, like some bag of meat.

[00:22:58]

[00:23:01] **Adam:** I think that's it.

[00:23:02] **Ben:** Well, so, so do all of those phases now become different messages on different cues? Like here's the message for processing the file and like, here's the message for sending the email.

[00:23:13] **Adam:** No. so the cue is just a request to do an import. that's what, we're, what we're putting in the queue. Each item in the queue represents one request to do an import. and if you can imagine it just at first with a single queue, so all requests for all customers across all environments would just go into this one queue.

[00:23:30] **Adam:** Be roughly first in, first out. So not a quote-unquote standard queue we've got, and we're talking about AWS SQS. a standard Q is roughly first in, first out. whereas the Five-O queue is like guaranteed first in, first out. So as long as you're not dealing with like millions of messages, you're probably going to be FIFO or close enough to it that you don't care.

[00:23:49] **Adam:** and so the first, There's a thing, looking for messages to find the first message and it does the work, right. So it's job then is, import the file, delete the message and send whatever notifications are necessary.

[00:24:02] **Ben:** And do you have a single worker, like is only one consumer pulling messages off the queue.

[00:24:07] **Adam:** so in our imaginary single queues scenario. Yes. So, okay. So that's the basic gist of it. Then they make an API request to let us know that they've sent us a file on S3 and we take that API request the details of it, and basically push it into our SQS queue. We massage it a little bit. Like we add our grid to indicate this was the request ID.

[00:24:29] **Adam:** and, and then the API returns like, okay, your request has been queued instead of the file is now. importing your request has been queued, wait for your email sort of thing. so then, my initial plan was from what I had, was able to figure out on my own for reading was I would add the item to SQS and then I would also manually trigger an SNS message, simple notification service, and that SNS would trigger a lane.

[00:24:56] **Adam:** And that Lambda would go, okay, I need to start up the processor. So the Lambda would then, do a quote unquote deploy. I mean, it's just changing some settings on the ECS service. So elastic container service is like a Docker container orchestration thing. It can, auto-scale that sort of thing. You can set it to zero desired workers and it'll just shut everything down and then you can programmatically say, okay, I want three right now.

[00:25:23] **Adam:** And it'll spend three up and they'll start doing whatever their job. So the plan was the, we would cue the message and SQS fire off an SNS message, which would start a Lambda, which would, do a quote-unquote deploy VCs to tell it, okay, go from zero to one workers because there's work to do now. So basically you can kind of think of our ECS approach as Lambdas that can run for more than 15 minutes.

[00:25:47] **Adam:** Right? Like I just want to start a worker, do some work and then shut down. and that was our, my plan going into it with a way to do that. I started explaining that to one of my coworkers and he's been poking around in a vent bridge a lot lately and he's like, I'm pretty sure you can do that with just like regular CloudWatch alarms now. And so yeah, we looked at it and you can, it's. I'm not even going to try to describe it here, but I can tell you if you need to know this, hit me up on Twitter. I'll give you some details. Maybe I'll have to write a

[00:26:11] **Carol:** write a blog

[00:26:12] **Carol:** post.

[00:26:12] **Adam:** but, basically you can create a CloudWatch alarm and that alarm can automatically scale up and scale down your ECS service

[00:26:18] **Ben:** Th this is instead of the SNS.

[00:26:21] **Adam:** Correct instead of SNS. So now that, that was my plan. Right? So playing was API. Does it SQS and an SNS, the SNS triggers a Lambda Lambda triggers, ECS to scale up when the ECS task would scale up. What it does is it just checks the SQS queue. And if there's work to do it grabs that first item off the list.

[00:26:40] **Adam:** And does the work when it's done it checks, is there any more work to do if not.

[00:26:45] **Ben:** So it'll keep pulling things off the queue until there's

[00:26:47] **Ben:** nothing left and then it shows. Gotcha. How does it shut down?

[00:26:51] **Adam:** So unfortunately, the way we're doing it right now is we have two alarms for each queue, the queue,you can monitor the number of visible messages in the queue. And so when it goes above zero, I trigger a deploy to scale up.

[00:27:06] **Adam:** And then when it goes down to zero and when it's been zero for long enough that I'm. Extremely confident that there's nothing still processing in the background. Then I

[00:27:17] **Carol:** I tell them

[00:27:17] **Adam:** down.

[00:27:18] **Ben:** Gotcha. So the worker is not like self terminating, cause it has nothing left to do. It's more like it sits idle for too long and something else terminates it.

[00:27:25] **Adam:** It does actually quit the process, which triggers another container to spin up, but it takes seconds, for that container to come up. And then it waits 10 seconds to get a message From sq. And since nothing comes down, then it just like logs a thing that says nothing in the queue and shuts itself down and

[00:27:44] **Adam:** It repeats over and over until, it's told to

[00:27:47] **Carol:** to scale down

[00:27:48] **Adam:** So, okay. So that was all hypothetical single queue right now. You can just imagine, like, we have two databases and we have QA and production, and then we also have, some jobs that we know are going to be fast. Right? Some jobs take a minute or two or max, like five and some jobs take somewhere between 20 and 40 minutes to run. And you don't want to mix the two. Yeah. You don't really want to mix the two because you really want those fast ones to just get out of the.

[00:28:13] **Adam:** and so we have a fast Q and a slow queue for each of the databases for each environment except QA. We only have one, one QA databases that all customers share.

[00:28:24] **Adam:** And so we have, it's one QA database server. So it's sharing physical resources, but separate databases. and so we have, DB

[00:28:31] **Carol:** be one,

[00:28:31] **Adam:** production fast DB, one production, slow DB, two production, fast DB, two production, slow QA, fast and QA slow. and so for each of those cues, there needs to be two alarms, one to monitor when the message goes from zero up to anything above zero and spin up, and then another alarm that watches for it to have been zero long enough to shut down. And then I have separate monitors that just exist for the purpose of letting us know that stuff has been in the queue for so

[00:28:58] **Carol:** so long

[00:28:59] **Adam:** that something is wrong.

[00:29:00] **Carol:** That's

[00:29:01] **Carol:** interesting.

## [00:29:02] Workflow Errors

[00:29:02] **Ben:** They could the Q stuff where I get, I constantly get tripped up. And I alluded to this earlier, when I was asking about the emails that you have to send back to say, Hey, we've done the thing. Eh, cause something can crash it.

[00:29:16] **Ben:** Time for

[00:29:16] **Ben:** any reason, like cosmic bit flipping due to sunspots, right? Like, so it's, I guess at some point it's theoretically possible that you have pulled down the. You've processed it. And then just before you're going to send the email to say, Hey, we're done the server crashes or, like Amazon could just take your ECE instance away and be like, Nope, sorry, you don't have this anymore.

[00:29:39] **Ben:** and w how do you deal with that? Like, how do you, what happens then? Does that email just never go out or does the whole job, every process and like, item I didn't potent sort of way.

[00:29:48] **Adam:** I think in the exact scenario that you described, we would be mostly fine, except that, like you said, that email notification wouldn't go out. But, one of the early steps in that handling, when it starts to process the item from the queue, is it checks to see if that quid that's in the queue message has already been written to a table as like I've processed this.

[00:30:11] **Ben:** Ah,

[00:30:11] **Adam:** and so I, and I forget whether, right. I forget whether writing that record, comes before or after sending the success or failure notification, but it's, the last couple of things that happen. And so it's possible, I guess, maybe depending on the order of those things, that the, either the record got written before the email was sent and then the job died, or the

[00:30:33] **Adam:** email was sent

[00:30:34] **Adam:** and the job died before we could write that.

[00:30:36] **Adam:** Right.

[00:30:36] **Carol:** that record.

[00:30:37] **Adam:** And in that case, like in the first case, then there will be no email notification, but we would have record of it internally. and we already have like a page that shows us the last time that the files were imported. So if they ask, we can just be like, yeah, it was successful. and, the, I guess the other case is it would just get imported again, right.

[00:30:55] **Adam:** if they never got their

[00:30:56] **Carol:** their

[00:30:56] **Adam:** emails,

[00:30:56] **Carol:** email,

[00:30:57] **Adam:** I don't know. I mean, I guess they got their success emails, so they wouldn't feel the need to re-trigger it. But,if for some reason they did and we didn't have record of it, then we would just reimport it. And it's not that big of a deal, but the import itself is idempotent.

[00:31:10] **Ben:** yeah.

[00:31:10] **Adam:** So

[00:31:11] **Ben:** Right. Because you're basically resetting the database more or less. It sounds like.

[00:31:15] **Adam:** Yeah. I mean, basically it's import all this data into some table underscore new and the very last step of the import is drop table XYZ, renamed table XYZ, underscore new to X, Y.

[00:31:28] **Ben:** Sneak attack. You know, this stuff is so fascinating to me. I just had to build something to work, where I had to make three separate API calls and. I kept having to pull one of the guys from the other teams in and I'm walking through my code and I'm like, it could die here. die here. It could die here and I have to rerun it again.

[00:31:47] **Ben:** And I'm like, what happens when I make the first API call and then it dies. And then I have to make that other API call again, like, do I get a 500 error? Do I get a 4 0 9 conflict? Does it just give me a 200 that it already exists? Like a, and then, it's like, it's stepping through that all these failure cases, trying to figure out how to.

[00:32:04] **Ben:** To understand how to replay parts of workflows. it's it's very it's. I dunno. It's very exciting to put code like that together. Like forces you to think through all the sad paths.

[00:32:14] **Adam:** You are a masochist.

[00:32:17] **Carol:** Yeah. He's worrying about cosmic bit flips. yeah.

[00:32:21] **Tim:** sake.

[00:32:22] **Carol:** Solar flares.

[00:32:24] **Adam:** so it's funny the way you described that reminded me of the way that my kids talk about what I do, right. They're like, oh, you just sit at a computer all day and just like mash on the keyboard. And I'm like, it's a little more complicated than that.

[00:32:37] **Carol:** I'm kidding.

[00:32:41] **Ben:** There's one line from one of the, I think it must be the first oceans 11 movie. And I don't know why this just tickles me, but I, it will forever be with me, George Clooney and Brad Pitt are talking about how they actually have to break into the safe. And they're like, yeah, we have to get through all the security guards and then we have to get through this elevator that has motion sensors and special keys.

[00:32:59] **Ben:** And then we have to get down to a special volt that has pressure detectors on the floor. And of course we only have 30 seconds till the SWAT teams are alerted. And Matt Damon's like, oh, so it's a smash and grab kind of job. It's a little more complicated than that.

[00:33:16] **Tim:** Hey, my index finished.

[00:33:18] **Carol:** Yay. Yeah.

[00:33:20] **Tim:** Yeah. So it's over two gigs of D the text file itself is two gigs is, and the only thing it is it's area code, comma, phone number.

[00:33:29] **Carol:** 24

[00:33:30] **Tim:** 24 million records of that, the index gets a big, the index is

[00:33:35] **Tim:** 7.3

[00:33:36] **Carol:** gates.

[00:33:37] **Ben:** Nice. Nice. Nice.

[00:33:39] **Tim:** But yeah, I did. So I did as select, on my phone number and it, two minutes it'll still run on.

[00:33:45] **Tim:** So now it comes back within,

[00:33:48] **Carol:** Yeah, the second.

[00:33:48] **Tim:**

[00:33:48] **Adam:** The way it was two

[00:33:50] **Tim:** millisecond. index.

[00:33:52] **Tim:** two minutes before and now it's like zero milliseconds.

[00:33:56] **Ben:** nice

[00:33:58] **Carol:** That is one of the things I've never wrapped my head around very well is database indexing. I don't do a good job at that. I didn't like I've never really had to do it. And now I have DBA that handle it for me. So I still don't have to know it, but I know that if it's wrong, it can go bad really quick.

[00:34:17] **Carol:** You won't find anything. Everything will crash on you. And if it's great, then nobody notices because they're just happy. They get their data back. So.

## [00:34:25] Postgres

[00:34:25] **Ben:** I have a question about Postgres. So we're talking about message cues, and I'm always impressed with what Postgres actually has baked into it out of the box. And as much as I love the idea of spinning up an Amazon message queue, or like a rabbit MQ in most scenarios, I already have a database working in my application.

[00:34:47] **Ben:** Does PostGrest come with. Poor man's message queue like special API to just use

[00:34:53] **Ben:** this data

[00:34:53] **Ben:** table as

[00:34:54] **Ben:** a

[00:34:54] **Carol:** uh,

[00:34:54] **Ben:** queue.

[00:34:54] **Tim:** that I'm aware of. I'm sure I'll be corrected if I'm wrong. But

[00:34:57] **Carol:** yeah,

[00:34:58] **Ben:** feels like something they should just

[00:34:59] **Carol:** odd use

[00:35:00] **Tim:** this seems like an odd use case

[00:35:01] **Tim:** for a database to me.

[00:35:03] **Ben:** Yeah. A hundred percent. But sometimes it's nice to just not have one more technology to spin up, Especially if you're in a situation like Adams and I'm not trying, this is not throwing shade at anything Adam is doing, but I'm thinking more about myself where it's like, I get so afraid of spinning up new technologies.

[00:35:20] **Ben:** Cause, cause it's like just one more thing that can fail. Especially in a situation like, well, you're talking about where you mostly have one worker and it's not like, it's not like the problem you need to solve is queue contention where I have a bunch of different consumers trying to pull from the queue.

[00:35:35] **Ben:** If I just have one consumer, it's like, if I just had a simple data table that could sort of act like a queue, like maybe we just cut out one more thing. And again, I'm not trying to say Adam should do this. I'm saying more like, if I wanted to build a poor man's. It'd be cool if the database just made

[00:35:51] **Ben:** that a little bit

[00:35:52] **Tim:** I don't know, we've got just a simple Google search. What I'm finding is that it does have a listen notify event and S but you still would have to use something like rabbit, MQ, and a plugin for the listener

[00:36:03] **Tim:** exchange. So

[00:36:05] **Ben:** Gotcha. Gotcha. Gotcha.

[00:36:07] **Tim:** that rabbit MQ would talk to your

[00:36:09] **Tim:** database and look, listen for the notify event.

[00:36:11] **Tim:** And then it would aggregate the messages and create the QS. And

[00:36:14] **Ben:** We do run into a situation at work where like once every nine months rabbit MQ will just stop responding for no particular reason. Like if you look at rabbit MQ, it looks healthy. And if you look at the application servers, they look healthy and messages are going into rabbit MQ, but nothing can read from it. And they just restart rabbit MQ and it starts working all of a sudden we can. Yeah, we just

[00:36:39] **Ben:** can't

[00:36:39] **Ben:** figure out what the

[00:36:40] **Ben:** heck is that.

[00:36:40] **Carol:** Do you guys automate a restart on it then? Or do you just wait for it to die?

[00:36:44] **Ben:** no. the platform, the SRE is the site. Reliability engineers have to go in and cycle the pods down one at a time. it's a huge pain, but we

[00:36:53] **Ben:** don't know what else.

[00:36:54] **Adam:** oh, like how many servers do you think are out there? Like maybe in percentage of just, average servers in the cloud, do you think people have configured to just like. Restart every Saturday morning, because if I don't then stuff gets jus just for the reason that if I don't then, eventually after two weeks or after, 50 days or whatever stuff just gets starts to get ugly stuff starts to go over.

[00:37:18] **Ben:** Well, it's really funny because our teams, we deploy pretty regularly at work. And then around new years we usually have a deployment freeze just because we have limited staff. And like a lot of people are taking vacations around new year. And you'll see. So it'll be like, no one can deploy between, the day before Christmas and like the two days after new year or something, just because it reduces the chances that something will explode.

[00:37:43] **Ben:** But because of that, there's no automatic cycling of the pods or, the deployments we're not cycling. And like two, three days into that, you'll see stuff just suddenly start to break that never broke before. Like suddenly people are running out of memory and CPU's are spike and you're like, oh yeah, there's just serious problems that were coincidentally taken care of by the fact that we're deploying, once a day.

[00:38:05] **Adam:** Yeah, those memory leaks and whatever that just don't have time to be.

[00:38:09] **Carol:** You clear it? Yep.

## [00:38:12] Do Not Call List

[00:38:12] **Tim:** So, I mean, I've gone though. My work bench, so this. We it's early in the week and Mosul end of last week and working on, so we have tools that, basically look for events in insurance company's life cycle. your policy is going to cancel, you got a payment due or you're having an automated payment that just declined or an automated.

[00:38:36] **Tim:** That cleared, sending out emails and SMS messages and Mo most of that stuff was done. The part that I've been really been working on is a tracking the delivery, right. Having it. So we can say with a degree of confidence that the SMS message was delivered or the email didn't matter. so working a lot with callbacks building channels for callbacks to call a page to say this email was opened as, this SMS message was blocked because, it's an invalid number or it was blocked because they opted out.

[00:39:07] **Tim:** and then also doing research on the, do not call list, on getting that, of course the government, you sign up for an account, if you are a telemarketer, They charge you $19,000 a year for the entire list of like the entire country. But if you're not doing it, if all you're doing is just like, telling a person, Hey, you have a business relationship with them already.

[00:39:28] **Tim:** And it's like, this is about to happen on this, this service that you signed up for, supposedly you're exempt, but the company I'm working with. They're afraid of litigation. So they wanted me to make sure that we got this put in place, so sign up for it and they go, right. W could be, two to three weeks before we approve here.

[00:39:47] **Tim:** And I just got the email today that I got approved. So I went in there and download it. That's what I was working on when you guys called. But, yeah, just, it's just fun. I like playing with the data. I like working with the callbacks and just seeing, you send something out and then another service like syndrome.

[00:40:01] **Tim:** void provide Twilio, basically send you data back so you can track all that, have a tying in a good that ties in so that you can track everything and report on it. So I've been working on.

[00:40:12] **Tim:** I'm Pretty

[00:40:13] **Tim:** fun,

[00:40:14] **Tim:** not as cool.

[00:40:15] **Tim:** as message queues and all that

[00:40:16] **Tim:** stuff, but

[00:40:18] **Carol:** I was like, yeah, why didn't you put it in a queue, Tim? Gosh,

[00:40:22] **Ben:** Do you get like monthly updates to that

[00:40:24] **Ben:** list.

[00:40:25] **Ben:** How does that work?

[00:40:26] **Tim:** They update it daily. So

[00:40:29] **Tim:** I think double check on this, but I think if a person has signed up and they've been on the do not call list. for more than 18 days and you, and you call them.

[00:40:38] **Tim:** with a telemarketing, then That's a

[00:40:40] **Tim:** violation. but honestly I've never found how you do anything to these people. Right. I Get calls all the time and I'm on the list. I look myself up. I've been on the list for a long time and I don't know how you. because supposedly you can Sue them and get thousands of dollars for them having called you.

[00:40:58] **Carol:** but

[00:40:59] **Carol:** I don't know how to do that.

[00:41:00] **Tim:** don't think anybody

[00:41:00] **Adam:** I think it, it must have something to do with how easy it

[00:41:03] **Adam:** is to spoof a phone number, because it's like, how are the, how are

[00:41:07] **Adam:** you somebody that wants to Sue them, going to

[00:41:09] **Adam:** know who to Sue? Right.

[00:41:11] **Adam:** You get a phone call. You have no idea where it really came

[00:41:14] **Adam:** from.

[00:41:15] **Adam:** You just know they want you to give them money ostensibly, to renew your car,

[00:41:20] **Carol:** your

[00:41:20] **Adam:** extended warranty,

[00:41:22] **Tim:** All right.

[00:41:22] **Adam:** and

[00:41:23] **Tim:** This is my last notification,

[00:41:25] **Adam:** yeah,

[00:41:26] **Adam:** except the one that we're going to call you

[00:41:27] **Adam:** tomorrow. And the day after

[00:41:28] **Adam:** that, and day after that, I feel like $19,000 is a pretty cheap source of phone numbers that they

[00:41:36] **Carol:** that they could.

[00:41:36] **Carol:** be called.

[00:41:42] **Ben:** Well, and half the calls that I get on my iPhone now

[00:41:44] **Ben:** say spam

[00:41:45] **Ben:** risk in the actual phone ID. I don't, I wonder where getting that information.

[00:41:52] **Tim:** Probably the carriers like

[00:41:54] **Tim:** tracking the number of calls or doing.

[00:41:56] **Carol:** Yeah. It's probably carrier. Not necessarily your apple. Yeah.

[00:42:00] **Carol:** Yeah.

[00:42:02] **Ben:** It

[00:42:02] **Ben:** makes

[00:42:02] **Carol:** So back to your updates real quick. So are you going to write something that pulls the data daily for an update or what are you planning on

[00:42:09] **Tim:** Yeah. that?

[00:42:09] **Tim:** I haven't figured out yet? Cause I, because like I, said, I can't, I haven't found a way to automate it. You have to log in and every time you log in, they call you with anonymous. Your number is 7 6 5 4 3 2. And then you type that in your log in. So there's, I don't know how an app, it's just, I use just.

[00:42:27] **Tim:** once a week, have a person go download it and FTP it to a site and we'll upload it to a S3 bucket and we'll parse it.

[00:42:35] **Carol:** you have voice automated phone systems already, right? So you should just give it a number habit, call it, have it record the number for you and do it for you.

[00:42:45] **Tim:** still don't know how to

[00:42:46] **Tim:** log in and then downloads.

[00:42:48] **Tim:** So

[00:42:48] **Tim:** yeah.

[00:42:50] **Adam:** That's definitely the future that we're heading towards, right. People are going to start selling services that exists to intercept other like robotic phone calls or whatever services and do work for you that currently is supposed to be done by a human.

[00:43:05] **Tim:** I'll have it Intercept the spam call and then automatically send the, the notice.

[00:43:10] **Tim:** of the lawsuit. And I'll just, you know, as many calls as I get, I'll never have to work again.

[00:43:16] **Adam:** I want like,

[00:43:16] **Adam:** maybe I'll like record a voicemail. It's like, if you're

[00:43:18] **Adam:** calling about my cars,

[00:43:19] **Adam:** extended

[00:43:20] **Carol:** warranty,

[00:43:20] **Adam:** one. And just like, try to keep them on the line as long as

[00:43:24] **Adam:** possible without actually having to be there.

[00:43:26] **Tim:** I mean, with the exception of my parents, most people are normal human beings. I text you first,

[00:43:32] **Tim:** like, Hey, I'm

[00:43:32] **Carol:** Hey, I'm going to call you.

[00:43:33] **Tim:** like you.

[00:43:33] **Tim:** Okay.

[00:43:35] **Adam:** I don't really do that, but I, if I don't recognize a number and I'm not expecting some sort of like, important phone call from a number that I won't recognize, like a doctor's office or something, then I

[00:43:46] **Carol:** And

[00:43:46] **Adam:** won't answer.

[00:43:48] **Ben:** Absolutely.

[00:43:49] **Adam:** that's become a little bit problematic because now our work, like we have a Twilio provided work phone line, like a company line.

[00:43:58] **Adam:** And my extension on there just goes to my cell phone. So occasionally I'll get voicemails from, one of my customers and it's like, I'm trying to reach you about such and such problem. And I'm like, well, yeah, sorry. answer my phone.

## [00:44:09] ROPE

[00:44:09] **Carol:** So yeah, my topic is actually related to my triumph being that I shipped something. And, the thing that happens after I ship is I go into this. Postpartum depression. And I feel like,I feel like postpartum is actually kind of accurate because you're sort of birthing something into the world except like I didn't grow it in my tummy.

[00:44:30] **Ben:** Like women do. I grew it in my brain and I gave it out into the world. And then after it's gone, I feel like a little sad and like a little empty. And, I had this man. This kind of rich Armstrong, who is my engineering manager a couple of years ago. And he had this thing that he called rope R O P E, which stood for responsible, organized.

[00:44:54] **Ben:** Productive and effective and the ideas that, you sort of gradually become more engaged and more effective in a task until you finish it. And then you kind of, in my case, I go into my little depressive cycle and then I have to start back at our, so I've shipped. And now I got to go back to our, which is reliable. I just have to show up, like I just have to reliably show up to work and like, that's the bar that I'm setting for myself. I don't have to worry about anything else. Then once I've done that I can move on to oh, organized. I can start to get organized about what I want to work on next. I can think about my backlog.

[00:45:32] **Ben:** I can think about the maybe epics I want to create and just start to gather my thoughts and start to point myself in a particular direction. And then I can move on to P productive. And that's like where I'm probably fleshing out tickets. And I'm actually maybe starting to think about how I want to put this work together and maybe I'm starting to write some code.

[00:45:50] **Ben:** And then finally, I'm starting to build up all this momentum and this mental energy, and I can move on to E effective. And like now I'm just starting to crank out code. I'm moving tickets across my Kanban board until eventually I finished all my work and I.

[00:46:04] **Tim:** shift,

[00:46:06] **Ben:** And then I get my postpartums again. and I just start back at the beginning of my rope

[00:46:11] **Adam:** That sounds like a really depressing cycle, man.

[00:46:16] **Ben:** it,it is

[00:46:17] **Ben:** sad.

[00:46:18] **Ben:** I mean, like it's, I should.

[00:46:19] **Carol:** I showed all

[00:46:21] **Ben:** And then I make these like, demo videos for internal stuff at work. And I'm super excited, emojis everywhere and, rocket ships and like party parrot. I don't know if party parrot is like a generally known thing or if that's

[00:46:32] **Carol:** Yes, it is. I use it all the time.

[00:46:34] **Ben:** I'm frigging party parrot like all over the place. Right. And that lasts for like two, three hours. And then all of a sudden, just like

[00:46:41] **Carol:** Yeah

[00:46:42] **Ben:** now I'm sad.

[00:46:44] **Carol:** onto the next

[00:46:45] **Adam:** Yeah.

[00:46:47] **Ben:** Yeah, I get low-key and then I got to figure out what are you aware? Where to go next? And, so that's where I met. I'm currently sort of combing through the backlog and looking to see where there might be some missed opportunity and trying to fit. a balance of level of effort versus return on investment.

[00:47:04] **Ben:** And, do I want to put in a lot of effort and try and build something bigger? I want to try to get some smaller things done, or maybe just do like a week or two of just small bug fixes and not really feature development. And I just got to get, I just got to put myself in a direction and I'll get there and I know I'll feel great once I start.

[00:47:20] **Ben:** but there's this sad intermediate. Period where, I'm sort of aimlessly searching for something.

[00:47:27] **Carol:** See, that's what I love about how we have started working. We've started working in a cycle model. So when I'm wrapping up and getting ready to release what I have currently in work, or let's say it gets to UAT, so it gets over to customer testing. I already know what's coming down in the next cycle, so I can go ahead and start that process.

[00:47:47] **Carol:** I can go ahead and start building out an MVP. I can start building. some stories I can start figuring out questions to ask. So while it's in UAT and I'm still getting to kind of see it through the finish line, I'm starting something ahead of that. So I don't have that big lull in between. Cause when I have the lull, it's when I'm like, what am I going to do?

[00:48:06] **Carol:** I don't know what to do right now. Like I need something to occupy my time.

[00:48:09] **Ben:** I can do that to a limited degree. But I have trouble if I, if I have something and it's sort of waiting to go out, I feel very mentally blocked. And I feel like I can't really think effectively about a whole new topic until the thing that's sitting there is actually done. And.

[00:48:31] **Carol:** Yep. one of my friends was talking to Steve about how I text whenever I text people. I'm like one sentence, send one sentence, send one. I don't do paragraph texting. And she's like, just let it go. She's an engineer. They don't think like us, like she thinks immediately. And then there's another thought she can't think through multiple things at once is one thing at a time she gets very clearly through that.

[00:48:54] **Carol:** And then she thinks the next thing you can't ask her to make a paragraph. Okay. That's just mean

[00:49:01] **Carol:**

[00:49:01] **Adam:** I'm the same way if I'm texting on my phone, but at least half the time, probably closer to 75% of the time I'm sitting at my laptop and I'm typing out my text messages on the laptop.

[00:49:11] **Ben:** Oh, and like I messaged her something.

[00:49:13] **Adam:** I mean, it's, Android, so it's a little different, but yeah, there's a browser based. You can connect your phone and just, Type your message. Do the, all the text messaging stuff through there, Google messages.

[00:49:24] **Ben:** I've tried to do the I young and on the computer and I, for whatever

[00:49:28] **Carol:** Okay.

[00:49:28] **Ben:** I just could never figure it out.

[00:49:30] **Adam:** Well, it's probably dying when you try to open it because you have 170 million unanswered.

[00:49:39] **Carol:** Ben's like kill don't like Dean don't like being.

## [00:49:44] Carol's MVP

[00:49:44] **Carol:** Well, I guess I could chat about mine super quick. I don't think it's going to take too long. So we have been working on this project and there's been a lot of requirements to it. And there's been a lot of change. Like once we've started meeting with the customers and the product team, and we've been interviewing the people who are going to be using the system, the requirements have went from.

[00:50:04] **Carol:** Here's this big, giant overview of like what we want done and what we want accomplish down to probably we're at five bullet points for what is in the MVP now, which is really great. Because every time I go back to product, I'm like, oh, well, should we do text notification? They're like, kill it. We don't want it.

[00:50:21] **Carol:** Make it the later phase. I'm like, oh, what about the daily digest? That's going to be a later phase to kill it. We literally went. For the first time with this whole effort and everything we do, we really be, we really want a true minimum, minimal viable product to put out. We want the least amount we can put in and build from there.

[00:50:41] **Carol:** We just want to see how they're going to use it and see what tweaks we need to make in order for them to actually be productive in this. And I have been so happy that our product team has. Has just supported us on every turn. Like, yes, Nope. Kill it. We're not going to do it. That's a phase two is a base three.

[00:50:57] **Carol:** We're going to keep building on it. So when the customer's like, oh, open it really should do that. Our product team is like, no, you don't get it. No check boxes for you. You can't mark that as anything.

[00:51:09] **Adam:** That's awesome.

[00:51:10] **Carol:** So it's been great to just have the buy-in of everybody to see that. Let us go small. That's one thing I will say I love about ColdFusion is I can get a product out so freaking fast, like we can get something out the door and it's just like in the system, like so quick.

[00:51:27] **Carol:** So we have it out there running, and then we can build on it and then we can see how we want to use it. So it's just, it's great to have the buy-in from the company when you're actually making an MVP and they can scale it back with you and feel supported. So that's what I'm working on and it is great.

[00:51:42] **Adam:** Are they expecting that MVP in one eight week cycle?

[00:51:45] **Carol:** Yeah. Yep. We're already three weeks into it and we just now find our four weeks and we just finally got the bullet points down to where I could put stories in. So the stories still have a few questions on there. Like we have a design team who are sending us some UI stuff or how they want it laid out based off of their interviews with the customers.

[00:52:03] **Carol:** But yeah, it's, we'll get it out the door. it's not going to be an issue because we're doing so small. It's literally. An internal chat system. That's, it's just storing messages and displaying them, but they want it super complex and we've scaled it back to just store the messages, just see them where previously they were having to send out emails and everything was then being handled inside email.

[00:52:27] **Carol:** So it's getting them in our system. So it's just starting as a starting point. So,

[00:52:31] **Adam:** This isn't the system that you were talking about, like using pusher for, is it

[00:52:34] **Carol:** it is, this is going to be it, but pusher won't be till down the road and then that's going to be like another phase into it.

[00:52:40] **Carol:** So, yeah, it's just, it's good to have buy-in yeah.

[00:52:45] **Ben:** Yeah. Talking about ColdFusion, allowing you to move quickly. I am,one thing I'll say when I was talking about when I deploy stuff and then it's like emojis and party parents everywhere,in our slack, slack allows you to have a bunch of custom emojis as well. And somebody uploaded Lucy and CF emojis.

[00:53:01] **Ben:** So like everything I deploy, I definitely have. Emoji with ColdFusion related paraphernalia. Cause like, I don't want to be a ColdFusion fan boy, but I do feel very proud of the fact that especially as the only person left on the legacy team, like I still F and ship and I N like in part I can do it because confusion just makes a lot of stuff really easy, Like I, I like to celebrate.

[00:53:27] **Adam:** So, you know that your slack administrator gets a, like a monthly report of a million different things, but one of them is like your, your most and least used emoji.

[00:53:37] **Ben:** Really?

[00:53:38] **Adam:** Yeah.

[00:53:38] **Ben:** Oh, I totally want to see

[00:53:40] **Adam:** And like the people that use them the most and that sort of thing. And, I'd be curious to see where your Lucy and CF emoji's

[00:53:47] **Adam:** land on that.

[00:53:48] **Carol:** one of our QA staff left in the past couple of weeks, his name was Jeff. He was absolutely the best and he's missed already, but the other QA team created a little, emoji for him. It says blame Jeff, and it's his head. So anytime something breaks, you see it pop up and it just says, blame Jeff.

[00:54:07] **Adam:** That's awesome.

[00:54:08] **Ben:** Yeah, that is great.

[00:54:10] **Adam:** That's one thing. So we switched from slack to Discord for a variety of reasons. But, one thing that I miss is that we can't have animated emojis for free anymore. you can have them, but you have to pay for like nitro when it's a monthly subscriptions or a deal. And.

[00:54:26] **Carol:** Did you switch after they added threading?

[00:54:28] **Adam:** No it was before. So, I mean, we have threading now, but

[00:54:31] **Carol:** yeah. How do you follow a chain? If there's no threads?

[00:54:35] **Adam:** there's replies. I mean,

[00:54:36] **Carol:** I mean, it's just

[00:54:37] **Carol:** like our podcast It's very hard to follow that discord. Not

[00:54:40] **Adam:** It can be, if there's a lot of, if there's a bunch of different topics going on at once. Yeah. But I, yeah, I like the threads. It's funny. Like now I'll go back and I'll, be working in slack for various things and it's like, wait, where's the, how do I do the reply thing that I'm used to

[00:54:52] **Carol:** used to doing

[00:54:53] **Adam:** discord?

[00:54:53] **Adam:** You can't do that. It's just threading and tagging, I guess you would call it like tag the person.

[00:54:59] **Ben:** Yeah. If I could do a tiny bit of cross show promotion.

[00:55:03] **Adam:** Sure.

[00:55:04] **Adam:** The, uh,so base camp has their podcast. I think it's called rework. And I know that the base camp people are very polarizing they've had Yeah. I mean, we can throw him some love. They probably nobody's heard of this podcast or this company, and they could use the

[00:55:20] **Adam:** working code bump.

[00:55:22] **Ben:** So th this season of rework, DHH. And, Jason freed are like per episode going through a chapter of their most recent book. I think it's the rework book, or maybe it's the, it doesn't have to be crazy workbook Cameron, but which title it is. but they talk so much about exactly what Carol is talking about right now.

[00:55:40] **Ben:** They talk about MVPs and how they, create cycles for work and how they. Differ things like almost as much as possible to see maybe they never even have to do it and they work in six weeks cycles, but it's just, it's, I've been finding this season of rework to be riveting. I mean, I read the book, so none of it's like really a surprise, but it's so great to hear them actually talk about it instead of me just reading the words that they wrote.

[00:56:05] **Ben:** so anyway, that's just. if people like thinking about product development, life cycles of this season of reworks, just been really good.

[00:56:14] **Adam:** Well, I hope

[00:56:15] **Carol:** I hope they

[00:56:15] **Carol:** appreciate the.

[00:56:16] **Carol:** bum.

[00:56:18] **Adam:** I guess that about wraps it up.

## [00:56:19] Patreon

[00:56:19] **Adam:** So this episode of Working Code is brought to you by Postgres. It's this new

[00:56:22] **Carol:** database that you probably

[00:56:23] **Adam:** of.

[00:56:24] **Adam:** and listeners like you. If you're enjoying the show, you should consider supporting us on Patreon. It's the best way to keep this show running Patreon donations cover the cost of editing recording, and we couldn't do this every week without those things.

[00:56:37] **Adam:** So we appreciate all the support that we can get Special. Thanks. Go out to our top patron Monte. If you'd like to help us out, you can go to patreon.com/WorkingCodePod.

[00:56:47] **Adam:** All patrons get early access to new episodes and the after show. And today on the after show tonight this week on the after show we're, let's see. Ben's dad, let him stick his finger in something

[00:56:59] **Carol:** something hot,

[00:57:00] **Adam:** Carol is building a Spotify screen and, something, somebody dog buried something for the first time.

## [00:57:08] Thanks For Listening!

[00:57:08] **Adam:** So, let's see, you know what, I'm going to ask you for a review this week. we got a new review, and I just want to send out some appreciation to hatrick 22. He says a part of a bigger team. I work on a small team and sometimes I feel isolated and out of touch with what's happening outside of our company.

[00:57:24] **Adam:** I appreciate that the working code team gives me a glimpse that the, at the success and failures that we deal with week-to-week are universal. Good luck. Well, good

[00:57:32] **Carol:** good luck to

[00:57:33] **Carol:** you too.

[00:57:33] **Adam:** 22 and thanks for

[00:57:35] **Adam:** the.

[00:57:35] **Ben:** you so much.

[00:57:36] **Adam:** So that's it for us this week. We'll catch you next week.

[00:57:38] **Adam:** And until then

[00:57:40] **Tim:** remember Your

[00:57:40] **Tim:** heart matters. Even if you just burst some code and feel like you're at the end of your rope,

[00:57:45] **Carol:**

[00:57:45] **Ben:** Just remember folks, even when Tim's Mike is

[00:57:48] **Ben:** unplugged, your heart still matters.
