---
title: "119: Potluck #7"
description: "On today's show, we all bring something juicy to consider for Potluck #7."
date: 2023-03-22
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/119-potluck-7/id1544142288?i=1000605336055"></iframe>

On today's show, we all bring something juicy to consider. Carol kicks things off with some trepidation about becoming an independent contractor; Tim shares an article on [Technical Debt][tech-debt] and digs into the subtle differences between _tech debt_ and _bad code_; Ben is befuddled by the fact that "common sense" is apparently wildly subjective; and, Admin introduces us to [Bloom Filters][bloom-filters].

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[bloom-filters]: https://en.wikipedia.org/wiki/Bloom_filter
[tech-debt]: https://stackoverflow.blog/2023/02/27/stop-saying-technical-debt/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/119-potluck-7.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Adam:** So classic bloom filters use 1.44 log base, two of one over. I believe it's a sigma bits of space per inserted key where sigma is the false positive rate of the bloom filter. Right? So, the,

[00:00:14] **Tim:** I

[00:00:14] **Ben:** Did you say

[00:00:15] **Carol:** It just sounded,

## [00:00:36] Intro

[00:00:36] **Adam:** Okay, here we go. It is show number one 19, and on today's show we are going to learn with you what we are talking about. that's right. We are doing another potluck, so, none of us knows what the other people are going to talk about. We're gonna just figure it out as we go.

[00:00:47] **Adam:** but as usual, we'll start with our chimes and fails. Carol's back. Welcome back, Carol.

[00:00:53] **Carol:** Hey.

[00:00:53] **Adam:** Uh, we didn't, we didn't know why you were gone last week. We, we only found out after we recorded that it was the bronchitis and your

[00:00:58] **Carol:** Yeah. Being sick sucks.

[00:01:01] **Adam:** glad you're better. Glad you're back. And, yeah.

[00:01:05] **Adam:** So, Ben, why don't we start with you.

## [00:01:07] Ben's Failure

[00:01:07] **Ben:** I'm gonna go with a failure, which is just that at work lately I've been feeling really burnt out.

[00:01:13] **Ben:** and I think I'm, I, I've been reflecting on it and trying to get at the root of what it is. Cause I feel like, I've talked about this on the podcast before where my day is packed usually, like I have everything that I need to do on my, on my juror board, and it's just attacking the day and trying to fit as much into the nooks and crannies of, of the, of, of time as possible.

[00:01:35] **Ben:** And I've, I've been finding lately myself just staring at the screen or I'll, I'll just like, I just like left an hour early today.

[00:01:44] **Carol:** which isn't like you, right?

[00:01:45] **Ben:** like me at all. I just, like, I had nothing left in the tank. And I think if I do like a, like a five whys get to the bottom, I feel like I'm not doing consumer facing work.

[00:02:00] **Ben:** I'm doing internal platform work. I'm doing the object scanning, looking for unused objects in S3. And these are all technically interesting problems. But I think I just got so much. Energy from working for customers and with customers to solve problems that not having that in my life right now is very, it's very draining for me.

[00:02:25] **Ben:** It's, I dunno, I just, like, I'm, I'm having trouble finding the, the inspiration from doing just behind the scenes work.

[00:02:33] **Carol:** Yeah, I never enjoyed when I felt like I was just a code monkey, like just putting code out the door, right? Like I didn't wanna just be writing like, I like interacting with people more than anything, so There's no stimulation for me if all I'm doing is just writing code and pushing it out, and I don't get any feedback on the process or how it impacted anyone.

[00:02:54] **Carol:** I feel like it was pointless.

[00:02:56] **Ben:** It, yeah, exactly. It's tough.

[00:02:59] **Adam:** Well, I mean, Ben, don't, you know, corporations are people too.

[00:03:04] **Tim:** Court,

[00:03:04] **Tim:** Supreme Court.

[00:03:05] **Adam:** helps the, you're doing work that helps the

[00:03:07] **Ben:** That's true. I'll bring that with me tomorrow when I start work

[00:03:11] **Carol:** Make yourself a post-it note.

[00:03:13] **Ben:** It's weird though. So, you know, you know, I'm straddling the, the two different systems at work, the legacy system and the modern system, and I'm, and I've been told more or less not to do anything on the legacy system other than this data cleanup stuff that we're working on. And it's, it's like I, I'm trying so hard to be good actually, and, and, and not color outside the lines right now, but I'm, I'm just itchy.

[00:03:37] **Ben:** I'm just itching to build something for somebody. I dunno, eventually, I guess I'll be on the, the new platform and I'll be able to build for our customers. Then once I finish this data deletion stuff, I just need to figure out how to get the data deletion stuff done faster. There's just, there's a lot of stuff there, but.

[00:03:52] **Adam:** I was gonna say, do you have a rough idea back of the napkin math like,

[00:03:58] **Ben:** It's, it's unclear. It's unclear. There's a, cuz we, we've talked about this before, A lot of this is scanning over S3 and there's, there's really not that many shortcuts you can take because you literally have to list out, you know, millions or billions of objects. So

[00:04:15] **Tim:** What letter

[00:04:16] **Tim:** are you on now?

[00:04:17] **Ben:** well, so yeah, that one folder that has a ridiculous amount of stuff in it, it, I think it should cross over into nine, tonight. So I'm more than halfway through the hex alphabet.

[00:04:28] **Tim:** go.

[00:04:29] **Adam:** Okay. Yeah. Yeah. It's zero through nine, then A through F.

[00:04:32] **Ben:** Yeah.

[00:04:33] **Ben:** So that's

[00:04:33] **Adam:** was gonna say, is it letters or numbers first, but yeah, then it all came back to me.

[00:04:37] **Ben:** Carol, what about you? What do you got going on?

## [00:04:39] Carol's Triumph

[00:04:39] **Carol:** I am gonna call the Triumph. It's probably a failure, but I'm gonna call it the Triumph. for the past month, no No, no. Poo. Poo. Sorry. Beep right. No quack. every night at six 18, our internet goes out. Every night and it's very frustrating and we

[00:04:58] **Carol:** call customer support. Yeah, it is. It's six 18 to which they like to tell us we probably have loose cables.

[00:05:05] **Carol:** So they've sent two technicians out. They've even came out and reburied our cables because clearly that causes it to go out at six 18. Like new hardware, new everything. So we said on hold, so on hold, I've even hit a Twitter now and I post every day to the same thread, like, oh, it's out again. Oh, it's out again.

[00:05:22] **Carol:** So I filed a

[00:05:24] **Carol:** complaint with the FCC and they responded yesterday that they've served my I S P with the complaint and they have 30 days to respond, like with written, information on how the resolution's being handled and stuff. So hopefully don't reach out and get it fixed. So I feel good that I went a step further and was like, I'm going to ask the government for help here because every day and you telling me I need to like tighten my cables is BS because my

[00:05:49] **Carol:** cables are just fine.

[00:05:52] **Tim:** Wow,

[00:05:53] **Carol:** Oh gosh,

[00:05:54] **Adam:** do you have other options?

[00:05:56] **Carol:** no. That's the other thing and I don't wanna tell him that cuz my husband is on the phone. He's like, we're looking for another provider. I'm like, we can't get another provider here,

[00:06:04] **Adam:** star length or, yeah.

[00:06:06] **Tim:** starlink isn't available.

[00:06:07] **Carol:** All we

[00:06:08] **Carol:** can do is get a hotspot through like T-Mobile and

[00:06:11] **Carol:** it's like, has the worst coverage ever. And it gives you a warning that in the afternoon you may not have connectivity at all.

[00:06:19] **Carol:** So

[00:06:19] **Tim:** six 18

[00:06:20] **Carol:** yeah, probably around six 18. Yeah. Yeah. So I'm calling it the triumph that I went a step further and you know, am hopefully gonna get it resolved. But who knows? ISPs suck. They just have like you have no say in anything when it comes to who provides service to your house for things like power or water, you just have to go with who's there.

[00:06:41] **Carol:** And that includes internet. So stuff.

[00:06:45] **Ben:** I just wanna say though, between you, Getting your rights, defended as a consumer, and then the other week you getting a lawyer to help defend your rights as an employee. I feel like you uphold your own rights more in the last month than I've done in my entire life,

[00:07:01] **Carol:** gosh, I,

[00:07:02] **Ben:** impressed.

[00:07:03] **Carol:** I have had to stand up for myself over the past two months. A lot, well, month and a half. So, you know, since the end of January I've had to get some people to back me saying that I have rights and I'm gonna fight for them because, well, I've earned them and so has everyone before me. So, yeah.

[00:07:19] **Carol:** Thanks,

[00:07:20] **Ben:** such a, yeah, that's such a great instinct. I feel like my instinct is just to, like suck it up and complain to people, but, but like, you actually do something about it. It's

[00:07:29] **Carol:** I'm a, I'm a fighter. I'm definitely a fighter at

[00:07:31] **Carol:** heart, so, yeah. But yeah, that's me. I will not be screwed over. Not again. What about you, Sam? What you got?

## [00:07:41] Tim's Triumph

[00:07:41] **Tim:** Well, I'm glad to say things. going with the triumph, things are back to normal. This week has been normal. You know, I will never again, and if I do ever complain, hold me to this. I like, about three weeks ago I was like, you know, things have been really quiet. And things have been so quiet. And then after two weeks of absolute hell, if things are back to being quiet, I'm like, okay, don't, don't, don't, don't ever say

[00:08:05] **Tim:** that this is boring, because I don't wanna go.

[00:08:07] **Tim:** I mean, those last, those last two weeks, man, I was like, I, I barely saw my family. Although way I worked from home, I didn't take dinner with anybody. I don't, I think five days I didn't shower. But you know, things are,

