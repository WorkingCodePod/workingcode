---
title: "181: More Laws of Software"
description: "On today's show, we continue our discussion of the entries outlined on the website, the Laws of Software. Topics include McKinley's law on boring technologies, Doerr's law on aligning team vision, and Fitt's law on target touchability."
date: 2024-06-05
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/181-more-laws-of-software/id1544142288?i=1000657914410"></iframe>

On today's show, we continue our discussion of the entries outlined on the website, the [Laws of Software][laws-of-software]. Topics include McKinley's law on boring technologies, Doerr's law on aligning team vision, and Fitt's law on target touchability.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[laws-of-software]: https://www.laws-of-software.com/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/181-more-laws-of-software.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Ben:** we swung so hard into the microservices direction. of architectures that we now have literally hundreds of Docker files that may be affected by this. And had we had, you know, a monolith and maybe a handful of microservices, this would not be so terrifying.

[00:00:18] **Tim:** Yeah. But hopefully you have like a non prod version of the RDS that you can test this out on and not be too afraid to break. Oh,

[00:00:32] **Ben:** no, we'll see. Well, I mean, we have stuff, but

## [00:00:55] Intro

[00:00:55] **Adam:** Okay, here we go. It is show number 181, and on today's show we're revisiting the laws of software. I thought we would get in and maybe do some lesser known laws of software this time.but first, as usual, we'll start with our triumphs and fails.

[00:01:07] **Adam:** Carol is once again not able to join us. She, her power is disconnected while they're getting moved into her house. So, maybe next week. We'll try again. But, in the meantime, I have. two of my best friends in the world, Mr. Ben Nadal wearing a red t shirt and Mr. Tim Cunningham wearing a red t shirt.

[00:01:23] **Adam:** I apparently missed the memo,

[00:01:24] **Tim:** Yep.

[00:01:25] **Adam:** joining us.

[00:01:26] **Ben:** Tim and I are twinning, as they say, I believe.

[00:01:28] **Tim:** Yeah.

[00:01:29] **Adam:** So Ben, what do you got going on?

## [00:01:32] Ben's Triumph/Failure

[00:01:32] **Ben:** I'm going to go a little triumph, a little failure. triumph is last week I talked about how I was feeling very directionless, very rudderless, and I wasn't quite sure what I should be doing with my spare time and what I should be leaning into learning wise. So my triumph is that I have picked kind of a small side project to play around with.

[00:01:51] **Ben:** And what I want to do is I want to create a little companion playground site. For my Feature Flags book. So the Feature Flags talk about how Feature Flags work and they walk through building a little bit of a toy application that manages Feature Flags. And what I'd like to do is now build a little companion site where you can actually log in.

[00:02:11] **Ben:** I say log in in the loosest sense possible. And you can see a list of feature flags and you can turn on and off feature flags and you can change the rules. And then maybe, I don't exactly know how I'm going to illustrate this, but maybe I could give some sort of a, a data grid where I have people on the left and feature flags on the right, and it'll show which users getting which feature flag based on, on the targeting.

[00:02:34] **Ben:** Just something that would kind of illustrate the, the, the concepts. So I'm feeling good about that. I'm excited to have a little bit of a direction, a little bit of a place to focus my, my mental energies and solve some interesting problems. So that's my triumph. And as a failure, I just want to say tech debt is real.

[00:02:51] **Ben:** And it was putting me in a mood, at work. I've mentioned this before. I'm working on this export system for people's documents. And part of what I'm doing is having to recode some of the old logic that was built in a bunch of different places and in different technologies. And I'm trying to coalesce it into this little project.

[00:03:12] **Ben:** And I've had to reimplement just the bonkers, bonkers stuff. And it's one of those things where we made a bad choice on how we want to store some data 13 years ago. And now every time you want to touch that data in any way, you have to relearn how all those poor choices work and, and all the edge cases and remember how to massage the data to get it to work the way it should have done.

[00:03:37] **Ben:** Had you made the right decision 13 years ago? And I just, it makes me so angry that we didn't go back and fix it when we realized it was a bad idea. And I don't know. It's one of those things you probably couldn't convince people that it was the right thing to do at the time to fix it, but it just kept costing over and over and over again, and it is costing me now.

[00:03:57] **Ben:** And it's just very frustrating.

[00:03:58] **Adam:** So you started this new side project. What are you going to use for feature flags? Like, are you actually going to wire in like LaunchDarkly or

[00:04:07] **Ben:** No, no, no. The it's so I, I made a repository on GitHub. I think it's called like Feature Flags Playground or something. and, and it's going to be totally public repository. And then it's just going to be a site and I'm, I'm building the feature flags. So you can go in and look to see how they're, one, managed from an administrative perspective, and then two, consumed from a client perspective.

[00:04:33] **Ben:** It's just, it's, it's not supposed to be a very robust implementation. It's more like, you know, if you, if yeah, if the concepts in the book, like aren't quite hitting home, maybe opening up a repository and looking at how it works. In a concrete sense can help solidify the concepts.

[00:04:51] **Adam:** I see. So this is more a GitHub repo than a website that I can go click on.

[00:04:55] **Ben:** It'll sort of be both, it'll be both. The repository is open, you know, it's public, but then it will also be a site that you can go to. So like the site is, you know, the book site is FeatureFlagsBook.com and this will be App.FeatureFlagsBook.Com.

[00:05:14] **Adam:** Okay. And I guess, but you're saying you're going to implement feature flags, right? So, I mean, I guess it depends on how sophisticated you want to make them. Right. Are you just going to be like toggle it on and off for Jane Doe and John Smith or

[00:05:27] **Ben:** wanted to have some light ruling. you know, here's the feature flag, given this user ID, turn this on or given, you know, email addresses that end in this subdomain or, you know, at domain. Turn this on, the, maybe some true false things, maybe some things that are numeric, maybe some, something else, you know, I'm, I'm kind of making it up as I go.

[00:05:49] **Ben:** And I'm, I'm trying to strike a balance between robustness because clearly this is not a production grade feature flag system, nobody's paying me to do this. I don't have that much time. and, and. But I also want it to be not so trivial that you lose the value of what it actually is.

[00:06:09] **Adam:** what technology are you going to be using to, to make this

[00:06:13] **Ben:** But only the most robust technology available.

[00:06:17] **Tim:** you had to ask the question.

[00:06:20] **Ben:** So I, I didn't want to have a database because it's just one more thing to manage. And I, and I, and I just don't want this to be a whole thing. Plus, so the, the repository is, uh, dockerized, meaning it, it uses, Command box, their Docker image, and, you can run ColdFusion.I'm going to try to not even have a build step for anything like the JavaScript and the CSS.

[00:06:43] **Ben:** I'd love to just have it simple enough that it can be just static. And, and I don't want to have a database again, just for no other reason to, to make the development of the containerization much easier. So. And you log in and you are like, you give an email address. I just basically hash your email address and I say, okay, this is your JSON data file, and so I will write a JSON data file to disk, and that is your data persistence.

[00:07:10] **Ben:** And, you know, over time I might just delete those if they get old and, we'll

[00:07:15] **Adam:** And well, I guess, I mean, if the whole point though, is to be able to see different experiences, right? So I want to be able to control. I want to have two logins. I don't want to see like flag on for one and flag off for the other.

