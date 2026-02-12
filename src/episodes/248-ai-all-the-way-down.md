---
title: "248: AI All the Way Down"
description: "Ben's been riding high on vibe coding—until he tries it on code he actually cares about and that 10x productivity starts feeling more like 10%."
date: 2026-02-12
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/e8919a64-db4c-493a-99ca-880b3b5ff7fe"></script>
<div class="redcirclePlayer-e8919a64-db4c-493a-99ca-880b3b5ff7fe"></div>

Ben had been riding high on vibe coding—throwaway scripts, zero attachment, pure productivity magic. Then he tried the same approach on a project he actually cares about and watched that 10x feeling crater to something closer to 10%. The bottleneck, it turns out, was never the typing.

The hosts dig into what it feels like to let go of code you used to care about, whether "write-only code" is actually the future, and the growing gap between building software and keeping it alive.

### Links

- [Vibe Coding by Gene Kim & Steve Yegge][vibe-coding] - The audiobook on AI-assisted development
- [1Password: From Magic to Malware][1password-blog] - How OpenClaw's agent skills became a supply chain attack surface
- [TLDR Newsletter][tldr] - Source of the "write-only code" concept

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Thursday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/248-ai-all-the-way-down.md
[vibe-coding]: https://www.audible.com/pd/Vibe-Coding-Audiobook/B0DQJPB5VT
[1password-blog]: https://1password.com/blog/from-magic-to-malware-how-openclaws-agent-skills-become-an-attack-surface
[tldr]: https://tldr.tech/

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Cold Open

[00:00:00] **Adam:** I did the insights. I've only done it once.

[00:00:01] **Adam:** it said that I was a power user. 'cause I had managed to use Claude for 500 hours that week,

[00:00:07] **Ben:** 500 hours a week, baby.

[00:00:09] **Adam:** That's right.

[00:00:11] **Adam:** Take that tech bros. you're doing your 9, 9 6, I'm doing 500 hours a week.

## [00:00:37] Intro

[00:00:37] **Adam:** Okay, here we go. It is show number 248, and on today's show we're gonna discuss how it's just AI all the way down. But first, as usual, we'll start with our triumphs and fails. Carol's not able to be here with us tonight. She's just got a bunch of stuff going on, so she gets an excused absence. So Ben, I'm coming to you first my friend.

[00:00:53] **Adam:** What's going on, man?

## [00:00:54] Ben's Triumph

[00:00:54] **Ben:** Sure. I'm gonna kick it off with a triumph, which is that I'm going to be participating tomorrow in a human gathering. Uh, yeah.there's a local meetup, which I live in the boonies, so there's not a whole lot of meetups. And, uh, there's a local technology meetup called,the Open Hub Hudson Valley Meetup, I think. they're obviously doing stuff about ai, as is everybody. And I've been participating in some of their online zooms.

[00:01:24] **Ben:** but they're gonna have a, in-person meetup, just a couple of towns over and the host asked me to come and just do a little demo of some of the AI stuff I've been doing mostly 'cause I've been, having questions about how it all works. And, uh, I said yes. I, no bone in my body wanted to say yes.

[00:01:41] **Ben:** I absolutely wanted to say no. but I said yes anyway 'cause it was the hard thing and I'm trying to lean into it.

[00:01:48] **Adam:** So when was the last time you had like a, a microphone in front of your face that wasn't in your house for the podcast?

[00:01:53] **Ben:** I, I did participate in a live ish event at CF Summit last year. But, it was mostly being run by Ryan Brown, so it wasn't like. My show, per se. I was just like, a participant, but this is, it's not even really a lightning talk. I'm just gonna go up to the front of the room. It's in the library, so it's pretty low stakes.

[00:02:12] **Ben:** and just give a little demo of some of what I've been working on. So, I don't know. I'm terrified at the thought of doing a live demo, especially one that involves ai. my big concern is I'm gonna prompt something and it's gonna go off and think for like three minutes.

[00:02:26] **Ben:** I'm like, what do I do when I'm just sitting up there and there's people staring back at me? So I'm gonna have to

[00:02:31] **Adam:** Well, that's when you talk about how sometimes it thinks for three minutes and you just gotta like,find something to do or,

[00:02:36] **Tim:** have an arm wrestling competition in between.

[00:02:40] **Ben:** So I'm excited that,

[00:02:41] **Adam:** out another quad session and you start having to do more stuff on another

[00:02:44] **Ben:** do that. That's too, I, it's,I'm still at the kindergarten level. Anyway, I'm excited to, uh, try to push myself a little bit, even if it's just a, baby step lightning talk demo at a very, very local tech meetup.

[00:02:57] **Tim:** Is it really a lightning talk? Because it is like a,

[00:02:59] **Ben:** No, no, no.

[00:03:00] **Ben:** it's not a lightning talk. It's more like a

[00:03:02] **Tim:** short

[00:03:02] **Ben:** yeah, yeah, exactly.

[00:03:04] **Tim:** Yeah, because Lightning Talk is what we called, what was that called? PechaKucha.

[00:03:08] **Adam:** PiOh, PechaKucha or something.

[00:03:10] **Tim:** PechaKucha. Yeah. But you can, but you can't call it that 'cause it's like copyrighted. It's, yeah, it's a branding thing. So we called, I know 'cause we had the, that format where you show us, show a slide, talk about it for 20 seconds and you have so

[00:03:24] **Adam:** Yeah. The auto, auto advance or

[00:03:26] **Tim:** Yeah. I got auto advance. Yeah. We did that at, dev.Objective() set CF Objective years ago.

[00:03:31] **Tim:** That was a always fun. Ben did one on, uh love. Yeah.

[00:03:36] **Ben:** Yeah. Oh man. That was like, oh God, it's gonna be 15 years ago.

[00:03:40] **Tim:** Don't just shut up.

[00:03:44] **Ben:** So anyway, I'm going triumph, pushing myself, trying to lean into the discomfort. So I'm kicking over to Tim. Tim, what do you got going on?

## [00:03:52] Tim's Triumph

[00:03:52] **Tim:** I'm going for a win. So again, it's an AI thing, kinda like you were talking about. and I think we'll get a little bit more in, in depth when we talk about AI all the way down. AI's made me be a lot more bold when it comes to what languages or coding e ecosystems that I work with because I'll, if it's a greenfield project where I'm just starting from scratch, back in the day, I would just like, well, I'm just gonna write in CFML 'cause that's what I know, right?

[00:04:18] **Tim:** But like today, or actually yesterday, We're trying to come up with a better way to deal with incident responses, like when we have outages or downtime or things like that. and so I just started spit balling with Claude and it started, you know,had it ask me questions about, what tools we have.

[00:04:32] **Tim:** So we're on Microsoft 365. We used teams and all that stuff. I started that about six o'clock after work and worked for about five hours on it. And now I'm talk about it in the main part of the show. But I have a pretty cool system for, generating these incident things, generating meetings, generating the, notifications to, customers.

[00:04:54] **Tim:** And, so that's pretty cool. And then I, another project I did, I posted about it in our discord was I'm watching rewatching them. All of Ds nine, star Trek Deep Space nine. And, but the quality of the videos were awful. And so had, Claude helped me use, some existing like AI upscaling projects that are out there, but to build a Python executable that I could run on my laptop.

[00:05:19] **Tim:** And so I'm sitting here chugging even right now while we're talking, I'm, my GPU is chugging through, just going through all of these videos and upscaling them to 10 80 p from the old, uh, you know,

[00:05:31] **Ben:** Oh, it wasn't even 10 80 p. Dang.

[00:05:33] **Tim:** no, no. So deep Space nine, it was back in the nineties, I think 93 it came out.

[00:05:37] **Tim:** And so it was television quality, even though this was from A DVD and it's, 5 67 by four 90 some, some weird set

[00:05:46] **Adam:** it's like four by three. Yeah.

[00:05:48] **Tim:** it's four by three aspect ratio. So I had to upscale. It didn't change the aspect ratio 'cause that would look bad. But it, but yeah, it's.

