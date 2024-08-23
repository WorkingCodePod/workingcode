---
title: "192: The Best of Code and The Worst of Code"
description: "In this episode, the hosts discuss their experiences with different codebases, from the best they've worked on to the worst."
date: 2024-08-21
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/192-the-best-of-code-and-the-worst-of-code/id1544142288?i=1000666103762"></iframe>

In this episode, the hosts discuss their experiences with different codebases, from the best they've worked on to the worst. They explore the complexities of evolving and maintaining legacy code, the challenges of debugging, and the importance of clean architecture. Key points include the pain of working with ORMs, and the impact of early design decisions on long-term project health. They also touch on reactivity concerns in modern frameworks and share personal anecdotes of both successful and problematic coding practices.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/192-the-best-of-code-and-the-worst-of-code.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Ben:** And sometimes it gives you the error that's just like, It didn't work and the injector failed. And you're like, well, why did the injector fail? And then, I mean, you can continue on with your story, but it's in my case, at least it's a lot of just commenting out entire files.

[00:00:13] **Carol:** you figure it out, right? Yeah. I remember those days. Split

[00:00:17] **Adam:** many times in my life have I done a binary search of my code by like, just comment out half the file? Okay. The error is not in that half. It's got to be in the other half. Now let me take that half and comment out half of

[00:00:26] **Carol:** it in half.

[00:00:27] **Adam:** Yep,

[00:00:27] **Ben:** it's like a manually bisecting.

[00:00:31] **Tim:** reasoning

[00:00:52] **Adam:** Okay. Here we go. It is show number 192. And on today's show, we're going to talk about a tale of two code bases. It was the best of code and it was the worst of code.but first as usual, we'll start with our triumphs and fails. We've got the whole crew here

[00:01:03] **Ben:** Yo, yo,

[00:01:04] **Tim:** Yay. Hello.

[00:01:06] **Adam:** and Ben, it looks like it is your turn to go first, my friend.

## [00:01:09] Ben's Fail

[00:01:09] **Ben:** I'm going to kick us off with a failure, which is that I have been working on this demo app for some feature flag targeting experimentation. And I got the V1 version, the kind of proof of concept version working with AlpineJS and full page refreshes, essentially a multi page application. That, gathered the data with CodeFusion and just rendered it HTML page and then wired up some click handlers kind of stuff with AlpineJS.

[00:01:36] **Ben:** And once I got that done, I thought, okay, now I'm going to go back and make it look nice. And I'm going to throw an Angular 18. That's the latest version at the time of this recording. Angular 18 SPA single page application experience. It's going to be smooth and classy looking, and I'm going to have encapsulated styles, and it's going to be really nice.

[00:01:54] **Ben:** And what I'm realizing is. Twofold one, I'm just rusty on Angular and I thought I'd be able to jump back into it, like riding a bike, remembering all the little details and it, I don't know if I'm tired or just getting old. And this is a by product of cognitive, you know, steady cognitive decline over the, the last 80 years of a person's

[00:02:16] **Tim:** Eight years.

[00:02:19] **Adam:** Person, woman, man, camera, TV.

[00:02:23] **Ben:** I'm just, I'm, I'm having trouble kind of.

[00:02:26] **Ben:** Kicking over into the flow state for this Angular stuff, in particular, I've hit a kind of weird hurdle where I'm just trying to build a little bit of a, of an HTTP client for contacting the backend API. And I have decisions to make about what layers handle, what type of logic and, and how the, the strong typing works at TypeScript.

[00:02:49] **Ben:** I'm having trouble figuring out where to put things. And on top of that, that's sort of making me not immediately fall in love with TypeScript. I, I don't use TypeScript in my day to day life because I work in AngularJS, which is, you know, like 15 years old at this point.

[00:03:05] **Adam:** Okay.

[00:03:05] **Ben:** and it's just vanilla JavaScript that happens to have some APIs that, AngularJS provides.

[00:03:11] **Ben:** And dealing with, Typed languages on the client side is feeling a little bit like, I love the fact that it enables dependency injection, and I'm almost not liking anything else about it. It's just forcing me to put a lot of types. And I don't want to say overly consider things because it's calling me out on my bad assumptions and that's exactly what it's supposed to do, but it's one of those things where the bad assumption is the one out of a thousand cases.

[00:03:45] **Ben:** And I'm just like, F it. Let me, let me just tell you that this is an object and it has the key type on it. And I don't have to worry about, you know, that it's actually sometimes nullable and depending on this, and I have to check if this is an instance of that. And I don't know, I mean, I'm, I'm sure I'm going to get over this mental hurdle.

[00:04:04] **Ben:** I'm kind of in the dip of relearning the Angular platform and I'm sure I'll get there, but it's just. It kind of hit me in the face. It was a slap across the face that I'm not young and nubile and, and I can't just jump in and pick up the reins as quickly as maybe I used to.

[00:04:22] **Carol:** Oh, man, getting old sucks, Ben.

[00:04:25] **Ben:** Oh yeah.

[00:04:29] **Carol:** I will say I feel like I'm going to date myself a little, but Tim will remember the struggle that we had. Let's go to Angular 2.

[00:04:36] **Tim:** Hmm. Yeah.

[00:04:37] **Ben:** That must've been huge. Cause for, for people who are maybe. Not as old as us. the Angular 1. x to Angular 2 was a complete ground up rewrite of the Angular platform, introduced TypeScript, introduced RxJS, introduced a whole bunch of stuff, a much more robust router. And it basically, there was no upgrade path, really.

[00:05:02] **Carol:** Nope. It wasn't pretty.

[00:05:03] **Ben:** Yeah, they like sort of made up the fact that you could incrementally do stuff by wrapping things and doing some weird stuff. And every time I saw an article about it, I'm like, what are you, nuts? No one's doing this. So that's me. That's my failure. Carol, what do you got going on?

## [00:05:21] Carol's Triumph

[00:05:21] **Carol:** Well, I am going to, see your failure and raise you one triumph.

[00:05:25] **Ben:** Oh, cheers.

[00:05:26] **Carol:** Yeah. Thanks. So I got promoted at work.

[00:05:29] **Ben:** Ah,

[00:05:29] **Carol:** Big, big things. Woohoo.

[00:05:31] **Tim:** Wow.

[00:05:31] **Carol:** So I was, yeah, jazz hands. I got hired as, an engineer just to kind of be on a team. And you guys remember me talking about it and they're like, Hey, we're going to give you your own team.

[00:05:42] **Carol:** So we're going to make you an architect of the team. And now I am the architect for the entire, like, department. So now I have a bunch of architects and teams that I have to help along the way. And. Basically, it's just a fancy way of saying I'm going to bulldoze through problems and support our team, and that I'm going to drive for success and make sure that we continue on the paths we're on and that we make change where we need to.

[00:06:07] **Tim:** so are you going to be doing more people managing or code managing?

[00:06:11] **Carol:** no, here's the good thing. So there are these, unicorn type positions that exist within the government and they're called technical. Grades and technical promotions. So I got a technical promotion without having to supervise anyone. So I don't have to actually manage people. Like I'll be called upon to, to do things like, how do I feel someone's skill set is, like where are we missing skills?

