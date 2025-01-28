---
title: "183: Who's Got the Beans? Carol's New Project"
description: "In this episode, the team discusses various aspects of starting new projects, dealing with both personal and professional challenges, and the excitement and fears around initiating new work."
date: 2024-06-19
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/183-whos-got-the-beans-carols-new-project/id1544142288?i=1000659547207"></iframe>

In this episode, the team discusses various aspects of starting new projects, dealing with both personal and professional challenges, and the excitement and fears around initiating new work.

Carol shares her idea for a new web application to help organize event contributions, and the group explores initial steps and considerations for starting such a project. They touch on security, data management, and different frameworks and platforms for development

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[laws-of-software]: https://www.laws-of-software.com/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/183-whos-got-the-beans-carols-new-project.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Carol:** But basically, software gets approved through FedRAMP and it gets assigned a level of security, meaning that it's low security. So if the software you're writing is low, then you can use the low tools or higher.

[00:00:16] **Adam:** I'm sorry, this is just the, the person in me that watches way too much YouTube, but I couldn't help but like reinterpret or reimagine what you're talking about as a tier list. Ben is just looking at me

[00:00:25] **Ben:** No, I have no

[00:00:26] **Carol:** I don't know what you're talking about. Yeah.

[00:00:28] **Adam:** who just added himself as the millennial.

## [00:00:52] Intro

[00:00:52] **Adam:** Okay. Here we go to show number 183. And on today's show, we're going to talk to Carol. Carol's back. Welcome back, Carol. Wait a minute. You were here last week. It was me that was

[00:01:00] **Carol:** yeah, let's get this right.

[00:01:02] **Adam:** I, I'm back. Ben's back.

[00:01:05] **Carol:** Tim's gone.

[00:01:06] **Adam:** We're just shaking it all up. Anyway, there's some people here, and we're going to talk about stuff. But first, as usual, we'll start with our triumphs and fails. I'm going to go first. I don't know, we're kind of resetting the whole thing here. So, I'm going to go first.

## [00:01:17] Adam's Triumph and Fail

[00:01:17] **Adam:** I have both a triumph and a fail this week, because I have a triumph that has to be celebrated. And I have a fail because that's kind of what is on my mind for the day for work. So, a triumph is that, my DNA has been spread across the globe. Um, but so, and by which I mean, I have sent out our stickers, and I had to lick a bunch of envelopes to do that.

[00:01:39] **Adam:** And so, I, I notified our patrons and discord that, stickers were on their way. And I said, you know, I had to lick all of these envelopes. Please don't use my DNA to get me implicated in any crimes. Or if you're going to, at least do me the favor of like synchronizing so that I'm in, I'm implicated in crimes all across the world.

[00:01:55] **Adam:** Like all at the exact same

[00:01:56] **Ben:** He couldn't have done it.

[00:01:57] **Carol:** Yeah.

[00:01:59] **Adam:** that's my triumph. I'm super excited to finally have that behind me. It is, oh, I, oh, today's June 17th as we're recording this. If it had been June 15th, I'm pretty sure that's like the halfway point through the year, right? It's the sixth month, it's the middle of the month. I don't know, whatever. so it took me more than half a year to get that completed.

[00:02:14] **Adam:** I am sorry, but,

[00:02:16] **Carol:** Done is done. Hey.

[00:02:17] **Adam:** Hey, it's done. So that's my, my triumph, my fail is, I have, I, I just noticed, while talking to some coworkers today that on my calendar for next week is an event, that I scheduled last year around this time called Bureaucracy Retreat. Do you guys remember discussing that?

[00:02:36] **Carol:** Maybe. Remind me.

[00:02:38] **Adam:** So, The, the fail about this is that it snuck up on me and I had no idea it was coming and I'm like taken by surprise by this. even though it's still like a weekend change away, but basically bureaucracy retreat is just, I'm going to lock all of the important decision maker type people from my company in a video chat because I can't lock them in a room and they're not allowed to leave until we like, you know, check a whole bunch of boxes for compliance stuff.

[00:03:00] **Adam:** Like it's like, you know, we have to do, our, our vendor risk assessment and we have to. Review our subprocessor list to make sure we're happy with all of them still. And, you know, all these stupid compliance things that you have to do that like, it's pretty much a, of course we're, you know, we're not going to drop AWS, right?

[00:03:16] **Adam:** Like, duh. But, you have to have the discussion. And so that's what bureaucracy retreat is. Just like, you know, if you don't force it, it'll never happen. And so you have to force it.

[00:03:29] **Ben:** I like it. It's like a Saw style movie. Suddenly a bunch of people wake up in a Zoom room and there's a whole bunch of security puzzles. So you want to be SOC compliant. Do you? So what, I mean, is there, how much planning do you have to do? Or is it mostly just showing up on the day and there's a list? Yeah,

[00:03:52] **Adam:** and there's a list for

[00:03:53] **Carol:** but someone has to make that list.

[00:03:55] **Adam:** Yeah, exactly. So I have to go through all the requirements, be like, okay, these are the things that we're supposed to do at least yearly, you know, at least like 36 months, whatever. I'm pretty sure that, when I was writing all of our policies last year, I, I like double checked all of them and, and.

[00:04:10] **Adam:** Everything that I could legally get away with, it's like, you know, they might recommend that you do it four times a year or, you know, 12 times a year or whatever. If I could legally get away with it, I was like, at least once per year. You know, so it gives us leeway to do, you know, a disaster recovery drill every month, but we only have to do it once a year, for example. it's just, it's snuck up on me. I cannot believe it's already time to do that again. I, as far as this current review goes, I think, you know, I'm, I'm knocking on wood here and like, you know, rubbing my lucky rabbit's foot and all that. But, I believe there is finally light at the end of the tunnel.

[00:04:44] **Adam:** We've started to get, we haven't gotten any drafts of our SOC 2 report or the AOC attestation of compliance, I believe is what that's called. but, they've started, like they sent back the, the list of exceptions that would, you know, things that technically weren't 100 percent correct. And so we either had to fix their perception or provide a response that would be included in the document, that sort of thing.

[00:05:07] **Adam:** I feel like we're approaching the finish line and I cannot wait for that to.

[00:05:13] **Carol:** Yeah, it feels like this has been going on

[00:05:14] **Ben:** forever,

[00:05:16] **Carol:** Forever.

[00:05:17] **Adam:** has, it absolutely has.

[00:05:18] **Carol:** Well, we're excited. We hope you get wrapped up soon.

[00:05:22] **Adam:** And the, the terrifying part about it is like, it's just a treadmill, right? I, when we stepped onto the treadmill, we were on the treadmill and we can never get off and we're already halfway through this year and like, I'm, I just now this or last week, Friday, started interviewing, companies, auditing companies to do our audit for calendar 2024.

[00:05:41] **Carol:** wow,

