---
title: "151: Async Human Solutions"
description: "When you build a system that is wholly contained within a single process, life is quite clean and predictable. But, the moment you reach outside of your process in order to get work done, you realize how messy the world is."
date: 2023-11-01
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/085f76d8-9061-4bce-abfe-54c018108ef4"></script><div class="redcirclePlayer-085f76d8-9061-4bce-abfe-54c018108ef4"></div>

When you build a system that is wholly contained within a single process, life is quite clean and predictable. But, the moment you reach outside of your process in order to get work done, you realize how messy the world is. Communication between systems can breakdown for any number of reasons. Often times, we try to create resiliency within the chaos by apply technology. But, sometimes, it makes more sense—and is far less expensive—to fix these problems using a human-oriented solution.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/151-async-human-solutions.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Ben:** And you can imagine a lot of newer people, and I would probably group myself even still in that group, where we focus on, okay, what's the technical solution? And then, you know, some gray beard in the corner is like, what if we just tell them to chill and like,

[00:00:14] **Ben:** have a drink,

[00:00:15] **Carol:** could you imagine putting like a sleep or a wait in your code that says like, try again in 24 hours? Like, that seems so wrong.

## [00:00:23] Intro

[00:00:23] **Adam:** Okay here we go, it is show number 151. And on today's show, we're gonna talk about how Ben is an async boy, and he's living in an async world.

[00:00:49] **Carol:** So fancy.

[00:00:52] **Adam:** but first, as usual, we'll start with our triumphs and fails, and Carol, why don't you lead us off?

## [00:00:57] Carol's Fail - No Place Like Home

[00:00:57] **Carol:** All right, I'm gonna start us off terribly. So I'm gonna call this a fail. it has hit me that I no longer, like, have a place that's home. Like it's more of like a feeling, it's just kind of some things around me, but I don't have home anymore. I'm only going to be here a few months. Then we're going to move.

[00:01:18] **Carol:** And then a year and a half later, we'll move again. And until we figure out where we put roots at, we don't have home. And I am missing what I would consider like home, which is the normalcies, my everyday life, knowing which grocery store carries the items I'm looking for and not having to go three places.

[00:01:38] **Carol:** just the daily routine, like this time zone sucks. It sucks for trying to contact my kids. Like it's great for some things, but for trying to communicate with people who still live on the East Coast, it's awful. It's so bad.

[00:01:52] **Tim:** The best coast.

[00:01:53] **Carol:** Yeah, yeah, I'm kind of going back to missing the East Coast. I said forever I wanted to leave the South, and I wanted to leave the East Coast, and now I'm thinking I might want to go back.

[00:02:04] **Carol:** But yeah, I just miss it. I'm sure I'll get settled in and things will be good, but... Right now, I'm pretty blue.

[00:02:11] **Tim:** No, sorry.

[00:02:12] **Carol:** Yeah,

[00:02:14] **Tim:** I mean, my wife has been here in this country 23 years since she came over from Sweden to marry me and she still is like, I want to go home. I'm like, what are you talking about?

[00:02:26] **Carol:** I get it. This isn't

[00:02:27] **Tim:** are you going to, where are you going to go? None of your family even lives in Sweden anymore.

[00:02:32] **Carol:** Yeah, I told my husband, I'm like, I just want my mom to hand me a plate of food. And I want it to be like cornbread, and collard greens, and a nice big fried pork chop. Things that just don't really exist in my world right now.

[00:02:47] **Tim:** have a taco.

[00:02:48] **Carol:** let's have a taco. It's so great here! All right, that's me. What about you, Tim?

## [00:02:53] Tim's Triumph - Competition

[00:02:53] **Tim:** So I mean, we, it was only a few days ago since we recorded last. I don't really have a whole lot of workplace stuff to talk about. Nothing, nothing shaking the world. So I'll go with something personal. So I think I've talked in the past about, when I was in high school, I did one act competition where it's, it's a, it's competitive theater, basically you.

[00:03:15] **Tim:** Put a, you do a one act play, you compete against other schools and they have judges and, I was in Pike County when I was growing up and, and Merry Persons always hosted the competition and Merry Persons always won, surprise, surprise, cause they had a lot of money in their, they weren't a private school, but I guess they got some sort of, you know, someone donated them a huge amount of money cause they have like fantastic theater and like just rooms full of costumes and I mean, just really, and we, we basically had a little stage and.

[00:03:44] **Tim:** Yeah, that was about it in 50 bucks. but my daughter has been doing it for the past three years in high school. And, so that today it was actually today, this morning, she left to go up there to compete against Merry Persons and all the other schools. And I think there was probably like 10 schools and out of all of them, they play second for their one act play,

[00:04:04] **Carol:** Oh, wow. Congratulations!

[00:04:07] **Tim:** They were doing a 25th annual Putnam County Spelling Bee. And she was one of the, you know, spellers and they did really well. They got best set design and then they had two actors on their team kind of called out for, for excellence. So

[00:04:24] **Adam:** Wait, their, their play that they put on was a spelling bee?

[00:04:28] **Tim:** Yeah. It's a play about a spelling bee. Yeah. It's a play

[00:04:30] **Adam:** I just wanted to clarify, that was a little confusing.

[00:04:33] **Ben:** glad that your kids are continuing to overachieve. That's very nice.

[00:04:37] **Tim:** Yeah, yeah,

[00:04:37] **Adam:** Gotta, gotta keep those coattails there for Tim.

[00:04:40] **Tim:** I mean, the, the, the main thing though, I was like, I, I'm like, just beat Merry Persons, whatever you do. And of course, Merry Persons put on Fiddler on the Roof and it was, and it was like, my daughter's like, it was flawless. She said, I would go pay money to see them do it again. So they got first place.

[00:04:56] **Tim:** So, but anyway, they, they did really well. I'm super proud of all those kids. They worked super hard on it. They were, you know, doing rehearsals every day after school. Until like five, five 30. And then sometimes on the weekends on Saturday and Sunday, and just put a whole lot of time into it. They did fantastic.

[00:05:14] **Adam:** Cool. Well, good for them.

[00:05:16] **Tim:** That's me. How about you, Adam?

## [00:05:17] Adam's Fail - Down in the Dumps

[00:05:17] **Adam:** I'm gonna go with a fail. I've just been, I think the, the word that I remember Ben using for this back in the day here on the podcast was Logie. I'm just not feeling, I'm just like, kinda down in the dumps, you know, no, no good reason, just like, nothing seems positive, you know, I'm doing work, but it doesn't make me hyped, which is sad, right, like, I, I, there are so many days when I'm just like, super excited about work from the moment that I sit down at my desk until the moment at 5 o'clock that I realize I completely missed lunch, you And you know, like that kind of day where you're just like on all day and cranking out the code, I miss those days.

[00:05:57] **Adam:** Cause it feels like it's been a while since I've had one. I'm just kind of like, blah. I mean, as Tim mentioned, we've had kind of a short week, so we haven't had a whole lot going on. And I was also, I guess I should mention, when we last recorded it was the day before my foot surgery. I am now post op and I survived, and I weigh slightly less now.

[00:06:17] **Adam:** they took some, some tissue from my foot.

[00:06:20] **Ben:** But do you have any cadaver tissue now?

[00:06:23] **Ben:** I don't know for sure. I didn't get to talk to the surgeon post surgery, but I'll talk to him tomorrow. Until then, we'll just have to monitor for mood changes and erratic behavior.

[00:06:35] **Carol:** Or was it, wasn't pig an option?

[00:06:38] **Adam:** It was. Yeah, so I, I have a feeling that, uh, today's episode might be brought to you by brains, but we'll see.

