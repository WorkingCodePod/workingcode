---
title: "111: How To Learn Stuff Good"
description: "On today's show, we share our respective approaches to learning from the ground up, including reading the manual, building applications from scratch, and everything in between."
date: 2023-01-25
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/111-how-to-learn-stuff-good/id1544142288?i=1000596491397"></iframe>

Learning something new - whether it be a language, framework, or library - can be challenging. And, if you're already an expert in some ways, it can be both humbling and frustrating to suddenly feel like a novice in other ways. On top of that, our expectations are often distorted by time; and, we forget how long it took us to amass the understanding that we have today. This can lead to unrealistic expectations when it comes to learning something new. Not to mention that our strategies for learning might change in relation to our experience. On today's show, we share our respective approaches to learning from the ground up, including reading the manual, building applications from scratch, and everything in between.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/111-how-to-learn-stuff-good.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Carol:** For me, I can pick up things, but if it doesn't come quickly, I become very frustrated and I feel like I'm failing and why can't I figure this out? So that scares me enough that I, I hesitate to pick up new things sometimes.

[00:00:14] **Adam:** But have you tried not failing

[00:00:16] **Carol:** Yeah. Yeah. Great. Adam, thanks for reminding me. I failed.

## [00:00:42] Intro

[00:00:42] **Adam:** Okay, here we go. It is show number 1 11, 1 11, and on today's show we are going to learn how to learn stuff. Good. but first as usual, we'll start with our triumph and fails. Tim's back. Welcome back, Tim.

[00:00:55] **Tim:** Hey.

[00:00:56] **Adam:** So Tim, why don't you go first?

[00:00:58] **Tim:** Yeah, so I'm back from butt stuff.

[00:01:01] **Adam:** nobody knew that.

[00:01:02] **Carol:** mean, we didn't tell him

[00:01:03] **Tim:** Oh, you didn't tell him that? Yeah, so I had a little surgery on my backside, so I was a little tender last week, so, and on drug, really good drugs, actually, I'm not feeling super great right now myself actually, but, yeah, a lot, a lot better. My butt's fine guys. Don't worry about it. Yeah. Yeah, it's, it's fantastic.

## [00:01:21] Tim's Triumph

[00:01:21] **Tim:** so I'm going for a triumph this week, so, and I've said this before and I'm, I'm sorry to repeat it again, but I just really. This past, like, so right before Christmas holiday, new Year's holiday, we had a client, they were kind of a, an odd case of a client. They, they had a very different use case for the normal payment stuff that we do.

[00:01:43] **Tim:** And I had a couple meetings with them. I really couldn't figure out what their use case was. I had a couple calls with them, kind of thought I knew what they were talking about. I built this kind of prototype just a very quick. This is by no means a ready for production kind of thing. But this is just a, a proof of concept to show them.

[00:02:02] **Tim:** Cause a lot of times you show someone some something and it like triggers something and says, okay, yeah, you're close, but not quite. Here's what we really need.

[00:02:11] **Adam:** So then you shipped it to production today, or

[00:02:13] **Tim:** no, no, no. Yeah, I, I don't, I don't do that. Yeah. I handed it off to people much smarter, much, much, much better than I am to actually build it securely and stably. I mean, I actually got the brief, so I had the, I had the call with them yesterday and showed them what I, what, you know, showed the prototype, you know, said, I told 'em up front like, look, this is sort of a prototype of what you can do with our technology and our stuff that we use. Is this sort of the use case you're looking for?

[00:02:40] **Tim:** And they absolutely loved it.

[00:02:42] **Ben:** Nice.

[00:02:43] **Carol:** Yay.

[00:02:43] **Tim:** They're like, oh my God, we are so glad we took this call because this is, this is fantastic. This is exactly what we need. This ticks all the boxes for us, and I don't think they've seen, because I, I know who we're up against, right? I know our competitors who are up against us, and they're, I know what they're showing them.

[00:02:59] **Tim:** The same thing outta the box. They didn't build a custom for them, and so I showed them exactly what they wanted to see. Confirmed that that's what they needed. And they're like, yeah, this is, this is great. We're gonna make a decision this week. So they're making all the buying signals that, that you're looking for in a sales call.

[00:03:16] **Tim:** And I just realized how much I love that. I mean, I just absolutely love like getting into their head, trying to figure out what it is that you want, what are you trying to solve, and build it for them really, really quick, really dirty. I did not write tests, you know, I, I'm building this just for proof of concept and then I'll hand it off to the team and, you know, if we get the contract, we'll, I'll hand it off to them.

[00:03:38] **Tim:** They'll build it. Right, right. But

[00:03:41] **Carol:** Actually make it work.

[00:03:42] **Tim:** yeah, actually make it safe and secure and, and, yeah, and, and I'm fine with that because I really, I just get such a rush and I'm like trying to figure out what your, what's your problem? And show you how a possible solution can come about. And then, you know, once you're financially committed, let's build it.

[00:03:59] **Tim:** Right. So that just, yeah, just that just, I just realized that's really what I'm good at.

[00:04:05] **Ben:** So it's, you, you mentioned this idea that there's a value add and at least maybe this is my interpretation of what you're saying, of building custom stuff for clients and you, you were positioning it that this other competitor, they're not building custom stuff here at customers. I often take that stance at work that we do a lot of little custom things for our clients and I feel like our sales team and our customer success teams are like never underscoring that.

[00:04:33] **Ben:** Cuz you know, in some ways we have a, a product that's not as good as certain competitors in certain ways and, and some ways our product's a lot better in, in other ways. but I'm, my, my position has always been, yeah, but we build custom stuff. How many people can get on the phone with an engineer and in, you know, 24 hours have tweaks that they need made to the system.

[00:04:56] **Ben:** And I just, it always drives me crazy that our customer success people are not hitting that hard and being like, how awesome is it that you guys get to work hand in hand with our engineers? Like, try going to another company and getting that kind of treatment. But maybe it's just is overly impressive to me.

[00:05:12] **Ben:** Maybe that's not impressive to other people, but, I, I just wish we, we leveraged it more

