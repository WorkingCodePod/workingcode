---
title: "137: The Grug Brained Developer"
description: "This week on the show, we have Tim—our only host with screen acting experience—read from The Grug Brained Developer, 'A layman's guide to thinking like the self-aware smol brained'."
date: 2023-07-26
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/137-the-grug-brained-developer/id1544142288?i=1000622388533"></iframe>

This week on the show, we have Tim—our only host with screen acting experience—read from [The Grug Brained Developer][grug-brained], "A layman's guide to thinking like the self-aware smol brained". This guide uses fun, caveman'esque language to point out the challenges and missteps that we often take in software development. And, how keeping things simple - for easy _smol brain_ consumption - will often lead to better software outcomes.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[grug-brained]: https://grugbrain.dev/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/137-the-grug-brained-developer.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Adam:** so Grug, what do you think about microservices?

[00:00:02] **Tim:** Grug wonder why big brain take hardest problem, factoring system correctly, and introduce network call too.

[00:00:11] **Carol:** Oh, man.

## [00:00:32] Intro

[00:00:32] **Adam:** Okay. Here we go. It is show number 137. And once again, bucking the trend, we have everybody on the show.

[00:00:39] **Adam:** Say hi, everybody.

[00:00:40] **Ben:** Yo, yo, yo!

[00:00:41] **Adam:** Once again, they are everybody I am adam. and let's see, today on the show we are going to meet grug If you are not familiar there You know, we'll we'll save it. We'll get in later. We're gonna meet grug. but first as usual We'll start with our triumphs and failures and tim. Why don't you go first?

[00:00:58] **Adam:** This

## [00:00:58] Tim's Triumph

[00:00:58] **Tim:** Oh, I mean, it's not exciting on Call of Triumph, spent the last two weeks going 21 rounds with legal

[00:01:04] **Tim:** between two different companies. Yeah, but, finally got it done Friday. So just had to send this off to some company's board of directors to see if they'll sign off on it.

[00:01:14] **Tim:** So on the hand, it's like. It was annoying, but the other hand, it's like, this was like the first time I ever got 100% of our legal team's attention.

[00:01:21] **Carol:** Oh, wow.

[00:01:23] **Tim:** and so I could see how much we can actually get done. Because otherwise this would have stretched out for a year. So we

[00:01:29] **Adam:** is like a new feature or new

[00:01:31] **Tim:** It's a new, it's a new partnership with someone else.

[00:01:34] **Tim:** So, um,yeah, so. This is something that could have dragged out for a year or maybe longer if it had gone to normal channels. But I managed to get someone, someone with some juice to say, legal, stay on this until it's done. And I'm like, okay, we got it done. So I see what is possible.

[00:01:54] **Carol:** So once their board of directors signs off, could you tell us more about it then?

[00:01:58] **Tim:** Now, we'll have to do some product. I'll tell you about a new product that we're coming out with. And then when that's, when that's out there, I'll tell you that that was the one we were doing the legal stuff. So.

[00:02:08] **Carol:** Okay. Well, we'll know then.

[00:02:10] **Tim:** So that's, that's good. just to get that behind me. It's not how I envisioned my, my job becoming, but it's what it's become. So. Anyway, that's me. I've got that behind me. How about you, Adam?

## [00:02:22] Adam's Triumph

[00:02:22] **Adam:** So I'm going to go with a triumph this week as well. I finally got after 11 plus years, I think it is, at this company. I have a company credit card, something I've long wanted. It's pretty great. I haven't actually used it for anything yet. but for however long I've been here, you know, it's. It's always just been pay with my own credit card and submit an expense report to get, recompensated. And. It's fine at first, but then when you start doing it like for years on end and, having to

[00:02:49] **Carol:** your AWS bill is like paid on your personal credit card.

[00:02:52] **Adam:** not, not that bad, but like, you know, when you, when it gets to the point where you have to be like constantly, not constantly, but pretty regularly, like, okay, wait a minute.

[00:03:02] **Adam:** I got this recompensation check. Which things does this cover? What am I still owed? It just becomes like a pain in the neck to keep track of it all. And so, I am happy to have the card and you know, like there's only a few little things that I will use it for. other than when I travel for work, like, you know, I'll probably put my, Apple care for my laptop on there and my GitHub co pilot and other stuff that work is paying for, but that like is not travel related, which is few and far between, but So, but, I'm excited because it's going to simplify the family budget and anything that does that is a good thing.

[00:03:38] **Carol:** Oh yeah.

[00:03:39] **Ben:** up.

[00:03:40] **Carol:** But see, I always enjoyed all of the work expenses because I used it for points for flying personally. So I enjoyed the perks of putting everything expensive from work and just getting reimbursed really quickly. It only went bad when reimbursement took like three pay cycles to pay me back. And now I'm like, Oh, I have to cut this out of my own pocket now and then wait to get paid back.

