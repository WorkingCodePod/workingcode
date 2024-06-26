---
title: "184: Solving World Peace with Code Comments"
description: "In this week's show, Ben and Adam discuss the aesthetics and functionality of code comments."
date: 2024-06-26
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/26d7636b-ef4e-4688-8663-f3f1da7b4edb"></script><div class="redcirclePlayer-26d7636b-ef4e-4688-8663-f3f1da7b4edb"></div>

In this week's show, Ben and Adam discuss the aesthetics and functionality of code comments.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/184-solving-world-peace-with-code-comments.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Ben:** to say that there is a functional nature to comments, but then in my world, there is also an aesthetic nature, and I know that this is going to sound crazy.

[00:00:09] **Ben:** But having a, grayed out, you know, comment that acts as a visual separator between function bodies. Like, I like that.

[00:00:17] **Adam:** This is going to be fun, because I feel

[00:00:19] **Ben:** Cause everything you said is just wrong.

[00:00:26] **Adam:** How do I say this without saying you're wrong?

## [00:00:47] Intro

[00:00:47] **Adam:** Okay, here we go. It is show number 184 and on today's show, I got just Mr. Ben Nadel with me tonight. apparently it's too hot in Texas or something. Carol, Carol's power to, to her, body just turned off. She's not able to make it. Tim is, still on vacation in Ireland. And so it's just Mr. Nadel and myself tonight.

[00:01:08] **Ben:** Yo,

[00:01:09] **Adam:** welcome.

[00:01:10] **Ben:** happy to be here.

[00:01:11] **Adam:** And as always, we'll start with our triumphs and fails. I went first last time. So Ben, why don't you go first this time?

## [00:01:16] Ben's Failiumph

[00:01:16] **Ben:** I'm going to go with a bit of a fail yumph. It's, it is a failure of focus, but I, I'm going to consider it a triumph in terms of just general fun and learning. So I think I had mentioned before that I started to build a, a little companion app for my feature flags book, which would just be a way to play around with feature flags in a very controlled way.

[00:01:38] **Ben:** So you could see how turning on and off targeting and changing rules would actually affect. Who receives what versions of feature flag values. So at some point I'm creating this visual representation. If you can imagine a grid where we have users on the side and you have feature flags along the top and each user gets a certain variant assigned to them.

[00:02:01] **Ben:** And what I wanted to do is create sort of a, I was thinking about the heat map you were talking about a couple of weeks ago with your, I think it was billing related heat map or. Yeah, yeah, cronjobs, and I was like, oh, this is this, this feels very heat map ish. I want my different variants to have different colors so that when you change the variations or when you change the targeting, you can see kind of a fun, multi colored display.

[00:02:26] **Ben:** So that immediately made me have to find some colors to choose. So I started to look at, Maps. so there's maps, if you remember from your geography classes in middle school, you have, you know, here's a, here's a red state next to a yellow state, which is next to a blue state, which is next to a green state.

[00:02:43] **Ben:** And there's, algorithms about how many, what's the minimum number of colors you need to have things next to each other. I, I didn't really care about the minimum number, but I knew that this was an area Had been deeply thought about. So I said, let me look into maps and I'll pick some colors there. and I found some colors and I didn't love them.

[00:03:01] **Ben:** So then I started to look at other palette, color palette generators. And I found this one site called Cooler, which is like C O O L O R or something like that. I don't know off the top of my head. And it was just a fun little utility where you have five columns and you can pick different hex colors for each column and you can cycle them.

[00:03:18] **Ben:** Like it'll pick random colors. and I wanted to add a six color and you can't add a six color unless you upgrade to a paid version. And, and, and I saw this and I'm like, you know what, it's just columns of colors and it's choosing random colors. When I hit the space bar, I'm like, I can build this. I was like, come on, this'll take me like, I don't know, like an hour.

[00:03:39] **Ben:** I figured it'd be fun to play around with AlpineJS, which is a front end, client side JavaScript application framework. And very lightweight. And, so the failure was not just sticking to the Feature Flags app and what I thought, Oh, I can just knock this out in an hour. I ended up working on it for like a solid week of mornings.

[00:04:03] **Ben:** It's like, it's, it's, it's, it's 1400 lines of code.

[00:04:11] **Adam:** For a color picker?

[00:04:13] **Ben:** And it's like, I just got, I went so far down the rabbit hole. I mean, getting, to let me just get some columns on the page and hit the space bar and it generates a random number, a random color that's, I mean, literally that takes like half an hour. It's just math dot random, you know, between hue saturation and lightness.

[00:04:30] **Ben:** I went with eight hue saturation and lightness instead of red, green, blue, because, The numbers just felt easier, like to manipulate with sliders. That was the next thing I was like, I want to have little sliders and I can have a hue, you know, going from zero to 360, saturation going from zero to a hundred, lightness going from zero to a hundred.

[00:04:47] **Ben:** It just felt like a, like an easy way to think about colors as opposed to adjusting red, green, blue. and then I'm like, well, what if I, then I should be able to use keyboard shortcuts to focus the HS and the L. and then I was like, well, if I'm going to do that, then like, I should be able to move the, the, the color swatches over to the left and change focus.

[00:05:06] **Ben:** And so I'm like, I need keyboard shortcuts for that. And I just, like, I just. I kept falling deeper and deeper down this hole. And every time I thought I was about to be done, I was like, Oh wait, there's one more little thing I can add. And, like even just this morning, I'm still, I was still working on it.

[00:05:20] **Ben:** I was like, Hey, wouldn't it be cool if you could just copy a string of hex values and just paste them into the page and then it would render, them as a palette and I'm like, Oh, I can't publish without that. So anyway. I ended up actually having a lot of fun building this and, having to, yeah, I'm going to call it overall a triumph.

[00:05:40] **Ben:** I haven't, I haven't, I pushed it to my GitHub, but I haven't written up or, or, you know, mentioned it to anyone yet, but I'll, I'll, I'll do that in the morning. But, I don't know, you know, I, now I got to get back to the actual thing I was trying to do. In the first place,

[00:05:53] **Adam:** So you actually have the ability to generate colors and play around with that now.

[00:05:58] **Ben:** now I've got to pick colors.