[00:05:18] **Tim:** I, I think the, the pushback from a customer might be, well, yeah, it's great. While you're actually interested in creating this custom thing for me. What happens, you know, when I'm really, I'm not the hot hotness customer that you know, that you're trying to court right now, and other people are getting that and I can't, you know, I need some custom thing and I can't get it now because you know that there, that's a two edge sword.

[00:05:43] **Tim:** I, I get where you're coming from, but I've seen that where like we customize to the customer, to the infant degree and then it comes back to bite you years later because it's like, well, why can't we get, you know, we just want this thing you did this. Custom module for us five years ago when we can't get this one tweak, and we're like, well, we're not really making more revenue from you right now, so we're not interested.

[00:06:07] **Ben:** You have downgraded your plan several times,

[00:06:09] **Tim:** Exactly, yeah. The plan you didn't even know you were on. So I, I, I mean, I, I get that, I get the excitement from doing that for our customer, but it's like, , if you're gonna be roving from customer to customer and like giving them, sprinkling fairy dust everywhere, it makes you feel good. But if you're not getting the fairy dust, you know, as a customer, he is like, where's mine?

[00:06:28] **Ben:** That's, that's fair. I can respect that perspective.

[00:06:33] **Carol:** And there's something to be said about supporting multiple ways of doing something. So when you're an engineer and you're like, oh, well this page is this way for one customer, but there another customer is having an issue, it's because we've changed it and made it custom for this one customer. Now there's this whole other workflow that you have to support as an engineer and maintain, and I hate that.

[00:06:53] **Carol:** I like for everybody to be the same.

[00:06:55] **Ben:** I'll tell you, there's a, so as we talked about legacy platform, yada, yada, yada, we're about to have no enterprise customers on our legacy platform, and I can't tell you how many hundreds of places in the code is. Like, if you're an enterprise user, show them this. And if they're not an enterprise user, show them that.

[00:07:12] **Ben:** And it just makes the code so much more complicated than it has to be. I'm so excited to be able to just burn all that to the ground.

[00:07:20] **Tim:** See positives, finding positives there you.

[00:07:22] **Ben:** go.

[00:07:23] **Tim:** That's me. How about you?

## [00:07:25] Carol's Triumph

[00:07:25] **Carol:** I'm gonna go with the triumph. last week I mentioned the code I've been working on where we were having to rewrite a process that no one ever intended to be rewritten. And, you know, you gotta get at the data somehow, right? So I put it up on QA a couple days ago, tested it heavy yesterday, and realized I broke something.

[00:07:45] **Carol:** Uh, in the process of realizing I broke something, realized I had more questions, went to business only to find out what they requested upfront isn't the actual solve the po, the problem wasn't very clear upfront what we were trying to deliver. And as of like 30 ish, 45 minutes ago, there was a slack message that said, I'm so sorry.

[00:08:07] **Carol:** Everything I told you was wrong, and here's the correct information. And again, I'm so sorry. And old me would be like furious, right? That I've spent this time and now I have to go through and make adjustments, but. The way that I've matured and kind of just got set in my old age now is just go with the flow.

[00:08:25] **Carol:** Right? Like I'm not even mad , oh, I wish I had a few years. But yeah, like I'm not even mad. I'm just like, all right, we missed something. We're gonna go back, adjust, tweak. I'll get it re-delivered. All's good and we'll move on. But I'm kind of proud of myself for not letting the changes bother me and for being okay when last minute adjustments are needed.

[00:08:49] **Carol:** So yeah, triumph.

[00:08:50] **Ben:** Very nice.

[00:08:52] **Carol:** Yep. What about you, Adam?

## [00:08:54] Adam's Triumph

[00:08:54] **Adam:** well, it's a bit of a personal thing, but I'm gonna go with a triumph. we talked in our, end of the year wrap up about, one of the things we talked about was like reading and I talked about, my goal for last year was to read 24 books. I and I barely by the skin of my teeth made it and I set the same goal for this year.

[00:09:10] **Adam:** Well, so far it's the middle of January and, I think I'm three books ahead of schedule right now. I've read three books so far this this year. And I'm just, I'm happy that I'm getting ahead instead of always playing, trying to play catch up. and so I'm hopeful that I can parlay that lead that I've got into some motivation to, re finish reading the t d d book that I started in 2021 and just has been sitting on my desk for an entire year and change. So

[00:09:41] **Ben:** very.

[00:09:41] **Carol:** awesome. So do you listen to books to you or only read them? Because

[00:09:45] **Adam:** I mostly listened to books these days. Yeah.

[00:09:48] **Carol:** Yeah. I'm like, I couldn't have a book in front of me the whole time, cuz I'm like cooking dinner and taking the dog on walks and I need audio books.

[00:09:57] **Adam:** Oh yeah, that's, that's the only way I made 24 books last year was, you know, I, I, I told you guys, I, I took the week between Christmas and New Year's off, and I think I read six books that week. I spent a lot of time, at the lathe that week, and I can listen to an audiobook and, and turn stuff on the lathe at the same time.

[00:10:13] **Adam:** And so it's like, you know, to listen for six or eight hours in a day is not a big deal. It's just easy to fit it in. So

[00:10:21] **Carol:** Nice. Congratulations.

[00:10:23] **Adam:** thanks, hopefully I'll finish this book and I'll have something to say about it. So, oh, That's it for me. Ben, how about you?

## [00:10:31] Ben's Triumph But Actually A Failure

[00:10:31] **Ben:** Uh, well, you guys had three triumphs, so I feel bad saying I have a failure, so I'm gonna say this is a triumph, but it's a failure anyway, which is that I, I've been working on this project at work and, it has to do with data deletion and, and kind of purging a system from a, a both database records and also correlating S3 objects, so making sure that those are deleted as well.

[00:10:54] **Ben:** And, the, basically the, the mechanism works by building up this queue of deletion actions that it has to carry out. And then in theory, it's gonna work through this queue. And I haven't gotten that far yet. and, and the, and the, and originally I was like, oh, January 27th is sort of my shooting from the hip estimation, which gives me like another 15 days.