[00:04:02] **Carol:** And, but usually it turned out okay.

[00:04:05] **Adam:** yeah. And I mean, you mentioned last week that like you guys have,like an airline credit card, so you get like extra miles and stuff. I don't do that, but we just do, like points. We get like a minimum of 1% cash back and, other, some, some things like hotels and gas and whatever, we get a little bit more, but, you know, long term, I think.

[00:04:23] **Adam:** We probably over the last 10 years, I think we probably made like maybe 500 bucks off of that in profit by doing my own card. So it just was not worth the effort.

[00:04:33] **Carol:** Yeah. I've made quite a bit more.

[00:04:37] **Ben:** I wonder if there are any legal. Issues around forcing, or I should say maybe around protecting employees from having to pay for things at work. I mean, I, I know in our world, having to put out the cash to do something and that get reimbursed is not necessarily a make or break issue. But I assume there are people here, if they're asked to say, buy their own uniform, that's an expenditure they literally don't have in their budget.

[00:05:03] **Ben:** Are there, are there laws that say you cannot force employees to have to pay for things?

[00:05:10] **Carol:** Yeah. I don't, I don't know about laws. Yeah.

[00:05:13] **Adam:** I mean, I have seen in the past coworkers who I knew were living kind of like paycheck to paycheck. And the idea of having to wait a pay period or two to get their expenses reimbursed is, stressful for them. And I'm super glad that I don't have to worry about that.

[00:05:28] **Adam:** I feel, grateful, man, that, that would suck. So

[00:05:33] **Carol:** Yeah. I know when I was managing people, one of the responsibilities of the management team was whenever travel was approved, that you reach out directly to your direct employee, like your direct reports, and you ask them if you can book their travel for them. That way it's not, do you need me to, but can I go ahead and book this for you?

[00:05:51] **Carol:** That way it's just all done. And most of the time the answer was, no, I'll just book it myself and get reimbursed, but then there's no awkward conversation of, I don't have the money, can you pay for it? So you just always knew when conferences were coming up or work travel was happening, you reached out to your director for us and you said, Hey, can I book your travel for you?

[00:06:09] **Carol:** And you've got, you either did it for them or they did it themselves.

[00:06:13] **Adam:** that's how you got all that extra reimbursement,

[00:06:16] **Carol:** Yeah, extra

[00:06:16] **Carol:** points.

[00:06:18] **Tim:** Carol puts it on her points card.

[00:06:19] **Carol:** I was like, we're all going to dinner. I'm just paying for that. Thank you.

[00:06:24] **Ben:** Whenever we have to do businessy travel stuff, which, you know, the last couple of years hasn't happened, but in the past where you have to, a lot of people go to hotel, oftentimes they'll ask or demand that some percentage of the people. Double up in the same room. And as an adult, I just, I can't do that anymore.

[00:06:43] **Ben:** I've reached

[00:06:44] **Tim:** Nope.

[00:06:44] **Ben:** where I need my own bathroom and I will, I will very quickly be like, what, just tell me how much I can spend and then I will make up the difference so that I can be in my own room. Cause I cannot, I cannot sleep next to other humans anymore.

[00:06:57] **Carol:** the perks of being a female engineer is that's never happened to me.

[00:07:01] **Ben:** Yeah.

[00:07:02] **Carol:** Not one time.

[00:07:03] **Tim:** Well, not in a way that you can publicly talk about.

[00:07:05] **Carol:** Sure. Sure.

[00:07:09] **Adam:** The very first time that I went to max, I basically like invited myself to sleep on the couch, of a friend who was attending and had a hotel room. It's like, Hey, you're, you're going to max, right? You got a room with a, with a couch. Okay. Can I sleep on it? Cool. Thanks.

[00:07:24] **Carol:** To be young and have fun again.

[00:07:26] **Tim:** I think that was the year I first met you.

[00:07:29] **Adam:** It might've been

[00:07:30] **Tim:** Your first max.

[00:07:32] **Adam:** so, okay. that's enough for me. How about you, Ben? What's going on?

## [00:07:36] Ben's Failure

[00:07:36] **Ben:** I'm going to go with a failure, which is that as I've talked about on the show previously, I've been working on Dig Deep Fitness, my ColdFusion fitness tracker. And I, so I went away for the weekend. I went down to Maryland for my wife's birthday. And so I wasn't around my computer for like three or four days.

[00:07:53] **Ben:** And it turns out that I had deployed a bug to, I'm going to call it production, right? But it's a very, it's like an early alpha version of a piece of software, but I had deployed a bug to production. That broke on an empty state in the most critical part of the application, which is the actual performing of a workout.

[00:08:12] **Ben:** And, I just, I, I logged in this morning and suddenly I looked in my, um.What do I use for error tracking again?

[00:08:19] **Adam:** Did you, did you send yourself nasty emails complaining about not being able to get your workouts done?

