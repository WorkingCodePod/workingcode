---
title: "099: Technical Debt Isn’t Always A Choice. Or Is It?"
description: "Adam, Ben, Carol, and Tim are all back at it again. And today, we're talking about technical debt."
date: 2022-11-02
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/099-technical-debt-isnt-always-a-choice-or-is-it/id1544142288?i=1000584779305"></iframe>

Sponsors

- [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

This week, we're super excited to be getting the band back together! After several weeks of personal and professional obligations, Adam, Ben, Carol, and Tim are all back at it again. And today, we're talking about **Technical debt**. When engineers talk about technical debt in public, they often try to use financial metaphors; such as taking out a loan in order to buy a house.

These financial metaphors _romanticize_ the notion of technical debt, elevating it into the realm of _calculated decision making_. But, if we're being honest without ourselves, is any kind of calculation really taking place? Or, are we just trying to do the best that we can with the knowledge and experience that we have? In other words, isn't most technical debt _really_ just the result of engineers writing janky code at the limit of our capabilities?

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/099-technical-debt-isnt-always-a-choice-or-is-it.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** someone asked for my feedback, they're like, Hey, can you jump in and leave some feedback about option D? And it's talking about all the risks and then under all the mitigations, they're like, Oh, we'll mitigate the risk by having lots of unit tests and integration tests.

[00:00:11] **Ben:** And I was like,

[00:00:12] **Adam:** Uh, talking to the wrong

[00:00:16] **Adam:** guy.

[00:00:17] **Carol:** Yeah.

## [00:00:18] Intro

[00:00:18] **Adam:** Okay, here we go. It is episode number 99 and oh 99, almost a hundred. We're, we're nearly there. but, on today's show we're gonna talk about technical debt, but we're gonna do it a little bit of a different angle. I think we've discussed technical debt previously episodes 60 many weeks ago, 39 weeks ago, I guess it was.

[00:00:56] **Tim:** did you do that in your head?

[00:00:57] **Carol:** Dang.

[00:00:57] **Tim:** Wow. You're a genius.

[00:01:01] **Adam:** I, I do maths. Well, I guess. but this time we're gonna do it a little bit differently. Is technical debt always a choice? Is it not? I guess we'll see. But first, as usual, we're gonna start with the triumphs and fails. And Tim, I'm gonna come to you first.

## [00:01:13] Tim's Triumph

[00:01:13] **Tim:** All right, so I'm going with a triumph for two reasons. It's fallen in the South, which I mean. You guys have If you, if you live up north, you have no idea what fall is like in the south after months and months of relenting, over a hundred degree, whether 90% humidity with no rain, it to, to go outside and not feel like you're sucking soup through a straw. And to put on a sweater. It's sweater weather, sweater weather. It's amazing. So yeah, that's just, that just sets me right to just, you know, go outside and feel cool. Like 60 degree weather. It's like in the low thirties in the at night. It's great.

[00:01:53] **Ben:** Oh, I didn't realize it gets down that low in the.

[00:01:55] **Carol:** Yeah, and we had to drain out our pull pipes so they don't burst. Mm.

[00:02:00] **Tim:** to pull all my, uh, potted plants in and so they wouldn't freeze the other night.

[00:02:05] **Tim:** But yeah, besides the weather, so this week I've been, so we're working on doing a Strat session for our company. So as I mentioned before, where our company, my division is separating out as its own company. And so we're really doing our very first Strat session as a for us, right? So we'll be working on our, I don't know, I think most companies kind of do some sort of version of a Strat session per year where you basically plan for the next year and say, All right, you know, what are our goals, but we're really coming at this from, you know, Ground zero.

[00:02:40] **Tim:** Like what is our company vision? What is our core? What are our core values? What is our b a g our big, hairy, audacious goal? You know, where do we wanna be in three years, five years, 10 years kind of thing. What, what, who is our identity? What are we as a company? You know, what do we wanna project to the market as we are?

[00:02:58] **Tim:** So we're going through all that kind of stuff. So I'm really looking forward to that. you know, it's gonna be three days. next week, three days and just, just kind of planning the, the agenda for the Strat session. I won't be running it. I don't think it's good for kind of the leader to run it. You need sort of an a, a third party, an objective person to, you know, to run things into speak truth to power.

[00:03:20] **Tim:** So, but fortunately because we're such, we're part of a big organization. we have a sister company, someone from another company I've known her for years. She's fantastic. And she runs another company similar to ours, and she's coming over and she'll run the, the strategy session. She'll be the facilitator and, really looking forward to it.

[00:03:38] **Tim:** I just, you get so much outta these Strat sessions to say, All right, what are we doing next year? Cause the best thing about it, what I love about it is that it's like we have all the major players, all the key players will be in the room and they will all, It's not. Top down saying, you know, someone from the top saying, Here's what we're doing next year.

[00:04:00] **Tim:** If you don't like it, leave. It's like we start from the ground up and say, you know, what's the plans for next year? Here's the goals, here's the financial targets we want to hit. How do we think we can get there? And then everyone comes up with ideas. And you know, when you're in the room and you come up with the idea, You know, you feel empowered to make them happen.

[00:04:20] **Tim:** and you can't say afterward like, Well, I don't agree with the vision where we're going, because you had time

[00:04:27] **Ben:** Right.

[00:04:27] **Tim:** give your input. If you didn't give your input then, then what were you doing in the room

[00:04:31] **Ben:** You had your chance and you blew it.

[00:04:33] **Tim:** You blew it. Yeah.

[00:04:35] **Carol:** There is something about having buy-in, right? Like I will go all at it if I feel like I was part of the decision. Even if my idea doesn't come to play, if what I'm pushing for doesn't work. You still heard me? I had the chance to say what I wanted and now I'm sold. Like no matter what the decision is, I'm committed.

[00:04:56] **Carol:** So either we went my way, we don't. It's, it's crucial to get that buy in from your team. So it's awesome that you're doing that. It, it'll definitely help you be successful.

[00:05:06] **Tim:** Yeah, and it's one of those things when we got bought in 2013 that Constellation software, you know, made, made us do, We didn't do that before. It was all very top down driven and it was a bit toxic, honestly, cuz you know, if, if the plans didn't work then

[00:05:20] **Carol:** which way was toxic? The older, the

[00:05:22] **Tim:** the old way. So if, if, if, if the plans didn't work, cuz you know, the people at the top said, Oh, we're doing this because we know better and then it didn't work.

[00:05:30] **Tim:** People at the top aren't gonna. Blame for that

[00:05:33] **Carol:** Right. Yeah.

[00:05:33] **Tim:** they're gonna say, you guys didn't execute it. Right? Right. So, and then it became a battle between the, you know, the haves and the have nots. So I, I think just getting everyone on board and saying, Here's our vision for 2023. Here's what we're working on.

[00:05:46] **Tim:** Here's, you know, the things we're gonna build, the processes we're gonna improve. And, you know, some of them work, some of them don't. And then next year you just, you know, you pivot and you work on other stuff. But that's, that's what I've been working on this week and looking forward to that next week.

[00:06:02] **Ben:** I, I like that. I've never heard the phrase b a g before, but I'm enjoying that.

[00:06:07] **Tim:** Yeah, so that's, I mean, so when we first got acquired, we were like the second company. That got acquired, in this portfolio, of businesses. This was the insurance and, and financial services portfolio. And so it's like a tiny, I mean, we were just, I mean, small and the other company was small, and now this company is like this, this portfolio, the b a g, that the guy, you know, who is our, the guy who bought our company, he was the one who facilitated the buy.

[00:06:36] **Tim:** He's like, You know, I want to be. he talked some several hundred millions of dollars, you know, our portfolio in, within, 10 years. And I looked at him like, You're crazy I was like, You're absolutely crazy. And not only did he meet that, he met that within five years, and he's doubled that in 10 years.

[00:06:53] **Tim:** So, yeah. So

[00:06:56] **Ben:** crazy.

[00:06:57] **Tim:** so if you don't shoot high, you're, you're not gonna get. How about you, Adam?

## [00:07:01] Adam's Fail

[00:07:01] **Adam:** Oh goodness. I think I could go either way this week, but I think I'm gonna go with a fail just because I'm in pain right now. I'm on antibiotics for the strep throat that I mentioned last week that I was struggling with, and they're helping greatly with the strep throat. I'm, I'm feeling fine in my throat, but the medication that I take for my autoimmune disease is a biologic, medication, which as far as I know means it's like alive.

[00:07:25] **Adam:** and this is just me theorizing. I'm not a doctor. I haven't talked to my doctor about this yet, but, I get the feeling that the antibiotics are killing whatever is in my medication. And so the medication's like not really able to help me. So I've been, you know, I have previously discussed with my doctor and they said it's fine for me to increase the recommended dose of ibuprofen.

[00:07:44] **Adam:** So normally you take two pills. I take three when it's just a mild pain, and four when it's a bad pain. Still on the every six hour schedule. And when it starts to wear off, I can tell I'm in significant pain. So, I'm not feeling great, but

[00:07:58] **Tim:** Plus antibiotics are tough in your stomach.

[00:08:00] **Carol:** They are. Yeah.

[00:08:01] **Adam:** I mean, stomach issues is kind of my baseline anyway,

[00:08:05] **Tim:** Yeah.

[00:08:05] **Adam:** So,

[00:08:07] **Tim:** that's, that's, that's your, immune problem, right? Your stomach.

[00:08:10] **Adam:** yeah, it, i b d is one of the many afflictions that I suffer from.

[00:08:14] **Carol:** oh man.

[00:08:15] **Adam:** so yeah, you know, can't really tell the

[00:08:17] **Carol:** I'm sorry.

[00:08:18] **Adam:** problems. But the back pain I could live with, I brought, So I'm in a hotel, I'm in Washington, DC this weekend, for work, and I brought my heating pad with me because I like to sleep on it or just lay on it, you know, in the evenings.

[00:08:32] **Adam:** When I'm resting

[00:08:33] **Carol:** Aw, that's the worst. Like when you're traveling and you're feeling bad, like at least when you're at home, you can go get in your bed, right and cuddle up to your pillow next to your spouse and have a little

[00:08:44] **Tim:** or your

[00:08:44] **Carol:** like Yeah. Or your dogs, Yeah. Whatever it is. And yeah, I'm sorry.

[00:08:50] **Adam:** Thanks. Well, I guess that's gonna do it for me. So, Ben, how about you?

## [00:08:54] Ben's Fail

[00:08:54] **Ben:** I'm gonna go with a failure this week, and that is that, Docker is hard Could be hard. And it's one of those things where when it's working, I don't quite understand why it's working and then when it breaks, I don't really know what to do about it. and, and it's also one of those situations where it really shines a light on just how much more engineers need to know depending on i, I guess, where you are in your, in your job stack.

[00:09:21] **Ben:** But like, so the, the thing that wasn't working for me is that, I, I was trying to get my local ColdFusion development environment working just for my personal stuff. And, Adobe released a new hot fix for their, some security hot fix, which suddenly made something break in the command box image that I was using.

[00:09:39] **Ben:** And this is not a knock against command box or anything, it's just something was, was a little wonky

[00:09:44] **Adam:** An Adobe changeaffected command box.

[00:09:47] **Tim:** Hmm.

[00:09:47] **Tim:** Looks like they don't even care about the community.

[00:09:50] **Ben:** I was, I'm using Command Box to, to start up an Adobe ColdFusion image.

[00:09:55] **Adam:** Gotcha.

[00:09:56] **Ben:** and, and it's just like, and it doesn't work. I, I don't know what to do. I don't even know where to start debugging it.

[00:10:01] **Ben:** I, it had something to do with modules being installed, but, and then once I got that working, it wasn't using the right home directory for the server and I was complaining about this on, on Twitter, I think it was, and, or, or no, Facebook and Tom Shiver was like, Oh, just copy over your server XML file and change the app route for the Tom Cat context.

[00:10:25] **Ben:** I'm like, I don't understand any of the words you just said.

[00:10:28] **Carol:** Oh,

[00:10:30] **Ben:** But it's one of those things, It's, it's like I, I, I'm reminiscent of the, I'm nostalgic for the days when it was just code and code is all I needed to know. And when something went wrong, it was something going wrong in the code because there was someone who managed the IIS server and the, the like s ColdFusion mod connector, whatever that did to forward ports.

[00:10:50] **Ben:** I, I don't really know. But now, like you just don't have those people anymore. And it's like, if you kind of have to, what you need to know bleeds out into the rest of the stack and it's, it's it's just not coming very easily for me. I code for whatever reason. I'm not saying I'm like, you know that I know everything about code, but code

[00:11:08] **Tim:** Could make sense to you.

[00:11:09] **Ben:** enters my brain.

[00:11:10] **Ben:** Yeah. Code just makes sense. And I, I think, I, I really just have to sit down and learn Tomcat or you know, like there's some you Udemy courses on Tomcat. I think I might try and take just cuz. Things, I, I don't know what a server it is. I don't know what a context is. I don't, I don't know the difference between like a, a web route and a context.

[00:11:32] **Ben:** I don't know what the web in folder is and the meta inf and it's just like, there's all these magical files and folders that do really important stuff and I don't, It's a

[00:11:42] **Tim:** And what makes it harder is when you Google it, you get stuff from 2015, not not from

[00:11:47] **Adam:** Wait,

[00:11:48] **Tim:** right now.

[00:11:49] **Adam:** You

[00:11:49] **Carol:** And yeah.

[00:11:49] **Adam:** I think you meant to say like 1015,

[00:11:55] **Tim:** Now, come on.

[00:11:57] **Adam:** Man. You just have been, everything you've been saying is just reminding of me, of all of the myriad reasons that I hate everything about Java. I, I can't stand working in that stack because it's, it's everything about working in that stack is very similar to the problems that you just described, every aspect of working.

[00:12:15] **Tim:** you were talking about Docker, so it's like I, I, I went down that rabbit hole as well with Docker, and then I realized, like, you know it, and this is just my use case, I didn't really need Docker. I wasn't deploying Docker to production. What I really needed was Vagrant. I just needed a simple way to spin up a VM to do stuff locally.

[00:12:35] **Tim:** Change code. And that's been a whole lot easier. Once I, once I've realized, you know what, I really don't need docker. I'm like, okay, life's much simpler cuz I just need something to spin up a VM for

[00:12:44] **Carol:** Yeah, don't add that

[00:12:45] **Carol:** layer of complexity.

[00:12:46] **Ben:** but I never, I never learned vagrant or chef or puppet or whatever. I like, I never learned any of those things. So Docker was really my first foray into trying to automate machine based development workflows.

[00:13:02] **Ben:** So there's no, I don't have, like, the fallback for me would be just installing it locally on

[00:13:07] **Ben:** my host machine.

[00:13:08] **Tim:** Yeah.

[00:13:09] **Carol:** Having the server run.

[00:13:10] **Carol:** yeah, Like I will do this myself,

[00:13:15] **Ben:** It's every time I feel like maybe my mental model for Docker is beginning to gel, I'll go and look at someone else's docker file. Like I'll go to a Docker hub and you can look at the Docker files for some of those things. And like, I don't understand anything that's happening in those Docker files. And it just, it makes me feel so defeated.

[00:13:36] **Tim:** It's funny, I, I actually saw that interaction that you're talking about on Facebook, and I saw the guys reply like, Oh, Ben, you just did this. Like, I just went right over, Ben.

[00:13:46] **Carol:** You? No. If you were a good friend, you would've called Ben immediately and been like, Look buddy, don't cry. We're gonna get through this. Take a deep breath. I know, I know this is struggling, but, I, I know you're gonna be okay

[00:14:02] **Ben:** So, so yeah. So that's me. I, I really just need to set some time aside and, and do a little bit deep learning. Which is not something I've really done in a long time. So

[00:14:12] **Carol:** or maybe consider a different route. I'm like, Tim adjusted

[00:14:17] **Ben:** that I feel like that's, now I'm learning multiple things. I need, I need to learn like, one more thing,

[00:14:22] **Adam:** Let me ask

[00:14:23] **Ben:** not completely start

[00:14:24] **Adam:** Is it gonna be beneficial for your future at all to go deep on Tomcat and Java and learn all

[00:14:31] **Ben:** I, I don't think I need to go deep, deep, but like, I need to have a, I need to have at least a, a general understanding of how these things fit together. I

[00:14:41] **Adam:** Do you though,

[00:14:42] **Ben:** I mean, apparently I do

[00:14:44] **Tim:** I don't know. Cause

[00:14:45] **Adam:** mean, do you think you can make it to the end of the year without learning this?

[00:14:50] **Ben:** This isn't for work. This is, this is for my, personal site. I, I, for my local development environment,

[00:14:56] **Adam:** Just start over. Move to Word.

[00:14:58] **Ben:** just,

[00:14:59] **Carol:** I moved a WordPress

[00:15:00] **Ben:** it in a node and import the HTP module. And you're

[00:15:03] **Tim:** just do a, do a static side. Put it in j

[00:15:07] **Ben:** All right, so that's me. Carol, what about you?

## [00:15:10] Carol's Fail

[00:15:10] **Carol:** Hey, well, I mean, I guess I'm gonna go with a triumph, sort of the first one's, Hey, I'm back, right?

[00:15:16] **Tim:** Yay. We missed

[00:15:18] **Adam:** Yay, welcome.

[00:15:19] **Carol:** thanks guys. I've missed y'all to you. So, had a lot going on though the past several weeks. so the, the triumph's going to quickly turn to a failure and then maybe a triumph. so over the past few weeks, had some mental stuff going on, was dealing with some family things and some panic attacks and some, you know, trying to just breathe a little more.

[00:15:41] **Carol:** And then right after kind of feeling like I was back on my feet, we did mass layoffs.

[00:15:47] **Ben:** Hm.

[00:15:48] **Tim:** At your company.

[00:15:48] **Carol:** at my company, so my job's safe. I'll start there. You know, I'm gonna try to not cry cuz I still get a little emotional about it. But, Yeah, we had, we just, we had to make some cuts. Sadly, the market isn't where we expected it to be.

[00:16:01] **Carol:** the fear of recession is coming up hard. The next set of interest rate spikes that are predicted is not gonna be good for us cuz we're financial software and we are reliant on mortgages and we're reliant. This, this part of the business is reliant on people buying houses, people refinancing their homes, and that's not happen.

[00:16:23] **Carol:** So when you start looking at the people doing those jobs, those jobs aren't really needed for the market. So, we had to make some hard cuts and ended up laying off 27% of our staff. So, uh, there were, there were cuts at every level. It wasn't just, you know, some busy bodies, working little things. These were every single level and people that were doing good jobs, the people that were working hard, and it, it came with lots of tears and a lot of time trying to figure out how else we could do it.

[00:16:54] **Carol:** we've also, you know, close some offices cut back on those expenses. of course, like all the engineers are already full-time remote, so there's not seats needed for the, for us and for our teams. So we've, we've reduced costs where we could, but it just, it was a hard hit. It was hard to, you know, get that back to my team.

[00:17:12] **Carol:** And honestly, my fear now is losing my team. How do I convince these guys that, and gals, that jobs are okay, right? That we are moving forward and that these cuts were necessary to keep the company going. And it's hard to just keep building that trust with the team when they've seen something happen. So I'm just, I'm keeping the dialogue open, answering questions that they can, when I don't know the answers, I'm just pushing those to management and then reminding them , you know, I meet with 'em.

[00:17:43] **Carol:** I'm like, Hey, here's the five questions I'm still waiting on answers for. I promise you I'm still pushing even though I don't have an answer. And it's been great to have the guys just remind me that they know we're doing the best we can for them, and that they feel like I'm doing a good job and that I'm being transparent with what's happening.

[00:18:03] **Carol:** And. And to know that they feel like I still have their back and that I'm gonna fight for them has been great. But it's definitely come with a lot of tears, a lot of crying in meetings, a lot of, a lot of long nights. So,

[00:18:16] **Carol:** we're moving forward. We're gonna keep pushing forward with products that are going to bring in more income to head up our revenue, but it's gonna take a little bit of time to, to get people in good spots.

[00:18:28] **Tim:** Hmm.

[00:18:29] **Tim:** That sucks. I'm so sorry.

[00:18:31] **Carol:** Yeah. Yeah. I know Ben just went through some of this recently and man, did I immediately go, Oh, I feel what he felt now, and I understand

[00:18:40] **Tim:** Hey, but this is industry wide, isn't it? I

[00:18:42] **Tim:** mean, right now we're seeing this, I mean, after years and years of just tech, you know, hand over fist, just growing and growing, I mean, the big guys, Amazon, Microsoft, Facebook, I mean, they're all laying people off, just cuz I mean, I mean the economy is shifted right now

[00:18:59] **Tim:** for a variety of

[00:19:00] **Carol:** Yep. Yeah. And it was crazy cuz the same day we announced ours was when the big Intel announcement was made that they were gonna reduce staff because there's no need for hardware right now. Like they literally don't have hardware coming out. So Intel's so Intel had stuff going on. We, I was like, oh my.

[00:19:17] **Tim:** Which is crazy because, I mean, they just passed that chips law, right? Where the United States is trying to get, you know, less dependent on China for, for processors, and they're laying people off. I, I think that's gonna bite 'em in the butt.

[00:19:30] **Carol:** it might, but I think they're also seeing the, the signs of people aren't buying machines, right? You're not spending as much as you were if you're, if people are actually planning for a recession. Right. These, these extra things you may do with what you got a little longer. So

[00:19:46] **Adam:** I don't wanna go on a late stage capitalism rant, but, uh,

[00:19:49] **Carol:** I about

[00:19:50] **Adam:** think that the, the IBMs of the country are, you know, they're like, Okay, great, we can do manufacturing here, but they're not looking to build people jobs. They wanna build jobs that robots can do.

[00:20:01] **Adam:** And, you know, like

[00:20:04] **Adam:** not, Yeah.

[00:20:06] **Tim:** somewhat of a tangent. I think that is one of the things where, you know, because of Covid, everyone's working from, not everyone, but a lot more people are working from home now. So if it doesn't matter where you live and where you work, then what's. Companies from hiring, taking your job and going, Okay, well we'll just hire someone from India or, you know, Pakistan or, you know, somewhere where labor is cheaper.

[00:20:28] **Tim:** I, you know, I think that's the only good argument right now for going back to work is to say, Hey, I'm in the office and I'm being productive and you see my face and it's gonna be harder to fire me. But I, I, I think that's sort of the, the negative thing of if you can hire people from anywhere, then why are you hiring expensive people in the United States?

[00:20:47] **Carol:** Yeah, I don't know about like what you guys have with your customers and stuff, but I did find out that we have some, customers who have contracts with us that prevent us from accessing their data outside of the US

[00:21:00] **Tim:** Mm.

[00:21:00] **Carol:** So certain customers, like, you know, with these banks, like you can't actually touch their data if you're in another country, which we are having to cross because my husband's in the military, right?

[00:21:10] **Carol:** And he's staying in now. So we don't know where we're gonna be next, other than, you know, out west for a year. Then we don't know where we land. So I'm like, please don't go to another country. I might,

[00:21:21] **Tim:** go to South Korea.

[00:21:22] **Carol:** I might have to find a new job.

[00:21:25] **Tim:** Yeah.

[00:21:26] **Ben:** I, if it's any consolation, Carol, it, when we went through it at work, it was heartbreaking and it was first, I'd say like two weeks I felt like. I was just floating through space. Like, it just was so surreal. That's the word I kept using over it. It's like, just so surreal. And, but then eventually the company sort of gels around the idea that everyone is in this together and we're just trying to figure out how to keep everything going and where

[00:21:51] **Carol:** Right.

[00:21:52] **Ben:** the, the tough decisions And, and, ruthless prioritization is a phrase that they keep throwing around.

[00:21:58] **Ben:** and it's still not great. Like, that's not fun. But you do feel like at least it's like everyone is now pointing in, in a single focused direction. And, and, and that makes it better.

[00:22:08] **Carol:** Yeah, I mean we've definitely had some of those conversations around reprioritization of projects and what makes sense to keep working on. You know, we were doing a rewrite of the system that I work on, and now we're reviewing like, does it make sense to keep rewriting or does it make sense to, to do like smaller sets of people?

[00:22:26] **Carol:** So, I mean, we have a lot to figure out still, but those conversations are definitely happening where we're trying to make sure the priority's clear to everyone and that we're all on the same, same, same train. You know, we're getting to this destination together. So, yeah. So

[00:22:42] **Ben:** strong.

[00:22:43] **Carol:** thank you. Thank you. Trying my best.

## [00:22:45] Ben's Note To Self

[00:22:45] **Adam:** so our topic today, started out as a one of Ben's infamous note to self comments in our private channel and our Discord. But when we, when he left it in our Discord, the, the four of us kind of got to talking about it a little bit and we kind of decided it could be a whole show in and of itself.

[00:23:05] **Adam:** So maybe one of the two of you guys that haven't been with us for a couple of weeks could read that for us in the traditional Ben's note to self voice and, and then we'll get into it.

[00:23:17] **Tim:** Note to self, so many discussions about tech debt scare quotes revolve around calculated decisions. I e the developer took a shortcut, but in my experience, most of my technical debt stems from incompetence, ie. Naivete, meaning I literally don't know any better. At the time, there was no scare quotes, decision being made.

[00:23:50] **Tim:** Love, Ben.

[00:23:53] **Ben:** Excellent

[00:23:53] **Carol:** Great job. Great

[00:23:55] **Adam:** I love the way that comes out.

[00:23:58] **Tim:** All right. Where do we go with this one? Guys?

[00:24:02] **Tim:** Talk to

[00:24:02] **Tim:** us, Ben.

[00:24:03] **Ben:** I had this thought because as I've mentioned before, I listen to a lot of tech podcasts and tech adjacent podcasts, and for whatever reason, it feels like technical debt has been a hot topic lately.

## [00:24:14] Who's To Blame?

[00:24:14] **Ben:** I, I don't know why, but in most of the discussions around tech debt, they try to come up with metaphor.

[00:24:21] **Ben:** Like, it's like taking a loan out to buy a house. So you're taking on that debt, but it's, it's for a good reason. And the underlying concept there is that you're making this calculated trade off. I'm, I'm doing something that's maybe not the right idea in the short term, but it's gonna have, a payoff and I'm gonna be able to pay that down eventually when I need to, account for that technical debt. And, and I think it's, it, it, kind of romanticizes the idea of tech debt, making it into this, this thing that I opted into. And, as, as you may have heard me mention, one or two times in the past, I work on a legacy system and that legacy system is littered with tech debt. And as I'm been maintaining it and I'm looking at this code and I'm looking at code that I wrote from years ago, none of it smacks of calculated decisions.

[00:25:15] **Ben:** It's all like, Oh, I just didn't know how to write good code. And like that was literally the best code that I could write at the time. And, that's not romantic. Like, it's not like I'm, I'm weighing pros and cons and, I don't know if that's, that's just like a unique experience or if a lot of people are making real calculated decisions around tech debt.

[00:25:36] **Ben:** but I know that I'm not, like almost the entirety of my tech debt is, is incidental shenanigans that I didn't know how to do anything about

[00:25:45] **Adam:** So, first off, I gotta say, I think you're putting entirely too much faith in people that take out loans,

[00:25:52] **Adam:** in, in, in, like financial loans. I mean, you were alive in 2008. You saw what happened there.

[00:25:58] **Adam:** not, not that the people are entirely to blame for that, but they bear some responsibility.

[00:26:03] **Tim:** Yeah, I, I mean, I, I totally agree with you, Ben, because it's like, I've never said, You know what? I really should be using this library here, you know, rather than, you know, just doing it kinda the way I know to do it. But we'll eventually get around to that. most of the time it's just like, I just didn't know any better.

[00:26:20] **Tim:** I was ignorant of the options that I had at the time. And when I go back and look at the stuff I'm fixing for technical debt, it's not because I had a better option. I knew about a better option. It's just like I was completely clueless at the time that, and now that it's smarter me today, me knows that, you know what, that was really a bad decision at the time.

[00:26:39] **Tim:** But I was using the tools I knew about. And now I know better. And now I'm fixing what I'm now calling technical debt at the time, which I thought was really cool.

[00:26:50] **Carol:** Yeah.

[00:26:51] **Tim:** And that's the worst feeling in the world. I I, I think you're right. It is romanticizing, it's, it's, it's technical debt is what you tell the non-technical people, the reasons why you have to go rework the code you did before.

[00:27:04] **Tim:** It's a great

[00:27:04] **Tim:** story, right? Because you're talking to, typically you're talking to sea level people who are dealing with financials and everything. You're like, you know how you take a loan, right? So that you can do, I mean, you, you're taking on debt and that's bad, but it's good because it helps you grow.

[00:27:18] **Tim:** And so at the time it was bad because, but it was good because it helped us grow the software, but now we have to go pay it back. That's a great story. It is inherently BS

[00:27:30] **Ben:** Yeah, it sounds better than I up.

[00:27:32] **Tim:** Uh,exactly. I, I, you know, I was a dummy back then 2015. Tim was a complete moron when it came to like, testing and, you know, mocking and all of that stuff. But, you know, 2022, Tim's much smarter now, and he knows he needs release to do that stuff so he can make it better. and so, you know, we have to pay this back.

[00:27:52] **Tim:** So it's, it's, it makes it sound like you made a contract and now you have to fulfill a promise. But in the fact you, you're like, No, none of that really happened. It's a great story.

[00:28:01] **Carol:** But I feel like I just had the opposite of this happen. Like I'm working in this part of the code where it was pushed out pretty quick and it was not thought through to the full extent by the product side of the world. So they were like, It's always, always gonna be a one to one thing. I don't know why you're trying to make it so much more complex than it needs to be.

[00:28:23] **Carol:** Just make it always assume it's gonna be one to one. Don't quote around thinking that there's ever gonna be one to two or two back to two. Like it's always gonna be one to one. Code it, put it out and we're just gonna call this, you know, a five point story. This was years ago. What falls in my plate? You know, a couple months back.

[00:28:42] **Carol:** Oh, that one to one match now needs to match on three different things or all three things. And I'm like, No, you literally have had them code this system to say it's always one to one. Do you know how many, Like this isn't just one little line of code I can change. This is everywhere. Assumes this is a one to one match.

[00:29:03] **Carol:** Like you can't add another record in this table because we already have identifiers like we are locked. Like I have to go change database, I have to change the code. That's not a naive engineer that is being pushed to get something out and being told the next option is not an option. Even though they brought it back and said, Well what about this?

[00:29:26] **Carol:** And they were told, No, don't spend extra time doing it. Get it out like it is, and this is what it'll always.

[00:29:33] **Tim:** So I'll ask you this. Is that technical debt or is that not doing premature optimization? Because how long did you say it took to get to this point?

[00:29:41] **Carol:** Oh, a couple years. Yeah.

[00:29:43] **Tim:** Yeah.

[00:29:45] **Ben:** I, it's a really interesting question because we often. Technical debt in terms of people taking shortcuts, but talking about the, the contention between the engineering side of the house and the product side of the house, I think Carol brings up a fascinating point that I think to some degree technical debt is brought on explicitly when you don't take shortcuts.

[00:30:07] **Ben:** I, I know, you know, design, because they don't have the, the deep engineering knowledge. They'll put something in their design like, Oh, can we just slap on the date that somebody last checked your credit report? And you know, it's like one line of text and then the engineering team goes off and they're working on it for weeks and they're trying to come up with systems.

[00:30:25] **Ben:** It's like checking all these independent credit report systems and then materializing data and local databases. And the product team is like, Yo, why is this taking so long? They're like, Oh, this is so complicated to, to aggregate this data and make sure it's not too stale. And then the product team could be like, Oh, well then let's just not do that.

[00:30:43] **Carol:** We don't want

[00:30:43] **Ben:** Oh. Yeah, like you tell me, if I had just pushed back and taken out that one little piece of text, we would've knocked weeks off of the timeline. And I, and I think there is a certain amount of technical debt that we take on as engineers in terms of complexity, because we don't push back against product people who don't maybe know what they're talking about in the first place. And I

[00:31:06] **Adam:** That's a that

[00:31:06] **Ben:** way. Like,

[00:31:07] **Carol:** sure.

[00:31:08] **Adam:** right? I think again, like everything else, it comes back to communication. We have to train ourselves to, in those product design meetings or, you know, specification meetings, whatever's going on, when there's gonna be something that's gonna require significant effort, even if it's discovered after the fact, to, to say, Okay, well this is not a quick, easy thing.

[00:31:30] **Adam:** How important is it to you? Right? Is it worth investing a month of three people's time to write this feature? If not, then, then we'll pull it out. But you gotta have those discussions

[00:31:40] **Ben:** I, remember years and years ago, and this, this is like before Border Radius existed in CSS and before people really knew how to position things like Absolutely. And relatively and stuff. And, we, we would oftentimes get designs from the designer, which was, here's the, here's what the homepage looks like as a psd, that's a Photoshop file for people who are young.

[00:32:03] **Ben:** and then here's the detail page and like, that's it. That's all you'd get. You get two designs and everything would have to be some extrapolation of that. And I remember talking to the team I was on at one point and, and pleading with them more or less. I'm like, if the designer put a button in a crazy place, And now you're gonna have to cut that button into like multiple parts and have this crazy layout in order to get this button overlapping with something else.

[00:32:27] **Ben:** I was like, just don't do it. Just bump the button down a few pixels and put it, you know, wherever it's easiest to go. Yeah. I'm like, you're not gonna want to have to maintain that. I mean, now it's trivial. Most of this stuff is trivial with css, but back in the day it was not

[00:32:42] **Tim:** Yep. That day was a Wednesday. If you don't know, just, just if you're wondering.

[00:32:49] **Adam:** So I, I, when this originally came up in Discord, I had thrown out some comments, about kind of how, now with the benefit of hindsight, I kind of want to, modify them a little bit. So, you know, I think that there are multiple categories of naive technical debt, right? So there's, I'm just coding the best I know how, I don't know that potentially there's a better solution.

[00:33:09] **Adam:** So I just do the best that I can. And then 2, 3, 10 years later, we discover there's a better way to, to do it. So we go back and we fix it, or we scold ourselves for whatever and, and wait another 10 years and just get progressively more frustrated and upset. but so that's the, the completely naive one, but then also, right, like there's gotta be times when it's obvious to you that you are not an expert at whatever it is that you need to be working on, and you're making the choice not to seek outside help, right?

[00:33:44] **Adam:** And so I. I would say 90% of my job and prob, I would guess 90% of the three of your jobs is on the job training, right? Like we're just given a task and it's like, here, go figure this out. Go do it. And that's fine, as long as everybody is fully aware of, you know, what that means is that you're letting a newbie do this even though it's a newbie with 20 years experience

[00:34:09] **Tim:** Right, but newbie at the new thing.

[00:34:12] **Adam:** right?

[00:34:12] **Adam:** Yeah, yeah. I've never done, you know, web sockets or whatever it's gonna be, before, so you're gonna get, an implementation that's not as good as the guy who's been doing it for 10 years could do.

[00:34:22] **Ben:** That reminds me of one of my favorite presentation slides of all time, and I can't even remember who it is. I feel embarrassed about that, but it was, it was about microservices versus monolith. And the presentation slide is something like, if you couldn't figure out how to do a monolith, what made you think you could figure out how to do a micro surface

[00:34:37] **Carol:** I love that. I love it.

## [00:34:41] Technical Debt vs Calculated Decision

[00:34:41] **Tim:** Yeah. So I'm gonna give two examples. One which I think is not technical debt and one that I think that is, and hopefully I can hold those two ideas in my head while I talk. so one that I think isn't so I'll I'll admit, I hate, I hate, I'm gonna puke in my mouth when I say this, but I do love ColdFusion because you

[00:35:01] **Tim:** can. you can, you can prototype something very quickly. You can get something, you can do something really fast and easy and get it up and running. And so many times there's an idea, there's a product and all you really wanna do is just get a proof of concept out there. Right. And you might even sell it, right?

[00:35:20] **Tim:** But it's like, from my experience, sorry, Ben, it's not always a hundred percent the, just because you got it working doesn't necessarily mean it is the best version of itself as a product. So many times, we'll, we'll prototype model something, you know, we'll demo something, it's demo ready, we can like start selling it right, really, really fast.

[00:35:42] **Tim:** But, you know, once we get the order to to do it, we're gonna write it in something else that's gonna be more scalable. And so I, I don't think that's technical debt, right? Because we're, we're making a decision. This is. Not the best technology right now for the overall health of the product, but this is the right technology to get something off the ground and to show something that's working.

[00:36:08] **Tim:** so I don't think that's technical debt,

[00:36:10] **Adam:** I disagree. I think proof of concept is, is a valid technical debt use case, right? You're, you're proving the idea. It's a, you're prototyping it rapidly to, to help somebody who can't understand the way that you can transform the thoughts into words. Like give them something that they can see and interact with so that they go, Okay, yes, this is worth investing the money in.

[00:36:32] **Adam:** And then you do it with the tools that are gonna make it. maintainable and scalable and webscale and whatever else.

[00:36:38] **Tim:** Yeah. But doing it right takes a lot longer, right?

[00:36:41] **Tim:** So sometimes you just wanna get ahead of the market and say, Look, we have a

[00:36:46] **Adam:** exactly.

[00:36:47] **Ben:** thing. We can, we can demo the thing and we all know how demos are, right? Demos are all smoke and mirrors. But I, I think what Adam's saying is this is the calculated decision version of technical debt.

[00:36:58] **Adam:** Yeah. You, you're spending two weeks building something with the rapid prototyping language that you fully intend to throw away and start from scratch, with the permanent platform, once it, once it, the concept is proven and the okay to spend the money on the long term project is given. That, to me, that sounds like textbook technical debt.

[00:37:20] **Tim:** Okay. Then you said you disagreed. That's exactly what I was saying.

[00:37:24] **Adam:** You were saying it's not technical debt.

[00:37:25] **Tim:** No, it is. Okay.

[00:37:28] **Adam:** the tape.

[00:37:29] **Tim:** Yeah. Throw the red flag.

[00:37:32] **Adam:** roll two 20.

[00:37:33] **Carol:** see, I, I think it's not, Yeah, I think it's not technical debt because it's no longer gonna exist. Right. You built that into your budget. You know the cost. It's gone now. It's gone. It's not

[00:37:43] **Ben:** on.

[00:37:43] **Carol:** da,

[00:37:44] **Carol:** it's

[00:37:44] **Tim:** I'm, but I'm saying that there, what I'm saying is, is there was a certain amount of effort and expense spent, Right. So if you spend money that you're not gonna get anything forward, that's debt.

[00:37:56] **Carol:** Oh, okay, fine. That part is true.

[00:37:59] **Carol:** Yes.

[00:37:59] **Tim:** how I was thinking.

[00:38:01] **Carol:** I considered the money already gone. Right? This was, This was like fluff money we had to spend. It's not like we took out a loan for it. It was money we had in the bank that we spent. So we are not in debt for it. We're using what we've already profited with. Get rid of it.

[00:38:17] **Carol:** It's

[00:38:18] **Carol:** gone. Did it?

[00:38:19] **Tim:** We haven't you know, you're not gonna sell it really until it's

[00:38:22] **Carol:** Yeah. This assumes that you're later in the game then. Okay.

[00:38:26] **Tim:** so it's technical investment. It's

[00:38:28] **Tim:** investment.

[00:38:29] **Carol:** There you go.

[00:38:30] **Adam:** an advance on your allowance for mom

[00:38:32] **Tim:** There you go. Yeah. Yeah. And as, as I was afraid, I can't remember what the other thing I had in my head was. So,

[00:38:38] **Carol:** Oh, darn

[00:38:39] **Tim:** It'll come back later, I'm

[00:38:41] **Ben:** let me, let me ask this then, because. When I think of a calculated decision there, there's sort of two types of calculated decision. I think there's the, we have a deadline to meet, and if we do quote unquote the best choices, we're not gonna make that deadline. So in order to make that deadline, we're gonna cut some corners, we're gonna do some suboptimal solutions because we know we're gonna get it done, but then we're gonna have to pay for that later because now it's a system that we're maintaining.

[00:39:09] **Ben:** To me that feels a little different philosophically than the proof of concept. We don't know if anyone's gonna want this, so let's build kind of the lowest barrier to entry, minimum viable product to see if anyone even wants it. And then if someone wants it, then we can maybe iterate and, and build it out.

[00:39:29] **Ben:** And, and I, I'm only saying that those are both, those are both examples of doing the suboptimal thing, but I think it's for different reasons.

[00:39:38] **Ben:** Sorry, go ahead Adam.

[00:39:39] **Adam:** I I completely agree with you,

[00:39:42] **Carol:** don't please stop hitting yourself.

[00:39:44] **Adam:** I, I completely agree with you until the moment that you, you tell the, the CTO or, or you know, whoever is holding the purse strings that, okay, that demo I just showed you can only be used to show you this and I have to throw it away and start from scratch. And so I need another, you know, three months for five people to build the thing.

[00:40:06] **Adam:** And he's like, But you just showed it to me working. Why, why can't I just go sell it? Right?

[00:40:11] **Tim:** That is a challenge. Yeah. Particularly you show the salespeople and they're like, Oh yeah, it works. No, dude, it doesn't. Yeah. So you totally have to be upfront with everyone involved, like the cto, the sales team, the marketing team. Look, this is a prototype that we're not telling the customers this is a prototype, but we, we cannot go to market with this right now.

[00:40:30] **Tim:** This is just to show that we can do it, that it's possible to help sell the product. But yeah, no, we're not selling this. We're not , we're not signing any contracts right now with this, cuz you know, it's not gonna, it's not gonna scale well.

[00:40:45] **Ben:** It's so interesting. You, you hear all these wacky stories about people in, in kind of startup world where they'll, they'll talk about how they never built a particular feature. I can't remember what it was. There was some guy who was building some sort of a site where he was selling a product or, or a set of products, and he was talking about how he didn't know how to get the refund feature to work and Stripe or whatever payment processor.

[00:41:09] **Ben:** Like they didn't really have a good API for it,

[00:41:12] **Ben:** so

[00:41:13] **Tim:** us.

[00:41:14] **Ben:** he just, he didn't build it. And if people needed a refund, they would submit a ticket and he would have to go and do it manually in the payment system.

[00:41:21] **Carol:** what?

[00:41:22] **Tim:** Wow.

[00:41:22] **Ben:** Yeah. And he was like, he's like, You know what? I ended up just not getting that many requests. I just never built the refund feature.

[00:41:28] **Ben:** And he's like, he's like, and it's just fine,

[00:41:30] **Adam:** Was by any chance was that the Christmas Guardy interview with, Joel Hooks on the Badass Courses podcast?

[00:41:39] **Ben:** I, I don't know. It may have been, it may have been

[00:41:42] **Adam:** I think I just listened to that like earlier today.

[00:41:45] **Ben:** This was from a while

[00:41:46] **Carol:** I was like, Dude, your brain

[00:41:49] **Tim:** Wow. got photo memory.

[00:41:52] **Ben:** so like, I don't know, I, you could look at that and say it's technical debt, things like that. But people are running, it seems like perfectly scalable applications, like sometimes you just don't realize how big or how little a piece of debt is gonna be in the moment. And then sometimes it's just not nearly as big as you might anticipate.

[00:42:12]

## [00:42:12] No Tests As Technical Debt

[00:42:12] **Tim:** So I'm gonna channel Channel my inner Adam Cameron, after we met in London, we're like BFFs now.

[00:42:19] **Tim:** And say to you, Ben, that not having tests is technical debt.

[00:42:24] **Ben:** You, I always, I had a, I had an lol at work earlier today cuz someone, So at work we do these things called DA and I, and I can't even remember what a DACI stands

[00:42:34] **Ben:** for. It's like daci, it's a D D A C. It's a decision

[00:42:39] **Carol:** Yeah, it's a tree. So you basically, how you come up with a, an answer to a question,

[00:42:43] **Ben:** It's like we need to do this thing and here's options A, B, C, and D and here's the pros and cons and like the level of effort and the cost of doing all these things.

[00:42:52] **Ben:** And you figure out which one you're gonna do.

[00:42:54] **Carol:** it's kind of cool. Mm-hmm.

[00:42:57] **Ben:** it's interesting. so anyway, in the option, someone asked for my feedback, they're like, Hey, can you jump in and leave some feedback about option D? And it's talking about all the risks and then under all the mitigations, they're like, Oh, we'll mitigate the risk by having lots of unit tests and integration tests.

[00:43:12] **Ben:** And I was like,

[00:43:13] **Adam:** Uh, talking to the wrong

[00:43:17] **Adam:** guy.

[00:43:18] **Carol:** Yeah.

[00:43:19] **Tim:** Oh, Ben,

[00:43:20] **Ben:** Yeah, . But you know, I mean that's, so, but it is a fascinating question as well because as I've said before, which Adam Cameron refuses to agree with ever, which is that, I'm the o

[00:43:33] **Tim:** he ever.

[00:43:34] **Ben:** I'm the only one who's ever gonna touch this code. And, and it just doesn't feel like Tess are, are a value add. And I'm not saying Tess are never a value add, I'm saying in this context, it's, it's me and then it's the trash bin.

[00:43:46] **Ben:** Like there is no, there is no one afterwards. So to me it's not technical debt, but to all onlookers. Perhaps it is.

## [00:43:56] Back To Prototyping As Technical Debt

[00:43:56] **Tim:** So, how about you, Carol? What you gotta say about this?

[00:43:58] **Carol:** I just go back to, I feel like if you spend the two weeks developing it, then you guys could disagree and it's a prototype and you tell the ceo, This is just a prototype and we're gonna waste the money on it.

[00:44:10] **Carol:** It's not technical debt, but whatever.

[00:44:12] **Carol:** I'm not gonna fight you.

[00:44:14] **Tim:** I mean, I, I think it's just phrasing, right? I, it is. Like I said, I wasn't sure. I wasn't a hundred percent sure, so I, I think it's a thing you do that it costs you money, but it's money well spent.

[00:44:27] **Carol:** Yeah,

[00:44:28] **Adam:** I can be convinced.

[00:44:29] **Tim:** Whereas, you know, being dumb about the code is, you don't, you don't, you don't know you're spending money at

[00:44:34] **Carol:** Yeah. Agree. Completely agree.

[00:44:36] **Adam:** As we discussed earlier, the concept of technical debt is just a way to help us communicate with non-technical people, right? And so as long as we're all on the same page, it doesn't matter what we call it or

[00:44:47] **Adam:** you know, Yeah.

[00:44:50] **Carol:** Yeah. Like I went to product with this code I was writing and I was like, literally, you can't push anymore changes into this code. That's it is, it is beyond its capability of taking more changes. Like I can't force this to do anything else. Like it's gonna need work across the board, like everywhere to make this happen.

[00:45:08] **Carol:** Unless you make the decision on do you really want this multiple matching or do you not, because. I'm gonna have to rewrite things to fix what was done before or to make changes to it. And you just need to know there's gonna be time associated with it. Plus every test that's been written for this has to be rewritten.

[00:45:24] **Carol:** Plus our automation, like in our automated, like in suite, in N E N D suite testing has to be done as well. So like it's multiple tests across the board. Several teams need to work on this and you know, it's gonna cost money to clean this up and fix it.

[00:45:42] **Tim:** Yeah, I, I think what you're talking about there is really kind of, A classic technical debt because you had an architectural decision that was made based off the assumptions of what was possible and then what was impossible became possible . And now it's like, okay, so we built to this spec and now this spec's no longer valid.

[00:46:07] **Tim:** We really have to rebuild everything. I mean, I think that's very much technical debt, but people assumed at the time that it was impossible, so it was not foreseeable. So it's, again, it's, it's not one of those things where Ben said earlier where it's the, were taking out a loan because we know this.

[00:46:26] **Tim:** We can't owe, we can't afford it. That whole story breaks down there. It's like we didn't know we needed a loan at the time. We spent the money we had and didn't realize we didn't have a roof on the house. And they're like, Oh crap, we don't have a.

[00:46:41] **Carol:** or in this case you have a door, but the door is like on fire, so there's no other exit.

[00:46:46] **Tim:** right? Yeah,

[00:46:47] **Carol:** One way. Only buddy. Yeah.

[00:46:49] **Tim:** what are we gonna do? I guess we need to put the roof on or put the fire

[00:46:53] **Carol:** Yeah.

## [00:46:54] Prototyping Then Scrapping

[00:46:54] **Ben:** I've, I've never built anything as a prototype and then thrown that prototype away.

[00:46:59] **Ben:** I've, I've, I mean, I will maybe not use the prototype in its entirety. I might copy and paste a lot of it into like a fresh set of files, but I've, I don't think, I don't, I cannot recall building something and then completely scrapping it.

[00:47:17] **Carol:** Oh my goodness. Tim and I, when we worked together, we used to do these like yearly challenges for like team building where we would like come up with a product and figure out what that product would probably cost, and then we would like code out what it would be or just present some type of presentation on it.

[00:47:35] **Carol:** I love that so much because I got to come up with something that might help the system. nobody could like it don't really care. And actually one year they didn't like it, didn't care. It all got trashed after point being is I got to just create something with my team that was outside of any request that was made to us outside of what the customer wanted.

[00:47:54] **Carol:** We got to spend some hours doing it, mock it up, get it out there, do some code to it, and then we're like, All right, we're proud of this. Either way, you know, someone else could win, but it can go in the garbage now. Like, I love that feeling. I love knowing that I got it working. I got a good idea from it, but I also don't have to support the garbage that I put in to make it work when it, like, if it, if it doesn't become successful.

[00:48:16] **Carol:** Right. It's like a, a base like, Okay, I'm gonna cut my hair short now it's gonna grow back out.

[00:48:22] **Carol:** So

[00:48:23] **Tim:** I love it. Love it. Yeah, Ben, I've done it multiple times, so it's like six years ago I found sort of new technology in the FinTech, the financial space. Just built something really slapdash and quick, just kind of shows some customers like, yeah, we're interested in that. And, but then because of politics and like organizational changes didn't really take a, So it started as a ColdFusion kind of thing that I built and it was a sort of a prototype.

[00:48:49] **Tim:** I mean, I'm still working on it today and it's not because it's technical stuff. I'm not actually, I'm not even working on it. So it's, it's in.net right now. I'm, I have not touched one line of code in it, but I've been driving the project because it's all legal and dealing with banks and dealing with finance, credit card services and things like that.

[00:49:09] **Tim:** So I'm dealing with all the financial services and the, the legal aspects and the relationships and all that stuff while everyone else is building the better version. My version was crap. It would totally have fallen down, but it's like, it showed what could be done. And now we're building this. Right.

[00:49:28] **Tim:** And I'm dealing with all the contractual stuff to, to make sure this comes live. And we're so freaking close, so freaking close.

[00:49:37] **Carol:** But you were okay throwing it away, right? You're

[00:49:39] **Carol:** okay that? yeah.

[00:49:41] **Carol:** Oh

[00:49:41] **Tim:** I just, I just, I just wanted to show that this, this, you know, I want people to say we need that. We want that. Right? And so when customers say they're ready to put money up, then management's like, Yeah, okay, let's build this.

[00:49:52] **Carol:** I'm with you.

[00:49:53] **Tim:** And they knew it was a prototype.

[00:49:54] **Ben:** There is something I think very wonderful about flexing the muscle of throwing things away. Cause too often, We as, as a, I don't want broad stroke industry here, but I see at our company and at other companies, people suffering big time from the sun cost fallacy. You know, you're building something, you put, poured a bunch of money into it and the only path forward is to keep pouring money into it.

[00:50:19] **Ben:** practicing the art of throwing something away is super powerful,

[00:50:23] **Tim:** Like legacy pin

[00:50:26] **Ben:** like a legacy. You're missing the point. Tim

[00:50:29] **Adam:** Shots fired.

[00:50:34] **Tim:** sorry about

[00:50:36] **Ben:** about technical debt though, and, and calculated decisions, and I did say that most of my technical debt is just ignorance and naivety and lack of experience. The, when I think back to technical debt that. Intentionally took on mostly because doing it at the better way was technically like an order of magnitude more complicated, was doing, CPU intensive tasks on the same machine that I do everything else.

[00:51:04] **Ben:** And unfortunately that is debt that I am continuing to pay interest on like 10 years later. And, that's something that I really wish I had not taken, I wish I had not taken, I wish we just solved that right the first time. Things like image processing, pdf generation,

[00:51:23] **Ben:** things that the, that just like suck memory and CPU that really, really, really should have been architected into its own little service.

[00:51:33] **Adam:** The types of things that are like perfect use cases for microservice.

[00:51:37] **Ben:** Yeah. Yeah, a hundred percent. Like the rest of it, it's just, Oh, you look at code and you're just, you face palm and you're like, Oh, this just wasn't put together well. But like you can work with it. It's just not fun. But you know, someone generates a 30,000 by 30,000 pixel image and your machine, you know, comes to a standstill.

[00:52:00] **Ben:** Like

[00:52:00] **Ben:** it's hard to, It's hard. Yeah. It's hard to work around that.

[00:52:04] **Carol:** I actually got a text from an old co, like a coworker a few weeks back, and it had a, just a screenshot of code and it said Carol's debug, and it was a SQL statement, like a, an execute I had in there that explained like how you could debug this file. And she was like, You will forever live in our source, like our source, our source code, right?

[00:52:25] **Carol:** And I, I just immediately responded back. I'm like, Ha ha. I'm like, Yeah, not too often do I look back at my old code and, and, and, and like, Oh, let me be proud of myself here. And she was like, Yeah. She's like, I don't high five my old version very often. I'm like, No, no. We look at it and went, Man, I should have done that better.

[00:52:44] **Carol:** The first.

[00:52:46] **Tim:** Keep growing.

[00:52:47] **Carol:** Yeah.

## [00:52:47] YOLO, Yeeting and Sending It

[00:52:47] **Ben:** Yeah, absolutely. The other piece of technical debt, when I scraped the bottom of the barrel here, looking for things that I calculated a decision on was, doing a lot of on the fly SQL calculations. you know, like reading in hundreds of thousands of rows and

[00:53:03] **Ben:** arrogant.

[00:53:04] **Carol:** Yeah.

[00:53:04] **Ben:** Because you're like, I don't know if anyone's gonna use this.

[00:53:07] **Ben:** I'll just put some counts and some sums and like, there's no really great indexes on this table, but whatever. Like, just, you know, grip it and rip it. Let's do this. And,

[00:53:16] **Ben:** uh, yeah. So some of That stuff really, Yeah. Yeah. Yeah. There's, there's been some queries that have taken the database to a standstill.

[00:53:24] **Tim:** They don't age well. No.

[00:53:26] **Ben:** No.

[00:53:27] **Adam:** For some reason this week at work, I've found myself using the terms Yolo and ye

[00:53:32] **Carol:** You

[00:53:33] **Adam:** frequently.

[00:53:35] **Ben:** I don't know the second one. What was it? Ye

[00:53:37] **Tim:** ye

[00:53:38] **Tim:** to throw something.

[00:53:40] **Adam:** Why? E e t? Ye

[00:53:43] **Adam:** it just like launch. It's just chuck

[00:53:44] **Carol:** Mm-hmm.

[00:53:45] **Tim:** Don't ye. It's the fetus.

[00:53:49] **Adam:** It's just, when you said grip it and rip it, that's probably the, the most analogous

[00:53:53] **Ben:** I like it.

[00:53:54] **Adam:** thing and I feel very old using the same, using, analogous and ye in the same sentence.

[00:54:00] **Tim:** Yep. Wow.

[00:54:03] **Ben:** Did anyone ever watch the Tosh Point? Oh, Daniel TA's, like clip

[00:54:06] **Adam:** I've seen it never religiously

[00:54:08] **Tim:** Seen it.

[00:54:08] **Ben:** There's one, there's one guy he interviewed. It was this guy. He was gonna do like a jump with a, on a snow, on a snowmobile. Yeah. And I forget, he's like trying to figure out whether or not he is gonna make it. And he looks at the camera and goes, Y'all silly.

[00:54:22] **Ben:** I'm still gonna send it. And it's just like he's become my, my go-to mental model for anything

[00:54:29] **Tim:** I, I'm gonna have to Google that.

[00:54:31] **Ben:** that's the best.

[00:54:32] **Adam:** All right. Well, I think that's gonna about wrap it up for this one. on tonight's after show, looks like we are going to be talking about, Carol telling inappropriate jokes at the wrong time, maybe

[00:54:43] **Carol:** yeah,

[00:54:44] **Carol:** yeah,

[00:54:45] **Adam:** and, uh, something that we talked about previously, a bunch. I think it, it's possible that this only came up on the after show.

[00:54:52] **Adam:** It's been a while, since I talked about doing taffi training stuff.

[00:54:55] **Adam:** I might have mentioned it in the past. I just have some, some new sort of rekindled thoughts and I figured the after show would be a good place to do that. So we will shortly be going to record our after show and, that is one of the benefits that we give to our patron.

## [00:55:10] Patreon

[00:55:10] **Adam:** So this is the part where I tell you that this episode of Working Code is brought to you by Ibuprofen. The only thing keeping me upright right now, and listeners like you, if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:55:27] **Adam:** Our patrons cover our recording and editing costs, and we couldn't do this every week without them. So thank you all very much. Of course. Special thanks. Go to our top patrons, Monte, Sean, and Giancarlo. if I'm mispronouncing that, please email me or hit us up in Discord or something and let me know.