[00:05:56] **Tim:** Pretty cool. I, I mean, I never would've said, Hey, let me build this thing with Python before, 'cause I don't really know Python very well, but yeah,

[00:06:02] **Ben:** that's, that is pretty cool though. So I was able to take a, 200 megabyte file and upscale it into a four gigabyte file.

[00:06:09] **Tim:** it didn't do too bad. Well, and that's the encoding that decides how big the file is. But what it did was it would like say someone's wearing an outfit, AI could interpolate, this outfit should have like fabric. It looks like fabric and you can actually see fabric patterns now.

[00:06:23] **Tim:** Whereas before it was just this blob of colors. and now it's, and now it, now you can actually see threads in the fabric. but I'll talk about it more in the main

[00:06:32] **Adam:** So it, did it just write Python that calls out to FFmpeg, or is it actually using like AI stuff as part of the conversion that it's

[00:06:40] **Tim:** It's, it's using, so there are some AI upscaling projects out there. it's the one I wound up using was, it's called Waifu2x

[00:06:48] **Adam:** Okay.

[00:06:49] **Tim:** Wife. Waifu is a Japanese for wife or girlfriend. so I don't dunno why they call it that. But anyway, two x and so it has built in AI functionality in it. That's only specific. it's a, it's not a general purpose ai, it's not a LLM, it's just a very, it uses AI specifically for improving, images.

[00:07:07] **Tim:** And so it pulled that project down, put it as part of my executable so that way I don't have to burn a bunch of tokens. I just burn the tokens to build the project. And then once the project's built, then I can run through and use the, that tool locally on my machine.

[00:07:23] **Adam:** That's pretty cool.

[00:07:24] **Ben:** Yeah. Very cool.can I ask a quick aside, just, uh, this is more of like a lazy Google situation. so I'm on a Mac, so I have a high density pixel display. Presumably I don't really understand how any of it works, and I occasionally do screen recordings and, so I use Camtasia I open my Camtasia and it says, what size recorded do you wanna do?

[00:07:46] **Ben:** And has a bunch of presets, like 10 80 p and 4K and eight k. And,it keeps doing this thing where it's like, I'll record on 4K size, but then when Camtasia goes to render the timeline. it shrinks the video down by 50%, which then the export is much faster. If I export at the original 4K size, it just takes a lot longer.

[00:08:10] **Ben:** and my question is should I even care about this? is,

[00:08:14] **Tim:** It depends on where the end result's going, right? If you're just posting it on a blog or a, if you're gonna watch this on a big screen,

[00:08:20] **Ben:** No, no, no. It's just like, code stuff. So it's like IDE, I'm looking at my ID or I'm doing a little browser demo, like

[00:08:27] **Adam:** One nice thing can be like if you're capturing at high resolution and if you're not aiming to output 4K video, but you know if you're gonna crop it and all that anyway, then capturing at high res gives you the opportunity, you have the pixels to play with or wanna zoom in on this and crop it this way or whatever.

[00:08:44] **Adam:** And you keep a lot of that resolution as if you had planned ahead and said, okay, I'm gonna capture a high resolution of just this square of my screen.

[00:08:52] **Ben:** Yeah, yeah, yeah. You can do those cools. Zoom in, zoom out,

[00:08:55] **Ben:** Gotcha. Yeah, I dunno. I just, it's one of these things I know I, I know nothing about video recording or editing and I figured out how to do something like 15 years ago and my mental model for it has not improved at all in that time, and I have a lot of guilt about it.

[00:09:11] **Ben:** And then all of a sudden high density displays came along. I'm like, oh,

[00:09:15] **Tim:** Looks

[00:09:15] **Ben:** I'm, yeah. I'm like way outta date now on how I think about this stuff.

[00:09:19] **Adam:** I feel like we gotta have mats to like put in like a, a ding sound effect or something every time we go off on a tangent so we can keep track of the number of tangents,

[00:09:27] **Tim:** Yeah. Something like, uh, that sounds like an a, an adventurer, like a video game when you do a Do a quest. Little side quest. Little sound.

[00:09:36] **Ben:** I like it.

[00:09:37] **Tim:** Yeah, that'd be interesting. Little, little meta show

[00:09:40] **Ben:** Sorry, didn't mean to to, to tangent us too quickly there, but, uh,

[00:09:44] **Tim:** Anyway, that's me. How about you, Adam?

## [00:09:46] Adam's Triumph

[00:09:46] **Adam:** I'm also gonna go with a triumph. Um, and it's a real simple one. Yeah, three outta three,basically, I built a bunch of code in the last, uh, let's see, today's Tuesday. So let's say like the last three days, right? Real heavy on Sunday and again today on side project, stuff on jump run and everything that I've built on jump run in those three days, which was basically like all day Sunday.

[00:10:10] **Adam:** while I ate dinner tonight, was something that I've been putting off since before LLMs were like, good at coding, right? These are features that have just been on the wishlist for a really long time. And I was, I finally was like, actually, I could, I can not write this code and make the LLM write the code.

[00:10:28] **Adam:** and it worked really well. And now, I mean, I say that, but I literally spent from probably like. 9:00 AM until 1:00 PM ish on Sunday. Literally like writing a spec, right? I talk about the Ralph Loop stuff and like how I have a spec kind of as JSON with all my tasks and requirements and stuff.

[00:10:48] **Adam:** And I have a, Claude prompt that I use to help me go from, here's a brain dump of just random thoughts. I want you to organize it and get it ready to put into the spec sort of thing. So it was like one of those conversations that I just kept going and iteratingand iterating and iterating. and so it was like two projects that I did on Sunday that I wrote the specs for and it took half a day.

[00:11:09] **Adam:** And then I would let Ralph run in. I think it ran for an hour or two, to. Complete all the work in that spec. And then after work ended today, before I went down for dinner, I specked out a couple of more features, which were smaller, but still, significant enough that I haven't taken them on myself.

[00:11:26] **Adam:** and while I was eating dinner, Ralph implemented now it's implemented all those things, and they're committed in their own little branches. I have not even opened a browsers to look at anything that has done yet, but it, it says it's done. that's close, right? It's a lot closer than I was before.

[00:11:41] **Adam:** the way that it has unlocked my brain to, to make this stuff happen is instead of thinking about it as using Claude to write code, I'm been thinking of it as Claude is a developer that works for me and I'm writing this specification, right?

[00:11:54] **Adam:** that's my job in this interaction is to just clearly define the problem. And if I happen to know, then point to specific things that will be helpful to, for Claude to see and read, to figure out, okay, this is actually gonna be a useful function for me. Or I, this is the route where I want you to put the changes, that sort of thing.

[00:12:14] **Adam:** and like just doing that sort of stuff has been really, productive for me.

## [00:12:19] Vibe Coding vs. Caring About Code

[00:12:19] **Ben:** I think that's gonna be my big hurdle,

[00:12:21] **Adam:** which is that, in my experience, which, is going on one week roughly, vibe coding felt exciting and freeing when I was just having a generate python code that I didn't care about to download videos from Patreon.

[00:12:37] **Ben:** I think I had mentioned this on the last show,

[00:12:39] **Adam:** You did.

[00:12:40] **Ben:** and like I didn't care what the code looked like. It ran, I could see that it was running. I

[00:12:46] **Adam:** He said, Paton not only fans.

[00:12:50] **Ben:** I was still learning obviously, and I'm still very much learning now, I just didn't care as much. it was very much more just about the output. Was it doing what, it's what it I wanted it to do. And then over the weekend, this past weekend, I started to use Claude Code to try to improve my big sexy poems side project.

[00:13:08] **Ben:** And this project, if you can, imagine it's not a commercial project, the point of the project was mostly for me to have a place to think about software architecture and figure out patterns that I wanna like, and try to think about previous frictions that have, I've never really had a good solution for.

[00:13:26] **Ben:** And can I reimagine how I might wanna put code together and strike the good, like a good balance between ease of development and also efficiency of the code, et cetera. And then I started throwing some vibe coding at. And I could not let go of my personal connection to the code. and like whatever efficiencies I was having from a CLA is both an amazing academic and an incredibly fast typer.