[00:08:18] **Tim:** things are, things are back to nor I was working from 6:00 AM to about 11:00 PM every night.

[00:08:23] **Carol:** Oh my gosh.

[00:08:24] **Tim:** And I didn't eat. I've lost about five pounds, which is psych,

[00:08:27] **Tim:** that, that's the only positive side, which I've since gained back. But yeah, so I, I'm glad things are back to normal. And then I'll say the another thing, my son, max, he's been, you know, he comes home every day from college and talks about what he's learning in his, he's taking discreet mathematics.

[00:08:41] **Tim:** And I have

[00:08:41] **Tim:** to say, I, I'm a bit envious of his CS classes he is taking cuz he's like telling me, oh yeah. So we, I had a wrote a program that was, you know, they'd give him these exercises and he created this wild loop and it was like, it worked, but it was like a lot of code and it was kind of slow. And he's like, then discreet mathematics, we talk about Euclid and algorithms.

[00:09:02] **Tim:** And then I refactored my program and now it's like, it

[00:09:05] **Tim:** converted it down to like, you know, 10 lines of code from like, 70 lines of code and it runs so much faster. And he's like, oh, and I can count on binary on my fingers and I can convert them to hex. And I'm like, wow. Yeah, I didn't, I didn't go the traditional route.

[00:09:20] **Tim:** I didn't, I, you know, I didn't learn, I didn't take a, a traditional CS class. So I'm just, I'm a bit jealous. He's a bit jealous of my son that he, he's, he's taken to it well, and he's like, gets super excited. He comes in from when he comes home from college and then he'll be like, tell me what he learned today.

[00:09:35] **Tim:** And it's like, he just gets really in depth. And I'm sitting here working and typing and he's like going on and on. I'm like, I don't understand, like 20% of what he said.

[00:09:47] **Adam:** your stunt Sounds like me. I really enjoyed the computer science parts of college.

[00:09:50] **Tim:** Oh yeah. He loves the mathematics. I was, I'm not good at math. I didn't like math. I don't understand math. but he really, he gets it. So I'm super proud of him.

[00:09:59] **Carol:** So part of all of this has been going on with me. I'm like, should I go back to school? Like how much would going

[00:10:04] **Carol:** back to school mean for me right now? Because I think I would love learning it the correct way knowing that I know how to do it right. So I would be able to take what I've learned and apply like the actual CS knowledge on top of what I know and it makes me kind of wanna go back and take some classes just because I've been doing this and let's see how they pair together.

[00:10:26] **Carol:** Like once you have the knowledge of just learning in like your everyday using it versus getting some education with it.

[00:10:32] **Adam:** Yeah, that sounds like it could be a lot.

[00:10:34] **Carol:** Yeah.

[00:10:34] **Tim:** yeah. And he's not actually even take HA hasn't really even taken programming classes yet. In, in, but he, what he tends to do, and he did this in high school, like with statistics and stuff, they give him computers to work on. So if he had to do like a statistics problem, he would just write a JavaScript.

[00:10:50] **Tim:** Program to, to like do the calculations for him. And so whenever he had, and they let him use the computer for the test, so he'd do the pro, he would just pop in the numbers that they spit it out and he'd be done with his test in like 10 minutes. And everyone else has like an hour to work on it because he wrote all these little programs.

[00:11:07] **Tim:** So, and that's what he is kind of doing with his discreet mathematics classes. He's taking what he's learning in math and going, okay, let me write a program to simulate this.

[00:11:15] **Carol:** That's so cool.

[00:11:16] **Ben:** That was.

[00:11:17] **Carol:** Yeah.

[00:11:18] **Tim:** So I was super proud of him.

[00:11:19] **Carol:** He'd make a good educator.

[00:11:22] **Tim:** Yeah. But you don't make money.

[00:11:23] **Carol:** True, true. Maybe like a side hustle for him would be teaching cuz you know,

[00:11:28] **Carol:** the, the learning's good for him.

[00:11:30] **Adam:** West Boss seems to be doing okay for him.

[00:11:32] **Tim:** That's true. Yeah. Yeah. If you're doing like, yeah. That kind of stuff. My, my daughter, she, she, she went to her with her English class. They went last, last. And spoke to, they went to like the elementary school and spoke to like the lower grades, the little kids and read to them and she loved it. She

[00:11:52] **Carol:** Aw.

[00:11:52] **Tim:** good, just asked such a good time talking to the, reading to the kids and I'm like, she's like, maybe I could be a teacher.

[00:11:58] **Tim:** I'm like, maybe

[00:12:00] **Adam:** Do

[00:12:00] **Tim:** any money.

[00:12:01] **Adam:** charity

[00:12:03] **Tim:** Yep. So that's me. How about you Adam?

## [00:12:06] Adam's Triumph

[00:12:06] **Adam:** Oh, I have a fail, which is that this t d d book is still on my desk because this is a triumph. I finished the t d D book.

[00:12:14] **Adam:** Huh?

[00:12:16] **Tim:** Did you finish?

[00:12:17] **Adam:** I did. I finished it.

[00:12:19] **Adam:** I read

[00:12:19] **Ben:** were joking.

[00:12:20] **Carol:** Yeah.

[00:12:21] **Tim:** fake out.

[00:12:22] **Adam:** That's right. no, it, it's here because I wanted to mention it before I go over and put it on the bookshelf. so yes, and the reason that I read it today, I read it from, you know, where I had left off two years ago to the end of the book today.

[00:12:34] **Adam:** and the reason that I read it today was that I took today off of work. that's part of how this is also a triumph. I had a particularly long and rough day yesterday, which I will talk about in a second. and so I took today off, and just like for recovery, right? Not so much like a, a comp time, but just like I am a zombie, after yesterday, and I, I cannot function another day, so I'm gonna take the day off.

[00:12:57] **Adam:** And I slept in and I made myself a nice big breakfast and I caught up on some important emails in my personal life that I had to get done. And, and yeah, just like. You know, little things and I, you know, I did things, a couple things around the house and, I took a nap in the afternoon and I went out to lunch with my friend Chuck and I read this book.

[00:13:16] **Adam:** the reason that I had such a long day yesterday is because it was one of our customers giving day. and so, you know, they, they do a bunch of email through us and they don't have a particularly nuanced approach to email. Their approach is usually just like, let's send as many emails as we possibly can and hope that some people open them and that, they are inspired enough to give us money.

[00:13:37] **Adam:** And as much as I don't like it, it actually worked. Last I checked, they had made about $3 million from their email campaign

[00:13:45] **Ben:** Noise.

[00:13:46] **Carol:** gonna mass email everybody. I.

[00:13:48] **Adam:** for real. Yeah, it, it was a difficult day, right? So, you know, it, we have this system built to send a lot of emails as fast as we possibly can and that's, that's fine. It does reasonably well, most of the time.

[00:13:59] **Adam:** But where it tends to get, bogged down and, and struggle is when, okay, like here's half a million emails, please go, right? Like it's a lot of work to like prepare half million emails to, to send, cause you've gotta pre-render them all and get it all ready so that it can, at the moment of send, you can send them all as fast as possible.

[00:14:15] **Adam:** and the database queries.

[00:14:17] **Ben:** You pre-render them, like you don't render them as you're sending them.

[00:14:21] **Adam:** that's right.

[00:14:21] **Ben:** Oh, fascinating.

[00:14:23] **Adam:** So, so that we can, you know, and when you're only sending to 20,000 people, that makes a lot of sense cuz you can send 20,000 emails really quick and you do that in a couple of minutes. We could actually do it a lot faster, but we are being rate limited by mail done.

[00:14:37] **Adam:** And so we have to have a whole little thing that, that we keep track of how many emails we send per calendar minute is what we call it. , right? Like a minute on the, the clock. and, and if we're getting close to, you know, we're like, we're using math, right? We're actually doing like standard deviation, like how close are we gonna come if we try to process another batch this minute?

[00:14:56] **Tim:** and if it's too high, then we're like, okay, well, we'll, we'll just go to sleep until the next minute sort of thing. does, does mail gun re you sitting one at a time or do you, can you like send a batch, like a big file of 'em?

[00:15:08] **Adam:** they do have, what effectively is like a mail merge sort of thing where you can say, okay, here's the template, here's the, recipient list and here's like a, a set of datas for, you know, for their particular type of mail tokens. Here's the values I want you to fill in for the, those tokens per, per user, right?

[00:15:24] **Adam:** So Tim gets, you know, hi Tim and Carol gets Hi Carol. And Ben gets, hi Ben. If you, if you set the first name token. , they do have, I'm, I'm closing my eyes cuz you guys waving at me is distracting. they do have a feature like that and we, I, I don't know if we didn't know about it or they introduced it after we had like, put in a bunch of work to build our own pre-ordering system.

[00:15:46] **Adam:** Or maybe it only became available to us at a certain pricing tier that we later opted into or something like that. I don't know. But for whatever reason we do it ourselves.

[00:15:57] **Carol:** That sounds like tech debt to me.

[00:16:01] **Adam:** it's a, it's an interesting topic. yeah, I, I, I don't recall all of the history, but

[00:16:05] **Tim:** only, only reason I ask is I know, SendGrid, which is what we use, they have a way you can do, rather than sending one mail at a time, you can just send a huge batch of them. Right. And it's just a chase on payload. And we actually render, we render the HTML and put it in the body.

[00:16:19] **Tim:** They have like things where mail merge, where they can do

[00:16:22] **Tim:** that, but it's like we're using ColdFusion to do it. So we just kind of create that JSON itself

[00:16:28] **Tim:** and then send it to 'em. And you can send. We've never done millions, but it's in a lot.

