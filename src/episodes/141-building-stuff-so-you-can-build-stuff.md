---
title: "141: Building Stuff So You Can Build Stuff"
description: "Inspired by an article from 'Dimitri Glazkov: Build a thing to build the thing', we talk about the importance of consuming of our own products."
date: 2023-08-23
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/141-building-stuff-so-you-can-build-stuff/id1544142288?i=1000625378187"></iframe>

Inspired by an article from [Dimitri Glazkov: Build a thing to build the thing][dimitri-glazkov], we talk about the importance of consuming of our own products. Often referred to as "Dog Fooding", this means that we must try and build something in the same way that _our customers_ would be expected to build something. And, in doing so, better identify the feature gaps and the points-of-friction. In order to best meet our customers _where they are_, we have to - in a sense - become our customers.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[dimitri-glazkov]: https://glazkov.com/2023/08/03/build-a-thing-to-build-the-thing/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/141-building-stuff-so-you-can-build-stuff.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** Anyway, one of the other attendees at the workshop, his company was building an Ecommerce platform.

[00:00:06] **Ben:** And in order to make sure that the Ecommerce platform worked, they decided to build an online store as, as a demo site,

[00:00:13] **Ben:** so he's like, Oh, here's a, here's an idea. We'll make a gluten free bread online shop and he said it became so popular that they ended up making more money from selling the bread out of this bakery than they did from selling the Ecommerce platform itself.

[00:00:28] **Adam:** And I bet you the baker was happy too.

[00:00:30] **Carol:** Yeah. Win win for the whole community.

## [00:00:52] Intro

[00:00:52] **Adam:** Okay, here we go. It is show number 141 and on today's show we're going to talk about building stuff so that you can build stuff. Which, I don't know how we could possibly be more specific than that. But first, as usual, we're going to start with our triumphs and fails.

[00:01:04] **Adam:** Ben couldn't be with us tonight, so it's just the three remainders. sorry? Sorry, not sorry? I don't know. But, yeah, so why don't we start with you, Tim?

## [00:01:13] Tim's Triumph

[00:01:13] **Tim:** So I'm going to go with the Triumph this week. Uh, it's, you know, it's not, I guess it is kind of my Triumph. Well, me and my, my wife, but, it's not like a work Triumph, but, raising some coders. Right. So my son, my son, Max is, you know, college about a year and a half now. And he's, he's getting to his real core classes, of like programming and stuff.

[00:01:35] **Tim:** So he's like intro to, web development, intro to programming, things like that. And because of just all the, you know, stuff he's done in the past, he's took a Harvard. Online course and got a certificate for that. Cyber security stuff. It's like, so he's taking these classes. He's like, yeah, yeah. So learning HTML and Python.

[00:01:57] **Tim:** He's like, I've known that since I was 12.

[00:02:00] **Carol:** Yeah.

[00:02:02] **Tim:** So he's pretty bored at class. It, I feel bad for him. Cause it's like, I, I, he can handle being bored a little bit more than I can. When I get bored, I get destructive.

[00:02:10] **Carol:** Oh yeah.

[00:02:11] **Tim:** but yeah, he's, he's, he's a good kid, but yeah, he's. He's, and he's never made below a 95 on any of his classes.

[00:02:18] **Tim:** And he's, he's, he's taking a full load. I mean, this, this last year and this year, he's like going to school from nine in the morning to 5 PM and just really every day, but Friday. And then, working in the evenings, on Friday and Saturday. So

[00:02:32] **Carol:** Oh wow.

[00:02:33] **Tim:** it's just proud. It's like, he's like, yeah, I got this.

[00:02:37] **Tim:** This ain't hard. He's waiting

[00:02:38] **Carol:** Piece of cake.

[00:02:39] **Tim:** Piece of cake. He's the ones he's is enjoying is like calculus. So he's taking, he's taking the college calculus and really enjoying that. So yeah, just, just like, you know what we did okay. I didn't force him, you know, I introduced it to him. He took to it and then stuck with it himself.

[00:02:55] **Tim:** So it's like. Trying to find that balance of encouraging your, your children to, to do something of value without being a helicopter parent. So maybe we did okay. We'll see.

[00:03:07] **Carol:** I mean, it sounds like you did pretty good.

[00:03:10] **Tim:** So I, I think he, maybe he might do a minor in, do a ma a major in software development and a minor in cybersecurity.

[00:03:18] **Carol:** Ooh, that's cool.

[00:03:19] **Tim:** So

[00:03:20] **Adam:** on this course, you can just ride his coattails all the way into the grave, man. I

[00:03:24] **Tim:** for sure. So yeah, I was just, just super proud of him and, that's me. How about you, Adam?

## [00:03:30] Adam's Failure

[00:03:30] **Adam:** have a somewhat work related fail. for, I don't know, a couple of weeks now, I've noticed there's the slightest bit of flickering in my, my primary monitor, I so I have a laptop and I have a couple of external monitors and the one that's like directly in front of me and it's big and it's expensive and it's curved, is, it's now significantly flickering. So I feel

[00:03:53] **Carol:** Is it older?

[00:03:54] **Adam:** I bought it in like May of 2019. So it's not that old.

[00:03:57] **Carol:** that old. Yeah.

[00:03:59] **Adam:** you know, I feel like the whole tech industry, like gadgets, don't last as long as they used to, right? When we were kids, you'd get a monitor and you'd have it for 15 years.

[00:04:09] **Adam:** And there was like, that was the normal. Right. And I think we went through a few years, like as we were switching to LCD and then LED and plasma and, and like sizes got bigger and stuff like it was pretty normal to upgrade your monitor, like every two or three years

[00:04:24] **Carol:** Yeah. Yeah.

[00:04:26] **Tim:** Back in my day. Mm-hmm.

[00:04:29] **Adam:** I'm just really worried cause like, you know, I guess I think I bought it when it was a little on the, you know, on the early side for these larger monitors. I think it's 4k. I don't, I'm not pumping 4k into it, but you know, it's a nice, big, high quality monitor.

[00:04:43] **Carol:** and you have a couple of monitors, right?

[00:04:45] **Adam:** Yeah, I do have a, so I use my laptop screen as like one monitor and then two externals, cause I have a Mac, I have a MacBook Pro, M1 Pro, which can support up to two external monitors. I would have liked to have, have, have three. Can't do it.

[00:05:02] **Carol:** I'm sure you've already debugged everything, but if you switch cabling and just flipped it around to see, oh, does the flickering happen on another monitor if I switch my cables? Because if so, I could have a port issue on my MacBook or I could just have a cable issue.

[00:05:19] **Adam:** That's a really interesting question. No, I did start to go down that path, but I didn't think to like, go all the way down. I did like, you know, unplug everything, fully reseat all the cables, that sort of thing, but I didn't try like swapping in like, okay, is it the monitor or the cable? Can I swap in one or the other?