[00:07:30] **Ben:** Right. So, yeah, so the illustration of the consumption of the feature flags is going to be, A little challenging. The best that I can come up with so far is some concrete set of user properties. And, and then you can essentially assume that those exist and you can target them. And then I'll give you a grid to show who can see what versions of what feature flags.

[00:07:56] **Ben:** So, you know, it's a, it's a, it's a jump of imagination to say, okay, this feature flag is on. So in my head, I can imagine this user would be exposed to a different experience.but I think it would be nice. You could start to see things like percent based rollouts. So if I could give a, just a sample of like a hundred people, and then you could roll out to say like 30 percent of those people and then see on this little data grid that 30 boxes in this list of a hundred are green and 70 of them are red, you know, you can start to get a sense of, of how you could, you know, Incrementally roll out a feature.

[00:08:32] **Ben:** I'm hoping

[00:08:34] **Adam:** Yeah, that sounds neat.

[00:08:35] **Ben:** you just sent me something. IQ platform feature flags. I don't know what this is.

[00:08:39] **Ben:** So that's a screenshot of my FeatureFlags dashboard that I built, uh, for our product. Oh, I see. Alumni IQ, IQ. I get it.

[00:08:49] **Adam:** yeah, yeah, yeah. Everything is, it, it's funny, This is one of those things, I'm sure I've brought it up before, like I will never, ever, ever, ever name a company using a portmanteau ever again because everybody either mispronounces it or uses like acronyms or shortenings that just drive me bananas.

[00:09:08] **Adam:** For some reason, everybody always wants to shorten our name to AIQ. And so just as like a subtle passive aggressive, like you're wrong. I always like, if I send them documents or whatever, it's like IQ underscore, blah, blah, blah, blah, right. Like just to, just to drive it home. Like, I don't know, like somebody spells your name wrong and you're just like, you know, you make sure you spell it correctly in front of them.

[00:09:32] **Adam:** Very obviously.

[00:09:33] **Ben:** totally. I totally get it.

[00:09:34] **Adam:** Yeah. So, I mean, yeah, I mean, this is a little bit of a self promotion, right? So I have that little feature flags engine that I built in CFML. And I have this, the screenshot is, it's actually a Next. js application. It doesn't have a database. It uses a JSON file.

[00:09:52] **Ben:** That's what I'm talking about.

[00:09:53] **Adam:** Right. and I mean, the way that this one works is like, if you make a change in the dashboard, it writes it to the JSON file and then submits a GitHub pull request to update the

[00:10:01] **Ben:** Right, right, right. Exactly.

[00:10:03] **Adam:** which is to be fair, now that we've lived with it for a while, not my favorite thing.

[00:10:10] **Ben:** Hey, you know, it's better than nothing.

[00:10:12] **Adam:** Yeah, exactly. But like, okay, so I built that, right. And then, you know, whatever, sometime in the next year or whatever, we started like requiring all of our commits to be signed. and so that's like a hoop, but that's not currently jumping through. So I always just have to, when I get one of those pull requests from an edited feature flag, I have to say like, Oh, you know, bypass this branch protection that it's not signed.

[00:10:34] **Adam:** and then what is the other one? I don't know. I feel like there's a second requirement that it's not doing because of, because it's doing that. Yeah,

[00:10:44] **Ben:** pull request is, but I can tell you that every time we've run up against that problem at work, we have just disabled that feature.

[00:10:53] **Tim:** That's on brand.

[00:10:54] **Ben:** Yeah. Cause you know, cause we're on such a limited team right now. So inevitably someone will have to go in and work on some other team's repository and that team doesn't exist anymore. And they're like, Oh, this needs to be signed. Like, yeah, I'm just going to turn it off. Problem solved.

[00:11:10] **Adam:** that's different. You know,

[00:11:11] **Tim:** Yeah, that is different.

[00:11:12] **Adam:** right enough into the sunset,

[00:11:14] **Ben:** I don't even know what it means for a pull request to be

[00:11:16] **Adam:** I mean, it, it, it's just that like you literally sign the commit, right? So you, part of the commit includes a cryptographic hash of the commit itself, plus your like public key, basically. so

[00:11:28] **Ben:** Like what's

[00:11:29] **Adam:** could be verified that you were the one that committed it.

[00:11:31] **Adam:** So here, here's why it matters. if somehow I get put, push access to your Git repo and then it, it would be without requiring signed commits. It would be trivial for me to push additional commits that look like they came from you, because I would just say, you know, my email address is ben@bennadel.com

[00:11:50] **Adam:** and, you know, and, and so that's it. Like, that's all you need to do is say this, this was committed by Ben Nadel, whose email address is ben@bennadel.Com. And, and it looks like you, you committed it unless

[00:12:02] **Ben:** this is one of those situations where I've been integrated with GitHub for so long that I don't even remember setting up

[00:12:10] **Adam:** you probably,

[00:12:12] **Ben:** on my computer,

[00:12:14] **Adam:** yeah, I mean, yeah, you probably aren't signing your commits

[00:12:18] **Ben:** right. But, but

[00:12:19] **Adam:** extra hoops to do it.

[00:12:19] **Ben:** only to say that I don't even know what's getting sent under the hood or whether or not I needed to download like an SSH key at some point to do something. It's, it's, it's one of those things where this is not a thing that I do more than once every eight years. And so I have zero mental model or

[00:12:37] **Adam:** time you get a new computer,

[00:12:38] **Ben:** Yeah. I have to look up to see what any of this actually means. Anyway. so that's my triumphs and fails. I don't want to go too far

[00:12:45] **Adam:** got off on a tangent

[00:12:46] **Ben:** Yeah, yeah, yeah. So, Carol's not here, so I'm going to kick it over to Tim. What you got going on?

## [00:12:51] Tim's Triumphs

[00:12:51] **Tim:** So I've got two triumphs, actually. One personal triumph. So my daughter graduated high school on Friday morning at 9 a. m. And, she gave a fantastic speech. I posted it on. I think I posted, did I post it on

[00:13:06] **Adam:** Yeah. You posted it on discord.

[00:13:07] **Tim:** I posted on discord. Gave a really good speech. She focused on being kind and, it's very on brand for her.

[00:13:13] **Tim:** She really is kind of one of the kindest, most thoughtful people I know. She, in middle school, she won an award or tied for an award for best Most polite. So her and another girl were the most polite and they're both going up to the stage to

[00:13:27] **Ben:** After you,

[00:13:27] **Tim:** presentation. Exactly. So the other girl that they're like looking who's goes first and my daughter like, you know, gestures after you and then the girl goes forward and like, yeah, she just won.

[00:13:37] **Tim:** She just broke that tie right there. But yeah, she's very kind, but she gave a great talk. And then we had like 80 people over to the house on Sunday and had a taco party. That's what she wanted, a pool party. So we had people swimming and eating tacos and. So, it was,

[00:13:51] **Ben:** Yo, putting that, uh, septic tank on, on trial there.

[00:13:55] **Tim:** Well, yeah, yeah, we, we put the bathrooms out of order, so they had to do it at home.

[00:14:01] **Adam:** You gotta do it like PCU, stand at the door. Number one or number two.

