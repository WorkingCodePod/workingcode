---
title: "031: To the Cloud! But Why?"
description: 'What is "The Cloud"? Why and when would you choose to use it? And what are the drawbacks and trade-offs?'
date: 2021-07-14
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/031-to-the-cloud-but-why/id1544142288?i=1000528845195"></iframe>

There is no _one thing_ that is "The Cloud". Instead, there are a set of _general characteristics_ that underscore cloud technologies: we can provision, deprovision, and scale resources at will; we don't need to manage those resources; and, we only pay for the resources that we use. But, even within this definition, there is a broad spectrum of technologies that more-or-less fit the bill. From Geocities, to managed hosting, to elastic clouds, to distributed edge-computing, lots of things _kind of look like "The Cloud"_, depending on how hard you squint.

This week, the crew talks about what The Cloud is and why people are so keen to adopt it. And, of course, since nothing is _truly free_, we'll also take a look at the drawbacks of cloud-based architectures.

Follow the show! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media][editor].

[working-code]: https://workingcode.dev/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[editor]: https://www.zcross.media/
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/031-to-the-cloud-but-why.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Adam:** I mean, it does still occasionally happen. They'll be like, you're still on the old hardware and we just need you to reset your box. And when it comes back up, it'll be on the new stuff. That's pretty painless though. I mean, yeah. That's

[00:00:11] **Carol:** not, oh, I need to go offline and replace the entire switch in my data center.

[00:00:16] **Carol:** Spend my Saturday doing

[00:00:18] **Ben:** it.

[00:00:18] **Adam:** Well, I

[00:00:19] **Tim:** configured the firewall wrong and the NAT wasn't hitting ICP correctly. So, uh, sorry about the 24 hours of downtime.

[00:00:29] **Adam:** While

[00:00:30] **Ben:** I smoke.

[00:00:33] **Tim:** Clip my pony tail.

[00:00:36] **Adam:** Wow.

[00:00:52] **Adam:** All right. Well, it is show number 31 for July 14th and on today's show, we're going to be talking about to the cloud, but why, and as usual, we're going to start with our triumphs and fails and it looks like it is my week to go first. So I'm going to start it off by saying I am just. All over the place. I couldn't decide.

[00:01:08] **Adam:** I've got so many goods and so many bads going on right now. I couldn't choose. I'm just going to kind of lay my hand down on the table here. Uh, I mentioned last week I had my books in hand and I was, uh, starting to collect money for pre orders and get those into the mail. And so as of today, that first batch of books went out in the mail.

[00:01:27] **Adam:** So anybody that's paid me by today got theirs in the mail and looking for it. Yeah. Yep.

[00:01:33] **Carol:** Yep. I heard one's coming

[00:01:34] **Adam:** to Warner Robins. Yep. Two of them to Georgia. Yeah, so what else? I've been, it's been a rough week for me at work, um, just in terms of like struggling to find motivation. The thing that, so I have ADHD and the thing that I'm working on isn't urgent and it's not novel and it's not, um, super interesting to me and I'm just, I'm just struggling to find that motivation and I think that I'm just gonna, it's gonna be one of those things where I just have to push through.

[00:02:00] **Adam:** But, you know, sort of, again, flipping back the other way, today, at the very end of the day, like, even after I was supposed to be done working for the day, and I still was, I figured out a neat trick with npm scripts that I'm going to be blogging about to Probably whatever it's a, it's a tech nerd thing that is way too deep to discuss here.

[00:02:19] **Adam:** Uh, and, and then, you know, again, back in the other direction today, I got an email that my gym is closing down like permanently. And I mean, I just started going back, you know, I I'd stopped going because of COVID. I just started going back like two weeks ago. So now I got to figure out where I'm going to go instead.

[00:02:34] **Adam:** Or maybe I'll, maybe I'll take this as my moment to like do the research and get a squat rack and a bench and some plates and do it at home or something. I don't know. To talk to somebody. But yeah, I mean, I'm just all over the place. I can't even think straight right now. So that's me. Who wants to go next?

[00:02:49] **Adam:** Ben, don't you work out at home?

[00:02:51] **Ben:** Yeah. I have a, we, we were in a co op and we rented a garage in the next building and, uh, I have a squat rack pushed up against the, uh, the back of the garage. Um, it's been great. I, I miss the camaraderie of being in the gym. I don't need, I don't even know if I'd say camaraderie cause I'm not like a very social person, but, but there's an energy, you know, and you get the music and the people.

[00:03:15] **Ben:** Yeah.

[00:03:16] **Carol:** Yeah. Seeing the other people lift is like my like, okay, I can push harder.

[00:03:19] **Adam:** Yeah. It's, but it's a double edged sword. Right. Cause then you have to like wait when somebody is using the stuff you want to use. A hundred percent. Or, or you have to like, you, you see them sweating all over it. And even though when they're done wiping it down, I'm like, you know, I think I'll wipe it down again.

[00:03:34] **Adam:** I'm that person. Yeah.

[00:03:36] **Ben:** Yeah. Having it at home is great because it's, it's a, you know, 60 seconds from my door to the garage. So. Yeah. Yeah. Yeah. I mean, you

[00:03:44] **Adam:** get, you get all that time back. And you get to control what's on the TV while you're working out. Yep.

[00:03:49] **Tim:** Which, which bench in there being like 130, 140, something massive like that.

[00:03:52] **Adam:** Yeah. A little bit. Yeah. With one pinky. No, no, no. My,

[00:03:56] **Ben:** my bench is like one of my weakest things. Plus I've always have some sort of shoulder discomfort and stuff. It's getting older. Everything's getting

[00:04:03] **Adam:** older. All right, Tim, what do you got going on this week? Well,

[00:04:06] **Tim:** you know, I've had a series of failures and I'm, I'm trying to turn this boat around and, uh, I'm going to call it a triumph.

[00:04:12] **Tim:** You know, I talked. I think it was last week where I talked about how that each day I, I get to inbox zero first thing in the morning is what I do. And then I, I think about, I look at my list of my checkbook, my checklist of things that I'm working on, and I ask myself, what am I avoiding? Mm-hmm. Well, today I, I ask myself that, but I also, I ask myself, what, what is the thing that I am the roadblock on for other people?

[00:04:35] **Tim:** Okay. Because I'm trying to get to a point where, People need me less. That sounds terrible. I want them not to need me. Well, you are getting old. Yeah. You know, I did, I did have a birthday. I just turned 50 last week. So the big five Oh, and one thing I realized is that because we don't have log aggregation, I tend to be the one that when something goes wrong and it's not often, but they're like, Hey, can you look into the, what's going on with this?

[00:05:03] **Tim:** I'm like, I don't know. So I guess stop what I'm doing. I go on a machine and I. Grep a log or tail the log or do whatever it is. And then what's the wrong instance. So I go to another machine. I'm like, this is ridiculous. We don't have any, we have all these services and all the logs are just local to the machine they're running on.

[00:05:21] **Tim:** We don't have any log aggregation. And so I said, all right, today's the day I'm going to start researching. So started researching. I'm looking at different things right now. I'm looking at Apache Flume. But yeah, if any of our listeners out there have suggestions for me about, uh, log aggregation and things that they use, they like or whatever, shoot me, shoot me a line on Twitter or something.

[00:05:42] **Tim:** I would definitely appreciate the feedback.

[00:05:45] **Adam:** A little more tech

[00:05:46] **Carol:** stack. What are you logging? Are we talking CF logs? You want to look at AWS logs? You want to look at application logs? So Windows errors, all you want, everything all, all the, all the

[00:05:56] **Adam:** logging.

[00:05:57] **Tim:** Well, it's, so, you know, we got, we have a, our scholar stack and it's writing to, to a log file.

[00:06:02] **Tim:** And you know, you got our ColdFusion stack and Lucy Stack, they're writing to different log files and then, um, you know, we have a, a s and they have their own log files. I want all of that. All of those are aggregated together.

[00:06:12] **Adam:** And I mean, this is kind of relevant to today's topic. You said you have all these things and you listed AWS as one of them.