[00:06:35] **Carol:** Those types of things, growing people. But I don't have to worry about, Oh, you're fighting with your coworker. That's not my problem. I don't have to deal with that. I get to just enjoy technology and enjoy innovation and see people succeed without having to do the supervisory things.

[00:06:53] **Tim:** but you do have to do the like people, technical reviews of people, right?

[00:06:56] **Carol:** Nope. Nope. Only if I get asked to provide feedback will I actually like jump in and be like, yeah, I think this person's competent in what we're trying to achieve. Or I think they, they have some areas to grow in. So I'm excited.

[00:07:12] **Ben:** congratulations, Carol. Well

[00:07:14] **Carol:** you.

[00:07:14] **Tim:** Well deserved,

[00:07:16] **Carol:** Thank you. So what about you, Tim? What are you bringing in tonight?

## [00:07:19] Tim's Triumph

[00:07:19] **Carol:** Woohoo!

[00:07:21] **Tim:** Triumph, it's a team Triumph. I can't take a lot of credit for it. I'm sort of, I've not done a single line of code on this. this, but I've been driving the product that this is our new, we're doing a direct to T SYS, which is, basically used to be Visa, Visa sold it, but it's a T SYS integration, direct to T SYS, which is a credit card platform, which And yeah, we got pretty much most of the features working.

[00:07:45] **Tim:** The team's worked really, really hard on it in the past, past like eight, nine months, and it, and just in time, because the paperwork, which we've been working on for years is also, it looks like it's just about to be signed. So we've got, we've sent everything off for the paperwork is always the hardest bit in our organization.

[00:08:03] **Tim:** It's the legal stuff, the security stuff, but handing that off to, we've Basically sent it to the other party and said, look, here's thousands of pages of documentation and, and please review this and tell us what we're missing. They came back with like 10 bullet points, which was great. So we filled those out and, gonna get this.

[00:08:26] **Tim:** So yeah, hopefully soon we'll have, have this new product up and running and be able to. Squeeze a little extra out of the margins,

[00:08:34] **Ben:** Very nice. Woop

[00:08:37] **Carol:** it, what's it written in?

[00:08:39] **Tim:** ASP. NET. Yeah.

[00:08:41] **Adam:** How many,

[00:08:41] **Tim:** C sharp.

[00:08:42] **Adam:** how many different like languages or stacks or whatever you want to call it? Would you guys, would you say you, you run over there, Tim?

[00:08:49] **Tim:** so we, you know, we've got the old legacy ColdFusion stuff that's still kicking and running. Yep. Yep. Been, been, been likes that. we've got that. We've got, Scala, and we got ASP. NET. I'm trying to think if there's anything else.you know, database. We have Postgres, our Lord and Savior,MySQL.

[00:09:05] **Tim:** We don't have any SQL, Microsoft SQL. So really about three language stacks. Yeah. And then just some stuff on AWS that for infrastructure.

[00:09:15] **Carol:** Well, congrats, that's awesome news.

[00:09:18] **Tim:** Yeah. So hopefully in a few weeks, I'll be able to say that it's actually, launched and we start using it with some customers and. And I was super excited because it kind of gives us some more flexibility about how we basically bill people. Right. A little, a little more flexible, a little more flexibility about, you know, finding ways to help the customer be more flexible in how they do payments, but also be a little more flexible about giving them a good rate while at the same time, we're making a good margin on each transaction.

[00:09:46] **Tim:** So

[00:09:47] **Carol:** This sounds like something Adam mentioned recently, with the whole, do you allow PayPal and Apple Pay from the same people who you, like, ACH from, or direct bill. Yeah.

[00:09:57] **Tim:** that's me. How about you, Adam?

## [00:09:59] Adam's Triumph

[00:09:59] **Adam:** I am also going to go with a triumph and as is my prerogative, I'm going to double dip again. So I've been talking for the last couple of weeks about this feature that I've been building to support multiple payment gateways concurrently for the same customer, which has, you know, the the mouthful of a name.

[00:10:21] **Adam:** We're calling it like hybrid payment service providers hybridization project.

[00:10:26] **Tim:** Hydra, Project Hydra.

[00:10:29] **Adam:** that's the quiet part. We keep that inside. well, so while I, let's just say I've reached feature complete. I finished all the code changes that I think I need to make. and I'm just now getting started on testing. So, I, it's surprising to me a little bit how fast it went, right? Like, I know I've been talking about it for a couple of weeks, but. I'm doing other things too, right? I'm doing compliance work, I'm mentoring my junior developer, that sort of thing. And so like, really, I've been spending like two, maybe two and a half days a week writing code, for the last couple of weeks. And so, really I've gotten it done in like, you know, a weekend change.

[00:11:03] **Adam:** and as I talked about last week, like working backwards, which is new and different for me, trying to make sure like, you know, I know where I'm going to end up and then all the changes sort of like, Get to that point, right? I'm making changes so that I can, I don't know, accomplish the, the, the goals of the code that's already written, right?

[00:11:19] **Adam:** I'm working backwards. Anyway. so that's all done. I started to push that to QA at the very end of today, and I'll be doing some testing there, over the next couple, probably a day or two. and then it'll be ready for production, which is super exciting. And it's behind a feature flag. So.

[00:11:34] **Carol:** Yay! Fancy beach of flags.

[00:11:36] **Adam:** Yeah. so that's cool.

[00:11:37] **Adam:** And then, my other triumph, a personal triumph, I have been, working out and dieting again, which, you know, I guess it's a little bit of a failure that I like, you know, I go off and I get fat and then, I have to come back and, you know, work out and diet again. But, but since I started dieting and working out about a month ago, I'm down almost 10 pounds.

[00:11:56] **Adam:** So,

[00:11:57] **Carol:** that's great news!

[00:11:58] **Tim:** That's good.

[00:11:59] **Adam:** yeah.

[00:11:59] **Ben:** What is, I'm curious because I struggle very much to lose any weight whatsoever. It seems it's, yeah, like we wish it were so. what is your

[00:12:10] **Tim:** layer of chubby.

[00:12:12] **Ben:** Dieting?

[00:12:13] **Adam:** What is my strategy?

[00:12:14] **Ben:** Yeah. Like, are you just eating less or are you eating different

[00:12:18] **Adam:** I am eating a little

[00:12:19] **Carol:** your macros and weighing your chicken?

[00:12:22] **Adam:** Yes, I weigh a lot of my food unless it's like something, you know, if we have a, a dish that we've had recently and I have it like in my My phone. So I use an app. It's called Macrofactor. It is not a free app, but it's very much worth it if you are trying to do the same thing.

[00:12:38] **Adam:** You know, a lot of these apps like MyFitnessPal or whatever, you, you have to input everything and it'll, it'll track it all for you and give you a place to put it. But it's, it's very, very manual, right? You can create recipes and say, okay, I'm having two servings of this recipe or whatever.and they, it has, you know, like a barcode scanner in my fitness panel and stuff too.

[00:12:56] **Adam:** However, what I've really, liked about this app, it's called Macrofactor, is that there's two things that I have to do. I have to track what food I eat, And I have to enter my weight. And I, I've gotten into a really good habit of just weighing myself every morning, like after, you know, I get up and I have my morning bowel movement and, and then I weigh myself because I figure like that's going to be the, sort of the, the, the baseline, right?