[00:05:43] **Adam:** So like, I have to pick one. We have to get a contract in. And meanwhile, I need to catch up on all the stuff that I was supposed to be doing starting January 1st, right? All this documentation stuff. So

[00:05:54] **Carol:** working sucks.

[00:05:55] **Adam:** yeah, I said to Steve today, I was like, this is a very nice hole we've dug for ourselves.

[00:06:01] **Ben:** It's in moments like this where I just, I know this is not exactly on point, but the idea that software is static and you can just write something and never touch it again and it'll just work. I'm like, I just, I'm just like the world doesn't actually work that way. Like that's, that's make believe physics.

[00:06:18] **Carol:** Oh yeah.

[00:06:19] **Adam:** Yeah. I had a conversation today with some, with an auditing company. And one of the questions they asked me was like, so do you have like any custom built software? And I'm like,

[00:06:28] **Ben:** You're like, that's literally what we do.

[00:06:31] **Carol:** like what, what is not custom built software?

[00:06:34] **Adam:** I guess like off the shelf stuff. Like, yeah, I don't understand. What does it mean to run a business and not write software?

[00:06:40] **Carol:** Right. It's all custom. Otherwise you just buy it from someone else.

[00:06:43] **Adam:** Right. That's the value. Yeah. I don't know. That's my, triumph and my fail. how about you, Ben? What do you got going on

## [00:06:51] Ben's Fails

[00:06:51] **Ben:** I'm going to go fails on top of fails.

[00:06:53] **Carol:** Oh, no.

[00:06:54] **Ben:** first micro fail, just totally randomly, I've been looking at Carol's shirt and I kept thinking it said Menor Center and then I'm like, that's a really weird kind of branding, but I realized it says Maneuver Center, which is ironically, I just went for my annual eye exam and they said my eyes were fine.

[00:07:11] **Ben:** Or I should say they're holding steady.but so fails on fails. I have just recently been feeling very stressed and anxious. I've had a lot of anxiety, kind of nondescript anxiety and a lot of specific anxieties and it's both mental and physical, and I'm feeling it in my wrists and my forearms. I, I, I've always had a little bit of repetitive stress strains, you know, I think a lot of programmers deal with that occasionally.

[00:07:47] **Ben:** but when I'm stressed, my body definitely manifests it way more. And I've just been, I've been just kind of meh. And, that's part of why I haven't been here the last two weeks. We've also had a lot of people popping over, which. You know, that's not my superpower, dealing with people. So that's like, yeah.

[00:08:04] **Ben:** So I have not been able to sort of, I think, process a lot of the stress and we're right about to kick off a heat wave up here in the Northeast. I don't know if that's going to affect you down in Texas. Texas, I guess, is always in a heat wave though,

[00:08:18] **Carol:** already started. Yeah.

[00:08:19] **Ben:** Yeah. Yeah. You're like a heat wave kind of between March and November.

[00:08:23] **Carol:** Yeah. Yeah.

[00:08:24] **Adam:** down there? Yeah, it's cause it gets so hot that the power goes out.

[00:08:28] **Carol:** Yeah.

[00:08:29] **Ben:** So, I don't know. I'm, I'm just trying to get back into the swing of things and I'm happy to be back on the show, but, I've been

[00:08:36] **Adam:** And we're happy to have you back on the show,

[00:08:38] **Ben:** Thank you.

[00:08:39] **Carol:** So this is a, you don't have to like answer the question, right? But this is just a good thing that they're out there. One thing that came about really, COVID was the idea of therapy. And seeing someone online and it's so easy now to just talk to someone. Like there's better health. There's some lemonade one.

[00:09:01] **Carol:** Like there's all these, these places you can go to online and you never have to interact with a person. So if you haven't done it, it's a good option. And for anyone listening, if you're struggling, there's always people you can talk to you. And COVID made it a lot easier to get help virtually instead of having to go to an office.

[00:09:18] **Ben:** I think that's a great idea and I've never had professional help and, and there are things that I think I just, I need strategies for dealing

[00:09:27] **Carol:** Tools.

[00:09:28] **Ben:** Yeah, you know, something very specifically that has been causing me a lot of anxiety. And I think all of this is, is amplified just because of work stuff with this heat wave coming.

[00:09:39] **Ben:** And just more recently, the last couple of months, I've started to have a lot of, I Googled this, apparently it's called climate anxiety. Like I'm just becoming more aware of climate change and How hot things are getting and how dry things are getting, how expensive things are getting. And it's, it's filling me with a sense of helplessness that I've never really considered before.

[00:10:01] **Ben:** And, and I don't know how to process that. And I, I don't know. So that's, that's just one of the things, but, but, having someone to talk to about that would be helpful probably.

[00:10:12] **Adam:** Yeah, for sure. I've had a little bit of therapy and it's so weird, like, there's a category of problems in my brain that is like, okay, obviously that's something that therapy can help with. And then there's things, it's just like, it wasn't obvious to me that therapy can be helpful with so much more, right?

[00:10:32] **Adam:** Sometimes it's just like, like you're saying, I just need somebody to talk to, I need strategies to deal with certain things. And. like, you know, there were like ways that, parenting was triggering me, like having to discipline our kids or having to deal with their issues, right? Like, it wasn't the fact that I had to be a parent that was upsetting or, or triggering me, but it was like, I couldn't cope with the way that their problems manifested as behavior issues, right?

[00:10:59] **Adam:** And so like, that was extremely difficult for me. And it was just like, And as crazy as it sounds, you know, a non zero portion of my therapy was like, do you think that they're doing this on purpose? No? Okay, so we've established it's not a choice. Should they be at blame? You know, should, should you punish them for something that's not something they chose to do?

[00:11:21] **Adam:** No?

[00:11:23] **Ben:** Yo, I, I totally relate because, While I don't have kids, I do have a dog, and as my dog gets older, one she just requires a lot more upkeep, medications, and walks, and we have a pee pee blanket on the bed now because she pees on herself in the middle of the night, and I love this dog so much. But she is 100 percent an anchor on, on everything that I do during the day.

[00:11:49] **Ben:** And, and that's part of, of talking about this climate anxiety. She can't be left home alone. She freaks out, which means that if I go out, I have to bring her with me. Which means that if I'm out with her, I have to be outside because I can't pop into a restaurant. And, and like, that fills me with all this anxiety about, I feel bad.

[00:12:09] **Ben:** Like, I feel like she needs to be stimulated mentally and physically, but. She would walk out into 90 degree weather and, and she can't deal with it. And I'm trying to come up with ways, like I'll take her to the Home Depot because at least it's inside and it's air conditioned. Yeah, exactly. And, you know, I'm trying to come up with things to do like that.

[00:12:27] **Adam:** And they have a cement floor just in case.

[00:12:28] **Ben:** hundred percent. And, and, and like, you know, I don't want to say that I resent having to think about that kind of stuff, but like, part of me is very frustrated.

[00:12:38] **Adam:** It's work.

