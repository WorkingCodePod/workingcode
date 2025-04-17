---
title: "214: Is Tech the Bad Guy Now?"
description: "In this week's episode, Adam, Ben, and Tim discuss the evolving perception of technology, shifting from an optimistic view in the 80s and 90s to a more critical stance today due to its potential negative impacts. "
date: 2025-04-17
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/f2a78bd1-b57b-40f2-9be0-c86baa6beec5"></script><div class="redcirclePlayer-f2a78bd1-b57b-40f2-9be0-c86baa6beec5"></div>

In this week's episode, Adam, Ben, and Tim discuss the evolving perception of technology, shifting from an optimistic view in the 80s and 90s to a more critical stance today due to its potential negative impacts.

They delve into the consolidation of tech power among major companies like Facebook and Amazon, contrasting it with ideas like Amazon's two pizza teams for maintaining team efficiency.

Adam also has some authentication issues that Ben and Tim weigh in on.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/214-is-tech-the-bad-guy-now.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Ben:** if you look at a place like Amazon, where they have the two pizza teams. So I, I assume part of what that means is if a team gets too big, acknowledge at least that the, the size of the team is kind of directly or inversely proportional to the effectiveness of the team.

[00:00:14] **Tim:** why can't this a be said for a company, right?

[00:00:16] **Adam:** Any team that I'm on is gonna suffer as a result of that two pizza team rule. They're gonna have far fewer people on it. 'cause I can put away some pizza,

[00:00:23] **Ben:** yo.

## [00:00:25] Intro

[00:00:25] **Adam:** All right, here we go. It is show number 214. And on today's show, we're gonna talk about how tech is kind of the bad guy now, and, and also learning is hard. And, and also we're gonna talk about some authentication stuff. So we got a lot to get into. unfortunately, Carol's still not able to be with us tonight.

[00:01:01] **Adam:** so again, just the boys.

## [00:01:02] Ben's Triumph: Learning by Doing

[00:01:02] **Adam:** So Ben, I'm gonna come to you first. What do you got going on, man?

[00:01:05] **Ben:** I'm gonna go with a triumph and I had mentioned in the last show that I had been working on a side project, which I had talked about over several of the previous shows, kind of just a learning project. And I put that on hold 'cause I was just feeling pretty stressed out and feeling like I was, I dunno, just treading water.

[00:01:21] **Ben:** And what I decided to do was take the Hypermedia Systems book that I've read and take the contact app that he iterates through as a learning context and translate that into cold fusion. I mean, specifically, I, I did it on a, on a. Command Box Lucy Server. But,I took the app and I translated it into ColdFusion and I took all the steps and I tried to break them out into individual sub folders.

[00:01:47] **Ben:** So it's like version one is just the vanilla version of the app, and then version two is the vanilla version plus the HX boost attribute, which is part of the HTMX framework. And then I, I just stepped through it and I don't know, it took me, I wanna say like a week to a week and a half of, of some morning times to get it done, but I got it done and I've just, it felt, very satisfying to actually take something to completion.

[00:02:13] **Ben:** And, I wouldn't say that I am now feeling super confident in my ability to build anything meaningful with HT MX, but it definitely underscored that just reading about a technology is very different than actually using it. And even though I had read the book and I had walked through. The application that he was walking through, once I actually got to do it myself, it's like suddenly, all of a sudden, there's like, you know, all these questions that you didn't realize you have now you have to solve while you're trying to write this thing.

[00:02:45] **Ben:** So it was just, it was a good lesson for me, or I should say a good reminder. 'cause I'm, I'm a very hands-on learner, but I also like the idea of reading books and it was just a reminder that just reading isn't, isn't nearly as good as reading and doing.

[00:02:59] **Adam:** Yeah, it, it, it does feel good to like finally finish something. I dunno about you guys at work. Like, my job is just one of those things where it, there is no finished state. It's always like, okay, what's next? Right? And so you never really get to close the book on anything. There, there are chapters you get to finish, but there's never, you never feel done.

[00:03:20] **Adam:** And I, I totally see what you mean by like, there's a, there's the catharsis of finishing something.

[00:03:26] **Ben:** Absolutely. Absolutely. Plus it was also, there's something nice that to have a kind of contained experimental context. 'cause you could easily just go from one rabbit hole to another rabbit hole, to another rabbit hole, kind of going down different experimental paths. But because this was based on something that I had read, it gave me very concrete things to do and a fairly concrete definition of done.

[00:03:51] **Ben:** So it wasn't just that I finished it, it was that there were just known boundaries and, and that also just made it very comfortable to do, like, I didn't feel like it was gonna go on forever, so that made me feel very motivated to get it done as well. Although it's like, no matter how motivated you get, so the, the, it's, it's, it ended up being 16 iterations and it's not like each one of those iterations is a lot of work.

[00:04:13] **Adam:** Mm-hmm.

[00:04:14] **Ben:** But man, you get up into that 12th iteration and you're just. I don't wanna do this anymore. And you're like, no, no, keep going.

[00:04:23] **Tim:** groundhog.

[00:04:26] **Ben:** So, but yeah, I feel good about it. And, I'll kick it over to Tim. Tim, what do you got going

[00:04:29] **Adam:** Before you go, is this an application that you're gonna like actually keep and use, or was this just like,

[00:04:36] **Ben:** Oh, no, totally

[00:04:36] **Adam:** get the experience and throw it away.

[00:04:38] **Ben:** I mean, it's a, it's a GitHub repository. You could pull it down and, you know, command box start server and, and it'll run. But, but no, I mean, it was, it was purely for learning.

[00:04:47] **Adam:** For, yeah, it's, it's, it's reps, right? You're just, lifting the weights so that you get stronger.

[00:04:51] **Ben:** Yeah. Yeah. Absolutely. Absolutely.

## [00:04:53] Tim's Triumph: A Celebration of Life

[00:04:53] **Ben:** Tim, kicking it over to you, sir. What do you got going on?

[00:04:56] **Tim:** Well, I'm gonna go with a triumph, which is gonna sound a little weird. It's what it is. course everyone I talked before that, you know, my aunt suddenly died with a massive stroke and brain bleed, but, they had our funeral Sunday and it was really, I mean, it was, it was beautiful. It was a celebration of life.

[00:05:12] **Tim:** There was about, so we had it, we had to go up to Conyers for it.and it was about 520 people in attendance in person and about 550 on Zoom.

[00:05:25] **Adam:** Oh my

[00:05:26] **Ben:** Holy

[00:05:27] **Tim:** so about a thousand people were, were there, people came down from New York and from Pennsylvania and, and, Florida and came from all over to,

[00:05:38] **Adam:** weren't kidding when you said you had a big family.

[00:05:40] **Tim:** yeah, well, I mean, it's not just family.

[00:05:41] **Tim:** So, I mean, my, my family is pretty well, entrenched in the Griffin, Georgia community, and so they're pretty well known. That's why I don't live there anymore. 'cause it's like, I don't wanna live with that. It's, it's not a big, big cities, but, you know, it's decent sized, but it's like, it's, yeah, I, I, I don't, yeah, everyone knows everybody and just like, I, I didn't want any part of that anymore.

[00:06:07] **Tim:** So, but yeah, so a lot of people showed up. It, it was beautiful then. And, you know, my, my aunt, she was actually a fairly private person. I knew her pretty well. you know, she was very, I. She was like one of the first adults when we were little. 'cause they lived with us for a little while back. They moved up to Georgia and they lived with us for a short bit.

[00:06:26] **Tim:** Three, you three had three kids at the time. And then me and my sister. So five kids in a tiny little house. But, she was very honest. She spoke, she spoke to children like they were adults. And I, I, I remember thinking when I was little that she was just really mean, but she wasn't mean. She was just honest.

[00:06:44] **Tim:** And as I got when I became a teenager, I really appreciated that. 'cause she wouldn't take any of my, my crap, you know, she saw right through me. So I, I learned to appreciate that. But yeah, it was, it was beautiful. It, it really was. And it was just kind of good to get that out of the way. I think, you know, for her husband, he can now actually start healing, you know?

[00:07:04] **Tim:** 'cause past three weeks everybody's just been busy with preparations and family coming in and people visiting and it's just go, go, go, go, go. And now it's time to. Now, now the real healing begins. So

[00:07:16] **Ben:** Can I,

[00:07:16] **Tim:** was