[00:13:20] **Adam:** That's the most consistent way I can weigh myself every day. If I weigh myself like after dinner, then it's going to depend on what I ate that day, right? Like,

[00:13:27] **Ben:** all day.

[00:13:28] **Adam:** right. So I'd figure like, that's my, that's my, my way to be like, I don't know, as consistent, I guess, as I can be in terms of like, what's inside my body at that point.

[00:13:39] **Adam:** and so I weigh myself first thing in the morning, I enter that every day, and then I track what I eat. And I work really hard to, be as accurate as possible. And you know, and it's got like, you know, you can say, okay, I'm trying to lose weight, I want to lose a half a pound a week, you know, I'm, Gonna, you can say like, I, this is what I want my macro breakdown to be.

[00:13:58] **Adam:** I want to be like, you know, 40 percent protein and split the rest evenly between carbs and fats or whatever. You know, you can do whatever you want. I have it set so that on Fridays and Saturdays, I'm allowed a little bit extra calories and the rest of the week is lower calories just so that I can have weekends a little easier sort of thing anyway.

[00:14:16] **Adam:** and, and so what it does is between your weight and what you track that you eat, it figures out what your like daily expenditure is, you know, and that sort of thing. So it can, and it does like rolling averages of your weight and of your expenditure and, and it just like, you just have to enter those two things and it figures everything else out for you.

[00:14:31] **Ben:** It tells you like, okay, this is, you know, you're, you're burning this many calories a day. So if you eat exactly that many calories a day, then, then that's your maintenance sort of thing.That's pretty good. I have zero self control when it comes to food. It has to just not be in the house or I have to make a blanket. Like I just don't eat this food anymore. Cause the second I put my stupid fingers in the bag,

[00:14:57] **Carol:** huh. It never

[00:14:58] **Ben:** Then it's like, then I'm going to come back to the bag every 15 minutes.

[00:15:01] **Adam:** There's no such thing as eating just two Oreos.

[00:15:04] **Ben:** Yeah. Yeah.

[00:15:05] **Carol:** So I know this podcast isn't about your app and what you're using, but does it have recipes in that? Cause we use one for a while that you basically would pull up recipes and then you just be like, yeah, that's exactly what I'm making. Like I'm going to make this turkey chili. And from there I'd put it in four bowls and separate it and be like, that's the serving, it's four servings.

[00:15:23] **Carol:** Easy to do. Yeah.

[00:15:25] **Adam:** I, I know that there are some recipes in there. I've added my own recipes for like for what the things that we make. You can add your own recipes and, and it's, it's really annoying. Sometimes I'll like, you know, my wife will make dinner and I'll be like, okay, nobody take any of it yet.

[00:15:37] **Adam:** I'm going to take all of it out of, out of the pan and I'm going to weigh it, put it in a bowl and weigh, like, okay, this is a full, you know, like the, the

[00:15:45] **Carol:** Oh, I would

[00:15:46] **Adam:** prepared amount. Yeah. And then I'll put it back in the pan.

[00:15:49] **Tim:** You just dirtied a bowl for no reason.

[00:15:51] **Adam:** well, you can't, you can't put a hot pan on the, on the scale, right? so yeah, yeah, do that so that I know, okay, this is the full amount.

[00:15:58] **Adam:** And then I can, you know, if I'm going to take a quarter of it or a fifth of it or whatever, then I know, okay, I need to take this many grams of the food and I'll dish it up that way. But, yeah.

[00:16:07] **Ben:** The other day somebody put something on Facebook that just made me feel seen. And it was something like, being an adult means working out every day and eating clean so that I can stay 25 pounds overweight. I was like, yeah,

[00:16:23] **Ben:** that feels right.

[00:16:24] **Tim:** yeah, my, my, my phone has been shaming me. Cause like we were in Ireland for a month and we walked a lot. Right. So we'd walk to the grocery store, walk, you know, we walked everywhere. It was a lot of walking. It was great. You know, the weather was nice. It was nice and cool. So I didn't get overheated. And so I get back here and it's like, my walk is, you know, from my bed to my computer. And once in a while to the mailbox and then it's like, it says, Hmm. So it seems to be a significant drop off in your activity. Is everything okay? I'm like, like, stop shaming me. I'm not doing 10, 000 steps a day anymore. I'm like doing like a thousand, maybe at most.

[00:17:01] **Carol:** Oh man. Same thing. I use my Apple watch to track a lot of stuff and, over the past few weeks, because I haven't been working out hard. Like I've worked out some since I got to Texas, but not a ton. It's been trying to adjust. And my watch, I feel like every week goes, we have new trends for you. And they're way worse than what they were.

[00:17:20] **Carol:** Like I'm sleeping less. I am moving less. I'm standing up out of my chair less. I'm like, I'm just getting it all wrong. Stop telling me. Don't shame me.

[00:17:30] **Ben:** The most shaming for me is, The, the audio books app on the iPhone, it will alert you if you've beat your recent trend and read it quote unquote reading, you know, cause it's audio books and sometimes I'll throw on an audio book to take the dog out and literally two minutes later, it'll be like, congratulations.

[00:17:47] **Ben:** You've read more than you've read in a long time.

[00:17:51] **Tim:** You're like, I've been listening to podcasts, stupid audible.

[00:17:54] **Adam:** That's good.

[00:17:56] **Ben:** Good times.

## [00:17:56] It Was The Best of Code, It Was The Worst of Code

[00:17:56] **Ben:** I

[00:17:59] **Adam:** was the best of code, it was the worst of code. I think it's time to move on to our, our, our topic for the day. So, this was an idea that we had, and we just kind of wanted to have a little group discussion. Like, you know, what is the best codebase you've ever worked on?

[00:18:12] **Adam:** What is the worst codebase you've ever worked on? And we, not to spoil it or anything, but we did have a brief chat about this before we turned the mics on. And it sounds like we kind of all have the same answer. Haha.

[00:18:24] **Carol:** Yeah. I mean,

[00:18:25] **Tim:** It can be a little redundant, but yeah.

[00:18:28] **Carol:** I don't know that I've worked on any code base that I would want to write a book about and be like, this has just been amazing.

[00:18:35] **Adam:** Right.

[00:18:36] **Carol:** Every code base I've had has had lots of, lots of challenges. Oh,

[00:18:45] **Tim:** 13 years old in the Kmart store with the brand, with the computer sitting there for sale. And I wrote line 10, say hello world, line 20, go to line 10. That was the best, without a doubt, the best code base I have ever worked under my, it was clear.

[00:19:08] **Tim:** It was concise. It had a function. It was noticed people like we're talking, Hey, look, you know, Timmy was here, you know, whatever. Yeah. So. Yeah, that was, that, that was the best code after that. It was all down here from there.

[00:19:22] **Ben:** I, if I can just interject with a philosophical statement, well, not so much a philosophical statement, but this immediately makes me think of John Gall's law, which I'm almost certain we've talked about several times, but if I can read the law very quickly and then follow up with another thought. John Gall's Law states that a complex system that works is invariably found to have evolved from a simple system that works.

