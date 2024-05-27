---
title: "180: The Laws of Software"
description: "On today's show, we discuss a few of the entries outlined on the website, the Laws of Software. Topics include Atwood's Law on JavaScript, Cunningham's Law on getting answers, Parkinson's Law on getting things done, Goodhart's Law on taking measurements, Hofstadter's Law on inevitable failure, and the Peter Principle."
date: 2024-05-29
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/0c1ca143-d805-44e1-a194-10fcfca56019"></script><div class="redcirclePlayer-0c1ca143-d805-44e1-a194-10fcfca56019"></div>

On today's show, we discuss a few of the entries outlined on the website, the [Laws of Software][laws-of-software]. Topics include Atwood's Law on JavaScript, Cunningham's Law on getting answers, Parkinson's Law on getting things done, Goodhart's Law on taking measurements, Hofstadter's Law on inevitable failure, and the Peter Principle.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[laws-of-software]: https://www.laws-of-software.com/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/180-the-laws-of-software.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Tim:** Cunningham's law from Ward Cunningham. No relation. The best way to get the right answer on the internet is not to ask a question. It's to post the wrong answer. A

[00:00:09] **Adam:** honestly, you know what? I think it works best in like a discussion setting, I do think that it works like on Reddit.

[00:00:15] **Tim:** I think it works on this podcast.

## [00:00:39] Intro

[00:00:39] **Adam:** Okay, here we go. It is show number 180 and on today's show, we are going to talk about the laws of software. We're going to be giving out some tickets, coding misdemeanors and the like. Uh, police.

[00:00:51] **Adam:** yeah, but as usual, first, we'll start with our triumphs and failures. Carol couldn't be with us here tonight. she's still, unpacking boxes and can't find her recording equipment yet. So, maybe next week we'll get her back in and, we'll, we'll lighten up the testosterone on this podcast a little

[00:01:04] **Tim:** Mm hmm. Mm

[00:01:05] **Adam:** in the meantime, I guess I will go first, seems like it's been a little while since that's happened.

## [00:01:10] Adam's Triumph

[00:01:10] **Adam:** and I'm going to start us off with a triumph. And really, you know, things have just been going smooth and, and, I don't have a whole lot to complain about. So right now I'm just going to go with the triumph that is my co op. You know, this junior developer that I hired, it's going smoothly. He is super independent right now, working on adding tests and adding, what is the word?

[00:01:28] **Adam:** Continuous integration workflows. So that like, you know, things that previously didn't have tests, not only is he adding the test suites, but he's adding the continuous integration configuration to run those tests for pull requests and on deploys

[00:01:39] **Ben:** Oh, wow.

[00:01:39] **Tim:** Very nice.

[00:01:41] **Adam:** And so that's going swimmingly. and you know, one of the things that's made that possible too, which, is just also super nice is that we put in a bunch of work earlier this year to move all of our secrets out of config and into 1Password and use like some integration stuff to be able to pull that up at runtime, load it directly out of 1Password over their API.

[00:02:04] **Adam:** and that way, so like, We do have a couple that are stored is like environment variables within GitHub itself that, that get used for, integration or for, for whatever, you know, secrets they need for that. but for the most part, you know, like there were hundreds of secrets as you accrue over the years of doing stuff.

[00:02:21] **Adam:** and so I just can imagine it would have been a total nightmare to try and have him work on something like that. but. To have it be like, okay, well, you can't touch that. You can't have access to that repo because it's got secrets in it sort of thing. That's, that's another sort of big triumph is just like knowing that it's safe and secure and, and being able to.

[00:02:43] **Adam:** Spread that work out has been very nice.

[00:02:45] **Ben:** Yeah. You've set it up so that your co op can't accidentally drop a production database. That's always,

[00:02:50] **Adam:** Yes, that's right. And I mean, by multiple, means as well, right? So like, not only does he not have a username and password for the production database, but like our VPN thing has him in a group where when he connects the VPN, he can't even connect to the production database server or any of them, like in that group or whatever.

[00:03:09] **Adam:** So

[00:03:10] **Tim:** So he he's been with you. How long?

[00:03:12] **Adam:** that is a good question. his first day, I think was, I want to say May, First, second, something like that. Let

[00:03:19] **Tim:** So about, so about three weeks.

[00:03:22] **Adam:** It feels like it's been longer than that, but I'm going to pull up on the calendar here. Yeah. Okay. It was April 1st.

[00:03:28] **Tim:** Okay. All right. So it's been a little more than a month. I find, I kind of. Found the same thing when we, this has been several years back, but when we hired a bunch of interns, Carol was one of them, felt at first it was like really just slow and it was like pulling teeth to, you know, you're like, you feel bad because they're not really doing anything productive at the same time.

[00:03:49] **Tim:** You don't have time to handhold, but then you spend some time and then eventually it gets to the point where, oh, it seems almost like a light switch goes off and like. Now that, oh, now they're getting stuffed. Are you getting surprised by what they're getting done? Like, Oh, look at that. Okay. It's just, I think the momentum kind of builds up over time and then it eventually just kicks in.

[00:04:08] **Tim:** So,

[00:04:08] **Adam:** And I mean, there's still, you know, opportunities for, some mentoring, you know, like he wrote some tests and he did, this is such a, like a tiny little nuanced thing, but it was like, for me, it was like a light bulb, like, oh, this is a perfect, you know, piece of feedback for me to give him in a code review.

[00:04:22] **Adam:** I might've even talked about this last week, but like, you know, he was writing some tests and he used assert. ok, which just verifies that whatever expression is inside the assertion is true. Right. And then if it, if it fails. If it's falsy, then it would, it would fail the test and it would just say assertion failed, right?

[00:04:41] **Adam:** But he was doing it to check the, that the expected node version was the node version that was running during the tests to, to guarantee that the tests are running on a similar environment or production environment. And, but he was just saying like assert. okay, you know, node version equals this, right?

[00:05:00] **Adam:** And so you get true or false from that. But If it fails, you don't know why. You just see assertion failed and you have to go like, trace it back and figure out what's going on, right? So what I did was I was like, this works, this test passes, and that's good. Here's how we can make it better, right? Instead of assert.

[00:05:15] **Adam:** okay, let's do assert. strictEqual. And then put like expected on this side and actual on this side. And then when it fails, you'll see, I expected version 20, but I got version 19 and then you'll know exactly what the problem is. So just like little things like that or that, or like, you know, just how does stuff, he's got the software fundamentals, but he doesn't understand fully yet, which, and I would, I wouldn't expect him to is like how it all comes together as our product and like the domain knowledge.

[00:05:43] **Tim:** That's cool.

[00:05:44] **Ben:** Let me, let me ask you tangential question for a second, because he's sitting there and he's learning some about this, CI, CD stuff and GitHub actions and whatnot. And I admittedly know very little about CICD. I understand it philosophically. There's like a server somewhere that does some building that prepares some stuff to be deployed.

[00:06:08] **Ben:** Like I, that's like it, like that's literally the amount that I understand. And it has always felt very much to me like this big, scary black box. And I know historically when I've come up against black boxes, I've That usually when I peer inside and try some stuff out, it's always not nearly as scary as I thought it was.

[00:06:29] **Ben:** A silly example is XML. there was a time in my life where XML was this abstract document format. I didn't know anything about it. And then I tried it. I'm like, Oh, it's just text. And there's just like a child parent relationship between notes. It was actually quite simple.

[00:06:44] **Tim:** It got, it has tags. You should be comfortable

[00:06:46] **Ben:** know. So my question to you is, do you think CI, CD as a topic in general follows along with that trend?

[00:06:57] **Ben:** Or would I peer into that box and be like, Oh, this is just as weird and complicated as I was afraid it was going to be.

[00:07:05] **Adam:** I think that. If you start with GitHub Actions and like modern tooling, it doesn't have to be GitHub Actions, but that's just a good example of a modern toolkit for CICD stuff, then yes, it's going to be like that, you know, looks scary from the outside black box. you know, at the end of the day, sort of the, the value proposition of GitHub Actions is You don't have to do really that much work to make it work, right?

