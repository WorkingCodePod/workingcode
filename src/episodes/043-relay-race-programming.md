---
title: "043: Relay Race Programming"
description: 'You might think that "programming" is a relatively straightforward concept: take abstract ideas and codify them into lines-of-code (LOC). But, within this broad abstraction, there are a multitude of implementation details. Some engineers love to hunker down and write code inside a metaphorical bubble; mob programmers love to dog-pile on the same machine, blitzing the problem until it''s obliterated; and, pair programmers methodically alternate responsibilities between a "driver" and a "navigator" in cooperative pairing sessions.'
date: 2021-10-06
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/043-relay-race-programming/id1544142288?i=1000537721757"></iframe>

You might think that "programming" is a relatively straightforward concept: take abstract ideas and codify them into lines-of-code (LOC). But, within this broad abstraction, there are a multitude of implementation details. Some engineers love to hunker down and write code inside a metaphorical bubble; [mob programmers][mob-programming] love to dog-pile on the same machine, blitzing the problem until it's obliterated; and, [pair programmers][pair-programming] methodically alternate responsibilities between a "driver" and a "navigator" in cooperative pairing sessions.

On today's episode, Carol shares her team's approach to product development which sounds more like "Relay Race Programming." First, her team does some up-front design and planning in order to orient the work. Then, her team divvies up the tasks, processes the work in parallel, and keeps a constant line-of-communication open such that they can unblock each other as soon as issues arise. While this approach takes some getting used to, Carol believes that it has increased her productivity, decreased her Pull-Request review latency, and opened the door to many more mentorship opportunities.

## Notes &amp; Links

- [Agile Alliance: Pair Programmging][pair-programming]
- [Agile Alliance: Mob Programming][mob-programming]
- [Ward Cunningham: Ping-Pong Programming](http://wiki.c2.com/?PairProgrammingPingPongPattern)

Follow the show! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media][editor].

[mob-programming]: https://www.agilealliance.org/glossary/mob-programming/
[pair-programming]: https://www.agilealliance.org/glossary/pairing/
[working-code]: https://workingcode.dev/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[editor]: https://www.zcross.media/
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/043-relay-race-programming.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** I think the thing that trips me up the most is this idea that someone would just finish work that Carol started or that Carol finished work. Someone else started. I feel like I'm just an emotional child when it comes to my code and I have this extreme sense of ownership.

[00:00:18] **Carol:** Yep.

[00:00:18] **Ben:** I, and if I came in one day and someone was just like, oh, I saw some of the stuff you're writing.

[00:00:22] **Ben:** So I just

[00:00:23] **Ben:** added a

[00:00:23] **Ben:** bunch to it. I'd be like,

[00:00:25] **Carol:** so good, good point. Like circle back to that. That's what happened up front. When I switched over and started working like this, because I've never done this before in my life. I've never worked like this. It was an insult. I immediately went, my code's not good enough. Why are you even looking like what's going on here?

[00:00:44] **Carol:** Like I messaged someone and was like, did I not do something right? And it was like, no, I just wanted to keep it going. I was like, oh, okay. So I can calm down. My blood pressure can drop a

[00:00:55] **Carol:** little bit, but there's like the attachment to it. So it took me a long time to go from it's mine to it's my teams.

[00:01:03] **Carol:** This

## [00:01:04] Intro

[00:01:04] **Carol:** is my

[00:01:05] **Carol:** teams

[00:01:06] **Adam:** Hey everybody. It is show number 43. And on today's show, we're gonna be talking about some pair program. Hey, you know what guys, it's October, we are closing in, on our first year of completeness or,

[00:01:32] **Adam:** or

[00:01:33] **Ben:** That's

[00:01:33] **Adam:** yeah, well, that was awful. Awfully put our first year of,of recording this podcast, this thing we're doing.

[00:01:38] **Adam:** yeah, so I mean less than 10 episodes. All right. This is 43. We've got nine more before we hit 52. Oh full year. Anyway, before we start on today's topic, we're going to start as usual with our triumphs and fails. and Tim, it's your turn to

[00:01:51] **Adam:** go first.

## [00:01:52] Tim's Failure

[00:01:52] **Tim:** Yeah, so I got a fail. So I thought I knew how SSL certificates worked. but today, I learned how much, I didn't know, particularly using when you're using a Java type program, you have your CA certs file and sometimes you have to go, update manually update your CA

[00:02:08] **Tim:** But then your certificate, so whatever your

[00:02:10] **Tim:** domain name is, it's, google.com the main level certificate, just for your domain name.

[00:02:14] **Tim:** It there's a chain, right? There's a certificate authority. We use let's encrypt and let's encrypt because they aren't expiring. on September 30th, they're expiring their routes certificate. They have issued like, intermediate certificates and cross signing certificates. So that in hopes that wins timber 30th rolls round things don't break.

[00:02:37] **Tim:** But today, for some reason, I think I really haven't figured out why, but so the certificate for one of our sites stopped working and I API was calling that site and just getting an error, a connection area. and it turns out he was having an issue with one of those. It didn't ha basically have the intermediate certificate.

[00:03:00] **Tim:** and I think the reason was because we have scripts that automatically go and update the certificates. And for some reason it wasn't being done because there was a firewall change needed to happen. Once that change happened, he went and got it and it didn't have the intermediate certificate, which is why I'm so broke.

[00:03:15] **Tim:** But I mean, there's so much more to certificates and I thought, well, reading up on it. I, found an article by Pete Frye tag at had some really good, information on it. And basically what he said not to do is what we were doing. And that was just, and that was just going and getting the intermediate certificate and manually sticking in into your CA certs.

[00:03:37] **Tim:** So, apparently Java updates CA. Pretty regularly. so you can go get that. Also Mozilla keeps up a very up-to-date version of a certificate authority list, and he has some links and articles to there about how you can make basically make your own CA certs file and just replace it so that you have all of the trusted routes, certificates, intermediate certificates to cross sign certificates, and things like that.

[00:04:01] **Tim:** So, yeah, it opened my eyes just how ignorant I was of SSL

[00:04:06] **Tim:** certificate world.

[00:04:08] **Carol:** it's one of those things when it's working, you're just like, oh great. But when it doesn't work and you have to go research it and learn it all over again, you're just get like mind blown every time.

[00:04:16] **Carol:** And then I just always forget it again

[00:04:18] **Carol:** because

[00:04:18] **Carol:** it works for several years then.

[00:04:20] **Tim:** Yeah. Well, I mean, because we're using let's encrypt let's encrypt really, they only

[00:04:24] **Tim:** want to issue 30 days certificates. we force it to do, three months certificates, but I'm like, if I'm going to have to check stuff every three months that's not tenable, we got to figure out a way to, to make sure that this is correct.

[00:04:37] **Tim:** So

[00:04:38] **Tim:** that's what I kind of was not what I was planning on working on today, but that's kinda what me and the, our dev ops team got working on today.

[00:04:48] **Ben:** Yeah. I don't know anything about certificates. It's all very confusing to me. I listened to an interview with the guy who started let's encrypt. I think maybe it was on the software engineering, daily podcasts, maybe like a couple of years ago. And he was working on the let's encrypt project

[00:05:03] **Ben:** for. A solid decade before it became an actual thing and started to get widely used.

[00:05:10] **Ben:** And it just, every time I hear about people who are so committed to something that they work on, these, what I think is an extremely long timeline, I'm just in awe. I feel like my attention span for work projects is like, if something's going to go more than a

[00:05:28] **Ben:** month,

[00:05:29] **Ben:** it's very hard for me to wrap my head around

[00:05:33] **Tim:** Well, the good news is the new roots certificate that they're issuing doesn't expire until 2035. So, by then I'll be at retirement age