[00:05:33] **Carol:** That's where I would start. I would go there because, yep, it could just be a cable problem.

[00:05:39] **Adam:** yeah, I'll have to try it. Like, see if I can, I don't know. I'm pretty sure that this monitor is on the, I have one on HDMI and one on Thunderbolt or DisplayPort or whatever it is. I think they're the same thing. and. I don't know which one this is, but if I had to guess, I'd say it's the HDMI, and I only have the one HDMI port, but maybe, yeah, I don't know, maybe I can find a Thunderbolt cable and see if it has a Thunderbolt port on the monitor or something.

[00:06:04] **Tim:** It's funny you say that because I'm sitting here, the other day I was looking at the monitor that's to the right of my laptop and it's like, I've had this thing over 10 years.

[00:06:13] **Adam:** Mm hmm.

[00:06:14] **Tim:** And like, I don't treat it nicely either. It's like, it's, it's in front. So my, I got my laptop in front of the TV that I watch when I'm laying in bed.

[00:06:23] **Tim:** And so it's like, whenever it's time to watch TV, I just take that thing and kind of slam it to the side of the wall to get it, get it out of the way. I mean, it's like been in the back of trunks. It's been in cars rolling around, backpacks. And the thing is just, yeah, just, and it's not even like a high quality.

[00:06:39] **Tim:** It doesn't have a brand on it.

[00:06:40] **Carol:** Is it curved?

[00:06:42] **Tim:** No, it's not

[00:06:42] **Carol:** Yeah.

[00:06:43] **Tim:** Oh yeah.

[00:06:44] **Carol:** I feel like whenever we went curved, things stopped lasting as long. And I don't, yeah. Same with mine. Like, I feel like I've replaced my curved monitors once already. So I'm on my second set.

[00:06:56] **Tim:** Never got the draw of the whole curb monitor thing.

[00:06:59] **Carol:** Oh, surround

[00:07:00] **Adam:** my, my brother kind of talked me into

[00:07:02] **Carol:** Yeah.

[00:07:03] **Adam:** Like, I was expecting it to be like, okay, you know, you're getting like same view distance if you sit at the, at the right distance from it, it kind of like makes it less of like a triangular field, right? So if you're looking at the edge of the screen, especially with a big monitor, right?

[00:07:18] **Adam:** If it's, you're looking out at the edge of the screen, it's further away than if you're looking at the center of the screen. And maybe that's true even at the distance that I'm sitting, maybe it's not, I don't know, but it is such a subtle curve,

[00:07:29] **Carol:** Yeah, I

[00:07:30] **Adam:** You know, it's like a, it's like a 10 meter, diameter circle that it's on the curve, right?

[00:07:35] **Adam:** It's, it's... Just a tiny little bit, but...

[00:07:38] **Carol:** It's kind of funny. Cause I was saying like, I have two curve monitors. So in there each 34 inches, I think they're huge. They're like way too big for anything. So, what I do is I bring everything on my right monitor to the left panel and I bring everything on my right or my left model to the right panel.

[00:07:54] **Carol:** So I basically use this one view inside, like. What I can see and everything on the outside, like Discord or, you know, whatever else, and YouTube will be over on the far right playing. So I still only use the center part of my screen, even though I have all this extra space.

[00:08:10] **Tim:** Let me break in here for a second here. Carol. we have breaking news, breaking news. This just in, Ben Nadal has entered the chat. Welcome Ben. We thought you wouldn't be with us. How are you doing buddy? And what did you eat for dinner?

[00:08:23] **Ben:** I went to a local Mexican place and I had Barbecue Chicken Wings, a Mexican delicacy.

[00:08:29] **Carol:** Clearly.

[00:08:30] **Adam:** wait, wait, wait, Ben. Ben, did you know that you can get them with no sauce on them?

[00:08:34] **Carol:** It's called naked. Yeah. You can get naked.

[00:08:38] **Ben:** I was, you know, trying to step outside my comfort zone and,a carnitas burrito, hold the beans, hold the salsa, hold the sour cream, hold everything else. And,

[00:08:49] **Carol:** you just got this, you just got a shell and meat.

[00:08:51] **Ben:** I get, I get the meat, the cheese and the, and the, rice, that's it. And then, I topped it off with a, a flan. I happen to love flan and it's always at Mexican restaurants.

[00:09:01] **Carol:** Yeah,

[00:09:02] **Adam:** The reason that Tim asked about your dinner is because you mentioned to us when you said you weren't gonna be able to make it that you were out on an indulgent...

[00:09:09] **Ben:** Well, it's the, uh, the flan really pushed me over the edge. I feel pretty gross right now,

[00:09:15] **Adam:** Ha ha ha

[00:09:18] **Ben:** And then I yell at, I yell at my wife cause I'm like, why would you let me eat that? Like you, you, I said, you really disappointed us tonight.

[00:09:25] **Tim:** Wow. You know, you're a grown man, right?

[00:09:29] **Carol:** man.

[00:09:30] **Ben:** So sorry, I didn't mean to interrupt. I just, I couldn't stay away from you guys.

[00:09:34] **Adam:** yeah, we were just talking about how my monitor is flickering. That's my fail. I'm worried. I spent like 400 on this monitor in 2019, and, and now it's flickering. And I'm not happy. Ugh. It's just, you know, it's one of those things where it's like, I'm not going to replace it until it dies, but like, it just stresses me out the whole time that it's doing it.

[00:09:53] **Adam:** I did notice that if I turn the brightness down a good bit, which I should have been doing a long time ago anyway, I'm a dark mode for life type of person

[00:10:00] **Adam:** anyway, to begin with, but then, you know, you open a Google doc or whatever, certain websites are like bright white. I did like the vibrance of colors in dark mode with the brightness on the screen all the way up, but then when you open a white website, it's like, holy, I'm blind now, right?

[00:10:15] **Adam:** so, yeah, I cranked the brightness down, and that seems to help, but I'm still, I can still, like, in certain scenarios, certain areas of the screen, see some flickering, so. Big, big old fat fail coming my way soon.

[00:10:28] **Adam:** So, that's enough about my flickering monitor. Ben, since you're back, it would be your turn to, to go next if you have something prepared, triumph or a fail.

[00:10:36] **Ben:** Let me, let me defer to Carol. Carol was on a roll talking about monitors so

[00:10:40] **Carol:** I know and then you just jumped in and Adam's gonna give you my spot. I mean, come on. That's not very fair. So mean.

## [00:10:48] Carol's Failure

[00:10:48] **Carol:** Well, I'm gonna go with a fail anyways because, I didn't learn Dagger. I said I was gonna go learn Dagger. I didn't learn Dagger. However, I did move my kid into college, I did list my house for sale, and I've started packing for my two week adventure across the country.