[00:07:29] **Adam:** You, you put a YAML file in the, in a folder with a specific name and they have some documentation on like what things you can write in that YAML file and you know, like, here's how you tell it to check out your code. Here's how you run a makefile or, you know, run a node command or execute your own script or run a go thing or whatever, right?

[00:07:50] **Adam:** And here's how you can set environment variables and, you know, here's how you can. Like have, what is the word that I'm looking for things that like come out of it that you want to hold on to? Artifacts, right? So you, you generate a container image or something and you want to hold onto that and it's just, you're literally just writing YAML and it does stuff and it's that, that easy.

[00:08:12] **Adam:** Yeah, I want to, I want to jump on here. So when you started talking about this, like it seems so scary from the outside, you're like, Oh, I don't know if I have the skill to do that. Right. My very, the, the, it's probably happened to me before this, but the first one that comes to mind for me, like earliest one that comes to mind for me is jQuery.

[00:08:29] **Ben:** Hmm.

[00:08:30] **Adam:** You know, people are talking about like, Oh, this is so amazing. I'm like, I don't know. I know how to do, you know, like document. get element by ID. I don't know if I can handle that stuff, but

[00:08:40] **Ben:** We at work, we've, there's always been teams that have set it up for me or not for me specifically, but for the teams and we just follow along and every now and then I would join a team at work and they would give me the documentation. And for whatever reason, there's always a line that's like, Oh, just go install something called JET. I don't know if this was specific to code chip, which is what we use. And then you have to run something called JET steps. And I almost feel like it's just a naming problem. It felt so not in alignment with what I was trying to do. Like, why am I installing something called JET to run tests? I don't know.

[00:09:16] **Ben:** It didn't make any sense. And then it just felt so tangential to. The actual writing of the application code. I, I just got very, befuddled by it.

[00:09:24] **Adam:** I've never heard of this. Is this like a Go thing or a Angular thing

[00:09:29] **Ben:** I, I, no, no, I think it's, I think it, well, let's say if I, if I Google for JetSteps, it brings up CloudBees.

[00:09:35] **Adam:** never? I mean, I've heard the name,

[00:09:36] **Ben:** yeah, yeah. But I, I, I think it maybe was very specific to, to CodeShip and the way they do their integrations. Anyway, sorry.

[00:09:45] **Adam:** That's the other thing that can, can often piss me off about like learning new stuff People pick name, you know, naming stuff is hard. I'll grant them that. But then if you pick a name for something that is like impossible to Google,

[00:09:57] **Tim:** Right.

[00:09:57] **Adam:** I said that very poorly, I'm going to repeat it. If you pick a name for something that's really impossible to Google, because like you pick the word cloud or, you know, like Hexbolt or something, right?

[00:10:06] **Adam:** Like if there's a billion years of prior art for that term and you name your, your software thing after it, it's like impossible to find it. And so

[00:10:15] **Tim:** Yeah. Name a jet jets. You're just going to get a stuff about Aaron Rodgers and his Achilles tendon playing for the football.

[00:10:23] **Adam:** I mean, so I think that I'm sort of the same boat as you. We have like people who are like CICD experts and they just build it for me. Right. And they're so good at it. They're so smart at it.

[00:10:35] **Tim:** And they talk about it at a very detailed level beyond what I'm comfortable with. And I'm like, okay, you deal with that. You do you over there. I'm going to worry about me over here. But I imagine if you took, took an afternoon to just kind of sit down and look at something simple, like he was saying, like, You know, GitHub actions.

[00:10:54] **Tim:** You'd figure it out.

[00:10:55] **Adam:** Yeah, seriously, just watch like two YouTube videos on it and you'll be like 80 percent there.

[00:11:00] **Tim:** Yeah.

[00:11:01] **Ben:** All right. Maybe that'll be my, my mission. I, you know, two years ago I had the mission to build a container and deploy it. Maybe I don't even have to do that. If I can just learn a little bit more about CICD, that'll scratch that itch.

[00:11:14] **Adam:** I love you, Ben, and I know you don't buy a Udemy course on GitHub actions. You can learn everything you need to know, from, for, yeah, from YouTube plus documentation.

[00:11:28] **Ben:** All right, I'm on it. I'm on it. That's it.

[00:11:30] **Adam:** Okay, cool. So that's going to do it for my triumph. Ben, what do you got going on?

## [00:11:34] Ben's Failure

[00:11:34] **Ben:** I'm going to go with a failure and I, my failure is that I have been feeling a little directionless, a little rudderless. I've been throwing that phrase around lately. I had gone into this year with this feeling, it's going to be not a, not a sabbatical, but it's, it's a low pressure year at work because we're taking it kind of into the final end zone there.

[00:11:56] **Ben:** And I was going to use that as an opportunity to spend more time just learning random stuff and trying to expand my horizons. And, what I am realizing is that that's actually really hard to do when it's. Purposeless, meaning I love to build stuff and I love to learn stuff, but I love to learn. In the journey of building something specific.

[00:12:20] **Ben:** This was always how I really did learning. I'd be doing stuff at work and I'd be bumping into a lot of weird edge cases and corner cases, and that's where I was forced to learn. I'm not really doing that for work. I'm just picking a topic and saying, Oh, I didn't know anything about that. I didn't know anything about Svelte or Tailwind or SQLite or Alpine JS.

[00:12:39] **Ben:** Let me go poke around in that. But the problem is I don't know when to stop poking. You know, you, you can.

[00:12:47] **Adam:** Don't, it's

[00:12:49] **Tim:** Oh

[00:12:50] **Adam:** not that kind of show, man.

[00:12:53] **Ben:** You know, and it's like, SQLite, for example, I've been poking around in SQLite just a little bit recently and I don't have a use case for it and it seems really fascinating, but like, I don't care. What I mean is like, I don't care to go to the next level of understanding SQLite

[00:13:10] **Tim:** mean, I mean, how much are you going to invest in this? If you may or not ever use it?

[00:13:13] **Ben:** right. And I was feeling that even when I was getting kind of deep into AlpineJS and I was trying to understand how to build. extensions and, and mess around with different kind of expression evaluators and whatnot. And so I just don't know what to do about it. I mean, I've actually been over the last like week or so kind of depressed. Because I wake up and I just feel a little overwhelmed because I don't know what I want to be doing with my free time. And I feel like I need to pick something to build. Like I need to build something real.

[00:13:47] **Ben:** Not, not, not necessarily something that makes money, but I feel like I have to go have a goal of, of learning for a specific reason.

[00:13:54] **Tim:** So, so Ben, I'm going to say, I'm usually against this. I know people right now, since remote working over COVID or people are doing this and I think it's unethical, but I think in your situation where you're basically have been told, look, we're sunsetting everything, company shutting down, I think you would, would be probably one of the few ethical examples I think would be okay to do.

[00:14:16] **Tim:** Go get a second job and do them both at the same time.

[00:14:18] **Ben:** Just pick up another, a subsequent paycheck.

[00:14:22] **Tim:** Yeah. Be, be double employed because then it will be real. Right. And then it'll mean, actually, it would mean something. And then it's like, whenever, you know, your, your original job is done, you just. Go, you know, just say, Hey, I'm done now. I'm going to be a hundred percent full time and be honest about it. I mean, they're not going to let you go at your current company because, Hey, I'm going to, I have a lot of free time because of this.

[00:14:42] **Tim:** So I'm taking a second job. They're like, okay. And then the other job is like, look, this one's dying and it's winding down. So I want to come work for you. And then that, that way you can, I can go full steam whenever I get hired. Yeah. Go get a second paycheck. That'll make it

[00:14:57] **Ben:** a, it's a very fascinating idea. I mean, I've heard people joke about things like this, mostly on the,

[00:15:02] **Tim:** I know

[00:15:02] **Ben:** skills, soft skills podcast.

