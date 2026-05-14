---
title: "259: Walling Off Your Mental Garden"
description: "This week is a philosophical conversation about what you let into your head and the difference between a snapshot you can hold at arm's length and a living relationship you're quietly being shaped by."
date: 2026-05-14
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/ef922926-1507-432c-bb78-8c9d55997e2e"></script>
<div class="redcirclePlayer-ef922926-1507-432c-bb78-8c9d55997e2e"></div>

This week is a philosophical conversation about what you let into your head — the podcasts, the influencers, the political figures, the friends — and the difference between a snapshot you can hold at arm's length and a living relationship you're quietly being shaped by.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Thursday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

Mentioned in this episode:

- [Fritz Haber (YouTube)](https://www.youtube.com/watch?v=QQkmJI63ykI)

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/259-walling-off-your-mental-garden.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Cold Open

[00:00:00] **Adam:** A broken analog clock is right twice a day, and yet it is still broken,

[00:00:04] **Ben:** Right.

[00:00:04] **Adam:** right? that doesn't make the clock trustworthy. It just means that twice a day you can look at it and it will happen to be right.

[00:00:11] **Ben:** Right. But, but then you can't say, "You know, most of the time I don't agree with this clock, but at 12:03, you know, it's got some pretty good stuff to

[00:00:20] say."

## [00:00:40] Intro

[00:00:40] **Adam:** Okay, here we go. It is show number 259, and on today's show, having failed to successfully solve last week the concept of having three topics in a show, we're gonna try again this week.

[00:00:51] We're just gonna... We're gonna do Ben's thing that he wanted to talk about. So, we're gonna talk about walling off your mental garden, part deux.but first, as usual, let's start with the triumphs and fails. Carol's again, still in the middle of moving across the country as she is wont to do apparently.

[00:01:06] and, so it's just the boys

## [00:01:07] Ben's Fail

[00:01:08] **Adam:** again. Ben, I'm

[00:01:08] gonna come to you first. How's it going, my friend?

[00:01:10] **Ben:** very tired today, so I hope, my malaise doesn't come through too easily in the audio here.

[00:01:16] **Adam:** Gonna drink some caffeine.

[00:01:18] **Ben:** with a little bit of a failure, which is that I am feeling like I don't have a solid strategy for learning about AI and integrating AI into my workflows.and I think it's partly because I just have never had to deal with something like this, meaning so much of what I've learned in the past has been an established technology with a good amount of documentation, obviously a lot more predictability because these things historically have just been very predictable.

[00:01:48] You know, you use a framework to do this, you use a

[00:01:50] **Adam:** Mm-hmm.

[00:01:51] **Ben:** that.and so my strategy has always just been really read the documentation and then try some stuff. And I think maybe part of it is that I just feel overwhelmed by the pace of change, that I know that there's a vast amount of documentation about AI. I think of me just doesn't trust it.

[00:02:13] **Tim:** Mm-hmm.

[00:02:14] **Ben:** it's not even almost that I don't trust it, it's that the amount of documentation is so overwhelming that I don't know what to take out of

[00:02:22] it.

[00:02:24] **Adam:** Well, it's overwhelming,

[00:02:25] but it's also underwhelming 'cause it's documentation on all the, the knobs you can tweak for, you know, the, the harness a- and that sort of thing. But it's not really like to get this output, create this input. It's like... It's a... Well, I mean, that's, it's a non-deterministic... This, this came up on the Discord.

[00:02:42] We talked about this a lot in the last couple of weeks. you know, it, it's a non-deterministic thing, so it's, there is no, "If you put this in, you'll get this out." And, and

[00:02:52] it's constantly changing on top of that.

[00:02:56] **Ben:** Yeah. So I'm finding

[00:02:57] myself kind of at a loss mentally. Like I, I, I'm struggling to motivate. I mean, I'm using the tools. I'm trying to- Play around with the terminology that I use and the language that I use and, know, always having to constantly remember to say things like, "Don't make any changes until you discuss your findings," because half the time it'll just go off and start making changes, and like constantly

[00:03:22] **Adam:** one of those things that you should have in your very short claude.md file.

[00:03:28] **Tim:** Yeah.

[00:03:29] **Ben:** Right. So but, but again, it's like

[00:03:31] one of these things where, uh no strategy f- in my mind for like dead code elimination, like the equivalence of dead code elimination, right? So let's say today I have in my Claude MD file, you know, your best. Don't make any mistakes.

[00:03:45] **Adam:** You're

[00:03:46] **Ben:** never commit or

[00:03:47] **Adam:** joking, right? You don't actually have those sentences in there.

[00:03:50] **Ben:** have never, never commit code without asking

[00:03:53] **Adam:** Okay.

[00:03:54] **Tim:** Mine, mine says, "Claude, you is smart. You is kind."

[00:04:00] **Ben:** So

[00:04:00] **Adam:** And gosh darn it, people like you.

[00:04:02] **Ben:** as a thought experiment, I have these things in there today because I've been tripping over certain outcomes, and I find that if I add this to a Claude MD file or a skill, then it

[00:04:11] **Tim:** Mm-hmm. Yeah, I mean, I, I don't

[00:04:12] **Ben:** it, not 100% of the time, but to a high enough degree where I'm, I want it in there. And then over time, the models are gonna evolve, agents are going to evolve. And with traditional code, I can look at a function and say, "Does anybody call this function? Oh, nobody calls this function anymore? I can just delete this."

[00:04:31] **Adam:** Mm-hmm.

[00:04:31] **Ben:** With something like this, where it's so non-deterministic, at what point do I say, "Okay, I have all these lines of code in my Claude MD file. Do I just randomly start deleting them and seeing if the bad behavior comes back?" Or is it like the perennial CSS problem where I'm just constantly adding CSS to the end of this file because I never know if it's safe to remove

[00:04:52] **Tim:** I share with you my mental

[00:04:53] **Ben:** the, the rando selectors that I've had in there for the last 12 years?

[00:04:57] **Tim:** that

[00:05:01] **Ben:** problem.

[00:05:01] I'm just saying like It's all so and fuzzy,

[00:05:06] **Adam:** Mm-hmm.

[00:05:06] **Ben:** and I, I just, I'm, struggling to come up with a plan that makes me feel like I'm making progress other than just trying to use the tool, but like, you know, use Claude Code directly, which is what we use at work.

[00:05:23] **Adam:** Mm-hmm.

[00:05:24] **Ben:** when I have an outcome that I don't like, try to change the way I prompt it the next time. I've been very hesitant to try and introduce new tools because that to me just feels like this combinatorial explosion of variables.

[00:05:37] **Tim:** doesn't seem to I,

[00:05:39] I

[00:05:42] **Ben:** Sure.

[00:05:43] **Tim:** think of AI, Claude, which I use as well, as basically, first off, it's Google, So it's Google. You can ask it a question and get an answer, and it, and it... But it's Google that I find that is a lot better 'cause it kind of searches everything and it understands your question probably better than, than, than Google, Search does. But then it's also a combination of Google Search plus kind of a junior developer that you can guide. And I, that's really, I mean, the Claude MD is kind of important if there's just, not necessarily for making the LLM do better, but making it fit what you want it to do. Like, I want it to, use certain all the time.

[00:06:32] **Adam:** I want it to not do certain things, and I just explicitly put that in, in there. It's

[00:06:37] like putting a sticky note on that junior developer's monitor, right? Like, remember these things and you, you-- There's only so

[00:06:42] much room for sticky notes

[00:06:44] **Tim:** Right. Eventually, there's too many sticky notes, developer's gonna get bogged down. But it's like, yeah. And so doing that every time for... 'cause every project's a little different. I've been building, like, deployment pipelines and that's very different from, like, building, you know, a credit card payment system. Very different rules I'm gonna give Claude. So

[00:07:02] **Ben:** Hmm.

[00:07:03] kind of how I think about it. I, I try not to overthink that it's, how smart it is, although it does tend to impress me how very good it does.in the Claude file... I mean, obviously our Claude file at work is out of control. I, I got-- It was up at over like 50k characters, I think, and I got it under 40k, and now it's back over 40k. It just, it keeps wanting to sneak things in. But it's so interesting because when I first started learning how to use Claude, was this concept of, well, you can just ask Claude, "How could I have improved this the next time?"

[00:07:41] You know, like, "Oh, we had this misunderstanding in our conversation," or, "You made this mistake and I wasn't clear enough. Is there anything that we should add to the Claude MD file to make it less likely that this mistake is gonna happen next time?" And it'll have a very great answer. You know, like, "Oh yeah, of course, you should add these lines to the Claude MD file, and this way I'll know to do the right thing next time." And then I add it, and then days, weeks will go by, and I find myself like really fighting with it. And when I'm interrogating like, "Why do you keep making this decision over and over again?" It's like, "Well, the code here goes against what's in the Claude file." And I'm like, "Well," I'm like, "Is the Claude...

[00:08:18] Is, is, is what's in the Claude MD file too restrictive?" And it'll be like, "Oh, yes, it's way overly restrictive for the kinds of code we're trying to write." I'm like, "But you're the one who told me to write that."

[00:08:30] you know, it's

[00:08:31] **Adam:** it's non-deterministic.

[00:08:32] **Tim:** Yeah.

[00:08:32] **Adam:** It doesn't--

[00:08:34] Just 'cause, yeah, just 'cause it says it's too much, too restrictive now doesn't mean if you start a slightly different session in 20 minutes, you know, working on a different problem and ask it the same thing, "Is this overly restrictive?" It might be like, "No, this

[00:08:46] is perfect."

[00:08:47] **Ben:** getting caught in my, in the, in the mental trap of like assuming that this thing has any idea what it's talking about.

[00:08:53] **Tim:** Yeah.

[00:08:54] **Ben:** saying... To Tim's point, like it is very impressive, and the things it can do are, are legitimately impressive. it's so impressive that I forget that it's math, that it doesn't actually know anything about programming, and it doesn't actually know anything about what's gonna happen tomorrow, and it doesn't remember even what happened yesterday. But it's, it's so convincing that it's so hard to let go of thinking that it knows what it's talking about in a, in like a much more meaningful way. And then I get so frustrated with myself. Anyway, all to say I, I'm just, I'm,

[00:09:32] I'm just

[00:09:32] **Adam:** Still holding it wrong

[00:09:34] **Ben:** Yeah, I'm still holding it wrong, and I,

[00:09:36] **Adam:** It's your theme for the year.

[00:09:38] **Ben:** I

[00:09:38] just don't know what to do about it. And like I, I, I default to watching kind of edutainment videos about AI because it like makes me feel like I'm doing something productive, but I'm not really. You know, I'm just listening to other people either praise or complain about AI, but I'm not...

[00:09:58] **Tim:** listeners.

[00:09:59] **Ben:** Yeah, exactly.

[00:10:00] **Tim:** Hey,

[00:10:00] **Ben:** Like these fools.

[00:10:01] **Tim:** hey, hey, their hearts

[00:10:04] **Ben:** Your heart matters. So anyway, I'll... I don't wanna take up too much time with

[00:10:10] my

[00:10:11] **Adam:** Well, I mean, so

[00:10:12] to give you some specific advice, I would say maybe consider a claude.md bankruptcy. Just like go maybe not totally empty, but like limit yourself to like five sentences, right? Like if these are the, the prime directives, this is your opportunity to say these are the rules that are inviolable.

[00:10:31] know. And then

[00:10:33] and yeah, I mean, it can grow from there, but like

[00:10:36] **Ben:** But

[00:10:36] **Adam:** start...

[00:10:38] **Ben:** this is gonna sound so stupid, so forgive me for making this analogy. But when I'm in a restaurant and I order a plate of food, and it comes out and, you know, it's like a massive American portion where it's like steak for three people and two sides of fries. I say to myself, "This is what the chef wanted me to have." Like this was the curated experience, so I have to eat it all, because otherwise why would they have made it this big? And I know that that is ridiculous,

[00:11:09] **Adam:** Mm-hmm.

[00:11:09] **Ben:** that same mentality when I'm talking to Claude and I'm saying, "Claude, how can we update the Claude MD file to make you more effective?" And in my mind I'm thinking, well, Anthropic is the chef, and if Anthropic has built a tool and that tool says, "These are the things you should put into the Claude MD file to make it better," in my mind I'm like- Well, of course that makes sense, because why would they give me a tool that tells me how to use the tool incorrectly?

[00:11:36] That would be

[00:11:37] crazy.

[00:11:38] **Tim:** A-and then

[00:11:38] **Ben:** And I know that's not real.

[00:11:39] **Tim:** turn around and say, "What should I take out of my Claude MD file?" And it starts taking stuff out that it told you

[00:11:43] **Ben:** Right. So, so it's

[00:11:46] just, I... It, it's like it's constantly breaking, I'm gonna say the fourth wall, but I know that's not the right, uh, analogy there. But,

[00:11:54] **Tim:** you're saying.

[00:11:55] **Ben:** you know, it's like I keep thinking it's talking to me, but it's not. It's just outputting words.

[00:12:01] Okay, so that's my failure. Carol, as mentioned, is not here, so I will kick it over to

## [00:12:06] Tim's Triumph

[00:12:06] **Ben:** Tim.

[00:12:07] **Tim:** Hey,

[00:12:07] hey. So my triumph is, is not gonna be code related, but, I unlocked a new achievement,

[00:12:15] **Ben:** Oh, yeah.

[00:12:15] **Tim:** of marriage.

[00:12:17] **Adam:** Ooh, congrats

[00:12:18] **Ben:** congratulations.

[00:12:19] **Tim:** yeah, so May 8th was our wedding anniversary. We met on maytheforcebewithyou.com, 1998.

[00:12:27] **Adam:** just for Tim.

[00:12:28] **Tim:** Yep, exactly. Yep. Just... And then, got married the next year on May the 8th 'cause that was a weekend.

[00:12:34] good thing we didn't get married before 'cause there was like a, there was like a tornado that came through. We thought the weather was gonna be terrible. It was an outdoor wedding we-- with a tent and everything. But yeah, tornado came through, and everything was fine, and the weather was absolutely gorgeous that May the 8th.

[00:12:47] So yeah, that was good. So... And we do, we kind of do it up. It's almost like, kind of our Christmas and birthdays all kind of combined. The whole family kind of celebrates it. So we all give e-you know, put presents on the fireplace. And then the May 8th we had pizza night. We, we always have pizza on, on Friday,

[00:13:04] **Ben:** What?

[00:13:04] **Tim:** we open

[00:13:05] **Ben:** Lord

[00:13:05] **Tim:** And I got,a Blackstone grill, which I've been dying for. So got that. And then,I'm, I'm now a Scottish lord.

[00:13:13] **Ben:** Cunningham?

[00:13:14] **Tim:** Yeah. wife, she, she got it for me. She says, "I will only call you this once, but here you are, my Lord Cunningham," and gave

[00:13:21] **Ben:** Yeah.

[00:13:22] **Tim:** You know, it's a little... I don't... I'm pretty sure it's all fake, but they...

[00:13:25] Supposedly you, you, you pay a f- a f- a fee, and they, and they your name, on the deed of, you know, a little piece of square, like two square foot land in Scotland, you become a Scottish lord. 'Cause if you own property, you're a lord.

[00:13:38] **Adam:** Mm-hmm.

[00:13:40] **Ben:** That's

[00:13:40] **Tim:** And then, I got a Damascus s- Damascus-style Japanese chef's knife, which is pretty awesome. I almost cut my finger off with it. So

[00:13:51] **Ben:** awesome.

[00:13:52] **Tim:** So yeah, it was, it was good. It was-good day. But then unfortunately everyone got, except me, I'm, I'm just had allergies for the past week. If I sound stuffed up, that's what's going on, just Georgia allergies. But everyone else got the flu, so I

[00:14:05] **Adam:** Yuck.

[00:14:05] **Tim:** I'm walled off on this side of the house.

[00:14:07] I'm staying in my office and staying away from everyone. I push food under their door l- like a, like a

[00:14:15] **Adam:** To

[00:14:19] **Ben:** That's the worst thing

[00:14:20] about allergies, in my opinion. I mean, obviously being stuffed up is awful, but the not knowing if I'm getting sick

[00:14:27] is so frustrating.

[00:14:30] **Tim:** Yep. Well, I... Once it's been three weeks, 'cause I've been... had allergies really bad for the past three weeks, so sure I'm not sick. It's just 'cause I don't feel sick, I just feel

[00:14:38] **Ben:** Heck

[00:14:39] **Tim:** up and itchy, so. But that's Georgia. We've, we've had a lot of fires. I was telling you guys before we started recording, a little town in south Georgia's completely burned to the ground. Over 100 houses just completely wiped out. Didn't even make a blip in the news cycle, so.

[00:14:54] **Adam:** be clear, not your town, just a little town in Jordan. Yeah

[00:14:58] **Tim:** remember the name. I've never heard of a town, heard of it. But, yeah. So that's me. My triumphs, I, I'm still married.

[00:15:07] **Adam:** That

[00:15:07] **Ben:** yeah.

[00:15:07] **Adam:** is a triumph.

[00:15:08] **Tim:** we'll, we'll see how long that lasts.

[00:15:11] **Adam:** Good luck.

[00:15:12] **Tim:** Good luck. How about you,

## [00:15:13] Adam's Triumphs

[00:15:13] **Tim:** Adam?

[00:15:15] **Adam:** I'm gonna double dip. I'm gonna go with two triumphs just because I've, I've got some really cool stuff going on.

[00:15:20] **Tim:** Cool. Go for

[00:15:21] **Adam:** o- over the weekend, I, got to fulfill a dream I've had for several years now. you know, uh No.

[00:15:29] **Tim:** birthday?

[00:15:30] **Adam:** It's not that kind of show, Tim. Um,for the longest time, for, for a long time now, I've wanted to get an electric car just for, you know, like environmental stuff, and also they're just cool cars.

[00:15:40] They're nice new cars. and so I finally did. I got myself an electric car. I bought a gently used, 2023 Rivian R1T, which I have to ha- I mean, I do and I don't have to have a truck. you know, I guess technically the, the times of year that I need to tow or like haul a bunch of stuff, I could rent a truck if I really needed to, and I could have a different vehicle, but that's just not how...

[00:16:05] **Ben:** if

[00:16:05] **Adam:** the page...

[00:16:06] **Ben:** it doesn't matter, man.

[00:16:07] **Adam:** I guess, yeah.

[00:16:08] **Ben:** anytime.

[00:16:10] **Adam:** fair. I, yeah, I don't know, whatever. But, so I, it's a, it's an electric pickup truck, and it is baller.

[00:16:16] I love it. It's great.

[00:16:18] **Ben:** Yo, having, We, we

[00:16:19] g- got a small Chevy Bolt just for local driving, 'cause we

[00:16:24] **Adam:** mm-hmm.

[00:16:25] **Ben:** really do much more than local driving with this little car. And I'll tell you get a couple of weeks, and then you realize, like, "Oh, we have not had to go to the gas station in a while,"

[00:16:35] **Adam:** Mm-hmm.

[00:16:35] **Ben:** and it is amazing, and that feeling never stops.

[00:16:39] So-

[00:16:39] **Tim:** right

[00:16:40] **Ben:** Congratulations.

[00:16:41] **Tim:** gallon

[00:16:42] **Adam:** Yeah, that

[00:16:42] didn't hurt the,

[00:16:43] convincing the wife part of the the discussion. So that's my first triumph.

[00:16:49] **Tim:** curious, did your insurance costs go up significantly? They did.

[00:16:53] **Ben:** Oh,

[00:16:54] **Adam:** it, it went up about 400 bucks a year.

[00:16:56] **Tim:** Wow.

[00:16:57] **Ben:** that expected with an

[00:16:59] **Adam:** Yeah, I

[00:16:59] knew, I knew that was coming. Yeah. but I mean, hang on, I have a whole spreadsheet. let me pull up my, my Rivian spreadsheet here. Oh, yeah, that's, that's me to a T.

[00:17:08] **Tim:** 100%.

[00:17:09] **Adam:** just... So the, the recurring costs, it-- when you include that increased, insurance of $400 a year and when you include that the state I live in, Pennsylvania, has a additional registration fee, right?

[00:17:23] Like over and above the normal registration fee if you drive an electric vehicle in Pennsylvania, they know that they're not gonna be collecting taxes on the gas that you buy because you're not buying gas. So to recover that, they increase the cost of your registration by $228 a year.I'm gonna be going through tires more frequently.

[00:17:41] **Tim:** Yep,

[00:17:41] **Adam:** But- Right. 'Cause it's a, it's a s- it's like a 7,000-pound truck or something like that. It's very heavy.anyway, so those things are more expensive, but pretty much e- everything else is cheaper. and so when you, like all, when you net it all out, the difference is it's like $445 more expensive on the routine maintenance upkeep type costs per year, and that's including $400 of in- increased insurance, so slightly increased.

[00:18:06] However, what that doesn't account for is fuel. and just based on my typical usage and our current gas prices and, our current electric prices, w- I'm looking at saving $730 a year, somewhere between $730 and, $1,100 a year on powering my vehicle.and also that's before we sign up for, what do they call it?

[00:18:32] Like a time of use-based electric prices. So like basically you can get off-peak rates if you charge your car overnight, that sort of thing, which, you know, we're, we're paying, I have solar with net metering and which is one price, and then a separate price for the, the energy I get from the grid. So between the two, I'm just averaging it, assuming it's about 50/50.

[00:18:52] It's pretty close to that. I'm paying about 18 cents a kilowatt hour. The, the super off-peak rate, which is like midnight to 6:00 AM, is 5 cents a kilowatt hour. So I'm excited to

[00:19:02] make that switch.

[00:19:03] **Tim:** caveat that f-

[00:19:04] **Ben:** Heck yeah, man. Yeah, very cool. Oh, interesting

[00:19:10] **Tim:** insurance is because repairs are so

[00:19:16] **Adam:** Mm-hmm.

[00:19:17] **Tim:** new that pretty much if you get any significant damage in a car wreck, they're gonna total the car

[00:19:23] **Adam:** Yeah.

[00:19:23] **Tim:** than try to repair it almost

[00:19:25] **Adam:** Right.

[00:19:29] **Tim:** them. and so, you know, hopefully you don't wreck and get significant damage where-- I mean, if a bumper here or there, that's, that's fine. But it's like you, you get significant damage, like mechani- particularly mechanical damage,

[00:19:42] **Adam:** Right.

[00:19:43] **Tim:** they're just, they're just gonna wipe the car and, and you're not gonna get the

[00:19:45] **Adam:** Well,

[00:19:46] I mean, fortunately, there's not that much in the way of mechanical stuff. We're talking about motors that have, you know, motors and axles is pretty much the only moving parts.

[00:19:53] **Tim:** Right. But there's

[00:19:54] not a big backlog of supply of

[00:19:57] **Adam:** No. Yeah, no.

[00:19:58] **Tim:** is why, why insurance companies do that, So

[00:20:01] **Adam:** Yeah, you're right. We'll

[00:20:02] see.

[00:20:03] So there's that.

[00:20:04] **Tim:** drive safe.

[00:20:05] **Adam:** Yeah. I, I do still have something like, 24 months and 26,000 miles left on the manufacturer's bumper-to-bumper warranty, and then I've got plenty of,effectively a lifetime warranty on the

[00:20:16] battery and drivetrain stuff, so,

[00:20:19] **Tim:** I, I think if I ever bought an EV, I would probably lease if possible.

[00:20:24] **Adam:** I thought about it.

[00:20:25] It, mathematically it's not a good fit for us just because I don't drive that many miles per year, so the amount of usage versus the price that I'd be paying

[00:20:32] would not be worth it.

[00:20:34] **Tim:** Yeah. It's just I, I think

[00:20:36] their cars are just gonna continue to update rather quickly.

[00:20:38] **Ben:** Bro, let him

[00:20:39] **Tim:** of

[00:20:39] **Ben:** have his triumph.

[00:20:41] **Tim:** Sorry. Sorry. just-- I've been wanting one really-- I'm jealous, basically. I'm

[00:20:45] **Adam:** Sure.

[00:20:46] **Tim:** 'cause I'm jealous.

[00:20:48] **Adam:** Make yourf- make yourself feel better. That's all right. That's okay.

[00:20:50] **Tim:** Yeah.

[00:20:51] **Adam:** I

[00:20:51] **Tim:** you had a

[00:20:52] **Adam:** s-

[00:20:52] **Tim:** Sorry.

[00:20:53] **Adam:** still, yeah, yeah, I still like my tattoo even though you don't like it. That's fine. It's not for you, it's for me.

[00:20:57] **Tim:** That's all right.

[00:20:58] **Adam:** yeah, so second, second triumph, which is, you know, we've been talking for I think about five years now about this ORM migration I've been doing.

[00:21:08] and, so as of today, we finally finished merging the last of the pull requests that I had Claude create when it found a bunch of bugs in our production code, right? So I, I was doing the ORM migration and then sort of like once I wrapped up, I said, "Okay, now do code reviews of all these things." And it was looking for specifically bugs introduced by the ORM migration.

[00:21:30] But in the process of doing that, it also identified, like hundreds of small but real bugs in production. and so I was like, "Well, I don't, I don't want that in my branch. I want the two to be separated." So I was like, "Okay, let's log issues for each of these things." And then I set, did a separate process after the migration stuff was complete that was process all these issues.

[00:21:49] For each one of them, create a branch. In that branch, solve the issue, create a PR, that sort of thing. So then I ended up with this pile of like, I don't know, it was like three or four hundred pull requests, and I'm not just gonna like dump all of that on my team. I'm not gonna be that guy. So I, I just, I said a thing.

[00:22:04] I was like, "Okay, I'm gonna do 25 a day, and it takes however lo- however long it takes." I was like, "25 is kind of the limit," right? You know, the vast majority of these... So out of that 25 a day, let's say 18 to 20 were three lines or fewer, right? So it's like a lot of times it's like, oh, you're missing an encode for JavaScript here.

[00:22:23] **Ben:** Mm-hmm.

[00:22:24] **Adam:** Totally easy to review. The remaining seven or five were somewhere between that three lines and maybe 20 to 30 line changes. So, you know... Yeah,

[00:22:36] **Ben:** reasonable though.

[00:22:36] **Adam:** yeah. It, it was in the ballpark of like, okay, this is a sustainable pace.and so yeah, I was doing 25 a day, and it just took however long it took. There were a couple of times that I was like, "I can tell people are getting fatigued from all these reviews every day," so I just took a day off from it, took a day off from it here and there.

[00:22:52] and so today we merged the last of them in. And so, am checklist-wise prepared to merge my ORM migration branch into QA. However, timing being what it is, the universe,abhorring me getting things done on time, it is now a very bad time of year to rock the boat you know, merging this even just into the QA branch is kind of asking for trouble, eh, especially with like this is the, the peak time of year for our event season and like half the, the company is on the road.

[00:23:24] Yeah, like you got commencements and reunions kicking up, and just like half of our company's on the road traveling and, and dealing with events and stuff. So basically I promised that, we would put it off until June. So, another like

[00:23:38] three-ish weeks and then...

[00:23:40] **Ben:** Yo, this

[00:23:41] could be a triple triumph, which is that in years previous donation season, there would often be periods where you could not record or you'd be recording from a hotel room because you were on the road, you are now one of the muckety mucks and no longer have to go on the road.

[00:23:58] **Adam:** Well, it's not

[00:23:59] because I'm a mucky muck, although that is to some degree true. it's more that we've hired people to do that work specifically, and we have enough of it to keep them busy all year round.

[00:24:10] **Tim:** you

[00:24:10] **Adam:** Yeah. Yeah, I know. Full-time employees. And yeah, so it's... We have sort of-- I've talked about it on the podcast before.

[00:24:16] We have our two products, right? Platform, which is like the minor events, the, uh, alumni association membership, online giving, online directory, you know, the, all these little like death by a thousand paper cuts things that, a alumni association uses.and then our other product is the like one-stop shopping for your huge events, right?

[00:24:39] So where you've got 30,000 people coming back to campus, you're gonna package the activities that they're gonna do and, and the-- they might, you know, want to rent a dorm room as a place to crash for the weekend, and there's products they might need, and packages, and dealing with large groups, and seating arrangements at certain big dinners and stuff.

[00:24:58] Like, all that is built into the signature system, and all that is just overkill for our everyday platform. And so we've got the two sides of the house, and all these other people work for the signature side of the house, and I'm on the everyday side. And...

[00:25:14] **Tim:** Amazon Everyday Basics.

[00:25:16] **Adam:** Yeah, sure.

[00:25:17] **Tim:** you

[00:25:17] **Ben:** be in your

[00:25:18] **Adam:** It does give me a big blue smile, so.

[00:25:20] **Ben:** a

[00:25:23] **Adam:** Yes.

[00:25:26] Will not complain about that. I, I did enjoy some aspects of the... Like, I enjoyed the travel part, and I didn't really mind the, the working. It's the-- I don't necessarily... It, it kinda has like a sales face to it, right? Like customer service I don't even necessarily mind, but like it's the show up at six AM with a, you know, bright-eyed and bushy-tailed, set up my equipment, and then hang out all day retraining people.

[00:25:54] Like there's t- you know, there's four shifts in a day and I gotta train all four of them, on how to use the software and how to deal, troubleshoot the issues, and I gotta be there to refill printer paper, all this other stuff. It's just like

[00:26:05] No, thanks.

[00:26:06] **Tim:** lot of, lot

[00:26:09] **Adam:** yeah,

[00:26:10] that's not my thing.

[00:26:11] **Tim:** Yeah

[00:26:12] **Adam:** so, it, you know, it, it was a nice excuse to fly to a state I'd never been to before and go skydive at a drop zone I'd never been to before, but it's hard to get paid to do that.

[00:26:21] It's a lot of work to get

[00:26:22] paid to do that. So, I was willing to give it up.

[00:26:26] **Tim:** Gotcha.

[00:26:27] **Adam:** So

## [00:26:27] Walling Off Your Mental Garden, Part Deux

[00:26:27] **Tim:** right.

[00:26:29] **Ben:** all

[00:26:29] **Adam:** yeah. Well, let's get into, uh, our mental gardens

[00:26:32] and

[00:26:33] get

[00:26:33] dirty.

[00:26:34] **Ben:** So okay, l-let me, let me try and ease into this. And, and, and not like it's gonna be crazy or anything, but I'm just trying to, like,

## [00:26:39] Self-Knowledge and the Video Game Test

[00:26:40] **Ben:** tell the story. So, my freshman year of college, I roomed with this guy who, as a side gig, wrote video game reviews for magazines. So he had, like, all these different video game systems. And I literally spent my entire freshman year playing, Marvel versus Street Fighter, it was freaking awesome and

[00:27:00] **Tim:** that.

[00:27:01] **Ben:** It was so great. I think it was on the Sega Saturn or something. And then he also had all these special edition games, like he had these, like, little mini characters that would play Street Fighter. And, I don't know, it was just great, and, and I played video games kinda throughout my college years. And I remember, I moved into my own apartment at some point after college, and I did something where I won a video game system, and maybe it was at a conference or at work. Who... I don't even remember. it home, I plugged it in, and I played for, like, four straight hours, and I said to myself, "I can't have this in my room."

[00:27:36] **Adam:** Mm-hmm.

[00:27:37] **Ben:** I won't be able to function as a grown adult I have a video game system at home. And again, like, I know a lot of people love video games. This is not a, admonishment of video games. Again, I'm only talking about my own experience here. I couldn't have it in my house, so I gave them away.

[00:27:54] **Adam:** You're giving me a lot of fodder for my joke at the end of the show here.

[00:27:59] **Ben:** So th- this was, like, one of the earliest memories that I have of, like, me trying to understand the way that I react to the world and how I can try to set myself up for success. I... And, and one of the subsequent memories is I remember hearing this thing on the radio about these things. I think they're called rage rooms, which is where you can rent a room, and it has all these shelvings of materials, TVs, and vases, and tables, and whatnot.

[00:28:31] And you can rent a room and go in with a baseball bat and essentially take out all of your anger, and you can break the TVs and, and... Yeah, exactly. And, and I just remember hearing about that

[00:28:42] **Tim:** Mm. Mm-hmm.

[00:28:43] **Ben:** and feeling in a way that I don't think I could articulate that that seemed extremely unhealthy, if I'm trying to process anger, I should not then be associating that with, well, the way I process anger is violence.

[00:29:00] **Adam:** Mm-hmm.

[00:29:01] **Ben:** that's definitely not gonna be laying down patterns of behavior set me up for success in the long run.Um, guy therapies.

[00:29:10] I... You know, it's like in my 20s and 30s, I feel like I was all about the self-help books and, and there was a lot of introspection. And, you know, when you don't drink and you don't party, you have a lot of free time

[00:29:25] **Adam:** And a, a bunch more money too.

[00:29:27] **Ben:** not hanging out with people.

[00:29:29] **Tim:** can confirm. Been to many conferences with Ben, he does not drink and he does not party.

[00:29:33] **Ben:** Yo. so anyway, you know, that was, like, the early years,

[00:29:37] So then things that I didn't know how to reconcile started to happen in, in

## [00:29:42] Separating the Art from the Artist

[00:29:42] **Ben:** my life. Like, not to me personally, but like- I grew up watching "Braveheart" with Mel Gibson, and "Braveheart" to me is, like, one of the best movies ever made.

[00:29:51] I find it just stunning and fascinating, and the story is great, and the action is great, and just the accents are great. And then it turns out that Mel Gibson is kind of anti-Semitic and kind of a terrible person like...

[00:30:05] **Tim:** shouldn't,

[00:30:08] **Ben:** like, has a lot of unredeemable qualities.but I freaking love "Braveheart," I love the "Lethal Weapon" movies, and I

[00:30:15] **Adam:** Yeah

[00:30:16] **Ben:** uh,"What Women Want," and he's a great actor.

[00:30:19] I'm sorry. I enjoy his movies a lot. then, you know, I love Woody Allen, and then it turns out that Woody Allen maybe, probably, I don't know, but probably did some stuff with his kid that he shouldn't have done and, and like, I love his movies.

[00:30:32] **Tim:** his stepdaughter, so

[00:30:34] **Ben:** Right. And so, like, there was a lot of pop culture wrestling with someone has created art, and it turns out that that person is maybe not the best person,

[00:30:46] **Adam:** Mm-hmm.

[00:30:46] **Ben:** hypothetically, sometimes very actually, and can I continue to enjoy that person's art being hypocritical or

[00:30:56] **Adam:** Yeah.

[00:30:57] **Ben:** setting a bad precedent, setting a bad example?

[00:31:00] **Adam:** There's

[00:31:00] a thing people say, like you have to

[00:31:02] separate the art from the artist.

[00:31:04] **Ben:** Right. Yeah.

[00:31:05] **Adam:** And I, I think I kind of-- I, I-- It could just be rationalizing, but I think I kind of agree when the art was made before, and, and beloved before the artist was found to be a butthead, in whatever form, right? So like J.K. Rowling is, is widely panned now, but Harry Potter was widely loved prior to anybody realizing and, I think most people would say it's, it's okay to still like the original Harry Potter books and movies. those same people would say you probably shouldn't patronize the new Harry Potter stuff 'cause she's trying to take... She's trying to remake it to make more money for herself and less for the

[00:31:46] original cast.

[00:31:47] **Ben:** Hmm.

[00:31:48] **Tim:** I, this is not the way I thought this whole conversation would go. This, this is not... Be- because, yeah, I mean, I got, I got feelings

[00:31:55] **Ben:** Right.

[00:31:56] **Tim:** 'cause it's like, know, you supported it in the past, and you enjoyed it. You learned to love it.but you, you, you said something that someone's irredeemable. I don't ever believe that

[00:32:07] **Ben:** I, I, I agree with that. I agree with that.

[00:32:09] **Tim:** I, I don't ever believe that someone's irredeemable. Just, it, to say that is just giving up on humanity. All of us make mistakes to some degree. Some degrees are worse than others, and some are less, and some do more damage, some do less. But I, I think all of us are ultimately, if we, you know, put our mind to it and we try to reform ourselves, we can get better. S- how long, how long, you know, when we say we shouldn't listen to this art or this music or these movies, what is the, what is the purpose of that? Are we, A, virtue, virtue signaling about ourselves? I'm such a good person, I'm not ever going to watch a movie by so-and-so because they did something bad 20 years ago. Or are we trying to punish them? I don't, I don't truly believe in punishment. I believe in rehabilitation,

[00:33:03] **Adam:** Mm-hmm.

[00:33:03] **Tim:** I think

[00:33:03] **Ben:** Yeah.

[00:33:04] **Tim:** rehabilitated if they want to be. So I, I, I get people say those sort of things, but it bothers me we just say, "Well, this person made a mistake, and they're done forever.

[00:33:16] **Ben:** Yo, and it's very,

[00:33:18] What is it? Sun Tzu's-- I,

[00:33:20] **Adam:** of war?

[00:33:21] **Ben:** I read "The Art of War," or, you know, at least parts of it. there is one thing about that you should never back your enemy into a corner, then the only option he has is to fight.

[00:33:32] **Adam:** Right.

[00:33:33] **Ben:** And it's kinda like, what do you, what do people do if they have no path to redemption? You know? There's no-- That, that's

[00:33:41] not a way to live.

[00:33:43] **Adam:** Yeah, they double down.

[00:33:44] **Tim:** now true, if they've done something criminal,

[00:33:46] they should be prosecuted. But, but, you know, this day and age, like all someone has to do is make an accusation, and people have been accused and got, you know... Some people say got off with it or got away with it, but, you know, they didn't get prosecuted by the legal system.

[00:34:05] **Adam:** Mm-hmm.

[00:34:06] **Tim:** what are we doing where we say, "Well, we're just gonna continue to persecute someone has been criminally cleared of something"? I mean, I, I get it, but it, it's definitely a difficult subject. So yeah.

[00:34:17] **Ben:** Yo.

[00:34:18] **Tim:** trying to keep, you're trying to keep your mind clean. I get that. You're trying to

[00:34:20] **Ben:** Right. Right.

[00:34:21] **Tim:** hygiene process for your brain.

[00:34:23] **Ben:** And it, and it, it gets more complicated in a second, but, but I just wanna do-- No, no, just slightly more

## [00:34:27] Fritz Haber and Moral Complexity

[00:34:28] **Ben:** complicated. I, I wanna go on a, just a quick tangent, because I literally just happened to, over the weekend, be listening to an old Radiolab episode. You know, they were replaying it their podcast.

[00:34:38] **Tim:** Mm-hmm.

[00:34:38] **Ben:** And it was about this German Jewish scientist who won a Nobel Prize for coming up with the way where they, where we can extract nitrogen the air, which then laid the foundation for essentially our ability to mass produce fertilizers,

[00:34:57] **Adam:** Mm-hmm.

[00:34:58] **Ben:** I think is, people say is, like, one of the best that humankind has ever

[00:35:04] **Adam:** Yeah, he, he saved millions and millions and millions of lives by doing that.

[00:35:07] **Tim:** Yeah.

[00:35:08] **Ben:** Yeah.

[00:35:08] Then it turns out he, in World War I, was the guy who created chlorine gas and, and killed, you know, hundreds, thousands of people. to which his wife then killed herself because she was so disgusted by him,

[00:35:24] **Adam:** Mm-hmm.

[00:35:25] **Ben:** his son left Germany and then subsequently, I think, also killed himself. Then, out he created the, poison that was used in the gas chambers.

[00:35:37] **Adam:** Yeah.

[00:35:37] **Ben:** Uh, and like...And he happened to create, you know, the fertilizer that has laid the foundation for our ability to grow as a species. Like, it, it's very complicated. People are very complicated. Life is very complicated. I mean, you know, I'm only trying to say that, like, you can't, you can't create a world in which you say, "Well, can't have fertilizer because the guy who

[00:35:57] created this process is an evil

[00:35:59] **Adam:** Yeah. So his name is Fritz Haber or

[00:36:02] Haber,

[00:36:02] **Ben:** sounds

[00:36:02] **Adam:** probably

[00:36:03] Haber

[00:36:04] I'll, I'll drop a link in the show

[00:36:05] notes to a really good video about him.

[00:36:07] **Tim:** that is sort of to point out we kind of pick and choose, right? So if, if everyone knows the story of Haber, were they gonna stop using fertilizer or eating food that's been fertilized? But some actor that you used-- you know, thought was awesome said some bad

[00:36:20] **Adam:** I guess

[00:36:21] **Tim:** and now is sorry about it and is trying to make recompense and makes a

[00:36:24] **Adam:** the,

[00:36:25] I guess the question though is, are they really sorry or are they just saying sorry so that they can continue to make money?

[00:36:31] **Tim:** True.

[00:36:32] **Ben:** And, and, you know,

[00:36:32] there's, there's a, there's a myriad of, of examples. You know, I buy a phone, that's created by people in a factory that have suicide nets because their lives are terrible. Or, you know, you're, you're buying sweatpants that were literally made by children, and that's awful, but I need my pants.

[00:36:48] You know? I'm s-

[00:36:49] **Adam:** Yeah.

[00:36:50] **Ben:** like, we live in a world where we're making a lot of moral compromises to survive and to be out in the world,

[00:36:56] and that's, that's a

[00:36:56] **Adam:** yeah,

[00:36:57] it goes to, I think something I said last week or the week before about how a lot of companies are pushing down moral choices to us when they should be the ones making the choices themselves. They should be... Yeah, recycling I think was what we were talking about at the time, but like, you know, Foxconn should be improving their work practices and Apple should be sourcing their labor and materials from, companies that don't have work practices that are so bad that people jumping off the building.

[00:37:25] **Ben:** Please,

[00:37:25] **Adam:** Right.

## [00:37:26] Parasocial Relationships and the Slippery Slope

[00:37:26] **Adam:** So yeah, anyway.

[00:37:28] **Ben:** So up until now, I feel like of the examples that I've given are,

[00:37:34] let's

[00:37:34] **Adam:** You

[00:37:34] **Ben:** unidirectional, meaning, like, I'm just a product that was created at a point in time, have not created a relationship with the person who has created that content, whether it's a movie, whether

[00:37:50] it's a song, whether it's a phone, whether it's a piece of clothing

[00:37:53] **Adam:** are consuming a Harry Potter movie, you're not dating J.K. Rowling.

[00:37:59] **Ben:** And

[00:38:00] it, it's a very static thing. You know, the, the Harry Potter book does not continue to evolve time. It's a, it's a fixed product. You know, Braveheart doesn't continue to evolve over time. Mel Gibson's thoughts don't get incrementally baked into it as a product over time.

[00:38:21] **Adam:** Mm-hmm.

[00:38:22] **Ben:** So it-- to me, that's very different than where we are now in the most modern world, where we have all of these, let's call them paras-- what is it? Parasympathetic relationships with

[00:38:37] **Adam:** Mm-hmm.

[00:38:38] **Ben:** where

[00:38:38] **Adam:** Parasocial

[00:38:39] **Ben:** parasocial, thank you, where we feel like we're having these relationships with our social media influencers and our podcasters and even our politicians. And I feel like that is... somehow fundamentally different than everything else that we've talked to so far. And the reason that it is different is because it is so fluid and evolving and changing. this is where I think I h- it, it helps me, it galvanizes me to both clarify my previous views where I had conflicts, and it helps me understand the kind of gut reactions that I'm having to things that I see in today's world.

[00:39:29] I

[00:39:29] **Adam:** I think you might be onto

[00:39:30] something, right? With the whole, like, parasocial relationships and stuff. Like, A, the whole, like, separate the art from the artist thing, that's been something people have been saying for a very long time, probably since, you know, like paintings and-- Well, probably since, like, paintings and books were the, the, the, the, the recent technology in art, right?

[00:39:53] and now that we've got, I'm gonna gag when I say it, influencers as, as a job, you know, like at that point, now their personality and their content, ugh, as I say here on my content, I guess, it, it... Like, those things are their product, and so now the... Or their art. And so if you are appreciating the art, to some degree you can't separate that from the artist.

[00:40:23] And then people, interact with enough of it, right? You listen to enough podcast episodes, you watch enough YouTube videos, you start to feel like you know a person.

[00:40:31] You

[00:40:32] start to feel like

[00:40:32] you have a ton in common.

[00:40:34] **Ben:** okay

[00:40:35] **Tim:** I

[00:40:35] mean, this kinda goes back to the... Let me jump in. So, I mean, back in the olden days, there was the idea of honor, chivalry, and reputation, and people would, you know, duel To the death over, over a slight over the reputation because their reputation was so important to them. And that's, it's kind of what, you know, pe- we're going back to this personal... talk about media influencers. Really they're, what they're doing is they're building a reputation

[00:41:05] **Adam:** Mm-hmm.

[00:41:06] **Tim:** is tarnished, rightly so, anything going forward af-after that tarnishment should, you know, probably be re-evaluated,

[00:41:15] to some degree.

[00:41:16] **Ben:** I

[00:41:18] think, you know, in the modern era, in this idea that people get... I know this is maybe an extreme case, but like people who get radicalized into,not Al-Qaeda. What was the one-- What was the, what was the next one? ISIS. Well, a-any of these, like any of the conspiracy theories, any of the, you know, radicalization, anything where people kind of start on one place and then like they slowly slip into a kind of narrow, narrower and narrower view of the world. I, I think that to me is where it becomes a very different world that we live in, and that helps me understand my, ability to reconcile in the past versus my, let's say, non-desire to reconcile in the future. And I'm-- And by that, what I mean is going back to "Braveheart." watching "Braveheart" doesn't over time make me anti-Semitic. know, saying that I like "Braveheart" not, to the people who are listening to me, I think, this is my assumption here, does not make them think, "Oh, he likes to support anti-Semitic people or anti-Semitic artists." Like, you could make that jump, but I don't think that's how people take that,

[00:42:40] **Adam:** Yeah

[00:42:42] **Ben:** So I think that's helped me understand the, the trouble

[00:42:48] **Adam:** it was Joe Rogan that

[00:42:53] **Ben:** do I live in that world? And the, the way that I'm rationalizing that to myself is that that's okay because it's not a slippery slope, that watching this movie over and over again doesn't make me any more like the person who created it that I don't necessarily like or agree with. In the current world where We have this ongoing relationship and that relationship is fluid and dynamic and, and evolutionary. That to me feels very different. You know, if I-- and this is just like a one example. This is not meant to yuck anybody's yum, but I'll say like someone like Rogan, I don't care for him personally.

[00:43:34] I don't find his podcast very interesting personally. But I think my biggest issue with it is not that I couldn't go on and watch, him talk to a, a, a fitness scientist for 45 minutes and actually quite enjoy it and find interesting things in it. But I know, same with like I can't have a video game in my apartment because I know that's gonna be dangerous for me. If I watch someone who I agree with sometimes and in other times I find them to create content that is maybe morally objectionable, do I have the mental fortitude to not let that become a slippery slope for myself? You know, how, how easy is it to go with, "Yeah, I totally believe in this m- macro ratio of protein, carbohydrates, and fats in your diet," three months later I'm like, "You know what? This guy talking about flat Earth, he's making some really good points." You know? It's like

[00:44:32] **Adam:** said both things sort of thing?

[00:44:36] **Ben:** because you're, because you're platforming

[00:44:39] **Adam:** Right

[00:44:40] **Ben:** have such a wide variety of views, you either have to be very mentally strong, maybe a lot of people are. I don't think that I am in certain cases, and I think I'm not in other cases, and I'm-- it's like that's not the thing I wanted to ex- find out about myself.

[00:44:59] so,

[00:45:01] **Tim:** I

[00:45:01] **Ben:** go ahead.

[00:45:01] **Tim:** my,

[00:45:01] my dad growing up said, you know, "Show me who your friends are and I'll show you how you, you're gonna turn out."

[00:45:08] **Ben:** Yeah.

[00:45:08] **Tim:** And it's like in the age where, like it or not, people that we spend a lot of time listening to, podcasts, things like that, they become our friends. Which is why, like, I, I talk to you guys.

[00:45:19] I like you guys. You're my friends. And, and I feel that you're good

## [00:45:22] Mental Models Versus Value Systems

[00:45:30] **Tim:** influences on me. And so you, you know, when, when you talked about this kind of mental model or what did you call it? The, mental garden. I, I notice that you, you tend to talk a lot about a mental model of things. You

[00:45:37] **Ben:** Yeah.

[00:45:37] **Tim:** a mental model.

[00:45:38] You like to have a, kind of a working construct about things, you know. And I get that for code and for work and stuff like that. For me, I feel, 'cause we're getting kind of philosophical in

[00:45:49] **Ben:** Yeah, yeah. This, this whole episode is philosophy.

[00:45:52] **Tim:** Yeah, very philosophical. For, for me, the world is too

[00:45:57] **Ben:** Mm-hmm.

[00:45:57] **Tim:** it is too chaotic to have a mental model of how the world works. you could have one, but you're always gonna be having to refactor it constantly because just, I mean, the past, you know, COVID, everything, everything that's happened in the past few years, like, you, you're-- If all you have is a mental model and that's what you're working off of, you are constantly going to be having to rebuild it and feel like you don't understand. And what I've been working on for the past few years is rather than having, trying to have a mental model of the world and things that are too complex for me to understand, I just have a value-based system. What do I value? What do I want to be? How do I want to be perceived? What's important to me? And then I measure things as they come along in life based off that value system. my value system is a little, is, is wrong, and I have to tweak that.

[00:46:58] **Ben:** Mm-hmm.

[00:46:58] **Tim:** But that's not as massive as trying to come up with a whole mental model for the world. Certain values are never gonna change for me: honesty, kindness, hospitality Things of those things,

[00:47:10] **Ben:** Right.

[00:47:14] **Tim:** consider important, and I fall short of it every day. But at least I have a value system that I can measure as they come to me and things as I try to put them out into the world. So I wonder if rather than having-- trying to have a mental model of this garden, you'd rather just come up with a list of, you know, Ten Commandments of here is Ben Nadel's value system, filter things through that passively or actively, rather than trying to understand everything and

[00:47:45] then go forth into the world.

[00:47:48] **Ben:** I, I mean, I think that's

[00:47:49] makes 100% sense, and I think that's what I'm to do. And, like, you know, understanding your own set of values, I think, is a changing thing. as we get older, as we're exposed to more of the world, as we're exposed to a wider variety of people, our values change, they expand, they contract in certain ways. how do we change the way we navigate through the world to, to reconcile

[00:48:15] with that? And I think, again, kind of

[00:48:20] just juxtapositioning movies with podcasts and the way that, that they either adhere or don't adhere to values. And I think that's, that's kind of the, the crux of, where I'm thinking about these days, is that I don't think I'm necessarily sacrificing my values to enjoy the art make, if they're not the best people. As opposed to being, it participating in a conversation In which half of the conversation has values I don't agree with. to me feels like it's a much more slipperier... Slip... A much more slippery slope. Thank you.

[00:49:04] even if I don't, let's say change my values, I think it will make me somewhat numb to when those values are misaligned, I, and I feel like that will be problematic for me. And world where there is such an embarrassment of choices, you know, if I want to get my science, I can get my science from, somebody like a Joe Rogan.

[00:49:30] I'm just picking on him 'cause he's so well-known. Or I can get my science from like a Science Friday podcast. And it's like I can do it from the Science Friday podcast without having to then also talk to the people who are like, "You know what? I actually have

[00:49:46] **Adam:** I

[00:49:46] **Ben:** evidence that the, moon landing was faked, and if you look at the photos..."

[00:49:50] **Adam:** saw a movie about that.

[00:49:52] **Ben:** Yeah. So, there are so many choices that I can make, and I can make the choices where I'm not feeling like I'm compromising too much, and I, and I... I don't know. I don't... Like I don't have a way to wrap this up in a very succinct way other than to say I'm trying to protect my mental garden

[00:50:11] **Adam:** So

[00:50:12] **Ben:** rotting.

[00:50:14] **Adam:** I'll throw it, since you said you don't really know how to wrap this up, I wanna circle back a little bit. I let you guys go on a bit 'cause I didn't wanna interrupt. I, I was enjoying your discussion about, like, your personal philosophies, and I think that mine is a lot closer to Tim's, except I would say it's like the-- these are my values and I just kind of evaluate stuff as it, as it hits me.

[00:50:32] But I, I, it... To a small degree, I try to be the feather at the beginning and the end of the movie Forrest Gump. Like, wherever the wind wants to take me in terms of, like, what, you know,of, like, life, right? Just in general. Not, not in terms of my opinions changing because the wind blows, but just, like, you know, I, I, I don't

[00:50:55] to go down a specific path in life, you know?

[00:50:59] I, I'm, I am a very much I, I float by the seat of my pants, you know, the, like,

[00:51:04] **Ben:** skydiver

[00:51:05] **Adam:** I fly by the seat of my pants. Is that what the expression is? Like, maybe, yeah. Like, but, you know, a lot of life I'm fine improvising, right? Like, I... If I am on a road trip, I don't feel the need to pl- if I'm driving all the way across the country, I don't feel the need to plan my hotel stops and book the reservations before I go.

[00:51:22] Whereas my wife is like, you know, three m-

[00:51:24] **Ben:** that at all, sir.

[00:51:25] **Adam:** three months ahead she'll have the, the rooms booked and, and, and...

[00:51:29] **Tim:** I'm with you, Adam.

[00:51:31] **Adam:** Yeah, you know, it's like, "Okay, we'll

[00:51:32] find a hotel, and if we don't, then we'll sleep in the, in the backseat of the car," right? Like, it's okay.

[00:51:38] But we'll find one.

[00:51:39] **Ben:** Even just, hearing you say that is making me anxious.

## [00:51:44] If Fear Were Not in Charge

[00:51:44]

[00:51:44] **Tim:** Uh,

[00:51:45] so,

[00:51:46] **Ben:** Hmm.

[00:51:49] **Tim:** have mentioned this on the show or maybe to you guys personally off the show. But he asked a statement that absolutely me in my tracks, and he said... 'Cause it was, I was talking about my life and kind of how I respond to some trauma that I went through as a kid. And he, he said, "If fear were not in charge,

[00:52:10] who would you show up as?"

[00:52:12] **Adam:** Hmm. I do vaguely remember you mentioning that.

[00:52:15] **Ben:** I like

[00:52:17] **Tim:** I had to, like, end the session. I'm like, I'll

[00:52:19] **Adam:** You w- you blue screened on him.

[00:52:21] **Ben:** that.

[00:52:23] **Tim:** blue screened on him. and you think about this, I, I think a lot of times we're driven by fear 'cause fear is... Fear for humans is extremely important to survival

[00:52:34] **Adam:** Yeah.

[00:52:35] **Ben:** Mm-hmm.

[00:52:36] **Tim:** living in an age where everything is life and death, but yet our bodies, our endocrine system, our minds still treat every scary thing.

[00:52:45] The scary thing could be you have a deadline. it

[00:52:47] **Adam:** Mm-hmm.

[00:52:48] **Tim:** like or death, and it's not. That's 100% not. No one's gonna die.

[00:52:52] **Adam:** and we just make based off of other things other than fear, what would that be like? And I'm, I, I don't have an answer for you yet. I'll let you know if I

[00:53:04] **Ben:** Fear is

[00:53:04] **Tim:** it

[00:53:05] **Ben:** my, is, like, such a big motivator for me.

[00:53:09] **Tim:** is such a big motivator. In, in fact,

[00:53:10] **Adam:** somebody has to say it. Fear is the mind-killer.

[00:53:13] **Tim:** It is the mind-killer. I do

[00:53:14] **Ben:** Hmm.

[00:53:18] **Tim:** you and

[00:53:19] **Adam:** Mm-hmm.

[00:53:20] **Tim:** and then whatever left remaining is

[00:53:22] **Adam:** Mm-hmm. Mm-hmm.

[00:53:23] **Tim:** And so if you can get to that point where you just let that fear, you just face it

[00:53:27] **Adam:** Yeah. Nope. Was that

[00:53:31] **Tim:** gone?so there was a, act, a movie studio makeup artist, three-time Oscar... I can't remember his name right now. But anyway, we-- my wife and I, we hosted,a sci-fi makeup thing back in like 2017, 2018, and he showed up to it. He wasn't even invited. He just showed up and wanted to hang out. And, are asking him like, "What's your secret being so successful?"

[00:53:54] And that's what he said. He's like, "Treat every project like you're going to die." And I'm like, I

[00:54:02] **Adam:** that like

[00:54:06] **Tim:** Nope. not

[00:54:07] **Adam:** the

[00:54:10] **Tim:** Yeah, back

[00:54:11] **Adam:** Kardashian makeup days? Okay. Yeah.

[00:54:13] **Tim:** but yeah, it's-- so what

[00:54:15] **Ben:** I...

[00:54:16] **Tim:** Ben, if, if, if like fear weren't ruling

[00:54:18] your life?

[00:54:19] **Ben:** Oh my goodness.

[00:54:21] F-

[00:54:21] He

[00:54:21] I don't know. I mean, part of me feels like it will be radically different, and then part of me feels like it would only be a little different. It'd be more

[00:54:28] **Adam:** would

[00:54:29] **Ben:** but, like, I'm fundamentally the

[00:54:31] **Adam:** have zero unread messages on his phone.

[00:54:35] **Ben:** 'Cause I did, like, select all, delete.

[00:54:37] **Adam:** Yeah.

[00:54:37] **Ben:** It's, it's the fear that prevents me from

## [00:54:40] When You Become the Influencer

[00:54:42] **Ben:** deleting.okay, let, let me just take this one step further. we talked about consuming a product that's a snapshot in time: movies, comedy albums, musical albums, that kind of stuff. then we sort of went to this sort of parasympathetic, parasocial,

[00:54:59] **Adam:** Parasocial, yeah

[00:55:00] **Ben:** relationship where we're still kind of unidirectionally consuming information, but that information is changing over time. So it becomes, mm, you know, is there a slippery slope? Is there a, you know, someone getting their foot in the door and then slowly poisoning you? Then there is the, okay, and now we live in another world where people are watching the things that we do, whether in person or on social media, and how do we play that role in a way that is best, for lack of a better term? And I'm gonna throw out an example that, that drives me crazy. And again, this is a personal thing. Everyone is different. To each their own. This is just to make it concrete. I think is crazy. I think he's batshit crazy. I think he does a lot of crazy

[00:55:50] **Adam:** you're talking about RFK Jr.?

[00:55:51] **Ben:** Yes, yes, yes. Sorry, RFK Jr., the, head

[00:55:54] **Adam:** Current, how-- yeah.

[00:55:56] **Ben:** I think

[00:55:56] he's crazy. I think he says a lot of crazy stuff. I think he has a lot of crazy beliefs.

[00:56:00] every now and then, though, he will say something that is either very obviously true, like people should eat better, or he'll say something that, you know, you know, that maybe has some... You know, he challenges the system in a way that probably would be good. And people will say things publicly like, "Well, I don't agree with most of what he says, but XYZ is actually a really good point."

[00:56:27] **Adam:** Mm-hmm.

[00:56:27] **Ben:** to myself, you can't that because, and here's where the, the kind of bidirectional relationship with the world starts to come into play, that let's say, I say that, well, you know, I don't personally agree with his take on, on, you know, the CDC and his, and his views on vaccinations I think are crazy.

[00:56:48] **Adam:** And

[00:56:49] **Ben:** I,

[00:56:49] **Adam:** roadkill.

[00:56:50] **Ben:** Yeah, you know, hiding bear carcasses in his car, like all the, all the crazy stuff that he's done, right? then I'm like, "Oh yeah, we should probably take dyes out of food. Like, that's probably a good idea." Now, someone who might hear me say that says, "Oh, you know, Ben said... I, I think I remember Ben saying that, oh, RFK Jr.

[00:57:06] actually had some really good ideas about nutrition." And in a very isolated way,

[00:57:11] **Adam:** Ben, you're canceled.

[00:57:13] **Ben:** No, that's, but that's the thing that they take away, right? And then in a totally different scenario, they go and they hear RFK Jr. say something like, "Oh, wouldn't it be great if we, you know, stopped teaching kids how to read?"

[00:57:27] I don't know, like something batshit crazy.

[00:57:29] **Tim:** Yeah.

[00:57:30] **Ben:** And, like, what they have in their head is, "Oh,

[00:57:32] **Adam:** Well,

[00:57:36] **Ben:** to say about RFK Jr. And, like, a pretty smart guy. I think he's a pretty honorable guy.

[00:57:40] Like, oh, maybe I should give this other stuff that RFK Jr. is saying more weight because of my relationship with this person that I actually know in real life." think that's where it gets, like, really tricky do we... Y- you know, 'cause it's not just our own mental gardens that we're dealing with.

[00:57:59] It's, it's

[00:58:00] **Adam:** eh.

[00:58:00] **Ben:** we're possibly affecting other people's the world. And, and maybe I'm blowing that out of proportion, but I'm just saying, like, that's, that's like this, like, highly connected world that we live in, and it gets very

[00:58:12] s-

[00:58:12] funky.

[00:58:13] **Adam:** A broken analog clock is right twice a day, and yet it is still broken,

[00:58:17] **Ben:** Right.

[00:58:18] **Adam:** right? And so, like, that doesn't make the clock trustworthy. It just means that twice a day you can look at it and it will happen to be right.

[00:58:29] **Ben:** Right. But, but then you can't say, "You know, most of the time I don't agree with this clock, but at 12:03, you know, it's got some pretty good stuff to

[00:58:37] say."

[00:58:38] **Tim:** I-I-I'll, I'll say this, so I forget, I, I read a book on, the philosopher's toolkit, to be the smartest person in the room, and it talked

[00:58:47] thumb, I guess, is kind of like the generic way to refer to it. We, we sort of have these little shorthand ways to arrive at close enough or correct decisions.

[00:58:58] **Adam:** Yeah.

[00:58:58] **Tim:** And one of those is like, sort of like, you know, an a- an authority figure. Like, so,

[00:59:03] **Adam:** Yeah. You have to...

[00:59:07] **Tim:** like RFK Jr. says," right? And so a person who's not actively thinking and using rationality and logic and applying rigor to their life say, "Well, Ben said that about him.

[00:59:20] It was good for there, so I guess everything he says is good. That could be a rule of thumb." that's, I mean, that's on them, right? I

[00:59:28] **Ben:** it, it is on them. But I'm... But, but, to push back

[00:59:32] **Tim:** because otherwise the other thing we do is we wind up demonizing everybody, right? So anyone who disagrees with us in any little way, we have to demonize them. We have to say that, you know, shun them.

[00:59:43] **Ben:** Yeah, 100%. Right.

[00:59:47] **Tim:** I mean, we've seen this over the, over my lifetime where, you know, people are not willing to compromise anymore. They have to be right 100% of the time. They can never apologize. And the, their, their oppon- their opponents are terrible human beings. They're, they're evil, right? There, there's no room for being,

[01:00:08] **Adam:** nuance.

[01:00:09] **Ben:** Everything is extreme.

[01:00:11] **Tim:** without being disagreeable. And that's kind of where we got to get back to. But I don't know how to fix society, so

[01:00:19] **Ben:** I, I, I, and

[01:00:20] **Adam:** week's show.

[01:00:21] **Ben:** I, I, I

[01:00:21] totally agree, and I don't mean to imply in any of this that, that the extreme is the only option, and in fact it is

[01:00:31] **Adam:** You're just

[01:00:32] **Ben:** probably like the one terrible option. It's like the only unacceptable option is the extreme. You know, it's like when I say like the religiosity, the radicalization, like I don't mean by any stretch of the imagination, like I'm against religion or people who want the community of the church or whatever. I'm against the, you know, all Muslims must die or like all Christians must die. Like

[01:00:54] that's wrong. That's, that's crazy.

[01:00:57] **Adam:** servit--

[01:00:57] serving those quotes up for people to steal them out of

[01:01:03] **Tim:** The

[01:01:04] **Adam:** context in your voice.

[01:01:04] **Ben:** for a hell of a clip show.

## [01:01:07] Choosing Where to Get Your Information

[01:01:07] **Ben:** you know, and I, and I think this is where like I don't have a great way to articulate the, the nuance that I'm feeling.I... Going back to this idea that there's kind of an embarrassment of choices of where you can get your source of information from in today's, you know, bajillion podcast world and 17 million streaming services, I-- are places where I can get information that feels safer for me in, in like how I feel like I need to exist in the world, hopefully there's balance. And, you know, I want to be challenged. Like, I want to listen to things. Like, one of the podcasts that I really enjoy is "The Ezra Klein Show."

[01:01:51] **Tim:** Mm-hmm.

[01:01:52] **Ben:** a New York Times journalist, and part of what I like about it is that he has conversations that I think are uncomfortable and are challenging. And, you know, why do, liberals, and I very much consider myself a liberal, like why did we make it so hard for people to build housing in this country?

[01:02:08] And like why did we, you know, go so far overboard with environmental protection acts that we make it impossible to move anything forward? And like those are uncomfortable conversations to have 'cause it really forces you to think about like- How much is important? Like, where's the balance? Where's the line?

[01:02:23] Where do you put people first? but like I, like that's, that's one degree of challenge. Then there's, you know, a whole... Again, like I don't have the right words to say like, I don't want to be curious about people who are just hateful. You know? Like, I don't need to have that in my life

[01:02:44] **Adam:** Mm-hmm

[01:02:45] **Ben:** like I'm living a balanced view, into the world. And like, again, like I don't know what the words are to describe that well. I'm saying I'm, I'm-- The world is crazy, and I'm trying to make the best choices I can to protect my mental garden. Call out to

[01:03:05] the show title.and, yeah, that's, that's... I'll leave it there. It's j- it's, it's hard.

[01:03:11] **Tim:** Yep

[01:03:12] **Adam:** It's hard.

## [01:03:13] Patreon

[01:03:13] **Tim:** real.

[01:03:13] **Adam:** Okay.

[01:03:15] Well then, this episode of Working Code is brought to you by the canceling of Ben Nadel. Not... Now, hang on, I wa- ha- there's more. I wanna be specific, okay? Not for his views on religion, not for his views on politics, not for his views on video games. No, Ben Nadel is canceled because of how he writes podcasts.

[01:03:37] C-

[01:03:38] **Ben:** one

[01:03:38] **Adam:** pod, capital P, Pod, space, capital C, Casts. Okay? Let's get on this, you know, get in the comments,

[01:03:49] write, you know, I want a, I want a letter-writing campaign. Write your senator.

[01:03:53] **Tim:** I thought it was C-A-K-S,

[01:03:55] casks, like beer casks. No?

[01:04:00] **Adam:** We, we gotta... Something must be

[01:04:02] done. This man must be taken off the airwaves. So, this episode of, of Working Code is brought to you by the cancellation of Ben Nadel and listeners like you. If you're enjoying the show and you wanna make sure we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[01:04:16] Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them. Special thanks, as always, to our top patrons, Monty and Giancarlo. You guys rock. We're gonna go record the after show. Got a couple of topics on the list here. I'm gonna keep it secret. If you wanna know what's in the after show, there's a real easy way to find out.

[01:04:33] You just send us some money. You put it in an envelope, write my name on it, don't worry about anything else.

[01:04:38] **Tim:** Come

[01:04:38] **Adam:** Don't, don't... Just, write Adam Tuttle on an envelope, lick it, put it in an e- put it in your mailbox with some money in it, and y- that makes you a patron, okay? Or you can go to patreon.com/workingcodepod and, and do it.

[01:04:52] Probably more likely to get your,

## [01:04:54] Thanks For Listening!

[01:04:54] **Tim:** Yeah.

[01:04:54] **Adam:** to the after show

[01:04:55] **Tim:** Yep.

[01:04:56] **Adam:** that's gonna do it for us this week. We'll catch you again next week,

[01:04:59] and until then...

[01:05:00] **Tim:** I'd like to see

[01:05:02] what you will be when you wall off your garden from people like me. your heart matters.
