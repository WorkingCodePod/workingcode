---
title: "163: Exposing Yourself, to New Tech"
description: "Is dabbling in new technology really moving the needle? Does learning a little of this and little of that really make for a more robust engineer? Or, is there more value to be gained from depth of understanding?"
date: 2024-01-24
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/163-exposing-yourself-to-new-tech/id1544142288?i=1000642768885"></iframe>

In web development, we tend to hold learning as a virtuous activity that's worthy of our spare time. In fact, there can be a lot of pressure on us to always be learning; and, to some degree, those of us who _don't_ ride the wave of cutting-edge tech are "othered". But, is _dabbling_ in new technology really moving the needle? Does learning a little of this and little of that really make for a more robust engineer? Or, is there more value to be gained from depth of understanding? And, at the end of the day, does the biggest impact on what we know actually come from switching jobs and joining new teams?

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/163-exposing-yourself-to-new-tech.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** Now, if I can bring up ColdFusion for a second, because.

[00:00:03] **Adam:** What's that?

[00:00:04] **Ben:** It's a cutting edge web technology framework,

[00:00:08] **Adam:** Is that, that's because it's, it's falling apart. So all the edges are sharp.

[00:00:13] **Carol:** that's a good one. That's a real good one. Yeah.

## [00:00:36] Intro

[00:00:36] **Adam:** Okay, here we go. It is show number 163, and on today's show we're gonna talk about exposing yourself. To new tech. New, that's right. I said it. New tech. but first, as usual, we'll start with our triumphs and fails. It would be Tim's turn to go first, but he has an excuse to absence. He's busy casting Magic Missile at the darkness.

## [00:00:53] Adam's Triumph

[00:00:53] **Adam:** So, I guess that makes it my turn to go first. and I'm gonna start us off with a triumph. today, my team and I spent some time, what is it, what is it when you're pairing and there's three of you? Is it, is it triad ing? I don't know, whatever. The, the three of us got together and we broke ground on our SvelteKit rewrite of our monolith, our like, legacy monolith.

[00:01:15] **Adam:** so the design system is like close enough to done now that, that we're able to like, you know, sort of try to use it. And there's a bunch of things, problems that we have to solve, before we can actually start like writing app code. You know, you've got like, you got to set up the sessions and you got to set up the database access and I've got to like make it multi tenant and you got to have it in a container.

[00:01:36] **Adam:** And so like we're working on solving all of these problems. but, ground was broken. The first shovel full of dirt was moved off to the side. and it feels good. Super excited.

[00:01:47] **Ben:** I mean, when did, so how long ago did you start working with Svelte? That was like two years ago.

[00:01:53] **Carol:** Like a hundred episodes ago.

[00:01:56] **Adam:** That would be about two years.

[00:01:58] **Ben:** Yeah.

[00:01:58] **Ben:** Um,You'd started with a modal window and I guess it just sort

[00:02:02] **Adam:** yeah, I mean, that was the first thing that I did that like landed in production. Yeah. And I mean, God, I hope that wasn't two years ago, but it might've been, might've been somewhere close to that.

[00:02:10] **Ben:** No shame in that.

[00:02:11] **Carol:** No, none whatsoever.

[00:02:13] **Adam:** No shame. It's just like, it would be almost sort of depressing that it took that long to go from, you know, first, first felt code in production to where I actually was aiming at this whole time.

[00:02:24] **Carol:** Well, there would, there would only be shame if you'd done nothing else.

[00:02:28] **Adam:** sure the wheels of progress move slowly.

[00:02:31] **Ben:** there you go. And I think that ties in nicely with the show.

[00:02:34] **Adam:** Absolutely it does. And I, and I've had like, you know, I said the wheels of progress move slowly.

[00:02:40] **Adam:** Well, really what's happened is the wheels of compliance move slowly, right? I've been, I spent the last year working almost exclusively on compliance stuff. So, that's really what slowed that progress down, I guess. And as I mentioned last week, you know, we had that, failure where we have to do the SAC D.

[00:02:56] **Adam:** Well, I got my SAC D done. It's we ended up deciding to just do a self signed one and not get a QSA signature, which greatly simplified the process. but that's done. So sort of double triumph for me this week.

[00:03:09] **Ben:** Well, but this was for a particular client. Is that particular client okay with the self sign situation?

[00:03:16] **Adam:** We did have to clear it with them in, in advance. the whole, and, and it's almost hilarious to me because for the last N years, we've been doing a self signed SACD. And the, the whole reason that we went down this road with compliance and SOC2 and all that, Was because they wanted a QSA signed, PCI certification.

[00:03:38] **Adam:** I think they assumed it would be a SAC D. And when we started off that process, you know, through talking with auditors, they were like, well, you know, SAC A kind of makes more sense. So we did a SAC A. And then we brought it to the, the client and they were like, yeah, no, you can interpret the requirements however you want, but we want a SACD.

[00:03:55] **Adam:** So, uh, we're, we're basically at the end of the day, they're getting the exact same thing that we gave them last year, the self signed SACD, and they're okay with it because they ultimately actually what, what it boiled down to was we told them like, look, we, we did what the letter of the law says, right?

[00:04:16] **Adam:** We. you know, we did a QSA signed SAC A and we didn't even have to do a QSA signature. We just did that because you wanted us to. And we did that out of our own pocket with our own time, when we could have been doing other things. And so now you're saying you're, you're moving the goalposts on us, sort of.

[00:04:32] **Adam:** and so if you really want that, then we'll do it, but you have to pay for it. So we were like, you know, it's going to cost us 12, 000 plus. We're just going to forward that bill right on to you.

[00:04:41] **Ben:** They're like, well, in that case,

[00:04:43] **Adam:** Yeah. So, so that's it for me. How about you, Ben?

## [00:04:48] Ben's Failiumph

[00:04:48] **Ben:** I'm going to go with a fail yumph, which is, so as we discussed in the previous episode, very recently. At the beginning of January, we announced that, my company is going to be end of life, the end of 2024. And that was a pretty huge emotional hurdle for me. I think it affected me more than I.

[00:05:07] **Ben:** Thought it would. And, in terms of work, I just, I really took my foot off the gas. I have historically prided myself as someone who really optimizes their time and I get into work and I'm working solid until I do lunch. And then after lunch, I'm working solid to the end of the day. And I feel like I've really just been someone who can stay focused and rock out tasks one after another and move tickets, point of production.

[00:05:34] **Ben:** And come this January, I just sort of was in a little bit of a cloud and I just, I started leaving work sometimes at like four 30 in the afternoon. And we usually work till six and I didn't love that, but I feel like I really needed that just mentally for my own stability. So it is a failure in that I fell away from my standard operating procedures, but I think it is also a triumph in that.

[00:06:01] **Ben:** I did what I had to do and I didn't just try to work through that and get burnt out. And I'm, I'm actually feeling much more motivated right now. So yeah, a little, a little good, a little bad, but I think ultimately it was the right thing to do because it's what I had to do to, to be healthy.

[00:06:19] **Adam:** Good for you, man.

[00:06:21] **Carol:** you think that you were okay kind of stepping back a little bit because you actually have a definite ending date now or like an end in sight? So there's only so much you can accomplish,

[00:06:34] **Ben:** Well, it's interesting. It's a mixed bag because, because there is this finite timeline now. Part of me wants to just say. What's the point of doing anything? You know, I could, I could put in, you know, an hour of work a day and just make sure that the servers don't crash for the next 12 months. Or I could do something that helps the current customers have an improved experience some period of that time.

