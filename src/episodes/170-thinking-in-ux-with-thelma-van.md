---
title: "170: Thinking in UX with Thelma Van"
description: "On today's show, we talk to Thelma Van about integrating design into the product development workflow."
date: 2024-03-20
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/170-thinking-in-ux-with-thelma-van/id1544142288?i=1000649848615"></iframe>

On today's show, we talk to [Thelma Van][thelma-van] about integrating design into the product development workflow. This includes User Experience (UX) design, User Interface (UI) design, scope negotiation, and user validation through interviews. It turns out, even if you can only [talk to five of your customers][five-users], having this amount of feedback can have a massively out-sized impact on your overall design and development trajectory.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[five-users]: https://www.nngroup.com/articles/why-you-only-need-to-test-with-5-users/
[thelma-van]: https://www.linkedin.com/in/thelmavan/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/170-thinking-in-ux-with-thelma-van.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Thelma:** But I do think it's important to, be able to listen and hear what customers or users, I should say, in order to form, or start to build that muscle. Like, it doesn't happen overnight, right?

[00:00:12] **Thelma:** only, there's only two industries that call their customers users. That's computer programmers and drug dealers.

[00:00:18] **Thelma:** it's my favorite. It is my favorite. It's so true.

## [00:00:44] Intro

[00:00:44] **Adam:** Okay, here we go. It is show number 170. And on today's show, we have a special guest, Thelma Vann. Hi, Thelma.

[00:00:49] **Thelma:** Hello.

[00:00:50] **Adam:** so Thelma is a coworker of Carol's. She's a UI slash UX designer. And so we thought we would bring her on the show and just have a conversation about having a designer on the team.

[00:01:00] **Adam:** Cause I don't know about the rest of you guys, but I've never had the privilege. So there, I'm sure there's a lot to unpack there. A lot of discussion to have and should be fun. but first, as usual, we'll start with our triumphs and fails. And Carol, it's your turn to go first.

## [00:01:12] Carol's Fail

[00:01:12] **Carol:** Alright guys, so I'm going to kick us off with maybe a failure, maybe a triumph, not really for sure, but I have decided I definitely need more fingers, meaning that

[00:01:23] **Ben:** Yeah,

[00:01:26] **Carol:** I need another person on my team. I have hit the point where I keep getting tunnel vision on the work I'm doing, and I need someone to just brainstorm with daily, and I need someone to kind of pull me out of the trenches.

[00:01:37] **Carol:** And someone to just have conversations with. being the only engineer on the team has been okay for a little while, but I've hit the point where I'm done with it. So next week when I'm on site with my supervisor, I'm going to have the conversation and be like, Hey, look, I'm ready for those extra hands you told me you were going to give me, because I need it now.

[00:01:57] **Ben:** totally.

[00:01:58] **Adam:** So this is not out of the blue. This is like, they figured you'd get here at some point. And

[00:02:02] **Carol:** Oh, yeah, we're supposed to hire a whole team, but instead of hiring people, we were going to transition a few people from other teams onto the project so that I would have a lot of knowledge of the system, some areas that I don't know, and then they would backfill those positions with new people.

[00:02:17] **Carol:** So, I'm to the point now where there's enough work, and I am getting tunnel vision on the effort I'm working on enough that I need to, I need a person. I need a friend. So, next week, I'm going to ask for that friend. So, I don't know. Failed or triumphed. Failed, I like hit the point. Triumphed, but I'm pretty sure they're going to give me the person.

[00:02:36] **Adam:** that sounds like a win to me, man.

[00:02:38] **Carol:** Okay, whiz it is then. Yeah,

[00:02:41] **Ben:** we've discussed this in the past. I know we have, but I don't know if we've done it in the context of your current job. Are you allowed to use things like chat GPT and copilot at work? Or are you in like an air gap situation where you can't make external calls?

[00:02:58] **Carol:** not in an air gap situation. the last kind of big overall Arching, like security meeting was that we don't have the infrastructure for AI yet. so things like recording your team's calls whenever they do the closed captioning on it and they try to create the, the, what is it? The transcript of it.

[00:03:18] **Carol:** That's considered information that we need to keep in house because it was generated by AI. So there's a few different things, but no, I'm not supposed to use any type of AI yet. Okay.

[00:03:30] **Ben:** Yeah, that makes sense. That feels on brand for, for government work.

[00:03:34] **Carol:** It's getting there though. Like we are getting there to where we will be able to utilize our own corporate accounts for those things.

[00:03:40] **Adam:** It, if there are, happen to be any listeners that haven't seen all the same nerd movies as the three of us, do you want to explain what an air gapped situation is?

[00:03:48] **Carol:** Me or Ben.

[00:03:51] **Adam:** Yes. Either

[00:03:52] **Ben:** as far as I understand it, air gap just means that you're on a computer and or network that doesn't actually connect to an, an external network.

[00:04:01] **Adam:** the wider internet.

[00:04:02] **Ben:** yeah.

[00:04:03] **Adam:** Yeah. So it's a, it's a computer that can't have been corrupted by anything coming from the internet because it's never touched it.

[00:04:10] **Carol:** No, we're like where I work at. Like I can work from home, work wherever. My husband has a lot of, sessions, I guess. I don't know that he does that are in SCIFs. So they're actually secure facilities. So like he can't have his phone. There's no internet in there. Yeah. So that's the difference between what he does and what I do.

[00:04:28] **Carol:** I have the internet.

[00:04:29] **Ben:** Yeah. Like in Mission Impossible, right? When Tom Cruise is, is lowering himself into that room to get the knock list. I'm pretty sure that's a whole air gap situation, which is why he had to physically be there

[00:04:40] **Adam:** Hmm.

[00:04:42] **Ben:** Thelma. We make a lot of pop culture references on this show.

[00:04:44] **Carol:** I don't get any of them.

[00:04:48] **Thelma:** If you see the blank stare, it's like, I should just nod. I don't really quite get them all, but

[00:04:55] **Ben:** No

[00:04:56] **Carol:** You're my friend. All right. Well, that's me. what about you, Tim? What you got going on?

[00:05:03] **Tim:** Well, it's not like work related

## [00:05:05] Tim's Triumph

[00:05:05] **Tim:** or anything, but you know, it's spring, it's springtime in Georgia. It's almost like 80 degrees here today. It was beautiful weather.

[00:05:12] **Ben:** Oof.

[00:05:12] **Tim:** And this is my favorite time of year when it's like, there's no humidity. The bugs really haven't got out yet. And I'm outside and I'm planting things and getting my garden ready.

[00:05:22] **Tim:** this year I, I bought, so I saw, it's on TLDR, I think it was about, This genetically modified tomato that is actually purple, it has a purple skin and a purple flesh. So, this company, I forget the name of it, but they, they took some genes from the periwinkle plant, which is, purple, and they patched that into the color producing genes in a tomato.

[00:05:47] **Tim:** And so they, they can't sell it like at the grocery store or anything, but they can sell it to home gardeners. so yeah, so I got those are, but little cherry tomatoes, like about plum size and they look really cool. Cause I mean, the skin is purple and the flesh is purple and it's supposed to be extremely good for you.

[00:06:03] **Tim:** Cause like, I forget what the, the antitoxin kind of thing is that's in it, but like blue foods are extremely good at like antioxidant. Yeah. Antioxidant. They have hot, super high antioxidant, like cancer fighting properties. So I got some little seedlings coming up and I'll plant them probably in a few weeks.

[00:06:22] **Adam:** And here I was trying to think of a joke, like when Tim starts growing a second nose or a second ear or

[00:06:26] **Adam:** third ear,

[00:06:27] **Tim:** Yeah, I mean, I understand why some people are scared of GMO stuff, but it's like, to me, it's just like natural selection on steroids. I mean, that's

[00:06:39] **Adam:** Oh, absolutely.

[00:06:40] **Tim:** is, right? I mean, they, when they breed for plant qualities, it's just really slow GMO. Now, of course you can never, you know, take something from another plant and put it into another plant naturally, but I don't know.

[00:06:53] **Tim:** Maybe one year, maybe a hundred years from now, we'll look back and realize what a mistake it was. But for now, it's like, I got a purple tomato. That's cool.

[00:07:00] **Adam:** When are they going to make a tomato that has testicles, Tim?

[00:07:02] **Tim:** I don't, you know, if they, all right, we have to explain that to Thelma.

[00:07:07] **Carol:** Backstory, backstory.