[00:15:05] **Adam:** you say, you know, people who do it, like you physically have a friend that you've like high fived or something that does it. Wow,

[00:15:11] **Tim:** yeah. I know, I know

[00:15:12] **Adam:** shared testicles,

[00:15:14] **Tim:** Well, no,

[00:15:17] **Adam:** a plate of testicles. I want to be

[00:15:19] **Tim:** I play, yeah. You need some, you need some context on that there, Adam. So yeah, I mean, yeah, I know, I know people that are within my circle of friends that they're like, yeah, I'm working two jobs. Like, oh, okay.

[00:15:32] **Ben:** I don't know. I don't know if I have that kind of mentality, meaning I think it would just be hard to do a lot of the context switching and then I don't know, I'm getting old, but I still have

[00:15:43] **Tim:** doing that. You're doing that now. You're context switching to like, Playing around with technology and then going, well, I don't know how much you need to do that. You're, you're constantly context switching this time. You'll only have two to context switch between

[00:15:55] **Ben:** It's, it's an interesting, it's a fascinating idea. I will say that I will let it marinate.

[00:16:00] **Tim:** just, yeah,

[00:16:01] **Adam:** I got to say, I think Tim's right. I, you know, at first I was like, I don't know where this is going. I thought you were going to tell him to just like play Tetris all day or something. And. You know, like to, to, you know, like take a vacation, but get paid for it. Sort of, sort of deal. Right. But then you did the double employment thing.

[00:16:16] **Adam:** I'm like, Oh, that's kind of genius. Like if there was one time where it's not immoral, right? Like they, they just don't have duties for

[00:16:23] **Ben:** I mean, I have stuff I'm doing, you know, it's not

[00:16:26] **Tim:** right. But it doesn't take a hundred percent, right?

[00:16:29] **Adam:** if you're doing 10 hours a week of that and 20 to 30 of another employer,

[00:16:34] **Ben:** all right. All right. I, I, we, we have to stop this before I become liable for anything. All right. So that's, that, that's my failure. I've, I'm missing a little bit of a spark and I'm, and I'm trying to figure out how to get that spark. So we'll leave it at that before anyone gets in trouble. And, Carol's not here.

[00:16:52] **Ben:** So I'm going to kick it over to Tim to take us home. What do you got going on?

[00:16:55] **Tim:** so you stop that just in time. You do know when to stop poking.

[00:17:00] **Adam:** And for, for any lawyers that might be listening, everything we say on the show is for entertainment purposes. May or may not be true.

[00:17:07] **Tim:** Yeah. This is all satire. None of us are actually coders.

[00:17:10] **Ben:** actually all just various AI implementations here.

[00:17:13]

## [00:17:13] Tim's Triumph

[00:17:13] **Tim:** So I'm, I'm going for a triumph speaking of AI. so I've been working on my AI presentation that I'll be doing in a couple of days in Nashville. And, so as we talked about last time, last week, I'm having my AI agent call everyone who's coming to the show. Who's not on the, who's not on the do not call list.

[00:17:32] **Tim:** and so a lot of these phone numbers are actually like office phones

[00:17:37] **Ben:** sorry. Can we back up for just one second? Is, is there an API that you can hit to tell if someone's on the do not call list?

[00:17:44] **Tim:** It's the government that will never make it that easy. Yeah, so you have to sign up, you have to join, sign up for the, the, I think it was a FTC. You get an account there, you tell them your use, and then you can download the list. And it's, it's a CSV file that I had to parse. I was asking on CodeHelp, I was trying to get that huge, it's like 4 gigs worth of numbers.

[00:18:06] **Tim:** And it's all it is, it's an area code, comma, phone number, that's all it is, it's still 4 gigs. And, Anyway, I got it loaded in my local and hit it against the number and it took like half the numbers out, like half the people that were coming that was on the list. Yeah.and so, so I call all of them and this, like, it didn't get a lot of more like phone trees at a company and a lot of people, like 10 people would be coming.

[00:18:28] **Tim:** They all had the same phone number. So I know they're listing like business. I'm not going to get anybody. I got a lot of voicemail. Fortunately, this thing can leave, can tell if it's a, if it's a human or if it's a, it's a machine. So I left the voicemail and then, so we have other products. So, that we use for marketing.

[00:18:45] **Tim:** It's this one, the one we use is called ZoomInfo. You guys know what that is? It's, it's basically you can put information about a company or your current contacts that you have. So I loaded all the contacts that I could call and actually I loaded all of them and then put it in ZoomInfo and it comes back.

[00:19:04] **Tim:** It gives me other phone, other contacts information about the same person. So it gave me, there's a lot of them gave me their cell phones.

[00:19:10] **Adam:** so you're, you're using a data broker, you evil, evil person.

[00:19:13] **Tim:** yes, I am. Yeah. So use that, got there a lot of people's cell phones. So about half the people that I was allowed to call, I got their cell phones, got their cell phones, popped it in there.

[00:19:22] **Tim:** And those that got some answers on, but then again, it's like most people don't answer their cell phones either. So.

[00:19:29] **Adam:** For an unknown number. Yeah.

[00:19:30] **Tim:** Right, so you'll see an unknown number, you get a voicemail, so I left the voicemail. I actually got out of like 300 people that I called today, five of them actually answered and talked to my AI.

[00:19:46] **Tim:** I know I kind of say, you know, can we see you there at the presentation? Three of them, five answered, three said yes, two said no. And, none of them took advantage of trying to have a conversation with the AI, like asking it questions. So tomorrow I'm going to try what you suggested is just doing a text message.

[00:20:02] **Tim:** So I know the phone, the phones that are,cell

[00:20:04] **Adam:** that answered.

[00:20:05] **Tim:** right. I've got a, so I'm going to send the ones that I didn't already. A commitment from, I'm gonna send text messages and have a AI text chat with them and see if that goes better. 'cause a lot of people will answer their texts rather than their phone.

[00:20:18] **Adam:** Right.

[00:20:19] **Ben:** I have to say, and this is definitely a reflection of the times that we live in. So in the U S for our many global listeners. we're in the middle of a presidential election campaign season, and I'm getting just bombarded with, you know, oh, you haven't donated 5 this month, and oh, you know, we'd love to poll you about some information on, on various things.

[00:20:43] **Ben:** And as I get older, I'm actually more inclined to want to participate in giving my feedback about stuff just because I'm, I know more about the process and I'm more keen to, to be part of the process. I, I feel like we live in a time where I just can't trust anybody. I, every, every, News real about online stuff always comes back to, Oh, and it was a giant scam.

[00:21:10] **Ben:** And they just wanted you to say this certain thing or leave this certain message and they end up stealing all your information. And I, I don't know how you breach that, that, how do you get past that leap of faith that people have to have? It seems almost impossible.

[00:21:22] **Tim:** It's, it's funny you say that 'cause I noticed that one of the callers, I, I can watch this transcript as it's going by and I ask them, I, I, the AI kind of implied a yes or no answer. And the person said, maybe, and I thought that's smart because saying yes, sometimes on one of these kinds of calls where they're recording it, you say yes, they can use that and kind of reverse it to say you agreed to some sort of charge.

[00:21:47] **Tim:** And the recording of you saying yes is the proof. Even though it's not what you're trying to do. So I, I, yeah, I agree. There's that fear of, I don't want to say anything yes or no on this call because it might come back to bite me. Oh, and, I guess, yeah, that was just re recorded. So I sent you Ben, I've cloned my voice. And had to call you. You remember that last

[00:22:09] **Ben:** Yes. Yeah, of course.

[00:22:11] **Tim:** So that was scary. It took five minutes. It's not perfect, but if I spent more time, I can get it a lot better. But in five minutes, I came up with a facsimile of my voice to call you and ask you questions.

[00:22:21] **Tim:** And it was, I mean,

[00:22:22] **Ben:** it was really cool. I thought it was you at first, honestly.