[00:07:01] **Ben:** I could try to build maybe some sort of export tools that'll help them retain their data before it disappears. I mean, there's, I think there's, there's things that I can do and it's, it's now this tug of war in my head between, do I really care?

[00:07:15] **Carol:** Yeah.

[00:07:15] **Ben:** And can I motivate to care? It's a, it's a, it's a tug of war.

[00:07:20] **Ben:** So we'll see how it goes. It's, it's January 17th right now. I got, I got 11 and a half months.

[00:07:27] **Carol:** Well, I'm glad that you're doing it and you're feeling okay about it mentally. That's a big thing for you.

[00:07:33] **Ben:** So that's me. Carol, what do you got going on?

## [00:07:36] Carol's Triumph

[00:07:36] **Carol:** Well, I have a triumph that's going to go pretty well with our topics tonight, I think. I, passed my Microsoft Azure Fundamental Certification test this past week. So, I can, apparently, so they say, allegedly, I can tell you about infrastructure management, database management, software development, computing, networking, and storage.

[00:08:00] **Adam:** Woo hoo.

[00:08:02] **Ben:** It sounds like one of those, I don't think they have these commercials anymore, but when I was a kid, I think it was for like the DeVry Institute. It was some sort of technical college where you could go and be like, learn to be air conditioning repair man, plumber, heating repair man. And it listed like all these different things you could do.

[00:08:20] **Ben:** That's what that reminded me of. That was very nostalgic all of a sudden.

[00:08:24] **Carol:** Well, yeah, I'm happy I passed it. I was very stressed out because, it was a proctored test. So I had to clean everything off my desk, send them pictures of my desk. Be on video the whole time. If anyone spoke, you fail the test and you know, we live in a duplex. So like, you know, there are people running around, there are kids and stuff.

[00:08:43] **Carol:** I'm like, there's kids on the other side of the wall. If you hear them, they're not in my house. They're in the other house and I have a dog here. And the guy's like, that's fine. I was like, okay. So, the most stressful part was after when I needed to start having meetings and going back to work and I had nothing on my desk where it was supposed to be at.

[00:09:03] **Carol:** And every time I'd go to reach for something, I would have to go find it. And the other part of my office where I had stashed it, I was like, where are those post it notes at now?

[00:09:12] **Ben:** Yeah, the, the whole, isolation of the test is so interesting. So a guy at work just recently passed a Kubernetes certification and he had to do something very similar. He literally had to take his webcam off. He had to show people his desk, had to show people under his desk. He actually had to show them his ears to make sure that he didn't have some sort of an earpiece in.

[00:09:35] **Ben:** And it was like, he had to do something else. Like, I think maybe they even sent him a special keyboard that he had to use. I mean, it was like ridiculous.

[00:09:41] **Adam:** Wow.

[00:09:42] **Carol:** Oh, that's crazy.

[00:09:43] **Ben:** it's just a certification,

[00:09:45] **Adam:** Right,

[00:09:46] **Ben:** you're not flying fighter jets here,

[00:09:49] **Adam:** right. This is

[00:09:50] **Carol:** serious about it.

[00:09:51] **Adam:** This is just You're competent with Kubernetes.

[00:09:55] **Ben:** but it was the same kind of thing too. He had to have the video on the whole time with the sound. No one could talk. He couldn't use any, you know, anything that wasn't supposed to be there.

[00:10:05] **Carol:** They were like, don't read the questions out loud, ma'am. I was like, but I talked to myself like, how am I gonna pass this? So at one point I cover my mouth and I'm like, they're like, don't cover your mouth and speak, ma'am. I was like, oh my gosh. Like I can't talk out loud. I can't cover my mouth and talk.

[00:10:20] **Carol:** What am I supposed to do here? Anyways, that's me,

## [00:10:24] Patreon Stickers

[00:10:24] **Adam:** Alright, well, before we move on to today's topic, I guess, we have a scant few opportunities left to remind our listeners that, if you would like to get stickers, that we have these special Patreon only stickers coming up, And if you'd like to get some, then you are running out of opportunities to join our Patreon.

[00:10:43] **Adam:** so on, on January 31st, that's the deadline. Join our Patreon at any level. So you can do, I think it's 4 a month is the, the Most inexpensive level where you can support us and get stickers. if you do sign up, make sure you get your address in there. That's the only thing that we're going to use it for.

[00:11:00] **Adam:** We don't, you know, it's not like we're selling it to big botany or something. I don't know what they would do with your address, but we're not selling it to them. anyway, so yeah, join our Patreon workingcode.dev/ no. Patreon.com/workingcodepod. and, and you can sign up to get some stickers.

[00:11:18] **Adam:** so it's this week and I think next week when next week's show comes out on January 31st will be your last opportunity to, to do it. Get them in there.

## [00:11:29] Exposing Yourself to New Tech

[00:11:29] **Adam:** So, we were going to talk about new tech and exposing yourself to it. Diminutively.

[00:11:37] **Ben:** I think about learning technology as falling into two broad categories. There's the technology you learn on the job because it's either an existing technology at the place where you're employed, or it's a new technology that's being introduced to solve some sort of new problem at the place where you're employed.

[00:11:57] **Ben:** So that's one category. The other category is I have eight hours a day, the other eight as Adam will call it, where I have an opportunity to do self directed learning, having Maybe something to do with work, maybe nothing to do with work. Maybe I'm going way off on a tangent. I'm learning something completely unrelated because it's new, because it's fascinating, because it's just fun.

[00:12:20] **Ben:** And I see those as being the two ways to learn. And the tech industry, I feel like we often, pride is not the right word. I feel like on one hand, we pride ourselves as being engaging with technology proactively. That's something that technology people do. But then I think there's a flip side to that where.

[00:12:41] **Ben:** People who don't do that are a little bit chastised or, or othered almost like, Oh, here's the, the nine to five, or they're coming in, they're just doing their work and they're not taking time to explore new database technologies or new paradigms, or they're not trying to get better. And, you know, I think there's a lot of gray area in between the two extremes.

[00:13:03] **Ben:** And I think about the fact that I've been place of employment for 12 years now, something like that, and that there are people who jump around from job to job every one or two years. And I think it makes a lot of sense that the people who jump from job to job, and I'm not saying jump diminutively, diminutively, diminishingly.

[00:13:26] **Ben:** I'm not trying to make fun, diminutively. I'm not trying to paint that negatively that people who go to multiple jobs, but they're going to, I think, have more natural opportunity to be exposed to new technology just because of the number of different contexts in which they've been employed. Someone like me, if I've been in the same place, and I've been maintaining the same application for.

[00:13:47] **Ben:** Over a decade, the opportunity to be exposed to new technology, I think is very naturally significantly limited compared to people who switch jobs with higher frequency. Which means that if I'm going to introduce myself to new technology, I either have to do it on the job, in which case I have to make a pretty compelling business case for doing that.

[00:14:12] **Ben:** Like, hey, we all know how to manage MySQL and MySQL is running super well. But why don't we throw MongoDB in there? Why don't we throw DynamoDB in? You know, I have to justify the cost of the learning, the cost of the implementation, the cost of the maintenance, the cost of the hosting. So that's a, that's a tough sell.

