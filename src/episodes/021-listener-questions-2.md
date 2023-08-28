---
title: "021: Listener Questions #2"
description: This week, the crew responds to questions shared by our wonderful, wonderful audience! We continued the discussion on feature flags, compared Kanban and Scrum, discussed staying up to date with new tech while working on old tech, the importance of having a GitHub profile, and whether we'd rather be a jack of all trades or a master of one.
date: 2021-05-05
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/021-listener-questions-2/id1544142288?i=1000520261529"></iframe>

This week, the crew responds to questions shared by our wonderful, wonderful audience! [Nathan Strutz][nathan-strutz] - who called the Working Code Hotline - shares his exciting journey into feature flags; [Ryan Mueller][ryan-mueller] wants to compare and contrast Kanban and Scrum style project management; and, LD2 covers the gamut with questions regarding staying-up on new technology, the importance of having a GitHub profile, and whether the hosts prefer having a deep knowledge in one area (ie, a technical expert) or a shallower knowledge across a variety of areas (ie, a Jack or Jill of All Trades).

This week's sponsored shout-out is **[Grace Hopper Celebration][ghc]** - an event, inspired by the legacy of Admiral Grace Murray Hopper - that brings the research and career interests of women in computing to the forefront.

And finally, don't forget that we are going to have our first book club episode on May 12th for [Clean Code by Robert Martin][clean-code] (aka, "Uncle Bob"). Feel free to read-up and follow along!

## Triumphs &amp; Failures

-  **Adam's Triumph** - After feeling like [Gatsby][gatsby] wasn't performing well enough (at least on the old version that he's using), Adam's decided to start porting his blog over to [Eleventy (11ty)][11ty]. This new static blogging engine is proving to be much faster and will allow Adam to build-out more of the features that he used to have in his older, dynamically-rendered blog engine.

-  **Ben's Failure** - Piling onto some previous failures, he's been in a bit of slump lately. More specifically, he feels disconnected from the programming community. Having nothing to do with the pandemic, he longs for the time that he used to spend reading blogs, watching videos, and - generally speaking - being "part of the conversation." He fears that his hyper-focus on work problems may be holding him back. And, he wants to figure out how to make learning (for the sake of learning) part of his every-week routine.

-  **Carol's Triumph** - She got vaccinated! Woot woot! And, after [last week's episode][working-code-20], Carol is really **crushing it**! With one 4-hour Udemy course about AWS under her belt and she already has her AWS lambdas running on a SAM local stack, all while seamlessly integrating with Google Auth and GMail. All in all, she's quite pleased with how well all the pieces are coming together; and she feels like she's unlocked a lot of potential value in her future development efforts!

-  **Tim's Triumph** - After triumphantly releasing a new product last month, Tim held a retrospective with his customers to get a broad sense of how things are going. And, so far, everything seems to be going swimmingly. Yes, a few obscure edge-cases have presented themselves (and have been promptly dealt with); but, for the most part, payments are getting processed and people are very pleased with the new functionality! In fact, motivated by the current success, he's now planning to release this new product offering to a wider customer-base.

## Notes &amp; Links

