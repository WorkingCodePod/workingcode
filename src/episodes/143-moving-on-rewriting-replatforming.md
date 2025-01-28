---
title: "143: Moving On, Rewriting, Replatforming"
description: "On today's show, we explore the difficulties in 'moving on' using several different contexts: Jobs, tech stacks, video games, API implementations, front-end frameworks, and more."
date: 2023-09-06
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/143-moving-on-rewriting-replatforming/id1544142288?i=1000626943446"></iframe>

While change is inevitable, managing and adapting to change is always a challenge. Change represents the end of something we knew and - at least for some period - loved; and, ushers in the start of something completely unknown. On today's show, we explore the difficulties in "moving on" using several different contexts: Jobs, tech stacks, video games, API implementations, front-end frameworks, and more.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/143-moving-on-rewriting-replatforming.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** Can you, just out of, for my own personal curiosity, can you talk more at all about the actual re platforming that you want to do or is that,

[00:00:07] **Adam:** Our application is Mostly built on CFML,

[00:00:11] **Ben:** Oh, so you're already done.

[00:00:12] **Adam:** Lucy. What's that?

[00:00:14] **Ben:** You're already done with the rewrite.

[00:00:15] **Tim:** Mm

## [00:00:37] Intro

[00:00:37] **Adam:** Okay, here we go. It is show number 143 and on today's show, we are going to once again, attempt to discuss the topic of moving again, inspired by by Carol's excused absence. Carol's not with us tonight because she's still working on moving from Georgia to, it's, it's Arizona right now, right?

[00:00:52] **Tim:** Correct.

[00:00:52] **Adam:** of a temporary basis. I don't know. We'll, we'll get more information from her later, but in the meantime, we're going to attempt to keep our triumphs and fails short, shorter this week, and get to the real topic at hand. We have some things we want to discuss, so let's just get straight into it.

[00:01:09] **Adam:** Ben, why don't we start with you? What's going on, man?

## [00:01:12] Ben's Failure

[00:01:12] **Ben:** I'm going to go with a failure, which is just full body stress. I, as we discussed in previous episodes. I've been moved from a full time employee to a part time employee, and that's still very much in limbo. I don't exactly know what that means yet, and it's just, it's taking a toll on me physically and mentally.

[00:01:32] **Ben:** Big knots in my, in my back and my traps. I feel all just uncomfortable, and my wrists, have been Flaring up in their pain. I bought myself a mouse that has a track ball, so I don't have to move my hand back and forth. I can do just my thumb and that. I don't know.

[00:01:50] **Ben:** I've got,

[00:01:50] **Adam:** that are on the trackball life and they say that it helps with that.

[00:01:54] **Ben:** that's my hope. I'm on day, three, I think. it's coordination wise, it was really hard to get going. but on day three, it feels much better than day one, just in terms of coordination, whether or not it's actually doing anything for my repetitive stress injury, that's remains to be seen. But, I do think that a lot of my wrist stuff is emotional because there was a day or two where I was actually feeling somewhat relaxed.

[00:02:20] **Ben:** I was sort of had let my mind just go with the flow and not really worry about work so much. And I swear my wrist felt way better. And then today. I was just feeling very stressed out at work and feeling like I didn't know what I should be doing. And I was struggling to stay motivated and find stuff that I actually wanted to work on.

[00:02:38] **Ben:** And my wrist just really started to hurt again. So I'm, I'm, you know, like a hundred percent convinced that I've got a little mind body connection going on here. And when my brain hurts, my body hurts.

[00:02:49] **Adam:** well, yeah, I mean, that's well documented stress induced pain stuff and tension.

[00:02:55] **Ben:** So that's a bummer, not loving it.

[00:02:59] **Adam:** Well, before we move on from the, this, section of the show, sorry, here we go. you mentioned the, the trackball, the trackball mouse, I, at one point bought myself a vertical mouse, which, you know, is supposed to be helpful for, you know, wrist pain or whatever, from moving a mouse around. And I was expecting something kind of dramatic and it's like, you know, oh, sorry, my, I forgot my mouse is currently wired, not wireless.

[00:03:20] **Adam:** Here, let me unplug it. You know, you, you go from, you know, like flat and a vertical mouse, they're like, it tips up like 10, 15 degrees and I'm like, this is, this is nothing. What the heck is the point?

[00:03:30] **Ben:** I think my, so I also have a vertical mouse, mine is wireless. So I can say, I think it's like a 60 degree slant.

[00:03:38] **Adam:** one is that? Is that

[00:03:39] **Ben:** This is, this is Kensington.

[00:03:41] **Adam:** Okay. I bought the anchor off of Amazon and I was so just like nonplussed with it that I was like, nope, returning this. No problem.

[00:03:47] **Ben:** Yeah. I, I, I did get a couple that, that did not work out well. And then the, actually the, the track ball one that I have now is also a vertical mouse, but the track, so the track balls on the side. And not on the top or anything like that.

[00:04:00] **Adam:** Interesting. Okay. Yeah. When we talked about the, the different like keyboard stuff last week, when you were talking about, you know, trying to do better ergonomics, I went into a small rabbit hole looking at that kind of stuff. And. I, I, so I was looking at the Kinesis website. They had, they sell all kinds of those ergo specialty keyboards and mice and stuff, and they have a vertical mouse that looks like it's like almost straight up.

[00:04:22] **Adam:** And that really has me interested. I don't

[00:04:24] **Ben:** I, you know,

[00:04:25] **Adam:** drop that kind of money on it

[00:04:26] **Ben:** well, and I think the issue too, is that, the more vertical it goes, the, the more you have to kind of squeeze it from both sides so that when you hit the button, you're not just tapping the mouse to the side, or it has to have something that you actually put your wrist on to sort of hold it in place.

[00:04:42] **Ben:** That was also one of the ones that I did try to get as a vertical mouse. Had this big kind of hand rest you were supposed to use. And it was, it was very uncomfortable, but you know, I'm, I'm not saying don't do it. I'm just saying that it's, it's so trial and error, but there's really. You know, what seems to be really working well for one person doesn't seem to work well at all for other people. Stupid human bodies.

[00:05:05] **Adam:** Yeah.

[00:05:06] **Tim:** Stupid human bodies.

[00:05:08] **Ben:** They're so dumb. Freaking shoulders? They're like your arms are barely even attached to your body.

[00:05:15] **Tim:** Hey, at least when you get knots in your shoulders, you actually have muscles back there and I have knots just, I have like little ping pong balls on a, on a, on a, cutting board.

[00:05:24] **Adam:** Yeah, like held down by a rubber band or whatever. I'm, I'm with you. I don't have like big muscles on my back.

[00:05:28] **Ben:** Yo, I, I'm, I'm, I need to get a massage. Y'all get massages ever?

[00:05:33] **Adam:** I did go to a massage therapy place and I asked specifically for a massage of like my upper back and then like along my spine. And, and she like ignored me. She spent like half the time on like my legs and stuff. Like,

[00:05:45] **Tim:** Well, I mean, to be fair, you have really nice legs.

[00:05:49] **Adam:** Thanks.

[00:05:50] **Ben:** no.

[00:05:50] **Tim:** don't blame her.

[00:05:51] **Ben:** my wife got me a massage. This was, I think back. During Christmas or something, she got me a full body massage. And I'll tell you, having my legs massaged does nothing for me whatsoever. Like I want people to just go at my traps and my shoulders and my back for like a brutal 45 minutes or something.

[00:06:10] **Ben:** I'm like, once you get past that, I'm done. Yeah, exactly.

[00:06:15] **Tim:** We sit down all day.

[00:06:17] **Ben:** Right. Yeah. I've got this tender.

[00:06:19] **Tim:** with the, with the mouse and the, and the, and the keyboard. That's where it hurts,

[00:06:22] **Ben:** Right. This is where I keep my stress all up my neck. So I want to figure out something, something where I can, to your point, tell them what to do and they'll actually do it. I almost would love it. It used to be, I mean, this is really dating myself, but it used to be when you would go to the mall. There would be people doing chair massages.

[00:06:42] **Ben:** You know, the ones where you lean forward. I, I, I probably doesn't exist anymore,

[00:06:46] **Adam:** They do.

[00:06:47] **Tim:** Have him at airports.

[00:06:49] **Ben:** oh, they have many airports. Oh, I got to get a ticket

[00:06:51] **Adam:** well, hang on, Tim, you're not talking about the like electronic ones, right? You

[00:06:54] **Tim:** No, no, an actual person. Yeah.

[00:06:56] **Adam:** Yeah. Yeah. I've seen them, all the ones that I've seen recently have been at drop zones. Right. So like, there'll be a big boogie and a masseuse will come out and