[00:07:17] **Ben:** I ask, I'm just kind of intrigued from a technology standpoint, so if, if half this was attended by Zoom, was there a. Like someone had to come in and set up a camera and I guess, was that like a service provided by the?

[00:07:30] **Tim:** No, where, where we were doing the facility we were doing at, it was a, a, a, a church like facility. It seats about 4,000 people. That's why I was in Con was not in Griffin. 'cause we didn't have, there wasn't a place that was big enough locally that, and it was, you know, it was free to use. So they had all that's built in the camera system and all that.

[00:07:49] **Tim:** The, the Zoom, the connectivity. So they, they do that pretty regularly there. So it was pretty easy to do. So, so they just put a Zoom code on there and people who couldn't come in person did it, you know, watched it on Zoom.

[00:08:03] **Ben:** Very nice.

[00:08:04] **Adam:** Yeah, I'm glad for you.

[00:08:07] **Tim:** I think it, I. For her husband and her children and the grandkids. So, yep. But anyway, that's what I got. How would you, Adam

## [00:08:15] Adam's Triumph: Skydiving App Success

[00:08:15] **Adam:** I'm also gonna go with a triumph. it looks like we got three triumphs tonight. so the, the skydiving app that I've been working on, that's my side project, actually saw the light of day. So, I mean, it's just, the tiniest little, like shakedown flight basically to use, aviation terms. But, you know, they, they, there was a, a Sunday, this last weekend there was a little bit of skydiving happening and the club president, who I've been working most closely with on the app, was there and he's like, do you mind if we just, you know, try it out, see how it goes, and, and, you know, find the, the bugs.

[00:08:49] **Adam:** And I was like, yeah, sure. Go What ahead? Go ahead. You know what's gonna happen? Worst case scenario is it does, doesn't work. or you know, best case you're gonna find some bugs and I'll fix 'em. and you know, he was there and there was like, I think seven jumpers there and they just did like two loads, so didn't get a ton of use, but everybody that was there was really excited about it.

[00:09:08] **Adam:** they were really happy with, you know, what was there and, and they saw the potential for what could come outta this. I'm actually really close to, you know, calling it feature, complete version one sort of thing. there's a handful of things that I've kind of put off as like, because I know I'm not going to market with this, right?

[00:09:27] **Adam:** I'm not like asking other drop zones to sign up. This is like, there's no billing stuff, you know, like I'm, I'm not charging these guys anything for it yet. So there's, there's like no way to sign up for an account. There's no way to like create another drop zone and pay me money to use it. Any of that, none of that's done.

[00:09:41] **Adam:** And then.other pieces, like if it's something that doesn't need to change regularly, then I have just sort of like hard coded the data in the database and I'm like, if we need to change it, I can change it. Right? that, 'cause I'm trying to like, do MVP, just the things that we need to get it, in their hands and actually using it.

[00:09:59] **Adam:** so there's a message that they wanna display on the self manifest screen, and that's not likely to change, like, almost ever. So I just put it in the database. I'm like, if you want to change that later, just let me know and I'll do it.

[00:10:08] **Adam:** So there's a little, a couple little things like that that eventually will work back into the ui, but for the most part it's, it's getting there. There's one big piece that I is still kind of like, not on solid footing yet that I wanna talk about later in the show. but, for the most part it, it's.

[00:10:25] **Adam:** Being used sort of gently, and everybody's excited about it, which makes me really happy.

[00:10:31] **Ben:** Great. Cool. And it's, it's running on super base, super base.

[00:10:35] **Adam:** the database is Postgres, which I think, yeah, superb base is Postgres, but it's not on superb base. I, I was

[00:10:42] **Tim:** Lord and our Lord and Savior Postgres sequel.

[00:10:45] **Ben:** Uh, SvelteKit, so are you, can you talk about just where you're hosting it? I'm

[00:10:49] **Adam:** yeah, yeah. so the, the application is running on Vercel, which if you're not familiar, is like a, they, they're the company that makes Next Js and Vercel is their like hosting platform where you can, very easily host Vercel applications or next JS applications.

[00:11:03] **Adam:** And they also support a couple of other things, including SvelteKit, which is what my AMP has written in as if anybody didn't already just assume that, um.And, and yes, it is using Postgres. There's a, there's a database hosting company called, I think it's Neon that, and you know how you remember back in the day with, what was it?

[00:11:23] **Adam:** who were the ones that were like the first company where you could push to a get repo and it would auto deploy And they were like a Ruby

[00:11:31] **Ben:** Oh, Heroku,

[00:11:32] **Adam:** Heroku. Yes. And Heroku. One of the things that was really cool about Heroku was you could just like click ops sign into your account and say, I want a Redis, and like, pick this Redis provider.

[00:11:42] **Adam:** and they would, they would automatically set up the environment variables for you and everything.and it's like, okay, you now have an account with this Redis provider. You, they've got a free tier. If you exceed that, you're gonna have to start paying for it or whatever. It's already set up in your production environment.

[00:11:56] **Adam:** So now it's, it's there. You could just start using it, right? It was, and they had tons of stuff on Heroku. You could do MongoDB, you could do Redis, you could do a million other things. Vercel has a bunch of similar integration stuff available, and Neon for Postgres was one of 'em. And, and I looked, and Neon has pretty, reasonable pricing.

[00:12:15] **Adam:** So if this does happen to grow to where I need actually to store more data than they offer on the free tier, or, or if it's performance or whatever, becomes a problem because I have more customers, then that's okay. I don't mind paying for it.so yeah, it, it's Postgres in the cloud on Vercel, on SvelteKit.

[00:12:33] **Adam:** Is it, is it a mobile optimized front end or is it an app?

[00:12:38] **Adam:** it's responsive design, web, web stuff. and I am, and so it's Tailwind, because obviously, and my general approach with Tailwind is I try to start thinking about phone sizes and then. expand, like, okay, so now if you're on a tablet size, like what is, what should, how should the experience be different, right?

[00:12:56] **Adam:** Stuff shouldn't always be full width once you get up to that larger screen and then like desktop computer, what could even be more? So, yeah, that's the, the general gist of the stack.

[00:13:09] **Adam:** Um,

[00:13:10] **Ben:** cool. And I remember you saying that you at least started out with kind of a vibe, coding,

[00:13:15] **Adam:** yeah,

[00:13:16] **Ben:** prompt based development. What's the, what's, okay, so, so now you're into the, into the, just hands-on stuff.

[00:13:23] **Adam:** Yeah, yeah. No, I got as far as I could with the prompt based stuff. And then when it started to get like, honestly, I think part of it is just that I'm doing SvelteKit, which is not as popular as React. So there's less internet for the LLMs to have scraped and learned. There's less, there's less just known about it.

[00:13:39] **Adam:** And also the, the. This SvelteKit stuff is newer, right? React hasn't changed as much in the last five years as Vel and SvelteKit have. and so, you know, it just doesn't have as much training data to go on. So it, I think it kind of hit a little bit of an artificial wall there, if we can call it an artificial wall, fairly early.

[00:13:59] **Adam:** And then, you know, the other part of it is being, an experienced developer. I have exacting standards and a high bar of what I'm willing to accept. You know, I'm not, just trying to, like, that's, I think that's the difference is I know how to write the code and so I'm not gonna just be like, well, you know, I'm not gonna to spin my wheels trying to make it work through prompts when I can be like, well, okay, well you're clearly not getting this, so let me just get in here and do it for you, sort of thing.

[00:14:26] **Ben:** Yo, can I, sorry, I just wanna,

[00:14:30] **Tim:** So lemme. Me, let me ask this. So since this was an MVP, did you get any valuable experiment feedback that you're going to be able to put to use?

[00:14:41] **Adam:** Yeah, I mean, I, I did try to take the MVP mindset of only work on the stuff that is actually going to move the needle, make, make it, make it possible to use this, and defer everything else. And I've been keeping a, you know, a nice long ideas and to-do list of things that should come later. but I think in the, the MVP strategy often you're, you intend to throw the first one away.

[00:15:07] **Adam:** I don't think I'll be doing that. I think that I've got us all on enough baseline here that, yeah, there's gonna be tweaks that I need to make along the way. And something I'm, I'm kind of learning over these last couple of weeks is a little bit more. Thoughtfulness and diligence and patience in making changes to the architecture.

[00:15:27] **Adam:** So I'm using, a database migration tool, which has been amazing. I, I started working in this industry before anybody had ever thought of the concept of database migrations. And so I've got 20, god now, probably 30 years of experience of, of living without database migrations. And then I started a new project and I'm like, oh, this is a great opportunity to try this thing.

