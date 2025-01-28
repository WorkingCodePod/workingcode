---
title: "049: Revisiting Replatforming"
description: "On today's show, we talk about the choices that we'd personally make if we had to rebuild our application using a new language."
date: 2021-11-17
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/049-revisiting-replatforming-there-is-no-correct-answer/id1544142288?i=1000542206157"></iframe>

One of our fans on Patreon is about to embark on a large "replatforming" endeavor. His team has decided to move away from their "traditionally coded" application (think hard to maintain, big ball of mud); and, will soon rebuild the server-side aspect of their application using a new language. The team isn't yet sure what language they'll use (this is how the topic came up in [Discord][working-code-discord]); but, they know that they want a statically typed language with a strong separation of concerns in the MVC (Model, View, Controller) layers.

In episode 25, we talked about [breaking up with your tech-stack][working-code-25]. But, this discussion of replatforming has rekindled our interest in the topic. On today's show, we talk about the choices that we'd personally make if we had to rebuild our application using a new language. Based on historical trends, it feels like a gamble no matter what you do. As such, we also talk about how we might go about validating some of our choices.

## Notes &amp; Links

- [Rich Hickey: Simple-Made-Easy](https://www.infoq.com/presentations/Simple-Made-Easy/)

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. Or, leave us a message at (512) 253-2633 (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[editor]: https://www.zcross.media/
[rich-armstrong]: https://www.linkedin.com/in/armstrongrich/
[working-code]: https://workingcode.dev/
[working-code-25]: https://workingcode.dev/episodes/025-breaking-up-with-your-stack/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/049-revisiting-replatforming.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** if one is going to go through the act of replatforming, could you not think of sticking with the same language, but rebuilding the same thing using modern techniques essentially as replatforming?

[00:00:12] **Adam:** yes, you could think of that as replatforming, but I think that it would be totally valid for any team to decide. We don't think that this platform has a future, whether in general or with us, we have reasons that we just don't want to be with that platform. And that's a totally valid reason to switch, right?

[00:00:30] **Adam:** Like if literally a hundred percent of your team hates working on it, on that

[00:00:35] **Adam:** platform.

[00:00:35] **Carol:** problem.

[00:00:36] **Adam:** And that's a valid reason to find something else.

[00:00:39] **Carol:** Or the language is actually not being supported anymore. Like that would be a

[00:00:43] **Ben:** yeah, yeah, yeah.

[00:00:44] **Ben:** That's fair.

[00:00:45] **Adam:** hiring

[00:00:46] **Carol:** Yeah. hiring is

[00:00:47] **Carol:** an issue.

[00:00:48] **Adam:** a really good reason to.

## [00:01:09] Intro

[00:01:09] **Adam:** Okay. Here we go. It is show number 49 and on today's show, we're going to discuss replatforming a topic that kind of came up in our Discord this morning. And actually we've kind of met a, discussed this in the past on episode 25.

[00:01:22] **Adam:** We'll discuss that a little bit later, but, we're going to revisit it and we're actually going to answer the questions this time. but first as usual, we're going to do our triumphs and fails. And Carol, it is your turn to go for.

[00:01:32] **Carol:** Yeah,

## [00:01:32] Carol's Triumph

[00:01:32] **Carol:** guys, I'm going to kick us off with a triumph. So, we hired a new engineer and I have spent 10 solid working days, mentoring him, and he has two full requests out and he is working pretty smoothly, which is pretty much like record for us. We'd never get anyone out this quick. Usually it takes a lot longer just to get through training and onboarding and we straight up have them rolling.

[00:01:57] **Carol:** And it's really, really good. I'm very stressed out because I miss writing code and I am just tired of answering questions all day long, but he's gotten two PCRs out. He's got tests, he's got task over and testing, and I feel like I've just done a really good job, onboarding someone for my first time onboarding.

[00:02:17] **Carol:** And it's just went really well. So I'm going to call it a triumph and I'm really happy with it. So yeah,

[00:02:23] **Adam:** Can I ask, was it a senior role or a junior role or somewhere in between?

[00:02:28] **Carol:** it senior. We only hire senior engineers, so we don't hire any junior of our company. We only hire, pretty qualified people. So it is someone who already knows code, but the code isn't the issue. It's understanding a whole new workflow. It's someone who's never written tests before. So I spent four hours yesterday morning just going through how mocking works, because if you've never written a test before and you don't understand mocking, you just.

[00:02:53] **Carol:** Wrap your head around it. So I was getting some pushback from him on this, just isn't going to work. I'm like, look, just type it Tiflis I'm saying, and let me show you, it's literally a testing framework. Trust me when it calls the get for this. we've told it what gets going to be. It's going to know that we've told it what the data's going to be for it.

[00:03:12] **Carol:** And then when it runs, he's like, oh my God. So it's

[00:03:18] **Adam:** mind

[00:03:19] **Carol:** mind blowing, like distrust me type the words. So it's just been, it's been good. It's been good for me to kind of receive someone new to it as well. But, I just feel like it's went really well and I'm happy. It's the first time I've mentored someone, here.

[00:03:34] **Carol:** So I'm happy. Yeah.

[00:03:35] **Carol:** Try it.

[00:03:37] **Tim:** I think a pretty know who pretty much know who you talking about. He's a smart guy. So he catches

[00:03:40] **Carol:** Yeah. He has the, and he's eager to learn and wants to show himself pretty quickly. So it helps. Yeah.

[00:03:47] **Ben:** And were you a pair programming when this was going on? I mean, how did you onboard him?

[00:03:51] **Carol:** Yeah. So, I signed in through, I literally have just sat with him? for hours and hours on Google Hangouts. it seemed to be the easiest way to show everything. So he showing me his code and rather than me taking control and typing, which is what I would have done in the past, I would just been like, here, let me type that out for you.

[00:04:08] **Carol:** I'm like, no, no, no, no, no backspace type this exact thing inter and now do you see it? He's like, oh yeah. Now I see it. So it was a lot of describing when I was doing, but having him actually do it and having him run it locally and have him run all the tests locally so that he wasn't just seeing what I was doing.

[00:04:26] **Carol:** He's actually doing it himself. So it took longer. But I think he learned a lot better and a lot more thoroughly than if we'd done it kind of the old way, which was me doing it and just observing. Yeah. That's me. I bet you.

## [00:04:42] Adam's Triumph

[00:04:42] **Adam:** I have a triumph this week. It's actually a triumph from today. we are actually considering let's call it relevant. We are kind of, sort of considering replatforming, one little like module of our application. it basically it's written in react, but it's like super old reacts, like react 14 or 13, something like that.

[00:05:03] **Adam:** and it's on a really old stack of Babel and Webpack and it's a maintenance. It's a, yeah, it's a maintenance nightmare. just because it's so outdated, we haven't done anything to keep it up to date. And so every time we have to make a change it's hell on earth to, to deal with. And, we could put in the work to sort of bring it up to modern react.

[00:05:24] **Adam:** but we've grown to have some growing, like a lot of the decisions that we made when we made that app were, later changed and the code wasn't as cleanly, refactored,things were kind of left in a little bit of a messy state. And so we are also eager for a rewrite at the same time. And so, I've been given the green light to do some experimentation with felt and tailwind And, oh my goodness. It is fire. I have had so much fun today was one of those days when you just like, I got the headphones on, I crank up the music to 11, even though my tinnitus is already like really bad. We've got the caffeine on full tilt and I'm just like cranking away having so much fun learning and writing code and playing with new toys and.

[00:06:07] **Adam:** I love it. It's amazing. there's, things I had to figure out nothing is ever easy, but,it's just my, read on spelt is like, they took everything. That's annoying about writing an app with react and just made it better

[00:06:21] **Ben:** that's cool.

[00:06:21] **Tim:** Yeah, you'll have to give us more detail when we get into the meat of this topic today.

[00:06:25] **Carol:** Yeah, it sounds like they don't relate.

[00:06:27] **Adam:** maybe. But yeah, so I've just had a tremendously fun day. and, I'm still riding the high from that.

[00:06:33] **Adam:** So.

[00:06:34] **Carol:** Is that. what the host do you guys listen to the bike shed?

[00:06:38] **Carol:** Is that what the host works on? They do a lot of salt

[00:06:41] **Carol:** projects, right?

[00:06:42] **Ben:** he does spell. And so does the guys from

[00:06:44] **Ben:** a syntax.

[00:06:47] **Carol:** Okay.

[00:06:48] **Adam:** Yeah, Scott from syntax does a good amount of salt. I think west probably has experimented with it, but Scott is all about it. He's so Scott Tolunsky, has a course platform. Like he sells new courses, just like video tutorial courses, a new one every month. And so he's got this whole platform and he converted the whole thing to spell it.

[00:07:10] **Adam:** D he said he got to like 80% in a weekend. So

[00:07:15] **Carol:** That's a lie.

[00:07:16] **Adam:** yeah. Yeah. Like, they kind of kicked the can on it for awhile and he's like, eh, that's, you're not supposed to do that. You're not supposed to like, oh, I'm just gonna rewrite the whole thing. And he was like, but I'm interested. So he was like, oh, let's see.

[00:07:26] **Adam:** Let me see how far I can get in a weekend. And the weekend was over. He's like, holy cow, I'm this close. I might as well finish it up. Yeah, it's really interesting technology there. They're getting really popular. The developer satisfaction is really high. The tooling is great. I'm just having a blast. Can't speak highly enough about it.

[00:07:42] **Adam:** So until one, two,this is my first project using tailwind. And like I said, this is my first project and I'm not super up on it, but my first impression is that it's like, CSS bumper bowling. Right? So you can,

[00:07:57] **Carol:** was is how, when can, you circle back to that?

[00:07:59] **Adam:** yeah. So tailwind is like a framework for making your own CSS design system sort of like it's got a default sort of a set of colors and whatever you can change all of that.

[00:08:10] **Adam:** But really where I think tailwind thrives is. It has, good defaults for spacing, right? So instead of saying like the spacing is three pixels or nine pixels or whatever, it's like, it has levels, right? So like, padding one, padding, two padding, three padding, four padding, five padding, six all the way up to, I think it goes to 10 and it's not just like one pixel to pixel three pixel the higher, the number, the larger it's growing sort of grows exponentially.

[00:08:35] **Adam:** And, but it's consistent, right? You're padding in your margins. As long as you're staying within this system of like, number ranges, they give you, it kind of, like I said, it's bumper bowling. it's not going to keep you from,what's the bowling term, get rolling a zero, right? It's not going to keep you from getting a zero, but it's going to make it much easier to knock down a bunch of those pins.

[00:08:54] **Adam:** Right. Anyway, I've gone on for way too long. That's my triumph. I'm writing.

[00:08:57] **Adam:** Hi Ben, what are you got going?

## [00:09:00] Ben's Triumph

[00:09:00] **Ben:** I'm also gonna follow up here with a triumph. I actually took today off and I'm taking tomorrow off and, I've just been feeling. Burned out and not burnt down. That's too extreme. I've been just feeling physically and emotionally challenged. my wrists I've had on and off repetitive stress strains on my wrist for the last like 15 years.

[00:09:23] **Ben:** and usually it's really under control. And like the last two weeks, I'd say my wrist had been really achy just on and off all day. So I'm trying to give myself a little time to recover, which,is a new concept for me. Usually I just try to muscle through it or bear down. so I'm pretty excited.

[00:09:42] **Ben:** I feel like I've reached a level of maturity there, in my career where I can take a few days off just for health reasons and, kind of coinciding with that and this dovetails with the show as well. I'm using that as an opportunity. R to kickoff and, more upgrades to my blogging platform, which my blog has been around for a really long time.

[00:10:00] **Ben:** And the code that runs it is really old. so I had my hosting provider upgrade me to the latest Adobe ColdFusion. So as of yesterday, it's running on Adobe ColdFusion, 2021. and I was basically on ColdFusion and 10 for about a decade. So, I've got many versions to, now fold into the sweet CFML goodness that, underlies the magic.

[00:10:25] **Ben:** That is the visual rendering of the blog. So

[00:10:28] **Ben:** I'm

[00:10:28] **Ben:** pretty

[00:10:28] **Ben:** excited about that.

[00:10:29] **Adam:** You should convert as this

[00:10:29] **Adam:** felt.

[00:10:31] **Ben:** Well, I mean, I get, I'm always playing around with what I can do on the front end. I played around a little bit with, parcel, which I think is parcel might actually be what's, compiling the JavaScript, but. Yeah, I'm just excited that, I'm taking time off and, just doing me for awhile.

[00:10:46] **Adam:** So you took a vacation day to work on your.

[00:10:48] **Carol:** I

[00:10:49] **Carol:** was going to say, it sounded like you didn't

[00:10:51] **Carol:** take your risk, like away from the keyboard. Really.

[00:10:53] **Ben:** no, I, I put a couple of, I put like two hours into it this morning, my early morning hours. And then the rest of the day, I was just out and about walking the dog taken in the crisp fall air and, just loving life. So pretty happy about that.

[00:11:08] **Adam:** for you.

[00:11:09] **Ben:** yeah. And it just to circle back on tailwind.

[00:11:13] **Ben:** One of the things that I feel like I've not done really well over the bulk of my career is experiment more. I do a lot of experimenting, but the experiment is really in a very narrow scope of things. And someone was actually asking the Discord about the various online learning services. And, I, what I want to try to do is when I have an interest in a topic, I just want to find a course on it and just take it, even if I don't follow along with code or I don't actually try it for myself.

[00:11:40] **Ben:** I actually looked up tailwind courses on you to me the other day, and there's a bunch of them. And, they're super inexpensive. They're like 11 bucks or something for a couple of hours. And I feel like if I could just sit there and have someone tell me everything about how a technology works, then it'll set me up to decide whether or not I want to dig in deeper on my own or how I could theoretically work it into something that already exists.

[00:12:03] **Ben:** And,I wanna use educational resources a lot more than I have historically,

[00:12:07] **Ben:** just going

[00:12:08] **Carol:** I get that. Yeah. We get you to me at work. And I have found myself just streaming them in the background and listening, even if I'm not following along and actually doing the project or writing the code with it. one of the recent ones I did was on just some container stuff. And I was like, even though I'm not building out everything, when it's with it, just hearing the hierarchy of it and hearing how they work.

[00:12:28] **Carol:** I'm like, okay, it's making sense to me. Like some of the things I didn't know or clicking. So I get that. I get the playing in the background, like I do a podcast, so.

[00:12:37] **Ben:** I can dig it. All right, Tim, what do you take us home when you got

## [00:12:40] Tim's Triumph

[00:12:40] **Tim:** Well, I'm going to make this four of a kind,

[00:12:43] **Ben:** oh, yes.

[00:12:44] **Carol:** go on the Vegas baby.

[00:12:45] **Tim:** because I also have a triumph

[00:12:47] **Tim:** . So I had four days in a row. Just very focused coding, which for me lately has been very rare because I wear so many different hats. I've been doing a lot more on the strategic side and the management side lately, just getting prepared for next year, but it's like I had four straight days where all I did was head down, lost track of time, got in the flow and just reminds me why I'm in this job just made me happy.

[00:13:11] **Tim:** so that's great. and separately from work, I've actually read a physical book. I actually read a physical book for the first time in a long time, actually bought a book. I listened to it first and it was so good. I had to actually buy it. I posted in our Working code discord, but that's called a how to think like a Roman emperor about Marcus Aurelius, who was a stoic philosopher and also the emperor of Rome.

[00:13:36] **Tim:** So good. it's a combination of history of learning about philosophy of stoicism and a bit of psychological, the guy who wrote it is a, he's a psychologist who teaches cognitive behavioral therapy. And he just kind of shows how stoicism and cognitive behavioral theory, which came out of stoicism actually is they're very similar and just kind of how to think better.

[00:14:03] **Tim:** So, yeah.

[00:14:03] **Ben:** I'm fascinated by stoicism. Tim Ferris, I believe is a big stoic fan, for our work, with.

[00:14:09] **Tim:** Yeah. Now I'm in the more I read it, the more I realize it's like there's, it just puts into words, sort of the things I've kind of already known and tried to apply in my life. but it just sort of gives you a methodology of how to progress even better. So just a really great book.

[00:14:23] **Adam:** All right. Glad to hear you read something interesting. cool.

## [00:14:26] Patron's Replatforming Requirements

[00:14:26] **Adam:** So let's, transition into our discussion for today. So as I mentioned earlier, we did kind of discuss this topic back on episode 25. what was that called? Breaking up with your stacks? Something like that. and I went back and looked at the notes from that, and it seems like we mostly discussed sort of like meta aspects of it.

[00:14:41] **Adam:** Right. Why would you want to, or why would you not want to and

[00:14:44] **Adam:** things to consider.

[00:14:45] **Carol:** Like pros and cons.

[00:14:47] **Adam:** but one thing we didn't discuss in that episode, if I remember correctly is what we would pick and why. And, the topic came up in our Discord this morning. one of our patrons asked if, he said, I have this set of constraints and we are going to be replatforming because we're not going to stay where we are.

[00:15:05] **Adam:** and X, Y, and Z requirements. And what would you pick if you were in his shoes? So we thought that was a good topic to consider.

[00:15:14] **Ben:** So basically he's transitioning away from what he called a traditionally coded CFML apps. So that was in quotes and what he meant by that is like garbage code, write spaghetti code and lots of bad practices. and, he said it's, mostly a typical web app.

[00:15:29] **Adam:** Right. It's got a database and it's kind of your typical crud thing. but there are. Interested in replacing the database. And, is business facing not public facing, a good amount of code, but not an overwhelming amount. He said it's about 50,000 lines of code. they are not averse to learning a completely new language.

[00:15:46] **Adam:** part of their mandate is to if the deemed worthy to do the training on a new programming language,

[00:15:53] **Adam:** they want something statically typed. I think it was not in his original post, but he definitely said, for them JavaScript is off the tables who then they are not considering like node or TypeScript.

[00:16:03] **Tim:** it's mostly rest based web services.

[00:16:06] **Adam:** Yeah. but given those concerns. Statically typed, you have a good amount of code, but it's accomplishable. Right? You could maybe get 50,000 lines of codes done in what?

[00:16:15] **Adam:** Six months

[00:16:16] **Tim:** Oh, and Ben would like this one. He wants community accepted quality linting standards.

[00:16:21] **Ben:** No.

[00:16:23] **Carol:** Oh,

[00:16:24] **Ben:** mean, what's even the.

[00:16:27] **Tim:** And being able to hire developers is important too.

[00:16:30] **Adam:** oh yeah, that was a good one. Yeah.

[00:16:32] **Carol:** Well, I think that's key for anyone Right. now. Who's thinking of a technology switch is what does the community support for it? And can I find people to ride it because why would you go to a language that you can't find people to support? That doesn't make sense. So that's

[00:16:46] **Carol:** an easy check-off

[00:16:48] **Adam:** eh, well, it's an important thing. I don't know that it's going to be necessarily easy to determine. Right. So when I think of, if I need to find, I need to consider all possible language switches. To make sure it's going to be easy to hire somebody. The thing that, to me says easy to hire is going to be a rapidly growing community, not just growing but rapidly growing because there's a huge shortage of developers, qualified developers for the number of jobs that are available.

[00:17:15] **Adam:** And the number of jobs is growing too

[00:17:17] **Carol:** Yeah. And I feel like he, he shot himself in the foot a little bit by saying no node. Like that's a

[00:17:23] **Adam:** well. I mean, he said that that's not his, it's not his preference. he's not a huge fan of JavaScript, but that's coming from above. So they don't, he doesn't have a choice. Node is already off the

[00:17:32] **Carol:** Uh, so they'd killed it for him. It's not that he's shooting it down. Is that he's been told? No.

[00:17:37] **Adam:** Right.

## [00:17:39] Choosing A Language

[00:17:39] **Ben:** I don't understand though, because if you look at an existing application, that's old, the people who wrote that crap code were probably people who were fairly new to the language in which it was written.

[00:17:51] **Ben:** So part of me always feels like if you're going to jump into a rapidly growing community, it's going to be with a bunch of people who are very new to the language in which the stuff is being written.

[00:18:02] **Ben:** Like aren't, they just destined to write the same crap code as well.

[00:18:05] **Carol:** Can

[00:18:05] **Carol:** easily

[00:18:06] **Adam:** Well, so you're not wrong, but this particular patron, I don't know his exact job title, but I

[00:18:11] **Adam:** know,

[00:18:12] **Ben:** love you the most.

[00:18:13] **Adam:** like I said, I don't know his exact job title, but I do know that he is, let's just approximate it let's just call him an agile coach. Right? Like his job is not so much to be an engineer as it is to be like a mentor, like to whip people into shape.

[00:18:29] **Adam:** And he's got a lot of experience and strong preferences around clean code and refactoring and testing. And I certainly know it. He's not scared to crack the whip. Try to force people to get in line. And as long as he's got the, management backing to tell the rest of the team that they have to listen to him,then I think that it could be possible.

[00:18:52] **Adam:** Right. he gets testing and refactoring and clean code and all these things, and yes, absolutely. The code that you write, the code that I've been writing all day today in my news fel project, I'm sure as garbage, but I'm coming at it from the perspective of, I know it's garbage, but I have to get something on the page that works and then I'll make it better.

[00:19:12] **Adam:** Right. We're like refactor it.

[00:19:14] **Adam:** So

[00:19:14] **Carol:** got to start somewhere, right?

[00:19:16] **Ben:** Yeah. Yeah. And to be clear, I'm not saying that you should only choose languages in which you can write perfect code. I'm just saying that so if I can go out on a small tangent for a second, so at the top of the show, I mentioned that I'm working on some of my blogging infrastructure and the code that runs my blog currently is ColdFusion code, which is what I'm still writing today, but it's terrible.

[00:19:37] **Ben:** ColdFusion code. Like it's just enough to work and it's terrible. And I spent a couple hours this morning, deleting loads of components, like literally, probably two dozen, maybe more components, taking some of them, ripping them apart, refactoring them, moving them into other components, all without linting or a unit test, not a single unit test, by the way.

[00:19:57] **Ben:** and, you move it into something that's better and more modernized and reads well, and is more maintainable, at least that's the hope,

[00:20:04] **Carol:** So I guess it's okay. When stuff is garbage, as long as you just continue to evolve it over time. I think where garbage code really is demonized is when it's garbage code and then it's left alone

[00:20:16] **Adam:** Exactly

[00:20:17] **Adam:** it works is step one of like nine. And so often step one is like the finish line.

[00:20:23] **Ben:** So I don't know. I mean, just to say like, I don't have a lot of experience with different languages. I've basically been in ColdFusion and JavaScript as my two workhorses for the last, 15, 20 years. So to me, I can't imagine being as productive or as comfortable in anything else. So the idea of replatforming to a totally different language seems like it would be a huge setback. I'm also,

[00:20:50] **Ben:** I'm not a good mentor and I don't have a lot of candor in the way that I communicate with people. And I tend not to be very strong in my, forcing ideas onto other people. So I think,

[00:21:01] **Tim:** Pedro doesn't have that problem.

[00:21:03] **Ben:** right. and I think that's a huge asset when it comes to something of this magnitude where you can switch horses and lay down the law.

[00:21:12] **Ben:** I, I couldn't lay down the law. I'm just, my I'm just not wired.

[00:21:16] **Tim:** Yeah. And I get that. I mean, looking at what he said, what immediately came to my mind was so second day from two angles here, based off what he said, and then I can also take, I will internalize it and say what I would do. So based off what he said, I mean, you think about Python. Python is not a new language.

[00:21:36] **Tim:** It's been around since the eighties, but it is currently the most popular language on the web. And there's, it's a huge community. And there is what is a Django that they use for, to build API APIs. So there's already a framework that is built to help you basically build API APIs rather quickly. And so you shouldn't be able to have problems, hiring people that know Python.

[00:21:58] **Tim:** it's got a good community support. It's got, linting as well.

[00:22:02] **Adam:** Idiomatic Python.

[00:22:04] **Tim:** yeah, and it'sit's a very expressive language, right. As well. it's not, super tours. So I mean that's, if you had to change, that's what I would do personally though. It's like, I think the problem sometimes, you build a rest API from scratch and you don't really know what you're doing the rest of the beginning.

[00:22:23] **Tim:** And I would do exactly what I did I'm using, CFML on Lucy and using taffy because it makes building a rest API soup. It takes all the rest stuff away. And I don't have to worry about any of that stuff. So

[00:22:35] **Carol:** makes total sense. Yeah, it

[00:22:36] **Tim:** Yeah.

[00:22:38] **Tim:** I mean, yeah, I don't, I look at my code and I'm proud of that code that I've done there.

[00:22:42] **Tim:** So I was like, I don't have a problem with it. I wouldn't want to move away from that, but it's like if you're being forced to move away for whatever reasons, I would say Python and Django.

[00:22:52] **Adam:** If you, I think if you, so Python and Django doesn't fit the strict criteria. he threw out there, right? It's not statically typed. If I'm remember correctly, it's a dynamic. and, but I think it probably meets all of the other requirements. like you said, there is a huge community. I think the whole Python two versus three thing is interesting, but we're probably far enough past it now that it's not as big of a deal as it used to be.

[00:23:17] **Adam:** I know someone throughout, dot net C sharp, but.

[00:23:20] **Tim:** Yeah.and the it's not dynamic, but it only runs a windows, which was a deal killer for him.

[00:23:27] **Adam:** Oh yeah. So I want to get back to Ben at some point we don't have to do it immediately, but I think Ben, your, hesitance to answer. To dig in, I think is an interesting possibility, right? So we're, this is all hypothetical anyway. Right? So if Adobe

[00:23:42] **Adam:** called you tomorrow and said, Adobe and Lucy both called you tomorrow and said, we're shutting down no more.

[00:23:49] **Adam:** and it's going to stop working in six months, after you were done crying, what would you start investigating next? Right. So you said you don't have a whole lot of experience in other things to make us suggestion, but my question for you is surely you've heard of other programming languages.

[00:24:02] **Adam:** what has most Mindshare for you? what has peaked your interest that you would look into first or the most.

[00:24:08] **Tim:** What would be your criteria for deciding.

[00:24:12] **Ben:** Well, so I love JavaScript. So I would definitely look into something in the node ecosystem probably, or the Deno ecosystem. that's also because I love TypeScript and Deno is I think natively TypeScript. Right? my, my big issue is that I'm also a huge angular fan and it seems like a lot of the JavaScript server side solutions focus primarily on react these days.

[00:24:36] **Ben:** I think view has one. I think angular sorta has one, but, react seems to be the one that's getting the most focus in terms of robustness of, uh, of functionality. so it can do it. I mean, so, yeah, so I would definitely be pretty comfortable looking into anything within the JavaScript world, beyond.

[00:24:55] **Ben:** I Ruby seems fascinating to me, it's it? I know it's not in the heyday that it was probably 10 years ago. but it's still, I think, a huge community. And I think a large number of things continue to run on Ruby on rails. I've looked at the Ruby syntax a little bit and it's a little loosey goosey for me.

[00:25:13] **Ben:** it doesn't seem to have a lot of the CIN taxi stuff I like in, in some of the other languages. but that's not speaking from experience here, but I, I have no problem jumping into a language that's been around for a really long time, to Tim's point, Python's been around for 30 years and it's hugely popular and it's not going anywhere.

[00:25:31] **Ben:** I know Ruby on rails is not the Belle of the ball. It's also, a huge productivity language and the Ruby itself was designed for developer happiness, I believe was the motto. So, I love the idea of developer happiness, because that's so much of what CFML ColdFusion is all about.

[00:25:49] **Adam:** Yeah, I experimented with Ruby and rails a few years back and I agree. I think that, from a language design perspective, I really liked Ruby itself. I didn't really jive with rails. and again, I was a newbie at the whole thing, so I'm sure I did it poorly, but, it just didn't work out for me. that's an interesting perspective though, one thing I didn't hear from you is any interest in say rust or NGO or any of these other sort of newer,

[00:26:16] **Ben:** I'll tell you, I've looked at go. I know people love go. I look at it and I cannot stand it. it

[00:26:22] **Ben:** looks, it is. We use it at work a lot.

[00:26:25] **Carol:** talked about this, Adam, where have you been

[00:26:27] **Carol:** that? Yeah.

[00:26:30] **Adam:** I'm over here running the show.

[00:26:32] **Carol:** Yeah.

[00:26:32] **Ben:** I, this is a big philosophical thing for language design, I guess. I'm a huge fan of throwing errors when you give me something and it's not the thing I need, I will throw an error and I can do it in ColdFusion, and I can do it in JavaScript, go with like vehemently against the idea of ever throwing an error, panicking, everything returns, error, objects, or non error objects.

[00:26:54] **Ben:** And then you have like half of the code that you look at is littered with these. If an error object came back, then deal with it, which usually just means like returning another error object and then everything else has to check. I mean, it's basically the antithesis. I feel like of so much of what uncle Bob Martin was saying in clean code about separating concerns and readability.

[00:27:18] **Ben:** And it's just,

[00:27:19] **Adam:** you said you had some interest in node. Have you done old school? Like we call it air back, like error, first

[00:27:25] **Ben:** Yeah.

[00:27:25] **Ben:** yeah. I, call back hell and I've played around with express, the pre promises. Now the promises are native to the language and async await and definitely stuff looks way nicer now from a readability standpoint. I mean, my, ColdFusion code and my TypeScript code more or less look exactly the same these

[00:27:49] **Carol:** same,

[00:27:49] **Ben:** really like.

[00:27:50] **Carol:** same exact same here. I was realizing that the other day I was like, wow, you really don't see a big difference between how the two are written because just how it's just how right.

[00:27:59] **Ben:** So, yeah, I think I'd be pretty comfortable in a node situation.

[00:28:03] **Adam:** Right. Carol, did you answer like

[00:28:06] **Adam:** the whole hypothetical situation?

[00:28:08] **Carol:** yeah, it's hard for me to think that through, because I write in the TypeScript project and I can't see going off that. I mean, I have a

[00:28:15] **Carol:** legacy after that support as Well, yeah. But I'm happy with what I with where I am. So it's hard to think of moving off of something that's new and hot still, that has a lot of community support and people love and it's working

[00:28:27] **Carol:** well.

[00:28:27] **Carol:** So

[00:28:27] **Carol:** I'm having a hard time thinking what I would move this to.

[00:28:30] **Adam:** well, I mean, I think that the place that you are probably satisfies most of his requirements, except the one that it can't be JavaScript.

[00:28:37] **Adam:** Right.

[00:28:38] **Adam:** It doesn't have a enforced separation between model view and controller, but, other than that, I think it's pretty much checks all the boxes.

[00:28:46] **Carol:** enforced that ourselves,

[00:28:48] **Adam:** yeah. well then I guess that leaves me.

[00:28:50] **Adam:** I was the one that threw out C sharp.net and the discussion in discord. Not because I particularly like it. I do have some experience with it and it was fine. But I think that it suffers from the same thing that I don't like about Java, which is that it just gets really verbose really fast. At least when I was doing it 10 plus years ago, this was like maybe two or three years before they introduced like, I think they call it asp.net MVC or.net NBC or whatever it is.

[00:29:18] **Ben:** Yeah,

[00:29:19] **Tim:** Razor pages.

[00:29:20] **Adam:** and this was like, they called it post-bacc was the,

[00:29:23] **Adam:** paradigm

[00:29:24] **Ben:** yeah, yeah. It would pose

[00:29:25] **Ben:** back the

[00:29:25] **Ben:** entire state of the page.

[00:29:27] **Ben:** That

[00:29:27] **Adam:** Yeah.

[00:29:28] **Adam:** Yeah.

[00:29:29] **Ben:** Yeah.

[00:29:29] **Ben:** Yeah.

[00:29:30] **Adam:** Yeah. So it wasn't a huge fan. I did like the C-sharp again, going back to like language design C sharp as a language I liked, I thought developer happiness, writing C sharp code itself was good, but the dotnet framework and using that to get it onto the web was not my, metaphor of choice.

## [00:29:46] Updating Old Code

[00:29:46] **Ben:** here's something that, so I, as I was mentioning earlier, I spent a couple hours this morning refactoring my blog platform, which, this is just step one in a really long journey. And it was really interesting to see the style of code that I was attempting to. 10 years ago versus the code that I write today, because the code that I was trying to write, and I say trying in heavy air quotes because it was garbage.

[00:30:11] **Ben:** but it was very complicated. It was lots of components and trying to create abstractions and encapsulate things for

[00:30:21] **Adam:** Architecture, astronaut.

[00:30:22] **Ben:** it was so high in the atmosphere, architecture, I was coming off of reading headfirst, Java, and the gang of four book on design patterns. And I was trying to learn object oriented programming and just, I was trying to throw everything that I thought was clever and elegant at the page to see what would work.

[00:30:42] **Ben:** And it was so garbage. It was so, so garbage. and I look at the code that I write today and it's significantly more. I mean, it's almost like I've come full circle. Right? Where, when I first got into programming, it was simple queries and rendering interpolated data into templates. And then I went crazy and tried to make it complicated and solve a lot of problems that I wasn't actually having.

[00:31:06] **Ben:** And now I've pulled a 180 and I'm really back to simple queries that are just encapsulated a little bit nicer and some separation of concerns, and then taking that data and jamming it into a template. And it's just, it's really interesting to see this sort of a return to simplicity. And it makes me think of, rich hickies.

[00:31:27] **Ben:** He's done a couple of presentations where he talks about the languages. Language design has all these beautiful data structures and data is really easy to work with. Objects are hard to work with. Data is really simple and that you should embrace that and lean into it. And I feel like I've really either like case in point, There was one component that I deleted this morning.

[00:31:48] **Ben:** it was something like an array iterator. And I thought everything had to have this iterator interface that it adhere to. And then you could just next something until the next return to normal or, like it would have a has next. And then you could call next. I mean, clearly I had been reading a lot of stuff about Java and like, now you look at the language and you could just for in over an array, like no ceremony about it whatsoever.

[00:32:12] **Ben:** And I just want to return to that as much as humanly possible. So when I think about these languages, these frameworks, these language paradigms words, a lot of framework stuff built into it. At this point, I feel like, no, I want to just go back to the regular, just super easy. A request comes in. It gets routed to something that's something makes some database calls and renders it. I don't know. maybe it's childish, but, I'm just craving. That's returned to simply.

[00:32:39] **Tim:** Ah,

[00:32:41] **Carol:** Back in my day, children.

[00:32:44] **Ben:** I craved the simplicity on the server side stuff, but I'm still leaning into the complexity on the client's side,like, I, things like spelt,

[00:32:54] **Adam:** Your angular.

[00:32:55] **Ben:** yeah, like I'm angular, you're going to have this giant ass, compilation step that does a whole bunch of things.

[00:33:01] **Ben:** Like I'm okay with that.

[00:33:02] **Carol:** Yeah. We just know it's there.

[00:33:04] **Ben:** yeah. for what it does. I'm still okay. Writing just a vanilla JavaScript file. If I just need a simple page that does a simple thing. Right. And that's something that I think I'd like to look into spelled for.

[00:33:14] **Carol:** I think most of us do that, just put something simple up just to make it do the little thing, not try adding super complex to it, but you were mentioning Adam about the.net projects. Right? So what I liked about writing C-sharp was that it had the model view controller split out, right?

[00:33:31] **Carol:** So, I mean, it's required. We had to do it that way, but what it didn't like is when I wrote it, we also use knockout. And I don't know if you've ever used knockout before, but knockout is a model of you view controller itself. So then everything had this whole other layer of Java script type model, view controller that had to be laid on top of it.

[00:33:49] **Carol:** And I'm like, why do I have so many models? And so many views like this does not make sense anymore. So they just complicated it by adding this extra layer on top of it. And I was like, no,

[00:33:59] **Adam:** wasn't it like MVVM

[00:34:02] **Carol:** Yeah. MVVM

[00:34:04] **Carol:** yep.

[00:34:05] **Adam:** view and view

[00:34:06] **Carol:** View model Yep. Milo view and view model. Yeah,

[00:34:09] **Carol:** On top of a model view, controller projects are like already set up and I'm like, what model am I in? Again?

[00:34:16] **Carol:** Like I'm on

[00:34:17] **Carol:** this model to get to that model. And I Was like, oh man, to get to that, controller, I'm like done. I quit. I'm like, I'm going back to CSU guys.

[00:34:26] **Carol:** This is stupid.

[00:34:27] **Tim:** , was, that was that called Leonardo DiCaprio from this model of that model?

[00:34:33] **Carol:** Yes. I had to find my, what was the thing he spun around in the movie Yeah. Yeah. Yeah. He, his totem.

[00:34:39] **Carol:** had to go find it where it was at as this thrill one or not. So, yeah, it's awful. You can like mess yourself up So bad when you start adding layers top the layers.

## [00:34:48] Considering Your Team And Project

[00:34:48] **Adam:** So I guess I had another thought sort of meta about this, the original question here. Like what would you do? And I think that we kind of discussed this in the past it's not just the best tool for the job, but it's the best tool for the project and the people on the team and the current time and, a couple of other factors. And I think that has to factor into, right. Like, if you have. a hundred junior developers and two senior developers, then you're going to have a whole lot harder time learning a more complicated language. If you're choosing to pick something that none of you know yet, then if you pick something that, at least you have some familiarity with, or if your team is mostly seniors and not very many juniors, then,there's a lot of, context is going to come into play here. So I wanted to throw that out there and that sort of separately, my team is kind of doing this, like this whole replatforming thing we're on, I think probably a much longer time horizon than, this original question. We don't have a deadline. So we're basically, our deadline is try to slip it in little by little, as much as possible without interrupting productivity so that we can still be profitable, gets, get stuff done that our customers need us to get done because they don't care.

[00:35:55] **Adam:** Whether we're on CFML or rust or TypeScript. Right. and so all they care is that the site is online and it does what it needs to do and the accounting stuff works out. so that's where we're at, is like, we are, long-term going to be abandoning, CFML currently pointing ourselves toward JavaScript of some form because it is the lowest common denominator of the web.

[00:36:17] **Adam:** Right. it's pretty much the only choice for the moment for the front end. And so we're all pretty well versed in it for the front end. We might as well use it for the backend too. It's just reusing those skills and less context switching. we are interested in TypeScript. We don't have any, significant experience with it on our team, but we all agree.

[00:36:35] **Adam:** It could provide some benefit and Yeah. So, I mean, that's kinda where we're at. And I think that the other thing that draws us to it is just the sheer volume of the community. Like it's huge, almost uncountable, probably uncountable.

[00:36:51] **Tim:** Which community?

[00:36:52] **Adam:** JavaScript and TypeScript to a lesser extent, but I think that it feels a bit like a vocal minority situation.

[00:36:59] **Adam:** but I do feel like content creators, the people that are, the most followed people on Twitter,the biggest projects that you see on GitHub, all the libraries are converting to TypeScript or worst heard in TypeScript. And that, vanilla JavaScript is falling out of favor in that crowd.

[00:37:17] **Adam:** But I think that in terms of like sheer lines of code, probably JavaScript outweighs TypeScript, I would guess three or four or five.

[00:37:27] **Carol:** Yeah, that's probably right. I like to use that whenever I'm adding new API APIs, I'm adding new packages, almost everything has samples and has references written already in TypeScript. So I, if I get lost on something or I get confused or I'm having a hard time, there's usually projects out there that already have it because the samples And like the documentation have a TypeScript version of it.

[00:37:48] **Carol:** So

[00:37:49] **Carol:** easy

[00:37:49] **Carol:** Chidi

[00:37:50] **Carol:** way to

[00:37:50] **Carol:** go find things.

[00:37:52] **Adam:** the other thing that I'm really, trying to optimize for is like the least number of pieces that I have to integrate myself. Right. So, just say you need a JavaScript project and you want a certain UI library and you're, you want maybe to use tailwind for that, and you want a certain testing thing and you want to use TypeScript and you want this and that.

[00:38:12] **Adam:** You gotta, a lot of times you have to wire all those things together. And sometimes there's. okay, well, if you want to use our framework, what TypeScript here's, how you do that. But then it doesn't, when you start to match too many things together, there tends to be places where it sort of falls apart.

[00:38:25] **Adam:** And that can be really frustrating. So I'm trying to optimize for as little of that as possible, pick two or three things and everything else just kind of gets rolled in rolled by hand or as much as possible stay separate, right? Like our testing lives off to the side. It's not integrated with anything.

[00:38:40] **Ben:** if one is going to go through the act of replatforming, could you not think of sticking with the same language, but rebuilding the same thing using modern techniques essentially as replatforming?

[00:38:52] **Adam:** yes, you could think of that as replatforming, but I think that it would be totally valid for any team to decide. We don't think that this platform has a future, whether in general or with us, we have reasons that we just don't want to be with that platform. And that's a totally valid reason to switch, right?

[00:39:10] **Adam:** Like if literally a hundred percent of your team hates working on it, on that

[00:39:15] **Adam:** platform.

[00:39:15] **Carol:** problem.

[00:39:17] **Adam:** And that's a valid reason to find something else.

[00:39:19] **Carol:** Or the language is actually not being supported anymore. Like that would be a

[00:39:23] **Ben:** yeah, yeah, yeah.

## [00:39:24] Considering Hiring

[00:39:24] **Ben:** That's fair.

[00:39:25] **Adam:** hiring

[00:39:26] **Carol:** Yeah. hiring is

[00:39:27] **Carol:** an issue.

[00:39:28] **Adam:** a really good reason to.

[00:39:30] **Ben:** Well, let me ask for some clarity on that, because from everything that I've heard on various podcasts, it seems like hiring is just hard period everywhere. I mean, I don't do any hiring myself personally, but we use a lot of Golang at work. And part of the reason that we switched a lot of services over to Golang was because it was going to be so much easier to hire people for this new hot language.

[00:39:53] **Ben:** And I'm pretty sure in the Golang world, a lot of people are having trouble finding go leg programmers.

[00:39:58] **Adam:** Yeah, I can't speak to Golang.

[00:40:00] **Ben:** yeah. I mean, I, but I think tech is so hot. It's so hot right now. think everybody's having trouble finding people.

[00:40:08] **Carol:** So we've had two open recs on our team for over a year and it's taken over a year to find people qualified, to do the job because senior engineers aren't leaving their CF jobs. Those companies, once they get the offer their counter offering, because they know they can't replace that person. So it is really hard to find a senior CF engineer that can leave their job because when they're like, Oh, we're going to leave for money.

[00:40:36] **Carol:** Their company's like, oh, whoa, we'll give you more. So just stay here where you already know what the devil in the closet looks like as opposed to opening up a whole new CS can of worms, you know,

[00:40:46] **Ben:** Yeah,

[00:40:47] **Tim:** And plus it's just, I mean, it's hard to developers period right now, right.

[00:40:51] **Adam:** I, yeah,

[00:40:52] **Tim:** is outstripping the supply.

[00:40:54] **Adam:** the only hiring I've done any time recently, we were specifically looking for CF developers and we did get a reasonable number of, applications, but I gotta believe that if I went onto your average JavaScript Discord or slack and said, Hey, I'm hiring, submit your resumes here. I would probably have gotten easily 10 times as many people to say.

[00:41:19] **Tim:** Hmm.

[00:41:19] **Carol:** Agree.

[00:41:20] **Adam:** I

[00:41:20] **Ben:** Yeah, probably.

[00:41:21] **Tim:** I'm trying to recruit Scala engineers and there they're like rare.

[00:41:25] **Adam:** we'll see

[00:41:25] **Adam:** that came up in the Discord this morning. Another person on our Discord said that, there was some discussion of Kotlin and Scala and a couple of other, want to say Elm, maybe

[00:41:35] **Tim:** Yeah.

[00:41:36] **Adam:** OCaml.

[00:41:37] **Tim:** I'm going to find too many Kotlin engineers.

[00:41:39] **Adam:** Yeah.

[00:41:40] **Tim:** So what I'm looking for scholar, I'm just like, do you

[00:41:42] **Tim:** know. Yeah. Funky

[00:41:44] **Carol:** It's functional

[00:41:45] **Carol:** right?

[00:41:45] **Tim:** something similar, right? Yeah. Yeah. Some, yeah. Like, any sort of, not procedural language, just, yeah. Just anything, not procedural, like language buying.

[00:41:55] **Tim:** Come on.

[00:41:57] **Adam:** I'll take anybody.

[00:41:58] **Tim:** I'll take anybody.

[00:41:59] **Adam:** I mean, I like to think of it as like fishing, right? So when you're trying to hire somebody you're fishing it's not a perfect metaphor, but you can fish in a puddle or you can fish in. You know, the great lakes, right? which one are you going to pick, which is going to have more fish.

[00:42:13] **Adam:** So

[00:42:13] **Tim:** Yeah. And this sort of the thing I was looking to, why I recommend Python is because in America, our patron is not necessarily in America. I think he's in England, but over here, the Mo one of the most popular languages to learn in college is Python right now, Python and R, which is more statistical.

[00:42:30] **Adam:** R it's a math programming thing.

[00:42:32] **Tim:** It's a math program. It's

[00:42:33] **Tim:** more statistical and graphics kind of thing. But I mean, they're two of the most popular languages right now in colleges. and so if you have an existing community that's been around for a while and you have new people coming in, that's why I recommend it. Even though it's not statically typed, which I know he was super hot on, but it's like, I'd be like, all right, right now that seems to be the thing to two, three years from now.

[00:42:54] **Tim:** It could be something completely different. these things go on trends. Like Ruby was super hot 10 years ago. so you just, it is a gamble, no matter what you do, there's always going to be a pro or con, no matter which one you choose.

[00:43:06] **Carol:** It's a lie. The research.

## [00:43:08] Making The Decision

[00:43:08] **Adam:** something we haven't talked about is, how would you finalize that decision? And I think that for me, the obvious choice is to pick like maybe your top two and do some experimentation, right? Like this app that I'm playing with for . what I did. And what our team did was we took a day and picked like the most complicated screen on our app and some other things that aren't particular to that screen, but, are technically challenging.

[00:43:37] **Adam:** And we wrote all of this down in like a list of requirements. It's like, okay, go build something that does this. as we're kind of rebuilding that screen, plus a couple of other pages to satisfy all those different requirements, just as like a proof of concept, like, okay, if we can get this done, then we can get pretty much anything that we would want to do done.

[00:43:53] **Adam:** And so, and it gives you that experience. And then you come back with a taste in your mouth, there's a positive taste or a negative taste, right? you enjoy the process or you didn't, and you can compare them to each other. I think that would be really useful for anybody considering, switching languages.

[00:44:10] **Carol:** Yeah.

[00:44:10] **Carol:** we brought up a lot of this on episode 25. So he talked about a lot of the, how tos.

[00:44:16] **Tim:** I think you've had a little money to spend how I would experiment with it is to have, like you said, my team build it in a language, but then also hire a, outsource, like to a consultant or someone who's very knowledgeable and say, given the use case, you build something like this and then compare how different the two solutions are and why.

[00:44:36] **Tim:** Right. Because obviously if I'm just new to a language, I'm going to probably make a lot of rookie mistakes or design decisions that probably shouldn't have. And then if I see afterward, I see how someone else solved the exact same problem. could probably give me a better cause.

[00:44:51] **Tim:** Cause you might come to wrong decision based off the fact that you just didn't know what you're doing.

[00:44:54] **Adam:** Yeah.

[00:44:55] **Ben:** so I think about programming paradigms and essentially thinking about just the life cycle of a request, not even talking about distributed systems and message cues and inventing and that kind of stuff, but essentially a request comes into the server. It has to be handled by something that's something gathers data.

[00:45:13] **Ben:** And then that's something that also renders a response to the client and our different languages. So radically different. And in how it does those,

[00:45:22] **Adam:** I guess what I'm saying is. I think there are different languages have somewhat different parallel. There's like different camps of how this has done and all the languages in one camp. is it really going to matter? Is it having the language gonna make or break the success of the product

[00:45:40] **Ben:** if essentially that language is doing the same thing?

[00:45:43] **Carol:** it's kind of like what Adam said, my customer doesn't care how I write it. They care how they see it. Right. They see, they just want to see the number, their bill at the end of the month. And they want to see that it came out on the screen correctly. They don't care how it got there. So I'm with you.

[00:45:58] **Carol:** Like if it's working good for you, use that language.

[00:46:02] **Tim:** I mean, so the language syntax might not be completely different. I mean, I've, if you're writing in the eczema script type language, they all look extremely similar. Perhaps how you build the application and architected can be very different depending on language, my opinion,

[00:46:19] **Tim:**

[00:46:19] **Adam:** was, it has been decided we're

[00:46:22] **Adam:** moving. Right. And so,

[00:46:24] **Ben:** right, right.

[00:46:25] **Adam:** and from there go. Right.

[00:46:27] **Ben:** And what phase does he switch over to Postgres?

[00:46:32] **Tim:** Now, just

[00:46:33] **Carol:** said no database changes.

[00:46:35] **Tim:** said no database change, but he should reconsider that

[00:46:39] **Carol:** Cockroach

[00:46:39] **Carol:** DB,

[00:46:40] **Tim:** sure.

[00:46:40] **Tim:** Yep.

[00:46:41] **Ben:** I guess the only other thought would be to change only one thing at a time. I don't necessarily know how well you can do that in a replatforming, but I don't try to bring too many things into the replatforming at one time. Like, just do the one thing that you think is going to

[00:46:59] **Tim:** Yeah. And I think another one of her patrons on there, he recommended Kotlin for the very reason that it's on JVM as well. So you can possibly run them side by side the exact same time, which I

[00:47:11] **Tim:** get, but I don't know how many Kotlin people are

[00:47:14] **Tim:** gonna find out

[00:47:15] **Tim:** there.

[00:47:15] **Carol:** never even heard of it, so,

[00:47:17] **Tim:** had to Google it after he recommended it.

[00:47:19] **Tim:** So,

[00:47:20] **Carol:** And that feels So,

[00:47:21] **Carol:** bad now.

[00:47:21] **Tim:** but I mean, knock, I know every way language out there, so that guys a lot smarter than me.

## [00:47:27] Patreon

[00:47:27] **Adam:** This episode of Working Code is brought to you by Hansel. He's so hot right now,

[00:47:32] **Carol:** Hey, I like it. Like.

[00:47:34] **Adam:** and listeners like you, feel like what we're doing here. You might want to consider supporting us on Patreon. You could do that at patreon.com/WorkingCodePod, Pedro, on, if you don't know is just a place where you can go to donate money to the things that you love to help them continue to exist. you can support us for as little as $4 a month, and all of our patrons get our after show and early access to new episodes.

[00:47:55] **Adam:** As soon as they're ready, typically lately, it's been at least a week. of course we need to top think our top patrons, Mani and Peter. So thank you guys so much for your support.

## [00:48:03] Thanks For Listening!

[00:48:03] **Adam:** if patronizing podcast, isn't your thing. No worries. We appreciate that. You take the time to listen. if you enjoyed this episode, you should post about it on your social media, and it would also really help us out.

[00:48:13] **Adam:** If you left us a rating and a review on apple podcasts, please send us your questions and show topics on Twitter or Instagram @WorkingCodePod. Or you can leave us a message at 512-253-2633 that's 512-253-CODE. Or you can join our Discord now public and share your ideas with us there. and, yeah, I guess that's it.

[00:48:31] **Adam:** We'll catch you next week and until then.

[00:48:33] **Tim:** Remember your heart matters, even if you're dynamically typed

## [00:48:40] Bloopers

[00:48:40] **Adam:** I had a thought you guys,how we were discussing, like, what do we want to do for our one year anniversary show? I came up with an idea. I got an idea.

[00:49:07] **Carol:** All right.

[00:49:08] **Adam:** we're going to pivot and we're going to become an unboxing podcast.

[00:49:17] **Carol:** No,

[00:49:18] **Adam:** Carol's just like,

[00:49:20] **Tim:** Just going to take apart ColdBox stuff.

[00:49:22] **Carol:** no,

[00:49:23] **Adam:** no, no, just going to buy stuff and open it on here. And then I get it to do it as a tax. Write off.

[00:49:28] **Tim:** There you

[00:49:28] **Carol:** will do it. If people send me boxes for free.
