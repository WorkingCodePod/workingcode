---
title: "195: When the Juice Isn't Worth the Squeeze"
description: "In this week's episode, the hosts discuss situations where the effort put in is not worth the results."
date: 2024-09-11
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/195-when-the-juice-isnt-worth-the-squeeze/id1544142288?i=1000669133945"></iframe>

In this week's episode, the hosts discuss situations where the effort put in is not worth the results. They cover topics like the inefficiency of tracking every minute, the high cost of striving for 100% code coverage, and handling lengthy build times during deployments. The team debates the importance of releasing features incrementally versus deploying massive changes and highlights the inefficiencies in requiring extensive requirements documentation.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/195-when-the-juice-isnt-worth-the-squeeze.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** you know, we had a customer who was like, we absolutely need this functionality and we need it by June 1st.

[00:00:06] **Adam:** We just got a hotel in that town so that we could be away from our families. And we went and we worked. As close to 24 hours a day as we could manage, right? Like we had bosses bringing in pizzas and we would just sit in the lobby of the hotel and code, code, code, code, code. And we, you know, we finished it like the week to spare or something. And they didn't use it for frigging six months.

[00:00:24] **Adam:** And I was so mad, so mad.

## [00:00:27] Intro

[00:00:27] **Tim:** Okay, here we go, it is show number 195, and on today's show, we're gonna talk about those times when the juice just isn't worth the squeeze. But first, as usual, we'll start with our triumphs and fails. We got the whole crew, Ben's back from being an extrovert, uh, so, uh,You gotta hear about that later.

[00:01:03] **Adam:** Yeah, we'll have to. But, Tim, it looks like it's your turn to go first, my friend.

## [00:01:07] Tim's Fail

[00:01:07] **Tim:** Okay. Well, I've got a fail. I've got, you know, how, you know, in, we talked, clean code, but you shouldn't be lazy. Put things in the right place. I didn't do that apparently, passed me, was coding lazy and just decided to, I had a nice function for it. It was great, it was a good function, but, it was just hard coded data that I returned afterward, just being lazy.

[00:01:31] **Tim:** And that kind of totally bit me in the butt today. I had to completely refactor and the refactoring turned out to be a lot harder than I thought. I'm like, oh, okay. I can just refactor that one function. No, no, I really couldn't do that. So yeah. And I, when I was doing it, I'm like, I felt dirty when I originally wrote that function.

[00:01:46] **Tim:** I'm like, this is dirty. This is really dirty. This, I was like, you know what? I can't think of a case where this is going to hurt me, but, maybe it will. And today it did. So yeah, bad Tim, don't do that. You better.

[00:01:59] **Adam:** This is a totally aside thing, but it's just, you know how we like to talk about, you know, just doing random stuff to learn from it and have fun. Um,as you were describing, you know, like, this hard coded response, it just reminded me, I think there was like an XKCD comic or something where it's like, you know, an implementation for a getRandomNumber function, and it's just like return 7.

[00:02:19] **Adam:** Mm. You know, it's a comment, uh, you know, determined by fair dice roll or something like that. And it, it, it instantly my mind was like, you know what? I bet it would be cool to like build something with like, what is it? The Lego, but it's got like motors and

[00:02:31] **Tim:** Oh, um,

[00:02:32] **Ben:** Servo or something?

[00:02:34] **Adam:** uh, Mindstorms.

[00:02:35] **Adam:** Um,yeah, so to build something where you like have like a dice tower and you have a, like a little webcam pointed down at where the dice rolls out and you have like, you, you know, you use Legos to, I'm sorry, you use Lego. There's the plural of Lego is Lego. You use Lego to like catch the, the die when it's done rolling so that the next time that you need a random number generator, you can like conveyor belt it up to the top of the dice tower and drop it in again.

[00:02:59] **Adam:** And then you like use machine vision to see the dice value. That would be so fun to just like have a. A random number generator actually rolls a die.

[00:03:09] **Tim:** know, I would love to figure out how your brain works. Cause I don't have no idea how, where, where I got, where I came from, that you got to there, but

[00:03:18] **Tim:** Hey,

[00:03:18] **Adam:** ADHD.

[00:03:19] **Tim:** okay, baby.

[00:03:20] **Ben:** Wait, so I think Stripe actually has something

[00:03:24] **Ben:** similar. Don't they

[00:03:25] **Adam:** know exactly what you're talking

[00:03:25] **Ben:** wall of lava lamps or something?

[00:03:28] **Adam:** I believe that's CloudFlare.

[00:03:30] **Carol:** Cloudflare. Yeah. Just saw that this week.

[00:03:32] **Tim:** That runs their random number generator. That's

[00:03:35] **Adam:** it's a whole wall. It's like, you know, 50 or something like that, lava lamps, and they have like a webcam pointing at it. And so they use that as like a input for the entropy for their random number generator.

[00:03:46] **Ben:** That's awesome.

[00:03:46] **Tim:** Using analog to do some digital. That's pretty cool. Anyway, that's, that's my fail. Bad Timmy. Be better. How about you, Adam?

## [00:03:54] Adam's Fail

[00:03:54] **Adam:** I am also going to go with a fail.and my fail is a pretty simple one this week. I'm just going to say, I am a to do list item hoarder. You know, I put a lot of effort sometimes into having a good system for keeping track of the things that I need to do. I'm pretty good about putting things on my calendar when they do have a fixed Time and date and location, right?

[00:04:14] **Adam:** Like I need to go to the dentist. That's on my calendar. I'm not going to miss that. But I've got hundreds and hundreds of items on my to do list that are just like, I know I need to do them to do them, but I just haven't gotten the motivation to do it yet. And it's like, it like, for example, fix my Backblaze backups.

[00:04:30] **Adam:** I've been paying for Backblaze for like 15 years. And I'm pretty sure that it's still backing up my wife's computer, But I've switched computers so many times and it's like, I can't, I could just hook it up to my laptop and say, okay, go back up this machine, but then I would lose all the data that they have backed up for my previous machine, whenever the last time that I was doing backups with them is.

[00:04:53] **Adam:** And so like, I know I need to go in and like download a copy of all the old data and, you know, kind of dig through it, decide what to keep, what to throw away, store that stuff somewhere, and then just kind of do like a fresh reset and say, okay, here, back up my machine. But I haven't done that yet because it's just not urgent yet.

[00:05:09] **Adam:** I haven't lost my machine. and so it's just, that's an example of one thing that's sitting on my to do list because it feels important, but it doesn't feel urgent. And so I just haven't gotten around to it. And I just, my to do list is like hundreds of those things. Plus, you know, the things that I need to get done today and this week are kind of hovering at the top of that list, but it's just, I'm broken and I don't know how to fix it.

[00:05:33] **Adam:** Like I feel like, so I've been, I even paid, this is how much I like care about getting a good system. I paid for the things app, which is not cheap, right? I paid for the desktop one and the mobile phone one,

[00:05:45] **Carol:** Oh, you've doubled.