[00:06:45] **Tim:** I was about to say, are you craving brains?

[00:06:48] **Adam:** Yeah, I don't know. So I've been walking around in this, I don't know if orthotic is the right word, but you know, the, it's like, I had, when he said you'll have to wear a boot after the surgery, I pictured that like, gigantic, like, almost all the way up to the knee, plastic, like, boot, That were like, you know, it's got like six velcro straps around your leg or whatever.

[00:07:05] **Adam:** That's kind of what I envisioned. I come out and they're like, here you go. And they hand it to me and it's like a shoe with a, with a three or four inch thick heel. It's all like kind of a hard foam. And then it's just like a little bit of like a foam sides and some velcro to go over the top. It's like, I, it

[00:07:21] **Tim:** is so hot right now.

[00:07:25] **Adam:** feels like, If you ask, like, a clown to design a medical shoe, or if you ask a doctor to design a clown shoe, right, like, they're, it feels very weird and whatever, but, like, I don't know, whatever, things are going well with

[00:07:40] **Tim:** I think everybody be wearing them soon.

[00:07:43] **Adam:** maybe, what really sucks is that, you know, I'm supposed to wear it pretty much constantly, and the difference in like I said, it's like a, probably at least three inch thick sole, and then on my other foot I'm wearing like my slippers, which is like almost nothing, right?

[00:07:58] **Adam:** Like maybe a half inch at most, including all the padding. Um, and so like, I'm, I'm kind of standing, you know, like catty wampus, my, got one shoulder higher than the other, just, like, I, when I'm standing there brushing my teeth, I feel weird. I'm like looking in the mirror, I'm like, what is wrong?

[00:08:16] **Ben:** You know, you need is a Philly's win. I think that will

[00:08:19] **Adam:** Yeah, please, can we? So, I mean, as we're recording this tonight, it's gonna be a little anachronistic for listeners, but, hopefully, the Phillies will clinch their spot in the World Series tonight, and, and we are, I appreciate you guys recording a little early tonight so that I can catch the beginning of the game.

[00:08:37] **Ben:** Absolutely.

[00:08:39] **Adam:** Well, I'm all decked out, I got my Phillies hat on, I got my Phillies jersey on, got my Phillies sweatpants on. I don't actually have Phillies sweatpants, but...

[00:08:46] **Ben:** in the show, it's always sunny in Philadelphia. There's that green character that Charlie is always doing where he's dressed in the night. And is that, is that a real character that, that comes out to games or, okay. I didn't know if that was

[00:08:57] **Adam:** That's a, that is a Charlie Day character. yeah, no, it's like, it's a, it's his alter ego that he brings out for the, the show every once in a while. It's like a, it's a, it's a character on the show, but it's, it's funny. So, I guess that's about it for me. Just feeling blah. I need a vacation.

[00:09:15] **Adam:** Feeling, I guess the word is logie. how about you, Ben?

## [00:09:18] Ben's Triumph - Async Human Solutions

[00:09:18] **Ben:** I'm going to go with the triumph, but it is not my triumph. It was an experiential triumph. So I ordered something on Amazon, like on Friday or Saturday, and it said it'll arrive on Monday, which at the time of this recording is yesterday. and then Monday rolls around and I get an alert from Amazon, your package is out for delivery, it should arrive by 9pm tonight.

[00:09:42] **Ben:** So 9 p. m. rolls around and nothing is there and then at 9 30, I get an alert that the package has been delivered. So I take the dog out, I go out in my, in my boxers, which is just a nice thing that I can do since there's nobody around. And, I just walk around to the garage, I look around the porch, nothing is there. So in the morning I was tired, so I went to sleep and in the morning I wake up and I go to my Amazon dashboard and I log into my orders. And it still says that the order was delivered the night before. And so I go to open up a support ticket to say that it wasn't actually delivered. And one of the options that they have is we said it was delivered, but nothing showed up.

[00:10:22] **Ben:** So I clicked on that and it has some text that says, try checking in the bushes and around the porch. If not,

[00:10:30] **Tim:** Did you look or did you man look?

[00:10:33] **Ben:** it says,

[00:10:34] **Adam:** Honey, where's my package?

[00:10:38] **Ben:** says, if, if not orders tend to, it's the language is funny. It's like orders tend to be found within 24 hours of the delivery day, which I just thought was a strange way to phrase it.

[00:10:49] **Tim:** They're not blaming you, but they're blaming you is what they're doing there.

[00:10:52] **Adam:** Mm mm.

[00:10:53] **Ben:** So I'm like, okay, I'm going to let it go. And then finally, so that was, that was a Monday morning. or that was, that was Monday. It hadn't showed up. So then Tuesday I checked and today is Tuesday at the time it's recording. And then it showed up finally around like two o'clock this afternoon. And, and, I just thought it was a really great example of the way that the world is very messy.

[00:11:16] **Ben:** You know, Amazon sending out this package. And it's getting delivered by USPS, the United States Postal Service. So they don't really have any control once it leaves their factory or, you know, their distribution center and USPS marked it as delivered. And again, Amazon just, they can't do anything about that.

[00:11:33] **Ben:** They can't argue with the fact that the USPS is marking this as delivered. So instead of just believing that all the data is correct and all the world is always synchronous and, and up to date. They address it with language and the language that they have on their support page, again, is that, Oh yeah, even if it says it delivered, it should show up within 24 hours.

[00:11:54] **Ben:** And I just thought that that was a great example of. Solving the right problem with the right solution. Meaning instead of trying to, you know, spend weeks investigating the USPS API and opening support tickets with the postal service to try and figure out why something wasn't delivered when it said it was delivered, they said, you know what, we're just going to solve that with words and it's not going to be a technical solution, it's going to be a human solution and the world is going to go on.

[00:12:21] **Ben:** And, I just wish that I had a better instinct about when to lean into solutions like that. I think because of the way that I work, which is generally more of a monolithic architecture where you send in data to the database and it better be saved, I don't wanna have to argue about that. Uh, I, I don't have a kind of backlog of experiences and patterns that I can use to say, Hey.

[00:12:47] **Ben:** This may or may not work and it'll probably work most of the time. And if it doesn't work most of the time, maybe the right solution is not a technology one, but you know, we're just going to accept the fact that maybe some support tickets get open and that's going to be fine. And that's never a problem we have to solve. So

[00:13:02] **Adam:** Yeah, it strikes me as, very similar in some ways to a thought that I had and shared with my team today, which was that Starting a business is much more interesting and exciting than running a business.

[00:13:18] **Ben:** yes.

[00:13:19] **Adam:** You know, like when you're, when you're starting a business, you just like, okay, got some ideas and test some stuff out and sell it to people, get some sales, you know, work out their early kinks.

[00:13:29] **Adam:** But like running a business, now you're 10, 15, 20 years into this. got stuff, you know, you got commitments, you got bugs that are gonna pop up, you got, you know, wear and tear on your equipment, stuff just like, it's never ending and then you're also supposed to continue to be productive and somehow this is supposed to be, enjoyable.

[00:13:48] **Adam:** It's like, it, it occurred to me the other day, I was like, man, I, I very much right now do not have a job, right? Like, even though I, I do just kind of have a job, I could just quit and go work somewhere else, whatever, but, like, the, the sort of, emotional investment that I have to my position is very much, like, sort of semi, you know, founder level, right?

[00:14:13] **Adam:** So, like, I, I'm invested, I'm personally, emotionally invested in making this business work, and so, like, when stuff is, Not working. I don't feel like I have that freedom to just be like, you know what, this job sucks, it, I'm out, right? Like, I want to see it through, I want to make it work. And it's hard.

[00:14:31] **Adam:** It's hard work.