[00:06:02] **Ben:** So, anyway, that was a lot of fun. It reminded me of that, Malcolm in the Middle meme where he has to fix the shelf in order to fix the shelf. He has to, or it was like, he has to fix the light bulb in order to fix the light bulb, the screwdriver and then like, drawer he takes out if it's broken, then he has to fix that and he has to go get in the car and the car's broken, so he has to start fixing the car.

[00:06:20] **Ben:** Anyway. That was my week.but I ended up having a lot of fun. Yeah.

[00:06:25] **Adam:** bad. I had the opposite of fun this week.

[00:06:28] **Ben:** Yeah. Yeah. What do you got going on?

## [00:06:29] Adam's Fail

[00:06:29] **Ben:** Oh,

[00:06:33] **Adam:** IQ bureaucracy retreat is coming up last week. and, you know, the, the subtext of that is that, you know, we're, the, the wheel has come all the way back around and it's time to start this process all over again.

[00:06:45] **Adam:** Which, the reason I'm counting this as a fail is that We're officially getting on this treadmill, right? of doing this for a year long period, every year, just back to back to back forever. And I still haven't finished the quick, easy one that was supposed to be, you know, like, okay, let's get this under our belt and figure it out.

[00:07:06] **Adam:** Look, I, I'm not going to name names. I don't want to, I don't want to like, you know, do that, but. I think that we made some mistakes in, you know, audit partner selection upfront. We just kind of like got a couple of bids and went with the cheapest one to save money. And we ended up getting what we're paid for

[00:07:25] **Ben:** that sucks. I mean, it sucks

[00:07:27] **Adam:** yeah.

[00:07:27] **Adam:** And so, yeah, yeah. Well, it's what really sucks is, you know, I've been having a bunch of sales calls. My next several days is like full of meetings, which is rare for me, right? Like my calendar. on an average week, I have maybe three, four meetings for the entire week. Uh,on a good week, I have one meeting, just like our Monday morning team, all hands sort of situation, and then nothing else for the entire week.

[00:07:53] **Adam:** And then there's this week, just, just like all meetings all the time.anyway, so I've been having all these sales calls with the different vendors of the software and also the. the audit firms themselves and, you know, some of them, they give you good vibes and they're like, we have a 12 week project plan and we'll get it done.

[00:08:11] **Adam:** And I'm like, they have a 12 week project plan to cover an entire year, whereas we did like, well, I mean, our, our review period itself was 12 weeks. We did ready, we did like six months or nine months of readiness prior to that. And here it is, you know, six months after our review period is over and we still haven't finished everything. you can shave off a few weeks here and there. Like I was on vacation one week, the auditor was on vacation one week, you know, little bits here and there, but still it's just a lot of, it's almost, it feels very much like, we're working across time zones, right? Like they've outsourced it to across the world.

[00:08:48] **Adam:** And so like anytime I make, I make a request, I get, you know, within an hour or two, I'll get a like, okay, yeah, sure. We'll get back to you on that. And then I don't actually get a substantive reply for at least a couple of days. So it's just like. Everything is pulling teeth.

[00:09:03] **Ben:** Yeah. So in terms of a variety of vendors to choose from, it seems like compliance work isn't magic, meaning that it's, there's standards that you have to adhere to, and presumably each one of these companies. has a deep understanding of what needs to be done and needs to get you to do whatever it takes to comply with those things.

[00:09:25] **Ben:** What is, how are companies differentiating from one another? Is it, is it, are they just basically competing on, on schedule and price?

[00:09:35] **Adam:** You would think, right? It sounds an awful lot like it would be, everybody offers pretty much the same thing, right? Because, and I mean, I guess the difference is like, you know, their, their team and the way they run their projects and stuff, because every company is different, right? Every company getting, the audit done, right?

[00:09:53] **Adam:** My company and Envision and IBM are all three going to be very different. you know. Organizations,

[00:10:01] **Ben:** Yeah, it's very different surface areas.

[00:10:03] **Adam:** yes. But at the end of the day, it's a list of requirements that have to be satisfied. And the list is, as long as you are, you know, getting the same certifications done, right, same trust service criteria for SOC 2 or whatever, then the requirements are the same.

[00:10:22] **Adam:** And it's only, you know, it's like, are you playing on easy mode or hard mode, depending on how many employees you have and that sort of thing. But,

[00:10:28] **Ben:** Do you think, being a remote only company, do you think that makes compliance easier or harder?

[00:10:36] **Adam:** Hmm. That's an interesting question. Yeah. I'm guessing it probably goes both ways. So it's easier because we don't have to worry about securing a physical premises, right? Like, so if we had, if we had office space, conceivably, depending on what kind of data you have, where you store it, that sort of thing, we might have to have a physical penetration test.

[00:10:58] **Adam:** Like you hear about on podcasts or whatever, where like, you know, this, like somebody tries to break into your building in the middle of the night, or they try to,

[00:11:04] **Ben:** It's the premise of the movie sneakers.

[00:11:06] **Adam:** Yeah, yeah, they social engineer the security guard at the door or whatever, right? Or let's see if they can clone somebody's RFID card or whatever.

[00:11:14] **Adam:** and we don't have a physical premises for them to do that. So that, I think, you know, it eliminates a bunch of scope, but at the same time, part of me thinks that like, if we could physically get people in the same room, it would be easier to get certain things done,

[00:11:28] **Ben:** Yeah. Yeah. That, yeah, I can

[00:11:30] **Adam:** Being remote and async makes everything feel less urgent until it's late. So.

[00:11:37] **Ben:** Yeah. man, I just, I feel like, I think Carol mentioned this last time. I, it, it is getting harder to remember a time in which you were not working on compliance. It just, it just feels like it, it never ends. So I hope. I hope this next round of vendor selection goes well.

[00:11:58] **Adam:** Yeah, and, and really, kind of what it's boiling down to is I think we're going to end up spending more money this year, but hopefully get a vendor that is more aggressive in, you know, being proactive with us on readiness and, in following up on communications. the, the one vendor, if I had to pick right now, there's one vendor I know that I would pick.

