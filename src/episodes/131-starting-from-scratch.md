---
title: "131: Starting From Scratch"
description: "Ben has finally started to write code for Dig Deep Fitness. On today's show, Ben walks us through the pragmatic choices that he's made in order to try and keep progress moving forward even if it comes at the cost of elegance."
date: 2023-06-14
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/131-starting-from-scratch/id1544142288?i=1000616982179"></iframe>

After years of wanting to build a fitness tracking application, Ben has finally started to write code for [Dig Deep Fitness][dig-deep-fitness]. But, starting a new project from scratch isn't something that we engineers do very often; and, all of the features that we take for granted - session manage, error logging, rate limiting, email delivery - those foundational aspects all need to be created when we start something new. On today's show, Ben walks us through the pragmatic choices that he's made in order to try and keep progress moving forward even if it comes at the cost of elegance.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[dig-deep-fitness]: https://www.digdeepfitness.com/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/131-starting-from-scratch.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Intro

[00:00:00] **Adam:** Did you, so you consi you said you're on v ps, you said you're on windows. You said you're gonna FTP stuff in. Did you consider

[00:00:06] **Ben:** Checking all the modern boxes right there, baby.

[00:00:11] **Adam:** yeah, I mean, that's a, that's a, that stack doesn't even have a name yet. It's so, so hot and fresh.

## [00:00:36] Intro

[00:00:36] **Adam:** Okay, here we go. It is show number 1 31, and on today's show we are going to steal another podcast's idea and just, we're gonna steal their format. and, and also, welcome to the Ben and Adam show. It's just, it's just Ben and myself now, for the second week running. we haven't, kicked out our, our co-host, but, Carol is, uh, still working on moving and Army stuff, and Tim is sick this week, so the two of them, once again, will not be joining us.

[00:00:59] **Adam:** And that's their loss, isn't it?

[00:01:02] **Ben:** a hundred percent

[00:01:03] **Adam:** Yeah.

[00:01:04] **Ben:** Hundo P.

[00:01:06] **Adam:** so Ben has, finally gotten up off his lazy quack. Ben has finally gotten around to, working on this project and he wants to talk about stuff. So we're gonna, we're just gonna kinda like steal sort of the idea or the format, I guess, a little bit of the Escape Velocity podcast, which I know Ben and I both enjoy.

[00:01:23] **Adam:** and just, just chat through how things are going. but first, as usual, we will start with our triumphs and fails. And I believe last time that it was just Ben and myself, I went first. So Ben, why don't you go first?

## [00:01:33] Ben's Triumph

[00:01:33] **Ben:** Yeah, absolutely. And this is, I, I think it's a triumph. I'm not sure. It feels a little bit like a failure. It's weird. I think I mentioned on the previous episode, or two episodes ago, I removed Twitter and Facebook from my phone. So I have only been using social media from my desktop. And what that has essentially done is remove any desire that I have to actually engage in social media.

[00:01:59] **Ben:** Because when I'm at my desktop, I'm doing things like I'm being a productive human being, whether it's working on the project we're gonna talk about or doing work, work for monies. and I just, I, I can't motivate to open a tab and look at tweet deck or look at Facebook or, you know, like I'll post when I write something, but I have no, I just have no desire to check in.

[00:02:19] **Ben:** It was really the walking the dog or standing in line at the store, sitting on the toilet. Like that's when I was flipping through the phone, looking at the social media. And without that, I, I just, like, I don't care about social media anymore, which feels like a triumph from a, from like a societal standpoint.

[00:02:37] **Ben:** But I, I've actually started to feel a little bit disconnected. Like, I,

[00:02:41] **Adam:** I get it.

[00:02:42] **Ben:** I'm, there's no pulse. Like I have no pulse to anything. and it, I'm not saying that the pulse that I had before was good and healthy, but it was something and, uh, I'm actually feeling a little disconnected.

[00:02:53] **Adam:** I, I totally see that. Right. Like the, the, connection to society has kind of swapped from being like, you know, reading blogs and, and newspapers online and watching the news and stuff on TV to be social media driven, you know, hopefully to, I think the, the original intent when we made this shift, I know it was somewhat intentional frame for me, was like, oh yeah, you know, the, the good stuff will bubble up.

[00:03:18] **Adam:** The good articles will get shared and. and if you give up social media altogether, which is not an altogether unhealthy thing to do, I, I commend you on the effort.

[00:03:26] **Ben:** Well, I mean, just recently the, the surgeon, was it the surgeon General of the, of the US released a a statement saying that social media is, is bad for teens, especially teen women. The, some of the most recent episodes of the Ezra Klein podcast, which I think I maybe mentioned before, were all about teen mental health crisis in America and, and actually globally and talking about how when they, when they look at all the data that it seems to be consistently coinciding with the rise of social media and that there seems to be a direct link with how much time people spend on social media with how bad of an experience they have.

[00:04:05] **Ben:** And, and, and it's, so it's that last point that I've been thinking about because I'd never really spent a whole lot of time on social media. It was like, again, standing in line or walking the dog and she's, you know, sniffing

[00:04:16] **Adam:** at the RIN

[00:04:16] **Ben:** minutes. Yeah, exactly right. It, it, it was that like one or two minutes of, of, of, of free mental space.

[00:04:24] **Adam:** how long does it take you to pee?

[00:04:27] **Ben:** I drink, I drink a lot, I drink a lot. so I think I didn't have a lot of experience on social media, so I think my experience has. Overall been quite positive. So I, I don't think I ever really ventured into that unhealthy relationship with social media and because of that, it, I'm, I'm missing the value add that I think it was presenting,

[00:04:48] **Adam:** Hmm.

[00:04:49] **Ben:** but I'm not sure if I wanna add it back to my phone because I, I feel like maybe I wanna get a couple more weeks under my belt before I decide that it was actually maybe something I want to change my mind about.

[00:04:58] **Adam:** Yeah. I mean, you're not totally disconnecting from social media. You're just not doing it in those moments where you, you know, Should just be allowing your mind to wander or appreciating the peace and quiet.

[00:05:09] **Ben:** Yeah. It's true. And I'll tell you. And I have enjoyed just letting my wind wander a lot more. I mean, I fill a lot of that void with podcasts and well podcasts really. And, I've started to try and listen to music a little bit more just on, on the go, which I, I sort of gave up listening to music when I started listening to podcasts when I'm, you know, away from my computer.

[00:05:31] **Ben:** I'm trying to let my brain just relax a little bit more and, and kind of

[00:05:34] **Adam:** yeah. I'm, I'm addicted to productivity,

[00:05:37] **Ben:** Yeah, I I, I, I know exactly what you're saying,

[00:05:39] **Adam:** yeah. Like, once I discover it, that I could listen to podcasts and audio books while I'm driving, while I'm in the shower, while I'm, I don't do it at the urinal. Sorry, Ben. But like, well, you know what, if I'm already listening, then I won't stop it because I'm going to pee.

[00:05:53] **Adam:** That's, you know, but, but yeah, like it. It started out as like, Ooh, I can reclaim all this time that I'm just kind of wasting right now. And then it just became this obsession of like, okay, now I can read three books in the next three weeks and I can also do this and also do that. And it just became this like unhealthy obsession with getting as much stuff done in as little time as possible.

[00:06:17] **Ben:** Yo,

[00:06:18] **Adam:** I can see it happening, like I still do it and it, and it, it's almost like I can't stop it. Sometimes I can, you know, sometimes I'm intentionally like, okay, no, stop. let's take a break. But it's hard

[00:06:29] **Ben:** It is hard. And then I find myself feeling exactly the same way where I can't stop myself, cuz I have kind of, I have two genres of podcasts. I have tech podcasts, and I have like, I