[00:12:39] **Ben:** That, yeah. That it's work and, and you know, you start to fantasize a little bit about like, what's our life gonna look like after , you know, it's like the equivalent of like, once my kids go to college, right?

[00:12:52] **Ben:** It's like, you know, once my dog, crosses the Rainbow Bridge, like all the vacations I can go on all, all the restaurants I could eat at.

[00:13:00] **Carol:** Yeah. The overnight road trips.

[00:13:05] **Ben:** Yeah, yeah,

[00:13:06] **Carol:** Yeah. The, just the, the weather, right? We're having the issue with, we can't take Ruby out here to walk because the roads get so hot so quick that it's actually not good for her. Even with shoes on, the shoes get way too hot. Like you can feel the heat through your shoes when you're working, like walking on black tops here.

[00:13:24] **Ben:** bonkers.

[00:13:25] **Carol:** I'm currently also in the process of trying to teach my dog to walk on a treadmill because we have a treadmill in the garage. And if I, right now she's sitting on it, she'll sit on it. But when it comes on, she flips out. We're done. Yeah. So trying to teach her to walk on it because like, how do I get her exercise when she can't be outside?

[00:13:43] **Carol:** The AstroTurf Well, it's great. We have no cactus, have no burrs here, not in our yard. The AstroTurf itself gets so hot, you can't walk on it when the sun's been on it. So there's no good place for her to go potty. And yeah, it's, weather is very stressful when you have an animal or a small child. Yeah.

[00:14:02] **Ben:** and, and she gets so fixated on things, so she'll stop and sniffs a spot for like, two minutes, and I'm standing there in the sun, and I'm trying to pull her, but the more you pull a dog, the more they're like, F no, I ain't going nowhere, and they dig in, they flatten down, at least mine does, it's, it's, it's a lot of, it's making me anxious, and it's, Anyway, I'm happy to be back.

[00:14:26] **Adam:** we're glad you're back. Before we move away from this, this is, this is not really germane to our podcast, but then again, I have a microphone in front of my mouth and I have the opportunity to do something that, could potentially make the world a slightly better place. So I'm going to take that opportunity.

[00:14:40] **Adam:** Forgive me in advance. I just learned about this. Apparently, I mean, I guess it's pretty obvious, but apparently, just the cows that we raise for beef, for like humans to eat

[00:14:51] **Ben:** Yeah.

[00:14:52] **Adam:** are responsible for approximately, I think it was one and a half, maybe it was 2 percent of, the expected meat yield. or, or one and a half to two degrees of our expected climate, you know, increase, right?

[00:15:06] **Adam:** And, and so the idea that this person had that I want to pass on is beef days. Basically, it's not, it's not don't give up meat.

[00:15:14] **Ben:** Like a meatless Monday kind of a

[00:15:16] **Adam:** Well, it's not, it's not, don't, it's not give up meat. It's basically give up beef, except for you pick, you say like three or four times a year, you, you pick certain holidays, something that's important to you or whatever, and it becomes like beef day.

[00:15:28] **Adam:** And it's like a thing you celebrate. And we just have a little bit less beef or a lot less beef in our lives, right? We're just having, you know, four times a year or whatever we eat beef for whatever special thing. And by just by doing that, we could make a huge dent on climate change. Yeah.

[00:15:43] **Ben:** Yeah. I,

[00:15:45] **Carol:** it would be hard. I could try, right? We eat lots of chicken already and my husband was vegan for years and now he's back to the, if I can't kill it, I don't want to eat it. So it may not be so hard for us to give up beef, but if it's something that we could kill ourselves and not feel guilty about, then he's okay eating it.

[00:16:03] **Carol:** So we could eat all the fish we want. But I'm very allergic to fish. I can, I could kill a chicken, right? Like I grew up doing that. That doesn't bother me at all. But once I get to even turkey size, then I start feeling very guilty about killing a turkey. So I'm like, I really don't want to eat turkey. So I guess we're down to fish and chicken for a while.

[00:16:22] **Ben:** Yeah, I

[00:16:23] **Adam:** So, yeah, I'll, I'll drop some links in the show notes, about like where, where I got this beef days information from. So if anybody's interested,

[00:16:30] **Carol:** Yeah, I want to share it with him because I'm sure he'll enjoy that.

[00:16:34] **Ben:** Yeah, sounds good. All right. So that's me. Fails on fails. Carol, can get it over to you. Take us home.

[00:16:40] **Carol:** Well, I'm really glad you're back and hopefully we helped talking to us a little bit.

[00:16:45] **Ben:** I'm already feeling better.

[00:16:47] **Carol:** Awesome.

## [00:16:48] Carol's Fail

[00:16:48] **Carol:** Well, I'm going to have a fail. So at work, I'm forced to use a Windows machine and I talked about it previously that it's just been running into a few issues here and there. Well, last week it started blue screening at least twice a day.

[00:17:04] **Carol:** And helpdesk got on and ran two cleanup commands that I was like, Oh boy, this could either go really good or really bad. And this was Thursday towards the end of the day. And Friday was my off day. So I come in this morning, now my laptop just blue screens turns on to blue screen again to turn on to blue screen again.

[00:17:25] **Carol:** Yeah, so I got on with Helpdesk and they're, over my, overriding me another laptop. But then we don't have any type of image that's like a developer image. So it's just a laptop that comes to you. So now I've got to wait for rights to be given to me on my laptop. Now I have to install Visual Studio and every tool I had.

[00:17:46] **Carol:** Remember what my bookmarks were in my browsers cause I didn't export them and we can't sync them cause we can't sign into browsers. Oh my goodness. I'm actually very sad and I'm dreading this. Just new laptop setup is the worst thing in the world when you're a developer and you have your tools completely customized exactly how you like your preferences.

[00:18:09] **Carol:** Yeah,

[00:18:12] **Adam:** you choose to do it and you're in control of the timeline. It's the worst thing ever. If it's not that

[00:18:17] **Carol:** no,

[00:18:18] **Ben:** It occurs to me that in the government realm, there must be competing forces between like different perspectives on security. Because you could look at machine updates and be like, we should just be rolling out updates constantly to make sure that the machines are all up to date and they're all, you know, managing the various, exploits and whatnot.

[00:18:38] **Ben:** But then I think there could be a competing view that's like, Whoa, we can't just be rolling out updates willy nilly because we might start crashing machines and installing stuff that's no longer compatible and I wonder how they. Balance those two perspectives. I mean, it must be cause you hear these, you hear these, you hear these, these, these horror stories.

[00:18:58] **Ben:** I mean, I don't want to say horror stories, but like you hear these things where, you know, Microsoft says, Hey, we're going to end of life windows 95 and then some agencies like, Whoa, you can't be doing that. We're still running on windows 95, despite the fact that it's like 2015.so I don't know how, I guess that that's all preamble to the question of.

[00:19:18] **Ben:** What do you think actually happened? Was it an automatic update that got installed that borked, you know, it was like no longer compatible with whatever you're running?