[00:14:33] **Tim:** trying to think if I can think of an example, something in our business that's similar

[00:14:37] **Ben:** Well, you were just talking the other day about how, when you're doing transactions. And Rogue sends Carol some stuff and Carol's credit card pays for it. Like, that doesn't necessarily get I don't know what the right word is, but like all the

[00:14:50] **Tim:** none of that, none of that's synchronous, that's for sure.

[00:14:53] **Ben:** Right. And, and, but there it's so obvious, that I assume all the people who are building systems like this, they, they plan for that, but I think there's so many little subtle things that, I don't know.

[00:15:06] **Adam:** Eventually consistent.

## [00:15:08] Async in Payments

[00:15:08] **Tim:** Yeah, actually, I just thought of one. so, you know, because we're the payment processor, we're the ones in the middle for, you know, someone else's software. We don't necessarily, so you have the act of taking the money, right? And that's what we do. We put the card information in on our, our, our technology.

[00:15:26] **Tim:** We talk to whatever. You know, back end processors, we need to. And then we tell another piece of software, the API or, you know, some monolith or something and say, Hey, this is, this was approved. Here's the approval information. You go do your stuff to update your financials to know that that was paid, right?

[00:15:47] **Tim:** 99 percent of the time they say, yep, got it. And they apply it. And then that 1 percent of the time. They, they get it and for some reason they're like, Oh, I, I, I, I, it's for some reason they don't apply it. So a person looks and he goes, well, I paid this. Why doesn't my, why doesn't my, you know, invoice reflects this, my insurance.

[00:16:09] **Tim:** I paid it today at 9am. It's not showing up. So rather than trying to fix that, because it's like, there could be so many reasons why that doesn't apply. And I'm not in control of that. It's not my software, right? It's not my software's fault. they, they didn't do it. So what we do is just have an audit routine that runs through and says, we sent you 5, 000 payments today.

[00:16:30] **Tim:** Do you have this one? And we have a thing that we can go query and say, yep, we got it. You know, here's the approval code. Okay, good. And just marked it off. And then for like the 1 percent that didn't get through, we say, we have a manual process. Like we have customer service people that go and check it and go, yep, it's not there.

[00:16:47] **Tim:** They, they have a way to manually apply it. And so it's not instantaneous, but it's close enough, right? So if you make a payment in the morning and then in the afternoon payment shows up. You're like, okay, I still got insurance. So that was a, but that's a business decision, right? That was, you know, a developer, you know, a developer themselves can't make that decision.

[00:17:07] **Tim:** Someone higher up has to say, you know, it's okay if it's not immediate, we can wait a few hours and apply this and it's not the end of the world, but you need someone whose job just isn't all technically focused because otherwise they're just gonna drive themselves crazy trying to figure out how to do it.

[00:17:23] **Tim:** When it's. Not even within their realm of control,

[00:17:26] **Ben:** That, that's a great point in terms of who can even make these decisions, because I think. You can go down so many deep rabbit holes trying to build crazy resiliency into an asynchronous process that it can be very expensive. On a previous episode, Adam and I were talking about building resiliency and we're talking about the, the level of nines, the availability that there's like three nines availability, four nines, five nines, which is the percentage of uptime you commit to having in your service level agreements.

[00:17:57] **Ben:** And each one of those nines adds an extraordinary amount of cost. if you go from four nines to five nines, like super expensive, and five nines to six nines, like only Google can pay for that kind of stuff. You know, in order to know where to cut corners, I think engineers oftentimes don't feel comfortable or don't know that they have permission to even do things like that.

## [00:18:19] Who Can Make the Decision?

[00:18:19] **Tim:** Yeah. I think developers, engineers, we tend to think it has to be perfect, right? Well, that's what, that's the goal, right? Mentally. But it's like, that's just not how things are sometimes. Sometimes perfect's impossible or, or good enough is good enough.

[00:18:34] **Ben:** I keep thinking about thumbnailing images, that keeps popping into my mind because that's something that we have to do at work a lot. And thumbnailing images is one of those things where it probably is going to work pretty well in 99. 99 percent of cases. But then for whatever reason, maybe, there's a file IO issue, or if you're storing to S3, maybe Amazon throws an error.

[00:18:54] **Ben:** And suddenly your thumbnail is broken or, you know, it goes to request the thumbnail file, but it hasn't been generated yet. And you're showing a broken image on the client. And, it's like you could build in a very robust process that keeps trying to generate a thumbnail over and over again, or queues it up and does something very clever, or you could just say, you know, when the user reuploads that image, the thumbnail will get generated and that'll just fix it.

[00:19:18] **Ben:** And that's okay. but it's. That's like a whole product question. Is it okay to have a broken thumbnail for some period of time? Is it okay to ask a user to re upload their file in order to regenerate the thumbnail? And that's not something that the engineer can necessarily just make in isolation, but they don't necessarily know that it's something they can even bring up.

[00:19:40] **Adam:** I mean, that to me sounds like the perfect reason to have like a product owner or product manager sort of thing. That's the type of person that you would expect to be able to have that strategic, mental model for the application, right? Is this an app where... We need that thumbnail and I need you to re try it 50 times or, or, is it okay to just be like, hey, your thing broke, can you re upload it?

[00:20:04] **Adam:** And that speaks, I think, to the, the whole way you kicked this off with the Amazon, you know, you probably just didn't notice that it was six inches to the left of where you were looking. Right, in their help text, I think you're absolutely right that like, you know, what they did was they saw, okay, we have this problem, you know, N percent of our support tickets are people calling to say, you said my package was delivered, but I don't see it, and it actually either already was there or, you know, USPS reported it's delivered two hours too early or something like that.

[00:20:41] **Adam:** I don't know. And they like, they, they recognize that that's a self fixing problem for, for the vast majority of those tickets. And so they were like, really, what we need is some way to convince the user that it will fix itself. Right? So that language there, that helps with that. And then it's like, okay, well, if it's still not fixed in 24 hours, then please let us know.

[00:21:00] **Adam:** We want to make it right. But, you know, like, and doing it in a way that's not like, you're an idiot. You didn't look in the right place, you know. the, emotional intelligence of that prompt that you were talking about, I think, is, very high. And I think that this, go ahead.

[00:21:16] **Ben:** was just going to say, I think, I think it is high. And I think this kind of differentiation between approaches to solutions is what separates, you know, maybe a very experienced, I don't want to say engineer, cause I think this, you know, these ideas could come from anyone in the stack, but someone who is new and is more focused on correctness.

[00:21:37] **Ben:** And someone who is maybe more experienced and is more focused on product outcome. Maybe, I don't know if product outcome is a good comparison to correctness, but you could imagine that someone's like, hey, team, you know, we're getting 400 tickets opened a month for people who are saying, That their package isn't there, and we told them it's there.

[00:21:57] **Ben:** And you can imagine a lot of newer people, and I would probably group myself even still in that group, where we focus on, okay, what's the technical solution? And then, you know, some gray beard in the corner is like, what if we just tell them to chill and like,

[00:22:11] **Ben:** have a drink,

[00:22:12] **Carol:** could you imagine putting like a sleep or a wait in your code that says like, try again in 24 hours? Like, that seems so wrong. It's not there right

[00:22:22] **Ben:** so wrong, but I think it ends up being totally the right approach in this context.

[00:22:28] **Tim:** This is a small kind of piddly example, but so whatever you're calculating, like The, the percentage, like you're doing a percentage fee on, on what you're going to charge the customer for processing a payment. So the merchant who's, you know, the company that's taking credit cards, they're getting charged a certain percentage, right?

