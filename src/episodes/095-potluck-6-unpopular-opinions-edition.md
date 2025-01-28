---
title: "095: Potluck #6 - Unpopular Opinions Edition"
description: "This week on the show, we have ourselves an Unpopular Opinions potluck. This means sharing ideas for which we feel strongly; but, which may not be so popular in the broader programming community."
date: 2022-10-05
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/095-potluck-6-unpopular-opinions-edition/id1544142288?i=1000581663572"></iframe>

Sponsors

- [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

This week on the show, we tip our hats to the [Go Time podcast][go-time] and have ourselves an **Unpopular Opinion** potluck. This means sharing ideas for which we feel strongly; but, which may not be so popular in the broader programming community. Topics include password rotation policies (which are dumb), relational databases (which are stupendous), the technical ability of an executive leadership team (which is important), the user experience (UX) of forms (which is often over-thought), automated deployments (which should be based on tags), and code duplication (which can certainly be the right approach).

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[go-time]: https://changelog.com/gotime/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/095-potluck-6-unpopular-opinions-edition.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** If your form is sensical, I mean, you can create a nonsensical form where people make mistakes because your, your design is just terrible, but

[00:00:07] **Ben:** like,

[00:00:08] **Carol:** I I wish Tim were.

[00:00:09] **Ben:** right.

[00:00:10] **Ben:** right.

[00:00:11] **Carol:** favorite. Yeah. My favorite one is the credit card. One like a credit card form. It should just be standard that you do name,

[00:00:19] **Ben:** Yeah. That's true. That's

[00:00:21] **Carol:** put in your card number, put in the expiration date, put in your CVV when you flip those things. Guess what goes in that very first form.

[00:00:28] **Carol:** I put in my card number every time

## [00:00:31] Intro

[00:00:31] **Adam:** okay. Here we go. It is show number 95 and on today's show, we're gonna do a potluck, of unpopular opinions. So it's a potluck unpopular opinions edition. Tim, can't be with us this evening. Apparently he's in London getting plastered with some of our patrons.

[00:01:04] **Adam:** So hope you're having fun, Tim. off the top of the show, hopefully my audio quality is much improved over last week. I, I listened to it and wow. That was bad.

[00:01:13] **Carol:** you sound great now.

[00:01:14] **Adam:** yeah. Yeah. So got a new microphone. That was the problem. unfortunately I wasn't the cheap fix the cable. so, I figured double, double patron.

[00:01:22] **Adam:** Thank you this week, top of the show and we'll do it at the bottom of the show too. you know, cuz having those guys help us out guys and gals, enabled me to go get a new microphone.

[00:01:32] **Ben:** Heck yeah.

[00:01:33] **Carol:** Yay.

[00:01:34] **Adam:** so Tim's Mia. It would be his turn to go first. So he just loses his place in line. And, Carol, what do you got going on for your triumph for fail?

## [00:01:42] Carol's Triumph

[00:01:42] **Carol:** Well, I'm gonna pretend like Tim just gave us a great triumph because you know, he's traveling and drinking with friends and that sounds like a win. So that's one win. So I'm gonna throw a second win on it. Oh man. Okay. Well you can double your triumphs. It's fine. I'm gonna go to the triumph. So, I have just been feeling really overwhelmed.

[00:01:59] **Carol:** And while that doesn't sound like a triumph, I got handed this situation where I was asked if something was ready, for product review yet. And I immediately being a redhead and having somewhat of a temper flipped my switch and. What the hell are you asking me about this? Like what, from our conversations made you think that I would have this information for you?

[00:02:28] **Carol:** Well, I did not say it that way. That's just what I thought while I sent my coffee. but I did message my direct boss and I messaged my counterpart and said, Hey, what? From all of these conversations made this come across as it was my responsibility to deliver this by today, when nothing was ever like expected, there was no communication that said, Hey, we need to have this review and pointed by today.

[00:02:58] **Carol:** Like none of that happened. And it was just straight up, like miscommunication across the board and the expectations weren't laid out. But instead of going with what I wanted to say, which is like, what the hell are you thinking? I said, Hey, kind of, where did this fall short at? And. Just so you guys are aware, like to my boss and to my counterpart, I was like, just so you're aware, this is getting in my head.

[00:03:21] **Carol:** Like, this is frustrating me that I feel like I dropped a ball on something or that now product is behind because they had an expectation that I was going to deliver something today. And it's bothering me that I am putting people behind. So before I would've just grabbed it, did it and been like, okay, I don't know where it happened at, but here it is.

[00:03:42] **Carol:** I'm now gonna have to work two hours after and, you know, make up for some other project that got behind because I was doing this and communicated the question and got it across, got the solution in, got the process fixed. So this isn't happened going forward and didn't actually do the review and said, we will schedule to do this.

[00:04:01] **Carol:** And that's how it's gonna be going forward. But I just feel like I handled it better than I would have in the past. So I'm calling it a triumph that, you know, it didn't turn into a disaster.

[00:04:11] **Ben:** Nice.

[00:04:12] **Carol:** Yeah.

[00:04:13] **Ben:** Nice, nice restraint.

[00:04:15] **Carol:** Whew. I held back my ears burned a little, but I didn't yell. So it's a good thing. I'm remote. that's me. What about you, Adam?

## [00:04:26] Adam's Triumph

[00:04:26] **Adam:** Oh, I am having a wonderful week. and I was trying to think maybe half an hour, 45 minutes ago of like, what am I gonna pick for my triumph? and I just was, struck by how lucky I am to have so much to choose from. I've just had a really good productive week, I guess, you might say, or, or if you're a baseball fan, you would say that I've put down a lot of base hits this week.

[00:04:45] **Adam:** Right? Just project after project, after project that are all like single day projects, which was a really good week. but I think I'm gonna go with this and that is that, for various reasons. And, and maybe we can talk about this in today's topic. I have been using Microsoft edge this week, and like on a Mac, right.

[00:05:03] **Adam:** I'm not on windows and it's. Bad, but it's not as bad as I expected. Right. Like it's,

[00:05:10] **Carol:** I was about to. Why

[00:05:13] **Ben:** Yeah, like just for funsies.

[00:05:15] **Carol:** you just enjoy it?

[00:05:16] **Adam:** just for, so, okay. how do I tell, I'll try this short version here, right? So I love chromium, right? Especially the dev tools, right? I am in love

[00:05:24] **Ben:** Yeah.

[00:05:25] **Adam:** dev tools.

[00:05:27] **Adam:** I try, I try to avoid the Chrome monoculture.

[00:05:29] **Adam:** Like I, I like the Chrome browser. There's, I've got nothing against it, but, if everybody only ever uses Chrome, then that's bad for the web. I tried Firefox and had some issues with it, slow rendering. And the dev tools were not as good as Chrome dev tools. So I've tried a, a variety of other chromium browsers, including Vivaldi and one that's relatively new called arc.

[00:05:51] **Adam:** and you know, they all have their shortcomings and. I kept, you know, finding little things, death by a thousand paper cut sort of things. And so now I find myself on edge because I'm still trying to avoid the Chrome monoculture edges, chromium based. And I hadn't given it a fair shot yet. So I figured I'll give it this week.

[00:06:11] **Adam:** on Monday I installed it and set it as my default browser and I haven't turned it off yet. but, it's been a little frustrating here and there, but it's, it's fine. It's got a couple of things that are nice about it even.

[00:06:23] **Carol:** Okay. What's a nice thing. Give me one, you said there's a couple. Give me something.

[00:06:27] **Adam:** Yeah. So, the, if I like the way that it does, vertical or horizontal tab switching, right? So there's a lot of browsers that give you the opportunity, like a config setting to use vertical tabs instead of horizontal or, or

[00:06:40] **Ben:** didn't know that that's cool.

[00:06:41] **Adam:** horizontal. Well, in the tab bar edge, I guess by default, I'm sure you can turn it off, has like a button where it allows you to switch like on demand just by clicking a button in the tab bar.

[00:06:53] **Adam:** And that's, I've been making a little bit of use of that and that's nice.

[00:06:57] **Carol:** kind of cool. Okay. That's a cool thing. I'll give you that. Yeah.

[00:07:02] **Ben:** I, I tried to start doing more of my personal stuff in Firefox and my work stuff in Chrome, which I've, I've always used Chrome. And, and kind of to your point, like just to keep the multi browser system. it's really hard there. There's so many things that Chrome does really well. Especially the dev tools.

[00:07:24] **Ben:** The, the dev tools in safari are terrible. I think, it's, and it's not like, it's not like the functionality is bad in safari. The experience is bad, in my opinion, in the dev tools.

[00:07:36] **Adam:** I would say apple is a user experience company and, and so for them to have such

[00:07:41] **Carol:** They should be better. Mm-hmm yeah.

[00:07:44] **Ben:** it's hard. I, I started going back to Chrome, even for a bunch of my personal stuff, just cuz it's just more enjoyable. The one thing that Chrome does that I Firefox doesn't do and it was really sorely missed right off the bat. Was that in Chrome you can go into the settings and you can set up like, special phrases that you can put in the universal search.

[00:08:08] **Ben:** So I'll do MDN. For example, if I start a query with MDN, it'll automatically search Mozilla developer network and I'll, and, and I have a couple of those set up and Firefox doesn't have those. Apparently you can install an extension, but I'm like very anti extension. I just like, I want the thing to do the thing that I want.

[00:08:28] **Ben:** I don't wanna have to get something else to do it.

[00:08:30] **Carol:** Yeah. I like the whole box package, right? Like it should work out of the box. I shouldn't have to buy the add-ons.

[00:08:37] **Ben:** Yeah.

[00:08:37] **Adam:** I guess that's, that'll be good for me. Ben, how about you wish you're trying for fail.

## [00:08:41] Ben's Failure

[00:08:41] **Ben:** I'm gonna go with failure, but it's not like a huge failure. It's just sort of a, it's more of an, an emotional failure. So as I talked about on a previous episode, Invision recently had a very large. Reorganization to, to put it very politically correct. a lot of people were let go. And as part of that, the Invision board wanted to contract.

[00:09:04] **Ben:** they wanted fewer people on the board so that they could, my understanding is move more efficiently without having to get people involved. And I have been on the board for years and, but didn't really participate. I was mostly just a spectator. And so I was asked to resign from the board and I didn't think that would bother me so much.

[00:09:26] **Ben:** But then when I actually signed the, the document that says I'm no longer the, the secretary, I was technically the secretary also, it actually hit me really hard. I was not anticipating that and it, it left me feeling really gloomy for an entire day. And then on top of that, I had a conversation with my director of engineering.

[00:09:47] **Ben:** And he was saying that some of the stuff that I do at work has caused some kerfuffles. and I asked him, I'm like, why don't people just come and talk to me about that stuff. I feel like I'm a pretty reasonable individual. And he said that, people believed that I was on the board, so they didn't wanna, they didn't wanna poke the bear essentially.

[00:10:06] **Ben:** And so now I feel like not only did leaving the board hit me emotionally, apparently it was acting as some sort of a ground cover from interoffice politics. So I'm a little bit worried about what's about to come down the pipe and, hopefully I can meet it with grace and, compassion, understanding.

[00:10:26] **Ben:** I dunno. So I dunno, it was just an unfortunate emotional state this week, but, but I'm, I'm feeling better already even now just talking about it.

[00:10:38] **Adam:** Well, that's good. Yeah. I mean, I can totally see how that would be a situation loaded with emotion.

[00:10:43] **Carol:** Oh, yeah, yeah,

[00:10:44] **Ben:** you, you said you've been on it for a long time. I mean since the beginning. Really?

[00:10:49] **Adam:** okay. So like roughly 10 years then, yeah. Like that, anything that you did for 10 years, if you, especially, if you're asked to let it go,

[00:10:58] **Adam:** instead of if you volunteer to do it, you know, that's, that's gonna be very emotional whether you wanted to or not.

[00:11:04] **Ben:** it's, you know what it is too. It's like, I've always been the co-founder of the company and I've been on the board and I was briefly the CTO. And then I'm a, now I'm a principal engineer and it, it, it just feels like over the years there's been less and less stuff that has set me apart from any other face in the company.

[00:11:25] **Ben:** And. Not to be like too ego driven here, but there is an emotional residue. Let's call it from being on. I don't wanna call it a pedestal, but being like someone of some importance to now, I really, I really do feel like I'm just one of the engineers and because the company has had a lot of churn, I, I feel like there's probably a lot of people in this company who don't even know my history here.

[00:11:53] **Ben:** And that's, you know, that hurts a little bit, not in like a, not in a painful way, but in like a, I don't know, I don't know what I'm trying to say.

[00:12:02] **Adam:** I feel like I can relate to this, I, the way that you're describing it, I feel like I had very similar emotions when I made the choice to stop focusing my attention on CFML and started focusing as the community that I choose to belong to. And that I, you know, try to, focus my learning on, as like JavaScript is sort of my, my chosen family.

[00:12:24] **Adam:** and not that I'm not doing CFML anymore. It's just that now I do it begrudgingly. but you know, when I made that choice, I didn't expect it, but it turned out to be true that, I went from being, I, I'm not trying to toot my own horn here, but this is just kind how it felt. I, I went from being, a big fish in a small pond to, a planktons, you know, like some, some crust on the foot of a plankton in, in a much, much, much, much larger.

[00:12:50] **Adam:** Pond. Right.

[00:12:52] **Ben:** know exactly what you.

[00:12:53] **Carol:** Oh,

[00:12:55] **Adam:** and yeah, so it was a, I wanna say it was a rude awakening, but it wasn't, it wasn't that bad. It's just a, I think it was like you were saying it's a, it's a hit to the ego.

[00:13:03] **Ben:** Yeah. Yeah.

[00:13:04] **Carol:** Yeah. this week I got a text from a coworker that I worked with at my previous job. And it was just, she texted me and it's a picture of some code and it was a comment that I had put in the code base about something and just kind of explaining it. And she's like, you will forever live in our code, like in our source code.

[00:13:23] **Carol:** And I was like, Aw, you know, it's like, it's nice to feel like you had some value and that people realize what you did mattered there, even though you're not there anymore. So it was super sweet.

[00:13:34] **Ben:** that is.

[00:13:36] **Carol:** yeah,

[00:13:37] **Carol:** does that make coding like a superpower, like, you know, the average person, you know, you die and then, you know, within, let's just say like three generations you're, you're forgotten. you're gone. Yeah.

[00:13:49] **Adam:** gone. The code you wrote, especially the bad code you wrote is probably gonna live on for like, at least twice as long, if not like four times as long.

[00:13:59] **Carol:** It, yeah. So actually that's what I responded back with. I was like, it's funny. I was like, I questioned the code I wrote last week. So I wonder what I would think if I looked at what you sent me that I wrote five years ago. Right. And she's like, yeah. She's like, it's not often that I look at my old code and I turn around and high five myself for what I did.

[00:14:17] **Carol:** I'm like, yeah, same.

[00:14:21] **Ben:** all right. Groovy. Not, not a bad showing of triumphs and fails today.

[00:14:25] **Adam:** No.

[00:14:26] **Carol:** No, I think we did.

[00:14:26] **Ben:** Yeah.

## [00:14:29] Key/Password Rotation Is Dumb

[00:14:29] **Adam:** all right. So let's get into our potluck here. it's gonna be unpopular opinions edition. I'll go first. this is not a fully formed opinion, but I'm just gonna say it anyway, because it will definitely be unpopular.

[00:14:40] **Adam:** And so, you know, I'm still figuring it out, but I think it's possible that requiring password change, like a password reset or rotating, like API keys on a short recurring schedule is entirely wasted time and, and effort. Like it's just dumb and that, I mean, I, so I say that, I guess for me with the caveat that it it's dumb, as long as you have a, a good security posture authorized, right?

[00:15:10] **Adam:** Like your passwords are. Actually strong, you, are doing the things that you're supposed to be doing to prevent security intrusions. You have, you know, a web application firewall, and you're doing all, all the best practices to, you know, prevent SQL injection and, and exercise and all this other stuff that like could give people an avenue into your stuff.

[00:15:32] **Adam:** You're doing penetration testing from actual professional penetration testers. Like if you're doing those things. Then 99% of the, the mental and physical effort of changing your password every three months or whatever it is and rotating your API keys. Even if it's like only once a year, it's still, you know, it's gonna take you 10, 15 minutes to do that.

[00:15:57] **Adam:** And 99% of that effort is just being frustrated that you have to do this again, right? Like it's not actually getting or anything and you know, oh, another part of that, good security posture, I would say is event based key rotations are not included in this, right? So if somebody leaves the company and you, and they had access to keys, now you have to rotate those keys.

[00:16:15] **Adam:** That's not what I'm talking about. I'm just talking about time based

[00:16:19] **Ben:** Hmm.

[00:16:19] **Adam:** key rotations. So I think it's dumb.

[00:16:23] **Ben:** I, I think I tend to agree with you on this. it, it's funny cuz when people talk about things like encryption strength and password strength and they talk about You know, like the number of operations modern computing can do.

[00:16:34] **Ben:** They're like, oh, someone could undo this hash in, you know, 15 bajillion, Terra flops an hour. And, and to your point, I'm like, yeah, but you can't make that many requests to my application without being blocked. Period. Like, you know, CloudFlare is gonna block you for a DDoS attack or our application logic is gonna say, well, you failed to enter the right password 10 times.

[00:16:57] **Ben:** So we're just gonna block all your requests going forward. It like you'd in order for some of the brute force stuff to make sense, you'd either have to have a a really severe security vulnerability to begin with, or someone would have to have access to your raw database. And like, I mean, at that point you're kind of hosed.

[00:17:16] **Ben:** Anyway, it just seems, so, so I agree. That some of these things seem hypothetically important, but not necessarily practically important. It's like, I remember one time I was reading an article where this guy was railing against the use of a JWTs jots for session storage. the argument, I forget what the argument was as pro jot. And someone was like, someone was like, oh, well, it's, it's more secure than a cookie. And the guy was like, yeah.

[00:17:47] **Ben:** But, for example, if you can, if, if someone can do a, a persisted cross site security issue and they can inject code into your application, like, it doesn't matter how you're storing your, your session tokens. Like you're already hose whether or not it's in a cookie or a jot. If someone can start making requests your application on behalf of another user, the storage mechanism doesn't makes it doesn't matter at that point. anyway, sorry. So

[00:18:13] **Adam:** being pounded.

[00:18:16] **Ben:** so, yeah, security.

[00:18:17] **Adam:** All right. Well, that's mine. somebody else can go.

## [00:18:19] Relational Databases Are Awesome

[00:18:19] **Ben:** I I'm just gonna say that I love relational databases. I grew up on relational databases. It is by far the vast share of my experience. relational databases will just be my default selection going forward until I have a reason to not use a relational database. And that's not to say that I don't like some of the other databases.

[00:18:41] **Ben:** I'm a big fan of Redis. Redis is pretty cool, but it's, it's like peripheral stuff to the application. It's not the thing I would use. Mongo, I've dabbled with a little bit at work and it's just not, doesn't spark joy for me. And, I find relation databases very easy to work with. I love writing SQL.

[00:18:59] **Ben:** I, I. I don't connect at all with people who think that SQLs like a funky, clunky language, to me, writing ands and OS seems so much more natural than doing like dollar sign and in passing in a raise of conditions that, or together for document databases. So I just I'm so pro relational databases

[00:19:22] **Carol:** Yeah, I get it. I feel like a lot of what I develop is just how I'm using the data. Right. So I'm constantly like with what I'm developing, I'm like, How is this all related? Like, what am I using with it? And maybe you could do that with, like a document database, but I'm like with relational database, I can just go, Hey, this is tied to this and this is how it's tied to it.

[00:19:42] **Carol:** And I know exactly how to get there. And it reads like English to me. And I don't have any questions about it and I don't have to worry about states of anything. Like I know exactly what it is at all times. So I feel like when I'm writing a function, it's just about taking data and putting it on a screen, saving the data and then displaying it back.

[00:20:00] **Carol:** That's what our applications do. So

[00:20:02] **Adam:** Ben, I wonder who you surround yourself with. So my, my gut reaction here was I think that the only thing unpopular about this opinion is that you think that it's an unpopular opinion because, like,

[00:20:15] **Carol:** think it's unpopular

[00:20:16] **Ben:** I I think, yeah, maybe it depends on the circles.

[00:20:19] **Adam:** yeah, yeah, yeah. And that's what I'm getting at is, you know, like I I'm sure that relational databases are unpopular in certain circles.

[00:20:26] **Adam:** I, I think we've kind of touched on this before about like, you know, certain people, maybe people newer to the industry, you know, they, they start by following some guide, some tutorial on learning programming. And the first thing that they're introduced to is Mongo or something. And so that's, that's what they cut their teeth on and that's what is familiar to them.

[00:20:43] **Adam:** And so the idea then for them of SQL and relational databases becomes weird and, and other, but I think that. It, it, the circles that I run in, the, the articles that I read, the, you know, that sort of thing, the non relational databases, document databases, and that sort of thing seem to be other to

[00:21:04] **Ben:** Mm. All right. That's

[00:21:05] **Adam:** you know, and it, it could also be a case of like, everything that needs to be said about relational databases has been said, not that not that we need to stop talking about them, but like, we've kind of covered all of that ground.

[00:21:20] **Adam:** And so it's mostly people rediscovering things or, or, you know, solving different problems with the same techniques that gets discussed versus, you know, these newer technologies, document databases and things that are, more fertile ground for explaining things that people don't already understand.

[00:21:38] **Adam:** And so that's why maybe they get discussed more.

[00:21:40] **Ben:** That could be, that could certainly be, it, it could also be that when people are pro relational databases, it doesn't register in my brain. But when people are like, well, actually MongoDB allows you to scale to 15 simultaneous nodes. I'm like, hold on bro. And like, it sticks out in my head. I, I also, it seems to me like a lot of the document databases or let's the NoSQL databases solve problems that I will likely never run into.

[00:22:09] **Adam:** in terms of scaling. So I I'm sure that there are reasons to use them that are very persuasive in certain contexts, but those are not the default context for anything that I've ever worked on.

[00:22:23] **Carol:**

## [00:22:23] Executives Should Understand Code And Technology

[00:22:23] **Carol:** Okay. I'm gonna go with one. So it's not really super techy, but it's one that I've seen in the past. So you bring executives in to manage the company or run this company, but they have no idea of what, like the actual technology is that we're using. Right? So maybe, you know, the industry, but you don't actually understand software.

[00:22:45] **Carol:** Like our company is a software company. Our company like does nothing but software. If you don't understand code, if you don't understand what it takes to deliver a product based off of engineering side, I don't understand how you can do your job. So I struggle with that because people make decisions based off of, we think it looks like this, but in reality, when you're on our side of the house, it's completely different.

[00:23:09] **Carol:** And I don't know, I dunno if it's actually like an unpopular thing, but I'm just like, I feel like executives should, if you're running a software company, You should have started in code. You should know what code is. You should be able to read it. You should have an understanding of what engineering actually is and what it takes in order to run a software company.

[00:23:29] **Ben:** So it's a silly one, but it's one I'm

[00:23:31] **Ben:** no, I think I, I,

[00:23:33] **Carol:** close to

[00:23:34] **Ben:** I tend to agree. It's funny. So in the early days of Invision Clark, who was the CEO was formally, an engineer, not an Invision, but at previous things, he, he was a ColdFusion developer. And, in the early days it actually cost a lot of contention because someone would talk about a feature that we wanna build and they'd say, oh, it'll.

[00:23:56] **Ben:** Three weeks to build this. And he would say, isn't it just a database query though? Like what is actually making that so complex? And we'd always be like, oh dude, you're oversimplifying it. There's so many more moving parts than you realize. But I think there was actually a very healthy aspect to that, that he could, to some extent, you know, with varying degrees of accuracy, call BS on, on people's estimations, because even in his oversimplified view of how the application worked, he understood enough from a technical standpoint to be like, cut the crap.

[00:24:32] **Ben:** Like it's actually not as complicated as you think it is. Let's be more reasonable about how we wanna approach it. And I think there's when a, when a manager can temper the, the sort of engineers pension for over architecting, I think that can be a really healthy relationship.

[00:24:50] **Carol:** Absolutely. It stops things up front. So maybe they are like over architecting something and you're kind of like, Hey, this is can be much simpler. Let's think about it again. Or like even having the boss say, Hey, isn't this just a database query? And you're like, Hey, actually, no, it's not just that let's have the conversation.

[00:25:10] **Carol:** That's healthy too. Like both sides of it are good. But when you have someone who has no idea, you're kind of just having to bat at what you can and hope you hit the ball somewhere and make 'em happy. So.

[00:25:21] **Adam:** Okay, you got another one, Ben.

## [00:25:23] Form UX Is Overrated

[00:25:23] **Ben:** yes, I will go with, I think people overthink the user experience of forms. There's a lot of handwringing that I see happens around the richness of reporting errors and making form interactions very compelling. And as a user, myself, of many, many forms, I feel like the richness of a form just really doesn't matter that much to me if I come in

[00:25:52] **Carol:** do you mean? What do you mean by the richness of a form? I don't know

[00:25:55] **Ben:** so, so it's like, the degree of effort you wanna put into relaying the state of a form, what's going well, what's not going well.

[00:26:04] **Ben:** So for example, let's say I have a form of a couple of inputs and I, and I hit submit. And one of those inputs is invalid. I could, for example, just put a banner at the top and say something went wrong, right. That's not a great experience. Or I could say, Hey. Social security number is supposed to be nine digits.

[00:26:22] **Ben:** And like that's definitely better, but then some people might put that error message actually next to the social security form and outline that input in red. And like at some point there's a diminishing return on investment. And I think that happens way earlier than people actually think it does because, you know, if I wanna fill out a form, it it's gonna happen.

[00:26:45] **Ben:** Like I I'm gonna make it happen. And, and the, like where you report your error messages and whether or not you outline your inputs in read and like whether or not you fade in a message as opposed to just refreshing the page. Like, I just, I don't know. It seems like people over index on trying to make that as rich and compelling as possible.

[00:27:06] **Carol:** So I've got two things, one whenever a form loads and I fill out everything and it just says something didn't save. Like something's not right. I get pretty pissed off. So then I just call someone. I'm like, I'm not filling it out again. Like if you guys, I am going to call you and you're gonna fill this thing out for me now, because you've wasted my time and I'm mad.

[00:27:31] **Carol:** But the other thing is that if you expose a lot, then I'm very curious. So I might have. Paid my county taxes with an AMAX card when they don't take AMAX cards, because they popped up a banner that said we don't accept AMAX cards. And I like right. Clicked on it and did the debugger, and then was like, oh, I can just bypass this and put in my card number.

[00:27:57] **Carol:** And it processed the payment because I wanted my Delta points. Okay. My property tax is expensive and I put it on my credit card to get the points. So I get to fly for free. Right. So I was like, after doing that, I realized that when you expose too much in what the errors are, people can bypass them too.

[00:28:14] **Carol:** If you don't have everything shared up on the back end. Right. So I was like, there has to be a healthy level of just enough information to know that you don't have it quite right. Let's fix it versus it's wrong. You figured out yourself. So

[00:28:29] **Ben:** Ah, to, to be a developer and know how to bypass things.

[00:28:32] **Carol:** Yeah. Hey, I like points.

[00:28:36] **Adam:** maybe to, to prove your point here, Ben, I disagree. maybe, you know, I guess the, a total disagreement would be that like, it's impossible to have a form UI that is too rich, right? Like there no such thing as too rich. And I, I don't agree with that, but I will say that, like, I think my bar for what is, what we should be aiming at is probably higher than yours.

[00:28:59] **Adam:** I like, you know, as I'm, as I'm tapping through foreign fields, I like it when it turns green after I tab out and it's like, okay, cool. I didn't mess that one up. Right. I like it when the error message appears as I tab out and I don't have to wait, like get down to the bottom of a 300 input form and hit submit to find out that, you know, fields 17 and 37 and 49.

[00:29:20] **Adam:** And you know, all of these are, are messed up. Like help me while I'm at the thing, what, like, while I'm doing it,

[00:29:27] **Ben:** Well, it's so funny that you mentioned the, the tabbing away. Cuz one of the things that drives me nuts is I will often, command tab on the Mac. I don't, I don't or alt tab, I think on windows, I will command tab into my one password application. To find my, my password for a particular login form and the act of doing that will oftentimes immediately throw up an error because I, I unfocus my password field and they'll be like, no, your password's invalid.

[00:29:56] **Ben:** I'm like, bro, I didn't even enter my password yet. And you know what? It's like the input form has two fields on it. It has email and password. You don't need to tell me that my password form was empty. Like I'm gonna hit submit and it's gonna tell me my login's not correct. I like you don't. So, so, and I guess, I guess so that also going back to the databases for a second, cause I think there is like a parallel metaphor here, which is that document databases, I think do legitimately have certain scaling characteristics that, that are harder to achieve in a relational database and that's fair, but that's also a very specific edge case, or I don't wanna call it an edge case.

[00:30:39] **Ben:** It's a very specific context. Most forms are very small in my experience, like a handful of fields. And I think people will often try to solve all form interactions the same, so that like you're saying, I don't wanna get to the bottom of 50 fields and then realize that the third field was wrong, but most forms don't have 50 fields.

[00:31:02] **Ben:** And, and to apply the same rigor of richness to the email and password login that you do with the I'm filling out a, a, you know, a mortgage application. Yeah. Yeah.

[00:31:15] **Carol:** Yeah.

[00:31:16] **Ben:** So I don't know. I just, I,

[00:31:17] **Adam:** I, I don't completely disagree with you, but, you need to install the, the browser extensions that allow you to just hit a keyboard shortcut and it auto fills your password from one password. You

[00:31:30] **Ben:** you.

[00:31:30] **Carol:** yeah, you do need

[00:31:32] **Ben:** So I actually just did that because I, I did have that sense that I'm really missing out on some wonderful experience here. And for whatever reason, it only works on a tiny fraction of the forms that I fill out. I don't, I don't, I think I'm doing something

[00:31:45] **Ben:** wrong.

[00:31:46] **Adam:** okay. So it sounds like you're creating your one password entries by, like manually entering

[00:31:51] **Ben:** Yeah, yeah, yeah. Yeah.

[00:31:52] **Adam:** up, it's say add to thing. Well, when you create them, by like the first time you log into the website, in the browser with the extension installed, it says, do you wanna save this to one password?

[00:32:01] **Adam:** You click? Yes. Not only does it save the username and password that you submitted, but it saves the URL that you were at too.

[00:32:06] **Adam:** That's how it

[00:32:07] **Ben:** Oh, so maybe my URLs are wrong.

[00:32:09] **Adam:** belonged to that form. Yeah.

[00:32:11] **Carol:** Right. And it'll also do things like whatever the form filled is. Right. So it'll be like, oh, I see it's been here versus like an actual name. And it saves all that for you. Yeah.

[00:32:21] **Ben:** Yeah. I, I do gotta get better about that because it is frustrating to command tab to my one password, all the.

[00:32:27] **Carol:** Yeah. The other thing I see with one password sometimes is I'll be on a site like local working and I'll get these weird console, like messages or console errors that pop up and I'm like, what's going on? And it's like, one password is trying to populate something and I'm like, how did that even start happening?

[00:32:44] **Carol:** So I have to like, stop it. And I'm like, oh, okay. Yeah, still don't know what's going on with it. But that's seeing pop up every now and then. And one more thing about your rich UI with forms, right? So what drives me nuts when I'm on the form is when tab stops working is like around date pickers and things where you hit tab and like a window pops up and it's like, oh, select this other thing.

[00:33:07] **Carol:** And you select it and you hit tab again. And it either like re circles you back into that field, or it's just gone. There is no more understanding of where tab was and you have to go click. I get so mad. So everything I write, if I'm ever working with user interface, I make sure when I'm done, you can hit tab and get through every single input with no Interac with like no interference.

[00:33:30] **Adam:** Mm-hmm

[00:33:31] **Carol:** yeah.

[00:33:32] **Adam:** oh yeah.

[00:33:32] **Adam:** I did, a form design for an event registration flow, and there's a lot of optional fields in it. Right. So like, you know, this is for universities. So you've got your first name and middle name and last name, but then you might also have, a different name than when you were in school.

[00:33:46] **Adam:** Right? A different, last name, right? Like traditionally we would call it a maiden name, but we're moving away from that,

[00:33:52] **Carol:** Thank you it's appreciated for some of us. Yeah. Yeah.

[00:33:55] **Adam:** But, yeah, so it is like last name at graduation or something like that, but there's that there's nickname, there's, you know, a bunch of these like hidden fields.

[00:34:01] **Adam:** And I made it a point to make sure that, you know, not only is the tab order, right. When the page loads and the, the fields are hidden, but then as you start to expose other fields by clicking on things and you can tab to the links that, that expand those things, that every time you make a change like that, that the tab order stays.

[00:34:18] **Adam:** Right?

[00:34:18] **Carol:** Stays in order. It's key.

[00:34:21] **Adam:** Yeah.

[00:34:22] **Carol:** how do you screw that up? Like, just go through the page when you're ready to deploy. Make sure you can tap through it. It's so simple. Yeah.

[00:34:30] **Ben:** Yeah. The, the, the one that gets me sometimes is when people will take a piece of input and break it up into several input fields, and then they get very aggressive about auto tabbing. You like auto moving you to the next field. A lot of times that will happen when you're for like typing in a social security number, or you're typing in some sort of a, like a two-factor authentication code.

[00:34:54] **Ben:** And every now and then I'll have to go back and delete something in the middle of that. And it's like, it's constantly trying to move me to the next input. I'm like, no, I'm still editing. I'm still editing.

[00:35:02] **Adam:** Yep. That's frustrating.

[00:35:04] **Ben:** think it's also worth saying, and maybe this is because I. An engineer and a developer and I spend my whole day typing or whatnot, but I, but I do think most forms are filled out correctly. The first time I, I, I think we approach error handling in a form, like it's the default experience for users. And I, I have to believe that it's, it's, it's like a small number of interactions with forms actually lead to errors.

[00:35:34] **Ben:** If your form is sensical, I mean, you can create a nonsensical form where people make mistakes because your, your design is just terrible, but

[00:35:42] **Ben:** like,

[00:35:43] **Carol:** I I wish Tim were.

[00:35:45] **Ben:** right.

[00:35:45] **Ben:** right.

[00:35:46] **Carol:** favorite. Yeah. My favorite one is the credit card. One like a credit card form. It should just be standard that you do name,

[00:35:55] **Ben:** Yeah. That's true. That's

[00:35:56] **Carol:** put in your card number, put in the expiration date, put in your CVV when you flip those things. Guess what goes in that very first form.

[00:36:04] **Carol:** I put in my card number every time. And the second form says, oh, we can't have like, alpha like characters in here only numeric. And then I look at it and I'm like, well, why did you ask me for my card number first? Like you idiot. Everybody does first name, thing, card number. It's just standard. Oh

[00:36:22] **Ben:** Yo, sorry. So on that note, I feel like sometimes I want to take almost like a, a moral objection, stance. I mean, that's not the right phrasing, but, but, so, so if you can imagine a signup form for, for an application and you have to enter your name, your email address, and a password, and then someone comes along and says, Hey, actually we get like half a percent more conversions.

[00:36:46] **Ben:** If we do email first and then name and then password. And I wanna be like, I don't care. I don't care. The name should go first. No, one's putting email then name that's way unnatural. It doesn't. It's like, I, I don't care what your statistics say. Your, your, your compass is wrong.

[00:37:04] **Carol:** Yeah,

## [00:37:05] Address Line Order

[00:37:05] **Adam:** okay. Okay. Hang on. Hang on. While we're talking about form field order, here's the unpopular opinion country should come first in address. country and then zip code, you go

[00:37:17] **Carol:** actually that makes

[00:37:18] **Adam:** broadest broadest to

[00:37:19] **Adam:** least broad. Right? So like your, your street address should be the last field because, or it depends on whether or not you include the name in that.

[00:37:26] **Adam:** But, for example, we have a, a form where we validate that the zip code matches the country that you've chosen. Right. So, if you, and, and this is a form that does some, feedback as you type, right? So you enter your zip code and it's like, okay, this looks valid. and then if the, the, the traditional thinking is country is last.

[00:37:48] **Adam:** So your zip code is before that. And then, so you've en energy, your, you know, Antarctica, zip code, whatever that happens to be, which might not be the same as the, the default country. and then, then you go and you change the country, and that changes the validation rules for the zip code. Like. But, and that's the thing is like, I, I think all of the developers that I talked to about this completely agree, but the general public is not ready for it.

[00:38:10] **Adam:** We tried that, just like, okay, here's our,

[00:38:12] **Carol:** You can't change the world. Yeah.

[00:38:14] **Carol:** Yeah. Here's our registration form. And, and it's the right way. It's like, you know, it's like a date, right? The only, the only way to the proper way to format a date is your month, day period. There's no question. I'm I will not be taking questions on this Um,right. So similar with addresses, right. It should be like, you know, country, zip code, state, city, whatever. Phone numbers have changed that. So whenever you go to put your phone number in somewhere, it's like the very first thing you do is select the country so that it gets the, the routing number. Right. So if you do us, it's like plus one or whatever it is for any other country. Sorry. I don't know them. Phone, phone numbers have moved to that addresses have not yet.

[00:38:57] **Adam:** Yeah, no, that's a really good point cuz in this exact same form, we have a phone number field and it has the little country drop down before that. But it's it, what it is is it's the country prefix code, right. Like plus one for the United States and, and we have flags in there. And so

[00:39:13] **Ben:** like visual flags, you

[00:39:15] **Ben:** mean? yeah.

[00:39:17] **Adam:** Picture pictures of flags. and you're, you're absolutely right. And it makes me wonder, could we just put something very similar? Like no, no. Plus one for United States, but just like the flag

[00:39:26] **Carol:** A flag. I would

[00:39:27] **Carol:** select it.

[00:39:28] **Carol:** Yeah.

[00:39:29] **Adam:** the zip code.

[00:39:29] **Adam:** Right? Hmm.

[00:39:31] **Carol:** select it.

[00:39:33] **Adam:** Anyway, what I was gonna say was like, we, we tried to, to kind of push this viewpoint on the world, in our forms.

[00:39:38] **Adam:** And immediately when we showed it to our customers before they even showed it to their constituents, they were like, yeah, we're gonna need you to change this around. This is not gonna fly. I.

[00:39:50] **Ben:** I, I I'll tell you, I, as a consumer, I have definitely been on an e-commerce style website where they want you to put in the zip code so they can immediately give you estimates on, on shipping costs.

[00:40:01] **Carol:** shipping. Yeah. Yeah.

[00:40:03] **Ben:** and I, and I still, I still would rather have the zip code at the end. I don't and it's, and I, and I have no logical explanation for that.

[00:40:10] **Ben:** I think it's just 40 years of, of doing it one way. It's hard to switch in the same way that I want my name to come before an email. Yeah.

[00:40:20] **Carol:** No. See for me, I am the person that would like to see it off flip. I'm kind of with Adam, like start me with a country. Let me give you a zip, because then I know when I start typing in my street name, it's gonna be such a smaller, like result set because it's gonna be based off of the city where I live at.

[00:40:36] **Carol:** Right. It's not gonna be based off of every single street that starts with a letter in that could possibly like be a match to it. And things are just gonna be more efficient

[00:40:45] **Ben:** I'm always suspicious when I enter a shipping address and I'll be like, it's 1, 2, 3 Smith court and I'm spelling court as CT. And then you go to submit it and they're like, you use this, but we have this on file. And it's court spelled out as C O U R T. And I, and I just always default to whatever they chose, because I just assumed that whatever they had is gonna get my product here faster.

[00:41:09] **Ben:** And with less error, but there is something very unsettling about that that like, why doesn't every site have to do that? Like, why are you doing that? Is your delivery process much more brittle that you can't understand the address that I've been using for the last 20 years? That I don't know. It's weird.

[00:41:28] **Ben:** I don't, I don't like it as an

[00:41:30] **Ben:** experience.

[00:41:31] **Carol:** Yeah, no, I get what you're saying. But like from previous software and current software, we do a lot with physical addresses, right. So we do validate against what is in registries, right? So while you may be putting CT, all the registries may be saying court, and it's just an easy way for us to validate without any manual check that says it's actually that. So other than that, I have no idea. Just send it. If it doesn't go, it gets returned. It's your own fault. Yeah.

[00:42:01] **Ben:** all right. What's next.

## [00:42:03] Not Deploying Every Commit

[00:42:03] **Adam:** I got one. I'll go. so I I'll, I'll start with this. I don't think that you should auto deploy every commit to your main branch,

[00:42:10] **Adam:** which,

[00:42:11] **Adam:** I say that, but I'm also a huge proponent and fan of automation, especially automatic deploys. I just think that instead of deploying every. you should deploy every tag instead.

[00:42:24] **Adam:** And I say that because I think that this is an unpopular opinion because, I don't think I've ever seen a guide or a blog post on the idea of automating your deploys based on commits that talks about doing it from tags. It all, it seems to always be based on a commit.

[00:42:40] **Adam:** And

[00:42:40] **Ben:** sorry, just, just for our listeners context here, you're talking about, for example, something like Netlify where I have it hooked up to a repo. And I commit to my main branch and then Netlify is like, oh, I see you committed to your main branch. So I'm now gonna deploy that as a static site. Like that's is that what you're talking about?

[00:42:58] **Carol:** Oh,

[00:42:59] **Adam:** yeah, I wasn't even thinking about Netlify. I was like, thinking about my

[00:43:02] **Ben:** It's just like the lowest, the lowest hanging fruit in terms of complexity. Yeah.

[00:43:06] **Adam:** yeah,

[00:43:07] **Adam:** part. of the reason that I think that it should be tags instead of commits is because sometimes, you know what, if you have five poll requests that you need to merge and you just want them all to be merged

[00:43:16] **Ben:** yeah.

[00:43:16] **Adam:** and one deploy

[00:43:18] **Ben:** also for the ability to roll back. Right? So instead of, if you need to roll back, well, which commits were deploys, right?

[00:43:28] **Carol:** Yeah. That's where I would struggle with it though. Cause if you're doing a tag and you're saying like, I have five things that are going out with it, the rollback would then include everything in that five tag. Whereas like right now, what I do is I roll back the single merge, right. It's like, okay. in Maine, in Maine, let's pull it.

[00:43:45] **Adam:** that would be an option, right? If, if you are doing those incremental releases and you're actually doing deploys after only, you know, one merge or whatever one poll request. it would be functionally identical, except that you would be tagging the releases to, to trigger that automation.

[00:43:59] **Ben:** that every tag would be a deployment or, or would the tag have to have like a special prefix or something?

[00:44:06] **Adam:** no, I mean, that's an interesting question, I guess, I'm not a heavy user of tags currently. We're, we're kind of moving in this direction. We're starting to use tags for deployment, after having some, experience over the last year or so, trying to auto deploy every merge to our main branch.

[00:44:21] **Adam:** I could see a use case where you might want to have a series of tags that don't get auto deployed.

[00:44:27] **Carol:** Yeah, I really need to read about this more, cuz I don't understand how you would stop it.

[00:44:32] **Adam:** well, so there's like. Carol the thought the thing you brought up that I wanna make sure it doesn't get lost here is, you know, something break, you do a release, something's broken, you need to fix that. Right. You have a couple of different options. You could fix the bug and

[00:44:45] **Adam:** do a, a new release with that.

[00:44:46] **Adam:** Right. And so that's not a rollback at all. That's just, you know, another

[00:44:50] **Adam:** version number, or you can roll that entire tag back, I guess the, the thing is, it, it, it very much depends on the way that you do your releases, right? So if you are, if your team strategy is to pile up 10 things that all need to be, you know, that all get merged on the same day, and then you do a release halfway through the day or whatever, then, yes.

[00:45:11] **Adam:** If you did need to roll back, then all 10 of those things would

[00:45:14] **Adam:** go

[00:45:14] **Adam:** back

[00:45:14] **Carol:** it would.

[00:45:15] **Adam:** or, I mean, alternatively, if this is where it gets tricky, because if you and we get into the particulars of the tech, but if you revert the commit that creates a new commit that undoes the previous commit. And I don't think off the top of my head with get that you can do like a undo of your revert.

[00:45:35] **Adam:** I guess you can revert

[00:45:36] **Adam:** the

[00:45:36] **Carol:** You can revert the revert. Yeah. You can revert your revert. Yeah.

[00:45:40] **Adam:** yeah. But now, now we're getting into dangerous, like metalevel stuff here.

[00:45:45] **Carol:** I don't like doing that.

[00:45:46] **Adam:** yeah. So yeah, like there's, there's pros and cons, I think, but I think if you are, if you are considering doing deploys for every commit, I think tagging would be better because it's more explicit

[00:46:00] **Ben:** that's interesting.

[00:46:01] **Adam:** favor of explicit.

[00:46:03] **Carol:** Yeah, I need to see it on paper. Like this is one of those things. I need to see some like lines and some dots and some understanding of like, where things are going and where they exist and how they come back out before I say yes or no to either. Cuz I'm so used to just doing the work, getting it ready, having my branch out there, it merges into Maine and then it deploys, right?

[00:46:23] **Carol:** Like that's, that's the point. And that's when I know my database has been deployed as well. And I have rollbacks for both the. Database and for what would happen if code fells? Right. So the thought of a tag needing to roll back, like scares me because we would have possibly a ton of database rollbacks that would need to go with it.

[00:46:45] **Carol:** But in reality, maybe only one of those things needs to come out. So why would I wanna roll back my database to that point?

[00:46:51] **Ben:** at work, at least our, our database and our code sort of evolves independently. And what I mean by that is oftentimes. We have to change the database before we change the code in order to get it ready.

[00:47:05] **Carol:** I think that's kinda normal, right? Like we deployed database

[00:47:08] **Ben:** So, and I, and I say that only to say that when I think about rolling back code, I'm often not thinking about the database only because the database is hopefully a little bit backwards compatible, just because it already had to have been updated before the code went out.

[00:47:24] **Adam:** Yep.

[00:47:25] **Ben:** sometimes you get in a really tough situation where you deploy something and it starts writing new data in a new way. And then you, like, you can roll back the code, but the data's already there and now you've sort of lost it essentially.

[00:47:39] **Carol:** And see, I guess I'm thinking more like when conversions happen, like when something is changing, so we're changing, you know, some customer to a new form. And now what they had before is being converted to a new form. So we're rolling out the code for it. And then we're also converting what the old was to a new forms.

[00:47:56] **Carol:** If it fails, we have to roll back the, what it is now to what it was before.

[00:48:03] **Adam:** Yeah. I mean this, like I was saying, there's, there's a, probably a hundred different variables at play here. And one of those is. What does a rollback mean to you? Right? So if, if the rollback means, our remote desktop into the server and say, check out this commit hash instead to, to just point your head at the, at the different place at a different commit, that's very, that's different too.

[00:48:23] **Adam:** Right? So, and to your point, or, or perhaps against your point, if you're deploying 10 things at once, and the problem is in number five, out of 10, then everything that got deployed got merged after the problem. One you're, you have to roll back using that strategy too,

[00:48:41] **Carol:** Yeah. Agree. Yeah. I could see that. Yeah. We look at how things are related usually. So we're like, oh, numbers six through 10 had absolutely no impact on the thing that's failing. So it's safe to roll back. But then that just becomes an engineer and some leadership person saying, yes, we are good with just this one thing being pulled back, or sometimes, you know, there's always a dirty way to do it.

[00:49:05] **Carol:** And you know, you. Change the server and let it sit there a minute and you fix it and push it back up. But yeah,

[00:49:11] **Adam:** Yeah, we, we have that ability right now and, and we're working toward not having that ability, which is a little bit scary,

[00:49:17] **Carol:** yeah, it, it absolutely is. Yeah.

[00:49:20] **Adam:** yeah. We currently can remote desktop into the server and like just change something in production. And it, this, now it's an uncommitted change on the production server, which is very useful in, in certain events.

[00:49:32] **Adam:** And you're like, it only happens in production. How the heck am I gonna test this?

[00:49:36] **Adam:** And you know, what's what's going on, but it's

[00:49:39] **Carol:** the thought of losing, losing that scary. Yeah.

[00:49:42] **Ben:** I have a confession that when I do a get revert, I know I have to do a dash M one in order to make it work, but I don't know what that means. I, it has something to do with like the branches or something and which you're reverting to. I don't know. I don't understand how branches work at that low level. I just know that when I revert, I gotta do dash M one and magic happens.

[00:50:06] **Ben:** And then my revert works.

[00:50:09] **Adam:** Well, so here's my confession on the back of your confession. I haven't done a get revert since probably the year that I learned get forever ago. Hey, you know, if I have a problem, I just fixed the problem.

[00:50:18] **Ben:** Yeah.

[00:50:19] **Adam:** I don't need to revert.

[00:50:20] **Ben:** We call that at, at work. At least we call that rolling forward. I don't know if that's a. A common term.

[00:50:26] **Carol:** That's common. Yeah. That's common. Yeah. You're all forward with that. I'll say that. I love Sourcery so I tend to do everything I can in an interface. So I right. Click on lots of things and say, can I do this in an interface with no command? Because if so, I feel way safer.

[00:50:42] **Adam:** Makes sense.

[00:50:43] **Carol:** So guys, time for

[00:50:44] **Ben:** Let's do it.

[00:50:45] **Adam:** Sure.

## [00:50:46] DRY, WET and AHA

[00:50:46] **Carol:** All right, I'm going to go with duplication. So I feel like it's, definitely unpopular opinion that, you know, it's okay to duplicate your code, right? Like, I feel like I hear constantly that duplication is disaster and that you should definitely follow the dry, methodology, which is don't repeat yourself.

[00:51:07] **Carol:** However, we speak in English and we think in, or we speak in whatever we speak in, but we think logically, right? We think in steps and sometimes what you're writing, doesn't always make sense to not be duplicated. And you find yourself in the spot where you do have to duplicate it because otherwise it doesn't make sense to you.

[00:51:27] **Carol:** And if you can't understand your code, then what's the point of writing code. Like I need to be able to read it. I need to understand what it's doing. And sometimes I have to duplicate it. Sometimes I have to make such a minor tweak to it that. It makes sense to just double the query, add the change, let everyone else keep pulling it with this identifier that they were using.

[00:51:48] **Carol:** And I don't need that identifier rather than trying to figure out how to change this query to never use this identifier in this one off case. So I don't feel like duplication is disaster. I try to avoid it. I try my best, but sometimes I just, I have to duplicate the process and I have to duplicate the functionality.

[00:52:07] **Carol:** And I'm not sad about that.

[00:52:09] **Adam:** I think you're right. That, that, that was the attitude for a really long time. That duplication was like evil and should be avoided at all costs. I think people are kind of coming around on that. so there's, I, I have heard, I don't recall what it stands for, but I have heard that somebody has like a, an alternative, you know, acronym there's dry.

[00:52:28] **Adam:** Don't repeat yourself. Somebody created wet. Which, oh, it's right. Everything twice. Right. Don't,

[00:52:33] **Adam:** don't abstract it away

[00:52:35] **Adam:** until you've written it twice. And then, and then, okay. Then abstract it away when you need it a

[00:52:40] **Adam:** third time or something. And then, I think the one that I like the most is aha.

[00:52:45] **Adam:** Avoid hasty abstractions, right?

[00:52:47] **Carol:** Oh, wait,

[00:52:48] **Carol:** explain it.

[00:52:49] **Adam:** that one's from Kene Dodds. He has a blog post on it. So if you, if you Google, Kene Dodds, avoid hasty abstractions, I'm sure you'll find it. We'll, I'll put a link in the show notes, but, um, uh, don't write an abstraction. Don't like if you're, I guess the thing with dry and and wet is if you're reusing functionality, it should be a method or something that you can call and, and reuse it that way.

[00:53:14] **Adam:** Instead of duplicating the code, the avoid hasty abstraction is basically just make sure that you fully understand the problem before you write the abstraction. you know, I, I, I think that the argument that he makes is like, you know, you end up with two or three duplicates of the code so that you can fully understand the ways that it's gonna vary.

[00:53:38] **Adam:** You know, I know when we did, clean code, our book, book club episodes, we talked about how like, methods should have ideally like zero arguments or one argument and like, bullying, like true or false arguments to a, a function are kind of considered evil because like a function should only ever do one thing and do it one way.

[00:53:57] **Adam:** so it's, it's so funny because that's like, it's such a anti pattern. It's such a re recognizable thing that I think we've all done a million times because there's not an obvious better way to do it. I, I, I'm absolutely sure that there are better ways to do it, but I think that it takes a, a slightly.

[00:54:16] **Adam:** Higher level of thinking to figure that out and to be able to recognize what's going on when you're reading that code. And I think that's probably where the, where things break down is trying to read somebody else's code. That was clever enough to avoid that bullying argument, you know, by passing in another function or, you know, that kind of stuff.

[00:54:33] **Adam:** but yeah, I I'm, I'm rambling. Sorry.

[00:54:37] **Ben:** Well, I will, I will double and triple down on your enjoyment of duplication because at work I, so I use a technique, I call it a partial. That's kind of my own little nomenclature, but essentially at work, what I have taken to doing is I separate out two concepts on, on one side, I have my crud style. I'm gonna mutate the system and all of those operations kind of flow through a, a, co-located set of queries and functions.

[00:55:12] **Ben:** And then I have, on the other hand, I have to render this page. It has some random data on it, and I'm gonna build separate queries. To the same database and the same tables, but it's gonna be very specifically tailored for this particular view. So I might have, a, a user, if I'm gonna edit a user, for example, I'm gonna go through a very specific user oriented service.

[00:55:36] **Ben:** But if I want to say, for example, list out a top 10, most active users this month, that's gonna be a separate specialized query that also goes to the user table and does, you know, select ID and name and email from user, but it's gonna have nothing to do with that other set of queries. And I might have 10, 15, 20 views that all have their own queries that look very much like that query, except maybe they join to different tables or they only pull back a subset of columns, or maybe they do a little bit of string concatenation or some grouping and, and aggregation.

[00:56:14] **Ben:** And, definitely some people at work have pushed back against that and be like, why do you have a. Why are you selecting from this table in this view? And you selecting from the same table in a different view. And I'm like, they're two different views. Like the SQL looks the same to you, but it is not the same because they have different masters.

[00:56:32] **Ben:** And, so I'm, I'm when it comes to SQL, especially I'm freaking duplicating all day long and I'm loving it.

[00:56:40] **Carol:** Yeah, but it doesn't sound like you're doing full a hundred percent duplication, right? Like yours are slightly tweaked different for what the use

[00:56:48] **Ben:** yeah, yeah, exactly. Exactly.

[00:56:51] **Carol:** Yeah. Same here. Yeah. I get it.

[00:56:54] **Ben:** That's that I think is the, the hardest thing to get over when it comes to dry and do not repeat yourself, is that things that look the same are not necessarily the same thing. They just happen to have a lot of the same words, but they change for different reasons. And, and, and that ultimately I think is, is. pivotal point is when things change for different reasons. They're different things. Even if they look exactly the same,

[00:57:22] **Carol:** They're not the same anymore. Yeah. I literally just went through this at work. Like I'm wrapping it up right now. we had a story come in that was like, oh, just modify this page, rename it to this. When it's these certain forms, and then we're gonna do this whole, I talked about it previously a little bit about this whole, like how we match on different IDs and stuff.

[00:57:41] **Carol:** And ultimately, while it looked like, Hey, it's gonna be pretty much just some minor modifications, the process wasn't written to handle this new way. So it's no longer the same process. It's pretty much two different processes for how you do it. And it has to be handled that way, even though there is some duplication. Kind of looks sort of the same. It's not working the same at all. Like one expects there to be the one-to-one relationship. The other says I'm gonna have a bunch of records come through and you're gonna have to come find the right one. It's never a one-to-one anymore. So it's, they're different even though they kind of look the same and you just have to write it in my opinion, in a way that people can read it and understand how they differ.

[00:58:23] **Carol:** So I try to do the best I can when I'm naming functions. And when I'm, I know comments are bad, but I will still throw a comment in there that says like, Hey, I know above this, we're looking for a loan number. And then this one, we're looking for a loan number, but here's why we can't use the loan number above, like, this is why they never match.

[00:58:40] **Carol:** So you understand what the two differences are?

[00:58:43] **Adam:** Oh, I don't think the comments are bad. I think that comments that say what the code is doing are bad.

[00:58:50] **Adam:** I think comments should say why right. Should explain. Why, why, why are we doing this? Because I think that comments that explain what the coder do is doing are a smell that the code is not well written.

[00:59:02] **Adam:** Like if, if

[00:59:02] **Adam:** it's variable names or function names or whatever, like

[00:59:06] **Adam:** yeah.

[00:59:06] **Ben:** I, I definitely, yeah. I definitely have lots of comments in my code. A hundred percent.

[00:59:11] **Adam:** we know Ben, we, Richard fog, it's more, you have these code samples and it's more

[00:59:17] **Ben:** yeah. Yeah.

[00:59:18] **Adam:** lines of.

[00:59:19] **Ben:** But even in, even in a production application, I do a lot of commenting. I part of it is like, so this, I know this is the worst reason to comment, but sometimes I need some light gray text to break up chunks of logic, cuz I can't have too many lines in a row. It it's like my brain just can't work like that.

[00:59:40] **Ben:** And sometimes I have to throw in a comment just to be like visual space, break it up.

[00:59:45] **Adam:** Sure. I, I will say reading code blocks on your blog. They are very readable, right? There's there's a high level of like being able to, to not be overwhelmed by looking at that code block.

[00:59:59] **Adam:** So

[01:00:00] **Ben:** highest

[01:00:01] **Ben:** compliment. Thank you.

[01:00:02] **Adam:** cool.

## [01:00:04] Patreon

[01:00:04] **Adam:** Well, this episode of Working Code is brought to you by putting the country field first in your address forms. and listeners like you, if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe than you should consider supporting us on Patreon, our patrons, they cover the cost of our recording and editing and buying new microphones and microphones die. and we couldn't do it every week without them. So thank you guys so much for your support special, thanks, of course, to our top patrons, Monte, Gavin, and

[01:00:28] **Adam:** Sean. Uh, if you'd like to help us out, you can go over to patreon.com/WorkingCodePod, and, and one of the benefits, all of our patrons get, our after show, which we're gonna go record as soon as we're done with this part.

[01:00:40] **Adam:** and on tonight's after show, after more than 10 years, being an Android fanboy, I, I, I bit the bullet I bought an

[01:00:48] **Ben:** Ah,

[01:00:48] **Adam:** so I think we should talk about that a little bit.

[01:00:51] **Carol:** I saw that when I texted you, it went blue. I was like, what?

[01:00:55] **Adam:** uh, that's all I'm gonna.so that's it.

## [01:00:58] Thanks For Listening!

[01:00:58] **Adam:** your homework for tonight? leave us a question for our 100th episode.

[01:01:02] **Adam:** This is episode 95. So that means in five weeks, we're doing episode 100,

[01:01:06] **Adam:** as you are listening to this. If you're, if you're a patron four weeks and if you're not a patron three weeks, we will be recording our, 100th episode roughly on October 27th. So time is running out. you can find the link to leave us a question for our AMA.

[01:01:22] **Adam:** if, if you didn't know, this is your first episode, for our 100th episode, we're going to punish ourselves with spicy hot sauce on chicken wings or something close to that. a and try to do an AMA at the same time. and so you can lead us a question for that. you can find the link to the GitHub repo, where we're taking those questions as issues, at the top of our website, workingcode.dev.

[01:01:42] **Adam:** If you'd like to hang out with our community, you can join our Discord workingcode.dev/discord. that's it. let's see. I'm trying to do minimum stuff tonight, cuz I know I go on and on here. emails at WorkingCodePod@gmail.com.

[01:01:53] **Adam:** Send a voice memo to the same place. That's it for us this week. We'll catch you next week. And until then,

[01:01:57] **Carol:** Even you guys who follow all of the,popular opinions, your heart still matters.
