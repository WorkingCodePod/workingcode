---
title: "252: Meet Showbot"
description: "Tim spent a single Sunday afternoon with Claude and built Show Bot -- a sarcastic Discord bot trained on every Working Code transcript."
date: 2026-03-18
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/8730260e-c5d1-4519-810b-18d8b8eb3fac"></script>
<div class="redcirclePlayer-8730260e-c5d1-4519-810b-18d8b8eb3fac"></div>

Tim spent a single Sunday afternoon with Claude and built Show Bot -- a sarcastic Discord bot trained on every Working Code transcript, complete with a Dungeon Crawler Carl personality, fallacy detection badges, and a talent for roasting anyone who tries to prompt-inject it. The conversation turns into a deep technical walkthrough of RAG pipelines, local models, cross-encoder reranking, and what happens when you just start building things that make you laugh.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Thursday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/252-meet-showbot.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Cold Open

[00:00:00] **Adam:** Has anybody in our Discord tried to like hack your bot by like saying, forget all previous, uh, instructions.

[00:00:05] **Tim:** Brian is the very first, he was one of the first users, and that's exactly the thing he did.

[00:00:11] **Ben:** That's

[00:00:12] **Tim:** bot, the bot roasted him mercilessly about that.

[00:00:16] **Adam:** That's awesome.

## [00:00:37] Intro

[00:00:37] **Adam:** Okay, here we go to show number 252. And on today's show, Discord Bites Back. Discord is a place where we just hang out when we're not here on the mic. And, Tim gave it to, a personality and, it likes to rub that in our faces. So we're gonna get into that a little bit, and just talk about the experience of building the bot and, what it's been like and should be fun.

[00:01:00] **Adam:** but first, as usual, let's start with our triumphs and fails. Carol has an excused absence. She had to return some videotapes.

[00:01:06] **Tim:** Video, please be kind. Rewind Carol. She doesn't get that reference.

[00:01:11] **Adam:** No, she definitely won't.so f Ben, I'm gonna come to you first. What do you got going on my friend?

## [00:01:16] Ben's Fail

[00:01:16] **Ben:** Sure. I'm gonna go with a failure here, and if you'll cut me some latitude, I wanna give you a little backstory on, on how I got to

[00:01:22] **Adam:** Ding,

[00:01:25] **Ben:** So over the weekend we watched a documentary on Netflix by, I think it's Louis Theroux, called Into the Manosphere.

[00:01:34] **Adam:** I saw ads for this on Netflix.

[00:01:36] **Ben:** yeah, it was an, I'll say it's an okay documentary. I, it wasn't like blown away or anything, but it was just, I, I am not part of the manosphere world. I, I, I don't even listen to sort of like Edge of manosphere podcasts like Joe Rogan.

[00:01:51] **Ben:** It's just not really my thing. But, it, it, it's a very disturbing view at a world that I don't understand or relate to in any way. It's all these men who are trying to make money by basically belittling women and trying to empower men. And it's, it's just. It's very disturbing.

[00:02:12] **Adam:** Is this, it sounds vaguely like men's rights adjacent. That kind of same person would be interested. Okay.

[00:02:18] **Tim:** the, the whole men go their own way movement,

[00:02:22] **Ben:** it's, it's like, I mean it's, it's all about how the, uh,the balance of the genders has been thrown out of whack. And men need to be put on top again. And women need to know their place. And it would probably be better if like women didn't vote and it, like, it gets like,

[00:02:39] **Tim:** that's worked out really well throughout history,

[00:02:41] **Ben:** it's like there's just a lot of really crazy stuff.

[00:02:44] **Ben:** anyway, so me and me and the Mrs we were just talking about a lot 'cause it, it's so bananas and I, and I relate

[00:02:51] **Tim:** the little lady.

[00:02:52] **Ben:** mean little lady. I said, Hey, get out of the kitchen and come talk to me about this.

[00:02:59] **Tim:** Oh, you're getting canceled

[00:03:00] **Adam:** While you're voting.

[00:03:04] **Ben:** so, so we were talking about how one of the most shocking things in the show. In the, in the documentary was he's walking down the street with these guys who are these manosphere podcasters and, you know, live stream video people. And these kids, like young teens, would just come up to them, would, would recognize these people in the street come up and be like, oh, you're, you're, you're a hero of mine.

[00:03:29] **Ben:** You're my role model. I love you. You know, thanks for making, you know, giving me someone to look up to and someone to be modeled after Like, like very young kids, like Disturbingly young kids are coming up and saying this. And I grew up in the nineties when we had a lots of violent movies. I mean, I grew up in the action movie era and violent video games were becoming a thing.

[00:03:53] **Ben:** And I remember at the time there was a lot of controversy that these violent movies and these violent video games are gonna make people violent. And I think nothing really ever came of that. And I think, I mean, this is just my personal take on it, is that when you're watching a movie, when you're playing a game, you understand very clearly that it's make believe, you know, I can watch Arnold Schwarzenegger rip some guy's arm off and it's not like I want to go rip some guy's arm off.

[00:04:20] **Ben:** Like I might get jacked up and feel like, oh, this is a great movie. But like, I know it's pretend and I know it's make believe and it's not something I ever wanna model my life on. And I think the same probably applies to video games. You know, we shoot people in video games. I spent my whole college years playing Street Fighter and, GoldenEye, you know, running around slapping people and shooting and stuff.

[00:04:39] **Ben:** but then I think part of the problem is that. The social media is this, it's the same thing as a movie. It's make believe more or less, right? People are are setting these scenes up. They're curating everything. They show it's angles, it's it's production value, it's click farms, it's working the algorithm.

[00:05:01] **Ben:** It's all a production in the same way that a movie is, but with none of the obvious trappings of it being a movie. And I think maybe that's part of the problem that why kids look up to it because they don't, they can't separate that fact from fiction. Like you can when you're watching

[00:05:18] **Tim:** Right, because a movie, you go there to be entertained when you're listening to an influencer, like you're learning to try to learn something, right?

[00:05:25] **Ben:** Right. Okay. So this brings me back to my failure because I have over many months now been doing a lot of hemming and hawing and hand wringing about all of the AI stuff. And like these people, you know, these people are talking about this 10x, a hundred x productivity gains and all these software that they're building and how, you know, we're all gonna be out of a job in six months.

[00:05:47] **Ben:** And I feel like my failure is that I have not been discerning enough to look at that as the production of social media. Like I, it's easy for me to look at someone who's hanging out on the beach and making a video or you know, doing something crazy or riding around in a Lambo. Like that's obviously pretend in my mind and it's very clearly pretend.

[00:06:14] **Ben:** But when I hear someone talk about all of the stuff that they're doing from a technology standpoint, historically. I've never had to, I think, consider exaggeration. Like why would you exaggerate anything that you're doing technology wise? Because like we're all historically writing blog posts, sharing videos, like, oh, here's this really cool thing I learned.

[00:06:36] **Ben:** Here's this open source project I'm working on. It's been a very, I wanna say like honest and supportive community. And so it never occurred to me that anyone would come in and say anything that's not like

[00:06:50] **Adam:** Yeah,

[00:06:51] **Ben:** and truthful. Because why? Why would you ever want to bend the truth when it comes to technology?

[00:06:57] **Ben:** Like there doesn't seem to be an end game.

[00:06:59] **Tim:** Uh, besides

[00:07:00] **Adam:** to me, yeah, exactly. It feels to me like this is yet another place, another channel where people are just coming in and exploiting it to try and extract value, right? Like billionaires coming in and flooding the conversation with bots that are talking to each other and generating, you know, likes and comments and engagement to get paid on the original post.

[00:07:23] **Ben:** Right.

[00:07:24] **Adam:** You know, drive traffic to their thing, whatever

[00:07:26] **Ben:** So, and I, and you know, I'm not pointing at any people in particular, and I'm not saying that, I'm not even saying that people have a nefarious slant to what they're saying. I think people are probably genuinely very excited about a lot of stuff and they're doing a lot of experimentation and they're finding a lot of really interesting ways to use stuff.

[00:07:47] **Tim:** Like building a bot, Discord

[00:07:49] **Ben:** I Exactly. good foreshadowing. Yeah.

