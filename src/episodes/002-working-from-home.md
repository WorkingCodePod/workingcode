---
title: "002: Working From Home"
description: Like it or not many of us found ourselves working from home for most of 2020!
date: 2020-12-23
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/002-working-from-home/id1544142288?i=1000503318818"></iframe>

## Your hosts

- Adam Tuttle -- [Twitter](https://twitter.com/adamtuttle), [Website](https://adamtuttle.codes)
- Ben Nadel -- [Twitter](https://twitter.com/bennadel), [Website](https://www.bennadel.com/)
- Carol Hamilton -- [Twitter](https://twitter.com/k_Roll242)
- Tim Cunningham -- [Twitter](https://twitter.com/timcunningham71)

## Triumphs & Fails

- **Ben's Triumph + Failure:** He finally backs up his computer! Only 5 years in the work.
- **Tim's Triumph:** He was invited to speak at a virtual conference this week as a community expert. It was really amazing.
- **Carol's Triumph and Failure:** She was locked out of a database only to realize she configured the connection wrong from the first day. Total face/palm time.
- **Adam's Failure:** He committed to main... tsk tsk. Who commits to main?? Oh yeah, Adam does...

Follow the show! Our website is [workingcode.dev](https://workingcode.dev) and We're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes weekly on Wednesday.

## Notes & Links

- We want discuss how we handle remote working. Adam and Ben are pros at it but Tim and Carol are new. We go over communication styles and how they differ between face to face and virtual. How we balance home life and work life when we work in our home. We might not get it right, but we keep trying. Grab a drink and laugh with us as we figure it all out.
- [Freakonomics Podcast](https://freakonomics.com/)
- [Rich Hickey: Hammock Driven Development](https://www.youtube.com/watch?v=f84n5oFoZBc)
- [Rich Hickey: Simple Made Easy](https://www.infoq.com/presentations/Simple-Made-Easy/)

[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/002-working-from-home.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:08] **Adam:** All right. Here we go. It's episode number two for right now. Today on the show, we're going to be talking about working from home, but first triumphs and fails. Who wants to go first?

[00:00:24] **Ben:** I'll jump in because I was talking at the start of the show. Uh, this is again, something that is both a triumph and a fail, but I've been a developer for. 20 years, and I literally, for the first time, bought an external hard drive over the weekend to back up my computer in case of catastrophic failure, which I have had in the past once before catastrophic failure lost a laptop.

[00:00:48] **Adam:** How long ago was that?

[00:00:51] **Ben:** That was probably like five years ago.

[00:00:53] **Adam:** So it took you five years to learn your lesson?

[00:00:56] **Ben:** I'm slow. I'm slow. Slow and steady wins the race. And, you know, five years is a long time to learn your lesson, but I've learned it. And now I have Nice little four terabyte hard drive in the corner of my desk, slowly making sure that I don't wake up and start crying.

[00:01:13] **Adam:** So I don't know whether to be proud or, or like upset with you. Yeah,

[00:01:20] **Ben:** I think it's, uh, uh, you know, we're all human and we all have our, uh, Everything is, everything is a, is a balance of safety and effort, and, uh, I'm finally starting to err on the side

[00:01:34] **Tim:** of safety. I have to admit, I've still never done it. Hmm, alright.

[00:01:39] **Tim:** I never, I mean, anything, it's important, I'm already saving in the cloud. Any, everything else is just, I have scripts that I run. If I could destroy my machine right now, and I have a giant PowerShell script that would just rebuild everything for me.

[00:01:53] **Carol:** Yeah, but you've got safety. Yeah,

[00:01:55] **Adam:** but with your cloud backups.

[00:01:57] **Adam:** Yeah, well,

[00:01:58] **Ben:** so and I guess I'll say that. Part of it is that all of my super, super critical things are on GitHub. When I say super critical, I mean my work stuff. That's all already on GitHub. So even if my computer blew up, I'd be able to pull all that stuff. And then I guess I do have some... All of them are important documents in Dropbox, although every article will tell you not to treat Dropbox as a backup system.

[00:02:24] **Ben:** But it seems like a backup system in an emergency.

[00:02:28] **Tim:** I just know I would never actually take the time to continually back it up. So whenever I did lose it, I'd still wind up being in the same situation. I'd be like, Oh man, this backup is like 6 months old.

[00:02:41] **Ben:** I feel like I'm finally at the big boys table.

[00:02:44] **Adam:** I'll get there one day.

[00:02:46] **Adam:** Or not.

[00:02:48] **Tim:** Ha ha. I'll go next. Uh, so my try, I have a triumph for this week. So kind of at the last minute, I got contacted by one of those big Silicon, I won't name the company, but a big Silicon Valley company to just be on a panel about the future of their programming language, which I don't know if that was kind of cool.

[00:03:05] **Tim:** Cool. You've been around long enough. People just tap you and they give you a little gift card, you know, for the, for the, for the trouble. For your trouble. For your trouble. A little Amazon gift card, which is nice. But, you know, just to say, Hey, come, come give your opinion on this. And they didn't prep me, didn't tell me what to say, but still pretty cool to be on a virtual conference like that.

[00:03:23] **Adam:** So that's cool. I knew you were doing it. I popped in for a little bit, but I. Didn't know that that was a last minute thing. I thought you had been planning that for a long

[00:03:32] **Carol:** time. Yeah, it didn't come out as unplanned. It sounded really good. Well, that's

[00:03:36] **Tim:** another trial, because I literally, like, 30 minutes before the topic, pulled up the little document that they said we were talking about.

[00:03:42] **Tim:** I'm like, okay, and then we went. So that was it.

[00:03:48] **Adam:** How about you, Carol?

[00:03:49] **Carol:** Um, yeah, so I had a failure and a triumph, I guess. So, um, got forced into a password reset. So I kind of got the wrong password. And this is an Oracle because I had configured my test environment to point to the QA environment this whole time.

[00:04:06] **Carol:** So it also explained why my data was always wrong, when I was looking at tests. So I got that fixed, but I had to reach out to a DBA who then was like, you've got the wrong service name, you're pointing tests to QA, so, hey, it's fixed now, and my login is corrected, so.

[00:04:28] **Adam:** I guess that just leaves me. Uh, I have a fail to report this week. Um, so I made that cardinal sin and I committed something to the main branch mistakenly when I thought I was committing to a feature branch. And, um, because I'm an administrator on our GitHub repo, it didn't...

[00:04:49] **Adam:** Um, and, uh, so I, I mean, I guess maybe you could say the fail there is that we have that, um, that checkbox in the settings that allows administrators to, to bypass the, uh, the restrictions of needing, um, an approval on a pull request before merging into the main branch, but yeah, it happened and, and, uh, You know, I think like Ben said, I've been working professionally in this industry for 20 years.

[00:05:18] **Adam:** So, uh, it's something that should not be biting me, but, uh, I did it. I'll

[00:05:25] **Ben:** tell you some of the happiest moments of my life have been when they've taken permissions away from me at work. It's like you start out a company small so you can do everything. And then slowly you don't access these private keys over here and you don't have access to the production database and then you can't access certain git repositories.

[00:05:43] **Ben:** And I'm like, not my

[00:05:44] **Adam:** problem. Yeah. I still, we're still so small that I kind of have the keys to the kingdom, at least in terms of the code. There's, you know, there's a lot of stuff that I don't, but.

[00:05:54] **Carol:** I miss that. I miss that so much. Being able to just control everything or having access to it. Now I have to go through everybody to get to things and I'm having to adjust to that.

[00:06:03] **Adam:** Yeah.

[00:06:04] **Ben:** Yeah. That also has its

[00:06:05] **Adam:** challenges

[00:06:06] **Carol:** for sure. Yeah. Like the, you know, embarrassing moment when you find out from the DBA, you've pointed your test environment to QA. If I had control myself, nobody would have known.

[00:06:20] **Tim:** Yeah.

[00:06:21] **Carol:** All right, well, let's get rolling with today's topic. Being a remote engineer, half of us have been doing that, and half of us are new to it.

[00:06:29] **Carol:** So we want to dive into some tips, tricks, and even the pitfalls.

[00:06:35] **Adam:** So I have a fun, uh, working from home story that might be good to start with. Um, so I've been working from home for eight plus years, maybe nine years now. Um, and when I first started we were doing consulting, um, which was kind of fun. Um, you know, normally consulting is, is pretty, uh, what's the word I'm looking for?

[00:06:56] **Adam:** Um, laid back to, to start with, and. By the time that I started this job, I had always felt like, um, I, uh, worked pretty quickly and could get my work done quickly and, and, uh, finish ahead of most people's expectations. And so when I started working from home, it was pretty great that I would be able to, uh, turn in something well ahead of my deadline.

[00:07:21] **Adam:** After having spent a day or two playing video games in my basement, uh, and no one was any the wiser because I was consulting and working from home and, and, uh, you know, they were happy with my output and that was great. The golden age of working from home, I think.

[00:07:37] **Ben:** Well, maybe should we just go around and say who's been working from home for how long just to kind of lay the land.

[00:07:44] **Ben:** Sure. Adam, you said you've been working

[00:07:46] **Adam:** on nine years. Yeah. Um, I used to work in Philadelphia, uh, and Through some of the connections that I made while I was in Philadelphia, I, uh, got the opportunity to take my current job. Um, and we don't have an office. So our entire company is work from home full time.

[00:08:04] **Adam:** And so, uh, I believe I'm coming up on my nine year anniversary. And, uh, so yeah, I've been home full time since then. And it's not always been easy.

[00:08:14] **Ben:** Yeah, I'm sure. Um, I've been working at home, I think about seven years at this point. Uh, I work at Invision and Invision is an entirely remote company. We have About 600 employees, uh, globally.

[00:08:27] **Ben:** So, uh, we've woven it into our, into our culture forever. So it's, uh, it's interesting.

[00:08:37] **Carol:** So for me, I was able to work remote before as needed. So if I didn't feel good or whatever's going on, I always had the opportunity, but I had a desk and I had an office to go to, and that is where I spent. I would say 95% of my time was in an office.

[00:08:51] **Carol:** So, starting in February of this year with COVID and with an injury, I ended up working from home. So, this has been new to me, um, kind of having to set my own schedule and maintain it and also maintain my life around that. It's, it's been an adjustment.

[00:09:09] **Tim:** Yeah, same for me. Yeah, I, 20 years, worked in an office, had my own office, shared offices, and now since COVID

[00:09:17] **Adam:** in March.

[00:09:18] **Adam:** And breaking your leg? I didn't break my leg. I

[00:09:21] **Carol:** broke my leg. That was me. That was

[00:09:24] **Adam:** the joke. Oh, yeah.

[00:09:25] **Tim:** No, I didn't break my leg. And I didn't break her leg.

[00:09:30] **Carol:** Or so he tells

[00:09:31] **Adam:** everybody. Yeah, that's right. That's what we

[00:09:32] **Tim:** told HR. Um, no, it's just, yeah, so working from home and it's, it's been, it's been a struggle.

[00:09:38] **Tim:** I'll, I'll be honest with you. I went through a period of depression. The first month, month and a half. Um, I think part of it was just being quarantined as well on top of working from home, but it was definitely a struggle. Right.

[00:09:53] **Carol:** Um, so for me, the challenge, the biggest challenge I faced early on was I didn't have any expectation to be anywhere at a certain time.

[00:10:02] **Carol:** So prior to working from home, you know, I got up I took a shower. I put on makeup. I got dressed. I left my house. Well, by not doing that, it was like, Oh, I can sleep an hour longer and then just walk and grab the coffee and walk to a desk. Well, then an hour turned into, Oh, if I do it for two hours and then don't really eat lunch, it's totally fine.

[00:10:26] **Carol:** And then suddenly I'm going, it's 10 o'clock and I'm not even starting work yet. Like I have to adjust back. And that also hit me because then I'm not working out. I'm not. Leaving the house at all. Like I'm not putting any effort into most things that were priorities before. And I'm just. Pretty much being lazy a lot and it's taken this entire time to finally get to where I have my alarm set again and I'm getting up at a certain time even though I know nobody knows if I'm up and working other than is my icon green or is it not green?

[00:11:01] **Carol:** Like that's, that's the only known if I'm working or not. So I've had to, you know, get back into making myself have a schedule when no one requires me to have the

[00:11:09] **Adam:** schedule. Yeah, that's key. Having set hours, uh, especially if you've got other people depending on you, like I know you've got kids, I've got kids, um, just to be able to set that expectation, like between these hours, I'm unavailable or only available for emergencies.

[00:11:31] **Ben:** Yeah, schedulers. I'm, I'm an individual that... Absolutely thrives with structure and I, I wake up at the same time, seven days a week, I start work at the same exact time. My lunch will change a little bit depending on what meetings I have. Um, but I take a full lunch, you know, usually to go for a walk or, or try to work out.

[00:11:53] **Ben:** And then I stop work at the same time every single day. And, uh, and rinse and repeat. And I, and I find that I need that exact schedule in order to, to function, to function well.

[00:12:07] **Adam:** Yeah. The routine, go ahead.

[00:12:08] **Carol:** No, I was going to say, do you ever find that when you're bored though, it's easy to just go pick it up and get back to what you were doing because now we're all bored and at home and don't have anything else going on.

[00:12:20] **Carol:** So that was a struggle before that I would just.

[00:12:25] **Carol:** So, um, I'm just gonna go work a few more hours, but then that turns into being burnt out. So, am I the only one that was doing that or does that? The

[00:12:33] **Adam:** temptation is there. Um, and I would say if you're enjoying the work and it's not burning you out, then, uh, you know, there, I don't want to say there's nothing wrong with it, but, uh, there's nothing wrong with it every now and then or in short bursts.

[00:12:49] **Adam:** Um, you don't want to work for free as a habit. As part of your routine, but, um, you know, if I think of it kind of like, um, a side project, right. So if I get a feature that I have to work on for work, and I'm just super hyped about it, and I'm really excited about learning whatever the new thing is or dealing with whatever API or whatever, then, um, you know, I have no shame putting in an extra hour or two just because I'm excited.

[00:13:17] **Adam:** Um, you know, nothing wrong with that.

[00:13:21] **Ben:** I think one thing that's really helped Us at work, culturally, is that communication between people really happens during business hours. And I know when you're remote and everybody's communicating digitally, it's really easy to start messaging people at like 9, 10, 11 o'clock at night.

[00:13:40] **Ben:** Uh, you know, especially if you're on the East coast and they're on the West coast or vice versa, I should say. Yeah. But, but For everyone to sort of commit to just not doing that and being very respectful. Here are the business hours, here's where we communicate. If you're going to communicate outside this, it should be some sort of asynchronous form of communication.

[00:13:58] **Adam:** You guys don't, do you have Slack that you're saying is not asynchronous?

[00:14:04] **Ben:** Even with Slack, I feel like we've been very good about it. I think it's just something that we, we, we have stated business hours, um, even though we have people spread out, we, we typically work in a certain set of hours, East coast time.

[00:14:19] **Ben:** And I think most people are just good about communicating strictly within those periods.

[00:14:25] **Adam:** It sounds like it would be helpful in a big company. I was going to say, like, time zones probably, uh, you know, has a, an important role depending on the size of your company and how far spread out you are. Yeah. I am the

[00:14:36] **Carol:** only one on the East coast for us.

[00:14:38] **Carol:** We'll have a project manager, but I'm the only one on the East coast and everyone else is California. So I'm a three hour shift and I have my Slack set to do not disturb starting at 630 my time, which is three 30 their time. And we've been really good about. Not having that communication unless it was a planned event and in which case I just sign on later that day or I take a three hour lunch and you know, chill.

[00:15:07] **Tim:** I think the hard thing for me was the lack of movement, right? Yeah. Particularly quarantine. I think That kind of compounded it. It may not have been so bad if I, this was my choice to work from home. It really, it wasn't my choice. It was mandated that we had to, and just the lack of movement, of not going.

[00:15:25] **Tim:** You mean physically, right? Physically, yeah. It's not physically moving from my house to to a place to say I'm working

[00:15:31] **Adam:** now, right? So, is it the change of scenery that you're looking for or the physical, like the exercise sort of aspect or both? Both, yeah. I think it's

[00:15:39] **Tim:** both. It's so I felt like I wasn't doing anything, although I was probably actually doing a lot more than I normally was.

[00:15:46] **Tim:** Right. Because, uh, I'm like, I'm not, I wouldn't say I'm like, Ben in that regard, but I am, I do like a routine. I do get up at the same time every day and I start working. If I don't, I feel guilty. A couple of times I slept in, I felt terrible about it. So I just stopped doing it. So I got up, I do it, you know, the worst for me though, is when it's a quiet day.

[00:16:06] **Tim:** It's like, it's really good. If I get on, there's people there. I can like start chatting with them and you check on things and, you know, start poking the beehive. And it makes me feel like, you know, stuff's happening. Today was awful because I don't think hardly anyone talked to me today. No one sent me any messages and I'm like, something's wrong.

[00:16:25] **Tim:** Like I'm out of the loop. Right. Are they talking about me behind my back?

[00:16:30] **Carol:** It's like the paranoia. Yeah.

[00:16:33] **Tim:** Did I, did I, did I bathe? I did shower. They

[00:16:35] **Adam:** wouldn't know, it's fine. I, I can relate, but mine was a little different. So when, when I was having similar thoughts, it was, I was the second employee of my company, right?

[00:16:46] **Adam:** So we have our CEO and then I was the, the only other person working at the time and he's not the overly communicative type. You know, I'm, I think I'm just more outgoing and I, uh, I find value in that. Um, open communication, like even though it was just the two of us, I, I found value in it being in, I think at the time it was HipChat.

[00:17:09] **Adam:** This was pre, pre Slack. Uh, but, uh, you know, having it there to be able to refer back to or, or something, something about that just seemed more valuable than email or, uh, a phone conversation or something like that. And so I would, I would be chatty. in there all the time and he would not be as, you know, uh, responsive.

[00:17:34] **Adam:** Yeah. Responsive or, or, uh, not the one to start conversations. This wasn't his style of communicating. Yeah. I see that. And, um, so I would have similar thoughts, like, just a feeling of, of, uh, lonesomeness. Mm hmm.

[00:17:52] **Tim:** But, but it's funny, when we were in the office, I would literally have Slack conversations with people 15 feet away from me.

[00:17:58] **Tim:** The door behind you. Right. And never, never physically interact with them, but I knew they were there. Right. I don't know why that made a difference, but it's gotten better now. I've gotten, I've gotten a little bit more used to it now, and as long as it's not a quiet day, I'm usually happy.

[00:18:13] **Adam:** Right. So, uh, I mean, I know there's a pandemic right now, and this is not really a viable suggestion for this week, but something that helped me a lot in the beginning, uh, especially with that sort of like, I feel like I need the change of scenery, a little bit of exercise to get up and move.

[00:18:29] **Adam:** I, I find it difficult to motivate myself to. Just go for a walk around my neighborhood at lunchtime. Like lunchtime, I tend to either feel like, okay, this is my time to relax and reset my brain. So I'll watch a TV show for my hour or whatever. Um, or if I'm either really excited about something or I'm working on something that's really important, then I will eat as fast as I can and get right back to work.

[00:18:53] **Adam:** Right. Those are sort of the The two patterns I see in the way I handle my lunch hour, uh, even though I fully admit and wish that I had the motivation to get up and go for a walk at lunch. So what I found worked really well for me early on in my remote career was, uh, taking my laptop and going out to somewhere I would go to a Starbucks or to, um, there's a couple of brew pubs near me that would open up at noon.

[00:19:17] **Adam:** So I would like go out at noon, grab lunch. Uh, and finish the day out there sort of thing. So it was, you know, it was like co working by myself, right? I would just go out somewhere and the, the change of scenery, the noise, the,

[00:19:31] **Carol:** the beer. Just hearing other people talk. Yeah, that chatter.

[00:19:35] **Adam:** And I mean, I know it's not everybody's company culture, but, uh, if you would like to and, and nobody at your company minds, it's.

[00:19:44] **Adam:** Kind of nice to be able to have a beer while you finish your workday. Yeah. Plus it forces you to put

[00:19:50] **Ben:** pants on,

[00:19:50] **Adam:** which is... There is that. Yeah, that. Put on the good sweat pants. I like, I like that video is up, yeah. Yeah.

[00:19:55] **Carol:** Yeah. Like

[00:19:57] **Adam:** chest

[00:20:00] **Tim:** height up. One thing I found though, cause I love to cook. Some of you probably know that about me.

[00:20:06] **Tim:** I love to cook. And so I, I got into the habit of like. Getting into little food projects while I was working. Mm. It became a big distraction early, early on, and I think I was stress eating as well. Mm. Um, so, you know, I would, I'd, you know, I'd get up in the morning, I'd like go start, you know, creating, making some kimchi, and then I'm making, you know, doing some, getting some steaks ready in the, so for, you know, the thought of, well, you know, I'm, I'm at home, so I've got time to do that.

[00:20:32] **Tim:** I wound up ca you know, calculating the time I was spending cooking versus working, and it was like, I'm, yeah. Cutting into my work time here by cooking so much, and I started to gain a lot of weight, which didn't make me happy. So to take my control back, um, one thing I've done for the past two years is, is water fasting.

[00:20:50] **Tim:** So what helps me get through the week to kind of mark the days is I actually don't eat food from Sunday night until Friday morning. I only drink water. Wow. Four days a week.

[00:21:02] **Ben:** You said from Sunday night to Friday morning? Right. That's right. Four

[00:21:06] **Adam:** days a week.

[00:21:06] **Tim:** I only drink water. That's intense. Yeah, it is intense.

[00:21:09] **Tim:** But, uh, I mean, I built two years building up to that. I did it for two days and I did it for three days and then during the pandemic, I'm doing it for four days. And so I spend the whole week really looking forward to Friday.

[00:21:21] **Adam:** Wow. That's that's intense, dude. That is a lot. Yeah.

[00:21:25] **Tim:** Well, I did it for my, my, you know, cholesterol.

[00:21:28] **Tim:** I dropped my cholesterol 200 points. Doing that without having you take Oh, take nice. Without having to take medicine. So I don't, I do not recommend it to anyone. No, do not, do not anyone out there listen to this. This is not a push for this, not a push for this. This just works

[00:21:40] **Adam:** for me. So we are not doctors.

[00:21:42] **Adam:** No, no.

[00:21:44] **Carol:** I have one in the other room

[00:21:45] **Adam:** if you need, we'll, we'll ask later

[00:21:49] **Ben:** One thing that, uh, When I first started to work from home, one thing that was surprisingly stressful for me was the dog. And suddenly she's sitting there and staring at me and I start to worry about whether or not she's sufficiently intellectually stimulated as a dog, right?

[00:22:06] **Ben:** Like I actually had to start doing research about how much activity dogs need and how much attention. And it turns out that they're predators and they actually should be sleeping most of the day and it's not. You know, you don't have to be entertaining them 12 hours. So that was, that was a little bit of a relief, but I, I, even, even today, I still, I worry that she's getting attention and I'm, it's not just a couple of short walks a day.

[00:22:29] **Adam:** And we're neglecting her. We're Facebook

[00:22:31] **Tim:** friends. I've seen her hump that pillow. She's good.

[00:22:36] **Ben:** She self suits. I'll have to

[00:22:41] **Adam:** bring my dog in sometime and let him sleep on the sofa behind me. Uh, while we're recording sometime, you'll be able to hear him snoring. I have a Boston Terrier and, uh, yeah, he's, he sleeps all day and he sleeps all night and he's a, they call it brachycephalic. He's a smush face dog, uh, and so they snore like crazy.

[00:23:00] **Adam:** Yeah, we got

[00:23:01] **Tim:** two pugs and they have been the MVP of this pandemic. I don't think any of us in this family would have survived without those dogs. They've kept us completely sane with their silly antics. The other challenge is kids, right? So I've got two teenagers and they're, you know, they're, we took them out of public school and, and started homeschooling them and, and making sure that they're doing their schoolwork and getting up on time and all that stuff.

[00:23:27] **Tim:** But actually I think it's been good for them. They've been able to go at their own pace. So they're usually in the next room while I'm working, so I'm just curious if they're over listening to me during my conference calls and wonder, does dad really say that? Does he say, let's circle back? Or, you know, is he that guy for real?

[00:23:48] **Adam:** So that actually kind of dovetails nicely with something I wanted to circle back on. So you were talking about... I see what you did there. That was totally unintentional. Uh, the, the, oh God, see, now I can't think because you made me Get your own! That too. So, Tim was talking earlier about, uh, being able to step away to, to work on food, that sort of thing.

[00:24:10] **Adam:** And I have to say, that's gotta be, for me, um, one of the biggest benefits and one of the reasons that, um, I was willing to take a risk on this job, you know, uh, working for, for one other person at that small of a company where it's just the two of you is, is a huge risk. Um, And, uh, one of the reasons that that was so appealing to me to make it worth the risk was the ability to spend more time with my kids.

[00:24:35] **Adam:** Um, and not just like, you know, I'm, I'm home earlier and I leave later sort of thing. But, um, you know, the days that they're home, if they're sick or something, I can be there for them. Um, if they need to go to the dentist, you know, I can be the one that runs out and takes them out. Um, and. Yes, the, the lack of a commute.

[00:24:55] **Adam:** One of the things I used to say was that like, now I have the opportunity to make my kids breakfast and lunch every day. And that was true for a long time, but now my kids are, are grown up even more, you know, that was eight years ago that I was saying that thing. And now they make their own breakfast and lunch and I don't, they don't need me anymore.

[00:25:12] **Carol:** You're still around though, you're still around in the area. So if they have a question about it, you're just a room away, it's easy for them to have that conversation. Whereas if you're not there. You do miss out on those little quick conversations that would have never existed.

[00:25:27] **Adam:** But it's, it's the little things, right?

[00:25:29] **Adam:** It's stuff you never would have expected. The, the huge benefit of being able to take five minutes in the middle of the day and go have a conversation about something that's important to them is huge to them and it cost me. You know, the kids being in the next room, my son is part

[00:25:53] **Tim:** of extra school work, is taking a Harvard course online about computer game programming, which he's really, really thrived at. I mean, he's, it's, the course curriculum looks really cool. They've done like A version of Flappy Bird, and he's built a Mario clone, and he's done some, I mean, they give you a lot of the code already, so all the digital assets and everything are already there, so you feel like you're actually building a game, because you are.

[00:26:22] **Tim:** It's in Lua, and then in, uh, they're using Unity Engine, um, but. You know, I'm in here banging my head against the keyboard for, you know, some error that I've been working on. And then I go in there and he's, he's in there banging his head against the keyboard. 'cause he forgot, he forgot a semicolon somewhere.

[00:26:38] **Tim:** And I'm like, son, we're doing the same thing, man. Yeah.

[00:26:42] **Carol:** I mean, you feel like just going

[00:26:43] **Tim:** high five. Yeah. Right. Yeah. To, to bond over that. He's so proud of himself. Come here, come here. I, I created, you know, this. It's like a version of Portal that he's working on now. Oh, awesome. He's showing me that and I'm like, I'm pretty amazed at the stuff he's doing.

[00:26:56] **Tim:** But yeah, to be able to, I couldn't do that if I were, I would come home from work and he'd show it to me and I'd be tired. And, but now when he's excited at that moment, he can just, you know, if not in a meeting, he can say, Hey, come, come look at this. I did this cool thing in Unity Engine. It looks like Portal and that's, that's invaluable.

[00:27:14] **Tim:** So it's.

[00:27:16] **Carol:** Yeah, or he finds the missing semicolon and never tells you that he never, that he, you never know that it, it happened to him. So you don't have that moment. Yeah. Or it's like when we're in the office, people walk by and distract you all the time. And you're like, Oh, well, since you know, you want to talk, I'll give you a minute to talk to you.

[00:27:34] **Carol:** Yeah. But when you're at home and it's them, it just, it feels more valuable. It feels like. That 5 minute conversation, like Adam said, is more valuable than a 5 minute smoke break

[00:27:42] **Tim:** any day. Yeah, because he, I mean, he came in and asked me and told me about, he's like, I can't figure this out. And, uh, you know, I just.

[00:27:48] **Tim:** I talked him emotionally through it, but I'm like, I'm not going to debug this for you. That's your job. And then when he finally, uh, an hour later, I hear, Oh my God. And he found the one missing space that he, you know, that, you know, that triumph that shared joy was awesome.

[00:28:07] **Ben:** That's cool. One thing that I think all of us have said at this point is that.

[00:28:12] **Ben:** Uh, we do have a separate space at home that is now sort of the de facto office and I think just to acknowledge that that makes a huge difference that it's, it's not that, you know, we're lucky enough that we're not at a kitchen table and our, you know, entire family is right there doing their work on their, on the couch or something like we still have what is effectively an office, even if this is the second bedroom, but that it makes a huge difference.

[00:28:41] **Carol:** Yeah. It's still a designated area. Yeah. Yeah. Cause that was one of my struggles was I am. I have ADHD already, so my focus is not on until it's on. So, when I would wake up, I'm like, oh, I need to go do the laundry. Well, I can't go to work until the laundry's finished drying. It's like the whole process has to be done, and I'm wandering around the kitchen going, well, there's dirty dishes I need to pick up.

[00:29:05] **Carol:** So, once I stopped working out in my house, like just in the general area and moved into my office, my physical office, it, it was very, very hard to stay focused. There was just way too many things around me, too many things that felt like what needed to be the priority because I had gotten really good at telling myself when I'm at work, work's priority.

[00:29:25] **Carol:** Yeah. When I'm at home Home's priority and you don't cross them. So to be at home and to try to make work a priority was difficult. Upfront. Yeah. So having, having an office, definitely.

[00:29:37] **Adam:** Or just easier a space, even if it's just a door that you can shut, like if you can put a little fold up table and a chair in your bedroom mm-hmm.

[00:29:45] **Adam:** and you can shut, shut the door and say like, look when the door is shut. I'm at work, and if you need me, you can text me, and you can email me, and if it's an emergency and the house is going to burn down, then yeah, come knockin But, uh... Or even

[00:29:58] **Carol:** do that to yourself, you know? Don't wander out to the laundry room to go do the laundry, you know?

[00:30:04] **Carol:** Wait for lunch to do that if it's really going to bother you. Like, go put the laundry in and then take a walk, and then throw it in the dryer when you get back.

[00:30:11] **Tim:** Right. Yeah, so I think the challenge this year is some... Usually it's work home balance, and now it's like work home...

[00:30:20] **Carol:** Integration. Yeah. That's a good way to put it.

[00:30:21] **Carol:** I

[00:30:23] **Tim:** stole that from somewhere. I don't know where, but

[00:30:25] **Adam:** you heard it here a second. Yeah. You stole from me still twice. Yeah.

[00:30:30] **Ben:** I was just listening to, I think it was an episode of a Freakonomics, which if you haven't tried it, it's a really fantastic show. And, uh, they were talking about a camera. It was a company.

[00:30:42] **Ben:** I want to say maybe it was in China, and, uh, they did a six month experiment at this one company where they selected half of their employees to work at home for six months randomly to see if they would, uh, be more productive. And they found that after six months, people who work from home were actually, I think they said 13% more productive.

[00:31:03] **Ben:** But then when the study ended, I think something like 25% of the people who work from home actually wanted to come back into the office and only a handful of the people who had been working in the office decided that they want to then work from home now that there was more of an open policy around it.

[00:31:18] **Ben:** So it's, it's definitely not for.

[00:31:22] **Adam:** Right. You know what? That kind of made me think of something. So in Philadelphia, there is a co working space called Indy Hall. And, um, I know there's a lot of co working spaces out there that get a bad reputation for it's a, you know, it's a subscription desk and electricity and locked door service.

[00:31:45] **Adam:** And that is not. at all what Indy Hall is, but, and I haven't spent a ton of time at Indy Hall, but I did go there and it's definitely way more of like a community. And I think that if I was going to crave leaving my working at home situation, that would be what I would want, right? Like, I don't want to go back to a stuffy office where I have to wear, uh, an iron shirt.

[00:32:09] **Adam:** and slacks and not sneakers and, uh, that sort of thing. Like I crave being around other people and the, the, the clean break between home sometimes, home and work. Uh, but I don't know that the thing that I'm craving is actually being in an office. Like an office seems like too much sometimes. I think that, uh, maybe a coworking space is probably a good choice for a lot of people who feel like they, they are, for whatever reason, working from home isn't working for them.

[00:32:40] **Adam:** But you got to find the right co working space.

[00:32:43] **Ben:** Well, and, and, and I think it's, it's important to remember that we're all in this together, and there's all going to be a certain degree of lacking or maybe yearning for some human interaction. And I think pulling that into the business context. is really, really healthy because I know, um, a lot of teams will have daily rituals around meetings and, and updates and whatnot.

[00:33:09] **Ben:** And, and I think when you're in an office and everybody wants to just get back to their desk and start working, it's very sort of by the books, you know, Adam, what are you doing? Carol, what are you doing? Tim, what are you doing? Okay. Back to work. When that meeting. is now the time during the day I actually get to see other people's faces.

[00:33:24] **Ben:** Like, don't make it just business, you know, feel free to talk about TV shows and your kids and what your pets did and, and like, yeah, throw some business in, but don't make it just business because this is now both the meeting room. And the, the water

[00:33:39] **Adam:** cooler, so to speak. Yeah. Yeah. No, our, our morning standup meeting, especially after the pandemic became a lot of a mix of what's going on that day in the business and also commiserating over the problems of having our children in our hair all day as we're trying to work.

[00:33:58] **Tim:** I want to go back to what Ben said earlier about productivity, because I do find that interesting. So you said that, that Freakonomics thing to the, the team that was. Remote became more productive, is that correct? Yeah, I think

[00:34:11] **Ben:** they said 13% and I think it was, um, I can't remember the type of company. It was like they did a lot of phone calls and reaching out, I think product sales.

[00:34:21] **Ben:** So it was, they had something that they could very concretely measure in terms of productivity. Um, and I, and I think they said that the remote workers ended up being 13% more,

[00:34:30] **Tim:** more productive. Yeah. So what I find interesting, so the company that, that I worked for, it's, it's kind of a smaller company, but it's inside of a portfolio of a much, much larger company.

[00:34:43] **Tim:** And over the bigger company scale of, you know, tens of thousands of employees, you know, they send out these newsletters and their experience, and this is global, um, that since everyone has the company mandated that everyone inside there has to work from home during the pandemic, um, that productivity has not dropped off, it has gone up, which has been their finding that they're working from home.

[00:35:08] **Tim:** They were afraid would Negatively affect them. They found the exact opposite. It has not negatively affected productivity. What it has hurt is morale. There's been a big hit morale for people that have been forced to work from home and probably because of the same things that I emotionally went through, uh, you know, just that level of lack of control, a slight little bit of depression, a little bit of uncertainty.

[00:35:34] **Tim:** Um, and so to combat that, what, uh, we've been doing, and I don't know what the other companies in our portfolio have been doing, but what we've been doing is trying to have more just for fun kind of social things. Like we had. A couple months ago, we had a, uh, an online cocktail class that people were coming up for, and then we had this company, and they, they had these, you know, cocktail, we get, and they brought us, they actually shipped to us the alcohol, and we made the drinks, we got to get on the camera, and everyone was there, what we, that was really lots of fun.

[00:36:03] **Tim:** People stayed, like, I mean, that was toward the end of the day. We could, we could do it during working hours. So I think it started at three and then it was like an hour and a half class. And then afterward people stayed off like two hours and just chatted, which was great. Uh, we did like an escape room, an online escape room.

[00:36:19] **Tim:** We did, uh, our murder mystery, a clue murder mystery online. We, you know, these are paid companies. We, this is during working hours. And so it's, it's been an effort to increase morale and to kind of have sort of that social interaction. Um, and it's helped, but, uh, you know, we'll see next year when things quiet down, how many people will want to continue to stay home and how many people want to, uh, go back to work.

[00:36:45] **Tim:** I would actually just prefer to stay home for the most part unless there's a meeting that I need to attend.

[00:36:51] **Carol:** Yeah, I will be staying home.

[00:36:53] **Ben:** Well, and I think just going back to Tim's point about stress, that there is a difference, an important difference between... People who plan to work from home and people who have now been forced to work from home.

[00:37:05] **Ben:** It's a very different experience. And not to say that you can't transition from one to the other, but don't on day one. expect that you're having the work from home experience because you're not really. No, it's a

[00:37:17] **Carol:** struggle. It's a struggle. It's hard.

[00:37:20] **Adam:** It was, I think it was years before I really stopped having cabin fever.

[00:37:25] **Adam:** I can't remember the last time that I actually went out and intentionally worked someplace out of my home. Because I felt like I needed to, you know, I, I, I used to need that in order to just feel like I wasn't going to vibrate out of my chair. But, uh, lately, you know, I, I guess I've just gotten into the right rhythm, the right routine with work, and we have a lot of challenging work going on.

[00:37:53] **Adam:** So, um, you know, I just feel like from the time that my butt hits the seat in the morning until the time that it's time to leave in the afternoon, uh, you know, I'm, I'm engaged and, and I don't. feel the need to to go anywhere else anymore. And I think that it wasn't something that I noticed in the moment, but I can remember looking back and going, you know, it actually has been a while since I felt that need to go somewhere else.

[00:38:17] **Adam:** And I don't know what clicked, but something did eventually. And I think it just takes time to get there. Well,

[00:38:24] **Ben:** and when I used to work in an office, I would never even have considered leaving early just because. See, people see the whole point of being in an office is to be there and see it's time. And now that everybody is remote, uh, it, it, it feels way easier to.

[00:38:48] **Ben:** At 4 30 in the afternoon, just say to the team, yo, I'm really burnt out and I'm going to leave. And I'm, you know, slack me if there's an emergency, but I'm done for the day. Cause it's, I, you know, maybe just because it's not so physical, it feels so much, I want to say safer to, to put yourself out there and admit that you just have to step away from the desk.

[00:39:12] **Ben:** Whereas in a physical office, I mean, I can only speak for myself, but I, it would have never in a million years occurred to me. That I'm just going to push away from my desk and walk out of this room that has 30 other people in it.

[00:39:23] **Tim:** Here you guys, I'm going home. Yeah.

[00:39:28] **Carol:** I used to actually work a lot later when I was in the office.

[00:39:31] **Carol:** I would put in a lot more hours. And now I do cut off more. I'm like, I'm going to cook dinner. Bye. Like done. That's a hard stop where I'd be like, alright, I'm just picking up some food on the way. It's fine. No big deal. I gotta work late.

[00:39:48] **Adam:** And that's another huge benefit of working from home is that not only can you have that flex time to take five minutes to be with family when they need you, but also, um, If you're already working remote, then there's pretty much no reason, I guess it depends on what you're doing, but for what we're doing, developing, writing code, there's almost no reason that I can think of that you couldn't leave an hour early to go to a doctor appointment and then come back and make up that hour later.

[00:40:17] **Adam:** Yeah.

[00:40:18] **Carol:** Yeah. It's not like I had to drive back to the office and go work it. Yeah.

[00:40:22] **Tim:** Yeah. And, and so the last week my, my wife had neck surgery and so she's been laid up. So this is, I mean, it's been a real blessing to be able to be here cause I can be here for her and make sure she's taking it because she can't probably do anything.

[00:40:33] **Tim:** She's in a lot of pain, can't even swallow, swallowing water. Water hurts. So, I mean, I would have had to take two weeks PTO probably before, but now it's like I can still work. I mean, it's not a 24 seven check on her kind of thing, but it's like just get up every few minutes, check on her and see what she needs.

[00:40:50] **Tim:** So that's been, it's been wonderful.

[00:40:52] **Carol:** It's healthy for you to get up and walk away too every few minutes. So, and from her, good thing both.

[00:40:59] **Tim:** We'll go both ways. She, she's like, please go.

[00:41:01] **Carol:** Just go. Yeah. , don't you have some code to write, Tim? That's right.

[00:41:06] **Adam:** One of the things

[00:41:08] **Tim:** I, I got a different thing kind of jump off.

[00:41:10] **Tim:** So,

[00:41:10] **Ben:** yeah, go ahead. I, I, I was just gonna say, to go back to the Freakonomics episode for a second, one of the guys that they were interviewing, Was saying that one of the really nice things about the pandemic, and I hate to say that, but one of the nice a

[00:41:21] **Adam:** about

[00:41:21] **Tim:** it's a thing, the silver lining.

[00:41:23] **Adam:** The silver lining, yeah.

[00:41:24] **Ben:** Is that it has removed a lot of the stigma of being a remote worker. Mm-hmm. Mm-hmm. Because prior to this, people who would remote work were, were the odd men out. You'd be the one person at the office who worked remotely. And everyone in the office, you know, think about, what's Carol doing? Is she even at her

[00:41:42] **Adam:** desk?

[00:41:42] **Adam:** Like... Special treatment.

[00:41:43] **Carol:** Yeah. There's a green light. Do you see the green light? Then I'm working.

[00:41:47] **Ben:** Right. So now it's, it's, uh, everybody has to do it. You realize, oh yeah, we're just at home working just like we would be normally. And it's, it's not a weird thing anymore.

[00:41:55] **Tim:** Right. And it kind of leads into one of my, like, life bucket list, bucket list life plans.

[00:42:03] **Tim:** At some

[00:42:04] **Carol:** point... Say that again. One more

[00:42:05] **Tim:** time. So kind of one of my bucket list,

[00:42:12] **Tim:** one of the things I want to do before I die is to be like a digital nomad and to just kind of sell everything and head out and, and just move from country to country and work remotely, just, you know, work remotely, take your laptop with you because you can do, I mean, if Lisbon or Bali or Chiang Mai, Thailand.

[00:42:36] **Tim:** Um, you know, there's even a website, TheNomadList. com has a list of all the best places and cheapest places.

[00:42:44] **Carol:** Just make sure your VPN connects to work and you're good.

[00:42:47] **Adam:** Yeah, I've got it. I've gotten a taste of that, actually. Not, not from Thailand, but, you know, from a campground, you know, a couple hours from my house.

[00:42:55] **Adam:** So my family, we have a very small pop up camper, and we like to go camping a lot during the summer. And, you know, something that, uh, has always been very clear to me at work is that it doesn't matter where I am, right? It doesn't matter if I'm working from the bar or from my desk at home or from somewhere on the road.

[00:43:11] **Adam:** As long as I'm getting my work done. And I'm available to have the discussions that need to be had, then it doesn't matter. And so I have on many occasions taken my work with me, you know, we'll leave first thing on Friday morning, pull into the campground, get the camper set up. And then I tether my phone to my laptop and, and I put in my hours for the day and I punch out and I'm at the beach or whatever.

[00:43:33] **Adam:** It's great.

[00:43:34] **Tim:** There's a guy on our team. He, that's what he has done before he started.

[00:43:43] **Tim:** And I think they have three kids. And they went around the country in, um, an RV. Yeah. I think it was a pull behind. But anyway, and for years, that's, that's how he lived, you know, he didn't tell me all the places they'd visited. And I'm like, okay, it's That's kind of a nomadic life. That seems kind of cool.

[00:44:01] **Tim:** I'll do that. I'll do that after the kids

[00:44:03] **Carol:** graduate. Yeah. Oh, yeah. I don't, I don't want multiple people with me for that. That's right. But could you imagine waking up and just setting on top of your camper? Just climbing your ladder to the top, putting your, your lawn chair up there and just coding from the roof?

[00:44:15] **Carol:** Yeah. Like... Looking at the Grand Canyon. The view, everything you have. Yeah. And that's a good thing that we can do it. That's why I love being remote engineer is that I can do it from here. I can do it from anywhere. And then I save all my vacation time for vacations, not for our doctor's appointments or to run to the orthodontist or to pick up something from the store.

[00:44:35] **Carol:** I'm using my vacation for vacation for time away. Yeah. The fun

[00:44:40] **Tim:** stuff. I still use PTO defensively though. If there's, if, if there's a, not saying a meeting, but basically I want the team to know like, I really do not want to be bothered. I'm taking four hours.

[00:44:51] **Adam:** Sure.

[00:44:52] **Carol:** Sure. Yeah. Yeah. Sure. I can see that. So we've went over, you know, a lot.

[00:44:58] **Carol:** Um, what would each of you say is the biggest pitfall that you've had to, um, overcome?

[00:45:10] **Adam:** Put us on the spot, why don't you? Yeah, pressure.

[00:45:13] **Ben:** I'd say at least for me, in the earlier days of the company, it was getting late night text messages and feeling like I had to get out of bed. And go respond. Yeah. And that was. Put me in such a foul mood.

[00:45:28] **Carol:** So you felt, you felt like since you were working from home, you had to like give extra connection to show you were still connected or something?

[00:45:35] **Adam:** Yeah,

[00:45:36] **Ben:** you, you feel, at least at first, I felt like I had to be always available because everybody's at home. Computers in the next room. Yeah. And I think once I learned that I had to have boundaries, that was a, that was really a huge improvement.

[00:45:54] **Tim:** And I think our, the morale for some people has gone down because they feel they haven't learned that lesson yet.

[00:46:02] **Tim:** Yeah. And, uh, they need to learn to, to, to turn off. I think that's kind of the phase we've gotten into now and having worked from home is that people are learning, hey, just because my laptop's right there and I've been at it all day doesn't mean I need to be at it at 10, 11 at night. Um, So someone

[00:46:20] **Carol:** should physically have to go through the chain of command and give me a call, like go through the list of people.

[00:46:26] **Carol:** My phone should have to ring if there's a problem. I shouldn't have to wait for a slack dean to be like, go look at this message. Like, there should be a clear way that says this is when we have an emergency. Yeah. Close the laptop.

[00:46:40] **Adam:** Well, we have, um, to, to, I guess, follow on that a little bit, we use a service, not, uh, not an endorsement or anything like that, not an advertisement, but we use a service called Ops Genie that, uh, in addition to being able to, um, with an API or whatever, push in when there's a, an outage or something that we need to deal with, we can, um, create events on purpose.

[00:47:03] **Adam:** So like if, if something's going on and we know it hasn't raised an alarm, then somebody can go in and manually raise an alarm to get the attention of the person that's on call. Um, and that will break through your phones, do not disturb and all of that. So if you can figure it too, that's been handy. At work, we

[00:47:18] **Ben:** use a service called pager duty and literally my last moments, literally my last moments of the day are turning on my alarm.

[00:47:30] **Ben:** And then making sure my Patriot duty app has not crashed. And that's it. And then I get into bed.

[00:47:35] **Adam:** Nice.

[00:47:37] **Carol:** So what's your biggest pitfall?

[00:47:39] **Adam:** Oh goodness, this whole time I've been trying to think of one and I think it's tough because I feel like the only thing I can really think of anymore, I've been doing this for so long, the only thing that I still struggle with sometimes is boundaries.

[00:47:52] **Adam:** And if it's, sometimes it's because I'm annoyed with the kids because they're kids and they do kid things. Sometimes it's because I'm really enjoying the work that I'm doing. Sometimes whatever, you know, whatever the reason is, sometimes, you know, I have an alarm set on my phone for five o'clock and it'll go off and I'll just turn it off and keep working and, and wait until somebody goes, you know, dinner's ready.

[00:48:16] **Adam:** Uh, and then I'll come down and I'm not proud of it, but it's true. And, uh, you know, it's, it's tough to try to force myself to. Uh, to go down and be home at home time when I don't, when I'm not in the mood for it already. And I'm sure if I go and do it eventually, you know, it's like fake it till you make it, eventually it'll come to you.

[00:48:43] **Carol:** Yeah, but when you're in that mindset, that's, that's what I find is the hardest to check out of, like when my brain is on and I feel like I am just producing something that if I stop tomorrow, I may not remember what I was on. I don't want to walk away and then I have to go. Okay. You have to still stop.

[00:48:59] **Carol:** You have to cut it off. Like you have to be okay with picking it back

[00:49:03] **Adam:** up. Yeah. Yeah. It's tough to walk away from flow state. And I guess in those cases, the best advice I can think of for myself is to leave myself a note, you know, write a, write a code comment and leave it uncommitted or something that says like, this is what you were working on, this was what you were thinking of for next steps and, and this is how you should start it back up in the morning

[00:49:23] **Carol:** and hope you're not like Ben and have a backup in case your computer crashes that

[00:49:26] **Adam:** night.

[00:49:29] **Ben:** There's a, uh, a presentation, a couple of presenters, uh, Rich Hickey, who I believe is the inventor of, um,

[00:49:36] **Adam:** oh my God, Clojure. Oh, I thought you were going to say like Jell O pudding or Hickey's. Hickey's. He invented

[00:49:42] **Tim:** Hickey's. Good job. Rich

[00:49:43] **Ben:** Hickey. He's got some fantastic presentations on YouTube and, uh, one of them is called Hammock Driven Development and, uh, kind of dovetailing with what you were saying that he advocates very strongly for.

[00:49:58] **Ben:** Thinking about something very, very heavily and then going off and doing something completely unrelated, like laying in a hammock and, and letting that sort of primed brain work in the background, solving those problems and then go back to work and, uh, and hopefully it comes more naturally. So I, I feel like when I stop at 6 PM every night, I'm often, then it feels like letting stuff just marinate in the back of my brain.

[00:50:27] **Ben:** while I'm watching TV, while I'm sleeping. And then sometimes I just feel recharged

[00:50:32] **Tim:** in the morning and ready to go. Yeah, I just, what you said, Ben, just struck me because it's like, I didn't know that was a thing, but I think I kind of have been doing that, particularly in the springtime. I have a big vegetable garden that I kind of, that's my little hobby to put around.

[00:50:47] **Tim:** And if there was like a particularly stressful meeting, or if I just had like a really Pro, like a, a tough code problem. That's like, I'm sitting there for hours, just just my eyes are bleeding at the screen. , I get up and I'll just go walk outside and start just pulling some weeds or, you know, checking the plants for aphids or things like that.

[00:51:05] **Tim:** Do that for like 10 minutes, 15 minutes, and then come back in. I feel de-stress, right? And then now I can see clearly, you know, the, the issue that I'm working on and that, that really helped me get through some, some rough patches

[00:51:18] **Adam:** there. Yeah, shower thoughts are a real thing. Yeah. And, uh, throw a shower

[00:51:24] **Carol:** beers,

[00:51:24] **Adam:** I hear, yeah, well, you know, but just like Tim saying, pulling weeds, uh, you know, sometimes, you know, just familiarizing yourself with a problem and then completely separating yourself from work can help you find that solution.

[00:51:37] **Adam:** You just have that, that light bulb moment, um, had a few of those in my day. So, one thing I wanted to say before we wrap up is that, uh, we. We don't have any idea how we're going to do show notes or anything like that yet, but I found this, uh, hammock driven development, uh, video from Rich Hickey, uh, on, on ClosureTV on YouTube.

[00:51:57] **Adam:** So I will, uh, assuming we get show notes figured out, I will add it to that. And, uh, and you'll be able to find it to do keeps going.

[00:52:07] **Ben:** If I can plug one more Rich Hickey presentation. Do. It's called, I think it's called Simple Made Easy.

[00:52:15] **Adam:** That

[00:52:15] **Tim:** sounds good. It's

[00:52:16] **Ben:** like really, really deep thinking about what it means to

[00:52:22] **Tim:** build

[00:52:22] **Adam:** software.

[00:52:24] **Adam:** So, I will add both of those to the show notes, and I've already added both of them to my Watch Later playlist on YouTube, so. I'll be checking those out.

[00:52:36] **Adam:** Cool. Well, Carol, you want to bring it home? All right,

[00:52:40] **Carol:** well, I guess with that, that's going to do it for us today. Thank you guys for listening, all three of you.

[00:52:46] **Adam:** Well, there's four, right? We have four moms between us.

[00:52:49] **Carol:** Oh, I have two moms! We just went to

[00:52:52] **Adam:** five! Sweet. And if you like

[00:52:55] **Tim:** this show, please share it with a friend.

[00:52:58] **Tim:** Don't just think about doing it. Pick three names from your contacts right now and send them an email saying, hey, check these guys out. More than anything else, what we need from you right now is word of mouth referrals.

[00:53:09] **Ben:** And after that, if you're still feeling generous, please rate us on iTunes or wherever you happen to get your podcasts.

[00:53:15] **Ben:** It would really help us out.

[00:53:18] **Adam:** And if you have something you'd like to hear us discuss on the podcast, reach out to us on Twitter or Instagram at @WorkingCodePod. Our DMs are open if you want to submit your topic anonymously. Slide on into them

[00:53:28] **Tim:** DMs, yo. Yeah.

[00:53:53] **Adam:** All right. All the jokes you guys made about me while I was gone. You know, I'm going to see that on the recording, right?

[00:53:59] **Carol:** Yeah. We were just wanting to know if it was one or two.

[00:54:05] **Adam:** Uh, you're going to have to pay for my Patreon to find that out.

[00:54:12] **Adam:** I post my, my log, my log log in my Patreon. That's number two. You did a log log. You'll have to find out. You have to become a member.