[00:06:41] **Adam:** beekeeping.

[00:06:42] **Ben:** podcasts. You gotta love a good apiary. and what I have found myself doing over time is, is sort of pushing all of the human interesty podcasts to the side.

[00:06:55] **Ben:** like scouring, sc scavenging,

[00:06:59] **Adam:** scouring.

[00:07:00] **Ben:** scouring. Yeah. I'm like scour Melissa. Like, oh, where's, where's the, where di I must have missed a tech podcast. Like I must have missed a,

[00:07:06] **Adam:** words. We

[00:07:06] **Ben:** uh, yeah.yeah. Yeah. and I end up listening to podcasts that I, I don't even think I enjoy that much, but, but I listen to them because they're tech podcasts and then, If I totally run out and I go and listen to something like how I built this or this American Life, I'm like, oh man, I remember why I love these shows so much.

[00:07:23] **Ben:** These are great shows, but I've, I've denigrated them almost to like the second class citizen in the podcasting world, which is totally, it's, it's unfortunate.

[00:07:32] **Adam:** There are a couple that I've found myself, for lack of a better word, I will say, like hate listening to, like, hate watching a YouTube thing or, or hate, not because I don't like the people or don't like the thing, but it's like I, I feel a personal responsibility, like to myself, to keep up on the, the whatever the topic that they're discussing.

[00:07:50] **Adam:** But in, in recent weeks, I have given myself permission to just be like, you know what? I don't care about this one. They're talking about, you know, this particular feature of CSS that will never matter to me because I don't, you know, I don't do whatever that type of animation or that, was probably a little too, in my ho in my wheelhouse to be a good example.

[00:08:10] **Adam:** But you get the idea. Like, it just, it doesn't interest me. It'll never apply to me. So I'm just gonna skip this one. And, that's been nice to help keep my backlog from getting out of control again.

[00:08:21] **Ben:** Yeah, so I'll report back in a couple weeks and, and see where we are. See if I'm still social media free or if I've gone back to, to the, the dark side.

[00:08:31] **Adam:** Sounds good.

[00:08:33] **Ben:** Anyway, how about you? What do you got going on?

## [00:08:35] Adam's Failure

[00:08:35] **Adam:** So I am gonna go with a fail this week. I, it feels recently, I was gonna say, I, I have recently returned from Princeton's, alumni reunion. I am not a Princeton grad, but my company works at, you know, university events. They're big, you know, homecoming, reunion, commencement, these sort of large events where they have tons of people on campus and they need to manage a check-in and registration experience and, and, deal with all of that stuff on site.

[00:09:01] **Adam:** And it was a great weekend. and, and compared to last year, we were way better in just about every possible way. Certainly there's things that we took away from it that we could learn and do better from. But the hardest part about the whole experience was that, it was like one sort of normal-ish workday followed by three 18 hour shifts in a row.

[00:09:20] **Ben:** Brutal.

[00:09:21] **Adam:** yeah, it, it was absolutely brutal. you know, it was working, we had to be on campus at like 8:30 AM and we were released to go back to our hotel room at like somewhere between two 30 and 3:00 AM only to get up and do it again the next day, right? From, so you, from two 30 to to eight 30, you have to drive back to the hotel, you know, whatever your, your personal, if you're an evening shower, morning shower, whatever, but you have to sleep, you have to shower, you have to, you know, eat breakfast.

[00:09:48] **Adam:** You have to, you know, whatever other stuff you need to do in that period. And then you're right back on campus for in, in six hours. Right. Including sleeping, which was,

[00:09:57] **Ben:** oh my God. That's crazy.

[00:09:59] **Adam:** but it, you know, we're, we're working on, Learning how we can reduce staff needs and like, rely more on, the, the university.

[00:10:08] **Adam:** They, they like get their student workers to help out. They have staff that volunteer, they have all kinds of people involved, but it's, it's a long day necessarily. and so we're, we're learning what it will take to, you know, split it up into shifts and have people be doing, you know, easy jobs and, our staff hopefully just kind of, playing, you know, like dispatch Right.

[00:10:28] **Adam:** Sit somewhere stationary and run the show, but the people running around doing stuff be, you know, sort of hired help.

[00:10:35] **Ben:** When you go to Princeton now, or you know, like this last time, is it, is it, I assume it's not just you, ed, what is it? Two people or three people?

[00:10:43] **Adam:** this year we had, four of us.

[00:10:46] **Ben:** Oh, wow.

[00:10:46] **Adam:** Yeah. And I mean, that's, that's us again sort of doing the, you know, we're the top of the food chain, but then, you know, Helping us out. We had a lot of, student workers and staff and, and volunteers from the, different alumni classes. And then a and that was like, you know, running the technology pieces, at the, at the gates where people were showing up and checking in and getting their wristbands.

[00:11:10] **Adam:** and then the, we have special hardware. It's basically like an Android phone with a, like a scanner, like sort of similar to what you would see at the checkout at a grocery store or, you know, self checkout at Wawa or whatever. where, you know, so a little, just a little barcode reader sort of deal baked in.

[00:11:27] **Adam:** We have some with like a, a cradle, or some, it's, we're working on the terminology. It's like a cradle or a sled. We're trying to avoid any, gun metaphors cuz especially being on college campuses. Like, you just gotta avoid that. But it does very much look like, like a phaser. We were fir, at one point we were calling them phasers cause they look like Star Trek, phasers.

[00:11:45] **Adam:** but yeah, it's just like a little Android phone with a baked in, you know, QR code reader. And we use that and, and it acts as a keyboard, right? We use that to fill in, a text input and it hits enter after it reads and, and you just do validation through that stuff. and so those things were run by, uh, campus security.

[00:12:03] **Adam:** I, they have their own sort of like police force and then they also have, public safety, which is sort of like campus police light as far as I could tell. And I apologize if that's offensive. You know, I'm, it's, if it's, if it's wrong, it's because I'm an idiot, not for any other reason. and, and all of these people were amazing, you know, a lot of them were with us last year as well, and they, they noticed the improvement and they were happy with it.

[00:12:24] **Adam:** And, you know, tho those people were doing the hard part, right? We were running around making sure the technology worked. They were standing at the gate for hours on end, scanning people's wristbands and. Looking for fakes, cuz that's a big thing that happens

[00:12:37] **Ben:** Really at an

[00:12:38] **Adam:** Yeah. Oh yeah, yeah. Well, I mean, it's,

[00:12:41] **Ben:** their, I guess, is there free beer? Is that the Gotcha. Okay.

[00:12:44] **Adam:** Yeah, there is free beer and, and yeah, exactly. and, and so you, I told you, you get a wristband and, and obviously you, it's got a QR code on it. There are people who are so excited about coming back for their reunion that they post a picture of their wristband with the QR code on, on their Instagram or something, and Yeah.

[00:13:06] **Adam:** So,

[00:13:06] **Ben:** that's funny.

[00:13:07] **Adam:** yeah. And it, it's, it's kind of hilarious to see it all happen, see it all play out, but at the same time it's like, you know,

[00:13:13] **Adam:** you have a responsibility to try. Yeah. Well, yeah. It's a whole thing, right? So it was like 26,000 people registered, 24,000 people showed up, which was a, a really great attendance.

[00:13:25] **Adam:** Yeah.

[00:13:26] **Ben:** people.

[00:13:27] **Adam:** Yep. And they all have to get wristbands and you have to, you know, you have to card people and do, adults and minors, and you have to. you have a couple VIPs mixed in. Yeah. It's a whole big thing.

[00:13:36] **Ben:** when does prep work? So you're gonna Princeton how, I mean, you're not printing out stuff, but it sounds, it sounds like you're helping coordinate with the university. You're getting these volunteers. Like how much, how much ahead of time, you know, I'm arriving on Day X at Princeton. How early do you have to start talking to Princeton and talking to whoever does stuff there that's going to get equipment, get volunteers?