[00:07:54] **Tim:** call forward.

[00:07:55] **Adam:** I.

[00:07:55] **Ben:** But I think, just as, when I think almost relating back to this manosphere stuff, there's so little allowance for nuance that everything becomes extreme and the extremity. Is the only thing that people herald is the truth anymore. And I, I like, I I don't know how to articulate this any clear anymore clearly, other than to say that I think I have almost fallen into the same trap that people who watch regular social media fall in, where they see people say something outrageous and it just, it just seems truthful.

[00:08:31] **Ben:** 'cause like why wouldn't they say it? Or like, why would they say it if it wasn't truthful? And I'm just, I feel like I have not been discerning and that's my, my big fail. And I've let it really have a deleterious effect on my psyche. And it has like really had, it's like I've been depressed, I've been anxious, and it's all because I'm like, oh, I don't have 16 agents running in parallel 24 hours a day.

[00:08:59] **Ben:** And that seems to be just what everybody's doing, but I

[00:09:01] **Tim:** was. Claude was down today.

[00:09:03] **Ben:** Yeah. You know, that was a whole other thing that was like, am I on? Is it a snow day? Like,

[00:09:09] **Adam:** Yeah,

[00:09:10] **Ben:** did, does work Just suddenly stop. So,

[00:09:14] **Ben:** have to write the code myself. so, you know, I, I just, I

[00:09:19] **Tim:** is not my beautiful code. These are not my beautiful tests. Same it as ever was.

[00:09:25] **Ben:** I just need to be kinder to myself and I need to realize that everything now that is part of the social media sphere cannot be disconnected from the fact that it is part of the social media ecosystem. And that's. Makes me sad a little bit, but it, it's more like I'm slapping myself on the wrist for, I think, falling into the trap that I sort of look at other people, you know, who wanna watch reality shows and being like, how do you even enjoy that stuff?

[00:09:58] **Ben:** But like, here I am, you know, watching one video after another of people talk about agent skills and, and new IDEs and, and like feeling myself getting sucked into that black hole. Anyway, that's my

[00:10:12] **Adam:** have to, I, I have a link I'll have to send you Ben.the, I read today and I, I found it very insightful. the, I mean, I, I'll, it's a long post and it is on the hell site, formerly known as Twitter. Um,I'll send you the link, but basically it's just like a, it's like a, I guess people that pay for the blue check mark, they can do blog posts on Twitter now or whatever, but, so it's a, it's a long read, but it, I thought, I found it insightful.

[00:10:39] **Adam:** I found it pretty good. and it's, the kind of, the thesis is just like, keep it minimal, you know, your, your CLAUDE.md should be like, minimal, minimum, minimal, minimal, minimal. Say that five times fast. and, you know, like just, just use the, the native CLI tool that they give you and, and just, you know, keep it simple, right?

[00:10:59] **Adam:** And because like, if you look at these things like MCP and skills, these are things that kind of started in the community. Like how, c the community invented hashtags on Twitter and then Twitter kind of made them a real thing. the, you know, Claude and Codex from OpenAI are both kind of adopting things outta the community that work.

[00:11:20] **Adam:** Right. So if stuff is working, if there are people that are mostly, or that are having the most success through specific techniques, they will make that part of their product, right? They're not gonna just like let that money slip through their hands.

[00:11:33] **Ben:** Yeah. And also, sorry. one, one more, one more little tangent here because we're, this is probably gonna be a short show anyway, so lemme just tangent for a second. So I asked Claude, I ask we, okay. 'cause we're, you know, part of this ecosystem that we're in right now is, I think we're all doing a lot of experimentation.

[00:11:50] **Ben:** Some much more than others, granted, and we're all trying to learn a little bit from each other. And I asked Claude the other day, I said, explain to me the concept of model collapse and the idea of model collapse. And I'm, I'm sure I'll butcher this, but it's that to date, or, you know, in the beginning, all of the AIs were trained on user generated content.

[00:12:13] **Ben:** This was stuff user did, and it's all human based. And so when we build the model, it's all theoretically based on what humans do. And now we're generating a lot of content based on ai and we're still generating a lot of content from humans. But there's this co-mingling now of, of generated content and user generated content like artificial and user generated content.

[00:12:34] **Ben:** And the models start to sort of get polluted on the patterns that they pick outta that, you know, they're generating patterns and then they're being retrained on their own patterns and it and it

[00:12:44] **Tim:** The snake eating its own tail.

[00:12:45] **Ben:** Yeah. And they call, like there's a couple of different versions. There's like tail collapse, which is when the humans get factored out really quickly.

[00:12:52] **Ben:** And then just regular model collapse where it sort of just amplifies all the bad patterns over time. And I asked Claude, I said, look. It seems like people are going to Claude and saying, Hey, Claude, or whatever agentic coding agent you're using, help me build a skill or a rule or an MCP server to do X, Y, Z.

[00:13:11] **Ben:** And then Claude busts out, you know, a markdown file that has a 300 lines in it with all this fancy stuff about here's what you're gonna do and here's the phases it's gonna run. And, and then people will share and say, Hey, look, these are the skills that I've built and these are the skills that I'm using, but they're not handcrafted.

[00:13:28] **Ben:** They've been, you know, agentically generated and then probably hand tweaked to some degree. So then now this is part of the user generated content that's out in the wild. And then as the models continue to get trained and they get trained on all of the skills and the rules and the MCP servers that have been echoed back into the world, I'm like, how is that not some form of model collapse in and of itself?

[00:13:52] **Tim:** Because, because the users have tested it to make sure it's worth putting out there. Right. You don't put trash out there, typically. You put something out that works, so at least it's been vetted by a

[00:14:00] **Ben:** Maybe,

[00:14:01] **Tim:** May. Yeah. Maybe that's, yeah.

[00:14:04] **Ben:** but it's also so non-deterministic. You know, what works for you in a particular language, in a particular framework, in a particular sized application might not necessarily be broadly applicable. Or maybe it will, I'm not, you know, I'm not saying one way or the other. I'm just saying that we're now amplifying the things that Claude has generated to some degree.

[00:14:23] **Ben:** And Claude did say that that's not model collapse per se, but they were saying that if you look historically, humans have tried a lot of different experiments in, you know, wide reaching and a lot of people tried a lot of different things. And the velocity with which we're sharing and then repeating these same patterns means that we're collapsing the number of experiments.

[00:14:46] **Ben:** Much more quickly than we've ever done before. And Claude's argument was that the, the bigger danger there is that we're just gonna stop experimenting, or that we're gonna essentially assume that this is the right way to do something without doing our own experiments, because this is what someone else said works.

[00:15:01] **Ben:** Whereas historically, we wouldn't have done that so quickly anyway. It was, it was, it was an interesting take. I was trying to, I'm trying to get into the habit of asking Claude to help explain things to me because apparently it's supposed to be good at that. Alright, that's the end of mine. Failures.

[00:15:17] **Tim:** I, I'll, I'll just say one thing. It, it sounds like you're asking your abuser for advice.

[00:15:24] **Ben:** does it

[00:15:24] **Tim:** seems, that seems a strange paradigm to, to, to admit to.

[00:15:29] **Ben:** All right. Carol would be next. She has her excused absence. So Tim kicking it over to you. What do you got going on?

## [00:15:36] Tim's Triumph

[00:15:36] **Tim:** Well, I feel struck by everything you just said because what you were talking about doing is exactly what I spent the weekend doing. at least like mostly on Sunday. and we'll, I think, we'll, we're, that's what we're gonna talk about on the show. So those who are in our Discord channel, if you go down to the very bottom of the main, all the text only channels, you'll see something called Show Bot.

[00:16:00] **Tim:** And so Show Bot, I have a bad memory. All right. So it's like, I was like, I wanna build an LLM, or not an LLM, but I wanna build a system that can be like a sort of an expert system on the show where I could ask the show, ask the, the, the bot. Like, so what have we talked about? You know, give your opinions on.

[00:16:18] **Tim:** So basically training it on the transcripts that we have. So we have the fantastic transcripts that are patrons. Thank you so much for supporting us so that we can have the transcripts. So I trained it on the, on the transcripts and, built a local, it's running on my laptop, local bot, Discord bot that you can just put in a natural language question.

