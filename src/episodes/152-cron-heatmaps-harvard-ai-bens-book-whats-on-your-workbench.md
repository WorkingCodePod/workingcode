---
title: "152: Cron Heatmaps, Harvard AI, and Ben's Book - What's On Your Workbench"
description: "On today's show, we talk about visualizing your cron heatmap, Harvard's AI course, and we get an update on Ben's book."
date: 2023-11-08
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/152-cron-heatmaps-harvard-ai-and-bens-book-whats-on/id1544142288?i=1000634121204"></iframe>

This week on the show, the hosts talk about what they have going on. Adam is trying to better understand the cadence with which his scheduled tasks are executing; and, has built a visualization tool using Svelte and D3. Tim has signed up for [CS50 at Harvard][cs50] - an online course introducing Artificial Intelligence (AI) with Python. And, Ben has a working draft for the first half of his Feature Flags book; and, is now considering some sort of pre-sale (if he can figure out how to turn his Markdown files into something consumable).

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[cs50]: https://cs50.harvard.edu/ai/2023/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/152-cron-heatmaps-harvard-ai-bens-book-whats-on-your-workbench.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** Tim, you got, your son got you into Harvard?

[00:00:02] **Tim:** He did. Yeah, I just put his name in, but I'm actually taking the courses. No, um, a free, so

## [00:00:10] Intro

[00:00:10] **Adam:** Okay, here we go. It is show number 152, and on today's show, we're going to talk about visualizing your cron heatmap, Harvard's AI course, and Ben's book. but first, as usual, we'll start with our triumphs and fails.

[00:00:41] **Adam:** And Ben, it looks like it's your turn to go first. What's going on, man? Right,

## [00:00:44] Ben's Failure

[00:00:44] **Ben:** Yeah, I'm going to kick it off with a failure. It's a light failure, but, at work we've been using framework one, which is just a, ColdFusion web development framework. And, as with many frameworks, you have the option to define a whole lot of routes using pattern matching. And then those routes get mapped onto internal server side controller calls.

[00:01:05] **Ben:** And, after essentially creating a custom pattern route for like every internal API call over the last decade, it only just recently, like in the last couple of months, dawned on me that I don't actually need internally used routes to actually look nice in any way whatsoever. And, I've slowly been going through the application and well, I should say as I'm building new internal routes, I'm just using the, the routing pattern that would naturally work.

[00:01:40] **Ben:** Um, for this, right, exactly. Where you can do like subsystem colon controller dot method name. And, it just, it just feels like I've been jumping through all these pattern matching hoops for years. And, and it's so frustrating to realize that I've been doing something for so long without actually understanding why I was doing it in the first place.

[00:02:04] **Ben:** And now that I've stepped back and asked, actually asked myself, what was the value add of doing this? I realized there was no value add. And in fact, all it does is leave a lot of cruft configuration in the application that makes it a lot more complicated to even understand how things are being invoked and I'm just frustrated.

[00:02:21] **Ben:** I'm just frustrated when I do, I call it sloppy. It's like, it's just sloppy. You copy paste something and you never really think about why you're doing it in the first place.

[00:02:30] **Adam:** Well, you know, better late than never, right?

[00:02:32] **Ben:** Yeah,

[00:02:33] **Tim:** I mean,

[00:02:35] **Ben:** you know

[00:02:35] **Tim:** how many years? Like six, seven years.

[00:02:38] **Ben:** Like eight or nine, but whatever, who's counting? You know, I think as web developers, I, or I can't say as web developers, I'll say that I spent so long thinking about what public routes looked like, especially, coming from a blogging background, you know, you think about the URL structures and creating slugs and how do you get an ID in the URL without making it seem just like gibberish so that it has some SEO juice, maybe poured on top of it a little bit.

[00:03:08] **Ben:** And I think taking that mentality. And then porting it into a business product context. It's just that, that, I think that's where I made the mistake that I wasn't coming at it from a business standpoint. I was coming at it almost from a SEO standpoint, but internal routes don't need SEO users. Don't see them.

[00:03:30] **Ben:** And even if users do see them in the network activity or whatnot, like who cares what those URLs, it shouldn't be easy for them to understand necessarily. It should be easy to implement as an engineer.

[00:03:40] **Tim:** So what was your aha moment that made you realize you didn't need to do that?

[00:03:44] **Ben:** So. I think my aha moment was that in order to consume those routes from a SPA or a single page application, you have to construct a URL in your API calls on the client side, which usually uses some sort of, in Angular, you can sort of define these weird Resources that will kind of do URL interpolation for you.

[00:04:07] **Ben:** So you could say, I want this to go to slash users slash colon user ID. I guess it's actually an at user ID, I think, in the resource. I don't remember offhand. And then you can say, here's, here's an object and it has a user ID and then it'll end up generating the URL where it replaces the at user ID with the value you give it.

[00:04:25] **Ben:** And, I just had this moment where I'm like, why am I even worrying about interpolating string values into URLs? When I could just say, go to this subsystem controller, controller method, and then all of the values that I actually want to pass either get appended as URL, you know, this equals that parameters or post it as a body.

[00:04:46] **Ben:** And it just, it just seemed all of a sudden like so much less work. I didn't have,

[00:04:50] **Tim:** you already know those values.

[00:04:52] **Ben:** yeah, exactly. I didn't have to, I didn't have to construct a URL. I think that was it. It's like, there was a moment where it was, I didn't have to build a URL anymore. And that just seems so much easier. And then that made me wonder why I was even doing it in the first place.

[00:05:05] **Carol:** Because nine years ago you needed to, and you just forgot to update your code.

[00:05:10] **Ben:** But

[00:05:11] **Tim:** culted that

[00:05:12] **Ben:** the, the frustrating thing now is if you go into the application CFC, so framework one, the way it works is you have your application CFC, which extends the framework one's version of the application CFC, and then you can define all your configuration and your event handlers. And if you open up our application CFC, I mean, there's probably.

[00:05:31] **Ben:** 700 custom pattern routes being defined in the application CFC. It's, it's bananas. And I know that this is a micro optimization, but one thing that I always consider or that is always tickling the back of my mind is in ColdFusion, every single time you make a request to the application, the application CFC gets reinstantiated on every single request, which means it's this giant.

[00:05:53] **Ben:** 700 line object has to get instantiated and put into the memory of the request, which, you know, in the grand scheme of things is probably not even worth considering, but. I know that that's happening and it, yeah, it just makes me all the more angry that those are there. And the super frustrating thing is, because that's just like an internal redirect, so to speak, for the routing of the request, is it makes it really challenging to know when I can remove those custom mappings.

[00:06:25] **Ben:** Because if I update my client side code to no longer use them and to actually just hit the controller directly, like, I don't know if anything's actually calling that weird mapping anymore. Cause all of the, all of the, the, the, the, like the stats D that I'm recording is, is it the, like the final controller level has nothing to do with the incoming route.

[00:06:45] **Ben:** It's the final, it's like what, which controller method was actually hit. So I, I just, there's this appendage now that I feel like I can never get rid of.

[00:06:52] **Adam:** I feel your pain. I know exactly what you're talking about. Like, there's just, you don't feel like there's a deterministic way to know. Is this still being used? So I think it's been a while since I've been in this part of the guts of framework one, but I think there's going to be, I couldn't even imagine what to, what it's called, but there's going to be a function that you can override where it's doing the resolution of those, aliases or whatever.

[00:07:16] **Adam:** And so you're just basically going to say, okay, log that this one was used. However you want to log that fact and then call super. whatever, right? So you're, you're just, you know, you're sort of monkey patching on some additions, but you don't want to change the underlying behavior, right? So if it's, if it's, if it's a resolve alias, right?