[00:11:03] **Carol:** So, I have a lot of wins in there, but...

[00:11:06] **Adam:** That's it?

[00:11:06] **Carol:** Dagger was not on that list and it has now been put on the back burner for just a little while while I get my life in order.

[00:11:14] **Adam:** I'm disappointed, Carol.

[00:11:16] **Carol:** I know. I'll do better. I'll do better, guys.

[00:11:18] **Adam:** it's fine. So, I would imagine most of the people listening have no idea what you're talking about because that was something that came up on the After Show two weeks ago.

[00:11:25] **Carol:** Yeah. Yeah. So only after I mentioned that I had heard about Dagger and I was super eager to go learn it and Adam mentioned wanting to learn it and I told him he couldn't because I wanted to learn it first and now, well, Adam's had to go learn it without me.

[00:11:39] **Adam:** We're gonna fight.

[00:11:40] **Tim:** Dagger fight.

[00:11:41] **Carol:** Yeah. Alright, well that's me.

[00:11:43] **Carol:** I guess now Ben can go.

## [00:11:46] Ben's Failures

[00:11:46] **Ben:** all right. I got, I got fails all the way down today. Uh,so today we had a huge reduction in force to say it as plainly as possible at Invision. I think the company went from 130 employees. I think an estimated 40 employees, which if you keep in mind, we used to be over 800, I think we were like 850 at one point. Then we had a massive layoff last July, then like another smaller one in February and then another one. And then this one is, basically they're kind of going into hibernation mode or they're, they're basically, I think they're putting a pause on feature development and basically just trying to, to, to maintain in hopes of having the market just bounce back a little bit more, but, most people that I work with.

[00:12:38] **Ben:** Basically all the people that I work with, less a few, were affected by this. I have been affected by this. I am no longer at Invision as a full time employee, but I am going to be doing some contract work for them in the interim while I'm looking for full time work. But, they need me

[00:12:58] **Carol:** Yeah.

[00:12:59] **Ben:** I was working on the legacy platform and apparently no one else knows how to do that anymore who's still there.

[00:13:06] **Ben:** So I have made myself invaluable by never moving on. Let the lessons be learned, kids.

[00:13:15] **Tim:** that's like security by obscurity

[00:13:18] **Ben:** Yeah. And then, and then I said fails all the way down because in conjunction with this and I'm, and I think this is partly stress related or maybe primarily stress related, I've also been feeling a lot of, wrist pain for like the last week and a half. My, my repetitive stress stuff has really been flared up big time.

[00:13:35] **Ben:** and, and I'm sure it's because I'm probably like all tensed up and my shoulders are all up and it's thrown my arms out of alignment. And then also I've been. You know, putting some time into the Dig Deep Fitness stuff, and it's probably just been a little too much coding and, and a little too much stress and a little, a little too much for the old broken body parts that I still have.

[00:13:57] **Carol:** But didn't I see that you were trying a new keyboard to help with some of the wrist pain?

[00:14:02] **Ben:** Yes. I, I, so I ordered a, I've been on an ergonomic keyboard since forever because of wrist pain. I used the Microsoft Sculpt as my keyboard of choice,

[00:14:12] **Carol:** one of my favorites.

[00:14:13] **Ben:** it's,

[00:14:14] **Carol:** keyboard. Yeah.

[00:14:15] **Ben:** really nice, but, you know, I have been feeling some pain, so, I, I've always been curious to try the keyboards that are completely split in half and just connected by a wire, because I figured maybe if I had my arms farther apart.

[00:14:27] **Ben:** It could help, or you can adjust the, the, the horizontal tilt as well. And, so I got the Kinesis something or the Kinesis Freestyle 2. And, I tried it for about an hour this morning and, it's really weird what, what works and what doesn't work. So the escape key is really far away. And if you're a normal typer, you probably almost never use the escape key.

[00:14:53] **Ben:** But if you think about IntelliSense, things are being suggested to me constantly, whether I'm in a SQL editor and the code editor. So I actually realize now that I use escape continuously throughout the day to close those menus out because they're always popping up right before I want to hit return or tab, which is what would trigger the accepting of the IntelliSense.

[00:15:13] **Ben:** And I'd actually, I kept having to physically pick my hand up and move over to the escape key to make it happen. So

[00:15:19] **Carol:** Oh, that's frustrating

[00:15:20] **Ben:** yeah. So that keyboard, I think is just. Probably not going to work out, but I don't know. There's there, there's so many split keyboards. I might continue to look or, you know, hopefully just taking some time off will give me enough.

[00:15:32] **Ben:** Of a break,

[00:15:33] **Tim:** I don't want to bury the lead here. so essentially you got fired.

[00:15:38] **Ben:** I got let go.

[00:15:40] **Carol:** Yeah.

[00:15:42] **Tim:** you got fired.

[00:15:44] **Adam:** Were you given the opportunity to, depart on your own terms?

[00:15:48] **Ben:** Well, so I, you know, like I said, I am gonna be doing some contract work, for the V6 platform, the legacy platform. 'cause no one else there knows anything about it. But it is understood that that is a temporary situation, until I find work. But now that, I mean, now that I'm thinking out loud, I, you know, I guess that doesn't, I don't know what severance, I guess severance would kick in after that's done.

[00:16:12] **Ben:** Or maybe this counteracts.

[00:16:13] **Tim:** And

[00:16:13] **Carol:** you'll probably get severance before that. It, they're not gonna tie together.

[00:16:18] **Ben:** Cause I haven't signed anything yet. Nothing's been presented to me officially, but,

[00:16:22] **Tim:** I mean, you got like kind of co founder status. How long were you at InVision?

[00:16:26] **Carol:** yeah,

[00:16:27] **Ben:** I think over 11 years, 12 years, something like that. But it's, it's a bit of a blur.

[00:16:32] **Adam:** Well, you can have, like, Unofficial co founder status, but if you were a co founder, you would know it and that, like, you would have been in the discussions of who's getting let go.

[00:16:43] **Ben:** Oh, well, yeah, I don't know.

[00:16:45] **Adam:** Yeah, you can have, like, the, the touchy feely co founder status, but you're not getting the real thing, apparently.

[00:16:50] **Ben:** Touchy feely is my thing.

[00:16:53] **Tim:** So my question to you is, I mean, how are you doing, buddy?

[00:16:56] **Ben:** I've been having a lot of different emotions. you know, the company has been trending in a direction that has not been amazing. So in some ways this has been a really long time coming. And then in addition to that, because I have, you know, continued to have enthusiasm for the legacy platform and not necessarily engaged fully from an emotional standpoint for the new platform.