[00:15:48] **Adam:** I've always wanted to have that at my fingertips, and it's working great for me. And so now there have been one or two times where I like, make a change real quick, create a migration to do it, blah, blah, blah, push it out. And I'm like, you know, it really would've been better if I had done it the other way, right?

[00:16:01] **Adam:** And so now you gotta like, either try to migrate down production and, and, you know, do it the other way or you gotta write a, a, a second migration on top of it. That kind of re changes stuff. and you have to worry about, you know, the existing data up there. So. I'm sure this is all old news to somebody who has a lot of experience working with migrations, but to me this is, it's exciting and it's fresh and it's, it's, it's making me grow in ways that are very positive.

[00:16:31] **Adam:** Right? Like I said, it's making me be more patient and more thoughtful in terms of, especially the data model. you know, what is the right approach for this problem and, and how do I get to there from here, sort of thing.

[00:16:44] **Ben:** Database migration stuff is, is super interesting.we used to use something called Liquid base, which, which I think is like technically running on top of Percona database tools or something. Like, I think it's like a series of things stacked on top of each other. and Perona is a, is like a fork of MySQL and it maintained as its own thing, I believe as well.

[00:17:06] **Ben:** and we only ever dealt with rolling things forward. There was no concept of rolling back. It's like you could have a roll forward that changed some things back, but for the most part, data is one of those things that it's, it's just hard to get back, you know, if you drop a column, you can't just undr a column unless you're using one of those fancy like point in time database things where it's like you just make a get branch and suddenly you have a new database.

[00:17:33] **Ben:** I don't, I don't know how that

[00:17:34] **Adam:** when you first started, when you first said drop a column, like, yeah, you can drop a column, but if you're, if dropping the column is the migrate up, you can't undr it on the migrate down.

[00:17:41] **Ben:** well, that's what I'm saying. That's, yeah, exactly. Like, so, so you sort of just have to have this, not there's no going back mentality, but. You have to have this, like no matter what happens, we're moving forward unless someone wants to pull it back up and

[00:17:55] **Adam:** Well, yeah. And that, that has also been interesting too. There have been a couple of times where I'm like, you know, I've got my local dev database. I'll do a migration locally, run it locally. So I've got the change here and I'm, I'm like kind of living with that locally for a couple of hours, you know, trying to make the application changes that go along with it.

[00:18:11] **Adam:** That's another, oh, I love it. That's the other thing about the, this that is great is like the, the migrations are paired with the code changes, right? It's all just in the same repo. And when I hit deploy the code, like when I get push, it's the build process for the website that runs the migration, which connects to the database and makes the database changes so I don't have to worry about manually keeping those things in sync.

[00:18:33] **Adam:** Now, I guess there's a, a second or two between the time that my migrations run and the new application code is up there. So potentially the website could be broken for, you know, a few seconds. But in the grand scheme of things, I'm not gonna sweat that.

[00:18:50] **Ben:** Yeah, especially for something, you know, in the early days of an application. It's like who even we used to run locking da database alters for like, I don't know, like the first four years of, of Envision and, and there'd be literally times where you had to add a column to the user's table. And we're sitting there and we're just watching requests queue up and we're let going, oh, finish, finish.

[00:19:17] **Tim:** I thought we could get away with it.

[00:19:18] **Ben:** Right. It's like at some point I think we, we hit, like once we had to alter a table that had it's like over a million rows, then you're like, okay, you can't just do this willy-nilly anymore. Like it actually takes some time to do.

[00:19:31] **Adam:** Right.

[00:19:32] **Tim:** Yeah.

## [00:19:33] AI Deep Research

[00:19:33] **Ben:** Yo, can I, just side Quest for a second here because,

[00:19:36] **Adam:** in the show for side Quest, but Sure.

[00:19:39] **Ben:** so, 'cause you were talking about the vibe coding and I'm trying to embrace AI a little bit more.

[00:19:45] **Ben:** And, a lot of the things that people have been talking about is the, chat g pt or I guess open AI has the deep, Deep research functionality where it'll, it'll like go off for half an hour and come back with a more extensive research item,

[00:19:59] **Tim:** It is just taking a, a smoke break, that's all

[00:20:01] **Ben:** you know, and, and like people talk about just how amazing it is.

[00:20:04] **Ben:** I just wanna, so I tried to use it and I wanna read a prompt because I feel like I was, this is like the most extensive prompt I've ever written in my life. And it's three paragraphs. Don't, don't worry, let's take 30 seconds to read. But I wanted it to, so I'm learning about HTMX and I wanted to have some help kind of overcoming the, the mental shift I think it takes.

[00:20:22] **Ben:** My prompt was, this will take about 30 seconds to read. I'm trying to learn about the HTMX JavaScript framework. I have a heavy angular JS and modern angular background and been building spa or single page applications for the past 15 years. But I'm keen to try and find ways to improve the developer experience for applications that don't require the full spa treatment.

[00:20:41] **Ben:** I've been told that HTMX provides that nice happy middle ground enhancing the application experience while still using a multi-page application architecture. Please write me a research paper that looks at HTMX and provides a way for me to think about HTMX coming from a SPA background. Focus on many of the major hurdles that people face when trying to construct an application using HTMX and how those hurdles can be overcome.

[00:21:04] **Ben:** Please use a lot of code samples in the explanations. The code samples

[00:21:07] **Adam:** lots of white space in your code samples.

[00:21:10] **Ben:** the code samples should use cold fusion CFML and CFF and CF script on the backend. The H TM L should not use tailwind, The H TM L should only include CSS class names in cases where those class names are used. For HTMX targeting, do not use Hypers script.

[00:21:26] **Ben:** That's an HTMX thing. Either use the HX on bindings or use alpine js for client side scripting. Use a cookbook style format presented as a series of problem statements and then solutions. After reading this research paper, I should feel like I can start to build an HTMX application on my own. I felt like that was like a I, I was proud of that.

[00:21:46] **Ben:** If for no other reason, I've literally never written a prompt that was more than two sentences and. I don't know. I don't know. Like, so my expectation going into this is everybody talking about how freaking amazing all of this deep research stuff is, and like it comes back with like such well of research stuff.

[00:22:04] **Ben:** And I was just very underwhelmed. I, I sat down and I read this thing and it took me like half an hour to read it. And like the code samples were very inconsistent. Some of them were just not correct. And I definitely didn't come away feeling like I had really learned anything. I,

[00:22:25] **Adam:** you think it could have done better code samples in something that it's probably got more training data on like JavaScript,

[00:22:31] **Ben:** so I, I, I, and I think this is again where the, the kind of, I don't know what the right words are here. It's like there's the, there's the, The abstract way in which we talk about Theis is having this kind of intelligence. And like you, a lot of people say, well, it's not really intelligence, it's just numbers and math and probabilities and like how great it is to get coalescing all this information.

[00:22:56] **Ben:** And so there's, there's this kind of broad strokes kind of stuff. And then there's the pragmatic realities of it actually having to have been trained on data. And if it doesn't have the right training data, it's not gonna give you the right answers. And it, it's hard to, I don't wanna say reconcile, but it's hard to keep those two things in your head.

[00:23:16] **Ben:** You know, half the world telling you how revolutionary all this stuff is. And then the other half being like, it's just math. Like if it's, if it didn't go in, it's not coming out.and I, I don't know. I guess I was just like, I was so excited that I was letting myself go into this with an open mind and I, I.

[00:23:35] **Ben:** I wish I had been more impressed. Like, it's, it's, it's, it's like one of those things, like Louis ck, he's a comedian and he had this bit about how easily we forget how amazing things are and like people will be on this plane going 700 miles an hour in the air and they're like, oh, it's too cramped. And they're like, but you're flying through the air, you know?

[00:23:55] **Ben:** so I don't know. I'm just complaining, I guess. But, it, it's fascinating that it can do this. I mean, it blows my mind that it works, that it comes up with actual paragraphs and the paragraphs are somehow coherent and it is actually telling a cohesive story that has flow and is, and, and is meaningful to the reader.

[00:24:12] **Ben:** Like, I don't even understand how that's possible that, that, that's science fiction to me already. But it's just like the quality of the content. I, I don't know. I'm just, I.

[00:24:22] **Tim:** It's, it is like talking to that one guy at a party who knows, who thinks he knows everything and knows nothing. Right. He sounds good. He sounds like really good. He is using all the right words, all the right lingo, and you're like, you actually listen to what he said and you're like, dude did not say a damn thing That made any, any sense whatsoever.

