---
title: "213: Staying Motivated Through Long Projects"
description: "In this week's episode, Adam, Ben, and Tim discuss strategies to stay motivated during long-term projects or repetitive tasks."
date: 2025-04-10
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/a4d07c5a-ba0a-46fc-a7f5-f3a0f8b4b4be"></script><div class="redcirclePlayer-a4d07c5a-ba0a-46fc-a7f5-f3a0f8b4b4be"></div>

In this week's episode, Adam, Ben, and Tim discuss strategies to stay motivated during long-term projects or repetitive tasks.

If you've been at the same company or working on a project for a very long time, how do you stay motivated doing the same thing for a long time?

Mentioned Links:

-   Ze Frank - An Invocation for Beginnings - [https://www.youtube.com/watch?v=RYlCVwxoL_g](https://www.youtube.com/watch?v=RYlCVwxoL_g)
-   Cat Purr Generator - [https://purrli.com/](https://purrli.com/)

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/213-staying-motivated-through-long-projects.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** there's a phrase that I love, the grass is always greener where you water it

[00:00:03] **Tim:** Mm-hmm.

[00:00:04] **Adam:** so you know what, what you're paying attention to, what you're taking care of, what you're investing in, that's where it's gonna be the best.

[00:00:10] **Adam:** Even if it's on old technology.

[00:00:11] **Tim:** Yep.

[00:00:12] **Ben:** Heck yeah. jQuery UI is still getting it done.

## [00:00:16] Intro

[00:00:16] **Adam:** Okay, here we go. It is show number 213. And on today's show we're gonna talk about, staying motivated, during long-term projects or just long, long stretches of, the same stuff going on over and over.but first, as usual, we'll start with our triumphs and fails. Carol still, on hiatus this week, just not able to join us.

[00:00:53] **Adam:** So just the boys again tonight.

## [00:00:55] Adam's Fail

[00:00:55] **Adam:** Looks like it's my turn to go first, so I'm gonna start us off with a fail.basically I'm gonna try to keep it short and sweet this time. we have been onboarding a few new customers recently and when they started to use some of the functionality that they're paying for, they found that stuff just wasn't working.

[00:01:13] **Adam:** And it was like five o'clock this afternoon that it, it was discovered. Of course, it's always FA five o'clock. Um,but it gets discovered and, you know, I'm on call so I feel responsible for like, sticking around to until it's figured out, that sort of thing. It turned out that, we had some deploy automation stuff that was using like an outdated version of our configuration.

[00:01:35] **Adam:** So like not all of our code is multi-tenant yet. As there's a lot of things that are like, okay, this customer gets a copy and this customer gets a copy and this customer gets a copy, right? Like for a, a, not an EC two instance, a ECS instance sort of thing. And, or, or they get their own lambda function or something.

[00:01:52] **Adam:** And this particular feature, was a, a custom lambda per customer and the deploys, like we've been making code changes and deploying them and it just wasn't working for this one customer. And it turned out that, the deploy script was using a very outdated way to get the list of customers for which it should deploy the code.

[00:02:16] **Adam:** So it just didn't have these new customers. And so it was, it, it ended up being an easy fix, but it's like, you know, five o'clock in the afternoon, bug comes in, mail's not going out. This is a big deal. Like, ugh. So

[00:02:30] **Ben:** At least it's a Tuesday and not a Friday or something.

[00:02:32] **Adam:** yeah. Have you heard of the Friday trash?

[00:02:36] **Ben:** No.

[00:02:37] **Adam:** a political thing. So usually like when the government doesn't, you know, they kind of wanna sweep something under the rug.

[00:02:43] **Adam:** They have to announce it, but they, they wa they would prefer to people just not, not notice it, you know, like late in the day on a Friday, that's when they announce the stuff that they're hoping nobody pays any attention to. 'cause everybody just wants to go home for the weekend.

[00:02:55] **Tim:** The, the weekend news cycle kills it. It,

[00:02:58] **Adam:** So they called the, the Friday trash, but taking it out with the trash, so, yep, that's it for me.

[00:03:04] **Adam:** fortunately I got that fixed. It only took like a half hour, but, that's just, it's just a crummy way to end my day. So that's my failure.

[00:03:12] **Tim:** and yet you're still on time to record.

[00:03:14] **Adam:** You know, I'm getting better about that. I've got, they, they invented this neat thing. I've been wearing it. It's a, it's a special new device that they invented recently. It's called a watch.

[00:03:21] **Tim:** Really? Is that like a, is that like a phone,

[00:03:25] **Adam:** Yeah. It's like a phone, but you put it on your arm.

[00:03:27] **Tim:** really.

[00:03:28] **Adam:** Yeah. Except you can't make phone calls with it, and the apps all suck.so it, it's pretty much just like, it just tells time.

[00:03:35] **Tim:** Oh, okay. So it's just a simple form factor for time telling

[00:03:39] **Adam:** Yeah, yeah, yeah.

[00:03:41] **Ben:** When I,

[00:03:41] **Adam:** pretty well too? I haven't, I haven't had one

[00:03:44] **Tim:** Well that's

[00:03:44] **Adam:** messed up yet, so.

[00:03:46] **Ben:** when I was in fifth grade, a friend of mine had a wristwatch that had a built-in calculator and it, it

[00:03:53] **Tim:** I remember those.

[00:03:54] **Ben:** coolest thing I had ever seen in my entire life,

[00:03:57] **Adam:** My father-in-law still wears that. Yeah. Yeah. He, he was a, an engineer, and he had, you know, pocket protector flannel shirts and, and a. Wristwatch calculator and he still wears it. And I, every time I see it, I'm like, how is that convenient or like, easy to use. Right. It it, it's not that big. And you, you even, I, you know, there are people that have like big meat paw, you know, ev every fingertip is like a full, I don't know, centimeter or two in diameter, like the, at the thinnest point where you would touch something.

[00:04:32] **Adam:** I'm like, I, I don't have those hands. I have small pointy fingers and still trying to use that just looks like the worst thing ever. I don't understand. Maybe they do it with like a pencil or something, but,

[00:04:45] **Ben:** Do they have a calculator on the on the Apple watch? They

[00:04:48] **Adam:** not, I don't think so. Lemme

[00:04:49] **Ben:** What? Oh, missed nostalgic opportunity.

[00:04:53] **Adam:** there it is. Yep, it's there.

[00:04:56] **Ben:** I keep wanting to use a smart device to monitor my sleep, so a friend of ours has some, like a smart ring that you can wear that will monitor your, but my thing is, is I don't sleep particularly well, but I sleep very still, and so I'll get into bed and I, I, I'm, I'm up to four pillows now, so I have a pillow between my legs.

[00:05:17] **Ben:** I have a hugging pillow, I have an armrest pillow, and I have a head pillow. So I get into like the perfect position and then I just lay

[00:05:24] **Adam:** which one has the anime character on it?

[00:05:26] **Ben:** Just that's the body pillow. And but sometimes it might take me 45 minutes to fall asleep, but every time I have historically tried to use something to track my sleep, it always says I fall asleep in like two minutes.

[00:05:40] **Adam:** Yeah.

[00:05:41] **Ben:** So, but, but I think it would help me with my middle of the night thrashing, you know, that, that would gimme some insight into that, I'm assuming.

[00:05:48] **Adam:** Maybe like, I always wonder about that sort of thing. Like, okay, so you've, you've got all this data that says, yeah, you're, you're doing a job of sleeping at 2:00 AM to fix that.

[00:05:57] **Ben:** Can't even do that. Right.

[00:06:00] **Adam:** Yeah. You can't even do nothing, right? Yeah. I don't know. the, the one, the one of those things not sponsored that like has me, kind of Jones in and, and curious, like I kind of really wanna give it a try, is the eight sleep. because you can like, have it, have you heard of this?

[00:06:17] **Ben:** Oh, this is the bed heating and cooling

[00:06:19] **Adam:** Yeah. So it's like a, it's a kind of a mattress cover and it's, it's woven through with, with water.

[00:06:26] **Adam:** And so it can, it can heat, it can also cool and then you can use it as like an alarm.

[00:06:33] **Tim:** Ooh, it's a soy for your bed.

[00:06:35] **Ben:** Yeah, basically

[00:06:37] **Adam:** You can So feed yourself every morning. Yeah. Yeah. But you can have it, like, I, I think it might have some vibration stuff too, but you can have it like,

[00:06:43] **Tim:** How many quarters do you have to put in it? Get it right? If I can

[00:06:48] **Ben:** it, it's expensive, so it'd be very, very many quarters.

[00:06:51] **Adam:** yeah. It's a, it's a, there's a quarter subscription,

[00:06:54] **Ben:** Yeah.

[00:06:54] **Adam:** don't stop.but, I think, yeah, I think you can vibrate, I think, and you can have it like wake you up with temperature too, like get super cold or get super warm to wake you up or, or whatever. It's interesting. And, and in theory, if you do have trouble sleeping at 2:00 AM or whatever, you can say like, okay, always cool me off for that period, or always warm me up

[00:07:12] **Ben:** Oh, interesting. Yeah, I was looking into some of

[00:07:15] **Adam:** it's super

[00:07:16] **Ben:** a while back. 'cause I had gotten, I, you know, half of my Facebook feed is advertisements and at one point I was getting a bunch of, advertisements for the eight sleep, but then also for bed jet, which is like the cheap version of, it's not air conditioning, it's literally just a hose

[00:07:32] **Tim:** A fan

[00:07:33] **Ben:** blows.

[00:07:33] **Tim:** Yeah, it blows under the covers. Look, you got an AC split stuck on your med.

[00:07:40] **Ben:** But, there were people who were complaining, and I don't know if this was true for the eight sleep, but it was true for some of them where. Even after you get the physical product, you still then have to do a monthly subscription in order to get the app to work. And people were like, what? It's like it's a device.

[00:07:55] **Ben:** It shouldn't have a subscription.

[00:07:57] **Tim:** Everything's subscription based

[00:07:58] **Ben:** Ugh. It's crazy. But it is something I'm very curious about.

[00:08:03] **Adam:** Yeah. Alright, well that's enough waffle from me. What do you got going on, Ben?

## [00:08:06] Ben's Triumph

[00:08:06] **Ben:** I, I will also keep mind short because I think it actually dovetails with the show. So I had talked over several episodes about how I was working on this little side project as a learning experiment. I was thinking about permissions and data access and view rendering and all this jazz. And you know, I've also talked recently about how I've been suffering from a lot of anxiety and some depression.

[00:08:28] **Ben:** And I feel like some of that, not entirely, but definitely some of it was just heads down on this little side project and I wasn't getting a lot of joy out of it. It started to feel like grind. So I have put that on hold. I have started taking, I, I think I had mentioned a while back that I read the hypermedia Systems book, which is a book written by the, the creator of HTMX.

[00:08:53] **Ben:** So it's, it's like a part, here's what HTTP is really meant to do, and then also here's how it applies in the HTMX world. anyway, in that book he has, he walks the reader through building a contact app and kind of progressively enhancing with more and more of the HTMX features. so I am now taking that little app and I'm translating it into ColdFusion as a way to learn more about HTMX.

[00:09:20] **Ben:** And it's a very simple, it's a contact list, so it's basically like a list, detail, edit, delete kind of thing. It's a very simple app, but I'm trying to break it out into individual steps. So it's like, step one is just the ColdFusion and like step two is just installing HTMX and Boost deifying, the app.

[00:09:36] **Ben:** And like step three is adding, you know, this and that. Step four is adding, you know, another thing. Loading indicators, et cetera. And and I feel like just emotionally that has had a nice impact. I feel like I've, I've got that new relationship energy going with my new little side project and so, you know, failure that, I felt like I had to put my previous side project on hold, but triumph and that I'm feeling better about moving forward with some, some learning.

[00:10:01] **Adam:** Sometimes you just need something new, something different.

[00:10:04] **Ben:** Yeah,

[00:10:05] **Adam:** Your brain needs a different flavor to suck on for a little while.

[00:10:08] **Ben:** Exactly. And I think that'll be very relevant for our conversation. So I'll leave it there. And, Carol's not with us. She would've been next. So I'll kick it over to Tim. Tim, what do you got going on?

## [00:10:18] Tim's Triumph

[00:10:18] **Tim:** I've been, doing one-on-ones with, I've, I've taken on some more responsibility. I'm helping out Silver Vine as well as Pay Cloud. still have all my responsibilities from, from Pay Cloud, but just taking over, some of the lead, like the, leading development teams over at Silver Irvine. And there's a whole lot of people there that they've been hired over the past five years that I don't really know very well.

[00:10:41] **Tim:** So I've been doing one-on-ones with, starting with like the newest people and working my way up to. the long timers. I, me and one other guy we're only separated by about a few months. We're the longest tenured people in the company at, like, coming up on 25 years.but yeah, I've been doing one-on-ones with 'em, and it's, it's been nice, you know, I, you know, just try to set 'em at ease, you know, ask what their favorite book is or what their favorite fandom is, and just kind of get a feel for, you know, what, what do you like about what you're doing, what you know, what do you get excited when you get assigned to do, or what are the things that are holding you back?

[00:11:14] **Tim:** And just, you know, just, I, you know, there's no scoring here. There's no mentoring here. Actually, they're mentoring me honestly about, you know, who they are and what they do. Just try to get a feel for, you know, the, the mood of the company. 'cause, you know, you get these employee surveys that come through every, we get 'em like every quarter.

[00:11:34] **Tim:** It's like depending on how you slept that day, that, that survey, it can be good or bad. Right. but a conversation I think is really kind of helpful. And then some of 'em will tell me, yeah, I got the survey and this is what I put and here's what I meant. And I'm like, okay, well that's, that's helpful 'cause that's not what we heard.

[00:11:51] **Tim:** so, so just communicate, I think people under communicate.

[00:11:56] **Ben:** Yep.

[00:11:56] **Tim:** E even just 'cause you're having meetings doesn't mean you're communicating

[00:12:01] **Adam:** That's a good point.

[00:12:01] **Ben:** I mean, I know you talked about the fandom stuff to kind of get at

[00:12:07] **Tim:** Break the ice. Yeah.

[00:12:08] **Ben:** Yeah. Break their ice. But are there, more professional oriented questions that you like to ask everybody to sort of help them figure out how to open up, you know, to find the right words to,

[00:12:17] **Tim:** I, I, I ask them where they go whenever they're, they're stuck on something and you know, and I don't box it and I don't try to. Frame the question. 'cause if, if they just go to some other person in the company, then that's fine, but they like are going to a blog or a book or, you know, I wanna know that too.

[00:12:36] **Tim:** So I'm like, you know, whenever you're stuck, where do you, where do you go for help? Just some are like, yeah, chat, GPT or I go to Bo. Yeah, exactly. Penn Island. yeah, it, it, it talked to, you know, Bob over in accounting or something. So just finding out, just, just kind of where they go for work, when they're stuck.

[00:12:57] **Tim:** I think that says a lot about how they like to be helped, right? So if they say, yeah, I read a blog. Well, if they say that if they get stuck and come to me, I'm gonna send them an article.

[00:13:07] **Ben:** I got you. It's like you're learning their love language.

[00:13:10] **Tim:** learned, yeah. I'm learning how they want to work, right? I'm trying to take away friction from them in their job.

[00:13:15] **Tim:** we we're finding out a very common theme is that, that our, how we've set up our Jira is, is quite.a source of friction. Let's just put it that way. The, the Jira was set up in a way, and it's like everybody to a person is like, yeah, I don't understand this Jira. I have to review a ticket. Two people have to review each ticket.

[00:13:33] **Tim:** but then when I review it, I get added to the ticket and there's no way to remove me. So I get hundreds of emails a day about a ticket. I only thing I did was looked at it and said, yeah, this, it looks right and I don't care about this ticket. And I had to stop and check these and not accidentally delete ones that I do care about.

[00:13:49] **Tim:** And I'm like, yeah, that, that's a problem. And the way we're using epics and stories is completely wrong.

[00:13:56] **Ben:** Yo, that reminds me. I remember my previous job. I was getting dozens of GitHub emails a day because I, I must have been an administrator or some, some weird ranking where every time a PR was opened or a depend bot issue was filed, or permissions were changed. I was just getting emails for everything.

[00:14:19] **Ben:** So I finally started filing all of the GitHub emails into a folder, and I never looked at them. But then I, what I didn't realize until much, much, much later was there were actually other important emails that were kind of getting swept up into that filter.

[00:14:33] **Tim:** Like, Hey, you need to pay your bill.

[00:14:35] **Ben:** Well, it was other GitHub related things, but it was more like people specifically mentioning me or, or I, I didn't know what the right filtering was, but it's that, that alarm fatigue, you know, you

[00:14:45] **Adam:** there's, that's a very real thing. I will say I am our GitHub administrator or one of, and, I don't get that many emails from them. So there's, it's definitely a setting that

[00:14:57] **Ben:** Some, something was turned on and I didn't, I didn't know what it was. It's also, I, I have this thing and this, I don't know if this is just something that I haven't figured out yet because I haven't put in enough time to look at it, but I imagine, and I don't wanna put words in anybody's mouth here, but when I use GitHub, I use my personal email.

[00:15:19] **Ben:** But historically,

[00:15:20] **Adam:** a, yeah.

[00:15:21] **Ben:** when I've worked at a company, the company often has a GitHub organization. But the problem is, is now any interaction with me goes to my personal email and I wish I could say anything in this organization should go to my business email, not my personal email. But I and I have not been able to figure out how to do that.

[00:15:41] **Ben:** So, yeah, that's a been of a source of frustration for me. I, I do have, I guess you can have multiple email addresses on your GitHub account, and I think you might be able to set per repo which one it uses, or, yeah, it, it's definitely a thing. I would encourage you to look into it more. ask someone else, I was complaining this, and, and they said that they dealt with that by just creating a totally separate GitHub account for

[00:16:09] **Adam:** ugh.

[00:16:10] **Ben:** I'm like, that's doesn't feel like the right solution isn't, isn't this like a bajillion dollar company?

[00:16:17] **Adam:** Maybe like, maybe yes, maybe no. Does does GitHub have like an account switcher? Right? So like a lot of these,

[00:16:23] **Ben:** profile kind of thing.

[00:16:25] **Adam:** yeah. And so you don't have to like fully log out and log back in. If you can be logged into multiple accounts at the same time, I don't. If it has one of those, then that might be a great solution.

[00:16:33] **Adam:** But yeah, it, it is super annoying to like see, to look back at my company project, get history and see my personal email address all over a bunch of these commits before I figured out how to set my, work email address on, on work commits. But

[00:16:48] **Ben:** And you do that in the, at the get repository level or something.

[00:16:52] **Adam:** I'm not entirely sure

[00:16:53] **Ben:** It's like, I figured it out

[00:16:54] **Adam:** honestly, it's entirely possible that I'm using my work email address on my personal projects. But honestly that's like, that's less of a concern for me, you know?

[00:17:03] **Ben:** totally.

[00:17:04] **Adam:** So

[00:17:05] **Ben:**

[00:17:05] **Tim:** I was gonna tell you, Ben, though, that, Facebook just recently added a friend's tab, which

[00:17:09] **Ben:** Oh.

[00:17:10] **Tim:** No, they have, this

[00:17:11] **Adam:** know, and I'm laughing because it's ridiculous.

[00:17:14] **Tim:** which is great. I mean, it is ridiculous that. But it's like you, you click that. If you look at it on mobile, it's like you click your profile and like your groups and you'll see your friends.

[00:17:24] **Tim:** You click that. That's only the people you follow.

[00:17:26] **Adam:** Mm-hmm.

[00:17:27] **Ben:** Oh, interesting. So, okay, let me, if I can go off on one more tangent for a second. So, I had talked a couple of weeks ago, I think this may have been one of my triumphs, is that I had uninstalled, Facebook from my phone because I was, I was finding that I was just mindlessly scrolling through it while watching TV or sitting on the toilet or something.

[00:17:46] **Ben:** And then I felt like it was, it was making me not dumb, but like, I just, I felt like it was sucking time. So I uninstalled it, and what I realized is that. My intention was to only check it on the desktop. 'cause I'm on my desktop most of the time. So this seemed just like a natural thing to do. But I am such an out of sight, out of mind person that I ended up never checking Facebook at all.

[00:18:10] **Ben:** And I actually started to feel disconnected from people and I just recently put it back on my phone, but I've left it on the second screen, so it's not the first screen that comes up. So I still have to kind of actively go to it as a, as a kind of point of good friction. But it was just a really interesting moment of reflection where it's like, on one hand I kind of hate Facebook and there's a whole lot of Oz.

[00:18:35] **Ben:** you know, obviously like additional political meta information about all that kind of stuff. But, I also kind of like it, you know, even if I'm only keeping tabs on people in the most superficial way, in an almost, what do they call it, like a parasocial relationship, It's still comforting. Like it's still nice to see that,you know, like James Allen started a new movie, marathon Genre or, or you know, something like that.

[00:19:01] **Ben:** And, Adam just jumped out of a plane for the thousandth times. Something to that effect like that. There is the just like nice little, little blips of information to make me feel a little bit more connected to people. I was, I was definitely feeling more

[00:19:15] **Adam:** complete the trifecta, or Tim ate some new kinds of

[00:19:17] **Ben:** Yeah, exactly. Tim made some, some testes of a unknown origin.

[00:19:23] **Adam:** And Providence.

[00:19:24] **Ben:** Yeah.

[00:19:27] **Tim:** Mountain Lion.

[00:19:28] **Ben:** I don't know. That was just an interesting feeling for me. It was an interesting reflection. It's like, I wish there was no social media, but I also don't know what to replace it with.

[00:19:36] **Adam:** as a parent, social media is a very interesting thing, right? Like I feel like there's this whole class of ways to kind of screw up your brain. Not in like a permanent bad thing, but like, just like a, there's kinds of trouble you can get into and, and ways that you can kind of become extra lazy because of social media that we just didn't have to deal with growing up. And it, it adds additional challenges.

[00:20:09] **Ben:** Yeah, a hundred

[00:20:10] **Adam:** It's probably what our parents were saying about like frigging video games or something. Right? Like why don't these kids read a book or go outside?

[00:20:18] **Ben:** All right. Should we do this?

[00:20:20] **Adam:**

## [00:20:20] Staying Motivated in Long-Term Projects

[00:20:20] **Adam:** So I guess our topic for the day is long-term projects or maybe like long-term assignments. If you're, if you're maybe kind of feeling you've been at the same company for a very long time and, and you're not necessarily sure if it's time to move on or not, like how do you just stay motivated doing the same thing for a long, long time?

## [00:20:37] What Makes You Feel Whole

[00:20:37] **Adam:** Ben, I think, I think it was you who wrote this, that, that seems like a very Ben line. What makes you feel whole?

[00:20:43] **Ben:** What makes you feel whole? So when I, when I wrote that down, what I was thinking about was, what is it in the work itself that makes me feel good about myself and good about the work and good about life? And I think so much of what I enjoy in project work is doing work for somebody, you know, some type of customer, whether it's an external customer like a university or fundraiser, or if it's internal customer, like another developer that I'm trying to make his job or his life a little easier.

[00:21:18] **Ben:** There's, I, I feel like I have to have somebody that I can look at and say, here, I did this for you. And they can look back at me and say, awesome, this is gonna be really helpful.

[00:21:32] **Adam:** that definitely gives me a spike of, of endorphins of, you know, like. If that was worth the, the last three hours working on it, the last three days or three weeks working on it.

[00:21:43] **Tim:** Ben's Ben's theme song is, can anybody find Me Somebody to Love?

[00:21:49] **Ben:** it's true. Like, this is the eternal debate that I have in my head, or the battle that I have in my head where it's like, I know that. In an ideal world, all of my validation can be internal. Like I could just do good work and be proud of it, and that is enough, but like, it's just not enough. I, I, I need to see someone be pleased with the work that I'm doing to feel like my time means something.

[00:22:14] **Adam:** Yeah. Like, and, and it's gotta b for the right reasons too. Right. So like, just because your boss comes and says, oh great, you, you did a really good job copying column A into column B in this spreadsheet all day, every day for the last six weeks. I, there's gonna, that's great. It's amazing work. I'm so proud of you.

[00:22:32] **Adam:** Like, that's not gonna be fulfilling anyway.

[00:22:34] **Ben:** Yeah. Yeah. Right. It has to be genuine. It has to be genuine and

[00:22:38] **Adam:** Well, I mean, even if it is genuine, like if it's just stupid menial, like a monkey could do it kind of work, like that's still, at least for me, that that's not gonna be motivating at all.

[00:22:51] **Ben:** sorry, there's.

[00:22:52] **Tim:** no one, no amount of validation could have me become an accountant.

[00:22:59] **Adam:** Especially not considering the grades I got in my accounting classes in

[00:23:01] **Tim:** Right.

[00:23:03] **Ben:** so along the same lines, the, I think the validation is important and I think that ultimately I wouldn't be super motivated without some level of like doing this for somebody. Right. Somebody, somebody needs the thing I'm working on because what I'm about to say would be boring if it was. Just because that was the only reason, like I'm, I'm doing the thing for the reason, but I feel like I get more pleasure.

[00:23:26] **Adam:** Like, great. It was for somebody, they needed it, it was useful. I'm glad to have done that for them. But where, where I get more endorphins from is figuring out a hard problem, trying new technology, doing something, maybe somebody no, nobody's ever done before. like that sort of thing. The, the, the work that I do, right?

[00:23:47] **Adam:** I, I work for a company that provides software and services for colleges and universities, primarily around alumni engagement and advancement, which is a fancy word for please give us your money. and not us. The, the colleges, they're, they're the ones that call you a dinner dime and ask for money anyway.

[00:24:05] **Adam:** work in itself doesn't necessarily speak to me. I wouldn't like seek out working in that vertical. However, it has presented amazing challenges. I, I love my coworkers and I love the, the technical challenges that we get to solve, and so it has worked out to be amazingly fun and rewarding for me to work here.

[00:24:27] **Ben:** Yeah, absolutely. And and I think I would also add, I would color that to say that when you're doing that type of work for somebody, it also helps temper and focus the efforts. You know, and I think this is when I was talking about how I just stopped one side project to work on another side project. I think part of that was the problem is that because I wasn't really doing it for anybody, I didn't know which rabbit holes were safe to go down and which rabbit holes weren't valuable.

[00:24:55] **Adam:** Mm-hmm.

[00:24:56] **Ben:** when, at the end of the day, I know I'm trying to deliver value for somebody specifically, I can pick and choose my battles a little bit. You know, I can say, Hey, this is an exciting problem to work on, but I can't spend three months working on it. I could spend a week working on it. So like, where do I, you know, scope out my efforts in that context?

[00:25:14] **Ben:** And there's, and I, and that's, you know, that's as much a value add for me as it is for the person I'm building for.

[00:25:21] **Adam:** For sure.

[00:25:22] **Tim:** What if there's just a big, if it's a big project, there's a big distance between you and the actual people you're creating it for, right? So you're in a big company and there's, there's, there's groups of people that they talk to the customer, and all you do is just receive, you know, some stories in an epic and some tasks.

[00:25:40] **Tim:** I mean, how, how do you find motivation that way? If you can't know exactly what it is you're doing for this, these imaginary people.

[00:25:51] **Ben:** I, I think that is tougher. I think that is genuinely tougher to do. I, I would hope that I could find some, something to connect with that it's not just pulling tickets off of a Jira board and moving them across the Kanban. but like, if there's, you know, if maybe I have to lean more on my project manager to kind of get validation from him or her or somebody, or feedback from the clients, even if I'm not directly talking to them.

[00:26:17] **Ben:** I, I, I think I would need something. I don't think I would be very healthy in a situation where I was really completely disconnected from the, the end user.

[00:26:24] **Adam:** Yeah, I mean, this might be where you start to have to just embrace the suck,

[00:26:28] **Ben:** Yeah. Yeah.

[00:26:29] **Adam:** you know, sometimes it's just gonna be a grind and there's nothing fun about it. And I guess hopefully in those situations it's, finite, right? You can, you know where the, the endpoint is. I have to copy 10,000 rows one at a time in this Excel sheet from column A to column B.

[00:26:45] **Adam:** and okay, you know, it is 10,000, so I know there was a stopping point and I can set like mile markers, right? I can say, okay, 5,020 500 and, you know, every 500 or whatever. Just like chip away at 'em. But yeah, sometimes there's just no, there's no motivation to be had. You just have to do it.

[00:27:04] **Ben:** There's a video from this guy, Zay Frank. I don't know that much about him, but I think he was like a really early innovator in video publishing and, and like internet

[00:27:15] **Adam:** was doing online video before there was YouTube.

[00:27:18] **Ben:** Yeah. And he has this one video that I think I learned about from the Ruby Rogues podcast possibly. Many, many years ago, and it's a video called Invocation for New Beginnings.

[00:27:29] **Ben:** And it's, I think it's like something he kind of says to himself when he's getting ready for a project and there's one line in it that says something like, work isn't just a series of stepping stones, but if it is, let me become fascinated with the shape of the stone. And you know, it's a lofty thought, but the hope is, I think there, if I can interpret it, it's that to Adam's point, sometimes stuff just sucks.

[00:27:57] **Ben:** And hopefully there's something in the ery that you can find Fascinating. Whether it's I learned some new key combination that makes this one step easier than copy pasting a thousand rows or something. Or, you know, maybe I take a little side tangent to, find a way to write a macro that helps me do this.

[00:28:16] **Ben:** Or like something that takes some of the ery out of it and makes it a little bit more interesting and a little bit more fulfilling.

[00:28:24] **Adam:** yeah, for sure. Well, do we wanna talk about like, so obviously sometimes there's just no, no motivation to be had. You have to embrace the suck, but most of the time hopefully there's, it's possible to get motivated. So should we talk about some techniques? Mm-hmm.

## [00:28:39] Breaking Down Tasks

[00:28:39] **Ben:** Yeah. I, I am most motivated by action and motion. So, for me what that means is always breaking tasks down into smaller tasks. you know, even where one of the tasks is break the rest of these tasks into smaller tasks. You know, like the, the, The, it is like the check the checklist where the last item or the first item is like, make checklist, you know, like I need to have some sense of progress, some sense that I'm moving forward and the more granular I can make my actions, the more I feel like I can check things off and have a sense of progress.

[00:29:15] **Ben:** That's a, that's a huge motivator for

[00:29:17] **Adam:** And I, I feel like too, sometimes projects that are gonna be long term are overwhelming because they, you, it's hard to fit it all in your head, right? Like this skydiving app that I've been working on, I was a very similar situation to what you're talking about. Like create a checklist. First item on the checklist is create checklist.

[00:29:34] **Adam:** And I don't c check it off until like I've just emptied my head. This is everything I'm thinking about. Totally unorganized, just like out into a, a checklist. And the nice thing about that approach is then like, as you think of new stuff, it's like, oh yeah, I need to make sure I do this. You just put it on the checklist and that way you don't have to continually keep it in your head and worry that you're gonna forget something.

[00:29:55] **Ben:** Right. Very, uh, getting things done, kind of a strategy.

[00:29:59] **Tim:** It's one thing I do like about the whole epic story, mode of creating work, units of work. So you have an epic, which is basically, basically the entire project and it kind of describes what the reason of being for that, that whole project. And then you got the individual stories from the user's perspective.

[00:30:20] **Tim:** And I wanna be able to see a screen that does this from a backend architect's perspective. I should, this should be done as a, you know, all the different stories that make up that Epic. And then any of those.

[00:30:30] **Adam:** I should have a direct line to your

[00:30:32] **Tim:** Exactly. A hundred percent. And then, You know, having the individual tasks that make up that, each of those stories so you can sort of, if you look at it as, as a, like a book, right?

[00:30:42] **Tim:** So you're, you're telling a story about this thing that you're building and here's all the chapters in it and here's all the sentences in it. And as you complete those, you can sort of see that story starting to take shape. The problem is that most time with the projects, you start with what you think is a very simple story of an epic, and then it just cont, you know, you start working on these things and then the pit never ends, right?

[00:31:07] **Tim:** It just, you're adding more and more. You're, you find things out, you're like, oh my God, well we need to add this, this and this, and this thing that we worked on. This part of the story was completely wrong. We totally misunderstood that. So we gotta yank all that out. That's when it starts to get frustrating when there's, as long as there's some linear growth to it and you're like, yeah, I could see that's where things are going, but that's usually not how projects work.

[00:31:28] **Tim:** It, they're chaotic and so there's a lot of stop and start, and. Starting and rega. All right. What are we doing here again, let's, we can either, what, what do we, what's, what do we, what do you say we do here?

## [00:31:41] Using Jira

[00:31:41] **Ben:** Well if, if I could take a small tangent quickly for a second because we're

[00:31:45] **Tim:** We've never stopped you before.

[00:31:46] **Ben:** stopped before, Eddie. 'cause you're talking about creating epics, creating tickets, and I was listening to an interview the other day, and as happens so many times, someone brings up Jira. Only for everyone else on the podcast panel to crap on how terrible Jira is.

[00:32:03] **Ben:** And you know, it's just the thing to do. And I've used Jira a couple of different times now, and my experience with it has actually been fairly positive. Where I find that I don't have a good experience is not because of Jira itself, it's because someone is trying to use all of the features of Jira and adds a lot of friction.

[00:32:26] **Ben:** And it, it reminded me of back when I, I read like the headfirst design patterns or you know, like any kind of patterns book for programming. And then suddenly you wanna apply every single pattern that you can in your next application. And all it does is make development so much harder because half the patterns aren't relevant.

[00:32:45] **Ben:** You know, the other half you didn't really understand well enough to apply in the right ways. You just create a lot of friction for yourself. I think if you treat project management systems like glorified to-do lists, they're actually pretty great. It's when you start having all of these, I think, highly constrained control flows and like, this has to go to this before it goes to this.

[00:33:07] **Tim:** You can only have so many things in this column, but like only certain people can move from this com to that com and then like other people have to move from this com. That com. You're like, yeah, of course. No one's gonna enjoy that. That sounds awful. It's just a to-do list. So I think, you know, kind of tangential there, but no, I agree with you a hundred percent. It people poo poo on, on Jira, but it's like, it's, it's usually how, it's just a tool. It's, it's how you implement it, right? People start creating, you know, they're like making it do things that really wasn't designed to do, or trying to create insights into things that they thought were important.

[00:33:44] **Tim:** And then they actually get the report and then they're like, oh, this doesn't actually tell me anything. And, but yet that artifact that they created now stays around and there's these, these statuses that you have to go through to get to the next status. And no one's like even understands, well, why do we have to go through, I don't know.

[00:33:58] **Tim:** I'm just clicking it so I can get to the next spot. Right.

[00:34:01] **Ben:** We had a workflow one time where it's like we had, we had several columns where you had like to do in progress and then ready for review, I think. And then once something went into ready review for review, you couldn't move it back into the in progress column. You actually had to move it all the way back to the to-do and then, so you could move it forward.

[00:34:25] **Ben:** And like, it's just a configuration that someone did somewhere, but it, you know, can only be changed by an admin and nobody knows who the admin is anymore because the person who set up the workflow no longer works at the company. And you're like, like all all like, why? Like you didn't have to do that feature.

[00:34:42] **Adam:** Hmm.

[00:34:43] **Ben:** anyway, I wasn't really going anywhere with that specifically other than to say, where possible remove friction

[00:34:51] **Adam:** Yeah.

[00:34:52] **Ben:** to make life more enjoyable.

## [00:34:54] Stay Curious

[00:34:54] **Adam:** Yeah. I guess another one for me would be to like, stay curious, right? So, it, it depends on what kind of work you're doing, right? If it's like, here are 10,000 tasks and they're all exactly the same and you have to do that, then there's not a whole lot of opportunity for curiosity there. But if it's like, you know, solve this list of problems and they're all gonna be different and unique, then you know, it gives you an opportunity to.

[00:35:15] **Adam:** Dig in on maybe parts of the language that you're not super familiar with or you know, like new data structures or something like that. Right? Like, think of it as an opportunity to learn something.

[00:35:27] **Ben:** Yo. A hundred percent. A hundred percent. Case in point I, I worked at this company called Nylon Technology, and we built a lot of data management system for law firms, which basically consisted of them exporting an Excel spreadsheet that had like 75 pages worth of poorly formatted data into a CSV file, which then had poorly formatted all kinds of stuff.

[00:35:52] **Ben:** And then we had to figure out how to. Massage that into SQL insert statements. So we could do this sort of data import thing. And you know, you could look at that and say, that sounds like the most tedious, awful work imaginable. but it was where I learned regular expressions because I was just trying to figure out how I'm gonna parse this data and how I'm gonna pick fields apart.

[00:36:14] **Ben:** And you figure out how to do an iterative process, you're like, all right, well, you know, like this little pattern here is constantly wrong. So is there a way that I can do one pass just to fix that stuff, but not actually export any data? And then like, okay, now that unlocks a whole lot of other pattern matching that becomes much easier.

[00:36:29] **Ben:** You are like, you make it an interesting problem even though it is insanely tedious and boring, but you, you find the exciting parts of it.

[00:36:39] **Adam:** Yeah, for sure.

[00:36:40] **Ben:** Plus regular expressions are awesome. It's funny, you know. This is the, the, whenever I complain about AI these days, that's, that's like one of the go-to things people talk about. They're like, oh, it's so great. I just type, you know, give me a regular expression for such and such and it, and it knocks it out.

[00:36:57] **Ben:** And I'm like, no, you're going the wrong way.

[00:37:01] **Adam:** Now it's a regular expression that can't be read or written.

[00:37:07] **Ben:** Oh yeah.

## [00:37:08] Pomodoro Technique

[00:37:08] **Tim:** Have you heard of the Pomodoro

[00:37:11] **Adam:** Yeah.

[00:37:12] **Tim:** technique is just basically, you know, you

[00:37:16] **Adam:** on a tomato.

[00:37:17] **Tim:** yeah. Yeah. You have a little, you set thing, you set you kind of time box things. You'll set like 25 minutes to work on a task and then take a short break so that, that breaking things up. So that, 'cause I think that sometimes wears you out is if, if you are into, into the project and you just don't work on it, don't stop working on it.

[00:37:39] **Tim:** I mean, so taking breaks, you know, keep your mind fresh. Sometimes burnout is just you, you could be, you know, be enjoying your work, but gotta, you gotta reset your brain every now and then. We're not, we're not, we're not machines.

[00:37:54] **Adam:** that just unlocked a couple of ideas for me too.

## [00:37:57] Getting Out

[00:37:57] **Adam:** Like, sometimes, especially if we're doing work that's like embrace the suck, you can improve your mood getting through it by changing something about like your working environment, right? So we are all fortunate enough to be working from home, but even if you're not like a work from home person, maybe your office has like an outside area that you can go sit in or you can do, like, I'm gonna work the first half of the day at my, the, the Starbucks on the corner.

[00:38:22] **Adam:** Right next to our office or whatever. And just like moving yourself physically to a different space with different sounds and different, you know, maybe a more comfortable chair or something is, often just a, you know, just tweaks your mood, makes it possible to get through the day. you know, I'm working remotely, but early on in our company, one, this was the first time I'd ever worked full-time remotely.

[00:38:44] **Adam:** Like I, at previous jobs, I'd worked from home like two days a week, three days a week, something like that. Or maybe for two weeks on end or something. But I started doing this full-time and pretty quickly started to run into cabin fever. it just was, I was not used to not leaving the house, and so I got into this habit.

[00:39:01] **Adam:** There's a airport near my house and I would go. The, the airport has a restaurant in it. It's not a very good restaurant. It's a bar. And, and you can get, like, anything that they can freeze and ship you, they'll, they'll microwave it for you, right? Like you get a, a hamburger that's been frozen and, and reheated or french fries that were frozen and reheated sort of thing.

[00:39:21] **Adam:** but I would go and I would sit there and I'd work and, you know, being a super small company, Steve didn't give a crap if I had a beer or two while I was there working. So I'd go like, sit at a bar all day and work and, and you know, it was kind of just neat. Like every now and then planes would take off for land or whatever, be outside of the house listening to music that I'm not in control of.

[00:39:39] **Ben:** Hmm.

[00:39:40] **Adam:** you know, people walking by just a good way, a good change of scenery, change of pace.

## [00:39:46] Music

[00:39:46] **Ben:** Well, music is also an interesting aspect of work too, because. In my mind, I always want to be able to work consistently with the same type of music. But what I find is that there's just certain types of thinking and certain types of activities that don't work well for all kinds of music. And I can, instead of fighting that, I find it's nice to lean into sometimes, like if I'm gonna do deep work, where I really have to think hard, probably what I'll put on is something like a classical music or a,

[00:40:14] **Tim:** Gregorian

[00:40:15] **Ben:** Gregorian chant.

[00:40:16] **Ben:** Yeah, I love it. Those are like my two in my Pandora. Those are the two stations that are actually prefixed with a dash, so that they're always first alphabetically.

[00:40:23] **Adam:** Your Spotify rap is just like a big shrug emoji, isn't it?

[00:40:26] **Tim:** Yeah.

[00:40:27] **Ben:** But you know, if I'm doing stuff that's a little bit more mundane and a little bit more repetitive, I'll put on something a little bit more poppish or you know, something with more lyrics. Sometimes I'll even put on a, like a presentation and leave it on in the background just to hear somebody else talking.

[00:40:44] **Ben:** so, you know, you can, you can lean into those kind of shallower thought workflows to, you know, dribble in a little bit of extra information that doesn't necessarily distract, but is, is entertaining in a different way, perhaps.

[00:40:57] **Adam:** I used to use an app called cotivity, like Coffee productivity.

[00:41:02] **Ben:** Oh, this is like the sounds of the coffee shop kind of

[00:41:04] **Adam:** Yeah. Yeah. It was like, so, I think it had some white noise stuff built in too. But the, the main thing was like, it was like a, I don't know, two hours, something like that recording of just being in a busy coffee shop and you could like tweak it.

[00:41:18] **Adam:** You could say, I want, you know, a city coffee shop versus, I don't know, rural or, or. I guess rural places don't really have that many coffee shops, but you, you get my point. Like, there, there's different, different coffee shops you could be in, and some of 'em are more bustling, some of them are, you know, whatever, more, more chill.

[00:41:34] **Adam:** And it just, it kind of tricks your brain into thinking you're there. Right.

[00:41:40] **Ben:** I, I, I had one like that. This is gonna sound ridiculous to say out loud, but it was cat purring and you could, and you could modulate like the intensity of the vibration and the volume and like, whether there was a modulation in the purring. And then like,

[00:41:56] **Adam:** It's just a, this still a thing

[00:41:57] **Ben:** lemme see. Hold on. Let's see.

[00:41:58] **Adam:** because, I don't,

[00:41:59] **Tim:** How many hair balls it coughs up.

[00:42:02] **Adam:** I don't know that I would necessarily want this, but I'm absolutely certain that my kids would love

[00:42:06] **Ben:** Oh no, it's, it was so great. Let's see. Is it, is it, I think this is it. I'll put it in the, it's called purley, P-U-R-R-L i.com. And you can adjust. You can adjust. How Sleepier happy. How steady or lively the pur out, how relaxed or overjoyed close distance like, it kind of just puts you into this meditative state.

[00:42:34] **Ben:** It's this like vibration. I, I don't know. Vibrations are so fascinating to me. In general, they say that, part of why cats heal so much faster than other animals is because of the purring, the, the vibration itself. I mean, I don't know if there's like real science behind this, but this is at least a theory,

## [00:42:50] Graph

[00:42:50] **Ben:** I did have one other thought, which was that I get a lot of joy from seeing something graphed. And

[00:42:59] **Adam:** Oh

[00:43:00] **Ben:** know, like let's say you're working on some sort of new checkout flow for alumni queue and you know, you just put one metric, like someone click this button. And I can't tell you how excited it is to see, even if it's infrequent, it'd be like once a day or once a week.

[00:43:17] **Ben:** You know, you, you get to work Thursday morning, oh, there's a bar on that graph suddenly and you're like, oh yeah, that's, someone did that. Someone just used something that I built. And it's, it, it's, you know, talk Tim, when you talked earlier about how, like what if you work at a company where you're actually quite a number of steps removed from the customer.

[00:43:34] **Tim:** You know, if you can graph something that kind of gives you that tangibility of the application, kind of exposes the, the pulse of the system, that can be super, super validating and very motivating.I didn't think about that.

[00:43:48] **Ben:** Adam just posted some beautiful, they,

[00:43:51] **Adam:** I, so you were talking about graphs and I was like, oh, I love a good graph. Like, even if it's, just like kind of monitoring the stuff that, that's going on, it's not even your progress, it's just nice to have, like, it's, it shows that the, the work that you're doing is valuable, right? Even if it's not show, if it's not visualizing the progress that you're actually making, which is.

[00:44:12] **Ben:** Yo and I can't. So, so we talked earlier, we talked on previous shows about how Envision was shutting down and it was shutting down over the course of a year, and we were constantly sending out notifications that we were shutting down and people should come in and get their data. And I can't tell you how much satisfaction I got looking at these graphs.

[00:44:30] **Ben:** And you, you know, you slowly see that all the traffic start to tick down because people are leaving the system. But like, it was still that sense of like, oh, these are my ride or dies. Like, these guys are going off the cliff with us. You know, we're gonna Thelma and Louise this on December 31st. It was so, it was just so heartwarming to see activity in the system, you know, people using it.

## [00:44:59] Buyers Remorse

[00:44:59] **Tim:** one danger I I think I see in, in long projects is, you know, we always should be learning new skills and technologies and techniques and things, but I, I think sometimes there's like, you get this buyer's remorse once you've like start or you architect something, you start working on it and you get like 80% through the project.

[00:45:21] **Tim:** You're like, oh man, we really should have done X instead of Y are used this technology. So in your mind, do you think it could have been so much better and in that. If it's a really like, you know, multi-year project, you might think, well, we got time, we can squeeze it in. And then you just multiply that times everyone else who's just really, what they've got is fine.

[00:45:46] **Tim:** They're just like bored with it and they're like, it would've been so much more fun doing it this way. Well, you don't know. You probably would've got bored with that too. But I, I think that is a, a, a pothole that people can, can run over. Is that in an effort to try to keep things exciting? They're like, oh, we should, you know, change the tire of this thing while we're driving it.

[00:46:05] **Tim:** that'd be great.

[00:46:07] **Adam:** Have you ever seen that done?

[00:46:08] **Tim:** I have actually, yeah.

[00:46:09] **Ben:** Is that a thing? That's a thing you can do.

[00:46:12] **Adam:** Yeah. So I've seen videos and I think they're just doing it to, to show off. Right. Showboating. But like, it, it, it, I I'm probably gonna whatever, somewhere in the Middle East, let's just say there. Right. I wanna pick a specific country and like be a mean bad person or something. But I've seen people that like, it's a thing they'll like go out and they, they kind of just jerk the wheels their cars up on two wheels, like on the right side.

[00:46:33] **Adam:** Right. Drivers, drivers in the air, kind of balancing onto on the two wheels. And then like, somebody in the backseat like kind of jumps out on the, on the side of the car and like tire iron, take the wheel off, put it in the seat, and they hand another one out and they put the, the tire on and, and tighten it on.

[00:46:49] **Adam:** And then they just, obviously after he climbs back in the

[00:46:51] **Ben:** bonkers, that that's even possible.

[00:46:54] **Adam:** Yeah. It's bananas.

[00:46:56] **Ben:** That's like, isn't there a, there's a car race where you drive across country, right? And you have to make it in the least amount of time.

[00:47:04] **Adam:** Oh, Cannonball run.

[00:47:05] **Ben:** Is that what it is? Can you, what? Is that a, is that, no, but isn't that a, I think it's a real race. I mean, I don't know if it's a cannonball run, but I think this

[00:47:15] **Tim:** talking about the DA car, like the one where it goes through the desert?

[00:47:18] **Ben:** No, no.

[00:47:19] **Ben:** I think they, is this, am I

[00:47:21] **Adam:** you, the, I mean, there's a TV show, the Amazing Race, which is

[00:47:23] **Ben:** No. Speed. Race across country in car. Well, okay, so Wikipedia says it's the Cannonball Run challenge. I don't know if this, I.

[00:47:33] **Adam:** inspired by the movie, but yeah.

[00:47:35] **Ben:** Yeah. Yeah. So maybe it's inspired by the movie, but that seems like something you could do there where you don't wanna stop 'cause you're literally racing for minutes.

[00:47:43] **Adam:** Right.

[00:47:43] **Ben:** Sounds

[00:47:44] **Adam:** it sounds like, yeah, it kinda sounds like we're about ready to wind down. I, I do wanna say before we get outta here, especially Tim brought up, you know, getting bored with stuff, there's a phrase that I love, which is, the grass is always greener where you water it

[00:47:57] **Tim:** Mm-hmm.

[00:47:58] **Adam:** so you know what, what you're paying attention to, what you're taking care of, what you're investing in, that's where it's gonna be the best.

[00:48:04] **Adam:** Even if it's on old technology.

[00:48:07] **Tim:** Yep.

[00:48:08] **Ben:** Heck yeah. jQuery UI is still getting it done.

[00:48:12] **Adam:** yeah. I'm gonna need to see you in my office after this podcast.

## [00:48:16] Patreon

[00:48:16] **Adam:** Alright. this episode of Working Code is brought to you by, wait. What's that? JQueryUI? Uh,okay. and listeners like you, if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:48:30] **Adam:** Our patrons cover our recording, editing and transcription costs, and we couldn't do this every week without them. Special thanks of course to our top patrons, Monte and Giancarlo. You guys rock.

## [00:48:38] Thanks For Listening!

[00:48:38] **Adam:** we're gonna go record the after show. I have a big question for these other gentlemen and I'll share mine as well.

[00:48:43] **Adam:** I'm gonna ask what's on your home screen on your phone? Ben brought up earlier that, he doesn't have Facebook on his, on the first screen of his phone anymore. So that just made me wonder, like, let's, let's get into it.

[00:48:53] **Ben:** Let's

[00:48:53] **Adam:** gets pride of place for sure. and then we will, we'll laugh at Ben's notification counts. Um,if you wanna get that, and all of our other after shows, you can do that by going to work,patreon.com/workingcodepod and become a patron of the show. We'd love to have you on board.I'm also gonna go ahead and shout out our discord. it's been popping off lately. A lot of, a lot of new people joining.

[00:49:16] **Adam:** I'd love to have you join up as well. Great place to hang out, stay motivated, talking to other of your, of your peers

[00:49:21] **Ben:** Oh, wait. Oh, oh, wait. Before we leave, thinking about Patreon people, Tim, you met up with Mingo.

[00:49:27] **Tim:** I did. Yeah. Yeah.

[00:49:28] **Ben:** very exciting. That was cool. I saw that you posted the picture or he posted the picture of his, his van or not van truck with the mounted sleeper.

[00:49:35] **Tim:** Took him to Waffle House. Yep. As far as he'd never been to Waffle House before. So yeah, he got the Waffle House in the, in the middle of the afternoon. Got to walk around his camper, see, see where they're living. So yeah, it was pretty cool. Nice to meet them. They're really nice folks.

[00:49:48] **Adam:** Did anybody like throw a chair or,

[00:49:51] **Tim:** No, no. This was sober time at Waffle House.

[00:49:53] **Tim:** It was. It was. It was fine. We, it wasn't, it wasn't 2:00 AM after a concert, so we were good. We were good. Everybody, everybody behaved themselves. Everyone even had shoes on. That was great.

[00:50:05] **Adam:** Oh, okay. That's going to do it for us this week. We'll catch you next week, and until then,

[00:50:10] **Tim:** Remember, you're our favorite flavor for our brains, and your hearts matter.
