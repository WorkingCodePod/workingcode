---
title: "215: New Endeavours, New Challenges"
description: "In this week's episode, the full crew is back to discuss the challenges and strategies of managing development teams."
date: 2025-05-01
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/215-new-endeavours-new-challenges/id1544142288?i=1000705675429"></iframe>

In this week's episode, the full crew is back to discuss the challenges and strategies of managing development teams. Tim shares his new role as Director of Development and his approach towards improving developer experience and scaling applications.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/215-new-endeavours-new-challenges.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Ben:** Survivorship bias,

[00:00:01] **Adam:** Yeah.

[00:00:01] **Ben:** where it's like the thing that you did may be coincidentally what made you successful? Or it might be causally what made you successful and you have no idea.

[00:00:09] **Tim:** It may be what Adam said earlier that he wanted as a developer is give me a North star. And that North Star doesn't matter

[00:00:16] **Adam:** then light a fire under me. Yeah.

[00:00:17] **Tim:** Yeah, exactly. It doesn't matter that the North Star in from perspective looks opposite from another company's North star. The fact that both of them had one and everyone bought into it led to success.

[00:00:28] **Ben:** that's a great point.

## [00:00:29] Intro

[00:00:49] **Adam:** Okay, here we go. It's show number 215. And on today's show, we got the whole gang back on the show.

[00:00:53] **Carol:** Wow. Hi everybody.

[00:00:56] **Tim:** everybody.

[00:00:58] **Adam:** and on today's show we are gonna talk about new endeavors, new challenges, stuff's going on. but first as usual, we'll start with our triumphs and fails.

## [00:01:05] Carol's Triumph and Fail

[00:01:05] **Adam:** Carol, welcome back.

[00:01:05] **Adam:** You've been away a little bit on a hiatus, taking care of stuff, so it's nice to have you back. why don't we let you go first

[00:01:11] **Carol:** Yeah. So I'll, yeah. Well, I mean, technically I was supposed to go first in the document, but we won't talk about that. Uh, yeah. So

[00:01:19] **Tim:** It doesn't exist.

[00:01:20] **Carol:** I'm gonna go with first atrium, meaning that I'm back and I still have a job. So I was pulled into a meeting and was told, you know, our kind of initial, some riffs are probably done for my organ, for where I work and my piece of, of what I do, and that I can breathe a little easier.

[00:01:37] **Carol:** So, that was just this, this current week or past week. So I feel like now I'm to the point where let's go cause some trouble, right? Meaning, no, I don't even cause trouble, cause trouble, but I've been scared to make big changes at work because I didn't wanna leave my team. Holding massive implementation processes or big changes to how we, you know, branch or how we deploy packages if they didn't fully understand it.

[00:02:04] **Carol:** So I've kind of had everything documented, ready to go. So now that I feel a little more secure, I'm gonna pull the trigger on some of these process changes and made things more efficient for everyone and more, developer friendly throughout the day with what we do. So, super excited about that. But on top of that, I'm gonna throw in a giant fail.

[00:02:24] **Carol:** I don't know what happened, but my control button has stopped working and it is wrecking

[00:02:31] **Adam:** losing control.

[00:02:32] **Carol:** on my life. I didn't realize how often I use control to do actions until now I have to do a right click and I'm just going. My code now just says like, V what just happened to it? I had everything highlighted and it says C or it says V and I'm having to like go into the menu and click undo.

[00:02:51] **Carol:** As opposed to just being able to hit control C. It is destroying my world. And since I can't just plug in another like, a keyboard to my work laptop, right, I have to choose to then either type on my work laptop, which isn't good either, or go without control. So I've had to bounce between neither, neither are good solution.

[00:03:16] **Carol:** So it's wrecking havoc on my mental state, on my physical state. My wrist hurts from right clicking all day. Yeah, so that's a big old giant fail, and I'm gonna have to order a new keyboard tomorrow that's approved for usage.

## [00:03:31] Keyboard Woes and Solutions

[00:03:31] **Ben:** Yo, I've been trying to use some different keyboards lately 'cause I've been having some wrist pain. So I'm just trying different, slightly different layouts and it's, it's like every keyboard is a little different. Every keyboard makes some unique decision about where the command or the control key should be, or like how big the delete key should be or is like delete or backspace the primary action.

[00:03:52] **Ben:** And, I, it, it's really weird. It's like I can still type okay when I go to a new keyboard, but it takes me a couple of days to sort of trick my brain into thinking about just even minor, minor variations. And some of them I just feel impossible to adjust to. so I hope that whatever keyboard you get.

[00:04:11] **Ben:** Does not continue to trip you up.

[00:04:14] **Carol:** I am gonna try to get the sa, I'm gonna try to get approval for the same one, but who knows if they have it right? So.

[00:04:19] **Adam:** I, I feel your pain. And, and to a lesser degree. So, and it was annoying enough for me. So today actually, I went to the Apple store and had them replace a key on my keyboard, on my, on the like keyboard built into my laptop. Because the J key, you know, you just lightly rest your fingers on the home row to start typing, right?

[00:04:36] **Adam:** You've done something with a mouse or whatever. You reach back over touch, lightly touch the home homeroom. And I would just get like five js, even like press a button, just like, okay, this is untenable. I cannot work like this. And so, you know, I have Apple Care or whatever. So I just made an appointment, went in, the guy like cleaned it out and, and he's like, well, it's a little bit better, but it's still kind of doing it.

[00:04:54] **Adam:** So he replaced the key cap. He's like, I don't see anything wrong with the old key cap, but with the new one, it's fine. So here you go. And, and yeah, I mean, compared to a control key, that's like nothing. Right. And, and that was driving me crazy. So I can't imagine the, the frustration that you're going through.

[00:05:09] **Carol:** Yeah. I live in a shortcut kind of world.

[00:05:12] **Adam:** Mm-hmm. I wonder, like, could you, in the meantime, could you like remap caps lock to control or something so that you can

[00:05:19] **Ben:** Oh, that's a player idea,

[00:05:21] **Carol:** maybe, but I don't know if I'm allowed to do that on this computer. Right. I will tell you, there is technically another control key on my right side by the pinky, but I've never trained my brain to use that one. I only use

[00:05:34] **Tim:** Oh my God. There is,

[00:05:35] **Carol:** I've never used it. Yeah. So everything is control with that.

[00:05:39] **Carol:** Even on my caps, like I shift my A to the other finger to do caps A Right. Should control.

[00:05:45] **Adam:** I don't think I have ever used that control

[00:05:46] **Tim:** yeah, I don't think so either. Is that for like left people? Left hitting what?

[00:05:50] **Carol:** Yeah. It's for both handed people. Yeah. For it's for left-handed people. Yeah.

[00:05:54] **Tim:** Huh?

[00:05:55] **Carol:** So maybe I just try to convince my brain to use the other control key until I get the new keyboard. Wish me luck you guys.

[00:06:03] **Adam:** Good luck.

[00:06:03] **Tim:** Good luck.

[00:06:05] **Carol:** But that's

[00:06:05] **Adam:** honestly, you deserve PTO for not having a control key.

[00:06:10] **Tim:** PTSD.

[00:06:11] **Carol:** I know. I mean, that's as bad as your laptop not working, in my

[00:06:14] **Ben:** I, I literally can't imagine programming missing my, my modifier key,

[00:06:20] **Carol:** Imagine just dropping your head to your desk multiple times through the day. 'cause you're so angry. That's me.

[00:06:27] **Ben:** geez, Louise.

[00:06:28] **Carol:** Yeah. All right. What about you, Tim? What you got?

## [00:06:32] Tim's Triumphs