[00:11:12] **Ben:** And so far everything's been running smoothly. I've been feeling good about that target until I got to this week. And the volume of data that I have to delete is now starting to materialize in my head. And it's far more data than I think I'm typically used to thinking about. And, I mean, it's, it's millions of records and millions of S3 objects that I have to keep track of and make sure that my delete calls, you know, don't get 5 0 8 gateway timeouts or bad requests or whatever.

[00:11:43] **Ben:** Five oh eights, I can't remember. And,I, I don't, I know I'll get there, but the path forward is not yet clear to me there, it's taking much longer to add data to the queue, and I assume that it will take even longer to then process the data that requires a lot of a a p I calls. So I'm just, I'm, I'm unsteady.

[00:12:06] **Ben:** I feel like that January 27th deadline, which again is 15 days away, which is, that's a lot of wiggle room, but,

[00:12:12] **Adam:** That was just an arbitrary line in the sand that you guessed, right,

[00:12:15] **Ben:** Yeah, it was, it, it was arbitrary, you know, it was my shooting from the hip. This is an internal project, but I, I like to, I like to be good on my estimates. I don't usually estimate things out that far. My estimates are usually, like, I can get it done by end of week. Like, that's how far out I estimate. So the 27th is a stretch for my estimation skills, but it, it felt like it was on track.

[00:12:37] **Ben:** But, it's, it's more just like the, I'm, I've entered a world of data volume that I'm just not familiar with. So I don't have a lot of patterns ready to go. In the back of my mind, historically, I've been in a world where brute force was just sufficient. Like it could be brute forest and it would be fine enough.

[00:12:59] **Ben:** And, this is tough. This is, this is, it's humbling right now. Trying to wrap my head around it.

[00:13:04] **Carol:** Do you have some people you can work with on this

[00:13:06] **Carol:** or that? You can get like a second set of eyes on it.

[00:13:09] **Ben:** Yeah, I, I, I have some people I'm gonna probably reach out to next week once I, I dunno, take the rest of the week to try and just get as much of it done as I can. And, I, I've been slowly adding a couple of optimizations here, moving some stuff, say like, out of a subsequent query I move it up into an earlier query, but I add a join.

[00:13:30] **Ben:** So it kind of gets both sets of data at the same time. And that turns out to be a little bit easier in this particular case. There, there's little things that I'm doing along those lines and reducing the number of, database records that I have to create. But it's, I mean, it's, it's moving the needle, but it's not moving it terribly far.

[00:13:46] **Carol:** Yeah, that's baby steps.

[00:13:48] **Ben:** Yeah. The, the, the biggest thing that I can, in my past, the thing most on this scale was when we had to migrate our object storage from a local network drive onto S3. And this, I mean, just saying that out loud, I think dates, how long ago this was that we had a, a network drive for storage at work, where we had to move about a terabyte of data, or no, I think it was two terabytes of data from a network attached storage up to S3.

[00:14:16] **Carol:** And I had to script that. And, that took about 30 something days for that script to actually run once I kicked it off. Holy

[00:14:24] **Ben:** but like I didn't really have to keep track of anything, which was kind of that, that, that's what made that part easy. It was basically just, here's the file on the drive, let me push it up to S3 at a known location.

[00:14:34] **Ben:** But like the file name stayed the same. And so the application code essentially had to look in two places, with a fallback during that migration. But I didn't have to keep track of anything. I just had essentially had a, a huge list of IDs that I had to keep cursor over, you know, gave me the next thousand IDs, gave me the next thousand IDs kind of thing.

[00:14:53] **Ben:** This I actually have to like, keep track of all the data and keep track of whether or not it worked and. It's just, I don't know. Again, I'm just, I don't have a lot of patterns ready to go in the back of my mind for this. So it's exciting cuz it's new and,

[00:15:08] **Carol:** Scary, right,

[00:15:08] **Ben:** yeah.

[00:15:10] **Adam:** So you're giving your, you, you know, your arbitrary line in the sand was the 27th that was to finish coating it. Right. So then it could potentially take a month to run or something.

[00:15:20] **Ben:** Yeah, yeah, yeah. And it's, and it's, it's unclear how much it'll have to be run. Like those details aren't even relevant or not relevant. Those details aren't, given to me yet. I'm, I'm just in the building phase, like how to actually use this thing once it's built. I, I don't think we've even discussed that at work yet.

[00:15:38] **Adam:** Gotcha. And, but there's, I guess the real point that I wanted to get to is there's no real consequence if you slip by a week or two. Like,

[00:15:45] **Ben:** I, I don't think so. I don't think so. There, there's some, there's some. Pressures from outside the engineering organization to make sure this gets done. But it's, it's all internal, but external to engineering. Anyway, that's me.

## [00:16:01] How Do You Learn Stuff Good?

[00:16:01] **Adam:** Alright. Well then how do you learn stuff?

[00:16:07] **Ben:** Well, so this has been top of mind for me lately because I have been living in a, a fairly small focused world for the past, it feels like several years where I've been focusing very hard on ColdFusion on the backend and angular on the front end, various versions of Angular. part of my goals for this year was to really try to step outside my comfort zone and build some stuff, learn some stuff.

[00:16:31] **Ben:** I'm, I'm sort of a fanboy of the Basecamp people and d h h and I, I watched a couple of his Ruby keynotes recently. he, Basecamp has built this framework called Hotwire. Which is a collection of a couple of other kind of like sub libraries. Turbo Drive, stimulus, turbo frames. Turbo streams.

[00:16:52] **Ben:** It's, and, and the premise of it all is essentially what if we could deliver single page applications, spa like behavior, but kind of keep the simplicity of the older multi web page app kind of techniques. and basically it works by intercepting a lot of links and form submissions and automatically fetching data over Ajax and then swapping out parts of the page.

[00:17:20] **Ben:** So, so doing a lot of stuff that we'd be doing programmatically in a spa, but it's sort of just being done automatically via conventions. Anyway, I've been struggling to figure out how to actually learn it because one, the documentation is okay, but it, it's, it's more like, Technical documentation and not philosophical documentation.