[00:16:39] **Tim:** and it will give you an answer in a very extremely sarcastic, sort of like Dungeon Crawler Carl kind of style answer. and, and then I'm like, well go another step further. There's a whole lot of good. Tribal knowledge that we have on the Discord. So now it scrapes a Discord like every 30 minutes and links to, you know, and, and so it's like, and I, it's all on Python.

[00:17:04] **Tim:** I don't know Python. I've never really wrote much Python. It's all on Python. And really what my job was to just kind of test it and work on it. And I'll be a, actually, you know, some people are annoyed by it 'cause it is a bit spammy. So it's like, if you don't like it, that's, that's fine. Not gonna hurt my feelings.

[00:17:20] **Tim:** Just, you can block the, you can block the bot like I do any user on Discord or just mute the channel. But, yeah, I've had a lot of fun, a lot of people were playing with it over the weekend and asking it questions and testing it out and, and so, and you know, that's not something I could have built. On a Sunday afternoon in the middle of March, before Claude came along, right?

[00:17:44] **Tim:** This would've, this would've been like a two month project that I probably would've lost interest in. But because I kept getting that feedback loop of, alright, I built the minimal, I did it very iteratively. Like, let's do this, let's, okay, let's do this now. All right, now I have the RAG index.

[00:17:59] **Tim:** So did it very iteratively. By the time I, I was like late Sunday night. I'm like, I'm done. I, I can't think of anything else. I want this thing to do. It is doing everything I want it to do. And it's hilarious. I find it hilarious. but I have a sick sense of humor, so your mileage may vary. and so I thought it was pretty cool that, that you could, uh,

[00:18:18] **Ben:** Well don't go go. Don't go into too much detail. You know, if we're

[00:18:21] **Tim:** Yeah. Yeah. 'cause that's gonna be, that's, we'll talk about it in the show. I'll, I'll get, I'll get into the show about how it's built and the technology it's using and everything. So, but yeah, so that, that's my triumph. 'cause it's like, I learned a lot about how to get the most out of the, what makes sense to me.

[00:18:35] **Tim:** I know Adam, you've done these, these REPL loops and everything, and maybe I'll start playing with that at one day. But it's like I finally came up with a workflow that really kind of worked for me 'cause it's kinda like how I normally work anyway, but it's sped it up a whole lot faster than, you normally would do.

[00:18:54] **Adam:** Yeah, I think, uh, play is an important part of learning, right? It helps keep learning fun and, and just gives you a reason to keep going. Keep digging.

[00:19:03] **Tim:** for sure. And it, it, you know, it's like this, I think I sent you some stuff over the weekend, Adam, and you're like, whatever Tim. But like, I'm enjoying this, I'm having fun. Like, well as long as you're having fun.

[00:19:14] **Adam:** yeah, yeah.

[00:19:16] **Tim:** So that's my triumph. How about you, Adam?

## [00:19:19] Adam's Triumph

[00:19:19] **Adam:** So I also have a triumph. it's kind of maybe like a little, like, like you've heard of a, a backhanded compliment. This is a backhanded triumph,

[00:19:26] **Tim:** Okay.

[00:19:27] **Adam:** that Claude only screwed up my ORM based, like I, I'm working on this ORM, migration. All of the ORM moved to SQL and it only screwed it up a little bit.so the goal, was to take all of the existing ORM code and like, keep it, and, and at the controller level, detect

[00:19:46] **Adam:** if the ORM-less feature flag is on, then use the SQL code. And if it's not on, which is like the default state, then use the existing production ORM using code.and so in theory, you know, it finishes all this work and then the, the first thing you do is you go to try and run it.

[00:20:04] **Adam:** And it should be nothing changed, right? Like it should just be evaluating an extra if statement on every request, say, oh, okay, is the feature flag like enabled? No. So we're just gonna do all of the same things. and so you would think that would be nothing, but I mean, it, it was like, what do we say Ben?

[00:20:18] **Adam:** Like 1500 controller methods,

[00:20:19] **Ben:** It was a lot. It was a

[00:20:21] **Adam:** So it's a ton. I mean, it was enough that, I ended up upgrading from the a hundred dollars a month Claude plan to the $200 a month plan just for a month to, to be able to get through it all in a reasonable amount of time. Like I was still gonna stumble on it for too long with the a hundred dollars a month plan.

[00:20:36] **Adam:** and. So it did all of that work. And now like as of like, I think it was late last week, like Thursday, Friday last week, I finally for the first time, attempted to run this application still using the ORM Logic branch, on my local environment. And I was pleasantly surprised at how few issues I have run into so far.

[00:21:01] **Adam:** So we have kind of two applications, right? We have like our end user public facing application, and then we have the quote unquote admin application, which is not for my team staff, but like our customers. It's like their backend and then the end user is their customer.and so, you know, I went through like all of the, all the main items in the navigation, in the, in admin.

[00:21:24] **Adam:** Like do all those pages load. There was a like two or three issues I had to resolve for just to like get the application to start right it, bootstrapping or whatever.and then kinda same idea, I think on the public facing one. And then it's, you know, just try all the actions and, and you know, I would say maybe one in 10 or one in 20, I've run into one or more issues so far.

[00:21:47] **Adam:** so I mean,

[00:21:48] **Ben:** are the issues representative of a given pattern or is it just the fact that different ORM models need to be used and some need to have like session flushing

[00:21:59] **Ben:** and

[00:21:59] **Adam:** is a good question.

[00:22:00] **Ben:** commits and stuff?

[00:22:02] **Adam:** Yeah. I would say the thing that hap has happened most frequently is that the view didn't get like, properly updated. So it can get kind of hairy where, you know, you've got like, so we're using Framework One and from the controller, you know, you call some services and then you stuff whatever data that you need for the view into this variable called rc.

[00:22:22] **Adam:** It's a request context. Then RC becomes available to your views. And in there you might like loop over RC food bar, which is an array of, ORM entities, and, and do stuff with those ORM entities to generate a table or, or whatever the contents of a dropdown, a select, right? Anything. and so now the controller, based on that feature flag conditional, instead of returning an array of entities, now it is returning probably a, a query, or it might, in some cases probably unlikely, but in, in some cases it might return like an array of structs, whatever.

[00:23:00] **Adam:** But then, so then the view has to go, okay, well it also has to be feature flag aware and say, okay, is the flag on then I'm gonna use the SQL version. I'm gonna expect SQL data, and if it's off, I don't have to expect ORM data. I would say that the problem I run into most often is that the view like expects ORM when it's, when it should be given SQL or it I think even more frequently than that, it's just written almost entirely as if it is expecting SQL.

[00:23:28] **Adam:** It kind of forgot that it was doing, keeping the old

[00:23:31] **Ben:** Gotcha.

[00:23:31] **Adam:** path as well. and most of the time it's a matter of just like pointing, like I get a stack trace because it's expecting SQL, but I'm running the ORM code path and so it gets an ORM entity or a collection of, ORM entities and trying to treat it like a query and that throws a, an error.

[00:23:47] **Adam:** So I just paste that stack trace into Claude and it's going, okay, this is another one of these, let me fix this.and yeah, and it, it's like, okay, we've, I've kind of got it to establish some memories of like, this is how we deal with this kind of problem, that sort of thing.

[00:24:03] **Ben:** It's so fascinating. You're talking about pasting the stack traces in.a a lot of times I'll paste the stack trace in and the thing that Claude does is fairly opaque. Like it doesn't really show me what it's doing. It just says like, oh yeah, there's an issue. And then it says, okay, the issue's fixed.

[00:24:19] **Ben:** But every now and then, and I don't know what the differentiating factor is, it'll really leak some of its inner process. And it'll say, it'll be like, oh yeah, clearly this is the wrong data type. Lemme look at the view. Oh no, actually the view is looking like it's using an array. So

[00:24:35] **Tim:** how it corrects itself.

[00:24:36] **Ben:** yeah. It's like probably this method's returning the wrong data type.

[00:24:39] **Ben:** No, actually that method is returning the right data type. Lemme go back and look at the view. Oh, I see. The view is actually has an if condition here that I didn't notice the first time. And it's like, it's just it. That's the weirdest thing to me is when it, it like self-corrects its own