[00:13:55] **Ben:** Like those efficiencies that I was having with the Python code, suddenly it became. I really enjoyed having Claude Code as somebody to discuss the problem with and help come up with a plan and it could type faster, but it was really typing in one or two files. And when it was done typing, I would go in and I would look and say, ah, I don't really like the way this is done, or I don't like this variable name.

[00:14:18] **Ben:** Or like, I would literally go in and change variable names, change the comments that had put in. 'cause like, it wasn't my kind of code per se, so it was like it got me the 80% absolutely. But that 20%, I definitely spent a lot of time tweaking and fine tuning some of those little low devil details. And I feel like it, it, like I, I went from someone who could say, oh yeah, I could see how maybe I become like a 10 x more productive developer to be like, okay, I feel like this could make me 10% more productive.

[00:14:50] **Tim:** Yeah, of course, there are ways around that. It's like you can, I don't, I didn't like the way for code that I'm familiar with. I didn't like the way it named variables. It would, I don't like using like the letter I for any, , you know, you know what I mean?so, I,

[00:15:05] **Tim:** if you tell your Claude Code, your CLAUDE.md file, those kind of things, it will obey that, right?

[00:15:11] **Tim:** So if you can pinpoint those little code smells that you just don't like, that's your personal brand,you can have it do that, right? So that's,

## [00:15:20] Rewriting Code the Elegant Way

[00:15:20] **Adam:** so one technique that I found that's really helpful and useful is, you know how sometimes you like write some code, and it.

[00:15:28] **Adam:** It gets, fairly close to what you were wanting from it. But you, like you're saying you don't really like the code that I wrote and it's not a hundred percent of the functionality you're looking for. So you can kind of like steer it and it'll modify and build on it. And then this is the part that I like is when you finally get to the solution, but you're still not necessarily happy with the code.

[00:15:46] **Adam:** You can tell it. Okay. Now, based on what you understand about the problem, 'cause I've, brought you, you basically just say okay, take all that code you just wrote and now that you know where we're trying to get, write it again, throw it away and write it again as the elegant solution

[00:16:02] **Ben:** Oh, that's interesting.

[00:16:03] **Tim:** Yeah. A so I learned about this from our, I dunno who it was in our Discord. One of our, one of our listeners, told me about the slash insights.

[00:16:12] **Adam:** yeah.

[00:16:12] **Tim:** that, Ben?

[00:16:13] **Tim:** So if you go into Claude Code and put in, was it forward slash that way, forward slash Insights, it'll pop up with a choice.

[00:16:20] **Tim:** When you hit the slash, there'll be some things, but basically what it does, it reviews how you've been using Claude and it'll kind of review, here's how you're using it, and it,does some introspection on what it thinks you're trying to do, but it will also give you suggestions on things you're missing out on or.

[00:16:35] **Tim:** Common problems that you have over and over again. Like if you're constantly telling the ai, I know that's wrong, do it this way. And it's like the same, some sort of code formatting sort of thing or variable name. it will catch onto that and it will give you suggestions on how to improve your CLAUDE.md.

[00:16:51] **Tim:** And so you could take those and put them in your CLAUDE.md or you can actually tell it to, and he'll do it for you.

[00:16:56] **Ben:** so one of the things that I've been trying to do is I'll have Claude do a bunch of work and then I'll review that work and I'll probably make tweaks and, move some functions around every now and then. it'll wanna break something out into its own function and I'll look at the code and say, no, I want that function in line where it's used because.

[00:17:16] **Ben:** I find it easier to read the code as opposed to jumping to different functions and trying to keep track of what's going on, which, like already to anyone who's vibe coding is probably like a huge red flag in the way that I'm thinking about this. but I'll get to the end and we'll, like the work will be done and I'm still in that same context window, so it's still understands everything that's been happening.

[00:17:33] **Ben:** At least that's my understanding. And I'll say, Hey, look at the changes that I've made, and is there any updates you think we should make to CLAUDE.md file so that we don't have to make these kinds of mistakes or these kind of edits again? And it's actually been quite good about that. It'll be like, oh yeah, I see you made these changes and that's missing from the CLAUDE.md.

[00:17:53] **Ben:** Or like, oh, this is alluded to in the CLAUDE.md, but it could be much more explicit in the way you actually want it to be done. and I think one time I sat down maybe yesterday morning and I just said to Claude, Is there anything like, look at the code base, is there anything that you see in terms of the changes that we've made?

[00:18:11] **Ben:** I think I had to look at the Git log. I'm like, look at the git log and is there anything here that hasn't been well identified within the CLAUDE.md? And it finds really good stuff and it puts it in there and I'm nervous about making it too big, but apparently I've seen numbers that you can have your CLAUDE.md be like 15 to 20,000 kb kilobytes.

[00:18:27] **Ben:** And it's still like, okay, in terms of the context window, butI dunno like all this, like, I feel like I'm just gonna be too emotionally connected to the code and I don'tI don't know how to let go of that. I don't know if I should let go of that. I feel like everyone's telling me I should let go of that and I'm, and I don't know how to feel about it.

[00:18:43] **Ben:** I'm having trouble processing that part.

[00:18:46] **Adam:** I think what you're latching onto there is that the people who are saying, let go of, that are the loudest. That doesn't necessarily mean that there's, that's the majority of people. It just means that they're the easiest to pick up on

[00:18:59] **Ben:** Yeah, that could very well be for sure. Like with the greasy, not the greasy wheels here. The squeaky wheels.

[00:19:05] **Adam:** wheel. The greasy wheel gets the squeak.

## [00:19:10] Specifying Work vs. Building to Discover

[00:19:10] **Ben:** Okay. So let me ask you another question though, because you're talking about your jump run stuff and you spent two, three hours specking something out and I think this is

[00:19:19] **Adam:** more. Yeah.

[00:19:20] **Ben:** yeah, and I think this is also a big stumbling point for me because I feel like I don't even know what the software should do until I start to build parts of it.

[00:19:31] **Ben:** I get that on the page and I can play with it, and I'm like, oh, that's a terrible idea. I should definitely not do that. Or like, oh yeah, that's great, but I actually wanna take it in this other slightly different direction. and so it's like the idea of getting to this, Ralph Loop where I have 15 steps and each of those steps has seven different acceptance criteria.

[00:19:53] **Ben:** I feel like maybe I can think two steps ahead

[00:19:56] **Adam:** Right.

[00:19:57] **Ben:** and I need that to be on the paper so I can click on it and see how it feels.

[00:20:01] **Adam:** Well, that's the thing is like those, each of those tasks that's in that PRD for Ralph is way over specified. if you were just gonna do one of those things, it would be like one line in a to-do list for you, right? And it's over specified so that the AI can know when to stop and, know everything it needs to know to accomplish that, that you just have as like background knowledge that you don't even realize that you're calling on, this context available to you.

[00:20:30] **Adam:** that has to be explicitly provided.And I know it sounds crazy to have a two or three or four hour long conversation with the AI to write specifications for two features, and I completely agree with you on like, I don't truly, if I'm just sitting down to write code, I don't truly understand the.

[00:20:49] **Adam:** Path I intend to take until my code is partly written, right? Like I, I get there, I start writing it, and I go, oh yeah, what about this? And oh yeah, what about this? And how do I, how am I gonna handle this? And those things just don't occur to me in the planning phase. So, what the, my planning approach, when I'm planning, a feature to put into the PRD is, this prompt that I have, basically, it's like, I'm gonna brain dump at you.

[00:21:12] **Adam:** I just want you to keep listening, keep gathering information that I'm telling you when I don't think I have anything else to say, I'll let you know. And then I want you to, based on what I've told you based on relevant context, like at that point, go look at the code of the application that you feel is relevant to what I've been talking about, get an idea for what the feature's gonna be, and then ask any clarifying questions.