[00:06:18] **Adam:** I was going to ask, like, what, you know, where is your cloud? Are you Google Cloud Platform? Are you AWS? Are you self clouding? We're all of those. Oh my

[00:06:27] **Carol:** gosh. And some, you have some prims,

[00:06:30] too.

[00:06:30] **Adam:** That sounds painful, dude. Yeah. Yeah. It's, it's,

[00:06:32] **Tim:** well, no, no, it's the hybrid cloud, right? That's the negative thing. It's the worst of all worlds.

[00:06:39] **Tim:** Yes. Yes. The worst of all worlds. We got Azure. We're on Azure. We're on AWS. We're on on prem. Yeah.

[00:06:46] **Adam:** Remind me to not come work for you. For

[00:06:49] **Carol:** anyone who doesn't know, on prem means you have it in a server room, like at your building. If you On

[00:06:55] **Adam:** premise. Yeah. And then,

[00:06:56] **Tim:** you know, and then our on prem is like, so we have our regular environment, then we have our PCI environment, and then we have the replicated systems that are going to our, you know, we copy everything to a geolocated second place in case, you know, our building burns down.

[00:07:10] **Tim:** So yeah, it's a lot to log.

[00:07:12] **Adam:** I have to say. So if any of

[00:07:13] **Carol:** you have that stack, help

[00:07:14] **Ben:** Tim. I'm just, given how much you are into technology and how significantly advanced it seems like your system is. I'm, I'm a little shocked that you don't have log aggregation. I

[00:07:26] **Tim:** know. I know. Yeah. Trust me. It's, it's, it's embarrassing to say out loud.

[00:07:31] **Tim:** I, I, I like tasked people years ago, I'm like, look, we got to have log aggregation and it just went nowhere. I'm like, all right, if I, if I'm going to get something done, I've got to, I've got to rally this thing and do it. And people are just going to have to follow me because no one wants to be the leader on this.

[00:07:46] **Tim:** I

[00:07:47] **Ben:** have no idea how it really works. At, uh, at work, but I, essentially all of our systems just write to the standard output. And, uh, and then I think like maybe all of the pods have some sort of a sidecar that's consuming that, uh, output and doing the log aggregation. It's

[00:08:06] **Carol:** like magic back there.

[00:08:09] **Tim:** Yeah, that's what she said.

[00:08:13] **Adam:** Oh, no. Oh, dang. Here we come PG

[00:08:16] **Tim:** 13. Well, that's

[00:08:18] **Adam:** me. How about you, Carol?

[00:08:20] **Carol:** All right. So I'm going to go with two triumphs first, you know, just to update. The bird eggs are still there. I did get asked about them, you know, there's three bird eggs in my backyard and I'm slowly watching

[00:08:32] **Adam:** them. You should do like regular bird updates on our Instagram.

[00:08:36] **Carol:** Maybe I should do that. You know, man. Okay. I'll try. I'll do my best. No promises. Um, and then the other thing is I've been struggling kind of with just some personal stuff going on. And this past weekend, I was having dinner with my son and his girlfriend and just popped up like, Hey, let me show you this baby picture of Peyton and let's embarrass him.

[00:08:56] **Carol:** Right? Well, then like, I sort of go, Every... It's the best thing ever. You don't know you love it till you love it. So, um, while looking back through pictures, I realized that I have a lot to be thankful for. I've had a lot of really good things happen in my life. And I'm really glad that I spent the time kind of looking back and just reflecting on where I've been and where I've come from.

[00:09:19] **Carol:** And it totally took the pain of kind of everything right now. And just kind of like washed it away a little bit. It reminded me that I have a lot of good things and that I should love myself a lot more than I do when things go wrong. And it's okay to, to have happy moments and to like, go back and reflect on those.

[00:09:40] **Carol:** So I had like made this post on Facebook and it wasn't like, Hey, come like, give me love or whatever. It was more of, if you're going through something. Be glad that you back up your photos to Google Photos and just go scroll through them, because every picture I've taken on my phone is in Google Photos.

[00:09:55] **Carol:** So I'm going through like t ball pictures. I'm looking through all these things with my kids and it's just, it's good to have those memories. It's good to, to know that it's okay. Things are good. So that.

[00:10:09] **Ben:** Yeah. Yeah. That's awesome. Scrolling through my phone's photos, it's pretty funny because it's sort of the timeline of my life. And, and you can see like, Oh, here's a, you know, pictures of me with my friends before I met my, uh, my wife and then like, Oh, here's when I met my, uh, you know, wife was my girlfriend at the time.

[00:10:26] **Ben:** It's a lot of pictures of her. And then it's like, then we, then we got a dog and then it's like the next 8 million photos.

[00:10:32] **Adam:** Yep. Yep. Same.

[00:10:38] **Carol:** But you so happy when

[00:10:39] **Adam:** you look through them? No, it does for me. I

[00:10:41] **Ben:** don't know about the wife so

[00:10:43] **Adam:** much. And what was that thing you said? Or I don't know if it was on the podcast or what, but you like, you're taking pictures of her talking to the dog.

[00:10:52] **Adam:** And then the wife was like, uh, what am I? Chopped liver? Like sometimes

[00:10:56] **Ben:** I'll just look at the dog and I'll be like. I love you. I love you so much. You're so beautiful. My wife will just, she'll jump in with a response.

[00:11:07] **Adam:** Thank you. I appreciate that. That's funny.

[00:11:11] **Tim:** You know, Carol, I'm glad to hear that. You know, I've known you a good while.

[00:11:15] **Tim:** I said this the other week that we had a mid year strategy session and I kind of said this at the wrap up at the end that homo sapiens are, they're funny creatures because we got these really big brains and we have these very good eyes. We have extremely good eyesight for animals, but we're upright.

[00:11:33] **Tim:** And so we can see really, really far in the distance. So if you're like out in the, you know, out in this area, you can see pretty much

[00:11:42] **Tim:** We're not the fastest creatures. So we're looking almost into the infinite distance and it feels like we're never getting there, but step by step we are. That's our, that's our superpower, right? We just keep going. We do. But it's incremental, right? And so if you don't ever stop and look back and go, wow, look how far I've came.

[00:12:01] **Tim:** You might feel like you're never getting anywhere. I completely agree. Yeah. So as humans, you just got to stop sometime and just take it in and you know, count your blessings or whatever you want to call it. Incremental improvement day by day. It doesn't seem like a lot, but when you look back, you realize you've really come, you've come a long way, baby.

[00:12:20] **Adam:** It's a lot. Yeah. Yeah.

[00:12:23] **Carol:** What about you, Ben? Um,

[00:12:25] **Ben:** I'm going to go with a little bit of a failure here. I have, so I consider myself a T shaped developer. I think we've talked about that on previous episodes where I'm experienced in a wide range of things, but I've been very focused heavily on the ColdFusion side of things for the last couple of years, I guess, maybe like the last two years, I've been very ColdFusion oriented.

[00:12:47] **Ben:** And, uh, I'm a little bit starting to feel like. Some of the JavaScript stuff is not passing me by, but I feel like I'm getting rusty and I'm starting to let the imposter syndrome of, of being more of a foolish stack developer. I feel like that's creeping in. And then I'm also getting a little bit of the, uh, the FOMO, the fear of missing out on, on some of the more fancier front end type things.

[00:13:12] **Ben:** I don't know. It's not a good feeling. So I feel like I want to start to focus more on some client side development and just do a little bit more research and development. I used to do all kinds of fun little experiments in Angular as the new versions were coming out. You know, Adam's been talking about, uh, next.

[00:13:32] **Ben:** No, no. Have you been talking about next? Am I getting that confused? Next and you're heading heavy into react. I know that Gatsby and like, I, I, I hear all these things get discussed on various podcasts, but I'm just, yeah, I'm

[00:13:44] **Adam:** like, well, I mean, if I can maybe temper your, your Emotions? I don't even know.

[00:13:51] **Adam:** Whatever. Yeah. Yeah. Something on this. Your FOMO. Yeah. Help you just help you, uh, take that more as a glancing blow. You know, when you listen to a podcast like Syntax, like those guys, yes, they, they go all the new stuff very deep, very fast all the time constantly. And it's crazy the amount of stuff that they get through, but then you think about it.