[00:14:05] **Tim:** yeah, everyone gets one square of toilet paper. Yeah, so that was good. But yeah, the other triumph was, I was talking about how I was going to Nashville last week to go to the National Association of Mutual Insurance Companies, or NEMIC as we call it, and I was really worried that I wasn't going to have anyone show up to my, talk on AI.

[00:14:25] **Tim:** One, when I looked at the app, so, you know, most of it's have some sort of downloadable app. It didn't have, it just had the company name and that we were doing a fast pitch and didn't have any info on what we were talking about or what, you know, who we were and it was not on, so all the topic rooms are in one, level of the hotel. And we were on the bottom level, like behind the restaurant, behind the bar.

[00:14:52] **Tim:** I'm like, Oh, geez, you know, it's like, no, one's even going to know where this room is and you know, they didn't say what we're talking about. And I was kind of looking at some of the other, like. presentations that were going on that none of them were really extremely well attended. And, but surprisingly my AI phone call must've worked because that in combination with the email, I didn't get to do SMS messaging, unfortunately, I just ran out of time.

[00:15:17] **Tim:** But, so some guy walked in, I saw his name, I don't want to say his name here, but his last name was Carpenter. And, I, I recognized that name from one of the people I called that actually interacted with the ai. And I go, did you, are you the guy who said maybe to the online robot that called you?

[00:15:32] **Tim:** And he goes, yeah, that was me. I'm like, yeah, I thought that was okay.

[00:15:36] **Ben:** funny.

[00:15:36] **Tim:** he, he was very engaged with the, topic. In fact, everyone was, it turned out very well attended. one of the people said it was, it was probably, besides the keynote is probably the most attended session

[00:15:46] **Ben:** Yo,

[00:15:46] **Tim:** that had been there.

[00:15:48] **Tim:** And people were very engaged. you know, there's a lot of questions. I got a lot of, a lot of good feedback and, and, and other people asking me to come talk to like do a presentation for their company on AI. So,

[00:15:59] **Ben:** Oh, wow.

[00:16:00] **Tim:** so yeah, it got very well attended and, hopefully it'll drive, some more conversations, some more sales.

[00:16:06] **Adam:** That's awesome, man.

[00:16:07] **Tim:** Yeah, and I got, and I got to meet, I'm sorry, were you going to say something,

[00:16:10] **Ben:** I was going to ask, I knew you were playing around with synthesizing your voice. Did you end up using your own voice or,

[00:16:17] **Tim:** Well, I did. So my voice, after I listened to it a couple of times, the quality, the background noise, a little bit of background noise there. I need to like, really like get into a clean room with, you know, no echoes and just do a good recording. But, so I did use one of the pre can voices that we had, but then I had it call me back.

[00:16:35] **Tim:** And I, and I told him the story. I'm like, you know, I read in the news, you know, how someone used Joe Biden's voice to like discourage people voting. I said, I just wondered how hard that was. And I said, here's what, five minutes of just reading something in training and AI on how to create your voice. And I had it call me, and I'm holding the microphone like, hello, this is Tim.

[00:16:54] **Tim:** And the AI goes, no, this is Tim. I'm like, no, I'm Tim. And we had a little conversation, it was more for comedic effect. It was back and forth. I said, no, I'm Tim. And so it got a good laugh. So,

[00:17:05] **Ben:** very cool, man. That's awesome.

[00:17:07] **Adam:** And did you have any like negative backlash from making the phone calls?

[00:17:11] **Tim:** so one of the guys, the fact that Carpenter guy, he's like, well, you know, our, our brand is that we had like a, they had a motivational speaker and we were like pretty much right after his keynote and, the motivational speaker was like, Saying your brand is what and blah, blah. And they're like, our brand is that, you know, we have a really tight relationship with our customers, you know, Geico and all these other people.

[00:17:33] **Tim:** You're just somebody else. But you know, we, you know, we've known these people for years and we, they're like our neighbors and like, you know, our, our thing is our customer service. And so he was kind of pushing back on that. And I was like, well, I get that. I said, but like Geico or, you know, One of the big insurance companies.

[00:17:51] **Tim:** Do you actually have 24 7 customer service where they can talk to a person anytime of day or night? He's like, no, we're, we're from eight until five. I'm like, so if they need to call at like 6 PM, what do you do? He goes, well, they just got to call back. I'm like, don't think of this as AI replacing your, your, your people.

[00:18:12] **Tim:** This is AI supplementing them in the after hours where you can't afford to hire people 24 7. At least they can get a good answer or an answer to say, you know, the basics about what they need to do. If there's something they need to fill out, a place to go, a place to visit, something informational. And then at the same time, The AI can like store that or send an email to your customer service or send saying that so and so called yesterday at six.

[00:18:39] **Tim:** Here's what happened. And then, you know, Susie or whoever next day can say, Hey, I understand that you guys had a fire at your farm. Do you need us? What do you need us to do? You know, and I said, it's a supplement. So he's like, Oh, okay. Yeah. I didn't think. Yeah. Yeah. But we need that. That's great. Yeah. We need that.

[00:18:54] **Tim:** So it went really good. Yeah,

[00:18:57] **Ben:** around.

[00:18:58] **Adam:** yeah, did that happen in your session so that like the whole audience got to see

[00:19:01] **Tim:** the whole audience heard. Yeah, it was cause we had like a 10 minute presentation and then it was like just question and answers. And I had a peaceful pushback and I wasn't like pushing like an AI evangelist. I'm like, I was saying, listen, it's a lot of hype right now. There's a whole lot of stuff that can't do.

[00:19:16] **Tim:** There's a whole lot of stuff they say it can do and it really doesn't do it well. But, it's something you guys need to look at because we had, The guy who was the moderator, he is, he was part of an investment company, a venture capitalist company that works with insurance companies. And he was telling them before I talked, he said, listen, this guy's talking about AI.

[00:19:38] **Tim:** He says, right now that is like one of the top three topics that VCs and insurance companies, the top insurance companies in the world, that's what they're looking at. So you need to listen to this guy and hear what he has to say. And I was like, thanks. I'll pay you later.

[00:19:52] **Adam:** Checks in the mail.

[00:19:53] **Tim:** Check to the mail. So it went good. And I got to see, you know, the. We, we rag on ColdFusion, but the best thing about ColdFusion is the community, the people, the friends that we made along the way. I don't think he was even really a ColdFusion developer, but Andy, Andy Matthews,

[00:20:09] **Adam:** Yeah, he was.

[00:20:10] **Tim:** Was he a ColdFusion?

[00:20:11] **Tim:** I, I, I thought, yeah. So he was a ColdFusion developer back in the day and I've seen him at conferences and he lives in Nashville and I had posted that I was going to be there and he's like, Hey, what you doing? So he lived like, just like 10 minutes away. So he came down to see me and We hung out and talked for probably about an hour.

[00:20:28] **Tim:** It's great. It's like, I don't know what it is. It's like, there's some certain people that you, we haven't seen each other in like over 10 years. And we met and just picked right back up where we left off and it's like no time had passed. The conversation just was going and it's like great conversation.

[00:20:43] **Tim:** And then he headed out and he recommended I go to eat Hattie B's hot chicken. So I went and had some hot chicken, but yeah, it was good to see him.

[00:20:51] **Adam:** Did you get the mouth sweats?

