---
title: "257: We Solved Everything"
description: "In this episode we attempt to solve all the worlds problems."
date: 2026-04-30
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/9b903b35-0c1a-4a10-9f04-e8472326fc51"></script>
<div class="redcirclePlayer-9b903b35-0c1a-4a10-9f04-e8472326fc51"></div>

"We have solved all of the world's problems." Observability past the point where more logs stop helping, continuous deployment when the customer is the federal government and the change-management board is a real room with real people in it, JSON's loose schema as a load-bearing feature rather than a quirk to apologise for, and the awkward question of who actually owns the code you wrote on a work-issued machine.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Thursday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/257-we-solved-everything.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Cold Open

[00:00:00] **Tim:** Jason Dean had a quote once at a conference that stuck with me for years. He said, XML is like violence. The only answer for it is more violence.

## [00:00:29] Intro

[00:00:29] **Adam:** Okay, here we go. It is show number 257, and on today's show, we have solved all of the world's problems, and we're ready to succinctly put the information out to you. So we've got four topics we're gonna cover today instead of just one. We're gonna talk about observability. We're gonna talk about JSON and robustness.

[00:00:44] We're gonna talk about separation of work and play, and we're gonna solve all of your continuous deployment problems.

[00:00:49] So

[00:00:49] get ready.

[00:00:51] **Carol:** Grab a

[00:00:51] **Adam:** And this is

[00:00:52] gonna be a short one too.

[00:00:53] **Carol:** Yeah,

[00:00:54] **Tim:** 30 minutes tops.

[00:00:55] **Adam:** anyway. but first, as usual, let's start with our triumphs and failures. Tim, I'm coming to you first. What is going on, my

## [00:01:00] Tim's Triumph

[00:01:00] **Adam:** friend?

[00:01:01] **Tim:** so I'm going for a triumph. So today I added on an MCP interface in front of my,

[00:01:09] **Adam:** Dammit. What are we, like nine words into this podcast?

[00:01:11] **Tim:** Sorry, sorry.

[00:01:13] **Adam:** All right. The, the no AI rule starts after triumphs, and fails.

[00:01:16] **Tim:** The, the main body of the show.

[00:01:18] **Carol:** Whew. Thank goodness.

[00:01:19] **Tim:** Yeah. yeah. So I got a Taffy. you know, courtesy of, Adam Tuttle, our favorite, open sourced ColdFusion, rest, API provider framework provider.

[00:01:30] **Adam:** It's a shallow pond.

[00:01:32] **Tim:** yeah, very shallow pond, but I wanted to put an MCP interface in front of it. It's not really for public consumption, it's really more for me, just so I can just, since I'm always living in the Claude terminal,

[00:01:44] don't want to jump out and go to a Swagger page and whatever and, and do query. I just wanna query it directly. I used my, I call it argument, which is my little tool that pits two AIs against each other to come up with the best plan

[00:01:59] **Adam:** Yeah. This is what you talked about on the after show last week. Yeah.

[00:02:01] **Tim:** show last week, and I talked a little bit, I think a little bit about the main show for, a tiny bit. But yeah, basically you basically put in two AI keys. I have one for Claude, one for, ChatGPT,

[00:02:11]

[00:02:12] keys in. It's a web interface. You give it a prompt and then it spits out a suggestion and then they go back and forth round after round, coming up with the best plan and asking me questions to challenge assumptions and things. after it took about 15, 20 minutes to do that sort of, argumentative, request between the two until I got to something, I'm like, okay, let's build that.

[00:02:33] I put that prompt into Claude and built it. It sipped and churned and spun and discombobulated for about 45 minutes. And when I was done, it was done so I could, go to my command line query, taffy.io about. This is a tool that I've basically have worked on for the past five, six years and asked English language commands and it came back with great answers.

[00:02:57] So pretty cool.

[00:02:59] **Adam:** Nice.

[00:03:00] **Ben:** Very cool.

[00:03:01] **Tim:** that's me. How about you,

## [00:03:02] Adam's Triumph

[00:03:02] **Tim:** Adam?

[00:03:03] **Adam:** I am also gonna go with a triumph, and mine is also related to Taffy. So small world, no. so I have, it's been a while since I've done any work on Taffy. It's just been like stable and good to go for years and years. and since we have, set aside the no AI, rule during triumphs and fails here, I, I used AI to do some stuff, some work that I've been wanting to do for years and years.

[00:03:25] 'cause it was finally like really easy to do. I totally modernized the code base.

[00:03:31] **Carol:** Ooh.

[00:03:32] **Adam:** I talked about this previously on the show. I, first, I had it fix all the tests so that they were. Accurate, right? Like, I knew the framework was good, but the test suite was a little flaky and had some holes in it and stuff.

[00:03:44] So like, okay, first things first, let's make the test suite good. And then once the test suite was good, I said, okay, you can't make any, any changes to the tests, but I want you to rewrite all this code in CFScript. It was all I, tag based CFML and officially and, and actually did support all the way back to Adobe ColdFusion eight, which was like when Jesus roamed the earth.

[00:04:05] and so it was time to, to modernize a bit. So I had to rewrite it in CFScript and made sure all the, the new tests were passing on, Lucee five, six, and seven actually. And then just kind of cleaning stuff up. Oh, andI like redid the dashboard. It's kind of like a fresh new design, inspired by a lot of the Tailwind designs I've done recently.

[00:04:25] But in, in addition to like redesigning it, I also ripped out jQuery, ripped out, bootstrap. Yeah, so like previously it was very lazy. It was like, let's just embed a, a version of jQuery and the bootstrap JavaScript and the bootstrap CSS to like give you this like easy to build cookie cutter UI because that's where I was at in my design abilities, you know, whatever.

[00:04:48] Eight years ago when, when I built that, probably even more than that. Geez. and, so yeah, I was like, let's, let's, if we're doing this full resale, like let's. Keep the same functionality but just rip all that stuff out and go vanilla JS, vanilla CSS to really lighten the load here. and so that's, that went really well.

[00:05:06] and I did all that and I did like a release candidate and then a second release candidate. I got all the way up to like six different release candidates. 'cause it fixed a couple of bugs. And after I think the first release candidate I started, we started using it in production at work. So it's, it's, you know, very good now.

[00:05:20] it's been in production with us for like over a month or two now. So that's easily a million dollars has passed through it, if not more.

[00:05:27] **Ben:** Very cool.

[00:05:28] **Adam:** It's a good thing. You, got access to Project Glasswing, to, test all that security flaws.

[00:05:32] I did not, but I did, after that Project Glasswing thing, happened, I was like, you know, this is a good opportunity too to like have it review for potential security stuff. And it did find a couple of very minor things. It was like, there's a potential, not a, not a leak or a, a bug in Taffy itself, but it was like the JSONP implementation allows for somebody to do something that, like to provide a JSONP endpoint that could then trigger XSS or whatever.

[00:06:01] So, fix that. And there's a couple other very minor things that have found, but,

[00:06:06] **Ben:** Can

[00:06:06] **Adam:** and that made me feel good.

[00:06:07] **Ben:** just for the, the younger listeners who have maybe never heard of J-S-O-N-P, this was the,

[00:06:14] I I, think this was maybe created by the jQuery team. I don't know if it existed before them, but just as a quick aside for everyone who's familiar working with JSON APIs, when you're making requests from the browser back to the server, we used to run into cross site, permissions like, cross origin resource sharing

[00:06:35] **Adam:** Mm-hmm.

[00:06:36] **Ben:** And the jQuery team, I'll attribute to them, maybe it wasn't them, they solved this by saying, okay, the browser can't make API calls to a different domain, but they can load JavaScript tags, you know, like script tags from any domain whatsoever. they essentially came up with a strategy where they will. a totally random method name. a script tag that calls your API endpoint, and then I think you have to wrap it in that random method name,

[00:07:07] **Adam:** Yeah.

[00:07:08] **Ben:** tag loads, it executes that random method and

[00:07:13] it was. The response from an API call

[00:07:15] **Adam:** So

[00:07:16] **Ben:** I

[00:07:16] **Adam:** yeah. It's brilliant. It was actually proposed by Bob Ippolito in 2005 and jQuery added it in jQuery 1.2 in September of 2007.

[00:07:25] So this is old school stuff, but

[00:07:27] **Carol:** It is.

[00:07:28] an engineer.

[00:07:30] **Ben:** Cray

[00:07:30] cray.

[00:07:32] **Adam:** That's, yeah, we're old. thanks Carol.

[00:07:37] anyway, so, yeah, V four is out. It took me, I think I, about a week and a half to two weeks after I published in the, CFML Slack, there's a Taffy channel. I said, okay, this upcoming Monday I'm gonna publish V four. And then about a week later, I was like, oh, crap, I never did that.

[00:07:53] **Carol:** Uh

[00:07:53] oh.

[00:07:53] **Adam:** I, I just published it.