[00:07:09] **Tim:** Alright, so our listeners know, but Thelma, you probably don't listen, so I do an annual, like, wild game, exotic game party that I cater for in memorial of my ex boss's dad. and we do, like, stuff like kangaroo, antelope, pheasant, bear, all different kind of weird animals, but we always have as the main starter some form of testicle. And so Adam thinks, you know, rock. Yeah. So this, this year it was turkey testicles.

[00:07:38] **Adam:** And we just talked about it last week, so.

[00:07:41] **Tim:** So, so if they can genetically modify a tomato to have testicles, I will definitely cook them.

[00:07:48] **Ben:** Dear.

[00:07:52] **Tim:** There's way too much testicle talk on this show.

[00:07:57] **Carol:** love that your, your spring like thing is to go plant stuff. My spring like warning from our garrison was make sure you remember that the tarantulas, rattlesnakes, and some type of owls are coming out of hibernation, so be careful with what you touch in your yard. I was like, okay, interesting. I didn't know I had to be scared of owls here, but I am now.

[00:08:21] **Tim:** Anyway, that's me. how about you, Adam?

## [00:08:25] Adam's Triumph

[00:08:25] **Adam:** Oh, I'm going to go with the Triumph. so recently I've been talking about this new SvelteCare project that we've been working on, and I know last week I went into a little bit of detail on, The sort of the GraphQL thing and how we've been kind of struggling some, some issues here and there with fighting with TypeScript and, getting certain aspects of the GraphQL schema and data resolvers and all of that set up.

[00:08:46] **Adam:** And, again, I've been totally hands off. I haven't touched this GraphQL code at all, but I'm counting it as a big triumph that the rest of my team is getting that working and I haven't had to touch it and it works great and it's getting better all the time. Every day it gets better. Rapidly. and it's just new and different and fun and exciting.

[00:09:04] **Adam:** And, you know, that's, you know, me, I like new stuff. So, I'm just excited to be working with it. Super cool.

[00:09:12] **Ben:** When you get a little bit more hands on with the GraphQL stuff, I'm sure I'm going to have a thousand questions because I've never tried it, but conceptually I have some disconnects in my head and I'm looking forward to someone explaining it.

[00:09:23] **Adam:** Yeah. Yeah. And maybe in like a month or two after I've gotten some like real development work done with it, I've just, so far I've hooked it up to, uh, load. So, so the way that this application works is you're still, we're kind of shunting you over to the old application for the purposes of login. And then you can come back to the new, you know, we're doing strangler pattern, replace different sections of the application at a time.

[00:09:46] **Adam:** You can come back to the new application after you're logged in. And by virtue of that approach, by the time you get to our application, you're already logged in, your session is established, and there's a bunch of stuff in your session. That we can use to then load information into memory about the user.

[00:10:00] **Adam:** So your session has like your user ID or whatever, right? So, one of the things that I did was like, okay, I can take your session ID out of your session, I'm sorry, your user ID out of your session and hit the GraphQL API and say, give me the relevant details that I need to know about this user so that I can have a in memory cache of this session.

[00:10:17] **Adam:** Users information in particular at the moment so far, the thing that's been biggest is like, I need all of the users roles so that I can filter down the navigation to only show them the screens that they have access to. And so. Pulling that via GraphQL. and then what was the other thing? Oh, loading. Of course the, the sidebar config, the navigation, configuration, of course, it comes out of the database.

[00:10:39] **Adam:** Where else would it come from? and I say that because it's a terrible idea, but this is where we are. and don't at me, that's all.

[00:10:48] **Ben:** Very cool. I'm

[00:10:49] **Adam:** Yeah, I'm, I'm super excited, super happy, having fun playing with it. And I look forward to having that conversation about GraphQL after I've got some more experience under my belt. That's it for me. How about you, Ben?

[00:10:58] **Adam:** What's going on?

## [00:10:58] Ben's Triumph

[00:10:58] **Ben:** going to go with a triumph, which is, as we've talked about before in the show, I work at Invision., Invision. Is going to be end of life at the end of December. And,a writer from Fast Company reached out to me. Fast Company is a publication. And they are writing a story and they just want to dig at some background.

[00:11:16] **Ben:** I still work at Invision., so nothing that I say can be on the record, but I can verify things and, and give background. And, I just had a really adult conversation and I feel like I have not had one of those in, in a long, long time.

[00:11:31] **Tim:** It's cause you talk to us

[00:11:32] **Adam:** at that,

[00:11:33] **Carol:** I mean, hello, offended here.

[00:11:36] **Tim:** No, it checks out. It totally checks out.

[00:11:38] **Ben:** was just, you know, talking about business and, and, and, and, and, and, Spend, spend allocations.

[00:11:44] **Ben:** And I use the word counterfactual, like five times, the hat tip to a, you know,

[00:11:48] **Carol:** Oh my God, you're adulting

[00:11:50] **Ben:** don't get to drop that in regular conversation. so I don't know. I just had a very, it was just really refreshing to talk to someone about business because I have not been included in business conversations in a long time.

[00:12:03] **Adam:** Is this something, I mean, I'm, I just want juicy gossip, right? That's, that's where I'm coming from, but is this something that we could dig into in the after show or is this like totally

[00:12:11] **Ben:** I can, I can share some of it for sure. I mean, none of it is super controversial. I don't think, I mean, it's basically my

[00:12:19] **Tim:** What are they going to do, fire

[00:12:20] **Ben:** but anyway, I just had a good time, so I'm going full triumph there.

[00:12:28] **Adam:** Excellent.

[00:12:29] **Ben:** So that's me. Thelma, do you have anything to share with us?

## [00:12:33] Thelma's Triumph

[00:12:33] **Thelma:** Ooh, I'm going to go with a Triumph. I, so I've been helping organize, facilitate, a major initiative, for the account that I'm on to transform their product management strategy, and to hopefully help, development teams work better together on prioritized work. It's always fun when work is prioritized.

[00:13:00] **Thelma:** and we hit a major milestone today. I was iffy. I was like, you know, and anytime you're doing organizational transformation, everybody is on board in the beginning. but it's tough to stick with it and stay consistent. And today we hit a major milestone. And so I was, I was excited to see that for sure.

[00:13:21] **Ben:** Very nice. Wow.

[00:13:25] **Adam:** All right. Well, I,

## [00:13:27] Introducing Thelma Van

[00:13:27] **Adam:** it's a little awkward doing this. I don't know. I mean, this is probably my fault for structuring the show this way, but, now that, now that we've heard you a little bit, Thelma, can you tell us a little bit about yourself? How did you get into design and, and, what brings you to us today?

[00:13:40] **Thelma:** Yeah.

[00:13:41] **Tim:** what's, Yeah. what's your origin story?

[00:13:44] **Thelma:** So back in the day, no, actually I, so I've been designing for a decade and I fell into design by accident, specifically into UX design, by accident. I was. The creative director at a company and, they had a developer that came in and he was working on our platform and he was like, I'm used to working with the designer, where is the designer?

[00:14:14] **Thelma:** And so they're like, give it to Thelma's team. Maybe she'll be able to help you out. And of course, you know, sometimes you don't want to stretch your team. So you go ahead and take the work. And I started working with this developer and I fell in love. I was like, what am I doing? What have I been doing my whole life?

[00:14:33] **Thelma:** I absolutely love, UX. And at the time it wasn't necessarily UX. or it was just emerging as like sort of. a well known profession. And so I really felt like it was my area. I loved working on software. I love designing software. I love, Making experiences and so I've been doing that and, helping build teams ever since.

## [00:15:03] What is UX?

[00:15:03] **Carol:** So silly question. What is UX? Like, how would you define UX to people who don't know?

[00:15:10] **Thelma:** yeah, I would describe it as, user experience. It was first coined, back in the early 90s. and

[00:15:18] **Thelma:** it was really, you were there, okay? and it really was about the entire experience. that a user has with a compu with the software, right? now it has evolved to really be more oriented towards user interfaces, right?

[00:15:37] **Thelma:** So, how a user interacts with the software. I still like to think about it as the starting place is me sitting here in this office, In a physical space, what are the things that I need to accomplish and I might access software to help me meet my goals? I still think of it that way, but most of the time when you hear UX, it's typically talking about an app, piece of software, website, all of that stuff.

[00:16:09] **Adam:** So you came into design from, it sounds like a mostly non technical background. You said you're a creative director.