[00:14:09] **Adam:** That's kind of their job, right? Their job is to get through that new stuff so they can be there in the beginning to explain it to somebody who's ready to pick it up. Yeah,

[00:14:18] **Ben:** it's true. And you know, the reality is at work, I'm doing both server side and client side development, but the client side stuff I do uses a very old version of AngularJS.

[00:14:30] **Ben:** And I know, and I accept that the foundational stuff is all very, very much transferable to, to more modern versions of both Angular and other frameworks, but it's hard. It's hard sometimes not to feel like you're. Missing out or you're, you know, you're not at the cool kids table at the cafeteria. But you can

[00:14:50] **Carol:** always sit with us.

[00:14:51] **Carol:** Thank you. Always sit with us. We'll create

[00:14:53] **Adam:** the loser's

[00:14:54] **Carol:** table. I didn't say it was a cool kids table, but you can definitely

[00:14:59] **Adam:** sit with us. the podcast, the

[00:15:01] **Ben:** loser's table, but I will say that I did have one sort of triumph. This week and that it's, so it's super hot out recently. We're having a heat wave, at least in the Northeast.

[00:15:11] **Ben:** I assume we're having heat basically everywhere right now in this pre apocalyptic time. Um, so I went to Best Buy, we have an Apple TV, so I went to Best Buy and I got this Bluetooth transmitter. So I take the Bluetooth transmitter and I plug it into the TV and then both me and the missus can wear headphones.

[00:15:33] **Ben:** And listen on the Bluetooth transmitter so we can keep the air conditioner. Cause we have, we have in window air conditioners and they're like jet engines. So what we used to do is turn the air conditioning off to watch TV and like basically boil until it was time to go to bed and then hopefully flash freeze the room.

[00:15:51] **Ben:** That sounds awful. So now we can, we can watch TV with the headphones on together with the air conditioning running.

[00:15:59] **Adam:** That sounds amusing to watch, but did, like, do you guys have some aversion to just turning the volume up on the TV? It's well, well, aren't you in like a duplex? So we

[00:16:06] **Ben:** share, we share a wall and this building was built in like 1942 and it, and there's no insulation.

[00:16:13] **Ben:** So you, it's, there's not a lot of sound dampening. So we're just, you know, you're a

[00:16:18] **Adam:** nice neighbor, trying to be courteous. That's fair. Give me that. So, but

[00:16:22] **Ben:** it was, it was, uh, it's a game

[00:16:24] **Adam:** changer. That sounds cool. My headphones. My wife and I wear headphones when we watch TV at the same time.

[00:16:31] **Ben:** Well, but it's great because it's, you can, uh, if anyone doesn't know this, you can connect Bluetooth headphones to an Apple TV, but only one person can do it at a time.

[00:16:42] **Ben:** So what we needed was the transmitter that essentially is a splitter for Bluetooth.

[00:16:46] **Carol:** Yeah. Cool. That's pretty cool. Yeah. I didn't

[00:16:48] **Adam:** know you could do that.

[00:16:50] **Tim:** I've got an RF. It's not Bluetooth. It's RF transmitter. It's great. I can walk all the way to the other side of the house and still listen to the

[00:16:57] **Adam:** TV

[00:16:58] **Carol:** show.

[00:16:58] **Carol:** Is that radio frequency? Is that what RF stands for? Yeah, radio frequency. Okay. Yeah. I didn't really know what RF was. It's old

[00:17:04] **Tim:** school technology, dear.

[00:17:05] **Ben:** I guessed.

[00:17:07] **Adam:** Okay, sounds like we are ready to go to the cloud, the cloud

[00:17:11] **Carol:** and beyond.

[00:17:13] **Adam:** Yeah. But why? Yeah. Yeah. Yeah. So, you know, everybody's heard it. You know, the cloud is just somebody else's computer kinda, right?

[00:17:22] **Adam:** So I think we, if we're going to have this discussion, it makes sense to discuss what we mean by the cloud, right? So the definition I had in mind was, you know, A, yes, it is somebody else's computer, but it's not just because it's somebody else's computer doesn't make it the cloud, right? Like I can run a server on a, on a computer in my office and expose it to the internet.

[00:17:43] **Adam:** That doesn't make it the cloud that makes it my computer. As far as you're concerned, so, and it's not

[00:17:48] **Tim:** hosting where you're buying a machine dedicated machine, right? That's

[00:17:52] **Adam:** hosted, right? Cloud is, so, yeah, to me, I guess the cloud means, um, kind of two things. The 1st would be, um, I can kind of commission it and decommission it at will.

[00:18:06] **Adam:** And the 2nd is that it is not. In like my purview and when I say my I'm really kind of meaning like you know my company or if this is me personally it's you know it's not a server on in my bedroom under my desk or something like that. Yeah, I think of

[00:18:22] **Carol:** shared resources. Yeah. Like that's a good way to put it.

[00:18:24] **Carol:** Like I'm on this box, if you want to call it that, but there could be a whole bunch of other people on that box too, all sharing the resources. So when I'm down there up with those resources. I

[00:18:34] **Adam:** think, you know, before we saw Google cloud and AWS really take off, I think that tons of companies had huge amounts of.

[00:18:42] **Adam:** Uh, money and hardware in their data centers and they were doing like huge VMware installs and you would like provision a VMware instance from your IT group and that sort of thing. And it's like, that's the idea, but now we're sort of abstracting that out outside of your company. So that's what I think of when I think of the cloud.

[00:19:01] **Adam:** Does anybody think of something

[00:19:02] **Ben:** different? I think one additional thing, and I think Amazon Lambda really brought this to people's attention, is the, is how you think about paying for usage.

[00:19:12] **Adam:** Yes. Oh yeah. Absolutely. Pay for what you use. And

[00:19:15] **Ben:** Lambda, didn't they, they went from like paying per 100 milliseconds or something down to like per 10 milliseconds, something nuts.

[00:19:25] **Ben:** Yeah.

[00:19:25] **Adam:** The granularity is crazy. Yep. Absolutely. Yeah. It was kind of annoying to have a Lambda that would run for 3 or 10 milliseconds and have to pay for the full hundred. Yeah.

[00:19:36] **Carol:** Fixed it. It was awful. Those

[00:19:38] **Adam:** pennies. Right. Add that up though. So, all right. So it sounds like we're kind of in agreement on what the cloud is.

[00:19:45] **Adam:** So the first question I wanted to ask the three of you, see, I said the three of you this time instead of the four of you, was what was each of your first exposure to using cloud services? And like, when do you think you really started to take advantage of, you know, quote unquote real cloud computing? I

[00:20:03] **Ben:** mean, I have, my blog is on managed hosting with

[00:20:08] **Adam:** host tech.

[00:20:08] **Adam:** So managed hosting, is that different from shared

[00:20:12] **Ben:** hosting? Well, so I'm on, I mean, I don't know, I don't know. I'm on a, I'm on a VPS, I guess, but it's probably virtualized. So it's probably a VPS that's actually part of a much larger machine, I

[00:20:23] **Adam:** assume. So VPS stands for Virtual Private Server. And when I think of VPS, I think of like what we're talking about with VMware, but then it's, it's outside of your company, right?

[00:20:32] **Adam:** You know, it's, uh, you know, you're doing that. Somebody is providing that as a, as a business.

[00:20:37] **Ben:** Right. And so part of what the managed aspect of it is. They manage the infrastructure, they manage the database backups, they manage the disk backups. OS patching. Yeah, they'll do the patching. I can get them to do the ColdFusion updates, because for whatever reason, whenever I try to run it manually, it doesn't work.

[00:20:55] **Ben:** And they'll provision SSL certificates. And it's like, intellectually, I know I could maybe do some of these things, certainly not all of them. And I probably couldn't do all of them well. And the reality is I don't want to spend my time thinking about that stuff. It's not my skillset. So I'd rather just pay someone, you know, some amount of money to do it

[00:21:17] **Adam:** for me.