[00:22:25] **Tim:** Yeah. Yeah. So that's scary because it's like, you go, the news is like these callers called out and with Joe Biden's voice to say, don't come to the election. You know, I thought, well, okay. You know, that took some effort. No, I could have done that. I didn't for legal reasons. I did not do that.

[00:22:41] **Tim:** It was not me.

[00:22:42] **Tim:** but yeah, I mean, that's a lot easier than you expect. Just, I recorded myself for five minutes talking and then yeah, I had a Tim Cunningham sounding AI.

[00:22:51] **Adam:** And this is different than the recording that you put in discord for us, right?

[00:22:55] **Tim:** Yeah. Yeah. Yeah. It's different. I had a call, Ben.

[00:22:59] **Ben:** as a fun aside, just for a second, it's cross promotional. One of the podcasts that I really enjoy, it's called the hard fork from the New York times and two episodes ago, one of the hosts, I'm terrible with names. I don't remember who they are, built like 15 AI buddies. And I get across all these different services that offer virtual friends and virtual girlfriends, or, you know, the girlfriend, boyfriend experience.

[00:23:24] **Ben:** they have conversations with these models as part of the podcast. So it's a lot of fun. It's both terrifying and very fun at the same time.

[00:23:35] **Tim:** I, I, I will say, even though that sounds like a fail, that I only got out of several hundred calls, five people actually interacted. I mean, the whole process costs me like three, $4. So if, if just one of those turns into a sale, it's worth it.

[00:23:50] **Ben:** totally. And you can make it better. I mean, I know that this was for a presentation, but in theory, you make this process better and better and you fine tune in and you probably drive up the conversion rates.

[00:24:01] **Tim:** Yeah. And, and to be fair, what I'm gonna be presenting is having this as an inbound call. So a person's calling to get customer service, so they want information. Their option, first option is to talk to ai and hopefully the AI can answer their questions. If not, hand them over to RealHuman. That's the pitch.

[00:24:18] **Tim:** So I don't see it as a failure, but yeah, I was really interested to see that, yeah, folks do not answer their phones. I mean, I don't, so I don't blame them.

[00:24:27] **Tim:** Man, can we talk about that for a second? Cause. You know, I'm 42 years old. I was born in 1982. and I feel it, it, it very much feels like a generational thing, although, Tim, you're saying you don't answer your phone and you're the oldest of us. Not 10 years older than you.

[00:24:41] **Adam:** not trying to rub it in. I'm just saying like, you know,

[00:24:43] **Tim:** No, you bring it up every show. That's fine.

[00:24:47] **Adam:** my coworkers. Paint it as a very like millennial and younger thing, right. And I'm kind of on the border between millennial and Gen X.and the, I, I feel a responsibility to answer the phone, because we have a company line that has like, you know, for Steve or sales, press one for Adam, press two, that sort of thing.

[00:25:09] **Adam:** And so. There, there's a very, I would say like maybe one in six of the unrecognized numbers that I get are actually like customers who need something, right? And so if I let all those go to voicemail, I think I would feel really bad about not answering the phone for them. And, and honestly, I have zero problems.

[00:25:26] **Adam:** Like, you know, I answered the phone and usually they're like, can I speak to so and so? And I'm like, what can I do for you? Or, you know, like, who are you calling from? Sort of thing. Like, don't, don't answer their question, like fire back another question. And if they're not one of my customers, it's like, not interested, click.

[00:25:40] **Ben:** Dang. Good on you. That's the thing. I'm terrified to answer the phone because I feel, I feel bad hanging up on people. So I'm, it's, I'm constantly waiting to get my in in the conversation so I can say no or no. Thank you. And, and, you know, they know that people are very uncomfortable.

[00:25:57] **Adam:** It's, you know, it's the same thing when like somebody comes to your door trying to sell you,

[00:26:00] **Ben:** Oh, the worst.

[00:26:01] **Adam:** Pest control stuff or whatever. Like, you know, they're, they are just trying to not let you get in a word edgewise so that like, they figure the longer they can make you stand there at your front door, the more likely they are to close

[00:26:12] **Ben:** how many Christmas wreaths have I bought?

[00:26:18] **Adam:** which is totally. And that's why, like, I can see right through it. It's transparent when they're like, you know, I just have to, I have to keep pushing this word salad across the phone line at you so that you won't hang up. Like, screw that. No, click.

[00:26:30] **Ben:** Good on you.

[00:26:31] **Tim:** Anyway, that's me. So we'll see how it goes. We'll let you know next week.

[00:26:36] **Ben:** Yeah. Very exciting. Good luck.

[00:26:39] **Adam:** Indeed. Good luck as well from me. Cool.

## [00:26:41] Laws of Software

[00:26:41] **Adam:** So let's talk about laws of software. whoop whoop! Pulling up behind you. Gonna write some tickets. Uh I pulled you over, sir?

[00:26:50] **Adam:** Because you're not following Atwood's law.

[00:26:52] **Tim:** You're, you're using spaces instead of tabs.

[00:26:55] **Adam:** That is a felony, by the

[00:26:57] **Tim:** Yeah, it

[00:26:58] **Adam:** we're not, that's not a misdemeanor. That one you just go straight to

[00:27:01] **Tim:** straight to jail. Do not collect 200.

[00:27:03] **Adam:** Indeed. Okay, cool. So, I mean, I already said it.

## [00:27:05] Atwood's Law

[00:27:05] **Adam:** We have to start with Atwood's law, I think. So, do you guys remember what Atwood's law is?

[00:27:10] **Ben:** Read it for us, read it for the listeners. I obviously know, but

[00:27:13] **Tim:** Hey, me too, obviously.

[00:27:14] **Adam:** How could you not?

[00:27:15] **Tim:** It's memorized. I have a tattoo of it.

[00:27:19] **Adam:** Any application that can be written in JavaScript will eventually be written in JavaScript. So it's called Atwood's Law after Jeff Atwood, famously co creator of Stack Overflow, and a couple of other things. in 2009 he wrote that. What do you guys think about that? Mm hmm. Mm

[00:27:37] **Ben:** I, so this is where I wonder if it's an echo chamber issue. Meaning if I were to take the pulse of Twitter, I would say, yes, everybody's writing everything in JavaScript. But then you find people who are deeply embedded in the NET community as an example, or, or the PHP larval community, or, or, you know, you just hear like, Oh, by the way, did you know that WordPress still powers, you know, 60 percent of all websites in the world?

[00:28:07] **Ben:** And I, I never know what to think. Clearly, clearly JavaScript is hugely popular and hugely influential and impactful.

[00:28:14] **Tim:** I mean, he said this in 2009 and I get why he said that back then. I

[00:28:20] **Adam:** You guys think it's not necessarily true, then?

[00:28:23] **Tim:** think, well, let's, let's broaden it. He says JavaScript and I guess, you know, this applies to everything JavaScript related. But really it's about pushing the processing down to the client computer rather than the server side,

[00:28:38] **Adam:** I disagree.

[00:28:39] **Tim:** to, no, you disagree. I'm not even done yet.

[00:28:42] **Adam:** I disagree,

[00:28:43] **Tim:** All right, fine.

[00:28:43] **Adam:** sir. So I think that the ethos of this law is, what it's really trying to say is that, the lingua franca of the web Of the internet is JavaScript, right? It runs in all of the browsers. And now we've got server side JavaScript. It can run literally everywhere. You can do like, program drones with it and little robots and RC cars.

[00:29:06] **Adam:** And, it, I mean, JavaScript, I'm not saying that JavaScript is like the only thing used, by SpaceX, but like the, the touchscreen computers in, in the, the, do they call it a cockpit? I don't know. And it, like that the astronauts are using in there. I believe that the touchscreen. Has some like JavaScript stuff, making it work.

[00:29:26] **Tim:** I think cockpits and canceled. I don't know what they call it now though. Yeah.

[00:29:32] **Adam:** the, I, but I think what it's getting at is, JavaScript is the lingua franca of the web and more and more, I mean, this was in 2009 and we have only

[00:29:42] **Ben:** exist yet, right? In 2009? Node's only like 10 years old.