[00:06:32] **Tim:** Well, I got two triumphs. If I may be so bold.

[00:06:35] **Carol:** Go at it?

[00:06:36] **Tim:** can I, can I take two? So one's

[00:06:38] **Adam:** do you think you are? Me.

[00:06:39] **Tim:** I know, right? I'm not, I mean, no, I'm obviously not as awesome as you, but I, I can strive. So I posted a couple pictures in our, in our secret channel there. So it was our anniversary, well, it's our anniversary next week, but we did an anniversary trip Ed.

[00:06:56] **Tim:** Yeah, so I put pictures up here. So we went to North Georgia. There is, it's place is brand new. it is only been open like seven months and it's a hobbit house up in North Georgia Mountains and I saw it, one of the cosplay that I'm a fan of, she went there, she's from Georgia for her birthday and I saw her pictures and I immediately like, I got a book.

[00:07:15] **Tim:** This Airbnb, it's places is a

[00:07:16] **Adam:** was just, I was just gonna ask, is this like an Airbnb you can

[00:07:19] **Tim:** Yeah. Yeah, it's an Airbnb and, it's, it's, I mean, it's like, like I said, it's seven months old. It's still, everything's still new. It's beautiful. It's got the big blue round doors. It's underground and then it's got just everything in it. It's just, it's tiny. It's got a one bedroom, queen bed queen.

[00:07:36] **Tim:** it doesn't really have like a kitchen, but it has a little kitchenette with a little half fridge and, a composting toilet. And there's also a mic microwave, but it's all hidden, so it looks like you're in a hobbit hole. And it's on a farm, so there's chickens and there's dogs and cats, and there's, there's a bunch of cows.

[00:07:52] **Tim:** And you can walk down to the little river creek and see the cows. And Beautiful place. Absolutely beautiful. Just had a fan. It, it was like a spur of the moment. I'm like. I've been wanting to get away with Michelle 'cause I'm like, the kids are old enough. We, I don't know why we don't go away without the kids.

[00:08:06] **Tim:** Like, they're grown, they don't need us. So it's like, this was really like the first time we've been away without the kids in, I mean, since we made in Japan five years ago. So, yeah,

[00:08:17] **Adam:** that, is that a screen accurate water bottle?

[00:08:19] **Tim:** no, that is my, my wife's mason jar. I don't know, hobbits may have had mason jars. It kinda seems like a thing they would do, but, yeah.

[00:08:27] **Tim:** But yeah, it's, it was really, really cool. So if you wanna

[00:08:29] **Tim:** look,

[00:08:30] **Adam:** in, in cosplay outside of it.

[00:08:31] **Tim:** yeah, she brought some costumes and, and dressed up and I took photos.

[00:08:35] **Carol:** I love it.

[00:08:36] **Tim:** yeah. So if, if you wanna, if you want to, if you, if you're in Georgia or wanna come here and book it, if look up, on Airbnb, Hobbit and Somerville, Georgia. It's near Rome, Georgia, so it was really great.

[00:08:49] **Tim:** So it was a super good time.

[00:08:51] **Carol:** Halfling Hills Farms. I

[00:08:52] **Tim:** Ha. Yep. Already found Halfling Hills Farms. Yep. And the guy there, the, the, the family that owns it, they're super nice. Just, I mean, it was perfect. It was a great like three day weekend and just, we really didn't do much. We chilled. We, they had a bunch of games. We played, doom Lings, which is a really fun, kind of card game.

[00:09:08] **Tim:** And we played games and I don't think, we didn't turn the TV on once, barely looked at our phones, so,

[00:09:13] **Carol:** perfect.

[00:09:15] **Ben:** I cannot tell you how many conversations I have either been directly part of, or I have overheard on a podcast, and I, I sometimes get the sense like, I'm the only one who watches TV anymore.

[00:09:26] **Tim:** no. You know, I watch a lot of tv, but it's like, you know, it's like your anniversary. I'm not gonna, we're just gonna watch TV in the

[00:09:31] **Tim:** Hobbit

[00:09:32] **Ben:** I know, I know, I know. I'm just saying like, it's, it's becoming a thing that I'm hearing very often now that there are people who just don't watch television.

[00:09:40] **Adam:** Well, I think what it has been is we're getting old, right? The younger generations are less interested in tv.

[00:09:46] **Carol:** well, finally I can relate to the younger generation then. 'cause I watch hardly anything.

[00:09:51] **Tim:** Yeah,

[00:09:51] **Adam:** you're Carol. You're a, you're a, a, a we babe, according or compared to the rest of us, I think.

[00:09:57] **Tim:** yeah. So it's all relative. So that's my personal trium, but my, my business, my work related triumph is, I was been really busy and, we'll, I think, we'll there's new endeavors that we're doing and I'll just, I'll just say this, I don't wanna take too much time on this 'cause we'll talk about it in the, the main show, but, been super busy and I haven't actually been very busy the past few years, which is, which is okay.

[00:10:21] **Tim:** I, I'm, I'm very much, if you're in management, you should delegate as much as possible, right? That's how you know you had a good team. If, if you're, I. If you're not necessary, then you're doing your job right. And so I've done my job very, very well the past few years. But it's like, at the same time, it's like I've been looking for stuff to do and so I've taken on new responsibility and I'm like, this is nice.

[00:10:43] **Tim:** It feels my day up. I'm doing more stuff. I, yeah, I was starting to feel a little bit worthless and I, honestly a little depressed, but it, it's been nice to be busy. So I, I'm glad, glad I've taken on more responsibility lately. So that's me. How about you, Adam?

[00:10:57] **Adam:** I

## [00:10:58] Adam's Triumph

[00:10:59] **Adam:** am gonna go with the Triumph. so I wrote some code like a year and a half ago, and it just landed in production last week, which is, so, yeah, I, I mean, I'll get into it a little bit, but, but before I do that, so it just landed in production last week

[00:11:11] **Tim:** Move slow break stuff. Is that what we're doing?

[00:11:14] **Adam:** that's how we, that's how we roll.

[00:11:15] **Adam:** and, and it, had zero issues, like no merge conflicts? No, like no, no bugs or anything. It just like landed and everything went perfect and it was a, a, it's a relatively small change. you know, we're talking about like maybe a hundred, 150 lines of code changed. and this was for our mail pipeline, right?

[00:11:35] **Adam:** So the, the whole, it's, it was a big part of how we send email and we send a lot of email. And so it was kind of like a, when we finally decided, okay, like let's get this thing merged. we're waiting for the right moment, right? You don't want to like in the middle of sending a big email. Update the lambda that's sending it.

[00:11:51] **Adam:** 'cause then like, you know what if it falls over, what if there's something wrong? You don't wanna like risk that. So I would like wait till there's a window with like, no emails going out. Merge it, make sure the merge went okay. Or, or the deploy went. Okay. And then like real quick schedule and send an email to test it with a, with the ability to roll back if it didn't go well.

[00:12:09] **Adam:** Tests went fine, everything's good. So the, the big change was, you know, I, I've talked years ago on this podcast about how we originally built our application as like single tenant and it's just like copy modify all over the place. And we've been slowly kind of methodically working our way back towards a true multi-tenant system.

[00:12:27] **Adam:** And this is one of those things that for a long time has just been a copy modify service all off, off on the edge. so we had these lambda functions that were used to actually take the mail from the database and send it to the users or to the, the service that will send it to the users. The, the, I I say service, I mean third party service, right?

[00:12:43] **Adam:** Like a, a software as a service that we're paying for.and it was kind of a little bit ridiculous the way that it worked. Like we just had a copy of the, it was literally the same code deployed to all these different lambda functions and that each one just basically existed to be a function that would invoke, that had different environment variables.

