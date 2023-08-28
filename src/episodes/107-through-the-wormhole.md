---
title: "107: Through The Wormhole"
description: "Ben talks about the crippling attachment he has to his own fingers (and why he won't work with wood); Adam talks about how excited he is for the v1.0 release of Svelte Kit; and, Tim reflects on the blinding speed with which people seem to be to making science and technology breakthroughs."
date: 2022-12-28
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/107-through-the-wormhole/id1544142288?i=1000591481896"></iframe>

[Happy Festivus][festivus], dear listeners! Welcome to our last show of 2022! Closing out "No Effort December", we truly run the gamut this time: Ben talks about the crippling attachment he has to his own fingers (and why he won't work with wood); Adam talks about how excited he is for the v1.0 release of [Svelte Kit][svelte-kit]; and, Tim reflects on the blinding speed with which people seem to be to making science and technology breakthroughs - I mean, we're talking some serious Sci-Fi-level stuff here!

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[festivus]: https://www.youtube.com/watch?v=1njzgXSzA-A
[svelte-kit]: https://kit.svelte.dev/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/107-through-the-wormhole.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Tim:** So, I mean, they proved that you could travel through a wormhole. So, I mean, you think about that if, if that is true, if you could actually travel through a wormhole and a, and a wormhole is basically a black hole. So if that's true, uh, they, I mean they're, they're, they're similar. So yeah,

[00:00:14] **Ben:** It is

[00:00:14] **Ben:** bananas.

[00:00:15] **Tim:** nuts.

[00:00:16] **Adam:** yet, you know, DHL can't get a package from here to there in

## [00:00:42] Intro

[00:00:42] **Adam:** Okay, here we go. It is show number 107, and on today's show, we don't know, we're gonna get into it. Got some stuff. It's no effort. December, the train keeps rolling. but first as usual, we'll start with our chimes and fails. carol's out sick this week. So just the boys. Tim, why don't you go first?

[00:00:59] **Tim:** Yeah. No effort December, right? You, it's a 2023 problem coming up with topics.

[00:01:05] **Adam:** that's not a today problem.

[00:01:07] **Tim:** no, today that's a, not a today pro, a 2022 problem. It's a 2023 problem.

## [00:01:11] Tim's Triumph

[00:01:11] **Tim:** So I, I'm gonna go with the triumph just cuz you know, it's like, I'm trying to think of, something interesting, but it's, that's sort of a struggle cuz just stuff keeps working.

[00:01:21] **Tim:** You poor.

[00:01:22] **Tim:** I, I know. Yeah. To stay, you know, stuff keeps working. We we're building new stuff. There's new products coming out, and we'll see, you know, once, once some, some of these new products launch, maybe, maybe there'll be some excitement. But I just kinda feel like I need a little bit of a challenge. And I don't mean challenge in the sense of I want fire, I definitely do not wanna fire, I spent too many years in my career just being, being the firefighter and, and, and dealing with constant 24 7 panic. And, you know, I almost got kind of addicted to that honestly. That, that, that was the only way I could actually get up in the morning was knowing that something terrible is gonna happen today,

[00:01:57] **Tim:** And, and we, me and my team would have to fix it. and so it's like anytime I get, you know, like, man, it's kind of kind of quiet today, I, I, I slap myself on the wrist and go, it could be worse. So, but yeah, I need, I need a challenge and to come up with some sort of skunkworks type project or something to kind of keep my creative juices Yeah.

[00:02:17] **Tim:** I should play with I'm, but you know, I, I don't, front end does not get me, get me going. Front end does. Does seriously

[00:02:25] **Adam:** know, it's, it's funny, I used to be the same way. I, I remember, let's see, probably in like the early to mid two thousands, like 2008 to 2010, that was, that was my jam, right? I was like, I am so good at making server side pages that, that render forms and taking that data and putting it into databases.

[00:02:48] **Adam:** You know, I'm, I'm crud forms for life. That's my job. And God, that got so boring, so fast.

[00:02:55] **Ben:** Well, I'll tell you, I've become just recently fascinated with Hot wire. Have you guys heard of that? It's from the base camp guys.

[00:03:03] **Tim:** I heard about it from.

[00:03:04] **Ben:** So it, it, it's, it's basically my understanding, and I haven't really played with it at all yet, is, is it takes what you're talking about Adam, which is the traditional server request response building CRUD style pages, and then sort of Sprinkles, age ified interactions on top of it where it's still making the full page request behind the scenes via a act, but then it's plucking out just portions of the rendered page and then using that to dynamically update.

[00:03:31] **Ben:** I, it, it seems like, I mean, I, it doesn't solve every solution. It doesn't solve every problem, and they're very upfront about that, that this is for a particular type of web application. But, I don't know. I'm fascinated by the, by the kind of a nostalgia of, of the web apps of, of yester.

[00:03:51] **Adam:** I kind of wanna say, I'm pretty sure it was the 37 Signals, or I don't know if that's still the name that they go by, but that, that crew, pretty sure. The last thing that they did, that I actually like a hundred percent loved, was, they had around Christmas time, I think it was like Christmas time, 2020, they had a service where you could, I think, send them an email or something and it would like, it had a, a little machine, it would like print it out and go up a little treadmill and then into it a literal dumpster fire

[00:04:20] **Ben:** Oh my God, I remember that. That was fun.

[00:04:23] **Adam:** And it like was at a, a live webcam feed of it. So you could see your, your thing come through.

[00:04:28] **Tim:** Yeah, so that's, you know, I need a, I need a challenge. Maybe over Christmas break I'll be off a, we get off a week, so maybe I'll do a hackathon or something on some sort of technology I think is interesting to, to kind of play around. So,

[00:04:41] **Ben:** What if, what if you let your customers start paying with Bitcoin? Just throw, just throw that in there.

[00:04:46] **Tim:** Sure. Yeah. I, that actually is on our, our roadmap, not our, not our, yeah. Not our one year roadmap, but our five year roadmap. It, and you'll be, and the only reason I'll tell you, so the only reason is, so we get these RFPs, you know, requests for proposals and customers because we're in payments. They'll, they'll like, you know, what ways can you pay?

[00:05:05] **Tim:** And they, and I'm sure it's one of those things that it's just a checkbox, but it's like Bitcoin is on there. They wanna know, can, can we pay with Bitcoin? And so my, my goal is within five years, to have every, to be able to answer positively on every R F P on every single question. And that's one of them.

[00:05:23] **Tim:** So will people use it? Probably not, because there was a period of time where can you pay through Facebook? And I, I created this whole Facebook pay thing and it worked slick, it worked great. People, people signed up for it. No one ever used it. Not once they paid for it, they gave me a licensing fee, but they never once used it.

[00:05:41] **Tim:** And I'm like, so this, it's one of those checkbook things, right?

[00:05:43] **Ben:** Wait, is, is Facebook payments? Is that a thing that I don't know about?

[00:05:48] **Tim:** Well it, so it was, is not a payment method through Facebook, but it was, it was basically your inter you, you would do Messenger. It was basically an IVR over Messenger. So you would, you would chat with, with the digital assistant over, you would like go to this insurance company's Facebook page and, and, and Messenger pop up and say, would you like to, you know, look up your policy and you look up a policy and then you can make a payment.

[00:06:12] **Tim:** The payment would actually redirect you to another. Cuz you know, you can't put credit card data into Facebook cuz it's not PCI compliant. But, yeah, so it really wasn't like Facebook pay or like, like, like Apple Pay is a real thing, but Facebook, this was just a way to make a payment through Facebook because, you know, all the kids are on Facebook these days.

[00:06:29] **Tim:** Actually, no they're not. But, not anymore.

[00:06:31] **Adam:** nobody knows cuz it's a audio podcast. But I was over here making gross faces when you. Are talking about paying with Bitcoin. And it's funny because I'm the person who has the most institutional knowledge on our team about our payment stuff. Like I rewrote the entire PayFlow stuff to be able to support, configurable payment gateways, right?

[00:06:52] **Adam:** So we originally had one provider and then, we wanted to add support for Braintree. And I was like, okay, well getting from one to two is the hard part if you do it right, and then going from two to three to 10 to 12 is nothing if you've done it right. and so I did, I I spent a lot of time thinking about it and doing it right.

[00:07:08] **Adam:** And, and so like I know the guts of payment flow very well right now. And my personal position currently is if they tell me, if I'm told to implement, you know, decentralized whatever, cryptocurrency as a payment method, my answer's gonna be no. You can fire me or you can just accept a no. and, and you know, look, I, I'm not saying that opinion will never change, but that's my opinion of it right now.

[00:07:34] **Adam:** Like it's just, there's no good reason. The only good reason to implement it is to be able to say that you can support it so that some VP somewhere who has a bug up their butt about accepting Bitcoin is gonna meet a future. Like no

[00:07:48] **Tim:** I I don't disagree with you on that. I honestly don't.

[00:07:52] **Adam:** I'm sure there would be some people that would pay with it, but, it's not worth the effort in my opinion right now.

[00:08:00] **Ben:** It'd be really funny if, if someone actually implemented a, a barter based payment system where you could be like, ah, I can't pay them my invoice this month, but I got this bicycle. I'm not using anymore

[00:08:11] **Tim:** it's funny. So it's funny you say that we're, we're going off topic here in the very first triumph here, but so one of our earliest customers, earliest customers, this is like we were, they were customer even before I joined the company, and. 2000, was a company called Trade Bank, and I think they're still in business.

[00:08:28] **Tim:** And they, they were a barter company. So basically you could say if you were, like a, a local vet actually has their sticker on the door trade bank. if you had, if you offered any sort of service you could pay with trade bank dollars. And so what it was, so it's like say is a $200 vet visit, right?

[00:08:47] **Tim:** Well, you could pay them in, in trade bank. So like, I'm a web designer, I've done some work for someone and we, we swap in trade bank money . so you could basically just use this barter system, to do that. And, and it never really took off. I think it was kind of local to around the southeast area.

[00:09:03] **Tim:** but it, it was a brilliant scheme because trade bank could just print money. And I think that's kind of what did them in, they, they could just generate, you know, they could just generate their own dollars inside the system and they could go buy stuff and they would buy art and different things. And, and we, we were paid, our company, was paid in trade bank dollars.

[00:09:21] **Tim:** And so like at one point we had this huge reserve of like hundreds of thousands of dollars with the trade and we weren't doing it. So my boss is like, that's what he was taking his, his payments and that's how he was paying himself cuz he didn't have a salary. So he would like, you know, buy artwork and different things and just, and you know, and then resell it to pay his own

[00:09:41] **Adam:** to launder it into cash

[00:09:42] **Tim:** exactly. But yeah, it, it was, yeah, it was an interesting, interesting thing. But yeah, it would definitely be good to actually be the, the, The company that was the bank, cuz I mean, all it was was just generating numbers for them.

[00:09:56] **Adam:** Yeah. That was the first thing that I thought of. Like, okay, but where, what's the first trade and how does new value enter the system? Right? Like,

[00:10:04] **Ben:** Yeah, I thought, I thought you were gonna say it was like a pawn shop that had dollar credits where you could trade in, you know, a used bike or something and get a hundred dollars and what was, whatever the name of the company was.

[00:10:19] **Tim:** yeah. So yeah, if I did like $2,000 worth of web development for someone, you know, I would get $2,000 trade bank dollars, in exchange and just swap those around and pay for stuff. So it was interesting. All right. Enough about me, Adam, what you got?

## [00:10:33] Adam's Triumphs

[00:10:33] **Adam:** I think I'm gonna go with a couple of, mini triumphs here. So, the fence that, was and then wasn't now is again, back on the schedule to

[00:10:42] **Ben:** Nice. Nice.

[00:10:43] **Adam:** so it'll be happening I think in like a week or two,

[00:10:47] **Ben:** Were, were they able to reuse the, posts that they had already put in?

[00:10:51] **Adam:** that we haven't gotten that far yet with the, the new materials have arrived at the fencing company.

[00:10:57] **Ben:** Mm

[00:10:57] **Adam:** They don't keep it in stock, they had to order it. and so now they, now that they have it, they've put us on the schedule to come back out and redo the install. So what was, I guess, supposed to be a one day install job is now gonna be like a, a three quarter day de-install job and a three quarter day, install job or something like that, or one the install job.

[00:11:17] **Adam:** So, but it's happening, so, you know, we're moving forward. Thankfully. that's a mini thing. this is not at all my thing, but I'm taking, I'm calling it a triumph because I've been eagerly awaiting this. so a couple of days ago, as we record this, actually yesterday, as we record this, spell kit, 1.0 was officially released.

[00:11:36] **Ben:** Noise.

[00:11:37] **Adam:** is big for me because, you know, I've been eager to use felt kit, but they're for about. Two months ago they announced like a whole bunch of breaking changes that they were gonna be making and like big re-architecture stuff. And that really took all the wind outta my sails for playing with spelt kit, the framework.

[00:11:58] **Adam:** So I've done some spelt stuff, but not spelt kit. Kit is like the, the next JS for spelt. So I've just been doing the like, you know, the, this felt, which is like the, the react to, to next js. and you know, it's good. I, I'm enjoying the work, but I can clearly see how ITEL kit will be even better and I'm excited cuz now I can actually use it and not have to worry about the breaking changes and all that stuff.

[00:12:22] **Adam:** So, very excited about that.

[00:12:24] **Ben:** very.

[00:12:25] **Adam:** And then, I know I spent a bunch of time talking about, changes that we were making in support of emoji and I would be hard pressed to say for sure that this is the very first. email that we've sent that had emoji in it, but it was the first one that we noticed went out today, that had emoji in the subject.

[00:12:40] **Adam:** And so that, that made it appear on our, dashboard where we monitor all of the outgoing mail. So that was kind of a milestone

[00:12:47] **Ben:** do you have any, and this might be proprietary, but do you have anything like click through or open tracking? I Okay, cuz I'm curious there, there's controversy, or at least I've heard of controversy around whether or not emojis decrease interactions with the email. So I'd be curious to know if, if you guys are discovering any patterns emerging.

[00:13:10] **Adam:** Yeah, I

[00:13:10] **Ben:** it's the

[00:13:11] **Adam:** too early to say for this particular email. And also they didn't that I saw do any, like AB testing. I think if you were to, to do anything scientific, you'd have to have, you know, clear, you know, this is the only difference

[00:13:24] **Ben:** Right, right, right.

[00:13:25] **Adam:** And, and they didn't do that. This particular school would be good at it because they're really good at segmenting and, and they, so, from the tools that we've built, we've given them, given them ways to create very niche focused segments of their audience, and then send a message, a, a targeted message to that segment, right?

[00:13:43] **Adam:** The content of the message or the way that it's, like the perspective of the messenger or whatever, is very, tailored to the audience, right? And most schools don't bother with that. You know, they, they like, okay, here's a list of 300,000 people and, and email, send it, go . And this school, they're really good at like, okay, we're gonna do segments, you know, like our engineering majors want engineering news and the, you know, the journalism majors want the journalism news sort of thing.

[00:14:10] **Adam:** So they, they like split it up in, you know, they might wanna send 50,000 emails, but they'll send it across 40 segments or something. And so there's like 40 different messages each to a much smaller segment. anyway. yeah, they, so they could, I guess, you know, split and, and do some AB testing. We would love to add AB testing tools to our, our features or to our modules.

[00:14:31] **Adam:** But, it's not currently in the cards. Like we've just got bigger fish to fry right now,

[00:14:35] **Adam:** so that's like a one day thing.

[00:14:37] **Ben:** That's really interesting though. Email

[00:14:39] **Adam:** is a derail us December, right. So

[00:14:43] **Ben:** I mean, email is just so fascinating because it's one of those technologies that everyone kind of poo-poos and it's so old, and to, to Tim's point, all the kids are on Facebook,

[00:14:55] **Tim:** they're not.

[00:14:57] **Ben:** but it, it emails just, it, it, it persists con and it and it, and it makes a huge difference.

[00:15:03] **Ben:** And it, and it's still such a primary means of communicating with everyone.

[00:15:08] **Tim:** I mean, it's absolutely the best form of error logging,

[00:15:12] **Adam:** You're, you're fired.

[00:15:16] **Ben:** I was actually listening to an interview with the c t O of, I can't remember it, the CTO or the c o now I think he's the CTO O of MailChimp, and he was talking about the volume of email that they send and it's, it's numbers. I can't even wrap my head around. I, I, I'm sure this is not correct, but I think he was saying they send like, A billion emails.

[00:15:40] **Ben:** I, I wanna, I feel like he said a day they have like 217 shards of like, they have like 217 replications of their entire application running or something. I mean, it

[00:15:51] **Adam:** See, I thought you were gonna say per hour,

[00:15:54] **Ben:** It's, it's just, it's bananas. The amount of email they send

[00:15:57] **Tim:** Yeah.

[00:15:57] **Adam:** surpris.

[00:15:58] **Tim:** Yeah. I wouldn't be surprised.

[00:16:00] **Adam:** I got one customer that I feel like sends that much email

[00:16:07] **Ben:** Good times.

[00:16:08] **Adam:** maybe Ben, now we move on to you. How's your triumph for fail going

## [00:16:11] Ben's Triumph

[00:16:11] **Ben:** I'm, I'm going, it's a Triumph ish, which is that, a while back, maybe like a year ago, two years ago, I added comment moderation to my blog so that, unless you have a a, an approval. You, you know, you, you can't post comments directly to the site. They, they essentially get put into a pending queue and then I have to approve them.

[00:16:33] **Tim:** you have a blog.

[00:16:34] **Ben:** yeah, , and I don't even remember why I added comment moderation. I think it was because someone said a bunch of really jerky things. I'm like, you know what? I just can't stand people anymore, so I'm

[00:16:43] **Adam:** that Ray

[00:16:44] **Ben:** up,

[00:16:44] **Tim:** Yeah, right.

[00:16:46] **Ben:** that's what he is known

[00:16:47] **Tim:** It was.

[00:16:48] **Ben:** so anyway, the comment moderation hasn't made a huge difference.

[00:16:51] **Ben:** except I woke up yesterday morning and I had hundreds of pending comments in my comment queue, and I had,like hundreds of contact form submissions. Someone had started maliciously scanning my site from Australia. There were about 38 unique IP addresses from Australia, which I don't know how hard it is to get 38 unique IP addresses on, on cloud infrastructure.

[00:17:18] **Ben:** I presume it's pretty easy, but to me it seems very sophisticated.

[00:17:21] **Ben:** But anyway, I mean, nothing like that had ever really happened to me. but the triumph is that comment moderation basically took the brunt of it and users didn't see, anything. They didn't see any malicious content being posted the site.

[00:17:34] **Ben:** There was no service interruption or anything like that. And, I don't know. I feel like that was pretty exciting

[00:17:40] **Tim:** So, so what was the content they were trying to post?

[00:17:42] **Ben:** it, it, it was just like gobbledy cook. I mean, there wasn't even advertisements for anything. It was just, I I think they were just like automatically probing everything that they could try and probe.

[00:17:53] **Adam:** They weren't trying to sell V1 agra, or.

[00:17:55] **Ben:** No, it was, that's the, there, there was just a bunch of junk, you know, I guess, I

[00:18:00] **Tim:** Were there

[00:18:00] **Ben:** can,

[00:18:01] **Tim:** in it?

[00:18:01] **Ben:** no, that's the crazy thing. I guess what happens though is they, they probably, I'm, I'm guessing they are programmatically trying to post things and then checking to see if it shows up and then if it shows up, I assume then they post a bunch of crap.

[00:18:14] **Ben:** But it was a, yeah, just, I mean, people are the worst. and, and so it's a triumph ish because it's a triumph that, that there was no negative repercussions in the, in the site itself. But it is a bit of a failure in that. Clearly I need to add some sort of rate limiting to some degree, you know, to just try and, stop some of this.

[00:18:36] **Ben:** But,

[00:18:36] **Tim:** what do you use for your comment? Moderation. Is it home rolled or

[00:18:39] **Ben:** yeah, yeah, every, everything's home ruled.

[00:18:42] **Tim:** Okay.

[00:18:42] **Ben:** I like, I li I like to build stuff

[00:18:45] **Tim:** Yeah, that's, that's what the personal projects are for, right?

[00:18:48] **Ben:** I was a little surprised though that, so I, everything is fronted. Everything is, everything sits behind CloudFlare and CloudFlare usually I think, blocks a lot of malicious stuff. And for whatever reason, It didn't catch any of this.

[00:19:04] **Ben:** And maybe, maybe there were too many I, or maybe it caught some of it. I actually, so I did go into cloud. This is why I know how many IP addresses there were because I did have to, I looked in my, in my data and, use that to create some IP address blocking rules inside of CloudFlare. You can go into their, their web application firewall rules and you can just start blocking ranges of IP addresses.

[00:19:26] **Ben:** And I, so I put the kibosh on that and then it's interesting. So then the scan continued for, I'd say like a solid 12 hours, even after I blocked all the IP addresses. But you, cuz you can see them showing up in CloudFlare as being blocked by my rules. So they weren't even checking for success on any of their actions it seemed like. And it all, IP info, I dunno if anyone, did you guys ever use IP info? I. It's a, it's a cool little site where you could just put in IP addresses and like chunks of IP addresses and it'll tell you where they're from and like what corporation is

[00:19:59] **Tim:** G Yeah, there's several sites like

[00:20:01] **Ben:** Yeah, yeah,

[00:20:01] **Tim:** things. Yeah.

[00:20:02] **Ben:** and all of these IP addresses were being announced as a Microsoft, but I assume that just means it's like Azure Cloud computer, something.

[00:20:10] **Tim:** Probably.

[00:20:10] **Ben:** yeah, that, that's me. Three triumphs,

[00:20:13] **Tim:** Yeah.

[00:20:15] **Ben:** not bad.

[00:20:15] **Adam:** The energy is really flowing right now.

[00:20:19] **Tim:** Hey, it's no effort, man. No effort.

[00:20:23] **Adam:** well I see here. Let's see. Tim is breaking stuff. Ben is worried about cutting his fingers off. And we're gonna talk about o off

[00:20:30] **Tim:** no, I'm not breaking stuff. I'm talking about breakthroughs.

[00:20:32] **Adam:** I know. Trying to make it sound good.

[00:20:36] **Tim:** Okay.

## [00:20:38] Getting Into Woodworking And Safety

[00:20:38] **Ben:** All right. So I'll, I'll kick it off then. I have over the years amassed a series of barbells of various lengths and dimensions and I have them kind of in a pile on the floor in the basement. And, some of them are pretty heavy. Some of them are, you know, like 50, 60.

[00:20:57] **Tim:** I mean, not tore. You're swell, bro. I get it.

[00:21:01] **Ben:** And I, I get nervous having to get them off the floor cuz I'm not flexible, especially my hamstrings. And so getting all the way down to the ground, picking up, I feel like I'm, I'm bound to hurt myself. So ideally

[00:21:13] **Adam:** the ones that have their own parking spots?

[00:21:18] **Ben:** so ideally what I would like is to build myself some sort of a barbell rack. And and I think it's for people who know how to work with wood, I think it's probably the easiest possible thing to build. It's basically just like a little frame with some. Some, like little notches on it that, that you can rest the barbells on.

[00:21:39] **Ben:** I'm sure if I was taking like an intro to woodworking class, I could build something like this, but I am so absolutely terrified of cutting my fingers off that I, if, if, if I even dane to attack this problem, it will be with a manual, you know, sliding back and forth kind of a saw because getting near any sort.

[00:22:02] **Ben:** Yeah, yeah. Handsaw, like getting near any type of, of mechanically, rotating blade. I, I just, I'm, I just can't do it. I just can't do it.

[00:22:13] **Tim:** What's funny is your, your fear would probably even make you like, just accidentally just do it cuz that's all you're

[00:22:19] **Ben:** Just don't touch it. Don't touch it

[00:22:21] **Adam:** Mm.

[00:22:23] **Ben:** But I know Adam, like you do a, you do a ton of woodworking and, uh, you also use your fingers for. Income. And so you don't seem to have any of this fear. Was there, was there fear in the beginning? Did you have to overcome this fear or you were just, from day one you were, it didn't matter.

[00:22:40] **Adam:** It's

[00:22:41] **Ben:** So he asks the guy who jumps out of planes,

[00:22:43] **Adam:** Yeah. I mean, I, I'm trying to figure out where, how, how do I start my answer to this? So, I guess I would say my, my initial exposure to woodworking would've been in high school in like shop class. Right. And so there, we had, you know, the, the, the stereotypical teacher with nine fingers, you know, like

[00:23:04] **Tim:** Did he

[00:23:04] **Adam:** the whole, yeah.

[00:23:05] **Adam:** And the first

[00:23:06] **Adam:** whole, the whole first week of, of the class was like, you know, we're just focusing on safety and what to do and what not to do and what to do in an emergency and all this stuff. And then we finally got to make, you know, a banana stand and a, a little. Like flat pack rabbit . Anyway, so I got exposed to it early on and then I got out of it for a long time, and then I got the bug again. Oh, that's what it was. So, several years ago, my wife wanted a growth chart to track our children's heights as they grow. Right. So it looks

[00:23:39] **Ben:** like pencil lines on the, yeah. Yeah.

[00:23:41] **Adam:** huh? It, it looks like a ruler. you know, like the, the ruler you had in school that was like a piece of wood with a little metal edge on that, on the side.

[00:23:47] **Adam:** and you take that and you stand it on end, and then you put it up against the wall and then you scale it out so that an inch on there is a foot in, in real life, right? So you've got a, like a six foot, ruler. And so really all it was

[00:23:59] **Tim:** Wow. Way to limit your kids. Just six

[00:24:02] **Adam:** Well, so I started mine at, like three quarters of a foot, or three quarters of an inch so that it goes up to six and three quarters.

[00:24:11] **Adam:** Right? So, so if they could go to six foot, what is it, nine or something? and, and that would be,

[00:24:17] **Adam:** but they're, they have my jeans. They're not gonna be six nine, they'll be like 6 2, 6 3 if they're lucky. Um,anyway, so it was a really simple project, right? It was like, I, I went to the Home Depot. I bought a board.

[00:24:27] **Adam:** I, I had, I, I used some tools, from my brother-in-law to like, you know, make the board nicer, like round the edges and corners and stuff. And then I stained it real nice. I put a nice go to finish on it, and I had bought, like, on Amazon,an applique, I guess you would call it. It's like a giant sticker of the, the ruler.

[00:24:44] **Adam:** And it's all to scale and everything. So you just like stick it down and make sure it goes on straight and doesn't have any, Bubbles or whatever. And that was it. Like, and then I put a little keyhole thing in the back of it to hang it on the wall. and that was like my reawakening into woodworking. It was like, wait a minute.

[00:24:57] **Adam:** I really enjoy waking stuff. This wasn't even, you know, that much of a make, but it was like, wait a minute, this is unlocking something in me. and so from there I got, I went deep into a rabbit hole of YouTube. I got real into like maker YouTube. and if you want, I could give you some suggestions, especially like for, you know, for the position that you are in, right?

[00:25:17] **Adam:** Somebody who doesn't have a whole lot of tools, doesn't have any experience and, and just wants to like safely get into it and, and know, you know, what to build, what, how to do it safely correctly, and, and learn from it and that sort of thing. and I, I probably watched way too much YouTube before I even actually got started.

[00:25:38] **Adam:** But one of the benefits of that is, you know, Sort of the evergreen content of Maker YouTube is safety stuff, right? So tips on it, how to use the table, saw safely, tips on how to use the band, saw safely or whatever. and so I, I learned a lot from that. And then because of the high school stuff and because of the YouTube stuff, I went into it with a healthy respect for the tools.

[00:25:58] **Adam:** I've always been, thanks for the anxiety mom, but I, I've always been a, a catastrophist, you know, e everything I do, I'm constantly like, what's the worst that could happen here? and so I think that that also contributed to my just, you know, general approach to everything. Always. Like, not, I'm not afraid to try stuff, but I try to be cautious and conservative about it and notice when things go wrong or are about to go wrong and try to learn from that.

[00:26:25] **Adam:** And, you know, that's not to say I haven't made any mistakes, I don't think I. Hurt myself with tools in any significant way, you know, more than just like, you know, bumping something and getting a cut or whatever. But I'm not talking about like bumping a, a spinning saw blade. I'm talking about like walking backwards into my band, saw when it's off and like the, the sharp edge of the table.

[00:26:43] **Adam:** Right. You know, like pokes me, that sort of thing. But, I

[00:26:46] **Tim:** I I would say, I would say, I would say, Ben, if you're scared of like, you know, woodworking injuries, do not watch the movie Walk the.

[00:26:52] **Ben:** Which one's that

[00:26:53] **Tim:** This is Johnny Cash biopic.

[00:26:56] **Ben:** is, is that the one with, Reese Weatherspoon and, Yeah. Yeah, I've seen that. I don't

[00:26:59] **Ben:** rem Did he

[00:27:01] **Tim:** So his brother? Yeah, his brother. They're like working, like doing sawing like making boards and his brother fell on the moving blade and died

[00:27:10] **Ben:** Oh,

[00:27:11] **Tim:** and his mom's like the wrong kid died.

[00:27:15] **Ben:** that's dark. Well, I mean, so, so the irony, I mean, Adam mentions, thank you, mom, for the anxiety. my dad was a terribly skilled woodworker. I mean, the man could build anything. And he had, he built himself a whole workshop off the side of the house with like all kinds of machinery and just was not afraid to do anything and tried building anything.

[00:27:42] **Ben:** And somehow that skipped generation and whatever chutzpah he had, it does not exist in me at all.

[00:27:49] **Tim:** but could he builds own content moderation?

[00:27:52] **Ben:** Probably not

[00:27:53] **Tim:** Probably not.

[00:27:55] **Adam:** So going back to the intrusive thoughts of like, you know, don't reach in there. Don't touch to solve Bleed. I, you know, even as experienced as I am, you know, it's, there's certain things, like I have a CNC machine, which is a computer controlled router. So it's got the spiny bit, spiny blade. It's like a, like a stick sticking out of the, out of a motor, makes it spin, and then it's got a blade on it and, that's kind of pointing down.

[00:28:19] **Adam:** And then you, you can lay down and, and, secure a piece of wood underneath of it. And you have a computer that can control it, X, y, and Z. And so can cut out different things or, or create textures and all kinds of fun stuff. And it's not something that I struggle with, but it's, every now and then I just catch myself going. I could, I, if I, there's nobody to stop me, I could just stick my hand in there,

[00:28:44] **Tim:** Yeah, life is full of risk, man.

[00:28:46] **Ben:** All right. Well, maybe, in, in the 2023 year in review, I will, be able to report some, some very low effort woodworking abilities.

[00:28:57] **Tim:** Yeah. You, you, you know what I do see? And I totally get your fear, Ben, cuz I have this constant like, recurring dream of like my fingers falling off. And a lot, a lot of it has to do with the fact that I'm, like, I, when I'm sleeping, I press on the headboard and my hand starts, my hand starts to hurt, and then my dreams start to interpret that as like, my skin's falling off, my fingers are coming off.

[00:29:18] **Tim:** So when I do, we're working, I use a jigsaw. I mean, it's really hard to cut a finger off with a

[00:29:23] **Ben:** what's

[00:29:24] **Tim:** it's, So it's a little handheld, little handheld thing

[00:29:28] **Tim:** kind, and

[00:29:29] **Ben:** Like where the blade goes, up and

[00:29:30] **Tim:** little, little blade goes

[00:29:31] **Ben:** yeah, yeah.

[00:29:32] **Ben:** Yeah.

[00:29:32] **Tim:** down. Yeah. I mean, you could definitely skin it pretty good, but it's like, that's completely different from like a high speed, you know, table saw where you're like, just slap your hand down, like hand cutting in half kind of thing.

[00:29:44] **Ben:** I think I, I think maybe I've actually used a jigsaw when I was a kid, ironically. So I think I had more guts as a kid than I did as an adult

[00:29:51] **Tim:** yeah. Yeah. How had less knowledge,

[00:29:53] **Ben:** true.

[00:29:54] **Tim:** and

[00:29:54] **Ben:** had less to lose

[00:29:57] **Tim:** Yeah. The same amount to lose 10 fingers, but

[00:30:00] **Adam:** So for your barbell rack though, if you, if it is something you do decide to pursue, I would say be careful to over build it, especially if you're gonna be putting these gigantic car sized barbells on there,

[00:30:12] **Tim:** Yep.

[00:30:12] **Adam:** you know, think about, you know, am I using a cheap two? But, well, no, they're no longer cheap, but, you know, material, low, low quality material, not cheap, two

[00:30:22] **Ben:** of wood all the way,

[00:30:23] **Adam:** Lowe's to, to hold up, you know, five barbell, or I guess they're not, you're probably gonna do even pairs, but you're like 10 barbells that are all each over 50 pounds.

[00:30:32] **Adam:** Right. You know, that's a lot to ask

[00:30:34] **Adam:** from, you know, a, a third of a two by four or something like that.

[00:30:40] **Ben:** Yeah. Yeah,

[00:30:41] **Ben:** over. Agreed

[00:30:43] **Tim:** or better? Yeah, just learn welding and you don't have to worry about your fingers.

[00:30:46] **Adam:** there you go. And Max could teach you,

[00:30:48] **Tim:** Yeah. Max. Yeah, max show you

[00:30:50] **Adam:** I was gonna say maybe you're not that far from me. Maybe you should just come down and hang out with me for a day and we'll build something

[00:30:55] **Ben:** That'd be fun actually. Yeah, could have some hers potato chips.

[00:30:59] **Tim:** Some hers.

[00:31:04] **Adam:** We'll take some hymns.

[00:31:09] **Tim:** Some hers and hymns. Oh, yep. Once you get a certain age, that's all the advertising you see on Facebook these days. not the hers, just the hymns. Anyway, so I'm gonna take it from here, Ben. If you're, if you're done.

[00:31:27] **Tim:** Yeah.

## [00:31:28] Recent Technology Breakthroughs

[00:31:28] **Tim:** So maybe it's me just getting older, you know, you know how, how your old folks

[00:31:34] **Adam:** I'm also getting older.

[00:31:35] **Tim:** things, everyone's getting older, but it's like, you know, folks talk about how changed your whole fire care, keep up, watch this internet thing.

[00:31:44] **Tim:** Right? but seriously, this, just this past, even just like six months, I've just had this feeling from all the news I read and I, and I always read the news, so it's not like it's a new thing that I'm, I'm reading tech news, but there's been a huge amount of what I feel are significant breakthroughs

[00:32:01] **Ben:** Yo.

[00:32:02] **Tim:** that

[00:32:02] **Adam:** Well, I mean, you're not wrong. So just to, to zoom out a little bit here. I don't, I don't know the exact number. So again, you know, working code podcast, you're number one source for misinformation about things. But, um,the, what we would think of as like, you know, recorded human history is like less than a percent of actual human history, right?

[00:32:24] **Adam:** So we're talking about from the time that they built the pyramids until earlier this week, they announced the first successful fusion reaction.

[00:32:33] **Tim:** That, that's what I was, that's one of the things I was thinking about.

[00:32:35] **Adam:** Right. So, yeah, like, you're, you're absolutely right. The, the, the, it feels like we're still accelerating.

[00:32:43] **Tim:** Yeah. It it is crazy. So it's like, yeah, we, the announcement just this week was that they, they actually created a, a fusion reaction and we used to call it ColdFusion, but it's like super hot laser. So I don't know how cold. That actually generated more power than was put into it. Right. So that's a huge milestone.

[00:33:01] **Tim:** They've been working for that forever. That the whole joke about ColdFusion is that not the programming language, the actual G energy generation is that it's always 30 years away, but now with this kind of thing, it's like, you know what, it might be just 10 years away now for, for real. Right. And they're not the only ones.

[00:33:17] **Tim:** There's, there's several other tracks of, of ways of doing, fusion that have had significant results recently, but this one was touted by the US government, cuz they've spent billions on it, so they have to tout it. But a and then, so the stuff with, you know, the M R N A,

[00:33:34] **Adam:** Vaccines.

[00:33:35] **Tim:** vaccines, so just, so just recently they announced that they have, they can create a vaccine to treat cancer.

[00:33:43] **Adam:** Hmm. I missed that one.

[00:33:46] **Tim:** Yeah. So I mean, it was just,

[00:33:47] **Tim:** it was

[00:33:47] **Adam:** types of cancer.

[00:33:48] **Tim:** so this one they're focusing on, I mean, they could possibly do it on all types of cancer, but the one they're focusing on is melanoma. So, so with melanoma, they can, they, but it has to be like a personalized build. So they, they can take your cells, your melanoma cells, they can build an mRNA.

[00:34:05] **Tim:** mRNA is basically, you basically give it a mugshot of what you want to kill. You put that in a vaccine and that vaccine goes off and kills it. That's a very super simplified way of looking at it, but it just says, here's a, here's a section of, of, of cells that represent this cancer. Go kill it. And they, they did that, and I mean, it's, it's working.

[00:34:27] **Tim:** They can also take, so, take a, so people have rare forms of, blood leukemia that are incurable. That would ne ne person would necessarily die. A young girl was cured of it. Using these same sort of, cell manipulation DNA n manipulations. They would take a

[00:34:44] **Tim:** healthy, they would take a healthy white blood cell, modify it and modify the D n A so that it would find basically all the cancerous blood cells in her body and kill them.

[00:34:57] **Tim:** And once it killed them all, they would give her a, they gave her a, bone marrow transplant and it would generate healthy blood cells after that, white blood cells after that. And so it's like,

[00:35:07] **Ben:** It's just crazy.

[00:35:08] **Tim:** yeah.

[00:35:09] **Ben:** Well, in talking, I mean, I don't know if this is building on top of crispr, but crispr as far as gene editing is like a whole nother just crazy bananas awesome thing. I mean, awesome. Depending on who you talk to.

[00:35:22] **Adam:** It's . It's funny, I read a lot of, like sci-fi near future, potentially apocalyptic, you know, like people see what's interesting in the news and then how could it go wrong? And they, they write a book about, you know, that potential future. And those are the ones that's I tend to gravitate toward.

[00:35:40] **Adam:** and so I've read several books in the last couple of years that are based on like, the idea of CRISPR and jean hacking and that sort of thing. I just finished one like three days ago called, upgrade, which was really good.

[00:35:52] **Tim:** Yeah. And, and, and so I mean, that's like biochemistry and, and just even like the stuff that's gone on with ai, we, we talked about a lot the past few episodes, but just the AI has like grown leaps and bounds within the past six to eight months, how

[00:36:07] **Adam:** who's. ,it was less than a year ago that I was like, that's a joke. Right? They'll, they will not come for our jobs within my lifetime. And I still think that would be a bit excessive to expect them to come for our jobs in my lifetime. But I've totally changed my position on having them there to augment, you know, the, the code that we're writing, I was working on something today and you know, this is just GitHub co-pilot, where, you know, it's like doing something repetitive, right?

[00:36:35] **Adam:** So I was making, I was adding a set of. Database columns to a bunch of API resources. and you've got a bunch of different views of the same data. So I was going around and I still had the files open where I'd already added the columns in one place and then, you know, go over here and I hit enter to go to a new line and I start just a couple of characters of the first one that I wanna add.

[00:36:53] **Adam:** And it's like, oh, do, are you trying to add this? And it was the first one and it, and one at a time. You know, I, I, I would say, okay, sure. Accept that. And it's the first one, it hit enter and it would immediately suggest the second one, like, sure, tab enter tab, enter tab, enter tab, enter. And it was like, sure, save me all that time.

[00:37:10] **Adam:** Thanks.

[00:37:11] **Tim:** Yeah. Yeah. That it did, it just, and that's very, very new. I mean, that's this year that stuff that, that's really

[00:37:19] **Adam:** second half of this year.

[00:37:21] **Tim:** For

[00:37:21] **Tim:** sure. Yeah. So I just, like, so you talk about you don't, they're not coming for your jobs, talk to artists right now. Right. So I'm seeing a lot of extremely negative pushback, you know, so these are just people who are like playing with some of like the, the, the AI filters, right.

[00:37:38] **Tim:** That, that do artwork on your, on your face and stuff like that. Lindsay, I think is a popular one. And this, I talked about earlier, she, like, she's a college player and she would like just kind of like put prompts in to come up with things to see how she looks. And she deleted all of them because like someone basically lambasted her saying, you're stealing from artists and you're, you know, like people have very black and white opinions about this right now.

[00:38:03] **Tim:** And it's like, you know, the genie out of the bottle here that this isn't going away and I don't think this is gonna get resolved in the next 10 years. Honestly, I don't think we've really fully dealt ethically with the, the last revolution of just the computers,the computer, like being able to do things with computers and, and,

[00:38:23] **Adam:** when you say dealt ethically with it, you're talking about like, you know

[00:38:25] **Adam:** how

[00:38:26] **Adam:** we have the internet and, and it was not thoughtfully spread and so now like the social injustices of the real world have just kind of repeated themselves in

[00:38:36] **Adam:** the

[00:38:37] **Tim:** Yeah. Well, I mean, well, I mean, think about like for instance, you know how Google will just scrape like news sites and then put them up as part of their search results that you don't even have to go to the news site. So these news sites are like generating content, but they don't get any benefit from it.

[00:38:52] **Tim:** If a person just looks at the Google result and just looks at it and goes, okay, and they don't actually go to the site and get the ads or whatever, so, so it's like the rate of change and the breakthroughs just particularly this year, just have made me feel like, wow, are we at a inflection point or is just like, I'm just catching up with the rest of the world.

[00:39:13] **Ben:** Well, I think I even heard some news piece about quantum computing. Like, you can, you can start to rent quantum computer or like rent time on these massively powerful quantum computers. I, I don't even understand the science behind it, but it sounds crazy.

[00:39:30] **Tim:** So you, you brought that up. That was another thing. So that was a breakthrough. So they were able to prove apparently, on a quantum computer, a Google Quantum computer. The actual, an actual wormhole.

[00:39:44] **Ben:** Oh, this is the sending data through like protons moving at the same speed or something kind of a.

[00:39:50] **Tim:** Yeah.

[00:39:50] **Tim:** So, so exactly. Spooky accident at, at a distance. So Einstein Rosen basically said, that, you know, wormhole you could possibly go in one, in and out the other, but they couldn't come up with a way to figure out, you know, wormholes can kind of collapse on their own. So they couldn't actually tr Traverse through it.

[00:40:07] **Tim:** And later, I think it was, like 2018, I think it was, the number's probably wrong. But anyway, so someone basically came up with that. Einstein Rosen Bridge is actually the exact same thing. The wormholes, the same thing as spooky action at a distance. And so they couple scientists, like three or four scientists, spent two years working on a, a Google Quantum computer and actually showed in real time that information that went in one side came out the other, but the distance was longer than it should have been because it was going through a wormhole.

[00:40:43] **Ben:** Crazy.

[00:40:45] **Tim:** So, I mean, they proved that you could travel through a wormhole. So, I mean, you think about that if, if that is true, if you could actually travel through a wormhole and a, and a wormhole is basically a black hole. So if that's true, uh, they, I mean they're, they're, they're similar. So yeah,

[00:40:59] **Ben:** It is

[00:40:59] **Ben:** bananas.

[00:41:00] **Tim:** nuts.

[00:41:01] **Adam:** yet, you know, DHL can't get a package from here to there in

[00:41:07] **Ben:** yo. So here, just to put it on perspective a little bit though, I find it fascinating that given all of this crazy stuff, I'll, every now and then be flipping through TV and I'll come across this show. It's been on, I wanna say like at least 15 or 20 years called How It's Made. Have you ever seen that?

[00:41:24] **Adam:** Oh, yeah, yeah.

[00:41:24] **Adam:** Yeah,

[00:41:25] **Ben:** It feels like it was the original A S M R. It, it's just like a monotonic person narrator talking about how factories work. Like, oh, how did this basketball get made? And talks about all the machinery that goes into it. When they look at these machines that build these stuff in the factories, I'm, I'm blown away that we can do that kind of stuff.

[00:41:45] **Ben:** That, that, you know, some, like, there's a machine that rolls the steel and then cuts it and there's a machine that applies the labels and then something that spurts goo into it and then applies the top, I mean, and then like, and then packages it, and then

[00:41:57] **Adam:** And then they add the FL I don't think Tim got it.

[00:42:08] **Ben:** I dunno if I got it. It was

[00:42:10] **Adam:** It was a Rick and Morty reference.

[00:42:12] **Ben:** I just, I just enjoy. but I, yeah, and, and you know, these factories have been around for ages, it feels like. And the stuff that they, that they're doing in there with these giant machines is amazing to me.

[00:42:24] **Adam:** And the economies of scale that that produces, right? Like when you make a billion basketballs a year, you can sell 'em for 3 99, even though the exact same materials and the exact same methodologies would cost me like $50 to make one basketball.

[00:42:37] **Adam:** Right?

[00:42:37] **Ben:** Right? And, and they're cooking stuff. That's the thing that I think blows my mind the most is, is their cooking things with such extreme precision where, you know, a company that creates,pancakes, frozen pancakes, they're making like a million pancakes a day or something in their factory, and they're all, exactly the same quality.

[00:42:57] **Ben:** I mean, it's mind boggling.

[00:42:59] **Tim:** If, if you wanna watch something funny, there's a YouTube channel called Huggies.

[00:43:04] **Ben:** Huggies.

[00:43:05] **Tim:** Huggies, how it's actually made, and it's a parody of, so they take these videos like, or like they show the actual how something is made, but it's a complete, the, the guy like has a very serious voice, but it is a complete joke.

[00:43:18] **Tim:** It's so

[00:43:19] **Ben:** That sounds fun. We'll have to, we'll have to share a link to that.

[00:43:22] **Tim:** It is super funny.

[00:43:25] **Adam:** So actually I want to take this discussion and go back to tech with it, right? So you were talking about how. you know, the, the rate of change continues to accelerate and, and I think that we can all just kind of generally agree that that is also true for tech. We don't have to give any specific examples.

[00:43:40] **Adam:** We just,

[00:43:41] **Tim:** Yep,

[00:43:42] **Adam:** you can tell it it's true because of the way it is. and I think the o the only thing that's coming to me for like, ways that we're gonna have to find, to deal with this is through increased specialization, right? We've already seen it where like, I don't know, was it five years ago, 10 years ago, there was no such thing as a front end developer, right?

[00:44:04] **Adam:** There was just, I'm a web, I'm a web master and, and so like now we have front end and backend developers. We have DevOps, we have, you know, probably a dozen other, I'm sure you have Kubernetes specialists, right? Like, I, I, I don't know how, but I think we're gonna have to continue to specialize so that the. Problem space of things that are continuing to grow and innovate. you know, there's less of it that you have to pay attention to, which makes it possible for you to stay on top of it well enough to be good at that professional,

[00:44:37] **Tim:** Until the AI just takes over, you just explain the program to it.

[00:44:41] **Adam:** So, again, going back to that, like the way that I found that to be super useful, beyond just like copilot, but like ChatGPT, I've been using that to have it write, Linux command line, like commands, like I'll say, you know, generate a Linux alias that will pull the third line out of this file and grab the seventh column tab to limited, and reverse the string and, you know, whatever things it needs to do.

[00:45:05] **Adam:** And it's like, here you go.

[00:45:06] **Ben:** What? Really? That's

[00:45:08] **Ben:** amazing.

[00:45:10] **Tim:** I, I saw you posted something about like generating a, a Git request to basically squash all the commits in a branch

[00:45:18] **Adam:** yeah, yeah, yeah. So we were talking

[00:45:18] **Adam:** about the, the ftx, their trial was starting in government whatever today, or not today, but that day. and so somebody made, somebody posted something that like basically get commit, in their repository was being used as evidence against them. Like that they knew what that what they were doing was wrong.

[00:45:36] **Tim:** Yeah. N never liquidate Alameda. Was, was the comment

[00:45:40] **Adam:** And, and so like, I was like, okay, well how can I turn this into something humor? So I, I asked Ja Chat, g p t to generate like a Linux alias named Raid, right? The, the alias name is Raid and it's, you know, squash all, all commits on the branch down to One Commit and you know, they're like, give it some super generic, commit.

[00:46:02] **Ben:** I didn't realize I could do stuff like this. I haven't tried it. I just see the things people are posting on social

[00:46:06] **Ben:** media

[00:46:07] **Tim:** I mean, correct me if I'm wrong, apparent. I, I think chat g B t is used by code pilot.

[00:46:13] **Adam:** I think that they might have some similar, there might be some overlap in the engine or something, but I don't think, from what I've heard, that they are

[00:46:24] **Tim:** Okay.

[00:46:25] **Adam:** using each other. But again, you know your source for misinformation,

[00:46:31] **Tim:** Not misinformation.

[00:46:32] **Tim:** Just, uh, you know, it's not, it is not fake news. It's just wrong news

[00:46:39] **Adam:** we've never let, not knowing what the truth is, get in the way

[00:46:42] **Tim:** Exactly. Ignorance. Ignorance is is not something we shy away from.

[00:46:48] **Ben:** here. Here's going back to some of the bioengineering stuff for a second, and, and this is such a fascinating thing to. And I, and I hope I'm not getting this wrong, but I remember hearing a, an interview with one of the people who was working on the CRISPR project, and they were talking about how they're taking the economies of scale, kind of like what Adam's talking about and applying it to crispr.

[00:47:10] **Ben:** And in China they had some massive laboratory where in, you know, they have like a hundred thousand mice or something, I think they were talking about. And they're using CRISPR to just randomly try changing the genes. And they're like, we don't know what it's gonna do, but we have a hundred thousand mice.

[00:47:27] **Ben:** Yeah. But you know, like, we'll just tweak this gene and see what happens. And they're doing that at the scale of hundreds of thousands of mice. And, it just like, it's just mind-boggling to take, to take just to, to brute force, progress that way. It's kind of, it's, it's both terrifying and, and awe-inspiring at the same time.

[00:47:49] **Adam:** That's like the plot of any of, you know, one out of every of five of the last 20 books that I've read.

[00:47:58] **Ben:** Oh man.

## [00:47:59] Social Logins

[00:47:59] **Adam:** So, Ben, you had this other thing on here.

[00:48:01] **Ben:** Yeah, social logins. So by social logins, I mean, is you go to, to say, sign in to discuss commenting, which is a commenting, feature on a lot of static sites. And, you can sign in with GitHub or you can sign in with Twitter, or you can sign in with, with, WordPress, or you can sign in with your email.

[00:48:20] **Ben:** And I, I totally understand the allure of wanting to sign in with a social network because it's like one less password you have to create. but the thing that bugs me is I can never remember which thing I used to sign into something.

[00:48:32] **Adam:** Yes.

[00:48:33] **Ben:** Like, I'm like, oh, was I in a Twitter mindset, so I logged in with my Twitter?

[00:48:37] **Ben:** Or did I want to be more professional? So I started logging into everything with GitHub or like, did, was GitHub not always an option? And it got added later, so maybe it isn't the thing that I used. And I, and and there are sites now that I see that don't even offer a standard username and password or email password option.

[00:48:55] **Ben:** Like it's only social logins and I'm, I'm just sort of over it. I don't enjoy it. I, adding things to one password is so easy and, and I have all the control and I just, I would rather do that all the time. I don't enjoy the social login experience.

[00:49:13] **Adam:** My role used to be like, I would just use Twitter for everything cuz I was on Twitter and I, I, and I had a, an early distaste for Facebook. So my role was like just never Facebook. Right. If that's, if that's, uh, one of the options I knew it was not the one that I had chosen. And then I hit good reads and it is like, I had, I, I think I had a username and password there, but either they were really pushing social login or something and, and they got bought by Facebook.

[00:49:41] **Adam:** And so it ended up that I have now it's like the one site that I use Facebook to log into. And to your point, like. If something is like a developer tool that I use for work, I tend to try to use the GitHub, social login if they offer it. Or is it okay, well did I, did I log in with my personal Google, Google account?

[00:50:03] **Adam:** Or did I log in with my work Google account? You know what? Oh, you wanna know what really grinds my gears If you've got Google login, right? But if I, if I do Google login and I choose the wrong Google account, and instead of saying we don't have an account for that email address, you just go ahead and create a new one for me, just like

[00:50:24] **Tim:** Where my stuff go.

[00:50:27] **Adam:** well, I was gonna curse real bad, but just like f right off, right? Like, that's, that's just the worst. Cause now, now I have to go dig around and hope that you have some sort of account delete thing automated and I don't have to like, get in touch with customer service to delete this account that I never wanted in the first place.

[00:50:43] **Adam:** So that hopefully, like when I do, when I have the same problem next year, the, the, the one time a year I need to log into your service. I'm like, wait a minute, this account exists. It was created a year ago. Why? Why is there nothing in it?

[00:50:56] **Ben:** Yo. And, with, I don't understand what a pa, what did Apple come out with? Like passcodes or something. What's it

[00:51:03] **Ben:** called? pass keys.

[00:51:06] **Ben:** Yeah. It

[00:51:07] **Tim:** is coming out soon.

[00:51:08] **Ben:** with Apple doing that. And I think Google's supposed to be doing something similar. and the fact that, you know, like Twitter is melting down and people have been going off of Twitter and people are going off Facebook, it, it feels like less and less.

[00:51:22] **Ben:** And, and I don't know how far this extends outside the world of technology or those, you know, in the world of technology, like you wanna own your identity and I, I wonder if the concept of a social login is just gonna phase out.

[00:51:35] **Tim:** well well Pasky, so the whole thing with Pasky is like, it's a private, a public private key pair. And so you basically have your own, you have your own private key that's stored locally in, then you have to be able to biometrically log into the device. So typically it's your phone, but you never actually use the same password twice on any site.

[00:51:56] **Tim:** That's, that's the promise of passcode, which, hey, I'm that, that sounds

[00:52:00] **Tim:** great because. That's, that's the big problem is some, you know, some site gets hacked, Adobe or you know, whoever, Microsoft, they get hacked, all the passwords are exposed, and now people tend to reuse the same password over and over again.

[00:52:13] **Tim:** Right. Just cuz I mean, they're human, but, but with passkey, as long as you have your private key on your, you know, biometric device, then every single time you log in, it's a, it's a new password every single

[00:52:28] **Adam:** So what's the

[00:52:29] **Adam:** relation, what's the relation between something like this? And like a Yuki, which is like the, it's like a Yuki is like a USB thing that you plug into your computer and that authentic, so it's, it's kind of like a, a slightly better version of like, before we had like, you know, Google Authenticator and apps on your phone to give you one time passwords.

[00:52:49] **Adam:** People had 'em on like key chains. Right? So

[00:52:52] **Tim:** Little, little dongle.

[00:52:53] **Adam:** Yeah, yeah. Rsa. Yeah, yeah, yeah. And so like, Yuki came along and it's like, okay. , I have my keys and they're plugged into the side of my laptop, and that's good enough, like it would somehow through the usb, just know that. Okay. You have Tim's device so you can log in as Tim.

[00:53:09] **Tim:** It's, it's kind of like that, but I mean, if someone stole your YubiKey, they could basically plug it in somewhere else and log in as you, with the idea is with a biometric device of passkey, it's like, it's either your fingerprint or your face. You know, they, they're gonna have to have that phone that has your, your private key stored on it in order to log into it.

[00:53:29] **Tim:** So it's a little more safe than, yeah. You lose Yuki your sunk. Right.

[00:53:34] **Adam:** maybe? Yeah. I mean, probably not anymore than if you lose your, you know, your Google Authenticator keys,

[00:53:41] **Tim:** Right. But you lose your phone and a person can't use their fingerprint or their face to log into it. They're not gonna be able to get

[00:53:48] **Adam:** Sure.

[00:53:48] **Tim:** site.

[00:53:49] **Adam:** Yeah.

[00:53:50] **Adam:** That's

[00:53:50] **Adam:** fair.

[00:53:51] **Ben:** So anyway, I don't like social logins. I'm, I'm done.

[00:53:55] **Adam:** Yeah, that, that's the exact same. That's why I have two logins on our Discord here, because I used one email and then another time I, some reason I couldn't get in, so I now have two. I, I think I kicked one of them out.

[00:54:06] **Tim:** that's

[00:54:06] **Adam:** the one you don't use.

[00:54:07] **Tim:** log in.

[00:54:08] **Adam:** Cool. well, I guess that seems like a good enough place to wrap it up. So,

## [00:54:12] Patreon

[00:54:12] **Adam:** okay, so this episode of Working Code was brought to you by cutting your fingers off with a jigsaw and listeners like. If you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe with effort or without, you should consider supporting us on Patreon.

[00:54:27] **Adam:** Our patrons cover our recording and editing costs, and we couldn't do this every week without them. Special thanks to our top patrons, Monte, Sean, and Giancarlo. If you wanna help us out, you can go to patreon.com/WorkingCodePod.

## [00:54:39] Thanks For Listening!

[00:54:39] **Adam:** Alright, your homework this week, I'm gonna say join our Discord and that's gonna be useful because we are planning, trying to put together, we don't have a date or anything yet, but a, a tentative plan to have a ga another game night where we just get together and play video games or board games or something like that over our Discord video chat.

[00:54:56] **Adam:** Done several in the past, always a lot of, lot of fun, really good time. and if you want to be involved in that, join our disc. Currently we're trying to shoot for some time between Christmas and New Year's Eve. I guess this, this is coming out on December 28th, so maybe we will, if possible, schedule it later in the week.

[00:55:11] **Adam:** So if you hear this, and it's not, not January 1st yet, get on the Discord, look for Game Night, get the details, and come have a good time with us. on the after show tonight, which is a, you know, after show is the thing that the patrons are just gonna keep listening after your episode ends. They're gonna keep listening.

[00:55:26] **Adam:** And tonight we're gonna talk about, Tim is apparently drinking blood. So we're gonna be asking him about that , that that's what it looked like at least. and, and we'll see where it goes from there. send us your topics or questions @WorkingCodePod on Twitter. As long as that continues to exist, we should set up a Mastodon or something because, I, I just, every time I go on Twitter, now it's worse and worse.

[00:55:45] **Adam:** join our Discord, like I said, workingcode.dev/discord. You can email us WorkingCodePod@gmail.com. That's it for us this week. We'll catch you next week. And until then,

[00:55:54] **Tim:** Remember,

[00:55:55] **Tim:** Your heart matters No snappy comeback this time because that's a, a 2023 problem.

[00:56:00] **Adam:** nice,