[00:05:47] **Adam:** I did. and, it has a concept of like a someday list, right? So you can just push those things off that these things that I'm describing probably should go on the someday list, but my problem is I never look at the someday list, never.

[00:06:00] **Adam:** And so I know if I put it on there, it's just going to go there to die. And so I, like, I don't want these things to die, but they're just sitting rotting on the vine with the rest of my stuff. So I am broken. send help.

[00:06:12] **Ben:** You know, I

[00:06:13] **Tim:** Kind of think of it as like, you know, like your little micro diary. You look back over the years and go, look at all these things I thought I could do that I never did. I remember, I remember when I was young and full of energy.

[00:06:24] **Adam:** The list of regrets.

[00:06:27] **Ben:** I was thinking about, I think it's the getting things done framework where one of the bullet points is if a task comes up and it would take less than two minutes to do it, you should just stop and do it. And I don't know when that framework was first published as a, as a methodology. It occurred to me the other day when I was driving that so much of today's tasks have become digital and readily available that with that same rule, does that same rule even make sense anymore?

[00:06:57] **Ben:** Meaning like so many things could theoretically be done in two minutes that if you had to stop and do every task that you could do in two minutes, it would be this like death by a thousand cuts.

[00:07:07] **Adam:** Well, I mean, I guess you have to also in that system kind of use the context of like, what are you in the middle of right now? Right. You're not gonna stop and, and, you know, fill out a survey that's important to you that only take a minute to fill out if you're on the highway. Right.

[00:07:23] **Ben:** Right, right. I'm just, I just wonder if that rule or if that rule of thumb even still makes sense in today's fast paced world,

[00:07:32] **Adam:** Maybe, I mean,

[00:07:33] **Carol:** meaning like it's on your list. It was like, Hey, I need to talk to my mom. Well, now I could just shoot her a text and say, Hey mom, hope things are going good.

[00:07:41] **Ben:** Right.

[00:07:41] **Carol:** that's done. Like that's checked off. I don't have to make that call. That's going to take 30 minutes.

[00:07:46] **Ben:** Just even the idea of responding to an email, you know, there was a time in life where responding to a message may have involved, you know, sharpening my quill and making sure my ink bucket is full and then unrolling my parchment paper and, and, you know, blotting paper when the ink, you know, there's, there's a lot involved.

[00:08:03] **Ben:** And now it could be like, I could take 30 seconds to respond to this email. Does that, Does that reduction in overhead mean that I should actually do it? I'm not arguing for or against. I just wonder if it feels like maybe that's not a valuable way to think about things anymore.

[00:08:19] **Adam:** well, okay. So to answer your question that you had, unintentionally posed earlier, getting things done was, first published on January 1st, 2001. So there's a guy.

[00:08:29] **Carol:** 23 years ago.

[00:08:31] **Adam:** is a, this is a guy who had his ish together, right? Like, you don't publish a book on January 1st, 2001. Unless you planned to do that, right?

[00:08:41] **Adam:** That was no accident. and, so I, I've kind of read the book, I guess? I, I forget exactly where I got it, but I got a, an audio recording of a seminar that he did, like, I don't know, 10 years ago or something like, or no, It was very clearly in the 80s actually, like you can tell from the music that they put in between, you know, like during breaks and stuff.

[00:09:02] **Adam:** and so I listened to this whole thing, which was basically like a copy of the book, but you could like, you know, listen to the whole thing in eight hours or something like that. and it made a lot of sense, but also it just like, he talks about carrying around a little binder with different folders for like, you know, this is, Stuff that I have to do at the computer.

[00:09:18] **Adam:** And this is stuff that I have to, and like, everything goes on a piece of paper. right. So if you're, his system was like, you know, it doesn't matter if it's a computer task and I am notified of it digitally. Like if it's something I need to do, it goes on a piece of paper and it goes in the folder. I don't care if it's on the back of an envelope or a restaurant napkin.

[00:09:34] **Adam:** Like it goes onto something physical and into my binder. And then

[00:09:38] **Tim:** What a dork.

[00:09:40] **Adam:** I'm not disagreeing,

[00:09:41] **Tim:** What a dork. Live in the moment, buddy. Come on.

[00:09:44] **Adam:** get it, get a digital to do list so you can put 10, 000 things on it and forget about all of them.

[00:09:48] **Tim:** There

[00:09:49] **Carol:** them, right? Yeah. But paper is great. Like I love putting my notes on paper because my phone distracts me. If I get on there to like change my list, suddenly I am three apps in on something else and responding to messages and remembering I didn't pay a bill. So if I have it on a piece of paper, there's no distraction.

[00:10:07] **Carol:** I'm like, Oh, this is it. Walk with this in front of my face. Nothing else is getting in the way. This is what's happening right now.

[00:10:13] **Adam:** I have this idea. Yeah. So I, it's an idea of, I guess, for like an app or some sort of thing that could be in your life that would be helpful. But I just don't think that technology is possible right now. So I, I struggle with the same thing, Carol, with distractions. And sometimes it's not even distractions.

[00:10:29] **Adam:** It's just like, here's an urgent thing. And then while you're working on that urgent thing, here's a more urgent

[00:10:32] **Carol:** Yeah.

[00:10:33] **Adam:** Like work on this instead. And then while you're working on that one, okay, now I need this first. So, you know, I've got three urgent things on my stack, right? I'm thinking, you know, the, the technological, data structure of a stack, and so I'm thinking like, okay, you can push stuff on, but it always goes on top and then.

[00:10:51] **Adam:** I want to pop off the next thing. So I have this idea. I just want like, I want a,some way to keep track of what I'm thinking about, what I'm working on as a stack. So that at any time I can just say, okay, this is what I'm working on. And I am, I can pop the thing off when it's done. And I know what I should go back to next.

[00:11:08] **Adam:** Cause that's where I mess up. It's like, okay, I'm, I work on the thing and it's like, okay. Crap. What was the other really, really important thing that now I'm supposed to be doing? And like, I think the reason that doesn't work for me, like, you could just go write it on a piece of paper or whatever, right?

[00:11:22] **Adam:** Start at the bottom of the page and work your way up instead of top down. But I needed to be faster than that, right? I needed to, and I can't alt tab. Siri, stack push this, right? And then, Hey Siri, stack pop. And that would be, I think the only thing I can

[00:11:40] **Tim:** Yeah,

[00:11:41] **Tim:** I see what you're saying, some sort of like digital assistant that like hides all the distractions from you and just say, Hey Siri, what's the most important thing I need to work on right now? And

[00:11:48] **Tim:** she tells you,

[00:11:49] **Adam:** Yes.

[00:11:50] **Tim:** and then, and then it's like, you get no other notifications and then, okay, Siri, I'm done with that one.

[00:11:55] **Tim:** What's next?

[00:11:56] **Adam:** Yeah.

[00:11:57] **Carol:** or what was I just on? You know, like, what did I walk away from?

