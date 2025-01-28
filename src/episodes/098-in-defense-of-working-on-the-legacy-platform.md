---
title: "098: In Defense Of Working On The Legacy Platform"
description: "In this episode, Adam plays Devil's advocate and gets Ben to justify a mode over operation that seems to be - at times - in opposition to his company's larger goals."
date: 2022-10-26
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="450" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/working-code/id1544142288"></iframe>

Sponsors

- [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

If you've listened to the Working Code podcast for any period of time, you've no doubt heard Ben mention the fact that he works on maintaining a **legacy platform** at [InVision][invision]. His role on the legacy team was originally focused on security, stability, and bug-related fixed. However, over the years, he's become increasingly aggressive about adding features and actively improving the legacy experience. This has caused no shortage of controversy both internally to the company, and more broadly within the [Working Code community][working-code-discord]. In this episode, Adam plays Devil's advocate and gets Ben to justify a mode over operation that seems to be - at times - in opposition to his company's larger goals.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[invision]: https://www.invisionapp.com/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/098-in-defense-of-working-on-the-legacy-platform.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** The cost of building a legacy is having a legacy platform. And, and that kind of struck a chord to me. It's like, the way I interpret that is, in order to build your legacy, you have to not forget about the people who, allowed you to build that legacy. and, and that's, and that's how I look at the legacy platform is I don't wanna forget about these customers.

## [00:00:21] Intro

[00:00:21] **Adam:** okay. Here we go. It is show number 98. And on today's show we are going to discuss Ben's Persistence, I guess, at working on the legacy platform. maybe, maybe it's a defensible position, but, I'll be the judge of that. episode 98. Can you believe we're almost at a hundred? It's almost time to punish ourselves with those wings. both at the same time. Looking forward to and terrified of

[00:01:01] **Ben:** I'm, I'm a little afraid that I'm actually gonna get hurt. Like, I'm like something, I'm, I feel like having a heart attack is not off the table, just cuz I can't stand so.

[00:01:12] **Adam:** Should have paramedics standing by. Just dial nine one and wait. Oh, okay. But, first as usual, we're gonna start with our Travis and fails. as you can probably tell Carol and Tim are not with us this evenings, just myself and Ben once again. hopefully those two will be able to, uh, Account for themselves. When they return, we'll, we'll put their feet to the coals and see what they have to say for themselves.

[00:01:36] **Adam:** But in the meantime, you get just us. So, uh,why don't you go first, Ben.

## [00:01:41] Ben's Triumph

[00:01:41] **Ben:** All right, I'm gonna kick it off with a triumph. It's a small triumph, but I'll take it after last week's, failure. so I have this new fancy space, Gray M one, fully packaged Mac, and, it's just sitting there doing nothing because I can't actually run all my Docker stuff on it yet. So I've been, working on and off with Mark Drew friend of the show on getting all of the Docker stuff running on the M one and, Basically he's, he's kind of giving me this Docker file that, rebuilds the Lucy container based on the Lucy Docker repository.

[00:02:17] **Ben:** So it basically runs the build that they would run. But I'm running it locally, so it runs under the, the arm processor. That's my understanding. I'm saying a lot of words that I don't fully understand yet. Anyway, we got it to a point where it was actually starting to run the Docker file and it ran into this thing that said, Phantom JS package not found Phantom js My understanding is it's sort of like a headless browser that people can run the tests in, and apparently they don't have any compatible version of it that runs on the M one or the arm, and any phantom js.

[00:02:51] **Ben:** Repositories that you go to, they're all marked as archived from like six years ago. So I went in and I ripped out phantom js and then ripped out anything that seemed to make a reference to phantom js, something called Karma. I think karma's also like a testing related framework. I had to go in and ripped that out of our C I C D system.

[00:03:09] **Ben:** we, we still have some tests. There's some MOCA tests or something. I'm not a big testing person, so I don't really even understand what some of these things are doing, but I ripped them. and nothing exploded, which was kind of exciting cuz I'll tell you, when you look at a package, json file and you're looking at your dependencies and there's like a thousand dependencies, It.

[00:03:28] **Ben:** I don't know if there's some sort of special tool you can run to say whether or not these are being used or how they're being used, but it's very daunting to go in and figure out what you can, what you can kill. Cuz like, let's say Phantom JS had a peer dependency, or Karma had a peer dependency, and now I've removed Phantom js and Karma.

[00:03:46] **Ben:** Now do I have leftover crush that's being installed, but nothing's actually using it? I, I don't know how to answer that question effectively, but. I'm at least pleased that I, I got phantom js out and I'm looking forward to spending some time seeing if I can get the rest of that Docker file to run.

[00:03:59] **Ben:** Cause I really, really, really wanna get off this MacBook Pro 2015.

[00:04:05] **Adam:** So when you say you're ripping phantom js and. Out of your docker container build that's not, you're not changing like the, the official Lucy image itself, like rebuilding it from scratch. Without those things, you are removing those things from your company's like, use of the Lucy container.

[00:04:23] **Ben:** Yes, correct. So we have a Lucy image that we run. And essentially what Mark is having me do, again to my understanding here, cause I'm like a pretty novice when it comes to Docker, is I'm building the official Lucy EngineX container locally, and then it gets cashed using the docker path or whatever, like the image name.

[00:04:49] **Ben:** It gets cashed locally using the image name so that when our work Docker file then runs and says, Hey, pull from Invision. Slash Lucy, it's pulling from the cash, which is the thing I just built. So there's been all, it's been a series of things that had that happen in order to get it all to work on, on the M one.

[00:05:09] **Ben:** And again, I'm, I'm not even there yet, but, I'm hoping that this phantom js is the last of the hurdles before I can actually get the app running. Effectively.

[00:05:19] **Adam:** And this is only for the legacy platform.

[00:05:22] **Ben:** Yes, the, the modern platform.

[00:05:25] **Adam:** I guess they're

[00:05:26] **Ben:** They don't, Yeah, they don't, they don't use loosey, but they also, they don't do a tremendous amount of development locally on the machines. I think it depends. So it's, there's, there's like, there's camps of people who are doing primarily front end work and I think what they actually do is just run all the stuff on their host and then they have this some sort of fancy system.

[00:05:49] **Ben:** They can run sort of a, like, almost run the production app, but have it used their local version of all the JavaScript files and the css. I don't, it's some sort of magical something or other. so they don't even have to have a huge system running locally. Some of the server side teams, they actually do development in e c two instances, so they're, even if they're on M one max, they're actually working.

[00:06:14] **Ben:** On Intel based EC two instances and then doing some sort of, again, magic that I don't understand where they, I don't know if it's through some sort of like enro or whatever that thing is called where it's like they create some sort of magic tunnel between their code and the EC two system so that the C two system is running and their editing code locally, but only for like a small portion of the system it the local develop.

[00:06:40] **Ben:** Story for the new platform has had a long and very, very contentious and often, maddening path from what I've understood. So e C two has been how they solve that problem.

[00:06:54] **Ben:** Yeah. Interesting and expensive. so that's me. what about you?

## [00:07:03] Adam's Triumph

[00:07:03] **Adam:** So I'm also gonna go with a triumph. and I know I mentioned many weeks ago now, that we got a new dog and that unfortunately she has heartworm. And so we've been going through the treatment with that and has been very difficult. And like at times even kind of depressing cuz you can see she, you know, she's a playful, you know, kind spirited just like super chill, but also super happy and, and playful dog.

[00:07:32] **Adam:** And it, it kind of breaks my heart to like, have to, you know, I, I, I'm gonna say keep her chained up, but that's not it. You know, like we, we give her some leash and, and whatever. The limitation is she's not supposed to like get her heart rate up, cuz that could kill her effectively. in a little bit of a roundabout way.

[00:07:50] **Ben:** man, that's the hardest.

[00:07:51] **Adam:** Yeah.

[00:07:52] **Ben:** Lucy has been through a number of things, and that has historically been the most challenging, is she wants to do something and she's not allowed to, and she gives those big, sad eyes like, Why are you depriving me of everything that's good in life.

[00:08:06] **Adam:** I still, I still crack up over the idea that both of our dogs have the same name and, and neither one is the, the C FML platform that we both have experience with. yeah. So, the triumph here is that, the treatment is basically over almost there. I, I think like at the end of this week, she'll be done and then at that point we can start to slowly introduce a little bit of a, like, we can walk.

[00:08:30] **Adam:** Two houses down to the end of the street and back, you know, and, and just start to introduce a little bit of exercise into her routine. And, tonight with some supervision, we like let her off leash inside the house and just kind of gave her free Rome to just like, you know, have some freedom and. She instantly was like, kind of going crazy. So we have to like, kind of like stop her, hold onto her, be like, I know this is awesome, but you know, like, bring it in, bring it in. Calm down.

[00:08:57] **Ben:** Have you had any issues with the FedEx deliveries or the post postal worker and knocking on the door? Does she go nuts? That kind of

[00:09:05] **Adam:** no, not, not too bad. every once in a while, yeah, she, we don't, I mean we do, Like Amazon Key. So they'll put stuff in the garage or,

[00:09:14] **Ben:** Oh, that's

[00:09:15] **Adam:** Um, yeah, and I think typically FedEx and UPS mostly just leaves stuff on our step and, and, maybe ring the doorbell and my, my other dog will bark and go crazy for that.

[00:09:25] **Adam:** But, Lucy's been pretty low key about it. I think she might, you know, one or two barks, but she doesn't like get all worked up over it.

[00:09:32] **Ben:** Nice life is saving her own life.

[00:09:35] **Adam:** Yeah. Really. So yeah, like the, the real triumph fear is gonna be in a, in a week or two when I can like, take her to the dog park. Oh. And we're, we're putting in a fence. So our, we bought a house, I don't know, 10 years ago. and it's got this nice big yard. There's, there's, woods behind my house. And, we've kind of just decided to keep it open when we bought the house, cause our kids were, were really young and we wanted them to have the opportunity to like run all the way around the house or ride bikes around.

[00:10:04] **Adam:** And it's got a big hill, It's got like a walkout basement situation. and so we, we didn't put up a fence and we've been using, we call it a tie out for our other dog. We just have a, a steel cable. Attached to the bottom of the deck stairs and, and it reaches up to the back door and he can get like that length of cord away from the deck to, to go to the bathroom or whatever when we let him out.

[00:10:26] **Adam:** Well, we're having a fence installed. and that should be done like the week of Thanksgiving. And man, that's another thing that's just so exciting for me, just the idea of being able to like, let her out in the yard and watch her have fun or go, you know, throw a stick or a ball for her, like it sounds so cheesy.

[00:10:44] **Adam:** I get to play with my dog is a triumph, but at the same time, like we've had her for two months now and change and we've had to just try to keep things so low key for that entire time. It's, it's kind of depressing.

[00:10:59] **Ben:** Yeah, I totally get it.

[00:11:01] **Adam:** So,

[00:11:01] **Ben:** I totally get it. Well, that's awesome.

[00:11:04] **Adam:** yeah. Thank you.

## [00:11:06] The Legacy Platform Rundown

[00:11:06] **Adam:** So, I hear you work on the Legacy platform.

[00:11:10] **Ben:** I've hinted, I've hinted occasionally, but I work on a legacy platform. So this topic came up because, as I've mentioned many times, I work on the legacy platform and in the last show we had talked a little bit about when I'm actually gonna move over to the modern platform. And this, precipitated some chat.

[00:11:28] **Ben:** Almost the morality of working on the legacy platform in terms of the, the company's wellbeing and the company roadmap and, and the, the value add

[00:11:37] **Adam:** And

[00:11:38] **Adam:** when you say chat, you're talking about our Discord.

[00:11:40] **Ben:** yes, and the Discord chat. Check it out on the Discord chat. And, it is interesting. It is not, the first time I've heard that kind of talk.

[00:11:48] **Ben:** That's the kind of stuff that I deal with actually at work, and I've been dealing with it for a long time. So I thought maybe it would just be interesting to. Go a little bit more in depth into my perspective and some of the discussions that I've had previously and, and maybe try to reconcile that with, with some of the perspectives that we're seeing in the chat as well.

[00:12:06] **Adam:** Yeah. And, and I mean for, for the benefit of the listeners and for the people that we're chatting about at Discord, maybe I'll try to play a little bit of like devil's advocate on their behalf.

[00:12:17] **Ben:** Yep.

[00:12:17] **Adam:** I'll I'll try to represent their opinions or whatever, that sort of thing.

[00:12:20] **Ben:** So let me, let me try to give you the elevator pitch on how the legacy platform and the modern platform came to be. and I hate to say this, but I do blame a lot of this on anti ColdFusion mentality. So the legacy platform is built on ColdFusion, as I've talked about before. And, we had a bunch of engineers working in a relatively small applic.

[00:12:43] **Ben:** We grew very fast as a company. I think we grew far too fast as a company and we ended up just, I think having too many cooks in the kitchen. And, everybody was stepping on everybody else's toes, you know, literally having multiple people on different teams working in the same file occasionally, and that's just recipe for disaster.

[00:13:03] **Ben:** And then there was all kinds of a talk about maybe trying. Cut off little bits of the application to help deal with, some processing problems. And then microservices were becoming much more a, a thing that people were talking about. So there was just, Oh, maybe we should try to figure out maybe where we can cut some of this up. And, What happened was some of the engineers had to recreate logic that was in the monolith, in the microservices that they were working on, or really just like the one or two microservices they were working on, and that was incredibly challenging for them. Like the lingly challenging when you, when you consider that cold, the ColdFusion application is actually fairly straightforward.

[00:13:43] **Ben:** I think a lot of co fusion applications tend to be fairly straightforward. There are a lot of database access and view rendering that's. The bread and butter of what ColdFusion does really well. And, and they just, they like couldn't get the queries to line up, which again, like I don't understand that.

[00:14:00] **Ben:** Like you just look at the SQL queries that are running in one place and you rewrite them somewhere else. I don't understand. Why was it challenging? So anyway, they were struggling and one of the guys who was involved in this sort of a separation workflow went to the CTO and said, Hey, the reason that we can't get this working, Is ColdFusion.

[00:14:19] **Ben:** ColdFusion is terrible. Everybody hates it. it's complicated. it's, it's bad. It's making us bad programmers. I don't know. Like I'm oversimplifying here and I'm painting with an extremely broad brush. but essentially it was a lot of anti ColdFusion hatred that, dovetailed with the CTO at the time who I think was very excited about doing microservices and very excited about Go Lang. Which was becoming more popular as well. Anyway, long story short, they decided to start breaking up this monolith, not not breaking up, they decided to start recreating this monolith in a bunch of Go Lang and no JS services. And at the same time, they were also completely changing the database structures cuz one of the key stones of the microservices architecture is that microservices own their own data.

[00:15:09] **Ben:** So, Sean Corfield on the chat. One of the things that he was talking about when he was migrating systems on his end was that he would keep the same database and essentially rewrite the code that was calling the database way easier. cause you don't have to migrate data, you're just sort of changing the things that, that are, that are interacting with it.

[00:15:27] **Ben:** We completely split up the databases, completely split up all the services. So now you have services talking to other services in order to get data Anyway.

[00:15:37] **Adam:** So just so we're clear, and I understand you, the, the legacy platform and the modern platform have separate databases,

[00:15:47] **Ben:** Mostly so

[00:15:49] **Adam:** even better.

[00:15:50] **Ben:** Because we knew that there was gonna be a challenging migration process to get people from the legacy platform to the modern platform. What we ended up doing was allowing the user table what essentially amounts to a couple of user related tables. Those were gonna be shared so that people could, while still using the legacy platform, start to experiment with the modern platform without having to create totally new accounts.

[00:16:14] **Ben:** And so all of this started literally like five years ago, six years ago. I don't even know what the timeline is at this point. And, people talked about in the chat here, The way we should have approached it is that all hands should be on deck to get every, all the users from the legacy platform onto the modern platform.

[00:16:35] **Ben:** And I'll tell you, for the first like two or three years, that's basically what it was. It was, it was the legacy platform was frozen, just bug fixes and security fixes, you know, things from like penetration testing and, and, critical issues found by users. 99% of the engineers were a hundred percent of their time focused on building out this new system. and, and I was, for a period of that, working on the new system, I was working on some no JS services. And then they actually pulled me back into the legacy platform and said, Hey, we can't abandon the legacy platform. Like there are users complaining that certain things aren't working. Like we need to have people.

[00:17:20] **Ben:** Working on the legacy platform that actually know and enjoy working with ColdFusion. So I was like, Yeah, of course. I love ColdFusion, I love users. Let's do this. Let's make it happen. So I went back to the legacy platform and towed the line. You know, did the bug fixes, did the, did the critical things, but, but basically was in maintenance mode. And that went on for a while. And at some. I, I just like, I was mad as heck and I wouldn't take it anymore. which is that we have these users, they're paying us, like they're paying customers and they're on the legacy platform. And we basically just started ignoring them from my perspective. And I could not let it stamp.

[00:18:02] **Ben:** so I started arguing. We have to do something, we have to start adding value to our customers' lives. It, it's unfair for the system that they're paying for to stagnate so heavily

[00:18:13] **Adam:** For years. Yeah.

[00:18:15] **Ben:** for years and, and to address some of the things that people brought up in the chat, You couldn't just migrate yourself there.

[00:18:21] **Ben:** There's, even to this day, there's no self serve option for. Moving your data over to the, to the new. And, and in fact, even today, if you wanna get on the new platform, there's no guarantee that your data will ever actually get to the new platform. we have our enterprise customers and our non-enterprise customers.

[00:18:39] **Ben:** All the enterprise data has been prioritized, and that's gonna go to the modern platform, but non-enterprise be because the data structures are actually quite different for non-enterprise, which, you know, talk about mistakes that we made eight years ago.

[00:18:53] **Ben:** That's one that continues to haunt. it would have to be a completely different migration process for them and the team that's doing all the migration, just, I mean, it, it's taken them like six years to get the enterprise data migrated properly. The idea of doing the self-serve, the non-enterprise is, is a, it's, it's just a non-starter. So it, it, you know, I think to say that it should have been all hands on deck to get everyone over to the modern platform. Is essentially what was happening and, and essentially continues to happen with the exception of me, Right? I'm one engineer, and, and, and you know, not to say that I'm the only one who's ever worked on the Legacy platform for the last couple years.

[00:19:35] **Ben:** We had about three engineers working on the legacy platform full time, but for the last year. So it's been exclusively me and,

## [00:19:43] Comparing Development on Legacy vs Modern

[00:19:43] **Ben:** And I, and I do it, I do it for several reasons. One, I absolutely love our customers and I think the way we've treated them has been very unfair. and I wanna do what I can to add value and if that causes friction between the legacy platform and the modern platform, to some degree, I'm. Don't make your problems my problem, like the company has made decisions that has put us where we are, but don't make that a limiting factor for how I can treat our customers. and also I know this, this, so this is maybe sounds crazy and is maybe not the right attitude to have, but I continue to work as a solo engineer on the legacy platform because, I think it provides a good juxtaposition between the old architecture and the new architecture.

[00:20:32] **Ben:** What I mean by that is when I can go in and build something on the legacy platform in two days and the people on the modern platform look at that and say, Hey, we can, that'll take us a couple of weeks to build, or a couple of months to build, or we literally can't do it right now because other teams would have to go build APIs to provide that data.

[00:20:53] **Ben:** Before we could even do something like this, like I think that sends an interesting message to the company. Like, people need to see that their architectural decisions and choices have consequences. And when I can build stuff as an individual, then I think it helps to put everything in perspective. And I'm, That's not to say. That I can build everything that they're building on, on the new platform, the new platform's much more robust and is all event based.

[00:21:22] **Ben:** And, and they have some very cool stuff that happened and I can't do that, but there's some stuff that I can do that they can't do. And I think it's important to sort of keep all that in mind all the time. So, so that is part of why I, I continue to do what I do.

[00:21:38] **Adam:** Do, are you kind of hoping that this would inspire, like in a best case scenario, it would inspire them to take a step back and, and maybe think about things that they've made? Too complex and try to simplify so that they can, for example, build a feature like that in a day or two.

[00:21:56] **Ben:** The, Yeah, I, I think that would be, amazing. I mean, and I, and I think that's part of what I've been hoping is. I can keep up a cadence. the, So I work on a team called the Rainbow Team, and I've been on the Rainbow team now for like five years or something. and we have this phrase rolling thunder, that, that sort of the cornerstone of the, of the rainbow mentality has always been rolling thunder, which is this idea of small releases.

[00:22:23] **Ben:** So that you can say, Hey, I released this, and then two days later, hey, I released this. And then two days after that, hey, I released this. You get this kind of like just stream of small but continuous improvements to the application. And part of why I believe that the Rainbow team has been capable of rolling Thunder is because of our historical architectural choices.

[00:22:44] **Ben:** On the legacy platform, it's monolithic. It's got more or less a single database. it's very easy to reason about for the most part. And having all of that, you know, in top of mind allows us to move with a lot of agility, which is kind of, contradictory to I think what a lot of people think of.

[00:23:04] **Ben:** When they view a monolithic system, right? If you listen to a lot of podcasts and they talk about monoliths, the thing they, they talk about is it's so hard to change anything. You, you touch something here and something way over there, unrelated breaks. it's this big ball of mud. And, and I like to demonstrate that at least in our application, it's exactly the opposite.

[00:23:26] **Ben:** The monolithic properties are what allow. The legacy team, which is now really just me. It's what allows us to move so fast and, and be so agile and do a little improvement here. Then do a little improvement there, and then do a little improvement over here. And I'm running without tests. And we've talked about that before.

[00:23:45] **Ben:** And, and again, tests are more important when it comes to teams, I think. So being an individual sort of negates some of that, that, that problematic decision.

## [00:23:55] Platform Feature Parity

[00:23:55] **Ben:** But, You know, one of the, one of the arguments that I used to get into with my manager who was no longer at the company, he would say that, it's unfair to users that you build something on the legacy platform and then eventually they move to the modern platform and that thing isn't there anymore. For whatever reason, that's never connected with me. And it's, and I've, it's been hard for me to find a parallel where I can say that that reasoning makes sense. you know, some of the metaphors or the analogies that I've used are, franchises. Like, imagine that I was running a franchise and that franchise represents the legacy.

[00:24:35] **Ben:** And my franchise was gonna shut down in six months. And so then all the customers who came to this franchise location would have to start going to another franchise location. Would I spend those last six months not caring about my customers or. Would I continue to find ways to innovate and, and, and add value?

[00:24:53] **Ben:** Like, Oh, maybe I can have a free,cucumber water or something, or like four o'clock cookies at this franchise location. Like, does it matter if none of the other franchise locations have four o'clock cookies? Is that a reason for me to not do it And that it was, I could just never come up with anything where someone could convince me that having to move users off of the platform was reason to not do anything for them. And so maybe it's a communication problem. I don't know.

[00:25:21] **Adam:** It's becoming very difficult for me to play devil's advocate because I feel like you're making a very strong case for your positions here

[00:25:28] **Ben:** So some of the frustrations that my coworkers have expressed to me are, I'm creating parity gap issues, meaning that I'm creating features on the legacy platform that don't exist on the new. and, and my counter argument to that is, one, you've already done that. We've already done that as a company.

[00:25:48] **Ben:** We've already decided there are things in, in, in the modern platform that we don't wanna replicate regardless of whether or not people are using them on the legacy platform. So, so that's already an issue whether or not I exacerbate that issue, two. A lot of the times it's probably not gonna be a problem cuz a lot of the stuff I build is crap.

[00:26:05] **Ben:** So if I build it and it's crap and users migrate to the new system and they don't care that it's not there anymore, like no harm, no foul or three, I build something interesting on the, on the legacy platform, people migrate to the new platform and then they freak out because, hey, where's this nice thing that that you guys built on the legacy platform?

[00:26:25] **Ben:** It's no longer here. That's really disappointing. And my perspective on that is, that's awesome because now you know that users actually want it. And how many times do we end up building something that users didn't want? And now you have users actually telling you that this is something that they want.

[00:26:41] **Adam:** I feel like it's a, at least three times a year that we get some. Customer driven. Like, I don't, I'm not gonna say customer mandate, but you know, a customer just like throws a temper tantrum and it comes down from like their vp, like, we absolutely have to have this feature. And it's not just like, you know, we need to be able to change the background color of the page.

[00:27:02] **Adam:** It's like, oh, we need you to build a crowdfunding platform, right? Like this is not small potatoes. Right? And and so we're like, fine. Okay, we'll do it. You're a big customer, you give us a lot of money. We'll build the thing that you need to keep you on our platform, and we do it. We spend like six months for two people, if not more than that.

[00:27:23] **Adam:** You know, build this thing like it works great. It works exactly as they requested, and they never use it like the, we'll, we'll catch up, We'll catch 'em like a year later doing the halfass thing that they should have done in the first place. With like, you know, some features that had already existed and it's infuriating.

[00:27:46] **Ben:** I used to work at a place and, we had a, we had this customer and he was like the technology side of this company that we were working with, and he had a lot of product people that he was interfacing. He was basically like the liaison between our two companies. And, he kept using the phrase, Hurry up and wait.

[00:28:03] **Ben:** He's like, My people are screaming at me for you to build this. And he was like, Just be prepared though. When you build it, they're not gonna use it because they just want to know that it's there. They don't care that, they're like, but he's like, Just manage expectations. You gotta hurry up and wait.

[00:28:17] **Adam:** It sucks though, like yeah, I'm very familiar with the phrase and, it's when you, when you can see it coming and it's like a, it's a freight train. You can't stop it from coming. But it's still, you know, you know it's gonna suck. You could see it sucking. It sucks when it arrives and there's nothing you could do about it.

[00:28:38] **Adam:** It's just have you seen The Good Place,

[00:28:40] **Ben:** Yeah. Yeah,

[00:28:41] **Adam:** relatively early on in, that show, They do the, the trolley problem, They'd like discuss it and they put him on the trolley and, you know, he can see it's coming and, and, and he keeps getting splashed with blood and it's just, he's like, just disgusted and, and just freaked out and, you know, he has to do it over and over and over again.

[00:29:01] **Adam:** And I feel that way sometimes.

[00:29:05] **Ben:** Somebody had just posted a meme on Facebook. One of my friends on Facebook posted this thing about Batman, and they were like, Why didn't you just kill the joker? Jokers running around killing everybody and, and you could just kill him and Batman's like, if I killed him that I would, I I would just, I'd be the same as him.

[00:29:24] **Ben:** And the next frame is like, let me tell you about the trolley problem. So, so one of the other constraints that I have on the legacy platform, which I've mostly agreed to, but I've, I've as of late, been straying from it a little bit, is that I can't create new types of data. Because it's not a shared database system. So if I create a new table or if I add new columns to an existing database table, the team that's managing the migrations would then have to figure out how to move that data into the new system. So for the last like three years, I've been building new features, but it's really just new views into existing data. I haven't created any new data. I've just said, Is there something interesting about this data that I can. That I could bring to the surface or can I reshape this data to make it more consumable or accessible for the customers?

[00:30:17] **Ben:** And to me it's like that's, that can create feature parody issues between the platforms, but it's like the easiest types of feature parody things to deal with. Because I'm basically like, you can almost literally go into my code files and copy and paste them and then just translate them into whatever language you're using because I'm not adding any data.

[00:30:36] **Ben:** I'm. I'm just rearranging the, the records that I'm getting back from the database. so I, you know, I don't want people to think that I'm, I'm like going completely rogue and, and, you know, kicking down doors and jumping with guns blazing. Like I've, I've been operating under some significant constraints and even within those constraints, I feel like, Finding ways to add value to the customers.

[00:31:02] **Ben:** And at the end of the day, again, like that's my whole thing is I love my customers and I want my customers to be happy and they've been underserved for a really long time. And I feel like I'm in a position to do something about that in my own limited way. And

[00:31:15] **Adam:** Yeah.

[00:31:15] **Ben:** if that creates a problem for the new platform, like that's not my problem.

[00:31:20] **Adam:** I mean it is, but,

[00:31:22] **Ben:** It is. Yeah. Yeah. It isn't, But it is

[00:31:24] **Adam:** I take your meaning. Yeah.

## [00:31:25] Legacy Platform EOL

[00:31:25] **Adam:** So, you probably can't get into specifics of how many people, or you shouldn't, how many customers are still on the L platform, But can you give like ballpark or percentage of overall customers or,

[00:31:35] **Adam:** order of magnitude,

[00:31:36] **Adam:** raw number

[00:31:37] **Ben:** our intention is to be done with the migrations by the end of the year.

[00:31:41] **Adam:** by the end of 2020?

[00:31:42] **Ben:** yes. so for people listening, that's like two more months,

[00:31:47] **Adam:** yeah.

[00:31:47] **Ben:** two and a half months. And, and I think we're on track. I mean, I'm looking at the numbers in our, in our all hands meetings, they talk about the amount of ARR and annual recurring revenue that's on the old system versus the new system.

[00:31:58] **Ben:** And the trend is such that I think they're probably gonna make it,

[00:32:02] **Adam:** And even if they don't,

[00:32:02] **Adam:** it sounds like, you know, maybe one more month.

[00:32:04] **Ben:** Yeah, yeah, yeah, yeah, yeah. Exactly. As we talked about on a previous show, I, I, I talked to my director of engineering about continuing to work on the legacy platform until I, we cross an ARR threshold, meaning that until a certain amount of money has been drained out of the legacy platform, I'll continue to treat it as if we have paying customers because we have paying customers on it I don't know when that threshold gets crossed. So, and, and the reason I say that is because as I mentioned earlier in the show, the enterprise customers are being migrated. The non-enterprise customers are not, which means that if non-enterprise customers want to get onto the new platform, they basically have to opt into it and go and, and, and sign up on the new platform.

[00:32:51] **Adam:** But they could do that at any time. Right? And do they know that, You know, that's their only option.

[00:32:56] **Adam:** do they know that there's no way for them to get their data over there?

[00:32:59] **Ben:** I'm not a hundred percent sure. I don't, I I think, I don't know how clearly that's been communicated. I think it's been communicated. I'm not, I'm not entirely sure. but what that means is that there is some number of users who are living on a legacy platform until they choose not. Or until we literally turn it off, meaning that there is a, there is an option on the table where we could, either just not renew, like not allow plans to be renewed on a legacy platform, or if we so choose to, we could get even more extreme and we could buy out contracts. So if you have an annual subscription and, and that's another six months, we could just refund you six months worth of, you know, a prorated amount of your plan and say, I'm sorry that.

[00:33:44] **Ben:** We're literally taking the system offline in two weeks. I'm, I, I don't think we're gonna do that, cause that seems financially burdensome, but, it's, it's, it's not off the table in terms of the conversations that I know people are having.

[00:33:57] **Ben:** So, I don't know. It's all very emotional.

[00:33:59] **Adam:** Let me ask you this, If I'm to play devil's advocate, let me ask you this, the ARR target that you said you would use to, as your signal to, to move off the legacy platform. Hopefully that is higher than your salary

[00:34:12] **Ben:** Yes, it's higher than my salary and it's higher than what it would take to keep the legacy platform running.

[00:34:19] **Adam:** Okay. Like the operational costs?

[00:34:20] **Ben:** Yeah, yeah. As as far as I understand. I mean, it's. it's a non-trivial amount of money.

[00:34:26] **Ben:** I mean, it's dwindling every day. Let me put

[00:34:29] **Ben:** it that way.

[00:34:30] **Adam:** Which is, I mean, ultimately that's the goal, right? Is get everybody migrated the new thing, and, and that frees you up to contribute to the modern platform.

## [00:34:38] Ben's Role on the Modern Platform

[00:34:38] **Adam:** And maybe your thing in the modern platform can be going around and, helping if, if it's process improvement or if it's, you know, or, or whatever to, to help them, you know, be a little bit more nimble and able to, get

[00:34:52] **Adam:** small wins quickly.

[00:34:53] **Ben:** it's interesting because this is the conversation that I've had a number of times with various, like director level people, is, is they say, you know, I think they placate me a little bit. They're like, Hey, we love what you're doing. We love the enthusiasm, we love the cultural leadership, right? and they say, But wouldn't it be great if you could bring that over to the new system and, and like, bring that magic and that productivity over to the new system?

[00:35:19] **Ben:** And what I tell them is, The magic comes from the legacy platform. Like, yeah, I'm excited to be a programmer and I'm excited to solve problems for our users, but a huge part of why I'm able to be productive is one, first of all, nobody cares what I'm doing. Like I have no oversight. I have no manager. So like that gives me a certain degree of freedom, but do it architecturally.

[00:35:45] **Ben:** It's a significantly simpler system and it's, it's, it's a, there'd be no way for me to. You know, lift and shift that magic into a new system that's significantly more complicated.

[00:35:59] **Adam:** I think that you might be underselling it a little bit. I think that your perspective, right? You, you would bring that perspective and say like, Well, but if I was still over there, I could get this done today. And what is, what is in the way of that over here? And does it have to be that way? And what can we do to improve?

[00:36:19] **Adam:** The process that we have to go through here, why does it have to be that way and what can we change to make it more agile and nimble? You could be like the productivity consultant,

[00:36:32] **Adam:** You have to change your

[00:36:33] **Adam:** name to Bob.

[00:36:33] **Ben:** couple just start slashing processes. yeah, I, I, it would be interesting, I don't know really how the, the new platform is run, even just from a cultural, like a team and cultural standpoint. I, I, I assume they have more process in place simply cuz they have more people and they have more layers in, in their side of the organization.

[00:36:51] **Ben:** They have a lot of, of more I think consensus building. Where you can't just run with an idea. Your idea has to be run by people before it can be put into action. so, and then they have, you know, have to prioritize stuff and weigh the pros and cons of building this versus not building something else.

[00:37:07] **Ben:** I, I bypass all of that because it's like, I wake up one day and I'm like, I wanna work on this. And then I finish it and I'm like, I need a break, so now I'm gonna work on something entirely different. Like there's really. There's no roadmap. I got no roadmap, right. I'm living on borrowed time. And that's kind of the exciting part too, is, is, it, it, it's like at any moment all of this could be taken away from me.

[00:37:27] **Ben:** and, and so I have to, I have to work on things that are relatively simple. So I have, you know, I talked about the constraints. I can't really create new data. Because that would blow up migrations. I can't build anything big because I don't know if I have time to build anything big because I don't know when all of this is gonna be taken away from me.

[00:37:45] **Ben:** And so I'm, I'm just like, just operating as fast as possible and, and the smallest feedback loops as possible, and I'm having a great time.

[00:37:54] **Adam:** It's kind of very, like, in a way it's, it's kind of Zen Buddhist, like, there's a video I saw where, a Buddhist was like talking about, you know, not just a Buddhist, but like a monk. I was talking about like a, you know, a morning routine. And one of the things is to contemplate death. That's like a step in this morning routine.

[00:38:14] **Adam:** Like this day is not guaranteed. Right. It's a. You're, it's a privilege for you to have this day. And what can you do to capitalize on the fact that you're alive today?

[00:38:25] **Ben:** totally. I, I, I think that's, it is a big part of how I approach my day, or at least my week, you know? it's, it's also really interesting that because I don't have managers, nobody is feeding me information. So part of how I find inspiration on what to work on, Is I'm constantly in various Slack channels that are support related or that are sales related.

[00:38:50] **Ben:** I'm looking to see like, oh, I was just on a call with a customer and they said such and such about so and so, and I'm looking for, is there something there? Like, can I tap into whatever that customer just said as a source of inspiration or, you know, I'm combing through our Zen Desk tickets to see if there's something interesting there.

[00:39:05] **Ben:** So I've, I've been forced to sort of have my finger on the pulse. As much as an individual can of the company so that I can draw inspiration from somewhere. Otherwise, I'm basically just living entirely in a vacuum. So that's, it's, it's, that's like stressful because it, I, it, it would be just in a way easier to have things hand fed to me and I could just move tickets across a board.

[00:39:31] **Ben:** But because I have to sort of create my own backlog. The responsibility of creating and curating a backlog is, is left up to me. Then I, I have to be a, you know, a man about town trying to find, things to do. I dunno. At the end of the day, I have customers and you have to have an incredibly persuasive argument for me to not care about those customer.

## [00:39:58] Adam Sums Up

[00:39:58] **Adam:** Sure. Okay, so I wanna summarize a little bit. Let's see if we can kind of pull this all together. It's going away soon, like we've got a, a very real timeline on it now. When we started this podcast over a year ago, You were on the

[00:40:11] **Adam:** legacy system, but it

[00:40:12] **Ben:** away soon.

[00:40:13] **Adam:** Yeah, but, but it was, the timeline was s o o n ,

[00:40:18] **Adam:** right?

[00:40:18] **Adam:** Like we don't know for sure. And now you've got, possibly low single digit months remaining. And you've got some number of customers That have been on a legacy platform for years. Postmodern platform being a thing that was available to them. And it sounds like your, your

[00:40:37] **Ben:** sorry, just to clarify though, when you say modern platform being available to them, The, it's a, it's a, it's a tough thing only because I don't know how many users are educated about the existence of the new platform or, you know, cuz on the inside it's really easy to see that it's a completely separate product.

[00:40:58] **Ben:** But from the outside, people see Invision and they're like, What do you mean new platform versus old platform? Like, I pay for Invision. so it, it's, it's hard to understand what the customer's perspective on. Two system reality.

[00:41:13] **Adam:** Yeah. Okay. and then, yeah, and it's not that they, in most cases, have made the decision to stay on the legacy platform. They just haven't been pulled to the, the modern platform, whether. By choice or kicking and screaming. and then it sounds like your philosophy is kind of like, these people are spending on our product.

[00:41:32] **Adam:** We should give them something for that money other than security updates and critical bug fixes.

[00:41:39] **Ben:** Yeah, exactly.

[00:41:40] **Adam:** I don't think I can argue with that. You know, especially knowing now that we're looking at single digit months remaining. I think with single digit months left, personally, if I were in your shoes, I think I would be kind of coasting . I wouldn't be trying to, you know, do too much experimentation unless it was something I was passionate about, right? Like some feature idea that I had that was like, Ooh, this whole, you know, like it's an opportunity to user test something and, and, you. It sounds like you, you do a lot of that, right? You put something out there and see if it sticks.

[00:42:13] **Ben:** Well, it's, it's funny, I do think I, so I was just handed a project for the legacy platform from, from the product side, meaning someone asked me to work on this. This isn't just me. A little bit of me feels like, someone just, it's like a, like Bitcoin mining. Like someone just gave me a lot of work

[00:42:32] **Ben:** that's gonna consume my CPU so that I don't work on other things.

[00:42:36] **Ben:** but I am going to try to stay vigilant about not letting that consume a hundred percent of my time, cuz part of my whole work philosophy is nothing consumes a hundred percent of my time that. That I have built into my schedule wiggle room so that I can try a little of this and try a little of that.

[00:42:56] **Ben:** Even if I have one thing. That's my main focus for some period of time. Even within that period of time, I, I do some, some shifting in terms of my focus in order to, you know, just keep the brain fresh a little bit so you don't. but you know, I've been having these conversations, I've been having conversations like this for, for over three years. So if, if you can imagine, this is something I said in the Discord chat, like I was one engineer. It's not like I'm 50% of the workforce and I've chosen not to work on the new platform.

[00:43:30] **Ben:** I'm a tiny percentage of the workforce and I'm continuing to work on the legacy platform. And if I had decided not to do that three years ago, we wouldn't really be any farther forward in, in terms of the migration cause it's, I'm, I'm, I wasn't holding anything back. So instead you would just have a platform that was completely stagnant for a very extended period of time. I, I, I just, I, I can't imagine ever feeling good about that I can't imagine feeling like that was the right decision for the customers.

[00:44:07] **Ben:** Again, you'd have to have like a very persuasive

[00:44:10] **Ben:** argument.

[00:44:11] **Adam:** yeah, I, I think you've made a pretty good case. You know, like it would be one thing if the, if you were six months into the modern platform existing and people were giving you a hard time about still being on there. But this light into the life of it, if you still have so many people on the old platform, thenyeah.

[00:44:29] **Adam:** Like Those customers deserve some attention. Whether that is the effort to get them migrated or the effort to keep the platform. Growing and evolving for them, and if they're not getting one, then they should get the other.

[00:44:45] **Ben:** Yeah, I agree and, and at one point enough customers will have moved to the new platform. Where threshold kicks in and then we no longer even have these conversations.

[00:44:57] **Adam:** then we're, well have a whole new conversation.

[00:45:00] **Ben:** Yeah, like what

## [00:45:06] Legacy And The Legacy Platform

[00:45:06] **Adam:** Cool. All right. Well, you got anything else you wanna discuss on that sounds

[00:45:12] **Ben:** Hm. No, I, I'll tell you, I, I know I've brought up the, the base camp guys a bunch of times. I'm a huge fan of theirs and, DHH said something in either, I think it was an interview, and he said, The cost of building a legacy is having a legacy platform. and. Something to that effect.

[00:45:32] **Ben:** And, and that kind of struck a chord to me. It's like, the way I interpret that is, in order to build your legacy, you have to not forget about the people who, who allowed you to build that legacy. and, and that's, and that's how I look at the legacy platform is I don't wanna forget about these customers.

[00:45:50] **Ben:** These are the customers that allowed us to build what we have today and, and they deserve to not be forgotten.

[00:45:57] **Adam:** Well.

## [00:45:58] Patreon

[00:45:58] **Adam:** This episode of Working Code was brought to you by Phantom JS. Apparently it still exists. and listeners like you, if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording and editing costs, and, we really appreciate them for it.

[00:46:18] **Adam:** and in exchange we give them early access to new episodes and our after show, which after we're done here, we're gonna go talk. I think we're gonna talk more about our dogs, uh, Lucy and Lucy. And,that's the sort of thing that you get if you are a patron of this show. Thank you patrons. Of course.

[00:46:35] **Adam:** Special thanks to our top patrons, Monte, Sean, and, sorry, not sorry. Giancarlo

[00:46:42] **Ben:** Thank you

[00:46:42] **Adam:** you'll have to let us know how to, how to pronounce that.

## [00:46:44] Thanks For Listening!

[00:46:44] **Adam:** if you wanna help us out, you can go to patreon.com/WorkingCodePod. When this episode comes out, October 26th, tomorrow the 27th is when we are planning on, recording our 100th episode.

[00:46:57] **Adam:** Spectacular AMA and Hot Wings inspired challenge. so you have one day left to get your questions in. Go to workingcode.dev, and at the top there's this big ugly, yellow and red banner with a link where you can go to ask us a. And, we hope we get a bunch of good questions in there. And I see we've got 43 so far.

[00:47:19] **Adam:** That's nice. Hopefully we'll get some good ones include in the, in the show and, yeah. leave us a question. you can join our Discord at workingcode.dev/discord. emails at WorkingCodePod@gmail.com. Send us a voice memo to the same location. Nathan Struts, I saw your rant in Discord and I, I'm now verbally, encouraging you to record that as a voice memo because that was a good rant and I want that on the show.

[00:47:45] **Adam:** Send that to WorkingCodePod@gmail.com. that's gonna do it for us this week. We'll catch you next week. And until then,

[00:47:50] **Ben:** Remember folks, your heart matters
