---
title: "231: Good Friction"
description: "It's all too common in business to hear about reducing and eliminating friction, but some forms of friction can be positive in ways we take for granted."
date: 2025-09-18
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/231-good-friction/id1544142288?i=1000727328238"></iframe>

In this week's episode the whole crew is back, and Ben brings our attention to "good" friction. It's all too common in business to hear about reducing and eliminating friction, but some forms of friction can be positive in ways we take for granted.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/231-good-friction.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Ben:** There are all of these apparently, like micro payment plans, systems that have come online

[00:00:05] **Ben:** where it's like you go to buy your burrito chipotle.com and you can pay over the course of four, you know, like you can buy your $12 burrito over the course of three payments of $4 they were saying essentially that the friction of taking on debt has essentially completely disappeared.

[00:00:22] **Adam:** Can you imagine going bankrupt because of your burrito habit?

[00:00:25] **Tim:** Right.

## [00:00:47] Intro

[00:00:47] **Adam:** Okay, here we go. It's show number 231. And on today's show we're gonna talk about good friction. No, not that kind. Get your mind outta the gutter. The other kind.

[00:00:56] **Tim:** Okay.

[00:00:57] **Adam:** Hey, Tim's back.

[00:00:58] **Tim:** Yay.

[00:00:59] **Carol:** Hey Tim.

[00:01:00] **Adam:** Welcome back. Timmy.

## [00:01:00] Carol's Triumph: Cost Savings

[00:01:02] **Adam:** Timmy.but first as usual, we'll start with our triumphs and fails.

[00:01:04] **Adam:** And Carol, we're coming to you first. What do you got going on?

[00:01:07] **Carol:** All right, so, you know, I work for this place called the government and I just want you guys to know that I have been trying very, very hard to make sure that your taxpayer dollars and mine are being used wisely.

[00:01:21] **Ben:** Thank you.

[00:01:22] **Carol:** yeah, yeah, like putting a lot of effort into making sure what I'm doing, like makes sense from a dollar standpoint, trying to get rid of some big costly tools, going to some open source stuff, they'll do it.

[00:01:33] **Carol:** But I recently found that we had deployed our staging environment to Azure, and anticipation of going to the cloud when everything changed in January, moved to the cloud, got halted, and we decided to come back on-prem and use our, our resources there. I found a whole bunch of resources that had to be deleted and needed to be shut down. And I got rid of so many that I got an award for it and got a cash prize, so

[00:02:03] **Ben:** wow. That's awesome.

[00:02:04] **Carol:** Yeah.

[00:02:05] **Adam:** That's a lot of resources that have been up since January doing nothing.

[00:02:09] **Carol:** doing nothing costing several hundred dollars every day, so it's not crazy expensive, but it was several hundred dollars every single day

[00:02:16] **Adam:** Wow.

[00:02:17] **Ben:** cow.

[00:02:17] **Carol:** we never were gonna promote. Right. And these things become visible when you're in a smaller group, but once we lost our staff and we lost the people monitoring this, it just slipped through the cracks. So got it all removed. And then I found some other places where we can reduce some costs as well. So super happy to be able to kinda look at everything at a financial, like look at it through financial eyes and think the, this is what my money is paying for because it is my taxpayer money pays for this too.

[00:02:45] **Carol:** You know? So trying to be a good servant to the people.

[00:02:48] **Ben:** Very cool.

[00:02:50] **Tim:** Thank you for your service.

[00:02:52] **Adam:** Indeed.

[00:02:54] **Carol:** Doing my best, you guys? Mm-hmm.

[00:02:55] **Ben:** I remember at, envision after we had a bunch of our reductions in force or riffs, we had, started to do a, a. cutting initiative and the amount of VPSs and various servers that had been left running by people who no longer even worked at the companyuh, a little staggering at one point.

[00:03:16] **Carol:** It's crazy. it's easy. It's so easy for the slice of the cracks when the person monitoring it or the person who knew about it isn't there anymore.

[00:03:24] **Ben:** Yeah.

[00:03:25] **Carol:** no one picked up that job. Well anyways, all right, that's me.

## [00:03:29] Tim's COVID Struggles and Upcoming Plans

[00:03:29] **Carol:** What about you, Tim? What do you got going on?

[00:03:31] **Tim:** I'm gonna go with the, I guess a failure. So, you know, I haven't been on the show the past two weeks 'cause I've had COVID still not 100%, but I'm feeling better to talk for a little bit, but managed to work my work the entire time I was sick, so, yay.

[00:03:47] **Carol:** What?

[00:03:49] **Tim:** Just really didn't have much choice, just so much going on.

[00:03:51] **Tim:** We had a, like a strategy session we had to do, so it was so pathetic. I'm sitting there, at this big giant table and I'm like off in the corner in a leather chair with my, with a mask on and you know, just staying away from everyone with big box of Kleenexes and everything. And

[00:04:07] **Adam:** Oh, you were there physically.

[00:04:08] **Tim:** I was there physically, yeah,

[00:04:10] **Adam:** Wow.

[00:04:11] **Tim:** So it was rough. Fortunately. But fortunately it's like my part, they, they just kind of said, well, you know, I commented when I could, but it's like I didn't talk a whole lot, but then I had like a hour presentation that I had to do, which I managed to make my way through. But yeah, I was, it was feeling rough, man. I can, I can't tell you how many, teams meetings I've ac that had recurring that I just thought I was canceling and I just deleted.

[00:04:35] **Adam:** Uh oh.

[00:04:35] **Carol:** no.

[00:04:36] **Tim:** I'm like, don't, this week I'm like, don't we have a meeting today? They're like, you deleted it. They're like, we thought you canceled it. I'm like, no, I just meant to delete the one. So.

[00:04:44] **Carol:** occurrence versus series.

[00:04:46] **Tim:** Yeah,

[00:04:47] **Carol:** Big difference.

[00:04:48] **Tim:** So, but I'm feeling better. I'm working my way back. I'll be fully better this weekend. 'cause I'm flying out to Vegas this Sunday

[00:04:56] **Ben:** Oh, you're coming out to Summit? That's right.

[00:04:58] **Tim:** I'm gonna be on the keynote. Yep.

[00:05:00] **Carol:** Oh, nice.

[00:05:01] **Tim:** So,

[00:05:02] **Carol:** You'll see Ben.

[00:05:04] **Ben:** From across the room.

[00:05:06] **Adam:** Nice little super spreader event. Yeah,

[00:05:08] **Ben:** Yeah,

[00:05:08] **Tim:** I'll, I'll be, I'm, I'm fine. I'm not positive now.

