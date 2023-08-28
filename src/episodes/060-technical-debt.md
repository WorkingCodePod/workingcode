---
title: "060: Technical Debt"
description: "This week, the crew discusses technical debt and goes so far as to say that taking on technical debt is a necessary negotiation within every successful product development life-cycle."
date: 2022-02-02
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="450" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/working-code/id1544142288"></iframe>

Sponsors

-  [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

Every software application has "technical debt". Some of that debt is acquired through meaningful consideration: short-term value gained in lieu of longer-term ease-of-maintenance. And, some of that debt is obtained incidentally through a lack of experience and a dearth of business knowledge. This week, the crew discusses technical debt in their web applications. And goes so far as to say that taking on technical debt is a necessary negotiation within every successful product development life-cycle.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/060-technical-debt.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Adam:** yeah. and another one is like having no tests is a form of technical debt.

[00:00:04] **Tim:** True.

[00:00:05] **Ben:** No. Happy to know that I sort of wish I had a test the other day.

[00:00:12] **Carol:** Oh,

[00:00:14] **Ben:** so okay

## [00:00:34] Intro

[00:00:34] **Adam:** It is show number 60 and on today's show, we're going to talk about technical debt, but first as usual, we're going to start with our triumphs and fails. And Tim, you're up, man? What's going on?

## [00:00:46] Tim's Triumph

[00:00:46] **Tim:** So I'm calling this one, a triumph. So I have for vanity reasons, I have a Google alert, news alert. So anytime my name Timothy Cunningham, or Tim Cunningham pops up like in a newsfeed somewhere. It alerts me. And most of the time, it's about my nemesis, Tim Cunningham. Who's a saxophone player, is, you know,very accomplished expo player of like five or six albums.

[00:01:09] **Tim:** But today it was about me. I was quite surprised I pulled it. I looked at it. I'm like, oh, w what's old, Tim, where's he playing today? But then I saw it was about, MIT licensing. So we'll put the description of the link in the show notes. But, so years ago, like 2012, I wrote and little open source project that just integrated I text and used ITEX to generate QR codes.

[00:01:35] **Tim:** Cause we needed to generate QR codes at work. And, I was trying to share with the world. And so I put it out there as an open source, but I was trying to find a open source license and I was just Googling around and I came across one called the no Bob Saget, open source license. So it's based off of the MIT license.

[00:01:58] **Tim:** but basically it says, it's licensed under the MIT. No, Bob Saget open source license, Timothy Cunningham 2012. it says permission is hereby granted free of charge to any person except Bob Saget, obtaining a copy of this. And so it goes on, it's like everything, it talks about the rights it's like, except Bob Saget.

[00:02:14] **Tim:** Right? So it's just, and the article basically, I mean, it quotes the entire, thing here and then it says most likely he had nothing against Bob Saget per se, which I don't. I liked him a lot. just a quirky sense of humor, which I do. He presumably pick the name from popular culture as the least likely person in the world to whom one might want to license the library.

[00:02:35] **Tim:** Well, he assumes that I wrote, came up with this myself. I don't know where I found it. I just found it somewhere and thought it was funny. but then the takeaway from his article is That frivolity in these licenses, such as others, such as the beer license and chicken dance license is amusing, but it doesn't encourage the use of one software and it creates friction and extra work for attorneys.

[00:02:54] **Tim:** Best practice developers is to stick with the most common licenses and let Bob rest in peace to which I say, I want to make more work for our attorneys. I hate attorneys.

[00:03:04] **Carol:** Earn your keep.

[00:03:06] **Adam:** yeah, I mean, rip Bob Saget,

[00:03:08] **Carol:** Yeah. Oh

[00:03:10] **Tim:** I did. I did comment on there. I put a comment on it. It has a discuss. I said full disclosure. I did not write the Bob Saget open-source license. I found it somewhere on the internet and found it funny. My condolences to the family and friends of Bob Saget on his untimely passing

[00:03:23] **Carol:** No.

[00:03:24] **Adam:** And a second, I don't think there's a lawyer on this planet who would be at all upset that they get to bill extra hours. Cause some

[00:03:33] **Tim:** joker.

[00:03:34] **Adam:** programmer thought he was being funny by, using some nonstandard license,

[00:03:38] **Tim:** Yep. So that's my trap. If they're writing about you, they're talking about you that even if it's bad or good, it doesn't, it's a win. So it's a

[00:03:46] **Adam:** no bad press.

[00:03:47] **Tim:** no bad press.

[00:03:49] **Adam:** How about you?

## [00:03:50] Carol's Failure

[00:03:50] **Carol:** Yeah, I'm going to go with a failure this week. I have been in just like flight mode, all week long. Like every little thing is triggering me and it's everything from like a comment on a PR to like a whip getting added on my tasks that I'm working on right now. Everything is just like huge anxiety.

[00:04:12] **Carol:** And I don't know what's going on. I don't like this. So I've got to figure out was like triggering all of this with work and get myself reset because it's not been a good week dealing with it. So not fine.

[00:04:24] **Tim:** I think a lot of people for, I mean, I'm feeling that way too, this whole week. I've just been, I just want to curl up and hide. Right. I want to avoid people, but I'm trying my best to work through it.

[00:04:34] **Carol:** Yeah. I actually responded to one of them and was like, I feel like crying right now. Like in slack privately. I was like, I don't know why just saying like, Hey, we could do this another way. You're accurate. We could do this another way. I just feel like crying that you said we could do it another way. I don't know, but I got to figure it out because I can't do another week like this, so yeah.

[00:04:56] **Carol:** Failure, failure.

[00:04:57] **Tim:** I think all of us are at the whole world is struggling right now. this whole, we thought we were done with COVID then Delta came and then it went and now Omnichron is here. it's like, when will the world be back to normal? As bad as normal was, at least it wasn't this.

[00:05:13] **Carol:** right. I

[00:05:14] **Tim:** all just so emotionally scarred from this entire anxiety that is just

[00:05:19] **Adam:** And exhausted.

[00:05:20] **Tim:** Yeah.

[00:05:20] **Tim:** Just exhausted of

[00:05:21] **Carol:** that's true too.

[00:05:23] **Adam:** I've been seeing news articles show up in my newsfeed that are like Alma. CRA may be the last variant that we have to deal with. And it's just going to kind of fizzle out after this and I can't help, but think that it's just wishful thinking right there, writing the headlines that people want to see.

[00:05:38] **Carol:** Gotta give us a hope somewhere, right? There's a little bit,

[00:05:41] **Tim:** yeah. I mean

[00:05:41] **Adam:** to hold on to.

[00:05:42] **Carol:** Yeah.

[00:05:43] **Tim:** until the whole world has immediately this thing is going to continue to be variant. So it's just in

[00:05:47] **Carol:** Is that viruses work?

[00:05:48] **Tim:** some might be worse than Omicron. I mean, so.

[00:05:51] **Ben:** Well, they keep talking about it, moving into sort of a flu. Classification, but I don't know, avoid the flu. Like it's a plague. I almost be happy with us, downgrading a coronavirus to something in that realm and then stop living in fear because even right now, every time I go anywhere, I'm like, part of me is worried about not necessarily that I'm going to get it cause I'm youngish and healthy-ish, but am I going to then interact with someone?

[00:06:20] **Ben:** Like for like, for example, my wife's mother's is not doing very well, so am I going to bring something home and then she's going to go visit her mother and then her mother is going to get sick. Like I, I think about that and that's not a, it's not a good way to live.

[00:06:33] **Adam:** Yeah. I mean, similarly sort of the other side of the same coin, I'm immunocompromised for. My own stuff, but, my kids are going to school because they have to in our area. And I'm a little bit worried that one of them is going to bring it home from

[00:06:50] **Adam:** school. I mean, both of my kids are lucky enough to be old enough to be vaccinated, but they could still get it.

[00:06:55] **Adam:** And then if they get it and bring it home and it affects me, I'm vaccinated boosted, but you know, then if I get it and, heaven forbid something bad happens to me because of it. I would hate for that to sort of hang around their neck,

[00:07:09] **Carol:** Right. Did they brought it?

[00:07:10] **Adam:** even though I wouldn't want it to, but, but, you know, I would hate for them to feel like it should,

[00:07:15] **Tim:** a general anxiety and fear of it. I mean, I'm not been able to see my parents. I saw them once when, like in June, when we thought everything was done, we went to go visit my parents because my mom has like half of a working kidney. but it's like, that's the only time. And it's like, they're scared.

[00:07:27] **Tim:** They don't want, my, my last week, my triumph was my thing about my son, max. Who's having that dinner that they're throwing for him for being the star student and having the sat scores, they want to come, but they're not going.

[00:07:40] **Tim:** And it's that just, it's a sad, they've missed. They've missed and they're getting older and they're, they've missed like the teenage years of both my kids,

[00:07:48] **Adam:** Yeah.

[00:07:48] **Tim:** my son's going to like a foot and a half since the last time they saw him.

[00:07:51] **Tim:** So it's ridiculous.

[00:07:53] **Adam:** I'm getting pretty tired of like zoom birthday parties.

[00:07:56] **Tim:** Yeah,

[00:07:57] **Carol:** I

[00:07:58] **Adam:** So,

[00:07:58] **Tim:** I'm sorry. You're feeling like that, Carol. I hope it gets better.

[00:08:02] **Carol:** Meaty. Meaty. It's got to get better. I'm not going to stay down long, so, or I'm just going to be like, I can't code this week. I have to do something else. Cause I'm going to cry.

[00:08:11] **Tim:** you need to talk, we're

[00:08:12] **Carol:** Oh, thank you. Thank you. All right, Ben, what do you got going on?

## [00:08:17] Ben's Failure

[00:08:17] **Ben:** I'm also going to start off with a failure here. And,

[00:08:20] **Tim:** Boy, am I,

[00:08:20] **Tim:** the only one with the win?

[00:08:22] **Carol:** We'll have

[00:08:22] **Carol:** to wait

[00:08:23] **Adam:** still gotta wait for

[00:08:23] **Adam:** me.

[00:08:24] **Tim:** Oh,

[00:08:24] **Adam:** You gotta wait.

[00:08:24] **Tim:** All right.

[00:08:25] **Ben:** so I had mentioned in previous episodes that during the holidays and early in the new year, I had been working on just some upgrading tasks on our, Legacy app at work and upgraded our angular JS version to a much more modern angular JS version. and I had done that mostly because there was a deployment freeze at work for sort of the two weeks around Christmas and new year's.

[00:08:48] **Ben:** And I sort of just assumed after that I would get back into the swing of quote unquote feature development. And, I've been really struggling, kind of getting my groove back. and, know, I've just been floundering and not quite sure what I want to be working on.

[00:09:02] **Ben:** And, part of it too is, as I mentioned, many times I'm on the legacy platform and pretty much everyone else in the company except me, is working on a modern platform. And what that means is that when I have victories to sell. I don't really have that many people to celebrate with. And even the people on the sales and customer success team, who we're still very much focused on users on the legacy platform, they've begun migrating a lot of their sales efforts towards the new platform.

[00:09:28] **Ben:** So even these entirely unrelated to engineering folk, who I could sort of bounce victories off of, even there are fewer and farther between now and not having this, echo chamber of cheer,has definitely been negatively impacting my motivation. But, I will I'll turn it around a little bit and just say that just this, this afternoon I did start creating an epic and laying out some tickets for, for a new feature that,am I going to complete it?

[00:09:53] **Ben:** I think so. Will it add value? I dunno. I hope so, but,I'm putting faith in the idea that if I can just close one ticket at a time, Oh, I'll get that feature to something that's valuable for our users. And, yeah.

[00:10:07] **Adam:** The other.

[00:10:09] **Ben:** And so it's just a little slumpy,

[00:10:12] **Carol:** yeah, the isolation is bad. I feel like when you're working on a project alone and, or even just with a couple people, and you're not getting feedback from others and you're not getting to enjoy like more celebration. Cause you're also not seeing a lot of other teammates succeed either. I mean, you all are kind of at the same pace.

[00:10:30] **Carol:** So I have 14 people on my team that I get to watch celebrate victories all the time. So that does help. So even if I'm not achieving, I'm not isolated off, not achieving on my own, if that makes sense at all.

[00:10:41] **Ben:** yeah. I think so. I think so, but, we'll see. All right. So Adam, which direction you're taking us in?

## [00:10:47] Adam's Failure In Triumph Clown Makeup

[00:10:47] **Adam:** how's that so far, we've got one triumphant, two failures. I'm going to, I'm going to add to the pot here. A failure in triumph, clown makeup. I'm gonna

[00:10:55] **Tim:** So I am the only one with this dry.

[00:10:57] **Adam:** Oh, well, let's see here. Let's that's how I'm couching it. You guys tell me at the end of this, whether it's a triumph or a failure, I'm going to say TDD is really hard to do, right?

[00:11:06] **Adam:** So TDD test driven development, right? I've been reading the book, learning about how to do it, trying to get better at testing fundamentals so that I could then move into doing some actual TDD. So this week I started a project where I was able to start from scratch, which to me feels like, the best case scenario for success with TDD.

[00:11:28] **Adam:** and, so I did, I decided to do TDD with it. I'm also doing TypeScript, which is, maybe it's biting off too much to do too much to learn in one project, but both are going reasonably well. For me, I've talked, I think last week about how I've been enjoying TypeScript, and it's gone, the TypeScript is going really well for me, TDD. I struggle with, I believe it is the right way to go for a variety of reasons. And I like the result that I'm getting out of it, but it is so hard not to break the rules of TDD. Right. I have 20 plus years of experience of just sitting down and writing the code that I need to write. Right. When I think about a feature that I need to complete code starts pouring out of my brain.

[00:12:09] **Adam:** And it's hard to turn off that faucet and write the test that proves the code doesn't work yet, and then go write the code. And, so as I've been trying to TDD this project, it's I started out doing terrible and I'm getting a little bit less terrible, I guess, every day. And when I say terrible, it's like, I write a test cause I know I'm supposed to do that.

[00:12:29] **Adam:** And then I go to start to implement the feature and I write the feature code and then like, I go just a little bit too far and push past making the test pass. And then I catch myself and I go, oh no. I was supposed to write a test for that. So maybe I'll comment out that extra stuff, go write a new test and what gets on my nerves about it.

[00:12:46] **Adam:** It's like, okay, but that's not the logical thing to test next. Right. So then I've got this code that I can either leave, comment it out and maybe lose or forget about. and now I've got another test. That's sort of a different sort of thing that I want to work on next. I don't know. it's frustrating to have to try and rewire my brain after 20 years of experience doing it without this approach.

[00:13:08] **Adam:** But like I said, I really like this process. I like what it's doing to my code. It's making my code more tests. and definitely refactoring, right? If you're not, if you don't have tests, you're just changing and

[00:13:23] **Adam:** I'm getting better. The other thing about this too, is I'm trying to keep in mind that this is my first TDD project and to have the proper amount of appreciation for the fact that just knowing that it's my first time is proof enough that I'm going to complete the entire project and do it poorly, but then, I'll do the next one better and the next one better.

[00:13:50] **Adam:** Right. But at the same time, not use that as an excuse to cut corners. It's.

[00:13:57] **Tim:** Incremental growth.

[00:13:58] **Ben:** Yo, I'll tell you there's being technically proficient in a lot of things, programming related. There's I think this inherent sense that when you move to something very closely related, that you'll just immediately be good at it. And it's very humbling to then realize that's a totally different mindset and a totally different way to attack problems and requires a totally different learning process.

[00:14:22] **Tim:** I apologize if you said this in your description, but are you writing the test first

[00:14:29] **Tim:** and then the.

[00:14:31] **Adam:** Yeah, true to is as best as I can accomplish having never done it before. And, just read a book and trying to put into practice the lessons that I'm learning, trying to do real TDD.

[00:14:43] **Tim:** 'cause that's the thing I find hardest is doing the test first. I many times I'll like try to do the test first and I'll be like, I can't figure this out in our, write a function that does it. And I'm like, okay, now I know what I need to test against.

[00:14:56] **Adam:** Right.

[00:14:56] **Carol:** I think that's because that's how our brains are wired and how we've been doing it for so long. Like Adam said, it, the code disclose out, right. It's easier to write the function than it is. Write the test.

[00:15:07] **Tim:** and I still think there's value in it because a lot of times the tests will tell me that I'm doing too many things in this function. It's not testable because I'm doing three things in any one of those three things can break. So I got to break that out, refactor it. so yeah.

[00:15:19] **Tim:** but I agree. it's hard.

[00:15:21] **Adam:** So today I kind of had an inflection point where I finished a whole bunch of features and the code was at a hundred percent code coverage, every line, and every logic branch was covered by tests and. So I took that moment before I started working on something new to run a couple of quick stats.

[00:15:40] **Adam:** And I have some numbers here for you

[00:15:42] **Carol:** so I, I want you guys to guess, if you haven't already seen the numbers, what do you think? The number of lines of test code, including mocks and mock data, per line of app code is number of lines of test code per line of app code

[00:15:57] **Carol:** Three. Yeah, I would say three to,

[00:15:59] **Adam:** Ben.

[00:16:00] **Ben:** I was going to say two to three, but I'm, I'm not based on experience.

[00:16:05] **Adam:** Okay. The actual answer for this particular app that I'm writing was 9.56.

[00:16:11] **Carol:** Ooh.

[00:16:12] **Adam:** so what I've written so far is 322 lines of application logic and a little over 3000 lines of tests and mocks.

[00:16:22] **Ben:** Are you finding that in that 10 X there's a lot of repetitive setup kind of code.

[00:16:28] **Adam:** Yeah, it very much is, but I was actually, showing a little bit of it to Adam Cameron, the guy who we're always talking about is like pushing us to do more and better testing. because he's a friend of mine, a friend of the show and he's, passionate about this stuff. So he was,

[00:16:44] **Tim:** and my number

[00:16:45] **Tim:** one hater.

[00:16:46] **Adam:** and so he's always game to,kind of help me improve and stuff.

[00:16:51] **Adam:** And, so showing him a little bit of the tests and the code and stuff, and, he pointed that out as well. Like there's a lot of, especially, if I'm writing something that's going to be. Hitting the database, a bunch. It can be a little bit verbose to set up. Okay. Like, okay, then it's going to call the database and I want this to be the response.

[00:17:11] **Adam:** Then it's going to call the database again. And I want this to be their response. You can, especially when you want those to be, readable. Right? So you're, you've got a bunch of line breaks baked into that, I'm returning a big Jason blob. So one database response might cover 10 plus lines.

[00:17:26] **Adam:** but, and then the reason that it gets so verbose so fast, it's like, there's so many different logic branches in the code that you need to have, say 10 tests for a reasonably small chunk of code. And then those tests all have variations on the same. Inputs to, to test all the different paths through the code.

[00:17:47] **Adam:** And so you've got to modify the input data for the function for every test implication, which gets kind of hairy. So

[00:17:57] **Ben:** it'd be interesting to see if either Tim or Adam could convince you to test your SQL statements like we're talking about on

[00:18:05] **Adam:** that's it. You know what, it's funny that you should mention that this application, is th like it is kind of a standalone application. It is a dynamic SQL builder and.

[00:18:16] **Ben:** oh,

[00:18:16] **Adam:** So I've talked in the past about our segmentation engine, where we,you give it criteria and it builds a SQL statement and runs out against the database to get like, you might say, I want everybody with an engineering degree from the year 2000 who lives in this zip code, who has made a donation before, right?

[00:18:31] **Adam:** Whatever, all your different criteria are. Well, each of those criteria is like defined as a database row and all the different things that you can do so that you can say, has made a donation or you can say a donation of a certain amount. And so you can say, I want a greater than, or greater than, or equal or less than, or between, or, we have like date, operators.

[00:18:49] **Adam:** So you can say like month and day match, but not year. So that's useful for like birthday, right? Give me everybody whose birthday is today, but I don't care what the year is. so there's, a lot of variation in this. You give it a bunch of criteria and you say, okay, I care about this field. We use this operator.

[00:19:06] **Adam:** This is the input value, maybe a minute in the max or whatever. And it spits out some SQL statements. So this is a SQL generation engine. Really. There's a big chunk of what this application is doing. And, so that's like 90% of what these tests are, is, give it some input and it spits back some SQL.

[00:19:25] **Adam:** And I'm just verifying that it's generating the correct SQL.

[00:19:29] **Ben:** Nice. Nice.

[00:19:30] **Ben:** Nice.

[00:19:31] **Carol:** You don't care about the return. You only care about the generated

[00:19:34] **Adam:** Um, I do also care about the return only in as much as the sort of the next step after running the query is massaging that data and doing some different things with it for other purposes. So I don't care so much what the return is, but I do have to model out some sample responses so that I can do. Test the downstream processes that happen after you get a response.

[00:20:02] **Carol:** because that bit me today, I put up a branch and I was like, why is this failing? Like, why is my PR failing right now? This doesn't make sense. Nothing. I worked with only to find out that some of the integration tests expected this record to never change while in production, they literally just removed this user from this record.

[00:20:20] **Carol:** They thought this user would never be removed from. So the assertion bells, because it's no longer assigned to it. I'm like, why are we checking that this user is still assigned to this record? Like this makes no sense for an integration test. So I was like, I'm going to go rewrite this.

[00:20:37] **Adam:** Hm.

[00:20:37] **Ben:** Well, speaking of integration tests, I know on one of the previous calls, we had talked about a quote being something like write tests, not too many, mostly integration tests from a TDD standpoint. When do you start to think about integration of tests and I guess, are there TDD tests that you skip over in lieu of?

[00:21:01] **Ben:** Oh, I'll test this with an integration test later.

[00:21:04] **Adam:** So I kind of think at three levels, right? So you've got, and I imagine if you ask an expert, there's probably more to it than this.

[00:21:10] **Adam:** And I, my viewpoint on it is not very well educated and probably not nuanced enough, but I think of it in terms of unit integration and end to end, where unit is, you broke it out into the smallest possible, like pure function sort of thing. and. It may not even make sense as to why you're expecting the behavior that you're expecting, but it's just proving, given this input, the function returns, this output, integration, I think of as a, if the application starts at one end of the assembly line and ends at the other end of the assembly line and integration test for me is some window where you can see some portion of the assembly line and you can control the inputs and you can inspect the outputs of just that window of the line.

[00:21:51] **Adam:** And so you can,given some specific inputs, is it, am I getting what I'm expecting at this other checkpoint at the other end, somewhere else in the middle of the assembly line? And, that's useful because it gives you the opportunity to make some assumptions. If that test is passing, there's a really good chance that everything between the start and the end point is.

[00:22:14] **Adam:** And less now, if you're adding tests after the fact that may or may not be true, if you're doing TDD, then you're more or less guaranteed. if you did TD, right. I guess they would say they, that you're guaranteed that everything that your tests in force is actually true about your code. and then end to end test is obviously like, control the browser log in and that sort of thing.

[00:22:35] **Adam:** does that answer your question? oh, you asked specifically about integration tests and TDD,

[00:22:39] **Ben:** well, I guess like when do you think about writing them and do you ever defer writing the low-level tests in lieu of an integration test, but you're saying.

[00:22:50] **Adam:** yes, actually. So like that tweet said, write tests, not too many, mostly integration. I try to focus mostly on integration tests. Imagine some portion of the code, you've got a function that may call other functions and then it returns some results. and, so write code that tests that, and then write those functions so that they do the thing.

[00:23:13] **Adam:** The problem is if you bite off too much at once, then it's difficult to test and you need to scale it down. Some,

[00:23:21] **Adam:** and for me, like I had something come up today where I, like, I had written an integration test for a whole chunk of code and it was working great, except that my code coverage was telling me there was this one little branch of logic that wasn't being tested. It was like, setting a default if, if the value wasn't, there, right?

[00:23:38] **Adam:** Like a CF parameter sort of situation. And. Given that my situation is a little bit unique. I am bolting on a TypeScript, a application that shares data with a CFML application type script to being statically typed is a little bit more strict, is a lot more strict about data. It moves around and the CFML application is writing adjacent blob to the database.

[00:24:02] **Adam:** And then this app is pulling it out of the database and, and operating on it. And so basically my app was set up to not just assume that a key in that Jason blob was going to be a string, like treat it as if it could be null or undefined, and give it a default value in that case. And the tests were passing, but saying you didn't cover this case.

[00:24:25] **Adam:** And so what I did was I refactored out that, that line or two of code into a separate function, and I wrote a unit test for that specifically. So that, so it was like generating a string, a key name that you would use in a cache. And,and using some of the parts of the Jason as part of that key name.

[00:24:44] **Adam:** And I was saying, well, if it's undefined or no, then just use empty string or something. And that's the part that was uncovered. And so what I did was I'm refactored that functionality out into its own function. And then I wrote a unit test that proved that, given an undefined or no value, it would return empty string in that spot.

[00:25:02] **Adam:** So it was a very, it was a very pure function, right? Given this set of inputs,if it's missing a key or whatever, then you get this specific string as an output, doesn't really make a whole lot of sense when you're thinking about the application. But then when you plug it in. To the integration stuff.

[00:25:18] **Adam:** It all works. Does that make sense?

[00:25:20] **Ben:** Yeah, it sort of reminds me of when we were looking at a clean code by uncle Bob, one of the practices that he had outlined in the book. It was something like everything in a method should be at the same level of abstraction. And it sounds a little bit like that. If you have logic, that's just dealing with putting things into a cash as an abstract concept, the idea of generating the cash key almost feels like it should be factored out into its own thing.

[00:25:45] **Ben:** So then you have high level concepts and you're not mixing and matching low level, key generation with high level cash interactions. I'm just

[00:25:52] **Ben:** shooting from

[00:25:53] **Adam:** I,

[00:25:54] **Adam:** I guess that goes back to that our recent discussion about clean code as a teaching tool. Right. it's good to have something to, have a rule of thumb if you don't have a better opinion already.

[00:26:04] **Adam:** but once you have some experience, you start to. Get a better understanding of when it's the right time to break the rules are those rules of thumb. So,

[00:26:12]

## [00:26:13] Audible

[00:26:13]

[00:26:57] **Adam:**

## [00:27:01] Google Charging Free Users For GSuite

[00:27:01] **Adam:** So, we record two weeks in advance, just so that it makes it easier for us to, release on a regular schedule so by the time you hear this, there's a good chance that you already know, but just in case you didn't already know,

[00:27:12] **Adam:** Google is going to start charging their users of their legacy G suite, platform. So basically if you're using G suite on a custom domain for free, Google is going to start charging you for it starting July 1st, and it's going to be $6 per user per month. and that, that includes anything G suite.

[00:27:30] **Adam:** So not only Google docs and sheets and drive, but also just accessing. Which is huge news. I mean, on the one hand, like you said earlier, Ben,we've been using this thing for like 15 years for free, which is

[00:27:44] **Adam:** awfully nice of them, but on the other hand, it kind of sucks.

[00:27:47] **Tim:** Yeah, it kinda does.

[00:27:50] **Ben:** it's offset by the fact that a good hub had allowed private repos to appear for free accounts. Something like, I don't know, like six months ago, a year ago I was paying like $7 a month for GitHub accounts that I could have private repos. And then they decided to allow free accounts to have private repos.

[00:28:07] **Ben:** So I would downgrade it. So I'm now just reallocating my GitHub funds to a Gmail, I guess.

[00:28:13] **Tim:** Yeah, I have some bad G suite stories cause even paying for it. Right. So we moved to like virtual phone, like Google voice, to set up a Google voice for all my, the folks that I work with. And, there was an error. I was trying to add a new user. Right. I've done this many times before that never had a problem and I clicked it and I got an error.

[00:28:37] **Tim:** So it said, please try again. So I did, I tried again like three or four times, and then my account got suspended

[00:28:44] **Adam:** Oh, no.

[00:28:45] **Tim:** because they said I was misusing the platform. Now they wouldn't tell me exactly what I did and their customer service is terrible. If you have a PR, they're great when they work.

[00:28:55] **Tim:** But if you have a problem with them and there's like, you can't talk to them. It's all like this email form where you have to explain everything without knowing why you got blocked in the first place. And I re appealed four times and they kept get, they kept denying me.

[00:29:11] **Adam:** Wow.

[00:29:12] **Tim:** So at the end of the day, I just like, all right, You know what?

[00:29:14] **Tim:** Google voice is free for an individual for now. I just said all of you just go make your own Google voice account and create that for your phone. Cause we were getting rid of our phone system. So I mean, yeah, the customer service really is bad when there's a problem.

[00:29:29] **Adam:** You talking about Google voice kind of is giving me bad feelings because so I've been a long time user of Google voice since before it was li like the law that you had to the phone companies had to let you transfer your phone number. When you switched companies back in the day, you would switch from Verizon to T-Mobile and you'd have to get a new phone number.

[00:29:47] **Tim:** you millennials don't know about that.

[00:29:49] **Adam:** Hey, I'm barely a millennial. And I know about that. so, in order to not have to deal with that problem, I switched or I got myself a Google voice number and had it like forward to my phone. And then it wouldn't matter if my phone number changed. And of course, like two years later they changed the law.

[00:30:03] **Adam:** but you know, I just long enough that I had convinced all, everyone, I knew all my family,every place on the internet where I put my phone number and I had started putting in my Google voice number. And so that's ever since been my personal phone number is my Google voice number.

[00:30:17] **Adam:** And I do like that it gears ahead of being available on Android or iOS or anything, you can do all the texting you want through a web browser, which is really nice.

[00:30:26] **Carol:** yeah.

[00:30:27] **Adam:** and that's, I use that a lot,

[00:30:29] **Tim:** the keyboard.

[00:30:30] **Adam:** exactly. but, Just like G suite users for free domains are kind of like the redheaded stepchild with all new Google features.

[00:30:38] **Adam:** Like you can't use, a G suite account for so many Google services is a pain in the butt. so for that reason alone, I started a few years back. I moved over all my personal stuff to,just an@gmail.com email address are started the process. I have a lot of stuff to clean up now that they're going to start charging me.

[00:30:55] **Adam:** it makes me worried that because I feel like Google voice gets the same treatment. Like we don't really care about you. then I'm worried that they're gonna take it away from me. And then my phone number is just going to up and disappear one

[00:31:08] **Tim:** Yeah. I mean, because like, like I said, for individuals, they don't charge anything. Right. And so if you're a company and using G suite, they do charge you per user. But, Yeah. All the stuff they don't charge for don't ever get comfortable thinking it's gonna last forever. Eventually either they charge for it or they'll kill it.

[00:31:24] **Tim:** Cause I kill a lot of projects.

[00:31:26] **Carol:** I just need my app scripts to keep running. Otherwise my is going to be a disaster.

[00:31:31] **Adam:** All right. So that's the end of your breaking news, segment at your it's gotta be something other than breaking news, right? A two week old news.

[00:31:39] **Carol:** Yeah. Read all about it two weeks ago.

## [00:31:45] Tech Debt (Question From LD22)

[00:31:45] **Adam:** yeah. Cool. So let's talk about technical debt. we got a question from a listener.

[00:31:50] **Tim:** Let's talk about debt, baby. Let's talk about debt.

[00:31:56] **Adam:** okay.

[00:31:57] **Adam:** So we have a, we got a question from one of our listeners and patrons, LD 22 on Twitter. they asked, how often do people take on tech debt knowing, in advance that it's going to go away in a short amount of time? Like the project is just going to get killed in, say one to three years, or I guess the other side of that coin is.

[00:32:15] **Adam:** is anybody in a situation where technical debt of any kind it's just not acceptable ever

[00:32:20] **Carol:** So, what I'm reading is that tech debt is temporary for a year to three years. Like in my opinion, that's not like a short timeframe at all. That is a long-term commitment to some tech debt. When I say short-term, I'm like, oh, it's not going out this cycle. It's going to get fixed next cycle.

[00:32:40] **Carol:** I'm talking six week turnaround. That's short term to me. I'll have to maintain this a year. That's not going to be fun.

[00:32:48] **Adam:** Yeah. I mean, I guess it depends on what kind of technical debt you're talking about. Right. So

[00:32:52] **Adam:** My definition is just cutting a corner. I'm doing something in that I know for sure. I'm intentionally doing something that is not what I would describe as the right way.

[00:33:01] **Adam:** That's just my definition of technical debt. and I'm doing it because it saves me time or resources now, in exchange for the time and resources to fix it later, I guess. so that could be something as simple as like copy and pasting code in multiple places instead of making a reusable function.

[00:33:18] **Tim:** Yeah.

[00:33:19] **Carol:** That's not terrible tech debt to maintain

[00:33:21] **Adam:** not exactly, it's not terrible.

[00:33:24] **Tim:** Taking bins code from his blog, pacing into your

[00:33:28] **Carol:** Removing all the line breaks first.

[00:33:30] **Carol:** Yeah.

[00:33:31] **Tim:** maybe.

[00:33:33] **Adam:** I mean, I guess to answer the question,the less severe the tech debt, the longer I'm willing to let it go an unpaid,

[00:33:42] **Carol:** I guess I need to know more of the level of tech debt here, so let's assume it's something big.

[00:33:49] **Adam:** well, I also think that you and I read the question a little bit differently. Maybe that's worth exploring. I read this as the project itself is not tech debt, but there's a project and let's just say, you're going to be changing platforms. And you know, you're going to be changing platforms in sometime in the next one to three years.

[00:34:07] **Adam:** So any code that you write on the current platform is going to be in theory, thrown in the garbage in three years time, is it worth paying down any technical debt in that system? Knowing that you're going to be throwing it away. Is, would it be better to save that time so that you can put it toward moving to the new platform or to, toward something else that's going to improve your bottom line or improve developer productivity or?

[00:34:35] **Carol:** Yeah, but then you're not really taking on the tech debt. You're moving the resources to the new project, right. You wouldn't be working on the old, so that's not taking on tech debt. That's just letting it sit and write itself out.

[00:34:46] **Adam:** if, I guess it depends. Right? So

[00:34:48] **Adam:** sometimes tech debt means that you are not automating a process. So then that process is manual

[00:34:56] **Carol:** Oh, those are the worst. Someone go upload this Excel sheet because we don't know how to get the data in here. No,no, the answer's no. Okay. If we weren't clear, no means no, you guys

[00:35:12] **Ben:** I very much liked the concept that you'll never know as little about the thing that you're building as you do today. Meaning that tomorrow you'll know a little bit more than you did today and in a month, you'll know a lot more than you did today.

[00:35:24] **Tim:** that's funny. My, I had Chinese food today. That was my fortune cookie saying it was awesome.

[00:35:30] **Ben:** awesome. So I look at technical debt sometimes as leaning into this idea that you don't know enough about your project yet. So I will often build a, say a sub optimal solution today because I don't even know if this feature is going to get buy in and then I'll deploy it in some sort of a MVP style. Put some metrics on it. See if anyone starts to use it. If they do start to use it, what kind of performance is it getting? And then reevaluate the severity of that technical debt. and most of the time, I'd say the vast majority of times, at least in my experience, which is very narrow, the technical debt turns out to be fine.

[00:36:13] **Ben:** Like things perform good enough, or it's used by few enough people where the performance is not a huge impact. And, and then you get to move on to other things instead of worrying about necessarily over architect in the quote unquote better solution.

[00:36:27] **Adam:** Strong agree. I'll put

[00:36:28] **Adam:** my stamp

[00:36:28] **Carol:** Yeah. I approve. Yeah.

[00:36:30] **Adam:** that's just textbook, not premature optimum.

[00:36:34] **Tim:** Yeah.

[00:36:35] **Ben:** It's interesting. I wonder how many people here have been in a situation where, you're dealing with someone else who has to review your code and the two of you have very different ideas about what is okay for technical. Because there is nothing more frustrating than trying to get a pull request approved by someone who is pushing back hard on like every decision you make.

[00:36:56] **Ben:** And you're like, bro, I don't even know if anyone's going to use this. Why are you giving me so much?

[00:37:03] **Carol:** told you I almost cried it. The pull request was seriously. We should create like utilities function, the maintain, all of these, like across the system, a whole bunch of like different things. I'm trying to just fix one error that's happening in production. Can we just create a story and let's come back to this and actually create the utilities function to incorporate all of it.

[00:37:27] **Carol:** wipe. Yeah. Look like why did you throw that on my PR? That's just validating a string right now. Like, that's it like, just let it do its thing. I understand that we could put this in the utility function and we could then not duplicate code. Fine. We can do that, but not on my PR right now. Not today.

[00:37:43] **Carol:** I've had a bad week. You guys?

[00:37:46] **Adam:** Well, so, I've started when feedback like that lands on one of my PRS, what I'll say is I'll file an issue for that. Right. And I go and I file an issue for it. And then when I want to do it to somebody else, when I feel myself starting to type that in and get that, that vibe in my head, I'm like, I'm going to go file an issue for this.

[00:38:03] **Adam:** And I go, and I'll leave a comment like this inspired this issue and I link the issue or whatever.

[00:38:09] **Adam:** So.

[00:38:10] **Adam:** I'm trying to sort of like lead by example then.

[00:38:12] **Carol:** So we use Bitbucket and like all of our, like all the Atlassian products and stuff. So when we are doing our pull request in there, and that's where we review everything at, on each comment, I can just click a single button that says create task or create an issue. So it makes it super easy to link everything together.

[00:38:30] **Carol:** So that is a good thing, but I'm like, oh,

[00:38:33] **Carol:** so yeah. So we all agree. We all have tech debt. Right.

[00:38:36] **Adam:** Oh yeah.

[00:38:37] **Carol:** we have to take it on.

[00:38:39] **Tim:** I think most people totally under estimate the amount of tech that they have, because they don't know what they don't

[00:38:46] **Tim:** know.

[00:38:46] **Carol:** yeah.

[00:38:48] **Tim:** Right. They're like, Oh, yeah. I wrote this really well. and someone reviews it and they're just as ignorant as them. And they're like, yeah, this is great. But you know, if you have a team of any reasonable size where you have different levels of, programmer maturity, you're going have. Tech debt at some point. Right. And if you think that you don't have any tech debt, I think you just have ignorance because you have some, you just don't know about it yet. you'll figure it out later that you have tech debt. I, I think not having documentation is tech debt, right?

[00:39:21] **Tim:** It's not

[00:39:21] **Tim:** code, but if you don't have documentation, that means that the people that come on to your team and start working on something and they don't have any documentation to go by, they're just going to create chaos inside your system because they don't have any guidance. Right. So I think we all underestimate the level of tech debt that we have.

[00:39:44] **Adam:** So instead of like coding a chaos monkey thing, maybe I'll just hire somebody and give them like full access to everything and,and, uh,and no instructions.

[00:39:53] **Carol:** Yep. Click, whatever you want to click. If you have access at your.

[00:39:58] **Ben:** I'm typically very comfortable taking on a tech debt because I feel like it is a thought-through through. But one piece of tech debt that I always feel bad about. and I'd, haven't been able to break this pattern is we'll create a user interface that has a particular style of interaction.

[00:40:16] **Ben:** And it's, it works really well for

[00:40:18] **Ben:** customers who have a small amount of data, and then we'll get like a whale of a customer and they have so much data. And the interface was just never designed to deal with that much data effectively. And then we'll have to build another interface. That's sort of like that one.

[00:40:32] **Ben:** And I think to myself, I really should make it workable for people with a lot of data, but in order to do that, I'd have to like completely rethink the way all the interaction patterns happen and where I'm loading data from and where pagination is happening, how filtering works, et cetera, et cetera, et cetera.

[00:40:48] **Ben:** And as I've mentioned, many times, I'm one person on a legacy team of one. And, I just don't have that time or that the sort of freedom of operation. And, so I ended up creating another interface that has all the same problems that I know will happen with a customer that has large data. And I just don't have the resources to break out of that pattern.

[00:41:09] **Ben:** And every time it happens, I feel terrible. And I just hope that I'll do something slightly different in this interface that mitigates some of those performance problems. Like, I don't know. It's just, I hate it. I hate feeling that way. I hate knowing that I'm introducing a problem. That's what it is. I don't mind taking on tech debt when I feel like it's cutting corners.

[00:41:30] **Ben:** I don't like taking on tech debt when I know I'm creating problems

[00:41:34] **Ben:** that, that not everyone will have.

[00:41:37] **Tim:** Yes, same thing with database optimization, right? you build, build a database and it works great, but then all of a sudden you hit a certain level of rows and now it's like falling apart because you didn't index properly or you didn't build your tables properly or whatever. So yeah. It's like, why is it, why did it stop working?

[00:41:55] **Tim:** It was working fine a couple of weeks ago. Nah. Well, well he got a whole lot more data.

[00:41:59] **Adam:** I think that that's what you want to happen though. Right? Cause if you, if that never happens to you, it means that you spent a whole bunch of time optimizing for every possible scenario and probably 90% of the scenarios that you optimize for never happen.

[00:42:13] **Carol:** Never going to get cross.

[00:42:15] **Adam:** And so,

[00:42:16] **Tim:** Yeah, it try to explain that to a customer like.

[00:42:18] **Adam:** we work in different industries and maybe that's not something that you can deal with. And you, I think in your industry, credit card processing stuff, other financial stuff, you have to assume a certain amount of scale to start with.

[00:42:32] **Tim:** you deal with people's money. They get very ticky about that.

[00:42:35] **Adam:** yeah. and I think that, there any given feature that I develop has the potential to be a big hit and go, have to churn through a lot of data has equally as much potential to just sit on the shelf, going unused for three years at a time. So, I like to start with a naive approach, just do the minimum possible thing to make it work and wait for it to break under heavy load, under pressure or whatever, and then go, okay, great.

[00:43:01] **Adam:** This feature is actually being used. Let's make it.

[00:43:04] **Ben:** Yo a thousand percent. this is the argument that I get into with the people on other teams of the company. Cause they're working on the new platform and I'm working on the old platform. And while they're doing their stuff, I'm continuing to try and move the goalpost on the legacy platform because we have paying customers and they expect some degree of service and and they'll say, well, what happens when we have a customer on the legacy platform, that's using something you built for them.

[00:43:29] **Ben:** And then they moved to the new platform and the new platform doesn't have that. Like how are we supposed to deal with that? And I look at them, I go, you're welcome. I just did a lot of user research for you. I just proved out feature. And now you can go build

[00:43:41] **Carol:** That's

[00:43:41] **Carol:** needed. Yeah.

[00:43:42] **Tim:** actually use

[00:43:43] **Ben:** Yeah. I'm like, are you complaining about all the features that I built that no one cares about when they leave this platform?

[00:43:48] **Ben:** Like, no, they're not all going to be winners, but when they are a winner, that's when you should be thankful that I put time and effort into it, because now you don't have to think about it. Now you just have to build it.

[00:43:58] **Carol:** I agree.

[00:43:58] **Adam:** Congratulations. You played.

[00:44:02] **Tim:** Cell phone and what broke been,

[00:44:09] **Adam:** I did it.

[00:44:10] **Tim:** you broke been good job.

[00:44:16] **Adam:** That's it. We can call it a show, their accomplished.

[00:44:20] **Tim:** I will also challenge the assumption that they say, they say that the project is stopped gap. It's gonna be temporary one, one to three years. A lot of times what you think is that every one to three years, it turns out to be a lot longer. Right. So, I mean, Ben, how many, how long has your legacy app been labeled that?

[00:44:37] **Ben:** I kid you not the legacy app. the legacy app was supposed to be like six to eight months. and that was about four years ago

[00:44:45] **Tim:** Yeah.

[00:44:46] **Adam:** Okay. But how many people were on the team four years ago?

[00:44:50] **Ben:** on the legacy team, many more,

[00:44:53] **Adam:** How many

[00:44:54] **Ben:** uh,ballpark, I mean probably in the twenties.

[00:44:59] **Carol:** Yeah.

[00:45:00] **Adam:** So the writing has been on the wall. It's just not written in English. It's written in dwindling staff.

[00:45:05] **Carol:** Yeah.

[00:45:07] **Tim:** Yeah,

[00:45:07] **Tim:** but that's my point. I E everyone's like, oh, this will be gone relatively soon. Well, maybe as long as it's not completely broken and it's making money business leaders, aren't going to be like, oh, just shut it off. I don't care what, I don't care what happen. I don't care what customers we lose, because those early customers that you got that are on the legacy system, they're important, they have value.

[00:45:28] **Tim:** And so, so did say that it's going to go away quick is not as wishful thinking. I think so. I think you still need to try. To continue to remove tech debt out of, whatever it is that you think is a temporary project,

[00:45:42] **Carol:** because it's probably not. Yeah.

[00:45:44] **Tim:** but it needs to be strategic. Right. I mean, it's like, it doesn't need to be perfect.

[00:45:47] **Tim:** No, but does it just not need to error constantly?

[00:45:51] **Tim:** Yes.

[00:45:52] **Carol:** Security needs to be maintained. Yeah.

[00:45:55] **Adam:** yeah. and another one is like having no tests is a form of technical debt.

[00:46:00] **Tim:** True.

## [00:46:01] Ben Wishes He Had A Test

[00:46:01] **Ben:** No. Happy to know that I sort of wish I had a test the other day.

[00:46:08] **Carol:** Oh,

[00:46:10] **Ben:** so okay. I,I will freely admit that in the past. I often talk about that. I don't have tests and most of the time it's fine. Quote, unquote fine. because I'm working in such a narrow part of the application. I see everything that I'm going to change and it's like, there's one path or two paths through this code that I needed to test manually.

[00:46:29] **Ben:** but the other day we were trying to update one of the, container, like the base image for one of our containers or Docker containers. And, I don't understand servers and I don't really understand containers. And I certainly don't understand how apt get works, which is like, it's like a package manager for Unix.

[00:46:47] **Ben:** Right. I think there's a bunch of them like yummy and advocate and a couple of others.

[00:46:51] **Adam:** different flavors of Linux have different package

[00:46:53] **Ben:** Gotcha. Okay. I don't understand how versions on those things work. I don't know if you can pin versions. I don't know if it's even clear how you can pin them or where you can see the list of versions. Anyway, for reasons that I still don't understand, we tried to upgrade, the base image and it changed one of the versions for one of our app, get installs from like 0.3 to like 3.7 and had completely broke every API that we were using.

[00:47:19] **Ben:** and it was just a part of the application that I didn't smoke test after changing the image. And, unfortunately I had deployed the update to production before I caught it. And thankfully we only got a handful of errors because again, it's in this sort of weird corner of the application, but I, I shook my head and said, I wish there was a test for this.

[00:47:41] **Ben:** That would have been nice.

[00:47:44] **Adam:** we're getting in, we're getting in

[00:47:46] **Ben:** So it, and it gets, it gets even more frustrating because the area of the application that broke, I actually did test. but I didn't realize that the type of file I was testing with actually had its own edge case, deepen the code. Basically it said the thing that's going to break, if you're testing was a JPEG, don't do this thing and it skips over it.

[00:48:06] **Ben:** And, and then, so it only started to break when people started to upload non JPEG images. And it just happened to me that I didn't test with that.

[00:48:13] **Adam:** Hmm.

[00:48:13] **Ben:** I blame it on code complexity, more than not having a test, but.

[00:48:18] **Adam:** so like I said, having no tests at all as a form of technical data or missing tests is technical debt. And I guess the question then is, when should you pay that off or does it make sense to write those tests? If you know that the code that you're going to be testing is going away soon.

[00:48:35] **Adam:** And for me, I think the answer is, it depends on how soon, and it depends on how critical. Of a part of the application is untested, right? If it's your payment collection stuff, it doesn't matter if you only have a week left. Like if it's going to affect your bottom line like that, then you should have confidence that it's not broken.

[00:48:56] **Tim:** I would say that if you don't have tests at all and you're like, where are you going to put your resources? Right. So the things going away. One to three years, maybe four years, maybe five years. Where's the best resources for that. And I don't know Adam, camera's going to hate me for this, but I don't know if test is really the best thing to go.

[00:49:13] **Tim:** Like we don't have any tests. Let's go build a bunch of tests. I don't know if that necessarily is going to be a best use of resources.

[00:49:19] **Adam:** I don't think that he would argue with that statement, given enough nuance. Right? Like I even, I agree with you, like, the. Nobody is going to agree. Oh, well, whatever. I can't speak in generalizations it's I don't think it is a smart thing to, stop the ship and start writing tests and do nothing but write tests.

[00:49:40] **Tim:** I mean, how do you make that to the C level? It's like, listen, we're going to write a whole bunch of tests to make sure that this thing that supposedly is going away very soon, w works well. but we're not going to add any new features. we'll only fix breaking bugs during that time.

[00:49:52] **Tim:** and it probably would take a lot longer than we think, and they won't make us any extra money.

[00:49:56] **Tim:** that is extremely hard sell.

[00:49:58] **Adam:** Exactly. Which is why I think that you need to couch it in. Okay. So the test that we're going to write are for the things that break in the middle of the night, for the things that collect money for the things that are gonna, that are gonna make us as a business or as a team, or, like you, my boss, that's gonna make you look bad because it broke.

[00:50:14] **Adam:** are the things I want to test.

[00:50:16] **Carol:** You need to cover the things that are going to cost you, and that does make it to the C-level. And that does make sense. this is costing us face with our customer. This is costing us resources to keep fixing it and we keep introducing more problems. So I feel like if you're supporting this project as a, as like a stop gap, that if you're adding new features, you should be adding the test with it and fixing where the bugs happen to add a couple of tasks.

[00:50:40] **Carol:** You don't have to cover the whole system, but what you're touching could be easy,

[00:50:43] **Tim:** at the end of the day, what's the user experience, right? that's all, it really matters. the users are the one that's matters, not the coders don't

[00:50:49] **Carol:** We mean nothing.

[00:50:51] **Tim:** Yeah. We mean nothing.

[00:50:53] **Tim:** you know, we're building it for them. So if the users are having a bad experience, that has to be stopped at all costs.

[00:50:59] **Ben:** I have run into issues. Speaking of user experience where. There's an area of the application that I would really love to refactor because it's a really hard part to maintain. And because it's a hard part to maintain, I feel like I'm very limited in trying to improve the user experience in that area of the application, because it's just super complicated and super old, which is just poorly done.

[00:51:23] **Ben:** And a couple of years ago, I went to my engineering manager at the time. I said, Hey, I'd really love to set aside time to just completely refactor this area of the application, incrementally move files around and start to co-locate things that live together and just make it cleaner. and I said to him, I said, I can't promise you that this will be a huge return on investment.

[00:51:43] **Ben:** All I can tell you is that today working with that code is extremely challenging and it's very limiting in what we can do. And ultimately, and I'm not blaming him ultimately as a team, we decided that because we didn't, we couldn't prove that there'd be a good return on investment. We decided not to do.

[00:52:00] **Ben:** And this was like three years ago. And again, it was this case where, oh, how long is the legacy platform going to be around? Oh, not that long. It's not worthwhile. And now, cut to three years later, that area of the application is still terrible. It's still very hard to improve and I've lost three years of potentiality of improving it because I didn't want to put time into cleaning up that tech debt.

[00:52:24] **Tim:** I think that the case you have to make. With return on investment is how, I mean, how much time is a highly paid software engineer going to spend in there because it's badly written. Right? So, I know that feeling, there's some portions of code that I go, oh my, I do not want to go there. dragons, be there.

[00:52:44] **Tim:** And,you know that if you have to touch this portion of the system, that it's going take you three to five times longer than other places that are better written. And so I think that needs to be the argument is like, look, it might not be return of investment from our customers, but it's a return on investment on people's time because people's times.

[00:53:05] **Ben:** Yeah, that's great. I don't think I've ever considered it from that point of view, from a making a case for the work I've only ever really thought about it just in terms of how long would it take now and like what money do we get from it?

[00:53:18] **Tim:** Yeah.

[00:53:19] **Tim:** What else could I tell you that, if a bug happens in this section of whatever the feature is, it would only take them 30 minutes to fix rather than, 10 hours. I mean that, that's a huge cost savings, so yeah, I definitely get you there.

## [00:53:35] Answering The Question On Tech Debt

[00:53:35] **Carol:** So did we answer the question?

[00:53:37] **Adam:** so, okay. here's I think what the answer to the question is I can sum it all up very succinctly for you here. It depends.

[00:53:45] **Tim:** Yep.

[00:53:45] **Carol:** We all take it on.

[00:53:47] **Adam:** my answer.

[00:53:48] **Ben:** I mean, I think if I can be a little stronger on a point, I think taking on technical debt is the norm. And I think fighting super strongly fighting against technical debt, I think is the outlet.

[00:54:02] **Adam:** Oh yeah. I think that, so to, to throw it back to something very old, the Joel Spolsky. Joel on software. one of his big things like it, do you remember the Joel test? It was like a list of criteria to evaluate a company, for like whether or not you would want to work there or give a company a score to like, be able to rate them against each other.

[00:54:23] **Adam:** It was like, developers get private offices and a bunch of other things. One of the things on that list was do you fix bugs before working on new features? And I think that there's a certain amount of truth to that, but what system has zero bugs,

[00:54:40] **Ben:** Right, right.

[00:54:41] **Adam:** right?

[00:54:41] **Tim:** the answer is supposed to be Yes. you fix bugs before features.

[00:54:45] **Adam:** That's supposed to. and I mean, I guess if you want to take a nuance to look at it, right, then you fix important and, or urgent bugs before working on new features.

[00:54:55] **Adam:** that seems fair,

[00:54:56] **Tim:** what about we only do bug fixes and never add features. not a company I want to work for.

[00:55:01] **Adam:** yeah. Right. and it's also not a product I want to buy. Right. I know it's not going to grow. So

[00:55:08] **Tim:** And the question there was, How often do people take on tech debt knowing that it'll go away in a short timeframe and I've, I'm going to rephrase it.

[00:55:18] **Tim:** I think people take on tech debt all the time, regardless of how old it's going to be. I have to do is in my code that had been there for several years and I've just, don't get around to, they work. I hate like nested if statements, I hate them, I want to refactor the mountain. Sometimes I just do them and then I never come back and fix them.

[00:55:39] **Tim:** And that's on me. But as far as the sin goes, that's kinda minor. It's like jaywalking. Yeah. Th there's bigger ones. there's bigger fish to fry normally than that. So there's some level of tech debt and every single project,

[00:55:54] **Adam:** where's the line between bad code and tech debt. And the only thing I can think of is tech debt is if you're doing bad code on quote unquote bad code, not that it's evil, but it's just on this side of the line between good and bad. your tactic is if you know you're doing it and you're doing it anyway, like on purpose versus you're just coding and you don't really think about it and it could be.

[00:56:16] **Tim:** Or you don't know any better.

[00:56:17] **Adam:** Right. Like at some point you learn or you, something happens, right? Like you have a performance issue, then it becomes tech debt. So you don't necessarily get to choose whether or not you're taking out tech debt. Sometimes tech debt happens.

[00:56:31] **Carol:** And, you

[00:56:32] **Adam:** Yeah.

[00:56:32] **Tim:** I like that you might be dealt with tech debt, but tech debt is not done with

[00:56:38] **Tim:** you.

[00:56:39] **Adam:** Word

[00:56:39] **Tim:** Love it.

[00:56:40] **Adam:**

## [00:56:40] Patreon

[00:56:40] **Adam:** this episode of Working Code soon to be the testing podcast was brought to you by that part of your application, that you're afraid to change because there are no tests and you don't want to break anything. And listeners like you, if you like what we're doing here, you might want to consider supporting us on Patreon.

[00:56:54] **Adam:** And you can do that by going to patreon.com/working code. All of our patrons get early access to an ad free version of new episodes and our after show. We really appreciate all of their support, but our biggest thanks. Go out to our top patrons, Monte and Peter.

[00:57:08] **Adam:**

## [00:57:08] Thanks For Listening!

[00:57:08] **Adam:** Are you staring angrily at your phone right now? Because you could have contributed something to the conversation that we missed.

[00:57:15] **Adam:** It sounds like you should probably join our Discord so that you can talk to a bunch of other like-minded coders and share your knowledge. Go to work and code.dev/discord to join. That's it for this week. We'll catch you next week. And until then,

[00:57:27] **Tim:** Remember your heart. It matters regardless of the percentage of tech debt you have.

## [00:57:32] Bloopers

[00:57:32] **Adam:** and, Tim, can I get like a breaking news?

[00:57:56] **Tim:** What I do last time,

[00:57:58] **Adam:** I don't even remember. Well, this is you did that. It was like the, yeah, but you did, it was something about, the main show topic or whatever. This is breaking news about the Google thing. breaking news. All right. Well, I guess we'll just use me doing. I'm going to be so embarrassed, but why not?

[00:58:18] **Tim:** It seems like every time I talk about money, though, the conversation dies.

[00:58:25] **Carol:** Hmm.

[00:58:25] **Adam:** I'm convinced that Tim doesn't wear pants when we record. Cause every time he gets out of his chair, he turns off his video.

[00:58:31] **Ben:** I've done. I've done a few shows in just my underwear, for sure.

[00:58:36] **Carol:** Wait, you usually have on shirts.

[00:58:38] **Ben:** yeah. Yeah. I mean just the no pants, but I'll have my underwear on,

[00:58:41] **Carol:** yeah.

[00:58:42] **Ben:** they're boxer briefs, so they're like shorts anyway,

[00:58:46] **Ben:** but I

[00:58:47] **Ben:** also

[00:58:47] **Adam:** there's not two layers,

[00:58:49] **Ben:** It's not too late. It's just one layer.

[00:58:51] **Adam:** is

[00:58:52] **Carol:** I have always or pants or shorts or something over my booty recording this by guests. Let's just be clear

[00:59:01] **Adam:** the record

[00:59:02] **Carol:** the record. I'm not

[00:59:04] **Adam:** to two layers of fabric covering all of my genitals.

[00:59:09] **Carol:** here.

[00:59:10] **Adam:** wear pants

[00:59:12] **Carol:** I wear the pants on this podcast.

[00:59:17] **Carol:** so so when you got up, you always turn your camera off 10. So Adam's like, he must never wear pants when he records the podcast.

[00:59:26] **Tim:** do. It's just, I just find it. People moving around. It's kind of distracting as I don't want to distract anyone's eyes. I'm tall. I'm totally wearing pants. Look,

[00:59:36] **Adam:** That's a sweet set of hangers you got there.

[00:59:39] **Tim:** thanks.

[00:59:40] **Carol:** So Ben openly admitted. He might not wear pants sometimes when recording

[00:59:45] **Tim:** Really.

[00:59:46] **Ben:** my underwear on, I got my boxer briefs, but especially if it's, you know, in the warmer months, you can't be expected to be wearing pants all the time.

[00:59:57] **Tim:** too

[00:59:57] **Tim:** much. It's too much to

[00:59:59] **Tim:** ask.

[01:00:01] **Adam:** I think working from home has gotten to you Ben,

[01:00:04] **Tim:** Yeah. You also don't have kids. I don't want the kids to see my twigs and berries