[00:21:18] **Adam:** That managed aspect. That's another good definition to throw out there for part of the cloud, right? Somebody else does a good chunk of that. Work that orchestration and management. It's a bit, I,

[00:21:28] **Tim:** I mean, I wouldn't say that what that, what you just described, the VPS, it wouldn't be the cloud, right? That's just, well, it's, it's

[00:21:36] **Ben:** you renting a box spectrum of the things I don't have to manage, you know, it's at the lowest, it's at the lowest part of that totem

[00:21:45] **Adam:** pole.

[00:21:45] **Adam:** Maybe. And that's exactly what I was asking for. Yeah. Like, what was your, how did you dip your toe into the cloud? And I think that that's a good answer. For me,

[00:21:54] **Carol:** I started a GCP project. So Google Cloud Platform project, when I...

[00:21:59] **Adam:** What's a GP? Google Cloud

[00:22:02] **Carol:** Platform, GCP. Yeah. So I wanted my inbox to basically not really be an inbox.

[00:22:09] **Carol:** I wanted to filter every one of my emails by the domain that it came from. So they all had labels on it so that I could easily just go find everything that comes to my inbox and get it to spam quicker and not look at things. So I just wrote an app script, you know, just like a Google app script that goes through and takes my emails and puts a label on it based off the domain.

[00:22:27] **Carol:** And that's just running in GCP. So that was my very first like exposure to having code executing that's free, doesn't cost me anything.

[00:22:36] **Adam:** That's how long ago was that?

[00:22:37] **Carol:** Um, Ooh,

[00:22:40] **Adam:** six years. Okay. Yeah. I feel like I came late. First toe into the water. Yeah.

[00:22:45] **Carol:** It's not that hard. Just go Google it and you'll find some examples like how the app script itself works.

[00:22:51] **Carol:** So once you figure out how you set up the project and GCP, and then you learn just how to deploy it and how to actually write app scripts in Google, it's no different than writing just some JavaScript. You're like, all right, cool. Go do it. And then you just have to watch timers and errors.

[00:23:07] **Tim:** Yeah, I mean, I feel like I kind of came late to the cloud because just the background, you know, 1990, 1999, I started working part time at the company I'm at now.

[00:23:16] **Tim:** And, you know, we basically were pretty much a data center, right? We had T1 lines coming in and we were had servers. And that was really my first job was just, you know, managing the servers. And, and so people would kind of like, you know, ban, they would like buy. Compute resources. And so we were sort of that provider.

[00:23:35] **Tim:** So if I ever wanted to do anything, I wasn't going to, it was free for me to like throw something on one of our machines. Right. So it made no sense, but really wasn't until probably eight years ago, I started using AWS and initially just using like the EC2 and EC2, in my opinion, it's kind of like the same thing.

[00:23:53] **Tim:** It's like you, you stand up a machine, provision it, and you, you, you basically are just using their internet and they're, they're taking care of backups and things like that. It's really not even fully managed hosting, but it was cheap, right? So, uh, that was sort of my first thing. And, you know, we started using other services as well.

[00:24:11] **Tim:** Uh, but yeah, that was, that'd be my first one was kind of like using EC2 on, on AWS.

[00:24:16] **Carol:** And what, what did you say EC2 was? Cause I don't even know what that is. It's

[00:24:20] **Adam:** Elastic Compute Cloud. Yeah. So whenever, whenever there's a number... I don't know shorthand anything. Yeah. In an AWS service, whenever there's a number, it usually means that they're...

[00:24:30] **Adam:** Uh, repeating the letter before it. So S3 is the simple storage service. I

[00:24:36] **Tim:** did not know that. I always wonder what the two was. Okay.

[00:24:39] **Adam:** Yeah. Elastic compute

[00:24:40] **Ben:** cloud. You know, actually pre managed hosting. I had a, uh, GeoCities page. I know, I know. What was it? The Church of Dew? What was it?

[00:24:52] **Adam:** And that was on AOL, but yeah,

[00:24:54] **Ben:** in a way GeoCities is kind of like cloud in that it was just an FTP folder.

[00:25:00] **Ben:** I didn't know anything about the infrastructure. I don't know how it was maintained or kept online. I just had a file system. I mean, you know, I pushed. You

[00:25:08] **Adam:** literally just

[00:25:08] **Carol:** dropped in

[00:25:09] **Adam:** and that's it. Yeah.

[00:25:11] **Tim:** Well, if you, if you're going to consider, yeah, I had a little website on AWL as well, FTP things up there and all the flashing blinking things going across the screen.

[00:25:20] **Adam:** Seven under construction gifts. Yeah, exactly. Yep. So yeah, I mean, I had a GeoCities too. I remember in high school. And I put up a website. I don't have no idea what was on it, but, uh, I remember like printing up a sheet of paper that had the URL, you know, it's like, you know, 150 characters long, geocities.com/ whatever neighborhood slash your username, whatever. It's so easy. Just type it. What's a tilde? And, um, and I would like cut out the strips of the paper so that I'd had like individual little strips and I would pass those out to people.

[00:25:56] **Carol:** Okay, Ben, it's confirmed. If you sit with us, you're definitely at the nerd table.

[00:26:02] **Adam:** I had totally forgot about that until you mentioned it, Ben. That's awesome. Nice. So the thing I had in mind when I was thinking about my first, you know, semi cloud experience, probably around the time that I was in college, I was using, I was just trying to get into blogging and I was unhappy with things like Blogger.

[00:26:25] **Adam:** And WordPress, you know, you could get free hosting for like PHP stuff or, or HTML, like Geocity sort of thing, FTP it in. But I wanted, and I was at the time getting into ColdFusion and I really wanted to do CFML code. So I started looking and I found shared hosting for CFML. It was like five bucks a month and support was basically non existent.

[00:26:48] **Adam:** There was an email address, but I don't think they even bothered to check it. And you know, and it was terribly slow. And all, it was all sandbox. You couldn't run into the, any of the interesting tags and it was awful, but you know, that was like my sort of my first experience. And then from that, from that bad experience, what I ended up doing was like the very first ColdFusion conference that I went to.

[00:27:11] **Adam:** The, the nerd table that I sat at at lunch, I talked to a bunch of those people and I complained about this and we decided we were going to form like our own little co op and we pulled our money together and we bought a VPS and had just a Windows server with like SQL Express on it and ColdFusion. One guy donated his ColdFusion license and, and we, uh, we shared the server and so everybody had FTP access and RDP and there's just like the six of us or whatever on there.

[00:27:37] **Adam:** It was so much faster, so much better. That's

[00:27:40] **Carol:** one thing I love about this community, about the CF community. Those people, the people are just awesome. Yeah,

[00:27:46] **Adam:** it's a lot of fun. And, and then thinking about like, when, when did I really get into something I would put, you know, I would take away the quotes, real cloud computing?

[00:27:56] **Adam:** Probably not until my current job. So I think I started here in 2003. No, sorry, that's way too early.

[00:28:06] **Carol:** Appscripts have only been around 12

[00:28:08] **Adam:** years, so. Well, yeah, I mean it would have been after my youngest, or after my oldest was born, so probably like 2009, 2010 ish. Um, anyway. Yeah, I mean, we, you know, we were putting together these products and we knew we needed to be able to sort of scale on demand, add additional servers and section everybody off, uh, into isolation.

[00:28:29] **Adam:** So, uh, that's kind of when we made that pivot from. Buying a, you know, buying a server and having this be our server. And yes, it's managed server, but it's still our, our one little thing. As we pivoted that from that to like Tim, I think it was Tim saying doing like EC2. Yeah. And that was our first foray into the cloud.

[00:28:51] **Adam:** And then from there we started to branch out and to like use different services for different

[00:28:55] **Carol:** things. Yeah, we use a lot at work, but my first like big work has been this project I started on. Yeah. Like, you know, that's been my first big actual start a project in the cloud. Begin there, not moving anything.

[00:29:08] **Carol:** So, yeah, that's only 12 weeks ago.

[00:29:12] **Adam:** Goodness. So. Everybody okay to move on? Yeah,

