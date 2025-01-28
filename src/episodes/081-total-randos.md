---
title: "081: Total Randos"
description: "This week on the show, the crew shares some of the random stuff that they've been dealing with at work."
date: 2022-06-29
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/081-total-randos/id1544142288?i=1000568106571"></iframe>

Sponsors

- [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

This week on the show, the crew shares some of the random stuff that they've been dealing with at work. Carol is about to submit a PR (Pull Request) that accounts for 8-weeks worth of commits; and, she's already warning her engineers that it's gonna be beefy! Ben wonders if he's been fooling himself into his love of Lucee CFML's "Tag Islands"; or, if there's something fundamentally more enjoyable about the developer ergonomics of the `CFQuery` tag. And, Tim's been working on remaining PCI (Payment Card Industry) compliant by scrubbing credit card numbers out of his customer's _"name" fields_; because, as it turns out, customers will jam a credit card number in just about any form field that they find!

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/081-total-randos.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** So that's my, pro tip find a big backlog of information.

[00:00:05] **Tim:** like big backlogs and I can not lie.

## [00:00:28] Intro

[00:00:28] **Tim:** All right, here we go. It's show number 81. we're calling this one, total randos. and, Adam is not here today. He has a little family emergency, so we're gonna start with triumph and fails. And it's actually, I think my turn to go first, right?

[00:00:39] **Carol:** Yeah, it is.

## [00:00:41] Tim's Fail

[00:00:41] **Tim:** So I'm gonna start with a failure.

[00:00:43] **Carol:** Oh,

[00:00:44] **Tim:** So, and I was all excited. You know, I went away for a couple weeks and everything ran and I've been trying to be better about being a good delegator. and I'm, I am I'm, I am delegating and now it's like, it seems like all the fun stuff I wanna do. I have to delegate and all the stuff I really don't wanna do.

[00:01:01] **Tim:** I have to do

[00:01:02] **Carol:** No.

[00:01:05] **Tim:** and I'm not sure how I feel about that.

[00:01:07] **Ben:** Well,

[00:01:08] **Tim:** I've been spending a lot of time doing marketing and sales stuff and just, contracts and yeah,that's not fun. I need a side project, little, I need a little skunkworks project to keep me going. But,

[00:01:19] **Carol:** I was just about to ask if you had one, if you had anything, you could work on define your

[00:01:23] **Tim:** I'm wait. I'm waiting on, I'm waiting on my muse to, to hit me. So we'll see.

[00:01:28] **Carol:** Hmm.

[00:01:29] **Ben:** let me ask you a random question about credit card processing. If you don't mind, this might be something. So I ordered food from our local diner the other day, and I'm waiting at the counter to pick it up. And I look down and pasted onto the counter as a little, a little graphic that says, if you pay with a credit card, then we have to charge you an extra 3% in order to counteract the credit card fee.

[00:01:51] **Ben:** and it got me thinking, so I have an Amazon prime card, which I think gives me 5% cash back on, on any purchases I make through Amazon. So why doesn't, and I assume there's regulatory reasons for this, but like why doesn't someone like Amazon or apple just release a credit card that has 0% fees and just like consume that entire market.

[00:02:17] **Ben:** Like if they're already willing to lose percentages in certain things, why not just become the only credit card that anyone wants to work with?

[00:02:24] **Tim:** But you're working from false premise. They're not losing, you're thinking, okay, it's three seven, 3% they're charging and they're, doing 5% cash back. They're I trust they're not losing money on that. So that, that three, that 3% really is just sort of a. Group aggregate average of what the typical fees are.

[00:02:44] **Tim:** So every single card that you charge it, the actual cost to the merchant, like the store that you're buying from is different every single time. There's no way for them to know when they swipe the card. Right? So, so if it's a debit card is pennies, right? The debit card is super cheap.

[00:03:01] **Tim:** If you're using your bank debit card as a, like a visa, Just a standard credit card itself is pretty cheap as well. It's those points cards, those travel cards, those cash back cards, they're higher. So what they, what you know, that merchant is doing, they're saying on average, it's about 3%. So we're gonna charge a 3% markup.

[00:03:19] **Tim:** but yeah, trust me that 5% cash back. They're not losing money on you.

[00:03:22] **Ben:** Gotcha. All right. All right. I just, especially in an Amazon context,I've heard, and I don't know if it's actually true, but I've heard that they're willing to lose money on a lot of their consumer products because they make so much money on their cloud, their AWS stuff.

[00:03:37] **Tim:** Yeah.

[00:03:37] **Ben:** just, it struck me as like, would there be a value for them to become a dominant credit card provider, but maybe there's no real value in it.

[00:03:46] **Tim:** Yeah. I don't know. I think the. The real issue here is I guess this is a much bigger discussion, but honestly, I mean the credit card, like visa and all them, they don't actually produce cards. They're a network visa, MasterCard. They're just a giant network. And it's so antiquated. the network that they're using with the internet, if there were no credit cards, Up until today.

[00:04:06] **Tim:** And you were building the idea of a credit card company. It'd all be internet based and the fees would be so much lower. There's so many, I mean, I'm a middle man in this whole thing, right? So Visa's getting their cut. I'm getting their cut as the bank's getting their cut. There's so many people with their hands in the cookie jar, that, if you rebuilt it today, you just have one giant network that's global.

[00:04:24] **Tim:** And one person taking their cut per transaction and that would be it. And it'd be so

[00:04:29] **Carol:** be so low, so low.Yeah.

[00:04:31] **Ben:** Interesting.

[00:04:31] **Tim:** So anyway, that's me. That's my fail. But now I feel better. I think it's a triumph cause I taught Ben something. So. Yay. Thank you, Ben. How about you, Carol?

## [00:04:41] Carol's Triumph

[00:04:41] **Carol:** Oh me. so I'm the opposite of you. I delegated and it feels so good.

[00:04:48] **Tim:** It's like we planned it, but we

[00:04:49] **Carol:** oh, we did that. I swear. We didn't. I was thinking of, you know, the song where it's like, reunited and it feels so good. Right. That's what I thought

[00:04:56] **Tim:** I'm surprised you get that reference. That song is like older than

[00:05:00] **Carol:** I was like, I delegated and it feels so good. Yeah, I can't sing, but yeah.

[00:05:06] **Tim:** Well, my triumph is that for the past few weeks, I have been struggling. I have been struggling like daily because I've been on production support. I am handling management roles and

[00:05:16] **Carol:** I have this giant deadline lingering that's due the end of this week, where we're cutting over for UAT testing. And I've just every morning I start work with a to-do list from the previous day because I just can't get everything done. And, as part of this project, someone needed some help and it was kind of.

[00:05:36] **Carol:** Laying on my shoulders to go help this person and go help this person. And I really need to just set side, like set some time aside. Oh, that's hard to say set some time aside to help this person. And, I get up on a call with my boss and my peer, and we're just kind of talking about everything going on and kind of what's happening.

[00:05:57] **Carol:** And I mentioned that I'm just kind of struggling with. Too much on my plate at the moment because of the production support that I have. And typically there's not a lot of production support, but we had a lot of production support for the past few weeks that is not normal. So I was just super busy and then trying to help this engineer that needed help.

[00:06:14] **Carol:** So, My peer was like, why don't you just hand that off to so-and-so he's really good at that. So I just ping both of them and I'm like, Hey, do you have some time free?

[00:06:23] **Carol:** Because this other engineers stuck on writing this entire unit test from scratch because he doesn't really know testing so well, he's new to this, and I really could use the help. And he jumped in, helped him today, halfway through the day, they have almost all the task like structure pretty well has a big.

[00:06:41] **Carol:** Push out and it just went very smoothly and I'm sitting here going, I should delegate things more often and stop trying to like, hold so much on my plate or stop thinking that I have to be the one that, that initiates the help. Like other people can help people and that's fine. And it's all good to delegate something and feel like it, it succeeded.

[00:07:00] **Carol:** So yeah. A delegation

[00:07:05] **Ben:** Very

[00:07:05] **Tim:** cool.

[00:07:06] **Carol:** yeah, that's me. what about you, Ben?

## [00:07:08] Ben's Triumph

[00:07:08] **Ben:** so I'm gonna go with a triumph, but it's not a particularly well articulated triumph. I think I had mentioned on last week's show that I built something and I actually, for the first time, in a long time received one feedback and two a compliment, which is just,

[00:07:23] **Carol:** Yay. That's awesome.

[00:07:25] **Ben:** it is like blowing my mind and I've just been flying so high on that compliment ever since.

[00:07:31] **Ben:** And, so there's no like particular triumph here. I'm just feeling triumphant in general and very motivated. It's like, I feel I don't know, blade is an old reference, right? Anything with vampires, there's always a scene in a vampire where vampire is weak and then they bite into some young, new bile human.

[00:07:49] **Ben:** And then all of a sudden they're like, ah, there's like veins are pumping. Like, that's just, it's like I was beaten down and then I drank some blood and now I just feel amazing.

[00:07:59] **Carol:** Edward I'm so happy your Edward right now. Yeah,

[00:08:03] **Tim:** so, yeah. I'm sorry. Edward is not in vampire vampires. Do not sparkle. That is just, that is

[00:08:08] **Carol:** a vampire. All vampire. Okay. Fine. Ben, your Bella.

[00:08:17] **Ben:** so, and I think kind of as an adjacent note here, for managers, just in general, I think the, sometimes just the lightest touch. Has such a huge impact on people and,

[00:08:28] **Carol:** I agree.

[00:08:29] **Ben:** you don't necessarily think about it or expect it, but, like, again, I've just been flying high for like a week now and feeling great.

[00:08:37] **Carol:** And it sounds so small when you say it, right? Like I did something, someone noticed it and it got a good compliment and it's changed your life for a week. Like that's awesome. Take note. People, take note, compliment your people.

[00:08:51] **Tim:** Yeah, I think, yeah, I think we having an attitude of gratitude, is important. Just, it,

[00:08:56] **Carol:** That's a good way to

[00:08:57] **Tim:** it takes so little just to, to tell a person, thank you. Or, you know what, I'm really glad you're in our team, or, what you did there is pretty amazing. It takes a little out of us, but just, we get so busy and so focused on ourselves sometimes we're, I mean, all humans are naturally selfish creatures.

[00:09:13] **Tim:** We have to work toward being giving. Right. So, but if we do that, it can have such an incredible impact on people's lives and just the culture in.

[00:09:23] **Carol:** Oh yeah.

[00:09:24] **Ben:** And definitely, I think a productivity boost for the company, cuz I, I mean, I can't speak for anyone else. I know that when I'm feeling good, I like, my physicality is the limiting factor. Like I have so many ideas bursting around in my head and I wanna put them on screen. It's like, I literally just can't get it out fast enough.

[00:09:42] **Ben:** And

[00:09:42] **Carol:** Aw.

[00:09:43] **Ben:** and, but you know, that's when I'm feeling good. So I assume the more people make me feel good, the more I can jam out. So

[00:09:50] **Tim:** He's going super soon. I got a compliment today. It wasn't even actually a compliment cause we had a meeting and you guys know how I feel about meetings. I had a meeting today and and my, the person I direct report to, is a meeting that I had called. And so we had the meeting and like 15 minutes in, we were done.

[00:10:09] **Tim:** She goes, that's what I love. That's what I love about having meetings with Tim. We get straight to the point we get done early. I'm like, yeah, you know what I do? It's like, I think that sitting there talking about the weather is a complete waste of time. So let's, let's get into the meat of this, get it done.

[00:10:22] **Tim:** I'll give you 15 minutes of your life back. Exactly. Yeah,

[00:10:24] **Carol:** Yep. And the good thing is that my calendar still shows I'm blocked for 15 minutes, so nobody knows that they can put something on my calendar. So I get to sit and do something. It's great.

[00:10:34] **Tim:** Yeah. When people cancel the meeting, I don't take it off my

[00:10:37] **Carol:** I don't either. Nope.

[00:10:38] **Tim:** I'm like free time, baby.

[00:10:41] **Carol:** Yeah.

[00:10:41] **Tim:** Go work on something I want to,

[00:10:44] **Ben:** I actually try to make it a point to block off an hour every day in the middle of the day, like a lunch. Like, even if I'm not sitting there eating or out eating, I like to have an hour that I know no one else can take on my calendar.

[00:10:56] **Tim:** I have a hard time with that because of my time zone difference. Right. So people are coming in when it's like, time for my lunch. So I either have to do it before they come in, or I just have to find somewhere that I can walk away. Like there are times I don't get up and leave till like four o'clock and I'm like, well, I'll come back or just I'll keep working and call it quits a little early.

[00:11:17] **Carol:** So, but I get that if I were on the same time zone as like everyone else I worked with, I totally would block off every day at lunchtime and make sure that no one put anything on my calendar.

[00:11:27] **Tim:** our glorious leader, Adam is not here today. so we had a hard time coming up with a topic. So it is gonna be kind of a random, it's not really a potluck. it's kind of random things we're gonna talk about here today. and who wants to start us off?

[00:11:40] **Carol:** I can start us off if you want.

[00:11:41] **Tim:** Sure.

## [00:11:42] Carol Is Ahead Of Schedule

[00:11:42] **Carol:** So, we've been on this project for several months now and between some travel for work and between my. My design buddy being wrapped up in production support and me then right following behind him on the next set of production support, I was freaking out all weekend long that we weren't going to meet our deadline for this project.

[00:12:05] **Carol:** So we're supposed to hand this off for U a T. well, we're gonna go QA first, so QA will have it for about a week and then they'll go to UT the following week. So we're supposed to hand this off this Friday. Like it's supposed to be handed off, done delivered and all weekend long. I was like, I should just go code.

[00:12:20] **Carol:** I should just go write something for this because I know how far behind we are on it. I just, it's just bad. Right? I know everything's gonna just kick us in the ass whenever we do this demo, cuz the demo was actually. Well, I am happy to report that. it is dev complete as of today and we are on schedule and actually, well ahead of schedule.

[00:12:41] **Carol:** And I spent my weekend in my head worrying about it for nothing. the few little minor things that were remaining that I thought were gonna be critical and like, Super big fixes that were still needed. I kicked them out in about a day. So I got, had them done yesterday afternoon. And this morning I wrapped up the last ones while I was still having tons of meetings, because that's what I do most of my day now is just meet with people.

[00:13:03] **Carol:** So in between the meetings, I was able to code the final few things and then the other engineer wrapped up one of them. So I think, after today's demo, we officially have zero, work items left on it. So the PR will be up first thing in the morning and it'll be handed off and we are setting pretty.

[00:13:20] **Carol:** And I am just super happy about that. That between the two of us, we both were stressing last week, just cuz of the, we feel like we haven't had a lot of time on it just because of the production support needs and us not being really great at production support cuz he's newer than I am. So he's only been here, Eight months.

[00:13:37] **Carol:** So whenever you're throwing production support at someone who's only been here eight months, our system's huge there's areas we've never even looked at. I still get hit with things. I don't know what they mean. Like I always use the example of, we have something called the FTD or something. Anyways, it's the same, an accurate is the same initials as the flower delivery service.

[00:13:58] **Tim:** about to ask. Yeah.

[00:13:59] **Carol:** Yeah. so someone put in his index to get this like couple times ago was like, Hey, this is failing. And I was. Hey team. When did we start delivering flowers? And they're like, no, it's this other thing for this other thing. And I'm like, this is why acronyms suck. Like you should just call 'em what they are.

[00:14:17] **Carol:** Don't give anything initials or short version, like, just give 'em their name anyways. So he and I spend a lot of time on fraud support, like researching and trying to figure out what it is before we even can come up with a solution. So the fact that we were able to cover prod support for full four, for four full weeks of our development cycle and are done three days early has me super giddy on the inside and even giddy on the outside.

[00:14:43] **Carol:** I'm just so happy right now. Like I could hug this guy, like, if we weren't, if we weren't so far apart, I totally would hug this guy. So just happy. I'm happy. Very happy.

[00:14:54] **Ben:** you say that there's gonna be a PR tomorrow. Is that a PR that is like representative of the last four weeks of work. I mean, how large is that PR?

[00:15:05] **Carol:** this PR is actually the representative of about eight weeks of work. Let's be real. So we started off the project planning and we got brought in a little too early, and this is something that we're learning and that we're figuring out, we're trying to get engineers involved sooner in the conversation with how we design things.

[00:15:24] **Carol:** And not later well, business hadn't fully like gotten all of the kinks out of their design. So they handed off to us. We thought we were maybe a couple conversations away from design. We wrote the tear, wrote the tech doc from the tear sheet and it just went back and forth for several weeks. So we coded uncoded because it was still changing so much.

[00:15:45] **Carol:** So, yeah, it's about 50 files.

[00:15:47] **Ben:** oh, that's that's beasty.

[00:15:50] **Carol:** Yeah, it's a pretty hefty one, but it's, not, maybe it's not. Yeah. Well with all the tests, it's probably, I'll tell you later exactly how many it is, but it's a pretty hefty change. And I am gonna communicate very early in the morning to the people who were putting on it to block off time to go review it because it's not gonna be a quick. we didn't break it out into individual PRS, cuz typically we'll do that. we'll have like a main PR that has like some, maybe we're setting up a gateway and we're setting up a service like that core base for it. Like these are the core pieces of what you need. And then all the extra stuff we spin off as individual PRS.

[00:16:29] **Carol:** So once the base is good and you have an understanding of it, it's easier to just kind of click approve on those smaller ones as they come in like, oh, we're now gonna do it a different way. Small changes. We didn't do it this time because there were so many changes up front. So it is gonna be a hefty one, but we're gonna warn everyone ahead of time to make sure they block off their calendar to get this PR.

[00:16:49] **Carol:** And cuz also we kinda need done by Friday. so two, two things.

[00:16:55] **Ben:** Very cool. So, and then who actually reviews these PRS? So if you have two people doing the work, is it the user acceptance people that are doing the PRS or

[00:17:04] **Carol:** No, my other engineer. So, yeah, so I'll just. Probably ping a few people and see if anybody has availability. And if nobody has availability, I'll put as many engineers on it as I can put in the list. And then hopefully some of them have time. our rule is we have two leads, an architect, and then we have the two managers and the, director of engineering.

[00:17:25] **Carol:** So between the six of us, there's six of us, right? Six of us now. Yeah, between the six of us, there has to be at least one approval by the six of us before it can go to production. That's the, and then it has to have approval by two other engineers, but it's engineers,

[00:17:40] **Ben:** multiple approvals. I see.

[00:17:41] **Carol:** Yeah. You have to have three, you have to have three.

[00:17:43] **Carol:** So one's by a lead. So any of those six people, and then the other two have to be engineers that didn't code on it. It's like, I can't approve it. And the other engineer can't approve it. And that count as our like votes because we code it prior to the

[00:17:56] **Tim:** So are they reviewing the code? Is that for quality? Okay.

[00:18:00] **Carol:** yeah. Yeah. So they'll be doing the PR on it.

[00:18:02] **Carol:** Yep.

[00:18:03] **Ben:** are you finding, having different types of people? Do the PR, is that like, is that actually adding value? I mean, are different types of people finding significantly different types of things?

[00:18:18] **Carol:** So, there's always a way to cheat the system, right? There's always a way to cheat the system. after you work on the team for so long, you learn kind of what people go after. Right? So I know who to put on a PR that isn't going to nitpick it. Right. And I know who is going to tear the thing apart.

[00:18:38] **Carol:** So depending on how critical I want someone to be on it, then maybe I won't put the person who's gonna, tell me, I've put too many spaces on my, in carriage return. Like

[00:18:49] **Carol:** so this is a, total side, tangent. I hate when PRS come back that are just like, oh, you didn't style that.

[00:18:55] **Carol:** Right? Like you should put camel case here. Not an underscore. Freaking does my code work? Like, is it functioning? Let's okay, fine. It's readable. It looks good. And it functions.

[00:19:08] **Tim:** I guess you're not ING then.

[00:19:09] **Carol:** jerk off. No, we don't Lin. We Lin in our type script projects, but we don't li in the CF projects,

[00:19:16] **Tim:** Yeah,

[00:19:17] **Carol:** is there even a linter that works for CF.

[00:19:19] **Tim:** that's a winter. I don't know if it works

[00:19:21] **Carol:** Exactly.

[00:19:22] **Tim:** because we ran one. It took forever. It was slow.

[00:19:25] **Carol:** I do not want to Lin this project. It's massive. It's a old legacy app.

## [00:19:30] Gaming The System

[00:19:30] **Ben:** You know, here's something interesting. you talked about people gaming the system. we just had a meeting on Monday and we're trying, one of the teams is trying to revamp their PR culture a little bit, cuz PR had been taking a really long time to, to get done. And, one of the things that they brought up in the meeting was code coverage and they're leaning now at the idea of completely getting rid of code coverage tools because what they were finding were people were building unit tests that didn't really test anything meaningful, but they were writing them because the continuous integration or whatever, like they would get blocked if they weren't increasing the code coverage with their PRS.

[00:20:10] **Ben:** And they're like, the tests are just becoming useless and they're taking longer to run. So they end up, they just wanna delete a bunch of tests and get rid of the code coverage.

[00:20:17] **Carol:** And they're blocked at the automation level. So it's like your builds can't run at all because automation says you didn't add coverage on it. I've been in that spot before. I remember adding something that was. I found a way in type script and with Jess to go find out if I console logged anything out.

[00:20:35] **Carol:** So inside the bottom of my returns, I was like console. Right? And I was like, this is successful. And does it have a console in there? And it did. So it passed and therefore it got code coverage. And I was like, I'm moving on because I don't have time to deal with it right now. I know it wasn't accurate and I shouldn't have done that, but I did it at the time.

[00:20:54] **Carol:** so like, there are ways around it and that's all you do is you learn how to game the system to bypass a rule. Because someone thought that this number looked right, a hundred percent code coverage might not get you anywhere. It may, for some people it may work and you may get it right. But if you don't have the time to write accurate tests, then a hundred percent code coverage is usually pretty much faked across the board just to get the number.

[00:21:19] **Carol:** Right. Because someone said we had to meet that number. So I get it. I get it. Ben.

[00:21:24] **Tim:** yeah. Charlie Munger, he's an investor. Billionaire. He has a famous quote, says, show me the incentives and I'll show you the outcome. Right. So if the,

[00:21:34] **Carol:** that I don't get it.

[00:21:35] **Tim:** so the, so if you say the incentive is, a hundred percent code coverage or 90% code coverage, right. The outcome's gonna be, you're gonna get that, but you're not necessarily, you're not necessarily going to get what you really mean is like bug-free code.

[00:21:48] **Tim:** Right. because people are, You can just say, well, we really couldn't test this, so we're just gonna mock that out. Right. Well, you mock that out, but really, mocking, it is always gonna give you the desired result, right?

[00:22:01] **Carol:** told you what it was. Yeah. You expect an array. Let's mock an array for you. It's so pretty. It's right. My coat's right,

[00:22:08] **Tim:** Yeah. So I mean, people, the test can be wrong.

[00:22:12] **Tim:** The test can pass, but the test can be wrong. And that's why you can have really good code coverage and then still have bugs in the system because you're not really either using the system in a way that's going to be a real world scenario

[00:22:27] **Carol:** Yeah,

[00:22:28] **Tim:** or you're an area or your tests really are just stupid tests.

[00:22:32] **Tim:** that go green and don't really ex have a chance to expose, bad logic.

[00:22:37] **Carol:** true. Yeah. I mean, the only way it would like in those scenarios where you're like, oh, let me just mock or return back so that it matches what I expect this to be returning. Right. The only way that helps you in the future is if someone does go change it. And now, instead of returning like an array, it's now returning like a query, then, you've hit a problem, right?

[00:22:54] **Carol:** That is the only way that helps otherwise. It's just useless. And how often do people change return types on functions that are already implemented? Like it's not option. It's not often you're like, let me just go change the type that it's coming out of most people, or I find most people are like, oh, this is being used.

[00:23:10] **Carol:** I don't wanna use it that way. I'm gonna create one. Almost like it. That does something different though. That way we have both available for the different use cases for it. So I'm like, oh, here's my query version. Here's my array version. Like you have your dated, we have this and now we can tweak them as needed.

[00:23:25] **Carol:** So yeah.

[00:23:26] **Tim:** you got Ben.

## [00:23:26] Evaluating Habits And New Techniques

[00:23:26] **Ben:** I,

[00:23:27] **Tim:** Mm,

[00:23:32] **Tim:** Fooling like,

[00:23:33] **Ben:** like, I don't know if you

[00:23:34] **Carol:** like trickery, like

[00:23:35] **Ben:** don't know if you ever do this where you have a belief and then you question whether or not you actually believe that thing, or if you fooled yourself into believing that thing, like, like when people who, and this is not to throw shade on any vegetarians, but like, when people are like, oh, you, you can't taste the difference between soy ice cream and regular ice cream.

[00:23:56] **Ben:** And like, they've definitely convinced themselves that's true. It's clearly Yeah. And, and, and,and I, and so the reason that this was point of mind for me was because, in Lucy CFML, which is what I use professionally at work, they have this concept called tag islands, which is when you're inside of a script block, you can do a triple back tick, and you can start to use tags inside of a script, which I really only ever use, because I love.

[00:24:24] **Ben:** CF query tag and the CF query perm tags. Yeah. Yeah. So, and,if I bring this up, Scott St. STRs will, his eye will start to Twitch and he'll tell me that tag islands is the worst thing that's ever occurred, uh, in human

[00:24:36] **Ben:** history.

[00:24:37] **Tim:** I gotta admit

[00:24:38] **Ben:** So, so, so here's where I come back to this idea of fooling myself or do I fool myself?

[00:24:43] **Ben:** So professionally I use Lucy CFML and then on my blog runs an Adobe ColdFusion and Adobe ColdFusion does not have the tag islands. it, so I use query execute in there because all of my components are script based and I just cannot get used to query execute. Like I, I use it and it's, and it does what I needed to do, but I'm just constantly wishing that I had tag island so that I could fall back to using CF query and CF query PR tags and it makes me wonder if.

[00:25:13] **Ben:** There's something fundamentally different about the two approaches. Like it's not just preference, like it's not just, oh, I only use CF query tag. So I assume that's the only thing I want. I actually use both because I'm forced to in different contexts and I still can't get used to one of them. And I don't know if that's just because I'm overcoming 15 years worth of bias towards CF query tags, or if literally there's an ergonomics to the CF tag that is literally just better, which is why I will never be able to feel as positive towards query as I do towards the tag based equivalent.

[00:25:48] **Tim:** man, I love you.

[00:25:51] **Carol:** so cute.

[00:25:52] **Tim:** I mean, I get it. I get it. I mean, but let's see, I think it's safe to say your personality. You are somewhat change averse with certain routines that you have. I mean, would you agree with that, David? Yeah, but, I feel you, because I'll be honest. It took me a long time to learn to like query execute.

[00:26:09] **Carol:** Yeah.

[00:26:09] **Tim:** I really did like, and I guess it's because, just the old days of just like having the select star from table name, where having that block of SQL, it just, it felt so nice to see that air, but then once you start writing, everything in script components and everything, it just that it just is jarring to me now to see that I'll tell you what sold me on.

[00:26:31] **Tim:** And this is, I think this is something that Adam Cameron and I were kind of haranging you about. So what I do like about query execute and sorry, our non ColdFusion CFML developers out there, but what I do like about query execute, it's got three arguments, right? So you have the SQL statement,

[00:26:47] **Carol:** Mm-hmm

[00:26:48] **Tim:** you've got the,

[00:26:49] **Ben:** Yeah.

[00:26:49] **Tim:** the parameters, right?

[00:26:50] **Tim:** So the parameters, whatever, your, in your aware statement, and then you have the options, like the data source and caching information or whatever. what I do like about it. So my kind of template way of building a query execute is I have a function that builds a SQL string. I do that for testing, right?

[00:27:05] **Tim:** So, I'm testing, is this coming back as a string, things like that. And I have a function that builds the parameters, kind of a function that builds the argument. So my query execute is really just kind of one line with three calls to. to functions. And then in the function I can format that beautiful SQL text.

[00:27:24] **Tim:** However, I like in, in the function that builds the SQL statement text, and I can F you know, build that, however I like in there. And it just, it looks clean to me.

[00:27:32] **Ben:** and I only wonder if you're now, if this is. Soy ice cream phase of your development. where like you've so far removed yourself from the ease of tags that you're like, oh, this is actually better. yeah, that's

[00:27:46] **Tim:** You know what I don't like. So one thing I, so sometimes occasionally I'll just because the page is in tags. I will go back to the tags. I really dislike the way CF query per breaks up your SQL statement. I

[00:27:59] **Carol:** do you mean?

[00:28:00] **Tim:** So, so you have this like nice SQL code, and then you have this inside of there. You have these brackets of CF per equals and now, and it's really long and verbose.

[00:28:10] **Tim:** Right. And now my beautiful SQL statement is like chalk full of these tags, these

[00:28:16] **Carol:** yeah.

[00:28:17] **Ben:** true. It does make it a little bit more wordy.

[00:28:20] **Carol:** I like the query execute too, because whenever I output the query, it outputs with the like semicolon and then the parameter it's looking. So whenever I throw it in Oracle and I hit execute, it just pops up the window automatically that says, give me your values.

[00:28:35] **Carol:** You want for all of these inputs. And I don't have to go

[00:28:38] **Ben:** Oh, that's

[00:28:39] **Carol:** I can just,I can just go put 'em in there. Whereas if I do it the other way, it actually puts out the tags and then I'm like having to go comment each one of those out and like put in the value. So I can't just paste it in easy.

[00:28:50] **Carol:** So that's why, whether that's one thing I do like about the query versus just the CF query tag.

[00:28:56] **Ben:** That's pretty cool. I didn't know that, there was a SQL client, like a gooey that would prompt for the inputs. That's pretty cool. I wonder if I can get, I use nav cat for MySQL. I wonder if that's something I could configure it to do.

[00:29:09] **Carol:** Yeah, take a look at it, cuz this is what Oracle does. And Aqua data did the same thing. When I did M just database stuff. I didn't even know it's called now T SQL Microsoft SQL database server. I don't know names of things cuz now I'm only Oracle and I've forgotten everything

[00:29:25] **Tim:** yeah, well, one day maybe we get to use Postgres, so

[00:29:28] **Carol:** Aww. We actually have Postgres.

[00:29:30] **Carol:** I will go there. I will join the dark side

[00:29:33] **Tim:** go. It's not the dark side. It's the light side,

[00:29:37] **Tim:** but no, but I feel you, man, the query ex it took a while. I mean, I think you and I probably started, you probably started a little bit before me in doing co vision. Yeah. Just the beauty of that. That's what sold me on the language, man.

[00:29:49] **Tim:** the ability to like do a sea of query. I mean, back in that, yeah. It's talked to a database so easily like that instead of building these crazy long connection strings and yeah. I was like, wow, that is just elegant. Yeah. So it took a long time for me to learn to love queer execute, but I'm not, I don't think it's soy ice cream.

[00:30:08] **Tim:** It's more maybe Sherbert. I really do like Sherbert. So

[00:30:12] **Carol:** it's yummy.

[00:30:13] **Tim:** it doesn't gimme a tummy ache. So

[00:30:15] **Carol:** Yeah. Orange or green.

[00:30:17] **Tim:** orange, Herbert.

[00:30:18] **Ben:** What is, what is green Sherbert?

[00:30:20] **Carol:** Lime

[00:30:21] **Ben:** lime. Okay. Yeah.

[00:30:22] **Carol:** yum. It's good too. It's good. On like a hot summer day yeah.

[00:30:26] **Tim:** for sure.

[00:30:27] **Carol:** Yep. Throw it in with some, pineapple juice and drink it.

[00:30:30] **Tim:** That's a good idea. I'm thirsty

[00:30:33] **Ben:** This is sorry if I could just round out the thought here I, there is something so nice. Almost luxurious a decade in, I don't know what the right word is about having sort of, actively working in sort in two different modes as a way to kind of constantly check whether you're fooling yourself or whether you actually feel a certain way.

[00:30:53] **Ben:** like, I dunno, one of the ways where I feel like maybe I fool myself is I love SQL. I love relational databases. And, and every time I hear someone get interviewed about document or just other kinds of NoSQL databases, they'll say something to the effect of people use SQL because they have to use SQL.

[00:31:12] **Ben:** And I was thinking to myself, no, I love SQL. Like, it's literally, it allows me to express exactly what I want, but again, it's like, am I saying that because 99.99% of all of my database interactions is through SQL. So I fooled myself into believing this is a very powerful, very elegant language. and I almost wish that I also did a lot more document database interactions so that I could have that constant comparison.

[00:31:34] **Ben:** Am I fooling myself into thinking that Sherbert is as delicious as, full fat milk ice cream? Or am I actually, just fundamentally liking something.

[00:31:46] **Carol:** may be fooling yourself and guess what? That's okay. It's totally fine. Cause I can't, there are things I just, I can't wrap my head around because of what I know. Like I am so set in how I work and how things function and I see, SQL relational databases working for me. So to throw another path at me, I'm like, I don't even know what that would look like.

[00:32:09] **Carol:** Like my brain can't comprehend how to do something if it's not related to each other, like what do I do? I don't understand. So it's okay. It's okay to be fooling yourself. And are you happy? The questions are you happy doing.

[00:32:25] **Tim:** it, is

[00:32:26] **Carol:** Then guess what? It's fine.

[00:32:28] **Tim:** Yeah.

[00:32:28] **Carol:** Don't let anyone tell

[00:32:31] **Tim:** And, I've done the same thing I've played around with document databases and there they worked, but it's like, I don't really know what I earned from that. It's I think my use case is it was different from whatever

[00:32:41] **Carol:** right? Yeah.

[00:32:43] **Tim:** and so yeah, not changing and I'm not leaving Postgres right.

[00:32:47] **Tim:** Or

[00:32:47] **Carol:** Sam boy.

[00:32:49] **Ben:** anyway, that's me. Tim,

[00:32:50] **Carol:** That's a good one. I like it. I like it. So what, what

[00:32:51] **Tim:** Thanks. Yeah. I'm good. Like I said, I love you. he's so thoughtful and emotional. Yeah.

## [00:32:58] PCI Woes

[00:32:58] **Tim:** So I was talking earlier with you guys, before we started recording about, the PCI was,like, like,

[00:33:04] **Carol:** is PCI?

[00:33:05] **Tim:** so that is, oh goodness. I should know what that means.

[00:33:07] **Carol:** Just high level. Like what does

[00:33:10] **Tim:** So PCIs, if you're dealing with, credit card data, you have to be PCI compliance. So that I forget

[00:33:17] **Carol:** it's a compliance.

[00:33:17] **Tim:** it's a compliance thing. Right. So it's, how are you building your software? How are you dealing with the credit card information? Are you storing it? how are you keeping that safe?

[00:33:24] **Tim:** if you're storing it,

[00:33:26] **Carol:** Are you using query execute or are you using CF query

[00:33:29] **Carol:** tag? Yeah.

[00:33:30] **Tim:** Yeah.

[00:33:30] **Carol:** that's Ben's question on the checklist.

[00:33:32] **Tim:** We execute all the way. Well, actually, no, because in Scala, so yeah, that doesn't, but it's like, so we, I mean, we've been doing these audits for years, right? I mean, yeah. Over a decade and they've never caught like credit card numbers in our data, but obviously they missed something because they caught some this time.

[00:33:54] **Tim:** But what happens is, so it's like some people when they go to a payment page, There's, your name and then the credit card number and then expiration date and the CVV code. So they go to their name and they start typing their credit card number and they put it in

[00:34:08] **Carol:** hand

[00:34:09] **Tim:** Carol. Oh, you do that.

[00:34:10] **Carol:** Yeah, I've done that. I've done that a few times. And it's like, oh, we need name like letters here. Like alphas, not numbers. I'm like, oh, wrong.

[00:34:18] **Tim:** Yeah. and just over the years, I never thought, and I mean, this actually even predates me, never just thought that, someone could accidentally cuz our credit card, we do store the last four of the credit card number. Right. So we make sure we try never to store it anywhere. we tokenize it and then we store the token.

[00:34:34] **Tim:** So it's like, we only have four characters. So the past, like 10 years I've showed the auditor the same, like, Hey, so show me where the credit card data is stored. I'm like, okay, here it is. it's only four characters, so yeah. Obviously we can't put it in there. but then yeah, somehow I, maybe their scanner, like it was upgraded or something, but yeah, it found like people would put their credit card.

[00:34:52] **Tim:** It was like, I mean, going back over a decade is like 700 people.

[00:34:57] **Carol:** Oh, that's not bad.

[00:34:58] **Carol:** not a lot when you think of that

[00:34:59] **Tim:** we don't store the CVV. we don't store the, the expiration date. And so honestly, no one could actually have used that data regardless. So it's not a breach that, is material, but yeah, it's like, yeah, super crazy.

[00:35:12] **Tim:** And so basically had to build a bunch of red Xs. I should have called Ben he's the REDX

[00:35:16] **Carol:** yeah.

[00:35:17] **Tim:** but had to build some red X to go find all these credit card numbers and look em in different fields and say, all right, where else could people possibly be? They putting in their address field? I don't know

[00:35:29] **Carol:** I mean you could, yeah.

[00:35:29] **Tim:** too.

[00:35:30] **Tim:** Yeah. so going through all that and then, and just building, so then after that we found that. So I mean, the thing we're not gonna fail the PCI, the whole thing of the PCI audit is to say, all right, are you following the rules? Yes.

[00:35:42] **Carol:** Yeah. I mean, you're doing your best.

[00:35:43] **Tim:** You have data that's bad. Right? How are you gonna clean it up?

[00:35:45] **Tim:** So cleaned it up, went through, found all of them. So, and still looking in a few places, but, and then built a trigger that basically says, if their payment name is just all numbers,

[00:35:57] **Carol:** There's a problem.

[00:35:58] **Tim:** that's probably, unless you're. Elon Musk kid. You probably don't have like a mathematical formula in your name.

[00:36:04] **Tim:** and just, yeah, just the trigger prevents. It doesn't prevent, but just it replaces it. So,

[00:36:09] **Carol:** Ah, nice. Nice.

[00:36:12] **Tim:** so that was, yeah.

[00:36:13] **Carol:** crazy.

[00:36:13] **Ben:** know sometimes I, will just do muscle memory. I'm all tabbing back and forth between things like one password and various login forms and every now and then, muscle memory blips, and I'll paste my password into the username field and hit enter and like, and and then to Carol's point, it'll say, Nope, you're logging failed.

[00:36:33] **Ben:** And I'm like, as an engineer, I'm like, yeah, my password has probably just logged somewhere

[00:36:37] **Tim:** and clear text

[00:36:38] **Ben:** yeah, cuz if they weren't, they probably filtering out passwords, but they may have been logging the username that failed for some reason. And then I have to do a quick calculation. Like, do I need to go and change my password?

[00:36:47] **Ben:** If someone were to compromise this account?

[00:36:50] **Carol:** What happens? We'll see.

[00:36:51] **Ben:** important enough information?

[00:36:53] **Tim:** as it's not your bank account.

[00:36:55] **Carol:** Yeah,

[00:36:56] **Tim:** Yeah. And I'll emit Carolyn. So sometimes I'll go to a checkout page and I, I use, I store my credit card in Chrome. Right. And so it's like, I'll start typing and putting some numbers in like, and it doesn't populate. I'm like, why is it not Popp? Oh, I'm in the name field.

[00:37:09] **Tim:** Okay. Yeah. Yeah. Yeah. Like, but I don't think I ever actually pull the trigger on submitting it.

[00:37:15] **Carol:** I have before. Definitely. it probably was drunk purchases, but

[00:37:21] **Carol:** yeah. I've definitely done it. Yeah. Yeah.

[00:37:23] **Tim:** for sure.

[00:37:29] **Ben:** used to, we used to use this credit card processor. don't quite know where the line falls between the payment gateway and the processor. Cause I think they're technically two different things like we use Recurly

[00:37:40] **Ben:** Mm-hmmcause like we used to use Recurly and I think Recurly is the processor, but then I think internally they turn around and actually post it to a payment gateway or something.

[00:37:53] **Ben:** So they like, they don't control. I don't know. I, anyway, that's not the point of the story. the way they implemented the JavaScript and HTML for inputting the credit card stuff, each form field was actually rendering an iframe that they would load on their end. So, because it was an iframe on a different domain, even if we're someone were to compromise our application and inject JavaScript, there'd literally be no way for them to access the iframe.

[00:38:23] **Ben:** And I think

[00:38:23] **Tim:** we do. We do the exact same

[00:38:24] **Ben:** yeah, it was, I had never seen anything like that. I'm like, oh, this is so complicated and frustrating. And I had to build some like weird angular directives around making sure forms were ready to submit everything. but then someone explained to me all the reasons of the PCI compliance and like why they actually do that.

[00:38:39] **Ben:** it was pretty clever actually.

[00:38:41] **Carol:** I was like, I've been through this before. This sounds very familiar.

## [00:38:45] Finding Things To Work On

[00:38:45] **Ben:** I, so I have talked about in the past having a backlog of stuff, like I always wanna have some

[00:38:53] **Carol:** It's a very sexy backlog and it's what I want in my life of lots of things to work on whenever you wanna work on

[00:38:59] **Ben:** yeah, exactly. and that's,I don't curate it very well, but it's more, it's mostly like a collection of random thoughts. and our support team just started putting together a biweekly meeting with various teams to help bubble up ideas and frictions from the users. And basically just to kind of shorten the distance between user complaints and the backend engineers who might be able to do something about it.

[00:39:23] **Ben:** And I was telling them that I had this backlog and I have a spreadsheet of things that I look at, but it's like three years old. And they were like, if you just go into Zendesk, there's feature requests and. Bug requests. And like you can filter it based on the area of the product and the version of the platform. I was like, what? you're like, you're telling me I can just literally open this at any time and see how many people requested new features last week. And they're like, yeah, it's literally right there. It's just like, oh, mind blowing. This is I'm. I'm so excited. I spent, I probably spent like three hours yesterday afternoon, just paging through.

[00:40:02] **Ben:** Yeah. And like, I probably went through like 30 or 35 pages of feature request dating back to 2017 or something.

[00:40:11] **Carol:** Oh,

[00:40:11] **Ben:** Yeah. I mean, most of them, the vast majority of them are, I'll never be able to even consider building them, but it's

[00:40:18] **Carol:** are some right. You found something. Yeah. Nice.

[00:40:22] **Ben:** So I'm just super excited about that.

[00:40:23] **Ben:** I think. Having a place to look for inspiration is something that all people, I don't wanna say, people, I think all engineers, there should be a way for all engineers to access that information. Because even if product managers and project managers and,product leads and designers, even if they're supposed to funnel down the vast majority of information to the engineers, there's something fundamentally different about executing on a task that someone told you to execute on and executing on a task because you saw it and you were like, that's exciting.

[00:40:59] **Ben:** I wanna work on that. And yeah, just being able to sprinkle those together, zipper them together.

[00:41:07] **Tim:** I

[00:41:08] **Ben:** Yo, it's so good. And it's addictive.

[00:41:12] **Carol:** So we just, I just saw this with one of my engineers. he found a problem and some development he was doing, and I'm not sure I've seen him so excited to work on something. As I saw him work on the next effort, following what he did, which was to correct all the problems he found during this. And he was super excited to get it out and is so proud of it.

[00:41:33] **Carol:** And it's just like, converting some old code to new code and he's so happy about it. And I'm like, man, like there is something to be said about getting to, to find it and do it yourself. Not just having it put in front of you, that we can going, Hey, we need this done, go work on it. Like you found this, you solved it and you're better for it.

[00:41:51] **Carol:** And the system's better for it. So I get it. I get it. Yeah.

[00:41:55] **Ben:** So that's my, my, my pro tip find a big backlog of information.

[00:42:02] **Tim:** like big backlogs and I can not lie. I have a confession to make, so I really like building kind of new stuff. Right. not just new stuff, just like, not like features. Right. Just building something completely

[00:42:16] **Ben:** Like R and D kind of stuff.

[00:42:18] **Tim:** Yeah. But the second it's like, so like, I'm really like all in, on the first customer, like maybe, you have an idea, you pitch a customer, like yeah, let's do it.

[00:42:26] **Tim:** We'll pay for it if you build it. So I'm like all in on that second customer. Oh my God. I have so little, I have so little desired.

[00:42:36] **Ben:** you're like, bro, I I already did

[00:42:38] **Tim:** like there, there's no excitement there

[00:42:40] **Carol:** because

[00:42:40] **Carol:** it's not new it's implementation

[00:42:42] **Tim:** we're just configuring now. and that's where I'm gonna start delegating,

[00:42:46] **Carol:** Yeah.

[00:42:51] **Tim:** but not everything can be like that. So I, I'm a greedy selfish man, and I need to work on that.

## [00:42:57] New Ideas vs Maintaining

[00:42:57] **Carol:** I'm excited. We have an engineer coming back who worked for us a long time ago. and he isn't super like keen on new development. He's not like, oh, I just wanna go do the new thing. He's more of a, Hey, this isn't performing so well, what the hell is going on with it? And he's like, let me go find it. Let me go figure it out.

[00:43:17] **Carol:** He doesn't need to do the new, he gets excited about being able to reengineer something that didn't work the first go around or to restructure something that wasn't handled quite right. That's where he gets super happy at. And I'm excited to work with this guy.

[00:43:30] **Tim:** And that's the only, those stupid personality tests, the Meyers Bri.

[00:43:33] **Tim:** And I mean, I hate 'em, but just the only reason I find any value in them, because sometimes you can kind of find the people that, who are the big idea people and who are the people that, once the big idea is done, just really kind of wanna putter around on it, maintain it, build it, make it better.

[00:43:47] **Tim:** you need a group of people that, that kind of. Cover all those bases. if you don't, it's like you, you can't have like five, six big idea people on the team, otherwise nothing never

[00:44:00] **Carol:** You just, you, yeah. You butt heads and probably get one thing

[00:44:04] **Tim:** exactly. Right. And you can't have too many of the, just the people who are just, they're really excited about maintaining and, incremental increases and features because like, you're not gonna have any innovation,

[00:44:15] **Carol:** Right, right.

[00:44:16] **Tim:** that's a really hard dynamic to, to sustain.

[00:44:19] **Tim:** and then it changes from time to time. There was a point in my life where I was completely fine with just, Hey, just gimme the next bug. I wanna knock this out in an hour. I don't want but it's like, that's not me now. I'm like, I wanna build the next big thing. I don't have turn me loose and let me build something.

[00:44:34] **Tim:** But don't ask me to work on the same thing twice.

[00:44:37] **Carol:** you're right. It does change over time. I'm seeing that with myself. I'm like, I go from these spots where I'm like, I just wanna design new things. And after this project I'm like, I just wanna go work in the backlog. Nobody asks me to do anything new again. I don't wanna like, after architect anything, I don't wanna have to deal with deadlines.

[00:44:52] **Carol:** I just wanna go work. I just wanna go code when I can code, so I get it.

[00:44:56] **Tim:** Yeah. I think it's kind of ebbs and flows in, in, in just your personal energy.

[00:45:03] **Ben:** Well, and then like with me, because I'm on the old platform at work, I know I don't have a lot of time. So somehow fixing bugs doesn't feel like, like that them like rearranging

[00:45:15] **Ben:** chairs on the Titanic. Right? Like I wanna, if I only have a limited amount of time, I wanna be flexing hard as possible. And, Yeah.

[00:45:23] **Carol:** I put my muscles up, but you couldn't see cuz I don't know where my camera

[00:45:27] **Carol:** is.

[00:45:28] **Tim:** I think his are a little bit bigger than yours, Carol.

[00:45:32] **Ben:** It's not a competition. Well,

[00:45:35] **Tim:** But if it was you'd be winning.

[00:45:36] **Carol:** but if it was you'd be winning. Yes. Yes.

## [00:45:39] Patreon

[00:45:39] **Carol:** Oh, this episode of working co was brought to you by Ben's big, sexy backlog and you're right. He has to now and listeners like you, if you're enjoying this show, consider supporting us on Patreon, it's the best way to keep the show running Patreon donations cover the cost of editing all of Tim's mic bumps out and recording

[00:46:01] **Carol:** We can do this every week without those things. So we appreciate all the support and we'd like to give a special thanks to Monte and Gavin. So, yep. Go hit us up on patreon.com/WorkingCodePod.

[00:46:15] **Tim:** And join us on the after show where

[00:46:18] **Carol:** Oh yeah. Big,big things are coming up

[00:46:23] **Ben:** Thank

[00:46:24] **Carol:** and all the Patreons get really access and the after show.

## [00:46:27] Thanks For Listening!

[00:46:27] **Carol:** and you can always leave it to reviewat workingcode.dev/review. so that's it for this week. we'll catch you next time and until then,