[00:16:16] **Thelma:** yeah, I guess I would say definitely like not a software developer or anything like that, but I did work. I did, like, the typical sort of web developer doing action scripting type stuff back in the day. Like, you know, having fun, in a very not so great world. Like development skills, but I, I did a thing or two, and then I worked at a company and actually did help desk support for a little while.

[00:16:48] **Thelma:** And honestly, I remember not wanting to hear from customers a second time. And I'm like, so whatever I can do.

[00:16:57] **Tim:** Mood!

[00:16:58] **Thelma:** Yeah, I started working with developers probably even then too, like being like, Hey, we got to fix this because I don't want to get another call. So,

[00:17:08] **Tim:** I don't want the first call.

[00:17:09] **Carol:** Yeah.

[00:17:11] **Thelma:** I think for when it comes to UX, you have to have a little bit of a technical understanding so you can speak the language of the people.

[00:17:24] **Tim:** So help me understand. Is this something, did you take like classes in school for this? Or is it you just kind of learned on the job? Because you said, oh, this is cool. I want to do this and kind of got on the

[00:17:32] **Thelma:** Yeah, I learned on the job. I, yeah, I, I didn't, I didn't go to school for it. I just really, I guess I just had a knack for it. and I was lucky enough to work at a company who allowed me to explore and to do all of the things. I mean, I did usability testing. I did all, all the things that you should be doing.

[00:17:54] **Thelma:** they were just, it was great. I

[00:17:57] **Tim:** She said, she said testing our, our patrons would be happy

[00:18:00] **Carol:** Yeah. Yeah. Bonus points.

[00:18:05] **Tim:** So, so when you first like started your career, like you got out of school, what did you think you were going to be doing? What did you imagine Thelma doing? You know, at work?

[00:18:13] **Thelma:** Yeah, so, you know, I think for me, I have a very wild story and I'll spare you all of the details.

[00:18:22] **Thelma:** I,

[00:18:22] **Thelma:** I,

[00:18:23] **Tim:** We

[00:18:23] **Carol:** want them all.

[00:18:24] **Tim:** it, give

[00:18:24] **Tim:** us the

[00:18:25] **Thelma:** detail. Okay. So I'll give you the tea. So, when I was 19, I left my home in California, flew across country, to go to Parsons New School of Design,

[00:18:36] **Tim:** It's like a Joni Mitchell song already,

[00:18:38] **Thelma:** Yeah, no money. no place to live.

[00:18:42] **Thelma:** And I was just determined. I'm like, I'm going to figure it out. I feel like that's where I should be. And so of course I get there and I do like the summer semester and I realize I can't afford to go here. Nor can I really afford to live in New York City either. So,

[00:19:01] **Tim:** I lived in Brooklyn for four years. It was hard.

[00:19:05] **Thelma:** Exactly, exactly. You get it. So I, ended up living, I had a family who was willing to host me in New Jersey. Like this is wild. You know, you just live with strangers for, for a couple years and a job came open, at a pharmacy. And so I started working there at a long term care pharmacy. I was very lucky, I would say, early in my career that I I don't know how, ended up at companies that allowed me to grow, and allowed, like really supported me and I got to do a lot of different things.

[00:19:42] **Thelma:** and so I, I went from there, went to a payroll company, and they built their own software, so I got an opportunity to see, soup to nuts, what it's like to, have be, be in software, actually at a company that delivers a SaaS model. That was great. Then moved on to elections and worked in elections for a good bit of time.

[00:20:08] **Thelma:** that was

[00:20:09] **Tim:** Elections doing

[00:20:10] **Carol:** mean like, like government elections? Like political

[00:20:13] **Thelma:** yeah, working on software. Yep. For,

[00:20:16] **Carol:** That is cool.

[00:20:17] **Tim:** so. Did you rig the, did you rig the 2020 election?

[00:20:20] **Thelma:** I did not, okay, so I was the director of product during the 2020 election

[00:20:26] **Carol:** Oh, oh no.

[00:20:27] **Thelma:** company, and I literally every day was like, please don't let our name be in the news. Please don't let our name be in the news. It was, I, I'm not gonna lie, it was very stressful.

[00:20:39] **Carol:** Oh, I bet so. Yeah, yeah,

[00:20:41] **Tim:** Wow. I was joking and she's like, actually

[00:20:44] **Thelma:** but yeah, so I've, I think that I, yeah, I've had an opportunity to do a lot of things adjacent to UX work as well. And so, and I, I always tell people, I think that that's one of the things I think that helps me think about experience is because when you, you have so many different ways of being able to look at experiences, I feel lucky in that way.

[00:21:10] **Thelma:** Yeah. Yeah. Yeah.

[00:21:11] **Carol:** yeah.

## [00:21:11] Thinking in UX

[00:21:11] **Carol:** So I struggle whenever I'm creating things because I come at, my approach is technical. So when, you know, my product owner asked me if we can do something, I usually go, sure, we can do that. I don't know what the user experience is going to be like, and does it even make sense to do it? So even this past week I was asked to do something.

[00:21:33] **Carol:** I'm like, yeah, we can add that. Lucky for me, there were two other product owners on the call and they were like, Hey, this doesn't make any sense. The users aren't going to like this. I'm like, well, I don't think like a user. You asked me if something could be accomplished. I said, yes. And I move on. So we definitely need people on our team that think like users because I just know technically, I can change that data and show it to you.

[00:21:57] **Carol:** It doesn't matter to me. It's a line of code, but does the user need to see that? And does the user care about it? And I don't think like that. I don't think like the user. I think from performance and from technical like views on what the software should do.

[00:22:14] **Thelma:** Yeah, I get that. Honestly, if we all thought exactly the same, what, we would never have good software, right? Uh, you definitely need that perspective too and you need people who can just say, yes, it's possible. That's better than, no, it's not possible. but yeah, I think one of the key things, at least for me, how I really start to think about The user is actually just talking to people and asking them what they need.

[00:22:47] **Thelma:** I think that that's an incredibly like first step. And, more recently we've started doing, really kind of workshops where they are customer oriented workshops where developers actually are coming and they're hearing firsthand. Like, here's what, here's what customers are saying. Here's what customers need.

[00:23:11] **Thelma:** and I think it's important to build the muscle. Not everybody's going to have it 100%, right? But I do think it's important to, like, be able to listen and hear what customers want in order to kind of, or users, I should say, in order to form, or start to build that muscle. Like, it doesn't happen overnight, right?

[00:23:36] **Thelma:** only, there's only two industries that call their customers users. That's computer programmers and drug dealers.

[00:23:42] **Thelma:** it's my favorite. It is my favorite. It's so true.

[00:23:48] **Tim:** So let me ask you though, what, what I think. You know, user design, user design, user experience. I just think, okay, CSS, pretty colors, make it look nice on the page. Is that, I mean, I imagine that's a pretty dumb because I just mostly work on the backend and kind of stuff. It's, is there more to it than that?

[00:24:08] **Thelma:** Yeah, I wouldn't call it dumb. I would call it a lot of people's assumptions. So you're, you're right there with the masses.

[00:24:15] **Tim:** Oh, so I'm ignorant. Okay. I got it. Of course,

[00:24:18] **Thelma:** No, I think when I think about UX and which is why you see UX slash UI, right? UI and UX are two different things. They're actually two different disciplines, believe it or not. But we normally couple them together. So UX. I always like to start with UX because I feel strongly that user experience impacts system architecture.

[00:24:43] **Thelma:** So therefore, you will see me starting a lot of times with user flows, right? And understanding not who cares about what the UI looks like. I could care less. First, how am I going to, how is, how am I going to facilitate a user accomplishing their goal in the application? Regardless of what the user interface looks like.

[00:25:06] **Thelma:** So I will start with detailed flows. and then if I'm lucky enough and I'm working with a great architect, we work. Early and often together to make sure that, Hey, this, your flow is going to impact this area of the system. Or I work also with the data, specialist engineer. the, the

[00:25:29] **Carol:** Great title. Yeah.

[00:25:30] **Thelma:** thank you.

[00:25:31] **Thelma:** and I will map, he will map or she will map the data specifically, like, here's my interaction. Regardless of what it looks like on the screen, do we have data available to support that action, right? So, it's so much more than just the UI and making something look pretty. Now, should it look pretty?

[00:25:55] **Thelma:** Absolutely.

[00:25:58] **Carol:** So I will say when she said working with a great architect, she meant Carol. Let's just be clear on that. That's, that's, that's the one she was talking about, but

[00:26:08] **Adam:** you would assume that we didn't assume that.

[00:26:09] **Carol:** I know, right. But,