[00:12:19] **Adam:** They're, they're almost twice what we paid last year. But, they've answered all of my emails within, like, an hour. when, you know, I, I, and their attention to detail has been really good, too, right? So, like, our current auditor, The, we corrected them three or four times about the way that our, so like in the United States Company names are very specific, right?

[00:12:41] **Adam:** It's like you have to get the capitalization correct. If there's spaces in the name, you have to get that correct. You know, we, we are not alumni Q comma Space Inc. Period. We are alumni Q with a capital a i inq, everything else is lowercase space, LLC with no comma and no period at the end. And for legal reasons, that's the way it needs to be.

[00:13:03] **Adam:** The current auditor, you know, several times have corrected them on it and they're still getting it wrong all the time. The new auditor, or the one that I would pick right now, if I, if you were holding the gun to my side and say, hold, you know what I mean, made me pick right now, the ones that I would pick, when I like reached out to them through their website, so that a contact form and there was like a notes box on that contact form and I.

[00:13:25] **Adam:** In that thing, I said, okay, this is what I want to talk about. Please schedule some time on my calendar using my, my cal. app link, right? Which is just like Calendly or any of these other services where you can sort of, yeah, you can sort of like outsource that, that secretary scheduling bit.they did it and they did it within an hour, like less than an hour later, I had a meeting on my calendar already to talk to these people.

[00:13:49] **Adam:** And, and I was just like, yes, thank you. Thank you for just caring about the little details. And they got our name right in the proposal when they sent it to us. Right? Like, these are the things that you shouldn't have to be like looking forward, caring about, but it's the details that matter.

[00:14:05] **Ben:** it, it, it reminds me of, I was listening to a podcast. I don't know, maybe like a month ago. And this, older, older gentleman, I think was giving advice to younger people about how to be successful at work. And he was like, if I could give anyone solid advice, it would be show up on time and do things before people ask you to.

[00:14:23] **Ben:** Like, if you do that, you'll be better than 99 percent of people who show up to the job. And I'm like, Oh, it's so true. Just doing the work is a, apparently a superpower, especially with vendors. Yeah. Oh, man, though, you mentioned getting names, right? I have so much anxiety. So I go by Ben, legally, I am Benjamin, but I don't know what forms.

[00:14:48] **Adam:** do you think that goes for me, man? My legal first name is not Adam.

[00:14:52] **Ben:** Oh, I didn't know that. You've been lying to us this whole time.

[00:14:58] **Adam:** For 184 episodes. Yeah, I'll leave it as an exercise for the listener to try and figure out what

[00:15:03] **Ben:** Yeah. Yeah. But so the thing is, is I can never remember which forms I've signed with which names. Because a lot of things I do sign is Ben. Most things I do sign is Ben. Even things I think my say, like my debit card, I think says Ben on it. And when I, but my thing, my driver's license says Benjamin and it really boils down, does anyone need to look at my ID and match it to something that I've already signed?

[00:15:27] **Ben:** And I never quite know if that's going to happen. And it leaves me with a lot of anxiety.

[00:15:32] **Adam:** Yeah, I remember. So I've been going by Adam since like the sixth grade. And when we bought our first house, they made me sign my full name. Spell my whole first name out. Because so when I've been signing things, you know, as an adult, I just put my first initial. And then Adam, Adam Tuttle, right? So, and they were like, you're going to have to sign your whole name.

[00:15:55] **Adam:** And I was like, okay, I need a piece of paper. I need to practice 20 times writing on my own name.

[00:15:59] **Ben:** Well, I forget what the exact issue was, but when we were, So we, we moved into this house two years ago and we sold our apartment that we were living in previously. And, I forget what exactly the issue is, but we're sitting there with the banker and the lawyers and we're trying to do all the closing stuff.

[00:16:19] **Ben:** And so they're just passing around packets for everyone to sign and we get through it like halfway. And it turns out that Mary Kate, my wife, I think she was like signing her name with a dash, like Mary dash Kate, or maybe she would do it with a space, but it's like an actual dash in one of the documents that the bank had created.

[00:16:40] **Ben:** And I'm telling you, we got, we, we got through like 45 minutes of document signing and they were like, Nope, got to start over. And I'm like, are you kidding me? Do these signatures even matter?

[00:16:51] **Adam:** The problem was missing a dash.

[00:16:52] **Ben:** It was, I don't, I don't remember exactly what it was, but it was, she had, she had, some name was funky. Ever so slightly and they wouldn't, they wouldn't let it go.

[00:17:01] **Ben:** They said, no, we have to get these reprinted

[00:17:04] **Adam:** and fill it in,

[00:17:05] **Ben:** and maybe it was, yeah, yeah, yeah, it was something,

[00:17:07] **Adam:** other way, but wow. That sucks. Well, I mean, okay. So while we're on the subject of, of names and, and, you know, legal documents being a pain in the butt. my wife, when we got married, took my last name, but she made her maiden name her middle name,

[00:17:24] **Ben:** Okay.

[00:17:25] **Adam:** and no big deal. You know, that's a very normal thing for people to do. we got married in Maryland, where we both lived at the time. She was born and raised in Pennsylvania. We ultimately, a few years later, ended up moving to Pennsylvania. And When we moved to Pennsylvania, we had to come and get our driver's licenses here.

[00:17:42] **Adam:** The state of Pennsylvania would not allow her to use the name on her marriage certificate as her name on her driver's license, because they already had. A driver's license record for her using her birth name, right? Like the, her original middle name and her married name is last name. So they made her, they tried to, or what they ultimately did make her do was my last name is now her last name on her driver's license, but her birth middle name is on her driver's license.

[00:18:14] **Adam:** And on like our marriage certificate and other legal documents, it's her, her maiden name is her middle name.

[00:18:19] **Ben:** It's so, it's so ridiculous. So ridiculous.

[00:18:23] **Adam:** And like at one point when we, I mean we were young and, and whatever, but like I kind of went up there and I was like, is this the moment where I'm supposed to like, stand up for my wife and be like, I need to speak to a manager.

[00:18:34] **Adam:** Right? Like, this is not okay. And, and we tried to kind of like push a little bit gently tried not to be a, a jerk about it. Push. And they were like, this is, this is the way it's gonna be. You know what? Let's just, we've been in the, the de the what? In, in, oh, sorry. In Maryland it was the MBA, the motor vehicle authority.