[00:19:47] **Ben:** The inverse proposition also appears to be true. A complex system designed from scratch never works and cannot be made to work. You have to start over, beginning with a simple system. And I wanted to throw that out there because I do think that the best codebases that I've worked on were code bases that started from a small concept and grew over time.

[00:20:11] **Ben:** I mean, Adam's referring to his, his code being the work of his life. I mean, because he's been

[00:20:17] **Adam:** Yeah, I haven't said that yet, but go ahead.

[00:20:18] **Ben:** No, you said it, you said it,

[00:20:19] **Adam:** it before we turned the mics on.

[00:20:21] **Ben:** oh, sorry, my bad.

[00:20:23] **Carol:** Oh, geez,

[00:20:24] **Ben:** We know like, I've been working on the same application for, for over a decade and it has a lot to be desired, but there's also a lot of decisions that were made over time, conversely, I've worked a little bit in a microservice based rewrite of set platform, which is essentially a complex system designed from scratch and it's bonkers.

[00:20:49] **Ben:** and so I, I think that, I feel like John Gall's law applies really well here, at least in my experience.

[00:20:57] **Adam:** Yeah, I mean, I don't disagree with Galls Law, for sure. So, yeah, I mean, okay, since you've, since you've kind of, you know,

[00:21:05] **Ben:** Yeah, my bad there, my bad.

## [00:21:06] Adam's Current Codebase

[00:21:06] **Adam:** you, you spoiled mine, uh, so the, the, my answer, I think is gonna be the current code base that I'm working on, which I've, I've been working on for more than 10 years now.

[00:21:19] **Adam:** and I think it is kind of simultaneously the best and the worst code I've ever worked on. I would say it's the best because it, it does, I mean, I don't think I've ever written code that has generated more revenue than this one, right? This one is doing a tremendous job. It's very useful. It has made a lot of people's lives better.

[00:21:40] **Adam:** And when I think of back, think back to software that I wrote previously, like when I started my career, I was working on an intranet where people could do, I mean, I guess it could do alpha paging. That was kind of cool at the time. like when, when you had a beeper on your hip and it had, you know, the like 20 character display and

[00:21:55] **Ben:** Nice, nice,

[00:21:55] **Adam:** whatever, that was cool.

[00:21:57] **Adam:** and I did, you know, I've, I've worked on some interesting problems in the past, but nothing was ever really of like this scale. This challenging, this complexity. And like you said, you know, it grew from something small initially. And it's like, okay, well, we've hit this problem. How do we deal with that?

[00:22:13] **Adam:** And we, we grow in complexity to deal with that. so in that way, I'm like really proud of it. but at the same time, It's a 10-year-old code base and you cannot always, like, pay down your technical debt. You, there's just stuff that it's working. So I, I can't afford to, to rewrite it just because I don't feel like using ORM anymore.

[00:22:34] **Adam:** so like there's a lot of code in there that like, is not as performing as it could be or it's, it's problematic for us for one reason or another.and it's, you know, it's 10 years of lackluster decision making alongside a lot of good decisions in there as well. But like the, the bad decisions are the ones that I'm thinking about.

[00:22:53] **Adam:** and we just have to carry that and deal with that fact. God knows how much longer.

[00:22:59] **Ben:** There's definitely something to be said about working in a code base for a long time, if for no other reason, you're super familiar with it and your instincts are Instantaneous, you know, you, you want to know where something's done, you know, the name of the file more or less, and you can super menu it in your IDE to get to it.

[00:23:18] **Carol:** 100%.

[00:23:19] **Ben:** There's not a lot of looking through folders, trying to find stuff. And that immediacy of access, I think probably also heavily colors the way that we think about the quality of the code, because there's a layer of friction. That has been inherently removed when compared to someone else who might be diving in for the first time.

[00:23:41] **Adam:** Yeah, for sure.

[00:23:42] **Carol:** Yeah, Spaghetti Code is a lot easier to be okay with when you understand it all. If you're coming in day one and you're like, why is this file in this folder in this place where it should never have been placed and now I have to know to go find this here? Like, why are we doing work for this piece of the system in something called something totally different?

[00:24:05] **Carol:** But yet, when you know it, you're just like, oh, cool, I'll go there. You stop, you stop seeing those big problems.

[00:24:11] **Tim:** that's, that's becoming a swamp guide, right? That's, that's, that's what that is. I mean, I'll, I'll say the worst code it, you know, is code that basically there was just, you know, Teams of people or individual people, and none of them had really any contact with each other about how the overall architecture should work.

[00:24:30] **Tim:** And they all just kind of did what they wanted. And then, and then there was this like, okay, try to make it work together, right? Like, like, let's, let's, all right, we got this thing that kind of works, this thing that kind of works. Let's kind of stick them together.

[00:24:43] **Carol:** been there, Tim.

[00:24:45] **Tim:** know we both were, but, but it's like, okay, what, why does it work this way?

[00:24:51] **Tim:** Well, so and so wanted to do it that way. So, you know, someone went to a conference and they learned about, you know, this new, new method and so now, now they did it that way and no one else learned about it. And then that person's now gone. And so it's like, why is it run this way? I'm like, well, that's so and so's code.

[00:25:08] **Tim:** And everybody's like, oh yeah, yeah. So and so. Yeah. It's, so I, I guess what I'm trying to say there is that software. When you have a, you know, unless you're in just a company of one person, it's really kind of a team building thing. But I don't think coders in general tend to be team players. And so I don't know how you get to that place where like everyone kind of agrees on here's how.

[00:25:38] **Tim:** Things go, here's the archi I've never been in a company that's really done that well. I don't know if I do that well. I just trust my team to make right decisions and I don't micromanage them. And as long as there's good, testing and as long as they can show that it works and there's testing and good documentation, I'm like, okay.

[00:25:56] **Tim:** I'm going to assume things are well, but I don't know.

[00:26:01] **Carol:** So I think for me, I've got two things that kind of like go good and bad, right? So a bad, a really bad system I worked on, every customer had their own version of the software. So there was no core like software, like this is what our application does. It was if you're customer A, this is how your software runs.

[00:26:23] **Carol:** We're going to call it our system, but if you're customer B, you have your own version of the software and this is how it runs. There is no like unity, like

[00:26:32] **Tim:** Well,

[00:26:32] **Carol:** unity where it started.

[00:26:34] **Tim:** It's loosely based off an older one. It's like an archeological dig, right? It's like, you're, you're digging, like this one was built on this one on top of this city, but this one was built on top of this city, like 200 years later. Yeah.

[00:26:45] **Carol:** It's not fun. It's not fun when you're trying to work different versions of the application, different repos for problems across the board. That's not a good situation. But on the good side, you know, I've worked at companies where we have one code base Everyone uses that. Well, if you log into our systems, then you're using that single code base.

[00:27:06] **Carol:** It's just how it has a tentative, database. So depending on what customer you are, you have your own database. So you just have to look at different places, but the database schemas. are perfectly in sync. There's no difference between customer A or customer B's database other than the data that lives in it.