[00:05:40] **Tim:** and I won't have to worry about it.

[00:05:41] **Ben:** no way.

## [00:05:42] Carol's Triumph

[00:05:42] **Tim:** how about you, Carol? What's up?

[00:05:44] **Tim:** You've got to

[00:05:45] **Tim:** fail. You've got to fail.

[00:05:45] **Carol:** no, no. I refuse to let this be the failure time. Like I'm going to make one of us be good. Okay. So I'm going to go with the triumph. I worked on a project months ago and this was before, you know, this big effort I had going on for a couple months. And it was this, big data import to basically automate how our users can use another side of data that we have.

[00:06:04] **Carol:** So we automate that like coming in for them. Right. So, the business wanted to add this import to another set of like our, how would I describe this into another set of like our what's called our forms, but it's basically a type of data. Okay. So we're going to add all this back in. Well, I looked at how I had wrote some things before.

[00:06:24] **Carol:** And I was like, it's okay to fix it because this was not great. So I am not even upset that I didn't get it right. The first time. I'm just happy that I'm willing to go back and fix it. So I'm changing kind of how we live over some of the data and how we're using it. And rather than, recreating every time, recreating it every time, just because, very well names are like differ between the two data sets when it's the same data.

[00:06:47] **Carol:** I'm just having it switch it rather than like actually go hard-code every one of them. So now I've just created this little like, list that does the conversion for me, and then it's just always there. So it's a lot cleaner. And now when you make a change to it, it's a lot smaller to change. And if we want to add more, it's just better.

[00:07:03] **Carol:** So I'm just happy that I looked at my old code and was like, Hey, this isn't great. I'm going to fix it. And I'm going to make it better going

[00:07:10] **Carol:** forward. So yeah. Wins.

[00:07:12] **Adam:** Nice.

[00:07:13] **Ben:** That's how you get better.

[00:07:14] **Carol:** Yeah. How about you, Adam?

## [00:07:16] Adam's Failure

[00:07:16] **Adam:** I've got a fail and it's a feature flag thing, but it's, I mean, I'm calling it a fail. It kind of is a fail, but it's just a fail of, my, my personal opinion or something. So a while back, we put in the ability to do feature flags and my coworkers have been using it and loving it. And my fail is I haven't got to do any of that.

[00:07:35] **Adam:** I haven't had any of that fun. I did all this work to build a feature flag service and the API and the data storage and all that. And that was a lot of fun, but I'm not reaping any of the rewards yet. the only feature flag that, like the only feature that I put behind a flag was a thing that just like proved that the feature flag service was working, that we could toggle them on and off immediately.

[00:07:53] **Adam:** Just a little blurb of Texas says you are a developer on the admin dash page dashboard page. and,I'm kinda sad about that. Although, as we were like, kind of transitioning into this for me, I started to think of something that would be a really good use case for a feature flag, which is we have, so we among the many things that our product does, we have a event registration system and it's got, Very complicated, pricing rules built in, right?

[00:08:19] **Adam:** You can have different types of people in your party. You can have adults and minors. You can have the primary person and their guests, and you can have grandparents and the person that's a student versus a parent,like student relationship to the school. And so like all, and you can be in the alumni association and be a member.

[00:08:37] **Adam:** So there's all these different things that need to be taken into consideration. And there's a CFC that handles all of that currently. and nobody wants to touch it. it's one of those things, right? As a couple hundred, several hundred lines long, and it's very,function calls, another function, calls another function, 12 layers deep or whatever.

[00:08:54] **Adam:** It's very hard to wrap your head around. And, I just thought that like, Hey, we could create a alternate, implementation and using feature flags. And like, if it doesn't work, just turn it off and.

[00:09:07] **Adam:** So that would be

[00:09:08] **Adam:** fun,

[00:09:09] **Adam:** but yeah, I, haven't got to do a

[00:09:11] **Adam:** single thing with them yet, so I'm calling that a

[00:09:13] **Adam:** fail

[00:09:14] **Tim:** Not eating your own dog food.

[00:09:17] **Ben:** Well, he's making other people eat his dog food, but he just has some painful too.

[00:09:24] **Adam:** right. So, yeah, that's me. how about you, Ben?

## [00:09:28] Ben's Failure

[00:09:28] **Ben:** I'm going to go with a failure. And it's a little bit of a strange

[00:09:30] **Ben:** one. Usually I talk about technology stuff, but

[00:09:32] **Ben:** this

[00:09:33] **Tim:** The boys all failed.

[00:09:33] **Ben:** one. Yeah.

[00:09:36] **Ben:** So,

[00:09:37] **Ben:** I live up in New York state and, over the weekend my wife went down to visit her mother down in Maryland. And I don't, I work from

[00:09:45] **Ben:** home.

[00:09:45] **Ben:** So we're together like all the time and, and I love it, but

[00:09:50] **Tim:** She works from home too.

[00:09:51] **Ben:** yeah. And, when she was down in Maryland, I have to say I got really lonely, which was

[00:09:57] **Ben:** like surprisingly lonely. And then I think it, I think that was happening because I've been kind of overwhelmed at work. And I think I lean on her just from a social construct standpoint when I'm not working to like prop me up and make me feel better. And I think being alone over the weekend, It made me become more aware of like how we're just run down and stressed and tired. I am. And, don't know. it was unnerving is maybe not the right word, but it was, I was taken back at how lonely I felt like usually when I'm alone, it's like time to rock out on some side hustle, coding, and listened to some podcasts and just like

[00:10:39] **Ben:** rejuvenate.

[00:10:40] **Ben:** But I didn't have any of that going on

[00:10:43] **Ben:** at that thing. I

[00:10:43] **Ben:** ended

[00:10:44] **Ben:** up

[00:10:44] **Ben:** just watching TV and

[00:10:45] **Tim:** probably mess with your schedule too, right?

[00:10:47] **Ben:** yeah. Yeah. I think so,

[00:10:48] **Ben:** too.

[00:10:48] **Carol:** And you are a creature of

[00:10:49] **Carol:** habit.

[00:10:50] **Ben:** That's true.

[00:10:50] **Adam:** Was this your first time apart since like,

[00:10:53] **Ben:** no, we've been.

[00:10:55] **Adam:** So the reason that I bring it up is I felt something that I feel like was probably kind of similar, right before COVID my family went on a cruise. And so we, the four of us were staying in the same, like eight foot by 10 foot space for a week.

[00:11:09] **Adam:** And we were on top of each other. And of course there was a certain amount of annoyance with that. But when we got home and the kids went back to school that first week that they were back to school, I have never

[00:11:18] **Adam:** missed them. Like I miss them, just the kids never missed them. Like I missed them that

[00:11:22] **Adam:** week.

[00:11:23] **Ben:** Yeah.

[00:11:23] **Adam:** very strange.

[00:11:24] **Ben:** it's weird. It's like, normally if I'm alone, I have this whole list

[00:11:29] **Ben:** of things I

[00:11:29] **Ben:** want to

[00:11:29] **Ben:** do. And usually I can't motivate to do all of them by any means,

[00:11:33] **Tim:** it's nice to dream.

[00:11:34] **Ben:** but it's, yeah, it's nice to dream. And what I found is like, I'd wake up in the morning and I do my sort of morning ritual stuff.

[00:11:39] **Ben:** And then I would just be like, what am I going to do with the rest of my day? Why there's so much day ahead of me. It was, I don't know. It was just

[00:11:46] **Ben:** sad, but I feel good now. I mean, I'm tired and rundown, but I feel good. So

[00:11:51] **Tim:** I'm glad you're in a better place.

[00:11:52] **Ben:** Yeah, yeah.

[00:11:53] **Ben:** yeah.