[00:13:01] **Adam:** It was like a, you are customer, this environment, qa or environment prod, whatever. and, and then it would just be like, okay, cool. So now based on that, I know how to connect to the database and get the thing and where to send it, into the, the cloud. And so the code that I wrote was just basically like, instead of looking for environment variables, look in the invocation.

[00:13:21] **Adam:** Payload, right? When you start a Lambda function, you can send it some data, like pull the customer in environment outta there and then do the thing. and it was kind of, what's a, like, almost like prop drilling in a React app, you kinda gotta pass those things down a

[00:13:34] **Ben:** Well, it's like a pure function. You're passing in what you need and then it's returning something else.

[00:13:39] **Adam:** Right. And yeah.

[00:13:39] **Adam:** And so we had like, when, when you combine production and QA and we've onboarded a bunch of new customers in the last year or two, we probably had like 50 to 60 lambda functions that I have now replaced with a single one. Now, in the interest of, playing a conservative, we actually haven't deleted any of those other functions yet.

[00:13:57] **Adam:** We're gonna like let it ride that out for maybe a month and just be like, okay, cool. We don't have to roll back. Everything's going smooth. So now it's safe to delete them, but in the meantime, I've replaced like 50 or 60 lambda functions that are all now being called in one function, which is so much fun and it just blows my mind.

[00:14:15] **Adam:** Like, I wrote this code like a year and a half ago, and, and it's just been sitting there waiting. It kind of got sidelined at first because it just wasn't a good time in terms of like projects that were going on, right. It was one of those things where it's like, this is really bothering me. I know it won't take me that long to write the code.

[00:14:30] **Adam:** Lemme just do it. And then I'll get to it next week, you know, next week we'll merge it. Next week we'll merge it, and then eventually you forget. Right? And, and then all of a sudden it's a year and a half later and you're like, oh, oh, I did that. Let's see if it still works. And so I like did a, a little branch off of Maine and just merged it to see if there was b if there would be any merge conflicts.

[00:14:52] **Adam:** and there weren't. I was like, that's interesting. Maybe we can give this a go. Yeah, let me, lemme put up on QA and, and test it there. It worked great there. Like, okay, what do you guys think?

[00:15:02] **Carol:** So it wasn't some code that had been merged into lower environments, it just hadn't went anywhere yet.

[00:15:07] **Adam:** Correct. Yeah. I mean, I did test it locally, but you know, it, it hadn't

[00:15:13] **Carol:** We all test locally.

[00:15:15] **Adam:** Yeah.

[00:15:16] **Ben:** I blame SOC compliance

[00:15:18] **Tim:** Yeah.

[00:15:19] **Ben:** your your life.

[00:15:20] **Carol:** Yeah.

[00:15:21] **Adam:** Sock and PCI, man, that's,

[00:15:22] **Carol:** Mm-hmm.

[00:15:23] **Adam:** that's like, it's funny now, you know, we, we have meetings about various things. We've been, I've been in some meetings this week about Salesforce stuff and we're talking about like, oh, we gotta create this account for whatever ss o stuff to work with Salesforce. And everybody just looks at me like, is that okay? Like, well, okay, from a compliance perspective, having a single like, quote unquote root user account that's not supposed to ever be used, but it can be a credentials for it can be shared as long as it's in like a break in case of break glass of in case of emergency type situation, you know, like squirrel it away, tightly guard the, the secrets, yes, it's okay, but you're just, you know, that's kind of like a, a emergency thing.

[00:16:03] **Adam:** Anyway. Yeah. So like that's my life now is just knowing all this crap and dealing with the PCI and talk to. So anyway, that's about enough for me. what do you got going on, Ben?

## [00:16:13] Ben's Failiumph

[00:16:13] **Ben:** I am gonna go with a little bit of a failure, which is that at work. and actually this kind of dovetails with the topic of the show. So I, I have been working somewhere and I haven't really talked about it on this podcast, so

[00:16:24] **Carol:** I was just thinking I

[00:16:26] **Tim:** Yeah. Wait, wait to hijack my topic.

[00:16:28] **Ben:** No, I, no, you know, I'll, I'll just,

[00:16:29] **Tim:** That's fine. That's fine. That's fine. That's fine. Go ahead. No, go ahead. Go ahead.

[00:16:32] **Ben:** but, but, but the, the, the failure is that at work, my, my boss, Peter Amir, has been trying to get us to play around with Claude Code. Claude Code is one of these AI coding assistance. So Claude is from Anthropic, and Claude has a chat GPT like interface.

[00:16:52] **Ben:** But then Claude Code is a command line thing that sits in your terminal and, and does the kind of, I'll go and modify a whole bunch of files on your behalf. so two things. One, just kind of funny, I wanted to set it up in a docker image or a docker container. 'cause you're supposed to just globally install it on your computer.

[00:17:12] **Ben:** And I just feel like once I discover docker containers, I like, I don't wanna install things on my computer anymore. It feels icky, like giving something, especially something that can just run, you know, RM commands willy-nilly in theory, I, I just, I, I need to have it a little bit contained so they don't really have documentation about how to get it running in a Docker container because it feels like it doesn't really wanna be doing it that way.

[00:17:36] **Ben:** But I went to Claude, the online chat, GPT version, and I said, can you help me set up Claude code in a Docker container? It's like, oh yeah, of course. No problem. I can totally help you with that. And, it, it like really, really struggled to just give me straightforward information on how to set it up in a Docker container, which I thought was just kind of funny.

[00:17:53] **Ben:** but, but the, the main failure here, I guess, is that I can already tell. That the biggest hurdle to having any of these AI code assistance is it's just gonna be emotional on my part. Like, you, you just have to let go. And I'm, and I, that's gonna be so freaking hard for me to not wanna have full control over the code that gets written.

[00:18:18] **Ben:** And it's like, it, it feels like when you're on a rollercoaster, and I'm not a big rollercoaster person, but you know, you're on that, that initial incline, it's going like, ching, ching, ching, ching, ching ching. Right? And it's like you're getting to the top and it's like you get like queasy in your stomach.

[00:18:31] **Ben:** 'cause you know you're about to go over the edge and, and like, there's Yeah. Yeah. Like, and you can't go back. And it like, that's the feeling I get. I just, it's, it's terrifying to me the idea that somebody else is gonna write my code. And, I, I don't quite know how to overcome that. I mean, I, I know it's like a,what, what's the, what's the behavioral I.

[00:18:52] **Ben:** Cognitive behavioral therapy where, or like the one where it's like exposure therapy. Like I just gotta try it a bunch of times and let go and be okay throwing code out and embracing the idea that I could anytime get reset dash dash hard and just throw out all the changes. But don't know, man. It's, I, I can already tell it's not gonna line up with the way I like to see the world.

[00:19:12] **Tim:** so what's, what's the thought process that you should use, that,

[00:19:17] **Ben:**

[00:19:17] **Tim:** what's the value benefit here?

[00:19:18] **Ben:** so obvi, obviously there's a tremendous amount of hype around ai. I don't know how

[00:19:23] **Tim:** That's not a benefit, but okay.

[00:19:27] **Ben:** the, I mean, the hope is that we can deliver code faster

[00:19:31] **Carol:** Mm-hmm.

[00:19:32] **Ben:** but it's, it's really, it's really weird. And, I think I had talked on this show a couple of episodes ago about programming as theory building.

[00:19:44] **Ben:** and this was based on a podcast I had heard. this idea that you as a team have this sense of how the application works and how it fits together and what it means to be part of this application and the idioms and the way we like to view, I don't know, like everything, like it's not just the code, it's how everybody thinks about the code.