[00:14:00] **Ben:** Like how much time does that take?

[00:14:01] **Adam:** The, I think the best way to explain or to answer this question is so, planning for next year will start seven to eight weeks after this year ended.

[00:14:11] **Ben:** Geez. Holy cow. That's been bonkers.

[00:14:14] **Adam:** Yeah. I mean, it, it's, it's not a hundred percent necessary, right. We're not, we're not dedicating a bunch of people to be a hundred percent on this until then.

[00:14:22] **Adam:** Mm-hmm. You know, they will do a, a lot of the planning, and the, the prep is done by the university. we were just sort of involved from a technological standpoint. We have a lot of check-ins and stuff, but you know, we have to evolve the technology as well cuz Right. You know, people, a couple of years into this, people know what to expect so they're like, you know, maybe I, so for example, right, the, the wristbands change their fabric wristbands and you, they have a, a special class bottom that once it's on you cannot remove it until, without like, cutting it off.

[00:14:49] **Adam:** Right? So the idea is it'll be easier to spot somebody who's like just holding it on cuz it's been cut off sort of thing. If they're like, you know, get in and try to throw it over the wall to the next guy, whatever. well, so people I guess saved them from last year and then tried to, like use a marker to like change the color of it so that it more easily blends in with this year's and then they like tape over a QR code that will scan prep properly from this year.

[00:15:15] **Ben:** that's

[00:15:16] **Adam:** Oh yeah. It's like a whole black market for these things, man.

[00:15:20] **Ben:** I

[00:15:20] **Adam:** so hilarious to see. Oh yeah. It's great cuz it's, it's mostly, to be honest, it's mostly high school kids trying to sneak in to get free beer. and they work so look, they work so hard to, to, to be honest, I have a tiny amount of respect for how hard they are working.

[00:15:37] **Adam:** But really at the end of the day, you were putting in how many hours to get like two free Coors lights, right? Like, I don't know.

[00:15:46] **Ben:** oh.

[00:15:47] **Adam:** So anyway, that, that was quite a, quite a ramble. I don't even know if I got to the point of that.

[00:15:52] **Ben:** I don't, I don't think so. Cause I'm seeing there's about

[00:15:54] **Adam:** Yeah. Yeah. So the, the whole point was I worked these really long shifts and in order to get through them, I was, I was a, a fiend for the caffeine.

[00:16:02] **Adam:** Mm-hmm.

[00:16:03] **Adam:** you know, I, I was having three, four monsters a day plus other soda, and, and you know, whatever. And absolutely. And it worked for the most part I felt. You know, like a zombie on days two and three of those three 18 hour shifts, and for like two to three days after. But, the thing that's been hard now is, you know, I worked so hard to get down to my two mountain Dews a day, you know, as my, my baseline.

[00:16:30] **Adam:** And now I'm coming home and I'm like, I can't, I can't function, I can't human without a little bit more chemical assistance than I'm used to

[00:16:39] **Ben:** I understand. I understand. I, my, my thing when I have more caffeine is that I then, I can't sleep well. So then I have to start taking Advil PMs to knock myself out at night, and then I'm extra groggy in the morning. Yeah. And then I, and I need to counteract with even more caffeine the next day. So it's a, it's a cycle.

[00:17:00] **Ben:** It's a cycle of triumph.

[00:17:01]

## [00:17:02] Ben's Fitness App

[00:17:02] **Adam:** okay. Well, I guess then let's switch gears and switch into stealing a format. Ben, how's your thing going? What's the thing you're making?

[00:17:15] **Ben:** so I have forever wanted to build a fitness tracking application, and I,

[00:17:19] **Adam:** don't say.

[00:17:20] **Ben:** and I actually built one 13 years ago, in a weekend. It was ColdFusion. It has like, it had like four pages in it, and it did just enough to do basically what I wanna do in this application, but it, it wasn't architected very well, obviously.

[00:17:35] **Ben:** I mean, it's 13 years ago, I barely knew what I was doing in programming and, it, it was originally designed so that you could track multiple people's workouts at the same time. which just didn't end up being the way that I wanted to use the application. And just like, there's all kinds of stuff that was bad with it.

[00:17:52] **Ben:** Anyway, I stopped, I stopped even caring about that one years ago, so I wanted to rebuild it. To say, rebuild it. I wanna start from scratch. I deleted everything, deleted the database completely, you know, nothing in the finder folder. and it's weird to start from scratch. You don't start a project from scratch very often.

[00:18:12] **Ben:** I haven't really started anything from scratch in years it feels like. And, there's a lot of questions that have to be answered in the beginning of a project that you don't think about. You don't have a lot of practice, right? You don't have that muscle memory of, of how you wanna put things together.

[00:18:25] **Ben:** Plus your perspective on how code is organized has changed over time. Your perspective on architectures has changed over time. Your perspective on database schema has changed over time. So there's a lot of, you know, old mental models, new techniques, and just kind of rusty approaches that, it, it's weird.

[00:18:42] **Ben:** It's hard to get that, that momentum going. Even just trying to figure out how to organize the site. So, It's gonna have a, a logged in section and a public section like, like a marketing page and you know, click here to log in, sign up. And even just, should that be two separate sites? Should that be the same site where the logged in part is just a subfolder of the, of the main site?

[00:19:04] **Ben:** And then, I don't know, like I didn't know how to answer those questions. And then I started to look at how cookies get organized and, and would it make sense to have cookies be separated from the marketing site versus the logged in site. And that sort of felt like the more secure options so that I could really segment out my cookie storage.

[00:19:23] **Ben:** And so I ended up going with, I'm gonna have the dub dub dub site be the, the landing page. And I'm actually on the, on the public site. I'm, I'm listing my change log. So as I'm adding functionality to the app, I'm listing out what I've done. And I mean, you can't even log in yet. But, you know, I'll say like, oh, I'm like, I put my IIS sites in place and I.

[00:19:44] **Ben:** I, I figured out how to use Lets Encrypt. I didn't figure it out. Host Deck, which is my hosting provider, they actually have Lets Encrypt built into their control panel now, which I didn't even know. That's pretty exciting. So I can now get SSL certificates just, with a click of a button, which is pretty fantastic.

[00:19:59] **Adam:** That's cool.

## [00:20:00] Separating Marketing and the App

[00:20:00] **Adam:** Do you want to do, like, is it too late or do you want to have some of these discussions? Like the, the, I have thoughts

[00:20:06] **Ben:** yeah, yeah, yeah. I'm, I'm just, I'm just rambling, so Yeah. Please jump in.

[00:20:10] **Adam:** The, the marketing site being separate versus, you know, sort of part of the application that handles the rest of the application.

[00:20:18] **Adam:** There's, I think there's valid reasons to go both ways, right? So like the first thing that brings to my mind is like, is it a big deal if one of them going down takes both of them down? Right? whether that's for a maintenance issue, if you're rebooting the server, or, or if it's for, you know, a bug crash or, or whatever. you know, if you split them, then you have a little bit more resiliency between them. the other thing that I particularly like is just being logged in when I get there, which cookies will do for you. I, I will say too, you mentioned cookies. I hope I, I have an opinion and I'll just go with my strong opinions and I'll, I'll stop trying to be diplomatic about

[00:20:58] **Ben:** all about strong opinions

[00:20:59] **Adam:** Yeah. there's no need for, for cookies on the marketing site.

[00:21:03] **Ben:** Yeah, a hundred percent. That's what, that's what I'm feeling right now.