[00:11:53] **Adam:** Okay, well then let's talk about some pair

[00:11:56] **Adam:** programming

## [00:11:57] Do You Even Pair Program?

[00:11:57] **Carol:** Yeah. Do you guys even pair program, have you pair program

[00:12:00] **Carol:** before?

[00:12:01] **Adam:** I've

[00:12:01] **Tim:** about an apple.

[00:12:02] **Carol:** I, Yeah,

[00:12:04] **Tim:** Wow.

[00:12:05] **Adam:** and

[00:12:05] **Carol:** not that the joke.

[00:12:07] **Carol:** Yeah.

[00:12:07] **Carol:** it took me a minute.

[00:12:09] **Tim:** Let's just get that out of the way. Okay.

[00:12:10] **Adam:** I've let's I'll say I'm pair

[00:12:12] **Adam:** curious,

[00:12:13] **Adam:** I've experimented

[00:12:15] **Adam:** with

[00:12:15] **Carol:** dabbled my toes in

[00:12:16] **Carol:** it.

[00:12:17] **Adam:** right. But th the, where I got, where I get stuck on it mentally is like, the thing that I did, I would say falls under the category of like obvious code. We weren't pair programming because we were trying to make the code any, like, trying to solve a hard problem.

[00:12:35] **Adam:** Pair programming to like try out pair programming.

[00:12:38] **Adam:** And this was, several, several years ago at my last job. and, it was myself and like our team lead and trying to experiment with it and see if it was something we were gonna, like make a normal thing for our team. And it was fine. The code we wrote was fine.

[00:12:52] **Adam:** We both understood it, which was a good thing, but, it just didn't feel like it had huge benefits for us. And this is from like maybe spending a week together working on this. So not a huge amount of time. And

[00:13:04] **Adam:** that's all that came with it. Like we just kinda, it kind of went by the wayside.

[00:13:09] **Carol:** I think it does for a lot of

[00:13:10] **Carol:** people. What about U2? Ben? Have you pair

[00:13:12] **Carol:** programmed,

[00:13:13] **Ben:** I've never, I've put heads together to try to debug a problem. I'll be pulled into a screenshare, I'll pull someone else into a screen-share if someone's stuck,and that'll last like half hour, hour, maybe most, but I've never actually pair programs as a paradigm

[00:13:28] **Ben:** of how we're going to do work. and the idea of it is very scary to

[00:13:31] **Ben:** me.

[00:13:31] **Carol:** It is, and it's intimidating.

[00:13:33] **Ben:** an energy emotional

[00:13:35] **Ben:** standpoint,

[00:13:36] **Ben:** it, it sounds like it would

[00:13:37] **Ben:** be

[00:13:37] **Ben:** exhausting.

[00:13:38] **Carol:** Yeah. There, There, are days it's very, very

[00:13:40] **Carol:** challenging.

[00:13:41] **Tim:** so I'm looking at the definition, right? Of pair programming and according to agile alliance.org, it is consists of two programmers sharing, a single workstation, one screen, one keyboard and mouse among the pair. Okay. First off, no developer only has one screen. So

[00:13:58] **Tim:** I take issue with that

[00:13:59] **Ben:** I only have one screen,

[00:14:01] **Ben:** Tim.

[00:14:02] **Tim:** really? Oh my God.

[00:14:04] **Adam:** So he's saying you're not

[00:14:05] **Adam:** a developer, Ben.

[00:14:06] **Carol:** Oh,

[00:14:08] **Ben:** I demand satisfied.

[00:14:10] **Tim:** I can't imagine that anyway, the program or the keyboard

[00:14:14] **Tim:** is usually called the driver and the other also actively involved in the programming tasks, but focusing more on the overall direction is the navigator is expected that the programmers swap roles every few minutes or so. So have I done that?

[00:14:28] **Tim:** No, absolutely not. Never. what we

[00:14:30] **Tim:** have done is kind of, kind of what Ben said, you're dealing with a difficult problem. You go to someone's computer and you stand there for maybe 30, 40 minutes and you work out an issue together. So yeah, this idea of pair programming is not something, I've ever done, nor do I think I could ever get management, including myself as a manager to approve of.

[00:14:49] **Tim:** So.

[00:14:50] **Carol:** Yeah. So the troubleshooting side of it with pair programming. Sure. I think most of us have done that if you've ever been in any type of lead position, like people are going to come to you with challenges, they're going to come to you with problems and

[00:15:00] **Carol:** you're going to have to go look at what they're looking at.

[00:15:03] **Carol:** And that's usually easier for me to like, look at what they're seeing, like what they have open than me trying to get into the code myself and figure out where they went, how they got there. Like, let me just start with where you're at right now. So that's one thing. And the pair programming you're describing is like how I see it on movies.

[00:15:19] **Carol:** Right? It's like the nerdy someone's at the whiteboard, drawing out like guides and things and someone's coding. And then they jumped back up and, they switch back and forth. That's not exactly what I'm talking about here. So. The thing that, we do is we actually,

[00:15:34] **Carol:** we've talked about before we had the design buddies, right?

[00:15:37] **Carol:** So up front, we designed together, but through the last two, yeah, the last two big efforts I've done, we've actually pair programmed everything. So I'm on this last one, we actually broke out the, like the duties of the application and every person had their own objective to cover. So like I was handling all the authentication and I'm having to push up my code constantly.

[00:16:00] **Carol:** Even if it's in the broken state, I'm having to constantly kind of push it up so that whoever's working in, it has like a fresh version and has like something to Deepa has something look at how we're going with things. And we're constantly having to communicate back and forth just with, where we're going, where we're stuck at it.

[00:16:17] **Carol:** It turns into like daily calls with, Hey, here's where I'm at today. Here's what I'm doing right now. But the big thing that I struggle with still while doing this is pushing up broken code. I have to get at the end of the day, I'm on the east coast or on the west coast. So I push up three hours before they even finished wrapping up and I literally put up code and I'm like, Hey guys.

[00:16:38] **Carol:** So I have some aborts in here. If you go look at the stuff I'm doing, like all of this is kind of just kind of hanging out. If you want to look at it, go ahead. Well, on this last project, we got really good about picking up each other's work about going, okay, I'm going to take where you've just stopped at.

[00:16:56] **Carol:** I'm going to hit play. I'm going to look at what you were doing. And I'm just going to add a whole bunch of code to what you've been coding. So I would come in the morning and I would have written like maybe, started a class. And in that class I had like a few methods that were doing something and he would take my idea and keep adding to it.

[00:17:13] **Carol:** And that blew my mind initially up front, like the fact that. We've laid these guidelines out well, enough structured what we want to do have like got a good plan in place that I can halfway write something and someone can come behind me and they can pick up and keep riding on top of it because we know what the goal is and we know what we're doing.

[00:17:33] **Carol:** So then I pick it up in the morning. I'm like, oh, okay, I'm going to keep going with this part. Like we're on it. And then the afternoon, like we resync and it works really well, but there are days if anybody is off their game. It's exhausting because like, like last week or was it week before last? I just, I wasn't feeling people not wanting to communicate and then sick.

[00:17:54] **Carol:** I didn't want to talk to people. So the last thing I want to do is sit and talk about like, how I'm thinking through this problem. I just want to mindlessly like write code and not worry about anything else, but when you're pair programming, you can't do that. You have to like continuously communicate to each other about the status of things.

[00:18:11] **Carol:** So I'm finding really good benefits with like pair programming, these projects, but I'm also seeing like the downside and the insecurity of having to like have my code always out there, even in a broken state, like it's, I'm on both sides of it

[00:18:25] **Carol:** and

[00:18:26] **Adam:** I have two questions

[00:18:27] **Adam:** for you. So it sounds like you're not doing what Tim just