[00:17:22] **Ben:** I, you could say that my priorities and the company's priorities have started to diverge over time, which means that I became less and less. In step with, with the value of the company. And so in some respects I've expected to be let go for quite a long time. And I think I ended up, they kind of let me have this job, I think a lot longer than I thought they would.

[00:17:45] **Ben:** So I feel good about that, but it was, it was a tough day, you know, it was a tough day because a lot of people that I care greatly about and who I've worked with. In some cases, some of these people I've worked with for literally an entire decade, were just let go. And it's really hard for, for all the things that Invision stumbled with.

[00:18:06] **Ben:** We hired amazing people. Like that's one thing that we really just got right over and over and over again was hiring really great, high quality people. And the tenure of these people at the company, I think, is a testament to that, that a lot of these people have been there six, seven, eight, nine, ten years, when, when you think about the industry average is like a year and a half, two years tenure at a company. So it was just, it was, it was a tough day. It was a tough day.

[00:18:36] **Tim:** Yeah.

[00:18:37] **Adam:** I bet.

[00:18:38] **Tim:** I mean, I just point out that it's been kind of a tough year for the Working Code podcast here. We got half of us have been, uh,

[00:18:46] **Adam:** Rift.

[00:18:47] **Tim:** made redundant as they say, over across the pond. hopefully these things don't come in threes, Adam, cause

[00:18:55] **Tim:** I mean, Ben, you, you got a name for yourself out there. It's like, I

[00:19:00] **Tim:** You know, if you want to, if you, if you want to keep working at ColdFusion, you know, shoot, if I told our company, my old company, like, Hey, the ColdFusion guru, Ben Nadell is looking for a job. They would be all over that.

[00:19:13] **Carol:** Oh yeah.

[00:19:13] **Tim:** I'm pretty sure every company would be like that.

[00:19:15] **Carol:** Yeah.

[00:19:16] **Ben:** that makes me hopeful because I have, I've literally not looked for a job in 15 years. So it's really scary. And, the industry's just changed so much in that time. You know, we've, we've talked about this on the show. The last time I was looking for a job, they didn't have backend engineers and front end engineers.

[00:19:37] **Ben:** They just had web developers and like, maybe there was a database administrator. Like that was the, the extent of the diversity. And now things have become so diverse and so specialized in many ways. Yeah, I haven't had to interview for anything. I'm just, it's, it's a little daunting, the idea of, of what's out there, but I am terribly charming.

[00:19:59] **Ben:** So,

[00:20:01] **Carol:** if,

[00:20:01] **Adam:** I do

[00:20:02] **Ben:** so yeah, you know, so I've got that going for me,

[00:20:06] **Tim:** so charming that I mentioned it myself.

[00:20:08] **Ben:** just, you know, for those who weren't in the know

[00:20:11] **Tim:** I'm kind of a big deal. No, I mean, you know, I think all that stuff you've done with your blog is you, you kind of invested, you have a personal brand. Let's just, let's just be frank about it. It's like, someone says ColdFusion, if they know anything about it, you're one of the first names that come up

[00:20:27] **Carol:** Oh yeah.

[00:20:28] **Tim:** a hundred percent.

[00:20:29] **Tim:** If they ever Googled it, it was you. It used to be Ray Camden

[00:20:32] **Carol:** Ray Camden,

[00:20:32] **Tim:** yeah.

[00:20:33] **Tim:** and then he, then he changed ColdFusion Jedi to just his name. And it's like, yeah, it's, it's, now you, buddy. You and Charlie, you, you and Charlie Areheart are probably,

[00:20:42] **Ben:** keeping the dream alive,

[00:20:43] **Tim:** yeah, keeping the dream alive. So I think you'll be, I think you'll be just fine, but you know, you don't like change.

[00:20:49] **Tim:** We know that about you so.

[00:20:51] **Ben:** That's true. So we'll see. I mean, I think in a, in a perfect world, I would love. Very much to continue doing ColdFusion. I do find it to be an incredibly enjoyable language, almost fault free, but not entirely, and, uh,

[00:21:07] **Adam:** Okay. So we know your vision's not great.

[00:21:10] **Carol:** hmm.

[00:21:11] **Ben:** but you know, I, I've also, I do love front end work too, so

[00:21:15] **Adam:** New employer must have, I've, oh, is it a vision care, vision insurance?

[00:21:20] **Tim:** Yeah, for sure.

[00:21:22] **Carol:** Well, I'll throw this out here, Ben. Once you kind of get down the road and you decide you want to start interviewing, I will gladly mock interview you to break the ice if you want. That way, you know, the nerves are kind of gone and then you can get back on that horse.

[00:21:36] **Tim:** Oh, Carol and I will tag team you.

[00:21:37] **Carol:** Oh yeah.

[00:21:38] **Tim:** Yeah, yeah.

[00:21:40] **Carol:** I have commitment issues.

[00:21:41] **Carol:** Three years and I'm looking for something new. So. I know what interviews are.

[00:21:45] **Tim:** She do. She also knows how to negotiate for

[00:21:48] **Carol:** I do, I can help you with that

[00:21:50] **Ben:** Yeah, you are quite a savvy individual for sure. Well, thank you guys. I don't want to, I don't want to take up all the time, but I, I appreciate it. I appreciate you letting me get here a little late, cutting me some slack and and then just being always there for me.

[00:22:04] **Carol:** we love you, Ben, and we hate that you're going through this.

[00:22:07] **Tim:** Yeah. But just stop it with the Mexican burps, okay?

[00:22:11] **Adam:** Eat some beans, man.

## [00:22:14] Building Things For Building Things

[00:22:14] **Carol:** Let's talk about like, building things for building things. What's that about, Tim?

[00:22:20] **Tim:** Yeah. So I saw an article, by Dimitri Glazkov and we'll put a link to it there. And he made a point that, so it really struck with me because, you know, I work on a lot of APIs and you assume, because you understand the API that you're building, that you can just hand this to someone with the documentation that, you know, he's like, Oh, just go build.

[00:22:43] **Tim:** You know, it's credit card processing thing based off this API. It's, it's a Swagger doc. There's some explanatory stuff too. It should just be easy, but this year I've been building a lot of prototypes to like basically kind of show for our sales cycle. Hey, here's how you, you know, if, if you want to do solve this problem, here's how you use our pay via APIs to do that.

[00:23:09] **Tim:** And in doing so, I found out, you know what, our APIs could probably be a little more friendly. And this is kind of what this article talks about. There's a diagram. Of the, you know, you have different mentalities. So you have a mentality about, you know, this is Ben's thing, ship something quickly, launch and iterate.

[00:23:27] **Tim:** Right. So make, do something fast, launch it as fast as possible, and then just make small changes constantly. That that's the Ben method. Right. And then the other, other folks are like, you know, let's just take our time. Let's experiment, figuring it out. Let's try to figure everything out sort of in the middle.