[00:08:24] **Ben:** No, but you know, I could, so it's interesting, so I see a couple people actually trying to use it, whether or not they're using it to just poke around or whether they're actually trying to use it, I don't know, haven't actually looked in the database, but I can see in Bugsnag people hitting that screen and getting an error, a null pointer reference.

[00:08:41] **Ben:** And, I just, I don't know, I felt so guilty about it,

[00:08:44] **Carol:** Aww.

[00:08:45] **Ben:** but, I was able to quickly fix it. It was unfortunately one of those things where, you know, when you build a piece of software, oftentimes you have to deal with the empty state first because you have no data and you get that in place and then you start adding data and then you start dealing with the incrementally populated states.

[00:09:01] **Ben:** And it's hard sometimes, I'd say oftentimes, at least for me, to remember to go back and explicitly test the empty state again after you've started to make more changes.

[00:09:12] **Carol:** Yeah, once you have data, suddenly it's just you kind of, your brain turns to always expecting it.

[00:09:19] **Ben:** Yeah. And I'll, I'll, you know, go out on a limb here and I'll blame Adobe CodeFusion's implementation of the Elvis operator,

[00:09:26] **Tim:** Yeah. I was going to ask about that.

[00:09:28] **Ben:** the null coalescing operator. so, so the, just as a quick aside here, the, the Elvis operator says if you have this expression and it doesn't. evaluate to a valid value, you can give it a default value.

[00:09:41] **Ben:** So it's expression, question mark, colon, default fallback value. And if the expression on the left is just a series of struct paths, like foo. bar. baz. goblamo, And none of those things exist. ColdFusion is like, yeah, no problem. I'll evaluate that as undefined and then I'll use your fallback value. If part of that expression is an undefined array index, it just blows up.

[00:10:08] **Carol:** Oh,

[00:10:09] **Ben:** which is just like a junky monkey implementation. Well, I shouldn't say that. I should say that in Lucy CFML, it just works the way you'd want it to work. And in Adobe ColdFusion, it does not. So it's, you know, I'm not saying it's a bug. I'm saying it's a less, it's a, it's a less helpful.

[00:10:26] **Ben:** Implementation.

[00:10:27] **Tim:** And I think that was due to the latest patch, right? That came out.

[00:10:31] **Ben:** I, I thought it was at first, but then I think I, I think I had deployed this book on my own because then I went back and I tried to reproduce it in an earlier build of Docker, which like, hello, how awesome is using Docker once again? Cause you can just. Essentially roll back to an earlier version of your docker image and test

[00:10:52] **Adam:** an earlier version of

[00:10:54] **Ben:** Yeah, exactly. Yeah, yeah, yeah. And then I, I got the same empty state in place and I, and I ran and I get the null pointer expression, so I was like, ah, okay, yeah, that's my fault. My bad. but I fixed it. And, moved on with my life. So So that's me. Carol, what do you got going on?

## [00:11:11] Carol's Triumph

[00:11:11] **Carol:** Well, I, I think I'm going to call it a triumph. It's, it's not, I don't know. It's not triumph, it's not a failure. It's just a fact. Like this is just what's happening and it going with it. Right. So moving day for us to move to Arizona is getting, Very close and so close that we are scheduling like our final dinner with our close people.

[00:11:32] **Carol:** So we've scheduled now next weekend, we're going to go see my parents two weekends after that, we're going to have the weekend with the boys. And then, you know, we have one weekend and then all of our stuff is packed up. So we're down to five weeks before we're out to Arizona. And it's just, it's getting really close.

[00:11:49] **Carol:** There's lots to get done, but the, the scheduling things with the most important people has been. Sad, but also like a little exciting too, because these are big steps and we're pretty, pretty stoked to see what's out west for us.

[00:12:04] **Adam:** That's awesome.

[00:12:05] **Tim:** Thanks guys.

[00:12:05] **Ben:** Are you freaking out at all about these record high temperatures that have been in Arizona or is coming from Georgia? Like whatever.

[00:12:14] **Carol:** so only a tad, but actually we're like 10 degrees where we'll be at like 10 degrees lower than Phoenix. So it's gonna be a like just a smidge cooler and let's be real. I live inside. So it's not like I ever go out if there's no water. I'm not gonna go out to do anything and apparently there's a drought and most of the pools are closed.

[00:12:33] **Carol:** But I guess there's always a drought there. I don't know. I have a whole lot to learn about living out West and you know, no grass and things. So

[00:12:41] **Carol:** the

[00:12:41] **Tim:** but no humidity.

[00:12:42] **Carol:** no humidity also, everyone's been like, you're going to hate it when you get there because your hair is not going to respond to anything you do to it because it knows nothing but to work in humidity.

[00:12:53] **Carol:** So when you go change your skin's different, your hair's different, and it's going to take a long time for your hair to adjust to the new climate. Which sounds silly, you know, but when you try to look nice for dinner and you can't make your hair do anything, it just kinda ruins your night.