[00:05:10] **Tim:** It's just, I've still got some lingering congestion, but yeah. I'll be the extrovert to like, you know, get Ben to actually interact with people.

[00:05:17] **Ben:** I'll do some, I'll do a a, a degree of peopling.

[00:05:21] **Tim:** Yeah. It's just not too late. Yeah. I

[00:05:23] **Ben:** Yeah. Yeah. Until, until the, late hours of 9:00 PM

[00:05:27] **Tim:** Yeah,

[00:05:27] **Adam:** that's later than I thought you were gonna say.

[00:05:29] **Ben:** to be fair, east Coast time is like 11.

[00:05:33] **Carol:** I was gonna ask, are you doing like nine on the East Coast? Is that your limit?

[00:05:37] **Ben:** See,

[00:05:38] **Carol:** Yeah.

[00:05:39] **Ben:** we'll play it by ear.

[00:05:41] **Tim:** So anyway, that's me. How about you, Adam?

[00:05:43] **Adam:** I

## [00:05:43] Adam's Fail: Back Pain

[00:05:47] **Adam:** guess I'm gonna call this a, a fail with a nice little triumphant in its back pocket. I feel like I pulled a muscle in my back and I've been working out really hard lately. and it's either like my trap or my lat on my left side just feels like pain, right? Like, it's not a cramp, it's not a knot, it's just pain.

[00:06:01] **Adam:** So I'm calling that a pulled muscle, I guess. and I feel like poo, I've been, laying on a heating pad for like 24 hours straight, basically at this point. if not longer. And, that helps, you know, a little, ibuprofen helps, but. Just not feeling good. Not really. And it's, I can't even really a hundred percent focus because of it.

[00:06:20] **Adam:** That's how much it sucks.

[00:06:22] **Ben:** Cool.

[00:06:22] **Adam:** However, like I said, I do have a little bit of a triumph in the back pocket here. tomorrow is my 20 year wedding anniversary as we're recording this. and as part of the festivities from that, we had already scheduled, like couples massage. So I'm kind of hoping that, that,

[00:06:37] **Carol:** need it?

[00:06:38] **Adam:** yeah, I'm kind of hoping that that helps clear that up.

[00:06:41] **Adam:** So looking forward to that. And as soon as we're done recording here, I'm just gonna go straight to bed.

[00:06:47] **Ben:** I'll tell you, there's nothing that makes me as angry about fitness influencers as being in pain and watching them post videos like, do this one stretch and watch all of your bodily paints

[00:07:02] **Adam:** Yeah,

[00:07:02] **Ben:** away. And I'm like, how about you go f yourself?

[00:07:05] **Adam:** yeah.

[00:07:05] **Ben:** that's not how the body works.

[00:07:07] **Adam:** You're 22. You don't know about and pull up your pants.

[00:07:11] **Ben:** I'm so happy that you don't have the weight of the world on your shoulders.

[00:07:15] **Carol:** Or I love it, like I'll go try doing it, and then I'll like yell at Steve. I'm like, I don't know why, but I can't fill my toes now.

[00:07:22] **Ben:** Yeah, totally.

[00:07:24] **Carol:** was wrong.

[00:07:26] **Ben:** I, every time I go to physical therapy for various things that they inevitably recommend that I try this thing called nerve flossing, which

[00:07:35] **Adam:** Oh, that doesn't sound painful at all.

[00:07:36] **Ben:** it, it's, so it's, it's like to try to increase the degrees of motion around some of the big nerves. So you do things like put your arm out and then you sort of f flap your, your things or

[00:07:52] **Ben:** You bend it, you bend at the wrist, like a little bit of a he Hitler, and a little bit of like, or it's like, I, I tend to have to do it. Um,or, or like you'll, you'll, I mean, people listening can't see this, but it's like you would flex your arm and move your head to the side and then go back and it's basically like you're just trying to move the lengths of the nerves around. don't know. I just have no patience for any of this stuff.

[00:08:16] **Ben:** If it doesn't work in the first two minutes, I'm

[00:08:19] **Adam:** Yeah.

[00:08:19] **Ben:** dedicate 15 minutes a day for the rest of my life to this. Like, I need results. I'm a results driven person.

[00:08:25] **Adam:** did I talk about when I had some vertigo going on a couple of weeks ago?

[00:08:29] **Ben:** No, I

[00:08:30] **Adam:** that on podcast. I, it just was like a little minor bit of vertigo here and there, and my doctor told me about this thing called the Epley Maneuver, which if, if you have been in this position, you've probably heard of it.

[00:08:41] **Adam:** Basically. It's like, you know how you have like tubes of water or tubes of fluid in your ears

[00:08:45] **Ben:** Yeah.

[00:08:46] **Adam:** like, that's how you can kind of get motion sickness. Like that's a, it's a sense you have there, balance or whatever that is. And, there's like little crystals inside those tubes, and it's, if they break off, then they can be free floating.

[00:08:59] **Adam:** And that can cause like motion in the, in the fluid there when you're not actually moving. And so that causes your eyes to just kind of like, go a little crazy, which is what they thought that my, vertigo was caused by. And so she had me doing this maneuver, which is just like, it's a series of like, you know, you lay down this way and you turn your head that way and you wait 30 seconds and then you turn your head this way and you wait 30 seconds.

[00:09:21] **Adam:** You, you do this and you wait 30 seconds and it's like, it adds up to like two and a half or three minutes of, you know, do this thing and then wait 30 seconds and, and then you do it like the opposite side. Like what? 'cause they weren't sure which side of which ear might be affected for me. So it's like, do it for the right ear and then do it for the left ear.

[00:09:39] **Adam:** I'm supposed to do this like three times a day for a couple of weeks. And I never felt immediate relief, but like over the long term, I do feel like it did help. Like I haven't, I haven't been doing it in a while because I. I haven't had the vertigo in a while, so that's nice. But it was, it's one of the, I'm totally on board with you, Ben.

[00:09:54] **Adam:** Like, if I don't get that immediate, like, oh, hey, that helped then it's so hard to motivate myself to

[00:10:00] **Ben:** hard.

[00:10:01] **Adam:** through.

[00:10:01] **Ben:** this, this is why I'm, I'm just not a stretcher either. There are people who swear by stretching and I, and I just feel like it's never done anything for me, so I don't stick with it.

[00:10:13] **Adam:** I stretch while I'm working out. Like, I not, not like stop to do stretches, but like, you know, when I'm doing my barbell R dls, it's like put a stand on a plate and get as deep as I can. Right. Stretch it out in the lift.