[00:18:51] **Adam:** And Pennsylvania is the DMV. But anyway, we are way off on a

[00:18:55] **Ben:** Yeah. Good times. All right. Let's circle back. What are we doing

## [00:18:58] Code Comments

[00:18:58] **Adam:** Okay, so the topic for today, code comments. Which is, 184 episodes in, I'm kind of surprised we haven't really dug into the concept of code comments. But, I know, I'm sure it's come up a

[00:19:10] **Ben:** Probably on the clean code episode at the very

[00:19:12] **Adam:** Sure.but, you know, we figured, let's dedicate an episode to it and see what comes out of it. Because there's always plenty to say about comments, otherwise the comments themselves wouldn't exist, right?

[00:19:22] **Ben:** Agreed. I, I, I, okay. So just right off the bat. I enjoy a good comment. I'm, I am, my default nature is to like comments. I don't, I don't hate comments as a default gesture when I'm looking at code. So, my conversation comes from that standpoint, but I have evolved more over time as I'm hoping all programmers are to be more judicial in the types of comments that I put, but I have certain rules.

[00:19:53] **Ben:** Like, for example, every function gets a comment. I don't care how completely obvious the comment or the function is for me. It's just a rules that I never have to think about it. If I have a function that says, you know, get some, it has a comment that says, like, I returned the sum of the values because as a rule, every function has a comment, hopefully.

[00:20:18] **Ben:** Not a terrible comment, but that's, that's just one thing. Like that's just, that's a hill I'll die on because I hate for whatever reason, scrolling down a code file and just not seeing a comment above a function. And, and, and, and sorry, I don't, I don't mean to cut you off here before you even jump in for the first time, but, but there is, so I, to say that there is a functional nature to comments, but then in my world, there is also an aesthetic nature, and I know that this is going to sound crazy.

[00:20:46] **Ben:** But having a, grayed out, you know, somewhat,opaque comment that acts as a visual separator between function bodies. Like, I like that. And I want to keep that, even if the function itself is not always the most helpful.

[00:21:03] **Adam:** This is going to be fun, because I feel

[00:21:05] **Ben:** Cause everything you said is just wrong.

[00:21:12] **Adam:** How do I say this without saying you're wrong? I feel like there is a spectrum of like preference, right? And you are pretty close to one end, and I feel like I'm pretty close to the

[00:21:22] **Ben:** Okay. Okay.

[00:21:23] **Adam:** So just, you know, and I personally, I, one of my core beliefs is nuance is everything, right? So there's, there's a lot of nuance to this or a lot of nuance available, but as a, as a sort of rule of thumb, a baseline, I consider comments to be a code smell.

[00:21:39] **Ben:** Okay. Okay.

[00:21:40] **Adam:** So, basically what that, what I mean by that is like, if you have to put a comment next to something, then you, it's either not named well, right? The function name needs to be better, or the variable name needs to be better or, or something like that. Or it needs to be abstracted, right? Or, you know, if you've got this like gangly 600 line for loop that goes like 12 nesting levels deep, indentation levels, I mean, then, well, A, obviously that needs to be abstracted, but like, you know, that would be probably a prime candidate for, a big comment at the top that says, okay, this is what this loop is doing.

[00:22:14] **Adam:** Right. But. And this is a preference that I've grown into over the last 20 ish, 25 ish years of working in this field. so, you know, I certainly wasn't born this way. This is a preference that has developed over time, and this is where I am now. Yeah, I just, to me, the code should read pretty cleanly, right?

[00:22:40] **Adam:** Like, it should almost be pseudocode, and then anything that's like, you know, clearly not pseudocode, you know what I mean? Like, kind of breaking from that, should be small chunks in functions and should be refactored away.

## [00:22:56] Comments as Spacers

[00:22:56] **Adam:** That said, I 100 percent agree with you on the spacing thing, especially now with things.

[00:23:03] **Adam:** So I spent a lot of my time writing JavaScript and we've got like prettier and prettier enforces, you know, like only one blank line between any two lines, right? And you can't have a blank line between the last line of the function body and the end curly brace, right? It just, I mean, there's, there's settings to change these things, but,

[00:23:22] **Ben:** Right. But there's a, there's a

[00:23:24] **Adam:** way that we've got it

[00:23:24] **Ben:** and, and team standards and whatnot. Yeah.

[00:23:27] **Adam:** Right. And so it's enforcing rules. And sometimes I feel like it is getting a little crowded. And so I agree with you that just from a, a readability and not, you know, preventing feeling overwhelmed when looking at the code, comments can be nice.

[00:23:46] **Ben:** Yeah. It's like a breathing room.

[00:23:49] **Adam:** for sure.but yeah, I think that like, just in, as a starting point, if I get the itch to add a comment, I've trained myself to think.

[00:23:59] **Adam:** Okay. Well, but like, why, what, what do I need to rename? What do I need to refactor?

[00:24:04] **Ben:** So let me, let me dig into that a little bit because. On one level, I agree that if something is getting too complicated, it could very well be an indication that you need to take some of that logic and move it somewhere else behind a named abstraction and then call that thing.but I, I don't know what the feeling is, but there are times when I write a piece of code it's not.

[00:24:33] **Ben:** Academically, I think it would make sense to break it up more than I do, but there is an experience to reading the code where I think breaking it up and having to jump from function to function would ultimately hurt the consumability of the code. Let me give you an example. So I talked about in my triumphs and fails, this little color palette thing I'm creating.

[00:24:57] **Ben:** And one of the things that it can do is it can take your colors and it can generate a palette. PNG and, and download it. And so what it has to do to generate a PNG is it has to loop over the colors. And

[00:25:11] **Adam:** that really necessary when you were just trying to,

[00:25:15] **Ben:** So you could see why it took a week, but okay. So as part of generating this canvas, what I have to do is I have to loop over the colors and for each color, I have to write a rectangle and fill it in with a solid color, you know, representation of the hex color, and then below it, I have to write the little text.

[00:25:34] **Ben:** That says this is FF3366, kind of that kind of thing. and writing things to a canvas, it is not a, it is not a concise syntax. It is like, I have to set a context color and I have to set a context family and I have to set. you know, the X and the Y position and the text and the fill colors. And it's to write a rec