[00:07:54] When I finally got around to it, I was like, okay, today's V four day, pushed it out there and then like the next day I got a pull request from somebody who wants to, add a couple of features and stuff. I'm like, uh, why didn't you get this in during the, the release candidate stuff? so now there's gonna be probably a 4.1 pretty soon.

[00:08:12] But, I did look up some interesting stats about this too. So, it, about a year ago I did release 3.7, which was the, the previous minor release, which doesn't sound that bad, but, if you go like by major versions with breaking changes, the last release with breaking changes was in 2014. So that's how stable it's been over a long time.

[00:08:32] So quite a long time ago.

[00:08:33] **Carol:** Mm-hmm.

[00:08:34] **Ben:** good.

[00:08:35] **Adam:** I'm old anyway, so that's what I got going on. How about you,

## [00:08:38] Ben's Triumph

[00:08:38] **Adam:** Ben?

[00:08:39] **Ben:** I am gonna go with a totally non-tech related triumph, which is that on Sunday I went to a movie theater

[00:08:47] and I

[00:08:47] **Adam:** A cinema.

[00:08:48] **Ben:** a a cinematic, an immersive cinematic experience. And, I watched the 35th anniversary screening of Silence of the Lambs. let me tell you what, that movie holds up. It is so good. I was just blown away. I, I, I was like, I was, it's one of those things where you plan to go do something and then the day of you're like, oh, I can't believe I decided to do that. I have no interest in doing it. But I had already agreed to see it with some other people and I was just so pleased that I went 'cause it is just such a fantastic movie.

[00:09:20] **Carol:** is a serial killer movie, right?

[00:09:22] **Ben:** Oh, Carol.

[00:09:23] **Carol:** Yeah. Is it?

[00:09:26] **Ben:** Yes, it is. Of course,

[00:09:27] **Carol:** Okay.

[00:09:28] **Ben:** your, your questioning hurts my heart.

[00:09:30] **Tim:** it's

[00:09:31] Jodie Foster Anthony Hopkins.

[00:09:34] **Ben:** Uh,

[00:09:35] **Carol:** who any of those people are, but I feel like there's a, well I,

[00:09:38] **Tim:** Yes.

[00:09:38] **Ben:** you ever hear anyone say anything to the, effect of it puts the lotion on the skin or else it gets the hose again, that's from this movie.

[00:09:46] **Carol:** shit, that sounds awful.

[00:09:47] **Ben:** Yeah.

[00:09:50] **Carol:** I hope no one ever says that to me.

[00:09:53] **Ben:** So this is part of a series of movies that gets screened from this company called Fathom Events. And they, they do this kind of stuff not all the time, but like once a month it seems like is the cadence of, of these re-release of, of anniversary movies. I've never really been good about going to them, but I wanna make this part of my, my repertoire.

[00:10:13] And I, and I know, I think in the upcoming months they're gonna be doing Ocean's 11. V for Vendetta. there's another Fifth Element that was, that was a classic for my high school years, I think was Fifth Element maybe, that was a good big explosions kind of a movie. So I, anyway, my, my success is I, I went out and I did some people stuff and saw a movie and, I want movies to be a bigger part of my life.

[00:10:40] **Carol:** It sounds like I should. Yeah, it, I feel like I should go watch all of them. 'cause I don't know, does Fifth Element have glasses of water

[00:10:47] **Ben:** This Fifth Element,

[00:10:48] **Carol:** the little girl drinks them

[00:10:50] **Adam:** No. You're thinking of

[00:10:52] **Carol:** everywhere. Okay. I don't

[00:10:53] **Adam:** a, that's a Mel Brooks or Mel. Mel Gibson movie. That's Signs. Yeah. Fifth Element is, go ahead

[00:11:00] **Ben:** Bruce Willis and, Milla Jovovich, where she's got the strappy, the white strappy suit. It was a, it was a big Halloween costume for a long time after that. And, multipass go see it. It's very good.

[00:11:15] **Carol:** I'm seeing, I should definitely add it to the list.

[00:11:17] **Tim:** There you

[00:11:17] **Ben:** If you have a good sound system. Years ago, maybe it was like Samsung. There was a TV commercial where they were talking about how great the sound on the TV is. And, and the guy's like, so let me ask you this. He's like, it's, he's talking to the guy trying to buy the tv. And the salesman at one point says, now I, the only important question is, do you have any movies where stuff blows up and they kind of look at each other and start giggling, and then it cuts to the Fifth Element as the emblematic movie of where stuff blows up and there's a lot of great sound. Anyway, that's my Triumph movies. Carol, what do you,

[00:11:48] **Carol:** peopled because that's a big deal these days. It's

[00:11:51] **Ben:** especially for me.

[00:11:52] **Carol:** yeah, I mean, it's hard for all of us. You know, we get like set in our, our schedule and our routine and it doesn't

[00:11:59] people to come into it. So proud of

[00:12:01] **Ben:** hun Hundo. P uh, but that's me. Carol, what do you

## [00:12:04] Carol's Triumph

[00:12:04] **Ben:** got going on?

[00:12:05] **Carol:** Oh man. So I'm gonna go with a giant triumph, and if I am reading this undisclosed document correctly, like we all had triumphs this week. Is that

[00:12:14] **Adam:** Indeed we did.

[00:12:15] **Ben:** Yes, we did.

[00:12:16] **Carol:** finally a winner. So I, I think I've talked about on the show, if I haven't, you know, like I'm the lead AI ambassador for OPM, so I get to like, wear this fancy hat where I get to do a lot of mentoring and a lot of teaching. Well, it also gave me the opportunity to go work with another team. It's a team of data scientists and economists. So they aren't software engineers at all. Like, not even slightly. So we got with them and talked about a problem they're trying to face and something they're trying to deliver and something they wanna develop, but they don't have a team of engineers to support it. so. I worked with a couple other engineers and somebody who does like our Azure stuff and we use just a template that we have that we've spin up for other applications when we wanna create something. It's just a Blazor and .NET app. it's easy to use, easy to implement, you know, the IaC is easy to understand if you know anything about, like infrastructure as code, like you can just kind of spin up what you wanna do. we worked with them for two weeks prior to the actual meeting on site and kind of gave them an understanding of what we think we could help with, how we could deliver this with them. Um, showed up with pretty much just a template in place. And inside of the first working day, going into the second working day, every one of the data scientists and economists were able to run the project locally.

[00:13:35] They were able to test their code. They were able to use Codex to actually generate features. by the end of it, we had one of the data scientists, he was actually able to implement session storage and caching and an understanding of states so that you could return to a conversation and get back to where you were.

[00:13:55] so that was just like to be able to mentor and teach. I didn't have to teach someone how to write code. I just had to teach them the. To use a tool that they had never used before. And by, my team setting up the foundation for them to be able to implement on top of, we really like gave them the nice like starting point.

[00:14:14] And then the teaching onsite, it went from us expecting to write a whole bunch of code for them and with them to after day one we were hands off the keyboard. We weren't doing anything. We were just mentoring shoulder surfing, going, how can we help ask us a question. And it

[00:14:29] **Adam:** Right.

[00:14:30] **Carol:** how does Git work?

[00:14:32] And we're like, oh, let me screen share. I'll show you Git, I'll show you GitHub Actions. Let me teach you what you're doing.

[00:14:38] **Adam:** Nice. So they were kind of, you're like doing guided vibe coding

[00:14:41] **Carol:** Yeah. Pretty much just teaching them how to do it. 'cause again, they're not engineers, they're

[00:14:47] They're

[00:14:48] **Ben:** and where was it? Was it running locally or This was running in like Azure or something?

[00:14:52] **Carol:** Nope. It was running locally. We got everything running locally for them.

[00:14:56] **Ben:** Yeah. That's awesome.

[00:14:58] **Carol:** So

[00:14:58] **Ben:** But I'm also feeling like a little PTSD from bajillion years ago there, there was a conference out in Indiana, Bloomington, Indiana, I think it was at a university. And it was one of the CF conferences, I was helping someone do like a hands-on workshop for one of the days. It's like

[00:15:19] **Adam:** So you're like a lab assistant?

[00:15:21] **Ben:** yeah, and you

[00:15:22] first five hours

[00:15:24] because no one's installs are working. Half the people brought laptops that were totally underpowered to do any kind of installation at all. It's like other people had work laptops that they, like, they didn't even have administrative permissions to install new things, and you're like, oh god.

[00:15:40] **Carol:** it. I I totally remember being at ones like that where we pass around a thumb drive and just stick it in our laptop without any thought. I'm like, I'll take those files. Thank you. Next,

[00:15:50] files. Thank you. Next.

[00:15:52] Now I'd be like, you're not putting that in there. No, no, no. But yeah, it was, it was just so rewarding.

[00:16:00] I came back from the trip and I told Steve, I was like, this is the most rewarding work trip I've been on in ages. Like, I don't know the last time I came back from doing actual work and being exhausted from everything I was doing to say I would do that again next week if I had the opportunity. So