[00:20:04] **Ben:** And I'm seeing now that I don't think you can maintain that holistic sense of an application the moment you put control into, into an AI to write it. And where that's manifesting for me is I'll look at a line of code that I'm pretty sure someone else wrote with ai and it was a change to a code I had written.

[00:20:30] **Ben:** So now I'm like, did this person change my code because they didn't like it and they thought this approach was better? Or was this just a strange compression artifact of AI having touched this file and it happened to change this line of code? And like it, it's not an implication of how I wrote it, it's just, it's like that's what the numbers came out to be in the statistical models that this line should be changed.

[00:20:53] **Ben:** So I'm feeling now like, am I gonna have to go back and ask every time I see a line of my code having been changed, do I have to have a conversation about that? Or should I assume that the person who'd made the change knew exactly what was happening? I don't know. I'm just, it, it, it's like this is a, it's not just a different way to write code, it's a different way to think about teamwork.

[00:21:15] **Ben:** And, and I, and I have no mental model for it, and it's a little, I get like queasy in my tum,

[00:21:21] **Carol:** So, it's actually funny you said that 'cause we've had this conversation before at work, like I wish sometimes whenever I was looking at someone's code it said like written by developer A and then the other parts would say, generated. It by co-pilot. That way I know you wrote it or it generated it and you just trusted it.

[00:21:40] **Carol:** Right. So I could be like, okay, well it shouldn't have changed. That example yesterday on my pr I was super happy because in the, the like co-pilot review of it, it told me I declared a variable twice. I didn't, I did not declare that variable twice. It was one time in the file. And you wanna know what's even better is when you try downloading it, it doesn't work.

[00:22:02] **Carol:** I can't even tell it. It's wrong. And I

[00:22:05] **Tim:** Ai, AI can count. Everybody knows AI can't count.

[00:22:08] **Carol:** It was like, source URL declare twice this could cause a problem. I was like, no it's not, and I'm gonna down vote you. But I couldn't, it wouldn't accept the down vote. Hmm.

[00:22:18] **Ben:** Yeah, it's, it's, like I, I want to be able to learn and embrace it, and there are people that I know and respect. They get a lot of value out of it, or at least they, they say that they do. I don't know, but I feel like so many of those conversations are tempered by, oh, you know, I had some fun playing around this weekend, and me and my daughter created a game.

[00:22:40] **Ben:** And I'm like, okay, but that's, that's not the same as as like working in a brownfield application that a corporation depends on.

[00:22:48] **Carol:** And that people have to be able to maintain, you know,

[00:22:51] **Ben:** what it is too. It's like I have to be able to come back in six months and know what this code is doing, and.

[00:22:57] **Tim:** I almost feel like when you're working with ai, it's almost like you have a, a junior developer that corporate paid way too much money for. They're like, we spent like a butt ton of money. This person is like really super smart and they're genius, but like they're just, you know, they're just starting out.

[00:23:14] **Tim:** So code with them, but like, kind of like keep 'em under control. Yeah. And that's kinda what I feel like. It's like, well, AI goes, oh, this is, and it's so confident in, is is expression that you're like, well, I, I guess you kind of know what you're doing. And then you're like, wait a minute, I don't really think you've, have you really thought about the whole picture?

[00:23:33] **Tim:** Like, no, this is, this is the way to do it. Right? It's this type. The best description, I forget why I heard this. I guess it is a meme. A meme or something, but, they described AI as mansplaining as a service. Have you heard this?

[00:23:49] **Carol:** No,

[00:23:50] **Adam:** heard that.

[00:23:51] **Tim:** So Mans Landing as a service. So you, you basically, you, you send information to this service and the service tells you with 100% confidence that what it is telling you is the gospel truth of everything, even though it really doesn't have a full, complete understanding of what you're asking or the topic at hand, but it's so confident and it sounds really, really, really good.

[00:24:13] **Tim:** And you then you actually try it and you're like, this doesn't work at all. That's mansplaining as a.

[00:24:20] **Adam:** I mean.

[00:24:21] **Ben:** I totally had this moment the other day. So I think I was, I had mentioned this in the, in the, discord. I was trying to get chat GPT to help me with some, inter like I, I said, okay, I, I'm trying to learn HTMX and I've learned alpine js. Both of these JavaScript libraries wanna have some control over the dom.

[00:24:40] **Ben:** So I think when you combine these into a single application, there can be issues. Can you please outline common problems that will happen when these two frameworks are brought together? And you know, exactly, to your point, very confidently it gave me, oh, these are like the top six things you're gonna wanna watch out for.

[00:24:57] **Ben:** And one of them, I was like, that doesn't. That sounds really wrong based on what I know about Alpine js. So I said, okay, this is how I think Alpine works. And you're saying it doesn't, where is my assumption wrong? And it said something to the effect of like, don't worry, you're not that wrong.

[00:25:17] **Tim:** Oh wow.

[00:25:19] **Ben:** then it, and then like, yo, and then it gave me like a whole bunch of explanation.

[00:25:23] **Ben:** And then I came back and I said, okay, I actually just tried this in the browser and I'm not seeing the behavior that you're talking about. And it's like, oh yeah, of course, because I'm telling you about version two and you're probably on the latest version three. I was like, oh, come on, bro. Like, how can I trust anything? And like, and like this is where, okay, so, someone was saying this on a podcast the other day. They're like, when, when Cha bt. It tells you about something you know very well. It's wrong 60% of the time, but when they're telling you about a topic you don't understand at all, it's right a hundred percent of the time. And, and I feel like that's, that makes me so nervous because I catch these things because I happen to be talking to it about something that I wanna just learn better, but it's something that I already know. But how easy would it have been if I didn't understand the subtle difference in what they were saying and actually took the time to go and say, Hey, I actually just checked this in the browser and it doesn't work this way.

[00:26:21] **Ben:** Like it was giving me all these workarounds. I'm like, oh, well if you're gonna bring these two libraries together, you have to set up these special event bindings. And like, you don't have to do any of that stuff. But like someone who doesn't know that would just follow those things and it would work.

[00:26:36] **Ben:** It's just you are doing so much more work than you have to. Okay. Sorry. there's no point to my rant here other than to say it's very tricky.

[00:26:45] **Tim:** Yeah.

[00:26:46] **Adam:** So would you say you're bullish on ai, Ben?

[00:26:50] **Ben:** I, I mean, like, okay. So I, again, like so much of it I think comes down to me. it's just gonna be a huge emotional hurdle. I have a way that I like to think about coding. I have a way that I like to think about software design. I, I hold the notion of thinking, like deep thinking about something as like, having almost, inherent value, like the act of having to sit down and think through a problem. It creates more value than the actual solution because like it trains you how to think. It helps you, I think, coalesce different ideas and bring them together and, and it sets up, you know, like, like then stuff is marinating in the back of your brain. You get those shower insights, you know, you're laying in bed.

[00:27:37] **Ben:** You get your little eureka moments and. I'm, I'm worried that if I try, like I don't want, I don't want to get rid of that, but I also don't necessarily know how to dovetail all these things. Well

[00:27:50] **Adam:** Yeah.

[00:27:51] **Ben:** a work in progress, so I'm, I'm excited at least to, to be somewhere where this is like becoming part of the culture, but in, in a, in a tempered way. It's not like, it's not, I dunno if you guys heard about Shopify where they're like, your performance reviews will actually be based on whether or not you're using ai and if you're not using ai, it's not gonna be good for you.

[00:28:13] **Ben:** Kind of. They send out

[00:28:14] **Adam:** Oh,

[00:28:14] **Carol:** my goodness.

[00:28:15] **Ben:** Like the president of the company sent around