[00:25:55] **Adam:** I forgot it. I might've missed it. If you said this, are you doing this all as like SVG? Oh, this was for the PNG.

[00:26:00] **Ben:** yeah, yeah, yeah. So the P is, so you write the, you, you basically write to a canvas and then you can get a data URI from the canvas that it represents a PNG. So long story short, to, to create this canvas, it, it ends up being like 20 or 30 lines of code, which is in the grand scheme of things, it's not huge.

[00:26:18] **Ben:** But, As I'm in, I don't want to break it up into multiple functions because this one function creates this canvas and to have say a method that writes the rectangle or like a method that writes the text that I can, you know, for color of colors, write rectangle, write text. That would read really nice, but I think it there, you would lose the co location of, of, of logic of behavior, you know, like it's, this is all for this one thing.

[00:26:46] **Ben:** I don't necessarily want to break it up. So in cases like that, I will have this 30 or 40 line function and I'll put a comment that is not a meaningful comment, but it's like a we're on this journey together as the reader and the code and you've gotten to this point and I want you to know, stop for a second, we're about to, we're about to add a colored rectangle.

[00:27:08] **Ben:** Okay, that's 10 lines of code. All right, stop for a second. We're about to add a hex value to the canvas. And so it's like the worst kind of comment because it's literally telling you what the code is doing and not why it's doing it. But I think from an experience standpoint, it's like a mile marker. It's like, it lets you check off what you've done and kind of mentally prepares you for this is what we're about to do. And I think maybe the, as I'm, as I'm saying this and I'm thinking about it, maybe what the differentiating, like the dividing line for me is, The worst kind of comments are one line of comment that describes one line of code. You know, I'm about to get the user from the database, var user equals getUserById. The difference for me is I'm about to tell you what we're going to do, but the what we're going to do takes eight, nine, ten lines of code. So I'm giving you just a little, a little heads up. This is the tunnel we're about to go through and, sit back and enjoy. And, and, and I think maybe that's the, that's where I think I diverge maybe from a lot of quote unquote best practices about code is I like these little, these little check ins, these like mental check ins, say this is what we're about to do. Speechless.

[00:28:26] **Adam:** It definitely wasn't muted and coughing.

[00:28:30] **Ben:** Your silence only incriminates you, sir.

[00:28:34] **Adam:** So, I can't, based on the words that you just said out of your mouth,

[00:28:41] **Ben:** My mouth, my mouth sounds.

[00:28:43] **Adam:** not, not the ones about me being, unable to argue, but the, the ones before that where you were making a point. Those words. I cannot argue that you're wrong. I think that you made some, some good sense there. And I, based on that alone, I would have to see the code to know whether or not it fully jives with my personal philosophy on comments, but, I think maybe one indicator would be cyclomatic complexity, which is, as I said before, just like the number of indentation levels, right?

[00:29:14] **Adam:** And so.

[00:29:15] **Ben:** Well, if I can just touch on that for one second, I, I think part of, part of the reason that, that I've developed this as a, what's called a defense mechanism, in terms of keeping the code clean is because the, the larger structure of the code probably leaves something to be desired. So, I mentioned at the top of the show, I'm working on this thing, it's 1400 lines of code. If I had found a way to cleanly say, let me take this hundred lines of code and break it out into its own module. And let me take this 150 lines of code and break it out into its own module. Then I would, I would have one very cohesive JavaScript module as the JavaScript. And in that case, breaking little pieces of logic out into their own functions, which are like two lines below and six lines below, that would probably be better.

[00:30:09] **Ben:** And I think part of what I'm worried about is, Because I, and this is again, just like a hill I'll die on, because my methods are sorted alphabetically, if I break a method apart and it's got a weird name, like, okay, now it's 600 lines of code away, you know? And, and so there is a, there is a. I'm in a bad space and now I have to co locate more complexity in order to keep what is simple that could have been better done in isolation.

[00:30:42] **Ben:** If that makes

[00:30:43] **Adam:** yeah. Yeah, I get it. And, and I've been there. I think that my first thought as a rebuttal to your, the functions are going to be too far apart from each other, is that if you name the functions in a way that, you know, it's clear that one is a child of the other, right? So like if you're, if it's generatePNG and you're, and you named the one like generatePNG color square, and the other one is generatePNG.

[00:31:10] **Adam:** you know, hex label or whatever, right? Then, then they're going to be next to each other alphabetically, but that I, I will be the first one to admit that that may not always be the best approach, right? Because then, you know, you could easily find yourself in a situation where you've got like a 70 character long function name

[00:31:30] **Ben:** Yeah. Yeah.

[00:31:30] **Adam:** it is garbage to read and write, butthis is also making me think, god, it's been, it's probably been more than 10 years since I've written any C sharp.

## [00:31:38] Function Folding

[00:31:38] **Adam:** So And this may or may not be still a feature, maybe it was just a visual studio thing.and, and yeah. And honestly as I'm saying it, I'm even starting to think that maybe this is a bad idea too, but it's making me think of this thing that I have a memory of. Maybe it's a false memory. It's, it was kind of like comments, but it was like section identifiers, right?

[00:31:59] **Adam:** You could, it was like a special comment or something and you could say like, here's a begin section and end section and the the IDE. would allow you to collapse that chunk of the code. Like, like fold it,

[00:32:10] **Ben:** Yeah, yeah.

[00:32:11] **Adam:** fold a function shut.and this was probably around the time that IDE started getting function folding anyway.

[00:32:19] **Adam:** But,

[00:32:20] **Ben:** Function folding is one of those things that I never think to use it. And then every day, like every, you know, random days I'd be like, Oh, right. Function folding. Let me try that. I try it. I'm like, Oh, that's pretty amazing. Like that just made my file much more readable.

[00:32:35] **Adam:** mean, this is also a symptom of a larger problem, which is that we have, you know, components that have hundreds of functions in them. And so to make them scannable at all, you kind of have to use function folding. But, I have developed this like muscle memory of when I open a component, I hit the keyboard shortcut to like, fold at that first indentation level.