[00:16:35] **Tim:** So, I dunno. That's the only reason I was asking.

[00:16:38] **Adam:** we are rate limiting ourselves to a target of about 4,500 a minute. and I think that the actual might be 5,000 a minute, something like that, so that, you know, if we go a little bit over, it's not that big of a deal. and that tends to be fine. Right. So then you, 4,500 a minute.

[00:16:51] **Adam:** I don't know what the math is, but you know, we can get out a large audience in a half an hour, so we figure that's fast enough. anyway, so it was giving day and they sent a butt load of email. And, the first one, because, you know, they're trying to maximize the, the calendar day. the first one got sent at like 12 0 0 0 1, right midnight oh one, on.

[00:17:13] **Adam:** Tuesday night, going into Wednesday. And so I stayed up, and, and made sure that that pre-render and everything worked good. and then I made sure, and it did struggle because that was one of those giant, you know, let's send to half a million people, once. And so, you know, I had to kind of help that through its render process.

[00:17:28] **Adam:** And then I stayed up to midnight to just make sure that it went and we were getting, off on the right foot for this giving day. And, and then I went to bed and I had set myself an alarm for 3 55, wake up and be ready. F yeah, 3:55 AM So three hours and 55 minutes after I went to bed, I got up.

[00:17:43] **Adam:** and you know, that was when the next big render was gonna start. And so I had to get up and just watch that one, make sure, and again, it needed help cuz it was another giant one. and then, you know, a couple here and there, a couple of giant ones throughout the day interspersed. A couple of, smaller audiences between them and I had to, you know, just kind of babysit this thing and help it throughout the day.

[00:18:01] **Adam:** And so, you know, I got up at 3 55 after having gone to bed at midnight ish. and I was up until about 9:30 PM yeah, so it, it was a very long day. And, and, and I'm not 25 anymore. That's a, that takes a, a toll on me.

[00:18:16] **Carol:** you need your sleep

[00:18:17] **Adam:** and, and I'm, you know, I'm also down on the Mountain Dew, right? So I used to just, like, that would be a 12 Mountain Dew day for me before, and I still managed to do it with just, my usual two plus one.

[00:18:27] **Adam:** I had a, I I allowed myself a third,

[00:18:29] **Tim:** down on the Mountain Dew sounds like it should be a rage against the

[00:18:31] **Tim:** machine. Song down on the Mountain Dew

[00:18:37] **Adam:** maybe. I, I'm not a youth anymore, so, I wouldn't know those things anyway. so I was exhausted. I took today off to recover. I read my book and did a whole bunch of other. It's, you know, like personal betterment things. No, I'm happy about that. It was a good day and I feel restored because of it.

[00:18:56] **Tim:** You know, you need those mental wellness days.

[00:19:00] **Tim:** Right.

[00:19:01] **Ben:** Mm.

[00:19:02] **Tim:** My, my daughter yesterday, I, I didn't even realize she like, cause I work in the, in my office and then their little computer room is next door. I went and kissed her on the forehead yesterday at 4:00 PM I'm like, how is school? She's like, I slept all day.

[00:19:17] **Tim:** I'm like, what? I didn't realize my, my, my wife was told me that she, like, Lilly is just shot. She just can't handle. But she didn't tell me she stayed home. So she slept like 17 hours.

[00:19:27] **Carol:** Oh

[00:19:28] **Tim:** It took, it just took a mental health day and then she went to school today and they're like, where were you? Were you sick?

[00:19:32] **Tim:** She's like, no, my parents let me take a mental health day. And they're like, they did what? The kids are like blown away. They're like, yeah, we get, we get to take at least, you know, one mental health day per semester. So

[00:19:44] **Tim:** she took.

[00:19:45] **Ben:** cool.

[00:19:46] **Tim:** She was just, she was just broken. She's, my wife's like, she's just crying. She like drinks

[00:19:50] **Carol:** Oh, no,

[00:19:51] **Tim:** go, I just can't handle, I just, I just can't. So she, she stayed home and now she's right as rain, so,

[00:19:57] **Carol:** it's good you guys raise your kids in a, in an environment where it's okay to have mental health days, it really is because a lot of parents shut that down. So to be like, Hey, it's okay that you're having emotions and you need to express that. And if you need to take a day off from life, take a day off from life and stay in the bed, that's okay.

[00:20:14] **Carol:** Tomorrow will come around. Then you can try again.

[00:20:17] **Tim:** yep. Either that they're gonna pretend they're sick and

[00:20:19] **Tim:** then you're gonna be suspicious. So it's like,

[00:20:21] **Tim:** yeah, just be honest. I just can't, I just can't mentally cope today. So

[00:20:25] **Tim:** I'm staying home. I'm staying in

[00:20:27] **Tim:** bed.

[00:20:27] **Carol:** Good parenting.

[00:20:28] **Ben:** When I was a, kid, I desperately wanted to stay home from wor from school one day, and I was pretending to be sick. And my mom gave me a thermometer, like it's a digital thermometer,

[00:20:38] **Tim:** Put it next to the

[00:20:39] **Tim:** light

[00:20:39] **Ben:** I put next light bulb and it completely melted.

[00:20:44] **Ben:** I was like, oh, that's a high fever. I should definitely not go to school.

[00:20:48] **Tim:** I, I did the old light bulb trick so many times. Just there was just days like, I can't handle, but my mom was like, ah, take your temperature. Like, light bulb was like, how, how are you? 107 degrees

[00:21:01] **Adam:** All right. I guess that brings us to our topic, our, our four topics for the day.

[00:21:06] **Carol:** Yeah.

[00:21:07] **Adam:** go first?

[00:21:08] **Carol:** I can kick us off if you want.

[00:21:09] **Tim:** let's go.

## [00:21:11] Going Independent and Making Tough Decisions

[00:21:11] **Carol:** So,

[00:21:11] **Carol:** I have hit the, the point where it is really scary being alone, making decisions. I've went from being on a team where I have a lot of people supporting me on my ideas. I have people to constantly talk to you and sitting at home going, oh geez, like, what projects do I pick up?

[00:21:31] **Carol:** Like which routes do I go? This impacts my life and everyone around me, because if it's too stressful, everyone in my house is gonna be impacted. If I don't charge enough money, then I'm gonna be mad at myself for not doing the math right. And it is. Very scary when you're talking about consulting and making all the decisions on your own because not only are you making the decisions about what you pick up, you're also contributing to people's tech that you don't really know and you're having to learn their infrastructure.

[00:22:01] **Carol:** You're having to learn, you know, what they do day in, day out. And I feel a level of commitment with everything I write. And I feel like any advice I give should be very solid. So then I second guess myself on, is that right? Like, what would I say if I were sitting in an office with like my old team, with people who I trust to be honest with me?

[00:22:23] **Carol:** And like, would I be saying the same things or would I be saying it and then looking at them going, Hey, like, are they like responding to this positively or negatively? Cuz maybe I need to change what I'm thinking. And now it's just kind of like all on my shoulders and it's

[00:22:39] **Carol:** very, very, scary you guys.

[00:22:43] **Ben:** For.

[00:22:45] **Carol:** I didn't kinda like, I'm, I'm hitting things I didn't know I was gonna like be feeling. Right. But it, it is a little scary when you're talking about the doing it alone thing and you know, having a lot of people rely on you, so,

[00:22:58] **Adam:** I guess I have a piece of advice for you, which is, start.

[00:23:02] **Adam:** You know, uh, small project and that way, you know, if it gives you a taste of, you know, making that money and you'll figure out like, is that enough?

[00:23:11] **Adam:** Right? And then you can go for the next project. Okay. Well, you know, I learned from the last project that I only charge you half of what I actually need to make.

[00:23:17] **Adam:** So this one's gonna cost more.

[00:23:20] **Carol:** there's a whole thing I didn't even know about till finally I got an accountant to kind of work with me is, There's a whole tax I didn't even realize I had to deal with. Right. Not only do I have to pay tax here where I physically write the code, because I'm in Georgia, I have to deal with Washington regulation and Tad Bitt too because I'm a resident of Washington because we're military.

[00:23:41] **Carol:** So in a few months, all of my Georgia knowledge has to go pick, picked up like in Arizona, cuz that's where we're gonna be at. And then I also have to handle tax in wherever the company

[00:23:51] **Carol:** is established at that

[00:23:52] **Carol:** I'm working for.

[00:23:53] **Carol:** So I ultimately circle in like four taxes. Yeah. It's not fun. So I'm like, okay, it's settled.

[00:24:00] **Carol:** I will not handle this somewhat else is going to be

[00:24:02] **Carol:** responsible for this part of my life because I don't even know what happens in Pennsylvania. So how am I supposed to handle any taxes there?

[00:24:11] **Tim:** Wow.

[00:24:11] **Carol:** Yeah,

[00:24:12] **Carol:** And military just adds like a layer of complexity to everything we do now. So,

[00:24:18] **Tim:** so, so you have to deal with that even though you're not, you're not in the military

[00:24:22] **Carol:** I'm not in the military. I'm a resident of Washington, so I'm taxed under Washington because of the residency? No, the state of Washington. But because I physically am residing in Georgia and I am doing the work in the state of Georgia, there are like b and o taxes as I'm responsible for since I'm self-employed here.

[00:24:41] **Tim:** gotcha.

[00:24:42] **Carol:** But yeah, I don't get tax Georgia

[00:24:44] **Carol:** taxes.

[00:24:45] **Tim:** so who's in Washington State?

[00:24:47] **Carol:** Me and my husband, no, me and my husband, that's, that's our state of residency.

[00:24:51] **Carol:** When you're in the military. Yeah. So when you're in the military, you have a state of residency and that's where you pay your individual taxes out of, and that's who protects you against unemployment.