## [00:26:11] Fulfilling UX Demands

[00:26:11] **Carol:** I will say one thing that caught me off guard when I finally got design on my team was they gave me a front end that looked beautiful and looked amazing.

[00:26:22] **Carol:** I still had to code it. And I'm like, wait, I have to make this work? You did such a great job. This is a lot to accomplish. I didn't know how to do this. Like, I don't, I still struggle with that sometimes. Like, with what needs to happen and how you actually make that work in code sometimes doesn't align.

[00:26:43] **Carol:** Like, what do you do when those type of situations arise? Like, the customer's already bought in. They're like, we love this workflow. We love the way it's going to go. But then the engineering team is like, Ooh, but this isn't going to work right.

[00:26:55] **Thelma:** Yeah, that is such a good question and one that I have run into a lot. That's why I, I said, or I work with an architect early and often, right? So my preference is before it even sees, like the user sees it or the customer sees it, I know that it's feasible, right? Versus.

[00:27:18] **Carol:** You get the team buy in, right?

[00:27:20] **Thelma:** Yeah, 100

[00:27:21] **Thelma:** percent versus I'm going to show this to the customer and then go back to them and be like, just kidding.

[00:27:27] **Carol:** Yeah.

[00:27:28] **Ben:** Yeah. I

[00:27:30] **Thelma:** I will actually change, I will work to change the design when I need to.

[00:27:34] **Carol:** Cause you're cool like that. Yeah.

## [00:27:37] Scoping for Deadlines

[00:27:37] **Ben:** want to ask a question about scoping. So we're all technical people and oftentimes what happens is someone designs a very robust technical concept. And then when it comes time to implement it, we say, okay, well, we're definitely not going to be able to fit all of this in by a particular due date. So let's de scope some of the things that are.

[00:27:59] **Ben:** Less important, less, you know, table stakes for what this feature needs to do. Maybe we, instead of having a full calendaring system, you just have a text box where you can enter a date kind of a thing, and that'll get us 80 percent of the way there. Does the design process do anything like that? Like, is there a, here's the perfect design.

[00:28:20] **Ben:** We have all the right animations. We have all the right affordances. Now it's time to actually build it. And some of those are going to be more complicated. So we're just. Not going to get rid of them, but we're going to defer them. Like, what's the, do you ever have to come up with an 80 percent of all of the, the user experience that we can do at a particular time and then improve it later, or is, is, is you a, Or is UX more, this is, UX is table stakes, it has to get done, and then we can de scope on the technical side if we have to.

[00:28:57] **Thelma:** I think, you're exactly right. We do the same thing on the design side as well. hopefully if you're working with a great product owner or product manager early on as well, that they're helping to establish, you know, I know can be a dirty acronym sometimes, but MVP. But they are helping to establish that so that as a designer, I know what features are already in scope and what is not, right?

[00:29:29] **Thelma:** I generally take the approach with the long term, like here's where I know we want to go. I'm going to design up front for it, but know that a subset of those features can wait to a later date, right? Or a subset of the design can wait to a later date. I am trying to think about it early so that I'm not having to redesign so much later on.

[00:29:57] **Thelma:** You know, like you said, like there might be a calendar with like 10 different bells and whistles, but you really only need three of them. Right. But I am still thinking about the entire 10 and my design up front.

[00:30:11] **Ben:** Makes sense.

[00:30:13] **Ben:** I was just wondering if designers, so again, we're all very technical people here, and so we have a lot of insight into the problems on the technical side of the house, and Engineers, I think, are married pretty hard to some of their ideas from time to time, and it's hard for them to cut back on things or to reduce complexity once they have it in their head.

[00:30:34] **Ben:** But I have also definitely seen and experienced that. On the design side of the house, a designer comes to the table and says, Hey, this, this dropdown should have check boxes in it so that you can check multiple items. And we'd be like, Oh, that's a terrible idea. We shouldn't be doing that. And it, and it's like pulling teeth to try to get them to think about anything else, but the design that they had is, is that something you have to work with people to, you know, we often talk about, was it strong?

[00:31:03] **Ben:** I can never remember what it is off the top of my head. Strong feelings, loosely held, no strong opinions,

[00:31:08] **Adam:** Strong Opinions, Losely Held.

[00:31:10] **Thelma:** Oh yeah, I, yeah. Okay. So you'll hear a lot of designers say it depends. It's a hundred percent like that. That's

[00:31:19] **Ben:** Engineers do that too.

[00:31:20] **Thelma:** okay, it depends. but yeah, there's definitely, and I have been probably one of those designers at times who have held fast to a specific idea that I really felt needed to be, you know, To be implemented, right?

[00:31:38] **Thelma:** For sure. but those battles, I think over time and experience, you realize like those battles are what hill do you really want to die on? and so it is like coaching designers that there are some things that are absolutely worth fighting for and yes, they're worth dying on the hill for. And then there are some other things like.

[00:32:02] **Thelma:** A dropdown with some check marks in it that maybe you can let go of until it's in production and you get real feedback, you know, from users as to whether or not they actually want and need that, you know, that it's really going to benefit them. And so it is, it is a challenge for designers as well. Like we're, we're in the same boat where we got something in our head.

[00:32:29] **Thelma:** We really feel strongly about it. And we're probably with, like, a dog with a bone, you know. All

[00:32:39] **Tim:** Which

[00:32:40] **Adam:** So, for those that can't see us right now, uh, two of the hosts, yeah, two, two of the hosts have had their dogs come in and sit in their laps, so far.

[00:32:48] **Carol:** And, one of their dogs might weigh 55 pounds currently. She is not a lap dog.

[00:32:57] **Tim:** no, momo only weighs 20 pounds. She's tiny little bug, but she needed tickles. So I need a hot take from you, Thelma.

[00:33:05] **Carol:** All

## [00:33:05] Top Pet Peeves in UX

[00:33:05] **Tim:** I need a hot take. I

[00:33:06] **Thelma:** right,

[00:33:08] **Tim:** I need your top pet peeves that when it comes to user design that you see on the internet, or in apps.

[00:33:17] **Carol:** Ooh,

[00:33:18] **Tim:** What boils your blood?

[00:33:20] **Thelma:** top pet peeve is probably when it is A, inaccessible, right? that's, that's a pet peeve,

[00:33:27] **Carol:** big one. Yeah.

[00:33:28] **Carol:** yeah. and that's probably because of working in the public sector. It's drilled in your head, must be accessible. 508.

[00:33:36] **Tim:** So access, accessibility, you mean like, so for people who You know, impaired and things like that. Is that what you're talking about? Accessibility? I

[00:33:46] **Thelma:** yes, where people have, a known disability. the other accessibility I tend to think about as well is like people who have,maybe less obvious, so PTSD, right? So if you come across a design that is inconsistent and uses inconsistent patterns, it is known to trigger people with PTSD because that inconsistency is, is a struggle.

[00:34:13] **Thelma:** So I'm, I'm a lot about trauma informed design. So also thinking about it, not just from known disabilities, but also like, What are people going through? Like you got in a, somebody got in a car accident, right? They need to go file an insurance claim. And now that insurance claim, the process to do so is challenging and difficult.

[00:34:35] **Thelma:** Sure. Does that person not have a long term maybe disability? They have this immediate issue that is impairing them from being able to complete a task, right? But we don't think about it like that. You think, oh, beautiful site, you know, but it's totally inaccessible.

[00:34:53] **Tim:** feel bad now because I feel called out because I do work in the insurance sector and I'm pretty sure I probably triggered many, many people with some of my bad design decisions,

[00:35:02] **Adam:** giving people PTSD, Tim.

[00:35:05] **Tim:** on top of their existing PTSD.

[00:35:08] **Thelma:** Oh my word, you're doubling down there. Oof.

[00:35:15] **Adam:** to a computer on the phone instead of a person, that's Tim's fault. All of it across the entire world.

[00:35:20] **Tim:** If you hear about some shootings in,in Kansas city, it's probably me. Oh, wait, that's the Superbowl thing. Huh? Wonder if they had an accident. Nevermind. So I liked that one. Give me another, give me another hot take. What's, what's, give me another one that boils your

[00:35:36] **Adam:** Well, I, I, can I, can I,

## [00:35:38] The Hamburger Menu

[00:35:38] **Adam:** I want to throw out a specific thing and see, I want your, your opinion on this. How do you feel as a, as a person who is a specialist in design and in information architecture and that sort of thing, how do you feel about the hamburger menu?