[00:14:28] **Ben:** It can be a very tough sell. The other opportunity, of course, as we talked about before, is I can take my spare time and I can learn MongoDB because it could be interesting. Or I could learn DynamoDB because it could be interesting. Or I could learn a new front end framework because it could be interesting.

[00:14:43] **Ben:** But then there's the consideration about how much do I actually learn? And, and this came to the front of my mind just recently when I haven't touched my blog in a couple of months because I've been working on my book and I went to edit something on my blog and my, I had rewritten my front end stuff to use Hotwire, which is a front end framework. and I had to like remind myself how Hotwire even worked. And I had this button that was generating a preview of a, of a text field. And I swear, it took me like 15 minutes just to figure out how that button was wired up to show the thing that's on the page. I'm looking at the network activity and I'm looking at the HTML and I'm trying to figure out where the, the click handlers are happening.

[00:15:27] **Ben:** And I'm, and I'm trying to trace and I mean, it's so ridiculous. I, I'm fantastic at JavaScript. I'm fantastic at HTML. Like the fact that it took me 15 minutes to figure out how this was wired up, it was bonkers. And it's not that it was a problem with Hotwire. It's a problem that I'm not using it every day, that I haven't looked at it in months.

[00:15:46] **Ben:** Well, I think, you know, my point is that to say that we learned something, isn't just that we looked at it and we have a cursory understanding of maybe how it works, I think to say that you actually learned something is, is, is like, you're proficient in it, that you could. Start it and use it. And it makes sense.

[00:16:09] **Ben:** And you have paradigms that you understand. You have idioms, like you know how to use it. It isn't just that you read the syntax and now I can use that language.

[00:16:19] **Adam:** I think the metaphor of like belts in martial arts, like, you know, the, you start out as a white belt, I guess it is. And you, you know, you go orange and yellow and green and blue and whatever, all the way up to a black belt, stripes and stuff. you know. I agree with you that, you know, to say that you learned a language or you know the language is pretty high up there on the belt scale, right?

[00:16:42] **Adam:** But to say that I am familiar with a language, I've exposed myself to it, and I have a general understanding of when I might try to push forward or say like, Oh, we're having that problem? I think I know something that might be able to help. you know, that's pretty low on that scale, right? That's like, you know, white belt or whatever comes immediately after that.

[00:17:01] **Ben:** Is it orange belt or something? Yeah. And, and so I think maybe there's a disconnect between the pressure that we put on ourselves as an industry versus what the output, what the intended output is, you know, if we say, Hey, you people in this industry should proactively. Learn new technology so that they can stay up to date. This is like the same thing that we have where someone says, Oh, singletons are bad.

[00:17:30] **Ben:** And then we don't actually understand what singletons are. So we go through a decade of misunderstanding what that even means. And then realize that, Oh, what we thought was a singleton actually isn't a singleton at all. And, you know, if someone said, Hey, you should learn new technology. One person could walk into that statement thinking, Oh, wow, that means I should probably learn a new language, be able to build.

[00:17:51] **Ben:** A production grade application with that language and then maintain that language over time, and someone else could walk into that statement and say, Oh, I should just have a cursor understanding of what's available in a language such that if I ever need to use it in the future, I'll at least know that it exists.

[00:18:07] **Ben:** And the amount of learning that has to go into those two experiences are vastly different. You know, one could be, I watched the eight hour Udemy course, and one could be. I read four books and I built an application for a side hustle and I deployed it. And, and that's, that's very different. And I'm, and I'm, it's,

## [00:18:29] 10 Years, N Languages

[00:18:29] **Adam:** think that there's a tendency in this industry and it's all too easy to forget that it's I'm beating around the bush. It's painting with a very wide brush to say everybody in this industry should be, learning new technologies all the time, right? Like, so you, you mentioned before we started the call, like people who say things like, I learn a new programming language every year, right?

[00:18:52] **Adam:** Like, I don't know about you, but I'm thinking of one person in particular. hi, Sean, reader of this show, who, is. you know, he says that. If I'm not mistaken, he does try to learn a new programming language every year. And that's fine. There's absolutely nothing wrong with that. I think that's great.

[00:19:08] **Adam:** But, Sean is not the, doesn't have the same lifestyle as me, right? So Sean doesn't have kids, I have kids. And he's a, he's a different age than me. I think he's like roughly 10 years older than me, if I'm not mistaken. and you know, so we're just like at totally different places in our lives and our lives have gone vastly different directions.

[00:19:27] **Adam:** And so, also, You know, I feel like I'm that type of person that's super ambitious and, and I try to, even if I'm not, like, experimenting with it, I'm, I'm watching YouTube videos, I'm, I'm, aware of a lot, even if I'm not, like, physically messing with it, and So I feel like I kind of satisfy that requirement in my own way, right?

[00:19:53] **Adam:** That like staying aware and, and, able to put that knowledge to use if the need arises without spending a whole bunch of time outside of, my nine to five hours on that sort of stuff. Now, at a different point in my career, I did, you know, like that was how I chose to spend my free time. And I've just, you know, my life has evolved to where I prefer to spend my free time.

[00:20:19] **Adam:** Jumping out of planes or making sawdust and instead. And so, you know, like I said, I think it's, it's painting with a very wide brush and we have to acknowledge the fact that A, not everybody can do that, right? Like there's people that are single parents or who have to support their family or, you know, whatever else is going on that just don't have that time.

[00:20:43] **Adam:** Or maybe they're trying to break into the industry and they're, you know, got their first programming job and they still also have to do their. or whatever on the side too, you know,

[00:20:53] **Ben:** but so, okay. So, and I, I don't want to pick on Sean here, but the idea of learning a new language, the idea of learning a new language every year is fascinating only because we've talked in the past. About people who work at a job and we say, you know, they've worked at this job for 10 years. Have they had a 10 year career or have they had one year repeated 10 times?

[00:21:18] **Ben:** Meaning that they didn't really improve so much as an engineer. They just kind of did the same thing year after year after year, and they made it through 10 years. And again, I'm not picking on Sean here in any way whatsoever. He's, he's a very brilliant person, but someone could attempt to learn a new language every year.

[00:21:36] **Ben:** And in a way, I don't think you have to squint that hard to say, did that person just have the same year over and over for 10 years? Like you, yeah. Okay. You spent a year learning a language, but like, so what? Did you really get good enough to, you know, what is it as an

[00:21:54] **Adam:** be able to write hello world in

[00:21:55] **Ben:** Right, exactly. Would it have been more valuable to spend 10 years mastering one language, 10 years kind of getting to know 10 languages?

[00:22:04] **Ben:** And I'm not saying that one of those is absolutely better than the other. I'm just saying that I think in my mind, I haven't positioned it in a, in a way that makes me able to think about it critically.

[00:22:19] **Carol:** And there's something to be said, too, about the people who implement the changes and have only been slightly curious about what they're learning. So now it's implemented in a way that's not able to be supported. It's very bad. So everyone has a bad taste for what's going on with this language because it was added in a way that it should have never been added.

[00:22:41] **Ben:** Yeah, absolutely. And I think a lot of that comes from experience and part of that experience is oftentimes failing to do something the right way, you know, one or multiple times. And then finally, you know, you're at year five of using this

[00:22:56] **Carol:** Right?

[00:22:57] **Ben:** and you're finally like, you know what? I think I finally get it now.