[00:20:53] **Tim:** I did. So that hot chicken, you know, I eat hot food, but I think just the fact they fry it in that hot oil, that the oil like holds on to the, to the hot sauce more.

[00:21:03] **Tim:** It was, it was, it was making me pant. It was, I was feeling it. And the next day, boy, oof. feeling it. That was good stuff though.

[00:21:11] **Adam:** Awesome. I'm glad your, your presentation went really well.

[00:21:13] **Tim:** Yeah, me too. I was, I was really worried. I'm like, it's just going to be me and the other present presenter. We'll just talk to each other, but no, it was, it was really well attended and well received.

[00:21:22] **Ben:** So, you know, feel free to, bypass this question if you want, but I'm just curious with all of the playing around that you did with the bland AI and like, and making the calls and the transcripts, this, thought experiment, how much did it cost? Is it, you know, in the orders of like tens of dollars, dollars?

[00:21:40] **Tim:** no. So I called like 300 and something people, 400 people. I forget the exact number, but it was less than, it was less than 3,

[00:21:47] **Ben:** Nice.

[00:21:48] **Adam:** Oh my goodness. Thanks.

[00:21:49] **Tim:** less than 3.

[00:21:50] **Ben:** Awesome.

[00:21:51] **Tim:** And that's what I told them as well. And I also told my, like, it may, AI made my slides, came up with all my bullet points, came up with all my images. So.

[00:22:01] **Adam:** Was that something that you disclosed early on in the presentation or

[00:22:04] **Tim:** No, at the end, at the end. I'm like, how'd you guys like the pictures in here? They're like, yeah, they're weird. They're weird pictures. Like, yeah, AI did that. Like, then all those bullet points, AI did that. So I just gave it kind of the general outline and did the rest. Anyway, that's me. How about you, Adam?

## [00:22:19] Adam's Triumph

[00:22:19] **Adam:** I'm going to go with the triumph. so this actually happened today. we were having a conversation back and forth with one of our customers in a ticket. And, Steve said that, like, she asked, you know, how come it doesn't do this, right? So we have this, I'll just, I guess I'll go ahead and explain it.

[00:22:35] **Adam:** So we have a feature in the product called Wingman, which is, you can set up an event, for registration, right? So you're creating a happy hour, right? You might expect 15, 20 people ish to come to an event like this. and you can expect that number to go down if you like require pre registration, right?

[00:22:53] **Adam:** Like for a thing like a happy hour, people just kind of want to show up.

[00:22:56] **Ben:** Yeah. Yeah.

[00:22:57] **Adam:** But the school really wants to know who's there, who's engaged as an alumni, right? Who should they be asking for money because you're spending a lot of attention on the school, for example. That's not the only thing you care about, but that's one of the, you know, thought processes. and, and so as a way to sort of allow the, like, I'm just going to show up person to, to do that, but also to capture the fact that they were there. we built this feature, we call it Wingman. And basically, you can still set up your event just like normal.

[00:23:27] **Adam:** You can still invite people and they can pre register. That's fine. But we also, under very certain circumstances, like there can So in our system, an event can have multiple activities. Activities can have options. Activities can have sections. You can have products and products can have options. And like five of those seven things can have fees.

[00:23:46] **Adam:** And you know, it gets real complicated real fast if you want it to. But with, for Wingman. there are restrictions. You can only have one activity. It can't have any options, any sections, any products. No, like it has to be free. So if you, if you check all of these boxes of like, make your event as simple as possible, then you can use Wingman and Wingman is, we'll give you a QR code that you just like put on a little flyer on a piece of, on a, on the table or something.

[00:24:11] **Adam:** and when people come, they can scan it and it just pops up a form where they put in like their first name, last name, and email address to say they were there, it's just like, Hey, let us know you were here. And we capture that and we like create a registration for them on the fly and we match that to their database record.

[00:24:27] **Adam:** And so we're like capturing high quality information at the last possible second, right? And so, the, the conversation in the ticket was like, well, how come, how come it's not working? Right. I've created this, I created an event and I'm trying to use wingman. And it's when I go to the QR, like when I scan the QR code, it's not showing me the form, it redirects somewhere else.

[00:24:47] **Adam:** And the answer that she got was, well, it's because your event's not free. Right. And that's one of the requirements. And, you know, I'm, I'm just kind of a fly on the wall. I see all the responses coming through in our tickets channel and wasn't really participating in the discussion. But I saw that the answer go, go by, like, you know, it's, it's because your event's not free.

[00:25:04] **Adam:** And she's like, well, your interface should, you know, make that clearer. How come, it doesn't point that fact out to me. And Steve's reply was like, well, you know, it's a little bit of a chicken and an egg problem. You know, if you turn on, when you enable wingman. You might then go on to add fees, or if you add a fee, then you, and then you enable wingman, you don't know that you're kind of like breaking it.

[00:25:30] **Adam:** And he kind of described it as like this impossible feature, and I'm like, that's not impossible, it's just a pain in the neck. Because we've got all these different places that we're going to have to like, okay, is the event eligible for wingman, or is the event configured for wingman right now? and to like toggle on the ability to add fees or add options, add products, add blah, blah, blah, all the things, right?

[00:25:52] **Adam:** and so I, I got a B in my bonnet about that. I'm like, this is not an unsolvable problem. And like, as he's having this discussion in, the ticket, I created a new branch in the repository. It was like, you know, feet slash, chicken versus egg wingman. And I pushed the branch name and he replies with this gif of like the, the guy at the sports game, who sports game at whatever, sports ball game, match who like, he's got his hands on his hips and he's

[00:26:19] **Ben:** yeah, it's looking

[00:26:20] **Adam:** Oh, all upset.

[00:26:20] **Adam:** And he's just like, looks away. Right. he's like, fine, whatever. I guess it's, I guess it is possible. And then I did end up working a little bit late, to get it done. Cause I started at four o'clock, but by like 540, I had it done and pushed up to our QA environment. I'm like, look, it's done.

[00:26:36] **Ben:** Yeah, I love it.

[00:26:38] **Adam:** happy about that.

[00:26:38] **Ben:** That's very cool. And if I can go on one quick aside for a second, it reminds me, I was just listening to this podcast

[00:26:45] **Tim:** We've never said no to a side, so you don't have to, yeah.

[00:26:48] **Ben:** let's do it. I listened to a podcast the other day on the power of friction, both in adding friction to a system and removing friction, both, both in meaningful ways.

[00:26:58] **Ben:** And I love the fact that you have created a system where you have intentionally removed, it's, it's, it's, you, you've almost done both. You've added friction in that you're forcing people to simplify the types of events so that you can then remove friction from the people who are actually providing the information at the last moment to make it as easy as possible for them.

[00:27:19] **Ben:** And I just, I don't know, I've been trying to become more cognizant of how friction is being leveraged in both good and bad ways. So.

[00:27:28] **Adam:** Yeah, for sure. And like the, so when you go to try to do something that would be affected by your eligibility or whatever, I've got like, you know, of course it shows you like some sort of alert that, you know, it may or like it's being disabled because XYZ, right. But, it also has like links in it, right.

[00:27:47] **Adam:** It says you can't turn on wingman because you have fees already associated with this event. So if you want to enable wingman, you have to make the fees go away. If you need information about that, and it like, in, in some cases it'll be like, okay, if you want to, if you want to add fees, you have to disable wingman.