[00:29:46] **Adam:** One of you guys look it up. Nah, I think it's more than 10 years old, but, so JavaScript's the web.

[00:29:50] **Adam:** I'm, that's the last time I'm going to say that, I promise. And everything is moving to online. Right. So, like just internet is becoming such a core part of daily life for more and more people every single day. Right. It's just become this like expectation. Like you, I'm sure that there are places where you can only pay your rent online.

[00:30:14] **Adam:** Right. Like, it's like, you can't bring a cash, an envelope full of cash down to the front office anymore. Right. like that's, that's kind of what I think he's getting at here is like, Everything is moving online and, and online is coalescing around JavaScript. Now I will say, I, I don't think that this, I don't think that he's implying that everything will stay in JavaScript, right?

[00:30:35] **Adam:** We've seen so many things that are written in JavaScript get ported out to Rust or Go or whatever, because there's, there's gains to be had there. And I don't think that that breaks Atwood's law.

[00:30:46] **Ben:** Well, on your, so by the way, Node apparently was released in 2009, which is the same year that this law came into being.if you were going to start a new project, sorry,

[00:30:57] **Adam:** was the exact date in 2009? Do you know?

[00:30:59] **Ben:** let's see. It was whatever Google said at the very top. May 27th.

[00:31:02] **Adam:** Okay. He coined the, the, the law, I guess, on August

[00:31:08] **Ben:** Coincidence?

[00:31:09] **Adam:** 14th. Maybe.

[00:31:10] **Ben:** if you were going to start a new project tomorrow, would you do full stack JavaScript?

[00:31:16] **Adam:** I mean, yeah, I, we're not even in, we're very, very early phase one of like porting our app away from CFML into SvelteKit, which is, you know, SvelteKit is just sort of like nice tooling on top of JavaScript. It

[00:31:30] **Ben:** I know I keep going back and forth on how I feel about it. I, I, to be clear, I love JavaScript and I love writing JavaScript. And I, and I know a lot of people think it's like a weird, funny language, but I think it's very usable and,

[00:31:44] **Adam:** a lot of idiosyncrasies,

[00:31:45] **Ben:** but like every

[00:31:46] **Adam:** a language that doesn't.

[00:31:47] **Ben:** exactly. I don't know. And I know this is so stupid.

[00:31:51] **Ben:** I just keep coming back to the idea of writing SQL and, and not having the CF query tag, and I just, I have a lot of trouble. I have a lot of trouble getting over that emotional hurdle. And I, and you know, maybe

[00:32:04] **Adam:** you still special ordering the same style of tennis shoes that they discontinued 20 years ago that you just fell in love

[00:32:10] **Ben:** my, Reebok pumps are still getting the job done. Okay.

[00:32:14] **Tim:** that's funny. That's why Sean, Sean Corfield, who is a patron, doesn't actually listen to the show unless someone chimes in on Discord, because when you say stuff like that, Ben, about the CF query, he wants to literally chuck his phone out the window.

[00:32:29] **Ben:** but it's not, you know, it's not everything. It's just a small set of things that feel very enjoyable in certain languages. And I, and I don't always know if it's worth giving that up. I mean, you know, there's so much that goes into a calculation like that, obviously, but you know, I'm only saying that it's just one of the considerations that I have.

[00:32:50] **Tim:** So I was going to ask you, I mean, you quickly shut me down there, Adam, but reading,

[00:32:54] **Adam:** end it. I just was, I needed to interject.

[00:32:56] **Tim:** but, but reading what he says here, that is the, what the site says, ultimately, this law concerns software distribution. The web is the best mechanism for distributing software. I agree a hundred percent with that. I don't know why that is JavaScript.

[00:33:12] **Adam:** Because JavaScript is the de facto language of the web because all browsers support it

[00:33:18] **Tim:** Nice way to use another term other than lingua franca. Yeah, I get that. Yeah. I can agree with that. I get that. Currently it is,

[00:33:28] **Adam:** Yeah. I mean, who knows?

[00:33:30] **Tim:** yeah, but 2009, that was a long time ago. So

[00:33:32] **Ben:** When was the iPhone released? And was I, 2007. Oh, okay. So the iPhone was already out.

[00:33:38] **Adam:** shall we move on?

[00:33:39] **Ben:** Sure. Let's move on.

[00:33:41] **Tim:** who wants to pick?

[00:33:41] **Adam:** You pick.

## [00:33:43] Cunningham's Law

[00:33:43] **Tim:** I'm going to pick one near and dear to my heart. Cunningham's law,

[00:33:46] **Adam:** I was hoping you would go there. Yeah.

[00:33:48] **Ben:** Read it for the listeners, please.

[00:33:50] **Tim:** Cunningham's law from Ward Cunningham. No relation. The best way to get the right answer on the internet is not to ask a question. It's to post the wrong answer. A hundred

[00:34:00] **Adam:** I, I, I can't disagree.

[00:34:03] **Tim:** I can't disagree.

[00:34:04] **Adam:** honestly, you know what? I think it works best in like a discussion setting, right? So I don't think that you can necessarily intentionally invoke that on say stack overflow, but I do think that it works like on Reddit.

[00:34:18] **Tim:** I think it works on this podcast. I can probably name like five, six times on the, in the run of the show where I've said something and then like, particularly early access, you know, then people who are really invested in the show, the early access listeners will immediately pounce on, Tim, you said in this episode, blah, blah, blah.

[00:34:38] **Tim:** But actually, I always wonder what the real answer was.

[00:34:46] **Adam:** All right. Mark it in your, in your calendars. Episode 180 was the first time that one of us pooped on a. On the listeners.

[00:34:53] **Tim:** No, that was, that was, that was them spilling out, spilling out information. It wasn't poop noise. It's like them just, you know, data dumping on me.

[00:35:01] **Adam:** I get it.

[00:35:02] **Tim:** They were pooping, but they were pooping on me.

[00:35:05] **Ben:** So here's, cut me some latitude here and some reasoning that I'm about to go into.

[00:35:09] **Tim:** We, we, we always do.

[00:35:10] **Adam:** Maybe. Yeah.

[00:35:14] **Ben:** I don't remember which one. It may have been a bit of optimism and they were talking about a, like an open, like a growth mindset and a closed mindset. And one of the things that they were talking about was how you frame something.

[00:35:31] **Ben:** Basically, they were talking, I think this all came up in the context of genius. And if you portray someone as a genius, Oh, you know, Adam is a musical genius. He's playing his guitar since he was three. It's amazing. If you frame something like that, and then you have people listen to Adam's music, they will be more likely to be very. Gracious towards it. Oh, it's, it's wonderful. You can tell Adam's a genius. clearly everyone is right about him. His music is wonderful. If you said Adam's not a genius, but he works his ass off and he practices guitar 12 hours a day and he's amazing. And you have to listen to his music. If you frame it that way and people listen to it, they'd be like, yeah, he's good, but like, I can hear all these technical problems and you can see where he's actually really struggling.

[00:36:16] **Tim:** And I, I pull it back to Conway's Law. cutting him. I

[00:36:23] **Ben:** I'm sorry, Cunningham's law. I think I clicked on the wrong one there. I wonder if there's like something like that going on, you know, if you, if you have something that's terrible or if you have something that's wrong, it's like people focus on all the things that are bad with it.

[00:36:38] **Ben:** Whereas if you write about something and it's marginally correct, like people just don't care. They'd be like, okay, yeah, it's fine. I don't care. And it's, it's just like how our brains are primed to. Pick things apart when we think that something, it's like, we want to almost like cut people down when they're already struggling.

[00:36:58] **Ben:** Does that make sense? I, it took me a while to get to the words there.

[00:37:03] **Tim:** don't see it as like cutting people down. It's like, I think it's much easier to spot check a flaw in someone's answer than it is to holistically answer a general question, right? So if you walk in a room, it's a giant white wall and there's a black spot in the middle and you ask people what they see, they don't see a giant white wall.