[00:18:30] **Carol:** No, it's different. It's

[00:18:32] **Carol:** different.

[00:18:32] **Tim:** I was going to say, congratulations, you just invented relay

[00:18:35] **Tim:** race programming.

[00:18:37] **Carol:** yeah.

[00:18:38] **Tim:** Congratulations. It's a new thing. It will be

[00:18:40] **Tim:** the, it will be the hot, the hotness

[00:18:42] **Tim:** of

[00:18:42] **Tim:** 2022,

[00:18:43] **Carol:** So I could see if we were sitting in an office together. So if the three of us were sitting physically in an office together, granted,

[00:18:50] **Carol:** we

[00:18:50] **Carol:** wouldn't touch each other's keyboards. Cause that's just gross. I don't know where your hands have been. I

[00:18:54] **Carol:** don't

[00:18:55] **Carol:** want to touch your keyboard. Okay. I know where your keyboards been.

[00:18:59] **Carol:** That's why I don't want to touch it. Okay. Yeah. We're not going to do that. There's no dishwashers

[00:19:03] **Carol:** here.

[00:19:04] **Adam:** After COVID nobody's ever gonna touch each other's keyboards

[00:19:06] **Adam:** again

[00:19:06] **Carol:** Exactly. Exactly. You keep

[00:19:08] **Carol:** them to

[00:19:08] **Carol:** yourself. So, but I could totally see doing that. Like just rotating through code and sitting there, talking back and

[00:19:14] **Carol:** forth through problems and only one person writing code.

[00:19:17] **Carol:** I could see that

[00:19:18] **Carol:** functioning.

[00:19:19] **Adam:** Yeah, the, I could see it functioning, like over screen, not screen share, but like get on a video chat and, I guess you would probably screen share just to, so the other person can look over your shoulder, like they would do if you were in person. but, and to your point about pushing broken code, I think that like, if you and I were pairing on something and Ben and Tim were pairing on something and they're saying.

[00:19:38] **Adam:** as long as they don't depend on each other directly,we could be working in separate branches and just merge them in when the features are done and that way you can push your code and you can share that code, with each other remotely, working remotely without pushing it into like, say Maine for it affects everybody.

[00:19:55] **Adam:** so in that regard, I think that is fine networks. That's potentially a good thing. But the other thing I was going to ask you was,said that, it, you can see how it's beneficial when everybody's clicking and if somebody's having an off day it's bad, like

## [00:20:10] The Benefits Of Pair Programming

[00:20:10] **Adam:** what are the benefits that you feel

[00:20:11] **Adam:** like you got from doing this from your relay race programming or pair programming

[00:20:15] **Carol:** And no, I never get stale. I never get stalled because the minute one of us is like, Hey, I've been on this half the day and we've not made any

[00:20:24] **Carol:** progress. Everybody knows you're immediately like, okay, I don't want to them looking at my code going, you didn't make any progress. Like I want to be able to say, Hey, I'm not really sure where to go with this.

[00:20:34] **Carol:** So let's talk about it. And we resolve things way, way sooner than if I was just doing this whole effort by myself. Plus it gives me the mindset of three other people to think through the same thing on three I'm thinking through. So we have four people trying to solve, ultimately the big picture, even though maybe we each have our own little box that we're working in, they all have to still, unite at the end to make this application.

[00:20:57] **Carol:** So I get their view of everything they're doing and how it's going to

[00:21:00] **Carol:** integrate with everything I'm touching.

[00:21:02] **Tim:** So it sounds like you guys have like sort of a rubber duck system, right? It's a built-in rubber duck kind of system where people can help each other out. But what I don't what I imagine the benefits of true pair programming is you have two people at the exact same time, actively engaged their minds on it.

[00:21:21] **Tim:** Right?

[00:21:22] **Tim:** So you have, so in real time you have a person who's driving. A lot of times you just start typing out code. Do you think that's the best way to do it in the times in the. Troubleshooting type situations where we've done that, someone's looking at me and they're like, oh, you named that argument wrong, or you caught this wrong, or you probably should break that up into multiple

[00:21:42] **Tim:** functions rather than one.

[00:21:43] **Tim:** And that's helpful. What you described your relay race programming. I don't see that

[00:21:47] **Tim:** you get that right. Cause you're going to run it for, I mean, how long is how long you writing for

[00:21:52] **Carol:** how long

[00:21:52] **Carol:** I'm

[00:21:52] **Carol:** writing code for how long does a project last?

[00:21:55] **Tim:** How long you coding for it as stretch? How long are you driving and

[00:21:58] **Tim:** writing code before you

[00:22:00] **Tim:** hand it off to someone else?

[00:22:01] **Carol:** I mean like maybe four hours I have some code in and then I push it

[00:22:04] **Carol:** up

[00:22:05] **Carol:** and

[00:22:05] **Adam:** So, but then you

[00:22:06] **Adam:** push and somebody else is.

[00:22:07] **Adam:** taking over on that. Are you moving to another thread and working on somebody else's

[00:22:10] **Adam:** that

[00:22:11] **Tim:** Are you had to stop and explain

[00:22:12] **Carol:** No,it depends. I mean, it really depends on the end on how the day went. I mean, I could pick up and look at something else or I could keep going on what I'm on. But the fact is that when I come in, I can either start working on that or I can look at what someone else put up and go work on what they were doing.

[00:22:26] **Carol:** So me, if I still have work to do, then I can go back to mine. But like, if my buddy's

[00:22:30] **Carol:** like, Hey, I'm going to wrap up this piece that you were doing and I'm going to see how that works. Cause I'm curious, he can do that. And then when I come in,

[00:22:36] **Carol:** it's just

[00:22:37] **Carol:** there and I'm like, oh yeah, that's smart. I like that.

[00:22:39] **Carol:** Like how you did it.

[00:22:40] **Tim:** I'm assuming there's lots of tests there as well.

[00:22:43] **Carol:** Yeah. Lots

[00:22:43] **Carol:** of.

[00:22:43] **Carol:** tests.

[00:22:44] **Carol:** Lots of.

[00:22:44] **Adam:** I was going to say, I think that the going back to this, like traditional definition of paraprogramming switching, drivers every couple of minutes, I think that, would be particularly well-suited for TDD. Right. I've been trying to read this TDD book and I'm dragging my feet on it because I'm not

[00:22:58] **Adam:** particularly enjoying it, but I'm forcing myself through it.

[00:23:02] **Adam:** And the idea

[00:23:03] **Carol:** Test driven development for anyone who doesn't know what TDD

[00:23:06] **Tim:** sorry. with TD.

[00:23:08] **Carol:** you know me.

[00:23:09] **Adam:** the idea of like, okay, before we start on this feature, somebody has to write a test and then maybe you swap seats and, and then you implement the feature and you swap back and write the tests. And I could see going back and forth like that. a would work really well, kind of like,encourage you to do better TDD and also having those clear break points of, okay, we've finished the test

[00:23:28] **Adam:** for now.

[00:23:29] **Adam:** Now we need to go work on the code. That would be like clear indication of time to swap

[00:23:32] **Adam:** seats too. So they kind of would work well.

[00:23:34] **Adam:** They

[00:23:34] **Adam:** would dovetail nicely.

[00:23:37] **Tim:** Dovetail

[00:23:37] **Tim:** that's a join the joinery. So I, yeah, so, I mean, I imagine if you have written

[00:23:42] **Tim:** good tests upfront, actually first, then maybe the person who's, you're handing it off to knows what the outcome should be.

[00:23:50] **Carol:** Yeah. Because they can't change too much to break what you've already done, because if they get the break, they have to figure out, is it a good break? Like, okay. That test was written bad. And we actually went at it the wrong way, or I