[00:25:00] **Carol:** All of that stuff is Washington, which is great cuz Washington doesn't have income tax, but what they have is higher tax rates on services to cover that. So then I have to deal with their services as well.

[00:25:12] **Carol:** Yeah. Again,

[00:25:14] **Carol:** account. Nobody take any of that for advice. Get an accountant, because that's how I figured it out.

[00:25:21] **Adam:** Yeah, that's the real advice.

[00:25:22] **Carol:** Yeah. Get an accountant

[00:25:24] **Carol:** and they're very busy right now because it's tax season.

[00:25:27] **Adam:** Mm-hmm.

[00:25:29] **Ben:** But there, there is definitely a trade off to going out on your own. I mean, there, there are definitely a lot of people, I probably count myself among them, who like, I just want to go in and do my work and I don't want to have to think about not just the tax stuff, but like, where's the work coming from and who's, you know, putting in requests for, like bids for work and all that kind of stuff.

[00:25:50] **Ben:** And that's a lot. It is very,

[00:25:53] **Carol:** it's huge. And. I didn't realize how many people trust me until I started down this venture, because I have friends reaching out to me going, we're ready to quit working and just work for you. So let us know, like when you're ready to go bigger than what you're doing. Right?

[00:26:09] **Carol:** So when you have more work than what you're capable of, we will gladly sign on with you at any point.

[00:26:14] **Carol:** And I'm like, okay, I don't trust myself right now to make decisions, so I'm not about to impact someone else's

[00:26:19] **Tim:** let me get on my own. Let me get on my own feet

[00:26:21] **Tim:** here first. Right.

[00:26:22] **Carol:** But it, it's good to like know that people reach out to you for a doing work. Like, you know, I've talked to, I dunno, can I say this, Adam, do you mind like if I say this, like I've talked to Adam

[00:26:31] **Carol:** A.

[00:26:31] **Carol:** Little bit about like, the possibility of consulting with them. several of my friends have reached out and been like, Hey, our company wants to talk to you because we mentioned that you were looking for contracting or consulting work. So lots of people trust what I do. As far as how good I am, but then to have people be like, I trust you with my family's life, , you know, to provide for us is a whole nother thing.

[00:26:54] **Carol:** So I'm like, okay, I have to be a lone burst and figure out how to stand on my own two feet and make this work before I pick up anyone else. But it is good to know that I have shown people that I'm capable of doing it. So it gives me a little like, okay, I can be okay. Maybe, maybe

[00:27:14] **Adam:** I mean, if nothing else, you know, if you do end up in a spot where you have more work to do, then you can physically get done yourself. You know, those people would probably be happy to subcontract for

[00:27:24] **Carol:** Yeah. Yep.

[00:27:25] **Adam:** on like a, a project by project basis.

[00:27:27] **Carol:** Yeah, like weekend work and stuff. Yep. So it's definitely scary, but I'm stepping through it day by day. It, it is great. When I say alone, I'm not alone, obviously. I have my husband who's constantly reminding me, we're okay and that I should keep going forward with this and I shouldn't be taking a permanent job, and I should just, you know, go through this and enjoy it and figure it out.

[00:27:48] **Carol:** So it's good to have his support.

[00:27:51] **Ben:** I remember when I was in school, years and years and years ago, one of the guys in my class who was senior year and we were all talking about, you know, do you have, does anybody have plans for after graduation? And this one guy was like, yeah, I'll probably just do, you know, a bunch of consulting. And I was like, consulting.

[00:28:09] **Ben:** You literally know nothing and have zero experience. , like what could you possibly consult about? I just love people's enthusiasm, man, or confidence. People's confidence just is like amazing.

[00:28:22] **Carol:** Yeah.

[00:28:24] **Tim:** You don't know what you don't know.

[00:28:27] **Carol:** Isn't that song in Hamilton?

[00:28:29] **Adam:** no

[00:28:30] **Tim:** Don't think so.

[00:28:31] **Carol:** Okay. Okay,

[00:28:32] **Carol:** nevermind. Doesn't matter.

[00:28:36] **Adam:** All right, well, are we ready to move on to the next one then?

[00:28:38] **Carol:** Yeah.

[00:28:39] **Ben:** it.

[00:28:40] **Adam:** Okay. Who wants to go next?

[00:28:42] **Tim:** I'll go.

## [00:28:44] Technical Debt

[00:28:44] **Tim:** So I was reading an article the other day. that popped up about, I think it was from Stack Overflow, kind of their summary email for, let's talk about, stop saying technical technical debt. I think, I think Ben kind of brought this up. Is it technical debt or is it just bad code that you didn't know about at the time?

[00:29:04] **Tim:** Right. And, and it, it kind of, it kind of drove that home a bit. Right? So, I mean, one of the subheadings is tech debt is just more than just bad code. And we don't have to read the article, but I think the principle of it is, is that, you know, when you talk about technical debt in the, in the actual technical term that Martin Fowler talked about, this is like where you make a decision that you're, you're not necessarily going to deal with that problem right now.

[00:29:32] **Tim:** The best way. That's a decision, right? And you hold yourself account like with debt, right? You don't, you just don't just like throw something in a credit card and then go, oh, I'm not gonna worry about it ever until it's a problem because. , that's really bad, right? You, you

[00:29:47] **Tim:** always have a statement coming every month that tells you just how much debt you have, and eventually you have to rectify that debt.

[00:29:53] **Tim:** There's, there's going to be a, a coming due of that debt. If you write bad code, you don't really know that that's debt. Right. It's, it's not on your statement until it's a problem.

[00:30:03] **Adam:** I, I saw this is just because you were kind of trying to struggle for words there. I saw somebody recently, refer to it as retirement of technical debt. Like you, you accept the technical debt as a choice, and then when you go back and you pay it back, he referred to it as retirement of technical debt.

[00:30:19] **Adam:** And, and I

[00:30:20] **Adam:** kind of like that.

[00:30:21] **Carol:** I

[00:30:21] **Tim:** and I

[00:30:22] **Tim:** think I, I think I ran into that today. So I ran into an issue today, and this was a decision that I made. So I have, a voice recognition kind of system thing where you can call and make a payment on, on an insurance policy. And the only customers that we had, they only had, like, so in our system you have keys.

[00:30:42] **Tim:** Payment keys and the keys determine what bank account the, whenever the money is received from the consumer where that money is deposited. And all of our customers, at the time, they only had one account, so they only had one set of keys. So there's really, at the time, no reason for me to try to look up what the keys should be.

[00:31:03] **Tim:** Cause no one had multiple keys. So I just kind of hard, hard coded. But in configuration files I put their keys. And so whenever a payment was made, those were the keys that were sent. Well, unbeknownst to me, so you know, just because of lack of communication, one of our customers signed another, they had another bank account that stuff needed to go into.

[00:31:23] **Tim:** So they had another set of keys but no one told me. And so to today, I got an email from the customer going, Hey, I just noticed that, you know, stuff from, cuz they represent multiple insurance companies. Stuff from insurance company A is going into this bank account, which is good, but. Insurance company B is going also going in here, which is bad.

[00:31:45] **Tim:** I'm like, oh. So that was technical. That was a decision I had made. Now the debt has come due, like, so now I need to, I need to write some code that basically goes and looks up and says, all right, what should it be? And I did that. It, it took a couple hours. I got it pushed out today, and, and it worked fine.

[00:32:01] **Tim:** I didn't write bad code. It's just I made a decision like, look, none of our customers that are using this system have more than one set of keys, so I'm not gonna prematurely optimize and write it. the bad thing is I wasn't told in advance that, you know, this had happened, this happened back

[00:32:16] **Carol:** We usually aren't by the.

[00:32:18] **Tim:** Yeah, for

[00:32:19] **Tim:** sure. Yeah, for sure. So, I see that as technical debt, cuz I, I, that was a decision I had made. I was like, when we come to that point, when someone says, Hey, we need to add another set of keys to this customer, I'll, I'll go refactor and it'll work. But fortunately communication broke down. But, you know, writing just bad code is not technical debt.

[00:32:39] **Tim:** That's just

[00:32:41] **Adam:** Well,

[00:32:41] **Tim:** cleaning stuff up.

[00:32:43] **Adam:** I think I disagree with you just a little bit, right?

[00:32:45] **Tim:** ahead. Yeah. Yeah.

[00:32:46] **Adam:** I think an and accretion of bad code can become technical debt in, in a way that it is weighing you down. And, and I guess honestly, this kind of ties back into what that article was referring to, or, or sort of where that article headed, which was, you know, how do you present technical debt as something that is valuable for your team to work on to the business so that they will give you the time to work on it.

[00:33:13] **Adam:** Right. Because if you just go and say like, look, we

[00:33:15] **Ben:** you can't, it'll never

[00:33:16] **Adam:** Yeah. We, we wanna make a whole bunch of changes to the code that will have zero effect on how the program runs. And we still wanna get paid for this six weeks that we're gonna do this yeah. And they're gonna be like, no. So the article I've really loved, the way it framed it is call, they could say, call it maintenance load.

[00:33:31] **Adam:** Right. This technical debt is slowing you down, right? You have to do things in more than one place, or you have to run a bunch of manual tests because things aren't well tested or, or, you know, whatever it is that's going on, because of this technical debt, they say refer to it as maintenance load.

[00:33:45] **Adam:** So if it's, if you are at a 50% maintenance load, then a six week project will take you 12 weeks to complete because you're spending 50% of your time dealing with the fact that you have these problems in the code. And so by framing it that way, you are showing the business that if they invest in reducing maintenance load, then they are investing in future projects moving more quickly.