[00:10:23] **Ben:** Yeah, yeah. I'm definitely more enjoying that kind of stuff, or it feels like I'm doing functional, like I'm, I'm doing the body the way it's supposed to be done, as

[00:10:32] **Adam:** Yeah.

[00:10:32] **Ben:** randomly trying to move it ways.

[00:10:36] **Carol:** While we're talking about stretching, then don't play golf. Because the one thing I've realized with playing golf is I have to stretch a few times before, or my first hit, my ball goes all over the place and I feel like I throw my shoulder out.

[00:10:47] **Adam:** Hmm.

[00:10:48] **Carol:** So you definitely need to do a tiny bit of stretching before you start hitting balls.

[00:10:52] **Ben:** It does seem like a very wild movement.

[00:10:54] **Carol:** Yeah, it

[00:10:55] **Ben:** I, I did go to a driving.

[00:10:57] **Carol:** it.

[00:10:58] **Ben:** did go to a driving range one time with my brother years ago, and I, I, you know, you go out and you have a bucket of, it was like a hundred balls or something and by the time I was done, like my whole body hurt.

[00:11:09] **Carol:** Oh, yeah.

[00:11:10] **Adam:** Yeah, it's a good way to pass an evening. Alright, anyway, so that's, gonna be it for me. What about you, Ben? What do you got going on?

## [00:11:15] Ben's Triumph: Social Media Detox

[00:11:15] **Ben:** I'm gonna go with a little bit of a, maybe a controversial, depending on which circles you run in triumph, which is that, have not used Twitter in many months, but I just had my account, however, I just took steps over the weekend to deactivate it. So I think that means that in 30 days it'll be deleted if I don't log back in.

[00:11:34] **Carol:** Good for you.

[00:11:34] **Ben:** Um,I've also, I, my Facebook profile has been public for a really long time and, I went through and I just started making all that stuff private and essentially I'm just trying to decrease my social exposure. 'cause there's just a lot of. Lot of anger in the world and I'm trying to not have as much of that in my life.

[00:11:55] **Ben:** and mostly I also just want less people in my life. is something that I wanna start doing on Facebook as well. Facebook, because I'm not a people person. I treated it just like a, a grab bag of, of connections, like almost like a LinkedIn. so over the years, anyone who has sent me a friend request on Facebook, I would just

[00:12:15] **Adam:** Mm-hmm.

[00:12:40] **Ben:** Oh, you weren't supposed to get that. I'm, I'm struggling with all of the notifications.so yeah, so just trying to, to limit that. I also, this is not quite related, but I did, I, I also downgraded my open ai. I had the $20 a month plan and I downgraded to free. and this is more of just like a personal issue, so there's a lot of AI maximalist out there, and I have stumbled into a world of AI, minimalists, people who talk about all the financial aspects of the AI industry and how they just spend a tremendous amount of money and, and even when people say, oh, anthropic or Open ai, they're the fastest growing companies in history, but they're still losing billions of dollars.

[00:13:25] **Ben:** I'm like, I don't, I don't know. I just don't know if I want to help fund that. I'll still use it at the free tier, but I don't need to generate images and have audible audio conversations. So. Just trying to vote a little bit with my dollars.

[00:13:38] **Adam:** Good for you, man. I'll, I'll, save you a space at my local Amish,what do you call it? Market.

[00:13:44] **Ben:** and a butter churn and I'm a happy man.

[00:13:46] **Adam:** Yeah.

[00:13:48] **Tim:** Brother Ben.

[00:13:51] **Ben:** Peace be upon you.

[00:13:53] **Tim:** Mm-hmm.

[00:13:56] **Adam:** Well, it's good that you're adding a little bit of friction to your life there for the doom scrolling.

[00:14:00] **Ben:** Act a hundred percent. A

## [00:14:02] The Concept of Good Friction

[00:14:07] **Adam:** nd that, and that dovetails very nicely with the topic of the show. Good friction. Imagine that.

[00:14:07] **Tim:** imagine that, and definitely my desire to reduce my social media footprint is in an, an attempt to add that, that good friction. So I've been, I have so many thoughts that go through my head all the time as I'm, I'm sure people see with all of my tangents and my just random little notes that I leave around places. that you

[00:14:27] **Ben:** and.

[00:14:27] **Tim:** philosophy major.

[00:14:29] **Ben:** Well, so I, I have all these things and I don't know how to, I don't know what to do with them and I don't know how to the dots all the time. Like I have a lot of feelings, but I don't necessarily know how to approach them academically or intellectually. And I try to just sometimes find patterns in the feelings that I'm having to see if there's some there, there. I've been thinking about this concept of friction, lot in the context of ai, a lot in the context of social media. a lot in the context of just everyday stuff. You know, we've talked about smart homes as an example, and how, as much as I love my, digital thermostat because I can turn the temperature down without getting out of the bed, there's a lot of smart home stuff that I don't subscribe to. And I, I think it's maybe something worth discussing. So mechanically in the physical world, friction is basically how we survive. You know, I can pick up this can of seltzer because there's friction between my fingers and the can. If there was no friction, I would just slip off into space, right? No, friction is basically like in, in gravity when they're spinning around in, in open space and you can't stop 'cause there's noso obviously as a people friction is, is super important. But, I think it, the more I think about it, the more it seems to apply to everything. And I think that friction ends up allowing systems to work. And if we could talk about AI for a second, 'cause this is sort of where a lot of these feelings came from.

[00:16:07] **Adam:** Every week.

[00:16:10] **Ben:** Well, it's so, it's so it, you know, it's everywhere. I was thinking about,

[00:16:15] **Tim:** who can't stop talking about his ex, can't

[00:16:17] **Adam:** Yeah.

[00:16:17] **Tim:** but can't stop talking about her.

[00:16:20] **Ben:** but, it's like, okay, we all right. Let's start with a non-AI topic for a second. It's like, I expose public endpoints on a website like my blog or an API, if someone wanted to attack it, could open a VPS and they could send a certain amount of traffic and maybe it would be, but it wouldn't necessarily take me down. And over the years, the amount of friction that it takes to spin up an entire botnet of malicious actors has gone down and down and down. the ability to launch massively scaled denial of service attacks has. The cost of entry there is much lower. The, the amount of friction is much lower. And that starts to call into question, well, how do we easily keep these systems online?

[00:17:07] **Ben:** And we have to start to come up with new ways to think about stuff. with the ai, I was thinking a lot about pull requests and if I'm writing code manually and I'm sending a PR, maybe two, maybe three prs to someone a day, and maybe those prs are a couple of hundred lines of code, you know, that system works because there's a certain amount of natural friction.