[00:32:55] **Adam:** So like, the component stays unfolded, but all of the top level functions within the component fold themselves shut. Right, so for in me, for VS Code, you know, it's like, Command K, Command 1, I think for, I don't even know, I just do it, right? to fold at the first level.

[00:33:14] **Ben:** Oh, that's pretty good. I'm sure Sublime Text has a keyboard shortcut for it, but I don't,

[00:33:18] **Adam:** Probably.

[00:33:19] **Ben:** I don't do it enough to

[00:33:20] **Adam:** You probably have to bang two rocks

[00:33:21] **Ben:** Yeah.

[00:33:24] **Adam:** yeah, and then, like, Command K, Command J will unfold everything. Like, so if you, if you get, like, you know, to the point where you just want to reset everything, Command K, Command J will unfold everything. But, you know, like I was saying, maybe that's not a good thing, right? Maybe that's a symptom of a, of a bad problem too, right?

[00:33:41] **Adam:** If you, if you need to fold something that doesn't otherwise provide you folding opportunities, please. Maybe that's like, you should make that a function so that the function itself can be folded shut.

## [00:33:51] Peek

[00:33:51] **Adam:** another thing that I really like about VS Code that, that maybe, you know, this is just like the way that I use it kind of influences the way that I write code. It's got this feature called peak, which you can access through the command palette, just type peak. But, for me, I think I have it set to alt command P, if I remember correctly. Again, you know, the memory is in the fingers, it's

[00:34:11] **Ben:** Yeah. What does Peek do there?

[00:34:13] **Adam:** so basically, it, it, how do I want to explain this?

[00:34:18] **Adam:** Like, it, it kind of cuts the, so if you're on like line 24 and it's like in about a third of the way down the window, right? So what it does is it kind of physically cuts the, the editor horizontally between line 24 and 25 because you're on line 24, right? And it pushes line 25 down, I don't know, 10, 15 lines.

[00:34:37] **Adam:** It creates this like window inside there, right? And what you

[00:34:41] **Ben:** ripping his shirt open to reveal his S.

[00:34:43] **Adam:** kind of, yeah, right? And so, what you had your cursor focused on, if it's a function name that was being executed there on line 24, not the function definition, but execution, and you hit the peek command, it would sort of slide in a view of that function implementation.

[00:35:02] **Ben:** Oh, that's pretty cool.

[00:35:03] **Adam:** It's awesome, especially, like, it's not great if you're trying to edit that code, if you're like trying to trace

[00:35:08] **Ben:** No, but just

[00:35:09] **Adam:** okay, yeah, like, oh yeah, what does this function do again? Yeah. Yeah. So that's it. And you can resize it and scroll in the middle of that little pane or whatever,

[00:35:18] **Ben:** that's really cool, I got to

[00:35:19] **Adam:** So I think, you know, yeah, so that sort of functionality I think influences the way that I write code because it is easy to peek in and see what does this small little function do.

[00:35:30] **Ben:** I like it. I got to check that out.

## [00:35:33] Apologetic Comments

[00:35:33] **Ben:** other, other types of comments that I like to do are apologetic comments. Like, like this code, I w I'll leave a comment that says, I wish I could figure out how to make this code cleaner. I could not. and maybe here's why, and this is complicated and it is what it is.

[00:35:51] **Ben:** I'll definitely leave comments like that.

[00:35:55] **Adam:** I actually just had the pleasure of removing one of those comments. So I, I had a comment in our TypeScript. tests that was like, so when you're writing TypeScript, you can leave a comment that's like slash slash at TS expect error to say, like, I know the next line is going to throw a TypeScript error.

[00:36:12] **Adam:** I don't know how to fix it, but I just want you to ignore it. Like TypeScript, I know better. I'm telling you it's okay. You know, go back and play. and, and so, and you can like leave a little comment after that, right? So it was like TS expect error. Adam doesn't know why this doesn't work, but it's fine. And, we hired this junior developer and he's been working for us and he, you know, I just was like, here, you know, go, go figure this problem out. And I saw his code and I was like, wait a minute. I recognize that problem. How did he solve that? Like, oh my goodness. And so I like, I got the opportunity. I showed him, I was like, look, look what you just solved for me.

[00:36:48] **Adam:** you know, I, you know, I had this problem and you just came up with the solution. And now I get to go fix all this stuff. So that was, that was super cool. I was glad to be able to show that to him.

[00:36:58] **Ben:** Love it.

[00:36:59] **Ben:** so I feel like I have, as I mentioned before, skewed away from leaving comments that explain what the code is doing and more toward comments that are explaining why the code is doing it, right? That might be some business decision.

[00:37:12] **Adam:** It might be some technical reason about like, oh, this library works this way versus this library works that way. Or, you know, or I guess sometimes I'll leave comments Are obvious to a very experienced developer, but wouldn't be so obvious for a beginner developer. And I'm like leaving them breadcrumbs to like help them be able to come back and read through it later.

[00:37:35] **Ben:** I'm down with that. Well, let me, let me, okay,

[00:37:38] **Adam:** Can we just solve, you know, world peace with comments?

## [00:37:41] Turn Signal Analogy

[00:37:41] **Ben:** I, I, I think, I think we had mentioned this, in the pre, in the pre show chat. One of the metaphors that I like to think about is a turning lane. And turn signals. So for, people who may not be familiar with, highway driving, road and cars, oftentimes you will have multiple lanes and at an intersection, some of those lanes have to do certain things.

[00:38:05] **Ben:** So maybe the right lane has to turn right at the intersection and the left lane can either turn left or go straight. That kind of a thing. if one were taking a, what is the requirement? you could look at the turning lane and say, well, why should I put my turn signal on if I'm in the turn only lane because I have to turn?

[00:38:26] **Ben:** So the turn signal feels superfluous. It feels unnecessary. it is unnecessary to you. As the person in the turning lane, because you know exactly what this lane is meant for, because you got into it on purpose, at least that's what we hope, but the turn signal is not, is not obvious to everyone else around you.

[00:38:49] **Ben:** Whether it's the person crossing the crosswalk or the oncoming traffic or the person who's not sure if you're, going to go straight or turn behind you. And so the, the turn signal in this metaphor is akin to the comments that as an experienced developer, probably as a person who wrote the code, it's really obvious to you what it's supposed to do, but for everyone else around the code or who comes after you've written it, it may not be obvious to them.