[00:19:27] **Carol:** I hope this doesn't get me fired. So

[00:19:30] **Ben:** you could plead the fifth, you know?

[00:19:33] **Carol:** no, no, no, it's, it's well known that the process for getting laptops to people is someone sends in their laptop when it doesn't work and they just re image it. And the thought is that an image is going to fix the problem. So then they ship that laptop back out to the next person in line, even though it may have had a hardware failure, it just has a new image on it.

[00:19:56] **Carol:** So I have a feeling mine came in use. I can tell it's used based off of the keyboard. You can tell it wasn't a new, a new machine. probably already had issues cause I've had issues with just my wifi adapter not working.so I think it's just that hardware starts to fail. We run these machines like they're servers.

[00:20:15] **Carol:** I mean, they run all day long. They run hard. They're building several applications. They have their own databases. These are not just document editing kind of laptops. So when a hardware failure happens, it just, you can't recover from it unless you fix the hardware. And since the policy is pretty much just a re image it and send it new.

[00:20:34] **Carol:** Eventually, someone gets it and it just stays broken and then it comes out of the circulation.

[00:20:40] **Ben:** it's funny. So you, you mentioned your computer running like a server constantly. And, and it reminds me, this is a bit of a non sequitur, but it reminds me, there was a period in my life, maybe like. 10 years ago, where at the end of the day, I literally used to close all of my browser tabs, turn off my local development server, and literally shut down my computer. part of me wants to get back to that way of being, but then part of me doesn't even realize how that was possible. Like, what kind of life was I running where I could do that?

[00:21:13] **Carol:** Ben's a psycho. Don't listen to him, you

[00:21:15] **Ben:** yeah, old Ben, old, old Ben is psycho. New Ben is pragmatic. But there, there's a, there was like a cleanliness to that.

[00:21:23] **Ben:** It's like when you hear, People who have kind of end of day rituals where they might even have something that they say, you know, like it is now the end of the day and I will be putting aside all of my work stuff and I will be doing family stuff and they close things down. I think there's, there's something very Zen about being able to start fresh in the morning, but I don't know.

[00:21:43] **Ben:** I just can't bring myself to do it.

[00:21:46] **Carol:** If I had to rebuild my projects every morning, I would be angry. I have to load in 46 projects just for one of the things I work on. And if I had to do that all the time, I wouldn't be very happy.

[00:22:00] **Ben:** You know, and speaking about bookmarks, I mean, I, my life, you know, Depends on the autocomplete in the URL bar. I don't even have bookmarks. I just know that if I type in like. P platform dot something or other comes up and, you know, if I type in, oh, Okta. com comes up, you know, I don't actually remember what any of those things are,

[00:22:19] **Carol:** Yeah. One of my developers hit me up today. It was like, Hey, I'm struggling on something. You know, can you help me get to it? I was like, Oh, have you already elevated your, your, your role in Azure yet? And he was like, I don't know how to do that. I'm like, Oh, the link is. I don't know it because it's just in the left folder and I just hit the first link every time I need to elevate my role, right?

[00:22:42] **Carol:** So then I had to go figure out what the URL is like to Azure and then what, what you click in there to get to elevate roles. I was like, you can tell you just have things bookmarked. You never, I never would remember it because I don't have to.

[00:22:57] **Adam:** on the topic of bookmarks, I started doing this thing. So I switched to Raycast as my like launcher. Thingy instead of like Alfred or Spotlight on the Mac. so I, I use that to like, you know, you, you bring it, I hit command space and I just type, you know, whatever,discord, right. And it'll start, it'll launch the discord app and you can use it for a lot of different things.

[00:23:15] **Adam:** And I learned that it has. Quicklinks, which is like, I can just tell it to open this URL in a browser and I can make up my own alias for it. So it's kind of like bookmarks in a way.

[00:23:24] **Carol:** Oh, that's neat.

[00:23:24] **Adam:** And so like, there's, there's all these things like specific GitHub repos that I find myself pulling up frequently because I want to reference some piece of the code or something under the readme or something.

[00:23:32] **Adam:** Mostly our internal stuff. So I started like just tons and tons and tons of, of, Quicklinks. And I feel like that's nice because. I don't have to go somewhere. It's right there at my fingertips. I just, I do command space and I just start typing the keyword for that particular link and it pops up.and I'm really enjoying that.

[00:23:51] **Carol:** I miss development on the Mac. I just want to throw that out there too. And I miss having rights to do things on my machine. That's

[00:23:58] **Ben:** Though Windows does have the start key. And it pops up the little search bar, which is almost kind of like,

[00:24:06] **Adam:** little

[00:24:06] **Carol:** not the same.

[00:24:07] **Adam:** Yeah. There is, you can get Raycast on Windows, I believe. probably don't have permission to install it.

[00:24:13] **Carol:** I bet it's blacklisted

[00:24:14] **Adam:** Yeah. Yeah. It does have AI in it, so.

[00:24:17] **Carol:** It's blacklisted everywhere.

[00:24:22] **Ben:** Oh, dude. Speaking of AI, didn't you have to go to a, like an AI training session? Did we ever talk about that?

[00:24:28] **Carol:** Oh, I still haven't went to it. So when I go, when I go, I'll be sure I bring it back up. But no, we still haven't, we still haven't done it. This is just to use Copilot, like inside, Office 365. So everyone has to go to training to learn how to use AI before we're allowed to roll it out. At the last all hands, it's still coming.

[00:24:46] **Carol:** So we'll see when it gets through the final approval processes. And then I'll let you know what the training is like.

[00:24:53] **Adam:** is the government, Ben. They'll get there in about a year and a half.

[00:24:56] **Carol:** Yeah, or two.

[00:24:58] **Ben:** Awesome.

[00:24:59] **Carol:** Anyways, but that's me and Tim's on vacation, you guys. He's enjoying another country, so I think he's going to have lots of triumphs when he gets back.

[00:25:08] **Adam:** absolutely. He's been posting lots of pictures in Discord. It's a lot of fun.

## [00:25:10] Carol's New Project

[00:25:10] **Adam:** Cool. So I guess that'll bring us around to our topic for the day, Carol, you were telling us about this, like you want to start, it's not a project that you're trying to like sell, right? This is not a side hustle. This is just, this is just for fun.

[00:25:22] **Carol:** no, totally not a side hustle. So if someone wants to go do this and start it for me, you would help me because I really hate starting new things and it scares the bejesus out of me thinking that I'm going to start something new, so let's just go ahead and say that. Part of what we do like as military spouses is we spend a lot of time organizing like different events.

[00:25:42] **Carol:** It's just to keep families together. It's to make you feel like you have a home because you're not at home. Like we're in Texas all by ourselves. We know no one here. So it's all about trying to get people over to your house, going out to, we have Dave and Buster's, like we have a lot of cool places we can just go hang out at, but whenever we do things together, it's always a struggle to organize who's bringing what, because everyone wants to bring something.