[00:07:03] **Ben:** Oh, that's cool.

[00:07:04] **Adam:** and for people who get old.

[00:07:06] **Tim:** You just need to start jumping on

[00:07:09] **Ben:** Throw, throw myself at the earth and I'll be fine.

[00:07:13] **Adam:** All right.

[00:07:14] **Ben:** All right. Yeah. All right. So, so we're, we're Carol's not here. She would normally be next as, as Adam mentioned. So I'm going to move on to Tim. Tim, what do you got going on?

[00:07:22] **Tim:** Well, I had a triumph, but I'm gonna have to pivot.

[00:07:26] **Adam:** Pivot.

[00:07:26] **Tim:** because,

[00:07:27] **Ben:** Late

[00:07:27] **Tim:** Breaking news, breaking news. So I was before, you know, our call here to record, I was looking on our discord. And so I, there's a new member, a new patron. He goes by SpiffyTech on our discord. and I played last week and I was playing Magic the Gathering online.

[00:07:45] **Tim:** I was like, anybody wants to play with me? And he's like, oh, I play. So we played like five or six rounds. And, and, that was pretty cool hanging. And I said, you know, what's your name? I don't want to keep calling you SpiffyTech. And, and I heard him say his name. I said, okay, cool. Thanks, Ryan. And I kept calling him Ryan and now I get online and I realize he has spiffy text slash Brian.

[00:08:05] **Ben:** Dropping the subtle hint.

[00:08:07] **Tim:** Yeah. So while, while, while Ben's talking, I'm like, Hey dude, I am so sorry. You have to realize I have, you know, bad hearing. I really don't have very good hearing. And I kept calling you Ryan the entire time. He's, and, you didn't correct me. He's like, yeah, I was, you know, I was being polite. I don't want to correct you.

[00:08:21] **Tim:** It happens all the time. And I'm like, Oh man, I'm sorry. I hate being that oblivious old man who like mishears things. But at least, at least I try not to get angry when I get corrected. I try my best. And they're like, no, dad, it's so and so. I'm like, oh, sorry. I realized this is family I've known for five years.

[00:08:39] **Tim:** I kept calling them the Fords. And their name's not the Fords. It's Fours. Like the number four.

[00:08:45] **Adam:** Oh my.

[00:08:47] **Tim:** Yeah, all these years. So anyway, I am so sorry, Brian slash SpiffyTech. Appreciate your being a patron.

## [00:08:55] Tim's Triumph

[00:08:55] **Tim:** But so I'll go my, my, my triumph. So, so corporate mentoring. so that's sort of a thing. So we're part of a big multinational conglomerate, but they buy like smaller software companies and they let the companies just continue to kind of run themselves as small companies, but you sort of get the resources of bigger companies,

[00:09:14] **Adam:** Do they have an interest in buying like a prototyping wireframing app?

[00:09:19] **Ben:** Nice.

[00:09:20] **Tim:** they might be interested in buying like a college reunion and funding kind of thing. Yeah, they would, they would buy your, they would buy your whole company. They don't buy like ideas. They buy companies. but one of the things they encourage is, number one, doing mentoring across the, the organization.

[00:09:38] **Tim:** So, last year I was in London, I get, I think it was around October. probably September, in London and it's, you know, we, huge hotel, the whole company, we bought the hotel out and there's people from Australia and all over. And I was talking to, one person and she was, we had this, thing called initiatives.

[00:10:00] **Tim:** So initiative is where basically you have a new business idea inside your company that you can sell. Most likely to your existing customers and you, you basically have to get at least two, we call them SIGs. So they're special interest groups. So they're existing customers who said, Hey, we're willing to buy this.

[00:10:18] **Tim:** If you do it, we'd like to be on board. And I've talked about this before in the past, but we'd like to be on board and help you build this product. And so I was talking to her about that because she was starting to do that. And I was just telling her the importance of pre selling and making sure you get customers on board because they help you build the thing that Actually, people are going to buy rather than just building a thing that your developers think is cool.

[00:10:40] **Tim:** And, so she reached out to me last week. She's like, Hey, you know, I want to pick your brain about, doing initiatives because, you know, I remember talking to you there and you, we were talking about it. And so I met with her today and unfortunately, I didn't really have a whole lot, I mean, she's telling me about her initiative and she's done everything, pretty much textbook.

[00:10:57] **Tim:** you know, we suggest that you at least get two customers. She had five. pre sold, you know, they're already paid for it, even though they're not using it yet. And, and the only thing, you know, that I did point out was like, her, their initiative is really, they're building a, they do, school administration in Australia.

[00:11:15] **Tim:** So she's in Australia, I just had the call with her before we, we had this, cause it's morning for her and night for me. So, you know, they manage a school, the school payroll, like. Parent teacher things that, and they're just building a mobile app. So the parents could have insight into what is going on at the school and teachers can communicate with parents and, and things like that.

[00:11:35] **Tim:** so really it's kind of a mobile interface to their existing product. Really an initiative should be a business that could, you could sell, split out completely and would not be so, but I mean, there is. Maybe something for that, but I say all that to say this, I just think it's really cool to be able to have, it's kind of like this built in, CEO network that whenever you just need some mentoring, you just have that there and particularly, and that's why they have these annual.

[00:12:05] **Tim:** Meetings with everyone just so you can get together, find stuff out, and then just remember that person and could reach out to them because, you know, I get sold on CEO networks all the time. I got one recently where they want to pay like 600 so that I can hear a remote online speech from, you know, some random CEO, but it's like, that's really.

[00:12:26] **Tim:** That's cool. I can say, Oh, I saw this cool talk by Elon Musk or whatever,

[00:12:31] **Tim:** but it doesn't really help me to having someone who's sort of in the same organizational structure and like, and she had questions about, you know, how do I move up to where you are and things like that? And I'm like, number one, ask yourself if you even want to get there in the first place, cause this job is not necessarily what you think it is.

[00:12:49] **Tim:** so I asked that question, but yeah, just to have that sort of mentoring. And it's kind of casual, it's not, it's not forced on you, but to have it there is, is pretty cool. So,

[00:12:59] **Ben:** You know, as you were saying that it reminded me of a service that I had come across, I mean, probably like 10 years ago, maybe not quite that much. I have no idea what it was called, but it was almost like a paid social network for consulting hours. Like you would, you'd have, there's a, there was a big directory and you would say, Hey, I want to talk to a lead software engineer that has expertise in JavaScript and Node.

[00:13:26] **Ben:** js and I want to book an hour of their time to have a conversation.

[00:13:30] **Adam:** Was it CodeMentor?

[00:13:32] **Ben:** I have no idea. And you,

[00:13:34] **Adam:** think I was on that. Yeah.

[00:13:35] **Ben:** and you could, you could get CTOs and, and, you know, get some, it's like, they weren't doing work for you. They were just having conversations with you. And, I don't know, I did, it suddenly made me want to look that up again.

[00:13:47] **Ben:** Cause I was, I did it once or twice cause I was looking for some help with some JavaScript stuff and more just from a philosophical standpoint, almost more than a technical standpoint, but, I remember it being kind of a cool idea.

[00:14:00] **Adam:** Mentoring is pretty, pretty dope.

[00:14:02] **Tim:** and they do, I mean, they do push that in our organization. They have like seminars when we go to these offsite, you know, meetings about how to, how to mentor people. and so, yeah, so it's pretty cool. And I just really appreciate her reaching it because she's pretty young. I mean, compared to me, most people are, but, in her, in her probably late twenties, but, yeah, cause you know, she's got a plan and she's, and she's killing it.

[00:14:26] **Tim:** So I'm like, yeah, just, Hey, I gave her a little bit of advice, but I just keep, keep doing it. You're sounds like you're on the right track. So

[00:14:32] **Adam:** That's awesome.

[00:14:33] **Tim:** that's cool to see. That's me, how about you, Adam?

## [00:14:37] Adam's Triumph

[00:14:37] **Adam:** Well, everything's coming up millhouse over here. Sorry, boys. I got triumph on triumph on triumph on triumph this week. It's just been a great week for me. so, we've talked about the compliance ad nauseum. I'll just say that compliance wise, we are so, so, so, so, so close to being done. Right. So it's, it's kind of broken up into two phases.

[00:14:53] **Adam:** So there's the readiness phase where like you have to go through and you just complete the whole checklist to go, okay, if we started a review right now, then we'd be in good shape and we could complete the review in compliance. and we are just about at the end of that readiness phase, and then once that's done, we'll start our compliance audit.