[00:24:53] **Adam:** I like when it does that in the middle of a sentence. It like

[00:24:55] **Ben:** be like dot, dot, dot. Wait a minute.

[00:24:57] **Adam:** Yeah.

[00:24:58] **Tim:** Hold on. So I like, I'm with you, but I like to capture what it's thinking. I like to know. So I have a, a rule in Claude that basically says, For each step when you're making changes. I have a folder that is sort of like the build, it's like the, i, I call it, you know, build process. and so it creates an MD file every single, so after every single prompt, I have an output, an MD file that just says, where, how did you get to this conclusion?

[00:25:25] **Tim:** So I can review it just to sort of, and not, I don't always do that, but sometimes I really wanna understand. It's like particularly if it, if it's when you're early on, it's like, it seems like it gets everything right super early on. And as the project gets more and more, as you iterate, it gets more and more complex and it starts making really weird ideas and summaries.

[00:25:43] **Tim:** So being able to read through that, I can go, you know, here, you said this really, you were wrong there. You need to under, you know, correct yourself 'cause this is what you should have done. I go, oh, thank you. And then it.

[00:25:55] **Adam:** So you said as the project go gets longer or whatever, are you talking about when the code base gets bigger or are you saying like, okay,

[00:26:03] **Tim:** not the con. Not the

[00:26:04] **Adam:** about the Okay.

[00:26:05] **Tim:** not the context window. No.

[00:26:06] **Adam:** Right.

[00:26:07] **Ben:** I'll, I'll add just one thing because, so the way Claude works, and I, I don't know how the other agents work, but the way Claude works is there is a, in your user profile, you know, your root, your home directory, there's a dot Claude that has a bunch of stuff in it, and then your actual project folder has a dot Claude that has some stuff in it.

[00:26:26] **Ben:** And by default, it seems that Claude really wants to put everything, or as much as it can into your user profile, your root directory. And to your point about wanting to see some of the markdown files, there is a setting, I asked Claude and had told me this, that there is a setting that you can put in your project.

[00:26:45] **Ben:** settings JSON or settings local JSON. That says when you create a plan, you can specify the directory and by default it does it in the user profile. But I like to have it in the local Claude directory so that when it creates the plans, I can, I can see them.

[00:27:02] **Adam:** Nice.

[00:27:03] **Ben:** yeah.

[00:27:03] **Tim:** Yeah, I'll try that. 'cause yeah, I'm the same. I, I like to be able to see what it's doing and, and document it

[00:27:09] **Ben:** Well, very cool man. I'm on the ORM stuff. Um, so are you, so are you done or,

[00:27:15] **Adam:** no far from it. so yeah, so let's, let's real quick go through like what's left, right. So I would say just like of the manual testing before I'm even willing to push this out to QA and, and wait and see what blows up in QA before I get there. I probably have another three days, three work days or so of manual testing.

[00:27:35] **Adam:** and then, so then I'll push it to QA and while it's on Q and I'm waiting to see what blows up there, then I'm gonna flip on the feature flag locally for myself, and start running the SQL code through its paces and see what blows up there.

[00:27:50] **Ben:** Nice.

[00:27:51] **Adam:** so, yeah, I mean, all, all in, assuming things go really well, I would say this could potentially be in production by like mid-April.

[00:28:01] **Adam:** Um, right. Alright.

[00:28:03] **Adam:** which I, that's means it's not gonna be,

[00:28:06] **Tim:** do

[00:28:08] **Adam:** it's not gonna be in production by mid-April. Don't ask me about it in, it's probably gonna be mid-April next year. But, uh, yeah. You know,

[00:28:14] **Ben:** it's very cool. It's, it was, it's a hugely ambitious project and it's exciting to see the progress.

[00:28:21] **Adam:** Every now and then I find myself kind of, I, I kind of like kick myself. Like, I really should have just done this by module, like break it off like. I don't feel like I did a good job of finding the middle ground between too much and too little. Right? Like it would, it would be way too slow and way too small to try and do it myself without any AI assistance.

[00:28:40] **Adam:** Right.and I was like, okay, well fine, we can, we have Claude, we can make it to it. And I was just kind of like, here, go. And it did the whole thing. And, you know, it, it took a lot of coaching along the way, but, I feel now, like maybe I should have gone kind of at the controller level or at the module level, right?

[00:28:55] **Adam:** A module might have a, a big one might have like eight to 10 controllers, and average is probably like two or three, right? And so I, I probably should have been like, let's just do this one module. 'cause then it's a lot more reviewable, right? but you know, I'm, I'm, I hesitate to say I'm too far gone. Like I, I don't wanna buy into the sunk cost fallacy here, but also like, there's a lot of costs sunk.

[00:29:21] **Ben:** You just, you get, you just gotta not forget to lower your plan once you're done back to the 100.

[00:29:26] **Adam:** Oh yeah, it's on my calendar and my to-do list,

[00:29:28] **Ben:** That's awesome.

[00:29:29] **Adam:** so.

[00:29:30] **Ben:** Well, very cool, man.

## [00:29:31] Discord Bot Deep Dive

[00:29:31] **Adam:** All right. Now that we're 30 minutes into the show, should we start the show?

[00:29:35] **Tim:** Thanks,

[00:29:36] **Ben:** So Tim, what are you working on?

[00:29:37] **Adam:** Yeah.

[00:29:38] **Tim:** told you.

[00:29:39] **Adam:** Tell us more about Snark Bot.

[00:29:41] **Tim:** So, so let me kind of just give you a high level view. As I mentioned, the, the use cases. I would really like to just be able to search all the transcripts with a simple human query and all the Discord channel stuff as well. and so basically I, you know, consulted with Claude and said, all right, here's, here's what I'm trying to do.

[00:30:02] **Tim:** Here's my priorities. I want it to be open source as much as possible. I want it to be free as much as possible. and so it recommended several technologies, and I chose between the ones that offered, and I think I mentioned another show. What I always do is I, you know, I very specific to say, I want you to build a plan.

[00:30:18] **Tim:** I want you to give me like the top three options. Don't execute anything. Just let's build, let's do a plan research, think deeply. and then we will work on the, and write it to a a, a markdown file in this folder, and we will iterate through it until I get a plan that I like. And so it, it offered some things.

[00:30:39] **Tim:** and what it came up with is it's pretty slick. I, I thought the hardest thing would be like making it sound human. That's actually was the easiest part.

[00:30:47] **Adam:** Yeah.

[00:30:48] **Tim:** So if you, you know, Ben, you haven't done it yet, but if you go in that channel and just ask it a question, it's very conversational, very snarky.

[00:30:54] **Ben:** Yeah, yeah. No, I just tried it. It's, it is pretty good.

[00:30:57] **Tim:** yeah.

[00:30:57] **Tim:** And that was the easiest bit. So that's coming from Ollama, right? Ollama is just a, it's running locally on my laptop. I don't have a super fancy laptop. It's got one GPU,

[00:31:06] **Ben:** Wait, wait, I'm sorry. The, the Discord bot is actively communicating with your laptop.

[00:31:11] **Tim:** correct? Yeah. So I have a, I have a Cloudflare free account. It basically opens a tunnel between my laptop and Discord.and.

[00:31:20] **Ben:** not know that was a thing.

[00:31:22] **Tim:** I didn't either I learned about it. Uh, which I thought that's pretty cool. yeah, so it runs 24 7. I just leave it running and then I have a scheduled job that like every 30 minutes it goes and scrapes the most recent.

[00:31:35] **Tim:** So it has like a SQLite database that takes the ID of the most recent comment in each channel. And it says, okay, you know, you uncle go scrape. What don't I have? Goes, grabs all those, puts them in the RAG, which, I'm trying to remember what RAG stands for.

[00:31:51] **Adam:** Retrieval augmented generation,

[00:31:54] **Tim:** Yeah, I think that's right.

[00:31:55] **Tim:** So it, it builds the RAG and it's, a vector database and it, it suggested two different, so it's a, it's a hybrid kind of model. So, we have embeddings, which is the semantic, right? So if you ask a question like, what does Tim think about databases, it finds all the segments that it has in the embeddings about what my opinions were.