[00:21:06] **Adam:** Except, you know, if, if it is sort of integrated where like you drop onto the marketing site and if you already have your logged in cookie, then it's like, you know, you're already logged in. Go ahead and click here to open the application, whatever. One thing I will say that drives me nuts is applications where you, like, you can't get to the marketing site while you're logged in.

[00:21:23] **Adam:** You have to like open it in incognito or, or something like that. It's like, come on. I just, I wanted, somebody asked me about how much your product costs and I wanted to give them the pricing page link, but I can't get to the pricing page cause I'm logged. Like, screw you just

[00:21:37] **Ben:** One, one thing that I've found as a consumer of other SaaS products, the experience that I like is you go to the marketing page because that's, you know, you either don't remember it and that's what you Google for, or you remember it, but you don't remember how the, the authenticated version is, and they show you the marketing page and they show you the, the login button, so they don't even know, necessarily know that you're logged in.

[00:21:58] **Ben:** But then you click the login button and they just take you to the app. Like they, it's not like a forced login page. Once you click the login and they take you to wherever you need to go, at that point, I assume all the cookies kick in and they know who you are and they know whether or not you're logged in.

[00:22:12] **Ben:** So it's, it, it, I, I'm, I'm actually pretty pleased with that experience. I don't mind. Seeing the login call to action if clicking it, you know, doesn't force me to do anything unnecessarily.

[00:22:24] **Adam:** Right. If you're already logged in, it's not gonna make you re-log in. Yeah.

[00:22:28] **Ben:** So, so that's what, that's what I'm gonna go with right now. and

[00:22:32] **Adam:** like you were gonna do like a subdomain for the, the app itself,

[00:22:35] **Ben:** yeah, so you're gonna go dub dub dub, it's, so, the, the app is

[00:22:38] **Adam:** It's big, sexy muscles.

[00:22:41] **Ben:** it's called Dig Deep Fitness.

[00:22:43] **Adam:** so, so the public site is dub dub dub Dig Deep Fitness.com, and then the app will be app dot Dig Deep Fitness.com. So it's, it's just a separate sub-domain. just a Microsoft Word document

[00:22:56] **Ben:** say what now?

[00:22:58] **Adam:** design-wise. It's just, it's just, Black text on a white

[00:23:01] **Ben:** Oh, yeah, yeah, yeah, yeah. A hundred percent. There's no, there, there's no, I'm, so I'm trying to do the least amount of work possible.

[00:23:09] **Adam:** for sure.

[00:23:09] **Ben:** there's no design system or anything I want to do. I wanna get like all the data storage stuff ready to go before I even really start to think about how it should look and, and the, and the user experience.

[00:23:21] **Ben:** I mean, I sort of have some of that in my head already, but, you know, it's so easy to go down rabbit holes. You know, you wanna, you wanna start trying new things and experimenting and like, I'm already finding myself guilty of experimenting probably more than I should be for just trying to get something off the ground.

[00:23:37] **Ben:** But I, I am trying to do the bare minimum that still makes me feel proud of the code, but doesn't solve a problem that I don't have. If I get sum it up, like I only wanna solve the problems that I actually have right in front of me right now.

[00:23:52] **Adam:** Can I,

[00:23:53] **Ben:** yeah, please jump

[00:23:54] **Adam:** it anyway. What you're doing is you're doing t d D, but you're just not writing any tests,

[00:24:01] **Ben:** I was thinking about tests too, which is funny because, so if I can walk you through how I build a little piece of functionality. So the very first thing I had to do was figure out how I'm gonna store a user. I need people in the system, they have to have a representation of the database. So I created a user table and I think, I think the only thing it has is an id, which is just an auto incrementing, big integer, an email address and like a created ad and an updated ad.

[00:24:26] **Ben:** Like that's all I have. I don't have a name, I don't have anything.

[00:24:30] **Adam:** set the seed for that auto incrementing beginner, like 6 million. So the first user is 6,000,001.

[00:24:37] **Ben:** I could, I could change that. I could change that. and, and it was even just having a name. I'm like, oh, someone will probably wanna put a name. Maybe I should put that in. I'm like, I'm not gonna put a name right now that, that's not a problem that I actually have. I don't even have passwords. So the, the initial, I haven't even built the login system, but I, I think all the login is gonna be a magic link based.

[00:24:58] **Ben:** I don't know if Magic Link is like a technical term or if it's a term that some marketing sites have used, but a magic link, basically you'll say, Hey, I wanna log in. I put in my email address. That system sends me, a signed URL essentially that says, okay, here, you verified your email by clicking on this link, and I will either log you in or create an account and log you in.

[00:25:18] **Ben:** And,

[00:25:19] **Adam:** Hmm.

[00:25:19] **Ben:** so no passwords will be required.

[00:25:22] **Adam:** Nice.

[00:25:22] **Ben:** Yeah, at least initially

[00:25:24] **Adam:** up as as easy as just gimme your email address.

[00:25:26] **Ben:** a hundred percent. And then it also means that someone has to have an email address. I mean, there's ways around that. Obviously there's all kinds of like, give me a garbage email address service that I never have to think about again.

[00:25:36] **Ben:** But,

[00:25:37] **Adam:** What are you gonna do for people who wanna share an email address?

[00:25:40] **Ben:** I, I, I don't know.

[00:25:41] **Adam:** like, it's, it's a real problem that I have to deal with every day at work, but I, I was just kind of just giving you, just

[00:25:47] **Ben:** Yeah. Yeah. Yeah. I mean, I think the user experience just won't be good for them, cuz it, the weights are your weights, you know, the exercises are your exercises. So if you're sharing with someone, it's gonna be confusing.

[00:25:58] **Adam:** absolutely. Yeah. And, and honestly, on that page, I would just put the thing that says like, your, your email address is your identity in the app, and if you share an email address with somebody, don't, they're free.

[00:26:10] **Ben:** right. Yeah, exactly. Exactly.

## [00:26:11] Testing

[00:26:11] **Ben:** Oh, so I wanna, so I wanted to talk about testing cuz I'm, I'm, as I'm telling you this, and, and you know, as people will listen to this, I'm sure they'll be screaming into the, the podcast player like, you idiot. Like, you're testing, but you're not recording any of it. so basically what I do is I say, okay, I have this user table, it's got a couple of columns.

[00:26:30] **Ben:** so I will create the data access ColdFusion component, which is just all the, basically the create, update, delete, and, read queries. So it's, it's like, it's the low level SQL stuff. So I'll put that in place and then I'll create a little scratch file, you know, scratch a C F M file and I'll instantiate that component and I'll send some data into it and I check the database.

[00:26:51] **Ben:** I'm like, that looks good. And then like, I'll read, you know, I'll call the read from it and I dump it out to the page. I'm like, yeah, that data looks good. I'll try to request a file, record that I know doesn't exist and it either throws an error or I catch it and I say, oh, it didn't exist. So I basically do, I think a lot of what tests would do, except once I'm done, I just delete that scratch file and I never think about it again.

[00:27:12] **Ben:** I'm like, I've already validated that this code works, so, you know, if I ever make changes to that, I'll just have to come and do the same thing again. But, but, I don't have to have the test live there forever. Just taking up space. I mean, I'm obviously being a little facetious, but,

[00:27:24] **Adam:** Yeah, you wanna leave a comment on this podcast? Go to working Code dev slash Discord.

[00:27:30] **Ben:** So I'll, I'll do the, I'll do the data access, and then usually I have a, a, I call it a service layer. I have another cold vision component that sits above that, which does more of like the taking in the data and massaging it before sending it down to the lower level data access. And again, I'll do the same kind of thing while I'll create a little scratch file.

[00:27:48] **Ben:** I instantiate that. I instantiate the gateway, I wire them together. I start making a couple of calls, make sure that all the calls gimme the right data or don't give me the data if the records don't exist. And again, I feel satisfied that it works. I throw away the scratch file and I basically never think about that code again.

