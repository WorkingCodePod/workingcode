---
title: "255: AI in the Streets"
description: "You spend all day steering AI through code. Then you step outside and it's steering everything else."
date: 2026-04-09
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/b98c8b29-f9a1-433a-95ce-4ae5cd6ccb5f"></script>
<div class="redcirclePlayer-b98c8b29-f9a1-433a-95ce-4ae5cd6ccb5f"></div>

You spend all day steering AI through code. Then you step outside and it's steering everything else. AI is listening to therapy sessions and suggesting treatments to your therapist. Your spouse is arguing with a chatbot about where Savannah, Georgia is. You call a company for help and get handed from one AI pretending to be human to another AI pretending to be human. The crew has been noticing it everywhere, and this week they compare notes on what it actually feels like when AI stops being a tool you chose and starts being a thing that just happens to you.

Links mentioned in the show:

- [hairstyles.net](https://hairstyles.net)
- [RunPee.com](https://runpee.com)

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Thursday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/255-ai-in-the-streets.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Cold Open

[00:00:00] **Ben:** If Claude is down, I don't know how the application works. I don't know the language that, you know, it's like, I don't know how to write Python. I don't know how to use CockroachDB.

[00:00:08] **Ben:** I don't know how to write React, but like, that's what's underpinning this application

## [00:00:31] Intro

[00:00:31] **Adam:** Okay. Here we go. It is show number 254. And on today's show, we admit it. AI is making us stupid and lazy. There I said it,not that I'm giving it up. You can't have it back. Uh, but first as usual, we'll start with the triumphs and fails. it looks like it's my turn to go first. Got the whole crew here tonight.

[00:00:47] **Adam:** So I got a, a whole bunch of triumphs and fails to get through tonight. So I'm gonna go with a nice, quick, easy one.

## [00:00:53] Adam's Triumph

[00:01:04] **Tim:** Uh, it's a nice triumph for me, and that is that I finally got my boss, my CEO to kind of maybe put down the, the AI curmudgeon hammer just a little bit. Steve. Steve, not a fan.

[00:01:06] **Adam:** no, I think he's, he's been a long time skeptic.

[00:01:10] **Adam:** you know, and very early on the, the. Non-coding use cases were very much like, we'll write your email for you, or something like that. Right? And, and when you get those things, you can see like right off the bat that they're not genuine from a human right. This is an LLM, spat out this, this content and that would be detrimental to the types of things that our customer, like the type of business uses that we would put it toward, generating text for stuff like that.

[00:01:38] **Adam:** So for that reason, he had kind of pushed it away for a while, refused to ever use like ChatGPT for his personal interests and stuff. and finally, so I mean, you know, months ago, I got him to buy into the team using the coding tools and we've been having some really good success with it. I don't think he was aware of how useful and how good the tooling have has gotten.

[00:02:01] **Adam:** And how the models have gotten. and so I've been working on this ORM migration stuff, right? I keep talking about it every week. If you don't know by now, where have you been?

[00:02:09] **Carol:** Catch up.

[00:02:10] **Adam:** yeah. so part of this process, like I, I did the ORM migration. Okay, great. And now, like phase two is have Claude review all the changes, right?

[00:02:19] **Adam:** It's reviewing my branch and I'm breaking it up into these vertical slices and re-reviewing and re-reviewing. It's, it's like rerunning the tests after you make a change. You just keep iterating until it gets it right, right. Um,making incremental improvements along the way. But in the process of doing the code code reviews for all of my ORM migration changes, it's also found a bunch, you know, let's say.

[00:02:41] **Adam:** More than 10, less than a hundred bugs in our existing code. part of the logic that I put into the code review prompt is to verify against main, right? So we're on a branch and it looks at my changes, and then it like, looks at the same file in the same section or the same functions on main to compare them and say, okay, well like the, the ORM fork of this, this function, should be I basically identical to main.

[00:03:06] **Adam:** And if it's not, then that's a bug and whatever. But like in the process, it's noticing all these other bugs that are, have nothing to do with the ORM migration, right? Like, oh, you got this thing. It's, I mean, there was some that were as simple as like instead of passing a variable to a function, somehow it got quoted.

[00:03:21] **Adam:** So instead of like passing arguments do id, it, it passes the string

[00:03:25] **Tim:** Oh wow.

[00:03:25] **Ben:** funny.

[00:03:27] **Adam:** It's like, okay, yeah, we definitely need to fix that. And I'm like.so you, you know, being the, the trying my best to follow best practices, right? Like, I don't wanna fix that in my branch. 'cause then it's gonna take forever to get to production and it kind of intermingles with my changes and stuff.

[00:03:42] **Adam:** So I'm like, okay, well that needs to go on its own branch. I'm just like so deep into this process now. I have been getting into worktrees. That's a whole separate thing. but I'm so deep into this process now. I'm like, I just, I I can't even think about that right now. So what I want you to do, Claude, is file a GitHub issue for it, right?

[00:03:57] **Adam:** Like just, I've got the GH CLI tool installed. Just use the GH CLI file a GitHub issue. Make sure you include all the relevant files and details and proposed fix and all that. Just go ahead, file an issue. And that's fine. And it's, I, I've put that into the automated part of my code review. So like, as I'm hunting for bugs, it's automatically filing GitHub issues for these things that it finds, which is great.

[00:04:19] **Adam:** And Steve has started to look at some of those issues and he's like, these are great, like bug reports. I wi he's like, I wish we had some interns or co-ops on, on hand to like, go through these and implement them. 'cause they're like, none of them is a big deal to implement, right? Like, take the arguments that I, ID should not be a string.

[00:04:36] **Adam:** It should be the variable. Okay, boom. Easy. That's five minute fix. and you know, he's, he's done some of those super low hanging ones just to, to, you know, if they're important and they're low hanging, why not? But, so I think he's finally starting to buy in. Like, oh actually this is getting pretty decent.

[00:04:52] **Adam:** and so he, I think he said, I forget his exact wording, but he said something on our, our all hands meeting yesterday that, he might actually have to start considering using it himself. Like, oh, okay.

[00:05:04] **Ben:** Oh,

[00:05:05] **Tim:** Slippery slope.

[00:05:06] **Adam:** Yep.

[00:05:07] **Adam:** As we will get into it is a slippery

[00:05:09] **Carol:** Mm-hmm.

[00:05:10] **Tim:** Yeah, for sure.

[00:05:11] **Carol:** Slight crack.

[00:05:12] **Tim:** Mm-hmm.

[00:05:13] **Ben:** much as the AI tools, I feel like have become pretty good for coding E, every time I hear someone talk about how they're using it to revolutionize the way they live life and they give examples, I'm constantly like, what? They're like, oh yeah. You know, I'm using OpenAI now, so it sends me a reminder to take my trash out on Tuesday nights.

[00:05:34] **Ben:** I'm like, literally, that's what the reminders app on your phone is for? Like, why are you OpenAI-ing the apps that

[00:05:41] **Tim:** Why are you giving root access to your life to.

[00:05:44] **Carol:** Pass.

[00:05:45] **Adam:** for sure. Totally agree. I, I think that there will, somebody will figure it out. There will be good use cases for that sort of life integration later, but they're not here yet. And,

[00:05:56] **Tim:** I, I want what they had in Star Trek where you just have a, you know, a thing that's in your house and you say computer

[00:06:03] **Adam:** Hmm.

[00:06:04] **Tim:** ask it a question and it does something for you.

[00:06:07] **Adam:** Yeah.

[00:06:08] **Carol:** mean like Siri?

[00:06:10] **Tim:** T Yeah. Siri, so annoying. I, I've gotten so used to ChatGPT and, and Claude, like coming up with good answers. I get so mad at

[00:06:18] **Carol:** Yes.

[00:06:19] **Tim:** and I was so excited when I got my new phone that you could like hook ChatGPT into Siri, but it, there's no way to control it, to, to use it, right?

[00:06:26] **Tim:** It's like occasionally it'll go using ChatGPT to answer this question. So.

[00:06:33] **Carol:** Ask me. It's like, do you wanna use the web or GPT.

[00:06:37] **Adam:** So. Alright, well that's all I got. Ben, what do you got going on man?

## [00:06:41] Ben's Fail

[00:06:41] **Ben:** I don't know how to articulate this one. I'm gonna call it a failure, and it's more like sometimes people say, oh, you are holding the tool wrong and. I'm beginning to wonder if maybe what it is is I just don't know how to hold the tool at all. and I know that doesn't make any sense. we, we've talked about how,

[00:07:01] **Tim:** We need context here. That's very

[00:07:02] **Ben:** right, so we've, we've talked about how with generative code that we have to be, or at least this is the, the, the mindset that we have to be less attached to the low level implementation, more attached to the outcome.

[00:07:17] **Ben:** And it's easy to think of that when you're looking at code because ultimately the end user isn't seeing the code, they're seeing the product, they're experiencing the product. So the code is kind of a layer removed. But I started thinking more deeply about this last week when I was playing around with some generative AI with,nano banana and Google Gemini.

[00:07:38] **Ben:** And it's an interesting context to think about because the end product is the thing that you can see. So there's, there's no like separation between the technology. The thing you're trying to create, right? It's not like it's using Python to generate this image, so I don't care about that. Or it's using some other technology and all I care about is the image.

[00:07:58] **Ben:** That's the thing I'm generating is the image. So I have to be very attached to it because there's no separation between the product and the process, so to speak. And no matter what I did, I could not get the thing that was in my head to become the image that was being generated by Google Gemini, no matter how in depth my prompt was.

[00:08:20] **Ben:** No matter how many times I asked Gemini to give me a prompt, that would better describe the thing I'm trying to describe. It would end up giving like extra joints to people's arms and legs. The more I tried to futs with it and I'd be like, oh, you know, change this person's position just slightly. And then suddenly they'd be sitting in a totally different way on the bench, even though I didn't ask it to do that kind of stuff.

[00:08:43] **Ben:** And I guess like the, the failure here to me is these tools seem most effective when you almost don't really care what the outcome is. Like that's when they're the most impressive. Like, oh, I want this app that does something kind of generic. And then blam, it makes her like, I want this image that kind of looks something like something like this.

[00:09:06] **Adam:** And you're like, blam, oh my God, I can't believe it did that in 20 seconds. But the moment you have a very clear vision in your head of what should happen, that's like almost never the thing that you can actually create. I think I can, I, I've had similar experiences with the image generation stuff. Like you have to be very open-minded with what you want out of it. I think I have found that the, the code generation specifically works a heck of a lot better when you do have, you know, some foundational computer science knowledge and you can guide and be like, no, don't do that.

[00:09:40] **Carol:** Yeah.

[00:09:41] **Ben:** and, and if it's copying and pasting essentially what you've already done in the app, but in kind of tweaking it for a different part of the application, like it is very good at that. But I was, okay, so I dunno if it was last week or the week before Google released something called Stitch, or at least maybe that's when it came on my radar.

[00:09:57] **Ben:** It's like this design AI platform where you can say, design me a website that does such and such and it barfs out like five different versions of it. And then you can click into them and say, let's do variations on this one and like make 'em very creative and mess around with the typography and go crazy with the color schemes.

[00:10:15] **Ben:** And again, it's like one of these things where. In a vacuum where you don't really care what it looks like, you're like, holy cow. It just came up with some like really kind of professional looking, you know, maybe templated looking designs, but like fun typography and fun color schemes, and you can iterate.

[00:10:31] **Ben:** But the second you take a screenshot of your existing application and put it in there and say, Hey, can you try tweaking some of the UI to create more separation between the UI widgetry? It's like, it has no idea how to do that. You know, because suddenly you're anchored to an experience that you want and you're not just allowed to get anything that it's gonna suggest.

[00:10:53] **Adam:** but I, I mean, I, are you asking it to generate that image that looks like what you're talking about? Or are you just saying like, you give it a screenshot and you're saying This is the interface, this is the page that has the code, this is the change that I wanna make.

[00:11:04] **Ben:** the, the one, I mean the, the Google Stitch, what I was trying to use. You take a screenshot and then it, but then it can generate actual. You can like click in and it shows you that this is text and this is a button and you can change the colors. And it like, it,

[00:11:16] **Ben:** like reverse generates the markup for your screenshot and then does variations on it. Like again, it's like, it's very technically impressive what it's doing,

[00:11:26] **Adam:** mm-hmm.

[00:11:27] **Ben:** but it's not doing the thing that I wanted it to do. And I, and it's like I don't know how to hold the tool to get the thing that's in my head to come out on the screen and I don't know.

[00:11:37] **Ben:** So I don't know where I'm going with this other than I'm feeling like It's hard to feel like you just don't know how to use the tools when you're not sure if maybe the tools just don't do what you think they do.

[00:11:47] **Adam:** Yeah, I hear you. I, I feel like I've seen somewhere and I wish I could remember where, but like people who use these creative tools that do like image stuff, right? People who are in Photoshop all day, or InDesign or, or whatever these other things are. you know, like they might be more open to AI generation of stuff.

[00:12:07] **Adam:** If it didn't just like, give you one flat rasterized like, here are the pixels you requested in the order you requested. Right? You know, they want layers. They want to be able to tweak and. Sort of thing. And like, I think, you know, like exactly what you're talking about. Like you asked it for the, the A person to be slightly repositioned and it totally changed it to be able to like prompt just against that one layer of the image, like move this, or even if you could just manually drag that person over a little bit, right?

[00:12:35] **Adam:** Like that sort of thing I think is exactly what they want.

[00:12:39] **Tim:** I ran into that. I think I talked about last week. I had that for my, Cooking blog my recipe, blog it. The first shot out, it is the picture that I use on my discord image. and I just wanted, I was like, put me in a kitchen. I'm a home, home cook, kind of a science food nerd. And it generated, it was a great picture.

[00:12:57] **Tim:** The face looked like me, but it had like a weird, like two ended spoon. I've never seen a spoon in my life. It was like a, it was a wooden spoon with a spoon on each end. I'm like, I have never seen a spoon like that in my life. And I, I was trying to remove the spoon. That's all I wanted to do was take away the damn spoon.

[00:13:14] **Tim:** And every time it generated a new picture, the spoon wasn't there. But I was like, I gained 20 pounds. Like, like my face didn't look anything like me anymore. Like, oh my God. So I had to create a new session, uploaded the exact picture, like, just take away the spoon. That's it, period. And it, it finally did it.

[00:13:32] **Tim:** But

[00:13:33] **Ben:** yo.

[00:13:34] **Tim:** a pain. I probably spent an hour trying to get rid of that spoon.

[00:13:38] **Ben:** The funniest thing is, so I was trying this on Google Gemini and then eventually I'm on the free tier. So I, I ran out of image credits and then, so I said, okay, lemme try and go into ChatGPT and then I would paste the description from Gemini into ChatGPT and ChatGPT say like, oh, we can't do this 'cause it violates our terms of service for like content moderation.

[00:13:57] **Ben:** And I'm like, this is not an erotic photo. All of these people have clothing. This is just supposed to be a joyful scene. If there's anything that violates the terms of service, please do not include it. And it'd be like, oh, of course. Well, we put it that way and then it starts to show the image generation, like the fuzziness, and it gets like 30 seconds into it and it's like, Nope, sorry.

[00:14:15] **Ben:** We can't do that. It doesn't comply with our, uh, content moderation. I'm like, oh my God.

[00:14:20] **Carol:** The image that is generating is a guy sitting on the bench eating a hot dog.

[00:14:25] **Tim:** yeah.

[00:14:25] **Adam:** nano banana. It's not my fault. Your mind is in the gutter.

[00:14:27] **Ben:** Yeah,

[00:14:28] **Tim:** Yeah.

[00:14:29] **Carol:** Did you guys watch Silicon Valley?

[00:14:32] **Carol:** It was like a, yeah.

[00:14:33] **Carol:** And where he had the app that was like, not a hot dog. Not a hot dog.

[00:14:38] **Tim:** that's my failure. I'll, uh, pass off to Carol. What do you got going on?

## [00:14:42] Carol's Fail

[00:14:42] **Carol:** Well, uh, well, you kids talk about your AI stuff and these things. I'm just gonna admit I got old really quick and uh,you'll understand in the minute I went on,

[00:14:53] **Adam:** in the sandbox anymore.

[00:14:54] **Carol:** I, uh, I went on vacation last week and went and visited my in-laws and we played quite a bit of golf and where they live, it was like 104 degrees while we were playing.

[00:15:05] **Carol:** And me and Drew, we were in Tucson, Arizona.

[00:15:08] **Tim:** oh, he live on the sun. Good God.

[00:15:11] **Carol:** they live on the sun. Yes. So we're like out in the middle of the day, they're like, Hey, kids, don't forget to hydrate. And we're like, Hey, old parents. Don't forget to hydrate. Friday morning, I wake up pretty much have no memory of Friday morning because I was so hydra dehydrated.

[00:15:28] **Carol:** I landed in the ER

[00:15:29] **Ben:** Oh my goodness.

[00:15:30] **Carol:** my heart racing. G wouldn't stop bad EKG, it took fluids and fluids and fluids. And they're like, all right, now everything's good. They're like, you're just severely dehydrated. It happens to people here all the time. I was like, not young people.

[00:15:46] **Tim:** If you're not used to it, that's that. That's stuff's dangerous. That,

[00:15:49] **Carol:** and the thing that bothered me though, I was like, we live in the desert. We are 2000 feet higher in elevation than they are. And we have like, it's, they have usually have a little bit more humidity than we do. And I'm like, it's interesting that I can go from one climate to the other and I get really, like, I can't handle it there, I guess.

[00:16:07] **Carol:** But I think it's because I was out in the sun at the middle of the day. My middle of the day here is writing code. It's sitting in the air conditioner, in front of monitors, not in the sun. So.

[00:16:20] **Ben:** on the TV show, the Pit, this current season, fantastic

[00:16:25] **Adam:** No spoilers.

[00:16:26] **Ben:** No spoilers. I'll, I'll just say, so the second season takes place on July 4th. That's said on the first episode. That's no spoiler. but throughout the show, none, none of these are major cases, but throughout the show, people are coming in from, they're overheated, they're dehydrated exactly what Carol's talking about.

[00:16:40] **Ben:** And they, there's a couple of times where they allude to putting people, I can't remember what it's called. It's like the artificial jungle or something. It's this room where it's this misters

[00:16:50] **Ben:** and it's just

[00:16:50] **Carol:** Which is a real thing.

[00:16:52] **Adam:** Rainforest Cafe.

[00:16:53] **Tim:** Yeah, exactly.

[00:16:54] **Ben:** Yeah. And so I didn't know if Carol did they put you in anything like that.

[00:16:58] **Carol:** No, no, they didn't do that. They just pumped me full of cold IVs and got me cooled off, I guess, because mine wasn't temperature right. Mine was just dehydration. My

[00:17:08] **Ben:** right, right, right, right, right.

[00:17:09] **Carol:** Yeah.

[00:17:11] **Ben:** Well, you look healthy now

[00:17:13] **Carol:** Thank you. That's all the fluids they gave me. I'm still wearing them off. All right, but that's me. What about you, Tim?

## [00:17:21] Tim's Triumph

[00:17:21] **Tim:** I'll go for a triumph. So I, you know, I did my little, um, fake podcast, AI generated podcast where it generates the voices.

[00:17:29] **Carol:** Which is so creepy. if you make a voice for myself.

[00:17:34] **Tim:** but, so I, I took the idea because that was all in prep for like, the idea of like coming up with a corporate, like 10, 15 minute podcast, you know, once a week or whatever for corporate, you know, marketing and stuff to put on LinkedIn.

[00:17:49] **Tim:** And so I played it, I, I generated it for my CEO, I took her, I told her I was gonna do it. I was like, I'm, I'm recording your voice. I'm gonna put it into ElevenLabs and generate a voice, and we'll do a little, I said, give me an article to like, kind of summarize. And so it was pretty cool. It built a little script of me and her talking about, you know, reinsurance, which is the most absolutely riveting information to talk about insurance, reinsurance.

[00:18:14] **Tim:** but yeah, it made it kind of cute and funny. We, we had a little banter back and forth. I kind of described her voice and her talking style. and it already had transcripts about me and, and how I talk. And she loved it. She's like, yeah, I, I, I thought she was absolutely gonna hate it. I'm like, but she's like, actually, it sounds a lot like me.

[00:18:31] **Tim:** And, she said, it doesn't sound like you though. I'm like, no, it doesn't sound like me. So we're tweaking it and I, I think it probably will become a thing where we can like, just launch this. We'll be up at, we'll, I'm trying to find a way to be upfront and honest with people to let 'em know, Hey, this is not real humans.

[00:18:48] **Tim:** But at the same time, I don't want it to be like, in their face, in their face, but just to acknowledge that, yeah, we're, we're generating this, we're a tech company, we're generating this, but you know, if you just wanna listen to a 10 minute podcast on the way to work about, you know, the insurance space and what's going on, here's your place to go to it.

[00:19:05] **Tim:** So, but she loved it. She's like, yeah, let's, let's do it. So I was pretty, pretty pleased with that. she's not a computer per, she's not like she's from the insurance world. She was one of our customers. They came over to take over to like run our company. And, uh, yeah, she's, she's pretty, pretty cool with like, trying new stuff and experimenting, so I I appreciate that.

[00:19:28] **Carol:** That, that's really awesome because typically I find leaders that don't have a tech background are very scared when you start talking about new things and they want lots of like red tape pass before, before you're allowed to actually like innovate and try stuff.

[00:19:44] **Tim:** Yeah. She's a hundred, I mean, she is more into AI than I am. I mean, I've been absolutely flummoxed by how like everything I get from her has run through ChatGPT or Claude at some point. I could, I could tell. But I mean, she's, she's utilizing it. In fact, she told me, she's like, how did I ever remember anything without, without AI,

[00:20:05] **Carol:** Wow. What a good way to like segue into

[00:20:08] **Tim:** right? Almost like I didn't plan that at all.

## [00:20:11] AI Making Us Lazy and Stupid

[00:20:11] **Ben:** So AI making us lazy and stupid. I'll, I'll, I'll jump in. 'cause I,

[00:20:16] **Ben:** I feel like I am, I'm using AI in two very different ways today at work. It's much more of a vibe coding scenario where I'm really not looking at the code, I'm just trying to base it on the product experience and I'm talking to our internal customers and trying to create the thing that they want to see on the screen and making sure that all works.

[00:20:40] **Ben:** In my personal life, I'm still very much writing the code and looking at the code, but I'm using AI one to help me think through. Some of the planning and some of the problem space, and I'm, I'm getting it to generate some of the code as well. but in a, in a very narrow scope where it's, you know, not generating more than, you know, at, at, at most like 10 files where it's copy pasting and changing things that I've already done in the application more or less.

[00:21:10] **Ben:** And, the reason I'm illustrating these two different perspectives, because I feel like the thing that I am missing a lot when I compare the way my experience is to the way the, the blogosphere is, is that a lot of people say that they, they're learning a lot from what the AI is doing. The AI is, you know, having a PhD in your pocket with a terrible attention span, but it's doing some really great stuff and they're looking at the stuff that it's doing.

[00:21:36] **Ben:** They're really learning a lot. When I'm vibe coding, I'm not looking at the code, so there's nothing for me to learn there. More or less even that's, even though it's doing interesting architectural things under the hood, I'm sure, like I'm not looking at it so there's not a real leveling up of skills other than thinking about the product itself.

[00:21:56] **Ben:** Then in the personal stuff, where I am still looking at the code a lot, it's more copy pasting what I'm already doing. So it's not like introducing new revolutionary clean architecture ideas that I hadn't thought of, and that's not, that's not like a humble brag, like, oh, my architecture's so clean, it's got nothing to teach me.

[00:22:14] **Ben:** It's like even when I try to ask it, I'm saying, look at this architecture. Tell me where I'm falling short. Tell me how this application could be made better. It basically always comes back with either. For the size of your application, like what you're doing is totally sufficient. I wouldn't recommend changing anything, or it'll, it'll say, oh, you should change this, and then I ask it to explain why, and it says, upon further reevaluation of the code, there's probably not gonna be a value add to making the change that I originally suggested.

[00:22:42] **Carol:** Oh, I love the backtracking.

[00:22:43] **Ben:** Ah, so, so

[00:22:44] **Carol:** of it.

[00:22:45] **Ben:** my big thing that makes me angry is like, I feel like I'm not having those learning moments that a lot of people are talking about. So are you guys learning stuff from your ai? Is it teaching you things?

[00:22:57] **Carol:** So for me, I feel like I'm learning a new technology. Like that's my learning point. It's my way to integrate with this new tool that I have access to. I remember Stack Overflow being the place I go, and now I'm just going to this new place to get the information and I feel like I'm learning how to delegate to something not human, more than I'm learning technology.

[00:23:20] **Ben:** Can you, like an example is like, Hey, I need to include this new library. Can you show me how to use this library, kind of

[00:23:28] **Carol:** Or, or even like, oh, so I'm getting this weird error that's popping up all of a sudden where for some reason I have all these database connections that are going to the, the correct connection string. But this one is reading back to local hosts, which tells me it's somewhere along the line, the context is getting lost.

[00:23:46] **Carol:** So go figure out where it's actually like getting lost with context and then they'll go back and search. Right? Or for the Stack Overflow, I would be like, Hey, help me understand how DP like context works and where the session actually like gets stored and how the string could be lost.

[00:24:03] **Ben:** Okay.

[00:24:04] **Ben:** All right. Yeah, I think so. It like you're helping it, it's helping you debug the applications For sure.

[00:24:10] **Carol:** Yeah. But I'm not really learning new technology from it.

[00:24:14] **Ben:** I hear

[00:24:15] **Carol:** Yeah.

[00:24:15] **Tim:** I, I, I'll push back on your premise a little bit. So we're talking about automation, right? This, so this is basically an automation of our jobs, which has happened before in history. So my grandfather, when he came over from Ireland and Scotland, he worked in Detroit at, a motorcycle factory where he stitched the.

[00:24:40] **Tim:** Leather seats, right? So he'd hand stitch and like put the seats on, but then eventually that was automated, right? And so what you're saying kind of sounds to me like my granddad saying, well, you know, since these new machines have come in, I really, my stitching hasn't gotten any better. Well, duh, you're not stitching anymore, grandpa.

[00:25:00] **Tim:** You're, you're the machine's stitching it. What you're doing is quality control, making sure the stitching looks good and moving it from one place to another. And I think that's kind of where we're going with, with, with coding is like, you know, I've spent all last week in all this week writing code, but I've not actually written a single line.

[00:25:20] **Tim:** My job was to, explain what I wanted to do, have it do some research. I review the research, and then I tell it to build a plan. To implement the research, said research. I review the plan to make sure there's no holes in the plan. Then I tell it to do the plan, and then I test, test it afterward. Actually, I let it test itself first, and then it fixes any errors iteratively, and then I do some human testing on it.

[00:25:43] **Tim:** And that's, I, I've come to accept that that's kind of what our job seem like they're turning into. Now these days it's not necessarily crafting the code. if you're crafting the code, it's because either AI screwed it up or you didn't explain it well enough.

[00:25:58] **Adam:** Or you're out of credits.

[00:26:00] **Tim:** Exactly. Or you're getting 503s from Claude.

[00:26:04] **Carol:** but I, but I think what you said just adds like extra credit to what Ben said.

[00:26:11] **Tim:** Okay.

[00:26:12] **Carol:** You're not learning, you're just

[00:26:14] **Tim:** Well, I'm learning something I'm learning something different. I'm not learning how to stitch. What I'm learning to do is how to, how to help the AI set it up for success. That's what I'm learning.

[00:26:25] **Adam:** you're, you're mentoring your computer instead of coding it now. so I actually, I'll, I'll push back on the pushback or, or I don't know where we go

[00:26:31] **Carol:** Oh,

[00:26:32] **Adam:** but I

## [00:26:33] Learning About 3D Secure From Claude

[00:26:33] **Adam:** actually, I did learn something, not necessarily a, a bit of technology, although it's technology adjacent, but I did learn something important from my job today via asking Claude.

[00:26:44] **Adam:** we do a lot of payments, stuff online payments with credit cards and digital wallets, Venmo, PayPal, et cetera, Google Pay, Apple Pay.and one of the features that's available in those technology stacks is something called 3D Secure. I'm sure Tim is gonna internally be nodding his head over there. and, so basically what 3D Secure is, I have come to learn, I did not know this earlier today, is basically it's a way for some additional checks to be done by the technology that's used to capture the card to then give the, I'm gonna use the wrong terminology of the service provider.

[00:27:20] **Adam:** I don't know. The, the, basically the, the, the bank that's, that owns the card or whatever that's, that's providing some of the technology there.

[00:27:27] **Tim:** the sponsor bank.

[00:27:28] **Adam:** sure. Whatever. but it gives them, it gives them, I guess, enough confidence that they then. own the responsibility for validating that the card use is not fraudulent.

[00:27:41] **Adam:** So basically the what what it ends up meaning is that if there's a chargeback, it is no longer the merchant's responsibility, right? Like if I run a business and I set up a, a Stripe account, then I am acting as a merchant. I'm collecting credit card payments and, and charging cards. That makes me a merchant.

[00:27:58] **Adam:** If somebody does a chargeback, if you just call your credit card company and say, Hey, Adam charged me a thousand dollars. That's not cool. I wasn't, he wasn't supposed to do that. Then the credit card company's very likely gonna say, okay, that's fine, and take my money away, even though I have a signed receipt and a contract from you, they don't typically care.

[00:28:16] **Adam:** and so that's, that's a chargeback and. Without 3D Secure, all of that risk is on me. It's up to me to maintain that. With 3D Secure, the, it gets kind of pushed upstream. The, the banks and the, the technology. Providing companies, I guess, take on some of that risk by making it slightly more onerous in some cases to make the payment right?

[00:28:39] **Adam:** You have to like, I dunno if they do like more one-time password type stuff, oh, we're gonna text you a code, you gotta put it in sort of thing. I don't know what it is, but that's what 3D Secure is in a nutshell. and I didn't know that earlier today, and I was, and we got a request from one of our customers that was like, we, we have been asked by our campus IT to start looking into this.

[00:28:59] **Adam:** Is this something you guys support? You know, what, what other customers do you have that are using this? That sort of thing. So I started looking into it and I said, I, I gave Claude a couple of things. I was like, okay, we're, I started with a simple explanation. We are, we've been asked by some of our customers to look into implementing 3D Secure.

[00:29:15] **Adam:** I gave it like one JavaScript file and one CFC of, like, this is where we're doing some payment gateway stuff. Like these are good places to start. You can spider out from there if you want. And then I said something to the effect of, I don't really know anything about 3D Secure, so what I want you to do, oh, I, I also linked it to the, the docs for our two gateway providers, the Spreedly and Braintree.

[00:29:35] **Adam:** I said, these guys I know support 3D Secure. What kind of changes would be necessary for our applications? Like, I'm not, I'm not asking you to plan the code changes, just like kind of teach me what is 3D Secure? What do I need to know? Is this gonna be a big effort on the client side? Is gonna be a big effort on the server side.

[00:29:53] **Adam:** Like, and, and then what am I, what questions am I not asking that I should be asking? And it came back and it gave me a really good, overview of all of it, which is kind of where I gave you, I, I passed that information on to you just now. But it, then it had a couple of follow up questions, and like, of the five questions, three of 'em, I was like, I don't know.

[00:30:11] **Adam:** Tell me more. Because that I, I understand what those words are individually, but I don't understand what the sentence means. and, uh, so I learned quite a bit from that. And then of course, at the end of all of that discussion, so, okay, great. I understand this. Now, now take this discussion and file a GitHub issue to implement all of this stuff, using all the, the information that we just discussed in our inner our chat.

[00:30:33] **Adam:** And it did, and the issue looks great. So,

[00:30:36] **Tim:** But you didn't learn anything about coding?

[00:30:38] **Ben:** No, but I, I, I think, I think that's a great, a great use case. And maybe this is also just one of these things where. The words that people use are so imprecise that when, when I hear someone talk about, oh, I see the, I see the agent doing something and I'm learning stuff new, you know, I'm thinking, well, if the agent's doing something, then it must be at, at like a low level technical thing that you're learning, not necessarily a more abstract, conceptual thing.

[00:31:06] **Ben:** So again, this could just be words, meaning different things to different people.

[00:31:11] **Tim:** Yeah. Yeah. See, I don't see any. Clash between the, the things that we all said, because I've talked about, you know, my job is to review the research, and that's what you did. You did research and you reviewed it and you, you learned something from it. I didn't learn, you know, you didn't learn anything about the code or the implementation because it handled that.

[00:31:29] **Tim:** And so I, I think Ben, my feeling was, Ben was talking about more about, oh, I learned some cool way to handle a technical problem. 'cause the implementation it did. that, that, that I'm not gonna get down into as long as it works, it works. The, the test pass and my QA test, you know, use test works. So, yeah.

[00:31:51] **Adam:** Yeah. I mean, I don't think Claude is gonna invent any new patterns that are novel that we need to be on the lookout for, other than bad ones.

[00:31:59] **Tim:** Yeah.

[00:32:01] **Ben:** I don't think I was expecting it to invent anything new. It was more like, because it's a PhD in your pocket and it has the entire history of knowledge, you know, compressed into its trillion facet

[00:32:13] **Adam:** Parameters. Yeah.

[00:32:14] **Ben:** Yeah. Like I was hoping that I could just have it look at the code base and suggest improvements. And it's interesting I mentioned this on.

[00:32:26] **Ben:** Facebook, I think, and Mark Takata, who's the chief evangelist for ColdFusion product, evangelist for Adobe. He was saying that it's really great at looking at the code that you're writing and making sure that it adheres to the established best practices of the application. I said, yeah, it is

[00:32:43] **Tim:** From what year?

[00:32:46] **Ben:** no, like, like of the application that you're building, you know that it's staying on point with how you like to build the application.

[00:32:51] **Ben:** I say yeah, that's definitely, that's definitely true. I found that to be the case. You know, you get a good CLAUDE.md file and, and it, and it sees the patterns and the code and, and it, and it does really well. What it doesn't seem to be able to do very well at all, at least in the way that I'm prompting it, is to look at the code and almost tell me what's not there.

[00:33:09] **Ben:** You know, what are the abstractions that I don't have that would help, or like what are the architectural choices that I didn't make that actually would make the application easier to maintain? And I have not really gotten it to give me any sound advice from that regard. Which I, I'm, I was surprised. I thought that would just be something that it would do very well.

[00:33:29] **Tim:** when, so when I'm in the planning stage, right, so the, the, the stage where you're doing research b before you start implementing, one thing I always tell Claude to do and in my CLAUDE.md is that it should ask me three questions to challenge its assumptions about what I'm trying to do. And so it every time it asks me, and, and I found that that three question gate tends to.

[00:33:53] **Tim:** Initially it tends to like really focus, laser focus down to what I'm trying to accomplish, and then eventually gets to the point where it's just arguing over implementation details that are minor, and I just stop caring. I say Stop asking me those questions, but the having those questions kind of helps you kind of focus down to what you're really trying to do, because you don't know you have a blind spot sometimes, and so sometimes it has a better view of of what to ask you.

[00:34:24] **Adam:** So it, it sounds, if I, I just want to understand, it sounds like you're kind of asking it to use the Socratic method to steelman its own argument to you, like a ask you questions where the answers could potentially disprove its argument.

[00:34:37] **Tim:** Yeah. Yep. Yep.

[00:34:39] **Ben:** I like, well, this almost calls back to, the, I can't remember who was doing this. I think this was Adam, where it had to rate bugs and then it had to rate the rating of the bugs.

[00:34:49] **Adam:** Yeah. Yeah.

[00:34:50] **Tim:** He game, he gamified the bug

[00:34:51] **Tim:** system.

[00:34:52] **Ben:** Yeah.

[00:34:53] **Carol:** Oh, that's great.

[00:34:55] **Adam:** Well, let's, uh, let's talk about some more ways that AI is making us stupid and lazy.

[00:34:59] **Tim:** Look, so I a hundred percent I'm waiting for the day. When Claude says to me, Tim, you asked me that exact same question five prompts ago, because

[00:35:07] **Tim:** seriously, it's

[00:35:07] **Tim:** like not just five prompts ago. Yeah. Yeah. 'cause it's like my context window is much smaller than his context window. And, I, I'll be like, I know it, I know it answered this.

[00:35:19] **Tim:** I don't remember what it was, and I'll just a, I'll just type it in the, the CLI, I'm like, what's the answer to this? And it'll give me the answer again, but I was just too lazy to scroll up. To look, to look at

[00:35:30] **Adam:** That's pretty lazy.

[00:35:31] **Tim:** yeah, it's pretty lazy.

## [00:35:32] Managing AI Usage Quotas

[00:35:32] **Tim:** And then I, I feel guilty if I'm not burning tokens. Like I'm burning tokens right now while we're talking. 'cause I'm like,

[00:35:38] **Tim:** I'm like, I'm at a computer. I might as well,

[00:35:43] **Ben:** I never look at my token usage. I don't care. Like I just kind of go do my thing and

[00:35:49] **Carol:** if someone yells at me, they'll yell at me.

[00:35:51] **Ben:** She's on the

[00:35:51] **Adam:** so yeah, I was gonna say, you're, you're not on Anthropic anymore, right?

[00:35:54] **Carol:** No, no, no,

[00:35:56] **Adam:** Yeah, because the government and Anthropic are fighting. so, I, I know that OpenAI, I assume that's what you guys have now,

[00:36:03] **Carol:** we have several things. Let's be clear. Yeah.

[00:36:05] **Adam:** Okay. but I know OpenAI has the, they have their $200 price point, which matches, I'm sure, more or less the 200 price point from Anthropic, which is what I'm familiar with.

[00:36:16] **Adam:** I'm currently on the a hundred dollars a month price plan from Anthropic, which is I guess five x the pro amount. and the 200 is 20 x the pro amount. So it's a, it's a big step down and like I feel like I need a, I need a step between, 'cause I continuously run into the limit of the five x. And they're like, I, when I first got onto the 20 x, I was using it a good bit and, and kind of getting close to bumping up against the limits of the session and the week.

[00:36:44] **Ben:** but I don't think I ever actually ran out. But now I'm, I'm right back in the thing where I'm constantly kind of guarding my session. and I, that's kind of how I'm noticing my own laziness, right? Like,so if I look right now, I'm at 52% for the week, which resets in four and a half days. No.

[00:37:06] **Adam:** yeah.

[00:37:07] **Adam:** Uh, and so because of that, I have stopped all of the automations that I was doing and I'm only using it interactively, throughout the day because I don't what I like. I'm kind of, if I'm gonna like admit it to myself, I'm a little terrified of like starting my day on Friday with no weekly usage left.

[00:37:25] **Carol:** So what will you do if that happens? So you're just gonna sit in meetings all day,

[00:37:28] **Carol:** just

[00:37:28] **Adam:** lot of email and No, I mean, I'll, I'll, I'll do stuff, but it, I probably won't prioritize code. Right. there's, I'm sure there's always, there's plenty of like, cleanup and compliance and you know, other kinds of stuff that needs to be done. cleaning up the backlog and prioritizing tickets and stuff, but,

[00:37:47] **Carol:** And maybe that's why I don't look at it as much. My morning is usually spent like fighting fires. It's just helping my entire team get back on track, resolve some issue they're having deal with something that AI generated for them that doesn't work and they can't figure out why. And that doesn't really require necessarily my usage.

[00:38:08] **Carol:** So maybe that's why I'm not run into any issue. Plus, whenever I'm using it, I spend a lot of time in the plan mode. So I have it generating like the concept of what we wanna do and get some like baseline understanding of how we do it, and then spin that up into stories which then the developers end up taking and doing the bulk of the work from.

[00:38:26] **Carol:** So right now I don't generate a ton of code other than my own, just, I want to fix little things and I wanna see how it handles a bug or an issue here, or go find a problem because I see these, this log all the time.

[00:38:39] **Ben:** Well on, on top of that, even when it's not a, a running out of tokens issue, where at work, we're doing mostly vibe coding. If Claude is down, I don't know how the application works. I don't know the language that, you know, it's like, I don't know how to write Python. I don't know how to use CockroachDB.

[00:38:56] **Ben:** I don't know how to write React, but like, that's what's underpinning this application. So when Claude goes down, or almost even worse this afternoon, it was just really hanging for a long time. That's like, that's almost like one of those denial of service attacks where they do really slow responses and I, you know, I can do exactly what Adam's talking about.

[00:39:17] **Ben:** I can look at the backlog. I can flesh out some tickets, but like, I can't, I can't build product because I don't know how the product works.

[00:39:24] **Carol:** that's,

[00:39:24] **Adam:** that's, that would be a good time to catch up on my articles. I haven't been, uh, all these browser tabs that I've been opening and not reading.

[00:39:31] **Ben:** But it, but I just wanted to add on to kind of what Tim was saying, at the start here where, where he's asking the same things over and over again. I am kind of doing that as well, but I've. Almost take it in an absurdist direction where I have a a, a Claude Code skill that is really just a bulleted list of things that I would tell Claude to do.

[00:39:52] **Ben:** So one of the things that I have is a skill called Branch, and what it does is it runs in sequence, check out the main branch, pull the code down to make sure it's up to date. Rebase the feature branch that I was working on, on main run, any pending database migrations that haven't been run, I'm getting my, my skills confused.

[00:40:13] **Ben:** But basically I have like a steps to either prepare this branch for development or push this branch for make sure it's up to date. And the, the reason that I think this is ridiculous is because it's non-deterministic. I really should have just asked Claude to write me a bash script that would have done this

[00:40:31] **Adam:** I was just

[00:40:31] **Adam:** gonna

[00:40:31] **Ben:** right every single time.

[00:40:33] **Ben:** But it's, I've gotten into this mindset where. Even though Claude is the one doing the work and the work is non-deterministic, it somehow still feels easier than just asking Claude to write a script that will do the right thing every single time. And I don't know what that, I don't know. There's a laziness in there and I can't, I can't articulate it, but it's like AI has somehow made me lazy in this weird, amorphous way.

[00:41:02] **Tim:** That example sounds like not necessarily, it's made you lazy, it's made you codependent. It's

[00:41:07] **Tim:** like, I can, I can create a bash script to do it for you, but I re you know, you're like, I really just need to ask Claude, make sure it's okay.

[00:41:16] **Carol:** Yeah.

[00:41:16] **Tim:** Get that, get that. I wanna see that beep booping, you know, whatever the little things it says

[00:41:22] **Ben:** Pontificating,

[00:41:22] **Tim:** it's thinking.

[00:41:23] **Tim:** You're like, I wanna see it. Think and, and then do the thing rather than just double click a, a, a batch file or something. Okay.

[00:41:30] **Adam:** Did you guys see that the Claude Code source code leaked today? Like kind of a backwards way, like I think it was like a source map sort of leak.

[00:41:39] **Carol:** no way.

[00:41:40] **Adam:** and yeah, so I think it's available on GitHub. I, I haven't looked for it, but I did see some people sharing screenshots of this and that, like the, the regex that they used to find curse words and negative sentiment stuff.

[00:41:50] **Adam:** and then the other thing was like, it's like a 180-item list of those words. So like beep-booping, procrastinating, you know, all those

[00:42:02] **Ben:** Flibbertigibbeting.

[00:42:03] **Carol:** I enjoy those. I, okay. I enjoyed those back in the

[00:42:08] **Adam:** Past tense.

[00:42:08] **Carol:** Yeah.

[00:42:09] **Tim:** Back in the day when Trump wasn't fighting with them

## [00:42:12] AI Replacing Search Engines

[00:42:12] **Carol:** So, my learning piece, I do wanna add something from earlier, you

[00:42:16] **Carol:** know, like we are using Azure AI Foundry to do a lot of our LLM stuff. Well, I haven't been in Azure AI Foundry doing anything. So before we had access to these tools, I would have, you know, watched a few YouTube videos while I was working or read some articles or even went to their site and did any demos, you know, walked through and got an understanding of what Azure AI Foundry is and how to use it instead.

[00:42:41] **Carol:** I pulled down a repo today and was like. How do I connect to Azure AI Foundry and it's explaining all this or no? I was like, how do I get all my connection strings? And I didn't lay out that I needed Azure AI Foundry. So it's explaining to me like how to set up my connection through Entra ID, which we will need, like that's gonna have to be created as well.

[00:43:00] **Carol:** But finally at the end of it, I'm like, look, I'm brand new to Azure AI Foundry. I haven't even opened the site until today. I don't know where anything is in there. And it pretty much said, well you're stupid because I'm not talking about Azure AI Foundry. You're supposed to be an Entra ID doing all of this. And I'm like, uhoh, I probably should have like, went back and said, I need all the connection information for the LLM models in Azure AI Foundry to understand like how to make it connect from my local, to these models that we're gonna be using.

[00:43:29] **Carol:** And I was just like. Back before I had access to a tool that could just answer things, I would've went and found out a lot more on my own. And now I have a dependency on the information being quickly available to me and just a couple questions, and I feel like that's where I see myself being very lazy right now with ai.

[00:43:47] **Adam:** Yeah. I do feel like maybe part of the trap that it's, that it has lulled us into is that it's like one interface that can do everything, right? You can ask it for a recipe, you can ask it to fix a bug. You can ask it to do research on something, and it makes it too easy to make it the default place to go for everything.

[00:44:08] **Carol:** Yeah. I have to remember, it's not really my search engine. Like I still need to go search, but then when it pops up, the very first thing is now an AI response. I'm like, do I just scroll past it or do I read the AI response? Well, now I always read the AI response first, so I'm like, why even go the search

[00:44:24] **Tim:** Yeah. I've, I've, past couple weeks I've stopped searching.

[00:44:28] **Carol:** really?

[00:44:29] **Tim:** yeah, because I feel like, and I, rightly or wrongly, I, my gut tells me that people who are the top of like the list have gotten there because they've gotten really good at their SEO game and not necessarily the best answer. And whenever you ask explicitly an LLM to do deep research, like use those words, deep research, you know, it will, you can see it beeping and booping and bopping and whatever through like, you know, dozens and dozens of websites, more websites than I would ever scan, you know, past page one of the, of Google search, which is.

[00:45:07] **Tim:** obviously the dark web. Yeah, the dark web is page two. so it, it's searching and searching and so I, my assumption is that their answer's gonna be better than what I could have done in the same amount of time doing like several Google searches.

[00:45:22] **Adam:** Right, and you're probably not that wrong, or if you're wrong at all,

[00:45:26] **Tim:** All right.

[00:45:27] **Adam:** in most cases,

[00:45:28] **Tim:** But there, but there's, there's no way to, I guess you could ab test that I should ask Max. That's kind of what actually what he's doing with the AI company he's working for.

[00:45:37] **Adam:** ask Claude.

[00:45:39] **Tim:** It'll lie to me.

[00:45:40] **Ben:** I feel like there's almost a little bit of a dystopian undertone that some people have when they talk about the web, where they now talk about making the web almost optimized for agents and less for humans, which is so depressing and also

[00:45:56] **Ben:** feels like, how is that any different than saying, well, blind people won't use my site, so I don't have to worry ever about accessibility?

[00:46:04] **Ben:** You're like, are we going back there though? That seems weird.

[00:46:08] **Tim:** Yeah, we're look at, look work. We're looking to like put MCP in front of all of our APIs. Just

[00:46:15] **Carol:** Just so people can go pull 'em in and learn. Yeah. Use them. Yeah. Or not learn like use them.

[00:46:20] **Tim:** because, because I've used, MCP, like Atlassian has an MCP server or several others that we use. And it's actually really, really cool to, to be able to just use that, to find out about their services.

[00:46:34] **Ben:** I still like going to the web, not for everything. It's not like I do a lot of searches, but I still enjoy using websites. I, there's, when people talk about how they want to use the web only through agents and like the only thing I wanna do is go to my ChatGPT and ask it what show times things are playing and buy me this meal.

[00:46:52] **Ben:** And for Uber Eats like that doesn't appeal to me at all. That seems really weird personally to each their own. I'm not here to yuck anyone to yum, but like I really hope that's not what the web becomes.

## [00:47:04] Google Search Is Broken

[00:47:04] **Adam:** Yeah, I mean, on the subject of like, you know, Google search results and are they even worth looking at anymore? I do feel like pre LLM AI stuff, there was this sentiment that like the, the first, at least half dozen results from the Google search would be basically worthless. Like, go, the value of Google just went way down over the last few years because what, what is it?

[00:47:29] **Adam:** I forget which law it is, but any, any metric that you start to track then becomes a, a useless metric. I don't know. But, you know, just by, by virtue of tracking it, it becomes useless because people start to gamify it. Well, okay. Being first on Google became good for being profitable, and that's what this country is good at, is taking things that are useful and, and making them not useful, but profitable.

[00:47:55] **Adam:** and so now Google sucks. And so for that reason, I think that there's a, there's a reasonable expectation that these LLMs that can look at 15 articles and cross compare notes and, and, you know, kind of crystallize the, the, the salient thoughts are, you know, potentially better than Google

[00:48:17] **Tim:** Until they learn to gamify it

[00:48:20] **Adam:** until they're eating their own tail, right?

[00:48:21] **Tim:** exactly.

[00:48:22] **Ben:** Google search the other day and I literally could not tell what was an advertisement and what wasn't. It was like the AI response and then it was sponsored links, and then it was like ad links and then it was like another block of something and I, and I swear, it felt like nothing on the entire first page was actually a search result.

[00:48:41] **Ben:** It was, it was really creepy.

[00:48:44] **Adam:** I do use DuckDuckGo as my default search engine. Now when I, when I need one. And it does, I think it does have the, AI response at the top, but then I, I don't feel like there's sponsored links. I'll have to go look.

[00:48:57] **Carol:** All the way to Arizona on our drive. There were so many bill billboards for Duck Duck AI, and finally my husband's like, what the heck is Duck Duck AI? I was like, do you know what DuckDuckGo is? He's like, yeah. He goes, oh, I was.

[00:49:15] **Ben:** So, to kind of take it in a slightly different angle for a second, one of the things that I'm finding is that I am now tempted to add things to the product that probably don't need to be there, simply because it's really easy to add them. And, and I want to differentiate this from, it's easier to experiment because I think experimentation at least implies that the thing you're building has value.

[00:49:42] **Ben:** But I've definitely, especially when I'm, when I'm feeling blocked on a particular part of building an application, personally, I might just as almost a way to self-soothe, try to build something new inside of it, because like, oh, at least I'm moving forward. I I'm finding that I'm, I'm losing some of that critical thinking of, is the thing that I'm building actually going to be adding value or just a distraction?

[00:50:08] **Ben:** And I think historically the amount of friction it would've taken to build something would have tampered my perspective a little bit better. And I'm, I feel like I'm losing that critical evaluation. Maybe

[00:50:21] **Tim:** I don't see that as a bad thing. Being able to add more features in the same time.

[00:50:27] **Ben:** it's more like, am I adding the features because I can, not because they're helpful.

[00:50:33] **Carol:** That's a bad thing.

[00:50:34] **Ben:** I, I mean, I'm not saying it's a bad thing. I'm, I'm saying that I'm not, I don't think I'm thinking as deeply because the cost is lower.

[00:50:43] **Tim:** Hmm. Yeah.

[00:50:45] **Carol:** I still find myself going, is this going to be useful in the near future with code it's generating or with suggestions it's making? Or is this just gonna be legacy junk? I'm gonna have to support and maintain down the road? I do constantly find myself questioning the architecture of what it's putting in, but I feel like that's just the way I've always been with how I code as I try to think about the longevity of what I'm writing and the maintainability, you know, in the future.

[00:51:13] **Adam:** Okay.

[00:51:14] **Ben:**

## [00:51:14] Patreon

[00:51:14] **Adam:** All right. Well, I guess we're all too brain rotted now to, uh, come up with a good way to, to off ramp the show. So we're just, I'm just gonna smoothly transition into the outro like this now. And you can blame Claude Code for, for all of that.so, this episode of Working Code was brought to you by learning things.

[00:51:33] **Adam:** You may or may not be doing that.I, I only you can decide that's, that's my, my take on that. and listeners like you, if you're enjoying the show and you wanna make sure that we keep putting more of whatever this is out into the universe, you should consider supporting us on Patreon. Our patrons cover our recording, editing and transcription costs, and we couldn't do this every week without them.

[00:51:52] **Adam:** Special thanks to our top patrons, Monte and Giancarlo.

## [00:51:54] Thanks For Listening!

[00:51:56] **Adam:** You guys rock. We're gonna go do the after show as my co-hosts furiously edit the after show portion of the document that doesn't exist. I have no idea what we're gonna talk about, but Carol's back, I'm sure we got some stuff to get into. so if you would like to get access to the after show.

[00:52:11] **Adam:** New ones, old ones, and the ones in between. the easiest way to do that, and in fact the only way to do that is to go to patreon.com/workingcodepod, throw a few dollars our way, we'll hook you up with a special RSS link that, includes all the, the back catalog and the front catalog of the, the podcast episodes, including after show.

[00:52:31] **Adam:** So, that's how that works. That's gonna do it for us this week. We'll catch you again next week. And until then

[00:52:37] **Tim:** You make us smarter, not dumber. Your heart matters.