[00:34:10] **Adam:** And, and, and it also gives them something very concrete like, I don't know. It gives them something that, that they can understand as a non-technical person, right? Like there are things about the way that this exists that need to be better. And it's slowing us down and. Yeah.

[00:34:28] **Ben:** Here's something that I've been grappling with, so I don't know if you know the, the name Eric Elliot. And he's, he's fairly well known, I think, in the JavaScript world. He's an author, I believe he teaches courses on JavaScript. And, he, he's a proponent of this primary key library for databases called qwi, which essentially is a, a variation on u UIDs, universally unique identifiers.

[00:34:53] **Ben:** And, he, he lays out in a very well-crafted argument why you should be using UU IDs as your database keys, because, They don't leak any information about when they're created. They don't leak any information about the order. they can be generated outside of the database from different systems. You can have all this horizontal scalability that you wouldn't have with something like an auto incrementing value.

[00:35:18] **Ben:** storage is no longer an issue really, with databases. Performance around clustered primary keys is like no longer a performance concern apparently. And, and he can lay this argument out entirely. and I'm listening to it. I'm like, I agree a hundred percent with everything you say. And on my next project, I will use an auto incrementing integer because like, that's just literally how my brain thinks.

[00:35:41] **Ben:** And I don't know if that's technical debt or if, is it, is it just me saying I don't have to deal with horizontal scalability? I'm not dealing with secure information. Like if, if it leaks the order in which records are created, like that just doesn't matter for the type of application I'm building. Am I just being naive and stuck in my ways?

[00:36:02] **Ben:** Or am I just making some non-art articulated, calculated decision about how I enjoy building applications? Or am I just baking in technical debt that I'm gonna have to pay for eventually? I, I don't know. I don't know what the answer is.

[00:36:17] **Tim:** I don't know what the answer is either, but I'll tell you what I do. So I always create tables with an auto increment Id only because the tools that I use whenever I'm like doing, like, you know, ad hoc queries on, you know, in a, in a SQL tool, they need that in order to. Deal with the data when I'm doing like fixing stuff, but in the code I always use a, a go or a, a, UU i d and that the code itself uses that.

[00:36:46] **Tim:** It never uses the primary key.

[00:36:48] **Ben:** So you're saying that your, your record has both an incremented integer but then also a separate column for a, a more complex value,

[00:36:57] **Tim:** Yeah. And, and the, the biggest reason for that is because, yeah, like you said, if that U U I D is exposed, there's no way you can just go in there and go, you know,

[00:37:07] **Tim:** ID equals and plus one.

[00:37:09] **Tim:** Right. Right.

[00:37:09] **Tim:** And that's, I mean, cuz that's one of the os top 10 kind of

[00:37:12] **Tim:** things. That's you, that's one of the biggest, biggest ones.

[00:37:15] **Tim:** So yeah. So the code itself never uses the primary key. The only thing the primary key is for is like when I need to go in, like correct some data manually and my just, you know, it's just, it is just my tool. It has to. I use aqua data to update stuff and whenever I'm doing some ad hoc updates, it needs a primary key and that's, so I'm like, okay, I'll, I'll create that for you with my code only uses the, the U i D

[00:37:40] **Tim:** So, I disagree . Um,Hey, that's why we do potlucks.

[00:37:44] **Adam:** yeah, so, I mean, I, I think everything that you guys have said is true and, and correct and, and that's fine and great. Here's what we do and why we do it. we, similar to Tim, have a numeric auto incrementing primary key and a separate quid column. And when we have something that is user facing, Where that quid would be visible in the URL or whatever.

[00:38:06] **Adam:** That's, that's why we use the quid over the ID for all the reasons that you have said. However, the linking together of rose via like foreign keys, we use, we do that with the primary key that the numeric, it is my understanding that, indexes on numerics will be faster than indexes on a 36 character wide, string column.

[00:38:31] **Ben:** And that's where I get into trouble too, and trouble's not the right word, but that's where I feel like I don't have a leg to stand on because Hill or other people will say something very technical about databases. Like my understanding used to be that if you as a database is inserting new rows, if the primary key is in, in incrementing, like monotonic, mono atomically incrementing value that they get put literally on disk next to each other.

[00:39:02] **Ben:** And the, and the database doesn't have to move things around in memory. And that not doing that would be slow because you'd have to do a lot of disc seeking in order to find like the right place to put it in the clustered index. But then someone will say something like, oh, well, on solid state drives, that just doesn't, that's not a thing

[00:39:17] **Carol:** It's not, doesn't matter.

[00:39:18] **Ben:** And I'm like, is it not though? Because I feel

[00:39:21] **Tim:** How do we know?

[00:39:22] **Ben:** I don't know enough. It, it's, it's like when people say, oh, with HTTP two, you no longer have to bundle files cause we can just like push all this junk in your face at the same time. And, and, but then like, you know, two years later you hear, you'll hear people say like, oh, well that wasn't really true.

[00:39:37] **Ben:** And HTP two like didn't really give us a lot of the advantages we thought that we're gonna have, but HTP three will be the best. I'm like, how do I know that we're not gonna say the same exact thing about random, insertion of data in a clustered index? Like maybe that's just not working as fast. I don't know.

[00:39:52] **Ben:** But like, I, I'm not technical in that sense, so I don't know. So it's, it's hard for me to push back against some of that stuff.

[00:39:57] **Tim:** at the end of the day, if my queries are coming back with, you know, milliseconds, like low milliseconds, I don't care.

[00:40:03] **Tim:** Honestly, I honestly don't care.

[00:40:06] **Ben:** I hear you

[00:40:07] **Adam:** yeah, yeah. So we, I mean, we have a good column. We put an index on it and. That's what we show to people when we need to show them an id. but we still use the, the numerics internally.

[00:40:16] **Tim:** Yeah, no, I, I get that, that that would be my preferred way, but just. Stuff happened.

[00:40:22] **Tim:** So ,So , was that technical debt? I don't know. But, that's just the way it happened, that, that probably wasn't technical debt. That was probably just like, Hey, I'm gonna use this U U I D to join things and Okay. It doesn't, didn't run slow.

[00:40:35] **Tim:** So good enough. So,

[00:40:38] **Tim:** but anyway, stop calling it technical debt, unless it actually is that, that's, that's

[00:40:42] **Tim:** what I got from

[00:40:43] **Tim:** that article.

[00:40:44] **Adam:** we'll we will, put the link to that article in the show notes for sure. That was a really good read.

[00:40:48] **Ben:** At work, there's always conversations about who should be working on technical debt. We have. Most of the teams at work have some sort of an on-call rotation where there's in theory someone who's getting page and in theory, that person should probably also be fielding more of the pull request reviews and like more of the interrupt driven work and dealing with support.

[00:41:09] **Ben:** Like they're kind of, they're on crap duty for the week kind of a thing. And some people have, have put together a theory that, that that person should also be the one actively working on technical debt. But I, I think it's, it's the same as like trying to get the business to buy into technical debt. Like it's just, it's, it's isolating it too much as a thing versus something that everyone should be working on all the time to some degree.

[00:41:34] **Tim:** Plus, I mean, who, who has like the central repository of what is

[00:41:37] **Tim:** considered technical? Right. I mean, I don't know of any, I mean, we don't have that unless it's a, a project that I've worked on pretty much exclusively. I know where the bodies are buried. but it's like when you got a team of people, it's like pretty much everyone's gonna have a different idea of what is it that needs to be refactored.

[00:41:55] **Tim:** I've had people join a project that I was on that start refactoring stuff like, oh, we need to take this out of a, out of a config file and put it in a database. I'm like, no, no, no, no, no, no, no. Please, please don't do that. Don't do that.

[00:42:06] **Carol:** Please don't cause us more technical debt.

[00:42:09] **Tim:** Yeah, why, why are you doing that? It's working fine way It is

[00:42:12] **Adam:** That was another really good point in the article, was that like too often or it's too easy and too common for people to just be like, I don't like this code. I wouldn't have written it this way. So I'm calling it technical

[00:42:23] **Carol:** That's not technical

[00:42:24] **Carol:** debt. Yeah.

[00:42:25] **Tim:** just changing

[00:42:25] **Carol:** Yeah.

[00:42:26] **Adam:** Yeah.

[00:42:27] **Ben:** To be fair, sometimes that is technical debt but sometimes it is not.

[00:42:33] **Adam:** Correct. Alright, Ben, do you wanna go next?

## [00:42:37] Common Sense is Apparently Subjective

[00:42:37] **Ben:** Yeah, sure. I, I'm calling this one common sense is apparently subjective. and that's, it's snarky, but I, I started off my day, thrown out a couple of what I thought were very common sense things, and I got, I felt like a hard pushback against both of them, which I was not expecting in any way whatsoever.

[00:42:59] **Ben:** So the two things were one, I had, I had put in our main engineering channel, kind of a public service announcement. Say it again?

[00:43:07] **Adam:** War is bad.

[00:43:08] **Ben:** Yeah.

[00:43:10] **Adam:** Well, I'm, I'm sitting here thinking like, what could, well,

[00:43:12] **Carol:** Yeah. What.

[00:43:13] **Adam:** could you say that's like more universally accepted?

[00:43:17] **Ben:** So the first thing I wrote today in the main engineering channel was, Hey, when people are doing pull requests, and we use GitHub at work, so you know, they go to GitHub to review someone's. I said, when you're done reviewing code, just ping the person whose code it is and let them know that you're done reviewing it.

[00:43:36] **Ben:** And I, I thought that was just like, why? So that someone will know that their code's been reviewed and they can go do something about it.

[00:43:45] **Carol:** do you not get emails that are like,

[00:43:46] **Carol:** Hey, it's done reviewing?