[00:17:44] **Ben:** Like how do you start thinking in terms of building applications this way? and it's just very different from how I'm used to thinking. So it's, you know, like when I went from jQuery to Angular, from a mental model standpoint, it wasn't a huge leap because basically I was taking what I was doing in jQuery and then codifying it more intelligently in Angular, but it was philosophically the same kinds of stuff.

[00:18:11] **Ben:** This is very fundamentally different and I'm just, I'm really, really struggling to, like, I, I'm almost struggling just how to know how to move forward. Like, I wanna do the work. I just don't know what the work almost is yet.

[00:18:26] **Adam:** I, I don't wanna get too far before we take a breath to say that, to, like, we need to acknowledge that Jake and Angular are like 0% alike. Right. But like, I kind of get what you're saying, right? Like, You were, you were adding interactivity to a client side only experience, and so changing that from jQuery to Angular it wasn't like trying to plug French into Spanish or something as a native English speaker.

[00:18:54] **Adam:** Right. You know that you're still speaking the same language, you're just organizing things differently.

[00:18:58] **Ben:** Yeah. Yeah. Like with jQuery, fundamentally I'm reaching into the dom, the document object model. I'm finding elements, I'm attaching event handlers, and then I'm listening to those event handlers to then programmatically change the, the view of the document in response. And Angular fundamentally does that too.

[00:19:19] **Ben:** It just does it in a very different way, but it's, it's very, it's, it's both philosophically different, but also philosophically exactly the same. Hot wire is like completely different in that you're actually making requests back to the server to render pages. And it's, and it's just like swapping out parts of the pages and it's, it's, it's just, it's like it's turning my mind inside out a little bit.

[00:19:43] **Ben:** And I'm just having trouble, I don't know. I don't like, I don't know how to learn something so new anymore. I've like lost that muscle.

[00:19:49] **Adam:** Well, I don't wanna poo whoo, your, your thing, but

[00:19:53] **Ben:** Yeah. Yeah. Go

[00:19:54] **Adam:** I don't feel like how, maybe it's new to you. I feel like this thing came out like five plus

[00:19:59] **Ben:** yeah, yeah, yeah. Sorry. Sorry. I mean, new to me for sure. A hundred percent

[00:20:03] **Adam:** Now there's probably something that I'm missing because I have never looked into Hotwire, but how is it any different than, say, like a jQuery load, right?

[00:20:12] **Adam:** Where you say, okay, go hit this URL and whatever html it returns, just like drop it into the diviv that I'm.

[00:20:20] **Ben:** right. So it's kind.

[00:20:22] **Adam:** intercepting the request, right?

[00:20:23] **Ben:** Yeah, it's, it's trying to do that for you based on the conventions that, that you follow. but then it, it's just, I don't know, you know, maybe it's not that hard and I'm just having trouble wrapping my head around it. But anyway, I, I'm, I'm feeling very humbled by the learning experience itself, which is why I thought learning in general, especially learning new things, could be interesting to share techniques.

[00:20:50] **Adam:** Oh, absolutely. I think This is an interesting topic that we haven't covered on the podcast. So, yeah, for sure.

[00:20:56] **Carol:** we haven't ever talked about learning

[00:20:57] **Adam:** I, I feel like there's definitely some aspects of learning that we haven't covered, right? I don't know, like, I don't have, we have, we hit this topic specifically, like how do you learn a new framework, a new. I don't think we have.

[00:21:10] **Carol:** I don't know if we have. I'd have to go look at the list, I suppose.

## [00:21:13] Methods To Start Learning

[00:21:13] **Adam:** Well, so let's, let's just attack the problem head on then, or the question. So for whatever reason, whether it is personal interest or something that you want to learn to make yourself more hireable in the job market or something that you've been handed down from on high at work, you need to learn this so that you can accomplish some task, some project. Then what, how do you, how do you learn that? What's your approach? Go

[00:21:40] **Carol:** Hello, Google

[00:21:43] **Ben:** But you need a plan. I think you need some sort of a.

[00:21:47] **Adam:** I think it helps to understand h how you've had success learning in the past, right? Like some people learn better from video, so they'll head to YouTube or some people prefer to jump into the documentation. Some people might prefer. Learn just the minimum from the documentation possible and then go like, try to just figure it out by messing around with the code and see what they screw up and try to, you know, fix that.

[00:22:13] **Carol:** That's me. I tend to go at it and just kind of figure out a high level of what this is, right? Like what I'm, what I'm going at. And then from there I start finding problems. And then I look for answers to the problems. So for example, like when you're trying to figure out, like Gmail, like their api, like how you pull emails in and how you authenticate users and how you can have multiple users authenticated to one account.

[00:22:38] **Carol:** Like I just go find the problem, then find the answer.

[00:22:43] **Carol:** But yeah, so I like to high level, just kind of figure out what it is, like key takeaways, what is it? Read a little bit, maybe watch a few videos, and then I just start writing code that hits endpoints and start seeing what data's available to me.

[00:22:55] **Carol:** And then I start thinking about what the problem is I'm trying to solve.

[00:22:59] **Ben:** Yeah, I tend to. Read the documentation. I try to read the documentation somewhat exhaustively at first, skipping over things that I feel like are not relevant to me in any way. you know, a lot of technologies will do a lot more than you need. so I try to find the documentation and, and read it almost like a book from cover to cover as best I can to, to get a sense of just what's available.

[00:23:26] **Ben:** Even if, you know, none of it is really gonna stick in my mind from a depth perspective, I'll have a problem and then be like, oh, right, I think I saw something about this in the documentation. It must be possible. Let me go look for it. but this, and like when I learned Angular and the Angular IO docs are like, it's like a 400 page book learning angular.

[00:23:46] **Ben:** It's crazy. Yeah, it's massive. and this comparatively hot wire is, is just like a handful of pages, which. In comparison, it feels like there's so much in the Angular docs. It's just about the sort of like the philosophy of organizing Angular and there's a whole,