[00:23:43] **Tim:** Is sort of build a thing to build a thing. And that's, that's what talks about that. So you basically, you build a product that similar to what your customers would do, that uses your product, that, that. That's there and to see how easy that is. And the article really talks about that, you know, they learned a whole lot from it, that there are, gaps in knowledge and things that they could learn to make it easier for them to do so.

[00:24:14] **Tim:** And I just, I think that's a, that's a valuable takeaway because you can. To learn from the customer's perspective that's consuming your product. No, I'm not. This is, I think this applies really. They talk about an API and some things that they built in Chrome. they adopted the, the attitude live as our customer, which I think is powerful.

[00:24:36] **Carol:** So it doesn't have to be something you sell, right? Like this could be something that's just you use internally to actually, like your developers use for your product. Your sales team use it to see how it works. I mean, it doesn't have to be something that's sold as something that could just be in, in house.

[00:24:51] **Adam:** Or not even, not even used beyond what you need to learn, right? You're just building a prototype of a product that uses your, your product so that. You can see how it goes, and then you're just like, Okay, we've learned what we need to learn and throw it away.

[00:25:05] **Carol:** Yeah, I guess I, I think of projects lasting a lot longer, so I can't imagine building it and throwing it away. I'm like, Oh no, keep it. Cause you know, the next person's going to want to see that and then they're going to want to add to it. So.

[00:25:17] **Ben:** I do really appreciate when a Sass offering will also ship clients for that, for, for API consumptions. Like you can download the Java SDK for the Amazon API, or, you know, everyone has a Java or JavaScript or Ruby or PHP implementation of stuff, but it's, that's always really helpful and I think can help a company think about how you can consume the API without, you know, you, you, your API clients that you distribute usually have.

[00:25:47] **Ben:** More semantic gestures than you might initially have in a REST based API. And that can sort of help you think about the touch points.

[00:25:57] **Adam:** That's a really good point. And like building SDKs to go along with your API, for example, if the API is your product.

[00:26:06] **Tim:** Yeah, so the, example that this person gave was that it was about a decade ago. They were, he was working on the Chrome web platform. And, they wanted to get a sense if the APIs and primitives they were shipping were actually helping developers make better mobile web applications.

[00:26:23] **Tim:** So they basically spent a few weeks, locked themselves in a room and then basically built a proof of concept using what they had built, to see, you know, how, how well it worked. And then after, then they, each week they would write up a report to say what they've learned, where the friction was, some things were easy and some things were extremely hard to do.

[00:26:43] **Tim:** and their, some of their API primitives that they had in their APIs. They weren't necessarily as useful as they thought they were. And the end result was, he says that they failed. they basically, they basically failed. They had absolute proof that if we wanted, if we wanted for mobile web apps to be on par with their native equivalents, we had to do something different as a team.

[00:27:05] **Tim:** And I think if you don't do that exercise, if you're giving people tools to build something else, then build something that uses those tools. As your customer would, and you'll learn a whole lot more about where you're succeeding and where you're failing

[00:27:22] **Carol:** Yeah, so I guess one of my things would be, okay, not me personally, cause obviously I never do anything wrong and I don't think like this, you know, but I would

[00:27:32] **Ben:** You could imagine

[00:27:33] **Carol:** I, I can, I can imagine someone just building the thing to use it, to make it work in a way that what they've designed works so that it passes so that it looks usable.

[00:27:43] **Carol:** So wouldn't there, like, wouldn't you want some differentiating, like. Team for the people building it, then what's building the actual product. Because I, I would say, Oh, I've made it call this, this way. And that's how it's always going to be used. So therefore it passes and looks great. And if you don't add some diversity in there between the two teams, then you end up with passing, passing every time product looks good, looks usable.

[00:28:09] **Carol:** Let's go. In reality, I just said my test passed and let's call it done.

[00:28:15] **Tim:** so you're saying there could be some bias if it's the same team? Yeah.

[00:28:19] **Ben:** one thing that I've heard that companies can do is they'll have internal hackathons where they'll have an API and then they get all of their engineers for three or four days to just have internal pitch days. And, and they'll work on products that consume the APIs and then they get prizes and stuff.

[00:28:37] **Ben:** And I think that's. That, that sounds like a really fun way to test out an API

[00:28:41] **Carol:** I I think it is too. I like that idea.

[00:28:45] **Tim:** I mean, I mean, the article does say that you need to make an earnest effort, right? That if you go into this, we we're just trying to check a box off. You're not gonna learn anything. But if you're go into this that we're trying to learn how well our, our, our customers are going to perceive the thing that we've given them. And if you do that, then you could learn from that. And another argument is you could have, so if you're a big enough company and you have a DevRel, you know, developer relations person, whose job is to like, you know, build demos and go out and, you know, evangelize the product you're doing, you give it to them and say, right, you give it to them and say, Hey, go do this.

[00:29:24] **Tim:** And then take their feedback and say, you know, because those people typically are talking to. Your, your target audience as a customer, right? And they're, they're going out there and try and say, Oh, if you use our stuff, it's so much easier, you can track stuff, log stuff, whatever it is you're, you're selling, and they're talking to technical people.

[00:29:44] **Tim:** So they've heard those questions. Your DevRel can, can say, okay, let me, let me try to build something, give them the time to, to build a tool that consumes your product, and then say all right, what, what do we need to

[00:29:59] **Tim:** change? What was hard? What was easy?

[00:30:01] **Ben:** If I can go down a quick aside for a second, this reminds me of a story from, I went to a Hal Helms workshop. Hal Helms was a guy in the ColdFusion world for, for many years. He was holding this workshop down in Florida. I mean, God, like 15 years ago, maybe. Anyway, one of the other attendees at the workshop, his company was building an Ecommerce platform.

[00:30:26] **Ben:** And in order to make sure that the Ecommerce platform worked, they decided to build an online store as, as a demo site, kind of like this, building it to make sure that the thing you're building for people works and the idea that they came up with was that where the guy lived, there was a baker in town who made gluten free bread and 15 years ago, that wasn't such a common thing like it is today.

[00:30:49] **Ben:** So he's like, Oh, here's a, here's an idea. We'll make a gluten free bread online shop and people will buy and will literally just go down to the store and buy a loaf of bread and package it up and ship it to people. And he said it became so popular that they ended up making more money from selling the bread out of this bakery than they did from selling the Ecommerce platform itself.

[00:31:10] **Adam:** And I bet you the baker was happy too.

[00:31:12] **Carol:** Yeah. Win win for the whole community.

[00:31:15] **Ben:** always had a dream that I could figure a scheme out like that, but I have yet to, yet to come up with

[00:31:19] **Adam:** Yeah. Yeah. Right.

[00:31:20] **Adam:** Tim, you mentioned DevRel as like maybe an obvious, group of people to, to do this sort of thing. And I think that the article that you