[00:39:17] **Ben:** And. I think the comments can help in those cases.and as a fun follow up, I actually Googled a couple of weeks ago, whether or not you have to use your turn signal in the turn only lanes, and I think it's state by state, but in New York, which is where I am, it is a legal requirement to use the turn signal in a turn only lane.

[00:39:40] **Ben:** So if anything, That underscores my argument.

[00:39:45] **Adam:** Yeah. I mean, okay. I agree with you. And I, and I, I tend to agree with that particular law, just like you're, you're turning signal. Is not for your benefit, right? You're signaling to others, right? So it could be oncoming traffic and they may not know that you're in a turn only lane

[00:40:01] **Ben:** Right. I'm moving a 3000 or, you know, like a three ton vehicle at 30 miles an hour. Let's all be very clear about what's about to happen. You know, let's leave nothing to the imagination.

[00:40:13] **Adam:** I love it. Well, shall we wrap it there? You have anything else you want to get off your chest?

## [00:40:17] Starting With Comments

[00:40:17] **Ben:** I will say that sometimes when I'm approaching a piece of code in my mind to And I'm not a hundred percent sure how I want to write it. I will sometimes start by writing little comments. Like I generally understand what the algorithm is. So I'll just write in comments, the steps to the algorithm, and then I'll start to write the code below each one of those comments.

[00:40:40] **Ben:** So the comment will say what I'm supposed to be doing. And sometimes when I get to the end of writing the code, I'm like, I'm just going to keep those comments in there. Or like, maybe I'll remove some of them, but not all of them. I feel like they served a purpose for me. And to that end, maybe they'll serve a purpose for the next person to help them understand the it's, it's, I don't know.

[00:41:03] **Ben:** You know, it's, it's, I just believe in, yeah, yeah, yeah. A hundred percent.

[00:41:07] **Adam:** I've done the same thing where you're like, okay, I, this is going to be a big task, right? This writing, this one function is probably going to be most or all of my day, or maybe even like all of my week, right? And so I need to like come into this with a plan. And so the first thing I'll do is write this big, long comment that has like 10 steps, numbered steps that say, okay, first I'm going to do this, then I'm going to do this, right.

[00:41:26] **Adam:** And I'll start to fill in the code between them. And I think in those cases, when I have kept the comments around, I like to keep a copy of the entire plan at the top of the function, right? Like this is, these are the steps I'm going to do. And that way you're kind of coming into it knowing, okay, these are, there's 10 pieces to this function.

[00:41:45] **Adam:** And I'm going to be able to identify each piece. Now, again, I'd have to see the code, but I think that me of today would probably view that as a code smell. And I would probably want to refactor that out to, to function calls. Now that said, you know, it can't just be functions all the way down, right? You, you, you have to draw the line somewhere and say, this is getting ridiculous, we don't need to go 700 layers deep on the call stack for hello world, right?

[00:42:11] **Adam:** Like

[00:42:12] **Ben:** Yeah. Yeah. I think, you know, certain algorithms, I don't mean any in particular, but some classification of algorithms, they're just complicated. They're like, you know, Simplification is not necessarily the thing that's going to make it more consumable from a, from a reader standpoint, like it's just going to be complicated.

[00:42:35] **Ben:** And in cases like that, I do find that it's really nice to have comments in there that literally tell you what the code is about to do.I can't tell you how many times I have looked at, say the Angular source code or the React source code. And you look and you're like, what the F is this code doing?

[00:42:55] **Adam:** And I'm sure it's very clear to someone who is very versed in how the underlying framework is written. When you are not versed, that code does not make any sense whatsoever, no matter how well the methods are named and the functions, you know, and the variables are named, like sometimes you got to just put some commas in there.lost me at no matter how well they're named, but okay, again, nuance

## [00:43:19] Ben's Habits

[00:43:19] **Ben:** All right. So, so. One of the things that, one of the algorithms that I had to write one time was I had a, I had a, an arbitrary. structure, a nested, basically like a objects of arrays of objects of arrays kind of a thing, like just arbitrarily deep. And I needed to, write something that traversed over it.

[00:43:39] **Ben:** And so historically, you would say, oh, one might say, oh, that's a perfect, example of where recursion would come into play. Like I'm at one level and then I explore it by exploring all the layers below it, which in turn explore by exploring all the layers below it kind of a thing. but it turns out that recursion is not always the fastest.

[00:43:56] **Ben:** and it, and it can, depending on the size of the object you're exploring, you can run out of heap space or something. I don't know all the right technical terms. So you can replace recursion with an array. And essentially what, like, let's say you have an object and you need to explore all of the, the child nodes of that object.

[00:44:18] **Ben:** You can take all those and just add them to the end of an array. That's kind of your exploration queue. And you can start consuming this array and whether or not you push things onto the end of the array, or whether you push them onto the front of the array, or whether you push them on in reverse or forward, depends on whether you're not, whether you're doing them depth first recursion or breadth first recursion.

[00:44:36] **Ben:** And that's, it's just complicated. You're looking at someone pulling objects out and pushing them onto other things. And like, you just need some comments to say, what the heck is this code doing? Why am I using a. A prepend here instead of a, an append or, you know, like an unshift instead of a, of a push.

[00:44:56] **Ben:** And like, you just need someone to tell you why that's happening because the second

[00:45:01] **Adam:** again. Why not? What? Why?

[00:45:03] **Adam:** well, it is, it is the why of the what. But, but, so I think, you know, to, I have seen code that I feel errors on the side of not writing comments as like a. Moral stance and I, and I do think that the code can suffer from that, but I will also, I will also agree that I probably write more comments than I need to. And I will say that I am getting better as I'm getting older.Time is short. The future is now old man. so while you were talking about that, it, I, in a way you reminded me of it. And in a way my mind was just wandering because that's what my brain does.

[00:45:46] **Ben:** what we do.

[00:45:47] **Adam:** I was thinking about arrow functions in JavaScript and you know, how like If you write an arrow function, you can, like, you can return something without any braces, and without a return statement, right?