[00:12:01] **Tim:** Yeah. Hey Siri, I, I, I got distracted. What was I working on? That was the most important thing. And then

[00:12:06] **Carol:** That would be amazing.

[00:12:07] **Tim:** actually

[00:12:08] **Tim:** my,

[00:12:08] **Adam:** start going again?

[00:12:09] **Carol:** Uhhuh.

[00:12:10] **Tim:** my phone is like, there we go.

[00:12:15] **Carol:** Awesome.

[00:12:16] **Adam:** We got way off the rails there. Who was, who was in there? What?

[00:12:18] **Carol:** You. That's you, now it's Ben's

[00:12:20] **Tim:** was you.

[00:12:20] **Adam:** Okay. Okay. So that's all I got. Ben, what do you got going on?

## [00:12:24] Ben's Fail

[00:12:24] **Ben:** I am also going to go with a failure, which is just that I

[00:12:27] **Tim:** three in a

[00:12:28] **Ben:** continue to be and have always been my entire life, terrible at responding to people. And I just don't know how to get on top of it. I, what, what happens to me every time is I'll, a message will come in, email, slack, what have you, and I'm not ready to respond to it because I'm probably doing something else, but okay.

[00:12:49] **Ben:** I'll get back to that later. And then later comes and I say, ah, I can't deal with that right now. I'll do it in the morning. And then before I know it, I've lost two weeks and I swear 90 percent of my responses to everybody is sorry for the late reply. Yada, yada, yada. And I, and

[00:13:10] **Adam:** and write it down on there and then put that in a binder.

[00:13:15] **Ben:** I, I really do want to be better about responding to people. I genuinely feel bad about it. I think it is a shortcoming of mine and has always been. I just. Cannot figure out what to do about it.

[00:13:28] **Tim:** Does it take an emotional tax on you responding?

[00:13:31] **Ben:** it's like exhausting. Even I'll sometimes say, all right, here's what I'm going to do tomorrow morning, I'm going to wake up and for the first hour of the day, all I'm going to do is process inbox emails and whatever.

[00:13:44] **Ben:** I mean, it's mostly inbox and I swear I get past that first email and I feel like I have to take a nap. It's so emotionally draining and I.

[00:13:55] **Tim:** I, I, I'm the exact opposite of you. I am a very fast responder. A lot of times, sometimes my response is, Hey, thanks for bringing that up. I can't handle that right now. I can't deal, you know, I'm in the middle of something. If you don't hear from me in like five hours, message me again. And I put the onus back on them because that's the thing, you feel that burden of the response, but they ask you, particularly when it's, they're asking you for something.

[00:14:20] **Tim:** I have no problem with just flipping it around, doing that UNO card on them,

[00:14:24] **Tim:** doing a reverse.

[00:14:25] **Tim:** Yeah. UNO reverse. And it's like, Hey, I, you and, you know, they injected on me. I'm like, I can't deal with this right now. I'm give me about five hours. If you don't hear from me in five hours, message me back and remind me.

[00:14:36] **Tim:** Otherwise I will forget.

[00:14:38] **Carol:** Yeah. Just know it's gone.

[00:14:40] **Tim:** And just, and then I don't, it just cleans off my plate, right? It's like, I don't have to worry about that. If they don't message me back, I got, I've got an email thread or a message thread or whatever that says, well, you were supposed to hit me back and you didn't, so on you, buddy,

[00:14:54] **Ben:** you know what I mean? That's such a power move. I love it.

[00:14:57] **Adam:** If, if I got that email from you, I might reply back. Okay. If you, if I don't remind you in five hours, let me know to remind you.

[00:15:04] **Tim:** that's what my wife does. My wife totally does the reverse. Oh, no. She's like, she's like, yeah, I probably won't remember that. So yeah, if I don't remind you of five hours, you remind me. I'm like, no, no.

[00:15:19] **Ben:** So that's my failure. I'm going to continue to work at it. I go through periods where I actually do pretty well at this. And it's oftentimes when I commit to making responses, the first thing I do in the morning. But the problem is, is the moment I have something more interesting to think about, responding to people takes a lot longer.

[00:15:39] **Ben:** To say a backseat is very generous. I think it takes like a distant, 10th car on the train kind of a backseat.

[00:15:47] **Ben:** But

[00:15:47] **Tim:** Damn, I get it. Come

[00:15:49] **Ben:** it's a journey. That's me. Failure. Carol, what do you got going on? Bring us home.

[00:15:54] **Tim:** us from this royal flush of failures.

## [00:15:56] Carol's Fail

[00:15:56] **Carol:** Oh man, I really wish I could, but I am on the same, the exact same train as Adam right now. my to do list just, and we did not plan this. We didn't talk about it. I was in here first. Mine was in before yours, so technically you copied me, Adam. Just saying it.

[00:16:12] **Adam:** all right. I'm going to check that off my to do

[00:16:13] **Carol:** good, good. So my to do list just seemed to be getting heftier and heftier and I keep postponing things and snoozing emails.

[00:16:23] **Carol:** That's my worst like habit I think I have when it comes to organizing my day. His emails will come in and I'll be like, I don't have time to deal with this. Everyone else is working. Like I have to go answer a bunch of people snooze until tomorrow at 8 AM. And all of a sudden it rolls around to the day, like today, where I have 15 emails.

[00:16:43] **Carol:** I really need to go through and I need to pay attention to and focus on, but there's a lot more happening. So it's just getting like a bit overwhelming with the delaying to do's and I've got to get better about it. I told one of my coworkers, I was like, Hey, just so you know, I took everything you said down on a post it note and I've moved it to my real to do list.

[00:17:05] **Carol:** So I think that's a win. I was like, I think I'm just going to call it that like mental victory that I've taken it from one place and put it on a to do list. I will actually work on.

[00:17:16] **Tim:** So let me ask you, is, is it the same reason for Bend is like emotionally taxed you to like respond to this? Or is that you just genuinely just don't have enough time? Yeah.

[00:17:26] **Carol:** that. Like emails have come out for us to go learn Bicep and learn some things with GitHub Actions. And in the middle of the migration, I didn't have time to go learn those things. I needed to focus on getting things working because nothing was working. So I was on calls all day long with people trying to get things right.

[00:17:45] **Carol:** So I didn't have time to do it. So they just got delayed. And it was also the people I need to meet with about some of the to do items are in these same calls as me. And I know they're just as stressed as I am. So I've had to put things off that typically I'd be like, Hey, can we just talk for 15 minutes in this block?

[00:18:00] **Carol:** Or can I grab you tomorrow? Instead, it's turned into how's next week looking for you? Well, next week was really busy too, it turns out. And the list didn't get any shorter, it just got longer.

[00:18:12] **Tim:** Yeah. Yeah. That's tough. Cause you, you are kind of in a learning phase right now. Yeah.

[00:18:17] **Carol:** Big time in my role.

[00:18:18] **Tim:** It'll get better. It'll get better.