[00:07:35] **Adam:** Then you're going to do a function resolve alias, do your logging and just call super. resolvealias.

[00:07:41] **Ben:** that's pretty clever. It didn't even occur to me to do that.

[00:07:43] **Adam:** Is it just super? I don't know. I don't do that very much.

[00:07:46] **Ben:** So yeah, I'm sure I can figure it out. I mean, it's, I mean, the frame, the framework or what is it? Like one. cfc or framework. cfc, I can't remember what it's called. Like it's just sitting there in the file system, you know, it's easy enough to go in,

[00:07:58] **Adam:** Yeah, I did that for our application, which is also built on Framework 1 for, I think it is the request handler, the one that like wraps before and after. and I don't even remember what for, but it was just like, I had this moment one day, you know, I was like struggling for, I don't know, half a day on something.

[00:08:18] **Adam:** Like I, I need to, I want to hook into those lifecycle events. And I was like, wait a minute, just use the, use the platform as they say.

[00:08:26] **Ben:** right, exactly. So better late than never, but, always good to question why you're doing certain things.

[00:08:34] **Adam:** I just wanna, I gotta squeeze this in here before we move off this topic, you know, when, when you were talking about, you know, you've got 700 of these things and, and Tim said you cargo culted yourself, I just had this vision in my head of the DJ Khaled, like, congratulations, you played yourself.

[00:08:48] **Tim:** yourself. Another one.

[00:08:53] **Ben:** Oh, all right. Groovy. So that's me. Carol, what do you got going on?

## [00:08:58] Carol's Triumph

[00:08:58] **Carol:** Guys, I'm going to go with a big giant win. A few weeks ago, I mentioned that I was having a really hard time getting SQL the alias so that I didn't have to change my code. I got it working. So now I don't have to change my code. So whether I run the Docker version of the database or I run the updated version, I just go in and add my new, name.

[00:09:22] **Carol:** Piped alias for it, and I am good to go. So I am super happy. I thought I had it working. Then I realized I forgot to do it on both versions. Cause apparently you have to make the configuration change in 32 bit and 64 bit in order for it to work. So once I made the second change, everything just connected like it was supposed to.

[00:09:43] **Carol:** So I got to go delete all my stash code where I had went through and made all the changes and kept. Deleting it, reapplying it, deleting it, reapplying it, and now it just works like magic.

[00:09:54] **Ben:** Nice. Well, and if I recall, something you were saying in the previous episode was that because you are new to the team, this affected you, but it wasn't necessarily affecting anyone else because they were doing incremental patches to their database.

[00:10:07] **Carol:** Yeah. They kept reapplying the migration. Yeah.

[00:10:10] **Ben:** so you've now unblocked not only yourself, but anyone else who might subsequently join the team or have to wipe out their entire database for some reason,

[00:10:18] **Carol:** Yep. So if anyone needs to do a full restore now, they can use my method because those databases are stored encrypted, so you can't unencrypt them on the 2019 version, you have to have the 2022 version of SQL server in order for anything to work. So yeah, super excited about that cause now other people will be able to follow that same plan that I laid out.

[00:10:38] **Carol:** Which currently is just written on a notepad, but I will get it into the repo very soon, like into our wiki pages.

[00:10:45] **Ben:** Nice.

[00:10:45] **Tim:** Making the changes.

[00:10:47] **Carol:** Woohoo. I documented something. Look at that, you guys.

[00:10:50] **Tim:** Hey, you, yeah, the

[00:10:51] **Ben:** uh,

[00:10:52] **Adam:** favorite activity.

[00:10:53] **Tim:** 32.

[00:10:54] **Ben:** one, one thing you said there, you talked about updating 32 bit and 64 bit systems that we said, this is, this is one of those things where it's like, I just sort of nod my head a lot of the time. I've heard the phrase of the 64 bit and 32 bit, I mean, probably for like 15 years now, cause I feel like, windows, right?

[00:11:13] **Ben:** When you install on windows, there's like a system 32 and then like another folder or, you know, it's like programs and programs, 86 or something like that. And I just, I've looked it up several times and my brain could not commit to memory what the heck the difference is between 32 and 64 bit systems

[00:11:31] **Carol:** And I have, I have, yeah, it's just math. Come on,

[00:11:35] **Adam:** Give or take one,

[00:11:36] **Ben:** roughly that

[00:11:38] **Carol:** And oddly enough, the two changes I had to make were in the system, 32 folder and the system. Wow. 64 folder. I was like, when did it get named? Wow. Like, I've been on Mac for a while. I was like, at some point it stopped being like the 86 and went, wow. 64.

[00:11:54] **Carol:** And I was like, oh, interesting.

[00:11:56] **Tim:** It's been a minute,

[00:11:59] **Ben:** does one of those just no longer matter anymore. Meaning, meaning like it's, it's 64 bit, just the new thing and 32 bit is, is a very old compatibility issue.

[00:12:09] **Adam:** pretty

[00:12:10] **Carol:** don't know. Yeah, I don't know anyone that runs a 32 bit operating system now.

[00:12:14] **Tim:** probably the U. S. government

[00:12:16] **Carol:** We don't. Yeah.

[00:12:18] **Adam:** I mean, this is a wild guess, but I'm guessing like maybe some older Raspberry Pis or something like that might be 32 bit. So, I, you know, I've been out of that world for a long time, but to the best of my memory, the primary difference, Ben, for, between 32 bit and 64 bit is... It doubles the amount of memory that the processor can address.

[00:12:40] **Adam:** So it, it basically, you can, you know, if it was a maximum of 256 gigs of memory before, now you've got 512 or, or maybe it's like it raises it to the power of two or something, I don't know, but it, it's a, you know, it's a, it's a giant leap forward in the amount of memory was, that is my memory of the, the initial reason to upgrade.

[00:13:02] **Tim:** and then how it's compiled is different, right? Cause the compiling is different versus 64 versus 32. I'm sure that we've given an answer and it's probably wrong

[00:13:11] **Adam:** Probably wrong, the listeners will let us know for

[00:13:13] **Tim:** our, yeah, our listeners will, will definitely let us know.

[00:13:18] **Carol:** What about you, Tim? What you got going on?

## [00:13:21] Tim's Triumph

[00:13:21] **Tim:** Well I survived Las Vegas.

[00:13:23] **Ben:** Woot

[00:13:24] **Tim:** I spent, all last week for work, flew in on Monday and then, was there until Friday, in Vegas for the ITC, the Insurance Technology Conference, which we go to every year and we have a booth. We set up a booth and people come, you know,

[00:13:39] **Adam:** Is this the place where you had like set up the beer garden one

[00:13:42] **Tim:** Yeah. Yeah. We, we didn't have the beer garden this time around.

[00:13:45] **Tim:** We had the beer garden a couple of years ago, which is, which was awesome. yeah. Got a lot of traffic that time. Yeah. This time just had a booth, some of our sister companies, we got a really large booth and a split it three ways. So, it was nice. Yeah. Just, I mean, these things that, you know, it's like you go to these, you spend a whole lot of money and it's like, maybe you get a few leads, but it's one of those, you gotta, you gotta pay to play our, our biggest competitor had like, I mean, they had branding everywhere.

[00:14:12] **Tim:** Oh my God. Everywhere. It's like every time you turn around and you saw our biggest competitor and it's like, I have no clue how much money they spent. I mean, had to be probably a quarter of a million dollars they spent.

[00:14:24] **Adam:** Wow.