[00:28:04] **Adam:** Well, then the text disable wingman takes you. It's like a link that takes you to the place where you go to disable wingman. And it also like the next line down says, do you need help with wingman? Read the docs here. And that's a link to the docs for wingman.

[00:28:16] **Ben:** If I could, if I could probe just a little bit into the business decisions, is, I could knowing nothing about how this is implemented or why it's been implemented in a certain way, I'm wondering, is there a world in which from a consumer standpoint, i. e. from the party attendee standpoint, wingman is just always available?

[00:28:41] **Ben:** And then whether or not the product consumer, i. e. the, the university or educational institution, whether or not they can consume that data, that becomes more an issue of whether or not they're paying for it or whether or not the event has fees. Like, is there a way to make it always available to the attendee and sometimes available to the,

[00:29:02] **Adam:** no,

[00:29:03] **Ben:** all right.

[00:29:04] **Ben:** Just

[00:29:05] **Adam:** yeah, no. I mean, the, the whole, the whole point of it, think of it as like express registration. Right? So if you've got an event that's, and we have that as well, right? You have an event that has like the simplest possible situation, one event, express registration will even support a fee, but it's like, okay, I'm an adult with no guests, there's one fee, there's one activity, there's no options that I have to deal with, like simplest possible path through.

[00:29:32] **Adam:** And like, when I click register, it basically just takes me to the page that says, this is how much you owe us, click here to pay. Right? It skips all of the steps between there where you'd have to fill out those details. So this is like, express registration after the fact. So it has to be a free event.

[00:29:46] **Adam:** It has to be like, no special configuration stuff, as simple as possible.

[00:29:51] **Tim:** I do like the name, Wingman. It's a great name. Yeah, I think it's great.

[00:29:56] **Adam:** I'm, I'm very on the fence about it. And this is like, years later, still. I just, I find it.

[00:30:01] **Ben:** It's fun. And it's, it's on point because it's about party attendees and it, and it's like someone who's helping you out at the party. I mean, I don't go to parties, so this is all academic for me. but I don't know. It's fun.

[00:30:16] **Tim:** Well, these are academic parties, so maybe you would go to one of those.

[00:30:18] **Adam:** You don't feel like there's like negative connotations with the word wingman. I feel like the wingman is like the guy that will, you know, hang out with the less desirable, person. you know, obviously the three of us are male, so let's just go that way. Right. So like your wingman is the guy who hangs out the less desirable girl in the group of girls so that you can hang out with the girl you want to hang out with.

[00:30:38] **Adam:** Right.

[00:30:38] **Ben:** I mean, I grew up in the age of Top Gun. So it immediately makes me just think of that movie and 80s, you know, action movies, and I dunno, to me, it's just a fun name, but I could, I guess I could understand what you're saying.

[00:30:52] **Tim:** Yeah, I get what you're saying, but yeah, Wingman can also mean just someone who comes along with you, right?

[00:30:57] **Adam:** And really the only people that see it are the, the users of our software, right? It doesn't, we don't, the QR code doesn't like say scan here for wingman. It's just like, here's a QR code. Just tell us that you're here.

[00:31:09] **Ben:** Right, right.

[00:31:09] **Tim:** I think it's a great name.

[00:31:11] **Adam:** Yeah. I'm on the fence. I feel like I, I love when

[00:31:16] **Tim:** At least it's not a pormento. It

[00:31:20] **Adam:** you're very, very correct, sir. I love when. You find a name that like is slightly clever, but also like, obviously like, yeah, that's it. And for me, this one hit this, like checks the sort of slightly clever fun box, but it doesn't check the, Oh yeah, that's the perfect name box.

[00:31:38] **Tim:** could be worse, could be side chick.

[00:31:41] **Adam:** And on that note, All right. let's, let's, move into our topic for the day. How about that?

[00:31:48] **Ben:** Let's do it.

[00:31:49] **Adam:** Okay. so I think I mentioned at the top of the show, we're just going to kind of keep on rolling with this, like laws of software thing.

[00:31:55] **Tim:** And yes, we realize it's a bit meta discussion. We get that, but you know, these episodes, we'd like to keep them evergreen. So,

[00:32:02] **Adam:** yeah, there you go. So who's that, who has one you want to kick it off with?

## [00:32:06] Choose Boring Technology

[00:32:06] **Ben:** Well, since we brought up Cold Fusion already, I think we should go with Choose Boring Technology. From, Dan McKinley, 2015, consider how you would solve your immediate problem without adding anything new. So, I, boring in this perspective, I think isn't necessarily, any, yes, exactly, it's more what you already know.

[00:32:32] **Ben:** You know, you don't have to solve a problem by pulling in something that your team hasn't been trained up on, that hasn't been battle tested in production, that you don't know if your DevOps people know how to scale and keep online. You almost certainly have technologies that are turnkey at this point in your companies. Lifecycle. And why not just continue to use those, even if maybe you suspect that there are aspects of it that aren't the perfect fit? The fact that they are so well known and so well understood kind of makes them the perfect fit for the solution in terms of your particular team.

[00:33:14] **Adam:** right? So there's a, Dan McKinley does a lot of presentations and he has one, you can like view the slides and everything online as well as his comments. and it's on, at a URL, it is boringtechnology. club. That's the presentation for this particular, topic, I guess. It's a really good presentation if you haven't seen it.

[00:33:34] **Adam:** and one of the things that stands out in my memory from it is, I believe he has something that he calls like innovation tokens, right? So like as a company, you get so many innovation tokens and you, you know, when you do something like what, if you pick a database, that's like less than five years old, then you're spending an innovation token, right?

[00:33:51] **Adam:** You're, you're kind of. If you, if you pick too many new hotness things and try to like glom them together, you're kind of building a house of cards that's going to make it easy to push it over and, and, you know, it'll be a more fragile, right? And I think that's kind of his point here is like by choosing PHP and MySQL, you know, like these things that have been around forever in Redis, Then the likelihood of that falling over because of anything other than like huge scale or something like that is extremely low, right?

[00:34:22] **Adam:** These are battle tested products and you're not going to get stuck because nobody knows how to work with it. Do the wrong thing.

[00:34:31] **Ben:** Yeah, absolutely. And it makes me think of Chris Coyier did a retrospective on, CodePen, he had a 10 year anniversary for CodePen and did a retrospective on all the things that they've learned over the last decade. I brought this up, I don't know, like 50 episodes ago or something. And one of the things that they talked about in that show was only solving one big problem at a time.

[00:34:53] **Ben:** And so one of the things that they wanted to try and do was start to play around with Golang. I think they were initially built entirely on Ruby on Rails. End. One option could have been to let's build a completely new service and let's build it in Golang which we've never used before. And what they realized was that would be a crazy idea because they didn't know anything about Golang.

[00:35:16] **Ben:** So why try to learn something new while they're trying to understand how something new should operate? So what they did was take things that they understood well, that had already been written in Ruby on Rails, and And then rewrite just small parts of that in Golang. So what they were doing was just learning the Golang parts and not learning how the feature should work.

[00:35:36] **Ben:** And to me, that feels like a, a kind of tangential, but on point to this choose boring technologies is that you're, you're doing something for the. I don't want to say for the right reasons, but you're doing it in such a limited scope that you, you curtail the potential fallout of, of making a bad decision.