[00:16:20] **Ben:** That's awesome.

[00:16:21] **Carol:** yeah.

[00:16:21] **Ben:** What a great feeling.

[00:16:22] **Tim:** to vibe

[00:16:22] **Carol:** Mm-hmm.

[00:16:24] **Adam:** That's pretty great. Okay, so now with preamble outta the way, let's, uh, solve all the world's problems.

[00:16:30] **Tim:** you

## [00:16:30] Observability vs. Logging

[00:16:30] **Tim:** go.

[00:16:31] Tim, you spoke first, so you're gonna go first. Okay. yeah, so observability versus logging.

[00:16:39] So the past couple weeks on lots of different, APIs that I have built over the years and I'm doing all these logs and I never get any benefit out of it. And then when people are like, Hey, this thing happened on, you know, 4 25 at around 2:00 PM do you have any

[00:16:57] And I'd be like, nah, it's probably something you did

[00:17:01] **Adam:** Turn it off and back on again.

[00:17:02] **Carol:** It's always the user.

[00:17:03] **Tim:** yeah. Obviously it's your system, not My

[00:17:05] **Carol:** Mm-hmm.

[00:17:07] **Tim:** um, then I realized, yeah, what am I, what's the point of having all these logs if I don't have a really good way to them and look at them? And what makes it even more difficult is that I, we run on a load balancer. and so I have logs in two different places. I'm thinking, well, this is one particular transaction they're talking about that happened a certain time. I'm gonna have to log into multiple places to figure out actually where it's logged. That's such a pain in the butt.

[00:17:33] **Adam:** Mm-hmm.

[00:17:35] **Tim:** So, built recently, using Grafana, which is kinda like a, a graph, I, I never know how to say that.

[00:17:43] Word graph. SQL graph. What's, what's

[00:17:46] **Carol:** GraphQL. Graph.

[00:17:48] GraphQL. Yeah.

[00:17:49] **Tim:** thank you.

[00:17:50] **Carol:** Okay.

[00:17:51] **Tim:** which is sort of like an aggregator, all, all free tools, Loki, Alloy. And so basically I have one machine, but I have the load balance system. I have one machine that's sort of like the, the main person handles everything.

[00:18:03] I have a web interface all the other machines will feed their log. So that

[00:18:08] and the Grafana will build, like, help me basically. I can query the logs or have dashboards. And that's probably the most beneficial thing is being able to have dashboards where I can see like, these transaction came over this time, here were some errors, things like that. So it can be more, Observable. That's, it's kind of also the same reason I did the, in addition to this, I also added the MCP server in front because it's not necessarily, it's more observable, but it's a whole lot more queryable.

[00:18:39] I can actually query, the API, which is also talking to Loki, to, that's aggregating those logs. And so if someone says, you know, something happened at a certain time, do you know why? I can either go look at a dashboard and see, okay, here's where that thing happened, I can just, you know, in a. I'm not gonna say the A word. Um, Cheater. habit. It tell me, you know, you know where it is and narrow it down. So, yeah, I just, I, I think we spent a lot of time talking about logging. I don't think we talk about the importance of making it more observable

[00:19:18] So far I've not exposed this to anybody else.

[00:19:20] It's usually just for me. But I do want to make it a little bit more easy for, people to either like a web front end that's behind an intranet or something so that it's, you know, safe so that other people can go, rather than asking me questions, I, I can tell them to go here, look at the dashboard, figure it out, drill down, find the error the, the transaction or whatever that happened that they're searching for, so that they can help troubleshoot the problem themselves rather than relying on me.

[00:19:50] **Carol:** So we've talked about this a few times at work, and this isn't exactly at work now, but I will say there have been times where I go, I just wanna know if a service isn't running and they're like, oh, well for some reason the app didn't report that it wasn't running, and I just wanna go. If there was zero error logs written in the last hour, it's

[00:20:09] Like

[00:20:10] this app has problems. So you could just set a rule for that. If you got no error logs for an hour, you should go start investigating because

[00:20:18] it's

[00:20:19] **Adam:** Well, yeah, there's that. And there's also, if you don't know, like if it, if, if that's a normal thing for sometimes that you just don't get a report that it's down, then your system for downtime reporting is also broken and needs attention.

[00:20:33] **Tim:** Yeah.

[00:20:34] **Adam:** We use a, a tool called Dead Man's Snitch, which is built on the idea of a dead, dead man's switch, which is every app has to check in and say, I'm still here, I'm still alive, I'm still doing my job.

[00:20:44] And if it goes missing, then we get alarms.

[00:20:48] **Carol:** I remember back in the day when I worked with Tim, one of the SAs had his ringtone set for one of the like notifications he would get, and it was, I think it's Kesha, I don't know, artist. I'm so sorry. But it was the song like, it's like it's going down for real.

[00:21:03] **Adam:** Oh yeah.

[00:21:04] **Carol:** So we'd be at lunch and that'd start playing and we'd all just go silent.

[00:21:08] We're like, is it mine? Is it mine?

[00:21:11] Is it mine? Do I have to leave too?

[00:21:14] **Tim:** That is nice. Grafana does have it alerting, so it will alert you if, you know, the past, shamefully, you know, I know Adam has given talks on, that, email logging or alerting

[00:21:25] **Adam:** Oh, bug log.

[00:21:26] **Carol:** Mm-hmm.

[00:21:28] **Tim:** Where basically you send an email when there's a problem and I've had. That works sometimes, but sometimes when stuff really hits the fan, I, I basically broke my outlook one time because I had like

[00:21:38] **Carol:** Oh shoot.

[00:21:40] **Tim:** emails that happened over a weekend.

[00:21:42] **Adam:** Well, that, that's all that was the whole point of my talk is stop using email. yeah.

[00:21:46] **Tim:** what I'm saying. I

[00:21:47] be, be ashamed of me. So this kind of prevents that. It, it aggregates all those errors and if

[00:21:54] a certain threshold, it says, okay, let me actually do an alert

[00:21:57] **Carol:** Problems. Yeah,

[00:21:59] **Tim:** rather than, yeah. C clogging up my email server.

[00:22:03] **Ben:** thing that always drives me crazy as an individual developer is that there are some tools that are so good, but they're just too expensive for like funs. I'm gonna apply it to a side project just to see how it works,

[00:22:18] when we talk about logging and observability, I can't help but think of Datadog.

[00:22:22] **Carol:** Mm-hmm.

[00:22:23] **Tim:** Expensive.

[00:22:23] **Ben:** just freaking world class

[00:22:27] and the monitoring that they have. And then they just as, as we were sort of getting to the end of InVision, they added this concept of logging without limits, where you could treat Datadog as your log aggregator as well. And then they would cross tie all of your observability metrics at the same time.

[00:22:43] So you could just like click through from, oh, I saw this spike here. Let me click through to see all of the tracing and all of the logs that are associated with this timeframe with these, you know, ECS and EC2. And it's just, but it's expensive. And there was no free tier. There was no like funsies open source, weekend developer free tier.

[00:23:03] So

[00:23:04] I was like, but it's way too expensive to pay for.

[00:23:07] **Tim:** Yeah, I mean for my level it wasn't as big as that, but so everything I used was free

[00:23:13] **Ben:** yeah.

[00:23:14] **Tim:** so that kind of makes it a little bit easier to, to swallow. And I had to, I couldn't do it where it, 'cause you know, there's like cloud options that

[00:23:24] but it's like everything within our environment is, has to be whitelisted and I just didn't feel like dealing with that.

[00:23:33] So it's all basically just running local. There's the things on the machine, but really the only thing that can access it is my local machine

[00:23:41] can and, and, and, or if I give it to other developers, I can give it to them too. So that kind of the cost equation out of it when you use all open source stuff,

[00:23:51] **Adam:** Yeah.

[00:23:51] **Carol:** Yeah. One thing we deal with right now is the adaptive sampling that happens in App Insights. So every one of our logs are set up to be adaptive sampling, so I can't even find real logs. It's just like a subset of it, which gives you like a sampling of what's going on. And I'm like, well, that's not the one I got the help desk ticket for,

[00:24:09] doesn't help me. I'm like, why are we doing this? And then I get an email back and it's like, because of cost. And I'm like, well, we need to do a better job logging.

[00:24:19] **Adam:** Yeah. There's a, a related thing. I think I've talked about it on the show before, but it's, I think it is worth bringing up here. It's a thing I'm only experimenting with, so I can't necessarily vouch for it yet, but early results are positive and that is, what I'm calling wide events. so the idea is basically like every request logs one and only one line.

[00:24:40] Right minimum one, maximum one line. And that line is like, in my case, it's a JSON blob of like all the stuff that I wanted to log during that request, right? So you have to, there's work that you have to put in to be able to capture those log statements from all over and aggregated into one structured output.