[00:18:20] **Carol:** Yeah, I'll eventually do my to do list.

[00:18:23] **Ben:** I feel like I have one emotional spoon in my drawer. You know, we talk about the spoon

[00:18:28] **Tim:** Oh yeah. Spoon

[00:18:28] **Ben:** Just like, I got one. If I have to deal with one person, that's it for the day. The rest of it is just me and my own head.

[00:18:35] **Tim:** Yeah. I want to, I want to hear the after show. I want to hear about your, meetup you went

[00:18:38] **Ben:** Oh, sure. I'd also like to say that we could treat this Triumphs and Fails like shooting the moon in, what is that, hearts? Where if you get, if we all have a failure, then that is kind of a triumph.

[00:18:50] **Tim:** Okay. I like that. I'll take it.

[00:18:53] **Adam:** been a long time since I've played hearts, but that sounds vaguely familiar.

[00:18:57] **Ben:** Yeah. I haven't played cards in like 15 years.

[00:18:59] **Carol:** I'm going to say like Yahtzee, it's four of a kind. That's good for something,

[00:19:02] **Ben:** There you go. Yeah. It's a blush or something.

## [00:19:06] When the Juice Isn't Worth the Squeeze

[00:19:06] **Adam:** with that out of the way, let's do the topic for the day, which is, I believe, Ben, you said that, in lieu of. Getting another job after you get, canned from InVision, you're going to start laundering money?

[00:19:19] **Tim:** I think it's pretty sure what he said. Yeah.

[00:19:21] **Adam:** Yeah. Yeah. Okay.

[00:19:22] **Ben:** sounds, that sounds to me.

[00:19:23] **Carol:** Bad way, right?

[00:19:24] **Tim:** Yeah.

[00:19:25] **Ben:** Absolutely. I had listened to an episode of the Freakonomics of Everyday Things, which is a fantastic podcast, part of the Freakonomics Network. It's like a short 12 to 15 minute show about all kinds of random stuff. And they had an episode recently about money laundering.

[00:19:41] **Ben:** And they were saying in the show that even from the government's perspective, that the perfect amount of money laundering is not zero, because in order to have a zero money laundering policy, you'd actually have to put in so many regulations and slow down so much commerce that It would be a net loss, not a net benefit.

[00:20:02] **Ben:** And it occurred to us that there are a lot of things in our lives where a hundred percent effort is probably not the right amount of effort. And, I guess that's what we're going to be discussing today.

[00:20:13] **Tim:** Yeah. Yeah. Cause you brought that up earlier and I was thinking about that. It's like, so in the banking regulations that if you. Deposit in some sort of increments. I don't know what the timeframe is, like 10, 000 is the magic number. So if you're putting 10, 000 into a bank account, it triggers a review by the bank every time.

[00:20:34] **Tim:** So it doesn't matter if you like put 5, 000 in today, maybe 5, 000 in tomorrow. Or you break it up into, you know, a hundred different transit. It doesn't matter. It doesn't matter how you stack it.

[00:20:45] **Ben:** So they actually,

[00:20:47] **Tim:** 000, they review it.

[00:20:48] **Ben:** they mentioned that on the show and I, and I think they called stacking. And, and that is actually illegal. So it's not just that it will trigger an alarm, but trying to do that is illegal.

[00:21:00] **Tim:** Right. But, but only if the. If there is a possibility that there's, money laundering going on, right? Oh yeah, money laundering. I've moved 10, 000 before

[00:21:10] **Ben:** No, no, no. So there's nothing wrong with moving 10, 000. The, the illegal action is trying to break it up into smaller amounts in order to avoid the

[00:21:19] **Adam:** To hide the fact

[00:21:20] **Tim:** to hide, yeah.

[00:21:21] **Carol:** Oh gosh. I think I'm going to jail, you guys. So let me just tell you why real quick. You guys remember a few years ago, I was the treasurer and the president of the booster club for the band, right? So high school bands in the States and in Georgia make a lot of money at football games. Selling food to people, working the concession stands.

[00:21:43] **Carol:** All of that is ran by the boost organization for the band. That's how they fund the band for equipment, for instruments, for uniforms, for all that stuff. Right. So it'd be nothing to bring in, you know, 10 in one night just from a football game. And I had heard from the previous treasurer that not to put more than 10, 000 in one deposit so we didn't get flagged for taxes on the IRS stuff.

[00:22:08] **Carol:** So of course I didn't know. Granted. That year we also hired an accountant and they're also, you know, tax exempt now. There's a whole lot going on with it. They're way better now. But I was like, okay, 9, 000 in one deposit. Tomorrow is the rest of the money. I never really knew like why I couldn't do it. I probably should have looked a little better.

[00:22:27] **Carol:** But I think I might be going to jail, you guys.

[00:22:29] **Tim:** Yeah.

[00:22:29] **Ben:** All right, well, we'll, write and put money in your commissary.

[00:22:32] **Adam:** Yeah. I was going to say, I was gonna say the same thing and we'll put it in 9, 000 at a

[00:22:35] **Carol:** Yeah.

[00:22:36] **Tim:** All the special flavor Pop Tarts, they'll be yours. You can trade them. Yeah, and cigarettes you don't smoke, but yeah, you can,

[00:22:41] **Carol:** I'll try them. Yeah. Yeah.

[00:22:43] **Tim:** them. There you go. And, and credit card fraud too. So that, I mean, that's the, the same thing. It's like, it's, you can never stop a hundred percent of fraud and people will do chargebacks, right?

[00:22:53] **Tim:** People will legitimately buy something with the intent of, I'm just going to charge it back. And just, I'm just going to say, oh, I didn't get this thing or whatever, you know. There's some industries that are very high chargeback rates and credit card companies know that. So if you're in those certain industries where there's just a high level of chargebacks, they just up the interchange on that, just the merchant, basically whoever the store is taking credit cards, they're paying more in credit card fees to cover that, and then they go, yeah, you know, we're going to stop 100 percent of this fraud, so we can't bother stopping it, so we'll just factor that into our.

[00:23:31] **Tim:** Bottom line. And you know, it just all washes out. So that's another area where the squeeze just ain't worth the juice.

[00:23:38] **Adam:** It's like when you try to balance your budget and you come up like 2 cents off and you're like, you know what? It's not worth my time to, to try and find that 2 cents. Where did it go? So, you know what? Just call it even like put in a,

[00:23:49] **Adam:** Just put in an adjustment to, to make it balance and then you're done.

[00:23:53] **Tim:** accountant's at work. Oh my God. Like this is two cents off. I'm like, are you serious right now? I'll, I'll walk over. I'll hand you two pennies. Let's just see. Why are we worried about this right now? This makes no sense.

[00:24:05] **Carol:** It was your Excel sheet I started with. You've got something wrong. It's not my fault.

[00:24:09] **Tim:** Yeah. Ridiculous.

[00:24:11] **Adam:** So let's bring this around to tech then, right? So we've kind of, I think, explained the concept here. So what are some things that people perhaps wastefully, spend time on that are not worth the squeeze?