[00:22:59] **Ben:** I understand how all these pieces fit together. Actually like right before we got on this call, I was listening to an episode of GoTime as part of the ChangeLog podcast. And they were talking about Kafka. And Kafka, it's like a message broker. I've never actually used it. It's a, it's an event bus and a message broker and a, an event system.

[00:23:18] **Ben:** And, and, on the, in the interview, they were asking this guy, I said, well, how do I know as a company when I should start using Kafka? And he was like, definitely don't start using it until you totally understand what it does. And you absolutely know that you have to use it. Because if you don't know that and you just want to throw it in there, he's like, it will not work.

[00:23:38] **Ben:** You will be in a world of hurt. Your application will have to be completely re architected and it will not

[00:23:42] **Carol:** Oh, yeah,

## [00:23:44] Implementing New Technology

[00:23:44] **Ben:** Yeah. And so, but you can imagine how, how easy it would be for someone to say, oh yeah, eventing. Oh, let's just throw Kafka in there because I heard about it on a podcast. And, and you could rationalize that.

[00:23:56] **Ben:** A hey, we need to stay ahead of the curve. And, and Kafka is cutting edge and it's gonna be what everyone's using and LinkedIn uses it and they scaled to, you know, 4 billion users or whatever. But the reality is, is like you don't have that team and you don't have that skillset. And is this the place to learn it?

[00:24:13] **Ben:** Maybe it is, maybe it's not. But there's no inherent, there's no implicit value that says that was the good choice. I'm kind of going off on a tangent there, but

[00:24:22] **Carol:** that's okay. You can go off on your tangents. You're allowed 1 of the things 1 of the things you mentioned kind of early on was that 1 of the reasons why people tend to learn things is they have a problem at work, right? Something you need to solve. Well, I tend to circle back to you wrote it wrong the first time.

[00:24:42] **Carol:** So what makes me think that a new technology is going to fix it? Like first you need to understand the problem and probably understand how to fix whatever's happening in the current stack that you have before you try to make it work in something new. I'm not saying don't learn it. I'm just saying maybe you understand your problem and figure out how to fix what you have first.

[00:25:04] **Ben:** One of my favorite quotes of all time, and I'm paraphrasing here because I don't remember the exact thing, and it's from someone's presentation. And it was something along the lines of like, if you couldn't build a monolith correctly, what made you think you could build microservices correctly? And I think it's, yeah, it's so perfect.

[00:25:21] **Carol:** So true.

[00:25:22] **Adam:** if I'm, if we're doing tangents, I have one. so I mean, it's, it's kind of connected because like you were talking about, you know, does it make sense for the company to pay me to explore around with new technology? Right. and. If we're just trying to draw a line in the sand, very binary, zero, one, then no, obviously it makes no sense for the company to, you know, pay you to, you know, just.

[00:25:46] **Adam:** Screw around in random stuff until you maybe, you know, 1 percent of the time find something interesting that's useful. But, if we're going to allow for gray area, I was, you know, this whole discussion reminded me of something I saw. I forget the, where it's, where I saw it, but basically, you know, there was a open source, like, framework and the person who was maintaining it you know, it was like, just burnt out and said, you know what?

[00:26:11] **Adam:** I'm, I need to take some time away. I'm not going to work on this anymore. and they just kind of stopped and, and companies, multiple people or multiple companies said like, well, this is terrible because now I have to train 20 developers to Go, you know, learn a different framework or something instead, because this one's no longer going to be maintained when, you know, the whole spirit of open source is like, you know, well, instead of training 20 developers to use a different framework, what if you just paid one developer to work on it, right?

[00:26:42] **Adam:** And to, like, contribute to the open source and fix the bugs and whatever, it would probably be less expensive. It would be better for the whole community. Your framework would be better, like, you know, it's just, there's gray area. And if you are willing to look through the right lens, I think that there is opportunities for mutual benefit.

[00:27:02] **Ben:** Yeah, I think absolutely. And, and, and this is where I also, again, going back to this idea of tenure of employment. I just don't know how to feel about it because on the one hand, if I change jobs with higher frequency, I would absolutely be introduced to more technology and in doing so, I could probably build a more well rounded, more robust understanding of the technology landscape.

[00:27:30] **Ben:** I'm also extremely pleased with the fact that I've been able to work on the same thing for over a decade. And that's taught me. All kinds of stuff in terms of robustness of architecture and depth of understanding and user experience and having to live with choices that is, it's robust in a narrower sense, but in a deeper sense than I would if I, you know, went to this company and we used Vue.

[00:27:55] **Ben:** And then I went to this company and we used Ember. And then I went to this company and now I'm on the backend. Went to this company and now I'm on the front end again. It's different. And I don't know how to think about it because neither is right or wrong. I don't know. I just. It frustrates me. It frustrates me that they're different.

[00:28:15] **Adam:** I hear you. I get it.

[00:28:17] **Carol:** tell you, I've bounced around a few times. You guys know that. I've only ever left one job that wasn't by my choosing. And, the majority of times has been because I was burnt out with the technology decisions and the inability to move forward with new tech or to make changes to the existing stack.

[00:28:38] **Ben:** I mean, that's good though, that you're moving on because you're frustrated or burnt out. It, and not just like chasing shiny things.

[00:28:47] **Carol:** Yeah, I guess it's diff well, I mean, kind of, but I mean, had I had the opportunity to make technology changes, I would have stayed around. You know, had I been able to implement things to make the application better, to store data differently, then I probably wouldn't have left. I would have stuck around and kept building to make a better solution.

[00:29:05] **Ben:** Gotcha.

## [00:29:07] Side Projects

[00:29:07] **Ben:** The other thing I think about is side projects. So again, part of what brought this all to the front of my mind was because I had recently redone the front end of my blog using Hotwire and it had previously just been native JavaScript, you know, just like homegrown JavaScript wiring stuff. And Part of me enjoyed that.

[00:29:26] **Ben:** Part of me thought maybe it was a little bit of a mistake that I wasn't getting a huge value out of it. It was, I was definitely just trying something new mostly for the sake of trying something new. And I'm, I don't want to demonize that because maybe it didn't add a lot of value in this case. So I'm not, I'm not trying to demonize learning just for the sake of learning.

[00:29:42] **Ben:** I don't think it really worked out for me in this particular case. then, but then I think about, okay, well, maybe I want to start another side project. Like I have my Dig Deep Fitness stuff, which I want to add a more robust front end to, and my front end of choice would be Angular. But then maybe I want to do another small site.

[00:29:59] **Ben:** Like I've talked in the past about wanting to create a poetry site. And part of me thinks, oh, it'd be interesting to Try maybe Vue. js for that particular site and maybe try to create a containerized deployment pathway.

[00:30:15] **Adam:** you just want to torture me by like mentioning everything except SvelteKit, don't you?

[00:30:20] **Ben:** I just like to mention everything except React. I'm sorry. but then I think, is that really going to be valuable or in the long term, is it just going to make all of those things harder to maintain because I'm just one person and I don't want to have to now. Keep this library up to date and then this library up to date and it runs into different issues because of different problems and now I have to go through different migration guides for different languages and nobody's paying me to do any of this and.

[00:30:45] **Ben:** All I really wanted to do was build something cool. I didn't, I didn't really want to necessarily get better at a particular technology. I just wanted to build a product.

[00:30:53] **Adam:** So actually that brings up a really interesting point. So you've, you've mentioned right there two different approaches to playing with new technology. And I think that both have strengths and weaknesses or pros and cons, right? So one is your blog, which is for the most part, no matter what, the blog itself is going to stick around, right?