[00:29:15] **Ben:** I would say also maybe one other thing that we haven't touched on necessarily. So not only is there the concept of things being managed for you and paying for what you use, but now in the last few years, there's been a lot of push towards moving actual processing out closer to customers through CDNs where CDNs have historically been just.

[00:29:38] **Ben:** Content delivery networks, but now they're also becoming sort of edge processing where you can have now workers like processors in points of presence close to users that actually can intercept and do a lot of processing for you without ever having to go back to your origins. I haven't really done much of that myself at all, but I know that's, that's becoming more of a thing.

[00:30:00] **Ben:** And I know, I know people are trying to figure out how to best leverage that these

[00:30:03] **Carol:** days. Is that where like regions come into play? Like in AWS? Kind

[00:30:07] **Adam:** of,

[00:30:08] **Carol:** I don't know. So like we have things executing like in the, like Oregon region and then those things take a little longer for me to process than it does for people.

[00:30:19] **Adam:** Yeah, it can, it can, uh, how do I want to say this? It can serve sort of both purposes, right? So if it's closer to you, you're going to get faster responses, you know, lower latency sort of thing. But that, that's not exactly what Ben was saying. Okay. This was, you know, you can sort of have both at the same time.

[00:30:38] **Adam:** Okay.

[00:30:39] **Carol:** Just trying to better understand.

[00:30:40] **Adam:** Yeah. It's

[00:30:40] **Ben:** all just getting so crazy. And

[00:30:42] **Tim:** I think that was sort of the origin of this whole topic, right? That someone, uh, one of our patrons was. Complaining about just how many services there

[00:30:50] **Adam:** are, you know? Yeah. Like even just within AWS, didn't I see that you looked it up, Tim?

[00:30:55] **Adam:** There's something like. 192. Yeah.

[00:30:58] **Tim:** Yeah. 192. And, and it's like, I, I'm looking at my management console here, uh, online. And really the, my recently visited, so 192 out of all of 'em, I'm using eight. I use Amazon Poly, which is the, uh, text, text to voice service where you, or Yeah. We can create, uh, type in something and it comes out with very nice natural sounding voice, uh, e C two, which talk about, you know, it's kind of like, Basically, you have a machine there on their premise, S3, their storage, uh, RDS.

[00:31:30] **Tim:** We have a Postgres, several PostgresSQL databases up there that we use route 53, which is their, which is their host domain names and stuff.

[00:31:40] **Adam:** I'm pretty sure that's one of the only ones that has numbers in it that the numbers aren't significant about the. YouTube

[00:31:46] **Tim:** ISTP why, but I feel like that is a lot more trendy.

[00:31:49] **Tim:** I don't care what you're going to do to it. I agree with that. I don't think there's anything I can do about it. And I think it's smart not toPR and, it's better to PR it.

[00:32:04] **Tim:** And I look boring? Do

[00:32:15] **Tim:** I look cool? though. Doing things with satellites and like Amazon Managed Blockchain. So much stuff. It's a lot.

[00:32:20] **Carol:** And you said you only use a couple, but I feel like you named so many.

[00:32:23] **Adam:** Well, eight.

[00:32:24] **Tim:** I mean, yeah. And that's his thing. I mean, there's a whole lot of like these little, I guess, kind of like microservice kind of thing,

[00:32:31] **Carol:** right?

[00:32:31] **Carol:** Yeah, I have, I have 14 favorited that I use often enough. So I have 14

[00:32:35] **Adam:** favorited. Well, there you go.

[00:32:36] **Tim:** You're

[00:32:37] **Ben:** doing good. It's basically S3. Yeah, that's where I'm at right now. That's my level of cloud. So do

[00:32:44] **Carol:** you query, do you query S3? Will you query S3 web? We

[00:32:48] **Ben:** basically just use it as a, the object store using the Java client through ColdFusion.

[00:32:54] **Ben:** So I'm. Pushing to and pulling things down. I mean, Invision as a company, we use a lot more cloud than, than just that, but that's kind of my area of interaction. But as you know, on a, on a previous episode, a couple months ago, maybe I was saying that. One of the things that terrifies me about AWS is the IAM rules and permissions and who can do what.

[00:33:18] **Ben:** so scary. And not only that, just the other day, we had a system where thumbnailing, image thumbnailing just completely stopped working. And it turned out it was because someone had changed some permission setting on the SQS, the Simple Queue Service, which is how we queue up the thumbnailing jobs. And, uh, and like that was done by people who their whole job is managing the infrastructure, right?

[00:33:41] **Ben:** So like, like it's hard for them too. So, so I, and that's where I get very intimidated because. There are so many things that I see in the cloud amongst the Amazon services and other things where it feels like there's a lot of potential there. And I can, like, I feel it in my gut, but I don't necessarily know how to picture it in my head.

[00:34:03] **Ben:** And there's an overhead to the orchestration of all the systems working in harmony. And that's where I always feel like. I'm not going to have that skillset or it's going to just be too much of my time. And that's not really what I, you know, where my value is best added in terms of like what I do on a day to day basis.

[00:34:21] **Ben:** So that's, it, it, it scares me a little bit. You know, part of it is FOMO, part of it is imposter syndrome. Part of it is, is like just prioritization. There's a lot, there's a lot going on in those emotions. Yeah. Your heart matters.

[00:34:37] **Carol:** Reminder. No, I was gonna say one thing we do at work. We have a Slack channel.

[00:34:42] **Carol:** So we have like our DevOps Slack channel. So we can go post in there, but we also have a channel called serverless. So whenever we get hit with like some error or something going on, we'll just throw it in that that serverless channel. And usually pretty quickly, someone's like, oh, here's the right person to go ask about why this permission isn't working and.

[00:35:01] **Carol:** That gets you routed a lot quicker because if I have to sit and just search, I'm kind of going, I don't know what's happening here. I don't understand. And they're like, Oh, you just aren't even on the right role to have access to that. So you have to go assume this other role now. And in your template, you gotta make sure you've got the right roles assigned to everything for permissions.

[00:35:18] **Adam:** Is that because you're using Sam's stuff or? Wasn't just because , it sounded, uh, at first, like you were talking about if you have any issue with a aws, you put it in server list. Oh, I was like, huh? No, no, no.

[00:35:30] **Carol:** Serverless is just when something's going on with like your Sams stack. Okay. So we have, we've dedicated places to get help internally.

[00:35:37] **Adam:** Cool. So, I mean, I guess the sort of the last chapter that I had in mind for this topic was, uh, you know, when and why would you choose cloud stuff over non cloud stuff? And I think for me, having been in it long enough now and being familiar with it and familiar with the pricing model, And that takes a lot of the hesitation, the fear out of the basic stuff, like knowing I can get an EC2 for cheap and I can do Lambda for cheap.

[00:36:05] **Adam:** Um, I'm much more willing to, if I was going to start from scratch and, you know, on a personal thing, I would certainly start with cloud because it's just, it, especially when you're doing something that's not being used constantly, it's a lot cheaper to just pay for what you're actually using. So that's, you know, I would start from square one on something cloud.

[00:36:27] **Adam:** Um, what about you guys? You

[00:36:29] **Carol:** know, I agree. Having something hosted yourself is expensive. Plus, you have to consider all of the maintenance of it. You have to consider the security around it. You have to consider the backups, the disaster recovery. You know, what happens if your house floods and you've got your server sitting in your closet?

[00:36:45] **Carol:** You don't have to worry about that if you have it, you know. And I'm talking about someone starting out, obviously, right? Sure. So, I mean, you, you would have that out there. You would just log in from Wherever you have power at and you're back online, like, it never went offline for everyone else.

[00:36:59] **Ben:** I was just going to say that to piggyback on what you mentioned about security there, I would almost make it, uh, one of the things that's very attractive about cloud is that you can create better isolation, which allows you to do things that could otherwise be dangerous.

[00:37:14] **Ben:** And, and when I say dangerous, I don't mean something nefarious necessarily, although I think you, you do benefit from the isolation there, but, but dangerous can mean. Doing something that might take up all of your CPU processing, right? Yeah, like all of a sudden something can eat up your entire RAM allocation.