## [00:24:23] Chasing Every Exception

[00:24:23] **Ben:** I like someone wrote down here, chasing every exception in the exception log,

[00:24:28] **Ben:** and I feel this one very deeply because I have many errors in my exception log that I just, I know I'll never get to because they're doing. Necessarily indicate a critical issue. It's, I mean, half of them are people just trying to break the site by putting weird things in the URLs or putting crazy stuff in form fields and, I'm mostly okay just ignoring those because it would be, just a monumental effort to constantly have to respond to all of those.

[00:24:59] **Adam:** Well, yeah, so I'm the one that wrote that down in our, in our notes here. And the reason I wrote it down is because. I mean, because it's true, but, but the reason that I thought of it was that, initially when we kind of started our company and product stuff, like we have, a, an exception log and with, you know, one customer on at the time and, and not that many users, it was very easy to like stay on top of it.

[00:25:22] **Adam:** You know, an exception would come in and we would go look at it and we'd like send them an email, like, Oh, give me two minutes. I'll have that fixed. and then two minutes later they'd get another email, like, okay, it's good. Try again. And, you know, they really liked that in terms of like customer service.

[00:25:35] **Adam:** Like, Oh, wow, these guys are really paying attention and they're on top of it and they're, they're being proactive. Which was great, but, it's not a viable long term strategy, right? You can't, you can't do that when you get up to hundreds of active users and you've got projects that you need to work on and, and financial things that matter, right?

[00:25:55] **Adam:** you can't chase down, like you were saying, somebody put something weird in a form field or in the URL, and that doesn't matter when you've got like, Oh, the credit card form is behaving weirdly in this one situation.

[00:26:05] **Carol:** Yeah.

[00:26:06] **Ben:** Let me, let me pose this as a question here to the group, because I think this is going to be indicative of a certain size of a company. But I get a lot of joy and fulfillment out of occasionally glancing at the log aggregator. So I don't mean like the raw text log files, but we pipe all of our logs to, something called Logly, but we've used something called Kibana in the past.

[00:26:30] **Ben:** We've used all kinds of stuff, you know, over my career.

[00:26:33] **Tim:** They use Datadog at some point.

[00:26:35] **Ben:** we use Datadog at some point. And I like to go into those dashboards and every couple of hours, just refresh them to see what the most recent hundred errors were just by kind of a summary. And it gives me kind of a sense of a natural pulse of the errors in the system so that when I do see an error that I haven't seen before, It stands out a little bit more, or just, I get a sense of, Oh, this comes up once every couple of weeks.

[00:27:03] **Ben:** I don't have to worry about it. Or it comes up a couple of times a day, or it happens to cluster around deployments. So it's probably just some weird things getting taken out of the load balancer. It could be better, but not going to worry about it right now. and I know you could say that, Oh, a lot of logging tools have alerting built in and, and,anomaly detection, but I don't know, I love going in and just looking and exercising.

[00:27:27] **Ben:** The pattern matching muscles of the human brain. Is that crazy?

[00:27:33] **Carol:** A little. Yeah. Yeah.

[00:27:35] **Tim:** You should see a doctor.

[00:27:36] **Carol:** huh. You need help. See, I'm the opposite. I go in there and I, I'm really glad that we have the ability to see the logs and when something's happening, I can see, you know, several days and I can see if this was a trend, if something was going on, but if I were to just go in there and look at the logs.

[00:27:55] **Carol:** I know that we're saying we shouldn't squeeze like every ounce out of this juice or I mean out of this lemon, right? But I straight up would have the urge to start putting in ADO tickets. I'd be like, this is happening a thousand times a week. We're going to go fix it. Like, in reality, someone is just logging something wrong and it's not even a problem.

[00:28:15] **Carol:** But I'm like, okay, our command handler got hit. That's great. It's supposed to get hit. It's a command handler. Like, why are we adding any kind of exception in there? Like nothing is happening. It's doing what it's supposed to do. So then I would just be more stressed out. I would not be happy in there.

[00:28:30] **Ben:** Fair enough. Fair

[00:28:31] **Tim:** I mean, I mean, Ben, if you just want to ignore them, what do you could actually do is just have it email you the error every single time, and then, you know, you, you might get one of them every day. And then after that, you'll be too tired.

[00:28:42] **Carol:** Yeah.

[00:28:42] **Ben:** My spoon has been spent.

[00:28:46] **Adam:** So, I mean, I guess the obvious one too, we should mention is code coverage, right? So like writing tests and trying to get to a hundred percent code coverage, right? I think most people would agree that that's just a, if. A fool's errand or, you know, juice not worth the squeeze, like, those last five percent is just, you know, you're, you're chasing for the purpose of making the number go up, not because it's actually helpful.

[00:29:12] **Carol:** Yeah, it just turns into a making it do it, not that the tests actually serve a purpose. Like, that's the, the common thing that I see too, Adam. It's not fun. Yeah, I'm gonna, I'm gonna throw one out there.

## [00:29:24] Delivering Features All At Once

[00:29:24] **Carol:** I have realized over the past year that developing giant features just to get absolutely every possible thing that they want included and delivering all at once is a very bad idea.

[00:29:38] **Carol:** You should definitely do small things and you'll get bigger wins than if you try, you know, getting everything that the customer wants in one big giant release.

[00:29:47] **Tim:** Now that's funny. I thought Ben put that on our list. That's a 100 percent a Ben thing to say.

[00:29:53] **Carol:** no.

[00:29:53] **Ben:** That's feature flags all the

[00:29:55] **Adam:** I was going to say, he would have mentioned feature

[00:29:56] **Ben:** Yeah. Yeah,

[00:29:58] **Carol:** Yeah, during this migration, I was like, Oh God, my code hasn't merged yet. What are we gonna do? I'm gonna have to manually do all this stuff into GitHub because we just, we migrated from on prem to GitHub Cloud Enterprise. So now we're up in the cloud like everyone else. but my code wasn't in the branch yet and hadn't been scanned.

[00:30:17] **Carol:** So I was like, what am I going to do? I guess I'm going to have to do it. And one of the developers goes, Oh, is it not behind feature flags? And I went, wait, what? We have feature flags? And the answer then goes, Oh, I mean, you know, those toggles that we've added. I'm like, no, I didn't go put toggles on everything.

[00:30:34] **Carol:** And I was like, can we talk about feature flags? So yeah.

[00:30:38] **Tim:** Yeah, I read something that kind of You know, Ben has kind of been saying this for years to me and I'm like, yeah, okay. He's just, you know, being a little lazy, but I read an article, sorry Ben, I love you, but read an article and basically put it in the context of benefit to the end user and quicker you can get a change, an update, a bug fix to the user, the more value over time that thing is, right?