[00:13:11] **Ben:** Good luck.

[00:13:11] **Carol:** Thanks. Yeah. That's it for me.

## [00:13:13] Book Club Recap

[00:13:13] **Adam:** Alright, well I guess that brings us to our book club recap. If you have not been following along, then you won't know that we are reading The Phoenix Project, which is a book about DevOps. It's a narrative story, and Now is your last chance I'll say so we have one more meeting where we'll be discussing this book And then we might take a couple of weeks off just let everybody catch up on real life And you know have a couple of weeks of no books before we start another one But like I said, we have one more book club meeting about this book.

[00:13:43] **Adam:** It will be all the way up through the end So if you'd like to come join us, we are going to actually hold meeting a little bit later than usual so that I can make this announcement and you have the opportunity to come join us to discuss the book. and we're going to try to have all four of the hosts on and we're going to do it on Monday, July the 31st at 5 p.

[00:14:03] **Adam:** m. in our Discord.

[00:14:05] **Adam:** Yes. Oh, okay. Very good point. U. S. Eastern, 5 p. m. in our Discord. So, if you would like to join us, what you need to do is go to, workingcode.dev/Discord. And join our Discord. And then in there, there is a book club channel, a text channel where you can hang out and talk about the book if you want.

[00:14:25] **Adam:** And then, on Monday, the 31st at 5 PM, us Eastern. We have a voice and video channel, both being optional. If you just want to lurk and listen, that's fine. but we, it's a voice and video capable channel where we can, get together and see each other's smiling faces and discuss the book. That's the plan.

[00:14:43] **Adam:** And we'd love to have you join us. So, once again, workingcode.dev/discord.

## [00:14:48] Meet Grug

[00:14:48] **Adam:** All right, so grug welcome to the show grug. Do you want to say hi grug?

[00:14:54] **Tim:** Hello? Me name is Greggg.

[00:14:58] **Adam:** So there's this website, the grug brained developer and it is at grug brain. dev g r u g b r a i n dot dev and it's been around for a little while. It's it's a humorous look at sort of like best practices and you know things that you learned through a long career in coding told through, sort of like a caveman type perspective, like simple language, pretty humorous.

[00:15:23] **Adam:** And we just thought we would, you know, maybe break off a section, let Tim read it in an amusing voice, slash make Tim read it in an amusing voice, and then discuss it and see where that takes us. And if we, if this goes well, maybe this will be sort of a recurring segment. So, what are we talking about today?

[00:15:40] **Tim:** I, I just gotta point out there is a sag, you know, the Screen Actor's Guild. I can't talk about any projects. So this is, you know, this is not one of the STR groups, so, so I can do this.

[00:15:52] **Adam:** That's right, because you're a, you're, are you in SAG AFTRA?

[00:15:54] **Tim:** I'm not a sag, I Do

[00:15:57] **Adam:**

[00:15:57] **Tim:** Brain Developer. A layman's guide to thinking like a self-aware, small brain introduction. This collection of thoughts on software development gathered by Grug Brain Developer. Grug Brain Developer not so smart, but Grug Brain Developer programmed many long year and learned some things, although mostly still confused. Grug Brain Developer tried to collect learns into small, easily digestible, and funny page. Not only for you, the young Grug, but also for him. Because as Grug Brain Developer get older, He forget important things, like what he have for breakfast, or if pants put on. Big brain developers are many, and some not expect to like this.

[00:16:47] **Tim:** Big sour face. Think they are big brain developers many. Many, many more, and more even definitely probably, maybe not like this. Mini sour face. Such is internet. Note, Grug wants think big brain, but learn hard way. It's fine. It's free country, sort out at end of day, not really matter too much, but Grug hope you find fun reading and maybe learn from many, many mistake Grug make over long program life.

[00:17:18] **Ben:** Very

[00:17:18] **Adam:** there you go. Now,

[00:17:19] **Carol:** Yes.

[00:17:19] **Adam:** to expect is going to be good.

## [00:17:22] Microservices

[00:17:22] **Adam:** Okay. So, so Grug, what do you think about microservices?

[00:17:25] **Tim:** Grug wonder why big brain take hardest problem, factoring system correctly, and introduce network call too.

[00:17:34] **Carol:** Oh, man.

[00:17:35] **Tim:** Seem very confusing too, Grug.

[00:17:38] **Carol:** Oh, I think that's what we all said when we were like, let's go microservices. And then we're like, why'd we go microservices? Let's go back to monolith, please.

[00:17:48] **Adam:** So

[00:17:48] **Carol:** just put so many, so many layers of confusion in here.

[00:17:51] **Tim:** Yeah. And then having to determine, is it really a problem with the service? Or is it just like, you can't make the

[00:17:57] **Carol:** It can't connect.

[00:17:58] **Tim:** firewall connection or,