[00:17:29] **Ben:** I have to write the code, I have to do a lot of deep thinking, and I have to put the PR together. I have to send it to you and you have to to review it. And there's a certain throttling that happens with the amount of friction, and that's what allows the team to work effectively. But if you start to reduce the amount of friction that it takes to write code to create prs, suddenly I can send. You know, you 10 prs a day that each have tens of thousands of lines of codes in them.

[00:17:59] **Adam:** Mm-hmm.

[00:17:59] **Ben:** And fundamentally the gesture hasn't changed, but because the volume has changed so much with the reduced friction, the system becomes untenable. Or another example is, what's that? The hack tober, when you're supposed to go in and do little prs for open source things and you win a t-shirt, right?

[00:18:18] **Ben:** digital Ocean.

[00:18:19] **Ben:** Digital lotion. Thank you. it's like when you had to go in and do that manually and, and you know, with good intent, it seemed to work and then suddenly. People were submitting all kinds of prs. And then AI is getting used to generate slop prs.

[00:18:33] **Ben:** And now suddenly the thing that was fun for everybody is now ruined for everybody because the lowering of friction that it takes to interact with these systems and to generate slop code, and I guess in, in general, I'm just now looking for ways to keep that good friction in my life. Is, is any of this resonating with anybody or is this, am I, am I crazy?

[00:18:55] **Tim:** This makes absolutely zero sense. I'll just go, I'm just gonna say it out loud. It makes no sense.

## [00:19:00] Debating Good vs. Bad Friction

[00:19:00] **Tim:** I mean, the, the whole purpose for looking for efficiencies is to take friction out. You're talking about, oh, we need this friction so things can operate, but that's the opposite of what, what. Companies try to do, they're like, where's the friction in this process?

[00:19:13] **Tim:** What is causing, you know, people to not be able to complete their job or get frustrated with their job? It's 'cause there's friction at these points where you, you're having to log your time here, but you're having to log your time there and then you gotta log your time that you spent logging your time.

[00:19:29] **Tim:** That's just friction, right? You, so

[00:19:30] **Carol:** That's bad friction.

[00:19:31] **Tim:** that's bad friction.

[00:19:32] **Carol:** bad friction.

[00:19:32] **Tim:** so, so I guess, I guess what we need to narrow down is, is there good friction? Is there such a thing? 'cause your, your statement is that there is,

[00:19:41] **Ben:** Right. Not all friction is good, but I th I'm saying there is good friction and there's bad friction. And I think

[00:19:47] **Tim:** so how do we define good friction?

[00:19:49] **Ben:** and, and I think again, the, this notion of friction being a sort of built in governor the throughput of life. I think that there's an important thing there. You know, like back when phones were attached to the wall and I got a call and I had to get up outta my bed and I had to walk into another room and I had to pick up the phone.

[00:20:13] **Ben:** That was more friction. But when you compare it to something like, now I can just look at my phone in bed and I'm half paying attention to the TV and I'm half paying attention to the phone. I mean, not, not, you know, like,

[00:20:25] **Adam:** It was so annoying to have to get up and walk across the room to doom. Scroll on Twitter.

[00:20:32] **Carol:** Or play snake?

[00:20:33] **Tim:** Mm-hmm.

[00:20:35] **Ben:** okay, so, so maybe this just isn't resonating. I mean, I, to me.

[00:20:39] **Adam:** I, I do think that there's such a thing as good friction.

[00:20:41] **Carol:** I do too. I agree. Like I feel like there is good friction and when you have good friction in society of a healthy team, so for me, like the thing that stands out is we will spend so much time what feels like arguing about how to architect something. Like where do we wanna layer, layer on off?

[00:21:01] **Carol:** Like where do we wanna like name these variables of our case versus when they should be a lowercase variable. And at the end of the, all that arguing, I would say 90% of the time we come out with a more defined, a better defined system. It's more maintainable, people understand what's going on, but it does take some of that argument upfront to get your viewpoint or to get your view across.

[00:21:26] **Ben:** Mm-hmm.

[00:21:28] **Carol:** And I think that's healthy friction.

[00:21:30] **Ben:** Yeah, that's definitely healthy. Kind of interpersonal friction for sure.

[00:21:35] **Tim:** I, I, I, so I was being a little bit cheeky when I was saying it. Don't, so, I mean, code reviews is actually, I think an example of purpose-built friction, right? So if, if everyone just gets a code review and they just, they look at it for 10 seconds, go, I'm sure they knew what they were doing. You click it and approve it, you're missing an opportunity for, for friction there.

[00:21:55] **Tim:** Good friction. 'cause the friction is, you know, you say, well, why, why not use composition instead of inheritance? Right? It so you, you being the developer, it might feel annoying at the moment. It's like, dude, it works. I made it. I know it works. You know, I put some thought into it, but someone challenges you. you have to think about it. And perhaps a better understanding of the process or maybe coming up with a different way that you didn't think about. That's, I think that's an example of good friction.

[00:22:21] **Ben:** Yes, absolutely. And, oh God, sorry.

[00:22:27] **Tim:** in other places the estimation battles, right? If you do, was that? Poker

[00:22:30] **Ben:** The planning

[00:22:31] **Adam:** Oh, uh,

[00:22:32] **Tim:** Poker,

[00:22:32] **Adam:** yeah.

[00:22:33] **Tim:** yeah. So I mean, that's sort of a system built for friction. Everybody's like, well this is, you know, this is 10 and every, everybody's like, no, there's no way in heck that's 10. Come on.

[00:22:43] **Tim:** What, what? Why do you think that's 10? It's definitely a five and there's some friction and, but you, you talk it out

[00:22:48] **Adam:** Mm-hmm.

[00:22:49] **Tim:** good things come out of it.

[00:22:51] **Carol:** It's not a 10 because it can never be a 10. That's not a valid number, but go ahead.

[00:22:55] **Adam:** It depends on your system.

[00:22:56] **Tim:** we don't do planning poker, so we,

[00:22:58] **Adam:** Yeah.

[00:22:59] **Tim:** t-shirt sizes, so.

[00:23:00] **Adam:** You could do shirt sizes, you can do Fibonacci, you could do a lot of different things. Yeah.

[00:23:05] **Ben:** oh my goodness. When we were in vision, the amount of time that we argued between the half point and the single point, which was like less than a day and a day, and I swear we'd spend an hour arguing about this.

[00:23:17] **Adam:** like nine people. Right?