[00:46:00] **Adam:** It's just arrow function points at the number one. It's just going to be a function that returns one, right? And you can use that to your advantage. You know, there's some situations where you write functions that return functions that return functions, right? It gets

[00:46:14] **Ben:** Yeah.

[00:46:16] **Adam:** That and even like, if you're trying to write like reusable code for an express route handler or middleware or something, it can get real hairy there.

[00:46:26] **Adam:** and so in that case, but like at the same time, like, okay, so you have a choice to make there. You don't have to use arrow functions. You can just use standard functions, in which case it gets the syntax becomes a little bit clearer. By itself. However, there are some features of arrow functions that potentially could be useful, right?

[00:46:45] **Adam:** They don't have their own this, so if you need to reference this for some reason, or, or something like that, right? It could be very handy to do arrow functions that, like, arrow function returns an arrow function returns an arrow function that does a thing.and in those cases, like, I could see myself having that debate, but possibly landing on the side of leave a comment.

[00:47:04] **Adam:** Mm hmm.

[00:47:05] **Ben:** can I just say that I have this debate in my head for exactly this situation. not all the time, but I'd say like every two weeks I actually have this conversation with myself. the, the typical one is I have an array of objects. And I need to get an array of properties from each one of

[00:47:22] **Adam:** Mm hmm.

[00:47:23] **Ben:** And if I had something like low dash or underscore, they have a method for that called pluck. You say, you know, pluck this property out of all of these things and it returns the array of values. you can do that with one line of code as a map function. And you use your fat arrow and you know, like here's the element and then fat arrow element dot property.

[00:47:43] **Ben:** And it does all the implicit returns and it does the, you know, you don't have to have the braces and everything. And I, and I, and I, and I'll write that line of code and I'll sit there and I'll look at it. And I think to myself, you'd be an you know, like, and I'm like, no. And then I, then I have to go in, I add line returns and I add the return statement and I don't know why it just strikes me as so wrong to write code that

[00:48:10] **Adam:** you're still using an arrow function, but you just feel the need to have the curly braces and the word return?

[00:48:15] **Ben:** do, and I don't know why it's just a, it's, it's, it's, it's. It's just an emotional block, maybe.

[00:48:23] **Adam:** Honestly, to me, that feels like a, like somebody who compulsively puts semicolons at the end of every line of JavaScript, which is me,

[00:48:31] **Ben:** Yeah. Yeah. I do that too.

[00:48:33] **Adam:** Mm hmm. I do not write JavaScript without semicolons. You can have my semicolons when you take them from my cold, dead hands.

[00:48:38] **Ben:** You know,

[00:48:39] **Adam:** But I do like, I think it's called a naked, return or something like that on an arrow function.

[00:48:45] **Adam:** just the, the simplicity, like the, the lack of syntax

[00:48:49] **Ben:** I know I, I like it too. I like it too, but I can't do it. I don't know why. Cause so that I, I have, it's actually two conversations. The first conversation is don't do the single line. Nobody likes that guy. And I'm saying that to myself, right? I'm not saying that about

[00:49:05] **Adam:** Yeah, yeah, yeah.

[00:49:06] **Ben:** So I'm like, okay, all I got to do is add the brace and just return on a new line.

[00:49:11] **Ben:** And then I'm like, Oh, but I have a rule, which is that I have to have a line break at the beginning. I have to have an empty line at the start and the end of every function. And like, it's not even a linting rule. Like that's just how I write functions. And, and yeah, and then, so now the map,element, element dot property is now like six lines of code and you're like, Oh, it's so much worse, but it's better, but it's worse.

[00:49:35] **Adam:** Aren't you also the person that always has a line break after the return keyword before the value that you're returning?

[00:49:44] **Ben:** I, I, I was adding parentheses around all of my return and, and I will say, so Sean Corfield, amongst many other people have given me grief about this. I have stopped doing that as, as an, as a social experiment for myself. And I am mostly enjoying it actually. I, I still wrap complex, operations, compound, I still wrap compound operations in a parentheses.

[00:50:09] **Ben:** So if I have to say like return X plus 10, X plus 10 is in parentheses, having nothing to do with the return statement. It's just because if I had var result equals X plus 10, X plus 10 would be in a parentheses there too. That's, you know, that's another battle to be had, but I will say that if I just return X plus 10, I'll return that baby beast now, without a parentheses.

[00:50:35] **Ben:** And, and I do actually quite like the way the code looks. So,

[00:50:40] **Adam:** can send your hate mail to Benjamin Nadel, O. Box.okay. Let's kill it there before we say things that are going to get us canceled.

## [00:50:48] Patreon

[00:50:48] **Adam:** So this episode of Word Code is brought to you by using your right turn signal in the left turn only lane,

[00:50:56] **Ben:** No, that's the exact opposite. Yeah.

[00:51:04] **Adam:** with them, but anyway, and listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording.

[00:51:15] **Adam:** Editing and transcription costs and we couldn't do this every week without them. I, I am so in a routine. I always like try to push my glasses up during that sentence and I'm not wearing my glasses right now and I still reached up to try to push my glasses up. Special thanks to our top patrons Monte and Giancarlo.

[00:51:31] **Adam:** You guys rock.

## [00:51:32] Thanks For Listening!

[00:51:32] **Adam:** we are going to go record after show. It's probably going to be a short one because I got family coming into town and Ben doesn't people well, even when it's just me and him. so, the thing that I want to talk about a little bit, just Because it's fun and it's on my mind and it's, it's big is, I'm reorganizing my NAS, my network attached storage, from smaller drives to larger drives.

[00:51:50] **Adam:** and the hoops I'm having to jump through on that. So I'm gonna talk through that a little bit. If you'd like to, hear the after show, this one and all other past and future after shows, you can go to patreon.com/workingcodepod for as little as 4 a month, if you pay monthly, and even less than that, if you pay yearly, You too can be a listener of the after show and get your name in gold in our discord server, which if you'd like to join, you can go to workingcode.dev/discord. That's going to do it for us this week. We'll catch you next week. And until then,

[00:52:21] **Ben:** Remember folks, your heart matters, even if you don't put any breathing room in your function bodies.