[00:37:32] **Ben:** So one of the first places that we used cloud architecture at work is for image processing, where, you know, someone might upload something that all of a sudden requires 12 gigabytes of RAM to resize. And if you're doing that on a machine, that's also running your application server, you know, things could become unresponsive.

[00:37:51] **Ben:** Also with cloud, a lot of times you can just let things crash and it's not a problem because then they'll just spin up again. Yeah. There is a lot of security there in terms of durability

[00:38:04] **Tim:** and

[00:38:05] **Adam:** protection. I didn't even think about that.

[00:38:06] **Tim:** I think durability is probably better than security. Cause I do think that is some people think that, you know, they put it in the cloud, that it's, it's more secure.

[00:38:14] **Tim:** Not necessarily like if you are just running an EC2 instance or whatever the equivalent is and the other ones, and you're not. You know, you're not doing best practices on it, it can still get hacked. It's going to be, it's going to be limited to your machine, but it doesn't mean you're safe just because you're in the

[00:38:30] **Adam:** cloud.

[00:38:30] **Adam:** It's still

[00:38:30] **Carol:** your code running.

[00:38:32] **Adam:** Yeah. That's my biggest fear is that, you know, we've got all this stuff. We've got a VPC in AWS.

[00:38:41] **Adam:** And, uh, you know, all of our stuff is in there. And so if we have one thing misconfigured, somebody gets a way in and then they're in, and maybe they can find a way to escalate out to some other box and, you know, get access to all kinds of crazy stuff, change our IAM settings and lock us out and start mining Bitcoin.

[00:38:59] **Adam:** I, you know, who knows what I'm just, I'm, that's my, that's the thing that I lose sleep over. Is everything secure? And I think you

[00:39:06] **Tim:** talk about when is it time to move stuff. So, I mean, platforms like AWS, and I'm speaking about AWS because that's the one I'm most familiar with. We do have stuff in Azure, but I really don't touch it.

[00:39:15] **Tim:** I mean, they have so many different services that are more than just.

[00:39:24] **Tim:** So, you know, I'm not going to write my own text to speech or even install like some Java program that does it. It's like, it's an API that I can call and I can send it some text and it comes back with perfectly fluent Spanish, you know. Other things that they have like the media services where they can like, I used to try to like encode like big videos and stuff that, you know, the elastic transcoder, you can just just send up something up there and it will do it for you on their CPU much faster and quicker and send it back to you than you could do it yourself.

[00:39:55] **Tim:** They do so many things for you that it's worth it to, if you're deciding to build something, first look and say, all right, does whoever I'm using, whether it be Azure or Google or, or AWS, do they already have something like this already that I can take advantage of? Because it just makes sense to not reinvent the wheel.

[00:40:14] **Tim:** Chatbot, AWS chatbot. I mean, write your own chatbot. They have a chatbot. It's really good. Along

[00:40:20] **Ben:** those lines, I, I sometimes hear people talk about the worry of vendor lock in where the more services you start to use, say for example, from Amazon, the more bought in you are to the whole Amazon infrastructure.

[00:40:34] **Ben:** And then you couldn't say, Take your system and lift it over and shift it to Google cloud or Azure. Um, but the, the counter argument that I always hear to that is, so what? Like add value to your customers, add value to your business. Don't worry so much about that. It's the same as like, why use a specialized database or why use a, you know, a, a flavor of SQL that has advantages, like people will have.

[00:41:02] **Ben:** You're pre optimizing. People have vendor lock in all over the place. Don't worry about it from

[00:41:06] **Adam:** an infrastructure

[00:41:07] **Carol:** level. No matter what you use, if you're going to change, you're going to make changes. So.

[00:41:11] **Adam:** And,

[00:41:11] **Ben:** and nothing's ever easy to migrate anywhere.

[00:41:14] **Adam:** So, correct me if I'm wrong, but isn't that sort of the, the, uh, the value proposition of Kubernetes?

[00:41:21] **Adam:** That, you know, you, you configure your infrastructure as code with Kubernetes to say, you know, that we want this many clusters of this sort of thing. And it's a cluster is these, this, you know, X of three of X server and three cache servers and two web servers and whatever. And, and it goes into spins all that up on, you know, GCP or Azure or AWS, whatever you happen to be using and controls it for you.

[00:41:45] **Adam:** I was going

[00:41:46] **Carol:** to say, I think the vendor lock side of that isn't so much where it's spinning it up. I think it's more of like the services side. So it's like, I'm using, you know, the Comprehend for my natural language processor. And if I have to switch off to another one, then now I'm going to have to go figure

[00:42:00] **Adam:** out how to I mean, they're going to have different APIs that you're going to have to update to.

[00:42:04] **Adam:** And possibly different code. Well,

[00:42:05] **Ben:** and it's, it's not just the APIs though. I think it's the integration that the services have. So, so like last week or the week before when I was talking about Brian Klass doing his presentation, and I was joking around about how overwhelming it felt. To have a simple notification service posts, a simple queue service, which was then like automatically piped into, uh, something Firehose like Kinesis Firehose, which was then piped into S3 automatically, which was then queryable through Amazon Athena.

[00:42:36] **Ben:** I, and I think a lot of that sort of just happens. Like you just configure it and it just works. I mean, I don't know how to do any

[00:42:42] **Adam:** of it. It's

[00:42:43] **Tim:** funny you mentioned Brian. I actually sent him a message to see if maybe we could have him as a guest come on the show and like school us on all this. He's so far ahead of us on this kind

[00:42:53] **Adam:** of stuff.

[00:42:54] **Adam:** He's awesome. So we talked a little bit about the benefits here. What are some of the drawbacks of working in the cloud rather than not being in the cloud? And I think that the first one is probably pretty obvious. It's the learning curve, right? Oh, yeah. There's so much to learn when you're first getting started.

[00:43:09] **Adam:** Yeah.

[00:43:10] **Carol:** And the documentation isn't always well maintained.

[00:43:15] **Adam:** There's lots of documentation.

[00:43:16] **Tim:** It's, yeah, it's not always the most up to date. I think we mentioned that before. It's like, man, I'm struggling with a problem. And it's like, I find something like this is exactly my problem. And you look at it, it's like three years old and they've completely

[00:43:28] **Adam:** changed.

[00:43:29] **Adam:** Even if it's up to date, half the time, it feels like it's just, it's missing stuff. It doesn't cover my particular use case. There was all 11 other use cases, just not mine.

[00:43:39] **Carol:** Example, um, we're using S3 for storage of all of the emails that are coming in to basically go through, send them over to Comprehend.

[00:43:47] **Carol:** Then we just want to go come back, get the entities out of it. Anyways, I was just doing a list on it and it's like the list objects B2 is, I think, what it is through S3. And I'm like, man, I think my, like, I think this Lambda is timing out. It's running out of memory. Something's going on with this thing because no matter what I did, this one inbox would not pull a single message after the 22nd and I'm like, why does it stop on the 22nd after digging through it, digging through it?

[00:44:12] **Carol:** I'm like, I don't know. My lead developer comes back from vacation Monday. He's like, yeah, when's it doing it? I'm like on the 22nd for this one box every time. He's like, Oh, I think the documentation somewhere mentioned it only will pull 1, 000 keys at a time. Then you have to send back through the next like continuation token.

[00:44:31] **Carol:** I was like, it's literally one sentence in the documentation that says continuation token will be sent back if isTruncated is true. And you don't know what the isTruncated is. I'm like. How was I supposed to know that from like a sentence? Like, give me more information. Like, how would you use this? Like, where is this coming?

[00:44:49] **Carol:** Like, what do you do with it? Not just a sentence. Like, I just feel like it's missing. I was like, seriously? So then you had to go pull it with the continuation token. Then I got all of the days back after that.

[00:45:01] **Adam:** Nice. Another drawback that I was thinking of is that it's real easy to I mean, it can be a little too easy to set up extra stuff and to not realize what you've got going.

[00:45:11] **Adam:** And all of a sudden you, you know, you're, you're chugging along and you think you run in just like one little EC2 server and some S3 stuff. And then you get a bill for 5, 000 at the end of the month and you're like, Oh no. You're like, who