[00:43:49] **Ben:** that was the pushback. It's like everyone was, a bunch of people were like, oh, well this is a tooling problem and, and we need to set up email filters, or we should have some sort of Slack integration where when you get mentioned and you get a note in this special Slack channel that your PR is ready.

[00:44:05] **Ben:** And I I, I was like, to me, all of that sounds like a lot of work. And what doesn't sound like any work at all is saying, Hey, Carol, PR is good to go. And I just, I was blown away at how many people wanted to use technology to solve what I thought was a people problem, not a technology problem. And

[00:44:27] **Carol:** am a fan of the technology solution cuz the last thing I wanna be doing is writing, like be writing more code and you ping me to tell me my other code's ready. I'm like, I'll check at the end of the day so you don't have to tell me now. Like

[00:44:39] **Carol:** I'll check later. I don't wanna know. Right now I'm busy.

[00:44:42] **Ben:** the, it, it's, it's great that you say that because I was literally like 20 minutes into this, back and forth on Slack about this, and I had to stop and I said, all right, let me, let me just briefly reframe where I'm coming from cuz maybe that's where the issue is. I am coming from the belief that getting code into our customer's hand is the paramount importance and everything else is secondary.

[00:45:07] **Ben:** So the moment that a PR is done, what I'm trying to do is decrease the lag time between PR approval and deployment. And I'm like, if, if we're not all on the same page about that as the goal, then none of the rest of this conversation even makes any sense. And I think maybe that was part. The disconnect that I was having with the other engineers.

[00:45:27] **Carol:** so does it only require one reviewer? Is that like one reviewer and it's good to go? Because

[00:45:33] **Carol:** other places I've worked, it's like two reviewers and a lead have to sign off on the code before it's done. So three people are ping me to tell me they've completed a PR on my code. I would get angry.

[00:45:46] **Ben:** Yeah. We only have a one, A one reviewer policy.

[00:45:49] **Carol:** Okay.

[00:45:50] **Ben:** And then Tim, Tim, I believe his situation gets even more complicated where I think he said the person who writes the code isn't even the one who's allowed to deploy it. Right. Like, doesn't have to be a different person altogether.

[00:46:00] **Tim:** Yeah, true. For pci,

[00:46:01] **Tim:** we have to have, the person who writes the code has to be different from the person who deploys the

[00:46:05] **Tim:** code. It has to be different from the person who reviews the code.

[00:46:07] **Carol:** Yeah.

[00:46:09] **Ben:** So, so clearly people are in different contexts, which I think that's fair. There's different rules and regulations around how, how things go. But in our context, Where it's one person does the review and then the person who writes the code is ultimately the person who deploys the code. I, I was just, I, I, I was flabbergasted that I was getting any pushback at all.

[00:46:32] **Adam:** it's gonna be heavily dependent on what comes after merge, right?

[00:46:37] **Ben:** Deploy

[00:46:38] **Adam:** well, but the, the question that I'm asking is, what does a deploy look like? Because if the deploy is, you know, it could be as simple as pressing merge merges the code, which triggers an auto build and deploy script, which auto deploys the thing, and that's it, it's done.

[00:46:54] **Adam:** And maybe you need to monitor, maybe you need to, you know, make some database changes at the same time that you are deploying the code or whatever. but it, it, it entirely depends on what your deploy process is, right? If, if you have a very manual deploy process, you have to go prepare some archive and S F T P it up to the server and whatever,

[00:47:13] **Ben:** anything wrong with that,

[00:47:14] **Adam:** uh,

[00:47:15] **Adam:** then

[00:47:16] **Tim:** judgment.

[00:47:17] **Adam:** I judge you then, then there's, that's very vastly different than press the merge button and the code will work its way out there.

[00:47:23] **Adam:** Right? Which is. where some of our environments are. And so our process is if a pr, is gonna deploy itself, when it gets merged and doesn't need any babysitting through that process. And, like, and it's not gonna, it doesn't need any, any other inputs. Right? If, if the only thing it needs is for somebody to merge it and, and it'll deploy itself, then we tag it with a Okay, deploy.

[00:47:48] **Adam:** Okay. Two deploy tag, which, and like an okay to merge tag, so that everybody knows, like once it's reviewed, you have the author's permission to press the button that will make it be deployed without telling them.

[00:48:00] **Carol:** Like merges pr. Yeah.

[00:48:03] **Adam:** Yeah. And so it, it takes it out of the author's hands.

[00:48:06] **Adam:** No. You know, sometimes I'll end up being the one to deploy it anyway. Cause I have to be, you know, it'll be the next day and I still haven't gotten a review and I'm like, Hey guys, I'm still waiting on my review. And, and I'll, they'll go look at it and be like, okay. Yeah, I, I just. Reviewed it and it's, it's good to go and then I'll press the button cause I'm, you know, been standing there waiting for them.

[00:48:23] **Adam:** But, I think taking people out of the loop can be beneficial because like Yeah. And it, and it could work to the same goal that you're talking about in a reducing time from PR review to code running for users.

[00:48:38] **Ben:** I, I mean, if you have the infrastructure in place to do that, I think that's a very interesting conversation to have. We don't have that. We, we still have a manual step. You have to kick it off and then once you kick it off, it's fairly automated. After that, there's kind of a go no-go moment that someone has to agree to.

[00:48:57] **Ben:** So everyone's talking about all the different kind of integrations that they have or that we could have. And, and the point that I made was that all of that is great for you as the person who wrote the code and has created the pull request. The person who's reviewing the code can't assume that you have any of that in place.

[00:49:17] **Ben:** Because what happens if I'm doing a review for Carol and she's got 18 different integrations that alert her on her phone and her desktop and her tablet, but like, I don't know that. And then I, and then maybe she's like, oh, you don't have to tell me. I just get those automatic, and then I do a review for Adam, and I assume he has the same thing, but he doesn't.

[00:49:35] **Ben:** And he comes back and he's like, Hey, when are you gonna get that PR done? And I'm like, oh dude, I'm sorry. I did it two hours ago. I didn't realize you didn't ha you know, didn.

[00:49:44] **Adam:** cuz I didn't go look.

[00:49:45] **Ben:** No, but why? That's what I'm saying. Okay. So, so here, here's, here's a pet peeve. When I'm watching a movie, and I think I'm, I trust that a lot of people can relate to this, and maybe they can't, but I'm trusting there.

[00:49:55] **Ben:** In movies, oftentimes when people are having a phone conversation, when the phone conversation ends, they just hang up. There's no like, goodbye. There's no catch. Later. It was great to talk to you. I'll talk to you tomorrow. It's like someone finishes a thought and then they just hang

[00:50:11] **Ben:** up.

[00:50:12] **Ben:** Right? And you're like, whoa.

[00:50:13] **Ben:** That's not how people work in real

[00:50:15] **Tim:** it's, it's it's like, okay. yeah. Good, good talking to you all. Okay. yeah. Yeah, you too. All right. Alright. Good. Yeah. Hey, if you

[00:50:22] **Tim:** need anything, yeah, sure. Gimme

[00:50:23] **Tim:** okay. Alright. Yeah.

[00:50:24] **Tim:** Talk to you later.

[00:50:25] **Ben:** how humans

[00:50:26] **Tim:** Okay. Alright. Hey, bye.

[00:50:28] **Ben:** I feel like doing a PR and then not telling the person that you're done is, is the code equivalent of that? I just finished my thought and now I'm hanging up the call because you know what? When I stop talking to you and then you're like, Carol, you're there like, oh, you should just know that the conversation is over at that point.

[00:50:47] **Ben:** But like, that's weird

[00:50:50] **Carol:** So Ben just called me, not human, because I literally end every call with, okay, bye. And I click end.

[00:50:57] **Carol:** And if we weren't done, then I'm like, okay, bye. Click. And Steve will call me back and be like, oh, there was one more thing. Or you know, my mom usually is the one that calls me back. I'm like, I thought we were done.

[00:51:07] **Carol:** I said, bye. That was the cute word. This conversation's over, I'm on to the next thing.

[00:51:13] **Adam:** Yeah,

[00:51:13] **Ben:** This session has ended

[00:51:15] **Carol:** Yeah.

[00:51:16] **Adam:** I, I, I, I think that there's a, an element of truth to whoever it was that said, it's a, a tooling problem because GitHub is already sending alerts. I think the problem is that they're sending the alerts, via email. Unless you go into your, by default, they send you an alert via email

[00:51:34] **Ben:** but like who's checking their emails

[00:51:36] **Adam:** And that's the

[00:51:37] **Adam:** problem. And that's, And that's, the problem. I, I, Hey, listen, I'm right there with you. I check my work email tops like three times a day unless I'm specifically working on something that requires me to get emails from people. Like, I've been doing these compliance projects lately that require talking to outside vendors and stuff.

[00:51:53] **Adam:** And, You know, I'm like some, there are times when I'm like, okay, I need to go send four emails and then I need to keep checking and wait for the, for replies to my four emails. If it's not one of those moments, if it's not one of those days, I check first thing in the morning. I check when I get back from lunch and I check at the end of the day, and that is pretty much the only time I'm gonna check my email.

[00:52:11] **Carol:** But see, if I didn't, if I wasn't checking my emails, I would have push notifications set up in Slack. Like I would have an integration in that says, Hey, my PR has been approved.

[00:52:20] **Tim:** Yeah, we have them in teams,

[00:52:22] **Carol:** Mm-hmm.

[00:52:23] **Tim:** our continuous integr.

[00:52:24] **Carol:** I want the least amount of communication possible. So I don't want people telling me, and I get, some people want it, but when I'm ready, I'll go look. I'll be like, okay, twice a day at 10:00 AM and 3:00 PM I'm gonna check every day to make sure that if anything's approved, I get it merged. And if it's not been done, I'll handle it then.