[00:31:13] **Adam:** If you, if you, after a year messing around with Hotwire, you were like, eh, this is not it. You would either have to, you know, revert those commits or just go through the work of, of manually removing it and going back. or I mean, I guess technically you could take the content and, and, you know, start over with something else, uh, uh, and, but either way, right?

[00:31:37] **Adam:** Like, so there's, there's two approaches that I'm thinking of here. One is take a product that you already have that you intend to keep for the long haul. And the other is, I want to play with this technology, and I need an excuse, or I need a sandbox in which to play with it, so I'm going to create a fitness app, or a poetry app, or whatever, and I think that the con for that one is Okay, I haven't touched this technology, you know, maybe it was fine, maybe I loved it, maybe I didn't love it, but like, you know, I haven't touched my poetry app in three years and now I need to go fix something, you know, there's a new, there was a security vulnerability that I have to fix or whatever, and oh crap, you know, there's been six versions of React in the last three years, and you know, all of my libraries, my whole build tool chain is broken, right?

[00:32:24] **Adam:** Like that is a nightmare. I've been through that. There, I have an application that I wrote for making phone calls, right? So it uses a Twilio API and it like pulls up people's, you know, If you, if you happen to be a person who went to college and you graduated, there's a really good chance that sometime in your life, you'll be sitting down to dinner and you'll get a call from a student at that school where you went to college and they'll say, hey, I'm a student at the school where you went to.

[00:32:49] **Adam:** Can you give us some money? Right? And this is an application that helps that student, right? It like brings up your record. They've identified you because of. Certain things, maybe they're trying to raise money for the engineering department and you went to engineering school or maybe it's because you gave a gift last year but you haven't given a gift yet this year, whatever.

[00:33:07] **Adam:** They're different criteria. They pull up the data on the people that they're going to call and they, you know, kind of familiarize themselves with you as a persona briefly and then they call you and try to chat you up, make you feel good about your relationship with the school and then, hey, by the way, would you mind supporting students like me by making a donation?

[00:33:24] **Adam:** So I wrote an app like that. and it used like, React. I think it was a, like a pretty early version of Next. js. And GraphQL and the Twilio API, it was an awesome app. And it was just super stable and it was fine for like three years. And then they're like, oh, and we have some new feature requests and we'd like to move this over here and change this around.

[00:33:44] **Adam:** And I went back to it and I was like, this sucks. And, you know, we've done a few minor upgrades over in the, like, in the two or three years since it, that moment when I was like, Oh God, what have we done? in that, in the two or three years since that moment, we've done a couple of minor upgrades, but now we're at the point where, like, no, there will be no changes.

[00:34:06] **Adam:** The app can stay as long as the app is on its feet, that's fine. There will be zero changes. it's working, and it's internal only, right? Like, it's it's behind a login, so nobody can mess with it. There's no there's very, very limited security concerns, and We will eventually replace it with something more modern that we're going to actually like maintain and stay on top of it, like basically absorb it into the monolith, I think.

[00:34:30] **Adam:** but I kind of lost my train of thought. Where was I going with

[00:34:33] **Ben:** Well, but I think, I mean, I think that's a great point is that if you build something and it's using some cool technologies and you're sort of okay with never touching it again, and. And in a way, like sort of, okay, if upgrading it in the future is just more hassle than it's worth. And I think that makes a lot of sense.

[00:34:53] **Ben:** I think that's a great use case. That's not so different than saying, Hey, I just want to take the next month and learn this new technology and then build this thing. And I'm not saying, I'm not trying to diminish what it is that you're doing. I'm just saying like, you've, you've boxed it, you know, you've painted it inside a box and then you're okay with that.

[00:35:09] **Adam:** I

[00:35:11] **Ben:** And, and there's nothing wrong with that.

[00:35:13] **Adam:** think that that approach maybe makes more sense with the benefit of hindsight. I think that that approach makes more sense when the point of the exercise is to play with the technology. But if the point of the exercise is to have the thing that, you know, the, the end result that you build. Building it with something experimental and then just letting it sit there is very dangerous.

[00:35:36] **Carol:** Very, yeah,

## [00:35:39] Value of New Languages

[00:35:39] **Ben:** Now, if I can bring up ColdFusion for a second, because.

[00:35:42] **Adam:** What's that?

[00:35:44] **Ben:** It's a cutting edge web technology framework,

[00:35:48] **Adam:** Is that, that's because it's, it's falling apart. So all the edges are sharp.

[00:35:53] **Carol:** that's a good one. That's a real good one. Yeah. I'm going to keep that one in my pocket.

[00:36:03] **Ben:** well played, sir. cold fusion. I happen to love ColdFusion, not, not as many people do as maybe some other technologies, but fundamentally it's not a very unique language and, and I wanted to bring it up only because people have said things to me like, Oh, you only like ColdFusion because you don't know anything else or you haven't tried other things. And I'm like, that feels like such a cop out answer because I have to imagine that the difference between ColdFusion and PHP. And Ruby on Rails and Python with Django. Like fundamentally, they all have some sort of an application framework and they take a request and they route it to some sort of controller and they make some database calls and then they render a template and they serve it to the user.

[00:36:58] **Ben:** Like they're going to have different syntaxes and they're going to have different core libraries and they're going to have some advantages, but like fundamentally, they're all basically doing. Exactly the same stuff. Some use like a shared thread pool. Some spin up a new process every time they get a new request, but they're not really that different. and to that end, I feel like if I wanted to say, Hey, take a year and learn Ruby on Rails, like really, would that fundamentally change the way I look at programming? Would it really take me to another level and make me a more robust? developer, or if I took a year to learn PHP, like really, would that make me a fundamentally better programmer or would it have just kind of distracted me for a year from getting better at application architecture and solving customer problems?

[00:37:51] **Adam:** So I think if I could play the devil's advocate for a minute, I think that one of the benefits the people who say these things have in mind is that when you expose yourself to new languages frameworks and a new community of developers. You are opening yourself up to learn things that are not the syntax, right?

[00:38:14] **Adam:** So there might just be, patterns and methodologies and, you know, ways of thinking that are more common in this other community. than are common in your current community. to come up with a metaphor,

[00:38:30] **Ben:** No, no, no. But I think, and, and this is where just to circle back to what does it actually mean to learn something new? And I think if I want to be exposed to new ideas and a new community and people talking about things in a different way, do I have to go and learn that language? Or can I subscribe to a new podcast that talks about that particular language?

[00:38:53] **Ben:** Or can I maybe take, you know, a course on Udemy or Coursera that talks about that language? Like, do I really have to immerse myself? In order to feel like I've gotten that kind of value without having to really throw myself into it.

[00:39:09] **Adam:** Are you going to have the vocabulary to listen to that podcast and know what they're talking about if you don't have a basic understanding of that syntax?

[00:39:16] **Ben:** I mean, yes-ish. So I, I, to bring up Go Time, which is a Go podcast, it's, it's, it's a very good podcast, I think, and there's definitely language in Golan that I don't fully understand. They talk about channels and pointers and de referencing and that kind of stuff, and that, and that's not stuff that I use.

[00:39:41] **Ben:** Obviously it's a very different language, but it's like, I can hear how they're talking and I feel like I can, at least to a good degree, map the concept they're talking about over to ColdFusion, which is my language of choice. Think I'm losing a whole lot, but that, you know, that could be a naive understanding on my part, but it doesn't feel like I have to be spending a lot of time programming in Go in order to.