[00:55:43] **Adam:** I do say on Patreon that , you're, you're signing up to have your name butchered, but, you know, I'll put in a good faith effort if you tell me how I'm supposed to pronounce it. so if you'd like to help us out, you can go to patreon.com/working code.

## [00:55:56] Thanks For Listening

[00:55:56] **Adam:** let's see. So this episode is gonna come out on November 2nd, which means it comes out after we will have recorded episode 100, which makes perfect sense, right?

[00:56:04] **Adam:** This is, we're recording episode 99. We're gonna record episode 100 before episode 99 goes public. so, let's go back to our regularly scheduled homework. and for this week I want to ask you to leave us a review. I went and checked in on our reviews. We have, Apple makes it really difficult to see your reviews from other markets.

[00:56:23] **Adam:** I haven't had the opportunity yet to go look up other ones, but I saw that we're up to 22 ratings in the USA market

[00:56:29] **Adam:** and all of them are five stars. Thank you all so much

[00:56:33] **Adam:** for all of them and a lot of nice comments in there. So thank you very much. so yes, go to workingcode.dev/review and you can leave us a review in your local. you can send us your topics or questions @WorkingCodePod on Twitter or Instagram. You can join our Discord by going to workingcode.dev/discord. Email us text or voice memos to WorkingCodePod@gmail.com. That's gonna do it for us this week. We'll catch you next week. And until then,