[00:18:00] **Carol:** Network problem. Database.

[00:18:02] **Tim:** certificate

[00:18:03] **Carol:** huh.

[00:18:04] **Adam:** security groups,

[00:18:05] **Carol:** Yeah. So many things. Oh.

[00:18:10] **Tim:** you know, we do have a microservice type service, but it's, it's pretty simple, right? So it's, it's not too hard. But, if you get these really huge ones, I, I totally get what Greg's saying. It's like, you're, you're, you're compounding problems for yourself,

[00:18:24] **Ben:** One of the things that I struggle with a lot is just trying to figure out which services actually call into a given service. And this comes up when I'm, I'm interested in perhaps merging two services together. Which means that I'd have to either change the service name that gets invoked or, you know, put it under a path within another service, but I'd have to go and change something somewhere else so that it doesn't start making calls into the void.

[00:18:52] **Ben:** It actually has to reroute to a different area, but I feel so not confident that I'm actually going to find all the cases of here's service X and it's calling into service Y. And we manage a lot of that through environment variables, but every service defines its own environment variables. So there's no reason to say that service XYZ URL is called that in one service and not something completely different in another service.

[00:19:22] **Adam:** Yeah. It's like you need a network diagram, but not just of like what machines or, you know, whatever VMs are out there, but like. Of what depends on what.

[00:19:32] **Ben:** Yeah. And I'm sure there's some sort of, I'm going to say words like mesh, network, layer, I don't know what that is exactly, but it's, I, it's like, I mean, not to make a poor analogy, but you know, you take some sort of a medication that's important for something, but then it has a side effect, gives you dry mouth and then you have to take another medication to help combat the dry mouth, and then that gives you.

[00:19:56] **Ben:** You know, joint inflammation, then you got to take Advil to combat the joint inflammation. It, it feels like a lot of the tooling is to help fix some of the unfortunate side effects of the other decisions that we've made.

[00:20:08] **Adam:** hmm.

[00:20:09] **Tim:** you wonder why your, why your kidneys and liver are failing.

[00:20:13] **Ben:** You're like, can we just have not made that decision in the first place?

[00:20:16] **Adam:** And then your AWS bill is 30,000 a month.

[00:20:20] **Tim:** Yep.

[00:20:21] **Ben:** One of the things that holds me back the most right now is message queues. I, I have no experience with building message queues into ColdFusion. And I mean, I do have some experience, but it's all R&D. I have nothing in production in my like 20 plus years of using ColdFusion that uses message queues. And, if I could solve that problem or, you know, not solve it, right.

[00:20:48] **Ben:** Cause I'm sure everyone out there, not everyone, but I'm sure it's been done a thousand times by a thousand other developers. If I could just get comfortable with that. And putting a message queue consumer into ColdFusion, then I feel like I could start really collapsing a lot of services that don't have to exist in my world. Because a lot of stuff started out as, oh, we have this queue of things, and now we need to have workers, and of course those workers need to be built in nodes so that we can scale them up high. Forgetting entirely the whole fact that consuming from a message queue to update a database record is like no additional processing on top of the The confusion system already.

[00:21:27] **Ben:** It's not like it's pulling from message queue to do image processing and it's very CPU intensive or doing some sort of massive data transformation. It has to hold, you know, four gigs of data in memory. I'm sorry. I'm just ranting now against, against microservices.

[00:21:44] **Adam:** don't know, I, like, I have thoughts. And my mom told me if I don't have anything nice to say, then just don't say anything at all.

[00:21:52] **Ben:** Well,

[00:21:52] **Carol:** Your mom stole that from Bambi.

[00:21:56] **Tim:** That's not the Adam I know.

[00:21:58] **Adam:** I'm trying not to be too critical. Every, look, everything, everything has, stuff that's bad about it, right? So I guess my thought is, back in the day, very long time ago, ColdFusion had event gateways and they were not well maintained and they just kind of stopped working. And ever since then, it's been extremely difficult, if not impossible. To get event based, like, push actions into ColdFusion other than, like, a webhook.

[00:22:28] **Adam:** So if your thing doesn't have the capability to make a webhook, then the only way to do it with ColdFusion was to write some separate thing that can take an event and turn it into a webhook so that you can push it into ColdFusion, which is dumb. Yeah, you know, I don't know. I'm trying really hard not to just all over ColdFusion, but you know, that's just one of the things that that really soured me on.

[00:22:52] **Adam:** It's like you had this great feature and you just Let it rot and die and,

[00:22:58] **Ben:** I looked into event gateways a couple of times specifically because I think it had some early integrations with SMS and, WebSockets, like before there were really established solutions for that kind of stuff, and I just remember being so turned off at the seeming complexity of just configuring it.