[00:22:48] **Tim:** Usually around 3 percent or 2. 75 percent or whatever. And sometimes those percentage numbers kind of go out a little further. And... We have a, it's always the small customers. The big customers for some reason are like, ah, it is what it is. But like the little guys, they're like, they have, they had like 200 transactions for, for the month or actually the day.

[00:23:08] **Tim:** And, so we show them, here's how much you charge the customer. Here's the, you know, we do the percentage calculation and say, here's the fee that you're going to pay for it. And, and then, you know, here's what's left over. And. So we've shown it for each line item, but at the actual processor level, they don't do an individual line item.

[00:23:28] **Tim:** You know, they don't do each chart transaction. They'll just do it on an entire batch of payments, apply that percentage and charge them. And depending on how that goes, I mean, sometimes you're off by a penny up or down, it's always only a penny because just, you know, moving the decimal point and, you know, rounding and things like that, where you round to that, and, that, that just drove that customer nuts. And they're

[00:23:51] **Carol:** penny off?

[00:23:52] **Carol:** The Penny

[00:23:52] **Tim:** off. Yeah. They're like, well, you said, you said, you know, we're, you know, we're gonna pay, you know, $700 in fees, $700 and 3 cents, and, but actually the, this report here that you sent us, it says it was 702, so where's the penny? You know what's it's like so eventually

[00:24:09] **Adam:** you got a one cent discount.

[00:24:10] **Tim:** right?

[00:24:11] **Tim:** Well, yeah, some, but sometimes it was up, sometimes it was down. And so to illustrate to them how ridiculous worrying about this was, we said, we'll, tell you what we'll do. We'll track the over and under each and every day, and then at the end of the month, if there's a credit. Well, you know, 30 cents credit.

[00:24:27] **Tim:** We'll, we'll pay you that credit. We'll give you that credit back, or if it's charged, we'll bill you. The 30 cents. And when you put it in that perspective, like, they're like, I guess it's really not worth it. I'm like, thank you. First, they were like, fix the report. We're like, it's not a report problem.

[00:24:42] **Tim:** It's like, you're wanting to see each individual transaction, what your charge is, we're getting close, but it's like, but that's not actually how it's calculated. It's on the whole batch.

[00:24:53] **Tim:** I wonder if you could have, used a more precise number, right? Instead of saying, for this charge, you're gonna be, you are going to be charged a fee of, you know, a dollar and seventeen cents. If you could have said a dollar sixteen and, you know, Yeah,

[00:25:07] **Adam:** 1. 164321942, right? Like, if that

[00:25:10] **Tim:** I don't know. I spent, I spent two weeks trying to get that, those numbers right. And I even talked to the processor and they're like. They're like, yeah, this isn't going to happen and it's not worth it. So,

[00:25:22] **Adam:** Yeah, for sure.

[00:25:23] **Ben:** when you're talking about payments, another thing pops in my mind. I was listening to an interview maybe like two years ago, so I don't remember exactly what the context was, but there was a company that was accepting online payments, you know, some sort of e commerce system or service system.

[00:25:38] **Ben:** I can't remember what, and, and they made a decision at one point that because the upstream services, the payment gateways are not necessarily available all the time, they're just going to accept every single order that comes through. Like they won't say that you're, you know, that your order is complete.

[00:25:53] **Ben:** They'll say, we've accepted your order. Then they'll process the charge in the background. And if the charge doesn't go through, then they just send an email saying, Hey, we couldn't charge your credit card. Yeah, we couldn't charge your credit card. Click here to update your card details. And, again, just another thing, the world is messy, things don't always work out, and we just have to have an asynchronous process in place that reconciles systems.

[00:26:16] **Carol:** So, today, I ordered my niece's birthday presents from Hot Topic, because, you know, that's where all teenage girls shop at, and, I tried paying with Apple Pay, just like doing it on my phone, and I don't know if it's because our address was changed or whatever, it, Hot Topic returned back immediately, like, oh.

[00:26:35] **Carol:** We couldn't process this. We couldn't process this. We couldn't process this. So then I just go, okay, I'll do type in my credit card number myself. So I did that. I look at my credit card. There are four transactions to Hot Topic pending.

[00:26:49] **Tim:** uh,

[00:26:50] **Carol:** So I think the, the failure wasn't in the credit card. It was somewhere on their sides.

[00:26:55] **Carol:** I mean, they let me know they couldn't process it. But they still have four pending out there, but I just assumed it was an issue with Apple Wallet.

[00:27:04] **Adam:** I had a very similar thing. I was buying some skydiving equipment from, skydiving equipment, yeah, from Hot Topic. And... I had, you know, they have like a rewards point thing, right? So you get like a point for every dollar you spend and then you can cash in those points for, you know, one point is one cent or something on your future orders. And I had like, you know, three dollars worth of points. I was like, whatever, I'll just, you know, it'll cover the tax or something.

[00:27:30] **Adam:** And it, I think that whatever there, there were, their system for tracking usage of those points was messing up because like, I, I ordered hundreds of dollars worth of equipment, like four times. Always just trying to use that stupid 3 discount.

[00:27:46] **Carol:** Yep.

[00:27:47] **Adam:** and, and finally I was like, you know what? I bet you this is what's breaking it.

[00:27:50] **Adam:** Let me just put in the order without. and, and of course that one worked. I'm like, okay, well, you know, whatever. No big deal. And then I look at my credit card like the next day and there's four charges. I'm like, that's not gonna, I don't need four helmets to show up at my house. Like, let me email them real quick.

[00:28:07] **Tim:** Oh,

[00:28:08] **Ben:** Let me, let me, Tim, let me ask you a question, because this is something you might have some insight into. So... I noticed that I make purchases through Apple. Like I pay for my Hulu subscription through Apple, and then I'll rent movies through Apple. And I get a number of charges from Apple every month. But what I noticed is that they appear to sort of chunk charges together.

[00:28:29] **Ben:** So they won't necessarily charge me for Hulu separately from a movie rental. They'll defer charging me for a movie rental, like two weeks. And then when my Hulu subscription is up for renewal, they'll charge me for both of the Hulu. And the movie rental. And is that, is that some sort of technique to get like lower some charge overage cost or something?

[00:28:52] **Adam:** fees or something.

[00:28:53] **Ben:** Yeah.

[00:28:54] **Tim:** maybe because so on the, on the backend, it depends on how they're, they're paying, Their processes. So sometimes you'll have a flat percentage and if they do that, then it really wouldn't matter because the percentage of the total is going to be very similar to the, within a penny of, doing it individually, but sometimes there's, it's a percentage plus, an

[00:29:14] **Tim:** amount, right?

[00:29:15] **Tim:** So it could be a percentage,

[00:29:16] **Tim:** a percentage plus, you know, 10 percent plus 10 cents or 5 cents or whatever. And so they might do roll those up into one transaction so that. They're saving 5 cents. And then on the scale they're doing stuff. I mean, that can probably add up.

[00:29:32] **Ben:** It's so crazy to think about scale. Sorry. Go

[00:29:35] **Carol:** The other, I was gonna say, no, the other thing I had saw with that was there was a lot of issue with cards starting to reject transactions because the same amounts were being charged over and over again for things like in app purchases. And when you were doing games and it was a lot easier for Apple and other providers to be like, Oh, well, here's an email that says we charge you 23.

[00:29:55] **Carol:** And here are the 10 things you bought versus 199, 199. Cause people would be like, I didn't charge that 199, but I charged the other 199. So it, it made their fraud levels go down as well.

[00:30:09] **Adam:** And I'm sure, like,

[00:30:09] **Tim:** Mm-Hmm.