[00:31:07] **Tim:** And so if you have it hidden, if you have it lumped in with this huge group of features, it's all just, you know, it's just going to sit there. It's like not putting your money in the stock market when it's hot, right? It's like you're taking on this big wad of money, you're holding it in like a low interest savings account, and then you're just, Yeah, your mattress and you're waiting cause you're money laundering and you're waiting to like shift that into the market.

[00:31:30] **Adam:** You're waiting until you have 10, 000.

[00:31:32] **Tim:** Exactly. Yeah. So, but, so you're not, but during that time where you're waiting, you're not getting value out of that. And you're, and, and that's sort of the same thing with that is if you can do super small releases where you can get it into, not just into staging or QA or whatever, get it into production as fast as possible, that's going to benefit your users.

[00:31:52] **Tim:** And you're also going to get feedback from what you're doing. And that really sold that idea of you don't, you know, don't pile them all up together in this huge, which is one of the things I don't like about the whole two week sprint release, right? Why can't we roll it out? You know, you do something now it works.

[00:32:08] **Tim:** It's been tested. Why do we have to wait two weeks? Let's get it out right now.

[00:32:11] **Ben:** Fact.

[00:32:12] **Tim:** That's kind of what, kind of what I do, but you know, we have a small team and we can like, you know what, this works. So we tested it, it approved, passes PCI test. Let's roll it into production.

[00:32:21] **Tim:** And then tomorrow you're like, what do we got to post anything today? No. Okay. Tomorrow. Yeah, we got it. It's value to customers.

[00:32:29] **Adam:** Absolutely.

[00:32:30] **Ben:** And if I can piggyback on this as well, one thing that I have changed my mind over, over my entire career is that when I used to think about building a solution for a customer base, I felt like the solution had to work for everybody. And what I have come to realize as a more mature programmer is that solutions can be more targeted, that my version one of a solution might only work for a small subset of the users, but that's at least gives me a foothold.

[00:33:02] **Ben:** Into something, to Tim's point, that I can start to get feedback and improve. And if I can make it great for a small set of users, maybe I can start to expand it to encompass more people, or maybe we just decide that different solutions work better for different types of customers and we, and we go from there.

[00:33:19] **Ben:** This old idea of, of kind of, I started to call it just consistency for the sake of consistency has, really worn on me and, I try not to think too heavily about it anymore.

[00:33:32] **Tim:** Okay. I'll go. so time tracking, you know, I, I get it, you know, managers, they want to know where the time's being spent. They want to make sure there's billable hours being billed, but you know, whatever your Tracking, like how many times are we sitting in meetings? And so we have a special code for that, that you go in there and it's like, then do you actually have to track the amount of time where you're just tracking your time?

[00:33:57] **Tim:** And that seems like our infinite turtles all the way down kind of thing that just goes on. You know, time tracking should be just kind of a smell test of, you know, in general, where are we spending our time? What are we doing? You're not going to get a hundred percent snapshot of what every single person is doing.

[00:34:14] **Tim:** And it's a terrible, terrible metric to try to figure out who is like, not doing their work.

[00:34:20] **Carol:** Oh yeah. That's really bad.

[00:34:21] **Tim:** If you, if you're like, oh, I want to track their time because I don't think they're doing their work and I want to fire them. That's terrible. That's not the way to do it. People, people who don't want to do their work, they're really good at not doing their work and making it look like they're working.

[00:34:34] **Tim:** They're really good at faking it. So you're never going to catch them. You're just going to aggravate the hard working people who are just trying to get stuff done and are upset because you're making them do this ad infinitum time tracking. So use it as a general smell test. And you catch the cheaters by seeing what they actually do.

[00:34:51] **Carol:** it was produced. Yeah.

[00:34:52] **Adam:** Yeah, what, show me what you've done. Show your work. It's like math class. Show your work. How'd you get there? warlock in World of Warcraft is now a level 70.

[00:35:02] **Tim:** exactly. Yeah. Okay. Well, you have plenty of time to level him up to 90 because you're fired. So yeah, that is, that squeeze ain't worth the juice.

[00:35:11] **Adam:** Or the juice isn't worth the squeeze.

[00:35:13] **Tim:** No, you know what, I, the effort is more important to me than the actual amount of juice, how hard I have to squeeze. That's like, yeah, I'm not, yeah, I'm not, yeah, I

[00:35:22] **Ben:** It'd be great if there was some metric that you could look at at a business and decide. Basically saying, we live and die, but whether or not this metric goes up or down, and everything else is just noise, meaning, you know, how in depth are your tickets being outlined, how well are you tracking, what hours are you coming to the office, like if this golden number continues to go up, then who cares what you're doing, like whatever you're doing, just keep doing that.

[00:35:50] **Ben:** And I know it's vastly oversimplified and businesses don't run quite that smoothly and they don't all roll up to a single metric like revenue or monthly active users or number of support tickets. It's probably to a great degree, much more nuanced, but.

[00:36:08] **Adam:** I mean, and I mean, obviously you're going to run into good hearts flaw there too, right? When, whenever a measure becomes a target, it ceases to be good measure.

[00:36:14] **Tim:** mean, so maybe at a higher level. So Constellation, the company that, that owns us, they very much have metrics. So they say your amount of percentage you should be spending on sales and marketing should be between this metric. Your amount that on R&amp; D should be between this metric. Therefore you should expect this amount of organic, you know, and they have all the, I mean, as much as I hate that it's, you know, they're very much an accounting company rather than a software company, those metrics work.

[00:36:45] **Tim:** I mean, it's like, you're like, you know, why, why aren't we growing? Well, how much are you spending on sales and marketing? Well, you know, where it's less than 4%. Like, well, you should be spending 10 percent on making those numbers up.

[00:36:56] **Carol:** Yeah,

[00:36:58] **Tim:** cause all those numbers are proprietary. So, uh,but yeah, so they have these metrics and you know, if you can hit them right, it's like when things are going well, you're like, Oh, look at that.

[00:37:08] **Tim:** Our numbers are exactly where they should be. That's exactly. Yeah. Look at that. That's awesome. So, but they don't get down to the minutiae about software development, right? That's more of a,

[00:37:16] **Carol:** right.

[00:37:18] **Tim:** their, their metric is giving value to stockholders.

[00:37:22] **Carol:** Yeah. Sometimes those numbers don't take into account like. Is your code maintainable?

[00:37:26] **Tim:** Right. Yeah. A hundred percent.

[00:37:28] **Carol:** can you re platform and everything not just die? Like what happens if we decide to go from on prem to the cloud? Like, is it going to shut us down for months because nothing's going to work? You know, like that, those numbers don't take into account like the technical side of things that are needed to, to keep us in the future, so, and that kind of sucks.

[00:37:47] **Carol:** It's hard to get that through to people sometimes.

[00:37:49] **Tim:** awesome. Those, those numbers don't measure if you're a healthy company. Those measure if you're a profitable company

[00:37:55] **Carol:** Yeah.

[00:37:56] **Tim:** and those two are not the same.