[00:27:23] **Carol:** So I think that's a great code base, is one that you don't have to support multiple versions for customer needs. And a bad one is when you have to support a code base for every application and for every customer. That's not fun at all.

[00:27:38]

## [00:27:38] Adam's Previous ColdFusion Application

[00:27:38] **Adam:** So actually while we've been sitting here, I know I said that possibly the worst codebase I've worked on is my current one, but I did kind of have a memory of a really bad application that I was fortunate enough to work on. So. Yeah, I'm gonna spill the tea. I'm not gonna say the company name, even though the company itself, I don't think technically exists anymore.

[00:27:58] **Carol:** It was bought by 1 800 Flowers. Interesting.

[00:28:01] **Adam:** but, so, I, this was a codebase that I worked on when I was a consultant. I did, so I did a couple of years as a consultant before I started working here. and, so we were brought in to work on this codebase. It wasn't originally written by my team or anything. But it was a ColdFusion application, and it, I'm almost certain, made extremely little use of components, like it was pretty much all CFMs, and it was like, you know, query at the top, view down below, and like, submit to self, or maybe submit to another one, and it was the same sort of structure.

[00:28:35] **Adam:** It was a huge application, e commerce, it had like, Flash widgets in it that were like, you know, real time. Dynamic, designing of, of the products. I don't, I don't want to give too much away about what it was. Cause I don't, you know, I don't know if this is a publicly traded company. I don't know if it's a, if it's still there or anything, I don't want to get anybody in trouble.

[00:28:55] **Adam:** So, but it was a, it was a very. I mean, what it was doing, especially considering this was like 30 years ago, was, was really cool, God, please tell me it wasn't 30 years ago. No, it couldn't have been 30 years ago because I'm only 40 something, so let's, let's say 15 years ago, or 15 to 20 years ago, they, but it was, oh my God, it was, For the time, it was really cool, very dynamic.

[00:29:20] **Adam:** Just like the, so the very first thing that I did, well, you know, we were brought in because there was some performance issues and they needed to do some new features and. I looked at the code, it was application. cfm, not application. cfc. And,

[00:29:33] **Adam:** that dates you there for all the cold non ColdFusion people. Yeah. it was pretty old code. And then, there was so much stuff.

[00:29:41] **Adam:** I mean, we're talking about like an 800 1000 line application. cfm with like a bunch of database queries in it and stuff. And so, for the uninitiated, this is all stuff that runs on every single request. Right? This runs before the, the code that you're requesting, right? If you request a page before that page

[00:29:59] **Tim:** I, how else am I supposed to get my variables?

[00:30:03] **Adam:** Oh my god. And it, yeah, and it used client variables instead of session stuff. And yeah, so I, yeah, I, I think this is going to go for now in my, my worst code base. Column.

[00:30:17] **Carol:** Well, let me ask you something. You guys have, like, I remember when I used to work with ColdFusion, there was no way to have, like, a true debugger running when you run your code. So it's not like you have breakpoints and you can't do watches on your variables and you can't Pause the application and it'd be working.

[00:30:36] **Carol:** Like I'd always have to throw in the CF outputs and CF dumps and get my information that way. There was no fancy way to just, in the middle of it, let's just pause right here, take a look at what's going on, figure out what needs to happen. Hot reload, which you could reload immediately in ColdFusion, which was nice.

[00:30:54] **Carol:** Sometimes I have to completely start over. Hot reload, fix it, and then see what it looks like.

[00:31:00] **Adam:** there was, there probably technically still is a step debugger available, but like it was only in ColdFusion Builder and

[00:31:08] **Ben:** also, like, pre Java, when

[00:31:11] **Adam:** oh yeah,

[00:31:12] **Ben:** in, I don't know, C? C

[00:31:15] **Tim:** Five.

[00:31:16] **Ben:** was a debugger built in at that point,

[00:31:19] **Tim:** that was a five.

[00:31:20] **Ben:** then when they moved to Java, I think we lost it. But then the, the good folks at, Fusion Reactor, You can pause code through their, their Java agent.

[00:31:32] **Carol:** Oh, that's kind of cool.

[00:31:34] **Tim:** Yeah. Which they've told me and I've never figured out how to do it. So

[00:31:38] **Ben:** the one nice thing about debugging on a ColdFusion server or really any server is that the server is typically not very stateful, meaning most of your state in a server side application is stored in the database and most of the web applications that sit in front of it are, have to be scalable horizontally, at least in many of the modern applications.

[00:32:03] **Ben:** So they can't really have state. Otherwise they wouldn't be able to scale very well. So typically a server side application is significantly easier to debug, at least in my experience, than a JavaScript client side application, because client side applications have a lot of complicated states. Hanging out and refreshing becomes really weird.

[00:32:24] **Ben:** You got to get back to points in a workflow. And the, I mean, thankfully the debugger in the Chrome DevTools is, is really world class,

[00:32:34] **Carol:** does really good.

[00:32:35] **Ben:** all to say that when I'm debugging my cold fusion code, it's a lot of dumping and aborting is pretty much,

[00:32:41] **Carol:** that's what I remember

[00:32:42] **Ben:** much how I get it done,

[00:32:43] **Carol:** actually like add lines of code in there to make it do something, where I think,

[00:32:48] **Tim:** Or, or send yourself an email.

[00:32:50] **Carol:** yeah, oh, with like a dump, like you could do that. Is that what you're talking about?

[00:32:55] **Tim:** Yeah. Send yourself an email with a dump that basically says, here's what happened while it was running through

[00:33:00] **Ben:** but yeah, been there.

[00:33:01] **Carol:** about

[00:33:02] **Tim:** So ghetto.

[00:33:04] **Carol:** I

[00:33:04] **Tim:** yeah.

[00:33:06] **Carol:** Has the ability to debug well and break.

[00:33:12] **Tim:** Yeah.

[00:33:16] **Adam:** a code base? It's like, not just like looking at a file of code,

## [00:33:19] What Makes a Codebase Good or Bad?

[00:33:19] **Adam:** but like as a, as a whole, as the code base, what makes, what distinguishes a good one from a bad one? And

[00:33:25] **Carol:** read it? Like, is it laid out well? When you open it, does it make sense on where things go? I think that's a good code base. I think, I think that's a good flag that it's going to possibly be a good code base. Like, how's it organized?

[00:33:41] **Ben:** Yeah. And just to double down on the debuggable aspects of it that Carol was just talking about, stack traces, a language that makes stack traces available, and then a programmer who understands how to access and log that stack trace is so critical. I can't tell you how many terrible code bases I've looked at that will log errors, but don't really tell you where they're coming from. Oh. I don't know how people do anything in an application

[00:34:11] **Adam:** So, okay. I got, I have a bone to pick here. I think 99 percent of what you were just talking about, ColdFusion does pretty well. And I know you happen to love ColdFusion, Ben. So I'm going to pick on you. So I had an issue today. I made all, you know, when working on these payment service provider hybridization things, the, what do we call it?

[00:34:31] **Adam:** The, oh, Project Hydra. the, I made some changes to a file today. I made changes to like dozens of files today, right? And, the, I started up the application. It's a, it's a Framework 1 application. So it's very heavily component based. And. I had made a syntax error in one of my files and, and DI1 helpfully spits out the, the error saying like, you know, couldn't, couldn't instantiate this.