-  [Adam Tuttle - Dead Code](https://adamtuttle.codes/blog/2021/dead-code/) - An exploration of when it makes sense to comment-out code.

Follow the show! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[11ty]: https://www.11ty.dev/
[clean-code]: https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship-ebook/dp/B001GSTOAM
[gatsby]: https://www.gatsbyjs.com/
[ghc]: https://ghc.anitab.org/
[nathan-strutz]: https://www.dopefly.com/
[ryan-mueller]: http://creativenotice.com/
[working-code]: https://workingcode.dev/
[working-code-20]: https://workingcode.dev/episodes/020-carol-needs-a-consult/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/021-listener-questions-2.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:17] **Adam:** Okay, here we go. It is show number 18 for May the 5th. That's going to be Cinco de Mayo. And on today's show, we're going to be doing some listener questions again. But as usual, we're going to start with our triumphs and fails. And Ben, I'm coming to you first. What do you got?

[00:00:28] **Ben:** I'm gonna kick it off with a failure.

[00:00:31] **Ben:** I know I've had a couple of failures. I've had a couple of failures lately. And, uh, I seem to just be in a little bit of a slump. And, uh, I, I think once you feel a little bit down on yourself, or once I feel a little bit down on myself, it kind of picks up its own momentum and, uh, it sometimes it's hard to get out of that rutt and, uh, lately I've been feeling, I, I don't know if it's a disconnected from community.

[00:00:56] **Ben:** Or it's a lack of learning, but I'm just feeling like when I think about the programming communities that I feel part of, a lot of that feels like it's the momentum of a previous time. And if I were to jump into a programming community today, I just, I don't have the, um, I wouldn't feel connected the way I used to.

[00:01:16] **Ben:** And I think part of that is because I don't do a lot of independent learning. So I don't spend very much time at all, really. Reading other people's blogs or reading books, or watching videos or presentations, reading

[00:01:28] **Adam:** books. You say ,

[00:01:31] **Carol:** but you listen to a ton of

[00:01:32] **Ben:** podcasts. I, I love podcasts, but I, the problem that I have with listening to podcasts is that it's one sided, meaning I am consuming the content, but I don't feel like I can participate in the conversation.

[00:01:45] **Ben:** Uh, the way that I used to be able to when I would, you know, go to blog aggregations and just spend time reading through other people's stuff and, uh, participating. I'm terrible at social media. I, I really can't stand being on Facebook or Twitter. I am, but not very good at it. I don't, I don't social media

[00:02:02] **Adam:** good.

[00:02:02] **Adam:** You're there begrudgingly. Yeah,

[00:02:04] **Ben:** a little bit. I like to post pictures of my dog. Anyway, so I'm, I'm just feeling like I want to somehow operationalize my learning and participation a little bit more, whether that's maybe dedicating a day of the week to just doing reading instead of feeling like I should be writing code or I don't know, I don't know what it looks like.

[00:02:24] **Ben:** And I've had this thought before and I've never been able to follow through in any kind of successful

[00:02:28] **Adam:** way. So what I'm hearing is you want to do the podcast twice a week.

[00:02:34] **Ben:** I just, I want to, I want to make sure that I'm not falling behind on a lot of learning. Yeah, I'm, I'm hyper focused on the stuff that I do at work these days.

[00:02:43] **Ben:** And it's, it doesn't necessarily set me up for success with

[00:02:47] **Carol:** other things. Yeah, no, I was going to say, I totally get it. Sometimes I feel like I'm excelling at exactly what I do, but I'm still or stagnant and everything else that's outside of

[00:02:57] **Adam:** that.

[00:02:57] **Ben:** Yeah. So that's, that's

[00:02:59] **Adam:** where I'm at. Yeah, I can relate. I have been busy from punch in to punch out every day for the last nine years.

[00:03:06] **Adam:** And so, uh, I've just, you know, I've kind of fallen off the wagon with writing on my blog and because I'm not writing, I'm not, you know, researching stuff as much. And, and, you know, occasionally I find a spark of interest and I, I dig into that, but there's a lot less itches to scratch when you're working, uh, you know, on hard problems for work all day,

[00:03:26] **Carol:** every day.

[00:03:26] **Carol:** I start my morning on Y Combinator. Just to kind of scroll through what anyone is saying, just to give me like a little glimpse into the world outside of what I do. And I'm like, Oh, five or 10 in. And I'm like, okay, now go do something else.

[00:03:40] **Adam:** Yeah. I probably should read. Hacker News instead of Reddit. I, I like Reddit because it's a little bit more, I don't even know, like it's less tech focused, more the, the way that I have my Reddit set up, right?

[00:03:51] **Adam:** There's a lot more broadly social things that I subscribe to. Woodworking and skydiving and other stuff versus...

[00:04:00] **Carol:** Reddit's great, but like you said, I get a whole bunch of information there. It's not specific to technology. And I want to kind of make sure that I'm staying fresh on some new things with tech.

[00:04:10] **Adam:** So,

[00:04:11] **Tim:** I mean, Ben, so how are you going to address this failure?

[00:04:15] **Ben:** I think, so the idea that I keep coming back to is that I want to get back into reading other people's material. And I have an iPad and I'm sure there's a ton of RSS feed readers. RSS still seems to be a technology that is the best way to propagate written content, it feels like.

[00:04:35] **Ben:** So what I'd love to do is have some set of blogs that I just subscribe to and just actually try to read some stuff. I'd also like to maybe be better about reading, um, watching the content that's posted from various conferences. Oh, yeah. Occasionally, I'll, I'll go through a couple of keynotes, but conferences lately, you know, in the last couple of years have been really, really good about posting all of the content, typically for free after the conference has been run.

[00:05:04] **Ben:** And there's, um, there's just gotta be a wealth of information there that is like. Super easy to consume, you know, 2x speed watching a YouTube video. Yeah. Uh, just sit back and drink my seltzer and take it all in.

[00:05:18] **Adam:** You said that you feel like you've been stagnating. I was going to ask you if that you think may be related to not attending any conferences in the last year.

[00:05:25] **Adam:** I don't know how often you were going to conferences before the pandemic,

[00:05:27] **Ben:** but I was going to basically one ColdFusion conference a year. That was sort of my, my thing. And then a year or two ago, I had tried to make a better effort to go to some local meetup groups, but I live outside of the city, like a solid, it's 45 minutes by train, but to get to a meetup, it's, you know, a train and then a walk or a train to a subway, that kind of a thing.

[00:05:49] **Ben:** So door to door and then having to get home, it's. It's not easy to get to meetups. There's no technology meetups that are near me, uh, locally, but, but going to the meetups felt good. I just, I just feel disconnected from other people. Yeah. And I, and I don't even know if that's pandemic related. I think that's just compounded by pandemic, but I think pre pandemic, I was feeling this also, maybe just not as acutely.

[00:06:14] **Ben:** Anyway, what

[00:06:15] **Adam:** do you got going on, Adam? I'm gonna go with the Triumph this week. I, uh, it's more of a personal one. Um, I, uh, a few years ago, I moved my blog from... I guess what we've come to think of as a traditional blog, where it's got a database and everything is generated dynamically on request like an application, I've moved it from that to doing a static site generated with Gatsby.

[00:06:40] **Adam:** And I don't want to throw Gatsby under the bus, you know, a lot of the problems that I was having, I'm sure are. Because I, Gatsby was moving too fast when I adopted it. Like I grabbed onto that train as it was speeding by and I wasn't ready for, for it to keep evolving. And, uh, you know, I, I, I liked What it does, Gatsby has some really cool stuff, but I was having some problems stemming from the fact that I am way out of date on the Gatsby stuff.

[00:07:08] **Adam:** I've just moved on without me. And like you were saying with RSS, I don't have that right now because there's just like some bug where RSS generation takes way too long and, or even fails sometimes. And build times are ridiculously slow for me, which I think is. Even if I did upgrade to the latest Gatsby, I've heard a lot of people talking about Gatsby build time.

[00:07:26] **Adam:** So anyway, I'm moving toward Eleventy, which is a static site generator. And one of its primary features is that it's fast. Um, and so far in my experience, it definitely is. And it's going pretty good so far, kind of going through this phase of, it's like something I do every time I, I, uh, move my blog is I try to redesign it and I start with something super simple.

[00:07:46] **Adam:** And I, I, you know, I spend a couple of days thinking, yeah, yeah, I'm just, it's just gonna be black text and a white background with, you know, maybe a maximum width and that's kind of it. Times New Roman, go back to the basics and then, you know, look at it for a couple of days. It's like, no, no, no, it needs something.

[00:08:02] **Adam:** So, uh, you know, but that's it. I'm hoping that I'm reducing the friction to writing and that that's going to encourage me to write more often. I like that. Writing's hard. Yeah. Really hard.

[00:08:15] **Carol:** I'm not, not

[00:08:16] **Adam:** me. One of the things that I find amusing about this whole thing is that I still haven't finished porting all of my content from my previous blog into the Gatsby blog, so I haven't, I'm like skipping an entire blog here.

[00:08:27] **Adam:** Um,

[00:08:29] **Carol:** yeah. Are you going to port it all into Eleventy?

[00:08:31] **Adam:** Uh, that's the hope. So, the problem is, it, it was, the previous iteration was in a, um, SQL, what was there, free, the Microsoft SQL. Express. That's what it was. And I am totally removed from Windows and that whole world these days. So, in order to get my data out of that database, I had to find a friend who has a Windows server with SQL Express running on it, who would let me import my database, which was like, several gigs because I've got 20 years worth of writing and images and crap on there.

[00:09:05] **Adam:** Uh, and then I have to like export from the database into a bunch of markdown files and then I have to clean up those files and, you know, add a whole bunch of metadata. So it's, it's slow going. When the first round that I did, I kind of went through and I picked out like specific articles that I wanted to revive.

[00:09:22] **Adam:** Like some of your faves. Yeah. Anyway, that's what I got going on. Carol, how about you?

[00:09:27] **Carol:** Yeah, I'm going to go with the Triumph. I have two, actually. So the first one is I'm vaccinated. Yay. Nice. Oh, yeah. I got the second shot this week and the first shot kicked my butt. I had like flu like symptoms for three days.

[00:09:41] **Carol:** This one, I just felt bad one day. You know, I had like fever around where the injection was. Just. Didn't feel great, so I took the day off work yesterday, but yep, second shot and way to go. So happy with myself. Did you

[00:09:53] **Adam:** get your shot on Tuesday? On Monday. Okay. I got mine on Tuesday. You were saying you took off yesterday.

[00:09:59] **Adam:** So

[00:09:59] **Carol:** yeah, it, I didn't start running a fever until late Tuesday night, so it was a little after. But yeah, and then the second thing was, if you listened to the podcast last week, uh, we were talking about me starting up this new project and just kind of being confused and a little lost on just the setup with AWS and how lamb does work and how my SAM stack was going to work and.

[00:10:21] **Carol:** I would like to say it's all running very smoothly, and this is so easy to use, and I'm so happy that I have, like, been introduced to this, and now that this is, like, that this is how I will be coding going forward. Nice. So, I have my SAM stack, I have my Lambda, I have my Node code, I have my TypeScript, it's all working, my Google authentication works, and between AWS and Google, pretty seamlessly, and I'm able to get to everything I need within the Gmail app.

[00:10:46] **Carol:** So, kind of did my little happy dance today. Nice.

[00:10:49] **Adam:** Boss.

[00:10:50] **Ben:** Yeah. That's a pretty serious ramp up time you had there. Yeah. I mean, seriously effective, it sounds like. I

[00:10:55] **Carol:** watched four hours on Udemy, Udemy. Let's get Adam's word for it. You to me. I watched like a four hour course on just what, just like the whole AWS, uh, ecosystem.

[00:11:08] **Carol:** And that really answered a lot of my questions on understanding roles and understanding how it all relates and what I had to do to get my service users in there. And yeah, it was pretty good.

[00:11:21] **Adam:** I am jealous of your attention span. I don't think I could sit through a four hour course consecutively on anything.

[00:11:26] **Carol:** So I, what I do is in the morning when I'm getting ready, like, if I'm actually going to put on makeup and like do my hair, I put the laptop in the bathroom and I sit there and like watch it while I'm doing other stuff. Because if I sit here, I'm just bored and I'm like daydreaming. But if my hands are occupied, then I'm usually able to focus them.

[00:11:44] **Adam:** I do that

[00:11:44] **Tim:** too when I put on makeup.

[00:11:46] **Carol:** Yeah. Yeah, absolutely. You gotta get that eyeliner right. So you gotta be watching the video very closely. Guy

[00:11:51] **Adam:** liner. Guy liner. Guy

[00:11:52] **Carol:** liner. All right. I'll get it right. Get it right. Yeah. I'm super excited about it. It makes me smile.

[00:12:00] **Ben:** I think very few things make me as nervous.

[00:12:04] **Ben:** As the idea of changing some sort of, I am permissions in production. The roles and permissions in Amazon feel like they're absurdly complicated. I guess unless you do it every day, but as someone who touches it like once a year. Yeah. It's like Indiana Jones when he's going to switch the skull out with a bag of sand.

[00:12:26] **Ben:** I'm just waiting for a suddenly no one can

[00:12:27] **Adam:** upload anything to S3. It's all broken. But you can change

[00:12:31] **Tim:** it back quick, so. Can you? I don't know.

[00:12:34] **Adam:** According to what I've learned, you can. permissions, then that's... Exactly, then you're screwed. Whenever I have to make IAM changes, I'm always reminded of like going down to the circuit breaker box and it's like, okay, flip the switch.

[00:12:48] **Adam:** Did that do it? No. No. Alright, turn that one back. Did that do it? No. Nope, that was it. So

[00:12:53] **Carol:** we have to assume roles, right? I guess you guys know this already. I didn't know about this. So I have to assume different roles whenever I'm working in my local. So I have to like assume like our developer role because that's who actually has access to everything inside AWS for my company.

[00:13:10] **Carol:** So then there's also service roles for the services we have that are communicating between the two. So one of the developers working with me, um, was like, I don't understand why this isn't working today. And he pasted in, like, his assume role command, I guess is what it's called. Just the CLI. So he pasted it in and I looked it up.

[00:13:27] **Carol:** I was like, oh, you're just missing a role in here. He was like, how'd you already figure that out? I was like, it's just right there in front of

[00:13:34] **Adam:** me.

[00:13:36] **Carol:** He was like, thank you. I was like, yes, and I've answered a question about this. Double win.

[00:13:41] **Adam:** Earned that paycheck. Yeah,

[00:13:42] **Carol:** you know. What about you, Tim? I see you're still blank on our sheet.

[00:13:46] **Carol:** You not have

[00:13:47] **Adam:** anything yet? It's a surprise.

[00:13:49] **Tim:** Oh. I'm coming at you. You don't know where I'm coming from. I think you're going to make something up. I'm like a spider monkey. Yeah, I'm making something up. Uh, no, so today we had a post, a retrospective, a postmortem. I tend to call things when you've had a bad issue and you got to go back and Yeah.

[00:14:06] **Tim:** So this was a retrospective on the, uh, the product that I was talking about last week that we released. I'm still feeling a bit of emptiness syndrome. I've consumed the data and the data looks good. And it's like, okay, I need to find another, another windmill to tilt out. But, uh, so I got with the customer and the project team today and we had a retrospective on.

[00:14:26] **Tim:** What went well, what went, what went bad. And in every organization, you're going to have people that no matter how things go, are going to find the negative. And they, they brought in, they brought her in as a customer, one of the customer facing people. And she's like, Oh, Oh, we just, we had so many payments that, that didn't get applied to the, to the policies correctly.

[00:14:48] **Tim:** And, uh, and so one of the other people from her company was like, So, how many were we talking about? She's like, Oh,

[00:14:55] **Adam:** 14. Oh. Out of 40, 000.

[00:14:59] **Tim:** Yeah. Out of thousands. And, uh, she's like, Oh, I thought you meant like hundreds. She's like, no, no, it was 14. But normally we only have one. I'm like, well, okay. That just says that we're doing a really good job normally.

[00:15:09] **Tim:** And, you know, we put something new in and 14 happened to slip through. So, yeah. So, we just had a portion where there was some things we learned from it and there's some other projects that are coming on that we can take. The, the things that we learned from the stuff that, that kind of, I wouldn't say even failed.

[00:15:27] **Tim:** It worked 98% of the time, but there was some, there were some edge cases that we just, there was no way we could have tested it for. And so we said, we caught those, right? Well, for the next release of the other thing that we're doing that's very similar, we'll put stuff in there for that. So I was very pleased.

[00:15:44] **Tim:** And as far as the, the, uh, the business owner, it was concerned, he. I mean, he was extremely pleased that everything went as well as it did. And, uh, you know, there's just a few oddities that happen here and there. And I was constantly looking at the logs and fixing them, you know, as they were happening. You know, they're like, someone's like, oh, I put a zip code in and it read the zip code back to me wrong.

[00:16:06] **Tim:** Like, yeah, I already fixed that. I saw that immediately. So, uh, yeah, so it just felt good to just have really, I'm kind of like. Saying the same triumph from last week, but it's, it's like, it's still, do you be able to get the feedback from the customer to say, you did good, you know, everything went well. It went better than we expected.

[00:16:27] **Tim:** Um, you know, that just makes you feel good. And so my next thing is I'm standing up services for another, I want to position this to sell this to other customers, uh, and, and just set it up so that. I'm just going to go ahead and set it up for them because I have access to all their data because they're existing customers.

[00:16:45] **Tim:** So I just say, Hey, by the way, here's your, here's your new, um, integrated call system. Just use the number. If you, if you want to use it, you can, here's what we'll charge you. If you don't, it doesn't matter to me and it'll work. So

[00:16:59] **Adam:** nice. It's pretty sweet. It's always kind of like half annoying, half amusing when, uh, like when somebody at a customer doesn't have the perspective, like you were saying with the 14 out of thousands.

[00:17:12] **Adam:** To really understand like, okay, yes, you know, technically that was not correct, but let's look at the bigger picture here. The best thing

[00:17:18] **Tim:** was I didn't have to point it out. It was someone from her own company. It was like... Oh, 14? I thought you meant like hundreds. Yeah. So dramatic. Right? But I mean, she's a person who's very focused on her job.

[00:17:30] **Tim:** She's, she's the person, like, she's the one who always reports problems, which I don't mind. I love that about her. It's the best thing about, she's, she's the first one to bring something up and you, she makes sure stuff gets done. Yep.

[00:17:43] **Adam:** So. I've got one of those and I always say, like, as soon as I can, as soon as we can afford, I'm going to hire her as a tester.

[00:17:49] **Adam:** Yeah. Those are the people you want. Yeah.

[00:17:51] **Ben:** Yeah, talking to customers is such a gold mine of information. One of the things that I get so frustrated about at work is just a general disconnect from the user base because we have support team and we have a customer facing team and, you know, customer success people.

[00:18:04] **Ben:** So. Engineers, if they're ever on a call, it's purely in a kind of supportive nature, but I just, I keep going to my, my CF team, my customer facing team. And I'm just like, put me on calls with people. I don't even care what we talk about because it doesn't really matter. I just want a customer to get on and give me a stream of consciousness about everything they feel about the software.

[00:18:26] **Ben:** And I will pick up things and the conversation will go in random directions and it'll be amazing. It doesn't even, whether they're happy, whether they're angry. It's going to be great.

[00:18:36] **Tim:** It's funny you bring that up because during, during the retrospective today, I, I had built a tool to help me analyze the data.

[00:18:43] **Tim:** I thought, you know what? This is actually be really helpful for them because they can sort of see the entire process flow of, you know, the call comes in, person makes the interaction, person makes a payment. Where do they, where do they dump out of the process? And I was using that for my own analytics.

[00:18:59] **Tim:** I'm like, this is actually good information for them because if they have a customer service call, they can say, well, I was calling and you know, I wasn't able to whatever. And like, well, you're putting in the wrong information at this point. So during that call, I kind of showed them my tool. And I said, do you want me to, sounds bad.

[00:19:16] **Tim:** During the call, I showed them the widget that I wrote. And, uh, and they're like, yeah, that'd be great. So I'm basically going to integrate it into their Their views and their system that, yeah, their dashboard that they can use. They can go in if there's a customer service call and they had an issue, they can help walk through it with them and explain what went wrong or help them, you know, where it, where it failed.

[00:19:40] **Ben:** That's cool. It's interesting talking about analyzing data. Earlier in my career, I always hated the idea that a customer just wanted raw data. I always, anytime they asked for raw data, I always came back to them with. Why don't you tell me what problems you're trying to solve with that data and I will do the solving for you and I'll give you the answers that you're looking for.

[00:20:03] **Ben:** And they were, they would always push back against it being like, no, I just want to see the data. I want to understand how people are using the system. And I'm like, you know, let me understand how them, how they're using the system and report it. And I feel like I finally reached a point where I came to this conclusion or understanding that some people are just comfortable with the data and they don't want you to answer the questions for you.

[00:20:25] **Ben:** They just want the data and they want to be able to analyze it themselves. And I, and I just don't want to fight that anymore. Like people who I can generate a report for and the report is good for them. That's, you know, gravy. But if there are customers who just want the raw data and they want to run it through their own analyst, analyzing tools, like I just want to give that to them.

[00:20:44] **Ben:** If that's what makes them happy, then that's what I want to do. And you never

[00:20:48] **Tim:** know. I mean, you might have a bias toward the data. Yeah. Right. So they might have a different bias that, that you. You don't have it, it could help uncover something that you never

[00:20:56] **Carol:** would have. I always get stuck with the people who want the data, but then don't know how to use it.

[00:21:01] **Carol:** And then they ask me a hundred questions about what this data means.

[00:21:05] **Adam:** I tell them hourly.

[00:21:06] **Carol:** Yes, I'm like, we're going to sign a contract for this,

[00:21:09] **Adam:** right? Okay, well, uh, I guess before we move on to our listener questions, which is our topic for the day, we have a couple of reminders that we want to get out there.

[00:21:18] **Adam:** Next week, we're going to be doing our book club episode, our discussion on Clean Code by Robert, Uncle Bob, Martin. And I'm really looking forward to that. Have you guys finished the book? Almost done with it. Not yet. This weekend. Yeah, I'm

[00:21:32] **Carol:** finishing it this weekend.

[00:21:33] **Adam:** I finished it a couple of days ago. And then I like that I've got it done a little ahead of time because now as I'm working, I'm thinking of things as I do them.

[00:21:42] **Adam:** And it's like, oh, this is what he was talking about in the book. And I can go and write down notes and stuff.

[00:21:46] **Carol:** Yep. Or I realize how poorly I wrote things before.

[00:21:51] **Adam:** Yeah. And, uh, actually I wrote a blog post this week, speaking of my blog, about dead code and, and commenting out code versus, uh, leaving it there or, or versus deleting it.

[00:22:03] **Adam:** And yeah, so I'll, I'll, we can link that in the show notes, but, uh, I just figured I'd throw a plug out there for that. It was something I am kind of proud of that I wrote. So. Um, so throw that out there. And then, um, the other reminder is we intend to keep doing listener question episodes again in the future.

[00:22:19] **Adam:** So if you have any questions you'd like us to discuss for all of us or for any of us in particular, you can send those to us on Twitter or Instagram at WorkingCodePod. You can of course call our hotline, 512 253 2633. That's 512 253 CODE. Or you can record a voice memo, well, recoid. You can record a voice memo on your phone and email it to us at workingcodepod at gmail.

[00:22:41] **Adam:** com. So our first question of the day. We received this, uh, on the hotline. And so we're going to play this for you now. And this is a call from our good friend Nathan Strutz. Insert call here.

[00:22:55] **Ben:** Ring, ring, ring. Hey, this is Nathan

[00:22:59] **Nathan Strutz:** Strutz from sunny Somerville, South Carolina. I've been listening to your podcast.

[00:23:04] **Nathan Strutz:** Really happy to hear my friends voices since we can't hang out in person. Hey, let's talk about feature flags. I'm really glad you did this episode. Actually, every episode so far has been really good. You guys are great. Um, I'll be using Feature Flags in my current project that I started just last year with a small team of devs.

[00:23:22] **Nathan Strutz:** Initially, we looked for a library, kind of like everyone's first, um, idea, right? But the library wasn't really needed. And kind of like Adam said, about one library he saw had questionable integration with users. And then Lost Darkly is a paid service, and we always use on prem tools. And we always lean towards free stuff, or custom built things.

[00:23:47] **Nathan Strutz:** And then I thought, like, hey, feature flags are really just a series of ifs, right? So we made a database table. Loaded flags up into the, into the UI when you, uh, when you log in. Actually, it's a Vue. js frontend, which is just fantastic, by the way. And every browser reload is just a login event that refreshes all the feature flags and all your session info.

[00:24:07] **Nathan Strutz:** So, uh, I implemented some easy access methods to make it easy on the team. Developer experience is real important. Created a small plugin to check if a feature flag is enabled for Vue. Uh, didn't make a plugin for the, the application API server app because it rarely needs flags. Uh, did make a SQL function to check for flags inside the database.

[00:24:32] **Nathan Strutz:** Uh, one table. Uh, from our feature flags eventually grew into a few tables and now it's kind of expanded. It's got targeted features and user groupings. Some of my key takeaways that I, I learned that DX is really key. Uh, developer experience, you know, if it isn't easy, uh, then my team won't do it. And if they have to do it, but it's complex, then they're going to copy and paste a lot.

[00:24:56] **Nathan Strutz:** So, it was up to me. I created some little tooling to keep it simple. I did reaffirm my belief that the UX and tooling is also key. That means, uh, crappy UI, uh, means no one will want to use the FutureFlag system. So we integrated a small little admin tool in the UI and hopefully it's good enough, but it's, it's on a constant improvement route there.

[00:25:17] **Nathan Strutz:** Uh, and I also learned that there's a difference between FutureFlags and configuration options. That's something that Ben mentioned. FutureFlags are short lived for new features and experiments. Config options are for long lived. Probably permanent settings is something that you'd want to toggle during a service outage.

[00:25:34] **Nathan Strutz:** And finally, I learned that we should probably track a lot more information with our flags. More than just the name of the flag and whether it's on or off, but things like which developer is responsible for which tags? When do we think the flag will no longer be necessary? Where in the application is it utilized, roughly?

[00:25:52] **Nathan Strutz:** So, that's my future flag journey. Question for Ben. What processes do you have to remove flags and clean up? We're kind of at the point, not as far along as you, but where we're starting to feel cluttered with all these flags and the forked code. Help. Thanks.

[00:26:11] **Ben:** I guess, uh, Nathan, it's great to hear from you.

[00:26:13] **Ben:** And I think we're all super excited that you're getting some value out of feature flags, obviously. You know that I'm ride or die on these babies.

[00:26:23] **Carol:** You haven't

[00:26:23] **Nathan Strutz:** noticed.

[00:26:25] **Ben:** They are very revolutionary. Um, and, and definitely some of the pain points that you're feeling are the pain points that we at work feel.

[00:26:34] **Ben:** I mean, especially with regard to leaving feature flags in code. This is something that is an ongoing struggle for us. Um, our best strategy so far is to be explicit about creating JIRA tickets that are for the purpose of removing the code. In an ideal world, and I don't do this all the time, but like, idealized Ben creates three tickets.

[00:26:59] **Ben:** One ticket is the feature itself behind the feature flag. Another ticket, which may be optional depending on the complexity, is the actual rolling out of the feature itself. Because sometimes it's not just an on off, sometimes it's a, let me throw 10% of user traffic at this particular feature and then watch my database graphs, watch some of the metrics that maybe I added as part of the feature code, compare it.

[00:27:26] **Ben:** to the control group or the old feature control flow. And maybe that happens over the course of hours, maybe that happens over the course of days. And then ideally that ticket is done. And then there's a third ticket, which is going back and removing the feature flag and committing to the new control flow.

[00:27:44] **Ben:** And hopefully, if possible, deleting the old code that is no longer relevant. I try not to be overly aggressive in the timeline of removing code, simply because. Not everything within an ecosystem can be rolled back with the same level of ease. For example, let's say I have a database migration and then code that corresponds that database, database migration, I'm dealing with a third party API.

[00:28:14] **Ben:** Some of that code is really within my control and some of it is not so much within my control. So sometimes I will leave feature flags in longer than I have to in case I have to roll back the code and then stuff just makes sense. In your case, you own the feature flags in your own database. So maybe it's a little bit different, but in my case, we have launched Darkly.

[00:28:33] **Ben:** So I'm maybe not as quick to delete the feature flags from launch Darkly because if I have to roll back the code. But the feature flag is no longer present in LaunchDarkly. Then we get the default values, which means that we revert to the old behaviors and it gets a little bit more complicated. Hang on, hang on.

[00:28:48] **Adam:** I want to stop you there for a second. If you've removed, if you've already removed the feature flag, so you've basically committed this code, you've said the experiment went well, we're going with the new code, and then, say, a week later, you decide, oh no, actually we want to roll that back, you get the default value for what?

[00:29:05] **Ben:** So in our, in the application code, typically, uh, we have our, our LaunchDarkly client, our Java client that we're consuming CoolFusion, and as part of the request for a feature flag, you can say, give me this feature flag for this user targeting. With this default value. And what happens is if the client can't communicate with LaunchDarkly or it hasn't synced up the rules, it will just give you the default value.

[00:29:31] **Ben:** So if you roll back to a previous version of code that uses a feature flag, but that feature flag no longer exists in LaunchDarkly, then the client will just give you the default value as opposed to whatever value head you had turned on. It's all in the launch

[00:29:45] **Adam:** darkly dashboard. So it's, you're trying to read from a cache and if there's not, if there's nothing in the cache, then it's going to fall back to this.

[00:29:50] **Adam:** Yeah,

[00:29:51] **Ben:** basically. So, which can be weird because then you default to the. Old control flow, which I guess if you're rolling back is maybe what you intended to do. I, sorry, I know I'm rambling here. All to say that getting stuff out of your code as soon as possible is typically the way to do it. Um, but sometimes it's a little bit more complicated than that, depending on the type of thing you're

[00:30:12] **Adam:** doing.

[00:30:13] **Adam:** One of the things that I thought was interesting was that They chose to home roll it. So he says that because I don't think he said it, but I have this feeling that I maybe remember from a different conversation with him that they, that he worked for like a government contractor or as part of the government or government agency.

[00:30:31] **Adam:** And so third party services can be difficult to get. I think it's actually Boeing. Okay. Yeah, I know for, I knew he worked there for a while. I wasn't sure if he was still there. So yeah, that would be a contractor. It can be difficult to get approval to use third party services. So that would encourage them to, to roll their own, right?

[00:30:49] **Adam:** I'm just curious, like, obviously he kind of went through some of the things that they created so that they can use feature flags. I'm curious, Ben, for you, as somebody who uses feature flags regularly, are there any features? that you use from LaunchDarkly regularly that you feel like this is maybe something you wouldn't have originally thought of to add, but that you're glad that you didn't home roll your solution because you wouldn't have had the time or the thought to implement this particular feature.

[00:31:20] **Ben:** Yeah, I think the flexibility with which you can target users or groups of users using the LaunchDarkly client has, has been surprisingly helpful. So when we first started to implement the feature flags, we just targeted based on a user ID. So a given user ID either had the feature or they didn't. And then that could be also extended to include percentages.

[00:31:45] **Ben:** So 10% of users, 25% of users, so on and so forth. What we found out... What's actually really compelling was the ability to also target on things like email address. Suffixes, so anyone with an at Invisionapp. com email address or anyone with an at alumniq. com email address. That was also very, very helpful.

[00:32:07] **Ben:** And then also being able to target based on some additional custom properties like subdomain. In our application, enterprise customers get their own subdomain. So they'll be you know, acmeinc. Invisionapp. com. And essentially being able to target all of the users for a particular subdomain. Uh, it was very helpful.

[00:32:27] **Ben:** So, just the flexibility with which you can target people, that was something we sort of stumbled onto when we started to need to answer questions about how features were going to work. And it wasn't something that immediately occurred to us at the onset.

[00:32:39] **Tim:** I'm just glad that he acknowledged what I was thinking when you were explaining feature flags that you were gushing about beforehand, and it's like, just a series of ifs, right?

[00:32:49] **Tim:** I mean, you explained it to me, I'm like, it's just a series of ifs.

[00:32:54] **Ben:** It is, really. It's, uh,

[00:32:58] **Adam:** some really complicated ifs.

[00:33:00] **Tim:** Right. True. But still. Just ifs. One thing he hit on, which I really, even beyond the idea of feature flags was talked about the developer experience is really important. Yes. And it is. And, uh, I totally agree with him on that because if you don't.

[00:33:17] **Tim:** If you create something that is going to supposedly help the developer, it has to be a good experience for them. Otherwise, they'd be like, well, I don't wanna use this tool. I don't understand it. I'll just do, do it my own way. And now you have people doing things 10 different ways. Yep. In one system, which is never, never good.

[00:33:34] **Tim:** So yeah, I totally agree with them that, that making sure that the developer experience for his rolled version of feature flag is vital and that he has it. It works well, it's understandable, it's easy to use, and very well documented. I would assume he's documented it well, so totally, totally agree with that because I've, I've seen the same thing where you create something that's really cool in your mind, but they don't know how to use it, or don't understand it, or can't really debug it.

[00:34:04] **Tim:** They're not going to use it. They're just going to go around you and you just wasted your time.

[00:34:08] **Adam:** There's going to be

[00:34:09] **Carol:** another if block at the bottom to just not do what it was doing. Yep. Because I don't

[00:34:14] **Adam:** understand it.

[00:34:16] **Tim:** If one equals two, then don't do this. We're

[00:34:19] **Carol:** going to my new way. Exactly.

[00:34:22] **Ben:** The developer experience, it really brings to my mind the difference between Datadog and Grafana.

[00:34:29] **Ben:** And I'm not intending to throw Grafana under the bus. But you will. But so Datadog and Grafana are both monitoring platforms. And at least in part, they both just consume statistics under the hood. Like we throw stats, D metrics at both Datadog and Grafana. And Datadog's interface is so intuitive and I don't want to say it's easy because metrics are really complicated and I don't necessarily understand how they work and the information that you can glean from them, but setting up a graph and throwing a counter and seeing the counter change over time, it's hard not to get it to work in Datadog because of the way they present the data and the way they allow you to wire data together and do aggregates.

[00:35:16] **Ben:** Grafana, on the other hand, it's like. It's like black magic trying to get it to do the same exact graph. I can't, we, and the only reason I know this is because we switched some of our servers from Datadog over to Grafana only because Datadog is fairly pricey and Grafana we hosted ourselves. So we're just paying for the infrastructure costs.

[00:35:38] **Ben:** But oh man, if I had my way, I'd be just paying for the cost of Datadog. Because it's, it's, um, I think about it as the pit of success. Like Datadog forces you to do it the right way because they make it hard to do it the wrong way. I love that. Whereas Grafana is like, they just give you an open ended query that you can run.

[00:35:55] **Ben:** And you're like, now I have to understand all of these aggregation queries. It's so challenging. And then you see graphs that don't look like they do in Datadog and all this weird oddities. And you're like, Datadog just makes it work because they. I don't know, they take away some of the freedom, I guess, but they, in return for that, they make it really easy to get work done.

[00:36:16] **Ben:** That's why they can charge what they do. Yeah.

[00:36:18] **Adam:** Yeah, exactly.

[00:36:19] **Carol:** They've given you an interface that

[00:36:21] **Adam:** works. This week's episode brought to you by Grafana.

[00:36:25] **Tim:** No, probably not. Hashtag not sponsored.

[00:36:29] **Adam:** But Ben will gladly change his opinion if you pay us enough.

[00:36:35] **Carol:** And maybe train him how to use it correctly.

[00:36:39] **Adam:** So, uh, that was like developer experience and he talked about the difference between feature flags and configuration options. I think that one was kind of fairly straightforward, right? Like, maybe you name them differently or they end up in a separate... section of your feature flag.

[00:36:53] **Adam:** It depends entirely on the implementation, but um, seems straightforward enough. But then the last thing he listed there was that, um, he thought that maybe they should track a lot more information with their flags, like the, the name of the flag, not just the name of the flag and whether or not it's on or off.

[00:37:11] **Adam:** But like, who's responsible for it and when do they think it'll no longer be necessary and where is it, where is it used in the application? Those all seem like great additions to me and I'm wondering, again, I'm going to look at you, Ben, you know, as somebody who uses them all day, every day, what else is like really useful when you're looking at the flag and...

[00:37:31] **Adam:** What kind of questions are you asking that you need those answers?

[00:37:34] **Ben:** Absolutely. I have feelings. Do you track those

[00:37:37] **Carol:** already? Are you look at?

[00:37:40] **Ben:** Uh, I know LaunchDarkly does have some sort of code integration setup that you can do. I have not done it myself, but essentially they have, I think, an integration with GitHub where In their dashboard, they will show you where in the code something is being referenced.

[00:37:56] **Ben:** Um, I think we'd have to actually update our client in order to be able to leverage something like that. And then there's obviously all sorts of security considerations about giving people access to our code base, etc. Uh, so we try to manage that using patterns more than anything technical. Uh, typically we'll try to include some sort of ticket number in the name of the feature flag itself.

[00:38:20] **Ben:** So, I might, I'm on the Rainbow team, so our Jira board, all of our tickets start with Rain. So, I might have a feature flag that's something like Performance Rain1234, which is the ticket number, dash, Homepage Loading Optimization. Something like that. So then, someone can look at the feature flag and get a sense of which team it's on based on the ticket.

[00:38:45] **Ben:** ticket corresponding to a particular board, uh, which then also gives them the ability to look at that ticket in JIRA to get a sense of how long it might be around, or if it's even needed anymore. A lot of times you'll look at a ticket and the last comment on the ticket will be just like fully rolled out.

[00:39:01] **Ben:** And then you look at the date and it's like September, 2018. And you're like, ah, okay, I can just delete this ticket and, or I can delete the, the, it's been rolled out. I can delete

[00:39:10] **Adam:** it. So you said that it got named performance, team name, ticket number, some description of the flag so that you're not just...

[00:39:17] **Adam:** You know, it's not some random letters and numbers, right? You said performance. So what are the other prefixes besides performance that you might use?

[00:39:25] **Ben:** I mean, I use either performance or product. So product would be a new feature, depending on how you squint. And performance would be something that's typically transparent to the user and is more of just a backend refactoring.

[00:39:39] **Ben:** Gotcha. I might be the only one in the entire company who actually uses that divergence.

[00:39:45] **Tim:** Reading this, one thing I would like to track, if, if I use feature flags, which I currently don't, but if I did, is, so, you know, in our software stack, we have a desired outcome. So basically, we want a person to come in, go through an entire process, and at the end, make a payment, right?

[00:40:01] **Tim:** That's the ultimate goal, is to make a payment, because that's where we make our money, is when they, they do a transact. So, I would want to track, you know, Does this feature flag affect the percentage of adoption of payments? Track that. Uh, that's information I would find very interesting. Like

[00:40:20] **Adam:** conversion rate, depending on what the feature flags are.

[00:40:23] **Adam:** I was like,

[00:40:24] **Carol:** what is the word I'm looking for? You got it.

[00:40:26] **Tim:** Conversion rate. Perfect.

[00:40:28] **Ben:** Perfect. I know that at work, we use, um, we send a lot of our metrics to segment IO and then segment IO is kind of like an if this, then that for metrics, and then it gets sent to amplitude, and then we do a bunch of. Charting and amplitude.

[00:40:43] **Ben:** I don't really understand analytics very well, but I will say that we do run experiments. And the way Segment works is you can essentially define an event and then you can give the event custom properties. And If the experiment is being influenced by a feature flag, we will include a specific feature flag state in the custom properties of the analytics event.

[00:41:06] **Ben:** And then I think people who know this tooling much better than I do can then go in and look at the, the click paths and the funneling and understand. How the feature flag state affects the conversions, but that's, you were way over my head now in terms of how to consume data.

[00:41:23] **Carol:** Yeah. What you were talking about, we actually use QuickSight for through AWS.

[00:41:29] **Ben:** That's I've never, I haven't heard of that one. AWS, man. What don't they do? Man,

[00:41:34] **Carol:** everything, all of it.

[00:41:37] **Ben:** It's, it's so, it's so bananas when you hear about these, these AWS with the reInvent conferences, and then you look at the recap and they're like, here's the 37 new services we deployed this year. And you're just like, Oh my God.

[00:41:51] **Tim:** And unlike Google, they don't kill them.

[00:41:55] **Adam:** Cause they're making a few dollars off of it. Yeah. I

[00:41:58] **Tim:** mean, AWS, that is what makes money. Amazon does not make money off their other products. That's it.

[00:42:05] **Adam:** Yeah, they're, their retail is a loss leader for for

[00:42:07] **Tim:** sure. The retail is, is a loss. Everything is based off their, their server services.

[00:42:11] **Tim:** That's where the money is.

[00:42:12] **Adam:** They're serverless servers. Yeah, exactly. Get it Right. But serverless

[00:42:17] **Tim:** Exactly. It's other people's computers is all that

[00:42:19] **Ben:** is. Yeah. I remember after one conference I was reading this little quip about, I dunno if it was called Snow Machine or something. It, it was, it was positioned as like they will just send you a truck with servers on it and you can load data onto this truck.

[00:42:34] **Ben:** And I thought that, I thought it was like an April Fool's joke or something. And you're like, no, that's an actual service they will do. They will ship you infrastructure to load data onto or

[00:42:43] **Tim:** off of. Yeah. What? And then they ship it back and put it back in their data center? I think so.

[00:42:47] **Adam:** Yeah. It's crazy. Is this supposed to be

[00:42:49] **Carol:** a faster transfer

[00:42:50] **Adam:** or something?

[00:42:50] **Adam:** It absolutely is. So, um, my, my, my home computer backups, right? So I use Backblaze and we back stuff up. Continuously, and then when it's time to do a restore, you can download it all, but it might take 12, 24, 36, 48 hours, depending on how much data you got, or you can just have them put it on a hard drive and mail you the hard drive, and then you can mail them the hard drive when you're done after you get it off.

[00:43:14] **Adam:** That's pretty cool. So, yeah, and, and yeah, so Amazon has, I think that was, uh, the one that I'm thinking of is like, you can put data on Glacier, like from S3 or something, and then that was one of the restore options was like, send it to me physically for memory. So before we totally

[00:43:32] **Tim:** get off this. Nathan, great to hear your voice.

[00:43:34] **Tim:** Yes. Miss you so much. Can't wait to get with you again. Yeah. And thank you so much for the question. I hope, I hope Ben gave you some, uh, some knowledge that is useful for you. You're going to show them your tool? No. A widget. I'll show my widget.

[00:43:51] **Adam:** The new widget. Okay, uh, well, so we do have a couple of other questions, but thank you, Nathan, for the call.

[00:43:57] **Adam:** Uh, we really appreciated it. It was great to hear your voice. And I think we're going to, when people call us, I think we're going to call that the callback. I think that would be appropriate for the show. Callback.

[00:44:07] **Tim:** We need, it needs like a snazzy theme song to it. The callback.

[00:44:11] **Adam:** Yeah. Maybe not

[00:44:13] **Carol:** that one.

[00:44:15] **Adam:** Just let him, we'll just let Tim keep riffing for a few minutes and we'll get it out of there.

[00:44:18] **Adam:** Just spitball it.

[00:44:21] **Tim:** The callback. Yeah. It's a little

[00:44:23] **Adam:** better. And, and, there it is. So white. The problem is I don't think that you get embarrassed. I don't. So like, I would love to just cut those out and use those, but you don't care. So it's just everybody else cringing and you don't care. So other questions.

[00:44:40] **Adam:** Um, let's go with this one from Ryan Muller, Creative Notice on Twitter. So Ryan says, Canvan and Scrum, uh, what is their effect on team dynamics and motivations? Also, he's interested to hear if any of us have seen teams choose one or the other For specific reasons or maybe even switch between them depending on a particular project or product goals.

[00:45:04] **Adam:** Anybody want to jump on that?

[00:45:07] **Carol:** Yeah, no, I don't mind giving a little insight. So, um, previous team I worked on, we were scrum. So we had our plans, we had everything laid out. But then our Kanban board was our support board. So it was our, uh, the, there are problems with the system. So it would go on the Kanban board and someone was assigned that sprint to be on the Kanban.

[00:45:26] **Carol:** So you knew that any customer issues like your Zendesk tickets were coming in and it was constantly going to be fluctuating. And, you know, you may have issues you've never seen before, or you may have things that are just repetitive. You don't really know until you get in there. Um, but I definitely prefer Scrum.

[00:45:44] **Carol:** I prefer the planned. I prefer, I, I would pick knowing what I'm going to be doing each week. And every day, as opposed to every day, my priority is changing. And knowing that we have said, this is going to take me 10 story points to get this done, and I'm not moving on to something else, so I'm done with my 10 story points.

[00:46:03] **Carol:** Not, we're going to go pick up something else and put it in front of that now, even though you've already started it.

[00:46:10] **Adam:** Yeah. I mean, maybe it would be useful to, um, useful. Maybe it would be useful as well to. Uh, define what the difference is between Kanban and Scrum because we had to look it up before the show just to be sure that we understood it correctly.

[00:46:26] **Adam:** So I'm sure that there are plenty about plenty of people out there that don't know it just like we didn't an hour ago. So what's the difference? Uh, hold on.

[00:46:36] **Carol:** Let me read it again.

[00:46:38] **Adam:** Here's what I remember. Uh, Kanban is sort of a continuous delivery. You've got prior, a prioritized list of, uh, things that need to be worked on.

[00:46:48] **Adam:** And, uh, Scrum is more like a two week, or it doesn't have to be two weeks, but a, a defined sprint. These are the things we're gonna work on. You make a plan, and then you work on that plan for a certain amount of time, and you release at the end of that.

[00:47:01] **Carol:** Typically you release together and all of the code is rolled out into one

[00:47:05] **Adam:** deployment.

[00:47:05] **Adam:** Kind of reminds me of, like, the old days when you'd get, like, the new CD in the mail for the new version of Microsoft Word or whatever, right? You know, they, that was a two year sprint, right? And you'd get a new one every couple of years. And with web development, we have the luxury of being able to deploy much more frequently.

[00:47:24] **Adam:** We don't have to put it on physical media, but.

[00:47:27] **Tim:** Yeah. So, I mean, my, my take on it. So, the challenge with Scrum is it is really hard to estimate things. I agree. Yes. That is just, it is, me personally, I tend to estimate things aggressively, because I think I can get it done quicker than I can. And then I run into problems and I realize this is going to take me longer.

[00:47:47] **Tim:** And then sometimes things that I thought were. We're actually pretty quick. So estimating is extremely hard. So when we typically do scrum, it's a two week sprint and we try to break everything down into t shirt size. So we have small, medium, large, and we try to, you know, if it's small, so many hours, medium, so many hours, if it's large, so many hours, and we, we don't, we, we, we come up, we just kind of come up with an average of in two weeks, we can typically do this many smalls.

[00:48:19] **Tim:** This many mediums, this many larges, and, and it, you want the goal to be that at the end of two weeks you are releasing everything you said you were going to do, and that typically doesn't happen. And so that, that is the real challenge with Scrum because you're, you're basically saying you're, you're going to take a bucket of tasks and do them in two weeks.

[00:48:46] **Tim:** Everything was going to rely on that because there has to be not just doing the task, but reviewing the task, QAing the task, testing them, getting approval. And so it, it, that tends to be hard, but from a customer's perspective, they do in, they do like the idea that they are getting this bucket of work done in two weeks, right?

[00:49:06] **Tim:** They can say, all right, we're going to be able to, in a week, test these things. And then the next week it will be released. Kanban. The challenge with that is what I've found is that Kanban tends to be, a lot of times it tends to be the fire that it's worked on first. Yeah, right. So, it's the, it's the burning issue that's working on it.

[00:49:31] **Tim:** So, those things always kind of percolate to the top because you typically, it's almost like a Trello board where you putting stuff at the top and saying, all right, what I'm working on, I'm grabbing the thing at the top, I'm going to work on this. And you're not really kind of gauging where it is. And so that is, that in itself is not necessarily a best way to address things either, because if you're only working on the burning issues, you're not really getting to maybe the longer, large t shirt size things that need to be done.

[00:50:00] **Tim:** Um, that can probably put out some of the fires. So I see benefits and challenges in both of them. And I think for my, for my feeling, and this is just completely me. If I'm working on something that is kind of a new product, something very, this kind of greenfield and it's, it's the first iteration of it, which tends to be in my career, the kind of things I like to work on is, is new stuff.

[00:50:29] **Tim:** I hate working on legacy things.

[00:50:31] **Adam:** Um, so say we all use,

[00:50:33] **Tim:** yeah, I use Kanban because it's like, it's really hard with something new. Estimating is almost impossible. So Kanban is, is, is for me is kind of where I go to. I'm like, we're just going to work on what needs to be worked on now to get this thing going.

[00:50:50] **Tim:** Once something has become established and really you're just adding new features, it's an established product, I tend to move to Scrum because it's kind of known, it's a little easier to estimate once you have a product that has been established and you kind of get a feel for how long it takes people to work on certain things.

[00:51:10] **Tim:** So then I moved to this Grumm thing and just, you can, you can come up with a reasonable t shirt size for each, each project. So that's just

[00:51:20] **Adam:** my take on it. You keep saying t shirt size, which makes me want to throw out the, my approach to estimating things is a little bit different. Um, instead of like small, medium, large, I tend to think of it in terms of.

[00:51:32] **Adam:** orders of magnitude. So, basically, there's a break point at each one, right? So, something is either going to take me minutes or hours or days or weeks. If it takes any longer than that, then we should be breaking it up. Um, so yeah, if it's going to take more than 60 minutes, then, then it is measured in hours.

[00:51:51] **Adam:** And if it takes more than 24 hours or whatever, eight hours, then it takes days sort of thing. So, that's how I, and that's not. Even, um, necessarily a, an approach to SCRUM, that's just how I estimate things in general, right? If somebody says, How long is this going to take? That's what, that's my approach to estimating things since I don't get any more specific than that.

[00:52:11] **Adam:** It's going to take me minutes, it's going to take me hours, days, or weeks. Joe DiViota But I can

[00:52:14] **Tim:** probably relate to the, I mean, T shirts are actually going to be minutes, small, medium,

[00:52:20] **Adam:** hours.

[00:52:22] **Ben:** Uh, I think to Tim's point though about us engineers being generally terrible at estimating, I think, I think the less process you have and the worse you are estimating, the more Scrum and Kanban basically look exactly the same.

[00:52:40] **Ben:** Um, and I think maybe drives the difference is having someone who really understands it well and, and acting, I don't know if you want to call them the scrum master. Yeah. Scrum master. There has to be someone there who's actually understands what they're doing and is running it properly and trying to get the benefit of it.

[00:53:01] **Ben:** Because I think if you don't have that, then people just devolve into. Path of least resistance, which is often fighting fires, as Tim is saying, and doing interrupt driven work. And it all just sort of ends up looking like Kanban anyway. And that's not to say that it's a bad thing necessarily, because I think everything that we talk about here is sort of a reaction to not doing the waterfall and the huge design upfront stuff.

[00:53:27] **Ben:** So I think whether you're doing Kanban or whether you're doing Scrum, At least you're not doing Waterfall and you're not, you know, you're not waiting two years to get a CD in the mail to cut a sprint, right? Whether it's deploying once a month or once a week or once a day or whatever it is, like at least you're moving and reacting to changes in the, in the world faster than you would in a, in a Waterfall scenario.

[00:53:52] **Ben:** I think that's pretty good.

[00:53:54] **Tim:** I think the Scrum is

[00:54:00] **Tim:** Limiting the customer's appetite. So with Scrum particularly, you say, all right, we have a two week sprint. What do you want in this? And they're like, well, we really need this, this, and this. They're like, well, you know what? These, these you, you pick 17 things. We really can only get to 10 in this scrum, this two week scrum.

[00:54:25] **Tim:** You know, we, we've estimated it, and, and they're, and for some reason, because you have a methodology and a, and a way of talking about it, they're like, okay. We'll accept that. We'll, this next two weeks, we, you know, we'll put off needing these other things. And you deliver these 10 things

[00:54:40] **Adam:** to us. Helps the prior, the customer prioritize.

[00:54:42] **Adam:** Right. Right. Right.

[00:54:43] **Tim:** So, uh, the customer, the product owner, whoever it is, right? They're the same usually, yeah. Yeah. So, I think that is actually the biggest benefit of that is to just have the, is, it's more, I, I see it more of a communication tool than it is a, um, project. It is product management, but I'd see it more really of communi, communication tool with the customer to say, here's what we can do in the two weeks that we're given.

[00:55:07] **Tim:** It, it boxes them in. Because everyone wants everything yesterday. Everyone always does. That's just human nature. So when you, you limit them and say, we got two weeks and here's what we can get done, pick. What's your priority? Yeah. And that is helpful. Kanban is kind of like, what's on the top of your list?

[00:55:29] **Tim:** We'll do it now.

[00:55:31] **Carol:** It's either now or later. That's the two options when you're in Kanban, it's now or later. So.

[00:55:37] **Tim:** And so I, I think a lot of it is just kind of your kind of working speed and your customers. Appetite. I mean, some people, I mean, some customers are different than others. So

[00:55:48] **Carol:** one thing you said was that as developers or engineers, like we're pretty bad at estimating.

[00:55:53] **Carol:** So you can get around that if you pre plan things. So what we do is we take a tear sheet of what's required and we take a couple people and we go and look at the system. We look at what's going to be needed. We put notes on it. So when it gets to story planning, which we call story time, we have story time every Thursday.

[00:56:11] **Carol:** It's so great. I bring my blankie and my pillow. This cookie's a milk. Yeah. So during story time, now it's already kind of been pre reviewed. Yeah. That's great. We went through and looked at the code. We've made notes on it. We've added, you know, some files to go reference. We've added data to go with it. So once the whole team reviews it, they can just point out any holes or any missing points.

[00:56:31] **Carol:** And it does become a lot easier to accurately, um, estimate what you think it's going

[00:56:36] **Adam:** to do. Man, that's methodical. We just kind of look at the requirements, go, yeah, you know, like maybe three days.

[00:56:46] **Carol:** If you can get there, if you can get your team to a place to where you can do it, it's great because then you actually know when I pick up a five point story, I know it's going to take me four or five days to do it.

[00:56:57] **Carol:** Like three to five days. Like I should be good. I don't have to go. Five

[00:57:01] **Tim:** point. What does that mean? So

[00:57:02] **Carol:** we do Fibonacci. So, you know, every increment goes a double of itself. So, you know, we have a two point that's about a day and then it goes. Three or, or it's, what is it? The number plus the number after it.

[00:57:16] **Carol:** I don't remember how Fibonacci works. I probably should look,

[00:57:19] **Adam:** I'm not Italian . Yeah,

[00:57:20] **Carol:** so it's like it's 2, 2, 5, 8 because the

[00:57:25] **Adam:** computer science major in me is dying over here. You

[00:57:28] **Carol:** can explain that if you'd like. So anyway, so eight is supposed to take you, you know, about a week and a half. Um, up to, what's the next one, 15 or something, I don't even know.

[00:57:39] **Carol:** The teaser size. Yeah, I mean, they're all just, it's just how you rate things. But we have to account for, um, after hours deployments if that's needed, and we also account for our quality testing. So our QA is actually in our story time, and we may put a 5 on it, and QA is gonna be like, it's gonna take us a 5 to test that alone, so there's no way you can get it done in 5 when we need 5 points to test it.

[00:58:02] **Carol:** So then the customer knows it's not feasible to be delivered and this week it's going to be a few weeks

[00:58:06] **Adam:** out.

[00:58:07] **Tim:** Yeah. And again, I think that's the biggest thing is that helping the product owner, the customer realize what the limitations are, what the boxes are in this, this

[00:58:16] **Adam:** release. Temporary expectations.

[00:58:19] **Adam:** Okay. I have to jump in. So Fibonacci. Yes.

[00:58:21] **Carol:** Thank you. Go ahead. Look, there are just buttons on my screen. I have

[00:58:24] **Adam:** to press them. The next number in the sequence is. The sum of the two numbers before it. So you start with zero and one, and then the next number is one. So you just use one as your starting point in points for stories.

[00:58:37] **Adam:** So it's one, two, three, five, eight, 13, 21, 34, and on. We start with two. 55, you want me to keep going?

[00:58:48] **Carol:** The only thing that's a one for us is if it just requires someone to go answer a question on something, or it's like a reminder task to go make sure something got done.

[00:58:58] **Adam:** Okay. Yeah, I, I think we've kind of, yeah, yeah.

[00:59:02] **Adam:** Well and truly beat this horse. Oh, yeah. Maybe we should move on to the next one. Oh, can we do the top one? Yeah, yeah, yeah.

[00:59:09] **Carol:** Go ahead. Yeah. So at LD two on Twitter, ask, how do you guys feel about learning new technology while maintaining a code base? That is going away soon, but not too soon.

[00:59:22] **Adam:** I mean, that's my life.

[00:59:24] **Adam:** It's always going away, right? But it never does. I have, I have something to say about this one. I, I used to have, you can, you guys can see the stuff on my wall behind me. I used to have a cork board up in my office that I divided up into six sections. And it was like the next six months, right? And I had like little cards that I would put, okay, the current month is the top left.

[00:59:45] **Adam:** And then it was, you know, the following months after that. And I would move stuff around. Over time, and I put this card, originally when I created the corkboard, I put this card on in month six that was CFML GTFO.

[01:00:01] **Adam:** What is GTFO? Get the frick out. And, uh, it just, every month it got moved closer and closer and then it got moved further and further back out and we still have... Now it's not on the wall. Yeah. The cork board didn't last and we're, we have changed CFML engines, but... It's still an indeterminate amount of time before we're going to be completely off of it.

[01:00:27] **Adam:** It's, technology choices never die, I feel like. What's your feelings, Carol? Yeah, so

[01:00:34] **Carol:** I feel like you should go learn it. So go learn the new so that it motivates you and your team to push for the change. Yeah. And if nothing else, you are thinking about how to write your current code in this language in a way that's portable to the new language.

[01:00:50] **Carol:** Because you need to now be thinking about functions that you could easily pore over to this new methodology of how you're going to be writing code. So go learn it. Learn it, learn it, learn it, and then push for it, and keep pushing for it, till people listen.

[01:01:04] **Adam:** Kind of

[01:01:04] **Tim:** what our book club that we're doing right now is talking about now, it's like the language you write is not so much as important as how you write it should look like it was written specifically for the application that you're writing.

[01:01:15] **Tim:** Yes. Right? And you can do that in any language. It's not, language snobs, you know, go screw yourselves. It doesn't, it doesn't really matter. So the fact that you're moving to somewhere else is, you know, could be based on financials, could be based on whatever. But yeah, Carol, you're totally right that, yeah, learn the new, learn the new technology because you're probably going to learn new things that you haven't been exposed to on your current technology.

[01:01:44] **Tim:** Yeah, and honestly, it's probably not going away as fast as you think it is because, I mean, I, I still interface with customers who. On AS400 mainframe machines today, right, that these things were built in the 70s. They don't die. You can shoot a bullet through these things and they don't die.

[01:02:04] **Ben:** I think part of the value of learning new stuff is because.

[01:02:08] **Ben:** overestimate how different technologies and languages are. Oh yeah. And I think what we discover is that when we learn something new, what we find is that we can actually backport a lot of that understanding into the quote unquote older technology. Because whether it's a relational database and now you're learning about document databases, there's a lot of transferable information about how indexes need to be designed and how things are atomic or they're not atomic.

[01:02:35] **Ben:** You know, it's even... Front end frameworks, whether you're moving to more of like an immutable data store, there's all kinds of concepts that can be ported at least in part or in degree to the existing code. And what you can actually do is start to clean up your existing code and put more modernized concepts into it.

[01:02:56] **Ben:** And over time, if you babystep that long enough, I think what you discover is that your old code actually starts to look kind of hot. It's not

[01:03:06] **Carol:** so bad, is it?

[01:03:07] **Ben:** Yeah. You might even reach a point where you're like, why are we even moving on to something else? Cause now I'm feeling pretty keen on the way we're doing stuff here.

[01:03:14] **Adam:** It was me all along, Ben, it was me all along. Or

[01:03:18] **Carol:** even if they do decide to move over, that legacy app that's still standing, it's a lot easier to maintain too. But good question.

[01:03:26] **Adam:** Yeah. Very good question. All right, we could probably squeeze one more in here. So, all right, last one for tonight. Again, from LD2 on Twitter, thank you for all of your questions.

[01:03:36] **Adam:** How important is having a GitHub? We host GitLab, so I don't have much publicly. So, it sounds like this is for your personal, like almost for your resume sort of thing. How important is it if you were to be looking for a new job or something like that? And I think I need to jump in and say, It shouldn't be important at all because not everybody has, uh, the time to, uh, to, to devote to doing, you know, open source.

[01:04:04] **Adam:** side stuff for fun or for, uh, resume boosting stuff. Like, you know, if you're a single mom and you have kids and a job and, um, stuff to do, then, then you just might not have time to do that. And maybe you're busy taking your kids to soccer practice or whatever. Um, and, and so it shouldn't count against you to not have stuff on GitHub, but that said.

[01:04:28] **Adam:** It's not going to hurt you to have stuff there either. And I think as somebody that occasionally hires somebody, I will say, um, if you have something on, whether it's on GitLab or unfuddle or whatever, you have something publicly visible, even if it's a zip file on your blog, like. I would count it, right?

[01:04:44] **Adam:** That's if you've got something that you've worked on that you're proud of, and you want to share that code with me as a potential hiring manager, then, you know, I give the same credit, whether it's, you know, it's embedded in blog articles or if it's on your GitHub. And

[01:05:01] **Tim:** I hire, I've hired in my career, lots of people.

[01:05:05] **Tim:** So I've looked at people's GitHub if they have it, but if they don't have it, I don't see that as a negative because there's a lot of people that work in sectors of. Uh, that can't release things. Right. I understand that, right? It's like, we, our, our GitHub, we have GitHub, but it's not public. Right. I mean, you can't go look at most of my code.

[01:05:27] **Tim:** I've done a few open source projects and stuff with QR codes and things like that, but, um, most of my work is behind a very private GitHub account that you can't, I can't reference that if I wanted to go get another job. So I wouldn't worry too much about that. The fact that you are working. Do you have a job and what you've worked on and the type of skills that you've cultivated is much more important on a resume than being able to show someone, you know, this is something I've worked on.

[01:05:56] **Adam:** I would say if you don't have something open source that you can share, something you probably can do is take notes on projects that are interesting or that you're proud of. Think about what about that project is interesting, um, or that you're proud of and, and be able to fit that into your resume in, you know, some short format.

[01:06:14] **Adam:** And then when they ask you about that, have a couple of facts ready to go that, uh, that make it possible to discuss that and to show that, you know, you're interested in learning, you can grow and you can solve hard problems, that sort of thing. And

[01:06:30] **Tim:** one thing, listening back, I actually did listen to our, um, interviewing podcast.

[01:06:38] **Tim:** You can bring up. That is important to the person who, because the person who's hiring is not always necessarily a technical person. They might be, the first interview might be a technical person. The second person might be more of a higher business C level kind of person, um, is to bring up the amount of revenue that, that you've generated.

[01:07:00] **Tim:** Even if you don't feel you necessarily earn that revenue, because a lot of times people who are writing stuff don't realize the revenue they're generating, but just saying that I wrote this product and this. I worked on this product. This product generated this much revenue for the company. If you have access to that data before you start moving to somewhere else, definitely bring that out because that is...

[01:07:20] **Tim:** That is a huge factor in hiring, is the amount of revenue that you can bring. Yeah,

[01:07:24] **Adam:** I mean, if you can say we had a Lambda function that was taking 300 milliseconds to run and I got it down to 100 milliseconds and it executes 10 million times a day, so that saves us, you know, whatever, 1, 000 a day, then that's huge.

[01:07:38] **Tim:** Or even revenue savings, like, you know, there was a service that we had that costs, you know, 10, 000 a month to run and we replaced it with this service that costs, you know, Five, you know, five, 5, 000 a month to run. I mean, things like that are much more important in hiring if that's what you're actually

[01:07:56] **Adam:** asking on this question.

[01:07:56] **Carol:** It shows you're well rounded and are thinking about more than just the code you write. It's the whole business

[01:08:02] **Tim:** layer. Yeah. That makes, it makes you look like a business player rather than just code slinger. And the other question that LD2 asked was, I know you said it's the last one, but I'd really like the last question about, would you rather be a jack of all trades?

[01:08:17] **Tim:** Oh man. Would you rather be a jack of all trades of the development cycle, or just know one part really, really well and leave the rest to other DevOps? I totally want to be a jack

[01:08:29] **Adam:** of all trades. All trades, all day.

[01:08:31] **Tim:** I want to know all things, all times. Triple

[01:08:33] **Adam:** down. See, um, the longer I go, the more I get interested in specializing.

[01:08:39] **Adam:** Yeah, not

[01:08:40] **Ben:** me. I think the powerful thing about being a jack of all trades is that you can't do things super well, but you can get a lot done.

[01:08:51] **Adam:** Yeah. Here we go. It may have been one of you guys that said this, but it's a concept I've heard recently in whatever, being T shaped, right? So you can, you have a basic level of knowledge across a lot of breadth, but then on something you go very deep.

[01:09:09] **Adam:** And I think that that is a very, uh, good, a good approach, right? So you, even if you don't know the answer, you know who to ask or what to Google or, you know, where to find the right documentation. And then you have that thing that you are the go to person for.

[01:09:26] **Tim:** The best thing I like, because I do consider myself a jack of all trades, because I do know DevOps.

[01:09:32] **Tim:** I do know programming. I'm more deep on programming than I am on DevOps, but I'm pretty, I'm pretty damn good at DevOps. Um, is that people can't BS me. I, I, sometimes I'll get pushback, particularly from the infrastructure people that, you know, the, Oh no, I'm like, well, wait, hold on. Really? Isn't it just doing this?

[01:09:55] **Tim:** And I'm like, well, yeah.

[01:09:59] **Carol:** Let me

[01:09:59] **Adam:** break out my Google Fu for this. Yeah, so I,

[01:10:02] **Tim:** I don't necessarily know how to do a, like, particularly Apache. I'm not an expert on Apache, but I, I do know enough to set up an Apache server Sure. And, and configure it. I, I've done it. And so when, if I get pushback on something particular because someone just maybe is not that comfortable on it, I'm like, this should not be as hard as you're saying.

[01:10:23] **Tim:** And so that, that for me is why I like being a jack of all trades because, I had, I don't know, I'm not maybe an expert on everything, but I know enough to know when someone is blowing smoke.

[01:10:35] **Ben:** It's an interesting perspective. Plus, I think... You also have a better sense of how much effort that an entire project might take.

[01:10:44] **Ben:** Because you can, you know, squint your way through, here's what it would take to set up a backend, here's what it takes to set up a database, here's what a front end effort would take. So it's not, it's not, I know this one area really well and then the rest of it is a black box. It's, I fuzzy understand most of this to some degree, so it's not as complicated as, as I think.

[01:11:05] **Ben:** And for me,

[01:11:05] **Tim:** it's more the community, being able to communicate with the infrastructure folks to be able to say, look, here's what I'm asking for. I understand the impacts here and, and I don't necessarily need this, this and this, which I know is really hard. So we don't need that right now. We'll put that off later.

[01:11:24] **Tim:** But give me this, at least to get going. And then I understand that this is much harder. We'll, you know, I'll give you time for that. And so, cause a lot of times you just get immediate pushback. Like, oh, wow, what you're asking for is way too big. Yeah. Yeah. It's too big. I'm like, I know it's not, I know it's not impossible.

[01:11:43] **Tim:** Here's the steps to get there.

[01:11:46] **Carol:** Yeah. I want to know enough to be able to at least ask the correct questions.

[01:11:51] **Adam:** Exactly. All right. Well, it sounds like we're done. Wrap

[01:11:54] **Ben:** it up. I want to say one more thing just about. Going back to the Kanban versus sprints. Go for it. It's just like a PTSD moment I have. I remember at one point our team was, I think we were, we were using JIRA.

[01:12:09] **Ben:** We still use JIRA, but we had switched over to JIRA. And I think we were, this was the first time we were trying to get into more of some sort of a formalized agile mindset. And someone in a meeting brought up this idea of, well, in JIRA, they have tickets or they have tasks and they have stories. And they're like, should we come up with some sort of rule about.

[01:12:28] **Ben:** What things are tasks and what things are stories and I was just like, every moment you spend discussing that is a moment I will never get back in my life. Like, it's a task. Whether you call it a story, it doesn't matter. It's something you move across the board. If you spend even a moment. Worrying about which one is which.

[01:12:46] **Ben:** I'm like, I will flip this table over. .

[01:12:50] **Carol:** I knew it was coming. Well, I

[01:12:51] **Nathan Strutz:** mean,

[01:12:52] **Adam:** hold on

[01:12:52] **Tim:** Ben. Hold on, hold on.

[01:12:54] **Ben:** I will flip this table and hold on. I, and I, I'm not saying that about all the types of cards you can have in Jira. Like I think there is a legitimate difference between an epic Yeah. And a story. I'm not gonna fight you on that, but like, Once you're low level, I just, just move the card across the board.

[01:13:12] **Ben:** It's more

[01:13:12] **Carol:** of, is it a task? Is it an issue?

[01:13:16] **Tim:** I think a story is basically, it's a user story, right? And those user stories are made up of tasks. It just seems a natural

[01:13:24] **Ben:** progression to me. But I don't think stories can contain tasks. I think that's an epic, I think, can contain tasks. No, am I wrong? I don't know what Carol, I don't know your sign language.

[01:13:36] **Ben:** Yes and no.

[01:13:37] **Carol:** Epics can create, can contain stories and then tasks are on the stories. So like right now I have an epic to do this entire OKR. And then I have a story for my Gmail piece and for my integration with Google. And in there, I have all the subtasks, which are create the authorization, um, set up the Lambda for it.

[01:14:02] **Carol:** It's, I have individual tasks

[01:14:04] **Ben:** that are broken down. I don't know if that's how, I, I, do you, are you saying that in a JIRA sense or in a generic sense? JIRA. In JIRA. And you're saying that in JIRA, stories can have tasks? Yeah. I did not know that. Yeah, that's

[01:14:17] **Tim:** how

[01:14:17] **Adam:** I use them. And

[01:14:18] **Carol:** every task, so whenever, every story I have, whenever I'm ready to hand it over to SQA for testing, I actually enter a SQA sub task that says, test this and

[01:14:29] **Nathan Strutz:** assign

[01:14:29] **Ben:** it to them.

[01:14:30] **Ben:** In my defense, one, I thought Epic was the only thing that could contain other things. Uh, but in my subsequent defense, no one on my team knows that stories can contain tasks. Well, we won't tell them. We were literally having a semantic discussion about when something should be called a task and when it should be called a

[01:14:49] **Carol:** story.

[01:14:49] **Carol:** Uh, yeah, that's not fine. Just make a decision and go with it. I gotta,

[01:14:55] **Adam:** I gotta go back and check, but I'm pretty sure

[01:14:57] **Tim:** that's, I mean, that's a reason that the thing we just launched, we had an Epic, it was the integrated service. The stories were, as a user, I want to be able to call this phone number and get a policy number and look it up.

[01:15:09] **Tim:** And the tasks were, go call this service, go call this service, return this. And they were, yeah.

[01:15:15] **Adam:** I'm about to take a

[01:15:15] **Carol:** screenshot

[01:15:16] **Adam:** of mine for you.

[01:15:17] **Ben:** It reminds me a little bit too, at one point, so I don't know if people are familiar with the, the quote unquote Spotify model of, of teams where they have, they don't have teams, they have, um, zones and they have, uh, squads.

[01:15:32] **Ben:** And I remember at one point management at my company was like, well, we're going to switch from the team model to the squad model. And like suddenly, suddenly we're all going to become more effective. I don't, I have no idea what the intent was. It makes me think of, I don't know if anyone's seen a. Six days, seven nights.

[01:15:51] **Ben:** It's a Harrison Ford movie from like 20 years ago. Anne Heche, he's a, he pilots people into these Caribbean islands or wherever it is. And at one point he's flying Anne Heche to this island and, and she's talking about whether or not it's a, it's a great place and it's great for romance. And he just looks at her and he's like, It's an island, babe.

[01:16:09] **Ben:** If you don't bring it with you, you ain't going to find it there. And I feel like that's how teams work. Like, whether you call your team a team or a squad, like if you don't have the people who want to do work, the organization is not going to make a difference. Yeah, sometimes

[01:16:23] **Tim:** I think management just comes up with ideas that, you know, they're, they're struggling to make change and they think that just introducing new terms for the same stuff is going to affect change.

[01:16:33] **Tim:** Well, the

[01:16:33] **Adam:** innovation team has to do something, right? Yeah. I just want to be

[01:16:37] **Carol:** on the rainbow team.

[01:16:39] **Tim:** Yeah, it's a solid team.

[01:16:41] **Carol:** Alright, I added a screenshot. We're going to confirm this. So the BP16863, whatever that first number is, that is my EPIC. The 68 is my story, and then you see how I hovered over my

[01:16:56] **Adam:** technical path.

[01:16:57] **Adam:** That's what I thought.

[01:16:59] **Ben:** How did I not know this?

[01:17:00] **Carol:** So maybe you guys don't have JIRA configured the same way we do, because you do, you can configure workflows.

[01:17:08] **Tim:** I mean, it just, it just totally makes sense to me. You have an epic, which is like, this is the project. Yeah. The whole thing. When the epic is done, the work is done, and then you have a story, which is part of the part of what you're building as a user.

[01:17:22] **Tim:** When this It's a user story. Yeah. As a user, I expect this to happen when this happens and you have the tasks that make that up. Yep.

[01:17:29] **Adam:** Now, I don't, we don't use JIRA at all, I have very little JIRA experience, so I'm just a fly on the wall here. You're a good looking fly. Thank you. With a nice haircut. Buzz buzz.

[01:17:40] **Adam:** Buzz buzz, haircut.

[01:17:42] **Ben:** Oh, you know what? In JIRA, at least in the way we have it configured, I can create subtasks under tasks.

[01:17:49] **Carol:** Oh, I cannot create tasks under tasks.

[01:17:53] **Adam:** Oh, he said subtasks, I don't know if there's a difference. Oh, you

[01:17:56] **Ben:** know. So, I don't know.

[01:17:59] **Adam:** Welcome to the JIRA podcast, right? Sponsored by, not sponsored by.

[01:18:04] **Adam:** Bit needs a consult.

[01:18:06] **Ben:** Listen as we describe the user interfaces.

[01:18:09] **Tim:** I, I checked that out.

[01:18:10] **Adam:** Cause yeah,

[01:18:12] **Tim:** I agree with you. If, if I were arguing about if a story and a task needs to be labeled that when they are. actually effectively mean the same thing, I'd be like, yeah, just, just stop.

[01:18:21] **Adam:** Yeah, don't waste my time.

[01:18:22] **Adam:** Kill me now. Alright, we are definitely getting into the weeds of a place that we don't need to be, so we're gonna close the show out there. That was my bad. I'm gonna go over here and thank our Patrons. So we've got a bunch of people supporting us on Patreon and we really appreciate their support. If you think we've earned it, please consider supporting us on Patreon.

[01:18:40] **Adam:** You can find us there at patreon.com/WorkingCodePod. We have different support tiers with different perks, like a lifetime invite to our Discard, sir. Discard? Discord. We're playing card games now, apparently. We have different support tiers with different perks, like a lifetime invite to our Discord server.

[01:18:54] **Adam:** I said it again, Discord. We have different support tiers with different perks, like a lifetime invite to our Discord server, early access to new episodes, and the after show where we keep the mics running for another 10 to 15 minutes after the show ends. And we are getting the ball rolling. We're going to try to start doing occasional, like, game nights.

[01:19:11] **Adam:** We're going to meet on online, play like D&D or Among Us or something. So that'll be fun. And we also have what we call our top tier on Patreon for people who want to pay a little bit extra and in exchange, they get what we call a sponsored shout out. So this week's Sponsored shoutout is going to go to the Grace Hopper celebration, that's ghc.

[01:19:33] **Adam:** anitab. org. We'll definitely put that in the show notes for you. Uh, and to everyone that just listens to the show, thank you for listening. Don't forget to share the show with a friend because there's no better support than a word of mouth referral. Tell the algorithms to boost our signal by leaving us a review and a rating on iTunes or wherever you get your podcasts.

[01:19:50] **Adam:** Send us your topic suggestions on Twitter or Instagram @WorkingCodePod or leave us a message at 512-253-2633. That's 512-253-CODE. Hotline. We'll catch you next week and until then, your heart matters. Nice.

[01:20:25] **Adam:** And we are starting to start the starting to start the process.