[00:24:38] **Tim:** I, I could tell, like when I read a newspaper, like, not a newspaper, but like an article that, that someone is, you know, crafted using ai, you can just tell, it's like, get to the point. What, what are you talking about? Why are you using all these words? Just, just tell me that. Just, just, you know, say the thing and they don't.

[00:24:57] **Ben:** You know, and the other thing that frustrates me, if I could just riff on AF for one more second here, they, people always talk about how certain models are better for other things. Like if you're using chat GPT and you want to think harder, you should use, you know, oh three mini. I'm just making things up.

[00:25:13] **Ben:** I don't actually know if that's meaningful. Or like, if you wanted to do code, then use this particular one. Or if you want it to be more about writing prose, use this one. I always think to myself like, shouldn't, shouldn't they be making that judgment for me, shouldn't they look at my prompt? And say, oh, this person is asking a question about code.

[00:25:32] **Ben:** Let me kick over to this model. Or This person's asking about writing poetry. Let me kick over to this model. Like you guys are the ones writing the models and

[00:25:39] **Adam:** Well, I I think that eventually we'll get there. I, you know, I think that right now the technology is so nascent still that they're, they're building the Lego bricks and they have to, you know, we, we've built one with a window in it and we've built one with a door in it, and we've built ones that are four by four and some that are three by four.

[00:25:58] **Adam:** And, and, and eventually we'll get to the place where they built the whole house, and you can just do whatever you want with it, and it'll be good at it. but yeah, in the, in the short term, I was thinking about that a lot today. the, you know, it seems like multiple times a week new models get released now, and that may or may not be true, but that's just the, the totally raw, uneducated guess that I have based on vibes

[00:26:23] **Ben:** your sense.

[00:26:23] **Adam:** Right? Yeah. and the, and, and, and exactly what you're talking about, like, some of them are, better at deep thinking. Some of them are just faster and maybe slightly less creative as a result or, or less correct or whatever. And it made me, I was struggling with, well, if I'm gonna be using it in vs code or whatever, like I want it to be relatively quick and I don't necessarily, I'm not willing to wait four minutes to get a response if it's only gonna be, if it's still gonna be incorrect or if it's, you know, honestly, I'm not really willing to wait four minutes for a response almost ever.

[00:27:01] **Adam:** And you know, if it, if it can't give me something within, I don't know, 10 seconds, 15 seconds, then I'm, I'm probably not gonna mess with it at all. And, and then I'll, you know, if it can gimme an answer, then I, I will evaluate that answer and decide whether or not I like it. But, yeah, I don't, it's

[00:27:19] **Ben:** all, so it's, it's so frustrating because, I, I was listening to an interview the other day, I can't remember if it life me, where it was. And the guy being interviewed was saying that it really helps to think about these, these large language models, like they are people, and to talk to them a little bit.

[00:27:36] **Ben:** Like you would talk to a person and have expectations, like you were having the expectation of another person. And the example that they were talking about really was the, the, the, like the change reasoning stuff. They're saying, you know, it's like a person. If you sit there and you just spend more time thinking about a question that someone asks you, you'll probably come up with a better answer. But it's like, but it's not a person, right? It's, it's math, it's statistics. Like if I, if I gave a, a computer longer to do a for loop, it's like the for loop doesn't become more accurate. And I, and I know that that's like a really poor analogy probably,

[00:28:14] **Adam:** mean, Ben, arguably we are math too.

[00:28:18] **Ben:** but I'm just saying it's like I, I, it, we, we have this, we have this two visions of it that are at odds.

[00:28:26] **Ben:** It's like, on the one hand it's people like, and it's intelligent. And then on the other hand it's just, it's just inputs and outputs. And, it, I just feel like the two stories are kind of hard to reconcile sometimes.

[00:28:42] **Adam:** Hmm.

[00:28:43] **Tim:** That's why humans are good. We can hold two contradictory things in our brains and not blow up.

[00:28:47] **Ben:** You for real. It's like, I'm like, oh, I gotta lose weight. And then like 30 seconds later, I'm like, but that ice cream looks really good.

[00:28:56] **Adam:** I got a birthday coming up and at dinner tonight, my wife asked me if I wanted a peanut butter pie for my birthday, which is the tradition instead of a birthday cake. She makes me a peanut butter pie, which is basically just imagine peanut butter and a lot of sugar. and it's in basically pie form,

[00:29:11] **Tim:** Sounds like Heaven.

[00:29:12] **Adam:** it does, doesn't it?

[00:29:14] **Tim:** It does.

[00:29:14] **Ben:** It, it sounds like what? Oh, heaven.

[00:29:16] **Tim:** heaven?

[00:29:17] **Ben:** It's probably a million calories. you said, it sounds like Kevin,

[00:29:23] **Tim:** Oh, Kevin.

[00:29:25] **Ben:** is it, is it like a, like a pumpkin pie visually? Is that what I'm thinking about?

[00:29:30] **Adam:** I mean, and so it's basically peanut butter,cream cheese and, and, and confection or sugar in a specific ratio

[00:29:37] **Ben:** So it's like if a cheesecake and a pumpkin pie could have a child, like,

[00:29:41] **Adam:** And the pumpkin pie was peanut butter instead of pumpkin. Yes.

[00:29:45] **Ben:** Alright, fair enough.

[00:29:46] **Adam:** but yeah, and I was like, just, you reminded me of that talking about, you know, I, I want to lose weight, but I also want to eat awesome stuff. Yeah. And I had to be like, you know, right now, this is not a good time. I'm trying to, I'm trying to get thinner.

[00:30:01] **Ben:** Oh yeah.

[00:30:02] **Adam:** Anyway, let's, let's move on. We were, we've,

[00:30:04] **Ben:** Should we do an actual topic?

[00:30:05] **Adam:** down a rabbit hole here. Should we actually 30 minutes into our podcast? Should we get into the actual podcast?

[00:30:10] **Tim:** I don't know. We filled down a ben hole.

## [00:30:16] Is Tech the Bad Guy Now?

[00:30:16] **Adam:** alright, why don't we start with, tech being the bad guy now.

[00:30:19] **Tim:** Yeah. And I think it kind of, I mean, what Ben was kind of saying is, is kind of in line. He didn't really explicitly say it, but I, I was thinking about, you know, when I was young, like early teens and the movie war games came out, and just the, the general attitude toward. Toward technology in the eighties and nineties was like, it's gonna solve our problems, right?

[00:30:40] **Tim:** It's gonna democratize the world. It's going to, you know, solve the problems that we have. Like, like even the war games movie that, you know, there's a computer and it wasn't a big bad computer trying to take over the world. It was a, you know, do you, you know, do you want, it was a simulation program and

[00:30:56] **Adam:** Would you like to play a

[00:30:57] **Tim:** would you like to play a game?

[00:30:58] **Tim:** And they play thermonuclear war and it plays out the scenarios and, and learn, you know, obviously it was, you know, an early ai and as it they represented it, it learns that war is bad and the best way to, to win is not to play. And, and that was the general take on, on, on it. Even like aliens where, you know, they come to earth, they find a kid and you're the last star fighter, right?

[00:31:19] **Tim:** And you, and then like Star Trek, the next generation. I mean every, you know, post scarcity world, technology's fixed all the problems. And then, you know, and, and then you actually, get jobs in, in tech. And it's like sort of this still this kind of optimism that, you know, now we can connect people, people are gonna be closer, they're gonna, you know, we're gonna break down barriers between human beings.

[00:31:40] **Tim:** 'cause now they can talk instantly and, and share ideas and a free thought or exchange of ideas. And it's gonna make everyone smarter and people are gonna be closer together than they ever have been.and then yeah, that none of that happened. And then we got Nazis and, and so now it's like all the news, like all the things in the news and in popular culture about tech is, is about how it's taking away our humanity.

[00:32:08] **Tim:** It's making humanity worse. And to be fair, there is some truth to that. You see what social media has done, what this constant flow of information is. It's helped to make more people propagandize more easily and to spread easily, and people are worried about that. You know, technology would just basically replace human beings rather than save them.

[00:32:31] **Tim:** So I, I just try to wrap my head around how this shift happened where tech is now the bad guy, not the, not the messianic promise that we felt it was, or at least I did in the early days.