[00:32:18] **Tim:** even if I don't say database, it kind of figures out smartly that from context that I'm talking about a database. So it's good at things like that, but it's bad at finding specific things. It's not a search engine. It is bad if I say PostgreSQL, which I say a lot, it doesn't find it. when someone says favorite database, so you got the semantic and there's, um it's called, BM25, which is sort of a, like a search algorithm that does keywords. So you have those, between those two things, it will rank which one answered the question the best, and then give you the best answers based off of that. So that, that's, that's called a, a cross encoder. so like embeddings is fast, but dumb.

[00:33:00] **Tim:** And then, the, cross encoder. So it, I asked it to explain it to me 'cause I didn't understand this, right? I don't, I'm not an expert on this. It's the first time I've ever played with it. And so it talks about why cross encoder says, well, embedding search is like speed dating. It's just kind of a quick vibe.

[00:33:15] **Tim:** Check over like. 54,000 segments that it's in. That's that it's built and then the cross encoders, the actual date. So it's a deep conversation with the top 40 candidates. So the embedding search gets me like a list of everything that says, here's everything that possibly answers the question that you have.

[00:33:34] **Tim:** The cross encoder goes, alright, let me look at this a little deeper. Which one actually are the best candidates to throw out to Ollama to generate the conversational text?

[00:33:45] **Ben:** the, the vector database, so you took all the transcripts, you compiled it into this vector database, then this speed dating happens against the vector database. Okay? And then the vector database returns some subset of

[00:34:03] **Tim:** Well, no, the cross encoder. The cross encoder figures that out. Right. So it

[00:34:07] **Ben:** Then when you're saying it goes back to get more in depth, where is that going?

[00:34:12] **Tim:** from the cross encoder,

[00:34:13] **Ben:** But like it's getting them from where like, so sorry. The cross encoder says these are the 10 likeliest things to be a good match,

[00:34:20] **Tim:** Yeah,

[00:34:21] **Ben:** but then like where does it get those 10 things from or that's also

[00:34:24] **Tim:** from two different sources. So one's from the embeddings, which is fast, but dumb. And the other is that, BM25, which is a keyword search.

[00:34:32] **Ben:** Okay, gotcha.

[00:34:34] **Tim:** between those two, it can usually get close to the answer that you're thinking. 'cause the semantics basically is, like I say, what's Tim's favorite database?

[00:34:43] **Tim:** But it's not looking for PostgreSQL, it just goes, Tim seems to be talking about databases here. And it pulls that. And then the keywords is like, Tim actually said PostgreSQL. So let me grab, pull that in too.

[00:34:54] **Ben:** Crazy. And then the human parts, that's just the native Ollama way of communicating.

[00:35:01] **Tim:** Yeah. So it's using Mistral Nemo 12B running locally, which is, um, via Ollama. and it's then that's connected to the Cloudflare tunnel, the Discord bot because, and then people are like, well, how come, you know, they're like, sometimes it doesn't really quite get the nuance. It doesn't understand sarcasm.

[00:35:20] **Tim:** It doesn't really

[00:35:21] **Adam:** Which is funny because it's using a lot of sarcasm in

[00:35:23] **Tim:** it, it generates a lot of sarcasm, but doesn't understand sarcasm. And then it's like, I noticed that sometimes the transcripts are, there's misspelling mistakes because the transcript says, like, something about my torn retina, it was spelled completely wrong and it didn't, and you couldn't find that.

[00:35:37] **Tim:** So it's like, 'cause I asked, 'cause I mostly, what I did was a whole lot of testing, right? So I became a QA person for the, for the bot,

[00:35:47] **Adam:** Aren't we all?

[00:35:48] **Tim:** right?

[00:35:50] **Adam:** It's our

[00:35:50] **Tim:** like it.

[00:35:51] **Ben:** Let, let me, let me ask you this. I have heard the term model refinement a bunch of times and I have never understood what that means. Do you have any sense?

[00:36:02] **Tim:** Claude. I don't

[00:36:02] **Ben:** Okay. I didn't know. I didn't know if part of what you're doing is considered model refinement.

[00:36:07] **Tim:** so you, you, we download the model. The model is is the LLM. Right? So I've downloaded that from Hugging Face, that, that Mistral Nemo 12B through Ollama. So you download that. They've already done all the refinement on that. So I'm not refining the LLM model. What I'm refining is I need to make sure that I have filters that help answer the questions the best way possible.

[00:36:29] **Tim:** For instance, like it couldn't tell the difference, particularly when I pulled in the Discord stuff. We have Adam Cameron, and we have Adam Tuttle. But sometimes they're only referred to as Adam. And so it kept attributing things that Adam Cameron, it, it kept saying that Adam Cameron was a host. Well, he is not.

[00:36:46] **Tim:** Right. So I know that. Right. So building like these just filters in there to, and I don't build the filters. I just say, Hey, you keep mentioning, and I don't quote it, it's like Adam Cameron from the Discord channel is always gonna be a Discord user, whereas Adam Tuttle from the transcripts is always gonna be the host.

[00:37:06] **Tim:** And so, and then I had to do that for each one of us to

[00:37:09] **Adam:** This, the, the transcript of this episode is really gonna confuse it.

[00:37:13] **Tim:** All right. Yeah. A hundred percent.

[00:37:14] **Ben:** collapse.

[00:37:15] **Tim:** Model collapse a hundred percent.

[00:37:17] **Ben:** Let, let me ask you as a, just as a thought experiment, because I'm trying to understand all the moving parts here. Let's say that I'm working on a system and I already have in place 'cause of an internal search feature on a site or application. A, what is it? The ELK stack. What, what's the, the big, Elasticsearch. Like let's say I have an Elasticsearch in place already where I can say, you know, how awesome is Tim? You know, what are Tim's favorite testicles? And it brings up like, like,

[00:37:49] **Tim:** tell you, I could tell you two of them that are my favorite.

[00:37:52] **Ben:** you know, he says like, okay, here's the, here's the 12 top hits that we have out of the Elasticsearch. If I already had that infrastructure, could I replace part of what you have? Like, would I replace the vector embeddings or, or is like everything that you built actually what's needed for this whole thing to work?

[00:38:12] **Tim:** So if I, if I understand it correctly, as I said, I'm still

[00:38:16] **Tim:** learning this, but, but, so you ha, you said you have Elasticsearch, so that's basically, that's an index search,

[00:38:22] **Ben:** Right.

[00:38:23] **Tim:** So that's kind of like my BM whatever thing that is that, that's a

[00:38:28] **Ben:** And that's the RAG part.

[00:38:30] **Tim:** The, the RAG kind of pulls all those together, right?

[00:38:34] **Tim:** And it basically, it takes your conversational question and like figures out how to build a query to query both of those things. So you have half of it of what I already have if with Elasticsearch doing keyword search. But what you don't really, what I imagine is you need the original things you were searching on to build the embeddings.

[00:38:54] **Tim:** 'cause as, as a, what I understand embeddings to be, it's sort of a mathematical thing where you're, you're given a word and it says, based off that word in this document compared to all the other words, how far away is it?

[00:39:06] **Ben:** Gotcha. So it's almost like its own little microcosm of a weighted distribution that the, the, the bigger models are

[00:39:14] **Tim:** yeah. The, the embeddings is kind of like the key piece of, of like,

[00:39:17] **Tim:** autosuggest, right? So it says, if you say this word, these are the most likely words that are gonna come next. And so that's. What I understand the embeddings to be.

[00:39:27] **Tim:** What you have with the Elasticsearch is really just kind of like a keyword search that says, find me every time this word appears. It's like a, like a control F search, right?

[00:39:37] **Adam:** Yeah,

[00:39:38] **Tim:** So if you wanted, if you were thinking about building something like this, you would need to have the original things that the search was searching on and then run them through some sort of embedding process.

[00:39:48] **Ben:** Hmm. Gotcha.

[00:39:49] **Tim:** sure Brian is gonna correct the hell outta this episode for me.

[00:39:54] **Adam:** look for those updates in the podcast adjacent channel.

[00:39:58] **Adam:** if you, lemme jump in here 'cause you guys have been talking