[00:26:07] **Carol:** Like, Oh, I'll bring beans. I've got, you know, some Cokes. I'll bring a foldout table. Like whatever you need, people have you covered. They just need to know what to bring. So I was thinking of starting like a little website, just so organized. And I was thinking of calling it seriously, like who's got the beans, just, just as a little way to like, send it out to my military spouse brands.

[00:26:29] **Carol:** It'd be like, okay, Let me know what you're bringing so the night before I can make a quick grocery run and now we have what, what we're going to get covered. So that's just kind of like the little idea to it. But honestly, I just want a playground where I can start trying new things and I can implement new stuff and it's not going to really hurt anyone.

[00:26:48] **Carol:** And if I can get this spun up, Then there's also a place where my friends can come and do work with me. So if you have a cool idea, it's somewhere that you don't have to have a, a starting point. You can take a fork of what I've done, or you can even go where I am and let's start working on something together.

[00:27:06] **Carol:** So it also gives me the opportunity to work with some people who I wouldn't normally work with because we don't, you know, work at the same job. So that was kind of like my, my big picture thought on it was do a small side project that's going to help me that I can put out there and have a couple of people use for whatever I'm doing and make my life a little easier.

[00:27:27] **Carol:** But then also to give me a playground to work with some people and to just have fun or to just, you know, kind of push myself into learning again.

[00:27:34] **Adam:** I love that.

[00:27:35] **Ben:** Yeah, absolutely.

## [00:27:37] How Carol Starts a Project

[00:27:37] **Adam:** So you've got this idea. what is your typical approach to starting? I know you said you don't like to start new stuff, but like, if you, if you have to. Mm hmm. You're, you're, you know, it like, it's at work, it's totally greenfield. And they're like, okay, go make the thing that we want you to make.

[00:27:52] **Carol:** Yeah, yeah. I think if I were doing it at work, I would be using something. We have this, I have a tool called Enterprise Architect. It basically allows me to start designing data and starts, like, lets me lay out some classes and kind of what things would look like, and then I get an idea of just,like what my model would be, what the interface might look like.

[00:28:12] **Carol:** And then from there, I would just pick out a JavaScript library to do most of the work with,

[00:28:17] **Carol:** because that's so easy.

[00:28:19] **Adam:** you went through the whole stack in like two sentences there. Database, classes, model, and the, and the interface and JavaScript library. Wow.

[00:28:30] **Carol:** Yeah, I, I really like my favorite way to start something is on the whiteboard. So the enterprise architect tool is basically like using a whiteboard. I can just start typing out some, like a few tables and what the columns are going to look like, how they're going to relate to each other and then throw on what I think an interface for that might look like.

[00:28:47] **Carol:** So I mean, it's just like using a big whiteboard and drawing it out and then from there picking out, like I said, Any JavaScript library is good with me because it's, they're so much easier to learn. And then just something that other people could pick up with too would be great.

[00:29:01] **Adam:** So I'm reminded of something we discussed on a recent episode. That's Gaul's Law, right? and Carol, I don't think you were here for that. But basically, yeah, yeah. So we talked about different laws of software. I don't know if you've been listening to those episodes. and one of them was Gahl's law, which says that a complex system that works has evolved from a simple system that worked, a complex system built from scratch won't work.

[00:29:23] **Adam:** Right. And so.

[00:29:24] **Ben:** favorite loft.

[00:29:25] **Adam:** Yeah, what you're talking about reminded me of that. It's just like, you know, if you're talking about starting something from scratch, really the best approach seems to be start as small as

[00:29:34] **Carol:** Yeah, and that was my thought. I literally, like, all I need for it to work, like, in my brain is a list

[00:29:42] **Adam:** Mm

[00:29:42] **Carol:** the ability for someone to put their name next to it or add to the list for anything blank. So just a blank one, hit enter. Now you have a new item and that's what you have assigned to it.

[00:29:53] **Adam:** Right. Yeah, so I guess the, the, the place that I would start mentally is like this, the absolute, you know, MVP of this product would be like a Google doc that anybody can edit, right? You just make it totally public and it's got a title that says Carol's Barbecue and anybody can edit it and they can just say, okay, you know, my name is Adam and I'm bringing the beans, right?

[00:30:17] **Adam:** And so you want something like, okay, Google Doc could work, but that's a little, crunchy, I guess is a word that I like there. so like, you know, what is, what, what can you take from that? Go ahead.

[00:30:27] **Carol:** I was gonna say, a Google Doc feels like the anti software engineer approach,

[00:30:31] **Adam:** Yeah.

[00:30:32] **Carol:** you know?

[00:30:33] **Ben:** was just going to say the, the two sort of limiting factors when I think about starting something new are, do I need security or, or, or what are the trade offs that I'm going to make with security and do I need a database? And if I, you know, like, how do I, I guess more, more, more accurate, like, how do I persist data?

[00:30:55] **Ben:** So if, if you're coming up with a list where multiple people can collaborate on it, even if it's just, you know, a bunch of input boxes or something, you know, how does everyone get to that? Is it just a. Quote unquote, sufficiently complicated URL that no one can guess, or do people have to log in or do you send them a magic link, you know, once you figure out

[00:31:17] **Adam:** Or does it matter if they can guess it?

[00:31:19] **Ben:** right, yeah.

[00:31:20] **Ben:** Then like, you know, is this mission critical data? You know, this is, these aren't nuclear codes. These are, these are bean recipes and folding tables and that's, I go back and forth on, on how I answer those questions because. On one hand, there's, I can try something totally new that I haven't tried before, and maybe I don't know how it's going to work out.

[00:31:39] **Ben:** And I don't know how to answer those questions, or I can do something more traditional and I know how to answer those questions, but then I don't, it's more about actually just building the product and not learning something new. And I don't always know where to draw that line very well.

[00:31:53] **Carol:** I'm completely with you. I had thought that through kind of in the beginning of how do I make sure nobody gets to it? And then I realized I don't care if anyone gets to it. They're just going to insert a bunch of data and I'm going to see that it's wrong. And it's not like I'm storing anyone's email address or a real name.

[00:32:10] **Carol:** It's just a first name. And only I know what that name associates to. So I think initially it's just get it out there, then start learning on it. And I know I'm not learning a ton up front, but starting new is learning for me. I have almost always been part of projects and applications that have been established.

[00:32:27] **Carol:** So there's only been a few times I could think about that. I have actually went and. Zero out. That just doesn't exist in my world.

[00:32:38] **Ben:** So one of the other ways that I tend to think about this, And this does this, this is all theoretical at this point. I, these aren't things that I've actually acted on, but I will think about a platform that I might want to learn more about. So as an example, CloudFlare, which I think a lot of people know as a CDN content delivery network, also actually has a bunch of other services like persistent object storage.

[00:33:01] **Ben:** They have an S3 compatible storage called R2. They have Edge workers, so you can move processing to the points of presence around the world. They have. key value store functionality. So you can have kind of these centralized databases. I, I, I'm not really talking here from experience, just from little tidbits that I've heard.