[00:15:09] **Adam:** Review period and they'll monitor our stuff for a couple of months and we'll, that'll be the, the review for our SOC 2. And hopefully at the end of that we get the paperwork that comes out of that, you know, like first of the year or something around there. It says, okay, AlumnIQ is SOC 2 compliant.

[00:15:22] **Adam:** That's the goal. And we have like four things left on the checklist to get done before we are done. And the goal is to have that done by October 1st. So, to be ready to start on October 1st is the goal. And

[00:15:34] **Ben:** more month.

[00:15:35] **Adam:** Yeah, but like, you know, getting those four things done shouldn't, it really shouldn't. If, if I could whip people and make them do the things that I want them to do instead of things that are urgent, then, then we'd be done, you know, maybe by the end of next week at the absolute latest.

[00:15:50] **Adam:** but I can't do that. We're getting there and it's, and it's going to be awesome. I'm getting excited by being this close to being done with it. Anyway, setting that aside, the, the thing I'm most excited for right now is we're recording this on a Tuesday. the Tuesday before Labor Day weekend. I am flying on Thursday down to Florida.

[00:16:09] **Adam:** And when I say flying, not me as pilot in command, but myself and a friend of mine will be the only two people in the airplane, a small aircraft, and we're flying down to Florida, and

[00:16:20] **Tim:** you're flying. There's a hurricane coming through. It should be. Pretty much passed by then.

[00:16:24] **Adam:** yeah, it should be, I mean, by Thursday, yeah. and so yeah, we're flying down to Florida. and I'll be taking the tandem instructor rating course, to become a tandem instructor for

[00:16:33] **Ben:** very exciting.

[00:16:34] **Adam:** so yeah, that's, I'm super excited about that. Finally got all my ducks in a row, completed all the tests that I had to take to prepare for that, all the reading, which was ridiculous.

[00:16:42] **Adam:** so very excited for that. And just, this will be my first like cross country, small aircraft flight. You know, I've done probably many dozens of hours of, small aircraft flight. For the purpose of jumping, but, not cross country.

[00:16:57] **Ben:** The question I have immediately is, how close is your parachute going to be to you in this small aircraft?

[00:17:04] **Adam:** far enough away that if we, if I needed it, it would be easier for us to just land. Like it'll be in the plane and I could probably reach back and grab it and try to throw it on. But by the time I got it on, we would be, you know, it would be pretty much landed.

[00:17:20] **Ben:** All right, all right.

[00:17:21] **Adam:** And I'm not going to wear it the whole way down.

[00:17:22] **Adam:** There's like a six hour, six hours of flying. And that doesn't count, you know, stops for fuel and bathroom breaks and stuff. So.

[00:17:29] **Ben:** Very cool.

[00:17:30] **Adam:** Yeah. And then,

[00:17:31] **Tim:** Oh, so I'll wave to you as you fly over. I'll be in Atlanta. I'll be

[00:17:37] **Adam:** Yeah. I'll, I'll send you a picture of your house from, from a few thousand feet up. the, then the other thing that I wanted to list here is, I started a semi-official mentoring relationship, with, a friend who I'll say is also a friend of the show, and, we all know, and, he's kind of a big guy, big, muckety-muck type of guy, , and.

[00:17:59] **Adam:** I'll tell you guys later who it is, but, he's, really, he's mentoring me, you know, in like an engineering management, product owner, product manager type of, Perspective, I guess, is the best way to think about it, right? Like I'm, I'm kind of trapped at this crossroads where like, I'm doing all of these things very heavily and I need to, in order to continue to push my career forward, I have to like, maybe pick a path and push harder down that one way.

[00:18:25] **Adam:** Cause right now I'm just like being pulled equally in all of these directions. And not that I dislike it, but it's not a very productive place to be in terms of like pushing my career forward.

[00:18:36] **Tim:** of serendipitous that we both talk about mentoring. I think it's something that people, one thing. So at the end of the call with, with, Annie that I had, I was like, you know, I really appreciate your level of humility and modesty to be able to ask, you know, For some help and some, some insight on that.

[00:18:56] **Tim:** And that's so many people just try to fake it till they make it. When, I mean, when you can just ask someone who's in a similar situation, you know, just to say, you know, what is your experience of this? And just get some feedback. You can do what you want with it. You're not admitting a failure. You're just admitting you don't know what you don't know.

[00:19:14] **Tim:** And that's, I think that's pretty cool that I think that's cool that you're doing that as well. That, you know, just. To just get that extra, and you know, it's to be the person to ask, honestly, you think, well, I don't want to bother them. They're too busy. It's, it's a honor, honestly. You're like, wow, okay.

[00:19:31] **Tim:** Someone's someone has acknowledged that I have something, a viewpoint or some experience to, to give them. And so when you're asked to be a mentor, it's not like you're being asked to just do work for you. It's just, I just need advice. I just need help. And I think so many people don't do that. But I mean, honestly, and particularly men, it's like we're, we're culturally programmed to not ask for help. And, and honestly, mentoring is not asking for help. It's just asking for, Hey, can I bounce stuff off you? I think that's really

[00:20:06] **Adam:** somebody that I can have a conversation with.

[00:20:08] **Tim:** Yeah. And it's not transactional. It's like the mentor and the mentee. I mean, the mentee is probably getting a little bit more than the mentor itself, but it's not transactional.

[00:20:16] **Tim:** It's like, you do this for me and I'll do this for you. It's like, I just need to bounce this off you. Can I do that? I'm like, yeah, I don't think. I've ever asked someone for mentorship advice and gotten a not too busy or I don't like you or sometimes I just never got a response,

[00:20:33] **Adam:** because you haven't asked me, Tim. Sorry.

[00:20:37] **Tim:** you haven't asked me either. Actually, you did. Nevermind.

[00:20:42] **Adam:** Did I?

[00:20:43] **Tim:** PCI stuff.

[00:20:44] **Adam:** Oh, okay, yeah, there was that. That was a little different. That was like, I

[00:20:47] **Tim:** was, that was, that was, that was transactional. But yeah, that's, that's cool. That's awesome to hear.

[00:20:55] **Adam:** All right, well, let's, stop dilly dallying and get into the show, right? So... Once again, in

[00:21:02] **Tim:** Wait, wait, hold on, hold on. Let's be fair. Triumphs and fails is a vital part of the show.

[00:21:07] **Adam:** Oh, I absolutely agree, you just, we certainly let it get, out of hand and take over the entire show last week, so I'm trying to

[00:21:13] **Tim:** We did. We did. We

[00:21:14] **Tim:** did. All right. We'll do better.

[00:21:18] **Adam:** So, once again, we're gonna try to discuss this topic of moving in honor of Carol, not being able to make it because she's moving, right? And just the, the, the idea of moving gave us a whole lot of different ideas of things we could discuss, so, I guess, man, where anybody have any particular angle on moving that you want to start with?

[00:21:36] **Ben:** you just use an ORM for everything, and then moving on is like a piece of cake.

[00:21:43] **Adam:** That's what Uncle Bob says, right?

[00:21:45] **Ben:** I mean, there's so many different types of moving on, whether it's, personal relationships, work stuff, technical stuff, career stuff. I mean, you're talking just now about moving on, focusing more on, management versus the technology aspects. I think we just got to pick a, pick an ingress

## [00:22:06] Ben Moving on From InVision

[00:22:06] **Ben:** here and go for it.

[00:22:07] **Adam:** mean, since this has been very, topical lately, if you don't mind, can we start with you and your moving on from InVision? I actually do have a question for you, too. Maybe that's a good place to start.

[00:22:18] **Ben:** Let's do it.

[00:22:19] **Adam:** okay, so you mentioned earlier that you have, I guess, semi officially been moved from a full time employee to a part time employee,

[00:22:27] **Ben:** Yes. That.

[00:22:27] **Adam:** I wanted to make sure you're not being exploited, because as a full time employee, you're paid a salary, and you get benefits, right, medical, 401k, et cetera.

[00:22:38] **Adam:** As a part time employee, I don't know what the laws are, especially in New York. I know it could be different there versus where I am in Pennsylvania and stuff. But as a part time employee, you are not necessarily entitled to those same benefits, right? You get the pay, but you may not qualify for 401k insurance, et cetera.

[00:22:54] **Ben:** Yeah. So it's, it's a little unclear as to what is actually going on at this moment. I think I am still technically a full-time employee until I actually sign a contract or receive, you know, my walking papers telling me that I'm no longer a full-time employee.

[00:23:13] **Adam:** Made redundant.

[00:23:14] **Ben:** yes, exactly. And I have received neither of those things.

[00:23:17] **Ben:** So I'm sort of operating. Under the guise of full time employment, as far as I know. and you know, my next paycheck better reflect that as well.