[00:35:51] **Thelma:** now I think it's more commonplace. I think it was confusing at one point. I, I

[00:35:56] **Thelma:** think people are used to it now.

[00:35:58] **Adam:** So bad design can become good design just by existing for long enough?

[00:36:03] **Thelma:** So. Why do you call it bad? Why do you call it bad, though?

[00:36:07] **Adam:** because like you said, it was, it was confusing. It was like, I don't understand what is, why does three lines mean? you

[00:36:13] **Carol:** Open a menu.

[00:36:14] **Adam:** to find other things. Yeah.

[00:36:16] **Thelma:** Yeah, yeah, I think, maybe what I would consider that is an unknown pattern. Not necessarily bad, just unknown, right? Um, and I think that over time, it has become commonplace and people know it. And people evolve, solutions evolve, applications evolve. The hamburger menu in use on desktop can still be a little bit baffling, right?

[00:36:44] **Thelma:** But you understand its purpose on a, on a mobile device, for sure. Ah,

[00:36:51] **Tim:** Hamburger menu is kind of like, I don't see what I need to do on here. So let me press this thing up here and see if there's more options,

[00:36:58] **Carol:** That's definitely how it started, right? I was like, what is this thing? Oh, this is the menu.

[00:37:04] **Tim:** but that has to be, like you said, it's more common cause that's a learned behavior. They're like, Oh, I don't see it here. Let me. Click this little hamburger up here.

[00:37:12] **Tim:** Oh, there it is. Okay.

[00:37:13] **Thelma:** yeah. And one small word underneath it that said menu could have, you know, definitely eliminated a lot of confusion early on.

[00:37:25] **Ben:** Well, can I ask you a thought experiment here? And as we're talking about pet peeves and user experience, the only time I ever go to a restaurant website is because I either want to one, look at the menu or two, know the operating hours. And I feel like every restaurant website I have ever been to Does not put those front and center.

[00:37:47] **Ben:** You know, sometimes you got to scroll all the way down and maybe they have the hours in the footer. So,

[00:37:52] **Ben:** and,

[00:37:52] **Tim:** I don't, I don't need to know that you learned cooking in the South of France and that you really enjoy skyboarding and you know, come on,

[00:37:59] **Ben:** so from a, you know, just as a thought experiment from a user stories, user persona perspective. If you had to guess what goes wrong in a design situation like that, how does the, what I would call the majority use case for that website somehow get put on the back burner?

[00:38:19] **Thelma:** Because they're focusing on UI and they got lots of great pictures of their food, right? And which not bad, right? It's just what's important to you. I would say this is why we might consider using or talking, I would talk to Ben. I would say, okay, Ben, what is important to you on this restaurant's website?

[00:38:44] **Thelma:** And then Ben would tell me, you know what, hours of operation and the menu. And then I would go to Tim and to Adam and to Carol, and I would say, What is it that's important to you? And they would echo the same thing that Ben did, right?

[00:39:01] **Tim:** no, no, I want to know where they went to culinary school

[00:39:04] **Thelma:** okay. And so you would

[00:39:05] **Tim:** and how many testicles they cook.

[00:39:07] **Thelma:** so I might

[00:39:08] **Thelma:** split the screen. I might split the screen then and give Tim his happy little story. Right? But over at the top of the screen, I would do, you know, the hours operation and make it very clear that this is how you get to the menu. But how I arrived at that is because I talked to you. I understand what is important to you.

[00:39:30] **Thelma:** Most restaurant owners, and this is no fault to them, right? They are busy people starting their businesses. They see Joe Schmo has templates for restaurants and, I can tell you almost in New Orleans, almost everybody uses the same, like, restaurant, like, template. I'm like, I see the same exact template.

[00:39:53] **Thelma:** And, you know, it. It's not because they just don't, they just don't know. And they don't think to ask. And they're using a template. They need to get the job done.

## [00:40:06] The Curse of Knowledge &amp; Human Centered Design Principles

[00:40:06] **Adam:** engineers, I think we often suffer from Knowledge bias. Is that the right bias? The curse of

[00:40:12] **Ben:** cursive knowledge, right? You, as engineers, we know how something is built. We know how pages connect. And so it is oftentimes hard for us to put ourselves in the shoes of people who don't have that background information. So it, it is not immediately apparent to us that when I get to a landing screen or an empty state, that of course I would know what to do because I built the system and I know how it works. Do you feel that designers also suffer from the curse of knowledge in that for the same reasons, they have a vision in their head of what the software should work like and look like and how the experience should be. So it's hard sometimes to create that proper, empty screen or landing page or tool tip, because there's so much backstory in their head already.

[00:41:04] **Ben:** It's not. It's not clear to them how to nudge people in the right direction.

[00:41:08] **Thelma:** definitely happen. It can happen more so on using existing patterns, right? That you're used to using, you're used to seeing. And I'll hear a lot, Of people say, you know, like, they'll talk about the Airbnb experience or the Uber experience or all these other, like, existing patterns, right?

[00:41:35] **Thelma:** that may or may not be appropriate for the thing that they are designing, right? So we, we bring all this existing experience or all this existing, You know, pattern knowledge and try and apply it to a place that it really doesn't belong. I would say for the designer though, what we have though are HCD principles and the one of the very first principles,

[00:42:01] **Carol:** HCD?

[00:42:02] **Thelma:** human centered design, thank you, principles, in the human centered design principles, you know, one of them is really about, reminding yourself that you are not the user. You are not like, there is no possible way that you could ever understand how somebody is going to use something, what are they going to do when they get to that state, and therefore you must validate. You have to always validate your design. Like, even if it's with five people, it's known that it reduces usability issues.

[00:42:38] **Thelma:** Development rework issues. All of that. so that's like constantly playing like a broken record in the back of our head. Validate. Validate. You're not the user. Validate. You're not the user. Validate.

[00:42:52] **Carol:** Yeah, because in my system, the user never does anything wrong and everything I code is always the happy path and there should never be anything unhappy because they're gonna do what I think they should do.

[00:43:02] **Tim:** doesn't know. I mean, like, so we have company that I used to work with. Carol also used to work with, there's some reports in the system where they just give the, you know, they can go put in like some dates You know, 2016 and today, and just totally crashed the system and they'll crash the system and then everyone's in the, in the, in the dis in the channels going, yeah, this idiot ran that.

[00:43:26] **Tim:** I'm like, no, they're not the idiot. You're the idiot for letting them do it.

[00:43:30] **Tim:** Stop them from, stop them from doing it. If you know this is going to crash the system, stop it. Don't. Don't assume if you let them do it, the user assumes that, okay, you guys are smarter than me. You wrote the system. I can run this for like the past 10 years.

[00:43:46] **Tim:** And, and then all of a sudden it's like, Oh wait, you can't, your insurance system is down. Oh, what happened? Oh yeah. So and so ran it for 10 years. Like, yeah, don't let them do that.

[00:43:57] **Carol:** 100%.

[00:43:58] **Thelma:** Yeah. And we, we sometimes too also do the happy path and forget to design around like things that are not so happy. Yeah.

[00:44:10] **Adam:** I love that you brought that up, Tim. The, I mean, I just wrote down a whole bunch of stuff in like a culture document for our company as we're starting to onboard this new intern type person soon, and one of the things

[00:44:20] **Carol:** wait, what's a culture document?

[00:44:22] **Adam:** it's just like writing down things that we think are important to the culture of our, of our company and our team, right?

[00:44:28] **Adam:** So, the top, the very top line of that document says your culture is the behaviors that you reward.

[00:44:34] **Carol:** Oh, I like this.

[00:44:36] **Adam:** Yeah,

[00:44:37] **Thelma:** Yeah. Yeah.

[00:44:39] **Adam:** the one that I wanted to get to was, don't blame users for doing something the software let them do.

[00:44:45] **Tim:** Yeah. A hundred

[00:44:46] **Carol:** 100%.

[00:44:47] **Adam:** something that a couple people have done over the years, and it always rubbed me the wrong way.

[00:44:51] **Adam:** I'm like, no, that's our fault. But,

[00:44:57] **Carol:** reason why when I log into all of my bank accounts, I can only go back like 18 months. There's no way for me to pull transit, like transactions to my checking account or savings account more than 18 months ago, more than that. I have to contact someone to get it.

[00:45:13] **Carol:** Like there's a reason why that data isn't accessible. And we shouldn't just give it to people and say, oh, it's okay. Take it. And if the system goes down, good for you. Sorry. You have your data.

[00:45:25] **Tim:** You're too lazy to limit the