[00:33:19] **Ben:** So. I could, I could see myself approaching a new project where I say, okay, I want to build this all on CloudFlare. Given that constraint, what does that mean in terms of what languages can I use for the server side processing? Can it have a build step? You know, how do I store data? What kind of stuff does it give me out of the box?

[00:33:42] **Ben:** Or you could use, you know, Azure has a bajillion services as well. I assume that answer a bunch of these same questions. I was listening to a podcast the other day. They said. Amazon just announced some sort of new service that's geared towards app development. I don't know what that entails, but I could see picking a platform first that you want to focus on and then, and then kind of going from there as being helpful.

[00:34:06] **Carol:** Yeah. Azure's what I have to use at work. So let's pick another one. Yeah,

[00:34:12] **Adam:** you know, way of thinking about it, right? Like, okay, I'm going to know Azure because that's what I work with all day, every day. So let me learn, let me do AWS so I can have that feather in my cap too, for sure.

[00:34:23] **Ben:** I was just listening to an interview at the founder, I think it was the founder of some service called render. com. And basically from what I gathered on the interview, you just give it a GitHub repository. It will containerize the code for you and then deploy the container on their services.

[00:34:44] **Carol:** dude, that's too fancy for me.

[00:34:46] **Ben:** I, I don't know, it sounded, it's just, you know, the, I, I've, I've used netlify.com to point things at GitHub, and then it deploys static sites.

[00:34:56] **Ben:** But I, I think the render.com stuff also has more dynamic stuff, so it felt like kind of that fun medium where it's, it's click, you know, pushed to GitHub and maybe something deploys automatically, but it's not just a static site. is kind of in the realm you'd be in. so exciting thinking about new work.

[00:35:15] **Carol:** And see, it's so scary to me.

[00:35:16] **Ben:** so scary.

[00:35:17] **Carol:** I'm like, if someone could just spin it up for me, then I probably would be more likely to, like, see it all the way through. The first step's the scariest.

[00:35:27] **Adam:** So

[00:35:28] **Carol:** I wanna do it. I really wanna do it.

## [00:35:29] Working on a MVP

[00:35:29] **Adam:** Yeah, for me, the first thing I, I, I can't stop myself from thinking about things this way. It's like, I always start to think about, like, minimum data model, right? So, you know, I'm thinking you got some sort of event thing, because you, you know, it's gonna, the goal is to eventually branch out past a single event.

[00:35:45] **Carol:** Yeah, yeah.

[00:35:46] **Adam:** So, you got some sort of an event identifier and a name, and then you've got lists, and, and, you know, every item in the list can have, like, the name of the person that's bringing it and what it is, right? So it's really just like four pieces of information, you know, two in each table. and like the way that my brain works is I would create those two tables and the four columns, and then I would just populate the tiniest amount of data.

[00:36:10] **Adam:** I would create the one row of event data, and I might create one or two rows of like item data for that event, manually drop it in the database, and then I would start to work on the UI to like, you know, okay, here's. You know, the, oh, that's the other thing. So then, you know, again, this is kind of how my brain works, right?

[00:36:26] **Adam:** So I, as I was getting to that part where, okay, you know, I'm gonna have to write the UI so that it looks up that event. Well, okay. So you can either have the, id be the, the part of the yell, URL, or you can have like some sort of like slug column in that, in, in that table. And, and then just display that stuff.

[00:36:46] **Adam:** And to me, like you were talking about earlier, Ben, like, does this need to be, authenticated, secured, right? Like I could see a way. That you wouldn't have to, but the question then becomes like, am I becoming too clever? Right? Like you could just, you know, on the client side, you could have the client set up to like, just create like four or five UUIDs and just concatenate them together.

[00:37:10] **Adam:** And like, that's my, that's me, right? That's my ID. Just toss that in local storage. It's always available. if it's, if it's not there, then you've never been to the site before. Generate a new one, toss it in local storage. And now every time you come back, it's right there. You're, you're already quote unquote logged in.

[00:37:23] **Adam:** I know who you are. I can pre fill your name when you do that. I'll save it from the last time that you did it. But like, is, is that going to be shooting yourself in the foot? I don't know.

[00:37:34] **Ben:** Well, you can always migrate stuff. I, I think you have to, this took me a long time, but you have to be comfortable with the idea that data and approaches change

[00:37:45] **Adam:** Mm

[00:37:46] **Ben:** and you can do stuff about that. You don't, you, you never, you. You're never stuck in cement. Like things might be difficult and you can make unfortunate decisions, but there's always a way to code yourself out of that in a, in a, in some process, hopefully in a point in time so that you never have to think about it again.

[00:38:05] **Ben:** But don't be, the trap that I've fallen into is being so afraid of making the wrong choice that I don't make any choice.

[00:38:12] **Adam:** hmm. Mm hmm.

[00:38:14] **Ben:** I've just begun to take it on faith that I can get out of my problems. The, the, the, the, the thing that I struggle with a lot, because I've been doing a lot more MVP style thinking lately is I don't want to jump right into a complex front end framework, like Angular, like Svelte.

[00:38:33] **Ben:** The problem is,

[00:38:34] **Adam:** Cool fusion.

[00:38:36] **Ben:** well, the, the, I do like, I, you know, the, I'm going to, you know, someone renders a page, then they submit a form and it posts back to the server and the server renders another page. Like that's really the easiest possible thing to get up and running.

## [00:38:49] Styling Frameworks

[00:38:49] **Ben:** The problem is. The things that the frameworks do so well that I feel like hasn't really been solved in a, in a, in a way that I love is styling, you know, we all know CSS here, but the things that things like Svelte do really nice is inside a component, you have a class called label that doesn't conflict with another component that also has a class called label because everything gets scoped during compilation, unless you're going to use an atomic CSS framework, like And I think there's a couple of others that people like, I just feel like that has not been answered well yet in a multi page application, submitting forms, navigating from page to page.

[00:39:32] **Ben:** And that's, that's what I still don't, to this day, I still don't know how to solve that problem well, except for making really weird class names that I actually apply manually in my HTML, which is kind of stupid. So I tend to make stuff really ugly at first. Almost without CSS at all, like just semantic H1s and H2s and paragraph tags on our list.

[00:39:56] **Ben:** But then I never quite know how to go back and actually make it look good without adding the complex UI frameworks.

[00:40:04] **Carol:** You mean you don't know how to go back and make your code look good? Not that the site that's

[00:40:08] **Ben:** Yes. Yes.

[00:40:09] **Carol:** Yes. Okay. Yeah.

[00:40:11] **Ben:** And I just can't bring myself to use Tailwind. And that's not a hate on Tailwind. I just, I don't know, for whatever reason, I don't want to use it.

[00:40:19] **Carol:** Who uses Tailwind? Adam, you use Tailwind?