[00:34:55] **Adam:** Yeah. Yeah. That's where I'm at. That's where I'm headed. couldn't instantiate this class because there's like a, a, a. I think it implied syntax error. It didn't even say syntax error. It's just like, can't instantiate this class. And you're like, okay, there's, there's some bad syntax in there somewhere, but it doesn't.

[00:35:11] **Adam:** And it does give me a stack trace, but that stack trace is the code that tried to instantiate the object. Doesn't tell me anything about the file that has the error. And it, it just drove me nuts.

[00:35:21] **Ben:** hundred percent. And it, and it's inconsistent. Sometimes if you have a problem, it's like, It's like, it depends on how the CodeFusion compiler itself is failing or something, because DI1, just for this, for the listeners, it does a lot of meta programming. So you say, Hey, I need, give me an instance of the payment gateway.

[00:35:43] **Ben:** So it looks at the component and it, and it reads the definition of the payment gateway into memory. And it says, okay, let me look at the metadata associated with this. It has five properties. you know, it has an API key, it has an API type, it has a logger, it has this, it has that. So then I have to go back to my dependency injection container and I have to get those things.

[00:36:03] **Ben:** And if they don't exist, I have to create them and then I have to. And then I have to instantiate the payment gateway and I have to set all these properties and I have to finally return to the context that was asking for it. All to say, anything in there can break. And sometimes DI1 is really good about saying, I couldn't do it because of this specific line, there was something wrong.

[00:36:24] **Ben:** And sometimes it gives you the error that's just like, It didn't work and the injector failed. And you're like, well, why did the injector fail? And then, I mean, you can continue on with your story, but it's in my case, at least it's a lot of just commenting out entire files.

[00:36:39] **Carol:** you figure it out, right? Yeah. I remember those days. Split

[00:36:43] **Adam:** many times in my life have I done a binary search of my code by like, just comment out half the file? Okay. The error is not in that half. It's got to be in the other half. Now let me take that half and comment out half of

[00:36:51] **Carol:** it in half.

[00:36:52] **Adam:** Yep,

[00:36:53] **Ben:** it's like a manually bisecting.

[00:36:56] **Tim:** reasoning.

[00:36:58] **Adam:** So what this one turned out to be.

[00:36:59] **Carol:** me of what's bad code. So keep going. Yeah.

[00:37:02] **Adam:** Yeah, so what this one turned out to be was I was, let me make some changes to the way I was calling a particular function and it, I accidentally had like comma, comma. Between two arguments

[00:37:14] **Ben:** Yo, I was just about to say that that's the worst is the extra comma.

[00:37:18] **Adam:** Yeah. And it's just like, blow up. And now, fortunately, very fortunately, I knew that I was looking for a syntax error. And I, and the one thing it did tell me, the error message was the name of the file that couldn't be loaded. Right. So, okay. I've got it nailed down to one file and I'm looking for a syntax error.

[00:37:37] **Adam:** So I went to my, my diff in my GitHub pull request. I'm like, okay, it's gotta be in this file. And it just so happened that there was only like eight lines that I changed. So it was really easy to find it.

[00:37:48] **Ben:** And

[00:37:48] **Adam:** was just, I was just so mad.

[00:37:50] **Ben:** it's so solvable too, because really all they would have to do is in the DI1 code where it tries to read in the component metadata. If they just put that in a try catch, then I'm pretty sure they'd be able to get, but there's something that they're not catching properly.

[00:38:09] **Adam:** I would be, I don't know for sure. Personally, I would be surprised if that's true. If it's actually DI1's fault and not Lucy's fault in this case because I was using Lucy. I would be surprised.

[00:38:23] **Ben:** It is, it is possible that there's something, because the, the there's weird, there's like a, there's like a special class of error that can't be caught. And I, I think it's like the actual parser errors or, or there's like a, I don't know, I, I'm talking above my pay grade here, but there is something very special that can't be caught. believe.

[00:38:44] **Tim:** Leprechauns.

[00:38:46] **Adam:** But like, I mean, that's just it to, to, to go back to the conversation about like, you know, what makes code good and bad, like not, I mean, not to say like the language that you choose, but at the same time, like if you're writing code and the, the language can't tell you what line you've got an error on, that's, that's bad.

[00:39:03] **Ben:** Yeah, really bad.

[00:39:06] **Tim:** Yep. Looking at you, Orm.

[00:39:08] **Ben:** I will be really interested to see when Svelte 5 comes out, and I, and I don't think it has yet, right? It's probably in

[00:39:15] **Adam:** I think there are like release candidate or beta or something like that. Yeah.

[00:39:18] **Ben:** you're, you're,

[00:39:19] **Tim:** red meat in front of him? Anytime he says felt,

[00:39:22] **Ben:** you're our in house Svelte expert, and I know that Svelte is going to be having runes, I, I don't really know exactly, and I think they already have some degree of reactivity.

[00:39:33] **Ben:** Where you can like compute it. Like this variable is computed based on these other variables.and I think I, I bring this up because it's top of mind for me diving back into Angular with RxJS and all of this reactive stuff, and then Angular also has signals now, which I have not dug into, I find reactivity in general to be one of those things that feels really magical at first, but then can, I think, quickly get out of hand.

[00:40:03] **Ben:** And one of the things that we always bring up, or people always bring up when they talk about reactivity is Excel and how amazing is it that in Excel you can have, you know, like hundreds of cells linked together and you change this and suddenly the whole spreadsheet changes and it's just mind blowing and it's magical.

[00:40:20] **Ben:** But then I also think to myself, how often has it been where I want to conditionally color some cells and now I have this crazy ass. Like 17 nested deep function, expression that has to do all kinds of stuff to make sure that it, and I'm like, this would just been three lines of code if it was like a four statement and a couple of ifs.

## [00:40:44] Not Being Able to go Back to Code

[00:40:44] **Carol:** I did have like one thought when I think about a good codebase and a bad codebase.

[00:40:49] **Adam:** Yeah,

[00:40:49] **Carol:** you guys ever written something that you thought was so fancy and so shiny and just the

[00:40:57] **Carol:** But a year later, you're looking back at it going, why would I have, like, ever put that in the system and why did I think this was a good idea? And now you've made the code base bad, but you don't know how to take it out.

[00:41:11] **Adam:** Oh, that's a really interesting spin on it. I mean, when you started talking, I was like, yeah, of course. Who hasn't felt that the code that they wrote last week is now total garbage.to, to take it to the point where like, you don't know how to pull it out. Like, ooh. Yeah. So,

[00:41:25] **Carol:** so, we're so focused. Like everything is now working around this process that you've created. And suddenly it's, this is actually a pretty bad process and we can do it a lot better, but how do you do it?

[00:41:37] **Adam:** Yeah. I mean, I, I, I have an answer. and I started to like, think about how I would explain it, and I think that has given me an idea of how I would fix it. But , we'll go through it anyway. Right. So, my, my thought is our ORM code, the way that we wrote our ORM usage, I is pretty bad. basically the mistake that we made was, putting ORM code in our, like, domain logic, in the services, right, instead of having, like, a separate data access layer.