[00:45:22] **Carol:** turned on X Ray?

[00:45:24] **Adam:** Yeah, so we,

[00:45:25] **Tim:** so it wasn't our company, but a sister company of ours that, uh, they, I mean, they're, they're, you gotta be smart about how you deploy stuff to a cloud service because yeah, you can want, you can run up a really big bill really, really fast if you don't know what you're doing.

[00:45:41] **Tim:** And I, I think they just kind of said, we're moving to the cloud and they just, they just basically took all their boxes, copied them and put them on EC2, super extra large instances, maxed out the memory, maxed out the drives. And, and yeah, they were paying huge amounts of money, um, for it and they really, a lot more than they ever needed.

[00:46:00] **Tim:** Uh, our EC2, I have got 24 EC2 instances, I pay 500 bucks a month. How many? For, for the five, 24. That feels pretty good. 24 instances, I pay 500 bucks a month. That feels nice. For just EC, I mean, there's other services, the RDS, I mean, the total bill adds up a little bit, but it's, I mean, 500 bucks for 24 servers.

[00:46:19] **Tim:** It's not bad. That's good. But I mean, most of them are small. I mean, our applications that we build, they're microservices, right? I can run most of them on a small instance, some of them on micro. So, yeah, so it stays pretty cheap. So you have to be very smart about how you're deploying stuff and what, you know.

[00:46:38] **Tim:** The knee-jerk reaction sometimes is, oh, this service is running slow. We'll just make it extra large. Well, maybe they'll

[00:46:46] **Adam:** figure, figure out what else doing on

[00:46:47] **Tim:** it might, you know, might solve the problem. But that's a long-term bill. Mm-hmm. , you, you do that now you're paying for that for the rest of the life of the product.

[00:46:53] **Tim:** So maybe figure out what the problem is for before you decide that upgrading your, your service is the, is the answer. Yeah.

[00:47:00] **Adam:** I mean, also that's kind of a benefit too, is that you can change that, right? So if you buy hardware, Then throw it in your data center somewhere. That's the hardware you've got. You can sell it.

[00:47:08] **Adam:** You can buy new hardware. But if you don't like the size of the instance that you bought from AWS, you just stop using that one and start using a different one. You can resize it without even like some of them, some services you can resize without even turning them off. I think EC2, you have to like shut the machine down.

[00:47:24] **Adam:** Yeah. But still. You know, we're talking two minutes of work. When

[00:47:28] **Carol:** Lambdas, they have a pretty good interface. Like you literally can log into the interface and just go. I want to increase memory. Just go to the configuration tab, give it more minutes. That's it. I mean. You don't have to do the interface, obviously, you can do it all in code, but I like that I can do it there because then I also can, in the right hand corner, say export my SAM stack, and I can get an understanding of how to build the template then.

[00:47:48] **Carol:** Nice. I'm like, oh, these are the changes that you need. Got

[00:47:50] **Adam:** it. Understand. I do wish that on Lambda, they would separate CPU power from memory. Because there are times that I need lots of CPU, but I don't need a ton of memory. And nope, you just get

[00:48:00] **Carol:** time.

[00:48:01] **Adam:** And yeah, the more memory you assign, the more CPU power you get.

[00:48:05] **Adam:** Nope,

[00:48:06] **Ben:** not splittable. I think that, uh, there's a certain degree of complexity and then, you know, obviously this kind of dovetails with learning curves and just general skill sets and experience. The more services you have, just general operational complexity and mental model of how you think about a system increases.

[00:48:28] **Ben:** I mean, that's not necessarily cloud specific. If you had all of your own hosted services, you'd still have all that operational complexity. But because, as Tim pointed out, cloud makes things easier and you can just start spinning stuff up and emitting events and piping things into other things. It's, it's, it's easier to maybe get running, but it's just, there's a lot of complexity there and there's a lot of hidden, hidden things.

[00:48:54] **Ben:** Like I know at work we'll have an incident where something's breaking and it takes us a little while sometimes to figure out what's breaking and where that issue is. And cause you know, you'll have something that's symptomatic, but that's really symptomatic because something upstream from the request is actually breaking and there's a cascading failure and things get complex.

[00:49:15] **Tim:** Yeah. And so sometimes like Amazon will send me alerts to say that, you know, by this date, they're going to do this thing. They're going to update something or like I can't, I can maybe do it earlier, but I, you know, I can't postpone it. So I can't stop it. They're going, they're going to update that thing regardless of what it does.

[00:49:34] **Tim:** And typically it tends to not be nefarious or destructive of the process, but it's like, I always worry. I'm like, I watched that date and sometimes I'll just go ahead and run, you know, I can run it myself. You know, while I'm awake, I don't want to break while I'm sleeping and wake up to a mess in the morning.

[00:49:50] **Tim:** But yeah, you don't have control over, over some things and it's all about trust, right? So it's like you're trusting that Amazon and Microsoft and Google, that they are going to be up and running. And sure, I mean, they're big companies and they're probably are going to be up and running, but you know, there are cases where they do go down and you, you have no control over that.

[00:50:11] **Tim:** Honestly.

[00:50:12] **Adam:** I use that to my advantage. So I have a, a side business with just one customer. And occasionally, like when Amazon goes down, if, if, uh, not S three, but if E C two goes down in like one region, then they go offline and you know what? So does the other half of the internet snow day. Right. And I'm like, it's not, it's not just me that's down.

[00:50:33] **Adam:** Sorry. It's, it's Twitter and Facebook and Yeah. Everybody's down. Hold your horses. We'll be back. Yeah.

[00:50:39] **Carol:** Whereas if you're hosting it, you're like, man, not going to explain this. Yeah.

[00:50:43] **Adam:** Yeah. Then you got to reach out to that support email and hope that they answer. What

[00:50:47] **Tim:** was that service that went down not too long ago that pretty much took like a quarter

[00:50:50] **Adam:** of the internet down?

[00:50:51] **Adam:** Cloudflare. Cloudflare. Cloudflare. Yeah. Yeah. Yeah. You

[00:50:54] **Carol:** didn't realize how much it was backing until it went down. Mm hmm. Mm hmm. Discord was out.

[00:51:00] **Adam:** But I mean, overall, I

[00:51:01] **Tim:** think it's positive because I mean, they do a lot of things for you. They offer a lot of things. I agree. And the pricing is. You know, very affordable, reasonable because it's, it's, it's pay as you use for the most case.

[00:51:13] **Tim:** Right. So you don't use it. You don't pay for it. And you can

[00:51:15] **Adam:** also do like bulk discounts. Right. So if, you know, I'm going to be using the CC2 server and I'm not going to need to upsize it for the next three years, you can pay for three years in advance. And it works out to be like the cost of paying monthly for two years, something like that.

[00:51:30] **Adam:** Now you are stuck with that. I mean, you've, you've prepaid that and there's no refund, right? So you can, you can, um, they have a service actually for people who have done this and then decide they don't want it. You can like sell your remaining lease, basically. Oh, that's actually cool too.

[00:51:45] **Carol:** I get to sublet my service.

[00:51:47] **Adam:** I need to do that

[00:51:48] **Tim:** though. Cause yeah, so you, you know, you're, you started spending enough money with him when all of a sudden you get a call and you get a sign in an account manager, but they count me. All they really want to do is sell me other stuff. And I'm like, really, I'm not interested. I just want you to save me some money.

[00:52:02] **Tim:** And they're like, Oh yeah, we'll save you some money. The whole time. They're just trying to push other services. They're trying to, they want to do, they want to do a discovery call where they can discover what else are you doing that we didn't tell you? Like, look, and. Whenever I need to build it, I'll use you.

[00:52:14] **Tim:** Don't worry about it. Just, just

[00:52:15] **Adam:** tell me how I can save some money. We don't have 17 and a half services on AWS and one on GCP. Like if we need something new, we're going to build it on AWS. You just hold

[00:52:24] **Ben:** your horses. But talking about building something historically, I've heard the phrase, do it until it hurts.