[00:30:10] **Adam:** I bet you too, like, you're just saying if I got 6199 charges on my thing and, on my credit card and, you know, I knew that four of them were real, but the two weren't like, then I'm going to have to like jump through a whole bunch of hoops and do a whole bunch of crap just to deal with some chargebacks on 4 worth of charges.

[00:30:29] **Adam:** And I'm sure I don't want to do it. Apple doesn't want to do it. So by like bundling, just, it makes the whole process like. I guess easier or,

[00:30:37] **Carol:** yeah, it seems easier to maintain for everybody.

[00:30:40] **Adam:** bundles the overhead in as well, right? Like instead of spreading it out across,

[00:30:44] **Tim:** And it could be how their accounting is done. They could roll things into like a monthly invoice. You just kind of have an open account. You charge whatever you want to that account. Then they make the account good for you at a certain point in the month. Right. So everything's on that, that rolling in monthly invoice.

[00:30:58] **Adam:** you got to give your, your credit card to Apple for incidentals in case you use the app store minibar

## [00:31:04] Ticket Reservation

[00:31:04] **Tim:** Right. Exactly. I think today there was an example of this in my, in my purchasing life today. So, at DragonCon, they have what they call, we call the hotel hunger games. And it's, it's so it's like, there, there's certain they'll announce in advance when the rooms, the hotel rooms for the, for the official hotels are going to be opened.

[00:31:27] **Tim:** And so, Marriott Marquis already did theirs in, one of the other hotels. I forget which of the, but anyway,

[00:31:34] **Adam:** you're talking about for next year

[00:31:36] **Tim:** for next year

[00:31:36] **Tim:** Oh yeah, yeah. This is for next year. You have to be, you have to like really prepare because it's like, it sells out so fast. So we already have our tickets for next year, but the Westin, which is like the hotel we'd like to go to, the Westin Peachtree Atlanta, today was theirs.

[00:31:50] **Tim:** That was the last one with the Hunger Games. And, so they, in previous things, you would basically go to their, the, the hotel website and just hit refresh as much as you could until you got in. It would crash. Marriott Marquis had this terrible thing, this thing where people were being asked for, please enter your passkey.

[00:32:09] **Tim:** And I was like, I don't know what, what, what do you want? There's like some sort of password and no one could figure it out. And people spent like four or five hours of their morning trying to get a hotel room. Well, Weston did something different. It's still passkey, which is a reservation system. What they did is they gave you a link.

[00:32:29] **Tim:** Everyone gets the same link. You go to that link and it puts you in a queue. So 10 a. m. is when the block opens to get rooms. I get it up at 930 and, you know, make sure I was up and there, got my coffee ready. 930, I go there and it gives me a GUID. And no matter how much I refresh the page or whatever, the GUID stays the same.

[00:32:46] **Tim:** And they say, you, you will be, when it opens at 10 a. m. Eastern time, you'll randomly be put in the queue. And so I'm like, all right, let me increase my chances. So I'm opening IE, Explorer. I've got Brave open and I've got Chrome open. I've got three different ones open and I'm refreshing in. I got a different GUID each time, GUID on each browser.

[00:33:07] **Tim:** So I'm like, okay, I'm set. So 10 a. m. rolls around. One of my browsers within 30 seconds pops up and says, make a reservation.

[00:33:14] **Carol:** Yay.

[00:33:16] **Tim:** So I got a room. That's the great thing. But the other ones I'm like, I just want to see, so I'm sitting there like. 12 minutes on one of the browsers, I think it was Brave, and I finally get in, and it says there's 3, 000 people in front of you.

[00:33:28] **Carol:** boy.

[00:33:30] **Tim:** And so by the time I actually got around to making a resume, all the other ones, they were all gone. And so, that, but, At least, I mean, normally the, the booking process would take several hours of frustration. This, you know, within, within a few minutes, actually, I had one, but it's like, even at the worst, it was only like within 10, 15 minutes people were doing it.

[00:33:50] **Tim:** So it was this, this asynchronous process, but they made it synchronous by basically putting everyone in a virtual queue.

[00:33:57] **Tim:** And then they

[00:33:58] **Carol:** Limiting the numbers. Yeah.

[00:34:00] **Tim:** Yeah. They're like, you have, once you get in, you have, we'll reserve it. We'll hold a room for you. We'll hold you a spot, but you have 10 minutes after 10 minutes.

[00:34:06] **Tim:** If you haven't purchased a room, there's no chance that the virtual room that we're holding for you is gone. So

[00:34:13] **Ben:** that is such a good solution. I like it's that's so clever. It makes me almost angry because I feel like I would have never come up with something like that. But that's just so I think about a ticket master, you know, and how people always complain about. who's that, who's that woman that everyone loves now?

[00:34:28] **Ben:** Uh, Taylor Swift. Yeah. Like Taylor Swift concert

[00:34:31] **Tim:** Travis Kelsey's girlfriend, girlfriend.

[00:34:34] **Adam:** Yeah,

[00:34:34] **Ben:** Taylor Swift tickets, they'll go on sale and will be sold out in, in like 30 seconds and, and like half of the tickets have been bought by scalpers that are operating bots kind of things. But if you put everyone into a queue and then just randomly sort the queue, when it comes time to purchasing, I don't know, it just seems so clever.

[00:34:55] **Tim:** I mean, it feels clever if you got a room,

[00:34:57] **Carol:** Yeah. Right.

[00:34:58] **Tim:** the other people, the other people who didn't get what they're like, this sucks, I hate this.

[00:35:02] **Ben:** But just think about it. It's, it's like. Equally unfair to everybody in a way that makes it fair. So it's, it's, you know, it's not that, you know, Oh, your bots were better at solving the CAPTCHA fast. So now you were able to buy 27 tickets. It's a, you know, whether or not your bots are any good, you get put in the queue, just like everyone else. I don't know. I'm just, I just think that's a really clever idea. And I'm going to put it in my back pocket for, you know, when I have people sign up for my bake sale.

## [00:35:30] Real World Side Effects

[00:35:30] **Adam:** that's been kind of going through my head as we've been having this conversation is like, I've noticed a, an evolution or a maturing maybe is a better explanation for it of like the type of applications that I've been building throughout my career. And I don't, I don't know if this is, The, the mature, the maturation of my career itself or of like the things that we're doing with the internet, like maybe the internet itself is maturing or, or maybe it's something else entirely.

[00:36:00] **Adam:** But like, you know, when I first started out, I, my, my personal opinion was like, I don't care about UI. I don't care about this or that. All I want to do is like forms and database queries, right? Like I'll, I will. Create a form, and I'll let you post it, and I'll save that data to the database, and then I'll make some HTML reports from it.

[00:36:20] **Adam:** And that's, that's my bread and butter, and let the designers be designers. and, that is, that's an incredibly boring thing. I was really good at it, which is why I felt like drawn to it. but it's an incredibly, like, can you imagine doing that for 20 years? That would, God, that would suck. but like, but so that's the, like, the minimum useful thing that an application can do is like data collection and reporting, right?

[00:36:47] **Adam:** And then as, as you start to interact with the real world, right? Like as the internet matures. And it evolves. We are, we are having side effects in the real world and we need to be affected by things in the real world. So just to throw out one example that comes to mind from an earlier conversation, you know, like lambda step functions.

[00:37:10] **Adam:** Right, you can use those and it's like the, the kind of like totally async, I've never used them, but from my understanding it's like, you know, you can just say like, when these conditions are met, then you run the next function in the, in the chain here. And the condition might be like, you know, for, I think, What I heard was that Uber uses this when like signing up new drivers, right?

[00:37:31] **Adam:** So when you sign up as a Uber driver, you have to go through the training, you have to get your, your equipment, you maybe have to find, you have to like submit information about your car. I'm sure there's like 5, 6, 20 different things you have to do, whatever. And so each of these things like is a, is checking something off on a checklist.