[00:21:34] **Adam:** And like, so one of the things I did today,I, you guys are somewhat familiar with the jump run interface, right? It shows a list of like upcoming flights and who's on them, and then. some details about what each person's gonna be doing on the jump. And one of the things I wanted to do was add to the top of each of those flights,a countdown.

[00:21:51] **Adam:** You're, this plane is taking off in 20 minutes. This plane is taking off in 40 minutes. This plane is taking off in 60 minutes. And so I said, you know, okay, we're gonna display a, a countdown, show me eight minutes only. and I want you to accomplish that by putting a database column on to store the timestamp of when it's gonna take off.

[00:22:09] **Adam:** And, update the timestamp on, on these pages once a second so that it's always, it's fairly close to correct. andI want you to put buttons on that, on the admin interface where they're controlling. 'cause I want you to put buttons to plus 20, plus five plus one minus 20, minus five minus one.

[00:22:26] **Adam:** to control the time.and that's the gist of what I put in there, right? I pointed out some specific files or something and it came back with like maybe a half a dozen to a dozen questions. what about when there's nulls? should I display,nothing?

[00:22:39] **Adam:** Should I display something? And what about what happens when the timer gets down to zero? Should it go negative? Should it just say, now? Should it display zero? these are things that didn't initially occur to me, but they were really good follow up questions, and it was really easy to answer that question.

[00:22:54] **Adam:** And sometimes it asks you a question and you're like, Ooh, yeah, that gives me, like that openness, a whole new line of conversation. And so it's like, I'll answer the question and then once it's done asking questions, it's like, okay, are you ready for me to build it? And in that case, I'll be like, no. Okay. Us, the usual flow is I'll say, okay, now write it to the PRD.

[00:23:12] **Adam:** but in this case, if it's at like, opened up a new line of thought, I'll be like, okay, not yet, don't write because now I have more to brain dump about you. And I'll just start brain dumping again and then. I have it, loop on that, on the planning process

[00:23:24] **Adam:** until

[00:23:25] **Tim:** you keep, hitting your mic.

[00:23:27] **Adam:** I, I banged my watch on my desk.

[00:23:29] **Adam:** Sorry.

[00:23:29] **Ben:** He's

[00:23:29] **Ben:** gonging.

[00:23:30] **Tim:** was? You gong, you got gonged yourself.

[00:23:33] **Adam:** yeah.

[00:23:33] **Ben:** Yeah. So if I can, maybe say back what I think I'm hearing. It almost sounds like you have. Two, three. It is there are three different phases. Phase one is, I just wanna talk about an idea, like almost in the abstract, I mean still in the context of jump run, but more so in the idea of jump run as opposed to the implementation.

[00:23:53] **Adam:** Mm-hmm. Yeah. I know. I'm trying to be like the point of haired boss standing behind the guy that's written the code being like, make it do this.

[00:23:58] **Ben:** And then phase two is you say to Claude, alright, go look at the actual code and jump run so that you have a better idea of what's already there, where the feature gap is, how we can fill it, what other questions. And then phase three is like, okay, now that you have the abstract idea and the concrete implementation constraints, you know the prior art, the existing code, let's now reconcile these two things and then ask me anything that you don't understand or might be an improvement or it could add clarity.

[00:24:28] **Adam:** Yeah, I mean, you could say that those are three separate phases. I would almost call it just two phases, let me brain dump and then go look at relevant files and ask me any clarifying questions. Kind of. Those are the two. Yeah. But

## [00:24:40] Building an Incident Response System

[00:24:40] **Tim:** So let me give you a concrete example of how I did. So I talked in our tribes of fails about our instant, notification and tracking systems where we have outages just to have a standard way to do it. So initially, first I went into like the Claude web face 'cause I didn't want it to create new files.

[00:24:58] **Tim:** I didn't want, I just wanted it to think and it just, I just found it's easier to do it there 'cause I know it can't. Touch anything. And so I say we are a software company. We have multiple projects running different versions of our PTS software. When there are outages or major slowdowns, we need to actively keep track of how the company notifies of the issues, who's working on it to resolve it, notification when it's resolved, and the after action items.

[00:25:21] **Tim:** We tend to work through Microsoft teams chats, outlook, email messages, teams meetings where we discuss the issue. make a suggestion as to different delivery methods we can use with a plan to build a software methodology that can assist in automating it and ensure that we follow our incident rules Very long run on sentence.

[00:25:39] **Tim:** It loves run on sentences.

[00:25:41] **Tim:** it does. And so it generated basically a markdown file with explain the core problem, talked about the different tiers, how to build the automation, Yeah. And so then I took that MD file, put it into VS Code, and then I referenced that code and said, here, you generated this for me.

[00:26:01] **Tim:** reviewed that file. It was generated from another Claude Code session. the last question you generated was, do you want me to start generating individual component files next, starting with the adaptive cards in the phase one flow definition? And so it started doing that, and then it started building the project, right?

[00:26:18] **Tim:** one thing I found that annoyed the heck outta me was,I, you guys probably, I don't know if you work at Microsoft, but if you'd done power automate, I had never messed with it before. It's sort of a,a no code interface where you build, Canvas and you put things on there, it's like scratch, you know, it's like scratch program.

[00:26:38] **Tim:** And so you build these cases and switch cases, but you can have all these hooks into other APIs, into Microsoft teams, into Outlook and things like that. And so it's all very visual, which I didn't really like working with, but I mean it's getting the job done. so it built some JSON files for me.

[00:26:57] **Tim:** And then one thing I ran into was like, a lot of times it doesn't know the version I'm on, so I remembered Adam had talked about how he would do screenshots of issues and put it into the AI and it would read the screenshot and then give it answers. So that worked out well. Thank you for that suggestion, Adam.

[00:27:16] **Adam:** Yeah, of course.

[00:27:17] **Tim:** But a lot of times he would tell me all these steps and the step, six, seven steps in a row and I'd do step one, two, and then I'd get to three and three. It absolutely has no bearing on reality of what's on the screen. And so I said, please stop giving me multi-step problems. I wanna work this step by step.

[00:27:34] **Tim:** And every single time I do a step, I want to give you feedback to, to test, to see if it works. And then af, once I did that, we really started making progress. It would do one thing. It'd say, okay, go here, click that. And I'd like, that doesn't exist. I give it a screenshot. I'm like, I don't see the button you're saying that exists.

[00:27:52] **Tim:** And I give the screenshot, it goes, oh, I'm so sorry. this is, and they say they don't gimme the right thing. just going through that step by steps, that way it doesn't, you don't get halfway down a huge step of files and then have to delete everything and go back. I could catch it earlier.

[00:28:08] **Tim:** So very, being very reiterative is extremely helpful in this case for me.

## [00:28:15] Deployment Orchestration in the AI Era

[00:28:15] **Ben:** and both of you are talking about working through steps, and this is also something that I'm finding is becoming a point of contention in my head, which is that historically I have wanted to take a larger problem and think about the steps that I can break it up into, not just to make it manageable.

[00:28:34] **Ben:** But also because in the back of my head for the last 15 years, I've been thinking about how do I actually deploy this? So if I have a system that, for example, has both backend database changes and front end angular changes that are calling that API, and I'm deploying to a system that has a 15 nodes that need to be deployed on a rolling basis, like that calculus was always in my head like, okay, I'm gonna have to do the database changes first, and I'm gonna have to fully deploy those because I can't risk deploying front end changes before that.

[00:29:07] **Ben:** Talk to a node that doesn't yet have the back end changes. So the. Orchestration of the journey of the feature development was always in the context of how does this code actually move from one place to another? And what I don't yet have any sense of how I'm supposed to do in the vibe coding world is have that type of thought where I can be like, okay, here's this huge feature we need to build.

[00:29:34] **Ben:** And definitely after you finish the data persistence layer, I need to review it because I might need to deploy this. And then you can't start on any of the other stuff until the data persistence layer is out the door. But I also don't know if that's just an old school mentality that I'm never gonna have to worry about again, or is that still very much like a real world constraint?