[00:37:25] **Tim:** They see a black spot. And that's how we are with, with deficiencies in, in, in an answer. 90 percent of that answer may have been correct. People will focus on the portion that they think is incorrect and they won't acknowledge the rest of it. And that's just, I think that's just human nature. I don't see that as a flaw.

[00:37:41] **Tim:** I think as long as you know Cunningham's Law, if you really want to, if you ask a question, you're not getting any answers, go log in on a different account and give a really wrong answer. You'll get, you'll get amazing results. Sorry.

[00:37:54] **Ben:** No.

[00:37:54] **Tim:** saying I've done that, but I've done that.

[00:37:56] **Ben:** I like your explanation much better than mine.

[00:38:00] **Tim:** I'm a lot more, you know, human positive view there. Yeah.

[00:38:06] **Ben:** I don't know. I just get very frustrated by people. We, we talked about, I think on a previous episode, we talked about, How bad sometimes people are about asking questions. It's like, Oh, you know, my code's broken. Why? like, well, are you getting error messages? You know, did you like, what version are you installed with?

[00:38:23] **Ben:** Kind of like a corollary to that. I find that people are often really bad about making suggestions. And, and it's kind of along the same lines of, of Cunningham's law, where you say like, Hey, my SQL is really great. And then someone will just immediately jump in with, have you tried Postgres? Or like, I like relational databases and like, yeah, have you tried NoSQL?

[00:38:43] **Ben:** You're like, why? Like, give me a reason. Tell me, tell me what it is that made you want to give me that suggestion other than you just wanted to like contradict the thing that I said.

[00:38:55] **Adam:** I'm better than you. I'm right and you're wrong

[00:38:58] **Ben:** I think suggesting is just a skill people.

[00:39:03] **Tim:** It's hard to people.

## [00:39:04] Parkinson's Law

[00:39:04] **Tim:** All right, Ben, you want to pick one?

[00:39:08] **Ben:** Yeah. Here's I, well, I have one that, I, I feel very strongly about it and I know other people feel very strongly in the other direction, which is Parkinson's law. Which says that work expands so as to fill the time available for its completion. Basically, people will use up all the time out allotted for a job. And this to me always feels like something that bosses and managers say, but I don't feel like I've ever heard an actual engineer say it.

[00:39:38] **Adam:** it's interesting that you say that because I forget. I think I read an article about this, but it was like a study was done about Making highways wider, right? So we have a main thoroughfare into Philadelphia. It's called the Schuylkill Expressway, Route 76. And it is, for the most part,

[00:39:56] **Ben:** The Skoogle Expressway? Skoogle?

[00:40:01] **Adam:** me on the spot, but I'm gonna try it anyway.

[00:40:02] **Adam:** S C H U, U Y L K Y L. That's my best guess.

[00:40:11] **Ben:** That sounds good. Sorry. I didn't mean

[00:40:13] **Adam:** it's, no, that's okay. I, I believe it's named after, like, some, regional Native American,

[00:40:18] **Ben:** a fun name. It's a fun name. That's what I wanted to.

[00:40:21] **Adam:** So, but it's, so it's the Schuylkill, right? And it's for the, for the most part, it is a two lane road coming out from the Western suburbs into Philadelphia.

[00:40:31] **Adam:** and it is always packed. You could be driving through at like 4 a. m. on Christmas morning or, you know, whatever. And, and it's going to be bumper to bumper traffic. Now, I mean. That's a little bit of a hyperbole, but you get the idea. and I believe that there have been studies done where, like, you take a road like that, and you make it wider, right?

[00:40:49] **Adam:** You you expand it to four lanes wide on each side. And, the the traffic is just, like, the the people are like, oh, okay, cool, we can it the traffic's not gonna be so bad anymore, so now we can drive in and out of the city more. And they just, you know, they fill the available lanes. Mm

[00:41:03] **Ben:** But so I, I mean, I love that as a painting a picture, but I think where the analogy falls down is the intent that, that people who are driving on the road, their intention is not to take longer. That's a, that's an unfortunate circumstance, but I think what Parkinson's law is saying is that whether consciously or unconsciously.

[00:41:28] **Ben:** If you say, Hey, you have a week to complete this task, people will intend to take a week to complete this task. And, and what I find, and maybe this is me just giving people the benefit of the doubt, I find people really just want to finish stuff quickly and move on to the next thing. I don't think people enjoy languishing on a task.

[00:41:50] **Ben:** I do think that people can get lost in the kind of gold plating weeds where they. Want to really optimize something that don't love solution a hundred percent. They'll kind of go back and forth and they'll tweak it and tweak it and tweak it, and it's like not quite there. And that certainly happens, but I think for the most part, people just want to do good work.

[00:42:11] **Tim:** Yeah.

[00:42:11] **Adam:** I think that we're going to suffer from a little bit of a sampling bias on this particular topic, because, you know, when I was thinking about who did I want to be on this podcast with me, I was, I was not thinking, okay, what slackers do I

[00:42:23] **Ben:** Right.

[00:42:23] **Adam:** that just want to burn time? Right. It was like ambitious people, people that want to get something done that have something to say.

[00:42:28] **Adam:** Right. And

[00:42:31] **Tim:** this. Let's say, let's just put one of us in a job that's sun setting their software and then you got a whole bunch of free time and you, you make up your mind that you're not going to waste that time because you have lots of hours available. You're not going to waste that time.

[00:42:45] **Tim:** You're going to learn some really good stuff and just see how much you actually get done in that situation.

[00:42:50] **Adam:** hypothetically,

[00:42:51] **Ben:** yeah, yeah, we'll, we'll workshop it, workshop it out. Well, let me, so again, sampling bias here is going to be an issue, but you have your intern,

[00:43:01] **Adam:** well, I've, I've since come around on the terminology co op. I think that.

[00:43:06] **Tim:** Go up. Yeah.

[00:43:07] **Adam:** Intern is just kind of, for, for lack of a better description, I feel like it's kind of become a pejorative, right? It's just like, it's a negative term. And I think that's part of why they call it a co op. And it's because a lot of reasons.

[00:43:18] **Adam:** Anyway, go ahead.

[00:43:19] **Ben:** but like, here's someone who's, you know, early on in their career. Do you, and then, you know, if you don't want to talk about this, it's totally understandable, but like, do you feel like he spends? Too much time on stuff, or would, do you ever feel like you want to say, Hey, hurry up or not hurry up, but like, don't, you know, don't get so lost in the weeds, like,

[00:43:40] **Adam:** it's interesting that you asked me this because I didn't even think about it until now, but I have never given him a deadline for anything. I just assign the task and you know, if he gets stuck, I, you know, I remind him every once in a while. It's like, okay, you know, I'm here. If you get stuck, let me know.

[00:43:55] **Adam:** Whatever, or if you, if you feel like you need a longer discussion, great, let me know. We'll, we'll schedule something. but it's just like, here's the job. Go do it and let me know when you're done.

[00:44:04] **Ben:** and it sounds, I mean, just circling back to the top of the show, I mean, it sounds like he's making good progress and, and, and is doing good stuff.

[00:44:12] **Adam:** He is,

[00:44:12] **Ben:** So I feel like this is my issue with Parkinson's law. To me, this always feels like it's, it's a top down. It's a top down judgment in an organizational chart where people say, we don't want to give people any leeway because all they're going to do is abuse it.

[00:44:26] **Ben:** And I, I just don't, I don't feel like that's backed up by anything.

[00:44:30] **Adam:** you know, I agree with you in, in concept. It makes me think about trying to run a very large company, right? So it is hard to build a company, you know, where your IT department is 150 people And they are all, you know, ninja, senior developer, rockstar people, right? Like you just have to assume that.

[00:44:55] **Ben:** I can't all be

[00:44:55] **Adam:** percentage, yeah, throwback,

[00:44:59] **Ben:** That's a deep cut people.