[00:24:57] So for me, I, you know, I'm doing this in like Lambda on running Node.js, so it's, you know, like a global object sort of thing. aggregating log statements as things run. And then at the end it just spits out the log. And so far I'm pretty happy with it. I guess though, the one potential downside is like, there's a possibility of a crash before the log rights and then you get nothing.

[00:25:16] But, you know, that seems to be knock on wood, few and far between.

[00:25:23] Yeah, but I, I really like it and I mean, I guess it could be a little, I mean, it's certainly no worse than trying to parse out, when you're running processes in parallel, right? So if I have a list of like a, a queue of things I wanna process, and I'm processing them all in parallel, and each item being processed is spitting out multiple log statements, then you're gonna get those interleaved, right?

[00:25:46] you know, if you have three threads running and each thread is handling a ten second process that it's doing and, and logging every step of the way, you're, you're gonna have to dig through those logs, which is gonna be difficult. And it, I, I don't think it's any better or worse with wide events.

[00:25:59] The, the nicest thing about it though, is just like you, when you, once you find the log statement, that's it, you have found it, and you have the entire history of whatever got logged for that request. I don't know, necess,

[00:26:12] I don't know exactly how that cross sections neatly with observability, but I do feel like it's applicable.

[00:26:17] **Ben:** well

[00:26:17] **Carol:** stuff better. have to go to App Insights and I have to go to a database and then I also have to go to a server because we have an app that actually writes to the hard drive. So that's fun.

[00:26:30] **Ben:** People used to talk about the ELK stack all the time.

[00:26:33] **Adam:** Yeah,

[00:26:34] **Tim:**

[00:26:34] **Ben:** Something in Kibana Logstash,

[00:26:37] but

[00:26:38] **Tim:** Okay.

[00:26:39] **Ben:** it was, was essentially a, a logging and observability open source platform, but I never hear anybody talk about it anymore. I wonder if it's just been taken over by other things or platform as a

[00:26:52] **Adam:** or maybe it's table stakes and we're all behind.

[00:26:54] **Ben:** Yeah, it could be.

[00:26:57] **Tim:** Anyway, so that's, that's me. I'm just trying to improve the observability of, of the logs that I've been keeping for years and never actually look at. So what, what you guys got to solve the world's problems. I don't think I pulled it off, but if you, if more observable,

## [00:27:10] Continuous Deployment in Government

[00:27:10] **Tim:** then maybe you can

[00:27:13] **Carol:** I can go. Yeah. I don't, I definitely don't have a solve. So I think Adam definitely gave this the wrong topic 'cause I just got anxiety

[00:27:21] **Adam:** I explained it wrong. Yeah, that's all right.

[00:27:24] **Carol:** for me, we, uh, we've been tasked with this new like, directive to try to get us closer to continuous deployment. And that sounds like an easy thing for most tech companies. However, we go through a lot of change management and we have to have a lot of documentation around like, what, like we, our software bill of materials, right? So we have to have everything included in the SBOM with what? Is being included for the packages. Everything has to be signed off on, and then we need to be able to lay out all the changes.

[00:27:56] And an easy rollback if something does go wrong, right? Like we don't want to impact the American people in any way. Like we wanna do the best job possible. for me, when I was told this, all I did was just start writing down every reason that we can't do this. Currently, I'm like, number, number one, every change has to go through an ECM board.

[00:28:15] I'm like, so how do I even merge to main if there's no ECM approval on it yet? How do I get tester's approval before I merge to main? Now I have to solve the where do you test the code? Because if main's being deployed all the time, I can't do a pull request on main. It has to go somewhere else. Or they have to have a way to test it. I feel like problems I would've solved just give and try and see what happens at other companies. I can't do that here. I'm so scared I'm gonna up something and it's gonna go wrong and I'm gonna end up like in prison, like something's gonna happen. You know? So it kind of scared me when I was like, when I heard that, that's one of our directives, it's like, okay, let's get to continuous deployment. Because right now, like, you know, we do introduce bugs. I mean, we have junior developers who still sometimes don't get it right. I don't get it right. I mean, I can screw stuff up just as easy as one of them. I just understand the testing side to be a little different and I know what's not covered in automated testing.

[00:29:12] So I know what to be a little more critical of when I make a change. So I think one of the things we're gonna do is, I've already talked about implementing Playwright across the board, but we're gonna do a lot more of that. So I can actually teach non-developers how to generate these tests using Playwright whenever they go through and do their testing.

[00:29:30] So they go, okay, this looks good. Now let's commit that in and let's get a test coverage and let's get test coverage in place for just what the system should be doing. Like, what happens when I click a button? Like what happens when I submit a form? Like some of those things. So it does give us more as surety that what we're de delivering is solid.

[00:29:48] But again, that's just another flaw right now that we do a lot of manual testing and we have a lot of people confirming it's good before it's released to the, to the people. Like to the

[00:29:59] **Adam:** Yeah. So maybe you said this and I missed it. You, you said that, you know, it sounds like continuous delivery is a, an agreed upon or directed from on high strategy that you're supposed to be getting towards.

[00:30:13] Did you say what the goal is that the strategy is trying to get you to, other than continuous deployment?

[00:30:19] Like, is it

[00:30:20] **Carol:** integration and continuous deployment. I, I think the big thing is we're trying to be more current. I don't know because I wasn't given that I kind of just got this information today.

[00:30:30] wanna be more current and one issue we have is when sprints take four weeks, well, by the time it gets out to Dev and now it's gonna sit for four weeks while they do testing in UAT, then it goes to a staging environment.

[00:30:42] You're 12 weeks out before it goes to prod. So if there is a issue, good luck getting a developer to remember what they did 12 weeks ago

[00:30:50] ago even. Right? Like, we've went down on my team to two weeks sprint, so now I'm only in a six week interval or four week, but still, that's a long time to remember what was I trying to do.

[00:31:00] **Adam:** I think this is a, a, a popular complaint against the whole agile methodology stuff like the, the sprint piece in particular, right? Like my company, I would say that we are kind of agile-ish. You know, we just, we're very customer focused and we listen and responsive and stuff, but we, we don't follow sprints.

[00:31:17] It's just like, it's wild west. We all have a thing we're working on and we work it until it's in production, and then we work the next thing, right? And

[00:31:26] we

[00:31:26] we, do a lot of our own testing, and then we try and hunt down a customer and drag 'em by their ear over to test it if necessary. and, and, yeah.

[00:31:34] And so like, I, I get it. not every organization has the freedom and the ability to do that, but also, like, I think you're describing the, the. Most obvious drawback of the whole sprint, timeline thing.

[00:31:48] **Tim:** So here's an ignorant question or an uneducated question.

[00:31:52] So does the fact in the Agile methodology, why can't you just, if you think a, if a ticket is done, you are gonna ticket, it's gone, you know? Why? Why can't you just go to production? Why do you have to wait for the end of the sprint?

[00:32:09] **Ben:** I, I think that's, yeah, I think that's the difference between big a agile and little A agile. I think the little a agile people would be like, of course you can deploy, because it's always

[00:32:19] over process.

[00:32:21] And then the agile industrial complex is like, no, there has to be rules and can teach them to you.

[00:32:27] **Adam:** Right. Because then we can't do scheduled postmortems and all that. Yeah.

[00:32:31] **Carol:** Well, I can tell you for me, the reason why I don't do that is because all of our code gets married together in that initial branch just going out to production. So only thing going in would be any hot fixes or WIPs that were found immediately. But if I were to try to release my code, I would have to do some manual like cherry picking and moving to another branch.

[00:32:50] Otherwise, everyone's work's going,

[00:32:52] **Adam:** Oh, so you like, you have a shared development branch.

[00:32:55] **Ben:** Well, but that's the whole, I mean, I, I can't speak for you obviously, but I think a value add of the CI/CD mentality is that only the thing that you did is the thing that's going out. So

[00:33:10] the, blast radius of any change is vastly reduced.

[00:33:14] **Adam:** So do you, you said you're sharing a development branch. Why is, what's there? Is there a,

[00:33:18] **Tim:** is there?

[00:33:19] **Adam:** an established reason why you don't have your own personal development branch and then maybe merge into a developer's integration branch for the current release train or whatever?

[00:33:28] **Carol:** Yeah, so we do our own development work, and then we do the pr. So we can test it locally,

[00:33:34] for it to be integrated, it has to go into main, which ties to our develop, and then we branch off for a test branch when we're ready to go. So everything goes in and the test goes out, and then from there there's releases that go out.

[00:33:46] It's a whole, very convoluted

[00:33:48] **Adam:** Is, may not your production branch.

[00:33:50] **Carol:** No, no. main is not our production branch, which also means what's in production at any point doesn't match main because developers could have merge things in and it no longer mattered. They never got it working. They never reverted it. So that's one of my like big sticky notes, is you have to keep the production branch as where we start from then,

[00:34:12] **Adam:** Interesting,