[00:37:58] **Ben:** Well, Carol, you just mentioned something there that triggered a thought in my head. You talked about replatforming from on prem to the cloud. And it occurs to me that one of the ways that can be done maybe more easily is to have the right abstractions within your software. But that's another thing where I sometimes feel like the juice isn't worth the squeeze.

[00:38:20] **Ben:** I spend so much time from time to time. Thinking about where's the exact right boundary between these two things. And I do a lot of hand wringing and I move code here and then I move it back over there because I'm trying to find that really clean layer that's the separation of concerns. And I feel like I could have actually spent all of that time just writing code and not worrying about having the most perfectly elegant solution.

[00:38:44] **Ben:** And I, I guess maybe to step back even more and just say, sometimes elegance isn't. Worth the effort. Sometimes just ugly, disgusting, get it done. Code is the right type of code for the moment.

[00:38:57] **Carol:** Hmm, is it? I mean, I

[00:39:03] **Ben:** man, I am not winning today at all.

[00:39:05] **Carol:** No, no, I completely get what you're saying. Like, there have been so many times I'm like, look, there's probably a much more elegant way to handle what I'm doing. But the truth is that I've written it, I've tested it, it works. It's not like costing CPU. It's not losing memory anywhere.

[00:39:22] **Carol:** Like it functions, let's just go. And then we'll come back to it and figure out how we make it more elegant. Like we know it can work this way. What can we do to make changes? But when I think of like, just get it out there, I think of someone, and we kind of talked about this a moment before the show, like today I looked at someone's SQL code and it was like update table, new line set, new line, all the columns, new line, where, and everything was perfectly aligned together.

[00:39:47] **Carol:** There were no tabs for the column names. There were no tabs for the and. There was nothing. I was like, do you think anyone can read this? Oh, I'll fix it. I was like, yeah, please. Cause I, I need, I need to know where my eyes should go because I'm not checking your columns. I'm checking your conditions. You know, I want to make sure that your logic is right.

[00:40:05] **Carol:** So I'm like, at least, at least make it readable. If it's very ugly. Make it readable. Let's hit bin. There you go.

[00:40:13] **Ben:** I can dig it. I'm pro readability.

[00:40:15] **Ben:** so yeah. I mean, I, Ben is so pro readability that he's way in favor of linters. I'm so pro readability. I don't even need a linter.

[00:40:25] **Adam:** Ben is the linter.

## [00:40:26] Checking Pull Requests

[00:40:26] **Adam:** so Carol, you had mentioned something before we started recording about like, doing code quality or security like type checks on every pull request. Can you describe what that experience was like for you?

[00:40:38] **Carol:** Okay. Well, let's start with this just happened last week. I'm still learning all the problems and all of the things that come with moving to the cloud and everything that goes into a government, like. Repo being in the cloud, even though we're a private cloud, it doesn't matter. like every single PR we do has to go through something called CodeQL.

[00:40:58] **Carol:** And CodeQL is the test that runs against it that says, Oh, are you releasing any secrets? Are there any, is there anything in here like the security needs to know about? And then obviously there's Dependabot too. And we were, Behind on like 400 pull requests currently on dependencies that we hadn't updated, which we'll get to, you know, one closes six, so it's all fine.

[00:41:20] **Carol:** So CodeQL is running on like every one of our PRs. So every time we do a PR, rather than our builds taking, they were taking on average like six minutes, I think, on prem. We're talking 28, 38 minutes now per build on a PR. So you put it up, you might as well go work on something else because all of the scanning is just eating through your time.

[00:41:43] **Adam:** And, oh man, I've worked on systems like that when the build takes so long, and That's when I start to like really buckle down and, and get better at testing my change before I commit it and, and get out. Cause I, you know, sometimes when, when you've got these like short loops and you can just like deploy change, Oh, that's not right.

[00:42:02] **Adam:** Let me deploy another one. And it's up in a minute and a half, two minutes. You're like, I feel a little bit more like loosey goosey shoot from the hip. Is okay. But man, when you've got like a almost 40 minute deploy, you imagine you hit deploy and then two seconds later you go, Oh no, I see the problem.

[00:42:19] **Carol:** You can't touch it. That's not even to deploy. That's just to get the ability to approve a PR.

[00:42:24] **Adam:** Oh no.

[00:42:27] **Carol:** You can't approve it yet.

[00:42:29] **Adam:** So, I mean,

[00:42:29] **Tim:** it's the new smoke break.

[00:42:31] **Carol:** PR. Yeah.

[00:42:32] **Adam:** So this thing that that's running on every, PR it's called CodeQL. I assume that's the, the GitHub product CodeQL. Okay, cool.

[00:42:39] **Carol:** think it's GitHub. However, I was kind of

[00:42:41] **Adam:** there is a,

[00:42:42] **Carol:** day and it might not be. Hold on.

[00:42:43] **Adam:** I searched for it while you were talking and there is a CodeQL. github. com. so I assume that's the one. Um,And I don't know anything about this other than that exists and what the URL is, but I have to imagine if it works like other GitHub, like little, like Dependabot, for example.

[00:42:59] **Adam:** and there's other things too, but like, you could probably wire it up so that it runs like just on the main branch twice a day, right? Instead of on every pull request. And that way, you know, like stuff might sneak through, but then you're going to catch it by the end of the day.

[00:43:15] **Carol:** Yep. Yeah, that's absolutely what we're trying to accomplish. However, security is way far outside of my team and sometimes with security and when you're talking about a government agency policy, Doesn't change quickly and it doesn't change because one team isn't happy with it. So I know that they're talking about trying to get it to where it only runs on main and it doesn't run on every PR.

[00:43:40] **Carol:** It's like, there's no reason to have it up there. It would only do it to main and then it would create the, the issues at that point. So hopefully if we get there, it'd be great. But for now we aren't allowed, like I have no ability to do any branch policy. I can't set anything up. That's all handled by another security team.

[00:43:57] **Adam:** So this is, my weekly opportunity to say bless you for helping take care of our government,

[00:44:01] **Carol:** Yeah,

[00:44:02] **Adam:** something I could not

[00:44:03] **Carol:** didn't know that.

[00:44:03] **Adam:** I

[00:44:04] **Ben:** Yo, I can't imagine having to wait that long for a build. If, if I was a CTO of a company and I got hired and I came in and builds were taking 40 minutes, I feel like that would be my only initiative. I'd be like, everyone has stopped what you're doing. No one can do product work until we figure out how to make this build five minutes max.

[00:44:25] **Ben:** I mean, I'm just throwing five minutes out as an arbitrary thing, but that's, I feel like. Maybe I'm going too far out on a limb here, but a 40 minute buildup, that's toxic. I think that's got to deteriorate so much morality and a desire to get work done.

[00:44:42] **Adam:** you just mean morale, not

[00:44:43] **Ben:** Morale. Yes. Morale. Thank you.