[00:24:04] **Ben:** yeah, there's this whole like, I dunno if they do this particular thing anymore, but there used to be this thing called the Tour of Heroes, which was essentially a, we're gonna build a superhero list detail application, and now let's walk through it step by step.

[00:24:18] **Ben:** You're adding your routing, you have your, your components, then you're wiring them together, and then you're feeding in data and then you're, you know, doing all this stuff and it's sort of, it, it really handholds you through the act of building an application. And, the hot wire stuff, it's, it's, there's technical stuff and like, that's it.

[00:24:36] **Ben:** There's like a little tiny bit of philosophy, but there's no like, let's build an application together. And, and, and that's tough. That's, that's hard for me because again, because this is so different. So my, my. My prototypical go read the documentation, which I, I still need to do. I haven't really read it fully yet, but like that's, doesn't even feel like it's gonna get me on the right path yet.

[00:24:59] **Adam:** Yeah.

[00:25:00] **Carol:** So is it bad that I don't like that part? I don't like the part of having to figure out how you can figure everything and how you set it up. I would much rather someone else figure that out. Hand it to me. I'll learn, I'll see if there are problems with it, but I don't wanna do that work. That work bores me and it's not fun for me.

[00:25:18] **Carol:** Like some people love it.

[00:25:20] **Adam:** you're talking about the Greenfield day, like we just get to we're, you know, it's our first day using TypeScript ands felt kit, so we're gonna have to figure out how to organize the project. You,

[00:25:27] **Adam:** you don't like that?

[00:25:28] **Carol:** pass. I would rather go work Zendesk for two weeks while you guys figure it out because that, that bores me. I get burnout really quick. My attention span's not there for it. My a d D kicks in and I can't. I can't get beyond trying to figure out the documentation and figuring out how to set up the initial configuration that I get overwhelmed and I go past, we have people who would love to do this.

[00:25:50] **Carol:** You guys should do this. And since I don't have to anymore, I'm gonna go work on something else. When you get it ready, that's when I wanna jump in, like, okay, well have you done, now teach me and now let's go

[00:26:01] **Adam:** yeah. You're, you're onto something there because the, I think the hardest part of learning something new, especially when you're doing something that is such a fundamental part of your stack, that it, you know, like if you're learning a whole new framework and it's how you organize your files is important and it's gonna have like lasting effects on the project, getting that

[00:26:20] **Adam:** wrong on day one is such a pain in.

[00:26:23] **Carol:** I mean, we all know the, the projects we've worked on, where we've went. Why did they ever start it this way, right? Like, why did Carol ever think that this was the right, you know, file structure that we should have for saving everything? Like, who thought it was great idea to do this? Like, I don't want that to be me

[00:26:42] **Adam:** Mm-hmm.

[00:26:42] **Carol:** don't want that responsibility.

[00:26:44] **Ben:** yo, that's like, sorry. Just I've, as I've been working on this stuff at work for, for deleting data, I came across a part of the code where someone stored every file as a dot png regardless of what type of file it is. it's like, it's something like weird bug that someone found and probably just never fixed cuz they're like, ah, there's already data.

[00:27:04] **Ben:** It's too late.

[00:27:09] **Carol:** that doesn't sound good.

## [00:27:12] Conference Talks

[00:27:12] **Adam:** I know I asked the question earlier, and I, I gave a couple of examples, but I was, while you guys were answering, I kind of thought of something else. So, pre, pre covid, I think my favorite way to learn something new was to start with a conference talk. Whether that was like attending it in person or watching one online, because I could know that I would go into that talk knowing nothing about the topic, and that I would come out of it knowing a couple of things.

[00:27:37] **Adam:** One, is this something that I care to continue learning about? Right? I, you know, if, if I spent an hour to know that, I don't ever need to think about it again. That's an hour well spent. and b, If I do want to continue to learn about it, then I have a good vocabulary.

[00:27:52] **Adam:** Like I know the, the keywords that I need to search for in the docs that'll like remind me of what they taught in the presentation or the things that I need to expand my knowledge on. I feel like that's such a hard thing when you're taking on something big. , you understand what it is you're trying to accomplish, but you don't know the way that the, the project, the framework, whatever, labels these things.

[00:28:13] **Carol:** And when you go to a conference too, usually the person speaking on it is eager about the project or about the technology that they are presenting on. So while you're learning, you also see someone else being very passionate about it. And that does motivate me to go learn more. So when I'm like, okay, I feel like I have a community supporting me, and I have some people who know.

[00:28:35] **Carol:** I can reach out to, or I can go read their blogs, then suddenly I feel a little more safe in learning it and less likely to just fail upfront and never wanna pick it up again.

[00:28:45] **Adam:** Yeah. So then after the conference presentation, I guess I've kind of developed this, bad habit, I'll say like good slash bad habit of like, Only just barely skimming when I'm reading something. Like if I'm reading the philosophical docs like Ben was talking about, or if I'm trying to read through tech docs, I will skim.

[00:29:06] **Adam:** I like the first three or four words of a paragraph. I'm like, no, this paragraph doesn't matter matter to what I'm trying to learn. This paragraph doesn't matter. And like, it, I've noticed myself doing that, like trying to read emails from people that are like, really important and I'll, I'll skim it and go, wait, no, no, no.

[00:29:20] **Adam:** I need to read this whole

[00:29:21] **Adam:** thing. Go back and start over. And then halfway through it I catch myself skimming again. I'm like, no. so yeah, like, you know, figure out the vocabulary from a talk. And then like, for me from there, it's a mix of read the docs to, you know, get, get myself into trouble, right?

[00:29:39] **Adam:** Like learn just enough to,

[00:29:41] **Ben:**

[00:29:41] **Adam:** make something bad and broken. And then, yeah, I don't know. Like, it's not a, it's not a direct, this than this than this for me.

## [00:29:48] Courses

[00:29:48] **Adam:** Like sometimes I'll. Do like a video training? there's a couple of, like, I really like West Boss courses and I really like egghead courses.

[00:29:56] **Adam:** They tend to be organized well, and I like the way that they chunk things up into really small, short videos so that like, when I want to come back in six months, I know. Okay. I may not know exactly which one it is, but there's a, there's a video on, you know, flexbox, you know, aligning vertical versus horizontal.

