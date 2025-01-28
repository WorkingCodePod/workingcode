---
title: "034: Some of My Best Friends Are React Developers!"
description: 'This week, Adam talks about his "obnoxious optimism": his general tendency to believe that all problems can be solved and that everything will just sort of work itself out.'
date: 2021-08-04
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/034-some-of-my-best-friends-are-react-developers/id1544142288?i=1000530968195"></iframe>

This week, Adam talks about his "obnoxious optimism": his general tendency to believe that all problems can be solved and that everything will just sort of work itself out. This optimism allows him to take action and make decisions quickly. However, it also means that he may not be fully considering the future cost of his choices.

This is not uncommon in the programming world. Engineers are often criticized for choosing technologies based solely on their merits and almost never on their drawbacks. Of course, we don't want to be so cautious that all productivity grinds to a halt. The best possible scenario is to have a team with diverse personalities that can all temper each other. Every team needs an Adam; but, every team also needs a few curmudgeons.

## Notes & Links

- [Just command runner](https://github.com/casey/just)
- [CockroachDB](https://www.cockroachlabs.com/)

Follow the show! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media][editor].

[working-code]: https://workingcode.dev/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[editor]: https://www.zcross.media/
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/034-some-of-my-best-friends-are-react-developers.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** And now it's two different databases that have to be kept online with

[00:00:03] **Carol:** And see, that's just annoying.

[00:00:04] **Tim:** you've segmented data, right? You can't, I mean, how do you run report? I don't know if any there's any need for reporting on both of those

[00:00:11] **Carol:** Yeah. Like what's the

[00:00:12] **Tim:** run it from two

[00:00:13] **Carol:** between that data even.

[00:00:14] **Ben:** it's the same, you know, I think I had ranted on a previous episode about how we have react and this is not a dig on react. We have react rendered in.

[00:00:23] **Adam:** I want to be racist, but,

[00:00:25] **Ben:** We

[00:00:25] **Tim:** some of my best friends are re react programmers.

## [00:00:45] Intro

[00:00:45] **Adam:** Okay. Here we go. It is show number 34. And on today's show, we're going to try playing with the format a little bit. We're just going to go back to our roots. We're going to talk more water cooler discussion and just see where it goes.

[00:00:56] **Adam:** but as usual, we're gonna start with the trumps and fails and Ben, it looks like it is your turn to go first.

## [00:01:00] Ben's Triumph

[00:01:00] **Ben:** excellent. And I'm kicking us off with a triumph. two weeks ago, I was asked to estimate some work for a client of ours. We're building some custom feature into the application. And I estimated that I would be able to get it done by this Friday and I finished today. So I'm coming in a full day ahead of schedule, and I feel like that in the engineering world , pretty, pretty, pretty good.

[00:01:29] **Ben:** So you're saying you're underestimated.

[00:01:32] **Carol:** Every time.

[00:01:34] **Ben:** but you know, I think I went about it very strategically. I said, I need to do a little investigation to see how much of the application I need to touch before I understand the scope of work. So I took a full day and looked through the application, looked to various repositories, look through the code base, did a bunch of extended fines.

[00:01:50] **Ben:** And I got a sense of here are all the different touch points that I'm going to have to probably interact with. I didn't do like a deep dive, but I got tobird's eye view. Wrote down a list and, just, I tend to be really high level in my estimation. I don't look at something and say, that'll take an hour, that'll take three hours.

[00:02:09] **Ben:** I basically just give a day for everything on the list, figuring that some of those will be less than a day. And then some of them will be more than a day that sort of just figures itself out. So pretty excited about that. Yeah. So that was I was ending the week on the high there.

[00:02:24] **Carol:** Good job.

[00:02:25] **Ben:** Thank you, Tim. What do you got going on?

## [00:02:27] Tim's Triumph

[00:02:27] **Tim:** Well, we're doing two episodes this week in the same week. Normally we do once a week, but so two, a last episode show. I was I was down because I had lost my just drive. I just wasn't feeling it on Tuesday, but amazingly I got it back. So, yay. Come on, mojo back. I think what made the difference was I didn't really have a lot of code.

[00:02:48] **Tim:** I wear a lot of hats. I didn't have a lot of code work to be doing at the time and I was looking for something to do. So I just said, all right, I'm going to take the coding hat off. And I'm going to focus on some sales and marketing stuff, some relationship building stuff, partnership, building stuff. And I got really into it.

[00:03:07] **Tim:** And I'm like, okay, cool. So, and it seemed to be paying off because you made some really good headway on some really important collaborative efforts with other companies. And so that kind of gave me that excitement, but I do have some code stuff that's coming in the future that I can look forward to.

[00:03:23] **Tim:** So I'm excited about that. So, yeah, Just I had a case of the Mondays on Monday and Tuesday. but now I'm back, maybe. So it makes me,

[00:03:33] **Adam:** Just need some extra flair.

[00:03:34] **Tim:** Yeah. a little more flare on

[00:03:36] **Carol:** You're only feeling better. Cause you knew you were going to see us again.

[00:03:40] **Tim:** that's true. That's true. Twice in one week.

[00:03:42] **Carol:** a lot of energy.

[00:03:43] **Tim:** like, that's like Christmas twice in a year. That's fantastic. How about

## [00:03:48] Carol's Failure &amp; Triumph

[00:03:48] **Carol:** Oh guys, I got some sad news for ya. so yesterday had bird eggs today. The eggs are gone. They are just gone. They're not in the birdhouse at all. So I think something in nature ate them.

[00:04:05] **Carol:** So kudos to the thing and Aden and nature, that ate them. I'm glad you got some dinner, but something ate the eggs. So they're gone

[00:04:13] **Tim:** a little snake. Got it.

[00:04:15] **Carol:** but I do.

[00:04:16] **Ben:** eat bird eggs

[00:04:17] **Carol:** Do they, I know owls will probably, there was no shell. So I thought a snake. Yeah,

[00:04:27] **Tim:** a snake. no more three little birds by your

[00:04:30] **Carol:** No more, but I have a tech win. Let me go them a

[00:04:34] **Tim:** Ben got

[00:04:35] **Carol:** it was a song. Right. And then the chipmunk

[00:04:37] **Tim:** Yeah.

[00:04:38] **Ben:** Bob

[00:04:39] **Tim:** Now it's Bob Marley.

[00:04:40] **Carol:** sing it?

[00:04:42] **Tim:** I ma maybe, I mean,

[00:04:45] **Carol:** think the chipmunks thing at teal that's who I'm giving credit to for the song is the chipmunks.

[00:04:50] **Tim:** don't worry about a thing. That's the

[00:04:53] **Carol:** So, like Tim said, we recorded on Tuesday and on Tuesday I was in a hole in an async await problem where something just was not coming out. Right. And couldn't figure it out, had someone else look at it with me and he couldn't figure it out either.

[00:05:08] **Carol:** So, I slept on it, came in here Wednesday morning and open my code and was like, oh, look at that. I kind of introduced my own problem by throwing a dot then and there to a promise that shouldn't have been there. So I'm like, oh, so whenever I took out some things that I had added to actually get the promise out, I was like, oh, now everything just works perfectly.

[00:05:29] **Carol:** I was like, why did I ever introduce that? Like, why did I put that coat there?

[00:05:36] **Adam:** there should be like an ESL Lindt rule you can opt into that tells you, like, don't use that. Then you're going to be

[00:05:42] **Carol:** Yeah. Like if I'm in an async function, just why am I even throwing a dot then into it? And I was like, Aw, I'll get it next time. Right. So then I had to tell my team, I was like about that problem. I couldn't fix, not only do I fix it, I introduced it. And sorry. So yay. Thanks God.

[00:06:02] **Adam:** Five little characters.

[00:06:03] **Carol:** it was?

[00:06:04] **Ben:** One thing that I don't quite connect with, and I know people are loving, this is one of the, I don't know if it's TypeScript or one of the newer releases of ECMAScript now includes top level of weight. So typically you have to have an await inside an async function. But I think now in like the bleeding edge stuff, you can just have an awake, even if you're not inside of an async function.

[00:06:28] **Ben:** And I just, I don't get how that's supposed to work, meaning that the await function returns a promise always.

[00:06:36] **Carol:** Yep.

[00:06:37] **Ben:** So how does it, like, what's the expectation of error handling.

[00:06:43] **Adam:** I think your understanding might be flawed and maybe that's why you don't get it. So, wait let's you wait for a promise to return an async function. Always returns

[00:06:51] **Carol:** Oh, sorry. That's what I meant to say. If I said something different. So I

[00:06:55] **Adam:** Yeah. So I mean, the way that I am looking at it is that like that top level of your code that, the whole file itself just sort of becomes an async function.

[00:07:07] **Adam:** Right. And so the event loop, or whatever's running your JavaScript is expecting a promise back now. And if you in return, I mean, it doesn't even have to return anything. Right. Like, yeah. So yeah, whatever. I mean, it's just doing that.

[00:07:24] **Ben:** guess

[00:07:25] **Adam:** I

[00:07:26] **Adam:** there've been so many times that I wanted top level await that. Yeah.

[00:07:29] **Adam:** I'm one of those people that's like, yes. Finally dancing in the

[00:07:32] **Carol:** But see, I haven't seen a use for it. Like, I don't know when that would use it, so.

[00:07:37] **Adam:** So for me, the first thing that comes to mind is we have config that we have available inside of our VPC on AWS. And so basically only when you're like on our VPN or you're inside of our cluster of servers behind the firewall config is available over an HTTP service. and so there are a lot of things that are like simple scripts that run, but it needs to get config first before it can do anything.

[00:08:04] **Adam:** And because we don't have top level await, we have to jump through some extra hoops to like wrap everything in an async iffy or something crazy. Like.

[00:08:15] **Ben:** then do you ever run into this, a race condition where in note, I know you can register an unhandled promise rejection.

[00:08:26] **Adam:** Handler.

[00:08:26] **Ben:** didn't want to say handle the handler.

[00:08:28] **Carol:** Handled.

[00:08:30] **Ben:** I mean, so I, it's interesting, right? Because it's almost like you need If you have your ingress file, like your top level file, it's almost like the asynchronous aspect of it is defined by the fact that it has an await inside of it.

[00:08:47] **Ben:** Or maybe it's just always a sink. cause I'm wondering if there's now some weird race condition where what happens if an error occurs before you register your unhandled promise rejection call back, like does the nature of an async in that function now change the timing of when those functions get called.

[00:09:04] **Ben:** Is there a time where you can throw an error now on a top file and the get swallowed because there's nothing listening for it, but because it's technically returned as a promise, like it doesn't error, error just sort of rejects. I dunno. I've never played with

[00:09:19] **Adam:** That's a good question. I don't know. It sounds like something I would look up on Ben's blog.

[00:09:24] **Carol:** Okay.

[00:09:26] **Ben:** Yeah,

[00:09:28] **Tim:** Sounds like something Ben would look up on Ben's blog. That's why he wrote it.

[00:09:32] **Carol:** What about you, Adam?

## [00:09:35] Adam's Failure

[00:09:35] **Adam:** so I have a fail and it's going to sound weird to me. This sounds like, one of those disingenuous interview answers, right. what's your biggest what, and what is that? I'm trying to think of it. What's your biggest weakness? And you were like, oh, I care too much. Or, too much attention to detail, whatever.

[00:09:52] **Adam:** So my fail here is that. I would say naturally obnoxiously optimistic to the point where it can be a problem. And I know that that probably doesn't make a whole lot of sense by itself. So I have a story prepared

[00:10:05] **Tim:** Storytime kids.

[00:10:07] **Adam:** about, eight years ago my family moved, right. We were just outgrowing our our first house and looking to buy a second house.

[00:10:14] **Adam:** And so we were hell shopping and pretty much everywhere that we looked at, as long as it was, it met the minimum level of like, we could live here. I was all gung ho. I was just like, yeahthis is a great house. Why do we need to look at anything else? Just let's buy it. to the point where, like, I think one of the first places that we saw the family room or living room, the place where you spend most of your time in your house, this house is family room was like, I dunno, eight feet wide by like 20 feet long.

[00:10:45] **Adam:** And it was obvious that this was just like, oh, an awkward floor plan, right? That didn't phase me, I was like, I liked, there were other things about the house that I liked and I was like, w we would live, we would survive here. We'd be fine. Be fine. And so, I was like, gung ho couldn't.

[00:10:59] **Adam:** I couldn't see the negatives because I was too happy with the potential of the positives. Right. And so that sort of optimism can get me into not so much trouble, but it just, it leads me down a bad path sometimes. And so I have a sort of a tech example here too. We've talked to recently about my love for make files and that's not going anywhere.

[00:11:24] **Adam:** I still love make files for basic stuff. But we've also talked about some of the ways that, that my team has been pushing, make files probably sort of to the limit of what they are. Capable of doing or what should be done with them. and things get kind of hairy. And speaking of, clean code, the code definitely gets unclean.

[00:11:45] **Adam:** when you've got three times as much comments as code to explain why things are working this way. And it's just not a good sign. And so, I think we might be backing away from make files a little bit just because, and I mean, we haven't even identified a good place to go next, but the approach that we're currently using, it's just not going to be a good one longterm.

[00:12:09] **Adam:** And I did find so Kurt tweeted back. I tweeted out a thread of like, this is my problem. These are sort of the constraints I'm trying to work within. and Kurt replied back with a link to this library called just, which is actually written in rust. I know that might be a part of where it gets its name from, but it's basically. sort of a reimplementation of make, but they took away some of the idiosyncrasies of make that were specific to the fact that this was invented. I don't even know how many years ago, I want to say 30, 40 years ago.

[00:12:41] **Tim:** It's been around a long time. Yeah.

[00:12:43] **Adam:** and and so it, there were some assumptions baked into mate that don't work when you're using it as a task runner.

[00:12:50] **Adam:** Right. It's it was invented as sort of a build system for C programs. And when you're using it for a different purpose, it's a little odd. And so there's some things that are different about it. and I'm really interested in, oh, another thing about this. So, you guys have seen some basic make files.

[00:13:06] **Adam:** One of the really interesting things about just is that in each target, so, right. Like I said, it's basically a very slight variation on. I see you still got a target and a script underneath each target, but at the top of each of that little script in, for each target, you can put it's called a shebang the pound exclamation point slash user bin end node, or whatever executable you want to use.

[00:13:29] **Adam:** And so you can script different targets in different languages. So you can have like one quote, unquote, make file, like just file that has Ruby in it and Python and node and bash,

[00:13:41] **Carol:** Okay. I'm liking this.

[00:13:42] **Adam:** it's really interesting. So I'm going to be spending some time playing with it, just to

[00:13:47] **Tim:** you sound optimistic about it.

[00:13:49] **Adam:** well, why would you say that?

[00:13:51] **Carol:** kind

[00:13:51] **Tim:** I don't know he got it. Yeah. He kind of got a little excited there when you're like, oh, this is one thing he does is really, really

[00:13:57] **Adam:** me.

[00:13:57] **Carol:** Oh

[00:13:59] **Tim:** Yeah. I think all of us can, I probably have some stories like that too, where you Just get overly excited about a certain technology, little too early, and then you make decisions based off that excitement.

[00:14:13] **Tim:** And then you wind up dealing with the consequences down the road

[00:14:16] **Adam:** Right.

[00:14:16] **Ben:** So I'm a little confused as to the just sounds like it's basically a drop-in replacement for make files. So it's not that you're moving away from make files, you're moving towards a make file. That's better suited to your type of workflow.

[00:14:31] **Adam:** a new make executable kind. I mean, so, I mean, I was trying to be careful to say upfront there that we haven't necessarily decided to use. Just in fact, I sent a link toward the end of the day today to my coworker and said, this is interesting. And I pointed out some of the neat things about it, like the multiple language stuff.

[00:14:48] **Adam:** and I haven't gotten a single response from anybody about it yet, so I have no idea what my coworkers think,

[00:14:55] **Tim:** They busy.

[00:14:56] **Adam:** but,

[00:14:56] **Carol:** Like, man, Adam's happy again about something.

[00:15:00] **Adam:** Right, probably. So, I'm not saying necessarily that we're moving to that, but I found it really interesting. Now, one of the problems that our current solution does that we haven't found anything, including just that really intentionally. that we have, so we have a series of microservices and they are all deployed in the same way. Right. They're built as Docker containers. They're we have tests. So we have a consistent way to test them all consistent command to test them all. and they're all deployed to AWS far gate. And so there's a lot of similarity between them in the dev ops, right?

[00:15:40] **Adam:** So, the same commands to build your dev environment, to build and publish a production build to, to run the test, to do a deploy, et cetera, et cetera, et cetera. and so one of the things that we were doing with make files was that was why we had that whole like inheritance thing. We talked about where we had sort of a base make file that had the the default implementation, which was common to all of our modules, all of our microservices.

[00:16:06] **Adam:** And if we needed to override one for some reason, then we could do that. and I, again, I don't see an easy way to necessarily do that with just and then there's the idea of another part of the reason that we, well, I'm not sure. I forget the details of how this all came together, but so one of the things that it also does is it does sort of auto updating of that base inherited script by going into its directory and running a get poll so that we get the latest from that repository, if there happened to have been any changes to it.

[00:16:40] **Tim:** Okay.

[00:16:41] **Adam:** And again, like, that's just not something that I think anything out there is really solving for. And I don't know if that is a sign that we're doing things wrong, or if that, maybe that's a niche that needs to be filled. I have no idea at this point.

[00:16:58] **Ben:** well, if I can offer up some bander and maybe this is not really relevant, but in, in one of the previous episodes you were talking about, you're working on your feature, flag implementation, and part of the way you were implementing it is that when you change a feature flag, there's some magical screen.

[00:17:17] **Ben:** They're like autogenerates pull requests that store that, and that, to me, that feels, yeah, it feels a little too overly optimistic.

[00:17:31] **Carol:** love it. I

[00:17:33] **Adam:** No it's really cool. Don't get me wrong. It's really cool. But yeahit almost, it starts to feel because I don't know very much about the GitHub command lines and interacting with get programmatically. It starts to feel very magical from my perspective, because I have no experience there. Sure. So I can, I'll speak to that one specifically, we have another system that was already doing that.

[00:17:56] **Ben:** right, right, right.

[00:17:57] **Adam:** and it is working. Yeah. We haven't had any problems with that mechanism and it's using the official GitHub SDKto do all the interactions with GitHub. and yeah, I mean, all it's basically doing is checking out a copy of the repository, updating the Jason file, saving that and making a commit with it and then making a pull request with that one commit.

[00:18:17] **Adam:** so I totally agree with you. It sounds a little too crazy to actually be a good

[00:18:22] **Adam:** But but at the same time, it's working for us

[00:18:24] **Carol:** just a pull request. It's not like any codes going in. It's not anything crazy. It's just a PR that.

[00:18:32] **Ben:** I guessI'm jaded at this point in my life when two systems have to connect for some reason, I know that sounds weird in the world of web development, but it just there's in my experience in the application that I work on, which, every application is a unique snowflake. every point of contact between two systems represents some sort of future frustrates.

[00:18:58] **Carol:** I agree though. Yeah.

[00:19:00] **Ben:** So I try I almost err on the side of like being obnoxiously optimistic about a single technology, I'm like, oh, I can totally do this with ColdFusion. If I have to like, shoe horn in some sort of a distributed lock that manages task execution across multiple servers. Cause I'm like, you know what, I'm doing it in ColdFusion.

[00:19:25] **Tim:** Love your loyalty. Let me ask you though, Adam. So you talk about this as a fail. I mean, I. You know how you feel about it, but where have you seen legitimate failures from that sort of attitude that you have?

[00:19:44] **Adam:** That's a fair question. I think maybe the reason that I consider it a fail is because if it wasn't for the clear headedness of my wife, I probably would have bought up a house that was not a good idea to buy. Right. then that's a really bad decision.

[00:20:01] **Tim:** That's a big decision. Yeah.

[00:20:03] **Adam:** and so. I can see that as having a lot of potential to get me in trouble.

[00:20:11] **Tim:** So it sounds like, I mean, your wife is sort of the, the foil to your optimism there, that kind of tempers that w who's that in your organization when it comes to technology or is there

[00:20:21] **Carol:** any.

[00:20:22] **Adam:** Yeah. Yeah. I mean, I would say that my CEO is pretty good about that. He's very good at taking sort of a higher level view stepping back and seeing the forest for the trees sort of thing, and asking the right questions. And it's funny. I, so maybe actually, so while we were working on our current product, Maybe.

[00:20:46] **Adam:** So actually we've talked in the past about our get branching strategy and Ben, you said you wanted to hear like, that, that decision when we were when we decided to go with multiple sort of master branches for each customer that yeah, I mean, at the time they were mastered because nobody knew any better

[00:21:04] **Carol:** We all know better now.

[00:21:05] **Adam:** better

[00:21:07] **Carol:** Let's be

[00:21:07] **Adam:** right.

[00:21:08] **Adam:** but that same debt and I remember vividly, and we had that meeting that I had mentioned to you, where we were when we were waiting for a meeting and we made that decision after the meeting, we went to a coffee house. So it just sort of unwind and recap from the meeting. And I was like, okay, well, while we're here, well, let me show you this thing.

[00:21:27] **Adam:** This is a new thing that has just sort of popped up in the tech world. And I think it's really gonna be good and big. And I think maybe we should consider this and it turned out it did get big, it was react. So, there are times that, I pick the right horse

[00:21:42] **Carol:** Yeah.

[00:21:43] **Adam:** right?

[00:21:44] **Tim:** you guys use react.

[00:21:45] **Adam:** We do. Yeah, we have, I would say, oh God, in terms of lines of code it's a very small percentage, but in terms of revenue, then revenue generating code.

[00:21:57] **Adam:** It's a huge

[00:21:58] **Carol:** Okay.

[00:21:59] **Adam:** of

[00:21:59] **Carol:** You presented on react and

[00:22:02] **Adam:** I did

[00:22:03] **Carol:** in Minneapolis, how would you say that? I suck at Minneapolis, whatever at the college at that one time.

[00:22:11] **Adam:** Yep.

[00:22:11] **Tim:** Yep. Yes. So I mean, I, the reason I asked about, who's your foil is I think in a small company, if you don't have that, that, that unchecked enthusiasm can be

[00:22:21] **Carol:** get you in trouble.

[00:22:22] **Tim:** and have long-term effects on a company as it continues to grow. And I think a lot of small companies, I got really big, really fast deal with that, decisions made at the time.

[00:22:32] **Tim:** and I myself, Several times on this podcast. My love for cockroach DB, we don't officially use it anywhere, but I'm just absolutely enamored with the ability to, set up multiple shards of a CQL database that also kind of acts like a document database and you can just spread it geographically all over the place.

[00:22:50] **Tim:** And it keeps things atomic. I mean, just, it has so many benefits, but what my foil is because the size of the organization I'm in, I realize the struggle that I would have to introduce that into our ecosphere and to replace the incumbents is so big. It's just not a fight I'm ready to do now until you start really seeing cockroach make some big money moves in the marketplace where bigger companies are really using it.

[00:23:17] **Tim:** And it becomes more, somewhat more common. And now it'syou can get the people to sustain it and to maintain it. And yeah, there's just, that is what that's what puts me in check. just that. Organizational overhead of, if you're going to introduce something that important to it, to a place it's going to be scrutinized.

[00:23:35] **Tim:** And so I realized that, and so I say, well, okay, I gotta slow my

[00:23:39] **Carol:** I also take a look at the community support. Like I'm going to be able to get online and find help and find answers. And if it's brand new to it, no matter how shiny it is and how great it looks, I kind of just step back and go. Not enough people are contributing yet. None of the people are in there. I don't want to spend the first year of using this product, answering questions for everyone else.

[00:24:00] **Carol:** Like I want there to be a good support and a good community built when I started doing it.

[00:24:04] **Adam:** Yeah.

[00:24:05] **Tim:** And don't want to be the Guinea

[00:24:05] **Carol:** Nobody wants to be the Guinea beg not in tech, not fun.

## [00:24:11] Choosing Technologies and Confirmation Bias

[00:24:11] **Ben:** One thing that I've heard the engineering world in general, or maybe this is specific to the web development world in general, accused of, is judging things based on their benefits and almost not at all on their drawbacks

[00:24:25] **Tim:** Okay.

[00:24:25] **Ben:** and using that and like, essentially not thinking about the operational costs or the organizational costs like Tim was saying in the longterm only thinking about the things that you get in the happy path of how something works.

[00:24:38] **Carol:** But we kind of do that in everything. Adam walks are almost like, look, it has a toilet. This is. this is exactly where we should be at babe. Let's move in here.

[00:24:50] **Adam:** I go to the bathroom, like every day.

[00:24:52] **Carol:** think there's a spot for a fridge. We're good.

[00:24:55] **Adam:** Yeah.

[00:24:56] **Tim:** Like some sort of product that I just buy for around the house. I'm like, I really want this thing and I just buy it and I feel so good about it. And then I get it. And then I wind up looking at like the longer YouTube videos about the pros and cons. Like, why didn't I do this beforehand? because I didn't want, I think there's a part of ourselves that we don't want to hear the negative part about it. Right? We want to believe we want to buy into the dream and looking at hearing people say the negative parts of it are kind of. Kind of burst that bubble actually, although audio books, I'm very particular about, I always look at the negative reviews first.

[00:25:29] **Adam:** Oh yeah. I, as, I mean, that's good. I mean, they'll have information about narrator problems

[00:25:35] **Tim:** yeah. I always do that because I've been burned, I've only get so many tokens a month from audible and it's like, if I don't want to burn this one and then wind up with a book I don't even want to finish. So

[00:25:44] **Adam:** you know, you can return it.

[00:25:46] **Tim:** I do. I feel dirty when I do that. Yeah, You can If it's like a certain period of time, you can totally return it, but I just feel dirty.

[00:25:54] **Adam:** I'm almost certain you can return them any time, including after you've completely read it.

[00:26:00] **Ben:** Carol is laughing. Like she's totally done this. Like every single time she's purchased or something. Yeah.

[00:26:06] **Adam:** Karen Carol has only ever bought one audible credit.

[00:26:09] **Tim:** It just keeps recycling. It's funny,

[00:26:16] **Carol:** Adam, Adam,

[00:26:18] **Adam:** Tell

[00:26:19] **Tim:** good reasons.

[00:26:20] **Adam:** tell us how many audible credits that you've purchased in your life by how red you get.

[00:26:26] **Carol:** when we stop recording, we'll talk

[00:26:28] **Adam:** I'm, yeah. I absolutely take advantage of that, right? Like, so for the longest time I was the type of person that would read a book. what's the word that I'm looking for here? Like, I would get mad at it and read it anyway because like, I'm not enjoying it, but I feel like this responsibility to finish what I start.

[00:26:49] **Adam:** So I'll start a book and I'm like two chapters in and I hate it. I'm like, I hate reading it, And I reached this point in my life when I was like, nobody's making me do this. There's no test. Right? I'm not getting anything out of this. I'm hating every minute of it. Why am I doing this to myself?

[00:27:04] **Adam:** And so I just, I like, I can vividly remember the first time I put down a book and I was like, I'm not going to finish this book. And I returned it to the library. And that was that it was a cryptonomic con by Neil Stevenson.

[00:27:18] **Tim:** Really,

[00:27:18] **Adam:** Yeah, Hey, listen. I like a lot of his books, but that one, especially like th the constant jumping forth, back and forth between the timelines and the characters from the same family with the same name, like in two different timelines, I was like too much for me I'm out. so, it was a good story, but I couldn't keep it straight.

[00:27:40] **Adam:** have to try an audio book. Cause I feel like I would be able to get through it faster and that would help me keep it straight. And maybe like, if there, if a narrator does different voices for the different people, that would also help,

[00:27:51] **Tim:** Yeah. I mean, so bringing it back to tech, I mean, like Ben said, sometimes we need to maybe check out the negatives for a straight and weigh those rather than only weighing the pros. Yeah.

[00:28:01] **Tim:** Cause you know, I'll be honest. I've only looked at the pros of cockroach. I've never even tried to look at a search of like, what errors does it have?

[00:28:08] **Tim:** what is the common things that people complain about it? Cause they're out there

[00:28:11] **Adam:** there should be like a Yelp for

[00:28:12] **Carol:** Oh, Angie's list.

[00:28:15] **Adam:** So you can go read the one-star reviews

[00:28:17] **Tim:** it. Stack overflow.

[00:28:19] **Adam:** yeah, but there's not like a place where you can go and read, like literally rate the information and like, okay. So, Carol gave this app a one-star review, why, and what's our description and what's wrong with it.

[00:28:32] **Adam:** And it's just like on Amazon, right? There's going to be some one-star reviews that are like about the shipping time or the box that came in, or the fact that the shipper like beat it up, right. Obviously that has nothing to do with the product. So you just ignore those, but there's also plenty of useful one-star reviews.

[00:28:52] **Adam:** And also I think that the people that are most likely telling the truth are the like three, three and a half, four star people, you know, they're, , they're being objective. They're not just like blowing sunshine up.

[00:29:05] **Tim:** Who would ever want that? I mean,

[00:29:07] **Adam:** Sunshine of your

[00:29:08] **Carol:** Sounds like something Adam would

[00:29:09] **Tim:** yeah, I don't

[00:29:10] **Ben:** It's a spa treatment.

[00:29:12] **Carol:** Okay.

[00:29:13] **Adam:** Spa treatment. Here's a window.

[00:29:18] **Tim:** Ben Dover.

## [00:29:20] Feeling the Impact of Decisions

[00:29:20] **Ben:** one thing that I've noticed is that I'll be looking through code and it's code that I didn't write. And it's crazy. Not because I didn't write it because I think it's like legit crazy and it's really hard to update or it's not working properly or there's like crazy hacks. And I'm just like, oh, F you for making me maintain this code.

[00:29:39] **Ben:** and like, inevitably the person that I'm angry at no longer works at the company. and, we've talked about like, Adam, you've been at your place for nine years. Right. Are you going on nine years? I've

[00:29:51] **Adam:** Yeah, you and I have been

[00:29:52] **Ben:** yeah, I've been at the same. Tim's been at his company would for like 20 years. You said, Carol, I think you said you were at your previous one for five years.

[00:30:00] **Ben:** Is

[00:30:00] **Carol:** well, so I did like five years and then a year and a half somewhere, and then came

[00:30:05] **Ben:** yeah.

[00:30:05] **Carol:** years and now six months. Yeah.

[00:30:08] **Ben:** but

[00:30:08] **Tim:** she's like a bad penny. She

[00:30:09] **Ben:** I, you know, I think there's a benefit to being at a single place for years because you get to really see and feel, and experience the impact of decisions.

[00:30:20] **Carol:** Oh yeah.

[00:30:21] **Ben:** Whereas if you, even within a company, if you jump around from team to team, I think really what you lose is. Is the longterm impact of decisions. So I think it's easier to be optimistic when you don't have to then deal with your decision for the next eight years. And I think having to do that makes you maybe a little bit more gun shy though. Adam clearly is obnoxiously optimistic. So, so, your mileage may vary.

[00:30:50] **Ben:** but I would just wonder if there's like two different segments of people that have two very different feelings, just because they haven't had to deal with things the way certain people have.

[00:31:00] **Carol:** I can see that.

[00:31:01] **Tim:** yeah. When you have to clean up your own mess, it's humbling.

[00:31:04] **Carol:** Yeah. like the saying hindsight's 2020, right? Well, if you've never had to have hindsight, like what if you've never had to wonder what happened back then? Cause you weren't there to deal with it. You're like, all right. Cool. Everything went well, moving on.

[00:31:16] **Adam:** that's Peter. Right. last week we talked about the Peter

[00:31:20] **Ben:** yeah.

[00:31:21] **Adam:** was

[00:31:22] **Carol:** I know it was the week before.

[00:31:23] **Tim:** Couple of a couple of

[00:31:24] **Carol:** or three. Yeah.

[00:31:26] **Adam:** But

[00:31:26] **Tim:** You upwardly fail to your

[00:31:28] **Adam:** yeah, you just

[00:31:28] **Tim:** of incompetence.

[00:31:30] **Adam:** enough that it's not your problem.

[00:31:34] **Ben:** Like, oh my God. so I'm a relational database fan. I'm I like, we use MySQL. I happen to use MySQL. I grew up on Microsoft SQL

[00:31:43] **Tim:** Did I mention, I use Postgres

[00:31:44] **Adam:** I knew it was

[00:31:45] **Tim:** this episode.

[00:31:46] **Carol:** it is happening.

[00:31:48] **Ben:** and years ago, someone introduced Mongo DB into our application and I have nothing against Mongo DB, but now it's like, now there's two databases that we have to interact with.

[00:31:57] **Adam:** Is that like starting a sentence with, I don't want to be racist, but.

[00:32:01] **Tim:** Mongo DB sucks.

[00:32:02] **Ben:** like, there are still places in the code where I look at the queries that are hitting our Mongo DB D data. And the query is where the ID equals the ID as a number or the ID equals the ID as a string because there's no schema at the document level. And at some point someone wrote code that was inserting IDs as a string.

[00:32:24] **Ben:** And none of those were coming back. So it's like you opted to choose a database that had no schema validation, which is fine. But then when you realize there was a problem, you didn't then go back and clean up your data. You just add a jenky code that patched over that problem. Now

[00:32:44] **Ben:** I

[00:32:44] **Carol:** Okay.

[00:32:45] **Ben:** I could point that mirror back at myself and say, I've noticed that happening.

[00:32:48] **Ben:** And I have not gone back and cleaned up the data either.

[00:32:52] **Adam:** Yeah,

[00:32:53] **Ben:** Yeah.

[00:32:53] **Tim:** like not my mess. So I didn't do that.

[00:32:55] **Carol:** you get the, make the assumption that they didn't clean it up because they tried cleaning it up and something very bad happened. So you just leave it.

[00:33:02] **Tim:** Yeah.

[00:33:03] **Ben:** So,

[00:33:05] **Adam:** to assume the best in

[00:33:05] **Carol:** Yeah. They tried to fix it.

[00:33:07] **Ben:** Yeah. I don't even know where I was going with that rant. Other than to say, I look at, I'm not picking on Mongo DB. It's just point of mind for me. And I look at the way we use Mongo DB and we use it basically like it's a text area. It's not like we're doing fancy document level manipulations.

[00:33:27] **Ben:** We're like pushing onto a raise or incrementing sub keys. Like there's nothing interesting happening. It's basically all get me this Jason blob, where this ID equals this ID.

[00:33:38] **Adam:** So it's nothing you couldn't have done

[00:33:40] **Ben:** It's nothing you couldn't have done with the relational database. and now it's two different databases that have to be kept online with

[00:33:45] **Carol:** And see, that's just annoying.

[00:33:49] **Tim:** you've segmented data, right? You can't, I mean, how do you run report? I don't know if any there's any need for reporting on both of those

[00:33:55] **Carol:** Yeah. Like what's the

[00:33:56] **Tim:** run it from two

[00:33:56] **Carol:** between that data even.

[00:33:58] **Ben:** it's the same, you know, I think I had ranted on a previous episode about how we have react and this is not a dig on react. We have react rendered in.

[00:34:07] **Adam:** I want to be racist, but,

[00:34:09] **Ben:** We

[00:34:09] **Tim:** some of my best friends are re react programmers. okay.

[00:34:19] **Carol:** Ben,

[00:34:20] **Tim:** I, we broke Ben guys. We broke this.

[00:34:28] **Adam:** Okay.

[00:34:33] **Tim:** might have to take a break.

[00:34:36] **Adam:** Okay. Well, I thought Carol turned red.

[00:34:40] **Carol:** my vein didn't pop as much as yours did that time. Yeah. Yeah.

[00:34:43] **Ben:** Oh man.

[00:34:46] **Carol:** All right. So you know, some people who write react.

[00:34:51] **Ben:** Say in the way that we now have Mongo running alongside MySQL. If areas that render react inside angular and what it does is really just create a difference in cadence of maintenance that we have a team that's better at angular. So that's the part that gets the attention because nobody, it's not that nobody wants to work on the react.

[00:35:11] **Ben:** It's just even the build process is slower and that, there's all kinds of bad decisions that were probably made there having nothing to do with react itself. But like, same with Mongo. I know how to observeMySQL database. Like I know how to look at the performance. I know how to look at the slow queries.

[00:35:27] **Ben:** I know how to run explains on queries. I don't know how to do that

[00:35:31] **Carol:** it's not so easy. Yeah.

[00:35:32] **Ben:** So the by-product of that is that I don't try to optimize anything in Mongo because it's not.

[00:35:38] **Carol:** Yeah.

[00:35:39] **Carol:** So I, we tend to, like, I wouldn't say navigate, but that's the wrong word? what is it when you like go towards something? anyways, we tend to lean toward the thing that we know more and that we can do more. So then when there's something in the application that we don't know how to use or that we're just not as good at, it does become the thing that we neglect,

[00:36:00] **Adam:** Were you thinking of the

[00:36:01] **Carol:** maybe gravitate to gravitate with work.

[00:36:02] **Carol:** We tend to gravitate toward. Yeah. Yeah. I don't English all.

[00:36:09] **Tim:** Okay.

[00:36:09] **Carol:** Yeah.

## [00:36:09] Benefits of Obnoxious Optimism

[00:36:09] **Tim:** So I'll ask you this though, Adam. So you talk about the negatives, but I mean, I would imagine there's some positives for you being, as in your own words, obnoxiously optimistic when it comes to, so what would you say those are?

[00:36:23] **Adam:** I mean it pairs, well, I think with my ambitionI love a good challenge, right? Sit me down in front of a problem and some constraints and a pile of technology and some documentation. And I could spend three days before I realize I haven't eaten, like that's just, that's my personality.

[00:36:44] **Adam:** And it's because I get my high fromsolving those challenges or solving those problems. And it's just, I feel like I can identify for the most. Any problem that is impossible to solve or at least impossible to solve in our constraints. And so when a problem is not impossible to solve, I'm like, hell yeah, I'll take it on.

[00:37:08] **Adam:** Right? Like why not?

[00:37:12] **Ben:** I mean, I think that's awesome.

[00:37:14] **Ben:** I, my, one of my biggest weaknesses I think is that I can't dream any bigger than my own hands. Like if it's not a problem that I, not that I have to understand how to solve it ahead of time. But if it's not obvious, at least how to get like halfway there with the skills I already have, it's very hard for me to even think that path is possible.

[00:37:37] **Adam:** Yeah.

## [00:37:38] Optimists &amp; Pessimists

[00:37:38] **Ben:** So I think it's like when you build a company, you almost need some of, both of those people. Like you need the dreamers, like Adam, Yeah. He was like, I don't like, we'll just solve it. Who cares? Like let's solve this problem today and we'll just assume we can solve the next problem tomorrow and not fret about it too much.

[00:37:56] **Ben:** and then you need to be tempered with the people who are the naysayers like myself for like, ah, here's a hundred reasons that won't work.

[00:38:05] **Tim:** Hmm.

[00:38:06] **Adam:** Do you think Clark ismore like

[00:38:08] **Ben:** he's very much the visionary. App's a hundred percent P

[00:38:12] **Adam:** visionary is a different thing I think,

[00:38:14] **Ben:** he's the, yes, he's the eternal optimist. He's like the it'll.

[00:38:17] **Adam:** Okay.

[00:38:18] **Ben:** If he has the vision, he knows he can get there. Even if he doesn't know how that works.

[00:38:24] **Carol:** Nice.

[00:38:25] **Adam:** Right. Yeah. So for anybody who has no idea who we're talking about, Clark is the other co-founder of Invision.

[00:38:31] **Ben:** I, I always refer to myself as like, I'm a good number. Two guy. People are people are like, they're like, what are you going to do next? You should just start another company. I'm like, what are you crazy? I don't know anything about starting companies.

[00:38:42] **Carol:** Okay.

[00:38:43] **Tim:** scout

[00:38:43] **Carol:** You got a number one that needs help.

[00:38:45] **Ben:** Yeah. Yeah, exactly.

[00:38:48] **Adam:** I have always been in love with like infrastructure and enabling other people. When I was in college, my first foray into blogging, I kind of talked my best friend on my floor, in my dorm, into like co blogging with me. Really. It was all for me. It was all about I, okay. Now I get to write the software that he's going to use Tableau,

[00:39:10] **Carol:** Oh, I love it.

[00:39:12] **Adam:** right?

[00:39:13] **Tim:** funny.

[00:39:13] **Carol:** I mean, I remember about a year ago you were like, Hey, I had this idea for this podcast. Yeah.

[00:39:21] **Tim:** right.

[00:39:22] **Adam:** Not a full year. We're

[00:39:23] **Carol:** It was during the summer.

[00:39:24] **Adam:** is what episode

[00:39:25] **Carol:** no, we talked during the summer, like toward the end of the

[00:39:27] **Adam:** That's true. We did a.

[00:39:28] **Carol:** And I was like, Hey, when you think about doing this and we, met up around October, right.

[00:39:32] **Carol:** Kind of really started talking.

[00:39:34] **Adam:** Yeah, we did. We started recording in October, but we didn't release anything until December. So.

[00:39:38] **Carol:** So

[00:39:38] **Tim:** Yeah, but we were talking

[00:39:39] **Carol:** your optimism is good.

[00:39:42] **Tim:** Yeah, I think Ben hit on the head that you got to have that kind of mix of people. when we do our stand up. Although, stand up, it's really kind of about, what, you're working on any roadblocks, but sometimes there's that little bit of pushback of like someone, someone brings up, you know what I think we really need to like go in and re look at how we're doing X. And you're like, I'm like, well, X is working fine. why are we spending time on this? And like, well, this, and this, I'm like, okay. I mean, are those problems insurmountable with the way we're doing it now? No, but it'd be better if we just refactored the whole thing. And I just think that conversation between someone is not even that the negative Nelly on that conversation, it's just, I probably don't know enough about it.

[00:40:25] **Tim:** And when you start asking questions, hopefully a person who's an optimist might be a little self-aware about that and go, you know what, as I say it out loud, the way we're doing, it's probably fine. We've preached needed to make a small change rather than a wholesale change. and our time's been better elsewhere.

[00:40:42] **Adam:** I've gotten a lot better at that. Business-wise and Business is the only word that's coming to mind, but I know what you're talking about. Like what's good for the product is not necessarily what the developers want to do

[00:40:54] **Tim:** Yeah.

[00:40:55] **Tim:** Right. Developers want to do stuff that's fun to develop, Right. It has nothing to do with what necessarily. What's good for the product. What's good for the company. So getting another viewpoint from someone else says that's a good idea, But I mean, honestly, is it really more important than these five things that would really be better?

[00:41:11] **Tim:** Like, yeah. Okay. I see your

[00:41:12] **Adam:** But that's not to say that there's never a time that doing things that have no immediate impact on the bottom line is a bad idea. that was a lot of negatives in one sentence. What I'm trying to say is sometimes it is worthwhile to do things that seem completely worthless, like a refactor of a huge portion of the application because they improve your ability to make money from that code longterm.

[00:41:37] **Adam:** Right.

[00:41:37] **Tim:** Right. and

[00:41:37] **Adam:** the code is becoming

[00:41:38] **Carol:** as good as they are to maintain it.

[00:41:39] **Tim:** right? yeah.

[00:41:41] **Tim:** I wasn't talking bottom line. I was talking about, what's best for the product. Right. And sometimes Yeah, you're right. Something that isn't going to necessarily give a tangible benefit to the customer, but will make everyone's life a whole lot better.

[00:41:52] **Tim:** Maintaining the product, building the product, understanding the product, do it.

[00:41:56] **Carol:** just

[00:41:57] **Adam:** Okay, well, so we've established that the title of this episode is going to be some of my best friends are reactive,

[00:42:04] **Carol:** but

[00:42:06] **Tim:** I think so.

[00:42:07] **Carol:** are react developers.

[00:42:08] **Adam:** right? Yeah. Yeah.

[00:42:10] **Ben:** Yeah.

[00:42:10] **Adam:** is there anything else that we wanted to cover here? I think we're kind of getting close to the end. It's

[00:42:13] **Adam:** been

[00:42:14] **Carol:** I

[00:42:14] **Carol:** love that. You're optimistic. I don't think is obnoxious at all.

[00:42:19] **Adam:** Well, you don't have to deal with me on a date basis.

[00:42:23] **Carol:** weekly amount of you is good. You're good. Yeah.

[00:42:26] **Tim:** yeah.

[00:42:27] **Adam:** All right. Small doses.

[00:42:29] **Tim:** just

[00:42:29] **Adam:** That's right.

[00:42:30] **Tim:** know thyself.

[00:42:32] **Adam:** All right. Well then if nobody has anything else, let's bring it home.

[00:42:36]

## [00:42:36] Patreon

[00:42:36] **Adam:** So this episode of Working Code is brought to you by sunshine up your butt and listeners. Like you, we cannot do that.

[00:42:41] **Ben:** Yeah.

[00:42:42] **Carol:** totally. Can we just did?

[00:42:46] **Adam:** Okay. And if you like what we're doing here, you might want to consider supporting that's on Patreon at patreon.com/WorkingCodePod. Although after that, why would you

[00:42:55] **Carol:** to say thanks for your support? We offer perks to our patrons. They get an invite to our Discord server. We hang out, we talk about the podcast.

[00:43:02] **Adam:** So it works off lifestyle, anything, and everything is fair game. we have other perks like early access to our new episodes and our after show. We're going to go record and pretty much just more of this. every week we think our top patrons, and since this week is part of every week, we're going to send a huge thank you to Peter and to Monte.

## [00:43:20] Thanks for Listening!

[00:43:20] **Adam:** And you know, what if paying for podcasts? Isn't your thing. That's cool with us. We appreciate you taking the time to listen and you can help us out without spending any money by sharing the show with your friends and your coworkers, you can also leave us a rating and a review on iTunes or wherever you get your podcasts.

[00:43:34] **Adam:** Please send us your questions and your show topics on Twitter or Instagram @WorkingCodePod. Or you can leave us a message at 512-253-2633 that's 512-253-CODE. We'll catch you next week. And until then,

[00:43:48] **Tim:** Remember guys, your heart matters.