[00:23:32] **Adam:** Do you get paid twice a month or once a month

[00:23:34] **Ben:** on the 15th, so we did have a bunch of people who were technically included in the RIF, the reduction in force, but are being kept on until September 1st as a sort of transitional period. So I think what's happening, or at least what I hope what's happening is that all of. The people who are ending, ending, ending on the first are like, all of their I's are being dotted and T's are being crossed and the HR people are doing.

[00:24:02] **Ben:** Yes, exactly. and I'm actually going to reach out to my CTO tomorrow probably and be like, I'm under a lot of stress. Like, I just feel very stuck and I need to know, yeah, exactly. I just need to know what the world looks like going forward so that I can come up with a plan, because right now I feel like I can't move on.

[00:24:24] **Ben:** and it's, it's very, it's, it's exhausting, honestly. It's,

[00:24:29] **Ben:** uh, it's really, I'm struggling. I, you know, I'm staying positive, but I'm struggling for sure.

[00:24:35] **Adam:** Yeah, I get it. And yeah, I mean, I think this is a really good topic or a really good thing for us to discuss for anybody who might be going through something similar, like, you, it can be very difficult, but you have to advocate for yourself, like, you have to go, you just, just, you have to do what you just said you were going to do and go talk to your boss and say, I just, like, I have no control over this situation, but I need to know what the situation is, right?

[00:25:00] **Ben:** right. Yeah. I need to, I need to channel my Carol. Carol's really good at that stuff,

[00:25:06] **Adam:** she is.

[00:25:07] **Ben:** but, it's interesting.

## [00:25:08] Thinking About Work on Free Time

[00:25:08] **Ben:** So I had this moment the other day. This is on topic, but ever so slowly off topic. So I, I like to let my brain marinate and wander. And I'll be walking the dog and I'm often jumping from topic to topic, you know, I'm walking the dog, I'm listening to a podcast.

[00:25:24] **Ben:** I'm also thinking about stuff that's happening in my life and at work. And you know, this is where we make those fun synergistic connections. You know, you're in the shower, you're walking the dog, you're in the woodshop. Suddenly you, you realize, Oh, what was going wrong with the database or, you know, where the deadlocks are coming from or some product idea.

[00:25:44] **Ben:** So the other weekend I was up in Vermont and we were at this hotel, this Marriott. And for whatever reason, the Marriott was just packed. And, the elevator was taken forever to go from floor to floor. It's like a clown car on every floor, people getting on and off. So I'm in the lobby and I, and I call the elevator and I'm sitting there and I'm, I got some time to kill.

[00:26:06] **Ben:** I know I've got a few minutes to kill before the elevator actually gets the lobby and I started thinking about work and I got like a minute or two into it. And I'm like, what the heck am I doing? Like, why am I spending cycles? Thinking about how to improve features for a product that more or less no longer belongs to me. And, it was a really weird moment. I didn't know, I didn't know what to do with my spare cycles. You know, like I have all this mental capacity that I just need to direct at something. And I'm like, now I have a bunch of things that might be worth thinking about, whether it's. Family stuff, whether it's side projects, like my Dig Deep Fitness stuff, whether it's blogging stuff or work stuff.

[00:26:48] **Ben:** And I, and for the first time in a really, really long time felt like it didn't make any sense to spend time thinking about work. And that was a really weird moment.

[00:26:59] **Adam:** Do you feel like, as a habit for over the last 10 years or whatever, you've gotten into the habit of thinking about work in your free time. So like kind of, kind of working all day long, all week long.

[00:27:12] **Ben:** Well, so I do think so. I mean, I, I don't to say you get into a habit. I think it's, I think that's just how creative people are. And I hope I'm not painting with too broad a brushstroke here, but you know, we've talked about.

[00:27:26] **Tim:** think you're right.

[00:27:27] **Ben:** Hammock driven development and that kind of the, the idea of you got to let your subconscious do a lot of the work sometimes.

[00:27:34] **Adam:** Well, for me, when I hear that, I think of serendipity, right? Like you're reading a book in the hammock. That is in placing your focus in something non work related, whether it's working out or working on some creative. You're painting or you're woodworking or you're reading a book or whatever. But what I'm asking is, do you have a habit of like putting your focus on work stuff outside of work hours?

[00:27:59] **Ben:** I, I guess, I guess what I would say is yes. Also that I almost approach it like,Improv or your yes and-ing. You know, if I'm, if I'm walking the dog and I just get a random thought about a feature, or I'm listening to a podcast and someone mentioned something and suddenly there's a little bit of a crossover connection.

[00:28:18] **Ben:** I'm like, yes, and where can I go with that? And then I try to go down that rabbit hole a little bit mentally to see what other types of connections I can make. And I guess I am on some level choosing to do that, but it also just feels very natural from a problem solving perspective.

[00:28:37] **Adam:** I think that maybe something that gets left out of the discussion when people talk about like, you know, I just work at a company for two, three, maybe four years, then I move on. fine, but what that doesn't give you the opportunity is to like, have a thing that kind of becomes your life's work, right?

[00:28:55] **Adam:** So, like, I've been working at the same company for 10 years, you've been working at the same company for 10 years, both of us much longer than that, actually, but, and, and so, like, maybe when we first started, it was like, yeah, sure, I'll do this job, and it's a job, and you go in and you do it, and then, like, a few years into it, 5, 6, 7 years into it, you're like, I know this topic, right?

[00:29:13] **Adam:** This is, it, and I know the wrinkles on the back of the hand of this product, right? Like, every little in and out, the, the, the minutia of what could go wrong or why, and, It becomes different. It becomes a relationship that you have with the code and the product and continue to build on that for a long, long time.

[00:29:36] **Tim:** Until,

[00:29:39] **Ben:** So,

[00:29:40] **Adam:** it's different when you're not in control of that.

[00:29:41] **Ben:** so as I've been reflecting on this the last couple of days, I've started to think about and maybe question the whole idea of when we think about people who come to work and then go home, there's sort of two buckets that we generally create as a community. There's the people who are very passionate about it and this is their work, but it's also oftentimes their hobby and things they want to research.

[00:30:05] **Ben:** And then we say, oh, then there's this other bucket, these nine to fivers. They come, they get their work done, and then they go home and they leave work at work. And, I'm beginning to wonder how much that, that second bucket is actually possible. Like, how can you do anything and really leave it at the office?

[00:30:24] **Ben:** I, I, I'm, I'm, you know, I'm, I'm, I'm struggling. It's like, if I want to pick a, a, a thing that somehow feels very easy to pick on, it's like... A line cook. And I'm not picking on line cooks, but like, I can imagine thinking, oh, a line cook is cooking at work and then they're at home and that's it. They don't have to think about it anymore.

[00:30:40] **Ben:** But I have to imagine even line cooks are like, oh man, I really overcooked that steak today. Like what went wrong? How can I, how can I do better tomorrow? And they're letting their, their brain think about that. I just, I'm

[00:30:51] **Tim:** or they're cooking on the weekend and like, Oh no, this is absolutely not the way to do

[00:30:55] **Ben:** right, exactly. I just, I,

[00:30:58] **Adam:** yeah.

[00:30:58] **Ben:** I just can't imagine that there are really that many people who. Who can leave their work at work and, I should say like, and not completely hate what they do.

[00:31:10] **Adam:** Well, it's interesting that you say that because I feel like early on in my career, I was very much like a, you know, wake up, think about code, eat breakfast, work on code, eat lunch, work on code, eat dinner, work on code, go to bed type of person. And In more recent years as I have developed other personal interests outside of code, like I played a crapload of video games when I was younger, when I was in college and before that, a little bit after, and My kids are now of the age where they spend a lot of time playing video games and my oldest is constantly telling me about what he's doing in video games and he gets kind of depressed when I'm like, I don't have an interest in playing video games anymore.

[00:31:52] **Adam:** Like, yeah, it's cool and I'm, I'm, you know, I'm happy for you and I'm, you know, I'll come and check out the graphics on the new PS5 thing and that's all great. But like, I'm not going to sit here for eight hours and watch you play a video game. That's just not my thing. And he gets kind of depressed about that and I get it.

[00:32:09] **Adam:** For me. You know, like, as I've gotten into woodworking and skydiving and other things that interest me and take a considerable amount of time, I've gotten better and better at Punching the clock and setting it aside. And I do still very often have that like crossover serendipitous flash of insight like you're talking about.

[00:32:30] **Adam:** What I've gotten good at is like give myself 5 10 minutes to think about that, kind of create a kernel of something to come back to, and then try to take a decent note of what I was thinking about in my to do list for work. And then I'll come back to it during the week, and then I can go back to whatever I was working on.