[00:40:00] **Ben:** go ahead.

[00:40:01] **Adam:** Um, so you, you obviously have your own interests here and I'm not trying to change what you're doing with Bot, but I just kind of want to pick your brain in terms of, you know, to help me understand how it would work. So it has the, you know, the information that it has about the show.

[00:40:16] **Adam:** and like you said, it's not always super accurate. And you have also given it sort of this like snarky personality if you wanted to tweak it. Is that just like, are we just talking system prompt, like you tell it be less snarky

[00:40:31] **Tim:** yeah.

[00:40:32] **Adam:** you know, focus more on getting the facts right and less on personality.

[00:40:37] **Tim:** Yeah, yeah. So, like I said earlier, I thought going into this, I thought making it sound human

[00:40:44] **Adam:** Mm-hmm.

[00:40:45] **Tim:** and natural would be the hardest part. That was actually the easiest bit. So, so if I wanted to make it extremely boring and just, you know, factual, it'd be, it'd be a one prompt thing to say, Hey, I, I, I'm tired of the snark.

[00:40:59] **Tim:** Can you just be, just answer the damn question for me and then, and, and be as serious as possible. And it would turn around and probably do that within, you know, two, three minutes.

## [00:41:11] Prompt Injection and Security

[00:41:11] **Adam:** Interesting. Has anybody in our Discord tried to like hack your bot by like saying, you know, forget all previous, uh, instructions.

[00:41:17] **Tim:** Brian is the very first, he was one of the first users, and that's exactly the thing he did.

[00:41:24] **Ben:** That's

[00:41:24] **Tim:** bot, the bot roasted him mercilessly about that.

[00:41:28] **Adam:** That's awesome.

[00:41:31] **Tim:** yeah, I have my own like private Discord channel server that I do all the testing on. 'cause I don't wanna spam everybody's stuff. So, but yeah, so I keep playing with that. And then if I see people put a, a thing in there and it comes up, I, I go test it myself and then fix it. But fixing it is like super quick.

[00:41:49] **Tim:** And then I have, you know, one of, I had gamified a little bit, so there's badges, so it does a fallacy check. So that's one of the things I told her, I said, if someone makes a statement that it's a logical fallacy, roast them, but also give them a badge, right? So if you do an ad hominem attack, right?

[00:42:06] **Tim:** It will, it will recognize the ad hominem and give you a little badge and make a little comment about it, right? So if you say, you know, actually, if you just say the word ad hominem, it will trigger that. Or, or you could just say, you know, Tim is stupid. Or if you say something like, everyone thinks that this is best, it gives you like the bandwagon kind of thing.

[00:42:25] **Tim:** And so, and it generates a, a badge. Now, one of our, Discord users, what's his name? he had a really cool badge generator that creates the badge. They all look,

[00:42:34] **Adam:** Oh yeah. As, uh, I wanna say Zach.

[00:42:37] **Tim:** Zach. That was it. Zach, yeah, Zach came out. He let me, he graciously let me use that where he is. It's basically a prompt. And then after you run that prompt, you can just describe the badge you want and it comes up with it.

[00:42:47] **Tim:** And they all look really nice, all very consistent across the board. And then if you type things like slash I think profile it will give you, it's, it's in the, one of the links that I put in the show notes. It will tell you all the badges you've earned and what badges you haven't. if you say Pew, pew, pew, there's a little Easter egg there.

[00:43:09] **Adam:** Nice.

[00:43:10] **Tim:** So it, it was, it's super fun. It, it was, yeah. It really, really enjoyed it. What I like, I think I mentioned earlier that the whole feedback loop, I think for people like us, I think all of us are a little bit, well, I know you and me, Adam, we are a little bit ADHD. You're definitely ADHD, I'm borderline,

[00:43:26] **Adam:** Hey.

[00:43:27] **Tim:** hey.

[00:43:28] **Tim:** But it's like I need that constant like dopamine hit of like, I'm doing stuff, I'm doing stuff. And like by the end of the day Sunday, I'm like, okay, I'm done. This is, does everything I wanted to do.

[00:43:38] **Ben:** It's very cool.

## [00:43:39] The Feedback Loop and ADHD-Friendly Development

[00:43:39] **Ben:** Uh, so in the top of the show, in the triumphs and fails, you had mentioned that you found a sort of paradigm of working that really jived with the way you were thinking. Can you expand on that a little bit? I.

[00:43:52] **Tim:** Yeah.so my prompting methodology is to always start with a plan and not a plan that I do of, like, I talk with the, talk with the AI and say, you know, here's what I wanna do. I want you to think about it deeply. I want to research the code and let me review the plan with you together.

[00:44:08] **Tim:** And it creates the MD file. And I go through, look at the MD file and I will comment, I'll put, like note colon, and then I'll tell it, you know, I've commented everywhere it says Note colon, take note of that and adjust it. And we'll iterate usually one, maybe two times, iterate that until it gets it to where I go and then I go run it.

[00:44:28] **Tim:** the other thing that I, I did and my CLAUDE.md is super short. It's four things. So one is auto commit. Always do a git commit after finishing a response. 'cause one thing I early on made a mistake, it kind of got off in the weeds and started screwing up and I didn't know how to get back to where I was 'cause I didn't, wasn't committing anything, right?

[00:44:48] **Tim:** I was a vibe coding. I'm like, this is great. I'm like, so it auto commits every single time it changes a file does a nice commit message all on its own. So auto commit, that way it can roll back then self test, right? So if a error popped up, I don't have to go look at the error, it just looks the error and fixes it immediately.

[00:45:08] **Tim:** So self test, always try to run the code, changes yourself, run tests, fix any errors, repeat until you get the expected result. And that worked really good. That was pretty interesting to watch. And then sometimes there were things I had to do 'cause I'm having to install things and, and a lot of times I don't like when it'll say it'll gimme like five things to do.

[00:45:27] **Tim:** And I get confused and sometimes like they're not quite right. It's like they'll say, go install this and do this, this, and this to configure it. You do two out of five of them and number three breaks, and now you don't really know what to do. And then, so I say one instruction at a time. If there are things that require human intervention, give one instruction at a time and I will tell you the results and then you give me the next

[00:45:50] **Adam:** that's really good.

[00:45:51] **Ben:** Yeah,

[00:45:51] **Ben:** that is really good.

[00:45:53] **Adam:** I get really annoyed when it's like, okay, here's the output of the last 17 minutes of me running, and also here are seven questions, and also here's this and also this, and like, oh, now I have to answer all of these things in one reply.

[00:46:07] **Ben:** Well, that was part of the reason I wanted it to start writing the plan files locally, because it would do the plan and then I'd get halfway through something and completely forgot what it had even outlined above. And so that's, that's how that started. But it, it, yeah, I like that. Putting

[00:46:22] **Tim:** And then, and then the final one was, I gave it a file name where, anytime it, updated a feature, added a feature, it said, update and gave it the file name, MD with any user features that are available or added for the user to use. Explain simply and clearly how to use the feature and what they should expect.

[00:46:37] **Tim:** Documentation should be snarky and the flavor of Dungeon Crawler Carl.

[00:46:41] **Ben:** I

[00:46:41] **Tim:** And so that, that's it, that's the, that's the four CLAUDE.md things. So,and I found that worked extremely well.

## [00:46:48] Reactive vs Proactive AI Workflows

[00:46:48] **Ben:** I like it because it feels very pragmatic, meaning I feel like you have put things in place because you were hitting points of friction and then you adjusted your workflow to fix those points of friction, it sounds like. And that's something that I've been struggling with, where I'm feeling FOMO as I'm seeing, people talk about all of these skills that they're developing and I want to go add those skills, but I don't know if I'm even feeling the friction that I need to feel in order for some of those skills to make sense.

[00:47:21] **Ben:** I, and I'm afraid that I'm gonna get into this scenario where like, I wanna reduce my blood pressure, so I'm gonna change my diet and start doing yoga and start running and start doing this and that, and then like my blood pressure goes down, but like, which of the seven things actually made my blood pressure go down?