[00:40:21] **Adam:** I

[00:40:22] **Carol:** You have spell,

[00:40:23] **Ben:** Like half the world uses Tailwind from, from, you know, if I went according to Twitter.

[00:40:28] **Adam:** Yeah. It's very popular and it's increasing in popularity for sure.

[00:40:34] **Ben:** And I think part of it. Is the tooling in that the thing that I'm complaining about that, unless you're going to use a robust front end framework, there's not really a good answer to this stuff. And I think that the answer seems to be, well, there is no answer. So we're going to just do something totally different.

[00:40:50] **Adam:** Yeah. So I feel like one of the reasons that people have been gravitating towards Tailwind is it gives you if you do it like right or not right as in there's a wrong way but like if you put in the effort you can make it so that as a developer you can just add those utility classes to your divs or whatever and it styles things right and then when you compile the application you know that div just ends up with one class on it and that class has all the various properties as needed so like it kind of transforms.inline class names into, what is the, the word that I'm looking for, like a CSS that's, that's detached from, separated from your, your document. Right. I feel like that should in theory, satisfy the, the people that, that are like, well, but what about separation of concerns? And, you know, I don't know.

[00:41:42] **Adam:** Obviously there's some angst in me over this topic. Right? Like, we should just move on.

[00:41:49] **Ben:** Yeah, yeah, yeah. We're, we're, we're off on a

[00:41:52] **Carol:** Side tangent.

## [00:41:53] FedRAMP

[00:41:53] **Carol:** Well, I have another side tangent real fast. I have a little more push at work now or a little more voice, I guess. People listen a little more. So, in two weeks or a week. A week out now, we get to revisit the topic of feature flags

[00:42:08] **Ben:** Oh, yes.

[00:42:09] **Carol:** has an improved version that's I think it's on prem.

[00:42:13] **Carol:** They have an improved version that's class, that's government, approved. So it's already on our approved list of things we can use. So we're going to resurface that topic again, because the feature flags that have been implemented aren't that great. And. My view is that if someone does it really good, then we shouldn't try home growing that ourselves.

[00:42:32] **Carol:** Like, let's just pay for a product that does it well and that we can maintain.

[00:42:37] **Adam:** yeah, it always goes back to that. Like, is it your core competency? Is it your differentiator?

[00:42:42] **Ben:** You have to, I assume I only learned about this not too long ago, a certification called FedRAMP.

[00:42:49] **Carol:** Yep. Yep.

[00:42:50] **Ben:** like things that become FedRAMP compatible or certified, I guess would be maybe the right term. Then the government can use them. Otherwise they can't use them. So I

[00:42:59] **Carol:** Yeah. There's like a, my charcoal is a medium fed ramp now. So there's like a 400 ish page. Thing we have to read through if we want to completely understand it all. But basically, software gets approved through FedRAMP and it gets assigned a level of security, meaning that it's low security. So if the software you're writing is low, then you can use the low tools or higher.

[00:43:26] **Carol:** if what you're writing is medium, you have to only use medium tools or better. So if you're storing classified data, you can only store. Use tools that are approved at that high and highest kind of level.

[00:43:38] **Adam:** I'm sorry, this is just the, the person in me that watches way too much YouTube, but I couldn't help but like reinterpret or reimagine what you're talking about as a tier list. You know, they do that like S tier, A tier, B tier, C tier. Ben is just looking at me

[00:43:51] **Ben:** No, I have no

[00:43:52] **Carol:** I don't know what you're talking about. Yeah.

[00:43:55] **Adam:** who just added himself as the millennial. I don't even know if I can explain it. It's just, it's a ranking thing and people do like tier lists for everything. They're like, okay, we're going to, today we're going to rank JavaScript libraries and they just have a whole bunch of like, you know, icons that represent the different JavaScript libraries and they have, it's, it's like horizontal, it's not a chart.

[00:44:16] **Adam:** I don't, it's just like a, it's kind of like a table or a grouping thing. And you're just like, okay, S tier is the absolute best, like almost overpowered, and then you've got A tier, which is like really good. B tier, it goes all the way down. And you can have like. D or F tier that are like, these are trash.

[00:44:30] **Adam:** Just

[00:44:31] **Ben:** well, I have seen two dimensional graphs where it'll be like, like cost and complexity, and then they take a bunch of. different products and sort of cluster them around on this two dimensional graph and like, here's your Cisco systems up in the top, right. And then here's your Heroku's down and then kind of the mid bottom kind of stuff like that.

[00:44:52] **Ben:** Kind of sounds like maybe it's a little bit like that idea.

[00:44:55] **Adam:** YouTube for tier lists and you'll see.

[00:44:57] **Ben:** And

[00:44:59] **Adam:** you'll, you'll find, you'll like watch one video. You'll watch two minutes of one video and you'll be like, okay, I get it. And this is, this is obnoxious and I'm never going to look at this again.

[00:45:07] **Carol:** all I'm picturing is a food pyramid turned like upside down with the biggest thing on top. That's what's in my head right now. So yeah, so that was what I wanted to talk about you guys. Just the idea of starting something new and how it sounds really exciting and it doesn't sound too scary that I'm not going to do it.

[00:45:26] **Carol:** So I think once August rolls around, I'm going to. Gonna get at it cause that's when our schedules settle back down and that's when I have time again to work outside of work, a

[00:45:36] **Adam:** I would really encourage you to put thought and effort into making it as simple as possible for the people that are going to contribute.

[00:45:45] **Carol:** hundred percent.

[00:45:46] **Adam:** Yeah, not that this is something that you don't already know, but like, you know, for the benefit of the listeners, right? you know, if you could make it so that I can just, you know, text you a link on your phone, and you write there on your phone, you could just be like, My name is Susan, and I'm bringing potato salad that has way too much dill in it. then, then, then, and that's all you have to do. And like, and if you pull it back up on your phone next week, you can edit it and say, okay, fine, I'm on. I'm only gonna put a normal amount of dill in the potato salad. Like,

[00:46:15] **Carol:** I think that would be so cool.

[00:46:16] **Adam:** that would be, that would be killer because like no login. No registration. You can edit your own stuff.

[00:46:21] **Adam:** Like if you can get those three things,

[00:46:24] **Carol:** Pretty good. Yeah.

[00:46:25] **Adam:** I think, yeah. Yeah. I think that he has real potential.

[00:46:28] **Ben:** An interesting little anecdote, which I never quite know how I feel about this, but years and years ago, maybe like 20 years ago, almost. I worked at a company and on Fridays, the whole office. And when I say the whole office, it was like 12 people, the whole office would order lunch together. And I don't remember what site we were using at the time.

[00:46:47] **Ben:** It was like an online ordering site where the boss would go in, he would start a shopping cart, and then he would just send the URL in AOL instant messenger to everybody. And anyone could just load it up on their, on their web and start adding stuff to the cart. And we thought it was a feature and it turned out that that was like a huge security bug