[00:23:18] **Ben:** Yeah. And I'm always like, what's the point if if you finish early, then you just move on to the next task?

[00:23:23] **Adam:** Right. And also you just said you spent an hour. Well, but, but then you just say you spent an hour of approximately nine or 10 people's time. Right. So that's 10 hours of work time that you're paying people for when it doesn't matter. The, the difference in time spent on the on the task is nothing compared to the time spent arguing about the time spent on the task.

[00:23:44] **Carol:** Side tangent. At another job I worked at, I had this amazing engineer who we would start having these conversations and he would just check out of the conversation and you would know he was immediately working it. So by the time everyone was done arguing about it, he would go, I've already made the change to PRS out there.

[00:24:02] **Carol:** Can we move to the next story?

[00:24:06] **Adam:** That's great.

[00:24:08] **Ben:** That's awesome.

[00:24:08] **Adam:** Is that person looking for a job?

[00:24:11] **Carol:** I don't think so.

## [00:24:13] How AI Changes Friction

[00:24:13] **Ben:** So the other thing, not to harp on the AI stuff too, again, but there's so much talk about summarizing things. Like, oh, just take this book and summarize it, or just take this email and summarize, or take these meeting recording and summarize the meeting notes. again, it's one of these things where I feel like part of the value add of those things is the friction of having to experience them and to read them. I was listening to a podcast the other day and they were talking about change in educational structures in the age of ai. remember if I talked about this before, but one of the guys being interviewed was like, oh, kids just don't read books anymore, so we have to change the educational system allow them to not have to read books.

[00:25:00] **Ben:** And I'm like, well that's definitely not the right solution to that. Like you should have to know how to read books and you should have to be able to concentrate to read a book or. This one is maybe more unpopular, but you'll see studies about, oh, kids growing up actually function much better if they can sleep till 9:00 AM so we should start pushing back the hours of school.

[00:25:21] **Ben:** And I would think, yeah, but part of going to school is learning how to in the world and the fact that you have to do things that you don't like and you have to function while doing those things as, again, like you, it's friction that helps become a better person. I think there are just of these frictions in life that help you do things better and help systems work predictably and in a better way.

[00:25:46] **Ben:** And I'm just, I'm noticing that we, we becoming more and more obsessed with removing all frictions. And I, I don, I don't know, okay, so like, here's a silly one.

[00:25:56] **Tim:** we should remove bad friction. Right.

[00:25:58] **Ben:** Yes. Bad friction. Absolutely. Here, here's like a silly intro.

[00:26:02] **Tim:** I wanna take issue with your, study about kids, you know, needing sleep. They do. They honestly, a hundred percent do need to sleep till nine 'cause their, their brains are developing and that's not a problem they're gonna have when they're grown in the workforce.

[00:26:14] **Tim:** So.

[00:26:15] **Ben:** I hear you. But it, it, yeah. Okay. that's why I said that one's

[00:26:18] **Adam:** But I,

[00:26:19] **Ben:** but like,

[00:26:20] **Adam:** to be fair, I also wanna sleep until nine.

[00:26:24] **Ben:** Like, I think about, I dunno if this bothers anyone else, but this always bothers me so much. I'll be doing something and I'll get a call the person who calls me is like, they're in a car, or they're walking from one place to another and they're like, oh yeah, I'd just love to kill two birds with one stone.

[00:26:42] **Ben:** You know, like, I love to do my walk and make my calls, and I always think to myself, why are you making that my problem? why take it up my day to try and maximize your stuff? And it's, again, it's like one of these things, it's like, it, it was too easy for them to give me a call and disrupt my day. That's maybe more of an introvert's grievance, but, know, I'm trying to seed the, the, the whole here with information. I just feel like I'm not connecting on this at all with you people here. Here's, okay, so years ago, years ago, I used to watch, house md, as a medical drama. I'm sure Carol's never heard of it, but I'm, I'm sure other people have.

[00:27:21] **Adam:** Yes, I know. I, I have seen every episode go on.

[00:27:24] **Ben:** So there was an episode in House md I'm pretty sure it was from house

[00:27:28] **Adam:** Was it lupus?

[00:27:29] **Tim:** It's

[00:27:30] **Ben:** was, it was CIDI think it's like always CID where these two sisters, who I think had, had, had a rift between them, they had to come back 'cause one was hospitalized and the, the kind of twist to the storyline is that one of the sisters had, I dunno if it was considered photographic memory, but it was, it was like memory where they, they never forgot anything. And like every memory of theirs was fresh. And they had had some huge blow up years ago. And one sister was like, just, why won't you forgive me? And the, and the sister with the great memory is like, I really would love to forgive you. But every single day I wake up and it's like, it happened yesterday for me. She's like, you have the benefit of not really remembering it, and you start to lose details over time. And I don't, I remember everything you said to me that was so hurtful and I'm reliving it every day. So you could look at even something like that, the, the, the friction of having our memories fade over time and the friction of, of being exposed to too much information that our brain can really store.

[00:28:31] **Ben:** Like that's a good thing. And imagine if you didn't have that friction anymore and it was just this fire hose of information that you could never forget.

## [00:28:40] Frictionless Social Media

[00:28:40] **Adam:** Yeah, I mean, this is very, relevant right now with, I mean, so we're recording this on September 16th. It's been,several days now, but, you know, the, the killing of Charlie Kirk and, you know, just, it's been an absolute nightmare on every website, every news network. It's just all, anything, all anybody talks about, which, you know, maybe we all owe Charlie at least a moment of silence because he finally got them to shut up about ai.

[00:29:04] **Adam:** But, like, I don't even wanna make a comment on it, you know, everything's already been said. I don't have an original opinion on anything to add, but

[00:29:16] **Ben:** Well here's, here's if

[00:29:17] **Adam:** the, well, the, the, just on the, on the subject of friction, right? Like, I think. We've, we've been noticing, we as a society have been noticing the, the continued and deepening polarization of our society.

[00:29:33] **Adam:** And I think that that is largely due to the nearly eliminated friction of sharing information with each other, right. The Twitters and Facebooks and all that. And if we had to go back to, you know, if, if for some reason I waved my wa magic wand and we go back to society of what's like newspapers and the evening news is all you get, then you're gonna get a more considered take.

[00:29:59] **Adam:** It's gonna have gone through an editorial process, all that, and not saying it would be a perfect solution, a better world, but parts of it would be better.

