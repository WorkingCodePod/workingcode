---
title: "061: Software Is For People"
description: "The crew talks about their own experience dealing with customers. And, how hard it can be to manage expectations in either direction."
date: 2022-02-09
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/061-software-is-for-people/id1544142288?i=1000550550390"></iframe>

Sponsors

- [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

Many companies are seeded from the same basic concept: customers have a problem to be solved and the people on the Product team know how to solve it. This customer-centric approach is what gives a product much-needed early traction, helps build a loyal community, and lets customer-and-company alike feel as though they're moving in the same direction.

As a company matures, however, the distance between the Customers and the Product team can begin to grow: it's no longer engineers jumping on Zoom calls with customers, it's a Support Team translating issues into a ticketing system which the engineers will then consume _weeks later_ in an adjacent vacuum. This gap - this layer of abstraction - can create a breakdown in customer empathy and can quickly lead Product teams astray.

This week on the show, the crew talks about their own experience dealing with customers. And, how hard it can be to manage expectations in either direction, whether it be the little customer with the "high urgency" tickets; or, the lone engineer who's super excited to build a custom feature even if it's not on the roadmap. None of it is easy; and, the less communication we have with our customers, the harder it seems to become.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/061-software-is-for-people.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Adam:** Like Kara was saying you can't prematurely optimize everything to always do the right thing.

[00:00:04] **Adam:** But when something breaks, I take that as, okay, this is my moment, right? This is what I've been waiting for. The indicator that this is a thing that I need to stop the users from being able to do.

[00:00:15] **Carol:** I don't know why, but I just thought of put me in coach. I'm ready to play.

## [00:00:40] Intro

[00:00:40] **Adam:** Okay, here we go. It is show number 61. And on today's show, we're going to be talking about those darn users.

[00:00:44] **Adam:** Can't live with them. Can't live without them, but as usual, we're going to start with our trends and fails. And Carol, welcome back. Good to have you back.

[00:00:52] **Carol:** Thank you guys.

[00:00:53] **Adam:** Why don't you guys go first?

[00:00:55] **Carol:** Yeah.

[00:00:56] **Adam:** said, you guys, why don't you go first?

[00:00:57] **Carol:** yeah, and definitely not a guy, but thank you, Adam.

[00:01:01] **Carol:** I haven't checked under the hood, you know,I can confirm. Definitely not. So, oh, geez.

[00:01:09] **Tim:** Wow.

[00:01:09] **Adam:** off to a solid start here.

[00:01:11] **Carol:** I swear. I haven't been drinking it's noon on Saturday.

[00:01:14] **Tim:** noon on Saturday. right?

## [00:01:17] Carol's Failure

[00:01:17] **Carol:** All right. So I'm going to go with a failure. You guys, early this week, I don't know what happened. I mean, my laptop might have fallen on the kitchen floor, but I can't confirm that because it's definitely my work laptop. And since then, every time I use my track pad, it just goes all over the place.

[00:01:33] **Carol:** So I tried making it, like, I tried just dealing with it for a couple of days and, right. Clicking on the file and tried to hit the deploy button. And it actually is like the leading the file. And I'm going, this is awful. Yeah, because it would select the wrong thing because when I would try moving my mouse, like moving the cursor, it would be somewhere else.

[00:01:53] **Carol:** By the time I actually got the click to happen. So, I fought with that for a few days and it made me mad. So I bought a mouse and. Mice. I don't know why a mouse is not for me. Like, I definitely need a track pad, so I ordered one, but it's not going to be here for a couple of days. So I am not happy with apple mouse and using a mouse.

[00:02:16] **Carol:** I don't understand how people function with them. I need my track pad to actually function how,

[00:02:22] **Tim:** Yeah, that's funny. I hate track

[00:02:23] **Carol:** oh gosh, I can't do anything. I don't have any of my, like my shortcuts aren't here. Like how do you open, like your control stuff and how do you get to all your apps if you have a mouse?

[00:02:34] **Adam:** Spotlight or Alfred

[00:02:36] **Carol:** Oh yeah. I just, I like just gestures. I like being able to do three and four finger things and swipe left and right.

[00:02:44] **Adam:** Yeah. I mean the gestures, I I have a mouse that lets me do gestures. I have like a gesture button on the side of my mouse here. And it's got a bunch of different buttons that I can map to stuff.

[00:02:53] **Ben:** I am missing those buttons so hard. I had a really nice Logitech mouse that even had a, side to side scroll wheel, so sweet. And then my wrist started to hurt. So I switched over to this is vertical mouse, so it keeps my wrist and sort of a slightly more line position. And it's got zero features.

[00:03:11] **Ben:** It's got a scroll wheel. That's basically it. I don't know. It's like living in the dark

[00:03:15] **Adam:** that's table stakes for a mouse these days.

[00:03:17] **Carol:** that, that is the other thing I will say. I don't understand how people who actually use a mouse, like for day to day operation, how they deal with an apple mouse, because this thing is flat

[00:03:27] **Carol:** it's, you know, has just the controls on top, but free how you use your hand. Like, I feel like I would hurt at the end of the day.

[00:03:34] **Carol:** If I had to use this every single day, it would be miserable.

[00:03:37] **Adam:** do you have the one where you have to put batteries in it or does it have.

[00:03:40] **Carol:** I charged for it. Yeah.

[00:03:42] **Adam:** Have you tried to charge it yet?

[00:03:44] **Carol:** Oh, she can't use it because the charge port is on the bottom. So you have to plug it in and go, oh, well now I can't use my mouse and my track pads, just going to put the cursor, wherever it chooses at the moment. So I'll have to send my math book yet. I didn't get it fixed. I want to do that.

[00:04:01] **Ben:** I'm sure this is a vast overgeneralization, but I also find that people who use track pads a lot, tend to ignore the existence of scroll bars and will often design interfaces that don't have well configured scroll bars, because they're just swiping left and right. And up and down, they never think about anyone who doesn't have a swipe.

[00:04:21] **Adam:** well I feel like I fall into that same trap, but I have a horizontal scroll wheel and a vertical scroll wheel. So I'm not using a track pad, but same problem.

[00:04:31] **Carol:** I can confirm that is true for me, at least. So, yeah. All right. Well, that's me earlier. What about you, Ben? What'd you got.

## [00:04:40] Ben's Triumph

[00:04:40] **Ben:** I'm going triumph. And I have a, both a personal and a professional triumphal start with personal, I've. As I've talked about many times in the last few episodes I've been working on my personal website and just revamping it, modernizing it. I put it behind CloudFlare, which is a content delivery network.

[00:04:56] **Ben:** And, I started off first by just putting my static assets, my JavaScript files and images through CloudFlare, just to experiment with it. And I let that run for like a month and everything seemed to be honky Dory, if that's what the kids are saying these days.

[00:05:10] **Tim:** Uh,

[00:05:10] **Ben:** And

[00:05:13] **Tim:** not since the fifties.

[00:05:16] **Ben:** so, and then after that went really well, I think I actually just moved my. Domain name servers for my main domain over to CloudFlare. And I'm now routing all of my website traffic through the CDN. So most of the top of the pages aren't getting cash, but they're going into Cloudflare's big pipes. And I think that has an performance improvement and a denial of service attack prevention, that kind of stuff.

[00:05:42] **Ben:** Anyway, long story short, I've been working on my lighthouse score and, and I finally got a hundreds on all my lighthouse score, performance, accessibility, best practices. I only got the performance to be a hundred once every single time I've run it since then. It's been, in the high nineties, but never wants to a hundred, but I, I was pretty excited about that.

[00:06:00] **Ben:** So that felt like the culmination of a lot of little baby steps adding. so That's personal professional. I finished that feature that I had been talking about, whereas coming into the new year with a very low motivation, finally decided to just kick the tires on a new epic. And, I finally turned the feature flag for that epic on Wednesday, I think, of this last week.

[00:06:19] **Ben:** So pretty excited about that. Yeah. I feel like I put my mind to it and I accomplished some things. now it just becomes a matter of trying to get the company to promote it, which they probably won't because it's on the legacy system. So it'll just parlay itself naturally into a failure. But, personally, it's, it's triumph.

[00:06:36] **Ben:** So I'm pretty excited about that.

[00:06:38] **Adam:** Cool. Cool.

[00:06:38] **Ben:** Yeah. Adam, what about you? What do you got going on?

## [00:06:40] Adam's Triumph

[00:06:40] **Adam:** I guess I'm going to call mine and triumph as well. I finally got my invite to the co-pilot beta, the get hub,

[00:06:47] **Carol:** Oh,

[00:06:48] **Adam:** Rachel code for you thing.

[00:06:49] **Adam:** And I, yeah, I started playing with it. I turned it on, I will say it can be really annoying. if I've chosen to write most of the line myself and then I get to the point where I'm like trying to close the string and, parentheses and, a curly bracket.

[00:07:04] **Adam:** And the semi-colon

[00:07:05] **Carol:** all of this extra stuff.

[00:07:07] **Adam:** yeah. And it tries to like, guess what you want on the end of the string. And it's maybe not quite right. And it's just, it's kind of not a great contrast difference between what I would type and what it's suggesting. So I can't really tell, did I type that or not, and it's super annoying.

[00:07:24] **Adam:** And sometimes I'm just like escape shift to the right and just delete everything to the end of the line and type it

[00:07:29] **Carol:** yeah, I do that to you.

[00:07:31] **Adam:** but holy crap, that thing is like voodoo.

[00:07:35] **Carol:** it amazing.

[00:07:36] **Adam:** I was doing a lot of a TDD this week and I was writing some tests and it's like, you, okay, you set up a mock database connection and you mock a couple of different database responses.

[00:07:50] **Adam:** And then, I'm Octa, fetch request, like an HTTP request. And then I did an expectation and.

[00:07:58] **Carol:** It created it.

[00:07:59] **Adam:** It was like 99% there. And it was like pulling things out of strings in my various database things, mock responses and substituting them in a string that it pulled from somewhere else. And it was just like, how do you know this?

[00:08:14] **Carol:** I say it's code wizards. I don't know. All I know is I think something, so I'll write a little comment and I'm like, oh, I need this to do. And it'll start filling out what it thinks. I'm just even trying to comment and I hit enter and then it's like, oh, well, since we've already figured out your comment for you, let me write the code for you too.

[00:08:31] **Carol:** So I should enter again and like, look at that.

[00:08:34] **Adam:** Yeah.

[00:08:35] **Tim:** let's just give it up to a robot overlords that they're here.

[00:08:39] **Adam:** it's not always perfect. It's really, it's creepy when it does a really good job. Cause it's like, ha. How did you have that level of insight and so quickly.

[00:08:49] **Carol:** I'm going to be heartbroken when this goes away from beta and they put it in, cause it can be a paid program. Right. So you're going to have to pay to have it eventually. So when I have to uninstall this, I'm probably going to cry just because I've gotten so adapt to hitting tab and just even having something like my comments auto fill.

[00:09:10] **Carol:** So I'm like, oh,

[00:09:12] **Adam:** I've only been using it for like three days now, but still it's, I'll be curious. This is great marketing. If they are going to go,paid

[00:09:19] **Carol:** was, yeah, it was in the initial release when everyone got in it. Cause I was one of those that got into it like a couple of months ago and I was reading through everything and it was like, this will be a paid subscription when it said done. So I don't know the cost yet, but

[00:09:31] **Adam:** Yeah. That's I mean, like I said, it's pretty great marketing. Get everybody hooked on it and then be like, ah, now you got

[00:09:37] **Adam:** to start paying.

[00:09:38] **Carol:** will, probably buy it myself as long as it's, like $4 a month then I'm probably gonna definitely get at more than that amount. I'll write my own code again. That's fine.

[00:09:46] **Adam:** All right. So that's me. Tim, what's going on with you, man.

## [00:09:50] Tim's Triumph

[00:09:50] **Tim:** I'm going to say a triumph. It's not a big one. So, all have, you know, thepast. Christmas day, I've been sick and finally this week I feel human. I can human again now. Um,I was, yeah, yeah. I mean, just, I don't have to take a nap in the middle of the day just to get through the day to work. I only, I continued to work pretty much the whole time.

[00:10:14] **Tim:** I only took two days off. well I did take a week so we can do days, but, yeah, I feel human again, but so that's the triumph. I'm actually getting stuff done again. And I feel I stop feeling guilty. It's like, when you can't perform, it's like, you just feel, I just felt worthless. I just completely felt like a failure.

[00:10:34] **Tim:** I just had to keep telling myself you're not a failure. You're just sick. You're not a failure. You're just, you don't feel good. So you can't

[00:10:41] **Carol:** okay. It's okay. To

[00:10:43] **Tim:** It's okay All right. All right. So

[00:10:46] **Carol:** to have like a theory. I feel like we have screwed up our immune systems by not being exposed to anything now. So the minute we get something, our body is just wiped because we no longer exposed to just the common, cold every day at the grocery store.

[00:11:02] **Carol:** And we're out, we're just not fighting off stuff. And like, I feel like the things I used to just kind of pick up and my body figured out how to fight against it. Doesn't have to anymore. Cause I stay at home and pet a puppy all day long. So it's like, oh, that's the one thing you won't catch as anything the puppy has.

[00:11:16] **Carol:** But other humans, it's going to wipe you out because you don't have an immune system anymore.

[00:11:21] **Tim:** Yeah. I kinda agree with that. It's like, we spent, over a year and a half being completely screened away from everything except the people in your immediate circle. And then, we decided to go out and go do some stuff. We went to Atlanta and went to. Momo con, which is, an anime convention and video game convention.

[00:11:38] **Tim:** And we got, we all got sick after that site. we came in contact with other humans and we got sick and it wasn't even COVID it wasn't COVID, it was just the regular flu. So although I honestly think we got the flu and then got COVID cause it was like, it was back-to-back, it just wasn't normal, but the other triumph is, I'm sorry to do this, but I'm a proud parent.

[00:12:00] **Tim:** I have to brag on my son. We went to the dinner. So Thursday we were recording on Saturday because some of us couldn't be here. I couldn't be here on our normal recording night because they were doing a dinner in my son's honor. Absolutely amazing,

[00:12:12] **Carol:** Oh.

[00:12:13] **Tim:** absolutely amazing. He gave a speech and he did fantastic.

[00:12:17] **Tim:** He's very, unlike me, he's very introverted, but I've been teaching him public speaking and,getting him used to public speaking and he gave a fantastic speech. I mean, Polish, it was just beautiful. And he had people crying and he,he nominated,his favorite teacher from elementary school who helped them with some anxiety issues he had when he was younger.

[00:12:40] **Tim:** And she just, she gave a speech to, and she uses balling.

[00:12:44] **Carol:** oh, how

[00:12:44] **Tim:** I mean, just, absolutely. It was just, it's extremely. And like there's, 70 people there all to honor him and his accomplishments of academic accomplishments and just, yeah, it was just extremely moving night, so I'm very proud of him.

[00:12:59] **Carol:** we are proud of him. See you. Yay. Yeah. Great job

[00:13:03] **Tim:** Okay.

[00:13:05] **Carol:** Well, not really kiddo. About to be the door, right.

[00:13:08] **Carol:** Oh, he

[00:13:08] **Carol:** is 18 now. Oh, I'm still going to say kiddo. I don't care. Great job kiddo.

[00:13:16] **Ben:** let me ask you Tim. Totally unrelated to your kid. Apologies.

[00:13:19] **Tim:** That's fine.

[00:13:21] **Ben:** I know you're a fan of the spicy pepper. what's your take on eating spicy food when you're sick? Because when I'm sick, I definitely convinced myself that I should get some general Tso's chicken to help ward off the, the sickness is there any science behind that

[00:13:36] **Tim:** know if there's a size, but sure. Feels good. Right. If you can just congested, like getting some really hot peppers and just blow in your nasal cavities out. Yeah, it does but for me, I've completely ruined that. So it's like, I can't just go, like, I can't put cayenne pepper on something and do that.

[00:13:53] **Tim:** It's like, all right, I gotta get the Carolina reapers. I gotta get it to the super Megadeath, hot sauce kind of stuff.

[00:13:59] **Tim:** So,

[00:14:00] **Adam:** I'll just stick with the Alto.

[00:14:01] **Carol:** I was giggling that Ben's level of hot was the General's check-in come

[00:14:06] **Ben:** Yeah. Yeah. You know, you really

[00:14:07] **Ben:** get the,

[00:14:08] **Tim:** no, and I get General's chicken. I got to come home and put like tons of stuff on it just to like actually get the heat level to where I can feel it.

[00:14:14] **Carol:** it's more like a sweet barbecue sauce to me.

[00:14:17] **Tim:** It is.

[00:14:17] **Carol:** there's no spice in it and it has a little spicy symbol by it. I'm like, get real, get real.

[00:14:23] **Ben:** Yeah. I don't know if I've talked about this before, but for years I used to get,hot chicken wings at the Buffalo wings. I used to get Buffalo wings at restaurants and I would always ask for what's the mildest sauce. They'd always tell me that, oh, it only comes medium or, yeah, there's a mild sauce.

[00:14:37] **Ben:** And then one time, and this was only like seven years ago, I was ordering chicken wings. What's the mildest sauce I can get. And the waitress was like, well, there's a very mild sauce, but you can also just get it without the Buffalo sauce on it. You can just get plain wings. And it had never in my, like, like 30 years of life occurred to me that you could just get plain fried chicken wings and it blew my mind and I've have dramatically reduced the amount of hot sauce in my life, which I'm very excited about.

[00:15:06] **Tim:** Well, I would recommend to you. I don't know if you've ever seen the show hot ones.

[00:15:09] **Ben:** I don't think so.

[00:15:11] **Tim:** Yeah, it's a YouTube. It sets a great show. So this dude,

[00:15:14] **Tim:** so this is a show called hot ones where they interview celebrities while eating 10 wings and they get progressively hotter to like where it's like Carolina Reaper hot, and it's amazing the level of candor they can get, he can get in these interviews. And he's a very good interviewer.

[00:15:29] **Tim:** He is like very research is extremely well. but I only bring it up to say this, they're now selling a hot sauce that is marketed to kids as the first hot sauce for children, because it's not that hot. So I think maybe, I'll buy you a bottle and send it to you.

[00:15:43] **Ben:** That is crazy. That's awesome though. Thank you.

[00:15:46] **Adam:**

## [00:15:47] Audible

[00:15:47]

[00:16:47] **Adam:**

## [00:16:47] Gosh Darn Users

[00:16:47] **Adam:** Cool. So today's topic. those dag-gone users basically, we've been noticing, oh, I dunno. How would we want to put it, maybe like some hostility, toward users more than, typical hostility. there's always been sort of a love, hate relationship with users, right?

[00:17:04] **Adam:** Like without users, there's no reason for the software. so you kind of need them, but also often users, Hey, they never read the documentation, but B they do things that, to us seem dumb. but,the thing that has kind of caught my attention has been

[00:17:20] **Ben:** Okay.

[00:17:21] **Adam:** people complaining about users, doing things that create work for us, the developers, but those things.

[00:17:29] **Adam:** Our, what we would want them to do. Right? Like putting in a ticket, somebody gets upset about receiving a ticket at four 50 on Friday. I'm like, well, but they put in a ticket, they didn't call you or email you. Right. So they're using that as designed. it's just, I feel like we need to sort of, as a community, you take a step back and remind ourselves like, software is for people.

[00:17:49] **Adam:** we live in a society as the trope goes. and, yeah, I don't know.

[00:17:53] **Carol:** I would like to start with it's a feature, not a bug. Okay. Let's just go there. All right.

[00:18:00] **Carol:** It's supposed to, it's supposed to work that way. Just you weren't supposed to use it that way. It's feature not a bug.

[00:18:08] **Carol:** we joke around that whenever they would find a bug in the system, we'd be like, that's not a bug, it's a feature.

[00:18:13] **Carol:** It's something that you found that you just weren't supposed to use it that way. That's a feature. Okay. Not a bug. Our systems.

## [00:18:21] Distance Between User And Developer

[00:18:21] **Ben:** I think a big part of the problem is the distance between the developers and the end users. when a company is small, at least in my experience, developers and users have a lot more interaction because there's not a support team or customer success team or something to that effect. And so you get to know your users and you build relationships with them.

[00:18:40] **Ben:** And when they're having troubles and they can't get their work done, you sort of feel it in an emotional. And then as a company grows and there starts to be buffer between the developers and the users, the, it becomes this abstraction and it's not like here's Joe. And I know that Joe runs this type of company and needs to build this product and make this stuff for his customers.

[00:19:01] **Ben:** It's more just like here are the 10 support tickets that the, customer facing team assigned to me. And now it's just a pain because I want to do other stuff. And,and I think a lot of it just comes from this, disintegration of empathy due to the removal of users from the day-to-day life of the engineers.

[00:19:16] **Carol:** Yeah, I can see that. Cause whenever we get em work to do, and it comes in from our, like our project manager and like two other people, it's not from the people using the system is not primary end users. And the request is now instead of any technical design information, it's pretty much we need this to happen.

[00:19:36] **Carol:** So they try to not tell us how to fix it because they don't want to get like all like in the face of the engineering team, because they get mad when you're like, this is how it should be done. Like, no, we'll decide how to do it. Don't tell me how to do my job. Right. So they're like, okay, we're just going to be very vague.

[00:19:51] **Carol:** So then we're like, I don't know how they use the system. Like I assume that they clicked here to get it when reality does not even hell they got to the issue. So yeah, I think removing that, interaction with the end user is a big problem and it does cost them disconnect.

[00:20:06] **Tim:** I like that term. You use Ben disintegration of empathy.

[00:20:10] **Ben:** Thank you.

[00:20:10] **Tim:** that's yeah. That's deep, bro. That, because it's true. It's like, sometimes you get a ticket and it particularly if like maybe the end-user puts the ticket and they don't know how to describe, they're not a programmer. Right. They just say this doesn't work or right.

[00:20:26] **Tim:** They don't really explain. And you're like, I can't help you with this. I need more information. And you just, and now that begins, this sort of you're sort of upset because they can't describe their problem in a way that you can help them. And then they get upset because you seem like you're. Being obstructionist. Right? Know that you're just trying to deny that there's an issue when you're not you just like, I don't understand what are you saying here? And,and then it's all through email or ticketing systems and it goes back as sometimes I just found the best thing to do.

[00:21:00] **Tim:** I don't like to do this because they, figure out they can talk to you, but getting on the phone or a call and just say, Hey, I'm sorry. I don't understand what you're saying. Talk to me here. Only talk, talk you through. You're like, oh, and usually it's a lot more simple than you thought, right? It's usually a, you.

[00:21:18] **Tim:** think it's a bigger problem than it is.

[00:21:19] **Tim:** And it's like lot smaller issue, but they're just describing it in the wrong way. And you're like, okay, once you get that empathy, right, you build that back up through a conversation. You can usually handle it pretty well. But that initial feeling of. why can't you tell me what I need to know is very painful.

[00:21:39] **Adam:** Yeah. I find that non-technical people often have not enough of a vocabulary around technical things or around our products. I feel like a significant portion, not a majority, but a significant portion of the time that I spend with users is spent either disambiguating the things that they're talking about or trying to give them the vocabulary, They try to explain something and they're using words that sound technical to them, but it's not the right word.

[00:22:04] **Adam:** So it just serves to confuse us. So I'm like, ah, no.

[00:22:09] **Ben:** I wish there was a button I could push that would just set up the call between me and the user. Cause a lot of our tickets come from the support team. And so there's this weird sort of love triangle between me and the support team and the user where I need clarity. So I asked the support guys and they go and they talk to the users and that's usually over email and sometimes it takes weeks occasionally for the users to even respond to their request. I wish I could default to more exactly what Tim is saying. Whereas in the support ticket system, there'd be just a button to say like, Hey, support person, please just set up a call and let's all do this. Face-to-face because it's going to be crazy going back and forth over emails.

[00:22:47] **Adam:** Yeah. With an intermediary to.

[00:22:48] **Ben:** Yeah. Yeah. Yeah. The, although I'll tell you, I love, love, love talking to users and I love, love, love building things for users, but the thing that drives me crazy, and it's only because it's such an emotional let down is I'll be talking to a user and they say, Hey, wouldn't it be great if the software did X, Y, Z. And I get super excited because like, oh, I know how easy it would be to do that for you.

[00:23:09] **Ben:** So I'm going to go back into my cave and I'm going to build that. And in four hours I build it and I deploy it and I tell the user and I hear nothing

[00:23:18] **Ben:** for weeks. I was so excited. I was so excited to do this for you. And you don't seem to care.

[00:23:28] **Tim:** I totally get that. So we had a company come to us with like, Hey, we need you, we need a way to, there are. An insurance company, but they also do their own repairs. So they have a repair company that goes out and it's down in Florida and they fix, the rooms and everything.

[00:23:45] **Tim:** And they need to take payments sometimes from the, the people that they're doing the work for. And so we built, I built this whole thing for them, and,I put it live and they were testing it and they never even told me yesterday. I went and looked. I'm like, are they even using this?

[00:24:00] **Tim:** And I wouldn't look, yeah, they're using this. I've gotten nothing. I, I had no feedback, Hey, this is working great. It's like, I totally had no clue. I was just checking to make sure that, the emails are going out and payments are coming through and like, okay, they're using it. But I had no clue.

[00:24:15] **Tim:** Cause they were like, yeah, we're going to go live with this sometime around January, I guess. And I'm like, okay. It's like almost the end of January. Yeah. Nothing.

[00:24:25] **Ben:** So sometimes I wonder if that's the difference between enterprises and non enterprises, because as an, as a user myself, in a variety of different software contexts, it would never occur to me in a thousand years that I could ask for a feature in a, for a piece of software and then someone would actually build it in some sort of timely manner.

[00:24:44] **Ben:** It would never occur to me that's possible. and I think that's part of why it blows my mind when in an enterprise context, people seem very unresponsive to that workflow. But maybe that's just the expectation in enterprise. Like, yeah, we're going to throw hundreds of thousands of dollars that you're going to build some stuff for us to case. And like, I dunno, maybe it doesn't blow their minds at all. And it just, I imagine it does.

## [00:25:05] Taking Responsibility For User Issues

[00:25:05] **Adam:** The other sort of angle of this whole topic that I feel it like deep down in my soul and I just don't feel like everybody else agrees with me. Is that anytime a user does something like poorly or did the wrong thing, or like it used it, like Kara was saying, it's a bug or it's a feature, not a bug sort of thing, anytime that are maybe not every time, but you know, often it feels like we've, it's a failure on my part, the software developer and designer to push the user down a pit of success.

[00:25:38] **Adam:** Right. Like I. I take it personally, but not in a way that hurts me. Right. I just, every time I see a user doing something and they ran a report that happens to be particularly computationally expensive while they're also trying to do these other things that are computationally expensive and it crushes the server. That's my fault for allowing the report to be run while they're doing these other things yeah, I mean, and I feel like I constantly have to remind people of this, the same thing, right? Like, yeah, the user did something dumb, but they did something dumb because you let them do it.

[00:26:12] **Adam:** And you could have designed the software in such a way that didn't let them do that and said, Hey, maybe you shouldn't run that report right now because you're trying to also, whatever,

[00:26:22] **Carol:** right.

[00:26:22] **Adam:** this other big expenses.

[00:26:24] **Carol:** Yeah, but that's where if they don't put in the ticket, you don't know sometimes like you don't, you can't code for every scenario of what could be ran at the same time or what the users could be doing in the system. You do the best you can that front with what you know, and like we've talked about before you go live with that.

[00:26:40] **Carol:** And that's what you put out. And then as people start to use the system, that's when you find where your flaws are at and by them putting in the ticket that says, Hey, I ran this. At noon today and it stopped all of the printing that was happening in the system. You're like, oh, well now I know you can't run reports and print documentation at the same time.

[00:27:02] **Carol:** So we're going to put something in that warns you, that this report is very, time consuming and resource intense. So maybe choose to run this at a different time or put it on a different location for them. But again, back to the people using the system, you don't know those things exist sometimes until you know, they exist.

[00:27:19] **Carol:** They don't tell you, you might not find that out. So be glad they're telling you.

[00:27:23] **Adam:** So sort of along the same line, we see somebody in my work chat shared a tweet that says, oh, you have a weighted blanket. That's cute. I sleep with the crushing weight of all the crappy code I wrote years ago, still running in production. Right. So it's a good tweet. Good tweet.

[00:27:41] **Tim:** Did you write that?

[00:27:42] **Adam:** No, no,no. I could. but then one of my other coworkers and, I don't want to call them out by name or anything, but one of my other coworkers said maybe it's vain, but I don't have those regrets.

[00:27:52] **Adam:** I quickly learned to leave things better than I found them. And I've tried to achieve that with everything I work on. Otherwise you're just making hell on earth. And I've, I feel that right? Like that's, I think that's kind of the way that I approached this whole pit of success thing, right? Like Kara was saying you can't prematurely optimize everything to always do the right thing.

[00:28:09] **Adam:** But when something breaks, I take that as, okay, this is my moment, right? This is what I've been waiting for. The indicator that this is a thing that I need to stop the users from being able to do.

[00:28:20] **Carol:** I don't know why, but I just thought of put me in coach. I'm ready to play.

[00:28:27] **Ben:** I'll tell you though, there is a crushing weight when you see a bad thing happen over and over again, and you don't know how to fix it. And so all you can do is watch it happen and report generation that hits really close to home. Because one of the things that I see all the time I get out of memory errors all the time from people generating PDFs that have like an ungodly amount of pages, like they'll generate a 600 page PDF.

[00:28:53] **Ben:** Which eats up the entire memory of the machine and crashes their thread. and I see it, dozens of times a day, and I don't know what to do about it. I mean, in a perfect world, I would take that reporting system and I would move it off of the main system into some other system. But the problem is you run into all these other business constraints around contract issues with how isolated things need to be.

[00:29:15] **Ben:** And then, because they need to be isolated, we have a multitenant, or we have several single tenant systems so that like you'd have to build something that would run in each one of their things individually to be a contract compliant. And then there's then like the cost explodes, because now it's not just a, an economy of scale.

[00:29:30] **Ben:** It's, you're duplicating the cost everywhere. And so I don't know what to do. and my default position is to do nothing and I just watch those errors roll in and I feel really terrible about it. And I just don't know what.

[00:29:42] **Adam:** I mean, I don't know what's going into these PDFs. Is this like design comps

[00:29:46] **Ben:** Yeah. Yeah. So it's sort of, there'll be like a JPEG per PDF screen. And some people, they use PDFs almost

[00:29:52] **Ben:** like

[00:29:53] **Ben:** a, like a VA. Yeah. So they'll use the PDF almost like a way to archive, like to create a, an archived asset of the thing they're working on. But they're massive.

[00:30:03] **Adam:** Can you like limit the number of pages that'll generate

[00:30:05] **Ben:** Yeah.

[00:30:06] **Adam:** per,per PDF?

[00:30:08] **Ben:** but,and like, again, here's the complexity of software is that I can't even make that decision on my own. I would have to off this. This makes me so angry. I'm sorry. Now I'm just going to vent for a second. It's like in order to do something like that, I'd have to create a one pager.

[00:30:24] **Ben:** I'm doing air quotes for one pager, which writes up the value, add of why we should even be making a decision around this. And then you'd have to assemble a team. You'd have to put together a Dacey. And I don't even remember what Dacey stands for, but it's some sort of decision like we have, like there, we have these three options in each of these three options have pros and cons, and now we have to figure out which one to pick.

[00:30:44] **Ben:** And it'd be like months before you can even make a decision on anything, which is honestly used to working on a small team where you have an idea in the morning and then you deploy in the evening. And I hate process. I'm sorry, not a

[00:30:57] **Ben:** process person.

[00:30:58] **Ben:** Alright,

[00:30:58] **Ben:** tangent. Over.

[00:30:59] **Carol:** that's the whole reason why I can't work government again. Can't do that. I can't wait months to see my code go out.

[00:31:05] **Ben:** No.

[00:31:05] **Carol:** Nope,

[00:31:05] **Carol:** Nope.

## [00:31:06] Prioritising Valuable Users

[00:31:06] **Tim:** So I have An Axiom. that I've just kind of seen over the years

[00:31:11] **Carol:** An Axiom. What does that

[00:31:12] **Carol:** mean?

[00:31:13] **Tim:** just it's an Axiom sort of like a rule of thumb or truth,

[00:31:17] **Carol:** New word for Carol

[00:31:19] **Tim:** there you go, Axiom the least profitable better client is the more vocal and demanding. They will be.

[00:31:28] **Tim:** I've seen that over and over again. You have these little tiny customers who make you almost no money whatsoever and they want everything.

[00:31:36] **Tim:** They want it now and there, and they want it exactly their way and they're completely inflexible and just tear away and just, they're just there they're little chihuahuas nipping at you constantly. And then your like biggest customers who like, most profitable, like, hundreds of millions of dollars, th their value and their.

[00:31:56] **Tim:** Oh, Yeah. We've know this era has been going on for a while, but we don't, we really don't care. Right. It's all right. We know you'll fix it at some point, as you say. Yeah. It's like the squeaky wheel gets the grease kind of kind of thing. Right. It's just in a, just a noise beak because they just jump up and down and stomp and they constantly just jump on you and you give them the attention just so they go away.

[00:32:19] **Tim:** And I think they know that.

[00:32:20] **Ben:** I was listening to a Tim Ferriss. I assume everyone knows Tim Ferriss. He's the four-hour workweek guy, amongst many other things. And, he was talking about early on in his career when he was building up his business, he came to the realization that it was like 95% of all his revenue came from like 20% of his customers.

[00:32:39] **Ben:** And it was the same exact thing that the other 80% of the customers were just a drain on his entire enterprise. And, so his move, which I'm blown away by people who can make these leaps, his move was just a fire, those 80% of his customers. He was like, I just don't want to work with you anymore. Said I think it was like, he'll fulfill orders.

[00:32:57] **Ben:** I think this was part of his supplement business. He was like, I'll fulfill orders, but that's it. I'm not going to deal with customer support. If you don't wanna work with me, you don't have to work with me, but I'm happy to fill out. And that's it. And then the other 20% of his customers, he did sort of, high touch, white glove service for, and, and he said his business was great.

[00:33:15] **Ben:** He had more time and more throughput and he can build more things, et cetera, et cetera, but just having the vision to do something like that. It blows my mind when people can make those decisions.

[00:33:27] **Tim:** Yeah.

[00:33:27] **Tim:** I've kind of done the same thing. So it's like the people that. 80 20 rule just comes up so much in life, right? So like, the top 20% of your customers are giving you 80% of your revenue. And that just, I just, I don't know why, but it seems to be true. And, so yeah, so I just have a rule that if you're in that 80%, that are just not really doing a whole lot for us, you're just going to get the low level.

[00:33:52] **Tim:** You need the customer service people. You could never talk to anyone else other than

[00:33:58] **Carol:** It's going to cost. She had to speak to an engineer.

[00:34:01] **Tim:** but the 20%, they can talk to me, they can talk to other engineers that they get an access to people because they're not wasting our time.

[00:34:09] **Carol:** Yeah. I mean, we had seen something like that before. what kind of, what you were saying then where we had split some teams out, not where I am now, but where I was before we split the teams out and was like, okay, we're going to only take like, the top three clients and put them on this one team with seven or eight engineers.

[00:34:25] **Carol:** And they're went to take the next top three and put them on the team was having right engineers. And then everyone else falls on this one team that has like the same number of engineers, but they're supporting all of the needs for everyone else. So they don't get the level of support that, your top six clients do.

[00:34:40] **Carol:** Whereas, the other ones kind of fall to the bottom and just get cycled through as there's time available.

[00:34:47] **Tim:** yeah, I mean, you got to put the money where the money's coming in

[00:34:50] **Tim:** right

[00:34:51] **Carol:** I agree. Yeah.

[00:34:52] **Tim:** now.

[00:34:52] **Ben:** Have you guys ever had a, a more direct route of communication? Like I think every now and then we'll work with a vendor and we'll be in, what's called the beta testing phase of a piece of software. And they'll actually set up a special slack app just for us to ask them more direct questions. And I think we've done that maybe once or twice with really large clients.

[00:35:14] **Ben:** we'll set up. Like the customer support team will have a dedicated slack just for them. I have such a love, hate relationship with that idea that so you guys have you tried that?

[00:35:22] **Carol:** Oh, yeah, like we add, Tim said that I've done that. Definitely to me, it worked out good. As long as the customer understood the boundaries and they knew that they weren't, my only demand that they had to know that I'm also working on other projects. So I'd be like, Hey, Tuesday, Wednesday, I am on nothing, but what you're doing.

[00:35:40] **Carol:** So call me anytime, text me, do whatever we'll be in conversation with you. That's totally fine. On Monday, I've got to work on something else. So you use that day to gather anything you need and get it back to me, but you just have to be in communication with them and be open about when they can and can't actually contact you.

[00:35:57] **Adam:** Yeah. Yeah. We, I mean, when we first started, we had one customer and so yeah, we had our slack and slack has a single channel users, I think is what they were called at the time. I think they have a slightly different thing now where you can like bridge across to slacks and whatever. it was an interesting time, right?

[00:36:13] **Adam:** When we had one to our first leg, maybe three or four customers each got like their own channel, like a customer named channel in our slack. And we would have. The people that we were working with from their side that were like the software developers that were doing their side of our integration work or project managers, that sort of thing.

[00:36:33] **Adam:** And so we wouldn't invite all users into it, but just enough to be able to facilitate rapid communication and fixing things.

[00:36:42] **Adam:** I wouldn't want that permanently, but it has really helpful.

[00:36:47] **Adam:** And like Kara was saying, you got to set boundaries.

[00:36:49] **Carol:** It's super helpful when you're like in the initial design phase of a development project, because you don't always know what questions to ask until you're going at it. Right? So once I get in there and like, oh, we didn't even think about this. We didn't even think about that.

[00:37:02] **Carol:** And rather than having to put in a comment and my task and have it go to the customer and have them get back to it, I can just slack them. And then of course, because I don't copy and paste anything, I take a screenshot of the message. You can put the screenshot of the message in your ticket and there's your answer.

[00:37:17] **Carol:** So it does get things done that.

## [00:37:19] Meetings With Users

[00:37:19] **Ben:** I've always been enamored with this idea of having an office hours for customers, which I don't know if that would be good. Cause I, so, so the idea would be that let's just say Fridays from noon to four, some number of people will be hanging out in a zoom. Or whatever you use for video conferencing and just any customers can show up and ask questions or talk about frustrations or, talk about feature requests, et cetera.

[00:37:46] **Ben:** And I dunno, I think it would just be very fun and kind of community building. But then I also sometimes wonder if customers will be too cagey about having other people maybe accidentally hear what they're doing at work. And maybe it would be, maybe everyone would be too afraid to show up, but

[00:38:00] **Ben:** I've always loved that idea.

[00:38:01] **Adam:** I mean, I think we, we achieve mostly the same thing. It's a, it's less public, but what we do is just have standing meeting. With certain groups of people, newer customers or whatever, we'll just have like a meeting set up, it's Thursdays at four or whatever. And we show up in half the time.

[00:38:18] **Adam:** It's like, no, we've got nothing. So see ya. Or they'll email before the meeting. It's like, nothing's going on? Everything's great. So let's just cancel it this week.

[00:38:25] **Tim:** I have a term for there's certain meetings that you sit on, I get that, there's this big issue and we need you to, okay. So we set up this call and we've got our, our company's side and we have their company side. There's a whole bunch of people on their side. And as it progresses, you realize all you're really doing is marriage counseling because they have.

[00:38:45] **Tim:** Internally, right. They think is a software problem. It's not a software problem. It's a process problem on their side. And I've sat through like two hour meetings where the entire time they're all just talking to each other about what they maybe need to do differently. And so at the end of the call, there's actually zero action items on our side.

[00:39:05] **Tim:** And I will just straight out say, well, I enjoy this marriage counseling session. hope you guys can, sounds like you guys have some internal processes you need to work out and, hope everything goes well. Talk to you next week.

[00:39:18] **Adam:** Yeah.

[00:39:19] **Tim:** be billing you.

[00:39:20] **Ben:** one time and I can't cause any names here, but, one time we were working with a very large client and they were complaining to us that suddenly a lot of their users kept losing access to the system. And we were in the midst of setting up a new environment for them. And this is where they were seeing this behavior and it was going back and forth over support tickets.

[00:39:42] **Ben:** And, so we all decided to jump on a call and it was a really large company. So it's, it's called like 16 people from different countries. And the it department is from this country and the product managers are from this country. And some manager over here is different countries. So, it takes like 15 minutes just to get the call started and everyone to do all the introductions of who they are and where they work.

[00:40:01] **Ben:** And, and we wanted them to run through how they were configuring all of their users so we could get a better understanding of why everyone's losing access. So finally, a solid half hour into the call, we finally start to run through. The workflow. So the guy starts sharing a screen. He says like, yeah, I go into my El dab system.

[00:40:17] **Ben:** I don't remember what it was. And so, he's going through some sort of single sign on and he goes, okay. So to get ready first, I do this thing that kicks off all of the users so that I can then add this other user group. And we were like, wait a minute, you just started the square foot by kicking out all of your users.

[00:40:33] **Ben:** I'm like, why are we on this call?

[00:40:36] **Tim:** Well, there's your problem, rod layer.

[00:40:37] **Ben:** Can you just, can you stop doing that? But yeah, so we ended up being on the call for an hour because once we realized what was happening, then all of the different departments where they're talking about whether or not that's how we should be provisioning users. And then like, how do you organize user groups inside of your single sign on system?

[00:40:55] **Ben:** And everyone on our side, it was just sitting there watching them have this conversation. And in the end, the result was, yeah, just don't kick out your users before you assign new users. And it was exhausting. It was frustrating as Austin, but I, so I feel you that hit.

## [00:41:13] Prioritising Issues

[00:41:13] **Adam:** well, I want to jump back to Tim's 80 20 rule. another thing that I've seen is like every user, not every user does, but every user could potentially feel like the thing that's, bugging me right now about this one feature that I have to use once a month. is it as a top priority, I'm gonna create this ticket and I'm going to put it as priority at priority 11.

[00:41:34] **Adam:** because I really want it to be fixed. It's not important to me. and half the time you have to just be like, look, I can't run a business where I pounds on every trivial request from every annoying user, from every entry level customer, like your request has been noted now, get in line, be patient,

[00:41:50] **Ben:** Um,

[00:41:51] **Adam:** you know,

[00:41:52] **Ben:** I'll tell you. So I forget who the author is, but there's an author that talks all about. Hell. Yes. And if it's not a hell, yes, that's a no. So something to that effect, and there's a lot of people who have this mentality that if you're not doing the most important thing that you could be doing at this very moment for your business, you're doing the wrong thing.

[00:42:12] **Ben:** And I feel like philosophically, I understand that mentality, but practically something about it that doesn't feel right.

[00:42:21] **Adam:** Is that a Gary V thing

[00:42:23] **Ben:** Yeah. Probably,

[00:42:24] **Ben:** maybe. Yeah. Yeah. And then I think there's definitely a, what should we be working on now that maximizes value over the long-term. But I think you have to balance that with just doing lots of random stuff for users that may have a very targeted value, but not maybe be broadly applicable.

[00:42:42] **Ben:** And I don't know. It's like you got to scattershot a little bit. you can't just focus on the highest value items only because it just feels like you're

[00:42:50] **Adam:** Yeah. No, I totally get an agree with you there. I think I might've mentioned this previously on the show, but we do what we call, Big block of cheese day. So it's directly ripped from the west wing, if you ever watched that show. and I mean, the thing from the show was,once a year, I think it was once a year, they would, welcome any and all small requests from the public and they would just consider them and let you have access to a white house staffer to talk about your issue.

[00:43:17] **Adam:** and that way, like it gives the public a chance to be heard. and so we, have, a category, I guess you would call it in our ticketing system where, you can put in a ticket for whatever you want, but there's a good chance that we're going to mark it as cheese, which is means like we, this is something that we are not going to rush to work on, but there will be those days where we feel like, okay, now is a good time.

[00:43:42] **Adam:** take a day or two and fix 10 or 20 cheese tickets and boom. Now you've got this huge release announcement thing you can put out. You've fixed a whole bunch of little things for a bunch of people all at once. And I feel like that's a big win.

[00:43:56] **Carol:** really.

[00:43:56] **Tim:** Uh,

[00:43:57] **Tim:** I think that a lot of times with the smaller clients, right? the less profitable ones,they're a good opportunity to experiment, right? Because if the experiment goes wrong, there's not a whole lot on the line to lose. And that I do that sometimes I'll take a smaller customer that,they're really not that profitable, but I want to try.

[00:44:18] **Tim:** So it's, it's completely greedy and completely selfish, but I want to try something and I'm sort of, I'm going to experiment on them. I'm not gonna experiment. I'm like, my top 10 customers, right. I'm going to do it on the little guys. And if it works, then the big guys get the benefit of it later.

[00:44:33] **Tim:** But Yeah. they're a good place to, kind of Guinea pig.

[00:44:35] **Ben:** Yeah, I like that too. Especially if it goes well and then you can roll it out to everybody.

[00:44:41] **Ben:** Cause why not?

[00:44:43] **Tim:** Yeah. I actually been doing that kind of all week as a little tiny customer. I mean, we're in the payments business. they may be make a hundred payments a month. I mean, it's ridiculously small, but know we're trying something. I tried something new with them and it worked really well. So everyone else is going to get the benefit of it.

[00:45:00] **Tim:** So

[00:45:01] **Ben:** One thing that, we've talked about, I think before on the show,that it hits very close to home for me, which is this idea that I think engineers will want to over-engineer product teams will want to over-design things. And to some degree, I think if you can just get something smaller out to the users faster, it will usually just make them happy.

[00:45:22] **Ben:** And users don't need the huge giant end-to-end designed workflow for their problems necessarily be solved. And I think, keeping users in mind when you're in the design process is also very important.

[00:45:35] **Tim:** so small and fast makes them happy. Got it.

[00:45:37] **Ben:** Well, like, like you'll get a couple of users come to you and say something like, Hey, it would be really great. If there was a folder where I could see. Arbitrary documents so that I don't lose track of them. Right. So then your product team thinks, oh yeah, that's a cool idea.

[00:45:49] **Ben:** But then what if we had a whole document approval system? So it's not just storing documents, but now people can ask for approvals. And then maybe there is like a number of people who have to sign off before our document could be stored in there. Well, what if we version documents now? What if people can leave comments on different versions of documents and suddenly eight months goes by when you probably could have give someone a folder to put some stuff in a week and you end up wanting to design the better system, the quote, unquote better system before you solve any problems for the users at all.

[00:46:15] **Ben:** And I think product teams just have to remember why they're doing it. It's not to build a perfect system it's to solve user problems.

[00:46:23] **Carol:** Yep.

[00:46:24] **Tim:** true.

## [00:46:25] Former User Support Team Members

[00:46:25] **Adam:** The other thing is. The users that I have that tend to be troublemakers, like the ones that are doing it in a good way. Right? Like they, they break stuff and they let you know, and they want to understand, you'll every now and then you'll get a user that is like, they're curious.

[00:46:39] **Adam:** Those are the ones that I want to hire to be my QA testers. Right. Like, Hey, they're already breaking stuff. Right. Like I might as well pay them to break it and, make the product better.

[00:46:47] **Ben:** I'm almost certain that a non-trivial number of people on our support team. And I think a non-trivial number of our designers were originally just people who use the product and would write in tickets or reach out to Clark on Twitter. Just be like, Hey, I'd love to talk about the product. And then they ended up just getting a job.

[00:47:09] **Ben:** think it's

[00:47:09] **Tim:** Yeah, we have those too. we have former customers who are now work for us and do the same thing. So. Summarize customers and clients can't live with them. Can't kill him, but you need them. So,

[00:47:22] **Carol:** SAP, glad that they're putting in tickets and not just leaving your system.

[00:47:26] **Adam:** Exactly. they're complaining because of the.

[00:47:28] **Carol:** Yeah. They, more than likely have options. I could use something else.

[00:47:32] **Tim:** When they stopped caring, that's the problem.

[00:47:34] **Carol:** You're screwed.

[00:47:36] **Tim:** You just lost them.

[00:47:37] **Ben:** There was a, an episode of Seth Godin's podcast, akimbo, and I think he was talking about how it was support teams. There's three different types of customers. There's your super advocates. They're super excited about your product and everything. And his take on that was, there's really no need to service those people.

[00:47:54] **Ben:** Anyway. They just love your product. And then there's the middle of the road, customers who they don't love it, but they don't hate it. And you pretty much don't need to service them either because they're just middle of the road. They'll just keep chugging along. He said, really the entire value add of having a customer support team is for those people who just hate your product, because they're going to be the ones that you can actually turn around and turn into super advocates and heroes of the product because

[00:48:20] **Ben:** they, yeah, they come in with terrible expectations.

[00:48:23] **Ben:** They hate everything. Hopefully you can give them great customer support and respond to their issues. And then they suddenly become advocates because, oh, they're like, oh, this is so great. And like, your customer support is great. you're listening to me. I don't feel like I've been forgotten.

[00:48:38] **Ben:** And now these people become champions for you. I don't know. that's, I love that idea in theory. I don't know if I've ever done that myself in practice, but I do love it.

[00:48:45] **Adam:** Oh, that's not where I would have expected that to go. Right. I was with you on a, the people who love you kind of, no matter what, you don't have to do a whole lot to appease them. And I figured this was going to, it was moving toward haters. Right. and I figured they advice would be like, the haters are gonna hate you no matter what.

[00:49:01] **Adam:** Right. So some portion of them, you can't please all the people all the time. And so don't waste your effort. And the, I felt like the advice was going to go to. the people that you need to work to win over are the, like maybe that lower half of the

[00:49:14] **Adam:** middling people. So, yeah.

[00:49:17] **Adam:** I don't know. I mean, lots of different ways to look at it.

## [00:49:19] Patreon

[00:49:19] **Adam:** All right. Well then this episode of Working Code was brought to you by the disintegration of empathy and listeners like you. If you're enjoying the podcast, you should consider supporting us on Patreon support from listeners. Like you helps to keep the mics on and we appreciate every single one of you.

[00:49:35] **Adam:** Of course. we have to, thank our top patrons, Mani and Peter, and I want to send a special shout out to new this week. We have a new patron Sandy, welcome aboard. if you'd like to support us, then you can go to patreon.com/working code.

## [00:49:50] Thanks For Listening!

[00:49:50] **Adam:** you know what you should do right now, though, right?

[00:49:52] **Adam:** At this very moment, you should pause this episode and go leave us a review on apple podcasts. I mean, how else is apple going to know that they should be recommending us to other people who listen to the same other podcasts that you do? you should, make like totally relevant and timely referenced.

[00:50:06] **Adam:** Larry, the cable guy and head on over to workingcode.dev/review and get her done.

[00:50:12] **Carol:** Oh, my goodness.

[00:50:14] **Ben:** wondering where you're going with that.

[00:50:16] **Tim:** yeah, that was a journey.

[00:50:19] **Adam:** And I'm not going to apologize for it either.

[00:50:21] **Adam:** that's it for this week. We'll catch you next week. And until then,

[00:50:24] **Tim:** Remember your heart matters, even if you're an annoying user.

[00:50:28] **Adam:** oh, ouch.

[00:50:49]

## [00:50:49] Bloopers

[00:50:49] **Adam:** Okay. Here we go. It is show number 61. And on today's show, we are, ah, crap. I didn't even think about what I was going to say there. we're going to talk about what,

[00:50:57] **Adam:** So, yep. That's me. Ben, what do you got going on? No, wait, we came for Ben.

[00:51:03] **Adam:** Oh God,

[00:51:05] **Carol:** And the total roll

[00:51:06] **Adam:** thing is really throwing

[00:51:07] **Tim:** Wow. Someone's thirsty.