[00:35:55] **Adam:** Requires a ton of discipline.

[00:35:57] **Ben:** Yeah.

[00:35:57] **Tim:** So we just went through our PCA audit, PCI audit on site stuff this past, not this week, the week before. Oh, week before, you know, two weeks ago. and one thing that stood out to me was some decisions that we had made. And using some, what we thought at the time was going to be new cutting that was, we thought cutting edge technology.

[00:36:19] **Tim:** Problem is that there's a lot of tech that seems like a great idea at the time. And it probably is, it solved a really good problem, but then it kind of dies. And then What do you, you know, with PCI, you need to make sure that you're keeping all your stuff up to date, that everything's being supported and that you're getting security fixes.

[00:36:40] **Tim:** And if you choose something that was really cool at the time, but now it's been abandoned years later. Now you got to go redo it. So if you chose something just basic and boring, then, you wouldn't probably have less of a chance of having a problem with that.

[00:36:56] **Ben:** real. And we've talked so many times on this show about how things Decisions come back to haunt you and just today, kind of along these lines, so we got a, an alert from Amazon RDS. We use Amazon's relational database system, basically their wrapper around things like MySQL and Postgres and whatever other databases they offer.

[00:37:18] **Ben:** apparently they are rotating the certificates that they use for the end to end encryption with the Passing queries to the database layer. and their recommendation is they're going to, I guess they're going to generate new certificates that we then have to install into our, into our trusted CA certs or whatever it's called at the Java layer or, you know, I guess this applies probably to our Node services and our Golang services as well.

[00:37:47] **Ben:** This only came up today, so I don't know how this is going to be implemented, but I'm terrified

[00:37:51] **Tim:** Oh, they've been warning about this. They've been warning about this for a long time. It's coming up in August, right? It's the

[00:37:56] **Ben:** yeah, it's coming up in August. I didn't, this is the first time I've ever heard about this.

[00:37:59] **Tim:** Yeah. Now I've been getting emails like every three, four weeks from Amazon about

[00:38:03] **Ben:** Oh man. Ugh. Well, so at some point I'm terrified that we're gonna have to rebuild a bunch of our Docker files to get these new, like, to add some sort of command in the Docker file to save this new certificate. And it's gonna invalidate all of the cache layers that are already in these Docker images and.

[00:38:24] **Ben:** I'm just so worried that so many things are going to start breaking, meaning like it'll go to run some install from apt to get, and that module will literally no longer exist in the world. And I don't know what to do about that. I'll report back, but it's, it's, I'm just terrified.

[00:38:38] **Tim:** And that's not necessarily a boring technology thing. That's just

[00:38:41] **Ben:** Well, it is boring. So, sorry. Yeah, you're right. I didn't, I didn't, I didn't, explain that enough. Boring, the anti boring in that we swung so hard into the microservices direction. of architectures that we now have literally hundreds of Docker files that may be affected by this. And had we had, you know, a monolith and maybe a handful of microservices, this would not be so terrifying.

[00:39:09] **Ben:** But the fact that This affects any service that connects to an RDS database. Our architecture makes that terrifying.

[00:39:17] **Tim:** Yeah. But hopefully you have like a non prod version of the RDS that you can test this out on and not be too afraid to break. Oh,

[00:39:31] **Ben:** no, we'll see. Well, I mean, we have stuff, but it's terrifying.

[00:39:35] **Tim:** Cause that's what we're going to do. It's like, we have a non art, non production version and it's like, it's like, it's giving me the same notifications on that. So we'll just go update the certificate on that. And, and, if it breaks, it breaks, you know, it's development. People just have to take the day off while we fix it. It's when that happens in production, that's the problem,

[00:39:56] **Ben:** Good times.

## [00:39:57] Doerr's Law

[00:39:57] **Adam:** I have one. I, I, this is one of those names that I struggle to pronounce, so I apologize. I'm probably going to get it wrong.Doer's Law? Doer's Law? D O E R R? Doer? Do you guys know this one?

[00:40:11] **Ben:** I'm going to say doer.

[00:40:13] **Adam:** So, the law goes, we need teams of missionaries, not teams of mercenaries. Which is a very pithy Way to put it. I really like that.

[00:40:21] **Adam:** You know, like crystallizing it down to just a few words. Basically in software, I feel like the highest performing teams I've ever been on were teams where there was like not really any, deadlines to speak of. Like, you know, you kind of like have a sense of where things are going and how long it's going to take, but it's not like, okay, here's your, here's your thing and we need it next week.

[00:40:43] **Adam:** Right. That and, You know, everybody is sort of gathering around the, the vision, right? Everybody believes in what you're trying to accomplish and, and is working toward that goal and can, because of that, can kind of like pick and choose what they want to work on to some extent, if that makes sense, like from the backlog, right?

[00:41:04] **Tim:** they under, but they understand the mission, right? They understand here's what we're trying to do. Here's what we're trying to get done. I get it. You know, don't need to hold my hand. Just let me go,

[00:41:14] **Tim:** you know, start, start start working on this and, and make sure that we hit our mission, whereas a mercenary, they're just like, Hey man, I'm just, I'm here for the paycheck.

[00:41:21] **Tim:** And

[00:41:22] **Adam:** Yeah, exactly.

[00:41:23] **Ben:** Well, we talked about this a little bit, I think in our episode, when we were trying to define the differences between strategy and tactics, and that if you, if I, if I can recall, it's like, if you understand the strategy, then you can choose the tactics that, you know, roll up into that strategy effectively.

[00:41:44] **Ben:** And I think the same kind of transplanted here, where if you understand the mission of the company, and you understand. The philosophies and the, and the culture, then you can, you can choose to do the right thing as you see it, as long as it all sort of feeds up into the, into the, what the company's trying to accomplish.

[00:42:04] **Adam:** Yeah. I just, you know, it makes me wonder how scalable, how That approach, let's call it a strategy, right? Doors law, you know, have, having missionaries, not mercenaries. How scalable is that as a strategy? Right. Like, can you, does it still work when you have a thousand employees? Does it still work when you have 10, 000 employees?

[00:42:25] **Adam:** I don't

[00:42:25] **Tim:** says it's as scalable as, as, as the, the number of good leaders you have in your organization.

[00:42:31] **Adam:** Oh, I like that.

[00:42:33] **Tim:** You don't have people that are just good leaders and they're, they're also kind of missionaries, but they can like lead the charge with other folks and make sure everyone's on the same page yet you can scale it. But

[00:42:42] **Adam:** That's it's funny that this is kind of coming up because I, I feel like. These soft measurements are very much on my mind lately. So, we just had, I think it was last week or the week before we talked about how I was gonna, I was trying to figure out where do we draw the line between, let's get these, performance reviews done for our SOC 2 audit.

[00:43:02] **Adam:** And let's just like mark it as not done and, and get it done for next year sort of thing. And accept the note on the review. Did I, have I mentioned that on the show before?

[00:43:12] **Ben:** I don't, I'm

[00:43:13] **Tim:** you mentioned SOC several times.

[00:43:15] **Adam:** You think? So the, quickly to recap, the very last thing that we have to do to get our SOC 2 evidence done was some performance evaluations.