[00:34:13] **Carol:** have the missing code and we don't have code that never existed.

[00:34:17] **Adam:** right.

[00:34:17] **Tim:** so recently there's been a push within our company of like, the, the sprint done, like fin finishing everything, no rollover, no big things hanging over. and my team was like kind of pushing back on it and I'm like, I, I gave him a quote. I thought it was, um,Buffett who said it, and I think Warren Buffett was quoting this guy, but it was, a physicist who became like a business process guru, m Goldratt. And he said a quote that I heard years ago and it stuck with me. He says, tell me how you measure me. And I will tell you how I will behave. And if your measurement's illogical, do not complain if my behavior is illogical

[00:35:01] **Adam:** Yeah.

[00:35:02] **Tim:** because they gave us all these measurements. So like, here's how we're gonna measure you guys.

[00:35:05] I'm like, look, we can complain all day about the measurement is not fair here. Why it doesn't work here, what doesn't apply to us? I don't care about that anymore. Or stop complaining about that. If you want continuous development integration, you wanna finish the sprint within a two week, whatever, however long it is, I'm like, here's what we're gonna do. We're gonna make sure that you, when when you think you are done, done. You close the ticket.

[00:35:28] if someone isn't tested it, you're done because that's what they're measuring, how fast you

[00:35:34] done. And so we're moving the definition of done

[00:35:37] to fix their measurement of, of how they're measuring you.

[00:35:41] **Adam:** Yeah. This is like a, an implementation of Goodhart's law, basically. Right? Any measure that becomes a target ceases to be a good measurement,

[00:35:48] **Carol:** Yep, absolutely.

[00:35:50] **Tim:** Yep.

[00:35:51] **Carol:** So I do wanna say,

[00:35:53] I do think that this is a good idea. I just don't know how to implement it yet. And I don't think anyone really understands all of the check boxes that have to be checked before you click the button. Like, plus I'm not even allowed to click the button. I wrote the code.

[00:36:08] Like

[00:36:09] I can't

[00:36:10] out my own code. Someone has to do, so every day someone's gonna have to push a button.

[00:36:14] **Adam:** Are you the one that has to solve this problem? Like it's kind of your, your problem to figure out?

[00:36:19] **Carol:** So sadly, I think I have to punch holes in it in order to show that it's not super ready for us to just start doing this across

[00:36:27] have to go, Hey, thought of this? Have you

[00:36:31] Otherwise, I think people just go, yeah, let's get to work on it. And I'm going, well, I have the oldest system and the most complicated one, and here's why it's not gonna work just yet for me.

[00:36:41] **Adam:** right.

[00:36:42] **Ben:** Is, sorry, I think maybe I missed this in the very beginning. Is this just for OPM or this is for all the agencies.

[00:36:49] **Carol:** is gonna be for my agency.

[00:36:50] **Ben:** Okay, gotcha. Gotcha.

[00:36:52] **Tim:** I

[00:36:52] you, what you said, Carol, is kind of what I told the team. I'm like, we're gonna malicious not, I'm not saying we're maliciously complying here, but

[00:36:59] what we're doing.

[00:37:00] **Adam:** right.

[00:37:01] **Tim:** we will comply with this measurement and make it succeed for us till, till either A, it works for us, or B, it points out the flaws in the system.

[00:37:11] **Adam:** Right.

[00:37:12] **Carol:** and that's where I'm at. I'm like, point out the holes, let's solve them

[00:37:16] then we can figure out how to get there.

[00:37:18] **Adam:** So, I mean, my, this is gonna go right back to what I was talking about before, but it, it sounds to me, I just can't wrap my head around your flow. I think I kind of have an idea of like the way you guys use Git branches and, and your flow there. And I, I, my gut reaction is your Git workflow is incompatible with continuous delivery and continuous integration.

[00:37:37] And so that needs to, yeah. So I mean, and maybe we can take this offline or whatever, but like, I would be more than happy to sit down with you and kind of walk you through how we make changes in our, like what's our Git flow.

[00:37:49] **Carol:** Yeah, luckily for you, I worked with this guy named Tim a really long time ago and he

[00:37:56] **Adam:** he must be really old.

[00:37:57] **Carol:** he was so Git heavy that he made sure I learned a lot about Git so me, I have had a story in our backlog to completely redo our branching strategy,

[00:38:07] **Adam:** Mm-hmm.

[00:38:08] **Carol:** a full testing environment 'cause we don't need it.

[00:38:10] And it adds that layer of complexity that's, that's not there. So that'll be piece of a piece of the work that gets done. So, yeah, so I think between doing some free consultations with you and with Timmy, Timmy, Timmy, I could definitely, you know, get us to a better spot and a good starting place for how we branch and how we, get things out cleanly.

[00:38:30] **Tim:** I think you're way past me Padawan.

[00:38:34] **Ben:** Let me, let me ask you this though, because I know I, I, I can't remember who has said stuff over the years all the time, but I know that we have

[00:38:41] in the past talked about having dedicated QA teams and having work where it literally has to go to a QA environment and then someone has to review it and they have to do all these checklists, and then it comes back I, I'm by no means an expert here, but I do think that some of that kind of a workflow I I is a little an antithetical to the CI/CD system. So it's not just the whole git branching mentality. It's like you have to rethink which humans need to be in the loop. Do

[00:39:17] to be in the loop? Because if the moment you need to have a human in the loop, I feel like you've kind of, it, it's a little bit like an all or nothing. can't kind of, of have CI/CD. It's like you either have CI/CD or you don't. I'm, again, I'm not speaking as an expert here, but I feel like it's not just the Git branching

[00:39:38] **Carol:** No, 100%. That's where, that's where I'm at with, that was another thing I brought up. I was like, how do we get just my code testable?

[00:39:46] put it out on QA because then my two, my developers are gonna come behind me. They commit code all day long. Their code's going out too. So whose is actually being tested? So what we've done at, what I did at another company was we had a, like a webpage that the QA team would go to and there were 10 servers listed on the page. They just picked one that didn't look like it was being used. So they would ask the question and then they had a dropdown and it was all of our active branches.

[00:40:12] They that branch and all it did was do git reset hard and

[00:40:18] like would do a checkout on the branch.

[00:40:20] So all was that branch. They were

[00:40:23] testing that branch. And then they'd say, cool. And once they approved it, they would actually go have to approve the PR before the developer could merge it.

[00:40:31] It required one to to be an approver.

[00:40:35] once it got approved and that could go cool, they've signed off. It can now go into main, which means tomorrow morning it's going out to prod. But we can't solve that. I don't have ColdFusion. I can't just do that here. I can't give them a web server. Like it's a whole thing.

[00:40:50] **Tim:** And I'll tell you, in the business world, the the first ones to go, like when you're looking for cost efficiencies is the QA testers, the human QA testers.

[00:40:58] **Adam:** Yeah.

[00:40:59] **Tim:** Because

[00:40:59] used to have a very, like, we had a lot of people that did QA and then like, things kinda get a little tight and guess who left?

[00:41:06] And now we, I mean, Playwright, we've played around with Playwright.

[00:41:08] That's

[00:41:10] but it's, it still doesn't, hasn't got that smart yet. That's, that's the part of AI that I really wanna see happen is like QA, like end-to-end clicking around like a human being would click around and then reporting things that don't pass muster. I haven't really seen a good solve for that.

[00:41:30] **Carol:** Playwright's been updated. Have you looked recently? Playwright's been updated. See if it fits your, your need now. Oh yeah. I love

[00:41:37] **Adam:** There's a Playwright. MCP?

[00:41:39] **Carol:** Uhhuh,

[00:41:40] I can't access it yet,

[00:41:42] **Ben:** you.

[00:41:42] **Carol:** Okay. I had my time.

[00:41:44] **Adam:** Yeah.

[00:41:44] **Ben:** I, I just wanna go on like a very, very short, quick tangent,

[00:41:47] **Adam:** No.

[00:41:49] **Ben:** I, I, I think a lot of us have dealt with,

[00:41:52] with, like, I, I, I think GitHub calls it like GitHub flow, the idea that you

[00:41:58] **Adam:** Oh, Git Flow. Yeah.

[00:41:59] **Ben:** these feature branches,

[00:42:01] your feature and then you merge it back into the main branch or the development branch or whatever. then sometimes people will talk about trunk based development. And I've tried to read up on trunk based development and people are like, oh, you just, you're committing directly to, to the development branch, committing director development branch. And then at some point someone's like, so you guys don't use branches at all? And people will be like, oh no, we use branches. But they're just really short-lived. And I think to myself, like, you don't, you don't get to have short-lived branches and just call it something different. if you're branching doing feature work and then merging it back in, that's the same thing. That's Git flow. You don't just get to call it something new.

[00:42:40] **Carol:** Mm-hmm.