[00:28:17] **Tim:** Then the next performance review is AI is doing so good. We're doing a reduction in force of 20%.

[00:28:25] **Ben:** so at least it's, it's, it's much chiller than that, but I'm, I'm hopefully,

[00:28:29] **Adam:** When, yeah, when you, when you first brought this up, I was like, yeah, this is definitely a you problem, Ben. you're, you need to get over your emotions. 'cause I, I was thinking the way you initially phrased it was like, you know, I just, when AI overrides some of my code, or, or when, when AI writes code, I don't know how to feel about it.

[00:28:47] **Adam:** And, and like I, I was kind of thinking along the same lines of what Tim had said about, you know, okay, so it's just this, it's like, it's got, you've got your own little secretary or intern or something writing code for you because it can do it faster than you can, and then you just sort, sort of supervise and say like, okay, yeah, yeah, that looks good.

[00:29:02] **Adam:** That looks good. And then you write tests to verify that it actually does what it says. And, and then, yeah, you know, but, but I, I do think that you've, you're onto something interesting there about code that was written by a person that later being overwritten by ai. That doesn't necessarily mean it's wrong, but it does invite, I think, extra scrutiny.

[00:29:24] **Ben:** Yeah. And then also, maybe it's just a. Maybe it's so radically different that, that the old mental model doesn't make sense anymore. So one of the things that I've noticed in some of the code that's been generated by AI is it, it doesn't deal with abstractions at all. If it needs to do something in 17 different places, it will just do it in 17 different places.

[00:29:45] **Ben:** It doesn't think, how can I make this reusable or can I create a function or a component that I then call in these 17 places? Like it'll literally just duplicate the code in 17 different places. And

[00:29:57] **Tim:** The good old

[00:29:58] **Ben:** yeah, and I'm like, you know, that it strikes me as wrong because if I have to go in and maintain it, now I have to make those changes in 17 different places.

[00:30:09] **Ben:** But if you're living in a world where you're just prompting the AI to make changes for you, maybe the idea that it has to go and and edit 17 places, like maybe that's, is that just, okay now, like maybe abstractions aren't. They're no longer a value add because the thing, doing the maintenance doesn't care that it has to be done in 17 places.

[00:30:30] **Ben:** It's like, oh, just doing 17 places and, you know, in 300 milliseconds. But, but then the question,so then it's like, can I be confident that it actually made the right change in 17 places?

[00:30:41] **Adam:** Don't just run your test suite.

[00:30:43] **Ben:** So here's the thing too, right? They talk about, um, like terrorists not to equate AI

[00:30:48] **Tim:** Quit trolling him.

[00:30:51] **Ben:** like terrorists.

[00:30:52] **Ben:** They say, you know, it's like the good guys have to be right every time, and the bad guys only have to be right once. And I think about that with some of the code that gets written, that if there's, if there's, if there's just one place where a SQL injection attack or a cross-site script attack was opened up, I'm not to say that humans don't make mistakes, obviously all of these things can be done by humans as well.

[00:31:15] **Ben:** But if, if an AI makes changes to 30 different files. And that's a massive PR and it looks really, really good. Except for one place where they didn't escape. User provided content. Like that's all that had to go wrong. And someone just has to find that. And then I'm hosed.

[00:31:34] **Adam:** Well, but then, you know, your PCI compliance and your SOC two audit, you know, penetration test, they'll find that

[00:31:40] **Ben:** But, but, but you know what I mean? It's like, it's not a, it, it's not a,it, it's not like we're with bumper, with lane bumpers on, you know, bowling with lane bumpers. It's, it's like it has to be, right. And again, not to say the humans can't make mistakes, but I think we get, we can very easily be lulled into this sense of it just worked.

[00:31:59] **Ben:** Yeah.

[00:32:00] **Tim:** That's how Skynet gets started.

[00:32:04] **Ben:** Anyway, I've

[00:32:05] **Adam:** Yeah. So make sure you say thank you to your ai.

[00:32:07] **Ben:** yeah.

[00:32:08] **Adam:** Alright, well, shall we move on?

[00:32:10] **Ben:** Do

[00:32:11] **Tim:** it.

[00:32:11] **Adam:** getting nods of approval, so that's a yes.

## [00:32:13] New Patron

[00:32:13] **Adam:** so before we move on to the topic for the day, I just wanna point out, we have a new patron to thank, uh, Tony. Tony Junkies came on. I, I believe that's correct. I, I know I've seen that name many times. over, over the years he's been around.

[00:32:25] **Adam:** I recognize the name. So welcome Tony. Thanks for your support and, uh,

[00:32:30] **Carol:** thanks.

[00:32:31] **Tim:** the party pal.

[00:32:31] **Adam:** welcome to the

[00:32:32] **Ben:** it's worth, I have been saying junks in my head for years.

[00:32:36] **Adam:** For all I know, it's junkies or yos or, you know, like, I, I don't know, man, that's just junkies is just how I, I say it in my head. So feel free to correct us, you know, come join our discordant and, put us in our place. So, I don't know, Tim, do we wanna let, Ben steal the show with his, uh, new endeavors or,

[00:32:56] **Ben:** got this

[00:32:56] **Tim:** I mean, I can talk at first and then he'll just steal it. So

[00:32:59] **Adam:** yeah, there you go.

[00:33:00] **Carol:** Let's do that.

[00:33:01] **Tim:** that's how, that's how that works normally. Yeah.

## [00:33:04] Tim's New Endeavors and Challenges

[00:33:14] **Tim:** So yeah, new endeavors, new challenges. So I, I've been hinting at this for a little while. I haven't really fully spilled the beans, so my, my, I'm still working at Pay Cloud, still director of Pay Cloud, but we're kind of transitioning a little bit to a new stack, which would pretty much on the backend stuff that we're doing will kind of give us a whole lot more features and functionality for our customers, but really won't require a huge amount of, of work.

[00:33:31] **Tim:** I don't wanna go into any more detail than that, but that's kind of why I've been busy the last, last few weeks is like, I've been having conversa calling every single customer in our, and we have lots of customers in our payment space and just explaining, Hey, we're kind of doing this backend change where the payments are coming to these rails, we're gonna switch it over to these rails.

[00:33:51] **Tim:** It's within the same company, so it's not, you know, it's, it's just a little bit of paperwork change and there really won't be a huge effect. But the great thing is it's gonna give you the ability to, you know, take PayPal, Bitcoin, Venmo, cash app, go to Walmart and, you know, make payments and receive payments.

[00:34:08] **Tim:** So it's, yeah. So that's,

[00:34:10] **Tim:** so that's, that's nice. But that's, that's a lot of work explaining that and you have to shepherd that process and everything, but at the same time. So Silver Vine, where Carol, I used to work and Carol used to work.

[00:34:21] **Tim:** I, I've taken over the role of director of development. So basically I'm in charge of all development for the entire company.and, yeah, it's, it's kind of a new challenge and 'cause I've been, you know,

[00:34:32] **Adam:** When you say development, do, do you mean like technology development? Like development, writing code or development? Because like in my world, development is a different thing. There's like a development office and they're in charge of like bringing in new donors.

[00:34:44] **Tim:** yeah, no, so it's not that kind of development. So it is basically in charge of the dev, all the dev team. So anyone who's touching code, I'm in charge of them, right? So they're under my umbrella, not directly. there's a couple layers, but it mainly, it's sort of a more of a strategic role where you say, all right, all right, what does our tech stack, what does our roadmap look like?