[00:43:24] **Adam:** And Steve has not been great about doing performance evaluations over the years, leading into the SOC 2 thing. I, you know, I've told him like, this is your responsibility. You know, you wanted this, this,

[00:43:34] **Ben:** Wait, I'm sorry. Can I, can I interject? Cause I'm, I just want to make sure that I'm understanding what you're saying. Part of the SOC compliance requires employee evaluations.

[00:43:46] **Adam:** Yes, and that is because, so the, the different trust service categories of SOC 2, one of them is, like there's security and there's confidentiality. Those are the two that we're doing this year.and then there's three others, but for one of them, I don't remember which one there, there's a requirement that basically says that you, actively evaluate your employees and make sure that they are living up to the standards that you've set.

[00:44:12] **Adam:** you know, they're, they're, they're treating confidential data appropriately, and you know, all of these things, right? And the way that they, the evidence for the fact that you are doing those things is the performance evaluation.

[00:44:28] **Ben:** That's so funny because not to, not to throw this off the rails here, but to imagine any company that isn't evaluating its employees in some way, I mean, what does that? What does that even mean?

[00:44:40] **Adam:** therein lies the rub, those three words, in some way, right? Like, yeah, we're doing performance evaluations. If I was doing a job, I'd get fired, right?

[00:44:48] **Ben:** Yeah, exactly.

[00:44:49] **Adam:** but that's not good enough for, for, for an accountant running a SOC 2 audit. They need to have a written performance evaluation with a date and a signature, and it has to like cover certain things, right?

[00:45:01] **Ben:** interesting. Okay.

[00:45:03] **Adam:** And, and so, you know, Steve has historically not been graded. I've gotten, I think, three evaluations, like formal evaluations in the 12 years I've been working here. that's, you know, occasionally he'll just like, be like, yeah, you're doing a great job. I'm going to give you this much raise this year, whatever.

[00:45:20] **Adam:** Like, you know, and I'm, I like this and I, I'd like to see you improve there. And that's just like a five minute conversation on video chat or whatever. This is not, like, that would not satisfy this requirement. And I, you know, I made that clear to him. I'm like, look, you wanted this, organization of the company, right?

[00:45:35] **Adam:** It's a flat company. You're on top. Everybody else is on the next level down. That means that you have to write all the performance evaluations.I did write one for him, which I found, I had a lot of fun with, like, you know, it's just kind of like, I did a very genuine evaluation, like, these are the things that I see that you're doing really well, these are things that I see where I think that you could use some improvement, and at the very end, I was like, I guess I will allow you to continue being my CEO for another year.

[00:46:03] **Tim:** Yeah. You talked about that. I thought that was awesome.

[00:46:06] **Adam:** Um,

[00:46:07] **Tim:** move. The only thing you could do, like you can only do that if you really, really know that person really well. . No, they're not. Like get jerked off by it.

[00:46:15] **Adam:** yeah. did I tell you what he did in response to that?

[00:46:18] **Tim:** I think you did, but I can't remember.

[00:46:20] **Adam:** So, he, he enjoyed it so much that because of that last line, he completely ignored the fact that I sent it to him for more than 24 hours. Like made no indication that he had received it, read it, anything. And so because of that last line, I'm getting a little anxious.

[00:46:36] **Adam:** I'm like, is he pissed? Was that a bad idea? And finally I worked up the nerve. I was like, so we were talking about something else. I'm like, okay, change the subject. you know, I sent you that performance evaluation thing the other day. Did you get a chance to read that? and he's like, actually, yes. And I've intentionally said nothing about it just to, just to make

[00:46:57] **Tim:** you sweat

[00:46:58] **Adam:** Exactly.

[00:46:59] **Ben:** awesome. What

[00:47:02] **Adam:** the performance evaluation thing, basically. It, or for any, of these evidence tasks that you have to do for SOC 2, if you don't complete them or they're not up to spec or whatever, they give you a chance to remediate that. And then if you can't or won't, then they just put a note in the evaluation, right?

[00:47:20] **Adam:** They're like, okay, they, they. They, they failed to complete the performance evaluations and we asked them for a comment and here's what they wrote back, right. And that just gets added as like a little appendix to your certification. and so I talked to Steve, I was like, look, you know, and now we're headlong into reunion season.

[00:47:38] **Adam:** and so,I sent him a note. It's like, look, we've been waiting just for this one thing from you for like three, four weeks now. I'm, I'm gonna just call it, right. I'm going to tell her. And that we'll, we'll take the note. Like I asked for a sample of like, what is, what exactly, what is that note going to look like?

[00:47:56] **Adam:** and, just to make sure that we would be able to, to talk our way out of that, if, if somebody, if a customer or potential customer saw it and goes, well, what the heck, but, so, and we're going to hopefully do it next year. And I, I, in order to try and sort of like make it, cause so here's the reason that they don't get done.

[00:48:13] **Adam:** They don't get done because Steve is a perfectionist and he has, Steve is a fantastic writer. He has a way with words that's just like super impressive and, and motivational and, and, inspirational.

[00:48:27] **Tim:** He doesn't listen to the podcast. It's okay. You don't have to say all these nice things.

[00:48:30] **Adam:** You're right, he doesn't. and, and I still said it. the But, but he's so busy, right? He just does not have time to sit down and do these things. And, and writing performance evaluations is so far down the priority list because there's things like making sales calls and sending out contracts and signing paychecks, right?

[00:48:49] **Adam:** That these are things that have to come first. And so as a result, they just don't get done. And. so I was like, okay, well, how can I make both possible, right? I want to be able to check the box for SOC 2 next year, but I also want him to be able to have room to write his flowery prose that makes people feel good.

[00:49:09] **Adam:** So I was like, okay, I'm just going to make a spreadsheet that is, You know, just like score one, like a report card, right? From school, right? You know, here are the things that we're evaluating you on. Here's the, the grading scale. And it's like one through five from like consistently exceeds expectations to, you know, needs improvement or whatever on the very bottom.

[00:49:30] **Adam:** And, and I was like, okay, here's the things, these are the questions. And. You know, so we'll, we'll fill that out for everybody every year. And then if you also want to write an evaluation, go for it, go, go nuts. But like, at least we'll have this right as, as something that we can do. But the, and to, to bring it back to this, missionary thing, the, The thing that I struggle with is like, not every job is easy or maybe even possible to crystallize down into a line on that report card, right?

[00:50:01] **Adam:** Like, so you were talking to him about having a company full of good leaders. Like, yeah, clearly if you have leaders, if you have people in leadership roles that are not good leaders, right. They're not helping people understand the mission of the company and their place in that much mission and how it.

[00:50:20] **Adam:** Moving the ball forward, then that's just not going to, that's not going to get the results that you need. And so like, sort of that, that branch of the org chart is going to kind of suffer as a result. Right. And so how do you put that in the spreadsheet? You know, like is good leader, right? I don't know.

[00:50:40] **Tim:** To be honest, the auditors really don't.

[00:50:41] **Tim:** care. They want to check off a box. So you just,

[00:50:45] **Adam:** But I care, you know,

[00:50:47] **Ben:** you should

[00:50:48] **Tim:** So, so you, so you got, you got his problem. You're a perfectionist. You're trying to,