[00:23:19] **Ben:** I, I, I'm just, I can't live in a world where I have to go into the ColdFusion administrator or go into an XML file somewhere to wire together something. I have to be able to do it in the application code and it has to be in source control and it has to be easy to find and easy to update. And the second I have to go outside of that, it's just a no go.

[00:23:43] **Ben:** I refuse to go down that rabbit hole.

[00:23:45] **Adam:** and I think that that's at least a big part of why it died on the vine, right? Like just because it, it was not a good fit for the way that developers, need things to work. You're right. You know, you shouldn't, I mean, at the average company or government using ColdFusion, they're not going to give your average developer access to the CF administrator.

[00:24:08] **Adam:** And they're probably not going to be willing to go in there and set up event gateways back when they were functional,

[00:24:13] **Carol:** most devs didn't want to go learn it for the fact just to code around it. You know, like I wasn't, I was never going to go into the CF admin to see what I could change unless there was some big major problem.

[00:24:24] **Adam:** But like, so, you know, there was, there was some time years back that I wanted to do like a Redis pub sub with CFML and it was I eventually gave up on the idea because it just wasn't worth, the juice wasn't worth the squeeze, right? Like why try and squeeze blood out of a stone when I can just go over here to any other language that.

[00:24:44] **Adam:** Has been, you know, created or popular in the last 20 years and, it'll work fine out of the box, zero config. Just rubbed me the wrong way.

[00:24:54] **Ben:** No, I hear you. I've wanted to, I wanted to play around with Redis PubSub through the, the Jettis library, which is the kind of the main Java implementation of the Redis client. And in order to do it, you have to extend. Their PubSub base class and Exactly. Like you'd, you'd have to start writing Java code in

[00:25:15] **Ben:** order for that to happen.

[00:25:16] **Adam:** is the whole reason that you're writing ColdFusion is

[00:25:18] **Ben:** Yeah, yeah, yeah,

[00:25:19] **Carol:** Yeah. You're trying to avoid that.

[00:25:21] **Ben:** I, I am excited. I mean, not to go tangents on top of tangents, but, Lucy6, which was just announced at CF camp the other week, they're, they're having a huge push for Java implementations inside of the CFML code. I'm sure there's all kinds of, of booby traps and pitfalls there in terms of how things load and interoperate, but I'm, I'm excited to see.

[00:25:46] **Ben:** What that could mean in terms of these lower level integrations that we've not really had immediate access to historically.

[00:25:54] **Adam:** So wait, there's this like tag islands, but instead of tags, it's Java.

[00:25:57] **Ben:** Yeah. Like you can, you

[00:25:59] **Adam:** CF Java,

[00:26:01] **Ben:** you can, I, I mean, I don't want to speak out of turn here cause I don't, I don't really know the details other than what they did in the presentations, but I think you can have components literally extend Java classes and you can say that this. This function is actually Java code internally and write Java code inside of it. I, you know, I wouldn't. I would not want to mix and match more than I absolutely have to. But if there's, if there's some sort of clean separation, some clean scene where I can say very clearly, everything on this side is Java and very clearly, everything on this side is called fusion, I, you know, I'd be down to clown if there's, if there's the right abstraction,

[00:26:41] **Carol:** No. Yeah, agree.

[00:26:45] **Adam:** put it in the column of things that I don't give a flying about.

[00:26:50] **Ben:** I think it's so, it's interesting, I have so much more fear when it comes to Java because it feels like so much of a more unknown than I do when it comes to. JavaScript, which in some ways is pretty ironic because in both cases, I'm usually using someone else's library to implement something complex, you know, if I, if I have a.

[00:27:14] **Ben:** A queue consumer, and I'm using the, some sort of rabbit MQ consumer. Part of me is always like, what happens if that consumer, if like the thread internally to that consumer dies, do I have to restart it? Does the client take care of it? I have all this anxiety, especially because timeouts. So I'm a little, always unclear as to where the request timeout and the confusion, how it interacts with the threads that are happening below the surface in Java.

[00:27:49] **Ben:** But then if I were to go into a node application and just, you know, new up a, a rabbit MQ consumer and say, start consuming, I, for some reason, have no anxiety whatsoever about like, well, what happens if that rabbit MQ consumer dies, and then. I have some unhandled promise rejection. Like, do I have to start that again?

[00:28:12] **Ben:** Does the RabbitMQ client start that again? I just don't think about it. And I don't know why I have so much more anxiety over that kind of a problem in the ColdFusion world that I don't have in the JavaScript world,

[00:28:25] **Adam:** I bet you it's because you know you've been doing it for so long that you know ColdFusion inside and out and upside down and backwards So you, yeah, you know exactly how the engine under the hood works and you can, can, you can kind of, damn it, what is the word? You can see these problems coming, you know, before they become problems.

[00:28:46] **Adam:** Whereas in something like Node, I'm assuming you don't have as nearly as much, experience. And so it's like, okay, yeah, you can just kind of be naive, right? Like. Yeah, cool. Here's how you