[00:30:12] **Adam:** I just have to find the right video and I know it's gonna be a five minute thing and it's gonna teach me the thing that I've forgotten. yeah, like I don't have a, a very prescriptive way that I like to learn, but

[00:30:22] **Ben:** I, I also, I've been, I've been trying to watch some YouTube videos cuz it, there is something very, very helpful about seeing someone do something, like seeing someone actually wire something together. In a way that just reading about it doesn't always connect with. So that's, the YouTube videos have been really helpful.

[00:30:40] **Ben:** I, I would, I like the idea of doing a course though. I should see if there's a course. There may, there may be.

[00:30:46] **Carol:** The other thing I like about videos like that, so we have you Demi, right? And when I was like, I need to learn Docker because I'm gonna learn Docker and be a cool kid, I could rewind it and go, what did he just say? Because this isn't making sense to me. And I would listen to it again. I'd be like, okay, I'm gonna go click through a few things, pause this, see if I can figure out what's going on.

[00:31:06] **Carol:** And then be like, oh, okay, play again. Cuz now I know.

[00:31:10] **Adam:** Yeah. That's one of the great things about a video course is like you can build along with them. And then for me, you know, I've taken a bunch of different West Boss courses. the, the egghead stuff, I tend to just like sit and watch and try to absorb. And then after I'm done learning for the night, then I'll come back the next day and try to apply what I learned to my own work projects.

[00:31:28] **Adam:** But for something like the West Boss course where he kind of goes soup to nuts on something, I will often try to. Do the, like, build along with me thing, but I won't build exactly what he's building. Like I'll just sort of come up with my own idea. You know, if he's doing a e-commerce store for sneakers, I'll do, you know, pizza or something and, you know, try to apply what I'm learning from his lessons in a different way.

[00:31:53] **Adam:** And I think that for me, that helps the concepts gel, right? I'm not just, I'm not just parroting back what I saw him write. I'm trying to understand why he wrote what he wrote, and then apply that knowledge.

[00:32:05] **Carol:** And see, I think that's great for someone who's developed, right? And who understands engineering and understands software development. But for me, when I was starting out, there's no way I could have done that because I needed to kind of move on to the next set and go, okay, what did I get wrong? Because I feel like I'm understanding it, but my code's not executing.

[00:32:24] **Carol:** It is not working, and I don't know what I got wrong. So I would pull up the next like, set of instructions or you know, whatever the next code set was that you pull down and go, okay, here's where I messed up at. This is where I broke the logic. So early on I definitely just copied after, right? You know, did one for one.

[00:32:42] **Carol:** But I can see what you're saying with, I follow better now if I do it my own way and understand and put it, relate, like put it in, make it relatable to something that makes sense to me,

[00:32:54] **Adam:** Yeah.

[00:32:55] **Carol:** So,

[00:32:56] **Adam:** Yeah, that's a really good point. Like where you are in your career, whether you're a newbie or a tired old, you know, tire with a hole in it like I am.

[00:33:06] **Carol:** All of us now we're old people.

[00:33:09] **Adam:** You know that, I think that has a huge bearing on how you learn.

[00:33:13] **Carol:** Yeah.

[00:33:15] **Ben:** I also like to do, I, I don't know if this is a standard term, but I've always called them white page examples where I, I sort of, take a small feature of a framework or a library, and I try doing just that in a standalone page like that has no application to it. It's like, here's a button. What happens when you hover over the button and apply some technique?

[00:33:36] **Ben:** So like standalone, just white page. and, and I think for this particular learning adventure, I, I went too early into trying to build an application and not enough. I didn't have enough r and d. How does any of this actually work upfront? I sort of, I started dove in too early. Now to my credit, I will say that I didn't go down rabbit holes, meaning like, I don't even have a style sheet applied to this application.

[00:34:04] **Ben:** It's all

[00:34:05] **Ben:** just times New Roman or whatever Chrome does by default these days. And it looks horrible and, you know, all the lengths are purple. And, so I, I could have very easily rabbit hole down. How do I create. A design system that's outside of something like Angular, which is where I'm used to having a design system.

[00:34:22] **Ben:** which could easily be a whole learning adventure, I think, in and of itself. So,

[00:34:26] **Ben:** but I still went in too early. I went too deep, too early.

[00:34:30] **Carol:** And there's something about starting, right? Where you have all these off, you're like, I wanna do it all, and I wanna get it all right. So then you never start. So it's good that you did start and you didn't, you know, dive down any rabbit holes,

[00:34:41] **Ben:** It, it does, I do feel, I do, I am very proud of myself,

[00:34:45] **Carol:** Yeah, it's a big

[00:34:46] **Ben:** I did, I did something. Damn it.

[00:34:48] **Carol:** Yeah, I think it's a huge accomplishment. That first step is the hardest. Like today, this is not code related, but I've started working out again, like since I've been sick, I had to cut back and couldn't do anything, and I finally started working out again. So at the end of my workout, the like burnout thing was pushups.

[00:35:06] **Carol:** And I am on my like two hands on the floor going, I can't bend my elbows, I can't bend my elbows. My arms hurt so bad. And I did one. And I was like, that's a, that's a win. That's a win that I'm burnt out. I burnt myself out. It's done. One push up. I started, I finished. I'm good.

## [00:35:24] Exercises

[00:35:24] **Adam:** What about, like exercise type stuff? Do you guys ever do like advent of code or any of those other just like opportunity to practice? you know, problem solving there would be, you know, back in the day there were people that would like post every Friday on their blog. A different challenge. Ray Camden used to

[00:35:41] **Ben:** Oh yeah.

[00:35:42] **Adam:** you know, different things like that.

[00:35:43] **Adam:** Do you guys ever do any of that anymore?

[00:35:46] **Carol:** I have to say no, and I have to say I never did.

[00:35:50] **Ben:** I, I do it randomly.