[00:50:51] **Adam:** well, Hey, it's done. I, I, I, I did, I, I time boxed it and I got it done. I would love it if it were better, but I got it done.

[00:50:59] **Tim:** yeah, there you

[00:51:00] **Ben:** what you can do for the next sock on it. Is take all of Steve's known writing and train a large language model. And then you can write a little thing and say, please rewrite this in the voice of Steve. Boom.

[00:51:15] **Tim:** it.

[00:51:15] **Ben:** I say that not knowing how to do any of that, but I assume it's possible.

[00:51:20] **Adam:** That's it. I, yeah, I don't know. I don't know how I would feel getting my performance evaluation from ChadGPT. That sounds very depressing.

[00:51:28] **Ben:** Well, you would write the reviews, but then you would reframe them in Steve's voice. And now you could take on even more work.

[00:51:36] **Adam:** As a large language model, I feel like you are doing a great job this year.

[00:51:41] **Tim:** Yeah. But, but I, I, I, I like the idea of having, when they say missionaries, they're basically the subtext there is you got people that drank the Kool Aid, right? They're, they're enthusiasts and advocates for the mission of your product or your company. and yeah, you need that, but that's really hard to do.

[00:52:01] **Tim:** I mean, that, one of the things that the, Keynote speaker at the conference that I went to was saying was his main point. And he's worked with like Disney and different companies. And he's like, he would have people from an audience, you know, say, tell me, tell me about your company. And they get up and they just start listing.

[00:52:19] **Tim:** Well, we've been in business 25 years, and you know, we mostly sell this to this, and we know we can do this, but we don't do that. And we focus on this. And he's like, you just give me a list of features. You know, you're not really saying what is your purpose, right? And you can contrast that to say, you know, tell me about the love of your life, whoever that person is and people get up and they just give, you know, they don't list like, Oh, he's tall.

[00:52:45] **Tim:** He's handsome. he, you know, he makes good money. They don't list the features. They talk about them as a person. They, you know, they give stories about, you know, things they do and, and qualities that they have. And that's, that's really how you need to, if you have people that really understand what your company is, what it stands for, what it, what it does, then they're And they're going to try to push that as long as, you know, there's a, a single vision.

[00:53:12] **Tim:** If there's not a single vision, everyone has like contra contradicting ideas about what you're doing and what your mission is, then nothing gets done. It's just a mess.

[00:53:21] **Adam:** And I think, you know, the better you are at communicating that vision, that mission, in a few words, that's like super clear, the more likely people are to Make it happen and for it to like become sort of magical. And I use that word magical very intentionally because I'm, I'm guessing some people have probably heard this, but there's a, like the, I don't know if it's a motto or the mission statement or whatever, but Disney there's is no chipped paint, all horses jump,

[00:53:51] **Ben:** I've never heard

[00:53:51] **Adam:** basically translate translates to everything's perfect all of the time. Right.

[00:53:57] **Tim:** For, for just, for their

[00:53:58] **Adam:** For their parks and yeah. And so like, you know, they go the extra mile to make sure that everything at least appears to be perfect.

[00:54:08] **Tim:** And if there's a dead body in there, they hide it so well that you'll never know that there was a dead

[00:54:12] **Ben:** Magic.

[00:54:13] **Adam:** The 8th, the 8th dwarf.

[00:54:15] **Tim:** Yep, that body disappears. Well, hey, look at that, we made an hour.

[00:54:19] **Ben:** Noise. I

[00:54:21] **Adam:** a third one.

[00:54:23] **Tim:** That's,

[00:54:23] **Ben:** can do a third one really quick if you want.

[00:54:25] **Adam:** Do it. Oh.

## [00:54:28] Fitt's Law

[00:54:28] **Ben:** Alright, so right next to Doer's Law is Fitt's Law, and I'm going to add my own formula on top of this. So Fitt's Law is the time to acquire a target is a function of the distance Distance to and the size of the target. And basically I first heard this in terms of mouse targets, that the smaller a target is, the more effort it takes to move your mouse to a place where it can be accurate click.

[00:54:50] **Ben:** My corollary is, and this thing drives me crazy. I think. Anything that a user thinks should be clickable should be clickable. And I can't tell you how many times I have either experienced interface for myself or watched a user experience interface where they go to click on something that looks like a button or an icon or a link of some sort, and it just doesn't do anything.

[00:55:14] **Ben:** And it boggles my mind. The worst offender to me is you see something that is an, like an icon button where it has an outline. And then inside of this button is a little icon, you know, like a plus icon or a minus icon, and literally the only part of that that is actually clickable is the little, the little icon in the middle of the button itself.

[00:55:35] **Ben:** That looks like a button isn't actually clickable.

[00:55:38] **Tim:** People do

[00:55:39] **Ben:** oh my God, bro, people make terrible interfaces. Drives me nuts. And that's, that's my corollary is anything that a user might click should be clickable.

[00:55:48] **Adam:** And half of them should be jump scares.

[00:55:52] **Ben:** The,

[00:55:53] **Adam:** I totally agree.

[00:55:54] **Ben:** the, the, the, the one that gets on my nerves, and I don't know if this is totally a valid thing to be bothered by, but sometimes you'll see a list of links across the top of a site and some of them are clickable, like the root is clickable. And then some open up a dropdown menu on the, on the ones that open up a dropdown menu.

[00:56:13] **Ben:** Sometimes that root button doesn't actually do anything other than open that menu. And I feel like that root button should be clickable too. It should take you somewhere, maybe just to a page that I don't know, does the same, like a list of links that's in the dropdown. I just, I get so frustrated as a user thinking that something should be clickable and then nothing happened when you click it. Nailed it.

[00:56:32] **Tim:** God, you got that off your

[00:56:33] **Ben:** Thank you.

## [00:56:34] Patreon

[00:56:34] **Adam:** All right. Well, then this episode of Working Code is brought to you by Ben's QA database that definitely exists. Listeners like you. If you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover recording, editing, and transcription costs, and we could not do this every week without them.

[00:56:54] **Adam:** Special thanks, of course, to our top patrons, Monte and Giancarlo. You guys rock.

## [00:56:58] Thanks For Listening!

[00:56:58] **Adam:** we are gonna go record the after show, and once again, we are super prepared for that after show, with a whole list of items that we're gonna discuss there, and I'm just, for no particular reason, gonna not mention here.if you'd like to hear the after show, then you can go to patreon.com/workingcodepod and throw a few dollars our way, we'd really appreciate it. you should come join our discord. It's always fun times. it's totally free and it's open to everybody. You don't have to be a patron. Patrons get special perks in Discord, of course, but it's, but there's like, you know, 99 percent of our Discord is, is open to the public.

[00:57:32] **Adam:** So it's a lot of fun. Great place to hang out, talk about beer and sports and code and there's gifts and stuff. So yeah.did I say you can go to workingcode.dev/Discord to get there? It's a good

[00:57:43] **Tim:** I think you did, but you could say it again. Say it one more time just to be sure.

[00:57:46] **Adam:** Hit one more time.

[00:57:48] **Tim:** Oh, very good. Well done.

[00:57:50] **Adam:** That's it for us this week. we'll catch you next week. And until then,

[00:57:53] **Tim:** You know, I, I tried, but I can't make this a portmanteu, but your heart matters.