[00:30:09] **Ben:** Well, here's a, I've I've, 'cause I've been thinking, obviously, I think we've all been thinking a lot about social media in the last couple of days because of the massive amount of. Stuff that's happened. And I've, I was listening to a news piece today and they were talking about it being like a population level traumatic event because everyone was seeing live.

[00:30:28] **Ben:** I mean, I didn't, thankfully, I have not seen videos of anything because I'm not that much on social media or watching the news, but apparently people were just scrolling through Instagram and suddenly they're seeing these super graphic images that they did not expect to see. And they're talking about just the tr, the traumatic, the PTSD of it all. And I was thinking about what if, know, they talk about nudging people in the right direction, whereas, you know, instead of having to opt in to being an organ donor, when you apply for a driver's license, what if by default you're opted in and you have to opt out? they do these studies, it turns out the amount of people who become organ donors goes way higher.

[00:31:08] **Adam:** Yeah.

[00:31:09] **Ben:** they're nudged in the right direction. Like the good friction's been put into place and the, and the bad friction's been taken away.and I thought about is there,

[00:31:16] **Adam:** Ooh.

[00:31:16] **Ben:** what if all we did on a social media platform was essentially remove the retweet or you know

[00:31:23] **Adam:** Yeah, I mean that's a, that's a thing.

[00:31:25] **Carol:** Yeah.

[00:31:25] **Adam:** it mastodon? They don't, for a long time they didn't have retweets or rets or whatever you wanna call it. and that was an intentional choice as sort of like a social experiment.

[00:31:35] **Ben:** yeah. I think because at the end of the day, I do think a tremendous amount of people are lazy. I mean, I think that's just human nature and the amount of friction, the delta between click to retweet something and let me retype something or type something from my perspective seems like, oh, that's 140 characters.

[00:31:55] **Ben:** But I think the gulf of effort to do that is actually extremely large.

[00:32:00] **Tim:** Yeah.

[00:32:00] **Ben:** And I think adding that good friction might actually be a really good thing.

[00:32:05] **Tim:** Yeah. That, that, I guess I would agree with you guys on. 'cause like, I mean, back in Mark Twain's day, he had a very famous saying, he said, a lie can travel around the world and back again while the truth is lacing, its up, its boots.

[00:32:16] **Ben:** Yeah.

[00:32:17] **Tim:** Right? And so there it's like the things you guys were referring to that's happened recently this week.

[00:32:24] **Tim:** It's like before any facts got out, there's already tons of so-called news positions on, on this story before anyone knew anything. So obviously people are just making. Just saying stuff. So back in the day, you, like you said, you'd have to wait for a magazine to come out or a newspaper and some time had passed.

[00:32:45] **Tim:** Now it's like instant, like, oh, we see this graphic video. Somebody was, someone was killed. me go see what everybody's saying about it. Everybody's saying about it knows nothing more than you do. It's just the loudest lie is gonna win.

[00:32:58] **Ben:** Right.

[00:32:58] **Tim:** one that fits your, fits your worldview. So, yeah, but can we put that genie back in the bottle?

[00:33:04] **Tim:** No. You, you, the

[00:33:06] **Carol:** Sun out. Mm-hmm. Mm-hmm.

[00:33:10] **Tim:** people are gonna post, post immediately without any knowledge whatsoever.

[00:33:14] **Ben:** Right. And I think, so going back to my triumph, you know, that's my attempt to add that friction back in is to limit my social media. And I, and I've been gradually doing that and I think it's just gonna become more extreme in the near future, you know, limiting.and I'm like, I feel like this is a good friction that I'm gonna be adding back into my life.

[00:33:35] **Carol:** It's nice when I can scroll through Facebook or Instagram and only see things from people I care about. I did the same thing a while back, like I think I had had like 160 friends when I, when I ended everything and it was like military spouses. It was people whose our kids were best friends and I wanna see like still how their kids are doing and they, what they're achieving as they head off to college and stuff. But the majority of people, if I ever met you just once or I don't even know you, you got removed. And it's nice. It's nice to know what I'm getting into every day when I open an app.

[00:34:06] **Tim:** too,

[00:34:10] **Ben:** Coincidental.

[00:34:11] **Carol:** Mm-hmm.

## [00:34:12] Friction in Software Development

[00:34:12] **Tim:** but when, when it comes to software development, I, I, I'm trying to think more of good friction ideas. you want to prevent groupthink, right? You, you don't want cargo culting. Organization. So the whole having the argument about buy versus build, if there's no friction there say, oh yeah, I'm sure we can build that, we can build an image, you know, we can build our own DocuSign. Uh, maybe Yeah,

[00:34:37] **Ben:** Right,

[00:34:37] **Tim:** right. Is that really are, is that your, are you, is that really your core,

[00:34:42] **Ben:** right.

[00:34:43] **Tim:** Right,

[00:34:43] **Ben:** wanna get paged in the middle of the night when that doesn't work?

[00:34:45] **Tim:** exactly. Right. Do you do ha ha has yours been tested in court?

[00:34:49] **Carol:** you know, the legal document, so Yeah, yeah, yeah. Why? So it's like having that friction of, all right, no, we have to have this conversation might be a little uncomfortable, but by versus build, what are we gonna do?

[00:35:01] **Tim:** What are the pros and cons? Just having people think, and I think that's of what I think is the differentiator between good friction versus bad. Good friction is about,challenging the idea, not the person. Right? bad conflicts is, is attacking people's confidences. It undermines. It undermines their dignity, whereas good friction, although can sometimes be uncomfortable 'cause different people handle conflict different ways, good conflict, different ways. it, it, the result is that, you know, things are fleshed out and everyone at the end feels good about the, the end result. Mm-hmm.

[00:35:36] **Adam:** That's one thing that I love about my company is that we've really got a good culture of debating ideas, not people or motivations. Right? It's just like, I,

[00:35:46] **Carol:** healthy.

[00:35:46] **Adam:** I wanna do this and this is my thought on how I wanna do it. And then we like just kind of like sit around and spitball it for a few minutes, try to, did you think of this?

[00:35:54] **Adam:** Did you think of that? What about this approach instead? And it's like, oh, I hadn't thought of that, or, that's a really good idea, or, well, I did think of that and here's why I wouldn't do it that way.

[00:36:06] **Tim:** It does take a level of maturity though. 'cause I've seen some

[00:36:08] **Carol:** It does.

[00:36:08] **Tim:** smart people, and, and someone will say something and they're like, they're, they get all confused and they're like, that's just stupid

[00:36:15] **Adam:** Yeah.

[00:36:17] **Tim:** Maybe it's stupid to you, and maybe you didn't mean that you're, you're not saying that they're stupid.