[00:28:55] **Ben:** they set it to work. Anyway, we're pretty far off the reservation here.

## [00:29:00] Type Systems

[00:29:00] **Adam:** All right. So maybe we can, poke our, our friend Grug here over again. So Grug, thanks for the prompt on microservices. I'm curious, What do you think about type systems?

[00:29:08] **Tim:** Mmm, type systems. Grug very like type systems. Make programming easier. For Grug, type systems most value when Grug hit dot on keyboard, and list of things Grug can do, pop up. Magic!

[00:29:23] **Carol:** Love it! Love it!

[00:29:25] **Tim:** This 90% of value type of system, or more to Big brain type system shaman often say type correctness main point of type system.

[00:29:37] **Tim:** But Grug notes some big brain type system shaman not often ship code. Grug suppose code never shipped is correct in some sense, but not really what Grug mean when they say correct

[00:29:57] **Ben:** That's hilarious.

[00:29:58] **Tim:** Grug say tool magic pop up of what can do and complete of code Major most benefit of type system correctness also good But not so nearly so much. I don't really understand the rest of this, honestly. Also, often sometimes caution. Beware big brains here. Some type big brain think in type systems and talk in lemmas. Potential dangers. Did I say that right? Lemmas? I don't know. I had to look that up.

[00:30:30] **Adam:** an intermediate theorem in an argument or proof

[00:30:34] **Tim:** Okay. Danger. Abstraction too high. Big brain type system code become astral projections of platonic generic Turing model of computation into code base. Grug confused and agree some level very elegant but also very hard to do anything like record number of club inventory for Grug Inc. Task at hand. Always, most value type system come. Hit dot, and see what Grug can do. Never forget!

[00:31:05] **Adam:** man I love I mean I use types, in early on in my career, right? so I guess I cut my teeth on visual basic, but after that I did like c and a lot of like dotnet stuff c sharp, in college and beyond and The, the autocomplete and code insight stuff was always very good. And I kind of missed it when I swapped over to ColdFusion, sort of in the middle of my career.

[00:31:29] **Adam:** but then, here now later with TypeScript, it's nice to have it back. But lately, I've been struggling with TypeScript. you know, I totally get the vanilla case, right? Like, I just have a TypeScript file, I want to type some JavaScript stuff into it, put in type annotations. And it gets it gives me the the Editor tooling to make life better and that's great where it becomes more difficult is when you have to like add in a like a build tool chain and you have to Export it as both common.

[00:31:58] **Adam:** js and esm and or like maybe I don't know maybe sometimes you can get away with like just delivering the the typescript itself and let the Consuming if you're building a library, let the consuming project handle the fact that it's TypeScript and, and, use

[00:32:16] **Carol:** however.

[00:32:16] **Adam:** tool chain. I don't know, like, I honestly, I have not got a good setup and because of that, I last like, two or three weeks, I have been leaning into this new, TypeScript via JS stock annotations. I mean, I say new, it's. It's newer, it's newer, but it's not new. the, it, it, and it's ugly. And I think everybody involved knows that it's ugly. It's, you know, the, there's a

[00:32:39] **Adam:** certain

[00:32:39] **Carol:** talking about.

[00:32:40] **Adam:** Yeah. Okay. So, for example, like, I mean, this is going to be a terrible contrived example, but it'll, it'll get the point across.

[00:32:48] **Adam:** So you can do const foo colon string equals foo in in quotes, right? And that's how you do a string typed variable. In TypeScript, like with, like, what do you even call it? Like, like original TypeScript. I don't know. But then, with like actual TypeScript, the, this new or, syntax is basically you just have, you know, const foo equals foo in quotes as a string.

[00:33:13] **Adam:** And then on the line above that in, in a comment that it has to be a star, I'm sorry, a slash, and then two stars has to be two stars. and then you can do. It's a, you do like type colon and then like string in this case, and then star slash to close it. And so TypeScript will see that and go, okay, that means that this thing on the next line is this.

[00:33:37] **Adam:** and it gets really, I mean, TypeScript could do a lot of stuff, you know, with your generics and all kinds of promises and nested types and all kinds of weird stuff. So it gets pretty ugly pretty fast, but it works. And for like 95 plus percent of things that you could possibly want to do. And so the benefit being zero build step, zero extra tooling.

[00:34:02] **Adam:** You don't have to do, you don't have to think about TypeScript from the runtime perspective. It just works because it's just JavaScript with comments in it, but then your IDE can treat it as if it's TypeScript and you get all the TypeScript benefits while in development and it doesn't cost you, you know, there's no extra built time, anything like that.

[00:34:20] **Adam:** So. I've been dabbling there. It's not without its friction, but, I'm finding so far the juice to be worth the squeeze.