[00:35:02] **Tim:** What does our product roadmap look like? What should our coding standards be? Do we use AI or do we not use ai? Do, do we acquire that? You know, how, how should your code be formatted?and, and sort of what is our technology stack that we're working on? And, and then just, kind of working with the really that, that's kind of why I talked a bit a few weeks ago about developer experience, because I really want, I, I think a lot about, although Steve Jobs, you know, had his pros and cons, he did that, did that talk.

[00:35:33] **Tim:** And I really believe what he said where he talked about companies that are successful, they're successful for the content they produce. So whatever it is you do, if you're a car company, your content is a quality car. If you're a software company, your, your content is quality software, right?it's not the process that creates it, but people, when they get successful, they think, well, why are we successful? think, well, it's because our process is so good. And that's what happened to I-B-M-I-B-M became the process company. They had that process for everything, and they, they. When's the last time you bought anything from IBM? There's their, their content isn't of value to anyone anymore. And so Steve's jobs point was, your content is king.

[00:36:16] **Tim:** And rather that's your writing. Rather it's your creating movies, your software company software that you create is your content. And if you don't do good content, you're not gonna be a good software company. Doesn't the processes all behind the scenes, that's how the sausage is made. That does not matter at all.

[00:36:34] **Adam:** Yeah. And you don't use Gmail. You don't use Gmail because they let their developers have 20% time and they have slides and, and open buffet. Yeah.

[00:36:42] **Tim:** So, and that's, that's sort of the thing I I, I've been trying to, to, to wrap my head around on how do I get that, to get to that point where we're creating good content? Because there's, there's been a lot of bad habits that have developed over the years and you, you know, you can't just wash the board clean and start from scratch.

[00:37:03] **Tim:** You gotta. Pick and choose your battles. There's, there's things that you wanna attack and things. There's body, I know all the bodies in the software I was working today in so in, in, in some of it today. And I'm like, I, I, I came up with a solution to a problem. Like I'm pretty sure no one else in the company would've figured out how to fix this issue, but I knew where the bodies were and so I was able, I was, I was able to fix something.

[00:37:27] **Tim:** It probably would've taken someone else probably weeks. And I did it in a few hours, on code that I haven't worked on for years.but that's not really my role to work on code. My, my code has really kind of set the environment, that sets other people up for success. So that's my new challenge I'm looking for.

[00:37:45] **Tim:** And I really, I mean, I don't have a whole lot to say on the topic other than that. I'm just looking for, looking for feedback from our, from you guys, from our listeners about, I mean, how, how do you set developers up for success? Without stifling their creativity. It's the same challenge I've, I've felt raising children.

[00:38:04] **Tim:** I want to focus them. I want them to, you know, I want them to have a, a, a purpose and a desire. At the same time, I don't wanna control them.

[00:38:12] **Adam:** Yep.

[00:38:12] **Tim:** It's the same thing with developers. I want to give them the opportunities, but at the same time, I don't want them to just be wandering into the wilderness. So that balance of control versus freedom and, and, and I, I, I really just, yeah, I, I'm excited to, to do this.

[00:38:27] **Adam:** I, I've been wanting to do this for a long time, and finally they've given me the opportunity and hopefully I won't screw it up. it's a good thing that the three of us are actually collectively Seth Godin, because now we can answer your questions.

[00:38:39] **Tim:** SI don't know who, Seth Godin,

[00:38:41] **Ben:** What? Oh, Seth, going so good.

[00:38:44] **Adam:** You okay? Well, now you have some, some reading to do.

[00:38:46] **Tim:** homework. Okay.

[00:38:47] **Adam:** yeah, just, just Google it. Seth Godin, G-O-D-I-N. he is a pretty prolific, huh?

[00:38:53] **Ben:** I said friend of the podcast,

[00:38:56] **Adam:** not sponsored. Do I need to say that? Um,prolific well-known, like engineering manager, philosophical type

[00:39:04] **Ben:** he wrote Linchpin and Purple Cow and, practice. He has a podcast called Akimbo, which is, is pretty good.

[00:39:13] **Tim:** Yeah, I, I do like philosophy, so yeah. Seth Godin, I'll check him out.

[00:39:17] **Ben:** He's very philosophical. Absolutely.

[00:39:20] **Adam:** Yeah,

[00:39:20] **Ben:** He's, he's one of these people who I, I feel like has an uncanny ability to make connections across time, and he'll relate the way the business works today to the way that Coca-Cola and Pepsi competed 70 years ago. I mean, like, it's, it's just very interesting insights.

## [00:39:38] Set a North Star

[00:39:38] **Adam:** yeah. I mean, to your point though, Tim, I, I don't necessarily feel like I have a whole lot of stuff to offer as advice. I mean, you know, I'm. I don't really have any direct reports, I don't have anybody working for me that I have this, this responsibility that you're talking about to sort of lead the team in that particular way.

[00:39:57] **Adam:** But I can tell you what works on me as a senior engineer, and I think that, yeah. So what works for me is one, gimme a North star. Like if you're not around, there should be a single simple question that I need to ask myself that will help me figure out the answer to the question that I was gonna ask you.

[00:40:14] **Adam:** Right. so like, for example, the one that always sticks in my mind is, Southwest Airlines, they're like, north Star is, we are the low cost airline, right? So if you can't find your manager to decide which salad to offer on the plane, you go with the lower cost one because we are the low cost airline.

[00:40:28] **Adam:** Like, pass the savings onto you sort, right? That's the, that that concept. And then the, the other side of that coin, is. Motivation, you gotta figure out the right way to just sort of make your, your developers excited to move in the direction of that North Star I, and I think it is probably very dependent on your business and all that.

[00:40:51] **Adam:** I can't necessarily tell you how to do that, but mm-hmm.

[00:40:53] **Tim:** what I've been flirting with is, is just really the idea of software craftsmanship. think. because of the, the quarterly drivers of continuing to hit your EBITDA and your net revenue targets, it's all about just get it done. Just get it done fast so we can deliver fast and typically deliver stuff that's broken or low quality.

[00:41:18] **Tim:** Or the biggest one is do doesn't scale. So we've had, we've had issues in, in our corporate history where we got a big, big, big customer. Right? Or, or, or they started, they were a small customer and they grew big, and then they outgrew us because our, our software just didn't really scale.

[00:41:36] **Adam:** Yeah.

[00:41:37] **Tim:** and so, and I've talked to other companies within our, our, you know, family of, of companies and, and some of them have run into that and they, they, you know, they face a challenge by having outside resources that come in and do like, scale testing and, you know, what do you call it when you like.

[00:41:55] **Ben:** Vote testing.

[00:41:56] **Tim:** Load testing. Yeah, thank you. Do load testing and things like that. So because it's like by time, by time you get to that point where they have reached that tipping point and now they are basically killing the server on a daily basis. You know, it's like now you just, you're in fireman mode constantly and there's not really the time to re-architect that is before it happens because you know what's gonna happen. do have

[00:42:21] **Adam:** gotta be able to see it coming.

[00:42:22] **Tim:** yeah, you gotta be able to see, and I, and I mean, I think I, I do have a good feel for having worked on it for many decades, is it is, you know, we have a lot of stuff within the database, a lot of business logic in the database, which was a really bad decision many, many years ago.

[00:42:37] **Tim:** It continues to, we, no one's taken it on to bite that bullet and say, all right, how do we get it out of the da? This really isn't the place for the database to do this. We, this needs to be in, in, in code. It's compiled and, and that runs fast and it's easily testable. And, easily repeatable and easily scalable.

[00:42:57] **Tim:** can't

[00:42:57] **Carol:** Behind source control and behind. Yeah.

[00:43:01] **Tim:** I mean, even if you have, even if your database within source control, it's still, it's separate from the source control. it, yeah. So it's just putting business logic and triggers is a bad, bad thing. Just don't do it guys. Your, your data source should just be really a dumb data holder.