[00:28:03] **Ben:** And I sort of just iteratively do that as I'm building out the application. So I, I am testing, I just don't do it in any automated

[00:28:13] **Adam:** doing it in the hardest way possible. You're not automating it, and, and then you throw it away so that if you ever need to repeat that test, you have to start from scratch again.

[00:28:23] **Ben:** You know, the, the, the issue is, is like I don't wanna ever mock anything. I just, I'm not, I I,

[00:28:28] **Adam:** Yeah,

[00:28:28] **Ben:** the problem is that there's a database at the end of the day, there's a database that's pretty complicated piece of software. And I don't want to have to build out something that fakes what the database is doing.

[00:28:38] **Ben:** e e every time I look at an application at work and they're doing, they're jumping through all kinds of hoops to get data to work. And I'll tell you it, it's like I spend 30% of my time editing the code and 70% of my time just trying to get the tests to work cuz they're so complicated and they're breaking for weird reasons.

[00:28:58] **Ben:** And, I'm, I'm sure a non-trivial amount of that is me just not being familiar with whatever framework that that one particular team happens, be using that one particular repo because it's a different testing framework than the other team on this other repo. And it's, it's all over the place.

[00:29:12] **Adam:** yeah. Testing is great until you get to that point where you're like, okay, now how do I mock this? And then you spend three days trying to figure out like how to, how to mock one specific use case. You know, like, I need a, I need a particular database query in this chain of actions that's gonna happen. You know, like once we get seven layers deep, I need it to throw an error so that I can test this possible thing.

[00:29:33] **Adam:** Right? Like it gets, it gets hairy. and that is, especially when you're switching between testing frameworks and things, it gets very frustrating very fast.

[00:29:44] **Ben:** It does. So I sidestep that entire thing by not doing any testing, and so far I have not generated any bugs.

[00:29:53] **Adam:** Yeah. I mean, we just decided architects were too expensive, so we just poured, pour some concrete and stuck some rebar into it and we'll figure it out as we go.

[00:30:03] **Ben:** Oh.

[00:30:04] **Adam:** No, I mean, look, it's awesome. You're building something and it, you're, so, it seems to me that you have. Created a, a thing that you're excited to work on. right. It's a little skunkworks project where you can try new things, you can learn stuff, you can get some more recent greenfield experience. These are all great.

[00:30:22] **Adam:** one thing that springs to mind is that a while back, if I'm, if I'm remembering correctly, you wanted a project specifically to get yourself something to do with like docker, right?

## [00:30:33] Stack and Deployment

[00:30:33] **Ben:** yeah. But yeah, so, yeah. Yeah. Okay. So, so last year, my, my, my 2022 goal, which if for those listening, it's today is 2023. So my last year's goal was to do something that would allow me to build a docker image, deploy that image somewhere, and use, let's call it a grown up. Ci, continuous integration, continuous delivery type of approach.

[00:31:01] **Ben:** that 100% never happened. not a single line of code of that actually happened. So there was basically no effort put into that whatsoever. this is going completely the opposite direction. I'm just leaning into the fact that I have a V P S and I'm literally going to be FTPing these files to my server.

[00:31:20] **Ben:** And you know what? It kind of sucks. I, I, I, it kind of sucks, but like, again, I know it's gonna be so easy to go down rabbit holes. And my, the purpose of this is to build a business tracker. This is not necessarily a technology learning endeavor. This is a, I want to build a thing and

[00:31:40] **Ben:** I

[00:31:40] **Adam:** of an application thing than an infrastructure thing.

[00:31:42] **Ben:** yeah, yeah, yeah.

[00:31:43] **Ben:** So I, I just wanna do the least amount of stuff that it's gonna take to get this done. I still want it to be done well, I still want it to be architected. Well, I just, I, I, it's, it's not the right time for me personally. To worry about, you know, deploying an image and having bluegreen deployments and rolling restarts.

[00:32:02] **Ben:** Like, Hey, you know what, sometimes I'm gonna be able to deploy code via FTP and it's gonna be fine. And you know what? Sometimes there's gonna be race conditions and like certain files are just gonna break mid deployment and like, I don't, you know what it, I'm just gonna live with it for now.

[00:32:17] **Adam:** You, you said you have a VPs. Do you wanna explain what that is for

[00:32:20] **Ben:** Yeah. So a VPs is a virtual private server, which essentially means I have what looks like my own server somewhere. I use Host Deck. it's a ColdFusion hosting provider

[00:32:31] **Adam:** Not sponsored.

[00:32:32] **Ben:** not, not sponsored. and I don't know, it's, it's not a real computer. It's like some slice of a much larger computer, I assume is how it works.

[00:32:41] **Ben:** That's the virtual part. And, but I, I log into it like I would log into a computer, I can ftp, I can create, I sites and iis and, Yeah, it's like having my own server, but, but it's, not mine.

[00:32:54] **Adam:** Did you, so you consi you said you're on v ps, you said you're on windows. You said you're gonna FTP stuff in. Did you consider

[00:33:01] **Ben:** Checking all the modern boxes right there, baby.

[00:33:05] **Adam:** yeah, I mean, that's a, that's a, that stack doesn't even have a name yet. It's so, so hot and fresh.

[00:33:24] **Ben:** Oh man. It's so

[00:33:24] **Adam:** Oh, mission accomplished. Man, any show that'll make you crack up like that is good. did you consider, just like cloning the get repo and, and letting that be your deployment strategy, like remote desktop

[00:33:36] **Ben:** like doing like

[00:33:37] **Ben:** a get

[00:33:37] **Ben:** poll. Oh, you know what? That's a, that's a, that's a really good idea. And actually at, in, at Invision, so at Invision we have like a full image-based fancy deployment system. We use Code Chip, it does magic. I don't understand

[00:33:49] **Adam:** Mm-hmm.

[00:33:49] **Ben:** In the early days, that's what we did. We used to, essentially, so lemme lemme try to remember what it was.

[00:33:56] **Ben:** So there, in the early days of Invision, there were two folders that lived next to each other. There was like the pre-release folder and the production folder, and we would log into the server, we would do a get poll in the pre-release folder, and that had a special subdomain you could check to make sure everything looked okay.

[00:34:17] **Ben:** And then once you validated that, everything looked okay, there was like a, like a folder sync where you'd say, okay, now sync all the files in pre-release to production. And, and it was live. And you know what, it was actually pretty easy. maybe I should do that.

[00:34:32] **Adam:** Yeah, I mean we, we have two products and the one that I am very heavily involved in our platform, we are. Down to of, I think at our peak we were at 13 servers maybe, where you had to, for every production deploy, you had to remote desktop in, open up a command line, which we usually just left it open anyway.

[00:34:54] **Adam:** and then just go in and do a get pull. and we're down to only one of those remaining. All of the rest have already been turned into, like auto building containers that go through ci. They build from Git and they, they automatically deploy on ECS on aws, which is fantastic and great. It's, it's not without its own challenges, but one thing that I sleep so much better at night, as a result of this change is that no, it is impossible for someone to go on and make an UNC uncommitted change in production.

[00:35:24] **Adam:** It's just not possible. We don't have SSH on these machines. The only way to change what's up there is to deploy a new, updated version of the application.

[00:35:32] **Ben:** Sounds very so compliant.

[00:35:34] **Adam:** Oh, it very much is. And that that one remaining server will be going away, as soon as I can make it happen. And I, and we were actively pursuing it, so

[00:35:44] **Ben:** I, I'll tell you, and what's great about the GIT deployment, the GI based deployment, is that it knows all the files that have changed. you know, even not from a, from a change manager standpoint, but just from a, did you actually get all the files you meant to get, to get, because I have definitely, in my history of FTPing files just missed a file.