[00:45:26] **Carol:** Yeah. Yeah.

[00:45:28] **Thelma:** Yeah.

[00:45:29] **Ben:** it's an evolutionary issue too, right? I mean, on day one, you don't have to limit the system because there's not enough

[00:45:35] **Carol:** Heck no.

[00:45:36] **Ben:** data to matter.

[00:45:38] **Tim:** That that's a tomorrow Ben problem.

[00:45:40] **Ben:** Yeah.

[00:45:40] **Tim:** But then.

[00:45:40] **Tim:** tomorrow Ben's like, Oh crap, I should have done that.

[00:45:43] **Ben:** Well, and it's, and the problem is there's so much technical debt. And then is that the priority? Because maybe it'll take me a day to add some limitations.

[00:45:50] **Ben:** And then I go to my product manager. My product manager is like, what are you crazy? You can't take a day to do that. We've got deadlines we've already missed on this other thing. And, and it just never gets fixed.

[00:45:59] **Carol:** And now we're all sad, Ben.

[00:46:02] **Thelma:** We

## [00:46:02] User Experience Validation

[00:46:02] **Ben:** just to circle back to user experience validation for a second, because I think there are a lot of people who would listen to this. And would love to get in touch with customers and have things validated. But there's a sense that it's a little overwhelming. How, you know, how many people do I have to talk to?

[00:46:20] **Ben:** That's a whole program. I have hundreds of people. Maybe I'm only one person. Where do you, can you put it in better perspective for people? Is there a diminishing return on investment where. If I could just talk to three people, that'd be amazing. And 20 people would be a little bit better, but not that much better than three people.

[00:46:41] **Ben:** You know, is there a, is there a, a number that, that feels good for you?

[00:46:46] **Thelma:** Yeah, there's actually a study. Thankfully, I, I don't have to come up with a number. there's a study. It's five.

[00:46:53] **Ben:** Five. All right. That's very manageable.

[00:46:55] **Carol:** So all of us, you can just ask us all the question.

[00:46:59] **Thelma:** Yeah, well, technically, I'm not the user. So, I need one more person. So,

[00:47:04] **Ben:** The pug was just here.

[00:47:05] **Tim:** So the four of us in the bug.

[00:47:06] **Carol:** Yeah.

[00:47:07] **Thelma:** yeah, yeah. But, but yes, yeah. Five completely will, help avoid usability issues. And also Development Rework. That's that's it. obviously, the more you can talk to, the more diverse of people you can talk to, obviously, and that's going to give you better results in the end. But if you would at least, like, do five, that's a great starting point.

[00:47:36] **Thelma:** I knew

[00:47:37] **Carol:** So what is the name of that study? Like, do you know how someone can find it? I'm just curious.

[00:47:43] **Thelma:** were gonna ask this, and I'm like, where what is what is the name? I I don't know it. I'm gonna find it before

[00:47:50] **Carol:** Well, if you find it later, send it over and we'll put it in the show notes for anyone who wants to go read it, cause I'm sure it's useful information in there.

[00:47:57] **Tim:** So let me ask you this.

## [00:47:59] UX/UI Designer Characteristics

[00:47:59] **Tim:** You went to school to be a designer. So when I think design, what sort of design was that? Was that like artistic design? Like clothing design? Was there any special, and I'm leading it. This is a leading question. Cause I'm gonna ask another one after that.

[00:48:12] **Thelma:** I was going to attend for graphic design.

[00:48:17] **Tim:** Graphic design.

[00:48:18] **Carol:** Wonderful.

[00:48:19] **Tim:** Graphic design. So like With the thought of maybe what doing like advertisements or paintings, or, I mean,

[00:48:27] **Thelma:** No, it's hard to explain. I just knew from the 8th grade that I wanted to do something with computers and art. And graphic design seemed to combine the two.

[00:48:38] **Tim:** So it was your, it was your artistic bent. Okay. I'm asking this for a reason. So my son is in college, is a second year of college. he's doing a computer science, but he's extremely artistic. he draws like these animes. He does, there's this discord channel where they do like these battles where they'll create a story.

[00:48:56] **Tim:** They'll start a story and they'll, They'll do a couple of panels and then they'll, for a week, and then the other person would do a responding panel for the couple of weeks. And his art is just really, and it's all digitally, has a pad and, and extremely good at, at, at drawing and art and stuff. And, but right now he's going to school.

[00:49:12] **Tim:** He doesn't really know, you know, does he just want to be a straight, straight up programmer, kind of like I am, where, you know, you're doing kind of backend work or, you know, I'm thinking with his artistic bent, maybe he would be a good UI UX kind of person. But, but. I mean, what, so what do you think the characteristics, I kind of primed the question, so I apologize, but so what kind of characteristics do you think make a good UI UX designer?

[00:49:39] **Thelma:** Yeah, I would say that he could do both. He could be a front end developer, which is always needed. they're like the UI UXers best friend. I'm like, oh my word, working with a great one is good. I think having an eye just for layout, number one is, it is important, right? I know I talk about UX and the user experience, but when it comes to UI, The way something looks is important in understanding.

[00:50:09] **Thelma:** I would say the other characteristics of just interpersonal characteristics is, I think I talked about talking to five people, so you have to be comfortable talking to those five people, right?

[00:50:21] **Tim:** he's, he's screwed there. He's not, he's not, he's not a people person. He doesn't human

[00:50:28] **Carol:** Yeah. Humans suck. Just going to say it.

[00:50:30] **Thelma:** exactly. And it's funny because I am naturally an introvert, but, I enjoy talking to people about design, about UI, you know, so maybe if it's a focus, he'll be okay,

[00:50:45] **Tim:** Yeah, that's fair. So it's like someone, someone like asks, you know, he won't talk to people. He'll never initiate a conversation with another human being. But if someone says, so, you know, they ask him about something he's interested in, he will discourse. Not, not converse, discourse for the next 30 minutes straight. So yeah, maybe, maybe if he's like really interested in finding out like, you know, how his design is good and maybe he'll do that. We'll see. We'll see. Kids are hard to figure out.

[00:51:12] **Thelma:** would say like maybe another characteristic or final one is, is just your ability to think objectively. And I know we talked about designers holding strongly to their beliefs as developers do, but being able to like, Just let some stuff go. Cause 50 percent of the time you're design, like, somebody is going to squash it.

[00:51:36] **Thelma:** So, yeah.

[00:51:40] **Carol:** feel like if that were on the development side and the engineering side of the house, like, You would have some very angry people.

[00:51:49] **Carol:** If half, like if half of what I wrote was just squashed and never made it to production, I would quit. I'd be like, I'm not doing this anymore. Like I've put so much effort in and it's just squashed and never going to production.

[00:52:03] **Carol:** I don't know that I could, I could accept that.

[00:52:08] **Thelma:** And it

[00:52:08] **Carol:** You guys are special.

[00:52:10] **Thelma:** But yeah, it depends on where you're working too, because there's, you know, like Carolee, like you're great. You're fantastic, right? You're like, yes,

[00:52:19] **Carol:** but, however,

[00:52:20] **Thelma:** it's not a, but it's, it's, it's, we didn't talk about the re the working relationship between UXers and developers, , but sometimes

[00:52:28] **Carol:** oh,

[00:52:29] **Thelma:** it's like butting heads, where you're like, this is a good design.

[00:52:34] **Thelma:** And they're like, it's going to be take too much effort. The level of effort to implement this is too high, so we're not doing it. You know, so there's.

[00:52:42] **Tim:** programmer, computer programmers are lazy at heart. We all are a hundred percent. All of us are so lazy and it's not that we don't want to work. We just want to do it in the most efficient way. And we're like, ah, that's a bit harder than I expected. I'm not interested.

[00:52:55] **Ben:** one thing that drives me crazy though, is that engineers at the end of are also consumers of products. And, you know, we talked about, oh, how, how beautiful is this Apple computer? And, oh, it's a single aluminum body. Or like, what about this mechanical keyboard that I spent. 2, 000 on because it emits the right, you know, megahertz sounds and it has the right, whatever.

[00:53:18] **Ben:** I mean, I don't have mechanical, but it's like we spend so much time thinking and talking about how beautiful the products are around us. And then an engineer will turn around and code something that is clearly not good. You know, like here's my input box and here's the button next to it and they're offset and the input box has like a weird tight margin to the button.

[00:53:41] **Ben:** And you're like, I know, you know, that this doesn't look good. Why did you think it was okay to present this as finished work? Like you are a consumer as much as you are an engineer, just. It drives me nuts.