[00:31:28] **Tim:** Yeah, but it can't be a trap.

[00:31:29] **Adam:** Yeah, exactly. That's where I was going. It's like, the problem is if the people that are building the, the secondary product that consumes the primary product are not the people who are also developing the primary product, then the things that are frustrating about it, you know, once they get past it, cause they're, as that dev rel, as the person consuming something, you're just trying to feel like, how am I supposed to use this?

[00:31:52] **Adam:** What am I missing? Right. And, and if you're not the person who is developing that, you're, you may not recognize that that's a friction point that could be improved. and so those things just fall through the cracks.

[00:32:02] **Tim:** Right. Yeah. It does mention that that can be a trap because a lot of times the dev rel is they're coming in perspective of, Oh, we have this really cool API or this cool tool, I'm going to show the power of it. So all they're looking at it is from the perspective of what can this thing do? And how can I show that?

[00:32:17] **Tim:** Not from the perspective of I'm a customer, here are my needs. How does this solve it? and so, yeah, that can be a trap that, that's a good point. Cause the article completely says that, but I mean, so I, I only brought this up because I, like I said, I ran into this myself. We had a customer, they're a different insurance type entity than we're used to.

[00:32:39] **Tim:** Usually we don't deal with workers comp. I didn't fully understand their use case. But got talking to them, and the more I talked to them, the more I realized, okay, how can I show them? I didn't really even have a demo to show them based off their uses. so I started building it and then I realized as, as I started building it based off what they gave me, I'm like, I, I asked them, like, went to them and said, listen, what would be the perfect demo for you?

[00:33:04] **Tim:** What, what do you want to see happen in this demo that would, that would knock your socks off and say, this is what we need. This is what we gotta do. And, you know, they're like, okay, so they listed, we got, it has to do this. It has to have this sort of login, you know, these sort of things. And he's make these sort of payments and this sort of reporting.

[00:33:22] **Tim:** All right. Okay, cool. So went away three, four weeks and built sort of a MVP. It wasn't secure. It wasn't scalable. It was, you know, this thing, you know, was garbage. Had, had you tried to, you know, put this into the wild, but it, it did demonstrate what they did and it was only. Eating our own dog food. It was using our, our tools and in the process of doing that, I'm like, you know what, there's really some things we can add to the product here that would make this so much easier if we had these.

[00:33:51] **Tim:** And I never would have understood that. Had I just handed it off to their, their developers and said, oh yeah, here's the, here's the specs, go build it. Why can't you, why can't you figure it out, you dummies?

[00:34:02] **Ben:** Can you give us, maybe a semi concrete example? Like what are you talking about? Condensing multiple API calls down into a single API call or changing permissions models, or is there something that's not proprietary that you can share?

[00:34:17] **Tim:** Yeah. So exactly what you said. So like rolling, so there were some processes that to do. a payment authorization and finally, you know, because we talked a few weeks ago when we talked about fraud, you know, there's different steps. There's where you basically authorize the card and then transact the card and settle it.

[00:34:37] **Tim:** There were multiple steps, but. And for them, I realized as we did that, it's like, why does this have to be such a multiple step process? Condensing that down into basically one API call, because you have all the data there. and doing that basically extremely simplified it for their, for their developers.

[00:34:54] **Tim:** So that, that was at least one concrete example of doing that is where, I'm like, oh, you just call this thing and then you get this back and then you send that back. And then once you get that back, then you send this back and then now you get the result. Why can't we just all do that, have a helper function that combines all three of those steps into one, and now

[00:35:14] **Carol:** It's one send, one return.

[00:35:16] **Tim:** Right, exactly.

[00:35:17] **Ben:** You know, that's a little bit how I felt the first time that I tried to design a REST based API and for those listening, and I'm sure I'm going to butcher this, but. A REST API is sort of designed around a set of grouped resources. and you're performing operations against these resources. And I didn't know anything about designing APIs and I, I, I

[00:35:41] **Tim:** there

[00:35:41] **Carol:** I know,

[00:35:41] **Tim:** this, this, this call that

[00:35:43] **Carol:** there might be a book you could read on that.

[00:35:46] **Ben:** So here, the thing is, is this was for work and this was the early days. And so you have users and users own prototypes and prototypes contain screens and screens contain comments. And so we've ended up building out these URLs where it would be like users slash user ID slash projects, project ID slash screens slash screen ID slash comments.

[00:36:10] **Ben:** And so anytime you wanted to do something at the very end, like. Add a comment or, or delete a comment. You'd have to have the user ID and the prototype ID and the screen ID and the conversation ID. And at some point I was like, you know what? We didn't need any of that because as long as you had the conversation ID that you're talking about, I could have gotten the rest on the server side and it could have really simplified it hugely for the user.

[00:36:36] **Ben:** So it's that, that exact kind of thing is that I didn't know how complicated I was making it. Until I ended up having to also be the one who consumed it much later, realizing that, ah, it's such a pain in the butt to have to get all of this data to make these low level changes.

[00:36:52] **Tim:** hmm. I read a complete, complete same thing. It's like, when you start having, required parameters that you need for RESTful API, there are a bunch of, like, random IDs. It's like, you, you don't know where to start. How do I even get that? So... You know, building things that basically says, you know what? Like we have a policy id, I have a policy ID and I wanna be able to do this and that's the only thing I need.

[00:37:16] **Tim:** I'll go figure out all the rest based off of that. doing that kind of extremely simplifies, your API to make it easier for people. 'cause then, then you get a whole bunch of questions like, well how do I get these six. You know, parameters I need to pass to this. Oh, we got to go to this thing, this thing, this thing, and this thing, you know, I can get there from where I know.

[00:37:38] **Tim:** Right. If they can get it, I can get it. So why do I make them get all these other parameters past one, one parameter and get the rest for them?

[00:37:47] **Ben:** Yeah, absolutely. Let, let the server side people leverage the relational part of the relational database, like don't foist that unnecessarily on to people who don't have to.

[00:37:57] **Tim:** Yeah. And plus you, you're not, it's not like you're giving them a database diagram. They, they're not, they're not going to know.

[00:38:03] **Adam:** And this topic is covered, in pretty good detail in, what is it? It's REST web APIs. No, no, sorry. That was the old, that was the old name of the book. I renamed it, REST Assured.

[00:38:13] **Carol:**

[00:38:13] **Tim:** Rest assured by Adam, Adam Cameron. Oh, Tuttle. Oh yeah.

[00:38:18] **Adam:** RestAssuredBook.com.

[00:38:21] **Tim:** It's a good book.

## [00:38:22] Transcripts Soon