[00:29:55] **Ben:** Like I can't just blast out, a full slice, a full vertical slice of a feature that touches every tier of the web app.if, I can't deploy it in one piece either. So likegetting the AI kind of to Tim's point to be like, at this step you have to stop. You can't just keep going and I have to get involved and then you can go onto the next step like

[00:30:15] **Ben:** I'm still wrapping my head around even that kind of a thought.

[00:30:17] **Adam:** I see what you mean. And I've been there, right? So with Jump Run, I use database migrations and actually I don't have that problem. So I, I,I make database migrations or I have cloud right database migrations as part of my changes. And then when I deploy the changes, it's the build and release script that actually runs the migration that causes it to, to change the database.

[00:30:43] **Adam:** So in that regard, it's keeping it in sync. if anything, it's, it might be slightly ahead of the UI changes, right? Like you were talking about, you need the database changes out before the code changes, which is nice. And I guess I do need to be thoughtful about any deletes that I would do.

[00:30:58] **Adam:** Right? Make sure that that's kind of its own.

[00:31:00] **Ben:** Some changes are just easier and some changes are harder

[00:31:03] **Adam:** But I think that with, if you think about it, you could put that into some Claude rules, right? You could say database column removals and table removals are always their own poll requests that go separate from everything else.

[00:31:16] **Adam:** and so for that reason, they need to be on their own branch. And, we never combine 'em with any other, any code changes at all.

[00:31:24] **Ben:** it's like I used to be the point of friction, right? I was the slow thing in the loop. So this kind of thought process, like I was always in the way. And now that the code can run so quickly or, the coder can run so quickly because it's a machine. It's like that natural slowness just isn't there anymore.

[00:31:44] **Ben:** So it's like I have to reimplement part of that slowness. You know, not all of it is gonna be required, but some of it probably still will be. And I have to figure out how to reimplement that slowness in a very fast world.

[00:31:56] **Adam:** So you, I mean, when you were talking about the database, that's what I latched onto was the database

[00:32:01] **Ben:** it's the most easy to understand for sure. It, it's, it's the least emotional. Like it's the one that actually has a practical, real world impact as opposed to being like, I just like small commits. 'cause I can understand them. that's just more emotional.

[00:32:13] **Adam:** I get it. and sometimes, just like us, Claude is not going to anticipate every database change necessary to complete its work upfront. and just like us, there's ways around that, right? So you could have it just committing everything to one branch, and when that's done, you can just take those migrations and make a new branch off of Maine or whatever, only put the migrations in it and merge that and deploy that.

[00:32:38] **Adam:** And then when they come in from, your feature branch, I guess they, you could probably delete 'em from your feature branch at that point. I'm not entirely sure. but to like, to avoid merge conflicts or you just get merge conflicts and they're identical and you're like, okay, accept either it doesn't matter.

[00:32:53] **Adam:** But, yeah, I mean there, there's gonna be ways around that, but I see what you're saying. And it certainly could be a friction point.

## [00:32:59] Muscle Memory and PR Etiquette

[00:32:59] **Ben:** It's also like I'm, so it's one of these things where there's just so much muscle memory at this point, built up to the way stuff works. And,the database changes having to go out first. again, we latch onto that because I think that one is the easiest to understand because it has practical implications.

[00:33:18] **Ben:** It's not just emotional, but there is a tremendous amount of muscle memory that is in some strong way about the emotionality, about the team dynamics. 'cause I could never send a PR to someone that had, 3000 lines of code changing it. Like they'd think I was a,something that would've to be quacked.I can't tell you how many times, like I've gotten a large PR where I like every bone in my body wants to send it back to the other developer

[00:33:45] **Tim:** Did you say you have a large pair?

[00:33:48] **Adam:** No, he said he has a

[00:33:48] **Ben:** oh, that's p

[00:33:49] **Adam:** his body.

[00:33:51] **Ben:** where like every bone in my body has the urge to just send it back to the other developer being like, bro, you need to actually split this up into four prs.

[00:34:00] **Tim:** Oh,

[00:34:00] **Ben:** then like you. Yeah, yeah, yeah. And it's like you have something in here that isn't even related to this pr, it just happens to be a bug fix for something you came across.

[00:34:09] **Ben:** Like that's, when you're talking about when you were dealing with humans, like that's just, it's like there's an etiquette, but it, that's emotional. And I don't know,I have to like kill that part of me that is like, I want these to be small, neat commits and I want the commit message to be meaningful and I don't want it to, I don't know.

[00:34:28] **Ben:** like I'm trying to transport the decades of human perspective and try to overlay that onto a machine now. And I'm, that's, I can just, I can see already that's gonna be a big part of my struggle.

[00:34:40] **Tim:** I, I still don't think that's wrong. I mean, and I think you can get the AI to help you do that. You just gotta figure out how to tell it to do that way.

[00:34:47] **Adam:** Yeah.

[00:34:48] **Adam:** I don't think that, Claude is gonna fix a bug that it found, that's not germane to your task at hand. Right? Like it, a, it's probably not even gonna notice the bug is there. But b, even if it did, if it's not necessary to fix it, to complete the task at hand, it's probably not going to.

[00:35:03] **Ben:** Yeah. I like, and the changes that it makes are really good. I'm quite impressed with what it can do. Like, it, it was even finding things like I moved where I was incrementing a variable inside of a while loop and it said, oh yeah, that's great for 90% of the use cases, but there's gonna be this edge case that you're not considering where you, you don't increment it when you were supposed to.

[00:35:22] **Ben:** And then suddenly on the next loop iteration, you're gonna grab the wrong value. And I'm like, you're right. I dunno how you figured that out. Like you're correct. And that's bonkers that you were able to figure that out. 'cause you're not, you're not running the code, you're just staring at it. Right.

[00:35:34] **Ben:** With a, a

[00:35:34] **Adam:** even new. It's, it's, uh, auto complete,

[00:35:36] **Ben:** Right.

[00:35:37] **Ben:** Right. I know. It's insane. It's insane. So there's stuff like that that's just like genuinely extremely impressive.

[00:35:43] **Tim:** And just think, it was nine months ago, we were just laughing at it. It's like, oh, made these stupid. Now it's like we're, all of us are impressed. It's just, yeah, it's getting better I don't think people are talking about AI taking people's jobs. I think it's just gonna make our jobs.

[00:35:59] **Tim:** We're just gonna be doing more of it. Which,

[00:36:01] **Adam:** yeah,

[00:36:02] **Tim:** all of this a, people are getting laid off. I don't think it really has a lot to do with ai. Maybe a tiny bit, but the AI washing is what basically people are doing. It's like they're laying people off for other economic reasons and they're saying, oh, it's 'cause of AI in the software industry.

[00:36:17] **Tim:** I don't really think that it has anything to do with it right now. if you can just get more out of people, then they're just gonna get more out of people.

[00:36:24] **Adam:** Yep.

[00:36:25] **Ben:** Yeah.

[00:36:26] **Adam:** Yeah. If anything, AI should be increasing hiring because, oh, now we can get, everybody's a 10 X developer. Let's hire more 10 X developers. You know, like I.

## [00:36:35] The Vibe Coding Book

[00:36:35] **Ben:** So I finished listening to the Vibe coding book by, Gene Kim and Steve Yegge that I mentioned last week. And I quite enjoyed it. I think if you're already into vibe coding and you're understanding this, especially if you're looking at things like Ralph Loops, I don't think that book is gonna be a huge value add for me.

[00:36:56] **Ben:** it was more about painting the perspective and illustrating the landscape and where we are and what's coming and what's possible. But one thing that they do hammer home like a bunch of times in the book, and I think you guys are also alluding to this, is that if you ask Claude to do something and it doesn't do it right, like you are holding it wrong, meaning that there's something you could have done, either been more explicit in your prompt or had better, rules in your CLAUDE.md, or were defining skills that were specific to an area of the application or the type of code that you're working on, there's some tweak that you probably could have done to have done this last prompt better.

[00:37:37] **Ben:** If you fix that, it'll be better every time you do it going forward.