[00:43:16] **Tim:** That's really all it needs to be. And, and we made, that was early decisions early, early on that, that led to that. But so, but that's, that's a tough thing to tackle. And it's like, if I do it wrong, I'm probably out of a job, so, so it's scary. It's really scary.

[00:43:34] **Ben:** can I give you two? Is that okay?

[00:43:36] **Tim:** Yeah. You, I mean, you used to work there so.

## [00:43:38] Giving People Buy-in

[00:43:38] **Carol:** Yeah, well, it's not even like from working there. This is just what I've learned along the way. So like my job as a solutions level architect is to make sure that the system's functioning and secure and that the team is able to do what they need to do, basically.

[00:43:53] **Carol:** Like can the people keep moving and do we have a solution that's gonna keep working? So for me, I felt like one big thing was just pulling people to the side and saying, if I pulled you off work for a month, what would you wanna focus on? Like what is the problem here? What have you seen? What have you not been able to, to dive into because you've been fighting fires or because it wasn't a customer, my customer priority.

[00:44:19] **Carol:** And from there you can kind of build a list and maybe tackle a few of those things. Like show them that you are giving buy-in to their, to their feedback and to their opinion on the system. So they know that A, they can come to you and express things aren't right. And we have technical debt that we need to clean up, right?

[00:44:37] **Carol:** And then you can get the buy-in to go. We need to off shift some resources from making money to making the system to like more maintainable for the long run. So it makes this money longer instead of in the moment.

[00:44:50] **Tim:** That's

[00:44:51] **Carol:** then, the other thing I would say is always come to your people with problems and not solutions.

[00:44:57] **Carol:** So come to them with what's going on, even if you already know how to solve it. Like even if your big brain has put this idea in and you know exactly what to do, give them the opportunity to get there with you so they learn with you and you build that relationship.

[00:45:11] **Tim:** Yeah, those are good. Those are excellent because. One thing I've, I've felt is that if I were given this opportunity maybe 10 years ago, I would've came at it from a point of I know what I'm doing.

[00:45:24] **Carol:** Yep. Same.

[00:45:26] **Tim:** here, you know, you guys listen to me. Shut up. You know, just, just take it. Here's, here's what, here's what's happening.

[00:45:32] **Tim:** And that's not how I'm approaching it this time. So I'm, I I, I've learned through great pain and personal suffering that you have to build consensus first,

[00:45:45] **Ben:** If.

[00:45:46] **Adam:** dictator for life.

[00:45:47] **Tim:** yeah, you gotta build consensus first. So I, I've been going to every, so I started with the, the, I, I asked hr, I said, gimme a list of everyone who's worked at the company gimme their start date.

[00:45:58] **Tim:** And so I went, I go, I'm going to the newest people, to the people who've been there the longest, and me and one other person who had been there the longest. So I'm like, I'm the gray hair here. But I'm going through and I'm just asking questions and one of the questions is kind of similar to what you said.

[00:46:13] **Tim:** I'm like, if, if, if you had a magic wand right now and could change one thing in the system, knowing what you know about the architecture, what would it be?

[00:46:21] **Carol:** That change trigger, that damn change lock trigger.

[00:46:25] **Tim:** Exactly. Right. And, and like I said, I'm not coming to them with I'm, because I've been away for long. So if I think, well, maybe things have changed and so I can't come in and say, oh, I know the problem. 'cause the problem may have changed or may have shifted. But, you know, so I'm coming to each person and, and just saying, Hey, I, I want, explain to me what, number one, what can make your job better?

[00:46:46] **Tim:** What do you like about your job? What do you dislike about your job? You know, what would you change about your job? And, and if you could change one thing in the system to make it better, what would it be? And so I'm getting good feedback from that. And a lot of it's starting to, you're starting to see the layers

[00:47:00] **Carol:** Mesh, huh? Yeah.

[00:47:02] **Tim:** to right. And, and yeah. And I appreciate that. What, what you said about not coming with solutions. 'cause if I come in and people feel like, well, he is not listening to me, he's just trying to jam his agenda down my throat. Right?

[00:47:14] **Carol:** Yep.

## [00:47:14] Building a Structure for Feedback

[00:47:14] **Ben:** Can I, can I say something that I think underscores what both of you are saying, but in a slightly different way? And this is something that I've heard other people talk about because I've never actually really managed people. So this is something I've learned by proxy that you should never assume that people will ever come to you with problems, that you have to build a structure in which you are pulling that information out of them and hopefully doing that, or I should say preferably doing that on some sort of a regular basis.

[00:47:44] **Ben:** One of the examples that I heard one time, I think I'm probably messing this up in my head, was, we're all familiar with the concept of a one-on-one where you meet with your manager, you know, every couple of weeks or however long, and you have, you know, half an hour, an hour, and you talk about the state of the world.

[00:47:59] **Ben:** And I was listening to an interview with a guy who said that when he does that, every time he has that meeting, the person that's reporting to him has to show up with like one thing that they feel like they did well, one thing that they feel like they didn't do well. And one thing like that they would change about the company.

[00:48:16] **Ben:** Kind of like what Carol was saying, you know, if you, if you could snap your finger and had a magic wand, you know, what would you be working on? But not just like casually like they had to show up at the meeting with that ready to be discussed and having that framework in place was a way for him to drive the conversation forward always and not like never allowing people to just be like, yeah, everything's fine.

[00:48:38] **Carol:** Yeah.

[00:48:39] **Tim:** Yeah, that that's the easy out a lot of PE people. Tend to avoid conflict and those who like conflict tend to conflict on things that don't matter.

[00:48:50] **Ben:** So it's um,Feeling attacked. No.

[00:48:53] **Carol:** one thing that happened when I was there before, before I left Silver Vine was I had the conversations of what would you change? Like, what would you do different? And many of them started with get rid of ColdFusion. I hate riding cold fusion. Then it would turn into, okay, so we replace it with another language.

[00:49:10] **Carol:** Like what is the problem that you're facing? And it almost always went into, it wasn't a problem with the language, it was a problem with poorly written code that you just have to maintain in this language. So if you don't fix the problem of the application, you just have to support poorly designed code in another language.

[00:49:29] **Carol:** So it's kind of having to balance the, what is the big picture? You're just blaming it on that thing versus what is the piece of it that you really hate? Like if you told me, oh, I can't get any logs out of ColdFusion, or I hate the local stack on it. Okay, well that's something we can work with. But if it's just you don't like how this piece of the application runs on Gulf Fusion, then that's different.

[00:49:52] **Tim:** Yeah. When people say that, what they're basically saying is, let's just rewrite the thing from scratch. 'cause they don't have any real good answer.

[00:50:00] **Carol:** Yeah.

[00:50:01] **Ben:** Did anyone ever see the movie? It's a Harrison Ford and, Ann Ha, I think it's called Six Days, seven Nights. It's probably from like 20 years ago. So. Harrison Ford. The, the, the quick premise of the movie is Harrison Ford is a pilot, but he is like a, in one of these like four seater planes kind of a thing.

[00:50:18] **Ben:** And he'll bring people to this private island and it's, it's a resort island. And he's, he's flying this one woman over Ann Haes and she's talking about be kindling the romance with her husband. And he says something like, it's an island babe, if you don't bring it, you ain't gonna find it here. And I,

[00:50:36] **Carol:** I do like that.

[00:50:38] **Ben:** and, I dunno, that's how I always think about the software stuff.

[00:50:41] **Ben:** I'm like, if, if you're not bringing it, it doesn't matter what language you're gonna be writing it, it's gonna be garbage. You can write garbage anywhere. Hashtag pop culture references.