[00:14:25] **Tim:** Cause our beer garden was 80 grand and that was just like just one space, right? And they were everywhere.

[00:14:30] **Tim:** There was like branding on, the meeting. They have a big meeting space. So the, these kind of things, they have like a networking thing where everyone has an app and you try to connect with different people and they're like, meet me at booth, you know, 519. And if you don't have a booth, these little tables, hundreds and hundreds of these little tables where you can go talk to somebody and all of those are branded with their name.

[00:14:50] **Tim:** And the whole area was branded with their name. So. But I hate Vegas. I think I've probably been to Vegas 22 times in my life.

[00:15:00] **Ben:** Oh

[00:15:00] **Adam:** Wow. That's, that's a, that's plenty of times. You don't need to go back to

[00:15:03] **Tim:** Yeah. Maybe because back when I was doing cold fusion conferences, you know, I, we either went as a speaker or as an organizer, but sometimes I would be, particularly like in the fall, I'd be in Vegas like three times in the fall in one year for 10 years. So, yeah, so it's, yeah, I've seen all the shows, but the best thing is I really do like to, I did actually do something new in Vegas this time.

[00:15:27] **Tim:** And no, it was not cocaine.

[00:15:30] **Adam:** Is it a hot pot?

[00:15:32] **Tim:** it was hot pot. Yeah. And not marijuana pot, but yeah, you, yeah.

[00:15:37] **Adam:** With, with chili peppers in it.

[00:15:39] **Tim:** So,

[00:15:39] **Ben:** What is a hot pot?

[00:15:41] **Tim:** thank you for asking. so hot pot is like in China, it's Szechuan. So Szechuan is like the spicy region of, of China where they like their food kind of spicy. And we go in there and they have a table and they have these little electric burners on the table or inductive burners, probably.

[00:15:57] **Carol:** Yeah, inductionize.

[00:15:59] **Tim:** Induction. Yeah. So you don't burn yourself and they bring you out of this. That's Pot of boiling broth and they put it at your table. And it's, it's basically bone, bone broth and there's little spices in it and seasonings and everything. And then you just order, different kinds of meat and vegetables, all raw, right?

[00:16:16] **Tim:** So there's a super thin slice of Wagyu beef, pork or, lamb or whatever. And just, they bring it to your table and then you, you just swish it in the, kind of cook it in the boiling broth. And then you have like different like sauces and spices. You can like pull it out, dip it. So it's kind of like fondue.

[00:16:34] **Tim:** But for savory things, right?

[00:16:36] **Ben:** So,

[00:16:37] **Tim:** it was so good.

[00:16:38] **Ben:** Let me ask you this, because I went to a Korean restaurant, I mean this is probably like 15 years ago in New York City, and it sounds very similar where they had a boiling thing and they bring you out sliced stuff and you have chopsticks and you're cooking it. And I, at one point I freaked out because I realized that I wasn't paying attention to which chopsticks I had been picking up the raw food with and which I was putting in my mouth.

[00:17:00] **Ben:** And I mean, I don't know if, so I know that you're not supposed to deal with raw chicken, but I don't know if that's

[00:17:07] **Carol:** Or pork.

[00:17:08] **Tim:** were you doing chicken?

[00:17:09] **Ben:** yeah, yeah, chicken was definitely part of that situation. Okay, so if you, you were not dealing with chicken then, is that

[00:17:14] **Tim:** I wasn't doing chicken, but I was doing pork and beef and lamb. But I mean, maybe you're not supposed to, but in China, I guess they don't care because you're putting in boiling water.

[00:17:24] **Ben:** Yeah, I guess, I guess because you're dipping it in the boiling water, it's sterilizing stuff as well.

[00:17:29] **Tim:** Yeah. But what's nice is it like kind of, you add more meat. Cause first you kind of do the meat and then as you add different meats, it sort of flavors the broth even more. It starts to cook down. It just gets more and more tasty. I probably just was there for three, four hours. And then the next night, next night, I wanted to go back.

[00:17:46] **Tim:** One of our coworkers is like, Oh, that sounds great. I can I go? I'm like, yeah, we can go back. I liked it so much. And, go in there and the same place, the place was called, Chubby cattle. It's almost as if they put into Google translate like fat cow or something or fatty cow, and they came back with chubby cattle.

[00:18:06] **Tim:** I'm like, ah, good enough. So we walk in there and, and I mean, there's people working there, but there's no one at the tables and I thought it was empty and she goes, Oh, sorry, the, the, the broth wasn't good today, so we're, we're not serving.

[00:18:21] **Carol:** Oh, wow. I respect that.

[00:18:24] **Tim:** yeah, exactly. At first I was disappointed.

[00:18:26] **Tim:** I was like, you know what? I totally respect that. I don't understand why you have everyone here. All the servers were there. The bartender was there. Why, why are you working if you're not serving? But, anyway, so we went to another place called, called Nabe. This is in Chinatown in Vegas, which is a really big Chinatown actually.

[00:18:42] **Tim:** And it's the Japanese version of the hotpot. It's called Shabu Shabu. Which is an onomatopoeia, which shabu shabu is the sound of swishing. Cause you're swishing the food back and forth in the water.

[00:18:53] **Carol:** that's

[00:18:54] **Tim:** not as, it's not as spicy, but this place was great. It was like 25 bucks all you could eat and the food was amazing.

[00:19:01] **Tim:** So we were there probably three hours. So, I ate well, survived Vegas. It was a good show, had a lot of traffic, but I'm so glad to be home. I wish I'd never had to go back to Vegas,

[00:19:12] **Adam:** Did you, did you get the hotel room with the water fountain in it again?

[00:19:16] **Tim:** So I personally didn't get one. We had, so we had multiple companies that our parent company was there. And mostly like, our, we have a new branding of sort of our group that does insurance and banking software. It's called VinCura. And VinCura goes there specifically just to buy new companies. And so we had a giant suite and we had each night we'd have like a cocktail party.

[00:19:40] **Tim:** We'd invite. Different companies to come up, you know, have a cocktail party and try to get them to sell. So that one had the, I took a photo of the, of the water fountain, AKA the bidet, took a photo of that. So I wasn't staying there, but I got the full benefit of being able to hang out there. So

[00:19:55] **Adam:** The full benefit. Fancy way of saying your butt was splashed with water.

[00:20:02] **Tim:** shabu shabu. Anyway, so that was me. I went to you, Adam.

## [00:20:08] Adam's Triumph

[00:20:08] **Adam:** Oh, I've been having a really good week. I just finished my first, weekend of doing paid tandems, as a tandem inspector. Thank you, thank you. It was pretty fun. and yeah, it's just been fun. you know, I, I, we're gonna do, we're gonna be talking about, some of the stuff I was working on today.

[00:20:24] **Adam:** I've been working on some code stuff and, and, real excited. Like Carol jumped on to start recording the podcast tonight. And I'm like, hang on, can't stop thinking, can't stop typing. I'm still working on this. just cause, like, it's, it's fun and interesting and, you know, I'm working in Svelte and I'm, I'm doing something interesting, so, I'm excited to talk about it here in a few minutes.

[00:20:42] **Ben:**

[00:20:42] **Tim:** Let me ask you something, Adam, on the, on the getting paid to do tandems, is that the kind of thing where you actually. Like a profit or you just kind of break even for your hobby? Is that?

[00:20:51] **Adam:** I think long term, I will, it'll be a nice little source of like beer money or it'll help cover some of my skydiving expenses sort of thing. I'm, I'm, you know. I think it could be profitable, depends on how much time I'm able to dedicate to it and how much I let it take over my skydiving time. Right, I still want to do my solo fun jumping sort of stuff, so I don't want to just be like nothing but tandems.