[00:37:41] **Ben:** that's the thing I'm like, I'm trying to remember every time something goes wrong and I wanna shake my fist.

[00:37:46] **Tim:** I think you need, do, need to run the slash insights. and one thing to point out on slash if you do slash insights space and then a dot, it will just only do insights on that local project. 'cause I, what I found was it was co-mingling my video upscale project with my other ColdFusion, which those are two totally different use cases.

[00:38:06] **Tim:** So,but one thing it gave me a reference to was having Platform aware research before inflammation starts, right? AI is

[00:38:15] **Tim:** not gonna, it's

[00:38:16] **Ben:** one more time.

[00:38:17] **Tim:** platform aware research before the inflammation starts. So implementation starts. So a lot of times AI just makes an assumption of what you're working with, right?

[00:38:25] **Tim:** so it says, for me to paste into my code before implementing anything, I need you to research and verify the target environment. So you basically explain, I'm running CFML on Linux or Windows or whatever, or an EC2 or whatever. Having all those things give the version number. 'cause that's been a lot of the things where the mistakes happen is it's assuming my environment when it doesn't know anything about my environment.

[00:38:48] **Tim:** And so having it, basically paste this in there, it asks you the questions of, what are you working with here before I start building stuff, which saves a lot of frustration later down the road. But that, but like I said, you just copy and paste these suggestions from the Claude report and.

[00:39:04] **Ben:** Yo. So maybe this is something you guys understand. 'cause I only ran into this today, which in my mind when people have said memory. I have taken that to mean, oh, the CLAUDE.md file or the AGENTS.md file, depending on your agent. And, I just, so this, I was dealing with Claude today at work and it made some sort of mistake and I said, Hey, how can we make sure that mistake doesn't happen again?

[00:39:31] **Ben:** And I, and it says, oh, I'll add that to my memory. And then I did a git status and nothing in the repository had changed. And I was like, I thought you added it to your memory, but I don't see any changes in the CLAUDE.md file. And it said oh no, actually my memory is a totally different working set of information outside of the CLAUDE.md file.

[00:39:48] **Ben:** And that I was like, what? That was totally not what I had thought people meant when they said memory. What I could look this up. I just haven't is memory. What is memory? Do you guys know?

[00:40:01] **Adam:** I do believe it is just like another text file.

[00:40:04] **Adam:** it's in the, like,your user profile directory slash claude, and then it's like memory or something in there.

[00:40:10] **Ben:** Gotcha. So it's not specific to the project

[00:40:13] **Tim:** and I wonder if that's new. 'cause I only noticed that this past week.

[00:40:16] **Adam:** same.

[00:40:16] **Tim:** Where, where it, I think it's a new thing. So it, I told it to update it. It said yes. I updated my memory MD file, which is in my user's folder. It's not in my project. So if you do a git status, you're not gonna see it.

[00:40:29] **Tim:** 'cause it's not the same folder. It's sort of like, it's global memory.

[00:40:34] **Ben:** Oh, okay. That makes more sense. and so maybe historically, when people have said memory, they are talking about these agent files. It's just that now there's more nuance to it.

[00:40:44] **Adam:** Yeah. Could be.

[00:40:45] **Tim:** To be, I don't know. I've never seen it referenced at M Memory MD before, but I've never, until I started praying around with insights, I'd never actually looked in my user's folder to see what was there. There's a whole bunch of crap in there.

[00:40:57] **Adam:** Yeah. It's got like a whole bunch of data about your past sessions,

[00:41:01] **Ben:** Interesting. Maybe that's where the insights can come from too.

[00:41:04] **Adam:** it

[00:41:05] **Tim:** It is. That's where the insight, that's where the Insights report is.

[00:41:08] **Adam:** And that, yeah, that's like the data that it parses through to, to generate insights. And speaking of insights, since we keep mentioning it, I just have to have a little laugh here because I did the insights. I've only done it once. and I had definitely had been using Claude for more than a week, but it said you've been using Claude for a week.

[00:41:24] **Adam:** Or maybe it was said it was looking at a week's worth of data or whatever. But, it said that I was a power user. 'cause I had managed to use Claude for 500 hours that week,

[00:41:34] **Ben:** 500 hours a week, baby.

[00:41:36] **Adam:** That's right.

[00:41:37] **Adam:** Take that tech bros. you're doing your 9, 9 6, I'm doing 500 hours a week.

[00:41:44] **Ben:** Oh,

[00:41:45] **Adam:** so

[00:41:46] **Tim:** it it it told me I'm using Claude as a genuine project partner.

[00:41:50] **Ben:** there you go. Very elegant sounding.

[00:41:52] **Tim:** Going from research to architecture to implementation in a very disciplined way. Well, thank

[00:41:57] **Ben:** You're freaking pro dude.

[00:42:00] **Tim:** A gentleman and a scholar.

## [00:42:03] Ten Thousand Lines a Day

[00:42:03] **Ben:** one of the other things that I feel like, going back to the vibe coding book, Gene Kim, Steve Yegge, I feel like they're stressing two different things that feel like, in theory they're not in conflict, but in practice I feel like they are, which is that you're gonna be generating. 10,000 plus lines of code a day on one hand.

[00:42:24] **Ben:** And then on the other hand, you as the developer, it's your responsibility to fully understand what the code is doing. And anything you deploy to production is something you own and you are fully responsible for. And then they start talk that, that's like 10,000 lines of code if you're just like at normal mode, apparently.

[00:42:43] **Ben:** But then you can start to have multiple agents running in multiple tabs. And then you can have like agent orchestrators and at some point I feel like. it's impossible for people to continue to understand code at that volume and that amount of change. and I, this is not just from the Vibe coding book, but just generally when I'm listening to other podcasts or watching other presentations where people talk about ai, I feel like they keep saying these two things.

[00:43:09] **Ben:** you're responsible for all the code. You have to understand it, and, you're about to be a thousand times more productive.

[00:43:16] **Adam:** Yeah, I mean,

[00:43:18] **Ben:** uh, what?

[00:43:19] **Adam:** disingenuous to me. Like, to me, the, the definition, the like 1 0 1 of vibe coding is you're not looking at the code, right? You're vibe coding is all like, here's my idea. Go build it. Cool. Okay, this part of it doesn't work, go fix it. And I, you know, I don't care what the code isand that's why there's security bugs and everything and all this stuff.

[00:43:36] **Adam:** But likethat is what vibe coating is. And if you're looking at the code, then you're not vibe coating. You can start as a vibe coating and then,expand beyond that, but,

[00:43:46] **Tim:** it's funny you say that 'cause TLDR newsletter today had, a article referenced called Write only code,

[00:43:53] **Adam:** which basically says that we're moving toward a future where large amount of production code will never be read by a human. This right only code feature will happen when software production scales beyond human attention,

[00:44:04] **Ben:** Yeah, and I don't, again, like, I don't know how I feel about that,

[00:44:07] **Tim:** I know, which makes me wonder, we've had a whole lot of outages of a lot of really big systems lately. I'm wondering if they're just doing right. Only code.

[00:44:14] **Ben:** not just outages. We've had the supply chain attacks that Adam was talking about last week.

[00:44:18] **Adam:** Yeah.

[00:44:19] **Ben:** the, all the

[00:44:20] **Tim:** GitHub was down.

[00:44:21] **Ben:** Malt Malt book leaked, thousands of people's credentials and stuff. It definitely feels like every day or every other day there's some sort of pretty large

[00:44:30] **Adam:** you brought it up and I've been looking for a good place in the show to bring this in. we're getting close to the end here, so I'll go ahead and drop this in. So last week on the show we talked about LLM supply chain attacks and skills and how that all comes together.

[00:44:42] **Adam:** And there's a lot of trust being thrown around that isn't necessarily deserved and is definitely being exploited in some cases. I hadn't seen it when we recorded though. Apparently this article I'm gonna talk about was published the day before we recorded last week's episode. so it's on the 1Password blog.