[00:50:51] **Tim:** There you go.

[00:50:52] **Adam:** I don't wanna get into it. I think that there are legitimate reasons to want to change your stack, but that's not what we're talking about today, so,

[00:50:58] **Carol:** Yeah. No, no, no. I'm, I'm not saying there aren't reasons. I'm just, I'm just saying that shouldn't be the only allowed reason. Like tell me what part doesn't run well on,

[00:51:07] **Adam:** Oh, for sure.

[00:51:08] **Carol:** Like, let's talk about that and if Cold fusion can't handle it, then let's talk about creating a service that can in another language, but make sure you understand the ins and outs before you say the language is the problem,

[00:51:20] **Tim:** And because in practice what's happened is that there was like, oh, let's move things to do net. Okay, great. Let's move things to, but none of the actual problems got moved to.net. It was all the ancillary stuff that really weren't issues.

[00:51:33] **Carol:** the extra things. So.

[00:51:35] **Adam:** To

[00:51:35] **Carol:** Yeah,

[00:51:36] **Tim:** The stuff that's easier to

[00:51:37] **Carol:** I mean, that's what I would've picked.

[00:51:39] **Tim:** Yeah. Yeah. Because like, you don't wanna say, well, let's do it in T net and then it'll run better. And then like, okay, well we, we, we, you're doing well. Well, we still have an issue with this over here. Well, why didn't you move that? Like, well, that was too hard. So that, that's not a good, that's not a good answer.

[00:51:54] **Tim:** I. I mean, so that's the challenges I'm facing. That's what I'm looking forward to. And, and I'm, like I said, I'm enjoying it because it's, yeah, hopefully I'll, next 10 years I'll delegate myself outta this and I'll retire. So,

[00:52:08] **Carol:** So are you actually supervising people? Like do you have that, that role Because right now I get the joy of doing the tech side and supervising not a single human

[00:52:17] **Tim:** Yeah. Mostly, mostly managing people who are managing people. So, but Yeah. But I wanna hear about Ben, what you're doing. What are your new

[00:52:28] **Ben:** Well, we're,

[00:52:29] **Adam:** Yeah. You know, it's, it's been quite a long time since, January 1st when you became unemployed, sir.

[00:52:34] **Ben:** I say, can we tease it? Can we just tease it and say, because we're, we're almost at the top of the hour. Why don't, why don't we, I'll talk about my thing next time, but I'll say that.

[00:52:42] **Tim:** you promise?

[00:52:43] **Ben:** it? Yeah. Yeah.

[00:52:44] **Adam:** Okay,

[00:52:46] **Ben:** Tune in. Tune in next time.

[00:52:48] **Carol:** to hear, to hear about Ben's thing.

[00:52:51] **Adam:** Same bat time, same bat channel.

[00:52:53] **Tim:** Yep. New endeavors, new challenges, part two.

## [00:52:55] Survivorship Bias

[00:52:55] **Ben:** I, I do want to touch on one more thing though, which is that, so I, I've mentioned one podcast that I rather enjoy. It's called Lenny's Podcast. And, it's, it's basically just interviews with heads of product and heads of companies and heads of technology. It's, it's, it's fascinating to hear these people talk about how they build companies, but one of the things that I find very frustrating about, and this is the thing that I think touches on, on, on Tim's perspective, is that people will talk about what made their company successful and he'll have people on one episode say one thing, and then people on the next episode say the exact opposite thing, and they're both attributing it to the success of their company.

[00:53:37] **Ben:** Like one person will say, you know, so much of what. Made us successful was that we were maniacal about listening to our customers. We're constantly asking our customers, how could we improve the product? You know, where are the points of friction? And we're just every day asking like, what can we do better for the customers?

[00:53:52] **Ben:** And then like literally the next episode, they'll have some guy saying, the thing that really set us apart was we basically never listened to the customers because the customers have no idea what they want. And all we have to do is rely on our good taste. Yeah. And like, all we have to do is rely on the fact that we know how to build good software and we're gonna build the right thing for them by understanding their problems.

[00:54:12] **Ben:** And I'm like, like you just, you just start to realize that there's such a, what do they call it? Survivorship bias,

[00:54:19] **Adam:** Yeah.

[00:54:20] **Ben:** where it's like the thing that you did may be coincidentally what made you successful? Or it might be causally what made you successful and you have no idea.

[00:54:29] **Tim:** Or. It may be what Adam said earlier that he wanted as a developer is give me a North star. And that North Star doesn't matter

[00:54:37] **Adam:** then light a fire under me. Yeah.

[00:54:38] **Tim:** Yeah, exactly. It doesn't matter that the North Star in from perspective looks opposite from another company's North star. The fact that both of them had one and everyone bought into it led to success.

[00:54:50] **Ben:** that's a great point.

[00:54:51] **Tim:** That's what I'm getting from that.

[00:54:52] **Ben:** It's all about just everybody being on the same page

[00:54:55] **Tim:** yeah. Yeah. If if, if everyone's not rowing together, then you're just gonna have dysfunction and disaffection and apathy and that's not a recipe for success.

[00:55:07] **Ben:** Yeah, I like that.

[00:55:10] **Tim:** Yeah. End on that. 'cause that was really

[00:55:12] **Ben:** Yeah, that was nailed it.

[00:55:15] **Adam:** Okay.

## [00:55:15] Patreon

[00:55:20] **Adam:** Well then this episode of Working Code is brought to you by losing Control and Control J and listeners like you. If you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording, editing and transcription costs, and we couldn't do this every week without them.

[00:55:32] **Adam:** Special thanks to our top patrons, Monte and Giancarlo. You guys rock.

## [00:55:35] Thanks For Listening!

[00:55:39] **Adam:** We're gonna go record the after show, which I've said a thousand, well, 215 times, 200 I don't, probably 10 times now. that, basically we're just gonna keep the mics rolling after the outro plays, and our patrons will get some extra bonus content sometimes related to the show, sometimes not.

[00:55:50] **Adam:** If that's something that interests you, then you can go to patreon.com/workingcodepod, throw a few dollars our way. We'll throw a few extra minutes of, podcast Your Way every week. today on the after show, I am going to offer up, I don't know if we'll take a, if, we'll dive into it, but I'm gonna offer up a, an update on my skydiving app stuff, what's been going on there.

[00:56:09] **Adam:** and Carol, it looks like you wrote in here. You've got a new toy. I don't even know how to pronounce that word that you wrote after

[00:56:15] **Carol:** Find, find out in the after show.

[00:56:17] **Adam:** Okay. Okay. I, a little, little, little tease. anyway, so like I said, patreon.com/workingcodepod, we'd love to have you, join our supporters. Everybody is welcome to join.

[00:56:26] **Adam:** no Patreon, no cost needed. go to workingcode.dev/discord, join our community, hang out with us. Great place. It's honestly, it's the most fun discord I've ever been a part of. so, I would love to have you join us there.

[00:56:37] **Tim:** than syntax, that's for sure.

[00:56:41] **Adam:** No shade at all.

[00:56:42] **Tim:** shade.

[00:56:44] **Adam:** Alright.

[00:56:45] **Tim:** they wanna start beef with us, I'm, I'm fine with the, that'll

[00:56:47] **Adam:** yeah, let's do it.

[00:56:48] **Tim:** get a beef going.

[00:56:50] **Adam:** Yeah, we,Intercon or inter international beef. Yeah. 'cause West is in, Canada. Anyway, that's it for us this week. We'll catch you next week and until then,

[00:56:57] **Tim:** Hey, it's our North Star of this podcast. Your heart matters.