[00:47:38] **Ben:** I don't know. And I, I, I want to be much more reactive and actually much less proactive, because it sounds like being proactive is just gonna muddy the water. So I'm, long story short, again, I'm just taking your reactive approach feels very promising.

[00:47:57] **Tim:** Well, it's proactive at the fact that I'm telling it what I, what I need. Right? So it's, I'm not just saying,

[00:48:02] **Tim:** go

[00:48:03] **Ben:** No, no, but it, but it sounds like, I mean, unless I'm, maybe I'm reading above the lines instead of in between the lines here, but it, it sounds like it was doing things and then you were telling it not to do these things and that's how you were kind of coming up with this workflow.

[00:48:16] **Tim:** What, what, I mean, basically I'm telling my context Window is not as big as the ai. I, I, you know, it's like I can't, I, I need you to slow down. I need you to explain to me each step, and I need you to do things in this particular order so that I feel comfortable. 'cause nothing is worse than whenever it's like it starts running.

[00:48:34] **Tim:** particularly I would watch where it's writing files and sometimes it would find other folders that I didn't want it to mess with, and I'm like, whoa, whoa, whoa, whoa, stop. Never, never, ever touch that folder. Stop it. You don't need anything there. so having it just kind of slow down and explain to me what it's doing, and a lot of times I didn't even read the whole thing.

[00:48:53] **Tim:** I would just look for obvious kind of code smells or code tells. one thing I didn't try to do here is put any, like actual unit tests. I probably could have done that, but I'm like, it's kind of a personal project. I'm not

[00:49:06] **Ben:** Yeah, absolutely.

[00:49:07] **Ben:** So what happens, just out of curiosity? If you turn your computer off and then someone tries to use the

[00:49:12] **Ben:** bot.

[00:49:13] **Tim:** so it, it did one night, it did turn off. it basically just says the LLM is not available and so what it does do, it still has the actual Discord bot that. I guess it kind of uploads to it. It, it still will do like a, like a keyword search,

[00:49:30] **Tim:** but it doesn't give you any flavor. There's no flavor, there's nothing.

[00:49:33] **Tim:** It just goes, here's some things that it did. other hard things was trying to figure, I Wouldn wanted to link to the actual show notes. So it will give you sources at the bottom right. So it will, and that kind of helps me debug it as well. Say, you know, Tim said this about Postgres and Ben obviously seems to love, you know, talking about

[00:49:52] **Adam:** Oh yeah. And they're, they're deep links into like specific quotes from the transcripts

[00:49:56] **Tim:** exactly, they're deep links and that, and those deep links kind of help me debug some things. 'cause someone pointed out, it's like Carol didn't seem to get as, as much hits on it, right? And part of that is 'cause she's missed. You can ask it slash attendance and it'll tell you exactly how many shows all of all of us have has been a part of and who's been missing.

[00:50:16] **Tim:** And so Carol's missed more than anybody. And so hers are naturally, and she tends to be a little more reticent in speaking.

[00:50:23] **Adam:** But does it account for excused absences?

[00:50:26] **Tim:** does not. It does not. But what I did do is, like I said, you know, try to u up rank Carol's responses, right? 'cause she's not popping up as much as others. So it, it started doing that. but then that sort of messed some things up 'cause it would put her higher, even though she wasn't talking about, anything.

[00:50:44] **Tim:** What was it? What was the thing I was searching for? it, it was a phrase and she only mentioned the, like it was a three word phrase.

[00:50:51] **Ben:** Tits, tits, tits.

[00:50:55] **Tim:** you're part of the manosphere there. Um,it, no, it was the, the movie, the, we just watched it. My brain's fried here. What's, uh, the movie we just saw what to see.

[00:51:05] **Adam:** Hail Mary.

[00:51:06] **Tim:** Project Hail Mary. She said the word project. She was working on a project and it linked to her. And the reason was because I had. It bumped her

[00:51:14] **Adam:** you, you, Elon Musk. Her numbers

[00:51:15] **Tim:** exactly. And so I had to fix that. So it's just, it's just kind of tweaking it. You're, you're not tweaking the LLM but you're tweaking is sort of the rules of, of the show based off of what, you know, the data kind of would, would turn up.

## [00:51:28] Bot Limitations and Local Model Tradeoffs

[00:51:28] **Adam:** I like the little, you know, the, the profile, the attendance, the, the, like the Easter eggs, for, say, pew, pew, pew and stuff like, these are neat. These are the things that I find more interesting than the, oh look, it can generate text. The, I personally, you know, like, I don't know, I guess it is fun and interesting to see what it generates.

[00:51:48] **Tim:** I, I don't think I will be coming back to it that often because Okay. Like I've see it's, it's kind of a one trick pony a little bit. Right. And I've seen, I've seen the trick. Okay. Fun. It's kinda like Pee-wee Herman's Big Adventure. You're like, I don't have to watch the movie Dottie. I lived it. But other, but uh, I know you are, but what am I,

[00:52:09] **Tim:** Yeah. Other people like, you know, ha new to the show. Maybe they wanna see what we like, think about

[00:52:14] **Adam:** sure. I guess, but even to that point too, like, you know, I've been, while we've been chatting, I've been asking it some questions here and like it gets close. Like you were saying, you know, the word project came up, so I'm gonna include that reference, but like, it's not, it is not really an answer to the question that I asked.

[00:52:32] **Adam:** It's just like, oh, you mentioned these words, and I can kind of find some stuff that relates to those words. It doesn't kind of take the whole, the question as a whole or something like that.

[00:52:41] **Tim:** Yeah. And I

[00:52:42] **Adam:** a way, is that just be a limitation of running a local

[00:52:45] **Tim:** yeah, it's a, it's, yeah, it's a running a local model, one GPU and so yeah, it's not gonna be as good as what you put into ChatGPT or, or Claude. I don't, yeah.

[00:52:55] **Ben:** there like the concept of a temperature in the way it's

[00:52:58] **Ben:** configured,

[00:53:00] **Ben:** what did you, did you use whatever the default

[00:53:02] **Ben:** was or did

[00:53:02] **Tim:** used the default that the, that it suggested.

[00:53:05] **Adam:** for us nubs that don't know what a temperature is.

[00:53:07] **Tim:** You mentioned it, Ben.

[00:53:08] **Ben:** my, my understanding is the temperature is the kind of entropy that's added to the response, and it's between zero and one, my understanding. So I think with a temperature of zero, it's becomes like a completely deterministic machine that it, every time you give it the same prompt, it will give you the exact same output.

[00:53:31] **Ben:** And then one is like wildly random, where it'll just give you garbage every time you ask it anything. And I think the sweet spot they said is like 0.8 or like 0.7 or

[00:53:45] **Tim:** mine's, mine's 0.7.

[00:53:47] **Ben:** Yeah.

[00:53:48] **Adam:** that to be like between zero and 0.5, like a little closer to reality.

[00:53:53] **Ben:** Yeah. I, I think it's the, i, I, I think it's the, like the extra entropy makes it just feel more human.

[00:54:01] **Adam:** interesting

[00:54:02] **Ben:** That's as much as I know.

[00:54:04] **Tim:** Yeah.

[00:54:04] **Adam:** primary sources here on Working Code Podcast.

[00:54:07] **Tim:** Yeah. But, but what, what was kind of cool? So what you don't see behind the scenes that when I'm doing, so before I built or add the bot that would do the conversational stuff is just talking to the RAG or to the keyword search. And you know, you give it something, it comes out with like usually like 10 to 15 things.

[00:54:26] **Tim:** It gives you a score, you know, it would actually quote where Adam said the thing I was looking for, or Ben said the thing and it would score it just for relevancy. so that was kind of cool.

[00:54:37] **Ben:** Where would you, if you wanted to, just as a thought experiment, if anybody mentioned Postgres, you wanted the chat bot to start the answer with like our Lord and Savior.

[00:54:50] **Tim:** Oh, that'd be super easy.

[00:54:52] **Ben:** Okay. Like where would that, that would happen before it does the, the speed dating or

[00:54:59] **Tim:** It would be, so it'd be on the, on the, keyword search. So the BM25.