[00:21:19] **Adam:** But it's not, I mean, I made 350 bucks this weekend. And that was a very light duty weekend, so, I mean, I only did, five Tandems, and, I mean, I got a nice tip, one of those, people gave me a hundred dollar tip, so I made 2. 50 from the, the jumping, plus the hundred dollar tip, so.

[00:21:34] **Ben:** Yo, that's a sweet tip.

[00:21:36] **Adam:** And it was a very, surprise, it's like, are you, oh, seriously?

[00:21:39] **Adam:** Thank you!

[00:21:41] **Tim:** They're like, keep us alive.

[00:21:44] **Adam:** yeah, anyway, so we were gonna get into, this thing I've been working on, now that Tim's back from the bathroom, and, um,

[00:21:51] **Tim:** to drink.

## [00:21:53] Adam - Cron Heatmaps

[00:21:53] **Adam:** And, so cool. So we, my company, AlumniQ, we are, you know, moving towards multi tenant. We have a bunch of these different customers and we have lots of data that we have to process for them. So we have. a lot of repetitive jobs, and we have a lot of different scheduled jobs to, you know, stay on top of the data and make sure things are moving along in a near real time fashion.

[00:22:13] **Adam:** And it occurred to me today that it, like, when I look at our crontab file for the, you know, the list of all of our cron jobs, it's like 400 and something lines long. very long. And so I was like, you know, I don't really have a good sense of, you know, are we, are we shooting ourselves in the foot, right?

[00:22:30] **Adam:** Are we accidentally crowding a certain time of day or something like that? So I really wanted to see, is there some way to like visualize, the crontab file?

[00:22:38] **Carol:** So cron jobs are like, just tasks that are running, right? Like that's what a cron job is.

[00:22:43] **Adam:** yeah. so in Linux or probably in Unix, there's a, a tool, you know, whatever, an application called cron. and it's just for like running Tasks on a scheduler.

[00:22:55] **Adam:** So like from the ColdFusion world, it would be like scheduled tasks are sort of the equivalent. cron you can say run a script, and it will like save the output or whatever. And, and, so we use cron. It's, it's a, you know, battle tested. It's been around forever. It's pretty much bulletproof. And it's very, flexible and resilient, I guess.

[00:23:15] **Tim:** You know, all the good words. the cron notation is very cryptic.

[00:23:19] **Ben:** Yo, for real.

[00:23:20] **Adam:** it, it can be, but it's also, it's information dense, right? It allows you to, to, say, you know, okay, I wanted to run on, Tuesdays and Thursdays and every other Sunday at 4 a. m. and, you know, 5. 22 p. m. And, and, you know, you can fit all that into like 30 characters, right? So, it's, it. It is, it is, I guess, a little, cryptic to try and read.

[00:23:43] **Adam:** It's kind of like Regex, right? Like, when you're writing it, it's not that bad, but when you're reading it, it can be. So, pro tip for that, there's a website called crontab.guru, like, guru is the TLD. You just paste in your cron expression there and it'll explain the schedule for you. Anyway, so we have this, crontab file with like 400 lines and each line is a, it's a scheduled task, right?

[00:24:02] **Adam:** So you have the schedule and then the, the script that you want it to run. And I wanted to visualize this and I did some searching around and I did find, there's a website called, I think it's cronheatmap. com, and, I tried to plug my stuff in there and I wasn't really happy with what it was giving me.

[00:24:16] **Adam:** for starters, the Color like it kind of makes this like colored grid and it's supposed to like a heat map, right? the the darker squares will be the ones with more going on in them, and the The contrast like it almost looked like there was nothing going on at all when I dropped in my crontab contents I saw very little difference.

[00:24:36] **Adam:** It's just like slightly different shades of light blue and I was kind of disappointed in that and So I started looking around, I was like, okay, well, maybe I can find the source on GitHub, see if I can, you know, fork it or send a pull request or something like that. there was no links to anywhere on GitHub, but I did find like the author's name, on, in, in the source code.

[00:24:56] **Adam:** And I was able from that to find his website. And from there I found his GitHub and,

[00:25:01] **Tim:** You're stalking this dude.

[00:25:02] **Adam:** Oh, I really wanted, I mean, I was finding, I was, you know, I was very motivated to get the, this solution. And, Long story short, basically, he said he sold the website, the new owner, like, hasn't touched it at all, doesn't seem to be working, and a detail that was not visible on the website but was in, like, his blog post when he initially announced that he had created this tool, and I, you know, that's part of why I think it was just not showing me what I wanted to see, is that it's ignoring jobs that run more frequently than once per day.

[00:25:34] **Adam:** So if you have a job that runs every hour or whatever, it just, like, I guess when he created this tool, he was only interested in jobs that run like on a once a week or a couple of times a week or whatever, just to see like, you know, where, where his hotspots were for that. and you know, I've got a, the vast majority of my jobs run multiple times a day.

[00:25:54] **Adam:** And so it was just ignoring most of my data. And so I was like, okay, well, you know, maybe I can, get the source from him or whatever, like, of course, you know, first thing I did was view source. Can I just like save as and modify, but of course it's, it's bundled and minified and it would be a total pain in the neck to try and make that work.

[00:26:11] **Adam:** So I, I emailed him and I was like, you know, this is what I'm trying to do. Would you mind throwing up the source on GitHub or whatever? And that's when he, let me know that he had sold it. And so I was kind of SOL there, but he did point me in the right direction. He said, I'm using, pretty much all I did was like, take this cron parsing library and I use D3 to visualize the data.

[00:26:30] **Adam:** Okay. Well, thanks. I'll see what I can do. I need a quick, you know, searching around different components for things and ran across a Svelte. not exactly a charting library, it's called Layer Cake, and it's for like, doing visualizations, and they do a lot of, have a lot of examples of like, doing charts with D3 and different stuff, but it does more than that as well.

[00:26:50] **Adam:** and one of their examples was a, like a time series sort of thing, and so I was very easily able to go from, okay, I've got, I can generate time data from Cron, and I've got a thing where I can chart, time data. You know, in a manner that I like, so I just mushed the two together and, and I wrote some code to like, so our cron server, we actually store each job as a new line delimited JSON file, NDJSON,

[00:27:20] **Ben:** so I had to like, I read the crontab file, I parsed each line as JSON and I pull out the bits that I need and, you know, the schedule and the job name.

[00:27:27] **Adam:** and I, I parse it all out to get the, the data that I need, and I'm pumping that into, the Svelte application. It's very interesting, and I will probably try to, I'll see if I can maybe like, you know, post this up as something people can use or whatever, but,

[00:27:41] **Tim:** Yeah, I was just about to ask that because I think, I mean, that'd be great. Cause I mean, with the cold fusion scheduled jobs, it's easy to create them, but it's really hard to see, like, if you're trying to create a new one, you're like, well, I don't know, other than like looking through a list and say, what time is other stuff running?

[00:27:56] **Tim:** You know, how long, you know, it'd be nice to be able to visualize it.

[00:27:59] **Carol:** So is that what this would be helpful for then? And so you could be like, oh, I have too much running at 4 a. m. So my next job should probably not start till 6.

[00:28:08] **Tim:** Yeah.

[00:28:09] **Adam:** yeah, and even mine, I ended up having to, ignore jobs that run, more frequently than run, than every hour, right, so if it's running multiple, multiple times per hour, I'm ignoring those jobs for now. I want to try and,

