---
title: "245: Browser Passwords? You're Doing It Wrong"
description: "What starts as a gentle roasting turns into a deep dive on password managers, shared family vaults, and why your retirement account deserves better than Chrome's autofill."
date: 2026-01-22
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/245-browser-passwords-youre-doing-it-wrong/id1544142288?i=1000746194527"></iframe>

Tim stores his passwords in the browser. There, we said it. But before you grab your pitchforks, it turns out he's got an ancient password vault program backing him up—so he's not _completely_ feral. Still, the hosts can't resist a good-natured intervention. What starts as a gentle roasting turns into a deep dive on password managers, shared family vaults, and why your retirement account deserves better than Chrome's autofill. Carol reveals her galaxy-brain solution to her husband constantly forgetting his master password: she just signed him into her account. He still doesn't know he doesn't have his own 1Password.

### Links

- [Claude Code](https://github.com/anthropics/claude-code) - Anthropic's CLI for coding with Claude
- [Ralph Wiggum Plugin](https://github.com/anthropics/claude-code/blob/main/plugins/ralph-wiggum/README.md) - Official Claude Code plugin for autonomous loops
- [Everything is a Ralph Loop](https://ghuntley.com/loop/) - Geoffrey Huntley's deep dive on the technique

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Thursday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/245-browser-passwords-youre-doing-it-wrong.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Cold Open

[00:00:00] **Carol:** My husband. is the best, the best husband in the world. I got so tired of telling him what his 1Password password was, that I signed him out and signed him into mine, and now I just put everything in my private vault and he does too.

[00:00:12] **Carol:** And he doesn't realize that he doesn't have his own 1Password yet.

## [00:00:37] Intro

[00:00:37] **Adam:** okay, here we go. It is show number 245 and on today's show we're gonna be telling you that if you're storing your passwords in your browser, then you're doing it wrong. Tim.

[00:00:47] **Tim:** Hey.

[00:00:47] **Carol:** Timmy, Timmy.

[00:00:48] **Adam:** it came up a couple of weeks ago. We said we'd come back to it and I think we are getting back to it. I think that's the plan, but first as usual, we'll start with our triumphs and fails. And, Carol, it looks like we're coming to you first. Welcome back. Wait, were you off?

## [00:01:02] Carol's Triumph

[00:01:02] **Carol:** Yeah, I took the week off, but you all took the week off with me. Yeah.

[00:01:05] **Adam:** we were gonna record last week and personal stuff came up for a couple of us, so we, we just took the week off. So welcome back to all of us.

[00:01:12] **Carol:** Yay. Cool. I'm gonna kick us off with a triumph. I took the entire week off of work and I'm happy to report nothing died or crashed or failed. And I came back to a lot of junk emails, but not big problem emails and several people just wanting to catch me up on what they accomplished. And it was so nice to just detach and come back and see that things keep moving, progress kept happening and people are owning like their little sphere of what they're doing.

[00:01:45] **Carol:** So it's been a, a nice little change from, you know, previous weeks off and the chaos that ensues after.

[00:01:53] **Ben:** That's

[00:01:54] **Adam:** Congrats,

[00:01:55] **Carol:** Yeah. Thank you. I guess it's more of a, a team like win, not a personal one, but I'm claiming it.

[00:02:00] **Adam:** you're representing your team.

[00:02:02] **Carol:** And I am

[00:02:03] **Ben:** you took the week off to take care of your dog, I assume. Is that what happened?

[00:02:06] **Carol:** family time. Yeah. So visit with my sister. Yeah. Yeah. We don't, it, it needs lots of attention. I can't work and actually play with her. So. Yeah, we took her swimming. She did go swimming for the first time and she seems to like it for the most part. She turned into a little rat, but, she enjoyed it. So I think we'll keep swimming for the rest of the seat.

[00:02:27] **Carol:** Well, it's not even swim season yet. Our pool's hot. It's always swim season.

[00:02:31] **Tim:** Nice.

[00:02:32] **Ben:** Nice.

[00:02:33] **Carol:** me. What about you, Tim?

## [00:02:34] Tim's Triumph

[00:02:34] **Tim:** I'm going for a triumph as well, so it's a small one. So we're looking to improve our retrospectives, so every team in the company. They get slightly different processes, but one thing we're trying to add now is just adding a retrospective to say, what went well? What, do we need to improve?

[00:02:51] **Tim:** we don't wanna just create a whole bunch of ceremony for ceremony's sake, but we do want to try to improve some outcomes with not having a bunch of rework and things like that and measuring that each, period of, of, deployment that we're doing, which is either two weeks, every two weeks or every month.

[00:03:06] **Tim:** So just gathering information on that. But I mean, it's good 'cause I think we're, we're seeing improvements just kind of in throughput now. now that we're increasing our throughput, we wanna increase our quality, so.

[00:03:17] **Adam:** So when you say. Are you doing like project-based retros or time-based, like we do 'em every two weeks or whatever.

[00:03:24] **Tim:** we do 'em during our sprint, right? So at the end of our sprint, so after the sprint's over, you go through and say, okay, we, we thought we were gonna be able to do, you know, a hundred things, and we got 85 of 'em done and 10 of them had some rework. Right? And just measuring that, with the goal through getting sort of a baseline for improvement.

[00:03:44] **Adam:** Gotcha. It's a little more quote unquote agile

[00:03:47] **Tim:** Yeah, I mean, the, Agile's a weird word. Nobody really knows what it means. It's like pornography. I know it when I see it, but I've never, I don't think I've ever seen it, honestly. I think everyone just does it slightly different. So

[00:04:00] **Adam:** Are you talking about agile or porn?

[00:04:02] **Tim:** I about the same, honestly. so yeah. So yeah, we're just trying to get it prude.

[00:04:07] **Tim:** Now I derailed myself with that comment.

[00:04:11] **Ben:** When we were at, at Envision, we used an application, it was a website called Retro. And the way it worked is, it was set into this specifically for retrospectives and there'd be like a 10 minute brainstorming, period where retro worked. It was like a Trello board and everyone was adding cards.

[00:04:30] **Ben:** But during this brainstorming period, all the cards were fuzzed, so you couldn't see what anyone else was typing. You could just see that they were putting cards on the board, and then that time period would pass and all the cards would become visible. And then there was like a two minute voting period where you got a certain amount of votes and everyone said I wanna talk about this, talk about that.

[00:04:48] **Ben:** oh, of the 10 cards we put up, three of them have enough votes. These are gonna be the things that we talk about. And, it was mostly just A fest. I mean, it was basically like all we did was focus on all the stuff that didn't go right. And oftentimes that was because of all the cultural social problems at work and nothing really ever got fixed.

[00:05:06] **Ben:** But I'll tell you, I loved it. And, I would highly recommend,

[00:05:10] **Adam:** you're a fan of the ritual.

[00:05:12] **Ben:** I, I'm a, I'm a fan of the comradery of the acknowledging that things don't work as well as we'd like them to. And I feel like that, I think you can go one of two ways. You can, you can argue that people who complain get worse over time because it's like they just learn to hate.

[00:05:31] **Ben:** But I feel like if you can complain as a team, it actually has a sort of positive morale building where you're like, oh, we're all in this garbage together. we can do it. You know? And it becomes kind of a, a fight against the machine kind of mentality, I think. So it's, it's probably a fine line to walk.

[00:05:48] **Tim:** Yeah. we're just stepping our foot into it, just kind of saying it. How it, you know, it feels, if it, if it seems like it's helping, we'll continue doing it. If it doesn't, we'll we'll kill it. So quick failures and easy wins.

[00:06:00] **Carol:** Well, one thing I like about ours is our scrum master does a really good job of opening actual like risk and impediment stories for the following sprint. So like we closed out our sprint. One of my retro items was, guys, I have a problem, my laptop is blue screening. Seriously. So, a risk and impediment gets open that's Hey, we need to track this.

[00:06:22] **Carol:** We need to make sure like replacements get sent out. who's following up on this? So it doesn't feel so much just like talking, it feels like actions being taken. And then in standup I actually get to see oh, okay, this block thing is now being resolved or this impediment, we're working through it.

[00:06:37] **Carol:** Or even just the scrum master going, I don't have an answer yet, but I'm still working. I'm still trying to get things right. And the fact that we put visibility on it makes me wanna participate so much more in the retro and actually be honest. 'cause I feel like it's gonna make change.

[00:06:52] **Tim:** Gotcha. Cool. Anyway, that's me. How about you, Adam?

## [00:06:56] Adam's Triumph

[00:06:56] **Adam:** so I've talked in the past about, my dabblings with ai, and man I've gotten kind of AI pilled on stuff. you know, just not, I'm not a full on AI tech, bro. Hype it all, everything, it's gonna change the world type thing, but. If you hold it right, you know, if you wield the sword correctly, it can be, pretty powerful.

[00:07:16] **Adam:** You know, I think I talked briefly about how, I was using Cursor and it was working well for me. I had played a little bit with, a model from Anthropic called Opus, and that, that model was good. And, you know, not, not, too many miles ahead of the, the model that's built into Cursor called Composer one, but better.

[00:07:36] **Adam:** but it like absolutely chewed through like quota, right? You know, the getting this, getting the same work done in Composer that I would do in Opus, Opus uses easily two to three times as many tokens. So you're, you're chewing through your spend that much faster. anyway, so, you know, I, I watch a lot of tech, YouTube stuff and, and, consuming stuff and, Been wanting to try, have you guys heard of Ralph?

[00:08:02] **Carol:** No, I

[00:08:02] **Adam:** getting a lot of shaking heads. So it, it's,

[00:08:05] **Tim:** I've Ralph before, but.

[00:08:07] **Adam:** it's a, so it's actually a reference to Ralph Wiggum from The Simpsons because he is like a super idealistic and optimistic but naive. and so even if he does something wrong, he just keeps trying and, you know, tries to learn a little bit from what he did and just, just keep going.

[00:08:22] **Adam:** so that's, that's why, that's why it's named Ralph. But basically it's just a concept of breaking down, a, a big chunk of work that needs to be done into small tasks that are discreet, right? They can be completed individually, and then it like runs it in a loop so that you're kind of resetting context.

[00:08:40] **Adam:** The context window for whatever LLM you're using. and, and you like set it up in a way where it does a bunch of work, commits it to get, you know, write some notes for the people or the LLM to review in the next iteration of the loop. and, and then, checks the PRD, the project requirements, product requirements document, whatever.

[00:09:00] **Adam:** and if all the requirements are met, then print complete. and, and then it ends. And the, the, the bash script controlling the LLM checks to see if it printed complete, if it does exit, if it doesn't, then like loop again. Right? And you can have a max number of iterations. That's the, the, the basic, like the, the literal two minute description of, what Ralph Loops are.

[00:09:19] **Adam:** But, you know, it's something I've been wanting to play with, but because of the cost of Opus, it's just been not something that's. Been available to me. So they have this, I dunno if you've seen Anthropic has some new subscription tiers where you can do like a hundred dollars a month or $200 a month, and get like a, a huge amount of quota.

[00:09:38] **Adam:** and I talked to my CEO and i's look, you know, can I take a couple of months? Basically we're, we're talking about a couple hundred bucks to run an experiment, say like, is this something that we can use to be extremely productive? and, and can I use it to use this as an opportunity to kind of like, get my sea legs under me, right?

[00:09:56] **Adam:** build up the guardrails that are gonna keep us from making bad mistakes and, that sort of thing. And, and it's been going really well. you know, I'm not quite one of those people that's running, you know, I'm not running any Ralph loops right now. I'm, but you know, you, you talk to people sometimes and they're like, I got three things going right now.

[00:10:10] **Adam:** Yeah, go ahead.

[00:10:11] **Ben:** just a point of clarity is, is the Ralph Loop a technique or you're saying that's an actual product?

[00:10:17] **Adam:** I would classify it as a technique. I, so there's, if I'm, if I remember correctly, anthropic released like a feature in the Claude code CLI that, is inspired by this technique and it's basically, think of it as like plan mode, right? You, you, you build a plan for what you're gonna do.

[00:10:36] **Adam:** And then from what I understand, the Claude Code plugin that does Ralph whatever, you know, does a chunk of the plan and then it like resets the context window and does another chunk and resets or, or something like that. Or compacts maybe instead. and, it's not quite the same thing. 'cause this is, you know, you're, you're running what, what this is, is it's like a.

[00:10:56] **Adam:** Bash script. I'll send you guys some links and we can put some stuff in the show notes. But basically it's a, you write a bash script or whatever your local scripting, language of choice is, and you just, you're literally calling Claude in a headless, right? Here's my prompt. Go do the thing. And when it exits, then you look at the output.

[00:11:14] **Adam:** If it printed, I'm done. Then you exit the loop. If it didn't, then you, then you loop around. You just run the same prompt over and over. But the prompt is directing Claude to look at a specific file, which has all the requirements and the status of each requirement.

[00:11:29] **Ben:** Ah, gotcha. Okay.

[00:11:32] **Adam:** and you're, you're giving it a lot of agents that you're saying, okay, you decide what's the next most important topic in this document.

[00:11:39] **Adam:** And, and you work on just that one feature and you commit it when you're done and take notes here and do this and do that, is really interesting. And I can see a lot of value in it. I can see like the potential and really I think what unlocks this is.in my opinion, you know, this new, the Opus model and, and to some extent the new sonnet model too, they've gotten a lot smarter, right?

[00:12:01] **Adam:** I think the previous generation of models were really good at like, okay, here's the, the file that I have open and here's the change that I want you to make, right? refactor this jQuery thing to be this other thing or whatever, right? and they were pretty capable at that. Now with these newer generation models, you can really be like, okay, here's three different files that are related, and I want you to do this thing that, that affects all three of them in different ways.

[00:12:23] **Adam:** And maybe it affects some other files that you can find by, you know, you don't say this part, but you say, you know, it, it affects other files that it can find by TypeScript references, import statements, whatever, functions being called. And it, it kind of spiders out. It's like, okay, well what do I need to do to fix this to, to complete this task?

[00:12:40] **Adam:** And it's pretty impressive what it can get done.

[00:12:44] **Ben:** Very

[00:12:44] **Tim:** So, you know, I'm, I'm, starting to get Claude Pilled, I think,We bought co with Enterprise for the whole organization after messing with it for about six months. So

[00:12:53] **Adam:** What does that cost?

[00:12:54] **Tim:** I don't remember.

[00:12:55] **Adam:** Like seven arms and 14 legs

[00:12:58] **Tim:** no, it's, it's a little, it's a little under a hundred per, per developer.

[00:13:03] **Adam:** Okay.

[00:13:04] **Tim:** So it's not terrible

[00:13:06] **Adam:** I wonder if that gives you the same, like quota as me paying a hundred.

[00:13:11] **Tim:** it's a pool, right? So it's an enterprise pool. So if you got one super heavy user and one light user, maybe they balance each other out. But, yeah, eventually at some point you hit your quota and like, yep. Sorry. Done.

[00:13:23] **Adam:** Hmm.

[00:13:24] **Ben:** It's time to

[00:13:24] **Adam:** Yeah, that's, that's something that's been really interesting about it. So the, when you're this max subscription, that's MAX, not like MACS, it's per hour quota, basically. You have a per hour quota and you have a per week quota. And it's like, you know, so you can, you can really hammer it and you might run out in the current hour.

[00:13:44] **Adam:** Now I say that I haven't personally been able to get it over eight or 10% in a, in an hour. but I'm, like I said, I'm still kind of moving slowly into this, still trying to figure out how to be super productive. But, so I, I don't know who is doing what to need the $200 a month subscription, but that's bananas to me. So anyway, that's enough outta me. I gotta shut my mouth. So, Ben, what do you got going on?

## [00:14:09] Ben's Triumph

[00:14:09] **Ben:** I'm gonna go with a triumph, but I'm gonna maybe even call it a fum now, just in the, in the shadow of Adam's AI

[00:14:16] **Tim:** Don't compare yourself to others buddy. Never. Never compare.

[00:14:19] **Ben:** I never compare it as the, robs me of my joy. but so we kicked off 2026 the current year with me talking about all the stuff I wanted to try and learn this year, or at least the direction I wanted to go.

[00:14:30] **Ben:** And the triumph part of that is that I've actually been kind of committing to that journey. I spent some time going through the web platform features that have become classified as widely released or widely available as per Google's baseline project. And that's essentially any web feature that's been available for 30 months in all of the major browsers.

[00:14:51] **Ben:** I like, constraints. I thrive in constraints. So this feels like a nice constraint to be able to work with. oddly enough, I tried to ask chat, GBT, what are the. web features that have became, become classified as widely available in the last two years. And it could not do that at all. Even it was like searching all these kinds of pages and like cross-referencing blog posts and it came up with a list that had like 10 items on it, which I, I know is not true.

[00:15:16] **Ben:** and just from Googling now for young folks, Google is a website that allows you to search the web.that pointed me to the W three C actually maintains, or the community maintains this developer experience repository that lists out. Release notes for all of the newly available and widely available features for the web platform going back like four years.

[00:15:39] **Ben:** So I was like, jackpot, that's exactly what I want. So I went through that and I picked out all the things that were grabbing my attention that felt like either complete unknowns, like I've never used container queries, I've never used the dialogue element, things to that effect. And then things that were just gaps in my understanding.

[00:15:56] **Ben:** I'm a little bit behind on all of the array methods, for example, in JavaScript. They've added a bunch over the last couple years, and I'm, I just haven't built up the muscle memory. So I feel good, like I've actually been trying to go through that list and either read and write about it or just read if I don't feel like there's something I need to actually write about.

[00:16:12] **Ben:** So that's the triumph part. The, the, the failure esque part of this is that, you know, Adam's clearly doing better with the AI stuff, and AI is one of the things that I wanna try to learn. And I just, I get so swirled down. Like I don't have A-D-H-D-I, I think I just go down little rabbit holes, as I'm in my learning process.

[00:16:31] **Ben:** So I wanna learn AI agent coding, I'm probably gonna use Claude Code, but historically Claude Code has not had any kind of containerization. So I started to do some Googling about, can't you run Claude Code in a Docker container? And Claude Code says, well, here we give you, dev containers. Now dev containers is like a Microsoft thing.

[00:16:52] **Ben:** It integrates really well with Visual Studio Code. But of course I don't have Visual Studio Code 'cause I'm still Sublime pilled. so I go to ChatGPT and I'm like, what's difference between a dev container, a Docker container? And that's like another hour of time that I lost. but it turns out that now Docker has this docker sandboxes concept.

[00:17:08] **Ben:** It's, it's just like a experimental feature where they can basically spin up a micro VM and then run. Claude inside the micro VM and like transparently mount volumes for your projects into the vm. So it's like really? It's basically like a Docker container for Claude, so I wanna do that. So I started watch a YouTube video about that and then in the YouTube video they mentioned running it on this code kata called the Gilded Rose.

[00:17:30] **Ben:** And I was like, well I've never heard that Code Kata. So I started googling for that code kata and there's a whole repository of all these languages, but none of them are cold fusion. So I was like, oh, wouldn't it be fun to write that code Kata in cold fusion? So like that's where I am this morning. So that was like, so like

[00:17:45] **Adam:** just like nerd snipe yourself over and over and over again.

[00:17:48] **Tim:** yeah.

[00:17:49] **Ben:** I'm gonna hit that bottom of that recursive loop and then I'm gonna start to wind back up and eventually I'm gonna get to the Dockerized running of Claude Code and I'll be where Adam is.

[00:17:58] **Ben:** But you know, several months behind.

[00:18:01] **Adam:** You. You know how I can tell you don't have a DHD. It's because you can remember all the steps that it took you to get there.

[00:18:08] **Ben:** So, so I'm excited that I'm moving forward. I'm proud of myself for, I feel like committing to this learning journey, but I'm also knowing that I'm probably allowing myself to get distracted. But I also do feel like historically that's how my learning process has worked.you know, like a lot of, oh, that's weird kind of things.

[00:18:29] **Ben:** And then you go down this little side quest. So I'm trying not to feel too bad about it, although I probably should just sit down and really just do the AI thing so that I can make more progress on it. But you know, EMPH Triumph, EMPH, that's how I say it. Yeah, that's me.

[00:18:46] **Adam:** Trial year.

[00:18:49] **Tim:** You,

[00:18:50] **Ben:** that's what I got.

[00:18:51] **Tim:** you're not distracted. You're just on a side quest.

[00:18:53] **Ben:** Yeah, exactly.

[00:18:55] **Adam:** But your side quests has side quests, have side quests.

[00:18:57] **Tim:** Mm-hmm.

[00:18:58] **Ben:** And eventually there's just a giant turtle holding it all.

[00:19:01] **Tim:** Yep.

[00:19:02] **Carol:** A giant What? Holding it all together,

[00:19:05] **Ben:** there's a giant turtle holding it up.

[00:19:07] **Tim:** Turtles all the way down.

[00:19:08] **Adam:** turtles all the way down. Yeah.

[00:19:10] **Ben:** the notion of turtles all the way down. Yeah, exactly. Comes from some, I dunno if it's like some ancient myth. I don't know who originated it, but

[00:19:18] **Tim:** I think it's like Indian, Indian, European, like the continent of India.

[00:19:23] **Ben:** yeah, it's like this. Everything's being held up by a whole bunch of elephants, I think. And then those elephants are standing on a turtle.

[00:19:30] **Tim:** let's see Turtle that's swimming through space.

[00:19:33] **Adam:** No, but then what? Then the question is, you know, why, what is the, what's holding the turtle up? Well, there's another turtle underneath that well hurt. What's holding that turtle up? And it the, then you get to it's turtles all the way down.

[00:19:42] **Ben:** all the way down. Exactly.

[00:19:45] **Adam:** Anyway,

[00:19:46] **Tim:** We, we just, we just, this has been, this has been mansplain car.

[00:19:56] **Adam:** so Timothy,

[00:19:58] **Tim:** Adamus.

[00:20:00] **Adam:** I, this is your regularly scheduled, tongue lashing.

[00:20:04] **Tim:** Yeah,

## [00:20:06] Browser Password Storage

[00:20:06] **Adam:** so it came up a couple of weeks ago. You said that you just store your passwords for websites in the browser, and I

[00:20:15] **Tim:** part. For the most part I do, I

[00:20:17] **Adam:** You, you put the rest of them in your contacts in your phone or

[00:20:20] **Tim:** yeah, no, I do have a, a, a password safe. So it's not like whatever it is you use.

[00:20:27] **Carol:** 1Password.

[00:20:28] **Tim:** one, I don't use one part, but it is an encrypted safe where the leads are stored, and I do back that up regularly to some other place. but

[00:20:37] **Adam:** so.

[00:20:37] **Tim:** most part, they're usually in the browser.

[00:20:39] **Adam:** is it a browser plugin? Is it like a, an application that just tells you it's encrypting the file? Or What is the interface? What does it look like to work with this password safe you're talking about?

[00:20:49] **Tim:** So it's, it's just a. Program that sits in your cis tray, you double click it, you put in your, your master password, and then it opens up and I've got 500 passwords, right. That are, that are saved in there. And then I copy that to somewhere else and my wife knows the password in case I croak. 'cause like our, all our stock portfolio and all that is, is part of that.

[00:21:09] **Tim:** So,

[00:21:10] **Adam:** Gotcha. Okay. Well, you're not too far off with that

[00:21:12] **Tim:** it's, but it's not as like slick and cool as like 1Password to wherever it is. I just, I've been doing this. I like it, it works for me. It's simple. I don't how to explain it to my wife for my kids,

[00:21:23] **Ben:** Is this something you built or this is

[00:21:25] **Tim:** no, no. It's, it's, it's a pro, it's an old, old EXE program you can download called Password Safe.

[00:21:30] **Tim:** It's like ancient. It looks like it was written in vb.

[00:21:34] **Carol:** I was gonna ask if you've ever used KeePass, 'cause it sounds a little bit like KeePass.

[00:21:38] **Tim:** It's probably similar to KeePass. Yeah.

[00:21:40] **Carol:** Yeah, KeePass is one of the, so we can't use like the, the software that we use at work is very limited. KeePass is one of the things that we're allowed to use because it keeps your database of your passwords local.

[00:21:53] **Carol:** So what I do is I have a shared dev, Database on my SharePoint drive that any of the developers on my team can go get. And I just tell 'em the master password. Yeah. No. Well, it's not synced to the cloud. It is not up in, in their cloud or anywhere else. Like 1Password's blocked because it does a sync to the cloud.

[00:22:12] **Carol:** So we can't use 1Password. Right. So KeePass, I can, because it doesn't do any data push. So I put the pass, the, the, the KeePass database out there only because the thing that it gives me that the everyone else needs is whatever we create, our usernames and our passwords to go do testing in the other environments, everything requires MFA.

[00:22:32] **Carol:** So since I have to have multifactor authentication, I either have to give everyone an email account that you can access and we're not supposed to go to Gmail, so that's a problem. Or I just set up 10 accounts and I put the MFA in KeePass and now they all have access to that, that multifactor authentication code that gets populated from KeePass.

## [00:22:53] MFA and Second Devices

[00:22:53] **Ben:** Quick, quick, quick side Quest here on, on MFA for a second here. I, I, so at work we have single sign on, and when I log in in the morning, I have to get a push notification to my phone using a, this is a service called Duo. And, you know, I've, I had to do this at Envision and Envision we used Okta,

[00:23:11] **Ben:** And you know, I hit the little button and I'm logged in. And the other day I said in the IT room in Slack, I said, Hey, does Duo have a desktop app? 'cause I'm kind of tired of taking my phone outta my pocket. And someone said, well, the whole point of the phone is that it's a second device. And I said, but the computer's also a second device because everything we do is web-based.

[00:23:36] **Ben:** if you stole my phone and it could log into my phone, then you could get the push notifications as well. I, I didn't know if that was true. Like, I didn't know if that was the right way to think about MFA. I feel like desktops are treated often separately, or they're thought of separately

[00:23:51] **Tim:** Yeah, EV every SecOps person I've ever dealt with has told me the same thing. And I had a guy, I've never done this, but we had a guy work for us who got so he heated in the discussion with them about that. Or what he did is he started using Google Voice on his computer to do the MFA. So,

[00:24:11] **Ben:** I love it.

[00:24:12] **Tim:** because, because, because the, I the SecOps guy was like, yeah, it's, it's a thing, you know, it's a thing you have and they're gotta be separate things. And he's going on and on and the dude's like, nah, I'm just gonna work around your, I'm gonna make the exception to your rule, buddy.

[00:24:27] **Carol:** let me ask you something, Ben. So for your, MFA, you're using, this is when you log into your laptop, right? So you're logging in, you put in your username password, and then you have to push it, or is this some other time?

[00:24:38] **Ben:** It's not to log into the computer itself, but it's to log into all the web services once I'm on the computer. So like to log into the, Microsoft 360 or Office 360, whatever it is. And

[00:24:49] **Adam:** it's called Copilot now.

[00:24:50] **Carol:** Uhhuh.

[00:24:51] **Ben:** is it

[00:24:52] **Tim:** Copilot. Yeah.

[00:24:53] **Carol:** Mm-hmm.

[00:24:54] **Ben:** my goodness.

[00:24:55] **Tim:** We should just go back to clippy. Let's just, Microsoft Clippy.

[00:24:58] **Carol:** I'll put my passwords there too.

[00:25:01] **Adam:** It looks like you're trying to access your email

[00:25:06] **Ben:** all right. Anyway, sorry. I don't mean to distract. I, I would just, Carol triggered me with her, with her MFA.

[00:25:11] **Carol:** Well, yes. Sorry. I was gonna say, uh, another job. So I would log in and before I could get past the login screen, I had to authorize so I couldn't access my laptop be until that happened. And then once I logged out, they have to do it again. So then once I was on my laptop, they're like, oh, well you've already confirmed, so you're good to go.

[00:25:30] **Carol:** Now you're, you're past that check. Now I have a piv, I have a card that gets inserted that then has keys on it and asserts have to be on there and, yeah.

[00:25:38] **Ben:** Crazy. Yeah. You're, you're, you're living in a whole different kind of world,

[00:25:41] **Carol:** A little, a little different, yeah.

[00:25:44] **Tim:** The government.

[00:25:46] **Ben:** so, okay. I, I, I know that the browser has an option to store passwords, but where does that go?

[00:25:52] **Carol:** Session.

[00:25:53] **Adam:** it writes files to your computer. So on Windows it probably goes into the registry on, or is that, is that still a thing? I've been off Windows for so long.

[00:26:02] **Tim:** It's gotta be shared because I can go to my, I can, I can have a password in my Chrome on my desktop and it will show up in my phone. So I

[00:26:12] **Adam:** on the

[00:26:12] **Adam:** browser.

[00:26:13] **Tim:** I don't think it's, I don't think it's storing it in registry. It's storing it somewhere.

[00:26:17] **Adam:** Yeah, Chrome. Chrome is probably storing it in Google Cloud somewhere.

[00:26:21] **Carol:** Yeah, it's a profile that you have. It's part of your, profile that gets created is where they store it, I think.

[00:26:28] **Adam:** Yeah.

[00:26:29] **Ben:** So my wife is a big fan of saving stuff into her browser and

[00:26:34] **Adam:** So, uh, let's let's like lay out some ideas of like why this is a bad thing, right? So if you just, for example, your computer hard drive dies and you can't, you like physically cannot boot that computer anymore. There's no recovering it. You tried to spend a thousand dollars to recover the drive. You can't now, you can't log into your retirement account, you can't log into the payroll system.

[00:26:57] **Tim:** I can on my, I can on my phone, on Chrome.

[00:26:59] **Carol:** yeah. If, if the browser sync, if there's actually a sync on that browser, then yes.

[00:27:04] **Adam:** Yeah.

[00:27:04] **Carol:** So

## [00:27:05] 1Password Features

[00:27:05] **Ben:** contrasting that with something like 1Password where day one it's sinking to a remote service,

[00:27:11] **Adam:** Right.

[00:27:12] **Ben:** even if that computer dies as long as you have your like master was like product key in A PDF that they sent

[00:27:21] **Adam:** Master password. Yeah.

[00:27:22] **Tim:**

[00:27:22] **Ben:** So 1Password does something strange. And it's frustrating because it's one of these things where it's like I only have to do it once every five years. So I sort of forget how it works. But there's a master password that I have. But then I remember when I opened the account, they send me an emergency kit, PDF, and in it is a different key, which is not the master password, but I don't know what that key represents.

[00:27:47] **Ben:** And I'm not even sure where it is actually, if I think about it.

[00:27:50] **Adam:** black magic.

[00:27:51] **Carol:** It's just a recovery code. I mean, it's like, oh, you can't get into it. Well, here's a list like Gmail does it. Here's a

[00:27:56] **Ben:** no, no, no, no. This

[00:27:58] **Carol:** that you can use. '

[00:27:59] **Ben:** I think when I. Enabled it on a new computer. I had to enter both my Path Master key and also this

[00:28:07] **Carol:** Oh, and that long, like gooey key. Yeah.

[00:28:10] **Ben:** that freaks me out because I don't know where to keep that. And I have to use it so infrequently that I feel like I'm gonna forget where it is.

[00:28:18] **Ben:** I mean, I'm, it's probably in Dropbox somewhere,

[00:28:21] **Adam:** Sorry. Here's what I do with it.

[00:28:22] **Tim:** I got.

[00:28:25] **Adam:** It's got a QR code on his arm with the information in it. I, I stored in two places. I store it in 1Password because it, you know, nine times outta 10 99 times out of a hundred. When I wanna reference something in there, I can access it on one of my devices.

[00:28:37] **Adam:** Right. I can pull it up on my phone or my laptop or my iPad or something. But, and then I, you know, if for some reason my house burns down and all my devices go with it, I don't wanna be totally screwed. So we have a fireproof safe in our house where we keep important documents, birth certificates, that sort of thing.

[00:28:51] **Adam:** and I have, have it printed out and, and store a paper copy in there too.

[00:28:55] **Ben:** I feel like I'm writing this down to make sure that I remember to check that I actually have this PDF 'cause I think that's, that freaks me out. Literally, I, I don't know my passwords to almost anything, like 99% of my services are just random squiggly

[00:29:09] **Tim:** Right.

[00:29:10] **Carol:** I don't even know most of my usernames. I've stopped using my email for my user and I just have it generated a username for me too. So when their accounts, like when their accounts get breached or leaked, it's not tied to my email, then they go look for it.

[00:29:25] **Adam:** have you ever used a service where it's a credit card, but like for every transaction it kind of generates a new virtual credit card number?

[00:29:32] **Carol:** I have, I've done that. I

[00:29:34] **Adam:** I wish that something, and maybe it does exist, but like a sys a er, service that did the same thing for logins, right?

[00:29:40] **Carol:** would be great.

[00:29:41] **Adam:** Yeah.

[00:29:42] **Tim:** One time throw away.

[00:29:43] **Adam:** give out your real email address to every

[00:29:45] **Carol:** Well, apple does that, right? They do the hide my email. So whenever I go to fill it in, it's oh, okay, well this is now gonna forward to this email account, so it kind of hides it. But I still get the information.

[00:29:57] **Adam:** Yeah. That's for like when you sign up for apps or whatever, but

[00:29:59] **Carol:** Yeah,

[00:30:00] **Ben:** I, I don't, I'm not familiar with this. This is something that Apple's doing automatically, or this is something you.

[00:30:06] **Adam:** when you, yeah. When you use Apple ID to sign into an app. The, and it asks for your email address. They give you the option to give them your email address or for the, for Apple to mask your email address. So it generates like some random string@apple.com, which then if they were to need to email you, they can, they can email that address and it forwards to you.

[00:30:27] **Adam:** but then, you know, it can be taken away,

[00:30:29] **Ben:** this is just proof of how few apps I actually install.

[00:30:33] **Carol:** Well, mine's not just with apps 'cause it pops up in Chrome all the time when I'm creating logins. yeah, like I just was on Dyson looking at a new air purifier and was gonna create an account and I was like, I hit the little button in Chrome, said hide my email and it populated like 97 underscore Giants something, something, something at iCloud and it'll forward to my regular email address.

[00:30:56] **Adam:** Nice.

[00:30:56] **Tim:** I've not seen that.

[00:30:58] **Carol:** yeah. I use it quite often.I did wanna ask one thing though. So an issue I run into, so when I'm thinking about password management and kind of like what happens when I store it, say in Chrome or in edge or any browser, is I feel like the very first like place of attack happens in the browser.

[00:31:16] **Carol:** And it's not the browser that have issues with, it's things like ads and, extensions that were good. And now these extensions They get sold. They get sold, right? And then now that new owner isn't using the, the data the way the, original creator was. So now they have access to my session to what's going on.

[00:31:38] **Carol:** Like they have access to my passwords. And once one's out there, I feel like everything's out there. it's not like they're pulling a single password. They're getting the entire profile when that happens. So all of your passwords are then gone.

[00:31:51] **Tim:** But I, I mean, that might be true, but so I noticed that whenever I try to go look at a password, right, if, if, say for instance I actually can't remember it, it's not in my password safe. I will sometimes go into Chrome and look at the passwords, but it requires my route,

[00:32:11] **Ben:** Your computer

[00:32:11] **Tim:** the laptop.

[00:32:12] **Adam:** Gmail account password.

[00:32:13] **Tim:** No, no, not even Gmail for the actual physical machine.

[00:32:16] **Carol:** I like the machine passwords

[00:32:17] **Tim:** is a machine password for windows. So it, it will ask for that local machine password, which I leads me to believe that they're probably encrypting it and that without that they're not gonna get it. So as long as, I would hope that, as long as the bad guys can't figure out what your local machine password is, then you should be safe.

[00:32:37] **Tim:** But you never know. I mean, these guys are, these guys are so smart. Coming up with ways to be bad.

[00:32:45] **Ben:** okay. But this is, so Tim, you bring up one thing that I was unclear about because one of the things that I've always loved about 1Password is that I can go look at the passwords.

[00:32:53] **Ben:** It's not just a, a black box, but you're saying that when it gets stored at the OS level, you can do that as well?

[00:33:00] **Tim:** I dunno about 1Password, but I do know at the browser level on Chrome it asks, at the OS level, it asks for the the local Windows laptop

[00:33:09] **Ben:** sorry, sorry. What I mean is you can see the original password

[00:33:12] **Ben:** that you've stored. Gotcha. I thought that was one of the trade offs is like, it goes into the walled garden that is Apple security and you never get to see it again, kind of a thing.

[00:33:21] **Adam:** So,I'm glad to hear, Tim, that you're not just using the Chrome Password Manager and that's it. Like you, you've got the whatever vault or, or safe, password safe thing.

[00:33:30] **Tim:** I was being spicy. I was being spicy

[00:33:31] **Tim:** when I said That like, yeah,

[00:33:32] **Adam:** that's fine. That's your, that's,

[00:33:34] **Adam:** that's your role you play here sometimes. and, but, I do think even, even that aside, I think that there's still good reasons to use something like 1Password or KeePass or whatever.

[00:33:45] **Adam:** the one I have been using for too long to remember is 1Password, so it's the one I know the best. and I, I'm sure that other alternatives have something similar, but, IUI store a lot of stuff in my 1Password that is not passwords, right. So I have everybody in my family's social security numbers for quick reference.

[00:34:03] **Adam:** Right. You know, how, how many times have you been at the doctor's office or at, you know, trying to set something up and they're like, okay, I need your child's social security number. And you're like, I don't

[00:34:10] **Tim:** Yeah.

[00:34:10] **Adam:** Right.

[00:34:14] **Tim:** Six,

[00:34:16] **Ben:** Well, so along those same lines, if, if I can, you are, or one person is not always the only person who needs to know that information. And one of the things that I love about 1Password is that we're on a family plan and we have, me and my wife have a shared vault. We have private vaults, and then we have shared vaults.

[00:34:33] **Ben:** So a lot of stuff, even things that I sign up for, like the bank account or, or you know, whatever, the Hulu account that I store into the shared account so that she can access it when I'm not around.

[00:34:46] **Tim:** that, that, now that's a selling point. 'cause you can't do that with, with

[00:34:50] **Tim:** Chrome

[00:34:50] **Adam:** So.

[00:34:51] **Carol:** Hold, wait, hold. I need to add one thing, Ben. So the sharing is great as long as you can teach someone how to use it. My husband. is the best, the best husband in the world. I got so tired of telling him what his 1Password password was, that I signed him out and signed him into mine, and now I just put everything in my private vault and he does too.

[00:35:12] **Carol:** And he doesn't realize that he doesn't have his own 1Password yet.

[00:35:18] **Adam:** that's

[00:35:19] **Tim:** know, we all have our strengths and weaknesses.

[00:35:21] **Ben:** That's right.

[00:35:23] **Adam:** so yeah, like we also use the, we have a 1Password family plan, which I will say if you, if your company has 1Password for like your employees to use, each of those employees also gets a free 1Password family plan, um, which is a super nice benefit. And so like with that free family plan that I get, because my company uses 1Password, we just have a business license.

[00:35:44] **Adam:** I have myself, my wife, both my kids and my mom all on my family plan because I think you can have up to five people.and it, it, and then we also use the sharing heavily, right? So like we have, I have my private vault, my wife has her private vault. We have a shared Megan and Adam Vault, and then we have mom, dad, and kid one, and mom, dad and kid two, vaults.

[00:36:06] **Adam:** So they, and they each have their own private vaults too, but there's things that's you know, my kids' steam password is in there, shared one with us, so that if they're out and about and they need to get it and they don't have their phone or whatever, they can ask me and I'll just like, yeah, here, here's your steam password sort of thing, which is very handy.

[00:36:22] **Adam:** And then, so I, I'd mentioned social security numbers, but you can, also store other stuff in there. I think they call 'em identities, which is basically, it's like a name and address, right? But then when you're filling out a form online to ask for your address, it just pops up.

[00:36:33] **Adam:** You, you put your, cursor in the ad, you know, street, one field and it pops up and says, Hey, do you wanna fill in your home address, your work address, whatever.

[00:36:41] **Ben:** And that's coming out of 1Password.

[00:36:43] **Adam:** yes sir.

[00:36:43] **Ben:** Oh, I didn't know that.

[00:36:44] **Carol:** It is,

[00:36:45] **Tim:** see. Chrome does that as well, but it's just in Chrome.

[00:36:48] **Adam:** yeah.

[00:36:49] **Carol:** Because like I was gonna say, Chrome will do it like with your credit card, and I'm always like, no, do not save my credit card. I just pull it from 1Password I have. Everything's in

[00:36:58] **Adam:** I do. My credit cards are in there. My, like I have business credit cards and my personal credit cards. I have social security numbers. I mentioned driver's licenses or like loyalty reward programs, like my frequent flyer number, you know, that's in there. And they have like special types of things for a lot of these records.

[00:37:15] **Tim:** It makes it easy to like, filter and sort find the right stuff. So, yeah, I think so. Sharing. I think that is a good, really good feature of that. That's something that I don't have access to right now, so I, I might consider it

[00:37:28] **Adam:** Yeah. because I'm sharing now, but it's like manual, like every few months I'm like, okay, I'm gonna update this and put this on a shared that we have a shared computer that, that we use so that if I croak, you know, they can go get my passwords and take all my money or their money, their money.

[00:37:45] **Tim:** Now I'm dead. I don't need it.

## [00:37:46] Email Address Accumulation

[00:37:46] **Adam:** So of the four of us, does anybody only have let's set aside work only in your personal life, do you only have one email address or have you like over the years, accumulated more than one?

[00:37:58] **Tim:** I've got so many email addresses. Oh my God, I buy so many domains. I'm like, this is the coolest domain ever. And thenI use it for like two weeks.

[00:38:07] **Ben:** I have my original Ben Nadel at Gmail, and then when I realized that you could just have Gmail, work for any domain, I don't know what the right term for that is. Now I have my Ben at email address, but

[00:38:23] **Ben:** I I think the alias each other at this point or, or like there's some sort of forwarding

[00:38:28] **Adam:** forward or something? Yeah. What about you, Carol?

[00:38:32] **Carol:** I have one I use for most things, but I definitely have two different last names in an email address. So I have Hamilton and Weiler, and then Steve and I have, an account that we share for like our, Netflix logins that we share with the kids. Like we have one that's easy enough for them to have the password, but I don't, I don't use a ton.

[00:38:49] **Carol:** I don't use any other ones. So they've, over time I've deleted them.

[00:38:52] **Adam:** So you don't have a history of Carol at Yahoo and at Hotmail, that, that just linger on some of these old accounts that you haven't updated. Because where I was heading with this is okay, so even if your, you know, your laptop dies and you can't get to your, password vault on there, and you don't have it, something that's synced up to the cloud, you, your best recourse at that point is usually reset your password, right?

[00:39:13] **Adam:** Like at least then I could do that. And that's great if you happen to know what the email address is on the account and that's another thing that's stored in your password vault. It's oh, okay. So for my Netflix, I use this email address versus for, you know, Amazon Prime, it's this email address, whatever.

[00:39:28] **Adam:** But

[00:39:28] **Tim:** Now I'm wondering if my a OL account is still good.

[00:39:32] **Adam:** See I had one of those, I definitely had, I had a,

[00:39:35] **Ben:** I had a OLI had Hotmail. I don't think I ever had Yahoo. I think I went from Hotmail to Gmail.

[00:39:42] **Carol:** I had Yahoo in high school and went straight to Gmail.

[00:39:45] **Ben:** One thing that I wonder? So when I first got into web development back in the day, when we were building websites and we had to output an email address on the website, the company that I worked at went through all these programmatic. Shenanigans in the backend where they would actually take the email address and they would loop over the characters.

[00:40:05] **Ben:** And then each individual character in the email would be HTML encoded. Like it would do like a pound. And then the asking number for that letter and may have also been wrapped in spans this idea that it somehow made it harder for,you know, like a web, web scrapers to find the email addresses.

[00:40:23] **Ben:** And I, and I wonder if anybody still does stuff like that. I just assume that web scrapers are so advanced at this point. There's if it renders right, it's basically gonna be somehow, you know, screen captured and then OCR or something.

[00:40:36] **Adam:** there's gotta be 20 ways to skin that cat. yeah. I

[00:40:39] **Adam:** mean there's, I think there's even you know, diviv, if you, if you could run some JavaScript on the page, you can do get the, the element and just do like text content

[00:40:46] **Ben:** yeah, yeah.

[00:40:46] **Ben:** Totally.

[00:40:47] **Adam:** yeah. So if there are any spans or whatever in there, it's just gonna strip 'em out and give you the visible text from whatever's inside that.

[00:40:54] **Ben:** I'm curious. I'm just, it's, it's just random thought. I'm curious if there are still people who are trying to

[00:40:59] **Tim:** Sure there are people that are doing it, they're not doing it right. Obs obscurity through obscurity.

[00:41:04] **Ben:** You know, speaking of security through obscurity, I have a, a portion of my personal site that I am, I'm the only one who should ever access it. I have a special cookie value that I set. And if that cookie value doesn't exist, I just return a 5 0 3 service unavailable. And I'm like, every bone in my body is like, that's a terrible idea.

[00:41:24] **Ben:** But I'm like, yeah, it's working though. I think it's working at least.

[00:41:28] **Tim:** I'm not a high value. I'm not a high value target right now.

[00:41:31] **Ben:** and I'm

[00:41:32] **Adam:** It's the words cold fusion is the best with 17 lines of white space for between each word.

[00:41:36] **Ben:** Academically. I know it's a terrible idea, but like practically, I don't know how to poke holes in it. I'm like, how would anyone ever know that that cookie exists and is part of the processing logic? And even if they knew that that cookie was being checked, like how would they ever know about it?

[00:41:51] **Ben:** They'd have to hack into the logging

[00:41:53] **Tim:** Or listen to this podcast.

[00:41:55] **Ben:** or,

[00:41:56] **Adam:** So they listen to this podcast and then they go steal your laptop when you're at a conference and they just look at your cookies.

## [00:42:04] 1Password Mobile Integration

[00:42:04] **Ben:** oh God. I love security.

[00:42:07] **Adam:** Do you though?

[00:42:11] **Ben:** Oh man, I, one thing that I, was a big point of friction for me with 1Password. I'm just saying this for anyone else who might have not yet discovered this yet. whenever you go to a form on your phone and you have to go to a login. The default behavior is to be able to present the web, the browser embedded things like these things that are saved with the Mac Os.

[00:42:33] **Ben:** and then like literally, I had been using 1Password for years and maybe it was someone on this show that said, oh, by the way, you can just set 1Password to be a source for those auto suggests on the phone. , that changed my life. And if anyone here didn't know that, it's a game changer to be able to say you can look in 1Password for things.

[00:42:52] **Ben:** It's fantastic.

[00:42:54] **Adam:** it is. It's great. It's the best.

[00:42:56] **Ben:** Yeah, remove so much friction by those freaking, uh, QR codes to log into your Netflix account on the tv. It's game changer.

[00:43:03] **Adam:** Anybody else have anything you wanna say before we wrap it up?

[00:43:05] **Tim:** I would just say that I was not as wrong as you thought I was.

[00:43:09] **Adam:** You misrepresented how wrong you were, sir, which is fine. It's a good conversation.

## [00:43:15] Patreon

[00:43:15] **Adam:** okay. Well then this episode of Working Code is brought to you by the letters A, D, H, and D, and then number six, and listeners like you, if you're enjoying the show and you wanna make sure that we keep putting more of whatever this is out into the universe that you should consider supporting us on Patreon.

[00:43:28] **Adam:** Our patrons cover our recording, editing and transcription costs, and we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo. You guys rock.

## [00:43:37] Thanks For Listening!

[00:43:37] **Adam:** We're gonna go record the after show, a little teases of what we're gonna talk about. somebody wants to talk about the pit being back like it's a great TV show.

[00:43:44] **Adam:** and, Star Trek Academy, a new Star Trek TV show. Apparently we're gonna talk a lot about tv. I wanna talk about some code stuff. I'm gonna tell the story of my first Claude, like Yolo mode, like just turn off all the safeguards and the first time it did something kind of negative and scary

[00:43:59] **Adam:** to

[00:43:59] **Carol:** Uh oh.

[00:44:00] **Adam:** Yeah. So if you want to get stuff like that, you gotta become a patron of the show and you become a patron of the show by going to patreon.com/workingcodepod. Throw a few dollars our way, you get full access to all the historical archives and all the new, app shows and, other benefits like access to special areas of our discord, which by the way, we have a discord and it's free in public.

[00:44:21] **Adam:** workingcode.dev/discord will get you to the right place. That's gonna do it for us this week. We'll catch you next week. And until then,

[00:44:29] **Tim:** No password needed to encrypt the fact that your heart matters. . ​