[00:32:44] **Adam:** I, I don't think that tech itself is the bad guy. I think that tech got stolen from the, the meritocracy or, or whatever. Like, I, when I say tech, tech, what I'm really thinking about, because that's what, that's, that's how it colored my early life is like the early internet, right? A OL chat rooms and like open source software.

[00:33:07] **Adam:** The movement and, and Wikipedia, these things were like the, the. Clear indicators that the internet was coming to save humanity, like solve all of our problems and make everything great. And those things still are able to do good stuff. But I think that they got stolen and or taken by people who had power and, and power has been consolidated and that people who have too much power get power over tech and misuse it. You know, like, guns can do a lot of good too. They just also are capable of being used for bad.

[00:33:48] **Tim:** Yeah.

[00:33:49] **Ben:** I do think the consolidation has a lot to do with it. There was just a, a weirdness on the early web. I. 'cause there was, I think, such a

[00:33:59] **Ben:** broader shallower landscape, but now there's so, there's such huge gravity sinks between, you know, Facebook and Apple and Microsoft. I mean, it's like, there's not Amazon.

[00:34:13] **Ben:** There's really, there's like not that many massive players, but the ones that are there own so much of the, of the zeitgeists.

[00:34:22] **Tim:** Let's think about Facebook. I remember, I remember the days when Facebook made no money. I mean, they, they were consistently, and now they're like valued at trillions of dollars. It's a trillion dollar company. Right.

[00:34:34] **Adam:** And the value is all the information that they've extracted from us.

[00:34:37] **Tim:** Exactly. The, the only thing they're selling is they're selling us back to ourselves.

[00:34:42] **Ben:** To be fair, half of my Facebook feed is advertisements.

[00:34:45] **Tim:** Yeah. Unless you click the friend, friend tab.

[00:34:48] **Adam:** Yeah. I guess they kind of are selling us back to ourselves. I was gonna say, they're selling us to, you know, advertisers basically,

[00:34:55] **Tim:** I mean, us as the human being collective. Yeah.

[00:34:57] **Adam:** yeah, yeah. They're selling our information to data brick brokers who then use that information to influence us to do stuff,

[00:35:04] **Tim:** But it wasn't that long ago, like remember the Arab Spring when there was just this huge uprising of what they felt was like pro-democracy in these Arab countries. And these young people were using Facebook to coordinate these rallies of protest to, you know, to fight for, for, for their, their democratic rights and things.

[00:35:21] **Tim:** And you know, even then Facebook was like, it was being hailed as like this, this catalyst for positive change. Of course, none of that worked out. Strong men took over governments and then, and now it's like, you know. Zuckerberg's going back on all his promises and is being evil in general.

[00:35:41] **Ben:** I, I'm always shocked. That the, I I've listened to a couple of interviews over the past couple years about the evolution of Facebook, and apparently there was one real singular turning point in Facebook's history, which is, I don't remember what the context was. There was some sort of a, I think it was like a terrorist attack, and historically Facebook had always taken down anything that had been like violent or offensive, but there was some photograph of like a dismembered body in this terrorist explosion.

[00:36:17] **Ben:** And someone on one of the content moderation teams, like made a judgment call like, this is too important, like, we have to leave this up so that the world sees this. And like suddenly Facebook went and now a, a different trajectory that it was, it was opinionated about things in ways that it had not been before.

[00:36:35] **Ben:** And, and then they've sort of like the pendulum had to swing far back the other way and this way and then that way, but. I'm always shocked that the people who run companies at some point feel disconnected from the thing that they're running. Like if I was running a big company, especially where a lot of people were involved, I always feel like I would have an opinion.

[00:36:56] **Ben:** Like I would. I, I like, I feel like the company to some degree would always be an extension of how I saw the world, and I'm just amazed that there are people who, who can disconnect so much from what's actually happening on their software.

[00:37:11] **Tim:** But,

[00:37:11] **Adam:** Oh yeah, absolutely.

[00:37:12] **Tim:** but can you say that, I mean, do you really think Elon Musk is disconnected from

[00:37:16] **Ben:** No, that's true.

[00:37:17] **Tim:** what his, do you really think

[00:37:19] **Ben:** Right. Then he went back the other way.

[00:37:20] **Tim:** Right. I mean, you really think Zuckerberg, I, I mean maybe, maybe Tim, what's his name from Apple seemed, you know,

[00:37:28] **Ben:** Tim Cook.

[00:37:28] **Tim:** Tim Apple? Yeah. Good old Tim Apple.yeah. But I think the money is the other problem too, when you get so much money and like the companies get all this money and they, they have to do something with it.

[00:37:39] **Tim:** Right. You just don't sit on

[00:37:41] **Adam:** Yeah. Yeah. I mean, they're, that's a, that's a big problem. They're, they are almost contractually bound to do take any opportunity that comes their way to make shareholder value go up. Right. Whether it's for the public good or not. Mm-hmm.

[00:37:57] **Tim:** so they come up with these, these things that are really outside their wheelhouse, and some of 'em gonna win, some of 'em gonna lose, but it's like they're, you, you wonder why are you, why are you pursuing this? This isn't in the best interest of, of what is good for the planet, right? AI is like, okay, let's say AI replaces all our jobs and we, we get like a basic income and everyone just, you know, work a two day week and, and you know, get paid and, you know, some, some ways of wealth distribution where we all just live very relaxed lives.

[00:38:31] **Tim:** And Ai robots do all build all our stuff and farm all our things and, you know, do all our lawyerly stuff. According to Bill Gates, he, he thinks that the only three jobs that are protected, coders. So we're good guys. We're good, energy specialists and biologist. He says every other job will, will be replaced by AI in.

[00:38:52] **Tim:** The not too distant future in our, within our lifetimes, probably if we live long enough. So I don't know where I was going with that. I lost my, I lost my thought.

[00:39:06] **Ben:** I'm, I'm always surprised at these predictions. So, okay. On the one hand, I spend 10 minutes here ranting about the fact that this deep research thing, I was very underwhelmed. It's like both at on one hand, super impressive that it can do it. And then on the other hand, just overwhelming with what it actually produ, I mean underwhelming with what it actually produced.

[00:39:25] **Ben:** So that's in my head. And then I listened to an interview over the weekend on the Hard Fork Podcast, and they were interviewing this guy who, he wrote a paper. it was like 2027 ai.com or something, and it, it, it was like all these predictions about where AI and what probability it'll have reached these, these milestones in the next three years.

[00:39:48] **Ben:** And it, it goes through phases. Like is it expert coders and then is it like self-directed research agents? And then it kind of keeps going. And like at one point it, the AI starts to generate the new AI models kind of a thing. And then you get into like the whole cyber ine system situation. But, but they, I'm just blown away at how many people are actually fairly confident that general, what is it, artificial general intelligence, a GI is like just a handful of years away. Like

[00:40:22] **Adam:** I'm skeptical

[00:40:23] **Ben:** so, it's so hard for me to make that leap in my head based on what I see. 'cause again, like it's just math. I mean, and I know you're saying like we're just math also ultimately, and like just, you know, sacks of electrical reactions and whatnot.but it's just, it's just, I, I don't see how that leap happens in my head at all.

[00:40:45] **Adam:** that is why you don't get paid to

[00:40:47] **Ben:** I know.

[00:40:49] **Tim:** And

[00:40:50] **Ben:** it's, sorry, go ahead.

[00:40:52] **Tim:** I was gonna say, so here's my fear. my fear is that, you know, most people, Probably not as well-informed as we are about technology, right? Because we've been in it all of our life and we've worked in it, done it professionally that, you know, just this feeling of evil just makes people going to push back, right?

[00:41:14] **Tim:** Regardless. They don't really know why. They just think, oh, that's bad. And then there's a negative backlash against the thing. And how even though, yeah, there's probably some bad things going on. Do we really want to go to a world that's less technologically advanced, that doesn't seem right either. That there's gotta be a way to move forward with that helps people and helps the planet that is responsible without, you know, going back to, you know, we're all gonna live like the Amish.

[00:41:45] **Tim:** I, no, I'm not signing up for that. I'm not interested in that.

[00:41:47] **Ben:** I do like my, I do like my internet.

[00:41:50] **Adam:** the, yeah. I'm not giving up the internet. I'll, I'll move to Mars when we get the internet there at, at, at, faster than light speeds. Anyway, the, I think the, the key problem there is give, getting people who currently have power to give up somewhere, all of that power. That's gonna be a requirement if we're talking about, you know, tech utopia of the future, if we're trying to reach that goal, it's gonna require decentralization of that power, and that is like the thing that power resists.