[00:28:23] **Ben:** Why, why are you ignoring them? Sorry,

[00:28:25] **Adam:** Oh, because on the visualization, instead of having, so the, the way, yeah, the, the way that I'm visualizing it is each job gets a, mostly transparent colored circle, right?

[00:28:36] **Adam:** So you've got like a time series chart, you know, imagine a grid, right? So, you've got, days are on the Y axis, Sunday through Saturday, and across the X axis goes from like, Midnight, in the morning until 2359. 59pm along the x axis on the bottom, right? And so, you can kind of think of that as, I don't know, how many, a bajillion little grid squares, right?

[00:28:59] **Adam:** and, in each of those squares, I put a semi transparent, mostly transparent, colored dot using SVG. and then, because of the, because they're so tightly clustered, Because there's so many grid cells, when they start to overlap, then you've got like most, you know, mostly transparent red on top of mostly transparent red on top of mostly transparent red.

[00:29:21] **Adam:** You start to get these like darker shades of red because they're overlapping. and so that's how you see, that's where there's high traffic. And I'll, I'll, I will certainly post some screenshots of this in our discord for listeners when we,

[00:29:36] **Ben:** So this, this graphs when a task starts, but not necessarily, it doesn't necessarily give you an indication of how long a task might run for, right? Because

[00:29:45] **Ben:** that wouldn't, that wouldn't be available in the cron anyway.

[00:29:48] **Adam:** no. I mean, we might be able to, we certainly could, add an additional field of just like a expected runtime sort of thing to our, our crontab. I told you, you know, the newline delimited json thing. We have a utility that we're, I think it's an open source project that we're using to like manage the cron, so it gives us this GUI for... Searching and updating and, you know, change the schedule or disable a job, that sort of thing. and that's what's using the NDJSON.

[00:30:16] **Tim:** Yeah, I was, I was thinking the same thing you were thinking, Ben. I was thinking you had a way to like log the start and end times of each job and then cross reference that with the job.

[00:30:24] **Ben:** Yo, I'll tell you, that's something that definitely got... Away from us at work when we grew as a company over a period of years, we would have some scheduled tasks that would do essentially a full table scan. But in the early days, it's like, who cares? It's a hundred records, 200 records, 300 records. And then, and then, you know, four years later you look up and you're, and like, I'll notice this because I'll, I'll be looking in the slow query log in my SQL and I'll be seeing queries that are running for like 35, 40 minutes.

[00:30:53] **Ben:** I'm like, what the heck is going on? And I realized that, oh yeah, that Cute little schedule task that we wrote six years ago. Oh yeah. That now scans 17 million rows every hour. You're like, ah, should have fixed that.

[00:31:08] **Adam:** Well, yeah, you get your slow query log and

[00:31:10] **Ben:** Yeah. Yeah.

[00:31:10] **Adam:** Yeah. And then the other thing is for us, we, you know, we're, as we scale up and add more customers, right? So we're going, so you have, let's just say we have a job that runs once every minute. Well, now we've got, every time we add a customer, we're adding another job that runs once every minute to, to do something for that new customer.

[00:31:27] **Adam:** And so we're starting to like identify, okay, this is helping us identify which jobs we need to move to like a multi tenant job runner, right? So it can go, okay, just run the one task and it can handle across all customers, all databases sort of thing.

[00:31:42] **Ben:** Well, that's what I wanted to ask you from an architectural standpoint. So one thing that we realized is that, at first, we had our application nodes running and like, you know, we had our little Kubernetes cluster of nodes and that was originally running scheduled tasks, and it sort of worked using a, A distributed lock in Redis.

[00:32:03] **Ben:** So let's say we had 10 nodes, basically every single one of those 10 nodes was always trying to run the tasks, but only one of them would win for a particular instance, and they would take over for like that iteration of the task. It was not very clean and we ended up then. Essentially taking that code and deploying it as a separate service that was just the task runner.

[00:32:23] **Ben:** So it's the same application code but it was deployed more isolated so that it didn't have to compete. And that was helpful because what we were also realizing is that when the I call them the live application nodes. We're running the scheduled tasks. Anytime we'd go to do a deployment, it would essentially wipe out any tasks that happened to be running at that time.

[00:32:46] **Ben:** And then the task would have to start over. So I'm just curious to know, like, how are you dealing with that kind of stuff?

[00:32:52] **Adam:** Sure. Yeah. And I can talk a little bit about our, our evolution. Through there as well. So similar, but I guess somewhat different path that we took was, you know, as we started to onboard customers that had, you know, more data, more traffic, you know, they put a higher demand on the system. It got to a point where a couple of our customers.

[00:33:15] **Adam:** Just, we couldn't keep running the scheduled tasks against their production system because it would, you know, scheduled tasks would stop production requests from being able to go through, right? The, the system became unusable as a user. and so what we did was, kind of what you're talking about, like, we just made a copy of the production server and said, okay, you are the jobs box.

[00:33:36] **Adam:** We're only going to run jobs on here. It's like, Yeah, you're not publicly accessible, you're just over here, and we're gonna call the, we'll call the URLs with a custom host name that goes to only that one, and it's only accessible, like, inside our VPC, so the cron server can hit it. and that worked okay for us for a while, but it's, it's not scalable, right?

[00:33:56] **Adam:** Like, you, then you have to decide on a customer by customer basis, do we need to do this, or, or whatever, it's a pain in the neck. and so. I think the direction that we're moving towards now, we, so we did get everybody off of, those, you know, jobs boxes, EC2 instances, and instead we have Fargate instances.

[00:34:16] **Adam:** And we do have, I think, one remaining Fargate, like you're the jobs box, Fargate box, or Fargate, cluster service. Yeah, that's the right word, service. and, longer term. the, once we get to where we're like truly fully multi tenant where we just have like one, this is the code base, it's deployed, and everything scales up and scales down based on demand, then it won't matter, right?

[00:34:40] **Adam:** All the jobs will just run on the cluster and the cluster will scale up and down as appropriate based on demand. in the interim, I think that we are leaning more towards, especially because what you talked about with deploys, right? You If you have to think about whether or not it's safe to deploy, then something is wrong.

[00:35:01] **Ben:** Heh heh, well,

[00:35:02] **Ben:** yeah, not...

[00:35:03] **Adam:** sort of my philosophy is you should be able to deploy at any time, even in the middle of some critical process. and, you know, I don't think that we're fully there yet, but, we're getting closer and part of what is going to help us cross that finish line is like, serverless stuff approaches.

[00:35:24] **Adam:** So it's nice that Lambda now, I think, increased the time limit to 15 minutes for a Lambda thread. You're still paying for all that time. but you can, so if you deploy a Lambda while it's running, the current one continues while, what it's doing, and then, you know, future invocations will use the updated code.

[00:35:43] **Adam:** and so I'm kind of like leaning more towards some sort of, it's almost like maybe step functions or just, I don't know, like almost like dominoes knocking each other over sort of thing, but like, you know, okay, it's time to do the mail render job or process incoming web, web hooks or something. Right.

[00:36:02] **Adam:** And, and so the job runs a function that says, okay, well, and I need to go through the list of all customers who has this module enabled, and then of those people that have it enabled, who has data for me to work on, and then for each one of those, start a serverless function to, to handle that request. So that way they can all be running in parallel from the one job request.

[00:36:28] **Adam:** and, they

[00:36:31] **Ben:** Th th th...

[00:36:32] **Adam:** won't fall over if we do a deploy, that sort of thing.

## [00:36:35] Services and Monorepos