[00:32:49] **Tim:** I mean, I think the phenomenon we're kind of talking about here is human beings are at their core problem solving creatures.

[00:32:57] **Adam:** Mm hmm.

[00:32:58] **Tim:** So we, we, we all solve problems, whatever, whatever it is, coding, blind cooks, whatever it is, there's a problem. We try to solve it. I'm not going to quote Vanilla Ice. but as the more and more you do, you're in the same ecosphere, right?

[00:33:14] **Tim:** So you're at the same job for the first year, everything you're solving is a problem, everything, because you're not familiar with it. You don't know it. You're trying to solve everything. And so it's constant, constant, constant, constant. But now it's like, okay, I'm 23 years in to the same company.

[00:33:34] **Adam:** Mm hmm.

[00:33:34] **Tim:** you know, the software that I've been dealing with has been, I've been, you know, I have helped craft it and build it.

[00:33:40] **Tim:** Personally for the past 10 years. So initially there was a whole lot of problem solving, and now it's to the point where there's problems to solve because of my experience and knowledge and just time being there, it's not as urgent to solve. Immediately because I know, yeah, I don't really know the answer to this problem right now, but I'm pretty confident that, you know, within 10 minutes of looking at it, I can solve it and tends to be the case.

[00:34:12] **Tim:** So, yeah, so when we talk about that, Ben, it's like, I think, but that doesn't mean that I don't think about it, you know, when I'm in the shower or if I'm driving, those things come up, but it's, it's, it's, it's not a huge driving force.

## [00:34:26] Rewriting and Replatforming

[00:34:26] **Adam:** So can I, can I maybe push the conversation in a slightly different direction here now? We're talking about moving. And if this is not a sore subject, if it, if it, you know, whatever, you tell us if it's fair game, Ben. The, there was an article that we talked about, it was either last week or the week before, where, somebody had some criticisms of InVision and, it may, it gave me thoughts, right?

[00:34:49] **Adam:** So, I'm currently in the middle of trying to figure out how we are going to evolve our application. a totally different tech stack and like, what does that mean? What do we have to do to the current application to make that possible? And then what do we have to do to architecture in general to have them sort of, you know, like, what, what is the path forward?

[00:35:09] **Adam:** And

[00:35:10] **Tim:** or what is not path forward was the thing not to do.

[00:35:14] **Adam:** Well, okay. So I think the classic answer to that question, Tim, is like, let's just rewrite the whole thing in one big bang and, and go. And, and again, I, I have zero inside knowledge,

[00:35:26] **Ben:** That's what we did. It was awful.

[00:35:27] **Adam:** Okay, yeah, I was gonna say, like, speaking from my perspective here on the outside, it sounds like that's what InVision did.

[00:35:31] **Adam:** Like, there's, here's a new version of the thing, try to move people over, you have the struggle of the migrations.

[00:35:37] **Tim:** Mm-hmm.

[00:35:38] **Adam:** And, yeah.

## [00:35:40] Strangler Pattern

[00:35:40] **Tim:** let me, let me give you an example from over 10 years of experience on this. And Ben can jump in on this probably too. So like I was talking to earlier, the company that bought us out, all they do is they buy software companies, right? So they have since, I think when they start, I think they started in 1998.

[00:36:02] **Tim:** So pre tech bubble burst, but anyway, all they do is they buy very vertical software, software that's kind of very sticky, hard to get away from. And when they bought us in 2013. One of the things that their mantras was about, you know, doing a rewrite. Cause typically they're buying companies that are kind of, you know, having a little struggle.

[00:36:22] **Tim:** And so they're at a, they just, you know, replatformed or something. And now they're selling, their mantra was do not rewrite ever. Do not do a full, full platform rewrite ever because they had years of experience of finding out that it just. Doesn't work the way you think it can. Everyone always promised all the, all the tech heads say, Oh yeah, we'll do this.

[00:36:45] **Tim:** It'll be easier. It'd be so much better. They sell you on all the upsides, but they're completely oblivious to all the pitfalls of it. And the pitfalls almost always win.

[00:36:55] **Adam:** So, when you say, like, never rewrite, is that to be taken at face value? Like, once code is working, just leave it alone and let it run in production forever? Or are you saying, don't rewrite in one big bang?

[00:37:06] **Tim:** right. Right. So re rewrite, replatforms. A lot of times it's like, Oh, we're on an old, I mean, some of these companies they were buying in the late nineties were on Cobol or whatever. and, and it's like, we just need to do a complete. Let's just greenfield the whole thing and just write it from the beginning.

[00:37:21] **Tim:** Cause we know it's so much more now, right? We learn from experience. We're going to write it in X language. Doesn't matter what the language is, whatever the cool new hotness is. for sure. And it never works. So what they do say to do is, I mean, it's basically strangler pattern, right? You, you, you eat the elephant one piece at a time.

[00:37:43] **Tim:** And so you, you break those up into, you know, whatever, put them into different services, whatever. But. Just a complete re platform, rewrite, just for the sake of doing it. One a dozen ever, come on time, because... You always have the competing concern of working with your existing tech stack, right? Which you always continually have to support because that's where you're getting your money from.

[00:38:07] **Tim:** You're getting zero money from this complete greenfield that you built. What you do is you take that existing tech stack that you're working on. You take a piece of it and say, all right, we're going to take this little bit here. We're going to write it in the new thing and write it in the new ways and do it right.

[00:38:21] **Tim:** And have. You know, unit tests and all that other cool stuff and our existing elephant's going to continue to use that. And then eventually, and then you move to the next part. And eventually that elephant is now, you know, five or six different modules

[00:38:38] **Adam:** Ooh, interesting.

[00:38:39] **Tim:** that are, have been rewritten and are now in the new tech stack.

[00:38:43] **Tim:** And you, you. You do it so that there is a, because the worst part is, is the painful upgrade for your customers to say, Hey, we're not going to spend a whole lot of time helping you on the old tech stack because that's the old busted and we're working on the new hotness, but it's not going to be ready for a few years.

[00:39:00] **Tim:** So you're just going to have to suffer really bad servers for the next few years. Those next few years turn into almost a decade. and then the new hotness actually isn't that great.

[00:39:10] **Adam:** because it takes you five years longer than you thought to write it. And so...

[00:39:15] **Ben:** Well, and there's one of the issues that we continue to run into and probably even run into to this day. Is that the old system doesn't just sit there and not change. That the old system continues to receive bug fixes and feature improvements. And then the team has to decide, are we going to port those changes over to the new platform?

[00:39:36] **Ben:** Well, the people building the new platform are already so far behind schedule. We can't really have them worry about, growing parity gap issues. We have to just get them to get back to the baseline. But by the time they get to the baseline, the baseline is actually. No longer relevant because the old system has already continued to evolve over the last, however many years it took you to rewrite. Oh, I, you know, it's frustrating because I know the way not to do it at this point, but. don't necessarily, I don't necessarily know how you should do it. If there are parts that you really do need to rewrite, as an example, the legacy platform I work is on AngularJS. AngularJS is end of life, like entirely end of life.

[00:40:21] **Ben:** There's no new versions. There's no security fixes coming out for AngularJS for like the last three years. So, you know, I mean, talk about SOC compliance.

[00:40:31] **Ben:** You probably, yeah, yeah,

[00:40:32] **Adam:** when you say AngularJS, that's like Angular 1,

[00:40:35] **Ben:** yes. 1. X. Exactly. Like you probably can't get SOC compliance for an application that's using a framework that's no longer being updated.

[00:40:43] **Adam:** you can, you just have to say, we're choosing not to upgrade this and we accept the risk.

[00:40:48] **Tim:** You couldn't get a PCI compliance. I promise you that.

[00:40:51] **Ben:** So, you know, if. If you wanted to continue to evolve this application in a way that was really future facing, you'd have to do something, you'd have to do something drastic. And I don't know what that would look like.

[00:41:03] **Adam:** So, I mean, Tim mentioned the strangler pattern, which I, I've done a little research on this. I'm trying to put myself in a position to kind of shepherd our movement from our old platform to whatever ends up being our new platform. And

[00:41:17] **Tim:** So you're moving, you're moving, keeping on

[00:41:19] **Ben:** Yeah, yeah. Yep.

[00:41:20] **Adam:** read up on the strangler pattern, including like where it got its name, you guys, I don't know, you may or may not know this, it gets it from the strangler fig tree, which is, it doesn't actually, you can't just plant a strangler fig tree and it kind of grows up like a tree and exists, it has to like be a parasite on some other tree, like, you know, it gets planted next to that tree and then it grows up around and just sort of like takes over that tree, kind of swallows it a little bit at a time.