[00:45:00] **Adam:** 1Password, if you've never heard of it. No, I'm just kidding.

[00:45:04] **Tim:** You wonder where.

[00:45:05] **Adam:** yeah. on the 1Password blog, we'll link to it in the show notes, but basically it's, it goes real deep into this LLM supply chain stuff. and, talks about like the specific exploits that were happening in Open Claw, AKA,

[00:45:19] **Ben:** Malt Malt Malt book.

[00:45:21] **Adam:** yeah, malt Book was like a product built specifically to work with Claude Bot slash Open Claw. but yeah, like he, he refrained from sharing specifics of what the exploit was and which things were, were vulnerable or malware or whatever. 'cause he didn't want to, make it easier than it already is for people to go, oh, hey, look, it's that easy to go, start stealing stuff.

[00:45:45] **Adam:** but yeah, apparently the, even the most installed or one of the like top installed, plugins for. Open Claw was like a Twitter plugin, and that was affected, like it had code in it that was just like, if you install this skill, it's going to, it is gonna scour your machine for secrets and report them off to elsewhere.

[00:46:05] **Adam:** that's all you had to do is install the skill that

[00:46:07] **Tim:** Wow.

[00:46:07] **Ben:** I, I think I heard,maybe it was like the Verge cast or something. They were saying that it was like, I think they were talking about mold book, or they were talking about, or no,open claw and like the top, like in the top 20 most popular skills, like six or seven of them are just straight up malware.

[00:46:26] **Adam:** Yeah.

[00:46:27] **Ben:** It's just crazy. Oh, it makes me so nervous.

[00:46:30] **Adam:** yeah, and I'll just reiterate what the, one of the big points of this article was like, if you have installed this thing, you should consider it, very likely a security incident if you installed it on like a work computer. and I know I have mentioned on the podcast that I did install it on my laptop.

[00:46:47] **Adam:** however, I will also point out, I am pretty sure I said I didn't install any of the plugins. 'cause I started going through the list of available plugins and I was like, I don't use Twitter anymore, so I don't need that plugin. And there, there was like, I think there was like maybe one or two things that looked interesting to me and I was like, eh, this just doesn't seem like it's gonna be a good fit.

[00:47:05] **Adam:** So the same day I installed it, I also uninstalled it. And I neverdid anything with it. Never installed. I think I installed like one plugin and

[00:47:14] **Ben:** Huh. it's all just, it's all just changing so fast and I feel like we're, like, all of our heads are spinning so much that I think we're at least in, at times, losing perspective on all of the good practices that we've had. Like I clearly in my world there are quote unquote good practices that I'm probably gonna be holding onto for longer than I should, that they're actually gonna start holding me back.

[00:47:37] **Ben:** But I think that there are genuinely good practices that are just good. Yeah. That are forever good.

[00:47:46] **Tim:** Evergreen

[00:47:47] **Ben:** Yeah. And uh, you know, we can't lose track of those. We can't lose sight of what's ultimately good.

[00:47:53] **Tim:** because it's AI all the way down.

[00:47:55] **Adam:** From here on out, at least

[00:47:58] **Ben:** Okay,

[00:47:58] **Ben:** so, tea. Earl Gray Hot.

## [00:48:00] Building Software vs. Maintaining Software

[00:48:00] **Tim:** so here's another thing that I heard just yesterday. I dunno if you've heard of the company Lovable. They're one of these AI coding platforms. I think like they'll deploy stuff for you.they have a full-time vibe coder at the company. Like his whole job is just to vibe code stuff and help prototype projects and help bring things from idea into real life and to work with different teams.

[00:48:22] **Ben:** And he said at some point in this interview that I don't know how strongly he meant it. Maybe he just said it, off the cuff, not thinking about it. But I feel like what he said was that there is a difference between building a product. And maintaining a product.

[00:48:36] **Tim:** Hundred percent.

[00:48:37] **Ben:** 'cause he did talk about like, oh, I can just vibe code stuff.

[00:48:40] **Ben:** But then of course there's gonna be a whole different set of skills for people who need to maintain software. And I don't know if that's something that's really been discussed very broadly with all the vibe coding stuff. I feel like when people talk about it, it is a one size fits all solution. So it was very interesting to hear someone who is literally a professional vibe coder saying that there's actually a difference between these two gestures.

[00:49:03] **Ben:** That building software and maintaining it is different and it's gonna have a different field. It's gonna have a different set of skills.

[00:49:09] **Adam:** Yeah, I don't think that you'll be able to scale maintenance work, like you can scale creation work, like the Ralph Loop is all about creation, right? Let me

[00:49:18] **Ben:** Right, because

[00:49:19] **Adam:** change or addition

[00:49:21] **Ben:** 'cause it's greenfield at least, maybe in a focused way, but it feels very greenfield and that's very different. Then I have a customer ticket and they're saying they don't like how this one little part of the app works, and now I have to go get on the phone with them and I have to understand what it is that there's problems and like how do they work on their team and is there something that we can do to fix it?

[00:49:38] **Ben:** Is there some way we could take that idea and flesh it out a little bit to be more broadly applicable to not just this customer? Like you can't, you know, maybe you can get to something at that point where you can say, okay, now I can put this in a little bit more of a automated loop. But I just feel like the scope of it is probably not gonna be that huge to begin with, where you're gonna hit run and then step away for four hours.

[00:50:01] **Adam:** that's the thing is like the work involved there is like 90% understanding, 10% coding, and Ralph can only do, or not Ralph, Claude can only do the, the 10% coding,

[00:50:12] **Ben:** right. Okay. So like,I dunno, part of me is comforted that there's that divergence, I guess in, in the like, things that it's really good at. Because like, you know, if I look at something like the Ralph Loop, it's not a huge leap for me to start to catastrophize, to think, okay, then why can't my managers just replace me?

[00:50:32] **Ben:** But if that level of velocity can only be really achieved in like a truly green field, there's no prior art. We haven't even dealt with customers yet. I just need to blast, a hundred features into this app overnight. But that's gonna be very different from maintaining it. And I need people to understand customers and I need people to get, get on the phones and I need people to think deeply.

[00:50:55] **Ben:** if that's still available, then that makes me feel less replaceable. And that's very comforting. And I feel, I just feel like that doesn't, I feel like I haven't heard a lot of people have that discussion. I'm listening to.

## [00:51:09] Vibe Coding in Safe Sandboxes

[00:51:09] **Adam:** going back to the vibe coating thing a little bit, I do think that there is room for vibe coating in creation work. Within certain, like safe sandboxes, right? So I'm pretty sure I've mentioned on the past, or on the show in the past that, I would love to have like a personal kind of SharePoint instance.

[00:51:29] **Adam:** I don't want SharePoint, I don't want all the baggage that comes with that. I don't want all the complexity that comes with setting up and maintaining that, but I just want like a document store that I can share with my team that can have a permission system. So I can say, okay,my direct report can see the, the performance evaluation that I've uploaded in here for them, but nobody else can.

[00:51:48] **Adam:** And like these compliance stocks that I put in are available to all of the management team, but not to everybody in the company or whatever, right? Like just varying, rules and restrictions. But I just want, ultimately it's a, it's like Google Drive, but like it's less, less shareable and more organized and just organized differently.

[00:52:06] **Adam:** and I've talked about that on the show. having wanted that, have I talked about the thing that I built that was trying to solve that for me? I called it tagle, if that helps

[00:52:15] **Ben:** I don't think so.

[00:52:16] **Adam:** No. Okay. So yeah, I did vibe code this app, but I, wanting it to be super secure, like I didn't just be like, okay, make me a secure app that does this.

[00:52:24] **Adam:** Right. I, actually put some real effort into designing the authentication and roles and security stuff thoughtfully. I did use AI to write the code, but I was like, okay. it was very interactive, very like, okay, do one thing. Here's the thing I want you to do, and now let's like build this on it and build this on it.

[00:52:43] **Adam:** And then within it, I can be now with all that stuff set up and rules in the CLAUDE.md that say, okay, like every action has gonna have some security. Considerations, right? These are the types of, thing, these are the types of rules that can be applied. We can have documents that are, specifically listed as shareable, specifically listed as restricted.