[00:36:03] **Ben:** And then you go to the site and you refresh it and all of a sudden, you know, all the content's gone just as an error occurred. And you're like, oh, what? Like,

[00:36:11] **Adam:** What did I do? Okay, well just do the whole directory. It's gonna

[00:36:13] **Ben:** Right. Yeah. Yeah.

[00:36:14] **Adam:** but,

[00:36:16] **Ben:** So, you know, that just doesn't happen with Git, which is pretty

[00:36:18] **Adam:** yeah. Well, so what, what ends up happening is you just move the problem, right? So now instead of forgetting to deploy a thing, you forget to commit it. Right. So like, you know, you, you acc you forget that you added a file and you're just on your terminal and you're like, get commit dash, here's my message.

[00:36:34] **Adam:** Get commit messages are hard, enter, get, push. And you're like, you know, you don't, you don't think, oh, I added a new file and it's not gonna get picked up by that. So.

[00:36:45] **Ben:** You know, my, so the thing that will always happen to me is I will, I'll have the files all ready to go and I'm looking at my, and I'm looking at my PR or you know, or I'm looking at like a get diff and I see something that I missed in the Diff and I'm like, oh, let me go edit that. So I'll open up the file, I edit it, and then I forget to save it.

[00:37:03] **Ben:** So then I do get status. It looks like everything's been saved. And then I push it and it's broken. And then I, I like, I go to Checkout Master and it'll be like, oh, you can't check out Master, cause you have Uncon, uncommitted changes. And I'm like, what? Uncon uncommitted changes. That's not good.

[00:37:18] **Adam:** Yeah. Man, I feel like I, I've been served pretty well by a habit I picked up when I was a teenager, which was just like, save constantly, like at the end of every line I'm hitting save

[00:37:29] **Ben:** yo, absolutely. That it, it actually drives me, it drives me crazy when I'm using it. Just like I'll open up a temp file just to like, maybe just do some text, some text manipulation, not cause I actually care about it and just out of habit, I constantly hit command S and they'll say, oh, you wanna save this file?

[00:37:46] **Ben:** I'm like, no, I don't wanna save this

[00:37:46] **Ben:** file, go away. But then I'll type like one more word and I hit command S again. I'm like, no.

[00:37:52] **Adam:** Yep,

[00:37:53] **Adam:**

## [00:37:53] Error Logging and Sessions

[00:37:53] **Adam:** cool. So we talked a little bit about users. You just have a table with email addresses in it. this is your Greenfield, so like all the other, you know, greenfield stuff. Like what are you doing to, for like error logging?

[00:38:04] **Ben:** well, yeah, so that's the thing. It's like, again, there's all these hurdles you have to get over that once you build the application, adding features becomes just incremental. But there's this huge hill you have to get up. Error logging. So I'm, I'm using Bug Snag, which I've, I switched over to Bugsnag like a month or two ago.

[00:38:21] **Ben:** Not sponsored, but really just a really great user experience. I've been really enjoying it. Just, it organizes the bugs really well. But in order to get things in bug snag, I had to create a Bugsnag client, in ColdFusion, which is really just a single p I call, an H C P A P I call, but then I have to build an error management system.

[00:38:43] **Ben:** By that I just mean like I have to do, like, I have to have the tri catches in place at the root level to catch errors that weren't caught. And I have to feed those into the, to the bug log. So like I have to get that stuff working. And then, and now I'm starting to work on, on actually getting the user logged in.

[00:39:04] **Ben:** And I didn't want to use ColdFusion's, native session management, cuz that's just stored in the server. And

[00:39:10] **Adam:** Mm-hmm.

[00:39:10] **Ben:** don't know, I, I've sort of soured on the idea of having in memory, Sessions over the years. You know, at at work we use Reddis to store our sessions. We used to use MySQL. I don't have anything fancy, so I'm just gonna store my sessions in my

[00:39:24] **Adam:** Client variables? No, don't do that. But

[00:39:29] **Ben:** No, don't do that. but it,

[00:39:32] **Adam:** you're gonna store 'em where?

[00:39:33] **Ben:** I'm, so I'm just gonna, I'm gonna have a user, I think I just called it, user session table, which has

[00:39:38] **Ben:** a, it's gonna have a, an auto incrementing big in as the session id. And then I'm gonna have a, a 64 bite random value as the token value for the session. And then I have the user ID and like the date it was created and I think I logged the IP address for

[00:39:56] **Adam:** So the token is what goes into the cookie or whatever.

[00:39:59] **Ben:** Yeah, I think what goes into the cookie is like the, ID like the, the session ID dot the session token. And so, that'll get sent to the server and I'll. It's basically a.limited list. The first thing is the id, I get the record based on that and then I do a comparison of the token against the thing in the database.

[00:40:20] **Ben:** but do we, so I had, I haven't had to set up a new session in forever, so I, I'm like, oh, how long does the session have to be like, should I have some sort of a signing key or something like I, like I literally don't remember doing this stuff cuz I've been working on the same application forever. So I was, I was looking on Owas, which is the open web application security project.

[00:40:43] **Adam:** Yes.

[00:40:44] **Ben:** Fantastic project. And they have like a million cheat sheets. So they have a cheat sheet specifically for session management. They talk about how long IDs have to be and how long they should live and how they have to be locked down. And that you should be using cookies because cookies have the most security options.

[00:41:01] **Ben:** And they were like, local storage is pretty junky, but you could use it but not so great. And cookies are really the way to do it. Cuz you can have. You can say like, cookies are secure only you can say that they're only HDP accessible, so you can't access them through JavaScript. You can say like, you can only access them from the same sites.

[00:41:18] **Ben:** You can't do some, some cross-site request forgery stuff. you can lock 'em down to domains, you can lock 'em down to paths within the server. Like there's all kinds of like, really awesome stuff that cookies can do.

[00:41:28] **Adam:** Yeah.

[00:41:30] **Ben:** anyway, so, but like, you know, again, I, I don't want to build anything that's insecure, so I, I want to get this stuff right, at least, you know, try to get it right the first time.

[00:41:40] **Ben:** But it's, it's like relearning a lot of the stuff that I've taken for granted for so long, having worked in an established application.

[00:41:46] **Adam:** Sure.

[00:41:48] **Ben:** Whoa,

[00:41:48] **Adam:** liking Bugsnag? Have you, have you sent much over there yet?

[00:41:51] **Ben:** Yeah, it's really great. It's really great. they, they group things really well and then, they have good, I mean like, this is a really silly thing, but, in Gmail you hit, shift three to delete things and shift three.

[00:42:05] **Ben:** Works in bug snag also. So I'm like, awesome. That's just like a sweet convenience.

[00:42:10] **Adam:** That's bizarre, but Okay. Sure.

[00:42:12] **Ben:** Hey, I, I, I don't know, whatever. It's just great. So it has, it's just, it's just really good. I'm just really enjoying it.

[00:42:18] **Adam:** there have been like four times in my life that I really tried to be like, okay, this is, this is it. This is gonna be the month that I learned the Gmail keyboard shortcuts. And I think it's very

[00:42:27] **Ben:** the only one I know.

[00:42:29] **Adam:** Yeah. I think it's very heavily based on, I think e is archive. That's, that's one that sticks out in my

[00:42:34] **Ben:** Yes, I think you're right. I'm like, I got my hands on the keyboard. I think e is archive shift three is delete, C is composed forward slash is like focus the search input, and I

[00:42:46] **Adam:** okay. That's pretty, yeah, that's pretty common.

[00:42:49] **Ben:** that's, that's all that I know.

[00:42:50] **Adam:** Okay. Well, yeah, it is just too complex for me. I feel like if I was a regular Vim user, that might be different, but I feel like they're very, like the, the navigation move up and down