[00:24:02] **Carol:** need

[00:24:02] **Carol:** to change what I've done because I need

[00:24:04] **Carol:** to make sure I don't break the test,

## [00:24:06] Coordinating Pair Programming

[00:24:06] **Tim:** Okay. Yeah. So I, yeah, I can, I guess I can kind of see that I think traditional pair programming, the benefit is there's not a whole lot of need for stopping and saying, what are we doing? And communicating back and forth and figuring something out, which it sounds like you have to do occasionally.

[00:24:22] **Tim:** Right? You have to explain, what's going on. You're if you're both there in the moment, looking at the same code

[00:24:28] **Tim:** and actively talking about

[00:24:29] **Tim:** it, you're doing it at the time.

[00:24:31] **Carol:** And I am, you mentioned like screen sharing your code. We actually use live, share and vs code. So, you know,you can just see everything going on and you can just switch back and

[00:24:41] **Carol:** forth

[00:24:41] **Carol:** between the stream of the code versus, what you're riding over in

[00:24:44] **Carol:** your

[00:24:45] **Carol:** window. So

[00:24:46] **Tim:** Have you tried that? Have you guys tried that to say, Hey, let's just live, stream our code together

[00:24:51] **Tim:** and actually try real. I don't want to diminish what you're doing here, but it's not pair.

[00:24:58] **Carol:** My relay programming is what we'll call it. Yeah. no we have with a couple things. so whenever we create our plant, UMLS whenever we do that, we do them over live share. So we set on a call and someone's coding it while we're actually creating the design of everything. And we're breaking out the entire diagram of how the flow is going to work and putting in all the layers we do that over live.

[00:25:20] **Carol:** So the initial build up front, we do, and obviously that's writing code, but it's slightly different than writing the application

[00:25:25] **Carol:** code, but.

[00:25:26] **Adam:** One of the things you had said early on was that, because you had such a good plan going into the development process that kind of helped you through it. Do you think that pair programming is, hindered by not having a clear

[00:25:40] **Adam:** spec leading into the programming process?

[00:25:43] **Carol:** Absolutely. If you don't know what you're doing, it's hard enough for one person to accomplish unknown job had put four people on it and you're just gonna butt heads the

[00:25:52] **Carol:** whole time, because you have no clear goal of where you're going or any idea how to accomplish unknown said goal.

[00:25:58]

## [00:26:00] Code Ownership

[00:26:00] **Ben:** I think the thing that trips me up the most is this idea that someone would just finish work that Carol started or that Carol finished work. Someone else started. I feel like I'm just an emotional child when it comes to my code and I have this extreme sense of ownership.

[00:26:18] **Carol:** Yep.

[00:26:18] **Ben:** I, and if I came in one day and someone was just like, oh, I saw some of the stuff you're writing.

[00:26:22] **Ben:** So I just

[00:26:23] **Ben:** added a

[00:26:23] **Ben:** bunch to it. I'd be like,

[00:26:25] **Carol:** so good, good point. Like circle back to that. That's what happened up front. When I switched over and started working like this, because I've never done this before in my life. I've never worked like this. It was an insult. I immediately went, my code's not good enough. Why are you even looking like what's going on here?

[00:26:44] **Carol:** Like I messaged someone and was like, did I not do something right? And it was like, no, I just wanted to keep it going. I was like, oh, okay. So I can calm down. My blood pressure can drop a

[00:26:55] **Carol:** little bit, but there's like the attachment to it. So it took me a long time to go from it's mine to it's my teams.

[00:27:03] **Carol:** This is my

[00:27:04] **Carol:** teams. so when someone does good, nobody does good. Our entire team does.

[00:27:11] **Carol:** It's a whole different mindset and I love it. I will say I love

[00:27:16] **Carol:** it's. I don't want to go

[00:27:17] **Carol:** back to just coding on my own always all the time. Again, I love working with people like this, like where we're sharing the same effort and the same code that we're trying to deliver.

[00:27:29] **Ben:** I think maybe something that gets in my way is I am, I'm not good about asserting hard suggests now I don't know how to say this the right way. I don't, I am not good at telling people that their code could be better because I have so much insecurity about this idea that I have a better way to do something.

[00:27:48] **Ben:** So I will look at code that someone else wrote. And I, and what I could say in my own mind is I would never write it this way if I were the one writing it, but I don't have confidence to tell you that. I think you can improve it based on my feelings, because I'm always like, it's working. I couldn't point to something and say, this is going

[00:28:08] **Ben:** to cause a problem

[00:28:09] **Ben:** necessarily in the future. I just have.

[00:28:11] **Ben:** That there's

[00:28:12] **Ben:** some problems here.

[00:28:13] **Carol:** It could be more efficient or

[00:28:15] **Carol:** something. Yeah.

[00:28:16] **Ben:** I dunno, I

[00:28:16] **Ben:** just,

[00:28:17] **Tim:** Or you could just ask, why are you

[00:28:18] **Tim:** doing it that particular way? Not that you're

[00:28:20] **Tim:** criticizing. And can you explain to me, I don't understand

[00:28:22] **Carol:** We, we all know what that really means to him. Yeah.

[00:28:27] **Carol:** We

[00:28:27] **Carol:** all know. Yeah.

[00:28:28] **Ben:** well, so, and I think because I have so much insecurity about giving people's strongly worded feedback. I don't know what the right term there is that I think it, because of that, I don't play well with others because I don't know how to, I don't know how to negotiate that sort of workflow. So I it's like I have to have ownership over the whole code because I don't know how to help other people improve their code.

[00:28:52] **Ben:** If I don't agree with it. I don't know. I do, as Tim was saying in the last episode, I will disagree

[00:28:57] **Ben:** and

[00:28:57] **Ben:** commit instead of giving people like real actionable advice,

[00:29:00] **Tim:** No, you will avoid disagreeing and

[00:29:02] **Tim:** commit. That's what I

[00:29:04] **Carol:** let

[00:29:04] **Ben:** will quietly disagree and

[00:29:07] **Tim:** in your own mind.

[00:29:10] **Carol:** And see

[00:29:10] **Carol:** I'm okay with getting those questions. And I think I am more like you on that point. Like, I don't want to ask people every time. Like, why did you do it that way? Or what was your approach to that? I just kind of accept it and go on, but I am, that's not the case with almost every other engineer on my team.

[00:29:26] **Carol:** They will all ask and they'll ask in the PR where everyone's on it. Like, why did you do it this way? And unlike you could have just messaged me, now everybody's going to

[00:29:35] **Carol:** know,

[00:29:37] **Adam:** that's a, that's actually a really good thing that I like to bring up. Every opportunity that I get, which is if you have criticism for

[00:29:42] **Adam:** somebody, bring it to them in private. If you have praise for somebody, bring it to them.

[00:29:47] **Carol:** oh, let's see it like

[00:29:48] **Carol:** that.

[00:29:48] **Ben:** I like that.

[00:29:50] **Carol:** So yeah. I love this thing that we're doing. I just want to say that, like, what we're doing is really fun and it's really

[00:29:56] **Carol:** helpful until like, I

[00:29:57] **Carol:** don't want to

[00:29:57] **Carol:** talk to

[00:29:58] **Carol:** someone

[00:29:58] **Carol:** that's

[00:29:58] **Carol:** not

[00:29:59] **Carol:** so great.

[00:30:00] **Tim:** It's certainly interesting.

## [00:30:01] Common Pitfalls

[00:30:01] **Tim:** So going back to like, agile alliance.org, where they're talking about, they talk about some of the common pitfalls. The funniest one, I think is the last one. They said he can't force it upon

[00:30:11] **Carol:** No.

[00:30:12] **Tim:** especially if there's relationship issues, including the most mundane, such as personal hygiene, standing next to him with someone who smells like butt all day.