[00:38:22] **Adam:** All right, well then, it sounds like we're kind of, kind of done with this topic, so why don't we, we have a couple of other things we kind of wanted to fit in here if we could tonight, and I'll throw this one out first. we've danced around the idea for possibly years at this point of, having transcripts for the podcast, and it's now going to start happening. And, even better. We're going to sort of like open source them, right? So the podcast, our podcast website is built from, Markdown files on that are on GitHub. And, the, the transcript is going to be in the show notes file. If I understood correctly, what I talked about with our editor, Matt, the transcript will just sort of be like the bottom section of the show notes page.

[00:39:06] **Adam:** And so, and there'll be like, if you go to the, the show notes on our website, there'll be a link on there to like edit the, edit this page on GitHub or whatever. And then, so if there's, if there's a typo or something in the show notes and you want to improve it, you can just go over there and edit it and make a pull request, and improve it for everybody else.

[00:39:24] **Tim:** That would be pretty dope. we still have approval, but I don't want them putting words in my mouth.

[00:39:29] **Adam:** yeah. Yes. Tim, Tim will personally review all pull requests, no matter how asinine,

[00:39:34] **Tim:** wasn't signing up for that.

[00:39:36] **Adam:** you just did, I voluntold you

[00:39:37] **Tim:** Oh, okay. Okay. Okay.

[00:39:40] **Carol:** You'll enjoy the pay.

[00:39:41] **Tim:** I'm going to need,

[00:39:42] **Carol:** It's what you make now.

[00:39:43] **Tim:** Yeah, exactly. You're going to multiply my pay now by five.

[00:39:47] **Adam:** Yeah. So that's coming. we've been dancing around it for

[00:39:50] **Tim:** Now it would just be the main show, right?

[00:39:53] **Adam:** Yeah, we're not going to do the after show.

[00:39:55] **Tim:** Good. Thank goodness. Whew.

[00:39:57] **Adam:** Yeah, nobody needs to see the word testicles that many

[00:40:00] **Tim:** Yeah, I, I don't, I don't need that. I don't need that HR violation. that's cool. Better to see that.

[00:40:06] **Adam:** Yeah, me too. And I, I'm not promising that it'll be done for this episode or anything like Matt's going to go back and do our, our back catalog and, and our new shows going forward, but I don't know when he's officially going to start on that. So.

[00:40:17] **Tim:** So he is gonna start, is he gonna like physically type it out? I mean, how's he, I mean, that's, that sounds like a lot of work.

[00:40:22] **Adam:** I believe it is, it gets like a baseline starting point from like ML, right? Machine learning, AI, whatever you want to call it, right? It's gonna, a robot will do the transcriptions and then he'll clean up any obvious mistakes and take out all the parts where we divulge company secrets and call each other not safe for work words and hang on while I go pee.

[00:40:43] **Adam:** That sort of

[00:40:44] **Tim:** Yeah.

[00:40:45] **Carol:** Robots are taking their jarbs.

[00:40:48] **Ben:** They took our gerbs. Oh, dang.

[00:40:52] **Adam:** That's pretty cool. Coming soon.

[00:40:53] **Adam:** Um,

[00:40:55] **Carol:** I'm so happy about that.

## [00:40:57] Adam's Fitness Journey

[00:40:57] **Adam:** So, I don't think I've mentioned it on the main show. And I may or may not have mentioned it on the after show. for about a month, I was working with a personal trainer cause I've been trying to, stop getting fat and start getting healthier, you know, just, just baby steps. and so I, I started using the service as like an online personal trainer thing.

[00:41:19] **Adam:** and I liked the ethos of it. It's a really good service. And if anybody had the money, I would certainly recommend it, but it was a very expensive service. It was like 300 a month. Um,yeah. but I mean, it's, I, it's good, it's a good service. And I certainly would vouch for it in terms of like, if you have the money, then it's worth it.

[00:41:36] **Adam:** like if 300 a month doesn't sound bad to you, then check out, what it's called, My Body Tutor.

[00:41:43] **Tim:** if 300 doesn't sound bad to you, you should be. A patron of the

[00:41:47] **Adam:** Yeah,

[00:41:47] **Tim:** I'm just saying.

[00:41:48] **Carol:** Yeah.

[00:41:49] **Adam:** very true. And, and this is, this is where it gets, like if it does sound bad to you, keep listening, right, because, so because it's 300 a month and I tried it out and I was like, okay, this is, it's a good program, but. To be fair and honest, nothing about it was not obvious, right? The, the whole thing of the program is like, we're going to make small tweaks to your current routine, right?

[00:42:09] **Adam:** You're going to eat, you're eating, you know, tacos for dinner. And the, the thing, the bit of advice that I got from that, that one taco dinner was like, okay, well, you had five tacos. What if instead of eating five tacos in tortilla shells, you had like one taco in a tortilla shell and all the rest, you just took all the insides of the tacos and put it in a bowl.

[00:42:25] **Adam:** Then you're eating four fewer taco shells, which saves you a whole bunch of carbs and calories. And you get all the part that you actually care about. Cause nobody cares. They're not like, Ooh, this is such a good tortilla that my taco stuff is in. Right. You're there for all the flavor y stuff. Anyway, so that's the type of thing, right?

[00:42:41] **Adam:** It's, it's small tweaks that put you on a path toward. a healthier lifestyle and it's and it's sustainable because you're not, he's not asking you to like eat a pound of kale every day. It's like, you know, eat less tortillas, that sort of thing, right? And then he was also helping me out with like, okay, here's the workout equipment that I have, help me plan my, my weekly workout routine sort of thing.

[00:43:02] **Adam:** Anyway, so I stopped using this just because of the expense. and Instead, I sort of tried to start what I hope will just become like a little sort of similar community for the same purpose within our Discord server. So,

[00:43:17] **Tim:** Dig Deep Fitness.

[00:43:18] **Carol:** I was going to say,

[00:43:19] **Adam:** no, that's my, that's my chief

[00:43:21] **Carol:** you can use. Yeah.

[00:43:23] **Adam:** chief competitor. Mine's

[00:43:25] **Ben:** going down,

[00:43:26] **Adam:** in, mine's built in SvelteKit.

[00:43:28] **Adam:** course it is.

[00:43:30] **Adam:** no, so, okay, first of all, it's in our Discord, right? It's, sort of a, a, a corner of our existing community from the podcast. And as it exists in the Discord server. It has to have a name. So you have to have a good like nerdy, you know, it's nerdy, but it's also like fitness oriented, right? So what do you call a chat room channel?

[00:43:49] **Adam:** That's about like nerds doing fitness. I named it halt and eat fiber.

[00:43:56] **Tim:** I saw that pop up. I'm like, what the heck is this?

[00:43:59] **Adam:** Yes.

[00:44:00] **Adam:** I

[00:44:00] **Carol:** great. Someone's going to be talking about poop. Oh,