[00:36:35] **Ben:** It's... This is where I start to feel like my general experience with distributed systems really starts to fall apart, or I should say my lack of experience really comes to bear. when we have a single code base, a single application that we then deploy as two different services, like one services, this is the live application that the users use.

[00:36:57] **Ben:** And then this service, it's the same exact code, but it's the internal task runner. It, it's, it's two different services, but it is quote unquote the same application. It's actually the same code repository. So the fact that both of those services hit the same database feels like not amazing, but also not bad because they're really the same thing.

[00:37:18] **Ben:** We're just sort of drawing some boundaries around ingress traffic. Where it starts to get weird for me is that when you take When you take code that is in a completely different repository, like here's my application code repository, and then here's my lambda functions repository, and the code in the lambda functions repository may also hit the same database.

[00:37:41] **Ben:** Now I'm like, oh, that's starting to make me feel very uncomfortable. If for no other reason, because if I've pulled down a repository and I do a search for some query or some database column, and I'm like, Oh, there's nothing in this repository that references this database column anymore. I can probably drop it from the table.

[00:37:59] **Ben:** And then you do that. And all of a sudden, like a hundred lambdas start failing. You're like, Whoa, I didn't know that those were actually talking to this database and I'm, I'm not, I'm not. Throwing any shade, I'm saying like, there, there is definitely a academic part of my mind and a pragmatic part of my mind, and I don't know how to let those co mingle because I don't have the experience to back up the things that may or may not go wrong, if that makes sense.

[00:38:26] **Adam:** Yeah. And I mean, to just point out that there's, you know, the other side of the coin can be just as frustrating and,you know, full of, pitfalls. so we have, we have something in the neighborhood of like 25 lambda functions that are, you know, sort of like the everyday usage for our monolith.

[00:38:44] **Adam:** They're not part of the monolith, right? They've been pulled out to be. Lambdas, they're in the same repo, they're just often, you know, like, so you've got like, www is the, the monolith application. You've got the

[00:38:55] **Ben:** Oh, so you, you've almost got like a mono repo situation

[00:38:58] **Adam:** sort of. Yeah. And, and, and then there's a Lambdas folder, and we're, they're all in there.

[00:39:03] **Adam:** And so you've got, you know, let's just say 25 Lambdas. And then each of those, we have a QA and a production, right? So that we can make a change, test it, deploy it, or deploy it to QA lambda function, test it, make sure we're still happy with it. and then deploy it to production. So now you've got 50 lambda functions.

[00:39:20] **Adam:** And then, we have, GitHub workflows. That's how we do our, CI, CD, you know, deploys, all of that. Run the tests, deploys, etc, etc. And so, in our workflows file, there's, it's a ridiculous number of things, right? So you've got 25 lambda functions, you've got, 50. Just, this is just for the lambda functions, not for anything else.

[00:39:41] **Adam:** So you've got 25. yeah, run the tests for pull requests, 50 deploy scripts, because you've got QA and production. And then, you know, even more for other stuff, right? Beyond even just what we're talking about here. And the, the GitHub workflows interface for like finding a job that you want to run manually or something is not built for having, you know, hundreds of, of tasks that you might want to go through.

[00:40:06] **Adam:** It's capable. Of like finding the one you want, but you have to like, okay, show more, show more, show more. Okay. Now command F and, and find the one that I'm looking for. It's, it's frustrating.

[00:40:17] **Ben:** I gotcha. Yeah, yeah. Well, but at least. So my biggest, I don't want to call it a pet peeve, but like my litmus test is always, can I search for something and if I can't find it in that search, is that a safe indication that I can remove that thing from the universe? And at least when you're in a monorepository kind of approach, you, in theory, unless you have one of these like highly specialized situations where you have a monorepo, which are actually only like, Checking out parts of it because it's so huge you can't actually pull it down into a single computer.

[00:40:51] **Ben:** Like, I think Google, right? Or no, Microsoft. Is it like, like, Microsoft's entire world I think exists in a monorepo. But you

[00:40:58] **Adam:** But that may

[00:40:58] **Ben:** a bajillion terabytes. Yeah, maybe Google. So at least that gives me some peace of mind that even if the lambdas are being deployed separately, you can still, you know, Command Shift F or whatever your IDE of choice does for extended search and check for things and, and see that they exist.

[00:41:18] **Adam:** Yeah. Oh, and if anybody is listening and is using monorepos, here's another thing you can look into to save yourself some time and some frustration. GetSparseCheckout will allow you to like check out just a folder of your repo, right? So for like when we're doing Lambda deploys, right? That, that it doesn't care about any of the other code outside of this one Lambda function.

[00:41:39] **Adam:** Right? So I can say only check out the slash Lambda slash the one we care about for this script. Makes that checkout run a lot faster.

[00:41:48] **Tim:** That's cool.

[00:41:49] **Adam:** Cool. So, that's, that's, where my hat is at on cron visualization. Tim, you got, your son got you into Harvard?

## [00:41:58] Tim - CS50's Introduction to AI

[00:41:58] **Tim:** He did. Yeah, I just put his name in, but I'm actually taking the courses. No, um, a free, so I wanted to, you know, just. So every like Friday, I go up and visit my, my parents and I'll work from, work from their place and Friday's usually kind of a quiet day. So I'm taking this to do some extra learning and,taking a course.

[00:42:19] **Tim:** It's CS50's Introduction to Artificial Intelligence with Python from Harvard. It's free. It's pretty cool. It's good. They have,lectures, like a, it's a recorded lecture that you can watch. And then they have some code samples and then they have like quizzes that you take. And then, after you do the quizzes, you have code with the code samples as a problem you need to solve.

[00:42:41] **Tim:** So they kind of give you the boilerplate stuff to, very similar to, monthly, like every year they do like, a code, something days of code.

[00:42:49] **Adam:** Oh,

[00:42:49] **Carol:** the Christmas time thing.

[00:42:51] **Adam:** yeah. The calendar adds in a

[00:42:54] **Carol:** Advent Camp, yeah. Good job, Ben. Teamwork, you guys.

[00:42:58] **Tim:** Yeah. Advent. So it's kind of like Advent of code, but the code samples I gave you. but they give you a little bit more like how to parse the file and

[00:43:06] **Adam:** Yeah, that's,

[00:43:06] **Tim:** basically the main,

[00:43:08] **Adam:** to, like, learn something.

[00:43:09] **Tim:** yeah. Yeah. So, and as far as artificial intelligence goes, it's, you know, it's, it's a, so I took the first course, so they, they cover, it's like a 70 hour course.

[00:43:19] **Tim:** And if you pay some money, like 300 bucks, they'll give you a certificate to say, yeah, you completed a Harvard course, but I mean, it doesn't count toward. Anything other than just, you can print it out and put it on your resume. But, so they're covering like a search, the first one I took was search, but they go all the way to like neural networks and like language processing toward the end.

[00:43:41] **Tim:** and so I just thought it was interesting. So the first one I saw, I wasn't probably anyone who's been to college in the past, you know, few years probably did these things, but the, you know, the little game where you have like a, it's a square that has like numbers on it. One, two, and there's one tile that's missing.

[00:43:58] **Tim:** And you can slide the tiles around, you know, it's all mixed up and you try to fix that. Like that's the first episode, the first thing they get like, how do, how do you write a program that can figure that out? AI and like, where you create an agent and then you create the initial state. You represent the initial state, then you figure out what the goal is and then what actions in each state are available.

[00:44:21] **Tim:** And then, when you take the next, you know, action that's available, you go through, kind of go through the actions. And then figure out when that happens, do I reach the goal? And if not, am I closer than choosing that? and then also there was another one about like, basically pathfinding, depth first search, breadth first.