[00:52:31] **Ben:** Meaning that like you do the worst case scenario, not worst case. It's like you do the minimum vial product. Until it hurts to do it that way. And then you evolve it to be a better solution. And you kind of just keep iterating on that. And I wonder if the advent of cloud and the, and the ease with which people can spin up a lot of different types of services has sort of changed the way that people think about application architecture over time, meaning like day one, I could create one box and that box runs.

[00:53:05] **Ben:** The database server and the application server and say like stores files locally or stores files to elastic block storage or something, or on day one, I could spin up, you know, a managed RDS and write to DynamoDB and write to Amazon S3 and do a whole bunch of stuff, which, you know, probably would be more durable and have better performance and other characteristics that were attractive.

[00:53:32] **Ben:** But is that really what I wanted to be doing on day one or. Is, is there, are we getting away from sort of a minimum viable product? Mindset. I'm not saying that's bad. I'm just wondering if that's changing the way people think about building stuff and evolving products.

[00:53:46] **Adam:** I'm sure that it is changing the way that people think about it.

[00:53:49] **Adam:** I'm sure some for the better and some for the worse. I'm sure there's a lot of, uh, it's got to be web scale on day one people out there, but at the same time, I mean, a

[00:54:00] **Tim:** lot of the services that they offer kind of, it just makes it not, you don't, you don't have to build it yourself. Right. So it really, you're just going to leverage.

[00:54:07] **Tim:** Whatever tool that they have there already. And so you don't have to worry about that part so you can focus on what is it that you are, you are really building that you're cobbling together the, these other tools that are coming from these, these cloud services. So I, I think it actually gives you more to your, to your M V P.

[00:54:24] **Tim:** 'cause like, there's sections of it that I don't have to worry if is machine learning part of your project? Mm-hmm. , I don't have to worry about that. There's, you know, I have to integrate with it, but I don't have to really worry about that. I could just tie into what's already there in, in

[00:54:38] **Adam:** the ecosystem.

[00:54:39] **Carol:** Yeah. Like I already know it's gonna play well together. I don't have to mm-hmm. Vet that out.

[00:54:43] **Adam:** Yeah.

[00:54:43] **Ben:** I, I, I see what you're saying. Maybe I'm, I'm, I'm more, I worry sometimes about people building solutions that are robust before the need has been proven. Like, one example that pops in my mind is that, imagine I had to do a search on a data table.

[00:54:59] **Ben:** You know, SQL has had text matching since the beginning of time, you know, which is limited in what it can do and it's limited in performance characteristics, or I could spin up some sort of elastic search server and deal with that kind of an API. And that would probably be maybe better performance and maybe better results.

[00:55:22] **Ben:** But it's also now another service that I have to pay for and potentially manage. And like, would it be better on day one to just try throwing it in a relational database table and try running like on it and, or do some sort of other fuzzy text matching and like, and like just call it a day versus spending a whole bunch of time learning about.

[00:55:42] **Ben:** Yeah. That kind of stuff. I, I don't know. So I, I just wonder if, I mean, kids, kids these

[00:55:46] **Carol:** days will never understand it. ,

[00:55:48] **Adam:** I

[00:55:48] **Tim:** mean, Ben, when you put it like that, I, yeah, I get what you're saying. Yeah. Me, I would, yeah. I would just do a like statement. It's, it's quick and dirty. I don't need to go hoisting a whole new service, but for an M V P.

[00:55:59] **Tim:** Right. But maybe that you're working on, but I see it later down the road, you're gonna refactor that and maybe use some other service. We talked, we, we talked about this earlier, not pre-op optimizing too early. Right? Or ever. Don't pre optimize, just wait

[00:56:10] **Adam:** until you need it. Premature optimization. That's what you're looking for.

[00:56:12] **Adam:** There you go. Okay. I think we covered this pretty well. Yeah. I love the cloud. I can't think of anything else I want to say about the cloud. I mean, we, I think we did a pretty good job covering the benefits and the drawbacks. Uh, I just want to look at what

[00:56:23] **Tim:** else, uh, our Patreon said, how do you say, I get lost in the naming of all these services.

[00:56:29] **Tim:** Yep. But even before that, I just don't know why anyone would even start to think about using it. If it mostly because our stuff just runs fine, our traditional stuff. It's not like I really need a billion services to run a web app. Maybe explaining why, when and why you moved the services would be, yeah, I think we'd cover that.

[00:56:44] **Tim:** Yeah. Sounds

[00:56:45] **Adam:** great. Yeah. I mean, if, if you're outgrowing your server, then it's time to do something else. If you need more dependability, was that, or durability was the word that had been used. For probably the same price that you're paying for a physical server in a data center somewhere, you can have a virtual server, or a couple of virtual servers, in a couple of different availability zones, running your application and load balance between the two, or even just like a failover scenario.

[00:57:12] **Adam:** So that if one of them were to go offline, then the other one kicks in.

[00:57:17] **Tim:** I will say this. So he, he talked about, you know, why would you move it there? One of the pains that, that you, cause we do have a lot of on prem, on premise hosting that we do ourselves. And some of it, we can't really ever move that the pricing on a PCI environment in the cloud is just, it's too far out of reach.

[00:57:36] **Tim:** Yeah. It's pretty out. Yeah. So that's like, so you, you buy equipment and you. The assumption is it's going to have a five year lifespan. And so you depreciate out that cost of all that for over five years for your books. But it's like, Whenever you reach that point where you decide you need to upgrade your routers and your firewalls and your servers, there is a period of pain there that you go through, going through, changing out that hardware.

[00:58:03] **Tim:** None of that applies when you're dealing with the cloud. I agree. All that is done magically behind the scenes. They are upgrading their hardware constantly. It's completely transparent to you. It does

[00:58:16] **Adam:** still occasionally happen. They'll be like, you're still on the old hardware and we just need you to reset your box and when it comes back up, it'll be on the new stuff.

[00:58:24] **Adam:** That's pretty painless though. I mean, yeah.

[00:58:26] **Carol:** That's not, Oh, I need to go offline and replace the entire switch in my data center. It's been my Saturday doing it.

[00:58:34] **Ben:** Well,

[00:58:34] **Adam:** I configured

[00:58:35] **Tim:** the firewall wrong and the NAT wasn't hitting ICP correctly. So, uh, sorry about the 24 hours of downtime. While

[00:58:45] **Carol:** I smoke,

[00:58:48] **Ben:** I'm going to

[00:58:48] **Tim:** clip my ponytail.

[00:58:52] **Adam:** Wow. Remind I

[00:58:58] **Adam:** think it's time to bring it home. You guys agree? Y'all let's bring it in. All right. So we have, and this is probably very relevant to say, we have never taken any money from any companies to say nice things about them, including AWS, GCP, Azure, anybody. And to be honest, we prefer to keep it that way. And we can only do that because of the support of listeners like you.

[00:59:17] **Adam:** So if you like what we're creating here, you might want to consider supporting us on Patreon at patreon.com/WorkingCodePod. In addition to the warm feeling that you get in your heart for helping us create something positive in this world, we also offer perks for our patrons. They get an invite to our discord server where we hang out and chat about the podcast and work stuff and life stuff.

[00:59:36] **Adam:** And we have other perks available like early access to new episodes and the after show. Every week we thank our top patrons, and since this week is part of every week, we're sending out a huge thank you to Peter and to Monte. Thank you guys very much. And hey, if Patreon isn't your thing, then thanks for listening anyway.

[00:59:52] **Adam:** We appreciate having you here with us. You could share the show with your friends and co workers because, let's be honest, almost nobody searches podcast directories, so we really need your word of mouth referrals to help keep us growing. And you can leave us a rating and review on iTunes or wherever you get your podcasts so that maybe one day we'll rank first when you search for the name of our podcast.

[01:00:10] **Adam:** Today's, uh, show topic was a listener suggestion and we want you to keep sending those in. So please send your questions and your show topics to us on Twitter or on Instagram at @WorkingCodePod, or you could leave us a message at 512-253-2633. That's 512-253-CODE. We'll catch you next week.

[01:00:27] **Adam:** And until then, remember

[01:00:28] **Tim:** guys, your heart, that the thing deep down inside you, that beats and keeps you living, keeps you feeling it matters.