[00:30:22] **Tim:** Yeah. If there's get yes, all those first before you can, effectively pair program,

[00:30:26] **Adam:** on the after show, when we had Sean on, we talked briefly about TV and the TV show, billions, and just last night we watched. So because of that, my wife and I have started watching it. And we watched the episode where the lady is like, do you still have emergency deodorant in your office? And he's like, yeah, do you need some?

[00:30:41] **Adam:** And she's like,

[00:30:42] **Tim:** you do.

[00:30:47] **Carol:** Thank you.

[00:30:49] **Ben:** The other thing that I think would make pair programming challenging from my particular way to work is that I find that I have to just sometimes stare off into space or stare at my desk or stare at the screen, and then just kind of go into thinking mode for a few minutes, in order to wrap my head around a problem or to try and kind of game out some possible approaches in my head.

[00:31:13] **Ben:** I feel like the way I work is almost I create this buffer in my head of the stuff I want to create. And then I spend like the next 15 minutes trying to get it out of my head and onto the screen. And once that's done, then I go back to buffering code in my head for awhile. And then I bought vomited out onto the screen again.

[00:31:31] **Ben:** So I have these like

[00:31:32] **Ben:** starts and fits

[00:31:33] **Ben:** w like fits and stops, but I don't know what the right

[00:31:35] **Ben:** term is. It starts in fits. Yeah.

[00:31:38] **Tim:** Parts and pits.

[00:31:41] **Carol:** and that's okay. You just have to communicate that and did, that's how I've worked with one of my best friends and he will message me and be like, Carol. Shh. I need one minute. I will message you when I comprehend everything you

[00:31:53] **Carol:** just said. I was like, all right, cool. I'm going to go make coffee. Think about

[00:31:56] **Carol:** it.

[00:31:58] **Tim:** that's why I been, I, what I struggle with when I'm starting something particularly that's kind of open and not, I just try to figure out what is the smallest unit of task that I can accomplish. Right.

[00:32:13] **Tim:** It just get, can I do a call to something? Can I get a return on something and then build from there?

[00:32:19] **Tim:** But one of the other things that, this article is looking at here talks about is that, and maybe it's kind of what Carol was talking about is that the driver. And possibly both programmers are expected to keep a running commentary, so kind of programming out loud. So the driver gets silent and just starts going on the keyboard.

[00:32:37] **Tim:** the navigator would be like, Hey, talk to me out loud. are you

[00:32:40] **Carol:** are you

[00:32:40] **Tim:** What,what are we doing here? What are you trying to accomplish with this function or

[00:32:43] **Tim:** this

[00:32:44] **Tim:** thing you're doing?

[00:32:46] **Carol:** not everybody can do that. Some people need the right code would like their headphones in music Blair. And like, they can't have a conversation, a dialogue while they are actually writing code. So, not for everybody,

[00:32:58] **Carol:** but if it is for you, that's great.

[00:33:00] **Tim:** And it does address the, they talk about the doubling the cost, which immediately when my mind that's the first thing that Kevin's and they said that it, it's a misconception. At quading programming with typing,

[00:33:12] **Tim:** which that is

[00:33:13] **Tim:** very true. A lot of, I can't tell you how many times I've typed a whole lot.

[00:33:16] **Tim:** And then when

[00:33:16] **Tim:** said back, back, back, back, back, back, back control the control Z control Z delete, 40 minutes of typing gone. And then I realized I can do it and five minutes of typing. So yeah, that's what you're hoping to avoid with pair programming is that you have someone else who is the navigator is going, wait a minute, we're doing way too much boiler plate here.

[00:33:38] **Tim:** we're, you're solving the same problem, multiple places. let's reevaluate what we're doing and addressing it quickly because you have someone else kind of being the immediate code quality control in real time,

[00:33:52] **Carol:** Yeah. It brings it back in

[00:33:53] **Tim:** but both have to be actively engaged. You can't have just one

[00:33:56] **Tim:** person, checking their

[00:33:57] **Tim:** emails while

[00:33:58] **Tim:** someone else is typing.

[00:33:59] **Carol:** no, you have to be on the same project. Definitely. If you're actually doing what you're talking about or where's this. At points where like that, but not to that level. the other thing is you said the cost, right? I can't tell you how many times I have not here previously been told, we'll just throw more people at the problem and you'll get it done faster.

[00:34:18] **Carol:** That is not what this is about. Like, this is about getting it done right. And the most effective way, and it's building it together. So it, it doesn't make it any faster because you put two people or four people on it. It you're still going to have the same deadlines, the same delivery dates,

[00:34:33] **Carol:** but

[00:34:33] **Carol:** I feel like the quality is better.

[00:34:35] **Carol:** Cause there's multiple eyes on it at all times

[00:34:37] **Tim:** Let me, I mean, if I had someone standing over your shoulder all the time and just told me whenever I spelled the word arguments wrong, I would increase by like 30%. I had so many times I'm like debugged an issue where I just spelled a variable slightly differently. And my, I didn't catch it.

[00:34:55] **Adam:** Well, I mean, there are spellcheck,

[00:34:56] **Adam:** plugins for vs code or you're not

[00:34:58] **Carol:**

[00:34:58] **Carol:** he uses that other thing.

[00:35:00] **Tim:** Yeah. I mean, he's that other thing I'm waiting for?

[00:35:01] **Tim:** The other thing to go to

[00:35:03] **Tim:** be as

[00:35:03] **Tim:** scared.

## [00:35:04] Reviewing Code

[00:35:04] **Ben:** We worked. we had a big project at work maybe a year and a half ago. And on my team, most of the projects are one person. So if we have four people on our team, we're typically working on four completely separate projects. We had this high priority project that we had to get done. So we put three people on it at the same time, which was like unprecedented for our team.

[00:35:25] **Ben:** And we rocked it out in like a week and a half, which was crazy because of the amount of stuff that it had to do. but I'm looking at the code it's kind of bananas. Every, each person's code that they wrote is so wildly different than the other person's code, just in terms of general practices and methodology.

[00:35:47] **Ben:** So you'll be working in one part updating some. I'm talking about like a year later now, and then you have to go into the other person's code that they wrote. And you're like, oh, this is so different now. Like

[00:35:58] **Ben:** I have to

[00:35:58] **Tim:** it.

[00:35:59] **Ben:** it.

[00:36:00] **Ben:** and it's not even, and I was going to make a joke about linting, but it's not even, it's like, that's not even the kind of stuff that linting would capture.

[00:36:06] **Ben:** it's really just like fundamental.

[00:36:08] **Ben:** Yeah,

[00:36:09] **Adam:** if somebody really prefers functional programming, somebody really hates

[00:36:12] **Adam:** functional.

[00:36:12] **Ben:** yeah, yeah, exactly. That kind of

[00:36:14] **Ben:** stuff. So it had one person taking the time to write all of this stuff and granted it would have taken, let's say three times as long for sake of discussion, it would have had a uniformity and it would have been able to fit together in a, and I think a much more seamless way.

[00:36:30] **Ben:** So you lose time, but you, I think it probably would have added to the maintainability. Yeah. So, but I will say now going back to kind of what Carol was saying about, you're constantly having to check in with

[00:36:42] **Ben:** other

[00:36:43] **Ben:** people and review the code and talk about the code. We didn't do any. We basically had some

[00:36:49] **Ben:** upfront design said, you go do this, you go do this and I'll go do this.

[00:36:53] **Ben:** And then we merged it all together. And if it worked from a user experience standpoint, we're like good next project. so we didn't have that refinement or review step, which I think probably would have helped a

[00:37:03] **Ben:** lot,