[00:53:03] **Adam:** These are the types of restrictions that are available, that sort of thing. And, and I can say, okay, now I want you to build in support instead of documents. I wanna just be like, have A-A-U-R-L that's saved instead of a file and, can build that as a new file type or whatever. and, being extremely hands off in that creation mode, but with having built a safe, bubble for it to play in, I guess

[00:53:27] **Ben:** it, I listened to an interview with, the guy who created the Ralph Loop hat Hatley something I think.

[00:53:36] **Adam:** yeah, I forget his name.

[00:53:37] **Ben:** I feel like I, in his interview, he was saying that he would, he could go to a product, like a product that existed out in the world and say to Claude, go examine this product and come up with a specification for it, and like, have that specification be extremely detailed based on all of the documentation that's out in public.

[00:53:57] **Ben:** And then once he had that, he could then say, okay, now that you have this super detailed specification, go and rip it out overnight kind of a thing. which, whatever, that's like a whole other philosophical landmine I don't want to step on right now. But,but like that kind of again, goes back to your whole thing about spending all the time specifying something so that it's really clear and then you can be more hands off on how it's actually getting done.

[00:54:24] **Tim:** Kind of a somewhat of a tangent. have you guys ever

[00:54:27] **Adam:** Ding.

[00:54:29] **Tim:** whatever sound effect, I used VS Code and you know, you have a little side window where I tell it to do stuff. I just learned recently that you can basically. It has a feature called run in background, but you can't explicitly call it, but you can say something like, search for you, do research, so search for X in the background or look into that while we keep working on this.

[00:54:50] **Tim:** And it will spin off a side project

[00:54:53] **Tim:** and'cause a lot of times you sit, I would tell it to research something, I sit there and go get a coffee and whatever. But I found out you could just tell it to say, Hey, go do this in the background and it'll go do a bunch of research and then come back to you with an answer when it has it.

[00:55:07] **Tim:** And in the meantime you can still keep working on other stuff,

[00:55:10] **Tim:** which

[00:55:10] **Adam:** Yeah, I mean I've seen the keyboard shortcut for that in Claude Code and the terminal. and I wasn't really sure about what it did until like earlier this week. I haven't actually bothered to use it because my approach is just, I open another tab in my terminal and I, just go open another Claude session, especially if it's not something I need for the purpose of the session that I'm using.

[00:55:31] **Adam:** There have been plenty of times there where it's, it's chucking away on something and it takes eight minutes or whatever to answer the question I've asked it or to complete the thing I'm doing. And it offers to run in the back where in background I think it says press ampersand or B or something, control B to run in the

[00:55:45] **Ben:** B in there.

[00:55:46] **Adam:** Yeah.

[00:55:47] **Tim:** me that option.

[00:55:48] **Adam:** this is specifically in the terminal app. I don't know if you

[00:55:50] **Tim:** Oh yeah. I'm using

[00:55:51] **Adam:** but,and, You can run it in the background, but I don't want to have two conversations going in the same context window or the same session or whatever, Like I'm, I'm so kind of anal about the context window that like, when I'm done with something, I would say, I'm about 50 50.

[00:56:07] **Adam:** I'll either type the slash clear to clear the context and start over when I'm truly ready to start something fresh. Or I'll just click close the whole browser, uh, or terminal tab and start a new one.just to keep it a hundred percent clean. so like,I can't imagine when I would want to let some, like take a thing that I just told it to do after, you know, whatever other prompts prior to that.

[00:56:28] **Adam:** It starts running and it's taking a while and I would go, okay, let this run in the background and I'm gonna do something else. no, that's not how my management, my understanding of the best practices of this stuff works. A separate session on the side and running things in parallel. That sounds great, but

[00:56:42] **Tim:** I, I think that there's three things that are advantageous in doing it that way is that one, it has all the full context of the prior conversation that you've had, so it knows what you've been discussing. And know the files you looked at it knows what the problem is. And then two, it kind of jumps in, it can immediately jump in the conversation when it's done.

[00:57:02] **Tim:** And you don't have to, jump around. But then there's also no need to re-explain the problem or reread files. So you might save on tokens is the only thing I can think of that would be better about that, particularly if you're using the VS Code plugin.

[00:57:18] **Adam:** that's the thing though, is for me, if I do care about it, keeping that context, I, that's why I don't wanna split it off from the current session because I'm not the, I guess maybe it's possible, like if you've got a checklist, you're trying to do four things and they all require some level of the same amount of context, right?

[00:57:35] **Adam:** understand the routes for this app and all that, then it might make sense to be like, okay, here's, we're gonna work on project A and so set up all the basic context and then start it working on project A, and then you say, okay, running in the background, now we're gonna start on project B. That depends on 90% of the same original context.

[00:57:50] **Adam:** That might be a useful approach to it. But other than that, I can't think of a reason why that would

[00:57:56] **Tim:** Yeah, I mean, I don't know. I just found out about it yesterday, so I'll report, report back if it's more pain that it's worth.

## [00:58:04] Limits of Multitasking with AI

[00:58:04] **Ben:** I also feel like my ability to have multiple conversations diverging,the, ability to think as a muscle and obviously the more we practice thinking certain ways, the stronger we can get at it. But I do think there's gonna be some very humbling upper limit of the amount of parallel conversations you can really keep straight in your head and like how fast you can jump back and forth between these things. I, I've heard people in interviews talk about how they're, they'll be like simultaneously working on four different projects and different terminals

[00:58:41] **Tim:** Yeah, they

[00:58:41] **Ben:** and.

[00:58:41] **Tim:** need me.

[00:58:42] **Ben:** Yeah. And Ralph is running and I don't think that is the norm. Like I don't think that's gonna be the new baseline. I feel like those are people that can just operate at an extremely high level.

[00:58:56] **Ben:** and I, maybe I'm nervous to say that's gonna be become the new baseline because I don't feel like my brain can operate that way. But I feel like most people's brains can't operate that way.

[00:59:06] **Tim:** Humans are famously really bad at multitasking. They think they're good at it. They're not.

[00:59:10] **Ben:** And I dunno, it's, I'm, again, I'm still just trying to reconcile everything that I'm hearing.

## [00:59:16] Patreon

[00:59:16] **Adam:** Well, I, you know, why don't we, uh, wrap this. Let's land this plane, wrap this up. and I think that this is a great place to do it 'cause it gives me a chance to say, this episode of Working Code was brought to you by unlocking whole new levels of productivity by becoming a time Lord, getting access to 500 hours a week.

[00:59:31] **Adam:** and listeners like you, if you're enjoying this show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording, editing, and transcription costs. We could not do this every week without them.

[00:59:44] **Adam:** So special thanks to our top patrons, Monte and Giancarlo. You guys rock.

## [00:59:48] Thanks For Listening!

[00:59:50] **Adam:** We're gonna go record the after show. That is when, outro music plays and the unwashed masses leave and the patrons stick around and we keep talking. And we got a couple of things we're gonna bring up. the project Hell, Mary movie is coming.

[01:00:01] **Adam:** We're

[01:00:01] **Ben:** Ah, nice.

[01:00:02] **Adam:** they released the final trailer, which I think was, a fun for me. As somebody who's read the book, I'm not gonna get into it. We're gonna talk about the final trailer. We're gonna talk about some other related stuff. but, yeah, we just keep talking. Sometimes it's books, sometimes it's tv, sometimes it's more code.

[01:00:17] **Adam:** Sometimes it's Tim's strange culinary habits. You never know. You don't know till you get there. So if you'd like to check that out, go to patreon.com/workingcodepod, throw a few dollars our way.

[01:00:26] **Adam:** We'll give you all episodes of the past after show, and access to new episodes of the after show every week. That's gonna do it for us this week. We'll catch you next week, and until then,

[01:00:36] **Tim:** Hey guys, I just typed into our podcast slash insights. It only says this, your heart matters.