[00:42:11] **Adam:** And so now, yeah, and, well, I mean, so it's, it's partly our fault for doing that, and partly, Lucy, the, the, the platform, their fault for some bugs, in my opinion, that, that, the, the writers have no Um,but basically the problem is we, you know, when we started writing the ORM code, we were kind of new to it and naive and it was like, okay, this is great.

[00:42:36] **Adam:** You know, and it was like, everything looked like an ORM problem, right? Like that, that was our hammer. And so we've got all this like really complicated data access, like reading data out of the database to do stuff that looking back should have just been straight SQL queries. and because it's all interwoven into the application logic in the services, rather than being in a data layer, it is Not impossible, but way too much to ask to refactor that to be queries.

[00:43:08] **Adam:** And the reason it's a problem is because, if you are inside of an ORM transaction and you run a query, it's either that, or if you're there, they're way around, if you're running, if you are in like a, a declared transaction block, like try catch except instead of try, it's transaction. If you're in that and you're doing a SQL query and then you do ORM, it's, it's You know, either A or B, right?

[00:43:30] **Adam:** in terms of order. Yeah, you, if you mix them, it just like poops the bed. And, and it's, it's so infuriating because like, I don't want to be stuck with ORM, but because of how pervasive it is in our code, I feel stuck. And, and so we've kind of like, in some cases where it's a little bit easier to like bite off a chunk and just like fix this, we have like, okay, just rewrite this method all the way down through the stack.

[00:43:55] **Adam:** and everything it does, like only using query style. And so you'll, you'll see in our, in our services, it's like, you know, I don't know, like, like charge membership transaction, and then there's like a charge membership transaction, only queries, right? And so like in certain places, when we know we're, if, if it's, if from the start of the stack, if we know that we're going total ORM free, then we'll like call the one that's queries so that, you know, we, we don't mix them.

[00:44:22] **Carol:** Yeah,

[00:44:23] **Adam:** and so here's, yeah, I said, I had kind of figured out how I would fix it. And I think that the answer is like, start to build that data layer and just take these ORM things that are happening and move them down into the data layer, refactor them out and put them down in the data layer. And then once you've got all of that extracted out, then you can start changing the data layer itself to be queries, but still like

[00:44:44] **Carol:** that's costly.

[00:44:45] **Adam:** yeah, yeah.

[00:44:45] **Adam:** I mean, we're talking about, I don't know, somewhere between three and 5 million lines of code, and. Or a mixed wind with like all of that. So

[00:44:56] **Carol:** Feels like trying to change it all right when you're also trying to meet deadlines.

[00:45:00] **Adam:** exactly.

[00:45:01] **Carol:** Yeah,

[00:45:02] **Adam:** And the code is functional. It's just, you know, I've got performance issues and, and it's, it's holding us back. Yeah,

[00:45:14] **Carol:** where I decided to take where we had things written in actual readable, like, steps in the SOAR procedure. And I was like, I'm just going to table drive it. And every step is now a record in a database. And the record will be flagged as like, what the math should do.

[00:45:29] **Carol:** Like, is this an add step? Is this a, like, multiply? Well, then it turned into how the heck do you actually make updates to this down the road? Like, how do you maintain this? How do you teach someone, like, what was in

[00:45:42] **Tim:** That was you.

[00:45:43] **Carol:** was me. Like, I did that one. I was like, yeah. I actually just talked to a developer still working there about that, and he was changing something else to use it and was having, like, some questions and was a little, like, leery to do it.

[00:45:57] **Carol:** And my suggestion was, maybe don't do it then. Yeah. You might regret it later.

[00:46:04] **Tim:** Wow.

[00:46:05]

## [00:46:05] Reactivity

[00:46:05] **Adam:** So, you brought up Svelte and runes and signals and all that, and I just wanted to clarify that even now with Svelte 4, it has reactivity. Okay. but, it's, the way it's built in the compiler, it only looks for reactivity stuff in certain places, in certain files.

[00:46:25] **Ben:** the dollar sign expressions or

[00:46:27] **Adam:** Kind of, yeah.

[00:46:28] **Adam:** and, and the, the, the benefit of switching to signals and their implementation of signals is what they're calling runes. Which is basically just functions, special built in functions. Is that it will expand the surface area where you can put reactive code, which is really nice because like it's been kind of a pain in the butt to do things like When you want to have something reactive that's, like, extracted out into a service that can be shared in multiple places or something like that, it's been a little bit of a pain. That's all.

[00:46:59] **Ben:** Yeah. And I, and I totally think that there are ways that reactivity makes some things nice and easy, but I'm just. As with any kind of little sprinkle of magic, I feel like it can very easily get to the point where you're like, whoa, why did this value just change? And then you go to put something else and suddenly it stops changing or breaks or, you, all you want to do is put in a console log and there's like no good place to put that in.

[00:47:31] **Carol:** day.

[00:47:31] **Ben:** I don't know. So I think about, okay. I mean, just as a, as a case in point example, and I don't know if this is a bad example. So forgive me, just cut me some, some wiggle room here, some latitude, if you will.I think about driving a lot of application state based on the URL. So you can imagine coming to a data grid of some type and you have some filters, like keyword filters.

[00:47:59] **Ben:** And, like min price, max price, created by user filters, you know, transaction type filter. And as you're monkeying with those filters, let's say that what we want to do is actually change the URL, you know, put the transaction type, put the min price, put the max price into the URL, and then have the application update the data grid to reflect the changes in the URL.

[00:48:23] **Ben:** So my, my big concern, and again, maybe this is completely invalid, is that If the data grid has to be refiltered and resorted. Based on all of these values that are being pulled out of the URL, can you maybe too easily find yourself in a situation where, you actually pull five values out of the URL and each one of those indicates to the data grid computed value that the data grid has to be re sorted or re collated?

[00:48:57] **Ben:** And suddenly, one URL change actually re sorts and re collates the data grid five times in a row because of five variable changes. And again, I'm not saying that that's how it actually happens, but my concern would be depending on the order of operations, not quite understanding the magic can quickly lead to some weird performance and behavioral issues.

[00:49:20] **Adam:** So, yeah, I mean, you're absolutely right. When things get magical, that's where they can very easily and kind of secretly, I guess, for lack of a better word, kind of get out of hand without you realizing it's happening. And I will say that's one of the things that draws me to Svelte is that, the Svelte development team, but I think that they kind of inherited it from Rich Harris, the creator of Svelte, and he's still involved.

[00:49:44] **Adam:** But I think that, you know, Svelte does definitely have some magic in it. but, It's all, like, I have yet to see a time that they've ever done anything rashly. I'm ignoring the faces you're making at me, Tim.but, it seems like every time that they ever even touch a feature that's, like, magical in some way that's not, you know, you know, obvious, you know, Whatever.

[00:50:10] **Adam:** Anything that we would classify as magic, because it's indirect or something like that, it seems like they always take two weeks to consider it internally, and then they'll put up like her proposal online and ask for comments and, you know, they like, and these are the nine different variations we considered and implemented and tried and like, let them, you know, we used them, we used each one for two weeks and like, this is what we did like about it and this is what we didn't like about each one of them.