[00:42:41] **Adam:** Yeah, I mean it is and it isn't. Git Flow has some specific, I don't know. I think we're venturing into capital, a agile sort of, specification level when you start to like, well, it's not Git flow if it doesn't do tagged releases, but you know, there's some of that.

[00:42:57] **Ben:** Anyway, sorry, that was just my little tangent.

[00:42:59] **Adam:** Yeah. Well, that leaves two

## [00:43:02] JSON and the Robustness Principle

[00:43:02] **Adam:** of us. Ben, you wanna flip a coin or, or should I go first?

[00:43:05] **Ben:** I'm in the middle of ranting, I'll just keep ranting

[00:43:07] **Adam:** Okay,

[00:43:09] go off.

[00:43:10] **Ben:** I have always been a huge proponent of JSON JavaScript object notation the data format layer for interoperability between systems. When I make an API call, I like to send JSON. And when I return API responses, I like to return JSON. And then I feel like you get these, astronauts coming in and being like, oh no, everything has to be gRPC, and we have to have these compiled event types, and we have to have super efficient space usage over the wire and binary formats. And, I'm, don't mean any disrespect to anyone who uses those things and likes them very much. My thing here is that I've never really felt like I had a good argument to say why I don't like that, other than my tummy just says that's a bad idea. But I was listening to a podcast that I've really been enjoying lately called Book Overflow. The whole premise of that podcast is a quick aside as these two guys, they read very well-known technical books and then just review them. And it's just a, it's a great way to kind of buy proxy, learn from these books. Anyway, they were talking about the differences between JSON and things like GRPC. And they talked about it. They didn't say the robustness principle, but this is how they were describing it. that by using JSON as the format, you essentially decouple the consumer of an API from the producer of the API response.

[00:44:40] if you need a consumer and a producer to agree on a pre-compiled specification that is strongly coupled to a client, and then if you make a change on your end and they have to bump the client version on their end so that their gRPC structures look the same as your gRPC structures. And, they, they made the argument that if you just use JSON, you can add keys to your JSON response and your clients don't

[00:45:08] it and nothing breaks.

[00:45:10] **Adam:** And, Gzip like solves 99% of the, the efficiency over the wire,

[00:45:15] **Ben:** Yeah.

[00:45:16] **Adam:** complaint.

[00:45:17] **Ben:** So anyway, I heard them talking about this and I was just like, yes. I finally have, I feel like a coherent argument to why you should just use JSON for all of your transfer. And I was very pleased with that.

[00:45:30] **Adam:** Yeah.

[00:45:31] **Tim:** It's easy to read. That's

[00:45:32] **Ben:** It's also very easy to read.

[00:45:35] **Carol:** to read.

[00:45:36] **Tim:** was awful. Jason Dean had a quote once at a conference that stuck with me for years. He said, XML is like violence. The only answer for it is more violence. And I'm like, that is so true. XML is terrible. But JSON is just, it's just beautiful.

[00:45:52] You can read it, you can look at it. I, I go like, my probably most used website is JSON alphabetical sorter. 'cause a lot of times it's not alphabetical.

[00:46:01] that

[00:46:01] I can look at it and go, and it formats it nice and I'm go, oh, that's so pretty.

[00:46:07] **Ben:** yeah,

[00:46:08] **Adam:** So, I guess to to, what is it, steelman, the, the opposite side here a little bit. something I have used that doesn't just use vanilla JSON, I think it is kind of like. A, a wrapper around some JSON, but the, the way that SvelteKit does, what I, I guess you could effectively consider like a form of RPC, right.

[00:46:31] So there's a feature in SvelteKit called remote functions. And the way that it looks to you, the developer, as, as you're writing the code, is just like you're calling a function, right? You import this function in, in, we're talking basically like JavaScript type scripts. You import this function into your file and you just call it.

[00:46:48] And it just so happens that through, path and file name type of, indications that the file that this function is in is server side only, right? So you're, you're in a client side file. You import and use a function that's on the server side and SvelteKit just abstracts that away and it makes it basically an RPC and keeps it all safe, right?

[00:47:08] Any secrets that the function has access to that you don't want on the client side or never visible to the client side, you get your result back. And I think that the, the data layer between those two is like, it's this weird format. I don't understand it. I think it's probably optimized for sending, you know, not just the, the result data, but also like a status message and a status code and potentially multiple payloads in the same response.

[00:47:33] So you've got like this, it's like an array and the first couple of items in the array tell you like, okay, index five is this variable you're looking for. Index seven has this variable that you're looking for. And, it's, so, it's weird. I don't necessarily understand why they do it, but they do it and they're smart people, so I, I have to believe there's a good reason for it.

[00:47:53] Right. I think that I agree with you. If the API that we're talking about, I agree with you that it should just be JSON if the API that we're talking about is one that you want to expose outside of your application. If you would rather it be like, this is for me to use and only me to use, then there is some value in having the, something more complicated than just JSON.

[00:48:15] 'cause then you can have, like, like with this SvelteKit stuff, you, we have TypeScript type safety end to end, right? Like I can do a database query, get the result. I have a, I know an exact TypeScript type that that function returns. And then when I call it on the client side, it knows what type that function's gonna return and I get type safe like accessing the properties of the, that result, which is super nice.

[00:48:36] so

[00:48:37] **Ben:** And I think to your point, with the Svelte stuff, almost certainly. Owning both the server

[00:48:45] the client side code that

[00:48:46] **Adam:** And it's not something I want to share. Yeah.

[00:48:49] **Ben:** detail. And, and I stress this only because as I'm listening to this podcast and I'm realizing that this whole robustness principle is really solidifying my argument, I also tried to take a step back and, and, and introspect and think to myself, okay, well if that's the case, then why have I always been against MongoDB?

[00:49:10] And it's mostly schema list design a huge proponent of relational database design. And it came down to exactly that thing. It's when it's an internal, I own this implementation detail. I don't want things that are loosey goosey. You know, like I don't want the robustness principle. I want very strong constraints because I own it end to end.

[00:49:32] There should be no question about the data that's going into it. Again, this is my personal belief. I'm

[00:49:36] hating on MongoDB, that was the thing is the moment it leaves my boundary of ownership. Then I have to be a lot more loosey goosey with, what can go into it. And it's interesting because I've also experienced this from the other direction where you, you're trying to, let's say incrementally evolve an API and of that dance is always, well, I have the server side code and I have the client side code. And maybe I wanna start to evolve the client side code first by having it send new data that it's just gonna be ignored on the server. Like the server will, the res, the server will accept it, but won't do anything with it yet. 'cause it doesn't know about it. And you think, oh, this is gonna be no problem. And then someone puts some sort of really strict API shape

[00:50:23] **Adam:** Mm-hmm.

[00:50:24] **Ben:** where you're like, well, I accept first name and last name and email, but I don't accept job title, so I'm just gonna throw a 400 bad request. You're like, bro, why can't you just ignore a job title? Why, why can't, why you tell me I can't send that.

[00:50:36] You're literally making my life harder.

[00:50:38] **Carol:** Why didn't you put job title behind a feature flag? Ben?

[00:50:43] **Tim:** job. How's that hurt you? Just taking that in. It's

[00:50:47] Just

[00:50:47] **Ben:** Just ignore it. Just drop it on the floor.

[00:50:50] **Adam:** That's what Taffy does.

[00:50:53] **Carol:** When, uh, when we were switching over to Zendesk, it was probably a few months back. I was helping my team do that and I realized very quickly they do exactly like your first case. They go, send me what you got. If I don't need it, I won't use it and

[00:51:07] it. So I realized quickly I didn't need a model for like, every type of help desk ticket we could be putting in.

[00:51:14] A lot of the data could be like my generic model where you always get like these 10 fields, use it for your ticket creation or not. Zendesk is gonna wipe it out, so just send it. And I was like, since they're not rejecting it, I don't have to have a different model for every single type of ticket we're sending.

[00:51:31] **Tim:** Well,

[00:51:31] **Carol:** that got super. Yeah, I was so excited for that. I was like, yes, I don't have to have all this like legacy code to support because this one no longer wants first name. It can still take first name. It just doesn't use it.

[00:51:44] **Ben:** Yo, I just remember when I was at InVision, and I never had to deal with this, so this was just me kind of on the sidelines watching a car crash happen. But when people were talking about, we're trying, they were the, the new team was trying to build this event stream system, and the way they wanted to get it to work was there was gonna be this central repository of all the events that all of the systems could emit. So anytime any of the systems wanted to add a new event, they essentially had to bump the version of the event system and then every other client would have to eventually pull that down to be compatible with the event system. I'm like, that's so stupid. That sounds awful.

[00:52:27] **Carol:** Yeah.

[00:52:28] **Tim:** How'd that work out?

[00:52:30] **Ben:** I don't think they ever completed it. They ran outta runway, my friend.

## [00:52:34] Work Computer vs. Personal Computer

[00:52:34] **Carol:** Oh,