[00:44:04] **Adam:** I was so happy when I came up with that idea. That was great. Anyway, yeah, Halt and Eat Fiber. If you're not, if you're not familiar with Halt and Catch Fire, aside from, well, even if you are familiar with the TV show, there was a pretty good TV show by that name. But, Google, it's an old, it's a reference to an old IBM computer

[00:44:20] **Tim:** catchfire, a race condition.

[00:44:24] **Adam:** Anyway, so the idea is just like people who care to, to participate in this sort of thing. You know, we can share pictures of what we're eating or talk about our struggles or talk about workouts or share advice or, you know, like we, a bunch of us got together and shared our Apple Watch, stats, right?

[00:44:41] **Adam:** So you can see when somebody else in the group has completed a workout and everybody can see. Everybody can see that you haven't closed your rings or whatever. And so they're like, I got a text from one of my friends, like this, he's not in our Discord, but, I shared with another friend of mine and last night he texted me at like 9 30.

[00:44:56] **Adam:** He's like, why aren't your rings closed?

[00:44:58] **Adam:** Like, and that

[00:44:59] **Tim:** a, what's that mean?

[00:45:00] **Adam:** okay. So on the Apple watch, you can have, of course my phone's in do not disturb. So it's not going to show up here. Let me, let me turn that off real quick. so you can get different watch faces and some of them have these like multicolored rings.

[00:45:13] **Adam:** So the inner ring is blue and, and that's for, standing hours, right? So you're just supposed to be standing for at least a minute within every

[00:45:21] **Tim:** just let the listeners know that both him and Carol holding up their watches to the screen right now, which is great, great podcast material.

[00:45:29] **Adam:** Oh, it's for your benefit. Everybody else listening has probably already seen this. Anyway, so the inner ring is blue. It's for standing hours, right?

[00:45:34] **Adam:** If you stand for at least a minute within an hour, like a calendar hour, basically, then you get like one more in and you can control what your goals are for each of these, right? So mine is like 12 hours. you could set it to six hours if you like are just. Bed, not bedridden, bed bound. I don't know, whatever.

[00:45:51] **Adam:** Like if you can't get up and you, and that's not a realistic goal for you, you can lower the goal. And the next ring out is green. That's the like exercise time. So you can say, I'm going to exercise for 45 minutes every day or whatever. And so you start a workout on your watch and it attracts how long you've been spending on it.

[00:46:07] **Adam:** It does all kinds of other things too, right? Heart rate and. And that sort of thing, but the, the ring itself is for time spent working out. And then the outer ring is for calories burned. and yeah, so he was like, Hey, you, you haven't closed your rings today. Get on that. What are you doing? And that's honestly, that's the kind of thing that I needed from, you know, like my trainer or yeah, that accountability buddy thing.

[00:46:29] **Tim:** Well, it,

[00:46:30] **Carol:** or they'll also pop up on your watch. Like whenever your friends finish a workout, it's like, Hey, Megan just finished a workout and I can just swipe up and it has like automated responses. So it'll text her and be like, great job. Or like, how was it? How are you feeling? So, like, I know when one of my friends is having motivation issues and I make sure to, like, respond to it and be like, great job on working out.

[00:46:50] **Carol:** Like, super proud of you.

[00:46:52] **Adam:** I do wish that there were like better reactions. So like you go on Facebook, you can like emoji react to things. I wish there was that for those. And the, all the canned responses just sound so cheesy to me. So, and I don't have time to sit and write them out, but.

[00:47:04] **Carol:** I enjoy being cheesy.

[00:47:06] **Adam:** Maybe I'll do that to, to somebody just for fun.

[00:47:09] **Tim:** well, the channel seems popular on Discord cause I know I muted it today cause

[00:47:16] **Carol:** I will.

[00:47:17] **Tim:** working out. No, thank you. I don't know the start of myself.

[00:47:22] **Carol:** And you do.

[00:47:23] **Tim:** Yep.

[00:47:24] **Adam:** So, I mean, I guess maybe I should just throw this out there. It's probably a bad habit, but I think everybody in podcasting does it. Not sponsored, right? The, the whole MyBodyTutor thing. Like I, I paid for it with my own money. I got a refund cause I didn't want to keep paying for it every month. but, yeah, not sponsored.

[00:47:39] **Adam:** Just something I, and like I said, if you got the money and it sounds like a good deal to you, then I highly recommend it. It was too, too rich for my blood.

[00:47:48] **Tim:** And if your wife let you spend it,

[00:47:50] **Adam:** There is that. Like, I, uh, she probably would have been fine as long as I was, spend 300 a month less on skydiving and woodworking stuff, and that's not going to happen. So

[00:47:59] **Tim:** is all about choices,

[00:48:00] **Adam:** yeah.

## [00:48:01] Patreon

[00:48:01] **Adam:** All right. Well then, we're going to wrap it up. So this episode of Working Code was brought to you by RestAssuredBook.com. R-E-S-T-A-S-S-U-R-E-D-B-O-O-K dot com. Pretty sure I spelled that right.

[00:48:12] **Carol:** job.

[00:48:14] **Adam:** And listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:48:21] **Adam:** Our patrons cover our recording and editing costs and now our transcription costs. Thank you so much. We couldn't do this every week without them. Special thanks, of course, to our top patrons, Monte and Giancarlo. You guys continue to rock.

## [00:48:35] Thanks For Listening!

[00:48:35] **Adam:** we are going to go record the after show. By now you probably know what that is, right?

[00:48:39] **Adam:** Patrons get that. we're just going to keep talking. It's going to be totally off topic from work stuff. I don't know. Actually, I have a, I have a sci fi book thing I want to talk about. But I think Carol has a work thing, work adjacent

[00:48:50] **Adam:** thing, backlog thing.

[00:48:52] **Carol:** I do. I do.

[00:48:53] **Adam:** So we're going to get into that a little bit.

[00:48:55] **Adam:** and you know what? We're not, we're not going to do any homework. Nobody likes homework. It's the summer. so no homework this week. So that's it for us this week. We'll catch you next week. And until then.

[00:49:04] **Tim:** Remember, your heart matters, even if your ring is all busted.

[00:49:08] **Adam:** Your rings are not closed.

## [00:49:29] Bloopers

[00:49:29] **Ben:** just as a quick aside, if you guys don't mind, I, I, I'm not going to stay for the after show. I'm just, I'm exhausted.

[00:49:35] **Carol:** Do it. Yeah. Yeah. Get it.

[00:49:36] **Ben:** it.

[00:49:37] **Tim:** you're just milking this unemployment thing up for all its worth, isn't it, buddy? My God, what a pre Madonna.

[00:49:42] **Tim:** buddy. mean, you're already not working. You don't want to do a little extra work on the podcast.

[00:49:50] **Adam:** Oh, you're going to make him cry.

[00:49:52] **Carol:** Aww. All