[00:50:33] **Adam:** And, you know, it's like, everything is very carefully considered. and, and I'm like, that just to me says they're, they're doing it right. And, and the, the end result has always been in my experience, something very, ergonomic and as a joy to use. Yeah,

[00:50:54] **Tim:** an observation here that I, I've seen.

## [00:50:57] From the Outside Looking In

[00:50:57] **Tim:** So one of the things, because it's a company that we're in and been bought by Constellation. We buy a lot of software companies and, you, you, you think, you know, you look at someone else's product.

[00:51:09] **Tim:** Like when they're a competitor, you're like, man, their code base must be so amazing. Right?

[00:51:14] **Ben:** For real.

[00:51:16] **Tim:** I mean, look, look how, I mean, they're not outselling us, like, like, you know, I mean, they can, they can ask for 2 million. We can only ask for 1. 5 million. They might, you know, their developers seem so cool.

[00:51:26] **Tim:** You know, it's like from the outside, you look at it, like other people's code seems amazing to you. And then, then you buy that company and now they're like, Now you're partners and buddies and you're talking and then you're like, so tell me about your code base. Like, oh dude, we're on Visual Basic still.

[00:51:45] **Tim:** We're still writing in Visual Basic and the code base is a mess. And you know, version control is a nightmare. And you're like, we're on Visual Basic? How are you beating us on video? I mean, like what's going on? So I just say that to say, it's like a lot of times when we're the outside looking at it, you just assume that other people's stuff that just, you know, seems to work most of the time is like, you're assuming they're all best practices, right?

[00:52:12] **Tim:** They're just doing everything right. And my code's a mess because I know the warts, right? And, just, just keep that in mind because everyone, I don't think I've ever met a developer who's like, yeah, we're a hundred percent best practices. All of our code is. And, perfect and everything's great.

[00:52:30] **Tim:** And I really don't see room for improvement and that's, I, that does not exist. And if they do, they're lying to you,

[00:52:37] **Ben:** Well, it feels very much like an example of the halo effect, which I think is one of the cognitive biases where you see someone do something well, or be physically very attractive, and it grants them this halo where you think they're actually really good at a bunch of other things. And it's like, just because a company is successful.

[00:52:58] **Ben:** You get this halo effect. All the people who work there must be brilliant. Or it's kind of like the Peter principle is almost a,

[00:53:06] **Tim:** in reverse.

[00:53:07] **Ben:** yeah. Or it's like, oh, someone can do something well. So they must be able to do that thing well at the next level and the next level and the next level.

[00:53:15] **Tim:** It's just, I think all of us feel like because we know our, our code so intimately that we can't praise it. And there's a lot of things that does right. Cause if it didn't work, wouldn't get a customer. And so it's like. Don't assume that other people are doing it the best way either. All of us are at different paths on our journey.

[00:53:40] **Carol:** I feel like I've said that numerous times when I was working on any application that wrote, that wrote ColdFusion. I was like, this is the worst language ever. I will never work on another application that touches it. However, when I stop using it, I go back to Man, I could just spin something up so fast in ColdFusion and it reads like English.

[00:54:03] **Carol:** Like, I can actually just follow what's happening. Things just work. The setup on my local is nothing. I don't have to do anything. It's just, I can run it and it's there. Like, look how magical this is. And then when I'm actually using it to write the application, I'm like, I hate everything about this.

[00:54:23] **Tim:** So the grass is greener where you water it.

[00:54:27] **Ben:** There is always something to me, very satisfying is not the right word. Validating, maybe when you hear in an interview, On a podcast or wherever, someone say something that is totally antithetical to like everything you've ever heard about best practices. And I wish I could remember who the heck this was, but I was listening to an interview.

[00:54:49] **Ben:** I mean, it's gotta be seven or eight years ago. So this is like at peak solid principles, clean code, like this is peak hype cycle for all that stuff. And this guy was being interviewed and he said, You know, sometimes I'll just write a method that's 300 lines of code long. And the interviewer was like, what?

[00:55:06] **Ben:** That's gotta be a nightmare. And he goes, no, no, I mean, 300 lines of code, it's all right there. Like you don't have to jump around. You don't have to deal with abstractions. It's all right there. And it's actually really easy to follow. And I just, I was, I was walking down a street in New York city. I think it was.

[00:55:23] **Ben:** Seventh Avenue. This is, this is the kind of impact it had on me at the time. Like I remember where I was when I heard it. I was like, Oh, bro, I feel that too. Sometimes long methods are amazing. So I think it's good to always have a variety of opinions so that we don't have too much of an echo chamber.

[00:55:41] **Carol:** Yeah, I agree. Diversity makes for great software.

[00:55:45] **Adam:** And to be self critical, right? Like look at your own code and go, yeah, that. It's working and I can't, I can't justify spending the time to change it, but if I had it to do over again, this is what I would do differently.

[00:55:58] **Ben:** Plus as you're incrementally improving an application, you can change the way that you do things. I I'm of two minds. Obviously I love consistency. I think everybody loves consistency. But I think sometimes we consistency for the sake of consistency. And if you come in and you're like, ah, it's not really working so great anymore, as long as introducing a new pattern doesn't increase in a substantial way, the cognitive load of the application, I think it's totally okay to start playing around with new patterns and paradigms if you think they're going to make things easier.

[00:56:38] **Ben:** Now that's not like. One pattern was monoliths and the next pattern is microservices. Like that's not, that's, that's a, you know, orders of magnitude or even just be like, Oh, you know, we used to do object oriented programming and now we're just all in on functional programming. Like that's probably not right either, but you could like, yeah, we have a lot of ORM in one area, in this other area where performance is a real consideration.

[00:57:02] **Ben:** Like maybe we just dip down and start writing raw SQL. Like all the tables are the same. We're just sort of changing the way we're approaching it. Like I'd be much more okay with that. If

[00:57:12] **Carol:** Were you listening to us when you took the dog out?

[00:57:15] **Ben:** no, sorry, I was, I was, I was a wrist deep in poo.

[00:57:21] **Carol:** Well, so is Adam with his ORM code.

[00:57:23] **Tim:** Oh,

[00:57:25] **Adam:** not wrong. All right. Well, that sounds like a good place to wrap it. I don't think we're going to top Wrist Deep in poo. So

## [00:57:35] Patreon

[00:57:35] **Adam:** this episode of Working Code is brought to you by TypeScript, telling you that your code is bad and listeners like you.

[00:57:39] **Ben:** Fact.

[00:57:41] **Adam:** And if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:57:47] **Adam:** Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them. Special thanks, of course, to our top patrons, Monte and Giancarlo.

## [00:57:54] Thanks For Listening!

[00:57:54] **Adam:** You guys rock.we are getting ready to go record our after show. It's just, we outro plays and we are going to keep talking and even we don't know what we're gonna talk about yet, but we'll, we'll figure it out when we get there.

[00:58:04] **Adam:** and if you want to help us out, you can go to patreon.com/workingcodepod. that's going to do it for us this week. We'll catch you next week. And until then,

[00:58:12] **Tim:** remember line 10, your heart matters. Line 20, go to line 10.