[00:37:49] **Adam:** And when you get to, you get to certain like gates through that process or, you know, when these five things are done, then you can move that ball a little bit farther forward. Right, until eventually you were like, okay, you can go be an Uber driver, go. and I feel like that, that interaction with the real world increasingly requires this.

[00:38:10] **Adam:** Async mentality that we're talking about here, right? Like it's, there is no instantaneous, consistency, right? Like we're talking about with the, you've got the monolith application, you get some, somebody submits a form, you got the data, you write the data to the thing. You can spit out a PDF, you can send an email, whatever, but like none of those things have immediate and, and interesting side effects in the real world.

[00:38:35] **Adam:** And I, like, I feel like there's a parallel here between async and. Interesting side effects in the real world.

[00:38:44] **Ben:** Well, I do think that you are right in that there's a maturation of the things we're doing and, and, you know, so much of what we've talked about already involves payment processing and payment processing has been around forever. It's the dawn of exchanging of goods. So it's almost no wonder that it seems that everyone who processes payments has this stuff down to a T or at least is trying to, but as we're coming into more of a digital age and there's all kinds of new types of interactions and, and the, the amount of functionality that we can have in any process, I mean, you're just talking about, you know, running background checks and having to supply technical information.

[00:39:25] **Ben:** ShipEquipment, like that's just, those workflows probably didn't exist before and now they do. And now we're trying to come up with interesting ways to solve those problems. So I think, I think there is definitely an evolution and a maturation of how we're thinking and doing things.

[00:39:40] **Adam:** Yeah, and at the end of the day, it's all just, it's state machines all the way down.

[00:39:45] **Tim:** Yeah, I was about to say something very similar. That was the, you know, Bitcoin and, and, and blockchain and all that stuff was interesting. One of the things I thought was interesting was the whole promise. And maybe one day that we'll be there, but the whole promise of like, they called them smart contracts where basically, particularly like in the insurance world where certain, certain conditions are met and you sort of have like these authoritative sources.

[00:40:07] **Tim:** You have software that kind of runs in the background of the world

[00:40:11] **Tim:** To check that, to see when things are happening, you know, a certain weather service says that, you know, flooding happened in a certain area and it kicks off a thing where it reimburses people for whatever. That I thought was super interesting though, that whole thing.

[00:40:25] **Tim:** I don't know how much that's happening in the world right now, but that's a very sort of asynchronous thing where you just say, here's a set of rules, but these rules are met, kick something off. Kind of like that book, Daniel Suarez book you recommended to me, Adam, Damon,

[00:40:39] **Adam:** Demon, yeah.

[00:40:40] **Tim:** Damon. Yeah.

## [00:40:41] The Welcome Email

[00:40:41] **Adam:** And the, the, that's a, okay, that's an interesting thing to bring up because I feel like that's a, that's a problem that we deal with a lot, right? So there's, there's a lot of like, okay, when this happens, then do that. And the question is always about resolution. How long are you willing to be like how much lag time is acceptable, right?

[00:40:59] **Adam:** Like, you know,

[00:41:01] **Tim:** your refresh rate?

[00:41:02] **Adam:** well, but yeah, like, you know, okay, when somebody signs up for a membership or you wanna send 'em a welcome email, okay, great. do you want that to be in line? If you do, it could slow down the, your throughput. So you kind of need to make it, out of process, batch thing or push it into a queue or something.

[00:41:17] **Adam:** and then like, okay, well how often do you go through that queue? How often, right? Like, I guess that email thing is not a great example, but like.

[00:41:24] **Ben:** Well, no, it is an interesting example, I think, because there are so many different ways to solve. A problem like that, and they all have pros and cons. And if you can just cut me some wiggle room here for a second, right? One option could be that when you create a new account, you then dual write that information to another record that sort of acts as a local queue.

[00:41:44] **Ben:** And you can do that inside of a database transaction. So that you know that it's always going to be written. Then you have a process that takes that sort of temporary local queue and pushes it into something like a message queue. And then it can be consumed by a bunch of workers that have fanned out and they're sending welcome emails.

[00:41:59] **Ben:** And that's like a fairly complicated process. Or you could say, what if we just have another database record that has the last. User ID that we looked at and every night it'll churn from the last user ID to the max user ID, and it'll send out welcome emails for each one of those records. And if it fails, it'll just pick up where it left off.

[00:42:18] **Ben:** And that's a significantly simpler solution, but the lag time could be much higher. You know, maybe you're only running that once a night. And is that. Is that lag time worth the simplicity of the approach or is, or is having a big queuing mechanism, but you know, the email is probably going to go out in five minutes.

[00:42:39] **Ben:** Is that much more important than the cost of maintenance of a system like that?

[00:42:44] **Adam:** Right. And then you also have like, okay, how often does this happen? Right. If this is something that's happening 150 times an hour, then the, you know, you can, you could run the job, you know, once an hour and expect there to be a significant amount of work for it to do versus if it happens once every three days, right?

[00:43:01] **Adam:** Then running the job once an hour is like total overkill. But then like, you get to this position where, okay, it's only going to happen once a week. And we don't know when during the week, but we only want to allow like up to an hour of, of lag time, right? Like those are the interesting problems that you run into.

[00:43:18] **Ben:** Stuff's so fascinating.

[00:43:20] **Tim:** world's messy.

[00:43:22] **Adam:** It's like batch jobs, but I don't want to run the batch jobs on a schedule. I want them to be event, event based batch jobs, which is

[00:43:28] **Adam:** weird. Undeliverable

[00:43:29] **Ben:** You know, I build a system at work where, a bunch of things have to happen. And I, I, it wasn't built in a particularly robust way. Basically there's a master concept and then a bunch of API calls, a bunch of separate API calls have to happen to complete this master concept. And, any one of those could fail and I didn't build in any kind of clever retries or anything.

[00:43:50] **Ben:** You know, I think it may have like retried once or twice. And then it just marks itself as an error. And then all I did was in our internal administrative dashboard, I gave them a view and the view, you can say, show me all the things that have erred. And you can just, there's a restart button and it'll basically re initiate the process, but it'll only process the things that failed.

[00:44:12] **Ben:** And it's like, it sucks that someone has to go in and do that, but the cost of them doing that is so low that

[00:44:19] **Carol:** It's nothing.

[00:44:20] **Ben:** yeah, that it's, it's less expensive than it would have been to build a really robust system, given the platform and infrastructure that we had at the time.

[00:44:29] **Tim:** Yeah, but that kind of reminds me how ColdFusion handles their, their undelivered or not the, the, the mail

[00:44:34] **Ben:** Oh, yeah.

[00:44:36] **Tim:** which is just, which is awful. I, it's just, it's because by the time you realize that the mail spool is like getting big, you're like, oh my God, I don't even know. Do

[00:44:45] **Carol:** What happens if I restart this?

[00:44:47] **Tim:** Yeah, if I restart this, you know, I mean, do I really need to resend this email from five days ago to this person here?

[00:44:53] **Tim:** And it's like, I mean, that's why I went to, you know, something like, like SendGrid or, you know, Mailgun that, that just like, you know, hand that off to a, to a message queue.

[00:45:02] **Adam:** This is, we've, we've kind of like touched on a couple of different topics that are making me think of this story. So I have to bring it up. the, so we recently had somebody. We had, we got a support ticket and it was that somebody specifically was looking for their welcome email when they signed up for a membership, like an alumni association membership, and they didn't get it.