[00:42:22] **Tim:** Yep.

## [00:42:22] Anti-Trust

[00:42:22] **Ben:** know, in high school I took a, an anthropology class. I mean, I had to take an anthropology class. Everyone did, and it ended up being a, a fascinating class. It was really, really interesting. And they talked at one point, there's, so there's something called Dunbar's Number, which is like, you can have something like 150.

[00:42:43] **Ben:** Deep personal connections. And if you go beyond that, it's it like the how connected you feel to people starts to trail off. I'm pretty sure that's what Dunbar's number is. And they were

[00:42:52] **Tim:** pretty sure yours is lower than that.

[00:42:54] **Ben:** yeah, mine's like seven. But they were saying that there are tribes that followed roughly that schematic for the, the village would reach a certain size and then they would literally split the village in half, and one half would go this way and one half would go that way.

[00:43:11] **Ben:** So they keep the numbers artificially small to make sure that there was that strong sense of community. And I almost wonder if something, some analogous thought to that could be had, you know, we have antitrust litigation in this country to make sure that people don't have monopolies, but

[00:43:29] **Tim:** Supposedly we do

[00:43:30] **Ben:** supposedly, but I could imagine there being some sort of other less subjective number like.

[00:43:38] **Ben:** Number of employees or, you know, number, amount of annual income or something we say, okay, like a company hit, you're now worth a,

[00:43:45] **Tim:** market, percentage of

[00:43:47] **Ben:** yeah. Like, okay, now you've reached a trillion dollars. Like you're just not allowed to be one company anymore. You have to be different companies. And I'm not saying that would be an easy thing to do, but it, it would be interesting to have some sort of a, we generally know that this is not good.

[00:44:01] **Ben:** We can't necessarily articulate it any better than that, but we know that if we cut you in half, it'll be better for the world

[00:44:09] **Tim:** And, and I think, I think most of us probably lived through that when they broke. I remember how stagnant telephones were growing up.

[00:44:16] **Adam:** Oh,

[00:44:16] **Ben:** a mob be or

[00:44:18] **Tim:** Mabell, the breakup mob. Yeah. I mean, it was, it was ridiculously expensive. It was terrible user experience. I mean, you, you couldn't really call anywhere outside your county or, you know, depending on where you live, your area code and paid huge long distance fees.

[00:44:33] **Tim:** And then as, as long as they broke those up, I mean, things got a lot more competitive, a lot better. Right.

[00:44:39] **Adam:** Competition,

[00:44:40] **Ben:** the, and the irony is if you look at a place like Amazon, and granted this is just a small slice of Amazon where they have the two pizza teams. So I, I assume part of what that means is if a team gets too big, they probably cut it in half and like, make you responsible for this and this team responsible for that.

[00:44:56] **Ben:** Like they, they,acknowledge at least that the, the size of the team is kind of directly or inversely proportional to the effectiveness of the team.

[00:45:07] **Adam:** I gotta say.

[00:45:08] **Tim:** why can't this a be said for a company, right?

[00:45:09] **Ben:** Well, that's what I'm saying. It's like they, they, they appreciate that internally, but it gets lost in translation.

[00:45:16] **Adam:** Any team that I'm on is gonna suffer as a result of that two pizza team rule. They're gonna have far fewer people on it. 'cause I can put away some pizza,

[00:45:23] **Ben:** yo. There's, there was a, this comedian he's hosted on SNLA couple of times. Nate Azi, I, I think is, and I was watching a standup of relatively new standup of his from like, two or three months ago, and he is talking about how he wanna have his friends over for pizza. And his wife asked him like, well, how much piece should I, how much pizza should I order?

[00:45:45] **Ben:** He goes The most, whatever the most is. Get that.

[00:45:52] **Adam:** It's good leftover too. So like, what's the problem?

[00:45:54] **Ben:** Oh, it's so good leftover.

[00:45:57] **Adam:** All right, shall we, pivot to our next topic here?

[00:45:59] **Tim:** I mean, we haven't solved the issue yet, but yeah, I guess we can move on.

[00:46:04] **Adam:** We'll get to World Peace next week.

[00:46:05] **Tim:** Okay. We'll get to work. All right. Yeah. Sounds good.

## [00:46:09] Diving into Authentication Challenges

[00:46:09] **Adam:** So, I mean, we are running a

[00:46:11] **Ben:** yeah, let's go. You wanna go? Authentication stuff that's

[00:46:13] **Adam:** Sure. Yeah. We'll, we'll save Learning is hard for the week after World

[00:46:16] **Ben:** Yeah, yeah,

[00:46:17] **Tim:** Okay. Stay

[00:46:18] **Adam:** so yeah. Gotta get, gotta keep 'em wanting more, you

[00:46:22] **Tim:** exactly. Yeah, the little tease.

[00:46:24] **Adam:** so, okay, authentication stuff. basically, let me see if I can make this relatively short preamble here. You know, my, my skydiving app, it's SvelteKit, for authentication.

## [00:46:35] Exploring OAuth Providers

[00:46:35] **Adam:** I chose to use a library called Auth Js, which was kind of spun out of,an open source library called Next Auth, which was like all the authentication stuff for Next js right? Became like this all JavaScript PLA or all JavaScript frameworks can use off js and it's like, basically sets it up so it, it's got preexisting.

[00:46:58] **Adam:** OAuth functionality that works with like 90% of OAuth providers, right? So it works with Twitter, Facebook, Instagram, blah, whatever, you know, probably. And a lot of enterprise ones too, right? It's got like Okta and, and you know, whatever. It's got GitHub, it's got a bunch of 'em. So it's like, okay, cool. That sounds great.

[00:47:19] **Adam:** I, I would really like to avoid having to do email and password and like, sending password reset emails and, and email confirmation email. like if I can avoid having to send email through this thing, that would be awesome. 'cause pretty quickly I feel like if I, if I have to send emails, that's gonna probably end up being one of the first things that I'm gonna exceed the free tier of and have to start paying for.

[00:47:42] **Adam:** So, I, I've been trying to avoid it and that's why I went with OAuth. I was like, okay, cool. So, You, you go to the website and you just click sign in with Google, and I've got three buttons on there right now, and I picked those three specifically because of this problem that I'm having. You, you can, it's like sign in with Google, GitHub, and Spotify.

[00:48:00] **Adam:** and there are, like I said, there's a,

[00:48:03] **Ben:** Interesting.

[00:48:04] **Adam:** because they support OAuth and, and a lot of people have it. So I, in an ideal world, I would support Google accounts, Facebook accounts, Instagram probably, and then maybe like one other thing. I don't know what that would be yet, but, maybe, probably like Yahoo because a lot of people still have Yahoo emails in my sky having circles.

[00:48:23] **Adam:** and that way, like I wouldn't have to worry about, login. I never have to worry about the security side of it. Right. The problem I'm having is I'm up against a couple of. Reasons that I can't just use those logins, right? Like, why, why don't I have Facebook log on, login on there yet? It's because these days, in order to set up a a, a OAuth Facebook login thing, you have to have a registered business.

[00:48:48] **Adam:** and, and it's like, yeah, you have to, you have to set that up in your, in your developer account, and you can't like go through a review and all that. You can't just be like, Hey, I'd like to OAuth with Facebook anymore. Used to be that was the case, you could just sign up and do it. Yeah. And it it, and so because they are under the same meta umbrella, I believe Instagram is the same way.

[00:49:10] **Adam:** and then, I think Apple might be, I forget, I forget the reasons for all the ones in particular, but like I was thinking, okay, well probably 90% of Skydives have an iPhone. So if there's like Apple login, that would be nice to have. most people, most skydive divers are on Facebook. So there, that would cover a good chunk of them.

[00:49:32] **Adam:** Most of them, if they're posting anything on social media, are doing it on Instagram. That would be, you know, like all these are ways to like cover 99% of use cases. and setting aside the fact that the guy, the primary guy who has been developing this open source library just recently decided, like, I'm out,there is a community built around it and theoretically it could still survive.

[00:49:53] **Adam:** So there's that. But yeah, so I, I feel kind of painted into a corner. Oh, there's the, so here's the other thing. technically there is a security risk if you just allow the same, if you use email address as ident as, indicator of identity, right? So if you sign in with Google, and I've got your Gmail address. as, as the, the email address assigned to your account, and then later, for some reason you decide to sign in with Spotify and your Gmail address is your Spotify email address.