[00:52:37] **Ben:** All right, Adam, take us home.

[00:52:38] **Adam:** All right. let's start with a quick, survey. So we've got four people here on the podcast. you guys, do you have a separate work computer that's separate from your personal computer that you use? Like when you're not on the clock?

[00:52:50] **Carol:** What do you think my answer is?

[00:52:52] **Adam:** I, I know your answer. 'cause your kid built your personal computer.

[00:52:55] Now you, you've mentioned before, you don't, use that one a ton. but I'm curious, like at the end of the day, if you want to go sit on the couch and, you know, do something on the computer where you want a keyboard, right? Not an iPad, iPhone type situation, but you want a keyboard, like what computer do you take with you?

[00:53:11] **Carol:** I take a MacBook with me. Yeah,

[00:53:12] **Adam:** Is it, but is it a work provided or is it your own? Okay.

[00:53:15] **Carol:** Nope. so,

[00:53:16] and I, I will give you a little why, unless you want other people's answers first.

[00:53:21] **Adam:** It doesn't matter.

[00:53:22] **Carol:** Okay. Okay. So for me, I never want to type anything on my work computer, and this has been for almost everywhere I work

[00:53:29] ever be something I wanna produce or create, and then have intellectual property rights to it because I

[00:53:36] their machine. So I've always had my own personal GitHub where I put my own stuff. It's never been tied to my work accounts. They've always been very separate. I never wanted there to be a situation where I had some big grand idea. Not that they come around often or

[00:53:50] me, but I want it to be mine. Plus, I don't ever want to have someone questioning when I do on the clock, so I keep it separate.

[00:53:56] And with a government machine, everything's locked down anyway,

[00:53:59] wanna try using it.

[00:54:01] **Adam:** right.

[00:54:02] **Carol:** Yeah.

[00:54:02] **Ben:** I was gonna say, I'll, I'll almost flip it and say that in the last like 15 years, I don't think I've ever had a work machine,

[00:54:09] **Adam:** Oh, interesting. I have always had

[00:54:12] **Ben:** that I then do work on,

[00:54:14] **Adam:** okay.

[00:54:15] **Ben:** which.

[00:54:16] **Tim:** again. I've never had a personal machine. I've only had a work machine.

[00:54:21] our company doesn't claim rights over anything you do personally on your machine. they do with the age of AI. They, they don't want you using their corporate instance for personal projects.

[00:54:33] I, so I do have separate Claude and ChatGPT, instances that I

[00:54:37] **Adam:** Like profiles, whatever. Yeah.

[00:54:39] **Tim:** So,

[00:54:40] **Carol:** But you have that on your work machine, right? You have both signed into your work machine. Interesting. Okay.

[00:54:46] **Tim:** So,

[00:54:47] **Adam:** Well, I'm gonna flip it again. I don't believe computers exist.

[00:54:52] **Ben:** Is this all just a simulation?

[00:54:53] **Tim:** Yes.

[00:54:54] **Adam:** no. so I, I, I'm kind of closer to Tim, so I, I, for the last at least, I mean, I've been at this company for 13 or 14 years, something like that. And so I would say for at least the last 15 years, the machines that work has been, has bought me, have been nicer than anything I would've ever bought for myself.

[00:55:12] and the employment contracts have been friendly enough that I don't mind using it as my personal thing. So, like, you know, I was employee, I guess you could say. Number two, if you count the founder as employee number one of AlumnIQ. And so I got to help write the employment contract for myself and everybody that came after.

[00:55:30] And I made sure it was friendly to people like myself who would rather just use the work machine for everything. And so like, yeah, if you're on the clock, then the company has right of first refusal to what you're working on. So we can, as a company, we can say that's an open source project. It's open source.

[00:55:45] We don't care. We don't want the company to have any part in the ownership of that.

[00:55:50] fine.

[00:55:50] Cool. Like I, sometimes I do Taffy work on the clock because the company needs changes to it or whatever, right? Like Steve sent me a bug that he found today and I fixed it, and I, I did that on the clock. And, there's no worry about that.

[00:56:04] because it benefits the company too. And, and it was, that one in particular predates the company as being open source, but you get the point. so there's a right of first refusal, but then b also like very clear. If you're not on the clock for work, then the stuff you're using the company, equipment for.

[00:56:21] Is it's okay. Like you're allowed to use it for personal use and the company doesn't have claim over it. So that's where I'm at. So, and the reason I bring this up is because it came up on our Discord. you know, people kind of being shocked that you would not have that, I would not have a personal machine to do stuff like that on.

[00:56:38] And, and, you know, my response to that is, you know, I almost exclusively use my work machine for looking at porn, so, uh,

[00:56:46] **Ben:** I, I will say it, for me, it's almost entirely a friction issue.

[00:56:54] **Adam:** okay.

[00:56:54] **Ben:** desk that I sit at,

[00:56:56] **Adam:** Yeah.

[00:56:57] **Ben:** keyboard. there was a way that I could snap my finger and make having multiple computers effortless, I would do it. 'cause why not?

[00:57:06] **Carol:** is, You

[00:57:07] can, it's a switch. You can,

[00:57:09] **Ben:** the KVM switch,

[00:57:10] **Carol:** yeah.

[00:57:11] **Ben:** those things are called? I.

[00:57:12] **Carol:** well, all I have is I have a dock

[00:57:15] laptop plugs into, and then my other mon like my monitors each have different outputs and they read whatever's getting a signal. So I just unplug the C from my laptop.

[00:57:26] **Ben:** Unplug. No, this is already too much work.

[00:57:28] **Tim:** Yeah.

[00:57:29] **Carol:** Hit the computer. I'm

[00:57:30] **Ben:** You lost me.

[00:57:31] **Carol:** Yeah. I'm, I'm talking

[00:57:33] **Adam:** No, Ben, you, you stack your personal laptop on top of your work laptop.

[00:57:37] **Carol:** so I kind of do that sometimes.

[00:57:41] **Tim:** so I did see this kind of on Discord and the one argument that I did agree with, I, I never really thought about was if I got fired. Now I've been at my

[00:57:50] **Adam:** Mm-hmm.

[00:57:51] **Tim:** 1999, so I'm not too worried about that, but I mean, you never know

[00:57:56] **Ben:** Mm.

[00:57:56] **Adam:** Yeah.

[00:57:57] **Tim:** that, because in my company when you get fired, they're like, send us your, they shut off access to your laptop.

[00:58:04] **Adam:** Mm-hmm.

[00:58:05] **Carol:** You can't log in at all. Yeah. Mm-hmm.

[00:58:07] **Tim:** Your laptop is completely bricked to you.

[00:58:10] **Adam:** Right.

[00:58:11] **Tim:** and so that's why I make sure I do backups of, I have of my password vault 'cause it has personal password stuff in it and everything, things that I personally want or sound like an ex external drive that I hook up to it. but yeah,

[00:58:24] **Carol:** you do what?

[00:58:26] **Tim:** well I, I'm not government. I can hook up USB stuff

[00:58:28] **Adam:** That's right.

[00:58:31] **Carol:** What?

[00:58:32] **Tim:** but you know, there would be a period of time there where I would be like, technology. It'd be a technology desert at my house because my laptop is gone. The, the, the show bot

[00:58:43] **Adam:** Mm-hmm.

[00:58:44] **Tim:** Discord channel would, would be dead until I could get it back up and running again. I know everyone would, would, would

[00:58:49] **Adam:** Be so disappointed. Yeah.

[00:58:51] **Tim:** so, so disappointed. But, yeah, I mean I think that is a legitimate claim, but like Ben says, it's just I don't have enough desk space.

[00:58:59] so much work just to have another

[00:59:01] **Adam:** And we've seen your desk. It's tiny.

[00:59:03] **Tim:** It, my desk is tiny. Yep. The, the monitors are huge, but the desk is tiny. So, yeah. I, I, I dunno, I mean, I've got, and I've got multiple computers around the house to my kid.

[00:59:14] Each of my kids have a computer. There's a computer like in the entertainment room that, that runs, my plex storage stuff. So I was like, I, no, I'm not short for computers, but getting it back to where I need to be to actually be productive would be a pain in the butt. But it take a couple days and I need something to think about, you know, while I process getting fired,

[00:59:36] **Ben:** if I was gonna get fired, they would have to ask me to start shutting down my own access. So, Screw you guys.

[00:59:43] **Tim:** be king.

[00:59:44] **Adam:** yeah. Anyway, go ahead Carol. I.

[00:59:46] **Carol:** So talking about what we can plug in. I was on site at Microsoft in DC working on that project with the team, and we had Microsoft architects there and stuff. I get there, I pull my laptop out, I remembered my dock. I remembered the cables. I need to plug a monitor in. I forgot a mouse. So they're like, oh, we have one for you.

[01:00:06] They bring in this Bluetooth mouse and my coworker next to me starts laughing 'cause he understands what's about to happen.