[00:37:03] **Ben:** but we were just trying to, we were just trying to rip it out as fast as we could.

[00:37:08] **Carol:** Yeah. I mean, we would have to sit and talk about just like our model of everything. So we'd like be in our open API file, like putting in our model changes and as I'm changing how our author saving things and what we're using for it and what I'm actually using in like email, body contents and things like the other developers needing to know, because he's handling all the notification and queue side of everything.

[00:37:28] **Carol:** So he's like, I need to know the model changes. I mean, we just have to constantly be in communication about what's going on and why. And there were times he would add things and I'd be like, I don't know if we actually did this. Let's think about it. We'd add it and play with it for a little while and be like, yeah, you don't need it.

[00:37:43] **Carol:** Or I would add something and then three of us be like, yeah, this doesn't make sense. Take that back out. And we're going to go a different way with it. And if I would have been doing it all myself, those would have been laid in at the final end of it. You're stuck. There's no one doing some of that stuff.

[00:37:56] **Carol:** When you get to the last bits of the code, cause you've done wound everything. So, so much together that it's needed. Whereas if two days into it that this doesn't make sense, you can undo it and change your plans.

[00:38:07] **Adam:** Something that I think you said in there, and I want to give you credit for that, but that maybe got lost in some of the other stuff you said, was that by pairing, It makes code review easier because

[00:38:18] **Adam:** you've seen it before. Right? you are already familiar with this code. And so by like, if maybe four people are pair programming,on, the same thing at different times or whatever, and you're all really familiar with the code, then you just have to kind of

[00:38:31] **Adam:** give it a quick ones over all of you.

[00:38:33] **Adam:** And if everybody's happy, then that's.

[00:38:35] **Carol:** Because you've already functionally designed it together. the functionality in the core layout of that.

[00:38:40] **Adam:** yeah, that, that was a non-obvious benefit

[00:38:43] **Adam:** to me. And I wanted to pull that out and

[00:38:46] **Carol:** Thank you. Cause yes, that's a good one. Yeah.

## [00:38:49] Pair Pressure

[00:38:49] **Ben:** Do you ever find that pair programming ends up making the

[00:38:52] **Ben:** code more complicated? And let me caveat that with some further explanation, which I think if I were to write code on my own, I'd be willing to make. More shortcuts and calculated. Trade-offs like I might wrote code. That's not great with the idea of kind of going back to what you were saying, where I don't know if I'm going to need this in the long run.

[00:39:14] **Ben:** I want to get something in there just to start playing around with it and I'll come back to it or refactor later if I need to. And I wonder if, when you're pair programming, cause you have someone else's eyes on your code the whole time. Would that person jump in at at that point and say, Hey, actually that's not going to be very flexible or maybe we should refactor it to be something that's more dynamic in the future.

[00:39:36] **Ben:** And you end up kind of investing more into the quote unquote, elegance of the

[00:39:41] **Ben:** code, maybe

[00:39:42] **Ben:** too early. Does that ever happen?

[00:39:44] **Adam:** Architecture, astronauts.

[00:39:46] **Carol:** Yeah, I am the

[00:39:47] **Carol:** person who over-complicates things and thinks about the problems that can and might happen that one time in the future. So I overcomplicate things up front and they actually backed that out. They're like, you are going too far into this, and this is a one-off error. We're just

[00:40:03] **Carol:** gonna, catch the error and it's okay.

[00:40:05] **Carol:** If

[00:40:05] **Carol:** one time in a year this happens. it's not worth the amount of code you're putting into it. So for me personally, it, it goes the opposite way. they reign me

[00:40:12] **Carol:** back in.

[00:40:14] **Adam:** Ben while you were describing the situation. I couldn't help, but think that, there was like some that it was kind of maybe motivated by like a

[00:40:20] **Adam:** fear of judgment by the person that you're pair programming with. Right. So like

[00:40:25] **Carol:** Oh,

[00:40:25] **Carol:** I don't think I'm

[00:40:26] **Adam:** maybe not that,

[00:40:26] **Adam:** maybe not that, that harsh, but like, they're like, you're thinking in your head that they're going to be looking over your shoulder and thinking, oh, this is the wrong way to code it.

[00:40:35] **Adam:** Right. There's a right way and a wrong way. And you're doing it the wrong way sort of thing. But I think that the opposite could also be true, right? Like that person could be there helping you

[00:40:44] **Adam:** recognize this is a situation we don't need it twice yet. Let's not

[00:40:47] **Adam:** make it reusable.

[00:40:48] **Ben:** right, right. Why? And I think it comes back to what Tim was saying earlier about having to have that constant two-way communication.

[00:40:55] **Adam:** yeah.

[00:40:56] **Ben:** Where I think what you're saying is I have an internal dialogue and I'm afraid that the other person is not going to know what I'm trying to do or not know what I'm trying to think, which is probably what I would end up doing.

[00:41:07] **Ben:** But if I were to actually just stop and say, Hey, I'm going to write some shifty code here for a minute, because I don't know what it's going to be like in the long run. Like let's readdress this tomorrow. Once we get a better sense of how it all fits together. if I just took a minute to actually say that out loud and get everyone on the same page, and then I think we could

[00:41:24] **Adam:** Yeah,

[00:41:24] **Adam:** that sounds like exactly what you should be verbalizing during this pair program. I mean, I'm not an expert in pair programming, but based on what we've talked about here tonight, the, the expectation that you're going to sort of

[00:41:36] **Adam:** narrate your coding process. That sounds like exactly what you

[00:41:39] **Adam:** should be saying.

## [00:41:40] Ping Pong Programming

[00:41:40] **Tim:** Yeah. Have you heard of ping pong programming?

[00:41:44] **Tim:** a variant of

[00:41:45] **Adam:** that was a term that I threw out there when we were discussing

[00:41:48] **Adam:** the possibility of this topic and our, experience levels.

[00:41:52] **Tim:** Yeah. So, I mean,

[00:41:53] **Tim:** It's apparently. So if you combine pair programming with test-driven development, you have one person write a test and then the other person write the code. And then, you either, either see if you fail or pass it. And then you, whenever you switch over, you have the keyboard back over.

[00:42:10] **Tim:** Now they write the none of the tests and you write the code or vice versa. It can swap out. So that's what they call ping pong pro, which I think is probably good for like, maybe if you have a beginner with someone who's more experienced, right. That experienced person writes a test and they go, all right, see if you can pass a test.

[00:42:27] **Tim:** And then the big, the beginner goes and tries it. And if they struggle, you're there to talk, help walk them through it. But it's an interesting, I mean, I'm not opposed to this whole idea. It's just like, I've never been in an organization where this was a incurred.

[00:42:41] **Carol:** Yeah. Yeah, this is the first time

[00:42:43] **Carol:** for me.

[00:42:44] **Adam:** I'm going to do it again. Tim, something you just said that I think maybe wasn't quite as obvious as it could have been was that this is a good opportunity for mentorship.

[00:42:52] **Tim:** For sure. Yeah.

[00:42:53] **Adam:** Yeah.

[00:42:54] **Adam:** Or good technique from

[00:42:55] **Tim:** it and that, so I would say we

[00:42:58] **Tim:** probably did something akin to pair programming. We have new employees, right? So someone just stands over your shoulder and you talk out what you're doing. And then sometimes I'd swap out with them and say, all right, you, you hop on the keyboard and fix this, w what do we need to do here?

[00:43:11] **Tim:** And then walk them through it and then just go back and forth. But I mean, that, wasn't a permanent paradigm, right? That was sort of, the first month of employment for them to get them up to speed.

[00:43:22] **Adam:** just when you said, like, when you have a new person on the team and you're going to stand over their shoulder, as they're starting to program, I just couldn't help with picture, and run in Stimpy. The guy that would be like, oh,