[00:34:28] **Ben:** That's pretty cool. I, I, I have to say, I mean, I'm such a Luddite when it comes to all of the new fancy developer integration environment stuff and, before they had type systems, all the IDs could still just do, what is it like token completion? Where I don't, I don't even know how it works, but you type, you know, if you're typing confusion and you type an REQ, it'll auto suggest required because you've probably typed that a thousand times and function signatures.

[00:34:59] **Ben:** And like, I feel just that kind of gets me 90% of the way there in terms of the code I'm trying to generate now, it's not giving me. Appropriate types in terms of validation, but it is giving me a lot of the code completion, but

[00:35:15] **Tim:** what Grug would think about, co pilot,

[00:35:20] **Adam:** I wonder if that's in here.

[00:35:21] **Ben:** we'll carry you'll stir it. You're still rocking out copilot. Yeah.

[00:35:24] **Carol:** I'm not writing any code. I'm cutting down trees and playing in the pool. I am doing nothing that's techno that's like code related at all and haven't for like two months straight now. So, I still have the subscription because I just got an email this morning that said here's your github receipt. I

[00:35:41] **Adam:** Well, it's a pay annually, right? I guess you could pay monthly

[00:35:45] **Carol:** I think, I think I'd set mine up on pay monthly just with my other stuff. So, and I don't know if I'll be allowed to use it with the new job, like my crew, like job, job, but I'll be able to use it on side work. So,

[00:35:58] **Ben:** I've sort of soured is not the right word, but I'm, I'm. Less enamored, let's say all of the tools that I've tried to use that do add value. They also add complexity and I'm even so, you know, I spent a couple of months adding hotwire for the, the base cam framework into my blog. And even now I'm just, I'm not regretting doing that, but it adds, there's just pitfalls.

[00:36:31] **Ben:** And, and I had to change a bunch of stuff and I had to jump through some hoops to get it to work. And it does some cool stuff, but I'm, I'm now wondering if the cool stuff that it does is even worth the, the baked in complexity of, of having to adhere to that framework.

[00:36:46] **Adam:** as some would say, if the juice was worth the squeeze.

[00:36:49] **Ben:** Yeah. As wiser people might say, um, yeah, even TypeScript stuff. I mean, when I was doing a lot of Angular R&D, I was really excited about TypeScript because of how it made me think about wiring things together. But when I start another JavaScript project, just for funsies, that's not Angular, I don't reach for TypeScript and I don't miss it.

[00:37:14] **Ben:** And I feel weird saying that because I know, you know, you listen to any podcast where they mentioned TypeScript and it seems like people will say, Oh, I would never start another project without TypeScript again in my entire life. And I don't know, I just, I liked it, but it's not, it doesn't, it doesn't feel like a must have to me anymore.

[00:37:35] **Adam:** So as far as TypeScript goes, I think that like, for the, for some people, I could very easily seeing it, wait a minute, am I Grug?

[00:37:45] **Adam:** I could very easily see it becoming something like Git, right? Like, I would not start a new project without Git now, period. Like, if I think that it's gonna have any value at all, I want to know that I'll be able to roll back, like, Oh, I screwed up during the changes I was trying to make today. Let me just roll back to what I had yesterday, you know?

[00:38:07] **Adam:** And... I feel like it's possible for somebody who does it really well, who knows it really well, who does it all the time to feel the same way about their type system, whether it's TypeScript or, I mean, TypeScript is the only one that I can think of, or I should say type systems for JavaScript are the only ones that I can think of that are like bolted on by the community after the fact, like every other language that has types it's built into the language.

[00:38:33] **Adam:** So you don't really have a choice, right? It's either, I mean, I guess there, there might be some languages where. Typing is optional, but even then it's still baked into the language. So, all right. Well, you know what, why don't we just wrap it up there? Grug, thank you for joining us. And, uh,

[00:38:50] **Tim:** time. Hope I come back

[00:38:51] **Carol:** hmm.

[00:38:52] **Adam:** okay. I'd like to have you back, Grug.

## [00:38:55] Patreon

[00:38:55] **Adam:** so I'll just let you guys know that this episode of Working Code was brought to you by the juice that is worth the squeeze and listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of this stuff, whatever this was out into the universe.

[00:39:08] **Adam:** Then you should consider supporting us on Patreon our patrons cover our recording and editing costs and we couldn't do this every week without them Special thanks to our top patrons Monte and gene carlo. You guys rock of course,

## [00:39:20] Thanks For Listening!

[00:39:20] **Adam:** i'm just gonna throw out another reminder here book club on July 31st 5pm.

[00:39:25] **Adam:** m Us eastern you're gonna have to join our Discord And you're gonna want to show up, you know, five ten minutes early at least so that you can get the Discord part sorted out before book club's gonna start you can go to workingcode.dev/discord to get that on And that's going to do it for us this week.

[00:39:41] **Adam:** We'll catch you next week and until then

[00:39:43] **Tim:** Grug say, remember, your heart matters, even if you think you're big brain, and you not.