[00:35:51] **Adam:** yeah, I feel like it, it provided more value to me when I was younger in my career. I feel like right now, I, if there was any value that I could get from it, it would. Probably be, you know, enjoyment of like, you know, solving a problem. I guess if I was gonna get some sort of tech value out of it, like trying to use it as an opportunity to learn something new.

[00:36:13] **Adam:** Like, you know, if I'm solid in, JavaScript, but I wanted to try to learn Swift or Kotlin or something. And so if I have the basics of the language and then I want to try to use these problems that are presented to me as something to work on in that new language to me, gives me a reason or, you know, a specific thing to focus on instead of like, okay, here, go learn Kotlin.

[00:36:35] **Adam:** Yeah.

[00:36:36] **Carol:** So I feel like I'm at a spot in my life and my career, like where I can start doing those things. Up until this point, my free time has been spent raising kids and I did not want to spend extra time outside of work learning a ton. Like I would learn some, but a lot of what I learned was on the job and what I was like, what was needed to do my job and to do solid application design.

[00:37:01] **Carol:** So now having free time, I actually have the ability to start doing some of those things.

[00:37:07] **Ben:** Yeah, and definitely everyone has their own experience, so I don't wanna, I can only speak for myself, but, but things like advent of code, in theory, I get super excited about that idea and having a daily challenge. And then the reality of life sets in and I have to walk the dog or like I have to hang out with my wife, or I have to do

[00:37:26] **Ben:** something. Yeah,

[00:37:28] **Carol:** I am air

[00:37:29] **Ben:** to hang out with my wife,

[00:37:30] **Carol:** Oh, such a challenge.

[00:37:32] **Ben:** stops Um,and I just like, I don't have the energy for it, but, you know, then I look at someone like Adam, who has a wife and kids and like, has literally read

[00:37:42] **Carol:** A dog and

[00:37:43] **Ben:** this podcast. So

[00:37:45] **Adam:** I did what while we're recording this podcast,

[00:37:47] **Ben:** read two books. So

[00:37:51] **Adam:** Just

[00:37:52] **Ben:** know, we we all have different energies and, I, I don't know, I I, I, I wanna be the person who does things like advent of code, but I, I just, I don't motivate to prioritize it.

[00:38:05] **Carol:** Yeah, I get that. I agree.

[00:38:07] **Carol:** I think I will down the road.

[00:38:09] **Adam:** I have to be back my own ambition sometimes you know, so I, I'm around airplanes a lot because of the skydiving that I do, and for a long time I've been like, it'd be kind of cool to learn to fly, like,

[00:38:21] **Adam:** you know, that'd be

[00:38:22] **Carol:** Me too. I want to.

[00:38:24] **Adam:** and. Something, you know, I was on YouTube at one point in the last couple of days and they just randomly showed me like a, you know, somebody doing their first solo flight sort of thing.

[00:38:33] **Adam:** It's not, not a huge, I mean, it is a huge accomplishment for that person, but it's, it's not that massive, you know, it is something that a lot of people have done. but I watched the video and I was like, that looks like so much fun.

[00:38:45] **Carol:** Yeah.

[00:38:46] **Adam:** And, and I have been down a YouTube rabbit hole. I think I probably watched two or three hours worth YouTube videos about like, people, just, people flying.

[00:38:52] **Adam:** Like some, sometimes I watch videos and it's just like, I'm gonna fly from here to here and we're gonna stop and get fuel and you're gonna see what it's like to talk on the radio and, you know, you have to adjust this and adjust that. And, and it's like nothing gets accomplished in this video. I'm just watching somebody fly and talk on the radio and then land and it's like, okay.

[00:39:11] **Adam:** But it's so interesting. And I'm like, I, I really wanna do that. And it's like I have. at least two, depending on how you count. Maybe three to five hobbies that are really expensive and no time for extra hobbies right now. And this would be probably the most expensive hobby. If I were to take it on, it would probably be the most expensive hobby I've ever had.

[00:39:31] **Adam:** And that's saying something oh, but it's so tempting.

[00:39:37] **Carol:** I will say there's something about some people like you who are just natural learners and you pick up things quickly and you enjoy it. For me, I can pick up things, but if it doesn't come quickly, I become very frustrated and I feel like I'm failing and why can't I figure this out? So that scares me enough that I, I hesitate to pick up new things sometimes.

[00:40:01] **Adam:** But have you tried not failing

[00:40:04] **Carol:** Yeah. Yeah. Great. Adam, thanks for reminding me. I failed.

[00:40:11] **Ben:** Quick side tangent. I was listening to, I don't know if it was a news piece or a podcast about design. I can't remember what it was, but they were talking about how touchscreens are being put in a lot of places. Like your card dashboard probably has a touchscreen these days. And they were saying that, they, I don't know if they were going to, or they experimented with putting touchscreens inside of cockpits and planes and like immediately realized it was a terrible idea because even though you look down and the dashboard maybe has like 300 switches on it, they were saying that pilots can reach down without looking, locate the switch, flip it, and feel that it has been flipped and continue to, you know, keep their eyes on the horizon.

[00:40:53] **Ben:** And that essentially a touchscreen gets rid of all of that kind of, of, accessibility.

[00:40:58] **Carol:** Yep.

[00:40:59] **Ben:** N not to mention they're like constantly now it seems releasing, studies about how the touchscreens in cars make driving less safe.

[00:41:07] **Carol:** Oh,

[00:41:07] **Carol:** absolutely.

[00:41:08] **Adam:** The other thing, even having to look at it e even if you don't consider having to look at it, you know, in a plane, even on, on driving in a car, you know you're gonna hit bumps. There's gonna be wind pushing you around and you know, like, you know, you're gonna reach for a button that does one thing and you're gonna end up touching a button that does a different thing.

[00:41:26] **Adam:** And that may not be what you wanted.

[00:41:29] **Ben:** Yo. I would love for the next revolution in automobile design to be buttons.

[00:41:39] **Adam:** we're just gonna control planes with, chat. G P t isn't, that's a whole thing right now, like, chat based commerce or something, right? Like people are, assuming that that's gonna be the next step in e-commerce is, conversational commerce.