[00:43:00] **Ben:** Yeah. Yeah. I don't do any of that. I don't do any of that.

[00:43:03] **Adam:** well I was looking at the, I just pulled up Bugsnag in there.

[00:43:06] **Adam:** I think if you are planning on staying independent for a very long time on a, on a, any given project, that seems like a great place to start. Right? You get seven and a half thousand events, so I assume like bug reports, and one seat for free. So that's, that looks pretty cool. I was gonna say like, I don't, I, I have mixed feelings about this, but I will throw it out there.

[00:43:26] **Adam:** Uh, a product that we use that we like, because it's open source and, and we can, you don't run into pricing, and, and licensing issues. It's a ColdFusion product called Bug Log hq,

[00:43:38] **Ben:** Oh, yeah. By, uh, Oscar, uh, oh, yeah, he worked at Invision.

[00:43:43] **Adam:** Oh, really?

[00:43:44] **Ben:** Yeah.

[00:43:45] **Adam:** Okay. So you are well aware of this product and choosing not to use it. I see how it is.

[00:43:49] **Ben:** Well, it's so, so I, you know, not the, the, the.

[00:43:53] **Adam:** Nah.

[00:43:54] **Ben:** Oscar came? No, no, no, just I'll give you like this. Oscar came and we had already had a bug tracking system in place, which really was not a good system at all. It was, we were basically just writing errors to the database, and we had a little simple UI that would list them out.

[00:44:06] **Ben:** and he came and he was like, Hey, I wrote this bug tracking system. It's pretty great. I'm gonna put it in place. And we're like, okay, do it. And I think he was the only one who ever used it.

[00:44:15] **Adam:** Hmm.

[00:44:15] **Ben:** And, and then we eventually removed it. But, no, it, it, it, it seems like, from what I remember, him showing me, which, you know, this was like 10 years ago, and, and it looked like it had a lot of the features, like the grouping of errors and muting and stuff.

[00:44:27] **Ben:** Like it has a lot of the stuff that, the bugsnag looks like it

[00:44:29] **Adam:** I mean, it could be that I haven't, I just haven't looked to see, but I don't, I don't think it's been updated in, in like a decade or more, you know, it's just kind of it, right? It, it's kind of, and not, that's not to say that if there's anything wrong with it, it's just not continuing to grow and, and, evolve.

[00:44:46] **Adam:** Like modern bug tracking software stuff is right, so, you know, thing, it's not learning any new tricks from anybody else. but like I said, the reason we picked it is because it's free and there's no licensing concerns. We can host it ourself, which kind of sucks. Great. Cuz it's not our core competency, you know, we don't have it, it stinks when the bug thing goes off, which is rare.

[00:45:08] **Adam:** Right. Maybe when, when you try to submit a bug report, which is a rest API call. And it doesn't go through. You can have it configured to like, send you an email as a backup. And we get maybe, I dunno, 10 of those a month from a crapload of traffic.

[00:45:24] **Adam:** I mean, we're not stack overflow, but we're, we're like, you know, maybe one 20th or one 10th of what Stack Overflow does in terms of traffic and, yeah.

[00:45:33] **Adam:** So that doesn't feel too bad.

[00:45:34] **Ben:** Yeah, no. That I hate. It's,

[00:45:36] **Adam:** The, the reason I was hesitant to mention it is just because I feel like the ColdFusion community can so often be very insular, right? Like, not invented here, our thing is best. and you know, like there's pros and cons to every decision,

[00:45:49] **Ben:** Well, yeah, and I have to admit that I am, I don't wanna say that I'm a not invented here person, but I enjoy the idea of building stuff. I think I have a sense of where my competencies end. Like I'm not gonna build a Redis, client Redis does that and they've done a great job of it, but like, I will build maybe more stuff around Redis that you may have also been able to get a package for.

[00:46:18] **Ben:** But I want to build that part cause I feel like I understand it. Like I, like, I like to go maybe a little bit deeper than other people might go, but then I hit the, you know, I hit a, a wall pretty quick. I don't wanna get too nitty gritty,

[00:46:30] **Adam:** Right. That makes sense.

[00:46:33] **Adam:** like, mean, that can be a good way to learn too, right? Like, yes, I know there's a library that could do this for me, but I want to, you know, expand my knowledge in this sphere. So,

[00:46:41] **Ben:** it, it, it's interesting. So, I mean, this is, I, this is gonna sound like I'm throwing shade, but I'm not throwing shade. So I was just listening to the Syntax FM podcast actually, like right before this, as I was, brushing my teeth. and Wes and Scott are talking about, they were, they were, they're rebuilding their podcast website and they're talking about the tech that they're using.

[00:46:58] **Ben:** And at one point Scott talks about, oh, I've, I've been using this library that generates the slugs for URLs and I, and I'm like, like you could just write that. You don't have to pull in a library that does slug generation. And I'm not saying that, you know, there's probably a really good reason that there is a library for that.

[00:47:16] **Ben:** And he talked about like, it has, some have text translations for emojis that you can have emojis and titles of stuff. And, and I'm like, all right. You know, and, and I think that's part of the nice thing about building stuff for yourself is that it only has to work for you. It doesn't have to be the thing that works for everybody else.

[00:47:34] **Ben:** So you can live in a world of a lot of constraints and known quantities and, and you can really narrow in the degree of building that you have to do. And I think that, I dunno, it makes it, I have a lot of fun with that stuff.

[00:47:47] **Adam:** Yeah. I mean, there's a lot of reasons to build June.

[00:47:50] **Ben:** Like, okay, so maybe one thing that I did that I probably didn't have to do, I wanted to build a dependency injection system. For the,

[00:47:59] **Ben:** so, right? Like, it sounds

[00:48:00] **Ben:** crazy. It sounds crazy. When you look at something like WireBox from, from Ortis, that's like a tremendously complex piece of software. Or even something that's a lot more simple like dependency injection one, which is what comes with, framework one, DI one, right?

[00:48:16] **Ben:** and you look at DI one, if you open up the file, it's like, it's like 400 or 500 lines of code. Like, it's not, it's not an overwhelming amount of code. Of course, they have like almost no white space in that code, so it's really like, it's really like 4,000 bend lines of code, but whatever. but, but dependency injection systems that are out in the wild, they have to be very flexible because they have to work in a lot of different ways for a lot of different people.

[00:48:42] **Ben:** For example, you can say, Hey, this component should be a single tin, meaning that it's cashed in memory forever. But when I ask for this type of component, it's not a single tin. So I want you to instantiate a new one and give me a fresh one every time I ask for it. I'm never gonna do that. Like all of my components will forever be cashed in memory.

[00:49:00] **Ben:** As single instances. I never have to worry about transient objects so I don't have to have that logic in my injector. So I built a little injector and it's like 300 lines of code and it and it and it's, and it's working pretty well. But like, I don't know, I just had fun. Like I just wanted to build it and have, and have fun with it.

[00:49:17] **Ben:** I wanted to keep the excitement going.

[00:49:19] **Adam:** I get it. I, I too have written a dependency injection framework. Um, Uh, uh, mine was, Hey, now, hey, now I'm getting insulted.

[00:49:31] **Ben:** Just funny cuz we both have done it. That's great.

[00:49:34] **Adam:** Yeah, mine was part of Taffy. and basically when I, when I hit that point in the framework, I was like, okay, so you, you could have choices and I wanna support choices, all right? I wanted to, I, at that time, the things that I was aware of and, and wanted to support were Coldspring DI one and like nothing, right?