[00:36:22] **Adam:** Mm-hmm.

[00:36:23] **Tim:** just saying that idea is stupid. But it's like the natural tendency is for the person hearing that going, whoa, whoa. Now we're in fight mode.

[00:36:29] **Adam:** Yeah.

[00:36:29] **Carol:** Right? Gotta be defensive.

[00:36:31] **Tim:** I, I don't understand. Why do you think that's a good idea? Have you thought about this? Right? That's a better way to phrase it. This a better result than just going, oh, that, that makes no sense, or that's just stupid. then it just shuts down sort of conversation when, once it gets to that kind of tone.

[00:36:49] **Carol:** See for me, like I'll go into it with a problem statement and I will have a list of things that I think we could do. Like this is

[00:36:55] **Ben:** Tim is a jerk. What do we do about it?

[00:36:58] **Carol:** rid

[00:36:59] **Adam:** Should I, should I be unfriending Tim on Facebook or.

[00:37:02] **Carol:** we all did. You

[00:37:03] **Ben:** Sorry Carol. I didn't mean to

[00:37:05] **Carol:** You're,

[00:37:05] **Ben:** over you.

[00:37:05] **Carol:** okay. No, I was gonna say I go into it with like a list of like possibilities, but I don't bring those up.

[00:37:11] **Carol:** I don't bring 'em to the table until people have started talking. So I just wanna like come in with a problem and then I want to encourage my team to just start turning out ideas. Just let me know that you at least understand the problem statement enough to have thoughts about solutions or to ask questions about the problem. And then after a little while, if we're not getting anywhere, I can go, Hey, have we considered like this approach with us? Or procedure for pulling the data? Rather than letting EF build our link statements for us. Like there are little things that you can then. Kind of like add, but to me, the going back and forth with the how do you wanna solve something is super healthy. And I think encouraging your team to have those conversations just builds trust. It lets them know that a, I don't know, something. So I can go have conversations with anyone on the team. Like no one's gonna look at me and do the whole stupid comment. They're gonna go, oh yeah, let's, let's make sure you understand.

[00:38:08] **Carol:** And that's where the like friction, the having that upfront, having the ability to work through something gets you a solid team and leads to success.

## [00:38:17] The Value of Face-to-Face Meetings

[00:38:17] **Ben:** So along those lines, and this is something that I, dunno, I've just always felt really strongly about, there was, for the last, I, I haven't heard so much about it just recently, but for the last four or five years it felt like there was a huge push asynchronous communication. Like, you know, like, I'm gonna wire up this Slack bot, and the Slack bot's gonna ask you what you're working on today.

[00:38:42] **Ben:** And then you tell me what it is and then I'll post it to a slack room and people can go read it if they wanna read it. it was all about not going to meetings and not talking to people and not having to take time outta your data connect. I always felt like the meetings, like those kind of meetings where you're talking to people about what they're doing, like that's, that was the good part the day.

[00:39:03] **Ben:** Like, I don't really care about what you're doing. It was the talking to you about it. Like that was the interesting part. That was the synergistic part. If you just post three bullet points about what you're working on, like I'm never gonna read that. 'cause I don't know. I just don't care that much. Like it, it's like when people are like, oh, we're in this meeting.

[00:39:21] **Ben:** Hey, should we record this meeting? I'm like, no. one is ever gonna go and watch this recording. The whole point of this meeting was to show up.

[00:39:30] **Carol:** Yeah. when our teams did the whole shuffle, like we had a several people from different teams now all working together. So our teams used to work in these silos and now it's like two people, one person from a team and having to learn how everyone operates. So I implemented a daily standup, and the standup was just me saying what I was working on, what I'm blocked on, and then asking everyone to just say, are you blocked?

[00:39:54] **Carol:** Do you need help? Like, this is your safe spot to say, I don't know what I'm doing here. This is the area I've never touched. Can someone help me? Or to even say, I don't know what work to pick up next, because things were just so chaotic and the meetings would, you know, go 30 minutes. If there were problems, it would go five minutes.

[00:40:13] **Carol:** If there weren't anything,

[00:40:14] **Ben:** Right.

[00:40:14] **Carol:** would end it and then other people would join back. But I'm with you that getting the, like, I'm gonna air quote face-to-face, but getting that like in the same room, those conversations happening, like they're crucial for team development and to build trust with each other.

[00:40:29] **Ben:** You know, I will even say that the idea of good friction and having to show up for a meeting, and if you miss that meeting and there's no recording and there's no transcript and there's no summarization available, then you missed out. feel like that's good. Like you, there has to be, I think it's good that there is a repercussion for the fact that you did not get there. And if it becomes too easy to, you know, borrow someone else's notes and miss and watch the recording, then like, why show up next time?

[00:41:00] **Adam:** So speaking of being in a room.

## [00:41:02] Remote Work Habits and Personal Care

[00:41:03] **Adam:** World, maybe the good friction of meetings is that it forces me every day to just be in the habit of putting on a clean shirt and brushing my hair and washing my face so that I'm ready in case there is a meeting. Uh,I've been,

[00:41:17] **Carol:** because I'm not wearing a shirt right now?

[00:41:19] **Adam:** no,

[00:41:20] **Carol:** de I definitely have on the shirt.

[00:41:22] **Adam:** no. I,

[00:41:22] **Carol:** go to work with just my gym shirt on still, and when someone calls, I have fill a sweater.

[00:41:26] **Adam:** yeah, yeah. Very, very early on when I started working for alumni q when it was just me and Steve, there would be days, you know, it wasn't the normal thing, but there would be days where it's just like, I don't feel like getting outta bed today. So I didn't, you know, I would just wake up, get up and go to the bathroom, brush my teeth, and then go sit in bed with my laptop and work and then, you know, like, I get a, a, not FaceTime, like a, a video chat.

[00:41:50] **Adam:** I don't know what we were using at the time, but whatever a video chat thing would pop up and it's like, I decline it and be like, gimme a second. I'm not gonna put on a shirt.so, yeah, it's, it's good to be in the habit of taking care of yourself in this remote world. And you know, if you, if you don't know if you're gonna have to, appear on camera, it's, you know, it's a good motivator to take care of yourself.

[00:42:11] **Carol:** It's good for your mental health too,

[00:42:13] **Adam:** Exactly. It's a good friction

[00:42:15] **Carol:** mm-hmm.

[00:42:16] **Ben:** I almost thought I used to do this ritual where at the end of the day I would close down all of my browser tabs. And I

[00:42:24] **Adam:** psycho.