[00:45:21] **Adam:** Right, it was supposed to have certain information they were looking for, couldn't find it. So we looked into it, found out, oh, for, you know, a couple of customers, the job somehow got paused. Nobody remembers pausing it. But it's not running and it hasn't been running for a little while. So, we just turned it back on.

[00:45:36] **Adam:** No big deal, right? And, and, oh, and this is all predicated because, the, the customer, our customer decided that, you know, like when you sign up for membership, we want to send you a welcome email, but we want it to feel a little less, we want it to feel a little more organic, right? A little less like instantaneous.

[00:45:49] **Adam:** When you sign up, you get your welcome email. They wanted it to feel personal. and so

[00:45:54] **Tim:** Like I took a few minutes to think about it,

[00:45:56] **Adam:** Well, they wanted it to feel like you signed up for membership and then somebody got a notification and processed it and then they, they sent you a welcome email and it's designed to look like it comes from a person.

[00:46:09] **Adam:** and, so in order to accommodate that request for the feature, we, it's like some sort of a delay. It's like a 20 minute, 30 minute delay, the slight amount of randomization between or per, per recipient. and well, so we turned the job

[00:46:26] **Adam:** back on.

[00:46:27] **Tim:** kind of how FTX put their, their data on their

[00:46:29] **Adam:** Yeah,we, so we turned the job back on and whoops, it hadn't been running for a very long time and we sent out like 1, 500 welcome emails, some of which went to people who were deceased

[00:46:43] **Carol:** no.

[00:46:44] **Adam:** membership, which caused some hurt feelings and, and that sort of thing, because, you know, we kind of made our customer look bad in that situation, right?

[00:46:52] **Tim:** Here's my, here's my bespoke response to a dead guy.

[00:46:55] **Adam:** Yeah, so there was a little bit of crow to eat there, but like, it made us think like, okay, well, so in this sort of situation, how could we prevent that? You, you, you can always say, we could have like, okay, well, we don't know exactly how long the, job has been disabled. So we could go check the database and see how many of these would be queued up to run when we turn the job back on.

[00:47:16] **Adam:** But if you chase down that level of diligence for every single... You know, thing that you fix throughout a day, you would probably get less than half of the work done that, or I personally would at least get a less than half of the work done that I'm doing. Right? Like, so at some point you have to accept that the system is designed well enough to, to handle failures or faults like that.

[00:47:42] **Adam:** Right? So how do you, how do you. Design for this to not be a problem. And I mean, this is a very specific thing. I feel like it can be more generally applicable as long as we don't get stuck on the emailing dead people thing.

[00:47:57] **Ben:** think.

[00:47:57] **Tim:** the fun part.

[00:47:59] **Ben:** If I, if I could just say that, you know, one point of color here, which is that engineers are often, chastised for only coding the happy path.

[00:48:09] **Adam:** Mm hmm.

[00:48:10] **Ben:** code for the failures. And when you're talking about a single file and maybe a particular process. It's easy for someone to learn.

[00:48:20] **Ben:** I should just start with my try catch logic first, so that I know that I have my catch logic and I know that this can recover or log or do whatever it's supposed to do, and then I'll go and I'll put the happy stuff. In between the try and the catch. And you can learn to build a more robust system at a very local scale.

[00:48:37] **Ben:** I think it's very hard to then take that mentality and say, how do I do this across systems? You know, how do I code the unhappy path first so that I know that I've accounted for it and then code the happy path and that's, that just feels, even thinking about that feels much more challenging.

[00:48:56] **Adam:** Like again, going back to the specific example, you know, we could say, okay, you want there to be a delay of somewhere between 20 and 30 minutes before sending this email, what is the maximum delay? So if we've, if we've already crossed this threshold, don't bother sending it at all, right? If it's been two weeks, then just, just skip it.

[00:49:13] **Adam:** Right? But like, are you really going to think about that for everything? Right?

[00:49:18] **Ben:** You know, can I, can I jump in with one side story?

[00:49:20] **Adam:** Go ahead.

[00:49:21] **Ben:** This, this is very similar to your story. So we had something at work where, people's cards get charged on an annual basis or a monthly basis, depending on their subscription. And if we can't process their card, then we put their account into an overdue state.

[00:49:37] **Ben:** And then I think that lasts for... There's some sort of a like Dunning, there's a, there's a process name where it like charges the card, like an hour and then three hours and then a day, and it does it

[00:49:47] **Adam:** Oh, exponential backoff sort of thing?

[00:49:49] **Ben:** Yeah. But with credit cards, it's a very specific term. I think it's like a, the Dunning process. anyway, so for whatever, like, I don't remember the exact details, but someone had deployed a bug where, the credit card processor was telling us that the card couldn't be charged. And that there was a bug in our web hook that was then putting that person into an overdue state. And then what was the problem was we had about, it was like two or 3000 subscriptions.

[00:50:18] **Ben:** I think it was like 2000 subscriptions where they were overdue on their payment. but we had already expunged their billing data from our system because that was like a different process that didn't have a bug in it. So we had 2000 people that we either had to downgrade right now to a free plan. Or we had to contact them and ask them to fill out billing information, but we didn't have an interface that would allow people to just add arbitrary billing information.

[00:50:45] **Ben:** It had to be done as part of a billing process. And we were, we didn't know what to do about that. So we literally ran a calculation like, okay, these 2000 people account for such and such dollar amount. And it was, you know, some, it was like 7, 000. Like it wasn't a crazy amount of money, but it was not a trivial amount of money either.

[00:51:02] **Ben:** And so our solution was to, let's just go into their subscription and mark their end dates. To be 2030 and when 2030 rolls around the background process that downgrades people will take care of these. And there's a note in the code that's like, and hopefully none of us even still work here anymore.

[00:51:20] **Adam:** Mm hmm. Oh, I've left that, that comment before.

[00:51:26] **Tim:** That's just admitting failure right

[00:51:27] **Ben:** We didn't know what to do. Like, we're not going to send out 2000 emails to people, you know, from support, like support didn't have the capacity to even do something like that. And then we didn't have a way to really collect their. Payment information in a secure way. So we're like, let's just eat that cost.

[00:51:42] **Ben:** We're just going to eat the like 7, 000 or 10, 000 of money. And we're never going to charge these people again. And they're going to get to use the system because we just didn't know how to fix it in a way that felt less expensive than that.

[00:51:55] **Tim:** Wow. I

[00:51:57] **Adam:** That's a good story.

[00:51:58] **Tim:** guess it's a way to do it. People are like, man, I've never, I haven't had to renew past 10 years. What's this is great. What's going on.

[00:52:09] **Adam:** Invision error in your favor.

[00:52:11] **Ben:** Yeah, absolutely.

[00:52:13] **Carol:**

## [00:52:13] Monitoring

[00:52:13] **Carol:** So you were talking about how you track things, Adam, right? Like to know if something's wrong. So previously where I worked at, every project would basically be set up with how do we know when this stops working and how do we know that it's working?

[00:52:27] **Carol:** Because every new enhancement made to the system should be. For the most part, it should either impact the user in a positive way or it should be making money. So how do we know that that's actually happening? So the product owners would actually have data on their dashboard. So in your instance, you know, this new feature goes in, their new dashboard little number shows, you know, 5, 000 emails were added to the system today.

[00:52:52] **Carol:** 5, 000 emails were sent from the system today. You know, then 10 days later, when it stops working, you start seeing 5, 000 were added. 100%. And then as that keeps growing, then they bring it to someone's attention that this feature that they push for no longer is benefiting the customer and it's not making money.

[00:53:11] **Carol:** So figure out why it stopped being beneficial or figure out, like, if it's broken.

[00:53:18] **Adam:** Yeah, it becomes, eventually it becomes like a case of who watches The Watchman, right? So like, you