[00:41:44] **Ben:** For, for what it's worth, people should do a Google image search for this because those trees actually look really cool.

[00:41:49] **Adam:** Yeah, it's neat. yeah. And, it also made me think of the ship of Theseus, right? So when, when Tim, when you were talking about like, you know, you replace this part and that part and this part and that part, eventually you've got the whole thing moved, right? But it's, it's still kind of the same product, right?

[00:42:05] **Adam:** In an ideal, move, maybe, you know, you've, your product is super stable and, you know, no, no, bug fixes or feature changes over the last couple of years, you could do that full, like true ship of Theseus, it looks exactly like the old ship. But, you know, we know in the world of software, there's no such thing as stable, right?

[00:42:23] **Adam:** It's constantly evolving. I wanted to ask you guys, you know, if Big Bang Wholesale All at Once Rewrite is on one end of the spectrum and Strangler Pattern is on the other, and we can get into a little bit of what Strangler Pattern is, in a minute, but if those are the two ends of the spectrum, are you aware of anything else?

[00:42:42] **Adam:** Between them.

[00:42:43] **Ben:** So the thing that I've heard, and I have zero experience with this, so forgive me if I'm not describing it well, but in the last couple of years, people have started to talk about islands architecture. Where you have a bunch of quasi independent applications running together on the same webpage as these like individual islands.

[00:43:07] **Ben:** And I, and I think that's part of how people have been evolving these applications. We'll have an island that's Angular 1. x and an island that's modern Angular. And then, or, you know, something, something to that effect. I, to me, it sounds like an absolute nightmare. but this does seem to be something that people talk about.

[00:43:25] **Adam:** It's interesting. I've never thought about the islands architecture stuff in the context of replatforming, but that's, I could see how for the right type of application or the right, you know, screens, it could be useful that

[00:43:36] **Ben:** I mean, you have your Svelte modal window and that, and that was kind of a, an

[00:43:42] **Adam:** It is. Yeah. I mean, I, I talked about it in the context of islands. Yeah, for sure.

[00:43:47] **Ben:** but you know, how do you get from one modal to an entire application

[00:43:51] **Adam:** And, and honestly, exactly what you're talking about, you know, building the modal itself was fun and, rewarding and, you know, it worked great. But the interface between, okay, I've got this felt application that runs in memory, and then how do I plug that back into my application that's over here and it expects these data points in this organization?

[00:44:10] **Adam:** How do I get those two to play nice on the front end so that, like, when the page gets submitted, the exact same data is coming back to the back end and all I did was, like, fix the UI that was generating that data. so that was an interesting challenge, for sure.

[00:44:25] **Ben:** Can you, just out of, for my own personal curiosity, can you talk more at all about the actual re platforming that you want to do or is that,

[00:44:33] **Adam:** sure, yeah, I mean, Our application is Mostly built, and when I say mostly, I'm speaking in terms of like lines of code. Mostly built on CFML,

[00:44:42] **Ben:** Oh, so you're already

[00:44:43] **Ben:** done.

[00:44:43] **Adam:** Lucy. What's that?

[00:44:45] **Ben:** You're already done with the rewrite.

[00:44:46] **Tim:** Mm

[00:44:48] **Adam:** And that's how you know Ben is still dreaming. Um,and I don't have any hate in my heart for ColdFusion or CFML, but I don't think it has a future, long term.

[00:45:01] **Adam:** you know, the developer pool is dwindling, the product upgrades are, whatever, I don't even really want to get into that, right? Like it's just...

[00:45:07] **Ben:** right, right.

[00:45:09] **Adam:** Our, as a company, our outlook on CFML is trending down, and the, the trend line is somewhat steep. And so for us, that's a sign that we need to get off of this train.

[00:45:18] **Ben:** So you're, you're re platforming is primarily a backend migration, not so much a frontend migration. Yeah,

[00:45:25] **Adam:** yes. Like, one of the benefits that we see, available to us via replatforming is that, we can shorten dev life cycles, or dev cycles, or whatever they call it, right? So like, if you can. Spend less time developing something, get it out in front of users and, and test it faster than, you can iterate faster.

[00:45:49] **Adam:** You can be more nimble. You can try things and throw them away or try things. And when they succeed, you know, expand on them. and for a variety of reasons, we feel like that it's harder on CFML than it should be, and we get a whole lot for free in terms of that speed, the ability to move quickly, by moving to a more modern.

[00:46:09] **Adam:** Language, right? Like just, again, I don't want to get into

[00:46:12] **Ben:** yeah, yeah, but so, so are you moving to like a, a Node or a Deno or,

[00:46:17] **Adam:** So yeah, that's the, that's the thought is something in that realm. And, and it's not fully nailed down yet because there's some unanswered questions, right? So sort of the general thought right now is Svelte probably on Node, possibly on Deno, when I say Svelte, I guess what I really meant was SvelteKit.

[00:46:35] **Adam:** and, and that is for the monolith, right? So we, we, in addition to our monolith, which is. The monolith right now is ColdFusion, and then everything that's not the monolith is not ColdFusion, right? We've got a ton of Node lambdas, we've got a couple of Python lambdas that are, you know, mostly copy off of the internet and modify to do a little thing that we wanted or something.

[00:46:55] **Adam:** and then, you know, a couple little things here and there, like containers running JavaScript stuff via Node. That's, that's kind of our MO for our more modern things that we've broken off of the monolith is Node. One way or another.

[00:47:07] **Ben:** you know, so early, early on at work when we decided to move ahead with the modern replatforming stuff, one of the guys on my team, this guy, Sean Grigson, had this idea that you stand up a service in the target language, like Golang or Node, And you create a router that's literally like a star, you know, like any path coming into this router, turn around and just make the same request back to the old monolith, the old ColdFusion monolith.

[00:47:40] **Ben:** And then what you could start. So basically create just a pure proxy, like a blind pass through. So that you could essentially recreate, I'm air quoting here, recreate the entire API, but on the new platform, and then slowly just replace routes and say, well, this route no longer goes to the ColdFusion app.

[00:47:59] **Ben:** I'm actually having an explicit route handler for this method in this. Resource and I'm going to, and I'm going to do something new and fancy with it. We, we didn't do that, but it was a very interesting idea as a way to immediately go to the new platform, but then slowly actually kind of backpedal.

[00:48:16] **Adam:** it, it does.

[00:48:17] **Tim:** It's a, it's a shame they didn't do that. Cause honestly we're in the process of thinking of doing something very similar right now.

[00:48:23] **Ben:** Yeah. It's, it's a very, it's a very fascinating idea.

[00:48:27] **Adam:** Well, so I think it, it depends heavily on how you handle routing to begin with. Right. So like if each service kind of start, like if the service starts and then it registers routes with some sort of central routing service, Then that makes sense, right? Like you're saying, okay, I, I exist and I'm going to take priority for everything.

[00:48:47] **Adam:** Dang it. So it's saying I exist and I'm going to take priority for everything. Then that makes sense. Where, and I think that, you know, I'm just thinking about this differently because I've got my fingers in our architecture and I, I see, you know, what makes, what's the obvious choice for us, right? We have, everything goes through.

[00:49:07] **Adam:** We're on AWS, so everything goes through an ALB, an Application Load Balancer. And so you've just got like, okay, if the re and you've got a bunch of these different things that you can do to, to select and filter routes or whatever. But like, you can say, okay, if the host name is this, then send it over here.

[00:49:21] **Adam:** Or if the path looks like this via regex or something, send it over here. you know, if it, if it contains QA in the host name, then it goes to this pool of containers, you know, whatever. Or it can route to a lambda, whatever. and so for me, when I think about the strangler pattern, what I think is like, okay, we.

[00:49:38] **Adam:** Just like pick some, some sort of indicator that will only ever exist in the new platform. Right? So just like if, if the URL contains slash V two slash right, if that is in there, then it's gonna get routed to the new application. And if it doesn't, then it gets routed to the old application or goes through all the old rules and then, which you do is like a series of feature flags.

[00:49:58] **Adam:** Like, I wanna rewrite this module, you know, I create a feature flag that's like, okay, we're gonna use the old if, if the flag is off, then we use the old module. And all the routes and everything stay the same. And then when the flag gets turned on, you know, like, forms start submitting to slash v2, whatever, the links in navigation start taking you to v2, whatever, and you just sort of, like, slowly migrate over there.

[00:50:18] **Adam:** And then, depending on how you choose to visually design the application, it's possible that you could fully do the replatforming and if nobody ever looked at the URL bar, they would never know what was going on, right? And all of that is basically being done with a combination of routing rules for us in the ALB and feature flags.