[00:42:25] **Ben:** my local server. I used to do it. So I'd wake up the next morning, I'd come into the office and it would be a totally clean slate. I'm kind of tempted to try to do that again.

[00:42:34] **Ben:** 'cause I have all these taps. I'm looking at them right now, and they've been there for days, weeks,

[00:42:39] **Adam:** I. I have never had more productive mornings than when I would leave the, and end the day in the middle of like debugging something, or in the middle of building a feature. It's like that last two minutes of the day. I just leave myself a little post-it note somewhere on the screen that's like, okay, this is what you were working on.

[00:42:56] **Adam:** And I come back and it's like, oh yeah, right there. The cursor's in the spot where I was working on it and

[00:43:00] **Carol:** Yeah.

[00:43:01] **Ben:** true.

[00:43:03] **Adam:** getting back up to speed quickly,

[00:43:06] **Ben:** All right, well that's all I have to say about good friction. here, here, here's a challenge to you, challenge to listeners, just as you're going through the next week, counting the moments until the next airing of our show, you know, think

[00:43:18] **Adam:** as you do.

[00:43:19] **Ben:** as one does. Think about the things that could maybe benefit from being a little bit harder.

[00:43:25] **Ben:** No. You know, don't let your brain go there.

[00:43:28] **Adam:** Everybody loves a, everybody loves a podcast that gives 'em homework.

[00:43:34] **Ben:** you know, I, I don't know, I just, I'm, I'm curious.

[00:43:39] **Adam:** Yeah, no, I would, I would like to hear what you know, now that this is on my mind over the next week, I probably will think of things like, oh, this is a good example of good friction.

[00:43:49] **Ben:** here's something that, I heard this, I don't relate to this in any way, but there are all of these apparently, like micro payment plans, systems that have come online

[00:43:59] **Adam:** Mm-hmm.

[00:44:00] **Ben:** where it's like you go to buy your burrito

[00:44:03] **Ben:** chipotle.com and you can pay over the course of four, you know, like you can buy your $12 burrito over the course of three payments of $4 kind of a thing over the course of weeks.

[00:44:13] **Adam:** Yeah.

[00:44:14] **Ben:** And they were this piece that I was listening to about it, they were saying essentially that the friction of taking on debt has essentially completely disappeared. You know, you don't

[00:44:23] **Adam:** Yeah.

[00:44:23] **Ben:** a bank to apply for a loan anymore. It's like, you don't even have to,

[00:44:28] **Adam:** Can you imagine? Can you imagine going bankrupt because of your burrito habit?

[00:44:32] **Tim:** Right.

[00:44:34] **Carol:** eating

[00:44:35] **Ben:** but apparently there are so many of these, these loan, these like micro loan

[00:44:40] **Adam:** Yeah.

[00:44:40] **Ben:** and I guess they operate on some sort of different regulations so they don't have to do credit checks the way other loan systems work. And I, I don't know. I mean, I don't know much about that world, but, it's like we're just removing all of this friction and, and, or, I'm not a gambler.

[00:44:58] **Ben:** I don't like sports. I don't understand anything about sports or why people watch them. But the idea that it's, it's like now you can gamble on sports from the comfort of your own lazy boy.

[00:45:09] **Tim:** On your

[00:45:10] **Ben:** I have no, I have no moral, yeah. Like I have no moral judgment about gambling, but I know that when I hear about it on the radio and people talk about the like, oh, I'm $160,000 in debt my, from my gambling.

[00:45:22] **Ben:** Like, that's, that sucks. That's awful. And it's

[00:45:25] **Carol:** Shouldn't be so easy.

[00:45:26] **Tim:** Yeah,

[00:45:27] **Ben:** It shouldn't be so easy. It seems like, it seems like there should be some good friction.

[00:45:30] **Carol:** Yeah.

[00:45:32] **Tim:** a hundred percent.

[00:45:34] **Adam:** All right.

[00:45:34] **Ben:** to go to Vegas for a conference.

[00:45:36] **Tim:** Yep. Well, it was an interesting topic, Ben, that yeah, I'll think about it.

[00:45:41] **Ben:** Yeah. Put that, put the, put the noodle on. That's not a saying.

[00:45:45] **Tim:** Mm-hmm.

[00:45:47] **Adam:** It is now.

[00:45:48] **Tim:** It is now you just coined it.

[00:45:50] **Adam:** All right. So as a, like a quick, Programming note here at the end, I think we're gonna miss next week.

[00:45:55] **Adam:** So you're gonna have two weeks to think of your good friction stuff because Ben and Tim are gonna be in Vegas at a conference and Carol's going on vacation.and so nobody wants a full hour of just me talking. So,not to mention, I don't know. Well, yeah, if I do that, it's gonna be like, I'm gonna record an audio, audio book of my book or something.

[00:46:14] **Adam:** 'cause I don't know what else I would talk about by myself.

[00:46:17] **Tim:** Do some

[00:46:17] **Adam:** I, I'm, no, I'm no like Ezra Klein, right? I can't write an hour long essay and just sit and give that to camera, but whatever. anyway, we're skipping next week, so, we'll catch again in two weeks.

## [00:46:29] Patreon

[00:46:29] **Adam:** So this is the part where I say this episode of Working Code is brought to you by muting Tim on Facebook instead of unfriending him.

[00:46:34] **Ben:** Do the right thing guys.

[00:46:37] **Adam:** And listeners like you, if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording, editing and transcription costs, and we couldn't do this every week without them.

[00:46:50] **Adam:** Special thanks to our top patrons, Monte and Giancarlo. You guys rock. We love having you be continuing top supporters of the show. You guys are amazing.

## [00:47:01] Thanks For Listening!

[00:47:01] **Adam:** of course, as usual, we're going to go do the after show. Ben wants to talk about stuff he's noticing in people's dating profiles and, and, and I'm gonna drop a, a, a repeated, this is not the first time I've mentioned it, but, I'm gonna drop a podcast rec, of a very technical nature.

[00:47:19] **Adam:** I've mentioned the podcast in, in the past, but it'll be a good, repeat reference to them anyway, if you wanna get, the after show. Go to patreon.com/workingcodePod and become a Patreon of the show. We'd love to have you. You can join our discord, go to workingcode.dev/discord, join the community.

[00:47:35] **Adam:** It's totally free and open to the public. Just a great place to hang out with like-minded individuals. That's gonna do it for us this week. We'll catch you next week. And until then,

[00:47:43] **Tim:** Listen, the only thing that is 100% frictionless is the fact that your heart matters.

[00:47:50] **Ben:** Amen.