[00:44:41] **Tim:** So just greedy first and A star, just learning those kinds of things. And then adversarial search. Like they do, you have to write a program to do a tic tac toe game where you have to represent all the states and play against the computer. And so pretty interesting. I, I just, I just try to keep my mind a little more, A little more code related, doing a whole lot more stuff in my life that is not code related in my career.

[00:45:06] **Tim:** it just, cause I don't like the idea of, I would, after this, if I stick to this and finish it, I'll, I'll, look to see if there's anything about generative AI. Cause I don't like the idea of stuff looking like magic. Just, you know

[00:45:18] **Adam:** No, yeah.

[00:45:19] **Tim:** I mean? I don't want it to look like magic. So,

[00:45:22] **Ben:** Yeah, all the AI stuff to me very much feels like magic, and I'm even still having a lot of trouble trying to visualize how it fits into my life.

## [00:45:33] AI Fraud Prevention

[00:45:33] **Adam:** I did come up with one idea for something we're using. I don't know if I would even go so far as to call it AI, but maybe ML, machine learning. might be an interesting and potentially useful thing for us. And I, I may or may not have already mentioned this on the show, but, the idea was to use ML to help us identify fraudulent, credit card transactions or attempted fraud, right?

[00:45:56] **Adam:** So we

[00:45:56] **Tim:** kind of one of the reasons I want to learn it in the field I'm in, right?

[00:45:59] **Adam:** right. Yeah. So, I mean, as a human, I can see these requests coming in where it's like, okay, it's for 5 and the, the first and last name are just like, you know, G H J K L. and. you know, the, it's, it's, and I can see that there's like four or five requests all with the same address or whatever and different names and different credit card numbers or whatever.

[00:46:21] **Adam:** So it's, as a human, it's very easy to see that and go, okay, the pattern here, clearly somebody's trying to do something inappropriate. But like, how do you write that as code? It seems less obvious. And so my thought was like, I've got, these all come into us as API requests, so I've got, like, JSON payloads, and I can just go through it, like, here's a list of a thousand successful,what's the opposite of fraud?

[00:46:46] **Adam:** genuine or legitimate, charges, and here's a list of 500 ones that a human has verified to have been fraudulent. Learn to tell the difference, please. And then like, you know, if I could find some way to mark them, I wouldn't, I certainly wouldn't just be like, okay, we're just going to trust this new system, right?

[00:47:03] **Adam:** I'm going to like, try to like, put it in as like, this is what we think. And only use the feature flag to only show it to us. And like, and, and add training to like, okay, a new one came, comes in that the machine didn't find. We'll mark it as, as, new fraud or whatever. So more training data.

[00:47:19] **Tim:** Yeah, or even not, not even just fraud. So like, but, so we have a lot of data on chargebacks, right? So there's, there's certain people that will, I don't know what, for every reason they'll, they'll pay. And then afterward, they'll be like, Oh, I, I didn't, they'll challenge it. Right. They'll go to the card statement, either not recognize it, or they're just doing something unscrupulous and saying once they've already paid something, they're like, Oh, I want to, you know, they'll, they'll challenge it.

[00:47:44] **Tim:** Those are called chargebacks and just. And our industry that we do is like pretty low. It's like less than 1 percent of people do that, but still be nice. If you could like have a AI that kind of said, chances are this person's probably going to charge it back and then have some sort of way to try to get further info for them too.

[00:48:02] **Tim:** Cause if there's extra information that says basically says, yes, you did approve this, you, you know, you legitimately did this because normally they're like, Oh, I don't recognize this charge. It wasn't me. You can prove, yeah, it was you, then you can win those chargebacks. But it's interesting. So out in Vegas, when I was there, so PayPal came over to our booth and they're like, they're talking to us about stuff and they were explaining how all the stuff they do, I didn't realize PayPal did more than just plain old PayPal transactions.

[00:48:29] **Tim:** They actually do a lot of the credit card processing themselves.

[00:48:33] **Adam:** Did you

[00:48:33] **Tim:** And they're, they're, yeah, I think they might be a bit out of our range. but, yeah, they're talking about all this stuff. They, I don't know if they're using AI, but they use a whole lot of features to like prevent fraud. Like he was saying, you know, if, if you live in, you know, California and then all of a sudden we see a charge from Vietnam, we can't, you know, reject that charge and never, never even tell you like, well, what if I were just visiting Vietnam?

[00:48:58] **Tim:** It's like, well, That's your problem.

[00:49:01] **Adam:** Mm.

[00:49:01] **Carol:** Oh,

[00:49:02] **Adam:** Mhahaha.

[00:49:04] **Tim:** Should have told us you're going there. yeah. So I don't know what level the card, the card people are doing that at, you know, like the visas, the master cards. I imagine they do some, but I mean, with as much credit card fraud that goes around on around the world, it's like, I think they just, that, well, that's just the price of doing business and they eat it.

[00:49:22] **Adam:** Man, that must be nice to have such a high margin that you can just be like, Meh, we'll just let that one go.

[00:49:28] **Tim:** Yeah, for sure. We don't care.

[00:49:30] **Tim:** I'm done. How about you, Ben? What's on your bench?

## [00:49:35] Ben - Book Progress

[00:49:35] **Ben:** I've been continuing to write my book about feature flags, and I'm pretty excited because I, so, the book is sort of split up into two halves. Not in any official way, but the first half is much more technical, and the second half is much more philosophical. I'm like, how teams get organized and how feature flags maybe fit more into the overall.

[00:49:58] **Ben:** Team and workflow structures. Yeah, exactly. And I, I have, the first half of the book fully drafted out. I'm not saying that it's a good draft and that the chapters are in the right order and then the words make sense yet, but I actually have words associated with all of the chapter titles in the, in the first half of the book, and I'm now starting to work on the second half of the book, or I've been working on the second half of the book for about the past week now, so I'm feeling pretty great about that.

[00:50:28] **Ben:** I have gotten to the point where I'm actually starting to try and look up how you actually take content and turn it into a published thing. there's an application called Pandoc, which seems to be coming up over and over again. It's just a command line utility, and you say, like, here's my input, and here's some metadata, and some copyright information, and some cover art.

[00:50:49] **Ben:** And you tell it EPUB version 3 or MOBI, whatever, and it's supposed to spit out a file. I haven't actually tried any of this yet, but, in theory, there's a path forward. And, I'm, I'm getting to the point where I'm, I want to start to play around with that. And I'm also, I opened up a, a Gumroad account.

[00:51:06] **Ben:** Adam suggested Gumroad on a previous episode. I have not done anything in it yet. I was. At first I was excited because I Googled for, for like, how do you turn Markdown into EPUB using, Gumroad and you can't really do that, but they do have some sort of new docs functionality where you can author Markdown directly in Gumroad, I think, and then publish that way.

[00:51:30] **Ben:** But I'm not going to, I'm not, you know, I have, I have it all written in MD files locally.

[00:51:35] **Adam:** Okay.

[00:51:35] **Ben:** going to copy paste anything, but, anyway, so I don't have too many details there other than I'm making, I think, really great progress and I'm excited to maybe be done with this.

[00:51:47] **Adam:** Hahahaha. So, d d d Have you... I I know you've got... Is it is it all of what you've written? Or or, you know the the completed rough draft sections? is that what's posted on the website?

[00:52:00] **Ben:** Yes, they're on the website. They're truncated, you know, you get the first like couple of paragraphs in each chapter there, if you see a chapter that's just bullet points, then I have not written anything yet.