[00:53:55] **Thelma:** Yeah, that is funny you said, it is so true, you, you like, like engineers like beautiful things as

[00:54:02] **Ben:** Beautiful things. Absolutely. Constantly talking about, Oh, I had to switch from this IDE to this other IDE because, Oh, this one's so great. And it's,

[00:54:10] **Adam:** kerning is better.

[00:54:11] **Ben:** the current, Oh, I, I handpicked this, this, coding font out of a thousand fonts because the ligatures are more attractive. And you're like, bro, I know you have good taste.

[00:54:25] **Thelma:** Oh my goodness, yeah, yeah. If we're all a little bit lazy, myself included sometimes, I think, you know, we're, we would take the shortcut. But we, we shouldn't. Yeah.

[00:54:42] **Ben:** The thing that always just gets under my skin the most is, is lack of margins. When an engineer presents something with text, you know, butted up against an image or, I mean that, I know every, yeah, it's such an easy thing. I feel like you got to be yelled at once and then that should never happen again.

[00:55:02] **Thelma:** Oh man. Yeah.

[00:55:03] **Tim:** As I'm getting older, I, I do, you know, my fifties and it's like, if I don't have my glasses on, on, when I'm looking at my phone or the text is so small designers, you know, I, I'm like this, a young designer designed this, cause there is no way I can read that print. That is so terrible. And I try to make it bigger and it just all like bunches of garbles up like, Oh, this is so bad. That's my pet peeve. As a cranky old man.

[00:55:30] **Ben:** no, I feel

[00:55:30] **Thelma:** so true. I, I work with, data developers as well, like doing data viz and stuff like that. And, I finally just created like a set of template, like, listen, this is like the layout. Here's your, drop it right here. Okay. Like this, there's like, I think I have 16 variations. I'm like, you can't mess up the layout if you

[00:55:51] **Ben:** Pick one.

[00:55:52] **Thelma:** Yeah.

[00:55:53] **Adam:** awesome.

[00:55:54] **Tim:** we hire her? I need her.

[00:55:56] **Carol:** no, she's taken, she's taken.

[00:55:58] **Adam:** I already called dibs, Carol. You can't have her.

[00:56:00] **Carol:** We already have her. You can't have her.

## [00:56:03] Data Presentation

[00:56:03] **Carol:** I will say, like, data scientists in a data engineering team are a whole nother beast. Because I feel like they understand data in a way that users don't understand data. They're like, here's a row of information. You should just know what to gather from this information.

[00:56:20] **Carol:** But in reality, you need to visualize, like, what that data is showing. And typically, That's not what they're super great at. They're good at giving you 500 rows, and you can see in those 500 rows, this is a trend. But me picking up those 500 rows, I don't see the trend. I just see 500 rows of data that I don't know what to do with.

[00:56:40] **Thelma:** Yeah. Yeah. A hundred percent. I think that's another area that I've helped like create template. I'm all about templates and frameworks. Let me just tell you, like the

[00:56:53] **Carol:** Oh, they're great. Yeah.

[00:56:55] **Thelma:** less work that I have to continually do is better. it goes back to my help desk days. Like I want to solve the problem once.

[00:57:01] **Thelma:** but I, a lot of times I will put together like, Hey, here are the most critical business questions that these users want to know, or, or I should say customers want to know. Give the data that supports the answer to those, right? Versus like, here's a bunch of data and now I got to sort through it. You know, it's, it's, it's the same as working with, I guess, everyone.

[00:57:26] **Thelma:** Everybody needs design.

## [00:57:30] Low Hanging Fruit

[00:57:30] **Adam:** I'm on a small team and a dedicated UX specialist is just not in the budget. Like we, I don't think we could utilize somebody like that enough to make it worth hiring somebody like that. if I wanted to, and I'm kind of trying to speak for the listener, try to embody them a little bit, right. If I wanted to. Try to take it on myself to get better at some of these things. Maybe the, the low hanging fruit. What should I study? What should I try to learn about, in order to get those easy early wins and improving our UX?

[00:57:59] **Thelma:** Yeah. I think design thinking. So, this is like back in the day when it used to be lynda. com is now lin LinkedIn Learning, right? has a ton of like design thinking courses and bite sized, you know, things that you can read. I would say the other thing is, user flows. So understanding how to do a user flow.

[00:58:22] **Carol:** Third thing is that there are a ton of Slack, channels that have designers in them. Slack. People still use Slack?

[00:58:32] **Thelma:** yes, people still use Slack.

[00:58:34] **Ben:** about?

[00:58:34] **Carol:** my gosh. I'm like Discord only now, I feel like.

[00:58:38] **Thelma:** are

[00:58:38] **Ben:** Discord very

[00:58:39] **Thelma:** with designers in it as well, but all, there's nothing you should, if you can, right, it's nothing proprietary, I would say share your work and get feedback.

[00:58:50] **Thelma:** That's how you get better, you know? Get some honest

[00:58:54] **Carol:** I like that.

[00:58:55] **Adam:** I love that. Yeah.

[00:58:56] **Thelma:** Yeah.

[00:58:57] **Ben:** found, we've talked about Adam Watham before on the show, creator of Tailwind. he has a book called Refactoring UI, which.

[00:59:04] **Adam:** It's amazing.

[00:59:05] **Ben:** Yeah, it's really, really good. And I think maybe it speaks to people who have an engineering background and that they're not familiar with thinking about design and the language of design.

[00:59:16] **Ben:** I mean, just talking about things like, you know, margins and line heights and, and like tempos and textures, like people who just. But they don't, they don't have the, yeah, they don't have it on hand. And that book really speaks to that very, in a very accessible way.

[00:59:35] **Thelma:** That's a good, that's a good one. Actually, it's a really good one.

[00:59:38] **Tim:** So is there any particular like UI framework you lean toward that you use on a regular basis or do you, I mean, how do you kind of work?

[00:59:49] **Adam:** That almost strikes me as the badass. It starts with an empty notepad every time. I just design system in two hours. It's done. Is

[00:59:56] **Tim:** I mean, I'm a bootstrap guy. It's like, I can handle bootstrap. That's about it. I can kind of make it look okay.

[01:00:03] **Thelma:** That's funny. you know, for, are some that I do lean on, like, I don't know, like, Telerex is one,

[01:00:13] **Tim:** Thorax. What?

[01:00:14] **Thelma:** Telerex? Telerex? Telerex.

[01:00:17] **Tim:** I never heard of it.

[01:00:18] **Adam:** this a CSS framework or?

[01:00:20] **Thelma:** no, it's a design system. So, it works with, yeah, Bootstrap. Works with a lot, lots of different, things. I don't, it depends on who I'm working with. Let's put it that way.

[01:00:32] **Thelma:** Like,

[01:00:33] **Tim:** Okay.

[01:00:33] **Carol:** always the case, right?

[01:00:34] **Tim:** and what framework, like, you know, I'm always going to, I get the acronym wrong every time, but then there's also the USDWS, USDWS design system, right? Like that you need to use as well in your work. that because it's government or United States web design system?

[01:00:53] **Carol:** that's what we used. Yes.

[01:00:55] **Tim:** Yeah. Okay. You're

[01:00:56] **Thelma:** So it's, it really depends on, again, who I'm working with. I tend, as Adam, you mentioned, I do like to just start with a blank sheet. Sometimes, like, just like to go at it. Yeah. You were right on. I like to just get in there and go at it. Yeah. because I did think like every, every, every job is different.

[01:01:18] **Thelma:** Every user experience can be subtly different, right?

## [01:01:22] Designer Placement in Teams

[01:01:22] **Ben:** Can I go off in a different direction for a second? Because you, you mentioned at the top of the show that you help teams work with designers. And I worked at a company, I work at a company, and we used to have quite a number of designers, not enough for every team. So a team didn't have a dedicated designer, but a designer was dedicated to a certain number of teams.

[01:01:47] **Ben:** And we had this one designer, and so much wanted her to feel, I wanted her to flip the relationship. She very much felt like, I am a designer, and I sometimes work with your team. And I really wanted her to feel like she was on our team. And she sometimes talked to the designers and, and that was an important,

[01:02:11] **Tim:** jealous,

[01:02:12] **Ben:** no, it, it was an important perspective for me because it was creating friction in that we would have discussions about design and the product that we were, that we had control over.