[00:45:01] **Adam:** yeah, you're just gonna have to go back and listen to the back catalog if you want to get that one. Um,the, but you're just gonna, at that, at that scale, you're just gonna have to assume that a certain percentage of people are gonna be low, comparatively low, productivity people, and they're, they're gonna play World of Warcraft at their desk or something like that, right?

[00:45:21] **Tim:** Like, I mean, if you read,

[00:45:23] **Adam:** it.

[00:45:24] **Tim:** if you read like the, the corollary here in the law, it's less about personal attitudes. It's more about bureaucracy growth, right? So if you're talking about a large organization and you're given six months to complete a thing that there's going to be like, okay, well, let's schedule a meeting, you know, at this point, this point, this point, there's going to be bureaucracy time fill that, that isn't directly involved with getting the project done.

[00:45:47] **Tim:** well, maybe it is, but I think that's really where they're going at is, is growth of bureaucracy is going to fill up that, that time that you have so that regardless of how hard everybody works, the bureaucracy itself is going to make it so that you're going to get it done maybe by the deadline and probably past it.

[00:46:06] **Adam:** Musk is such a

[00:46:08] **Tim:** I think there's a lot of reasons why he's the way he is. It

[00:46:12] **Adam:** do you think that he is employing some sort of psychological manipulation there? Like, all deadlines are unreasonably short to try and, you know, kind of do some self selection or something to circumvent.

[00:46:30] **Tim:** sounds like he's trying to go anti Parkinson's law. He's like, let's just, you're going to have to sleep on the floor of the factory until this is done, right? And it scares people so bad. They're like, Oh, we got to get this done. Yeah. I don't know. It doesn't seem like he ever actually gets anything done these days.

[00:46:44] **Adam:** Right. I get the impression that, like, working at one of his companies is like, You know, there's a meteor headed to earth and we have to save humanity. And in order to do that, we have to make electric cars or we have to get this rocket off the ground or get it to land safely. You know, like it's not, it's not that perilous, but that seems like the, the ethos.

[00:47:03] **Tim:** Yep.

[00:47:03] **Adam:** Cool. Are we ready to move on?

[00:47:04] **Ben:** Let's move on.

[00:47:06] **Adam:** right.

## [00:47:06] Goodhart's Law

[00:47:06] **Adam:** I wanted to throw out an honorable mention. I don't think we'll spend much time on this one, but Goodhart's Law, which is, when a measure becomes a target, it ceases to become, or it ceases to be a good measure. You know, we've talked about that on the show in the past.

[00:47:18] **Adam:** I don't think that there's a whole lot to say on the matter. Do you guys have anything?

[00:47:22] **Ben:** Well,

[00:47:22] **Tim:** me what you measure and I'll tell you your results.

[00:47:25] **Ben:** the, the one that always pops to my mind when this gets brought up is code coverage. And, and when a team wants to be like a hundred percent code coverage, that, that's one of those things I'm always like, what, what's the underlying problem that you're actually trying to solve? And this is not an anti testing conversation. This, this is like a,

[00:47:45] **Tim:** it has been, we know who's

[00:47:46] **Ben:** a, it's a pragmatic conversation and, and

[00:47:51] **Tim:** The opposite can't be zero code coverage.

[00:47:53] **Ben:** No, it can't, but I, I'm always very weary of a team that makes code coverage as a part of a continuous integration step where like code coverage can say, for example, never drop or like never go below a certain number. I'm like, I don't know.

[00:48:07] **Ben:** That seems so arbitrary.

[00:48:09] **Adam:** Yeah. I've honestly, I vehemently agree with you, Ben, in terms of like 100 percent code coverage is a useless goal to set. And, and I also, I don't know if this is exactly what you're saying, but that like the rule that code coverage can never go down is equally unhelpful. Because sometimes you're just going to be adding 20, 000 lines of code.

[00:48:30] **Adam:** And, you know, if you drop by 1%, then somebody is going to do something to just make the code coverage go up, right?

[00:48:36] **Ben:** Yeah, exactly. Exactly. And that's, and that is exactly the, the, the point of the law there is that it just becomes bad metric.

[00:48:45] **Adam:** Cool. So with Honorable mention set Aside, I have a, a real pick for my next

[00:48:49] **Ben:** Do

[00:48:49] **Tim:** oh, you're double

[00:48:50] **Adam:** I am. That's what, Hey, it's my podcast, buddy

[00:48:52] **Tim:** All right. Yeah. All right. We're just here. We're just here to serve you. I got it. Like we're good for Elon.

[00:48:57] **Adam:** well, you, you're welcome to sleep on the floor of your podcast studio, sir

[00:49:02] **Tim:** Yep. He paid me about as well too.

## [00:49:05] Hofstadter's Law

[00:49:05] **Adam:** so this is a Hofstadter's Law. I really like this one. It says, it always takes longer than you expect, even when you take into account hofstadter's law. Mm-Hmm.

[00:49:14] **Tim:** Yeah.

[00:49:15] **Ben:** percent, yes.

[00:49:16] **Tim:** thousand percent. Yeah.

[00:49:18] **Ben:** I have a zone of accuracy. I feel like if I have to estimate something and it can be done in a week, I feel like I'm pretty good at estimating. And then once you go past a week, it just precipitously becomes less accurate by, you know, have very random values.

[00:49:38] **Adam:** like exponentially. Your estimates get worse.

[00:49:40] **Ben:** it could be six weeks or it could be four months. I'm not exactly sure.

[00:49:45] **Adam:** Yeah.

[00:49:46] **Tim:** I don't think there's a whole lot to argue on that one. That just, you're like, cause I will do that. I have a developer who's extremely thorough, very, I mean, I gotta admit the guy's code works right. It always takes him so much longer than he thinks, right. He's like, I'm like, so where are you at? It's like, okay.

[00:50:04] **Tim:** So we're dealing with, you know, with the migrations right now. I'm like, okay, so how long do you think it's going to take? He's like, yeah, I'm pretty close on this. So probably another couple of days. And I, in my head, I go, it's going to take two weeks and sometimes I'm right. But sometimes it's like, it's a little more than two weeks. So it's like, yeah, it's, it's cause I'm taking into that law into account and I don't tell him that hopefully he doesn't listen to the show. but yeah, he's always, he's always more optimistic. It's not even, he's optimistic.

[00:50:33] **Tim:** He just really thinks that. He's going to solve this problem real fast and not realizes that he's going to run into three more right after he gets to that one. And it's like, I've worked with him for like seven, eight years now. It's like, it's always that way. So I'm like, okay, that's just the way it

[00:50:49] **Adam:** Is he earlier in his career or later in his

[00:50:51] **Tim:** No, he's older than me. So

[00:50:54] **Adam:** That's pretty old.

[00:50:55] **Tim:** it is. Thanks.

[00:50:58] **Ben:** So let me ask this then, given that laws like this exist and be, and given the fact that we are historically very not good at estimating, do you think that the responsibility of accuracy falls on both the managerial part of the team, as well as the engineering? And I think so, but I feel like too often the managers are all too happy to hear a number and believe that it is a hundred percent accurate.

[00:51:29] **Ben:** And then all too happy to throw that back in the engineer's face when it is not accurate.

[00:51:35] **Tim:** And it's like, you got to know who you're working with. Like, you know, if you don't, if you're, you're not a manager, if you don't understand that an engineer is always going to tell you a number that's optimistic. They're always going to give you the happy path number and you've got to, you're not being a manager if you don't understand that those are fictions.

[00:51:53] **Tim:** That's what you hope it is and it never works out that way. So yeah. So I tell, you know, like I said, he tells me into this week, I'm like, this is going to be three weeks from now. And then I tell, and then finance wants to know when we can start recognizing revenue on this and knowing that there's going to be a whole bunch of legal stuff that's going to, you know, it's six months when we reckon, you know, it'll get done.

[00:52:15] **Tim:** Four weeks from now and then we'll recognize revenue in six months and hopefully we hit that.

[00:52:20] **Ben:** Yeah, you're right.

## [00:52:22] Peter Principle