[00:56:56] **Tim:** Hey, remember, your heart matters, but what matters more is your spicy hot tongues. But only if you watch us burn our faces off next week. Episode where I our faces off with insanely hot, hot sauce.

[00:57:10] **Ben:** I'm, I'm gonna

[00:57:10] **Ben:** make it past round one. That's my promise.

[00:57:14] **Adam:** You gotta have a goal. I, I do want to point out here at the very end, We are, episode 100 is gonna be in the normal podcast feed, but it's gonna be a very visual thing. We're gonna record the video, we're gonna get that out, and, and we will, I guess the YouTube link will be included in the show notes if, if you don't have any other way to get it.

[00:57:31] **Adam:** But, you know, it'll be in our podcast Discord and stuff, and on the website too. So look for it there. And,

[00:57:37] **Tim:** us sweat. Watch us burp. Watch us hiccup. Rub. Eyes burn. It's gonna, it's gonna be brutal guys.

[00:57:44] **Adam:** wish us luck,

[00:57:46] **Tim:** It's gonna be brutal

[00:57:47] **Adam:** All right. Thanks for listening.

## [00:58:08] Bloopers

[00:58:08] **Carol:** but in my experience, most of my technical debt seems from incompetent, Naive. Naive, right. Naivete. Why do you gotta use words in your things that I can't read? Okay. Naate.

[00:58:22] **Ben:** I'm.

[00:58:23] **Tim:** Back up,

[00:58:24] **Carol:** Hold

[00:58:24] **Carol:** on.

[00:58:25] **Tim:** up,

[00:58:26] **Carol:** Okay. Incompetent. Yeah.

[00:58:32] **Adam:** I mean, if we're gonna try and fix it, it's incompetence,

[00:58:34] **Carol:** incompetence. Thank you. Okay. I'm gonna give up. Tim, you,
