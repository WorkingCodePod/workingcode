---
title: "085: Shipping Complexity"
description: "This week on the show, the crew talks about how they try to reduce the complexity of their code shipping process"
date: 2022-07-27
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/085-shipping-complexity/id1544142288?i=1000571327737"></iframe>

Sponsors

-  [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

The less code you write, the easier it is for people to review, the less likely it is to contain bugs, and the more likely it is to merge cleanly into your main integration branch. The converse of this tends to also be true: the more code you write - particularly within a long-lived feature branch - the harder it is to review and the more likely it is to contain bugs that cause production issues. We all basically hold this to be true; however, that doesn't mean that we can _simply choose to do the former_. Shipping less complexity is a byproduct of both team and technology constraints. This week on the show, the crew talks about how they try to reduce the complexity of their code shipping process.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/085-shipping-complexity.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Adam:** I have a, a private channel in our team chat that only I am in. It's called hello darkness, my old friend. that's, the name of the channel and when stuff like this, when I notice it and it gets on my nerves, I just take a screenshot in it and I post it in that chat room and then only I can see it.

[00:00:15] **Adam:** And it's just that little release of catharsis for me. It's like, okay, I have admitted that this is a bad thing that the universe is aware and I can move on with my day.

## [00:00:24] Intro

[00:00:24] **Adam:** Okay. Here we go. It is show number 84 and on today's show, we're gonna talk about shipping complex things and trying not to let them get too complex, but, there's a lot to unpack there. So we're just gonna jump right into it.

[00:00:54] **Adam:** Like we usually do start with our triumphs and fails. it's been a while I think since I've gone first. So I'm gonna go first. I think I've got a fun one today. It's been a good week for me. I have a lot, of things that I could list as triumphs. I'll just throw this one out there real quick.

[00:01:06] **Adam:** This is not my triumph. we got a new dog. She's awesome. lab mix rescue from a local animal shelter. her name is Lucy not taken from you, Ben. the, they were calling her Lucy at the shelter and it just was like, you looked at her and you're like, yeah, that's your name? You are a Lucy. And,and it was perfect for her and yeah.

[00:01:25] **Tim:** It's gonna hump everything, just like Ben's Lucy

[00:01:28] **Adam:** so, no, she hasn't been Humpy anyway. moving on, that's not my triumph.

## [00:01:32] Adam's Triumph

[00:01:32] **Adam:** My triumph is a parenting triumph. So I had this phrase that I like to say to my kids, you know, when, you know, when they do something stupid and they get what's coming to 'em. I like to say play stupid games, win stupid prizes.

[00:01:43] **Adam:** Right. And.

[00:01:44] **Carol:** yeah.

[00:01:45] **Adam:** And,

[00:01:46] **Tim:** mess around and find out

[00:01:48] **Adam:** so you can, yeah. It's yeah, exactly. It's the duck around and find out of, of parenting. so you can kind of see where this is going. I think we put the kids to bed the other night and, my kids are older. They're 11 and 13. So bedtime is kind of like a suggestion, right? It's mom and dad are gonna spend time together downstairs.

[00:02:06] **Adam:** The kids go upstairs, they're quiet. and hopefully they go to sleep at some point. well, the kids are upstairs, we're downstairs watching TV and we hear like a series of really loud THS, like one loud thump and then a couple of small ones. And we're like, what was that? And we just holler up the stairs, like everything.

[00:02:22] **Adam:** Okay. And my one, my older son in, you could tell he's like feeling it he's the one that got hurt and he just yells down. I was playing a stupid game and I won a stupid prize. And Megan and I just looked at each other and cracked up. That was probably the highlight of my year. So far.

[00:02:47] **Tim:** I think that's great. I, there's certain like

[00:02:50] **Adam:** things like events that happen in life and you put like a little tag on it or a little shorthand, code for it in that it's sort of a family code for those sort of things. I think those are great because it's like, it takes a complex kind of emotional situation and puts a little tag on it that you can just reference, like in a word.

[00:03:08] **Tim:** Right. And then everyone knows what that means. And it just, I think that really just kind of helps people, particularly, you know,young yeah. Young minds to build this kind of yeah. Like a design pattern, sort of like a, here's a pattern like, if I do this, this is gonna happen. Or if this situation is very similar to another situation and you can reference it extremely quick just by using that sort of like two word, three word phrase.

[00:03:32] **Tim:** So I think that's fantastic.

[00:03:34] **Adam:** you know what, honestly, I have a feeling that's gonna come back into play for our topic tonight. I think, you know, when, when you play stupid games with your code, you're gonna win stupid prizes. So

[00:03:46] **Tim:** For

[00:03:46] **Carol:** Yeah.

[00:03:47] **Adam:** that'll be fun. So,

[00:03:49] **Tim:** he? Oh God. Yeah. wow.

[00:03:50] **Adam:** Yeah. Oh yeah. So, or let, I guess everybody's gonna wanna know. So I'll tell the story of what happened.

[00:03:54] **Adam:** he had like climb climbed up to the top of his door. Like the door is open, is kind of hanging on the hinges, swinging around a little bit. He climbed up to the top of his door and he brought up the bottom edge of his t-shirt and he like hung it over the end of the door. And was just hanging from it. and and of course the shirt ripped and he fell and

[00:04:18] **Ben:** my goodness.

[00:04:20] **Adam:** kids are great.

[00:04:21] **Tim:** awesome. Yeah, for

[00:04:22] **Carol:** he's just taking after you the whole, like jumping outta planes, being

[00:04:26] **Adam:** Yeah. Yeah.

[00:04:27] **Carol:** things.

[00:04:28] **Adam:** Live your best life, man.

[00:04:30] **Tim:** For sure. For sure. Good

[00:04:33] **Carol:** yeah.

[00:04:34] **Adam:** So, Ben, what do you got going on, man?

## [00:04:37] Ben's Triumph

[00:04:37] **Ben:** I'm gonna go with a triumph, which is that we just moved from an apartment into our first house. So I'm both terrified and exhilarated and overwhelmed and excited to be living a completely new residential lifestyle right now. but, the triumph is that it just, everything went so. Smoothly, like oddly smoothly, the movers showed up on time.

[00:05:04] **Ben:** Packing. The trucks went super easy. They actually beat us to the house in terms of, getting the trucks here. And then unpacking was super easy. Nothing was broken. Everything just went really smoothly. We just couldn't stop telling them how awesome everything was going. We're like, you guys are just crushing it.

[00:05:22] **Ben:** I can't believe how fast this is all going. You guys are just rocking it. And they were like, feeling our vibe, we're feeling their vibe. And it was just, I just was just awesome. And

[00:05:31] **Adam:** you invite him to stay for dinner and drinks or like,

[00:05:35] **Ben:** it could have been a nightmare. We actually had neighbors that were moving a few days before we were moving. they were moving across country from New York to California and their truck broke down on the way to get them. And then there were

[00:05:48] **Carol:** no, it's

[00:05:49] **Ben:** of problems and like not enough of the movers showed up and everything was taking really long. and like, that's what, that was our mindset going into this. We're like, oh, this is gonna be terrible. Everything that could go wrong is gonna go wrong. And then literally everything went. Right. So I'm feeling super stoked about that.

[00:06:08] **Tim:** I tell you having professional movers is yeah, that's a godsend. That's like doing it yourself is ridiculously

[00:06:15] **Ben:** mm-hmmYeah.

[00:06:16] **Adam:** have moved a lot of times in my life and never had professional movers. It sucks.

[00:06:20] **Carol:** really, it's

[00:06:21] **Tim:** it, once you do it, you're like never again. Am I moving

[00:06:24] **Carol:** you won't go back.

[00:06:26] **Ben:** it was really great. and they came with two trucks, like two full big ass trucks and, cuz we had the apartment and it was a two bedroom apartment, but then we had a garage and a storage unit in the building. So it's just like, you just accumulate a lot of junk over the years and yeah, it just went all great.

[00:06:42] **Ben:** and I'll say that I'm, super excited. So I have this area next to my desk. That is between the window and my desk. And that's gonna be where Lucy's bed is gonna go. And, I just ordered some Metro shelves and I'm gonna try and build her like the perfect size desk. And now I gotta do some shop, not desk, perfect size bed.

[00:07:02] **Ben:** And I got, I've got my stairs here. Ready to go and everything it's gonna be I'm I'm gonna build the ultimate doggy daycare next to my desk. I'm very

[00:07:10] **Tim:** We'llwe'll just hear hum.

[00:07:11] **Carol:** Yeah.

[00:07:12] **Tim:** while you're recording. So, so I mean, so how big, so like how big was your apartment square foot versus the house that you're moving into? what's the difference here?

[00:07:22] **Ben:** have no idea how big this house is, but I

[00:07:24] **Tim:** go downstairs, ask your wife and come back

[00:07:26] **Carol:** She knows.

[00:07:27] **Ben:** knows. So there's only one floor. Well, there's a main floor, it's she? I think she called it a ranch or a split ranch or

[00:07:33] **Tim:** okay. Yeah. Yeah.

[00:07:34] **Ben:** it's got a main floor, then it has a finished basement. and, the, our apartment was only like 850 square feet.

[00:07:42] **Carol:** Oh, wow.

[00:07:43] **Ben:** think is, I wanna say like 2,500 square feet or something like

[00:07:48] **Tim:** so

[00:07:48] **Tim:** it's, it's significantly bigger.

[00:07:50] **Adam:** That's a big house.

[00:07:51] **Ben:** It's like an actual house, which is great. And it's got a yard for the dog, which is

[00:07:55] **Carol:** Aw.

[00:07:55] **Ben:** great.

[00:07:56] **Carol:** Do you have a fence where you can just kinda let her out and go?

[00:08:00] **Ben:** Yeah. the backyard is fenced in, but apparently there's we, so we moved about an hour and a half farther north from where we were. So we moved from a suburban, but still fairly metropolitan area to this is like, we're definitely in the country now.

[00:08:15] **Tim:** Welcome.

[00:08:16] **Ben:** Yeah.

[00:08:17] **Ben:** And, uh,lot more pickup trucks, lot of pickup trucks around,around these parts.

[00:08:24] **Carol:** around them. Their

[00:08:25] **Ben:** uh,

[00:08:26] **Tim:** well,

[00:08:28] **Ben:** someone said that there's a Fox in the neighborhood, so I'm a little nervous about just letting the dog willy-nilly outside, but uh, . I

[00:08:36] **Adam:** Show hum.

[00:08:37] **Ben:** dunno.

[00:08:38] **Carol:** Yeah.

[00:08:39] **Ben:** so

[00:08:40] **Tim:** good. They can help you move boxes. Ain't gonna mess with your dog. Look, they'll kill your chickens. If you have 'em.

[00:08:43] **Ben:** oh, man. so yeah, so just overall, pretty excited and, terrified, but excited also, in the apartment building, there's a superintendent and like, he just does everything, anything that breaks, he just fixes it and his people fix it and now everything is on us and that's pretty scary.

[00:08:57] **Adam:** Let's be honest. It's on your wife.

[00:08:59] **Carol:** Yeah.

[00:09:00] **Tim:** two words for you. Ben home warranty,

[00:09:03] **Carol:** YouTube.

[00:09:04] **Tim:** home warranty, man. No home.

[00:09:06] **Carol:** Yeah.

[00:09:07] **Tim:** Yeah.

[00:09:08] **Ben:** I don't

[00:09:08] **Tim:** best thing I ever did is

[00:09:09] **Ben:** What?

[00:09:10] **Tim:** so

[00:09:11] **Adam:** Yeah,

[00:09:12] **Tim:** American home shield is, that's what, I'm not a sponsor. Wish they were, but yeah. So like for any house I have, it's like, I'm not a handyman and I don't even like having to figure out who to call American home shield.

[00:09:22] **Tim:** It's like, you buy a plan. It's like 50 bucks a month, maybe depending. And it's like anything breaks. You just go online and say, this is broken. They come in a couple days and fix it. It's like a, between, depending on the plan, it's like between a $50 and a hundred dollars copay,

[00:09:39] **Ben:** Oh, I'll take a look.

[00:09:40] **Tim:** they they've replaced my air conditioner.

[00:09:42] **Tim:** They've replaced

[00:09:42] **Tim:** my pool pump. They replaced

[00:09:44] **Tim:** Water heaters. yeah, definitely. If you're a homeowner, that is a, I, cuz I can deal with like, a hundred bucks a month payout. I cannot deal with like a $2,000 bill,

[00:09:54] **Carol:** Yeah,

[00:09:54] **Carol:** yeah, yeah, yeah. Oh, I'll look it up. Thank you for the recommendation.

[00:09:58] **Tim:** No problem.

[00:09:59] **Adam:** that Rolin makeup doesn't come cheap. So Tim's living paycheck to paycheck.

[00:10:05] **Tim:** for sure. Yeah. 49 days of Dragoncon.

[00:10:09] **Ben:** kick it over to Tim.

## [00:10:11] Tim's Fail

[00:10:11] **Tim:** Ah, well, I'm gonna break this triumph Fest. you and, Adam have going on here with a fail and it's not my fault, the fail. So it's like the Monday we had like a, an in-office kind of first time we've been in office in a super long time,kind of had some, reorg stuff. So it went in, sort of met a new overlord and met with him and, hung, talked for, the whole day.

[00:10:35] **Tim:** But then it's like, so I got fiber, which is a triumph for me recently, but it's like, everyone in my neighborhood is getting fiber now. And it's like, every time they get fiber, my internet goes down. So. All day Tuesday, my internet was out because they were coming in to bury the cable. Cause I just had like, a fiber optic cable, just running in the middle of the yard, going up down to the street,

[00:10:57] **Tim:** they had to come bury it.

[00:10:59] **Tim:** And so they had to unplug it. And then, so they had to unplug pretty much all day and then they bent it like 90 degrees and broke it. And so then they had to bring, the team come in and like run some more wired, So the whole day Tuesday was gone. and then all day today, for some reason it went out cuz someone down the street decided to get fiber and it messed my fiber up, but it's actually okay.

[00:11:17] **Tim:** Cuz I had a really bad headache, all like starting yesterday evening until like two o'clock today. It just, I couldn't do anything. I'm glad the internet was out. Cause I wouldn't have been able to work anyway. So I really haven't done a whole lot this week to even give you a triumph or fail because I didn't have internet.

[00:11:37] **Tim:** I went in the office for like a little bit just to deal with some. Stuff that I had to deal with, but like, after that I came home and just turned the lights off and laid down cuz my head was killing me. So yeah. I haven't really done a whole lot.

[00:11:49] **Carol:** I hate that for you. Headaches are the worst, like, I can handle most things, but when you give me a bad headache, I can't code. I can't sit and read emails. I just wanna go land my bed.

[00:11:59] **Tim:** Yeah. And I think I don't get headaches often, but I think what caused it. So it's like I had a blood test on Wednesday and I was trying to be really good. So like the entire, so from last, the prior Wednesday, I fasted, so I just had nothing but water for an entire week

[00:12:16] **Adam:** Which if you guys haven't listened before, this is something Tim does on the regular, and he's been consulting with his doctor the whole

[00:12:22] **Tim:** Yeah.

[00:12:22] **Tim:** I do it other regulars, so it's okay.

[00:12:24] **Tim:** But the difference is I stop drinking coffee. Normally when I'm fasting, sometimes I do have an espresso with no milk or sugar. I went off coffee and I think I had a caffeine headache because today, this morning I still had a headache. I had my first coffee since a week Tuesday. And so I had my first coffee and like the headache went away within a few hours.

[00:12:48] **Carol:** Oh, wow.

[00:12:49] **Tim:** I think that's what it was. I think it was a caffeine headache, but

[00:12:51] **Carol:** Do you ever take a like C tension, headache, or

[00:12:54] **Tim:** II took everything. I took everything to try to get rid of the headache. The headache was just there

[00:12:58] **Carol:** for like,

[00:12:59] **Carol:** the C intention has caffeine in it, so

[00:13:02] **Tim:** I did not have, I did not have that. I had aspirin. I had like a leave or whatever, but yeah, I just a massive headache.

[00:13:08] **Tim:** know, finally went away today. So, but yeah, that was my fail. Really. Haven't been able to do any work. So I can't tell you, I, I probably would've crushed it if I had internet, but.

[00:13:16] **Carol:** Of course you would have.

[00:13:18] **Ben:** here's a confession. In terms of internet speed. When people talk about the speeds that they get, like I get 700 megabits up and a gigabit down. I literally have no idea what any of that means. Like my mental model is like the 28 K broad modem is not as good as the 64 K automotive. And like, after that, it's like all just completely abstract to me.

[00:13:42] **Ben:** I have

[00:13:42] **Tim:** there there's a website for you, Ben, just, just Google speed test. You'll

[00:13:46] **Ben:** but like, I don't know what's good or not. if someone said, oh, I got 400 megabits. I'd be like, that

[00:13:51] **Ben:** sounds pretty fast.

[00:13:53] **Carol:** Pretty

[00:13:53] **Adam:** a lot of

[00:13:53] **Carol:** for home. That's good. Yeah. Yep.

[00:13:57] **Ben:** I don't know, like, in terms of like, it's like refresh rates on monitors, like at some point the human eye just doesn't pick it up anymore.

[00:14:03] **Ben:** I, I don't know what the megabit is, where we're like, I'm no longer able to consume information that fast.

[00:14:10] **Tim:** for me, it's like, what can you do with it? Right. So it's like, I think around 25 megabits per second, you can download 4k streaming videos. So yeah, anything above, if I can download 4k and watch, YouTube and 4k. I'm good. anything

[00:14:26] **Tim:** less

[00:14:26] **Adam:** you need that, that 25 megabit to be for your stream. So if you've got other people, if you've got nine phones in the house, all checking their email and kids watching YouTube and yeah.

[00:14:36] **Tim:** for sure. ha. Having one gig down is fantastic.

[00:14:39] **Adam:** yeah, I have

[00:14:40] **Carol:** great. Yeah. Ben, where's your gigabit

[00:14:44] **Ben:** I have no idea. we just had the switch at home. We were on Verizon FIS and I think that was some, is that fiber? I don't know if that's fiber, but it was

[00:14:53] **Adam:** Did he just refer to his previous place of domicile as at home?

[00:14:58] **Carol:** Yeah.

[00:15:00] **Ben:** And here we had to switch over to something called spectrum. I don't really know anything about it, but it's, we're in the country here, so

[00:15:06] **Carol:** It's probably a local thing. Yeah.

[00:15:08] **Ben:** that's

[00:15:09] **Tim:** well, I'm in the country and we finally got fiber.

[00:15:10] **Tim:** but that's my fail. How about you, Carol?

## [00:15:13] Carol's Triumph

[00:15:13] **Carol:** well, I'm gonna put this back on the triumph wagon, so yeah. Yeah. I'm gonna help this team out. we've been working on this big communication enhancement effort at work and it went into production on Tuesday and there have only been like three super minor issues reported in the post-release and one of them.

[00:15:34] **Carol:** Some static image isn't mapped. Right. And I didn't realize that because I didn't test it outside of the environment where we were at. So I didn't think to think how it would map elsewhere. So I went and fixed that another one was like, they were, able to put emojis in messages, which we already knew.

[00:15:51] **Carol:** That was a thing. Just, no one said it was a bad thing. Like no one said don't allow it. Like I knew they could do it. I saw it already. Yeah. So like they were super minor, but this is a huge win for us. Like it's reducing, the touch points for our customer service team by like 33% already. one part of the company it's taken their communication inside email to almost nothing.

[00:16:14] **Carol:** So everything is internal now. So this is all great. And everything just went really well. And when this effort was being released, we had the retro the day after. And the product owner was like, this is just so smooth. I wasn't even sweating this at all. And I am in the, like, back of my head going, this is two months of code.

[00:16:36] **Carol:** That's sitting here that at the end of it, there was so much codes, fatigue that I don't remember everything I wrote up front. So I was sweating it cuz I was like, oh God, did I cover that scenario? Did I cover this scenario? Like I'm running through everything in my head. I got married. I had a honeymoon, a lot happened during this whole project.

[00:16:53] **Carol:** So I come in and back like two a week and a half into being back. We're releasing this and I am freaking out on the inside going, I don't know if I covered everything. Oh God. And they're just like, oh, we're good. This all looks great. And they have so much confidence and me and this other engineer that wrote everything, it felt great to have their, like their boost of confidence.

[00:17:13] **Carol:** But I was like, I was sweating it when I had to release that code. I was definitely sweating it. So then for it to actually go out and there only be. Few minor things that are so just superficial that nobody even cares about them. So it is just that it went out great. And whew, I didn't

[00:17:30] **Adam:** the code movers came over and they were there on time and they got all the code moved to production, no issues, nothing

[00:17:36] **Carol:** And we no, nothing. And then we went out in the front yard and we hit balls, like happy Gilmore dead. Yeah. I just recently watched that movie. That's why I know that

[00:17:45] **Tim:** she

[00:17:45] **Tim:** got that reference?

[00:17:46] **Carol:** went out and hit golf balls with his movers.

[00:17:50] **Carol:** So you hit complexity and it worked. By the grace of God or some other entity inside my code that saved it all. I don't know, because I was definitely very scared that this hung out for so long and it was so confusing upfront with what the customer actually wanted and what we were gonna deliver. There were so many changes that this whole epic has like multiple stories in there right now that are phase two, because they were things they wanted in the initial design that then they decided they don't want 'em anymore.

[00:18:21] **Carol:** So I had to pull all that out of code. Like it was things we'd already coded. Some of it, we had some of we hadn't, so that had to get like ripped out and moved to a second phase. So yeah, there was a lot of moving parts with it and somehow the complexity got shipped and it shipped accurately this time.

[00:18:39] **Adam:** Yeah. This time.

[00:18:40] **Carol:** this time.

[00:18:43] **Adam:** Well, congrat.

[00:18:44] **Carol:** Thank you. Glad I could bring it home for you guys.

## [00:18:47] How Many Open Pull Requests Do You Have?

[00:18:47] **Adam:** Yeah. So, yeah, a as we have very thoroughly, I think at this point, alluded to the topic for today is gonna be,the amount of complexity that can build up when you're kind of like batching a release. And so I think maybe the best way to intro this is,not so much a competition, but let's just, pull open the kimono here a little bit.

[00:19:07] **Adam:** And want everybody to tell us, how many open poll requests you currently have on like your primary repo or your big project

[00:19:15] **Carol:** Oh, okay.

[00:19:16] **Tim:** who wants to first

[00:19:17] **Tim:** on. I'm gonna get him.

[00:19:20] **Ben:** I can't get to it. Sorry. Cause I'm not on the VPN in our GitHub as a

[00:19:24] **Adam:** do you have a, do you have a gut feeling.

[00:19:26] **Ben:** It's probably hundreds, I would guess. I mean, you know,it's over, over the course of 10 years, a lot of teams have come and gone. I'm sure most of them are nonsensical.

[00:19:34] **Adam:** so you're talking about open poll requests, not issues.

[00:19:37] **Ben:** yeah. Open portal credit. I would, I'm gonna throw out, there's probably like 167.

[00:19:42] **Tim:** Wow.

[00:19:43] **Ben:** I mean, I'm just guessing that's like a total guess.

[00:19:45] **Tim:** Wow.

[00:19:47] **Carol:** we have, I don't know, 10 to 14 ish developers right now working on our project. And I think there are currently like maybe 12 open poll requests. 13. There's not, I don't, I can't imagine there's over 20.

[00:20:04] **Tim:** So, I mean, I suggested this topic because I saw, a blog post about this and it kind of hit me where I live because I have a project that, I call it toffy, which is basically a take on taffy cuz it's based off of your taffy, Adam. it's an API. And so it's like, I was the only one working on for years.

[00:20:25] **Tim:** Right. So I was the only, it was all, it was my baby. It's like, I was just constantly just, I make a change, pull it, post it, and now I've opened it up and other people working on it. And so like a couple weeks ago I had like 15 poll requests. Right. And it's like, I review them. They seemed okay. But it's like, I tested them as best I could.

[00:20:44] **Tim:** And the, the, uh,the unit test passed. Right. But it's like, I'm like, okay, lemme just go pull this and everything broke. Because it's like a way to, you know,I don't really don't have a continuous integration set up right now for this project. I need to get one set up, but I just realized it's like, the more stuff you have out there, the more complex it gets.

[00:21:07] **Tim:** And if you don't, if you aren't constantly like pulling that in and testing it and promoting it and having it, be tested in real world applications, you don't really know if it works or not. So it's like, so it had a lot, but right now I have three. So I looked at, and they all came today, eight hours, 11 hours and one yesterday. so

[00:21:26] **Tim:** yeah. so I have three open right now.

[00:21:29] **Ben:** these are not poor requests that you've opened. These are poor requests that other people have opened

[00:21:32] **Ben:** that you're

[00:21:33] **Tim:** Right. Which scares me. I know, I trust my stuff. Right. I'm like, okay. I know exactly what I did. And like, I'm reviewing some of these. And like, I disagree with some of the logic, like, She's wanting to put stuff in a database. I'm like, I don't really know if this needs to go in a database.

[00:21:47] **Tim:** I'd never really had a database connected to this at all. I don't, And so like I'm balancing the, being the dictator versus being a collaborator, with my code, cuz it's like my baby, but it's like, all right, we'll try this. But, and some stuff broke and so now I've have,comments on the poll request, which I never usually do.

[00:22:07] **Tim:** I don't, obviously I never put comments on my own stuff, but now I'm putting comments going, you know what? I don't know if this needs to be in the application scope because we have one application, but multiple tenants. So how are we gonna deal with this? Cuz right now the one of the issues is like whoever the last person was that gets the application scope wins.

[00:22:26] **Tim:** And in a tenant situation, that's not necessarily great because it's like I have multiple tenants and now some reason customer a thinks it's customer B. That's not good.

[00:22:35] **Adam:** Yeah, that's worse than not great. That's bad.

[00:22:37] **Carol:** Yeah.

[00:22:38] **Tim:** really,really bad. So, so I put in a hot fix to fix that and like, yeah. Put comments on the pool, a pool request to fix it.

[00:22:45] **Tim:** I'm like, you really need to look at this. I don't think you're putting this application scope, but this is one application with multiple tenants. So who's gonna win on this one.

[00:22:54] **Carol:** Right. What about you, Adam? I wanna hear your numbers

[00:22:57] **Carol:** real

[00:22:57] **Ben:** side quest for a

[00:22:58] **Ben:** second? Just a quick side quest here. I almost never ever actually run people's code in a pull request. It's all just like visual thinking and stuff. It, how often are you guys actually pulling down and testing the code? That's in a poll request.

[00:23:14] **Adam:** I think that is a very relevant question for today's discussion. because I think that what we're gonna get into with the different complexity and the amount of stuff that you batch up,how you test it and how you deploy it is gonna come into it. And I think that your approach Ben relies heavily on feature flags and the assumption that this code is already deployed and somebody has.

[00:23:36] **Adam:** Probably if they're doing their due diligence, turned it on, like just for themselves to poke in production. and so like it, whether or not people agree that's the, the right way to do it, which, you know,we're sure there's at least one person out there who disagrees, even if just for the, opportunity to disagree.

[00:23:52] **Adam:** but, that's, that's gonna influence your approach for sure.

[00:23:55] **Ben:**

[00:23:55] **Tim:** Yeah, I'll tell you this, Ben. So it's like I, until. Today yesterday, actually I didn't, I would look at it and go, yeah. Okay. This kind of makes sense. And then some issues came up and develop. Fortunately, didn't get to production. This was in, development environments that, that started showing issues.

[00:24:14] **Tim:** It's like, I didn't really test it until then. I would look at it, go, okay, this kind of makes sense. I see what you know is going on here. I see what they're trying to accomplish. Makes sense. I don't see any formatting errors, approve it, but it's like,

[00:24:25] **Ben:** Gotcha. All

[00:24:26] **Tim:** whenever people's application scope started getting cross mixed, I'm like, all right, I really need to test this.

[00:24:32] **Tim:** And so I tested it and that showed me the issue. And so that's when I'm like, okay. Yeah. so so I guess the answer to your question is if it is significantly. Complex where you can't really look at it and eyeball it and go, all right. I get what they're doing. The only thing you can do is pull it down and run some unit tests and run some functional tests and say, is this actually doing what I think it's supposed to be doing?

[00:24:59] **Carol:** I'm with Tim there. I look at the PRS and I'm going, Hey, if I don't understand what the code's doing, if I can't just read it, I go run it. But anything that I can read and kind of get a feel for what they're trying to accomplish. And the understanding matches like what's in the request I move on. I don't run it locally.

[00:25:16] **Carol:** I only do that. If I do not understand the code

[00:25:19] **Adam:** I want an opportunity to jump in here before we go back to the main thread too. on my team, we have a chaos monkey. He also just happens to be the one that signs the paychecks. so there's not a whole lot you can do about that. and, look, I don't wanna throw anybody under the bus, but,there are times that the code that he submits is great and it works great.

[00:25:37] **Adam:** And that's fine. And then there are times that during the code review, I go, okay, you definitely haven't run this because there's no way this will, this is not even like Sy tactically valid. Right. You put in an L where there was supposed to be a semicolon and that's not gonna work. Right. and so that's when you throw it back and you go, you got some errors here and also I wanna see some evidence of this running, if not on your local machine, then, it's real easy to merge it into QA and that'll automatically deploy it.

[00:26:00] **Adam:** And then you can,you can show me some screenshots or whatever of it running in QA. So, yeah, that like, that kind of has become my crux for certain types of our apps. It's become difficult to, if you weren't the one who originally developed it, it's can be difficult to get it running locally initially, like, cuz you kinda have to figure out, okay, how am I gonna wire this all up?

[00:26:22] **Adam:** Which is a whole other discussion. But the ability to just merge it into the QA branch and push that code to the repository and that automatically triggers a build and a deploy and you can go see the code running in the QA environment I think is a huge, productivity boost for us for things like that. Okay.

[00:26:43] **Ben:** insight.

[00:26:44] **Adam:** Yeah. Okay. So my number then we're gonna go back to the main thread here. I win by the way. just our primary repository. we have maybe a dozen or two of like, little side repositories for little projects that are kind of on their own, but we have a sort of a, I won't call it a mono repo, but we do have like our main repository that has the core of our applications in it.

[00:27:07] **Adam:** currently has 262 open requests. and I will admit this does get under my skin. I have a, a private channel in our team chat that only I am in. It's called hello darkness, my old friend. that's, the name of the channel and when stuff like this, when I notice it and it gets on my nerves, I just take a screenshot in it and I post it in that chat room and then only I can see it.

[00:27:27] **Adam:** And it's just that little release of catharsis for me. It's like, okay, I have admitted that this is a bad thing that the universe is aware and I can move on with my day. so yeah, I have 262 open poll requests and the vast majority of those are automated dependency update poll requests for either Docker or JavaScript stuff.

[00:27:48] **Adam:** So like for example, we have a bunch of apps that run in, Docker containers. most of those are node things. but like, so say we're built on, such and such version of Linux for the Docker container. there's a bot for GitHub while of our code is on GitHub. There's a bot called depend abot.

[00:28:03] **Adam:** They'll say, oh, you're running version 1.2 0.3 of whatever version of Linux, but there's a 1.2 0.5 available, and it submits a pool request to upgrade you. And that's fine. Like, it just changes that version number in the Docker file, and submits a PR. Now you have no idea if that breaks anything, but there's the PR like it saves you that step.

[00:28:21] **Adam:** And so then you could in theory, download that code locally and try to run it. See what, what happens. You could run your test suite if that's something that you have,and see if anything breaks. a lot of these, we do not have tests for. So, and that's the thing is,it would be much, much worse, but, the things that are relatively trustworthy of obeying SIM, which if you're not familiar, sim.org, S E V E R, it's stands for semantic versioning, which is that, you have.

[00:28:52] **Adam:** Version number, right? Like major dot minor dot patch. Right. So one do two do three. that first number, the like version one version, two version three sort of thing. only gets incre only gets incremented when you have a breaking change. So back in the old days of software before SIM, before, before I've really had any, inkling of professionalism, I was just some kid making screensavers for his, computer.

[00:29:14] **Adam:** it was like, oh, this is a huge new update, to the thing that I wrote. So I'm gonna increase

[00:29:19] **Adam:** the major version number exactly. Right. It just felt like it deserved it. So that's why you increase the version number. and for SIM that's not the case, you only increment the major version when there are breaking changes.

[00:29:30] **Adam:** and then if there are like additions, oh, this is a huge new update, but it didn't break anything. Then you increase the minor version. The second, I don't know, segment. Whatever we're gonna call that. and then if you have just like little things, you changed a string somewhere from you, you fixed a spelling mistake.

[00:29:45] **Adam:** That's just a little like a bug fix sort of

[00:29:46] **Tim:** Our security patch.

[00:29:48] **Adam:** Right. then you would increment the patch version, the last segment. so the depend about pull requests that come in that are minor or patch versions. I, if I trust that project enough, right. If it's not just like Bob's library, that does this thing, if it's actually got a huge adoption from the community, if it's like something like react, right.

[00:30:10] **Adam:** You can trust, react to not break something with a minor or a patch release. and so I will kind of blindly accept those. If we don't have tests for that project, it's like, okay, I trust this. And if it ends up breaking something, then it's easy to roll back. So I'll accept that and publish and deploy that.

[00:30:27] **Adam:** but the ones that are building up here that we have 260, 2 of there's, some other stuff here from our recent work, that is our work. But the vast majority of these, I would say probably over 200 of these probably closer to 240 of them are these automated poll requests that are major versions of something that we haven't upgraded.

[00:30:47] **Adam:** And that I think that speaks to, not just the JavaScript app ecosystem that we find ourselves with in 2020 and beyond. but that's the current year. Yeah. I'm aware. Thanks.

[00:31:01] **Ben:** Yep.

[00:31:01] **Adam:** I, whatever, you gotta draw a line somewhere. and, but so like, I think that. Like now within like say the last year, my personal experience, my team and I, from what I can see the community at large is getting a lot more mature in our dependency posture.

## [00:31:19] Dependencies And Build Systems

[00:31:19] **Adam:** We've been, trying to use things that have less dependencies so that your tree doesn't explode just because you added one thing and it depended on 12 things. And each of those 12 things depended on 117 things. And then all of a sudden you have 10,000 dependencies. so the problem with that dependency explosion is that, okay, well then, every time any one of those gets an update or there's a security problem with them, then you've got like a huge blast radius to that change.

[00:31:46] **Adam:** and it's just impossible to stay on top of that. And so I think as a result, the approach that we used to take, and when I say we, I mean, me and the people I have worked with, but probably a good segment of the community, the developer development, whatever community, where we used to like build an application to, to resolve a project, to do what was asked.

[00:32:05] **Adam:** And then it goes into production and it just kind of sits there on a shelf for like five years until somebody asks for a change or something goes wrong, or need to integrate with something. And then, okay, you pick it up off the shelf and you dust it off and you change the thing. Well, now that we're like, depending on everybody else's modules and, libraries for things so much, the pace of change has gone like through the roof and. What I'm I've been calling it rot, right? Like our applications are sitting there on the shelf rotting away because things are changing in the ecosystem and those changes are not being reflected in our application. And then, you have an app and it, maybe it was built with,a build tool that was very relevant five years ago.

[00:32:45] **Adam:** With the last time you worked on it and you used libraries that were, totally, up to date at the time you come back to it in five years, and now like you can't even run the compile anymore. You just do MPM install and compile. And for some reason, something broke because there's a SIM compatible module that got updated.

[00:33:02] **Adam:** But you know, it somehow just because it's all so old and rotten, it breaks your build. Yeah. It's just, it's a nightmare. And so I've been personally trying to move away from dependencies as much as possible.

[00:33:16] **Ben:** I think I had mentioned this on a previous episode that I recently built my first gulp JS plugin for, trying to update a part of our build system.

[00:33:25] **Ben:** And it was really

[00:33:25] **Ben:** frustrating because I kept looking for an existing module on NPM. And, I would look at one that we were currently using that wasn't quite doing what I needed and I would go to the NPM JS page.

[00:33:37] **Ben:** And at the top, it'd be like, this project is archive and has not been edited since like 2014, just like, oh my God, this code, our code

[00:33:48] **Ben:** is

[00:33:48] **Ben:** so old.

[00:33:50] **Carol:** my goodness

[00:33:52] **Adam:** We recently like within the last year, maybe 18 months we upgraded, our main app was using, not gulp, but what's the other one grunt. Uh, so gulp was all like in memory where, grunt was file system based. So we upgraded from grunt to do all of our JavaScript com compilation and bundle creation.

[00:34:10] **Adam:** To ES build and I love it could not recommend it better more.

[00:34:14] **Ben:** Yeah, it's supposed

[00:34:17] **Adam:** is

[00:34:18] **Ben:** to be super fast, but that's gotta bea pretty big lift because I assume the grunt stuff was doing all kinds of funky, not funky stuff, but like a lot of configuration and intermediary steps. And.

[00:34:29] **Adam:** the thing is, all the stuff that we weren't doing anything crazy. It was just, you had to do the work of setting up the configuration to, to build the bundles you wanted and to set up, okay, I want you to first,concatenate all the JavaScript together and then build a source map.

[00:34:45] **Adam:** And then, minify it, that's the word I was looking for,and all these steps where, you plug it into build, you say, okay, here's the input file. This is what you want. I want you to name the output file. And it just does that because like that's sort of industry standard now

[00:34:57] **Adam:** bundle and.

[00:34:58] **Ben:** Gotcha.

[00:34:58] **Tim:** Yeah, our build system is so old and it's so janky. I don't even know if I can update it without a huge hassle cuz

[00:35:06] **Carol:** It's so scary, right?

[00:35:08] **Ben:** well. Yeah, cuz it's and that's the thing is like it's doing so much stuff and the code is so convoluted that even if I went to try to update it, I'm not even sure that I would understand the breadth of the things that I'd have to test to make sure that there wasn't some funky edge case where like a HTML template didn't get unified in a weird way that took out white space that needed to be there to separate elements on a page or something, it's just.

[00:35:34] **Ben:** and like ours also injects metadata about the JavaScript files into the ColdFusion templates that get rendered. And it's, there's some complexity.

## [00:35:42] Releasing Big Changes

[00:35:42] **Tim:** So, I mean, the article that I saw that kind of got me thinking about this was talking about Ethereum. Which is a crypto. It's not a cryptocurrency, it's more of the crypto network that cryptocurrency works on. I'm not advocating crypto in any way, even though I do invest heavily in it. but so they have delayed.

[00:36:04] **Tim:** So they're trying to switch from proof of work. So proof of work is where you have to do like a extreme, like sort of calculations to prove that you solve this mathematical problem in order to mine, a, Bitcoin or whatever version of currency you're doing, to validate transactions, to, proof of stake, which is a lot less, in compute intensive.

[00:36:26] **Tim:** So that, basically they're trying to like deal with the problem of that. Crypto is extremely, energy intensive that causes, greenhouse gases, cuz everything's running off electricity and electricity is running off coal. And so it's like, they're trying to. Lower their carbon footprint, which is a great thing, right?

[00:36:43] **Tim:** It's an awesome thing they're trying to do here, but they have, delayed. So the switch from the proof of work to proof of, stake is such a big change. And there really is no governing body. This sort of like a consensus kind of mechanism, no one is like saying, you need to ship this. Now they keep delaying it.

[00:37:04] **Tim:** They've delayed it before and today they announced they're delaying it by another a hundred days. So like sometime in September, they're possibly gonna to push this, but they don't know when it's gonna happen is it's a hundred percent because of fear of promoting something that has a huge, they call it a difficulty bomb.

[00:37:23] **Tim:** We call it shipping complexity on this show, but difficulty bomb is what they call it. and even though like, like, like I said, My small dealings compared to what they're dealing with is much smaller. But I get that. It's like whenever you have too many changes, trying to get changed at one time, it gets really hairy.

[00:37:44] **Tim:** And so how do you deal with that complexity? How you deal with that difficulty bomb from blowing up in your face?

[00:37:51] **Carol:** it's called test. No, uh,

[00:37:55] **Carol:** so I hit, if this isn't the same by any means, but Ithat's where I was with this project just went out. I was sitting there. if business hadn't have already submitted everything to our customer saying, Hey, here's the release date?

[00:38:07] **Carol:** This is all the changes you're gonna be seeing. Here's how you're gonna use the system. Now I would've like been sitting there going, I need to just hold this a few more days. Like I just need to go review it more. I just don't trust myself. I don't trust that. I tested everything. I am terrified to, to send this out because.

[00:38:23] **Carol:** When this goes out, there's no more communication. The way they use to communicate emails don't exist anymore. Like it's, they're not there. So I'm like, what if,what if someone's not using, like, what if doesn't work then we don't know someone needs help. What am I supposed to do? And like, in my head and inside my gut, I'm freaking out.

[00:38:41] **Carol:** So, I mean, if product hadn't been sitting there going, Nope, we're going and we trust you and we trust what you've done. I would've totally held this go a lot longer and been like, let me just take a fine tooth comb through it again and make absolutely certain, there are no knots Noles, no nothing. And yeah, before I would've released it.

[00:38:58] **Carol:** So I can't imagine when you have something, this visible to the public, going out with a massive change, it's just been stacking on top of each other for how long. The thought of releasing that now terrifies me. This is why we develop small, right? This is why I do small things. I go out small because it's a small break.

[00:39:16] **Carol:** It's not huge. And I get, there are times when it has to be something big, but man, I would be terrified to be sitting on that team right now. I don't think I'd be sleeping.

[00:39:27] **Adam:** you guys use facial flags, Carol.

[00:39:30] **Carol:** we do not. Actually we are talking about adding them. We do not use feature flags yet. we've brought it up in multiple conversations that this,

[00:39:36] **Carol:** like, this would be a time when we should use it.

[00:39:40] **Carol:** So I think it, it is something we'll be speaking about and planning into the version that we're just starting to plan and code now, but it's probably not gonna go into the legacy app.

## [00:39:50] Legacy Apps

[00:39:50] **Ben:** Well, speaking of legacy apps, I mean, my work is like the ultimate illustration of it. II've many times alluded on this podcast that I'm working on the quote unquote legacy platform, and they've been building the new platform for, going on like God, like five years or something

[00:40:10] **Ben:** insane. Right.

[00:40:12] **Ben:** and it's like, not only did they have the big bang rewrite that they were attempting to do on their end, but that entire time, the old platform is continuing to move forward and continuing to add features and continuing to refine existing features and fixed bugs. And all of that has to then either be poured explicitly over to the new platform, or they have to either implicitly or explicitly decide not to port something and then deal with the fact that customers might be bothered by the fact that there's now a feature parody gap between the two platforms.

[00:40:43] **Ben:** I mean, it's the big bang rewrite is like in, in a way the ultimate form of shipping complexity

[00:40:49] **Carol:** Oh yeah.

[00:40:49] **Ben:** in a, in not a great way.

[00:40:51] **Carol:** Yeah. I mean, I don't have my head fully wrapped around how we're going to achieve this yet. And I know we're in early discussions with just architect and how we actually plan on doing it. But my head just kind of spins because if the idea isn't to do small services, that we then can port into the legacy so we can turn off areas of the code and the legacy and use the new version, then I don't understand how they're gonna work in parallel or how we would ever port someone over because we're constantly developing new in the old system.

[00:41:23] **Carol:** And it just seems like the new would never catch up with what we're still putting in the legacy. So

[00:41:29] **Carol:** it's gonna, it's gonna take some time.

[00:41:31] **Adam:** I can't find it, but there was a tweet that I saw, come across my tweet deck sometime in day or two. That I thought was really kind of insightful and really applies here, which was basically somebody did the math. and they said like, if you have a legacy app and it's receiving like, a quarter of a week's worth of effort for, bug fixes and that sort of thing.

[00:41:52] **Adam:** and, I wish I could find it the basically like what you were talking about, Ben, you've got this new product you're trying to rewrite and you're trying to get parody with the old one. Right? So you're starting from scratch. You're trying to do it the right way lessons learned, but still, also reimplement all of the existing functionality, but then you've got the legacy app still sitting there and people are still using it, still finding bugs.

[00:42:14] **Adam:** You're still trying to keep it alive. the amount of time, and it wasn't even that big of an app for this example where the guy did the math, but it was like, it was crazy. Like if. Maybe it was just like, if you spend a quarter of your time on, bug fixes for the legacy app and the rest of your time on feature parody, it was something on the order of like thousands of weeks to complete that project. And it was, like I said, it wasn't even that big of a project that he was starting with. He, it was based on, like number of features or lines of code or something. I don't know. But when I saw that it was just kind of mind blowing. It's like, there's, it's an impossible problem.

[00:42:50] **Ben:** I had a former engineering manager, this guy, rich Armstrong was trying to explain it to me a couple times. There's some sort of like queuing theory where. You have to work at like less than 70% of capacity, cuz the moment you go over that, it's like, you're, it's like you're bound to never catch up with the

[00:43:09] **Ben:** amount of work that you have to do.

[00:43:10] **Ben:** And I, and there's math behind it. I didn't understand the math, but it's he illustrated it. there's a book that illustrates it, but it's, it feels like very much the same kind of thing.

[00:43:19] **Ben:**

## [00:43:19] Deployment Problems

[00:43:19] **Ben:** here's a gripe that I have, which is that I am often frustrated when deployment of code is not everyone's highest priority at work. Cuz for me, the idea of shipping code to production is. Critical to the idea of reducing complexity and keeping things simple and shipping small and shipping iteratively.

[00:43:43] **Ben:** So when anything in the deployment process breaks, I feel like that should be, I don't wanna say like an all hands on deck incident, but I feel like it should be an incident. And, and what I

[00:43:54] **Carol:** yeah. Mm-hmm. More

[00:43:56] **Ben:** and I can't compare this to anyone else's company culture, but I feel like at work when deployments are not working properly, it's sort of a, it's not special.

[00:44:06] **Ben:** Like it's the same way you would treat anything that might be an issue where a ticket gets opened and then someone gets assigned to it and then it gets the, a job gets worked and then they figure out maybe what's wrong, or maybe they just try to reset something or tell you to do it again. And I feel I get so angry, internally, obviously on the external, facing part of me, I'm very pleasant.

[00:44:27] **Ben:** Internally I'm like, how is everyone just not dropping what they're doing and getting my code to production? And it's not, cause my code's super important it's because like, how is the code that you have not completed more important than the code that is completed? That's ready to be facing customers.

[00:44:42] **Ben:** Like it just boggles my mind.

[00:44:45] **Carol:** That's just gonna be sitting there waiting for a conflict to happen now with people coding behind you. Yeah, no, it, it is a priority for us. If something happens with our deployments, it is all hands on deck.

[00:44:56] **Carol:** So we do take it very seriously.

[00:44:59] **Adam:** Ben, are you talking about, a failure to deploy or a deployment of code that has failed like a bug in the code sort of thing?

[00:45:08] **Ben:** like, like I'm talking about, so, so at least at work, our deployment pipeline is mechanized through chat bots and like get hub web hooks and, there's turtles all the way down that I don't really understand. and oftentimes something in that pipeline will break, not all the time.

[00:45:28] **Ben:** Oftentimes this may be an overstatement a lot of time, a lot of the time it works perfectly, but then sometimes it doesn't, and it's not clear to the developer who's using the deployment system, why it's not working, it just doesn't work. and, our platform team bless them are completely understaffed and overwhelmed.

[00:45:44] **Ben:** So I feel really bad for them, but I always feel like deployment is the most important fire that could be burning at any moment.

[00:45:52] **Adam:** I would agree with that. like if you can't deploy, then you can't do anything else. You can't fix anything. You can't

[00:45:56] **Carol:** What's the point of working. Yeah.

[00:45:58] **Ben:** not only that. It's one thing to consider the code that hasn't hit production yet that needs to hit production. And then it's another thing to consider. What about the code that's already out there that might be having a bug in it and might have a critical issue that you're only about to find out in five minutes and then what happens when I can't deploy a hot fix or roll back, something like that, that could become a super critical incident, except we just don't know about it yet.

[00:46:22] **Ben:** And then that's why deployment's just so

[00:46:25] **Adam:** I meanthe stuff you're talking about, I is sort of the fundamental theory behind my favorite presentation about automated deployments, which is basically just like the faster that you can go from. I would like this code to be deployed to, the, to, it is now running in production and everything's normalized the faster you can make that jump.

[00:46:47] **Adam:** The healthier your code will be. just in general, because you won't have any waiting, like if it was an instant thing, you commit the code and you push it and now it's running in production. Then there is no delay, for process when you push out a bug fix or a new feature, whatever. and so when there is a fire, there's no wait.

[00:47:06] **Adam:** Right? you have that safety net, where I can deploy this and something, if something goes wrong, I can fix it more or less instantly. Right. I can roll back or I can see what the problem is and deploy that fixed instantly.

[00:47:17] **Adam:** So it reduces your fear of deploying, gets rid of that fear of deploying on Fridays, right? Like cuz you know, that's 20% of the work week. if you're not deploying on Fridays, you're only. Utilizing 80% of your work week. anyway, two things that kind of went through my mind when you were discussing the, like, the way that deploys not working is being treated as like a ticket, I mean, on one hand it's I wanna say this without any judgment intended, it sounds like, deployment issues has become routine, right?

[00:47:50] **Adam:** So when it becomes a routine thing that they're experiencing, they treat it like any other routine thing, like a support request. Right. So, oh, okay. that happened again, let's file a support ticket so that we can, get it in the work queue or whatever. Whereas if it's a, if it's an anomaly, then it seems more urgent and people are more ready and willing to jump on it.

[00:48:08] **Adam:** But at the same time, the other side of that coin, I think is that. It could be seen as a sign of like maturity and professionalism, I guess maybe like if you have an issue where deploys are breaking and you want to fix this systemic problem, why are deploys breaking so often or too often? then you need to do root cause, diagnosis.

[00:48:35] **Adam:** and if you just, if it's all hands, jump on a fixed problem, we did it. Then there's no thought put into how do we keep this from happening again next week? Cosmic

[00:48:44] **Carol:** Can

[00:48:45] **Ben:** Yeah. Yeah. Well, it's funny you say that because, oftentimes in our deployment pipeline, if something breaks and I wait an hour and then try it again, it'll just magically work and I have no idea why and yeah. Yeah. and I'm, every time it breaks though, I open a ticket and I want them to investigate because for that exact reason, if I just retry and it works, then we don't learn anything.

[00:49:11] **Ben:** And all it does is waste my time. But if you actually investigate and figure out why it's broken this time, then maybe it won't break next time. And there's so many moving parts. I don't know how feasible that is, but I a hundred percent agree with that mentality.

## [00:49:27] Continuous Integration

[00:49:27] **Adam:** Yeah. So I think that we have, done a fantastic job of not talking about today's topic. uh, uh, we, we, we kind of talked about how we were, gonna talk about, building up complexity and trying to, how do you deploy that? and then we never really did that. I made a bunch of excuses for, why I have so many open poll requests and

[00:49:46] **Adam:** we beat around the Bush there, but does anybody have any actual thoughts on like, processes or advice for dealing with this problem?

[00:49:52] **Tim:** Yeah,

[00:49:52] **Adam:** Mm.

[00:49:53] **Tim:** yeah, I do. Don't ship complex stuff.

[00:49:56] **Carol:** build small.

[00:49:57] **Carol:**

[00:49:57] **Tim:** small. I mean, and I get the challenge with, Ethereum, trying to do, they're trying to do basically rearchitecting their whole entire network. Right. Really? That should just be, they should be releasing another version of Ethereum and having people move over to that's really the play that they should do.

[00:50:15] **Tim:** They've decided to do it as they're gonna kill Ethereum 1.0 and release 2.0 and hope that it goes well. And I just think that was a bad. Plan from the beginning, they should make it an option. Right. And slowly choke Ethereum 1.0 out, right. until it doesn't exist anymore. And be, and I don't think most of us deal with that sort of situation, maybe if you're moving from a legacy system to a new system, but honestly you can still kind of tamp that down and gate keep that to where it's like, you slowly kill off one while the other is actually running in parallel.

[00:50:54] **Tim:** yeah. So I think the thing is like, keep on top of your pull request, constantly integrate. And if you do that, you're not gonna have, you're not gonna face this complexity bomb, that they're dealing with. but. If you don't have good processes in place, like, I didn't recently it's like, it didn't get that complex.

[00:51:11] **Tim:** It was only like 14, 15. It got really difficult to deal with. And now I'm on top of it and, I'm researching how to, just constantly integrate these things. So that issues get determined earlier rather than waiting for, merge requests that, conflict and like problems that to deal with.

[00:51:28] **Tim:** So yeah, just, yeah. Constantly integrate. I think that's the solution.

[00:51:34] **Adam:** it, I like that you use those words. So you're what you're alluding to. There is continuous integration. and I saw, I probably talked about this on the show, not too long ago, but I saw this great YouTube video about continuous integration. that kind of opened my eyes up to how true continuous integration is different from just running my tests every constantly, while I'm making changes and merging and deploying as much as possible.

[00:52:00] **Adam:** Again, I could be totally wrong here, but the, my current understanding is that, the goal of continuous integration is to take everybody's work in progress and get it in the same place at the same time. So that if the thing that I'm currently working on breaks, the thing that you're currently working on, we figure that out before either one of us goes to production so that we can resolve that conflict.

[00:52:21] **Adam:** and so the way to do that is to have, whether it's a dedicated testing branch or something like that, but everybody's constantly merging your code there. If it's behind a feature flag that could work too. and that way your changes and my changes are running in the same place at the same time.

[00:52:35] **Adam:** And that way, when I'm running my tests,I could see when stuff is breaking and yeah, I mean, it's funny how much I have learned since we started this podcast and how much I feel like I've personally grown as a result of having these conversations with you guys. with the community, I've learned so much from the people in our Discord and, become a

[00:52:53] **Adam:** better programmer for it.

[00:52:54] **Tim:** One thing I was gonna say is like, and I think unit tests are. ButI think functional tests when it comes to deployment are even better. Right? So I have, I have a test harness of functional tests that just actually run the process, right? So it's in a development environment, it's going against development data.

[00:53:12] **Tim:** It's, nothing's in production. And so actually running the actual thing that's going to be happening in production is extremely important. And it's somewhat easier because, I'm not dealing with UI. I'm pretty much dealing strictly with APIs. So I could do like constant API calls. I have a harness of API calls that, that run, I can run a whole entire suite of them and if they error or they break or they don't give me the result I'm expecting, I know it immediately.

[00:53:38] **Tim:** So that is extremely important because,if you're merging in a bunch of different people's stuff and you're not getting the result you expect from the functional test, then you're not gonna get the same result. you're gonna get a bad result in product in production. if you pro.

[00:53:52] **Adam:** You, I think you do have a UI, your UI is just J or XML or something. Right. So, I think that's, in some ways, I think I'm jealous of you. I wish that I could just not have to worry about designing UIs in the first place, but also having to work around testing them. that tends to be one of the hardest parts.

[00:54:09] **Adam:** And when you're saying functional tests, I'm thinking that sounds a lot more like what I would call an, end to end test. If you're like going from the front end all the way to the database and back. Maybe you're not thinking of it because you don't have the UI, but,

[00:54:22] **Tim:** Well, I mean, it in effect is because, I mean, it, you're basically sitting a J payload. It's going to a database. It's gonna do a bunch of stuff and come back and it's either gonna error, or it's gonna give you a valid J on response.

[00:54:35] **Tim:** So.

[00:54:35] **Carol:** I just, I wanted to know how many times you deploy.

[00:54:38] **Adam:** me

[00:54:39] **Carol:** Yeah. You,

[00:54:40] **Adam:** like how often, how many times per

[00:54:42] **Carol:** Yeah. Yeah.do you like multiple deployments a day if needed?

[00:54:47] **Adam:** Yeah. Oh, absolutely. for QA and for a lot of our stuff that is easier to automate like, Lambdas and other things, that are not. So we have a series of EC two instances that are very,bespoke and hand made. And then we also have a whole bunch of other like satellite services that are like more cookie cutter in terms of their architecture, their infrastructure.

[00:55:08] **Adam:** And so all of those other satellite things, it's really easy. we merge the code, we have a GitHub action that runs and it might build a Docker container, publish it, make a, some AWS, SDK CLI can I get more TLAs in there? calls to, to automate the deploy. so I mean, it's an interesting question that you ask, because on one hand, I would say for certain types of apps that we have, I could easily deploy 10 or 15 times in a day.

[00:55:33] **Adam:** but others, like, we tend to batch them up, just because it's a pain in the butt to deploy and you have to go remote desktop into C two and deal with that whole thing. And we've got like 15 of those servers that we have to go do that anytime we wanna do a deploy. Cause we have to deploy to 15 different places.

[00:55:47] **Adam:** Yeah. Which is so it, it becomes obvious that people are going to start batching that up. And, like we have buy-in from the entire rest of the technical team here to do the things that are necessary to get to a point where we can automate that all away. And, everybody that was holding out thinking like automation is not, worth the investment has now come around and said, okay, yeah, it's worth the, it's worth the investment.

[00:56:10] **Adam:** So, we'll get there. but yeah, those, the other, those EC two boxes are lucky to see three deploys in a week,

[00:56:17] **Carol:** I mean, but that's okay though, cuz you're not probably doing a ton of code on them, so it's not like you're holding a bunch of work.

[00:56:24] **Adam:** right? Yeah. It tends to be like, if there's a big project that finishes up, then yeah. we'll do a deploy, sort of on demand as needed. But yeah, if there's just little like piddly bug fixes, typos or whatever, then they just sit there and wait until some, somebody has a good reason to do a deploy.

[00:56:39] **Carol:** Yeah, we were doing just as things got done, just constantly deploying, but then we always had to have an QA person set in to then check logs to make sure there's no errors in production for like that manual. Let's just have eyes on it to make everyone happy.

[00:56:55] **Carol:** And then if we needed a DBA to run any database scripts and production, like it took someone else like getting a schedule and everything. So we've switched it to where we, we deploy twice a day. So we'll just take the work from, that was approved from yesterday or the morning. And they'll get deployed the morning.

[00:57:10] **Carol:** What got approved throughout the day, we'll get deployed in the afternoon and it just continues in the cycle, but we don't deploy on Fridays unless it's critical. So yeah, it, that works good for us because then we only have to have those small blocks when we know a DBA is guaranteed for those two blocks and S Q a knows.

[00:57:27] **Carol:** Someone needs to be around to check error logs during these two windows, rather than just. 15 minutes. Can everyone jump on real quick? And let's deploy this and everybody check and make sure your stuff's good and let's call it done. So that's working well for us.

[00:57:40] **Ben:** one other thing that grinds my gears based on what you were just saying, I can. I get frustrated that the amount of times that I've had to deal with this, which is non-zero where people deploy something to code, sorry, people deploy something to production, and then we start getting tickets about it.

[00:57:58] **Ben:** And then you open the ticket and you go to check the thing in production, and it's very clearly broken. And you realize that the person who deployed it did not even bother to check it once they deployed it. I'm like, are you kidding

[00:58:10] **Ben:** me?

[00:58:11] **Carol:** a quick check. Quick. Check's all it takes.

[00:58:13] **Ben:** part of your process?

[00:58:14] **Carol:** Yeah. It's part of our process. Oh yeah.

[00:58:18] **Ben:** And I

[00:58:18] **Ben:** don't

[00:58:18] **Ben:** even mean like a QA team, like just the developer who builds it.

[00:58:22] **Ben:** Once it goes to production, they should do something to validate that it actually worked.

[00:58:28] **Carol:** Oh, yeah.I jump in the error logs immediately and I look to make sure that there's no new errors. And then about an hour later, I'll check again and be like, okay, still no errors from anything I've touched. So. Okay. Good

[00:58:39] **Ben:** Yeah, Yeah, absolutely.

## [00:58:41] Patreon

[00:58:41] **Adam:** Cool. Well then this episode of Working Code was brought to you by stupid prizes, which you can get by playing stupid games and listeners like you. If you're enjoying the show, you should consider supporting us on Patreon. It's the best way to help keep the show running your donations, cover the costs of recording and editing.

[00:58:58] **Adam:** And, we couldn't do this every week without you guys. So we really appreciate you special. Thanks, of course, to our top patrons, Monte Gavin and Sean, we have a new top patron this week. if you'd like to help us out, you can go to patreon.com/WorkingCodePod. As I mentioned, we do have, Sean now in our top spot.

[00:59:13] **Adam:** So Sean, sent us Patreon money and he wants us to spend it specifically on GitHub co-pilot for the four of us. So, uh,

[00:59:22] **Carol:** already signed up. Thank you.

[00:59:24] **Adam:** Yeah. So you're our, you are our co-pilot Sean. and, also new this week, Jason Hendrickson, who was our guest last week. has, joined our Discord. He's a patron.

[00:59:33] **Adam:** so happy to have you a board, all patrons get early access to new episodes and the after show.

## [00:59:36] Thanks For Listening!

[00:59:36] **Adam:** and I guess let's see your homework this week. Let's do discord. It feels like we've been, it's been a while since we've talked about this. So if you would like to join our community, get, come talk to other people.

[00:59:46] **Adam:** We do. Sometimes there will be like, let's, get together and hang out in the afternoon and have a drink on video chat and just, kind of like happy hour on our Discord or, we have, triumphs and fails in there. We're learning from each other. We're just having a good time. it's a great place to hang out, workingcode.dev/disor.

[01:00:03] **Adam:** we can always use your topics and questions. so if you've got something for that, then you can send it to us @WorkingCodePod on Twitter or Instagram, you can go to, you can email it to WorkingCodePod@gmail.com, and we would especially appreciate if you wanna record a voice memo, you can send that as well to WorkingCodePod@gmail.com.

[01:00:21] **Adam:** That's gonna do it for us this week. We'll catch you next week. And until then,

[01:00:24] **Carol:** Your heart matters.