[00:40:08] **Ben:** Participate, at least, you know, implicitly in those conversations. I'm not actually calling up being like, you know, long time listener, first time caller,

[00:40:17] **Carol:** I think there's something to be said about not necessarily learning a new language, but learning a new way of programming, right? So if you go from object oriented programming to an understanding of functional programming or like procedural based things, then I think that does help you become better in the language you write because you have like this I don't think that means you need to go learn several languages for each of them, but whatever you can do to just learn the different ways of programming helps.

[00:40:53] **Ben:** so I totally agree. And then when we're, when I talked about, when I talked about a lot of the languages like PHP and Python, Ruby, those are, I think people would call those like C based languages. I think, I'm sorry, I'm not a programming academic here, so maybe that's totally wrong, but then if you look at something like Lisp.

[00:41:11] **Adam:** like lineage, right?

[00:41:13] **Ben:** Like Lisp is very different. And I probably, if I went and learned Lisp, that learning Lisp, I think would be a larger value add than learning PHP. Only because PHP and ColdFusion and Node, like they're all so similar that it's really, I'm really learning syntax and core language libraries, but if I learned Lisp, to Carol's point, like I'd be fundamentally forcing myself to think about programming differently and having immutable data structures and new types of data structures and how data is being passed around and pure functions and functional programming, like that's very different and that would be.

[00:41:49] **Ben:** I think much more valuable.

[00:41:51] **Adam:** And I, oh, I 100 percent agree with that statement. And I think that a lot of the, when we see innovation come to a community, a language, a culture that we're familiar with and that we immerse ourselves in every day, probably 9 times out of 10, that innovation is being brought in by somebody who was exposed to something very similar, in another community, culture, language.

[00:42:15] **Adam:** and it's just that one out of ten that's just somebody, some random brilliant genius who's like, Oh, what if we tried this? Right? And they just kind of, invent it whole cloth. right, so like the, a lot of the big changes that we've seen in the JavaScript and React stuff in the last several years has come from things like Erlang or Elixir.

[00:42:34] **Adam:** you know, like the whole immutable data, time travel debugging. My understanding, I don't, I haven't messed with these languages, but My understanding is that that was just like sort of table stakes for those guys for years before we ever even heard of it in JavaScript land.

[00:42:48] **Ben:** Well, yeah, even in Angular, the big thing in Angular now is the introduction of something called signals, which is just another part of reactive programming and they're like, you know, keep in mind, SolidJS had this 15 years ago. Like we're just rolling it in now.

[00:43:03] **Adam:** art. I did come up with another metaphor. So I'm just gonna call it spade is spade. This is not a judgment on you, Ben, but I feel like the, what I'm hearing from you sounds very much like you're trying to be an apologist for somebody who, doesn't, want to, or maybe doesn't want to have to, broaden their horizons, right?

[00:43:25] **Adam:** Try new languages, that sort of thing. and the, the thing that came to me is, like, spoken language as a, as a metaphor, right? So, there are languages that die out over time because they, stop, you know, because, I don't

[00:43:43] **Ben:** You don't speak Latin. What are you talking about? No,

[00:43:46] **Adam:** Latin, and well, so really what I was kind of leaning towards was like Native Americans, right?

[00:43:50] **Adam:** So there's these decreasing populations of Native Americans here in America, and they have their own language and they still speak it. A lot of them within their families and they have, they feel a sense of obligation to, continue to carry on that tradition to help make sure that the language doesn't die by, by, you know, teaching their children, that sort of thing. And like, on the one hand, I find that admirable. On the other hand, it's like, it's a, it's a language, right? The purpose is to be able to communicate. If you can communicate, that's mostly what matters, right? and I feel like there's a, there's a similarity in technology if you choose to, you know, so if your parents only ever taught you, Latin, and that's all you ever spoke in the house was Latin.

[00:44:45] **Adam:** And then you went to school and nobody was speaking Latin. And you tried to get a job and nobody was speaking Latin. That would set you back. You'd be, you'd find it very difficult to get along in society. And I feel like if you make that decision for yourself, to keep yourself in a In a pond that you can see is shrinking technology wise, right?

[00:45:04] **Adam:** You choose to stay with a technology because it's comfortable because it's familiar because you like it, but you can see that that technology is decreasing in market share, decreasing in popularity. and, and meanwhile, other options are thriving and innovating and getting bigger and better. You're kind of, you're, you're doing that to yourself, right?

[00:45:27] **Adam:** You're kind of, setting yourself up for difficulty in society should you have to continue to exist in society after that pond is fully dried up. I know I mixed up a lot of

[00:45:37] **Ben:** no, no, no, no. I totally understand what you're saying.

[00:45:40] **Carol:** Yeah, and I'm not, I'm not sure I totally agree with you because often do you see a technology fully go away?

[00:45:50] **Adam:** that's true. I mean, there's still COBOL in production

[00:45:52] **Carol:** Yeah, they are, and the people supporting it get paid a lot of money to support it because there's only a handful of people that can do it. I

[00:46:01] **Adam:** but how much do they enjoy their, their work?

[00:46:04] **Carol:** mean, that's, maybe they really do, and that's not for us to kind of try to figure out. It's, it's kind of like, If there's a developer who isn't naturally curious, but loves just getting better and better at what they're doing, and you know, wants to be the best at what they're doing, I don't think that makes them a bad developer.

[00:46:22] **Carol:** I don't think that that should put them into this like lower category. I feel like if you are Motivated to do better in what you're doing, you're still like getting that green check mark from me. Like I'm like good for you. But if you're one of those is curious and wants to know 10 different things today, then green check marks for you too.

[00:46:40] **Carol:** Like there's no reason to, to put anyone down for it.

## [00:46:44] Practicality

[00:46:44] **Ben:** Yeah. And I think there's a lot of practicalities to consider. So, okay. I'm having a lot of thoughts. So, one thought is the practicality of side projects, that if, if I wanted to start a side project. Do I want to try something new on the off chance that it then becomes something I use more regularly and therefore is a value add?

[00:47:08] **Ben:** Or do I want to take something that I know I'll continue to use even if it's not necessarily the newest hottest thing because I'm familiar with it and it'll make building the side project and maintaining the side project easier? So there's, there's practicality there. Then there's like the The question of cost, you know, if I, I mean, this is very specific to me, so I don't know if I can generalize this, but I have a VPS that runs ColdFusion and I pay for that and I can put as many sites on that as I want in theory.

[00:47:37] **Ben:** So is there a business case, you know, if I'm putting on my business owners hat right now, like, is there a business case for me now and going. And paying every month for a DigitalOcean droplet to try a different language, or is that just money out of my pocket for no reason? And if I ever had to use that technology, I could probably learn it and use it on a job anyway, because the reality is the amount of work that I put into it on a side project isn't really going to make me significantly good at it anyway, to the point where now I'm this hireable person. and I think maybe part of my frustration here is that if you want to say, Hey, and when I say you, the royal you, like if, if one wants to say, Hey, you should learn new languages because it makes you more hireable, then that's. Totally legitimate. And I think we can definitely say that as an industry, but I don't want to then kind of color, color it over and say like, good engineers are constantly learning new stuff and they should be exploring new ideas.