[01:02:26] **Ben:** And this designer feeling that they had to go back to the design team to have greater discussions about the discussions we were having. And I, and I wanted her to just. Just dive in and be like, yeah, we're going to make mistakes. We're going to make some bad decisions. We're probably going to make some great decisions also, but we want to own it.

[01:02:45] **Ben:** And it shouldn't be this constant second guessing. And I felt like I never, I never had the right words. to kind of bring her into the fold or to convince her that she wanted to be in the fold, so to speak. And, and I just, maybe I was just asking too much or expecting too much. When you're,

[01:03:06] **Tim:** could tell you were too needy.

[01:03:08] **Ben:** she was like, why are you so thirsty?

[01:03:11] **Tim:** You're such a, you're such a, you're such a simp, Ben.

[01:03:14] **Adam:** No RIS.

[01:03:16] **Tim:** Was there a

[01:03:18] **Ben:** and I know, I guess, like, I just, I didn't know if I was asking too much. Like I wanted.

[01:03:23] **Thelma:** No, I actually think that you are not asking too much. It's why I argue that embedded designers are better. Well, okay. Before I

[01:03:35] **Carol:** Here we go. Here we go. Oh

[01:03:38] **Thelma:** to get in trouble, but I, it depends. It depends, folks. It depends. But I do tend to lean towards, especially early establishment of design, that designers are embedded on a team.

[01:03:52] **Thelma:** They are the, the team, they are part of the team for that very reason. They're working collaboratively with the team to come up with design to, as I mentioned before, working with an architect to understand, like, we're collaborating, we are so together, working with development, working with data. We should be part of that team and, and the ownership of that feature or the ownership of that thing should be with the team.

[01:04:22] **Thelma:** Now, I do structure in a way that there is reach back to a centralized hub of designers that meet together in order more so for like knowledge sharing and like, Hey, what are you doing in the part of that part of that application? So you're not doing something totally different, but what you're asking for, I think is it's spot on actually.

[01:04:50] **Ben:** I feel like I somehow needed to give her permission. Like I needed to find a way for her to give herself permission to, to want to dive in and, and lead the discussion. And I,

[01:05:02] **Thelma:** Yeah.

[01:05:03] **Ben:** I just didn't have the right words.

[01:05:05] **Thelma:** Can I ask you was, does she have a different leader? Like, did she have someone else who,

[01:05:10] **Carol:** Was her report, like her reporting structure different?

[01:05:13] **Ben:** Yes. Yeah. She, she reported to the design team and that was the issue that I had. I wanted her, not that she had to, no, no, no, no. It's, it's like, as an engineer, I'm going to make technical decisions and sometimes they're going to be right. And sometimes they're going to be wrong. And ultimately I have to answer to the CTO.

[01:05:33] **Ben:** I, I operate independently in the, in the details until I get stuck or until something explodes. And I wanted her to do the same thing. I wanted her to be able to jump in with our team. And think through new ideas and question things that maybe the other design teams had done. And if she wanted to feed that back into the, the main design team, absolutely, she should do that.

[01:05:58] **Ben:** But I didn't want the design team to become a blocker for the work that we were doing. And I, and I think if she had been able to flip the perspective, but I just, I couldn't get her there.

[01:06:10] **Thelma:** Yeah. I think some of that might be just even personality too. You know, you know, there's, there's a number of things. I think it's, as designers, we're always trying to strive for consistency. So it really depends on the organization but I, I think designers should be allowed to make their decisions with their product owners, with their teams.

[01:06:33] **Thelma:** But obviously like you should keep the other designers in the loop, especially if it's something that impacts, you know, I don't know if you ever work across teams where like you're, you have multiple teams working on a single product and one team makes like a major change and it impacts. You know, the other areas and they didn't tell you

[01:06:53] **Ben:** Yep.

[01:06:53] **Thelma:** then everybody's mad and frustrated.

[01:06:56] **Thelma:** And like, I tend to think of design that same way. Like, sure, run with your team. But also if you're working on team of teams, like you, you should check back in. So it's, it's a, it's a delicate balance, you know? Yeah.

[01:07:14] **Adam:** Heck yeah. Okay, well, we've been going for a little over an hour now, we want to be respectful of your time, Thelma, you've been very generous with it. is there anything, I just want to give you an opportunity, like, you've been super generous with us. I want to, I want to return the favor, right? Is there anything you want to plug?

## [01:07:27] How to Reach Thelma

[01:07:27] **Adam:** Do you want, like, people to reach out to you on social media? How can people continue the conversation with you?

[01:07:31] **Thelma:** yeah, you can reach out, via LinkedIn. You can find me there. Come hang out with me. I'm hoping to start some things soon. and more conversations there. So yes, come follow me on LinkedIn. yeah, no, I love developers, so I always get love and, and technical people. What's the right term?

[01:07:56] **Adam:** nerds,

[01:07:56] **Carol:** It's called the cool kids. Yeah.

[01:07:59] **Tim:** nerds.

[01:08:00] **Adam:** what I said, the nerds. Wait a minute. So is LinkedIn the preferred social network of designers?

[01:08:07] **Thelma:** It is not, it is the preferred, network for what I want to be doing right now

[01:08:14] **Carol:** Perfect. Yeah.

[01:08:16] **Adam:** That makes sense. There's an air of professionality to it.

[01:08:19] **Tim:** Mm hmm. Yep. And LinkedIn's that thing I check once a

[01:08:23] **Carol:** Yeah.

[01:08:24] **Carol:** was gonna say, you guys should know that a few months ago I met Thelma, and if we're talking about being professional, we were sitting in a room and I kept awkwardly staring at her because I knew that we were meant to like be friends, but I couldn't walk across the table and tell her that because we're in the middle of meetings.

[01:08:42] **Carol:** So I go from, Like this, what is it that they, the slideshows are on the projector, like the screens, right? So I'm looking at a screen to looking at Thelma and she looks back to ac like back at me. I'm like, look away. I'm like, don't make it awkward that you're trying to be friends with her

[01:08:58] **Adam:** You're, you're describing the experience of being a teenage boy.

[01:09:01] **Carol:** I, I was a teenage boy and I fell in love with Thelma the day I met her. So let's be clear.

[01:09:08] **Thelma:** No. Likewise, I kept staring at Carol and I actually had the same thought and I was like, damn, this girl's cool. Like, I can't

[01:09:16] **Carol:** we're meant to be, right? Yeah. Yeah. And as you guys have, have noticed on the show, she's great and, you know, is awesome designer.

[01:09:25] **Tim:** so good having you here.

[01:09:26] **Carol:** love to have, I would love to have you back to talk about facilitating at some point, because you are an awesome facilitator as well. And I think that's something that we all could learn from.

[01:09:37] **Carol:** Yay!

[01:09:38] **Thelma:** Yeah. Thank you. Yeah. I definitely have enjoyed hanging out with you guys. I'm like, it was such an easy conversation. I, when Carol first asked me, I was like, No.

[01:09:53] **Adam:** Talk to people?

[01:09:57] **Thelma:** Be recorded? No. Words out there for people to disagree with? I don't think so.

[01:10:04] **Carol:** Oh, it's great. We love it.

[01:10:06] **Adam:** Yeah, yeah, yeah. Well, thank you so much for coming on the show. Are you sticking around for the after show, Thelma?

[01:10:12] **Thelma:** Y'all

[01:10:12] **Adam:** Okay, great. Hey, well, I'm sure we'll, it'll be fun.

## [01:10:16] Patreon

[01:10:16] **Adam:** Okay. So, this is the part where I wrap up the show. So this episode of Working Code is brought to you by Thoughtful Information and Interaction Design, because that's a thing you can do if you didn't know.

[01:10:24] **Adam:** and, and listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them.

[01:10:38] **Adam:** Special thanks to our top patrons, Monte and Giancarlo. You guys rock.

## [01:10:42] Thanks For Listening!

[01:10:42] **Adam:** As previously mentioned, we're getting ready to go, record the after show, so for those of you that don't support us on Patreon, you'll hear the outro, and then you'll just have to go listen to a, an objectively worse podcast next, but for those of you that do support us on Patreon, you'll hear the outro, and then you'll hear more of these amazing people, and, you'll be better for it.

[01:11:02] **Tim:** it's a little more spicy, you know, to be fair. It's a little more spicy.

[01:11:06] **Adam:** Yeah, and, and secretive. Sometimes we give away secrets. Talk about the, the gossip. I guess, that's gonna do it for us this week. We'll catch you next week, and until then

[01:11:13] **Tim:** Trust me. It is not counterfactual. Your heart matters.