[00:49:54] **Adam:** Whatever Taffy uses under the hood, outta the box by default, right? So the taffy default is you've got your application C ffc somewhere, your index CFM application c, ffc, and index S c M are in a place, right? That's where your API is. And then, you have a subfolder off of that called resources. And in there it looks at all the CFCs and parses, them checks are meditated to see if they extend the right things in order to be considered, you know, whether it's a serializer or a resource or whatever. And so I, I, I just like, okay, well that's gonna be my thing, right? I'll, I'll, I'll just write a quick dependency injection thing that does that. And it's, it very heavily inspired by DI one. and except that there's no, it, it's not intended to be inherited from like di one you

[00:50:37] **Adam:** could inherit and overwrite and stuff.

[00:50:39] **Adam:** This is just like, this is the way it works. I mean, take it or leave it.

[00:50:42] **Adam:** So,

[00:50:43] **Ben:** I look, I. I think it's great because it also, it forces you to think about how things work just a little bit more than you would have before.

[00:50:51] **Ben:** Um, and I,

[00:50:53] **Adam:** Now, like, I totally understand problems of dependency injection, circular references and, and, not, not dependency trees, but you know, the order that things get, instantiated and, and built, you know, those things matter.

[00:51:07] **Ben:** It, it, it, yeah. It's really, I actually, in my injector, I have this huge comment block. I mean, it's like, it's like eight lines of comments long, and it's all about, I, I'm instantiating this ColdFusion component and it is not ready yet. It doesn't like, it doesn't have any of its dependencies injected into it, but I'm storing it in the internal cash.

[00:51:29] **Ben:** So in theory, this is an invalid component being stored in cash. But the reason I'm doing that is because I might have a circular reference later on, and I don't want to go down this infinite back and forth of trying to instantiate components. And so I'm, you know, I'm, I'm basically protecting against the circular references, but I'm doing it, with, you know, 10 lines of comments as a, this is, this is a shame that it has to be here, but I'm too lazy to figure out how to do it better, kind of a thing.

[00:51:56] **Ben:** But, but yeah, I dunno. And it's exciting to think about that stuff.

[00:52:00] **Adam:** Okay.

[00:52:01] **Ben:** Yeah, I'm trying to think if there's anything, also, even just is there, like, there's stuff that I haven't even solved yet, but again, it's just like this one hurdle after another. So I want to have these magic links, meaning you don't have to sign up with a password, you just give me an email address and I'll send you an email with a magic link that allows you to sign it.

[00:52:21] **Ben:** But in theory, that becomes an attack vector now, cuz anybody could go to the site, type in anyone's random email address and then they get a, an email saying, Hey, log in to Dig Deep Fitness. And they're like, I have no idea what that is.

[00:52:33] **Adam:** Right. Thanks for your creating your account. On

[00:52:35] **Ben:** Yeah, yeah. Like it's a stupid attack, but it's an attack nonetheless.

[00:52:39] **Ben:** And it probably costs me money at some point cuz emails are not nothing, they're pretty inexpensive, but they're not 0 cents, you know, per million or whatever. so now I have to figure out rate limiting and like, okay, you know, I can rate limit based on IP address, but then IP addresses can be pretty dynamically these days and people can spin up botnets.

[00:53:01] **Ben:** I'm like, do I think someone's targeting me with a botnet? No, but, but like, it's one of those things you have to think about and you're like, okay, do I have to worry about rate limiting on day one? Like, should I be including rate limiting in my initial implementation of my magic link? Or do I say, hey, I'm going to need rate limiting.

[00:53:19] **Ben:** Put a card on the Trello board and I come back to it when I come back to it. Like, I don't know what the right answer is There I am, I'm not sure how worried I should be and, it's something I have to consider as I'm, as I'm, as I'm waiting through this, murkiness.

[00:53:31] **Adam:** Yeah, for sure.

[00:53:33] **Ben:** Ah, anyway. Okay. I'm good. This is exciting. So, so my plan is I wanna start reporting, you know, sharing my progress, a as we're doing the show, and I'll, you know, I can roll it into the triumph and failures, but, you know, I wanna keep everyone abreast of what's going on.

[00:53:47] **Adam:** Let's do it. Sounds good.

## [00:53:49] Book Club Update

[00:53:49] **Adam:** And then, and I'll throw this out there as a, as a weekly update in case anybody's wondering what happened to book Club, why we didn't mention it this week. our book club recording or book club meeting, would've happened on Memorial Day earlier this week on the 30th. or I guess Memorial Day observed.

[00:54:06] **Adam:** I'm bad at holidays and calendars, I apologize. but, whatever the, everybody was celebrating here in the US on Monday. We were supposed to, get together on Monday and we just decided to postpone and we're kind of doubling up next week. So instead of reading chapters, I think it was,

[00:54:20] **Ben:** I think it was six through nine

[00:54:22] **Adam:** yes, I, so instead of six through nine, it's now six through 12.

[00:54:27] **Adam:** And we'll talk about those next week cuz when there's been some interest in like, increasing our pace. Nobody's complained about, having too much to read yet, and multiple people are like, I can't put it down. It's so hard to make myself stop. So, we're gonna, we're gonna try to turn up the, the throughput a little bit here.

[00:54:42] **Adam:** See how that goes.

## [00:54:43] Patreon

[00:54:43] **Adam:** okay. So this episode of Working Code is brought to you by Magic, which I can either confirm nor deny, is involved in authenticating into Dig Deep Fitness. May or may not.

[00:54:52] **Adam:** You'll have to try it for yourself. See if you get glitter in your email. and listeners like you, if you're enjoying show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon, Our patrons cover our recording and editing costs, and we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo, and actually we do have a new patron to welcome this week. So Andy McNeese, welcome.

[00:55:16] **Ben:** Woo

[00:55:16] **Ben:** woo.

[00:55:16] **Adam:** up. And yeah, so what do patrons get? we are going to continue talking after we stop the main show because that's what we do.

[00:55:25] **Adam:** We can't stop ourselves. we're gonna keep recording and, and we call it our after show. It could be about anything. I'm gonna ask Ben if he's been watching Ted Lasso and if he has like, you know, how far is he and can we talk about the finale? the

[00:55:37] **Ben:** Can't talk about the finale yet. Can't talk about it yet.

[00:55:39] **Adam:** we haven't seen it either, but we're, I think we'll watch it tonight.

[00:55:42] **Adam:** us too, right after this actually.

[00:55:43] **Adam:** Okay. Yeah. And the other thing that I'm gonna ask Ben about in the after show is, previously he had mentioned like some bizarre behavior they were seeing at work for, SMS people, like sending out SMS codes. And a listener of the show in our Discord, brought, like, sent us a, a link to an article about how that can be like scamming people somehow it's a scam and people make money off of it.

[00:56:08] **Adam:** I don't get it or I don't remember. It was a while back, but, I wanted to see if anything came to that. So we'll talk about that in the after show, unless Ben has something more interesting to talk about, in which case we won't talk about that.

## [00:56:18] Thanks For Listening

[00:56:18] **Adam:** But then I mentioned it. Here's your homework. You're just, I want you to join our Discord, go to workingcode.dev/discord, and that's where you can leave all of the nasty grams that you want for Ben for his testing and then throwing it away instead of automating it. and, and yeah, and, and we'll talk about book club and all the wonderful things that, are offshoots at this podcast. I'm still very excited to get everybody back on the show. I have a game that I wanna play with all four of us on. It's, it's gonna be fun, but I gotta wait till, you know, nobody, nobody's sick and nobody's moving and, and doing army stuff.

[00:56:49] **Adam:** and we'll figure it out. But I, I'm, I'm eager, I, I wanna keep mentioning it cuz if I don't then I'll forget. So, I guess that's it for this week. We'll catch you next week and until then,

[00:57:00] **Ben:** Remember folks, your heart matters even if that's not asserted in a unit. Test,