[00:48:39] **Ben:** And this is what, you know, this is how we learn. And this is how we grow like. If you want people to be hireable, then just say that, like, don't make it this virtuous adventure of always being the, the student of life and learning

[00:48:52] **Adam:** the way I want you to learn,

[00:48:54] **Ben:** like F that. Say, if you want a job, you got to learn this technology, period.

[00:48:59] **Ben:** I don't care if you even like it. That's what they're paying for these days. Don't make it virtuous. And if you want to make it virtuous, let's be more practical about what that actually means. On a day to day, yeah, like, again, like, does that mean listening to podcasts or does that mean building in depth products on the side that I maintain over 10 years?

[00:49:19] **Adam:** Or it could mean becoming better at being a tech lead or a manager or branching out from development and also taking on DevOps and getting good at Docker and Kubernetes and, you know, sysadmin stuff. Or, or 10 other things that we didn't mention

[00:49:36] **Ben:** Well, that's the thing too. like, I just keep on, my brain just keeps wanting to go down rabbit holes. So Carol talked about wanting to learn new things, at paradigms. But then, so I, I look at something like relational databases and object or, you know, document databases. And I've been using relational database for 20 years.

[00:49:56] **Ben:** I know pretty well, I understand a lot of the trade offs. You know, I'm not like a database administrator, but I'm a database consumer. If I want to just randomly switch to MongoDB, I'd have to really use it for a long time before I think I actually understood the value add and the trade offs of using that language, right?

[00:50:17] **Ben:** I mean, so a lot of just, just, atomic transactions, which I think MongoDB technically has now, but it did not in the beginning. You really have to understand what it means to build an application that doesn't have atomic transactions. And you have to plan for that. And you have to have, you know, things that keep data in sync on an ongoing process in case stuff fails in the middle.

[00:50:40] **Ben:** And, and if you just want to switch to MongoDB because you think MongoDB is great. Then you don't, it's web scale, like you, you won't understand the trade offs that you're making unless you start using it for years and you start hitting a scale where, oh, okay, now I have, you know, 4 billion records and, and a hundred million users.

[00:51:01] **Ben:** And now I see why I can't just scale up my database anymore that I really have to scale out and I have to shard and okay, now I can understand why I didn't want to have, you know, auto incrementing primary keys. But like, you, you can't get there to that level of understanding. It's like a catch 22. Like you can't get to a point where you understood why you should have used something until you've used it for a long time, which kind of makes this whole idea of I'm just going to take two months and learn a new document database for the sake of it.

[00:51:29] **Ben:** Like, like why it's, it's not gonna, it's not going to move the needle for you, I don't think in a meaningful way.

[00:51:38] **Adam:** Makes me want there to be like an index of technologies and their differentiators, right? So like. You'd go and you'd say, what makes MongoDB special? You'd look it up in this database or index or whatever, and it'd say like, I don't even know what it would be, right? There, there's, because I'm, I'm right there with you.

[00:51:55] **Adam:** I've been using, transaction or, or SQL like databases, relational databases. That's the word I was looking for, for my entire career, which was well over half of my life at this point. and Like, I have also messed with a few document databases. I've messed with Cassandra. I've messed with, CouchDB.

[00:52:13] **Adam:** I've messed with Mongo. And I have a basic understanding of like how to put data in them and take data out of them and the way their schemas work and that sort of stuff, or even schema less. What I don't understand is Why? Like what, what is the problem that somebody ran into with a relational database that they were like, okay, let's invent a new thing to solve this problem, right?

[00:52:37] **Adam:** And that I think is what you need to find out. That's the point of having that, that other technology. And maybe it was just like, let's just do things differently and see what happens. And that's a totally reasonable thing to do as a, as an academic exercise. like to know, right? Like, why would I choose MongoDB over a relational database?

[00:52:57] **Adam:** Or

## [00:52:58] Learning is Hard

[00:52:58] **Ben:** All to say learning is hard and I'm not throwing MongoDB under the bus. People absolutely love MongoDB. I think it does a, I'm sure it does a lot of tremendously great stuff. I just, I don't know it that well, but it, but it, it doesn't feel like relational databases aren't holding me back. And I know I don't want to make this a show about relational databases versus document databases.

[00:53:16] **Ben:** It's, it's just an

[00:53:17] **Adam:** it's about ColdFusion versus good languages.

[00:53:21] **Ben:** All to

[00:53:22] **Adam:** That felt too personal,

[00:53:23] **Ben:** learning is hard, learning is hard, and time is hard, time management is hard, learning is hard. I think there's also just a generational gap, meaning a new generation of programmers comes in and they just arbitrarily pick something or, you know, like me, I only know ColdFusion because it happened to be what they used at my internship.

[00:53:47] **Ben:** Had they been using, what's that?

[00:53:49] **Adam:** where was your internship?

[00:53:51] **Ben:** It was a place called, Kokopelli New Media. It no longer exists. It was a, it was a small web agency. you know, had they been using PHP, maybe I'd be using PHP today. You know, I'm not, I'm not so crazy to think that I would have, you know, all paths lead to cold fusion. It could very well just be coincidental.

[00:54:10] **Ben:** And it happened to be that I just accidentally landed on the best web program in language ever created, whatever, you know, if a new, if a new generation of engineers comes in and suddenly they're learning MongoDB and they're learning Node. js and they're learning React and whatever. That's just going to be the things that they happen to have learned.

[00:54:32] **Ben:** And it's not implicitly better than anything someone prior to them has learned, other than, you know, obviously some incremental improvements in the way we think about application architecture. It's just going to be accidental. It's tough. Maybe this is me just trying to wrestle with the idea of starting a new side project and rationalizing using the things that I actually know, and I'm actually very good at,

[00:55:00] **Carol:** I was gonna say, or maybe it's because you're also coming to the end of a career where all you've used is this technology. And now you're thinking of starting a new career somewhere where quite possibly ColdFusion isn't going to be the main thing they have.

[00:55:13] **Ben:** very possibly. Very,

[00:55:16] **Adam:** I could speak first hand, you know, when I made the decision to, try to put ColdFusion in my rearview mirror, right? And that's a very difficult thing to do, even just in terms of, I made the decision, and I no longer actively pursue ColdFusion work, and I could make other decisions that would make it, that would separate me from ColdFusion. I could quit my job and I could go somewhere else, but I like my job, I like the people, I like the product, I know the space, I have a good job, I, you know, I've got a lot of perks here that I like.

[00:55:52] **Adam:** And so, instead of making that decision to quit and go find work that doesn't include ColdFusion, I'm just trying to be the driver of change in my company. And push us to evolve in a way that is sensible for the business and good for the developers and all the other good things. but making that decision was scary and hard.

[00:56:18] **Adam:** And I had to, I mean, it felt very much like being a big fish in a small pond and jumping into the ocean. And, you know, in the ColdFusion community, I had a little bit of notoriety. People knew who I was. I was doing conference presentations and then I just jumped into the ocean of JavaScript, Node. js stuff.

[00:56:41] **Adam:** And I feel like nobody knows who the hell I am. I, you know, I I've done a couple of presentations since then. And. You know, it's just the vibe is totally different and that's fine. You know, I don't, I honestly, I think it's for the better. I don't, I've realized that, like, I don't necessarily think I want that level of spotlight in the, in a, in a larger pond.