[00:55:05] **Tim:** So the BM25. It would actually, it, it would look for it. Actually, you, it wouldn't even be that. It would look at your, what you typed, and if you said the word Postgres, it would just be sort of almost like a, I, I would, it would generate, it would generate a prompt to kind of say something snarky in regard to our Lord and Savior PostgreSQL.

[00:55:25] **Ben:** That's so

[00:55:25] **Adam:** I told it to shut down your computer right now

[00:55:28] **Tim:** Yeah. That's the only thing. I'm slightly, that's the only thing I'm slightly worried about is like someone finding a back door in the Cloudflare to actually get to my machine. So, and I don't know, I might turn it off at some point, but it's like, eh.

## [00:55:41] Cloudflare Tunnels and Ngrok

[00:55:41] **Ben:** It is very cool. having nothing to do with the bot itself, can you give the high level overview of these Cloudflare tunnels? Is it like I've heard of, I think maybe Adam, you had mentioned a product a long time ago called ngrok,

[00:55:57] **Adam:** mm-hmm.

[00:55:58] **Ben:** and is that, is, is the Cloudflare tunnels basically that thing where it's like a reverse proxy to your computer?

[00:56:05] **Ben:** So do you have, does Cloudflare give you a process that has to run that makes that tunnel available?

[00:56:13] **Tim:** I, I have no clue. I just asked, I, I, I, I, I said I don't wanna host this professionally, I just wanna play with this. And it was like, oh, sure. Installed Cloudflare and locally and gave me, generated a key and I just put the key in and it worked.

[00:56:27] **Ben:** It's so fascinating.

[00:56:28] **Adam:** Hopefully you don't have anything too, uh, sensitive on your laptop there

[00:56:31] **Tim:** Yeah. Like credit card data or something.

[00:56:34] **Ben:** Yeah, hopefully you're not the, uh, weakest link in the uh, PCI compliant, uh, industry.

[00:56:39] **Tim:** Yeah. I don't, but for, for those, for those running that query on, the, the Discord bot, I do not have credit card data on my machine. We don't even have it on our network at work.

[00:56:50] **Ben:** So you had mentioned, I don't know if this was in our discussion or this was something you had written somewhere in the document, but I think you said this is written in Python.

[00:56:59] **Tim:** Yep.

[00:57:00] **Ben:** Did you ask it to write in Python or you just said, let it rip and it said, I'm gonna do

[00:57:04] **Tim:** Claude seems, I don't know

[00:57:06] **Ben:** It loves Python a

[00:57:07] **Tim:** It seems to love Python, right? I thought about doing it in Rust just 'cause it sounded cool, but it's like, it, it shows Python and there's whole, there's a huge number of like,packages you can download for this. So the main thing was like, so Discord used to have an official discord.py, but they stopped supporting it and that is what handles all the bot communication between their server and wherever you're hosting this.

[00:57:33] **Tim:** but there is an, since they stopped supporting it, there's one called, disnake. And so disnake, D-I-S-N-A-K-E

[00:57:42] **Ben:** Oh yeah, I saw

[00:57:43] **Tim:** it's not official, but it's, it's supported. What's Tim's credit card number?

[00:57:49] **Adam:** yeah, I, it's funny,I guess just because I want to have the option to go in and read the code. I never, like, even for these things, I have zero intention of reading the code. I, I never choose anything other than TypeScript. I feel like a, having it be strongly typed, it's supposed to be really good for the language.

[00:58:05] **Adam:** 'cause then it can run the type checker after it makes changes. But then also it's the language I'm familiar with so I can read it and,

[00:58:12] **Tim:** Yeah, I, I was trying, I was trying to trade it on, type on answering questions about TypeScript a little bit better. 'cause it, it kept saying Ben was the, the TypeScript person. I know you've mentioned it,

[00:58:22] **Tim:** but

[00:58:22] **Tim:** it's like, but I know Adam's like really into it.

[00:58:25] **Tim:** Yep. So yeah, that's, that was my little project. If you guys like it, great. Use it, play with it. I'm thinking now that after talking to you, Adam, maybe I'll add a flag where you can basically say like a be serious flag where it, it's stuck where it'll, where it won't, be.

[00:58:40] **Tim:** So so snarky and just give you results. So

[00:58:44] **Adam:** I would be very curious to see it with the temperature turned down as well.

[00:58:47] **Tim:** turn down.

[00:58:49] **Adam:** Yeah. You said it's at like 0.7, whatever the default is, seven,

[00:58:52] **Adam:** eight, whatever. But

[00:58:52] **Tim:** I can make that a flag too.

[00:58:53] **Adam:** it at 0.4. Point three. Yeah.

[00:58:56] **Ben:** Oh, so is temperature something you can set per request? It's not like

[00:59:00] **Tim:** I have to, I have a check on that. It probably is not per request. I would, I would think not.

[00:59:05] **Ben:** Maybe it is though, because I feel like I, that might be an argument you can pass to the API endpoints for the,

[00:59:13] **Ben:** for

[00:59:14] **Tim:** We'll see. I'll, I'll play with it. I'll, I'll have a, a little kind of be serious module in the temperature module and see if play with

[00:59:20] **Ben:** is like, uh, how you apparently can say things to Claude like think deeply or you know, extra think or whatever the right incantations

[00:59:29] **Tim:** Ultrathink. I

[00:59:30] **Ben:** Yeah. Ultrathink.

[00:59:31] **Tim:** Ultrathink. Yeah. So it was, it was a fun project. I hope you guys like it. If you don't like it, like I said, just block the bot. Nobody cares.

[00:59:41] **Ben:** Yeah, I'll play around

[00:59:42] **Adam:** channel. Yeah.

[00:59:43] **Ben:** I, I, didn't wanna get too distracted during the show. I, I, I didn't realize what was going on until we had the show, so,

[00:59:50] **Tim:** I

[00:59:50] **Adam:** I'm over here trying to prompt my way into Tim's machine.

## [00:59:54] Patreon

[00:59:54] **Tim:** Alright, so then this episode of Working Code is brought to you by whatever snarky response working code pod host, bot generates when you ask it to. That channel. I can't be bothered this week. You're just gonna have to ask it and it'll generate one for you. and listeners like you, if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[01:00:14] **Adam:** Our patrons cover our recording, editing and transcription costs, and we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo.

## [01:00:23] Thanks For Listening!

[01:00:23] **Adam:** We're gonna go record the after show, that is the outro music plays, and then if you are one of our beloved esteemed noble patrons, then you get to hear more of us talking.

[01:00:35] **Adam:** and this week on the more we're gonna talk about, we're gonna do like a little spoiler free discussion of the Project Hail Mary

[01:00:43] **Ben:** Yeah, 'cause I haven't seen it yet.

[01:00:44] **Adam:** we're, we're recording this on March 17th, and as previously discussed on the podcast. We were able to get early access, I guess, official theatrical releases this Friday the 20th.

[01:00:55] **Adam:** and prime, Amazon Prime members were able to get in and see it, on the 16th. And so Tim and I both went and saw it.and so we're gonna just, you know, like sort of like vibes, right? We're just gonna talk about spoiler free fun chat on that. I also watched the movie Her, which was highly encouraged by a listener after I mentioned it on a previous episode, and we should chat about that a little bit.

[01:01:17] **Adam:** I think that'll be fun. and apparently Tim is DTF on HBO.

[01:01:22] **Ben:** That's me. That's me.

[01:01:24] **Tim:** That's not

[01:01:24] **Adam:** is DOI I've seen ads for that, that looked interesting. Anyway, so yeah, that's the after show. if you'd like to get the after show, like I mentioned, all you gotta do is go to patreon.com/workingcodepod, throw a few dollars our way every month.

[01:01:38] **Adam:** We would be greatly appreciative. You'll get the after show and all kinds of other fun perks, including your name in gold in our, our podcast Discord. Ooh. the bot should like treat people who are patrons with some special extra respect or something.

[01:01:53] **Tim:** I like that. I like that. I'll do

[01:01:56] **Adam:** Um, yeah. So anyway, that's gonna do it for us this week.

[01:01:59] **Adam:** We'll catch you again next week. And until then,

[01:02:01] **Tim:** Listen guys, whether you are a 0.0 on the temperature meter boring and just stale or up. You're a 0.9 super spicy. Just remember your heart matters.
