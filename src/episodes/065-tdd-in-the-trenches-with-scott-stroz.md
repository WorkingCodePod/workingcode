---
title: "065: TDD In the Trenches with Scott Stroz"
description: "The crew talks to Scott Stroz about his experience with Test Driven Development (TDD); and, about how he has come to understand that testing makes possible what would have otherwise been impossible."
date: 2022-03-09
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/065-tdd-in-the-trenches-with-scott-stroz/id1544142288?i=1000553429875"></iframe>

Sponsors

- [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

Testing code is like taking out insurance: until you _need_ it, it can be hard to understand why it's so important; it can be hard to understand what everyone is _raving_ about. And so, you continue writing your code without tests. And, everything is fine, until one day it isn't. And in that moment, you _finally_ see for yourself what value automated testing could have brought to the table.

On today's show, the crew talks to [Scott Stroz][scott-stroz] about his experience with Test Driven Development (TDD); and, about how he has come to understand that testing makes possible what would have otherwise been impossible. With solid testing practices in place, Scott was able to refactor an _exceedingly convoluted_ intake form that rendered 25 buttons, 6 unique workflows, and took the user through up to 28 steps. Crunch those numbers and try telling me that the chance of making a mistake isn't absolute. And yet, thanks to a rigorous test-first coding methodology, Scott was able to completely refactor this workflow - _from the ground-up_ - and delivery it on-time and without error!

## Notes &amp; Links

- [Sandi Metz: RailsConf 2014 - All the Little Things](https://www.youtube.com/watch?v=8bZh5LMaSmE)
- [Sandi Metz: No Private Methods](https://www.youtube.com/watch?v=qT5iriwidRg&t=732s)

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[scott-stroz]: https://www.linkedin.com/in/boyzoid/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/065-tdd-in-the-trenches-with-scott-stroz.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Scott:** I wanted to talk about a situation we had on a project that I'm on, where relying on unit tests actually saved us from missing a deadline.

[00:00:08] **Ben:** intriguing.

[00:00:09] **Tim:** So TDD and the.

[00:00:11] **Ben:** So this is science fiction. Okay. Hit it.

[00:00:15] **Tim:** Ben thinks this is fanfic. So let's,

## [00:00:37] Intro

[00:00:37] **Adam:** Okay, here we go. It is show number 65 and on today's show, we have another special guest with us today. I say, hi, Scott, we're joined by our good friend, Scott Stroh's today. We're going to be talking about TDD and testing.

[00:00:50] **Tim:** Ben's favorite topic.

[00:00:52] **Adam:** Yeah. You know,and

[00:00:54] **Adam:** so Carol couldn't make it this week. Another scheduling conflict. but, Ben, why don't you go first? what's going on?

## [00:00:59] Ben's Fail

[00:00:59] **Ben:** I'm going to kick it off with a failure. And, I'm going to harken back to our goals for 2022. And my big goal was going to be to try to take some sort of application yet to be determined and containerize it and deploy it, using modern techniques, continuous integration, et cetera. and I have to date made absolutely no progress on that whatsoever.

[00:01:23] **Ben:** So that's,I'm feeling like that goal slipping away. I've been having a lot of fun doing other stuff, modernizing my blogging platform and trying to bring better practices to that. Of course, all those files are still just FTP to production old school style. So I do want to at least pick something

[00:01:41] **Ben:** and then start to try to build some sort of container and deployment system around it only because it feels like such a huge gap in my understanding of how applications get put together and then managed over time.

[00:01:53] **Ben:** So I'm going to, give myself some slack, at least to the end of February. I've got a lot of stress at work, but, I really do want to start to move that big goal in an, in a meaningful direction.

[00:02:04] **Adam:** Well, you're only a little past 15% through the year. So.

[00:02:06] **Ben:** Uh, you know,it's slipped so fast though.

[00:02:09] **Scott:** is the most Ben Dell thing ever. It's February, and then hit my 2022 goal. I'm a failure.

[00:02:17] **Ben:** No. I was thinking about it the other day. Like I haven't even, I haven't even settled on an idea and, I dunno. And like all the conversations today in the Discord about language choice and developer, ergonomics and community and stuff, I don't know. It's got me all reflecting on my skillset and where I sort of sit in the developer ecosystem.

[00:02:36] **Ben:** So I don't know. I just wanna,I wanna build something and deploy it

[00:02:42] **Ben:** so

[00:02:42] **Tim:** Once, you know, there's room to grow, buddy.

[00:02:44] **Ben:** Yeah, Yeah, exactly. So that's what I got going on.

## [00:02:48] Adam's Triumph

[00:02:48] **Adam:** so I'm going to go with the triumph this week. we've been talking a lot about testing and TDD lately. I think last week or two weeks ago, I had to try them. Cause I had been TDD in an application and this week I've been working on TD doing another application and this is still pretty new to me.

[00:03:04] **Adam:** I'm still, struggling my way through it, but, I am fully bought in like, this is, I have seen the light.

[00:03:10] **Adam:** So

[00:03:11] **Adam:** yeah, I guess that's it for me, Tim? How about you?

## [00:03:14] Tim's Triumph

[00:03:14] **Tim:** So I'm going to go with the triumph here. did I say that right? I always think of when I say triumph, it's wrong. Is That,

[00:03:19] **Tim:** correct?

[00:03:19] **Adam:** Sounds good to me.

[00:03:21] **Scott:** uh,

[00:03:22] **Tim:** I just feel like when other people say it, it doesn't sound like when a triumph triumph, you say a word

[00:03:26] **Tim:** enough, it becomes weird.

[00:03:28] **Adam:** Maybe sometimes it comes out triumph

[00:03:29] **Tim:** Try up. Yeah, yeah, yeah,

[00:03:31] **Ben:** Sorry. If I could just interject for a second, I never watched, who was the red-headed talk show hosts. Conan O'Brien he had triumph, the insult dog. I think, I don't know. I w I was never a late night person, but I watched a clip of triumph, the insult dog one time. And he was at like a, some sort of a tech conference or something like that.

[00:03:49] **Ben:** He's talking to this kid and he says something like, if you are here, who's at home disappointing your parents, like.

[00:04:01] **Ben:** Um,I'd

[00:04:02] **Tim:** That's

[00:04:03] **Ben:** heard of my life.

[00:04:09] **Tim:** my wife pointed out. I say the word I, instead of wheelbarrow, I say.

[00:04:15] **Tim:** I didn't realize that I've said it that way all my life and I've been wrong.

[00:04:18] **Scott:** I do too.

[00:04:20] **Tim:** Okay.

[00:04:20] **Tim:** I don't feel so bad. It has got does it?

[00:04:22] **Tim:** Yeah, that's true. All right.

[00:04:23] **Tim:** Anyway, so here's my triumph.

[00:04:25] **Scott:** Well. You really emphasize the end of that word there.

[00:04:29] **Tim:** Here's my, he is my triumph. So multi-tenant systems with using polymorphism rocks. So I say that because built an API, it's a multi-tenant API and in the original architecture of it, just the ability to just go in and you got a different use case for a different client and to just go extend.

[00:04:48] **Tim:** the base class and then just put one tiny function or maybe two tiny functions in there and then have it work completely differently. It's just blew more. I did it today and I was like, I'm so glad I made this choice because early on in my career, it would have been a long page with CF query at the top, some HTML at the bottom and a bunch of if statements and it looks like just, just polymorphic that function out and you're good.

[00:05:10] **Tim:** So I just, it just made me happy.

[00:05:13] **Ben:** Very nice.

[00:05:13] **Adam:** Heck yeah. Design patterns for.

[00:05:15] **Tim:** There you go.

[00:05:16] **Ben:** I tried that one time, years and years ago. I mean, assault. 15 years ago and, it went terribly wrong. It went and they went the extreme opposite direction where every change became very challenging because I had no idea what I was doing.

[00:05:30] **Tim:** yeah. Trust me. I had many false starts for many years until I finally got there, but. But, I'm not saying object, join a program is the absolute best answer to everything. Cause

[00:05:41] **Tim:** there are seriously, there's a lot of cases where you just can't, inherit things properly and it just becomes a mess.

[00:05:46] **Tim:** So sometimes going functional programming is the answer to that too. But in my case it works great. So happy about that. So what about you Scott?

## [00:05:54] Scott's Triumph

[00:05:54] **Scott:** I'm going to go with a triumph and I hope I

[00:05:56] **Scott:** didn't. That didn't. sound weird. Cause now I'm thinking I say it wrong. Thanks Tim.

[00:06:01] **Tim:** So, I mean, it was self-conscious.

[00:06:02] **Adam:** Yeah.

[00:06:02] **Scott:** Every time I say that word, I'm going to have you in my ear. so I, I manage a golf league and I've managed the league now for, I think it's coming up on about 13 or 14 years.

[00:06:12] **Scott:** And over the years we've gone from managing it on Excel spreadsheets to a WordPress site, with a plugin that was used for managing soccer leagues that I just plugged our in, for the golf league. And eventually when the writing one myself. it's written in ColdFusion using bootstrap. I think it's three on the front end.

[00:06:32] **Scott:** And for years it was hosted on a server. That was a VPN we got, I had for free in England. So anytime somebody tried to hit the website here in West Virginia, the signal would go to England, get the data and send it back across the Atlantic. And it didn't really perform bed, but it was kind of slow because it just that extra time for the re request and response to come back, from England made it seem like it was slow.

[00:06:57] **Scott:** And I recently moved everything to, Oracle cloud, which I'm not sure if anybody knows, but you can actually get, a bunch of free stuff. And it's not like Amazon free, where it's free for a little while, and then they charge you. It's actually always free. As a matter of fact, when you go in and look around the Oracle cloud stuff, you'll actually see this stuff labeled as always free, depending on the size of the instance and stuff you get.

[00:07:17] **Scott:** But I moved it to. There are new arm instances where each one of the servers, I have one for the CSI one for the database side, which by the way, they used to be the same server. they were actually on the same VM. Now they're in separate PMs and each one of them has what full CPU and six gigabytes of Ram.

[00:07:34] **Scott:** And the speed increase has been so much that the and the golf league, several of them have reached out to me and went, Hey, if you've done something with the website, because it seems to be working really well. Something's going to give you get some of the, if you can get a Luddite to compliment you on technology, I think that's a freaking triumph right there.

[00:07:52] **Adam:** Yeah,

[00:07:52] **Ben:** I'm not a hardware person at all. So when you say arm,is that like the M one Mac? Is that also based on the arm

[00:07:59] **Scott:** I believe it

[00:08:00] **Adam:** that's not the type of arms that Ben is used to working on.

[00:08:03] **Tim:** Yep. And biceps buddy.

[00:08:04] **Scott:** it's also the same architecture that's in raspberry.

[00:08:09] **Ben:** I'll tell you though. I live on the east coast of the U S and every data center I've ever had, had been on the east coast of the U S and, I definitely just not by any nefarious reasons, just have no understanding of what people around the world experience when I access applications. I'm sure like a huge amount of the world runs on U S east two and Amazon because of the right.

[00:08:30] **Ben:** Wasn't like the only one that existed for a long time. Do people around the world, do you think they just generally expect websites to work? Not quite as well as,

[00:08:40] **Tim:** that what CloudFlare is for to spread that

[00:08:42] **Tim:** stuff out.

[00:08:42] **Ben:** I, I mean, CDN certainly help to distribute things that can be distributed from a caching layer and the, the edge computing stuff. I don't have much experience with, but if you have a database, right? I mean, most of us, unless you're getting very advanced with like, multi-region replication, I'm

[00:08:58] **Ben:** just saying buzzwords, I don't actually know how any of it works, but like your database has to live somewhere and that data still has to fly all around the world.

[00:09:05] **Tim:** That's why I use cockroach DB.

[00:09:07] **Ben:** Yeah. I know. You've been jazzed on that. We should talk about it more sometime. I'm very

[00:09:10] **Tim:** I know. I actually want to, I mean, I've used it kind of product prototypically I really liked it. One day. Use it, do an actual production version. It doesn't have a use for it. We don't have international customers everyone's in north America. So what's the point.

[00:09:22] **Scott:** I also counter Ben with that. A lot of the sites that people around the world are hitting are probably multi-regional anyway.

[00:09:29] **Ben:** Are they though? I mean, and I say that only as like, that feels like a very advanced topic

[00:09:34] **Tim:** Well, I mean, how many Invisioned customers do you have in Asia?

[00:09:41] **Ben:** I don't know, I think Europe is definitely after the U S the year is a, is the biggest area of customer base and they still have to, I assume there's some sort of tube

[00:09:51] **Ben:** that

[00:09:52] **Scott:** Yeah.

[00:09:53] **Ben:** travels,

[00:09:54] **Adam:** a series of.

[00:09:55] **Tim:** Yes, the internet is not a dump truck.

[00:09:57] **Ben:** I think it's the Atlantic tube. I don't know, but no,I'm genuinely very interested in the idea of doing anything globally or multi-region.

[00:10:06] **Ben:** I mean, that's, when you think about how the web architectures have evolved over the last 15 years, 10, 15 years. I mean, I still very much live in.

[00:10:16] **Ben:** like Scott was talking about having your application server and your database server be the same server. Like that's still a, for little things. Like, certainly that's still the world I live in. I wouldn't even know how to approach. Oh, let me have some sort of multi-region application.

[00:10:30] **Ben:** Unless I had a team of people that were advising me on how to do some of this stuff. so I don't know. maybe everybody has big teams these days and that's very natural

[00:10:38] **Adam:** Yeah. I mean, it's a different skillset, right? it's definitely a different skillset from web.

[00:10:43] **Tim:** yeah, I just let our infrastructure team deal with it.

[00:10:44] **Ben:** I need more access to infrastructure teams. That's my problem. And

[00:10:48] **Tim:** Yeah,

[00:10:48] **Ben:** budget.

[00:10:49] **Scott:** It can get expensive.

[00:10:53] **Ben:** Yeah. And product buy-in, there's a lot of red tape I need to get

[00:10:58] **Tim:** yeah.

[00:10:58] **Adam:** Yep.

## [00:10:59] Audible

[00:10:59] **Tim:** Timmy here. I hope you're enjoying the podcast. we put a lot of work into it. It really is a labor of love. There are costs. However, and if you'd like to help us out, one low friction auction is to sign up for a free trial of audible. All of us at WorkingCodePod, listen to audible every day. So it's something we believe in.

[00:11:18] **Tim:** I personally have over 500 titles, most are fiction, some coding and other non-fiction titles. I'm sure if you don't already have audible, you'll find some great titles to listen to. Long story short, if you'd like to help us out to cover the cost of the show, sign up at workingcode.dev/audible. That's workingcode.dev/audible.

[00:11:40] **Tim:** And thanks and remember your heart map.

## [00:11:44] Who Is Scott Stroz?

[00:11:44] **Adam:** okay. So Scott, who are you and why do we have you on our podcast?

[00:11:47] **Scott:** My name is Scott Stroh's. I am a developer. I have dropped the language adjective from that particular title because I don't want to pigeonhole myself. and I think when you've done things, as long as I have, no matter what language you have, you actually pick up skills that you can use in any language.

[00:12:04] **Scott:** And it actually becomes easier to learn new languages as you go. currently I work for Booz Allen Hamilton, and I wanted to talk about a situation we had on a project that I'm on, where relying on unit tests actually saved us from missing a deadline.

[00:12:19] **Ben:** intriguing.

[00:12:20] **Tim:** So TDD and the.

[00:12:22] **Ben:** So this is science fiction. Okay. Hit it.

[00:12:26] **Tim:** Ben thinks this is fanfic. So let's,

[00:12:28] **Scott:** Well, hold on to be fair, Ben, there is a time I would've agreed with you, but this actually, it really did. It really did save us from missing a deadline that had already been pushed several times.

[00:12:39] **Tim:** before we get into the store here, talk to us about, so, on the Discord channel folks are just constantly haranguing been are actually, trying to get me in and add them to like, get Ben to like, buy into

[00:12:50] **Tim:** TDD.

## [00:12:51] Getting Into TDD

[00:12:51] **Tim:** You are one who was kind of, I wouldn't say against it, but didn't really see the value of

[00:12:56] **Tim:** it.

[00:12:56] **Tim:** Didn't do it. And now you do it. Give us that journey before you give us the story.

[00:13:01] **Scott:** really comes down to the fact that I used to be. I been, I used to be like, he was like, oh, I've got a problem to solve. Let me just start writing code.

[00:13:07] **Scott:** I can just, you know,let me just solve that writing code. and tests were kind of like an afterthought. And honestly, I'm going to be honest.

[00:13:13] **Scott:** I still do slip into that every once in awhile where I'm like, I want to see if my idea is going to work before I test it. And then by the time I'm done, I'm like, oh, look, it works. Oh Now I've got another mic tests.

[00:13:26]

[00:13:26] **Scott:** and it just, for me, it's been situational on this particular project that I'm on. I've been on this project for three years and I have been a huge proponent of writing tests. We use test box for the ColdFusion code on the backend, and we use Jasmine for the, the front end tests. And there's been quite a few times where

[00:13:44] **Scott:** I'm a maniac. Every time I create a new branch, like off of our, like our, we have a dev branch where everything goes, we create feature branches off that every time I branch off of Devin do a feature branch. The first thing I do is I run all the tasks for the module on. And if any of them fail, then people get emails. and doing that has actually saved us. And it's gotten to the point where like, when I first started, I was like, yeah. Okay. I get the idea tests. That's great. But I've actually kind of become the person where I'm like, you gotta write the tests, you gotta make sure they work. And the one thing I realized on my particular team, and actually this is probably in a lot of different cases.

[00:14:21] **Scott:** Sometimes people don't know what to test or how to write the test to make sure that the code is doing what they expect it to do. And that, that last one is really hard. It's really hard to figure out, all right, I need to make sure that this is actually testing what you know, that the code is actually doing what I want it to do.

[00:14:42] **Scott:** And then you got to figure out how you're going to write the test for it because not only do you need to, in my mind, I'm thinking in every situation you need two tests, minimum, you need good test and a bed. So, and if you have an if statement now you need at least, or I should say for every like logical condition or something like that, you need a test.

[00:15:03] **Scott:** So if you have an if statement you need one for, Hey, you had that, it happens. And then it has, for one, it doesn't happen. If you have a switch statement, then you need one test for every case statement you have and then an extra one for when it doesn't match any of the case statements, if you don't have a default. and it's really hard. I think sometimes for people to start thinking like, how can I put these tests together to do that? Because they just think it's,

[00:15:23] **Tim:**

[00:15:23] **Scott:** it's a, they think it's a burden and it, and that

[00:15:25] **Scott:** there's no benefit. And I think that's probably the biggest thing is people need the need to see the benefit of it for themselves.

[00:15:33] **Scott:** And that's what happened to me, before it actually starts, drilling into your head, like this is a good thing, and it's something that we need to do.

[00:15:38] **Tim:** what's

[00:15:39] **Tim:** the benefit you saw?

## [00:15:40] The Benefits Of Tests

[00:15:40] **Scott:** We actually had, there were changes that were made in some parts of shared files. So like we have some shared services on the front end, and those changes to those services failed in several other modules that would not probably would not have been picked up on because the modules were actually done and had, they were ready. They were like blessed and ready to go out to production with everything else. and some changes are made to these shared services, which broke stuff in those modules. And if we didn't change or if I didn't run those tests, we never would have realized until it went to production and everything went boom and blew up.

[00:16:17] **Scott:** So it's really helped actually. And as the applications gotten better, It's become even more important because now we have a lot of interconnectivity where there's a lot of different communication between the different modules and data sharing and stuff between the different modules. So it's,I'm a big fan now.

[00:16:34] **Adam:** And one of the things you were saying before was like, every conditional, every switch, those are places where you need tests. But I think that the reason people don't realize that is the case is that each of those things, like each of that condition, that if statement, represents two things that could happen and those things happen for a reason.

[00:16:52] **Adam:** So those are features. Each of those represents a feature path through the code, and that's what you need to be testing is your.

[00:16:59] **Scott:** Yep. Exactly.

[00:17:01] **Ben:** As someone who watches the testing conversation with the outside, most of the time. Hurdles for me in terms of wrapping my head around it is the granularity of the desks themselves. and I know you're talking about conditions and switch statements and having tests that map to those branches. but just to give this a concrete sense, like, let's say I'm in a checkout process and I'm going to purchase an item and I'm buying in.

[00:17:27] **Ben:** I checkout. So during that interaction, a bunch of stuff is actually happening. Like, an order is getting placed. Like maybe it has order items. Maybe an email is going out. Maybe inventory is being decremented somewhere. Maybe there's a log being created for something. If I wanted to create a test that was like, the purchase works in.

[00:17:48] **Ben:** Am I creating. a single test that tests all of that happens. Or do you have like a test that says like when purchasing happens, here's the test that says the inventory is affected. Then I have another test that says, and when purchasing is done, let me make sure emails get sent. I have no sense if there should be like 15 asserts inside of my test, or if that's a code smell

[00:18:08] **Scott:** It depends.

[00:18:11] **Ben:** classic.

[00:18:12] **Adam:** I didn't realize we were in finding a politician on the show here.

[00:18:15] **Scott:** if I may, the,the situation that I wanted to talk about at work, I have one function inside of a service that the application calls and then inside of that function, it makes a bunch of other calls to the same service that gets specific data that we're looking for a specific data point.

[00:18:32] **Scott:** So rather than having all the logic I needed in the one function, I broke it out into a bunch of different functions. Now, granted, there are a lot of asserts when I test that main function, but all I'm doing is I'm making sure, like I said, a spy on all the other functions that are called in that particular main. And I just make sure that those are actually called and that they're called with the data that I expect it to be passed. And then each of the functions that gets called has its own set of tests, depending on how complex the logic was in that particular case.

[00:19:04] **Adam:** Yeah. So if somebody is more familiar with the terminology, a spy, it sounds like it's pretty much the same thing as. the thing that's calling it. It looks and acts like it's the same thing, but it doesn't actually do that work.

[00:19:15] **Scott:** yes, but it's a little bit different in the fact that in Jasmine, you can have both mocks and spies

[00:19:21] **Scott:**

[00:19:21] **Scott:** and they do functional. Like you can actually spy a mock.

[00:19:24] **Adam:**

[00:19:24] **Scott:** So in, in terms of like, test box, if that, I think that's what, you're, what you might've been referring to. it's similar, but. Like, cause the spy, you can actually mock out an object and then spied different, functions on that.

[00:19:35] **Scott:** Or you can actually spy functions off of, a related service

[00:19:38] **Adam:** So aspire is just the ability to see that it was invoked. And these were the arguments.

[00:19:42] **Scott:** exactly. Yeah.

[00:19:45] **Ben:** And are you testing against a database, like an active database? are you mocking out your data layer? How does that work? That, that honestly, with testing that's the biggest hurdle for me is where does the data come from?

[00:19:55] **Scott:** for the client side tests. No. Cause the clients I test for only doing unit tests and we're only testing, the individual functions and we're not testing how they interact with each other. And most of that's because if you have good test coverage in the related services and the related methods on those services, then you don't need to test that you're getting back the right data because you already have the coverage elsewhere to handle that.

[00:20:15] **Scott:** for the tests that we run on the,the server side. Yes we do. We mock out the,the. Like we

[00:20:20] **Scott:** actually,

[00:20:21] **Scott:** for all the different test files we have, we actually build the database files, populated with test data and then destroy everything. When the tests are done,

[00:20:28] **Ben:** Gotcha.

[00:20:29] **Tim:** Yeah, I typically I'll build a Jason data file, like, just scripted out. It pulls it in from there rather than talking to an actual database.

[00:20:38] **Adam:** As an industry, we seem to be so well aligned. That testing is so important in general. but the, there seems to be a complete lack of teaching of how to test and how to test. Well, that seems like something somebody should create.

[00:20:53] **Scott:** I'm working on that. I actually submitted that to pick that exact topic to several conferences for the summer.

[00:20:59] **Adam:** Oh, nice.

[00:21:00] **Adam:** I thought that was totally unplanned. Uh,

[00:21:04] **Tim:** And

[00:21:05] **Tim:** it's funny. So I got, I'm on them, an advisory board for a local college. And this year they've asked me to come speak,

[00:21:13] **Tim:** to like their graduating class and like talk to them about opportunities in computer science and things like that. But I do want to talk to them about, cause I don't know what they're teaching in college.

[00:21:22] **Tim:** Right. my son he's about to graduate. He's

[00:21:24] **Tim:** going to be going to the same school I'm speaking at. actually and I don't know how well they teach, testing and if they don't, that's a big

[00:21:31] **Tim:** miss, because

[00:21:32] **Tim:** I know when I went to school, they taught me a lot of programming.

[00:21:35] **Tim:** There was no testing. Of course this was ancient days. I don't think testing existed back then, but I hope they do now because

[00:21:42] **Ben:** I learned no testing in school. That's for sure.

[00:21:45] **Tim:** did.

[00:21:45] **Ben:** No, I did

[00:21:46] **Tim:** Oh, no you didn't. Yeah.

## [00:21:47] Scott's Button Service

[00:21:47] **Tim:** So, tell us your story then. Come on,

[00:21:50] **Tim:** don't leave us hanging.

[00:21:52] **Scott:** So, the project that I'm on right now is for a large government agency and the particular module we're working on has to do with getting certain entities within this government agency money from the federal government. So it's a pretty important piece of software that we're writing. And we were getting close to going to production.

[00:22:11] **Scott:** And there's one particular page that was having a lot of problems. This particular page has, I believe somewhere along the lines of 25 different buttons, they're not all displayed at the same time. It's just, there's 25 possible buttons to be on the page. And depending on which workflow of which I think there's six.

[00:22:33] **Scott:** And some of them, each is the biggest workflow, I think has 28 steps.

[00:22:38] **Ben:** Oh, my

[00:22:38] **Ben:** goodness.

[00:22:39] **Scott:** depending on which workflow you in and what step it is in the workflow and what type of user you are, will dictate what buttons you can see. And over time, the logic for figuring out which buttons should be displayed when just got ridiculous, because we were just, initially it was all inside of NGF statements cause we're using angular.

[00:22:58] **Scott:** And it was like, cause at the time when we started this module, it seemed like I'm like yeah, that'll be easy to do. But I didn't realize because this apparently is the second time that this application is being redone. I didn't have the institutional knowledge, to know what was going to happen. I just knew, oh look, here's the task.

[00:23:16] **Scott:** I need to put a button on the screen. Okay. Oh the only this user can see the button. Awesome. Just NGF. and it just, it got ridiculous and because some of the buttons that we're using are. They're used in multiple places on the page, like the there'll be a button row at the top and then the same exact button right at the bottom.

[00:23:32] **Scott:** And some places, they're in includes or they're in directives for it for a different page. And the logic to figure this out was just all over the place. and in many cases, the logic was duplicated. And in other places we were saying, Hey, yeah, this particular user at this step in this workflow can see the button.

[00:23:48] **Scott:** And then elsewhere, we were saying just the opposite. So it was like a pain to figure out, or this button is supposed to be there. Why isn't it there? so I was tasked with coming up with some type of framework or some type of way to centralize all the logic for all the buttons and make it easier to implement the problem is this all happened about two weeks before we were supposed to go to production and according to the client, it had to get done.

[00:24:16] **Scott:** And we couldn't push the deadline because we had already pushed it through. And they were like, this is it. It's gotta get done. And the biggest problem we had was getting the test data set up so that when QA was testing, they, it was easier for them because some of the, it would take sometimes a half hour to get this particular dataset through an entire workflow

[00:24:38] **Scott:** or to the very last step in the workflow.

[00:24:40] **Scott:** So we can test to see which button is that is there. So what we decided to do is they had people from QA, three of them sat down over three days and they created unique datasets for every possible iteration of every workflow in every user or user type. it took three of them, three of them three days. And then they turned around and said, okay, Scott, you need to duplicate this in the development database. And I'm like, that's not going to happen. I'm like, that's going to take me. More than a week. I said, it took three people three days. I said, if you want me to do it, we lose another week and then we're not getting done.

[00:25:13] **Scott:** So I had the idea that I was like, okay, how about we do this just for dev sake, not saying for QA, but just for dev sake. So I can say this is good for QA to take a look at it. We just let me base it off of comprehensive tests that I'm going to write.

[00:25:28] **Adam:** So it sounds like default posture, there was no tests

[00:25:33] **Scott:** It wasn't that it wasn't that the default posture was no test because we still write tests. But we also, like in the past, I've also gone to the page and pulled up the particular data at that particular step to make sure that we were seeing what we were seeing, but that's. Not only is it time-consuming to create all that data, but then they actually have to remember which data piece I had to go at what point to check which button it wasn't, it was going to be a nightmare.

[00:25:56] **Scott:** And because of the way the, our different environments are set up, we couldn't just copy the data from the QA database into the dev database, because they're actually at different stages of what's available. And what's not because there's stuff in the dev database, there were database changes that were not quite in the QA database yet, and it would overwrite stuff.

[00:26:15] **Scott:** It just, it would have been a much bigger deal to do that.

[00:26:19] **Ben:** Just a quick question. So when you say that you want to do this just in the dev environment, you're saying that you're going to run these tests manually, or, it's automated tests, but you're running the manually. It's not part of like a pre-commit hook or something

[00:26:32] **Scott:** No, it's just right. And actually, thanks Ben, but we don't have automated tests. if by automated you mean I automatically run them whenever I do a new poll. Yes, that's it.

[00:26:41] **Ben:** I'mjust making stuff up here.

[00:26:43] **Scott:** what I mean by that is like, before, whenever we'd work on something on the UI, we'd always have to make sure we pull up the page and inspect it to make sure we're seeing what we think we're seeing

[00:26:52] **Scott:** in this particular case.

[00:26:53] **Scott:** We didn't do that. I didn't do that. I just based whether or not the button was going to be there off of the test. If the test said the button was going to be there, it was blessed in the dev environment and pushed off to QA for them to actually load up the data that they created

[00:27:07] **Ben:** Gotcha. Gotcha.

[00:27:08] **Scott:** to see if the button actually existed. Nobody thought we were getting this done. I mean, it was like, it got to the point where I would get, I. Several times a day, how's it going? How's it going? How's it going? And I'm like, it'd be going a lot better if you stop asking me how it's going, and you guys know if you're in the zone and you're interrupted even for just like a brief second, you've

[00:27:35] **Scott:** lost all that momentum.

[00:27:36] **Scott:** so they actually told me that I could just, put myself as offline on our, on Microsoft teams until I was done. I'm like, listen, I'll let you know how my progress is going. If I think we're not going to make it, trust me, you're going to know. And I got everything done now, QA, wasn't able to test everything in time. because there was just, there was so much,

[00:27:56] **Scott:** I mean, there were so many different tickets, I think, just to give you there's three tabs on the spreadsheet, the one tab, which is the main one we had to get done. had somewhere in the area of, I think about 200 rows.

[00:28:08] **Ben:** Oh,

[00:28:08] **Scott:** then the number of buttons and combinations of buttons and whatever extended, I think to like, column B M was

[00:28:17] **Scott:** the last, yeah.

[00:28:18] **Scott:** So th thth the spreadsheet, I exactly, I haven't managed the guy who put it together, did a fantastic job, because it was so easy to, it was so easy to figure out, what needed to be done, what the logic we needed for particular buttons. And he really did put a lot of work into it and I would just sit there and like, I put my headphones on, like crank up my music and I would just freaking write, I was writing tests, And then once I'm like, okay, I think this is good. Then I'd write the code to make sure the test pass. And I, it got to the point where I was just flying through stuff. Like people were like, how are you getting all this done? And I'm like, cause I know what I'm doing. and when we were done, I had a.

[00:28:57] **Scott:** And this was between the service that I built and the test almost 6,000 lines of code.

[00:29:02] **Ben:** Oh, my

[00:29:02] **Adam:** Well,

[00:29:03] **Scott:** And we're up to right now on about 530 different tasks that run just for this particular service.

[00:29:11] **Adam:** yeah, one page with 25 buttons on it.

[00:29:13] **Scott:** Yeah. And I know I have the mail. I know it sounds ridiculous, but like I said, there's no one is ever going to see all 25 buttons at

[00:29:21] **Scott:** one time, you know,

[00:29:23] **Scott:** I'd say at the most five or six, maybe.

[00:29:27] **Scott:** but it just, it was one of those things where like, I was afraid. I'm like, wow, once QA gets this, it's just going to be, it's going to be a nightmare. Cause they're going to find so many problems. And then I'm like, great. Now I got to fix the stuff I already did and then continue to do the stuff I haven't done.

[00:29:41] **Scott:** and most of the stuff that got kicked back from QA were typos because I copied the logic out of the spring. And the person who created the spreadsheet had

[00:29:52] **Scott:** extra

[00:29:52] **Tim:** Who you just

[00:29:53] **Tim:** said did a great

[00:29:54] **Scott:** Yeah. He, well, no, he did. he did this didn't happen a lot. And I think it happened in like five places. But the problem is that particular text was used in a lot of different logic in the, the process. So like he added extra spaces because he didn't like the way words broke in the cell and the spreadsheet.

[00:30:10] **Tim:** Oh, he's a designer.

[00:30:12] **Tim:** Got it.

[00:30:12] **Scott:** like, you can't do that because if you're telling me it has to equal this, I'm just going to take that and put it in the code. the good thing was, it was easy to fix and usually just fixing one typo, helped address, like, a dozen or so possible issues that, that we were having.

[00:30:25] **Scott:** And we're still going through with, we call it the button matrix, I call it the matrix. Like, there's a glitch in the matrix.

[00:30:32] **Scott:** we're still going through and adding other stuff. Cause we, there was another page we had to do that didn't have nearly as many buttons, but probably had more complex logic.

[00:30:38] **Scott:** and a bunch of other stuff that we're going through. And like, of course. As the users have this now they're like, that's wrong. We need to fix this. So in the last two weeks it's been mostly, Hey, we have new requirements. So like I've had to go in and change some of the logic, which was cool because the way it's set up, it's like,

[00:30:54] **Scott:** You know what, for this particular user, in this particular workflow, at this particular step, we need to show this button. No problem. In like, literally in like two minutes, I got it fixed and it's, back out to QA again. And it really saved us. Being able to depend on those tests saved us. Because if, even if I just, even if we had the data and I had to go in and verify visually each one of these pages had the buttons, it was supposed to, there's no way that there's no way we would've gotten done in time.

[00:31:22] **Adam:** Yeah. And you were talking about there being, a bunch of tests. I think that's totally reasonable, right? Like tests tend to accumulate around complexity. Right? So where you have a complex part of your app, there's lots of tests when

[00:31:33] **Adam:** there's

[00:31:34] **Scott:** Yep.

[00:31:34] **Adam:** simple, easy.

[00:31:36] **Ben:** Did you uncover any bugs as you were putting the tests in place? I can definitely. I mean, you have a QA team, so this might be unlikely, but I would imagine that a lot of people who are adding tests to an existing system for the first time are actually going to start uncovering bugs. They didn't know were there.

[00:31:50] **Scott:** In this particular case? No, because I started fresh and like, this was basically on an island.

[00:31:55] **Scott:** there was no other tests involved in here. It was like, like we act in tag islands. we, we actually, this particular piece is it's called the button service and it's just the one file.

[00:32:08] **Scott:** it's one of those things where like, it sounds so stupid. Like when I try to explain to people, I'm like, my God, this sounds stupid, but it actually, it was necessary. We needed it because of how complex some of the logic was,

[00:32:17] **Tim:** Are you sure this isn't a clicker game.

[00:32:19] **Scott:** positive. It's not a clicker game.

[00:32:20] **Tim:** Okay. Just checking,

[00:32:22] **Scott:** I mean, maybe to some people it is.

[00:32:23] **Scott:** I don't know. I've never actually clicked all the way through because I didn't need to.

[00:32:27] **Tim:** you know, how it ends.

[00:32:30] **Ben:** so you have your NGS and for people who aren't familiar with angular, NGF is an attribute on a Dom element that basically determines whether or not the element is rendered in the page. So you can attach condition as to whether or not something shows up. It sounds like the NGF conditions were fairly complicated in the beginning.

[00:32:47] **Ben:** this type of user plus they've in this type of workflow and they've made these options, then show this button as you were refactoring and putting this all together. Did you also change the conditions in the NGF? Like did you bring those into some sort of a centralized location or this was more like, we just have to make sure that in two weeks this can be live with the right data.

[00:33:06] **Ben:** Let's focus just on the test and defer any refactoring really in terms of the UI

[00:33:10] **Scott:** no, actually we completely refactored everything in terms of

[00:33:14] **Scott:** the logic there. So

[00:33:16] **Ben:** That's

[00:33:17] **Ben:** ballsy right before production

[00:33:18] **Scott:** When the,

[00:33:19] **Scott:** when the, well, here's the thing I knew it was going to work. And yes, I was that arrogant with the climate on the call. They're like, are we going to, because somebody actually brought that exact point up, in the meeting and they were like, are you sure you can get it done? I'm like, I can guarantee it, you know? but so, so what we wind up doing is giving an idea like when the data loads on know on this one particular page with the 25 buttons, when the dataset loads, the last thing we do after the data loads is we call the button service and pass the data to the button service.

[00:33:48] **Scott:** And then in the button service, it goes, and there's two main methods. One for each of the two main pages we have, where it calls. Get me the details buttons. And then inside there, it calls another method inside that service for each individual button and passes the data it needs. And then inside of each one of those methods, it actually does the logic check.

[00:34:08] **Scott:** Like, is it this particular workflow process? And if it is, is it this particular step in the workflow process and is the user a user that's able to see it. in some of the cases that's like really easy, like the exit button was like yet returned true. Cause there's no logic there cause everybody's easy exit button.

[00:34:23] **Scott:** But like I said, there are some, there were some where it was like re like really like, how am I going to do this? And I wound up having to do like an inner process of like, okay, first I need to make sure that the button is there or the tests are passing for this particular type of workload prod. And then it's like, okay, then I need to add the different phases for that process.

[00:34:43] **Scott:** Okay. Now I need to check and make sure it's the other process that works. And then those particular phases or steps for that process. And then I'm like, okay, now we need to make sure that it's, a particular user, the good thing was it was either the user could see the button or couldn't see the button.

[00:34:56] **Scott:** So it wasn't like one user could see that this process and another user, because she had another it's it was basically, are you this type of user? Okay. Then as long as anything else was made, you can see the button.

[00:35:06] **Scott:** So I usually wrapped everything in with is the user basically is the user of this type.

[00:35:11] **Scott:** So if the answer was no, then they didn't see the button regardless.

## [00:35:15] Thoughts On Button Service Story

[00:35:15] **Tim:** I didn't know, there'd be so much button talk today

[00:35:18] **Scott:** they would

[00:35:18] **Tim:** so much. There's just so many, so many buttons.

[00:35:22] **Scott:** literally hundreds of combinations of buttons can happen on

[00:35:25] **Scott:** this page.

[00:35:26] **Tim:** this guy's button crazy.

[00:35:28] **Scott:** I'm the button master.

[00:35:29] **Adam:** I need to make you a button that says button master.

[00:35:32] **Scott:** It really, to me, it was like, this is the thing when I was like, man, if it wasn't for riding past, there's like I said, there's no way we could've gotten this done.

[00:35:39] **Scott:** There's absolutely no way it would've gotten done on time,

[00:35:41] **Tim:** What did you write the tests in for the

[00:35:43] **Tim:** buttons?

[00:35:43] **Scott:** Jasmine.

[00:35:44] **Tim:** Okay. So this all client

[00:35:46] **Scott:** Yep. It's all client side. and it's all based off of data that we knew we were getting back from the server.

[00:35:50] **Tim:** Gotcha.

[00:35:50] **Scott:** there's helper information in there. that let us know what state or what stage the particular, data set may be at or more to the point which workflow process is actually being looked at and,information about the, not necessarily their username, but are they a particular role?

[00:36:06] **Tim:** I don't know a whole lot about Jasmine cause mostly, I typically write API APIs. So Jasmine, I mean, how does that run the client side? It just makes a call to the browser and then inspects the Dom.

[00:36:18] **Scott:** it's magic.

[00:36:21] **Adam:** It runs in the browser.

[00:36:22] **Scott:** Friends in the browser. Yeah. And actually what's funny was I freaked people out because I was showing them something one day and I clicked in, I use intelligent idea, which I love, I actually love that ID. and you can actually run the test through karma in like directly in the ID, like, the command line.

[00:36:38] **Scott:** And like I clicked the button and to run the tests and somebody was like, wait, where's the browser. And I'm like, well, there isn't one because I have mine's configured to run in headless Chrome. everyone else has to run. Everyone else runs their tests through a command line and then like a Chrome window pops up and you actually had, you can actually see information in the Chrome window that pops up and then you'll get information in the command line.

[00:37:00] **Scott:** Or in my case, in the console where I'm, my tests are running to let me know past and what's.

[00:37:06] **Tim:** Interesting.

[00:37:07] **Scott:** I like, I like running the, the tests in the IDE, because when there's a failure, if I click the failure, it automatically opens the file and goes to the test that failed

[00:37:15] **Ben:**

[00:37:15] **Scott:** I can see why.

[00:37:16] **Adam:** Nice. So I'm really glad that we got to hear this story. I feel like it's very relatable. Probably not. Everybody has a screen in a 28 step workflow with 25 buttons on it, but, everybody has that file, right. That's just slowly grown from one conditional to. Nested conditionals and nobody wants to touch it.

[00:37:35] **Adam:** Cause you know, you're going to break some, one of the thousands of possible combinations. I'm positive. I mentioned on the show recently, although it might've been in the after show this great, conference presentation by Sandy Metz called, all the small things or all the little things, sorry, all the small things with blink 180 2 song.

[00:37:50]

[00:37:52] **Adam:** and it's about a code CATIA, which is like a practice problem, where you're given a similar thing,here's a whole bunch of nested conditionals and the code works, but your job is to add a feature without breaking anything. And it's,write tests to make sure that you haven't broken it.

[00:38:06] **Adam:** And then, in theory, not only can you write tests to make sure that your change doesn't break anything, then you can refactor the code to not be a complete mess too. and be, smart, clean code. And,I've watched it twice this month. and I pass it on to numerous other people and everybody loves it.

[00:38:20] **Adam:** So I'm definitely gonna put the link to that in the show notes. And, I would recommend anybody watch that. It's a really great talk, very relevant to this conversation.

[00:38:29] **Ben:** I like Sandy maths. She has another code kata. and we've talked about this before. I think where she says, try to design your classes. So that they have no private methods with the idea being that everything that is a private method could maybe actually be factored out into another component that has a more focused set of responsibilities and then gets injected into interior component.

[00:38:51] **Ben:** And this is actually a little bit relevant to Scott's button service, because I was thinking about

[00:38:58] **Scott:** Right.

[00:38:59] **Ben:** if I could, I, I have, but I'll have a component that, that has, let's say more than one functionality. So for example, posting a comment within my comment workflow component, I'll have methods for adding a comment and editing a comment and maybe approving a comment and rejecting comments.

[00:39:16] **Ben:** And I have them all there because there's a bunch of private methods that they all sort of share around validation and check in for things, whether or not they exist. And I think to myself, if I. If I could refactor it so that each component did just one thing. So like here's the component that just does adding comments.

[00:39:31] **Ben:** And here's the component that just deals with editing components. And here's the component that just deals with approving and rejecting comments. Then my big mental hurdle is a, what I call those things that I factored out. Like, I wouldn't know how to name them elegantly, but I see Scott has button service.

[00:39:48] **Ben:** It doesn't have to be super elegant. Like it doesn't have to be like a very sophisticated name. I, maybe it's just like comment, workflow, validation, service. And like that's just shared methods around validating stuff and, you get it wired together and then maybe a better name comes to you or maybe it doesn't.

[00:40:03] **Ben:** And I don't know. So that was, it's very nice to see buttons service exists at the, that gives me a lot of freedom in my head,

[00:40:09] **Scott:** I have to say as a developer, one of the hardest things in the world to do naming things.

[00:40:14] **Ben:** you know, athousand percent.

[00:40:16] **Scott:** Yeah,

[00:40:17] **Adam:** Yeah.

[00:40:17] **Adam:** there's only what is it? A two problems that are so hard in computer science, cache invalidation, naming things and off by one errors.

[00:40:24] **Tim:** yep, exactly.

[00:40:28] **Tim:** That was a great

[00:40:28] **Tim:** story, Scott.

[00:40:29] **Scott:** Thank

[00:40:29] **Tim:** Glad you're on the show.

[00:40:31] **Tim:**

## [00:40:31] Patreon

[00:40:31] **Adam:** Well then, it's my pleasure to let you know that this episode of Working Code is brought to you by the button service and listeners like you. If you like what we're doing here, you should consider supporting us on Patreon. We have a bunch of really great people helping us out over there, and we appreciate every single one of them special. Thanks to our top patrons, Monte, and. You can find us at patreon.com/WorkingCodePod. All of our patrons get early access to an ad-free version of new episodes and our after show that we're going to go record up right after this.

## [00:41:00] Thanks For Listening!

[00:41:00] **Adam:** did, you know, that we tweet clips of the show every time we release a new episode and did you know that it would warm our IC jaded developer hearts? If you gave a retweet because we do, and it would, you can find us on Twitter @WorkingCodePod. That's it for this week. We'll catch you next week. And until then,

[00:41:15] **Tim:** Remember your heart matters, even if you don't have any buttons.