[00:50:41] **Adam:** And to me, that seems like a really obvious implementation. Like, I asked you guys, like, is there something between Strangler Pattern and, you know, I'm trying to come up with, like, Shotgun. Shotgun upgrade, right? Like, all at once.

[00:50:55] **Tim:** Full Greenfield rewrite.

[00:50:58] **Ben:** I mean, I would say that this, I wouldn't say that strangler pattern is at one end. I think not doing anything is at one end. So your, your ends are not doing anything and big bang rewrite. And I think the strangler pattern is that what's in the middle so

[00:51:12] **Adam:** so you guys agree that that's kind of like the, the gold standard of the, the way to re platform.

[00:51:17] **Tim:** think, I think it's the middle path. Like he's saying,

[00:51:20] **Adam:** I, like, I've, I've read so much about the strangler pattern at this point that I can't think of any other way to do it, really. Like, aside from the, the path that is most likely to blow up in your face, to

[00:51:31] **Tim:** I'll say so. I think knowing a lot of our active people on Discord, a lot of the things they probably face at work or new projects are coming onto if they're consulting is they're running into, you have an early web development kind of page where you have a pattern of, you do a bunch of queries at the top.

[00:51:52] **Tim:** And then you do some visual output at the bottom, right? And some loops in the middle. and so we had a lot of those early, like many, many, many years ago. And what I found the best way to handle those was, is to take those, those pages that are doing kind of the crud and the data and just talk to an API and just make the, the front end data output just stupid.

[00:52:16] **Tim:** And a lot of times early on in, in the early web, we, we made that the page that displayed stuff was super intertwined with the HTML and the

[00:52:24] **Adam:** Mm.

[00:52:25] **Tim:** JavaScript and, and the, the display was, was very complex. Whereas if you just have an API, so first thing, convert everything to an API, make everything API driven, API first.

[00:52:38] **Tim:** So that really the, honestly, the, how you display the data at the end doesn't really matter. It's pretty stupid. It's just. It's templating at that

[00:52:47] **Adam:** Yeah, like, that's another thing. You know, we, we kind of struggle occasionally with, our API. Like, our API is great. We're getting a ton of usage from our customers pulling data out of us and also have a bunch of like our customers push data to us. We've got webhooks coming in from different services that we're using like Zoom and Twilio and Mailgun and all these things are pushing data into us.

[00:53:11] **Adam:** It's great, except that it's never complete. And, and customers are always like, well, how do I get this data? Or can I, can I get it in this organization? Right? And so, Like, as much as I don't think GraphQL is like a silver bullet to solve all problems, one thing that I think would be great for, that I think GraphQL would be great for is, you know, you just define your schema and you say, yes, it's hard to learn and figure out, but this is all the data.

[00:53:40] **Adam:** You can have access to whatever you want. Here you go. You know, dig in and I don't have to create, you know, I have one endpoint. You have access to everything. Go. So I don't have to create a whole bunch of different random stuff and it's going to be consistent, right? You're always going to get the same data types back where...

[00:53:59] **Adam:** Like, that's a thing that frustrates me about our current API is that like, it's, it's very hand rolled, right? You're, you're selecting a query, or you're running a query to get data from the database, then you, build a, an array of objects to return in the, in the response. But you might call it, you might use camelCase in one and snakeCase in a different one, if they're written by two different people or whatever, right?

[00:54:21] **Adam:** Versus like, that's one of those benefits of GraphQL is like, it's, it's all built on the same schema, it's all the same data types and it's going to get, it's going to be consistent. What you get back, no matter what.

[00:54:32] **Ben:** Something I wanted to say, this doesn't address what you just said directly, but, but I, I did want to say that it's tough because you want to move on for almost more socio political reasons and not necessarily, you know, crushing technical problems, but with, but let me just, just to finish

[00:54:51] **Ben:** that thought, but within, within that constraint, I would say, if you're going to do this strangler pattern, I would definitely start with the things that you feel are most.

[00:55:02] **Ben:** Challenging in a ColdFusion context, you know, like when you, when you start a new project and a rewrite is in some ways a new project, it's like, you want to kind of do the fun stuff first and, and I, you know, if there's something where every time you have to do it, you're like, Oh, ColdFusion makes this just harder. Do that first, rewrite that because one. It's going to be a value add every time you go to use it and it's not ColdFusion or, or, and, or it'll help you better understand the mileage you might get out of the rewrite itself. You know, if you just, just to play devil's advocate and I'm, and I'm not trying to sell you out of the idea, but you know, if you have a situation and you're like, Oh, ColdFusion makes this much harder.

[00:55:45] **Ben:** And then you rewrite it in whatever technology and you're like, yeah, this is better. But like. Like it still kind of sucks. And I'm not saying from a, because you're a bad programmer, I'm just saying like, cause it's, there is, there is, what do they call it? Like, not, not as incidental, like there's necessary complexity.

[00:56:01] **Ben:** And like, it turned out it really wasn't the technology. It was just this problem is really hard. You know, you might get a chance to step back and evaluate. Do we want to do everything? Do we want to do just some things? Are there places where this would be more valuable than other places? And how do we focus on those? Anyway, that's a, that just

[00:56:17] **Adam:** Yeah. No, that's

[00:56:18] **Ben:** a lot at you

[00:56:18] **Adam:** insight. Another thing that I think is, has gone so far kind of unsaid is that hiring, skilled CFML developers is very difficult right

[00:56:27] **Ben:** yeah. yeah. I believe it.

[00:56:29] **Adam:** just few and far between because they've all moved on to other things anyway. Mm

[00:56:33] **Tim:** Well, I, and it's not just that. So it's like, we are doing a rewrite, not a rewrite. We're doing a strangler. We're doing a conversion strangler pattern kind of thing, adding more, back end processors to our fold, but doing it in ASP. NET because it's so much easier to find ASP. NET developers. And I have, All the developers I have right now are ASP.

[00:56:56] **Tim:** NET. I've never actually had any, really, really true Scala developers. It's like been myself who is terrible. I'm not a good Scala developer. And someone else, you know, who's kind of figured out along the way. So yeah, we were doing the same thing. It's like, we are adding a new product to it. And then in the meantime, we're also taking kind of like what Ben, you said, where we're building a proxy to the existing Scala API and just have a proxy there, and then we will slowly just rewrite those end points of that API to be a different language and hopefully no one will ever know, hopefully,

[00:57:35] **Ben:** Fingers crossed.

[00:57:36] **Adam:** Yeah. I mean, I guess I could more directly respond to your comment earlier, Tim, about like, When you're doing the rewrite, start with the API and then, you know, build your application based on the API. Like, you know, if it, If you find that you can't build something because it's not in the API, then that exposes something that's missing from your API. So then you need to go add it, for, for completeness sake.

[00:58:01] **Tim:** The only, the biggest drawback with that is a lot of times your API is kind of higgledy piggledy. It's like you have a whole bunch of endpoints. You're like, I don't know what case I'm supposed to use this one for. And it seems like it kind of does something very, so, I mean, that has to be very deliberate and thought out about, all right, you know, each API call really is only doing a very generic thing.

[00:58:25] **Tim:** And if you need to do something a little bit more customized, either you, you know, you're, you're, you're, you're calling service is, is you rolling them together or maybe you build a helper function in the API, I don't know, but a lot of times if you have, if you have 10,000 endpoints in your API, it's like, like, which one do I use?

[00:58:48] **Tim:** In what situation? What is, you know, if, if you're building an API endpoint that only does one thing and it's extremely like an edge case. Okay. I don't know. I don't know why that's there. Should I worry about

[00:59:02] **Adam:** No, and that's why I think that as hard as it's going to be to pull people onto that train, like I'm just, I'm sitting here thinking about customers that I have, meaning universities and some of their staff who just seem so. willfully ignorant of how to use the internet. You know, it's like. The thing that I'm thinking of is we had a process, we talked about this, like the, the warehouse file importer, right?

[00:59:34] **Adam:** I, I rewrote this whole thing to make it queued and they, they push files up onto S3 for us. And then they just, all they need to do is make it a web request. It could, I think it could even be a get, but you know, a get or a post, something like that to say, okay, the file is there and we're ready for you to run the job.

[00:59:50] **Adam:** That's all that they need to do. Like a simple curl and the person that I'm thinking of would like email and say, but like, how do I do that from Oracle? And I'm like, I don't know. I'm not an Oracle person. That's your job.

[01:00:06] **Tim:** that? How do I do that from WordPress? I got that today.