[00:52:45] **Ben:** See, but again, I think, to be fair, you had a different context in that you were not deploying immediately when your code was done. Because I, that like wasn't the process, right? Like, didn't you deploy like every two weeks or something?

[00:52:59] **Carol:** No, no, no. We deployed Twice a day.

[00:53:01] **Carol:** We were deploying continuously, so when it was approved it was like go out, but it was too noisy and too much of a distraction on everyone. So we, my previous job had set up 10:00 AM and 3:00 PM releases.

[00:53:13] **Ben:** So, okay. So I don't, I don't wanna belabor this. So the other, the other point of pushback, which I was flabbergasted by, and again, it's all subjective apparently, I'm on a team now that just spun up a new Jira board and the Jira board was created with. To do in progress and done columns. So just three columns?

[00:53:32] **Tim:** Can.

[00:53:32] **Ben:** Yeah. Yeah. And, and we've been using it for the week. And I came in today and I was like, Hey, I just, it's been challenging for me to not have a column that represents some sort of a blocked status. Like, I've done the work and maybe it's waiting for a PR review, or it's waiting, I need to discuss it with someone else.

[00:53:51] **Ben:** So I, I don't wanna move it back to, to do, because it's already being worked on. I'm just not, it's not one of my focuses right now. And so I, like I said, we should have either an, a blocked or a, or a ready for review column, something like that. And again, I was like, oh, everyone's just gonna, you know, lift me on their shoulders and cheer for how great an idea this was.

[00:54:11] **Tim:** like,

[00:54:12] **Tim:** don't rock the boat. Newbie founder.

[00:54:14] **Ben:** literally like, everyone on the call was like, Hmm, that doesn't make any sense. Like, why not just leave it in the to-do column if it's blocked? I'm like, or,in the, in progress column, if it's blocked, I'm like, Because I got seven other tickets that are currently in progress and, and like it's,

[00:54:29] **Tim:** but, but, but are they assigned to you? Do you assign it to another person?

[00:54:31] **Ben:** well, I usually leave them assigned to.

[00:54:35] **Carol:** they say assigned to the. So I love the idea of a blocked swim line because it lets everyone ahead of you know what's happening. So like when the, like your scrum master or your P like your pm, come in and look at it, they can go, okay, Ben has four things in work. These are truly things he's working on.

[00:54:54] **Carol:** However, he's held on these other three because he started working but you guys didn't update a spec, or we need something else. Like, it gives them a very clear view of what is blocking you from working so they know what to go look at. They don't have to go through everything that's in progress to find what you're blocked on.

[00:55:13] **Carol:** This gives someone else the view to go, Hey, work on this because Ben needs it. He's stuck. Right?

[00:55:20] **Tim:** So what's the rationale on not doing a block?

[00:55:23] **Carol:** Yeah. That's silly.

[00:55:24] **Ben:** Thank you. All right. I'm glad we're all

[00:55:26] **Ben:** on

[00:55:26] **Adam:** I

[00:55:26] **Ben:** page.

[00:55:28] **Tim:** Okay. Always

[00:55:29] **Carol:** no vote Adam.

[00:55:31] **Ben:** what was the rationale? The rationale was like, Not every ticket even can enter a block state. Like it doesn't make sense for all work. And I was just like, all right, then just don't use that column. In that case. Yeah.

[00:55:43] **Ben:** And then one was like, I think people, the one guy was saying that, well, if he puts stuff in blocked, he tends to forget to check up on it again.

[00:55:52] **Ben:** And, and I'm like, all right, well that's like, that's a you problem. Yeah. Like, that's not a

[00:55:56] **Ben:** me

[00:55:57] **Ben:** problem. ,I, I, I don't know. And it's

[00:56:00] **Adam:** Well, to be fair, Ben, I wish there was a blocked column is a is to them. It's a you problem, not a them problem.

[00:56:10] **Tim:** You gotta find out who, who can unblock you. Is that what you're

[00:56:14] **Tim:** saying?

[00:56:15] **Ben:** So anyway, that was my day. I just, it it, every, every conversation that I thought was gonna be 30 seconds of everyone high fiving with me and my great ideas just like turned into me having to argue for what seemed to make sense. And it was just, it was, it was a bizarre day. I was like, in bizarre.

[00:56:31] **Adam:** Yeah. Yeah, I, I've been

[00:56:33] **Adam:** there.

[00:56:34] **Ben:** Anyway, that's me,

[00:56:36] **Tim:** You're finding an equi.

[00:56:38] **Ben:** We'll

[00:56:39] **Adam:** right.

## [00:56:39] Bloom Filters

[00:56:39] **Adam:** I, I'll try to make this fast cuz this could, my, my, my, potluck topic here is, could probably be its own episode, but I will try to, maybe we'll do a short version and maybe we can come back to it because I've, I've had this little segment idea, like a occasional topic idea that we could come back to where we like take some jargony term or some, you know, Algorithm or data structure or whatever that, that people have heard of, but

[00:57:04] **Adam:** maybe have been too intimidated to look into, to try and learn or whatever.

[00:57:08] **Adam:** And like, let's let's, let's demystify these things. So one of the things that

[00:57:12] **Adam:** I've

[00:57:12] **Tim:** Let's get, let's get

[00:57:13] **Tim:** Max on the.

[00:57:15] **Adam:** well, one of the things that I've

[00:57:17] **Adam:** heard, many times throughout my career, I never really, knew what it was. And, and finally I was just like, well, I, I can Google it and I can just go learn what it is real quick and and at least then I will know, right?

[00:57:27] **Adam:** So, it's a bloom filter, right? You, you may or may not have heard of a bloom filter, B l o o m, in your programming travels, if you're like me, you've heard it and you were always like, oh, that sounds

[00:57:37] **Adam:** complicated. I bet you're smart ,and then you just went about your day, right? so I, I wanted to learn, and, and I'm going to share with you what I've learned. I don't at all claim to be an expert on this topic, but I,

[00:57:47] **Adam:** I think that once you understand. at the level that I understand that you'll be like, oh, okay. That, that sounds like it could be very useful in certain niche cases. So at Bloom

[00:57:56] **Adam:** filter, you have to understand what a hash table is. And you know, I did have the luxury and the the benefit of going to college for computer science.

[00:58:04] **Adam:** So this is something that we covered in a significant amount of depth there. If you're not familiar with the hash table, it's basically think of like a, an object, a

[00:58:12] **Adam:** structure in C F M L or a a,

[00:58:14] **Adam:** an object in JavaScript where, you know, you get, it's like a key value pair, right? You've got a, a key name and some value that you can stick in there. And a hash table is like that.

[00:58:24] **Adam:** And you've got a, a predetermined hashing algorithm where you take whatever the input is and you run it through your algorithm and it gives you, a key name back, right? and, so for example, you could say MD five is the algorithm for hashing, which takes the input and gives you your key name, right? And so, you, you take whatever the input is, could be. A whole book. It could be a phone number, you know, whatever. and, and you run it through your algorithm and it spits out the, the key name for your, for your hash table, and you store the value at that location in the hash table, right? So it could be numeric, right?

[00:58:57] **Adam:** You could have an array of, of, items and you could just say, my array is only ever gonna hold, you know, one through a hundred and your hash hash algorithm somehow based on the input returns to number one through a hundred, right? And that's your hash table, and it goes into that position. The problem with hash tables is that you can have collisions and so you have to have a collision, management, not philosophy, I don't know some word,

[00:59:21] **Ben:** Collision

[00:59:22] **Ben:** res resistant algorithm.

[00:59:24] **Adam:** yeah, whatever. You have to, you have to know what you're gonna do in the case of a collision so that you can

[00:59:29] **Tim:** re.

[00:59:29] **Adam:** Yeah, there you go. Yeah, So, so that, okay, so if you're doing the array of one to a hundred and. and. the first thing goes into 50, And then the second

[00:59:36] **Adam:** thing goes into 51. And then what happens if the, the third thing goes into 50, right? Is it always like minus one? And then, so if you, what if there's already something at minus one, then you go to minus one again, or you know, whatever, whatever that policy is. You, you follow that? Well, okay, so that's a hash table, right? It's just, It's a, basically, it's a way of kind of indexing data in a way, right?

[00:59:58] **Adam:** So you're taking, given the, the input, I know where to find it in the hash table. A bloom filter is a hash table where you intentionally could have, collisions. And the purpose of it is to be able to tell if something is not in the hash table, right? So you, you maybe you scan an entire data set and then you, then you wanna be able to ask the question, is this piece of data somewhere in the data set? And, What a Bloom filter can tell you is one of two things. Either I can guarantee you it was not in the data set, or it might have been in the data set. It can't give you a, a for sure positive, but it can definitely give you a for sure negative. And it does that because the collision, resolution strategy is ignore it.

[01:00:46] **Adam:** Right? So if if three things end up in position 50 in your array, then okay, something landed in position 50. So if, the item that you are checking would land in position 50, is position 50 empty or does it have something in it If it's got something in it, then maybe it was the object you were looking for, but if that position is empty, then it definitely was not

[01:01:08] **Tim:** So false

[01:01:09] **Tim:** positives are possible, but false

[01:01:11] **Tim:** negatives are

[01:01:12] **Tim:** not.

[01:01:12] **Adam:** Correct. there's, you know, there's different variations on this thing, but,

[01:01:16] **Ben:** So do you, is is the,

[01:01:19] **Ben:** it it, it seems like there's some sort of a trade off or calculation that you can do where you say, I wanna have here like, here's the chance of having a false nega. No.

[01:01:34] **Adam:** false

[01:01:34] **Ben:** It false