[00:47:08] **Adam:** Yeah. It like had

[00:47:08] **Ben:** could just guess other people's, yeah, you could just, and so they, they removed it and we're like, what?

[00:47:14] **Ben:** You removed it? That was literally the best feature of this website was being able to use other people's shopping carts.

[00:47:21] **Adam:** I feel like I've seen that as like a Slack plugin or something like that.

[00:47:24] **Ben:** Oh, that would be cool,

[00:47:26] **Carol:** That would be neat. Yeah. I know you can do it on Uber Eats and stuff, but I think you have to be logged in and then someone has to invite you to it and your login gets added to it.

[00:47:36] **Adam:** Yeah. And you want to, you want to avoid that at

[00:47:38] **Carol:** Yeah. Yeah. Yeah.

[00:47:40] **Ben:** yeah, exactly. That's what I'm saying is it was so awesome that you could do that. I could imagine you having a, like a, a group, like a family group text message and just dropping this link. Like, Hey guys, remember the picnics coming up on Saturday here. Here's the link in the group chat.

[00:47:54] **Adam:** Oh yeah. And you know what else would be cool is like a way maybe for the organizer or maybe anybody could do it. Like you can have, okay, this at the top, these are the people who have signed up to bring things. Maybe at the bottom of the list is like people who are like, we should really have, we need, we need at least three folding tables, right.

[00:48:11] **Adam:** Who, who can bring that. And so they're not saying I'm going to bring it. They're just saying, we need.

[00:48:15] **Carol:** Yeah, yeah, and that's where I was like, I liked at the end, giving people the option to add to, even if it's not something that they're bringing.

[00:48:22] **Adam:** Oh, yeah.

[00:48:23] **Ben:** Well, it's like a, almost like a wedding registry. You just like, here's all the stuff we need. buy some of it.

[00:48:30] **Carol:** Yeah. And way down the road was the idea of templates too. Like, Oh, here's a barbecue template. Don't forget to add charcoal to your list. Like lighter fluid. Someone should probably bring a lighter, like those type of things.

## [00:48:43] Starting with a Single Page

[00:48:43] **Ben:** Oh, as a good forcing function, one really good first step could be, I have an index HTML file or PHP or whatever you want to use. And all it says is I got the beans and you're like, I just got to deploy that somewhere. And if I can, like, if I can do just that, and I've already had to answer a number of questions, like what's the domain going to be?

[00:49:08] **Ben:** Was it available? Where's my domain registrar who is handling my name servers? You know, how do I get that file into production? And if you can do just that with basically zero technical overhead, right? It's just a plain text file. Then you, I think you set yourself up to be able to start to answer these other questions with a lot less friction.

[00:49:30] **Carol:** Awesome. Yeah. I think that's a good idea. It makes it sound a lot easier to start.

[00:49:36] **Ben:** Yeah, exactly. I mean, it's, it's easy in that the code you write is one line of code, but it's challenging because actually to get that line of code from your computer to a, you know, publicly accessible URL, you have to answer maybe some tough questions, but, but, I think that'll, it'll force you to concentrate on the really important stuff first and not the.

[00:50:00] **Ben:** You know, going down some rabbit hole of what's the framework I'm going to use and what am I, do I need a new icon library for this,

[00:50:07] **Carol:** Oh, geez, stop, Ben.

[00:50:08] **Ben:** I

[00:50:09] **Carol:** I'm gonna quit.

[00:50:11] **Adam:** And do you want SVG or PNG or make it a font?

## [00:50:16] SVG Exploits

[00:50:16] **Ben:** Once I discovered SVGI, I'm like, I can, I feel like I can never use an icon that's made out of an image anymore.

[00:50:24] **Adam:** This is definitely a topic for another show, but I, I saw something today that was like, it made me never ever want to support, like a user upload of SVGs for anything ever again.

[00:50:35] **Ben:** A user upload, like people can upload a file, an S VG file.

[00:50:39] **Adam:** Correct. Yeah. So like we have,you can make attachments to a tickets in our ticketing system. Right. And so you can attach a screenshot or a word doc or zip file or whatever. And like, and those will, you know, if their images will display them in like, you know, you, you know, Ben attached screenshot.

[00:50:54] **Adam:** png and you click on it and it will show it in like a little modal pop up. Here's your screenshot and you can click on it to go full size or whatever.and basically SVG is just like a, it's a attack vector for anything you want.

[00:51:09] **Ben:** Yes. Yeah. Absolutely. It's, it's like, do you remember the, I don't know if any of you here were affected by the log4j like zero day vulnerability?

[00:51:20] **Adam:** that on the show.

[00:51:20] **Ben:** Yeah. Okay. And, and the issue there was that they decided in, in, in order to make log4j, this is for the listeners, in order to make log4j a very flexible logging library, they allowed it to basically execute a bunch of arbitrary commands.

[00:51:36] **Ben:** One of them ended up being like, reach out to this other URL and get some information, and then people realized they could use that to make internal calls from within the network. And SVG has things like that, where it's, you can just have elements, markup elements inside your SVG document object model that are like, just pull in this other random text file and render it.

[00:51:58] **Ben:** And, if that other random text file is like, You know, slash Etsy slash passwords or something. You know, I don't know what the exploits are. It was like, Oh yeah, I'll just pull that into my SVG. No problem. Yeah. You're like, Oh, you have to make it so flexible. So yeah, I agree. We used to try to process SVG using graphics magic or image magic.

[00:52:22] **Ben:** Yeah. And we had to solve a bunch of exploits that way as well.

[00:52:28] **Adam:** And, there'll be dragons here.

[00:52:30] **Ben:** Yeah. Yeah, exactly.

## [00:52:33] Patreon

[00:52:33] **Adam:** Well, then this episode of Working Code was brought to you by Susan and her potato salad with way too much dill in it. Susan, we get it. You like dill. and listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:52:49] **Adam:** Our patrons cover our recording and editing and transcription costs. And all the extra ands that I put in every sentence, those cost money. and we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo. You guys rock.

## [00:53:02] Thanks For Listening!

[00:53:02] **Adam:** We are going to, go record the after show.

[00:53:04] **Adam:** And, it's only just occurred to me, I have to ask Ben about Too Many Cooks. So I, I don't remember if we brought it up on the main show, or if it only came up in the after show. But I'm, if you know what Too Many Cooks is, it came up a couple of weeks ago when Ben was on the show. He was going to go watch it.

[00:53:19] **Adam:** And, and, we have to follow up on that. So that'll be interesting. you'd like to help us out, you can go to patreon.com/workingcodepod. We'd love to have you join the team. I would also love to have you join our discord workingcode.dev/discord.

[00:53:32] **Adam:** It'd be a great place to have you come hang out, talk to like minded, coders like yourself and just hang out. It's a great place to, to socialize and have fun. That's it for this week, we'll catch you next week, and until then heh

[00:53:43] **Ben:** folks, your heart matters.