[00:52:22] **Tim:** I

[00:52:22] **Tim:** got one.

[00:52:23] Peter Principle.

[00:52:25] **Adam:** Oh yeah.

[00:52:26] **Tim:** yeah. So I, I've got a different view on this. So Peter Principle, that one is one that like, you know, the Peter Principle is people in a hierarchy tend to rise to a level of respective incompetence.

[00:52:39] **Adam:** That one needs some translation.

[00:52:41] **Tim:** Yeah. So what I used to think this meant was that you as an individual, you're in a company and you're doing good.

[00:52:49] **Tim:** You're doing good. You get a promotion, right? You're doing good. You're there for a couple of years, like doing good, doing good. You're going to get a promotion. And then eventually it gets to the point where the job's too big for you and you're just going to fail. Right. but really I listened to, was it Freakonomics?

[00:53:06] **Tim:** It was a, it was an NPR thing where they talked about the Peter Principle. That is not really how I think they meant it to be. That's a bit of a harsh interpretation that, that, cause no one wants to be considered incompetent. And, and I had like a very, very high up level person kind of, I was struggling at some point and he goes, have you heard the Peter principle?

[00:53:27] **Tim:** And I'm like, you son of a,

[00:53:29] **Ben:** That's awful.

[00:53:31] **Tim:** yeah, but it's not the level of incompetence of you as a person. So the, the show that I was listening to the podcast I was listening to was basically saying, so you have a salesperson, like it's extremely highly successful salesperson and you want to promote them, right? You want to reward them.

[00:53:47] **Tim:** So you make them a manager. Of other salespeople, but it turns out that the skills that made them an extremely high earner, doesn't make them a good coach of other, of other salespeople. And so they have studied after study after study that shows that a company who like promotes their top earner actually takes a cut in profitability.

[00:54:12] **Tim:** They, I think they said like 13%, some number that was significant. because they, That person struggles. It's not his incompetence. He is very competent at what he does, he or she. Organization is incompetent because they don't know how to reward people that are doing their job well in a way that rewards them, makes them feel like they're promoting and growing that also works with their skillset.

[00:54:37] **Tim:** And I think that happens a lot with, with engineers, the engineers who are really, really good at their job, really, you know, they're, they're good at solving problems, they're good at technical things, they're good at understanding documentation. And so, and then you make them a manager of other developers and then all of a sudden they're floundering, right?

[00:54:54] **Tim:** And the whole team is suffering. So that's what I see as the Peter Principle, that is a failure of an organization to realize how do you reward people who are doing well in a way that sets them up for success rather than failure.

[00:55:06] **Adam:** I love that. I love that you were able to crystallize that so cleanly, and I, I really appreciate that. So, for so long, I've had two misunderstandings about the Peter Principle. First one's easy. I always thought it was like named after a particular bad manager type person, right? Like, some guy named Peter, who is so bad, he got the Peter Principle named after him.

[00:55:27] **Adam:** which, maybe it was true, but it was also coined by Lawrence Peter in 1969, so, I imagine it was just, it took his name.

[00:55:35] **Tim:** Took his name.

[00:55:36] **Adam:** but the other thing was, I always thought of it as like, you will tend to get promoted, even if you're incompetent. You'll get, you'll tend to get promoted, kind of like a teacher who just like passes you so they don't have to see you again next year, right?

[00:55:48] **Adam:** You'll tend to get promoted until the point where you're incompetence

[00:55:53] **Tim:** You can't fake it anymore.

[00:55:54] **Adam:** but until the point where your incompetence would actually be a danger to the company, right? Like just, that is where we have to stop promoting you.

[00:56:03] **Tim:** And that's an awful outlook, right?

[00:56:05] **Adam:** Absolutely. So I think that your, your description actually totally changes my, my, the way I think about this one.

[00:56:12] **Tim:** And that was just, that was just a few weeks ago. I heard that on the radio. I'm like, that makes so much more sense because that is so true. Like they want to reward you. And so they were talking about how they actually try to reward people as they give financial incentives and you can be an individual contributor.

[00:56:28] **Tim:** Who is like, they give, you know, they come up with some fancy title, but like a senior something architect, you know, you come up with these titles that recognize them as a person that says they are extremely good at what they do. You should recognize what you do. They get financially compensated for it.

[00:56:43] **Tim:** They get, you know, rewards, incentives for it as well, but they don't have any reports. They're an individual contributor who's of high value to the company and it's recognized. And I'm like, that is, that all my life is what I was like, You keep taking these really good programmers and putting them into managing jobs and they suck at it.

[00:57:02] **Tim:** They're not people persons. They don't know how to manage conflict and they don't know how to soothe egos. And so you get some guy who's an engineer who just, you know, he's fantastic, but you know, he thinks he's the cock of the walk and you know, anyone who challenges him, he steps on. Now that is not good team building, right?

[00:57:20] **Tim:** Let him be an individual contributor. Let him keep doing what he's doing, but find some way to make him, make him or her feel better. Respected and advanced in the organization with it. That doesn't hurt the organization.

[00:57:33] **Ben:** Well said.

[00:57:35] **Adam:** Indeed. Love it. Well, should we call it there? We've covered a bunch of it. So let me throw this out to the listeners and we're, we're going to wrap it there. it's been about an hour of us recording. so that's a good place to stop. If you like this, there's a lot more of these laws, so let us know, right?

[00:57:51] **Adam:** Hit us up in our discord or, or pretty much just our discord. We don't really do the whole social media thing all that well. But yeah, you can go to our discord, it's workingcode.dev/discord. It's free and open to join, and we'd love to hear from you. If you want to hear more of this stuff, then let us know.

[00:58:07] **Adam:** okay, cool.

## [00:58:08] Patreon

[00:58:08] **Adam:** So this episode of Working Code is brought to you by, Knowing When To Stop Poking it is that kind of show apparently and listeners like you, if you are enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:58:24] **Adam:** Our patrons cover our recording. Thanks for listening. Editing and transcription costs, and we could not do this every week without them. Special thanks to our top patrons, Monte and Giancarlo. If you don't happen to be on the Discord, then you won't know, because that's the only place that I've shared this information so far, I believe, that I have the stickers.

[00:58:42] **Tim:** What's that? Ooh,

[00:58:43] **Adam:** right here in my

[00:58:44] **Tim:** they, they, they sound amazing.

[00:58:47] **Adam:** definitely not just a Ziploc bag filled with rocks. It's actually a bag of stickers. I have the stickers. I will be sending them out very soon. I am very busy right now. This is like the busy season for my company. So I'm, it might take me another week or two to get them all in the mail.

[00:59:03] **Adam:** Or three or four or five. we'll see, but, the process is moving. I promise.

## [00:59:08] Thanks for Listening!

[00:59:08] **Adam:** Anyway, we are going to go do our after show. I don't think we thought too far enough ahead to put together a list of what we're going to talk about on the after show. So that's the kind of professionalism that we bring to podcasting that all these other podcasts are trying to aspire to. We're gonna figure it out, and I'm sure it'll be amazing. if you would like to listen to that after show and all of the other amazing after shows, then you're gonna have to go to patreon.com/workingcodepod, become a paton of the show for as little as $4 a month. actually it can go even lower than that if you do a yearly, subscription.

[00:59:39] **Adam:** and, and help us out.

[00:59:41] **Tim:** That's in a Starbucks. Come on.

[00:59:42] **Adam:** That's right, one a month. anyway, so, like I said before, join our discord, workingcode.dev/discord. We'd love to have your feedback on anything. the laws that we discussed tonight, whether or not you want to hear more of these, how old Tim is, it's all fair game. I'm going to get like a HR complaint

[01:00:02] **Tim:** Yeah. Yeah. Yeah. Ageist, you're ageist.

[01:00:05] **Adam:** All right. Before I get myself into any more trouble, that's it for us this week. We'll catch you next week. And until then,

[01:00:10] **Tim:** Remember, it's not the Peter principle talking here. Your heart matters.