[01:01:36] **Ben:** positive versus how many hashes I actually have to store. And if I can make like a concrete example,

[01:01:42] **Ben:** let's say,

[01:01:43] **Ben:** I'm lining people up and I'm lining them up by height and I can only see who's at the front of the line.

[01:01:49] **Ben:** So, or I should say, let's say I'm lining people up and I can only see who's on the front of the line. And in one approach I say, I wanna line people up by inches. So let's, like, I have five, like everyone who's five feet tall is in this line. Everyone who's five foot one is in this line. Everyone who's five foot two is in this line.

[01:02:05] **Ben:** And then I could say, you know, is Joe here? Joe's five nine. Oh, well, there's no one in the five nine line yet. So Joe's clearly not in this group, but I have a lot of lines now where if, as if I like did it by hair color and I only have like four hair colors and Joe comes in, Joe's blonde and there's no one in the blonde line, well, Joe's not here.

[01:02:26] **Ben:** But, it's also like my chance of having conflicting. Hash values, like maybe there's much more likely to have a blonde person, even though I only have four lines. Sorry.

[01:02:36] **Adam:** are, yeah, you're very right. I wanna point out one minor difference in that instead of a line, it's just the first person that lands, the first person that comes in, that's five nine, the first person that comes in that is blonde has to stand there and represent that line. Everybody else that's blonde or five nine gets to go sit

[01:02:52] **Adam:** down

[01:02:53] **Ben:** right,

[01:02:53] **Adam:** five nine is represented.

[01:02:54] **Ben:** Yeah, that, that's what I was trying to say with like you could only

[01:02:56] **Ben:** see the first person

[01:02:57] **Adam:** Yeah.

[01:02:58] **Adam:** And, and so, and that's, that is one of the reasons that a bloom filter exists is because what you're doing is you are trading memory for speed. And for, And for, I'm sorry. No, it is, it is a fast algorithm sort of regardless, but what you're trading is, memory for, for false positive rate, right?

[01:03:17] **Adam:** So if you can make your data set wider, if you can add more slots to put stuff in and theoretically have an evenly distributed hashing algorithm, then then your false positive rate goes down. But at the cost of needing more memory to store your index of data. So it's a way of being able to trade, oh, I only have a certain amount of memory, but I, I can accept a certain amount of false positives too.

[01:03:41] **Adam:** And I, I mean, I did, so here's where I got kind of stuck. I was like, okay, I, I, understand the basics of this. What I, What wasn't, immediately clear to me is like, where would this be useful? So I did go look on Wikipedia to just try and get like, okay, what are some practical

[01:03:54] **Adam:** examples of where you

[01:03:55] **Adam:** might use this?

[01:03:56] **Ben:** can just ask, chat. G p t,

[01:03:59] **Adam:** I should have, I

[01:04:00] **Tim:** Apparently fruit, fruit flies in Akamai.

[01:04:04] **Adam:** Okay,

[01:04:05] **Ben:** the cdn.

[01:04:06] **Adam:** well, that's okay. Perfect. So the, the, example on Wikipedia that resonated with me the most was caching, cash filtering. and so like being able to, because the, the example that they give is most URLs are not hit frequently if, you know, if ever more than once, right? Like, you know,

[01:04:25] **Adam:** whatever various resources on a

[01:04:26] **Tim:** one hit

[01:04:27] **Adam:** right? And so how do you de determine whether it needs to be in the cash or not? It's based on, I don't know, somehow they use bloom filters to, to make that determination and it's good for it. I, I don't know a hundred percent understand that, but that was the example that they gave. And I was like, okay, I kind of, I kind of understand why that would be necessary.

[01:04:45] **Adam:** But the, the, when I was on the do Wikipedia page, I did happen to notice, where did it go? They. Okay. Yeah. So classic bloom filters use 1.44 log base, two of one over. I believe it's a sigma bits of space per inserted key where sigma is the false positive rate of the bloom filter. Right? So, the,

[01:05:05] **Tim:** I

[01:05:05] **Ben:** Did you say

[01:05:06] **Carol:** It just

[01:05:07] **Carol:** sounded, it just sounded like Max was talking, right, Tim?

[01:05:10] **Tim:** Exactly. Yeah. He's standing in my room, he's like, that's exactly what he said to me. I'm like,

[01:05:15] **Tim:** I tuned out.

[01:05:16] **Carol:** Good job

[01:05:16] **Carol:** son.

[01:05:16] **Adam:** point,

[01:05:17] **Adam:** 1.44. Basically what it's saying is there's a, a proportion, a ratio of the amount of memory that you use to the, false positive rate that you can expect.

[01:05:28] **Tim:** I mean, I'm looking at the Wikipedia

[01:05:30] **Tim:** page too.

[01:05:30] **Tim:** because I know, I know nothing about this, but yeah, so like said Omi, it's like three quarters of their caching is like, is a page that just hits once within their timeframe. And they, they don't bother caching yet because

[01:05:43] **Tim:** they, because they're, it says that I don't,

[01:05:47] **Carol:** Well, no, I mean like, I mean, why would they cash it right? if it's only being hit 1% of the time, like why even cash that?

[01:05:54] **Tim:** yeah. So like three

[01:05:55] **Tim:** quarters. So,

[01:05:57] **Ben:** Hmm.

[01:05:57] **Tim:** yeah, this is way over my head, man.

[01:05:59] **Tim:** It's hurting my brain.

[01:06:00] **Adam:** Well, but now it is. Now you have a basic understanding of, you know.

[01:06:04] **Tim:** I, I, I know it

[01:06:05] **Tim:** exists. Let, let's, let's go there. Let's, I'll say that I

[01:06:09] **Tim:** don't have a basic understanding.

[01:06:10] **Carol:** now I know who to call if someone asks me about it.

[01:06:14] **Carol:** Like, I have a person for this now.

[01:06:17] **Adam:** Yeah. So, I hope that this can be sort of a regular segment for us where we just, uh, like take, take some sort of data structure, algorithm, something interesting. and demystify it for the other people

[01:06:29] **Adam:** on

[01:06:29] **Adam:** and

[01:06:29] **Adam:** listening to the podcast.

[01:06:31] **Tim:** I mean definitely I I will look this up cuz this does sound interesting.

[01:06:35] **Tim:** I, I'd imagine a lot of key pair mongo kind of things probably use this to, to deal with key pair structures so they're fast. Cause that's always, that's always blow my mind how, you know, relational databases, I get how they're kind of fast.

[01:06:48] **Tim:** Cuz you have these keys and they're all kind of tied together, but you just have a bunch of key pair

[01:06:54] **Tim:** sets in a file and how's that fast? So yeah, this, this seems like it might be part of.

[01:07:02] **Adam:** All right.

[01:07:03] **Ben:** when you, when you, when you said, when you were introducing the topic and you said, hash, and then you said something to the effect of, you know, if you're in fusion, it's like a struct, and if you're in JavaScript, it's like an object. I, I always, I get a little thrown when I hear, when I'm listening to a conversation and they'll be saying things like, oh, it's just an object, such and such.

[01:07:23] **Ben:** And then they'll be talking, talking, talking, and then someone will bring up, so, And the other person was like, oh, well that's really more of a dictionary than an object. And I'm like, wait, what? Isn't that the exact same thing? And I'd be like, oh, that's an associated array. And I'm like, isn't that also the exact same thing?

[01:07:37] **Ben:** And it's, I, I think a lot of languages have a lot more nuance in the data structures, whereas every language that I've ever used, which is, you know, like Col and JavaScripts, it objects like, there's just like bags of data that are either with string keys or number keys. There's not like a real big difference between how they

[01:07:55] **Tim:** and a rare

[01:07:56] **Tim:** stroke.

[01:07:57] **Adam:** Well, I think that, we've been running for quite a long time now, so we should wrap it up. let's see. I had thrown as a joke reference to last week's episode. I had thrown in our after show tease section of our notes document here that Ben is gonna tell us what he learned how to cook today,

[01:08:11] **Ben:** Nothing

[01:08:13] **Adam:** but apparently Carol's cooking too.

[01:08:16] **Adam:** 24 hour

[01:08:17] **Adam:** steak,

[01:08:18] **Carol:** Yeah. Yeah. Yeah.

[01:08:19] **Carol:** 24

[01:08:20] **Carol:** hours. Mm-hmm.

[01:08:21] **Adam:** that

[01:08:21] **Adam:** sounds dry and

[01:08:22] **Ben:** It's never taken me that long to eat a steak

[01:08:24] **Adam:** or to cook it. anyway, we are going to go record our after show, but

## [01:08:28] Patreon

[01:08:28] **Adam:** before we do that, I need to let you know that this episode of Working Code, was brought to you by Common Sense.

[01:08:32] **Adam:** It's electric. I mean it's subjective and

[01:08:35] **Adam:** and, Good. Somebody got it. And the listeners like you, if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording and editing costs, and we couldn't do this every week without them.

[01:08:51] **Adam:** Special thanks to our top patrons, Monte and Giancarlo. You guys rock. If you would like to help us out, you can go to patreon.com/WorkingCodePod.

## [01:09:01] Thanks For Listening!

[01:09:01] **Adam:** Your homework this week is to build something with Alu. No, um, I am going to once again ask you to tell a friend about the show. Tell somebody that you work with, give, do them the favor of introducing them to this

[01:09:17] **Adam:** podcast, Give them, give the gift of Working Code, and, we would really appreciate that. That's gonna do it for us this week. We'll catch you next week.

[01:09:26] **Adam:** And until then,

[01:09:28] **Tim:** Remember, your heart matters even if you like me. Do not grok how bloom filters work.

[01:09:36] **Adam:** oh, come on.

[01:09:37] **Adam:** It's not that hard. It's not that.