[00:50:24] **Adam:** Then if I did that and allowed you to then sign into that account that you created using Google authentication, then that's potentially a security risk because what if you didn't have a Spotify account and somehow somebody managed to set one up under your Gmail and then they could sign into your account?

[00:50:42] **Adam:** Not that there's a ton of risk there in terms of, using it as a jumper. Like no money changes hands through this application. The only money that will ever change hands is me billing my, the, the drop zones for how much they use the app.but I guess in theory, if somebody is a staff at the drop zone, and their account gets hacked, then prices could be changed and, and that sort of thing.

[00:51:06] **Adam:** It just would cause chaos. I don't think it would actually cause. Significant problems for drop zones, but it would be very annoying. So there's security implications there. So I have to be very careful about allowing sort of crossover from one OAuth provider to another. I'm kind of on the fence. So here's where I, where things sit right now.

[00:51:26] **Adam:** I've got Google, GitHub and Spotify, and those three I picked because they're free to use. They're, they were easy to set up. they're probably pretty common. you know, GitHub is probably the least common of the three there. Like of Skydivers.

[00:51:40] **Ben:** imagine most people, not most, but like a lot of people have a Google account.

[00:51:45] **Adam:** Yeah. There, there's honestly the, it's funny, there's a lot of people that I know that.

[00:51:50] **Adam:** Their primary, like the, when you want to email them, you do that through their Yahoo email address. But then it's like, okay, well we're gonna do a Google meet for our club, board meeting. Right. And so you have to have a Google account for that. And it's like they have a Google account and it's only for using like Google Docs with people, like sharing with people and, and Google Meet and that sort of situation.

[00:52:09] **Adam:** They don't actually use that Google account for anything, which is beyond me. I, I mean, I, I have to imagine that Yahoo Mail has gotten better since 1999 or whatever, but, can't be by, I, I doubt it's anywhere as good as Gmail, but that's just my personal opinion.

[00:52:25] **Ben:** Yo, I was on a call the other day, like, I, like I, I was watching a presentation. I. At the end, the guy had his contact information and literally his contact email was still an A OL email

[00:52:36] **Adam:** Oh my

[00:52:36] **Tim:** Nice.

[00:52:36] **Ben:** and all like God's player.

[00:52:39] **Adam:** I, I, I don't wanna be too mean about it, but if your email is like, at comcast.net, i, I judge you for it.

[00:52:47] **Tim:** At Earth net, EarthLink

## [00:52:49] Considering Alternatives to OAuth

[00:52:49] **Ben:** Have you looked into any one of these kind of authentication as a service type things? I mean things like Okta are gonna be very expensive, but I think there are other things now

[00:53:03] **Adam:** there's Auth0. I should look into that one.

[00:53:06] **Ben:** I think Auth0 is bought by Okta.

[00:53:09] **Adam:** I wouldn't be surprised, but I mean, if they have a, a reasonably generous free tier and the first step up beyond that free tier is something I could see myself paying, then I would be willing to, to start there. So here's the situation I find myself in. Not everybody has a Google account.I've got this security concern, so I have to.

[00:53:30] **Adam:** When, when, when an account is creative, right now, I am including on that account what OAuth provider was used to create the account. So if you create your account from Google sign in and you happen to sign in on Spotify, and that Spotify, your email address with Spotify is also your Google account, it actually creates a separate Google or a separate account for you on my app because the OAuth provider is different, which is I think a little bit less than ideal.

[00:53:57] **Adam:** and I, I find myself teetering on the edge of like saying, you know what, just screw it. I'm gonna go with, email and password. I, I don't love that idea, but it is the things it has going forward are, it, it's simple. It's well understood. I know how to do it. I've done it a thousand times. They, the only really negative of it is it's gonna increase the amount of data that I'm storing slightly.

[00:54:22] **Adam:** And I'm potentially signing up for the problem of having to send a bunch of emails and, the cost and the, the frustration. 'cause you know, email is not a perfect system. Sometimes they get lost, sometimes there's delays, whatever. And people get frustrated with that. But

[00:54:37] **Ben:** I

[00:54:37] **Adam:** I, I definitely wanna look into sign in services like Auth0 or whoever, especially if they can support Instagram and Facebook and those other ones.

[00:54:47] **Adam:** Like, hmm. That would be, I would honestly, even before I start making money with this, I might be, if it's not too expensive, I might be willing to pay out of pocket just to, to get on that train.

[00:54:58] **Ben:** I was listening to an interview, I don't know, a week or two ago, and there was another service. I can't, for the life of me remember what it was called,

[00:55:04] **Adam:** me.

[00:55:05] **Ben:** but I think it was, it was like a flat fee. It wasn't even a usage-based fee, but I think they don't have, I think it was, they don't have a generous free tier, or they may not have any free tier, but it's like a fixed cost per month, regardless of how many users you ever have.

[00:55:21] **Adam:** Interesting. I, I am definitely interested in this. If you can find it,

[00:55:26] **Ben:** Yeah, I'll, I'll see if I can find it.

[00:55:28] **Adam:** So if you were in my shoes, what would you do?

[00:55:31] **Ben:** I, I've been on the Magic Link train for a little while, you know, as I do these little side experiments where I, I don't wanna store people's passwords. I've been just sending out an email, but there's so low volume where it's like, I don't, I'm not paying, or it's like, I, I think I, I pay, you know, some number of dollars a month for all of the emails for like, something, I never go over it.

[00:55:55] **Ben:** 'cause it's like a, you know, a handful of emails across my blog and his little side thing.

[00:56:00] **Adam:** Right. I.

[00:56:01] **Tim:** Yeah, and you know, I host, we host our own SMTP server, so it's like,

[00:56:07] **Adam:** That sounds like hell,

[00:56:08] **Tim:** it's not bad, it's.

[00:56:10] **Adam:** it's gotta be constantly under attack.

[00:56:12] **Ben:** Well, what about if you're using, I mean, you have deep, experience with the simple email service on Amazon. Is that, is that like beyond, oh, you don't,

[00:56:22] **Adam:** no, we

[00:56:23] **Ben:** 'cause you, you, wow. That's right. That's right. You queue things up and then you, and then you send them out. That's right. Hmm.

[00:56:32] **Adam:** I, I did, I think very early on before I even got on this current sort of iteration of the, this application, back when I was trying to make super base work, I do think I did some research into SES and I was willing to, to go down that path. I might have to look at it again. right now I think if I was gonna do email, I'd probably work with Resend.

[00:56:51] **Adam:** They have a decent free tier

[00:56:54] **Ben:** With, what is it called? Resend.

[00:56:56] **Adam:** yes. It's a email as a service sort of thing. Developer friendly pricing.

[00:57:01] **Ben:** Hmm.

[00:57:02] **Adam:** You gotta find that service. I mean, you can do it offline, but you gotta find that

[00:57:05] **Ben:** yeah. Yeah. I mean, to be, to be fair, like I think the monthly bill wasn't a lot, but it wasn't trivial. I think it was like 70 bucks a month or something. So it was, I don't know if it's something you wanna start with, unless you were planning to get, you know, big, but,

[00:57:21] **Adam:** Yeah. I mean, I, I certainly don't see myself making 70 bucks a month off of this thing anytime soon.

[00:57:26] **Ben:** yeah. Yeah. Yeah. So maybe in the future iterations, is there a, I don't know how passkey work. Is that a thing? Like, is that a way that you could have tighter integration with the phones without actually having to send emails? Do passkey require emails in any way? I don't even know.

[00:57:47] **Adam:** know. I've never, never worked with them. My, my experience with Passkey is like, oh, cool. They, they exist in one password and oh, and you can create one in your Google account. Cool. Let me do that. And then the next time I try to log into my laptop, it's like, you know, okay, now press the button on your passkey.

[00:58:02] **Adam:** And I'm like, I, I don't have a button.

[00:58:05] **Ben:** Say what?

[00:58:06] **Adam:** What? So yeah, it's, it's, it's, they've definitely been promising that it's like the, the, the new thing that's gonna make everything better, but it's yet to materialize as far as I can tell.

[00:58:19] **Ben:** But this is a toughie.

[00:58:21] **Ben:** The the one thing that always bothers me with the sign in with other systems

[00:58:26] **Adam:** mm-hmm.

[00:58:27] **Ben:** is the, and, and most people probably don't even think about this, but because I'm a developer and I've had to sit through so many security training courses and seminars, you get to that one screen where it's like you just wanna log in and then it gives you that little intermediary thing like, oh, so and so would like to log in on your behalf.