[00:43:31] **Adam:** isn't that cute? But it's wrong.

[00:43:36] **Tim:** So we'll just stay at you.

[00:43:37] **Tim:** So good. Hello, Clarice.

## [00:43:41] Interruptions And Availability

[00:43:41] **Ben:** What about the, just practicalities of being available for someone else? So we all work from home at least

[00:43:49] **Ben:** currently, and there's the dogs coming in and out or needs a walk. Or my wife needs to talk to me or I get pulled into a slack conversation about something that's urgent or I'm in the middle of a deployment.

[00:44:01] **Ben:** And that's having issues. I mean, there's a lot of, there's a lot of just background noise of the day. And it's one thing. If it's just one person and they get sidetracked, but if you get sidetracked and there's someone else just sitting there waiting for you to come back that's, it seems very unfair to them.

[00:44:17] **Ben:** So maybe you just have to be super disciplined. you flip your, your on

[00:44:21] **Ben:** air light and no

[00:44:22] **Ben:** one can come into your office and talk to you about anything.

[00:44:25] **Carol:** So we don't, we are, very, let me see how this. We push for no shoulder tapping. So if I'm working through the day, it's very rare that my director of engineering, my PMO or my lead is going to shoulder tap me for anything. We plan ahead of time. So the emergencies, if you're a Zen master, you're going to get their emergencies and you know, they're coming.

[00:44:48] **Carol:** If you're the lead year, you're going to know. And if you've pushed a project out, then you know that they could land on your plate. But other than that, we don't do a lot of shoulder tapping. So that does make it good. And if I do hit a point where I'm blocked, I say that I'm like, Hey, I really need like a set of ears or a pair of eyes on this right now, because I am at a point where I'm blocked.

[00:45:09] **Carol:** And if the person I'm directly like working with there's four or five of us in it right now. So if someone isn't like that, someone who isn't immediately on this with me, someone else can jump in and go, Hey, let's just off. So, I mean, I haven't had a point where I've been blocked, if so I go read for an hour and, wait for someone to come back and then I'm like, all right, I have a better idea of at least my questions now.

[00:45:31] **Adam:** So you gave a list of people there that will definitely not come tap you on the shoulder. Does that you didn't say, and I

[00:45:38] **Adam:** want to know, does it include your peers, the other people working on the same project as you?

[00:45:43] **Adam:** The

[00:45:43] **Carol:** no me. if before on the same project we slack each other all day long. Hey, what do you think about this? And that's where I told you, like my best friend is like, Hey,

[00:45:51] **Carol:** just a minute. I need to think. And I'm like, cool. Is this like coffee think, or I'll catch you after lunch thing. And he'll tell me like, upfront, here's where I am.

[00:46:00] **Carol:** I'm in the middle of something, like whatever it is, we just, we're pretty open about timing on things.

[00:46:06] **Adam:** I think it takes some time to build up that kind of rapport with people, but it's very valuable when.

[00:46:11] **Carol:** absolutely. In

[00:46:12] **Carol:** this team is very open with each other. So that

[00:46:14] **Carol:** helps. So.

[00:46:16] **Ben:** I definitely get interrupted all day long.

[00:46:19] **Carol:** I used to at all my previous jobs, I would come home feeling like I didn't get any work done because all I did was just handle everybody else's stuff or answer questions for people. So then I would want to write a bunch of code when I got home, because I didn't feel productive. I don't have that.

[00:46:33] **Carol:** Now. I actually have a good setup to where I don't get shoulder taps a lot.

[00:46:38] **Ben:** I think going back to my failure at the top of the show, I think part of that, part of why I'm feeling so rundown lately is my team is basically me at the time. and because of that all week, we can't, there's no one to absorb new tasks other than me, and it's not even just absorbing the new tasks, it's absorbing the categorization and backlogging tasks that I'm not even going to work on.

[00:47:03] **Ben:** At this time. I was in a call earlier this week, like a status call for a particular project. And it's a project I haven't even started. And they're asking me for an update. And I said, well, the good news is I just finished a project, which means that I have only one more project ahead of you guys in my queue.

[00:47:19] **Ben:** So it's, it's, been, it's been exhausting daily.

[00:47:23] **Carol:** Well, I hope it gets better.

[00:47:25] **Ben:** Yeah. I think it's the fall. Right? we're deep into the fall now by a day. So pretty excited about that. I'm excited to whip out my sweatshirts soon.

[00:47:34] **Adam:** My lawn is already covered in leaves.

[00:47:36] **Ben:** Yeah,

[00:47:37] **Ben:** this is the good season.

[00:47:38] **Tim:** It was a nice crisp day here in Georgia.

[00:47:41] **Carol:** Yeah,

## [00:47:42] Patreon

[00:47:42] **Adam:** okay. Well then I guess this is the part of the episode where I

[00:47:45] **Adam:** let you know that this episode of Working Code is brought to you by terrible fruit-based puns

[00:47:50] **Tim:** You're welcome.

[00:47:51] **Adam:** and listeners like you. If you like what we're doing here, you might want to consider supporting us on Patreon. You can do that at patreon.com/WorkingCodePod.

[00:47:59] **Adam:** and we are grateful for every single one of our patrons. We are super grateful for every single one of our listeners. Thank you guys for listening. in exchange for the money they're giving us, we try to give our patrons something in return. So everybody gets an invite to our Discord server and we like to hang out and chat.

[00:48:12] **Adam:** We spend a lot of time bike shedding on, linting today, but manual

[00:48:16] **Adam:** linting and, so just that's the sort of thing you can expect in there.

[00:48:20] **Tim:**

[00:48:20] **Tim:** don't forget gain It We had a great time. This last game night we played everyone is John,

[00:48:25] **Adam:** I'm really sad that I

[00:48:26] **Adam:** missed that.

[00:48:27] **Carol:** It was really good.

[00:48:28] **Tim:** it was fun. Adam Cameron, his goal was to try to get, to teach a yoga class. And it's like a, it's like a, one page role-play game. It's super simple to play. it was really fun.

[00:48:37] **Tim:** We had.

[00:48:38] **Carol:** We have to play again.

[00:48:38] **Carol:** Yep.

[00:48:39] **Adam:** I'm looking forward to it. so I want to make sure that we send a special thank you to our top patrons,

[00:48:44] **Adam:** Monte and Peter. Thank you, guys. especially for your support.

[00:48:47] **Tim:** Yeah, Monte. And you achieve world peace during,

[00:48:50] **Tim:** during every buttons, John. So

[00:48:51] **Tim:** congratulations.

[00:48:53] **Adam:** Good job. I guess I have no idea what that means, but okay.

## [00:48:56] Thanks For Listening!

[00:48:56] **Adam:** and for everybody else at paying for podcasts, isn't your thing. That's not a big deal. We appreciate you taking the time to listen. and there's, if that's something you're interested in, there's free ways that you can help us out too. You could share the show with your friends and your coworkers, or you can leave us a rating and a review on apple podcasts or wherever you get your podcasts.

[00:49:13] **Adam:** Please send us, show, topics and questions on Twitter or Instagram, and you can find us there @WorkingCodePod, or you can call us and leave a message at 512-253-2633 that's 512-253-CODE.

[00:49:25] **Adam:** We'll catch you next week. And until then

[00:49:28] **Tim:** Remember guys, your heart matters. Even if you fail to roll for initiative on everyone is John.

[00:49:37] **Adam:** again, I have no idea what that means, but it sounds

[00:49:39] **Adam:** funny.

[00:49:39] **Carol:** You

[00:49:39] **Carol:** will

[00:49:40] **Carol:** learn

[00:49:40] **Tim:** you'll find

[00:49:41] **Adam:** Yup.