[00:57:03] **Adam:** In that small pond, it was fine. it's been, I think it's been freeing. I think that had a lot to do with my personal priority shift and how, like, Granted, other things too. My, you know, my kids growing up and the, you know, the way we spend time together changed from when they were little and they went to bed at 7.

[00:57:23] **Adam:** 30 versus now they're taller than my wife and, you know, we have actual shared interests other than dinner, right? and,

[00:57:32] **Ben:** But still, you're, the stuff that you're doing is different, but it's still at work, you know, it's still the day to day practice, the building up of muscle memory. I, I think that's totally legitimate, you know, if you wanted to start a side project where you're booking tandem skydiving flights. you're like, you know what, for funsies, I'm just going to try to build it in some totally new framework.

[00:58:01] **Ben:** I have to, you know, I, I don't want to put words in your mouth, but at some point, at some point, I would imagine you would have the internal thought of, do I actually want to learn something new or do I just want to book some flights and make some

[00:58:15] **Adam:** hmm.

[00:58:16] **Ben:** And I feel like I just want to book some flights and make some money.

[00:58:19] **Ben:** And then maybe do something new and interesting at work where someone's paying me to do it.

[00:58:24] **Adam:** Maybe.

[00:58:25] **Ben:** yeah, yeah. I don't know. I can't speak for

[00:58:26] **Adam:** some time reflecting on that for sure. Yeah, I'm, I'm totally at it. You know, I'm 41. I'll be 42 in less than six months. Um, I'm at a totally, yeah, old man here. am I the oldest one on the podcast with Tim not here?

[00:58:39] **Ben:** no, no, I'm 43.

[00:58:41] **Adam:** Okay. I, but like, I'm at a totally different place than I was when I was like, you know, 27, right?

[00:58:47] **Adam:** You know, when I was 27, my kids were little. And, just my interests were like a hundred percent in my career, right? My, my, what, what kept me up at night was not anything other than I'm so excited to learn this new thing and that new thing, or to build this open source project I've got an idea for, or to try and present it, at some conference.

[00:59:15] **Adam:** And now it's, you know, I'm, I'm, my mind is more focused on. quality of life with my family and the ways that I, like take care of, like self care, right? Like I take care of myself and I give myself time away from the computer. I think that, that has been a big thing for me. Like I've, I've grown a lot, even just since we started this podcast, I've grown a lot as a person.

[00:59:36] **Adam:** And I

[00:59:38] **Ben:** you're welcome.

[00:59:39] **Carol:** Uh,Ben.

[00:59:45] **Adam:** I think that has a lot to do with, a shift in how I spend my free time. And part of how I spend my free time is with the three of you. So I'll take, I'll allow it. All right. How do we wrap this up? Don't learn new stuff. It's bad.

[01:00:05] **Ben:** I will say I would love if I could put more of this onus, this responsibility on employers. That if we as an industry could somehow position it so you go and work at a place and it's up to that place to educate you and to create a more well rounded employee and more well rounded engineer and to introduce you to new ideas and not maybe lean so heavily to your point, Adam, on having to have people Do all this career building outside of their career and, and having to cope with the fact that priorities change and, and, you know, privilege changes.

[01:00:47] **Ben:** And it'd be great if. I didn't have to panic about learning new stuff outside of work or have

[01:00:55] **Adam:** know, that's a, that's an excellent point you just made to privilege. You know, I'm sure that my own personal privilege, my job security has gone up tremendously in the last 10, 15 years. my. you know, not just job security, but like the, the comfort that I enjoy from the job that I have that is secure has gone up.

[01:01:16] **Adam:** Right. And so I'm sure that that has influenced the fact that I am less hungry to constantly be exploring new technology.

[01:01:27] **Ben:** Yeah.

[01:01:28] **Adam:** And that's not that I'm not hungry. It's just that the hunger that I have is satiated at work for the most part. Okay..

[01:01:37] **Adam:** Bye bye.

[01:01:38] **Ben:** sorry, there's, I don't know if anyone here has ever seen the documentary Pumping Iron, Arnold Schwarzenegger from the seventies, I think. It's a fantastic documentary. If you like Arnold Schwarzenegger, it's just classic Arnold Schwarzenegger. So there's this one scene where there's a whole bunch of these bodybuilders and they're out sunbathing in, I think in Venice beach or something.

[01:01:58] **Ben:** And Arnold Schwarzenegger, he's best bodybuilder in the world is seven times Mr. Olympian, he's, he's a very cocky person and this other guy's talking to him and he's saying, you know, you're on the, you're, you're the king of the king of the mountain Arnold, but. You know, you're the wolf at the top and the wolf who's climbing the mountain, he's hungrier than the wolf at the top.

[01:02:17] **Ben:** And Arnold goes, he's hungrier, but the wolf at the top, when he's hungry, he knows the food is there. I feel like that's a kind of, kind of like what you're saying, Adam. You, you got that stability. So it makes you less hungry. You know, that when you want to learn something, you have more opportunity to do it.

[01:02:35] **Carol:** Yeah, I get that.

[01:02:37] **Ben:** just an opportunity to throw Arnold Schwarzenegger. Into the podcast. We don't do it enough. We don't do it enough.

[01:02:45] **Adam:** bodybuilder slash former governor.

[01:02:48] **Ben:** He just released a book, which apparently is getting very good reviews. Be, be useful, I think.

[01:02:54] **Adam:** It's a promising young, young upstart. I'm sure Joe Rogan will have him on any day now.

## [01:03:04] Patreon

[01:03:04] **Adam:** All right, well then I guess we'll wrap it up there. This episode of Working Code is brought to you by Sweet Potato. Wearing his Nantucket t shirt today. And listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[01:03:19] **Adam:** Our patrons cover our recording, editing, and transcription costs. And we could not do this every week without them. Special thanks to our top patrons, Monte and Giancarlo. Reminder, reminder, get in on the Patreon, get your address in there so that you can get your stickers. they're, they will not be available any other way, and it'll be a once and done, and you'll never be able to get them again.

[01:03:42] **Adam:** Not these ones. maybe we'll do it again next year too, who knows. But,so patreon.com/workingcodepod if you'd like to help us out. We actually do have a new patron to thank this week. Grace Lee joined us this week, so thanks for joining up, Grace. And,

[01:03:56] **Carol:** Hey, welcome!

[01:03:57] **Adam:** Welcome to the party, pal. That's what we say in the Discord.

## [01:04:02] Thanks For Listening!

[01:04:02] **Adam:** so, speaking of Discord, why don't I give you homework? It's been a while since we've done homework. Come join our Discord. It's been super, good chats in there the last couple of weeks. We've had several people reach out and just say that, like, our Discord is their favorite programming tech related community.

[01:04:19] **Adam:** And that just warms my heart. Like it is also my favorite place to be. It's the place that draws my attention the most. And I, I'm a member of like 12 different discords and ours is the one that I check first thing and last thing. And it's the only one that I don't like mute all the random notifications on.

[01:04:37] **Adam:** So it's a fantastic place to be.

[01:04:39] **Carol:** Yeah, how the heck do you manage those notifications?

[01:04:42] **Adam:** They're muted. That's how. Like, I only get notified for other discords when I get like pinged when somebody tags me. Anyway, so come join our discord. You can go to workingcode. dev slash discord to get on there. It's free. It's like slack, but better. And that's it for us this week. We'll catch you next week.

[01:05:00] **Adam:** And until then.

[01:05:02] **Carol:** Remember, your heart matters, even if you're the only Cobalt developer left.