[00:52:11] **Ben:** Um, so I think I have maybe like four or five chapters that are just bullet points at the end of the book now.

[00:52:18] **Ben:** And, you know, I'm, I, I I was gonna say, I do want to start thinking about monetization strategies. At this point, I had originally thought, well, okay, let me, if I draft the first half of the book, then maybe I can do a pre sale for the first half, cause that feels like some meaty enough content and then continue to flesh out the back half of the book.

[00:52:39] **Ben:** But I almost don't want to get distracted now. You know, we talked on a previous episode about going down rabbit holes and kind of doing the wrong work and like, but when it comes to a monetization strategy, it's, it's a little harder to say, which is the right work and which is the wrong work. Cause if I can get people invested in the journey of the book, then that's not necessarily the wrong work.

[00:53:01] **Ben:** It's a, maybe setting the book up for more success. I don't know. So

[00:53:07] **Adam:** Yeah, I mean, I don't claim to be any sort of professional at the, at what I'm about to describe, but the impression that I get from watching people who have done very well at this process of, like, building something in a very visible way, where they're talking about it as they're building it, kind of like you've been, I've seen your Facebook posts on it, um, you know, they talk about it as like, okay, so, you know, I'm working on the thing, And I can just take little bits and pieces of that, you know, some interesting thought or a screenshot of the thing that I was working on, whatever, and call that like sawdust from working on it, right?

[00:53:38] **Adam:** It's just a little by product. And I can sprinkle that out over time as, as, you know, teasers and ways to keep people interested and aware that this is going on and, and the more of it that I share. the more likely it is that people that see it are, are, going to find one that resonates with them and reshare it.

[00:53:58] **Adam:** And so that can increase awareness, increase the audience size. you know, and honestly, like, and again, I, I'm talking out of my butt here, cause I have no experience doing any of this and, and, you know, no, success to draw on in this. approach, but I've heard people say that doing a presale, can generate that same enthusiasm.

[00:54:23] **Ben:** Mm. Yeah. I think I have to do even if I don't go with the first half of the book is the impetus for the pre sale, having a rough draft I think is still a very legitimate thing because it could take me a while to, to polish it a little bit and, and fine tune chapter orders and, and, you know, thesis and conclusion kinds of stuff.

[00:54:44] **Ben:** So is it, I have a book here around here somewhere. and if you want, I can find it and send it to you. I think it's called Write Useful Books. heard of this.

[00:54:52] **Adam:** okay. Yeah. It's by the same

[00:54:53] **Ben:** may have recommended it in a previous episode.

[00:54:56] **Adam:** I probably did. It's by the same guy, Rob Fitzpatrick, who wrote the book that I read, while I was preparing for my taffy workshop.

[00:55:03] **Adam:** And it's all about, well, I haven't read that much of this book, right? Useful books, but I have followed the guy and I'm aware of some of his other stuff. And he has, like an online,like an author community, I guess you would call it. And, and there's a tool that you can use to do like beta reading for your, for your content, right?

[00:55:23] **Adam:** So you can say, here's my book content and you can get beta readers to sign up. And you could, you could even say like, okay, if you pre order the book, then you can be a beta reader and you can give me feedback that could affect the final version of the book, right? Like if I, if you found this story.

[00:55:38] **Adam:** confusing, or if you feel like this description in the technical half of the book is not good enough, right? Like that could make the book better for you and for everybody else.

[00:55:50] **Ben:** Yeah, I like that idea.

[00:55:52] **Adam:** then the thing I keep thinking about too, for myself personally is part of what was good for me about doing pre orders when I did my book was it made me feel responsible for finishing it, right? It wasn't, I didn't have that like, ah, I don't have

[00:56:07] **Adam:** to finish it. I don't owe anybody anything. It's accountability.

[00:56:11] **Adam:** And it helped me stay motivated to finish it and just get it done as fast as possible. And, and then, you know, probably about a year later, I like kind of revamped the whole thing anyway, just because like, you know, you read it enough times and you start to come up with better ways to say things, better examples,

[00:56:31] **Ben:** Yeah.

[00:56:33] **Adam:** And you can push it for Black Friday. There you go.

[00:56:36] **Ben:** Well, that's what I, I, I, I have not not been thinking about that because it is November and, and Black Friday is coming up and I, and I would love to be able to get something available by then, which, so at the time of this recording is, it's November 6th and Black Friday is what, like the 25th or the 26th or something?

[00:56:55] **Carol:** It's the day after Thanksgiving. The 24th, maybe? A

[00:56:58] **Ben:** 24th? I don't remember when Thanksgiving is.

[00:57:01] **Ben:** It's, it's, it's.

[00:57:02] **Adam:** The fourth Thursday of November.

[00:57:04] **Ben:** Yeah, yeah, yeah.

[00:57:06] **Adam:** Anyway. All right. Is there anything else we want to discuss before we wrap it up for the night? I got one thing I want to throw out. and it's entirely selfish and self serving. Not, not selfish for me because I, I will get nothing out of it. But, so I'm doing Extra Life again this year.

[00:57:20] **Adam:** Play video games to raise money for charity. I will have a link in the show notes and I'll post it in our Discord. And let me do this. even if you're just listening, it is, tutt.xyz/extralife. E X T R A L I F E. I haven't created that yet, but I'll create it before this goes out. and that will link you to the page where you can go to donate.

[00:57:41] **Adam:** and it's basically collecting money for Children's Miracle Network, which is a charity that pays, for medical bills for kids in the hospital whose families can't afford to pay for their care. and it's a pretty awesome charity. I've, I've been supporting them for years and years and love doing it.

[00:57:57] **Adam:** And it's a good excuse for me to get my friends together and stay up all night playing video games, which is fantastic. And now my kids are old enough, like, my, my youngest wants to, stream on, he streams on Twitch a couple of times a week right now anyway. And so now he's planning on doing like a 24 hour stream, playing Minecraft, which, yeah, I guess if you're into that thing, it's pretty,

[00:58:18] **Carol:** lot

[00:58:19] **Carol:** of kids are. Yeah.

[00:58:20] **Tim:** They are.

[00:58:22] **Adam:** So, cool.

## [00:58:23] Patreon

[00:58:23] **Adam:** Okay, this episode of Working Code is brought to you by Shabu Shabu, the onomatopoeia of your choice. and listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:58:36] **Adam:** Our patrons cover our recording and editing costs and we couldn't do this every week without them. Oh, and our, I gotta put that in the, my notes here for the, the outro, and our transcription costs as well. and so, Patrons, thank you very much. We really appreciate y'all. Special thanks, of course, to our top patrons, Monte and Giancarlo.

## [00:58:54] Thanks For Listening

[00:58:54] **Adam:** We are about to go record our after show. Looks like tonight on the after show, Ben is going to rant about short form video content. should be good. And Carol, apparently, I didn't hear about this, apparently there was some sort of a human error that resulted in direct deposits not working. so Carol's going to ask us about that and hopefully Tim has an answer.

[00:59:13] **Adam:** but you gotta get on the after show to, to find out how that goes. as a reminder, we are going to turn off the Patreon free trials at the end of the year. So if you want to give it a shot, you go to patreon.com/workingcodepod. See what that's all about. You can support us for, I believe it is as little as 4 a month, and it's actually even lower than that.

[00:59:33] **Adam:** If you'll go, there's a discount if you pay a whole year at a time. so less than 4 a month, less than a dollar a week. anyway, that's going to do it for us this week. We'll catch you next week. Until then.

[00:59:44] **Tim:** Remember, your heart matters, and it's on fire on that heat map after