[01:00:14] at it and I go, thank you for finding this, and I sit it down and don't touch it the whole time because Bluetooth is disabled on our machines. We're not allowed to use Bluetooth.

[01:00:23] I look at it and I go, oh, I appreciate it, but I have to have a cable that only can go into my dock. By the way.

[01:00:30] **Ben:** so the, this brings up a very interesting question that I have struggled with in my mind. So, and, and the reason that this is meaningful for me is because I have an external vertical mouse.

[01:00:42] an external, ergonomic keyboard, and I actually even have this like little rubber cut out that I put around the edges of the keyboard to rest my palm on a little bit. Like I am a physically broken individual and I can't work on my laptop directly, or, you know, if I can, it's only for small spurts of time. this made me realize that in the age of laptops, it, I feel like you can't expect me to be able to just pick up and go work anywhere. You know, if, if,

[01:01:14] the company was like, oh, everybody come to the office and we're gonna work together today, I'm like, whoa, bro. Like, what if I had a desktop computer?

[01:01:23] just gonna pick that up and carry it to the office.

[01:01:26] **Carol:** My cat situation for this onsite meeting was to have our help desk off like center in, in DC 'cause we were in DC so we have this, our main office is in DC so I had them arranged to have 13 monitors delivered

[01:01:40] not possible for me to work on a monitor. And I asked for two, someone else asked for two and I had to give one.

[01:01:47] I didn't have to, I chose to give one of my away. I was like, no, it's okay. There's not enough table space. Anyways. So everyone's sitting there like on their laptops piping, looking this way, like looking to the left and right to see their monitor. We had delivered.

[01:02:00] **Tim:** everybody's jammed in

[01:02:01] **Carol:** Yeah. Yeah. It

[01:02:03] **Tim:** like like a

[01:02:04] children's table at a

[01:02:05] **Carol:** Yes.

[01:02:06] **Adam:** the old school land party.

[01:02:07] **Tim:** Yeah, exactly. That's crazy.

[01:02:10] **Adam:** so Ben, you said that like you don't have a work computer. and I, so what I take that to mean is you just have a really nice personal computer and then, you know, you get hired somewhere, you work there and you just use your personal computer for work purposes. Does work, give you like a, a stipend or something that you can use to, to cover upgrades and, and whatever toward that.

[01:02:32] **Ben:** yes, I think so. I mean, I, I honestly, like, my computer is pretty old actually at this point. I don't wanna, I don't wanna make you guys all feel bad for me, but I'm only on an M1 chip. which, yeah, which I think is like, from

[01:02:46] 21. and before that, I, I think my previous one was from like 2015.

[01:02:51] but yes, I think you can get a stipend. InVision was weird because, you know, we were going out of business and there was no money. So I, at that time, I was like, I'll just buy my own computer, and I'll just write it off, I assume I could do. I've never quite clear on the rules of when you can write stuff off and how you're supposed to do it over, whatever. I'm, I haven't been audited since. There's no one working at the IRS anyway.

[01:03:16] **Tim:** Right.

[01:03:17] **Ben:** but I have always been very good about installing whatever security software they want,

[01:03:22] like, endpoint security and antivirus stuff.

[01:03:25] And that was actually one of the big things I was so nervous about. Going back to, you know, what if you get fired, when InVision was winding down and they started wiping people's computers, I was like, whoa, whoa. Just so you know,

[01:03:37] **Adam:** Yeah.

[01:03:37] **Ben:** is my computer.

[01:03:39] Do not wipe it.

[01:03:41] **Carol:** I will block you.

[01:03:44] **Ben:** But yeah, I mean in the last like 15 years I think, I've only owned three computers, so it's been, it hasn't been too bad.

[01:03:51] **Carol:** What I, what I struggle with though, with having two, is maintaining two developer spaces that have all my configs. 'cause

[01:03:58] at work and I'm like, oh, I hit the shortcut and I go do it at home. And I'm like, what? Why didn't it work? And I'm like, oh, I haven't moved that config over here yet.

[01:04:08] **Adam:** you gotta have your dotfiles synced up to a GitHub repo and

[01:04:12] **Carol:** I am not signing into my personal

[01:04:14] GitHub on

[01:04:14] **Adam:** yeah. Yeah.

[01:04:17] **Ben:** But just to go back to this idea of mobile computing,

[01:04:20] do you think it's fair to exist in a world where you can just expect people to have mobile compute? Or should you be designing as a business, should you be designing work environments where if you need people to come into the office, it should be for non-computer stuff, like it should be for the whiteboarding and the getting together in the conference room and scratching on old school paper.

[01:04:42] **Tim:** I don't know about fair, but I know that we pretty much only buy laptops. We

[01:04:48] we don't buy desktop computers for

[01:04:50] **Adam:** I, and I think Ben was kind of going further than that, right? Like not just buying laptops, but then to your point earlier, Ben, about like, okay, but for me to be comfortable working for any length of time, even if it's in the office or whatever, I have to bring in my, my personal mouse, my keyboard, my wrist rest.

[01:05:07] **Tim:** but, but I mean, so, so at our work, we don't have that

[01:05:11] space, but what we do have is every desk. The office has multiple

[01:05:18] exact same dock. We buy the exact same laptops. So there's a dock that fits. There's, there's, there's keyboards that there, all you have to do is come in and hook your machine up to the dock and you're ready to go. Now, if you have like preferences about a mouse or about a, a, you know, a pad for your carpal tunnel that's on you to bring that.

[01:05:36] But every, every machine you just

[01:05:38] in, hook your, hook it up to the dock, and you're good to go.

[01:05:41] **Adam:** So to answer the question, I think it's not unreasonable to expect some ability to be, to work mobilely, if that was the question. but I do think that we need to be cognizant to give appropriate affordances, right? Like so for somebody who needs that carpal tunnel, wrist rest or whatever, you know, we need to make sure that they have time and the ability to bring in the things that they need if we're asking them to come in somewhere and you know, time to set it up and that sort of thing, right?

[01:06:14] Like. I, I don't think it's unreasonable to ask people to be mobile, but we do need to be prepared to support them in whatever they need to make that happen.

[01:06:22] **Ben:** Yeah,

[01:06:23] **Carol:** you feel like there's a fair expectation that productivity greatly decreases when you don't have the

[01:06:29] your normal desk of like your multim monitors and you know your mouse, your keyboard productivity goes down when you're just on a a, a laptop screen.

[01:06:38] **Adam:** Yep.

[01:06:39] **Ben:** because like, I remember, so I, I have my MacBook right now, and the one before this was a MacBook. But for years I had an iMac, which is essentially just a giant monitor that's also a computer.

[01:06:51] **Adam:** Mm-hmm.

[01:06:51] **Ben:** if I ever had to do an onsite, I had to use this ancient laptop that I had that didn't have any of my work software in installed, like didn't have Docker or anything like that.

[01:07:02] And I would have, you know, I could do the most minimal amount of stuff on it, but I wasn't about to bring my iMac with me to a work event. And I just did. It's, it's one of these things I've grappled with over the years. Like what is the, what is appropriate? I don't know. I mostly just grumble. I, you know, everyone else has a

## [01:07:19] Patreon

[01:07:19] **Ben:** laptop.

[01:07:20] **Adam:** Alright, well then this episode of Working Code was brought to you by our new Ben Hates MongoDB Merch. And listeners like you, if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, you should consider supporting us on Patreon. Our patrons cover our recording, editing and transcription costs, and we couldn't do this every week without them.

[01:07:39] Special thank, special, thank one of my Kevin from the office.so much thank to our top patron Monte. You rock man. thanks for your long term support, long time support.we're gonna go record the after show. I've said it a million times, I've said it, more than 250 times, I guess. Well, but we didn't have after show in the beginning.

[01:07:58] So,

[01:07:58] but the after show for the uninitiated is, the non patrons, the outro music's gonna play for the patrons. The outro music's gonna play. And then we're gonna come back and we're gonna talk about more stuff, usually unrelated. you know, I thought I would offer, since we're, we're kind of getting to the end of, spoiler time period, spoiler warning time period, I'd offer my, final verdict on the Project Hail Mary movie.

[01:08:20] I've seen it a couple of times now.

[01:08:22] **Ben:** Nice.

[01:08:22] **Adam:** Um,have some thoughts that are different from my initial review, so I thought I'd offer that up. Tim wants to talk about his plants, and, and his music.and you know, that's what it is after show is fair game, anything, anything's fair game. so if you'd like to get, access to that, you can go to patreon.com/workingcodepod, throw a few dollars our way.

[01:08:42] Will you throw the after show your way? And that is even

## [01:08:45] Thanks For Listening!

[01:08:46] **Adam:** Steven. that's gonna do it for us this week. We'll catch you again next week. And until then,

[01:08:50] **Tim:** Hey listeners, even though Ben thinks your liver taste great with some fava beans and a nice Chianti, your heart matters.