[00:53:22] **Carol:** It's awful, but yeah.

[00:53:23] **Adam:** Yeah, you know, we could, we could say we're going to have a, okay, we're going to have a, another job that monitors and sees how many, how many emails it would have sent today or how many, how many emails there still are to send, right?

[00:53:33] **Adam:** And if it goes over this number, well, then clearly something is wrong, but then how do you know that that job is running, right? Like,

[00:53:39] **Carol:** There's all, all these things. Mm

[00:53:41] **Adam:** Actually, what we're describing, is a problem for a solution called a dead man's switch, right? So, it's, a dead man's switch is, like, think of, this is a terrible, dark thing, and I'm sorry in advance, but like, you know, a, a person wearing an explosive vest, right?

[00:53:55] **Adam:** Like somebody who's a suicide bomber type thing, right? And they have that, that handle that they hold, and if they release it... Then they explode, right? So that means that you can't shoot them because then they're going to drop the thing and anybody near them will explode with them. So it's called a dead man switch, right?

[00:54:10] **Adam:** You have to continue to,like be pressing down the button. And if you release it, then the button does something, uh, there is a website, a company, that I very much like, and I'll go ahead and give them the free plug here, you know, obviously not sponsored. Um, it's called Dead Man's. What's that? They should sponsor, hopefully they should.

[00:54:30] **Adam:** Uh, anyway, it's called Dead Man Snitch. Right? And

[00:54:33] **Adam:** it's

[00:54:33] **Carol:** I like that.

[00:54:34] **Adam:** it's a deadmansnitch.com. it's a very simple API, you know, you set up these different monitors and you say, okay, you give it a name and you how often you plan to have it check in. And it gives you a very unique URL. And basically all you have to do is like, make a request to that URL and that's a check-in.

[00:54:51] **Adam:** And if you stop checking in, and it's been, you know, like it. It can be smart, or you can say, okay, if, if I haven't heard from you within an hour, then you need to let me know, and it'll, it'll send you emails, it can send you text messages, we have it hooked up to our Ops Genie for some of them, so like if this is a, a mission critical process and it goes missing, then let us know, and that's been very good for us, but you can't hook everything up to, like, we don't want membership welcome emails to wake somebody up in the middle of the night, right?

[00:55:19] **Carol:** No.

[00:55:20] **Adam:** yeah. And then, there's other, like, like I was saying, it becomes a, a game of who watches the Watchmen, or, you know, is it worth it to, to monitor things, you, one of the solutions that I proposed for this whole email thing was, like, okay, instead of having a batch job that, like, starts up, looks to see if there's any work to do, and then, and then if there's work to do, does the work, instead of doing that, what if we just, like, you know, And instantly pushed it into a queue.

[00:55:45] **Adam:** And I don't, I don't know off the top of my head, if SQS allows you to say like, okay, I want to add this to the queue, but it doesn't actually become available to be worked until 15 minutes from now. Right. Like, like a, sort of a add with delay or whatever. that would be nice. And that would be like, then you can just monitor the queue depth, right?

[00:56:02] **Adam:** If it, if it ever goes above this number, then either, then something's wrong one way or another, right? Either we're not getting through them fast enough or the job isn't running.

[00:56:13] **Adam:** Anyway.

[00:56:14] **Ben:** We watch a lot of British crime dramas and a phrase that they'll throw in there occasionally is that the absence of evidence is not the evidence of absence. And that to me is the toughest part of alerting and monitoring is it's one thing to, to alert when a threshold goes too high. But what if suddenly your queue is totally empty for an hour?

[00:56:37] **Ben:** Like, is

[00:56:38] **Ben:** that, is that an unhealthy system or is that just, you know, because it happens to be a holiday and none of your banks are using the system. And so there's just happens to be no activity. That's so that's a very

[00:56:50] **Tim:** Or you lost, or you lost internet.

[00:56:54] **Ben:** And then at work, we always have the problem too, where people will, people will often say things. The engineers will say, Hey, I got paged. And then I just ignored the page for a few minutes and it just resolved itself. And you're like, how do we code that mentality into the monitor without being like, what if we just set the delay to 12 hours, see if everything resolves itself.

[00:57:18] **Adam:** this is too real for me right now. We have, so we have our CFML containers, running on AWS Fargate. And... For reasons, they have health checks on the Docker containers, and for reasons, they're configured the way they are, but what the end result of the current configuration is, the end result of that current configuration is that sometimes, sometimes it's like frequently, sometimes three or four customers will fail, will like have a, like a false negative health check, right?

[00:57:50] **Adam:** Or it could be that their, the customer's website is experiencing a high amount of traffic at the moment. and so because of that, the health check takes too long to succeed. And that is considered a, a failing health check, which then restarts the container. And because Lucy takes so dang long to start up, you know, it spins up a new container, but then as soon as that one is like up and they, it started the process, it starts to spin down the other process.

[00:58:19] **Adam:** and so you, we end up with downtime and alarms go off. And they, they fixed themselves because the fix has already happened. The fix is what caused the alarm, right? It didn't deploy. It's so frustrating to me because I'm like, I'm sure that the, the reason that the health checks are the way they are is good for some reason, but it's super annoying to have like alerts going off in the middle of the day or worse in the middle of the night for things that I know will fix themselves like 99 times out of a hundred.

[00:58:48] **Adam:** it's just, it's super frustrating. I feel like Docker health checks. Are fundamentally flawed in some ways.

[00:58:56] **Ben:** I mean, Kubernetes just adds, I don't know. I mean, I guess I shouldn't say Kubernetes, but, but containerization definitely has some quirks that you never have to think about when you have dedicated machines. It has a lot of advantages, but it also has a lot of quirks.

[00:59:12] **Adam:** yeah, for sure.

[00:59:13] **Adam:**

## [00:59:13] Patreon

[00:59:13] **Adam:** Alright, well, I guess that's where we will call it a night tonight. This episode of Working Code is brought to you by Hot Topic. Uh,apparently where teenagers still shop, it still exists. Uh,wait a minute. If, if malls don't exist anymore, how does Hot Topic still exist?

[00:59:29] **Carol:** topics still have storefronts.

[00:59:31] **Adam:** Wow. They haven't all become Spirit Halloween yet?

[00:59:35] **Carol:** Now, and they apparently are one of the few places that sell Twilight merchandise.

[00:59:41] **Ben:** For sure.

[00:59:41] **Adam:** Well, well, when you're, when you're in the market for some Twilight merchandise for your neighborhood teenage girls, Hot Topic is where you want to go. And listeners like

[00:59:48] **Carol:** Creepy.

[00:59:50] **Tim:** Creepy.

[00:59:52] **Adam:** episode. uh, very weird podcast. Uh,if you're enjoying the show and you want to make sure that we can continue putting more of whatever this was out into the universe, then you should consider supporting us on Patreon.

[01:00:01] **Adam:** Our patrons cover our recording and editing costs, and we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo. You guys rock.

## [01:00:10] Thanks For Listening!

[01:00:10] **Adam:** So we are going to go record our after show. there's a note here that I'm very curious to find out. It says, people who have two families. So apparently somebody has something to share with us. we'll, we'll get into it. but if you want to hear that story and more like it, you... Yeah, I have to become a patron.

[01:00:25] **Adam:** You can do so by going to Patreon.com/WorkingCodePod. I'll remind you that we do have a free trial of our Patreon still. Maybe, you know what I'm going to do? I'm going to say that free trial is going away at the end of the calendar year. So if you want to get a free trial, time is running out. While supplies last. That's it for us this week. We'll catch you next week. And until then,

[01:00:45] **Tim:** Remember, your heart matters, no matter how out of sync you are.