[00:44:47] **Carol:** Yeah, it's definitely not fun and we're working on it and we have so many engineers who are doing everything we can to get our pipeline like, like, cleaner in any other way to take away from that. And hopefully we'll get the approval to get it off of our PR soon and it'll just run on main and then that'll be a lot better.

[00:45:07] **Adam:** Well, I mean, hopefully at least us discussing it can give somebody out there who's suffering a similar fate and not stuck behind government bureaucracy, some ideas on how to, make their life a little bit better

[00:45:18] **Carol:** Yeah.

[00:45:19] **Adam:** regard.

[00:45:20] **Carol:** I heard a number, don't quote me on it, because obviously I have no idea if this is right or not. I think that we get 50, 000, like, GitHub Action Minutes a month, is how many we're allotted. And if this continues, we're looking at, this is for like all of our agency. This is like OPM in general, like the big, big overall, right? If this continues the way that it is with the number of devs that we have working on these PRs, we're looking at already eating up 28, 000 of those.

[00:45:50] **Adam:** Wow. Yeah.

[00:45:51] **Carol:** Yeah. So I'm like, someone's going to know quickly, like if that's actually happening, that. We're going to need to get it off of how it's currently set up so that we don't go over budget.

[00:46:00] **Tim:** Mm hmm. That's

[00:46:01] **Adam:** Yeah. I mean, I'm looking at mine. We get, we pay for, or no, I guess it's up to 3, 000 minutes is included. And then you can, we just have like a budget set. Like, never spend more than 15 a month on, on actions or something like that. And yeah, I mean, we're, we're not, there are a few months here and there where we come close to it, cause we're like deploying like crazy and our CFML builds do take more than five minutes, often.

[00:46:27] **Adam:** And that,It's a source of great frustration for me, but all I have to say about that.

## [00:46:38] 100% of Requirements

[00:46:38] **Tim:** I guess the last one here, I put this up in requirements. You're never going to get a hundred percent requirements. From, from, from a, particularly a customer or even like an internal project. it's, it's a pointless endeavor. So if you have a team that their whole job is to get requirements and they're taking a really long time, they gotta, they gotta like, you know, lower the bar a little bit, you're not, you're not going to know everything up front.

[00:47:02] **Tim:** I mean, that's kind of what the agile philosophy was at the beginning, right? That's why it was such a sexy selling point, but people still are like, well, how come this, you know, You know, we had so much problem with this project. Well, we didn't really know what we're building up front. No one knows what you're building up front.

[00:47:18] **Tim:** No one knows. No one knows. The people who think they know what they want, when you give it to them, they don't know what they want until they see what they get. And they're like, ah, that's not what I wanted. So get the, try to get the minimum amount of requirements possible to start working. And then, and then trust, trust people that during the middle of it, if they don't know what they're doing or if they get stuck, they're going to ask for help.

[00:47:42] **Tim:** Yeah,

[00:47:43] **Carol:** when I worked with, with Tim before, one of the things that used to frustrate me with requirements was We would get the request to go, you know, it was the insurance company or it was, it was work software for insurance companies, right? So we would get the requirements to be like, Oh, we're going to go into like this new state and we're going to start writing insurance there.

[00:48:01] **Carol:** And here are the requirements only to find out they haven't even filed it with the state yet or got approval to even file in the state yet. So who knows if these are going to get approved and if this, if this is right or what's going to have to change, it should be like, wait until you file, then let's talk.

[00:48:18] **Tim:** But they want to hit the ground running. I mean, I get it.

[00:48:20] **Carol:** they do.

[00:48:21] **Tim:** I get it. So, yeah.

[00:48:24] **Ben:** If you all had, we, at a previous company, we used to talk about our clients that were hurry up and wait style clients, where everything was an emergency when it was us trying to get materials for them, but the moment they had to respond to anything, it was crickets for weeks.

[00:48:41] **Adam:** Mm hmm.

[00:48:42] **Ben:** You're like, Oh, I guess it really wasn't an emergency then.

[00:48:45] **Ben:** Like you had made it up to be.

[00:48:47] **Adam:** Oh yeah. I mean, we, just to give one example, you know, we had a customer who was like, we absolutely need this functionality and we need it by June 1st. And we, I mean, we, because of that, this was back when the company that I worked for was just three people. We got a couple of hotel rooms and we literally went, In the town that we, like, lived in and worked in, right?

[00:49:10] **Adam:** We just got a hotel in that town so that we could be away from our families. And we went and we worked. As close to 24 hours a day as we could manage, right? Like we had bosses bringing in pizzas and we would just sit in the lobby of the hotel and code, code, code, code, code. You know, you go to the bathroom.

[00:49:25] **Adam:** All right, let's go take a, a three hour sleep break and we'll come back. and code, code, code, code, code. And we, we did, we finished it and it was exactly what they asked for by June 1st. And we, you know, we finished it like the week to spare or something. And they didn't use it for frigging six months.

[00:49:39] **Adam:** And I was so mad, so mad.

[00:49:43] **Ben:** Classic.

[00:49:44] **Tim:** Yeah. Classic. Classic Steve.

[00:49:50] **Adam:** Don't throw Steve under that bus. That's not him. That's, that's our customer. Anyway, sounds like we're about done. Anybody got any final closing thoughts on this, juice and squeeze stuff?

[00:50:00] **Tim:** Mm hmm. Nope.

[00:50:01] **Adam:** Squeezy juice?

[00:50:02] **Tim:** Easy to use.

[00:50:03] **Adam:** Okay, cool.

## [00:50:04] Patreon

[00:50:04] **Adam:** Well then, this episode of Working Code is brought to you by laying on the grass and looking up at your cloud logs looking for patterns.

[00:50:09] **Ben:** It's a dinosaur.

[00:50:11] **Adam:** And listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is, this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them.

[00:50:24] **Adam:** Special thanks to our top patrons, Monte and Giancarlo. You guys rock.

## [00:50:28] Thanks For Listening!

[00:50:28] **Adam:** We are going to go record our after show. We're going to talk to Ben. Ben did a peopling, so we got some stuff to talk about there. and I have a compliance thing that I'll talk about if we have time and interest. So if you're not sure what the after show is, here at episode 195.

[00:50:42] **Adam:** that is basically the outro rules and we're just going to keep talking. And those of you that support us, we'll get to hear what we talk about. And sometimes it's on topic, sometimes it's off topic, sometimes it, involves, DragonCon. You never know. so, yeah, if you want to do that and you want to hear that, you can go to patreon.com/workingcodepod, throw us a few dollars a month and it'll be all yours. We'd love to have you join our Discord. Discord is a lot like Slack if you're a work Slack type person, except it's better, better for communities. and we'd love to have you join ours. It's, it's free and it's open to the public and you can just go to workingcode.dev/Discord. Come hang out with us.

[00:51:18] **Tim:** your kids. They'll tell you.

[00:51:21] **Adam:** They'll tell you all about it. All right. That's going to do it for us this week. We'll catch you next week. And until then.

[00:51:25] **Tim:** Remember, you are readable and not ugly and your heart matters.