[00:41:58] **Ben:** Oh, interesting.

[00:41:59] **Adam:** Yeah.

[00:42:00] **Adam:** Built a couple businesses are being built around that.

## [00:42:03] AI

[00:42:03] **Ben:** I have yet to motivate to try any of the AI stuff.

[00:42:06] **Ben:** I tried the, the, yeah. Yeah. So it's interesting. I was listening to a podcast the other day on, it was the Ezra Klein podcast and they were interviewing this guy who's a, a big into artificial intelligence going back decades or something.

[00:42:20] **Ben:** And he was saying that the fundamental problem with all of the AI stuff that's come out recently is that it is essentially, auto complete. Like really fancy, auto complete is kind of how he phrased it. and that, so you can only, it has no sense of right and wrong or, or like even intent. All it can do is take what you're giving it and then do its best based on the things it's been exposed to, to try and complete that.

[00:42:42] **Ben:** Which is why, you know, what is it like Stack overflow? They had to ban it, right? Cuz people are coming out with all these answers that sounded really good, but were.

[00:42:51] **Carol:** Yeah.

[00:42:52] **Ben:** And it's said that it's just a fundamental problem that no matter, you know, there's this idea that, oh, if we just keep giving it a larger and larger and larger data set, it'll just become better over time.

[00:43:03] **Ben:** Which obviously it has to, to a point. But it said ultimately there's a fundamental disconnect between what it's trying to do and what people needed to do. And you, you need to have a, an intelligence that's both this sort of pattern matching, but then also based on, on like known laws and you know, on how objects relate.

[00:43:22] **Ben:** Anyway, I'm not gonna explain it very well because it's not stuff I understand, but all to say that there's like fundamental problems with the way all the AI stuff is working now, where it can really only get good to a point and then it'll never get better.

[00:43:37] **Carol:** It has its limitations. I will say I use copilot all the time in that I hit tab, I read what it says, and then I hit escape and type what I want.

[00:43:48] **Ben:** But, and, and I think that's, that's the kind of stuff where it makes the most sense, where it, it is to a large degree, like a really fancy auto

[00:43:57] **Carol:** it is, yeah. Agree. Because I don't use a lot of the code suggestions other than when it just spills out like, okay, I'm trying to set true false on some variables and I'm typing out the variable name, and it's like, oh, well I assume you're going to now set something for the one that's too above it, so I'm gonna go ahead and put that in for you.

[00:44:13] **Carol:** I'm like, yep, you're right. I was, cuz I wanted to test that. So go ahead and turn that true real quick for me and tap, tap done . But when it's like, here's a whole block of code, I'm like, okay, I'm reading it, but I'm gonna type this out myself because I get joy from typing it. Like I love typing code. So I get joy from typing out my entire block reading it and going, okay, this mine not okay.

[00:44:37] **Carol:** That's what I wanted to do and you created it for me. So it's not the same.

[00:44:43] **Ben:** I agree. I enjoy typing

[00:44:44] **Carol:** I do too.

[00:44:45] **Adam:** Is there more to say here?

[00:44:47] **Carol:** I'm not the biggest fan of learning, but I like typing.

## [00:44:53] Expectations

[00:44:53] **Ben:** Well, maybe I just have to also temper my expectations. It, it, it's a, you forget how long it took you to learn something. I think you,

[00:45:04] **Ben:** I

[00:45:04] **Carol:** is true

[00:45:05] **Ben:** I, I remember how well I know something.

[00:45:08] **Adam:** Yeah.

[00:45:09] **Ben:** and I forget that, oh, that knowledge that I have packed away in my head is accumulated over 20 plus years.

[00:45:16] **Ben:** And, and I have to realize that getting anywhere close to that even, you know, to even call it proficiency is probably not even, not even that much, but like, to just become comfortable probably takes a lot longer than I'm expecting it to. So I just have to embrace that.

[00:45:34] **Carol:** and it's okay to fail.

## [00:45:36] Having A Goal

[00:45:36] **Ben:** And, and I do think it's super helpful to have a, a thing to build, you know, I think I said

[00:45:42] **Ben:** this on a pre Yeah. Like, I, I think I said this on a, on one of the previous episodes where I, I didn't quite realize how much of my learning was tied to and related to what I was doing at work. So when the type of work I was doing at work started to stag.

[00:45:59] **Ben:** So did my learning, and that was very frustrating cause I didn't quite know how tightly coupled they were. So if I have a project that I can build, which is, which is what I was trying to do over the holiday break, at least I, it's like I, I hit real world problems that then motivate me to solve in, in a targeted specific way instead of just, you know, generally trying to learn everything about library or framework X, Y, Z, you know, it gives me specific targeted actions that I need to take. So I feel good about that. I feel like I'm doing that right. I'm just, I'm just stumbling.

## [00:46:32] Patreon

[00:46:32] **Adam:** Okay. Well then this episode of Working Code is brought to you by not failing. It's tantamount to success. And listeners like you, if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:46:49] **Adam:** Patrons cover our recording and editing costs. And again, we're having a goal to get enough in the bank to start doing transcriptions this year. That would be awesome. and we couldn't do this without every single one of them. So thank you all so much. Special thanks of course to our top patrons, Monte, Shawn and Giancarlo. If you'd like to help us out, you can go to patreon.com/WorkingCodePod,

## [00:47:08] Thanks For Listening!

[00:47:08] **Adam:** homework this week. Let's say, why don't you join us on Discord workingcode.dev/discord. Come join the community. talk to other like-minded developers all across the globe. And, yeah, it's good, fun, casual place to hang out.

[00:47:22] **Adam:** so you probably figured out, partway through this episode, Tim had to, bail. He just wasn't feeling good. He thought he was up for recording, and then pretty quickly after we got going, he just wasn't feeling up to it.

[00:47:32] **Adam:** So, We gave him the week off, but we expect him back double time next week. I wanna make him host he's not gonna hear that either cuz he doesn't listen to the, to the podcast. Anyway, that's gonna do it for us this week. We'll catch you next week and until then

[00:47:45] **Ben:** Remember folks, your heart matters.