[00:58:45] **Ben:** Granting this access will give them full permissions to all of your contacts and all of your emails and the ability to read all of your mail. And you're like, ah, that, I don't think that's what I'm trying to do.

[00:58:56] **Adam:** right.

[00:58:56] **Ben:** I just want them to use my email address as my login. And, I, I don't know. That always freaks me out.

[00:59:03] **Ben:** I've definitely gotten to one or two screens where I'm trying to log in and the permissions being requested seems so ridiculous that I, that I actually do stop signing in. I'm like, no, and this service isn't for me.

[00:59:15] **Adam:** Yeah. I've done that. Yeah, for sure.

[00:59:18] **Tim:** what do you do? You got, I mean, you, you're using SendGrid you said, right?

[00:59:23] **Adam:** I'm not doing anything with email right now.

[00:59:25] **Tim:** No,

[00:59:25] **Adam:** are you talking

[00:59:25] **Adam:** about at

[00:59:26] **Tim:** at work.

[00:59:27] **Ben:** mail, gun. You said

[00:59:28] **Adam:** Mail gun.

[00:59:28] **Ben:** Mail go. Oh, mail go. Okay. I use SendGrid. That's, sorry.for my little personal stuff.

[00:59:34] **Tim:** because I, I know like Zoho, they have like,uh, tier where you can do 6,000 emails a month, and it's like $3 a

[00:59:41] **Adam:** Okay.

[00:59:42] **Tim:** That's the, no, 6,000 is the free plan. The unlimited plan is $3 a month.

[00:59:47] **Ben:** That's pretty good.

[00:59:48] **Tim:** 'cause I use, and I use Zoho for, for my custom domains for sending and receiving email. So.

[00:59:56] **Adam:** Is that, like a, does that have a, a rest, API or anything like that to send email or does it have to be SMTP or what?

[01:00:04] **Tim:** I'm just using SMTP, but yeah, I'm pretty sure they have an API I'm just, for what I'm doing, it's just, it's just SMTP.

[01:00:11] **Ben:** SMTP is one of those things where I feel so dirty that I use it programmatically, but it, it's just so easy

[01:00:18] **Tim:** Mm-hmm.

[01:00:19] **Ben:** and like it just integrates with how CF mail for me works. So I'm not

## [01:00:23] SMS over Email

[01:00:23] **Tim:** Yeah. Well, it's like, so I'll give you my dirty feeling thing. So it's like, there is, you know, you can actually send a text message SMS message to someone using email.

[01:00:37] **Ben:** I was just talking about this with someone the other day.

[01:00:40] **Tim:** 'cause I was, I came across some old code of mine. I was, I was sitting like an s it, it's just, it's not even like for customer use, but it's like, it just sends me an alert. Sends me a text message in case I'm out and about. I'm not looking at my email. And, yeah, so like, I know, like Verizon, it's, it's, whatever is is the phone number@vte.com

[01:00:59] **Adam:** Yeah. You, you have to know who the provider is, and not all providers are.

[01:01:03] **Tim:** right, right.

[01:01:04] **Tim:** So, yeah, so I mean, if I'm sending it to people that I don't know who the provider, I just have, like, I send the same email, the phone number, and then at whatever, at whatever, at whatever, just, you know, 'cause it's obviously they're only, that number's only on one network, so it's not like they're gonna get four messages or five messages.

[01:01:21] **Tim:** So

[01:01:22] **Adam:** Oh, so that's a, that's a very interesting thought. 'cause my first thought was like, oh, that's a, that's kind of risky business. Business there, sending a, your authentication text to five different people on five different

[01:01:32] **Tim:** But only one's gonna get it right. You're not gonna, you're not gonna have my phone number at at T-Mobile 'cause I'm on Verizon. So, yeah. So I do feel dirty doing that, but it was like, it's free and it's super easy. I don't remember what the other providers are, but I know Verizon is VT text and, and it's like one of those things you think one day they're gonna close it and I just think not enough people know about it and they don't advertise it at all.

[01:01:58] **Adam:** Yeah.

[01:01:59] **Tim:** Early, early days of SMS, that was really what only the thing most people could do is like send an email to it. So like they just don't close that loophole.

[01:02:07] **Ben:** I've started getting formatted text messages like with bold text and italics text. I didn't even know that was possible. Like, like political things, you know, I'll get like, oh, you know, breaking news such and such.

[01:02:22] **Adam:** probably wonders if that's like markdown and the, the iPhone or whatever is, is formatting it for you.

[01:02:27] **Ben:** Oh, interesting. Maybe

[01:02:30] **Adam:** I'll text you later with some markdown in it and we'll see.

[01:02:33] **Tim:** we'll see.

[01:02:34] **Ben:** we can, I love markdown.

[01:02:35] **Tim:** Well, it doesn't sound like we're much help for you here, but I think maybe, maybe,

[01:02:38] **Adam:** Well, I mean, potentially right? You, you, you, so you put some ideas in my head, right off services like auth zero or whatever. The one that I'm gonna definitely hound Ben until he finds it and gives it to me. and then the potentially other email providers too. I, I had, so I, yeah. Hmm. I don't know what I'm gonna do.

[01:02:58] **Adam:** The, the, the other thing about this is that I had initially started to build, I think with email and password, and I built my own sort of like, session abstraction my SvelteKit app. And then I started using this off JS thing. And it does a lot of like, I'm not gonna call it magic, but it's like, okay, here it is.

[01:03:18] **Adam:** Like we've automatically created a session. It's type safe and it's attached here, right? So the person logs in, it's just like, here you go, here's the thing. And it, it doesn't make it easy to put that where you want it, right? So it's just like, here's your session.so I, I got that working. I was like, okay, this is actually super nice and I assumed that I would be able to easily add Facebook, et cetera, et cetera.

[01:03:40] **Adam:** and I just was like, okay, cool. I'm, I'm buying into this. This is the thing I'm gonna use. And so now if I'm gonna change off providers, like all of my session stuff, all the places where I'm pulling information outta the session is going to change, which is. It's gonna be frustrating, but I'm sure I'll survive.

[01:03:56] **Ben:** Oh, isn't it

[01:03:57] **Adam:** appreciate you guys being my, my, my sounding board and my rubber duck and listeners for sure. If you have suggestions, hit us up. Come join me in the Discord. I'm there all day, every day. Just about. I I was working on this over the weekend. I wasn't jumping I this last weekend and so I spent a bunch of time at home working on it and I was sending updates to my, my, I don't know what to call them, focus group, right?

[01:04:22] **Adam:** The, you know, the club president and a couple of other people. and I got a message, this morning like, did you leave your house this weekend? Like, did, all you did was send us updates over and over and over.

[01:04:33] **Ben:** Don't judge me.

[01:04:34] **Adam:** Yeah.

## [01:04:34] Patreon

[01:04:34] **Adam:** So, alright, well then, this episode of Working Code is brought to you by the guy at the party who really wants to tell you about blockchain and smart contracts.

[01:04:41] **Adam:** 'cause he knows everything about 'em and he thinks it's gonna change the world.and listeners like you, if you're enjoying the show and you wanna make sure that we can continue putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording, editing and transcription costs, and we couldn't do this every week without them.

[01:04:59] **Adam:** Special thanks to our top patrons, Monte and Giancarlo. You guys rock.

## [01:05:03] Thanks For Listening!

[01:05:03] **Adam:** we're gonna go record the after show, which, if you're not already familiar, basically just means that the outros gonna play. And then we're gonna keep talking for some time. And that is only gonna be available

[01:05:14] **Tim:** hot mic,

[01:05:15] **Adam:** yeah, that's only gonna be available to the, the people who support us on Patreon.

[01:05:20] **Adam:** and if you'd like to become one of those, then you can go to patreon.com/WorkingCodePod. We'd love to have you on the team. Just cost a couple of bucks a month.

[01:05:29] **Tim:** and you get to hear what Ben's really like.

[01:05:33] **Adam:** that's gonna do it for us this week. Actually, before I get into that, after show tease, I, I like to stick these in there sometimes. Tim had a, a near death experience of his own here recently, so, we're gonna talk about that for sure. on, on tonight's after show. So, with that said, that's gonna do it for us this week.

[01:05:49] **Adam:** . We'll catch you again next week. And until then.

[01:05:51] **Tim:** My favorite things are pizza world peace, and the fact that your heart matters.