[01:00:09] **Adam:** Like I get so frustrated with people who are not willing to put in the efforts to do their job well. And then they are the first people that come to mind when I think I would love to make our API just like here's GraphQL. Right. It's got the full schema, all of our data. You have access to what you have access to.

[01:00:27] **Adam:** Go nuts.

[01:00:28] **Tim:** And they still won't understand it because I had a guy today. I got on a call. He's like, he's supposedly part of a web development team that is being paid by an insurance company to build their stuff in WordPress. and I was like, okay, let me see. Look, could you hit, he's sharing the screen. Like, could you hit F12 so I can see the developer tools?

[01:00:47] **Tim:** And I blew his frigging mind.

[01:00:50] **Adam:** HACKER!

[01:00:52] **Tim:** Yeah, he's like, what's going on? I'm like, look, you're passing, you're passing this parameter in the URL and it's expecting this one. You can see that right there. He's like, how can I see your code? That's not secure. I'm like, dude, do you even know how the internet

[01:01:04] **Adam:** Wait a minute, is he a senator?

[01:01:06] **Tim:** Yeah, the internet is in a, it's a bunch of tubes. It's not a dump truck. I mean, Jesus, come on.

## [01:01:14] BFF Pattern

[01:01:14] **Ben:** so, so we talk about the strangler pattern, if I can throw a different pattern

[01:01:18] **Ben:** at

[01:01:18] **Adam:** Yeah, go, go.

[01:01:19] **Adam:** uh, the, what's often referred to as the BFF pattern, the back end for front end pattern. I thought we were going best friends forever. Go ahead.

[01:01:27] **Ben:** it's a dual use pattern. and I'm, I hope I don't butcher this, but the idea is that if you have a front end, such as the functionality that needs to be exposed to one of your customers, then you create a backend specific for them and their consumption.

[01:01:44] **Ben:** So in the way that GraphQL kind of can expose the entire world, you can create a very small, very targeted API. That they would consume, but then behind the scenes, that API is really just turning around and doing a bunch of other API calls to aggregate the data. In a, in a meaningful way. And the nice thing about that pattern in this particular case is that the, you know, the, the, the little duck legs that are below the surface of the pond, they can be doing all kinds of crazy stuff and changing how they work over time.

[01:02:18] **Ben:** But from the customer's perspective, the API that you're exposing to them is remains fairly static.

[01:02:24] **Adam:** Right.

[01:02:25] **Ben:** I don't know. I don't know how that gets back to the rewrite, but yeah, yeah,

[01:02:29] **Adam:** yeah, like, keep the existing API and just, like, proxy those requests over to get the data out of GraphQL as appropriate or something.

[01:02:35] **Ben:** yeah, exactly. And if, and if the model for the GraphQL stuff changes. You can always massage it back to what the, the, the customer's expecting on their end.

[01:02:45] **Adam:** Oh, that's, you know what? I like that idea. I'm just gonna be, I'll, I'll say, like, you know, here, the V1 API is, is deprecated. It's not going to change, it still works, but no new additions, no, you know, no new features. If you want the cool, the new hotness, you got to learn how to do GraphQL. And the thing that blows my mind about all this is like GraphQL is so easy because you can expose GraphiQL, the, the like query builder, and just be like, okay, and you get like a drop down.

[01:03:11] **Adam:** Like these are the fields that I want. I know this one has, this one has child properties. I can go get those, right. And like, You just like, you drag and drop and click around to get the query you want. You can see the data populating in, then you go, okay, copy and paste. This is the query I want to run.

[01:03:26] **Tim:** Well, I mean, you know, that they just did add that to the latest version of

[01:03:31] **Adam:** CFGraphQL, is that what I'm hearing?

[01:03:35] **Tim:** They did add it. GraphQL

[01:03:37] **Ben:** It's a, they added a client, so that you can consume GraphQL. I think, I don't think they have a way to like produce GraphQL APIs yet, but that's pretty funny. Good.

## [01:03:47] Gartner Hype Cycle

[01:03:47] **Adam:** That's honestly, that sounds like the most, modern and relevant thing that I've heard somebody say they added to ColdFusion in a long damn time.

[01:03:56] **Ben:** Although, I mean, I, I know that GraphQL was. Super, super exciting for people like, like two years ago. Yeah. It feels like it's kind of gone. What's that like the Gartner hype cycle or something? Like it's, it's kind of,

[01:04:11] **Adam:** That's it's in a trough of disillusionment

[01:04:12] **Ben:** yeah, yeah, yeah. I think so. I'm not saying it's bad. I'm just saying that it's, you don't, you don't

[01:04:17] **Tim:** Just saying people are actually using it and it's probably not as easy as they thought it

[01:04:20] **Adam:** I

[01:04:20] **Ben:** I mean, it's not true about just everything, right? Nothing. I, I always come back to the, to the, to the Rick, rich, Rick, Rich Hickey quote that developers. Understand the value of everything and the cost of nothing.

[01:04:35] **Ben:** That,

[01:04:35] **Ben:** that it's just, it's just so timeless.

[01:04:38] **Adam:** So. yes, it is the Gartner Hype.

[01:04:41] **Tim:** show?

[01:04:41] **Adam:** No, no, we're just going to keep this main show going all night. is the Gartner Hype cycle. And so, right, like, I think, Ben, what you're, what you're referencing, and I agree, if I'm interpreting your statements correctly, is that, like, the hype goes way up high because people are super excited about this new, interesting technology, and then people are like, you know, Wait a minute, they struggle with it or it doesn't solve all their problems.

[01:05:04] **Adam:** It turns out not to be a silver bullet. So, like, it crashes, and interest is down. I think right now where we're kind of like, we're either, according to the Gartner hype cycle chart that I pulled up, it's either, we're either on the slope of enlightenment, which comes after the trough of disillusionment, or the plateau of productivity, right?

[01:05:20] **Adam:** So, it goes back up, but not as high as the original hype peak, right? And

[01:05:26] **Ben:** People are making calculated

[01:05:27] **Adam:** where does this fit in? Yeah.

[01:05:30] **Tim:** I think AI, I think AI is hitting that. That's like, yeah, it's great. It's pretty cool and all. We did chat GPT, but how can anyone make money off of this right now? It's super expensive to even run one.

[01:05:43] **Ben:** Yo,

## [01:05:44] Patreon

[01:05:44] **Adam:** All right. Well, this episode of Working Code was brought to you by Vanilla Ice, who reminds you to stop, collaborate, and listen. And listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording and editing and transcript costs. And I can now happily announce that, transcripts have been published for at the, at the very least episodes zero through, I think it was 140.

[01:06:12] **Adam:** Matt told me. It's bananas, to use a term from my friend, Ben Nadel. Um,and, so those are all up and again, they're just, AI generated. They're, they're not expected to be perfect. And if you would like to improve them. Each and every one of those pages, there should be a link on there that takes you to edit that page on GitHub.

[01:06:29] **Adam:** And so you can fix the transcript and submit it as a pull request and Tim himself will review your pull request. and if it's good, he will, merge it back in and you will have made the internet and our little corner of it a better place. Anyway, all of those costs are covered by the money that we get from our patrons.

[01:06:49] **Adam:** So, thank you all. We couldn't do this every week without you guys, and gals. Special thanks, of course, to our top patrons, Monte and Giancarlo. Your continued huge support is greatly appreciated.

## [01:07:01] Thanks For Listening!

[01:07:01] **Adam:** if you'd like to help us out, you can go to patreon.com/WorkingCodePod, and you can support us for as little as $4 a month.

[01:07:08] **Adam:** and that really helped us out. we do have a new patron this week, a new, free trial. As I mentioned several times recently, we added free trial support to our patrons. If you want to come check out, what is this after show stuff about? What is the extra Discord access like? Come get a free trial.

[01:07:22] **Adam:** We'll get you hooked up and you can decide whether or not you want to stick around. So we, we do have a new patron this week. Ryan, welcome aboard. Hope you decided to stick around.

[01:07:30] **Tim:** not Brian, Ryan.

[01:07:31] **Adam:** This is a different Ryan. Actually, this one is Ryan. Yeah, yeah.

[01:07:35] **Tim:** this one is Ryan now.

[01:07:36] **Adam:** Okay. So, that's gonna do it for us this week. We'll catch you next week.

[01:07:39] **Adam:** And until then,

[01:07:40] **Tim:** Remember, your heart matters, no matter which way you're moving or not.

## [01:07:45] Bloopers

[01:07:45] **Adam:** I'm gonna strangle you.

[01:08:07] **Tim:** Yeah, that's my pattern, baby.

[01:08:10] **Adam:** Instead of that's my

[01:08:12] **Tim:** Yeah. Don't pattern shame.
